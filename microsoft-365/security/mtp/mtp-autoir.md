---
title: Analisi e risposta automatizzate in Microsoft 365 Defender
description: Panoramica delle funzionalità di analisi e risposta automatizzate, denominate anche riparazione automatica, in Microsoft 365 Defender
keywords: automatizzato, indagine, avviso, trigger, azione, correzione, riparazione automatica
search.appverid: met150
ms.prod: m365-security
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
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.date: 12/09/2020
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: 905455e4cd70485e099f8005b5f8876b1a5d9caf
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930331"
---
# <a name="automated-investigation-and-response-in-microsoft-365-defender"></a><span data-ttu-id="bfc7a-104">Analisi e risposta automatizzate in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bfc7a-104">Automated investigation and response in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="bfc7a-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="bfc7a-105">**Applies to:**</span></span>
- <span data-ttu-id="bfc7a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bfc7a-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="bfc7a-107">Si vuole provare Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="bfc7a-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="bfc7a-108">È possibile [valutarlo in un ambiente lab o](https://aka.ms/mtp-trial-lab) eseguire il progetto pilota in [produzione.](https://aka.ms/m365d-pilotplaybook)</span><span class="sxs-lookup"><span data-stu-id="bfc7a-108">You can [evaluate it in a lab environment](https://aka.ms/mtp-trial-lab) or [run your pilot project in production](https://aka.ms/m365d-pilotplaybook).</span></span>
>

## <a name="how-automated-investigation-and-self-healing-works"></a><span data-ttu-id="bfc7a-109">Come funzionano l'indagine automatizzata e la riparazione automatica</span><span class="sxs-lookup"><span data-stu-id="bfc7a-109">How automated investigation and self-healing works</span></span>

<span data-ttu-id="bfc7a-110">Quando vengono attivati avvisi di sicurezza, il team delle operazioni di sicurezza deve esaminare tali avvisi ed eseguire le operazioni necessarie per proteggere l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="bfc7a-110">As security alerts are triggered, it's up to your security operations team to look into those alerts and take steps to protect your organization.</span></span> <span data-ttu-id="bfc7a-111">La classificazione in ordine di priorità e l'analisi degli avvisi può richiedere molto tempo, soprattutto quando continuano ad arrivare nuovi avvisi durante il corso di un'indagine.</span><span class="sxs-lookup"><span data-stu-id="bfc7a-111">Prioritizing and investigating alerts can be very time consuming, especially when new alerts keep coming in while an investigation is going on.</span></span> <span data-ttu-id="bfc7a-112">I team delle operazioni di sicurezza possono sentirsi sopraffatti dall'enorme volume di minacce che devono monitorare e da cui devono proteggersi.</span><span class="sxs-lookup"><span data-stu-id="bfc7a-112">Security operations teams can feel overwhelmed by the sheer volume of threats they must monitor and protect against.</span></span> <span data-ttu-id="bfc7a-113">Le funzionalità di analisi e risposta automatizzate, con autori-riparazione, in Microsoft 365 Defender possono essere di aiuto.</span><span class="sxs-lookup"><span data-stu-id="bfc7a-113">Automated investigation and response capabilities, with self-healing, in Microsoft 365 Defender can help.</span></span>

<span data-ttu-id="bfc7a-114">Guardare il video seguente per vedere come funziona la riparazione automatica:</span><span class="sxs-lookup"><span data-stu-id="bfc7a-114">Watch the following video to see how self-healing works:</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

<span data-ttu-id="bfc7a-115">In Microsoft 365 Defender, l'analisi e la risposta automatizzate con funzionalità di riparazione automatica funzionano su dispositivi, contenuti & posta elettronica e identità.</span><span class="sxs-lookup"><span data-stu-id="bfc7a-115">In Microsoft 365 Defender, automated investigation and response with self-healing capabilities works across your devices, email & content, and identities.</span></span>
 
> [!TIP]
> <span data-ttu-id="bfc7a-116">Questo articolo descrive il funzionamento dell'indagine e della risposta automatizzate.</span><span class="sxs-lookup"><span data-stu-id="bfc7a-116">This article describes how automated investigation and response works.</span></span> <span data-ttu-id="bfc7a-117">Per configurare queste funzionalità, vedere Configurare le funzionalità di analisi e [risposta automatizzate in Microsoft 365 Defender.](mtp-configure-auto-investigation-response.md)</span><span class="sxs-lookup"><span data-stu-id="bfc7a-117">To configure these capabilities, see [Configure automated investigation and response capabilities in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md).</span></span>

## <a name="your-own-virtual-analyst"></a><span data-ttu-id="bfc7a-118">Analista virtuale</span><span class="sxs-lookup"><span data-stu-id="bfc7a-118">Your own virtual analyst</span></span>

<span data-ttu-id="bfc7a-119">È possibile immaginare un analista virtuale nel proprio team delle operazioni di sicurezza di livello 1 o di livello 2.</span><span class="sxs-lookup"><span data-stu-id="bfc7a-119">Imagine having a virtual analyst in your Tier 1 / Tier 2 security operations team.</span></span> <span data-ttu-id="bfc7a-120">L'analista virtuale simula i passaggi ideali che le operazioni di sicurezza seguirebbero per analizzare e correggere le minacce.</span><span class="sxs-lookup"><span data-stu-id="bfc7a-120">The virtual analyst mimics the ideal steps that security operations would take to investigate and remediate threats.</span></span> <span data-ttu-id="bfc7a-121">L'assistente virtuale potrebbe lavorare 24 ore su 24, 7 giorni su 7 con capacità illimitata e intraprendere un carico significativo di indagini e correzione delle minacce.</span><span class="sxs-lookup"><span data-stu-id="bfc7a-121">The virtual assistant could work 24x7, with unlimited capacity, and take on a significant load of investigations and threat remediation.</span></span> <span data-ttu-id="bfc7a-122">Un tale assistente virtuale potrebbe ridurre significativamente i tempi di risposta, togliendo l'incombenza al team delle operazioni di sicurezza per consentirgli di svolgere altri importanti progetti strategici.</span><span class="sxs-lookup"><span data-stu-id="bfc7a-122">Such a virtual assistant could significantly reduce the time to respond, freeing up your security operations team for other important strategic projects.</span></span> <span data-ttu-id="bfc7a-123">Se questo scenario sembra essere una fiction, non lo è!</span><span class="sxs-lookup"><span data-stu-id="bfc7a-123">If this scenario sounds like science fiction, it's not!</span></span> <span data-ttu-id="bfc7a-124">Tale analista virtuale fa parte della famiglia di prodotti Microsoft 365 Defender e il suo nome è analisi e risposta *automatizzate.*</span><span class="sxs-lookup"><span data-stu-id="bfc7a-124">Such a virtual analyst is part of your Microsoft 365 Defender suite, and its name is *automated investigation and response*.</span></span>

<span data-ttu-id="bfc7a-125">L'analisi e la risposta automatizzate consentono al team delle operazioni di sicurezza di aumentare notevolmente la capacità dell'organizzazione di gestire gli avvisi e gli incidenti di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="bfc7a-125">Automated investigation and response enables your security operations team to dramatically increase your organization's capacity to deal with security alerts and incidents.</span></span> <span data-ttu-id="bfc7a-126">Con l'analisi e la risposta automatizzate, è possibile ridurre i costi di gestione delle attività di analisi e correzione e ottenere il massimo dalla famiglia di prodotti di protezione dalle minacce.</span><span class="sxs-lookup"><span data-stu-id="bfc7a-126">With automated investigation and response, you can reduce the cost of dealing with investigation and remediation activities and get the most out of your threat protection suite.</span></span> <span data-ttu-id="bfc7a-127">l'analisi e la risposta automatizzate consentono al team delle operazioni di sicurezza di:</span><span class="sxs-lookup"><span data-stu-id="bfc7a-127">automated investigation and response helps your security operations team by:</span></span>

1. <span data-ttu-id="bfc7a-128">stabilire se una minaccia richiede un'azione;</span><span class="sxs-lookup"><span data-stu-id="bfc7a-128">Determining whether a threat requires action;</span></span>
2. <span data-ttu-id="bfc7a-129">eseguire (o consigliare) tutte le azioni correttive necessarie;</span><span class="sxs-lookup"><span data-stu-id="bfc7a-129">Performing (or recommending) any necessary remediation actions;</span></span>
3. <span data-ttu-id="bfc7a-130">stabilire quali ulteriori indagini dovrebbero essere intraprese;</span><span class="sxs-lookup"><span data-stu-id="bfc7a-130">Determining what additional investigations should occur; and</span></span>
4. <span data-ttu-id="bfc7a-131">ripetere il processo per altri avvisi, se necessario.</span><span class="sxs-lookup"><span data-stu-id="bfc7a-131">Repeating the process as necessary for other alerts.</span></span>

## <a name="the-automated-investigation-process"></a><span data-ttu-id="bfc7a-132">Il processo di indagine automatizzata</span><span class="sxs-lookup"><span data-stu-id="bfc7a-132">The automated investigation process</span></span>

<span data-ttu-id="bfc7a-133">**Avviso** > **incidente** > **indagine automatizzata** > **verdetto** > **azione correttiva**</span><span class="sxs-lookup"><span data-stu-id="bfc7a-133">**Alert** > **incident** > **automated investigation** > **verdict** > **remediation action**</span></span>

<span data-ttu-id="bfc7a-134">Un avviso attivato crea un evento imprevisto, che può avviare un'indagine automatizzata.</span><span class="sxs-lookup"><span data-stu-id="bfc7a-134">A triggered alert creates an incident, which can start an automated investigation.</span></span> <span data-ttu-id="bfc7a-135">Tale indagine può comportare una o più azioni correttive.</span><span class="sxs-lookup"><span data-stu-id="bfc7a-135">That investigation can result in one or more remediation actions.</span></span> <span data-ttu-id="bfc7a-136">In Microsoft 365 Defender, ogni indagine automatizzata correla i segnali tra Microsoft Defender for Identity, Microsoft Defender for Endpoint e Defender per Office 365, come riepilogato nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="bfc7a-136">In Microsoft 365 Defender, each automated investigation correlates signals across Microsoft Defender for Identity, Microsoft Defender for Endpoint, and Defender for Office 365, as summarized in the following table:</span></span> 

|<span data-ttu-id="bfc7a-137">Entità</span><span class="sxs-lookup"><span data-stu-id="bfc7a-137">Entities</span></span> |<span data-ttu-id="bfc7a-138">Servizi di protezione dalle minacce</span><span class="sxs-lookup"><span data-stu-id="bfc7a-138">Threat protection services</span></span>  |
|---------|---------|
|<span data-ttu-id="bfc7a-139">Dispositivi (detti anche endpoint)</span><span class="sxs-lookup"><span data-stu-id="bfc7a-139">Devices (also referred to as endpoints)</span></span>     |[<span data-ttu-id="bfc7a-140">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="bfc7a-140">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)<br/>[<span data-ttu-id="bfc7a-141">Che cosa è Microsoft Defender per identità?</span><span class="sxs-lookup"><span data-stu-id="bfc7a-141">Microsoft Defender for Identity</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) |      
|<span data-ttu-id="bfc7a-142">Contenuto della posta elettronica (file e messaggi nelle cassette postali)</span><span class="sxs-lookup"><span data-stu-id="bfc7a-142">Email content (files and messages in mailboxes)</span></span>     |[<span data-ttu-id="bfc7a-143">Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="bfc7a-143">Microsoft Defender for Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)         |

<span data-ttu-id="bfc7a-144">Ogni indagine genera verdetti (*Dannoso,* Sospetto o Nessuna minaccia *trovata)* per ogni prova esaminata.</span><span class="sxs-lookup"><span data-stu-id="bfc7a-144">Each investigation generates verdicts (*Malicious*, *Suspicious*, or *No threats found*) for each piece of evidence investigated.</span></span> <span data-ttu-id="bfc7a-145">A seconda del tipo di minaccia e del verdetto risultante, le azioni di correzione vengono eseguite automaticamente o al momento dell'approvazione da parte del team delle operazioni di sicurezza dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="bfc7a-145">Depending on the type of threat and resulting verdict, remediation actions occur automatically or upon approval by your organization's security operations team.</span></span> <span data-ttu-id="bfc7a-146">Le azioni in sospeso e quelle completate sono elencate nel [centro notifiche](mtp-action-center.md).</span><span class="sxs-lookup"><span data-stu-id="bfc7a-146">Pending and completed actions are listed in the [Action center](mtp-action-center.md).</span></span>

<span data-ttu-id="bfc7a-147">Durante l'esecuzione di un'indagine, tutti gli altri avvisi correlati che emergono vengono aggiunti all'indagine fino al suo completamento.</span><span class="sxs-lookup"><span data-stu-id="bfc7a-147">While an investigation is running, any other related alerts that arise are added to the investigation until it completes.</span></span> <span data-ttu-id="bfc7a-148">Se un'entità incriminata viene visualizzata altrove, l'indagine automatizzata amplierà il suo ambito per includere tale entità e verrà eseguito un playbook della sicurezza generale.</span><span class="sxs-lookup"><span data-stu-id="bfc7a-148">If an incriminated entity is seen elsewhere, the automated investigation will expand its scope to include that entity, and a general security playbook will run.</span></span> 

> [!NOTE]
> <span data-ttu-id="bfc7a-149">Non tutti gli avvisi attivano un'indagine automatizzata e non tutte le indagini generano azioni correttive automatizzate; Tutto questo dipende dalla configurazione dell'indagine e della risposta automatizzate per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="bfc7a-149">Not every alert triggers an automated investigation, and not every investigation results in automated remediation actions; this all depends on how automated investigation and response is configured for your organization.</span></span> <span data-ttu-id="bfc7a-150">Vedere [Configurare le funzionalità di analisi e risposta automatizzate in Microsoft 365 Defender.](mtp-configure-auto-investigation-response.md)</span><span class="sxs-lookup"><span data-stu-id="bfc7a-150">See [Configure automated investigation and response capabilities in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md).</span></span>


## <a name="next-steps"></a><span data-ttu-id="bfc7a-151">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="bfc7a-151">Next steps</span></span>

- [<span data-ttu-id="bfc7a-152">Vedere i prerequisiti per l'analisi e la risposta automatizzate in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bfc7a-152">See the prerequisites for automated investigation and response in Microsoft 365 Defender</span></span>](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
- [<span data-ttu-id="bfc7a-153">Configurare l'analisi e la risposta automatizzate per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="bfc7a-153">Configure automated investigation and response for your organization</span></span>](mtp-configure-auto-investigation-response.md)
- [<span data-ttu-id="bfc7a-154">Altre informazioni sul centro notifiche</span><span class="sxs-lookup"><span data-stu-id="bfc7a-154">Learn more about the Action center</span></span>](mtp-action-center.md)
