---
title: Procedure consigliate nella Ricerca avanzata di Microsoft Threat Protection
description: Come creare query di ricerca delle minacce veloci, efficienti e senza errori quando in Ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca delle minacce informatiche, ricerca, query, telemetria, rilevamenti personalizzati, schema, esplora dati, evitare timeout, linee di comando, id processo
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
ms.openlocfilehash: ceb8679ccdd5c1fb41772a8b48d9474665922f39
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2019
ms.locfileid: "39911203"
---
# <a name="advanced-hunting-query-best-practices"></a><span data-ttu-id="44824-104">Procedure consigliate per query in Ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="44824-104">Advanced hunting query best practices</span></span>

<span data-ttu-id="44824-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="44824-105">**Applies to:**</span></span>
- <span data-ttu-id="44824-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="44824-106">Microsoft Threat Protection</span></span>

[!include[Prerelease information](prerelease.md)]

## <a name="optimize-query-performance"></a><span data-ttu-id="44824-107">Ottimizzare le prestazioni delle query</span><span class="sxs-lookup"><span data-stu-id="44824-107">Optimize query performance</span></span>
<span data-ttu-id="44824-108">Applicare questi suggerimenti per ottenere risultati più rapidi ed evitare timeout durante l'esecuzione di query complesse:</span><span class="sxs-lookup"><span data-stu-id="44824-108">Apply these recommendations to get results faster and avoid timeouts while running complex queries:</span></span>
- <span data-ttu-id="44824-109">Quando si provano nuove query, usare sempre `limit` per evitare set di risultati molto grandi.</span><span class="sxs-lookup"><span data-stu-id="44824-109">When trying new queries, always use `limit` to avoid extremely large result sets.</span></span> <span data-ttu-id="44824-110">È anche possibile determinare all'inizio le dimensioni del set di risultati usando `count`.</span><span class="sxs-lookup"><span data-stu-id="44824-110">You can also initially assess the size of the result set using `count`.</span></span>
- <span data-ttu-id="44824-111">Usare prima i filtri del periodo.</span><span class="sxs-lookup"><span data-stu-id="44824-111">Use time filters first.</span></span> <span data-ttu-id="44824-112">Idealmente, è consigliabile limitare le query ai giorni pari.</span><span class="sxs-lookup"><span data-stu-id="44824-112">Ideally, limit your queries to even days.</span></span>
- <span data-ttu-id="44824-113">Inserire i filtri che si prevede rimuovano la maggior parte dei dati all'inizio della query, subito dopo il filtro del periodo.</span><span class="sxs-lookup"><span data-stu-id="44824-113">Put filters that are expected to remove most of the data in the beginning of the query, right after the time filter.</span></span>
- <span data-ttu-id="44824-114">Usare l'operatore `has` su `contains` quando si cercano token completi.</span><span class="sxs-lookup"><span data-stu-id="44824-114">Use the `has` operator over `contains` when looking for full tokens.</span></span>
- <span data-ttu-id="44824-115">Individuare una colonna specifica invece di eseguire le ricerche in tutte le colonne.</span><span class="sxs-lookup"><span data-stu-id="44824-115">Look in a specific column rather than running full text searches across all columns.</span></span>
- <span data-ttu-id="44824-116">Quando si uniscono le tabelle, specificare prima la tabella con meno righe.</span><span class="sxs-lookup"><span data-stu-id="44824-116">When joining tables, specify the table with fewer rows first.</span></span>
- <span data-ttu-id="44824-117">`project` solo le colonne necessarie dalle tabelle che sono state unite.</span><span class="sxs-lookup"><span data-stu-id="44824-117">`project` only the necessary columns from tables you've joined.</span></span>

