---
title: Utilizzare PowerShell per eseguire una migrazione a fasi a Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: a20f9dbd-6102-4ffa-b72c-ff813e700930
description: Informazioni su come utilizzare PowerShell per spostare il contenuto da un sistema di posta elettronica di origine nel tempo utilizzando una migrazione a fasi a Microsoft 365.
ms.openlocfilehash: ebf2067fe7ae9fc2d2b58d0aa804c7843295b38a
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691103"
---
# <a name="use-powershell-to-perform-a-staged-migration-to-microsoft-365"></a>Utilizzare PowerShell per eseguire una migrazione a fasi a Microsoft 365

*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*

È possibile migrare il contenuto delle cassette postali degli utenti da un sistema di posta elettronica di origine a Microsoft 365 nel tempo utilizzando una migrazione a fasi.
  
In questo articolo vengono illustrate le attività necessarie per una migrazione della posta elettronica a fasi tramite PowerShell di Exchange Online. L'argomento, [che cosa è necessario sapere su una migrazione a fasi della posta elettronica](https://go.microsoft.com/fwlink/p/?LinkId=536487), fornisce una panoramica del processo di migrazione. Una volta appresi i contenuti di questo articolo, utilizzare quest'ultimo per iniziare la migrazione delle cassette postali da un sistema di posta elettronica a un altro.
  
> [!NOTE]
> È anche possibile utilizzare l'interfaccia di amministrazione di Exchange per eseguire la migrazione a fasi. Vedere [eseguire una migrazione a fasi della posta elettronica a Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=536687). 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

Tempo stimato per il completamento di questa attività: tra i 2 e i 5 minuti per creare un batch di migrazione. Dopo l'avvio del batch di migrazione, la durata della migrazione varia in base al numero di cassette postali nel batch, alla dimensione di ogni cassetta postale e alla capacità di rete disponibile. Per informazioni sugli altri fattori che influiscono sul tempo necessario per eseguire la migrazione delle cassette postali a Microsoft 365, vedere [Migration performance](https://go.microsoft.com/fwlink/p/?LinkId=275079).
  
È necessario disporre delle autorizzazioni per poter eseguire queste procedure. Per verificare le autorizzazioni necessarie, vedere la voce "Migrazione" nell'argomento [Autorizzazioni di destinatari](https://go.microsoft.com/fwlink/p/?LinkId=534105).
  
Per utilizzare i cmdlet di PowerShell di Exchange Online, è necessario eseguire l'accesso e importare i cmdlet nella sessione di Windows PowerShell locale. Per le istruzioni, vedere [Connettersi a Exchange Online tramite Remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=534121).
  
