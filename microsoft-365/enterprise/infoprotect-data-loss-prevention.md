---
title: 'Passaggio 5: Configurare i criteri di prevenzione della perdita dei dati di Office 365'
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
description: Comprendere e distribuire i criteri di prevenzione della perdita dei dati di Office 365 in Microsoft 365.
ms.openlocfilehash: dbe88885812e51b0daefa89dae123af5907c60a8
ms.sourcegitcommit: 63e35b846d964dde5919a08c2fe432e749e8eff6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/19/2019
ms.locfileid: "37047249"
---
# <a name="step-5-configure-office-365-data-loss-prevention"></a><span data-ttu-id="fd2b5-103">Passaggio 5: Configurare i criteri di prevenzione della perdita dei dati di Office 365</span><span class="sxs-lookup"><span data-stu-id="fd2b5-103">Step 5: Configure Office 365 Data Loss Prevention</span></span>

<span data-ttu-id="fd2b5-104">*Questo passaggio è facoltativo e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="fd2b5-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="fd2b5-105">I criteri di prevenzione della perdita dei dati (DLP) del Centro sicurezza e conformità di Office 365 permettono di identificare, monitorare e proteggere automaticamente le informazioni riservate in tutto Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fd2b5-105">With data loss prevention (DLP) policies in the Office 365 Security & Compliance center, you can identify, monitor, and automatically protect sensitive information across Microsoft 365.</span></span> <span data-ttu-id="fd2b5-106">Con i criteri di prevenzione della perdita dei dati, è possibile:</span><span class="sxs-lookup"><span data-stu-id="fd2b5-106">With DLP policies, you can:</span></span>

- <span data-ttu-id="fd2b5-107">Identificare le informazioni riservate in numerose posizioni, ad esempio Exchange Online, SharePoint Online e OneDrive for Business e Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fd2b5-107">Identify sensitive information across many locations, such as Exchange Online, SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>
- <span data-ttu-id="fd2b5-108">Impedire la condivisione accidentale di informazioni riservate bloccando l'accesso a un documento o alla posta elettronica che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="fd2b5-108">Prevent the accidental sharing of sensitive information by blocking access to a document or blocking the email that contains it.</span></span>
- <span data-ttu-id="fd2b5-109">Monitorare e proteggere le informazioni riservate nelle versioni desktop di Excel, PowerPoint e Word.</span><span class="sxs-lookup"><span data-stu-id="fd2b5-109">Monitor and protect sensitive information in the desktop versions of Excel, PowerPoint, and Word.</span></span>
- <span data-ttu-id="fd2b5-110">Fornire agli utenti informazioni su come garantire la conformità senza interrompere il flusso di lavoro con notifiche di posta elettronica e suggerimenti per i criteri.</span><span class="sxs-lookup"><span data-stu-id="fd2b5-110">Help users learn how to stay compliant without interrupting their workflow with email notifications and policy tips.</span></span> 
- <span data-ttu-id="fd2b5-111">Visualizzare report DLP che indicano i contenuti corrispondenti ai criteri DLP dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="fd2b5-111">View DLP reports showing content that matches your organization's DLP policies.</span></span>

<span data-ttu-id="fd2b5-112">Un criterio DLP consente di specificare:</span><span class="sxs-lookup"><span data-stu-id="fd2b5-112">A DLP policy specifies:</span></span>

- <span data-ttu-id="fd2b5-113">**Dove:** Posizioni come ad esempio siti di Exchange Online, SharePoint Online e OneDrive for Business, ma anche chat e canali di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fd2b5-113">**Where:** Locations such as Exchange Online, SharePoint Online, and OneDrive for Business sites, as well as Microsoft Teams chats and channels.</span></span>
- <span data-ttu-id="fd2b5-114">**Quando:** Condizioni che il contenuto deve soddisfare all'interno di una specifica regola dei criteri.</span><span class="sxs-lookup"><span data-stu-id="fd2b5-114">**When:** Conditions the content must match within a specific policy rule.</span></span>
- <span data-ttu-id="fd2b5-115">**Come:** Azioni da eseguire automaticamente nell’ambito di tale regola dei criteri per soddisfare tali condizioni.</span><span class="sxs-lookup"><span data-stu-id="fd2b5-115">**How:** Actions within that matching policy rule to take automatically for the matching conditions.</span></span>

<span data-ttu-id="fd2b5-116">In altre parole:</span><span class="sxs-lookup"><span data-stu-id="fd2b5-116">In other words:</span></span>

- <span data-ttu-id="fd2b5-117">Per un documento in questa posizione (dove), se il contenuto soddisfa le condizioni di una regola (quando), esegue automaticamente le azioni specificate in tale regola (come).</span><span class="sxs-lookup"><span data-stu-id="fd2b5-117">For a document in this location (where), if the content matches the conditions of a rule (when), then automatically take the actions specified in the rule (how).</span></span>

<span data-ttu-id="fd2b5-118">Per determinare il set di criteri DLP di cui si ha bisogno, è necessario analizzare i documenti e i tipi di dati che necessitano di protezione dalla perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="fd2b5-118">To determine the set of DLP policies you need, you must analyze your documents and the types of data within them that need protection from data loss.</span></span> <span data-ttu-id="fd2b5-119">Ad esempio, se si possiede un'organizzazione finanziaria negli Stati Uniti d'America, sarà necessario creare un criterio DLP che impedisca la condivisione esterna all'organizzazione di documenti con i numeri di previdenza sociale o l’invio tramite posta elettronica a posizioni esterne all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="fd2b5-119">For example, if you are a financial organization in the United States of America, you would create a DLP policy that prevents documents with social security numbers from being shared outside the organization or sent in email to locations outside the organization.</span></span>

<span data-ttu-id="fd2b5-120">Quindi, si dovranno configurare e testare i criteri con posizioni di test per garantire il corretto funzionamento del criterio DLP e ridurre al minimo i falsi positivi.</span><span class="sxs-lookup"><span data-stu-id="fd2b5-120">Next, you configure and test the policies with test locations to ensure the correct DLP behavior and to minimize false positives.</span></span>

<span data-ttu-id="fd2b5-121">Infine, sarà presentato all'organizzazione informando i dipendenti sui nuovi criteri e il comportamento desiderato e ampliando il numero delle posizioni.</span><span class="sxs-lookup"><span data-stu-id="fd2b5-121">Finally, you roll it out to your organization by informing the employees of the new policies and their desired behavior and widening the scope of the locations.</span></span>

<span data-ttu-id="fd2b5-122">Per ulteriori informazioni, vedere [Cominciare con i suggerimenti per i criteri di prevenzione della perdita dei dati (DLP)](https://docs.microsoft.com/office365/securitycompliance/get-started-with-dlp-policy-recommendations).</span><span class="sxs-lookup"><span data-stu-id="fd2b5-122">For more information, see [Get started with DLP policy recommendations](https://docs.microsoft.com/office365/securitycompliance/get-started-with-dlp-policy-recommendations).</span></span>

<span data-ttu-id="fd2b5-123">Come checkpoint provvisorio, vedere i [criteri uscita](infoprotect-exit-criteria.md#crit-infoprotect-step5) che corrispondono a questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="fd2b5-123">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step5) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="fd2b5-124">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="fd2b5-124">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step6.png)|[<span data-ttu-id="fd2b5-125">Configurare la crittografia della posta elettronica</span><span class="sxs-lookup"><span data-stu-id="fd2b5-125">Configure email encryption</span></span>](infoprotect-email-encryption.md)|


