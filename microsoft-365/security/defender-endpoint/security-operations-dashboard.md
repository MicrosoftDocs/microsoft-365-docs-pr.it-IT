---
title: Dashboard delle operazioni di sicurezza di Microsoft Defender Security Center
description: Usa il dashboard per identificare i dispositivi a rischio, tenere traccia dello stato del servizio e visualizzare statistiche e informazioni su dispositivi e avvisi.
keywords: dashboard, avvisi, nuovo, in corso, risolto, rischio, dispositivi a rischio, infezioni, report, statistiche, grafici, grafici, integrità, rilevamenti malware attivi, categoria di minacce, categorie, furto di password, ransomware, exploit, minaccia, bassa gravità, malware attivo
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: bfa23138b1bab4abcdfa0b4b9d689a4a4cfc7fc1
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064914"
---
# <a name="microsoft-defender-security-center-security-operations-dashboard"></a><span data-ttu-id="eda13-104">Dashboard delle operazioni di sicurezza di Microsoft Defender Security Center</span><span class="sxs-lookup"><span data-stu-id="eda13-104">Microsoft Defender Security Center Security operations dashboard</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="eda13-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="eda13-105">**Applies to:**</span></span>
- [<span data-ttu-id="eda13-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="eda13-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="eda13-107">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="eda13-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="eda13-108">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="eda13-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-secopsdashboard-abovefoldlink) 

<span data-ttu-id="eda13-109">Il **dashboard delle operazioni di sicurezza** è il punto in cui vengono escose le funzionalità di rilevamento e risposta degli endpoint.</span><span class="sxs-lookup"><span data-stu-id="eda13-109">The **Security operations dashboard** is where the endpoint detection and response capabilities are surfaced.</span></span> <span data-ttu-id="eda13-110">Fornisce una panoramica generale della posizione in cui sono stati osservati i rilevamenti ed evidenzia i casi in cui sono necessarie azioni di risposta.</span><span class="sxs-lookup"><span data-stu-id="eda13-110">It provides a high level overview of where detections were seen and highlights where response actions are needed.</span></span> 

<span data-ttu-id="eda13-111">Il dashboard visualizza uno snapshot di:</span><span class="sxs-lookup"><span data-stu-id="eda13-111">The dashboard displays a snapshot of:</span></span>

- <span data-ttu-id="eda13-112">Avvisi attivi</span><span class="sxs-lookup"><span data-stu-id="eda13-112">Active alerts</span></span>
- <span data-ttu-id="eda13-113">Dispositivi a rischio</span><span class="sxs-lookup"><span data-stu-id="eda13-113">Devices at risk</span></span>
- <span data-ttu-id="eda13-114">Integrità del sensore</span><span class="sxs-lookup"><span data-stu-id="eda13-114">Sensor health</span></span>
- <span data-ttu-id="eda13-115">Integrità dei servizi</span><span class="sxs-lookup"><span data-stu-id="eda13-115">Service health</span></span>
- <span data-ttu-id="eda13-116">Report giornalieri sui dispositivi</span><span class="sxs-lookup"><span data-stu-id="eda13-116">Daily devices reporting</span></span>
- <span data-ttu-id="eda13-117">Indagini automatizzate attive</span><span class="sxs-lookup"><span data-stu-id="eda13-117">Active automated investigations</span></span>
- <span data-ttu-id="eda13-118">Statistiche sulle indagini automatizzate</span><span class="sxs-lookup"><span data-stu-id="eda13-118">Automated investigations statistics</span></span>
- <span data-ttu-id="eda13-119">Utenti a rischio</span><span class="sxs-lookup"><span data-stu-id="eda13-119">Users at risk</span></span>
- <span data-ttu-id="eda13-120">Attività sospette</span><span class="sxs-lookup"><span data-stu-id="eda13-120">Suspicious activities</span></span>


![Immagine del dashboard delle operazioni di sicurezza](images/atp-sec-ops-dashboard.png)

<span data-ttu-id="eda13-122">Puoi esplorare e analizzare gli avvisi e i dispositivi per determinare rapidamente se, dove e quando si sono verificate attività sospette nella rete per comprendere il contesto in cui sono apparsi.</span><span class="sxs-lookup"><span data-stu-id="eda13-122">You can explore and investigate alerts and devices to quickly determine if, where, and when suspicious activities occurred in your network to help you understand the context they appeared in.</span></span>

