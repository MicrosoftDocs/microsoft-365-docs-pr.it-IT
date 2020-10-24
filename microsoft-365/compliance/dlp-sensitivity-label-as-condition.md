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
ms.openlocfilehash: 2f8eb30e23d722a5e8faf7d0ddaca6b9a94e279b
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/21/2020
ms.locfileid: "48649635"
---
# <a name="use-sensitivity-labels-as-conditions-in-dlp-policies-preview"></a><span data-ttu-id="98438-103">Usare le etichette di riservatezza come condizioni nei criteri di prevenzione della perdita dei dati (anteprima)</span><span class="sxs-lookup"><span data-stu-id="98438-103">Use sensitivity labels as conditions in DLP policies (preview)</span></span>

<span data-ttu-id="98438-104">Le [etichette di riservatezza](sensitivity-labels.md) possono essere usate come condizioni dei criteri di prevenzione della perdita dei dati in queste posizioni:</span><span class="sxs-lookup"><span data-stu-id="98438-104">You can use [sensitivity labels](sensitivity-labels.md) as a condition in DLP policies for these location:</span></span>

- <span data-ttu-id="98438-105">Messaggi di posta elettronica di Exchange Online</span><span class="sxs-lookup"><span data-stu-id="98438-105">Exchange Online email messages</span></span>
- <span data-ttu-id="98438-106">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="98438-106">SharePoint Online</span></span>
- <span data-ttu-id="98438-107">Siti di OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="98438-107">OneDrive for Business sites</span></span>
- <span data-ttu-id="98438-108">Dispositivi Windows 10</span><span class="sxs-lookup"><span data-stu-id="98438-108">Windows 10 devices</span></span>

<span data-ttu-id="98438-109">Le etichette di riservatezza sono mostrate come opzioni dell'elenco **Il contenuto contiene**.</span><span class="sxs-lookup"><span data-stu-id="98438-109">Sensitivity labels appear as an option in the **Content contains** list.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="98438-110">![etichetta di riservatezza come condizione](../media/dlp-sensitivity-label-as-a-condition.png)</span><span class="sxs-lookup"><span data-stu-id="98438-110">![sensitivity label as a condition](../media/dlp-sensitivity-label-as-a-condition.png)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="98438-111">**Le etichette di riservatezza** come condizione non sono disponibili se sono state selezionate **chat di Teams e i messaggi del canale** come posizione in cui applicare i criteri di prevenzione della perdita dei dati.</span><span class="sxs-lookup"><span data-stu-id="98438-111">**Sensitivity Labels** as a condition will not be available if you have selected **Teams chat and channel messages** as a location to apply the DLP policy.</span></span>


## <a name="supported-items-scenarios-and-policy-tips"></a><span data-ttu-id="98438-112">Elementi supportati, scenari e suggerimenti per i criteri</span><span class="sxs-lookup"><span data-stu-id="98438-112">Supported items, scenarios, and policy tips</span></span>

<span data-ttu-id="98438-113">È possibile usare le etichette di riservatezza come condizioni per questi elementi e in questi scenari.</span><span class="sxs-lookup"><span data-stu-id="98438-113">You can use sensitivity labels as conditions on these items and in these scenarios.</span></span>

### <a name="supported-items"></a><span data-ttu-id="98438-114">Elementi supportati</span><span class="sxs-lookup"><span data-stu-id="98438-114">Supported items</span></span>

