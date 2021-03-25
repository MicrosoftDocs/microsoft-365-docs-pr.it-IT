---
title: Report sulla protezione dalle minacce in Microsoft Defender ATP
description: Tenere traccia dei rilevamenti, delle categorie e della gravità degli avvisi tramite il report di protezione dalle minacce
keywords: rilevamento degli avvisi, origine, avviso per categoria, gravità degli avvisi, classificazione degli avvisi, determinazione
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 4ecd2df31e1e03da5134d3d4180dcba75d3cee26
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51183838"
---
# <a name="threat-protection-report-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="a740c-104">Report di protezione dalle minacce in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="a740c-104">Threat protection report in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a740c-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="a740c-105">**Applies to:**</span></span>
- [<span data-ttu-id="a740c-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="a740c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a740c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a740c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="a740c-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="a740c-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a740c-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="a740c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

<span data-ttu-id="a740c-110">Il report sulla protezione dalle minacce fornisce informazioni di alto livello sugli avvisi generati nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a740c-110">The threat protection report provides high-level information about alerts generated in your organization.</span></span> <span data-ttu-id="a740c-111">Il report include informazioni sulle tendenze che mostrano le origini di rilevamento, le categorie, le gravità, gli stati, le classificazioni e le determinazioni degli avvisi nel tempo.</span><span class="sxs-lookup"><span data-stu-id="a740c-111">The report includes trending information showing the detection sources, categories, severities, statuses, classifications, and determinations of alerts across time.</span></span>

<span data-ttu-id="a740c-112">Il dashboard è strutturato in due sezioni:</span><span class="sxs-lookup"><span data-stu-id="a740c-112">The dashboard is structured into two sections:</span></span>

![Immagine del report sulla protezione dalle minacce](images/threat-protection-reports.png)

<span data-ttu-id="a740c-114">Sezione</span><span class="sxs-lookup"><span data-stu-id="a740c-114">Section</span></span> | <span data-ttu-id="a740c-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a740c-115">Description</span></span> 
:---|:---
<span data-ttu-id="a740c-116">1</span><span class="sxs-lookup"><span data-stu-id="a740c-116">1</span></span> | <span data-ttu-id="a740c-117">Tendenze degli avvisi</span><span class="sxs-lookup"><span data-stu-id="a740c-117">Alerts trends</span></span>
<span data-ttu-id="a740c-118">2 </span><span class="sxs-lookup"><span data-stu-id="a740c-118">2</span></span> | <span data-ttu-id="a740c-119">Riepilogo degli avvisi</span><span class="sxs-lookup"><span data-stu-id="a740c-119">Alert summary</span></span>

## <a name="alert-trends"></a><span data-ttu-id="a740c-120">Tendenze degli avvisi</span><span class="sxs-lookup"><span data-stu-id="a740c-120">Alert trends</span></span>
<span data-ttu-id="a740c-121">Per impostazione predefinita, le tendenze degli avvisi visualizzano le informazioni sugli avvisi del periodo di 30 giorni che terminano con l'ultimo giorno completo.</span><span class="sxs-lookup"><span data-stu-id="a740c-121">By default, the alert trends display alert information from the 30-day period ending in the latest full day.</span></span> <span data-ttu-id="a740c-122">Per ottenere una prospettiva migliore sulle tendenze che si verificano nell'organizzazione, è possibile ottimizzare il periodo di reporting modificando il periodo di tempo visualizzato.</span><span class="sxs-lookup"><span data-stu-id="a740c-122">To gain better perspective on trends occurring in your organization, you can fine-tune the reporting period by adjusting the time period shown.</span></span> <span data-ttu-id="a740c-123">Per regolare il periodo di tempo, selezionare un intervallo di tempo dalle opzioni a discesa:</span><span class="sxs-lookup"><span data-stu-id="a740c-123">To adjust the time period, select a time range from the drop-down options:</span></span>

- <span data-ttu-id="a740c-124">30 giorni</span><span class="sxs-lookup"><span data-stu-id="a740c-124">30 days</span></span>
- <span data-ttu-id="a740c-125">3 mesi</span><span class="sxs-lookup"><span data-stu-id="a740c-125">3 months</span></span>
- <span data-ttu-id="a740c-126">6 mesi</span><span class="sxs-lookup"><span data-stu-id="a740c-126">6 months</span></span>
- <span data-ttu-id="a740c-127">Personalizzato</span><span class="sxs-lookup"><span data-stu-id="a740c-127">Custom</span></span>

>[!NOTE]
><span data-ttu-id="a740c-128">Questi filtri vengono applicati solo nella sezione tendenze degli avvisi.</span><span class="sxs-lookup"><span data-stu-id="a740c-128">These filters are only applied on the alert trends section.</span></span> <span data-ttu-id="a740c-129">Non influisce sulla sezione di riepilogo degli avvisi.</span><span class="sxs-lookup"><span data-stu-id="a740c-129">It doesn't affect the alert summary section.</span></span>


## <a name="alert-summary"></a><span data-ttu-id="a740c-130">Riepilogo degli avvisi</span><span class="sxs-lookup"><span data-stu-id="a740c-130">Alert summary</span></span>
<span data-ttu-id="a740c-131">Mentre le tendenze degli avvisi mostrano informazioni sugli avvisi di tendenza, il riepilogo dell'avviso mostra le informazioni sugli avvisi nell'ambito del giorno corrente.</span><span class="sxs-lookup"><span data-stu-id="a740c-131">While the alert trends shows trending alert information, the alert summary shows alert information scoped to the current day.</span></span>

 <span data-ttu-id="a740c-132">Il riepilogo degli avvisi consente di eseguire il drill-down in una particolare coda di avvisi a cui è applicato il filtro corrispondente.</span><span class="sxs-lookup"><span data-stu-id="a740c-132">The alert summary allows you to drill down to a particular alert queue with the corresponding filter applied to it.</span></span> <span data-ttu-id="a740c-133">Ad esempio, facendo clic sulla barra EDR nella scheda Origini di rilevamento verrà visualizzata la coda degli avvisi con i risultati che mostrano solo gli avvisi generati dai rilevamenti EDR.</span><span class="sxs-lookup"><span data-stu-id="a740c-133">For example, clicking on the EDR bar in the Detection sources card will bring you the alerts queue with results showing only alerts generated from EDR detections.</span></span> 

>[!NOTE]
><span data-ttu-id="a740c-134">L'ambito dei dati visualizzati nella sezione di riepilogo è 180 giorni prima della data corrente.</span><span class="sxs-lookup"><span data-stu-id="a740c-134">The data reflected in the summary section is scoped to 180 days prior to the current date.</span></span> <span data-ttu-id="a740c-135">Ad esempio, se la data odierna è il 5 novembre 2019, i dati nella sezione di riepilogo rifletteranno i numeri a partire dal 5 maggio 2019 al 5 novembre 2019.</span><span class="sxs-lookup"><span data-stu-id="a740c-135">For example if today's date is November 5, 2019, the data on the summary section will reflect numbers starting from May 5, 2019 to November 5, 2019.</span></span><br>
> <span data-ttu-id="a740c-136">Il filtro applicato alla sezione tendenze non viene applicato alla sezione di riepilogo.</span><span class="sxs-lookup"><span data-stu-id="a740c-136">The filter applied on the trends section is not applied on the summary section.</span></span> 

## <a name="alert-attributes"></a><span data-ttu-id="a740c-137">Attributi degli avvisi</span><span class="sxs-lookup"><span data-stu-id="a740c-137">Alert attributes</span></span>
<span data-ttu-id="a740c-138">Il report è costituito da schede che visualizzano gli attributi di avviso seguenti:</span><span class="sxs-lookup"><span data-stu-id="a740c-138">The report is made up of cards that display the following alert attributes:</span></span>

- <span data-ttu-id="a740c-139">**Origini di** rilevamento: mostra informazioni sui sensori e sulle tecnologie di rilevamento che forniscono i dati utilizzati da Microsoft Defender for Endpoint per attivare gli avvisi.</span><span class="sxs-lookup"><span data-stu-id="a740c-139">**Detection sources**: shows information about the sensors and detection technologies that provide the data used by Microsoft Defender for Endpoint to trigger alerts.</span></span>

- <span data-ttu-id="a740c-140">**Categorie di minacce**: mostra i tipi di attività di minaccia o di attacco che hanno attivato gli avvisi, indicando le possibili aree di interesse per le operazioni di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="a740c-140">**Threat categories**: shows the types of threat or attack activity that triggered alerts, indicating possible focus areas for your security operations.</span></span>

- <span data-ttu-id="a740c-141">**Gravità**: mostra il livello di gravità degli avvisi, che indica l'impatto potenziale collettivo delle minacce per l'organizzazione e il livello di risposta necessario per affrontarli.</span><span class="sxs-lookup"><span data-stu-id="a740c-141">**Severity**: shows the severity level of alerts, indicating the collective potential impact of threats to your organization and the level of response needed to address them.</span></span>

- <span data-ttu-id="a740c-142">**Status**: mostra lo stato di risoluzione degli avvisi, che indica l'efficienza delle risposte agli avvisi manuali e della correzione automatica (se abilitata).</span><span class="sxs-lookup"><span data-stu-id="a740c-142">**Status**: shows the resolution status of alerts, indicating the efficiency of your manual alert responses and of automated remediation (if enabled).</span></span> 

- <span data-ttu-id="a740c-143">**Classificazione & determinazione**: mostra come sono stati classificati gli avvisi in base alla risoluzione, se sono stati classificati come minacce effettive (avvisi reali) o come rilevamenti non corretti (falsi avvisi).</span><span class="sxs-lookup"><span data-stu-id="a740c-143">**Classification & determination**: shows how you have classified alerts upon resolution, whether you have classified them as actual threats (true alerts) or as incorrect detections (false alerts).</span></span> <span data-ttu-id="a740c-144">Queste schede mostrano anche la determinazione degli avvisi risolti, fornendo informazioni aggiuntive come i tipi di minacce effettive trovate o le attività legittime rilevate in modo errato.</span><span class="sxs-lookup"><span data-stu-id="a740c-144">These cards also show the determination of resolved alerts, providing additional insight like the types of actual threats found or the legitimate activities that were incorrectly detected.</span></span>


 

## <a name="filter-data"></a><span data-ttu-id="a740c-145">Filtrare i dati</span><span class="sxs-lookup"><span data-stu-id="a740c-145">Filter data</span></span>

<span data-ttu-id="a740c-146">Utilizzare i filtri forniti per includere o escludere avvisi con determinati attributi.</span><span class="sxs-lookup"><span data-stu-id="a740c-146">Use the provided filters to include or exclude alerts with certain attributes.</span></span>

>[!NOTE]
><span data-ttu-id="a740c-147">Questi filtri si **applicano a** tutte le schede del report.</span><span class="sxs-lookup"><span data-stu-id="a740c-147">These filters apply to **all** the cards in the report.</span></span>

<span data-ttu-id="a740c-148">Ad esempio, per visualizzare solo i dati relativi agli avvisi di gravità elevata:</span><span class="sxs-lookup"><span data-stu-id="a740c-148">For example, to show data about high-severity alerts only:</span></span>

1. <span data-ttu-id="a740c-149">In **Filtri > Gravità** selezionare **Alta**</span><span class="sxs-lookup"><span data-stu-id="a740c-149">Under **Filters > Severity**, select **High**</span></span>
2. <span data-ttu-id="a740c-150">Assicurati che tutte le altre opzioni in **Gravità** siano deselezionate.</span><span class="sxs-lookup"><span data-stu-id="a740c-150">Ensure that all other options under **Severity** are deselected.</span></span>
3. <span data-ttu-id="a740c-151">Selezionare **Applica**.</span><span class="sxs-lookup"><span data-stu-id="a740c-151">Select **Apply**.</span></span> 

## <a name="related-topic"></a><span data-ttu-id="a740c-152">Argomento correlato</span><span class="sxs-lookup"><span data-stu-id="a740c-152">Related topic</span></span>
- [<span data-ttu-id="a740c-153">Report integrità e conformità dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="a740c-153">Device health and compliance report</span></span>](machine-reports.md)
