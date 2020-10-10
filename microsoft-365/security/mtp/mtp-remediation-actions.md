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
- m365-initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.date: 09/16/2020
ms.reviewer: evaldm, isco
ms.openlocfilehash: 5f6e7a1a3f9c19a0ecfdca922505d2b27ad466c6
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412311"
---
# <a name="remediation-actions-following-automated-investigations-in-microsoft-threat-protection"></a><span data-ttu-id="f6c1b-104">Azioni di correzione che seguono indagini automatizzate in Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="f6c1b-104">Remediation actions following automated investigations in Microsoft Threat Protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f6c1b-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="f6c1b-105">**Applies to:**</span></span>
- <span data-ttu-id="f6c1b-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="f6c1b-106">Microsoft Threat Protection</span></span>


## <a name="remediation-actions"></a><span data-ttu-id="f6c1b-107">Azioni correttive</span><span class="sxs-lookup"><span data-stu-id="f6c1b-107">Remediation actions</span></span>

<span data-ttu-id="f6c1b-108">Durante e dopo un'analisi automatizzata in Microsoft Threat Protection, le azioni di correzione vengono identificate per gli elementi dannosi o sospetti.</span><span class="sxs-lookup"><span data-stu-id="f6c1b-108">During and after an automated investigation in Microsoft Threat Protection, remediation actions are identified for malicious or suspicious items.</span></span> <span data-ttu-id="f6c1b-109">Alcuni tipi di azioni di correzione vengono eseguiti nei dispositivi, detti anche endpoint.</span><span class="sxs-lookup"><span data-stu-id="f6c1b-109">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="f6c1b-110">Altre azioni di correzione vengono eseguite sul contenuto della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="f6c1b-110">Other remediation actions are taken on email content.</span></span> <span data-ttu-id="f6c1b-111">Indagini automatizzate complete dopo che sono state apportate, approvate o rifiutate le azioni di correzione.</span><span class="sxs-lookup"><span data-stu-id="f6c1b-111">Automated investigations complete after remediation actions are taken, approved, or rejected.</span></span>

<span data-ttu-id="f6c1b-112">Nella tabella seguente sono riepilogate le azioni di correzione attualmente supportate in Microsoft Threat Protection:</span><span class="sxs-lookup"><span data-stu-id="f6c1b-112">The following table summarizes remediation actions that are currently supported in Microsoft Threat Protection:</span></span> 

|<span data-ttu-id="f6c1b-113">Azioni di correzione del dispositivo (endpoint)</span><span class="sxs-lookup"><span data-stu-id="f6c1b-113">Device (endpoint) remediation actions</span></span>  |<span data-ttu-id="f6c1b-114">Azioni correttive della posta elettronica</span><span class="sxs-lookup"><span data-stu-id="f6c1b-114">Email remediation actions</span></span>  |
|---------|---------|
|<span data-ttu-id="f6c1b-115">-Raccogliere il pacchetto di indagine</span><span class="sxs-lookup"><span data-stu-id="f6c1b-115">- Collect investigation package</span></span> <br/><span data-ttu-id="f6c1b-116">-Isolate Device (questa azione può essere annullata)</span><span class="sxs-lookup"><span data-stu-id="f6c1b-116">- Isolate device (this action can be undone)</span></span><br/><span data-ttu-id="f6c1b-117">-Trasferisce Machine</span><span class="sxs-lookup"><span data-stu-id="f6c1b-117">- Offboard machine</span></span> <br/><span data-ttu-id="f6c1b-118">-Esecuzione del codice di rilascio</span><span class="sxs-lookup"><span data-stu-id="f6c1b-118">- Release code execution</span></span> <br/><span data-ttu-id="f6c1b-119">-Rilascio dalla quarantena</span><span class="sxs-lookup"><span data-stu-id="f6c1b-119">- Release from quarantine</span></span> <br/><span data-ttu-id="f6c1b-120">-Esempio di richiesta</span><span class="sxs-lookup"><span data-stu-id="f6c1b-120">- Request sample</span></span> <br/><span data-ttu-id="f6c1b-121">-Limitare l'esecuzione del codice (questa azione può essere annullata)</span><span class="sxs-lookup"><span data-stu-id="f6c1b-121">- Restrict code execution (this action can be undone)</span></span> <br/><span data-ttu-id="f6c1b-122">-Eseguire l'analisi antivirus</span><span class="sxs-lookup"><span data-stu-id="f6c1b-122">- Run antivirus scan</span></span> <br/><span data-ttu-id="f6c1b-123">-Arrestare e mettere in quarantena</span><span class="sxs-lookup"><span data-stu-id="f6c1b-123">- Stop and quarantine</span></span>      |<span data-ttu-id="f6c1b-124">-Blocca URL (tempo di clic)</span><span class="sxs-lookup"><span data-stu-id="f6c1b-124">- Block URL (time-of-click)</span></span><br/><span data-ttu-id="f6c1b-125">-Eliminare i messaggi di posta elettronica o i cluster</span><span class="sxs-lookup"><span data-stu-id="f6c1b-125">- Soft delete email messages or clusters</span></span><br/><span data-ttu-id="f6c1b-126">-Posta in quarantena</span><span class="sxs-lookup"><span data-stu-id="f6c1b-126">- Quarantine email</span></span><br/><span data-ttu-id="f6c1b-127">-Mettere in quarantena un allegato di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="f6c1b-127">- Quarantine an email attachment</span></span><br/><span data-ttu-id="f6c1b-128">-Disattivare l'inoltro della posta esterna</span><span class="sxs-lookup"><span data-stu-id="f6c1b-128">- Turn off external mail forwarding</span></span>          |

