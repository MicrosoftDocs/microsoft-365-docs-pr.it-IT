---
title: Indagine e risposta automatizzate in Microsoft 365 Defender
description: Ottieni una panoramica delle funzionalità di indagine e risposta automatizzate, denominate anche auto-riparazione, in Microsoft 365 Defender
keywords: automated, investigation, alert, trigger, action, remediation, self-healing
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
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
ms.openlocfilehash: fcb7283faed6fe8c5af59cedeeb90577b557ab34
ms.sourcegitcommit: 5a1cb7d95070eef47d401a4693cc137a90550a5e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52259536"
---
# <a name="automated-investigation-and-response-in-microsoft-365-defender"></a><span data-ttu-id="7fcc6-104">Indagine e risposta automatizzate in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7fcc6-104">Automated investigation and response in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="7fcc6-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="7fcc6-105">**Applies to:**</span></span>
- <span data-ttu-id="7fcc6-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7fcc6-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="7fcc6-107">Se l'organizzazione usa [Microsoft 365 Defender,](microsoft-365-defender.md)il team delle operazioni di sicurezza riceve un avviso nel centro sicurezza Microsoft 365 ogni volta che viene rilevata un'attività o un artefatto dannoso o sospetto.</span><span class="sxs-lookup"><span data-stu-id="7fcc6-107">If your organization is using [Microsoft 365 Defender](microsoft-365-defender.md), your security operations team receives an alert within the Microsoft 365 security center whenever a malicious or suspicious activity or artifact is detected.</span></span> <span data-ttu-id="7fcc6-108">Dato il flusso apparentemente senza fine delle minacce che possono arrivare, i team di sicurezza spesso devono affrontare la sfida di affrontare l'elevato volume di avvisi.</span><span class="sxs-lookup"><span data-stu-id="7fcc6-108">Given the seemingly never-ending flow of threats that can come in, security teams often face the challenge of addressing the high volume of alerts.</span></span> <span data-ttu-id="7fcc6-109">Fortunatamente, Microsoft 365 Defender include funzionalità di analisi e correzione automatizzate (AIR) che consentono al team delle operazioni di sicurezza di affrontare le minacce in modo più efficiente ed efficiente.</span><span class="sxs-lookup"><span data-stu-id="7fcc6-109">Fortunately, Microsoft 365 Defender includes automated investigation and remediation (AIR) capabilities that can help your security operations team address threats more efficiently and effectively.</span></span>

<span data-ttu-id="7fcc6-110">In questo articolo viene fornita una panoramica di AIR e vengono forniti collegamenti ai passaggi successivi e a risorse aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="7fcc6-110">This article provides an overview of AIR and includes links to next steps and additional resources.</span></span>

> [!TIP]
> <span data-ttu-id="7fcc6-111">Vuoi provare Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="7fcc6-111">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="7fcc6-112">Puoi [valutarlo in un ambiente lab](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) o [eseguire il progetto pilota in produzione](m365d-pilot.md?ocid=cx-evalpilot).</span><span class="sxs-lookup"><span data-stu-id="7fcc6-112">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>

## <a name="how-automated-investigation-and-self-healing-works"></a><span data-ttu-id="7fcc6-113">Funzionamento dell'indagine automatizzata e dell'auto-riparazione</span><span class="sxs-lookup"><span data-stu-id="7fcc6-113">How automated investigation and self-healing works</span></span>

