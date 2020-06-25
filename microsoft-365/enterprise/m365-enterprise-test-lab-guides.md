---
title: Guide al lab di test di Microsoft 365 per le aziende
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/20/2019
audience: ITPro
ms.topic: hub-page
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: 706d5449-45e5-4b0c-a012-ab60501899ad
description: Utilizzare queste guide al lab di test per configurare dimostrazioni, modelli di verifica o ambienti di sviluppo e test per Microsoft 365 per le aziende.
ms.openlocfilehash: 5907edd1bc42b9d679ed020331f225ef2d2b2594
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818742"
---
# <a name="microsoft-365-for-enterprise-test-lab-guides"></a><span data-ttu-id="9ea58-103">Guide al lab di test di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="9ea58-103">Microsoft 365 for enterprise Test Lab Guides</span></span>

<span data-ttu-id="9ea58-104">*Questo articolo si applica sia a Microsoft 365 per le aziende che a Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="9ea58-104">*This applies to both Microsoft 365 for enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="9ea58-105">Test Lab Guides (TLGs) help you quickly learn about Microsoft products.</span><span class="sxs-lookup"><span data-stu-id="9ea58-105">Test Lab Guides (TLGs) help you quickly learn about Microsoft products.</span></span> <span data-ttu-id="9ea58-106">They provide prescriptive instructions to configure simplified but representative test environments.</span><span class="sxs-lookup"><span data-stu-id="9ea58-106">They provide prescriptive instructions to configure simplified but representative test environments.</span></span> <span data-ttu-id="9ea58-107">You can use these environments for demonstration, customization, or creation of complex proofs of concept for the duration of a trial or paid subscription.</span><span class="sxs-lookup"><span data-stu-id="9ea58-107">You can use these environments for demonstration, customization, or creation of complex proofs of concept for the duration of a trial or paid subscription.</span></span> 

<span data-ttu-id="9ea58-108">TLGs are designed to be modular.</span><span class="sxs-lookup"><span data-stu-id="9ea58-108">TLGs are designed to be modular.</span></span> <span data-ttu-id="9ea58-109">They build upon each other to create multiple configurations that more closely match your learning or test configuration needs.</span><span class="sxs-lookup"><span data-stu-id="9ea58-109">They build upon each other to create multiple configurations that more closely match your learning or test configuration needs.</span></span> <span data-ttu-id="9ea58-110">The "I built it out myself and it works" hands-on experience helps you understand the deployment requirements of a new product or scenario so you can better plan for hosting it in production.</span><span class="sxs-lookup"><span data-stu-id="9ea58-110">The "I built it out myself and it works" hands-on experience helps you understand the deployment requirements of a new product or scenario so you can better plan for hosting it in production.</span></span>

<span data-ttu-id="9ea58-111">Queste guide permettono di creare anche ambienti appositi per lo sviluppo e il testing delle applicazioni, noti anche con il nome di ambienti di sviluppo/testing.</span><span class="sxs-lookup"><span data-stu-id="9ea58-111">You can also use TLGs to create representative environments for development and testing of applications, also known as dev/test environments.</span></span>
  
