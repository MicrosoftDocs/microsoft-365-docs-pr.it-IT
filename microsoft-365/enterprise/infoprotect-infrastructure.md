---
title: 'Fase 6: protezione delle informazioni'
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
ms.openlocfilehash: 3174790d1ee6c9ed05605dd1c3c75405e3eac42b
ms.sourcegitcommit: 63e35b846d964dde5919a08c2fe432e749e8eff6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/19/2019
ms.locfileid: "37047309"
---
# <a name="phase-6-information-protection"></a><span data-ttu-id="3f2f8-103">Fase 6: protezione delle informazioni</span><span class="sxs-lookup"><span data-stu-id="3f2f8-103">Phase 6: Information protection</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon.png)

<span data-ttu-id="3f2f8-p101">La protezione delle informazioni è un set di criteri e tecnologie che definiscono la modalità di trasmissione, archiviazione ed elaborazione delle informazioni riservate. Durante la Fase 6, è possibile esaminare le impostazioni di protezione delle informazioni e le funzionalità di Microsoft 365 Enterprise che consentono di proteggere i dati per i carichi di lavoro e gli scenari basati sul cloud.</span><span class="sxs-lookup"><span data-stu-id="3f2f8-p101">Information protection is a set of policies and technologies that define how you transmit, store, and process sensitive information. In Phase 6, you step through information protection settings and features of Microsoft 365 Enterprise that help you secure data for your cloud-based workloads and scenarios.</span></span>

>[!Note]
><span data-ttu-id="3f2f8-106">Se è stata già impostata la protezione delle informazioni, vedere i [criteri uscita](infoprotect-exit-criteria.md) per questa fase per assicurarsi che soddisfino le condizioni facoltative e obbligatorie per Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="3f2f8-106">If you already have already deployed information protection, please see the [exit criteria](infoprotect-exit-criteria.md) for this phase to make sure that it meets the required and optional conditions for Microsoft 365 Enterprise.</span></span>
>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-information-protection-infrastructure"></a><span data-ttu-id="3f2f8-107">Pianificare e distribuire l'infrastruttura di protezione delle informazioni di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="3f2f8-107">Plan and deploy your Microsoft 365 Enterprise information protection infrastructure</span></span> 

<span data-ttu-id="3f2f8-p102">È importante lavorare insieme al team legale e a quello di conformità per determinare se i bisogni dell'organizzazione soddisfino gli standard di conformità come HIPAA, CJIS e RGPD. È anche consigliabile collaborare con il gruppo di sicurezza per determinare gli obiettivi per la protezione delle informazioni per l'organizzazione e per i reparti o i gruppi che richiedono una maggiore protezione.</span><span class="sxs-lookup"><span data-stu-id="3f2f8-p102">It’s important to work with your legal and compliance teams to determine if your organization needs to meet compliance standards such as HIPPA, CJIS, or GDPR. You should also work with your security group to determine the objectives for information protection for your organization and for departments or groups that require additional security.</span></span>

<span data-ttu-id="3f2f8-110">Successivamente, utilizzare i passaggi seguenti per costruire la protezione delle informazioni per Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="3f2f8-110">Next, use the following steps to build out information protection for Microsoft 365 Enterprise.</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)|[<span data-ttu-id="3f2f8-111">Definire i livelli di sicurezza e di protezione delle informazioni</span><span class="sxs-lookup"><span data-stu-id="3f2f8-111">Define security and information protection levels</span></span>](infoprotect-define-sec-infoprotect-levels.md)|
|![](./media/stepnumbers/Step2.png)|[<span data-ttu-id="3f2f8-112">Configurare la classificazione dell'ambiente</span><span class="sxs-lookup"><span data-stu-id="3f2f8-112">Configure classification for your environment</span></span>](infoprotect-configure-classification.md)|
|![](./media/stepnumbers/Step3.png)|[<span data-ttu-id="3f2f8-113">Configurare un livello di sicurezza maggiore per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3f2f8-113">Configure increased security for Microsoft 365</span></span>](infoprotect-configure-increased-security-office-365.md)|
|![](./media/stepnumbers/Step4.png)|[<span data-ttu-id="3f2f8-114">Configurare Windows Information Protection</span><span class="sxs-lookup"><span data-stu-id="3f2f8-114">Configure Windows Information Protection</span></span>](infoprotect-deploy-windows-information-protection.md)|
|![](./media/stepnumbers/Step5.png)|[<span data-ttu-id="3f2f8-115">Configurare i criteri di prevenzione della perdita dei dati di Office 365</span><span class="sxs-lookup"><span data-stu-id="3f2f8-115">Configure Office 365 Data Loss Prevention</span></span>](infoprotect-data-loss-prevention.md)|
|![](./media/stepnumbers/Step6.png)|[<span data-ttu-id="3f2f8-116">Configurare la crittografia della posta elettronica</span><span class="sxs-lookup"><span data-stu-id="3f2f8-116">Configure email encryption</span></span>](infoprotect-email-encryption.md)|
|![](./media/stepnumbers/Step7.png)|[<span data-ttu-id="3f2f8-117">Configurare la gestione degli accessi con privilegi per Office 365</span><span class="sxs-lookup"><span data-stu-id="3f2f8-117">Configure privileged access management for Office 365</span></span>](infoprotect-configure-privileged-access-management.md)|
|||

<span data-ttu-id="3f2f8-118">Dopo aver completato questi passaggi, passare ai [criteri uscita](infoprotect-exit-criteria.md) per questa fase per garantire che vengano rispettate le condizioni facoltative e obbligatorie per Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="3f2f8-118">When you've completed these steps, go to the [exit criteria](infoprotect-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="3f2f8-119">Come Microsoft esegue Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="3f2f8-119">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="3f2f8-120">Informazioni su come gli esperti IT di Microsoft usano [Azure Information Protection per proteggere i dati](https://www.microsoft.com/it-IT/itshowcase/deploying-and-managing-microsoft-365#primaryR9).</span><span class="sxs-lookup"><span data-stu-id="3f2f8-120">Learn how IT experts at Microsoft use [Azure Information Protection and safeguard data](https://www.microsoft.com/it-IT/itshowcase/deploying-and-managing-microsoft-365#primaryR9).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="3f2f8-121">Come ha agito Contoso con Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="3f2f8-121">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="3f2f8-122">Vedere come Contoso Corporation, un'azienda multinazionale fittizia ma rappresentativa, [ha implementato la protezione delle informazioni](contoso-info-protect.md) con i servizi cloud Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3f2f8-122">See how the Contoso Corporation, a fictional but representative multi-national business, [implemented information protection](contoso-info-protect.md) with Microsoft 365 cloud services.</span></span>

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="3f2f8-123">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="3f2f8-123">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)|[<span data-ttu-id="3f2f8-124">Definire i livelli di sicurezza e di protezione delle informazioni</span><span class="sxs-lookup"><span data-stu-id="3f2f8-124">Define security and information protection levels</span></span>](infoprotect-define-sec-infoprotect-levels.md)|

