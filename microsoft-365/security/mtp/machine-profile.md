---
title: Profile del computer nel portale di sicurezza di Microsoft 365
description: Visualizzare i livelli di rischio e di esposizione per un dispositivo nell'organizzazione. Analizzare le minacce passate e presenti e proteggere il computer con gli aggiornamenti più recenti.
keywords: sicurezza, malware, Microsoft 365, M365, Microsoft Threat Protection, MTP, Centro sicurezza, Microsoft Defender ATP, Office 365 ATP, Azure ATP, Machine Page, Machine list, Machine profile
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
ms.openlocfilehash: 1dfb567c8e6b8573397d503ae27c0aceb447c916
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895464"
---
# <a name="machine-profile-page"></a><span data-ttu-id="2bb2e-105">Pagina del profilo del computer</span><span class="sxs-lookup"><span data-stu-id="2bb2e-105">Machine profile page</span></span>

<span data-ttu-id="2bb2e-106">Il portale di sicurezza di Microsoft 365 fornisce pagine del profilo del computer, in modo da poter valutare l'integrità e lo stato dei dispositivi sulla rete.</span><span class="sxs-lookup"><span data-stu-id="2bb2e-106">The Microsoft 365 security portal provides you with Machine profile pages, so you can assess the health and status of devices on your network.</span></span> <span data-ttu-id="2bb2e-107">Ogni pagina del profilo del computer contiene una vasta gamma di informazioni sul dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2bb2e-107">Each Machine profile page contains a wealth of information about the device.</span></span>

<span data-ttu-id="2bb2e-108">È possibile esaminare informazioni approfondite sul software in esecuzione, sugli eventi o gli avvisi di sicurezza precedenti e presenti e trovare collegamenti a patch software rilevanti.</span><span class="sxs-lookup"><span data-stu-id="2bb2e-108">You can review in-depth information about what software it is running, any past and present security events or alerts, and find links to relevant software patches.</span></span>

<span data-ttu-id="2bb2e-109">È inoltre possibile utilizzare il profilo del computer per eseguire attività comuni relative alla sicurezza e esaminare rapidamente i dettagli di base del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2bb2e-109">You can also use the Machine profile to perform common security-related tasks, and quickly review basic details about the device.</span></span>

## <a name="navigating-the-machine-profile-page"></a><span data-ttu-id="2bb2e-110">Esplorazione della pagina del profilo del computer</span><span class="sxs-lookup"><span data-stu-id="2bb2e-110">Navigating the Machine profile page</span></span>

<span data-ttu-id="2bb2e-111">La pagina del profilo del computer è suddivisa in tre sezioni.</span><span class="sxs-lookup"><span data-stu-id="2bb2e-111">The machine profile page is broken up into three sections.</span></span>

![Immagine della pagina del profilo del computer con (1) area della scheda (2) barra laterale e (3) azioni evidenziate in rosso](../../media/mtp-machine-profile/mtp-machine-profile-all.png)

<span data-ttu-id="2bb2e-113">L'area di contenuto principale (1) contiene sette schede che è possibile passare per visualizzare diversi tipi di informazioni sul computer.</span><span class="sxs-lookup"><span data-stu-id="2bb2e-113">The main content area (1) contains seven tabs that you can toggle through to view different kinds of information about the machine.</span></span>

<span data-ttu-id="2bb2e-114">La barra laterale (2) elenca i dettagli di base del computer.</span><span class="sxs-lookup"><span data-stu-id="2bb2e-114">The sidebar (2) lists basic details about the machine.</span></span>

<span data-ttu-id="2bb2e-115">Esistono anche azioni di risposta disponibili in un'intestazione (3) prima della barra laterale e delle sezioni principali del contenuto.</span><span class="sxs-lookup"><span data-stu-id="2bb2e-115">There are also response actions available in a header (3) before the sidebar and main content sections.</span></span> <span data-ttu-id="2bb2e-116">È possibile utilizzare le azioni in questa intestazione per eseguire attività comuni relative alla sicurezza.</span><span class="sxs-lookup"><span data-stu-id="2bb2e-116">You can use the actions in this header to perform common security-related tasks.</span></span>