<span data-ttu-id="f6c1b-129">Le azioni di correzione, sia che si tratti di approvazione in sospeso o che sono già state completate, possono essere visualizzate nel [Centro azioni](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span><span class="sxs-lookup"><span data-stu-id="f6c1b-129">Remediation actions, whether pending approval or already complete, can be viewed in the [Action Center](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span></span>

## <a name="remediation-actions-follow-automated-investigations"></a><span data-ttu-id="f6c1b-130">Le azioni correttive seguono indagini automatizzate</span><span class="sxs-lookup"><span data-stu-id="f6c1b-130">Remediation actions follow automated investigations</span></span>

<span data-ttu-id="f6c1b-131">Al termine di un'indagine automatizzata, viene raggiunto un verdetto per ogni elemento di prova coinvolto.</span><span class="sxs-lookup"><span data-stu-id="f6c1b-131">When an automated investigation completes, a verdict is reached for every piece of evidence involved.</span></span> <span data-ttu-id="f6c1b-132">A seconda del verdetto, vengono identificate le azioni di correzione.</span><span class="sxs-lookup"><span data-stu-id="f6c1b-132">Depending on the verdict, remediation actions are identified.</span></span> <span data-ttu-id="f6c1b-133">In alcuni casi, le azioni correttive vengono eseguite automaticamente; in altri casi, invece, è necessario approvarle.</span><span class="sxs-lookup"><span data-stu-id="f6c1b-133">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="f6c1b-134">Tutto dipende da come [viene configurata l'analisi e la risposta automatizzata](mtp-configure-auto-investigation-response.md).</span><span class="sxs-lookup"><span data-stu-id="f6c1b-134">It all depends on how [automated investigation and response is configured](mtp-configure-auto-investigation-response.md).</span></span>

<span data-ttu-id="f6c1b-135">Nella tabella seguente sono elencati i possibili verdetti e i risultati:</span><span class="sxs-lookup"><span data-stu-id="f6c1b-135">The following table lists possible verdicts and outcomes:</span></span>

|<span data-ttu-id="f6c1b-136">Verdetto</span><span class="sxs-lookup"><span data-stu-id="f6c1b-136">Verdict</span></span>    |<span data-ttu-id="f6c1b-137">Area</span><span class="sxs-lookup"><span data-stu-id="f6c1b-137">Area</span></span>    |<span data-ttu-id="f6c1b-138">Risultati</span><span class="sxs-lookup"><span data-stu-id="f6c1b-138">Outcomes</span></span>|
|------|------|------|
|<span data-ttu-id="f6c1b-139">Dannosa</span><span class="sxs-lookup"><span data-stu-id="f6c1b-139">Malicious</span></span>    |<span data-ttu-id="f6c1b-140">Dispositivi (endpoint)</span><span class="sxs-lookup"><span data-stu-id="f6c1b-140">Devices (endpoints)</span></span>    |<span data-ttu-id="f6c1b-141">Le azioni di correzione vengono eseguite automaticamente (presupponendo che i [gruppi di dispositivi](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) dell'organizzazione siano impostati automaticamente su **minacce complete**)</span><span class="sxs-lookup"><span data-stu-id="f6c1b-141">Remediation actions are taken automatically (assuming your organization's [device groups](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) are set to **Full - remediate threats automatically**)</span></span>|
|<span data-ttu-id="f6c1b-142">Dannosa</span><span class="sxs-lookup"><span data-stu-id="f6c1b-142">Malicious</span></span>    |<span data-ttu-id="f6c1b-143">Contenuto della posta elettronica (URL o allegati)</span><span class="sxs-lookup"><span data-stu-id="f6c1b-143">Email content (URLs or attachments)</span></span> | <span data-ttu-id="f6c1b-144">Le azioni correttive consigliate sono in attesa di approvazione</span><span class="sxs-lookup"><span data-stu-id="f6c1b-144">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="f6c1b-145">Sospetta</span><span class="sxs-lookup"><span data-stu-id="f6c1b-145">Suspicious</span></span>    |<span data-ttu-id="f6c1b-146">Dispositivi o contenuto della posta elettronica</span><span class="sxs-lookup"><span data-stu-id="f6c1b-146">Devices or email content</span></span> |<span data-ttu-id="f6c1b-147">Le azioni correttive consigliate sono in attesa di approvazione</span><span class="sxs-lookup"><span data-stu-id="f6c1b-147">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="f6c1b-148">Non sono state trovate minacce</span><span class="sxs-lookup"><span data-stu-id="f6c1b-148">No threats found</span></span>    |<span data-ttu-id="f6c1b-149">Dispositivi o contenuto della posta elettronica</span><span class="sxs-lookup"><span data-stu-id="f6c1b-149">Devices or email content</span></span>    |<span data-ttu-id="f6c1b-150">Non sono necessarie azioni correttive</span><span class="sxs-lookup"><span data-stu-id="f6c1b-150">No remediation actions are needed</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="f6c1b-151">Se le azioni di correzione vengono eseguite automaticamente o solo dopo l'approvazione dipendono da determinate impostazioni, ad esempio i criteri di gruppo per i dispositivi dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f6c1b-151">Whether remediation actions are taken automatically or only upon approval depends on certain settings, such as your organization's device group policies.</span></span> <span data-ttu-id="f6c1b-152">Per ulteriori informazioni, vedere gli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="f6c1b-152">To learn more, see the following articles:</span></span>
> - [<span data-ttu-id="f6c1b-153">Configurare le funzionalità di analisi e risposta automatizzate in Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="f6c1b-153">Configure automated investigation and response capabilities in Microsoft Threat Protection</span></span>](mtp-configure-auto-investigation-response.md)
> - [<span data-ttu-id="f6c1b-154">Come vengono risolte le minacce nei dispositivi</span><span class="sxs-lookup"><span data-stu-id="f6c1b-154">How threats are remediated on devices</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

## <a name="next-steps"></a><span data-ttu-id="f6c1b-155">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="f6c1b-155">Next steps</span></span>

- [<span data-ttu-id="f6c1b-156">Visita il Centro notifiche</span><span class="sxs-lookup"><span data-stu-id="f6c1b-156">Visit the Action center</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
- [<span data-ttu-id="f6c1b-157">Approvare o rifiutare azioni in sospeso</span><span class="sxs-lookup"><span data-stu-id="f6c1b-157">Approve or reject pending actions</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)
- [<span data-ttu-id="f6c1b-158">Gestire i falsi positivi/negativi nelle funzionalità di analisi e risposta automatizzate</span><span class="sxs-lookup"><span data-stu-id="f6c1b-158">Handle false positives/negatives in automated investigation and response capabilities</span></span>](mtp-autoir-report-false-positives-negatives.md)
