---
title: Usare le etichette di riservatezza come condizioni per i criteri di prevenzione della perdita dei dati
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
description: informazioni sui servizi e sui tipi di elementi che è possibile usare nelle etichette di riservatezza come condizioni per i criteri di prevenzione della perdita dei dati
ms.openlocfilehash: 19bd80de225f703b5c280163e94826498fa097bd
ms.sourcegitcommit: 2655bb0ccd66279c35be2fadbd893c937d084109
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2021
ms.locfileid: "51876295"
---
# <a name="use-sensitivity-labels-as-conditions-in-dlp-policies"></a><span data-ttu-id="3b3db-103">Usare le etichette di riservatezza come condizioni per i criteri di prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="3b3db-103">Use sensitivity labels as conditions in DLP policies</span></span>

<span data-ttu-id="3b3db-104">Le [etichette di riservatezza](sensitivity-labels.md) possono essere usate come condizioni dei criteri di prevenzione della perdita dei dati in queste posizioni:</span><span class="sxs-lookup"><span data-stu-id="3b3db-104">You can use [sensitivity labels](sensitivity-labels.md) as a condition in DLP policies for these location:</span></span>

- <span data-ttu-id="3b3db-105">Messaggi di posta elettronica di Exchange Online</span><span class="sxs-lookup"><span data-stu-id="3b3db-105">Exchange Online email messages</span></span>
- <span data-ttu-id="3b3db-106">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="3b3db-106">SharePoint Online</span></span>
- <span data-ttu-id="3b3db-107">Siti di OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="3b3db-107">OneDrive for Business sites</span></span>
- <span data-ttu-id="3b3db-108">Dispositivi Windows 10</span><span class="sxs-lookup"><span data-stu-id="3b3db-108">Windows 10 devices</span></span>

<span data-ttu-id="3b3db-109">Le etichette di riservatezza sono mostrate come opzioni dell'elenco **Il contenuto contiene**.</span><span class="sxs-lookup"><span data-stu-id="3b3db-109">Sensitivity labels appear as an option in the **Content contains** list.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="3b3db-110">![etichetta di riservatezza come condizione](../media/dlp-sensitivity-label-as-a-condition.png)</span><span class="sxs-lookup"><span data-stu-id="3b3db-110">![sensitivity label as a condition](../media/dlp-sensitivity-label-as-a-condition.png)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3b3db-111">**Le etichette di riservatezza** come condizione non sono disponibili se sono state selezionate **chat di Teams e i messaggi del canale** come posizione in cui applicare i criteri di prevenzione della perdita dei dati.</span><span class="sxs-lookup"><span data-stu-id="3b3db-111">**Sensitivity Labels** as a condition will not be available if you have selected **Teams chat and channel messages** as a location to apply the DLP policy.</span></span>


## <a name="supported-items-scenarios-and-policy-tips"></a><span data-ttu-id="3b3db-112">Elementi supportati, scenari e suggerimenti per i criteri</span><span class="sxs-lookup"><span data-stu-id="3b3db-112">Supported items, scenarios, and policy tips</span></span>

<span data-ttu-id="3b3db-113">È possibile usare le etichette di riservatezza come condizioni per questi elementi e in questi scenari.</span><span class="sxs-lookup"><span data-stu-id="3b3db-113">You can use sensitivity labels as conditions on these items and in these scenarios.</span></span>

### <a name="supported-items"></a><span data-ttu-id="3b3db-114">Elementi supportati</span><span class="sxs-lookup"><span data-stu-id="3b3db-114">Supported items</span></span>

