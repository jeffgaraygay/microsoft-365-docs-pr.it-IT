---
title: Identità e prerequisiti di accesso dei dispositivi per la sincronizzazione dell’hash delle password in ambiente di testing di Microsoft 365
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 04/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Creare un ambiente Microsoft 365 per testare l'identità e l’accesso del dispositivo con i prerequisiti per l'autenticazione di sincronizzazione hash delle password.
ms.openlocfilehash: 274f73b1cd6a925b972ab14417c9d854c48c2f00
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "34074156"
---
# <a name="identity-and-device-access-prerequisites-for-password-hash-synchronization-in-your-microsoft-365-test-environment"></a><span data-ttu-id="80af5-103">Identità e prerequisiti di accesso dei dispositivi per la sincronizzazione dell’hash delle password in ambiente di testing di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="80af5-103">Identity and device access prerequisites for password hash synchronization in your Microsoft 365 test environment</span></span>

<span data-ttu-id="80af5-104">[Configurazioni di identità e accesso dei dispositivi](microsoft-365-policies-configurations.md) sono un set di configurazioni e i criteri di accesso condizionale per proteggere l'accesso a tutti i servizi integrati con Azure Active Directory (Azure AD), tra cui Office 365 ed Enterprise Mobility + Security (EMS) in Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="80af5-104">[Identity and device access configurations](microsoft-365-policies-configurations.md) are a set of features and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD), including Office 365 and Enterprise Mobility + Security (EMS) in Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="80af5-105">In questo articolo viene descritto come configurare un ambiente di testing di Microsoft 365 che soddisfi i requisiti di[Active Directory con configurazione dei prerequisiti di sincronizzazione dell’hash delle password](identity-access-prerequisites.md#prerequisites) per l’identità e l’accesso dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="80af5-105">This article describes how to configure a Microsoft 365 test environment that meets the requirements of the [Active Directory with password hash sync prerequisite configuration](identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span>

<span data-ttu-id="80af5-106">Le fasi principali della configurazione dell'ambiente di testing sono otto:</span><span class="sxs-lookup"><span data-stu-id="80af5-106">There are two phases to setting up this test environment:</span></span>

1.  <span data-ttu-id="80af5-107">Creare un’organizzazione simulata con ambiente di testing per la sincronizzazione dell’hash delle password</span><span class="sxs-lookup"><span data-stu-id="80af5-107">Create a simulated enterprise with password hash sync test environment</span></span>
2.  <span data-ttu-id="80af5-108">Configurare l’accesso Single Sign-On facile di Azure AD</span><span class="sxs-lookup"><span data-stu-id="80af5-108">Configure Azure AD seamless single sign-on</span></span>
3.  <span data-ttu-id="80af5-109">Configurare le posizioni specifiche</span><span class="sxs-lookup"><span data-stu-id="80af5-109">Configure named locations</span></span>
4.  <span data-ttu-id="80af5-110">Configurare il writeback delle password</span><span class="sxs-lookup"><span data-stu-id="80af5-110">Configure password writeback</span></span>
5.  <span data-ttu-id="80af5-111">Configurare la reimpostazione self-service delle password per tutti gli account utente.</span><span class="sxs-lookup"><span data-stu-id="80af5-111">Configure self-service password reset for all user accounts</span></span>
6.  <span data-ttu-id="80af5-112">Configurare l'autenticazione a più fattori per tutti gli account utente.</span><span class="sxs-lookup"><span data-stu-id="80af5-112">Configure multifactor authentication for all user accounts</span></span>
7.  <span data-ttu-id="80af5-113">Abilitare Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="80af5-113">Azure AD Identity Protection</span></span>
8.  <span data-ttu-id="80af5-114">Abilitare l'autenticazione moderna per Exchange Online e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="80af5-114">Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

## <a name="phase-1-build-out-your-simulated-enterprise-with-password-hash-sync-microsoft-365-test-environment"></a><span data-ttu-id="80af5-115">Fase 1: creare un’organizzazione simulata con ambiente di testing per la sincronizzazione dell’hash delle password di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="80af5-115">Phase 1: Build out your simulated enterprise with password hash sync Microsoft 365 test environment</span></span>

