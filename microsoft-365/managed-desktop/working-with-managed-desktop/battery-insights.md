---
title: Dati analitici sulle batterie
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: f339fc98ea94c291c533045e9906f626f4b74e2a
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2020
ms.locfileid: "46529840"
---
# <a name="battery-insights"></a><span data-ttu-id="0739b-103">Dati analitici sulle batterie</span><span class="sxs-lookup"><span data-stu-id="0739b-103">Battery insights</span></span>
<span data-ttu-id="0739b-104">Questa visualizzazione fornisce metriche per l'utilizzo di energia, batteria e app per i dispositivi Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="0739b-104">This view provides power, battery, and app usage metrics for your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="0739b-105">A tal fine, un'app viene considerata "in uso" se è in esecuzione e in stato di inattività.</span><span class="sxs-lookup"><span data-stu-id="0739b-105">For these purposes, an app is considered "in use" if it is running and in focus.</span></span>

<span data-ttu-id="0739b-106">Per visualizzare i dati di utilizzo, selezionare la scheda **batteria** .</span><span class="sxs-lookup"><span data-stu-id="0739b-106">To view usage data, select the **Battery** tab.</span></span>

![Riquadro della batteria: durata stimata della batteria per modello di dispositivo in alto a sinistra, consumer energetici superiori (per app) in alto a destra, tabella Insights nella parte inferiore.](../../media/insights_battery.png)

## <a name="predicted-battery-life"></a><span data-ttu-id="0739b-109">Durata prevista della batteria</span><span class="sxs-lookup"><span data-stu-id="0739b-109">Predicted battery life</span></span>

<span data-ttu-id="0739b-110">Nell'area di **durata della batteria** prevista, vengono fornite previsioni per la durata prevista della batteria per i dispositivi, organizzati per modello di dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0739b-110">In the **Predicted battery life** area, we provide predictions for the expected battery life for your devices, organized by device model.</span></span>

> [!NOTE]
> <span data-ttu-id="0739b-111">Questi dati sono derivati dal campionamento dell'utilizzo di energia, dal tempo di utilizzo e dalla capacità della batteria da una <em>selezione</em> casuale dei dispositivi nella distribuzione di Microsoft Managed Desktop che sono anche i dati di report.</span><span class="sxs-lookup"><span data-stu-id="0739b-111">This data is derived from sampling energy usage, usage time, and battery capacity from a random <em>selection</em> of the devices in your Microsoft Managed Desktop deployment that are also reporting data.</span></span>

<span data-ttu-id="0739b-112">La tabella fornisce la durata prevista della batteria (in ore), la durata media della batteria per gli stessi modelli in altre distribuzioni di Microsoft Managed Desktop e il numero di dispositivi che segnalano tali dati nell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="0739b-112">The table provides the predicted battery life (in hours), average battery life for the same models in other Microsoft Managed Desktop deployments, and the number of devices reporting this data in your environment.</span></span> <span data-ttu-id="0739b-113">Ordinare i dati selezionando le intestazioni di colonna.</span><span class="sxs-lookup"><span data-stu-id="0739b-113">Sort the data by selecting the column headings.</span></span>



## <a name="top-energy-consumers"></a><span data-ttu-id="0739b-114">Top Energy consumer</span><span class="sxs-lookup"><span data-stu-id="0739b-114">Top energy consumers</span></span>

<span data-ttu-id="0739b-115">Nell'area **Top Energy consumer** sono disponibili le app nel proprio ambiente che consumano il maggior numero di energia in milliwatt-hours (MWh).</span><span class="sxs-lookup"><span data-stu-id="0739b-115">In the **Top energy consumers** area you’ll find the apps in your environment that consume the most energy in milliWatt-hours (mWh).</span></span> <span data-ttu-id="0739b-116">Le app mostrate sono per dispositivo specifico, che si seleziona nella sezione **durata prevista della batteria** a sinistra.</span><span class="sxs-lookup"><span data-stu-id="0739b-116">The apps shown are per specific device, which you select in the **Predicted battery life** section to the left.</span></span> <span data-ttu-id="0739b-117">Ad esempio, per visualizzare il consumo per ogni app per i dispositivi di Microsoft Surface Book 2, selezionare tale riga nell'area Durata batteria.</span><span class="sxs-lookup"><span data-stu-id="0739b-117">For example, to see the per-app consumption for your Microsoft Surface Book 2 devices, select that row in the battery life area.</span></span> <span data-ttu-id="0739b-118">Se non si seleziona un modello, i dati di consumo delle app sono visualizzati per tutte le app che sono disponibili per i dati collettivi.</span><span class="sxs-lookup"><span data-stu-id="0739b-118">If you don't select any model, the app consumption data shown is for all apps that we have data for collectively.</span></span>

 <span data-ttu-id="0739b-119">Per ogni app, i segmenti colorati mostrano la distribuzione dell'utilizzo di energia dell'app tra queste categorie:</span><span class="sxs-lookup"><span data-stu-id="0739b-119">For each app, colored segments show you the distribution of the app's energy use among these categories:</span></span>

