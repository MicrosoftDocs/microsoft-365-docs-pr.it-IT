---
title: Assegnare la priorità agli incidenti in Microsoft 365 Defender
description: Informazioni su come definire la priorità degli incidenti dalla coda degli incidenti in Microsoft 365 Defender
keywords: evento imprevisto, coda, panoramica, dispositivi, identità, utenti, cassetta postale, posta elettronica, eventi imprevisti
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 4369d51ed740af652be632ba0b8752c708d6c719
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877220"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a><span data-ttu-id="c020d-104">Assegnare la priorità agli incidenti in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c020d-104">Prioritize incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c020d-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="c020d-105">**Applies to:**</span></span>
- <span data-ttu-id="c020d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c020d-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="c020d-107">Microsoft 365 Defender applica l'analisi della correlazione e aggrega tutti gli avvisi e le indagini correlati provenienti da prodotti diversi in un unico evento.</span><span class="sxs-lookup"><span data-stu-id="c020d-107">Microsoft 365 Defender applies correlation analytics and aggregates all related alerts and investigations from different products into one incident.</span></span> <span data-ttu-id="c020d-108">Microsoft 365 Defender attiva anche avvisi univoci sulle attività che possono essere identificate solo come dannose, data la visibilità end-to-end che Microsoft 365 Defender ha nell'intera proprietà e nella famiglia di prodotti.</span><span class="sxs-lookup"><span data-stu-id="c020d-108">Microsoft 365 Defender also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft 365 Defender has across the entire estate and suite of products.</span></span> <span data-ttu-id="c020d-109">In questo modo, Microsoft 365 Defender narra la storia degli attacchi più ampia, consentendo a un analista delle operazioni di sicurezza di comprendere e gestire le minacce complesse all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c020d-109">By doing so, Microsoft 365 Defender narrates the broader attack story, allowing a security operations analyst to understand and deal with complex threats across the organization.</span></span>


<span data-ttu-id="c020d-110">La **coda degli eventi imprevisti** mostra una raccolta di eventi imprevisti contrassegnati da diversi dispositivi, utenti e cassette postali.</span><span class="sxs-lookup"><span data-stu-id="c020d-110">The **Incidents queue** shows a collection of incidents that were flagged from across devices, users, and mailboxes.</span></span> <span data-ttu-id="c020d-111">Ti aiuta a ordinare gli eventi imprevisti in base alla loro priorità e a definire una risposta di cybersecurity mirata.</span><span class="sxs-lookup"><span data-stu-id="c020d-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span>


![Immagine della coda eventi imprevisti](../../media/incidents-queue.png) 

<span data-ttu-id="c020d-113">Per impostazione predefinita, la coda nel centro sicurezza Microsoft 365 Visualizza gli incidenti riscontrati negli ultimi 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="c020d-113">By default, the queue in the Microsoft 365 security center displays incidents seen in the last 30 days.</span></span> <span data-ttu-id="c020d-114">L'evento più recente si trova nella parte superiore dell'elenco, in modo che sia possibile visualizzarlo per primo.</span><span class="sxs-lookup"><span data-stu-id="c020d-114">The most recent incident is at the top of the list so you can see it first.</span></span>

<span data-ttu-id="c020d-115">La coda di eventi non consentiti espone colonne personalizzabili che consentono di visualizzare le diverse caratteristiche dell'evento Incident o delle entità contenute.</span><span class="sxs-lookup"><span data-stu-id="c020d-115">The incident queue exposes customizable columns that give you visibility into different characteristics of the incident or the contained entities.</span></span> <span data-ttu-id="c020d-116">In questo modo è possibile prendere una decisione informata in merito alle priorità degli incidenti da gestire.</span><span class="sxs-lookup"><span data-stu-id="c020d-116">This helps you make an informed decision regarding prioritization of incidents to handle.</span></span>

<span data-ttu-id="c020d-117">Per una maggiore visibilità a colpo d'occhio, la denominazione degli incidenti automatici genera nomi degli incidenti in base agli attributi di avviso, ad esempio il numero di endpoint coinvolti, gli utenti coinvolti, le origini di rilevamento o le categorie.</span><span class="sxs-lookup"><span data-stu-id="c020d-117">For additional visibility at a glance, automatic incident naming generates incident names based on alert attributes such as the number of endpoints affected, users affected, detection sources, or categories.</span></span> <span data-ttu-id="c020d-118">In questo modo è possibile comprendere rapidamente l'ambito dell'evento Incident.</span><span class="sxs-lookup"><span data-stu-id="c020d-118">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="c020d-119">Ad esempio: *eventi a più fasi su più endpoint segnalati da più origini.*</span><span class="sxs-lookup"><span data-stu-id="c020d-119">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="c020d-120">Gli incidenti che sono stati precedenti all'implementazione della denominazione degli incidenti automatici non avranno il nome modificato.</span><span class="sxs-lookup"><span data-stu-id="c020d-120">Incidents that existed prior the rollout of automatic incident naming will not have their name changed.</span></span>