## <a name="tabs-section"></a><span data-ttu-id="2bb2e-117">Sezione tabulazioni</span><span class="sxs-lookup"><span data-stu-id="2bb2e-117">Tabs section</span></span>

<span data-ttu-id="2bb2e-118">Le schede del profilo del computer consentono di alternare una panoramica dei dettagli sulla sicurezza del computer e delle tabelle che contengono un elenco di avvisi, una sequenza temporale, un elenco di suggerimenti per la sicurezza, un inventario software, un elenco di vulnerabilità individuate e mancanti KBs (aggiornamenti della sicurezza).</span><span class="sxs-lookup"><span data-stu-id="2bb2e-118">The Machine profile tabs allow you to toggle through an overview of security details about the machine, and tables containing a list of alerts, a timeline, a list of security recommendations, a software inventory, a list of discovered vulnerabilities, and missing KBs (security updates).</span></span>

### <a name="overview-tab"></a><span data-ttu-id="2bb2e-119">Scheda Panoramica</span><span class="sxs-lookup"><span data-stu-id="2bb2e-119">Overview tab</span></span>

<span data-ttu-id="2bb2e-120">La scheda predefinita è **Overview**.</span><span class="sxs-lookup"><span data-stu-id="2bb2e-120">The default tab is **Overview**.</span></span> <span data-ttu-id="2bb2e-121">In questo modo viene fornita una rapida occhiata ai fatti di sicurezza più importanti per il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2bb2e-121">It provides a quick look at the most important security fact about the device.</span></span>

![Immagine della scheda Panoramica per il profilo del computer](../../media/mtp-machine-profile/overview.png)

<span data-ttu-id="2bb2e-123">In questo articolo è possibile trovare un grafico del livello di rischio del dispositivo e gli avvisi attivi, tutti gli utenti attualmente connessi, un breve elenco di utenti più e meno frequenti e le valutazioni di sicurezza che illustrano il livello di esposizione del dispositivo, le raccomandazioni per la sicurezza, il software influenzato e vulnerabilità individuate.</span><span class="sxs-lookup"><span data-stu-id="2bb2e-123">Here, you can find a chart of the device's risk level and active alerts, any currently logged on users, a brief list of most and least frequent users, and security assessments that detail the device's exposure level, security recommendations, affected software, and discovered vulnerabilities.</span></span>

### <a name="alerts-tab"></a><span data-ttu-id="2bb2e-124">Scheda avvisi</span><span class="sxs-lookup"><span data-stu-id="2bb2e-124">Alerts tab</span></span>

<span data-ttu-id="2bb2e-125">La scheda **avvisi** contiene un elenco di avvisi che sono stati segnalati nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2bb2e-125">The **Alerts** tab contains a list of alerts that have been reported on the device.</span></span>

![Immagine della scheda avvisi per il profilo del computer](../../media/mtp-machine-profile/alerts.png)

<span data-ttu-id="2bb2e-127">È possibile personalizzare il numero di elementi visualizzati, nonché le colonne visualizzate per ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="2bb2e-127">You can customize the number of items displayed, as well as which columns are displayed for each item.</span></span> <span data-ttu-id="2bb2e-128">Il comportamento predefinito consiste nell'elencare 30 elementi per ogni pagina e con 11 colonne attivate per la visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="2bb2e-128">The default behavior is to list 30 items per page, and have 11 columns toggled on to display.</span></span>

<span data-ttu-id="2bb2e-129">Nelle colonne di questa scheda sono incluse informazioni sulla gravità del pericolo che ha attivato l'avviso, nonché lo stato, lo stato di indagine e l'utente a cui è stato assegnato l'avviso.</span><span class="sxs-lookup"><span data-stu-id="2bb2e-129">The columns in this tab include information on the severity of the threat that triggered the alert, as well as status, investigation state, and who if anyone the alert has been assigned to.</span></span>

