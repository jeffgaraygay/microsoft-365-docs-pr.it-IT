---
title: Risoluzione dei problemi relativi all'analisi dell'utilizzo di Microsoft 365
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a73632a1-62c8-4a13-8115-913773b30f93
description: Informazioni su come risolvere i problemi relativi all'app modello di analisi dei dati di utilizzo di Microsoft 365.
ms.openlocfilehash: a9da79a6d7760f7876de7a6321554545d411f6be
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/24/2020
ms.locfileid: "42244181"
---
# <a name="troubleshooting-microsoft-365-usage-analytics"></a><span data-ttu-id="2ae0b-103">Risoluzione dei problemi relativi all'analisi dell'utilizzo di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2ae0b-103">Troubleshooting Microsoft 365 usage analytics</span></span>

<span data-ttu-id="2ae0b-104">Esaminare l'elenco dei messaggi di errore seguenti per ottenere assistenza con i problemi più comuni relativi all'analisi dell'utilizzo di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2ae0b-104">Explore the following list of error messages to get help with the most common issues with Microsoft 365 usage analytics.</span></span>
  
    
## <a name="we-are-unable-to-process-your-request-you-have-to-first-subscribe-to-this-data-from-the-microsoft-365-admin-center"></a><span data-ttu-id="2ae0b-105">Non è possibile elaborare la richiesta.</span><span class="sxs-lookup"><span data-stu-id="2ae0b-105">We are unable to process your request.</span></span> <span data-ttu-id="2ae0b-106">Per prima cosa, è necessario iscriversi a questi dati dall'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2ae0b-106">You have to first subscribe to this data from the Microsoft 365 admin center</span></span>

 <span data-ttu-id="2ae0b-107">**Codice di errore:** 422</span><span class="sxs-lookup"><span data-stu-id="2ae0b-107">**Error Code :** 422</span></span> 
  
 <span data-ttu-id="2ae0b-108">**Dove viene visualizzato questo messaggio:** In Power BI quando ci si connette all'app modello di analisi dei dati di utilizzo di Microsoft 365 o quando si chiama direttamente le API di report di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2ae0b-108">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="2ae0b-109">**Causa:** Prima di potersi connettere all'app, è necessario sottoscrivere i dati dell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2ae0b-109">**Cause:** Before you can connect to the app you have to subscribe to the data from the Microsoft 365 admin center.</span></span> <span data-ttu-id="2ae0b-110">Se questo passaggio non viene effettuato per primo, non sarà possibile connettersi all'app modello, anche se si fornisce l'ID tenant Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2ae0b-110">If this step isn't done first, you won't be able to connect to the template app, even if you provide your Microsoft 365 tenant id.</span></span> 
  
 <span data-ttu-id="2ae0b-111">**Per correggere l'errore:** Per sottoscrivere i dati, passare all'interfaccia di amministrazione \> **segnala** \> l' <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">utilizzo</a> e individuare il riquadro Analisi utilizzo Microsoft 365 nella pagina del dashboard principale.</span><span class="sxs-lookup"><span data-stu-id="2ae0b-111">**To fix this error:** To subscribe to the data, go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="2ae0b-112">Selezionare il pulsante **inizia** e quindi nel riquadro **report** che si apre, trasformare i **dati disponibili in analisi di utilizzo di Microsoft 365 per** l'impostazione di Power bi su e **Save**.</span><span class="sxs-lookup"><span data-stu-id="2ae0b-112">Select the **Get started** button and then in the **Reports** pane that opens, turn the **Make data available to Microsoft 365 usage analytics for Power BI** setting on and **Save**.</span></span>
  
