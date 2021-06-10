---
title: Analizzare i domini di Microsoft Defender per endpoint
description: Usa le opzioni di indagine per verificare se i dispositivi e i server comunicano con domini dannosi.
keywords: analizzare dominio, dominio, dominio dannoso, Microsoft Defender for Endpoint, avviso, URL
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
ms.collection:
- m365-security-compliance
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 7826229ba67384137c033745a5b85e557fc9c4a7
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933470"
---
# <a name="investigate-a-domain-associated-with-a-microsoft-defender-for-endpoint-alert"></a><span data-ttu-id="1209a-104">Analizzare un dominio associato a un avviso di Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="1209a-104">Investigate a domain associated with a Microsoft Defender for Endpoint alert</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="1209a-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="1209a-105">**Applies to:**</span></span>
- [<span data-ttu-id="1209a-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="1209a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1209a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1209a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="1209a-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="1209a-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="1209a-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="1209a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatedomain-abovefoldlink) 

<span data-ttu-id="1209a-110">Analizzare un dominio per verificare se i dispositivi e i server della rete aziendale comunicano con un dominio dannoso noto.</span><span class="sxs-lookup"><span data-stu-id="1209a-110">Investigate a domain to see if devices and servers in your enterprise network have been communicating with a known malicious domain.</span></span>

<span data-ttu-id="1209a-111">Puoi analizzare un dominio usando la funzionalità di ricerca o facendo clic su un collegamento di dominio dalla **sequenza temporale del dispositivo.**</span><span class="sxs-lookup"><span data-stu-id="1209a-111">You can investigate a domain by using the search feature or by clicking on a domain link from the **Device timeline**.</span></span>

<span data-ttu-id="1209a-112">È possibile visualizzare le informazioni delle sezioni seguenti nella visualizzazione URL:</span><span class="sxs-lookup"><span data-stu-id="1209a-112">You can see information from the following sections in the URL view:</span></span>

- <span data-ttu-id="1209a-113">Dettagli URL, Contatti, Server dei nomi</span><span class="sxs-lookup"><span data-stu-id="1209a-113">URL details, Contacts, Nameservers</span></span>
- <span data-ttu-id="1209a-114">Avvisi correlati a questo URL</span><span class="sxs-lookup"><span data-stu-id="1209a-114">Alerts related to this URL</span></span> 
- <span data-ttu-id="1209a-115">URL nell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="1209a-115">URL in organization</span></span>
- <span data-ttu-id="1209a-116">Dispositivi osservati più recenti con URL</span><span class="sxs-lookup"><span data-stu-id="1209a-116">Most recent observed devices with URL</span></span>

## <a name="url-worldwide"></a><span data-ttu-id="1209a-117">URL in tutto il mondo</span><span class="sxs-lookup"><span data-stu-id="1209a-117">URL worldwide</span></span>

<span data-ttu-id="1209a-118">Nella **sezione URL in** tutto il mondo sono elencati l'URL, un collegamento a ulteriori dettagli su Whois, il numero di eventi imprevisti aperti correlati e il numero di avvisi attivi.</span><span class="sxs-lookup"><span data-stu-id="1209a-118">The **URL Worldwide** section lists the URL, a link to further details at Whois, the number of related open incidents, and the number of active alerts.</span></span>

## <a name="incident"></a><span data-ttu-id="1209a-119">Incidente</span><span class="sxs-lookup"><span data-stu-id="1209a-119">Incident</span></span>

<span data-ttu-id="1209a-120">La **scheda Evento** imprevisto visualizza un grafico a barre di tutti gli avvisi attivi negli eventi imprevisti degli ultimi 180 giorni.</span><span class="sxs-lookup"><span data-stu-id="1209a-120">The **Incident** card displays a bar chart of all active alerts in incidents over the past 180 days.</span></span>

## <a name="prevalence"></a><span data-ttu-id="1209a-121">Prevalenza</span><span class="sxs-lookup"><span data-stu-id="1209a-121">Prevalence</span></span>

