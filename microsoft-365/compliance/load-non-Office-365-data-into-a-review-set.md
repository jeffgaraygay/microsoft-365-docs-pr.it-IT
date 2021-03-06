---
title: Caricare dati non Microsoft 365 in un set di Revisione
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Informazioni su come importare i dati non Microsoft 365 in un set di revisione per l'analisi in un caso di eDiscovery avanzato.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f9b506edc55da1916ae908eaa7ca619ba7300f87
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2020
ms.locfileid: "44815463"
---
# <a name="load-non-microsoft-365-data-into-a-review-set"></a>Caricare dati non Microsoft 365 in un set di Revisione

Non tutti i documenti che devono essere analizzati in Advanced eDiscovery si trovano in Microsoft 365. Con la caratteristica di importazione di dati non Microsoft 365 in Advanced eDiscovery, è possibile caricare i documenti che non sono presenti in Microsoft 365 in un set di revisione. In questo articolo viene illustrato come portare i documenti non Microsoft 365 in Advanced eDiscovery per l'analisi.

## <a name="requirements-to-upload-non-office-365-content"></a>Requisiti per caricare il contenuto non Office 365

Se si utilizza la funzionalità carica non Microsoft 365 descritta in questo articolo, è necessario disporre di quanto segue:

- A tutti i depositari ai quali si desidera associare il contenuto non Microsoft 365 deve essere assegnata la licenza appropriata. Per ulteriori informazioni, vedere [Introduzione a Advanced eDiscovery](get-started-with-advanced-ediscovery.md#step-1-verify-and-assign-appropriate-licenses).

- Un caso avanzato di eDiscovery esistente.

- I depositari devono essere aggiunti al caso prima di poter caricare e associare ai dati non Microsoft 365.

- I dati non Microsoft 365 devono essere un tipo di file supportato da Advanced eDiscovery. Per ulteriori informazioni, vedere [tipi di file supportati in Advanced eDiscovery](supported-filetypes-ediscovery20.md).

- Tutti i file caricati in un set di revisione devono trovarsi in cartelle, in cui ogni cartella è associata a un determinato custode. I nomi di queste cartelle devono utilizzare il formato di denominazione seguente: *alias@domainname*. Il alias@domainname deve essere l'alias e il dominio Microsoft 365 dell'utente. È possibile raccogliere tutte le cartelle di alias@domainname in una cartella radice. La cartella radice può contenere solo le cartelle alias@domainname. I file allentati nella cartella radice non sono supportati.

   La struttura di cartelle per i dati non Microsoft 365 che si desidera caricare sarebbe simile all'esempio seguente:

   - c:\nonO365\abraham.mcmahon@contoso.com
   - c:\nonO365\jewell.gordon@contoso.com
   - c:\nonO365\staci.gonzalez@contoso.com

   Dove abraham.mcmahon@contoso.com, jewell.gordon@contoso.com e staci.gonzalez@contoso.com sono gli indirizzi SMTP dei depositari nel caso.

   ![Struttura di cartelle di caricamento dei dati non Microsoft 365](../media/3f2dde84-294e-48ea-b44b-7437bd25284c.png)

- Un account assegnato al gruppo di ruoli eDiscovery Manager (e aggiunto come amministratore di eDiscovery).

- Lo strumento AzCopy v 8.1 è installato in un computer che ha accesso alla struttura di cartelle di contenuto non Microsoft 365. Per installare AzCopy, vedere [Transfer Data with the AzCopy v 8.1 in Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy). Assicurarsi di installare AzCopy nel percorso predefinito, che è **% ProgramFiles (x86)% \ Microsoft SDKs\Azure\AzCopy**. È necessario utilizzare AzCopy v 8.1. Le altre versioni di AzCopy potrebbero non funzionare quando si caricano dati non Microsoft 365 in Advanced eDiscovery.


## <a name="upload-non-microsoft-365-content-into-advanced-ediscovery"></a>Caricare contenuto non Microsoft 365 in Advanced eDiscovery

1. In qualità di Manager di eDiscovery o amministratore di eDiscovery, aprire Advanced eDiscovery e passare al caso in cui verranno caricati i dati non Microsoft 365.  

2. Fare clic su **Revisione set**e quindi selezionare il set di revisione in cui caricare i dati non Microsoft 365.  Se non si dispone di un set di recensioni, è possibile crearne uno. 
 
3. Nel set di verifica fare clic su **Gestisci Revisione set**e quindi su **Visualizza caricamenti** nel riquadro **dati non Microsoft 365** .

4. Fare clic su **Carica file** per avviare l'importazione guidata dati.

   ![Caricare file](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

   Il primo passaggio della procedura guidata consente di preparare una posizione di archiviazione di Azure protetta fornita da Microsoft per il caricamento dei file.  Al termine della preparazione, il pulsante **Avanti: carica file** diventa attivo.

   ![Importazione non Microsoft 365: preparazione](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
5. Fare clic su **Avanti: carica file**.

6. Nella pagina **Carica file** eseguire le operazioni seguenti:

   ![Importazione non Microsoft 365: caricamento di file](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

   a. Nella casella **percorso della posizione dei file** verificare o digitare il percorso della cartella principale in cui sono stati archiviati i dati non Microsoft 365 che si desidera caricare. Ad esempio, per il percorso dei file di esempio visualizzati nella **sezione prima di iniziare**, è necessario digitare **%USERPROFILE\Downloads\nonO365**. Se si specifica la posizione corretta, il comando AzCopy visualizzato nella casella sotto il percorso viene aggiornato correttamente.

   b. Fare clic su **copia negli Appunti** per copiare il comando visualizzato nella casella.

7. Avviare un prompt dei comandi di Windows, incollare il comando copiato nel passaggio precedente e quindi premere **invio** per avviare il comando AzCopy.  Dopo aver avviato il comando, i file non Microsoft 365 verranno caricati nel percorso di archiviazione di Azure preparato nel passaggio 4.

   ![Importazione non Microsoft 365: AzCopy](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

   > [!NOTE]
   > Come indicato in precedenza, è necessario utilizzare AzCopy v 8.1 per utilizzare correttamente il comando fornito nella pagina **Carica file** . Se il comando AzCopy fornito ha esito negativo, vedere [risolvere i problemi relativi a AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).

8. Tornare al centro sicurezza & conformità e fare clic su **Avanti: elabora file** nella procedura guidata.  In questo modo viene avviata l'elaborazione, l'estrazione del testo e l'indicizzazione dei file non Microsoft 365 caricati nel percorso di archiviazione di Azure.  

9. Controllare lo stato di avanzamento dell'elaborazione dei file nella pagina dei **file di processo** o nella scheda **processi** visualizzando un processo denominato **aggiunta di dati non Microsoft 365 a un set di revisione**.  Al termine del processo, i nuovi file saranno disponibili nel set di revisione.

   ![Importazione non Microsoft 365: elaborare i file](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

10. Al termine dell'elaborazione, è possibile chiudere la procedura guidata.
