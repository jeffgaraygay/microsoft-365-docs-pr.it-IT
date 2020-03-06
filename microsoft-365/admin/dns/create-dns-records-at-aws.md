---
title: Creare record DNS in Amazon Web Services (AWS) per Office 365
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7a2efd75-0771-4897-ba7b-082fe5bfa9da
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e altri servizi su Amazon Web Services (AWS) per Office 365.
ms.openlocfilehash: baba7bb7275303604d241166f4dc1d2af77b3f17
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/02/2020
ms.locfileid: "42351477"
---
# <a name="create-dns-records-at-amazon-web-services-aws-for-office-365"></a><span data-ttu-id="f2cb7-103">Creare record DNS in Amazon Web Services (AWS) per Office 365</span><span class="sxs-lookup"><span data-stu-id="f2cb7-103">Create DNS records at Amazon Web Services (AWS) for Office 365</span></span>

 <span data-ttu-id="f2cb7-104">Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="f2cb7-105">Se AWS è il provider di hosting DNS, seguire la procedura descritta in questo articolo per verificare il dominio e configurare i record DNS per la posta elettronica, Skype online per le aziende e così via.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-105">If AWS is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype Online for Business, and so on.</span></span>
  
<span data-ttu-id="f2cb7-106">Dopo aver aggiunto questi record in AWS, il domino sarà configurato per l'uso con i servizi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-106">After you add these records at AWS, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="f2cb7-107">Per informazioni su hosting Web e DNS per i siti Web con Office 365, vedere [Usare un sito Web pubblico con Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="f2cb7-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="f2cb7-p101">In genere l'applicazione delle modifiche al DNS richiede circa 15 minuti. A volte può tuttavia capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="f2cb7-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="f2cb7-111">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="f2cb7-111">Add a TXT record for verification</span></span>
<span data-ttu-id="f2cb7-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="f2cb7-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="f2cb7-p102">Prima di usare il proprio dominio con Office 365, è necessario dimostrare di esserne proprietari. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Office 365 che si è proprietari del dominio.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f2cb7-p103">Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="f2cb7-p104">Per iniziare, passare alla propria pagina dei domini su AWS usando [questo collegamento](https://console.aws.amazon.com/route53/home). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-p104">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="f2cb7-119">Nella pagina **risorse** selezionare **aree ospitate**.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-119">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="f2cb7-120">Nella pagina \* \* aree ospitate \* \*, nella colonna **nome dominio** , selezionare il nome del dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-120">On the \*\* Hosted Zones \*\* page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="f2cb7-121">Selezionare **Crea set di record**.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-121">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="f2cb7-122">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-122">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="f2cb7-123">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span><span class="sxs-lookup"><span data-stu-id="f2cb7-123">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="f2cb7-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span></span> 
  
    |||||||
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="f2cb7-126">**Nome**</span><span class="sxs-lookup"><span data-stu-id="f2cb7-126">**Name**</span></span> <br/> |<span data-ttu-id="f2cb7-127">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="f2cb7-127">**Type**</span></span> <br/> |<span data-ttu-id="f2cb7-128">**Alias**</span><span class="sxs-lookup"><span data-stu-id="f2cb7-128">**Alias**</span></span> <br/> |<span data-ttu-id="f2cb7-129">**TTL (Seconds)**</span><span class="sxs-lookup"><span data-stu-id="f2cb7-129">**TTL (Seconds)**</span></span> <br/> |<span data-ttu-id="f2cb7-130">**Value**</span><span class="sxs-lookup"><span data-stu-id="f2cb7-130">**Value**</span></span> <br/> |<span data-ttu-id="f2cb7-131">**Routing Policy**</span><span class="sxs-lookup"><span data-stu-id="f2cb7-131">**Routing Policy**</span></span> <br/> |
    |<span data-ttu-id="f2cb7-132">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="f2cb7-132">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="f2cb7-133">TXT - Text</span><span class="sxs-lookup"><span data-stu-id="f2cb7-133">TXT - Text</span></span>  <br/> |<span data-ttu-id="f2cb7-134">No</span><span class="sxs-lookup"><span data-stu-id="f2cb7-134">No</span></span>  <br/> |<span data-ttu-id="f2cb7-135">300</span><span class="sxs-lookup"><span data-stu-id="f2cb7-135">300</span></span>  <br/> |<span data-ttu-id="f2cb7-136">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="f2cb7-136">MS=ms *XXXXXXXX*</span></span>  <br/><span data-ttu-id="f2cb7-137">**Note:** questo è un esempio.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-137">**Note:** This is an example.</span></span> <span data-ttu-id="f2cb7-138">Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella in Office 365.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-138">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="f2cb7-139">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="f2cb7-139">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="f2cb7-140">Semplice</span><span class="sxs-lookup"><span data-stu-id="f2cb7-140">Simple</span></span>  <br/> |
   
