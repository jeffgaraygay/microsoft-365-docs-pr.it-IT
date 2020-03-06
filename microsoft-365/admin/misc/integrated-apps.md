---
title: Attivazione o disattivazione di App integrate
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7e453a40-66df-44ab-92a1-96786cb7fb34
description: Vengono fornite informazioni sulle app integrate e su come attivarle per consentire alle app di terze parti di accedere ai dati di Office 365 degli utenti.
ms.openlocfilehash: 3c7c92e16b375fc374563e87ea2f6166c7384a29
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/02/2020
ms.locfileid: "42361387"
---
# <a name="turning-integrated-apps-on-or-off"></a><span data-ttu-id="cf178-103">Attivazione o disattivazione di App integrate</span><span class="sxs-lookup"><span data-stu-id="cf178-103">Turning Integrated Apps on or off</span></span>

<span data-ttu-id="cf178-p101">Se l'opzione App integrate è attivata, gli utenti dell'organizzazione possono consentire l'accesso di app di terze parti alle loro informazioni di Office 365. Un'eventuale app di terze parti usata da qualcuno potrebbe ad esempio chiedere l'autorizzazione per accedere al calendario e per modificare i file contenuti in una cartella di OneDrive di questa persona.</span><span class="sxs-lookup"><span data-stu-id="cf178-p101">When Integrated Apps is turned on, users in your organization can allow third-party apps to access their Office 365 information. For example, when someone uses a third-party app, that app might ask for permission to access their calendar and to edit files that are in a OneDrive folder.</span></span>

## <a name="turning-integrated-apps-on-or-off"></a><span data-ttu-id="cf178-106">Attivazione o disattivazione di App integrate</span><span class="sxs-lookup"><span data-stu-id="cf178-106">Turning Integrated Apps on or off</span></span>
<span data-ttu-id="cf178-107"><a name="__toc379982114"> </a></span><span class="sxs-lookup"><span data-stu-id="cf178-107"><a name="__toc379982114"> </a></span></span>

<span data-ttu-id="cf178-108">Ecco come attivare o disattivare App integrate.</span><span class="sxs-lookup"><span data-stu-id="cf178-108">Here's how to turn Integrated Apps on or off.</span></span>

1. <span data-ttu-id="cf178-109">Nell'interfaccia di amministrazione, andare alla pagina dei [componenti &amp; aggiuntivi dei servizi](https://go.microsoft.com/fwlink/p/?linkid=2053743) di **Impostazioni** \> e quindi selezionare **app integrate**.</span><span class="sxs-lookup"><span data-stu-id="cf178-109">In the admin center, go to the **Settings** \> [Services &amp; add-ins](https://go.microsoft.com/fwlink/p/?linkid=2053743) page, and then select **Integrated apps**.</span></span>

2. <span data-ttu-id="cf178-110">Nella pagina **app integrate** , selezionare l'opzione per abilitare o disabilitare le app integrate.</span><span class="sxs-lookup"><span data-stu-id="cf178-110">On the **Integrated Apps** page, select the option to turn Integrated Apps on or off.</span></span>

## <a name="more-info-on-integrated-apps"></a><span data-ttu-id="cf178-111">Altre informazioni sulle app integrate</span><span class="sxs-lookup"><span data-stu-id="cf178-111">More info on Integrated Apps</span></span>
<span data-ttu-id="cf178-112"><a name="__toc379982114"> </a></span><span class="sxs-lookup"><span data-stu-id="cf178-112"><a name="__toc379982114"> </a></span></span>

<span data-ttu-id="cf178-113">Le app integrate possono essere create nell'organizzazione oppure provenire da un'altra organizzazione di Office 365 o da una terza parte.</span><span class="sxs-lookup"><span data-stu-id="cf178-113">An integrated app can be created from within your own organization, or it can come from another Office 365 organization or a third-party.</span></span>

