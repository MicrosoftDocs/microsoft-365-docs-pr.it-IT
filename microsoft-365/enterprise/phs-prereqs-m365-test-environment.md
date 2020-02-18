---
title: Identità e prerequisiti di accesso dei dispositivi per la sincronizzazione dell’hash delle password in ambiente di testing di Microsoft 365
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 12/12/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Creare un ambiente Microsoft 365 per testare l'identità e l’accesso del dispositivo con i prerequisiti per l'autenticazione di sincronizzazione hash delle password.
ms.openlocfilehash: 125d8c6e1e954a05edd630c8f4d55848fa3314b3
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42066034"
---
# <a name="identity-and-device-access-prerequisites-for-password-hash-synchronization-in-your-microsoft-365-test-environment"></a><span data-ttu-id="f3d3c-103">Identità e prerequisiti di accesso dei dispositivi per la sincronizzazione dell’hash delle password in ambiente di testing di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f3d3c-103">Identity and device access prerequisites for password hash synchronization in your Microsoft 365 test environment</span></span>

<span data-ttu-id="f3d3c-104">*Questa guida al lab di test può essere usata solo per ambienti di testing di Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="f3d3c-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="f3d3c-105">Le [configurazioni di identità e accesso dei dispositivi](microsoft-365-policies-configurations.md) sono una serie di configurazioni e criteri di accesso condizionale per proteggere l'accesso a tutti i servizi integrati con Azure Active Directory (Azure AD), tra cui Office 365 ed Enterprise Mobility + Security (EMS) in Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="f3d3c-105">[Identity and device access configurations](microsoft-365-policies-configurations.md) are a set of configurations and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD), including Office 365 and Enterprise Mobility + Security (EMS) in Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="f3d3c-106">In questo articolo viene descritto come configurare un ambiente di testing di Microsoft 365 che soddisfi i requisiti di[Active Directory con configurazione dei prerequisiti di sincronizzazione dell’hash delle password](identity-access-prerequisites.md#prerequisites) per l’identità e l’accesso dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="f3d3c-106">This article describes how to configure a Microsoft 365 test environment that meets the requirements of the [Active Directory with password hash sync prerequisite configuration](identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span>

<span data-ttu-id="f3d3c-107">Le fasi principali della configurazione dell'ambiente di testing sono otto:</span><span class="sxs-lookup"><span data-stu-id="f3d3c-107">There are eight phases to setting up this test environment:</span></span>

1.  <span data-ttu-id="f3d3c-108">Creare un’organizzazione simulata con ambiente di testing per la sincronizzazione dell’hash delle password</span><span class="sxs-lookup"><span data-stu-id="f3d3c-108">Create a simulated enterprise with password hash sync test environment</span></span>
2.  <span data-ttu-id="f3d3c-109">Configurare l’accesso Single Sign-On facile di Azure AD</span><span class="sxs-lookup"><span data-stu-id="f3d3c-109">Configure Azure AD seamless single sign-on</span></span>
3.  <span data-ttu-id="f3d3c-110">Configurare le posizioni specifiche</span><span class="sxs-lookup"><span data-stu-id="f3d3c-110">Configure named locations</span></span>
4.  <span data-ttu-id="f3d3c-111">Configurare il writeback delle password</span><span class="sxs-lookup"><span data-stu-id="f3d3c-111">Configure password writeback</span></span>
5.  <span data-ttu-id="f3d3c-112">Configurare la reimpostazione self-service delle password per tutti gli account utente.</span><span class="sxs-lookup"><span data-stu-id="f3d3c-112">Configure self-service password reset for all user accounts</span></span>
6.  <span data-ttu-id="f3d3c-113">Configurare l'autenticazione a più fattori per tutti gli account utente.</span><span class="sxs-lookup"><span data-stu-id="f3d3c-113">Configure multifactor authentication for all user accounts</span></span>
7.  <span data-ttu-id="f3d3c-114">Abilitare Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="f3d3c-114">Enable Azure AD Identity Protection</span></span>
8.  <span data-ttu-id="f3d3c-115">Abilitare l'autenticazione moderna per Exchange Online e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="f3d3c-115">Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

## <a name="phase-1-build-out-your-simulated-enterprise-with-password-hash-sync-microsoft-365-test-environment"></a><span data-ttu-id="f3d3c-116">Fase 1: creare un’organizzazione simulata con ambiente di testing per la sincronizzazione dell’hash delle password di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f3d3c-116">Phase 1: Build out your simulated enterprise with password hash sync Microsoft 365 test environment</span></span>

