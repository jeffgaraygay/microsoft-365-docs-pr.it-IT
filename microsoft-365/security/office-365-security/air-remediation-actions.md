---
title: Azioni di correzione nell'analisi e nella risposta automatizzate di Office 365
keywords: ARIA, autoIR, ATP, automatizzato, investigazione, risposta, correzione, minacce, avanzate, minacce, protezione
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Informazioni sulle azioni di correzione nelle funzionalità di analisi e risposta automatizzate in Office 365 Advanced Threat Protection Plan 2.
ms.openlocfilehash: e75ef1523247cbddcf6cb28d69a889db1de8e42f
ms.sourcegitcommit: 8876c216954b94adce9cdf493c49bd5a10190a3a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42228532"
---
# <a name="remediation-actions-following-an-automated-investigation-in-office-365"></a><span data-ttu-id="04e11-104">Azioni di correzione dopo un'analisi automatizzata in Office 365</span><span class="sxs-lookup"><span data-stu-id="04e11-104">Remediation actions following an automated investigation in Office 365</span></span>

## <a name="remediation-actions-overview"></a><span data-ttu-id="04e11-105">Panoramica delle azioni di correzione</span><span class="sxs-lookup"><span data-stu-id="04e11-105">Remediation actions overview</span></span>

<span data-ttu-id="04e11-106">[Le funzionalità di ricerca e risposta automatizzate](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) in Office 365 Advanced Threat Protection includono determinate azioni di correzione.</span><span class="sxs-lookup"><span data-stu-id="04e11-106">[Automated investigation and response capabilities](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) in Office 365 Advanced Threat Protection include certain remediation actions.</span></span> <span data-ttu-id="04e11-107">Ogni volta che un'indagine automatizzata è in esecuzione o è stata completata, in genere vengono visualizzate una o più operazioni di correzione che richiedono l'approvazione da parte del team di operazioni di sicurezza per procedere.</span><span class="sxs-lookup"><span data-stu-id="04e11-107">Whenever an automated investigation is running or has completed, you'll typically see one or more remediation actions that require approval by your security operations team to proceed.</span></span> <span data-ttu-id="04e11-108">Nella tabella seguente sono riepilogate le azioni di correzione attualmente disponibili in Office 365 Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="04e11-108">The following table summarizes remediation actions currently available in Office 365 Advanced Threat Protection.</span></span> 

|<span data-ttu-id="04e11-109">Azione</span><span class="sxs-lookup"><span data-stu-id="04e11-109">Action</span></span> | <span data-ttu-id="04e11-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="04e11-110">Description</span></span> |
|-----|-----|
|<span data-ttu-id="04e11-111">Blocco di URL (al momento del clic)</span><span class="sxs-lookup"><span data-stu-id="04e11-111">Block URL (time-of-click)</span></span> |<span data-ttu-id="04e11-112">Proteggi da messaggi di posta elettronica e documenti che contengono URL dannosi.</span><span class="sxs-lookup"><span data-stu-id="04e11-112">Protect against emails and documents that contain malicious URLs.</span></span> <span data-ttu-id="04e11-113">In questo modo è possibile bloccare i collegamenti dannosi e tutte le pagine Web correlate tramite [collegamenti sicuri](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) quando l'utente fa clic su un collegamento in un file di Office esistente o in un messaggio di posta elettronica precedente.</span><span class="sxs-lookup"><span data-stu-id="04e11-113">This enables the blocking of malicious links and any related webpages via [Safe Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) when the user clicks a link in an existing Office file or in an older email message.</span></span> |
|<span data-ttu-id="04e11-114">Elimina messaggio di posta elettronica soft</span><span class="sxs-lookup"><span data-stu-id="04e11-114">Soft delete email</span></span>  |<span data-ttu-id="04e11-115">Eliminazione temporanea di messaggi di posta elettronica specifici dalla cassetta postale di un utente</span><span class="sxs-lookup"><span data-stu-id="04e11-115">Soft delete specific email messages from a user's mailbox</span></span>|
|<span data-ttu-id="04e11-116">Cluster di posta elettronica con eliminazione morbida</span><span class="sxs-lookup"><span data-stu-id="04e11-116">Soft delete email clusters</span></span>  |<span data-ttu-id="04e11-117">Eliminare i messaggi di posta elettronica dannosi che corrispondono a una query da tutte le cassette postali degli utenti</span><span class="sxs-lookup"><span data-stu-id="04e11-117">Soft delete malicious email messages matching a query from all users' mailboxes</span></span>|
|<span data-ttu-id="04e11-118">Disattivazione dell'inoltro della posta elettronica esterna</span><span class="sxs-lookup"><span data-stu-id="04e11-118">Turn off external mail forwarding</span></span> |<span data-ttu-id="04e11-119">Rimuove la regola di inoltro dalla cassetta postale di un utente finale specifico</span><span class="sxs-lookup"><span data-stu-id="04e11-119">Removes forwarding rule from a specific end user's mailbox</span></span>|

