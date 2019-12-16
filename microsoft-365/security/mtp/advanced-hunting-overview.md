---
title: Informazioni generali sulla ricerca avanzata di Microsoft Threat Protection
description: Informazioni sulle query di ricerca avanzata in Microsoft 365 e sul loro utilizzo per individuare in modo proattivo i rischi e i punti di debolezza della rete
keywords: ricerca avanzata, ricerca delle minacce, ricerca delle minacce informatiche, ricerca, query, telemetria, rilevamenti personalizzati, schema, esplora dati, Microsoft 365, Microsoft Threat Protection
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
ms.openlocfilehash: 03cd648a178d63b2b964e0136c105068f4d1c6ca
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2019
ms.locfileid: "39911238"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-threat-protection"></a><span data-ttu-id="80eb5-104">Cercare in modo proattivo minacce con la ricerca avanzata di Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="80eb5-104">Proactively hunt for threats with advanced hunting in Microsoft Threat Protection</span></span>

<span data-ttu-id="80eb5-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="80eb5-105">**Applies to:**</span></span>
- <span data-ttu-id="80eb5-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="80eb5-106">Microsoft Threat Protection</span></span>

[!include[Prerelease information](prerelease.md)]

<span data-ttu-id="80eb5-107">La ricerca avanzata è uno strumento di ricerca delle minacce basato sulla query che permette di esplorare dati non elaborati fino a 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="80eb5-107">Advanced hunting is a query-based threat-hunting tool that lets you explore up to 30 days of raw data.</span></span> <span data-ttu-id="80eb5-108">È possibile controllare in modo proattivo eventi nella rete per localizzare indicatori ed entità interessanti.</span><span class="sxs-lookup"><span data-stu-id="80eb5-108">You can proactively inspect events in your network to locate interesting indicators and entities.</span></span> <span data-ttu-id="80eb5-109">L'accesso flessibile ai dati facilita la ricerca non vincolata delle minacce conosciute e potenziali.</span><span class="sxs-lookup"><span data-stu-id="80eb5-109">The flexible access to data facilitates unconstrained hunting for both known and potential threats.</span></span>

