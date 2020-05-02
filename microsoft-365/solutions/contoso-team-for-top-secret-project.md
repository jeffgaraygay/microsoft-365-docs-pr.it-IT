---
title: Team isolato per un progetto Top-Secret di Contoso Corporation
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/01/2020
audience: ITPro
ms.topic: overview
ms.prod: microsoft-365-enterprise
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: Ent_Architecture
description: 'Riepilogo: in che modo Contoso ha utilizzato un team con isolamento di sicurezza per un progetto Top-Secret per sviluppare una nuova famiglia di prodotti e servizi.'
ms.openlocfilehash: 2da51890001a2890b2d65bc6b71537b51c335eb4
ms.sourcegitcommit: 101084f9c81616342d78493232d8f13f5ffa4ddf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/01/2020
ms.locfileid: "44003212"
---
# <a name="isolated-team-for-a-top-secret-project-of-the-contoso-corporation"></a><span data-ttu-id="d2d53-103">Team isolato per un progetto Top-Secret di Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="d2d53-103">Isolated team for a top-secret project of the Contoso Corporation</span></span>

<span data-ttu-id="d2d53-104">Dopo un Executive fuori sede, il CEO di Contoso ha ordinato lo sviluppo di una nuova famiglia di prodotti e servizi che potrebbe raddoppiare gli utili di Contoso nei prossimi cinque anni.</span><span class="sxs-lookup"><span data-stu-id="d2d53-104">After an executive offsite, Contoso’s CEO ordered the development of a new suite of products and services that could double Contoso’s profits in the next five years.</span></span> <span data-ttu-id="d2d53-105">Il progetto Top-Secret per sviluppare il piano aziendale, ingegneristico e di mercato è stato denominato **Project 2x** e il personale chiave in tutta la società sono stati reclutati.</span><span class="sxs-lookup"><span data-stu-id="d2d53-105">The top-secret project to develop the business, engineering, and market plan was named **Project 2X** and key staff across the company were recruited.</span></span> 

<span data-ttu-id="d2d53-106">Le sequenze temporali per la ricerca e lo sviluppo sono state rigorose, il che significa che la collaborazione deve essere efficiente e fornire riunioni sicure, conversazioni e archiviazione dei file.</span><span class="sxs-lookup"><span data-stu-id="d2d53-106">The timelines for research and development were tight, which meant that collaboration had to be efficient and provide for secure meetings, ongoing conversations, and file storage.</span></span>

<span data-ttu-id="d2d53-107">I risultati finali risultanti per Project 2X sono stati piani aziendali, specifiche di prodotti e di ingegneria e materiali di marketing e pianificazioni in formato Word, Excel e PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="d2d53-107">The resulting deliverables for Project 2X were business plans, product and engineering specifications, and marketing materials and schedules in the form of Word, Excel, and PowerPoint files.</span></span> 

<span data-ttu-id="d2d53-108">A causa della loro natura sensibile, l'accesso a questi file è stato:</span><span class="sxs-lookup"><span data-stu-id="d2d53-108">Due to their sensitive nature, access to these files were:</span></span>

- <span data-ttu-id="d2d53-109">Limitato ai membri del team di Project 2X.</span><span class="sxs-lookup"><span data-stu-id="d2d53-109">Restricted to Project 2X team members.</span></span>
- <span data-ttu-id="d2d53-110">Crittografati e protetti con le autorizzazioni per consentire l'accesso solo ai membri del team di Project 2X, anche se i file sono stati distribuiti all'esterno delle cartelle protette.</span><span class="sxs-lookup"><span data-stu-id="d2d53-110">Encrypted and protected with permissions to allow access only to Project 2X team members, even if the files were distributed outside of their secured folders.</span></span>

<span data-ttu-id="d2d53-111">Il personale IT di Contoso ha utilizzato un [team con isolamento di sicurezza](secure-teams-security-isolation.md) per Project 2x e questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="d2d53-111">Contoso IT staff used a [team with security isolation](secure-teams-security-isolation.md) for Project 2X and these steps.</span></span>

## <a name="step-1-created-a-private-team"></a><span data-ttu-id="d2d53-112">Passaggio 1: creazione di un team privato</span><span class="sxs-lookup"><span data-stu-id="d2d53-112">Step 1: Created a private team</span></span>

<span data-ttu-id="d2d53-113">In primo luogo, per proteggere l'accesso al sito di SharePoint sottostante per il team, gli amministratori IT di Contoso hanno configurato i [criteri di accesso di SharePoint consigliati](../enterprise/sharepoint-file-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="d2d53-113">First, to protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](../enterprise/sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="d2d53-114">Successivamente, un amministratore IT di Contoso ha creato un nuovo team privato denominato Project 2X e aggiunto gli account utente del personale di Project 2X come membri.</span><span class="sxs-lookup"><span data-stu-id="d2d53-114">Next, a Contoso IT administrator created a new private team named Project 2X and added the user accounts of Project 2X staff as members.</span></span>

