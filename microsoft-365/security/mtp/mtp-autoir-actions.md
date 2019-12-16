---
title: Approvare o rifiutare azioni in sospeso in seguito all’indagine automatizzata
description: Utilizzare il centro notifiche per gestire le azioni relative all’analisi e alla risposta automatizzate
keywords: azione, centro, autoair, automatizzato, indagine, risposta, correzione
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 5c690d07af285b5232d383bb89071c3b64343772
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2019
ms.locfileid: "39911276"
---
# <a name="approve-or-reject-pending-actions-from-automated-investigations"></a><span data-ttu-id="4d27a-104">Approvare o rifiutare azioni in sospeso dalle indagini automatizzate</span><span class="sxs-lookup"><span data-stu-id="4d27a-104">Approve or reject pending actions from automated investigations</span></span>

<span data-ttu-id="4d27a-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="4d27a-105">**Applies to:**</span></span>
- <span data-ttu-id="4d27a-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="4d27a-106">Microsoft Threat Protection</span></span>

[!include[Prerelease information](prerelease.md)]

<span data-ttu-id="4d27a-107">Quando viene eseguita un’indagine automatizzata, può dare come risultato una o più [azioni di correzione](mtp-action-center.md#remediation-actions) che richiedono l’approvazione prima di procedere.</span><span class="sxs-lookup"><span data-stu-id="4d27a-107">When an automated investigation runs, it can result in one or more [remediation actions](mtp-action-center.md#remediation-actions) that require approval to proceed.</span></span> <span data-ttu-id="4d27a-108">Ad esempio, potrebbe essere necessario eliminare un gruppo di email o potrebbe essere necessario eliminare un file in quarantena.</span><span class="sxs-lookup"><span data-stu-id="4d27a-108">For example, a cluster of email messages might need to be deleted, or a quarantined file might need to be removed.</span></span> <span data-ttu-id="4d27a-109">È importante approvare (o rifiutare) le azioni in sospeso il prima possibile in modo che l’indagine automatizzata possa essere completata nel tempo previsto.</span><span class="sxs-lookup"><span data-stu-id="4d27a-109">It's important to approve (or reject) pending actions as soon as possible so that your automated investigations can proceed and complete in a timely manner.</span></span> 

<span data-ttu-id="4d27a-110">Le azioni in sospeso possono essere riviste e approvate usando uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="4d27a-110">Pending actions can be reviewed and approved by using one of several methods:</span></span>
- [<span data-ttu-id="4d27a-111">Utilizzare il centro notifiche</span><span class="sxs-lookup"><span data-stu-id="4d27a-111">Use the Action center</span></span>](#review-a-pending-action-in-the-action-center)
- [<span data-ttu-id="4d27a-112">Utilizzare visualizzazione dettagli indagine</span><span class="sxs-lookup"><span data-stu-id="4d27a-112">Use the investigation details view</span></span>](#review-a-pending-action-in-the-investigation-details-view)

> [!NOTE]
> <span data-ttu-id="4d27a-113">È necessario avere [autorizzazioni appropriate](mtp-action-center.md#required-permissions-for-action-center-tasks) per approvare o rifiutare azioni correttive.</span><span class="sxs-lookup"><span data-stu-id="4d27a-113">You must have [appropriate permissions](mtp-action-center.md#required-permissions-for-action-center-tasks) to approve or reject remediation actions.</span></span>

## <a name="review-a-pending-action-in-the-action-center"></a><span data-ttu-id="4d27a-114">Rivedere un'azione in sospeso nel centro notifiche</span><span class="sxs-lookup"><span data-stu-id="4d27a-114">Review a pending action in the Action center</span></span>

1. <span data-ttu-id="4d27a-115">Andare su [https://security.microsoft.com](https://security.microsoft.com) ed eseguire l’accesso.</span><span class="sxs-lookup"><span data-stu-id="4d27a-115">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in with an admin account.</span></span> 

2. <span data-ttu-id="4d27a-116">Nel riquadro di spostamento fare clic su **Centro notifiche**.</span><span class="sxs-lookup"><span data-stu-id="4d27a-116">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="4d27a-117">Nel centro notifiche, nella scheda **In sospeso**, selezionare un elemento dall’elenco.</span><span class="sxs-lookup"><span data-stu-id="4d27a-117">In the Action Center, on the **Pending** tab, select an item in the list.</span></span> 

    - <span data-ttu-id="4d27a-118">Se si seleziona un elemento nella colonna **Numero indagine**, verrà visualizzata la pagina con i dettagli sulle indagini.</span><span class="sxs-lookup"><span data-stu-id="4d27a-118">If you select an item in the **Investigation number** column, the investigation details page opens.</span></span> <span data-ttu-id="4d27a-119">In questa pagina è possibile visualizzare i risultati dell'indagine e quindi approvare o rifiutare l'azione consigliata.</span><span class="sxs-lookup"><span data-stu-id="4d27a-119">There, you can view the results of the investigation, and then either approve or reject the recommended action.</span></span>
 
    - <span data-ttu-id="4d27a-120">Se si seleziona una riga nell'elenco, verrà visualizzato un riquadro a comparsa, in cui sarà possibile vedere le informazioni su quell'elemento.</span><span class="sxs-lookup"><span data-stu-id="4d27a-120">If you select a row in the list, a flyout opens, where you can view information about that item.</span></span> <br/>![Approvare o rifiutare un’azione](../images/air-actioncenter-itemselected.png)<br/><span data-ttu-id="4d27a-122">Utilizzare i collegamenti per visualizzare un avviso associato o un’indagine e approvare o rifiutare l’azione.</span><span class="sxs-lookup"><span data-stu-id="4d27a-122">Use the links to view an associated alert or an investigation, and approve or reject the action.</span></span>

## <a name="review-a-pending-action-in-the-investigation-details-view"></a><span data-ttu-id="4d27a-123">Rivedere un'azione in sospeso nella visualizzazione dettagli indagini</span><span class="sxs-lookup"><span data-stu-id="4d27a-123">Review a pending action in the investigation details view</span></span>

![Dettagli indagine](../images/mtp-air-investdetails.png)

1. <span data-ttu-id="4d27a-125">In una pagina di [investigazione dettagli](mtp-autoir-results.md), selezionare la scheda **azioni in sospeso** (o **Azioni**). Gli elementi in attesa di approvazione sono elencati in questa scheda.</span><span class="sxs-lookup"><span data-stu-id="4d27a-125">On an [investigation details](mtp-autoir-results.md) page, select the **Pending actions** (or **Actions**) tab. Items that are pending approval are listed here.</span></span>

2. <span data-ttu-id="4d27a-126">Selezionare un elemento nella lista, quindi scegliere **Approva** o **Rifiuta**.</span><span class="sxs-lookup"><span data-stu-id="4d27a-126">Select an item in the list, and then choose **Approve** or **Reject**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="4d27a-127">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="4d27a-127">Next steps</span></span>

- [<span data-ttu-id="4d27a-128">Altre informazioni sul centro notifiche</span><span class="sxs-lookup"><span data-stu-id="4d27a-128">Learn more about the Action center</span></span>](mtp-action-center.md)
- [<span data-ttu-id="4d27a-129">Altre informazioni sugli incidenti</span><span class="sxs-lookup"><span data-stu-id="4d27a-129">Learn more about OneDrive</span></span>](incidents-overview.md)
- [<span data-ttu-id="4d27a-130">Altre informazioni sulla ricerca</span><span class="sxs-lookup"><span data-stu-id="4d27a-130">Learn about hunting</span></span>](advanced-hunting-overview.md)