---
title: Analizzare gli eventi imprevisti in Microsoft 365 Defender
description: Analizzare gli incidenti relativi a dispositivi, utenti e cassette postali.
keywords: incidente, incidenti, analizzare, risposta, computer, dispositivi, utenti, identità, posta, posta elettronica, cassetta postale, indagine, grafico, prova
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
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
ms.openlocfilehash: 72e1efb8a06fb7fa64b83ab6522fe4cdcfd1a73e
ms.sourcegitcommit: 5a1cb7d95070eef47d401a4693cc137a90550a5e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52259637"
---
# <a name="analyze-incidents-in-microsoft-365-defender"></a><span data-ttu-id="292fa-104">Analizzare gli eventi imprevisti in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="292fa-104">Analyze incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="292fa-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="292fa-105">**Applies to:**</span></span>

- <span data-ttu-id="292fa-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="292fa-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="292fa-107">Microsoft 365 Defender aggrega tutti gli avvisi, gli asset, le indagini e le prove correlati da dispositivi, utenti e cassette postali in un evento imprevisto per fornire una panoramica completa dell'intera ampiezza di un attacco.</span><span class="sxs-lookup"><span data-stu-id="292fa-107">Microsoft 365 Defender aggregates all related alerts, assets, investigations, and evidence from across your devices, users, and mailboxes into an incident to give you a comprehensive look into the entire breadth of an attack.</span></span>

<span data-ttu-id="292fa-108">All'interno di un evento imprevisto, si analizzano gli avvisi che influiscono sulla rete, si comprende il loro significato e si fascicolano le prove in modo da poter elaborare un piano di correzione efficace.</span><span class="sxs-lookup"><span data-stu-id="292fa-108">Within an incident, you analyze the alerts that affect your network, understand what they mean, and collate the evidence so that you can devise an effective remediation plan.</span></span>

## <a name="initial-analysis"></a><span data-ttu-id="292fa-109">Analisi iniziale</span><span class="sxs-lookup"><span data-stu-id="292fa-109">Initial analysis</span></span>

<span data-ttu-id="292fa-110">Prima di esaminare i dettagli, esaminare le proprietà e il riepilogo dell'evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="292fa-110">Before diving into the details, take a look at the properties and summary of the incident.</span></span>

<span data-ttu-id="292fa-111">È possibile iniziare selezionando l'evento imprevisto dalla colonna del segno di spunta.</span><span class="sxs-lookup"><span data-stu-id="292fa-111">You can start by selecting the incident from the check mark column.</span></span> <span data-ttu-id="292fa-112">Di seguito viene riportato un esempio.</span><span class="sxs-lookup"><span data-stu-id="292fa-112">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incidents-ss-incident-select.png" alt-text="Esempio di selezione di un evento imprevisto dalla colonna del segno di spunta":::

