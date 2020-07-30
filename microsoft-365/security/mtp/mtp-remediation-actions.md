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
ms.openlocfilehash: e0f76f6a232edeac350d08eeeb47188535ffe688
ms.sourcegitcommit: 1b83b6bcacb997324bc4be355deba6daf319591d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/28/2020
ms.locfileid: "46502938"
---
# <a name="remediation-actions-following-automated-investigations-in-microsoft-threat-protection"></a><span data-ttu-id="6a5d1-104">Azioni di correzione che seguono indagini automatizzate in Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="6a5d1-104">Remediation actions following automated investigations in Microsoft Threat Protection</span></span>

<span data-ttu-id="6a5d1-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="6a5d1-105">**Applies to:**</span></span>
- <span data-ttu-id="6a5d1-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="6a5d1-106">Microsoft Threat Protection</span></span>


## <a name="remediation-actions"></a><span data-ttu-id="6a5d1-107">Azioni correttive</span><span class="sxs-lookup"><span data-stu-id="6a5d1-107">Remediation actions</span></span>

<span data-ttu-id="6a5d1-108">Durante e dopo un'analisi automatizzata in Microsoft Threat Protection, le azioni di correzione vengono identificate per gli elementi dannosi o sospetti.</span><span class="sxs-lookup"><span data-stu-id="6a5d1-108">During and after an automated investigation in Microsoft Threat Protection, remediation actions are identified for malicious or suspicious items.</span></span> <span data-ttu-id="6a5d1-109">Alcuni tipi di azioni di correzione vengono eseguiti nei dispositivi, detti anche endpoint.</span><span class="sxs-lookup"><span data-stu-id="6a5d1-109">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="6a5d1-110">Altre azioni di correzione vengono eseguite sul contenuto della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="6a5d1-110">Other remediation actions are taken on email content.</span></span> <span data-ttu-id="6a5d1-111">Indagini automatizzate complete dopo che sono state apportate, approvate o rifiutate le azioni di correzione.</span><span class="sxs-lookup"><span data-stu-id="6a5d1-111">Automated investigations complete after remediation actions are taken, approved, or rejected.</span></span>

<span data-ttu-id="6a5d1-112">Nella tabella seguente sono riepilogate le azioni di correzione attualmente supportate in Microsoft Threat Protection:</span><span class="sxs-lookup"><span data-stu-id="6a5d1-112">The following table summarizes remediation actions that are currently supported in Microsoft Threat Protection:</span></span> 

|<span data-ttu-id="6a5d1-113">Azioni di correzione del dispositivo (endpoint)</span><span class="sxs-lookup"><span data-stu-id="6a5d1-113">Device (endpoint) remediation actions</span></span>  |<span data-ttu-id="6a5d1-114">Azioni correttive della posta elettronica</span><span class="sxs-lookup"><span data-stu-id="6a5d1-114">Email remediation actions</span></span>  |
|---------|---------|
|<span data-ttu-id="6a5d1-115">-Raccogliere il pacchetto di indagine</span><span class="sxs-lookup"><span data-stu-id="6a5d1-115">- Collect investigation package</span></span> <br/><span data-ttu-id="6a5d1-116">-Isolate Device (questa azione può essere annullata)</span><span class="sxs-lookup"><span data-stu-id="6a5d1-116">- Isolate device (this action can be undone)</span></span><br/><span data-ttu-id="6a5d1-117">-Trasferisce Machine</span><span class="sxs-lookup"><span data-stu-id="6a5d1-117">- Offboard machine</span></span> <br/><span data-ttu-id="6a5d1-118">-Esecuzione del codice di rilascio</span><span class="sxs-lookup"><span data-stu-id="6a5d1-118">- Release code execution</span></span> <br/><span data-ttu-id="6a5d1-119">-Rilascio dalla quarantena</span><span class="sxs-lookup"><span data-stu-id="6a5d1-119">- Release from quarantine</span></span> <br/><span data-ttu-id="6a5d1-120">-Esempio di richiesta</span><span class="sxs-lookup"><span data-stu-id="6a5d1-120">- Request sample</span></span> <br/><span data-ttu-id="6a5d1-121">-Limitare l'esecuzione del codice (questa azione può essere annullata)</span><span class="sxs-lookup"><span data-stu-id="6a5d1-121">- Restrict code execution (this action can be undone)</span></span> <br/><span data-ttu-id="6a5d1-122">-Eseguire l'analisi antivirus</span><span class="sxs-lookup"><span data-stu-id="6a5d1-122">- Run antivirus scan</span></span> <br/><span data-ttu-id="6a5d1-123">-Arrestare e mettere in quarantena</span><span class="sxs-lookup"><span data-stu-id="6a5d1-123">- Stop and quarantine</span></span>      |<span data-ttu-id="6a5d1-124">-Blocca URL (tempo di clic)</span><span class="sxs-lookup"><span data-stu-id="6a5d1-124">- Block URL (time-of-click)</span></span><br/><span data-ttu-id="6a5d1-125">-Eliminare i messaggi di posta elettronica o i cluster</span><span class="sxs-lookup"><span data-stu-id="6a5d1-125">- Soft delete email messages or clusters</span></span><br/><span data-ttu-id="6a5d1-126">-Posta in quarantena</span><span class="sxs-lookup"><span data-stu-id="6a5d1-126">- Quarantine email</span></span><br/><span data-ttu-id="6a5d1-127">-Mettere in quarantena un allegato di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="6a5d1-127">- Quarantine an email attachment</span></span><br/><span data-ttu-id="6a5d1-128">-Disattivare l'inoltro della posta esterna</span><span class="sxs-lookup"><span data-stu-id="6a5d1-128">- Turn off external mail forwarding</span></span>          |

