---
title: Notifica dal servizio di trattamento dei dati per Windows ai sensi del GDPR
description: Informazioni su come il servizio di trattamento dei dati per Windows protegge da una violazione dei dati personali e su come Microsoft gestisce un'eventuale violazione e lo comunica agli utenti interessati.
keywords: Servizio di trattamento dei dati per Windows, Microsoft 365, documentazione di Microsoft 365, GDPR
localization_priority: Priority
ROBOTS: NOINDEX, NOFOLLOW
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: daniha
author: DaniHalfin
manager: dansimp
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
ms.openlocfilehash: bfadeae0f4f0b01197f58f0610d1040da3080922
ms.sourcegitcommit: 3ddcf08e8deec087df1fe524147313f1cb12a26d
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2020
ms.locfileid: "45023632"
---
# <a name="data-processor-service-for-windows-breach-notification-under-the-gdpr"></a>Notifica di violazione dal servizio di trattamento dei dati per Windows ai sensi del GDPR

>[!NOTE]
>Questo argomento è destinato ai partecipanti al servizio di trattamento dei dati per il programma di anteprima di Windows e richiede l'accettazione di specifiche condizioni d'uso. Per maggiori informazioni sul programma e per l'accettazione delle condizioni d'uso, vedere [https://aka.ms/dpswpublicpreview](https://aka.ms/dpswpublicpreview).

Per il servizio di trattamento dei dati per Windows di Microsoft, il rispetto degli obblighi derivanti dal Regolamento generale sulla protezione dei dati (GDPR) è importante. Il servizio di trattamento dei dati per Windows di Microsoft adotta misure di sicurezza estensive per proteggere gli utenti dalle violazioni dei dati. Queste includono team dedicati alla gestione delle minacce che prevedono, prevengono e riducono proattivamente il rischio di accessi dannosi.Le misure di sicurezza interne quali scansione porte, analisi delle vulnerabilità dei perimetri e rilevamento delle intrusioni rilevano e prevengono gli accessi dannosi, così come i processi di sicurezza automatizzati, criteri completi di sicurezza e privacy delle informazioni e formazione sulla sicurezza e sulla privacy per tutto il personale. 

La sicurezza è integrata nel servizio di trattamento dei dati per Windows di Microsoft, a partire dal [Security Development Lifecycle](https://www.microsoft.com/sdl/), un processo di sviluppo obbligatorio che incorpora le metodologie di privacy by design e privacy by default. Il principio guida della strategia di sicurezza di Microsoft consiste nel "presumere la violazione", configurandosi come un'estensione della strategia di difesa completa. Mettendo costantemente alla prova le funzionalità di sicurezza del servizio di trattamento dei dati per Windows, Microsoft può stare al passo con le minacce emergenti. Per ulteriori informazioni sulla sicurezza del servizio di trattamento dei dati per Windows, consultare queste [risorse](https://www.microsoft.com/TrustCenter/Security/windows10-security). Il servizio di trattamento dei dati per Windows risponde a una potenziale violazione dei dati in base al processo di risposta agli incidenti di sicurezza. La risposta agli incidenti di sicurezza del servizio di trattamento dei dati per Windows viene implementata tramite un processo costituito da cinque fasi: rilevamento, valutazione, diagnostica, stabilizzazione e chiusura. Il team di risposta in caso di incidenti di sicurezza può alternare le fasi di diagnosi e stabilizzazione man mano che l'indagine procede. Di seguito è riportata una panoramica del processo di risposta in caso di incidenti di sicurezza: 

|**Fase**|**Descrizione**|
| ------- | ------------- |
| ***1 - Rilevamento*** | Prima indicazione di un potenziale incidente. |
| ***2 - Valutazione*** | An on-call incident response team member assesses the impact and severity of the event. Based on evidence, the assessment may or may not result in further escalation to the security response team. |
| ***3 - Diagnostica*** | Gli esperti del team di intervento della sicurezza svolgono le indagini tecniche o forensi, identificano le strategie di contenimento, mitigazione e le soluzioni alternative. Se il team della sicurezza ritiene che i dati del cliente potrebbero essere stati esposti a un individuo non autorizzato o a un criminale, il processo di notifica dell'incidente al cliente si svolge in parallelo. |
| ***4 - Stabilizzazione e ripristino*** | The incident response team creates a recovery plan to mitigate the issue. Crisis containment steps such as quarantining impacted systems may occur immediately and in parallel with diagnosis. Longer term mitigations may be planned which occur after the immediate risk has passed. |
| ***5 - Chiusura e relazione finale*** | Il team di intervento per gli incidenti crea una relazione finale dettagliata dell'incidente finalizzata alla revisione di criteri, procedure e interventi per prevenire il ripetersi dell'evento. |

I processi di rilevamento utilizzati dal servizio di trattamento dei dati per Windows sono progettati per rilevare eventi che mettono a rischio la riservatezza, l'integrità e la disponibilità dei servizi del servizio di trattamento dei dati per Windows. Diversi eventi possono dare il via a un'indagine: 

 - Avvisi di sistema automatici tramite framework di monitoraggio e avviso interni. Questi avvisi potrebbero interferire con avvisi basati su firma come antimalware, rilevamento di intrusioni o tramite algoritmi progettati per tracciare il profilo dell'attività prevista e segnalare anomalie.
 - Report di prima parte dei servizi Microsoft in esecuzione su Microsoft Azure e Azure per enti pubblici.
 - Le vulnerabilità di sicurezza vengono segnalate a [Microsoft Security Response Center (MSRC)](https://technet.microsoft.com/security/dn440717) tramite [secure@microsoft.com] (mailto:secure@microsoft.com). MSRC collabora con partner e ricercatori di sicurezza di tutto il mondo per prevenire gli incidenti e migliorare la sicurezza dei prodotti Microsoft.
 - Report dei clienti tramite il Portale di supporto tecnico o il portale di Microsoft Azure e Azure per enti pubblici, che descrivono attività sospette attribuite all'infrastruttura di Azure (al contrario delle attività che si verificano nell'ambito di responsabilità del cliente).
 - Attività di [Red Team e Blue Team](https://azure.microsoft.com/blog/red-teaming-using-cutting-edge-threat-simulation-to-harden-the-microsoft-enterprise-cloud/) per la sicurezza. Questa strategia utilizza un Red Team altamente qualificato di esperti di sicurezza offensiva di Microsoft per individuare e attaccare potenziali vulnerabilità in Azure. Il Blue Team di intervento per la sicurezza deve rilevare e difendersi dall'attività del Read Team. Le azioni del Red team e del Blue Team vengono usate per verificare che gli interventi per la sicurezza di Azure gestiscano in modo efficace gli incidenti. Le attività di sicurezza del Red Team e del Blue Team vengono gestite secondo regole di ingaggio per garantire la protezione dei dati dei clienti.
 - Escalation da parte degli operatori di servizi di Azure. I dipendenti Microsoft sono addestrati per identificare e inoltrare potenziali problemi riguardanti la sicurezza.

 ## <a name="data-processor-service-for-windows-data-breach-response"></a>Risposta alle violazioni dei dati da parte del servizio di trattamento dei dati per Windows 

 Microsoft assegna all'indagine adeguati livelli di priorità e gravità determinando l'impatto funzionale, la recuperabilità e l'impatto dell'evento sulle informazioni. La priorità e la gravità possono cambiare nel corso dell'indagine sulla base di nuove scoperte e conclusioni. Gli eventi di sicurezza che comportano rischi imminenti o confermati per i dati del cliente sono considerati di gravità elevata e vengono seguiti 24 ore su 24 fino a quando non vengono risolti. Il servizio di trattamento dei dati per Windows di Microsoft classifica l'impatto dell'incidente sulle informazioni nelle seguenti categorie di violazione: 

| **Categoria**             | **Definizione**                                                                                                                   |
| ------------------------ | -------------------------------------------------------------------------------------------------------------------------------- |
| ***Nessuna***               | Nessuna informazione è stata estratta, modificata, cancellata o comunque compromessa. |
| ***Violazione della privacy***     | È stato possibile accedere o estrarre dati personali sensibili riguardanti i contribuenti, i dipendenti, i beneficiari e così via. |
| ***Violazioni di proprietà*** | È stato possibile accedere o estrarre informazioni proprietarie non classificate, ad esempio informazioni riguardanti l'infrastruttura critica protetta (PCII). |
| ***Perdita di integrità***     | Sono state modificate o cancellate informazioni sensibili o proprietarie. |

Il team di Security Response collabora con il servizio di trattamento dei dati per Windows di Microsoft per Windows Security Engineers e SME al fine di classificare l'evento sulla base di dati concreti tratti dalle prove raccolte. Un evento di sicurezza può essere classificato come: 

 - **Falso positivo**: un evento che soddisfa i criteri di rilevamento ma che risulta essere parte di una normale pratica aziendale e può avere bisogno di essere filtrato. Il team del servizio identificherà la causa principale dei falsi positivi e li risolverà in modo sistematico sfruttando le fonti di rilevamento e ottimizzandole se necessario. 
 - **Incidente di sicurezza**: un accesso illecito o non autorizzato ai dati del cliente o ai dati di supporto archiviati nei dispositivi o nelle sedi Microsoft che ha provocato la perdita, la divulgazione o l'alterazione dei dati del cliente o dei dati di supporto. 
 - **Incidenti di sicurezza segnalabili dal cliente (CRSI)**: un accesso o un utilizzo illecito o non autorizzato dei sistemi, dei dispositivi o delle sedi Microsoft che ha provocato la divulgazione, la modifica o la perdita dei dati del cliente. 
 - **Violazione della privacy**: un sottotipo di incidente di sicurezza che coinvolge dati personali. Le procedure di gestione non sono diverse da un incidente di sicurezza. 

 For a CRSI to be declared, Microsoft must determine that unauthorized access to customer data has or has very likely occurred and/or that there is a legal or contractual commitment that notification must occur. It is desired, but not required, that specific customer impact, resource access, and repair steps be known. An incident is generally declared a CRSI after the conclusion of the Diagnose stage of a security incident; however, the declaration may happen at any point that all pertinent information is available. The security incident manager must establish evidence beyond reasonable doubt that a reportable event has occurred to begin execution of the Customer Incident Notification Process. 

Throughout the investigation, the security response team works closely with global legal advisors to help ensure that forensics are performed in accordance with legal obligations and commitments to customers. There are also significant restrictions on system and customer data viewing and handling in various operating environments. Sensitive or confidential data, as well as Customer Data, are not transferred out of the production environment without explicit written approval from the Incident Manager recorded in the corresponding incident ticket. 

Microsoft verifies that customer and business risk is successfully contained, and that corrective measures are implemented. If necessary, emergency mitigation steps to resolve immediate security risks associated with the event are taken. 

Microsoft completa anche una relazione finale interna per violazioni dei dati. Come parte di questo esercizio, sono state valutate la sufficienza delle procedure di risposta e di funzionamento, e gli eventuali aggiornamenti che potrebbero essere necessari al SOP o ai processi correlati sono identificati e implementati. La relazione finale interna per le violazioni dei dati è un registro altamente riservato che non è disponibile per i clienti. Le relazioni finali, tuttavia, possono essere riepilogate e incluse nelle altre notifiche di eventi relative al cliente. Questi report vengono forniti ai revisori esterni per la revisione come parte del ciclo di controllo di routine del servizio di trattamento dei dati per Windows. 

## <a name="customer-notice"></a>Comunicazione ai clienti

Il servizio di trattamento dei dati per Windows di Microsoft informa clienti e autorità competenti delle violazioni dei dati come richiesto. Microsoft si basa su una forte compartimentazione interna nel funzionamento del servizio di trattamento dei dati per Windows. Anche i registri del flusso di dati sono solidi. Un vantaggio di questa struttura è che la maggior parte degli incidenti può essere ricondotta a clienti specifici. L'obiettivo è fornire ai clienti interessati una comunicazione accurata, attuabile e tempestiva nel momento in cui i dati vengono violati. 

Dopo aver dichiarato un CRSI, il processo di notifica si verificherà nel modo più rapido possibile, pur considerando i rischi per la sicurezza di tale rapidità. In generale, il processo di stesura delle notifiche avviene quando è in corso l'indagine sull'incidente. Le notifiche ai clienti vengono recapitate entro 72 ore dall’identificazione di una violazione tranne nei casi seguenti: 

 - Microsoft believes the act of performing a notification will increase the risk to other customers. For example, the act of notifying may tip off an adversary causing an inability to remediate. 
 - Altre circostanze insolite o estreme esaminate dall'ufficio legale di Microsoft (CELA) e dall'Executive Incident Manager. 

 Il servizio di trattamento dei dati per Windows di Microsoft fornisce ai clienti informazioni dettagliate che consentono loro di svolgere indagini interne e di assisterli nell'adempimento degli impegni assunti con l'utente finale, senza ritardare ingiustificatamente il processo di notifica. 

La notifica di una violazione dei dati personali verrà recapitata al cliente con qualsiasi mezzo Microsoft selezioni, anche tramite posta elettronica. La notifica di una violazione dei dati verrà inviata all'elenco dei contatti di sicurezza specificato nel Centro sicurezza di Azure, che può essere configurato seguendo le [linee guida per l'implementazione](https://docs.microsoft.com/azure/security-center/security-center-provide-security-contact-details). Se le informazioni sui contatti non sono disponibili nel Centro sicurezza di Azure, la notifica verrà inviata a uno o più amministratori di una sottoscrizione di Azure. Per fare in modo che la notifica possa essere recapitata correttamente, il cliente è tenuto a verificare la correttezza delle informazioni sui contatti amministrativi relative a ogni sottoscrizione e portale dei servizi online applicabile.

Il team del servizio di trattamento dei dati per Windows di Microsoft può anche decidere di informare altri membri del personale Microsoft, ad esempio il servizio clienti (CSS) e l'Account Manager del cliente (AM) o il Technical Account Manager (TAM). Tali figure hanno spesso strette relazioni con il cliente e possono facilitare una correzione più rapida. 

Per ulteriori informazioni su come Microsoft rileva e interviene a un caso di violazione dei dati personali, vedere [Notifica di violazione dei dati secondo il GDPR](https://servicetrust.microsoft.com/ViewPage/GDPRBreach) nel Service Trust Portal.