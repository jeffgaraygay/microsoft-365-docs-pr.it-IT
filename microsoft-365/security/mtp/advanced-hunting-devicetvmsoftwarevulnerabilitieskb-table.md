---
title: La tabella DeviceTvmSoftwareVulnerabilitiesKB nello schema di ricerca avanzata
description: Informazioni sulle vulnerabilità del software monitorate dalla Gestione delle minacce e delle vulnerabilità nella tabella DeviceTvmSoftwareVulnerabilitiesKB dello schema di ricerca avanzata.
keywords: caccia avanzata, caccia alle minacce, Cyber-caccia alle minacce, Microsoft Threat Protection, Microsoft 365, MTP, M365, ricerca, query, telemetria, schema, riferimento, kusto, tabella, colonna, tipo di dati, descrizione, Threat & vulnerabilità di gestione, TVM, gestione dei dispositivi, software, inventario, vulnerabilità, ID CVE, CVSS, DeviceTvmSoftwareVulnerabilitiesKB
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
ms.openlocfilehash: 378ffee34a24af225b1b6deebd7cc514c62e1926
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327971"
---
# <a name="devicetvmsoftwarevulnerabilitieskb"></a><span data-ttu-id="fa280-104">DeviceTvmSoftwareVulnerabilitiesKB</span><span class="sxs-lookup"><span data-stu-id="fa280-104">DeviceTvmSoftwareVulnerabilitiesKB</span></span>

<span data-ttu-id="fa280-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="fa280-105">**Applies to:**</span></span>
- <span data-ttu-id="fa280-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="fa280-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="fa280-107">La tabella `DeviceTvmSoftwareVulnerabilitiesKB` nello schema di ricerca avanzata contiene l'elenco delle vulnerabilità per le quali [Gestione delle minacce e delle vulnerabilità](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) valuta i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="fa280-107">The `DeviceTvmSoftwareVulnerabilitiesKB` table in the advanced hunting schema contains the list of vulnerabilities [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) assesses devices for.</span></span> <span data-ttu-id="fa280-108">Utilizzare questo riferimento per creare query che forniscano informazioni dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="fa280-108">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="fa280-109">Per informazioni sulle altre tabelle nello schema per Ricerca avanzata vedere [le informazioni di riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="fa280-109">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="fa280-110">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="fa280-110">Column name</span></span> | <span data-ttu-id="fa280-111">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="fa280-111">Data type</span></span> | <span data-ttu-id="fa280-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fa280-112">Description</span></span> |
|-------------|-----------|-------------|
| `CveId` | <span data-ttu-id="fa280-113">stringa</span><span class="sxs-lookup"><span data-stu-id="fa280-113">string</span></span> | <span data-ttu-id="fa280-114">Identificatore univoco assegnato alla vulnerabilità di sicurezza nell'ambito del sistema Vulnerabilità ed esposizioni comuni (CVE)</span><span class="sxs-lookup"><span data-stu-id="fa280-114">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `CvssScore` | <span data-ttu-id="fa280-115">stringa</span><span class="sxs-lookup"><span data-stu-id="fa280-115">string</span></span> | <span data-ttu-id="fa280-116">Punteggio di gravità assegnato alla vulnerabilità di sicurezza secondo il Sistema di punteggio della vulnerabilità comune (CVSS)</span><span class="sxs-lookup"><span data-stu-id="fa280-116">Severity score assigned to the security vulnerability under th Common Vulnerability Scoring System (CVSS)</span></span> |
| `IsExploitAvailable` | <span data-ttu-id="fa280-117">boolean</span><span class="sxs-lookup"><span data-stu-id="fa280-117">boolean</span></span> | <span data-ttu-id="fa280-118">Indica se il codice di sfruttamento della vulnerabilità è disponibile pubblicamente</span><span class="sxs-lookup"><span data-stu-id="fa280-118">Indicates whether exploit code for the vulnerability is publicly available</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="fa280-119">stringa</span><span class="sxs-lookup"><span data-stu-id="fa280-119">string</span></span> | <span data-ttu-id="fa280-120">Livello di gravità assegnato alla vulnerabilità della sicurezza in base al Punteggio CVSS e ai fattori dinamici influenzati dal panorama delle minacce</span><span class="sxs-lookup"><span data-stu-id="fa280-120">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `LastModifiedTime` | <span data-ttu-id="fa280-121">datetime</span><span class="sxs-lookup"><span data-stu-id="fa280-121">datetime</span></span> | <span data-ttu-id="fa280-122">Data e ora dell'ultima modifica dell'elemento o dei metadati correlati</span><span class="sxs-lookup"><span data-stu-id="fa280-122">Date and time the item or related metadata was last modified</span></span> |
| `PublishedDate` | <span data-ttu-id="fa280-123">datetime</span><span class="sxs-lookup"><span data-stu-id="fa280-123">datetime</span></span> | <span data-ttu-id="fa280-124">La vulnerabilità della data è stata resa pubblica</span><span class="sxs-lookup"><span data-stu-id="fa280-124">Date vulnerability was disclosed to public</span></span> |
| `VulnerabilityDescription` | <span data-ttu-id="fa280-125">stringa</span><span class="sxs-lookup"><span data-stu-id="fa280-125">string</span></span> | <span data-ttu-id="fa280-126">Descrizione della vulnerabilità e dei rischi associati</span><span class="sxs-lookup"><span data-stu-id="fa280-126">Description of vulnerability and associated risks</span></span> |
| `AffectedSoftware` | <span data-ttu-id="fa280-127">stringa</span><span class="sxs-lookup"><span data-stu-id="fa280-127">string</span></span> | <span data-ttu-id="fa280-128">Elenco di tutti i prodotti software soggetti alla vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="fa280-128">List of all software products affected by the vulnerability</span></span> |

## <a name="related-topics"></a><span data-ttu-id="fa280-129">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="fa280-129">Related topics</span></span>

- [<span data-ttu-id="fa280-130">Ricerca proattiva delle minacce</span><span class="sxs-lookup"><span data-stu-id="fa280-130">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="fa280-131">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="fa280-131">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="fa280-132">Utilizzare le query condivise</span><span class="sxs-lookup"><span data-stu-id="fa280-132">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="fa280-133">Ricerca delle minacce attraverso dispositivi e posta elettronica</span><span class="sxs-lookup"><span data-stu-id="fa280-133">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="fa280-134">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="fa280-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="fa280-135">Applicare le procedure consigliate per le query</span><span class="sxs-lookup"><span data-stu-id="fa280-135">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="fa280-136">Panoramica della Gestione della vulnerabilità e delle minacce</span><span class="sxs-lookup"><span data-stu-id="fa280-136">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)