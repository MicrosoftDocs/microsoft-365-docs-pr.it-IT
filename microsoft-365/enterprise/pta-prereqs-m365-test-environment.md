---
title: Prerequisiti per l’accesso di identità e dispositivi per l’autenticazione pass-through nell’ambiente di testing di Microsoft 365
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Creare un ambiente Microsoft 365 per testare l’accesso di identità e dispositivi con i prerequisiti per l'autenticazione pass-through.
ms.openlocfilehash: f257b85672a1a1b27f600d145b1f9f3296b21980
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199850"
---
# <a name="identity-and-device-access-prerequisites-for-pass-through-authentication-in-your-microsoft-365-test-environment"></a><span data-ttu-id="adf1a-103">Prerequisiti per l’accesso di identità e dispositivi per l’autenticazione pass-through nell’ambiente di testing di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="adf1a-103">Identity and device access prerequisites for pass-through authentication in your Microsoft 365 test environment</span></span>

<span data-ttu-id="adf1a-104">*Questa guida al laboratorio di testing può essere utilizzata solo per Microsoft 365 per ambienti di test aziendali.*</span><span class="sxs-lookup"><span data-stu-id="adf1a-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="adf1a-105">[Le configurazioni di identità](../security/office-365-security/microsoft-365-policies-configurations.md) e accesso ai dispositivi sono un set di configurazioni e criteri di accesso condizionale per proteggere l'accesso a tutti i servizi in Microsoft 365 per le aziende integrati con Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="adf1a-105">[Identity and device access configurations](../security/office-365-security/microsoft-365-policies-configurations.md) are a set of configurations and conditional access policies to protect access to all services in Microsoft 365 for enterprise that are integrated with Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="adf1a-106">In questo articolo viene descritto come è possibile configurare un ambiente di testing di Microsoft 365 che soddisfi i requisiti di [Configurazione dei prerequisiti di autenticazione pass-through ](../security/office-365-security/identity-access-prerequisites.md#prerequisites) per l’accesso di identità e dispositivi.</span><span class="sxs-lookup"><span data-stu-id="adf1a-106">This article describes how you can configure a Microsoft 365 test environment that meets the requirements of the [Pass-through authentication prerequisite configuration](../security/office-365-security/identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span>

<span data-ttu-id="adf1a-107">La configurazione di questo ambiente di testing è in dieci fasi:</span><span class="sxs-lookup"><span data-stu-id="adf1a-107">There are ten phases to setting up this test environment:</span></span>

1. <span data-ttu-id="adf1a-108">Creare un’organizzazione fittizia con autenticazione pass-through per l’ambiente di testing di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="adf1a-108">Build out your simulated enterprise with pass-through authentication Microsoft 365 test environment</span></span>
2. <span data-ttu-id="adf1a-109">Configurare l’accesso unificato Single Sign-On di Azure AD</span><span class="sxs-lookup"><span data-stu-id="adf1a-109">Configure Azure AD seamless single sign-on</span></span>
3. <span data-ttu-id="adf1a-110">Configurare le posizioni specifiche</span><span class="sxs-lookup"><span data-stu-id="adf1a-110">Configure named locations</span></span>
4. <span data-ttu-id="adf1a-111">Configurare il writeback delle password</span><span class="sxs-lookup"><span data-stu-id="adf1a-111">Configure password writeback</span></span>
5. <span data-ttu-id="adf1a-112">Configurare la reimpostazione self-service delle password</span><span class="sxs-lookup"><span data-stu-id="adf1a-112">Configure self-service password reset</span></span>
6. <span data-ttu-id="adf1a-113">Configurare l’autenticazione a più fattori</span><span class="sxs-lookup"><span data-stu-id="adf1a-113">Configure multifactor authentication</span></span>
7. <span data-ttu-id="adf1a-114">Abilitare la registrazione automatica dei dispositivi dei computer Windows dominio</span><span class="sxs-lookup"><span data-stu-id="adf1a-114">Enable automatic device registration of domain-joined Windows computers</span></span>
8. <span data-ttu-id="adf1a-115">Configurare la protezione con password di Azure AD</span><span class="sxs-lookup"><span data-stu-id="adf1a-115">Configure Azure AD password protection</span></span> 
9. <span data-ttu-id="adf1a-116">Abilitare Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="adf1a-116">Enable Azure AD Identity Protection</span></span>
10. <span data-ttu-id="adf1a-117">Abilitare l'autenticazione moderna per Exchange Online e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="adf1a-117">Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

