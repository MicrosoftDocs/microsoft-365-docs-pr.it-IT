---
title: Analizzare i dispositivi nell'elenco Defender for Endpoint Defender ATP Devices
description: Analizzare i dispositivi interessati esaminando avvisi, informazioni sulla connessione di rete, aggiungendo tag e gruppi di dispositivi e controllando l'integrità del servizio.
keywords: dispositivi, tag, gruppi, endpoint, coda avvisi, avvisi, nome del dispositivo, dominio, ultimo visto, IP interno, avvisi attivi, categoria di minacce, filtro, ordinamento, esaminare avvisi, rete, connessione, tipo, furto di password, ransomware, exploit, minaccia, bassa gravità, integrità del servizio
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
ms.openlocfilehash: 8873177f13ebe8d60533877fa9b8dc0be96a66f9
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51066941"
---
# <a name="investigate-devices-in-the-microsoft-defender-for-endpoint-devices-list"></a><span data-ttu-id="021de-104">Analizzare i dispositivi nell'elenco Di Microsoft Defender per dispositivi endpoint</span><span class="sxs-lookup"><span data-stu-id="021de-104">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="021de-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="021de-105">**Applies to:**</span></span>
- [<span data-ttu-id="021de-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="021de-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="021de-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="021de-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="021de-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="021de-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="021de-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="021de-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatemachines-abovefoldlink)

<span data-ttu-id="021de-110">Analizzare i dettagli di un avviso generato su un dispositivo specifico per identificare altri comportamenti o eventi che potrebbero essere correlati all'avviso o all'ambito potenziale della violazione.</span><span class="sxs-lookup"><span data-stu-id="021de-110">Investigate the details of an alert raised on a specific device to identify other behaviors or events that might be related to the alert or the potential scope of the breach.</span></span>

