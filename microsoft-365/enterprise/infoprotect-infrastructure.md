---
title: 'Fase 6: protezione delle informazioni'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/01/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: I passaggi per distribuire l'infrastruttura di protezione delle informazioni per Microsoft 365 Enterprise.
ms.openlocfilehash: a0d2c485b05e0969fe45cfd79c86e4e7dcb1d5ff
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "33400000"
---
# <a name="phase-6-information-protection"></a><span data-ttu-id="532f5-103">Fase 6: protezione delle informazioni</span><span class="sxs-lookup"><span data-stu-id="532f5-103">Phase 6: Information protection</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon.png)

<span data-ttu-id="532f5-p101">La protezione delle informazioni è un set di criteri e tecnologie che definiscono la modalità di trasmissione, archiviazione ed elaborazione delle informazioni riservate. Durante la Fase 6, è possibile esaminare le impostazioni di protezione delle informazioni e le funzionalità di Microsoft 365 Enterprise che consentono di proteggere i dati per i carichi di lavoro e gli scenari basati sul cloud.</span><span class="sxs-lookup"><span data-stu-id="532f5-p101">Information protection is a set of policies and technologies that define how you transmit, store, and process sensitive information. In Phase 6, you step through information protection settings and features of Microsoft 365 Enterprise that help you secure data for your cloud-based workloads and scenarios.</span></span>

>[!Note]
><span data-ttu-id="532f5-106">Se è stata già impostata la protezione delle informazioni, vedere i [criteri uscita](infoprotect-exit-criteria.md) per questa fase per assicurarsi che soddisfino le condizioni facoltative e obbligatorie per Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="532f5-106">If you already have already deployed information protection, please see the [exit criteria](infoprotect-exit-criteria.md) for this phase to make sure that it meets the required and optional conditions for Microsoft 365 Enterprise.</span></span>
>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-information-protection-infrastructure"></a><span data-ttu-id="532f5-107">Pianificare e distribuire l'infrastruttura di protezione delle informazioni di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="532f5-107">Plan and deploy your Microsoft 365 Enterprise information protection infrastructure</span></span> 

<span data-ttu-id="532f5-p102">È importante lavorare insieme al team legale e a quello di conformità per determinare se i bisogni dell'organizzazione soddisfino gli standard di conformità come HIPAA, CJIS e RGPD. È anche consigliabile collaborare con il gruppo di sicurezza per determinare gli obiettivi per la protezione delle informazioni per l'organizzazione e per i reparti o i gruppi che richiedono una maggiore protezione.</span><span class="sxs-lookup"><span data-stu-id="532f5-p102">It’s important to work with your legal and compliance teams to determine if your organization needs to meet compliance standards such as HIPPA, CJIS, or GDPR. You should also work with your security group to determine the objectives for information protection for your organization and for departments or groups that require additional security.</span></span>

<span data-ttu-id="532f5-110">Successivamente, utilizzare i passaggi seguenti per costruire la protezione delle informazioni per Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="532f5-110">Next, use the following steps to build out information protection for Microsoft 365 Enterprise.</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)|[<span data-ttu-id="532f5-111">Definire i livelli di sicurezza e di protezione delle informazioni</span><span class="sxs-lookup"><span data-stu-id="532f5-111">Define security and information protection levels</span></span>](infoprotect-define-sec-infoprotect-levels.md)|
|![](./media/stepnumbers/Step2.png)|[<span data-ttu-id="532f5-112">Configurare la classificazione dell'ambiente</span><span class="sxs-lookup"><span data-stu-id="532f5-112">Configure classification for your environment</span></span>](infoprotect-configure-classification.md)|
|![](./media/stepnumbers/Step3.png)|[<span data-ttu-id="532f5-113">Configurare un livello di sicurezza maggiore per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="532f5-113">Configure increased security for Microsoft 365</span></span>](infoprotect-configure-increased-security-office-365.md)|
|![](./media/stepnumbers/Step4.png)|<span data-ttu-id="532f5-114">[Configurare Windows Information Protection](infoprotect-deploy-windows-information-protection.md)</span><span class="sxs-lookup"><span data-stu-id="532f5-114">[](infoprotect-deploy-windows-information-protection.md)Configure Azure Information Protection</span></span>|
|![](./media/stepnumbers/Step5.png)|[<span data-ttu-id="532f5-115">Configurare i criteri di prevenzione della perdita dei dati di Office 365</span><span class="sxs-lookup"><span data-stu-id="532f5-115">Office 365 Data Loss Prevention (DLP)</span></span>](infoprotect-data-loss-prevention.md)|
|![](./media/stepnumbers/Step6.png)|[<span data-ttu-id="532f5-116">Configurare la gestione degli accessi con privilegi per Office 365</span><span class="sxs-lookup"><span data-stu-id="532f5-116">Configure privileged access management for Office 365</span></span>](infoprotect-configure-privileged-access-management.md)|


<span data-ttu-id="532f5-117">Dopo aver completato questi passaggi, passare ai [criteri uscita](infoprotect-exit-criteria.md) per questa fase per garantire che vengano rispettate le condizioni facoltative e obbligatorie per Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="532f5-117">When you've completed these steps, go to the [exit criteria](infoprotect-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="532f5-118">Come Microsoft esegue Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="532f5-118">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="532f5-119">Ulteriori informazioni su come gli esperti IT di Microsoft utilizzano le funzionalità di protezione delle informazioni di Microsoft 356 Enterprise per proteggere le informazioni e difendersi dagli attacchi informatici:</span><span class="sxs-lookup"><span data-stu-id="532f5-119">Learn how IT experts at Microsoft use the information protection capabilities of Microsoft 356 Enterprise to protect information and defend against cyber attacks:</span></span>

- [<span data-ttu-id="532f5-120">Protezione dei file nel cloud con Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="532f5-120">Protecting files in the cloud with Azure Information Protection</span></span>](https://www.microsoft.com/itshowcase/Article/Content/924/Protecting-files-in-the-cloud-with-Azure-Information-Protection)
- [<span data-ttu-id="532f5-121">Microsoft utilizza l'intelligence per le minacce per proteggere, rilevare e rispondere alle minacce</span><span class="sxs-lookup"><span data-stu-id="532f5-121">Microsoft uses threat intelligence to protect, detect, and respond to threats</span></span>](https://www.microsoft.com/itshowcase/Article/Content/934/Microsoft-uses-threat-intelligence-to-protect-detect-and-respond-to-threats)
- [<span data-ttu-id="532f5-122">Microsoft contrasta i tentativi di phishing con Office 365</span><span class="sxs-lookup"><span data-stu-id="532f5-122">Microsoft thwarts phishing attempts with Office 365</span></span>](https://www.microsoft.com/itshowcase/Article/Content/956/Microsoft-thwarts-phishing-attempts-with-Office-365)

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="532f5-123">Come ha agito Contoso con Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="532f5-123">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="532f5-124">Vedere come Contoso Corporation, un'azienda multinazionale fittizia ma rappresentativa, [ha implementato la protezione delle informazioni](contoso-info-protect.md) con i servizi cloud Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="532f5-124">See how the Contoso Corporation, a fictional but representative multi-national business, [implemented information protection](contoso-info-protect.md) with Microsoft 365 cloud services.</span></span>

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="532f5-125">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="532f5-125">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)|[<span data-ttu-id="532f5-126">Definire i livelli di sicurezza e di protezione delle informazioni</span><span class="sxs-lookup"><span data-stu-id="532f5-126">Define security and information protection levels</span></span>](infoprotect-define-sec-infoprotect-levels.md)|

