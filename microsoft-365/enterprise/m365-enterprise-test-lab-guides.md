---
title: Guide al lab di test di Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2018
ms.audience: ITPro
ms.topic: hub-page
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
ms.assetid: 706d5449-45e5-4b0c-a012-ab60501899ad
description: Utilizzare queste guide al lab di test per configurare dimostrazioni, modelli di verifica o ambienti di sviluppo e test per Microsoft 365 Enterprise.
ms.openlocfilehash: df723647748532936e40bbdb4e34ff698b9fa650
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868779"
---
# <a name="microsoft-365-enterprise-test-lab-guides"></a><span data-ttu-id="60986-103">Guide al lab di test di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="60986-103">Microsoft 365 Enterprise Test Lab Guides</span></span>

<span data-ttu-id="60986-p101">Le guide al lab di test (TLG) facilitano la conoscenza dei prodotti Microsoft. Forniscono istruzioni prescrittive per configurare ambienti di testing semplificati ma rappresentativi. È possibile utilizzare questi ambienti per la dimostrazione, la personalizzazione o la creazione di modelli di verifica complessi per la durata di un abbonamento di valutazione o a pagamento.</span><span class="sxs-lookup"><span data-stu-id="60986-p101">Test Lab Guides (TLGs) help you quickly learn about Microsoft products. They provide prescriptive instructions to configure simplified but representative test environments. You can use these environments for demonstration, customization, or creation of complex proofs of concept for the duration of a trial or paid subscription.</span></span> 

<span data-ttu-id="60986-p102">Le TLG sono progettate per essere modulari. Sono collegate l'una all'altra per creare diverse configurazioni che corrispondono più strettamente alle esigenze di configurazione di test o di apprendimento. L'esperienza pratica "fai da te" consente di comprendere i requisiti di implementazione di un nuovo prodotto o di un nuovo scenario, in modo da poter pianificare meglio l'hosting in produzione.</span><span class="sxs-lookup"><span data-stu-id="60986-p102">TLGs are designed to be modular. They build upon each other to create multiple configurations that more closely match your learning or test configuration needs. The "I built it out myself and it works" hands-on experience helps you understand the deployment requirements of a new product or scenario so you can better plan for hosting it in production.</span></span>

<span data-ttu-id="60986-110">Queste guide permettono di creare anche ambienti appositi per lo sviluppo e il testing delle applicazioni, noti anche con il nome di ambienti di sviluppo/testing.</span><span class="sxs-lookup"><span data-stu-id="60986-110">You can also use TLGs to create representative environments for development and testing of applications, also known as dev/test environments.</span></span>
  
