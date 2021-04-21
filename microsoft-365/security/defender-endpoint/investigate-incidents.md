---
title: Analizzare gli eventi imprevisti in Microsoft Defender for Endpoint
description: Visualizzare gli avvisi associati, gestire l'evento imprevisto e visualizzare i metadati degli avvisi per analizzare un evento imprevisto
keywords: analizzare, incidente, avvisi, metadati, rischio, origine di rilevamento, dispositivi interessati, modelli, correlazione
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
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 1d8f4452273047684a30db3b18d1281f40f46378
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903299"
---
# <a name="investigate-incidents-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="70085-104">Analizzare gli eventi imprevisti in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="70085-104">Investigate incidents in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="70085-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="70085-105">**Applies to:**</span></span>
- [<span data-ttu-id="70085-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="70085-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="70085-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="70085-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


<span data-ttu-id="70085-108">Analizzare gli eventi imprevisti che interessano la rete, comprenderne il significato e raccogliere le prove per risolverli.</span><span class="sxs-lookup"><span data-stu-id="70085-108">Investigate incidents that affect your network, understand what they mean, and collate evidence to resolve them.</span></span> 

<span data-ttu-id="70085-109">Quando si analizza un evento imprevisto, viene visualizzato:</span><span class="sxs-lookup"><span data-stu-id="70085-109">When you investigate an incident, you'll see:</span></span>
- <span data-ttu-id="70085-110">Dettagli incidente</span><span class="sxs-lookup"><span data-stu-id="70085-110">Incident details</span></span>
- <span data-ttu-id="70085-111">Azioni e commenti relativi agli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="70085-111">Incident comments and actions</span></span>
- <span data-ttu-id="70085-112">Schede (avvisi, dispositivi, indagini, prove, grafico)</span><span class="sxs-lookup"><span data-stu-id="70085-112">Tabs (alerts, devices, investigations, evidence, graph)</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4qLUV]


## <a name="analyze-incident-details"></a><span data-ttu-id="70085-113">Analizzare i dettagli dell'evento imprevisto</span><span class="sxs-lookup"><span data-stu-id="70085-113">Analyze incident details</span></span> 
<span data-ttu-id="70085-114">Fare clic su un evento imprevisto per visualizzare **il riquadro Operazioni non consentite.**</span><span class="sxs-lookup"><span data-stu-id="70085-114">Click an incident to see the **Incident pane**.</span></span> <span data-ttu-id="70085-115">Seleziona **Apri pagina evento imprevisto** per visualizzare i dettagli dell'evento imprevisto e le informazioni correlate (avvisi, dispositivi, indagini, prove, grafico).</span><span class="sxs-lookup"><span data-stu-id="70085-115">Select **Open incident page** to see the incident details and related information (alerts, devices, investigations, evidence, graph).</span></span> 