<span data-ttu-id="1209a-122">La **scheda Prevalenza** fornisce dettagli sulla diffusione dell'URL all'interno dell'organizzazione in un periodo di tempo specificato.</span><span class="sxs-lookup"><span data-stu-id="1209a-122">The **Prevalence** card provides details on the prevalence of the URL within the organization, over a specified period of time.</span></span>

<span data-ttu-id="1209a-123">Anche se il periodo di tempo predefinito è degli ultimi 30 giorni, è possibile personalizzare l'intervallo selezionando la freccia rivolta verso il basso nell'angolo della scheda.</span><span class="sxs-lookup"><span data-stu-id="1209a-123">Although the default time period is the past 30 days, you can customize the range by selecting the downward-pointing arrow in the corner of the card.</span></span> <span data-ttu-id="1209a-124">L'intervallo più breve disponibile è per la diffusione nell'ultimo giorno, mentre l'intervallo più lungo è negli ultimi 6 mesi.</span><span class="sxs-lookup"><span data-stu-id="1209a-124">The shortest range available is for prevalence over the past day, while the longest range is over the past 6 months.</span></span>

## <a name="alerts"></a><span data-ttu-id="1209a-125">Avvisi</span><span class="sxs-lookup"><span data-stu-id="1209a-125">Alerts</span></span>

<span data-ttu-id="1209a-126">Nella **scheda Avvisi** è disponibile un elenco di avvisi associati all'URL.</span><span class="sxs-lookup"><span data-stu-id="1209a-126">The **Alerts** tab provides a list of alerts that are associated with the URL.</span></span> <span data-ttu-id="1209a-127">La tabella riportata di seguito è una versione filtrata degli avvisi visibili nella schermata Della coda degli avvisi, che mostra solo gli avvisi associati al dominio, la gravità, lo stato, l'evento imprevisto associato, la classificazione, lo stato dell'indagine e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="1209a-127">The table shown here is a filtered version of the alerts visible on the Alert queue screen, showing only alerts associated with the domain, their severity, status, the associated incident, classification, investigation state, and more.</span></span>

<span data-ttu-id="1209a-128">La scheda Avvisi può essere modificata in modo da visualizzare più o meno informazioni selezionando **Personalizza** colonne dal menu delle azioni sopra le intestazioni di colonna.</span><span class="sxs-lookup"><span data-stu-id="1209a-128">The Alerts tab can be adjusted to show more or less information, by selecting **Customize columns** from the action menu above the column headers.</span></span> <span data-ttu-id="1209a-129">È inoltre possibile modificare il numero di elementi visualizzati selezionando gli elementi **per pagina** nello stesso menu.</span><span class="sxs-lookup"><span data-stu-id="1209a-129">The number of items displayed can also be adjusted, by selecting **items per page** on the same menu.</span></span>

## <a name="observed-in-organization"></a><span data-ttu-id="1209a-130">Osservato nell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="1209a-130">Observed in organization</span></span>

<span data-ttu-id="1209a-131">La **scheda Osservati nell'organizzazione** fornisce una visualizzazione cronologica degli eventi e degli avvisi associati osservati nell'URL.</span><span class="sxs-lookup"><span data-stu-id="1209a-131">The **Observed in organization** tab provides a chronological view on the events and associated alerts that were observed on the URL.</span></span> <span data-ttu-id="1209a-132">Questa scheda include una sequenza temporale e una tabella personalizzabile che elenca i dettagli dell'evento, ad esempio l'ora, il dispositivo e una breve descrizione dell'evento.</span><span class="sxs-lookup"><span data-stu-id="1209a-132">This tab includes a timeline and a customizable table listing event details, such as the time, device, and a brief description of what happened.</span></span> 

