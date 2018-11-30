---
title: Criteri uscita dell'infrastruttura di protezione delle informazioni
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Esaminare i criteri relativi ai servizi e all'infrastruttura basati sulla protezione delle informazioni per verificare che la configurazione soddisfi i criteri di Microsoft 365 Enterprise.
ms.openlocfilehash: 10d7b3b888999b65e5faff81e9a2d32e595294cf
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868807"
---
# <a name="information-protection-infrastructure-exit-criteria"></a><span data-ttu-id="26af7-103">Criteri uscita dell'infrastruttura di protezione delle informazioni</span><span class="sxs-lookup"><span data-stu-id="26af7-103">Information protection infrastructure exit criteria</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="26af7-104">Prima del completamento dell'infrastruttura di base, assicurarsi che l'infrastruttura di protezione delle informazioni soddisfi le condizioni.</span><span class="sxs-lookup"><span data-stu-id="26af7-104">Before you are complete with your foundation infrastructure, make sure that your information protection infrastructure meets these conditions.</span></span> 

<a name="crit-infoprotect-step1"></a>
## <a name="required-security-and-information-protection-levels-for-your-organization-are-defined"></a><span data-ttu-id="26af7-105">Necessario: vengono definiti i livelli di protezione delle informazioni e di sicurezza dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="26af7-105">Required: Security and information protection levels for your organization are defined</span></span>

<span data-ttu-id="26af7-p101">Sono stati pianificati e determinati i livelli di sicurezza in base alle esigenze dell'organizzazione. Questi livelli definiscono un livello minimo di sicurezza e livelli aggiuntivi per informazioni sempre più riservate e la relativa sicurezza dei dati necessaria.</span><span class="sxs-lookup"><span data-stu-id="26af7-p101">You've planned for and determined the security levels that your organization needs. These levels define a minimum level of security and additional levels for increasingly sensitive information and their required data security.</span></span>

<span data-ttu-id="26af7-108">Come minimo, si usano tre livelli di sicurezza:</span><span class="sxs-lookup"><span data-stu-id="26af7-108">At a minimum, you are using three security levels:</span></span>

- <span data-ttu-id="26af7-109">Protezione di base</span><span class="sxs-lookup"><span data-stu-id="26af7-109">Baseline</span></span>
- <span data-ttu-id="26af7-110">Dati sensibili</span><span class="sxs-lookup"><span data-stu-id="26af7-110">Sensitive</span></span>
- <span data-ttu-id="26af7-111">Protezione per ambienti altamente regolamentati</span><span class="sxs-lookup"><span data-stu-id="26af7-111">Highly regulated</span></span>

