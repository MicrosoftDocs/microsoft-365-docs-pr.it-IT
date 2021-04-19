---
title: Assegnare priorità agli incidenti in Microsoft 365 Defender
description: Informazioni su come filtrare gli eventi imprevisti dalla coda degli eventi imprevisti in Microsoft 365 Defender
keywords: evento imprevisto, coda, panoramica, dispositivi, identità, utenti, cassetta postale, posta elettronica, eventi imprevisti
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
ms.openlocfilehash: 3b381749108d4a75024d9a546c0d3f1631c948ed
ms.sourcegitcommit: 76f3c75413cc960289489d0ca29efadb8a9a5b31
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/19/2021
ms.locfileid: "51887258"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a><span data-ttu-id="42067-104">Assegnare priorità agli incidenti in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="42067-104">Prioritize incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="42067-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="42067-105">**Applies to:**</span></span>
- <span data-ttu-id="42067-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="42067-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="42067-107">Microsoft 365 Defender applica l'analisi della correlazione e aggrega gli avvisi correlati e le indagini automatizzate di prodotti diversi in un evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="42067-107">Microsoft 365 Defender applies correlation analytics and aggregates related alerts and automated investigations from different products into an incident.</span></span> <span data-ttu-id="42067-108">Microsoft 365 Defender attiva anche avvisi univoci sulle attività che possono essere identificate come dannose solo in base alla visibilità end-to-end che Microsoft 365 Defender ha nell'intera famiglia di prodotti.</span><span class="sxs-lookup"><span data-stu-id="42067-108">Microsoft 365 Defender also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft 365 Defender has across the entire suite of products.</span></span> <span data-ttu-id="42067-109">Questa visualizzazione offre agli analisti della sicurezza la più ampia storia di attacco, che li aiuta a comprendere meglio e gestire le minacce complesse all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="42067-109">This view gives your security analysts the broader attack story, which help them better understand and deal with complex threats across your organization.</span></span>

<span data-ttu-id="42067-110">La **coda eventi imprevisti** mostra una raccolta di eventi imprevisti creati su dispositivi, utenti e cassette postali.</span><span class="sxs-lookup"><span data-stu-id="42067-110">The **Incident queue** shows a collection of incidents that were created across devices, users, and mailboxes.</span></span> <span data-ttu-id="42067-111">Ti aiuta a ordinare gli eventi imprevisti in base alla loro priorità e a definire una risposta di cybersecurity mirata.</span><span class="sxs-lookup"><span data-stu-id="42067-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span> 

