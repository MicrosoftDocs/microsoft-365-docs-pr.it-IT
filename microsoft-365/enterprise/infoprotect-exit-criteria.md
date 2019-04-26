---
title: Criteri uscita dell'infrastruttura di protezione delle informazioni
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/10/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Esaminare i criteri relativi ai servizi e all'infrastruttura basati sulla protezione delle informazioni per verificare che la configurazione soddisfi i criteri di Microsoft 365 Enterprise.
ms.openlocfilehash: 681b3bb2500680b4f5d5801486347aec1b801714
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283698"
---
# <a name="information-protection-infrastructure-exit-criteria"></a><span data-ttu-id="ddfa1-103">Criteri uscita dell'infrastruttura di protezione delle informazioni</span><span class="sxs-lookup"><span data-stu-id="ddfa1-103">Information protection infrastructure exit criteria</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="ddfa1-104">Verificare che l'infrastruttura di protezione delle informazioni soddisfi i criteri obbligatori seguenti e assicurarsi di tenere in considerazione quelli facoltativi.</span><span class="sxs-lookup"><span data-stu-id="ddfa1-104">Make sure your information protection infrastructure meets the following required criteria and that you've considered those that are optional.</span></span>

<a name="crit-infoprotect-step1"></a>
## <a name="required-security-and-information-protection-levels-for-your-organization-are-defined"></a><span data-ttu-id="ddfa1-105">Necessario: vengono definiti i livelli di protezione delle informazioni e di sicurezza dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="ddfa1-105">Required: Security and information protection levels for your organization are defined</span></span>

<span data-ttu-id="ddfa1-p101">Sono stati pianificati e determinati i livelli di sicurezza in base alle esigenze dell'organizzazione. Questi livelli definiscono un livello minimo di sicurezza e livelli aggiuntivi per informazioni sempre più riservate e la relativa sicurezza dei dati necessaria.</span><span class="sxs-lookup"><span data-stu-id="ddfa1-p101">You've planned for and determined the security levels that your organization needs. These levels define a minimum level of security and additional levels for increasingly sensitive information and their required data security.</span></span>

<span data-ttu-id="ddfa1-108">Come minimo, si usano tre livelli di sicurezza:</span><span class="sxs-lookup"><span data-stu-id="ddfa1-108">At a minimum, you are using three security levels:</span></span>

- <span data-ttu-id="ddfa1-109">Protezione di base</span><span class="sxs-lookup"><span data-stu-id="ddfa1-109">Baseline</span></span>
- <span data-ttu-id="ddfa1-110">Dati sensibili</span><span class="sxs-lookup"><span data-stu-id="ddfa1-110">Sensitive</span></span>
- <span data-ttu-id="ddfa1-111">Protezione per ambienti altamente regolamentati</span><span class="sxs-lookup"><span data-stu-id="ddfa1-111">Highly regulated</span></span>

