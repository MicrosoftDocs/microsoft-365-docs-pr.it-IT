---
title: Profilo dispositivo nel portale di sicurezza di Microsoft 365
description: Visualizzare i livelli di rischio e esposizione per un dispositivo nell'organizzazione. Analizzare le minacce passate e presenti e proteggere il dispositivo con gli aggiornamenti più recenti.
keywords: sicurezza, malware, Microsoft 365, M365, Microsoft Threat Protection, MTP, centro sicurezza, Microsoft Defender ATP, Office 365 ATP, Azure ATP, pagina del dispositivo, profilo del dispositivo, pagina del computer, profilo computer
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: v-maave
author: martyav
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.technology: m365d
ms.openlocfilehash: 40897185ab885ee2b6880ecd5f25d95fbe3d771e
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929575"
---
# <a name="device-profile-page"></a><span data-ttu-id="4bbc3-105">Pagina Profilo dispositivo</span><span class="sxs-lookup"><span data-stu-id="4bbc3-105">Device profile page</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="4bbc3-106">Il portale di sicurezza di Microsoft 365 fornisce le pagine del profilo del dispositivo, in modo da poter valutare rapidamente l'integrità e lo stato dei dispositivi nella rete.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-106">The Microsoft 365 security portal provides you with device profile pages, so you can quickly assess the health and status of devices on your network.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4bbc3-107">La pagina del profilo del dispositivo potrebbe essere leggermente diversa, a seconda che il dispositivo sia registrato in Microsoft Defender for Endpoint, Microsoft Defender for Identity o entrambi.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-107">The device profile page may appear slightly different, depending on whether the device is enrolled in Microsoft Defender for Endpoint, Microsoft Defender for Identity, or both.</span></span>

<span data-ttu-id="4bbc3-108">Se il dispositivo è registrato in Microsoft Defender per Endpoint, puoi anche usare la pagina del profilo del dispositivo per eseguire alcune attività di sicurezza comuni.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-108">If the device is enrolled in Microsoft Defender for Endpoint, you can also use the device profile page to perform some common security tasks.</span></span>

## <a name="navigating-the-device-profile-page"></a><span data-ttu-id="4bbc3-109">Spostamento nella pagina del profilo del dispositivo</span><span class="sxs-lookup"><span data-stu-id="4bbc3-109">Navigating the device profile page</span></span>

<span data-ttu-id="4bbc3-110">La pagina del profilo è suddivisa in diverse sezioni generali.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-110">The profile page is broken up into several broad sections.</span></span>

![Immagine della pagina del profilo del dispositivo con (1) Area scheda (2) Barra laterale e (3) Azioni evidenziate in rosso](../../media/mtp-device-profile/hybrid-device-overall.png)

<span data-ttu-id="4bbc3-112">La barra laterale (1) elenca i dettagli di base sul dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-112">The sidebar (1) lists basic details about the device.</span></span>

<span data-ttu-id="4bbc3-113">L'area del contenuto principale (2) contiene schede che puoi alternare per visualizzare diversi tipi di informazioni sul dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-113">The main content area (2) contains tabs that you can toggle through to view different kinds of information about the device.</span></span>

<span data-ttu-id="4bbc3-114">Se il dispositivo è registrato in Microsoft Defender per Endpoint, verrà visualizzato anche un elenco di azioni di risposta (3).</span><span class="sxs-lookup"><span data-stu-id="4bbc3-114">If the device is enrolled in Microsoft Defender for Endpoint, you will also see a list of response actions (3).</span></span> <span data-ttu-id="4bbc3-115">Le azioni di risposta consentono di eseguire attività comuni relative alla sicurezza.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-115">Response actions allow you to perform common security-related tasks.</span></span>

## <a name="sidebar"></a><span data-ttu-id="4bbc3-116">Barra laterale</span><span class="sxs-lookup"><span data-stu-id="4bbc3-116">Sidebar</span></span>

<span data-ttu-id="4bbc3-117">Accanto all'area del contenuto principale della pagina del profilo del dispositivo è visualizzata la barra laterale.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-117">Beside the main content area of the device profile page is the sidebar.</span></span>

