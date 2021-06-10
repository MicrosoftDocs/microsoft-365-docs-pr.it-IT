---
title: Tecniche nella sequenza temporale del dispositivo
description: Informazioni sulla sequenza temporale del dispositivo in Microsoft Defender for Endpoint
keywords: sequenza temporale del dispositivo, endpoint, MITRE, MITRE ATT&CK, tecniche, tattiche
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6b080c209292c8cac1aa64d748926734f4be964c
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185468"
---
# <a name="techniques-in-the-device-timeline"></a><span data-ttu-id="b02c9-104">Tecniche nella sequenza temporale del dispositivo</span><span class="sxs-lookup"><span data-stu-id="b02c9-104">Techniques in the device timeline</span></span>


<span data-ttu-id="b02c9-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="b02c9-105">**Applies to:**</span></span>
- [<span data-ttu-id="b02c9-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="b02c9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


<span data-ttu-id="b02c9-107">Puoi ottenere maggiori informazioni in un'indagine analizzando gli eventi che si sono verificati in un dispositivo specifico.</span><span class="sxs-lookup"><span data-stu-id="b02c9-107">You can gain more insight in an investigation by analyzing the events that happened on a specific device.</span></span> <span data-ttu-id="b02c9-108">Prima di tutto, seleziona il dispositivo di interesse [nell'elenco Dispositivi](machines-view-overview.md).</span><span class="sxs-lookup"><span data-stu-id="b02c9-108">First, select the device of interest from the [Devices list](machines-view-overview.md).</span></span> <span data-ttu-id="b02c9-109">Nella pagina del dispositivo puoi selezionare la scheda **Sequenza** temporale per visualizzare tutti gli eventi che si sono verificati nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b02c9-109">On the device page, you can select the **Timeline** tab to view all the events that occurred on the device.</span></span>

## <a name="understand-techniques-in-the-timeline"></a><span data-ttu-id="b02c9-110">Comprendere le tecniche nella sequenza temporale</span><span class="sxs-lookup"><span data-stu-id="b02c9-110">Understand techniques in the timeline</span></span>

>[!IMPORTANT]
><span data-ttu-id="b02c9-111">Alcune informazioni riguardano una funzionalità di prodotto pre-rilasciata in anteprima pubblica che potrebbe essere sostanzialmente modificata prima che venga rilasciata commercialmente.</span><span class="sxs-lookup"><span data-stu-id="b02c9-111">Some information relates to a prereleased product feature in public preview which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="b02c9-112">Microsoft non fornisce alcuna garanzia, esplicita o implicita, in relazione alle informazioni contenute in questo documento.</span><span class="sxs-lookup"><span data-stu-id="b02c9-112">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="b02c9-113">In Microsoft Defender per **Endpoint, le tecniche sono** un tipo di dati aggiuntivo nella sequenza temporale dell'evento.</span><span class="sxs-lookup"><span data-stu-id="b02c9-113">In Microsoft Defender for Endpoint, **Techniques** are an additional data type in the event timeline.</span></span> <span data-ttu-id="b02c9-114">Le tecniche forniscono maggiori informazioni sulle attività associate a [MITRE ATT&tecniche CK](https://attack.mitre.org/) o sub-tecniche.</span><span class="sxs-lookup"><span data-stu-id="b02c9-114">Techniques provide more insight on activities associated with [MITRE ATT&CK](https://attack.mitre.org/) techniques or sub-techniques.</span></span> 

<span data-ttu-id="b02c9-115">Questa funzionalità semplifica l'esperienza di indagine aiutando gli analisti a comprendere le attività osservate in un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b02c9-115">This feature simplifies the investigation experience by helping analysts understand the activities that were observed on a device.</span></span> <span data-ttu-id="b02c9-116">Gli analisti possono quindi decidere di approfondire le indagini.</span><span class="sxs-lookup"><span data-stu-id="b02c9-116">Analysts can then decide to investigate further.</span></span>