<span data-ttu-id="2bb2e-130">La colonna *entità* interessate si riferisce al computer (entità) di cui è in corso la visualizzazione, oltre a qualsiasi altro computer della rete interessato.</span><span class="sxs-lookup"><span data-stu-id="2bb2e-130">The *impacted entities* column refers to the machine (entity) whose profile you are currently viewing, plus any other machines in your network that are affected.</span></span>

<span data-ttu-id="2bb2e-131">Se si seleziona un elemento da questo elenco, verrà aperto un collegamento all'avviso selezionato.</span><span class="sxs-lookup"><span data-stu-id="2bb2e-131">Selecting an item from this list will open a link to the selected alert.</span></span>

<span data-ttu-id="2bb2e-132">Questo elenco può essere filtrato in base a gravità, stato o assegnatario.</span><span class="sxs-lookup"><span data-stu-id="2bb2e-132">This list can be filtered by severity, status, or assignee.</span></span>

### <a name="timeline-tab"></a><span data-ttu-id="2bb2e-133">Scheda sequenza temporale</span><span class="sxs-lookup"><span data-stu-id="2bb2e-133">Timeline tab</span></span>

<span data-ttu-id="2bb2e-134">Nella scheda **sequenza temporale** è incluso un grafico cronologico interattivo degli eventi generati nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2bb2e-134">The **Timeline** tab includes a interactive, chronological chart of events raised on the device.</span></span> <span data-ttu-id="2bb2e-135">Spostando l'area evidenziata del grafico, è possibile visualizzare gli eventi su intervalli diversi di tempo.</span><span class="sxs-lookup"><span data-stu-id="2bb2e-135">By moving the highlighted area of the chart, you can view events over different ranges of time.</span></span> <span data-ttu-id="2bb2e-136">È inoltre possibile digitare un intervallo di date personalizzato.</span><span class="sxs-lookup"><span data-stu-id="2bb2e-136">You can also type in a custom range of dates.</span></span>

<span data-ttu-id="2bb2e-137">Di seguito è riportato un elenco di eventi per l'intervallo di date selezionato.</span><span class="sxs-lookup"><span data-stu-id="2bb2e-137">Below the chart is a list of events for the selected range of dates.</span></span>

![Immagine della scheda sequenza temporale per il profilo del computer](../../media/mtp-machine-profile/timeline.png)

<span data-ttu-id="2bb2e-139">È possibile personalizzare il numero di elementi visualizzati e le colonne dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="2bb2e-139">The number of items displayed and the columns on the list can both be customized.</span></span> <span data-ttu-id="2bb2e-140">Le colonne predefinite elencano l'ora dell'evento, l'utente attivo, il tipo di azione, le entità (processi) e altre informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="2bb2e-140">The default columns list the event time, active user, action type, entities (processes), and additional information about the event.</span></span>

<span data-ttu-id="2bb2e-141">Se si seleziona un elemento dall'elenco, verrà aperto un riquadro a comparsa che visualizza un grafico entità eventi, mostrando i processi padre e figlio che hanno attivato l'evento.</span><span class="sxs-lookup"><span data-stu-id="2bb2e-141">Selecting an item from the list will open a flyout displaying an Event entities graph, showing the parent and child processes that triggered the event.</span></span>

<span data-ttu-id="2bb2e-142">Questo elenco può essere filtrato in base al tipo di evento specifico. ad esempio, eventi del registro di sistema o eventi dello Smart Screen.</span><span class="sxs-lookup"><span data-stu-id="2bb2e-142">This list can be filtered by the specific kind of event; for example, Registry events or Smart Screen Events.</span></span>

### <a name="security-recommendations-tab"></a><span data-ttu-id="2bb2e-143">Scheda suggerimenti per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="2bb2e-143">Security recommendations tab</span></span>

