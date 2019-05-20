---
title: Prerequisiti di accesso di identità e dispositivi solo per cloud nell’ambiente di testing di Microsoft 365
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
description: Creare un ambiente Microsoft 365 per testare l'accesso di identità e dispositivi per l'autenticazione solo per cloud.
ms.openlocfilehash: 9721d2972990998ca345f1d48d96494096f9190e
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "34072566"
---
# <a name="identity-and-device-access-prerequisites-for-cloud-only-in-your-microsoft-365-test-environment"></a><span data-ttu-id="6bcbb-103">Prerequisiti di accesso di identità e dispositivi solo per cloud nell’ambiente di testing di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6bcbb-103">Identity and device access for your Microsoft 365 test environment</span></span>

<span data-ttu-id="6bcbb-104">Le [configurazioni di identità e accesso dei dispositivi](microsoft-365-policies-configurations.md) sono una serie di configurazioni e criteri di accesso condizionale per proteggere l'accesso a tutti i servizi integrati con Azure Active Directory (Azure AD), tra cui Office 365 ed Enterprise Mobility + Security (EMS) in Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="6bcbb-104">[Identity and device access configurations](microsoft-365-policies-configurations.md) are a set of features and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD), including Office 365 and Enterprise Mobility + Security (EMS) in Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="6bcbb-105">In questo articolo viene descritto come configurare un ambiente di testing di Microsoft 365 che soddisfi i requisiti della [configurazione dei prerequisiti solo per cloud](identity-access-prerequisites.md#prerequisites) per l’accesso di identità e dispositivi.</span><span class="sxs-lookup"><span data-stu-id="6bcbb-105">This article describes how to configure a Microsoft 365 test environment that meets the requirements of the [cloud only prerequisite configuration](identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span>

<span data-ttu-id="6bcbb-106">Le fasi principali della configurazione dell'ambiente di testing sono sette:</span><span class="sxs-lookup"><span data-stu-id="6bcbb-106">There are two phases to setting up this test environment:</span></span>

1.  <span data-ttu-id="6bcbb-107">Creare l'ambiente di testing semplificato</span><span class="sxs-lookup"><span data-stu-id="6bcbb-107">Build out your lightweight test environment</span></span>
2.  <span data-ttu-id="6bcbb-108">Configurare le posizioni specifiche</span><span class="sxs-lookup"><span data-stu-id="6bcbb-108">Configure named locations</span></span>
3.  <span data-ttu-id="6bcbb-109">Configurare il writeback delle password</span><span class="sxs-lookup"><span data-stu-id="6bcbb-109">Configure password writeback</span></span>
4.  <span data-ttu-id="6bcbb-110">Configurare la reimpostazione self-service delle password</span><span class="sxs-lookup"><span data-stu-id="6bcbb-110">Configure self-service password resets</span></span>
5.  <span data-ttu-id="6bcbb-111">Configurare l’autenticazione a più fattori</span><span class="sxs-lookup"><span data-stu-id="6bcbb-111">Configure multifactor authentication</span></span>
6.  <span data-ttu-id="6bcbb-112">Abilitare Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="6bcbb-112">Azure AD Identity Protection</span></span>
7.  <span data-ttu-id="6bcbb-113">Abilitare l'autenticazione moderna per Exchange Online e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="6bcbb-113">Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

## <a name="phase-1-build-out-your-lightweight-microsoft-365-test-environment"></a><span data-ttu-id="6bcbb-114">Fase 1: creare l'ambiente di testing semplificato di Microsoft 365 </span><span class="sxs-lookup"><span data-stu-id="6bcbb-114">Phase 1: Build out your lightweight or simulated enterprise Office 365 dev/test environment</span></span>