6. <span data-ttu-id="f2cb7-141">Selezionare **Crea**.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-141">Select **Create**.</span></span>
    
7. <span data-ttu-id="f2cb7-142">Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-142">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="f2cb7-143">Una volta aggiunto il record al sito del registrar, è possibile tornare in Office 365 e chiedere di cercarlo.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-143">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="f2cb7-144">Quando Office 365 trova il record TXT corretto, il dominio è verificato.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-144">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="f2cb7-145">Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-145">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="f2cb7-146">Nella pagina **Domini** selezionare il dominio da verificare.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-146">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="f2cb7-147">Nella pagina **Configurazione** selezionare **Avvia configurazione**.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-147">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="f2cb7-148">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-148">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="f2cb7-p107">In genere l'applicazione delle modifiche al DNS richiede circa 15 minuti. A volte può tuttavia capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="f2cb7-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="f2cb7-152">Aggiungere un record MX in modo che la posta elettronica per il dominio venga recapitata in Office 365</span><span class="sxs-lookup"><span data-stu-id="f2cb7-152">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="f2cb7-153"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="f2cb7-153"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="f2cb7-154">Per iniziare, passare alla propria pagina dei domini su AWS usando [questo collegamento](https://console.aws.amazon.com/route53/home).</span><span class="sxs-lookup"><span data-stu-id="f2cb7-154">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="f2cb7-155">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-155">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="f2cb7-156">Nella pagina **risorse** selezionare **aree ospitate**.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-156">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="f2cb7-157">Nella colonna **nome dominio** della pagina **aree ospitate** selezionare il nome del dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-157">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="f2cb7-158">Selezionare **Crea set di record**.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-158">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="f2cb7-159">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-159">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="f2cb7-160">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span><span class="sxs-lookup"><span data-stu-id="f2cb7-160">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="f2cb7-161">**Nome**</span><span class="sxs-lookup"><span data-stu-id="f2cb7-161">**Name**</span></span>|<span data-ttu-id="f2cb7-162">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="f2cb7-162">**Type**</span></span>|<span data-ttu-id="f2cb7-163">**Alias**</span><span class="sxs-lookup"><span data-stu-id="f2cb7-163">**Alias**</span></span>|<span data-ttu-id="f2cb7-164">**TTL (Seconds)**</span><span class="sxs-lookup"><span data-stu-id="f2cb7-164">**TTL (Seconds)**</span></span>|<span data-ttu-id="f2cb7-165">**Value**</span><span class="sxs-lookup"><span data-stu-id="f2cb7-165">**Value**</span></span>|<span data-ttu-id="f2cb7-166">**Routing Policy**</span><span class="sxs-lookup"><span data-stu-id="f2cb7-166">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="f2cb7-167">Lasciare vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-167">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="f2cb7-168">MX - Mail exchange</span><span class="sxs-lookup"><span data-stu-id="f2cb7-168">MX - Mail exchange</span></span>  <br/> |<span data-ttu-id="f2cb7-169">No</span><span class="sxs-lookup"><span data-stu-id="f2cb7-169">No</span></span>  <br/> |<span data-ttu-id="f2cb7-170">300</span><span class="sxs-lookup"><span data-stu-id="f2cb7-170">300</span></span>  <br/> |<span data-ttu-id="f2cb7-171">0  *\<chiave-dominio\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-171">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="f2cb7-p109">0 è il valore di priorità MX. Aggiungerlo all'inizio del valore MX, separato dal resto del valore da uno spazio.  </span><span class="sxs-lookup"><span data-stu-id="f2cb7-p109">The 0 is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="f2cb7-174">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="f2cb7-174">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="f2cb7-175">**Nota:** ottenere il valore \<*domain-key*\> dall'account di Office 365.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-175">**Note:** Get your \<*domain-key*\> from your Office 365 account.</span></span> [<span data-ttu-id="f2cb7-176">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="f2cb7-176">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="f2cb7-177">Semplice</span><span class="sxs-lookup"><span data-stu-id="f2cb7-177">Simple</span></span>  <br/> |
       
    ![AWS-BP-Configure-2-1](../../media/94a71ce7-1b3b-4b1a-9ad3-9592db133075.png)
  
6. <span data-ttu-id="f2cb7-179">Selezionare **Crea**.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-179">Select **Create**.</span></span>
    
    ![AWS-BP-Configurazione-2-2](../../media/1c050c72-c04f-48d5-a8e9-44cd83ddd33e.png)
  
7. <span data-ttu-id="f2cb7-181">Se ci sono altri record MX, rimuoverli.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-181">If there are any other MX records, remove them.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="f2cb7-182">AWS archivia i record MX come un set che potrebbe contenere più record.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-182">AWS stores MX records as a set that may contain multiple records.</span></span> <span data-ttu-id="f2cb7-183">**Non selezionare** **Elimina set di record**, in quanto verranno eliminati tutti i record MX, incluso quello appena aggiunto.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-183">**DO NOT** select **Delete Record Set**, as this will delete all of your MX records, including the one you just added.</span></span> <span data-ttu-id="f2cb7-184">Seguire invece queste istruzioni.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-184">Use the following instructions instead.</span></span> 
  
    <span data-ttu-id="f2cb7-185">Per prima cosa, seleziona il set di record MX.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-185">First, select the MX record set.</span></span>
    
    ![AWS-BP-Configurazione-2-3](../../media/9d9388cb-e2d0-43b7-928c-e1d07e519c6f.png)
  
    <span data-ttu-id="f2cb7-187">Poi, nell'area **Edit Record Set**, eliminare ogni record MX obsoleto selezionando la voce nella casella **Value** e quindi premendo **CANC**.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-187">Next, in the **Edit Record Set** area, delete each obsolete MX record by selecting the entry in the **Value** box and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![AWS-BP-Configurazione-2-4](../../media/c3b0c1bc-21ab-44cc-84b7-f504725c5540.png)
  
8. <span data-ttu-id="f2cb7-189">Selezionare **Salva set di record**.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-189">Select **Save Record Set**.</span></span>
    
    ![AWS-BP-Configurazione-2-5](../../media/86f0998d-f5d4-4750-a93d-ac13b318c40b.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="f2cb7-191">Aggiungere i cinque record CNAME necessari per Office 365</span><span class="sxs-lookup"><span data-stu-id="f2cb7-191">Add the five CNAME records that are required for Office 365</span></span>
<span data-ttu-id="f2cb7-192"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="f2cb7-192"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="f2cb7-193">Per iniziare, passare alla propria pagina dei domini su AWS usando [questo collegamento](https://console.aws.amazon.com/route53/home).</span><span class="sxs-lookup"><span data-stu-id="f2cb7-193">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="f2cb7-194">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-194">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="f2cb7-195">Nella pagina **risorse** selezionare **aree ospitate**.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-195">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="f2cb7-196">Nella colonna **nome dominio** della pagina **aree ospitate** selezionare il nome del dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-196">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="f2cb7-197">Selezionare **Crea set di record**.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-197">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="f2cb7-198">Aggiungere il primo record CNAME.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-198">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="f2cb7-199">Nelle caselle del nuovo record nell'area **Create Record Set** digitare oppure copiare e incollare i valori della prima riga della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-199">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="f2cb7-200">Selezionare i valori **Type** e **Routing Policy** negli elenchi a discesa.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-200">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="f2cb7-201">**Nome**</span><span class="sxs-lookup"><span data-stu-id="f2cb7-201">**Name**</span></span>|<span data-ttu-id="f2cb7-202">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="f2cb7-202">**Type**</span></span>|<span data-ttu-id="f2cb7-203">**Alias**</span><span class="sxs-lookup"><span data-stu-id="f2cb7-203">**Alias**</span></span>|<span data-ttu-id="f2cb7-204">**TTL (Seconds)**</span><span class="sxs-lookup"><span data-stu-id="f2cb7-204">**TTL (Seconds)**</span></span>|<span data-ttu-id="f2cb7-205">**Value**</span><span class="sxs-lookup"><span data-stu-id="f2cb7-205">**Value**</span></span>|<span data-ttu-id="f2cb7-206">**Routing Policy**</span><span class="sxs-lookup"><span data-stu-id="f2cb7-206">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="f2cb7-207">autodiscover</span><span class="sxs-lookup"><span data-stu-id="f2cb7-207">autodiscover</span></span>  <br/> |<span data-ttu-id="f2cb7-208">CNAME - Canonical Name</span><span class="sxs-lookup"><span data-stu-id="f2cb7-208">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="f2cb7-209">No</span><span class="sxs-lookup"><span data-stu-id="f2cb7-209">No</span></span>  <br/> |<span data-ttu-id="f2cb7-210">300</span><span class="sxs-lookup"><span data-stu-id="f2cb7-210">300</span></span>  <br/> |<span data-ttu-id="f2cb7-211">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-211">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="f2cb7-212">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="f2cb7-212">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="f2cb7-213">Semplice</span><span class="sxs-lookup"><span data-stu-id="f2cb7-213">Simple</span></span>  <br/> |
    |<span data-ttu-id="f2cb7-214">sip</span><span class="sxs-lookup"><span data-stu-id="f2cb7-214">sip</span></span>  <br/> |<span data-ttu-id="f2cb7-215">CNAME - Canonical Name</span><span class="sxs-lookup"><span data-stu-id="f2cb7-215">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="f2cb7-216">No</span><span class="sxs-lookup"><span data-stu-id="f2cb7-216">No</span></span>  <br/> |<span data-ttu-id="f2cb7-217">300</span><span class="sxs-lookup"><span data-stu-id="f2cb7-217">300</span></span>  <br/> |<span data-ttu-id="f2cb7-218">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-218">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="f2cb7-219">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="f2cb7-219">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="f2cb7-220">Semplice</span><span class="sxs-lookup"><span data-stu-id="f2cb7-220">Simple</span></span>  <br/> |
    |<span data-ttu-id="f2cb7-221">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="f2cb7-221">lyncdiscover</span></span>  <br/> |<span data-ttu-id="f2cb7-222">CNAME - Canonical Name</span><span class="sxs-lookup"><span data-stu-id="f2cb7-222">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="f2cb7-223">No</span><span class="sxs-lookup"><span data-stu-id="f2cb7-223">No</span></span>  <br/> |<span data-ttu-id="f2cb7-224">300</span><span class="sxs-lookup"><span data-stu-id="f2cb7-224">300</span></span>  <br/> |<span data-ttu-id="f2cb7-225">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-225">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="f2cb7-226">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="f2cb7-226">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="f2cb7-227">Semplice</span><span class="sxs-lookup"><span data-stu-id="f2cb7-227">Simple</span></span>  <br/> |
    |<span data-ttu-id="f2cb7-228">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="f2cb7-228">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="f2cb7-229">CNAME - Canonical Name</span><span class="sxs-lookup"><span data-stu-id="f2cb7-229">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="f2cb7-230">No</span><span class="sxs-lookup"><span data-stu-id="f2cb7-230">No</span></span>  <br/> |<span data-ttu-id="f2cb7-231">300</span><span class="sxs-lookup"><span data-stu-id="f2cb7-231">300</span></span>  <br/> |<span data-ttu-id="f2cb7-232">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-232">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="f2cb7-233">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="f2cb7-233">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="f2cb7-234">Semplice</span><span class="sxs-lookup"><span data-stu-id="f2cb7-234">Simple</span></span>  <br/> |
    |<span data-ttu-id="f2cb7-235">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="f2cb7-235">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="f2cb7-236">CNAME - Canonical Name</span><span class="sxs-lookup"><span data-stu-id="f2cb7-236">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="f2cb7-237">No</span><span class="sxs-lookup"><span data-stu-id="f2cb7-237">No</span></span>  <br/> |<span data-ttu-id="f2cb7-238">300</span><span class="sxs-lookup"><span data-stu-id="f2cb7-238">300</span></span>  <br/> |<span data-ttu-id="f2cb7-239">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-239">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="f2cb7-240">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="f2cb7-240">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="f2cb7-241">Semplice</span><span class="sxs-lookup"><span data-stu-id="f2cb7-241">Simple</span></span>  <br/> |
   
    ![AWS-BP-configure-3-1](../../media/895c71bd-0e3a-425e-9681-98c1c67e714b.png)
  
6. <span data-ttu-id="f2cb7-243">Selezionare **Crea**.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-243">Select **Create**.</span></span>
    
    ![AWS-BP-Configurazione-3-2](../../media/33964846-5282-44a4-b241-62ce02b96735.png)
  
7. <span data-ttu-id="f2cb7-245">Aggiungere gli altri quattro record CNAME.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-245">Add the other four CNAME records.</span></span>
    
    <span data-ttu-id="f2cb7-246">Nella pagina **aree ospitate** , selezionare **Crea record set**, creare un record usando i valori della riga successiva della tabella e quindi fare di nuovo clic su **Crea** per completare il record.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-246">In the **Hosted Zones** page, select **Create Record Set**, create a record using the values from the next row in the table, and then again select **Create** to complete that record.</span></span> 
    
    <span data-ttu-id="f2cb7-247">Ripetere questa procedura fino a creare tutti e cinque i record CNAME.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-247">Repeat this process until you have created all five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="f2cb7-248">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="f2cb7-248">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="f2cb7-249"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="f2cb7-249"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="f2cb7-250">Non può essere presente più di un record TXT per SPF per un dominio.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-250">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="f2cb7-251">Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-251">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="f2cb7-252">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-252">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="f2cb7-253">Al contrario, aggiungere i valori di Office 365 richiesti al record corrente in modo da ottenere un *unico* record SPF che include entrambi i set di valori.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-253">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="f2cb7-254">Servono esempi?</span><span class="sxs-lookup"><span data-stu-id="f2cb7-254">Need examples?</span></span> <span data-ttu-id="f2cb7-255">Vedere queste [informazioni dettagliate e record SPF di esempio](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span><span class="sxs-lookup"><span data-stu-id="f2cb7-255">Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span></span> <span data-ttu-id="f2cb7-256">Per convalidare il record SPF, è possibile utilizzare uno di questi[strumenti di convalida SPF](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="f2cb7-256">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="f2cb7-257">Per iniziare, passare alla propria pagina dei domini su AWS usando [questo collegamento](https://console.aws.amazon.com/route53/home).</span><span class="sxs-lookup"><span data-stu-id="f2cb7-257">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="f2cb7-258">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-258">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="f2cb7-259">Nella pagina **risorse** selezionare **aree ospitate**.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-259">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="f2cb7-260">Nella colonna **nome dominio** della pagina **aree ospitate** selezionare il nome del dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-260">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="f2cb7-261">Selezionare il set di record **txt** .</span><span class="sxs-lookup"><span data-stu-id="f2cb7-261">Select the **TXT** record set.</span></span> 
    
    ![AWS-BP-Configurazione-4-1](../../media/0310fa66-c016-4987-80df-930f1c8f3c39.png)
  
5. <span data-ttu-id="f2cb7-p115">Nell'area **Edit Record Set**, alla fine della voce corrente nella casella **Value** per il record esistente, premere INVIO per creare una nuova riga. Quindi, in questa nuova riga, sotto il valore esistente, digitare o incollare il valore della tabella seguente. Per un esempio, vedere la figura sotto la tabella.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-p115">In the **Edit Record Set** area, at the end of the current entry in the **Value:** box for the existing record, press Enter on your keyboard to create a new line; and then, on that new line (under the existing value), type or copy and paste the value from the following table. (You can see an example in the illustration below the table.)</span></span> 
    
    |<span data-ttu-id="f2cb7-265">**Value:**</span><span class="sxs-lookup"><span data-stu-id="f2cb7-265">**Value:**</span></span>|
    |:-----|
    |<span data-ttu-id="f2cb7-266">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="f2cb7-266">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="f2cb7-p116">Le virgolette richieste dalle istruzioni visualizzate vengono specificate automaticamente. Non è necessario digitarle manualmente.  </span><span class="sxs-lookup"><span data-stu-id="f2cb7-p116">(The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.)  </span></span><br/> <span data-ttu-id="f2cb7-269">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-269">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![AWS-BP-Configure-4-2](../../media/beb3c086-eaf8-4245-9860-18512a3ff72e.png)
  
6. <span data-ttu-id="f2cb7-271">Selezionare **Salva set di record**.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-271">Select **Save Record Set**.</span></span>
    
    ![AWS-BP-Configurazione-4-3](../../media/94b9306c-bdc9-4f84-ad6f-6d12edbfde90.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="f2cb7-273">Aggiungere i due record SRV necessari per Office 365</span><span class="sxs-lookup"><span data-stu-id="f2cb7-273">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="f2cb7-274"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="f2cb7-274"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="f2cb7-275">Per iniziare, passare alla propria pagina dei domini su AWS usando [questo collegamento](https://console.aws.amazon.com/route53/home).</span><span class="sxs-lookup"><span data-stu-id="f2cb7-275">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="f2cb7-276">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-276">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="f2cb7-277">Nella pagina **risorse** selezionare **aree ospitate**.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-277">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="f2cb7-278">Nella colonna **nome dominio** della pagina **aree ospitate** selezionare il nome del dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-278">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="f2cb7-279">Selezionare **Crea set di record**.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-279">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="f2cb7-280">Aggiungere il primo record SRV:</span><span class="sxs-lookup"><span data-stu-id="f2cb7-280">Add the first SRV record:</span></span>
    
    <span data-ttu-id="f2cb7-281">Nelle caselle del nuovo record nell'area **Create Record Set** digitare oppure copiare e incollare i valori della prima riga della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-281">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="f2cb7-282">Selezionare i valori **Type** e **Routing Policy** negli elenchi a discesa.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-282">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="f2cb7-283">**Nome**</span><span class="sxs-lookup"><span data-stu-id="f2cb7-283">**Name**</span></span>|<span data-ttu-id="f2cb7-284">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="f2cb7-284">**Type**</span></span>|<span data-ttu-id="f2cb7-285">**Alias**</span><span class="sxs-lookup"><span data-stu-id="f2cb7-285">**Alias**</span></span>|<span data-ttu-id="f2cb7-286">**TTL (Seconds)**</span><span class="sxs-lookup"><span data-stu-id="f2cb7-286">**TTL (Seconds)**</span></span>|<span data-ttu-id="f2cb7-287">**Value**</span><span class="sxs-lookup"><span data-stu-id="f2cb7-287">**Value**</span></span>|<span data-ttu-id="f2cb7-288">**Routing Policy**</span><span class="sxs-lookup"><span data-stu-id="f2cb7-288">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="f2cb7-289">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="f2cb7-289">_sip._tls</span></span>|<span data-ttu-id="f2cb7-290">SRV - Service locator</span><span class="sxs-lookup"><span data-stu-id="f2cb7-290">SRV - Service locator</span></span>|<span data-ttu-id="f2cb7-291">No</span><span class="sxs-lookup"><span data-stu-id="f2cb7-291">No</span></span>|<span data-ttu-id="f2cb7-292">300</span><span class="sxs-lookup"><span data-stu-id="f2cb7-292">300</span></span>|<span data-ttu-id="f2cb7-293">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-293">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="f2cb7-294">**Questo valore deve terminare con un punto (.).**></span><span class="sxs-lookup"><span data-stu-id="f2cb7-294">**This value MUST end with a period (.)**></span></span><br> <span data-ttu-id="f2cb7-295">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-295">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="f2cb7-296">Semplice</span><span class="sxs-lookup"><span data-stu-id="f2cb7-296">Simple</span></span>|
    |<span data-ttu-id="f2cb7-297">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="f2cb7-297">_sipfederationtls._tcp</span></span>|<span data-ttu-id="f2cb7-298">SRV - Service locator</span><span class="sxs-lookup"><span data-stu-id="f2cb7-298">SRV - Service locator</span></span>|<span data-ttu-id="f2cb7-299">No</span><span class="sxs-lookup"><span data-stu-id="f2cb7-299">No</span></span>|<span data-ttu-id="f2cb7-300">300</span><span class="sxs-lookup"><span data-stu-id="f2cb7-300">300</span></span>|<span data-ttu-id="f2cb7-301">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-301">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="f2cb7-302">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="f2cb7-302">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="f2cb7-303">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-303">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="f2cb7-304">Semplice</span><span class="sxs-lookup"><span data-stu-id="f2cb7-304">Simple</span></span>|
   
    ![AWS-BP-Configure-5-1](../../media/c3f841d3-6076-428f-bb04-e71cc5f392fa.png)
  
6. <span data-ttu-id="f2cb7-306">Selezionare **Crea**.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-306">Select **Create**.</span></span>
    
    ![AWS-BP-Configurazione-5-2](../../media/1bf5dc58-a46b-47a5-bd69-7c2147dd4e50.png)
  
7. <span data-ttu-id="f2cb7-308">Per aggiungere l'altro record SRV:</span><span class="sxs-lookup"><span data-stu-id="f2cb7-308">To add the other SRV record:</span></span>
    
    <span data-ttu-id="f2cb7-309">Nella pagina **aree ospitate** , selezionare **Crea record set**, creare un record usando i valori della riga successiva della tabella e quindi fare di nuovo clic su **Crea** per completare il record.</span><span class="sxs-lookup"><span data-stu-id="f2cb7-309">In the **Hosted Zones** page, select **Create Record Set**, create a record using the values from the next row in the table, and then again select **Create** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="f2cb7-p120">In genere l'applicazione delle modifiche al DNS richiede circa 15 minuti. A volte può tuttavia capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="f2cb7-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  