![Guide del laboratorio di testing per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="60986-112">Fare clic [qui](https://aka.ms/m365etlgstack) per consultare una mappa di tutti gli articoli relativi alla guida al lab test di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="60986-112">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="base-configuration"></a><span data-ttu-id="60986-113">Configurazione di base</span><span class="sxs-lookup"><span data-stu-id="60986-113">Base configuration</span></span>

<span data-ttu-id="60986-p103">Per prima cosa è necessario creare un ambiente di testing per [Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/) che includa Office 365 E5, Enterprise Mobility + Security (EMS) E5 e Windows 10 Enterprise. È possibile creare due tipi di configurazione di base diversi:</span><span class="sxs-lookup"><span data-stu-id="60986-p103">First, you create a test environment for [Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/) that includes Office 365 E5, Enterprise Mobility + Security (EMS) E5, and Windows 10 Enterprise. You can create two different types of base configurations:</span></span>

- <span data-ttu-id="60986-116">Usare la [configurazione di base semplificata](lightweight-base-configuration-microsoft-365-enterprise.md) quando si desidera configurare e dimostrare le caratteristiche e le funzionalità di Microsoft 365 Enterprise in un ambiente solo cloud, che non include componenti locali.</span><span class="sxs-lookup"><span data-stu-id="60986-116">Use the [lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md) when you want to configure and demonstrate Microsoft 365 Enterprise features and capabilities in a cloud-only environment, which does not include any on-premises components.</span></span>

- <span data-ttu-id="60986-117">Usare la [configurazione di base simulata per l’organizzazione](simulated-ent-base-configuration-microsoft-365-enterprise.md) quando si desidera configurare e dimostrare le caratteristiche e le funzionalità di Microsoft 365 Enterprise in un ambiente cloud ibrido, che usa componenti locali come un dominio di Windows Server Active Directory (AD).  </span><span class="sxs-lookup"><span data-stu-id="60986-117">Use the [simulated enterprise base configuration](simulated-ent-base-configuration-microsoft-365-enterprise.md) when you want to configure and demonstrate Microsoft 365 Enterprise features and capabilities in a hybrid cloud environment, which uses on-premises components such as a Windows Server Active Directory (AD) domain.</span></span>
    
## <a name="identity"></a><span data-ttu-id="60986-118">Identità</span><span class="sxs-lookup"><span data-stu-id="60986-118">Identity</span></span>

<span data-ttu-id="60986-119">Per verificare le funzionalità e le capacità relative alla gestione delle identità, vedere:</span><span class="sxs-lookup"><span data-stu-id="60986-119">To demonstrate identity-related features and capabilities, see:</span></span>

- [<span data-ttu-id="60986-120">Sincronizzazione hash delle password</span><span class="sxs-lookup"><span data-stu-id="60986-120">Password hash synchronization</span></span>](password-hash-sync-m365-ent-test-environment.md)
  
   <span data-ttu-id="60986-121">Abilitare e testare la sincronizzazione della directory basata su hash delle password da un controller di dominio di Windows Server AD.</span><span class="sxs-lookup"><span data-stu-id="60986-121">Enable and test password hash-based directory synchronization from a Windows Server AD domain controller.</span></span>

- [<span data-ttu-id="60986-122">Autenticazione pass-through</span><span class="sxs-lookup"><span data-stu-id="60986-122">Pass-through authentication</span></span>](pass-through-auth-m365-ent-test-environment.md)
  
   <span data-ttu-id="60986-123">Abillitare e testare l'autenticazione pass-through per un controller di dominio di Windows Server AD.</span><span class="sxs-lookup"><span data-stu-id="60986-123">Enable and test pass-through authentication to a Windows Server AD domain controller.</span></span>

- [<span data-ttu-id="60986-124">Accesso Single Sign-On facile di Azure AD</span><span class="sxs-lookup"><span data-stu-id="60986-124">Azure AD Seamless Single Sign-on</span></span>](single-sign-on-m365-ent-test-environment.md)
  
   <span data-ttu-id="60986-125">Attivare e testare l'accesso Single Sign-On facile di Azure AD con un controller di dominio di Windows Server AD.</span><span class="sxs-lookup"><span data-stu-id="60986-125">Enable and test Azure AD Seamless Single Sign-on (SSO) with a Windows Server AD domain controller.</span></span>

- [<span data-ttu-id="60986-126">Autenticazione a più fattori</span><span class="sxs-lookup"><span data-stu-id="60986-126">Multi-factor authentication</span></span>](multi-factor-authentication-microsoft-365-test-environment.md)
  
   <span data-ttu-id="60986-127">Abilitare e testare l'autenticazione a più fattori basata su smartphone per un account utente specifico.</span><span class="sxs-lookup"><span data-stu-id="60986-127">Enable and test smart phone-based multi-factor authentication for a specific user account.</span></span>

- [<span data-ttu-id="60986-128">Proteggere gli account amministratore globale</span><span class="sxs-lookup"><span data-stu-id="60986-128">Protect global administrator accounts</span></span>](protect-global-administrator-accounts-microsoft-365-test-environment.md)
 
   <span data-ttu-id="60986-129">Bloccare gli account amministratore globale con Office 365 Cloud App Security e i criteri di accesso condizionale.</span><span class="sxs-lookup"><span data-stu-id="60986-129">Lock down your global administrator accounts with Office 365 Cloud App Security and conditional access policies.</span></span>

- [<span data-ttu-id="60986-130">Reimpostazione delle password</span><span class="sxs-lookup"><span data-stu-id="60986-130">Password reset</span></span>](password-reset-m365-ent-test-environment.md)

   <span data-ttu-id="60986-131">Utilizzare la reimpostazione password self-service (SSPR) per reimpostare la password.</span><span class="sxs-lookup"><span data-stu-id="60986-131">Use self-service password reset (SSPR) to reset your password.</span></span>

- [<span data-ttu-id="60986-132">Licenze automatiche e appartenenza a gruppi</span><span class="sxs-lookup"><span data-stu-id="60986-132">Automatic licensing and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md)

   <span data-ttu-id="60986-133">L'amministrazione di nuovi account è più facile che mai grazie alle licenze automatiche e all'appartenenza a gruppi dinamica.</span><span class="sxs-lookup"><span data-stu-id="60986-133">Make administering new accounts easier than ever with automatic licensing and dynamic group membership.</span></span>

- [<span data-ttu-id="60986-134">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="60986-134">Azure AD Identity Protection</span></span>](azure-ad-identity-protection-microsoft-365-test-environment.md)

   <span data-ttu-id="60986-135">Analizzare gli account utente correnti per individuare possibili vulnerabilità.</span><span class="sxs-lookup"><span data-stu-id="60986-135">Scan your current user accounts for vulnerabilities.</span></span>

## <a name="mobile-device-management"></a><span data-ttu-id="60986-136">Gestione dei dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="60986-136">Mobile device management</span></span>

<span data-ttu-id="60986-137">Per verificare le funzionalità e le capacità relative alla gestione dei dispositivi mobili, vedere:</span><span class="sxs-lookup"><span data-stu-id="60986-137">To demonstrate mobile device management-related features and capabilities, see:</span></span>

- [<span data-ttu-id="60986-138">Criteri MAM</span><span class="sxs-lookup"><span data-stu-id="60986-138">MAM policies</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="60986-139">Creare gruppi utente e criteri di gestione di applicazioni mobili per dispositivi iOS e Android.</span><span class="sxs-lookup"><span data-stu-id="60986-139">Create user groups and mobile application management (MAM) policies for iOS and Android devices.</span></span>
    
- [<span data-ttu-id="60986-140">Registrazione di dispositivi iOS e Android</span><span class="sxs-lookup"><span data-stu-id="60986-140">Enroll iOS and Android devices</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
   
   <span data-ttu-id="60986-141">Registrare dispositivi iOS e Android e gestirli in remoto.</span><span class="sxs-lookup"><span data-stu-id="60986-141">Enroll iOS or Android devices and manage them remotely.</span></span>


## <a name="information-protection"></a><span data-ttu-id="60986-142">Protezione delle informazioni</span><span class="sxs-lookup"><span data-stu-id="60986-142">Information protection</span></span>

<span data-ttu-id="60986-143">Per verificare le funzionalità e le capacità relative alla gestione delle informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="60986-143">To demonstrate information protection-related features and capabilities, see:</span></span>

- [<span data-ttu-id="60986-144">Sicurezza aumentata di Office 365</span><span class="sxs-lookup"><span data-stu-id="60986-144">Increased Office 365 security</span></span>](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="60986-145">Configurare le impostazioni per una sicurezza aumentata di Office 365 ed esaminare gli strumenti incorporati per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="60986-145">Configure settings for increased Office 365 security and investigate built-in security tools.</span></span>
  
- [<span data-ttu-id="60986-146">Classificazione dei dati</span><span class="sxs-lookup"><span data-stu-id="60986-146">Data classification</span></span>](data-classification-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="60986-147">Configurare e applicare le etichette di Office 365 a un documento in un sito del team di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="60986-147">Configure and apply Office 365 labels to a document in a SharePoint Online team site.</span></span>
    
- [<span data-ttu-id="60986-148">Gestione degli accessi con privilegi per l'ambiente di testing di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="60986-148">Privileged access management for your Microsoft 365 Enterprise test environment</span></span>](privileged-access-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="60986-149">Configurare la gestione degli accessi con privilegi per l'accesso just-in-time alle attività con privilegi e privilegi elevati nell'organizzazione di Office 365.</span><span class="sxs-lookup"><span data-stu-id="60986-149">Configure privileged acccess management for just-in-time access to elevated and privileged tasks in your Office 365 organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="60986-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="60986-150">See also</span></span>

[<span data-ttu-id="60986-151">Esperienza di Microsoft Cloud con le guide al lab di test di adozione del cloud</span><span class="sxs-lookup"><span data-stu-id="60986-151">Experience the Microsoft Cloud with Cloud Adoption Test Lab Guides</span></span>](https://mva.microsoft.com/training-courses/experience-the-microsoft-cloud-with-cloud-adoption-test-lab-guides-17960?l=LXNRdhSLE_1000115881)
    
[<span data-ttu-id="60986-152">Pila di Guide al lab di test di One Microsoft Cloud</span><span class="sxs-lookup"><span data-stu-id="60986-152">One Microsoft Cloud Test Lab Guide stack</span></span>](http://aka.ms/catlgstack)
