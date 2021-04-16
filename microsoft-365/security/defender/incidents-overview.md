---
title: Eventi imprevisti in Microsoft 365 Defender
description: Analizzare gli eventi imprevisti visualizzati su dispositivi, utenti e cassette postali.
keywords: eventi, avvisi, analisi, correlazione, attacco, computer, dispositivi, utenti, identità, cassetta postale, posta elettronica, 365, Microsoft, M365
search.product: eADQiWindows 10XVcnh
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
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: e1e028f7b58df07eccf945b3a79012b4ea12366d
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861624"
---
# <a name="incidents-in-microsoft-365-defender"></a><span data-ttu-id="4d1fb-104">Eventi imprevisti in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4d1fb-104">Incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="4d1fb-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="4d1fb-105">**Applies to:**</span></span>
- <span data-ttu-id="4d1fb-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4d1fb-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="4d1fb-107">Vuoi provare Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="4d1fb-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="4d1fb-108">Puoi [valutarlo in un ambiente lab](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) o [eseguire il progetto pilota in produzione](m365d-pilot.md?ocid=cx-evalpilot).</span><span class="sxs-lookup"><span data-stu-id="4d1fb-108">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>
>

<span data-ttu-id="4d1fb-109">Un evento imprevisto in Microsoft 365 Defender è una raccolta di avvisi correlati e dati associati che costituiscono la storia di un attacco.</span><span class="sxs-lookup"><span data-stu-id="4d1fb-109">An incident in Microsoft 365 Defender is a collection of correlated alerts and associated data that make up the story of an attack.</span></span> 

<span data-ttu-id="4d1fb-110">I servizi e le app di Microsoft 365 creano avvisi quando rilevano un evento o un'attività sospetta o dannosa.</span><span class="sxs-lookup"><span data-stu-id="4d1fb-110">Microsoft 365 services and apps create alerts when they detect a suspicious or malicious event or activity.</span></span> <span data-ttu-id="4d1fb-111">I singoli avvisi forniscono indicazioni preziose su un attacco completato o in corso.</span><span class="sxs-lookup"><span data-stu-id="4d1fb-111">Individual alerts provide valuable clues about a completed or ongoing attack.</span></span> <span data-ttu-id="4d1fb-112">Tuttavia, gli attacchi in genere utilizzano diverse tecniche per diversi tipi di entità, ad esempio dispositivi, utenti e cassette postali.</span><span class="sxs-lookup"><span data-stu-id="4d1fb-112">However, attacks typically employ various techniques against different types of entities, such as devices, users, and mailboxes.</span></span> <span data-ttu-id="4d1fb-113">Il risultato è più avvisi per più entità nel tenant.</span><span class="sxs-lookup"><span data-stu-id="4d1fb-113">The result is multiple alerts for multiple entities in your tenant.</span></span> 

<span data-ttu-id="4d1fb-114">Poiché l'aggregazione dei singoli avvisi per ottenere informazioni approfondite su un attacco può essere impegnativa e dispendiosa in termini di tempo, Microsoft 365 Defender aggrega automaticamente gli avvisi e le informazioni associate in un evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="4d1fb-114">Because piecing the individual alerts together to gain insight into an attack can be challenging and time-consuming, Microsoft 365 Defender automatically aggregates the alerts and their associated information into an incident.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents.png" alt-text="Come Microsoft 365 Defender correla gli eventi dalle entità a un evento imprevisto":::

<span data-ttu-id="4d1fb-116">Guarda questa breve panoramica degli incidenti in Microsoft 365 Defender (4 minuti).</span><span class="sxs-lookup"><span data-stu-id="4d1fb-116">Watch this short overview of incidents in Microsoft 365 Defender (4 minutes).</span></span>

