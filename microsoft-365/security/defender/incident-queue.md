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
ms.openlocfilehash: 07a49fcdcfa7ea401b16b293b4831244253d2b28
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925888"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a><span data-ttu-id="cd1ae-104">Assegnare priorità agli eventi imprevisti in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cd1ae-104">Prioritize incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="cd1ae-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="cd1ae-105">**Applies to:**</span></span>
- <span data-ttu-id="cd1ae-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cd1ae-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="cd1ae-107">Microsoft 365 Defender applica l'analisi della correlazione e aggrega gli avvisi correlati e le indagini automatizzate di prodotti diversi in un evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="cd1ae-107">Microsoft 365 Defender applies correlation analytics and aggregates related alerts and automated investigations from different products into an incident.</span></span> <span data-ttu-id="cd1ae-108">Microsoft 365 Defender attiva anche avvisi univoci sulle attività che possono essere identificate solo come dannose, data la visibilità end-to-end che Microsoft 365 Defender ha nell'intera famiglia di prodotti.</span><span class="sxs-lookup"><span data-stu-id="cd1ae-108">Microsoft 365 Defender also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft 365 Defender has across the entire suite of products.</span></span> <span data-ttu-id="cd1ae-109">Questa visualizzazione offre agli analisti della sicurezza la più ampia storia di attacco, che li aiuta a comprendere meglio e gestire le minacce complesse all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="cd1ae-109">This view gives your security analysts the broader attack story, which help them better understand and deal with complex threats across your organization.</span></span>

<span data-ttu-id="cd1ae-110">La **coda eventi imprevisti** mostra una raccolta di eventi imprevisti creati su dispositivi, utenti e cassette postali.</span><span class="sxs-lookup"><span data-stu-id="cd1ae-110">The **Incident queue** shows a collection of incidents that were created across devices, users, and mailboxes.</span></span> <span data-ttu-id="cd1ae-111">Ti aiuta a ordinare gli eventi imprevisti in base alla loro priorità e a definire una risposta di cybersecurity mirata.</span><span class="sxs-lookup"><span data-stu-id="cd1ae-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span> 

