---
title: Analizzare gli avvisi in Microsoft 365 Defender
description: Analizzare gli avvisi visualizzati su dispositivi, utenti e cassette postali.
keywords: eventi, avvisi, analisi, correlazione, attacco, computer, dispositivi, utenti, identità, cassetta postale, posta elettronica, 365, Microsoft, M365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
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
ms.technology: m365d
ms.openlocfilehash: c4a67a6b0df9308e9e61733a951a5016fa69c082
ms.sourcegitcommit: d739f48b991793c08522a3d5323beba27f0111b2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/08/2021
ms.locfileid: "50928701"
---
# <a name="investigate-alerts-in-microsoft-365-defender"></a><span data-ttu-id="8ce27-104">Analizzare gli avvisi in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8ce27-104">Investigate alerts in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="8ce27-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="8ce27-105">**Applies to:**</span></span>
- <span data-ttu-id="8ce27-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8ce27-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="8ce27-107">Gli avvisi sono alla base di tutti gli eventi imprevisti e indicano il verificarsi di eventi dannosi o sospetti nell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="8ce27-107">Alerts are the basis of all incidents and indicate the occurrence of malicious or suspicious events in your environment.</span></span> <span data-ttu-id="8ce27-108">Gli avvisi fanno in genere parte di un attacco più ampio e forniscono indizi su un incidente.</span><span class="sxs-lookup"><span data-stu-id="8ce27-108">Alerts are typically part of a broader attack and provide pieces of clues about an incident.</span></span>

<span data-ttu-id="8ce27-109">In Microsoft 365 Defender, gli avvisi correlati vengono aggregati insieme per formare eventi imprevisti.</span><span class="sxs-lookup"><span data-stu-id="8ce27-109">In Microsoft 365 Defender, related alerts are aggregated together to form incidents.</span></span> <span data-ttu-id="8ce27-110">Gli incidenti forniscono sempre il contesto più ampio di un attacco, tuttavia, l'analisi degli avvisi può essere utile quando è necessaria un'analisi più approfondita.</span><span class="sxs-lookup"><span data-stu-id="8ce27-110">Incidents will always provide the broader context of an attack, however, investigating alerts can be valuable when deeper analysis is required.</span></span> 



## <a name="using-alert-pages-in-investigations"></a><span data-ttu-id="8ce27-111">Utilizzo delle pagine di avviso nelle indagini</span><span class="sxs-lookup"><span data-stu-id="8ce27-111">Using alert pages in investigations</span></span>

<span data-ttu-id="8ce27-112">Nella scheda Avvisi di qualsiasi evento imprevisto, selezionando un avviso si visualizzano le singole pagine di avviso.</span><span class="sxs-lookup"><span data-stu-id="8ce27-112">From the Alerts tab of any incident page, selecting an alert brings you to the individual alert pages.</span></span> <span data-ttu-id="8ce27-113">Una pagina di avviso è costituita da tre sezioni: asset interessati, storia di avviso e riquadro dei dettagli.</span><span class="sxs-lookup"><span data-stu-id="8ce27-113">An alert page is composed of three sections: affected assets, alert story, and the details pane.</span></span>

![Immagine della pagina di avviso di esempio](../../media/new-alert-page2.png)

<span data-ttu-id="8ce27-115">In tutta una pagina di avviso puoi selezionare l'icona a tre punti (**...**) accanto a qualsiasi entità in modo da visualizzare le azioni disponibili, ad esempio l'apertura della pagina di asset specifica o la procedura di correzione specifica.</span><span class="sxs-lookup"><span data-stu-id="8ce27-115">Throughout an alert page, you can select the three-dot icon (**...**) beside any entity so you can see available actions like opening the specific asset page or doing specific remediation steps.</span></span>

