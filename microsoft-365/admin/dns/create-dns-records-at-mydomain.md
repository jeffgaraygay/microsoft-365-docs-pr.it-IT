---
title: Creare record DNS su MyDomain per Office 365
f1.keywords:
- NOCSH
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
- Adm_NonTOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9982191d-ed79-46a9-b2e7-317d1a3a9867
description: Informazioni su come verificare il dominio e configurare record DNS per la posta elettronica, Skype for Business Online e altri servizi su MyDomain per Office 365.
ms.openlocfilehash: c85c04d369add95d3aaa815229257fe90a24fb28
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/02/2020
ms.locfileid: "42349867"
---
# <a name="create-dns-records-at-mydomain-for-office-365"></a><span data-ttu-id="8395b-103">Creare record DNS su MyDomain per Office 365</span><span class="sxs-lookup"><span data-stu-id="8395b-103">Create DNS records at MyDomain for Office 365</span></span>


  
 <span data-ttu-id="8395b-104">Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="8395b-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="8395b-p101">Il sito Web MyDomain non supporta i record SRV, quindi diverse caratteristiche di Skype for Business online e Outlook Web App non funzioneranno. Indipendentemente dal piano di Office 365 in uso, se si gestiscono i record DNS su MyDomain ci saranno [significative limitazioni del servizio](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx), quindi è consigliabile passare a un provider di hosting DNS diverso.</span><span class="sxs-lookup"><span data-stu-id="8395b-p101">The MyDomain website doesn't support SRV records, which means several Skype for Business Online and Outlook Web App features won't work. No matter which Office 365 plan you use, if you manage your DNS records at MyDomain, there are [significant service limitations](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx), and you might want to switch to a different DNS hosting provider.</span></span> 
  
<span data-ttu-id="8395b-107">Se si sceglie di gestire i propri record DNS di Office 365 in MyDomain nonostante le limitazioni del servizio, seguire i passaggi di questo articolo per configurare i record DNS per la posta elettronica, Skype for Business online e così via.</span><span class="sxs-lookup"><span data-stu-id="8395b-107">If you choose to manage your own Office 365 DNS records at MyDomain despite the service limitations, follow the steps in this article to set up your DNS records for email, Skype for Business Online, and so on.</span></span>
    
