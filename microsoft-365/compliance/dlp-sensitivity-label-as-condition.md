---
title: Usare le etichette di riservatezza come condizioni nei criteri di prevenzione della perdita dei dati (anteprima)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: informazioni sui servizi e sui tipi di elementi che è possibile usare per le etichette di sensibilità come condizioni dei criteri di prevenzione della perdita dei dati
ms.openlocfilehash: 561a6cbd7b8aeb9082862319c5cc6419fd79c896
ms.sourcegitcommit: f7ca339bdcad38796c550064fb152ea09687d0f3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2020
ms.locfileid: "48321111"
---
# <a name="use-sensitivity-labels-as-conditions-in-dlp-policies-preview"></a><span data-ttu-id="b78e8-103">Usare le etichette di riservatezza come condizioni nei criteri di prevenzione della perdita dei dati (anteprima)</span><span class="sxs-lookup"><span data-stu-id="b78e8-103">Use sensitivity labels as conditions in DLP policies (preview)</span></span>

<span data-ttu-id="b78e8-104">Le [etichette di riservatezza](sensitivity-labels.md) possono essere usate come condizioni dei criteri di prevenzione della perdita dei dati in queste posizioni:</span><span class="sxs-lookup"><span data-stu-id="b78e8-104">You can use [sensitivity labels](sensitivity-labels.md) as a condition in DLP policies for these location:</span></span>

- <span data-ttu-id="b78e8-105">Messaggi di posta elettronica di Exchange Online</span><span class="sxs-lookup"><span data-stu-id="b78e8-105">Exchange Online email messages</span></span>
- <span data-ttu-id="b78e8-106">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b78e8-106">SharePoint Online</span></span>
- <span data-ttu-id="b78e8-107">Siti di OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="b78e8-107">OneDrive for Business sites</span></span>
- <span data-ttu-id="b78e8-108">Dispositivi Windows 10</span><span class="sxs-lookup"><span data-stu-id="b78e8-108">Windows 10 devices</span></span>

<span data-ttu-id="b78e8-109">Le etichette di riservatezza sono mostrate come opzioni dell'elenco **Il contenuto contiene**.</span><span class="sxs-lookup"><span data-stu-id="b78e8-109">Sensitivity labels appear as an option in the **Content contains** list.</span></span>

![etichetta di riservatezza come condizione](../media/dlp-sensitivity-label-as-a-condition.png)

## <a name="supported-items-scenarios-and-policy-tips"></a><span data-ttu-id="b78e8-111">Elementi supportati, scenari e suggerimenti per i criteri</span><span class="sxs-lookup"><span data-stu-id="b78e8-111">Supported items, scenarios, and policy tips</span></span>

<span data-ttu-id="b78e8-112">È possibile usare le etichette di riservatezza come condizioni per questi elementi e in questi scenari.</span><span class="sxs-lookup"><span data-stu-id="b78e8-112">You can use sensitivity labels as conditions on these items and in these scenarios.</span></span>

### <a name="supported-items"></a><span data-ttu-id="b78e8-113">Elementi supportati</span><span class="sxs-lookup"><span data-stu-id="b78e8-113">Supported items</span></span>

