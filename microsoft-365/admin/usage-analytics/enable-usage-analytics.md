---
title: Abilitare l'analisi dell'utilizzo di Microsoft 365
f1.keywords:
- CSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
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
ms.assetid: 9db96e9f-a622-4d5d-b134-09dcace55b6a
description: Informazioni su come avviare la raccolta dei dati per il tenant utilizzando l'app modello di analisi di utilizzo di Microsoft 365 in Power BI.
ms.openlocfilehash: 249fadce15ca2e4c979d6e1930ff0d14ccd9bc08
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/02/2020
ms.locfileid: "42355007"
---
# <a name="enable-microsoft-365-usage-analytics"></a><span data-ttu-id="1da24-103">Abilitare l'analisi dell'utilizzo di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1da24-103">Enable Microsoft 365 usage analytics</span></span>

<span data-ttu-id="1da24-104">Microsoft 365 Usage Analytics è disponibile anche per la community di Microsoft 365 US Government.</span><span class="sxs-lookup"><span data-stu-id="1da24-104">Microsoft 365 usage analytics is also available for Microsoft 365 US Government Community.</span></span>
  
## <a name="steps-to-enable-microsoft-365-usage-analytics"></a><span data-ttu-id="1da24-105">Passaggi per abilitare l'analisi dell'utilizzo di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1da24-105">Steps to enable Microsoft 365 usage analytics</span></span>

<span data-ttu-id="1da24-106">Per iniziare a utilizzare l'analisi di utilizzo di Microsoft 365, è necessario prima di tutto rendere disponibili i dati nell'interfaccia di amministrazione di Microsoft 365 e quindi avviare l'app modello in Power BI.</span><span class="sxs-lookup"><span data-stu-id="1da24-106">To get started with Microsoft 365 usage analytics you must first make the data available in the Microsoft 365 admin center, then initiate the template app in Power BI.</span></span>
  
### <a name="get-power-bi"></a><span data-ttu-id="1da24-107">Ottenere Power BI</span><span class="sxs-lookup"><span data-stu-id="1da24-107">Get Power BI</span></span>