<span data-ttu-id="ddfa1-112">Se necessario, il [Passaggio 1](infoprotect-define-sec-infoprotect-levels.md) può aiutare a soddisfare questo requisito.</span><span class="sxs-lookup"><span data-stu-id="ddfa1-112">If needed, [Step 1](infoprotect-define-sec-infoprotect-levels.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step4"></a>
## <a name="required-increased-security-for-microsoft-365-is-configured"></a><span data-ttu-id="ddfa1-113">Obbligatorio: è stato configurato un livello di sicurezza maggiore per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ddfa1-113">Required: Increased security for Office 365 is configured</span></span>

<span data-ttu-id="ddfa1-114">Sono state configurate le impostazioni seguenti per una [sicurezza maggiore di Office 365](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security):</span><span class="sxs-lookup"><span data-stu-id="ddfa1-114">You've configured the following settings for increased security based on the information in [Configure your Office 365 tenant for increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security):</span></span>

- <span data-ttu-id="ddfa1-115">Criteri di gestione delle minacce nel Centro sicurezza Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ddfa1-115">Threat management policies in the Microsoft 365 security Center</span></span>
- <span data-ttu-id="ddfa1-116">Impostazioni tenant aggiuntive di Exchange Online</span><span class="sxs-lookup"><span data-stu-id="ddfa1-116">Additional Exchange Online tenant-wide settings</span></span>
- <span data-ttu-id="ddfa1-117">Criteri di condivisione del tenant nell'interfaccia di amministrazione di SharePoint</span><span class="sxs-lookup"><span data-stu-id="ddfa1-117">Tenant-wide sharing policies in SharePoint admin center</span></span>
- <span data-ttu-id="ddfa1-118">Impostazioni di Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="ddfa1-118">Settings in Azure Active Directory</span></span>

<span data-ttu-id="ddfa1-119">È stato inoltre [abilitato Office 365 Advanced Threat Protection (ATP) per SharePoint Online, OneDrive e Microsoft Teams](https://docs.microsoft.com/it-IT/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams).</span><span class="sxs-lookup"><span data-stu-id="ddfa1-119">You've also [enabled Office 365 Advanced Threat Protection (ATP) for SharePoint, OneDrive, and Microsoft Teams](https://docs.microsoft.com/it-IT/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams).</span></span>

<span data-ttu-id="ddfa1-120">Se necessario, il [Passaggio 3](infoprotect-configure-increased-security-office-365.md) può aiutare a soddisfare questo requisito.</span><span class="sxs-lookup"><span data-stu-id="ddfa1-120">If needed, [Step 3](infoprotect-configure-increased-security-office-365.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step3"></a>
## <a name="optional-classification-is-configured-across-your-environment"></a><span data-ttu-id="ddfa1-121">Facoltativo: la classificazione è configurata nell'ambiente</span><span class="sxs-lookup"><span data-stu-id="ddfa1-121">Optional: Classification is configured across your environment</span></span>

<span data-ttu-id="ddfa1-122">Si è collaborato con i team legale e della conformità per sviluppare una classificazione appropriata e uno schema di etichettatura per la governance dei dati dell'organizzazione e i criteri di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="ddfa1-122">You've worked with your legal and compliance teams to develop an appropriate classification and labeling scheme for your organization’s data, which include the following:</span></span> 

<span data-ttu-id="ddfa1-123">I criteri corrispondono alla configurazione e distribuzione di:</span><span class="sxs-lookup"><span data-stu-id="ddfa1-123">Those policies correspond to the configuration and deployment of:</span></span>

- <span data-ttu-id="ddfa1-124">Tipi di dati riservati</span><span class="sxs-lookup"><span data-stu-id="ddfa1-124">Sensitive data types</span></span>
- <span data-ttu-id="ddfa1-125">Etichette di conservazione</span><span class="sxs-lookup"><span data-stu-id="ddfa1-125">Retention labels</span></span>
- <span data-ttu-id="ddfa1-126">Etichette di riservatezza</span><span class="sxs-lookup"><span data-stu-id="ddfa1-126">Sensitivity labels</span></span>
- <span data-ttu-id="ddfa1-127">Etichette di Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="ddfa1-127">Azure Information Protection labels</span></span>

<span data-ttu-id="ddfa1-128">Se necessario, il [Passaggio 2](infoprotect-configure-classification.md) può aiutare a soddisfare questo requisito.</span><span class="sxs-lookup"><span data-stu-id="ddfa1-128">If needed, [Step 2](infoprotect-configure-classification.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step5"></a>
## <a name="optional-configure-privileged-access-management-in-office-365"></a><span data-ttu-id="ddfa1-129">Facoltativo: configurare la gestione degli accessi con privilegi in Office 365</span><span class="sxs-lookup"><span data-stu-id="ddfa1-129">Optional: Configure privileged access management in Office 365</span></span>

<span data-ttu-id="ddfa1-130">Sono state usate le informazioni contenute nell'argomento [Configurare la gestione degli accessi con privilegi in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) per abilitare l'accesso con privilegi e creare uno o più criteri di accesso con privilegi all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ddfa1-130">You've used the information in the [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic to enable privileged access  and create one or more privileged access policies in your Office 365 organization. You've configured these policies and just-in-time access is enabled for access to sensitive data or access to critical configuration settings.</span></span> <span data-ttu-id="ddfa1-131">I criteri sono stati configurati ed è abilitato l'accesso just-in-time ai dati sensibili o alle impostazioni di configurazione critiche.</span><span class="sxs-lookup"><span data-stu-id="ddfa1-131">You've configured these policies and just-in-time access is enabled for access to sensitive data or access to critical configuration settings.</span></span>

<span data-ttu-id="ddfa1-132">Se necessario, il [Passaggio 4](infoprotect-configure-privileged-access-management.md) può aiutare a soddisfare questo requisito.</span><span class="sxs-lookup"><span data-stu-id="ddfa1-132">If needed, [Step 4](infoprotect-configure-privileged-access-management.md) can help you meet this requirement.</span></span> 

## <a name="results-and-next-steps"></a><span data-ttu-id="ddfa1-133">Risultati e passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="ddfa1-133">Validation and next steps</span></span>

<span data-ttu-id="ddfa1-134">L'infrastruttura di protezione delle informazioni per Microsoft 365 Enterprise usa livelli di sicurezza definiti, maggiore sicurezza per Office 365, classificazione con etichette e tipi di dati riservati e gestione degli accessi con privilegi.</span><span class="sxs-lookup"><span data-stu-id="ddfa1-134">Your information protection infrastructure for Microsoft 365 Enterprise uses defined security levels, increased security for Office 365, classification using sensitive data types and labels, and privileged access management.</span></span>

<span data-ttu-id="ddfa1-135">Se si sta seguendo la distribuzione end-to-end di Microsoft 365 Enterprise, è possibile a questo punto far sì che i [carichi di lavoro e gli scenari](deploy-workloads.md) sfruttino tutte le funzionalità e la configurazione dell'infrastruttura di base.</span><span class="sxs-lookup"><span data-stu-id="ddfa1-135">If you're following the end-to-end deployment of Microsoft 365 Enterprise, you're now ready to have your [workloads and scenarios](deploy-workloads.md) take advantage of all the features and configuration of your foundation infrastructure.</span></span>
