---
title: Prerequisiti per l’accesso di identità e dispositivi per l’autenticazione pass-through nell’ambiente di testing di Microsoft 365
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
description: Creare un ambiente Microsoft 365 per testare l’accesso di identità e dispositivi con i prerequisiti per l'autenticazione pass-through.
ms.openlocfilehash: 348885b2cc7a0d6134dce49cd0a2a39706c5e71d
ms.sourcegitcommit: 1d376287f6c1bf5174873e89ed4bf7bb15bc13f6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/14/2019
ms.locfileid: "38627490"
---
# <a name="identity-and-device-access-prerequisites-for-pass-through-authentication-in-your-microsoft-365-test-environment"></a><span data-ttu-id="a028c-103">Prerequisiti per l’accesso di identità e dispositivi per l’autenticazione pass-through nell’ambiente di testing di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a028c-103">Identity and device access prerequisites for pass-through authentication in your Microsoft 365 test environment</span></span>

<span data-ttu-id="a028c-104">Le [configurazioni dell’accesso di identità e accesso dei dispositivi](microsoft-365-policies-configurations.md) sono una serie configurazioni e criteri di accesso condizionale per proteggere l'accesso a tutti i servizi integrati con Azure Active Directory (Azure AD), tra cui Office 365 ed Enterprise Mobility + Security (EMS) in Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="a028c-104">[Identity and device access configurations](microsoft-365-policies-configurations.md) are a set of configurations and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD), including Office 365 and Enterprise Mobility + Security (EMS) in Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="a028c-105">In questo articolo viene descritto come è possibile configurare un ambiente di testing di Microsoft 365 che soddisfi i requisiti di [Configurazione dei prerequisiti di autenticazione pass-through ](identity-access-prerequisites.md#prerequisites) per l’accesso di identità e dispositivi.</span><span class="sxs-lookup"><span data-stu-id="a028c-105">This article describes how you can configure a Microsoft 365 test environment that meets the requirements of the [Pass-through authentication prerequisite configuration](identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span>

<span data-ttu-id="a028c-106">Le fasi principali della configurazione dell'ambiente di testing sono otto:</span><span class="sxs-lookup"><span data-stu-id="a028c-106">There are eight phases to setting up this test environment:</span></span>

1.  <span data-ttu-id="a028c-107">Creare un’organizzazione fittizia con autenticazione pass-through per l’ambiente di testing di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a028c-107">Build out your simulated enterprise with pass-through authentication Microsoft 365 test environment</span></span>
2.  <span data-ttu-id="a028c-108">Configurare l’accesso unificato Single Sign-On di Azure AD</span><span class="sxs-lookup"><span data-stu-id="a028c-108">Configure Azure AD seamless single sign-on</span></span>
3.  <span data-ttu-id="a028c-109">Configurare le posizioni specifiche</span><span class="sxs-lookup"><span data-stu-id="a028c-109">Configure named locations</span></span>
4.  <span data-ttu-id="a028c-110">Configurare il writeback delle password</span><span class="sxs-lookup"><span data-stu-id="a028c-110">Configure password writeback</span></span>
5.  <span data-ttu-id="a028c-111">Configurare la reimpostazione self-service delle password</span><span class="sxs-lookup"><span data-stu-id="a028c-111">Configure self-service password reset</span></span>
6.  <span data-ttu-id="a028c-112">Configurare l’autenticazione a più fattori</span><span class="sxs-lookup"><span data-stu-id="a028c-112">Configure multifactor authentication</span></span>
7.  <span data-ttu-id="a028c-113">Abilitare Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="a028c-113">Enable Azure AD Identity Protection</span></span>
8.  <span data-ttu-id="a028c-114">Abilitare l'autenticazione moderna per Exchange Online e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="a028c-114">Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

## <a name="phase-1-build-out-your-simulated-enterprise-with-pass-through-authentication-microsoft-365-test-environment"></a><span data-ttu-id="a028c-115">Fase 1: creare un’organizzazione fittizia con autenticazione pass-through per l’ambiente di testing di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a028c-115">Phase 1: Build out your simulated enterprise with pass-through authentication Microsoft 365 test environment</span></span>