### <a name="analyze-affected-assets"></a><span data-ttu-id="8ce27-116">Analizzare gli asset interessati</span><span class="sxs-lookup"><span data-stu-id="8ce27-116">Analyze affected assets</span></span>
<span data-ttu-id="8ce27-117">Nella sezione asset interessati sono elencate le cassette postali, i dispositivi e gli utenti interessati da questo avviso.</span><span class="sxs-lookup"><span data-stu-id="8ce27-117">The affected assets section lists mailboxes, devices, and users affected by this alert.</span></span> <span data-ttu-id="8ce27-118">Se si seleziona una delle schede delle risorse, nel riquadro laterale dei dettagli vengono visualizzate informazioni, inclusi gli eventuali altri avvisi che hanno coinvolto gli asset.</span><span class="sxs-lookup"><span data-stu-id="8ce27-118">Selecting any of the asset cards populates the details side pane with information, including other alerts that occurred involving the assets, if any.</span></span>


### <a name="trace-an-alerts-role-in-the-alert-story"></a><span data-ttu-id="8ce27-119">Tracciare il ruolo di un avviso nella storia di avviso</span><span class="sxs-lookup"><span data-stu-id="8ce27-119">Trace an alert's role in the alert story</span></span>
<span data-ttu-id="8ce27-120">La storia dell'avviso visualizza tutti gli asset o le entità correlati all'avviso in una visualizzazione albero del processo.</span><span class="sxs-lookup"><span data-stu-id="8ce27-120">The alert story displays all assets or entities related to the alert in a process tree view.</span></span> <span data-ttu-id="8ce27-121">L'avviso nel titolo è quello a fuoco quando si atterra per la prima volta nella pagina dell'avviso selezionato.</span><span class="sxs-lookup"><span data-stu-id="8ce27-121">The alert in the title is the one in focus when you first land on your selected alert's page.</span></span> <span data-ttu-id="8ce27-122">Gli asset nella storia di avviso sono espandibili e selezionabili.</span><span class="sxs-lookup"><span data-stu-id="8ce27-122">Assets in the alert story are expandable and clickable.</span></span> <span data-ttu-id="8ce27-123">Forniscono informazioni aggiuntive e velocizzano la risposta consentendoti di eseguire azioni direttamente nel contesto della pagina di avviso.</span><span class="sxs-lookup"><span data-stu-id="8ce27-123">They provide additional information and expedite response by allowing you to take actions right in the context of the alert page.</span></span> 

> [!NOTE]
> <span data-ttu-id="8ce27-124">La sezione della storia dell'avviso può contenere più di un avviso, con altri avvisi correlati allo stesso albero di esecuzione visualizzati prima o dopo l'avviso selezionato.</span><span class="sxs-lookup"><span data-stu-id="8ce27-124">The alert story section may contain more than one alert, with additional alerts related to the same execution tree appearing before or after the alert you've selected.</span></span>

### <a name="view-more-alert-information-in-the-details-pane"></a><span data-ttu-id="8ce27-125">Visualizzare ulteriori informazioni sugli avvisi nel riquadro dei dettagli</span><span class="sxs-lookup"><span data-stu-id="8ce27-125">View more alert information in the details pane</span></span>

<span data-ttu-id="8ce27-126">Il riquadro dei dettagli mostra i dettagli dell'avviso selezionato in un primo momento, con i dettagli e le azioni ad esso correlati.</span><span class="sxs-lookup"><span data-stu-id="8ce27-126">The details pane shows the details of the selected alert at first, with details and actions related to it.</span></span> <span data-ttu-id="8ce27-127">Se si seleziona una delle risorse o entità interessate nella storia di avviso, il riquadro dei dettagli cambia per fornire informazioni contestuali e azioni per l'oggetto selezionato.</span><span class="sxs-lookup"><span data-stu-id="8ce27-127">If you select any of the affected assets or entities in the alert story, the details pane changes to provide contextual information and actions for the selected object.</span></span>

<span data-ttu-id="8ce27-128">Dopo aver selezionato un'entità di interesse, il riquadro dei dettagli cambia per visualizzare le informazioni sul tipo di entità selezionato, le informazioni storiche quando è disponibile e le opzioni per eseguire un'azione su questa entità direttamente dalla pagina di avviso.</span><span class="sxs-lookup"><span data-stu-id="8ce27-128">Once you've selected an entity of interest, the details pane changes to display information about the selected entity type, historic information when it's available, and options to take action on this entity directly from the alert page.</span></span>