![Immagine della scheda della barra laterale per il profilo del dispositivo](../../media/mtp-device-profile/azure-atp-only-device-sidebar.png)

<span data-ttu-id="4bbc3-119">La barra laterale elenca il nome completo e il livello di esposizione del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-119">The sidebar lists the device's full name and exposure level.</span></span> <span data-ttu-id="4bbc3-120">Vengono inoltre fornite alcune importanti informazioni di base nelle sottosezioni di piccole dimensioni che possono essere attivate o chiuse, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="4bbc3-120">It also provides some important basic information in small subsections which can be toggled open or closed, such as:</span></span>

* <span data-ttu-id="4bbc3-121">**Tag:** qualsiasi microsoft defender per endpoint, Microsoft Defender per l'identità o tag personalizzati associati al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-121">**Tags** - Any Microsoft Defender for Endpoint, Microsoft Defender for Identity, or custom tags associated with the device.</span></span> <span data-ttu-id="4bbc3-122">I tag di Microsoft Defender for Identity non sono modificabili.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-122">Tags from Microsoft Defender for Identity are not editable.</span></span>
* <span data-ttu-id="4bbc3-123">**Info di sicurezza:** eventi imprevisti aperti e avvisi attivi.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-123">**Security info** - Open incidents and active alerts.</span></span> <span data-ttu-id="4bbc3-124">Anche i dispositivi registrati in Microsoft Defender per Endpoint visualizzano il livello di esposizione e il livello di rischio.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-124">Devices enrolled in Microsoft Defender for Endpoint will also display exposure level and risk level.</span></span>

> [!TIP]
> <span data-ttu-id="4bbc3-125">Il livello di esposizione si riferisce a quanto il dispositivo è conforme alle raccomandazioni per la sicurezza, mentre il livello di rischio viene calcolato in base a una serie di fattori, inclusi i tipi e la gravità degli avvisi attivi.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-125">Exposure level relates to how much the device is complying with security recommendations, while risk level is calculated based on a number of factors, including the types and severity of active alerts.</span></span>

