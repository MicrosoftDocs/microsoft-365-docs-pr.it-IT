---
title: 'Fase 6: protezione delle informazioni'
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
description: I passaggi per distribuire l'infrastruttura di protezione delle informazioni per Microsoft 365 Enterprise.
ms.openlocfilehash: d6e3501e8262a0c3245c6e13da6633ac465276fb
ms.sourcegitcommit: 47c45bd81afdc4867ff2980ced3df31dbad92b84
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/16/2020
ms.locfileid: "44268304"
---
# <a name="phase-6-information-protection"></a><span data-ttu-id="aa1f8-103">Fase 6: protezione delle informazioni</span><span class="sxs-lookup"><span data-stu-id="aa1f8-103">Phase 6: Information protection</span></span>

![Fase 6: protezione delle informazioni](../media/deploy-foundation-infrastructure/infoprotection_icon.png)

<span data-ttu-id="aa1f8-p101">La protezione delle informazioni è un set di criteri e tecnologie che definiscono la modalità di trasmissione, archiviazione ed elaborazione delle informazioni riservate. Durante la Fase 6, è possibile esaminare le impostazioni di protezione delle informazioni e le funzionalità di Microsoft 365 Enterprise che consentono di proteggere i dati per i carichi di lavoro basati sul cloud.</span><span class="sxs-lookup"><span data-stu-id="aa1f8-p101">Information protection is a set of policies and technologies that define how you transmit, store, and process sensitive information. In Phase 6, you step through information protection settings and features of Microsoft 365 Enterprise that help you secure data for your cloud-based workloads.</span></span>

>[!Note]
><span data-ttu-id="aa1f8-107">Se è stata già impostata la protezione delle informazioni, vedere i [criteri uscita](infoprotect-exit-criteria.md) per questa fase per assicurarsi che soddisfino le condizioni facoltative e obbligatorie per Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="aa1f8-107">If you already have already deployed information protection, please see the [exit criteria](infoprotect-exit-criteria.md) for this phase to make sure that it meets the required and optional conditions for Microsoft 365 Enterprise.</span></span>
>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-information-protection-infrastructure"></a><span data-ttu-id="aa1f8-108">Pianificare e distribuire l'infrastruttura di protezione delle informazioni di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="aa1f8-108">Plan and deploy your Microsoft 365 Enterprise information protection infrastructure</span></span> 

<span data-ttu-id="aa1f8-p102">È importante lavorare insieme al team legale e a quello di conformità per determinare se i bisogni dell'organizzazione soddisfino gli standard di conformità come HIPAA, CJIS e RGPD. È anche consigliabile collaborare con il gruppo di sicurezza per determinare gli obiettivi per la protezione delle informazioni per l'organizzazione e per i reparti o i gruppi che richiedono una maggiore protezione.</span><span class="sxs-lookup"><span data-stu-id="aa1f8-p102">It’s important to work with your legal and compliance teams to determine if your organization needs to meet compliance standards such as HIPPA, CJIS, or GDPR. You should also work with your security group to determine the objectives for information protection for your organization and for departments or groups that require additional security.</span></span>

<span data-ttu-id="aa1f8-111">Successivamente, utilizzare i passaggi seguenti per costruire la protezione delle informazioni per Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="aa1f8-111">Next, use the following steps to build out information protection for Microsoft 365 Enterprise.</span></span>

|||
|:-------|:-----|
|![Passaggio 1](../media/stepnumbers/Step1.png)|[<span data-ttu-id="aa1f8-113">Definire i livelli di sicurezza e di protezione delle informazioni</span><span class="sxs-lookup"><span data-stu-id="aa1f8-113">Define security and information protection levels</span></span>](infoprotect-define-sec-infoprotect-levels.md)|
|![Passaggio 2](../media/stepnumbers/Step2.png)|[<span data-ttu-id="aa1f8-115">Configurare la classificazione per l'ambiente</span><span class="sxs-lookup"><span data-stu-id="aa1f8-115">Configure classification for your environment</span></span>](infoprotect-configure-classification.md)|
|![Passaggio 3](../media/stepnumbers/Step3.png)|[<span data-ttu-id="aa1f8-117">Configurare un livello di sicurezza maggiore per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="aa1f8-117">Configure increased security for Microsoft 365</span></span>](infoprotect-configure-increased-security-office-365.md)|
|![Passaggio 4](../media/stepnumbers/Step4.png)|[<span data-ttu-id="aa1f8-119">Configurare Windows Information Protection</span><span class="sxs-lookup"><span data-stu-id="aa1f8-119">Configure Windows Information Protection</span></span>](infoprotect-deploy-windows-information-protection.md)|
|![Passaggio 5](../media/stepnumbers/Step5.png)|[<span data-ttu-id="aa1f8-121">Configurare la prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="aa1f8-121">Configure Data Loss Prevention</span></span>](infoprotect-data-loss-prevention.md)|
|![Passaggio 6](../media/stepnumbers/Step6.png)|[<span data-ttu-id="aa1f8-123">Configurare la crittografia della posta elettronica</span><span class="sxs-lookup"><span data-stu-id="aa1f8-123">Configure email encryption</span></span>](infoprotect-email-encryption.md)|
|![Passaggio 7](../media/stepnumbers/Step7.png)|[<span data-ttu-id="aa1f8-125">Configurare la gestione degli accessi con privilegi per Office 365</span><span class="sxs-lookup"><span data-stu-id="aa1f8-125">Configure privileged access management for Office 365</span></span>](infoprotect-configure-privileged-access-management.md)|
|||

<span data-ttu-id="aa1f8-126">Dopo aver completato questi passaggi, passare ai [criteri uscita](infoprotect-exit-criteria.md) per questa fase per garantire che vengano rispettate le condizioni facoltative e obbligatorie per Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="aa1f8-126">When you've completed these steps, go to the [exit criteria](infoprotect-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="aa1f8-127">Come Microsoft esegue Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="aa1f8-127">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="aa1f8-128">Informazioni su come gli esperti IT di Microsoft usano [Azure Information Protection per proteggere i dati](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR9).</span><span class="sxs-lookup"><span data-stu-id="aa1f8-128">Learn how IT experts at Microsoft use [Azure Information Protection and safeguard data](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR9).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="aa1f8-129">Come ha agito Contoso con Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="aa1f8-129">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="aa1f8-130">Vedere come Contoso Corporation, un'azienda multinazionale fittizia ma rappresentativa, [ha implementato la protezione delle informazioni](contoso-info-protect.md) con i servizi cloud Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="aa1f8-130">See how the Contoso Corporation, a fictional but representative multi-national business, [implemented information protection](contoso-info-protect.md) with Microsoft 365 cloud services.</span></span>

![Contoso Corporation](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="aa1f8-132">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="aa1f8-132">Next step</span></span>

|||
|:-------|:-----|
|![Passaggio 1](../media/stepnumbers/Step1.png)|[<span data-ttu-id="aa1f8-134">Definire i livelli di sicurezza e di protezione delle informazioni</span><span class="sxs-lookup"><span data-stu-id="aa1f8-134">Define security and information protection levels</span></span>](infoprotect-define-sec-infoprotect-levels.md)|

