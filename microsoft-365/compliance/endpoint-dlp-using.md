---
title: Uso della prevenzione della perdita di dati degli endpoint (anteprima)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
description: Informazioni su come configurare i criteri di prevenzione della perdita dei dati (DLP) per usare le posizioni di Prevenzione della perdita di dati degli endpoint di Microsoft 365.
ms.openlocfilehash: 38300769a4d6d3a4093fe403e79f5b13e71f2c1c
ms.sourcegitcommit: 583fd1ac1f385c58b93bda648907a1bd8e0a1950
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/28/2020
ms.locfileid: "45430244"
---
# <a name="using-endpoint-data-loss-prevention-preview"></a>Uso della prevenzione della perdita di dati degli endpoint (anteprima)

Questo articolo illustra tre scenari in cui si creano e modificano criteri di prevenzione della perdita dei dati che usano dispositivi come posizione.

## <a name="dlp-settings"></a>Impostazioni DLP

Prima di iniziare, è necessario configurare le impostazioni di prevenzione della perdita dei dati da applicare a tutti i criteri DLP per i dispositivi. Vanno configurate se si prevede di creare criteri che impongono:

- restrizioni di uscita dal cloud
- restrizioni per app non consentite

Oppure

- Se si vogliono escludere dal monitoraggio i percorsi di file con troppi disturbi

![Impostazioni DLP](../media/endpoint-dlp-1-using-dlp-settings.png)

### <a name="file-path-exclusions"></a>Esclusioni di percorsi di file

È possibile escludere alcuni percorsi dal monitoraggio DLP, dagli avvisi DLP e dall'applicazione dei criteri DLP nei dispositivi, perché sono troppo disturbati o non contengono file a cui si è interessati. I file presenti in tali posizioni non verranno controllati e i file creati o modificati in tali posizioni non saranno soggetti all'applicazione dei criteri di prevenzione della perdita dei dati. È possibile configurare le esclusioni di percorsi nelle impostazioni DLP.

Per creare esclusioni di percorsi si può usare questa logica:

- Percorso file valido che termina con "\", per indicare solo i file direttamente nella cartella. Ad esempio, C:\Temp\
- Percorso file valido che termina con "\*", per indicare solo i file all'interno di sottocartelle, oltre ai file direttamente nella cartella. Ad esempio, C:\Temp\*
- Percorso file valido che termina senza "\" o "\*", per indicare tutti i file direttamente nella cartella e in tutte le sottocartelle. Ad esempio, C:\Temp
- Percorso con carattere jolly compreso tra "\" su entrambi i lati. Ad esempio, C:\Users\*\Desktop\
- Percorso con carattere jolly compreso tra "\" su entrambi i lati e con "(numero)" per indicare il numero esatto di sottocartelle. Ad esempio, C:\Users\*(1)\Downloads\
- Un percorso con variabili di ambiente di sistema. Ad esempio, %SystemDrive%\Test\*
- Una combinazione di tutti gli esempi precedenti. Ad esempio, %SystemDrive%\Users\*\Documents\*(2)\Sub\

### <a name="service-domains"></a>Domini del servizio

È possibile aggiungere domini a questo elenco, a cui Microsoft Edge Chromium farà riferimento durante l'applicazione della restrizione di accesso relativa al caricamento nel cloud di Endpoint DLP. 

Se la modalità dell'elenco è impostata su **Blocca**, l'utente non potrà caricare elementi sensibili in tali domini. Quando un'azione di caricamento viene bloccata perché un elemento corrisponde a un criterio di prevenzione della perdita dei dati, DLP genera un avviso o blocca il caricamento dell'elemento sensibile.

Se la modalità dell'elenco è impostata su **Consenti**, gli utenti possono caricare gli elementi sensibili ***solo*** in questi domini e l'accesso in caricamento a tutti gli altri domini non è consentito.

### <a name="unallowed-apps"></a>App non consentite

Quando l'impostazione **Accesso da app e browser non consentiti** di un criterio è attivata e gli utenti tentano di usare queste app per accedere a un file protetto, l'attività viene consentita, bloccata oppure bloccata ma gli utenti possono ignorare la restrizione. Tutte le attività sono controllate e disponibili per la revisione in Esplora attività.

### <a name="unallowed-browsers"></a>Browser non consentiti

È possibile aggiungere browser, identificati dai nomi dei processi, a cui verrà impedito di accedere ai file che corrispondono alle condizioni di un criterio DLP applicato in cui la restrizione relativa al caricamento nei servizi cloud è impostata su Blocca o Blocca con override. Quando a questi browser viene impedito di accedere a un file, gli utenti finali vedranno una notifica di tipo avviso popup che chiede di aprire il file con Microsoft Edge Chromium.

## <a name="tying-dlp-settings-together"></a>Unione di impostazioni DLP