<span data-ttu-id="f3d3c-117">Seguire le istruzioni contenute in [Sincronizzazione hash delle password](password-hash-sync-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="f3d3c-117">Follow the instructions in [Password hash synchronization](password-hash-sync-m365-ent-test-environment.md).</span></span>
<span data-ttu-id="f3d3c-118">Di seguito è riportata la configurazione risultante.</span><span class="sxs-lookup"><span data-stu-id="f3d3c-118">Here is the resulting configuration.</span></span>

![L'organizzazione simulata con ambiente di testing per la sincronizzazione hash delle password](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)
 
## <a name="phase-2-configure-azure-ad-seamless-single-sign-on"></a><span data-ttu-id="f3d3c-120">Fase 2: configurare l’accesso Single Sign-on facile di Azure AD</span><span class="sxs-lookup"><span data-stu-id="f3d3c-120">Phase 2: Configure Azure AD seamless single sign-on</span></span>

<span data-ttu-id="f3d3c-121">Seguire le istruzioni contenute nella [Fase 2 della guida al lab di test per l’accesso Single Sign-on facile di Azure AD](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso).</span><span class="sxs-lookup"><span data-stu-id="f3d3c-121">Follow the instructions in [Phase 2 of the Azure AD Seamless Single Sign-on Test Lab Guide](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso).</span></span>

## <a name="phase-3-configure-named-locations"></a><span data-ttu-id="f3d3c-122">Fase 3: configurare le posizioni specifiche</span><span class="sxs-lookup"><span data-stu-id="f3d3c-122">Phase 3: Configure named locations</span></span>

<span data-ttu-id="f3d3c-123">Prima di tutto determinare gli indirizzi IP pubblici o gli intervalli di indirizzi usati all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f3d3c-123">First, determine the public IP addresses or address ranges used by your organization.</span></span>

<span data-ttu-id="f3d3c-124">Quindi, seguire le istruzioni contenute in [Configurare le posizioni specifiche in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) per aggiungere gli indirizzi o gli intervalli di indirizzi come posizioni specifiche.</span><span class="sxs-lookup"><span data-stu-id="f3d3c-124">Next, follow the instructions in [Configure named locations in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) to add the addresses or address ranges as named locations.</span></span> 

## <a name="phase-4-configure-password-writeback"></a><span data-ttu-id="f3d3c-125">Fase 4: configurare il writeback delle password</span><span class="sxs-lookup"><span data-stu-id="f3d3c-125">Phase 4: Configure password writeback</span></span>

<span data-ttu-id="f3d3c-126">Seguire le istruzioni contenute nella [Fase 2 della guida al lab di test per il writeback delle password.](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain)</span><span class="sxs-lookup"><span data-stu-id="f3d3c-126">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

## <a name="phase-5-configure-self-service-password-reset"></a><span data-ttu-id="f3d3c-127">Fase 5: configurare la reimpostazione delle password self-service </span><span class="sxs-lookup"><span data-stu-id="f3d3c-127">Phase 5: Configure self-service password reset</span></span>

<span data-ttu-id="f3d3c-128">Seguire le istruzioni contenute nella [Fase 3 della guida al lab di test per la reimpostazione della password](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span><span class="sxs-lookup"><span data-stu-id="f3d3c-128">Follow the instructions in [Phase 3 of the password reset Test Lab Guide](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span></span> 

<span data-ttu-id="f3d3c-129">Quando si abilita la reimpostazione della password degli account in un determinato gruppo di Azure AD, aggiungere gli account al gruppo **Reimpostazione della password**:</span><span class="sxs-lookup"><span data-stu-id="f3d3c-129">When enabling password reset for the accounts in a specific Azure AD group, add these accounts to the **Password reset** group:</span></span>

- <span data-ttu-id="f3d3c-130">Utente 2</span><span class="sxs-lookup"><span data-stu-id="f3d3c-130">User 2</span></span>
- <span data-ttu-id="f3d3c-131">Utente 3</span><span class="sxs-lookup"><span data-stu-id="f3d3c-131">User 3</span></span>
- <span data-ttu-id="f3d3c-132">Utente 4</span><span class="sxs-lookup"><span data-stu-id="f3d3c-132">User 4</span></span>
- <span data-ttu-id="f3d3c-133">Utente 5</span><span class="sxs-lookup"><span data-stu-id="f3d3c-133">User 5</span></span>

<span data-ttu-id="f3d3c-134">Testare la reimpostazione della password solo per l'account Utente 2.</span><span class="sxs-lookup"><span data-stu-id="f3d3c-134">Test password reset only for the User 2 account.</span></span>

## <a name="phase-6-configure-multi-factor-authentication"></a><span data-ttu-id="f3d3c-135">Fase 6: configurare l’autenticazione a più fattori</span><span class="sxs-lookup"><span data-stu-id="f3d3c-135">Phase 6: Configure multi-factor authentication</span></span>

<span data-ttu-id="f3d3c-136">Seguire le istruzioni contenute nella [Fase 2 della guida al lab di test per autenticazione a più fattori](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) per gli account utente seguenti:</span><span class="sxs-lookup"><span data-stu-id="f3d3c-136">Follow the instructions in [Phase 2 of the multi-factor authentication Test Lab Guide](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) for the following user accounts:</span></span>

- <span data-ttu-id="f3d3c-137">Utente 2</span><span class="sxs-lookup"><span data-stu-id="f3d3c-137">User 2</span></span>
- <span data-ttu-id="f3d3c-138">Utente 3</span><span class="sxs-lookup"><span data-stu-id="f3d3c-138">User 3</span></span>
- <span data-ttu-id="f3d3c-139">Utente 4</span><span class="sxs-lookup"><span data-stu-id="f3d3c-139">User 4</span></span>
- <span data-ttu-id="f3d3c-140">Utente 5</span><span class="sxs-lookup"><span data-stu-id="f3d3c-140">User 5</span></span>

<span data-ttu-id="f3d3c-141">Testare l'autenticazione a più fattori solo per l'account Utente 2.</span><span class="sxs-lookup"><span data-stu-id="f3d3c-141">Test multi-factor authentication only for the User 2 account.</span></span>

## <a name="phase-7-enable-azure-ad-identity-protection"></a><span data-ttu-id="f3d3c-142">Fase 7: abilitare Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="f3d3c-142">Phase 7: Enable Azure AD Identity Protection</span></span>

<span data-ttu-id="f3d3c-143">Seguire le istruzioni contenute nella [Fase 2 della guida al lab di test per Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection).</span><span class="sxs-lookup"><span data-stu-id="f3d3c-143">Follow the instructions in [Phase 2 of the Azure AD Identity Protection Test Lab Guide](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection).</span></span> 

## <a name="phase-8-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="f3d3c-144">Fase 8: abilitare l'autenticazione moderna per Exchange Online e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="f3d3c-144">Phase 8: Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="f3d3c-145">Per Exchange Online, fare clic su [queste istruzioni](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span><span class="sxs-lookup"><span data-stu-id="f3d3c-145">For Exchange Online, follow [these instructions](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span></span> 

<span data-ttu-id="f3d3c-146">Per Skype for Business Online:</span><span class="sxs-lookup"><span data-stu-id="f3d3c-146">For Skype for Business Online:</span></span>

1. <span data-ttu-id="f3d3c-147">Connettere a [Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="f3d3c-147">Connect to [Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

2. <span data-ttu-id="f3d3c-148">Eseguire questo comando.</span><span class="sxs-lookup"><span data-stu-id="f3d3c-148">Run this command.</span></span>

  ```powershell
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. <span data-ttu-id="f3d3c-149">Verificare che la modifica sia stata applicata con questo comando.</span><span class="sxs-lookup"><span data-stu-id="f3d3c-149">Verify that the change was successful with this command.</span></span>

  ```powershell
  Get-CsOAuthConfiguration
  ```

<span data-ttu-id="f3d3c-150">Il risultato è un ambiente di testing che soddisfa i requisiti di [Active Directory con configurazione dei prerequisiti di sincronizzazione dell’hash delle password](identity-access-prerequisites.md#prerequisites) per l’identità e l’accesso dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="f3d3c-150">The result is a test environment that meets the requirements of the [Active Directory with password hash sync prerequisite configuration](identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span> 

## <a name="next-step"></a><span data-ttu-id="f3d3c-151">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="f3d3c-151">Next step</span></span>

<span data-ttu-id="f3d3c-152">Usare i [criteri comuni di identità e accesso ai dispositivi](identity-access-policies.md) per configurare i criteri basati sui prerequisiti e proteggere identità e dispositivi.</span><span class="sxs-lookup"><span data-stu-id="f3d3c-152">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites and protect identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="f3d3c-153">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f3d3c-153">See also</span></span>

[<span data-ttu-id="f3d3c-154">Guide al lab di test per identità aggiuntive</span><span class="sxs-lookup"><span data-stu-id="f3d3c-154">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="f3d3c-155">Fase 2: identità</span><span class="sxs-lookup"><span data-stu-id="f3d3c-155">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="f3d3c-156">Guide al lab di test di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f3d3c-156">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

<span data-ttu-id="f3d3c-157">[Distribuzione di Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="f3d3c-157">[Microsoft 365 Enterprise deployment](deploy-microsoft-365-enterprise.md)</span></span>

[<span data-ttu-id="f3d3c-158">Documentazione di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f3d3c-158">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
