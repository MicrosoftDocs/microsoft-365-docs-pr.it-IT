---
title: Introduzione all'ottimizzazione delle prestazioni per SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/22/2018
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid: SPO160
ms.assetid: 81c4be5f-327e-435d-a568-526d68cffef0
description: In questo articolo vengono illustrati gli aspetti specifici da considerare quando si progettano pagine per ottenere prestazioni ottimali in SharePoint Online.
ms.openlocfilehash: 6f40243c9d6a1657b6716a071288f5b4fb018164
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909739"
---
# <a name="introduction-to-performance-tuning-for-sharepoint-online"></a><span data-ttu-id="b0899-103">Introduzione all'ottimizzazione delle prestazioni per SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b0899-103">Introduction to performance tuning for SharePoint Online</span></span>

<span data-ttu-id="b0899-104">In questo articolo vengono illustrati gli aspetti specifici da considerare quando si progettano pagine per ottenere prestazioni ottimali in SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="b0899-104">This article explains what specific aspects you need to consider when designing pages for best performance in SharePoint Online.</span></span>
     
## <a name="sharepoint-online-metrics"></a><span data-ttu-id="b0899-105">Metriche di SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b0899-105">SharePoint Online metrics</span></span>

<span data-ttu-id="b0899-106">Le seguenti metriche generali per SharePoint Online forniscono dati reali sulle prestazioni:</span><span class="sxs-lookup"><span data-stu-id="b0899-106">The following broad metrics for SharePoint Online provide real world data about performance:</span></span>
  
- <span data-ttu-id="b0899-107">Velocità di caricamento delle pagine</span><span class="sxs-lookup"><span data-stu-id="b0899-107">How fast pages load</span></span>
    
- <span data-ttu-id="b0899-108">Numero di round trip necessari per ogni pagina</span><span class="sxs-lookup"><span data-stu-id="b0899-108">How many round trips required per page</span></span>
    
- <span data-ttu-id="b0899-109">Problemi con il servizio</span><span class="sxs-lookup"><span data-stu-id="b0899-109">Issues with the service</span></span>
    
- <span data-ttu-id="b0899-110">Altri aspetti che causano la riduzione delle prestazioni</span><span class="sxs-lookup"><span data-stu-id="b0899-110">Other things that cause performance degradation</span></span>
    
### <a name="conclusions-reached-because-of-the-data"></a><span data-ttu-id="b0899-111">Conclusioni in base ai dati</span><span class="sxs-lookup"><span data-stu-id="b0899-111">Conclusions reached because of the data</span></span>

<span data-ttu-id="b0899-112">I dati dicono:</span><span class="sxs-lookup"><span data-stu-id="b0899-112">The data tells us:</span></span>
  
- <span data-ttu-id="b0899-113">La maggior parte delle pagine garantisce buone prestazioni con SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="b0899-113">Most of the pages perform well on SharePoint Online.</span></span>
    
- <span data-ttu-id="b0899-114">Le pagine non personalizzate si caricano molto rapidamente.</span><span class="sxs-lookup"><span data-stu-id="b0899-114">Non-customized pages load very quickly.</span></span>
    
- <span data-ttu-id="b0899-115">OneDrive for Business, i siti del team e le pagine di sistema, ad esempio _layouts e così via, si caricano tutti rapidamente.</span><span class="sxs-lookup"><span data-stu-id="b0899-115">OneDrive for Business, team sites and system pages, such as _layouts, etc., are all quick to load.</span></span>
    
- <span data-ttu-id="b0899-116">La pagina più lenta di 1% di SharePoint Online impiega più di 5.000 millisecondi per caricarsi.</span><span class="sxs-lookup"><span data-stu-id="b0899-116">The slowest 1% of SharePoint Online pages take more than 5,000 milliseconds to load.</span></span>
    
<span data-ttu-id="b0899-p101">È possibile utilizzare un semplice test di benchmark per misurare le prestazioni confrontando il tempo di caricamento del proprio portale con il tempo di caricamento della home page di OneDrive for Business, perché utilizza alcune funzionalità personalizzate. Questo spesso sarà il primo passaggio che il supporto chiederà di completare durante la risoluzione dei problemi relativi alle prestazioni di rete.</span><span class="sxs-lookup"><span data-stu-id="b0899-p101">One simple benchmark test you can use would be to measure performance by comparing the load time of your own portal against the load time of the OneDrive for Business home page as it uses few customized features. This will often be the first step Support will ask you to complete when troubleshooting network performance issues.</span></span>
  