<span data-ttu-id="eda13-123">Dal **dashboard Operazioni di sicurezza** vengono visualizzati eventi aggregati per facilitare l'identificazione di eventi o comportamenti significativi in un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="eda13-123">From the **Security operations dashboard** you will see aggregated events to facilitate the identification of significant events or behaviors on a device.</span></span> <span data-ttu-id="eda13-124">È inoltre possibile eseguire il drill-down in eventi granulari e indicatori di basso livello.</span><span class="sxs-lookup"><span data-stu-id="eda13-124">You can also drill down into granular events and low-level indicators.</span></span>

<span data-ttu-id="eda13-125">Sono inoltre disponibili riquadri selezionabili che forniscono segnali visivi sullo stato di integrità generale dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="eda13-125">It also has clickable tiles that give visual cues on the overall health state of your organization.</span></span> <span data-ttu-id="eda13-126">Ogni riquadro apre una visualizzazione dettagliata della panoramica corrispondente.</span><span class="sxs-lookup"><span data-stu-id="eda13-126">Each tile opens a detailed view of the corresponding overview.</span></span>

## <a name="active-alerts"></a><span data-ttu-id="eda13-127">Avvisi attivi</span><span class="sxs-lookup"><span data-stu-id="eda13-127">Active alerts</span></span>
<span data-ttu-id="eda13-128">Puoi visualizzare il numero complessivo di avvisi attivi degli ultimi 30 giorni nella rete dal riquadro.</span><span class="sxs-lookup"><span data-stu-id="eda13-128">You can view the overall number of active alerts from the last 30 days in your network from the tile.</span></span> <span data-ttu-id="eda13-129">Gli avvisi sono raggruppati in **Nuovo** **e In corso.**</span><span class="sxs-lookup"><span data-stu-id="eda13-129">Alerts are grouped into **New** and **In progress**.</span></span>

![Fare clic su ogni sezione o gravità per visualizzare un elenco di avvisi degli ultimi 30 giorni](images/active-alerts-tile.png)

<span data-ttu-id="eda13-131">Ogni gruppo viene ulteriormente categorizzato nei livelli di gravità degli avvisi corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="eda13-131">Each group is further sub-categorized into their corresponding alert severity levels.</span></span> <span data-ttu-id="eda13-132">Fare clic sul numero di avvisi all'interno di ogni anello di avviso per visualizzare una visualizzazione ordinata della coda della categoria (**Nuovo** o **In corso**).</span><span class="sxs-lookup"><span data-stu-id="eda13-132">Click the number of alerts inside each alert ring to see a sorted view of that category's queue (**New** or **In progress**).</span></span>

<span data-ttu-id="eda13-133">Per ulteriori informazioni, vedere [Panoramica degli avvisi.](alerts-queue.md)</span><span class="sxs-lookup"><span data-stu-id="eda13-133">For more information see, [Alerts overview](alerts-queue.md).</span></span>

<span data-ttu-id="eda13-134">Ogni riga include una categoria di gravità dell'avviso e una breve descrizione dell'avviso.</span><span class="sxs-lookup"><span data-stu-id="eda13-134">Each row includes an alert severity category and a short description of the alert.</span></span> <span data-ttu-id="eda13-135">È possibile fare clic su un avviso per visualizzarne la visualizzazione dettagliata.</span><span class="sxs-lookup"><span data-stu-id="eda13-135">You can click an alert to see its detailed view.</span></span> <span data-ttu-id="eda13-136">Per altre informazioni, vedi Panoramica degli [](alerts-queue.md)avvisi e degli avvisi [di Microsoft Defender for Endpoint.](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="eda13-136">For more information see,  [Investigate Microsoft Defender for Endpoint alerts](investigate-alerts.md) and [Alerts overview](alerts-queue.md).</span></span>


## <a name="devices-at-risk"></a><span data-ttu-id="eda13-137">Dispositivi a rischio</span><span class="sxs-lookup"><span data-stu-id="eda13-137">Devices at risk</span></span>
<span data-ttu-id="eda13-138">Questo riquadro mostra un elenco di dispositivi con il maggior numero di avvisi attivi.</span><span class="sxs-lookup"><span data-stu-id="eda13-138">This tile shows you a list of devices with the highest number of active alerts.</span></span> <span data-ttu-id="eda13-139">Il numero totale di avvisi per ogni dispositivo viene visualizzato in un cerchio accanto al nome del dispositivo e quindi ulteriormente categorizzato in base ai livelli di gravità all'estremità finale del riquadro (passare il mouse su ogni barra di gravità per visualizzare l'etichetta).</span><span class="sxs-lookup"><span data-stu-id="eda13-139">The total number of alerts for each device is shown in a circle next to the device name, and then further categorized by severity levels at the far end of the tile (hover over each severity bar to see its label).</span></span>