<span data-ttu-id="7fcc6-114">Quando vengono attivati avvisi di sicurezza, il team delle operazioni di sicurezza deve esaminare tali avvisi ed eseguire le operazioni necessarie per proteggere l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7fcc6-114">As security alerts are triggered, it's up to your security operations team to look into those alerts and take steps to protect your organization.</span></span> <span data-ttu-id="7fcc6-115">La classificazione in ordine di priorità e l'analisi degli avvisi può richiedere molto tempo, soprattutto quando continuano ad arrivare nuovi avvisi durante il corso di un'indagine.</span><span class="sxs-lookup"><span data-stu-id="7fcc6-115">Prioritizing and investigating alerts can be very time consuming, especially when new alerts keep coming in while an investigation is going on.</span></span> <span data-ttu-id="7fcc6-116">I team delle operazioni di sicurezza possono sentirsi sopraffatti dall'enorme volume di minacce che devono monitorare e da cui devono proteggersi.</span><span class="sxs-lookup"><span data-stu-id="7fcc6-116">Security operations teams can feel overwhelmed by the sheer volume of threats they must monitor and protect against.</span></span> <span data-ttu-id="7fcc6-117">Funzionalità di indagine e risposta automatizzate, con auto-riparazione, in Microsoft 365 Defender può aiutare.</span><span class="sxs-lookup"><span data-stu-id="7fcc6-117">Automated investigation and response capabilities, with self-healing, in Microsoft 365 Defender can help.</span></span>

<span data-ttu-id="7fcc6-118">Guarda il video seguente per vedere come funziona l'auto-riparazione:</span><span class="sxs-lookup"><span data-stu-id="7fcc6-118">Watch the following video to see how self-healing works:</span></span> <p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

<span data-ttu-id="7fcc6-119">In Microsoft 365 Defender, l'indagine e la risposta automatizzate con funzionalità di auto-riparazione funzionano su dispositivi, posta elettronica & contenuti e identità.</span><span class="sxs-lookup"><span data-stu-id="7fcc6-119">In Microsoft 365 Defender, automated investigation and response with self-healing capabilities works across your devices, email & content, and identities.</span></span>
 
> [!TIP]
> <span data-ttu-id="7fcc6-120">In questo articolo viene descritto il funzionamento dell'indagine e della risposta automatizzate.</span><span class="sxs-lookup"><span data-stu-id="7fcc6-120">This article describes how automated investigation and response works.</span></span> <span data-ttu-id="7fcc6-121">Per configurare queste funzionalità, vedere [Configure automated investigation and response capabilities in Microsoft 365 Defender](m365d-configure-auto-investigation-response.md).</span><span class="sxs-lookup"><span data-stu-id="7fcc6-121">To configure these capabilities, see [Configure automated investigation and response capabilities in Microsoft 365 Defender](m365d-configure-auto-investigation-response.md).</span></span>

## <a name="your-own-virtual-analyst"></a><span data-ttu-id="7fcc6-122">Analista virtuale</span><span class="sxs-lookup"><span data-stu-id="7fcc6-122">Your own virtual analyst</span></span>

<span data-ttu-id="7fcc6-123">Imagine avere un analista virtuale nel team di operazioni di sicurezza di livello 1 o di livello 2.</span><span class="sxs-lookup"><span data-stu-id="7fcc6-123">Imagine having a virtual analyst in your Tier 1 or Tier 2 security operations team.</span></span> <span data-ttu-id="7fcc6-124">L'analista virtuale simula i passaggi ideali che le operazioni di sicurezza seguirebbero per analizzare e correggere le minacce.</span><span class="sxs-lookup"><span data-stu-id="7fcc6-124">The virtual analyst mimics the ideal steps that security operations would take to investigate and remediate threats.</span></span> <span data-ttu-id="7fcc6-125">L'analista virtuale potrebbe lavorare 24x7, con capacità illimitata, e assumere un carico significativo di indagini e di correzione delle minacce.</span><span class="sxs-lookup"><span data-stu-id="7fcc6-125">The virtual analyst could work 24x7, with unlimited capacity, and take on a significant load of investigations and threat remediation.</span></span> <span data-ttu-id="7fcc6-126">Un analista virtuale di questo tipo potrebbe ridurre in modo significativo il tempo necessario per rispondere, liberando il team delle operazioni di sicurezza per altre minacce importanti o progetti strategici.</span><span class="sxs-lookup"><span data-stu-id="7fcc6-126">Such a virtual analyst could significantly reduce the time to respond, freeing up your security operations team for other important threats or strategic projects.</span></span> <span data-ttu-id="7fcc6-127">Se questo scenario sembra fantascienza, non lo è!</span><span class="sxs-lookup"><span data-stu-id="7fcc6-127">If this scenario sounds like science fiction, it's not!</span></span> <span data-ttu-id="7fcc6-128">Tale analista virtuale fa parte della famiglia Microsoft 365 Defender e il suo nome è analisi e risposta *automatizzate.*</span><span class="sxs-lookup"><span data-stu-id="7fcc6-128">Such a virtual analyst is part of your Microsoft 365 Defender suite, and its name is *automated investigation and response*.</span></span>