<span data-ttu-id="c020d-121">La coda degli incidenti espone anche più opzioni di filtro, che quando vengono applicate, consentono di eseguire un'ampia gamma di tutti gli incidenti esistenti nell'ambiente o di decidere di concentrarsi su uno scenario specifico o una minaccia.</span><span class="sxs-lookup"><span data-stu-id="c020d-121">The incident queue also exposes multiple filtering options, that when applied, enable you to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="c020d-122">Applicando i filtri a una coda di eventi imprevisti puoi determinare quale evento richiede un’attenzione immediata.</span><span class="sxs-lookup"><span data-stu-id="c020d-122">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="c020d-123">Filtri disponibili</span><span class="sxs-lookup"><span data-stu-id="c020d-123">Available filters</span></span>

### <a name="assigned-to"></a><span data-ttu-id="c020d-124">Assegnata a</span><span class="sxs-lookup"><span data-stu-id="c020d-124">Assigned to</span></span>
<span data-ttu-id="c020d-125">È possibile scegliere di visualizzare gli avvisi assegnati all'utente o a quelli gestiti dall'automazione.</span><span class="sxs-lookup"><span data-stu-id="c020d-125">You can choose to show alerts that are assigned to you or those handled by automation.</span></span>

### <a name="categories"></a><span data-ttu-id="c020d-126">Categorie</span><span class="sxs-lookup"><span data-stu-id="c020d-126">Categories</span></span>
<span data-ttu-id="c020d-127">Scegliere categorie per concentrarsi su specifiche tattiche, tecniche o componenti di attacco visibili.</span><span class="sxs-lookup"><span data-stu-id="c020d-127">Choose categories to focus on specific tactics, techniques, or attack components seen.</span></span> 

### <a name="classification"></a><span data-ttu-id="c020d-128">Classificazione</span><span class="sxs-lookup"><span data-stu-id="c020d-128">Classification</span></span>
<span data-ttu-id="c020d-129">Filtrare gli eventi non consentiti in base alla classificazione impostata degli avvisi correlati.</span><span class="sxs-lookup"><span data-stu-id="c020d-129">Filter incidents based on the set classifications of the related alerts.</span></span> <span data-ttu-id="c020d-130">I valori includono avvisi veri, falsi avvisi o non impostati.</span><span class="sxs-lookup"><span data-stu-id="c020d-130">The values include true alerts, false alerts, or not set.</span></span>

### <a name="data-sensitivity"></a><span data-ttu-id="c020d-131">Riservatezza dei dati</span><span class="sxs-lookup"><span data-stu-id="c020d-131">Data sensitivity</span></span>
<span data-ttu-id="c020d-132">Alcuni attacchi sono incentrati sull’estrazione di dati riservati o di valore.</span><span class="sxs-lookup"><span data-stu-id="c020d-132">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="c020d-133">Applicando un filtro per vedere se sono coinvolte informazioni riservate nell'evento, puoi determinare rapidamente se le informazioni riservate sono potenzialmente compromesse e assegnare priorità all'intervento.</span><span class="sxs-lookup"><span data-stu-id="c020d-133">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span>

>[!NOTE]
><span data-ttu-id="c020d-134">Applicabile solo se Microsoft Information Protection è attivo.</span><span class="sxs-lookup"><span data-stu-id="c020d-134">Only applicable if Microsoft Information Protection is turned on.</span></span>

### <a name="device-group"></a><span data-ttu-id="c020d-135">Gruppo di dispositivi</span><span class="sxs-lookup"><span data-stu-id="c020d-135">Device group</span></span>
<span data-ttu-id="c020d-136">Filtrare in base ai gruppi di dispositivi definiti.</span><span class="sxs-lookup"><span data-stu-id="c020d-136">Filter by defined device groups.</span></span>

### <a name="investigation-state"></a><span data-ttu-id="c020d-137">Stato di indagine</span><span class="sxs-lookup"><span data-stu-id="c020d-137">Investigation state</span></span>
<span data-ttu-id="c020d-138">Filtrare gli incidenti in base allo stato dell'analisi automatizzata.</span><span class="sxs-lookup"><span data-stu-id="c020d-138">Filter incidents by the status of automated investigation.</span></span> 