<span data-ttu-id="b02c9-117">Per l'anteprima pubblica, le tecniche sono disponibili per impostazione predefinita e vengono visualizzate insieme agli eventi quando viene visualizzata la sequenza temporale di un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b02c9-117">For public preview, Techniques are available by default and shown together with events when a device's timeline is viewed.</span></span> 

![Tecniche nello screenshot della sequenza temporale del dispositivo](images/device-timeline-2.png)

<span data-ttu-id="b02c9-119">Le tecniche sono evidenziate in grassetto e vengono visualizzate con un'icona blu a sinistra.</span><span class="sxs-lookup"><span data-stu-id="b02c9-119">Techniques are highlighted in bold text and appear with a blue icon on the left.</span></span> <span data-ttu-id="b02c9-120">Il nome della tecnica e l'ID CK&MITRE ATT corrispondenti vengono visualizzati anche come tag in Informazioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="b02c9-120">The corresponding MITRE ATT&CK ID and technique name also appear as tags under Additional information.</span></span> 

<span data-ttu-id="b02c9-121">Le opzioni di ricerca ed esportazione sono disponibili anche per Tecniche.</span><span class="sxs-lookup"><span data-stu-id="b02c9-121">Search and Export options are also available for Techniques.</span></span>

## <a name="investigate-using-the-side-pane"></a><span data-ttu-id="b02c9-122">Analizzare usando il riquadro laterale</span><span class="sxs-lookup"><span data-stu-id="b02c9-122">Investigate using the side pane</span></span>

<span data-ttu-id="b02c9-123">Selezionare una tecnica per aprire il riquadro laterale corrispondente.</span><span class="sxs-lookup"><span data-stu-id="b02c9-123">Select a Technique to open its corresponding side pane.</span></span> <span data-ttu-id="b02c9-124">Qui puoi visualizzare ulteriori informazioni e informazioni dettagliate, ad esempio tecniche, tattiche e descrizioni ATT correlate&CK.</span><span class="sxs-lookup"><span data-stu-id="b02c9-124">Here you can see additional information and insights like related ATT&CK techniques, tactics, and descriptions.</span></span> 

<span data-ttu-id="b02c9-125">Seleziona la tecnica *di attacco* specifica per aprire la pagina relativa alla tecnica ATT&CK in cui puoi trovare ulteriori informazioni su di essa.</span><span class="sxs-lookup"><span data-stu-id="b02c9-125">Select the specific *Attack technique* to open the related ATT&CK technique page where you can find more information about it.</span></span>

<span data-ttu-id="b02c9-126">È possibile copiare i dettagli di un'entità quando viene visualizzata un'icona blu a destra.</span><span class="sxs-lookup"><span data-stu-id="b02c9-126">You can copy an entity's details when you see a blue icon on the right.</span></span> <span data-ttu-id="b02c9-127">Ad esempio, per copiare sha1 di un file correlato, selezionare l'icona pagina blu.</span><span class="sxs-lookup"><span data-stu-id="b02c9-127">For instance, to copy a related file's SHA1, select the blue page icon.</span></span>

