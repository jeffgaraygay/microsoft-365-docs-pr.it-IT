---
title: Usare le query condivise nella ricerca avanzata di Microsoft Threat Protection
description: Avviare subito la ricerca delle minacce con query predefinite e condivise. Condividere le query con il pubblico o la propria organizzazione.
keywords: ricerca avanzata, ricerca delle minacce, ricerca delle minacce informatiche, ricerca, query, telemetria, rilevamenti personalizzati, schema, esplora dati, repository GitHub, query personali, query condivise
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
ms.openlocfilehash: bd92bde39f56180a79490a24b78ee3824cc262e7
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2019
ms.locfileid: "39911207"
---
# <a name="use-shared-queries-in-advanced-hunting"></a><span data-ttu-id="5cb7e-105">Usare le query condivise nella ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="5cb7e-105">Use shared queries in advanced hunting</span></span>

<span data-ttu-id="5cb7e-106">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="5cb7e-106">**Applies to:**</span></span>
- <span data-ttu-id="5cb7e-107">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="5cb7e-107">Microsoft Threat Protection</span></span>

[!include[Prerelease information](prerelease.md)]

<span data-ttu-id="5cb7e-108">[Le query Ricerca avanzata](advanced-hunting-overview.md) possono essere condivise tra con gli utenti della stessa organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5cb7e-108">[Advanced hunting](advanced-hunting-overview.md) queries can be shared among users in the same organization.</span></span> <span data-ttu-id="5cb7e-109">È anche possibile trovare query condivise pubblicamente su GitHub.</span><span class="sxs-lookup"><span data-stu-id="5cb7e-109">You can also find queries shared publicly on GitHub.</span></span> <span data-ttu-id="5cb7e-110">Queste query consentono di intraprendere rapidamente specifici scenari di ricerca delle minacce senza dover scrivere le query da zero.</span><span class="sxs-lookup"><span data-stu-id="5cb7e-110">These queries let you quickly pursue specific threat hunting scenarios without having to write queries from scratch.</span></span>

![Immagine di query condivise](../images/advanced-hunting-shared-queries.png)

## <a name="save-modify-and-share-a-query"></a><span data-ttu-id="5cb7e-112">Salvare, modificare e condividere una query</span><span class="sxs-lookup"><span data-stu-id="5cb7e-112">Save, modify, and share a query</span></span>
<span data-ttu-id="5cb7e-113">È possibile salvare una query nuova o esistente in modo che sia solo accessibile all'utente o condivisa con altri utenti della propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5cb7e-113">You can save a new or existing query so that it is only accessible to you or shared with other users in your organization.</span></span> 

1. <span data-ttu-id="5cb7e-114">Creare o modificare una query.</span><span class="sxs-lookup"><span data-stu-id="5cb7e-114">Create or modify a query.</span></span> 

2. <span data-ttu-id="5cb7e-115">Fare clic sul pulsante a discesa **Salva query** e selezionare **Salva con nome**.</span><span class="sxs-lookup"><span data-stu-id="5cb7e-115">Click the **Save query** drop-down button and select **Save as**.</span></span>
    
3. <span data-ttu-id="5cb7e-116">Immettere un nome per la query.</span><span class="sxs-lookup"><span data-stu-id="5cb7e-116">Enter a name for the import job.</span></span> 

   ![Immagine del salvataggio di una query](../images/advanced-hunting-save-query.png)

4. <span data-ttu-id="5cb7e-118">Selezionare la cartella in cui si vuole salvare la query.</span><span class="sxs-lookup"><span data-stu-id="5cb7e-118">Select the folder where you'd like to save the query.</span></span>
    - <span data-ttu-id="5cb7e-119">**Query condivise**: query condivise con tutti gli utenti dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="5cb7e-119">**Shared queries** — shared to all users your organization</span></span>
    - <span data-ttu-id="5cb7e-120">**Query personali**: query accessibili solo all'utente</span><span class="sxs-lookup"><span data-stu-id="5cb7e-120">**My queries** — accessible only to you</span></span>
    