<span data-ttu-id="1209a-133">È possibile visualizzare gli eventi di diversi periodi di tempo immettendo le date nei campi di testo sopra le intestazioni della tabella.</span><span class="sxs-lookup"><span data-stu-id="1209a-133">You can view events from different periods of time by entering the dates into the text fields above the table headers.</span></span> <span data-ttu-id="1209a-134">Puoi anche personalizzare l'intervallo di tempo selezionando diverse aree della sequenza temporale.</span><span class="sxs-lookup"><span data-stu-id="1209a-134">You can also customize the time range by selecting different areas of the timeline.</span></span>

<span data-ttu-id="1209a-135">**Analizzare un dominio:**</span><span class="sxs-lookup"><span data-stu-id="1209a-135">**Investigate a domain:**</span></span>

1. <span data-ttu-id="1209a-136">Seleziona **URL** dal menu **a** discesa della barra di ricerca.</span><span class="sxs-lookup"><span data-stu-id="1209a-136">Select **URL** from the **Search bar** drop-down menu.</span></span>
2. <span data-ttu-id="1209a-137">Immettere l'URL nel **campo** Di ricerca.</span><span class="sxs-lookup"><span data-stu-id="1209a-137">Enter the URL in the **Search** field.</span></span>
3. <span data-ttu-id="1209a-138">Fare clic sull'icona di ricerca o premere **INVIO.**</span><span class="sxs-lookup"><span data-stu-id="1209a-138">Click the search icon   or press **Enter**.</span></span> <span data-ttu-id="1209a-139">Vengono visualizzati i dettagli sull'URL.</span><span class="sxs-lookup"><span data-stu-id="1209a-139">Details about the URL are displayed.</span></span> <span data-ttu-id="1209a-140">Nota: i risultati della ricerca verranno restituiti solo per gli URL osservati nelle comunicazioni dai dispositivi dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1209a-140">Note: search results will only be returned for URLs observed in communications from devices in the organization.</span></span>
4. <span data-ttu-id="1209a-141">Utilizzare i filtri di ricerca per definire i criteri di ricerca.</span><span class="sxs-lookup"><span data-stu-id="1209a-141">Use the search filters to define the search criteria.</span></span> <span data-ttu-id="1209a-142">Puoi anche usare la casella di ricerca della sequenza temporale per filtrare i risultati visualizzati di tutti i dispositivi nell'organizzazione osservati comunicando con l'URL, il file associato alla comunicazione e l'ultima data osservata.</span><span class="sxs-lookup"><span data-stu-id="1209a-142">You can also use the timeline search box to filter the displayed results of all devices in the organization observed communicating with the URL, the file associated with the communication and the last date observed.</span></span>
5. <span data-ttu-id="1209a-143">Se fai clic su uno dei nomi dei dispositivi, potrai passare alla visualizzazione del dispositivo, in cui puoi continuare ad analizzare gli avvisi, i comportamenti e gli eventi segnalati.</span><span class="sxs-lookup"><span data-stu-id="1209a-143">Clicking any of the device names will take you to that device's view, where you can continue investigate reported alerts, behaviors, and events.</span></span>

## <a name="related-topics"></a><span data-ttu-id="1209a-144">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="1209a-144">Related topics</span></span>
- [<span data-ttu-id="1209a-145">Visualizzare e organizzare la coda di Microsoft Defender for Endpoint Alerts</span><span class="sxs-lookup"><span data-stu-id="1209a-145">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="1209a-146">Gestire gli avvisi di Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="1209a-146">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="1209a-147">Analizzare gli avvisi di Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="1209a-147">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="1209a-148">Analizzare un file associato a un avviso di Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="1209a-148">Investigate a file associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="1209a-149">Analizzare i dispositivi nell'elenco Di Microsoft Defender per dispositivi endpoint</span><span class="sxs-lookup"><span data-stu-id="1209a-149">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="1209a-150">Analizzare un indirizzo IP associato a un avviso di Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="1209a-150">Investigate an IP address associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="1209a-151">Analizzare un account utente in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="1209a-151">Investigate a user account in Microsoft Defender for Endpoint</span></span>](investigate-user.md)