> [!NOTE]
> <span data-ttu-id="021de-111">Come parte del processo di indagine o di risposta, puoi raccogliere un pacchetto di indagine da un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="021de-111">As part of the investigation or response process, you can collect an investigation package from a device.</span></span> <span data-ttu-id="021de-112">Ecco come: Raccogliere [il pacchetto di indagine dai dispositivi](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/respond-machine-alerts#collect-investigation-package-from-devices).</span><span class="sxs-lookup"><span data-stu-id="021de-112">Here's how: [Collect investigation package from devices](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/respond-machine-alerts#collect-investigation-package-from-devices).</span></span>

<span data-ttu-id="021de-113">Puoi fare clic sui dispositivi interessati ogni volta che li vedi nel portale per aprire un report dettagliato su tale dispositivo.</span><span class="sxs-lookup"><span data-stu-id="021de-113">You can click on affected devices whenever you see them in the portal to open a detailed report about that device.</span></span> <span data-ttu-id="021de-114">I dispositivi interessati sono identificati nelle aree seguenti:</span><span class="sxs-lookup"><span data-stu-id="021de-114">Affected devices are identified in the following areas:</span></span>

- [<span data-ttu-id="021de-115">Elenco dispositivi</span><span class="sxs-lookup"><span data-stu-id="021de-115">Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="021de-116">Coda avvisi</span><span class="sxs-lookup"><span data-stu-id="021de-116">Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="021de-117">Dashboard delle operazioni di sicurezza</span><span class="sxs-lookup"><span data-stu-id="021de-117">Security operations dashboard</span></span>](security-operations-dashboard.md)
- <span data-ttu-id="021de-118">Qualsiasi singolo avviso</span><span class="sxs-lookup"><span data-stu-id="021de-118">Any individual alert</span></span>
- <span data-ttu-id="021de-119">Qualsiasi visualizzazione dei dettagli dei singoli file</span><span class="sxs-lookup"><span data-stu-id="021de-119">Any individual file details view</span></span>
- <span data-ttu-id="021de-120">Qualsiasi indirizzo IP o visualizzazione dei dettagli del dominio</span><span class="sxs-lookup"><span data-stu-id="021de-120">Any IP address or domain details view</span></span>

<span data-ttu-id="021de-121">Quando indaghi su un dispositivo specifico, vedrai:</span><span class="sxs-lookup"><span data-stu-id="021de-121">When you investigate a specific device, you'll see:</span></span>

- <span data-ttu-id="021de-122">Dettagli dispositivo</span><span class="sxs-lookup"><span data-stu-id="021de-122">Device details</span></span>
- <span data-ttu-id="021de-123">Azioni di risposta</span><span class="sxs-lookup"><span data-stu-id="021de-123">Response actions</span></span>
- <span data-ttu-id="021de-124">Schede (panoramica, avvisi, sequenza temporale, suggerimenti per la sicurezza, inventario software, vulnerabilità individuate, INDICATORI KPI mancanti)</span><span class="sxs-lookup"><span data-stu-id="021de-124">Tabs (overview, alerts, timeline, security recommendations, software inventory, discovered vulnerabilities, missing KBs)</span></span>
- <span data-ttu-id="021de-125">Schede (avvisi attivi, utenti connessi, valutazione della sicurezza)</span><span class="sxs-lookup"><span data-stu-id="021de-125">Cards (active alerts, logged on users, security assessment)</span></span>

![Immagine della visualizzazione del dispositivo](images/specific-device.png)

## <a name="device-details"></a><span data-ttu-id="021de-127">Dettagli dispositivo</span><span class="sxs-lookup"><span data-stu-id="021de-127">Device details</span></span>

<span data-ttu-id="021de-128">La sezione dettagli dispositivo fornisce informazioni quali il dominio, il sistema operativo e lo stato di integrità del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="021de-128">The device details section provides information such as the domain, OS, and health state of the device.</span></span> <span data-ttu-id="021de-129">Se nel dispositivo è disponibile un pacchetto di analisi, vedrai un collegamento che ti consente di scaricare il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="021de-129">If there's an investigation package available on the device, you'll see a link that allows you to download the package.</span></span>

## <a name="response-actions"></a><span data-ttu-id="021de-130">Azioni di risposta</span><span class="sxs-lookup"><span data-stu-id="021de-130">Response actions</span></span>

<span data-ttu-id="021de-131">Le azioni di risposta vengono eseguite nella parte superiore di una pagina specifica del dispositivo e includono:</span><span class="sxs-lookup"><span data-stu-id="021de-131">Response actions run along the top of a specific device page and include:</span></span>

- <span data-ttu-id="021de-132">Gestire i tag</span><span class="sxs-lookup"><span data-stu-id="021de-132">Manage tags</span></span>
- <span data-ttu-id="021de-133">Isola dispositivo</span><span class="sxs-lookup"><span data-stu-id="021de-133">Isolate device</span></span>
- <span data-ttu-id="021de-134">Limitare l'esecuzione delle app</span><span class="sxs-lookup"><span data-stu-id="021de-134">Restrict app execution</span></span>
- <span data-ttu-id="021de-135">Eseguire l'analisi antivirus</span><span class="sxs-lookup"><span data-stu-id="021de-135">Run antivirus scan</span></span>
- <span data-ttu-id="021de-136">Raccogliere il pacchetto di analisi</span><span class="sxs-lookup"><span data-stu-id="021de-136">Collect investigation package</span></span>
- <span data-ttu-id="021de-137">Avviare la sessione di risposta in tempo reale</span><span class="sxs-lookup"><span data-stu-id="021de-137">Initiate Live Response Session</span></span>
- <span data-ttu-id="021de-138">Avviare un'indagine automatizzata</span><span class="sxs-lookup"><span data-stu-id="021de-138">Initiate automated investigation</span></span>
- <span data-ttu-id="021de-139">Consultare un esperto di minacce</span><span class="sxs-lookup"><span data-stu-id="021de-139">Consult a threat expert</span></span>
- <span data-ttu-id="021de-140">Centro notifiche</span><span class="sxs-lookup"><span data-stu-id="021de-140">Action center</span></span>

<span data-ttu-id="021de-141">Puoi eseguire azioni di risposta nel centro notifiche, in una pagina del dispositivo specifico o in una pagina di file specifica.</span><span class="sxs-lookup"><span data-stu-id="021de-141">You can take response actions in the Action center, in a specific device page, or in a specific file page.</span></span>

<span data-ttu-id="021de-142">Per altre informazioni su come eseguire un'azione su un dispositivo, vedi [Eseguire un'azione di risposta in un dispositivo.](respond-machine-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="021de-142">For more information on how to take action on a device, see [Take response action on a device](respond-machine-alerts.md).</span></span>

<span data-ttu-id="021de-143">Per ulteriori informazioni, vedere [Investigate user entities](investigate-user.md).</span><span class="sxs-lookup"><span data-stu-id="021de-143">For more information, see [Investigate user entities](investigate-user.md).</span></span>

## <a name="tabs"></a><span data-ttu-id="021de-144">Schede</span><span class="sxs-lookup"><span data-stu-id="021de-144">Tabs</span></span>

<span data-ttu-id="021de-145">Le schede forniscono informazioni rilevanti sulla sicurezza e sulla prevenzione delle minacce relative al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="021de-145">The tabs provide relevant security and threat prevention information related to the device.</span></span> <span data-ttu-id="021de-146">In ogni scheda è possibile personalizzare le  colonne visualizzate selezionando Personalizza colonne dalla barra sopra le intestazioni di colonna.</span><span class="sxs-lookup"><span data-stu-id="021de-146">In each tab, you can customize the columns that are shown by selecting **Customize columns** from the bar above the column headers.</span></span>

### <a name="overview"></a><span data-ttu-id="021de-147">Panoramica</span><span class="sxs-lookup"><span data-stu-id="021de-147">Overview</span></span>
<span data-ttu-id="021de-148">Nella **scheda Panoramica** vengono visualizzate le [schede](#cards) per gli avvisi attivi, gli utenti connessi e la valutazione della sicurezza.</span><span class="sxs-lookup"><span data-stu-id="021de-148">The **Overview** tab displays the [cards](#cards) for active alerts, logged on users, and security assessment.</span></span>

![Immagine della scheda Panoramica nella pagina del dispositivo](images/overview-device.png)

### <a name="alerts"></a><span data-ttu-id="021de-150">Avvisi</span><span class="sxs-lookup"><span data-stu-id="021de-150">Alerts</span></span>

<span data-ttu-id="021de-151">La **scheda** Avvisi fornisce un elenco di avvisi associati al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="021de-151">The **Alerts** tab provides a list of alerts that are associated with the device.</span></span> <span data-ttu-id="021de-152">Questo elenco è una versione [](alerts-queue.md)filtrata della coda avvisi e mostra una breve descrizione dell'avviso, della gravità (alto, medio, basso, informativo), dello stato nella coda (nuovo, in corso, risolto), classificazione (non impostato, falso avviso, avviso vero), stato dell'indagine, categoria dell'avviso, destinatario dell'avviso e ultima attività.</span><span class="sxs-lookup"><span data-stu-id="021de-152">This list is a filtered version of the [Alerts queue](alerts-queue.md), and shows a short description of the alert, severity (high, medium, low, informational), status in the queue (new, in progress, resolved), classification (not set, false alert, true alert), investigation state, category of alert, who is addressing the alert, and last activity.</span></span> <span data-ttu-id="021de-153">È inoltre possibile filtrare gli avvisi.</span><span class="sxs-lookup"><span data-stu-id="021de-153">You can also filter the alerts.</span></span>

![Immagine degli avvisi correlati al dispositivo](images/alerts-device.png)

<span data-ttu-id="021de-155">Quando l'icona del cerchio a sinistra di un avviso è selezionata, viene visualizzato un riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="021de-155">When the circle icon to the left of an alert is selected, a fly-out appears.</span></span> <span data-ttu-id="021de-156">Da questo pannello puoi gestire l'avviso e visualizzare altri dettagli, ad esempio il numero di incidente e i dispositivi correlati.</span><span class="sxs-lookup"><span data-stu-id="021de-156">From this panel you can manage the alert and view more details such as incident number and related devices.</span></span> <span data-ttu-id="021de-157">È possibile selezionare più avvisi alla volta.</span><span class="sxs-lookup"><span data-stu-id="021de-157">Multiple alerts can be selected at a time.</span></span>

<span data-ttu-id="021de-158">Per visualizzare una visualizzazione a pagina intera di un avviso, incluso il grafico degli eventi imprevisti e l'albero dei processi, selezionare il titolo dell'avviso.</span><span class="sxs-lookup"><span data-stu-id="021de-158">To see a full page view of an alert including incident graph and process tree, select the title of the alert.</span></span>

### <a name="timeline"></a><span data-ttu-id="021de-159">Sequenza temporale</span><span class="sxs-lookup"><span data-stu-id="021de-159">Timeline</span></span>

<span data-ttu-id="021de-160">La **scheda** Sequenza temporale fornisce una visualizzazione cronologica degli eventi e degli avvisi associati che sono stati osservati nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="021de-160">The **Timeline** tab provides a chronological view of the events and associated alerts that have been observed on the device.</span></span> <span data-ttu-id="021de-161">In questo modo puoi correlare eventi, file e indirizzi IP in relazione al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="021de-161">This can help you correlate any events, files, and IP addresses in relation to the device.</span></span>

<span data-ttu-id="021de-162">La sequenza temporale consente inoltre di eseguire il drill-down in modo selettivo negli eventi che si sono verificati in un determinato periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="021de-162">The timeline also enables you to selectively drill down into events that occurred within a given time period.</span></span> <span data-ttu-id="021de-163">Puoi visualizzare la sequenza temporale degli eventi che si sono verificati in un dispositivo in un periodo di tempo selezionato.</span><span class="sxs-lookup"><span data-stu-id="021de-163">You can view the temporal sequence of events that occurred on a device over a selected time period.</span></span> <span data-ttu-id="021de-164">Per controllare ulteriormente la visualizzazione, è possibile filtrare in base ai gruppi di eventi o personalizzare le colonne.</span><span class="sxs-lookup"><span data-stu-id="021de-164">To further control your view, you can filter by event groups or customize the columns.</span></span>

>[!NOTE]
> <span data-ttu-id="021de-165">Per visualizzare gli eventi del firewall, è necessario abilitare il criterio di controllo, vedere [Audit Filtering Platform connection.](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-filtering-platform-connection)</span><span class="sxs-lookup"><span data-stu-id="021de-165">For firewall events to be displayed, you'll need to enable the audit policy, see [Audit Filtering Platform connection](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-filtering-platform-connection).</span></span>
><span data-ttu-id="021de-166">Il firewall copre gli eventi seguenti</span><span class="sxs-lookup"><span data-stu-id="021de-166">Firewall covers the following events</span></span>
>
>- <span data-ttu-id="021de-167">[5025](https://docs.microsoft.com/windows/security/threat-protection/auditing/event-5025) - Servizio firewall arrestato</span><span class="sxs-lookup"><span data-stu-id="021de-167">[5025](https://docs.microsoft.com/windows/security/threat-protection/auditing/event-5025) - firewall service stopped</span></span>
>- <span data-ttu-id="021de-168">[5031](https://docs.microsoft.com/windows/security/threat-protection/auditing/event-5031) - Applicazione bloccata dall'accettazione delle connessioni in ingresso sulla rete</span><span class="sxs-lookup"><span data-stu-id="021de-168">[5031](https://docs.microsoft.com/windows/security/threat-protection/auditing/event-5031) - application blocked from accepting incoming connections on the network</span></span>
>- <span data-ttu-id="021de-169">[5157](https://docs.microsoft.com/windows/security/threat-protection/auditing/event-5157) - Connessione bloccata</span><span class="sxs-lookup"><span data-stu-id="021de-169">[5157](https://docs.microsoft.com/windows/security/threat-protection/auditing/event-5157) - blocked connection</span></span>

![Immagine della sequenza temporale del dispositivo con eventi](images/timeline-device.png)

<span data-ttu-id="021de-171">Alcune delle funzionalità includono:</span><span class="sxs-lookup"><span data-stu-id="021de-171">Some of the functionality includes:</span></span>

- <span data-ttu-id="021de-172">Cercare eventi specifici</span><span class="sxs-lookup"><span data-stu-id="021de-172">Search for specific events</span></span>
  - <span data-ttu-id="021de-173">Usa la barra di ricerca per cercare eventi sequenza temporale specifici.</span><span class="sxs-lookup"><span data-stu-id="021de-173">Use the search bar to look for specific timeline events.</span></span>
- <span data-ttu-id="021de-174">Filtrare gli eventi da una data specifica</span><span class="sxs-lookup"><span data-stu-id="021de-174">Filter events from a specific date</span></span>
  - <span data-ttu-id="021de-175">Selezionare l'icona del calendario in alto a sinistra della tabella per visualizzare gli eventi dell'ultimo giorno, settimana, 30 giorni o intervallo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="021de-175">Select the calendar icon in the upper left of the table to display events in the past day, week, 30 days, or custom range.</span></span> <span data-ttu-id="021de-176">Per impostazione predefinita, la sequenza temporale del dispositivo è impostata per visualizzare gli eventi degli ultimi 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="021de-176">By default, the device timeline is set to display the events from the past 30 days.</span></span>
  - <span data-ttu-id="021de-177">Usa la sequenza temporale per passare a un momento specifico evidenziando la sezione.</span><span class="sxs-lookup"><span data-stu-id="021de-177">Use the timeline to jump to a specific moment in time by highlighting the section.</span></span> <span data-ttu-id="021de-178">Le frecce sulla sequenza temporale consentono di individuare indagini automatizzate</span><span class="sxs-lookup"><span data-stu-id="021de-178">The arrows on the timeline pinpoint automated investigations</span></span>
- <span data-ttu-id="021de-179">Esportare eventi dettagliati della sequenza temporale del dispositivo</span><span class="sxs-lookup"><span data-stu-id="021de-179">Export detailed device timeline events</span></span>
  - <span data-ttu-id="021de-180">Esporta la sequenza temporale del dispositivo per la data corrente o un intervallo di date specificato fino a sette giorni.</span><span class="sxs-lookup"><span data-stu-id="021de-180">Export the device timeline for the current date or a specified date range up to seven days.</span></span>

<span data-ttu-id="021de-181">Ulteriori dettagli su determinati eventi sono disponibili nella **sezione Informazioni** aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="021de-181">More details about certain events are provided in the **Additional information** section.</span></span> <span data-ttu-id="021de-182">Questi dettagli variano a seconda del tipo di evento, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="021de-182">These details vary depending on the type of event, for example:</span></span> 

- <span data-ttu-id="021de-183">Contenuto di Application Guard: l'evento del Web browser è stato limitato da un contenitore isolato</span><span class="sxs-lookup"><span data-stu-id="021de-183">Contained by Application Guard - the web browser event was restricted by an isolated container</span></span>
- <span data-ttu-id="021de-184">Minaccia attiva rilevata: il rilevamento delle minacce si è verificato durante l'esecuzione della minaccia</span><span class="sxs-lookup"><span data-stu-id="021de-184">Active threat detected - the threat detection occurred while the threat was running</span></span>
- <span data-ttu-id="021de-185">Correzione non riuscita: un tentativo di correzione della minaccia rilevata è stato richiamato ma non è riuscito</span><span class="sxs-lookup"><span data-stu-id="021de-185">Remediation unsuccessful - an attempt to remediate the detected threat was invoked but failed</span></span>
- <span data-ttu-id="021de-186">Correzione riuscita: la minaccia rilevata è stata arrestata e pulita</span><span class="sxs-lookup"><span data-stu-id="021de-186">Remediation successful - the detected threat was stopped and cleaned</span></span>
- <span data-ttu-id="021de-187">Avviso ignorato dall'utente: l'Windows Defender SmartScreen è stato ignorato e sostituito da un utente</span><span class="sxs-lookup"><span data-stu-id="021de-187">Warning bypassed by user - the Windows Defender SmartScreen warning was dismissed and overridden by a user</span></span>
- <span data-ttu-id="021de-188">Rilevato script sospetto: è stato rilevato uno script potenzialmente dannoso in esecuzione</span><span class="sxs-lookup"><span data-stu-id="021de-188">Suspicious script detected - a potentially malicious script was found running</span></span>
- <span data-ttu-id="021de-189">Categoria di avviso: se l'evento ha generato un avviso, viene fornita la categoria di avviso ("Movimento laterale", ad esempio)</span><span class="sxs-lookup"><span data-stu-id="021de-189">The alert category - if the event led to the generation of an alert, the alert category  ("Lateral Movement", for example) is provided</span></span>

#### <a name="event-details"></a><span data-ttu-id="021de-190">Dettagli evento</span><span class="sxs-lookup"><span data-stu-id="021de-190">Event details</span></span>
<span data-ttu-id="021de-191">Seleziona un evento per visualizzare i dettagli pertinenti su tale evento.</span><span class="sxs-lookup"><span data-stu-id="021de-191">Select an event to view relevant details about that event.</span></span> <span data-ttu-id="021de-192">Viene visualizzato un pannello per visualizzare informazioni generali sull'evento.</span><span class="sxs-lookup"><span data-stu-id="021de-192">A panel displays to show general event information.</span></span> <span data-ttu-id="021de-193">Se applicabile e i dati sono disponibili, viene visualizzato anche un grafico che mostra le entità correlate e le relative relazioni.</span><span class="sxs-lookup"><span data-stu-id="021de-193">When applicable and data is available, a graph showing related entities and their relationships are also shown.</span></span>

<span data-ttu-id="021de-194">Per esaminare ulteriormente l'evento e gli eventi correlati, è possibile eseguire rapidamente una [query](advanced-hunting-overview.md) di ricerca avanzata selezionando Cerca **eventi correlati.**</span><span class="sxs-lookup"><span data-stu-id="021de-194">To further inspect the event and related events, you can quickly run an [advanced hunting](advanced-hunting-overview.md) query by selecting **Hunt for related events**.</span></span> <span data-ttu-id="021de-195">La query restituirà l'evento selezionato e l'elenco di altri eventi che si sono verificati nello stesso momento nello stesso endpoint.</span><span class="sxs-lookup"><span data-stu-id="021de-195">The query will return the selected event and the list of other events that occurred around the same time on the same endpoint.</span></span>

![Immagine del pannello dei dettagli dell'evento](images/event-details.png)

### <a name="security-recommendations"></a><span data-ttu-id="021de-197">Consigli sulla sicurezza</span><span class="sxs-lookup"><span data-stu-id="021de-197">Security recommendations</span></span>

<span data-ttu-id="021de-198">**I suggerimenti per** la sicurezza vengono generati da Microsoft Defender per la funzionalità di gestione delle [& delle](tvm-dashboard-insights.md) vulnerabilità di Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="021de-198">**Security recommendations** are generated from Microsoft Defender for Endpoint's [Threat & Vulnerability Management](tvm-dashboard-insights.md) capability.</span></span> <span data-ttu-id="021de-199">La selezione di un suggerimento mostrerà un pannello in cui è possibile visualizzare dettagli pertinenti, ad esempio la descrizione del suggerimento e i potenziali rischi associati alla sua non applicazione.</span><span class="sxs-lookup"><span data-stu-id="021de-199">Selecting a recommendation will show a panel where you can view relevant details such as description of the recommendation and the potential risks associated with not enacting it.</span></span> <span data-ttu-id="021de-200">Per [informazioni dettagliate, vedere](tvm-security-recommendation.md) Consigli per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="021de-200">See [Security recommendation](tvm-security-recommendation.md) for details.</span></span>

![Immagine della scheda Suggerimenti per la sicurezza](images/security-recommendations-device.png)

### <a name="software-inventory"></a><span data-ttu-id="021de-202">Inventario software</span><span class="sxs-lookup"><span data-stu-id="021de-202">Software inventory</span></span>

<span data-ttu-id="021de-203">La **scheda Inventario** software consente di visualizzare il software nel dispositivo, insieme a eventuali punti deboli o minacce.</span><span class="sxs-lookup"><span data-stu-id="021de-203">The **Software inventory** tab lets you view software on the device, along with any weaknesses or threats.</span></span> <span data-ttu-id="021de-204">Se si seleziona il nome del software, verrà visualizzata la pagina dei dettagli del software in cui è possibile visualizzare i suggerimenti per la sicurezza, le vulnerabilità individuate, i dispositivi installati e la distribuzione delle versioni.</span><span class="sxs-lookup"><span data-stu-id="021de-204">Selecting the name of the software will take you to the software details page where you can view security recommendations, discovered vulnerabilities, installed devices, and version distribution.</span></span> <span data-ttu-id="021de-205">Per [informazioni dettagliate, vedere Inventario](tvm-software-inventory.md) software</span><span class="sxs-lookup"><span data-stu-id="021de-205">See [Software inventory](tvm-software-inventory.md) for details</span></span>

![Immagine della scheda inventario software](images/software-inventory-device.png)

### <a name="discovered-vulnerabilities"></a><span data-ttu-id="021de-207">Vulnerabilità individuate</span><span class="sxs-lookup"><span data-stu-id="021de-207">Discovered vulnerabilities</span></span>

<span data-ttu-id="021de-208">La **scheda Vulnerabilità individuate** mostra il nome, la gravità e le informazioni dettagliate sulle minacce delle vulnerabilità individuate nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="021de-208">The **Discovered vulnerabilities** tab shows the name, severity, and threat insights of discovered vulnerabilities on the device.</span></span> <span data-ttu-id="021de-209">La selezione di vulnerabilità specifiche mostrerà una descrizione e dettagli.</span><span class="sxs-lookup"><span data-stu-id="021de-209">Selecting specific vulnerabilities will show a description and details.</span></span>

![Immagine della scheda vulnerabilità individuate](images/discovered-vulnerabilities-device.png)

### <a name="missing-kbs"></a><span data-ttu-id="021de-211">Indicatori KPI mancanti</span><span class="sxs-lookup"><span data-stu-id="021de-211">Missing KBs</span></span>
<span data-ttu-id="021de-212">Nella **scheda Blob** mancanti sono elencati gli aggiornamenti di sicurezza mancanti per il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="021de-212">The **Missing KBs** tab lists the missing security updates for the device.</span></span>

![Immagine della scheda kb mancanti](images/missing-kbs-device.png)

## <a name="cards"></a><span data-ttu-id="021de-214">Schede</span><span class="sxs-lookup"><span data-stu-id="021de-214">Cards</span></span>

### <a name="active-alerts"></a><span data-ttu-id="021de-215">Avvisi attivi</span><span class="sxs-lookup"><span data-stu-id="021de-215">Active alerts</span></span>

<span data-ttu-id="021de-216">La **scheda Azure Advanced Threat Protection** visualizza una panoramica generale degli avvisi relativi al dispositivo e al relativo livello di rischio, se è stata abilitata la funzionalità Azure ATP e sono presenti avvisi attivi.</span><span class="sxs-lookup"><span data-stu-id="021de-216">The **Azure Advanced Threat Protection** card will display a high-level overview of alerts related to the device and their risk level, if you have enabled the Azure ATP feature, and there are any active alerts.</span></span> <span data-ttu-id="021de-217">Ulteriori informazioni sono disponibili nel drill-down "Avvisi".</span><span class="sxs-lookup"><span data-stu-id="021de-217">More information is available in the "Alerts" drill down.</span></span>

![Immagine della scheda avvisi attivi](images/risk-level-small.png)

>[!NOTE]
><span data-ttu-id="021de-219">Dovrai abilitare l'integrazione sia in Azure ATP che in Defender for Endpoint per usare questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="021de-219">You'll need to enable the integration on both Azure ATP and Defender for Endpoint to use this feature.</span></span> <span data-ttu-id="021de-220">In Defender for Endpoint puoi abilitare questa funzionalità nelle funzionalità avanzate.</span><span class="sxs-lookup"><span data-stu-id="021de-220">In Defender for Endpoint, you can enable this feature in advanced features.</span></span> <span data-ttu-id="021de-221">Per ulteriori informazioni su come abilitare le funzionalità avanzate, vedere [Attivare le funzionalità avanzate.](advanced-features.md)</span><span class="sxs-lookup"><span data-stu-id="021de-221">For more information on how to enable advanced features, see [Turn on advanced features](advanced-features.md).</span></span>

### <a name="logged-on-users"></a><span data-ttu-id="021de-222">Utenti connessi</span><span class="sxs-lookup"><span data-stu-id="021de-222">Logged on users</span></span>

<span data-ttu-id="021de-223">La **scheda Utenti connessi** mostra quanti utenti hanno effettuato l'accesso negli ultimi 30 giorni, insieme agli utenti più e meno frequenti.</span><span class="sxs-lookup"><span data-stu-id="021de-223">The **Logged on users** card shows how many users have logged on in the past 30 days, along with the most and least frequent users.</span></span> <span data-ttu-id="021de-224">Se si seleziona il collegamento "Visualizza tutti gli utenti", verrà aperto il riquadro dei dettagli, in cui vengono visualizzate informazioni quali il tipo di utente, il tipo di accesso e la data e l'ultima visualizzazione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="021de-224">Selecting the "See all users" link opens the details pane, which displays information such as user type, log on type, and when the user was first and last seen.</span></span> <span data-ttu-id="021de-225">Per ulteriori informazioni, vedere [Investigate user entities](investigate-user.md).</span><span class="sxs-lookup"><span data-stu-id="021de-225">For more information, see [Investigate user entities](investigate-user.md).</span></span>

![Immagine del riquadro dei dettagli utente](images/logged-on-users.png)

### <a name="security-assessments"></a><span data-ttu-id="021de-227">Valutazioni sulla sicurezza</span><span class="sxs-lookup"><span data-stu-id="021de-227">Security assessments</span></span>

<span data-ttu-id="021de-228">La **scheda Valutazioni della sicurezza** mostra il livello complessivo di esposizione, i consigli per la sicurezza, il software installato e le vulnerabilità individuate.</span><span class="sxs-lookup"><span data-stu-id="021de-228">The **Security assessments** card shows the overall exposure level, security recommendations, installed software, and discovered vulnerabilities.</span></span> <span data-ttu-id="021de-229">Il livello di esposizione di un dispositivo è determinato dall'impatto cumulativo dei consigli di sicurezza in sospeso.</span><span class="sxs-lookup"><span data-stu-id="021de-229">A device's exposure level is determined by the cumulative impact of its pending security recommendations.</span></span>

![Immagine della scheda di valutazione della sicurezza](images/security-assessments.png)

## <a name="related-topics"></a><span data-ttu-id="021de-231">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="021de-231">Related topics</span></span>

- [<span data-ttu-id="021de-232">Visualizzare e organizzare la coda di Microsoft Defender for Endpoint Alerts</span><span class="sxs-lookup"><span data-stu-id="021de-232">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="021de-233">Gestire gli avvisi di Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="021de-233">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="021de-234">Analizzare gli avvisi di Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="021de-234">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="021de-235">Analizzare un file associato a un avviso di Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="021de-235">Investigate a file associated with a Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="021de-236">Analizzare un indirizzo IP associato a un avviso Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="021de-236">Investigate an IP address associated with a Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="021de-237">Analizzare un dominio associato a un avviso Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="021de-237">Investigate a domain associated with a Defender for Endpoint alert</span></span>](investigate-domain.md)
- [<span data-ttu-id="021de-238">Analizzare un account utente in Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="021de-238">Investigate a user account in Defender for Endpoint</span></span>](investigate-user.md)
- [<span data-ttu-id="021de-239">Suggerimenti per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="021de-239">Security recommendation</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="021de-240">Inventario software</span><span class="sxs-lookup"><span data-stu-id="021de-240">Software inventory</span></span>](tvm-software-inventory.md)
