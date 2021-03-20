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
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: 706d5449-45e5-4b0c-a012-ab60501899ad
description: Utilizzare queste guide al lab di test per configurare dimostrazioni, modelli di verifica o ambienti di sviluppo e test per Microsoft 365 per le aziende.
ms.openlocfilehash: a006f549d0ac68562faee9c935df7f15161b2f12
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909599"
---
# <a name="microsoft-365-for-enterprise-test-lab-guides"></a><span data-ttu-id="4ae74-103">Guide al lab di test di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="4ae74-103">Microsoft 365 for enterprise Test Lab Guides</span></span>

<span data-ttu-id="4ae74-104">*Questo articolo si applica sia a Microsoft 365 per le aziende che a Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="4ae74-104">*This applies to both Microsoft 365 for enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="4ae74-p101">Le guide al lab di test (TLG) facilitano la conoscenza dei prodotti Microsoft. Forniscono istruzioni prescrittive per configurare ambienti di testing semplificati ma rappresentativi. È possibile utilizzare questi ambienti per la dimostrazione, la personalizzazione o la creazione di modelli di verifica complessi per la durata di un abbonamento di valutazione o a pagamento.</span><span class="sxs-lookup"><span data-stu-id="4ae74-p101">Test Lab Guides (TLGs) help you quickly learn about Microsoft products. They provide prescriptive instructions to configure simplified but representative test environments. You can use these environments for demonstration, customization, or creation of complex proofs of concept for the duration of a trial or paid subscription.</span></span>

<span data-ttu-id="4ae74-108">I TG sono progettati per essere modulari.</span><span class="sxs-lookup"><span data-stu-id="4ae74-108">TLGs are designed to be modular.</span></span> <span data-ttu-id="4ae74-109">Si basano l'uno sull'altro per creare più configurazioni che corrispondano più strettamente alle esigenze di apprendimento o di configurazione di test.</span><span class="sxs-lookup"><span data-stu-id="4ae74-109">They build upon each other to create multiple configurations that more closely match your learning or test configuration needs.</span></span> <span data-ttu-id="4ae74-110">L'esperienza hands-on "L'ho creata io e funziona" consente di comprendere i requisiti di distribuzione di un nuovo prodotto o scenario, in modo da poter pianificare meglio l'hosting in produzione.</span><span class="sxs-lookup"><span data-stu-id="4ae74-110">The "I built it out myself and it works" hands-on experience helps you understand the deployment requirements of a new product or scenario, so that you can better plan for hosting it in production.</span></span>

<span data-ttu-id="4ae74-111">È inoltre possibile utilizzare IGG per creare ambienti rappresentativi per sviluppare e testare applicazioni, note anche come ambienti di sviluppo/test.</span><span class="sxs-lookup"><span data-stu-id="4ae74-111">You can also use TLGs to create representative environments to develop and test applications, also known as dev/test environments.</span></span>
  
