---
title: "Passaggio 2: configurare la classificazione dell'ambiente"
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Comprendere e configurare i diversi modi per classificare i dati all'interno dell'organizzazione.
ms.openlocfilehash: bee0885eb3f8899560532895d1558723b281ab02
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868477"
---
# <a name="step-2-configure-classification-for-your-environment"></a><span data-ttu-id="9879c-103">Passaggio 2: configurare la classificazione dell'ambiente</span><span class="sxs-lookup"><span data-stu-id="9879c-103">Step 2: Configure classification for your environment</span></span>

<span data-ttu-id="9879c-104">*Questo passaggio è facoltativo e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="9879c-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="9879c-105">In questo passaggio, si lavora con i team di conformità e legali per definire uno schema di classificazione dei dati dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9879c-105">In Step 3, you work with your legal and compliance teams to define a classification scheme for your organization’s data.</span></span>

## <a name="microsoft-classifications"></a><span data-ttu-id="9879c-106">Classificazioni Microsoft</span><span class="sxs-lookup"><span data-stu-id="9879c-106">Microsoft classifications</span></span>

<span data-ttu-id="9879c-107">Microsoft 365 include tre tipi di classificazione:</span><span class="sxs-lookup"><span data-stu-id="9879c-107">Microsoft 365 includes three types of classification:</span></span>

- <span data-ttu-id="9879c-108">Tipi di informazioni riservate di Office 365</span><span class="sxs-lookup"><span data-stu-id="9879c-108">Sensitive information types for Office 365</span></span>
- <span data-ttu-id="9879c-109">Etichette di Office 365</span><span class="sxs-lookup"><span data-stu-id="9879c-109">Office 365 labels</span></span>
- <span data-ttu-id="9879c-110">Le etichette e protezione di Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="9879c-110">Azure Information Protection labels and protection</span></span>

### <a name="sensitive-information-types-for-office-365"></a><span data-ttu-id="9879c-111">Tipi di informazioni riservate di Office 365</span><span class="sxs-lookup"><span data-stu-id="9879c-111">Sensitive information types for Office 365</span></span>

