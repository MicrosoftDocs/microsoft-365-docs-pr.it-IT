---
title: Criteri uscita dell'infrastruttura di protezione delle informazioni
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/25/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Esaminare i criteri relativi ai servizi e all'infrastruttura basati sulla protezione delle informazioni per verificare che la configurazione soddisfi i criteri di Microsoft 365 Enterprise.
ms.openlocfilehash: 9c74a3994a1a404583326f65f1cec579fccbe659
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "33400040"
---
# <a name="information-protection-infrastructure-exit-criteria"></a><span data-ttu-id="3c2ca-103">Criteri uscita dell'infrastruttura di protezione delle informazioni</span><span class="sxs-lookup"><span data-stu-id="3c2ca-103">Information protection infrastructure exit criteria</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="3c2ca-104">Verificare che l'infrastruttura di protezione delle informazioni soddisfi i criteri obbligatori seguenti e assicurarsi di tenere in considerazione quelli facoltativi.</span><span class="sxs-lookup"><span data-stu-id="3c2ca-104">Make sure your information protection infrastructure meets the following required criteria and that you've considered those that are optional.</span></span>

<a name="crit-infoprotect-step1"></a>
## <a name="required-security-and-information-protection-levels-for-your-organization-are-defined"></a><span data-ttu-id="3c2ca-105">Necessario: vengono definiti i livelli di protezione delle informazioni e di sicurezza dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="3c2ca-105">Required: Security and information protection levels for your organization are defined</span></span>

<span data-ttu-id="3c2ca-p101">Sono stati pianificati e determinati i livelli di sicurezza in base alle esigenze dell'organizzazione. Questi livelli definiscono un livello minimo di sicurezza e livelli aggiuntivi per informazioni sempre più riservate e la relativa sicurezza dei dati necessaria.</span><span class="sxs-lookup"><span data-stu-id="3c2ca-p101">You've planned for and determined the security levels that your organization needs. These levels define a minimum level of security and additional levels for increasingly sensitive information and their required data security.</span></span>

<span data-ttu-id="3c2ca-108">Come minimo, si usano tre livelli di sicurezza:</span><span class="sxs-lookup"><span data-stu-id="3c2ca-108">At a minimum, you are using three security levels:</span></span>

- <span data-ttu-id="3c2ca-109">Protezione di base</span><span class="sxs-lookup"><span data-stu-id="3c2ca-109">Baseline</span></span>
- <span data-ttu-id="3c2ca-110">Dati sensibili</span><span class="sxs-lookup"><span data-stu-id="3c2ca-110">Sensitive</span></span>
- <span data-ttu-id="3c2ca-111">Protezione per ambienti altamente regolamentati</span><span class="sxs-lookup"><span data-stu-id="3c2ca-111">Highly regulated</span></span>

