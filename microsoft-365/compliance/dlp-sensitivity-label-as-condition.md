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
ms.openlocfilehash: bb06ed6919a396bef1e5d1f1cb04731fa11267ae
ms.sourcegitcommit: c1ee4ed3c5826872b57339e1e1aa33b4d2209711
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2020
ms.locfileid: "48235723"
---
# <a name="use-sensitivity-labels-as-conditions-in-dlp-policies-preview"></a><span data-ttu-id="7b055-103">Usare le etichette di riservatezza come condizioni nei criteri di prevenzione della perdita dei dati (anteprima)</span><span class="sxs-lookup"><span data-stu-id="7b055-103">Use sensitivity labels as conditions in DLP policies (preview)</span></span>

<span data-ttu-id="7b055-104">Le [etichette di riservatezza](sensitivity-labels.md) possono essere usate come condizioni dei criteri di prevenzione della perdita dei dati in queste posizioni:</span><span class="sxs-lookup"><span data-stu-id="7b055-104">You can use [sensitivity labels](sensitivity-labels.md) as a condition in DLP policies for these location:</span></span>

- <span data-ttu-id="7b055-105">Messaggi di posta elettronica di Exchange Online</span><span class="sxs-lookup"><span data-stu-id="7b055-105">Exchange Online email messages</span></span>
- <span data-ttu-id="7b055-106">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="7b055-106">SharePoint Online</span></span>
- <span data-ttu-id="7b055-107">Siti di OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="7b055-107">OneDrive for Business sites</span></span>
- <span data-ttu-id="7b055-108">Dispositivi Windows 10</span><span class="sxs-lookup"><span data-stu-id="7b055-108">Windows 10 devices</span></span>

<span data-ttu-id="7b055-109">Le etichette di riservatezza sono mostrate come opzioni dell'elenco **Il contenuto contiene**.</span><span class="sxs-lookup"><span data-stu-id="7b055-109">Sensitivity labels appear as an option in the **Content contains** list.</span></span>

![etichetta di riservatezza come condizione](../media/dlp-sensitivity-label-as-a-condition.png)

## <a name="supported-items-scenarios-and-policy-tips"></a><span data-ttu-id="7b055-111">Elementi supportati, scenari e suggerimenti per i criteri</span><span class="sxs-lookup"><span data-stu-id="7b055-111">Supported items, scenarios, and policy tips</span></span>

<span data-ttu-id="7b055-112">È possibile usare le etichette di riservatezza come condizioni per questi elementi e in questi scenari.</span><span class="sxs-lookup"><span data-stu-id="7b055-112">You can use sensitivity labels as conditions on these items and in these scenarios.</span></span>

### <a name="supported-items"></a><span data-ttu-id="7b055-113">Elementi supportati</span><span class="sxs-lookup"><span data-stu-id="7b055-113">Supported items</span></span>

