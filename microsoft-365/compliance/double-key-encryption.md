---
title: Crittografia a chiave doppia (DKE)
description: DKE consente di proteggere i dati altamente riservati mantenendo il controllo completo della chiave.
author: kccross
ms.author: krowley
manager: laurawi
ms.date: 07/21/2020
ms.topic: conceptual
ms.service: information-protection
audience: Admin
ms.reviewer: esaggese
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.openlocfilehash: f36eeeb1f228bff48088cbbf3241d6866d0b3a21
ms.sourcegitcommit: 234726a1795d984c4659da68f852d30a4dda5711
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/18/2020
ms.locfileid: "46794165"
---
# <a name="double-key-encryption-dke"></a>Crittografia a chiave doppia (DKE)

> *Si applica a: crittografia a chiave doppia per Microsoft 365 Public Preview, [microsoft 365 Compliance](https://www.microsoft.com/microsoft-365/business/compliance-management), [Azure Information Protection](https://azure.microsoft.com/pricing/details/information-protection)*
>
> *Istruzioni per: [client di etichettatura unificata di Azure Information Protection per Windows](https://docs.microsoft.com/azure/information-protection/faqs#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*
>
> *Descrizione del servizio per: [conformità di Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*

La crittografia a chiave doppia (DKE) utilizza due tasti insieme per accedere al contenuto protetto. Si archivia una chiave in Microsoft Azure e si tiene premuto l'altro tasto. Il client Azure Information Protection Unified Labeling protegge i contenuti estremamente riservati quando si mantiene il controllo completo di una delle chiavi.

La crittografia a chiave doppia supporta sia le distribuzioni cloud che quelle locali. Queste distribuzioni contribuiscono a garantire che i dati crittografati rimangano opachi ovunque vengano archiviati i dati protetti.

Per ulteriori informazioni sulle chiavi radice tenant basate su cloud predefinite, vedere [Planning and implementing your Azure Information Protection tenant Key](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key).

<!--
The following video shows how Double Key Encryption works to secure your content.

> [!VIDEO https://msit.microsoftstream.com/embed/video/f466a1ff-0400-a936-221c-f1eab45dc756]
-->

Se le organizzazioni hanno uno dei requisiti seguenti, è possibile utilizzare DKE per proteggere il contenuto:

- Si desidera garantire che sia possibile decrittografare il contenuto protetto *solo* in tutte le circostanze.
- Non si desidera che Microsoft abbia accesso ai dati protetti da solo.
- Sono necessari requisiti normativi per mantenere le chiavi all'interno di un limite geografico. Tutte le chiavi conservate per la crittografia e la decrittografia dei dati vengono mantenute nel Data Center.

## <a name="system-and-licensing-requirements-for-dke"></a>Requisiti di sistema e licenze per DKE

La crittografia a chiave doppia per Microsoft 365 è disponibile con Microsoft 365 E5 e Office 365 E5. Se non si dispone di una licenza Microsoft 365 E5, è possibile iscriversi per una [versione di valutazione](https://aka.ms/M365E5ComplianceTrial). Per ulteriori informazioni su queste licenze, vedere [Microsoft 365 Licensing Guidance for security & Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).

**Office Insider** Per utilizzare l'anteprima pubblica, è necessario essere membri del programma Office Insider. Per partecipare a Office Insider, accedere a [https://insider.office.com](https://insider.office.com) . Una volta che si è membri, preparare l'ambiente per la distribuzione di Office Insider Builds scegliendo il metodo di distribuzione appropriato per la propria organizzazione. Per istruzioni, vedere [Guida introduttiva alla distribuzione di Office Insider Builds](https://insider.office.com/business/deploy).

**Azure Information Protection**. DKE funziona con le etichette di riservatezza e richiede la protezione delle informazioni di Azure.

## <a name="supported-environments-for-storing-and-viewing-dke-protected-content"></a>Ambienti supportati per l'archiviazione e la visualizzazione di contenuto protetto da DKE

**Applicazioni supportate**. [Microsoft 365 Apps for Enterprise](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product) clients on Windows, tra cui Word, Excel e PowerPoint.

**Supporto per i contenuti online**. Sono supportati i documenti e i file archiviati online in Microsoft SharePoint e OneDrive for business. È possibile condividere il contenuto crittografato tramite posta elettronica, ma non è possibile visualizzare i documenti e i file crittografati online. Al contrario, è necessario visualizzare il contenuto protetto utilizzando le app desktop del computer locale.

## <a name="about-this-public-preview-article"></a>Informazioni sull'articolo relativo all'anteprima pubblica

Sono disponibili diversi modi per completare alcuni passaggi per la distribuzione della crittografia a chiave doppia. In questo articolo vengono fornite istruzioni dettagliate per consentire agli amministratori meno esperti di distribuire correttamente il servizio. Se si ha familiarità con questo metodo, è possibile scegliere di utilizzare i propri metodi.

In questo articolo sono incluse istruzioni dettagliate su come distribuire il servizio di crittografia a chiave doppia in Azure. Questo scenario non è qualcosa che si potrebbe fare in produzione. Per l'anteprima pubblica, l'utilizzo di Azure rappresenta una soluzione rapida per la distribuzione di DKE. La distribuzione in Azure consente di iniziare a usare la crittografia a chiave doppia immediatamente.

È possibile distribuire il servizio localmente sulla rete o con un altro provider. Sarà necessario pubblicare l'archivio chiavi utilizzando metodi adatti per tale percorso.

## <a name="deploy-double-key-encryption"></a>Distribuire la crittografia a chiave doppia

Questo articolo e il video sulla distribuzione utilizzano Azure come destinazione di distribuzione per il servizio DKE. Se si esegue la distribuzione in un'altra posizione, è necessario fornire i propri valori.

Guardare il [video sulla distribuzione di crittografia a chiave doppia](https://youtu.be/vDWfHN_kygg) per visualizzare la panoramica dettagliata dei concetti nell'articolo. Il video richiede circa 18 minuti per il completamento.

Seguire questi passaggi generali per configurare la crittografia a chiave doppia per l'organizzazione.

1. [Installare i prerequisiti software](#install-software-prerequisites)
1. [Clonare il repository di crittografia GitHub a doppio tasto](#clone-the-dke-github-repository)
1. [Modificare le impostazioni dell'applicazione](#modify-application-settings)
1. [Generare i tasti di testing](#generate-test-keys)
1. [Generare il progetto](#build-the-project)
1. [Pubblicare l'archivio delle chiavi](#publish-the-key-store)
1. [Convalidare la distribuzione](#validate-your-deployment)
1. [Registrare il proprio archivio delle chiavi](#register-your-key-store)
1. [Creare etichette di riservatezza](#create-labels-using-dke)

Al termine, è possibile crittografare documenti e file utilizzando DKE. Per informazioni, vedere [applicare etichette di riservatezza ai propri file e messaggi di posta elettronica in Office](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9).

### <a name="install-software-prerequisites"></a>Installare i prerequisiti software

Esistono due tipi di prerequisiti software per la crittografia a chiave doppia

- [Prerequisiti del servizio di crittografia a doppia chiave](#double-key-encryption-service-prerequisites)
- [Prerequisiti per la crittografia a chiave doppia per i computer client](#double-key-encryption-prerequisites-for-client-computers)

#### <a name="double-key-encryption-service-prerequisites"></a>Prerequisiti del servizio di crittografia a doppia chiave

Installare questi prerequisiti nel computer in cui si desidera installare il servizio DKE.

**.NET Core 3,1 SDK**. Scaricare e installare l'SDK da [download .NET Core 3,1](https://dotnet.microsoft.com/download/dotnet-core/3.1).

**Codice Visual Studio**. Scaricare il codice di Visual Studio da [https://code.visualstudio.com/](https://code.visualstudio.com) . Una volta installato, eseguire codice Visual Studio e selezionare **Visualizza** \> **estensioni**. Installare queste estensioni.

- C# per Visual Studio Code

- Gestione pacchetti NuGet

**Microsoft Office Insider**. Configurare almeno un metodo di [distribuzione](https://insider.office.com/business/deploy).

**Risorse git**. Scaricare e installare una delle opzioni seguenti.

- [Git](https://git-scm.com/downloads)

- [GitHub desktop](https://desktop.github.com/)

- [GitHub Enterprise](https://github.com/enterprise)

**Openssl** È necessario avere installato [openssl](https://slproweb.com/products/Win32OpenSSL.html) per [generare le chiavi di test](#generate-test-keys) dopo la distribuzione di DKE. Assicurarsi di richiamarlo correttamente dal percorso delle variabili di ambiente. Ad esempio, vedere la sezione "aggiungere la directory di installazione al percorso" https://www.osradar.com/install-openssl-windows/ per informazioni dettagliate.

#### <a name="double-key-encryption-prerequisites-for-client-computers"></a>Prerequisiti per la crittografia a chiave doppia per i computer client

Installare questi prerequisiti su ogni computer client in cui si desidera proteggere e utilizzare documenti protetti.

**Microsoft Office** Version *. 12711 o versione successiva.

**Azure Information Protection Unified Labeling client** Versions 2.7.93.0 o versione successiva. Scaricare e installare il client Unified Labeling da [Microsoft](https://www.microsoft.com/download/details.aspx?id=53018).

### <a name="clone-the-dke-github-repository"></a>Clonare il repository di DKE GitHub

Microsoft fornisce i file di origine di DKE in un repository GitHub. È possibile clonare il repository per creare il progetto localmente per l'utilizzo dell'organizzazione. L'archivio di DKE GitHub si trova in [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) .

Le istruzioni riportate di seguito sono destinate agli utenti di codice git o Visual Studio inesperti:

1. Nel browser, vai a: [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService)

1. Verso il lato destro dello schermo, selezionare **codice**. La versione dell'interfaccia utente potrebbe mostrare un pulsante **Clone o download** . Quindi, nell'elenco a discesa che viene visualizzato, selezionare l'icona copia per copiare l'URL negli Appunti.

    Ad esempio:

   ![Clonare il repository del servizio di crittografia a chiave doppia da GitHub](../media/dke-clone.png)

3. In Visual Studio Code, selezionare **Visualizza** \> **tavolozza dei comandi** e selezionare **git: Clone**. Per passare all'opzione nell'elenco, iniziare `git: clone` a digitare per filtrare le voci e quindi selezionarla dal menu a discesa. Ad esempio:

   ![Codice Visual Studio GIT: opzione Clone](../media/dke-vscode-clone.png)

4. Nella casella di testo incollare l'URL copiato da git e selezionare **Clone da GitHub**.

5. Nella finestra di dialogo **Seleziona cartella** visualizzata passare a e selezionare un percorso in cui archiviare il repository. Al prompt dei comandi, selezionare **Apri**.

    L'archivio viene aperto in Visual Studio Code e visualizza il ramo git corrente in basso a sinistra. La succursale deve essere **Master**.

    Ad esempio:

   ![Branch Master di Visual Studio Code](../media/dke-vscode-master.png)

6. Selezionare il **Master** di Word e quindi selezionare **public_preview** nell'elenco dei rami.

   > [!IMPORTANT]
   > Selezionando il ramo public_preview si garantisce che siano presenti i file corretti per la creazione del progetto. Se non si sceglie la succursale corretta, la distribuzione avrà esito negativo.

È ora necessario configurare l'archivio di origine di DKE localmente. Successivamente, [modificare le impostazioni dell'applicazione](#modify-application-settings) per l'organizzazione.

### <a name="modify-application-settings"></a>Modificare le impostazioni dell'applicazione

Per distribuire il servizio DKE, è necessario modificare i tipi di impostazioni dell'applicazione seguenti:

- [Impostazioni di accesso alle chiavi](#key-access-settings)
- [Impostazioni del tenant e delle chiavi](#tenant-and-key-settings)

È possibile modificare le impostazioni dell'applicazione nel appsettings.jssu file. Questo file si trova nel repo di DoubleKeyEncryptionService clonato localmente in DoubleKeyEncryptionService\src\customer-key-store. Ad esempio, in Visual Studio Code è possibile passare al file come illustrato nella figura seguente.

![Individuazione del appsettings.jssu file per DKE.](../media/dke-appsettingsjson.png)

#### <a name="key-access-settings"></a>Impostazioni di accesso alle chiavi

Scegliere se utilizzare la posta elettronica o l'autorizzazione di ruolo. DKE supporta solo uno di questi metodi di autenticazione alla volta.

- **Autorizzazione per la posta elettronica**. Consente all'organizzazione di autorizzare l'accesso alle chiavi solo in base agli indirizzi di posta elettronica.

- **Autorizzazione ruolo**. Consente all'organizzazione di autorizzare l'accesso ai tasti basati su gruppi di Active Directory e richiede che il servizio Web possa eseguire query su LDAP.

**Per impostare le impostazioni di accesso alle chiavi per DKE utilizzando l'autorizzazione per la posta elettronica**

1. Aprire il **appsettings.jssu** file e individuare l' `AuthorizedEmailAddress` impostazione.

2. Aggiungere l'indirizzo o gli indirizzi di posta elettronica che si desidera autorizzare. Separare più indirizzi di posta elettronica con virgolette doppie e virgole. Ad esempio:

   ```json
   "AuthorizedEmailAddress": ["email1@company.com", "email2@company.com ", "email3@company.com"]
   ```

3. Individuare l' `LDAPPath` impostazione e rimuovere il testo `If role authorization is used then this is the LDAP path` tra virgolette doppie. Lasciare le virgolette doppie sul posto. Al termine, l'impostazione dovrebbe essere simile alla seguente.

   ```json
   "LDAPPath": ""
   ```

4. Individuare l' `AuthorizedRoles` impostazione ed eliminare l'intera riga.

Questa immagine Visualizza il **appsettings.jssu** file formattato correttamente per l'autorizzazione della posta elettronica.

   ![Il appsettings.jsnel file che mostra il metodo di autorizzazione della posta elettronica](../media/dke-email-accesssetting.png)

**Per impostare le impostazioni di accesso alle chiavi per DKE utilizzando l'autorizzazione ruolo**

1. Aprire il **appsettings.jssu** file e individuare l' `AuthorizedRoles` impostazione.

2. Aggiungere i nomi dei gruppi di Active Directory che si desidera autorizzare. Separare più nomi di gruppi con virgolette doppie e virgole. Ad esempio:

   ```json
   "AuthorizedRoles": ["group1", "group2", "group3"]
   ```

3. Individuare l' `LDAPPath` impostazione e aggiungere il dominio di Active Directory. Ad esempio:

   ```json
   "LDAPPath": "contoso.com"
   ```

4. Individuare l' `AuthorizedEmailAddress` impostazione ed eliminare l'intera riga.

Questa immagine Visualizza il **appsettings.jssu** file formattato correttamente per l'autorizzazione di ruolo.

   ![appsettings.jsnel file che mostra il metodo di autorizzazione ruolo](../media/dke-role-accesssetting.png)

#### <a name="tenant-and-key-settings"></a>Impostazioni del tenant e delle chiavi

Le impostazioni del tenant e delle chiavi di DKE si trovano nel **appsettings.jssu** file.

**Per configurare le impostazioni relative a tenant e chiavi per DKE**

1. Aprire la **appsettings.jssu** file.

2. Individuare l' `ValidIssuers` impostazione e sostituirla `<tenantid>` con l'ID tenant. È possibile individuare l'ID tenant accedendo al portale di Azure e visualizzando le [proprietà del tenant](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties). Ad esempio:

   ```json
   "ValidIssuers": [
     "https://sts.windows.net/9c99431e-b513-44be-a7d9-e7b500002d4b/"
   ]
   ```

Individuare il `JwtAudience` . Sostituire `<yourhostname>` con il nome host del computer in cui verrà eseguito il servizio DKE. Ad esempio:



  > [!IMPORTANT]
  > Il valore per `JwtAudience` deve corrispondere *esattamente*al nome dell'host. È possibile utilizzare **localhost: 5001** durante il debug. Tuttavia, al termine del debug, aggiornare questo valore al nome host del server.

- `TestKeys:Name`. Immettere un nome per la chiave. Ad esempio: `TestKey1`
- `TestKeys:Id`. Creare un GUID e immetterlo come `TestKeys:ID` valore. Ad esempio, `DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE`. È possibile utilizzare un sito come [Generatore di GUID online](https://guidgenerator.com/) per generare casualmente un GUID.

Questa immagine Visualizza il formato corretto per le impostazioni dei tenant e delle chiavi in **appsettings.jsattiva**. `LDAPPath` è configurata per l'autorizzazione di ruolo.

![Visualizza le impostazioni relative ai tenant e ai tasti corretti per DKE nel appsettings.jssu file.](../media/dke-appsettingsjson-tenantkeysettings.png)

### <a name="generate-test-keys"></a>Generare i tasti di testing

Una volta definite le impostazioni dell'applicazione, si è pronti a generare chiavi di test pubbliche e private.

Per generare chiavi:

1. Dal menu Start di Windows, eseguire il prompt dei comandi di OpenSSL.

1. Passare alla cartella in cui si desidera salvare i tasti di test. I file creati eseguendo la procedura descritta in questa attività sono archiviati nella stessa cartella.

1. Generare il nuovo tasto di test.

   ```dos
   openssl req -x509 -newkey rsa:2048 -keyout key.pem -out cert.pem -days 365
   ```

2. Generare la chiave privata.

   ```dos
   openssl rsa -in key.pem -out privkeynopass.pem
   ```

1. Generare la chiave pubblica.

   ```dos
   openssl rsa -in key.pem -pubout > pubkeyonly.pem
   ```

1. In un editor di testo aprire **pubkeyonly. pem**. Copiare tutto il contenuto del file **pubkeyonly. pem** , tranne la prima e l'ultima riga, nella `PublicPem` sezione del **appsettings.jssu** file.

1. In un editor di testo aprire **privkeynopass. pem**. Copiare tutto il contenuto del file **privkeynopass. pem** , tranne la prima e l'ultima riga, nella `PrivatePem` sezione del **appsettings.jssu** file.

1. Rimuovere tutti gli spazi vuoti e le nuove righe in entrambe le `PublicPem` `PrivatePem` sezioni e.

    > [!IMPORTANT]
    > Quando si copia questo contenuto, non eliminare i dati PEM.

1. In Visual Studio Code passare al file **Startup.cs** . Questo file si trova nel repo di DoubleKeyEncryptionService clonato localmente in DoubleKeyEncryptionService\src\customer-key-store\.

2. Individuare le righe seguenti:

   ```c#
        #if USE_TEST_KEYS
        #error !!!!!!!!!!!!!!!!!!!!!! Use of test keys is only supported for testing,
        DO NOT USE  FOR PRODUCTION !!!!!!!!!!!!!!!!!!!!!!!!!!!!!
        services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
        #endif
   ```

3. Sostituire queste righe con il testo seguente:

   ```csharp
   services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
   ```

   I risultati finali devono essere simili al seguente.

   ![file di startup.cs per l'anteprima pubblica](../media/dke-startupcs-usetestkeys.png)

A questo punto si è pronti per [creare il progetto di DKE](#build-the-project).

### <a name="build-the-project"></a>Generare il progetto

Utilizzare le istruzioni seguenti per creare localmente il progetto DKE:

1. In Visual Studio Code, nell'archivio dei servizi di DKE, selezionare **Visualizza** \> **tavolozza dei comandi** e quindi digitare **Compila** al prompt.

1. Nell'elenco scegliere **attività: Esegui attività di compilazione**.

   Se non sono state trovate attività di compilazione, selezionare **Configura attività di compilazione** e crearne una per .NET Core come indicato di seguito.

   ![Configurare l'attività di compilazione mancante per .NET](../media/dke-configurebuildtask.png)

   1. Scegliere **crea tasks.jssu da modello**.

   ![Creare tasks.jssu file da modello per DKE](../media/dke-createtasksjsonfromtemplate.png)

   2. Nell'elenco dei tipi di modello selezionare **.NET Core**.

   ![Creare tasks.jssu file da modello per DKE](../media/dke-tasksjsontemplate.png)

   3. Nella sezione generazione individuare il percorso del file **customerkeystore. csproj** . Se non è presente, aggiungere la riga seguente:

      ```json
      "${workspaceFolder}/src/customer-key-store/customerkeystore.csproj",
      ```

  4. Eseguire di nuovo la Build.

1. Verificare che non vi siano errori rossi nella finestra di output.

   Se sono presenti errori rossi, controllare l'output della console. Verificare che siano stati completati correttamente tutti i passaggi precedenti e che siano presenti le versioni di compilazione corrette.

2. Selezionare **Esegui** \> **debug avvio** per eseguire il debug del processo. Se viene richiesto di selezionare un ambiente, selezionare **.NET Core**.

Il debugger di base di .NET in genere viene avviato in '' https://localhost:5001 `. To view your test key, go to ` https://localhost:5001 ' e aggiunge una barra (/) e il nome della chiave. Ad esempio:

```https
https://localhost:5001/TestKey1
```

Il tasto dovrebbe essere visualizzato in formato JSON.

La configurazione è stata completata. Prima di pubblicare il keystore, in appsettings.jssu, per l'impostazione JwtAudience, assicurarsi che il valore di hostname corrisponda esattamente al nome host del servizio app. Potrebbe essere stata modificata in localhost per risolvere i problemi relativi alla generazione.

### <a name="publish-the-key-store"></a>Pubblicare l'archivio delle chiavi

Per pubblicare l'archivio delle chiavi, è possibile creare un'istanza del servizio app di Azure per ospitare la distribuzione di DKE. Successivamente, verranno pubblicate le chiavi generate in Azure.

**Per creare un'istanza di Azure Web App per ospitare la distribuzione di DKE**

1. Nel browser, accedere al [portale di Microsoft Azure](https://ms.portal.azure.com)e passare a **app Services**  >  **Add**.

1. Selezionare l'abbonamento e il gruppo di risorse e definire i dettagli dell'istanza.

    - Immettere il nome host del computer in cui si desidera installare il servizio DKE. Verificare che sia lo stesso nome di quello definito per l'impostazione JwtAudience nel [**appsettings.jssu**](#tenant-and-key-settings) file. Il valore specificato per il nome è anche WebAppInstanceName.

    - Per la **pubblicazione**, selezionare **codice**e per **stack di Runtime**, selezionare **.NET Core 3,1**.

    Ad esempio:

   ![Aggiungere il servizio app](../media/dke-azure-add-app-service.png)

1. Nella parte inferiore della pagina, selezionare **revisione + crea**e quindi fare clic su **Aggiungi**.

1. Per pubblicare le chiavi generate in Azure, eseguire una delle operazioni seguenti:

    - [Pubblicare tramite ZipDeployUI](#publish-via-zipdeployui)
    - [Pubblicare tramite FTP](#publish-via-ftp)
    - [Pubblicare tramite Visual Studio 2019 o versione successiva](https://docs.microsoft.com/aspnet/core/tutorials/)
    - [Pubblicare in un sistema locale](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&tabs=netcore-cli)

    > [!NOTE]
    > È possibile preferire altri metodi per distribuire le chiavi. Selezionare il metodo più adatto per l'organizzazione.

    > [!TIP]
    > La [pubblicazione tramite Visual Studio](https://docs.microsoft.com/aspnet/core/tutorials/) e un [sistema locale](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&tabs=netcore-cli) è descritta nella [documentazione ASP .NET](https://docs.microsoft.com/aspnet/core/). Se si utilizza uno di questi metodi, aprire le istruzioni in una scheda separata in modo che sia possibile tornare facilmente al termine.

#### <a name="publish-via-zipdeployui"></a>Pubblicare tramite ZipDeployUI

1. Passare a `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`.

    Ad esempio: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI

1. Nella codebase per l'archivio delle chiavi passare alla cartella **Customer-Key-store\src\customer-Key-Store** e verificare che la cartella contenga il file **customerkeystore. csproj** .

1. Esegui: **pubblicazione di DotNet**

     La finestra di output Visualizza la directory in cui è stata distribuita la pubblicazione.

    Ad esempio: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`

1. Inviare tutti i file nella directory di pubblicazione a un file con estensione zip. Quando si crea il file con estensione zip, verificare che tutti i file presenti nella directory si trovino nel livello radice del file. zip.

1. Trascinare e rilasciare il file con estensione zip creato nel sito di ZipDeployUI che è stato aperto. Ad esempio: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI

DKE è distribuito ed è possibile passare alle chiavi di test create. Continuare a [convalidare la distribuzione](#validate-your-deployment) seguente.

#### <a name="publish-via-ftp"></a>Pubblicare tramite FTP

1. Connettersi al servizio app creato [precedentemente](#publish-the-key-store).

    Nel browser passare a: **Azure portal**  >  **App Service**  >  **Deployment Center**  >  **Manual Deployment**  >  **FTP**  >  **Dashboard**FTP Deployment Center di distribuzione manuale di Azure Portal app.

1. Copiare le stringhe di connessione visualizzate in un file locale. Queste stringhe verranno utilizzate per la connessione al servizio Web App e per il caricamento dei file tramite FTP.

    Ad esempio:

   ![Copiare le stringhe di connessione dal dashboard FTP](../media/dke-ftp-dashboard.png)

1. Nella codebase per l'archiviazione delle chiavi passare alla **directory Customer-Key-store\src\customer-Key-Store**

1. Verificare che la directory contenga il file **customerkeystore. csproj** .

1. Esegui: **pubblicazione di DotNet**

    L'output contiene la directory in cui è stata distribuita la pubblicazione.

    Ad esempio: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`

1. Inviare tutti i file nella directory di pubblicazione in un file zip. Quando si crea il file con estensione zip, verificare che tutti i file presenti nella directory si trovino nel livello radice del file. zip.

1. Dal client FTP, utilizzare le informazioni di connessione copiate per la connessione al servizio app. Caricare il file con estensione zip creato nel passaggio precedente alla directory radice dell'app Web.

DKE è distribuito ed è possibile passare alle chiavi di test create. Successivamente, [convalidare la distribuzione](#validate-your-deployment).

### <a name="validate-your-deployment"></a>Convalidare la distribuzione

Dopo aver distribuito DKE utilizzando uno dei metodi descritti in alto, convalidare la distribuzione e le impostazioni dell'archivio chiavi.

Eseguire: 

src\customer-key-store\scripts\key_store_tester.ps1 mykeystoreurl/MyKey

Ad esempio:

key_store_tester.ps1 https://mycustomerkeystore.com/mykey

Assicurarsi che non vengano visualizzati errori nell'output. Quando si è pronti, [registrare il proprio archivio delle chiavi](#register-your-key-store).

## <a name="register-your-key-store"></a>Registrare il proprio archivio delle chiavi

La procedura seguente consente di registrare il proprio archivio chiavi. La registrazione dell'archivio delle chiavi è l'ultimo passaggio della distribuzione di DKE prima di iniziare a creare etichette.

Per registrare l'archivio delle chiavi:

1. Nel browser aprire il portale di [Microsoft Azure](https://ms.portal.azure.com/)e passare a **tutte le** \> **Identity** \> **registrazioni delle app**di identità dei servizi.

2. Selezionare **nuova registrazione**e immettere un nome significativo.

3. Selezionare un tipo di account dalle opzioni visualizzate.

    Se si utilizza Microsoft Azure con un dominio non personalizzato, ad esempio **onmicrosoft.com**, selezionare solo gli **account nella directory dell'organizzazione (solo tenant di Microsoft).**

    Ad esempio:

   ![Nuova registrazione delle app](../media/dke-app-registration.png)

4. Nella parte inferiore della pagina, selezionare **registra** per creare la nuova registrazione app.

5. Nella nuova registrazione dell'app, nel riquadro sinistro, in **Gestisci**selezionare **autenticazione**.

6. Selezionare **Aggiungi una piattaforma**.
 
7. Nel menu a comparsa **Configura piattaforme** selezionare **Web**.
 
8. In **URI di reindirizzamento**, immettere l'URI del servizio di crittografia a chiave doppia. Immettere l'URL del servizio app, inclusi il nome host e il dominio.

    Ad esempio: https://mycustomerkeystoretest.com

    - L'URL immesso deve corrispondere al nome host in cui è distribuito l'archivio delle chiavi.
    - Se si sta verificando localmente con Visual Studio, utilizzare **https://localhost:5001** .
    - In tutti i casi, lo schema deve essere **https**.

    Verificare che il nome dell'host corrisponda esattamente al cognome del servizio app. Potrebbe essere stato modificato per `localhost` risolvere i problemi relativi alla generazione. In **appsettings.js**, questo valore è il nome host impostato per `JwtAudience` .

6. In **concessione implicita**selezionare la casella di controllo **token ID** .

1. Selezionare **Salva** per salvare le modifiche.

7. Nel riquadro sinistro, selezionare **esporre un'API**, quindi accanto a URI ID applicazione selezionare **imposta**.

9. Sempre nella pagina **esporre un'API** , nell' **ambito definito dall'area API** Selezionare **Aggiungi un ambito**. Nel nuovo ambito:

    1. Definire il nome dell'ambito come **user_impersonation**.

    2. Selezionare gli amministratori e gli utenti che possono acconsentire.

    3. Definire i valori rimanenti richiesti.

    4. Selezionare **Aggiungi ambito.**

    Selezionare **Salva** nella parte superiore per salvare le modifiche.

10. Sempre nella pagina **esporre un'API** , nell'area **applicazioni client autorizzate** Selezionare **Aggiungi un'applicazione client**.

    Nella nuova applicazione client:

    1. Definire l'ID client come **d3590ed6-52B3-4102-Aeff-aad2292ab01c**. Questo valore è l'ID client di Microsoft Office e consente a Office di ottenere un token di accesso per l'archivio delle chiavi.

    2. In **ambiti autorizzati**selezionare l'ambito **user_impersonation** .

    3. Selezionare **Aggiungi applicazione**.

    4. Selezionare **Salva** nella parte superiore per salvare le modifiche.

L'archivio delle chiavi di DKE è ora registrato. Continuare con la [creazione di etichette mediante DKE](#create-labels-using-dke).

## <a name="create-labels-using-dke"></a>Creare etichette utilizzando DKE

Nel centro conformità di Microsoft 365, creare una nuova etichetta di riservatezza e applicare la crittografia come si farebbe altrimenti. Selezionare **Use Double Key Encryption** e immettere l'URL dell'endpoint per la chiave.

Ad esempio:

![Selezionare Use Double Key Encryption in the Microsoft 365 Compliance Center](../media/dke-use-dke.png)

Tutte le etichette di DKE aggiunte verranno visualizzate per gli utenti nelle versioni più recenti di Microsoft 365 Apps for Enterprise.

> [!NOTE]
> La possibilità di aggiornare i client con le nuove etichette potrebbe richiedere fino a 24 ore.

### <a name="enable-dke-in-your-client"></a>Abilitare DKE nel client

Abilitare DKE per il client aggiungendo le seguenti chiavi del registro di sistema:

```properties
    [HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIPC\flighting]
    "DoubleKeyProtection"=dword:00000001

    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\flighting]
    "DoubleKeyProtection"=dword:00000001
```