<span data-ttu-id="cd1ae-112">È possibile accedere alla coda degli eventi imprevisti da **Eventi imprevisti &** avvisi > eventi imprevisti sulla barra di avvio veloce del Centro sicurezza Microsoft 365 ([security.microsoft.com](https://security.microsoft.com)).</span><span class="sxs-lookup"><span data-stu-id="cd1ae-112">You get to the incident queue from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span> <span data-ttu-id="cd1ae-113">Di seguito viene riportato un esempio.</span><span class="sxs-lookup"><span data-stu-id="cd1ae-113">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Esempio di coda degli eventi imprevisti":::

<span data-ttu-id="cd1ae-115">La **sezione Eventi imprevisti e avvisi più** recenti mostra un grafico del numero di avvisi ricevuti e di eventi imprevisti creati nelle ultime 24 ore.</span><span class="sxs-lookup"><span data-stu-id="cd1ae-115">The **Most recent incidents and alerts** section shows a graph of the number of alerts received and incidents created in the last 24 hours.</span></span>

<span data-ttu-id="cd1ae-116">Per impostazione predefinita, nella coda degli eventi imprevisti nel centro sicurezza Microsoft 365 vengono visualizzati gli eventi imprevisti visualizzati negli ultimi sei mesi.</span><span class="sxs-lookup"><span data-stu-id="cd1ae-116">By default, the incident queue in the Microsoft 365 security center displays incidents seen in the last six months.</span></span> <span data-ttu-id="cd1ae-117">L'evento imprevisto più recente si trova all'inizio dell'elenco in modo da poterlo visualizzare per primo.</span><span class="sxs-lookup"><span data-stu-id="cd1ae-117">The most recent incident is at the top of the list so you can see it first.</span></span>

<span data-ttu-id="cd1ae-118">La coda eventi imprevisti include colonne personalizzabili **(selezionare** Scegli colonne) che offrono visibilità sulle diverse caratteristiche dell'evento imprevisto o sulle entità influenzate.</span><span class="sxs-lookup"><span data-stu-id="cd1ae-118">The incident queue has customizable columns (select **Choose columns**) that give you visibility into different characteristics of the incident or the impacted entities.</span></span> <span data-ttu-id="cd1ae-119">Ciò consente di prendere una decisione informata sulla definizione di priorità degli incidenti per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="cd1ae-119">This helps you make an informed decision regarding the prioritization of incidents for analysis.</span></span>

<span data-ttu-id="cd1ae-120">Per una maggiore visibilità a colpo d'occhio, la denominazione automatica degli eventi imprevisti genera nomi di eventi imprevisti in base agli attributi di avviso, ad esempio il numero di endpoint interessati, gli utenti interessati, le origini di rilevamento o le categorie.</span><span class="sxs-lookup"><span data-stu-id="cd1ae-120">For additional visibility at a glance, automatic incident naming generates incident names based on alert attributes such as the number of endpoints affected, users affected, detection sources, or categories.</span></span> <span data-ttu-id="cd1ae-121">In questo modo è possibile comprendere rapidamente l'ambito dell'evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="cd1ae-121">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="cd1ae-122">Ad esempio: *evento imprevisto a più fasi in più endpoint segnalati da più origini.*</span><span class="sxs-lookup"><span data-stu-id="cd1ae-122">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="cd1ae-123">Gli eventi imprevisti che si verificavano prima dell'implementazione della denominazione automatica degli eventi imprevisti non cambieranno il nome.</span><span class="sxs-lookup"><span data-stu-id="cd1ae-123">Incidents that existed prior the rollout of automatic incident naming will not have their name changed.</span></span>

<span data-ttu-id="cd1ae-124">La coda degli eventi imprevisti espone inoltre più opzioni di filtro, che, se applicate, consentono di eseguire un'ampia gamma di tutti gli eventi imprevisti esistenti nell'ambiente o di decidere di concentrarsi su uno scenario o una minaccia specifici.</span><span class="sxs-lookup"><span data-stu-id="cd1ae-124">The incident queue also exposes multiple filtering options, that when applied, enable you to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="cd1ae-125">Applicando i filtri a una coda di eventi imprevisti puoi determinare quale evento richiede un’attenzione immediata.</span><span class="sxs-lookup"><span data-stu-id="cd1ae-125">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="cd1ae-126">Filtri disponibili</span><span class="sxs-lookup"><span data-stu-id="cd1ae-126">Available filters</span></span>

<span data-ttu-id="cd1ae-127">Dalla coda eventi imprevisti predefinita, è possibile selezionare **Filtri** per visualizzare un riquadro Filtri, da cui è possibile visualizzare un set filtrato di eventi imprevisti.</span><span class="sxs-lookup"><span data-stu-id="cd1ae-127">From the default incident queue, you can select **Filters** to see a Filters pane, from which you can view a filtered set of incidents.</span></span> <span data-ttu-id="cd1ae-128">Ecco un esempio.</span><span class="sxs-lookup"><span data-stu-id="cd1ae-128">Here is an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-filters.png" alt-text="Esempio del riquadro dei filtri per la coda eventi imprevisti":::

<span data-ttu-id="cd1ae-130">In questa tabella sono elencati i nomi dei filtri disponibili.</span><span class="sxs-lookup"><span data-stu-id="cd1ae-130">This table lists the filter names that are available.</span></span>

| <span data-ttu-id="cd1ae-131">Nome filtro</span><span class="sxs-lookup"><span data-stu-id="cd1ae-131">Filter name</span></span> | <span data-ttu-id="cd1ae-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cd1ae-132">Description</span></span> |
|:-------|:-----|
| <span data-ttu-id="cd1ae-133">Assegnata a</span><span class="sxs-lookup"><span data-stu-id="cd1ae-133">Assigned to</span></span> | <span data-ttu-id="cd1ae-134">Puoi scegliere di visualizzare gli avvisi assegnati all'utente o a quelli gestiti dall'automazione.</span><span class="sxs-lookup"><span data-stu-id="cd1ae-134">You can choose to show alerts that are assigned to you or those handled by automation.</span></span> |
| <span data-ttu-id="cd1ae-135">Categorie</span><span class="sxs-lookup"><span data-stu-id="cd1ae-135">Categories</span></span> | <span data-ttu-id="cd1ae-136">Scegli le categorie per concentrarti su tattiche, tecniche o componenti di attacco specifici.</span><span class="sxs-lookup"><span data-stu-id="cd1ae-136">Choose categories to focus on specific tactics, techniques, or attack components seen.</span></span> |
| <span data-ttu-id="cd1ae-137">Classificazione</span><span class="sxs-lookup"><span data-stu-id="cd1ae-137">Classification</span></span> | <span data-ttu-id="cd1ae-138">Filtrare gli eventi imprevisti in base alle classificazioni impostate degli avvisi correlati.</span><span class="sxs-lookup"><span data-stu-id="cd1ae-138">Filter incidents based on the set classifications of the related alerts.</span></span> <span data-ttu-id="cd1ae-139">I valori includono avvisi true, falsi avvisi o non impostati.</span><span class="sxs-lookup"><span data-stu-id="cd1ae-139">The values include true alerts, false alerts, or not set.</span></span> |
| <span data-ttu-id="cd1ae-140">Riservatezza dei dati</span><span class="sxs-lookup"><span data-stu-id="cd1ae-140">Data sensitivity</span></span> | <span data-ttu-id="cd1ae-141">Alcuni attacchi sono incentrati sull’estrazione di dati riservati o di valore.</span><span class="sxs-lookup"><span data-stu-id="cd1ae-141">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="cd1ae-142">Applicando un filtro per vedere se sono coinvolte informazioni riservate nell'evento, puoi determinare rapidamente se le informazioni riservate sono potenzialmente compromesse e assegnare priorità all'intervento.</span><span class="sxs-lookup"><span data-stu-id="cd1ae-142">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span> <br><br> <span data-ttu-id="cd1ae-143">Applicabile solo se Microsoft Information Protection è attivo.</span><span class="sxs-lookup"><span data-stu-id="cd1ae-143">Only applicable if Microsoft Information Protection is turned on.</span></span>|
| <span data-ttu-id="cd1ae-144">Gruppo di dispositivi</span><span class="sxs-lookup"><span data-stu-id="cd1ae-144">Device group</span></span> | <span data-ttu-id="cd1ae-145">Filtra in base ai gruppi di dispositivi definiti.</span><span class="sxs-lookup"><span data-stu-id="cd1ae-145">Filter by defined device groups.</span></span> |
| <span data-ttu-id="cd1ae-146">Stato dell'indagine</span><span class="sxs-lookup"><span data-stu-id="cd1ae-146">Investigation state</span></span> | <span data-ttu-id="cd1ae-147">Filtra gli incidenti in base allo stato dell'indagine automatizzata.</span><span class="sxs-lookup"><span data-stu-id="cd1ae-147">Filter incidents by the status of automated investigation.</span></span>  |
| <span data-ttu-id="cd1ae-148">Più categorie</span><span class="sxs-lookup"><span data-stu-id="cd1ae-148">Multiple categories</span></span> | <span data-ttu-id="cd1ae-149">È possibile scegliere di visualizzare solo gli eventi imprevisti mappati a più categorie e quindi causare più danni.</span><span class="sxs-lookup"><span data-stu-id="cd1ae-149">You can choose to see only incidents that have mapped to multiple categories  and can thus potentially cause more damage.</span></span> |
| <span data-ttu-id="cd1ae-150">Più servizi di origine</span><span class="sxs-lookup"><span data-stu-id="cd1ae-150">Multiple service sources</span></span>  | <span data-ttu-id="cd1ae-151">Filtra per visualizzare solo gli eventi imprevisti che contengono avvisi da origini diverse (Microsoft Defender per Endpoint, Microsoft Cloud App Security, Microsoft Defender per l'identità, Microsoft Defender per Office 365).</span><span class="sxs-lookup"><span data-stu-id="cd1ae-151">Filter to only see incidents that contain alerts from different sources (Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender for Office 365).</span></span> |
| <span data-ttu-id="cd1ae-152">Piattaforma del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="cd1ae-152">OS platform</span></span> | <span data-ttu-id="cd1ae-153">Limitare la visualizzazione della coda degli eventi imprevisti in base al sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="cd1ae-153">Limit the incident queue view by operating system.</span></span> |
| <span data-ttu-id="cd1ae-154">Servizi di origine</span><span class="sxs-lookup"><span data-stu-id="cd1ae-154">Service sources</span></span> | <span data-ttu-id="cd1ae-155">Scegliendo un’origine specifica puoi concentrarti sugli eventi imprevisti che contengono almeno un avviso dall'origine selezionata.</span><span class="sxs-lookup"><span data-stu-id="cd1ae-155">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> |
| <span data-ttu-id="cd1ae-156">Gravità</span><span class="sxs-lookup"><span data-stu-id="cd1ae-156">Severity</span></span> | <span data-ttu-id="cd1ae-157">La gravità di un incidente è indicativa dell'impatto che può avere sulle risorse.</span><span class="sxs-lookup"><span data-stu-id="cd1ae-157">The severity of an incident is indicative of the impact it can have on your assets.</span></span> <span data-ttu-id="cd1ae-158">Maggiore è la gravità, maggiore è l'impatto e in genere richiede l'attenzione più immediata.</span><span class="sxs-lookup"><span data-stu-id="cd1ae-158">The higher the severity, the bigger the impact and typically requires the most immediate attention.</span></span> |
| <span data-ttu-id="cd1ae-159">Stato</span><span class="sxs-lookup"><span data-stu-id="cd1ae-159">Status</span></span> | <span data-ttu-id="cd1ae-160">Puoi scegliere di limitare l'elenco degli eventi imprevisti visualizzati in base al loro stato per vedere quali sono attivi o risolti.</span><span class="sxs-lookup"><span data-stu-id="cd1ae-160">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span> |
|||

## <a name="save-defined-filters-as-urls"></a><span data-ttu-id="cd1ae-161">Salvare i filtri definiti come URL</span><span class="sxs-lookup"><span data-stu-id="cd1ae-161">Save defined filters as URLs</span></span>

<span data-ttu-id="cd1ae-162">Dopo aver configurato un filtro utile nella coda degli eventi imprevisti, è possibile aggiungere un segnalibro all'URL della scheda del browser o salvarlo in altro modo come collegamento in una pagina Web, in un documento di Word o in un punto a scelta.</span><span class="sxs-lookup"><span data-stu-id="cd1ae-162">Once you have configured a useful filter in the incidents queue, you can bookmark the URL of the browser tab or otherwise save it as a link on a Web page, a Word document, or a place of your choice.</span></span> <span data-ttu-id="cd1ae-163">In questo modo sarà possibile accedere con un solo clic alle visualizzazioni chiave della coda degli eventi imprevisti, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="cd1ae-163">This will give you single-click access to key views of the incident queue, such as:</span></span>

- <span data-ttu-id="cd1ae-164">Nuovi eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="cd1ae-164">New incidents</span></span>
- <span data-ttu-id="cd1ae-165">Eventi imprevisti di gravità elevata</span><span class="sxs-lookup"><span data-stu-id="cd1ae-165">High-severity incidents</span></span>
- <span data-ttu-id="cd1ae-166">Eventi imprevisti non assegnati</span><span class="sxs-lookup"><span data-stu-id="cd1ae-166">Unassigned incidents</span></span>
- <span data-ttu-id="cd1ae-167">Eventi imprevisti non assegnati e di gravità elevata</span><span class="sxs-lookup"><span data-stu-id="cd1ae-167">High-severity, unassigned incidents</span></span>
- <span data-ttu-id="cd1ae-168">Eventi imprevisti assegnati a me</span><span class="sxs-lookup"><span data-stu-id="cd1ae-168">Incidents assigned to me</span></span>
- <span data-ttu-id="cd1ae-169">Eventi imprevisti assegnati a me e a Microsoft Defender per Endpoint</span><span class="sxs-lookup"><span data-stu-id="cd1ae-169">Incidents assigned to me and for Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="cd1ae-170">Eventi imprevisti con uno o più tag specifici</span><span class="sxs-lookup"><span data-stu-id="cd1ae-170">Incidents with a specific tag or tags</span></span>
- <span data-ttu-id="cd1ae-171">Eventi imprevisti con una categoria di minacce specifica</span><span class="sxs-lookup"><span data-stu-id="cd1ae-171">Incidents with a specific threat category</span></span>
- <span data-ttu-id="cd1ae-172">Eventi imprevisti con una minaccia associata specifica</span><span class="sxs-lookup"><span data-stu-id="cd1ae-172">Incidents with a specific associated threat</span></span>
- <span data-ttu-id="cd1ae-173">Eventi imprevisti con un attore specifico</span><span class="sxs-lookup"><span data-stu-id="cd1ae-173">Incidents with a specific actor</span></span>

<span data-ttu-id="cd1ae-174">Dopo aver compilato e archiviato l'elenco di visualizzazioni filtro utili come URL, è possibile [](manage-incidents.md) utilizzarlo rapidamente per elaborare e definire le priorità degli eventi imprevisti nella coda e gestirli per l'analisi successiva.</span><span class="sxs-lookup"><span data-stu-id="cd1ae-174">Once you have compiled and stored your list of useful filter views as URLs, you can use it quickly process and prioritize the incidents in your queue and [manage](manage-incidents.md) them for subsequent analysis.</span></span>

## <a name="next-steps"></a><span data-ttu-id="cd1ae-175">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="cd1ae-175">Next steps</span></span>

<span data-ttu-id="cd1ae-176">Dopo aver determinato quale evento imprevisto richiede la priorità più alta, selezionarlo e:</span><span class="sxs-lookup"><span data-stu-id="cd1ae-176">After you've determined which incident requires the highest priority, select it and:</span></span>

- <span data-ttu-id="cd1ae-177">[Gestire](manage-incidents.md) le proprietà dell'evento imprevisto per tag, assegnazione, risoluzione immediata per incidenti falsi positivi e commenti.</span><span class="sxs-lookup"><span data-stu-id="cd1ae-177">[Manage](manage-incidents.md) the properties of the incident for tags, assignment, immediate resolution for false positive incidents, and comments.</span></span>
- <span data-ttu-id="cd1ae-178">Iniziare le [indagini](investigate-incidents.md).</span><span class="sxs-lookup"><span data-stu-id="cd1ae-178">Begin your [investigations](investigate-incidents.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="cd1ae-179">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cd1ae-179">See also</span></span>
- [<span data-ttu-id="cd1ae-180">Panoramica degli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="cd1ae-180">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="cd1ae-181">Gestire gli incidenti</span><span class="sxs-lookup"><span data-stu-id="cd1ae-181">Manage incidents</span></span>](manage-incidents.md)
- [<span data-ttu-id="cd1ae-182">Indagare sugli incidenti</span><span class="sxs-lookup"><span data-stu-id="cd1ae-182">Investigate incidents</span></span>](investigate-incidents.md)