|<span data-ttu-id="3b3db-115">Servizio</span><span class="sxs-lookup"><span data-stu-id="3b3db-115">Service</span></span>  |<span data-ttu-id="3b3db-116">Tipo di elemento</span><span class="sxs-lookup"><span data-stu-id="3b3db-116">Item type</span></span>  |<span data-ttu-id="3b3db-117">Disponibile per suggerimento per i criteri</span><span class="sxs-lookup"><span data-stu-id="3b3db-117">Available to policy tip</span></span>  |<span data-ttu-id="3b3db-118">Applicabile</span><span class="sxs-lookup"><span data-stu-id="3b3db-118">Enforceable</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="3b3db-119">Exchange</span><span class="sxs-lookup"><span data-stu-id="3b3db-119">Exchange</span></span>    |<span data-ttu-id="3b3db-120">messaggio di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="3b3db-120">email message</span></span>         |<span data-ttu-id="3b3db-121">sì</span><span class="sxs-lookup"><span data-stu-id="3b3db-121">yes</span></span>         |<span data-ttu-id="3b3db-122">sì</span><span class="sxs-lookup"><span data-stu-id="3b3db-122">yes</span></span>         |
|<span data-ttu-id="3b3db-123">Exchange</span><span class="sxs-lookup"><span data-stu-id="3b3db-123">Exchange</span></span>    |<span data-ttu-id="3b3db-124">allegato di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="3b3db-124">email attachment</span></span>         |<span data-ttu-id="3b3db-125">no \*</span><span class="sxs-lookup"><span data-stu-id="3b3db-125">no \*</span></span>         |<span data-ttu-id="3b3db-126">sì\*</span><span class="sxs-lookup"><span data-stu-id="3b3db-126">yes \*</span></span>         |
|<span data-ttu-id="3b3db-127">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="3b3db-127">SharePoint Online</span></span>     |<span data-ttu-id="3b3db-128">elementi di SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="3b3db-128">items in SharePoint Online</span></span>         |<span data-ttu-id="3b3db-129">sì</span><span class="sxs-lookup"><span data-stu-id="3b3db-129">yes</span></span>         |<span data-ttu-id="3b3db-130">sì</span><span class="sxs-lookup"><span data-stu-id="3b3db-130">yes</span></span>         |
|<span data-ttu-id="3b3db-131">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="3b3db-131">OneDrive for Business</span></span>     |<span data-ttu-id="3b3db-132">elementi</span><span class="sxs-lookup"><span data-stu-id="3b3db-132">items</span></span>         |<span data-ttu-id="3b3db-133">sì</span><span class="sxs-lookup"><span data-stu-id="3b3db-133">yes</span></span>         |<span data-ttu-id="3b3db-134">sì</span><span class="sxs-lookup"><span data-stu-id="3b3db-134">yes</span></span>         |
|<span data-ttu-id="3b3db-135">Teams</span><span class="sxs-lookup"><span data-stu-id="3b3db-135">Teams</span></span>     |<span data-ttu-id="3b3db-136">Messaggi di Teams e dei canali</span><span class="sxs-lookup"><span data-stu-id="3b3db-136">Teams and channel messages</span></span>         |<span data-ttu-id="3b3db-137">non applicabile</span><span class="sxs-lookup"><span data-stu-id="3b3db-137">not applicable</span></span>         |<span data-ttu-id="3b3db-138">non applicabile</span><span class="sxs-lookup"><span data-stu-id="3b3db-138">not applicable</span></span>         |
|<span data-ttu-id="3b3db-139">Teams</span><span class="sxs-lookup"><span data-stu-id="3b3db-139">Teams</span></span>     |<span data-ttu-id="3b3db-140">allegati</span><span class="sxs-lookup"><span data-stu-id="3b3db-140">attachments</span></span>         |<span data-ttu-id="3b3db-141">sì \*\*</span><span class="sxs-lookup"><span data-stu-id="3b3db-141">yes \*\*</span></span>         |<span data-ttu-id="3b3db-142">sì \*\*</span><span class="sxs-lookup"><span data-stu-id="3b3db-142">yes \*\*</span></span>         |
|<span data-ttu-id="3b3db-143">Dispositivi Windows 10</span><span class="sxs-lookup"><span data-stu-id="3b3db-143">Windows 10 devices</span></span>     |<span data-ttu-id="3b3db-144">elementi</span><span class="sxs-lookup"><span data-stu-id="3b3db-144">items</span></span>         |<span data-ttu-id="3b3db-145">sì</span><span class="sxs-lookup"><span data-stu-id="3b3db-145">yes</span></span>         |<span data-ttu-id="3b3db-146">sì</span><span class="sxs-lookup"><span data-stu-id="3b3db-146">yes</span></span>         |
|<span data-ttu-id="3b3db-147">MCAS (anteprima)</span><span class="sxs-lookup"><span data-stu-id="3b3db-147">MCAS (preview)</span></span> |<span data-ttu-id="3b3db-148">elementi</span><span class="sxs-lookup"><span data-stu-id="3b3db-148">items</span></span>         |<span data-ttu-id="3b3db-149">sì</span><span class="sxs-lookup"><span data-stu-id="3b3db-149">yes</span></span>         |<span data-ttu-id="3b3db-150">sì</span><span class="sxs-lookup"><span data-stu-id="3b3db-150">yes</span></span>         |

<span data-ttu-id="3b3db-151">\* Il rilevamento dei criteri di prevenzione della perdita dei dati e l'applicazione delle etichette di riservatezza nei messaggi di posta elettronica e negli allegati sono supportati durante il trasferimento.</span><span class="sxs-lookup"><span data-stu-id="3b3db-151">\* DLP detection and enforcement of sensitivity labels on emails and attachments are supported in-transit.</span></span> <span data-ttu-id="3b3db-152">I suggerimenti per i criteri di prevenzione della perdita dei dati per le etichette di riservatezza degli allegati dei messaggi non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="3b3db-152">DLP policy tips of sensitivity labeled email attachments are not.</span></span>

<span data-ttu-id="3b3db-153">\*\* Gli allegati inviati in Teams tramite chat individuali o canali sono caricati automaticamente su OneDrive for Business e SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3b3db-153">\*\* Attachments sent in Teams over 1:1 chat or channels are automatically uploaded to OneDrive for Business and SharePoint.</span></span> <span data-ttu-id="3b3db-154">Perciò, se SharePoint Online o OneDrive for Business sono inclusi come posizioni del criteri di prevenzione della perdita dei dati, gli allegati etichettai inviati in Teams saranno inclusi automaticamente nell'ambito di questa condizione.</span><span class="sxs-lookup"><span data-stu-id="3b3db-154">So if SharePoint Online or OneDrive for Business are included as locations in your DLP policy, then labeled attachments sent in Teams will be automatically included in the scope of this condition.</span></span> <span data-ttu-id="3b3db-155">Teams non deve essere selezionato come posizione nel criteri di prevenzione della perdita dei dati.</span><span class="sxs-lookup"><span data-stu-id="3b3db-155">Teams as a location does not need to be selected in the DLP policy.</span></span>