![Immagine dei dettagli dell'evento imprevisto1](images/atp-incident-details.png)

### <a name="alerts"></a><span data-ttu-id="70085-117">Avvisi</span><span class="sxs-lookup"><span data-stu-id="70085-117">Alerts</span></span>
<span data-ttu-id="70085-118">È possibile analizzare gli avvisi e vedere come sono stati collegati in un evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="70085-118">You can investigate the alerts and see how they were linked together in an incident.</span></span> <span data-ttu-id="70085-119">Gli avvisi sono raggruppati in eventi imprevisti in base ai motivi seguenti:</span><span class="sxs-lookup"><span data-stu-id="70085-119">Alerts are grouped into incidents based on the following reasons:</span></span>
- <span data-ttu-id="70085-120">Indagine automatizzata - L'indagine automatizzata ha attivato l'avviso collegato durante l'analisi dell'avviso originale</span><span class="sxs-lookup"><span data-stu-id="70085-120">Automated investigation - The automated investigation triggered the linked alert while investigating the original alert</span></span> 
- <span data-ttu-id="70085-121">Caratteristiche dei file - I file associati all'avviso hanno caratteristiche simili</span><span class="sxs-lookup"><span data-stu-id="70085-121">File characteristics - The files associated with the alert have similar characteristics</span></span>
- <span data-ttu-id="70085-122">Associazione manuale: un utente ha collegato manualmente gli avvisi</span><span class="sxs-lookup"><span data-stu-id="70085-122">Manual association - A user manually linked the alerts</span></span>
- <span data-ttu-id="70085-123">Tempo di proximate- Gli avvisi sono stati attivati sullo stesso dispositivo entro un determinato intervallo di tempo</span><span class="sxs-lookup"><span data-stu-id="70085-123">Proximate time - The alerts were triggered on the same device within a certain timeframe</span></span>
- <span data-ttu-id="70085-124">Stesso file: i file associati all'avviso sono esattamente gli stessi</span><span class="sxs-lookup"><span data-stu-id="70085-124">Same file - The files associated with the alert are exactly the same</span></span>
- <span data-ttu-id="70085-125">Stesso URL- L'URL che ha attivato l'avviso è esattamente lo stesso</span><span class="sxs-lookup"><span data-stu-id="70085-125">Same URL - The URL that triggered the alert is exactly the same</span></span>

![Immagine della scheda degli avvisi con la pagina dei dettagli dell'evento imprevisto che mostra i motivi per cui gli avvisi sono stati collegati tra loro nell'evento imprevisto](images/atp-incidents-alerts-reason.png)

<span data-ttu-id="70085-127">Puoi anche gestire un avviso e visualizzare i metadati dell'avviso insieme ad altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="70085-127">You can also manage an alert and see alert metadata along with other information.</span></span> <span data-ttu-id="70085-128">Per ulteriori informazioni, vedere [Analizzare gli avvisi.](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="70085-128">For more information, see [Investigate alerts](investigate-alerts.md).</span></span> 

### <a name="devices"></a><span data-ttu-id="70085-129">Dispositivi</span><span class="sxs-lookup"><span data-stu-id="70085-129">Devices</span></span>
<span data-ttu-id="70085-130">Puoi anche analizzare i dispositivi che fanno parte di un evento imprevisto o sono correlati a un determinato evento.</span><span class="sxs-lookup"><span data-stu-id="70085-130">You can also investigate the devices that are part of, or related to, a given incident.</span></span> <span data-ttu-id="70085-131">Per altre informazioni, vedi [Analizzare i dispositivi.](investigate-machines.md)</span><span class="sxs-lookup"><span data-stu-id="70085-131">For more information, see [Investigate devices](investigate-machines.md).</span></span>

![Scheda Immagine dei dispositivi nella pagina dei dettagli dell'evento imprevisto](images/atp-incident-device-tab.png)

### <a name="investigations"></a><span data-ttu-id="70085-133">Indagini</span><span class="sxs-lookup"><span data-stu-id="70085-133">Investigations</span></span>
<span data-ttu-id="70085-134">Selezionare **Indagini per** visualizzare tutte le indagini automatiche avviate dal sistema in risposta agli avvisi relativi agli eventi imprevisti.</span><span class="sxs-lookup"><span data-stu-id="70085-134">Select **Investigations** to see all the automatic investigations launched by the system in response to the incident alerts.</span></span>

![Immagine della scheda indagini nella pagina dei dettagli dell'evento imprevisto](images/atp-incident-investigations-tab.png)

## <a name="going-through-the-evidence"></a><span data-ttu-id="70085-136">Passare attraverso le prove</span><span class="sxs-lookup"><span data-stu-id="70085-136">Going through the evidence</span></span>
<span data-ttu-id="70085-137">Microsoft Defender for Endpoint analizza automaticamente tutti gli eventi supportati e le entità sospette degli eventi imprevisti negli avvisi, fornendoti la risposta automatica e le informazioni sui file, i processi, i servizi e altro ancora importanti.</span><span class="sxs-lookup"><span data-stu-id="70085-137">Microsoft Defender for Endpoint automatically investigates all the incidents' supported events and suspicious entities in the alerts, providing you with autoresponse and information about the important files, processes, services, and more.</span></span> 

<span data-ttu-id="70085-138">Ognuna delle entità analizzate verrà contrassegnata come infetta, correttiva o sospetta.</span><span class="sxs-lookup"><span data-stu-id="70085-138">Each of the analyzed entities will be marked as infected, remediated, or suspicious.</span></span> 

![Scheda Immagine della prova nella pagina dei dettagli dell'evento imprevisto](images/atp-incident-evidence-tab.png)

## <a name="visualizing-associated-cybersecurity-threats"></a><span data-ttu-id="70085-140">Visualizzazione delle minacce di cybersecurity associate</span><span class="sxs-lookup"><span data-stu-id="70085-140">Visualizing associated cybersecurity threats</span></span> 
<span data-ttu-id="70085-141">Microsoft Defender for Endpoint aggrega le informazioni sulle minacce in un evento imprevisto in modo da poter visualizzare i modelli e le correlazioni provenienti da diversi punti dati.</span><span class="sxs-lookup"><span data-stu-id="70085-141">Microsoft Defender for Endpoint aggregates the threat information into an incident so you can see the patterns and correlations coming in from various data points.</span></span> <span data-ttu-id="70085-142">È possibile visualizzare tale correlazione tramite il grafico degli eventi imprevisti.</span><span class="sxs-lookup"><span data-stu-id="70085-142">You can view such correlation through the incident graph.</span></span>

### <a name="incident-graph"></a><span data-ttu-id="70085-143">Grafico degli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="70085-143">Incident graph</span></span>
<span data-ttu-id="70085-144">Il **grafico** narra la storia dell'attacco di cybersecurity.</span><span class="sxs-lookup"><span data-stu-id="70085-144">The **Graph** tells the story of the cybersecurity attack.</span></span> <span data-ttu-id="70085-145">Ad esempio, mostra qual era il punto di ingresso, quale indicatore di compromissione o attività è stato osservato su quale dispositivo.</span><span class="sxs-lookup"><span data-stu-id="70085-145">For example, it shows you what was the entry point, which indicator of compromise or activity was observed on which device.</span></span> <span data-ttu-id="70085-146">ecc.</span><span class="sxs-lookup"><span data-stu-id="70085-146">etc.</span></span>

![Immagine del grafico degli eventi imprevisti](images/atp-incident-graph-tab.png)

<span data-ttu-id="70085-148">È possibile fare clic sui cerchi nel grafico degli eventi imprevisti per visualizzare i dettagli dei file dannosi, i rilevamenti di file associati, il numero di istanze presenti in tutto il mondo, se è stato osservato nell'organizzazione, in tal caso, il numero di istanze.</span><span class="sxs-lookup"><span data-stu-id="70085-148">You can click the circles on the incident graph to view the details of the malicious files, associated file detections, how many instances have there been worldwide, whether it’s been observed in your organization, if so, how many instances.</span></span>

![Immagine dei dettagli dell'evento imprevisto](images/atp-incident-graph-details.png)

## <a name="related-topics"></a><span data-ttu-id="70085-150">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="70085-150">Related topics</span></span>
- [<span data-ttu-id="70085-151">Coda incidenti</span><span class="sxs-lookup"><span data-stu-id="70085-151">Incidents queue</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [<span data-ttu-id="70085-152">Analizzare gli eventi imprevisti in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="70085-152">Investigate incidents in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-incidents)
- [<span data-ttu-id="70085-153">Gestire gli eventi imprevisti di Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="70085-153">Manage Microsoft Defender for Endpoint incidents</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-incidents)