<span data-ttu-id="8395b-108">Dopo aver aggiunto questi record a MyDomain, il domino sarà configurato per l'uso con i servizi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="8395b-108">After you add these records at MyDomain, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="8395b-109">Per informazioni su hosting Web e DNS per i siti Web con Office 365, vedere [Usare un sito Web pubblico con Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="8395b-109">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="8395b-p102">In genere l'applicazione delle modifiche al DNS richiede circa 15 minuti. A volte può tuttavia capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="8395b-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="8395b-113">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="8395b-113">Add a TXT record for verification</span></span>
<span data-ttu-id="8395b-114"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="8395b-114"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="8395b-p103">Prima di usare il proprio dominio con Office 365, è necessario dimostrare di esserne proprietari. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Office 365 che si è proprietari del dominio.</span><span class="sxs-lookup"><span data-stu-id="8395b-p103">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8395b-p104">Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="8395b-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="8395b-p105">Per iniziare, passare alla propria pagina dei domini su MyDomain usando [questo collegamento](https://www.mydomain.com/controlpanel). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="8395b-p105">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="8395b-121">Nella sezione **Preferiti** selezionare **Dominio centrale**.</span><span class="sxs-lookup"><span data-stu-id="8395b-121">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="8395b-122">In **Dominio** selezionare il nome del dominio da modificare.</span><span class="sxs-lookup"><span data-stu-id="8395b-122">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="8395b-123">Nella riga **Panoramica** scegliere **DNS**.</span><span class="sxs-lookup"><span data-stu-id="8395b-123">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="8395b-124">Nell'elenco a discesa **Modifica** selezionare **Record TXT/SPF**.</span><span class="sxs-lookup"><span data-stu-id="8395b-124">From the **Modify** drop-down list, choose **TXT/SPF Record**.</span></span>
    
6. <span data-ttu-id="8395b-125">Nella casella del nuovo record, in **Contenuto**, digitare oppure copiare e incollare il valore della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="8395b-125">Under **Content**, in the box for the new record, type or copy and paste the value from the following table.</span></span>
    
    ||
    |:-----|
    |<span data-ttu-id="8395b-126">**Contenuto**</span><span class="sxs-lookup"><span data-stu-id="8395b-126">**Content**</span></span> <br/> |
    |<span data-ttu-id="8395b-127">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="8395b-127">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="8395b-128">**Note:** questo è un esempio.</span><span class="sxs-lookup"><span data-stu-id="8395b-128">**Note:** This is an example.</span></span> <span data-ttu-id="8395b-129">Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella in Office 365.</span><span class="sxs-lookup"><span data-stu-id="8395b-129">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="8395b-130">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="8395b-130">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="8395b-131">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="8395b-131">Select **Add**.</span></span>
    
8. <span data-ttu-id="8395b-132">Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.</span><span class="sxs-lookup"><span data-stu-id="8395b-132">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="8395b-133">Una volta aggiunto il record al sito del registrar, è possibile tornare in Office 365 e chiedere di cercarlo.</span><span class="sxs-lookup"><span data-stu-id="8395b-133">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="8395b-134">Quando Office 365 trova il record TXT corretto, il dominio è verificato.</span><span class="sxs-lookup"><span data-stu-id="8395b-134">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="8395b-135">Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="8395b-135">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="8395b-136">Nella pagina **Domini** selezionare il dominio da verificare.</span><span class="sxs-lookup"><span data-stu-id="8395b-136">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="8395b-137">Nella pagina **Configurazione** selezionare **Avvia configurazione**.</span><span class="sxs-lookup"><span data-stu-id="8395b-137">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="8395b-138">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="8395b-138">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="8395b-p107">In genere l'applicazione delle modifiche al DNS richiede circa 15 minuti. A volte può tuttavia capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="8395b-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="8395b-142">Aggiungere un record MX in modo che la posta elettronica per il dominio venga recapitata in Office 365</span><span class="sxs-lookup"><span data-stu-id="8395b-142">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="8395b-143"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="8395b-143"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="8395b-p108">Per iniziare, passare alla propria pagina dei domini su MyDomain usando [questo collegamento](https://www.mydomain.com/controlpanel). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="8395b-p108">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="8395b-146">Nella sezione **Preferiti** selezionare **Dominio centrale**.</span><span class="sxs-lookup"><span data-stu-id="8395b-146">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="8395b-147">In **Dominio** selezionare il nome del dominio da modificare.</span><span class="sxs-lookup"><span data-stu-id="8395b-147">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="8395b-148">Nella riga **Panoramica** scegliere **DNS**.</span><span class="sxs-lookup"><span data-stu-id="8395b-148">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="8395b-149">Nell'elenco a discesa **Modify** selezionare **MX Record**.</span><span class="sxs-lookup"><span data-stu-id="8395b-149">From the **Modify** drop-down list, choose **MX Record**.</span></span>
    
    ![MyDomain-BP-Configure-2-1](../../media/bbfba978-8c53-471b-8c9e-8ae62e559d15.png)
  
6. <span data-ttu-id="8395b-151">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="8395b-151">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="8395b-152">\*\*Priorità \*\*</span><span class="sxs-lookup"><span data-stu-id="8395b-152">**Priority**</span></span>|<span data-ttu-id="8395b-153">**Host**</span><span class="sxs-lookup"><span data-stu-id="8395b-153">**Host**</span></span>|<span data-ttu-id="8395b-154">**Points To:**</span><span class="sxs-lookup"><span data-stu-id="8395b-154">**Points To:**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="8395b-155">0</span><span class="sxs-lookup"><span data-stu-id="8395b-155">0</span></span>  <br/> <span data-ttu-id="8395b-156">Per altre informazioni sulla priorità, vedere [Informazioni sulla priorità MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx).</span><span class="sxs-lookup"><span data-stu-id="8395b-156">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |@  <br/> | <span data-ttu-id="8395b-157">*\<chiave-dominio\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="8395b-157">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="8395b-158">**Nota:** ottenere il valore \<*domain-key*\> dall'account di Office 365.</span><span class="sxs-lookup"><span data-stu-id="8395b-158">**Note:** Get your \<*domain-key*\> from your Office 365 account.</span></span><span data-ttu-id="8395b-159"> > [Come trovarlo?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="8395b-159"> > [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |
   
    ![MyDomain-BP-Configure-2-2](../../media/3e19cec3-7f3b-493d-81f7-cda30ba007d5.png)
  
7. <span data-ttu-id="8395b-161">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="8395b-161">Select **Add**.</span></span>
    
    ![MyDomain-BP-Configure-2-3](../../media/1a1951a8-11d7-405d-bef5-285bbb053ce8.png)
  
8. <span data-ttu-id="8395b-163">Se sono presenti altri record MX, selezionare **Remove** nella colonna **Action** di ogni record per eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="8395b-163">If there are any other existing MX records, select **Remove** in the **Action** column for each one to delete it.</span></span> 
    
    ![MyDomain-BP-Configure-2-4](../../media/42576149-e056-4a81-a5fd-2c5dfac44e2e.png)
  
9. <span data-ttu-id="8395b-165">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="8395b-165">Select **OK**.</span></span>
    
    ![MyDomain-BP-Configure-2-5](../../media/d6b70eb7-b79c-499e-82ff-ecef2e300368.png)
  
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="8395b-167">Aggiungere i record CNAME necessari per Office 365</span><span class="sxs-lookup"><span data-stu-id="8395b-167">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="8395b-168"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="8395b-168"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="8395b-p110">Per iniziare, passare alla propria pagina dei domini su MyDomain usando [questo collegamento](https://www.mydomain.com/controlpanel). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="8395b-p110">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="8395b-171">Nella sezione **Preferiti** selezionare **Dominio centrale**.</span><span class="sxs-lookup"><span data-stu-id="8395b-171">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="8395b-172">In **Dominio** selezionare il nome del dominio da modificare.</span><span class="sxs-lookup"><span data-stu-id="8395b-172">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="8395b-173">Nella riga **Panoramica** scegliere **DNS**.</span><span class="sxs-lookup"><span data-stu-id="8395b-173">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="8395b-174">Nell'elenco a discesa **Modify** selezionare **CNAME Alias**.</span><span class="sxs-lookup"><span data-stu-id="8395b-174">From the **Modify** drop-down list, choose **CNAME Alias**.</span></span>
    
    ![MyDomain-BP-Configure-3-1](../../media/628267fc-d37b-42ef-bb92-265284e339ac.png)
  
6. <span data-ttu-id="8395b-176">Aggiungere il primo record CNAME.</span><span class="sxs-lookup"><span data-stu-id="8395b-176">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="8395b-177">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori dalla prima riga della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="8395b-177">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="8395b-178">**Host**</span><span class="sxs-lookup"><span data-stu-id="8395b-178">**Host**</span></span>|<span data-ttu-id="8395b-179">**Points To:**</span><span class="sxs-lookup"><span data-stu-id="8395b-179">**Points To:**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="8395b-180">individuazione automatica</span><span class="sxs-lookup"><span data-stu-id="8395b-180">autodiscover</span></span>  <br/> |<span data-ttu-id="8395b-181">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="8395b-181">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="8395b-182">sip</span><span class="sxs-lookup"><span data-stu-id="8395b-182">sip</span></span>  <br/> |<span data-ttu-id="8395b-183">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="8395b-183">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="8395b-184">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="8395b-184">lyncdiscover</span></span>  <br/> |<span data-ttu-id="8395b-185">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="8395b-185">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="8395b-186">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="8395b-186">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="8395b-187">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="8395b-187">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="8395b-188">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="8395b-188">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="8395b-189">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="8395b-189">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![MyDomain-BP-Configure-3-2](../../media/3c8660b3-40bb-453d-8b99-4d22032bc4b3.png)
  
7. <span data-ttu-id="8395b-191">Selezionare **Aggiungi** per aggiungere il primo record.</span><span class="sxs-lookup"><span data-stu-id="8395b-191">Select **Add** to add the first record.</span></span> 
    
    ![MyDomain-BP-Configure-3-3](../../media/103a1d99-70da-4fdf-9291-7dd058ec6c4a.png)
  
8. <span data-ttu-id="8395b-193">Aggiungere il secondo record CNAME.</span><span class="sxs-lookup"><span data-stu-id="8395b-193">Add the second CNAME record.</span></span>
    
    <span data-ttu-id="8395b-194">Usare i valori della seconda riga della tabella precedente e quindi selezionare **Aggiungi** per aggiungere il secondo record.</span><span class="sxs-lookup"><span data-stu-id="8395b-194">Use the values from the second row of the table above, and then select **Add** to add the second record.</span></span> 
    
    <span data-ttu-id="8395b-195">Aggiungere i record rimanenti allo stesso modo, usando i valori dalla terza, quarta, quinta e sesta riga della tabella.</span><span class="sxs-lookup"><span data-stu-id="8395b-195">Add the remaining records in the same way, using the values from the third, fourth, fifth, and sixth rows of the table.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="8395b-196">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="8395b-196">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="8395b-197"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="8395b-197"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="8395b-198">Non può essere presente più di un record TXT per SPF per un dominio.</span><span class="sxs-lookup"><span data-stu-id="8395b-198">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="8395b-199">Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="8395b-199">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="8395b-200">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="8395b-200">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="8395b-201">Instead, add the required Office 365 values to the current record so that you have a single SPF record that includes both sets of values.</span><span class="sxs-lookup"><span data-stu-id="8395b-201">Instead, add the required Office 365 values to the current record so that you have a single SPF record that includes both sets of values.</span></span> <span data-ttu-id="8395b-202">Servono esempi?</span><span class="sxs-lookup"><span data-stu-id="8395b-202">Need examples?</span></span> <span data-ttu-id="8395b-203">Vedere queste [informazioni dettagliate e record SPF di esempio](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords).</span><span class="sxs-lookup"><span data-stu-id="8395b-203">Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords).</span></span> <span data-ttu-id="8395b-204">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="8395b-204">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="8395b-p112">Per iniziare, passare alla propria pagina dei domini su MyDomain usando [questo collegamento](https://www.mydomain.com/controlpanel). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="8395b-p112">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="8395b-207">Nella sezione **Preferiti** selezionare **Dominio centrale**.</span><span class="sxs-lookup"><span data-stu-id="8395b-207">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="8395b-208">In **Dominio** selezionare il nome del dominio da modificare.</span><span class="sxs-lookup"><span data-stu-id="8395b-208">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="8395b-209">Nella riga **Panoramica** scegliere **DNS**.</span><span class="sxs-lookup"><span data-stu-id="8395b-209">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="8395b-210">Nell'elenco a discesa **Modify** selezionare **TXT/SPF Record**.</span><span class="sxs-lookup"><span data-stu-id="8395b-210">From the **Modify** drop-down list, choose **TXT/SPF Record**.</span></span>
    
    ![MyDomain-BP-Configure-4-1](../../media/c461c762-52e6-4fde-b5bc-4dd5e5d62ed3.png)
  
6. <span data-ttu-id="8395b-212">Nella casella del nuovo record, in **Contenuto**, digitare oppure copiare e incollare il valore della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="8395b-212">Under **Content**, in the box for the new record, type or copy and paste the value from the following table.</span></span>
    
    |<span data-ttu-id="8395b-213">**Contenuto**</span><span class="sxs-lookup"><span data-stu-id="8395b-213">**Content**</span></span>|
    |:-----|
    |<span data-ttu-id="8395b-214">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="8395b-214">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="8395b-215">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="8395b-215">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![MyDomain-BP-Configure-4-2](../../media/17d43106-88e6-47e5-aeba-0f18484acf3e.png)
  
7. <span data-ttu-id="8395b-217">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="8395b-217">Select **Add**.</span></span>
    
    ![MyDomain-BP-Configure-4-3](../../media/b3670563-b620-470c-a42b-2c77888981f8.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="8395b-219">Aggiungere i due record SRV necessari per Office 365</span><span class="sxs-lookup"><span data-stu-id="8395b-219">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="8395b-220"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="8395b-220"><a name="BKMK_add_SRV"> </a></span></span>

> [!CAUTION]
> <span data-ttu-id="8395b-p113">Il sito Web MyDomain non supporta i record SRV, quindi diverse caratteristiche di Skype for Business online e Outlook Web App non funzioneranno. Indipendentemente dal piano di Office 365 in uso, se si gestiscono i record DNS su MyDomain ci saranno [significative limitazioni del servizio](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx), quindi è consigliabile passare a un provider di hosting DNS diverso.</span><span class="sxs-lookup"><span data-stu-id="8395b-p113">The MyDomain website doesn't support SRV records, which means several Skype for Business Online and Outlook Web App features won't work. No matter which Office 365 plan you use, if you manage your DNS records at MyDomain, there are [significant service limitations](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx), and you might want to switch to a different DNS hosting provider.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="8395b-p114">In genere l'applicazione delle modifiche al DNS richiede circa 15 minuti. A volte può tuttavia capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="8395b-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  