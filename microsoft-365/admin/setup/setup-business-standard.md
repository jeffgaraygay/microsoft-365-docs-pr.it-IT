---
title: Configurare Microsoft 365 Business Standard
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
- TRN_SMB
ms.custom:
- TRN_M365B
- OKR_SMB_Videos
- okr_smb
- AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
- BEA160
description: Informazioni su come configurare la sottoscrizione a Microsoft 365 Business Standard.
ms.openlocfilehash: b42dd0779c708410614ea2ab0d134aa3dcf0c7e9
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2020
ms.locfileid: "44778926"
---
# <a name="set-up-microsoft-business-standard"></a><span data-ttu-id="1858a-103">Configurare Microsoft Business Standard</span><span class="sxs-lookup"><span data-stu-id="1858a-103">Set up Microsoft Business Standard</span></span>
  
 <span data-ttu-id="1858a-104">\*Queste procedure interessano le aziende e le [organizzazioni no profit](https://go.microsoft.com/fwlink/p/?LinkId=627221) che usano il \*\*[piano Microsoft 365 Business Standard](https://go.microsoft.com/fwlink/p/?LinkId=627220)\*\*\*.</span><span class="sxs-lookup"><span data-stu-id="1858a-104">*These steps are for businesses and [nonprofits](https://go.microsoft.com/fwlink/p/?LinkId=627221) that have the **[Microsoft 365 Business Standard plan.](https://go.microsoft.com/fwlink/p/?LinkId=627220)***</span></span>

<span data-ttu-id="1858a-105">È possibile guardare un breve video sulla configurazione di Microsoft 365 Business Standard (noto in precedenza come Office 365 Business Premium).</span><span class="sxs-lookup"><span data-stu-id="1858a-105">Watch a short video about setting up Microsoft 365 Business Standard (formerly known as Office 365 Business Premium).</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/913be1ad-bae1-40c0-9ded-15bb477b828b]