<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="4d1fb-117">Il raggruppamento degli avvisi correlati in un evento imprevisto offre una visualizzazione completa di un attacco.</span><span class="sxs-lookup"><span data-stu-id="4d1fb-117">Grouping related alerts into an incident gives you a comprehensive view of an attack.</span></span> <span data-ttu-id="4d1fb-118">Ad esempio, è possibile visualizzare:</span><span class="sxs-lookup"><span data-stu-id="4d1fb-118">For example, you can see:</span></span>

- <span data-ttu-id="4d1fb-119">Da dove è iniziato l'attacco.</span><span class="sxs-lookup"><span data-stu-id="4d1fb-119">Where the attack started.</span></span>
- <span data-ttu-id="4d1fb-120">Quali tattiche sono state usate.</span><span class="sxs-lookup"><span data-stu-id="4d1fb-120">What tactics were used.</span></span>
- <span data-ttu-id="4d1fb-121">La distanza dell'attacco nel tenant.</span><span class="sxs-lookup"><span data-stu-id="4d1fb-121">How far the attack has gone into your tenant.</span></span>
- <span data-ttu-id="4d1fb-122">Ambito dell'attacco, ad esempio il numero di dispositivi, utenti e cassette postali che sono stati influenzati.</span><span class="sxs-lookup"><span data-stu-id="4d1fb-122">The scope of the attack, such as how many devices, users, and mailboxes were impacted.</span></span> 
- <span data-ttu-id="4d1fb-123">Tutti i dati associati all'attacco.</span><span class="sxs-lookup"><span data-stu-id="4d1fb-123">All of the data associated with the attack.</span></span>

<span data-ttu-id="4d1fb-124">Se [abilitato,](m365d-enable.md)Microsoft 365 Defender può analizzare e risolvere automaticamente gli avvisi tramite l'automazione e l'intelligenza artificiale.</span><span class="sxs-lookup"><span data-stu-id="4d1fb-124">If [enabled](m365d-enable.md), Microsoft 365 Defender can automatically investigate and resolve alerts through automation and artificial intelligence.</span></span> <span data-ttu-id="4d1fb-125">È inoltre possibile eseguire ulteriori passaggi di correzione per risolvere l'attacco.</span><span class="sxs-lookup"><span data-stu-id="4d1fb-125">You can also perform additional remediation steps to resolve the attack.</span></span> 

## <a name="incidents-and-alerts-in-the-microsoft-365-security-center"></a><span data-ttu-id="4d1fb-126">Eventi imprevisti e avvisi nel Centro sicurezza Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4d1fb-126">Incidents and alerts in the Microsoft 365 security center</span></span>

