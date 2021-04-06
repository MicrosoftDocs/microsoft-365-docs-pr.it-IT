---
title: Azioni di correzione in Microsoft 365 Defender
description: Panoramica delle azioni di correzione che seguono indagini automatizzate in Microsoft 365 Defender
keywords: automatizzata, indagine, avviso, attivare, azione, correzione
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: 41d8b91cbc905da982f8a344392398635f8d3632
ms.sourcegitcommit: e0a96e08b7dc29e074065e69a2a86fc3cf0dad01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/06/2021
ms.locfileid: "51591853"
---
# <a name="remediation-actions-in-microsoft-365-defender"></a><span data-ttu-id="13cc8-104">Azioni di correzione in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="13cc8-104">Remediation actions in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="13cc8-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="13cc8-105">**Applies to:**</span></span>
- <span data-ttu-id="13cc8-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="13cc8-106">Microsoft 365 Defender</span></span>

## <a name="remediation-actions"></a><span data-ttu-id="13cc8-107">Azioni correttive</span><span class="sxs-lookup"><span data-stu-id="13cc8-107">Remediation actions</span></span>

<span data-ttu-id="13cc8-108">Durante e dopo un'indagine automatizzata in Microsoft 365 Defender, vengono identificate azioni di correzione per elementi dannosi o sospetti.</span><span class="sxs-lookup"><span data-stu-id="13cc8-108">During and after an automated investigation in Microsoft 365 Defender, remediation actions are identified for malicious or suspicious items.</span></span> <span data-ttu-id="13cc8-109">Alcuni tipi di azioni di correzione vengono eseguite nei dispositivi, definiti anche endpoint.</span><span class="sxs-lookup"><span data-stu-id="13cc8-109">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="13cc8-110">Altre azioni di correzione vengono eseguite sul contenuto della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="13cc8-110">Other remediation actions are taken on email content.</span></span> <span data-ttu-id="13cc8-111">Le indagini automatizzate vengono completate dopo l'esecuzione, l'approvazione o il rifiuto di azioni correttive.</span><span class="sxs-lookup"><span data-stu-id="13cc8-111">Automated investigations complete after remediation actions are taken, approved, or rejected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="13cc8-112">Il fatto che le azioni di correzione siano eseguite automaticamente o solo dopo l'approvazione dipende da determinate impostazioni, ad esempio il modo in cui i livelli di automazione.</span><span class="sxs-lookup"><span data-stu-id="13cc8-112">Whether remediation actions are taken automatically or only upon approval depends on certain settings, such as how automation levels.</span></span> <span data-ttu-id="13cc8-113">Per ulteriori informazioni, vedere gli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="13cc8-113">To learn more, see the following articles:</span></span>
> - [<span data-ttu-id="13cc8-114">Configurare le funzionalità di analisi e risposta automatizzate in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="13cc8-114">Configure your automated investigation and response capabilities in Microsoft 365 Defender</span></span>](m365d-configure-auto-investigation-response.md)
> - [<span data-ttu-id="13cc8-115">Modalità di correzione delle minacce nei dispositivi</span><span class="sxs-lookup"><span data-stu-id="13cc8-115">How threats are remediated on devices</span></span>](../defender-endpoint/automated-investigations.md)
> - [<span data-ttu-id="13cc8-116">Minacce e azioni di correzione sui contenuti di collaborazione & posta elettronica</span><span class="sxs-lookup"><span data-stu-id="13cc8-116">Threats and remediation actions on email & collaboration content</span></span>](../office-365-security/air-remediation-actions.md#threats-and-remediation-actions)

<span data-ttu-id="13cc8-117">Nella tabella seguente sono riepilogate le azioni di correzione attualmente supportate in Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="13cc8-117">The following table summarizes remediation actions that are currently supported in Microsoft 365 Defender:</span></span> 

|<span data-ttu-id="13cc8-118">Azioni di correzione del dispositivo (endpoint)</span><span class="sxs-lookup"><span data-stu-id="13cc8-118">Device (endpoint) remediation actions</span></span>  |<span data-ttu-id="13cc8-119">Azioni correttive della posta elettronica</span><span class="sxs-lookup"><span data-stu-id="13cc8-119">Email remediation actions</span></span>  |
|:---------|:---------|
|<span data-ttu-id="13cc8-120">- Raccogliere il pacchetto di indagine</span><span class="sxs-lookup"><span data-stu-id="13cc8-120">- Collect investigation package</span></span> <br/><span data-ttu-id="13cc8-121">- Isolare il dispositivo (questa azione può essere annullata)</span><span class="sxs-lookup"><span data-stu-id="13cc8-121">- Isolate device (this action can be undone)</span></span><br/><span data-ttu-id="13cc8-122">- Computer offboard</span><span class="sxs-lookup"><span data-stu-id="13cc8-122">- Offboard machine</span></span> <br/><span data-ttu-id="13cc8-123">- Esecuzione del codice di rilascio</span><span class="sxs-lookup"><span data-stu-id="13cc8-123">- Release code execution</span></span> <br/><span data-ttu-id="13cc8-124">- Rilascio dalla quarantena</span><span class="sxs-lookup"><span data-stu-id="13cc8-124">- Release from quarantine</span></span> <br/><span data-ttu-id="13cc8-125">- Esempio di richiesta</span><span class="sxs-lookup"><span data-stu-id="13cc8-125">- Request sample</span></span> <br/><span data-ttu-id="13cc8-126">- Limitare l'esecuzione del codice (questa azione può essere annullata)</span><span class="sxs-lookup"><span data-stu-id="13cc8-126">- Restrict code execution (this action can be undone)</span></span> <br/><span data-ttu-id="13cc8-127">- Eseguire l'analisi antivirus</span><span class="sxs-lookup"><span data-stu-id="13cc8-127">- Run antivirus scan</span></span> <br/><span data-ttu-id="13cc8-128">- Arrestare e mettere in quarantena</span><span class="sxs-lookup"><span data-stu-id="13cc8-128">- Stop and quarantine</span></span>      |<span data-ttu-id="13cc8-129">- URL di blocco (ora del clic)</span><span class="sxs-lookup"><span data-stu-id="13cc8-129">- Block URL (time-of-click)</span></span><br/><span data-ttu-id="13cc8-130">- Eliminazione recidiva dei messaggi di posta elettronica o dei cluster</span><span class="sxs-lookup"><span data-stu-id="13cc8-130">- Soft delete email messages or clusters</span></span><br/><span data-ttu-id="13cc8-131">- Posta elettronica in quarantena</span><span class="sxs-lookup"><span data-stu-id="13cc8-131">- Quarantine email</span></span><br/><span data-ttu-id="13cc8-132">- Mettere in quarantena un allegato di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="13cc8-132">- Quarantine an email attachment</span></span><br/><span data-ttu-id="13cc8-133">- Disattivare l'inoltro della posta esterna</span><span class="sxs-lookup"><span data-stu-id="13cc8-133">- Turn off external mail forwarding</span></span>          |

<span data-ttu-id="13cc8-134">Le azioni di correzione, in attesa di approvazione o già completate, possono essere visualizzate nel [Centro notifiche.](m365d-action-center.md)</span><span class="sxs-lookup"><span data-stu-id="13cc8-134">Remediation actions, whether pending approval or already complete, can be viewed in the [Action Center](m365d-action-center.md).</span></span>

## <a name="remediation-actions-that-follow-automated-investigations"></a><span data-ttu-id="13cc8-135">Azioni correttive che seguono indagini automatizzate</span><span class="sxs-lookup"><span data-stu-id="13cc8-135">Remediation actions that follow automated investigations</span></span>

<span data-ttu-id="13cc8-136">Al termine di un'indagine automatizzata, viene raggiunto un verdetto per ogni prova coinvolta.</span><span class="sxs-lookup"><span data-stu-id="13cc8-136">When an automated investigation completes, a verdict is reached for every piece of evidence involved.</span></span> <span data-ttu-id="13cc8-137">A seconda del verdetto, vengono identificate le azioni correttive.</span><span class="sxs-lookup"><span data-stu-id="13cc8-137">Depending on the verdict, remediation actions are identified.</span></span> <span data-ttu-id="13cc8-138">In alcuni casi, le azioni correttive vengono eseguite automaticamente; in altri casi, invece, è necessario approvarle.</span><span class="sxs-lookup"><span data-stu-id="13cc8-138">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="13cc8-139">Tutto dipende dal modo in cui [vengono configurate l'indagine e la risposta automatizzate.](m365d-configure-auto-investigation-response.md)</span><span class="sxs-lookup"><span data-stu-id="13cc8-139">It all depends on how [automated investigation and response is configured](m365d-configure-auto-investigation-response.md).</span></span>