## <a name="we-are-processing-your-data"></a><span data-ttu-id="2ae0b-113">Stiamo elaborando i dati</span><span class="sxs-lookup"><span data-stu-id="2ae0b-113">We are processing your data</span></span>

 <span data-ttu-id="2ae0b-114">**Dove viene visualizzato questo messaggio:** Nel riquadro **Analisi utilizzo microsoft 365** sul dashboard di **utilizzo** nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2ae0b-114">**Where you will see this message:** In the **Microsoft 365 usage analytics** tile on the **Usage** dashboard in the Microsoft 365 admin center.</span></span> 
  
 <span data-ttu-id="2ae0b-115">**Causa:** Quando si [sceglie di visualizzare i dati nell'app modello](enable-usage-analytics.md) dall'interfaccia di amministrazione di Microsoft 365, il sistema Microsoft 365 inizia a generare dati di utilizzo cronologici per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="2ae0b-115">**Cause:** When you [opt in to seeing data in the template app](enable-usage-analytics.md) from the Microsoft 365 admin center, the Microsoft 365 system starts generating historical usage data for your organization.</span></span> <span data-ttu-id="2ae0b-116">A seconda delle dimensioni del tenant, questa operazione potrebbe richiedere da 2 a 48 ore.</span><span class="sxs-lookup"><span data-stu-id="2ae0b-116">Depending on the size of your tenant, this step could take anywhere between 2 hours to 48 hours.</span></span> 
  
 <span data-ttu-id="2ae0b-117">**Per risolvere il riguardo:** Basta essere pazienti, ma se il messaggio non cambia ai **dati è pronto** dopo 3 giorni, contattare il [supporto tecnico Microsoft 365 for business](../contact-support-for-business-products.md).</span><span class="sxs-lookup"><span data-stu-id="2ae0b-117">**To fix this:** Just be patient, but if the message does not change to **Your data is ready** after 3 days, [contact Microsoft 365 for business support](../contact-support-for-business-products.md).</span></span>
  
## <a name="we-are-unable-to-process-your-request-at-this-time-we-are-still-preparing-the-data-for-your-organization"></a><span data-ttu-id="2ae0b-118">Non è possibile elaborare la richiesta in questo momento.</span><span class="sxs-lookup"><span data-stu-id="2ae0b-118">We are unable to process your request at this time.</span></span> <span data-ttu-id="2ae0b-119">La preparazione dei dati per l'organizzazione non è ancora terminata</span><span class="sxs-lookup"><span data-stu-id="2ae0b-119">We are still preparing the data for your organization</span></span>

 <span data-ttu-id="2ae0b-120">**Codice di errore:** 423</span><span class="sxs-lookup"><span data-stu-id="2ae0b-120">**Error Code:** 423</span></span> 
  
 <span data-ttu-id="2ae0b-121">**Dove viene visualizzato questo messaggio:** In Power BI quando ci si connette all'app modello di analisi dei dati di utilizzo di Microsoft 365 o quando si chiama direttamente le API di report di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2ae0b-121">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="2ae0b-122">**Causa:** Quando si [sceglie di visualizzare i dati nell'app modello](enable-usage-analytics.md) dall'interfaccia di amministrazione, il sistema Microsoft 365 inizia a generare dati di utilizzo cronologici per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="2ae0b-122">**Cause:** When you [opt in to seeing data in the template app](enable-usage-analytics.md) from the admin center, the Microsoft 365 system starts generating historical usage data for your organization.</span></span> <span data-ttu-id="2ae0b-123">A seconda delle dimensioni del tenant, questa operazione potrebbe richiedere da 2 a 48 ore.</span><span class="sxs-lookup"><span data-stu-id="2ae0b-123">Depending on the size of your tenant, this step could take anywhere between 2 hours to 48 hours.</span></span> 
  
 <span data-ttu-id="2ae0b-124">**Per risolvere il riguardo:** Basta essere pazienti, ma se il messaggio non cambia ai **dati è pronto** anche 3 giorni dopo l'inizio, contattare il [supporto tecnico Microsoft 365 for business](../contact-support-for-business-products.md).</span><span class="sxs-lookup"><span data-stu-id="2ae0b-124">**To fix this:** Just be patient, but if the message does not change to **Your data is ready** even 3 days since initiation, [contact Microsoft 365 for business support](../contact-support-for-business-products.md).</span></span>
  