|<span data-ttu-id="98438-115">Servizio</span><span class="sxs-lookup"><span data-stu-id="98438-115">Service</span></span>  |<span data-ttu-id="98438-116">Tipo di elemento</span><span class="sxs-lookup"><span data-stu-id="98438-116">Item type</span></span>  |<span data-ttu-id="98438-117">Disponibile per suggerimento per i criteri</span><span class="sxs-lookup"><span data-stu-id="98438-117">Available to policy tip</span></span>  |<span data-ttu-id="98438-118">Applicabile</span><span class="sxs-lookup"><span data-stu-id="98438-118">Enforceable</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="98438-119">Exchange</span><span class="sxs-lookup"><span data-stu-id="98438-119">Exchange</span></span>    |<span data-ttu-id="98438-120">messaggio di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="98438-120">email message</span></span>         |<span data-ttu-id="98438-121">sì</span><span class="sxs-lookup"><span data-stu-id="98438-121">yes</span></span>         |<span data-ttu-id="98438-122">sì</span><span class="sxs-lookup"><span data-stu-id="98438-122">yes</span></span>         |
|<span data-ttu-id="98438-123">Exchange</span><span class="sxs-lookup"><span data-stu-id="98438-123">Exchange</span></span>    |<span data-ttu-id="98438-124">allegato di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="98438-124">email attachment</span></span>         |<span data-ttu-id="98438-125">no \*</span><span class="sxs-lookup"><span data-stu-id="98438-125">no \*</span></span>         |<span data-ttu-id="98438-126">no \*</span><span class="sxs-lookup"><span data-stu-id="98438-126">no \*</span></span>         |
|<span data-ttu-id="98438-127">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="98438-127">SharePoint Online</span></span>     |<span data-ttu-id="98438-128">elementi di SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="98438-128">items in SharePoint Online</span></span>         |<span data-ttu-id="98438-129">sì</span><span class="sxs-lookup"><span data-stu-id="98438-129">yes</span></span>         |<span data-ttu-id="98438-130">sì</span><span class="sxs-lookup"><span data-stu-id="98438-130">yes</span></span>         |
|<span data-ttu-id="98438-131">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="98438-131">OneDrive for Business</span></span>     |<span data-ttu-id="98438-132">elementi</span><span class="sxs-lookup"><span data-stu-id="98438-132">items</span></span>         |<span data-ttu-id="98438-133">sì</span><span class="sxs-lookup"><span data-stu-id="98438-133">yes</span></span>         |<span data-ttu-id="98438-134">sì</span><span class="sxs-lookup"><span data-stu-id="98438-134">yes</span></span>         |
|<span data-ttu-id="98438-135">Teams</span><span class="sxs-lookup"><span data-stu-id="98438-135">Teams</span></span>     |<span data-ttu-id="98438-136">Messaggi di Teams e dei canali</span><span class="sxs-lookup"><span data-stu-id="98438-136">Teams and channel messages</span></span>         |<span data-ttu-id="98438-137">non applicabile</span><span class="sxs-lookup"><span data-stu-id="98438-137">not applicable</span></span>         |<span data-ttu-id="98438-138">non applicabile</span><span class="sxs-lookup"><span data-stu-id="98438-138">not applicable</span></span>         |
|<span data-ttu-id="98438-139">Teams</span><span class="sxs-lookup"><span data-stu-id="98438-139">Teams</span></span>     |<span data-ttu-id="98438-140">allegati</span><span class="sxs-lookup"><span data-stu-id="98438-140">attachments</span></span>         |<span data-ttu-id="98438-141">sì \*\*</span><span class="sxs-lookup"><span data-stu-id="98438-141">yes \*\*</span></span>         |<span data-ttu-id="98438-142">sì \*\*</span><span class="sxs-lookup"><span data-stu-id="98438-142">yes \*\*</span></span>         |
|<span data-ttu-id="98438-143">Dispositivi Windows 10 (anteprima)</span><span class="sxs-lookup"><span data-stu-id="98438-143">Windows 10 devices (preview)</span></span>     |<span data-ttu-id="98438-144">elementi</span><span class="sxs-lookup"><span data-stu-id="98438-144">items</span></span>         |<span data-ttu-id="98438-145">sì</span><span class="sxs-lookup"><span data-stu-id="98438-145">yes</span></span>         |<span data-ttu-id="98438-146">sì</span><span class="sxs-lookup"><span data-stu-id="98438-146">yes</span></span>         |
|<span data-ttu-id="98438-147">MCAS (anteprima)</span><span class="sxs-lookup"><span data-stu-id="98438-147">MCAS (preview)</span></span> |<span data-ttu-id="98438-148">elementi</span><span class="sxs-lookup"><span data-stu-id="98438-148">items</span></span>         |<span data-ttu-id="98438-149">sì</span><span class="sxs-lookup"><span data-stu-id="98438-149">yes</span></span>         |<span data-ttu-id="98438-150">sì</span><span class="sxs-lookup"><span data-stu-id="98438-150">yes</span></span>         |

<span data-ttu-id="98438-151">\* il rilevamento di prevenzione della perdita dei dati per le etichette di riservatezza dei messaggi di posta elettronica è supportato.</span><span class="sxs-lookup"><span data-stu-id="98438-151">\* DLP detection of sensitivity labels on emails are supported.</span></span> <span data-ttu-id="98438-152">Il rilevamento di prevenzione della perdita dei dati per le etichette di riservatezza degli allegati dei messaggi non è supportato.</span><span class="sxs-lookup"><span data-stu-id="98438-152">DLP detection of sensitivity labeled email attachments are not.</span></span>

<span data-ttu-id="98438-153">\*\* Gli allegati inviati in Teams tramite chat individuali o canali sono caricati automaticamente su OneDrive for Business e SharePoint.</span><span class="sxs-lookup"><span data-stu-id="98438-153">\*\* Attachments sent in Teams over 1:1 chat or channels are automatically uploaded to OneDrive for Business and SharePoint.</span></span> <span data-ttu-id="98438-154">Perciò, se SharePoint Online o OneDrive for Business sono inclusi come posizioni del criteri di prevenzione della perdita dei dati, gli allegati etichettai inviati in Teams saranno inclusi automaticamente nell'ambito di questa condizione.</span><span class="sxs-lookup"><span data-stu-id="98438-154">So if SharePoint Online or OneDrive for Business are included as locations in your DLP policy, then labeled attachments sent in Teams will be automatically included in the scope of this condition.</span></span> <span data-ttu-id="98438-155">Teams non deve essere selezionato come posizione nel criteri di prevenzione della perdita dei dati.</span><span class="sxs-lookup"><span data-stu-id="98438-155">Teams as a location does not need to be selected in the DLP policy.</span></span>