<span data-ttu-id="292fa-114">Quando si esegue questa operazione, viene visualizzato un riquadro di riepilogo con informazioni chiave sull'evento imprevisto, ad esempio la gravità, a cui è assegnato e le categorie [MITRE ATT &trade;&CK](https://attack.mitre.org/) per l'evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="292fa-114">When you do, a summary pane opens with key information about the incident, such as severity, to whom it is assigned, and the [MITRE ATT&CK&trade;](https://attack.mitre.org/) categories for the incident.</span></span> <span data-ttu-id="292fa-115">Di seguito viene riportato un esempio.</span><span class="sxs-lookup"><span data-stu-id="292fa-115">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incidents-ss-incident-side-panel.png" alt-text="Esempio del riquadro di riepilogo per un evento imprevisto":::

<span data-ttu-id="292fa-117">Da qui è possibile selezionare Apri **pagina evento imprevisto.**</span><span class="sxs-lookup"><span data-stu-id="292fa-117">From here, you can select **Open incident page**.</span></span> <span data-ttu-id="292fa-118">Verrà aperta la pagina principale dell'evento imprevisto in cui sono disponibili ulteriori informazioni di riepilogo e schede per avvisi, dispositivi, utenti, indagini ed elementi di prova.</span><span class="sxs-lookup"><span data-stu-id="292fa-118">This opens the main page for the incident where you'll find more summary information and tabs for alerts, devices, users, investigations, and evidence.</span></span>

<span data-ttu-id="292fa-119">È inoltre possibile aprire la pagina principale di un evento imprevisto selezionando il nome dell'evento imprevisto dalla coda degli eventi imprevisti.</span><span class="sxs-lookup"><span data-stu-id="292fa-119">You can also open the main page for an incident by selecting the incident name from the incident queue.</span></span>

## <a name="summary"></a><span data-ttu-id="292fa-120">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="292fa-120">Summary</span></span>

<span data-ttu-id="292fa-121">La **pagina** Riepilogo offre uno sguardo istantaneo sugli aspetti principali da notare sull'evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="292fa-121">The **Summary** page gives you a snapshot glance at the top things to notice about the incident.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Esempio della pagina Riepilogo per un evento imprevisto nel centro sicurezza Microsoft 365 sicurezza":::

<span data-ttu-id="292fa-123">Le categorie di attacco offrono una visualizzazione visiva e numerica dell'avanzamento dell'attacco contro la catena di uccidi.</span><span class="sxs-lookup"><span data-stu-id="292fa-123">The attack categories give you a visual and numeric view of how advanced the attack has progressed against the kill chain.</span></span> <span data-ttu-id="292fa-124">Come per altri prodotti di sicurezza Microsoft, Microsoft 365 Defender è allineato al framework [MITRE ATT&&trade; CK.](https://attack.mitre.org/)</span><span class="sxs-lookup"><span data-stu-id="292fa-124">As with other Microsoft security products, Microsoft 365 Defender is aligned to the [MITRE ATT&CK&trade;](https://attack.mitre.org/) framework.</span></span>

<span data-ttu-id="292fa-125">La sezione relativa all'ambito fornisce un elenco delle principali risorse interessate che fanno parte di questo incidente.</span><span class="sxs-lookup"><span data-stu-id="292fa-125">The scope section gives you a list of top impacted assets that are part of this incident.</span></span> <span data-ttu-id="292fa-126">Se sono presenti informazioni specifiche su una determinata risorsa (ad esempio, il livello di rischio, la priorità dell'indagine e i contrassegni sulle attività) saranno disponibili in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="292fa-126">If there is specific information regarding this asset, such as risk level, investigation priority as well as any tagging on the assets this will also surface in this section.</span></span>

<span data-ttu-id="292fa-127">La sequenza temporale degli avvisi fornisce un'anteprima dell'ordine cronologico in cui si sono verificati gli avvisi, nonché i motivi per cui questi avvisi sono collegati a questo evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="292fa-127">The alerts timeline provides a sneak peek into the chronological order in which the alerts occurred, as well as the reasons that these alerts are linked to this incident.</span></span>

<span data-ttu-id="292fa-128">Infine, la sezione delle prove fornisce un riepilogo del numero di artefatti diversi inclusi nell'evento imprevisto e del relativo stato di correzione, in modo da poter identificare immediatamente se è necessaria un'azione da parte dell'utente.</span><span class="sxs-lookup"><span data-stu-id="292fa-128">And last - the evidence section provides a summary of how many different artifacts were included in the incident and their remediation status, so you can immediately identify if any action is needed by you.</span></span>

<span data-ttu-id="292fa-129">Questa panoramica può essere di aiuto nella analisi iniziale dell'evento imprevisto fornendo informazioni dettagliate sulle caratteristiche principali dell'evento imprevisto di cui è necessario tenere conto.</span><span class="sxs-lookup"><span data-stu-id="292fa-129">This overview can assist in the initial triage of the incident by providing insight into the top characteristics of the incident that you should be aware of.</span></span>

## <a name="alerts"></a><span data-ttu-id="292fa-130">Avvisi</span><span class="sxs-lookup"><span data-stu-id="292fa-130">Alerts</span></span>

<span data-ttu-id="292fa-131">Nella scheda **Avviso** è possibile visualizzare la coda degli avvisi relativi all'evento imprevisto e altre informazioni su di essi, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="292fa-131">On the **Alert** tab, you can view the alert queue for alerts related to the incident and other information about them such as:</span></span>

- <span data-ttu-id="292fa-132">Gravità.</span><span class="sxs-lookup"><span data-stu-id="292fa-132">Severity.</span></span>
- <span data-ttu-id="292fa-133">Entità coinvolte nell'avviso.</span><span class="sxs-lookup"><span data-stu-id="292fa-133">The entities that were involved in the alert.</span></span>
- <span data-ttu-id="292fa-134">Origine degli avvisi (Microsoft Defender for Identity, Microsoft Defender for Endpoint, Microsoft Defender per Office 365).</span><span class="sxs-lookup"><span data-stu-id="292fa-134">The source of the alerts (Microsoft Defender for Identity, Microsoft Defender for Endpoint, Microsoft Defender for Office 365).</span></span>
- <span data-ttu-id="292fa-135">Motivo per cui sono stati collegati tra loro.</span><span class="sxs-lookup"><span data-stu-id="292fa-135">The reason they were linked together.</span></span>

<span data-ttu-id="292fa-136">Di seguito viene riportato un esempio.</span><span class="sxs-lookup"><span data-stu-id="292fa-136">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-alerts.png" alt-text="Esempio di pagina Avvisi per un evento imprevisto":::

<span data-ttu-id="292fa-138">Per impostazione predefinita, gli avvisi vengono ordinati cronologicamente per consentire di vedere come si è verificata l'evento imprevisto nel tempo.</span><span class="sxs-lookup"><span data-stu-id="292fa-138">By default, the alerts are ordered chronologically to allow you to see how the incident played out over time.</span></span> <span data-ttu-id="292fa-139">La selezione di ogni avviso consente di accedere alla pagina principale dell'avviso, in cui è possibile eseguire un'analisi approfondita dell'avviso.</span><span class="sxs-lookup"><span data-stu-id="292fa-139">Selecting each alert takes you to the alert's main page where you can conduct an in-depth analysis of that alert.</span></span> 

<span data-ttu-id="292fa-140">Informazioni su come usare le pagine della coda di avviso e degli avvisi per [analizzare gli avvisi](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="292fa-140">Learn how to use the alert queue and alert pages in [analyze alerts](investigate-alerts.md)</span></span>

## <a name="devices"></a><span data-ttu-id="292fa-141">Dispositivi</span><span class="sxs-lookup"><span data-stu-id="292fa-141">Devices</span></span>

<span data-ttu-id="292fa-142">Nella **scheda Dispositivi** sono elencati tutti i dispositivi correlati all'evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="292fa-142">The **Devices** tab lists all the devices related to the incident.</span></span> <span data-ttu-id="292fa-143">Di seguito viene riportato un esempio.</span><span class="sxs-lookup"><span data-stu-id="292fa-143">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-devices.png" alt-text="Esempio di pagina Dispositivi per un evento imprevisto":::

<span data-ttu-id="292fa-145">Puoi selezionare il segno di spunta per un dispositivo per visualizzare i dettagli del dispositivo, i dati della directory, gli avvisi attivi e gli utenti connessi.</span><span class="sxs-lookup"><span data-stu-id="292fa-145">You can select the check mark for a device to see details of the device, directory data, active alerts, and logged on users.</span></span> <span data-ttu-id="292fa-146">Seleziona il nome del dispositivo per visualizzare i dettagli del dispositivo nell'inventario dei dispositivi di Microsoft Defender for Endpoints.</span><span class="sxs-lookup"><span data-stu-id="292fa-146">Select the name of the device to see device details in the Microsoft Defender for Endpoints device inventory.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-devices-details.png" alt-text="Esempio di pagina dei dispositivi per Microsoft Defender for Endpoints":::

<span data-ttu-id="292fa-148">Dalla pagina del dispositivo puoi raccogliere informazioni aggiuntive sul dispositivo, ad esempio tutti gli avvisi, una sequenza temporale e suggerimenti per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="292fa-148">From the device page, you can gather additional information about the device, such as all of its alerts, a timeline, and security recommendations.</span></span> <span data-ttu-id="292fa-149">Ad esempio, dalla scheda **Sequenza** temporale puoi scorrere la sequenza temporale del computer e visualizzare tutti gli eventi e i comportamenti osservati nel computer in ordine cronologico, in sequenza con gli avvisi generati.</span><span class="sxs-lookup"><span data-stu-id="292fa-149">For example, from the **Timeline** tab, you can scroll through the machine timeline and view all events and behaviors observed on the machine in chronological order, interspersed with the alerts raised.</span></span>

> [!TIP]
> <span data-ttu-id="292fa-150">Puoi eseguire analisi su richiesta in una pagina del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="292fa-150">You can do on-demand scans on a device page.</span></span> <span data-ttu-id="292fa-151">Nel Centro sicurezza Microsoft 365 scegliere **Endpoint > inventario del dispositivo.**</span><span class="sxs-lookup"><span data-stu-id="292fa-151">In the Microsoft 365 security center, choose **Endpoints > Device inventory**.</span></span> <span data-ttu-id="292fa-152">Selezionare un dispositivo con avvisi ed eseguire un'analisi antivirus.</span><span class="sxs-lookup"><span data-stu-id="292fa-152">Select a device that has alerts, and then run an antivirus scan.</span></span> <span data-ttu-id="292fa-153">Le azioni, ad esempio le analisi antivirus, vengono rilevate e visibili nella **pagina Inventario** dispositivi.</span><span class="sxs-lookup"><span data-stu-id="292fa-153">Actions, such as antivirus scans, are tracked and are visible on the **Device inventory** page.</span></span> <span data-ttu-id="292fa-154">Per altre informazioni, vedi [Eseguire Antivirus Microsoft Defender analisi nei dispositivi](/microsoft-365/security/defender-endpoint/respond-machine-alerts#run-microsoft-defender-antivirus-scan-on-devices).</span><span class="sxs-lookup"><span data-stu-id="292fa-154">To learn more, see [Run Microsoft Defender Antivirus scan on devices](/microsoft-365/security/defender-endpoint/respond-machine-alerts#run-microsoft-defender-antivirus-scan-on-devices).</span></span>

## <a name="users"></a><span data-ttu-id="292fa-155">Utenti</span><span class="sxs-lookup"><span data-stu-id="292fa-155">Users</span></span>

<span data-ttu-id="292fa-156">Nella **scheda Utenti** sono elencati tutti gli utenti identificati come parte o correlati all'evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="292fa-156">The **Users** tab lists all the users that have been identified to be part of or related to the incident.</span></span> <span data-ttu-id="292fa-157">Di seguito viene riportato un esempio.</span><span class="sxs-lookup"><span data-stu-id="292fa-157">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="Esempio di pagina Utenti per un evento imprevisto":::

<span data-ttu-id="292fa-159">È possibile selezionare il segno di spunta per un utente per visualizzare i dettagli della minaccia, dell'esposizione e delle informazioni di contatto dell'account utente.</span><span class="sxs-lookup"><span data-stu-id="292fa-159">You can select the check mark for a user to see details of the user account threat, exposure, and contact information.</span></span> <span data-ttu-id="292fa-160">Selezionare il nome utente per visualizzare ulteriori dettagli sull'account utente.</span><span class="sxs-lookup"><span data-stu-id="292fa-160">Select the user name to see additional user account details.</span></span>

## <a name="mailboxes"></a><span data-ttu-id="292fa-161">Cassette postali</span><span class="sxs-lookup"><span data-stu-id="292fa-161">Mailboxes</span></span>

<span data-ttu-id="292fa-162">Nella **scheda Cassette** postali sono elencate tutte le cassette postali identificate come parte o correlate all'evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="292fa-162">The **Mailboxes** tab lists all the mailboxes that have been identified to be part of or related to the incident.</span></span> <span data-ttu-id="292fa-163">Di seguito viene riportato un esempio.</span><span class="sxs-lookup"><span data-stu-id="292fa-163">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-mailboxes.png" alt-text="Esempio di pagina Cassette postali per un evento imprevisto":::

<span data-ttu-id="292fa-165">È possibile selezionare il segno di spunta per una cassetta postale per visualizzare un elenco di avvisi attivi.</span><span class="sxs-lookup"><span data-stu-id="292fa-165">You can select the check mark for a mailbox to see a list of active alerts.</span></span> <span data-ttu-id="292fa-166">Selezionare il nome della cassetta postale per visualizzare ulteriori dettagli della cassetta postale nella pagina Esplora per Microsoft Defender per Office 365.</span><span class="sxs-lookup"><span data-stu-id="292fa-166">Select the mailbox name to see additional mailbox details on the Explorer page for Microsoft Defender for Office 365.</span></span>

## <a name="investigations"></a><span data-ttu-id="292fa-167">Indagini</span><span class="sxs-lookup"><span data-stu-id="292fa-167">Investigations</span></span>

<span data-ttu-id="292fa-168">Nella **scheda Indagini** sono elencate tutte le indagini automatizzate attivate dagli avvisi in questo evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="292fa-168">The **Investigations** tab lists all the automated investigations triggered by alerts in this incident.</span></span> <span data-ttu-id="292fa-169">Le indagini eseguiranno azioni di correzione o attenderanno l'approvazione degli analisti delle azioni, a seconda di come hai configurato le indagini automatizzate per l'esecuzione in Microsoft Defender per Endpoint e Defender per Office 365.</span><span class="sxs-lookup"><span data-stu-id="292fa-169">The investigations will perform remediation actions or wait for analyst approval of actions, depending on how you configured your automated investigations to run in Microsoft Defender for Endpoint and Defender for Office 365.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-investigations.png" alt-text="Esempio di pagina Indagini per un evento imprevisto":::

<span data-ttu-id="292fa-171">Selezionare un'indagine per accedere alla pagina dei dettagli dell'indagine per ottenere informazioni complete sull'indagine e sullo stato della correzione.</span><span class="sxs-lookup"><span data-stu-id="292fa-171">Select an investigation to navigate to the Investigation details page to get full information on the investigation and remediation status.</span></span> <span data-ttu-id="292fa-172">Se sono presenti azioni in sospeso per l'approvazione nell'ambito dell'indagine, verranno visualizzate nella scheda Azioni in sospeso. Eseguire un'azione nell'ambito della correzione degli eventi imprevisti.</span><span class="sxs-lookup"><span data-stu-id="292fa-172">If there are any actions pending for approval as part of the investigation, they will appear in the Pending actions tab. Take action as part of incident remediation.</span></span>

## <a name="evidence-and-response"></a><span data-ttu-id="292fa-173">Prova e risposta</span><span class="sxs-lookup"><span data-stu-id="292fa-173">Evidence and Response</span></span>

<span data-ttu-id="292fa-174">La **scheda Prova e risposta** mostra tutti gli eventi supportati e le entità sospette negli avvisi nell'evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="292fa-174">The **Evidence and Response** tab shows all the supported events and suspicious entities in the alerts in the incident.</span></span> <span data-ttu-id="292fa-175">Di seguito viene riportato un esempio.</span><span class="sxs-lookup"><span data-stu-id="292fa-175">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-evidence.png" alt-text="Esempio di pagina Prova e risposta per un evento imprevisto":::

<span data-ttu-id="292fa-177">Microsoft 365 Defender analizza automaticamente tutti gli eventi supportati e le entità sospette degli eventi imprevisti negli avvisi, fornendo informazioni sui messaggi di posta elettronica, i file, i processi, i servizi, gli indirizzi IP e altro ancora importanti.</span><span class="sxs-lookup"><span data-stu-id="292fa-177">Microsoft 365 Defender automatically investigates all the incidents' supported events and suspicious entities in the alerts, providing you with information about the important emails, files, processes, services, IP Addresses, and more.</span></span> <span data-ttu-id="292fa-178">In questo modo è possibile rilevare e bloccare rapidamente potenziali minacce nell'evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="292fa-178">This helps you quickly detect and block potential threats in the incident.</span></span>

<span data-ttu-id="292fa-179">Ogni entità analizzata è contrassegnata con un verdetto (Dannoso, Sospetto, Pulito) e uno stato di correzione.</span><span class="sxs-lookup"><span data-stu-id="292fa-179">Each of the analyzed entities is marked with a verdict (Malicious, Suspicious, Clean) and a remediation status.</span></span> <span data-ttu-id="292fa-180">In questo modo è possibile comprendere lo stato di correzione dell'intero evento imprevisto e i passaggi successivi.</span><span class="sxs-lookup"><span data-stu-id="292fa-180">This helps you understand the remediation status of the entire incident and what next steps can be taken.</span></span>

## <a name="graph-in-preview"></a><span data-ttu-id="292fa-181">Graph (in anteprima)</span><span class="sxs-lookup"><span data-stu-id="292fa-181">Graph (in Preview)</span></span>

<span data-ttu-id="292fa-182">Con la nuova **scheda Graph** (in anteprima), puoi vedere:</span><span class="sxs-lookup"><span data-stu-id="292fa-182">With the new **Graph** tab (in preview), you can see:</span></span>

- <span data-ttu-id="292fa-183">La connessione degli avvisi agli asset influenzati nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="292fa-183">The connection of alerts to the impacted assets in your organization.</span></span>
- <span data-ttu-id="292fa-184">Entità correlate agli avvisi e al modo in cui fanno parte della storia dell'attacco.</span><span class="sxs-lookup"><span data-stu-id="292fa-184">Which entities are related to which alerts and how they are part of the story of the attack.</span></span>
- <span data-ttu-id="292fa-185">Avvisi per l'evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="292fa-185">The alerts for the incident.</span></span>

<span data-ttu-id="292fa-186">Di seguito viene riportato un esempio.</span><span class="sxs-lookup"><span data-stu-id="292fa-186">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-graph.png" alt-text="Esempio di pagina Graph per un evento imprevisto":::

<span data-ttu-id="292fa-188">Il grafico degli incidenti consente di comprendere rapidamente l'ambito completo dell'attacco connettendo le diverse entità sospette che fanno parte dell'attacco con gli asset correlati, ad esempio utenti, dispositivi e cassette postali.</span><span class="sxs-lookup"><span data-stu-id="292fa-188">The incident graph helps you quickly understand the full scope of the attack by connecting the different suspicious entities that are part of the attack with their related assets such as users, devices, and mailboxes.</span></span> 

<span data-ttu-id="292fa-189">Ora è possibile comprendere come l'attacco si è diffuso nella rete nel corso del tempo, da dove è iniziato e fino a che punto è andato l'attacco.</span><span class="sxs-lookup"><span data-stu-id="292fa-189">Now you can understand how the attack spread through your network over time, where it started, and how far the attack went.</span></span>


## <a name="related-topics"></a><span data-ttu-id="292fa-190">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="292fa-190">Related topics</span></span>

- [<span data-ttu-id="292fa-191">Panoramica sugli incidenti</span><span class="sxs-lookup"><span data-stu-id="292fa-191">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="292fa-192">Assegnare priorità agli incidenti</span><span class="sxs-lookup"><span data-stu-id="292fa-192">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="292fa-193">Gestire gli incidenti</span><span class="sxs-lookup"><span data-stu-id="292fa-193">Manage incidents</span></span>](manage-incidents.md)

