---
title: Informazioni sulla conservazione per Exchange
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Informazioni sul funzionamento della conservazione per Exchange.
ms.openlocfilehash: e1860b9ff9c521a5a6a61c58d822a2a893570e99
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2020
ms.locfileid: "45127443"
---
# <a name="learn-about-retention-for-exchange"></a>Informazioni sulla conservazione per Exchange

Questo articolo integra [Informazioni sulla conservazione](retention.md) con informazioni specifiche per Exchange.

## <a name="how-retention-works-for-exchange"></a>Funzionamento della conservazione per Exchange

Le cassette postali e le cartella pubbliche utilizzano la cartella [Elementi ripristinabili](https://docs.microsoft.com/exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder) per conservare gli elementi. Solo gli utenti a cui sono state assegnate autorizzazioni di eDiscovery possono visualizzare il contenuto di una cartella Elementi ripristinabili di un altro utente.
  
Quando un utente elimina un messaggio da una cartella (fatta eccezione per la cartella Posta eliminata), per impostazione predefinita il messaggio viene trasferito nella cartella Posta eliminata. Quando un utente elimina un elemento dalla cartella Posta eliminata, il messaggio viene spostato nella cartella Elementi ripristinabili. Tuttavia, un utente può eliminare temporaneamente un elemento (MAIUSC+CANC) di qualsiasi cartella. Con questa operazione la cartella Posta eliminata viene ignorata e l'elemento viene inserito direttamente nella cartella Elementi ripristinabili.
  
Quando si applicano le impostazioni di conservazione ai dati di Exchange, un processo timer valuta periodicamente gli elementi nella cartella Elementi ripristinabili. Se un elemento non corrisponde alle regole specificate in almeno un criterio o una etichetta di conservazione, viene eliminato definitivamente dalla cartella Elementi ripristinabili.

L’esecuzione del processo timer può richiedere fino a 7 giorni, e il percorso di Exchange deve contenere almeno 10 MB.
  
Quando un utente prova a modificare le proprietà di un elemento della cassetta postale, ad esempio, l'oggetto, il corpo, gli allegati, i mittenti, i destinatari o la data di invio o di ricezione di un messaggio, una copia dell'elemento originale viene salvata nella cartella Elementi ripristinabili prima che la modifica diventi effettiva. Questo si verifica per ogni modifica successiva. Alla fine del periodo di conservazione, le copie nella cartella Elementi ripristinabili vengono eliminate definitivamente.

Dopo che le impostazioni di conservazione vengono assegnate ai contenuti di Exchange, i percorsi del contenuto variano in base al fatto che le impostazioni di conservazione siano Conserva ed elimina, Conserva solo o Elimina solo.

Se l'impostazione di conservazione è Conserva ed elimina:

![Diagramma del flusso di conservazione nella posta elettronica e nelle cartelle pubbliche](../media/88f174cc-bbf4-4305-93d7-0515f496c8f9.png)

1. **Se l'elemento viene modificato o eliminato definitivamente** dall'utente, con MAIUSC+CANC o eliminandolo da Posta eliminata, durante il periodo di conservazione: l'elemento viene spostato o copiato, in caso di modifica, nella cartella Elementi ripristinabili. Lì, a intervalli regolari viene eseguito un processo timer che identifica i messaggi il cui periodo di conservazione è scaduto. Questi elementi vengono eliminati definitivamente entro 14 giorni dalla data di fine del periodo di conservazione. 14 giorni è l'impostazione predefinita, ma può essere configurato un valore fino a 30 giorni.

2. **Se l'elemento non viene modificato o eliminato** durante il periodo di conservazione: lo stesso processo viene eseguito periodicamente in tutte le cartelle della cassetta postale e identifica i messaggi il cui periodo di conservazione è scaduto. Questi elementi vengono eliminati definitivamente entro 14 giorni dalla data di fine del periodo di conservazione. 14 giorni è l'impostazione predefinita, ma può essere configurato un valore fino a 30 giorni. 

Quando l'impostazione di conservazione è Conserva solo o Elimina solo, i percorsi del contenuto sono varianti di Conserva ed elimina:

### <a name="content-paths-for-retain-only-retention-settings"></a>Percorsi di contenuto per l'impostazione di conservazione Conserva solo

1. **Se l'elemento viene modificato o eliminato** durante il periodo di conservazione: una copia dell'elemento originale viene creata nella cartella Elementi ripristinabili e conservata fino al termine del periodo di conservazione, quindi la copia nella cartella Elementi ripristinabili viene eliminata definitivamente entro 14 giorni dalla scadenza dell'elemento. 

2. **Se l’elemento non viene modificato o eliminato** durante il periodo di conservazione: non succede niente prima o dopo il periodo di conservazione. L’elemento rimane nella posizione originale.

### <a name="content-paths-for-delete-only-retention-settings"></a>Percorsi di contenuto per l'impostazione di conservazione Elimina solo

1. **Se l’elemento non viene eliminato** durante il periodo configurato: alla fine del periodo configurato nel criterio di conservazione, l’elemento viene spostato nella cartella Elementi ripristinabili. 

2. **Se l'elemento viene eliminato** durante il periodo configurato: l'elemento viene immediatamente spostato nella cartella Elementi ripristinabili. Se un utente elimina l’elemento da questa posizione o svuota la cartella Elementi ripristinabili, l’elemento viene eliminato definitivamente. In caso contrario, l'elemento viene eliminato definitivamente dopo un periodo di 14 giorni nella cartella Elementi ripristinabili. 

## <a name="when-a-user-leaves-the-organization"></a>Quando un utente abbandona l’organizzazione 

Se un utente abbandona l’organizzazione e la relativa cassetta postale è inclusa nei criteri di conservazione, quest’ultima diventerà inattiva quando viene eliminato l'account di Microsoft 365 dell'utente. I contenuti di una cassetta postale inattiva sono comunque soggetti ai criteri di conservazione applicati alla cassetta postale prima della disattivazione e sono disponibili per la ricerca eDiscovery. Per altre informazioni, vedere [Cassette postali inattive in Exchange Online](inactive-mailboxes-in-office-365.md).

## <a name="configuration-guidance"></a>Linee guida per la configurazione

Se è tutto pronto per configurare la conservazione in Microsoft 365, vedere [Informazioni sui criteri e sulle etichette di conservazione](get-started-with-retention.md).