<span data-ttu-id="1da24-108">Se non si dispone già di Power BI, è possibile [iscriversi a Power bi Pro](https://go.microsoft.com/fwlink/p/?linkid=845347).</span><span class="sxs-lookup"><span data-stu-id="1da24-108">If you don't already have Power BI, you can [sign up for Power BI Pro](https://go.microsoft.com/fwlink/p/?linkid=845347).</span></span> <span data-ttu-id="1da24-109">Seleziona **prova gratis** per iscriversi a una versione di valutazione o **Acquista ora** per ottenere Power bi Pro.</span><span class="sxs-lookup"><span data-stu-id="1da24-109">Select **Try free** to sign up for a trial, or **Buy now** to get Power BI Pro.</span></span>
  
  
<span data-ttu-id="1da24-110">È anche possibile espandere **Prodotti** per acquistare una versione di Power BI.</span><span class="sxs-lookup"><span data-stu-id="1da24-110">You can also expand **Products** to buy a version of Power BI.</span></span> 

> [!NOTE]
> <span data-ttu-id="1da24-111">È necessaria una licenza Power BI Pro per l'installazione, la personalizzazione e la distribuzione di un'app modello.</span><span class="sxs-lookup"><span data-stu-id="1da24-111">You need a Power BI Pro license to install, customize, and distribute a template app.</span></span> <span data-ttu-id="1da24-112">Per ulteriori informazioni, vedere [prerequisiti](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="1da24-112">For more information, please see [Prerequisites](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).</span></span>

<span data-ttu-id="1da24-113">È necessaria una licenza Power BI Pro per condividere il contenuto e le persone con cui condividerlo o il contenuto deve trovarsi in un'area di lavoro con una [capacità Premium](https://docs.microsoft.com/power-bi/service-premium-what-is).</span><span class="sxs-lookup"><span data-stu-id="1da24-113">You need a Power BI Pro license to share your content, and the people you share it with do too, or the content needs to be in a workspace in a [Premium capacity](https://docs.microsoft.com/power-bi/service-premium-what-is).</span></span> 
  
### <a name="enable-the-template-app"></a><span data-ttu-id="1da24-114">Abilitazione dell'app modello</span><span class="sxs-lookup"><span data-stu-id="1da24-114">Enable the template app</span></span>

<span data-ttu-id="1da24-115">Per abilitare l'app modello, è necessario essere un **amministratore globale**, un **lettore di report**, un **amministratore di Exchange**, un amministratore **di Skype for business**o un **amministratore di SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="1da24-115">To enable the template app, you have to be either a **global administrator**, **report reader**, **Exchange administrator**, **Skype for Business administrator**, or **SharePoint administrator**.</span></span> 
  
<span data-ttu-id="1da24-116">Per ulteriori informazioni, vedere informazioni [sui ruoli di amministratore](../add-users/about-admin-roles.md) .</span><span class="sxs-lookup"><span data-stu-id="1da24-116">See [About admin roles](../add-users/about-admin-roles.md) for more information.</span></span> 
  
1. <span data-ttu-id="1da24-117">Nell'interfaccia di amministrazione passare alla pagina **Report** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Utilizzo</a>.</span><span class="sxs-lookup"><span data-stu-id="1da24-117">In the admin center, go to the **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> page.</span></span> 
    
2. <span data-ttu-id="1da24-118">Nella pagina **utilizzo** individuare la scheda **Microsoft 365 Usage Analytics** e quindi fare clic su **Avvia**.</span><span class="sxs-lookup"><span data-stu-id="1da24-118">On the **Usage** page, locate the **Microsoft 365 usage analytics** card, and select **Get started**.</span></span>
    
3. <span data-ttu-id="1da24-119">Nel riquadro rapporti che si apre, impostare **rendere disponibili i dati di Microsoft 365 Usage Analytics for Power bi** to **on** \> **Save**.</span><span class="sxs-lookup"><span data-stu-id="1da24-119">On the Reports panel that opens, set **Make data available to Microsoft 365 usage analytics for Power BI** to **On** \> **Save**.</span></span> 
  
<span data-ttu-id="1da24-120">In questo modo viene avviato il processo di raccolta dei dati e il completamento verrà eseguito tra 2 e 48 ore, a seconda delle dimensioni del tenant.</span><span class="sxs-lookup"><span data-stu-id="1da24-120">This initiates the data collection process and will complete in 2 to 48 hours depending on the size of your tenant.</span></span> <span data-ttu-id="1da24-121">Il pulsante **Vai a Power bi** verrà abilitato (non più grigio) quando la raccolta dati è stata completata.</span><span class="sxs-lookup"><span data-stu-id="1da24-121">The **Go to Power BI** button will be enabled (no longer gray) when data collection is complete.</span></span> 
    
### <a name="initiate-the-template-app"></a><span data-ttu-id="1da24-122">Avviare l'app modello</span><span class="sxs-lookup"><span data-stu-id="1da24-122">Initiate the template app</span></span>

<span data-ttu-id="1da24-123">Per avviare l'app modello, è necessario essere un **amministratore globale**, un lettore di **report**, un **amministratore di Exchange**, un amministratore **di Skype for business**o un **amministratore di SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="1da24-123">To initiate the template app, you have to be either a **global administrator**, **report reader**, **Exchange administrator**, **Skype for Business administrator**, or **SharePoint administrator**.</span></span> 
  
1. <span data-ttu-id="1da24-124">Copiare l'ID tenant e selezionare **Vai a Power bi**.</span><span class="sxs-lookup"><span data-stu-id="1da24-124">Copy the tenant Id and select **Go to Power BI**.</span></span>
    
2.  <span data-ttu-id="1da24-125">Dopo aver scaricato Power BI, eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="1da24-125">When you get to Power BI, sign in.</span></span> <span data-ttu-id="1da24-126">Seleziona app->Ottieni app dal menu di spostamento.</span><span class="sxs-lookup"><span data-stu-id="1da24-126">Select Apps->Get apps from the navigation menu.</span></span>    
  
3. <span data-ttu-id="1da24-127">Nella scheda **app** Digitare Microsoft 365 nella casella di \> ricerca e quindi selezionare **Analisi utilizzo Microsoft 365** **ottenerlo subito**.</span><span class="sxs-lookup"><span data-stu-id="1da24-127">In the **Apps** tab, type Microsoft 365 in the search box and then select **Microsoft 365 usage analytics** \> **Get it now**.</span></span>

    <span data-ttu-id="1da24-128">[![Seleziona Ottieni subito](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span><span class="sxs-lookup"><span data-stu-id="1da24-128">[![Select Get it now](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span></span>
    
4.  <span data-ttu-id="1da24-129">Dopo l'installazione dell'app.</span><span class="sxs-lookup"><span data-stu-id="1da24-129">Once the app is installed.</span></span> <span data-ttu-id="1da24-130">Fare clic sul riquadro per aprirlo.</span><span class="sxs-lookup"><span data-stu-id="1da24-130">Click on the tile to open it.</span></span>

5.  <span data-ttu-id="1da24-131">Fare clic su **Esplora app** per visualizzare l'app con dati di esempio.</span><span class="sxs-lookup"><span data-stu-id="1da24-131">Click **Explore app** to view the app with sample data.</span></span> <span data-ttu-id="1da24-132">Fare clic su **Connetti** per connettere l'app ai dati dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1da24-132">Click **Connect** to connect the app to your organization’s data.</span></span>

6.  <span data-ttu-id="1da24-133">Dopo aver fatto clic su **Connetti**, nella schermata **Connetti a Microsoft 365 Usage Analytics** digitare l'ID tenant copiato nel passaggio (1) \> **successivo**.</span><span class="sxs-lookup"><span data-stu-id="1da24-133">After clicking **Connect**, on the **Connect to Microsoft 365 usage analytics** screen, type in the tenant Id you copied in step (1) \> **Next**.</span></span>
    
7. <span data-ttu-id="1da24-134">Nella schermata successiva, selezionare **OAuth2** come accesso al **Metodo** \> **di**autenticazione.</span><span class="sxs-lookup"><span data-stu-id="1da24-134">On the next screen, select **oAuth2** as the **Authentication method** \> **Sign in**.</span></span> <span data-ttu-id="1da24-135">Se si sceglie qualsiasi altro metodo di autenticazione, la connessione all'app modello avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="1da24-135">If you choose any other authentication method, the connection to the template app will fail.</span></span>
    
    ![Choose oAuth2 as authentication method](../../media/ac85a360-c278-4c60-8aa3-68f4828f1d96.png)
  
8. <span data-ttu-id="1da24-137">Dopo aver creato un'istanza dell'app modello, il Dashboard Microsoft 365 Usage Analytics sarà disponibile in Power BI sul Web.</span><span class="sxs-lookup"><span data-stu-id="1da24-137">Once the template app is instantiated the Microsoft 365 usage analytics dashboard will be available in Power BI on the web.</span></span> <span data-ttu-id="1da24-138">Il caricamento iniziale del dashboard richiederà da 2 a 30 minuti.</span><span class="sxs-lookup"><span data-stu-id="1da24-138">The initial loading of the dashboard will take between 2 to 30 minutes.</span></span>
  
<span data-ttu-id="1da24-139">Le aggregazioni a livello di tenant saranno disponibili in tutti i report.</span><span class="sxs-lookup"><span data-stu-id="1da24-139">Tenant level aggregates will be available in all reports.</span></span> <span data-ttu-id="1da24-140">I **dettagli a livello di utente diventeranno disponibili solo dopo il 1 ° o 15 ° giorno del mese di calendario dopo l'opt-in**.</span><span class="sxs-lookup"><span data-stu-id="1da24-140">**User-level details will only become available after the 1st or 15th day of the calendar month after opting in**.</span></span> <span data-ttu-id="1da24-141">Questo influirà su tutti i report in attività utente (vedere [navigare e utilizzare i report di analisi di utilizzo di Microsoft 365](navigate-and-utilize-reports.md) per suggerimenti su come visualizzare e utilizzare questi report).</span><span class="sxs-lookup"><span data-stu-id="1da24-141">This will impact all reports under User Activity (See [Navigate and utilize the reports in Microsoft 365 usage analytics](navigate-and-utilize-reports.md) for tips on how to view and use these reports).</span></span>
    
## <a name="make-the-collected-data-anonymous"></a><span data-ttu-id="1da24-142">Rendere anonimi i dati raccolti</span><span class="sxs-lookup"><span data-stu-id="1da24-142">Make the collected data anonymous</span></span>

<span data-ttu-id="1da24-143">Per rendere anonimi i dati raccolti per tutti i report è necessario essere un amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="1da24-143">To make the data that is collected for all reports anonymous, you have to be a global administrator.</span></span> <span data-ttu-id="1da24-144">In questo modo vengono nascoste informazioni identificabili, ad esempio i nomi di utenti, gruppi e siti, nei report e nell'app modello.</span><span class="sxs-lookup"><span data-stu-id="1da24-144">This will hide identifiable information such as user, group and site names in reports and in the template app .</span></span>
  
1. <span data-ttu-id="1da24-145">\> Nell'interfaccia di amministrazione, passare alla scheda **Impostazioni e** in **Servizi** , scegliere **report**. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="1da24-145">In the admin center, go to the **Settings** \> **Settings**, and under **Services** tab, choose **Reports**.</span></span>
    
2. <span data-ttu-id="1da24-146">Selezionare **report**, quindi scegliere di **visualizzare gli identificatori anonimi**.</span><span class="sxs-lookup"><span data-stu-id="1da24-146">Select **Reports**, and then choose to **Display anonymous identifiers**.</span></span> <span data-ttu-id="1da24-147">Questa impostazione viene applicata sia ai report sull'utilizzo che all'app modello.</span><span class="sxs-lookup"><span data-stu-id="1da24-147">This setting gets applied both to the usage reports as well as to the template app.</span></span>
  
3. <span data-ttu-id="1da24-148">Selezionare **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="1da24-148">Select **Save changes**.</span></span>