## <a name="the-tenant-id-you-provided-is-not-in-the-correct-format"></a><span data-ttu-id="2ae0b-125">L'ID tenant specificato non è nel formato corretto</span><span class="sxs-lookup"><span data-stu-id="2ae0b-125">The tenant ID you provided is not in the correct format</span></span>

 <span data-ttu-id="2ae0b-126">**Codice di errore:** 400</span><span class="sxs-lookup"><span data-stu-id="2ae0b-126">**Error Code:** 400</span></span> 
  
 <span data-ttu-id="2ae0b-127">**Dove viene visualizzato questo messaggio:** In Power BI quando ci si connette all'app modello di analisi dei dati di utilizzo di Microsoft 365 o quando si chiama direttamente le API di report di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2ae0b-127">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="2ae0b-p107">**Causa:** l'ID tenant è un GUID e deve essere nel formato xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx. Se si immette qualsiasi altra stringa nella casella d input del tenant, verrà visualizzato questo messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="2ae0b-p107">**Cause:** The tenant id is a guid and has to be in the format of xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx. If you enter any other string in the tenant input box you will get this error.</span></span> 
  
 <span data-ttu-id="2ae0b-130">**Per correggere l'errore:** Passare all'interfaccia di amministrazione \> **segnala** \> l' <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">utilizzo</a> e individuare il riquadro Analisi utilizzo Microsoft 365 nella pagina del dashboard principale.</span><span class="sxs-lookup"><span data-stu-id="2ae0b-130">**To fix this error:** Go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="2ae0b-131">L'ID tenant è indicato nel riquadro.</span><span class="sxs-lookup"><span data-stu-id="2ae0b-131">The tenant id is listed on the tile.</span></span> <span data-ttu-id="2ae0b-132">È possibile copiarlo da qui e incollarlo nella finestra di dialogo per la connessione all'app modello.</span><span class="sxs-lookup"><span data-stu-id="2ae0b-132">You can copy it from here and paste it in the dialog box for connecting to the template app.</span></span> 
  
## <a name="the-tenant-id-you-provided-is-not-recognized-by-our-system"></a><span data-ttu-id="2ae0b-133">L'ID tenant specificato non è stato riconosciuto dal sistema</span><span class="sxs-lookup"><span data-stu-id="2ae0b-133">The tenant ID you provided is not recognized by our system</span></span>

 <span data-ttu-id="2ae0b-134">**Codice di errore:** 404</span><span class="sxs-lookup"><span data-stu-id="2ae0b-134">**Error Code:** 404</span></span> 
  
 <span data-ttu-id="2ae0b-135">**Dove viene visualizzato questo messaggio:** In Power BI quando ci si connette all'app modello di analisi dei dati di utilizzo di Microsoft 365 o quando si chiama direttamente le API di report di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2ae0b-135">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="2ae0b-136">**Causa:** l'ID tenant specificato non è valido o non esiste.</span><span class="sxs-lookup"><span data-stu-id="2ae0b-136">**Cause:** The tenant id you provided is not valid or does not exist.</span></span> 
  
 <span data-ttu-id="2ae0b-137">**Per correggere l'errore:** Passare all'interfaccia di amministrazione \> **segnala** \> l' <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">utilizzo</a> e individuare il riquadro Analisi utilizzo Microsoft 365 nella pagina del dashboard principale.</span><span class="sxs-lookup"><span data-stu-id="2ae0b-137">**To fix this error:** Go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="2ae0b-138">L'ID tenant è indicato nel riquadro.</span><span class="sxs-lookup"><span data-stu-id="2ae0b-138">The tenant id is listed on the tile.</span></span> <span data-ttu-id="2ae0b-139">È possibile copiarlo da qui e incollarlo nella finestra di dialogo per la connessione all'app modello.</span><span class="sxs-lookup"><span data-stu-id="2ae0b-139">You can copy it from here and paste it in the dialog box for connecting to the template app.</span></span> 
  
## <a name="please-re-enter-your-credentials-to-sign-in-to-power-bi-again"></a><span data-ttu-id="2ae0b-140">Immettere di nuovo le credenziali per accedere a Power BI</span><span class="sxs-lookup"><span data-stu-id="2ae0b-140">Please re-enter your credentials to sign in to Power BI again</span></span>

<span data-ttu-id="2ae0b-141">Codice di errore: 302</span><span class="sxs-lookup"><span data-stu-id="2ae0b-141">Error Code: 302</span></span>
  
 <span data-ttu-id="2ae0b-142">**Dove viene visualizzato questo messaggio:** In Power BI quando ci si connette all'app modello di analisi dei dati di utilizzo di Microsoft 365 o quando si chiama direttamente le API di report di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2ae0b-142">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="2ae0b-143">**Causa:** il codice di autorizzazione ha avuto esito negativo e potrebbe essere necessario immettere nuovamente le credenziali.</span><span class="sxs-lookup"><span data-stu-id="2ae0b-143">**Cause:** The authorization code failed and may require you to enter your credentials again.</span></span> 
  
 <span data-ttu-id="2ae0b-144">**Per correggere l'errore:** disconnettersi da Power BI, quindi eseguire di nuovo l'accesso.</span><span class="sxs-lookup"><span data-stu-id="2ae0b-144">**To fix this error:** Sign out of Power BI, and then sign in again.</span></span> 
  