### <a name="multiple-categories"></a><span data-ttu-id="c020d-139">Più categorie</span><span class="sxs-lookup"><span data-stu-id="c020d-139">Multiple categories</span></span> 
<span data-ttu-id="c020d-140">È possibile scegliere di visualizzare solo gli incidenti che sono stati mappati a più categorie e pertanto possono causare più danni.</span><span class="sxs-lookup"><span data-stu-id="c020d-140">You can choose to see only incidents that have mapped to multiple categories  and can thus potentially cause more damage.</span></span> 

### <a name="multiple-service-sources"></a><span data-ttu-id="c020d-141">Più servizi di origine</span><span class="sxs-lookup"><span data-stu-id="c020d-141">Multiple service sources</span></span> 
<span data-ttu-id="c020d-142">Filtro per visualizzare solo gli incidenti che contengono avvisi provenienti da origini diverse (Microsoft Defender per endpoint, Microsoft cloud app Security, Microsoft Defender for Identity, Microsoft Defender per Office 365).</span><span class="sxs-lookup"><span data-stu-id="c020d-142">Filter to only see incidents that contain alerts from different sources (Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender for Office 365).</span></span>

### <a name="os-platform"></a><span data-ttu-id="c020d-143">Piattaforma OS</span><span class="sxs-lookup"><span data-stu-id="c020d-143">OS platform</span></span>
<span data-ttu-id="c020d-144">Limitare la visualizzazione delle code degli incidenti in base al sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="c020d-144">Limit the incident queue view by operating system.</span></span>

### <a name="service-sources"></a><span data-ttu-id="c020d-145">Servizi di origine</span><span class="sxs-lookup"><span data-stu-id="c020d-145">Service sources</span></span>
<span data-ttu-id="c020d-146">Scegliendo un’origine specifica puoi concentrarti sugli eventi imprevisti che contengono almeno un avviso dall'origine selezionata.</span><span class="sxs-lookup"><span data-stu-id="c020d-146">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> 

### <a name="severity"></a><span data-ttu-id="c020d-147">Gravità</span><span class="sxs-lookup"><span data-stu-id="c020d-147">Severity</span></span>
<span data-ttu-id="c020d-148">La gravità di un evento imprevisto è indicativa dell'impatto che può avere sui cespiti.</span><span class="sxs-lookup"><span data-stu-id="c020d-148">The severity of an incident is indicative of the impact it can have on your assets.</span></span> <span data-ttu-id="c020d-149">Maggiore è la gravità, maggiore è l'impatto e in genere è necessaria l'attenzione più immediata.</span><span class="sxs-lookup"><span data-stu-id="c020d-149">The higher the severity, the bigger the impact and typically requires the most immediate attention.</span></span> 

### <a name="status"></a><span data-ttu-id="c020d-150">Stato</span><span class="sxs-lookup"><span data-stu-id="c020d-150">Status</span></span>
<span data-ttu-id="c020d-151">Puoi scegliere di limitare l'elenco degli eventi imprevisti visualizzati in base al loro stato per vedere quali sono attivi o risolti.</span><span class="sxs-lookup"><span data-stu-id="c020d-151">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span>

>[!IMPORTANT]
><span data-ttu-id="c020d-152">La classificazione, il gruppo di dispositivi, lo stato di indagine e i filtri della piattaforma OS sono attualmente disponibili solo in anteprima pubblica.</span><span class="sxs-lookup"><span data-stu-id="c020d-152">The Classification, Device group, Investigation state, and OS platform filters are currently only available in public preview.</span></span>


## <a name="next-steps"></a><span data-ttu-id="c020d-153">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="c020d-153">Next steps</span></span>
<span data-ttu-id="c020d-154">Dopo aver individuato l'evento che richiede maggiore priorità, puoi continuare eseguendo ulteriori operazioni di indagine su un evento.</span><span class="sxs-lookup"><span data-stu-id="c020d-154">After you've determined which incident requires the highest priority, you can proceed to do further investigative work on an incident.</span></span>
- [<span data-ttu-id="c020d-155">Indagare sugli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="c020d-155">Investigate incidents</span></span>](investigate-incidents.md)


## <a name="see-also"></a><span data-ttu-id="c020d-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c020d-156">See also</span></span>
- [<span data-ttu-id="c020d-157">Panoramica degli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="c020d-157">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="c020d-158">Indagare sugli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="c020d-158">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="c020d-159">Gestire gli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="c020d-159">Manage incidents</span></span>](manage-incidents.md)
