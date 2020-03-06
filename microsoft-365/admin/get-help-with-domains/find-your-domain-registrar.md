---
title: Trovare il proprio registrar per Office 365
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: b5b633ba-1e56-4a98-8ff5-2acaac63a5c8
description: Informazioni su come trovare il registrar e il provider di hosting DNS usando la ricerca di InterNIC.
ms.openlocfilehash: 058eb4468e073b6929fbc763b3d9bdb189063213
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/24/2020
ms.locfileid: "42252955"
---
# <a name="find-your-domain-registrar-for-office-365"></a><span data-ttu-id="3df30-103">Trovare il proprio registrar per Office 365</span><span class="sxs-lookup"><span data-stu-id="3df30-103">Find your domain registrar for Office 365</span></span>

 <span data-ttu-id="3df30-104">Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="3df30-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
## <a name="domain-registrar"></a><span data-ttu-id="3df30-105">Registrar per i domini</span><span class="sxs-lookup"><span data-stu-id="3df30-105">Domain registrar</span></span>
  
### <a name="find-your-domain-name-registrar"></a><span data-ttu-id="3df30-106">Trovare il proprio registrar</span><span class="sxs-lookup"><span data-stu-id="3df30-106">Find your domain name registrar</span></span>

>[!NOTE]
> <span data-ttu-id="3df30-107">Solo i domini che terminano con *.COM*, *.NET* e *.EDU* funzionano con questo strumento.</span><span class="sxs-lookup"><span data-stu-id="3df30-107">Only domains ending in *.COM*, *.NET*, and *.EDU* work with this tool.</span></span>
  
1. <span data-ttu-id="3df30-108">Nella [pagina di ricerca di InterNIC](https://go.microsoft.com/fwlink/p/?LinkId=402770), nella casella **Whois Search**, digitare il nome del dominio.</span><span class="sxs-lookup"><span data-stu-id="3df30-108">On the [InterNIC search page](https://go.microsoft.com/fwlink/p/?LinkId=402770), in the **Whois Search** box, type your domain.</span></span> <span data-ttu-id="3df30-109">Ad esempio, *contoso.com*.</span><span class="sxs-lookup"><span data-stu-id="3df30-109">For example,  *contoso.com.*</span></span> 
    
2. <span data-ttu-id="3df30-110">Selezionare l'opzione **Domain**, quindi selezionare **Submit**.</span><span class="sxs-lookup"><span data-stu-id="3df30-110">Select the **Domain** option, and then select **Submit**.</span></span>
    
3. <span data-ttu-id="3df30-111">Nella pagina **Whois Search Results** individuare la prima voce **Registrar**.</span><span class="sxs-lookup"><span data-stu-id="3df30-111">On the **Whois Search Results** page, locate the **Registrar** entry.</span></span> <span data-ttu-id="3df30-112">In questa voce è indicata l'organizzazione che fornisce il servizio di registrar per il dominio.</span><span class="sxs-lookup"><span data-stu-id="3df30-112">This entry lists the organization that provides registrar service for your domain.</span></span> 
    
## <a name="dns-hosting-provider"></a><span data-ttu-id="3df30-113">Provider di hosting DNS</span><span class="sxs-lookup"><span data-stu-id="3df30-113">DNS hosting provider</span></span>
  
### <a name="find-your-dns-hosting-provider"></a><span data-ttu-id="3df30-114">Trovare il provider di hosting DNS</span><span class="sxs-lookup"><span data-stu-id="3df30-114">Find your DNS hosting provider</span></span>

>[!NOTE]
> <span data-ttu-id="3df30-115">Solo i domini che terminano con *.COM*, *.NET* e *.EDU* funzionano con questo strumento.</span><span class="sxs-lookup"><span data-stu-id="3df30-115">Only domains ending in *.COM*, *.NET*, and *.EDU* work with this tool.</span></span>
  
1. <span data-ttu-id="3df30-116">Nella [pagina di ricerca di InterNIC]( https://go.microsoft.com/fwlink/p/?LinkId=402770), nella casella **Whois Search**, digitare il nome del dominio.</span><span class="sxs-lookup"><span data-stu-id="3df30-116">On the [InterNIC search page]( https://go.microsoft.com/fwlink/p/?LinkId=402770), in the **Whois Search** box, type your domain.</span></span> <span data-ttu-id="3df30-117">Ad esempio, contoso.com.</span><span class="sxs-lookup"><span data-stu-id="3df30-117">For example, contoso.com.</span></span> 
    
2. <span data-ttu-id="3df30-118">Selezionare l'opzione **Domain**, quindi selezionare **Submit**.</span><span class="sxs-lookup"><span data-stu-id="3df30-118">Select the **Domain** option, and then select **Submit**.</span></span>
    
3. <span data-ttu-id="3df30-119">Nella pagina **Whois Search Results** individuare la prima voce **Name Server**.</span><span class="sxs-lookup"><span data-stu-id="3df30-119">On the **Whois Search Results** page, locate the first **Name Server** entry.</span></span> 
    
4. <span data-ttu-id="3df30-120">Copiare le informazioni relative al server dei nomi che vengono visualizzate dopo i due punti (:), quindi incollarle nella casella **Search** nella parte superiore della pagina.</span><span class="sxs-lookup"><span data-stu-id="3df30-120">Copy the name server (NS) information that appears after the colon (:), and then paste it into the **Search** box at the top of the page.</span></span> <span data-ttu-id="3df30-121">Selezionare **Nameserver**, quindi selezionare **Submit**.</span><span class="sxs-lookup"><span data-stu-id="3df30-121">Select **Nameserver**, and then select **Submit**.</span></span>
    
5. <span data-ttu-id="3df30-p105">Nella pagina **Whois Search Results** individuare la voce **Registrar**. In questa voce è indicato il provider di hosting DNS, ovvero il provider DNS proprietario del server dei nomi per il dominio.</span><span class="sxs-lookup"><span data-stu-id="3df30-p105">On the **Whois Search Results** page, locate the **Registrar** entry. This entry lists your DNS hosting provider, the DNS provider who owns the name server for your domain.</span></span> 
    
---
