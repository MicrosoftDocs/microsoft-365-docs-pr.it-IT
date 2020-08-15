---
title: Prerequisiti per l’accesso di identità e dispositivi per l’autenticazione pass-through nell’ambiente di testing di Microsoft 365
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 12/12/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Creare un ambiente Microsoft 365 per testare l’accesso di identità e dispositivi con i prerequisiti per l'autenticazione pass-through.
ms.openlocfilehash: eeb6c1d1313c95e920b20cce419118fe1e61ad6e
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685643"
---
# <a name="identity-and-device-access-prerequisites-for-pass-through-authentication-in-your-microsoft-365-test-environment"></a><span data-ttu-id="3d7e0-103">Prerequisiti per l’accesso di identità e dispositivi per l’autenticazione pass-through nell’ambiente di testing di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3d7e0-103">Identity and device access prerequisites for pass-through authentication in your Microsoft 365 test environment</span></span>

<span data-ttu-id="3d7e0-104">*Questa guida del laboratorio di testing può essere utilizzata solo per Microsoft 365 per gli ambienti di testing dell'organizzazione.*</span><span class="sxs-lookup"><span data-stu-id="3d7e0-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="3d7e0-105">Le [configurazioni di accesso a identità e dispositivi](microsoft-365-policies-configurations.md) sono un insieme di configurazioni e criteri di accesso condizionale per proteggere l'accesso a tutti i servizi in Microsoft 365 per Enterprise integrati con Azure Active Directory (Azure ad).</span><span class="sxs-lookup"><span data-stu-id="3d7e0-105">[Identity and device access configurations](microsoft-365-policies-configurations.md) are a set of configurations and conditional access policies to protect access to all services in Microsoft 365 for enterprise that are integrated with Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="3d7e0-106">In questo articolo viene descritto come è possibile configurare un ambiente di testing di Microsoft 365 che soddisfi i requisiti di [Configurazione dei prerequisiti di autenticazione pass-through ](identity-access-prerequisites.md#prerequisites) per l’accesso di identità e dispositivi.</span><span class="sxs-lookup"><span data-stu-id="3d7e0-106">This article describes how you can configure a Microsoft 365 test environment that meets the requirements of the [Pass-through authentication prerequisite configuration](identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span>

<span data-ttu-id="3d7e0-107">Le fasi principali della configurazione dell'ambiente di testing sono otto:</span><span class="sxs-lookup"><span data-stu-id="3d7e0-107">There are eight phases to setting up this test environment:</span></span>

1.  <span data-ttu-id="3d7e0-108">Creare un’organizzazione fittizia con autenticazione pass-through per l’ambiente di testing di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3d7e0-108">Build out your simulated enterprise with pass-through authentication Microsoft 365 test environment</span></span>
2.  <span data-ttu-id="3d7e0-109">Configurare l’accesso unificato Single Sign-On di Azure AD</span><span class="sxs-lookup"><span data-stu-id="3d7e0-109">Configure Azure AD seamless single sign-on</span></span>
3.  <span data-ttu-id="3d7e0-110">Configurare le posizioni specifiche</span><span class="sxs-lookup"><span data-stu-id="3d7e0-110">Configure named locations</span></span>
4.  <span data-ttu-id="3d7e0-111">Configurare il writeback delle password</span><span class="sxs-lookup"><span data-stu-id="3d7e0-111">Configure password writeback</span></span>
5.  <span data-ttu-id="3d7e0-112">Configurare la reimpostazione self-service delle password</span><span class="sxs-lookup"><span data-stu-id="3d7e0-112">Configure self-service password reset</span></span>
6.  <span data-ttu-id="3d7e0-113">Configurare l’autenticazione a più fattori</span><span class="sxs-lookup"><span data-stu-id="3d7e0-113">Configure multifactor authentication</span></span>
7.  <span data-ttu-id="3d7e0-114">Abilitare Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="3d7e0-114">Enable Azure AD Identity Protection</span></span>
8.  <span data-ttu-id="3d7e0-115">Abilitare l'autenticazione moderna per Exchange Online e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="3d7e0-115">Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

## <a name="phase-1-build-out-your-simulated-enterprise-with-pass-through-authentication-microsoft-365-test-environment"></a><span data-ttu-id="3d7e0-116">Fase 1: creare un’organizzazione fittizia con autenticazione pass-through per l’ambiente di testing di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3d7e0-116">Phase 1: Build out your simulated enterprise with pass-through authentication Microsoft 365 test environment</span></span>

<span data-ttu-id="3d7e0-117">Seguire le istruzioni contenute in [Autenticazione pass-through](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="3d7e0-117">Follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>

<span data-ttu-id="3d7e0-118">Di seguito è riportata la configurazione risultante.</span><span class="sxs-lookup"><span data-stu-id="3d7e0-118">Here is the resulting configuration.</span></span>

![L'organizzazione fittizia con autenticazione pass-through per l’ambiente di testing](../media/pass-through-auth-m365-ent-test-environment/Phase2.png)
 
## <a name="phase-2-configure-azure-ad-seamless-single-sign-on"></a><span data-ttu-id="3d7e0-120">Fase 2: configurare l’accesso unificato Single Sign-on di Azure AD</span><span class="sxs-lookup"><span data-stu-id="3d7e0-120">Phase 2: Configure Azure AD seamless single sign-on</span></span>

<span data-ttu-id="3d7e0-121">Seguire le istruzioni contenute nella [Fase 2 della guida al lab di test per l’accesso Single Sign-on facile di Azure AD](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso).</span><span class="sxs-lookup"><span data-stu-id="3d7e0-121">Follow the instructions in [Phase 2 of the Azure AD Seamless Single Sign-on Test Lab Guide](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso).</span></span>

## <a name="phase-3-configure-named-locations"></a><span data-ttu-id="3d7e0-122">Fase 3: configurare le posizioni specifiche</span><span class="sxs-lookup"><span data-stu-id="3d7e0-122">Phase 3: Configure named locations</span></span>

<span data-ttu-id="3d7e0-123">Prima di tutto determinare gli indirizzi IP pubblici o gli intervalli di indirizzi usati all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3d7e0-123">First, determine the public IP addresses or address ranges used by your organization.</span></span>

<span data-ttu-id="3d7e0-124">Quindi, seguire le istruzioni contenute in [Configurare le posizioni specifiche in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) per aggiungere gli indirizzi o gli intervalli di indirizzi come posizioni specifiche.</span><span class="sxs-lookup"><span data-stu-id="3d7e0-124">Next, follow the instructions in [Configure named locations in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) to add the addresses or address ranges as named locations.</span></span> 

## <a name="phase-4-configure-password-writeback"></a><span data-ttu-id="3d7e0-125">Fase 4: configurare il writeback delle password</span><span class="sxs-lookup"><span data-stu-id="3d7e0-125">Phase 4: Configure password writeback</span></span>

<span data-ttu-id="3d7e0-126">Seguire le istruzioni contenute nella [Fase 2 della guida al lab di test per il writeback delle password.](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain)</span><span class="sxs-lookup"><span data-stu-id="3d7e0-126">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

## <a name="phase-5-configure-self-service-password-reset"></a><span data-ttu-id="3d7e0-127">Fase 5: configurare la reimpostazione delle password self-service </span><span class="sxs-lookup"><span data-stu-id="3d7e0-127">Phase 5: Configure self-service password reset</span></span>

<span data-ttu-id="3d7e0-128">Seguire le istruzioni contenute nella [Fase 3 della guida al lab di test per la reimpostazione della password](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span><span class="sxs-lookup"><span data-stu-id="3d7e0-128">Follow the instructions in [Phase 3 of the password reset Test Lab Guide](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span></span> 

<span data-ttu-id="3d7e0-129">Quando si abilita la reimpostazione della password degli account in un determinato gruppo di Azure AD, aggiungere gli account al gruppo **Reimpostazione della password**:</span><span class="sxs-lookup"><span data-stu-id="3d7e0-129">When enabling password reset for the accounts in a specific Azure AD group, add these accounts to the **Password reset** group:</span></span>

- <span data-ttu-id="3d7e0-130">Utente 2</span><span class="sxs-lookup"><span data-stu-id="3d7e0-130">User 2</span></span>
- <span data-ttu-id="3d7e0-131">Utente 3</span><span class="sxs-lookup"><span data-stu-id="3d7e0-131">User 3</span></span>
- <span data-ttu-id="3d7e0-132">Utente 4</span><span class="sxs-lookup"><span data-stu-id="3d7e0-132">User 4</span></span>
- <span data-ttu-id="3d7e0-133">Utente 5</span><span class="sxs-lookup"><span data-stu-id="3d7e0-133">User 5</span></span>

<span data-ttu-id="3d7e0-134">Testare la reimpostazione della password solo per l'account Utente 2.</span><span class="sxs-lookup"><span data-stu-id="3d7e0-134">Test password reset only for the User 2 account.</span></span>

## <a name="phase-6-configure-multi-factor-authentication"></a><span data-ttu-id="3d7e0-135">Fase 6: configurare l’autenticazione a più fattori</span><span class="sxs-lookup"><span data-stu-id="3d7e0-135">Phase 6: Configure multi-factor authentication</span></span>

<span data-ttu-id="3d7e0-136">Seguire le istruzioni contenute nella [Fase 2 della guida al lab di test per autenticazione a più fattori](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) per gli account utente seguenti:</span><span class="sxs-lookup"><span data-stu-id="3d7e0-136">Follow the instructions in [Phase 2 of the multi-factor authentication Test Lab Guide](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) for the following user accounts:</span></span>

- <span data-ttu-id="3d7e0-137">Utente 2</span><span class="sxs-lookup"><span data-stu-id="3d7e0-137">User 2</span></span>
- <span data-ttu-id="3d7e0-138">Utente 3</span><span class="sxs-lookup"><span data-stu-id="3d7e0-138">User 3</span></span>
- <span data-ttu-id="3d7e0-139">Utente 4</span><span class="sxs-lookup"><span data-stu-id="3d7e0-139">User 4</span></span>
- <span data-ttu-id="3d7e0-140">Utente 5</span><span class="sxs-lookup"><span data-stu-id="3d7e0-140">User 5</span></span>

<span data-ttu-id="3d7e0-141">Testare l'autenticazione a più fattori solo per l'account Utente 2.</span><span class="sxs-lookup"><span data-stu-id="3d7e0-141">Test multi-factor authentication only for the User 2 account.</span></span>

## <a name="phase-7-enable-azure-ad-identity-protection"></a><span data-ttu-id="3d7e0-142">Fase 7: abilitare Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="3d7e0-142">Phase 7: Enable Azure AD Identity Protection</span></span>

<span data-ttu-id="3d7e0-143">Seguire le istruzioni contenute nella [Fase 2 della guida al lab di test per Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection).</span><span class="sxs-lookup"><span data-stu-id="3d7e0-143">Follow the instructions in [Phase 2 of the Azure AD Identity Protection Test Lab Guide](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection).</span></span> 

## <a name="phase-8-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="3d7e0-144">Fase 8: abilitare l'autenticazione moderna per Exchange Online e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="3d7e0-144">Phase 8: Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="3d7e0-145">Per Exchange Online, fare clic su [queste istruzioni](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span><span class="sxs-lookup"><span data-stu-id="3d7e0-145">For Exchange Online, follow [these instructions](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span></span> 

<span data-ttu-id="3d7e0-146">Per Skype for Business Online:</span><span class="sxs-lookup"><span data-stu-id="3d7e0-146">For Skype for Business Online:</span></span>

1. <span data-ttu-id="3d7e0-147">Connettere a [Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="3d7e0-147">Connect to [Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

2. <span data-ttu-id="3d7e0-148">Eseguire questo comando.</span><span class="sxs-lookup"><span data-stu-id="3d7e0-148">Run this command.</span></span>

  ```powershell
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. <span data-ttu-id="3d7e0-149">Verificare che la modifica sia stata applicata con questo comando.</span><span class="sxs-lookup"><span data-stu-id="3d7e0-149">Verify that the change was successful with this command.</span></span>

  ```powershell
  Get-CsOAuthConfiguration
  ```

<span data-ttu-id="3d7e0-150">Il risultato è un ambiente di testing che soddisfa i requisiti di [Configurazione dei prerequisiti di autenticazione pass-through](identity-access-prerequisites.md#prerequisites) per l’accesso di identità e dispositivi.</span><span class="sxs-lookup"><span data-stu-id="3d7e0-150">The result is a test environment that meets the requirements of the [Pass-through authentication prerequisite configuration](identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span> 

## <a name="next-step"></a><span data-ttu-id="3d7e0-151">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="3d7e0-151">Next step</span></span>

<span data-ttu-id="3d7e0-152">Usare i [criteri comuni di identità e accesso ai dispositivi](identity-access-policies.md) per configurare i criteri basati sui prerequisiti e proteggere identità e dispositivi.</span><span class="sxs-lookup"><span data-stu-id="3d7e0-152">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites and protect identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="3d7e0-153">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3d7e0-153">See also</span></span>

[<span data-ttu-id="3d7e0-154">Guide al lab di test per identità aggiuntive</span><span class="sxs-lookup"><span data-stu-id="3d7e0-154">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="3d7e0-155">Roadmap dell'identità</span><span class="sxs-lookup"><span data-stu-id="3d7e0-155">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="3d7e0-156">Guide ai lab di test di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="3d7e0-156">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="3d7e0-157">Panoramica di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="3d7e0-157">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="3d7e0-158">Microsoft 365 per la documentazione relativa all'organizzazione</span><span class="sxs-lookup"><span data-stu-id="3d7e0-158">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)