<span data-ttu-id="13cc8-140">Nella tabella seguente sono elencati i possibili verdetti e i risultati:</span><span class="sxs-lookup"><span data-stu-id="13cc8-140">The following table lists possible verdicts and outcomes:</span></span>

| <span data-ttu-id="13cc8-141">Verdetto</span><span class="sxs-lookup"><span data-stu-id="13cc8-141">Verdict</span></span>    | <span data-ttu-id="13cc8-142">Area</span><span class="sxs-lookup"><span data-stu-id="13cc8-142">Area</span></span>    | <span data-ttu-id="13cc8-143">Risultati</span><span class="sxs-lookup"><span data-stu-id="13cc8-143">Outcomes</span></span>|
|------|------|------|
| <span data-ttu-id="13cc8-144">Dannosa</span><span class="sxs-lookup"><span data-stu-id="13cc8-144">Malicious</span></span>    | <span data-ttu-id="13cc8-145">Dispositivi (endpoint)</span><span class="sxs-lookup"><span data-stu-id="13cc8-145">Devices (endpoints)</span></span>    | <span data-ttu-id="13cc8-146">Le azioni di correzione vengono eseguite automaticamente [](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) (presupponendo che i gruppi di dispositivi dell'organizzazione siano impostati su **Completo - correggere automaticamente le minacce)**</span><span class="sxs-lookup"><span data-stu-id="13cc8-146">Remediation actions are taken automatically (assuming your organization's [device groups](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) are set to **Full - remediate threats automatically**)</span></span>|
| <span data-ttu-id="13cc8-147">Dannosa</span><span class="sxs-lookup"><span data-stu-id="13cc8-147">Malicious</span></span>    | <span data-ttu-id="13cc8-148">Contenuto della posta elettronica (URL o allegati)</span><span class="sxs-lookup"><span data-stu-id="13cc8-148">Email content (URLs or attachments)</span></span> | <span data-ttu-id="13cc8-149">Le azioni correttive consigliate sono in attesa di approvazione</span><span class="sxs-lookup"><span data-stu-id="13cc8-149">Recommended remediation actions are pending approval</span></span>|
| <span data-ttu-id="13cc8-150">Sospetta</span><span class="sxs-lookup"><span data-stu-id="13cc8-150">Suspicious</span></span>    | <span data-ttu-id="13cc8-151">Dispositivi o contenuto della posta elettronica</span><span class="sxs-lookup"><span data-stu-id="13cc8-151">Devices or email content</span></span> | <span data-ttu-id="13cc8-152">Le azioni correttive consigliate sono in attesa di approvazione</span><span class="sxs-lookup"><span data-stu-id="13cc8-152">Recommended remediation actions are pending approval</span></span>|
| <span data-ttu-id="13cc8-153">Nessuna minaccia trovata</span><span class="sxs-lookup"><span data-stu-id="13cc8-153">No threats found</span></span>    | <span data-ttu-id="13cc8-154">Dispositivi o contenuto della posta elettronica</span><span class="sxs-lookup"><span data-stu-id="13cc8-154">Devices or email content</span></span>    | <span data-ttu-id="13cc8-155">Non sono necessarie azioni correttive</span><span class="sxs-lookup"><span data-stu-id="13cc8-155">No remediation actions are needed</span></span>|