<span data-ttu-id="80eb5-110">nel Centro sicurezza Microsoft 365, la ricerca avanzata supporta query che esaminano i dati di Microsoft Defender ATP, di dispositivi caricati e di Office 365 ATP, fornendo i dati dalle email.</span><span class="sxs-lookup"><span data-stu-id="80eb5-110">in the Microsoft 365 security center, advanced hunting supports queries that look into data from both Microsoft Defender ATP, covering data from onboarded devices, and Office 365 ATP, providing data from emails.</span></span> <span data-ttu-id="80eb5-111">Per utilizzare la ricerca avanzata, [attivare Microsoft Threat Protection](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="80eb5-111">To use advanced hunting, [turn on Microsoft Threat Protection](mtp-enable.md).</span></span>

## <a name="get-started-with-advanced-hunting"></a><span data-ttu-id="80eb5-112">Introduzione alla ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="80eb5-112">Get started with advanced hunting</span></span>

<span data-ttu-id="80eb5-113">È consigliabile passare attraverso diverse fasi per diventare rapidamente operativi con la ricerca avanzata.</span><span class="sxs-lookup"><span data-stu-id="80eb5-113">We recommend going through several steps to quickly get up and running with advanced hunting.</span></span>

| <span data-ttu-id="80eb5-114">Obiettivo di formazione</span><span class="sxs-lookup"><span data-stu-id="80eb5-114">Learning goal</span></span> | <span data-ttu-id="80eb5-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="80eb5-115">Description</span></span> | <span data-ttu-id="80eb5-116">Risorsa</span><span class="sxs-lookup"><span data-stu-id="80eb5-116">Resource</span></span> |
|--|--|--|
| <span data-ttu-id="80eb5-117">**Avere un'idea della lingua**</span><span class="sxs-lookup"><span data-stu-id="80eb5-117">**Get a feel for the language**</span></span> | <span data-ttu-id="80eb5-118">La ricerca avanzata si basa sul [linguaggio di query Kusto](https://docs.microsoft.com/azure/kusto/query/), supportandone la sintassi e gli operatori.</span><span class="sxs-lookup"><span data-stu-id="80eb5-118">Advanced hunting is based on the [Kusto query language](https://docs.microsoft.com/azure/kusto/query/), supporting the same syntax and operators.</span></span> <span data-ttu-id="80eb5-119">Iniziare ad apprendere il linguaggio di query eseguendone la prima.</span><span class="sxs-lookup"><span data-stu-id="80eb5-119">Start learning the query language by running your first query.</span></span> | [<span data-ttu-id="80eb5-120">Informazioni generali sul linguaggio di query</span><span class="sxs-lookup"><span data-stu-id="80eb5-120">Query language overview</span></span>](advanced-hunting-query-language.md) |
| <span data-ttu-id="80eb5-121">**Comprensione dello schema**</span><span class="sxs-lookup"><span data-stu-id="80eb5-121">**Understand the schema**</span></span> | <span data-ttu-id="80eb5-122">È possibile ottenere una conoscenza buona e approfondita delle tabelle nello schema e delle relative colonne.</span><span class="sxs-lookup"><span data-stu-id="80eb5-122">Get a good, high-level understanding of the tables in the schema and their columns.</span></span> <span data-ttu-id="80eb5-123">Questo consente di determinare dove cercare i dati e come creare le query.</span><span class="sxs-lookup"><span data-stu-id="80eb5-123">This will help you determine where to look for data and how to construct your queries.</span></span> | [<span data-ttu-id="80eb5-124">Informazioni di riferimento sullo schema</span><span class="sxs-lookup"><span data-stu-id="80eb5-124">Schema Reference</span></span>](advanced-hunting-schema-tables.md) |
| <span data-ttu-id="80eb5-125">**Utilizzare le query predefinite**</span><span class="sxs-lookup"><span data-stu-id="80eb5-125">**Use predefined queries**</span></span> | <span data-ttu-id="80eb5-126">Esplorare le raccolte di query predefinite che coprono diversi scenari di ricerca delle minacce.</span><span class="sxs-lookup"><span data-stu-id="80eb5-126">Explore collections of predefined queries covering different threat hunting scenarios.</span></span> | [<span data-ttu-id="80eb5-127">Utilizzare le query condivise</span><span class="sxs-lookup"><span data-stu-id="80eb5-127">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
| <span data-ttu-id="80eb5-128">**Ottimizzare le query**</span><span class="sxs-lookup"><span data-stu-id="80eb5-128">**Optimize queries**</span></span> | <span data-ttu-id="80eb5-129">Informazioni su come creare query efficienti e query che combinino dati da email e dispositivi.</span><span class="sxs-lookup"><span data-stu-id="80eb5-129">Understand how to create efficient queries and queries that combine data from emails and devices.</span></span> | <span data-ttu-id="80eb5-130">[Procedure consigliate per le query](advanced-hunting-shared-queries.md), [Ricerca attraverso dispositivi ed email](advanced-hunting-best-practices.md)</span><span class="sxs-lookup"><span data-stu-id="80eb5-130">[Query best practices](advanced-hunting-shared-queries.md), [Hunt across devices and emails](advanced-hunting-best-practices.md)</span></span>

## <a name="get-help-as-you-write-queries"></a><span data-ttu-id="80eb5-131">Ottenere assistenza nella scrittura delle query</span><span class="sxs-lookup"><span data-stu-id="80eb5-131">Get help as you write queries</span></span>
<span data-ttu-id="80eb5-132">Trarre vantaggio dalle seguenti funzionalità per scrivere query più velocemente:</span><span class="sxs-lookup"><span data-stu-id="80eb5-132">Take advantage of the following functionality to write queries faster:</span></span>
- <span data-ttu-id="80eb5-133">**Suggerimenti automatici** — durante la scrittura di query, la ricerca avanzata propone suggerimenti.</span><span class="sxs-lookup"><span data-stu-id="80eb5-133">**Autosuggest** — as you write queries, advanced hunting provides suggestions.</span></span> 
- <span data-ttu-id="80eb5-134">**Riferimento di schema** — accanto all’area di lavoro è disponibile il riferimento a uno schema che include l'elenco di tabelle e le relative colonne.</span><span class="sxs-lookup"><span data-stu-id="80eb5-134">**Schema reference** — a schema reference that includes the list of tables and their columns is provided next to your working area.</span></span> <span data-ttu-id="80eb5-135">Per altre informazioni, passare il puntatore su un elemento.</span><span class="sxs-lookup"><span data-stu-id="80eb5-135">For more information, hover over an item.</span></span> <span data-ttu-id="80eb5-136">Fare doppio clic su un elemento per inserirlo nell'editor di query.</span><span class="sxs-lookup"><span data-stu-id="80eb5-136">Double-click an item to insert it to the query editor.</span></span>

## <a name="drilldown-from-query-results"></a><span data-ttu-id="80eb5-137">Eseguire il drill-down dai risultati della query</span><span class="sxs-lookup"><span data-stu-id="80eb5-137">Drilldown from query results</span></span>
<span data-ttu-id="80eb5-138">Per visualizzare altre informazioni sulle entità, come computer, file, utenti, indirizzi IP e URL, fare clic sull'identificatore di entità nei risultati delle query.</span><span class="sxs-lookup"><span data-stu-id="80eb5-138">To view more information about entities, such as machines, files, users, IP addresses, and URLs, in your query results, simply click the entity identifier.</span></span> <span data-ttu-id="80eb5-139">Quindi si aprirà una pagina profilo dettagliata per l’entità selezionata nel Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="80eb5-139">This opens a detailed profile page for the selected entity in Microsoft Defender Security Center.</span></span>

## <a name="tweak-your-queries-from-the-results"></a><span data-ttu-id="80eb5-140">Perfezionare le query dai risultati</span><span class="sxs-lookup"><span data-stu-id="80eb5-140">Tweak your queries from the results</span></span>
<span data-ttu-id="80eb5-141">Fare clic con il pulsante destro del mouse su un valore nel set di risultati per migliorare rapidamente la query.</span><span class="sxs-lookup"><span data-stu-id="80eb5-141">Right-click a value in the result set to quickly enhance your query.</span></span> <span data-ttu-id="80eb5-142">È possibile usare le opzioni per:</span><span class="sxs-lookup"><span data-stu-id="80eb5-142">You can use the DLP reports to:</span></span>

- <span data-ttu-id="80eb5-143">Cercare in modo esplicito il valore selezionato (`==`)</span><span class="sxs-lookup"><span data-stu-id="80eb5-143">Explicitly look for the selected value (`==`)</span></span>
- <span data-ttu-id="80eb5-144">Escludere il valore selezionato dalla query (`!=`)</span><span class="sxs-lookup"><span data-stu-id="80eb5-144">Exclude the selected value from the query (`!=`)</span></span>
- <span data-ttu-id="80eb5-145">Per aggiungere il valore alla query, è possibile usare gli operatori più avanzati, come `contains`, `starts with` e `ends with`</span><span class="sxs-lookup"><span data-stu-id="80eb5-145">Get more advanced operators for adding the value to your query, such as `contains`, `starts with` and `ends with`</span></span> 

![Immagine del set di risultati della ricerca avanzata Microsoft Defender ATP](../images/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a><span data-ttu-id="80eb5-147">Filtrare i risultati della query</span><span class="sxs-lookup"><span data-stu-id="80eb5-147">Filter the query results</span></span>
<span data-ttu-id="80eb5-148">I filtri visualizzati a destra forniscono un riepilogo del set di risultati.</span><span class="sxs-lookup"><span data-stu-id="80eb5-148">The filters displayed to the right provide a summary of the result set.</span></span> <span data-ttu-id="80eb5-149">Ogni colonna ha una propria sezione in cui sono elencati i valori distinti individuati per quella colonna e il numero di istanze.</span><span class="sxs-lookup"><span data-stu-id="80eb5-149">Each column has its own section that lists the distinct values found for that column and the number of instances.</span></span>

<span data-ttu-id="80eb5-150">Perfezionare la query selezionando i pulsanti "+" o "-" sui valori che si desidera includere o escludere e quindi selezionare **Esegui query**.</span><span class="sxs-lookup"><span data-stu-id="80eb5-150">Refine your query by selecting the "+" or "-" buttons on the values that you want to include or exclude and then selecting **Run query**.</span></span>

![Immagine del filtro di ricerca avanzata](../images/advanced-hunting-filter.png)

<span data-ttu-id="80eb5-152">Dopo avere applicato il filtro per modificare la query e aver eseguito la query, i risultati vengono aggiornati di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="80eb5-152">Once you apply the filter to modify the query and then run the query, the results are updated accordingly.</span></span>

## <a name="related-topics"></a><span data-ttu-id="80eb5-153">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="80eb5-153">Related topics</span></span>
- [<span data-ttu-id="80eb5-154">Apprendere il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="80eb5-154">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="80eb5-155">Utilizzare le query condivise</span><span class="sxs-lookup"><span data-stu-id="80eb5-155">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="80eb5-156">Ricerca delle minacce attraverso dispositivi ed email</span><span class="sxs-lookup"><span data-stu-id="80eb5-156">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="80eb5-157">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="80eb5-157">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="80eb5-158">Applicazione delle procedure consigliate per le query</span><span class="sxs-lookup"><span data-stu-id="80eb5-158">Apply query best practices</span></span>](advanced-hunting-best-practices.md)