<span data-ttu-id="a028c-116">Seguire le istruzioni contenute in [Autenticazione pass-through](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="a028c-116">Follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>

<span data-ttu-id="a028c-117">Di seguito è riportata la configurazione risultante.</span><span class="sxs-lookup"><span data-stu-id="a028c-117">Here is the resulting configuration.</span></span>

![L'organizzazione fittizia con autenticazione pass-through per l’ambiente di testing](media/pass-through-auth-m365-ent-test-environment/Phase2.png)
 
## <a name="phase-2-configure-azure-ad-seamless-single-sign-on"></a><span data-ttu-id="a028c-119">Fase 2: configurare l’accesso unificato Single Sign-on di Azure AD</span><span class="sxs-lookup"><span data-stu-id="a028c-119">Phase 2: Configure Azure AD seamless single sign-on</span></span>

<span data-ttu-id="a028c-120">Seguire le istruzioni contenute nella [Fase 2 della guida al lab di test per l’accesso Single Sign-on facile di Azure AD](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso).</span><span class="sxs-lookup"><span data-stu-id="a028c-120">Follow the instructions in [Phase 2 of the Azure AD Seamless Single Sign-on Test Lab Guide](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso).</span></span>

## <a name="phase-3-configure-named-locations"></a><span data-ttu-id="a028c-121">Fase 3: configurare le posizioni specifiche</span><span class="sxs-lookup"><span data-stu-id="a028c-121">Phase 3: Configure named locations</span></span>

<span data-ttu-id="a028c-122">Prima di tutto determinare gli indirizzi IP pubblici o gli intervalli di indirizzi usati all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a028c-122">First, determine the public IP addresses or address ranges used by your organization.</span></span>

<span data-ttu-id="a028c-123">Quindi, seguire le istruzioni contenute in [Configurare le posizioni specifiche in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) per aggiungere gli indirizzi o gli intervalli di indirizzi come posizioni specifiche.</span><span class="sxs-lookup"><span data-stu-id="a028c-123">Next, follow the instructions in [Configure named locations in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) to add the addresses or address ranges as named locations.</span></span> 

## <a name="phase-4-configure-password-writeback"></a><span data-ttu-id="a028c-124">Fase 4: configurare il writeback delle password</span><span class="sxs-lookup"><span data-stu-id="a028c-124">Phase 4: Configure password writeback</span></span>

<span data-ttu-id="a028c-125">Seguire le istruzioni contenute nella [Fase 2 della guida al lab di test per il writeback delle password.](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain)</span><span class="sxs-lookup"><span data-stu-id="a028c-125">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

## <a name="phase-5-configure-self-service-password-reset"></a><span data-ttu-id="a028c-126">Fase 5: configurare la reimpostazione delle password self-service </span><span class="sxs-lookup"><span data-stu-id="a028c-126">Phase 5: Configure self-service password reset</span></span>

<span data-ttu-id="a028c-127">Seguire le istruzioni contenute nella [Fase 3 della guida al lab di test per la reimpostazione della password](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span><span class="sxs-lookup"><span data-stu-id="a028c-127">Follow the instructions in [Phase 3 of the password reset Test Lab Guide](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span></span> 

<span data-ttu-id="a028c-128">Quando si abilita la reimpostazione della password degli account in un determinato gruppo di Azure AD, aggiungere gli account al gruppo **Reimpostazione della password**:</span><span class="sxs-lookup"><span data-stu-id="a028c-128">When enabling password reset for the accounts in a specific Azure AD group, add these accounts to the **Password reset** group:</span></span>

- <span data-ttu-id="a028c-129">Utente 2</span><span class="sxs-lookup"><span data-stu-id="a028c-129">User 2</span></span>
- <span data-ttu-id="a028c-130">Utente 3</span><span class="sxs-lookup"><span data-stu-id="a028c-130">User 3</span></span>
- <span data-ttu-id="a028c-131">Utente 4</span><span class="sxs-lookup"><span data-stu-id="a028c-131">User 4</span></span>
- <span data-ttu-id="a028c-132">Utente 5</span><span class="sxs-lookup"><span data-stu-id="a028c-132">User 5</span></span>

<span data-ttu-id="a028c-133">Testare la reimpostazione della password solo per l'account Utente 2.</span><span class="sxs-lookup"><span data-stu-id="a028c-133">Test password reset only for the User 2 account.</span></span>

## <a name="phase-6-configure-multi-factor-authentication"></a><span data-ttu-id="a028c-134">Fase 6: configurare l’autenticazione a più fattori</span><span class="sxs-lookup"><span data-stu-id="a028c-134">Phase 6: Configure multi-factor authentication</span></span>

<span data-ttu-id="a028c-135">Seguire le istruzioni contenute nella [Fase 2 della guida al lab di test per autenticazione a più fattori](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) per gli account utente seguenti:</span><span class="sxs-lookup"><span data-stu-id="a028c-135">Follow the instructions in [Phase 2 of the multi-factor authentication Test Lab Guide](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) for the following user accounts:</span></span>

- <span data-ttu-id="a028c-136">Utente 2</span><span class="sxs-lookup"><span data-stu-id="a028c-136">User 2</span></span>
- <span data-ttu-id="a028c-137">Utente 3</span><span class="sxs-lookup"><span data-stu-id="a028c-137">User 3</span></span>
- <span data-ttu-id="a028c-138">Utente 4</span><span class="sxs-lookup"><span data-stu-id="a028c-138">User 4</span></span>
- <span data-ttu-id="a028c-139">Utente 5</span><span class="sxs-lookup"><span data-stu-id="a028c-139">User 5</span></span>

<span data-ttu-id="a028c-140">Testare l'autenticazione a più fattori solo per l'account Utente 2.</span><span class="sxs-lookup"><span data-stu-id="a028c-140">Test multi-factor authentication only for the User 2 account.</span></span>

## <a name="phase-7-enable-azure-ad-identity-protection"></a><span data-ttu-id="a028c-141">Fase 7: abilitare Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="a028c-141">Phase 7: Enable Azure AD Identity Protection</span></span>

<span data-ttu-id="a028c-142">Seguire le istruzioni contenute nella [Fase 2 della guida al lab di test per Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-enable-and-use-azure-ad-identity-protection).</span><span class="sxs-lookup"><span data-stu-id="a028c-142">Follow the instructions in [Phase 2 of the Azure AD Identity Protection Test Lab Guide](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-enable-and-use-azure-ad-identity-protection).</span></span> 

## <a name="phase-8-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="a028c-143">Fase 8: abilitare l'autenticazione moderna per Exchange Online e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="a028c-143">Phase 8: Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="a028c-144">Per Exchange Online, fare clic su [queste istruzioni](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span><span class="sxs-lookup"><span data-stu-id="a028c-144">For Exchange Online, follow [these instructions](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span></span> 

<span data-ttu-id="a028c-145">Per Skype for Business Online:</span><span class="sxs-lookup"><span data-stu-id="a028c-145">For Skype for Business Online:</span></span>

1. <span data-ttu-id="a028c-146">Connettere a [Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="a028c-146">Connect to [Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

2. <span data-ttu-id="a028c-147">Eseguire questo comando.</span><span class="sxs-lookup"><span data-stu-id="a028c-147">Run this command.</span></span>

  ```powershell
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. <span data-ttu-id="a028c-148">Verificare che la modifica sia stata applicata con questo comando.</span><span class="sxs-lookup"><span data-stu-id="a028c-148">Verify that the change was successful with this command.</span></span>

  ```powershell
  Get-CsOAuthConfiguration
  ```

<span data-ttu-id="a028c-149">Il risultato è un ambiente di testing che soddisfa i requisiti di [Configurazione dei prerequisiti di autenticazione pass-through](identity-access-prerequisites.md#prerequisites) per l’accesso di identità e dispositivi.</span><span class="sxs-lookup"><span data-stu-id="a028c-149">The result is a test environment that meets the requirements of the [Pass-through authentication prerequisite configuration](identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span> 

## <a name="next-step"></a><span data-ttu-id="a028c-150">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="a028c-150">Next step</span></span>

<span data-ttu-id="a028c-151">Usare i [criteri comuni di identità e accesso ai dispositivi](identity-access-policies.md) per configurare i criteri basati sui prerequisiti e proteggere identità e dispositivi.</span><span class="sxs-lookup"><span data-stu-id="a028c-151">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites and protect identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="a028c-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a028c-152">See also</span></span>

[<span data-ttu-id="a028c-153">Guide al lab di test per identità aggiuntive</span><span class="sxs-lookup"><span data-stu-id="a028c-153">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="a028c-154">Fase 2: identità</span><span class="sxs-lookup"><span data-stu-id="a028c-154">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="a028c-155">Guide al lab di test di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="a028c-155">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

<span data-ttu-id="a028c-156">[Distribuzione di Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="a028c-156">[Microsoft 365 Enterprise deployment](deploy-microsoft-365-enterprise.md)</span></span>

[<span data-ttu-id="a028c-157">Documentazione di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="a028c-157">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)

