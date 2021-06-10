---
title: Eventi imprevisti in Microsoft 365 Defender
description: Analizzare gli eventi imprevisti che si verificano tra dispositivi, utenti e cassette postali nel centro Microsoft 365 sicurezza.
keywords: incidenti, avvisi, analizzare, analizzare, risposta, correlazione, attacco, computer, dispositivi, utenti, identità, identità, identità, cassetta postale, posta elettronica, 365, microsoft, m365, risposta agli incidenti, cyberattacco
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
ms.openlocfilehash: 9970bb6d410f39ff5d796dec678a750342f0f599
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842027"
---
# <a name="incidents-in-microsoft-365-defender"></a><span data-ttu-id="746b9-104">Eventi imprevisti in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="746b9-104">Incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="746b9-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="746b9-105">**Applies to:**</span></span>
- <span data-ttu-id="746b9-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="746b9-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="746b9-107">Vuoi provare Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="746b9-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="746b9-108">Puoi [valutarlo in un ambiente lab](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) o [eseguire il progetto pilota in produzione](m365d-pilot.md?ocid=cx-evalpilot).</span><span class="sxs-lookup"><span data-stu-id="746b9-108">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>
>

<span data-ttu-id="746b9-109">Un evento imprevisto in Microsoft 365 Defender è una raccolta di avvisi correlati e dati associati che costituiscono la storia di un attacco.</span><span class="sxs-lookup"><span data-stu-id="746b9-109">An incident in Microsoft 365 Defender is a collection of correlated alerts and associated data that make up the story of an attack.</span></span> 

<span data-ttu-id="746b9-110">Microsoft 365 e le app creano avvisi quando rilevano un evento o un'attività sospetta o dannosa.</span><span class="sxs-lookup"><span data-stu-id="746b9-110">Microsoft 365 services and apps create alerts when they detect a suspicious or malicious event or activity.</span></span> <span data-ttu-id="746b9-111">I singoli avvisi forniscono indicazioni preziose su un attacco completato o in corso.</span><span class="sxs-lookup"><span data-stu-id="746b9-111">Individual alerts provide valuable clues about a completed or ongoing attack.</span></span> <span data-ttu-id="746b9-112">Tuttavia, gli attacchi in genere utilizzano diverse tecniche per diversi tipi di entità, ad esempio dispositivi, utenti e cassette postali.</span><span class="sxs-lookup"><span data-stu-id="746b9-112">However, attacks typically employ various techniques against different types of entities, such as devices, users, and mailboxes.</span></span> <span data-ttu-id="746b9-113">Il risultato è più avvisi per più entità nel tenant.</span><span class="sxs-lookup"><span data-stu-id="746b9-113">The result is multiple alerts for multiple entities in your tenant.</span></span> 

<span data-ttu-id="746b9-114">Poiché l'aggregazione dei singoli avvisi per ottenere informazioni approfondite su un attacco può essere impegnativa e richiede molto tempo, Microsoft 365 Defender aggrega automaticamente gli avvisi e le informazioni associate in un evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="746b9-114">Because piecing the individual alerts together to gain insight into an attack can be challenging and time-consuming, Microsoft 365 Defender automatically aggregates the alerts and their associated information into an incident.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents.png" alt-text="Come Microsoft 365 Defender correla gli eventi dalle entità a un evento imprevisto":::

<span data-ttu-id="746b9-116">Guarda questa breve panoramica degli eventi imprevisti in Microsoft 365 Defender (4 minuti).</span><span class="sxs-lookup"><span data-stu-id="746b9-116">Watch this short overview of incidents in Microsoft 365 Defender (4 minutes).</span></span>

<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="746b9-117">Il raggruppamento degli avvisi correlati in un evento imprevisto offre una visualizzazione completa di un attacco.</span><span class="sxs-lookup"><span data-stu-id="746b9-117">Grouping related alerts into an incident gives you a comprehensive view of an attack.</span></span> <span data-ttu-id="746b9-118">Ad esempio, è possibile visualizzare:</span><span class="sxs-lookup"><span data-stu-id="746b9-118">For example, you can see:</span></span>

