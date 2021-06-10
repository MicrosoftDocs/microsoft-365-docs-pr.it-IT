---
title: Assegnare priorità agli eventi imprevisti in Microsoft 365 Defender
description: Informazioni su come filtrare gli eventi imprevisti dalla coda degli eventi imprevisti in Microsoft 365 Defender
keywords: incidente, coda, panoramica, dispositivi, identità, utenti, cassetta postale, posta elettronica, eventi imprevisti, analizzare, risposta
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
ms.openlocfilehash: df2d2660267c38dccf5ef09fa4955615d3a78141
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636267"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a><span data-ttu-id="d5ecb-104">Assegnare priorità agli eventi imprevisti in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d5ecb-104">Prioritize incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="d5ecb-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="d5ecb-105">**Applies to:**</span></span>
- <span data-ttu-id="d5ecb-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d5ecb-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="d5ecb-107">Microsoft 365 Defender applica l'analisi della correlazione e aggrega gli avvisi correlati e le indagini automatizzate di prodotti diversi in un evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="d5ecb-107">Microsoft 365 Defender applies correlation analytics and aggregates related alerts and automated investigations from different products into an incident.</span></span> <span data-ttu-id="d5ecb-108">Microsoft 365 Defender attiva anche avvisi univoci sulle attività che possono essere identificate solo come dannose, data la visibilità end-to-end che Microsoft 365 Defender ha nell'intera famiglia di prodotti.</span><span class="sxs-lookup"><span data-stu-id="d5ecb-108">Microsoft 365 Defender also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft 365 Defender has across the entire suite of products.</span></span> <span data-ttu-id="d5ecb-109">Questa visualizzazione offre agli analisti della sicurezza la più ampia storia di attacco, che li aiuta a comprendere meglio e gestire le minacce complesse all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d5ecb-109">This view gives your security analysts the broader attack story, which help them better understand and deal with complex threats across your organization.</span></span>

<span data-ttu-id="d5ecb-110">La **coda eventi imprevisti** mostra una raccolta di eventi imprevisti creati su dispositivi, utenti e cassette postali.</span><span class="sxs-lookup"><span data-stu-id="d5ecb-110">The **Incident queue** shows a collection of incidents that were created across devices, users, and mailboxes.</span></span> <span data-ttu-id="d5ecb-111">Ti aiuta a ordinare gli eventi imprevisti in base alla loro priorità e a definire una risposta di cybersecurity mirata.</span><span class="sxs-lookup"><span data-stu-id="d5ecb-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span> 

