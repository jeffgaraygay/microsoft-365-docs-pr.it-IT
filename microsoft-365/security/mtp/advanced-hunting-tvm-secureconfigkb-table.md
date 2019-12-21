---
title: Tabella DeviceTvmSecureConfigurationAssessmentKB nello schema per Ricerca avanzata
description: Informazioni sulle diverse configurazioni sicure valutate da Gestione delle minacce e della vulnerabilità nella tabella DeviceTvmSecureConfigurationAssessmentKB dello schema per Ricerca avanzata.
keywords: ricerca avanzata, ricerca delle minacce, ricerca minacce informatiche, ricerca, eseguire una query, telemetria, riferimento dello schema, esplora dati, tabella, colonna, tipo di dati, descrizione, gestione delle minacce e della vulnerabilità, TVM, gestione dei dispositivi, configurazione della sicurezza, framework MITRE ATT&CK, knowledge base, KB, DeviceTvmSecureConfigurationAssessmentKB
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: a3ae0a95af4a51d492c577e6a2ac1f2b96bba635
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2019
ms.locfileid: "40806935"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a><span data-ttu-id="f7b09-104">DeviceTvmSecureConfigurationAssessmentKB</span><span class="sxs-lookup"><span data-stu-id="f7b09-104">DeviceTvmSecureConfigurationAssessmentKB</span></span>