* <span data-ttu-id="4bbc3-126">**Dettagli dispositivo:** dominio, sistema operativo, timestamp della prima visualizzazione del dispositivo, indirizzi IP, risorse.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-126">**Device details** - Domain, OS, timestamp for when the device was first seen, IP addresses, resources.</span></span> <span data-ttu-id="4bbc3-127">Anche i dispositivi registrati in Microsoft Defender per Endpoint visualizzano lo stato di integrità.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-127">Devices enrolled in Microsoft Defender for Endpoint also display health state.</span></span> <span data-ttu-id="4bbc3-128">I dispositivi registrati in Microsoft Defender per l'identità visualizzano il nome SAM e un timestamp per la prima creazione del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-128">Devices enrolled in Microsoft Defender for Identity will display SAM name and a timestamp for when the device was first created.</span></span>
* <span data-ttu-id="4bbc3-129">**Attività di** rete: timestamp per la prima volta e l'ultima volta in cui il dispositivo è stato visualizzato in rete.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-129">**Network activity** - Timestamps for the first time and last time the device was seen on the network.</span></span>
* <span data-ttu-id="4bbc3-130">**Dati della directory** *(solo per i dispositivi registrati in Microsoft Defender per* l'identità): flag [di](https://docs.microsoft.com/windows/win32/ad/service-principal-names)Controllo dell'account utente, nomi SPN e appartenenze a gruppi. [](https://docs.microsoft.com/windows/security/identity-protection/user-account-control/user-account-control-overview)</span><span class="sxs-lookup"><span data-stu-id="4bbc3-130">**Directory data** (*only for devices enrolled in Microsoft Defender for Identity*) - [UAC](https://docs.microsoft.com/windows/security/identity-protection/user-account-control/user-account-control-overview) flags, [SPNs](https://docs.microsoft.com/windows/win32/ad/service-principal-names), and group memberships.</span></span>

## <a name="response-actions"></a><span data-ttu-id="4bbc3-131">Azioni di risposta</span><span class="sxs-lookup"><span data-stu-id="4bbc3-131">Response actions</span></span>

<span data-ttu-id="4bbc3-132">Le azioni di risposta offrono un modo rapido per difendersi dalle minacce e analizzarne le minacce.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-132">Response actions offer a quick way to defend against and analyze threats.</span></span>

![Immagine della barra delle azioni per il profilo del dispositivo](../../media/mtp-device-profile/hybrid-device-long-action-bar.png)

> [!IMPORTANT]
> * <span data-ttu-id="4bbc3-134">[Le azioni](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts) di risposta sono disponibili solo se il dispositivo è registrato in Microsoft Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-134">[Response actions](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts) are only available if the device is enrolled in Microsoft Defender for Endpoint.</span></span>
> * <span data-ttu-id="4bbc3-135">I dispositivi registrati in Microsoft Defender per Endpoint potrebbero visualizzare un numero diverso di azioni di risposta, in base al sistema operativo e al numero di versione del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-135">Devices that are enrolled in Microsoft Defender for Endpoint may display different numbers of response actions, based on the device's OS and version number.</span></span>

<span data-ttu-id="4bbc3-136">Le azioni disponibili nella pagina del profilo del dispositivo includono:</span><span class="sxs-lookup"><span data-stu-id="4bbc3-136">Actions available on the device profile page include:</span></span>

* <span data-ttu-id="4bbc3-137">**Gestisci tag:** aggiorna i tag personalizzati applicati a questo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-137">**Manage tags** - Updates custom tags you have applied to this device.</span></span>
* <span data-ttu-id="4bbc3-138">**Isola dispositivo:** isola il dispositivo dalla rete dell'organizzazione mantenendolo connesso a Microsoft Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-138">**Isolate device** - Isolates the device from your organization's network while keeping it connected to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="4bbc3-139">È possibile scegliere di consentire l'esecuzione di Outlook, Teams e Skype for Business mentre il dispositivo è isolato, a scopo di comunicazione.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-139">You can choose to allow Outlook, Teams, and Skype for Business to run while the device is isolated, for communication purposes.</span></span>
* <span data-ttu-id="4bbc3-140">**Centro notifiche:** consente di visualizzare lo stato delle azioni inviate.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-140">**Action center** - View the status of submitted actions.</span></span> <span data-ttu-id="4bbc3-141">Disponibile solo se è già stata selezionata un'altra azione.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-141">Only available if another action has already been selected.</span></span>
* <span data-ttu-id="4bbc3-142">**Limitare l'esecuzione delle** app: impedisce l'esecuzione di applicazioni non firmate da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-142">**Restrict app execution** - Prevents applications that are not signed by Microsoft from running.</span></span>
* <span data-ttu-id="4bbc3-143">**Eseguire l'analisi antivirus:** gli Windows Defender definizioni antivirus ed esegue immediatamente un'analisi antivirus.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-143">**Run antivirus scan** - Updates Windows Defender Antivirus definitions and immediately runs an antivirus scan.</span></span> <span data-ttu-id="4bbc3-144">Scegliere tra Analisi rapida o Analisi completa.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-144">Choose between Quick scan or Full scan.</span></span>
* <span data-ttu-id="4bbc3-145">**Raccogliere il pacchetto di** analisi: raccoglie informazioni sul dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-145">**Collect investigation package** - Gathers information about the device.</span></span> <span data-ttu-id="4bbc3-146">Al termine dell'indagine, è possibile scaricarla.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-146">When the investigation is completed, you can download it.</span></span>
* <span data-ttu-id="4bbc3-147">**Avvia sessione di risposta in tempo** reale: carica una shell remota nel dispositivo per indagini [approfondite sulla sicurezza.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)</span><span class="sxs-lookup"><span data-stu-id="4bbc3-147">**Initiate Live Response Session** - Loads a remote shell on the device for [in-depth security investigations](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response).</span></span>
* <span data-ttu-id="4bbc3-148">**Avviare un'indagine automatizzata:** consente di [analizzare e correggere automaticamente le minacce.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)</span><span class="sxs-lookup"><span data-stu-id="4bbc3-148">**Initiate automated investigation** - Automatically [investigates and remediates threats](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air).</span></span> <span data-ttu-id="4bbc3-149">Sebbene sia possibile attivare manualmente l'esecuzione di indagini automatizzate da questa [pagina,](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?view=o365-worldwide#default-alert-policies) alcuni criteri di avviso attivano automaticamente le indagini.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-149">Although you can manually trigger automated investigations to run from this page, [certain alert policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?view=o365-worldwide#default-alert-policies) trigger automatic investigations on their own.</span></span>
* <span data-ttu-id="4bbc3-150">**Centro notifiche:** visualizza informazioni sulle azioni di risposta attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-150">**Action center** - Displays information about any response actions that are currently running.</span></span>

## <a name="tabs-section"></a><span data-ttu-id="4bbc3-151">Sezione Tabs</span><span class="sxs-lookup"><span data-stu-id="4bbc3-151">Tabs section</span></span>

<span data-ttu-id="4bbc3-152">Le schede del profilo del dispositivo consentono di passare da una panoramica dei dettagli di sicurezza sul dispositivo e le tabelle contenenti un elenco di avvisi.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-152">The device profile tabs allow you to toggle through an overview of security details about the device, and tables containing a list of alerts.</span></span>

<span data-ttu-id="4bbc3-153">I dispositivi registrati in Microsoft Defender per Endpoint visualizzano anche schede che presentano una sequenza temporale, un elenco di suggerimenti sulla sicurezza, un inventario software, un elenco di vulnerabilità individuate e gli indicatori KPI mancanti (aggiornamenti della sicurezza).</span><span class="sxs-lookup"><span data-stu-id="4bbc3-153">Devices enrolled in Microsoft Defender for Endpoint will also display tabs that feature a timeline, a list of security recommendations, a software inventory, a list of discovered vulnerabilities, and missing KBs (security updates).</span></span>

### <a name="overview-tab"></a><span data-ttu-id="4bbc3-154">Scheda Panoramica</span><span class="sxs-lookup"><span data-stu-id="4bbc3-154">Overview tab</span></span>

<span data-ttu-id="4bbc3-155">La scheda predefinita è **Panoramica.**</span><span class="sxs-lookup"><span data-stu-id="4bbc3-155">The default tab is **Overview**.</span></span> <span data-ttu-id="4bbc3-156">Fornisce un rapido sguardo al fatto di sicurezza più importante sul dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-156">It provides a quick look at the most important security fact about the device.</span></span>

![Immagine della scheda Panoramica per il profilo del dispositivo](../../media/mtp-device-profile/hybrid-device-tab-overview.png)

<span data-ttu-id="4bbc3-158">Qui puoi visualizzare rapidamente gli avvisi attivi del dispositivo e gli utenti attualmente connessi.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-158">Here, you can get a quick look at the device's active alerts, and any currently logged on users.</span></span>

<span data-ttu-id="4bbc3-159">Se il dispositivo è registrato in Microsoft Defender per Endpoint, verranno visualizzati anche il livello di rischio del dispositivo e i dati disponibili sulle valutazioni della sicurezza.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-159">If the device is enrolled in Microsoft Defender for Endpoint, you will also see the device's risk level and any available data on security assessments.</span></span> <span data-ttu-id="4bbc3-160">Le valutazioni della sicurezza descrivono il livello di esposizione del dispositivo, forniscono consigli sulla sicurezza ed elencano il software interessato e le vulnerabilità individuate.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-160">The security assessments describe the device's exposure level, provide security recommendations, and list affected software and discovered vulnerabilities.</span></span>

### <a name="alerts-tab"></a><span data-ttu-id="4bbc3-161">Scheda Avvisi</span><span class="sxs-lookup"><span data-stu-id="4bbc3-161">Alerts tab</span></span>

<span data-ttu-id="4bbc3-162">La **scheda Avvisi** contiene un elenco di avvisi generati nel dispositivo, sia da Microsoft Defender per l'identità che da Microsoft Defender per endpoint.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-162">The **Alerts** tab contains a list of alerts that have been raised on the device, from both Microsoft Defender for Identity and Microsoft Defender for Endpoint.</span></span>

![Immagine della scheda avvisi per il profilo del dispositivo](../../media/mtp-device-profile/hybrid-device-tab-alerts.png)

<span data-ttu-id="4bbc3-164">È possibile personalizzare il numero di elementi visualizzati, nonché le colonne visualizzate per ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-164">You can customize the number of items displayed, as well as which columns are displayed for each item.</span></span> <span data-ttu-id="4bbc3-165">Il comportamento predefinito è elencare trenta elementi per pagina.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-165">The default behavior is to list thirty items per page.</span></span>

<span data-ttu-id="4bbc3-166">Le colonne in questa scheda includono informazioni sulla gravità della minaccia che ha attivato l'avviso, nonché lo stato, lo stato dell'indagine e l'utente a cui è stato assegnato l'avviso.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-166">The columns in this tab include information on the severity of the threat that triggered the alert, as well as status, investigation state, and who the alert has been assigned to.</span></span>

<span data-ttu-id="4bbc3-167">La *colonna delle entità interessate* fa riferimento al dispositivo (entità) di cui si sta visualizzando il profilo, oltre a tutti gli altri dispositivi della rete interessati.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-167">The *impacted entities* column refers to the device (entity) whose profile you are currently viewing, plus any other devices in your network that are affected.</span></span>

<span data-ttu-id="4bbc3-168">Se si seleziona un elemento dall'elenco, verrà aperto un riquadro a comparsa contenente ulteriori informazioni sull'avviso selezionato.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-168">Selecting an item from this list will open a flyout containing even more information about the selected alert.</span></span>

<span data-ttu-id="4bbc3-169">Questo elenco può essere filtrato in base alla gravità, allo stato o all'utente a cui è stato assegnato l'avviso.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-169">This list can be filtered by severity, status, or who the alert has been assigned to.</span></span>

### <a name="timeline-tab"></a><span data-ttu-id="4bbc3-170">Scheda Sequenza temporale</span><span class="sxs-lookup"><span data-stu-id="4bbc3-170">Timeline tab</span></span>

<span data-ttu-id="4bbc3-171">La **scheda Sequenza** temporale include un grafico cronologico interattivo di tutti gli eventi generati nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-171">The **Timeline** tab includes an interactive, chronological chart of all events raised on the device.</span></span> <span data-ttu-id="4bbc3-172">Spostando l'area evidenziata del grafico a sinistra o a destra, è possibile visualizzare gli eventi in periodi di tempo diversi.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-172">By moving the highlighted area of the chart left or right, you can view events over different periods of time.</span></span> <span data-ttu-id="4bbc3-173">Puoi anche scegliere un intervallo personalizzato di date dal menu a discesa tra il grafico interattivo e l'elenco degli eventi.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-173">You can also choose a custom range of dates from the dropdown menu in between the interactive chart and the list of events.</span></span>

<span data-ttu-id="4bbc3-174">Sotto il grafico è riportato un elenco di eventi per l'intervallo di date selezionato.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-174">Below the chart is a list of events for the selected range of dates.</span></span>

![Immagine della scheda sequenza temporale per il profilo del dispositivo](../../media/mtp-device-profile/hybrid-device-tab-timeline.png)

<span data-ttu-id="4bbc3-176">Il numero di elementi visualizzati e le colonne nell'elenco possono essere entrambi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-176">The number of items displayed and the columns on the list can both be customized.</span></span> <span data-ttu-id="4bbc3-177">Le colonne predefinite elencano l'ora dell'evento, l'utente attivo, il tipo di azione, le entità (processi) e informazioni aggiuntive sull'evento.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-177">The default columns list the event time, active user, action type, entities (processes), and additional information about the event.</span></span>

<span data-ttu-id="4bbc3-178">Se si seleziona un elemento da questo elenco, verrà visualizzato un riquadro a comparsa con un grafico delle entità evento che mostra i processi padre e figlio coinvolti nell'evento.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-178">Selecting an item from this list will open a flyout displaying an Event entities graph, showing the parent and child processes involved in the event.</span></span>

<span data-ttu-id="4bbc3-179">L'elenco può essere filtrato in base al tipo specifico di evento. ad esempio eventi del Registro di sistema o eventi smart screen.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-179">The list can be filtered by the specific kind of event; for example, Registry events or Smart Screen Events.</span></span>

<span data-ttu-id="4bbc3-180">L'elenco può anche essere esportato in un file CSV, per il download.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-180">The list can also be exported to a CSV file, for download.</span></span> <span data-ttu-id="4bbc3-181">Anche se il file non è limitato dal numero di eventi, l'intervallo di tempo massimo che è possibile scegliere di esportare è di sette giorni.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-181">Although the file is not limited by number of events, the maximum time range you can choose to export is seven days.</span></span>

### <a name="security-recommendations-tab"></a><span data-ttu-id="4bbc3-182">Scheda Suggerimenti per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="4bbc3-182">Security recommendations tab</span></span>

<span data-ttu-id="4bbc3-183">Nella **scheda Consigli per la** sicurezza sono elencate le azioni che puoi eseguire per proteggere il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-183">The **Security recommendations** tab lists actions you can take to protect the device.</span></span> <span data-ttu-id="4bbc3-184">La selezione di un elemento in questo elenco consente di aprire un riquadro a comparsa in cui è possibile ottenere istruzioni su come applicare il suggerimento.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-184">Selecting an item on this list will open a flyout where you can get instructions on how to apply the recommendation.</span></span>

![Immagine della scheda degli elementi consigliati per la sicurezza per il profilo del dispositivo](../../media/mtp-device-profile/hybrid-device-tab-security-recs.png)

<span data-ttu-id="4bbc3-186">Come per le schede precedenti, è possibile personalizzare il numero di elementi visualizzati per pagina, nonché le colonne visibili.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-186">As with the previous tabs, the number of items displayed per page, as well as which columns are visible, can be customized.</span></span>

<span data-ttu-id="4bbc3-187">La visualizzazione predefinita include colonne che dettagliano i punti deboli della sicurezza, la minaccia associata, il componente o il software correlato interessato dalla minaccia e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-187">The default view includes columns that detail the security weaknesses addressed, the associated threat, the related component or software affected by the threat, and more.</span></span> <span data-ttu-id="4bbc3-188">Gli elementi possono essere filtrati in base allo stato del suggerimento.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-188">Items can be filtered by the recommendation's status.</span></span>

### <a name="software-inventory"></a><span data-ttu-id="4bbc3-189">Inventario software</span><span class="sxs-lookup"><span data-stu-id="4bbc3-189">Software inventory</span></span>

<span data-ttu-id="4bbc3-190">La **scheda Inventario software** elenca il software installato nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-190">The **Software inventory** tab lists software installed on the device.</span></span>

![Immagine della scheda inventario software per il profilo del dispositivo](../../media/mtp-device-profile/hybrid-device-tab-software-inventory.png)

<span data-ttu-id="4bbc3-192">Nella visualizzazione predefinita vengono visualizzati il fornitore del software, il numero di versione installato, il numero di punti deboli noti del software, informazioni dettagliate sulle minacce, codice prodotto e tag.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-192">The default view displays the software vendor, installed version number, number of known software weaknesses, threat insights, product code, and tags.</span></span> <span data-ttu-id="4bbc3-193">Il numero di elementi visualizzati e le colonne visualizzate possono essere entrambi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-193">The number of items displayed and which columns are displayed can both be customized.</span></span>

<span data-ttu-id="4bbc3-194">Selezionando un elemento da questo elenco si apre un riquadro a comparsa contenente ulteriori dettagli sul software selezionato, nonché il percorso e il timestamp dell'ultima volta che il software è stato trovato.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-194">Selecting an item from this list opens a flyout containing more details about the selected software, as well as the path and timestamp for the last time the software was found.</span></span>

<span data-ttu-id="4bbc3-195">Questo elenco può essere filtrato in base al codice prodotto.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-195">This list can be filtered by product code.</span></span>

### <a name="discovered-vulnerabilities-tab"></a><span data-ttu-id="4bbc3-196">Scheda Vulnerabilità individuate</span><span class="sxs-lookup"><span data-stu-id="4bbc3-196">Discovered vulnerabilities tab</span></span>

<span data-ttu-id="4bbc3-197">Nella **scheda Vulnerabilità individuate** sono elencate tutte le vulnerabilità e gli exploit comuni che possono influire sul dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-197">The **Discovered vulnerabilities** tab lists any Common Vulnerabilities and Exploits (CVEs) that may affect the device.</span></span>

![Immagine della scheda delle vulnerabilità individuate per il profilo del dispositivo](../../media/mtp-device-profile/hybrid-device-tab-discovered-vulnerabilities.png)

<span data-ttu-id="4bbc3-199">La visualizzazione predefinita elenca la gravità del CVE, il punteggio di vulnerabilità comune (CVS), il software correlato al CVE, la data di pubblicazione del CVE, l'ultimo aggiornamento del CVE e le minacce associate al CVE.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-199">The default view lists the severity of the CVE, the Common Vulnerability Score (CVS), the software related to the CVE, when the CVE was published, when the CVE was last updated, and threats associated with the CVE.</span></span>

<span data-ttu-id="4bbc3-200">Come per le schede precedenti, è possibile personalizzare il numero di elementi visualizzati e le colonne visibili.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-200">As with the previous tabs, the number of items displayed and which columns are visible can be customized.</span></span>

<span data-ttu-id="4bbc3-201">Se si seleziona un elemento dall'elenco, verrà aperto un riquadro a comparsa che descrive il punto di controllo.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-201">Selecting an item from this list will open a flyout that describes the CVE.</span></span>

### <a name="missing-kbs"></a><span data-ttu-id="4bbc3-202">Indicatori KPI mancanti</span><span class="sxs-lookup"><span data-stu-id="4bbc3-202">Missing KBs</span></span>

<span data-ttu-id="4bbc3-203">Nella **scheda Kpi** mancanti sono elencati gli eventuali aggiornamenti Microsoft che devono ancora essere applicati al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-203">The **Missing KBs** tab lists any Microsoft Updates that have yet to be applied to the device.</span></span> <span data-ttu-id="4bbc3-204">I "Kb" in questione sono articoli [della Knowledge Base](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) che descrivono questi aggiornamenti; ad esempio [KB4551762.](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762)</span><span class="sxs-lookup"><span data-stu-id="4bbc3-204">The "KBs" in question are [Knowledge Base articles](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) which describe these updates; for example, [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).</span></span>

![Immagine della scheda kb mancante per il profilo del dispositivo](../../media/mtp-device-profile/hybrid-device-tab-missing-kbs.PNG)

<span data-ttu-id="4bbc3-206">Nella visualizzazione predefinita sono elencati i bollettini contenenti gli aggiornamenti, la versione del sistema operativo, i prodotti interessati, i CVE indirizzati, il numero KB e i tag.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-206">The default view lists the bulletin containing the updates, OS version, products affected, CVEs addressed, the KB number, and tags.</span></span>

<span data-ttu-id="4bbc3-207">Il numero di elementi visualizzati per pagina e le colonne visualizzate possono essere personalizzati.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-207">The number of items displayed per page and which columns are displayed can be customized.</span></span>

<span data-ttu-id="4bbc3-208">Se si seleziona un elemento, verrà aperto un riquadro a comparsa che collega all'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="4bbc3-208">Selecting an item will open a flyout that links to the update.</span></span>

## <a name="related-topics"></a><span data-ttu-id="4bbc3-209">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="4bbc3-209">Related topics</span></span>

* [<span data-ttu-id="4bbc3-210">Panoramica di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4bbc3-210">Microsoft 365 Defender overview</span></span>](microsoft-threat-protection.md)
* [<span data-ttu-id="4bbc3-211">Attivare Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4bbc3-211">Turn on Microsoft 365 Defender</span></span>](mtp-enable.md)
* [<span data-ttu-id="4bbc3-212">Analizzare le entità nei dispositivi, usando la risposta in tempo reale</span><span class="sxs-lookup"><span data-stu-id="4bbc3-212">Investigate entities on devices, using live response</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)
* [<span data-ttu-id="4bbc3-213">Analisi e risposta automatizzate (AIR) in Office 365</span><span class="sxs-lookup"><span data-stu-id="4bbc3-213">Automated investigation and response (AIR) in Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)