## <a name="phase-1-build-out-your-simulated-enterprise-with-pass-through-authentication-microsoft-365-test-environment"></a><span data-ttu-id="adf1a-118">Fase 1: creare un’organizzazione fittizia con autenticazione pass-through per l’ambiente di testing di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="adf1a-118">Phase 1: Build out your simulated enterprise with pass-through authentication Microsoft 365 test environment</span></span>

<span data-ttu-id="adf1a-119">Seguire le istruzioni contenute in [Autenticazione pass-through](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="adf1a-119">Follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>

<span data-ttu-id="adf1a-120">Di seguito è riportata la configurazione risultante.</span><span class="sxs-lookup"><span data-stu-id="adf1a-120">Here is the resulting configuration.</span></span>

![L'organizzazione fittizia con autenticazione pass-through per l’ambiente di testing](../media/pass-through-auth-m365-ent-test-environment/Phase2.png)
 
## <a name="phase-2-configure-azure-ad-seamless-single-sign-on"></a><span data-ttu-id="adf1a-122">Fase 2: configurare l’accesso unificato Single Sign-on di Azure AD</span><span class="sxs-lookup"><span data-stu-id="adf1a-122">Phase 2: Configure Azure AD seamless single sign-on</span></span>

<span data-ttu-id="adf1a-123">Seguire le istruzioni contenute nella [Fase 2 della guida al lab di test per l’accesso Single Sign-on facile di Azure AD](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso).</span><span class="sxs-lookup"><span data-stu-id="adf1a-123">Follow the instructions in [Phase 2 of the Azure AD Seamless Single Sign-on Test Lab Guide](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso).</span></span>

## <a name="phase-3-configure-named-locations"></a><span data-ttu-id="adf1a-124">Fase 3: configurare le posizioni specifiche</span><span class="sxs-lookup"><span data-stu-id="adf1a-124">Phase 3: Configure named locations</span></span>

<span data-ttu-id="adf1a-125">Prima di tutto determinare gli indirizzi IP pubblici o gli intervalli di indirizzi usati all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="adf1a-125">First, determine the public IP addresses or address ranges used by your organization.</span></span>

<span data-ttu-id="adf1a-126">Quindi, seguire le istruzioni contenute in [Configurare le posizioni specifiche in Azure Active Directory](/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) per aggiungere gli indirizzi o gli intervalli di indirizzi come posizioni specifiche.</span><span class="sxs-lookup"><span data-stu-id="adf1a-126">Next, follow the instructions in [Configure named locations in Azure Active Directory](/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) to add the addresses or address ranges as named locations.</span></span> 

## <a name="phase-4-configure-password-writeback"></a><span data-ttu-id="adf1a-127">Fase 4: configurare il writeback delle password</span><span class="sxs-lookup"><span data-stu-id="adf1a-127">Phase 4: Configure password writeback</span></span>

<span data-ttu-id="adf1a-128">Seguire le istruzioni contenute nella [Fase 2 della guida al lab di test per il writeback delle password.](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain)</span><span class="sxs-lookup"><span data-stu-id="adf1a-128">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

## <a name="phase-5-configure-self-service-password-reset"></a><span data-ttu-id="adf1a-129">Fase 5: configurare la reimpostazione delle password self-service </span><span class="sxs-lookup"><span data-stu-id="adf1a-129">Phase 5: Configure self-service password reset</span></span>

<span data-ttu-id="adf1a-130">Seguire le istruzioni contenute nella [Fase 3 della guida al lab di test per la reimpostazione della password](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span><span class="sxs-lookup"><span data-stu-id="adf1a-130">Follow the instructions in [Phase 3 of the password reset Test Lab Guide](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span></span> 

<span data-ttu-id="adf1a-131">Quando si abilita la reimpostazione della password degli account in un determinato gruppo di Azure AD, aggiungere gli account al gruppo **Reimpostazione della password**:</span><span class="sxs-lookup"><span data-stu-id="adf1a-131">When enabling password reset for the accounts in a specific Azure AD group, add these accounts to the **Password reset** group:</span></span>

- <span data-ttu-id="adf1a-132">Utente 2</span><span class="sxs-lookup"><span data-stu-id="adf1a-132">User 2</span></span>
- <span data-ttu-id="adf1a-133">Utente 3</span><span class="sxs-lookup"><span data-stu-id="adf1a-133">User 3</span></span>
- <span data-ttu-id="adf1a-134">Utente 4</span><span class="sxs-lookup"><span data-stu-id="adf1a-134">User 4</span></span>
- <span data-ttu-id="adf1a-135">Utente 5</span><span class="sxs-lookup"><span data-stu-id="adf1a-135">User 5</span></span>

<span data-ttu-id="adf1a-136">Testare la reimpostazione della password solo per l'account Utente 2.</span><span class="sxs-lookup"><span data-stu-id="adf1a-136">Test password reset only for the User 2 account.</span></span>

## <a name="phase-6-configure-multi-factor-authentication"></a><span data-ttu-id="adf1a-137">Fase 6: configurare l’autenticazione a più fattori</span><span class="sxs-lookup"><span data-stu-id="adf1a-137">Phase 6: Configure multi-factor authentication</span></span>

<span data-ttu-id="adf1a-138">Seguire le istruzioni contenute nella [Fase 2 della guida al lab di test per autenticazione a più fattori](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) per gli account utente seguenti:</span><span class="sxs-lookup"><span data-stu-id="adf1a-138">Follow the instructions in [Phase 2 of the multi-factor authentication Test Lab Guide](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) for the following user accounts:</span></span>

- <span data-ttu-id="adf1a-139">Utente 2</span><span class="sxs-lookup"><span data-stu-id="adf1a-139">User 2</span></span>
- <span data-ttu-id="adf1a-140">Utente 3</span><span class="sxs-lookup"><span data-stu-id="adf1a-140">User 3</span></span>
- <span data-ttu-id="adf1a-141">Utente 4</span><span class="sxs-lookup"><span data-stu-id="adf1a-141">User 4</span></span>
- <span data-ttu-id="adf1a-142">Utente 5</span><span class="sxs-lookup"><span data-stu-id="adf1a-142">User 5</span></span>

<span data-ttu-id="adf1a-143">Testare l'autenticazione a più fattori solo per l'account Utente 2.</span><span class="sxs-lookup"><span data-stu-id="adf1a-143">Test multi-factor authentication only for the User 2 account.</span></span>

## <a name="phase-7-enable-automatic-device-registration-of-domain-joined-windows-computers"></a><span data-ttu-id="adf1a-144">Fase 7: abilitare la registrazione automatica dei dispositivi dei computer Windows dominio</span><span class="sxs-lookup"><span data-stu-id="adf1a-144">Phase 7: Enable automatic device registration of domain-joined Windows computers</span></span> 

<span data-ttu-id="adf1a-145">Segui [queste istruzioni](/azure/active-directory/devices/hybrid-azuread-join-plan) per abilitare la registrazione automatica dei dispositivi dei computer Windows dominio.</span><span class="sxs-lookup"><span data-stu-id="adf1a-145">Follow [these instructions](/azure/active-directory/devices/hybrid-azuread-join-plan) to enable automatic device registration of domain-joined Windows computers.</span></span>

## <a name="phase-8-configure-azure-ad-password-protection"></a><span data-ttu-id="adf1a-146">Fase 8: configurare la protezione con password di Azure AD</span><span class="sxs-lookup"><span data-stu-id="adf1a-146">Phase 8: Configure Azure AD password protection</span></span> 

<span data-ttu-id="adf1a-147">Seguire [queste istruzioni](/azure/active-directory/authentication/concept-password-ban-bad) per bloccare le password deboli note e le relative varianti.</span><span class="sxs-lookup"><span data-stu-id="adf1a-147">Follow [these instructions](/azure/active-directory/authentication/concept-password-ban-bad) to block known weak passwords and their variants.</span></span>

## <a name="phase-9-enable-azure-ad-identity-protection"></a><span data-ttu-id="adf1a-148">Fase 9: abilitare Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="adf1a-148">Phase 9: Enable Azure AD Identity Protection</span></span>

<span data-ttu-id="adf1a-149">Seguire le istruzioni contenute nella [Fase 2 della guida al lab di test per Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection).</span><span class="sxs-lookup"><span data-stu-id="adf1a-149">Follow the instructions in [Phase 2 of the Azure AD Identity Protection Test Lab Guide](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection).</span></span> 

## <a name="phase-10-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="adf1a-150">Fase 10: abilitare l'autenticazione moderna per Exchange Online e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="adf1a-150">Phase 10: Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="adf1a-151">Per Exchange Online, fare clic su [queste istruzioni](/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span><span class="sxs-lookup"><span data-stu-id="adf1a-151">For Exchange Online, follow [these instructions](/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span></span> 

<span data-ttu-id="adf1a-152">Per Skype for Business Online:</span><span class="sxs-lookup"><span data-stu-id="adf1a-152">For Skype for Business Online:</span></span>

1. <span data-ttu-id="adf1a-153">Connettere a [Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="adf1a-153">Connect to [Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

2. <span data-ttu-id="adf1a-154">Eseguire questo comando.</span><span class="sxs-lookup"><span data-stu-id="adf1a-154">Run this command.</span></span>

  ```powershell
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. <span data-ttu-id="adf1a-155">Verificare che la modifica sia stata applicata con questo comando.</span><span class="sxs-lookup"><span data-stu-id="adf1a-155">Verify that the change was successful with this command.</span></span>

  ```powershell
  Get-CsOAuthConfiguration
  ```

<span data-ttu-id="adf1a-156">Il risultato è un ambiente di testing che soddisfa i requisiti di [Configurazione dei prerequisiti di autenticazione pass-through](../security/office-365-security/identity-access-prerequisites.md#prerequisites) per l’accesso di identità e dispositivi.</span><span class="sxs-lookup"><span data-stu-id="adf1a-156">The result is a test environment that meets the requirements of the [Pass-through authentication prerequisite configuration](../security/office-365-security/identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span> 

## <a name="next-step"></a><span data-ttu-id="adf1a-157">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="adf1a-157">Next step</span></span>

<span data-ttu-id="adf1a-158">Usare i [criteri comuni di identità e accesso ai dispositivi](../security/office-365-security/identity-access-policies.md) per configurare i criteri basati sui prerequisiti e proteggere identità e dispositivi.</span><span class="sxs-lookup"><span data-stu-id="adf1a-158">Use [Common identity and device access policies](../security/office-365-security/identity-access-policies.md) to configure the policies that build on the prerequisites and protect identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="adf1a-159">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="adf1a-159">See also</span></span>

[<span data-ttu-id="adf1a-160">Guide al lab di test per identità aggiuntive</span><span class="sxs-lookup"><span data-stu-id="adf1a-160">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="adf1a-161">Guida di orientamento all'identità</span><span class="sxs-lookup"><span data-stu-id="adf1a-161">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="adf1a-162">Guide ai lab di test di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="adf1a-162">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="adf1a-163">Panoramica di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="adf1a-163">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="adf1a-164">Documentazione di Microsoft 365 for enterprise</span><span class="sxs-lookup"><span data-stu-id="adf1a-164">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)