<span data-ttu-id="1858a-106">Se il video è stato utile, consultare la [serie di formazione completa per piccole imprese e nuovi utenti di Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span><span class="sxs-lookup"><span data-stu-id="1858a-106">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

## <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="1858a-107">Aggiungere il proprio dominio per personalizzare l’accesso</span><span class="sxs-lookup"><span data-stu-id="1858a-107">Add your domain to personalize sign-in</span></span>

<span data-ttu-id="1858a-108">Quando si acquista Microsoft 365 Business Standard, si può scegliere di usare un dominio di cui si è proprietari o di acquistarne uno durante l’iscrizione.</span><span class="sxs-lookup"><span data-stu-id="1858a-108">When you purchase Microsoft 365 Business Standard, you have the option of using a domain you own, or buying one during the sign-up.</span></span>

- <span data-ttu-id="1858a-109">Se è stato acquistato un nuovo dominio al momento dell’iscrizione, il dominio è già configurato ed è possibile [Aggiungere utenti e assegnare le licenze](#add-users-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="1858a-109">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

1. <span data-ttu-id="1858a-110">Autenticarsi allì[interfaccia di amministrazione di Microsoft 365](https://admin.microsoft.com) usando le proprie credenziali globali di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="1858a-110">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 

2. <span data-ttu-id="1858a-111">Scegliere **Vai alla configurazione** per avviare la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="1858a-111">Choose **Go to setup** to start the wizard.</span></span>

3. <span data-ttu-id="1858a-112">Nella pagina **Installa le tue app di Office**, è possibile installare le app sul proprio computer.</span><span class="sxs-lookup"><span data-stu-id="1858a-112">On the **Install your Office apps** page, you can optionally install the apps on your own computer.</span></span>
    
4. <span data-ttu-id="1858a-113">Nel passaggio **Aggiungi dominio** immettere il nome del dominio che si vuole usare (ad esempio contoso.com).</span><span class="sxs-lookup"><span data-stu-id="1858a-113">In the **Add domain** step, enter the domain name you want to use (like contoso.com).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="1858a-114">Se un dominio è stato acquistato durante l’iscrizione, il passaggio **Aggiungi un dominio** non comparirà.</span><span class="sxs-lookup"><span data-stu-id="1858a-114">If you purchased a domain during the sign-up, you will not see **Add a domain** step here.</span></span> <span data-ttu-id="1858a-115">Proseguire al passaggio [Aggiungi utenti](#add-users-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="1858a-115">Go to [Add users](#add-users-and-assign-licenses) instead.</span></span>

    
4. <span data-ttu-id="1858a-116">Seguire i passaggi della procedura guidata per [creare record DNS presso un provider DNS per Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) che verifica che si è proprietari del dominio.</span><span class="sxs-lookup"><span data-stu-id="1858a-116">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="1858a-117">Se si conosce l’host del dominio, vedere anche le [istruzioni specifiche dell’host](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span><span class="sxs-lookup"><span data-stu-id="1858a-117">If you know your domain host, see also the [host specific instructions](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span></span>

    <span data-ttu-id="1858a-118">Se il proprio provider di hosting è GoDaddy o un altro host abilitato con [Domain Connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), il processo è semplice e viene richiesto di eseguire l’accesso e lasciare che Microsoft Authenticate completi l’autenticazione.</span><span class="sxs-lookup"><span data-stu-id="1858a-118">If your hosting provider is GoDaddy or another host enabled with [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), the process is easy and you'll be automatically asked to sign in and let Microsoft authenticate on your behalf.</span></span>

    ![Nella pagina di conferma dell’accesso di GoDaddy, selezionare Autorizza.](../../media/godaddyauth.png)

## <a name="add-users-and-assign-licenses"></a><span data-ttu-id="1858a-120">Aggiungere utenti e assegnare licenze</span><span class="sxs-lookup"><span data-stu-id="1858a-120">Add users and assign licenses</span></span>

<span data-ttu-id="1858a-121">Gli utenti possono essere aggiunti nella procedura guidata, ma è anche possibile [aggiungere utenti in seguito](../add-users/add-users.md) nell’interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="1858a-121">You can add users in the wizard, but you can also [add users later](../add-users/add-users.md) in the admin center.</span></span> <span data-ttu-id="1858a-122">Inoltre, se si dispone di un controller di dominio, è possibile aggiungere utenti con [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span><span class="sxs-lookup"><span data-stu-id="1858a-122">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

## <a name="add-users-in-the-wizard"></a><span data-ttu-id="1858a-123">Aggiungere utenti nella procedura guidata</span><span class="sxs-lookup"><span data-stu-id="1858a-123">Add users in the wizard</span></span>

<span data-ttu-id="1858a-124">A tutti gli utenti aggiunti nella procedura guidata viene assegnata automaticamente una licenza di Microsoft 365 Business Standard.</span><span class="sxs-lookup"><span data-stu-id="1858a-124">Any users you add in the wizard get automatically assigned a Microsoft 365 Business Standard license.</span></span>

1. <span data-ttu-id="1858a-125">Se la sottoscrizione a Microsoft 365 Business Standard include già degli utenti (ad esempio se si è usato Azure AD Connect), sarà disponibile un’opzione per assegnare le licenze a questi utenti.</span><span class="sxs-lookup"><span data-stu-id="1858a-125">If your Microsoft 365 Business Standard subscription has existing users (for example, if you used Azure AD Connect), you get an option to assign licenses to them now.</span></span> <span data-ttu-id="1858a-126">Procedere aggiungendo le licenze anche per questi utenti.</span><span class="sxs-lookup"><span data-stu-id="1858a-126">Go ahead and add licenses to them as well.</span></span>

2. <span data-ttu-id="1858a-127">Una volta aggiunti gli utenti, sarà disponibile un’opzione per condividere le credenziali con i nuovi utenti aggiunti.</span><span class="sxs-lookup"><span data-stu-id="1858a-127">After you've added the users, you'll also get an option to share credentials with the new users you added.</span></span> <span data-ttu-id="1858a-128">È possibile scegliere se stamparle, inviarle tramite posta elettronica o scaricarle.</span><span class="sxs-lookup"><span data-stu-id="1858a-128">You can choose to print them out, email them, or download them.</span></span>

## <a name="connect-your-domain"></a><span data-ttu-id="1858a-129">Connettere il proprio dominio</span><span class="sxs-lookup"><span data-stu-id="1858a-129">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="1858a-130">Se si è scelto di usare il dominio .onmicrosoft o se si usa Azure AD Connect per configurare gli utenti, questo passaggio non sarà visibile.</span><span class="sxs-lookup"><span data-stu-id="1858a-130">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="1858a-131">Per configurare i servizi, occorre aggiornare alcuni record presso l'host DNS o il registrar.</span><span class="sxs-lookup"><span data-stu-id="1858a-131">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="1858a-132">La configurazione guidata rileva in genere il registrar e offre un collegamento a istruzioni dettagliate per l'aggiornamento dei record NS presso il suo sito Web.</span><span class="sxs-lookup"><span data-stu-id="1858a-132">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="1858a-133">Se ciò non si verifica, [Modificare i server dei nomi per configurare Office 365 con qualsiasi registrar](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar).</span><span class="sxs-lookup"><span data-stu-id="1858a-133">If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar).</span></span> 

    - <span data-ttu-id="1858a-134">Se si dispone di record DNS esistenti, ad esempio un sito Web, ma il proprio host DNS è abilitato per [Domain Connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), scegliere **Aggiungi record per me**.</span><span class="sxs-lookup"><span data-stu-id="1858a-134">If you have existing DNS records, for example an existing web site, but your DNS host is enabled for [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), choose **Add records for me**.</span></span> <span data-ttu-id="1858a-135">Nella pagina **Scegli i tuoi servizi online**, accettare tutti i predefiniti, scegliere **Successivo**, e scegliere **Autorizza** nella pagina del proprio host DNS.</span><span class="sxs-lookup"><span data-stu-id="1858a-135">On the **Choose your online services** page, accept all the defaults, and choose **Next**, and choose **Authorize** on your DNS host's page.</span></span>
    - <span data-ttu-id="1858a-136">Se si dispone di record DNS esistenti con altri host DNS (non abilitati per il protocollo Domain Connect), è possibile gestire i propri record DNS per assicurarsi che i servizi esistenti restino connessi.</span><span class="sxs-lookup"><span data-stu-id="1858a-136">If you have existing DNS records with other DNS hosts (not enabled for domain connect), you'll want to manage your own DNS records to make sure the existing services stay connected.</span></span> <span data-ttu-id="1858a-137">Vedere [Informazioni di base sul dominio](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) per maggiori dettagli.</span><span class="sxs-lookup"><span data-stu-id="1858a-137">See [domain basics](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

2. <span data-ttu-id="1858a-138">Seguire i passaggi della procedura guidata, la posta elettronica e gli altri servizi saranno configurati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="1858a-138">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

    <span data-ttu-id="1858a-139">Una volta completato il processo di iscrizione, si verrà reindirizzati all'interfaccia di amministrazione, in cui si seguirà una procedura guidata per l'installazione delle app di Office, l'aggiunta del dominio, l'aggiunta degli utenti e l'assegnazione delle licenze.</span><span class="sxs-lookup"><span data-stu-id="1858a-139">When the signup process is complete, you'll be directed to the admin center, where you'll follow a wizard to install Office apps, add your domain, add users, and assign licenses.</span></span> <span data-ttu-id="1858a-140">Dopo aver completato la configurazione iniziale, è possibile usare la pagina **Configurazione** dell'interfaccia di amministrazione per continuare a configurare i servizi disponibili con gli abbonamenti.</span><span class="sxs-lookup"><span data-stu-id="1858a-140">After you complete the initial setup, you can use the **Setup** page in the admin center to continue setting up and configuring the services that come with your subscriptions.</span></span>

    <span data-ttu-id="1858a-141">Per altre informazioni sulla configurazione guidata e sulla pagina **Configurazione** dell'interfaccia di amministrazione, vedere [Differenze tra la configurazione guidata e la pagina Configurazione](o365-setup-wizard-and-setup-page.md).</span><span class="sxs-lookup"><span data-stu-id="1858a-141">For more information about the setup wizard and the admin center **Setup** page, see [Difference between the setup wizard and the Setup page](o365-setup-wizard-and-setup-page.md).</span></span>

## <a name="finish-setting-up"></a><span data-ttu-id="1858a-142">Completare la configurazione</span><span class="sxs-lookup"><span data-stu-id="1858a-142">Finish setting up</span></span>

### <a name="set-up-outlook-for-email"></a><span data-ttu-id="1858a-143">Configurare Outlook per la posta elettronica</span><span class="sxs-lookup"><span data-stu-id="1858a-143">Set up Outlook for email</span></span>

1. <span data-ttu-id="1858a-144">Nel menu Start di Windows cercare Outlook e selezionarlo.</span><span class="sxs-lookup"><span data-stu-id="1858a-144">On the Windows Start menu, search for Outlook, and select it.</span></span>

    <span data-ttu-id="1858a-145">Se si usa un Mac, aprire Outlook dalla barra degli strumenti o cercarlo con il Finder.</span><span class="sxs-lookup"><span data-stu-id="1858a-145">(If you're using a Mac, open Outlook from the toolbar or locate it using the Finder.)</span></span>

    <span data-ttu-id="1858a-146">Se Outlook è già stato installato, nella pagina di benvenuto selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="1858a-146">If you've just installed Outlook, on the Welcome page, select **Next**.</span></span>

2. <span data-ttu-id="1858a-147">Scegliere **File** \> **Informazioni** \> **Aggiungi account**.</span><span class="sxs-lookup"><span data-stu-id="1858a-147">Choose **File** \> **Info** \> **Add Account**.</span></span>

3. <span data-ttu-id="1858a-148">Immettere il proprio indirizzo di posta elettronica Microsoft e selezionare **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="1858a-148">Enter your Microsoft email address and select **Connect**.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/9fe86884-8a83-42cc-bca9-61a12e6dad31?autoplay=false]
  
<span data-ttu-id="1858a-149">Per altre informazioni, vedere [Configurare Outlook per la posta elettronica](https://support.microsoft.com/office/f5bf0cd1-e1f3-4b0d-a022-ecab17efe86f).</span><span class="sxs-lookup"><span data-stu-id="1858a-149">More at [Set up Outlook for email](https://support.microsoft.com/office/f5bf0cd1-e1f3-4b0d-a022-ecab17efe86f).</span></span>
  
### <a name="import-email"></a><span data-ttu-id="1858a-150">Importare la posta elettronica</span><span class="sxs-lookup"><span data-stu-id="1858a-150">Import email</span></span>

<span data-ttu-id="1858a-151">Se si stava usando Outlook con un altro account di posta elettronica, è possibile importare i messaggi, il calendario e i contatti precedenti nel nuovo account Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1858a-151">If you were using Outlook with another email account, you can import your previous email, calendar, and contacts into your new Microsoft account.</span></span>
  
1. <span data-ttu-id="1858a-152">**Esportare i vecchi messaggi di posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="1858a-152">**Export your old email**</span></span>

    <span data-ttu-id="1858a-153">In Outlook scegliere **File** \> \*\*Apri ed esporta&amp; \*\* \> **Importa/Esporta**.</span><span class="sxs-lookup"><span data-stu-id="1858a-153">In Outlook, choose **File** \> **Open &amp; Export** \> **Import/Export**.</span></span>

    <span data-ttu-id="1858a-154">Selezionare **Esporta in un file** e quindi seguire le istruzioni per esportare il file di dati di Outlook (pst) e le eventuali sottocartelle.</span><span class="sxs-lookup"><span data-stu-id="1858a-154">Select **Export to a File** and then follow the steps to export your Outlook Data File (.pst) and any subfolders.</span></span>

2. <span data-ttu-id="1858a-155">**Importare i vecchi messaggi di posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="1858a-155">**Import your old email**</span></span>

    <span data-ttu-id="1858a-156">In Outlook scegliere **File** \> **Apri ed&amp; esporta** \> **Importa/Esporta**.</span><span class="sxs-lookup"><span data-stu-id="1858a-156">In Outlook, choose **File** \> **Open &amp; Export** \> **Import/Export** again.</span></span>

    <span data-ttu-id="1858a-157">Questa volta, selezionare **Importa dati da altri programmi o file** e seguire le istruzioni per importare il file di backup creato al momento dell'esportazione dei vecchi messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="1858a-157">This time, select **Import from another program or file** and follow the steps to import the backup file you created when you exported your old email.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/40f7df36-9e24-44e5-8791-e9ed0dd8fd21?autoplay=false]
  
<span data-ttu-id="1858a-158">Per altre informazioni, vedere [Importare la posta elettronica con Outlook](https://support.microsoft.com/office/6a3771d4-4c1d-4a25-92a6-0b8e476335de).</span><span class="sxs-lookup"><span data-stu-id="1858a-158">More at [Import email with Outlook](https://support.microsoft.com/office/6a3771d4-4c1d-4a25-92a6-0b8e476335de).</span></span>

<span data-ttu-id="1858a-159">È anche possibile usare l’interfaccia di amministrazione di Exchange per importare la posta elettronica di tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="1858a-159">You can also use Exchange admin center to import everyone's email.</span></span> <span data-ttu-id="1858a-160">Per altre informazioni, vedere [Migrazione di account multipli di posta elettronica](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).</span><span class="sxs-lookup"><span data-stu-id="1858a-160">For more information, see [migrate multiple email accounts](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).</span></span>
  
### <a name="use-a-public-website"></a><span data-ttu-id="1858a-161">Usare un sito Web pubblico</span><span class="sxs-lookup"><span data-stu-id="1858a-161">Use a public website</span></span>

<span data-ttu-id="1858a-162">Microsoft 365 non include un sito Web pubblico che possa essere usato dall'azienda.</span><span class="sxs-lookup"><span data-stu-id="1858a-162">Microsoft 365 doesn't include a public website for your business.</span></span> <span data-ttu-id="1858a-163">Se si vuole configurarne uno, è consigliabile usare un partner Microsoft, come GoDaddy o WIX.</span><span class="sxs-lookup"><span data-stu-id="1858a-163">If you want to set one up, consider using a Microsoft partner, such as GoDaddy or WIX.</span></span>
  
1. <span data-ttu-id="1858a-164">Nell'interfaccia di amministrazione passare a **Risorse** e quindi selezionare **Sito Web pubblico**.</span><span class="sxs-lookup"><span data-stu-id="1858a-164">From the admin center, go to **Resources**, and then select **Public website**.</span></span>

2. <span data-ttu-id="1858a-165">Selezionare **Altre informazioni** sotto una delle opzioni, quindi effettuare l'iscrizione con un partner di siti Web e usare i suoi strumenti per configurare e progettare il sito.</span><span class="sxs-lookup"><span data-stu-id="1858a-165">Select **Learn more** under one of the options, and then sign up with a website partner and use their tools to set up and design your site.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/4839abc6-9323-4cbf-a79d-2907235f9ebb]

<span data-ttu-id="1858a-166">Per altre informazioni, vedere [Usare un sito Web pubblico](https://support.microsoft.com/office/3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="1858a-166">More at [Use a public website](https://support.microsoft.com/office/3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>