## <a name="use-a-standard-user-account-when-checking-performance"></a><span data-ttu-id="b0899-119">Usare un account utente standard per controllare le prestazioni</span><span class="sxs-lookup"><span data-stu-id="b0899-119">Use a standard user account when checking performance</span></span>

<span data-ttu-id="b0899-120">Un amministratore della raccolta siti, un proprietario del sito, un editor o un collaboratore appartengono a gruppi di sicurezza aggiuntivi, dispongono di autorizzazioni aggiuntive e pertanto dispongono di elementi aggiuntivi caricati da SharePoint in una pagina.</span><span class="sxs-lookup"><span data-stu-id="b0899-120">A Site Collection Administrator, Site Owner, Editor, or Contributor belong to additional security groups, have additional permissions, and therefore have additional elements that SharePoint loads on a page.</span></span>
  
<span data-ttu-id="b0899-121">Ciò è applicabile a SharePoint locale e SharePoint Online, ma in uno scenario locale le differenze non saranno così facilmente notate come in SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="b0899-121">This is applicable to SharePoint on-premises and SharePoint Online but in an on-premises scenario the differences will not be as easily noticed as in SharePoint Online.</span></span>
  
<span data-ttu-id="b0899-122">Per valutare correttamente le prestazioni di una pagina per gli utenti, è consigliabile utilizzare un account utente standard per evitare di caricare i controlli di creazione e modifica e il traffico aggiuntivo correlato ai gruppi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="b0899-122">In order to correctly evaluate how a page will perform for users, you should use a standard user account to avoid loading the authoring controls and additional traffic related to security groups.</span></span>
  
## <a name="connection-categories-for-performance-tuning"></a><span data-ttu-id="b0899-123">Categorie di connessione per l'ottimizzazione delle prestazioni</span><span class="sxs-lookup"><span data-stu-id="b0899-123">Connection categories for performance tuning</span></span>

<span data-ttu-id="b0899-p102">È possibile classificare le connessioni tra il server e l'utente in tre componenti principali. Prendere in considerazione tali componenti durante la progettazione delle pagine di SharePoint Online per comprendere i tempi di caricamento.</span><span class="sxs-lookup"><span data-stu-id="b0899-p102">You can categorize the connections between the server and the user into three main components. Consider these when designing SharePoint Online pages for insight into load times.</span></span>
  
- <span data-ttu-id="b0899-126">**Server** Server ospitati da Microsoft nei datacenter.</span><span class="sxs-lookup"><span data-stu-id="b0899-126">**Server** The servers that Microsoft hosts in datacenters.</span></span>
    
- <span data-ttu-id="b0899-127">**Rete** La rete Microsoft, Internet e la rete locale tra il datacenter e gli utenti.</span><span class="sxs-lookup"><span data-stu-id="b0899-127">**Network** The Microsoft network, the Internet, and your on-premises network between the datacenter and your users.</span></span>
    
- <span data-ttu-id="b0899-128">**Browser** Posizione in cui viene caricata la pagina.</span><span class="sxs-lookup"><span data-stu-id="b0899-128">**Browser** Where the page is loaded.</span></span>
    
<span data-ttu-id="b0899-p103">All'interno di queste tre connessioni in genere esistono cinque motivi che causano il 95% delle pagine lente. Ciascuna di queste situazioni è illustrata in questo articolo:</span><span class="sxs-lookup"><span data-stu-id="b0899-p103">Within these three connections there are typically five reasons that cause 95% of slow pages. Each of these reasons is discussed in this article:</span></span>
  
- <span data-ttu-id="b0899-131">Problemi di navigazione</span><span class="sxs-lookup"><span data-stu-id="b0899-131">Navigation issues</span></span>
    
- <span data-ttu-id="b0899-132">Rollup contenuto</span><span class="sxs-lookup"><span data-stu-id="b0899-132">Content roll up</span></span>
    
- <span data-ttu-id="b0899-133">File di grandi dimensioni</span><span class="sxs-lookup"><span data-stu-id="b0899-133">Large files</span></span>
    
- <span data-ttu-id="b0899-134">Numero elevato di richieste al server</span><span class="sxs-lookup"><span data-stu-id="b0899-134">Many requests to the server</span></span>
    