|<span data-ttu-id="7b055-114">servizio</span><span class="sxs-lookup"><span data-stu-id="7b055-114">service</span></span>  |<span data-ttu-id="7b055-115">tipo di elemento</span><span class="sxs-lookup"><span data-stu-id="7b055-115">item type</span></span>  |<span data-ttu-id="7b055-116">disponibile per i suggerimento per i criteri</span><span class="sxs-lookup"><span data-stu-id="7b055-116">available to policy tip</span></span>  |<span data-ttu-id="7b055-117">applicabile</span><span class="sxs-lookup"><span data-stu-id="7b055-117">enforceable</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="7b055-118">Exchange</span><span class="sxs-lookup"><span data-stu-id="7b055-118">Exchange</span></span>    |<span data-ttu-id="7b055-119">messaggio di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="7b055-119">email message</span></span>         |<span data-ttu-id="7b055-120">sì</span><span class="sxs-lookup"><span data-stu-id="7b055-120">yes</span></span>         |<span data-ttu-id="7b055-121">sì</span><span class="sxs-lookup"><span data-stu-id="7b055-121">yes</span></span>         |
|<span data-ttu-id="7b055-122">Exchange</span><span class="sxs-lookup"><span data-stu-id="7b055-122">Exchange</span></span>    |<span data-ttu-id="7b055-123">allegato di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="7b055-123">email attachment</span></span>         |<span data-ttu-id="7b055-124">no \*</span><span class="sxs-lookup"><span data-stu-id="7b055-124">no \*</span></span>         |<span data-ttu-id="7b055-125">no \*</span><span class="sxs-lookup"><span data-stu-id="7b055-125">no \*</span></span>         |
|<span data-ttu-id="7b055-126">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="7b055-126">SharePoint Online</span></span>     |<span data-ttu-id="7b055-127">elementi di SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="7b055-127">items in SharePoint Online</span></span>         |<span data-ttu-id="7b055-128">sì</span><span class="sxs-lookup"><span data-stu-id="7b055-128">yes</span></span>         |<span data-ttu-id="7b055-129">sì</span><span class="sxs-lookup"><span data-stu-id="7b055-129">yes</span></span>         |
|<span data-ttu-id="7b055-130">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="7b055-130">OneDrive for Business</span></span>     |<span data-ttu-id="7b055-131">elementi</span><span class="sxs-lookup"><span data-stu-id="7b055-131">items</span></span>         |<span data-ttu-id="7b055-132">sì</span><span class="sxs-lookup"><span data-stu-id="7b055-132">yes</span></span>         |<span data-ttu-id="7b055-133">sì</span><span class="sxs-lookup"><span data-stu-id="7b055-133">yes</span></span>         |
|<span data-ttu-id="7b055-134">Teams</span><span class="sxs-lookup"><span data-stu-id="7b055-134">Teams</span></span>     |<span data-ttu-id="7b055-135">Messaggi di Teams e dei canali</span><span class="sxs-lookup"><span data-stu-id="7b055-135">Teams and channel messages</span></span>         |<span data-ttu-id="7b055-136">non applicabile</span><span class="sxs-lookup"><span data-stu-id="7b055-136">not applicable</span></span>         |<span data-ttu-id="7b055-137">non applicabile</span><span class="sxs-lookup"><span data-stu-id="7b055-137">not applicable</span></span>         |
|<span data-ttu-id="7b055-138">Teams</span><span class="sxs-lookup"><span data-stu-id="7b055-138">Teams</span></span>     |<span data-ttu-id="7b055-139">allegati</span><span class="sxs-lookup"><span data-stu-id="7b055-139">attachements</span></span>         |<span data-ttu-id="7b055-140">sì \*\*</span><span class="sxs-lookup"><span data-stu-id="7b055-140">yes \*\*</span></span>         |<span data-ttu-id="7b055-141">sì \*\*</span><span class="sxs-lookup"><span data-stu-id="7b055-141">yes \*\*</span></span>         |
|<span data-ttu-id="7b055-142">Dispositivi Windows 10 (anteprima)</span><span class="sxs-lookup"><span data-stu-id="7b055-142">Windows 10 devices (preview)</span></span>     |<span data-ttu-id="7b055-143">elementi</span><span class="sxs-lookup"><span data-stu-id="7b055-143">items</span></span>         |<span data-ttu-id="7b055-144">sì</span><span class="sxs-lookup"><span data-stu-id="7b055-144">yes</span></span>         |<span data-ttu-id="7b055-145">sì</span><span class="sxs-lookup"><span data-stu-id="7b055-145">yes</span></span>         |
|<span data-ttu-id="7b055-146">MCAS (anteprima)</span><span class="sxs-lookup"><span data-stu-id="7b055-146">MCAS (preview)</span></span> |<span data-ttu-id="7b055-147">elementi</span><span class="sxs-lookup"><span data-stu-id="7b055-147">items</span></span>         |<span data-ttu-id="7b055-148">sì</span><span class="sxs-lookup"><span data-stu-id="7b055-148">yes</span></span>         |<span data-ttu-id="7b055-149">sì</span><span class="sxs-lookup"><span data-stu-id="7b055-149">yes</span></span>         |

<span data-ttu-id="7b055-150">\* il rilevamento di prevenzione della perdita dei dati per le etichette di riservatezza dei messaggi di posta elettronica è supportato.</span><span class="sxs-lookup"><span data-stu-id="7b055-150">\* DLP detection of sensitivity labels on emails are supported.</span></span> <span data-ttu-id="7b055-151">Il rilevamento di prevenzione della perdita dei dati per le etichette di riservatezza degli allegati dei messaggi non è supportato.</span><span class="sxs-lookup"><span data-stu-id="7b055-151">DLP detection of sensitivity labeled email attachments are not.</span></span>

<span data-ttu-id="7b055-152">\*\* Gli allegati inviati in Teams tramite chat individuali o canali sono caricati automaticamente su OneDrive for Business e SharePoint.</span><span class="sxs-lookup"><span data-stu-id="7b055-152">\*\* Attachments sent in Teams over 1:1 chat or channels are automatically uploaded to One drive for business and SharePoint.</span></span> <span data-ttu-id="7b055-153">Perciò, se SharePoint Online o OneDrive for Business sono inclusi come posizioni del criteri di prevenzione della perdita dei dati, gli allegati etichettai inviati in Teams saranno inclusi automaticamente nell'ambito di questa condizione.</span><span class="sxs-lookup"><span data-stu-id="7b055-153">So if SharePoint Online or One Drive for Business are included as locations in your DLP policy, then labeled attachments sent in Teams will be automatically included in the scope of this condition.</span></span> <span data-ttu-id="7b055-154">Teams non deve essere selezionato come posizione nel criteri di prevenzione della perdita dei dati.</span><span class="sxs-lookup"><span data-stu-id="7b055-154">Teams as a location does not need to be selected in the DLP policy.</span></span>