<span data-ttu-id="2bb2e-144">La scheda consigli per la **sicurezza** elenca le operazioni che è possibile eseguire per proteggere il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2bb2e-144">The **Security recommendations** tab lists actions you can take to protect the device.</span></span> <span data-ttu-id="2bb2e-145">Se si seleziona un elemento di questo elenco, verrà aperto un riquadro a comparsa in cui è possibile ottenere istruzioni su come applicare il suggerimento.</span><span class="sxs-lookup"><span data-stu-id="2bb2e-145">Selecting an item on this list will open a flyout where you can get instructions on how to apply the recommendation.</span></span>

![Immagine della scheda consigli per la sicurezza per il profilo del computer](../../media/mtp-machine-profile/security-recs.png)

<span data-ttu-id="2bb2e-147">Come per le schede precedenti, è possibile personalizzare il numero di elementi visualizzati per pagina e le colonne visibili.</span><span class="sxs-lookup"><span data-stu-id="2bb2e-147">As with the previous tabs, the number of items displayed per page and which columns are visible can be customized.</span></span>

<span data-ttu-id="2bb2e-148">La visualizzazione predefinita include colonne che illustrano in dettaglio le debolezze della sicurezza affrontate, la minaccia associata, il componente o il software correlato e altro.</span><span class="sxs-lookup"><span data-stu-id="2bb2e-148">The default view includes columns that detail the security weaknesses addressed, the associated threat, the related component or software affected by the threat, and more.</span></span> <span data-ttu-id="2bb2e-149">Gli elementi possono essere filtrati in base allo stato della raccomandazione.</span><span class="sxs-lookup"><span data-stu-id="2bb2e-149">Items can be filtered by the recommendation's status.</span></span>

### <a name="software-inventory"></a><span data-ttu-id="2bb2e-150">Inventario software</span><span class="sxs-lookup"><span data-stu-id="2bb2e-150">Software inventory</span></span>

<span data-ttu-id="2bb2e-151">Nella scheda **inventario software** sono elencati i software installati nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2bb2e-151">The **Software inventory** tab lists software installed on the device.</span></span>

![Immagine della scheda inventario software per il profilo del computer](../../media/mtp-machine-profile/software-inventory.png)

<span data-ttu-id="2bb2e-153">La visualizzazione predefinita Visualizza il fornitore del software, il numero di versione installata, il numero di debolezze del software note, le informazioni sulle minacce, il codice prodotto e i tag.</span><span class="sxs-lookup"><span data-stu-id="2bb2e-153">The default view displays the software vendor, installed version number, number of known software weaknesses, threat insights, product code, and tags.</span></span> <span data-ttu-id="2bb2e-154">È possibile personalizzare il numero di elementi visualizzati e le colonne visualizzate.</span><span class="sxs-lookup"><span data-stu-id="2bb2e-154">The number of items displayed and which columns are displayed can both be customized.</span></span>

<span data-ttu-id="2bb2e-155">Se si seleziona un elemento da questo elenco, verrà aperto un riquadro a comparsa contenente ulteriori informazioni sul software selezionato, nonché il percorso e il timestamp per l'ultima volta che il software è stato trovato.</span><span class="sxs-lookup"><span data-stu-id="2bb2e-155">Selecting an item from this list opens a flyout containing more details about the selected software, as well as the path and timestamp for the last time the software was found.</span></span>

<span data-ttu-id="2bb2e-156">Questo elenco può essere filtrato in base al codice prodotto.</span><span class="sxs-lookup"><span data-stu-id="2bb2e-156">This list can be filtered by product code.</span></span>

### <a name="discovered-vulnerabilities-tab"></a><span data-ttu-id="2bb2e-157">Scheda vulnerabilità individuate</span><span class="sxs-lookup"><span data-stu-id="2bb2e-157">Discovered vulnerabilities tab</span></span>

