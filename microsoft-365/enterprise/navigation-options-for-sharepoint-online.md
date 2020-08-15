---
title: Opzioni di spostamento per SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 4/7/2020
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- SPO160
- MET150
ms.assetid: adb92b80-b342-4ecb-99a1-da2a2b4782eb
description: In questo articolo vengono descritti i siti delle opzioni di spostamento con la pubblicazione di SharePoint abilitata in SharePoint Online.
ms.openlocfilehash: 86cefc60a26687835fd6a88de7f249143811de4f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46696078"
---
# <a name="navigation-options-for-sharepoint-online"></a><span data-ttu-id="ef97b-103">Opzioni di spostamento per SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="ef97b-103">Navigation options for SharePoint Online</span></span>

<span data-ttu-id="ef97b-104">In questo articolo vengono descritti i siti delle opzioni di spostamento con la pubblicazione di SharePoint abilitata in SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="ef97b-104">This article describes navigation options sites with SharePoint Publishing enabled in SharePoint Online.</span></span> <span data-ttu-id="ef97b-105">La scelta e la configurazione della struttura di spostamento incidono in modo significativo sulle prestazioni e sulla scalabilità dei siti in SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="ef97b-105">The choice and configuration of navigation significantly impacts the performance and scalability of sites in SharePoint Online.</span></span> <span data-ttu-id="ef97b-106">Il modello di sito di pubblicazione di SharePoint deve essere utilizzato solo se necessario per un portale centralizzato e la funzionalità di pubblicazione deve essere abilitata solo in siti specifici e solo quando è assolutamente necessaria perché può influire sulle prestazioni se utilizzata in modo errato.</span><span class="sxs-lookup"><span data-stu-id="ef97b-106">The SharePoint Publishing site template should only be used if required for a centralized portal and the publishing feature should only be enabled on specific sites and only when absolutely required as it can impact performance when used incorrectly.</span></span>

>[!NOTE]
><span data-ttu-id="ef97b-107">Se si utilizzano le opzioni di spostamento di SharePoint moderne come menu Mega, spostamento a cascata o spostamento Hub, questo articolo non si applica al sito.</span><span class="sxs-lookup"><span data-stu-id="ef97b-107">If you're using modern SharePoint navigation options like mega menu, cascading navigation, or hub navigation, this article does not apply to your site.</span></span> <span data-ttu-id="ef97b-108">Le architetture di siti di SharePoint moderne sfruttano una gerarchia di siti più appiattita e un modello hub e spoke.</span><span class="sxs-lookup"><span data-stu-id="ef97b-108">Modern SharePoint site architectures leverage a more flattened site hierarchy and a hub-and-spoke model.</span></span> <span data-ttu-id="ef97b-109">In questo modo è possibile ottenere numerosi scenari che non richiedono l'utilizzo della caratteristica di pubblicazione di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ef97b-109">This allows many scenarios to be achieved that do NOT require use of the SharePoint Publishing feature.</span></span>

## <a name="overview-of-navigation-options"></a><span data-ttu-id="ef97b-110">Panoramica delle opzioni di spostamento</span><span class="sxs-lookup"><span data-stu-id="ef97b-110">Overview of navigation options</span></span>

<span data-ttu-id="ef97b-111">La configurazione del provider di spostamento può influire in modo significativo sulle prestazioni per l'intero sito e è necessario prendere in considerazione attentamente la scelta di un provider di spostamento e una configurazione in grado di ridimensionare efficacemente i requisiti di un sito di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ef97b-111">Navigation provider configuration can significantly impact performance for the entire site, and careful consideration must be taken to pick a navigation provider and configuration that scales effectively for the requirements of a SharePoint site.</span></span> <span data-ttu-id="ef97b-112">Sono disponibili due provider di spostamento fuori dalla casella, nonché implementazioni di spostamento personalizzate.</span><span class="sxs-lookup"><span data-stu-id="ef97b-112">There are two out-of-the-box navigation providers, as well as custom navigation implementations.</span></span>