- <span data-ttu-id="0739b-120">CPU</span><span class="sxs-lookup"><span data-stu-id="0739b-120">CPU</span></span>
- <span data-ttu-id="0739b-121">Visualizza</span><span class="sxs-lookup"><span data-stu-id="0739b-121">Display</span></span>
- <span data-ttu-id="0739b-122">Rete</span><span class="sxs-lookup"><span data-stu-id="0739b-122">Network</span></span>
- <span data-ttu-id="0739b-123">Altro</span><span class="sxs-lookup"><span data-stu-id="0739b-123">Other</span></span>

<span data-ttu-id="0739b-124">"Altro" potrebbe includere il consumo di energia da diverse fonti, come l'attività su disco, l'utilizzo della banda larga mobile e l'energia persa per la resistenza interna.</span><span class="sxs-lookup"><span data-stu-id="0739b-124">"Other" could include energy consumption by a variety of sources, such as disk activity, mobile broadband usage, and energy lost to internal resistance.</span></span> 

<span data-ttu-id="0739b-125">È possibile filtrare questa visualizzazione in modo da visualizzare solo le app in primo piano, le app in background o entrambe utilizzando il menu in alto a destra.</span><span class="sxs-lookup"><span data-stu-id="0739b-125">You can filter this view to show only foreground apps, background apps, or both by using the menu in the upper right.</span></span> <span data-ttu-id="0739b-126">Le app in primo piano sono quelle che hanno avuto l'interazione degli utenti negli ultimi 28 giorni, ad esempio la selezione di un elemento con un mouse.</span><span class="sxs-lookup"><span data-stu-id="0739b-126">Foreground apps are those that have had user interaction in the last 28 days, such as selecting something with a mouse.</span></span>

## <a name="insights"></a><span data-ttu-id="0739b-127">Approfondimenti</span><span class="sxs-lookup"><span data-stu-id="0739b-127">Insights</span></span>

<span data-ttu-id="0739b-128">Nell'area **Insights** sono elencati i primi tre consumer energetici nelle categorie CPU e rete.</span><span class="sxs-lookup"><span data-stu-id="0739b-128">The **Insights** area shows the top three energy consumers in the CPU and network categories.</span></span> <span data-ttu-id="0739b-129">Questi elementi consumano energia superiore alla media rispetto a tutte le distribuzioni desktop Microsoft gestite.</span><span class="sxs-lookup"><span data-stu-id="0739b-129">These items are consuming higher than average energy compared to all Microsoft Managed Desktop deployments.</span></span> <span data-ttu-id="0739b-130">Non viene visualizzata la risorsa di visualizzazione perché dipende fortemente dalle impostazioni di tempo di utilizzo del dispositivo e della luminosità dello schermo.</span><span class="sxs-lookup"><span data-stu-id="0739b-130">We don't show the display resource because it depends heavily on device usage time and screen brightness settings.</span></span> 

<span data-ttu-id="0739b-131">Per ulteriori informazioni, selezionare gli elenchi nella colonna **Details** .</span><span class="sxs-lookup"><span data-stu-id="0739b-131">Select the listings in the **Details** column for more information.</span></span>

## <a name="battery-optimization"></a><span data-ttu-id="0739b-132">Ottimizzazione della batteria</span><span class="sxs-lookup"><span data-stu-id="0739b-132">Battery optimization</span></span>

<span data-ttu-id="0739b-133">Windows 10 offre numerose [impostazioni del dispositivo](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) per migliorare l'utilizzo dell'alimentazione e aumentare la durata della batteria dei dispositivi Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="0739b-133">Windows 10 offers numerous [device settings](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) to improve power usage and increase the battery life of your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="0739b-134">Alcune di queste impostazioni possono ridurre le altre funzionalità di Windows, pertanto è necessario prendere in considerazione anche altri fattori, ad esempio il ruolo del dispositivo nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0739b-134">Some of these settings can decrease other Windows functionality, so you'll also have to consider other factors such as the role of the device in your organization.</span></span> <span data-ttu-id="0739b-135">Il supporto di Windows gestisce un elenco di questi suggerimenti per il [salvataggio della batteria](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips).</span><span class="sxs-lookup"><span data-stu-id="0739b-135">Windows support maintains a list of these [battery saving tips](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips).</span></span>

<span data-ttu-id="0739b-136">Gli utenti possono modificare le impostazioni in base alle proprie esigenze, senza necessità di supporto o elevazione di amministratore.</span><span class="sxs-lookup"><span data-stu-id="0739b-136">Users can adjust some settings on their own without the need for admin elevation or support.</span></span> <span data-ttu-id="0739b-137">Altre impostazioni richiedono supporto dall'amministratore IT dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0739b-137">Other settings require support from your organization's IT administrator.</span></span>