- <span data-ttu-id="b0899-135">Elaborazione di Web Part</span><span class="sxs-lookup"><span data-stu-id="b0899-135">Web Part processing</span></span>
    
### <a name="server-connection"></a><span data-ttu-id="b0899-136">Connessione al server</span><span class="sxs-lookup"><span data-stu-id="b0899-136">Server connection</span></span>

<span data-ttu-id="b0899-137">Molti dei problemi che influiscono sulle prestazioni di SharePoint locale valgono anche per SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="b0899-137">Many of the issues that affect performance with SharePoint on-premises also apply to SharePoint Online.</span></span>
  
<span data-ttu-id="b0899-p104">Come previsto, è necessario prestare maggiore controllo sul funzionamento dei server con SharePoint locale. Con SharePoint Online le cose sono leggermente diverse. Più lavoro si fa fare al server, maggiore sarà il tempo necessario per il rendering di una pagina. Con SharePoint, la causa principale a questo proposito sono le pagine complesse con più web part.</span><span class="sxs-lookup"><span data-stu-id="b0899-p104">As you would expect, you have far more control over how servers perform with on-premises SharePoint. With SharePoint Online things are a little different. The more work you make a server do, the longer it takes to render a page. With SharePoint, the biggest culprit in this respect are complex pages with multiple web parts.</span></span>
  
<span data-ttu-id="b0899-142">SharePoint Server locale</span><span class="sxs-lookup"><span data-stu-id="b0899-142">SharePoint Server on-premises</span></span>
  
![Schermata del server in locale](../media/a8e9b646-cdff-4131-976a-b5f891da44ac.png)
  
<span data-ttu-id="b0899-144">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b0899-144">SharePoint Online</span></span>
  
![Schermata del server online](../media/46b27ded-d8a4-4287-b3e0-2603a764b8f8.png)
  
<span data-ttu-id="b0899-p105">Con SharePoint Online, alcune richieste di pagine potrebbero effettivamente finire per chiamare più server. Si potrebbe finire con una matrice di richieste tra i server per una singola richiesta. Tali interazioni sono costose da una prospettiva di caricamento della pagina e rendono le operazioni lente.</span><span class="sxs-lookup"><span data-stu-id="b0899-p105">With SharePoint Online, certain page requests may actually end up calling multiple servers. You could end up with a matrix of requests between servers for an individual request. These interactions are expensive from a page load perspective and will make things slow.</span></span>
  
<span data-ttu-id="b0899-149">Esempi di tali interazioni da server a server sono:</span><span class="sxs-lookup"><span data-stu-id="b0899-149">Examples of these server to server interactions are:</span></span>
  
- <span data-ttu-id="b0899-150">Da Web a SQL Server</span><span class="sxs-lookup"><span data-stu-id="b0899-150">Web to SQL Servers</span></span>
    
- <span data-ttu-id="b0899-151">Da Web ai server applicazioni</span><span class="sxs-lookup"><span data-stu-id="b0899-151">Web to application servers</span></span>
    
<span data-ttu-id="b0899-p106">L'altra operazione che può rallentare le interazioni del server è la mancanza della cache. A differenza di SharePoint locale, esiste una possibilità molto piccola di raggiungere lo stesso server di una pagina visitata in precedenza. Ciò rende la memorizzazione degli oggetti nella cache obsoleta.</span><span class="sxs-lookup"><span data-stu-id="b0899-p106">The other thing that can slow down server interactions is cache misses. Unlike on-premises SharePoint, there is a very slim chance that you will hit the same server for a page that you have visited previously; this makes object caching obsolete.</span></span>
  
### <a name="network-connection"></a><span data-ttu-id="b0899-154">Connessione di rete</span><span class="sxs-lookup"><span data-stu-id="b0899-154">Network connection</span></span>

<span data-ttu-id="b0899-155">Con SharePoint locale che non utilizza una rete WAN, è possibile utilizzare una connessione ad alta velocità tra datacenter e utenti finali.</span><span class="sxs-lookup"><span data-stu-id="b0899-155">With on-premises SharePoint that doesn't make use of a WAN, you may use a high-speed connection between datacenter and end-users.</span></span> <span data-ttu-id="b0899-156">In genere, le operazioni sono facili da gestire da un punto di vista della rete.</span><span class="sxs-lookup"><span data-stu-id="b0899-156">Generally, things are easy to manage from a network perspective.</span></span>
  
