---
title: "Passaggio 2: configurare la classificazione dell'ambiente"
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
description: Comprendere e configurare i diversi modi per classificare i dati all'interno dell'organizzazione.
ms.openlocfilehash: 5323e4f682e8a530601308877423502f64878a4c
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "33400090"
---
# <a name="step-2-configure-classification-for-your-environment"></a><span data-ttu-id="843c2-103">Passaggio 2: configurare la classificazione dell'ambiente</span><span class="sxs-lookup"><span data-stu-id="843c2-103">Step 2: Configure classification for your environment</span></span>

<span data-ttu-id="843c2-104">*Questo passaggio è facoltativo e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="843c2-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="843c2-105">In questo passaggio, si lavora con i team di conformità e legali per definire uno schema di classificazione dei dati dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="843c2-105">In this step, you work with your legal and compliance teams to define a classification scheme for your organization’s data.</span></span>

## <a name="microsoft-365-classification-types"></a><span data-ttu-id="843c2-106">Tipi di classificazione Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="843c2-106">Microsoft 365 classification types</span></span>

<span data-ttu-id="843c2-107">Microsoft 365 include quattro tipi di classificazione:</span><span class="sxs-lookup"><span data-stu-id="843c2-107">Microsoft 365 includes four types of classification:</span></span>

- <span data-ttu-id="843c2-108">Tipi di informazioni riservate</span><span class="sxs-lookup"><span data-stu-id="843c2-108">Sensitive information types</span></span>
- <span data-ttu-id="843c2-109">Etichette di conservazione</span><span class="sxs-lookup"><span data-stu-id="843c2-109">Retention labels</span></span>
- <span data-ttu-id="843c2-110">Etichette di riservatezza</span><span class="sxs-lookup"><span data-stu-id="843c2-110">Sensitivity labels</span></span>
- <span data-ttu-id="843c2-111">Etichette e protezione di Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="843c2-111">Azure Information Protection labels and protection</span></span>

### <a name="sensitive-information-types"></a><span data-ttu-id="843c2-112">Tipi di informazioni riservate</span><span class="sxs-lookup"><span data-stu-id="843c2-112">Sensitive information types</span></span>