![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

<span data-ttu-id="9ea58-113">Aprire la [Guida al lab di test](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) per consultare una mappa di tutti gli articoli della guida al lab di test di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="9ea58-113">Go to the [Test Lab Guide Stack](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>

<span data-ttu-id="9ea58-114">[![Serie di guide al lab di test di Microsoft 365 per le aziende](../media/m365-enterprise-test-lab-guides/microsoft-365-enterprise-tlg-stack.png)](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)</span><span class="sxs-lookup"><span data-stu-id="9ea58-114">[![The Microsoft 365 for enterprise Test Lab Guide stack](../media/m365-enterprise-test-lab-guides/microsoft-365-enterprise-tlg-stack.png)](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)</span></span>

## <a name="base-configuration"></a><span data-ttu-id="9ea58-115">Configurazione di base</span><span class="sxs-lookup"><span data-stu-id="9ea58-115">Base configuration</span></span>

<span data-ttu-id="9ea58-116">First, you create a test environment for [Microsoft 365 for enterprise](https://docs.microsoft.com/microsoft-365-enterprise/) that includes Office 365 E5, Enterprise Mobility + Security (EMS) E5, and Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="9ea58-116">First, you create a test environment for [Microsoft 365 for enterprise](https://docs.microsoft.com/microsoft-365-enterprise/) that includes Office 365 E5, Enterprise Mobility + Security (EMS) E5, and Windows 10 Enterprise.</span></span> <span data-ttu-id="9ea58-117">You can create two different types of base configurations:</span><span class="sxs-lookup"><span data-stu-id="9ea58-117">You can create two different types of base configurations:</span></span>

- <span data-ttu-id="9ea58-118">Usare la [configurazione di base semplificata](lightweight-base-configuration-microsoft-365-enterprise.md) quando si desidera configurare e dimostrare le caratteristiche e le funzionalità di Microsoft 365 per le aziende in un ambiente solo cloud, che non include componenti locali.</span><span class="sxs-lookup"><span data-stu-id="9ea58-118">Use the [lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md) when you want to configure and demonstrate Microsoft 365 for enterprise features and capabilities in a cloud-only environment, which does not include any on-premises components.</span></span>

- <span data-ttu-id="9ea58-119">Usare la [configurazione di base simulata per l'organizzazione](simulated-ent-base-configuration-microsoft-365-enterprise.md) quando si vuole configurare e dimostrare le caratteristiche e le funzionalità di Microsoft 365 per le aziende in un ambiente cloud ibrido, che usa componenti locali come un dominio di Active Directory Domain Services.</span><span class="sxs-lookup"><span data-stu-id="9ea58-119">Use the [simulated enterprise base configuration](simulated-ent-base-configuration-microsoft-365-enterprise.md) when you want to configure and demonstrate Microsoft 365 for enterprise features and capabilities in a hybrid cloud environment, which uses on-premises components such as an Active Directory Domain Services (AD DS) domain.</span></span>

<span data-ttu-id="9ea58-120">È anche possibile creare ambienti di test per Office 365 E5 non aggiungendo la licenza di Microsoft 365 E5 all'ambiente di test di prova o di produzione.</span><span class="sxs-lookup"><span data-stu-id="9ea58-120">You can also create test environments for Office 365 E5 by not adding the Microsoft 365 E5 license to your trial or production test environment.</span></span>
    
## <a name="identity"></a><span data-ttu-id="9ea58-121">Identità</span><span class="sxs-lookup"><span data-stu-id="9ea58-121">Identity</span></span>

<span data-ttu-id="9ea58-122">Per verificare le funzionalità e le capacità relative alla gestione delle identità, vedere:</span><span class="sxs-lookup"><span data-stu-id="9ea58-122">To demonstrate identity-related features and capabilities, see:</span></span>

- [<span data-ttu-id="9ea58-123">Sincronizzazione hash delle password</span><span class="sxs-lookup"><span data-stu-id="9ea58-123">Password hash synchronization</span></span>](password-hash-sync-m365-ent-test-environment.md)
  
   <span data-ttu-id="9ea58-124">Abilitare e testare la sincronizzazione della directory basata su hash delle password da un controller di dominio di AD DS.</span><span class="sxs-lookup"><span data-stu-id="9ea58-124">Enable and test password hash-based directory synchronization from an AD DS domain controller.</span></span>

- [<span data-ttu-id="9ea58-125">Autenticazione pass-through</span><span class="sxs-lookup"><span data-stu-id="9ea58-125">Pass-through authentication</span></span>](pass-through-auth-m365-ent-test-environment.md)
  
   <span data-ttu-id="9ea58-126">Abilitare e testare l'autenticazione pass-through per un controller di dominio di Active Directory Domain Services.</span><span class="sxs-lookup"><span data-stu-id="9ea58-126">Enable and test pass-through authentication to an AD DS domain controller.</span></span>

- [<span data-ttu-id="9ea58-127">Autenticazione federata</span><span class="sxs-lookup"><span data-stu-id="9ea58-127">Federated authentication</span></span>](federated-identity-for-your-office-365-dev-test-environment.md)
  
   <span data-ttu-id="9ea58-128">Abilitare e testare l'autenticazione federata per un controller di dominio di Active Directory Domain Services.</span><span class="sxs-lookup"><span data-stu-id="9ea58-128">Enable and test federated authentication to an AD DS domain controller.</span></span>

- [<span data-ttu-id="9ea58-129">Accesso Single Sign-On facile di Azure AD</span><span class="sxs-lookup"><span data-stu-id="9ea58-129">Azure AD Seamless Single Sign-on</span></span>](single-sign-on-m365-ent-test-environment.md)
  
   <span data-ttu-id="9ea58-130">Attivare e testare l'accesso Single Sign-On facile di Azure AD con un controller di dominio di Active Directory Domain Services.</span><span class="sxs-lookup"><span data-stu-id="9ea58-130">Enable and test Azure AD Seamless Single Sign-on (SSO) with an AD DS domain controller.</span></span>

- [<span data-ttu-id="9ea58-131">Autenticazione a più fattori</span><span class="sxs-lookup"><span data-stu-id="9ea58-131">Multi-factor authentication</span></span>](multi-factor-authentication-microsoft-365-test-environment.md)
  
   <span data-ttu-id="9ea58-132">Abilitare e testare l'autenticazione a più fattori basata su smartphone per un account utente specifico.</span><span class="sxs-lookup"><span data-stu-id="9ea58-132">Enable and test smart phone-based multi-factor authentication for a specific user account.</span></span>

- [<span data-ttu-id="9ea58-133">Proteggere gli account amministratore globale</span><span class="sxs-lookup"><span data-stu-id="9ea58-133">Protect global administrator accounts</span></span>](protect-global-administrator-accounts-microsoft-365-test-environment.md)
 
   <span data-ttu-id="9ea58-134">Bloccare gli account di amministratore globale con criteri di accesso condizionale.</span><span class="sxs-lookup"><span data-stu-id="9ea58-134">Lock down your global administrator accounts with conditional access policies.</span></span>

- [<span data-ttu-id="9ea58-135">Writeback delle password</span><span class="sxs-lookup"><span data-stu-id="9ea58-135">Password writeback</span></span>](password-writeback-m365-ent-test-environment.md)

   <span data-ttu-id="9ea58-136">Usare il writeback delle password per modificare la password per l'account utente di Active Directory Domain Services da Azure AD.</span><span class="sxs-lookup"><span data-stu-id="9ea58-136">Use password writeback to change the password on your AD DS user account from Azure AD.</span></span>

- [<span data-ttu-id="9ea58-137">Reimpostazione delle password</span><span class="sxs-lookup"><span data-stu-id="9ea58-137">Password reset</span></span>](password-reset-m365-ent-test-environment.md)

   <span data-ttu-id="9ea58-138">Utilizzare la reimpostazione password self-service (SSPR) per reimpostare la password.</span><span class="sxs-lookup"><span data-stu-id="9ea58-138">Use self-service password reset (SSPR) to reset your password.</span></span>

- [<span data-ttu-id="9ea58-139">Licenze automatiche e appartenenza a gruppi</span><span class="sxs-lookup"><span data-stu-id="9ea58-139">Automatic licensing and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md)

   <span data-ttu-id="9ea58-140">L'amministrazione di nuovi account è più facile che mai grazie alle licenze automatiche e all'appartenenza a gruppi dinamica.</span><span class="sxs-lookup"><span data-stu-id="9ea58-140">Make administering new accounts easier than ever with automatic licensing and dynamic group membership.</span></span>

- [<span data-ttu-id="9ea58-141">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="9ea58-141">Azure AD Identity Protection</span></span>](azure-ad-identity-protection-microsoft-365-test-environment.md)

   <span data-ttu-id="9ea58-142">Analizzare gli account utente correnti per individuare possibili vulnerabilità.</span><span class="sxs-lookup"><span data-stu-id="9ea58-142">Scan your current user accounts for vulnerabilities.</span></span>

- [<span data-ttu-id="9ea58-143">Accesso a identità e dispositivi</span><span class="sxs-lookup"><span data-stu-id="9ea58-143">Identity and device access</span></span>](identity-device-access-m365-test-environment.md)

   <span data-ttu-id="9ea58-144">Creare un ambiente per testare l'identità consigliata, le configurazioni dei dispositivi di accesso e i criteri di accesso condizionali.</span><span class="sxs-lookup"><span data-stu-id="9ea58-144">Create an environment to test recommended identity and device access configurations and conditional access policies.</span></span>


## <a name="mobile-device-management"></a><span data-ttu-id="9ea58-145">Gestione dei dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="9ea58-145">Mobile device management</span></span>

<span data-ttu-id="9ea58-146">Per verificare le funzionalità e le capacità relative alla gestione dei dispositivi mobili, vedere:</span><span class="sxs-lookup"><span data-stu-id="9ea58-146">To demonstrate mobile device management-related features and capabilities, see:</span></span>

- [<span data-ttu-id="9ea58-147">Criteri di conformità dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="9ea58-147">Device compliance policies</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="9ea58-148">Creare un gruppo di utenti e un criterio di conformità dispositivo per i dispositivi Windows 10.</span><span class="sxs-lookup"><span data-stu-id="9ea58-148">Create a user group and a device compliance policy for Windows 10 devices.</span></span>
    
- [<span data-ttu-id="9ea58-149">Registrazione di dispositivi iOS e Android</span><span class="sxs-lookup"><span data-stu-id="9ea58-149">Enroll iOS and Android devices</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
   
   <span data-ttu-id="9ea58-150">Registrare dispositivi iOS e Android e gestirli in remoto.</span><span class="sxs-lookup"><span data-stu-id="9ea58-150">Enroll iOS or Android devices and manage them remotely.</span></span>


## <a name="information-protection"></a><span data-ttu-id="9ea58-151">Protezione delle informazioni</span><span class="sxs-lookup"><span data-stu-id="9ea58-151">Information protection</span></span>

<span data-ttu-id="9ea58-152">Per verificare le funzionalità e le capacità relative alla gestione delle informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="9ea58-152">To demonstrate information protection-related features and capabilities, see:</span></span>

- [<span data-ttu-id="9ea58-153">Sicurezza di Microsoft 365 aumentata</span><span class="sxs-lookup"><span data-stu-id="9ea58-153">Increased Microsoft 365 security</span></span>](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="9ea58-154">Configurare le impostazioni per una sicurezza aumentata di Microsoft 365 ed esaminare gli strumenti incorporati per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="9ea58-154">Configure settings for increased Microsoft 365 security and investigate built-in security tools.</span></span>
  
- [<span data-ttu-id="9ea58-155">Classificazione dei dati</span><span class="sxs-lookup"><span data-stu-id="9ea58-155">Data classification</span></span>](data-classification-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="9ea58-156">Configurare e applicare le etichette a un documento in un sito del team di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="9ea58-156">Configure and apply labels to a document in a SharePoint Online team site.</span></span>
    
- [<span data-ttu-id="9ea58-157">Gestione accessi con privilegi</span><span class="sxs-lookup"><span data-stu-id="9ea58-157">Privileged access management</span></span>](privileged-access-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="9ea58-158">Configurare la gestione degli accessi con privilegi per l'accesso just-in-time alle attività con privilegi e privilegi elevati nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9ea58-158">Configure privileged access management for just-in-time access to elevated and privileged tasks in your organization.</span></span>