![Copiare i dettagli dell'entità](images/techniques-side-pane-clickable.png)

<span data-ttu-id="b02c9-129">È possibile eseguire la stessa operazione per le righe di comando.</span><span class="sxs-lookup"><span data-stu-id="b02c9-129">You can do the same for command lines.</span></span>

![Copia riga di comando](images/techniques-side-pane-command.png)


## <a name="investigate-related-events"></a><span data-ttu-id="b02c9-131">Analizzare gli eventi correlati</span><span class="sxs-lookup"><span data-stu-id="b02c9-131">Investigate related events</span></span>

<span data-ttu-id="b02c9-132">Per utilizzare [la ricerca avanzata](advanced-hunting-overview.md) per trovare gli eventi correlati alla tecnica selezionata, selezionare Cerca eventi **correlati.**</span><span class="sxs-lookup"><span data-stu-id="b02c9-132">To use [advanced hunting](advanced-hunting-overview.md) to find events related to the selected Technique, select **Hunt for related events**.</span></span> <span data-ttu-id="b02c9-133">In questo modo viene visualizzata la pagina di ricerca avanzata con una query per trovare gli eventi correlati alla tecnica.</span><span class="sxs-lookup"><span data-stu-id="b02c9-133">This leads to the advanced hunting page with a query to find events related to the Technique.</span></span>

![Ricerca di eventi correlati](images/techniques-hunt-for-related-events.png)

>[!NOTE]
><span data-ttu-id="b02c9-135">L'esecuzione  di query tramite il pulsante Cerca eventi correlati da un riquadro laterale Tecnica visualizza tutti gli eventi correlati alla tecnica identificata, ma non include la tecnica stessa nei risultati della query.</span><span class="sxs-lookup"><span data-stu-id="b02c9-135">Querying using the **Hunt for related events** button from a Technique side pane displays all the events related to the identified technique but does not include the Technique itself in the query results.</span></span>


## <a name="customize-your-device-timeline"></a><span data-ttu-id="b02c9-136">Personalizzare la sequenza temporale del dispositivo</span><span class="sxs-lookup"><span data-stu-id="b02c9-136">Customize your device timeline</span></span>

<span data-ttu-id="b02c9-137">Nella parte superiore destra della sequenza temporale del dispositivo puoi scegliere un intervallo di date per limitare il numero di eventi e tecniche nella sequenza temporale.</span><span class="sxs-lookup"><span data-stu-id="b02c9-137">On the upper right-hand side of the device timeline, you can choose a date range to limit the number of events and techniques in the timeline.</span></span> 

<span data-ttu-id="b02c9-138">È possibile personalizzare le colonne da esporre.</span><span class="sxs-lookup"><span data-stu-id="b02c9-138">You can customize which columns to expose.</span></span> <span data-ttu-id="b02c9-139">È inoltre possibile filtrare gli eventi contrassegnati in base al tipo di dati o al gruppo di eventi.</span><span class="sxs-lookup"><span data-stu-id="b02c9-139">You can also filter for flagged events by data type or by event group.</span></span>

### <a name="choose-columns-to-expose"></a><span data-ttu-id="b02c9-140">Scegliere le colonne da esporre</span><span class="sxs-lookup"><span data-stu-id="b02c9-140">Choose columns to expose</span></span>
<span data-ttu-id="b02c9-141">Puoi scegliere le colonne da esporre nella sequenza temporale selezionando il **pulsante Scegli** colonne.</span><span class="sxs-lookup"><span data-stu-id="b02c9-141">You can choose which columns to expose in the timeline by selecting the **Choose columns** button.</span></span>

![Personalizzare le colonne](images/filter-customize-columns.png)

<span data-ttu-id="b02c9-143">Da qui è possibile selezionare il set di informazioni da includere.</span><span class="sxs-lookup"><span data-stu-id="b02c9-143">From there you can select which information set to include.</span></span>

### <a name="filter-to-view-techniques-or-events-only"></a><span data-ttu-id="b02c9-144">Filtrare per visualizzare solo tecniche o eventi</span><span class="sxs-lookup"><span data-stu-id="b02c9-144">Filter to view techniques or events only</span></span>

<span data-ttu-id="b02c9-145">Per visualizzare solo gli eventi o le tecniche, seleziona **Filtri** dalla sequenza temporale del dispositivo e scegli il tipo di dati preferito da visualizzare.</span><span class="sxs-lookup"><span data-stu-id="b02c9-145">To view only either events or techniques, select **Filters** from the device timeline and choose your preferred Data type to view.</span></span>

![Screenshot dei filtri](images/device-timeline-filters.png)



## <a name="see-also"></a><span data-ttu-id="b02c9-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b02c9-147">See also</span></span>
- [<span data-ttu-id="b02c9-148">Visualizzare e organizzare l’elenco dispositivi</span><span class="sxs-lookup"><span data-stu-id="b02c9-148">View and organize the Devices list</span></span>](machines-view-overview.md)
- [<span data-ttu-id="b02c9-149">Flag di evento della sequenza temporale del dispositivo Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="b02c9-149">Microsoft Defender for Endpoint device timeline event flags</span></span>](device-timeline-event-flag.md) 


 