<span data-ttu-id="2bb2e-158">La scheda **vulnerabilità individuata** elenca le vulnerabilità e gli exploit comuni (CVE) che possono influire sul dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2bb2e-158">The **Discovered vulnerabilities** tab lists any Common Vulnerabilities and Exploits (CVEs) that may affect the device.</span></span>

![Immagine della scheda vulnerabilità individuate per il profilo del computer](../../media/mtp-machine-profile/discovered-vulnerabilities.png)

<span data-ttu-id="2bb2e-160">La visualizzazione predefinita elenca la gravità di CVE, il Punteggio di vulnerabilità comune (CVS), il software relativo a CVE, quando è stato pubblicato CVE, quando è stato aggiornato l'ultimo CVE e le minacce associate a CVE.</span><span class="sxs-lookup"><span data-stu-id="2bb2e-160">The default view lists the severity of the CVE, the Common Vulnerability Score (CVS), the software related to the CVE, when the CVE was published, when the CVE was last updated, and threats associated with the CVE.</span></span>

<span data-ttu-id="2bb2e-161">Come per le schede precedenti, è possibile personalizzare il numero di elementi visualizzati e le colonne visibili.</span><span class="sxs-lookup"><span data-stu-id="2bb2e-161">As with the previous tabs, the number of items displayed and which columns are visible can be customized.</span></span>

<span data-ttu-id="2bb2e-162">Se si seleziona un elemento da questo elenco, verrà aperto un riquadro a comparsa che descrive CVE.</span><span class="sxs-lookup"><span data-stu-id="2bb2e-162">Selecting an item from this list will open a flyout that describes the CVE.</span></span>

### <a name="missing-kbs"></a><span data-ttu-id="2bb2e-163">KBs mancante</span><span class="sxs-lookup"><span data-stu-id="2bb2e-163">Missing KBs</span></span>

<span data-ttu-id="2bb2e-164">La scheda **KBS mancante** elenca gli aggiornamenti di Microsoft che devono essere ancora applicati al computer.</span><span class="sxs-lookup"><span data-stu-id="2bb2e-164">The **Missing KBs** tab lists any Microsoft Updates that have yet to be applied to the machine.</span></span> <span data-ttu-id="2bb2e-165">La "KBs" in questione sono [articoli della Knowledge base](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) che descrivono questi aggiornamenti; ad esempio, [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).</span><span class="sxs-lookup"><span data-stu-id="2bb2e-165">The "KBs" in question are [Knowledge Base articles](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) which describe these updates; for example, [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).</span></span>

![Immagine della scheda KBS mancante per il profilo del computer](../../media/mtp-machine-profile/missing-kbs.PNG)

<span data-ttu-id="2bb2e-167">La visualizzazione predefinita elenca il Bollettino contenente gli aggiornamenti, la versione del sistema operativo, i prodotti coinvolti, la CVE indirizzata, il numero di KB e i tag.</span><span class="sxs-lookup"><span data-stu-id="2bb2e-167">The default view lists the bulletin containing the updates, OS version, products affected, CVEs addressed, the KB number, and tags.</span></span>

<span data-ttu-id="2bb2e-168">Il numero di elementi visualizzati per pagina e quali colonne vengono visualizzate può essere personalizzato.</span><span class="sxs-lookup"><span data-stu-id="2bb2e-168">The number of items displayed per page and which columns are displayed can be customized.</span></span>

<span data-ttu-id="2bb2e-169">Se si seleziona un elemento, verrà aperto un riquadro a comparsa che si collega all'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="2bb2e-169">Selecting an item will open a flyout that links to the update.</span></span>

## <a name="sidebar"></a><span data-ttu-id="2bb2e-170">Barra laterale</span><span class="sxs-lookup"><span data-stu-id="2bb2e-170">Sidebar</span></span>