### <a name="manage-alerts"></a><span data-ttu-id="8ce27-129">Gestire gli avvisi</span><span class="sxs-lookup"><span data-stu-id="8ce27-129">Manage alerts</span></span>

<span data-ttu-id="8ce27-130">Una volta completata l'analisi degli avvisi, è possibile tornare all'avviso avviato, contrassegnare lo stato dell'avviso come Risolto e classificarlo come avviso False o True.</span><span class="sxs-lookup"><span data-stu-id="8ce27-130">Once you're done investigating the alerts, you can go back to the alert you started with, mark the alert's status as Resolved and classify it as either a False alert or True alert.</span></span> <span data-ttu-id="8ce27-131">La classificazione degli avvisi consente di ottimizzare il prodotto per fornire avvisi più veri e meno falsi.</span><span class="sxs-lookup"><span data-stu-id="8ce27-131">Classifying alerts helps tune your product to provide more true alerts and less false alerts.</span></span>

> [!NOTE]
> <span data-ttu-id="8ce27-132">Un modo per gestire gli avvisi tramite l'uso di tag.</span><span class="sxs-lookup"><span data-stu-id="8ce27-132">One way of managing alerts it through the use of tags.</span></span> <span data-ttu-id="8ce27-133">La funzionalità di tagging per Microsoft Defender per Office 365 in fase di implementazione incrementale ed è attualmente in anteprima.</span><span class="sxs-lookup"><span data-stu-id="8ce27-133">The tagging capability for Microsoft Defender for Office 365 in incrementally being rolled out and is currently in preview.</span></span> <br>
> <span data-ttu-id="8ce27-134">Attualmente, i nomi dei tag modificati vengono applicati solo agli avvisi creati *dopo l'aggiornamento.*</span><span class="sxs-lookup"><span data-stu-id="8ce27-134">Currently, modified tag names are only applied to alerts created *after* the update.</span></span> <span data-ttu-id="8ce27-135">Gli avvisi generati prima della modifica non rifletteranno il nome del tag aggiornato.</span><span class="sxs-lookup"><span data-stu-id="8ce27-135">Alerts that were generated prior to the modification will not reflect the updated tag name.</span></span> 


## <a name="manage-the-unified-alert-queue"></a><span data-ttu-id="8ce27-136">Gestire la coda di avvisi unificati</span><span class="sxs-lookup"><span data-stu-id="8ce27-136">Manage the unified alert queue</span></span>

<span data-ttu-id="8ce27-137">Selezionando Avvisi in Eventi imprevisti & avvisi nel riquadro di spostamento del Centro sicurezza Microsoft 365, viene visualizzata la coda degli avvisi unificati.</span><span class="sxs-lookup"><span data-stu-id="8ce27-137">Selecting Alerts under Incidents & Alerts in the Microsoft 365 security center navigation pane brings you to the unified alert queue.</span></span> <span data-ttu-id="8ce27-138">Gli avvisi di diverse soluzioni di sicurezza Microsoft come Microsoft Defender for Endpoint, Microsoft Defender per Office 365 e Microsoft 365 Defender vengono visualizzati in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="8ce27-138">Alerts from different Microsoft security solutions like Microsoft Defender for Endpoint, Microsoft Defender for Office 365, and Microsoft 365 Defender appear in this section.</span></span> 

![Immagine della pagina di avviso di esempio](../../media/unified-alert-queue.png)

<span data-ttu-id="8ce27-140">La coda avvisi mostra un elenco di avvisi contrassegnati nella rete.</span><span class="sxs-lookup"><span data-stu-id="8ce27-140">The Alerts queue shows a list of alerts that were flagged in your network.</span></span> <span data-ttu-id="8ce27-141">Per impostazione predefinita, nella coda vengono visualizzati gli avvisi visualizzati negli ultimi 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="8ce27-141">By default, the queue displays alerts seen in the last 30 days.</span></span> <span data-ttu-id="8ce27-142">Gli avvisi più recenti vengono visualizzati all'inizio dell'elenco per visualizzare prima gli avvisi più recenti.</span><span class="sxs-lookup"><span data-stu-id="8ce27-142">The most recent alerts are shown at the top of the list helping you see the most recent alerts first.</span></span>

