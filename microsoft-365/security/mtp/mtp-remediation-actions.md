---
title: Azioni di correzione che seguono indagini automatizzate in Microsoft Threat Protection
description: Ottenere una panoramica delle azioni correttive che seguono le indagini automatizzate in Microsoft Threat Protection
keywords: automatizzata, indagine, avviso, attivare, azione, correzione
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: ca0c557de24320692d903a1136fc434d635f0507
ms.sourcegitcommit: 58c1b4208a5e231463091573e40696d08fc39b8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2020
ms.locfileid: "42955592"
---
# <a name="remediation-actions-following-automated-investigations-in-microsoft-threat-protection"></a><span data-ttu-id="6f4d4-104">Azioni di correzione che seguono indagini automatizzate in Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="6f4d4-104">Remediation actions following automated investigations in Microsoft Threat Protection</span></span>

<span data-ttu-id="6f4d4-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="6f4d4-105">**Applies to:**</span></span>
- <span data-ttu-id="6f4d4-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="6f4d4-106">Microsoft Threat Protection</span></span>


## <a name="remediation-actions"></a><span data-ttu-id="6f4d4-107">Azioni correttive</span><span class="sxs-lookup"><span data-stu-id="6f4d4-107">Remediation actions</span></span>

<span data-ttu-id="6f4d4-108">Durante e dopo un'analisi automatizzata in Microsoft Threat Protection, le azioni di correzione vengono identificate per gli elementi dannosi o sospetti.</span><span class="sxs-lookup"><span data-stu-id="6f4d4-108">During and after an automated investigation in Microsoft Threat Protection, remediation actions are identified for malicious or suspicious items.</span></span> <span data-ttu-id="6f4d4-109">Alcuni tipi di azioni di correzione vengono eseguiti nei dispositivi, detti anche endpoint.</span><span class="sxs-lookup"><span data-stu-id="6f4d4-109">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="6f4d4-110">Altre azioni di correzione vengono eseguite sul contenuto della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="6f4d4-110">Other remediation actions are taken on email content.</span></span> <span data-ttu-id="6f4d4-111">Indagini automatizzate complete dopo che sono state apportate, approvate o rifiutate le azioni di correzione.</span><span class="sxs-lookup"><span data-stu-id="6f4d4-111">Automated investigations complete after remediation actions are taken, approved, or rejected.</span></span>

<span data-ttu-id="6f4d4-112">Nella tabella seguente sono riepilogate le azioni di correzione attualmente supportate in Microsoft Threat Protection:</span><span class="sxs-lookup"><span data-stu-id="6f4d4-112">The following table summarizes remediation actions that are currently supported in Microsoft Threat Protection:</span></span> 

|<span data-ttu-id="6f4d4-113">Azioni di correzione del dispositivo (endpoint)</span><span class="sxs-lookup"><span data-stu-id="6f4d4-113">Device (endpoint) remediation actions</span></span>  |<span data-ttu-id="6f4d4-114">Azioni correttive della posta elettronica</span><span class="sxs-lookup"><span data-stu-id="6f4d4-114">Email remediation actions</span></span>  |
|---------|---------|
|<span data-ttu-id="6f4d4-115">Quarantena del file</span><span class="sxs-lookup"><span data-stu-id="6f4d4-115">Quarantine file</span></span><br/><span data-ttu-id="6f4d4-116">Rimozione della chiave del Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="6f4d4-116">Remove registry key</span></span><br/><span data-ttu-id="6f4d4-117">Termine del processo</span><span class="sxs-lookup"><span data-stu-id="6f4d4-117">Kill process</span></span> <br/><span data-ttu-id="6f4d4-118">Interruzione del servizio</span><span class="sxs-lookup"><span data-stu-id="6f4d4-118">Stop service</span></span> <br/><span data-ttu-id="6f4d4-119">Disabilitazione del driver</span><span class="sxs-lookup"><span data-stu-id="6f4d4-119">Disable driver</span></span> <br/><span data-ttu-id="6f4d4-120">Rimozione di attività pianificate</span><span class="sxs-lookup"><span data-stu-id="6f4d4-120">Remove scheduled task</span></span>      |<span data-ttu-id="6f4d4-121">Eliminazione temporanea di messaggi di posta elettronica o cluster</span><span class="sxs-lookup"><span data-stu-id="6f4d4-121">Soft delete email messages or clusters</span></span><br/><span data-ttu-id="6f4d4-122">Blocco di URL (al momento del clic)</span><span class="sxs-lookup"><span data-stu-id="6f4d4-122">Block URL (time-of-click)</span></span><br/><span data-ttu-id="6f4d4-123">Disattivazione dell'inoltro della posta elettronica esterna</span><span class="sxs-lookup"><span data-stu-id="6f4d4-123">Turn off external mail forwarding</span></span>          |

