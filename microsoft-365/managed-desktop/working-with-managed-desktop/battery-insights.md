---
title: Dati analitici sulle batterie
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, servizi, documentazione
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
# <a name="battery-insights"></a><span data-ttu-id="2bdcc-103">Dati analitici sulle batterie</span><span class="sxs-lookup"><span data-stu-id="2bdcc-103">Battery insights</span></span>
<span data-ttu-id="2bdcc-104">Questa visualizzazione fornisce metriche sull'alimentazione, la batteria e l'utilizzo delle app per i dispositivi Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="2bdcc-104">This view provides power, battery, and app usage metrics for your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="2bdcc-105">Per questi scopi, un'app viene considerata "in uso" se è in esecuzione e ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="2bdcc-105">For these purposes, an app is considered "in use" if it is running and in focus.</span></span>

<span data-ttu-id="2bdcc-106">Per visualizzare i dati di utilizzo, selezionare la **scheda** Batteria.</span><span class="sxs-lookup"><span data-stu-id="2bdcc-106">To view usage data, select the **Battery** tab.</span></span>

![Riquadro batteria: durata stimata della batteria per modello di dispositivo in alto a sinistra, consumo di energia superiore (per app) in alto a destra, tabella insights in basso.](../../media/insights_battery.png)

## <a name="predicted-battery-life"></a><span data-ttu-id="2bdcc-109">Durata della batteria stimata</span><span class="sxs-lookup"><span data-stu-id="2bdcc-109">Predicted battery life</span></span>

<span data-ttu-id="2bdcc-110">Nell'area **Durata prevista della** batteria, forniamo previsioni per la durata prevista della batteria per i dispositivi, organizzati in base al modello del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2bdcc-110">In the **Predicted battery life** area, we provide predictions for the expected battery life for your devices, organized by device model.</span></span>

> [!NOTE]
> <span data-ttu-id="2bdcc-111">Questi dati derivano dal campionamento dell'utilizzo dell'energia, del tempo di utilizzo e della capacità della batteria da una selezione casuale dei dispositivi nella distribuzione di Microsoft Managed Desktop che segnalano anche i dati. <em></em></span><span class="sxs-lookup"><span data-stu-id="2bdcc-111">This data is derived from sampling energy usage, usage time, and battery capacity from a random <em>selection</em> of the devices in your Microsoft Managed Desktop deployment that are also reporting data.</span></span>

<span data-ttu-id="2bdcc-112">La tabella fornisce la durata stimata della batteria (in ore), la durata media della batteria per gli stessi modelli in altre distribuzioni di Microsoft Managed Desktop e il numero di dispositivi che segnalano questi dati nell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="2bdcc-112">The table provides the predicted battery life (in hours), average battery life for the same models in other Microsoft Managed Desktop deployments, and the number of devices reporting this data in your environment.</span></span> <span data-ttu-id="2bdcc-113">Ordinare i dati selezionando le intestazioni di colonna.</span><span class="sxs-lookup"><span data-stu-id="2bdcc-113">Sort the data by selecting the column headings.</span></span>



## <a name="top-energy-consumers"></a><span data-ttu-id="2bdcc-114">Principali consumatori di energia</span><span class="sxs-lookup"><span data-stu-id="2bdcc-114">Top energy consumers</span></span>

<span data-ttu-id="2bdcc-115">Nell'area **Dei** principali consumatori di energia troverai nel tuo ambiente le app che consumano più energia in milliWatt-hours (mWh).</span><span class="sxs-lookup"><span data-stu-id="2bdcc-115">In the **Top energy consumers** area you’ll find the apps in your environment that consume the most energy in milliWatt-hours (mWh).</span></span> <span data-ttu-id="2bdcc-116">Le app visualizzate sono per dispositivo specifico, che puoi selezionare nella sezione **Durata** stimata della batteria a sinistra.</span><span class="sxs-lookup"><span data-stu-id="2bdcc-116">The apps shown are per specific device, which you select in the **Predicted battery life** section to the left.</span></span> <span data-ttu-id="2bdcc-117">Ad esempio, per vedere il consumo per app per i dispositivi Microsoft Surface Book 2, seleziona la riga nell'area di durata della batteria.</span><span class="sxs-lookup"><span data-stu-id="2bdcc-117">For example, to see the per-app consumption for your Microsoft Surface Book 2 devices, select that row in the battery life area.</span></span> <span data-ttu-id="2bdcc-118">Se non si seleziona alcun modello, i dati di consumo dell'app mostrati sono relativi a tutte le app per cui sono presenti dati collettivamente.</span><span class="sxs-lookup"><span data-stu-id="2bdcc-118">If you don't select any model, the app consumption data shown is for all apps that we have data for collectively.</span></span>

 <span data-ttu-id="2bdcc-119">Per ogni app, i segmenti colorati mostrano la distribuzione dell'uso dell'energia dell'app tra queste categorie:</span><span class="sxs-lookup"><span data-stu-id="2bdcc-119">For each app, colored segments show you the distribution of the app's energy use among these categories:</span></span>

