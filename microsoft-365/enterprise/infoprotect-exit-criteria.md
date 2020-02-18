---
title: Criteri uscita dell'infrastruttura di protezione delle informazioni
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Esaminare i criteri relativi ai servizi e all'infrastruttura basati sulla protezione delle informazioni per verificare che la configurazione soddisfi i criteri di Microsoft 365 Enterprise.
ms.openlocfilehash: 28eff02ea870dcfca7e2e32580ed6a3a9e8a9484
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42067113"
---
# <a name="information-protection-infrastructure-exit-criteria"></a><span data-ttu-id="63c90-103">Criteri uscita dell'infrastruttura di protezione delle informazioni</span><span class="sxs-lookup"><span data-stu-id="63c90-103">Information protection infrastructure exit criteria</span></span>

![Fase 6: protezione delle informazioni](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="63c90-105">Verificare che l'infrastruttura di protezione delle informazioni soddisfi i criteri obbligatori seguenti e assicurarsi di tenere in considerazione quelli facoltativi.</span><span class="sxs-lookup"><span data-stu-id="63c90-105">Make sure your information protection infrastructure meets the following required criteria and that you've considered those that are optional.</span></span>

<a name="crit-infoprotect-step1"></a>
## <a name="required-security-and-information-protection-levels-for-your-organization-are-defined"></a><span data-ttu-id="63c90-106">Necessario: vengono definiti i livelli di protezione delle informazioni e di sicurezza dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="63c90-106">Required: Security and information protection levels for your organization are defined</span></span>

<span data-ttu-id="63c90-p101">Sono stati pianificati e determinati i livelli di sicurezza in base alle esigenze dell'organizzazione. Questi livelli definiscono un livello minimo di sicurezza e livelli aggiuntivi per informazioni sempre più riservate e la relativa sicurezza dei dati necessaria.</span><span class="sxs-lookup"><span data-stu-id="63c90-p101">You've planned for and determined the security levels that your organization needs. These levels define a minimum level of security and additional levels for increasingly sensitive information and their required data security.</span></span>

<span data-ttu-id="63c90-109">Come minimo, si usano tre livelli di sicurezza:</span><span class="sxs-lookup"><span data-stu-id="63c90-109">At a minimum, you are using three security levels:</span></span>

- <span data-ttu-id="63c90-110">Protezione di base</span><span class="sxs-lookup"><span data-stu-id="63c90-110">Baseline</span></span>
- <span data-ttu-id="63c90-111">Dati sensibili</span><span class="sxs-lookup"><span data-stu-id="63c90-111">Sensitive</span></span>
- <span data-ttu-id="63c90-112">Protezione per ambienti altamente regolamentati</span><span class="sxs-lookup"><span data-stu-id="63c90-112">Highly regulated</span></span>

<span data-ttu-id="63c90-113">Se necessario, il [Passaggio 1](infoprotect-define-sec-infoprotect-levels.md) può aiutare a soddisfare questo requisito.</span><span class="sxs-lookup"><span data-stu-id="63c90-113">If needed, [Step 1](infoprotect-define-sec-infoprotect-levels.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step3"></a>
## <a name="required-increased-security-for-microsoft-365-is-configured"></a><span data-ttu-id="63c90-114">Obbligatorio: è stato configurato un livello di sicurezza maggiore per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="63c90-114">Required: Increased security for Microsoft 365 is configured</span></span>

<span data-ttu-id="63c90-115">Sono state configurate le impostazioni seguenti per una [sicurezza maggiore di Office 365](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security):</span><span class="sxs-lookup"><span data-stu-id="63c90-115">You've configured the following settings for [Office 365 increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security):</span></span>

- <span data-ttu-id="63c90-116">Criteri di gestione delle minacce nel Centro sicurezza Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="63c90-116">Threat management policies in the Microsoft 365 security Center</span></span>
- <span data-ttu-id="63c90-117">Impostazioni tenant aggiuntive di Exchange Online</span><span class="sxs-lookup"><span data-stu-id="63c90-117">Additional Exchange Online tenant-wide settings</span></span>
- <span data-ttu-id="63c90-118">Criteri di condivisione del tenant nell'interfaccia di amministrazione di SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="63c90-118">Tenant-wide sharing policies in SharePoint Online admin center</span></span>
- <span data-ttu-id="63c90-119">Impostazioni di Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="63c90-119">Settings in Azure Active Directory (Azure AD)</span></span>

<span data-ttu-id="63c90-120">È stato inoltre [abilitato Office 365 Advanced Threat Protection (ATP) per SharePoint Online, OneDrive e Microsoft Teams](https://docs.microsoft.com/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams).</span><span class="sxs-lookup"><span data-stu-id="63c90-120">You've also [enabled Office 365 Advanced Threat Protection (ATP) for SharePoint, OneDrive, and Microsoft Teams](https://docs.microsoft.com/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams).</span></span>

<span data-ttu-id="63c90-121">Se necessario, il [Passaggio 3](infoprotect-configure-increased-security-office-365.md) può aiutare a soddisfare questo requisito.</span><span class="sxs-lookup"><span data-stu-id="63c90-121">If needed, [Step 3](infoprotect-configure-increased-security-office-365.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step2"></a>
## <a name="optional-classification-is-configured-across-your-environment"></a><span data-ttu-id="63c90-122">Facoltativo: la classificazione è configurata nell'ambiente</span><span class="sxs-lookup"><span data-stu-id="63c90-122">Optional: Classification is configured across your environment</span></span>

<span data-ttu-id="63c90-123">Si è collaborato con i team legale e della conformità per sviluppare una classificazione appropriata e uno schema di etichettatura per la governance dei dati dell'organizzazione e i criteri di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="63c90-123">You've worked with your legal and compliance teams to develop an appropriate classification and labeling scheme for your organization’s data governance and security policies.</span></span> 

<span data-ttu-id="63c90-124">I criteri corrispondono alla configurazione e distribuzione di:</span><span class="sxs-lookup"><span data-stu-id="63c90-124">Those policies correspond to the configuration and deployment of:</span></span>

- <span data-ttu-id="63c90-125">Tipi di dati riservati</span><span class="sxs-lookup"><span data-stu-id="63c90-125">Sensitive data types</span></span>
- <span data-ttu-id="63c90-126">Etichette di conservazione</span><span class="sxs-lookup"><span data-stu-id="63c90-126">Retention labels</span></span>
- <span data-ttu-id="63c90-127">Etichette di riservatezza</span><span class="sxs-lookup"><span data-stu-id="63c90-127">Sensitivity labels</span></span>
- <span data-ttu-id="63c90-128">Etichette di Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="63c90-128">Azure Information Protection labels</span></span>

<span data-ttu-id="63c90-129">Se necessario, il [Passaggio 2](infoprotect-configure-classification.md) può aiutare a soddisfare questo requisito.</span><span class="sxs-lookup"><span data-stu-id="63c90-129">If needed, [Step 2](infoprotect-configure-classification.md) can help you meet this requirement.</span></span> 


<a name="crit-infoprotect-step4"></a>
## <a name="optional-windows-information-protection-is-deployed-across-your-environment"></a><span data-ttu-id="63c90-130">Facoltativo: Windows Information Protection viene distribuito nel proprio ambiente</span><span class="sxs-lookup"><span data-stu-id="63c90-130">Optional: Windows Information Protection is deployed across your environment</span></span>

<span data-ttu-id="63c90-131">I dispositivi Windows 10 Enterprise registrati hanno un criterio di Intune distribuito e applicato che definisce:</span><span class="sxs-lookup"><span data-stu-id="63c90-131">Your enrolled Windows 10 Enterprise devices have an Intune policy deployed and applied that defines:</span></span>

- <span data-ttu-id="63c90-132">Quali applicazioni proteggere.</span><span class="sxs-lookup"><span data-stu-id="63c90-132">Which apps to protect.</span></span>
- <span data-ttu-id="63c90-133">Il livello di protezione.</span><span class="sxs-lookup"><span data-stu-id="63c90-133">The level of protection.</span></span>
- <span data-ttu-id="63c90-134">L’estensione della protezione.</span><span class="sxs-lookup"><span data-stu-id="63c90-134">Where the protection extends.</span></span>

<span data-ttu-id="63c90-135">Se necessario, il [Passaggio 4](infoprotect-deploy-windows-information-protection.md) può aiutare a soddisfare questo requisito.</span><span class="sxs-lookup"><span data-stu-id="63c90-135">If needed, [Step 4](infoprotect-deploy-windows-information-protection.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step5"></a>
## <a name="optional-office-365-data-loss-prevention-dlp-is-deployed"></a><span data-ttu-id="63c90-136">Facoltativo: Prevenzione perdita di dati (DLP) di Office 365</span><span class="sxs-lookup"><span data-stu-id="63c90-136">Optional: Office 365 Data Loss Prevention (DLP) is deployed</span></span>

<span data-ttu-id="63c90-137">Il set di criteri DLP è stato analizzato, testato e quindi distribuito - con le posizioni e le regole con condizioni e azioni- richieste dall'organizzazione per la protezione dei clienti e altri tipi di dati riservati e conformarsi alle normative e i requisiti locali e industriali.</span><span class="sxs-lookup"><span data-stu-id="63c90-137">You have analyzed, tested, and then rolled out the set of DLP policies—with locations and rules with conditions and actions—that your organization requires to protect customer and other types of private data and to adhere to industry and regional regulations and requirements.</span></span>

<span data-ttu-id="63c90-138">Il personale di sicurezza e conformità dati utilizza il dashboard di Sicurezza e conformità di Office 365 per monitorare gli eventi imprevisti del DLP.</span><span class="sxs-lookup"><span data-stu-id="63c90-138">Your data compliance and security staff are using the Office 365 Security & Compliance dashboard to monitor DLP incidents.</span></span>

<span data-ttu-id="63c90-139">Se necessario, il [Passaggio 5](infoprotect-data-loss-prevention.md) può aiutare a soddisfare questo requisito.</span><span class="sxs-lookup"><span data-stu-id="63c90-139">If needed, [Step 5](infoprotect-data-loss-prevention.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step6"></a>
## <a name="optional-email-encryption-is-configured"></a><span data-ttu-id="63c90-140">Facoltativo: la crittografia della posta elettronica è configurata</span><span class="sxs-lookup"><span data-stu-id="63c90-140">Optional: Email encryption is configured</span></span>

<span data-ttu-id="63c90-141">La crittografia della posta elettronica seguente è stata configurata in base alle esigenze dell'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="63c90-141">You've configured the following email encryption as needed for your organization:</span></span>

|||
|:-------|:-----|
| <span data-ttu-id="63c90-142">**Metodo di crittografia**</span><span class="sxs-lookup"><span data-stu-id="63c90-142">**Encryption method**</span></span> | <span data-ttu-id="63c90-143">**Per la posta elettronica inviata**</span><span class="sxs-lookup"><span data-stu-id="63c90-143">**For email sent**</span></span> |
| [<span data-ttu-id="63c90-144">Office 365 Message Encryption (OME)</span><span class="sxs-lookup"><span data-stu-id="63c90-144">Office 365 Message Encryption (OME)</span></span>](https://docs.microsoft.com/Office365/SecurityCompliance/ome)  | <span data-ttu-id="63c90-145">A contatti esterni all'organizzazione con la crittografia</span><span class="sxs-lookup"><span data-stu-id="63c90-145">Outside your organization with encryption</span></span> |
| [<span data-ttu-id="63c90-146">Information Rights Management (IRM)</span><span class="sxs-lookup"><span data-stu-id="63c90-146">Information Rights Management (IRM)</span></span>](https://docs.microsoft.com/office365/SecurityCompliance/information-rights-management-in-exchange-online) | <span data-ttu-id="63c90-147">Sia con crittografia che con le autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="63c90-147">With both encryption and permissions</span></span> |
| [<span data-ttu-id="63c90-148">S/MIME (Secure/Multipurpose Internet Mail Extensions)</span><span class="sxs-lookup"><span data-stu-id="63c90-148">Secure/Multipurpose Internet Mail Extensions (S/MIME)</span></span>](https://docs.microsoft.com/Exchange/policy-and-compliance/smime) | <span data-ttu-id="63c90-149">Sia con la crittografia che con le firme digitale con crittografia a chiave pubblica</span><span class="sxs-lookup"><span data-stu-id="63c90-149">With both encryption and digital signatures using public key cryptography</span></span> |
|||

<span data-ttu-id="63c90-150">Se necessario, il [Passaggio 6](infoprotect-email-encryption.md) può aiutare a soddisfare questo requisito.</span><span class="sxs-lookup"><span data-stu-id="63c90-150">If needed, [Step 6](infoprotect-email-encryption.md) can help you meet this requirement.</span></span>

<a name="crit-infoprotect-step7"></a>
## <a name="optional-configure-privileged-access-management-in-office-365"></a><span data-ttu-id="63c90-151">Facoltativo: configurare la gestione degli accessi con privilegi in Office 365</span><span class="sxs-lookup"><span data-stu-id="63c90-151">Optional: Configure privileged access management in Office 365</span></span>

<span data-ttu-id="63c90-152">Sono state usate le informazioni contenute nell'argomento [Configurare la gestione degli accessi con privilegi in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) per abilitare l'accesso con privilegi e creare uno o più criteri di accesso con privilegi all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="63c90-152">You've used the information in the [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic to enable privileged access and create one or more privileged access policies in your organization.</span></span> <span data-ttu-id="63c90-153">I criteri sono stati configurati ed è abilitato l'accesso just-in-time ai dati sensibili o alle impostazioni di configurazione critiche.</span><span class="sxs-lookup"><span data-stu-id="63c90-153">You've configured these policies and just-in-time access is enabled for access to sensitive data or access to critical configuration settings.</span></span>

<span data-ttu-id="63c90-154">Se necessario, il [Passaggio 7](infoprotect-configure-privileged-access-management.md) può aiutare a soddisfare questo requisito.</span><span class="sxs-lookup"><span data-stu-id="63c90-154">If needed, [Step 7](infoprotect-configure-privileged-access-management.md) can help you meet this requirement.</span></span> 

## <a name="results-and-next-steps"></a><span data-ttu-id="63c90-155">Risultati e passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="63c90-155">Results and next steps</span></span>

<span data-ttu-id="63c90-156">L'infrastruttura di protezione delle informazioni per Microsoft 365 Enterprise usa livelli di sicurezza definiti, maggiore sicurezza per Office 365, classificazione con etichette e tipi di dati riservati, Windows Information Protection, criteri di prevenzione della perdita di dati, crittografia della posta elettronica e gestione degli accessi con privilegi.</span><span class="sxs-lookup"><span data-stu-id="63c90-156">Your information protection infrastructure for Microsoft 365 Enterprise uses defined security levels, increased security for Office 365, classification using sensitive data types and labels, Windows Information Protection, Data Loss Prevention, email encryption, and privileged access management.</span></span>

<span data-ttu-id="63c90-157">Se si sta seguendo la distribuzione end-to-end di Microsoft 365 Enterprise, è possibile a questo punto far sì che i [carichi di lavoro e gli scenari](deploy-workloads.md) sfruttino tutte le funzionalità e la configurazione dell'infrastruttura di base.</span><span class="sxs-lookup"><span data-stu-id="63c90-157">If you're following the end-to-end deployment of Microsoft 365 Enterprise, you're now ready to have your [workloads and scenarios](deploy-workloads.md) take advantage of all the features and configuration of your foundation infrastructure.</span></span>
