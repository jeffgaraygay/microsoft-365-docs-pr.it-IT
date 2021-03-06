---
title: Importare contenuto non Microsoft 365 per l'analisi avanzata di eDiscovery
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- OEC150
- MET150
ms.assetid: 0ee60763-a30b-495b-8543-971c3384a801
description: Come eseguire la procedura per importare il contenuto non archiviato in Microsoft 365 in un BLOB di Azure in modo che possa essere analizzato con AeD
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fbb21f6bc3fdfd2a5251a9ec773a22351db5749e
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817595"
---
# <a name="import-non-microsoft-365-content-for-advanced-ediscovery-classic-analysis"></a>Importare contenuto non Microsoft 365 per l'analisi di Advanced eDiscovery (Classic)

Non tutti i documenti che potrebbe essere necessario analizzare con Advanced eDiscovery vivranno in Microsoft 365. Con la caratteristica di importazione di contenuto non Microsoft 365 in Advanced eDiscovery è possibile caricare documenti che non risiedono in Microsoft 365 (ad eccezione dei file PST) in un caso collegato, BLOB di archiviazione di Azure e analizzarli con Advanced eDiscovery. In questa procedura viene illustrato come portare i documenti non Microsoft 365 in Advanced eDiscovery per l'analisi.
  
> [!NOTE]
> Per usare Advanced eDiscovery è necessario avere Office 365 E3 con il componente aggiuntivo Advanced Compliance o un abbonamento E5 dell'organizzazione. Se non si ha questo piano e si desidera provare Advanced eDiscovery, è possibile [richiedere una valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
> [!NOTE]
> È possibile acquistare un abbonamento aggiuntivo per l'archiviazione dei dati di eDiscovery per il contenuto non Microsoft 365. Questo è disponibile solo per il contenuto che deve essere analizzato con Advanced eDiscovery. Seguire la procedura in [acquistare o modificare un componente aggiuntivo per Microsoft 365 for business](https://docs.microsoft.com/microsoft-365/commerce/buy-or-edit-an-add-on) e acquistare il componente aggiuntivo di archiviazione avanzata di eDiscovery. 
  
## <a name="requirements-to-upload-non-office-365-content"></a>Requisiti per caricare il contenuto non Office 365

Se si utilizza la funzionalità carica non Office 365 come descritto in questa procedura, è necessario disporre di:
  
- Un Office 365 E3 con un componente aggiuntivo di conformità avanzato o un abbonamento E5
    
- Tutti i depositari il cui contenuto non Office 365 verrà caricato devono avere E3 con licenze di componenti aggiuntivi o E5 con Advanced Compliance
    
- Un caso di eDiscovery esistente
    
- Tutti i file per il caricamento raccolti in cartelle in cui è presente una cartella per ogni custode e il nome delle cartelle è in questo formato *alias@domainname* . I *alias@domainname* devono essere utenti di Office 365 alias e Domain. È possibile raccogliere tutte le cartelle di *alias@domainname* in una cartella radice. La cartella radice può contenere solo le cartelle *alias@domainname* , non devono essere presenti file liberi nella cartella radice. 
    
- Un account che sia un Manager di eDiscovery o un amministratore di eDiscovery
    
- [Strumenti di archiviazione di Microsoft Azure](https://aka.ms/downloadazcopy) installati in un computer che ha accesso alla struttura di cartelle di contenuto non di Office 365. 
    
## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a>Caricare il contenuto non Office 365 in Advanced eDiscovery


1. In qualità di Manager di eDiscovery o amministratore di eDiscovery, aprire **eDiscovery**e aprire il caso in cui verranno caricati i dati non di Office 365. Se è necessario creare un caso, vedere [gestire i casi di eDiscovery nel centro sicurezza e &amp; conformità](ediscovery-cases.md) .
    
2. Fare clic su **cambia in Advanced eDiscovery**
    
3. In **tipo di origine** selezionare **dati non Office 365**.
    
4. Fare clic su **Aggiungi contenitore**. Denominare il contenitore e aggiungere una descrizione.
    
5. Selezionare il contenitore appena aggiunto dall'elenco contenitore e copiare l'URL visualizzato nel riquadro dei dettagli del contenitore e quindi chiudere il riquadro.
    
6. Aprire un prompt dei comandi come amministratore e cambiare directory nella cartella in cui è installato AzCopy.
    
7. Creare la riga di comando di AzCopy per caricare i file in questo modo:
    
    AzCopy/Source: " *percorso completo della cartella radice nel computer locale* "/dest: " *URL del contenitore fino a ma non incluso l'?*  "/DestSAS:" *resto dell'URL del contenitore dall'? fino alla fine* "/S. 
    
    Ad esempio, utilizzando questi valori: 
    
  - cartella radice-dati C:\Collected 
    
  - URL del contenitore- https://zoomsabcprodeuss114.blob.core.windows.net/ingestion53d059efe5f74784afb308f66cdebf17?sv=2015-04-05&amp ; SR = c &amp; si = NonOfficeData15% 7C0 &amp; sig = Bk5INP8CUfv1y4CSJiJl3pJt3Ekvu8GS3P8NkOvoQxA% 3D
    
    la sintassi della riga di comando di AzCopy è:
    
     `AzCopy /Source:"C:\CollectedData" /Dest:"https://zoomsabcprodeuss114.blob.core.windows.net/ingestion53d059efe5f74784afb308f66cdebf17" /DestSAS:"?sv=2015-04-05&amp;sr=c&amp;si=NonOfficeData15%7C0&amp;sig=Bk5INP8CUfv1y4CSJiJl3pJt3Ekvu8GS3P8NkOvoQxA%3D" /S`
    
    Per ulteriori informazioni sulla sintassi di Azcopy, vedere [trasferire dati con la Azcopy in Windows](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy) . 
    
    > [!IMPORTANT]
    > Deve essere presente una cartella radice per utente e il nome della cartella deve trovarsi nel formato *alias@domainname* . 
  
8. Dopo aver completato il caricamento delle cartelle, tornare a Advanced eDiscovery. Il contenuto delle cartelle che è stato caricato è ora pronto per essere elaborato in Advanced eDiscovery. Selezionare il contenitore e fare clic sul pulsante elabora. Per ulteriori informazioni sull'elaborazione avanzata di eDiscovery, vedere, [eseguire il modulo di processo e caricare i dati in Advanced eDiscovery](run-the-process-module-and-load-data-in-advanced-ediscovery.md)
    
    > [!IMPORTANT]
    > Dopo che il contenitore è stato elaborato correttamente in Advanced eDiscovery, non sarà più possibile aggiungere nuovo contenuto allo spazio di archiviazione SAS in Azure. Se si raccolgono contenuto aggiuntivo e si desidera aggiungerlo al caso per l'analisi avanzata di eDiscovery, è necessario creare un nuovo contenitore di **dati non Office 365** e ripetere questa procedura. 
  
    > [!NOTE]
    > Se il contenitore non *elabora correttamente a causa di problemi di denominazione delle cartelle* e quindi si corregge i problemi, sarà comunque necessario creare un nuovo contenitore e riconnetterlo e caricarlo nuovamente utilizzando le procedure illustrate in questo articolo.