- <span data-ttu-id="2bdcc-120">CPU</span><span class="sxs-lookup"><span data-stu-id="2bdcc-120">CPU</span></span>
- <span data-ttu-id="2bdcc-121">Visualizza</span><span class="sxs-lookup"><span data-stu-id="2bdcc-121">Display</span></span>
- <span data-ttu-id="2bdcc-122">Rete</span><span class="sxs-lookup"><span data-stu-id="2bdcc-122">Network</span></span>
- <span data-ttu-id="2bdcc-123">Altro</span><span class="sxs-lookup"><span data-stu-id="2bdcc-123">Other</span></span>

<span data-ttu-id="2bdcc-124">"Altro" potrebbe includere il consumo di energia da diverse origini, ad esempio attività su disco, utilizzo di banda larga mobile e perdita di energia per resistenza interna.</span><span class="sxs-lookup"><span data-stu-id="2bdcc-124">"Other" could include energy consumption by a variety of sources, such as disk activity, mobile broadband usage, and energy lost to internal resistance.</span></span> 

<span data-ttu-id="2bdcc-125">Puoi filtrare questa visualizzazione per mostrare solo le app in primo piano, le app in background o entrambe usando il menu in alto a destra.</span><span class="sxs-lookup"><span data-stu-id="2bdcc-125">You can filter this view to show only foreground apps, background apps, or both by using the menu in the upper right.</span></span> <span data-ttu-id="2bdcc-126">Le app in primo piano sono quelle che hanno avuto interazione con l'utente negli ultimi 28 giorni, ad esempio la selezione di qualcosa con il mouse.</span><span class="sxs-lookup"><span data-stu-id="2bdcc-126">Foreground apps are those that have had user interaction in the last 28 days, such as selecting something with a mouse.</span></span>

## <a name="insights"></a><span data-ttu-id="2bdcc-127">Dati analitici</span><span class="sxs-lookup"><span data-stu-id="2bdcc-127">Insights</span></span>

<span data-ttu-id="2bdcc-128">**L'area Dati** statistici mostra i primi tre consumatori di energia nelle categorie CPU e rete.</span><span class="sxs-lookup"><span data-stu-id="2bdcc-128">The **Insights** area shows the top three energy consumers in the CPU and network categories.</span></span> <span data-ttu-id="2bdcc-129">Questi elementi consumano energia superiore alla media rispetto a tutte le distribuzioni di Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="2bdcc-129">These items are consuming higher than average energy compared to all Microsoft Managed Desktop deployments.</span></span> <span data-ttu-id="2bdcc-130">La risorsa di visualizzazione non viene visualizzata perché dipende molto dal tempo di utilizzo del dispositivo e dalle impostazioni di luminosità dello schermo.</span><span class="sxs-lookup"><span data-stu-id="2bdcc-130">We don't show the display resource because it depends heavily on device usage time and screen brightness settings.</span></span> 

<span data-ttu-id="2bdcc-131">Per ulteriori informazioni, selezionare le **presentazioni** nella colonna Dettagli.</span><span class="sxs-lookup"><span data-stu-id="2bdcc-131">Select the listings in the **Details** column for more information.</span></span>

## <a name="battery-optimization"></a><span data-ttu-id="2bdcc-132">Ottimizzazione della batteria</span><span class="sxs-lookup"><span data-stu-id="2bdcc-132">Battery optimization</span></span>

<span data-ttu-id="2bdcc-133">Windows 10 offre numerose impostazioni [del dispositivo](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) per migliorare l'utilizzo dell'alimentazione e aumentare la durata della batteria dei dispositivi Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="2bdcc-133">Windows 10 offers numerous [device settings](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) to improve power usage and increase the battery life of your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="2bdcc-134">Alcune di queste impostazioni possono ridurre altre funzionalità di Windows, quindi dovrai anche prendere in considerazione altri fattori, ad esempio il ruolo del dispositivo nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="2bdcc-134">Some of these settings can decrease other Windows functionality, so you'll also have to consider other factors such as the role of the device in your organization.</span></span> <span data-ttu-id="2bdcc-135">Il supporto di Windows mantiene un elenco di questi suggerimenti [per il risparmio batteria.](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips)</span><span class="sxs-lookup"><span data-stu-id="2bdcc-135">Windows support maintains a list of these [battery saving tips](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips).</span></span>

<span data-ttu-id="2bdcc-136">Gli utenti possono modificare alcune impostazioni da soli senza la necessità di elevazione o supporto dell'amministratore.</span><span class="sxs-lookup"><span data-stu-id="2bdcc-136">Users can adjust some settings on their own without the need for admin elevation or support.</span></span> <span data-ttu-id="2bdcc-137">Altre impostazioni richiedono il supporto dell'amministratore IT dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="2bdcc-137">Other settings require support from your organization's IT administrator.</span></span>
