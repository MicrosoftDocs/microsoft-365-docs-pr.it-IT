---
title: Profilo del dispositivo nel portale di sicurezza di Microsoft 365
description: Visualizzare i livelli di rischio e di esposizione per un dispositivo nell'organizzazione. Analizza le minacce passate e presenti e Proteggi il dispositivo con gli aggiornamenti più recenti.
keywords: sicurezza, malware, Microsoft 365, M365, Microsoft Threat Protection, MTP, Centro sicurezza, Microsoft Defender ATP, Office 365 ATP, Azure ATP, pagina dispositivo, profilo dispositivo, pagina computer, profilo macchina
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: v-maave
author: martyav
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.openlocfilehash: 3840a6beae3b586fc90420f7813ff6e9d3cc6c60
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843853"
---
# <a name="device-profile-page"></a><span data-ttu-id="59fd2-105">Pagina del profilo del dispositivo</span><span class="sxs-lookup"><span data-stu-id="59fd2-105">Device profile page</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="59fd2-106">Il portale di sicurezza di Microsoft 365 fornisce pagine del profilo del dispositivo, in modo da poter valutare rapidamente l'integrità e lo stato dei dispositivi sulla rete.</span><span class="sxs-lookup"><span data-stu-id="59fd2-106">The Microsoft 365 security portal provides you with device profile pages, so you can quickly assess the health and status of devices on your network.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="59fd2-107">La pagina del profilo del dispositivo può essere leggermente diversa, a seconda che il dispositivo sia registrato in Microsoft Defender per endpoint, Microsoft Defender per Identity o entrambi.</span><span class="sxs-lookup"><span data-stu-id="59fd2-107">The device profile page may appear slightly different, depending on whether the device is enrolled in Microsoft Defender for Endpoint, Microsoft Defender for Identity, or both.</span></span>

<span data-ttu-id="59fd2-108">Se il dispositivo è registrato in Microsoft Defender per endpoint, è possibile utilizzare anche la pagina del profilo del dispositivo per eseguire alcune attività di sicurezza comuni.</span><span class="sxs-lookup"><span data-stu-id="59fd2-108">If the device is enrolled in Microsoft Defender for Endpoint, you can also use the device profile page to perform some common security tasks.</span></span>

## <a name="navigating-the-device-profile-page"></a><span data-ttu-id="59fd2-109">Esplorazione della pagina del profilo del dispositivo</span><span class="sxs-lookup"><span data-stu-id="59fd2-109">Navigating the device profile page</span></span>

<span data-ttu-id="59fd2-110">La pagina del profilo è suddivisa in diverse sezioni.</span><span class="sxs-lookup"><span data-stu-id="59fd2-110">The profile page is broken up into several broad sections.</span></span>

![Immagine della pagina del profilo del dispositivo con (1) area della scheda (2) barra laterale e (3) azioni evidenziate in rosso](../../media/mtp-device-profile/hybrid-device-overall.png)

<span data-ttu-id="59fd2-112">La barra laterale (1) elenca i dettagli di base del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="59fd2-112">The sidebar (1) lists basic details about the device.</span></span>

<span data-ttu-id="59fd2-113">L'area di contenuto principale (2) contiene le schede che è possibile passare per visualizzare diversi tipi di informazioni sul dispositivo.</span><span class="sxs-lookup"><span data-stu-id="59fd2-113">The main content area (2) contains tabs that you can toggle through to view different kinds of information about the device.</span></span>

<span data-ttu-id="59fd2-114">Se il dispositivo è stato registrato in Microsoft Defender per endpoint, verrà visualizzato anche un elenco di azioni di risposta (3).</span><span class="sxs-lookup"><span data-stu-id="59fd2-114">If the device is enrolled in Microsoft Defender for Endpoint, you will also see a list of response actions (3).</span></span> <span data-ttu-id="59fd2-115">Le azioni di risposta consentono di eseguire attività comuni relative alla sicurezza.</span><span class="sxs-lookup"><span data-stu-id="59fd2-115">Response actions allow you to perform common security-related tasks.</span></span>