<span data-ttu-id="b0899-157">Con SharePoint Online, esistono alcuni ulteriori fattori da considerare; ad esempio:</span><span class="sxs-lookup"><span data-stu-id="b0899-157">With SharePoint Online, there are a few more factors to consider; for example:</span></span>
  
- <span data-ttu-id="b0899-158">La rete Microsoft</span><span class="sxs-lookup"><span data-stu-id="b0899-158">The Microsoft network</span></span>
    
- <span data-ttu-id="b0899-159">Internet</span><span class="sxs-lookup"><span data-stu-id="b0899-159">The Internet</span></span>
    
- <span data-ttu-id="b0899-160">Il provider di servizi Internet</span><span class="sxs-lookup"><span data-stu-id="b0899-160">The ISP</span></span>
    
<span data-ttu-id="b0899-161">Indipendentemente dalla versione di SharePoint (e di rete) utilizzata, le operazioni che in genere rendono la rete occupata sono:</span><span class="sxs-lookup"><span data-stu-id="b0899-161">Regardless of which version of SharePoint (and which network) you are using, things that will typically cause the network to be busy include:</span></span>
  
- <span data-ttu-id="b0899-162">Payload di grandi dimensioni</span><span class="sxs-lookup"><span data-stu-id="b0899-162">Large payload</span></span>
    
- <span data-ttu-id="b0899-163">Numero elevato di file</span><span class="sxs-lookup"><span data-stu-id="b0899-163">Many files</span></span>
    
- <span data-ttu-id="b0899-164">Grande distanza fisica con il server</span><span class="sxs-lookup"><span data-stu-id="b0899-164">Large physical distance to the server</span></span>
    
<span data-ttu-id="b0899-165">Una funzionalità da sfruttare in SharePoint Online è Microsoft CDN (CDN, rete per la distribuzione di contenuti).</span><span class="sxs-lookup"><span data-stu-id="b0899-165">One feature that you can leverage in SharePoint Online is the Microsoft CDN (Content Delivery Network).</span></span> <span data-ttu-id="b0899-166">Una rete CDN è fondamentalmente un insieme di server distribuiti su più datacenter.</span><span class="sxs-lookup"><span data-stu-id="b0899-166">A CDN is basically a distributed collection of servers deployed across multiple datacenters.</span></span> <span data-ttu-id="b0899-167">Con una rete CDN, il contenuto delle pagine può essere ospitato su un server più vicino al client anche se il client è lontano dal server di SharePoint di origine.</span><span class="sxs-lookup"><span data-stu-id="b0899-167">With a CDN, content on pages can be hosted on a server close to the client even if the client is far away from the originating SharePoint Server.</span></span> <span data-ttu-id="b0899-168">Microsoft utilizzerà ancora questa funzionalità in futuro per l'archiviazione locale di istanze di pagine che non possono essere personalizzate, ad esempio la home page di amministrazione di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="b0899-168">Microsoft will be using this more in the future to store local instances of pages which cannot be customized, for example the SharePoint Online admin home page.</span></span> <span data-ttu-id="b0899-169">Per ulteriori informazioni sulle reti CDN, vedere [Reti di recapito del contenuto.](content-delivery-networks.md)</span><span class="sxs-lookup"><span data-stu-id="b0899-169">For more information about CDNs, see [Content delivery networks](content-delivery-networks.md).</span></span>
  
<span data-ttu-id="b0899-p109">Un elemento che è necessario tenere presente ma sul quale potrebbe non essere possibile agire, è la velocità della connessione del provider di servizi Internet. Uno strumento di test di velocità semplice indica la velocità della connessione.</span><span class="sxs-lookup"><span data-stu-id="b0899-p109">Something that you need to be aware of but may not be able to do much about is the connection speed of your ISP. A simple speed test tool will tell you the connection speed.</span></span>
  
### <a name="browser-connection"></a><span data-ttu-id="b0899-172">Connessione del browser</span><span class="sxs-lookup"><span data-stu-id="b0899-172">Browser connection</span></span>

<span data-ttu-id="b0899-173">Esistono alcuni fattori da considerare con il browser Web dal punto di vista delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="b0899-173">There are a few factors to consider with web browsers from a performance perspective.</span></span>
  