![Il riquadro Dispositivi a rischio mostra un elenco di dispositivi con il maggior numero di avvisi e una suddivisione della gravità degli avvisi](images/devices-at-risk-tile.png)

<span data-ttu-id="eda13-141">Fai clic sul nome del dispositivo per visualizzare i dettagli su tale dispositivo.</span><span class="sxs-lookup"><span data-stu-id="eda13-141">Click the name of the device to see details about that device.</span></span> <span data-ttu-id="eda13-142">Per altre informazioni, vedi [Analizzare i dispositivi nell'elenco Microsoft Defender per dispositivi endpoint.](investigate-machines.md)</span><span class="sxs-lookup"><span data-stu-id="eda13-142">For more information see, [Investigate devices in the Microsoft Defender for Endpoint Devices list](investigate-machines.md).</span></span>

<span data-ttu-id="eda13-143">Puoi anche fare clic **su Elenco** dispositivi nella parte superiore del riquadro per passare direttamente all'elenco **Dispositivi,** ordinato in base al numero di avvisi attivi.</span><span class="sxs-lookup"><span data-stu-id="eda13-143">You can also click **Devices list** at the top of the tile to go directly to the **Devices list**, sorted by the number of active alerts.</span></span> <span data-ttu-id="eda13-144">Per altre informazioni, vedi [Analizzare i dispositivi nell'elenco Microsoft Defender per dispositivi endpoint.](investigate-machines.md)</span><span class="sxs-lookup"><span data-stu-id="eda13-144">For more information see, [Investigate devices in the Microsoft Defender for Endpoint Devices list](investigate-machines.md).</span></span>

## <a name="devices-with-sensor-issues"></a><span data-ttu-id="eda13-145">Dispositivi con problemi di sensore</span><span class="sxs-lookup"><span data-stu-id="eda13-145">Devices with sensor issues</span></span>
<span data-ttu-id="eda13-146">Il **riquadro Dispositivi con problemi del** sensore fornisce informazioni sulla capacità del singolo dispositivo di fornire dati del sensore al servizio Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="eda13-146">The **Devices with sensor issues** tile provides information on the individual device’s ability to provide sensor data to the Microsoft Defender for Endpoint service.</span></span> <span data-ttu-id="eda13-147">Segnala il numero di dispositivi che richiedono attenzione e ti aiuta a identificare i dispositivi problematici.</span><span class="sxs-lookup"><span data-stu-id="eda13-147">It reports how many devices require attention and helps you identify problematic devices.</span></span>

![Riquadro Dispositivi con problemi di sensore](images/atp-tile-sensor-health.png)

<span data-ttu-id="eda13-149">Esistono due indicatori di stato che forniscono informazioni sul numero di dispositivi che non segnalano correttamente al servizio:</span><span class="sxs-lookup"><span data-stu-id="eda13-149">There are two status indicators that provide information on the number of devices that are not reporting properly to the service:</span></span>
- <span data-ttu-id="eda13-150">**Configurazione errata:** questi dispositivi potrebbero segnalare parzialmente i dati del sensore al servizio Microsoft Defender for Endpoint e potrebbero avere errori di configurazione che devono essere corretti.</span><span class="sxs-lookup"><span data-stu-id="eda13-150">**Misconfigured** – These devices might partially be reporting sensor data to the Microsoft Defender for Endpoint service and might have configuration errors that need to be corrected.</span></span>
- <span data-ttu-id="eda13-151">**Inattivo:** dispositivi che hanno interrotto la segnalazione al servizio Microsoft Defender for Endpoint per più di sette giorni nell'ultimo mese.</span><span class="sxs-lookup"><span data-stu-id="eda13-151">**Inactive** - Devices that have stopped reporting to the Microsoft Defender for Endpoint service for more than seven days in the past month.</span></span>