<span data-ttu-id="6f4d4-124">Le azioni di correzione, sia che siano in attesa di approvazione o che sono già complete, possono essere visualizzate nel [Centro azioni](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span><span class="sxs-lookup"><span data-stu-id="6f4d4-124">Remediation actions, whether they're pending approval or are already complete, can be viewed in the [Action Center](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span></span>

## <a name="remediation-actions-follow-automated-investigations"></a><span data-ttu-id="6f4d4-125">Le azioni correttive seguono indagini automatizzate</span><span class="sxs-lookup"><span data-stu-id="6f4d4-125">Remediation actions follow automated investigations</span></span>

<span data-ttu-id="6f4d4-126">Una volta completata un'indagine automatizzata, viene emesso un verdetto per ogni prova inclusa e vengono identificate le azioni correttive.</span><span class="sxs-lookup"><span data-stu-id="6f4d4-126">When an automated investigation completes, a verdict is reached for every piece of evidence involved, and remediation actions are identified.</span></span> <span data-ttu-id="6f4d4-127">In alcuni casi, le azioni correttive vengono eseguite automaticamente; in altri casi, invece, è necessario approvarle.</span><span class="sxs-lookup"><span data-stu-id="6f4d4-127">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="6f4d4-128">Nella tabella seguente sono elencati i possibili verdetti e i risultati:</span><span class="sxs-lookup"><span data-stu-id="6f4d4-128">The following table lists possible verdicts and outcomes:</span></span>

|<span data-ttu-id="6f4d4-129">Verdetto</span><span class="sxs-lookup"><span data-stu-id="6f4d4-129">Verdict</span></span>    |<span data-ttu-id="6f4d4-130">Area</span><span class="sxs-lookup"><span data-stu-id="6f4d4-130">Area</span></span>    |<span data-ttu-id="6f4d4-131">Risultati</span><span class="sxs-lookup"><span data-stu-id="6f4d4-131">Outcomes</span></span>|
|------|------|------|
|<span data-ttu-id="6f4d4-132">Dannosa</span><span class="sxs-lookup"><span data-stu-id="6f4d4-132">Malicious</span></span>    |<span data-ttu-id="6f4d4-133">Dispositivi (endpoint)</span><span class="sxs-lookup"><span data-stu-id="6f4d4-133">Devices (endpoints)</span></span>    |<span data-ttu-id="6f4d4-134">Le azioni correttive vengono eseguite automaticamente</span><span class="sxs-lookup"><span data-stu-id="6f4d4-134">Remediation actions are taken automatically</span></span>|
|<span data-ttu-id="6f4d4-135">Dannosa</span><span class="sxs-lookup"><span data-stu-id="6f4d4-135">Malicious</span></span>    |<span data-ttu-id="6f4d4-136">Contenuto della posta elettronica (URL o allegati)</span><span class="sxs-lookup"><span data-stu-id="6f4d4-136">Email content (URLs or attachments)</span></span> | <span data-ttu-id="6f4d4-137">Le azioni correttive consigliate sono in attesa di approvazione</span><span class="sxs-lookup"><span data-stu-id="6f4d4-137">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="6f4d4-138">Sospetta</span><span class="sxs-lookup"><span data-stu-id="6f4d4-138">Suspicious</span></span>    |<span data-ttu-id="6f4d4-139">Dispositivi o contenuto della posta elettronica</span><span class="sxs-lookup"><span data-stu-id="6f4d4-139">Devices or email content</span></span> |<span data-ttu-id="6f4d4-140">Le azioni correttive consigliate sono in attesa di approvazione</span><span class="sxs-lookup"><span data-stu-id="6f4d4-140">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="6f4d4-141">Non sono state trovate minacce</span><span class="sxs-lookup"><span data-stu-id="6f4d4-141">No threats found</span></span>    |<span data-ttu-id="6f4d4-142">Dispositivi o contenuto della posta elettronica</span><span class="sxs-lookup"><span data-stu-id="6f4d4-142">Devices or email content</span></span>    |<span data-ttu-id="6f4d4-143">Non sono necessarie azioni correttive</span><span class="sxs-lookup"><span data-stu-id="6f4d4-143">No remediation actions are needed</span></span>|

[<span data-ttu-id="6f4d4-144">Rivedere un'azione in sospeso nel centro notifiche</span><span class="sxs-lookup"><span data-stu-id="6f4d4-144">Review a pending action in the Action center</span></span>](mtp-autoir-actions.md#review-a-pending-action-in-the-action-center)

> [!TIP]
> <span data-ttu-id="6f4d4-145">Se si pensa che qualcosa è stato perso o rilevato erroneamente dalle funzionalità di analisi e risposta automatizzate in Microsoft Threat Protection, fatecelo sapere!</span><span class="sxs-lookup"><span data-stu-id="6f4d4-145">If you think something was missed or wrongly detected by automated investigation and response features in Microsoft Threat Protection, let us know!</span></span> <span data-ttu-id="6f4d4-146">[Segnala falsi positivi/negativi](mtp-autoir-report-false-positives-negatives.md).</span><span class="sxs-lookup"><span data-stu-id="6f4d4-146">[Report false positives/negatives](mtp-autoir-report-false-positives-negatives.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="6f4d4-147">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="6f4d4-147">Next steps</span></span>

- [<span data-ttu-id="6f4d4-148">Approva o rifiuta azioni</span><span class="sxs-lookup"><span data-stu-id="6f4d4-148">Approve or reject actions</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)

- [<span data-ttu-id="6f4d4-149">Altre informazioni sul centro notifiche</span><span class="sxs-lookup"><span data-stu-id="6f4d4-149">Learn more about the Action center</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