<span data-ttu-id="2bb2e-171">Accanto all'area di contenuto principale della pagina del profilo del computer è presente la barra laterale.</span><span class="sxs-lookup"><span data-stu-id="2bb2e-171">Beside the main content area of the Machine profile page is the sidebar.</span></span>

![Immagine della scheda barra laterale per il profilo del computer](../../media/mtp-machine-profile/sidebar.png)

<span data-ttu-id="2bb2e-173">La barra laterale fornisce alcune importanti informazioni di base in piccole sottosezioni che possono essere attivate in modo aperto o chiuso:</span><span class="sxs-lookup"><span data-stu-id="2bb2e-173">The sidebar provides some important basic information in small subsections which can be toggled open or closed:</span></span>

* <span data-ttu-id="2bb2e-174">**Tag** : tutti i tag associati al dispositivo</span><span class="sxs-lookup"><span data-stu-id="2bb2e-174">**Tags** - Any tags associated with the device</span></span>
* <span data-ttu-id="2bb2e-175">**Informazioni di sicurezza** : eventi di apertura, avvisi attivi, livello di esposizione e livello di rischio</span><span class="sxs-lookup"><span data-stu-id="2bb2e-175">**Security info** - Open incidents, active alerts, exposure level and risk level</span></span>
* <span data-ttu-id="2bb2e-176">**Dettagli del dispositivo** : dominio, sistema operativo, gruppo di risorse, stato di integrità, sensibilità ai dati e indirizzi IP</span><span class="sxs-lookup"><span data-stu-id="2bb2e-176">**Device details** - Domain, OS, Asset group, health state, data sensitivity, and IP addresses</span></span>
* <span data-ttu-id="2bb2e-177">**Attività di rete** -timestamp per la prima volta e l'ultima volta che il dispositivo è stato visualizzato sulla rete</span><span class="sxs-lookup"><span data-stu-id="2bb2e-177">**Network activity** - Timestamps for the first time and last time the device was seen on the network</span></span>

<span data-ttu-id="2bb2e-178">Questa sezione include anche il nome e il livello di esposizione del dispositivo e un'icona per indicare se è attualmente attiva sulla rete.</span><span class="sxs-lookup"><span data-stu-id="2bb2e-178">This section also includes the name and exposure level of the device, and an icon to indicate if it is currently active on the network.</span></span>

## <a name="response-actions"></a><span data-ttu-id="2bb2e-179">Azioni di risposta</span><span class="sxs-lookup"><span data-stu-id="2bb2e-179">Response actions</span></span>

<span data-ttu-id="2bb2e-180">Le azioni di risposta offrono una soluzione rapida per la difesa e l'analisi delle minacce.</span><span class="sxs-lookup"><span data-stu-id="2bb2e-180">Response actions offer a quick way to defend against and analyze threats.</span></span>

![Immagine della scheda barra laterale per il profilo del computer](../../media/mtp-machine-profile/actions.PNG)

<span data-ttu-id="2bb2e-182">Le azioni di risposta disponibili includono:</span><span class="sxs-lookup"><span data-stu-id="2bb2e-182">The response actions available to you here include:</span></span>