![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

<span data-ttu-id="4ae74-113">Per una mappa visiva a tutti gli articoli dello stack guida del laboratorio di testing di Microsoft 365 per le aziende, espandere il grafico seguente o passare a [Microsoft 365 per enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="4ae74-113">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, expand the following graphic or go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

<span data-ttu-id="4ae74-114">[![Serie di guide al lab di test di Microsoft 365 per le aziende](../media/m365-enterprise-test-lab-guides/microsoft-365-enterprise-tlg-stack.png)](../downloads/Microsoft365EnterpriseTLGStack.pdf)</span><span class="sxs-lookup"><span data-stu-id="4ae74-114">[![The Microsoft 365 for enterprise Test Lab Guide stack](../media/m365-enterprise-test-lab-guides/microsoft-365-enterprise-tlg-stack.png)](../downloads/Microsoft365EnterpriseTLGStack.pdf)</span></span>

## <a name="base-configuration"></a><span data-ttu-id="4ae74-115">Configurazione di base</span><span class="sxs-lookup"><span data-stu-id="4ae74-115">Base configuration</span></span>

<span data-ttu-id="4ae74-116">Innanzitutto, creare un ambiente di testing [per Microsoft 365 per le aziende](/microsoft-365-enterprise/).</span><span class="sxs-lookup"><span data-stu-id="4ae74-116">First, create a test environment for [Microsoft 365 for enterprise](/microsoft-365-enterprise/).</span></span> <span data-ttu-id="4ae74-117">È possibile creare due diversi tipi di configurazioni di base:</span><span class="sxs-lookup"><span data-stu-id="4ae74-117">You can create two different types of base configurations:</span></span>

- <span data-ttu-id="4ae74-118">[Configurazione di base](lightweight-base-configuration-microsoft-365-enterprise.md) leggera: utilizzare questa opzione quando si desidera configurare e dimostrare le funzionalità e le funzionalità di Microsoft 365 per le aziende in un ambiente solo cloud, che non include componenti locali.</span><span class="sxs-lookup"><span data-stu-id="4ae74-118">[Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md) - Use this when you want to configure and demonstrate Microsoft 365 for enterprise features and capabilities in a cloud-only environment, which does not include any on-premises components.</span></span>

- <span data-ttu-id="4ae74-119">[Configurazione](simulated-ent-base-configuration-microsoft-365-enterprise.md) di base aziendale simulata: utilizzare questa opzione quando si desidera configurare e dimostrare le funzionalità e le funzionalità di Microsoft 365 per le aziende in un ambiente cloud ibrido, che utilizza componenti locali, ad esempio un dominio di Servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4ae74-119">[Simulated enterprise base configuration](simulated-ent-base-configuration-microsoft-365-enterprise.md) - Use this when you want to configure and demonstrate Microsoft 365 for enterprise features and capabilities in a hybrid cloud environment, which uses on-premises components such as an Active Directory Domain Services (AD DS) domain.</span></span>

<span data-ttu-id="4ae74-120">È anche possibile creare ambienti di test per Office 365 E5 non aggiungendo la licenza di Microsoft 365 E5 all'ambiente di test di prova o di produzione.</span><span class="sxs-lookup"><span data-stu-id="4ae74-120">You can also create test environments for Office 365 E5 by not adding the Microsoft 365 E5 license to your trial or production test environment.</span></span>
    
## <a name="identity"></a><span data-ttu-id="4ae74-121">Identità</span><span class="sxs-lookup"><span data-stu-id="4ae74-121">Identity</span></span>

<span data-ttu-id="4ae74-122">Per verificare le funzionalità e le capacità relative alla gestione delle identità, vedere:</span><span class="sxs-lookup"><span data-stu-id="4ae74-122">To demonstrate identity-related features and capabilities, see:</span></span>

- [<span data-ttu-id="4ae74-123">Sincronizzazione hash delle password</span><span class="sxs-lookup"><span data-stu-id="4ae74-123">Password hash synchronization</span></span>](password-hash-sync-m365-ent-test-environment.md)
  
   <span data-ttu-id="4ae74-124">Abilitare e testare la sincronizzazione della directory basata su hash delle password da un controller di dominio di AD DS.</span><span class="sxs-lookup"><span data-stu-id="4ae74-124">Enable and test password hash-based directory synchronization from an AD DS domain controller.</span></span>

- [<span data-ttu-id="4ae74-125">Autenticazione pass-through</span><span class="sxs-lookup"><span data-stu-id="4ae74-125">Pass-through authentication</span></span>](pass-through-auth-m365-ent-test-environment.md)
  
   <span data-ttu-id="4ae74-126">Abilitare e testare l'autenticazione pass-through per un controller di dominio di Active Directory Domain Services.</span><span class="sxs-lookup"><span data-stu-id="4ae74-126">Enable and test pass-through authentication to an AD DS domain controller.</span></span>

- [<span data-ttu-id="4ae74-127">Autenticazione federata</span><span class="sxs-lookup"><span data-stu-id="4ae74-127">Federated authentication</span></span>](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
   <span data-ttu-id="4ae74-128">Abilitare e testare l'autenticazione federata per un controller di dominio di Active Directory Domain Services.</span><span class="sxs-lookup"><span data-stu-id="4ae74-128">Enable and test federated authentication to an AD DS domain controller.</span></span>

- [<span data-ttu-id="4ae74-129">Accesso Single Sign-On facile di Azure AD</span><span class="sxs-lookup"><span data-stu-id="4ae74-129">Azure AD Seamless Single Sign-on</span></span>](single-sign-on-m365-ent-test-environment.md)
  
   <span data-ttu-id="4ae74-130">Abilitare e testare Azure AD Seamless Single Sign-On (SSO senza soluzione di continuità) con un controller di dominio di Servizi di dominio Active Directory.Enable and test Azure AD Seamless Single Sign-On (Seamless SSO) with an AD DS domain controller.</span><span class="sxs-lookup"><span data-stu-id="4ae74-130">Enable and test Azure AD Seamless Single Sign-on (Seamless SSO) with an AD DS domain controller.</span></span>

- [<span data-ttu-id="4ae74-131">Autenticazione a più fattori</span><span class="sxs-lookup"><span data-stu-id="4ae74-131">Multi-factor authentication</span></span>](multi-factor-authentication-microsoft-365-test-environment.md)
  
   <span data-ttu-id="4ae74-132">Abilitare e testare l'autenticazione a più fattori basata su smartphone per un account utente specifico.</span><span class="sxs-lookup"><span data-stu-id="4ae74-132">Enable and test smart phone-based multi-factor authentication for a specific user account.</span></span>

- [<span data-ttu-id="4ae74-133">Proteggere gli account amministratore globale</span><span class="sxs-lookup"><span data-stu-id="4ae74-133">Protect global administrator accounts</span></span>](protect-global-administrator-accounts-microsoft-365-test-environment.md)

   <span data-ttu-id="4ae74-134">Bloccare gli account di amministratore globale con criteri di accesso condizionale.</span><span class="sxs-lookup"><span data-stu-id="4ae74-134">Lock down your global administrator accounts with conditional access policies.</span></span>

- [<span data-ttu-id="4ae74-135">Writeback delle password</span><span class="sxs-lookup"><span data-stu-id="4ae74-135">Password writeback</span></span>](password-writeback-m365-ent-test-environment.md)

   <span data-ttu-id="4ae74-136">Usare il writeback delle password per modificare la password per l'account utente di Active Directory Domain Services da Azure AD.</span><span class="sxs-lookup"><span data-stu-id="4ae74-136">Use password writeback to change the password on your AD DS user account from Azure AD.</span></span>

- [<span data-ttu-id="4ae74-137">Reimpostazione delle password</span><span class="sxs-lookup"><span data-stu-id="4ae74-137">Password reset</span></span>](password-reset-m365-ent-test-environment.md)

   <span data-ttu-id="4ae74-138">Utilizzare la reimpostazione della password self-service per reimpostare la password.</span><span class="sxs-lookup"><span data-stu-id="4ae74-138">Use self-service password reset to reset your password.</span></span>

- [<span data-ttu-id="4ae74-139">Licenze automatiche e appartenenza a gruppi</span><span class="sxs-lookup"><span data-stu-id="4ae74-139">Automatic licensing and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md)

   <span data-ttu-id="4ae74-140">L'amministrazione di nuovi account è più facile che mai grazie alle licenze automatiche e all'appartenenza a gruppi dinamica.</span><span class="sxs-lookup"><span data-stu-id="4ae74-140">Make administering new accounts easier than ever with automatic licensing and dynamic group membership.</span></span>

- [<span data-ttu-id="4ae74-141">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="4ae74-141">Azure AD Identity Protection</span></span>](azure-ad-identity-protection-microsoft-365-test-environment.md)

   <span data-ttu-id="4ae74-142">Analizzare gli account utente correnti per individuare possibili vulnerabilità.</span><span class="sxs-lookup"><span data-stu-id="4ae74-142">Scan your current user accounts for vulnerabilities.</span></span>

- [<span data-ttu-id="4ae74-143">Accesso a identità e dispositivi</span><span class="sxs-lookup"><span data-stu-id="4ae74-143">Identity and device access</span></span>](identity-device-access-m365-test-environment.md)

   <span data-ttu-id="4ae74-144">Creare un ambiente per testare l'identità consigliata, le configurazioni dei dispositivi di accesso e i criteri di accesso condizionali.</span><span class="sxs-lookup"><span data-stu-id="4ae74-144">Create an environment to test recommended identity and device access configurations and conditional access policies.</span></span>

## <a name="mobile-device-management"></a><span data-ttu-id="4ae74-145">Gestione dei dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="4ae74-145">Mobile device management</span></span>

<span data-ttu-id="4ae74-146">Per verificare le funzionalità e le capacità relative alla gestione dei dispositivi mobili, vedere:</span><span class="sxs-lookup"><span data-stu-id="4ae74-146">To demonstrate mobile device management-related features and capabilities, see:</span></span>

- [<span data-ttu-id="4ae74-147">Criteri di conformità dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="4ae74-147">Device compliance policies</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="4ae74-148">Creare un gruppo di utenti e un criterio di conformità dispositivo per i dispositivi Windows 10.</span><span class="sxs-lookup"><span data-stu-id="4ae74-148">Create a user group and a device compliance policy for Windows 10 devices.</span></span>
    
- [<span data-ttu-id="4ae74-149">Registrazione di dispositivi iOS e Android</span><span class="sxs-lookup"><span data-stu-id="4ae74-149">Enroll iOS and Android devices</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
   
   <span data-ttu-id="4ae74-150">Registrare dispositivi iOS e Android e gestirli in remoto.</span><span class="sxs-lookup"><span data-stu-id="4ae74-150">Enroll iOS or Android devices and manage them remotely.</span></span>

## <a name="information-protection"></a><span data-ttu-id="4ae74-151">Protezione delle informazioni</span><span class="sxs-lookup"><span data-stu-id="4ae74-151">Information protection</span></span>

<span data-ttu-id="4ae74-152">Per verificare le funzionalità e le capacità relative alla gestione delle informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="4ae74-152">To demonstrate information protection-related features and capabilities, see:</span></span>

- [<span data-ttu-id="4ae74-153">Sicurezza di Microsoft 365 aumentata</span><span class="sxs-lookup"><span data-stu-id="4ae74-153">Increased Microsoft 365 security</span></span>](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="4ae74-154">Configurare le impostazioni per una sicurezza aumentata di Microsoft 365 ed esaminare gli strumenti incorporati per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="4ae74-154">Configure settings for increased Microsoft 365 security and investigate built-in security tools.</span></span>
  
- [<span data-ttu-id="4ae74-155">Classificazione dei dati</span><span class="sxs-lookup"><span data-stu-id="4ae74-155">Data classification</span></span>](data-classification-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="4ae74-156">Configurare e applicare le etichette a un documento in un sito del team di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="4ae74-156">Configure and apply labels to a document in a SharePoint Online team site.</span></span>
    
- [<span data-ttu-id="4ae74-157">Gestione accessi con privilegi</span><span class="sxs-lookup"><span data-stu-id="4ae74-157">Privileged access management</span></span>](privileged-access-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="4ae74-158">Configurare la gestione degli accessi con privilegi per l'accesso just-in-time alle attività con privilegi e privilegi elevati nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4ae74-158">Configure privileged access management for just-in-time access to elevated and privileged tasks in your organization.</span></span>