5. <span data-ttu-id="5cb7e-121">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="5cb7e-121">Select **Save**.</span></span> 

## <a name="delete-or-rename-a-query"></a><span data-ttu-id="5cb7e-122">Eliminare o rinominare una query</span><span class="sxs-lookup"><span data-stu-id="5cb7e-122">Delete or rename a query</span></span>
1. <span data-ttu-id="5cb7e-123">Fare clic con il pulsante destro del mouse su una query che si vuole rinominare o eliminare.</span><span class="sxs-lookup"><span data-stu-id="5cb7e-123">Right-click on a query you want to rename or delete.</span></span>

    ![Immagine dell'eliminazione di una query](../images/advanced_hunting_delete_rename.png)

2. <span data-ttu-id="5cb7e-125">Selezionare **Elimina** per confermare l'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="5cb7e-125">Select **Delete** and confirm deletion.</span></span> <span data-ttu-id="5cb7e-126">In alternativa, selezionare **Rinomina** e immettere un nuovo nome per la query.</span><span class="sxs-lookup"><span data-stu-id="5cb7e-126">Or select **Rename** and provide a new name for the query.</span></span>

## <a name="access-queries-in-the-github-repository"></a><span data-ttu-id="5cb7e-127">Accedere alle query nel repository GitHub</span><span class="sxs-lookup"><span data-stu-id="5cb7e-127">Access queries in the GitHub repository</span></span>  
<span data-ttu-id="5cb7e-128">I ricercatori della sicurezza Microsoft condividono regolarmente query di ricerca avanzata in un [repository pubblico designato in GitHub](https://github.com/microsoft/MTP-AHQ).</span><span class="sxs-lookup"><span data-stu-id="5cb7e-128">Microsoft security researchers regularly share advanced hunting queries in a [designated public repository on GitHub](https://github.com/microsoft/MTP-AHQ).</span></span> <span data-ttu-id="5cb7e-129">È possibile collaborare a questo repository.</span><span class="sxs-lookup"><span data-stu-id="5cb7e-129">This repository is open to contributions.</span></span> <span data-ttu-id="5cb7e-130">Per collaborare, [iscriversi a GitHub gratuitamente](https://github.com/).</span><span class="sxs-lookup"><span data-stu-id="5cb7e-130">To contribute, [join GitHub for free](https://github.com/).</span></span>

>[!tip]
><span data-ttu-id="5cb7e-131">I ricercatori della sicurezza Microsoft forniscono anche query di ricerca avanzata che è possibile usare per trovare le attività e gli indicatori associati alle minacce emergenti.</span><span class="sxs-lookup"><span data-stu-id="5cb7e-131">Microsoft security researchers also provide advanced hunting queries that you can use to locate activities and indicators associated with emerging threats.</span></span> <span data-ttu-id="5cb7e-132">Queste query sono incluse nei report di [analisi delle minacce](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) nel Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="5cb7e-132">These queries are provided as part of the [threat analytics](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) reports in Microsoft Defender Security Center.</span></span>

## <a name="related-topics"></a><span data-ttu-id="5cb7e-133">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="5cb7e-133">Related topics</span></span>
- [<span data-ttu-id="5cb7e-134">Ricerca proattiva delle minacce</span><span class="sxs-lookup"><span data-stu-id="5cb7e-134">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="5cb7e-135">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="5cb7e-135">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="5cb7e-136">Ricerca delle minacce su dispositivi ed e-mail</span><span class="sxs-lookup"><span data-stu-id="5cb7e-136">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="5cb7e-137">Comprensione dello schema</span><span class="sxs-lookup"><span data-stu-id="5cb7e-137">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="5cb7e-138">Applicazione delle procedure consigliate per le query</span><span class="sxs-lookup"><span data-stu-id="5cb7e-138">Apply query best practices</span></span>](advanced-hunting-best-practices.md)