## <a name="sidebar"></a><span data-ttu-id="59fd2-116">Barra laterale</span><span class="sxs-lookup"><span data-stu-id="59fd2-116">Sidebar</span></span>

<span data-ttu-id="59fd2-117">Accanto all'area principale del contenuto della pagina del profilo del dispositivo si trova la barra laterale.</span><span class="sxs-lookup"><span data-stu-id="59fd2-117">Beside the main content area of the device profile page is the sidebar.</span></span>

![Immagine della scheda della barra laterale per il profilo del dispositivo](../../media/mtp-device-profile/azure-atp-only-device-sidebar.png)

<span data-ttu-id="59fd2-119">Nella barra laterale sono elencati il nome completo e il livello di esposizione del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="59fd2-119">The sidebar lists the device's full name and exposure level.</span></span> <span data-ttu-id="59fd2-120">Sono inoltre disponibili alcune importanti informazioni di base in piccole sottosezioni che possono essere attivate in modo aperto o chiuso, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="59fd2-120">It also provides some important basic information in small subsections which can be toggled open or closed, such as:</span></span>

* <span data-ttu-id="59fd2-121">**Tag** -qualsiasi Microsoft Defender per endpoint, Microsoft Defender per Identity o tag personalizzati associati al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="59fd2-121">**Tags** - Any Microsoft Defender for Endpoint, Microsoft Defender for Identity, or custom tags associated with the device.</span></span> <span data-ttu-id="59fd2-122">I tag di Microsoft Defender per Identity non sono modificabili.</span><span class="sxs-lookup"><span data-stu-id="59fd2-122">Tags from Microsoft Defender for Identity are not editable.</span></span>
* <span data-ttu-id="59fd2-123">**Info sulla sicurezza** -aprire gli incidenti e gli avvisi attivi.</span><span class="sxs-lookup"><span data-stu-id="59fd2-123">**Security info** - Open incidents and active alerts.</span></span> <span data-ttu-id="59fd2-124">I dispositivi registrati in Microsoft Defender per endpoint visualizzeranno anche il livello di esposizione e il livello di rischio.</span><span class="sxs-lookup"><span data-stu-id="59fd2-124">Devices enrolled in Microsoft Defender for Endpoint will also display exposure level and risk level.</span></span>

> [!TIP]
> <span data-ttu-id="59fd2-125">Il livello di esposizione si riferisce a quanto il dispositivo è conforme alle indicazioni sulla sicurezza, mentre il livello di rischio viene calcolato in base a una serie di fattori, tra cui i tipi e la gravità degli avvisi attivi.</span><span class="sxs-lookup"><span data-stu-id="59fd2-125">Exposure level relates to how much the device is complying with security recommendations, while risk level is calculated based on a number of factors, including the types and severity of active alerts.</span></span>