Con Endpoint DLP e il Web browser Microsoft Edge Chromium, è possibile limitare la condivisione involontaria di elementi sensibili con app e i servizi cloud non consentiti. Microsoft Edge Chromium riconosce quando un elemento è limitato da un criterio di Endpoint DLP e impone restrizioni di accesso.

Quando si usano il browser Microsoft Edge Chromium e la posizione Endpoint DLP in un criterio di prevenzione della perdita dei dati configurato correttamente, i browser non consentiti definiti in queste impostazioni non potranno accedere agli elementi sensibili che corrispondono ai controlli del criterio DLP. Gli utenti verranno reindirizzati all'uso di Microsoft Edge Chromium, che comprende le restrizioni imposte dalla prevenzione della perdita dei dati e può bloccare o limitare attività quando le condizioni indicate nel criterio DLP sono soddisfatte.

Per usare questa restrizione sarà necessario configurare tre elementi importanti:

1. Specificare le posizioni, ovvero servizi, domini o indirizzi IP, con cui si vuole impedire la condivisione di elementi sensibili
2. Aggiungere i browser ai quali non è consentito accedere a determinati elementi sensibili in caso di corrispondenza con un criterio DLP
3. Configurare criteri DLP per definire i tipi di elementi sensibili per cui limitare il caricamento in queste posizioni, attivando **Carica nei servizi cloud** e **Accedi dai browser non consentiti**.

È possibile continuare ad aggiungere nuovi servizi, app e criteri per estendere e aumentare le restrizioni in modo da soddisfare le esigenze dell'azienda e proteggere i dati sensibili. 

Questa configurazione contribuirà a garantire la sicurezza dei dati, evitando anche restrizioni inutili che limitano la capacità degli utenti di accedere a elementi non riservati e condividerli.

## <a name="endpoint-dlp-policy-scenarios"></a>Scenari dei criteri di Endpoint DLP

Per acquisire familiarità con le funzionalità di Endpoint DLP e su come vengono visualizzate nei criteri DLP, sono stati predisposti alcuni scenari da seguire. Tutto il contenuto di Endpoint DLP verrà inserito nel set di contenuti principale sulla prevenzione della perdita dei dati quando Endpoint DLP diventerà disponibile a livello generale.

> [!IMPORTANT]
> Questi scenari di Endpoint DLP non sono le procedure ufficiali per la creazione e l'ottimizzazione di criteri DLP. Vedere gli argomenti seguenti quando è necessario usare i criteri di prevenzione della perdita dei dati in situazioni generiche:
>- [Panoramica sulla prevenzione della perdita dei dati](data-loss-prevention-policies.md)
>- [Cominciare con il criterio di prevenzione della perdita dei dati predefinito](get-started-with-the-default-dlp-policy.md)
>- [Creare un criterio di prevenzione della perdita dei dati da un modello](create-a-dlp-policy-from-a-template.md)
>- [Creare, testare e ottimizzare un criterio di prevenzione della perdita dei dati](create-test-tune-dlp-policy.md)

### <a name="scenario-1-create-a-policy-from-a-template-audit-only"></a>Scenario 1: Creare un criterio da un modello, solo controllo

Per questi scenari è necessario aver già eseguito l'onboarding di dispositivi, che inviano report a Esplora attività. Se non si è ancora eseguito l'onboarding di dispositivi, vedere [Introduzione alla prevenzione della perdita di dati degli endpoint (anteprima)](endpoint-dlp-getting-started.md).

