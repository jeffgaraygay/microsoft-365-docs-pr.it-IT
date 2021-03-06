---
title: Notifica di violazione secondo il GDPR
description: Informazioni su come Microsoft protegge da una violazione dei dati personali e su come gestisce un'eventuale violazione e lo comunica agli utenti interessati.
keywords: Office 365, Microsoft 365, Microsoft 365 Education, Documentazione Microsoft 365, GDPR
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
titleSuffix: Microsoft GDPR
ms.openlocfilehash: ae69a8330f5daec275247e718f7eb66a5f0f8bf9
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633441"
---
# <a name="breach-notification-under-the-gdpr"></a>Notifica di violazione secondo il GDPR

In quanto responsabile del trattamento dei dati, Office 365 consente ai clienti di soddisfare i requisiti relativi alla notifica di violazioni del GDPR come titolari del trattamento dei dati. A tale scopo, Microsoft si impegna a:

- Garantire ai clienti la possibilità di specificare un apposito contatto privacy al quale sarà notificata un'eventuale violazione. I clienti potranno specificare questo contatto in Azure Active Directory (AAD).
- Informare i clienti riguardo alla violazione dei dati personali entro 72 ore dall'avvenuta violazione. Verrà inviata una notifica tramite posta elettronica al contatto specificato dal cliente.
- La notifica iniziale includerà almeno una descrizione del tipo di violazione, una stima approssimativa dell'impatto avuto sull'utente e i passaggi per la prevenzione (se applicabili). Se l'analisi non è completa al momento dell'invio della notifica iniziale, Microsoft indicherà nella suddetta notifica i passaggi successivi e la tempistica per le comunicazioni successive.