<span data-ttu-id="7fcc6-129">Le funzionalità di analisi e risposta automatizzate consentono al team delle operazioni di sicurezza di aumentare notevolmente la capacità dell'organizzazione di gestire gli avvisi e gli incidenti di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="7fcc6-129">Automated investigation and response capabilities enable your security operations team to dramatically increase your organization's capacity to deal with security alerts and incidents.</span></span> <span data-ttu-id="7fcc6-130">Grazie all'indagine e alla risposta automatizzate, è possibile ridurre i costi di gestione delle attività di indagine e correzione e ottenere il massimo dalla famiglia di prodotti di protezione dalle minacce.</span><span class="sxs-lookup"><span data-stu-id="7fcc6-130">With automated investigation and response, you can reduce the cost of dealing with investigation and remediation activities and get the most out of your threat protection suite.</span></span> <span data-ttu-id="7fcc6-131">Le funzionalità di analisi e risposta automatizzate consentono al team delle operazioni di sicurezza di:</span><span class="sxs-lookup"><span data-stu-id="7fcc6-131">Automated investigation and response capabilities help your security operations team by:</span></span>

1. <span data-ttu-id="7fcc6-132">Determinare se una minaccia richiede un'azione.</span><span class="sxs-lookup"><span data-stu-id="7fcc6-132">Determining whether a threat requires action.</span></span>
2. <span data-ttu-id="7fcc6-133">Eseguire (o consigliare) tutte le azioni di correzione necessarie.</span><span class="sxs-lookup"><span data-stu-id="7fcc6-133">Taking (or recommending) any necessary remediation actions.</span></span>
3. <span data-ttu-id="7fcc6-134">Determinare se e quali altre indagini devono essere eseguite.</span><span class="sxs-lookup"><span data-stu-id="7fcc6-134">Determining whether and what other investigations should occur.</span></span>
4. <span data-ttu-id="7fcc6-135">ripetere il processo per altri avvisi, se necessario.</span><span class="sxs-lookup"><span data-stu-id="7fcc6-135">Repeating the process as necessary for other alerts.</span></span>

## <a name="the-automated-investigation-process"></a><span data-ttu-id="7fcc6-136">Il processo di indagine automatizzata</span><span class="sxs-lookup"><span data-stu-id="7fcc6-136">The automated investigation process</span></span>

<span data-ttu-id="7fcc6-137">Un avviso crea un evento imprevisto, che può avviare un'indagine automatizzata.</span><span class="sxs-lookup"><span data-stu-id="7fcc6-137">An alert creates an incident, which can start an automated investigation.</span></span> <span data-ttu-id="7fcc6-138">L'indagine automatizzata determina un verdetto per ogni prova.</span><span class="sxs-lookup"><span data-stu-id="7fcc6-138">The automated investigation results in a verdict for each piece of evidence.</span></span> <span data-ttu-id="7fcc6-139">I verdetti possono essere:</span><span class="sxs-lookup"><span data-stu-id="7fcc6-139">Verdicts can be:</span></span>
- <span data-ttu-id="7fcc6-140">*Dannoso*</span><span class="sxs-lookup"><span data-stu-id="7fcc6-140">*Malicious*</span></span>
- <span data-ttu-id="7fcc6-141">*Sospetta*</span><span class="sxs-lookup"><span data-stu-id="7fcc6-141">*Suspicious*</span></span> 
- <span data-ttu-id="7fcc6-142">*Nessuna minaccia trovata*</span><span class="sxs-lookup"><span data-stu-id="7fcc6-142">*No threats found*</span></span> 

