---
title: Informazioni sulla conservazione per Teams
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
description: Informazioni sui criteri di conservazione applicabili a Microsoft Teams.
ms.openlocfilehash: 3dcc0e3ea94d002f603b44b777d7666a65b4a725
ms.sourcegitcommit: c692bdc186fb29499816e8bb2addcddef34d23d3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/20/2020
ms.locfileid: "46818319"
---
# <a name="learn-about-retention-for-microsoft-teams"></a>Informazioni sulla conservazione per Microsoft Teams

>*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](https://aka.ms/ComplianceSD).*

Questo articolo integra [Informazioni sulla conservazione](retention.md) con informazioni specifiche per Microsoft Teams.

## <a name="how-retention-works-with-microsoft-teams"></a>Funzionamento della conservazione con Microsoft Teams

È possibile usare i criteri di conservazione per conservare i messaggi di chat e canali in Teams. Le chat di Teams vengono archiviate in una cartella nascosta della cassetta postale di ogni utente incluso nella chat e i messaggi dei canali di Teams vengono archiviati in un'analoga cartella nascosta della cassetta postale del gruppo per il team.

È importante sapere che Teams usa un servizio di chat con tecnologia Azure che archivia anche questi dati e che, per impostazione predefinita, questo servizio archivia i dati a tempo indeterminato. Per questo motivo, è consigliabile creare criteri di conservazione che usino i percorsi di Teams per mantenere ed eliminare questi dati di Teams. Questi criteri di conservazione consentono di eliminare definitivamente i dati dalle cassette postali di Exchange e dal servizio di chat con tecnologia Azure sottostante. Per altre informazioni, vedere [Sicurezza e conformità in Microsoft teams](https://go.microsoft.com/fwlink/?linkid=871258) e in particolare la sezione [Architettura di protezione delle informazioni](https://docs.microsoft.com/MicrosoftTeams/security-compliance-overview#information-protection-architecture).

I messaggi di chat e canali di Teams non sono interessati dai criteri di conservazione configurati per le cassette postali di utenti o gruppi. Anche se i messaggi di chat e canali di Teams vengono archiviati in Exchange, questi dati vengono inclusi solo da un criterio di conservazione configurato per le posizioni **Messaggi del canale di Teams** e **Chat di Teams**.

> [!NOTE]
> Se un utente è incluso in un criterio di conservazione attivo che conserva i dati di Teams e si eliminata una cassetta postale di un utente incluso in tale criterio, per conservare i dati di Teams la cassetta postale viene convertita in una [cassetta postale inattiva](inactive-mailboxes-in-office-365.md). Se non è necessario conservare i dati di Teams per l'utente, escludere l'account utente dal criterio di conservazione prima di eliminare la relativa cassetta postale.

Dopo che i criteri di conservazione sono stati configurati per messaggi di chat e canali, un processo timer del servizio Exchange valuterà periodicamente gli elementi nella cartella nascosta in cui vengono archiviati i messaggi di Teams. Il processo timer richiede fino a sette giorni per l'esecuzione. Quando il periodo di conservazione degli elementi scade, questi vengono spostati nella cartella SubstrateHolds, un'altra cartella nascosta presente in ogni cassetta postale utente o di gruppo in cui vengono archiviati gli elementi "eliminati temporaneamente" prima che vengano eliminati definitivamente.

Dopo la configurazione di un criterio di conservazione per i messaggi di chat e canali, i percorsi del contenuto variano in base al fatto che il criterio di conservazione sia impostato per conservare e poi eliminare, conservare solo o eliminare solo.

Se il criterio di conservazione conserva e poi elimina:

![Diagramma del flusso di conservazione per messaggi di chat e canali di Teams](../media/teamsretentionlifecycle.png)

Per i due percorsi nel diagramma:

1. **Se un messaggio della chat o del canale viene modificato o eliminato** dall’utente durante il periodo di conservazione, il messaggio originale viene copiato (se è stato modificato) o spostato (se è stato eliminato) immediatamente nella cartella SubstrateHolds. Il messaggio viene archiviato in questa posizione fino alla scadenza del periodo di conservazione, quindi viene eliminato definitivamente entro 24 ore.

2. **Se il messaggio di una chat o un canale non viene eliminato**, così come per i messaggi correnti dopo essere stati modificati, il messaggio viene spostato nella cartella SubstrateHolds alla scadenza del periodo di conservazione. Questa azione richiede fino a sette giorni dalla data di scadenza. Dopo che il messaggio è stato spostato nella cartella SubstrateHolds, viene eliminato definitivamente entro 24 ore. 

> [!NOTE]
> I messaggi nella cartella SubstrateHolds sono disponibili per la ricerca tramite gli strumenti di eDiscovery. Finché i messaggi non vengono eliminati definitivamente (nella cartella SubstrateHolds), rimangono disponibili per la ricerca tramite gli strumenti di eDiscovery.

Quando il criterio di conservazione è Conserva solo, o Elimina solo, i percorsi del contenuto sono varianti di Conserva ed Elimina.

### <a name="content-paths-for-retain-only-retention-policy"></a>Percorsi di contenuto per il criterio di conservazione Conserva solo

1. **Se un messaggio della chat o del canale viene modificato o eliminato**: una copia del messaggio originale viene immediatamente creata nella cartella SubstrateHolds e conservata in tale posizione fino alla scadenza del periodo di conservazione. Quindi il messaggio viene eliminato definitivamente dalla cartella SubstrateHolds entro 24 ore.

2. **Se l'elemento non viene modificato o eliminato**, così come per i messaggi correnti dopo essere stati modificati durante il periodo di conservazione: non succede niente prima o dopo il periodo di conservazione. L'elemento rimane nella posizione originale.

### <a name="content-paths-for-delete-only-retention-policy"></a>Percorsi di contenuto per il criterio di conservazione Elimina solo

1. **Se il messaggio non viene eliminato** durante il periodo di conservazione: alla fine del periodo di conservazione il messaggio viene spostato nella cartella SubstrateHolds. Questa azione richiede fino a sette giorni dalla data di scadenza. Quindi il messaggio viene eliminato definitivamente dalla cartella SubstrateHolds entro 24 ore.

2. **Se l'elemento viene eliminato dall'utente** durante il periodo, verrà immediatamente spostato nella cartella SubstrateHolds da dove verrà eliminato definitivamente entro 24 ore.


## <a name="skype-for-business-and-teams-interop-chats"></a>Chat di interoperabilità di Skype for Business e Teams.

Quando una chat di Skype for Business viene spostata in Teams, diventa un messaggio in un thread di chat di Teams e viene inserita nella cassetta postale appropriata. I criteri di conservazione di Teams verranno applicati a questi messaggi dal thread di Teams. 

Tuttavia, se la cronologia delle conversazioni è abilitata per Skype for Business e dal lato client di Skype for Business questa cronologia viene salvata in una cassetta postale, i dati della chat non vengono gestiti dai criteri di conservazione di Teams. Per questo contenuto, usare un criterio di conservazione configurato per Skype for Business.

## <a name="meetings-and-external-users"></a>Riunioni e utenti esterni

I messaggi delle riunioni di canale vengono archiviati allo stesso modo dei messaggi di canale, quindi per questi dati selezionare il percorso **Messaggi del canale di Teams** quando si configura il criterio di conservazione.

I messaggi delle riunioni estemporanee vengono archiviati allo stesso modo dei messaggi delle chat di gruppo, quindi per questi dati selezionare il percorso **Chat di Teams** quando si configura il criterio di conservazione.

Quando in una riunione ospitata dall'organizzazione vengono inclusi utenti esterni:

- Se un utente esterno partecipa con un account guest nel tenant dell'organizzazione, l'utente ha una cassetta postale shadow che può essere soggetta ai criteri di conservazione dell'organizzazione per Teams. I messaggi della riunione vengono archiviati sia nella cassetta postale degli utenti che nella cassetta postale shadow. 

- Se un utente esterno partecipa usando un account di un'altra organizzazione di Microsoft 365, i criteri di conservazione non possono eliminare i messaggi per l'utente, perché sono archiviati nella sua cassetta postale in un altro tenant. Per la stessa riunione, tuttavia, i criteri di conservazione configurati possono eliminare i messaggi per gli utenti interni dell'organizzazione.

## <a name="when-a-user-leaves-the-organization"></a>Quando un utente abbandona l’organizzazione 

Se un utente lascia l’organizzazione e il suo account di Microsoft 365 viene eliminato, i suoi messaggi della chat soggetti alla conservazione vengono archiviati in una cassetta postale inattiva. I messaggi di chat restano sottoposti ai criteri di conservazione applicati all’utente prima della disattivazione della sua cassetta postale, e sono disponibili per la ricerca eDiscovery. Per altre informazioni, vedere [Cassette postali inattive in Exchange Online](inactive-mailboxes-in-office-365.md). 

Se l’utente ha archiviato dei file in Teams, vedere la sezione [corrispondente](retention-policies-sharepoint.md#when-a-user-leaves-the-organization) per SharePoint e OneDrive.

## <a name="limitations"></a>Limitazioni

Lavoriamo costantemente all'ottimizzazione della funzionalità di conservazione in Teams. Nel frattempo, di seguito sono riportate alcune limitazioni da tenere presenti quando si usa la conservazione per le chat e i messaggi dei canali di Teams:

- **Teams non è incluso in un criterio a livello di organizzazione**. Se si crea un criterio a livello di organizzazione, i messaggi dei canali di Teams e le chat di Teams non vengono inclusi perché richiedono criteri di conservazione specifici.

- **Teams non supporta la conservazione avanzata**. Quando si crea un criterio di conservazione, se si scelgono le [impostazioni avanzate per identificare il contenuto che soddisfa condizioni specifiche](create-retention-policies.md#advanced-settings-to-identify-content-that-meets-specific-conditions), i percorsi di Teams non sono disponibili. La conservazione in Teams si applica a tutto il contenuto di messaggi di chat e canali quando si selezionano tali posizioni.

- **I messaggi di Teams nei canali privati non vengono inclusi quando si configurano criteri di conservazione per i messaggi dei canali di Teams**. I canali privati non sono al momento supportati dai criteri di conservazione. 

- I **Like e le altre reazioni non vengono conservate per la chat dei Team ed il canale messaggi**. Le reazioni degli altri utenti sotto forma di emoticon non sono supportate dalle politiche di conservazione.

- **Problema di visualizzazione non corretta in Outlook**. Se si creano criteri di conservazione per i percorsi di Skype o Teams, uno di questi criteri viene visualizzato come criterio cartella predefinito quando un utente visualizza le proprietà di una cartella della cassetta postale nel client desktop di Outlook. Si tratta di un problema di visualizzazione non corretta in Outlook e di un [problema noto](https://support.microsoft.com/help/4491013/outlook-client-displays-teams-or-skype-for-business-retention-policies). Quello che dovrebbe essere visualizzato come criterio cartella predefinito è il criterio di conservazione della cassetta postale applicato alla cartella. Il criterio di conservazione di Skype o Teams non viene applicato alla cassetta postale dell'utente.

- **Problemi di configurazione**: 
    - Quando si seleziona **Scegli i team** per il percorso **Messaggi del canale di Teams**, potrebbero essere visualizzati gruppi di Microsoft 365 che non corrispondono anche a team. Non selezionare questi gruppi.
    
    - Quando si seleziona **Scegli utenti** per la posizione **Chat di Teams**, potrebbero essere visualizzati utenti non della cassetta postale e guest. I criteri di conservazione non sono pensati per questi utenti, quindi non selezionarli.

## <a name="configuration-guidance"></a>Linee guida per la configurazione

Se è tutto pronto per configurare la conservazione in Microsoft 365, vedere [Informazioni sui criteri e sulle etichette di conservazione](get-started-with-retention.md).