<span data-ttu-id="6a5d1-129">Le azioni di correzione, sia che siano in attesa di approvazione o che sono già complete, possono essere visualizzate nel [Centro azioni](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span><span class="sxs-lookup"><span data-stu-id="6a5d1-129">Remediation actions, whether they're pending approval or are already complete, can be viewed in the [Action Center](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span></span>

## <a name="remediation-actions-follow-automated-investigations"></a><span data-ttu-id="6a5d1-130">Le azioni correttive seguono indagini automatizzate</span><span class="sxs-lookup"><span data-stu-id="6a5d1-130">Remediation actions follow automated investigations</span></span>

<span data-ttu-id="6a5d1-131">Una volta completata un'indagine automatizzata, viene emesso un verdetto per ogni prova inclusa e vengono identificate le azioni correttive.</span><span class="sxs-lookup"><span data-stu-id="6a5d1-131">When an automated investigation completes, a verdict is reached for every piece of evidence involved, and remediation actions are identified.</span></span> <span data-ttu-id="6a5d1-132">In alcuni casi, le azioni correttive vengono eseguite automaticamente; in altri casi, invece, è necessario approvarle.</span><span class="sxs-lookup"><span data-stu-id="6a5d1-132">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="6a5d1-133">Nella tabella seguente sono elencati i possibili verdetti e i risultati:</span><span class="sxs-lookup"><span data-stu-id="6a5d1-133">The following table lists possible verdicts and outcomes:</span></span>

|<span data-ttu-id="6a5d1-134">Verdetto</span><span class="sxs-lookup"><span data-stu-id="6a5d1-134">Verdict</span></span>    |<span data-ttu-id="6a5d1-135">Area</span><span class="sxs-lookup"><span data-stu-id="6a5d1-135">Area</span></span>    |<span data-ttu-id="6a5d1-136">Risultati</span><span class="sxs-lookup"><span data-stu-id="6a5d1-136">Outcomes</span></span>|
|------|------|------|
|<span data-ttu-id="6a5d1-137">Dannosa</span><span class="sxs-lookup"><span data-stu-id="6a5d1-137">Malicious</span></span>    |<span data-ttu-id="6a5d1-138">Dispositivi (endpoint)</span><span class="sxs-lookup"><span data-stu-id="6a5d1-138">Devices (endpoints)</span></span>    |<span data-ttu-id="6a5d1-139">Le azioni correttive vengono eseguite automaticamente</span><span class="sxs-lookup"><span data-stu-id="6a5d1-139">Remediation actions are taken automatically</span></span>|
|<span data-ttu-id="6a5d1-140">Dannosa</span><span class="sxs-lookup"><span data-stu-id="6a5d1-140">Malicious</span></span>    |<span data-ttu-id="6a5d1-141">Contenuto della posta elettronica (URL o allegati)</span><span class="sxs-lookup"><span data-stu-id="6a5d1-141">Email content (URLs or attachments)</span></span> | <span data-ttu-id="6a5d1-142">Le azioni correttive consigliate sono in attesa di approvazione</span><span class="sxs-lookup"><span data-stu-id="6a5d1-142">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="6a5d1-143">Sospetta</span><span class="sxs-lookup"><span data-stu-id="6a5d1-143">Suspicious</span></span>    |<span data-ttu-id="6a5d1-144">Dispositivi o contenuto della posta elettronica</span><span class="sxs-lookup"><span data-stu-id="6a5d1-144">Devices or email content</span></span> |<span data-ttu-id="6a5d1-145">Le azioni correttive consigliate sono in attesa di approvazione</span><span class="sxs-lookup"><span data-stu-id="6a5d1-145">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="6a5d1-146">Non sono state trovate minacce</span><span class="sxs-lookup"><span data-stu-id="6a5d1-146">No threats found</span></span>    |<span data-ttu-id="6a5d1-147">Dispositivi o contenuto della posta elettronica</span><span class="sxs-lookup"><span data-stu-id="6a5d1-147">Devices or email content</span></span>    |<span data-ttu-id="6a5d1-148">Non sono necessarie azioni correttive</span><span class="sxs-lookup"><span data-stu-id="6a5d1-148">No remediation actions are needed</span></span>|

[<span data-ttu-id="6a5d1-149">Rivedere un'azione in sospeso nel centro notifiche</span><span class="sxs-lookup"><span data-stu-id="6a5d1-149">Review a pending action in the Action center</span></span>](mtp-autoir-actions.md#review-a-pending-action-in-the-action-center)

> [!TIP]
> <span data-ttu-id="6a5d1-150">Se si pensa che qualcosa è stato perso o rilevato erroneamente dalle funzionalità di analisi e risposta automatizzate in Microsoft Threat Protection, fatecelo sapere!</span><span class="sxs-lookup"><span data-stu-id="6a5d1-150">If you think something was missed or wrongly detected by automated investigation and response features in Microsoft Threat Protection, let us know!</span></span> <span data-ttu-id="6a5d1-151">[Segnala falsi positivi/negativi](mtp-autoir-report-false-positives-negatives.md).</span><span class="sxs-lookup"><span data-stu-id="6a5d1-151">[Report false positives/negatives](mtp-autoir-report-false-positives-negatives.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="6a5d1-152">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="6a5d1-152">Next steps</span></span>

- [<span data-ttu-id="6a5d1-153">Approva o rifiuta azioni</span><span class="sxs-lookup"><span data-stu-id="6a5d1-153">Approve or reject actions</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)

- [<span data-ttu-id="6a5d1-154">Altre informazioni sul centro notifiche</span><span class="sxs-lookup"><span data-stu-id="6a5d1-154">Learn more about the Action center</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