<span data-ttu-id="6bcbb-115">Seguire le istruzioni riportate in [Configurazione di base semplificata](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="6bcbb-115">Follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
<span data-ttu-id="6bcbb-116">Di seguito è riportata la configurazione risultante.</span><span class="sxs-lookup"><span data-stu-id="6bcbb-116">Here is the resulting configuration.</span></span>

![Ambiente di testing semplificato di Microsoft 365 Enterprise](media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)
 

## <a name="phase-2-configure-named-locations"></a><span data-ttu-id="6bcbb-118">Fase 2: configurare le posizioni specifiche</span><span class="sxs-lookup"><span data-stu-id="6bcbb-118">Phase 2: Configure named locations</span></span>

<span data-ttu-id="6bcbb-119">Prima di tutto è necessario determinare gli indirizzi IP pubblici o gli intervalli di indirizzi usati all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="6bcbb-119">First, determine the public IP addresses or address ranges used by your organization.</span></span>

<span data-ttu-id="6bcbb-120">Quindi, seguire le istruzioni contenute in [Configurare le posizioni specifiche in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) per aggiungere gli indirizzi o gli intervalli di indirizzi come posizioni specifiche.</span><span class="sxs-lookup"><span data-stu-id="6bcbb-120">Next, follow the instructions in [Configure named locations in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) to add the addresses or address ranges as named locations.</span></span> 

## <a name="phase-3-configure-password-writeback"></a><span data-ttu-id="6bcbb-121">Fase 3: configurare il writeback delle password</span><span class="sxs-lookup"><span data-stu-id="6bcbb-121">Phase 3: Configure password writeback</span></span>

<span data-ttu-id="6bcbb-122">Seguire le istruzioni contenute in[Fase 2 della guida al lab di test sul writeback delle password](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span><span class="sxs-lookup"><span data-stu-id="6bcbb-122">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

## <a name="phase-4-configure-self-service-password-reset"></a><span data-ttu-id="6bcbb-123">Fase 4: configurare la reimpostazione delle password self-service</span><span class="sxs-lookup"><span data-stu-id="6bcbb-123">Phase 4: Configure self-service password reset</span></span>

<span data-ttu-id="6bcbb-124">Seguire le istruzioni contenute nella [Fase 3 della guida al lab di test per la reimpostazione della password](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span><span class="sxs-lookup"><span data-stu-id="6bcbb-124">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span></span> 

<span data-ttu-id="6bcbb-125">Quando si abilita la reimpostazione della password degli account in un determinato gruppo di Azure AD, aggiungere gli account al gruppo **Reimpostazione della password**:</span><span class="sxs-lookup"><span data-stu-id="6bcbb-125">When enabling password reset for the accounts in a specific Azure AD group, add these accounts to the **Password reset** group:</span></span>

- <span data-ttu-id="6bcbb-126">Utente 2</span><span class="sxs-lookup"><span data-stu-id="6bcbb-126">User: %2</span></span>
- <span data-ttu-id="6bcbb-127">Utente 3</span><span class="sxs-lookup"><span data-stu-id="6bcbb-127">User Defined 3</span></span>
- <span data-ttu-id="6bcbb-128">Utente 4</span><span class="sxs-lookup"><span data-stu-id="6bcbb-128">User: %4</span></span>
- <span data-ttu-id="6bcbb-129">Utente 5</span><span class="sxs-lookup"><span data-stu-id="6bcbb-129">User 5</span></span>

<span data-ttu-id="6bcbb-130">Testare la reimpostazione della password solo per l'account Utente 2.</span><span class="sxs-lookup"><span data-stu-id="6bcbb-130">Next, you test password reset for the User 2 account.</span></span>

## <a name="phase-5-configure-multi-factor-authentication"></a><span data-ttu-id="6bcbb-131">Fase 5: configurare l’autenticazione a più fattori</span><span class="sxs-lookup"><span data-stu-id="6bcbb-131">Phase 5: Configure multi-factor authentication</span></span>

<span data-ttu-id="6bcbb-132">Seguire le istruzioni contenute nella [Fase 2 della guida al lab di test per autenticazione a più fattori](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) per gli account utente seguenti:</span><span class="sxs-lookup"><span data-stu-id="6bcbb-132">Follow the instructions in [Phase 2 of the multi-factor authentication Test Lab Guide](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) for the following user accounts:</span></span>

- <span data-ttu-id="6bcbb-133">Utente 2</span><span class="sxs-lookup"><span data-stu-id="6bcbb-133">User: %2</span></span>
- <span data-ttu-id="6bcbb-134">Utente 3</span><span class="sxs-lookup"><span data-stu-id="6bcbb-134">User Defined 3</span></span>
- <span data-ttu-id="6bcbb-135">Utente 4</span><span class="sxs-lookup"><span data-stu-id="6bcbb-135">User: %4</span></span>
- <span data-ttu-id="6bcbb-136">Utente 5</span><span class="sxs-lookup"><span data-stu-id="6bcbb-136">User 5</span></span>

<span data-ttu-id="6bcbb-137">Testare l'autenticazione a più fattori solo per l'account Utente 2.</span><span class="sxs-lookup"><span data-stu-id="6bcbb-137">Enable and test multi-factor authentication for the User 2 account.</span></span>

## <a name="phase-6-enable-azure-ad-identity-protection"></a><span data-ttu-id="6bcbb-138">Fase 6: abilitare Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="6bcbb-138">Phase 6: Enable Azure AD Identity Protection</span></span>

<span data-ttu-id="6bcbb-139">Seguire le istruzioni contenute nella [Fase 2 della guida al lab di test per Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-enable-and-use-azure-ad-identity-protection).</span><span class="sxs-lookup"><span data-stu-id="6bcbb-139">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-enable-and-use-azure-ad-identity-protection).</span></span> 

## <a name="phase-7-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="6bcbb-140">Fase 7: abilitare l'autenticazione moderna per Exchange Online e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="6bcbb-140">Phase 7: Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="6bcbb-141">Per Exchange Online, fare clic su [queste istruzioni](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span><span class="sxs-lookup"><span data-stu-id="6bcbb-141">For Exchange Online, follow [these instructions](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span></span> 

<span data-ttu-id="6bcbb-142">Per Skype for Business Online:</span><span class="sxs-lookup"><span data-stu-id="6bcbb-142">Skype for Business Online</span></span>

1. <span data-ttu-id="6bcbb-143">Connettere a [Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="6bcbb-143">[Migrate to Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell). (Administrator)</span></span>

2. <span data-ttu-id="6bcbb-144">Eseguire questo comando.</span><span class="sxs-lookup"><span data-stu-id="6bcbb-144">Run this command:</span></span>

  ```
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. <span data-ttu-id="6bcbb-145">Verificare che la modifica sia stata applicata con questo comando.</span><span class="sxs-lookup"><span data-stu-id="6bcbb-145">Ensure that the download was successful with this command.</span></span>

  ```
  Get-CsOAuthConfiguration
  ```

<span data-ttu-id="6bcbb-146">Il risultato è un ambiente di testing che soddisfa i requisiti di [Configurazione dei prerequisiti solo per cloud](identity-access-prerequisites.md#prerequisites) per l’identità e l’accesso dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="6bcbb-146">The result is a test environment that meets the requirements of the [cloud only prerequisite configuration](identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span> 

## <a name="next-step"></a><span data-ttu-id="6bcbb-147">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="6bcbb-147">Next step</span></span>

<span data-ttu-id="6bcbb-148">Usare i [criteri comuni di identità e accesso ai dispositivi](identity-access-policies.md) per configurare i criteri basati sui prerequisiti e proteggere identità e dispositivi.</span><span class="sxs-lookup"><span data-stu-id="6bcbb-148">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites and test protection for identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="6bcbb-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6bcbb-149">See also</span></span>

[<span data-ttu-id="6bcbb-150">Guide al lab di test per identità aggiuntive</span><span class="sxs-lookup"><span data-stu-id="6bcbb-150">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="6bcbb-151">Fase 2: identità</span><span class="sxs-lookup"><span data-stu-id="6bcbb-151">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="6bcbb-152">Guide al lab di test di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="6bcbb-152">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

<span data-ttu-id="6bcbb-153">[Distribuzione di Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="6bcbb-153">[Microsoft 365 Enterprise deployment](deploy-microsoft-365-enterprise.md)</span></span>

[<span data-ttu-id="6bcbb-154">Documentazione di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="6bcbb-154">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