## <a name="approve-or-reject-pending-actions"></a><span data-ttu-id="04e11-120">Approva (o rifiuta) azioni in sospeso</span><span class="sxs-lookup"><span data-stu-id="04e11-120">Approve (or reject) pending actions</span></span>

![Pagina azione indagini AEREe](../../media/air-investigationactionspage.png)

<span data-ttu-id="04e11-122">Durante la visualizzazione dei [Dettagli di un'indagine](air-view-investigation-results.md), è possibile approvare o rifiutare tutte le azioni di correzione in sospeso.</span><span class="sxs-lookup"><span data-stu-id="04e11-122">While viewing the [details of an investigation](air-view-investigation-results.md), you can approve or reject any pending remediation actions.</span></span> <span data-ttu-id="04e11-123">Si consiglia di eseguire questa operazione non appena possibile in modo che le indagini automatizzate siano state completate.</span><span class="sxs-lookup"><span data-stu-id="04e11-123">We recommend doing this as soon as possible so that your automated investigations complete.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="04e11-124">Le autorizzazioni appropriate devono essere approvate o rifiutate.</span><span class="sxs-lookup"><span data-stu-id="04e11-124">Appropriate permissions are required to approve or reject remediation actions.</span></span> <span data-ttu-id="04e11-125">Vedere le [autorizzazioni necessarie per utilizzare le funzionalità aeree](office-365-air.md#required-permissions-to-use-air-capabilities).</span><span class="sxs-lookup"><span data-stu-id="04e11-125">See [Required permissions to use AIR capabilities](office-365-air.md#required-permissions-to-use-air-capabilities).</span></span>

1. <span data-ttu-id="04e11-126">Selezionare la scheda **azioni** .</span><span class="sxs-lookup"><span data-stu-id="04e11-126">Select the **Actions** tab.</span></span>

2. <span data-ttu-id="04e11-127">Selezionare un elemento nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="04e11-127">Select an item in the list.</span></span> <span data-ttu-id="04e11-128">(Vengono attivati i pulsanti approva e rifiuta).</span><span class="sxs-lookup"><span data-stu-id="04e11-128">(This activates the Approve and Reject buttons.)</span></span>

3. <span data-ttu-id="04e11-129">Esaminare le informazioni disponibili per gli elementi selezionati e quindi approvare o rifiutare le azioni.</span><span class="sxs-lookup"><span data-stu-id="04e11-129">Review available information for the item(s) you selected, and then either approve or reject the action(s).</span></span> 
 - <span data-ttu-id="04e11-130">**Approvazione** consente di iniziare la correzione.</span><span class="sxs-lookup"><span data-stu-id="04e11-130">**Approve** allows remediation to begin.</span></span>
 - <span data-ttu-id="04e11-131">**Rifiuto** non esegue altre azioni</span><span class="sxs-lookup"><span data-stu-id="04e11-131">**Reject** takes no further action</span></span>

## <a name="related-articles"></a><span data-ttu-id="04e11-132">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="04e11-132">Related articles</span></span>

[<span data-ttu-id="04e11-133">Informazioni sull'analisi e la risposta automatizzate in Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="04e11-133">Learn about automated investigation and response in Microsoft Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)