---
title: Creare record DNS su Bluehost per Office 365
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
ms.assetid: 657934ff-d9d2-4563-9ccf-ef4832a03a99
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e altri servizi di Bluehost per Office 365.
ms.openlocfilehash: 0e64ed8787dca9822e71a63c57de7a7a3e2b3fe4
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/02/2020
ms.locfileid: "42350957"
---
# <a name="create-dns-records-at-bluehost-for-office-365"></a><span data-ttu-id="21351-103">Creare record DNS su Bluehost per Office 365</span><span class="sxs-lookup"><span data-stu-id="21351-103">Create DNS records at Bluehost for Office 365</span></span>

 <span data-ttu-id="21351-104">**Se non si trova ciò che si sta cercando, [vedere le domande frequenti sui domini](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="21351-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="21351-105">Se il proprio provider di hosting DNS è Bluehost, seguire i passaggi di questo articolo per verificare il dominio e configurare i record DNS per la posta elettronica, Skype for Business online e così via.</span><span class="sxs-lookup"><span data-stu-id="21351-105">If Bluehost is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="21351-106">Dopo aver aggiunto questi record in Bluehost, il domino sarà configurato per l'uso con i servizi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="21351-106">After you add these records at Bluehost, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="21351-107">Per informazioni su hosting Web e DNS per i siti Web con Office 365, vedere [Usare un sito Web pubblico con Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="21351-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="21351-p101">In genere l'applicazione delle modifiche al DNS richiede circa 15 minuti. A volte può tuttavia capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="21351-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="21351-111">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="21351-111">Add a TXT record for verification</span></span>
<span data-ttu-id="21351-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="21351-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="21351-p102">Prima di usare il proprio dominio con Office 365, è necessario dimostrare di esserne proprietari. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Office 365 che si è proprietari del dominio.</span><span class="sxs-lookup"><span data-stu-id="21351-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="21351-p103">Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="21351-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="21351-117">Per iniziare, passare alla propria pagina dei domini su Bluehost usando [questo collegamento](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="21351-117">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="21351-118">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="21351-118">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="21351-119">Nell'area **domain** della pagina **Domains** trovare la riga relativa al dominio da modificare e quindi selezionare la casella di controllo corrispondente.</span><span class="sxs-lookup"><span data-stu-id="21351-119">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="21351-120">Può essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="21351-120">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="21351-121">Nell'area ***Domain_name*** , nella riga **Editor zone DNS** , selezionare **Manage DNS Records**.</span><span class="sxs-lookup"><span data-stu-id="21351-121">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="21351-122">Nella pagina \* \* DNS zone editor \* \*, nell'area **Aggiungi record DNS** , nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="21351-122">On the \*\* DNS Zone Editor \*\* page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="21351-123">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="21351-123">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="21351-124">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="21351-124">**Host Record**</span></span> <br/> |<span data-ttu-id="21351-125">**TTL**</span><span class="sxs-lookup"><span data-stu-id="21351-125">**TTL**</span></span> <br/> |<span data-ttu-id="21351-126">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="21351-126">**Type**</span></span> <br/> |<span data-ttu-id="21351-127">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="21351-127">**TXT Value**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="21351-128">14400</span><span class="sxs-lookup"><span data-stu-id="21351-128">14400</span></span>  <br/> |<span data-ttu-id="21351-129">TXT</span><span class="sxs-lookup"><span data-stu-id="21351-129">TXT</span></span>  <br/> |<span data-ttu-id="21351-130">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="21351-130">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="21351-131">**Note:** questo è un esempio.</span><span class="sxs-lookup"><span data-stu-id="21351-131">**Note:** This is an example.</span></span> <span data-ttu-id="21351-132">Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella in Office 365.</span><span class="sxs-lookup"><span data-stu-id="21351-132">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="21351-133">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="21351-133">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
5. <span data-ttu-id="21351-134">Selezionare **Aggiungi record**.</span><span class="sxs-lookup"><span data-stu-id="21351-134">Select **add record**.</span></span>
    
6. <span data-ttu-id="21351-135">Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.</span><span class="sxs-lookup"><span data-stu-id="21351-135">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="21351-136">Una volta aggiunto il record al sito del registrar, è possibile tornare in Office 365 e chiedere di cercarlo.</span><span class="sxs-lookup"><span data-stu-id="21351-136">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="21351-137">Quando Office 365 trova il record TXT corretto, il dominio è verificato.</span><span class="sxs-lookup"><span data-stu-id="21351-137">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="21351-138">Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="21351-138">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="21351-139">Nella pagina **Domini** selezionare il dominio da verificare.</span><span class="sxs-lookup"><span data-stu-id="21351-139">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="21351-140">Nella pagina **Configurazione** selezionare **Avvia configurazione**.</span><span class="sxs-lookup"><span data-stu-id="21351-140">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="21351-141">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="21351-141">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="21351-p106">In genere l'applicazione delle modifiche al DNS richiede circa 15 minuti. A volte può tuttavia capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="21351-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="21351-145">Aggiungere un record MX in modo che la posta elettronica per il dominio venga recapitata in Office 365</span><span class="sxs-lookup"><span data-stu-id="21351-145">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="21351-146"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="21351-146"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="21351-147">Per iniziare, passare alla propria pagina dei domini su Bluehost usando [questo collegamento](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="21351-147">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="21351-148">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="21351-148">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="21351-149">Nell'area **domain** della pagina **Domains** trovare la riga relativa al dominio da modificare e quindi selezionare la casella di controllo corrispondente.</span><span class="sxs-lookup"><span data-stu-id="21351-149">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="21351-150">Può essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="21351-150">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="21351-151">Nell'area ***Domain_name*** , nella riga **Editor zone DNS** , selezionare **Manage DNS Records**.</span><span class="sxs-lookup"><span data-stu-id="21351-151">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="21351-152">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="21351-152">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="21351-153">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="21351-153">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="21351-154">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="21351-154">**Host Record**</span></span>|<span data-ttu-id="21351-155">**TTL**</span><span class="sxs-lookup"><span data-stu-id="21351-155">**TTL**</span></span>|<span data-ttu-id="21351-156">**Type**</span><span class="sxs-lookup"><span data-stu-id="21351-156">**Type**</span></span>|<span data-ttu-id="21351-157">**Points To**</span><span class="sxs-lookup"><span data-stu-id="21351-157">**Points To**</span></span>|<span data-ttu-id="21351-158">**Priority**</span><span class="sxs-lookup"><span data-stu-id="21351-158">**Priority**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="21351-159">14400</span><span class="sxs-lookup"><span data-stu-id="21351-159">14400</span></span>  <br/> |<span data-ttu-id="21351-160">MX</span><span class="sxs-lookup"><span data-stu-id="21351-160">MX</span></span>  <br/> | <span data-ttu-id="21351-161">*\<chiave-dominio\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="21351-161">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/><span data-ttu-id="21351-162">**Nota:** ottenere il valore \<*domain-key*\> dall'account di Office 365.</span><span class="sxs-lookup"><span data-stu-id="21351-162">**Note:** Get your \<*domain-key*\> from your Office 365 account.</span></span> [<span data-ttu-id="21351-163">Come trovarla</span><span class="sxs-lookup"><span data-stu-id="21351-163">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="21351-164">0</span><span class="sxs-lookup"><span data-stu-id="21351-164">0</span></span>  <br/> <span data-ttu-id="21351-165">Per altre informazioni sulla priorità, vedere [Informazioni sulla priorità MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx).</span><span class="sxs-lookup"><span data-stu-id="21351-165">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
   
   ![Scegliere tipo dall'elenco a discesa](../../media/70791420-d83c-4a5d-a46c-5cc3bc67f565.png)
  
5. <span data-ttu-id="21351-167">Selezionare **Aggiungi record**.</span><span class="sxs-lookup"><span data-stu-id="21351-167">Select **add record**.</span></span>
    
    ![Selezionare Aggiungi record](../../media/c7ef9733-1665-4dbf-accc-caadf1574abc.png)
  
6. <span data-ttu-id="21351-169">Rimuovere eventuali altri record MX presenti nella sezione **MX (Mail Exchanger)**.</span><span class="sxs-lookup"><span data-stu-id="21351-169">If there are any other MX records in the **MX (Mail Exchanger)** section, delete each of them.</span></span> 
    
    <span data-ttu-id="21351-170">Per uno degli altri record MX, selezionare **Elimina.**</span><span class="sxs-lookup"><span data-stu-id="21351-170">For one of the other MX records, select **Delete.**</span></span>
    
    ![Selezionare Elimina per ogni record MX aggiuntivo](../../media/6be17f54-3f33-47af-a9db-4689141530c2.png)
  
7. <span data-ttu-id="21351-172">Nella finestra di dialogo di conferma fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="21351-172">In the confirmation dialog box, select **OK**.</span></span>
    
    ![Seleziona OK](../../media/a50df7a3-2906-4cc0-87d4-1231ab234230.png)
  
8. <span data-ttu-id="21351-174">Usare la stessa procedura per eliminare eventuali altri record MX già presenti nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="21351-174">Use the same process to delete any other MX records that were already listed.</span></span>
    
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="21351-175">Aggiungere i sei record CNAME necessari per Office 365</span><span class="sxs-lookup"><span data-stu-id="21351-175">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="21351-176"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="21351-176"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="21351-177">Per iniziare, passare alla propria pagina dei domini su Bluehost usando [questo collegamento](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="21351-177">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="21351-178">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="21351-178">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="21351-179">Nell'area **domain** della pagina **Domains** trovare la riga relativa al dominio da modificare e quindi selezionare la casella di controllo corrispondente.</span><span class="sxs-lookup"><span data-stu-id="21351-179">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="21351-180">Può essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="21351-180">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="21351-181">Nell'area ***Domain_name*** , nella riga **Editor zone DNS** , selezionare **Manage DNS Records**.</span><span class="sxs-lookup"><span data-stu-id="21351-181">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="21351-182">Nella sezione **a (host)** Records individuare la riga del record di **individuazione automatica** e quindi fare clic su **Elimina** per tale riga.</span><span class="sxs-lookup"><span data-stu-id="21351-182">In the **A (Host)** records section, find the row for the **autodiscover** record, and then select **delete** for that row.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="21351-p110">È necessario eliminare il record **autodiscover** esistente  *prima*  di aggiungere il record **autodiscover** richiesto da Office 365. Bluehost non consente di mantenere due record **autodiscover** contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="21351-p110">You must delete the existing **autodiscover** record  *before*  adding the **autodiscover** record that is required by Office 365. Bluehost does not allow you to maintain two **autodiscover** records simultaneously.</span></span> 
  
    ![Seleziona Elimina](../../media/416a447e-3710-4ae7-8bf1-459381af4f6e.png)
  
5. <span data-ttu-id="21351-186">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="21351-186">Select **OK**.</span></span>
    
    ![Seleziona OK](../../media/0c8f409d-c39f-4ed2-9c95-9af3e61c2411.png)
  
6. <span data-ttu-id="21351-188">Creare il primo dei sei record CNAME.</span><span class="sxs-lookup"><span data-stu-id="21351-188">Create the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="21351-189">Nella pagina **DNS Zone Editor** digitare oppure copiare e incollare i valori della prima riga della tabella seguente nelle caselle del nuovo record nell'area **Add DNS Record**.</span><span class="sxs-lookup"><span data-stu-id="21351-189">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="21351-190">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="21351-190">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="21351-191">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="21351-191">**Host Record**</span></span>|<span data-ttu-id="21351-192">**TTL**</span><span class="sxs-lookup"><span data-stu-id="21351-192">**TTL**</span></span>|<span data-ttu-id="21351-193">**Type**</span><span class="sxs-lookup"><span data-stu-id="21351-193">**Type**</span></span>|<span data-ttu-id="21351-194">**Points To**</span><span class="sxs-lookup"><span data-stu-id="21351-194">**Points To**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="21351-195">autodiscover</span><span class="sxs-lookup"><span data-stu-id="21351-195">autodiscover</span></span>  <br/> |<span data-ttu-id="21351-196">14400</span><span class="sxs-lookup"><span data-stu-id="21351-196">14400</span></span>  <br/> |<span data-ttu-id="21351-197">CNAME</span><span class="sxs-lookup"><span data-stu-id="21351-197">CNAME</span></span>  <br/> |<span data-ttu-id="21351-198">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="21351-198">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="21351-199">sip</span><span class="sxs-lookup"><span data-stu-id="21351-199">sip</span></span>  <br/> |<span data-ttu-id="21351-200">14400</span><span class="sxs-lookup"><span data-stu-id="21351-200">14400</span></span>  <br/> |<span data-ttu-id="21351-201">CNAME</span><span class="sxs-lookup"><span data-stu-id="21351-201">CNAME</span></span>  <br/> |<span data-ttu-id="21351-202">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="21351-202">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="21351-203">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="21351-203">lyncdiscover</span></span>  <br/> |<span data-ttu-id="21351-204">14400</span><span class="sxs-lookup"><span data-stu-id="21351-204">14400</span></span>  <br/> |<span data-ttu-id="21351-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="21351-205">CNAME</span></span>  <br/> |<span data-ttu-id="21351-206">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="21351-206">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="21351-207">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="21351-207">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="21351-208">14400</span><span class="sxs-lookup"><span data-stu-id="21351-208">14400</span></span>  <br/> |<span data-ttu-id="21351-209">CNAME</span><span class="sxs-lookup"><span data-stu-id="21351-209">CNAME</span></span>  <br/> |<span data-ttu-id="21351-210">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="21351-210">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="21351-211">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="21351-211">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="21351-212">14400</span><span class="sxs-lookup"><span data-stu-id="21351-212">14400</span></span>  <br/> |<span data-ttu-id="21351-213">CNAME</span><span class="sxs-lookup"><span data-stu-id="21351-213">CNAME</span></span>  <br/> |<span data-ttu-id="21351-214">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="21351-214">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Creare il primo record CNAME](../../media/4f12e9b1-9dec-4bc2-aa15-8bffa71fe131.png)
  
7. <span data-ttu-id="21351-216">Selezionare **Aggiungi record**.</span><span class="sxs-lookup"><span data-stu-id="21351-216">Select **add record**.</span></span>
    
    ![Selezionare Aggiungi record](../../media/c2782250-a9a6-4aee-bb15-f57cb0008587.png)
  
8. <span data-ttu-id="21351-218">Aggiungere gli altri cinque record CNAME.</span><span class="sxs-lookup"><span data-stu-id="21351-218">Add each of the other five CNAME records.</span></span>
    
    <span data-ttu-id="21351-219">Sempre nella sezione **Add DNS record** creare un record usando i valori della riga successiva della tabella e quindi scegliere di nuovo **Add record** per completare il record.</span><span class="sxs-lookup"><span data-stu-id="21351-219">Still in the **Add DNS Record** section, create a record by using the values from the next row in the table, and then again select **add record** to complete that record.</span></span> 
    
    <span data-ttu-id="21351-220">Ripetere questa procedura fino a creare tutti e sei i record CNAME.</span><span class="sxs-lookup"><span data-stu-id="21351-220">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="21351-221">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="21351-221">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="21351-222"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="21351-222"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="21351-223">Non può essere presente più di un record TXT per SPF per un dominio.</span><span class="sxs-lookup"><span data-stu-id="21351-223">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="21351-224">Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="21351-224">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="21351-225">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="21351-225">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="21351-226">Al contrario, aggiungere i valori di Office 365 richiesti al record corrente in modo da ottenere un *unico* record SPF che include entrambi i set di valori.</span><span class="sxs-lookup"><span data-stu-id="21351-226">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="21351-227">Servono esempi?</span><span class="sxs-lookup"><span data-stu-id="21351-227">Need examples?</span></span> <span data-ttu-id="21351-228">Vedere queste [informazioni dettagliate e record SPF di esempio](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span><span class="sxs-lookup"><span data-stu-id="21351-228">Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span></span> <span data-ttu-id="21351-229">Per convalidare il record SPF, è possibile utilizzare uno di questi[strumenti di convalida SPF](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="21351-229">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="21351-230">Per iniziare, passare alla propria pagina dei domini su Bluehost usando [questo collegamento](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="21351-230">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="21351-231">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="21351-231">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="21351-232">Nell'area **domain** della pagina **Domains** trovare la riga relativa al dominio da modificare e quindi selezionare la casella di controllo corrispondente.</span><span class="sxs-lookup"><span data-stu-id="21351-232">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="21351-233">Può essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="21351-233">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="21351-234">Nell'area ***Domain_name*** , nella riga **Editor zone DNS** , selezionare **Manage DNS Records**.</span><span class="sxs-lookup"><span data-stu-id="21351-234">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="21351-235">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="21351-235">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="21351-236">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="21351-236">(Choose the **Type** value from the drop-down list.)</span></span> 
        
    |<span data-ttu-id="21351-237">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="21351-237">**Host Record**</span></span>|<span data-ttu-id="21351-238">**TTL**</span><span class="sxs-lookup"><span data-stu-id="21351-238">**TTL**</span></span>|<span data-ttu-id="21351-239">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="21351-239">**Type**</span></span>|<span data-ttu-id="21351-240">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="21351-240">**TXT Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="21351-241">14400</span><span class="sxs-lookup"><span data-stu-id="21351-241">14400</span></span>  <br/> |<span data-ttu-id="21351-242">TXT</span><span class="sxs-lookup"><span data-stu-id="21351-242">TXT</span></span>  <br/> |<span data-ttu-id="21351-243">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="21351-243">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="21351-244">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="21351-244">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Copiare il valore TXT](../../media/b2dabd7a-ee3d-4209-aa1e-0233eb8cf3b9.png)
  
5. <span data-ttu-id="21351-246">Selezionare **Aggiungi record**.</span><span class="sxs-lookup"><span data-stu-id="21351-246">Select **add record**.</span></span>
    
    ![Selezionare Aggiungi record](../../media/c050e9a2-2274-4640-8f0f-6752d382df5d.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="21351-248">Aggiungere i due record SRV necessari per Office 365</span><span class="sxs-lookup"><span data-stu-id="21351-248">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="21351-249"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="21351-249"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="21351-250">Per iniziare, passare alla propria pagina dei domini su Bluehost usando [questo collegamento](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="21351-250">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="21351-251">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="21351-251">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="21351-252">Nell'area **domain** della pagina **Domains** trovare la riga relativa al dominio da modificare e quindi selezionare la casella di controllo corrispondente.</span><span class="sxs-lookup"><span data-stu-id="21351-252">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="21351-253">Può essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="21351-253">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="21351-254">Nell'area ***Domain_name*** , nella riga **Editor zone DNS** , selezionare **Manage DNS Records**.</span><span class="sxs-lookup"><span data-stu-id="21351-254">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="21351-255">Creare il primo dei due record SRV.</span><span class="sxs-lookup"><span data-stu-id="21351-255">Create the first of the two SRV records.</span></span>
    
    <span data-ttu-id="21351-256">Nella pagina **DNS Zone Editor** digitare oppure copiare e incollare i valori della prima riga della tabella seguente nelle caselle del nuovo record nell'area **Add DNS Record**.</span><span class="sxs-lookup"><span data-stu-id="21351-256">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="21351-257">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="21351-257">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="21351-258">**Servizio**</span><span class="sxs-lookup"><span data-stu-id="21351-258">**Service**</span></span>|<span data-ttu-id="21351-259">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="21351-259">**Protocol**</span></span>|<span data-ttu-id="21351-260">**Host**</span><span class="sxs-lookup"><span data-stu-id="21351-260">**Host**</span></span>|<span data-ttu-id="21351-261">**TTL**</span><span class="sxs-lookup"><span data-stu-id="21351-261">**TTL**</span></span>|<span data-ttu-id="21351-262">**Type**</span><span class="sxs-lookup"><span data-stu-id="21351-262">**Type**</span></span>|<span data-ttu-id="21351-263">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="21351-263">**Priority**</span></span>|<span data-ttu-id="21351-264">**Peso**</span><span class="sxs-lookup"><span data-stu-id="21351-264">**Weight**</span></span>|<span data-ttu-id="21351-265">**Porta**</span><span class="sxs-lookup"><span data-stu-id="21351-265">**Port**</span></span>|<span data-ttu-id="21351-266">**Points To**</span><span class="sxs-lookup"><span data-stu-id="21351-266">**Points To**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="21351-267">_sip</span><span class="sxs-lookup"><span data-stu-id="21351-267">_sip</span></span>  <br/> |<span data-ttu-id="21351-268">_tls</span><span class="sxs-lookup"><span data-stu-id="21351-268">_tls</span></span>  <br/> |@  <br/> |<span data-ttu-id="21351-269">14400</span><span class="sxs-lookup"><span data-stu-id="21351-269">14400</span></span>  <br/> |<span data-ttu-id="21351-270">SRV</span><span class="sxs-lookup"><span data-stu-id="21351-270">SRV</span></span>  <br/> |<span data-ttu-id="21351-271">100</span><span class="sxs-lookup"><span data-stu-id="21351-271">100</span></span>  <br/> |<span data-ttu-id="21351-272">1</span><span class="sxs-lookup"><span data-stu-id="21351-272">1</span></span>  <br/> |<span data-ttu-id="21351-273">443</span><span class="sxs-lookup"><span data-stu-id="21351-273">443</span></span>  <br/> |<span data-ttu-id="21351-274">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="21351-274">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="21351-275">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="21351-275">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="21351-276">_tcp</span><span class="sxs-lookup"><span data-stu-id="21351-276">_tcp</span></span>  <br/> |@  <br/> |<span data-ttu-id="21351-277">14400</span><span class="sxs-lookup"><span data-stu-id="21351-277">14400</span></span>  <br/> |<span data-ttu-id="21351-278">SRV</span><span class="sxs-lookup"><span data-stu-id="21351-278">SRV</span></span>  <br/> |<span data-ttu-id="21351-279">100</span><span class="sxs-lookup"><span data-stu-id="21351-279">100</span></span>  <br/> |<span data-ttu-id="21351-280">1</span><span class="sxs-lookup"><span data-stu-id="21351-280">1</span></span>  <br/> |<span data-ttu-id="21351-281">5061</span><span class="sxs-lookup"><span data-stu-id="21351-281">5061</span></span>  <br/> |<span data-ttu-id="21351-282">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="21351-282">sipfed.online.lync.com</span></span>  <br/> |
   
    ![Copiare il valore per il nuovo record.](../../media/e2911bca-c00b-4b8a-837f-f1d438c474c4.png)
  
5. <span data-ttu-id="21351-284">Selezionare **Aggiungi record**.</span><span class="sxs-lookup"><span data-stu-id="21351-284">Select **add record**.</span></span>
    
    ![Selezionare Aggiungi record](../../media/0fd6a587-03fd-4bce-8321-b14e6ad21f5c.png)
  
6. <span data-ttu-id="21351-286">Aggiungere l'altro record SRV.</span><span class="sxs-lookup"><span data-stu-id="21351-286">Add the other SRV record.</span></span>
    
    <span data-ttu-id="21351-287">Sempre nella sezione **Add DNS record** creare un record usando i valori dell'altra riga della tabella e quindi selezionare di nuovo **Add record** per completare il record.</span><span class="sxs-lookup"><span data-stu-id="21351-287">Still in the **Add DNS Record** section, create a record by using the values from the other row in the table, and then again select **add record** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="21351-p114">In genere l'applicazione delle modifiche al DNS richiede circa 15 minuti. A volte può tuttavia capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="21351-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