> [!NOTE]
> <span data-ttu-id="8ce27-143">Al momento dell'avvio, la coda degli avvisi unificati avrà a disposizione solo 7 giorni di avvisi di Microsoft Defender per Office 365.</span><span class="sxs-lookup"><span data-stu-id="8ce27-143">At the time of launch, the unified alerts queue will only have 7 days’ worth of Microsoft Defender for Office 365 alerts available.</span></span> <span data-ttu-id="8ce27-144">La coda continuerà a essere compilata nel tempo.</span><span class="sxs-lookup"><span data-stu-id="8ce27-144">The queue will continue to build over time.</span></span> <span data-ttu-id="8ce27-145">Se è necessario eseguire la valutazione degli avvisi prima dell'avvio della coda di avvisi unificati, utilizzare la coda degli avvisi nel [Centro sicurezza e conformità.](https://protection.office.com/viewalerts)</span><span class="sxs-lookup"><span data-stu-id="8ce27-145">If you need to triage alerts prior to the launch of the unified alerts queue, use the alerts queue in the [Security and Compliance Center](https://protection.office.com/viewalerts).</span></span>


<span data-ttu-id="8ce27-146">Nella barra di spostamento superiore è possibile:</span><span class="sxs-lookup"><span data-stu-id="8ce27-146">On the top navigation, you can:</span></span>

- <span data-ttu-id="8ce27-147">Applicazione di filtri</span><span class="sxs-lookup"><span data-stu-id="8ce27-147">Apply filters</span></span>
- <span data-ttu-id="8ce27-148">Personalizzare le colonne per aggiungere o rimuovere colonne</span><span class="sxs-lookup"><span data-stu-id="8ce27-148">Customize columns to add or remove columns</span></span>
- <span data-ttu-id="8ce27-149">Esportare dati</span><span class="sxs-lookup"><span data-stu-id="8ce27-149">Export data</span></span>

<span data-ttu-id="8ce27-150">È inoltre possibile filtrare gli avvisi in base a criteri diversi:</span><span class="sxs-lookup"><span data-stu-id="8ce27-150">You can also filter alerts according to different criteria:</span></span>

- <span data-ttu-id="8ce27-151">Gravità</span><span class="sxs-lookup"><span data-stu-id="8ce27-151">Severity</span></span>
- <span data-ttu-id="8ce27-152">Stato</span><span class="sxs-lookup"><span data-stu-id="8ce27-152">Status</span></span>
- <span data-ttu-id="8ce27-153">Categoria</span><span class="sxs-lookup"><span data-stu-id="8ce27-153">Category</span></span>
- <span data-ttu-id="8ce27-154">Origine di rilevamento</span><span class="sxs-lookup"><span data-stu-id="8ce27-154">Detection source</span></span>
- <span data-ttu-id="8ce27-155">Criteri</span><span class="sxs-lookup"><span data-stu-id="8ce27-155">Policy</span></span>
- <span data-ttu-id="8ce27-156">Asset influenzati</span><span class="sxs-lookup"><span data-stu-id="8ce27-156">Impacted assets</span></span>
- <span data-ttu-id="8ce27-157">Prima attività</span><span class="sxs-lookup"><span data-stu-id="8ce27-157">First activity</span></span>
- <span data-ttu-id="8ce27-158">Ultima attività</span><span class="sxs-lookup"><span data-stu-id="8ce27-158">Last activity</span></span>


<span data-ttu-id="8ce27-159">Per avviare un'indagine su un evento imprevisto, leggere [Analizzare gli incidenti in Microsoft 365 Defender](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="8ce27-159">To start an investigation on an incident, read [Investigate incidents in Microsoft 365 Defender](investigate-incidents.md)</span></span>
## <a name="see-also"></a><span data-ttu-id="8ce27-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8ce27-160">See also</span></span>

- [<span data-ttu-id="8ce27-161">Panoramica degli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="8ce27-161">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="8ce27-162">Indagare sugli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="8ce27-162">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="8ce27-163">Gestire gli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="8ce27-163">Manage incidents</span></span>](manage-incidents.md)
