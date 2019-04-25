---
title: "Passaggio 2: configurare la classificazione dell'ambiente"
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
description: Comprendere e configurare i diversi modi per classificare i dati all'interno dell'organizzazione.
ms.openlocfilehash: ca64b98bceb6f969adc964e93a6a1cc872763199
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32286975"
---
# <a name="step-2-configure-classification-for-your-environment"></a><span data-ttu-id="b925f-103">Passaggio 2: configurare la classificazione dell'ambiente</span><span class="sxs-lookup"><span data-stu-id="b925f-103">Step 2: Configure classification for your environment</span></span>

<span data-ttu-id="b925f-104">*Questo passaggio è facoltativo e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="b925f-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="b925f-105">In questo passaggio, si lavora con i team di conformità e legali per definire uno schema di classificazione dei dati dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b925f-105">In this step, you work with your legal and compliance teams to define a classification scheme for your organization’s data.</span></span>

## <a name="microsoft-365-classification-types"></a><span data-ttu-id="b925f-106">Tipi di classificazione Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b925f-106">Microsoft 365 classification types</span></span>

<span data-ttu-id="b925f-107">Microsoft 365 include quattro tipi di classificazione:</span><span class="sxs-lookup"><span data-stu-id="b925f-107">Microsoft 365 includes three types of classification:</span></span>

- <span data-ttu-id="b925f-108">Tipi di informazioni riservate</span><span class="sxs-lookup"><span data-stu-id="b925f-108">Sensitive information types</span></span>
- <span data-ttu-id="b925f-109">Etichette di conservazione</span><span class="sxs-lookup"><span data-stu-id="b925f-109">Retention labels</span></span>
- <span data-ttu-id="b925f-110">Etichette di riservatezza</span><span class="sxs-lookup"><span data-stu-id="b925f-110">Sensitivity labels</span></span>
- <span data-ttu-id="b925f-111">Etichette e protezione di Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="b925f-111">Azure Information Protection labels and protection</span></span>

### <a name="sensitive-information-types"></a><span data-ttu-id="b925f-112">Tipi di informazioni riservate</span><span class="sxs-lookup"><span data-stu-id="b925f-112">Sensitive information types</span></span>