<span data-ttu-id="4d1fb-127">È possibile gestire gli eventi imprevisti da Eventi imprevisti & avvisi **> eventi** imprevisti sulla barra di avvio veloce del Centro sicurezza Microsoft 365 ([security.microsoft.com](https://security.microsoft.com)).</span><span class="sxs-lookup"><span data-stu-id="4d1fb-127">You manage incidents from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span> <span data-ttu-id="4d1fb-128">Di seguito viene riportato un esempio.</span><span class="sxs-lookup"><span data-stu-id="4d1fb-128">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Pagina Eventi imprevisti nel Centro sicurezza Microsoft 365":::

<span data-ttu-id="4d1fb-130">Se si seleziona un nome di evento imprevisto, viene visualizzato un riepilogo dell'evento imprevisto e viene fornito l'accesso alle schede con informazioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="4d1fb-130">Selecting an incident name displays a summary of the incident and provides access to tabs with additional information.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Esempio della pagina Riepilogo per un evento imprevisto nel Centro sicurezza Microsoft 365":::

<span data-ttu-id="4d1fb-132">Le schede aggiuntive per un evento imprevisto sono:</span><span class="sxs-lookup"><span data-stu-id="4d1fb-132">The additional tabs for an incident are:</span></span>

- <span data-ttu-id="4d1fb-133">Avvisi</span><span class="sxs-lookup"><span data-stu-id="4d1fb-133">Alerts</span></span> 

  <span data-ttu-id="4d1fb-134">Tutti gli avvisi relativi all'evento imprevisto e le relative informazioni.</span><span class="sxs-lookup"><span data-stu-id="4d1fb-134">All the alerts related to the incident and their information.</span></span>

- <span data-ttu-id="4d1fb-135">Dispositivi</span><span class="sxs-lookup"><span data-stu-id="4d1fb-135">Devices</span></span>

  <span data-ttu-id="4d1fb-136">Tutti i dispositivi identificati come parte o correlati all'evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="4d1fb-136">All the devices that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="4d1fb-137">Utenti</span><span class="sxs-lookup"><span data-stu-id="4d1fb-137">Users</span></span>

  <span data-ttu-id="4d1fb-138">Tutti gli utenti identificati come parte o correlati all'evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="4d1fb-138">All the users that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="4d1fb-139">Cassette postali</span><span class="sxs-lookup"><span data-stu-id="4d1fb-139">Mailboxes</span></span>

  <span data-ttu-id="4d1fb-140">Tutte le cassette postali identificate come parte o correlate all'evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="4d1fb-140">All the mailboxes that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="4d1fb-141">Indagini</span><span class="sxs-lookup"><span data-stu-id="4d1fb-141">Investigations</span></span>

  <span data-ttu-id="4d1fb-142">Tutte le indagini automatizzate attivate dagli avvisi nell'evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="4d1fb-142">All the automated investigations triggered by alerts in the incident.</span></span>

- <span data-ttu-id="4d1fb-143">Prova e risposta</span><span class="sxs-lookup"><span data-stu-id="4d1fb-143">Evidence and Response</span></span>

  <span data-ttu-id="4d1fb-144">Tutti gli eventi supportati e le entità sospette negli avvisi nell'evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="4d1fb-144">All the supported events and suspicious entities in the alerts in the incident.</span></span>

<span data-ttu-id="4d1fb-145">Ecco la relazione tra un evento imprevisto e i relativi dati e le schede di un evento imprevisto nel Centro sicurezza Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4d1fb-145">Here's the relationship between an incident and its data and the tabs of an incident in the Microsoft 365 security center.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-security-center.png" alt-text="Relazione di un evento imprevisto e dei relativi dati con le schede di un evento imprevisto nel Centro sicurezza Microsoft 365":::

## <a name="next-step"></a><span data-ttu-id="4d1fb-147">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="4d1fb-147">Next step</span></span>

<span data-ttu-id="4d1fb-148">Nella coda degli eventi imprevisti della **pagina Eventi imprevisti** sono elencati gli eventi imprevisti più recenti.</span><span class="sxs-lookup"><span data-stu-id="4d1fb-148">The incident queue from the **Incidents** page lists the most recent incidents.</span></span> <span data-ttu-id="4d1fb-149">Da qui è possibile:</span><span class="sxs-lookup"><span data-stu-id="4d1fb-149">From here, you can:</span></span>

- <span data-ttu-id="4d1fb-150">Vedere quali eventi imprevisti devono essere [classificati in](incident-queue.md) base alla gravità e ad altri fattori.</span><span class="sxs-lookup"><span data-stu-id="4d1fb-150">See which incidents should be [prioritized](incident-queue.md) based on severity and other factors.</span></span> 
- <span data-ttu-id="4d1fb-151">Eseguire [un'analisi](investigate-incidents.md) di un evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="4d1fb-151">Perform an [investigation](investigate-incidents.md) of an incident.</span></span>
- <span data-ttu-id="4d1fb-152">[Gestire gli eventi imprevisti,](manage-incidents.md)che includono la ridenominazione, l'assegnazione, la classificazione e l'aggiunta di tag per il flusso di lavoro di gestione degli eventi imprevisti.</span><span class="sxs-lookup"><span data-stu-id="4d1fb-152">[Manage incidents](manage-incidents.md), which includes renaming, assigning them, classifying, and adding tags for your incident management workflow.</span></span>