* <span data-ttu-id="2bb2e-183">**Gestione tag** : consente di aggiornare i tag personalizzati applicati al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2bb2e-183">**Manage tags** - Updates custom tags you have applied to this device.</span></span>
* <span data-ttu-id="2bb2e-184">**Isolate Machine** -consente di isolare il computer dalla rete dell'organizzazione mantenendo la connessione a Microsoft Defender Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="2bb2e-184">**Isolate machine** - Isolates the machine from your organization's network while keeping it connected to Microsoft Defender Advanced Threat Protection.</span></span> <span data-ttu-id="2bb2e-185">È possibile scegliere di consentire l'esecuzione di Outlook, teams e Skype for business mentre il computer è isolato, a scopo di comunicazione.</span><span class="sxs-lookup"><span data-stu-id="2bb2e-185">You can choose to allow Outlook, Teams, and Skype for Business to run while the machine is isolated, for communication purposes.</span></span>
* <span data-ttu-id="2bb2e-186">**Limitare l'esecuzione delle app** -impedisce l'esecuzione di applicazioni non firmate da Microsoft</span><span class="sxs-lookup"><span data-stu-id="2bb2e-186">**Restrict app execution** - Prevents applications that are not signed by Microsoft from running</span></span>
* <span data-ttu-id="2bb2e-187">**Run Antivirus Scan** -aggiorna le definizioni di Windows Defender antivirus ed esegue immediatamente un'analisi antivirus.</span><span class="sxs-lookup"><span data-stu-id="2bb2e-187">**Run antivirus scan** - Updates Windows Defender Antivirus definitions and immediately runs an antivirus scan.</span></span> <span data-ttu-id="2bb2e-188">Scegliere tra analisi rapida o analisi completa.</span><span class="sxs-lookup"><span data-stu-id="2bb2e-188">Choose between Quick scan or Full scan.</span></span>
* <span data-ttu-id="2bb2e-189">**Raccolta del pacchetto di analisi** : raccoglie informazioni sul computer.</span><span class="sxs-lookup"><span data-stu-id="2bb2e-189">**Collect investigation package** - Gathers information about the machine.</span></span> <span data-ttu-id="2bb2e-190">Al termine dell'analisi, è possibile scaricarlo.</span><span class="sxs-lookup"><span data-stu-id="2bb2e-190">When the investigation is completed, you can download it.</span></span>
* <span data-ttu-id="2bb2e-191">**Avvio di Live Response Session** -carica una shell remota sul computer per [indagini di sicurezza approfondite](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response).</span><span class="sxs-lookup"><span data-stu-id="2bb2e-191">**Initiate Live Response session** - Loads a remote shell on the machine for [in-depth security investigations](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response).</span></span>
* <span data-ttu-id="2bb2e-192">**Avviare l'analisi automatizzata** : consente [di analizzare e correggere automaticamente le minacce](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air).</span><span class="sxs-lookup"><span data-stu-id="2bb2e-192">**Initiate automated investigation** - Automatically [investigates and remediates threats](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air).</span></span> <span data-ttu-id="2bb2e-193">Anche se è possibile attivare manualmente le indagini automatizzate per l'esecuzione da questa pagina, [alcuni criteri di avviso](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?view=o365-worldwide#default-alert-policies) attivano le indagini automatiche in modo autonomo.</span><span class="sxs-lookup"><span data-stu-id="2bb2e-193">Although you can manually trigger automated investigations to run from this page, [certain alert policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?view=o365-worldwide#default-alert-policies) trigger automatic investigations on their own.</span></span>
* <span data-ttu-id="2bb2e-194">**Centro azioni** : visualizzare lo stato delle azioni inviate.</span><span class="sxs-lookup"><span data-stu-id="2bb2e-194">**Action center** - View the status of submitted actions.</span></span> <span data-ttu-id="2bb2e-195">Disponibile solo se è già stata selezionata un'altra azione.</span><span class="sxs-lookup"><span data-stu-id="2bb2e-195">Only available if another action has already been selected.</span></span>

## <a name="related-topics"></a><span data-ttu-id="2bb2e-196">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="2bb2e-196">Related topics</span></span>

* [<span data-ttu-id="2bb2e-197">Panoramica su Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="2bb2e-197">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
* [<span data-ttu-id="2bb2e-198">Attivare Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="2bb2e-198">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)
* [<span data-ttu-id="2bb2e-199">Esaminare le entità nei computer che utilizzano Live Response</span><span class="sxs-lookup"><span data-stu-id="2bb2e-199">Investigate entities on machines using live response</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)
* [<span data-ttu-id="2bb2e-200">Indagine automatizzata e risposta (AIR) in Office 365</span><span class="sxs-lookup"><span data-stu-id="2bb2e-200">Automated investigation and response (AIR) in Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)