<span data-ttu-id="b0899-174">L'esplorazione pagine complesse influisce sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="b0899-174">Visiting complex pages will affect performance.</span></span> <span data-ttu-id="b0899-175">La maggior parte dei browser presentano solo una piccola cache (circa 90 MB), mentre la media delle pagina Web in genere è di circa 1,6 MB.</span><span class="sxs-lookup"><span data-stu-id="b0899-175">Most browsers only have a small cache (around 90MB), while the average web page is typically around 1.6MB.</span></span> <span data-ttu-id="b0899-176">Questo non richiede molto tempo per abituarsi.</span><span class="sxs-lookup"><span data-stu-id="b0899-176">This doesn't take long to get used up.</span></span>
  
<span data-ttu-id="b0899-177">Anche la larghezza di banda potrebbe essere un problema.</span><span class="sxs-lookup"><span data-stu-id="b0899-177">Bandwidth may also be an issue.</span></span> <span data-ttu-id="b0899-178">Ad esempio, se un utente sta guardando video in un'altra sessione, ciò influirà sulle prestazioni della pagina SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b0899-178">For example, if a user is watching videos in another session, this will affect the performance of your SharePoint page.</span></span> <span data-ttu-id="b0899-179">Anche se non puoi impedire agli utenti di trasmettere contenuti multimediali, puoi controllare il modo in cui una pagina verrà caricata per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="b0899-179">While you can't prevent users from streaming media, you can control the way a page will load for users.</span></span>
  
<span data-ttu-id="b0899-180">Vedere gli articoli seguenti per le diverse tecniche di personalizzazione delle pagine di SharePoint Online e altre procedure consigliate per ottenere prestazioni ottimali.</span><span class="sxs-lookup"><span data-stu-id="b0899-180">Check out the following articles for different SharePoint Online page customization techniques and other best practices to help you achieve optimal performance.</span></span>
  
- [<span data-ttu-id="b0899-181">Opzioni di spostamento per SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b0899-181">Navigation options for SharePoint Online</span></span>](navigation-options-for-sharepoint-online.md)
    
- [<span data-ttu-id="b0899-182">Usare lo strumento Diagnostica pagine per SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b0899-182">Use the Page Diagnostics tool for SharePoint Online</span></span>](page-diagnostics-for-spo.md)
    
- [<span data-ttu-id="b0899-183">Ottimizzazione delle immagini per SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b0899-183">Image optimization for SharePoint Online</span></span>](image-optimization-for-sharepoint-online.md)
    
- [<span data-ttu-id="b0899-184">Ritardo caricamento immagini e JavaScript in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b0899-184">Delay loading images and JavaScript in SharePoint Online</span></span>](delay-loading-images-and-javascript-in-sharepoint-online.md)
    
- [<span data-ttu-id="b0899-185">Minimizzazione e creazione di bundle in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b0899-185">Minification and bundling in SharePoint Online</span></span>](minification-and-bundling-in-sharepoint-online.md)
    
- [<span data-ttu-id="b0899-186">Usare la rete per la distribuzione di contenuti di Office 365 con SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b0899-186">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-microsoft-365-cdn-with-spo.md)
    
- [<span data-ttu-id="b0899-187">Utilizzo della web part Ricerca contenuto anziché della web part Query contenuto per migliorare le prestazioni in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b0899-187">Using Content Search Web Part instead of Content Query Web Part to improve performance in SharePoint Online</span></span>](using-content-search-web-part-instead-of-content-query-web-part-to-improve-perfo.md)
    
- [<span data-ttu-id="b0899-188">Pianificazione della capacità e test di carico di SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b0899-188">Capacity planning and load testing SharePoint Online</span></span>](capacity-planning-and-load-testing-sharepoint-online.md)
    
- [<span data-ttu-id="b0899-189">Diagnosi dei problemi delle prestazioni con SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b0899-189">Diagnosing performance issues with SharePoint Online</span></span>](diagnosing-performance-issues-with-sharepoint-online.md)
    
- [<span data-ttu-id="b0899-190">Utilizzo della cache oggetti con SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b0899-190">Using the object cache with SharePoint Online</span></span>](using-the-object-cache-with-sharepoint-online.md)
    
- [<span data-ttu-id="b0899-191">Procedura: Evitare la limitazione o il blocco in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b0899-191">How to: Avoid getting throttled or blocked in SharePoint Online</span></span>](/sharepoint/dev/general-development/how-to-avoid-getting-throttled-or-blocked-in-sharepoint-online)
