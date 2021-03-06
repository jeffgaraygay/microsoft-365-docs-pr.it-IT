---
title: Suggerimenti relativi alle prestazioni di rete nell'interfaccia di amministrazione di Microsoft 365 (anteprima)
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 04/21/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Panoramica della connettività di rete nell'interfaccia di amministrazione di Microsoft 365 (anteprima)
ms.openlocfilehash: 2f7e922f1e9abd68ebe51d26ef270760a7c446e2
ms.sourcegitcommit: 22fd8517707ed3ab6ef996247ad2aa372535ee56
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/19/2020
ms.locfileid: "46815244"
---
# <a name="network-connectivity-in-the-microsoft-365-admin-center-preview"></a>Connettività di rete nell'interfaccia di amministrazione di Microsoft 365 (anteprima)

L'interfaccia di amministrazione di Microsoft 365 ora includesaggregated la metrica di connettività di rete raccolta dal tenant di Microsoft 365 e disponibile per la visualizzazione solo da parte di utenti amministrativi del tenant. Le **valutazioni di rete** e le informazioni sulla **rete** vengono visualizzate nell'interfaccia di amministrazione di Microsoft 365 in **Health | Connettività**.

![Pagina prestazioni di rete](../media/m365-mac-perf/m365-mac-perf-page-nav.png)

Quando si accede per la prima volta alla pagina connettività di rete, viene visualizzato un riquadro di panoramica contenente una mappa delle prestazioni della rete globale, una valutazione della rete con ambito per l'intero tenant e un elenco di problemi correnti. Dalla panoramica, è possibile eseguire il drill-down per visualizzare specifiche metriche delle prestazioni di rete e problemi in base alla posizione. Per ulteriori informazioni, vedere [Network Performance Overview in the Microsoft 365 Admin Center](#network-connectivity-overview-in-the-microsoft-365-admin-center).

## <a name="pre-requisites-for-network-connectivity-assessments-to-appear"></a>Requisiti preliminari per le valutazioni della connettività di rete da visualizzare

Sono disponibili tre opzioni per ottenere valutazioni di rete dai percorsi di Office:

### <a name="1-enable-windows-location-services"></a>1. abilitare i servizi di posizione di Windows

