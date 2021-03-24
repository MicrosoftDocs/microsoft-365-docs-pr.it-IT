---
title: Prerequisiti di accesso di identità e dispositivi solo per cloud nell’ambiente di testing di Microsoft 365
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
description: Creare un ambiente Microsoft 365 per testare l'accesso di identità e dispositivi per l'autenticazione solo per cloud.
ms.openlocfilehash: 537718eb0efcffc296162a4458158efcbdad9986
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051545"
---
# <a name="identity-and-device-access-prerequisites-for-cloud-only-in-your-microsoft-365-test-environment"></a><span data-ttu-id="c3735-103">Prerequisiti di accesso di identità e dispositivi solo per cloud nell’ambiente di testing di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c3735-103">Identity and device access prerequisites for cloud only in your Microsoft 365 test environment</span></span>

<span data-ttu-id="c3735-104">*Questa guida al laboratorio di testing può essere utilizzata solo per gli ambienti di testing di Microsoft 365 per le aziende.*</span><span class="sxs-lookup"><span data-stu-id="c3735-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="c3735-105">[Le configurazioni di identità e](../security/defender-365-security/microsoft-365-policies-configurations.md) accesso ai dispositivi sono un set di configurazioni consigliate e criteri di accesso condizionale per proteggere l'accesso a tutti i servizi integrati con Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="c3735-105">[Identity and device access configurations](../security/defender-365-security/microsoft-365-policies-configurations.md) are a set of recommended configurations and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="c3735-106">In questo articolo viene descritto come configurare un ambiente di testing di Microsoft 365 che soddisfi i requisiti della [configurazione dei prerequisiti solo per cloud](../security/defender-365-security/identity-access-prerequisites.md#prerequisites) per l’accesso di identità e dispositivi.</span><span class="sxs-lookup"><span data-stu-id="c3735-106">This article describes how to configure a Microsoft 365 test environment that meets the requirements of the [cloud only prerequisite configuration](../security/defender-365-security/identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span>

<span data-ttu-id="c3735-107">Le fasi principali della configurazione dell'ambiente di testing sono otto:</span><span class="sxs-lookup"><span data-stu-id="c3735-107">There are eight phases to setting up this test environment:</span></span>

1. <span data-ttu-id="c3735-108">Creare l'ambiente di testing semplificato</span><span class="sxs-lookup"><span data-stu-id="c3735-108">Build out your lightweight test environment</span></span>
2. <span data-ttu-id="c3735-109">Configurare le posizioni specifiche</span><span class="sxs-lookup"><span data-stu-id="c3735-109">Configure named locations</span></span>
3. <span data-ttu-id="c3735-110">Configurare la reimpostazione self-service delle password</span><span class="sxs-lookup"><span data-stu-id="c3735-110">Configure self-service password reset</span></span>
4. <span data-ttu-id="c3735-111">Configurare l’autenticazione a più fattori</span><span class="sxs-lookup"><span data-stu-id="c3735-111">Configure multifactor authentication</span></span>
5. <span data-ttu-id="c3735-112">Abilitare la registrazione automatica dei dispositivi dei computer Windows aggiunti al dominio</span><span class="sxs-lookup"><span data-stu-id="c3735-112">Enable automatic device registration of domain-joined Windows computers</span></span>
6. <span data-ttu-id="c3735-113">Configurare la protezione con password di Azure AD</span><span class="sxs-lookup"><span data-stu-id="c3735-113">Configure Azure AD password protection</span></span> 
7. <span data-ttu-id="c3735-114">Abilitare Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="c3735-114">Enable Azure AD Identity Protection</span></span>
8. <span data-ttu-id="c3735-115">Abilitare l'autenticazione moderna per Exchange Online e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="c3735-115">Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

## <a name="phase-1-build-out-your-lightweight-microsoft-365-test-environment"></a><span data-ttu-id="c3735-116">Fase 1: creare l'ambiente di testing semplificato di Microsoft 365 </span><span class="sxs-lookup"><span data-stu-id="c3735-116">Phase 1: Build out your lightweight Microsoft 365 test environment</span></span>