<span data-ttu-id="cf178-p102">Se l'opzione App integrate è attivata, le eventuali app che vengono usate chiedono l'autorizzazione per impostare il livello di accesso necessario per accedere alle informazioni dell'utente. Ogni utente può concedere l'accesso solo alle app di cui è proprietario e che accedono alle proprie informazioni di Office 365. Non può invece concedere l'accesso alle informazioni degli altri utenti.</span><span class="sxs-lookup"><span data-stu-id="cf178-p102">When Integrated Apps is turned on and an app is used, the app asks for permission to set the level of access it needs when it accesses the user's information. A user can give access only to apps they own that access their Office 365 information. They can't give an app access to any other user's information.</span></span>

<span data-ttu-id="cf178-p103">Con App integrate di Office 365 vengono usati due tipi di autorizzazione, ossia le autorizzazioni utente e le autorizzazioni di amministratore. Se ad esempio le app integrate sono abilitate per l'organizzazione e un utente usa un'app di terze parti, quest'ultima può chiedere l'autorizzazione dell'utente per leggere i dettagli del suo profilo, modificare o eliminare file, leggere gli elementi contenuti nelle raccolte siti e inviare messaggi di posta elettronica a nome dell'utente.</span><span class="sxs-lookup"><span data-stu-id="cf178-p103">There are two kinds of permissions that are used when using Integrated Apps in Office 365: user permissions and admin permissions. For example, when your organization is enabled for Integrated Apps and a user uses a third-party app, the app might ask for the user's permission to read their user profile details, edit or delete their files, read items contained in site collections, and send email as that user.</span></span>

![Autorizzazioni utente per App integrate](../../media/bb9a6cf8-da39-4ac0-9e40-cde03a81c121.gif)

<span data-ttu-id="cf178-120">Se un amministratore registra un'app per tutti gli utenti di un'organizzazione, gli viene chiesto l'autorizzazione per consentire all'app di accedere alle informazioni e alle risorse nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="cf178-120">If an admin registers an app for all users in an organization, he or she is asked for permission to let that app access information and resources in the organization.</span></span> <span data-ttu-id="cf178-121">Quando in seguito altri utenti dell'organizzazione useranno l'app, non visualizzeranno la richiesta di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="cf178-121">After this, when other users in the organization use that app, they won't be asked for permission.</span></span> <span data-ttu-id="cf178-122">L'amministratore che registra un'app deve verificare l'attendibilità di chi la pubblica.</span><span class="sxs-lookup"><span data-stu-id="cf178-122">When an admin registers an app, that admin must make sure that they trust that app's publisher.</span></span> <span data-ttu-id="cf178-123">Per informazioni sulla registrazione di app, vedere [Aggiunta, aggiornamento e rimozione di applicazioni](https://go.microsoft.com/fwlink/p/?LinkID=518600).</span><span class="sxs-lookup"><span data-stu-id="cf178-123">For details on registering an app, see [Adding, Updating and Removing an Application](https://go.microsoft.com/fwlink/p/?LinkID=518600).</span></span>

![Autorizzazioni dell'amministratore per App integrate](../../media/e24aa504-bf10-446c-a9d5-45a6f2655187.gif)

<span data-ttu-id="cf178-p105">Se l'opzione App integrate viene disattivata, le app già installate e con l'autorizzazione per accedere alle informazioni non verranno disinstallate e le autorizzazioni non verranno rimosse. Anche se questa opzione è disattivata, gli amministratori possono comunque registrare app per renderle disponibili agli utenti e consentire l'accesso alle informazioni. Per informazioni sulla rimozione di un'applicazione registrata e delle relative autorizzazioni, vedere [Aggiunta, aggiornamento e rimozione di applicazioni](https://go.microsoft.com/fwlink/?LinkID=518600&amp;clcid=0x409).</span><span class="sxs-lookup"><span data-stu-id="cf178-p105">If Integrated Apps is turned off, apps that have already been installed and have permission to access information won't be uninstalled, and the permissions won't be removed. Even though Integrated Apps is turned off, admins can still register apps to make them available to their users and allow those apps access to the users' information. For details on removing a registered application and it's permissions, see [Adding, Updating and Removing an Application](https://go.microsoft.com/fwlink/?LinkID=518600&amp;clcid=0x409).</span></span>