### <a name="supported-scenarios"></a><span data-ttu-id="3b3db-156">Scenari supportati</span><span class="sxs-lookup"><span data-stu-id="3b3db-156">Supported scenarios</span></span>

- <span data-ttu-id="3b3db-157">L'amministratore per la prevenzione della perdita dei dati sarà in grado di accedere a un elenco di tutte le etichette di conservazione del tenant quando sceglie di includere una o più etichette di riservatezza come condizioni.</span><span class="sxs-lookup"><span data-stu-id="3b3db-157">DLP Admin will be able to see a list of all sensitivity labels in the tenant when they choose to include one or more sensitivity labels as a condition.</span></span>

- <span data-ttu-id="3b3db-158">L'uso delle etichette di riservatezza come condizioni è supportato in tutti i carichi di lavoro, come indicato nella matrice di supporto precedente.</span><span class="sxs-lookup"><span data-stu-id="3b3db-158">Using sensitivity labels as a condition is supported across all workloads as indicated in the support matrix above.</span></span>

- <span data-ttu-id="3b3db-159">I suggerimenti per i criteri di prevenzione della perdita dei dati continuano a essere visualizzati in tutti i carichi di lavoro (salvo quelli di Outlook Win32) per i criteri di prevenzione che contengono etichette di riservatezza come condizioni.</span><span class="sxs-lookup"><span data-stu-id="3b3db-159">DLP policy tips will continue to be shown across workloads (except Outlook Win32) for DLP policies which contain sensitivity label as a condition.</span></span>

- <span data-ttu-id="3b3db-160">Le etichette di riservatezza sono visualizzate anche all'interno del messaggio di posta elettronica del report degli incidenti, se c'è una corrispondenza con un criterio di prevenzione della perdita dei dati con etichette di riservatezza come condizioni. </span><span class="sxs-lookup"><span data-stu-id="3b3db-160">Sensitivity labels will also appear as a part of the incident report email if a DLP policy with sensitivity label as a condition is matched.</span></span>

- <span data-ttu-id="3b3db-161">I dettagli dell'etichetta di riservatezza sono mostrati anche nel log di controllo della corrispondenza delle regole di prevenzione della perdita dei dati, in caso di corrispondenza con criteri di prevenzione che contengono etichette di riservatezza come condizioni.</span><span class="sxs-lookup"><span data-stu-id="3b3db-161">Sensitivity label details will also be shown in the DLP rule match audit log for a DLP policy match which contains sensitivity label as a condition.</span></span>


### <a name="support-policy-tips"></a><span data-ttu-id="3b3db-162">Supporto per i suggerimenti per i criteri</span><span class="sxs-lookup"><span data-stu-id="3b3db-162">Support policy tips</span></span>


|<span data-ttu-id="3b3db-163">Carico di lavoro</span><span class="sxs-lookup"><span data-stu-id="3b3db-163">Workload</span></span>  |<span data-ttu-id="3b3db-164">Suggerimenti per criteri supportati/non supportati</span><span class="sxs-lookup"><span data-stu-id="3b3db-164">Policy tips supported/not supported</span></span>  |
|---------|---------|
|<span data-ttu-id="3b3db-165">OWA</span><span class="sxs-lookup"><span data-stu-id="3b3db-165">OWA</span></span> |    <span data-ttu-id="3b3db-166">supportato</span><span class="sxs-lookup"><span data-stu-id="3b3db-166">supported</span></span>     |
|<span data-ttu-id="3b3db-167">Outlook Win 32</span><span class="sxs-lookup"><span data-stu-id="3b3db-167">Outlook Win 32</span></span>    |  <span data-ttu-id="3b3db-168">non supportato</span><span class="sxs-lookup"><span data-stu-id="3b3db-168">not supported</span></span>       |
|<span data-ttu-id="3b3db-169">SharePoint</span><span class="sxs-lookup"><span data-stu-id="3b3db-169">SharePoint</span></span>   |   <span data-ttu-id="3b3db-170">supportato</span><span class="sxs-lookup"><span data-stu-id="3b3db-170">supported</span></span>      |
|<span data-ttu-id="3b3db-171">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="3b3db-171">OneDrive for Business</span></span>    |    <span data-ttu-id="3b3db-172">supportato</span><span class="sxs-lookup"><span data-stu-id="3b3db-172">supported</span></span>     |
|<span data-ttu-id="3b3db-173">dispositivi endpoint</span><span class="sxs-lookup"><span data-stu-id="3b3db-173">endpoint devices</span></span>   |  <span data-ttu-id="3b3db-174">non supportato</span><span class="sxs-lookup"><span data-stu-id="3b3db-174">not supported</span></span>       |