## <a name="you-do-not-have-the-right-authorization-to-access-to-this-data-to-be-able-to-gain-access-to-the-data-from-this-service-you-need-to-be-either-a-global-admin-or-any-one-of-the-product-admins"></a><span data-ttu-id="2ae0b-145">Non si ha l'autorizzazione giusta per accedere a questi dati.</span><span class="sxs-lookup"><span data-stu-id="2ae0b-145">You do not have the right authorization to access to this data.</span></span> <span data-ttu-id="2ae0b-146">Per accedere ai dati da questo servizio, è necessario essere un amministratore globale o un amministratore prodotto</span><span class="sxs-lookup"><span data-stu-id="2ae0b-146">To be able to gain access to the data from this service you need to be either a global admin or any one of the product admins</span></span>

 <span data-ttu-id="2ae0b-147">**Codice di errore:** 403</span><span class="sxs-lookup"><span data-stu-id="2ae0b-147">**Error Code:** 403</span></span> 
  
 <span data-ttu-id="2ae0b-148">**Dove viene visualizzato questo messaggio:** In Power BI quando ci si connette all'app modello di analisi dei dati di utilizzo di Microsoft 365 o quando si chiama direttamente le API di report di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2ae0b-148">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="2ae0b-149">**Causa:** Il codice di autorizzazione ha avuto esito negativo perché l'utente che ha tentato di connettersi all'app modello non ha il livello di autorizzazione appropriato per accedere a questi dati.</span><span class="sxs-lookup"><span data-stu-id="2ae0b-149">**Cause:** The authorization code failed because the user who tried connecting to the template app does not have the right level of authorization to access this data.</span></span> 
  
 <span data-ttu-id="2ae0b-150">**Per correggere l'errore:** Specificare le credenziali di un utente che sia un amministratore **globale**, un amministratore di **Exchange**, un amministratore di **Skype for business**, un amministratore di **SharePoint**, un **lettore globale** o un **lettore di report** per connettersi all'app modello.</span><span class="sxs-lookup"><span data-stu-id="2ae0b-150">**To fix this error:** Provide the credentials of a user who is either a **Global admin**, **Exchange admin**, **Skype for Business admin**, **SharePoint admin**, **Global reader** or **Report reader** to connect to the template app.</span></span> <span data-ttu-id="2ae0b-151">Per ulteriori informazioni, vedere informazioni [sui ruoli di amministratore](../add-users/about-admin-roles.md) .</span><span class="sxs-lookup"><span data-stu-id="2ae0b-151">See [About admin roles](../add-users/about-admin-roles.md) for more information.</span></span> 
  
## <a name="refresh-failed"></a><span data-ttu-id="2ae0b-152">Aggiornamento non riuscito</span><span class="sxs-lookup"><span data-stu-id="2ae0b-152">Refresh failed</span></span>

 <span data-ttu-id="2ae0b-153">**Dove viene visualizzato questo messaggio:** messaggio di posta elettronica da Power BI o stato di errore nella cronologia degli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="2ae0b-153">**Where you will see this message:** Email from Power BI or failed status in the refresh history.</span></span> 
  
 <span data-ttu-id="2ae0b-154">**Causa:** A volte le credenziali dell'utente che ha effettuato l'accesso all'app modello vengono reimpostate e non aggiornate nelle impostazioni di connessione dell'app modello causando la possibilità di visualizzare gli errori di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="2ae0b-154">**Cause:** Sometimes the credentials of the user who connected to the template app are reset, and not updated in the connection settings of the template app causing the user to see refresh failure errors.</span></span> 
  
 <span data-ttu-id="2ae0b-155">**Per correggere l'errore:** In Power BI, individuare il set di dati corrispondente all'app modello di analisi di utilizzo di Microsoft 365, selezionare **Pianifica aggiornamento** e fornire le credenziali di amministratore.</span><span class="sxs-lookup"><span data-stu-id="2ae0b-155">**To fix this error:** In Power BI, find the dataset corresponding to the Microsoft 365 Usage Analytics template app, select **schedule refresh** and provide your admin credentials.</span></span> 
  
<span data-ttu-id="2ae0b-156">In caso contrario, cancellare la cache e creare di nuovo l'app modello.</span><span class="sxs-lookup"><span data-stu-id="2ae0b-156">If that doesn't work, clear the cache, and re-create the template app.</span></span>
  
  