<span data-ttu-id="7fcc6-143">Vengono identificate le azioni di correzione per entità dannose o sospette.</span><span class="sxs-lookup"><span data-stu-id="7fcc6-143">Remediation actions for malicious or suspicious entities are identified.</span></span> <span data-ttu-id="7fcc6-144">Di seguito sono riportati alcuni esempi di azioni correttive:</span><span class="sxs-lookup"><span data-stu-id="7fcc6-144">Examples of remediation actions include:</span></span>

- <span data-ttu-id="7fcc6-145">Invio di un file in quarantena</span><span class="sxs-lookup"><span data-stu-id="7fcc6-145">Sending a file to quarantine</span></span>
- <span data-ttu-id="7fcc6-146">Arresto di un processo</span><span class="sxs-lookup"><span data-stu-id="7fcc6-146">Stopping a process</span></span>
- <span data-ttu-id="7fcc6-147">Isolamento di un dispositivo</span><span class="sxs-lookup"><span data-stu-id="7fcc6-147">Isolating a device</span></span>
- <span data-ttu-id="7fcc6-148">Blocco di un URL</span><span class="sxs-lookup"><span data-stu-id="7fcc6-148">Blocking a URL</span></span> 
- <span data-ttu-id="7fcc6-149">Altre azioni</span><span class="sxs-lookup"><span data-stu-id="7fcc6-149">Other actions</span></span>

<span data-ttu-id="7fcc6-150">Per altre informazioni, vedi [Azioni di correzione in Microsoft 365 Defender.](m365d-remediation-actions.md)</span><span class="sxs-lookup"><span data-stu-id="7fcc6-150">For more information, see See [Remediation actions in Microsoft 365 Defender](m365d-remediation-actions.md).</span></span>

<span data-ttu-id="7fcc6-151">A seconda [di come vengono configurate](m365d-configure-auto-investigation-response.md) le funzionalità di analisi e risposta automatizzate per l'organizzazione, le azioni di correzione vengono eseguite automaticamente o solo dopo l'approvazione da parte del team delle operazioni di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="7fcc6-151">Depending on [how automated investigation and response capabilities are configured](m365d-configure-auto-investigation-response.md) for your organization, remediation actions are taken automatically or only upon approval by your security operations team.</span></span> <span data-ttu-id="7fcc6-152">Tutte le azioni, in sospeso o completate, sono elencate nel [Centro notifiche.](m365d-action-center.md)</span><span class="sxs-lookup"><span data-stu-id="7fcc6-152">All actions, whether pending or completed, are listed in the [Action center](m365d-action-center.md).</span></span>

<span data-ttu-id="7fcc6-153">Durante l'esecuzione di un'indagine, tutti gli altri avvisi correlati che emergono vengono aggiunti all'indagine fino al suo completamento.</span><span class="sxs-lookup"><span data-stu-id="7fcc6-153">While an investigation is running, any other related alerts that arise are added to the investigation until it completes.</span></span> <span data-ttu-id="7fcc6-154">Se un'entità interessata viene vista altrove, l'indagine automatizzata espande il suo ambito per includere tale entità e il processo di indagine si ripete.</span><span class="sxs-lookup"><span data-stu-id="7fcc6-154">If an affected entity is seen elsewhere, the automated investigation expands its scope to include that entity, and the investigation process repeats.</span></span> 

<span data-ttu-id="7fcc6-155">In Microsoft 365 Defender, ogni indagine automatizzata correla i segnali tra Microsoft Defender for Identity, Microsoft Defender for Endpoint e Microsoft Defender per Office 365, come riepilogato nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="7fcc6-155">In Microsoft 365 Defender, each automated investigation correlates signals across Microsoft Defender for Identity, Microsoft Defender for Endpoint, and Microsoft Defender for Office 365, as summarized in the following table:</span></span> 