<span data-ttu-id="d2d53-115">Per informazioni dettagliate sulla configurazione, vedere [creare un team privato](secure-teams-security-isolation.md#create-a-private-team).</span><span class="sxs-lookup"><span data-stu-id="d2d53-115">For the configuration details, see [Create a private team](secure-teams-security-isolation.md#create-a-private-team).</span></span>

## <a name="step-2-created-a-sensitivity-label-for-the-project-2x-team"></a><span data-ttu-id="d2d53-116">Passaggio 2: creazione di un'etichetta di riservatezza per il team di Project 2X</span><span class="sxs-lookup"><span data-stu-id="d2d53-116">Step 2: Created a sensitivity label for the Project 2X team</span></span>

<span data-ttu-id="d2d53-117">Gli amministratori di Contoso hanno creato una nuova etichetta di riservatezza denominata **Project 2x** che:</span><span class="sxs-lookup"><span data-stu-id="d2d53-117">Contoso admins created a new sensitivity label named **Project 2X** that:</span></span>

- <span data-ttu-id="d2d53-118">Richiede la crittografia.</span><span class="sxs-lookup"><span data-stu-id="d2d53-118">Requires encryption.</span></span>
- <span data-ttu-id="d2d53-119">Consente le autorizzazioni di creazione condivisa per il gruppo Project 2X Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d2d53-119">Allows Co-Author permissions for the Project 2X Microsoft 365 group.</span></span>

<span data-ttu-id="d2d53-120">I file nella sezione **Documents** del progetto sottostante 2x sito di SharePoint sono stati protetti da:</span><span class="sxs-lookup"><span data-stu-id="d2d53-120">Files in the **Documents** section of the underlying Project 2X SharePoint site were protected by:</span></span>

- <span data-ttu-id="d2d53-121">Le autorizzazioni per il sito, che consentono l'accesso solo ai membri del gruppo Project 2X Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d2d53-121">The site permissions, which only allow access to members of the Project 2X Microsoft 365 group.</span></span>
- <span data-ttu-id="d2d53-122">L'etichetta di riservatezza del progetto 2X, con la crittografia e le autorizzazioni che viaggiano con il file se sono state spostate o copiate dal sito.</span><span class="sxs-lookup"><span data-stu-id="d2d53-122">The Project 2X sensitivity label, with encryption and permissions that travel with the file if it is moved or copied from the site.</span></span>

<span data-ttu-id="d2d53-123">Per informazioni dettagliate sulla configurazione, vedere [Create a Sensitivity label](secure-teams-security-isolation.md#create-a-sensitivity-label).</span><span class="sxs-lookup"><span data-stu-id="d2d53-123">For the configuration details, see [Create a sensitivity label](secure-teams-security-isolation.md#create-a-sensitivity-label).</span></span>

## <a name="step-3-configured-the-underlying-sharepoint-site"></a><span data-ttu-id="d2d53-124">Passaggio 3: configurazione del sito di SharePoint sottostante</span><span class="sxs-lookup"><span data-stu-id="d2d53-124">Step 3: Configured the underlying SharePoint site</span></span>

<span data-ttu-id="d2d53-125">In primo luogo, per proteggere l'accesso al sito di SharePoint sottostante per il team, gli amministratori IT di Contoso hanno configurato i [criteri di accesso di SharePoint consigliati](../enterprise/sharepoint-file-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="d2d53-125">First, to protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](../enterprise/sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="d2d53-126">Successivamente, sono state configurate le impostazioni di autorizzazione aggiuntive per il sito per impedire che Project 2X condivida l'accesso al sito.</span><span class="sxs-lookup"><span data-stu-id="d2d53-126">Next, they configured additional permission settings for the site to prevent Project 2X from sharing access to the site.</span></span> <span data-ttu-id="d2d53-127">Per informazioni dettagliate sulla configurazione, vedere [impostazioni di SharePoint per un team con isolamento della sicurezza](secure-teams-security-isolation.md#sharepoint-settings).</span><span class="sxs-lookup"><span data-stu-id="d2d53-127">For the configuration details, see [SharePoint settings for a team with security isolation](secure-teams-security-isolation.md#sharepoint-settings).</span></span>

<span data-ttu-id="d2d53-128">Ecco la configurazione risultante del team di Project 2X.</span><span class="sxs-lookup"><span data-stu-id="d2d53-128">Here is the resulting configuration of the Project 2X team.</span></span>

![La configurazione risultante del team di Project 2X](../media/contoso-team-for-top-secret-project/contoso-team-for-top-secret-project.png)

 ## <a name="step-4-trained-project-2x-team-members"></a><span data-ttu-id="d2d53-130">Passaggio 4: formazione dei membri del team di Project 2X</span><span class="sxs-lookup"><span data-stu-id="d2d53-130">Step 4: Trained Project 2X team members</span></span>

<span data-ttu-id="d2d53-131">Il personale di sicurezza Contoso ha preparato i membri del team del progetto 2X in un corso obbligatorio che ha eseguito i seguenti controlli:</span><span class="sxs-lookup"><span data-stu-id="d2d53-131">Contoso security staff trained the Project 2X team members in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="d2d53-132">Come accedere al nuovo team di Project 2X, utilizzare riunioni e chat e come collaborare ai file del team.</span><span class="sxs-lookup"><span data-stu-id="d2d53-132">How to access the new Project 2X team, use meetings and chats, and how to collaborate on team files.</span></span>
- <span data-ttu-id="d2d53-133">Come creare nuovi file nel team e caricare nuovi file creati localmente.</span><span class="sxs-lookup"><span data-stu-id="d2d53-133">How to create new files in the team and upload new files created locally.</span></span>
- <span data-ttu-id="d2d53-134">Dimostrazione del modo in cui il criterio DLP blocca la condivisione esterna dei file.</span><span class="sxs-lookup"><span data-stu-id="d2d53-134">A demonstration of how the DLP policy blocks files from being shared externally.</span></span>
- <span data-ttu-id="d2d53-135">Come assegnare etichette ai file con l'etichetta di sensitivity di Project 2X.</span><span class="sxs-lookup"><span data-stu-id="d2d53-135">How to label files with the Project 2X sensitivity label.</span></span>
- <span data-ttu-id="d2d53-136">Dimostrazione del modo in cui l'etichetta del progetto 2X protegge un file anche quando lascia il team.</span><span class="sxs-lookup"><span data-stu-id="d2d53-136">A demonstration of how the Project 2X  label protects a file even when it leaves the team.</span></span>

<span data-ttu-id="d2d53-137">Il risultato finale è un ambiente sicuro in cui i membri del team di Project 2X hanno collaborato in un ambiente sicuro per chat, riunioni e file.</span><span class="sxs-lookup"><span data-stu-id="d2d53-137">The end result was a secure environment in which Project 2X team members collaborated in a secure environment for chats, meetings, and files.</span></span>

<span data-ttu-id="d2d53-138">Di seguito è riportato un esempio di un file archiviato nel sito del progetto 2X sottostante con l'etichetta di riservatezza del progetto 2X assegnata.</span><span class="sxs-lookup"><span data-stu-id="d2d53-138">Here is an example of a file stored in the underlying Project 2X site with the Project 2X sensitivity label assigned.</span></span>

![Un esempio di un file archiviato nel sito di progetto 2X sottostante](../media/contoso-team-for-top-secret-project/contoso-team-for-top-secret-project-example.png)

<span data-ttu-id="d2d53-140">In una coppia di istanze, Project 2X membri del team hanno scaricato i file protetti dall'etichetta Project 2X su un'unità locale per il lavoro offline.</span><span class="sxs-lookup"><span data-stu-id="d2d53-140">In a couple of instances, Project 2X team members downloaded files protected by the Project 2X label to a local drive for offline work.</span></span> <span data-ttu-id="d2d53-141">Tuttavia, dopo che sono state richieste le credenziali per l'apertura, si sono accorti del loro errore e li hanno eliminati.</span><span class="sxs-lookup"><span data-stu-id="d2d53-141">However, after being prompted for credentials when opening them, they realized their mistake and deleted them.</span></span>

<span data-ttu-id="d2d53-142">A causa dell'ambiente di collaborazione dei team e delle funzionalità di sicurezza di Microsoft 365, i dettagli di Project 2X sono stati mantenuti segreti per tutta la durata del progetto.</span><span class="sxs-lookup"><span data-stu-id="d2d53-142">Because of the collaboration environment of Teams and the security features of Microsoft 365, the details of Project 2X were kept secret for the duration of the project.</span></span> <span data-ttu-id="d2d53-143">Contoso ha annunciato i propri piani ed è in fase di implementazione dei nuovi prodotti e servizi per la gioia dei suoi clienti e investitori e per il disappunto dei suoi concorrenti.</span><span class="sxs-lookup"><span data-stu-id="d2d53-143">Contoso announced its plans and is in the process of rolling out the new products and services to the delight of its customers and investors and the chagrin of its competitors.</span></span>

## <a name="next-step"></a><span data-ttu-id="d2d53-144">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="d2d53-144">Next step</span></span>

<span data-ttu-id="d2d53-145">[Distribuire un team con isolamento di sicurezza](secure-teams-security-isolation.md) nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d2d53-145">[Deploy a team with security isolation](secure-teams-security-isolation.md) in your organization.</span></span>