<span data-ttu-id="eda13-152">Quando fai clic su uno dei gruppi, sarai indirizzato all'elenco dei dispositivi, filtrato in base alla tua scelta.</span><span class="sxs-lookup"><span data-stu-id="eda13-152">When you click any of the groups, you’ll be directed to devices list, filtered according to your choice.</span></span> <span data-ttu-id="eda13-153">Per altre informazioni, vedi [Controllare lo stato del sensore](check-sensor-status.md) e Analizzare i [dispositivi.](investigate-machines.md)</span><span class="sxs-lookup"><span data-stu-id="eda13-153">For more information, see [Check sensor state](check-sensor-status.md) and [Investigate devices](investigate-machines.md).</span></span>

## <a name="service-health"></a><span data-ttu-id="eda13-154">Integrità dei servizi</span><span class="sxs-lookup"><span data-stu-id="eda13-154">Service health</span></span>
<span data-ttu-id="eda13-155">Il **riquadro Integrità** servizio informa l'utente se il servizio è attivo o se si verificano problemi.</span><span class="sxs-lookup"><span data-stu-id="eda13-155">The **Service health** tile informs you if the service is active or if there are issues.</span></span>

![Il riquadro Integrità servizio mostra un indicatore generale del servizio](images/status-tile.png)

<span data-ttu-id="eda13-157">Per altre informazioni sull'integrità del servizio, vedi [Controllare l'integrità del](service-status.md)servizio Endpoint in Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="eda13-157">For more information on the service health, see [Check the Microsoft Defender for Endpoint service health](service-status.md).</span></span>


## <a name="daily-devices-reporting"></a><span data-ttu-id="eda13-158">Report giornalieri sui dispositivi</span><span class="sxs-lookup"><span data-stu-id="eda13-158">Daily devices reporting</span></span>
<span data-ttu-id="eda13-159">Il **riquadro Report dispositivi giornalieri** mostra un grafico a barre che rappresenta il numero di dispositivi che segnalano ogni giorno negli ultimi 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="eda13-159">The **Daily devices reporting** tile shows a bar graph that represents the number of devices reporting daily in the last 30 days.</span></span> <span data-ttu-id="eda13-160">Posizionare il puntatore del mouse sulle singole barre del grafico per visualizzare il numero esatto di report dei dispositivi in ogni giorno.</span><span class="sxs-lookup"><span data-stu-id="eda13-160">Hover over individual bars on the graph to see the exact number of devices reporting in each day.</span></span>

![Immagine del riquadro dei report dei dispositivi giornalieri](images/atp-daily-devices-reporting.png)


## <a name="active-automated-investigations"></a><span data-ttu-id="eda13-162">Indagini automatizzate attive</span><span class="sxs-lookup"><span data-stu-id="eda13-162">Active automated investigations</span></span>
<span data-ttu-id="eda13-163">Puoi visualizzare il numero complessivo di indagini automatizzate degli ultimi 30 giorni nella rete dal riquadro **Indagini automatizzate** attive.</span><span class="sxs-lookup"><span data-stu-id="eda13-163">You can view the overall number of automated investigations from the last 30 days in your network from the **Active automated investigations** tile.</span></span> <span data-ttu-id="eda13-164">Le indagini sono raggruppate in **Azione in sospeso,** **In attesa del dispositivo** e In **esecuzione.**</span><span class="sxs-lookup"><span data-stu-id="eda13-164">Investigations are grouped into **Pending action**, **Waiting for device**, and **Running**.</span></span>

![Inmage of active automated investigations](images/atp-active-investigations-tile.png)