<span data-ttu-id="9879c-p101">I tipi di informazioni riservate di Office 365 definiscono in che modo i processi automatizzati come la ricerca di tipi di informazioni specifici riconosciuti quali i numeri di previdenza sociale e di carte di credito. I tipi di informazioni riservate si usano per trovare dati riservati e applicare regole e criteri per la prevenzione della perdita di dati per proteggere tali dati. Per ulteriori informazioni, vedere [Panoramica dei criteri di prevenzione della perdita dei dati](https://support.office.com/article/overview-of-data-loss-prevention-policies-1966b2a7-d1e2-4d92-ab61-42efbb137f5e). Ad esempio, i tipi di informazioni riservate sono particolarmente utili per soddisfare requisiti di conformità e normativi, come il Regolamento generale sulla protezione dei dati (GDPR).</span><span class="sxs-lookup"><span data-stu-id="9879c-p101">Sensitive information types for Office 365 define how automated processes such as search recognize specific information types such as health service numbers and credit card numbers. You use sensitive information types to find sensitive data and apply data loss prevention rules and policies to protect this data. For more information, see [Overview of data loss prevention policies](https://support.office.com/article/overview-of-data-loss-prevention-policies-1966b2a7-d1e2-4d92-ab61-42efbb137f5e). For example, sensitive information types are especially helpful for meeting compliance and regulation requirements, such as for the General Data Protection Regulation (GDPR).</span></span>

### <a name="office-365-labels"></a><span data-ttu-id="9879c-116">Etichette di Office 365</span><span class="sxs-lookup"><span data-stu-id="9879c-116">Office 365 labels</span></span>
<span data-ttu-id="9879c-p102">È possibile utilizzare le etichette di Office 365 per i dati personali e per i file con segreti commerciali soggetti a normative in SharePoint Online e OneDrive for Business. Per ulteriori informazioni, anche su come crearle, vedere [Panoramica delle etichette](https://support.office.com/article/overview-of-labels-af398293-c69d-465e-a249-d74561552d30).</span><span class="sxs-lookup"><span data-stu-id="9879c-p102">You can use Office 365 labels for personal data and for highly regulated and trade secret files stored in SharePoint Online and OneDrive for Business. For more information, including how to create them, see [Overview of labels](https://support.office.com/article/overview-of-labels-af398293-c69d-465e-a249-d74561552d30).</span></span>

<span data-ttu-id="9879c-p103">Se si decide di usare le etichette di Office 365, è necessario configurarne almeno una per ogni livello di protezione. Ad esempio, creare tre etichette per:</span><span class="sxs-lookup"><span data-stu-id="9879c-p103">If you decide to use Office 365 labels, you should configure at least one for each level of protection. For example, create three labels for:</span></span>

- <span data-ttu-id="9879c-121">Protezione di base</span><span class="sxs-lookup"><span data-stu-id="9879c-121">Baseline</span></span>
- <span data-ttu-id="9879c-122">Dati sensibili</span><span class="sxs-lookup"><span data-stu-id="9879c-122">Sensitive</span></span>
- <span data-ttu-id="9879c-123">Protezione per ambienti altamente regolamentati</span><span class="sxs-lookup"><span data-stu-id="9879c-123">Highly regulated</span></span>

### <a name="azure-information-protection-labels-and-protection"></a><span data-ttu-id="9879c-124">Le etichette e protezione di Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="9879c-124">Azure Information Protection labels and protection</span></span>

<span data-ttu-id="9879c-p104">È possibile usare le etichette di Azure Information Protection per classificare e facoltativamente proteggere documenti e messaggi di posta elettronica dell'organizzazione. Le etichette si possono applicare ai documenti archiviati all'esterno di Office 365. Le etichette possono essere applicate automaticamente dagli amministratori che definiscono le regole e condizioni, manualmente dagli utenti o in modo combinato in cui agli utenti vengono fornite indicazioni.</span><span class="sxs-lookup"><span data-stu-id="9879c-p104">You can use Azure Information Protection labels to classify, and optionally protect, your organization’s documents and emails. These labels can apply to documents that are stored outside of Office 365. These labels can be applied automatically by administrators who define rules and conditions, manually by users, or a combination where users are given recommendations.</span></span>

<span data-ttu-id="9879c-128">Per pianificare e distribuire le etichette e la protezione di Azure Information Protection, eseguire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="9879c-128">To plan and deploy Azure Information Protection labels and protection, do the following:</span></span>

1. <span data-ttu-id="9879c-129">Esaminare i [requisiti di Azure Information Protection](https://docs.microsoft.com/information-protection/get-started/requirements).</span><span class="sxs-lookup"><span data-stu-id="9879c-129">Review the [requirements for Azure Information Protection](https://docs.microsoft.com/information-protection/get-started/requirements).</span></span>
2. <span data-ttu-id="9879c-130">Seguire la [guida di orientamento per la distribuzione delle funzionalità di classificazione, assegnazione di etichette e protezione](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap#deployment-roadmap-for-classification-labeling-and-protection).</span><span class="sxs-lookup"><span data-stu-id="9879c-130">Follow the [deployment roadmap for classification, labeling, and protection](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap#deployment-roadmap-for-classification-labeling-and-protection).</span></span>

<span data-ttu-id="9879c-131">Per ulteriori informazioni, vedere la [raccolta della documentazione di Azure Information Protection](https://docs.microsoft.com/information-protection/).</span><span class="sxs-lookup"><span data-stu-id="9879c-131">For more information, see the [library of Azure Information Protection documentation](https://docs.microsoft.com/information-protection/).</span></span>

## <a name="classification-for-gdpr"></a><span data-ttu-id="9879c-132">Classificazione del GDPR</span><span class="sxs-lookup"><span data-stu-id="9879c-132">Classification for GDPR</span></span>

<span data-ttu-id="9879c-133">Per uno schema di classificazione di esempio contenente dati personali in base al GDPR, vedere [Progettare uno schema di classificazione per i dati personali](https://docs.microsoft.com/office365/enterprise/architect-a-classification-schema-for-personal-data).</span><span class="sxs-lookup"><span data-stu-id="9879c-133">For an example classification scheme that includes personal data for GDPR, see [Architect a classification schema for personal data](https://docs.microsoft.com/office365/enterprise/architect-a-classification-schema-for-personal-data).</span></span>

|||
|:-------|:-----|
|![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="9879c-135">Guida del laboratorio di testing: classificazione dei dati</span><span class="sxs-lookup"><span data-stu-id="9879c-135">Test Lab Guide: Data classification</span></span>](data-classification-microsoft-365-enterprise-dev-test-environment.md) |
|||

<span data-ttu-id="9879c-136">Come checkpoint provvisorio, vedere i [criteri uscita](infoprotect-exit-criteria.md#crit-infoprotect-step3) che corrispondono a questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="9879c-136">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step3) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="9879c-137">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="9879c-137">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)|[<span data-ttu-id="9879c-138">Configurare un livello di sicurezza maggiore per Office 365</span><span class="sxs-lookup"><span data-stu-id="9879c-138">Configure increased security for Office 365</span></span>](infoprotect-configure-increased-security-office-365.md)|

