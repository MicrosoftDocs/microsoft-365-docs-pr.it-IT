---
title: 'Passaggio 5: Configurare i criteri di prevenzione della perdita dei dati di Office 365'
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
description: Comprendere e distribuire i criteri di prevenzione della perdita dei dati di Office 365 in Microsoft 365.
ms.openlocfilehash: d0a8beae3797e59eb1eb130afb9fd123be57d909
ms.sourcegitcommit: 9d4319a015e493fb88c7e1855bca0121654eb39d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/25/2019
ms.locfileid: "33308349"
---
# <a name="step-5-configure-office-365-data-loss-prevention"></a><span data-ttu-id="8fc94-103">Passaggio 5: Configurare i criteri di prevenzione della perdita dei dati di Office 365</span><span class="sxs-lookup"><span data-stu-id="8fc94-103">Step 5: Configure Office 365 Data Loss Prevention</span></span>

<span data-ttu-id="8fc94-104">*Questo passaggio è facoltativo e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="8fc94-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="8fc94-105">I criteri di prevenzione della perdita dei dati (DLP) del Centro sicurezza e conformità di Office 365 permettono di identificare, monitorare e proteggere automaticamente le informazioni riservate in tutto Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8fc94-105">Protection of personal information in Office 365 includes using data loss prevention capabilities. With data loss prevention (DLP) policies in the Office 365 Security & Compliance Center, you can identify, monitor, and automatically protect sensitive information across Office 365.</span></span> <span data-ttu-id="8fc94-106">Con i criteri di prevenzione della perdita dei dati, è possibile:</span><span class="sxs-lookup"><span data-stu-id="8fc94-106">With DLP, you can:</span></span>

- <span data-ttu-id="8fc94-107">Identificare le informazioni riservate in numerose posizioni, ad esempio Exchange Online, SharePoint Online e OneDrive for Business e Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8fc94-107">	Identify sensitive information across many locations, such as SharePoint Online and OneDrive for Business.</span></span>
- <span data-ttu-id="8fc94-108">Impedire la condivisione accidentale di informazioni riservate bloccando l'accesso a un documento o alla posta elettronica che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="8fc94-108">Prevent the accidental sharing of sensitive information by blocking access to a document or blocking the email that contains it.</span></span>
- <span data-ttu-id="8fc94-109">Monitorare e proteggere le informazioni riservate nelle versioni desktop di Excel, PowerPoint e Word.</span><span class="sxs-lookup"><span data-stu-id="8fc94-109">Monitor and protect sensitive information in the desktop versions of Excel 2016, PowerPoint 2016, and Word 2016.</span></span>
- <span data-ttu-id="8fc94-110">Fornire agli utenti informazioni su come garantire la conformità senza interrompere il flusso di lavoro con notifiche di posta elettronica e suggerimenti per i criteri.</span><span class="sxs-lookup"><span data-stu-id="8fc94-110">Help users learn how to stay compliant without interrupting their workflow with email notifications and policy tips.</span></span> 
- <span data-ttu-id="8fc94-111">Visualizzare report DLP che indicano i contenuti corrispondenti ai criteri DLP dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8fc94-111">View DLP reports showing content that matches your organization’s DLP policies.</span></span>

<span data-ttu-id="8fc94-112">Un criterio DLP consente di specificare:</span><span class="sxs-lookup"><span data-stu-id="8fc94-112">A DLP policy specifies:</span></span>

- <span data-ttu-id="8fc94-113">**Dove:** Posizioni come ad esempio siti di Exchange Online, SharePoint Online e OneDrive for Business, ma anche chat e canali di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8fc94-113">**Where:** Locations such as Exchange Online, SharePoint Online, and OneDrive for Business sites, as well as Microsoft Teams chats and channels.</span></span>
- <span data-ttu-id="8fc94-114">**Quando:** Condizioni che il contenuto deve soddisfare all'interno di una specifica regola dei criteri.</span><span class="sxs-lookup"><span data-stu-id="8fc94-114">**When:** Conditions the content must match within a specific policy rule.</span></span>
- <span data-ttu-id="8fc94-115">**Come:** Azioni da eseguire automaticamente nell’ambito di tale regola dei criteri per soddisfare tali condizioni.</span><span class="sxs-lookup"><span data-stu-id="8fc94-115">**How:** Actions within that matching policy rule to take automatically for the matching conditions.</span></span>

<span data-ttu-id="8fc94-116">In altre parole:</span><span class="sxs-lookup"><span data-stu-id="8fc94-116">In other words:</span></span>

- <span data-ttu-id="8fc94-117">Per un documento in questa posizione (dove), se il contenuto soddisfa le condizioni di una regola (quando), esegue automaticamente le azioni specificate in tale regola (come).</span><span class="sxs-lookup"><span data-stu-id="8fc94-117">For a document in this location (where), if the content matches the conditions of a rule (when), then automatically take the actions specified in the rule (how).</span></span>

<span data-ttu-id="8fc94-118">Per determinare il set di criteri DLP di cui si ha bisogno, è necessario analizzare i documenti e i tipi di dati che necessitano di protezione dalla perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="8fc94-118">To determine the set of DLP policies you need, you must analyze your documents and the types of data within them that need protection from data loss.</span></span> <span data-ttu-id="8fc94-119">Ad esempio, se si possiede un'organizzazione finanziaria negli Stati Uniti d'America, sarà necessario creare un criterio DLP che impedisca la condivisione esterna all'organizzazione di documenti con i numeri di previdenza sociale o l’invio tramite posta elettronica a posizioni esterne all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8fc94-119">For example, if you are a financial organization in the United States of America, you would create a DLP policy that prevents documents with social security numbers from being shared outside the organization or sent in email to locations outside the organization.</span></span>

<span data-ttu-id="8fc94-120">Quindi, si dovranno configurare e testare i criteri con posizioni di test per garantire il corretto funzionamento del criterio DLP e ridurre al minimo i falsi positivi.</span><span class="sxs-lookup"><span data-stu-id="8fc94-120">Next, you configure and test the policies with test locations to ensure the correct DLP behavior and to minimize false positives.</span></span>

<span data-ttu-id="8fc94-121">Infine, sarà presentato all'organizzazione informando i dipendenti sui nuovi criteri e il comportamento desiderato e ampliando il numero delle posizioni.</span><span class="sxs-lookup"><span data-stu-id="8fc94-121">Finally, you roll it out to your organization by informing the employees of the new policies and their desired behavior and widening the scope of the locations.</span></span>

<span data-ttu-id="8fc94-122">Per ulteriori informazioni, vedere [Cominciare con i suggerimenti per i criteri di prevenzione della perdita dei dati (DLP)](https://docs.microsoft.com/office365/securitycompliance/get-started-with-dlp-policy-recommendations).</span><span class="sxs-lookup"><span data-stu-id="8fc94-122">For more information, see [Get started with DLP policy recommendations](https://docs.microsoft.com/office365/securitycompliance/get-started-with-dlp-policy-recommendations).</span></span>

<span data-ttu-id="8fc94-123">Come checkpoint provvisorio, vedere i [criteri uscita](infoprotect-exit-criteria.md#crit-infoprotect-step5) che corrispondono a questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="8fc94-123">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step5) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="8fc94-124">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="8fc94-124">Next step</span></span>


|||
|:-------|:-----|
|![](./media/stepnumbers/Step6.png)|[<span data-ttu-id="8fc94-125">Configurare la gestione degli accessi con privilegi per Office 365</span><span class="sxs-lookup"><span data-stu-id="8fc94-125">Configure privileged access management for Office 365</span></span>](infoprotect-configure-privileged-access-management.md)|