Per un elenco completo dei comandi di migrazione, vedere [Cmdlet di spostamento e migrazione](https://go.microsoft.com/fwlink/p/?LinkId=534750).
  
## <a name="migration-steps"></a>Procedura della migrazione

### <a name="step-1-prepare-for-a-staged-migration"></a>Passaggio 1: predisporre la migrazione a fasi

Prima di eseguire la migrazione delle cassette postali a Microsoft 365 utilizzando una migrazione a fasi, è necessario apportare alcune modifiche all'ambiente di Exchange.
  
 **Configurare Outlook via Internet su Exchange Server locale** Il servizio di migrazione della posta elettronica utilizza Outlook via Internet (noto come RPC su HTTP) per connettersi a Exchange Server locale. Per informazioni su come impostare Outlook via Internet per Exchange Server 2007 e Exchange 2003, vedere gli argomenti seguenti:
  
- [Exchange 2007: Come abilitare Outlook Anywhere](https://go.microsoft.com/fwlink/?LinkID=167210)
    
- [Configurazione di Outlook via Internet con Exchange 2003](https://go.microsoft.com/fwlink/?LinkID=167209)
    
> [!IMPORTANT]
> È necessario utilizzare un certificato rilasciato da un'autorità di certificazione attendibile (CA) con la configurazione di Outlook via Internet. Non è possibile configurare Outlook via Internet con un certificato autofirmato. Per ulteriori informazioni, vedere [Come configurare SSL per Outlook via Internet](https://go.microsoft.com/fwlink/?LinkID=80875) 
  
 **Facoltativo: verificare che sia possibile connettersi all'organizzazione di Exchange utilizzando Outlook via Internet** Utilizzare uno dei seguenti metodi per verificare le impostazioni di connessione.
  
- Utilizzare Outlook all'esterno della rete aziendale per connettersi alla cassetta postale di Exchange locale.
    
- Utilizzare l' [Analizzatore connettività remota Microsoft](https://https://testconnectivity.microsoft.com/) per testare le impostazioni di connessione. Utilizzare i test di individuazione automatica di Outlook o Outlook via Internet (RPC su HTTP).
    
- In PowerShell di Exchange Online, eseguire i comandi seguenti:
    
  ```powershell
  $Credentials = Get-Credential
  ```

  ```powershell
  Test-MigrationServerAvailability -ExchangeOutlookAnywhere -Autodiscover -EmailAddress <email address for on-premises administrator> -Credentials $credentials
  ```

 **Impostare le autorizzazioni** L'account utente locale utilizzato per la connessione all'organizzazione di Exchange locale (denominato anche amministratore della migrazione) deve disporre delle autorizzazioni necessarie per accedere alle cassette postali locali di cui si desidera eseguire la migrazione a Microsoft 365. Questo account utente verrà usato per eseguire la connessione al sistema di posta elettronica creando un endpoint di migrazione più avanti in questa procedura ([Passaggio 3: creare un endpoint di migrazione](use-powershell-to-perform-a-staged-migration-to-microsoft-365.md#BK_Endpoint) ).
  
Per eseguire la migrazione delle cassette postali, l'amministratore deve disporre di uno dei seguenti set di autorizzazioni:
  
- Essere un membro del gruppo **Domain Admins** di Active Directory nell'organizzazione locale.
    
    oppure
    
- Disporre dell'autorizzazione **FullAccess** per ogni cassetta postale locale e dell'autorizzazione **WriteProperty** per modificare la proprietà **TargetAddress** negli account utente locali.
    
    oppure
    
- Disporre dell'autorizzazione **Receive As** sul database delle cassette postali locale in cui sono memorizzate le cassette postali degli utenti e dell'autorizzazione **WriteProperty** per modificare la proprietà **TargetAddress** negli account utente locali.
    
Per istruzioni su come impostare queste autorizzazioni, vedere [assegnare le autorizzazioni per eseguire la migrazione delle cassette postali a Microsoft 365](https://go.microsoft.com/fwlink/?LinkId=521656).
  
 **Disabilitare la messaggistica unificata** Se la messaggistica unificata è attivata per le cassette postali locali, disattivarla prima di eseguirne le migrazione. Una volta completata la migrazione, attivare la messaggistica unificata per le cassette postali. Per le procedure da eseguire, vedere l'argomento relativo alla[disabilitazione della messaggistica unificata](https://go.microsoft.com/fwlink/?LinkId=521891).
  
 **Utilizzare la sincronizzazione della directory per creare nuovi utenti in Microsoft 365.** È possibile utilizzare la sincronizzazione della directory per creare tutti gli utenti locali nell'organizzazione Microsoft 365.
  
Dopo avere creato gli utenti, è necessario assegnare loro le licenze. Il tempo disponibile per aggiungere le licenze dopo la creazione degli utenti è di 30 giorni. Per la procedura per aggiungere licenze, vedere [Passaggio 8: completare le attività successive alla migrazione](use-powershell-to-perform-a-staged-migration-to-microsoft-365.md#BK_Postmigration).
  
 È possibile utilizzare lo strumento di sincronizzazione di Microsoft Azure Active Directory (Azure AD) o Microsoft Azure AD Sync Services per sincronizzare e creare gli utenti locali in Microsoft 365. Dopo la migrazione delle cassette postali a Microsoft 365, è possibile gestire gli account utente nell'organizzazione locale e vengono sincronizzati con l'organizzazione Microsoft 365. Per ulteriori informazioni, vedere [Integrazione di directory](https://go.microsoft.com/fwlink/?LinkId=521788) .
  
### <a name="step-2-create-a-csv-file-for-a-staged-migration-batch"></a>Passaggio 2: creazione di un file CSV per un batch di migrazione a fasi

Dopo aver identificato gli utenti delle cassette postali locali di cui si desidera eseguire la migrazione a Microsoft 365, è possibile utilizzare un file CSV (comma separated value) per creare un batch di migrazione. Ogni riga del file CSV, utilizzata da Microsoft 365 per eseguire la migrazione, contiene informazioni su una cassetta postale locale. 
  
> [!NOTE]
> Non esiste un limite per il numero di cassette postali di cui è possibile eseguire la migrazione a Microsoft 365 utilizzando una migrazione a fasi. Il file CSV per un batch di migrazione può contenere al massimo 2.000 righe. Per eseguire la migrazione di oltre 2.000 cassette postali, creare altri file CSV e usare ogni file per creare un nuovo batch di migrazione. 
  
 **Attributi supportati**
  
Il file CSV per una migrazione a fasi supporta i tre attributi seguenti. Ogni riga nel file CSV corrisponde a una cassetta postale e deve contenere un valore per ognuno di questi attributi.
  
|**Attributo**|**Descrizione**|**Obbligatorio?**|
|:-----|:-----|:-----|
|EmailAddress  <br/> |Specifica l'indirizzo di posta elettronica SMTP principale, ad esempio pilarp@contoso.com, per le cassette postali locali.  <br/> Utilizzare l'indirizzo SMTP primario per le cassette postali locali e non gli ID utente di Microsoft 365. Ad esempio, se il dominio locale è denominato contoso.com ma il dominio di posta elettronica Microsoft 365 è denominato service.contoso.com, è necessario utilizzare il nome di dominio contoso.com per gli indirizzi di posta elettronica nel file CSV.  <br/> |Obbligatorio  <br/> |
|Password  <br/> |La password da impostare per la nuova cassetta postale di Microsoft 365. Le restrizioni relative alle password applicate all'organizzazione Microsoft 365 si applicano anche alle password incluse nel file CSV.  <br/> |Facoltativo  <br/> |
|ForceChangePassword  <br/> |Specifica se un utente deve modificare la password la prima volta che accedono alla nuova cassetta postale di Microsoft 365. Usare **True** o **False** per il valore di questo parametro. <br/> > [!NOTE]> Se è stata implementata una soluzione Single Sign-On (SSO) distribuendo Active Directory Federation Services (ADFS) o versioni successive nell'organizzazione locale, è necessario usare **False** come valore dell'attributo **ForceChangePassword**.          |Facoltativo  <br/> |
   
 **Formato del file CSV**
  
Di seguito viene illustrato un esempio di formato per il file CSV. In questo esempio, tre cassette postali locali vengono migrate a Microsoft 365.
  
Nella prima riga, o riga di intestazione, del file CSV sono elencati i nomi degli attributi, o campi, specificati nelle righe successive. Il nome di ciascun attributo è separato da una virgola.
  
```powershell
EmailAddress,Password,ForceChangePassword 
pilarp@contoso.com,Pa$$w0rd,False 
tobyn@contoso.com,Pa$$w0rd,False 
briant@contoso.com,Pa$$w0rd,False 
```

Ogni riga che segue l'intestazione rappresenta un utente e fornisce le informazioni che verranno utilizzate per la migrazione della cassetta postale di tale utente. I valori degli attributi di ciascuna riga devono trovarsi nello stesso ordine in cui sono elencati i nomi degli attributi nella riga di intestazione. 
  
Per creare il file CSV, è possibile utilizzare un editor di testo o un'applicazione come Excel. Salvare il file con estensione .csv o .txt.
  
> [!NOTE]
> Se il file CSV contiene caratteri speciali o non ASCII, salvarlo con la codifica UTF-8 o Unicode. A seconda dell'applicazione, il salvataggio del file CSV con codifica UTF-8 o Unicode può risultare più semplice quando le impostazioni locali del sistema del computer corrispondono alla lingua usata nel file CSV. 
  
### <a name="step-3-create-a-migration-endpoint"></a>Passaggio 3: creare un endpoint di migrazione
<a name="BK_Endpoint"> </a>

Per eseguire correttamente la migrazione della posta elettronica, Microsoft 365 deve connettersi e comunicare con il sistema di posta elettronica di origine. A tale scopo, Microsoft 365 utilizza un endpoint di migrazione. Per creare un endpoint di migrazione di Outlook via Internet usando PowerShell per una migrazione a fasi, è necessario innanzitutto [connettersi a Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=534121). 
  
Per un elenco completo dei comandi di migrazione, vedere [Cmdlet di spostamento e migrazione](https://go.microsoft.com/fwlink/p/?LinkId=534750).
  
Per creare un endpoint di migrazione di Outlook via Internet denominato "StagedEndpoint" in PowerShell di Exchange Online, eseguire i comandi seguenti:
  
```powershell
$Credentials = Get-Credential
```

```powershell
New-MigrationEndpoint -ExchangeOutlookAnywhere -Name StagedEndpoint -Autodiscover -EmailAddress administrator@contoso.com -Credentials $Credentials
```

Per ulteriori informazioni sul cmdlet **New-MigrationEndpoint**, vedere[New-MigrationEndpoint](https://go.microsoft.com/fwlink/p/?LinkId=536437).
  
> [!NOTE]
> Il cmdlet **New-MigrationEndpoint** può essere utilizzato per specificare un database per il servizio da utilizzare tramite l'opzione **-TargetDatabase**. In caso contrario, un database viene assegnato in modo casuale dal sito di Active Directory Federation Services (ADFS) 2.0 in cui si trova la cassetta postale di gestione.
  
#### <a name="verify-it-worked"></a>Verificare che il passaggio di migrazione sia avvenuto correttamente

In PowerShell di Exchange Online eseguire il comando riportato di seguito per visualizzare le informazioni sull'endpoint di migrazione "StagedEndpoint":
  
```powershell
Get-MigrationEndpoint StagedEndpoint | Format-List EndpointType,ExchangeServer,UseAutoDiscover,Max*
```

### <a name="step-4-create-and-start-a-stage-migration-batch"></a>Passaggio 4: creare e avviare un batch di migrazione a fasi
<a name="BK_Endpoint"> </a>

È possibile utilizzare il cmdlet **New-MigrationBatch** in PowerShell di Exchange Online per creare un batch di migrazione per una migrazione completa. È possibile creare un batch di migrazione e avviarlo automaticamente includendo il parametro _AutoStart_. In alternativa, è possibile creare il batch di migrazione, per poi avviarlo utilizzando il cmdlet **Start-MigrationBatch**. In questo esempio viene creato un batch di migrazione denominato "StagedBatch1" e viene utilizzato l'endpoint di migrazione creato nel passaggio precedente.
  
```powershell
New-MigrationBatch -Name StagedBatch1 -SourceEndpoint StagedEndpoint -AutoStart
```

In questo esempio viene inoltre creato un batch di migrazione denominato "StagedBatch1" e viene utilizzato l'endpoint di migrazione creato nel passaggio precedente. Poiché il parametro  _AutoStart_ non è incluso, il batch di migrazione deve essere avviato manualmente nel dashboard di migrazione oppure utilizzando il cmdlet **Start-MigrationBatch**. Come illustrato in precedenza, può esistere solo un batch di migrazione completa alla volta.
  
```powershell
New-MigrationBatch -Name StagedBatch1 -SourceEndpoint StagedEndpoint
```

#### <a name="verify-it-worked"></a>Verificare che il passaggio di migrazione sia avvenuto correttamente

Eseguire il seguente comando in PowerShell di Exchange Online per visualizzare informazioni su "StagedBatch1":
  
```powershell
Get-MigrationBatch -Identity StagedBatch1 | Format-List
```

È inoltre possibile verificare che il batch sia stato avviato eseguendo il comando riportato di seguito:
  
```powershell
Get-MigrationBatch -Identity StagedBatch1 | Format-List Status
```

Per ulteriori informazioni sul cmdlet **Get-MigrationBatch**, vedere[Get-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536441).
  
### <a name="step-5-convert-on-premises-mailboxes-to-mail-enabled-users"></a>Passaggio 5: convertire le cassette postali locali in utenti abilitati alla posta
<a name="BK_Endpoint"> </a>

Dopo la migrazione di un batch di cassette postali, è necessario fare in modo che gli utenti possano accedere alla propria posta. Un utente la cui cassetta postale è stata migrata ora dispone di una cassetta postale locale e una in Microsoft 365. Gli utenti che dispongono di una cassetta postale in Microsoft 365 impediscono la ricezione di una nuova posta nella cassetta postale locale. 
  
Poiché non è possibile eseguire le migrazioni, non si è ancora pronti a indirizzare tutti gli utenti a Microsoft 365 per la posta elettronica. Cosa si può fare per gli utenti che dispongono di entrambi? È possibile modificare le cassette postali locali di cui è già stata eseguita la migrazione agli utenti abilitati alla posta elettronica. Quando si passa da una cassetta postale a un utente abilitato alla posta elettronica, è possibile indirizzare l'utente a Microsoft 365 per la posta elettronica anziché passare alla propria cassetta postale locale. 
  
Un altro motivo importante per convertire le cassette postali locali in utenti abilitati alla posta elettronica consiste nel mantenere gli indirizzi proxy dalle cassette postali di Microsoft 365 copiando gli indirizzi proxy negli utenti abilitati alla posta elettronica. In questo modo è possibile gestire gli utenti basati su cloud dall'organizzazione locale utilizzando Active Directory. Inoltre, se si decide di rimuovere l'organizzazione di Exchange Server locale dopo che tutte le cassette postali vengono migrate a Microsoft 365, gli indirizzi proxy che sono stati copiati negli utenti abilitati alla posta elettronica rimarranno in Active Directory locale.
    
### <a name="step-6-delete-a-staged-migration-batch"></a>Passaggio 6: eliminare un batch di migrazione a fasi
<a name="BK_Endpoint"> </a>

 Dopo che tutte le cassette postali incluse in un batch di migrazione sono state migrate correttamente, e una volta convertite tutte le cassette postali locali del batch in utenti abilitati alla posta, si può procedere all'eliminazione del batch di migrazione a fasi. Assicurarsi di verificare che la posta elettronica venga inoltrata alle cassette postali di Microsoft 365 nel batch di migrazione. Quando si elimina un batch di migrazione in fasi, il servizio di migrazione cancella tutti i record relativi al batch di migrazione ed elimina il batch di migrazione.
  
Per eliminare il batch di migrazione "StagedBatch1" in PowerShell di Exchange Online, eseguire il comando riportato di seguito.
  
```powershell
Remove-MigrationBatch -Identity StagedBatch1
```

Per ulteriori informazioni sul cmdlet **Remove-MigrationBatch**, vedere[Remove-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536481).
  
#### <a name="verify-it-worked"></a>Verificare che il passaggio di migrazione sia avvenuto correttamente

Eseguire il seguente comando in PowerShell di Exchange Online per visualizzare informazioni su "IMAPBatch1":
  
```powershell
Get-MigrationBatch StagedBatch1
```

Il comando restituirà il batch di migrazione con uno stato di **Rimozione in corso** o restituirà un errore che informa che non è possibile trovare il batch di migrazione, confermandone l'eliminazione.
  
Per ulteriori informazioni sul cmdlet **Get-MigrationBatch**, vedere[Get-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536441).
  
### <a name="step7-assign-licenses-to-microsoft-365-users"></a>STEP7: assegnare le licenze agli utenti di Microsoft 365
<a name="BK_Endpoint"> </a>

Attivare gli account utente di Microsoft 365 per gli account migrati assegnando le licenze. Se non si assegna una licenza, la cassetta postale viene disabilitata allo scadere del periodo di prova (30 giorni). Per assegnare una licenza nell'interfaccia di amministrazione di Microsoft 365, vedere [assegnare o](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)annullare l'assegnazione delle licenze.
  
### <a name="step-8-complete-post-migration-tasks"></a>Passaggio 8: completare le attività successive alla migrazione
<a name="BK_Postmigration"> </a>

- **Creare un record DNS di individuazione automatica affinché gli utenti possano accedere facilmente alle proprie cassette postali.** Dopo la migrazione di tutte le cassette postali locali a Microsoft 365, è possibile configurare un record DNS di individuazione automatica per l'organizzazione di Microsoft 365 per consentire agli utenti di connettersi facilmente alle nuove cassette postali di Microsoft 365 con Outlook e i client mobili. Questo nuovo record DNS di individuazione automatica deve utilizzare lo stesso spazio dei nomi che si sta utilizzando per l'organizzazione Microsoft 365. Ad esempio, se lo spazio dei nomi basato su cloud è cloud.contoso.com, il record DNS di individuazione automatica che deve essere creato è autodiscover.cloud.contoso.com.
    
    Microsoft 365 utilizza un record CNAME per implementare il servizio di individuazione automatica per Outlook e i client mobili. Il record CNAME di individuazione automatica deve includere le seguenti informazioni:
    
  - **Alias:** individuazione automatica
    
  - **Destinazione:** autodiscover.outlook.com
    
    Per ulteriori informazioni, vedere [aggiungere record DNS per connettere il dominio](https://go.microsoft.com/fwlink/p/?LinkId=535028).
    
- **Rimuovere i server di Exchange locali.** Dopo aver verificato che tutti i messaggi di posta elettronica vengono instradati direttamente alle cassette postali di Microsoft 365 e non è più necessario mantenere l'organizzazione di posta elettronica locale o non pianificare l'implementazione di una soluzione SSO, è possibile disinstallare Exchange dai server e rimuovere l'organizzazione di Exchange locale.
    
    Per ulteriori informazioni, vedere gli argomenti seguenti:
    
  - [Modifica o eliminazione di Exchange 2010](https://go.microsoft.com/fwlink/?LinkId=217936)
    
  - [Come rimuovere un'organizzazione di Exchange 2007](https://go.microsoft.com/fwlink/?LinkID=100485)
    
  - [Disinstallazione di Exchange Server 2003](https://go.microsoft.com/fwlink/?LinkID=56561)
    