<span data-ttu-id="26af7-112">Se necessario, il [Passaggio 1](infoprotect-define-sec-infoprotect-levels.md) può aiutare a soddisfare questo requisito.</span><span class="sxs-lookup"><span data-stu-id="26af7-112">If needed, [Step 1](infoprotect-define-sec-infoprotect-levels.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step4"></a>
## <a name="required-increased-security-for-office-365-is-configured"></a><span data-ttu-id="26af7-113">Necessario: è stata configurata maggiore sicurezza per Office 365</span><span class="sxs-lookup"><span data-stu-id="26af7-113">Required: Increased security for Office 365 is configured</span></span>

<span data-ttu-id="26af7-114">Sono state configurate le seguenti impostazioni per aumentare la sicurezza in base alle informazioni in [Configurare il tenant di Office 365 per una maggiore sicurezza](https://support.office.com/article/Configure-your-Office-365-tenant-for-increased-security-8d274fe3-db51-4107-ba64-865e7155b355):</span><span class="sxs-lookup"><span data-stu-id="26af7-114">You've configured the following settings for increased security based on the information in [Configure your Office 365 tenant for increased security](https://support.office.com/article/Configure-your-Office-365-tenant-for-increased-security-8d274fe3-db51-4107-ba64-865e7155b355):</span></span>

- <span data-ttu-id="26af7-115">Criteri di gestione delle minacce nel Centro sicurezza e conformità di Office 365</span><span class="sxs-lookup"><span data-stu-id="26af7-115">Threat management policies in the Office 365 Security & Compliance Center</span></span>
- <span data-ttu-id="26af7-116">Impostazioni tenant aggiuntive di Exchange Online</span><span class="sxs-lookup"><span data-stu-id="26af7-116">Additional Exchange Online tenant-wide settings</span></span>
- <span data-ttu-id="26af7-117">Criteri di condivisione del tenant nell'interfaccia di amministrazione di SharePoint</span><span class="sxs-lookup"><span data-stu-id="26af7-117">Tenant-wide sharing policies in SharePoint admin center</span></span>
- <span data-ttu-id="26af7-118">Impostazioni di Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="26af7-118">Settings in Azure Active Directory</span></span>

<span data-ttu-id="26af7-119">È stata anche abilitata [Office 365 Advanced Threat Protection (ATP)](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607#turniton).</span><span class="sxs-lookup"><span data-stu-id="26af7-119">You've also [enabled Office 365 Advanced Threat Protection (ATP)](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607#turniton).</span></span>

<span data-ttu-id="26af7-120">Se necessario, il [Passaggio 3](infoprotect-configure-increased-security-office-365.md) può aiutare a soddisfare questo requisito.</span><span class="sxs-lookup"><span data-stu-id="26af7-120">If needed, [Step 3](infoprotect-configure-increased-security-office-365.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step3"></a>
## <a name="optional-classification-is-configured-across-your-environment"></a><span data-ttu-id="26af7-121">Facoltativo: la classificazione è configurata nell'ambiente</span><span class="sxs-lookup"><span data-stu-id="26af7-121">Optional: Classification is configured across your environment</span></span>

<span data-ttu-id="26af7-122">Si è collaborato con i team legale e della conformità per sviluppare una classificazione appropriata e uno schema di etichettatura per i dati dell'organizzazione, che include quanto segue:</span><span class="sxs-lookup"><span data-stu-id="26af7-122">You've worked with your legal and compliance teams to develop an appropriate classification and labeling scheme for your organization’s data, which include the following:</span></span>

- <span data-ttu-id="26af7-123">Tipi di dati riservati</span><span class="sxs-lookup"><span data-stu-id="26af7-123">Sensitive data types</span></span>
- <span data-ttu-id="26af7-124">Etichette di Office 365</span><span class="sxs-lookup"><span data-stu-id="26af7-124">Office 365 labels</span></span>
- <span data-ttu-id="26af7-125">Etichette di Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="26af7-125">Azure Information Protection labels</span></span>

<span data-ttu-id="26af7-126">Se necessario, il [Passaggio 2](infoprotect-configure-classification.md) può aiutare a soddisfare questo requisito.</span><span class="sxs-lookup"><span data-stu-id="26af7-126">If needed, [Step 2](infoprotect-configure-classification.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step5"></a>
## <a name="optional-configure-privileged-access-management-in-office-365"></a><span data-ttu-id="26af7-127">Facoltativo: configurare la gestione degli accessi con privilegi in Office 365</span><span class="sxs-lookup"><span data-stu-id="26af7-127">Optional: Configure privileged access management in Office 365</span></span>

<span data-ttu-id="26af7-p102">Le informazioni dell’argomento [Configurare la gestione degli accessi con privilegi in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) sono state usate per consentire l'accesso con privilegi e creare uno o più criteri di accesso con privilegi all'interno dell'organizzazione di Office 365. I criteri sono stati configurati e l'accesso just-in-time è abilitato per l'accesso a dati sensibili o a impostazioni di configurazione cruciali.</span><span class="sxs-lookup"><span data-stu-id="26af7-p102">You've used the information in the [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic to enable privileged access  and create one or more privileged access policies in your Office 365 organization. You've configured these policies and just-in-time access is enabled for access to sensitive data or access to critical configuration settings.</span></span>

<span data-ttu-id="26af7-130">Se necessario, il [Passaggio 4](infoprotect-configure-privileged-access-management.md) può aiutare a soddisfare questo requisito.</span><span class="sxs-lookup"><span data-stu-id="26af7-130">If needed, [Step 4](infoprotect-configure-privileged-access-management.md) can help you meet this requirement.</span></span> 

## <a name="next-step"></a><span data-ttu-id="26af7-131">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="26af7-131">Next Step</span></span>

<span data-ttu-id="26af7-132">Ora si è pronti a distribuire i [carichi di lavoro e gli scenari](deploy-workloads.md), come Microsoft Teams ed Exchange Online, che vengono eseguiti sull'infrastruttura di base di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="26af7-132">You're now ready to deploy [workloads and scenarios](deploy-workloads.md), such as Microsoft Teams and Exchange Online, that run on top of your Microsoft 365 Enterprise foundation infrastructure.</span></span>