<span data-ttu-id="b925f-113">I tipi di informazioni riservate per Microsoft 365 definiscono come i processi automatici, quali ad esempio la ricerca, riconoscono i tipi di informazioni specifiche.</span><span class="sxs-lookup"><span data-stu-id="b925f-113">Sensitive information types for Microsoft 365 define how automated processes such as search recognize specific information types.</span></span> <span data-ttu-id="b925f-114">Includono i dati riservati dei dipendenti o dei clienti, come ad esempio numeri del servizio sanitario e numeri di carta di credito.</span><span class="sxs-lookup"><span data-stu-id="b925f-114">These include sensitive employee or customer data such as health service numbers and credit card numbers.</span></span> <span data-ttu-id="b925f-115">Utilizzare i tipi di informazioni riservate per trovare i dati riservati e applicare regole di prevenzione della perdita di dati (DLP) e criteri per proteggere i dati.</span><span class="sxs-lookup"><span data-stu-id="b925f-115">You use sensitive information types to find sensitive data and apply data loss prevention (DLP) rules and policies to protect this data.</span></span> <span data-ttu-id="b925f-116">Per ulteriori informazioni, vedere [Contenuto di un criterio DLP](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies#what-a-dlp-policy-contains).</span><span class="sxs-lookup"><span data-stu-id="b925f-116">For more information, see [what a DLP policy contains](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies#what-a-dlp-policy-contains).</span></span> 

<span data-ttu-id="b925f-117">I tipi di informazioni riservate sono particolarmente utili per soddisfare i requisiti di conformità e delle normative, ad esempio per il GDPR (Regolamento generale sulla protezione dei dati)</span><span class="sxs-lookup"><span data-stu-id="b925f-117">Sensitive information types are especially helpful for meeting compliance and regulation requirements, such as for the General Data Protection Regulation (GDPR).</span></span>

### <a name="retention-labels"></a><span data-ttu-id="b925f-118">Etichette di conservazione</span><span class="sxs-lookup"><span data-stu-id="b925f-118">Retention labels</span></span>

<span data-ttu-id="b925f-119">Parte della definizione di una strategia di gestione dati è decidere il periodo di conservazione di specifici tipi di documenti o documenti con contenuti specifici in conformità con i criteri dell'organizzazione e le normative locali.</span><span class="sxs-lookup"><span data-stu-id="b925f-119">Part of defining a data governance strategy is deciding how long specific types of documents or documents with specific contents should be retained in compliance with organization policies and regional regulations.</span></span> <span data-ttu-id="b925f-120">Ad esempio, alcuni tipi di documento devono essere conservati per un determinato periodo di tempo e quindi eliminati e altri devono essere conservati a tempo indefinito.</span><span class="sxs-lookup"><span data-stu-id="b925f-120">For example, some types of documents should be retained for a set amount of time and then deleted and others must be retained indefinitely.</span></span>

<span data-ttu-id="b925f-121">Per i documenti archiviati in Microsoft 365, si definiscono e applicano le etichette di conservazione ai documenti e ai dati archiviati in posta elettronica di Exchange, SharePoint Online, OneDrive for Business e i messaggi di chat Teams e di canali.</span><span class="sxs-lookup"><span data-stu-id="b925f-121">For documents stored in Microsoft 365, you define and apply retention labels to documents and data stored in Exchange email, SharePoint Online, OneDrive for Business, and Teams chat and channel messages.</span></span> <span data-ttu-id="b925f-122">Per ulteriori informazioni, incluso su come crearli, vedere [Panoramica delle etichette di conservazione](https://docs.microsoft.com/office365/securitycompliance/labels).</span><span class="sxs-lookup"><span data-stu-id="b925f-122">For more information, including how to create them, see [Overview of retention labels](https://docs.microsoft.com/office365/securitycompliance/labels).</span></span>

<span data-ttu-id="b925f-123">Se si usano le etichette di conservazione, è necessario configurare un'etichetta per ogni categoria di file a cui deve essere applicato un criterio di conservazione.</span><span class="sxs-lookup"><span data-stu-id="b925f-123">If you use retention labels, you should configure a label for each category of file that needs to have a retention policy applied.</span></span> <span data-ttu-id="b925f-124">All'interno dell'etichetta di conservazione è possibile specificare:</span><span class="sxs-lookup"><span data-stu-id="b925f-124">Within the retention label, you can specify:</span></span>

- <span data-ttu-id="b925f-125">Un insieme di descrittori per i file (ad esempio, per reparto aziendale, categoria file o normative).</span><span class="sxs-lookup"><span data-stu-id="b925f-125">A set of descriptors for the files (for example, by business department, file category, or regulation).</span></span>

- <span data-ttu-id="b925f-126">Le impostazioni di conservazione per i file con l'etichetta di conservazione, ad esempio gestione tempi e comportamenti una volta raggiunto il tempo di conservazione.</span><span class="sxs-lookup"><span data-stu-id="b925f-126">The retention settings for the files that have the retention label attached, such as retain times and behaviors after the retain time has been reached.</span></span>

<span data-ttu-id="b925f-127">È anche possibile applicare un'etichetta di conservazione ai file automaticamente quando si configura un sito di SharePoint Online per applicare un'etichetta di conservazione predefinita per tutti i nuovi documenti del sito.</span><span class="sxs-lookup"><span data-stu-id="b925f-127">You can also apply a retention label to files automatically by configuring a SharePoint Online site to apply a default retention label to all new documents in the site.</span></span> 

<span data-ttu-id="b925f-128">Per altre informazioni, vedere [Panoramica delle etichette di conservazione](https://docs.microsoft.com/office365/securitycompliance/labels).</span><span class="sxs-lookup"><span data-stu-id="b925f-128">For more information, see this [overview of retention labels](https://docs.microsoft.com/office365/securitycompliance/labels).</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="b925f-129">Etichette di riservatezza</span><span class="sxs-lookup"><span data-stu-id="b925f-129">Sensitivity labels</span></span>

<span data-ttu-id="b925f-130">Parte della protezione e dell’implementazione della sicurezza per specifici tipi di documenti e documenti con contenuti specifici consiste nel contrassegnarli con un'etichetta in modo che possa essere applicata la sicurezza aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="b925f-130">Part of protecting and implementing security for specific types of documents or documents with specific contents is marking them with a label so that the additional security can be applied.</span></span> <span data-ttu-id="b925f-131">Con le etichette di riservatezza Microsoft 365 è possibile:</span><span class="sxs-lookup"><span data-stu-id="b925f-131">With sensitivity labels in Microsoft 365, you can:</span></span>

- <span data-ttu-id="b925f-132">Applicare le impostazioni di protezione, ad esempio la crittografia, le autorizzazioni o aggiungere una filigrana.</span><span class="sxs-lookup"><span data-stu-id="b925f-132">Enforce protection settings such as encryption, permissions, or adding a watermark.</span></span>

- <span data-ttu-id="b925f-133">Evitare che informazioni riservate escano dall'organizzazione nei dispositivi che eseguono Windows usando la protezione endpoint in Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="b925f-133">Prevent sensitive content from leaving your organization on devices running Windows, by using endpoint protection in Microsoft Intune.</span></span> 

- <span data-ttu-id="b925f-134">Usare la protezione di endpoint Windows Information Protection (WIP) per impedire che un contenuto venga copiato da un'applicazione di terze parti, ad esempio Twitter o Gmail, o venga copiato su supporti rimovibili, ad esempio un'unità USB.</span><span class="sxs-lookup"><span data-stu-id="b925f-134">Use Windows Information Protection (WIP) endpoint protection to prevent that content from being copied to a third-party app, such as Twitter or Gmail, or being copied to removable storage, such as a USB drive.</span></span>

- <span data-ttu-id="b925f-135">Proteggere i contenuti in app e servizi di terze parti con Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="b925f-135">Use Microsoft Cloud App Security to protect content in third-party apps and services.</span></span> 

- <span data-ttu-id="b925f-136">Classificare il contenuto senza usare nessuna impostazione di protezione.</span><span class="sxs-lookup"><span data-stu-id="b925f-136">Classify content without using any protection settings.</span></span>

<span data-ttu-id="b925f-137">Se si usano le etichette di riservatezza, è necessario configurare un'etichetta per ogni livello di protezione di sicurezza e delle informazioni.</span><span class="sxs-lookup"><span data-stu-id="b925f-137">If you use sensitivity labels, you should configure a label for each security and information protection level.</span></span> <span data-ttu-id="b925f-138">Ad esempio, creare tre etichette di riservatezza per:</span><span class="sxs-lookup"><span data-stu-id="b925f-138">For example, create three sensitivity labels for:</span></span>

- <span data-ttu-id="b925f-139">Protezione di base</span><span class="sxs-lookup"><span data-stu-id="b925f-139">Baseline</span></span>

- <span data-ttu-id="b925f-140">Dati sensibili</span><span class="sxs-lookup"><span data-stu-id="b925f-140">Sensitive</span></span>

- <span data-ttu-id="b925f-141">Protezione per ambienti altamente regolamentati</span><span class="sxs-lookup"><span data-stu-id="b925f-141">Highly regulated</span></span>

<span data-ttu-id="b925f-142">Per altre informazioni, vedere questa [Panoramica delle etichette di riservatezza](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels).</span><span class="sxs-lookup"><span data-stu-id="b925f-142">For more information, see [Overview of sensitivity labels](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels).</span></span>

### <a name="azure-information-protection-labels-and-protection"></a><span data-ttu-id="b925f-143">Le etichette e protezione di Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="b925f-143">Azure Information Protection labels and protection</span></span>

<span data-ttu-id="b925f-144">È possibile usare le etichette di Azure Information Protection per classificare, e facoltativamente proteggere, documenti e messaggi di posta elettronica dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b925f-144">You can use Azure Information Protection labels to classify, and optionally protect, your organization’s documents and emails.</span></span> <span data-ttu-id="b925f-145">Queste etichette possono essere applicate ai documenti archiviati all'esterno di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b925f-145">These labels can apply to documents that are stored outside of Microsoft 365.</span></span> <span data-ttu-id="b925f-146">Queste etichette possono essere applicate automaticamente dagli amministratori che definiscono regole e condizioni, manualmente dagli utenti oppure da entrambi, quando gli utenti ricevono raccomandazioni dagli amministratori.</span><span class="sxs-lookup"><span data-stu-id="b925f-146">This can be done automatically by administrators who define rules and conditions, manually by users, or a combination where users are given recommendations.</span></span>

<span data-ttu-id="b925f-147">Per pianificare e distribuire le etichette e la protezione di Azure Information Protection, eseguire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="b925f-147">To plan and deploy Azure Information Protection labels and protection, do the following:</span></span>

1. <span data-ttu-id="b925f-148">Esaminare i [requisiti di Azure Information Protection](https://docs.microsoft.com/information-protection/get-started/requirements).</span><span class="sxs-lookup"><span data-stu-id="b925f-148">Review the [requirements for Azure Information Protection](https://docs.microsoft.com/information-protection/get-started/requirements).</span></span>
2. <span data-ttu-id="b925f-149">Seguire la [guida di orientamento per la distribuzione delle funzionalità di classificazione, assegnazione di etichette e protezione](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap#deployment-roadmap-for-classification-labeling-and-protection).</span><span class="sxs-lookup"><span data-stu-id="b925f-149">Follow the [deployment roadmap for classification, labeling, and protection](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap#deployment-roadmap-for-classification-labeling-and-protection).</span></span>

<span data-ttu-id="b925f-150">Per ulteriori informazioni, vedere la [raccolta della documentazione di Azure Information Protection](https://docs.microsoft.com/information-protection/).</span><span class="sxs-lookup"><span data-stu-id="b925f-150">For more information, see the [library of Azure Information Protection documentation](https://docs.microsoft.com/information-protection/).</span></span>

<span data-ttu-id="b925f-151">Le etichette esistenti di Azure Information Protection collaborano facilmente con le etichette di riservatezza.</span><span class="sxs-lookup"><span data-stu-id="b925f-151">Existing Azure Information Protection labels work seamlessly with sensitivity labels.</span></span> <span data-ttu-id="b925f-152">Ad esempio, è possibile mantenere le etichette di Azure Information Protection esistenti e le etichette applicate a documenti e posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="b925f-152">For example, you can keep your existing Azure Information Protection labels and the labels that are applied to documents and email.</span></span>

<span data-ttu-id="b925f-153">Se sono presenti sia riservatezza sia le etichette di Azure Information Protection, è necessario [esegue la migrazione delle etichette di Azure Information Protection a etichette di riservatezza](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels#how-sensitivity-labels-work-with-existing-azure-information-protection-labels).</span><span class="sxs-lookup"><span data-stu-id="b925f-153">If you have both sensitivity and Azure Information Protection labels, you should [migrate your Azure Information Protection labels to sensitivity labels](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels#how-sensitivity-labels-work-with-existing-azure-information-protection-labels).</span></span>

## <a name="example-classification-for-gdpr"></a><span data-ttu-id="b925f-154">Esempio: Classificazione del GDPR</span><span class="sxs-lookup"><span data-stu-id="b925f-154">Classification for GDPR</span></span>

<span data-ttu-id="b925f-155">Per uno schema di classificazione di esempio contenente dati personali in base al GDPR, vedere [Progettare uno schema di classificazione per i dati personali](https://docs.microsoft.com/office365/enterprise/architect-a-classification-schema-for-personal-data).</span><span class="sxs-lookup"><span data-stu-id="b925f-155">For an example classification scheme that includes personal data for GDPR, see [Architect a classification schema for personal data](https://docs.microsoft.com/office365/enterprise/architect-a-classification-schema-for-personal-data).</span></span>

|||
|:-------|:-----|
|![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="b925f-157">Guida del laboratorio di testing: classificazione dei dati</span><span class="sxs-lookup"><span data-stu-id="b925f-157">Test Lab Guide: Data classification</span></span>](data-classification-microsoft-365-enterprise-dev-test-environment.md) |
|||

<span data-ttu-id="b925f-158">Come checkpoint provvisorio, vedere i [criteri uscita](infoprotect-exit-criteria.md#crit-infoprotect-step3) che corrispondono a questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="b925f-158">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step3) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="b925f-159">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="b925f-159">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)|[<span data-ttu-id="b925f-160">Configurare un livello di sicurezza maggiore per Office 365</span><span class="sxs-lookup"><span data-stu-id="b925f-160">Configure increased security for Office 365</span></span>](infoprotect-configure-increased-security-office-365.md)|