<span data-ttu-id="ef97b-113">La prima opzione, la [**struttura di spostamento strutturale**](#using-structural-navigation-in-sharepoint-online), è l'opzione di spostamento consigliata in SharePoint Online per i siti di SharePoint classici, **se si attiva la memorizzazione nella cache di spostamento strutturale per il sito**.</span><span class="sxs-lookup"><span data-stu-id="ef97b-113">The first option, [**Structural navigation**](#using-structural-navigation-in-sharepoint-online), is the recommended navigation option in SharePoint Online for classic Sharepoint sites, **if you turn on structural navigation caching for your site**.</span></span> <span data-ttu-id="ef97b-114">In questo provider di spostamento vengono visualizzate le voci di spostamento al di sotto del sito corrente e, facoltativamente, il sito corrente e i relativi elementi di pari livello.</span><span class="sxs-lookup"><span data-stu-id="ef97b-114">This navigation provider displays the navigation items below the current site, and optionally the current site and its siblings.</span></span> <span data-ttu-id="ef97b-115">Offre funzionalità aggiuntive quali la limitazione della sicurezza e l'enumerazione della struttura del sito.</span><span class="sxs-lookup"><span data-stu-id="ef97b-115">It provides additional capabilities such as security trimming and site structure enumeration.</span></span> <span data-ttu-id="ef97b-116">Se la memorizzazione nella cache è disattivata, questo influirà negativamente sulle prestazioni e la scalabilità e potrebbe essere soggetta a limitazione.</span><span class="sxs-lookup"><span data-stu-id="ef97b-116">If caching is disabled, this will negatively impact performance and scalability, and may be subject to throttling.</span></span>

<span data-ttu-id="ef97b-117">La seconda opzione, [**spostamento gestito (metadati)**](#using-managed-navigation-and-metadata-in-sharepoint-online), rappresenta gli elementi di spostamento utilizzando un set di termini metadati gestiti.</span><span class="sxs-lookup"><span data-stu-id="ef97b-117">The second option, [**Managed (Metadata) navigation**](#using-managed-navigation-and-metadata-in-sharepoint-online), represents navigation items using a Managed Metadata term set.</span></span> <span data-ttu-id="ef97b-118">È consigliabile disabilitare la riduzione della sicurezza a meno che non sia necessario.</span><span class="sxs-lookup"><span data-stu-id="ef97b-118">We recommend that security trimming be disabled unless required.</span></span> <span data-ttu-id="ef97b-119">La limitazione di sicurezza è abilitata come impostazione di protezione per il provider di spostamento. Tuttavia, molti siti non richiedono il sovraccarico della limitazione di sicurezza poiché gli elementi di spostamento spesso sono coerenti per tutti gli utenti del sito.</span><span class="sxs-lookup"><span data-stu-id="ef97b-119">Security trimming is enabled as a secure-by-default setting for this navigation provider; however, many sites do not require the overhead of security trimming since navigation elements often are consistent for all users of the site.</span></span> <span data-ttu-id="ef97b-120">Con la configurazione consigliata per disabilitare la limitazione di sicurezza, questo provider di spostamento non richiede l'enumerazione della struttura del sito ed è altamente scalabile con un impatto sulle prestazioni accettabile.</span><span class="sxs-lookup"><span data-stu-id="ef97b-120">With the recommended configuration to disable security trimming, this navigation provider does not require enumerating site structure and is highly scalable with acceptable performance impact.</span></span>

<span data-ttu-id="ef97b-121">Oltre ai provider di spostamento fuori campo, molti clienti hanno implementato con successo implementazioni di spostamento personalizzate alternative.</span><span class="sxs-lookup"><span data-stu-id="ef97b-121">In addition to the out-of-the-box navigation providers, many customers have successfully implemented alternative custom navigation implementations.</span></span> <span data-ttu-id="ef97b-122">Vedere [scripting sul fianco client](#using-search-driven-client-side-scripting) basato sulla ricerca in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="ef97b-122">See [Search-driven client-side scripting](#using-search-driven-client-side-scripting) in this article.</span></span>
  
## <a name="pros-and-cons-of-sharepoint-online-navigation-options"></a><span data-ttu-id="ef97b-123">Vantaggi e svantaggi delle opzioni di spostamento di SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="ef97b-123">Pros and Cons of SharePoint Online navigation options</span></span>

<span data-ttu-id="ef97b-124">Nella tabella seguente sono riepilogati i vantaggi e gli svantaggi di ogni opzione.</span><span class="sxs-lookup"><span data-stu-id="ef97b-124">The following table summarizes the pros and cons of each option.</span></span>

|<span data-ttu-id="ef97b-125">Esplorazione strutturale</span><span class="sxs-lookup"><span data-stu-id="ef97b-125">Structural navigation</span></span>  |<span data-ttu-id="ef97b-126">Esplorazione gestita</span><span class="sxs-lookup"><span data-stu-id="ef97b-126">Managed navigation</span></span>  |<span data-ttu-id="ef97b-127">Esplorazione basata sulla ricerca</span><span class="sxs-lookup"><span data-stu-id="ef97b-127">Search-driven navigation</span></span>  |<span data-ttu-id="ef97b-128">Provider di spostamento personalizzato</span><span class="sxs-lookup"><span data-stu-id="ef97b-128">Custom-navigation provider</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="ef97b-129">Professionisti</span><span class="sxs-lookup"><span data-stu-id="ef97b-129">Pros:</span></span><br/><br/><span data-ttu-id="ef97b-130">Facile da gestire</span><span class="sxs-lookup"><span data-stu-id="ef97b-130">Easy to maintain</span></span><br/><span data-ttu-id="ef97b-131">Protezione ritagliata</span><span class="sxs-lookup"><span data-stu-id="ef97b-131">Security trimmed</span></span><br/><span data-ttu-id="ef97b-132">Viene aggiornato automaticamente entro 24 ore dal momento in cui viene modificato il contenuto</span><span class="sxs-lookup"><span data-stu-id="ef97b-132">Automatically updates within 24 hours when content is changed</span></span><br/>     |<span data-ttu-id="ef97b-133">Professionisti</span><span class="sxs-lookup"><span data-stu-id="ef97b-133">Pros:</span></span><br/><br/><span data-ttu-id="ef97b-134">Facile da gestire</span><span class="sxs-lookup"><span data-stu-id="ef97b-134">Easy to maintain</span></span><br/>|<span data-ttu-id="ef97b-135">Professionisti</span><span class="sxs-lookup"><span data-stu-id="ef97b-135">Pros:</span></span><br/><br/><span data-ttu-id="ef97b-136">Protezione ritagliata</span><span class="sxs-lookup"><span data-stu-id="ef97b-136">Security trimmed</span></span><br/><span data-ttu-id="ef97b-137">Si aggiorna automaticamente man mano che i siti vengono aggiunti</span><span class="sxs-lookup"><span data-stu-id="ef97b-137">Automatically updates as sites are added</span></span><br/><span data-ttu-id="ef97b-138">Tempo di caricamento rapido e struttura dell'esplorazione memorizzata nella cache</span><span class="sxs-lookup"><span data-stu-id="ef97b-138">Fast loading time and locally cached navigation structure</span></span><br/>|<span data-ttu-id="ef97b-139">Professionisti</span><span class="sxs-lookup"><span data-stu-id="ef97b-139">Pros:</span></span><br/><br/><span data-ttu-id="ef97b-140">Scelta più ampia di opzioni disponibili</span><span class="sxs-lookup"><span data-stu-id="ef97b-140">Wider choice of options available</span></span><br/><span data-ttu-id="ef97b-141">Caricamento veloce quando la memorizzazione nella cache viene utilizzata correttamente</span><span class="sxs-lookup"><span data-stu-id="ef97b-141">Fast loading when caching is used correctly</span></span><br/><span data-ttu-id="ef97b-142">Molte opzioni funzionano bene con la progettazione delle pagine reattive</span><span class="sxs-lookup"><span data-stu-id="ef97b-142">Many options work well with responsive page design</span></span><br/>|
|<span data-ttu-id="ef97b-143">Contro</span><span class="sxs-lookup"><span data-stu-id="ef97b-143">Cons:</span></span><br/><br/><span data-ttu-id="ef97b-144">**Impatto delle prestazioni se la memorizzazione nella cache è disabilitata**</span><span class="sxs-lookup"><span data-stu-id="ef97b-144">**Impacts performance if caching is disabled**</span></span><br/><span data-ttu-id="ef97b-145">Soggette a limitazione</span><span class="sxs-lookup"><span data-stu-id="ef97b-145">Subject to throttling</span></span><br/>|<span data-ttu-id="ef97b-146">Contro</span><span class="sxs-lookup"><span data-stu-id="ef97b-146">Cons:</span></span><br/><br/><span data-ttu-id="ef97b-147">Non si aggiorna automaticamente per riflettere la struttura del sito</span><span class="sxs-lookup"><span data-stu-id="ef97b-147">Not automatically updated to reflect site structure</span></span><br/><span data-ttu-id="ef97b-148">**Impatto delle prestazioni se la limitazione di sicurezza è abilitata** o quando la struttura di spostamento è complessa</span><span class="sxs-lookup"><span data-stu-id="ef97b-148">**Impacts performance if security trimming is enabled** or when navigation structure is complex</span></span><br/>|<span data-ttu-id="ef97b-149">Contro</span><span class="sxs-lookup"><span data-stu-id="ef97b-149">Cons:</span></span><br/><br/><span data-ttu-id="ef97b-150">Non è possibile ordinare facilmente i siti</span><span class="sxs-lookup"><span data-stu-id="ef97b-150">No ability to easily order sites</span></span><br/><span data-ttu-id="ef97b-151">Richiede la personalizzazione della pagina master (necessarie competenze tecniche)</span><span class="sxs-lookup"><span data-stu-id="ef97b-151">Requires customization of the master page (technical skills required)</span></span><br/>|<span data-ttu-id="ef97b-152">Contro</span><span class="sxs-lookup"><span data-stu-id="ef97b-152">Cons:</span></span><br/><br/><span data-ttu-id="ef97b-153">Lo sviluppo personalizzato è obbligatorio</span><span class="sxs-lookup"><span data-stu-id="ef97b-153">Custom development is required</span></span><br/><span data-ttu-id="ef97b-154">L'origine dati esterna/cache memorizzata è necessaria ad esempio Azure</span><span class="sxs-lookup"><span data-stu-id="ef97b-154">External data source / cache stored is needed e.g. Azure</span></span><br/>|

<span data-ttu-id="ef97b-155">L'opzione più appropriata per il sito dipende dai requisiti del sito e dalle proprie capacità tecniche.</span><span class="sxs-lookup"><span data-stu-id="ef97b-155">The most appropriate option for your site will depend on your site requirements and on your technical capability.</span></span> <span data-ttu-id="ef97b-156">Se si desidera un provider di spostamento di facile configurazione che si aggiorna automaticamente quando il contenuto viene modificato, la struttura [di spostamento strutturale con memorizzazione nella cache abilitata](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43) è una buona opzione.</span><span class="sxs-lookup"><span data-stu-id="ef97b-156">If you want an easy-to-configure navigation provider that automatically updates when content is changed, then structural navigation [with caching enabled](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43) is a good option.</span></span>

>[!NOTE]
><span data-ttu-id="ef97b-157">Se si applica lo stesso principio dei siti di SharePoint moderni semplificando la struttura complessiva del sito a una struttura più piatta e non gerarchica, le prestazioni vengono semplificate e il passaggio a siti di SharePoint moderni è più semplice.</span><span class="sxs-lookup"><span data-stu-id="ef97b-157">Applying the same principle as modern SharePoint sites by simplifying the overall site structure to a flatter, non-hierarchical structure improves performance and simplifies moving to modern SharePoint sites.</span></span> <span data-ttu-id="ef97b-158">Ciò significa che, invece di disporre di una singola raccolta siti con centinaia di Site (Web secondari), un approccio migliore consiste nell'avere molte raccolte siti con pochissimi sottositi (Web secondari).</span><span class="sxs-lookup"><span data-stu-id="ef97b-158">What this means is that instead of having a single site collection with hundreds of sites (subwebs), a better approach is to have many site collections with very few subsites (subwebs).</span></span>

## <a name="analyzing-navigation-performance-in-sharepoint-online"></a><span data-ttu-id="ef97b-159">Analisi delle prestazioni di spostamento in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="ef97b-159">Analyzing navigation performance in SharePoint Online</span></span>

<span data-ttu-id="ef97b-160">Lo [strumento page Diagnostics for SharePoint](https://aka.ms/perftool) è un'estensione del browser per i browser Microsoft Edge e Chrome che analizzano sia il portale moderno di SharePoint Online che le pagine del sito di pubblicazione classiche.</span><span class="sxs-lookup"><span data-stu-id="ef97b-160">The [Page Diagnostics for SharePoint tool](https://aka.ms/perftool) is a browser extension for Microsoft Edge and Chrome browsers that analyzes both SharePoint Online modern portal and classic publishing site pages.</span></span> <span data-ttu-id="ef97b-161">Questo strumento funziona solo per SharePoint Online e non può essere utilizzato in una pagina di sistema di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ef97b-161">This tool only works for SharePoint Online, and cannot be used on a SharePoint system page.</span></span>

<span data-ttu-id="ef97b-162">Lo strumento genera un rapporto per ogni pagina analizzata che mostra la modalità di esecuzione della pagina in base a un set di regole predefinito e visualizza informazioni dettagliate quando i risultati di un test non rientrano nel valore previsto.</span><span class="sxs-lookup"><span data-stu-id="ef97b-162">The tool generates a report for each analyzed page showing how the page performs against a pre-defined set of rules and displays detailed information when results for a test fall outside the baseline value.</span></span> <span data-ttu-id="ef97b-163">Gli amministratori e i progettisti di SharePoint Online possono utilizzare lo strumento per risolvere i problemi relativi alle prestazioni per garantire che le nuove pagine vengano ottimizzate prima della pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="ef97b-163">SharePoint Online administrators and designers can use the tool to troubleshoot performance issues to ensure that new pages are optimized prior to publishing.</span></span>

<span data-ttu-id="ef97b-164">**SPRequestDuration** in particolare è il tempo necessario per l'elaborazione della pagina da parte di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ef97b-164">**SPRequestDuration** in particular is the time it takes for SharePoint to process the page.</span></span> <span data-ttu-id="ef97b-165">La navigazione pesante (come ad esempio le pagine in navigazione), le gerarchie di siti complesse e altre opzioni di configurazione e topologia possono contribuire in modo significativo a una durata più lunga.</span><span class="sxs-lookup"><span data-stu-id="ef97b-165">Heavy navigation (like including pages in navigation), complex site hierarchies, and other configuration and topology options can all dramatically contribute to longer durations.</span></span>

## <a name="using-structural-navigation-in-sharepoint-online"></a><span data-ttu-id="ef97b-166">Utilizzo dell'esplorazione strutturale in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="ef97b-166">Using structural navigation in SharePoint Online</span></span>

<span data-ttu-id="ef97b-167">Questa è la struttura di spostamento fuori campo utilizzata per impostazione predefinita ed è la soluzione più semplice.</span><span class="sxs-lookup"><span data-stu-id="ef97b-167">This is the out-of-the-box navigation used by default and is the most straightforward solution.</span></span> <span data-ttu-id="ef97b-168">Non richiede alcuna personalizzazione e un utente non tecnico può anche aggiungere facilmente elementi, nascondere gli elementi e gestire la struttura di spostamento dalla pagina impostazioni.</span><span class="sxs-lookup"><span data-stu-id="ef97b-168">It does not require any customization and a non-technical user can also easily add items, hide items, and manage the navigation from the settings page.</span></span> <span data-ttu-id="ef97b-169">Si consiglia di [abilitare la memorizzazione nella cache](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43), altrimenti si verifica un costo elevato delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="ef97b-169">We recommend [enabling caching](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43), otherwise there is an expensive performance trade-off.</span></span>

### <a name="how-to-implement-structural-navigation-caching"></a><span data-ttu-id="ef97b-170">Informazioni su come implementare la memorizzazione nella cache di spostamento strutturale</span><span class="sxs-lookup"><span data-stu-id="ef97b-170">How to implement structural navigation caching</span></span>

<span data-ttu-id="ef97b-171">In **Impostazioni sito**  >  **aspetto**di  >  **spostamento**, è possibile convalidare se l'esplorazione strutturale è selezionata per la struttura di spostamento globale o di spostamento corrente.</span><span class="sxs-lookup"><span data-stu-id="ef97b-171">Under **Site Settings** > **Look and Feel** > **Navigation**, you can validate if structural navigation is selected for either global navigation or current navigation.</span></span> <span data-ttu-id="ef97b-172">La selezione di **Mostra pagine** avrà un impatto negativo sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="ef97b-172">Selecting **Show pages** will have negative impact on performance.</span></span>

![Struttura di spostamento strutturale con i siti secondari visualizzati selezionati](../media/SPONavOptionsStructuredShowSubsites.png)

<span data-ttu-id="ef97b-174">La memorizzazione nella cache può essere abilitata o disabilitata a livello di raccolta siti e a livello di sito ed è abilitata per entrambi per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="ef97b-174">Caching can be enabled or disabled at the site collection level and at the site level, and is enabled for both by default.</span></span> <span data-ttu-id="ef97b-175">Per abilitare a livello di raccolta siti, in esplorazione raccolta siti di Amministrazione raccolta siti **Impostazioni sito**  >  **Site Collection Administration**  >  **Site Collection Navigation**selezionare la casella per **abilitare la memorizzazione nella cache**.</span><span class="sxs-lookup"><span data-stu-id="ef97b-175">To enable at the site collection level, under **Site Settings** > **Site Collection Administration** > **Site Collection Navigation**, check the box for **Enable caching**.</span></span>

![Abilitare la memorizzazione nella cache a livello di sito](../media/structural-nav/structural-nav-caching-site-coll.png)

<span data-ttu-id="ef97b-177">Per abilitare a livello di sito, in **spostamento Impostazioni sito**  >  **Navigation**selezionare la casella per **abilitare la memorizzazione nella cache**.</span><span class="sxs-lookup"><span data-stu-id="ef97b-177">To enable at the site level, under **Site Settings** > **Navigation**, check the box for **Enable caching**.</span></span>

![Abilitare la memorizzazione nella cache a livello di sito](../media/structural-nav/structural-nav-caching-site.png)

## <a name="using-managed-navigation-and-metadata-in-sharepoint-online"></a><span data-ttu-id="ef97b-179">Utilizzo dell'esplorazione e dei metadati gestiti in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="ef97b-179">Using managed navigation and metadata in SharePoint Online</span></span>

<span data-ttu-id="ef97b-180">L'esplorazione gestita è un'altra opzione che è possibile utilizzare per ricreare la maggior parte delle stesse funzionalità della struttura di spostamento strutturale.</span><span class="sxs-lookup"><span data-stu-id="ef97b-180">Managed navigation is another out-of-the-box option that you can use to recreate most of the same functionality as structural navigation.</span></span> <span data-ttu-id="ef97b-181">I metadati gestiti possono essere configurati in modo da abilitare o disabilitare la limitazione di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="ef97b-181">Managed metadata can be configured to have security trimming enabled or disabled.</span></span> <span data-ttu-id="ef97b-182">Una volta configurata con la limitazione della sicurezza disabilitata, l'esplorazione gestita è piuttosto efficiente poiché carica tutti i collegamenti di spostamento con un numero costante di chiamate del server.</span><span class="sxs-lookup"><span data-stu-id="ef97b-182">When configured with security trimming disabled, managed navigation is fairly efficient as it loads all the navigation links with a constant number of server calls.</span></span> <span data-ttu-id="ef97b-183">L'abilitazione della limitazione della sicurezza, tuttavia, nega alcuni dei vantaggi delle prestazioni dell'esplorazione gestita.</span><span class="sxs-lookup"><span data-stu-id="ef97b-183">Enabling security trimming, however, negates some of the performance advantages of managed navigation.</span></span>

<span data-ttu-id="ef97b-184">Se è necessario abilitare la limitazione della sicurezza, è consigliabile:</span><span class="sxs-lookup"><span data-stu-id="ef97b-184">If you need to enable security trimming, we recommend that you:</span></span>

- <span data-ttu-id="ef97b-185">Aggiornare tutti i collegamenti a collegamenti semplici tramite URL</span><span class="sxs-lookup"><span data-stu-id="ef97b-185">Update all friendly URL links to simple links</span></span>
- <span data-ttu-id="ef97b-186">Aggiungere nodi di ritaglio di sicurezza richiesti come URL descrittivi</span><span class="sxs-lookup"><span data-stu-id="ef97b-186">Add required security trimming nodes as friendly URLs</span></span>
- <span data-ttu-id="ef97b-187">Limitare il numero di elementi di spostamento a un massimo di 100 e non più di 3 livelli di profondità</span><span class="sxs-lookup"><span data-stu-id="ef97b-187">Limit the number of navigation items to no more than 100 and no more than 3 levels deep</span></span>

<span data-ttu-id="ef97b-188">Molti siti non richiedono la limitazione della sicurezza, in quanto la struttura di spostamento è spesso coerente per tutti gli utenti del sito.</span><span class="sxs-lookup"><span data-stu-id="ef97b-188">Many sites do not require security trimming, as the navigation structure is often consistent for all users of the site.</span></span> <span data-ttu-id="ef97b-189">Se la limitazione di sicurezza è disabilitata e viene aggiunto un collegamento alla struttura di spostamento a cui non è consentito l'accesso a tutti gli utenti, il collegamento verrà comunque visualizzato, ma comporterà un messaggio di accesso negato.</span><span class="sxs-lookup"><span data-stu-id="ef97b-189">If security trimming is disabled and a link is added to navigation that not all users have access to, the link will still show but will lead to an access denied message.</span></span> <span data-ttu-id="ef97b-190">Non vi è alcun rischio di accesso involontario al contenuto.</span><span class="sxs-lookup"><span data-stu-id="ef97b-190">There is no risk of inadvertent access to the content.</span></span>

### <a name="how-to-implement-managed-navigation-and-the-results"></a><span data-ttu-id="ef97b-191">Come implementare l'esplorazione gestita e i risultati</span><span class="sxs-lookup"><span data-stu-id="ef97b-191">How to implement managed navigation and the results</span></span>

<span data-ttu-id="ef97b-192">Sono disponibili numerosi articoli su docs.microsoft.com per i dettagli relativi all'esplorazione gestita.</span><span class="sxs-lookup"><span data-stu-id="ef97b-192">There are several articles on docs.microsoft.com about the details of managed navigation.</span></span> <span data-ttu-id="ef97b-193">Ad esempio, vedere [Overview of Managed Navigation in SharePoint Server](https://docs.microsoft.com/sharepoint/administration/overview-of-managed-navigation).</span><span class="sxs-lookup"><span data-stu-id="ef97b-193">For example, see [Overview of managed navigation in SharePoint Server](https://docs.microsoft.com/sharepoint/administration/overview-of-managed-navigation).</span></span>

<span data-ttu-id="ef97b-194">Per implementare l'esplorazione gestita, è necessario configurare i termini con gli URL corrispondenti alla struttura di spostamento del sito.</span><span class="sxs-lookup"><span data-stu-id="ef97b-194">In order to implement managed navigation, you set up terms with URLs corresponding to the navigation structure of the site.</span></span> <span data-ttu-id="ef97b-195">L'esplorazione gestita può anche essere curata manualmente per sostituire la struttura di spostamento strutturale in molti casi.</span><span class="sxs-lookup"><span data-stu-id="ef97b-195">Managed navigation can even be manually curated to replace structural navigation in many cases.</span></span> <span data-ttu-id="ef97b-196">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="ef97b-196">For example:</span></span>

![Struttura del sito di SharePoint Online](../media/SPONavOptionsListOfSites.png)<span data-ttu-id="ef97b-198">)</span><span class="sxs-lookup"><span data-stu-id="ef97b-198">)</span></span>

## <a name="using-search-driven-client-side-scripting"></a><span data-ttu-id="ef97b-199">Utilizzo di script sul lato client basato sulla ricerca</span><span class="sxs-lookup"><span data-stu-id="ef97b-199">Using Search-driven client-side scripting</span></span>

<span data-ttu-id="ef97b-200">Una classe comune di implementazioni di spostamento personalizzate abbraccia modelli di progettazione con rendering client che archiviano una cache locale dei nodi di spostamento.</span><span class="sxs-lookup"><span data-stu-id="ef97b-200">One common class of custom navigation implementations embraces client-rendered design patterns that store a local cache of navigation nodes.</span></span>

<span data-ttu-id="ef97b-201">Questi provider di spostamento hanno un paio di vantaggi principali:</span><span class="sxs-lookup"><span data-stu-id="ef97b-201">These navigation providers have a couple of key advantages:</span></span>

- <span data-ttu-id="ef97b-202">In genere funzionano bene con i progetti di pagina reattivi.</span><span class="sxs-lookup"><span data-stu-id="ef97b-202">They generally work well with responsive page designs.</span></span>
- <span data-ttu-id="ef97b-203">Sono estremamente scalabili e performanti perché è possibile eseguire il rendering senza costi di risorse (e aggiornare in background dopo un timeout).</span><span class="sxs-lookup"><span data-stu-id="ef97b-203">They are extremely scalable and performant because they can render with no resource cost (and refresh in the background after a timeout).</span></span>
- <span data-ttu-id="ef97b-204">Tali provider di spostamento possono recuperare i dati di spostamento utilizzando diverse strategie, che vanno dalle configurazioni statiche semplici ai vari provider di dati dinamici.</span><span class="sxs-lookup"><span data-stu-id="ef97b-204">These navigation providers can retrieve navigation data using various strategies, ranging from simple static configurations to various dynamic data providers.</span></span>

<span data-ttu-id="ef97b-205">Un esempio di provider di dati prevede l'utilizzo di una struttura di **spostamento basata sulla ricerca**, che consente la flessibilità per l'enumerazione dei nodi di spostamento e la gestione efficiente del taglio di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="ef97b-205">An example of a data provider is to use a **Search-driven navigation**, which allows flexibility for enumerating navigation nodes and handling security trimming efficiently.</span></span>

<span data-ttu-id="ef97b-206">Sono disponibili altre opzioni popolari per la creazione di **provider di spostamento personalizzati**.</span><span class="sxs-lookup"><span data-stu-id="ef97b-206">There are other popular options to build **Custom navigation providers**.</span></span> <span data-ttu-id="ef97b-207">Leggere le [soluzioni di navigazione per i portali di SharePoint Online](https://docs.microsoft.com/sharepoint/dev/solution-guidance/portal-navigation) per ulteriori informazioni sulla creazione di un provider di spostamento personalizzato.</span><span class="sxs-lookup"><span data-stu-id="ef97b-207">Please review [Navigation solutions for SharePoint Online portals](https://docs.microsoft.com/sharepoint/dev/solution-guidance/portal-navigation) for further guidance on building a Custom navigation provider.</span></span>

<span data-ttu-id="ef97b-208">Utilizzando la ricerca è possibile utilizzare gli indici sviluppati in background tramite la ricerca per indicizzazione continua.</span><span class="sxs-lookup"><span data-stu-id="ef97b-208">Using search you can leverage the indexes that are built up in the background using continuous crawl.</span></span> <span data-ttu-id="ef97b-209">I risultati della ricerca vengono recuperati dall'indice di ricerca e i risultati sono limitati per motivi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="ef97b-209">The search results are pulled from the search index and the results are security-trimmed.</span></span> <span data-ttu-id="ef97b-210">Questo è in genere più veloce rispetto ai provider di spostamento esterno alla casella quando è richiesta la limitazione della sicurezza.</span><span class="sxs-lookup"><span data-stu-id="ef97b-210">This is generally faster than out-of-the-box navigation providers when security trimming is required.</span></span> <span data-ttu-id="ef97b-211">Utilizzando la ricerca per l'esplorazione strutturale, soprattutto se si dispone di una struttura di siti complessa, è possibile velocizzare notevolmente tempi di caricamento delle pagine.</span><span class="sxs-lookup"><span data-stu-id="ef97b-211">Using search for structural navigation, especially if you have a complex site structure, will speed up page loading time considerably.</span></span> <span data-ttu-id="ef97b-212">Il principale vantaggio di questa esplorazione gestita è che è possibile beneficiare della limitazione per motivi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="ef97b-212">The main advantage of this over managed navigation is that you benefit from security trimming.</span></span>

<span data-ttu-id="ef97b-213">Questo approccio implica la creazione di una pagina master personalizzata e la sostituzione del codice di spostamento predefinito con codice HTML personalizzato.</span><span class="sxs-lookup"><span data-stu-id="ef97b-213">This approach involves creating a custom master page and replacing the out-of-the-box navigation code with custom HTML.</span></span> <span data-ttu-id="ef97b-214">Seguire questa procedura illustrata nell'esempio seguente per sostituire il codice di spostamento nel file `seattle.html` .</span><span class="sxs-lookup"><span data-stu-id="ef97b-214">Follow this procedure outlined in the following example to replace the navigation code in the file `seattle.html`.</span></span> <span data-ttu-id="ef97b-215">In questo esempio viene aperto il `seattle.html` file e sostituito l'intero elemento `id="DeltaTopNavigation"` con codice HTML personalizzato.</span><span class="sxs-lookup"><span data-stu-id="ef97b-215">In this example, you will open the `seattle.html` file and replace the whole element `id="DeltaTopNavigation"` with custom HTML code.</span></span>

### <a name="example-replace-the-out-of-the-box-navigation-code-in-a-master-page"></a><span data-ttu-id="ef97b-216">Esempio: sostituire il codice di spostamento fuori dalla casella in una pagina master</span><span class="sxs-lookup"><span data-stu-id="ef97b-216">Example: Replace the out-of-the-box navigation code in a master page</span></span>

1. <span data-ttu-id="ef97b-217">Andare alla pagina Impostazioni sito.</span><span class="sxs-lookup"><span data-stu-id="ef97b-217">Navigate to the Site Settings page.</span></span>
2. <span data-ttu-id="ef97b-218">Aprire la raccolta di pagine master facendo clic su **Pagine master**.</span><span class="sxs-lookup"><span data-stu-id="ef97b-218">Open the master page gallery by clicking **Master Pages**.</span></span>
3. <span data-ttu-id="ef97b-219">Da qui è possibile passare alla raccolta e scaricare il file `seattle.master` .</span><span class="sxs-lookup"><span data-stu-id="ef97b-219">From here you can navigate through the library and download the file `seattle.master`.</span></span>
4. <span data-ttu-id="ef97b-220">Modificare il codice utilizzando un editor di testo ed eliminare il blocco di codice nella schermata seguente.</span><span class="sxs-lookup"><span data-stu-id="ef97b-220">Edit the code using a text editor and delete the code block in the following screen shot.</span></span><br/>![Eliminare il blocco di codice visualizzato](../media/SPONavOptionsDeleteCodeBlock.png)<br/>
5. <span data-ttu-id="ef97b-222">Rimuovere il codice tra i `<SharePoint:AjaxDelta id="DeltaTopNavigation">` `<\SharePoint:AjaxDelta>` tag e e sostituirlo con il seguente frammento:</span><span class="sxs-lookup"><span data-stu-id="ef97b-222">Remove the code between the `<SharePoint:AjaxDelta id="DeltaTopNavigation">` and `<\SharePoint:AjaxDelta>` tags and replace it with the following snippet:</span></span><br/>

```javascript
<div id="loading">
  <!--Replace with path to loading image.-->
  <div style="background-image: url(''); height: 22px; width: 22px; ">
  </div>
</div>
<!-- Main Content-->
<div id="navContainer" style="display:none">
    <div data-bind="foreach: hierarchy" class="noindex ms-core-listMenu-horizontalBox">
        <a class="dynamic menu-item ms-core-listMenu-item ms-displayInline ms-navedit-linkNode" data-bind="attr: { href: item.Url, title: item.Title }">
            <span class="menu-item-text" data-bind="text: item.Title">
            </span>
        </a>
        <ul id="menu" data-bind="foreach: $data.children" style="padding-left:20px">
            <li class="static dynamic-children level1">
                <a class="static dynamic-children menu-item ms-core-listMenu-item ms-displayInline ms-navedit-linkNode" data-bind="attr: { href: item.Url, title: item.Title }">

                 <!-- ko if: children.length > 0-->
                    <span aria-haspopup="true" class="additional-background ms-navedit-flyoutArrow dynamic-children">
                        <span class="menu-item-text" data-bind="text: item.Title">
                        </span>
                    </span>
                <!-- /ko -->
                <!-- ko if: children.length == 0-->
                    <span aria-haspopup="true" class="ms-navedit-flyoutArrow dynamic-children">
                        <span class="menu-item-text" data-bind="text: item.Title">
                        </span>
                    </span>
                <!-- /ko -->
                </a>

                <!-- ko if: children.length > 0-->
                <ul id="menu"  data-bind="foreach: children;" class="dynamic  level2" >
                    <li class="dynamic level2">
                        <a class="dynamic menu-item ms-core-listMenu-item ms-displayInline  ms-navedit-linkNode" data-bind="attr: { href: item.Url, title: item.Title }">

          <!-- ko if: children.length > 0-->
          <span aria-haspopup="true" class="additional-background ms-navedit-flyoutArrow dynamic-children">
           <span class="menu-item-text" data-bind="text: item.Title">
           </span>
          </span>
           <!-- /ko -->
          <!-- ko if: children.length == 0-->
          <span aria-haspopup="true" class="ms-navedit-flyoutArrow dynamic-children">
           <span class="menu-item-text" data-bind="text: item.Title">
           </span>
          </span>
          <!-- /ko -->
                        </a>
          <!-- ko if: children.length > 0-->
         <ul id="menu" data-bind="foreach: children;" class="dynamic level3" >
          <li class="dynamic level3">
           <a class="dynamic menu-item ms-core-listMenu-item ms-displayInline ms-navedit-linkNode" data-bind="attr: { href: item.Url, title: item.Title }">
            <span class="menu-item-text" data-bind="text: item.Title">
            </span>
           </a>
          </li>
         </ul>
           <!-- /ko -->
                    </li>
                </ul>
                <!-- /ko -->
            </li>
        </ul>
    </div>
</div>
```

<br/>
6. <span data-ttu-id="ef97b-223">Sostituire l'URL nel tag Anchor dell'immagine di caricamento all'inizio, con un collegamento a un'immagine di caricamento nella raccolta siti.</span><span class="sxs-lookup"><span data-stu-id="ef97b-223">Replace the URL in the loading image anchor tag at the beginning, with a link to a loading image in your site collection.</span></span> <span data-ttu-id="ef97b-224">Dopo aver apportato le modifiche, rinominare il file, quindi caricarlo nella raccolta di pagine master.</span><span class="sxs-lookup"><span data-stu-id="ef97b-224">After you have made the changes, rename the file and then upload it to the master page gallery.</span></span> <span data-ttu-id="ef97b-225">Ciò genera un nuovo file con estensione master.</span><span class="sxs-lookup"><span data-stu-id="ef97b-225">This generates a new .master file.</span></span><br/>
7. <span data-ttu-id="ef97b-226">Questo codice HTML è il codice di base che verrà precompilato dai risultati della ricerca restituiti dal codice JavaScript.</span><span class="sxs-lookup"><span data-stu-id="ef97b-226">This HTML is the basic markup that will be populated by the search results returned from JavaScript code.</span></span> <span data-ttu-id="ef97b-227">Sarà necessario modificare il codice per modificare il valore di var root = "URL della raccolta siti", come illustrato nel seguente frammento:</span><span class="sxs-lookup"><span data-stu-id="ef97b-227">You will need to edit the code to change the value for var root = "site collection URL" as demonstrated in the following snippet:</span></span><br/>

```javascript
var root = "https://spperformance.sharepoint.com/sites/NavigationBySearch";
```

<br/>
8. <span data-ttu-id="ef97b-228">I risultati vengono assegnati alla matrice self. Nodes e viene creata una gerarchia degli oggetti utilizzando linq.js assegnando l'output a una matrice self. Hierarchy.</span><span class="sxs-lookup"><span data-stu-id="ef97b-228">The results are assigned to the self.nodes array and a hierarchy is built out of the objects using linq.js assigning the output to an array self.hierarchy.</span></span> <span data-ttu-id="ef97b-229">Questa matrice è l'oggetto in cui è associato il codice HTML.</span><span class="sxs-lookup"><span data-stu-id="ef97b-229">This array is the object that is bound to the HTML.</span></span> <span data-ttu-id="ef97b-230">Questa operazione viene eseguita nella funzione toggleView() passando l'oggetto utente alla funzione ko.applyBinding().</span><span class="sxs-lookup"><span data-stu-id="ef97b-230">This is done in the toggleView() function by passing the self object to the ko.applyBinding() function.</span></span><br/><span data-ttu-id="ef97b-231">Quindi, in questo modo la matrice di gerarchia va associata al codice HTML seguente:</span><span class="sxs-lookup"><span data-stu-id="ef97b-231">This then causes the hierarchy array to be bound to the following HTML:</span></span><br/>

```javascript
<div data-bind="foreach: hierarchy" class="noindex ms-core-listMenu-horizontalBox">
```

<span data-ttu-id="ef97b-232">I gestori eventi per `mouseenter` e `mouseexit` vengono aggiunti all'esplorazione di livello principale per gestire i menu a discesa dei siti secondari, che vengono eseguiti nella `addEventsToElements()` funzione.</span><span class="sxs-lookup"><span data-stu-id="ef97b-232">The event handlers for `mouseenter` and `mouseexit` are added to the top-level navigation to handle the subsite drop-down menus which is done in the `addEventsToElements()` function.</span></span>

<span data-ttu-id="ef97b-233">Nell'esempio di esplorazione complessa, un caricamento di pagina aggiornato senza la memorizzazione nella cache locale indica che il tempo trascorso nel server è stato ridotto dall'esplorazione strutturale di benchmark per ottenere un risultato simile a quello dell'approccio di spostamento gestito.</span><span class="sxs-lookup"><span data-stu-id="ef97b-233">In our complex navigation example, a fresh page load without the local caching shows the time spent on the server has been cut down from the benchmark structural navigation to get a similar result as the managed navigation approach.</span></span>

### <a name="about-the-javascript-file"></a><span data-ttu-id="ef97b-234">Informazioni sul file JavaScript...</span><span class="sxs-lookup"><span data-stu-id="ef97b-234">About the JavaScript file...</span></span>

>[!NOTE]
><span data-ttu-id="ef97b-235">Se si utilizza JavaScript personalizzato, verificare che la rete CDN pubblica sia abilitata e che il file si trovi in un percorso CDN.</span><span class="sxs-lookup"><span data-stu-id="ef97b-235">If using custom JavaScript, ensure that public CDN is enabled and the file is in a CDN location.</span></span>

<span data-ttu-id="ef97b-236">Di seguito è riportato l'intero file JavaScript:</span><span class="sxs-lookup"><span data-stu-id="ef97b-236">The entire JavaScript file is as follows:</span></span>

```javascript
//Models and Namespaces
var SPOCustom = SPOCustom || {};
SPOCustom.Models = SPOCustom.Models || {}
SPOCustom.Models.NavigationNode = function () {

    this.Url = ko.observable("");
    this.Title = ko.observable("");
    this.Parent = ko.observable("");

};

var root = "https://spperformance.sharepoint.com/sites/NavigationBySearch";
var baseUrl = root + "/_api/search/query?querytext=";
var query = baseUrl + "'contentClass=\"STS_Web\"+path:" + root + "'&trimduplicates=false&rowlimit=300";

var baseRequest = {
    url: "",
    type: ""
};


//Parses a local object from JSON search result.
function getNavigationFromDto(dto) {
    var item = new SPOCustom.Models.NavigationNode();
    if (dto != undefined) {

        var webTemplate = getSearchResultsValue(dto.Cells.results, 'WebTemplate');

        if (webTemplate != "APP") {
            item.Title(getSearchResultsValue(dto.Cells.results, 'Title')); //Key = Title
            item.Url(getSearchResultsValue(dto.Cells.results, 'Path')); //Key = Path
            item.Parent(getSearchResultsValue(dto.Cells.results, 'ParentLink')); //Key = ParentLink
        }

    }
    return item;
}

function getSearchResultsValue(results, key) {

    for (i = 0; i < results.length; i++) {
        if (results[i].Key == key) {
            return results[i].Value;
        }
    }
    return null;
}

//Parse a local object from the serialized cache.
function getNavigationFromCache(dto) {
    var item = new SPOCustom.Models.NavigationNode();

    if (dto != undefined) {

        item.Title(dto.Title);
        item.Url(dto.Url);
        item.Parent(dto.Parent);
    }

    return item;
}

/* create a new OData request for JSON response */
function getRequest(endpoint) {
    var request = baseRequest;
    request.type = "GET";
    request.url = endpoint;
    request.headers = { ACCEPT: "application/json;odata=verbose" };
    return request;
};

/* Navigation Module*/
function NavigationViewModel() {
    "use strict";
    var self = this;
    self.nodes = ko.observableArray([]);
    self.hierarchy = ko.observableArray([]);;
    self.loadNavigatioNodes = function () {
        //Check local storage for cached navigation datasource.
        var fromStorage = localStorage["nodesCache"];
        if (false) {
            var cachedNodes = JSON.parse(localStorage["nodesCache"]);

            if (cachedNodes && timeStamp) {
                //Check for cache expiration. Currently set to 3 hrs.
                var now = new Date();
                var diff = now.getTime() - timeStamp;
                if (Math.round(diff / (1000 * 60 * 60)) < 3) {

                    //return from cache.
                    var cacheResults = [];
                    $.each(cachedNodes, function (i, item) {
                        var nodeitem = getNavigationFromCache(item, true);
                        cacheResults.push(nodeitem);
                    });

                    self.buildHierarchy(cacheResults);
                    self.toggleView();
                    addEventsToElements();
                    return;
                }
            }
        }
        //No cache hit, REST call required.
        self.queryRemoteInterface();
    };

    //Executes a REST call and builds the navigation hierarchy.
    self.queryRemoteInterface = function () {
        var oDataRequest = getRequest(query);
        $.ajax(oDataRequest).done(function (data) {
            var results = [];
            $.each(data.d.query.PrimaryQueryResult.RelevantResults.Table.Rows.results, function (i, item) {

                if (i == 0) {
                    //Add root element.
                    var rootItem = new SPOCustom.Models.NavigationNode();
                    rootItem.Title("Root");
                    rootItem.Url(root);
                    rootItem.Parent(null);
                    results.push(rootItem);
                }
                var navItem = getNavigationFromDto(item);
                results.push(navItem);
            });
            //Add to local cache
            localStorage["nodesCache"] = ko.toJSON(results);

            localStorage["nodesCachedAt"] = new Date().getTime();
            self.nodes(results);
            if (self.nodes().length > 0) {
                var unsortedArray = self.nodes();
                var sortedArray = unsortedArray.sort(self.sortObjectsInArray);

                self.buildHierarchy(sortedArray);
                self.toggleView();
                addEventsToElements();
            }
        }).fail(function () {
            //Handle error here!!
            $("#loading").hide();
            $("#error").show();
        });
    };
    self.toggleView = function () {
        var navContainer = document.getElementById("navContainer");
        ko.applyBindings(self, navContainer);
        $("#loading").hide();
        $("#navContainer").show();

    };
    //Uses linq.js to build the navigation tree.
    self.buildHierarchy = function (enumerable) {
        self.hierarchy(Enumerable.From(enumerable).ByHierarchy(function (d) {
            return d.Parent() == null;
        }, function (parent, child) {
            if (parent.Url() == null || child.Parent() == null)
                return false;
            return parent.Url().toUpperCase() == child.Parent().toUpperCase();
        }).ToArray());

        self.sortChildren(self.hierarchy()[0]);
    };


    self.sortChildren = function (parent) {

        // sjip processing if no children
        if (!parent || !parent.children || parent.children.length === 0) {
            return;
        }

        parent.children = parent.children.sort(self.sortObjectsInArray2);

        for (var i = 0; i < parent.children.length; i++) {
            var elem = parent.children[i];

            if (elem.children && elem.children.length > 0) {
                self.sortChildren(elem);
            }
        }
    };

    // ByHierarchy method breaks the sorting in chrome and firefox
    // we need to resort  as ascending
    self.sortObjectsInArray2 = function (a, b) {
        if (a.item.Title() > b.item.Title())
            return 1;
        if (a.item.Title() < b.item.Title())
            return -1;
        return 0;
    };


    self.sortObjectsInArray = function (a, b) {
        if (a.Title() > b.Title())
            return -1;
        if (a.Title() < b.Title())
            return 1;
        return 0;
    }
}

//Loads the navigation on load and binds the event handlers for mouse interaction.
function InitCustomNav() {
    var viewModel = new NavigationViewModel();
    viewModel.loadNavigatioNodes();
}

function addEventsToElements() {
    //events.
      $("li.level1").mouseover(function () {
          var position = $(this).position();
          $(this).find("ul.level2").css({ width: 100, left: position.left + 10, top: 50 });
      })
   .mouseout(function () {
     $(this).find("ul.level2").css({  left: -99999, top: 0 });
   
    });
   
     $("li.level2").mouseover(function () {
          var position = $(this).position();
          console.log(JSON.stringify(position));
          $(this).find("ul.level3").css({ width: 100, left: position.left + 95, top:  position.top});
      })
   .mouseout(function () {
     $(this).find("ul.level3").css({  left: -99999, top: 0 });
    });
} _spBodyOnLoadFunctionNames.push("InitCustomNav");

```

<span data-ttu-id="ef97b-237">Per riepilogare il codice sopra riportato nella `jQuery $(document).ready` funzione viene `viewModel object` creata e quindi `loadNavigationNodes()` viene chiamata la funzione su quell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="ef97b-237">To summarize the code shown above in the `jQuery $(document).ready` function there is a `viewModel object` created and then the `loadNavigationNodes()` function on that object is called.</span></span> <span data-ttu-id="ef97b-238">Questa funzione carica la gerarchia di spostamento precedentemente creata memorizzata nell'archiviazione locale di HTML5 del browser client o chiama la funzione `queryRemoteInterface()` .</span><span class="sxs-lookup"><span data-stu-id="ef97b-238">This function either loads the previously built navigation hierarchy stored in the HTML5 local storage of the client browser or it calls the function `queryRemoteInterface()`.</span></span>

<span data-ttu-id="ef97b-239">`QueryRemoteInterface()` Compila una richiesta utilizzando la `getRequest()` funzione con il parametro di query definito in precedenza nello script e quindi restituisce i dati dal server.</span><span class="sxs-lookup"><span data-stu-id="ef97b-239">`QueryRemoteInterface()` builds a request using the `getRequest()` function with the query parameter defined earlier in the script and then returns data from the server.</span></span> <span data-ttu-id="ef97b-240">Questi dati sono sostanzialmente una matrice di tutti i siti nella raccolta di siti rappresentati come oggetti di trasferimento dei dati con alcune proprietà.</span><span class="sxs-lookup"><span data-stu-id="ef97b-240">This data is essentially an array of all the sites in the site collection represented as data transfer objects with various properties.</span></span>

<span data-ttu-id="ef97b-241">Questi dati vengono quindi analizzati negli oggetti definiti in precedenza `SPO.Models.NavigationNode` che utilizzano `Knockout.js` per creare proprietà osservabili per l'utilizzo da parte dei dati per l'associazione dei valori nel codice HTML definito in precedenza.</span><span class="sxs-lookup"><span data-stu-id="ef97b-241">This data is then parsed into the previously defined `SPO.Models.NavigationNode` objects which use `Knockout.js` to create observable properties for use by data binding the values into the HTML that we defined earlier.</span></span>

<span data-ttu-id="ef97b-242">Gli oggetti vengono quindi inseriti in una matrice di risultati.</span><span class="sxs-lookup"><span data-stu-id="ef97b-242">The objects are then put into a results array.</span></span> <span data-ttu-id="ef97b-243">Questa matrice viene analizzata in JSON utilizzando Knockout e memorizzata nell'archivio locale del browser per migliorare le prestazioni su caricamenti di pagina futuri.</span><span class="sxs-lookup"><span data-stu-id="ef97b-243">This array is parsed into JSON using Knockout and stored in the local browser storage for improved performance on future page loads.</span></span>

### <a name="benefits-of-this-approach"></a><span data-ttu-id="ef97b-244">Vantaggi di questo approccio</span><span class="sxs-lookup"><span data-stu-id="ef97b-244">Benefits of this approach</span></span>

<span data-ttu-id="ef97b-245">Uno dei principali vantaggi di [questo approccio](#example-replace-the-out-of-the-box-navigation-code-in-a-master-page) consiste nel fatto che tramite l'archiviazione locale di HTML5 la struttura di spostamento viene archiviata localmente per l'utente al successivo caricamento della pagina.</span><span class="sxs-lookup"><span data-stu-id="ef97b-245">One major benefit of [this approach](#example-replace-the-out-of-the-box-navigation-code-in-a-master-page) is that by using HTML5 local storage, the navigation is stored locally for the user the next time they load the page.</span></span> <span data-ttu-id="ef97b-246">Si ottengono miglioramenti delle prestazioni principali utilizzando l'API di ricerca per l'esplorazione strutturale; tuttavia, sono necessarie alcune capacità tecniche per eseguire e personalizzare questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="ef97b-246">We get major performance improvements from using the search API for structural navigation; however, it takes some technical capability to execute and customize this functionality.</span></span>

<span data-ttu-id="ef97b-247">Nell' [implementazione di esempio](#example-replace-the-out-of-the-box-navigation-code-in-a-master-page), i siti vengono ordinati in modo analogo a quello della struttura di spostamento strutturale fuori campo. ordine alfabetico.</span><span class="sxs-lookup"><span data-stu-id="ef97b-247">In the [example implementation](#example-replace-the-out-of-the-box-navigation-code-in-a-master-page), the sites are ordered in the same way as the out-of-the-box structural navigation; alphabetical order.</span></span> <span data-ttu-id="ef97b-248">Se si desidera deviare da questo ordine, diventa più complesso lo sviluppo e la manutenzione.</span><span class="sxs-lookup"><span data-stu-id="ef97b-248">If you wanted to deviate from this order, it would be more complicated to develop and maintain.</span></span> <span data-ttu-id="ef97b-249">Inoltre, questo approccio richiede di deviare dalle pagine master supportate.</span><span class="sxs-lookup"><span data-stu-id="ef97b-249">Also, this approach requires you to deviate from the supported master pages.</span></span> <span data-ttu-id="ef97b-250">Se non viene mantenuta la pagina master personalizzata, il sito verrà escluso dagli aggiornamenti e dai miglioramenti che Microsoft apporta alle pagine master.</span><span class="sxs-lookup"><span data-stu-id="ef97b-250">If the custom master page is not maintained, your site will miss out on updates and improvements that Microsoft makes to the master pages.</span></span>

<span data-ttu-id="ef97b-251">Il [codice sopra](#about-the-javascript-file) riportato presenta le dipendenze seguenti:</span><span class="sxs-lookup"><span data-stu-id="ef97b-251">The [above code](#about-the-javascript-file) has the following dependencies:</span></span>

- <span data-ttu-id="ef97b-252">jQuery https://jquery.com/</span><span class="sxs-lookup"><span data-stu-id="ef97b-252">jQuery - https://jquery.com/</span></span>
- <span data-ttu-id="ef97b-253">KnockoutJS - https://knockoutjs.com/</span><span class="sxs-lookup"><span data-stu-id="ef97b-253">KnockoutJS - https://knockoutjs.com/</span></span>
- <span data-ttu-id="ef97b-254">Linq.js- https://linqjs.codeplex.com/ , o github.com/neuecc/linq.js</span><span class="sxs-lookup"><span data-stu-id="ef97b-254">Linq.js - https://linqjs.codeplex.com/, or github.com/neuecc/linq.js</span></span>

<span data-ttu-id="ef97b-255">La versione corrente di LinqJS non contiene il metodo ByHierarchy utilizzato nel codice precedente e interrompe il codice di spostamento.</span><span class="sxs-lookup"><span data-stu-id="ef97b-255">The current version of LinqJS does not contain the ByHierarchy method used in the above code and will break the navigation code.</span></span> <span data-ttu-id="ef97b-256">Per risolvere il cosa, aggiungere il seguente metodo al file Linq.js prima della riga `Flatten: function ()` .</span><span class="sxs-lookup"><span data-stu-id="ef97b-256">To fix this, add the following method to the Linq.js file before the line `Flatten: function ()`.</span></span>

```javascript
ByHierarchy: function(firstLevel, connectBy, orderBy, ascending, parent) {
     ascending = ascending == undefined ? true : ascending;
     var orderMethod = ascending == true ? 'OrderBy' : 'OrderByDescending';
     var source = this;
     firstLevel = Utils.CreateLambda(firstLevel);
     connectBy = Utils.CreateLambda(connectBy);
     orderBy = Utils.CreateLambda(orderBy);

     //Initiate or increase level
     var level = parent === undefined ? 1 : parent.level + 1;

    return new Enumerable(function() {
         var enumerator;
         var index = 0;

        var createLevel = function() {
                 var obj = {
                     item: enumerator.Current(),
                     level : level
                 };
                 obj.children = Enumerable.From(source).ByHierarchy(firstLevel, connectBy, orderBy, ascending, obj);
                 if (orderBy !== undefined) {
                     obj.children = obj.children[orderMethod](function(d) {
                         return orderBy(d.item); //unwrap the actual item for sort to work
                     });
                 }
                 obj.children = obj.children.ToArray();
                 Enumerable.From(obj.children).ForEach(function(child) {
                     child.getParent = function() {
                         return obj;
                     };
                 });
                 return obj;
             };

        return new IEnumerator(

        function() {
             enumerator = source.GetEnumerator();
         }, function() {
             while (enumerator.MoveNext()) {
                 var returnArr;
                 if (!parent) {
                     if (firstLevel(enumerator.Current(), index++)) {
                         return this.Yield(createLevel());
                     }

                } else {
                     if (connectBy(parent.item, enumerator.Current(), index++)) {
                         return this.Yield(createLevel());
                     }
                 }
             }
             return false;
         }, function() {
             Utils.Dispose(enumerator);
         })
     });
 },

```
  
## <a name="related-topics"></a><span data-ttu-id="ef97b-257">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="ef97b-257">Related topics</span></span>

[<span data-ttu-id="ef97b-258">Panoramica dell'esplorazione gestita in SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="ef97b-258">Overview of managed navigation in SharePoint Server</span></span>](https://docs.microsoft.com/sharepoint/administration/overview-of-managed-navigation)

[<span data-ttu-id="ef97b-259">Memorizzazione nella cache e prestazioni della struttura di spostamento strutturale</span><span class="sxs-lookup"><span data-stu-id="ef97b-259">Structural navigation caching and performance</span></span>](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43)
