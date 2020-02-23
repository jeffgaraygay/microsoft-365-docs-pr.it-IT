---
title: Azioni di correzione nelle funzionalità di analisi e risposta automatizzate in Microsoft Threat Protection
description: Panoramica delle funzionalità di indagine e reazione automatizzate in Microsoft Threat Protection
keywords: automatizzata, indagine, avviso, attivare, azione, correzione
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 65ace4bda091b3e000d25a984b706f26fe9c8696
ms.sourcegitcommit: 48b69caf6550e68cb14472ea8cfc76b53e7ae9c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42225484"
---
# <a name="remediation-actions-in-automated-investigation-and-response-capabilities-in-microsoft-threat-protection"></a><span data-ttu-id="74ab6-104">Azioni di correzione nelle funzionalità di analisi e risposta automatizzate in Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="74ab6-104">Remediation actions in automated investigation and response capabilities in Microsoft Threat Protection</span></span>

<span data-ttu-id="74ab6-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="74ab6-105">**Applies to:**</span></span>
- <span data-ttu-id="74ab6-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="74ab6-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="74ab6-107">Le funzionalità di ricerca e risposta automatizzate in Microsoft Threat Protection includono determinate azioni di correzione.</span><span class="sxs-lookup"><span data-stu-id="74ab6-107">Automated investigation and response capabilities in Microsoft Threat Protection include certain remediation actions.</span></span> <span data-ttu-id="74ab6-108">Alcuni tipi di azioni di correzione vengono eseguiti nei dispositivi, detti anche endpoint.</span><span class="sxs-lookup"><span data-stu-id="74ab6-108">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="74ab6-109">Altre azioni di correzione vengono eseguite sul contenuto della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="74ab6-109">Other remediation actions are taken on email content.</span></span>

<span data-ttu-id="74ab6-110">Nella tabella seguente sono riepilogate le azioni di correzione attualmente supportate in Microsoft Threat Protection:</span><span class="sxs-lookup"><span data-stu-id="74ab6-110">The following table summarizes remediation actions that are currently supported in Microsoft Threat Protection:</span></span> 

|<span data-ttu-id="74ab6-111">Azioni correttive degli endpoint</span><span class="sxs-lookup"><span data-stu-id="74ab6-111">Endpoints remediation actions</span></span>  |<span data-ttu-id="74ab6-112">Azioni correttive della posta elettronica</span><span class="sxs-lookup"><span data-stu-id="74ab6-112">Email remediation actions</span></span>  |
|---------|---------|
|<span data-ttu-id="74ab6-113">Quarantena del file</span><span class="sxs-lookup"><span data-stu-id="74ab6-113">Quarantine file</span></span><br/><span data-ttu-id="74ab6-114">Rimozione della chiave del Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="74ab6-114">Remove registry key</span></span><br/><span data-ttu-id="74ab6-115">Termine del processo</span><span class="sxs-lookup"><span data-stu-id="74ab6-115">Kill process</span></span> <br/><span data-ttu-id="74ab6-116">Interruzione del servizio</span><span class="sxs-lookup"><span data-stu-id="74ab6-116">Stop service</span></span> <br/><span data-ttu-id="74ab6-117">Disabilitazione del driver</span><span class="sxs-lookup"><span data-stu-id="74ab6-117">Disable driver</span></span> <br/><span data-ttu-id="74ab6-118">Rimozione di attività pianificate</span><span class="sxs-lookup"><span data-stu-id="74ab6-118">Remove scheduled task</span></span>      |<span data-ttu-id="74ab6-119">Eliminazione temporanea di messaggi di posta elettronica o cluster</span><span class="sxs-lookup"><span data-stu-id="74ab6-119">Soft delete email messages or clusters</span></span><br/><span data-ttu-id="74ab6-120">Blocco di URL (al momento del clic)</span><span class="sxs-lookup"><span data-stu-id="74ab6-120">Block URL (time-of-click)</span></span><br/><span data-ttu-id="74ab6-121">Disattivazione dell'inoltro della posta elettronica esterna</span><span class="sxs-lookup"><span data-stu-id="74ab6-121">Turn off external mail forwarding</span></span>          |

<span data-ttu-id="74ab6-122">Le azioni di correzione, sia che siano in attesa di approvazione o che sono già complete, possono essere visualizzate nel [Centro azioni](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span><span class="sxs-lookup"><span data-stu-id="74ab6-122">Remediation actions, whether they're pending approval or are already complete, can be viewed in the [Action Center](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span></span>

## <a name="next-steps"></a><span data-ttu-id="74ab6-123">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="74ab6-123">Next steps</span></span>

- [<span data-ttu-id="74ab6-124">Approvare o rifiutare le azioni relative all'indagine e reazione automatizzate</span><span class="sxs-lookup"><span data-stu-id="74ab6-124">Approve or reject actions related to automated investigation and response</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)
- [<span data-ttu-id="74ab6-125">Altre informazioni sul centro notifiche</span><span class="sxs-lookup"><span data-stu-id="74ab6-125">Learn more about the Action center</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)