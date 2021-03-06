---
title: Gestire i componenti aggiuntivi nell'interfaccia di amministrazione
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: Informazioni su come distribuire i componenti aggiuntivi per gli utenti e i gruppi dell'organizzazione tramite la distribuzione centralizzata nell'interfaccia di amministrazione.
ms.openlocfilehash: caaea8404c099f56704d21684323a4b20e61f52d
ms.sourcegitcommit: 222fc3f8841de82b1b558f47db8a79aa5054d0ed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/11/2020
ms.locfileid: "45103100"
---
# <a name="manage-add-ins-in-the-admin-center"></a>Gestire i componenti aggiuntivi nell'interfaccia di amministrazione

::: moniker range="o365-21vianet"

> [!NOTE]
> L'interfaccia di amministrazione sta cambiando. Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

I componenti aggiuntivi di Office consentono di personalizzare i documenti e semplificare la modalità di accesso alle informazioni sul Web (vedere [iniziare a utilizzare il componente aggiuntivo di Office](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)). 

Dopo che un amministratore ha distribuito i componenti aggiuntivi per gli utenti di un'organizzazione, l'amministratore può disattivare o disabilitare i componenti aggiuntivi, modificare, eliminare e gestire l'accesso ai componenti aggiuntivi.

Per ulteriori informazioni sull'installazione dei componenti aggiuntivi dall'interfaccia di amministrazione, vedere [deploy Add-ins in the Admin Center](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins).
  
## <a name="add-in-states"></a>Stati dei componenti aggiuntivi

Un componente aggiuntivo può **essere in uno stato attivato o** **disattivato** .
  
|**Stato**|**Quando si verifica lo stato**|**Impatto**|
|:-----|:-----|:-----|
|**Attivazione**  <br/> |L'amministratore ha caricato il componente aggiuntivo e lo ha assegnato a utenti o gruppi.  <br/> |Gli utenti e i gruppi assegnati al componente aggiuntivo lo vedono nei client pertinenti.  <br/> |
|**Disattivato**  <br/> |L'amministratore ha disattivato il componente aggiuntivo.  <br/> |Gli utenti e i gruppi assegnati al componente aggiuntivo non possono più accedervi.  <br/> Se lo stato del componente aggiuntivo viene modificato su Attivo, gli utenti e i gruppi potranno accedervi di nuovo.  <br/> |
|**Eliminato**  <br/> |L'amministratore ha eliminato il componente aggiuntivo.  <br/> |Gli utenti e i gruppi assegnati al componente aggiuntivo non possono più accedervi.  <br/> |
   
Se non è più in uso, è consigliabile eliminare un componente aggiuntivo. La disattivazione di un componente aggiuntivo, ad esempio, può avere senso se un componente aggiuntivo viene utilizzato solo in periodi specifici dell'anno.

## <a name="delete-an-add-in"></a>Eliminare un componente aggiuntivo

È inoltre possibile eliminare un componente aggiuntivo distribuito.

1. Nell'interfaccia di amministrazione passare alla pagina **Impostazioni**  >  **& componenti** aggiuntivi.

2. Selezionare il componente aggiuntivo distribuito.

3. Fare clic su **Elimina componente aggiuntivo**. Rimuovere il pulsante del componente aggiuntivo nell'angolo in basso a destra.

4. Convalidare le selezioni e scegliere **Rimuovi componente aggiuntivo**.

## <a name="edit-add-in-access"></a>Modificare l'accesso del componente aggiuntivo

Dopo la distribuzione, gli amministratori possono anche gestire l'accesso degli utenti ai componenti aggiuntivi.

1. Nell'interfaccia di amministrazione passare alla pagina **Impostazioni**  >  **& componenti** aggiuntivi.

2. Selezionare il componente aggiuntivo distribuito.

3. Fare clic su **modifica** in **chi ha accesso**.

4. Salvare le modifiche.

## <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a>Impedisci download del componente aggiuntivo disattivando l'archivio di Office in tutti i client (eccetto Outlook)

> [!NOTE]
> L'installazione del componente aggiuntivo di Outlook è gestita da un [processo diverso](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx).

Come organizzazione, è possibile che si desideri impedire il download di nuovi componenti aggiuntivi di Office dall'Office Store. Questo può essere utilizzato insieme alla distribuzione centralizzata per garantire che vengano distribuiti solo i componenti aggiuntivi approvati dall'organizzazione per gli utenti all'interno dell'organizzazione.
  