<span data-ttu-id="f7b09-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="f7b09-105">**Applies to:**</span></span>
- <span data-ttu-id="f7b09-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="f7b09-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="f7b09-107">La tabella `DeviceTvmSecureConfigurationAssessmentKB` nello schema per Ricerca avanzata contiene informazioni riguardanti le varie configurazioni sicure (ad esempio, se un dispositivo ha aggiornamenti automatici attivi) controllate da [Gestione delle minacce e della vulnerabilità](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span><span class="sxs-lookup"><span data-stu-id="f7b09-107">The `DeviceTvmSecureConfigurationAssessmentKB` table in the advanced hunting schema contains information about the various secure configurations — such as whether a device has automatic updates on — checked by [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="f7b09-108">Include inoltre informazioni relative ai rischi, benchmark del settore correlati e tecniche e tattiche MITRE ATT&CK applicabili.</span><span class="sxs-lookup"><span data-stu-id="f7b09-108">It also includes risk information, related industry benchmarks, and applicable MITRE ATT&CK techniques and tactics.</span></span> <span data-ttu-id="f7b09-109">Utilizzare questo riferimento per creare query che forniscano informazioni dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="f7b09-109">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="f7b09-110">Per informazioni sulle altre tabelle nello schema per Ricerca avanzata vedere [le informazioni di riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="f7b09-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="f7b09-111">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="f7b09-111">Column name</span></span> | <span data-ttu-id="f7b09-112">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="f7b09-112">Data type</span></span> | <span data-ttu-id="f7b09-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f7b09-113">Description</span></span> |
|-------------|-----------|-------------|
| `ConfigurationId` | <span data-ttu-id="f7b09-114">stringa</span><span class="sxs-lookup"><span data-stu-id="f7b09-114">string</span></span> | <span data-ttu-id="f7b09-115">Identificatore univoco di una configurazione specifica</span><span class="sxs-lookup"><span data-stu-id="f7b09-115">Unique identifier for a specific configuration</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="f7b09-116">stringa</span><span class="sxs-lookup"><span data-stu-id="f7b09-116">string</span></span> | <span data-ttu-id="f7b09-117">Impatto nominale della configurazione sul punteggio di configurazione complessivo (1-10)</span><span class="sxs-lookup"><span data-stu-id="f7b09-117">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `ConfigurationName` | <span data-ttu-id="f7b09-118">stringa</span><span class="sxs-lookup"><span data-stu-id="f7b09-118">string</span></span> | <span data-ttu-id="f7b09-119">Nome visualizzato della configurazione</span><span class="sxs-lookup"><span data-stu-id="f7b09-119">Display name of the configuration</span></span> |
| `ConfigurationDescription` | <span data-ttu-id="f7b09-120">stringa</span><span class="sxs-lookup"><span data-stu-id="f7b09-120">string</span></span> | <span data-ttu-id="f7b09-121">Descrizione della configurazione</span><span class="sxs-lookup"><span data-stu-id="f7b09-121">Description of the configuration</span></span> |
| `RiskDescription` | <span data-ttu-id="f7b09-122">stringa</span><span class="sxs-lookup"><span data-stu-id="f7b09-122">string</span></span> | <span data-ttu-id="f7b09-123">Descrizione del rischio associato</span><span class="sxs-lookup"><span data-stu-id="f7b09-123">Description of the associated risk</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="f7b09-124">stringa</span><span class="sxs-lookup"><span data-stu-id="f7b09-124">string</span></span> | <span data-ttu-id="f7b09-125">Categoria o raggruppamento a cui appartiene la configurazione: Applicazione, Sistema operativo, Rete, Account, Controlli di sicurezza</span><span class="sxs-lookup"><span data-stu-id="f7b09-125">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span>|
| `ConfigurationSubcategory` | <span data-ttu-id="f7b09-126">stringa</span><span class="sxs-lookup"><span data-stu-id="f7b09-126">string</span></span> |<span data-ttu-id="f7b09-127">Sottocategoria o sottoraggruppamento a cui appartiene la configurazione.</span><span class="sxs-lookup"><span data-stu-id="f7b09-127">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="f7b09-128">In molti casi qui vengono descritte capacità o funzionalità specifiche.</span><span class="sxs-lookup"><span data-stu-id="f7b09-128">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationBenchmarks` | <span data-ttu-id="f7b09-129">stringa</span><span class="sxs-lookup"><span data-stu-id="f7b09-129">string</span></span> | <span data-ttu-id="f7b09-130">Elenco dei parametri del settore che consigliano una configurazione identica o simile</span><span class="sxs-lookup"><span data-stu-id="f7b09-130">List of industry benchmarks recommending the same or similar configuration</span></span> |
| `RelatedMitreTechniques` | <span data-ttu-id="f7b09-131">stringa</span><span class="sxs-lookup"><span data-stu-id="f7b09-131">string</span></span> | <span data-ttu-id="f7b09-132">Elenco delle tecniche del framework Mitre ATT&CK framework correlate alla configurazione</span><span class="sxs-lookup"><span data-stu-id="f7b09-132">List of Mitre ATT&CK framework techniques related to the configuration</span></span> |
| `RelatedMitreTactics ` | <span data-ttu-id="f7b09-133">stringa</span><span class="sxs-lookup"><span data-stu-id="f7b09-133">string</span></span> | <span data-ttu-id="f7b09-134">Elenco delle tattiche del framework Mitre ATT&CK framework correlate alla configurazione</span><span class="sxs-lookup"><span data-stu-id="f7b09-134">List of Mitre ATT&CK framework tactics related to the configuration</span></span> |

## <a name="related-topics"></a><span data-ttu-id="f7b09-135">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="f7b09-135">Related topics</span></span>

- [<span data-ttu-id="f7b09-136">Ricerca proattiva delle minacce</span><span class="sxs-lookup"><span data-stu-id="f7b09-136">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="f7b09-137">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="f7b09-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="f7b09-138">Utilizzare le query condivise</span><span class="sxs-lookup"><span data-stu-id="f7b09-138">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="f7b09-139">Ricerca delle minacce attraverso dispositivi e posta elettronica</span><span class="sxs-lookup"><span data-stu-id="f7b09-139">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="f7b09-140">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="f7b09-140">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="f7b09-141">Applicare le procedure consigliate per le query</span><span class="sxs-lookup"><span data-stu-id="f7b09-141">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="f7b09-142">Panoramica della Gestione della vulnerabilità e delle minacce</span><span class="sxs-lookup"><span data-stu-id="f7b09-142">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)