Per questa opzione è necessario disporre di almeno due computer in esecuzione in ogni percorso di Office che supporta i prerequisiti. OneDrive per Windows versione 19,232 o successive deve essere installato in ogni computer. Per ulteriori informazioni sulle versioni di OneDrive, vedere le [Note sulla versione di OneDrive](https://support.office.com/article/onedrive-release-notes-845dcf18-f921-435e-bf28-4e24b95e5fc0). Le misure di rete sono pianificate per essere aggiunte in altre applicazioni client di Office 365 nel prossimo futuro.

Il servizio percorso di Windows deve essere consenziente sui computer. È possibile eseguire il testing eseguendo l'applicazione **Maps** e individuando manualmente. Può essere abilitata in un singolo computer con la posizione della privacy **delle impostazioni**in  ->  **Privacy**  ->  **Location** cui deve essere abilitata l'impostazione "Consenti app per accedere al percorso". Il consenso dei servizi di posizione di Windows può essere distribuito ai PC utilizzando MDM o criteri di gruppo con l'impostazione _LetAppsAccessLocation_.

Non è necessario aggiungere percorsi nell'interfaccia di amministrazione con questo metodo, in quanto vengono identificati automaticamente nella risoluzione della città. Non è possibile visualizzare più percorsi di Office all'interno di una città tramite i servizi di posizione di Windows.

I computer devono disporre di una rete Wi-Fi anziché di un cavo Ethernet. I computer che dispongono di un cavo Ethernet non dispongono di informazioni sulla posizione accurate.

Gli esempi di misura e le posizioni degli uffici devono iniziare a essere visualizzati 24 ore dopo che questi prerequisiti sono stati soddisfatti.

### <a name="2-add-locations-and-provide-lan-subnet-information"></a>2. aggiungere posizioni e fornire informazioni sulla subnet LAN

Per questa opzione non sono necessari né i servizi di posizione di Windows né la connessione Wi-Fi. È necessario OneDrive per Windows version 20.161.0811.0001 o versione precedente installata su ogni commputer nel percorso.

È inoltre necessario aggiungere posizioni nella pagina di connettività di rete dell'interfaccia di amministrazione o per importare quelle da un file CSV. Le posizioni aggiunte devono includere le informazioni sulla subnet LAN di Office.

Poiché si aggiungono le posizioni, è possibile disporre di più uffici definiti all'interno di una città.

Gli esempi di misura e le posizioni degli uffici devono iniziare a essere visualizzati 24 ore dopo che questi prerequisiti sono stati soddisfatti.

### <a name="3-manually-gather-test-reports-with-the-microsoft-365-network-connectivity-test-tool"></a>3. raccogliere manualmente i report di test con lo strumento di test della connettività di rete di Microsoft 365

Per questa opzione è necessario identificare una persona in ogni posizione. Chiedere agli utenti di eseguire il [test di connettività di rete di Microsoft 365](https://connectivity.office.com) su un computer Windows con autorizzazioni amministrative. Nel sito Web devono accedere all'account di Office 365 nello stesso tenant in cui si desidera visualizzare i risultati. Fare clic su Esegui test. Durante il test è disponibile un EXE di test di connettività scaricato. È necessario aprire ed eseguire anche questo. Dopo aver completato i test, il risultato del test viene caricato su Microsoft.

I rapporti di test sono collegati a una posizione se sono stati aggiunti con informazioni sulla subnet LAN, altrimenti vengono visualizzati solo nella posizione della città.

Gli esempi di misura e le posizioni degli uffici devono iniziare a essere visualizzati 2-3 minuti dopo il completamento di un risultato del test.

## <a name="how-do-i-use-this-information"></a>Come si utilizzano queste informazioni?

**Intuizioni di rete**, le raccomandazioni relative alle prestazioni e le valutazioni di rete correlate sono utili per la progettazione di perimetri di rete per le posizioni di Office. Ogni Insight fornisce informazioni dettagliate sulle caratteristiche delle prestazioni per un problema comune specifico per ogni posizione geografica in cui gli utenti accedono al tenant. Le indicazioni relative alle **prestazioni** per ogni Network Insight offrono specifiche modifiche alla progettazione dell'architettura di rete che è possibile apportare per migliorare l'esperienza degli utenti in relazione alla connettività di rete Microsoft 365. La valutazione della rete illustra come la connettività di rete influisce sull'esperienza utente, consentendo il confronto tra diverse connessioni di rete per le posizioni degli utenti.

Le **valutazioni di rete** distillano un'aggregazione di molte metriche delle prestazioni di rete in un'istantanea dell'integrità della rete aziendale, rappresentata da un valore a punti compreso tra 0-100. Le valutazioni di rete sono limitate all'intero tenant e per ogni posizione geografica da cui gli utenti si connettono al tenant, fornendo agli amministratori di Microsoft 365 un modo semplice per afferrare istantaneamente una Gestalt dell'integrità della rete dell'organizzazione e analizzarla rapidamente in una relazione dettagliata per qualsiasi posizione globale dell'ufficio.

Le aziende complesse con più percorsi di Office e architetture perimetrali di rete non banali possono trarre vantaggio da queste informazioni durante l'onboarding iniziale a Microsoft 365 o per correggere i problemi di prestazioni della rete individuati con la crescita dell'utilizzo. In genere non è necessario per le aziende di piccole dimensioni che utilizzano Microsoft 365 o per le aziende che dispongono già di connettività di rete semplice e diretta. Le aziende con oltre 500 utenti e più sedi di Office dovrebbero avvantaggiarsi al massimo.

>[!IMPORTANT]
>Insights di rete, raccomandazioni sulle prestazioni e valutazioni nell'interfaccia di amministrazione di Microsoft 365 è attualmente in stato di anteprima ed è disponibile solo per i tenant di Microsoft 365 che sono stati registrati nel programma di anteprima delle funzionalità.

## <a name="enterprise-network-connectivity-challenges"></a>Problemi relativi alla connettività di rete aziendale

![Rete del cliente per il cloud](../media/m365-mac-perf/m365-mac-perf-first-last-mile.png)

Molte aziende dispongono di configurazioni perimetrali di rete che sono cresciute nel tempo e sono progettate principalmente per ospitare l'accesso ai siti Web di un dipendente, in cui la maggior parte dei siti Web non è nota in anticipo e non è attendibile. Lo stato attivo prevalente e necessario è evitare attacchi di malware e di pesca da questi siti web sconosciuti. Questa strategia di configurazione della rete, sebbene utile per motivi di sicurezza, può comportare un peggioramento delle prestazioni dell'utente e dell'esperienza utente di Microsoft 365.

## <a name="how-we-can-solve-these-challenges"></a>Come risolvere queste sfide

Le aziende possono migliorare l'esperienza utente generale e proteggere l'ambiente seguendo i [principi di connettività di Office 365](https://aka.ms/pnc) e utilizzando la funzionalità di connettività di rete di interfaccia di amministrazione di Microsoft 365. Nella maggior parte dei casi, i seguenti principi generali avranno un impatto positivo significativo sulla latenza degli utenti finali, l'affidabilità del servizio e le prestazioni complessive di Microsoft 365.

A volte viene chiesto a Microsoft di esaminare i problemi relativi alle prestazioni di rete con Microsoft 365 per i clienti di grandi dimensioni e spesso presentano una causa principale relativa all'infrastruttura di uscita della rete dei clienti. Quando viene trovata una causa principale comune di un problema di perimetro della rete del cliente, si cerca di identificare le misure di test semplici che lo identificano. Un test con una soglia di misurazione che identifica un problema specifico è importante perché è possibile testare la stessa misura in qualsiasi posizione, stabilire se questa causa principale è presente e condividerla come Insight di rete con l'amministratore.

Alcune informazioni di rete indicano solo un problema che richiede ulteriori indagini. Un'analisi di rete in cui sono disponibili test sufficienti per visualizzare un'azione di correzione specifica per correggere la causa principale è elencata come **azione consigliata**. Questi suggerimenti, basati su metriche in tempo reale che rivelano valori che non rientrano in una soglia predeterminata, sono molto più importanti dei consigli generali di Best practice, poiché sono specifici dell'ambiente in uso e mostrano il miglioramento effettivo dopo che sono state apportate le modifiche consigliate.

## <a name="network-connectivity-overview-in-the-microsoft-365-admin-center"></a>Panoramica della connettività di rete nell'interfaccia di amministrazione di Microsoft 365

Microsoft dispone di misure di rete esistenti da diversi client desktop e Web Office che supportano il funzionamento di Microsoft 365. Queste misure vengono ora utilizzate per fornire informazioni sulla progettazione dell'architettura di rete e una valutazione della rete mostrata nella pagina **connettività di rete** nell'interfaccia di amministrazione di Microsoft 365.

Per impostazione predefinita, le informazioni di posizione approssimative associate alle misure di rete identificano la città in cui si trovano i dispositivi client. La valutazione della rete in ogni percorso viene visualizzata con il colore e il numero relativo di utenti in ogni posizione è rappresentato dalle dimensioni del cerchio.

![Mappa Panoramica di Network Insights](../media/m365-mac-perf/m365-mac-perf-overview-map.png)

La pagina Panoramica Visualizza inoltre la valutazione della rete per il cliente come media ponderata in tutte le posizioni di Office.

![Valutazione della rete](../media/m365-mac-perf/m365-mac-perf-overview-score.png)

## <a name="specific-office-location-network-performance-summary-and-insights"></a>Riepilogo e informazioni dettagliate sulle prestazioni di una rete di Office location

Se si seleziona un percorso di Office, viene visualizzata una pagina di riepilogo specifica del percorso in cui vengono visualizzati i dettagli relativi all'uscita di rete identificati dalle misure per il percorso di Office.

![Informazioni dettagliate sulla rete in base alla posizione](../media/m365-mac-perf/m365-mac-perf-locations-plan-overview.png)

La pagina di riepilogo dell'ubicazione di Office consente inoltre di visualizzare la valutazione della rete della posizione, la cronologia di valutazione della rete, il confronto tra la valutazione di questo percorso e gli altri clienti della stessa città, nonché un elenco di approfondimenti e suggerimenti specifici che è possibile intraprendere per migliorare le prestazioni e l'affidabilità della rete. Le posizioni con raccomandazioni specifiche possono includere anche un miglioramento della latenza potenziale stimato.

I confronti tra clienti nella stessa città si basano sull'aspettativa che tutti i clienti abbiano uguale accesso ai provider di servizi di rete, all'infrastruttura di telecomunicazioni e ai punti di presenza della rete Microsoft nelle vicinanze.

![Posizioni di Network Insights](../media/m365-mac-perf/m365-mac-perf-locations.png)

Nella scheda Dettagli della pagina percorso di Office sono riportati i risultati di misura specifici che sono stati utilizzati per fornire informazioni dettagliate, suggerimenti e valutazione della rete. Questo viene fornito in modo che gli ingegneri di rete possano convalidare le raccomandazioni e il fattore in qualsiasi vincolo o specifiche nel proprio ambiente.

![Dettagli specifici della posizione](../media/m365-mac-perf/m365-mac-perf-locations-plan-details-all.png)

## <a name="csv-import-for-lan-subnet-office-locations"></a>Importazione CSV per i percorsi di Office subnet LAN

Per l'identificazione dell'ufficio della subnet LAN, è necessario aggiungere ogni locaiton in anticipo. Invece di aggiungere singoli percorsi di Office nella scheda **percorsi** , è possibile importarli da un file CSV. Potrebbe essere possibile ottenere questi dati da altri luoghi che sono stati archiviati, ad esempio il dashboard qualità chiamata o siti e servizi di Active Directory.

Nel file CSV una posizione della città scoperta è contrassegnata come **City**e una posizione di Office aggiunta manualmente è contrassegnata come **posizione**.

1. Nella finestra _connettività principale a Microsoft 365_ fare clic sulla scheda **percorsi** .
1. Fare clic sul pulsante **Importa** appena sopra l'elenco percorsi. Verrà visualizzato il riquadro a comparsa di **Import Office Locations** .

   ![Messaggio di errore di importazione CSV](../media/m365-mac-perf/m365-mac-perf-import.png)

1. Fare clic sul collegamento **download Office Locations (. csv)** per esportare l'elenco delle posizioni correnti in un file CSV e salvarlo sul disco rigido locale. In questo modo viene fornito un formato CSV formattato correttamente con intestazioni di colonna a cui è possibile aggiungere posizioni. È possibile lasciare le posizioni esportate esistenti così come sono. non verranno duplicati quando si importa il file CSV aggiornato. Se si desidera modificare l'indirizzo di una posizione esistente, verrà aggiornata quando si importa il file CSV. Non è possibile modificare l'indirizzo di una città individuata.
1. Aprire il file CSV e aggiungere le posizioni compilando i seguenti campi su una nuova riga per ogni posizione che si desidera aggiungere. Lasciare vuoti tutti gli altri campi; i valori immessi in altri campi verranno ignorati.
   1. **Indirizzo** (obbligatorio): indirizzo fisico dell'ufficio
   1. **Latitude** (facoltativo): popolato da Bing Maps Lookup se vuoto
   1. **Longitudine** (facoltativa): popolata dalla ricerca di Bing Maps se vuota
   1. **Intervalli di indirizzi IP di uscita 1-5** (facoltativo): per ogni intervallo, immettere il nome del circuito seguito da un elenco separato da spazi di indirizzi CIDR IPv4 o IPv6 validi. Questi valori vengono utilizzati per distinguere più percorsi di Office in cui si utilizzano gli stessi indirizzi IP della subnet LAN.
   1. **LanIps** (obbligatorio): elenca gli intervalli di subnet LAN in uso in questa posizione di Office.
1. Dopo aver aggiunto i percorsi di Office e aver salvato il file, fare clic sul pulsante **Sfoglia** accanto al campo **carica il completamento** e selezionare il file CSV salvato.
1. Il file verrà convalidato automaticamente. Se sono presenti errori di convalida, verrà visualizzato il messaggio _di errore nel file di importazione. Esaminare gli errori, correggere il file di importazione e quindi riprovare._ Fare clic sul collegamento **Dettagli errore di apertura** per un elenco di errori specifici di convalida dei campi.

   ![Messaggio di errore di importazione CSV](../media/m365-mac-perf/m365-mac-perf-import-error.png)

1. Se nel file non sono presenti errori, verrà visualizzato il messaggio che _il report è pronto. Sono stati individuati i percorsi x da aggiungere e x per l'aggiornamento._ Fare clic sul pulsante **Importa** per caricare il file CSV.

   ![Messaggio di importazione CSV pronto](../media/m365-mac-perf/m365-mac-perf-import-ready.png)

## <a name="faq"></a>Domande frequenti

### <a name="what-is-a-microsoft-365-service-front-door"></a>Che cos'è una porta principale di servizio Microsoft 365?

Microsoft 365 Service front door è un punto di ingresso sulla rete globale di Microsoft in cui i client e i servizi di Office terminano la connessione di rete. Per una connessione di rete ottimale a Microsoft 365, è consigliabile che la connessione di rete venga terminata nella porta principale di Microsoft 365 più vicina.

>[!NOTE]
>La porta principale di servizio Microsoft 365 non ha alcuna relazione diretta con il prodotto di servizio di Azure front door disponibile in Azure Marketplace.

### <a name="what-is-an-optimal-microsoft-365-service-front-door"></a>Che cos'è un'ottima porta di servizio di Microsoft 365 Service?

Un'ottima porta di servizio di Microsoft 365 Service è quella più vicina all'uscita di rete, in genere nella propria area urbana o metropolitana. Utilizzare il [test di connettività di microsoft 365](office-365-network-mac-perf-onboarding-tool.md) per determinare la posizione del portello anteriore del servizio Microsoft 365 in uso e la porta anteriore del servizio ottimale. Se lo strumento determina che la porta principale in uso è ottimale, è possibile connettersi in modo ottimale alla rete globale di Microsoft.

### <a name="what-is-an-internet-egress-location"></a>Che cos'è un percorso di uscita Internet?

La posizione di uscita Internet è il percorso in cui il traffico di rete esce dalla rete aziendale e si connette a Internet. Questo è anche identificato come il percorso in cui si dispone di un dispositivo NAT (Network Address Translation) e in genere dove si è connessi con un provider di servizi Internet (ISP). Se si vede una distanza interurbana tra la posizione e la posizione di uscita Internet, questo potrebbe indicare una significativa backhaul WAN.

## <a name="related-topics"></a>Argomenti correlati

[Microsoft 365 Insights Network (anteprima)](office-365-network-mac-perf-insights.md)

[Valutazione della rete Microsoft 365 (Preview)](office-365-network-mac-perf-score.md)

[Test di connettività Microsoft 365 nell'interfaccia di amministrazione di M365 (anteprima)](office-365-network-mac-perf-onboarding-tool.md)

[Microsoft 365 servizi di localizzazione della connettività di rete (anteprima)](office-365-network-mac-location-services.md)