- <span data-ttu-id="746b9-119">Da dove è iniziato l'attacco.</span><span class="sxs-lookup"><span data-stu-id="746b9-119">Where the attack started.</span></span>
- <span data-ttu-id="746b9-120">Quali tattiche sono state usate.</span><span class="sxs-lookup"><span data-stu-id="746b9-120">What tactics were used.</span></span>
- <span data-ttu-id="746b9-121">La distanza dell'attacco nel tenant.</span><span class="sxs-lookup"><span data-stu-id="746b9-121">How far the attack has gone into your tenant.</span></span>
- <span data-ttu-id="746b9-122">Ambito dell'attacco, ad esempio il numero di dispositivi, utenti e cassette postali che sono stati influenzati.</span><span class="sxs-lookup"><span data-stu-id="746b9-122">The scope of the attack, such as how many devices, users, and mailboxes were impacted.</span></span> 
- <span data-ttu-id="746b9-123">Tutti i dati associati all'attacco.</span><span class="sxs-lookup"><span data-stu-id="746b9-123">All of the data associated with the attack.</span></span>

<span data-ttu-id="746b9-124">Se [abilitato,](m365d-enable.md)Microsoft 365 Defender [può](m365d-autoir.md) analizzare e risolvere automaticamente gli avvisi tramite l'automazione e l'intelligenza artificiale.</span><span class="sxs-lookup"><span data-stu-id="746b9-124">If [enabled](m365d-enable.md), Microsoft 365 Defender can [automatically investigate and resolve](m365d-autoir.md) alerts through automation and artificial intelligence.</span></span> <span data-ttu-id="746b9-125">È inoltre possibile eseguire ulteriori passaggi di correzione per risolvere l'attacco.</span><span class="sxs-lookup"><span data-stu-id="746b9-125">You can also perform additional remediation steps to resolve the attack.</span></span> 

## <a name="incidents-and-alerts-in-the-microsoft-365-security-center"></a><span data-ttu-id="746b9-126">Eventi imprevisti e avvisi nel centro sicurezza Microsoft 365 sicurezza</span><span class="sxs-lookup"><span data-stu-id="746b9-126">Incidents and alerts in the Microsoft 365 security center</span></span>