<span data-ttu-id="42067-112">È possibile accedere alla coda degli eventi imprevisti da Eventi imprevisti & avvisi **> eventi** imprevisti sulla barra di avvio veloce del Centro sicurezza Microsoft 365 ([security.microsoft.com](https://security.microsoft.com)).</span><span class="sxs-lookup"><span data-stu-id="42067-112">You get to the incident queue from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Esempio di coda degli eventi imprevisti":::

<span data-ttu-id="42067-114">Per impostazione predefinita, nella coda degli eventi imprevisti nel Centro sicurezza Microsoft 365 vengono visualizzati gli eventi imprevisti visualizzati negli ultimi sei mesi.</span><span class="sxs-lookup"><span data-stu-id="42067-114">By default, the incident queue in the Microsoft 365 security center displays incidents seen in the last six months.</span></span> <span data-ttu-id="42067-115">L'evento imprevisto più recente si trova all'inizio dell'elenco in modo da poterlo visualizzare per primo.</span><span class="sxs-lookup"><span data-stu-id="42067-115">The most recent incident is at the top of the list so you can see it first.</span></span>

<span data-ttu-id="42067-116">La coda eventi imprevisti include colonne personalizzabili **(selezionare** Scegli colonne) che offrono visibilità sulle diverse caratteristiche dell'evento imprevisto o sulle entità influenzate.</span><span class="sxs-lookup"><span data-stu-id="42067-116">The incident queue has customizable columns (select **Choose columns**) that give you visibility into different characteristics of the incident or the impacted entities.</span></span> <span data-ttu-id="42067-117">Ciò consente di prendere una decisione informata sulla definizione di priorità degli incidenti per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="42067-117">This helps you make an informed decision regarding the prioritization of incidents for analysis.</span></span>

<span data-ttu-id="42067-118">Per una maggiore visibilità a colpo d'occhio, la denominazione automatica degli eventi imprevisti genera nomi di eventi imprevisti in base agli attributi di avviso, ad esempio il numero di endpoint interessati, gli utenti interessati, le origini di rilevamento o le categorie.</span><span class="sxs-lookup"><span data-stu-id="42067-118">For additional visibility at a glance, automatic incident naming generates incident names based on alert attributes such as the number of endpoints affected, users affected, detection sources, or categories.</span></span> <span data-ttu-id="42067-119">In questo modo è possibile comprendere rapidamente l'ambito dell'evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="42067-119">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="42067-120">Ad esempio: *evento imprevisto a più fasi in più endpoint segnalati da più origini.*</span><span class="sxs-lookup"><span data-stu-id="42067-120">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="42067-121">Gli eventi imprevisti che si verificavano prima dell'implementazione della denominazione automatica degli eventi imprevisti non cambieranno il nome.</span><span class="sxs-lookup"><span data-stu-id="42067-121">Incidents that existed prior the rollout of automatic incident naming will not have their name changed.</span></span>

<span data-ttu-id="42067-122">La coda degli eventi imprevisti espone inoltre più opzioni di filtro, che, se applicate, consentono di eseguire un'ampia gamma di tutti gli eventi imprevisti esistenti nell'ambiente o di decidere di concentrarsi su uno scenario o una minaccia specifici.</span><span class="sxs-lookup"><span data-stu-id="42067-122">The incident queue also exposes multiple filtering options, that when applied, enable you to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="42067-123">Applicando i filtri a una coda di eventi imprevisti puoi determinare quale evento richiede un’attenzione immediata.</span><span class="sxs-lookup"><span data-stu-id="42067-123">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="42067-124">Filtri disponibili</span><span class="sxs-lookup"><span data-stu-id="42067-124">Available filters</span></span>

<span data-ttu-id="42067-125">Dalla coda eventi imprevisti predefinita, è possibile selezionare **Filtri** per visualizzare un riquadro Filtri, da cui è possibile visualizzare un set filtrato di eventi imprevisti.</span><span class="sxs-lookup"><span data-stu-id="42067-125">From the default incident queue, you can select **Filters** to see a Filters pane, from which you can view a filtered set of incidents.</span></span> <span data-ttu-id="42067-126">Ecco un esempio.</span><span class="sxs-lookup"><span data-stu-id="42067-126">Here is an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-filters.png" alt-text="Esempio del riquadro dei filtri per la coda eventi imprevisti":::

<span data-ttu-id="42067-128">In questa tabella sono elencati i nomi dei filtri disponibili.</span><span class="sxs-lookup"><span data-stu-id="42067-128">This table lists the filter names that are available.</span></span>

| <span data-ttu-id="42067-129">Nome filtro</span><span class="sxs-lookup"><span data-stu-id="42067-129">Filter name</span></span> | <span data-ttu-id="42067-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="42067-130">Description</span></span> |
|:-------|:-----|
| <span data-ttu-id="42067-131">Assegnata a</span><span class="sxs-lookup"><span data-stu-id="42067-131">Assigned to</span></span> | <span data-ttu-id="42067-132">Puoi scegliere di visualizzare gli avvisi assegnati all'utente o a quelli gestiti dall'automazione.</span><span class="sxs-lookup"><span data-stu-id="42067-132">You can choose to show alerts that are assigned to you or those handled by automation.</span></span> |
| <span data-ttu-id="42067-133">Categorie</span><span class="sxs-lookup"><span data-stu-id="42067-133">Categories</span></span> | <span data-ttu-id="42067-134">Scegli le categorie per concentrarti su tattiche, tecniche o componenti di attacco specifici.</span><span class="sxs-lookup"><span data-stu-id="42067-134">Choose categories to focus on specific tactics, techniques, or attack components seen.</span></span> |
| <span data-ttu-id="42067-135">Classificazione</span><span class="sxs-lookup"><span data-stu-id="42067-135">Classification</span></span> | <span data-ttu-id="42067-136">Filtrare gli eventi imprevisti in base alle classificazioni impostate degli avvisi correlati.</span><span class="sxs-lookup"><span data-stu-id="42067-136">Filter incidents based on the set classifications of the related alerts.</span></span> <span data-ttu-id="42067-137">I valori includono avvisi true, falsi avvisi o non impostati.</span><span class="sxs-lookup"><span data-stu-id="42067-137">The values include true alerts, false alerts, or not set.</span></span> |
| <span data-ttu-id="42067-138">Riservatezza dei dati</span><span class="sxs-lookup"><span data-stu-id="42067-138">Data sensitivity</span></span> | <span data-ttu-id="42067-139">Alcuni attacchi sono incentrati sull’estrazione di dati riservati o di valore.</span><span class="sxs-lookup"><span data-stu-id="42067-139">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="42067-140">Applicando un filtro per vedere se sono coinvolte informazioni riservate nell'evento, puoi determinare rapidamente se le informazioni riservate sono potenzialmente compromesse e assegnare priorità all'intervento.</span><span class="sxs-lookup"><span data-stu-id="42067-140">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span> <br><br> <span data-ttu-id="42067-141">Applicabile solo se Microsoft Information Protection è attivo.</span><span class="sxs-lookup"><span data-stu-id="42067-141">Only applicable if Microsoft Information Protection is turned on.</span></span>|
| <span data-ttu-id="42067-142">Gruppo di dispositivi</span><span class="sxs-lookup"><span data-stu-id="42067-142">Device group</span></span> | <span data-ttu-id="42067-143">Filtra in base ai gruppi di dispositivi definiti.</span><span class="sxs-lookup"><span data-stu-id="42067-143">Filter by defined device groups.</span></span> |
| <span data-ttu-id="42067-144">Stato dell'indagine</span><span class="sxs-lookup"><span data-stu-id="42067-144">Investigation state</span></span> | <span data-ttu-id="42067-145">Filtra gli incidenti in base allo stato dell'indagine automatizzata.</span><span class="sxs-lookup"><span data-stu-id="42067-145">Filter incidents by the status of automated investigation.</span></span>  |
| <span data-ttu-id="42067-146">Più categorie</span><span class="sxs-lookup"><span data-stu-id="42067-146">Multiple categories</span></span> | <span data-ttu-id="42067-147">È possibile scegliere di visualizzare solo gli eventi imprevisti mappati a più categorie e quindi causare più danni.</span><span class="sxs-lookup"><span data-stu-id="42067-147">You can choose to see only incidents that have mapped to multiple categories  and can thus potentially cause more damage.</span></span> |
| <span data-ttu-id="42067-148">Più servizi di origine</span><span class="sxs-lookup"><span data-stu-id="42067-148">Multiple service sources</span></span>  | <span data-ttu-id="42067-149">Filtra per visualizzare solo gli eventi imprevisti che contengono avvisi da origini diverse (Microsoft Defender per Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender per Office 365).</span><span class="sxs-lookup"><span data-stu-id="42067-149">Filter to only see incidents that contain alerts from different sources (Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender for Office 365).</span></span> |
| <span data-ttu-id="42067-150">Piattaforma del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="42067-150">OS platform</span></span> | <span data-ttu-id="42067-151">Limitare la visualizzazione della coda degli eventi imprevisti in base al sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="42067-151">Limit the incident queue view by operating system.</span></span> |
| <span data-ttu-id="42067-152">Servizi di origine</span><span class="sxs-lookup"><span data-stu-id="42067-152">Service sources</span></span> | <span data-ttu-id="42067-153">Scegliendo un’origine specifica puoi concentrarti sugli eventi imprevisti che contengono almeno un avviso dall'origine selezionata.</span><span class="sxs-lookup"><span data-stu-id="42067-153">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> |
| <span data-ttu-id="42067-154">Gravità</span><span class="sxs-lookup"><span data-stu-id="42067-154">Severity</span></span> | <span data-ttu-id="42067-155">La gravità di un incidente è indicativa dell'impatto che può avere sulle risorse.</span><span class="sxs-lookup"><span data-stu-id="42067-155">The severity of an incident is indicative of the impact it can have on your assets.</span></span> <span data-ttu-id="42067-156">Maggiore è la gravità, maggiore è l'impatto e in genere richiede l'attenzione più immediata.</span><span class="sxs-lookup"><span data-stu-id="42067-156">The higher the severity, the bigger the impact and typically requires the most immediate attention.</span></span> |
| <span data-ttu-id="42067-157">Stato</span><span class="sxs-lookup"><span data-stu-id="42067-157">Status</span></span> | <span data-ttu-id="42067-158">Puoi scegliere di limitare l'elenco degli eventi imprevisti visualizzati in base al loro stato per vedere quali sono attivi o risolti.</span><span class="sxs-lookup"><span data-stu-id="42067-158">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span> |
|||

## <a name="incident-response-workflow"></a><span data-ttu-id="42067-159">Flusso di lavoro di risposta agli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="42067-159">Incident response workflow</span></span>

<span data-ttu-id="42067-160">Ecco il flusso di lavoro tipico per rispondere agli eventi imprevisti:</span><span class="sxs-lookup"><span data-stu-id="42067-160">Here's the typical workflow for responding to incidents:</span></span>

1. <span data-ttu-id="42067-161">Identificare e individuare gli incidenti con la priorità più alta per l'indagine e la risoluzione.</span><span class="sxs-lookup"><span data-stu-id="42067-161">Identify and triage the highest priority incidents for investigation and resolution.</span></span>
2. <span data-ttu-id="42067-162">Per ogni incidente ad alta priorità, avviare [un'indagine:](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="42067-162">For each high-priority incident, begin an [investigation](investigate-incidents.md):</span></span>

   <span data-ttu-id="42067-163">a.</span><span class="sxs-lookup"><span data-stu-id="42067-163">a.</span></span> <span data-ttu-id="42067-164">Visualizzare il riepilogo dell'evento imprevisto per comprendere l'ambito e la gravità e le entità interessate **(scheda** Riepilogo).</span><span class="sxs-lookup"><span data-stu-id="42067-164">View the summary of the incident to understand it's scope and severity and what entities are affected (the **Summary** tab).</span></span>

   <span data-ttu-id="42067-165">b.</span><span class="sxs-lookup"><span data-stu-id="42067-165">b.</span></span> <span data-ttu-id="42067-166">Iniziare a visualizzare gli avvisi per comprenderne l'origine, l'ambito e la gravità **(scheda** Avvisi).</span><span class="sxs-lookup"><span data-stu-id="42067-166">Begin looking at the alerts to understand their origin, scope, and severity (the **Alerts** tab).</span></span>

   <span data-ttu-id="42067-167">c.</span><span class="sxs-lookup"><span data-stu-id="42067-167">c.</span></span> <span data-ttu-id="42067-168">In base alle esigenze, raccogliere informazioni sui dispositivi, gli utenti e le cassette postali influenzati (le schede **Dispositivi,** **Utenti** e **Cassette** postali).</span><span class="sxs-lookup"><span data-stu-id="42067-168">As needed, gather information on impacted devices, users, and mailboxes (the **Devices**, **Users**, and **Mailboxes** tabs).</span></span>

   <span data-ttu-id="42067-169">d.</span><span class="sxs-lookup"><span data-stu-id="42067-169">d.</span></span> <span data-ttu-id="42067-170">Scopri come Microsoft 365 Defender ha risolto automaticamente alcuni avvisi **(scheda** Indagini).</span><span class="sxs-lookup"><span data-stu-id="42067-170">See how Microsoft 365 Defender has automatically resolved some alerts (the **Investigations** tab).</span></span>
   
   <span data-ttu-id="42067-171">e.</span><span class="sxs-lookup"><span data-stu-id="42067-171">e.</span></span> <span data-ttu-id="42067-172">Se necessario, usare le informazioni nel set di dati per l'evento imprevisto per ulteriori informazioni (scheda **Prova e** risposta).</span><span class="sxs-lookup"><span data-stu-id="42067-172">As needed, use information in the data set for the incident for more information (the **Evidence and Response** tab).</span></span>

   <span data-ttu-id="42067-173">Durante l'analisi, è necessario preoccuparsi di:</span><span class="sxs-lookup"><span data-stu-id="42067-173">As you investigate, you should be concerned with:</span></span>

   - <span data-ttu-id="42067-174">Containment: riduzione di qualsiasi ulteriore impatto sul tenant.</span><span class="sxs-lookup"><span data-stu-id="42067-174">Containment: Reducing any additional impact on your tenant.</span></span>
   - <span data-ttu-id="42067-175">Eliminazione: rimozione della minaccia alla sicurezza.</span><span class="sxs-lookup"><span data-stu-id="42067-175">Eradication: Removing the security threat.</span></span>
   - <span data-ttu-id="42067-176">Ripristino: ripristino delle risorse del tenant allo stato in cui si trovavano prima dell'evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="42067-176">Recovery: Restoring your tenant resources to the state they were in before the incident.</span></span>

3. <span data-ttu-id="42067-177">Dopo aver risolto l'evento imprevisto, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="42067-177">After you resolve the incident, take the time to:</span></span>

   - <span data-ttu-id="42067-178">Comprendere il tipo di attacco e il relativo impatto.</span><span class="sxs-lookup"><span data-stu-id="42067-178">Understand the type of the attack and its impact.</span></span>
   - <span data-ttu-id="42067-179">Ricercare l'attacco nella community di sicurezza per una tendenza di attacco alla sicurezza.</span><span class="sxs-lookup"><span data-stu-id="42067-179">Research the attack in the security community for a security attack trend.</span></span>
   - <span data-ttu-id="42067-180">Richiamare il flusso di lavoro utilizzato per risolvere l'evento imprevisto e aggiornare i flussi di lavoro e i playbook standard in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="42067-180">Recall the workflow you used to resolve the incident and update your standard workflows and playbooks as needed.</span></span>
   - <span data-ttu-id="42067-181">Determinare se sono necessarie modifiche alla sicurezza ed eseguire le operazioni necessarie per implementarle.</span><span class="sxs-lookup"><span data-stu-id="42067-181">Determine whether changes in your security posture are needed and take the steps to implement them.</span></span>

<span data-ttu-id="42067-182">Ecco un riepilogo del processo di base.</span><span class="sxs-lookup"><span data-stu-id="42067-182">Here's a summary of the basic process.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-process.png" alt-text="Processo di base per l'analisi degli incidenti":::

## <a name="next-step"></a><span data-ttu-id="42067-184">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="42067-184">Next step</span></span>

<span data-ttu-id="42067-185">Dopo aver determinato quale evento imprevisto richiede la priorità più alta, selezionarlo e avviare [l'indagine.](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="42067-185">After you've determined which incident requires the highest priority, select it and begin your [investigation](investigate-incidents.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="42067-186">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="42067-186">See also</span></span>
- [<span data-ttu-id="42067-187">Panoramica degli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="42067-187">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="42067-188">Indagare sugli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="42067-188">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="42067-189">Gestire gli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="42067-189">Manage incidents</span></span>](manage-incidents.md)