## <a name="automated-investigations-statistics"></a><span data-ttu-id="eda13-166">Statistiche sulle indagini automatizzate</span><span class="sxs-lookup"><span data-stu-id="eda13-166">Automated investigations statistics</span></span>
<span data-ttu-id="eda13-167">Questo riquadro mostra le statistiche relative alle indagini automatizzate negli ultimi sette giorni.</span><span class="sxs-lookup"><span data-stu-id="eda13-167">This tile shows statistics related to automated investigations in the last seven days.</span></span> <span data-ttu-id="eda13-168">Mostra il numero di indagini completate, il numero di indagini correttive, il tempo medio in sospeso necessario per l'avvio di un'indagine, il tempo medio necessario per correggere un avviso, il numero di avvisi esaminati e il numero di ore di automazione salvate da un'indagine manuale tipica.</span><span class="sxs-lookup"><span data-stu-id="eda13-168">It shows the number of investigations completed, the number of successfully remediated investigations, the average pending time it takes for an investigation to be initiated, the average time it takes to remediate an alert, the number of alerts investigated, and the number of hours of automation saved from a typical manual investigation.</span></span> 

![Immagine delle statistiche sulle indagini automatizzate](images/atp-automated-investigations-statistics.png)

<span data-ttu-id="eda13-170">È possibile fare clic **su** Indagini automatizzate,  Indagini correttive e  Avvisi esaminati per passare alla pagina Indagini, filtrata in base alla categoria appropriata. </span><span class="sxs-lookup"><span data-stu-id="eda13-170">You can click on **Automated investigations**, **Remediated investigations**, and **Alerts investigated** to navigate to the **Investigations** page, filtered by the appropriate category.</span></span> <span data-ttu-id="eda13-171">In questo modo è possibile visualizzare una suddivisione dettagliata delle indagini nel contesto.</span><span class="sxs-lookup"><span data-stu-id="eda13-171">This lets you see a detailed breakdown of investigations in context.</span></span>

## <a name="users-at-risk"></a><span data-ttu-id="eda13-172">Utenti a rischio</span><span class="sxs-lookup"><span data-stu-id="eda13-172">Users at risk</span></span>
<span data-ttu-id="eda13-173">Il riquadro mostra un elenco di account utente con gli avvisi più attivi e il numero di avvisi visualizzati in avvisi alti, medi o bassi.</span><span class="sxs-lookup"><span data-stu-id="eda13-173">The tile shows you a list of user accounts with the most active alerts and the number of alerts seen on high, medium, or low alerts.</span></span> 

![Riquadro Account utente a rischio mostra un elenco di account utente con il maggior numero di avvisi e una suddivisione della gravità degli avvisi](images/atp-users-at-risk.png)

<span data-ttu-id="eda13-175">Fare clic sull'account utente per visualizzare i dettagli sull'account utente.</span><span class="sxs-lookup"><span data-stu-id="eda13-175">Click the user account to see details about the user account.</span></span> <span data-ttu-id="eda13-176">Per ulteriori informazioni, vedere [Investigate a user account](investigate-user.md).</span><span class="sxs-lookup"><span data-stu-id="eda13-176">For more information see [Investigate a user account](investigate-user.md).</span></span>

><span data-ttu-id="eda13-177">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="eda13-177">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="eda13-178">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="eda13-178">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-secopsdashboard-belowfoldlink)

## <a name="related-topics"></a><span data-ttu-id="eda13-179">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="eda13-179">Related topics</span></span>
- [<span data-ttu-id="eda13-180">Informazioni sul portale di Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="eda13-180">Understand the Microsoft Defender for Endpoint portal</span></span>](use.md)
- [<span data-ttu-id="eda13-181">Panoramica del portale</span><span class="sxs-lookup"><span data-stu-id="eda13-181">Portal overview</span></span>](portal-overview.md)
- [<span data-ttu-id="eda13-182">Visualizzare il dashboard di gestione delle & delle minacce</span><span class="sxs-lookup"><span data-stu-id="eda13-182">View the Threat & Vulnerability Management dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="eda13-183">Visualizzare il dashboard di analisi delle minacce ed eseguire le azioni di mitigazione consigliate</span><span class="sxs-lookup"><span data-stu-id="eda13-183">View the Threat analytics dashboard and take recommended mitigation actions</span></span>](threat-analytics.md)