<span data-ttu-id="746b9-127">È possibile gestire gli eventi imprevisti & avvisi **> eventi** imprevisti sulla barra di avvio veloce del centro sicurezza Microsoft 365 ([security.microsoft.com](https://security.microsoft.com)).</span><span class="sxs-lookup"><span data-stu-id="746b9-127">You manage incidents from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span> <span data-ttu-id="746b9-128">Di seguito viene riportato un esempio.</span><span class="sxs-lookup"><span data-stu-id="746b9-128">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Pagina Eventi imprevisti nel centro Microsoft 365 sicurezza":::

<span data-ttu-id="746b9-130">Se si seleziona un nome di evento imprevisto, viene visualizzato un riepilogo dell'evento imprevisto e viene fornito l'accesso alle schede con informazioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="746b9-130">Selecting an incident name displays a summary of the incident and provides access to tabs with additional information.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Esempio della pagina Riepilogo per un evento imprevisto nel centro sicurezza Microsoft 365 sicurezza":::

<span data-ttu-id="746b9-132">Le schede aggiuntive per un evento imprevisto sono:</span><span class="sxs-lookup"><span data-stu-id="746b9-132">The additional tabs for an incident are:</span></span>

- <span data-ttu-id="746b9-133">Avvisi</span><span class="sxs-lookup"><span data-stu-id="746b9-133">Alerts</span></span> 

  <span data-ttu-id="746b9-134">Tutti gli avvisi relativi all'evento imprevisto e le relative informazioni.</span><span class="sxs-lookup"><span data-stu-id="746b9-134">All the alerts related to the incident and their information.</span></span>

- <span data-ttu-id="746b9-135">Dispositivi</span><span class="sxs-lookup"><span data-stu-id="746b9-135">Devices</span></span>

  <span data-ttu-id="746b9-136">Tutti i dispositivi identificati come parte o correlati all'evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="746b9-136">All the devices that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="746b9-137">Utenti</span><span class="sxs-lookup"><span data-stu-id="746b9-137">Users</span></span>

  <span data-ttu-id="746b9-138">Tutti gli utenti identificati come parte o correlati all'evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="746b9-138">All the users that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="746b9-139">Cassette postali</span><span class="sxs-lookup"><span data-stu-id="746b9-139">Mailboxes</span></span>

  <span data-ttu-id="746b9-140">Tutte le cassette postali identificate come parte o correlate all'evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="746b9-140">All the mailboxes that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="746b9-141">Indagini</span><span class="sxs-lookup"><span data-stu-id="746b9-141">Investigations</span></span>

  <span data-ttu-id="746b9-142">Tutte le [indagini automatizzate attivate](m365d-autoir.md) dagli avvisi nell'evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="746b9-142">All the [automated investigations](m365d-autoir.md) triggered by alerts in the incident.</span></span>

- <span data-ttu-id="746b9-143">Prova e risposta</span><span class="sxs-lookup"><span data-stu-id="746b9-143">Evidence and Response</span></span>

  <span data-ttu-id="746b9-144">Tutti gli eventi supportati e le entità sospette negli avvisi nell'evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="746b9-144">All the supported events and suspicious entities in the alerts in the incident.</span></span>

- <span data-ttu-id="746b9-145">Graph (in anteprima)</span><span class="sxs-lookup"><span data-stu-id="746b9-145">Graph (in preview)</span></span>

  <span data-ttu-id="746b9-146">Figura che mostra la connessione degli avvisi agli asset che hanno effetto nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="746b9-146">A figure showing the connection of alerts to the impacted assets in your organization.</span></span>

<span data-ttu-id="746b9-147">Ecco la relazione tra un evento imprevisto e i relativi dati e le schede di un evento imprevisto nel centro sicurezza Microsoft 365 sicurezza.</span><span class="sxs-lookup"><span data-stu-id="746b9-147">Here's the relationship between an incident and its data and the tabs of an incident in the Microsoft 365 security center.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-security-center.png" alt-text="Relazione di un evento imprevisto e dei relativi dati con le schede di un evento imprevisto nel centro sicurezza Microsoft 365 sicurezza":::

## <a name="example-incident-response-workflow-for-microsoft-365-defender"></a><span data-ttu-id="746b9-149">Flusso di lavoro di risposta agli eventi imprevisti di esempio per Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="746b9-149">Example incident response workflow for Microsoft 365 Defender</span></span>

<span data-ttu-id="746b9-150">Ecco un flusso di lavoro di esempio per rispondere a eventi imprevisti in Microsoft 365 con il centro sicurezza Microsoft 365 sicurezza.</span><span class="sxs-lookup"><span data-stu-id="746b9-150">Here's an example workflow for responding to incidents in Microsoft 365 with the Microsoft 365 security center.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-example-workflow.png" alt-text="Esempio di flusso di lavoro di risposta a eventi imprevisti per Microsoft 365":::

<span data-ttu-id="746b9-152">Su base continuativa, identificare gli eventi imprevisti con priorità più alta per l'analisi e la risoluzione nella coda degli eventi imprevisti e prepararli per la risposta.</span><span class="sxs-lookup"><span data-stu-id="746b9-152">On an ongoing basis, identify the highest priority incidents for analysis and resolution in the incident queue and get them ready for response.</span></span> <span data-ttu-id="746b9-153">Questa è una combinazione di:</span><span class="sxs-lookup"><span data-stu-id="746b9-153">This is a combination of:</span></span>

- <span data-ttu-id="746b9-154">[Per determinare](incident-queue.md) gli eventi imprevisti con priorità più alta, è necessario filtrare e ordinare la coda degli eventi imprevisti.</span><span class="sxs-lookup"><span data-stu-id="746b9-154">[Triaging](incident-queue.md) to determining the highest priority incidents through filtering and sorting of the incident queue.</span></span>
- <span data-ttu-id="746b9-155">[Gestire](manage-incidents.md) gli eventi imprevisti modificandone il titolo, assegnandoli a un analista e aggiungendo tag e commenti.</span><span class="sxs-lookup"><span data-stu-id="746b9-155">[Managing](manage-incidents.md) incidents by modifying their title, assigning them to an analyst, and adding tags and comments.</span></span>

1. <span data-ttu-id="746b9-156">Per ogni evento imprevisto, avviare [un'analisi e un attacco:](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="746b9-156">For each incident, begin an [attack and alert investigation and analysis](investigate-incidents.md):</span></span>
 
   <span data-ttu-id="746b9-157">a.</span><span class="sxs-lookup"><span data-stu-id="746b9-157">a.</span></span> <span data-ttu-id="746b9-158">Visualizzare il riepilogo dell'evento imprevisto per comprendere l'ambito e la gravità e le entità interessate **(scheda** Riepilogo).</span><span class="sxs-lookup"><span data-stu-id="746b9-158">View the summary of the incident to understand it's scope and severity and what entities are affected (the **Summary** tab).</span></span>

   <span data-ttu-id="746b9-159">b.</span><span class="sxs-lookup"><span data-stu-id="746b9-159">b.</span></span> <span data-ttu-id="746b9-160">Iniziare ad analizzare gli avvisi per comprenderne l'origine, l'ambito e la gravità **(scheda** Avvisi).</span><span class="sxs-lookup"><span data-stu-id="746b9-160">Begin analyzing the alerts to understand their origin, scope, and severity (the **Alerts** tab).</span></span>

   <span data-ttu-id="746b9-161">c.</span><span class="sxs-lookup"><span data-stu-id="746b9-161">c.</span></span> <span data-ttu-id="746b9-162">In base alle esigenze, raccogliere informazioni sui dispositivi, gli utenti e le cassette postali influenzati (le schede **Dispositivi,** **Utenti** e **Cassette** postali).</span><span class="sxs-lookup"><span data-stu-id="746b9-162">As needed, gather information on impacted devices, users, and mailboxes (the **Devices**, **Users**, and **Mailboxes** tabs).</span></span>

   <span data-ttu-id="746b9-163">d.</span><span class="sxs-lookup"><span data-stu-id="746b9-163">d.</span></span> <span data-ttu-id="746b9-164">Scopri come Microsoft 365 Defender ha [risolto automaticamente alcuni avvisi](m365d-autoir.md) **(scheda** Indagini).</span><span class="sxs-lookup"><span data-stu-id="746b9-164">See how Microsoft 365 Defender has [automatically resolved some alerts](m365d-autoir.md) (the **Investigations** tab).</span></span>
   
   <span data-ttu-id="746b9-165">e.</span><span class="sxs-lookup"><span data-stu-id="746b9-165">e.</span></span> <span data-ttu-id="746b9-166">Se necessario, usare le informazioni nel set di dati per l'evento imprevisto per ulteriori informazioni (scheda **Prova e** risposta).</span><span class="sxs-lookup"><span data-stu-id="746b9-166">As needed, use information in the data set for the incident for more information (the **Evidence and Response** tab).</span></span>

2. <span data-ttu-id="746b9-167">Dopo o durante l'analisi, eseguire il contenimento per ridurre qualsiasi ulteriore impatto dell'attacco e dell'eliminazione della minaccia alla sicurezza.</span><span class="sxs-lookup"><span data-stu-id="746b9-167">After or during your analysis, perform containment to reduce any additional impact of the attack and eradication of the security threat.</span></span>

3. <span data-ttu-id="746b9-168">Per quanto possibile, eseguire il ripristino dall'attacco ripristinando le risorse del tenant allo stato in cui si trovavano prima dell'incidente.</span><span class="sxs-lookup"><span data-stu-id="746b9-168">As much as possible, recover from the attack by restoring your tenant resources to the state they were in before the incident.</span></span>

4. <span data-ttu-id="746b9-169">[Risolvere](manage-incidents.md#resolve-an-incident) l'evento imprevisto e richiedere tempo per l'apprendimento post-incidente per:</span><span class="sxs-lookup"><span data-stu-id="746b9-169">[Resolve](manage-incidents.md#resolve-an-incident) the incident and take time for post-incident learning to:</span></span>

   - <span data-ttu-id="746b9-170">Comprendere il tipo di attacco e il relativo impatto.</span><span class="sxs-lookup"><span data-stu-id="746b9-170">Understand the type of the attack and its impact.</span></span>
   - <span data-ttu-id="746b9-171">Ricercare l'attacco in [Threat Analytics](threat-analytics.md) e nella community di sicurezza per una tendenza di attacco alla sicurezza.</span><span class="sxs-lookup"><span data-stu-id="746b9-171">Research the attack in [Threat Analytics](threat-analytics.md) and the security community for a security attack trend.</span></span>
   - <span data-ttu-id="746b9-172">Richiamare il flusso di lavoro utilizzato per risolvere l'evento imprevisto e aggiornare i flussi di lavoro, i processi, i criteri e i playbook standard in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="746b9-172">Recall the workflow you used to resolve the incident and update your standard workflows, processes, policies, and playbooks as needed.</span></span>
   - <span data-ttu-id="746b9-173">Determinare se sono necessarie modifiche alla configurazione della sicurezza e implementarle.</span><span class="sxs-lookup"><span data-stu-id="746b9-173">Determine whether changes in your security configuration are needed and implement them.</span></span>

<span data-ttu-id="746b9-174">Se non si ha di [](incidents-overview.md) che fare con l'analisi della sicurezza, vedere l'introduzione alla risposta al primo evento imprevisto per ulteriori informazioni e per analizzare un evento imprevisto di esempio.</span><span class="sxs-lookup"><span data-stu-id="746b9-174">If you are new to security analysis, see the [introduction to responding to your first incident](incidents-overview.md) for additional information and to step through an example incident.</span></span>

## <a name="example-security-operations-for-microsoft-365-defender"></a><span data-ttu-id="746b9-175">Operazioni di sicurezza di esempio per Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="746b9-175">Example security operations for Microsoft 365 Defender</span></span>

<span data-ttu-id="746b9-176">Ecco un esempio di operazioni di sicurezza per Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="746b9-176">Here's an example of security operations for Microsoft 365 Defender.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-example-operations.png" alt-text="Esempio di operazioni di sicurezza per Microsoft 365 Defender":::

<span data-ttu-id="746b9-178">Le attività giornaliere possono includere:</span><span class="sxs-lookup"><span data-stu-id="746b9-178">Daily tasks can include:</span></span>

- <span data-ttu-id="746b9-179">[Gestione](manage-incidents.md) degli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="746b9-179">[Managing](manage-incidents.md) incidents</span></span>
- <span data-ttu-id="746b9-180">Revisione delle [azioni di indagine e risposta automatizzate (AIR)](m365d-action-center.md) nel centro notifiche</span><span class="sxs-lookup"><span data-stu-id="746b9-180">Reviewing [automated investigation and response (AIR)](m365d-action-center.md) actions in the Action center</span></span>
- <span data-ttu-id="746b9-181">Analisi delle minacce più [recenti](threat-analytics.md)</span><span class="sxs-lookup"><span data-stu-id="746b9-181">Reviewing the latest [Threat Analytics](threat-analytics.md)</span></span>
- <span data-ttu-id="746b9-182">[Risposta](investigate-incidents.md) agli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="746b9-182">[Responding](investigate-incidents.md) to incidents</span></span>

<span data-ttu-id="746b9-183">Le attività mensili possono includere:</span><span class="sxs-lookup"><span data-stu-id="746b9-183">Monthly tasks can include:</span></span>

- <span data-ttu-id="746b9-184">Revisione delle [impostazioni AIR](m365d-configure-auto-investigation-response.md)</span><span class="sxs-lookup"><span data-stu-id="746b9-184">Reviewing [AIR settings](m365d-configure-auto-investigation-response.md)</span></span>
- <span data-ttu-id="746b9-185">Esame del [punteggio sicuro e](microsoft-secure-score-improvement-actions.md) della gestione delle & delle [minacce](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)</span><span class="sxs-lookup"><span data-stu-id="746b9-185">Reviewing [Secure Score](microsoft-secure-score-improvement-actions.md) and [Threat & Vulnerability Management](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)</span></span>
- <span data-ttu-id="746b9-186">Creazione di report alla catena di gestione della sicurezza IT</span><span class="sxs-lookup"><span data-stu-id="746b9-186">Reporting to your IT security management chain</span></span>

<span data-ttu-id="746b9-187">Le attività trimestrali possono includere una relazione e un briefing dei risultati della sicurezza al Chief Information Security Officer (CISO).</span><span class="sxs-lookup"><span data-stu-id="746b9-187">Quarterly tasks can include a report and briefing of security results to the Chief Information Security Officer (CISO).</span></span>

<span data-ttu-id="746b9-188">Le attività annuali possono includere l'esecuzione di un grave evento imprevisto o di violazione per testare il personale, i sistemi e i processi.</span><span class="sxs-lookup"><span data-stu-id="746b9-188">Annual tasks can include conducting a major incident or breach exercise to test your staff, systems, and processes.</span></span> 

<span data-ttu-id="746b9-189">Le attività giornaliere, mensili, trimestrali e annuali possono essere utilizzate per aggiornare o perfezionare processi, criteri e configurazioni di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="746b9-189">Daily, monthly, quarterly, and annual tasks can be used to update or refine processes, policies, and security configurations.</span></span>

## <a name="next-steps"></a><span data-ttu-id="746b9-190">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="746b9-190">Next steps</span></span>

<span data-ttu-id="746b9-191">**Se non si ha la novità dell'analisi** della sicurezza e della risposta agli eventi imprevisti:</span><span class="sxs-lookup"><span data-stu-id="746b9-191">**If you are new** to security analysis and incident response:</span></span>

- <span data-ttu-id="746b9-192">Vedere [](first-incident-overview.md) la procedura dettagliata Rispondi al primo evento imprevisto per ottenere una presentazione guidata di un processo tipico di analisi, correzione e revisione post-incidente nel Centro sicurezza Microsoft 365 con un esempio di attacco.</span><span class="sxs-lookup"><span data-stu-id="746b9-192">See the [Respond to your first incident walkthrough](first-incident-overview.md) to get a guided tour of a typical process of analysis, remediation, and post-incident review in the Microsoft 365 security center with an example of an attack.</span></span>

<span data-ttu-id="746b9-193">**Se si ha esperienza con l'analisi** della sicurezza e la risposta agli incidenti:</span><span class="sxs-lookup"><span data-stu-id="746b9-193">**If you have experience** with security analysis and incident response:</span></span>

- <span data-ttu-id="746b9-194">Introduzione alla coda degli eventi imprevisti dalla **pagina** Eventi imprevisti del centro sicurezza Microsoft 365 sicurezza.</span><span class="sxs-lookup"><span data-stu-id="746b9-194">Get started with the incident queue from the **Incidents** page of the Microsoft 365 security center.</span></span> <span data-ttu-id="746b9-195">Da qui è possibile:</span><span class="sxs-lookup"><span data-stu-id="746b9-195">From here, you can:</span></span>

  - <span data-ttu-id="746b9-196">Vedere quali eventi imprevisti devono essere [classificati in](incident-queue.md) base alla gravità e ad altri fattori.</span><span class="sxs-lookup"><span data-stu-id="746b9-196">See which incidents should be [prioritized](incident-queue.md) based on severity and other factors.</span></span> 

  - <span data-ttu-id="746b9-197">[Gestire gli eventi imprevisti,](manage-incidents.md)che includono la ridenominazione, l'assegnazione, la classificazione e l'aggiunta di tag e commenti in base al flusso di lavoro di gestione degli eventi imprevisti.</span><span class="sxs-lookup"><span data-stu-id="746b9-197">[Manage incidents](manage-incidents.md), which includes renaming, assignment, classifying, and adding tags and comments based on your incident management workflow.</span></span>

  - <span data-ttu-id="746b9-198">Eseguire [indagini](investigate-incidents.md) su eventi imprevisti.</span><span class="sxs-lookup"><span data-stu-id="746b9-198">Perform [investigations](investigate-incidents.md) of incidents.</span></span>

- <span data-ttu-id="746b9-199">Vedi questi [playbook di risposta agli eventi imprevisti](/security/compass/incident-response-playbooks) per indicazioni dettagliate su phishing, spray per password e attacchi di concessione del consenso delle app.</span><span class="sxs-lookup"><span data-stu-id="746b9-199">See these [incident response playbooks](/security/compass/incident-response-playbooks) for detailed guidance for phishing, password spray, and app consent grant attacks.</span></span>