>[!Tip]
><span data-ttu-id="44824-118">Per altre informazioni su come migliorare le prestazioni della query, vedere [procedure consigliate per le query di Esplora dati](https://docs.microsoft.com/azure/kusto/query/best-practices).</span><span class="sxs-lookup"><span data-stu-id="44824-118">For more guidance on improving query performance, read [Kusto query best practices](https://docs.microsoft.com/azure/kusto/query/best-practices).</span></span>

## <a name="query-tips-and-pitfalls"></a><span data-ttu-id="44824-119">Suggerimenti e insidie per le query</span><span class="sxs-lookup"><span data-stu-id="44824-119">Query tips and pitfalls</span></span>

### <a name="queries-with-process-ids"></a><span data-ttu-id="44824-120">Query con ID processo</span><span class="sxs-lookup"><span data-stu-id="44824-120">Queries with process IDs</span></span>
<span data-ttu-id="44824-121">Gli ID processo (PID) sono riciclati in Windows e riutilizzati per i nuovi processi.</span><span class="sxs-lookup"><span data-stu-id="44824-121">Process IDs (PIDs) are recycled in Windows and reused for new processes.</span></span> <span data-ttu-id="44824-122">Di per sé, non possono servire come identificatori univoci per processi specifici.</span><span class="sxs-lookup"><span data-stu-id="44824-122">On their own, they can't serve as unique identifiers for specific processes.</span></span>

<span data-ttu-id="44824-123">Per ottenere un identificatore univoco per un computer specifico, usare l'ID processo insieme all'ora di creazione del processo.</span><span class="sxs-lookup"><span data-stu-id="44824-123">To get a unique identifier for a process on a specific machine, use the process ID together with the process creation time.</span></span> <span data-ttu-id="44824-124">Quando si uniscono o si riepilogano i dati relativi a processi, includere le colonne per l'identificatore del computer (`MachineId` o `ComputerName`), l'ID processo (`ProcessId` o `InitiatingProcessId`) e l'ora di creazione del processo (`ProcessCreationTime` o `InitiatingProcessCreationTime`)</span><span class="sxs-lookup"><span data-stu-id="44824-124">When you join or summarize data around processes, include columns for the machine identifier (either `MachineId` or `ComputerName`), the process ID (`ProcessId` or `InitiatingProcessId`), and the process creation time (`ProcessCreationTime` or `InitiatingProcessCreationTime`)</span></span>

<span data-ttu-id="44824-125">La seguente query di esempio trova i processi che accedono a più di 10 indirizzi IP dalla porta 445 (SMB), possibilmente analizzando le condivisioni file.</span><span class="sxs-lookup"><span data-stu-id="44824-125">The following example query finds processes that access more than 10 IP addresses over port 445 (SMB), possibly scanning for file shares.</span></span>

<span data-ttu-id="44824-126">Query di esempio:</span><span class="sxs-lookup"><span data-stu-id="44824-126">Example query:</span></span>
```
NetworkCommunicationEvents
| where RemotePort == 445 and EventTime > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by ComputerName, InitiatingProcessId, InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

<span data-ttu-id="44824-127">La query riepiloga sia `InitiatingProcessId` che `InitiatingProcessCreationTime` in modo da visualizzare un singolo processo, senza combinare più processi con lo stesso ID processo.</span><span class="sxs-lookup"><span data-stu-id="44824-127">The query summarizes by both `InitiatingProcessId` and `InitiatingProcessCreationTime` so that it looks at a single process, without mixing multiple processes with the same process ID.</span></span>

### <a name="queries-with-command-lines"></a><span data-ttu-id="44824-128">Query con righe di comando</span><span class="sxs-lookup"><span data-stu-id="44824-128">Queries with command lines</span></span>

<span data-ttu-id="44824-129">Le righe di comando possono variare.</span><span class="sxs-lookup"><span data-stu-id="44824-129">Command lines can vary.</span></span> <span data-ttu-id="44824-130">Se applicabile, filtrare i nomi dei file ed eseguire una corrispondenza fuzzy.</span><span class="sxs-lookup"><span data-stu-id="44824-130">When applicable, filter on file names and do fuzzy matching.</span></span>

<span data-ttu-id="44824-131">Esistono diversi modi per creare una riga di comando per eseguire un'attività.</span><span class="sxs-lookup"><span data-stu-id="44824-131">There are numerous ways to construct a command line to accomplish a task.</span></span> <span data-ttu-id="44824-132">Ad esempio, un utente malintenzionato può fare riferimento a un file di immagine con o senza un percorso, senza un'estensione di file, con variabili di ambiente o con virgolette.</span><span class="sxs-lookup"><span data-stu-id="44824-132">For example, an attacker could reference an image file with or without a path, without a file extension, using environment variables, or with quotes.</span></span> <span data-ttu-id="44824-133">Inoltre, l'utente malintenzionato può anche cambiare l'ordine dei parametri o aggiungere più citazioni e spazi.</span><span class="sxs-lookup"><span data-stu-id="44824-133">In addition, the attacker could also change the order of parameters or add multiple quotes and spaces.</span></span>

<span data-ttu-id="44824-134">Per creare query più durevoli usando le righe di comando, applicare le procedure seguenti:</span><span class="sxs-lookup"><span data-stu-id="44824-134">To create more durable queries using command lines, apply the following practices:</span></span>

- <span data-ttu-id="44824-135">Identificare i processi noti (ad esempio *NET. exe* o *psexec. exe*) confrontando i campi filename (nome file), anziché filtrare nel campo della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="44824-135">Identify the known processes (such as *net.exe* or *psexec.exe*) by matching on the filename fields, instead of filtering on the command-line field.</span></span>
- <span data-ttu-id="44824-136">Quando si eseguono query per gli argomenti della riga di comando, non cercare una corrispondenza esatta su più argomenti non correlati in un determinato ordine.</span><span class="sxs-lookup"><span data-stu-id="44824-136">When querying for command-line arguments, don't look for an exact match on multiple unrelated arguments in a certain order.</span></span> <span data-ttu-id="44824-137">Usare invece espressioni regolari o utilizzare più operatori distinti.</span><span class="sxs-lookup"><span data-stu-id="44824-137">Instead, use regular expressions or use multiple separate contains operators.</span></span>
- <span data-ttu-id="44824-138">Usare corrispondenza maiuscole/minuscole.</span><span class="sxs-lookup"><span data-stu-id="44824-138">Use case insensitive matches.</span></span> <span data-ttu-id="44824-139">Ad esempio, usare `=~`, `in~`e `contains` anziché `==`, `in`e `contains_cs`</span><span class="sxs-lookup"><span data-stu-id="44824-139">For example, use `=~`, `in~`, and `contains` instead of `==`, `in`, and `contains_cs`</span></span>
- <span data-ttu-id="44824-140">Per migrare tecniche di offuscamento di linee di domando DOS, provare a rimuovere virgolette, sostituire virgole con spazi e sostituire doppi spazi con uno spazio singolo.</span><span class="sxs-lookup"><span data-stu-id="44824-140">To mitigate DOS command-line obfuscation techniques, consider removing quotes, replacing commas with spaces, and replacing multiple consecutive spaces with a single space.</span></span> <span data-ttu-id="44824-141">Tenere presente che esistono tecniche di offuscamento DOS ancora più complesse che richiedono altri approcci, tuttavia queste possono aiutare a gestire i casi più comuni.</span><span class="sxs-lookup"><span data-stu-id="44824-141">Note that there are more complex DOS obfuscation techniques that require other approaches, but these can help address the most common ones.</span></span>

<span data-ttu-id="44824-142">I seguenti esempi mostrano diversi modi di creare una query per cercare il file *net.exe* che blocca il servizio Windows Defender Firewall:</span><span class="sxs-lookup"><span data-stu-id="44824-142">The following examples show various ways to construct a query that looks for the file *net.exe* to stop the Windows Defender Firewall service:</span></span>

```
// Non-durable query - do not use
ProcessCreationEvents
| where ProcessCommandLine == "net stop MpsSvc"
| limit 10

// Better query - filters on filename, does case-insensitive matches
ProcessCreationEvents
| where EventTime > ago(7d) and FileName in~ ("net.exe", "net1.exe") and ProcessCommandLine contains "stop" and ProcessCommandLine contains "MpsSvc" 

// Best query also ignores quotes
ProcessCreationEvents
| where EventTime > ago(7d) and FileName in~ ("net.exe", "net1.exe")
| extend CanonicalCommandLine=replace("\"", "", ProcessCommandLine)
| where CanonicalCommandLine contains "stop" and CanonicalCommandLine contains "MpsSvc" 
```
## <a name="related-topics"></a><span data-ttu-id="44824-143">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="44824-143">Related topics</span></span>
- [<span data-ttu-id="44824-144">Ricerca proattiva delle minacce</span><span class="sxs-lookup"><span data-stu-id="44824-144">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="44824-145">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="44824-145">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="44824-146">Utilizzare le query condivise</span><span class="sxs-lookup"><span data-stu-id="44824-146">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="44824-147">Ricerca delle minacce attraverso dispositivi e email</span><span class="sxs-lookup"><span data-stu-id="44824-147">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="44824-148">Comprensione dello schema</span><span class="sxs-lookup"><span data-stu-id="44824-148">Understand the schema</span></span>](advanced-hunting-schema-tables.md)