Microsoft riconosce che i titolari del trattamento dei dati sono responsabili della valutazione dei rischi e sono tenuti a determinare se una violazione richieda una notifica del DPA del cliente; inoltre, con la notifica ai clienti verranno fornite le informazioni necessarie per eseguire tale valutazione. Microsoft notificherà ai clienti eventuali violazioni dei dati personali, fatta eccezione per i casi in cui i dati personali siano indecifrabili (ad esempio, in caso di dati con crittografia avanzata nei quali l'integrità delle chiavi è confermata).

## <a name="office-365-investments-in-data-security"></a>Investimenti di Office 365 per la sicurezza dei dati

Oltre a notificare tempestivamente le violazioni, Office 365 investe molto in sistemi, processi e personale per ridurre la probabilità di violazioni di dati personali e per rilevare velocemente le eventuali violazioni e ridurne le conseguenze.

Ecco una descrizione di alcuni degli investimenti in quest'area:

- **Sistemi di controllo di accesso.** Office 365 gestisce i criteri di "accesso zero standing", il che significa che i tecnici non hanno accesso al servizio a meno che questo non venga concesso in risposta a un incidente specifico che richiede l'elevazione dei privilegi di accesso. Ogni volta che viene concesso l'accesso, questa procedura viene eseguita seguendo il principio dei privilegi minimi: l'autorizzazione concessa per una richiesta specifica consente di eseguire solo un set minimo di azioni necessarie per soddisfare tale richiesta. A tale scopo, Office 365 mantiene una rigorosa separazione tra i "ruoli di elevazione", autorizzando ogni ruolo ad eseguire soltanto alcune azioni predefinite. Il ruolo di "Accesso ai dati del cliente" è diverso dagli altri ruoli che vengono utilizzati generalmente per gestire il servizio e viene analizzato scrupolosamente prima dell'approvazione. Nel complesso, questi investimenti nel controllo di accesso riducono notevolmente la probabilità che un tecnico di Office 365 acceda in maniera inopportuna ai dati dei clienti.

- **Automazione e sistemi per il monitoraggio della sicurezza:** Office 365 dispone di solidi sistemi di monitoraggio della sicurezza in tempo reale. Tra l'altro, questi sistemi generano avvisi per i tentativi illeciti di accesso ai dati dei clienti o di trasferimento di dati da un servizio. Relativamente ai punti riguardanti il controllo di accesso indicati in precedenza, i sistemi di monitoraggio della sicurezza registrano dettagliatamente le richieste di elevazione dei privilegi di sicurezza e le azioni eseguite per una richiesta di elevazione concessa. Office 365 gestisce inoltre gli investimenti di risoluzione automatica che vengono applicati automaticamente per attenuare le minacce in risposta ai problemi rilevati e dispone di team specifici per rispondere agli avvisi che non possono essere risolti automaticamente. Per convalidare i sistemi di monitoraggio della sicurezza, Office 365 esegue regolarmente gli esercizi dei red team, nei quali un team interno simula un attacco contro l'ambiente attivo. Questi esercizi sono utili per migliorare il monitoraggio della sicurezza e le capacità di intervento.

- **Interventi e personale:** in aggiunta all'automazione descritta in precedenza, Office 365 gestisce gli interventi e i team responsabili sia della formazione dell'organizzazione più grande riguardante la privacy e la gestione degli interventi relativi agli incidenti, sia dell'esecuzione di questi processi durante una violazione. Ad esempio, una dettagliata procedura operativa standard (SOP) di una violazione della privacy viene gestita e condivisa con i team di tutta l'organizzazione. Questa SOP descrive in dettaglio i ruoli e le responsabilità dei singoli team interni a Office 365 e dei team di intervento in caso di incidenti di sicurezza centralizzata. Ciò consente di determinare quali team devono migliorare il comportamento di sicurezza (eseguendo valutazioni sulla sicurezza, integrando con sistemi centrali di monitoraggio della sicurezza e altre procedure migliori) e come dovranno comportarsi i team in caso di un'effettiva violazione (escalation rapida di intervento in caso di incidenti, gestire e fornire le specifiche origini dati che verranno usate per velocizzare il processo di intervento). Inoltre i team ricevono una formazione regolare per poter classificare i dati ed eseguire correttamente le procedure di gestione e archiviazione dei dati personali.

In poche parole, Office 365 investe in maniera cospicua per ridurre la probabilità e le conseguenze della violazione dei dati personali sui clienti. Se si verifica una violazione dei dati personali, Microsoft si impegna a inviare il prima possibile una notifica ai clienti una volta che la violazione sarà stata confermata.

## <a name="what-to-expect-in-the-event-of-breach"></a>Cosa succede in caso di effettiva violazione

Nella sezione precedente sono descritti gli investimenti che Office 365 fa per ridurre la probabilità di violazione dei dati. Nell'eventualità improbabile che si verifichino violazioni, i clienti devono aspettarsi delle esperienze corrispondenti a quanto segue:

- Un ciclo di vita di intervento in caso di incidenti coerente all'interno di Office 365. Come illustrato in precedenza, Office 365 gestisce SOP di intervento in caso di incidenti dettagliate, descrivendo come i team dovrebbero prepararsi ad affrontare le violazioni e come dovrebbero agire qualora queste si verifichino. Ciò garantisce che le protezioni e i processi vengano applicati in tutto il servizio.

- Criteri consistenti per le notifiche ai clienti. I criteri di notifica si focalizzano su riservatezza, integrità e disponibilità dei dati dei clienti. Office 365 invierà una notifica direttamente ai clienti se la riservatezza o l'integrità dei dati dovessero venire compromesse. Microsoft invierà quindi una notifica ai clienti in caso di un eventuale accesso non autorizzato o una perdita o una distruzione non appropriata dei loro dati. Office 365 comunicherà inoltre i problemi relativi alla disponibilità dei dati, nonostante questa procedura sia generalmente effettuata tramite il dashboard sull'integrità dei servizi.

- Dettagli di notifica coerenti. Quando Office 365 comunica una violazione dei dati, i clienti ricevono dettagli specifici. I dettagli minimi che vengono forniti sono i seguenti:

    - Data e orario della violazione e del riconoscimento della violazione
    - Il numero approssimativo di utenti interessati
    - Il tipo di dati utente violati
    - Le azioni necessarie per attenuare la violazione, sia da parte del responsabile sia da parte del titolare del trattamento dei dati

I clienti devono tenere presente che Office 365, in quanto responsabile del trattamento dei dati, non determinerà il rischio di violazione dei dati. Nel caso in cui venisse rilevata una violazione dei dati personali, Microsoft invierà una notifica ai clienti e fornirà i dettagli necessari per identificare in modo accurato il rischio per gli utenti interessati e decidere se è necessario denunciare la violazione agli organismi di certificazione. A tale scopo, i titolari del trattamento dei dati devono determinare i dettagli seguenti:

- Gravità della violazione (ovvero la determinazione dei rischi)
- Se comunicare la violazione agli utenti finali
- Se comunicare la violazione alle autorità competenti (DPA)
- Le procedure specifiche che il titolare del trattamento dei dati dovrà intraprendere per attenuare le conseguenze della violazione

## <a name="contacting-microsoft"></a>Contattare Microsoft

In alcuni casi, un cliente potrebbe individuare una violazione e volerla segnalare a Microsoft. Il protocollo corrente prevede che i clienti si rivolgano al Supporto tecnico Microsoft, che li metterà in contatto con il team tecnico che fornirà loro ulteriori informazioni. In questo caso, i team tecnici Microsoft sono tenuti a fornire ai clienti le informazioni necessarie tramite il contatto di supporto in maniera tempestiva.

## <a name="call-to-action-for-customers"></a>Invito all'azione per i clienti

Come accennato in precedenza, Office 365 è tenuto comunicare una violazione ai clienti entro 72 ore dal riconoscimento della stessa. L'amministratore tenant del cliente riceverà una notifica. In aggiunta, Office 365 consiglia di designare un alias di Contatto privacy globale nel portale di Azure Active Directory (AAD). In caso di violazione dei dati personali, questo alias potrebbe ricevere una notifica tramite posta elettronica oltre a quella inviata agli amministratori.

Il contatto privacy del cliente può essere un singolo utente all'interno dell'organizzazione, una lista di distribuzione (DL) o un utente completamente all'esterno dell'organizzazione. Office 365 richiede ai clienti solo di fornire un indirizzo di posta elettronica per questo contatto da specificare nel portale di AAD, sotto il campo "Contatto privacy globale". Seppur diverso, questo campo è collegato al campo "Contatto tecnico" esistente in AAD. Se i clienti decidono di specificare una lista di distribuzione per tale contatto, è necessario che sia configurata per la ricezione dei messaggi da mittenti esterni.

Riassumendo, Office 365 chiede ai clienti di eseguire le operazioni seguenti per usufruire dei vantaggi dei nostri processi di notifica di violazione:

- Scegliere un contatto al quale inviare una notifica tramite posta elettronica in caso di violazione dei dati personali. Il contatto dovrebbe essere a conoscenza dei requisiti dei titolari del trattamento dei dati in base al GDPR e dovrebbe essere pronto a interagire con il DPO dell'organizzazione ed eventualmente con il DPA subito dopo la ricezione della notifica. Anche gli amministratori tenant riceveranno le notifiche relative alle violazioni e anche loro dovrebbero essere a conoscenza dei requisiti per i titolari del trattamento dei dati definiti dal GDPR.
- Immettere l'indirizzo di posta elettronica del contatto privacy nel portale di AAD. Se non viene inserita alcuna informazione riguardante il Contatto privacy globale, Microsoft invierà una notifica solo all'amministratore tenant.