<span data-ttu-id="c3735-117">Seguire le istruzioni riportate in [Configurazione di base semplificata](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="c3735-117">Follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
<span data-ttu-id="c3735-118">Di seguito è riportata la configurazione risultante.</span><span class="sxs-lookup"><span data-stu-id="c3735-118">Here is the resulting configuration.</span></span>

![Ambiente di testing semplificato di Microsoft 365 Enterprise](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)
 
## <a name="phase-2-configure-named-locations"></a><span data-ttu-id="c3735-120">Fase 2: configurare le posizioni specifiche</span><span class="sxs-lookup"><span data-stu-id="c3735-120">Phase 2: Configure named locations</span></span>

<span data-ttu-id="c3735-121">Prima di tutto è necessario determinare gli indirizzi IP pubblici o gli intervalli di indirizzi usati all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c3735-121">First, determine the public IP addresses or address ranges used by your organization.</span></span>

<span data-ttu-id="c3735-122">Quindi, seguire le istruzioni contenute in [Configurare le posizioni specifiche in Azure Active Directory](/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) per aggiungere gli indirizzi o gli intervalli di indirizzi come posizioni specifiche.</span><span class="sxs-lookup"><span data-stu-id="c3735-122">Next, follow the instructions in [Configure named locations in Azure Active Directory](/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) to add the addresses or address ranges as named locations.</span></span> 

## <a name="phase-3-configure-self-service-password-reset"></a><span data-ttu-id="c3735-123">Fase 3: configurare la reimpostazione della password in modalità self-service</span><span class="sxs-lookup"><span data-stu-id="c3735-123">Phase 3: Configure self-service password reset</span></span>

<span data-ttu-id="c3735-124">Seguire le istruzioni contenute nella [Fase 3 della guida al lab di test per la reimpostazione della password](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span><span class="sxs-lookup"><span data-stu-id="c3735-124">Follow the instructions in [Phase 3 of the password reset Test Lab Guide](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span></span> 

<span data-ttu-id="c3735-125">Quando si abilita la reimpostazione della password degli account in un determinato gruppo di Azure AD, aggiungere gli account al gruppo **Reimpostazione della password**:</span><span class="sxs-lookup"><span data-stu-id="c3735-125">When enabling password reset for the accounts in a specific Azure AD group, add these accounts to the **Password reset** group:</span></span>

- <span data-ttu-id="c3735-126">Utente 2</span><span class="sxs-lookup"><span data-stu-id="c3735-126">User 2</span></span>
- <span data-ttu-id="c3735-127">Utente 3</span><span class="sxs-lookup"><span data-stu-id="c3735-127">User 3</span></span>
- <span data-ttu-id="c3735-128">Utente 4</span><span class="sxs-lookup"><span data-stu-id="c3735-128">User 4</span></span>
- <span data-ttu-id="c3735-129">Utente 5</span><span class="sxs-lookup"><span data-stu-id="c3735-129">User 5</span></span>

<span data-ttu-id="c3735-130">Testare la reimpostazione della password solo per l'account Utente 2.</span><span class="sxs-lookup"><span data-stu-id="c3735-130">Test password reset only for the User 2 account.</span></span>

## <a name="phase-4-configure-multi-factor-authentication"></a><span data-ttu-id="c3735-131">Fase 4: configurare l'autenticazione a più fattori</span><span class="sxs-lookup"><span data-stu-id="c3735-131">Phase 4: Configure multi-factor authentication</span></span>

<span data-ttu-id="c3735-132">Seguire le istruzioni contenute nella [Fase 2 della guida al lab di test per autenticazione a più fattori](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) per gli account utente seguenti:</span><span class="sxs-lookup"><span data-stu-id="c3735-132">Follow the instructions in [Phase 2 of the multi-factor authentication Test Lab Guide](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) for the following user accounts:</span></span>

- <span data-ttu-id="c3735-133">Utente 2</span><span class="sxs-lookup"><span data-stu-id="c3735-133">User 2</span></span>
- <span data-ttu-id="c3735-134">Utente 3</span><span class="sxs-lookup"><span data-stu-id="c3735-134">User 3</span></span>
- <span data-ttu-id="c3735-135">Utente 4</span><span class="sxs-lookup"><span data-stu-id="c3735-135">User 4</span></span>
- <span data-ttu-id="c3735-136">Utente 5</span><span class="sxs-lookup"><span data-stu-id="c3735-136">User 5</span></span>

<span data-ttu-id="c3735-137">Testare l'autenticazione a più fattori solo per l'account Utente 2.</span><span class="sxs-lookup"><span data-stu-id="c3735-137">Test multi-factor authentication only for the User 2 account.</span></span>

## <a name="phase-5-enable-automatic-device-registration-of-domain-joined-windows-computers"></a><span data-ttu-id="c3735-138">Fase 5: abilitare la registrazione automatica dei dispositivi dei computer Windows aggiunti al dominio</span><span class="sxs-lookup"><span data-stu-id="c3735-138">Phase 5: Enable automatic device registration of domain-joined Windows computers</span></span> 

<span data-ttu-id="c3735-139">Segui [queste istruzioni per](/azure/active-directory/devices/hybrid-azuread-join-plan) abilitare la registrazione automatica dei dispositivi dei computer Windows aggiunti al dominio.</span><span class="sxs-lookup"><span data-stu-id="c3735-139">Follow [these instructions](/azure/active-directory/devices/hybrid-azuread-join-plan) to enable automatic device registration of domain-joined Windows computers.</span></span>

## <a name="phase-6-configure-azure-ad-password-protection"></a><span data-ttu-id="c3735-140">Fase 6: configurare la protezione con password di Azure AD</span><span class="sxs-lookup"><span data-stu-id="c3735-140">Phase 6: Configure Azure AD password protection</span></span> 

<span data-ttu-id="c3735-141">Seguire [queste istruzioni](/azure/active-directory/authentication/concept-password-ban-bad) per bloccare le password deboli note e le relative varianti.</span><span class="sxs-lookup"><span data-stu-id="c3735-141">Follow [these instructions](/azure/active-directory/authentication/concept-password-ban-bad) to block known weak passwords and their variants.</span></span>

## <a name="phase-7-enable-azure-ad-identity-protection"></a><span data-ttu-id="c3735-142">Fase 7: abilitare Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="c3735-142">Phase 7: Enable Azure AD Identity Protection</span></span>

<span data-ttu-id="c3735-143">Seguire le istruzioni contenute nella [Fase 2 della guida al lab di test per Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection).</span><span class="sxs-lookup"><span data-stu-id="c3735-143">Follow the instructions in [Phase 2 of the Azure AD Identity Protection Test Lab Guide](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection).</span></span> 

## <a name="phase-8-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="c3735-144">Fase 8: abilitare l'autenticazione moderna per Exchange Online e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="c3735-144">Phase 8: Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="c3735-145">Per Exchange Online, fare clic su [queste istruzioni](/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span><span class="sxs-lookup"><span data-stu-id="c3735-145">For Exchange Online, follow [these instructions](/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span></span> 

<span data-ttu-id="c3735-146">Per Skype for Business Online:</span><span class="sxs-lookup"><span data-stu-id="c3735-146">For Skype for Business Online:</span></span>

1. <span data-ttu-id="c3735-147">Connettere a [Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="c3735-147">Connect to [Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

2. <span data-ttu-id="c3735-148">Eseguire questo comando.</span><span class="sxs-lookup"><span data-stu-id="c3735-148">Run this command.</span></span>

  ```powershell
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. <span data-ttu-id="c3735-149">Verificare che la modifica sia stata applicata con questo comando.</span><span class="sxs-lookup"><span data-stu-id="c3735-149">Verify that the change was successful with this command.</span></span>

  ```powershell
  Get-CsOAuthConfiguration
  ```

<span data-ttu-id="c3735-150">Il risultato è un ambiente di testing che soddisfa i requisiti della configurazione dei prerequisiti solo [cloud](../security/defender-365-security/identity-access-prerequisites.md#prerequisites) per l'identità e l'accesso ai dispositivi.</span><span class="sxs-lookup"><span data-stu-id="c3735-150">The result is a test environment that meets the requirements of the [cloud-only prerequisite configuration](../security/defender-365-security/identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span> 

## <a name="next-step"></a><span data-ttu-id="c3735-151">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="c3735-151">Next step</span></span>

<span data-ttu-id="c3735-152">Usare i [criteri comuni di identità e accesso ai dispositivi](../security/defender-365-security/identity-access-policies.md) per configurare i criteri basati sui prerequisiti e proteggere identità e dispositivi.</span><span class="sxs-lookup"><span data-stu-id="c3735-152">Use [Common identity and device access policies](../security/defender-365-security/identity-access-policies.md) to configure the policies that build on the prerequisites and protect identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="c3735-153">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c3735-153">See also</span></span>

[<span data-ttu-id="c3735-154">Guide al lab di test per identità aggiuntive</span><span class="sxs-lookup"><span data-stu-id="c3735-154">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="c3735-155">Guida di orientamento all'identità</span><span class="sxs-lookup"><span data-stu-id="c3735-155">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="c3735-156">Guide ai lab di test di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="c3735-156">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="c3735-157">Panoramica di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="c3735-157">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="c3735-158">Documentazione di Microsoft 365 for enterprise</span><span class="sxs-lookup"><span data-stu-id="c3735-158">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)