1. Aprire la [pagina Prevenzione della perdita dei dati](https://compliance.microsoft.com/datalossprevention?viewid=policies).
2. Scegliere **Crea criterio (anteprima)**.
3. Per questo scenario, scegliere **Privacy** e poi **Informazioni personali (USA)**, quindi sceg **Avanti**.
4. Impostare il campo **Stato** in posizione di disattivato per tutte le posizioni tranne **Dispositivi**. Scegliere **Avanti**.
5. Accettare la selezione **Rivedere e personalizzare le impostazioni predefinite dal modello** e scegliere **Avanti**.
6. Accettare i valori predefiniti per le **Azioni di protezione** e scegliere **Avanti**.
7. Selezionare **Controlla o limita le attività nei dispositivi Windows** e uscire dalle azioni impostate su **Solo controllo**. Scegliere **Avanti**.
8. Accettare il valore predefinito **Vorrei prima testarli** e scegliere **Mostra i suggerimenti per i criteri in modalità di test**. Scegliere **Avanti**.
9. Rivedere le impostazioni e scegliere **Invia**.
10. Il nuovo criterio DLP verrà visualizzato nell'elenco dei criteri.
11. Controllare i dati degli endpoint monitorati in Esplora attività. Impostare il filtro della posizione per i dispositivi e aggiungere il criterio, quindi filtrare in base al nome del criterio per vederne l'impatto. Se necessario, vedere [Introduzione a Esplora attività](data-classification-activity-explorer.md).
12. Provare a condividere con un utente esterno all'organizzazione un test con contenuto che attiverà la condizione Informazioni personali (USA). Questo dovrebbe attivare il criterio.
13. Controllare l'evento in Esplora attività.

### <a name="scenario-2-modify-the-existing-policy-set-an-alert"></a>Scenario 2: Modificare il criterio esistente, impostare un avviso

1. Aprire la [pagina Prevenzione della perdita dei dati](https://compliance.microsoft.com/datalossprevention?viewid=policies).
2. Scegliere il criterio **Informazioni personali (USA)** creato nello scenario 1.
3. Scegliere **Modifica criterio (anteprima)**.
4. Passare alla pagina **Regole avanzate di prevenzione della perdita dei dati** e modificare il **Rilevato un volume ridotto di contenuti con informazioni personali (Stati Uniti)**
5. Scorrere verso il basso fino alla sezione **Report sugli eventi imprevisti** e impostare **Invia un avviso agli amministratori quando viene soddisfatta una regola** su **Attivato**. Gli avvisi di posta elettronica verranno inviati automaticamente all'amministratore e a tutti gli altri utenti aggiunti all'elenco dei destinatari. 
![attivare il report sugli eventi imprevisti](../media/endpoint-dlp-2-using-dlp-incident-reports.png)
6. Ai fini del presente scenario, scegliere **Invia un avviso ogni volta che un'attività corrisponde alla regola**.
7. Scegliere **Salva**.
8. Conservare tutte le impostazioni precedenti scegliendo **Avanti** e quindi **Invia** per applicare le modifiche al criterio.
9. Provare a condividere con un utente esterno all'organizzazione un test con contenuto che attiverà la condizione Informazioni personali (USA). Questo dovrebbe attivare il criterio.
10. Controllare l'evento in Esplora attività.

### <a name="scenario-3-modify-the-existing-policy-block-the-action-with-allow-override"></a>Scenario 3: Modificare il criterio esistente, bloccare l'azione con Consenti override

1. Aprire la [pagina Prevenzione della perdita dei dati](https://compliance.microsoft.com/datalossprevention?viewid=policies).
2. Scegliere il criterio **Informazioni personali (USA)** creato nello scenario 1.
3. Scegliere **Modifica criterio (anteprima)**.
4. Passare alla pagina **Regole avanzate di prevenzione della perdita dei dati** e modificare il **Rilevato un volume ridotto di contenuti con informazioni personali (Stati Uniti)**
5. Scorrere verso il basso fino alla sezione **Controlla o limita le attività nei dispositivi Windows** e per ogni attività impostare l'azione corrispondente su **Blocca con override**.
![impostare l'azione Blocca con override](../media/endpoint-dlp-6-using-dlp-set-blocked-with-override.png)
6. Scegliere **Salva**.
7. Ripetere i passaggi da 4 a 7 per **Rilevato un volume elevato di contenuti con informazioni personali (Stati Uniti)**.
8. Conservare tutte le impostazioni precedenti scegliendo **Avanti** e quindi **Invia** per applicare le modifiche al criterio.
9. Provare a condividere con un utente esterno all'organizzazione un test con contenuto che attiverà la condizione Informazioni personali (USA). Questo dovrebbe attivare il criterio.

Nel dispositivo client sarà visualizzato un popup come questo:

![notifica di override client bloccato di Endpoint DLP](../media/endpoint-dlp-3-using-dlp-client-blocked-override-notification.png)

10. Controllare l'evento in Esplora attività.

## <a name="see-also"></a>Vedere anche

- [Informazioni sulla prevenzione della perdita di dati degli endpoint (anteprima)](endpoint-dlp-learn-about.md)
- [Introduzione alla prevenzione della perdita di dati degli endpoint (anteprima)](endpoint-dlp-getting-started.md)
- [Panoramica sulla prevenzione della perdita dei dati](data-loss-prevention-policies.md)
- [Creare, testare e ottimizzare un criterio di prevenzione della perdita dei dati](create-test-tune-dlp-policy.md)
- [Introduzione a Esplora attività](data-classification-activity-explorer.md)
- [Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP)](https://docs.microsoft.com/windows/security/threat-protection/)
- [Strumenti e metodi di onboarding per i dispositivi Windows 10](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [Abbonamento a Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [Dispositivi aggiunti ad Azure Active Directory (AAD)](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join)
- [Scaricare il nuovo Microsoft Edge basato su Chromium](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
- [Cominciare con il criterio di prevenzione della perdita dei dati predefinito](get-started-with-the-default-dlp-policy.md)
- [Creare un criterio di prevenzione della perdita dei dati da un modello](create-a-dlp-policy-from-a-template.md)