|<span data-ttu-id="7fcc6-156">Entità</span><span class="sxs-lookup"><span data-stu-id="7fcc6-156">Entities</span></span> |<span data-ttu-id="7fcc6-157">Servizi di protezione dalle minacce</span><span class="sxs-lookup"><span data-stu-id="7fcc6-157">Threat protection services</span></span>  |
|:---------|:---------|
|<span data-ttu-id="7fcc6-158">Dispositivi (denominati anche endpoint o computer)</span><span class="sxs-lookup"><span data-stu-id="7fcc6-158">Devices (also referred to as endpoints or machines)</span></span> |[<span data-ttu-id="7fcc6-159">Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="7fcc6-159">Defender for Endpoint</span></span>](../defender-endpoint/automated-investigations.md) |      
|<span data-ttu-id="7fcc6-160">Utenti, comportamento delle entità e attività di Active Directory locali</span><span class="sxs-lookup"><span data-stu-id="7fcc6-160">On-premises Active Directory users, entity behavior, and activities</span></span>     |[<span data-ttu-id="7fcc6-161">Defender per identità</span><span class="sxs-lookup"><span data-stu-id="7fcc6-161">Defender for Identity</span></span>](/azure-advanced-threat-protection/what-is-atp) |      
|<span data-ttu-id="7fcc6-162">Contenuto della posta elettronica (messaggi di posta elettronica che possono contenere file e URL)</span><span class="sxs-lookup"><span data-stu-id="7fcc6-162">Email content (email messages that can contain files and URLs)</span></span>     |[<span data-ttu-id="7fcc6-163">Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="7fcc6-163">Defender for Office 365</span></span>](../office-365-security/defender-for-office-365.md) |

> [!NOTE]
> <span data-ttu-id="7fcc6-164">Non tutti gli avvisi attivano un'indagine automatizzata e non tutte le indagini generano azioni di correzione automatizzate.</span><span class="sxs-lookup"><span data-stu-id="7fcc6-164">Not every alert triggers an automated investigation, and not every investigation results in automated remediation actions.</span></span> <span data-ttu-id="7fcc6-165">Dipende dal modo in cui l'indagine e la risposta automatizzate sono configurate per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7fcc6-165">It depends on how automated investigation and response is configured for your organization.</span></span> <span data-ttu-id="7fcc6-166">Vedi [Configurare le funzionalità di analisi e risposta automatizzate.](m365d-configure-auto-investigation-response.md)</span><span class="sxs-lookup"><span data-stu-id="7fcc6-166">See [Configure automated investigation and response capabilities](m365d-configure-auto-investigation-response.md).</span></span>

## <a name="viewing-a-list-of-investigations"></a><span data-ttu-id="7fcc6-167">Visualizzazione di un elenco di indagini</span><span class="sxs-lookup"><span data-stu-id="7fcc6-167">Viewing a list of investigations</span></span>

<span data-ttu-id="7fcc6-168">Per visualizzare le indagini, passare alla pagina Eventi **imprevisti.**</span><span class="sxs-lookup"><span data-stu-id="7fcc6-168">To view investigations, go to the **Incidents** page.</span></span> <span data-ttu-id="7fcc6-169">Selezionare un evento imprevisto e quindi selezionare **la scheda** Indagini. Per ulteriori informazioni, vedere [Dettagli e risultati di un'indagine automatizzata.](m365d-autoir-results.md)</span><span class="sxs-lookup"><span data-stu-id="7fcc6-169">Select an incident, and then select the **Investigations** tab. To learn more, see [Details and results of an automated investigation](m365d-autoir-results.md).</span></span>


## <a name="next-steps"></a><span data-ttu-id="7fcc6-170">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="7fcc6-170">Next steps</span></span>

- [<span data-ttu-id="7fcc6-171">Vedere i prerequisiti per l'analisi e la risposta automatizzate</span><span class="sxs-lookup"><span data-stu-id="7fcc6-171">See the prerequisites for automated investigation and response</span></span>](m365d-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
- [<span data-ttu-id="7fcc6-172">Configurare l'indagine e la risposta automatizzate per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="7fcc6-172">Configure automated investigation and response for your organization</span></span>](m365d-configure-auto-investigation-response.md)
- [<span data-ttu-id="7fcc6-173">Altre informazioni sul centro notifiche</span><span class="sxs-lookup"><span data-stu-id="7fcc6-173">Learn more about the Action center</span></span>](m365d-action-center.md)