|<span data-ttu-id="b78e8-114">servizio</span><span class="sxs-lookup"><span data-stu-id="b78e8-114">service</span></span>  |<span data-ttu-id="b78e8-115">tipo di elemento</span><span class="sxs-lookup"><span data-stu-id="b78e8-115">item type</span></span>  |<span data-ttu-id="b78e8-116">disponibile per i suggerimento per i criteri</span><span class="sxs-lookup"><span data-stu-id="b78e8-116">available to policy tip</span></span>  |<span data-ttu-id="b78e8-117">applicabile</span><span class="sxs-lookup"><span data-stu-id="b78e8-117">enforceable</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="b78e8-118">Exchange</span><span class="sxs-lookup"><span data-stu-id="b78e8-118">Exchange</span></span>    |<span data-ttu-id="b78e8-119">messaggio di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="b78e8-119">email message</span></span>         |<span data-ttu-id="b78e8-120">sì</span><span class="sxs-lookup"><span data-stu-id="b78e8-120">yes</span></span>         |<span data-ttu-id="b78e8-121">sì</span><span class="sxs-lookup"><span data-stu-id="b78e8-121">yes</span></span>         |
|<span data-ttu-id="b78e8-122">Exchange</span><span class="sxs-lookup"><span data-stu-id="b78e8-122">Exchange</span></span>    |<span data-ttu-id="b78e8-123">allegato di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="b78e8-123">email attachment</span></span>         |<span data-ttu-id="b78e8-124">no \*</span><span class="sxs-lookup"><span data-stu-id="b78e8-124">no \*</span></span>         |<span data-ttu-id="b78e8-125">no \*</span><span class="sxs-lookup"><span data-stu-id="b78e8-125">no \*</span></span>         |
|<span data-ttu-id="b78e8-126">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b78e8-126">SharePoint Online</span></span>     |<span data-ttu-id="b78e8-127">elementi di SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b78e8-127">items in SharePoint Online</span></span>         |<span data-ttu-id="b78e8-128">sì</span><span class="sxs-lookup"><span data-stu-id="b78e8-128">yes</span></span>         |<span data-ttu-id="b78e8-129">sì</span><span class="sxs-lookup"><span data-stu-id="b78e8-129">yes</span></span>         |
|<span data-ttu-id="b78e8-130">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="b78e8-130">OneDrive for Business</span></span>     |<span data-ttu-id="b78e8-131">elementi</span><span class="sxs-lookup"><span data-stu-id="b78e8-131">items</span></span>         |<span data-ttu-id="b78e8-132">sì</span><span class="sxs-lookup"><span data-stu-id="b78e8-132">yes</span></span>         |<span data-ttu-id="b78e8-133">sì</span><span class="sxs-lookup"><span data-stu-id="b78e8-133">yes</span></span>         |
|<span data-ttu-id="b78e8-134">Teams</span><span class="sxs-lookup"><span data-stu-id="b78e8-134">Teams</span></span>     |<span data-ttu-id="b78e8-135">Messaggi di Teams e dei canali</span><span class="sxs-lookup"><span data-stu-id="b78e8-135">Teams and channel messages</span></span>         |<span data-ttu-id="b78e8-136">non applicabile</span><span class="sxs-lookup"><span data-stu-id="b78e8-136">not applicable</span></span>         |<span data-ttu-id="b78e8-137">non applicabile</span><span class="sxs-lookup"><span data-stu-id="b78e8-137">not applicable</span></span>         |
|<span data-ttu-id="b78e8-138">Teams</span><span class="sxs-lookup"><span data-stu-id="b78e8-138">Teams</span></span>     |<span data-ttu-id="b78e8-139">allegati</span><span class="sxs-lookup"><span data-stu-id="b78e8-139">attachments</span></span>         |<span data-ttu-id="b78e8-140">sì \*\*</span><span class="sxs-lookup"><span data-stu-id="b78e8-140">yes \*\*</span></span>         |<span data-ttu-id="b78e8-141">sì \*\*</span><span class="sxs-lookup"><span data-stu-id="b78e8-141">yes \*\*</span></span>         |
|<span data-ttu-id="b78e8-142">Dispositivi Windows 10 (anteprima)</span><span class="sxs-lookup"><span data-stu-id="b78e8-142">Windows 10 devices (preview)</span></span>     |<span data-ttu-id="b78e8-143">elementi</span><span class="sxs-lookup"><span data-stu-id="b78e8-143">items</span></span>         |<span data-ttu-id="b78e8-144">sì</span><span class="sxs-lookup"><span data-stu-id="b78e8-144">yes</span></span>         |<span data-ttu-id="b78e8-145">sì</span><span class="sxs-lookup"><span data-stu-id="b78e8-145">yes</span></span>         |
|<span data-ttu-id="b78e8-146">MCAS (anteprima)</span><span class="sxs-lookup"><span data-stu-id="b78e8-146">MCAS (preview)</span></span> |<span data-ttu-id="b78e8-147">elementi</span><span class="sxs-lookup"><span data-stu-id="b78e8-147">items</span></span>         |<span data-ttu-id="b78e8-148">sì</span><span class="sxs-lookup"><span data-stu-id="b78e8-148">yes</span></span>         |<span data-ttu-id="b78e8-149">sì</span><span class="sxs-lookup"><span data-stu-id="b78e8-149">yes</span></span>         |

<span data-ttu-id="b78e8-150">\* il rilevamento di prevenzione della perdita dei dati per le etichette di riservatezza dei messaggi di posta elettronica è supportato.</span><span class="sxs-lookup"><span data-stu-id="b78e8-150">\* DLP detection of sensitivity labels on emails are supported.</span></span> <span data-ttu-id="b78e8-151">Il rilevamento di prevenzione della perdita dei dati per le etichette di riservatezza degli allegati dei messaggi non è supportato.</span><span class="sxs-lookup"><span data-stu-id="b78e8-151">DLP detection of sensitivity labeled email attachments are not.</span></span>

<span data-ttu-id="b78e8-152">\*\* Gli allegati inviati in Teams tramite chat individuali o canali sono caricati automaticamente su OneDrive for Business e SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b78e8-152">\*\* Attachments sent in Teams over 1:1 chat or channels are automatically uploaded to OneDrive for Business and SharePoint.</span></span> <span data-ttu-id="b78e8-153">Perciò, se SharePoint Online o OneDrive for Business sono inclusi come posizioni del criteri di prevenzione della perdita dei dati, gli allegati etichettai inviati in Teams saranno inclusi automaticamente nell'ambito di questa condizione.</span><span class="sxs-lookup"><span data-stu-id="b78e8-153">So if SharePoint Online or OneDrive for Business are included as locations in your DLP policy, then labeled attachments sent in Teams will be automatically included in the scope of this condition.</span></span> <span data-ttu-id="b78e8-154">Teams non deve essere selezionato come posizione nel criteri di prevenzione della perdita dei dati.</span><span class="sxs-lookup"><span data-stu-id="b78e8-154">Teams as a location does not need to be selected in the DLP policy.</span></span>

