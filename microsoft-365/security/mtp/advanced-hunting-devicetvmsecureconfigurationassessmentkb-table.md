---
title: Tabella DeviceTvmSecureConfigurationAssessmentKB nello schema per Ricerca avanzata
description: Informazioni sulle diverse configurazioni sicure valutate da Gestione delle minacce e della vulnerabilità nella tabella DeviceTvmSecureConfigurationAssessmentKB dello schema per Ricerca avanzata.
keywords: caccia avanzata, caccia alle minacce, Cyber Threat Hunting, Microsoft Threat Protection, Microsoft 365, MTP, M365, Search, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, Threat & vulnerabilità di gestione, TVM, gestione dei dispositivi, configurazione della sicurezza, MITRE ATT&CK Framework, Knowledge base, KB, DeviceTvmSecureConfigurationAssessmentKB
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 2c16929555b3923086e249db61cebb3cf7af17c8
ms.sourcegitcommit: 51097b18d94da20aa727ebfbeb6ec84c263b25c3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2020
ms.locfileid: "46648966"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a>DeviceTvmSecureConfigurationAssessmentKB

**Si applica a:**
- Microsoft Threat Protection



La tabella `DeviceTvmSecureConfigurationAssessmentKB` nello schema per Ricerca avanzata contiene informazioni riguardanti le varie configurazioni sicure (ad esempio, se un dispositivo ha aggiornamenti automatici attivi) controllate da [Gestione delle minacce e della vulnerabilità](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt). Include inoltre informazioni relative ai rischi, benchmark del settore correlati e tecniche e tattiche MITRE ATT&CK applicabili. Utilizzare questo riferimento per creare query che forniscano informazioni dalla tabella.

Per informazioni sulle altre tabelle nello schema per Ricerca avanzata vedere [le informazioni di riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).

| Nome colonna | Tipo di dati | Descrizione |
|-------------|-----------|-------------|
| `ConfigurationId` | stringa | Identificatore univoco di una configurazione specifica |
| `ConfigurationImpact` | stringa | Impatto nominale della configurazione sul punteggio di configurazione complessivo (1-10) |
| `ConfigurationName` | stringa | Nome visualizzato della configurazione |
| `ConfigurationDescription` | stringa | Descrizione della configurazione |
| `RiskDescription` | stringa | Descrizione del rischio associato |
| `ConfigurationCategory` | stringa | Categoria o raggruppamento a cui appartiene la configurazione: Applicazione, Sistema operativo, Rete, Account, Controlli di sicurezza|
| `ConfigurationSubcategory` | stringa |Sottocategoria o sottoraggruppamento a cui appartiene la configurazione. In molti casi qui vengono descritte capacità o funzionalità specifiche. |
| `ConfigurationBenchmarks` | stringa | Elenco dei parametri del settore che consigliano una configurazione identica o simile |
| `RelatedMitreTechniques` | stringa | Elenco delle tecniche del framework Mitre ATT&CK framework correlate alla configurazione |
| `RelatedMitreTactics ` | stringa | Elenco delle tattiche del framework Mitre ATT&CK framework correlate alla configurazione |

## <a name="related-topics"></a>Argomenti correlati

- [Ricerca proattiva delle minacce](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
- [Cercare tra i dispositivi, i messaggi di posta elettronica, le app e le identità](advanced-hunting-query-emails-devices.md)
- [Comprendere lo schema](advanced-hunting-schema-tables.md)
- [Applicare le procedure consigliate per le query](advanced-hunting-best-practices.md)
- [Panoramica della Gestione della vulnerabilità e delle minacce](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