* <span data-ttu-id="59fd2-126">**Dettagli del dispositivo** : dominio, sistema operativo, timestamp per la prima volta che il dispositivo è stato visualizzato, indirizzi IP e risorse.</span><span class="sxs-lookup"><span data-stu-id="59fd2-126">**Device details** - Domain, OS, timestamp for when the device was first seen, IP addresses, resources.</span></span> <span data-ttu-id="59fd2-127">I dispositivi registrati in Microsoft Defender per endpoint visualizzano anche lo stato di integrità.</span><span class="sxs-lookup"><span data-stu-id="59fd2-127">Devices enrolled in Microsoft Defender for Endpoint also display health state.</span></span> <span data-ttu-id="59fd2-128">I dispositivi registrati in Microsoft Defender per Identity visualizzano il nome SAM e un timestamp per il momento in cui il dispositivo è stato creato.</span><span class="sxs-lookup"><span data-stu-id="59fd2-128">Devices enrolled in Microsoft Defender for Identity will display SAM name and a timestamp for when the device was first created.</span></span>
* <span data-ttu-id="59fd2-129">**Attività di rete** -timestamp per la prima volta e l'ultima volta che il dispositivo è stato visualizzato sulla rete.</span><span class="sxs-lookup"><span data-stu-id="59fd2-129">**Network activity** - Timestamps for the first time and last time the device was seen on the network.</span></span>
* <span data-ttu-id="59fd2-130">**Dati della directory** ( *solo per i dispositivi registrati in Microsoft Defender per Identity* ): flag del [controllo dell'account utente](https://docs.microsoft.com/windows/security/identity-protection/user-account-control/user-account-control-overview) , [nomi SPN](https://docs.microsoft.com/windows/win32/ad/service-principal-names)e appartenenze ai gruppi.</span><span class="sxs-lookup"><span data-stu-id="59fd2-130">**Directory data** ( *only for devices enrolled in Microsoft Defender for Identity* ) - [UAC](https://docs.microsoft.com/windows/security/identity-protection/user-account-control/user-account-control-overview) flags, [SPNs](https://docs.microsoft.com/windows/win32/ad/service-principal-names), and group memberships.</span></span>

## <a name="response-actions"></a><span data-ttu-id="59fd2-131">Azioni di risposta</span><span class="sxs-lookup"><span data-stu-id="59fd2-131">Response actions</span></span>

<span data-ttu-id="59fd2-132">Le azioni di risposta offrono una soluzione rapida per la difesa e l'analisi delle minacce.</span><span class="sxs-lookup"><span data-stu-id="59fd2-132">Response actions offer a quick way to defend against and analyze threats.</span></span>

![Immagine della barra delle azioni per il profilo del dispositivo](../../media/mtp-device-profile/hybrid-device-long-action-bar.png)

> [!IMPORTANT]
> * <span data-ttu-id="59fd2-134">Le [azioni di risposta](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts) sono disponibili solo se il dispositivo è stato registrato in Microsoft Defender per endpoint.</span><span class="sxs-lookup"><span data-stu-id="59fd2-134">[Response actions](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts) are only available if the device is enrolled in Microsoft Defender for Endpoint.</span></span>
> * <span data-ttu-id="59fd2-135">I dispositivi registrati in Microsoft Defender per endpoint possono visualizzare diversi numeri di azioni di risposta, in base al sistema operativo del dispositivo e al numero di versione.</span><span class="sxs-lookup"><span data-stu-id="59fd2-135">Devices that are enrolled in Microsoft Defender for Endpoint may display different numbers of response actions, based on the device's OS and version number.</span></span>

<span data-ttu-id="59fd2-136">Le azioni disponibili nella pagina del profilo del dispositivo includono:</span><span class="sxs-lookup"><span data-stu-id="59fd2-136">Actions available on the device profile page include:</span></span>

* <span data-ttu-id="59fd2-137">**Gestione tag** : consente di aggiornare i tag personalizzati applicati al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="59fd2-137">**Manage tags** - Updates custom tags you have applied to this device.</span></span>
* <span data-ttu-id="59fd2-138">**Isolate Device** -isola il dispositivo dalla rete dell'organizzazione mantenendo la connessione a Microsoft Defender per endpoint.</span><span class="sxs-lookup"><span data-stu-id="59fd2-138">**Isolate device** - Isolates the device from your organization's network while keeping it connected to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="59fd2-139">È possibile scegliere di consentire l'esecuzione di Outlook, teams e Skype for business mentre il dispositivo è isolato, a scopo di comunicazione.</span><span class="sxs-lookup"><span data-stu-id="59fd2-139">You can choose to allow Outlook, Teams, and Skype for Business to run while the device is isolated, for communication purposes.</span></span>
* <span data-ttu-id="59fd2-140">**Centro azioni** : visualizzare lo stato delle azioni inviate.</span><span class="sxs-lookup"><span data-stu-id="59fd2-140">**Action center** - View the status of submitted actions.</span></span> <span data-ttu-id="59fd2-141">Disponibile solo se è già stata selezionata un'altra azione.</span><span class="sxs-lookup"><span data-stu-id="59fd2-141">Only available if another action has already been selected.</span></span>
* <span data-ttu-id="59fd2-142">**Limitare l'esecuzione delle app** -impedisce l'esecuzione di applicazioni non firmate da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="59fd2-142">**Restrict app execution** - Prevents applications that are not signed by Microsoft from running.</span></span>
* <span data-ttu-id="59fd2-143">**Run Antivirus Scan** -aggiorna le definizioni di Windows Defender antivirus ed esegue immediatamente un'analisi antivirus.</span><span class="sxs-lookup"><span data-stu-id="59fd2-143">**Run antivirus scan** - Updates Windows Defender Antivirus definitions and immediately runs an antivirus scan.</span></span> <span data-ttu-id="59fd2-144">Scegliere tra analisi rapida o analisi completa.</span><span class="sxs-lookup"><span data-stu-id="59fd2-144">Choose between Quick scan or Full scan.</span></span>
* <span data-ttu-id="59fd2-145">**Raccolta del pacchetto di analisi** : raccoglie informazioni sul dispositivo.</span><span class="sxs-lookup"><span data-stu-id="59fd2-145">**Collect investigation package** - Gathers information about the device.</span></span> <span data-ttu-id="59fd2-146">Al termine dell'analisi, è possibile scaricarlo.</span><span class="sxs-lookup"><span data-stu-id="59fd2-146">When the investigation is completed, you can download it.</span></span>
* <span data-ttu-id="59fd2-147">**Avvio di Live Response Session** -carica una shell remota sul dispositivo per [indagini di sicurezza approfondite](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response).</span><span class="sxs-lookup"><span data-stu-id="59fd2-147">**Initiate Live Response Session** - Loads a remote shell on the device for [in-depth security investigations](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response).</span></span>
* <span data-ttu-id="59fd2-148">**Avviare l'analisi automatizzata** : consente [di analizzare e correggere automaticamente le minacce](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air).</span><span class="sxs-lookup"><span data-stu-id="59fd2-148">**Initiate automated investigation** - Automatically [investigates and remediates threats](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air).</span></span> <span data-ttu-id="59fd2-149">Anche se è possibile attivare manualmente le indagini automatizzate per l'esecuzione da questa pagina, [alcuni criteri di avviso](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?view=o365-worldwide#default-alert-policies) attivano le indagini automatiche in modo autonomo.</span><span class="sxs-lookup"><span data-stu-id="59fd2-149">Although you can manually trigger automated investigations to run from this page, [certain alert policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?view=o365-worldwide#default-alert-policies) trigger automatic investigations on their own.</span></span>
* <span data-ttu-id="59fd2-150">**Centro azioni** : consente di visualizzare le informazioni sulle azioni di risposta attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="59fd2-150">**Action center** - Displays information about any response actions that are currently running.</span></span>

## <a name="tabs-section"></a><span data-ttu-id="59fd2-151">Sezione tabulazioni</span><span class="sxs-lookup"><span data-stu-id="59fd2-151">Tabs section</span></span>

<span data-ttu-id="59fd2-152">Le schede profilo dispositivo consentono di passare attraverso una panoramica dei dettagli sulla sicurezza del dispositivo e delle tabelle contenenti un elenco di avvisi.</span><span class="sxs-lookup"><span data-stu-id="59fd2-152">The device profile tabs allow you to toggle through an overview of security details about the device, and tables containing a list of alerts.</span></span>

<span data-ttu-id="59fd2-153">I dispositivi registrati in Microsoft Defender per endpoint visualizzano anche le schede che dispongono di una sequenza temporale, un elenco di suggerimenti per la sicurezza, un inventario software, un elenco di vulnerabilità individuate e la KBs (aggiornamenti per la sicurezza) mancanti.</span><span class="sxs-lookup"><span data-stu-id="59fd2-153">Devices enrolled in Microsoft Defender for Endpoint will also display tabs that feature a timeline, a list of security recommendations, a software inventory, a list of discovered vulnerabilities, and missing KBs (security updates).</span></span>

### <a name="overview-tab"></a><span data-ttu-id="59fd2-154">Scheda Panoramica</span><span class="sxs-lookup"><span data-stu-id="59fd2-154">Overview tab</span></span>

<span data-ttu-id="59fd2-155">La scheda predefinita è **Overview**.</span><span class="sxs-lookup"><span data-stu-id="59fd2-155">The default tab is **Overview**.</span></span> <span data-ttu-id="59fd2-156">In questo modo viene fornita una rapida occhiata ai fatti di sicurezza più importanti per il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="59fd2-156">It provides a quick look at the most important security fact about the device.</span></span>

![Immagine della scheda Panoramica per il profilo del dispositivo](../../media/mtp-device-profile/hybrid-device-tab-overview.png)

<span data-ttu-id="59fd2-158">In questa sezione, è possibile consultare rapidamente gli avvisi attivi del dispositivo e tutti gli utenti attualmente connessi.</span><span class="sxs-lookup"><span data-stu-id="59fd2-158">Here, you can get a quick look at the device's active alerts, and any currently logged on users.</span></span>

<span data-ttu-id="59fd2-159">Se il dispositivo è registrato in Microsoft Defender per endpoint, verrà visualizzato anche il livello di rischio del dispositivo e tutti i dati disponibili sulle valutazioni di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="59fd2-159">If the device is enrolled in Microsoft Defender for Endpoint, you will also see the device's risk level and any available data on security assessments.</span></span> <span data-ttu-id="59fd2-160">Le valutazioni di sicurezza descrivono il livello di esposizione del dispositivo, forniscono suggerimenti per la sicurezza ed elenchino il software e le vulnerabilità individuate.</span><span class="sxs-lookup"><span data-stu-id="59fd2-160">The security assessments describe the device's exposure level, provide security recommendations, and list affected software and discovered vulnerabilities.</span></span>

### <a name="alerts-tab"></a><span data-ttu-id="59fd2-161">Scheda avvisi</span><span class="sxs-lookup"><span data-stu-id="59fd2-161">Alerts tab</span></span>

<span data-ttu-id="59fd2-162">La scheda **avvisi** contiene un elenco di avvisi che sono stati generati nel dispositivo, sia da Microsoft Defender per Identity che da Microsoft Defender per endpoint.</span><span class="sxs-lookup"><span data-stu-id="59fd2-162">The **Alerts** tab contains a list of alerts that have been raised on the device, from both Microsoft Defender for Identity and Microsoft Defender for Endpoint.</span></span>

![Immagine della scheda avvisi per il profilo del dispositivo](../../media/mtp-device-profile/hybrid-device-tab-alerts.png)

<span data-ttu-id="59fd2-164">È possibile personalizzare il numero di elementi visualizzati, nonché le colonne visualizzate per ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="59fd2-164">You can customize the number of items displayed, as well as which columns are displayed for each item.</span></span> <span data-ttu-id="59fd2-165">Il comportamento predefinito consiste nell'elencare trenta elementi per ogni pagina.</span><span class="sxs-lookup"><span data-stu-id="59fd2-165">The default behavior is to list thirty items per page.</span></span>

<span data-ttu-id="59fd2-166">Nelle colonne di questa scheda sono incluse informazioni sulla gravità del pericolo che ha attivato l'avviso, nonché lo stato, lo stato di indagine e l'utente a cui è stato assegnato l'avviso.</span><span class="sxs-lookup"><span data-stu-id="59fd2-166">The columns in this tab include information on the severity of the threat that triggered the alert, as well as status, investigation state, and who the alert has been assigned to.</span></span>

<span data-ttu-id="59fd2-167">La colonna *entità* interessate si riferisce al dispositivo (entità) il cui profilo si sta visualizzando, oltre a qualsiasi altro dispositivo della rete interessato.</span><span class="sxs-lookup"><span data-stu-id="59fd2-167">The *impacted entities* column refers to the device (entity) whose profile you are currently viewing, plus any other devices in your network that are affected.</span></span>

<span data-ttu-id="59fd2-168">Se si seleziona un elemento da questo elenco, verrà aperto un riquadro a comparsa contenente ulteriori informazioni sull'avviso selezionato.</span><span class="sxs-lookup"><span data-stu-id="59fd2-168">Selecting an item from this list will open a flyout containing even more information about the selected alert.</span></span>

<span data-ttu-id="59fd2-169">Questo elenco può essere filtrato in base alla gravità, allo stato o all'utente a cui è stato assegnato l'avviso.</span><span class="sxs-lookup"><span data-stu-id="59fd2-169">This list can be filtered by severity, status, or who the alert has been assigned to.</span></span>

### <a name="timeline-tab"></a><span data-ttu-id="59fd2-170">Scheda sequenza temporale</span><span class="sxs-lookup"><span data-stu-id="59fd2-170">Timeline tab</span></span>

<span data-ttu-id="59fd2-171">Nella scheda **sequenza temporale** è incluso un grafico cronologico interattivo di tutti gli eventi generati nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="59fd2-171">The **Timeline** tab includes an interactive, chronological chart of all events raised on the device.</span></span> <span data-ttu-id="59fd2-172">Spostando l'area evidenziata del grafico a sinistra o a destra, è possibile visualizzare gli eventi su diversi periodi di tempo.</span><span class="sxs-lookup"><span data-stu-id="59fd2-172">By moving the highlighted area of the chart left or right, you can view events over different periods of time.</span></span> <span data-ttu-id="59fd2-173">È anche possibile scegliere un intervallo di date personalizzato dal menu a discesa tra il grafico interattivo e l'elenco di eventi.</span><span class="sxs-lookup"><span data-stu-id="59fd2-173">You can also choose a custom range of dates from the dropdown menu in between the interactive chart and the list of events.</span></span>

<span data-ttu-id="59fd2-174">Di seguito è riportato un elenco di eventi per l'intervallo di date selezionato.</span><span class="sxs-lookup"><span data-stu-id="59fd2-174">Below the chart is a list of events for the selected range of dates.</span></span>

![Immagine della scheda sequenza temporale per il profilo del dispositivo](../../media/mtp-device-profile/hybrid-device-tab-timeline.png)

<span data-ttu-id="59fd2-176">È possibile personalizzare il numero di elementi visualizzati e le colonne dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="59fd2-176">The number of items displayed and the columns on the list can both be customized.</span></span> <span data-ttu-id="59fd2-177">Le colonne predefinite elencano l'ora dell'evento, l'utente attivo, il tipo di azione, le entità (processi) e altre informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="59fd2-177">The default columns list the event time, active user, action type, entities (processes), and additional information about the event.</span></span>

<span data-ttu-id="59fd2-178">Se si seleziona un elemento da questo elenco, verrà aperto un riquadro a comparsa che visualizza un grafico entità eventi, in cui vengono visualizzati i processi padre e figlio coinvolti nell'evento.</span><span class="sxs-lookup"><span data-stu-id="59fd2-178">Selecting an item from this list will open a flyout displaying an Event entities graph, showing the parent and child processes involved in the event.</span></span>

<span data-ttu-id="59fd2-179">L'elenco può essere filtrato in base al tipo di evento specifico. ad esempio, eventi del registro di sistema o eventi dello Smart Screen.</span><span class="sxs-lookup"><span data-stu-id="59fd2-179">The list can be filtered by the specific kind of event; for example, Registry events or Smart Screen Events.</span></span>

<span data-ttu-id="59fd2-180">L'elenco può anche essere esportato in un file CSV, per il download.</span><span class="sxs-lookup"><span data-stu-id="59fd2-180">The list can also be exported to a CSV file, for download.</span></span> <span data-ttu-id="59fd2-181">Anche se il file non è limitato in base al numero di eventi, l'intervallo di tempo massimo che è possibile scegliere di esportare è di sette giorni.</span><span class="sxs-lookup"><span data-stu-id="59fd2-181">Although the file is not limited by number of events, the maximum time range you can choose to export is seven days.</span></span>

### <a name="security-recommendations-tab"></a><span data-ttu-id="59fd2-182">Scheda suggerimenti per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="59fd2-182">Security recommendations tab</span></span>

<span data-ttu-id="59fd2-183">La scheda consigli per la **sicurezza** elenca le operazioni che è possibile eseguire per proteggere il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="59fd2-183">The **Security recommendations** tab lists actions you can take to protect the device.</span></span> <span data-ttu-id="59fd2-184">Se si seleziona un elemento di questo elenco, verrà aperto un riquadro a comparsa in cui è possibile ottenere istruzioni su come applicare il suggerimento.</span><span class="sxs-lookup"><span data-stu-id="59fd2-184">Selecting an item on this list will open a flyout where you can get instructions on how to apply the recommendation.</span></span>

![Immagine della scheda consigli per la sicurezza per il profilo del dispositivo](../../media/mtp-device-profile/hybrid-device-tab-security-recs.png)

<span data-ttu-id="59fd2-186">Come per le schede precedenti, il numero di elementi visualizzati per pagina, nonché le colonne visibili, può essere personalizzato.</span><span class="sxs-lookup"><span data-stu-id="59fd2-186">As with the previous tabs, the number of items displayed per page, as well as which columns are visible, can be customized.</span></span>

<span data-ttu-id="59fd2-187">La visualizzazione predefinita include colonne che illustrano in dettaglio le debolezze della sicurezza affrontate, la minaccia associata, il componente o il software correlato e altro.</span><span class="sxs-lookup"><span data-stu-id="59fd2-187">The default view includes columns that detail the security weaknesses addressed, the associated threat, the related component or software affected by the threat, and more.</span></span> <span data-ttu-id="59fd2-188">Gli elementi possono essere filtrati in base allo stato della raccomandazione.</span><span class="sxs-lookup"><span data-stu-id="59fd2-188">Items can be filtered by the recommendation's status.</span></span>

### <a name="software-inventory"></a><span data-ttu-id="59fd2-189">Inventario software</span><span class="sxs-lookup"><span data-stu-id="59fd2-189">Software inventory</span></span>

<span data-ttu-id="59fd2-190">Nella scheda **inventario software** sono elencati i software installati nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="59fd2-190">The **Software inventory** tab lists software installed on the device.</span></span>

![Immagine della scheda inventario software per il profilo del dispositivo](../../media/mtp-device-profile/hybrid-device-tab-software-inventory.png)

<span data-ttu-id="59fd2-192">La visualizzazione predefinita Visualizza il fornitore del software, il numero di versione installata, il numero di debolezze del software note, le informazioni sulle minacce, il codice prodotto e i tag.</span><span class="sxs-lookup"><span data-stu-id="59fd2-192">The default view displays the software vendor, installed version number, number of known software weaknesses, threat insights, product code, and tags.</span></span> <span data-ttu-id="59fd2-193">È possibile personalizzare il numero di elementi visualizzati e le colonne visualizzate.</span><span class="sxs-lookup"><span data-stu-id="59fd2-193">The number of items displayed and which columns are displayed can both be customized.</span></span>

<span data-ttu-id="59fd2-194">Se si seleziona un elemento da questo elenco, verrà aperto un riquadro a comparsa contenente ulteriori informazioni sul software selezionato, nonché il percorso e il timestamp per l'ultima volta che il software è stato trovato.</span><span class="sxs-lookup"><span data-stu-id="59fd2-194">Selecting an item from this list opens a flyout containing more details about the selected software, as well as the path and timestamp for the last time the software was found.</span></span>

<span data-ttu-id="59fd2-195">Questo elenco può essere filtrato in base al codice prodotto.</span><span class="sxs-lookup"><span data-stu-id="59fd2-195">This list can be filtered by product code.</span></span>

### <a name="discovered-vulnerabilities-tab"></a><span data-ttu-id="59fd2-196">Scheda vulnerabilità individuate</span><span class="sxs-lookup"><span data-stu-id="59fd2-196">Discovered vulnerabilities tab</span></span>

<span data-ttu-id="59fd2-197">La scheda **vulnerabilità individuata** elenca le vulnerabilità e gli exploit comuni (CVE) che possono influire sul dispositivo.</span><span class="sxs-lookup"><span data-stu-id="59fd2-197">The **Discovered vulnerabilities** tab lists any Common Vulnerabilities and Exploits (CVEs) that may affect the device.</span></span>

![Immagine della scheda vulnerabilità individuate per il profilo del dispositivo](../../media/mtp-device-profile/hybrid-device-tab-discovered-vulnerabilities.png)

<span data-ttu-id="59fd2-199">La visualizzazione predefinita elenca la gravità di CVE, il Punteggio di vulnerabilità comune (CVS), il software relativo a CVE, quando è stato pubblicato CVE, quando è stato aggiornato l'ultimo CVE e le minacce associate a CVE.</span><span class="sxs-lookup"><span data-stu-id="59fd2-199">The default view lists the severity of the CVE, the Common Vulnerability Score (CVS), the software related to the CVE, when the CVE was published, when the CVE was last updated, and threats associated with the CVE.</span></span>

<span data-ttu-id="59fd2-200">Come per le schede precedenti, è possibile personalizzare il numero di elementi visualizzati e le colonne visibili.</span><span class="sxs-lookup"><span data-stu-id="59fd2-200">As with the previous tabs, the number of items displayed and which columns are visible can be customized.</span></span>

<span data-ttu-id="59fd2-201">Se si seleziona un elemento da questo elenco, verrà aperto un riquadro a comparsa che descrive CVE.</span><span class="sxs-lookup"><span data-stu-id="59fd2-201">Selecting an item from this list will open a flyout that describes the CVE.</span></span>

### <a name="missing-kbs"></a><span data-ttu-id="59fd2-202">KBs mancante</span><span class="sxs-lookup"><span data-stu-id="59fd2-202">Missing KBs</span></span>

<span data-ttu-id="59fd2-203">La scheda **KBS mancante** elenca gli aggiornamenti di Microsoft che devono essere ancora applicati al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="59fd2-203">The **Missing KBs** tab lists any Microsoft Updates that have yet to be applied to the device.</span></span> <span data-ttu-id="59fd2-204">La "KBs" in questione sono [articoli della Knowledge base](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) che descrivono questi aggiornamenti; ad esempio, [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).</span><span class="sxs-lookup"><span data-stu-id="59fd2-204">The "KBs" in question are [Knowledge Base articles](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) which describe these updates; for example, [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).</span></span>

![Immagine della scheda KBS mancante per il profilo del dispositivo](../../media/mtp-device-profile/hybrid-device-tab-missing-kbs.PNG)

<span data-ttu-id="59fd2-206">La visualizzazione predefinita elenca il Bollettino contenente gli aggiornamenti, la versione del sistema operativo, i prodotti coinvolti, la CVE indirizzata, il numero di KB e i tag.</span><span class="sxs-lookup"><span data-stu-id="59fd2-206">The default view lists the bulletin containing the updates, OS version, products affected, CVEs addressed, the KB number, and tags.</span></span>

<span data-ttu-id="59fd2-207">Il numero di elementi visualizzati per pagina e quali colonne vengono visualizzate può essere personalizzato.</span><span class="sxs-lookup"><span data-stu-id="59fd2-207">The number of items displayed per page and which columns are displayed can be customized.</span></span>

<span data-ttu-id="59fd2-208">Se si seleziona un elemento, verrà aperto un riquadro a comparsa che si collega all'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="59fd2-208">Selecting an item will open a flyout that links to the update.</span></span>

## <a name="related-topics"></a><span data-ttu-id="59fd2-209">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="59fd2-209">Related topics</span></span>

* [<span data-ttu-id="59fd2-210">Panoramica di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="59fd2-210">Microsoft 365 Defender overview</span></span>](microsoft-threat-protection.md)
* [<span data-ttu-id="59fd2-211">Attiva Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="59fd2-211">Turn on Microsoft 365 Defender</span></span>](mtp-enable.md)
* [<span data-ttu-id="59fd2-212">Esaminare le entità nei dispositivi, utilizzando la risposta in tempo reale</span><span class="sxs-lookup"><span data-stu-id="59fd2-212">Investigate entities on devices, using live response</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)
* [<span data-ttu-id="59fd2-213">Indagine automatizzata e risposta (AIR) in Office 365</span><span class="sxs-lookup"><span data-stu-id="59fd2-213">Automated investigation and response (AIR) in Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)