### <a name="supported-scenarios"></a><span data-ttu-id="b78e8-155">Scenari supportati</span><span class="sxs-lookup"><span data-stu-id="b78e8-155">Supported scenarios</span></span>

- <span data-ttu-id="b78e8-156">L'amministratore per la prevenzione della perdita dei dati sarà in grado di accedere a un elenco di tutte le etichette di conservazione del tenant quando sceglie di includere una o più etichette di riservatezza come condizioni.</span><span class="sxs-lookup"><span data-stu-id="b78e8-156">DLP Admin will be able to see a list of all sensitivity labels in the tenant when they choose to include one or more sensitivity labels as a condition.</span></span>
- <span data-ttu-id="b78e8-157">L'uso delle etichette di riservatezza come condizioni è supportato in tutti i carichi di lavoro, come indicato nella matrice di supporto precedente.</span><span class="sxs-lookup"><span data-stu-id="b78e8-157">Using sensitivity labels as a condition is supported across all workloads as indicated in the support matrix above</span></span>
- <span data-ttu-id="b78e8-158">I suggerimenti per i criteri di prevenzione della perdita dei dati continuano a essere visualizzati in tutti i carichi di lavoro (salvo quelli di Outlook Win32) per i criteri di prevenzione che contengono etichette di riservatezza come condizioni.</span><span class="sxs-lookup"><span data-stu-id="b78e8-158">DLP policy tips will continue to be shown across workloads (except Outlook Win32) for DLP policies which contain sensitivity label as a condition.</span></span>
- <span data-ttu-id="b78e8-159">Le etichette di riservatezza sono visualizzate anche all'interno del messaggio di posta elettronica del report degli incidenti, se c'è una corrispondenza con un criterio di prevenzione della perdita dei dati con etichette di riservatezza come condizioni. </span><span class="sxs-lookup"><span data-stu-id="b78e8-159">Sensitivity labels will also appear as a part of the incident report email if a DLP policy with sensitivity label as a condition is matched.</span></span>
- <span data-ttu-id="b78e8-160">I dettagli dell'etichetta di riservatezza sono mostrati anche nel log di controllo della corrispondenza delle regole di prevenzione della perdita dei dati, in caso di corrispondenza con criteri di prevenzione che contengono etichette di riservatezza come condizioni.</span><span class="sxs-lookup"><span data-stu-id="b78e8-160">Sensitivity label details will also be shown in the DLP rule match audit log for a DLP policy match which contains sensitivity label as a condition.</span></span>


### <a name="support-policy-tips"></a><span data-ttu-id="b78e8-161">Supporto per i suggerimenti per i criteri</span><span class="sxs-lookup"><span data-stu-id="b78e8-161">Support policy tips</span></span>


|<span data-ttu-id="b78e8-162">carico di lavoro</span><span class="sxs-lookup"><span data-stu-id="b78e8-162">workload</span></span>  |<span data-ttu-id="b78e8-163">suggerimenti per criteri supportati/non supportati</span><span class="sxs-lookup"><span data-stu-id="b78e8-163">policy tips supported/not supported</span></span>  |
|---------|---------|
|<span data-ttu-id="b78e8-164">OWA</span><span class="sxs-lookup"><span data-stu-id="b78e8-164">OWA</span></span> |    <span data-ttu-id="b78e8-165">supportato</span><span class="sxs-lookup"><span data-stu-id="b78e8-165">supported</span></span>     |
|<span data-ttu-id="b78e8-166">Outlook Win 32</span><span class="sxs-lookup"><span data-stu-id="b78e8-166">Outlook Win 32</span></span>    |  <span data-ttu-id="b78e8-167">non supportato</span><span class="sxs-lookup"><span data-stu-id="b78e8-167">not supported</span></span>       |
|<span data-ttu-id="b78e8-168">SharePoint</span><span class="sxs-lookup"><span data-stu-id="b78e8-168">SharePoint</span></span>   |   <span data-ttu-id="b78e8-169">supportato</span><span class="sxs-lookup"><span data-stu-id="b78e8-169">supported</span></span>      |
|<span data-ttu-id="b78e8-170">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="b78e8-170">OneDrive for Business</span></span>    |    <span data-ttu-id="b78e8-171">supportato</span><span class="sxs-lookup"><span data-stu-id="b78e8-171">supported</span></span>     |
|<span data-ttu-id="b78e8-172">dispositivi endpoint</span><span class="sxs-lookup"><span data-stu-id="b78e8-172">endpoint devices</span></span>   |  <span data-ttu-id="b78e8-173">non supportato</span><span class="sxs-lookup"><span data-stu-id="b78e8-173">not supported</span></span>       |