### <a name="supported-scenarios"></a><span data-ttu-id="7b055-155">Scenari supportati</span><span class="sxs-lookup"><span data-stu-id="7b055-155">Supported scenarios</span></span>

- <span data-ttu-id="7b055-156">L'amministratore per la prevenzione della perdita dei dati sarà in grado di accedere a un elenco di tutte le etichette di conservazione del tenant quando sceglie di includere una o più etichette di riservatezza come condizioni.</span><span class="sxs-lookup"><span data-stu-id="7b055-156">DLP Admin will be able to see a list of all sensitivity labels in the tenant when they choose to include one or more sensitivity labels as a condition.</span></span>
- <span data-ttu-id="7b055-157">L'uso delle etichette di riservatezza come condizioni è supportato in tutti i carichi di lavoro, come indicato nella matrice di supporto precedente.</span><span class="sxs-lookup"><span data-stu-id="7b055-157">Using sensitivity labels as a condition is supported across all workloads as indicated in the support matrix above</span></span>
- <span data-ttu-id="7b055-158">I suggerimenti per i criteri di prevenzione della perdita dei dati continuano a essere visualizzati in tutti i carichi di lavoro (salvo quelli di Outlook Win32) per i criteri di prevenzione che contengono etichette di riservatezza come condizioni.</span><span class="sxs-lookup"><span data-stu-id="7b055-158">DLP policy tips will continue to be shown across workloads (except Outlook Win32) for DLP policies which contain sensitivity label as a condition.</span></span>
- <span data-ttu-id="7b055-159">Le etichette di riservatezza sono visualizzate anche all'interno del messaggio di posta elettronica del report degli incidenti, se c'è una corrispondenza con un criterio di prevenzione della perdita dei dati con etichette di riservatezza come condizioni. </span><span class="sxs-lookup"><span data-stu-id="7b055-159">Sensitivity labels will also appear as a part of the incident report email if a DLP policy with sensitivity label as a condition is matched.</span></span>
- <span data-ttu-id="7b055-160">I dettagli dell'etichetta di riservatezza sono mostrati anche nel log di controllo della corrispondenza delle regole di prevenzione della perdita dei dati, in caso di corrispondenza con criteri di prevenzione che contengono etichette di riservatezza come condizioni.</span><span class="sxs-lookup"><span data-stu-id="7b055-160">Sensitivity label details will also be shown in the DLP rule match audit log for a DLP policy match which contains sensitivity label as a condition.</span></span>


### <a name="support-policy-tips"></a><span data-ttu-id="7b055-161">Supporto per i suggerimenti per i criteri</span><span class="sxs-lookup"><span data-stu-id="7b055-161">Support policy tips</span></span>


|<span data-ttu-id="7b055-162">carico di lavoro</span><span class="sxs-lookup"><span data-stu-id="7b055-162">workload</span></span>  |<span data-ttu-id="7b055-163">suggerimenti per criteri supportati/non supportati</span><span class="sxs-lookup"><span data-stu-id="7b055-163">policy tips supported/not supported</span></span>  |
|---------|---------|
|<span data-ttu-id="7b055-164">OWA</span><span class="sxs-lookup"><span data-stu-id="7b055-164">OWA</span></span> |    <span data-ttu-id="7b055-165">supportato</span><span class="sxs-lookup"><span data-stu-id="7b055-165">supported</span></span>     |
|<span data-ttu-id="7b055-166">Outlook Win 32</span><span class="sxs-lookup"><span data-stu-id="7b055-166">Outlook Win 32</span></span>    |  <span data-ttu-id="7b055-167">non supportato</span><span class="sxs-lookup"><span data-stu-id="7b055-167">not supported</span></span>       |
|<span data-ttu-id="7b055-168">SharePoint</span><span class="sxs-lookup"><span data-stu-id="7b055-168">SharePoint</span></span>   |   <span data-ttu-id="7b055-169">supportato</span><span class="sxs-lookup"><span data-stu-id="7b055-169">supported</span></span>      |
|<span data-ttu-id="7b055-170">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="7b055-170">OneDrive for Business</span></span>    |    <span data-ttu-id="7b055-171">supportato</span><span class="sxs-lookup"><span data-stu-id="7b055-171">supported</span></span>     |
|<span data-ttu-id="7b055-172">dispositivi endpoint</span><span class="sxs-lookup"><span data-stu-id="7b055-172">endpoint devices</span></span>   |  <span data-ttu-id="7b055-173">non supportato</span><span class="sxs-lookup"><span data-stu-id="7b055-173">not supported</span></span>       |