<span data-ttu-id="d5ecb-112">È possibile accedere alla coda degli eventi imprevisti da **Eventi imprevisti &** avvisi > eventi imprevisti sulla barra di avvio veloce del Centro sicurezza Microsoft 365 ([security.microsoft.com](https://security.microsoft.com)).</span><span class="sxs-lookup"><span data-stu-id="d5ecb-112">You get to the incident queue from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span> <span data-ttu-id="d5ecb-113">Di seguito viene riportato un esempio.</span><span class="sxs-lookup"><span data-stu-id="d5ecb-113">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Esempio di coda degli eventi imprevisti":::

<span data-ttu-id="d5ecb-115">La **sezione Eventi imprevisti e avvisi più** recenti mostra un grafico del numero di avvisi ricevuti e di eventi imprevisti creati nelle ultime 24 ore.</span><span class="sxs-lookup"><span data-stu-id="d5ecb-115">The **Most recent incidents and alerts** section shows a graph of the number of alerts received and incidents created in the last 24 hours.</span></span>

<span data-ttu-id="d5ecb-116">Per impostazione predefinita, nella coda degli eventi imprevisti nel centro sicurezza Microsoft 365 vengono visualizzati gli eventi imprevisti visualizzati negli ultimi sei mesi.</span><span class="sxs-lookup"><span data-stu-id="d5ecb-116">By default, the incident queue in the Microsoft 365 security center displays incidents seen in the last six months.</span></span> <span data-ttu-id="d5ecb-117">L'evento imprevisto più recente si trova all'inizio dell'elenco in modo da poterlo visualizzare per primo.</span><span class="sxs-lookup"><span data-stu-id="d5ecb-117">The most recent incident is at the top of the list so you can see it first.</span></span>

<span data-ttu-id="d5ecb-118">La coda eventi imprevisti include colonne personalizzabili **(selezionare** Scegli colonne) che offrono visibilità sulle diverse caratteristiche dell'evento imprevisto o sulle entità influenzate.</span><span class="sxs-lookup"><span data-stu-id="d5ecb-118">The incident queue has customizable columns (select **Choose columns**) that give you visibility into different characteristics of the incident or the impacted entities.</span></span> <span data-ttu-id="d5ecb-119">Ciò consente di prendere una decisione informata sulla definizione di priorità degli incidenti per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="d5ecb-119">This helps you make an informed decision regarding the prioritization of incidents for analysis.</span></span>

<span data-ttu-id="d5ecb-120">Per una maggiore visibilità a colpo d'occhio, la denominazione automatica degli eventi imprevisti genera nomi di eventi imprevisti in base agli attributi di avviso, ad esempio il numero di endpoint interessati, gli utenti interessati, le origini di rilevamento o le categorie.</span><span class="sxs-lookup"><span data-stu-id="d5ecb-120">For additional visibility at a glance, automatic incident naming generates incident names based on alert attributes such as the number of endpoints affected, users affected, detection sources, or categories.</span></span> <span data-ttu-id="d5ecb-121">In questo modo è possibile comprendere rapidamente l'ambito dell'evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="d5ecb-121">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="d5ecb-122">Ad esempio: *evento imprevisto a più fasi in più endpoint segnalati da più origini.*</span><span class="sxs-lookup"><span data-stu-id="d5ecb-122">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="d5ecb-123">Gli eventi imprevisti che si verificavano prima dell'implementazione della denominazione automatica degli eventi imprevisti non cambieranno il nome.</span><span class="sxs-lookup"><span data-stu-id="d5ecb-123">Incidents that existed prior the rollout of automatic incident naming will not have their name changed.</span></span>

<span data-ttu-id="d5ecb-124">La coda degli eventi imprevisti espone inoltre più opzioni di filtro, che, se applicate, consentono di eseguire un'ampia gamma di tutti gli eventi imprevisti esistenti nell'ambiente o di decidere di concentrarsi su uno scenario o una minaccia specifici.</span><span class="sxs-lookup"><span data-stu-id="d5ecb-124">The incident queue also exposes multiple filtering options, that when applied, enable you to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="d5ecb-125">Applicando i filtri a una coda di eventi imprevisti puoi determinare quale evento richiede un’attenzione immediata.</span><span class="sxs-lookup"><span data-stu-id="d5ecb-125">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="d5ecb-126">Filtri disponibili</span><span class="sxs-lookup"><span data-stu-id="d5ecb-126">Available filters</span></span>

<span data-ttu-id="d5ecb-127">Dalla coda eventi imprevisti predefinita, è possibile selezionare **Filtri** per visualizzare un riquadro Filtri, da cui è possibile visualizzare un set filtrato di eventi imprevisti.</span><span class="sxs-lookup"><span data-stu-id="d5ecb-127">From the default incident queue, you can select **Filters** to see a Filters pane, from which you can view a filtered set of incidents.</span></span> <span data-ttu-id="d5ecb-128">Ecco un esempio.</span><span class="sxs-lookup"><span data-stu-id="d5ecb-128">Here is an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-filters.png" alt-text="Esempio del riquadro dei filtri per la coda eventi imprevisti":::

<span data-ttu-id="d5ecb-130">In questa tabella sono elencati i nomi dei filtri disponibili.</span><span class="sxs-lookup"><span data-stu-id="d5ecb-130">This table lists the filter names that are available.</span></span>

| <span data-ttu-id="d5ecb-131">Nome filtro</span><span class="sxs-lookup"><span data-stu-id="d5ecb-131">Filter name</span></span> | <span data-ttu-id="d5ecb-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d5ecb-132">Description</span></span> |
|:-------|:-----|
| <span data-ttu-id="d5ecb-133">Assegnata a</span><span class="sxs-lookup"><span data-stu-id="d5ecb-133">Assigned to</span></span> | <span data-ttu-id="d5ecb-134">Puoi scegliere di visualizzare gli avvisi assegnati all'utente o a quelli gestiti dall'automazione.</span><span class="sxs-lookup"><span data-stu-id="d5ecb-134">You can choose to show alerts that are assigned to you or those handled by automation.</span></span> |
| <span data-ttu-id="d5ecb-135">Categorie</span><span class="sxs-lookup"><span data-stu-id="d5ecb-135">Categories</span></span> | <span data-ttu-id="d5ecb-136">Scegli le categorie per concentrarti su tattiche, tecniche o componenti di attacco specifici.</span><span class="sxs-lookup"><span data-stu-id="d5ecb-136">Choose categories to focus on specific tactics, techniques, or attack components seen.</span></span> |
| <span data-ttu-id="d5ecb-137">Classificazione</span><span class="sxs-lookup"><span data-stu-id="d5ecb-137">Classification</span></span> | <span data-ttu-id="d5ecb-138">Filtrare gli eventi imprevisti in base alle classificazioni impostate degli avvisi correlati.</span><span class="sxs-lookup"><span data-stu-id="d5ecb-138">Filter incidents based on the set classifications of the related alerts.</span></span> <span data-ttu-id="d5ecb-139">I valori includono avvisi true, falsi avvisi o non impostati.</span><span class="sxs-lookup"><span data-stu-id="d5ecb-139">The values include true alerts, false alerts, or not set.</span></span> |
| <span data-ttu-id="d5ecb-140">Riservatezza dei dati</span><span class="sxs-lookup"><span data-stu-id="d5ecb-140">Data sensitivity</span></span> | <span data-ttu-id="d5ecb-141">Alcuni attacchi sono incentrati sull’estrazione di dati riservati o di valore.</span><span class="sxs-lookup"><span data-stu-id="d5ecb-141">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="d5ecb-142">Applicando un filtro per vedere se sono coinvolte informazioni riservate nell'evento, puoi determinare rapidamente se le informazioni riservate sono potenzialmente compromesse e assegnare priorità all'intervento.</span><span class="sxs-lookup"><span data-stu-id="d5ecb-142">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span> <br><br> <span data-ttu-id="d5ecb-143">Applicabile solo se Microsoft Information Protection è attivo.</span><span class="sxs-lookup"><span data-stu-id="d5ecb-143">Only applicable if Microsoft Information Protection is turned on.</span></span>|
| <span data-ttu-id="d5ecb-144">Gruppo di dispositivi</span><span class="sxs-lookup"><span data-stu-id="d5ecb-144">Device group</span></span> | <span data-ttu-id="d5ecb-145">Filtra in base ai gruppi di dispositivi definiti.</span><span class="sxs-lookup"><span data-stu-id="d5ecb-145">Filter by defined device groups.</span></span> |
| <span data-ttu-id="d5ecb-146">Stato dell'indagine</span><span class="sxs-lookup"><span data-stu-id="d5ecb-146">Investigation state</span></span> | <span data-ttu-id="d5ecb-147">Filtra gli incidenti in base allo stato dell'indagine automatizzata.</span><span class="sxs-lookup"><span data-stu-id="d5ecb-147">Filter incidents by the status of automated investigation.</span></span>  |
| <span data-ttu-id="d5ecb-148">Più categorie</span><span class="sxs-lookup"><span data-stu-id="d5ecb-148">Multiple categories</span></span> | <span data-ttu-id="d5ecb-149">È possibile scegliere di visualizzare solo gli eventi imprevisti mappati a più categorie e quindi causare più danni.</span><span class="sxs-lookup"><span data-stu-id="d5ecb-149">You can choose to see only incidents that have mapped to multiple categories  and can thus potentially cause more damage.</span></span> |
| <span data-ttu-id="d5ecb-150">Più servizi di origine</span><span class="sxs-lookup"><span data-stu-id="d5ecb-150">Multiple service sources</span></span>  | <span data-ttu-id="d5ecb-151">Filtra per visualizzare solo gli eventi imprevisti che contengono avvisi da origini diverse (Microsoft Defender per Endpoint, Microsoft Cloud App Security, Microsoft Defender per l'identità, Microsoft Defender per Office 365).</span><span class="sxs-lookup"><span data-stu-id="d5ecb-151">Filter to only see incidents that contain alerts from different sources (Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender for Office 365).</span></span> |
| <span data-ttu-id="d5ecb-152">Piattaforma del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="d5ecb-152">OS platform</span></span> | <span data-ttu-id="d5ecb-153">Limitare la visualizzazione della coda degli eventi imprevisti in base al sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="d5ecb-153">Limit the incident queue view by operating system.</span></span> |
| <span data-ttu-id="d5ecb-154">Servizi di origine</span><span class="sxs-lookup"><span data-stu-id="d5ecb-154">Service sources</span></span> | <span data-ttu-id="d5ecb-155">Scegliendo un’origine specifica puoi concentrarti sugli eventi imprevisti che contengono almeno un avviso dall'origine selezionata.</span><span class="sxs-lookup"><span data-stu-id="d5ecb-155">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> |
| <span data-ttu-id="d5ecb-156">Gravità</span><span class="sxs-lookup"><span data-stu-id="d5ecb-156">Severity</span></span> | <span data-ttu-id="d5ecb-157">La gravità di un incidente è indicativa dell'impatto che può avere sulle risorse.</span><span class="sxs-lookup"><span data-stu-id="d5ecb-157">The severity of an incident is indicative of the impact it can have on your assets.</span></span> <span data-ttu-id="d5ecb-158">Maggiore è la gravità, maggiore è l'impatto e in genere richiede l'attenzione più immediata.</span><span class="sxs-lookup"><span data-stu-id="d5ecb-158">The higher the severity, the bigger the impact and typically requires the most immediate attention.</span></span> |
| <span data-ttu-id="d5ecb-159">Stato</span><span class="sxs-lookup"><span data-stu-id="d5ecb-159">Status</span></span> | <span data-ttu-id="d5ecb-160">Puoi scegliere di limitare l'elenco degli eventi imprevisti visualizzati in base al loro stato per vedere quali sono attivi o risolti.</span><span class="sxs-lookup"><span data-stu-id="d5ecb-160">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span> |
|||

## <a name="next-steps"></a><span data-ttu-id="d5ecb-161">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="d5ecb-161">Next steps</span></span>

<span data-ttu-id="d5ecb-162">Dopo aver determinato quale evento imprevisto richiede la priorità più alta, selezionarlo e:</span><span class="sxs-lookup"><span data-stu-id="d5ecb-162">After you've determined which incident requires the highest priority, select it and:</span></span>

- <span data-ttu-id="d5ecb-163">[Gestire](manage-incidents.md) le proprietà dell'evento imprevisto per tag, assegnazione, risoluzione immediata per incidenti falsi positivi e commenti.</span><span class="sxs-lookup"><span data-stu-id="d5ecb-163">[Manage](manage-incidents.md) the properties of the incident for tags, assignment, immediate resolution for false positive incidents, and comments.</span></span>
- <span data-ttu-id="d5ecb-164">Iniziare le [indagini](investigate-incidents.md).</span><span class="sxs-lookup"><span data-stu-id="d5ecb-164">Begin your [investigations](investigate-incidents.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d5ecb-165">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d5ecb-165">See also</span></span>
- [<span data-ttu-id="d5ecb-166">Panoramica degli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="d5ecb-166">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="d5ecb-167">Gestire gli incidenti</span><span class="sxs-lookup"><span data-stu-id="d5ecb-167">Manage incidents</span></span>](manage-incidents.md)
- [<span data-ttu-id="d5ecb-168">Indagare sugli incidenti</span><span class="sxs-lookup"><span data-stu-id="d5ecb-168">Investigate incidents</span></span>](investigate-incidents.md)