## <a name="remediation-actions-that-are-taken-manually"></a><span data-ttu-id="13cc8-156">Azioni correttive eseguite manualmente</span><span class="sxs-lookup"><span data-stu-id="13cc8-156">Remediation actions that are taken manually</span></span>

<span data-ttu-id="13cc8-157">Oltre alle azioni di correzione che seguono indagini automatizzate, il team delle operazioni di sicurezza può eseguire alcune azioni di correzione manualmente.</span><span class="sxs-lookup"><span data-stu-id="13cc8-157">In addition to remediation actions that follow automated investigations, your security operations team can take certain remediation actions manually.</span></span> <span data-ttu-id="13cc8-158">Sono incluse le azioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="13cc8-158">These include the following actions:</span></span>

- <span data-ttu-id="13cc8-159">Azione manuale del dispositivo, ad esempio isolamento del dispositivo o quarantena dei file.</span><span class="sxs-lookup"><span data-stu-id="13cc8-159">Manual device action, such as device isolation or file quarantine.</span></span>
- <span data-ttu-id="13cc8-160">Azione manuale della posta elettronica, ad esempio l'eliminazione recidiva dei messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="13cc8-160">Manual email action, such as soft-deleting email messages.</span></span> 
- <span data-ttu-id="13cc8-161">[Azione di ricerca](../defender-endpoint/advanced-hunting-overview.md) avanzata su dispositivi o posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="13cc8-161">[Advanced hunting](../defender-endpoint/advanced-hunting-overview.md) action on devices or email.</span></span>
- <span data-ttu-id="13cc8-162">[Azione di Explorer](../office-365-security/threat-explorer.md) sul contenuto della posta elettronica, ad esempio lo spostamento della posta elettronica nella posta indesiderata, l'eliminazione recisa della posta elettronica o l'eliminazione permanente della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="13cc8-162">[Explorer](../office-365-security/threat-explorer.md) action on email content, such as moving email to junk, soft-deleting email, or hard-deleting email.</span></span>
- <span data-ttu-id="13cc8-163">Azione [di risposta in tempo](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) reale manuale, ad esempio l'eliminazione di un file, l'arresto di un processo e la rimozione di un'attività pianificata.</span><span class="sxs-lookup"><span data-stu-id="13cc8-163">Manual [live response](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) action, such as deleting a file, stopping a process, and removing a scheduled task.</span></span>
- <span data-ttu-id="13cc8-164">Azione di risposta in tempo reale con le API di [Microsoft Defender per endpoint,](../defender-endpoint/management-apis.md#microsoft-defender-for-endpoint-apis)ad esempio l'isolamento di un dispositivo, l'esecuzione di un'analisi antivirus e il recupero di informazioni su un file.</span><span class="sxs-lookup"><span data-stu-id="13cc8-164">Live response action with [Microsoft Defender for Endpoint APIs](../defender-endpoint/management-apis.md#microsoft-defender-for-endpoint-apis), such as isolating a device, running an antivirus scan, and getting information about a file.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="13cc8-165">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="13cc8-165">Next steps</span></span>

- [<span data-ttu-id="13cc8-166">Visita il Centro notifiche</span><span class="sxs-lookup"><span data-stu-id="13cc8-166">Visit the Action center</span></span>](m365d-action-center.md)
- [<span data-ttu-id="13cc8-167">Visualizzare e gestire le azioni correttive</span><span class="sxs-lookup"><span data-stu-id="13cc8-167">View and manage remediation actions</span></span>]( m365d-autoir-actions.md)
- [<span data-ttu-id="13cc8-168">Gestire falsi positivi/negativi nelle funzionalità di analisi e risposta automatizzate</span><span class="sxs-lookup"><span data-stu-id="13cc8-168">Handle false positives/negatives in automated investigation and response capabilities</span></span>](m365d-autoir-report-false-positives-negatives.md)