<span data-ttu-id="843c2-113">I tipi di informazioni riservate per Microsoft 365 definiscono come i processi automatici, quali ad esempio la ricerca, riconoscono i tipi di informazioni specifiche.</span><span class="sxs-lookup"><span data-stu-id="843c2-113">Sensitive information types for Microsoft 365 define how automated processes such as search recognize specific information types.</span></span> <span data-ttu-id="843c2-114">Includono i dati riservati dei dipendenti o dei clienti, come ad esempio numeri del servizio sanitario e numeri di carta di credito.</span><span class="sxs-lookup"><span data-stu-id="843c2-114">These include sensitive employee or customer data such as health service numbers and credit card numbers.</span></span> <span data-ttu-id="843c2-115">Utilizzare i tipi di informazioni riservate per trovare i dati riservati e applicare regole di prevenzione della perdita di dati (DLP) e criteri per proteggere i dati.</span><span class="sxs-lookup"><span data-stu-id="843c2-115">You use sensitive information types to find sensitive data and apply data loss prevention (DLP) rules and policies to protect this data.</span></span> <span data-ttu-id="843c2-116">Per ulteriori informazioni, vedere [Contenuto di un criterio DLP](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies#what-a-dlp-policy-contains).</span><span class="sxs-lookup"><span data-stu-id="843c2-116">For more information, see [what a DLP policy contains](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies#what-a-dlp-policy-contains).</span></span> 

<span data-ttu-id="843c2-117">I tipi di informazioni riservate sono particolarmente utili per soddisfare i requisiti di conformità e delle normative, ad esempio per il GDPR (Regolamento generale sulla protezione dei dati)</span><span class="sxs-lookup"><span data-stu-id="843c2-117">Sensitive information types are especially helpful for meeting compliance and regulation requirements, such as for the General Data Protection Regulation (GDPR).</span></span>

### <a name="retention-labels"></a><span data-ttu-id="843c2-118">Etichette di conservazione</span><span class="sxs-lookup"><span data-stu-id="843c2-118">Retention labels</span></span>

<span data-ttu-id="843c2-119">Parte della definizione di una strategia di gestione dati è decidere il periodo di conservazione di specifici tipi di documenti o documenti con contenuti specifici in conformità con i criteri dell'organizzazione e le normative locali.</span><span class="sxs-lookup"><span data-stu-id="843c2-119">Part of defining a data governance strategy is deciding how long specific types of documents or documents with specific contents should be retained in compliance with organization policies and regional regulations.</span></span> <span data-ttu-id="843c2-120">Ad esempio, alcuni tipi di documento devono essere conservati per un determinato periodo di tempo e quindi eliminati e altri devono essere conservati a tempo indefinito.</span><span class="sxs-lookup"><span data-stu-id="843c2-120">For example, some types of documents should be retained for a set amount of time and then deleted and others must be retained indefinitely.</span></span>

<span data-ttu-id="843c2-121">Per i documenti archiviati in Microsoft 365, si definiscono e applicano le etichette di conservazione ai documenti e ai dati archiviati in posta elettronica di Exchange, SharePoint Online, OneDrive for Business e i messaggi di chat Teams e di canali.</span><span class="sxs-lookup"><span data-stu-id="843c2-121">For documents stored in Microsoft 365, you define and apply retention labels to documents and data stored in Exchange email, SharePoint Online, OneDrive for Business, and Teams chat and channel messages.</span></span> 

<span data-ttu-id="843c2-122">Se si usano le etichette di conservazione, è necessario configurare un'etichetta per ogni categoria di file a cui deve essere applicato un criterio di conservazione.</span><span class="sxs-lookup"><span data-stu-id="843c2-122">If you use retention labels, you should configure a label for each category of file that needs to have a retention policy applied.</span></span> <span data-ttu-id="843c2-123">All'interno dell'etichetta di conservazione è possibile specificare:</span><span class="sxs-lookup"><span data-stu-id="843c2-123">Within the retention label, you can specify:</span></span>

- <span data-ttu-id="843c2-124">Un insieme di descrittori per i file (ad esempio, per reparto aziendale, categoria file o normative).</span><span class="sxs-lookup"><span data-stu-id="843c2-124">A set of descriptors for the files (for example, by business department, file category, or regulation).</span></span>
- <span data-ttu-id="843c2-125">Le impostazioni di conservazione per i file con l'etichetta di conservazione, ad esempio gestione tempi e comportamenti una volta raggiunto il tempo di conservazione.</span><span class="sxs-lookup"><span data-stu-id="843c2-125">The retention settings for the files that have the retention label attached, such as retain times and behaviors after the retain time has been reached.</span></span>

<span data-ttu-id="843c2-126">È anche possibile applicare un'etichetta di conservazione ai file automaticamente quando si configura un sito di SharePoint Online per applicare un'etichetta di conservazione predefinita per tutti i nuovi documenti del sito.</span><span class="sxs-lookup"><span data-stu-id="843c2-126">You can also apply a retention label to files automatically by configuring a SharePoint Online site to apply a default retention label to all new documents in the site.</span></span> 

<span data-ttu-id="843c2-127">Per ulteriori informazioni, vedere la [Panoramica delle etichette di conservazione](https://docs.microsoft.com/office365/securitycompliance/labels).</span><span class="sxs-lookup"><span data-stu-id="843c2-127">For more information, see this [overview of retention labels](https://docs.microsoft.com/office365/securitycompliance/labels).</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="843c2-128">Etichette di riservatezza</span><span class="sxs-lookup"><span data-stu-id="843c2-128">Sensitivity labels</span></span>

<span data-ttu-id="843c2-129">Parte della protezione e dell’implementazione della sicurezza per specifici tipi di documenti e documenti con contenuti specifici consiste nel contrassegnarli con un'etichetta in modo che possa essere applicata la sicurezza aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="843c2-129">Part of protecting and implementing security for specific types of documents or documents with specific contents is marking them with a label so that the additional security can be applied.</span></span> <span data-ttu-id="843c2-130">Con le etichette di riservatezza Microsoft 365 è possibile:</span><span class="sxs-lookup"><span data-stu-id="843c2-130">With sensitivity labels in Microsoft 365, you can:</span></span>

- <span data-ttu-id="843c2-131">Applicare le impostazioni di protezione, ad esempio la crittografia, le autorizzazioni o aggiungere una filigrana.</span><span class="sxs-lookup"><span data-stu-id="843c2-131">Enforce protection settings such as encryption, permissions, or adding a watermark.</span></span>
- <span data-ttu-id="843c2-132">Evitare che informazioni riservate escano dall'organizzazione nei dispositivi che eseguono Windows usando la protezione endpoint in Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="843c2-132">Prevent sensitive content from leaving your organization on devices running Windows, by using endpoint protection in Microsoft Intune.</span></span> 
- <span data-ttu-id="843c2-133">Usare la protezione di endpoint Windows Information Protection (WIP) per impedire che un contenuto venga copiato da un'applicazione di terze parti, ad esempio Twitter o Gmail, o venga copiato su supporti rimovibili, ad esempio un'unità USB.</span><span class="sxs-lookup"><span data-stu-id="843c2-133">Use Windows Information Protection (WIP) endpoint protection to prevent that content from being copied to a third-party app, such as Twitter or Gmail, or being copied to removable storage, such as a USB drive.</span></span>
- <span data-ttu-id="843c2-134">Proteggere i contenuti in app e servizi di terze parti con Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="843c2-134">Use Microsoft Cloud App Security to protect content in third-party apps and services.</span></span> 
- <span data-ttu-id="843c2-135">Classificare il contenuto senza usare nessuna impostazione di protezione.</span><span class="sxs-lookup"><span data-stu-id="843c2-135">Classify content without using any protection settings.</span></span>

<span data-ttu-id="843c2-136">Se si usano le etichette di riservatezza, è necessario configurare un'etichetta per ogni livello di protezione di sicurezza e delle informazioni.</span><span class="sxs-lookup"><span data-stu-id="843c2-136">If you use sensitivity labels, you should configure a label for each security and information protection level.</span></span> <span data-ttu-id="843c2-137">Ad esempio, creare tre etichette di riservatezza per:</span><span class="sxs-lookup"><span data-stu-id="843c2-137">For example, create three sensitivity labels for:</span></span>

- <span data-ttu-id="843c2-138">Protezione di base</span><span class="sxs-lookup"><span data-stu-id="843c2-138">Baseline</span></span>
- <span data-ttu-id="843c2-139">Dati sensibili</span><span class="sxs-lookup"><span data-stu-id="843c2-139">Sensitive</span></span>
- <span data-ttu-id="843c2-140">Protezione per ambienti altamente regolamentati</span><span class="sxs-lookup"><span data-stu-id="843c2-140">Highly regulated</span></span>

<span data-ttu-id="843c2-141">Per altre informazioni, vedere questa [Panoramica delle etichette di riservatezza](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels).</span><span class="sxs-lookup"><span data-stu-id="843c2-141">For more information, see this [overview of sensitivity labels](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels).</span></span>

### <a name="azure-information-protection-labels-and-protection"></a><span data-ttu-id="843c2-142">Le etichette e protezione di Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="843c2-142">Azure Information Protection labels and protection</span></span>

<span data-ttu-id="843c2-143">È possibile usare le etichette di Azure Information Protection per classificare, e facoltativamente proteggere, documenti e messaggi di posta elettronica dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="843c2-143">You can use Azure Information Protection labels to classify, and optionally protect, your organization’s documents and emails.</span></span> <span data-ttu-id="843c2-144">Queste etichette possono essere applicate ai documenti archiviati all'esterno di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="843c2-144">These labels can apply to documents that are stored outside of Microsoft 365.</span></span> <span data-ttu-id="843c2-145">Queste etichette possono essere applicate automaticamente dagli amministratori che definiscono regole e condizioni, manualmente dagli utenti oppure da entrambi, quando gli utenti ricevono raccomandazioni dagli amministratori.</span><span class="sxs-lookup"><span data-stu-id="843c2-145">These labels can be applied automatically by administrators who define rules and conditions, manually by users, or a combination where users are given recommendations.</span></span>

<span data-ttu-id="843c2-146">Per pianificare e distribuire le etichette e la protezione di Azure Information Protection, eseguire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="843c2-146">To plan and deploy Azure Information Protection labels and protection, do the following:</span></span>

1. <span data-ttu-id="843c2-147">Esaminare i [requisiti di Azure Information Protection](https://docs.microsoft.com/information-protection/get-started/requirements).</span><span class="sxs-lookup"><span data-stu-id="843c2-147">Review the [requirements for Azure Information Protection](https://docs.microsoft.com/information-protection/get-started/requirements).</span></span>
2. <span data-ttu-id="843c2-148">Seguire la [guida di orientamento per la distribuzione delle funzionalità di classificazione, assegnazione di etichette e protezione](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap#deployment-roadmap-for-classification-labeling-and-protection).</span><span class="sxs-lookup"><span data-stu-id="843c2-148">Follow the [deployment roadmap for classification, labeling, and protection](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap#deployment-roadmap-for-classification-labeling-and-protection).</span></span>

<span data-ttu-id="843c2-149">Per ulteriori informazioni, vedere la [raccolta della documentazione di Azure Information Protection](https://docs.microsoft.com/information-protection/).</span><span class="sxs-lookup"><span data-stu-id="843c2-149">For more information, see the [library of Azure Information Protection documentation](https://docs.microsoft.com/information-protection/).</span></span>

<span data-ttu-id="843c2-150">Le etichette esistenti di Azure Information Protection collaborano facilmente con le etichette di riservatezza.</span><span class="sxs-lookup"><span data-stu-id="843c2-150">Existing Azure Information Protection labels work seamlessly with sensitivity labels.</span></span> <span data-ttu-id="843c2-151">Ad esempio, è possibile mantenere le etichette di Azure Information Protection esistenti e le etichette applicate a documenti e posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="843c2-151">For example, you can keep your existing Azure Information Protection labels and the labels that are applied to documents and email.</span></span>

<span data-ttu-id="843c2-152">Se sono presenti sia riservatezza sia le etichette di Azure Information Protection, è necessario [esegue la migrazione delle etichette di Azure Information Protection a etichette di riservatezza](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels#how-sensitivity-labels-work-with-existing-azure-information-protection-labels).</span><span class="sxs-lookup"><span data-stu-id="843c2-152">If you have both sensitivity and Azure Information Protection labels, you should [migrate your Azure Information Protection labels to sensitivity labels](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels#how-sensitivity-labels-work-with-existing-azure-information-protection-labels).</span></span>

## <a name="example-classification-for-gdpr"></a><span data-ttu-id="843c2-153">Esempio: Classificazione del GDPR</span><span class="sxs-lookup"><span data-stu-id="843c2-153">Example: Classification for GDPR</span></span>

<span data-ttu-id="843c2-154">Per uno schema di classificazione di esempio contenente dati personali in base al GDPR, vedere [Progettare uno schema di classificazione per i dati personali](https://docs.microsoft.com/office365/enterprise/architect-a-classification-schema-for-personal-data).</span><span class="sxs-lookup"><span data-stu-id="843c2-154">For an example classification scheme that includes personal data for GDPR, see [Architect a classification schema for personal data](https://docs.microsoft.com/office365/enterprise/architect-a-classification-schema-for-personal-data).</span></span>

## <a name="take-it-for-a-test-drive"></a><span data-ttu-id="843c2-155">Va inteso come un test drive</span><span class="sxs-lookup"><span data-stu-id="843c2-155">Take it for a test drive</span></span>

|||
|:-------|:-----|
|![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="843c2-157">Guida del laboratorio di testing: classificazione dei dati</span><span class="sxs-lookup"><span data-stu-id="843c2-157">Test Lab Guide: Data classification</span></span>](data-classification-microsoft-365-enterprise-dev-test-environment.md) |
|||

<span data-ttu-id="843c2-158">Come checkpoint provvisorio, vedere i [criteri uscita](infoprotect-exit-criteria.md#crit-infoprotect-step2) che corrispondono a questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="843c2-158">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step2) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="843c2-159">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="843c2-159">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)|[<span data-ttu-id="843c2-160">Configurare un livello di sicurezza maggiore per Office 365</span><span class="sxs-lookup"><span data-stu-id="843c2-160">Configure increased security for Office 365</span></span>](infoprotect-configure-increased-security-office-365.md)|

