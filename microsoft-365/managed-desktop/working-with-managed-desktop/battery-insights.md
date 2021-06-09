---
title: Dati analitici sulle batterie
description: Report che mostra i dati sulla durata stimata della batteria e sui principali consumatori di energia
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 32ab3a984d5ab46aac26989518cd3e570082d688
ms.sourcegitcommit: cebbdd393dcfd93ff43a1ab66ad70115853f83e7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2021
ms.locfileid: "52739833"
---
# <a name="battery-insights"></a><span data-ttu-id="25f14-104">Dati analitici sulle batterie</span><span class="sxs-lookup"><span data-stu-id="25f14-104">Battery insights</span></span>
<span data-ttu-id="25f14-105">Questa visualizzazione fornisce metriche sull'utilizzo di alimentazione, batteria e app per i Microsoft Managed Desktop dispositivi.</span><span class="sxs-lookup"><span data-stu-id="25f14-105">This view provides power, battery, and app usage metrics for your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="25f14-106">Per questi scopi, un'app viene considerata "in uso" se è in esecuzione e a fuoco.</span><span class="sxs-lookup"><span data-stu-id="25f14-106">For these purposes, an app is considered "in use" if it is running and in focus.</span></span>

<span data-ttu-id="25f14-107">Per visualizzare i dati di utilizzo, selezionare la **scheda** Batteria.</span><span class="sxs-lookup"><span data-stu-id="25f14-107">To view usage data, select the **Battery** tab.</span></span>

![Riquadro batteria: durata stimata della batteria per modello di dispositivo in alto a sinistra, consumo di energia superiore (per app) in alto a destra, tabella insights nella parte inferiore.](../../media/insights_battery.png)

## <a name="predicted-battery-life"></a><span data-ttu-id="25f14-110">Durata stimata della batteria</span><span class="sxs-lookup"><span data-stu-id="25f14-110">Predicted battery life</span></span>

<span data-ttu-id="25f14-111">Nell'area **Durata prevista della** batteria vengono fornite previsioni per la durata prevista della batteria per i dispositivi, organizzati in base al modello di dispositivo.</span><span class="sxs-lookup"><span data-stu-id="25f14-111">In the **Predicted battery life** area, we provide predictions for the expected battery life for your devices, organized by device model.</span></span>

> [!NOTE]
> <span data-ttu-id="25f14-112">Questi dati derivano dal campionamento dell'utilizzo di <em></em> energia, del tempo di utilizzo e della capacità della batteria da una selezione casuale dei dispositivi nella distribuzione Microsoft Managed Desktop che segnalano anche i dati.</span><span class="sxs-lookup"><span data-stu-id="25f14-112">This data is derived from sampling energy usage, usage time, and battery capacity from a random <em>selection</em> of the devices in your Microsoft Managed Desktop deployment that are also reporting data.</span></span>

<span data-ttu-id="25f14-113">La tabella fornisce la durata stimata della batteria (in ore), la durata media della batteria per gli stessi modelli in altre distribuzioni di Microsoft Managed Desktop e il numero di dispositivi che segnalano questi dati nell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="25f14-113">The table provides the predicted battery life (in hours), average battery life for the same models in other Microsoft Managed Desktop deployments, and the number of devices reporting this data in your environment.</span></span> <span data-ttu-id="25f14-114">Ordinare i dati selezionando le intestazioni di colonna.</span><span class="sxs-lookup"><span data-stu-id="25f14-114">Sort the data by selecting the column headings.</span></span>



## <a name="top-energy-consumers"></a><span data-ttu-id="25f14-115">Principali consumatori di energia</span><span class="sxs-lookup"><span data-stu-id="25f14-115">Top energy consumers</span></span>

<span data-ttu-id="25f14-116">Nell'area **Consumatori** di energia principali sono disponibili le app nell'ambiente che consumano più energia in milliWatt-hours (mWh).</span><span class="sxs-lookup"><span data-stu-id="25f14-116">In the **Top energy consumers** area you’ll find the apps in your environment that consume the most energy in milliWatt-hours (mWh).</span></span> <span data-ttu-id="25f14-117">Le app visualizzate sono per dispositivo specifico, che è possibile selezionare nella **sezione Durata stimata** della batteria a sinistra.</span><span class="sxs-lookup"><span data-stu-id="25f14-117">The apps shown are per specific device, which you select in the **Predicted battery life** section to the left.</span></span> <span data-ttu-id="25f14-118">Ad esempio, per visualizzare il consumo per app per i dispositivi Microsoft Surface Book 2, seleziona la riga nell'area durata della batteria.</span><span class="sxs-lookup"><span data-stu-id="25f14-118">For example, to see the per-app consumption for your Microsoft Surface Book 2 devices, select that row in the battery life area.</span></span> <span data-ttu-id="25f14-119">Se non si seleziona alcun modello, i dati di consumo delle app visualizzati sono per tutte le app per cui sono disponibili dati collettivamente.</span><span class="sxs-lookup"><span data-stu-id="25f14-119">If you don't select any model, the app consumption data shown is for all apps that we have data for collectively.</span></span>

 <span data-ttu-id="25f14-120">Per ogni app, i segmenti colorati mostrano la distribuzione dell'uso dell'energia dell'app tra queste categorie:</span><span class="sxs-lookup"><span data-stu-id="25f14-120">For each app, colored segments show you the distribution of the app's energy use among these categories:</span></span>

