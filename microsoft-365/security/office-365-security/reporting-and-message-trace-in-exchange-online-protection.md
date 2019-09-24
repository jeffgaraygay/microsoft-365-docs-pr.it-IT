---
title: Creazione di rapporti e traccia dei messaggi in Exchange Online Protection
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 12/18/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: f40253f2-50a1-426e-9979-be74ba74cb61
description: Microsoft (EOP) Exchange Online Protection offre diversi rapporti che consentono di determinare lo stato generale e l'integrità dell'organizzazione. Sono inoltre disponibili strumenti per la risoluzione dei problemi relativi a eventi specifici, ad esempio il mancato recapito di un messaggio ai destinatari desiderati, e report di controllo per assicurare il rispetto dei requisiti di conformità. Nella tabella seguente vengono descritti i report e gli strumenti per la risoluzione dei problemi disponibili per gli amministratori di EOP.
ms.openlocfilehash: 39ac70c401cb4a630b95fab89fe3a145495c29eb
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37082809"
---
# <a name="reporting-and-message-trace-in-exchange-online-protection"></a>Creazione di rapporti e traccia dei messaggi in Exchange Online Protection

Microsoft (EOP) Exchange Online Protection offre diversi rapporti che consentono di determinare lo stato generale e l'integrità dell'organizzazione. Sono inoltre disponibili strumenti per la risoluzione dei problemi relativi a eventi specifici, ad esempio il mancato recapito di un messaggio ai destinatari desiderati, e report di controllo per assicurare il rispetto dei requisiti di conformità.

## <a name="usage-reports"></a>Report sull'uso

**Attività gruppi di office 365**: consente di visualizzare informazioni sul numero di gruppi di Office 365 creati e utilizzati.  

**Attività di posta elettronica**: consente di visualizzare informazioni sul numero di messaggi inviati, ricevuti e letti nell'intera organizzazione e per utenti specifici.  

**Utilizzo delle app di posta elettronica**: consente di visualizzare le informazioni sulle app di posta elettronica utilizzate. Questi dati includono il numero totale di connessioni per ogni applicazione e le versioni di Outlook con cui si stabilisce la connessione.  

**Utilizzo delle cassette postali**: consente di visualizzare informazioni sull'archiviazione utilizzata, sul consumo di quote, sul numero di elementi e sull'ultima attività (invio o lettura) per le cassette postali.

Per ulteriori informazioni, vedere le risorse seguenti:

- [Rapporti di Office 365 nell'interfaccia di amministrazione-gruppi di Office 365](https://go.microsoft.com/fwlink/p/?linkid=861610)

- [Report di Office 365 nell'interfaccia di amministrazione - Attività di posta elettronica](https://go.microsoft.com/fwlink/p/?linkid=859706)

- [Report di Office 365 nell'interfaccia di amministrazione - Utilizzo delle applicazioni di posta elettronica](https://go.microsoft.com/fwlink/p/?linkid=859707)

- [Report di Office 365 nell'interfaccia di amministrazione - Utilizzo delle cassette postali](https://go.microsoft.com/fwlink/p/?linkid=859708)

## <a name="security--compliance-reports-in-the-microsoft-365-admin-center"></a>Rapporti di conformità & di sicurezza nell'interfaccia di amministrazione di Microsoft 365

Questi report avanzati forniscono un'esperienza di report interattiva per gli amministratori di EOP, che include informazioni di riepilogo e la possibilità di eseguire il drill-down per ulteriori dettagli.  

**Advanced Threat Protection (ATP)**: visualizzare informazioni sui collegamenti sicuri e sugli allegati sicuri che fanno parte di ATP.  

**EOP**: consente di visualizzare informazioni su rilevamenti di malware, posta contraffatta, rilevamenti di posta indesiderata e flusso di posta da e verso l'organizzazione.  

[Visualizzare i report per Advanced Threat Protection e Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkid=852409)

## <a name="custom-reports-using-microsoft-graph"></a>Report personalizzati tramite Microsoft Graph

Creare report a livello di programmazione che sono disponibili nell'interfaccia di amministrazione di Microsoft 365 tramite Microsoft Graph vedere gli argomenti secondari di utilizzo dei [report sull'utilizzo di Office 365 in Microsoft Graph](https://go.microsoft.com/fwlink/p/?linkid=865135)

## <a name="custom-reports-using-reporting-web-services"></a>Rapporti personalizzati tramite servizi Web Reporting

Creare report a livello di programmazione dai cmdlet di report di Exchange Online Protection PowerShell disponibili utilizzando il filtro delle query REST/ODATA2.

Vedere [servizi Web di Reporting di Office 365](https://go.microsoft.com/fwlink/p/?LinkId=279926)

## <a name="message-trace"></a>Traccia dei messaggi

Consente di seguire il percorso dei messaggi all'interno di EOP. È possibile stabilire se un messaggio di posta elettronica è stato ricevuto, rifiutato, ritardato o recapitato dal servizio. Mostra inoltre quali azioni sono state eseguite sul messaggio prima del raggiungimento dello stato finale.  

È possibile utilizzare queste informazioni per rispondere in modo efficiente alle domande dell'utente, risolvere i problemi relativi al flusso di posta, convalidare le modifiche apportate ai criteri e ridurre la necessità di contattare il supporto tecnico per assistenza.  

Vedere [traccia di un messaggio di posta elettronica](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/trace-an-email-message)

## <a name="audit-logging"></a>Registrazione di controllo

Consente di tenere traccia di modifiche specifiche apportate all'organizzazione dagli amministratori. Questi report consentono di risolvere problemi di configurazione o individuare la causa di problemi relativi alla sicurezza o alla conformità. Vedere [rapporti di controllo in EOP](auditing-reports-in-eop.md).

## <a name="reporting-and-message-trace-data-availability-and-latency"></a>Rapporti e latenza e disponibilità dei dati dei messaggi

La tabella seguente descrive quando in EOP le funzionalità di creazione rapporti e dati di traccia dei messaggi sono disponibili e per quanto tempo.
  
||||
|:-----|:-----|:-----|
|**Tipo di rapporto**|**Dati disponibili per (periodo passato)**|**Latenza**|
|Rapporti di riepilogo sulla protezione della posta|90 giorni|L'aggregazione dei dati dei messaggi è quasi completa entro 24-48 ore. Alcune modifiche aggregate incrementali minori possono verificarsi in un periodo massimo di 5 giorni.|
|Rapporti dettagliati sulla protezione della posta|90 giorni|Per dati dettagliati creati da meno di 7 giorni, i dati devono essere visualizzati entro 24 ore ma potrebbero non essere completi fino a 48 ore. Alcune modifiche incrementali minori possono verificarsi in un periodo massimo di 5 giorni. <br/><br/> Per visualizzare rapporti dettagliati per messaggi creati da più di 7 giorni, i risultati potrebbero richiedere alcune ore.|
|Dati di traccia dei messaggi|90 giorni|Quando si esegue la traccia dei messaggi per i messaggi creati da meno di 7 giorni, i messaggi devono essere visualizzati entro un periodo compreso tra 5 e 30 minuti.<br/><br/> Quando si esegua la traccia dei messaggi per messaggi creati da più di 7 giorni, i risultati potrebbero richiedere alcune ore.|

> [!NOTE]
> La disponibilità e la latenza dei dati sono le stesse se richieste tramite l'interfaccia di amministrazione di Microsoft 365 o Remote PowerShell. 