<span data-ttu-id="3c2ca-112">Se necessario, il [Passaggio 1](infoprotect-define-sec-infoprotect-levels.md) può aiutare a soddisfare questo requisito.</span><span class="sxs-lookup"><span data-stu-id="3c2ca-112">If needed, [Step 1](infoprotect-define-sec-infoprotect-levels.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step3"></a>
## <a name="required-increased-security-for-microsoft-365-is-configured"></a><span data-ttu-id="3c2ca-113">Obbligatorio: è stato configurato un livello di sicurezza maggiore per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3c2ca-113">Required: Increased security for Microsoft 365 is configured</span></span>

<span data-ttu-id="3c2ca-114">Sono state configurate le impostazioni seguenti per una [sicurezza maggiore di Office 365](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security):</span><span class="sxs-lookup"><span data-stu-id="3c2ca-114">You've configured the following settings for [Office 365 increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security):</span></span>

- <span data-ttu-id="3c2ca-115">Criteri di gestione delle minacce nel Centro sicurezza Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3c2ca-115">Threat management policies in the Microsoft 365 security Center</span></span>
- <span data-ttu-id="3c2ca-116">Impostazioni tenant aggiuntive di Exchange Online</span><span class="sxs-lookup"><span data-stu-id="3c2ca-116">Additional Exchange Online tenant-wide settings</span></span>
- <span data-ttu-id="3c2ca-117">Criteri di condivisione del tenant nell'interfaccia di amministrazione di SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="3c2ca-117">Tenant-wide sharing policies in SharePoint admin center</span></span>
- <span data-ttu-id="3c2ca-118">Impostazioni di Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="3c2ca-118">Settings in Azure Active Directory (Azure AD)</span></span>

<span data-ttu-id="3c2ca-119">È stato inoltre [abilitato Office 365 Advanced Threat Protection (ATP) per SharePoint Online, OneDrive e Microsoft Teams](https://docs.microsoft.com/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams).</span><span class="sxs-lookup"><span data-stu-id="3c2ca-119">You've also [enabled Office 365 Advanced Threat Protection (ATP) for SharePoint, OneDrive, and Microsoft Teams](https://docs.microsoft.com/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams).</span></span>

<span data-ttu-id="3c2ca-120">Se necessario, il [Passaggio 3](infoprotect-configure-increased-security-office-365.md) può aiutare a soddisfare questo requisito.</span><span class="sxs-lookup"><span data-stu-id="3c2ca-120">If needed, [Step 3](infoprotect-configure-increased-security-office-365.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step2"></a>
## <a name="optional-classification-is-configured-across-your-environment"></a><span data-ttu-id="3c2ca-121">Facoltativo: la classificazione è configurata nell'ambiente</span><span class="sxs-lookup"><span data-stu-id="3c2ca-121">Optional: Classification is configured across your environment</span></span>

<span data-ttu-id="3c2ca-122">Si è collaborato con i team legale e della conformità per sviluppare una classificazione appropriata e uno schema di etichettatura per la governance dei dati dell'organizzazione e i criteri di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="3c2ca-122">You've worked with your legal and compliance teams to develop an appropriate classification and labeling scheme for your organization’s data governance and security policies.</span></span> 

<span data-ttu-id="3c2ca-123">I criteri corrispondono alla configurazione e distribuzione di:</span><span class="sxs-lookup"><span data-stu-id="3c2ca-123">Those policies correspond to the configuration and deployment of:</span></span>

- <span data-ttu-id="3c2ca-124">Tipi di dati riservati</span><span class="sxs-lookup"><span data-stu-id="3c2ca-124">Sensitive data types</span></span>
- <span data-ttu-id="3c2ca-125">Etichette di conservazione</span><span class="sxs-lookup"><span data-stu-id="3c2ca-125">Retention labels</span></span>
- <span data-ttu-id="3c2ca-126">Etichette di riservatezza</span><span class="sxs-lookup"><span data-stu-id="3c2ca-126">Sensitivity labels</span></span>
- <span data-ttu-id="3c2ca-127">Etichette di Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="3c2ca-127">Azure Information Protection labels</span></span>

<span data-ttu-id="3c2ca-128">Se necessario, il [Passaggio 2](infoprotect-configure-classification.md) può aiutare a soddisfare questo requisito.</span><span class="sxs-lookup"><span data-stu-id="3c2ca-128">If needed, [Step 2](infoprotect-configure-classification.md) can help you meet this requirement.</span></span> 


<a name="crit-infoprotect-step4"></a>
## <a name="optional-windows-information-protection-is-deployed-across-your-environment"></a><span data-ttu-id="3c2ca-129">Facoltativo: Windows Information Protection viene distribuito nel proprio ambiente</span><span class="sxs-lookup"><span data-stu-id="3c2ca-129">Optional: Windows Information Protection is deployed across your environment</span></span>

<span data-ttu-id="3c2ca-130">I dispositivi Windows 10 Enterprise registrati hanno un criterio di Intune distribuito e applicato che definisce:</span><span class="sxs-lookup"><span data-stu-id="3c2ca-130">Your enrolled Windows 10 Enterprise devices have an Intune policy deployed and applied that defines:</span></span>

- <span data-ttu-id="3c2ca-131">Quali applicazioni proteggere.</span><span class="sxs-lookup"><span data-stu-id="3c2ca-131">Which apps to protect.</span></span>
- <span data-ttu-id="3c2ca-132">Il livello di protezione.</span><span class="sxs-lookup"><span data-stu-id="3c2ca-132">The level of protection.</span></span>
- <span data-ttu-id="3c2ca-133">L’estensione della protezione.</span><span class="sxs-lookup"><span data-stu-id="3c2ca-133">Where the protection extends.</span></span>

<span data-ttu-id="3c2ca-134">Se necessario, il [Passaggio 4](infoprotect-deploy-windows-information-protection.md) può aiutare a soddisfare questo requisito.</span><span class="sxs-lookup"><span data-stu-id="3c2ca-134">If needed, [Step 4](infoprotect-deploy-windows-information-protection.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step5"></a>
## <a name="optional-office-365-data-loss-prevention-dlp-is-deployed"></a><span data-ttu-id="3c2ca-135">Facoltativo: Prevenzione perdita di dati (DLP) di Office 365</span><span class="sxs-lookup"><span data-stu-id="3c2ca-135">Optional: Office 365 Data Loss Prevention (DLP) is deployed</span></span>

<span data-ttu-id="3c2ca-136">Il set di criteri DLP è stato analizzato, testato e quindi distribuito - con le posizioni e le regole con condizioni e azioni- richieste dall'organizzazione per la protezione dei clienti e altri tipi di dati riservati e conformarsi alle normative e i requisiti locali e industriali.</span><span class="sxs-lookup"><span data-stu-id="3c2ca-136">You have analyzed, tested, and then rolled out the set of DLP policies—with locations and rules with conditions and actions—that your organization requires to protect customer and other types of private data and to adhere to industry and regional regulations and requirements.</span></span>

<span data-ttu-id="3c2ca-137">Il personale di sicurezza e conformità dati utilizza il dashboard di Sicurezza e conformità di Office 365 per monitorare gli eventi imprevisti del DLP.</span><span class="sxs-lookup"><span data-stu-id="3c2ca-137">Your data compliance and security staff are using the Office 365 Security & Compliance dashboard to monitor DLP incidents.</span></span>

<span data-ttu-id="3c2ca-138">Se necessario, il [Passaggio 5](infoprotect-data-loss-prevention.md) può aiutare a soddisfare questo requisito.</span><span class="sxs-lookup"><span data-stu-id="3c2ca-138">If needed, [Step 4](infoprotect-data-loss-prevention.md) can help you meet this requirement.</span></span> 


<a name="crit-infoprotect-step6"></a>
## <a name="optional-configure-privileged-access-management-in-office-365"></a><span data-ttu-id="3c2ca-139">Facoltativo: configurare la gestione degli accessi con privilegi in Office 365</span><span class="sxs-lookup"><span data-stu-id="3c2ca-139">Optional: Configure privileged access management in Office 365</span></span>

<span data-ttu-id="3c2ca-140">Sono state usate le informazioni contenute nell'argomento [Configurare la gestione degli accessi con privilegi in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) per abilitare l'accesso con privilegi e creare uno o più criteri di accesso con privilegi all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3c2ca-140">You've used the information in the [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic to enable privileged access and create one or more privileged access policies in your organization.</span></span> <span data-ttu-id="3c2ca-141">I criteri sono stati configurati ed è abilitato l'accesso just-in-time ai dati sensibili o alle impostazioni di configurazione critiche.</span><span class="sxs-lookup"><span data-stu-id="3c2ca-141">You've configured these policies and just-in-time access is enabled for access to sensitive data or access to critical configuration settings.</span></span>

<span data-ttu-id="3c2ca-142">Se necessario, il [Passaggio 6](infoprotect-configure-privileged-access-management.md) può aiutare a soddisfare questo requisito.</span><span class="sxs-lookup"><span data-stu-id="3c2ca-142">If needed, [Step 4](infoprotect-configure-privileged-access-management.md) can help you meet this requirement.</span></span> 

## <a name="results-and-next-steps"></a><span data-ttu-id="3c2ca-143">Risultati e passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="3c2ca-143">Results and next steps</span></span>

<span data-ttu-id="3c2ca-144">L'infrastruttura di protezione delle informazioni per Microsoft 365 Enterprise usa livelli di sicurezza definiti, maggiore sicurezza per Office 365, classificazione con etichette e tipi di dati riservati, Windows Information Protection, criteri di prevenzione della perdita di dati e gestione degli accessi con privilegi.</span><span class="sxs-lookup"><span data-stu-id="3c2ca-144">Your information protection infrastructure for Microsoft 365 Enterprise uses defined security levels, increased security for Office 365, classification using sensitive data types and labels, and privileged access management.</span></span>

<span data-ttu-id="3c2ca-145">Se si sta seguendo la distribuzione end-to-end di Microsoft 365 Enterprise, è possibile a questo punto far sì che i [carichi di lavoro e gli scenari](deploy-workloads.md) sfruttino tutte le funzionalità e la configurazione dell'infrastruttura di base.</span><span class="sxs-lookup"><span data-stu-id="3c2ca-145">If you're following the end-to-end deployment of Microsoft 365 Enterprise, you're now ready to have your [workloads and scenarios](deploy-workloads.md) take advantage of all the features and configuration of your foundation infrastructure.</span></span>