- <span data-ttu-id="25f14-121">CPU</span><span class="sxs-lookup"><span data-stu-id="25f14-121">CPU</span></span>
- <span data-ttu-id="25f14-122">Display</span><span class="sxs-lookup"><span data-stu-id="25f14-122">Display</span></span>
- <span data-ttu-id="25f14-123">Rete</span><span class="sxs-lookup"><span data-stu-id="25f14-123">Network</span></span>
- <span data-ttu-id="25f14-124">Altro</span><span class="sxs-lookup"><span data-stu-id="25f14-124">Other</span></span>

<span data-ttu-id="25f14-125">"Altro" potrebbe includere il consumo di energia da un'ampia gamma di fonti, come l'attività del disco, l'utilizzo della banda larga mobile e l'energia persa a causa della resistenza interna.</span><span class="sxs-lookup"><span data-stu-id="25f14-125">"Other" could include energy consumption by a variety of sources, such as disk activity, mobile broadband usage, and energy lost to internal resistance.</span></span> 

<span data-ttu-id="25f14-126">Puoi filtrare questa visualizzazione per mostrare solo le app in primo piano, le app in background o entrambe usando il menu in alto a destra.</span><span class="sxs-lookup"><span data-stu-id="25f14-126">You can filter this view to show only foreground apps, background apps, or both by using the menu in the upper right.</span></span> <span data-ttu-id="25f14-127">Le app in primo piano sono quelle che hanno avuto interazione con l'utente negli ultimi 28 giorni, ad esempio la selezione di un elemento con il mouse.</span><span class="sxs-lookup"><span data-stu-id="25f14-127">Foreground apps are those that have had user interaction in the last 28 days, such as selecting something with a mouse.</span></span>

## <a name="insights"></a><span data-ttu-id="25f14-128">Dati analitici</span><span class="sxs-lookup"><span data-stu-id="25f14-128">Insights</span></span>

<span data-ttu-id="25f14-129">**L'area Insights** mostra i primi tre consumatori di energia nelle categorie CPU e rete.</span><span class="sxs-lookup"><span data-stu-id="25f14-129">The **Insights** area shows the top three energy consumers in the CPU and network categories.</span></span> <span data-ttu-id="25f14-130">Questi elementi consumano energia superiore alla media rispetto a tutte le Microsoft Managed Desktop distribuzione.</span><span class="sxs-lookup"><span data-stu-id="25f14-130">These items are consuming higher than average energy compared to all Microsoft Managed Desktop deployments.</span></span> <span data-ttu-id="25f14-131">La risorsa di visualizzazione non viene visualizzata perché dipende in larga parte dalle impostazioni di tempo di utilizzo del dispositivo e luminosità dello schermo.</span><span class="sxs-lookup"><span data-stu-id="25f14-131">We don't show the display resource because it depends heavily on device usage time and screen brightness settings.</span></span> 

<span data-ttu-id="25f14-132">Per ulteriori informazioni, selezionare **le presentazioni** nella colonna Dettagli.</span><span class="sxs-lookup"><span data-stu-id="25f14-132">Select the listings in the **Details** column for more information.</span></span>

## <a name="battery-optimization"></a><span data-ttu-id="25f14-133">Ottimizzazione della batteria</span><span class="sxs-lookup"><span data-stu-id="25f14-133">Battery optimization</span></span>

<span data-ttu-id="25f14-134">Windows 10 offre numerose impostazioni [del dispositivo](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) per migliorare l'utilizzo dell'alimentazione e aumentare la durata della batteria dei Microsoft Managed Desktop dispositivi.</span><span class="sxs-lookup"><span data-stu-id="25f14-134">Windows 10 offers numerous [device settings](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) to improve power usage and increase the battery life of your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="25f14-135">Alcune di queste impostazioni possono ridurre altre funzionalità Windows, quindi dovrai anche considerare altri fattori, ad esempio il ruolo del dispositivo nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="25f14-135">Some of these settings can decrease other Windows functionality, so you'll also have to consider other factors such as the role of the device in your organization.</span></span> <span data-ttu-id="25f14-136">Windows supporto mantiene un elenco di questi suggerimenti per il [risparmio della batteria.](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips)</span><span class="sxs-lookup"><span data-stu-id="25f14-136">Windows support maintains a list of these [battery saving tips](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips).</span></span>

<span data-ttu-id="25f14-137">Gli utenti possono modificare alcune impostazioni in modo personalizzato senza la necessità di elevazione o supporto dell'amministratore.</span><span class="sxs-lookup"><span data-stu-id="25f14-137">Users can adjust some settings on their own without the need for admin elevation or support.</span></span> <span data-ttu-id="25f14-138">Altre impostazioni richiedono il supporto dell'amministratore IT dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="25f14-138">Other settings require support from your organization's IT administrator.</span></span>