### <a name="supported-scenarios"></a><span data-ttu-id="98438-156">Scenari supportati</span><span class="sxs-lookup"><span data-stu-id="98438-156">Supported scenarios</span></span>

- <span data-ttu-id="98438-157">L'amministratore per la prevenzione della perdita dei dati sarà in grado di accedere a un elenco di tutte le etichette di conservazione del tenant quando sceglie di includere una o più etichette di riservatezza come condizioni.</span><span class="sxs-lookup"><span data-stu-id="98438-157">DLP Admin will be able to see a list of all sensitivity labels in the tenant when they choose to include one or more sensitivity labels as a condition.</span></span>

- <span data-ttu-id="98438-158">L'uso delle etichette di riservatezza come condizioni è supportato in tutti i carichi di lavoro, come indicato nella matrice di supporto precedente.</span><span class="sxs-lookup"><span data-stu-id="98438-158">Using sensitivity labels as a condition is supported across all workloads as indicated in the support matrix above.</span></span>

- <span data-ttu-id="98438-159">I suggerimenti per i criteri di prevenzione della perdita dei dati continuano a essere visualizzati in tutti i carichi di lavoro (salvo quelli di Outlook Win32) per i criteri di prevenzione che contengono etichette di riservatezza come condizioni.</span><span class="sxs-lookup"><span data-stu-id="98438-159">DLP policy tips will continue to be shown across workloads (except Outlook Win32) for DLP policies which contain sensitivity label as a condition.</span></span>

- <span data-ttu-id="98438-160">Le etichette di riservatezza sono visualizzate anche all'interno del messaggio di posta elettronica del report degli incidenti, se c'è una corrispondenza con un criterio di prevenzione della perdita dei dati con etichette di riservatezza come condizioni. </span><span class="sxs-lookup"><span data-stu-id="98438-160">Sensitivity labels will also appear as a part of the incident report email if a DLP policy with sensitivity label as a condition is matched.</span></span>

- <span data-ttu-id="98438-161">I dettagli dell'etichetta di riservatezza sono mostrati anche nel log di controllo della corrispondenza delle regole di prevenzione della perdita dei dati, in caso di corrispondenza con criteri di prevenzione che contengono etichette di riservatezza come condizioni.</span><span class="sxs-lookup"><span data-stu-id="98438-161">Sensitivity label details will also be shown in the DLP rule match audit log for a DLP policy match which contains sensitivity label as a condition.</span></span>


### <a name="support-policy-tips"></a><span data-ttu-id="98438-162">Supporto per i suggerimenti per i criteri</span><span class="sxs-lookup"><span data-stu-id="98438-162">Support policy tips</span></span>


|<span data-ttu-id="98438-163">Carico di lavoro</span><span class="sxs-lookup"><span data-stu-id="98438-163">Workload</span></span>  |<span data-ttu-id="98438-164">Suggerimenti per criteri supportati/non supportati</span><span class="sxs-lookup"><span data-stu-id="98438-164">Policy tips supported/not supported</span></span>  |
|---------|---------|
|<span data-ttu-id="98438-165">OWA</span><span class="sxs-lookup"><span data-stu-id="98438-165">OWA</span></span> |    <span data-ttu-id="98438-166">supportato</span><span class="sxs-lookup"><span data-stu-id="98438-166">supported</span></span>     |
|<span data-ttu-id="98438-167">Outlook Win 32</span><span class="sxs-lookup"><span data-stu-id="98438-167">Outlook Win 32</span></span>    |  <span data-ttu-id="98438-168">non supportato</span><span class="sxs-lookup"><span data-stu-id="98438-168">not supported</span></span>       |
|<span data-ttu-id="98438-169">SharePoint</span><span class="sxs-lookup"><span data-stu-id="98438-169">SharePoint</span></span>   |   <span data-ttu-id="98438-170">supportato</span><span class="sxs-lookup"><span data-stu-id="98438-170">supported</span></span>      |
|<span data-ttu-id="98438-171">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="98438-171">OneDrive for Business</span></span>    |    <span data-ttu-id="98438-172">supportato</span><span class="sxs-lookup"><span data-stu-id="98438-172">supported</span></span>     |
|<span data-ttu-id="98438-173">dispositivi endpoint</span><span class="sxs-lookup"><span data-stu-id="98438-173">endpoint devices</span></span>   |  <span data-ttu-id="98438-174">non supportato</span><span class="sxs-lookup"><span data-stu-id="98438-174">not supported</span></span>       |