**Per disattivare l'acquisizione del componente aggiuntivo**
  
1. Nell'interfaccia di amministrazione passare a **Impostazioni** \> [Servizi &amp; componenti aggiuntivi](https://go.microsoft.com/fwlink/p/?linkid=2053743).
    
3. Selezionare **le app e i servizi posseduti dall'utente**.
    
4. Cancellare l'opzione per consentire agli utenti di accedere a Office Store.

In questo modo tutti gli utenti potranno acquistare i componenti aggiuntivi seguenti dall'archivio.
  
- Componenti aggiuntivi per Word, Excel e PowerPoint 2016 da:
    
  - Windows
    
  - Mac
    
  - Ufficio
    
    
- Acquisizioni che iniziano all'interno di **AppSource**
    
- Componenti aggiuntivi in Microsoft 365
    
Un utente che cerca di accedere all'archivio vedrà il messaggio seguente: **Microsoft 365 è stato configurato per impedire l'acquisizione individuale dei componenti aggiuntivi di Office Store.**
  
Il supporto per la disattivazione di Office Store è disponibile nelle versioni seguenti:
  
- Windows: 16.0.9001-attualmente disponibile.
    
- Mac: 16.10.18011401-attualmente disponibile.
    
- iOS: 2.9.18010804-attualmente disponibile.
    
- Il Web-attualmente disponibile.
    
Questo non impedisce a un amministratore di utilizzare la distribuzione centralizzata per assegnare un componente aggiuntivo da Office Store.
  
Per impedire a un utente di accedere con un account Microsoft, è possibile limitare l'accesso per utilizzare solo l'account dell'organizzazione. Per ulteriori informazioni, vedere [identità, autenticazione e autorizzazione in Office 2016](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx).  

## <a name="more-about-the-end-user-experience-with-add-ins"></a>Ulteriori informazioni sull'esperienza degli utenti finali con i componenti aggiuntivi

Dopo aver distribuito un componente aggiuntivo, gli utenti finali possono iniziare a utilizzarlo nelle proprie applicazioni di Office (vedere [iniziare a usare il componente aggiuntivo di Office](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)). Il componente aggiuntivo viene visualizzato in tutte le piattaforme supportate dal componente aggiuntivo.
  
Se il componente aggiuntivo supporta i comandi dell'interfaccia, questi vengono visualizzati sulla barra multifunzione di Office. Nell'esempio seguente il comando **Cerca citazione** viene visualizzato per il componente aggiuntivo **Citazioni**. 

![Barra multifunzione di Office con citazioni di ricerca](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
Se il componente aggiuntivo distribuito non supporta i comandi del componente aggiuntivo o se si desidera visualizzare tutti i componenti aggiuntivi distribuiti, è possibile visualizzarli tramite i **componenti**aggiuntivi. 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a>In Word 2016, Excel 2016 o PowerPoint 2016

1. Selezionare **Inserisci \> i componenti**aggiuntivi. 
    
2. Selezionare la scheda **Gestito dall'amministratore** nella finestra Componenti aggiuntivi per Office. 
    
3. Fare doppio clic sul componente aggiuntivo distribuito in precedenza, in questo esempio **Citazioni**. <br/>![Scheda gestita dall'amministratore della pagina dei componenti aggiuntivi di Office](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)
  
### <a name="in-outlook"></a>In Outlook

1. Nella barra multifunzione **Home** selezionare **Ricevi componenti**aggiuntivi.<br/>![Pulsante Store in Outlook](../../media/getaddinsicon.png)
  
2. Selezionare **gestito dall'amministratore** nel NAV sinistro. 

## <a name="learn-more"></a>Altre informazioni

[Distribuire i componenti aggiuntivi nell'interfaccia di amministrazione](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)

Altre informazioni sulla creazione e sulla compilazione dei [componenti aggiuntivi per Office](https://go.microsoft.com/fwlink/p/?linkid=846362).
  
[Utilizzare i cmdlet di PowerShell per la distribuzione centralizzata per gestire i componenti](https://docs.microsoft.com/office365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins)aggiuntivi.
  
[Risoluzione dei problemi: utenti che non vedono componenti aggiuntivi](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)

[Minorenni e acquisizione di componenti aggiuntivi da Microsoft Store](https://docs.microsoft.com/microsoft-365/admin/manage/minors-and-acquiring-addins-from-the-store)