<span data-ttu-id="80af5-116">Seguire le istruzioni contenute in [Sincronizzazione hash delle password](password-hash-sync-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="80af5-116">Follow the instructions in [Password hash synchronization](password-hash-sync-m365-ent-test-environment.md).</span></span>
<span data-ttu-id="80af5-117">Di seguito è riportata la configurazione risultante.</span><span class="sxs-lookup"><span data-stu-id="80af5-117">Here is the resulting configuration.</span></span>

![L'organizzazione simulata con ambiente di testing per la sincronizzazione hash delle password](media/password-hash-sync-m365-ent-test-environment/Phase3.png)
 
## <a name="phase-2-configure-azure-ad-seamless-single-sign-on"></a><span data-ttu-id="80af5-119">Fase 2: configurare l’accesso Single Sign-on facile di Azure AD</span><span class="sxs-lookup"><span data-stu-id="80af5-119">Phase 2: Configure Azure AD seamless single sign-on</span></span>

<span data-ttu-id="80af5-120">Seguire le istruzioni contenute nella [Fase 2 della guida al lab di test per l’accesso Single Sign-on facile di Azure AD](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso).</span><span class="sxs-lookup"><span data-stu-id="80af5-120">Follow the instructions in [Phase 2 of the Azure AD Seamless Single Sign-on Test Lab Guide](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso).</span></span>

## <a name="phase-3-configure-named-locations"></a><span data-ttu-id="80af5-121">Fase 3: configurare le posizioni specifiche</span><span class="sxs-lookup"><span data-stu-id="80af5-121">Phase 3: Configure named locations</span></span>

<span data-ttu-id="80af5-122">Prima di tutto determinare gli indirizzi IP pubblici o gli intervalli di indirizzi usati all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="80af5-122">First, determine the public IP addresses or address ranges used by your organization.</span></span>

<span data-ttu-id="80af5-123">Quindi, seguire le istruzioni contenute in [Configurare le posizioni specifiche in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) per aggiungere gli indirizzi o gli intervalli di indirizzi come posizioni specifiche.</span><span class="sxs-lookup"><span data-stu-id="80af5-123">Next, follow the instructions in [Configure named locations in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) to add the addresses or address ranges as named locations.</span></span> 

## <a name="phase-4-configure-password-writeback"></a><span data-ttu-id="80af5-124">Fase 4: configurare il writeback delle password</span><span class="sxs-lookup"><span data-stu-id="80af5-124">Phase 4: Configure password writeback</span></span>

<span data-ttu-id="80af5-125">Seguire le istruzioni contenute nella [Fase 2 della guida al lab di test per il writeback delle password.](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain)</span><span class="sxs-lookup"><span data-stu-id="80af5-125">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

## <a name="phase-5-configure-self-service-password-reset"></a><span data-ttu-id="80af5-126">Fase 5: configurare la reimpostazione delle password self-service </span><span class="sxs-lookup"><span data-stu-id="80af5-126">Phase 5: Configure self-service password reset</span></span>

<span data-ttu-id="80af5-127">Seguire le istruzioni contenute nella [Fase 3 della guida al lab di test per la reimpostazione della password](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span><span class="sxs-lookup"><span data-stu-id="80af5-127">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span></span> 

<span data-ttu-id="80af5-128">Quando si abilita la reimpostazione della password degli account in un determinato gruppo di Azure AD, aggiungere gli account al gruppo **Reimpostazione della password**:</span><span class="sxs-lookup"><span data-stu-id="80af5-128">When enabling password reset for the accounts in a specific Azure AD group, add these accounts to the **Password reset** group:</span></span>

- <span data-ttu-id="80af5-129">Utente 2</span><span class="sxs-lookup"><span data-stu-id="80af5-129">User: %2</span></span>
- <span data-ttu-id="80af5-130">Utente 3</span><span class="sxs-lookup"><span data-stu-id="80af5-130">User Defined 3</span></span>
- <span data-ttu-id="80af5-131">Utente 4</span><span class="sxs-lookup"><span data-stu-id="80af5-131">User: %4</span></span>
- <span data-ttu-id="80af5-132">Utente 5</span><span class="sxs-lookup"><span data-stu-id="80af5-132">User 5</span></span>

<span data-ttu-id="80af5-133">Testare la reimpostazione della password solo per l'account Utente 2.</span><span class="sxs-lookup"><span data-stu-id="80af5-133">Next, you test password reset for the User 2 account.</span></span>

## <a name="phase-6-configure-multi-factor-authentication"></a><span data-ttu-id="80af5-134">Fase 6: configurare l’autenticazione a più fattori</span><span class="sxs-lookup"><span data-stu-id="80af5-134">Phase 6: Configure multi-factor authentication</span></span>

<span data-ttu-id="80af5-135">Seguire le istruzioni contenute nella [Fase 2 della guida al lab di test per autenticazione a più fattori](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) per gli account utente seguenti:</span><span class="sxs-lookup"><span data-stu-id="80af5-135">Follow the instructions in [Phase 2 of the multi-factor authentication Test Lab Guide](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) for the following user accounts:</span></span>

- <span data-ttu-id="80af5-136">Utente 2</span><span class="sxs-lookup"><span data-stu-id="80af5-136">User: %2</span></span>
- <span data-ttu-id="80af5-137">Utente 3</span><span class="sxs-lookup"><span data-stu-id="80af5-137">User Defined 3</span></span>
- <span data-ttu-id="80af5-138">Utente 4</span><span class="sxs-lookup"><span data-stu-id="80af5-138">User: %4</span></span>
- <span data-ttu-id="80af5-139">Utente 5</span><span class="sxs-lookup"><span data-stu-id="80af5-139">User 5</span></span>

<span data-ttu-id="80af5-140">Testare l'autenticazione a più fattori solo per l'account Utente 2.</span><span class="sxs-lookup"><span data-stu-id="80af5-140">Enable and test multi-factor authentication for the User 2 account.</span></span>

## <a name="phase-7-enable-azure-ad-identity-protection"></a><span data-ttu-id="80af5-141">Fase 7: abilitare Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="80af5-141">Phase 7: Enable Azure AD Identity Protection</span></span>

<span data-ttu-id="80af5-142">Seguire le istruzioni contenute nella [Fase 2 della guida al lab di test per Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-enable-and-use-azure-ad-identity-protection).</span><span class="sxs-lookup"><span data-stu-id="80af5-142">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-enable-and-use-azure-ad-identity-protection).</span></span> 

## <a name="phase-8-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="80af5-143">Fase 8: abilitare l'autenticazione moderna per Exchange Online e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="80af5-143">Phase 8: Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="80af5-144">Per Exchange Online, fare clic su [queste istruzioni](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span><span class="sxs-lookup"><span data-stu-id="80af5-144">For Exchange Online, follow [these instructions](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span></span> 

<span data-ttu-id="80af5-145">Per Skype for Business Online:</span><span class="sxs-lookup"><span data-stu-id="80af5-145">Skype for Business Online</span></span>

1. <span data-ttu-id="80af5-146">Connettere a [Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="80af5-146">[Migrate to Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell). (Administrator)</span></span>

2. <span data-ttu-id="80af5-147">Eseguire questo comando.</span><span class="sxs-lookup"><span data-stu-id="80af5-147">Run this command:</span></span>

  ```
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. <span data-ttu-id="80af5-148">Verificare che la modifica sia stata applicata con questo comando.</span><span class="sxs-lookup"><span data-stu-id="80af5-148">Ensure that the download was successful with this command.</span></span>

  ```
  Get-CsOAuthConfiguration
  ```

<span data-ttu-id="80af5-149">Il risultato è un ambiente di testing che soddisfa i requisiti di [Active Directory con configurazione dei prerequisiti di sincronizzazione dell’hash delle password](identity-access-prerequisites.md#prerequisites) per l’identità e l’accesso dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="80af5-149">The result is a test environment that meets the requirements of the [Active Directory with password hash sync prerequisite configuration](identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span> 

## <a name="next-step"></a><span data-ttu-id="80af5-150">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="80af5-150">Next step</span></span>

<span data-ttu-id="80af5-151">Usare i [criteri comuni di identità e accesso ai dispositivi](identity-access-policies.md) per configurare i criteri basati sui prerequisiti e proteggere identità e dispositivi.</span><span class="sxs-lookup"><span data-stu-id="80af5-151">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites and test protection for identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="80af5-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="80af5-152">See also</span></span>

[<span data-ttu-id="80af5-153">Guide al lab di test per identità aggiuntive</span><span class="sxs-lookup"><span data-stu-id="80af5-153">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="80af5-154">Fase 2: identità</span><span class="sxs-lookup"><span data-stu-id="80af5-154">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="80af5-155">Guide al lab di test di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="80af5-155">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

<span data-ttu-id="80af5-156">[Distribuzione di Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="80af5-156">[Microsoft 365 Enterprise deployment](deploy-microsoft-365-enterprise.md)</span></span>

[<span data-ttu-id="80af5-157">Documentazione di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="80af5-157">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)