---
title: Utilizzo della cache oggetti con SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 4/20/2015
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
ms.assetid: 38bc9c14-3826-449c-beb6-b1003bcbeaaf
description: In questo articolo viene illustrata la differenza tra l'utilizzo della cache oggetti in SharePoint Server 2013 locale e SharePoint Online.
ms.openlocfilehash: 279d156a941aad6fbe7adbcf052c57f5b58c652f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46696117"
---
# <a name="using-the-object-cache-with-sharepoint-online"></a><span data-ttu-id="8329b-103">Utilizzo della cache oggetti con SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="8329b-103">Using the object cache with SharePoint Online</span></span>

<span data-ttu-id="8329b-104">In questo articolo viene illustrata la differenza tra l'utilizzo della cache oggetti in SharePoint Server 2013 locale e SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="8329b-104">This article explains the difference between using the object cache in SharePoint Server 2013 on-premises and SharePoint Online.</span></span>
  
<span data-ttu-id="8329b-p101">Esiste un notevole impatto negativo nell'affidarsi alla cache oggetti nella distribuzione di SharePoint Online. Qualsiasi dipendenza dalla cache oggetti in SharePoint Online riduce l'affidabilità della pagina.</span><span class="sxs-lookup"><span data-stu-id="8329b-p101">There is significant negative impact of relying on the object cache in SharePoint Online deployment. Any dependency on object cache in SharePoint Online will reduce the reliability of your page.</span></span> 
  
## <a name="how-the-sharepoint-online-and-sharepoint-server-2013-object-cache-works"></a><span data-ttu-id="8329b-107">Funzionamento della cache oggetti di SharePoint Online e SharePoint Server 2013</span><span class="sxs-lookup"><span data-stu-id="8329b-107">How the SharePoint Online and SharePoint Server 2013 object cache works</span></span>

<span data-ttu-id="8329b-108">Quando SharePoint Server 2013 è ospitato in locale, il cliente dispone di server Web front-end privati che ospitano la cache oggetti.</span><span class="sxs-lookup"><span data-stu-id="8329b-108">When SharePoint Server 2013 is hosted on-premises, the customer has private front-end web servers that host the object cache.</span></span> <span data-ttu-id="8329b-109">Ciò significa che la cache è dedicata a un cliente ed è limitata solo dalla quantità di memoria disponibile e assegnata alla cache oggetti.</span><span class="sxs-lookup"><span data-stu-id="8329b-109">This means the cache is dedicated to one customer and is only limited by how much memory is available and allocated to the object cache.</span></span> <span data-ttu-id="8329b-110">Poiché viene servito un solo cliente nello scenario locale, in genere i server Web front-end dispongono di utenti che effettuano richieste per gli stessi siti ripetutamente.</span><span class="sxs-lookup"><span data-stu-id="8329b-110">Because only one customer is served in the on-premises scenario the front-end web servers typically have users making requests to the same sites over and over.</span></span> <span data-ttu-id="8329b-111">Ciò significa che la cache si riempie velocemente e rimane piena dei risultati delle query dell'elenco e degli oggetti di SharePoint che gli utenti richiedono regolarmente.</span><span class="sxs-lookup"><span data-stu-id="8329b-111">This means that the cache gets full quickly and remains full of the list query results and SharePoint objects that your users are requesting on a regular basis.</span></span>
  
![Mostra il traffico e il caricamento ai server Web front-end locali](../media/a0d38b36-4909-4abb-8d4e-4930814bb3de.png)
  
<span data-ttu-id="8329b-p103">Di conseguenza, la seconda volta che un utente visita una pagina, il tempo di caricamento della pagina migliora. Dopo un minimo di quattro caricamenti della stessa pagina, la pagina è memorizzata nella cache su tutti i server Web front-end.</span><span class="sxs-lookup"><span data-stu-id="8329b-p103">As a result, the second time a user visits a page, the page load time improves. After a minimum of four loads of the same page, the page is cached on all of the front-end web servers.</span></span>
  
<span data-ttu-id="8329b-115">Al contrario, in SharePoint Online sono presenti molti più server, ma anche molti altri siti.</span><span class="sxs-lookup"><span data-stu-id="8329b-115">In contrast, in SharePoint Online there are many more servers but also many more sites.</span></span> <span data-ttu-id="8329b-116">Ogni utente può connettersi a un server Web front-end diverso che non dispone della cache compilata.</span><span class="sxs-lookup"><span data-stu-id="8329b-116">Each user may connect to a different front-end web server that doesn't have the cache populated.</span></span> <span data-ttu-id="8329b-117">In caso contrario, la cache viene popolata per un server, ma l'utente successivo a tale server Web front-end richiede una pagina da un sito diverso.</span><span class="sxs-lookup"><span data-stu-id="8329b-117">Or, perhaps the cache does get populated for a server, but the next user to that front-end web server requests a page from a different site.</span></span> <span data-ttu-id="8329b-118">Oppure, anche se l'utente successivo richiede la stessa pagina in base alla visita precedente, viene effettuato un bilanciamento del carico a un server Web front-end diverso che non dispone di tale pagina nella cache.</span><span class="sxs-lookup"><span data-stu-id="8329b-118">Or, even if the next user requests the same page as on their previous visit, they are load-balanced to a different front-end web server that doesn't have that page in its cache.</span></span> <span data-ttu-id="8329b-119">In questo ultimo caso, la memorizzazione nella cache non aiuta affatto gli utenti.</span><span class="sxs-lookup"><span data-stu-id="8329b-119">In this last case, caching doesn't help the users at all.</span></span>
  
<span data-ttu-id="8329b-p105">Nella figura seguente, ogni punto rappresenta una pagina che richiede un utente e la cache in cui è memorizzato. Colori diversi rappresentano diversi clienti che condividono l'infrastruttura SaaS.</span><span class="sxs-lookup"><span data-stu-id="8329b-p105">In the following figure, each dot represents a page that a user is requesting and where it cached. Different colors represent different customers making shared use of the SaaS infrastructure.</span></span>
  
![Mostra i risultati di memorizzazione nella cache degli oggetti in SharePoint Online](../media/25d04011-ef83-4cb7-9e04-a6ed490f63c3.png)
  
<span data-ttu-id="8329b-123">Come si può notare dal diagramma, le possibilità di un determinato utente di accedere a un server con la versione memorizzata nella cache sono limitate.</span><span class="sxs-lookup"><span data-stu-id="8329b-123">As you can see from the diagram, the chances of any given user hitting a server with the cached version of their page are slim.</span></span> <span data-ttu-id="8329b-124">Inoltre, a causa della velocità effettiva elevata e del fatto che i server sono condivisi tra molti siti, la cache non dura molto perché è disponibile solo così tanto spazio per la memorizzazione nella cache.</span><span class="sxs-lookup"><span data-stu-id="8329b-124">Also, due to the large throughput and fact that the servers are shared between many sites, the cache doesn't last long since there is only so much space for caching available.</span></span>
  
<span data-ttu-id="8329b-125">Per tutti i motivi fin qui citati, basarsi su utenti con oggetti memorizzati nella cache non è un modo efficace per garantire un'esperienza utente e dei tempi di caricamento delle pagine di qualità in SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="8329b-125">For all of these reasons, relying on users getting cached objects is not an effective way to ensure a quality user experience and page load times in SharePoint Online.</span></span>
  
## <a name="if-we-cant-rely-on-the-object-cache-to-improve-performance-in-sharepoint-online-what-do-we-use-instead"></a><span data-ttu-id="8329b-126">Se non è possibile fare affidamento sulla cache oggetti per migliorare le prestazioni in SharePoint Online, cosa sarebbe opportuno utilizzare?</span><span class="sxs-lookup"><span data-stu-id="8329b-126">If we can't rely on the object cache to improve performance in SharePoint Online, what do we use instead?</span></span>

<span data-ttu-id="8329b-p107">Dal momento che non si dovrebbe utilizzare la memorizzazione nella cache in SharePoint Online, occorre prendere in considerazione metodi di progettazione alternativi per le personalizzazioni di SharePoint che utilizzano la cache oggetti. In altri termini, occorre prendere in considerazione l'utilizzo di metodi per problemi relativi alle prestazioni che non si basano sulla memorizzazione di oggetti nella cache per produrre risultati ottimali per gli utenti. Ciò è descritto in alcuni degli ulteriori articoli in questa serie tra cui:</span><span class="sxs-lookup"><span data-stu-id="8329b-p107">Since you shouldn't rely on caching in SharePoint Online, you should evaluate alternative design approaches for SharePoint customizations that use the object cache. This means using approaches for performance issues which do not rely on the object caching in order to produce good results for users. This is described in some of the other articles in this series and include:</span></span>
  
- [<span data-ttu-id="8329b-130">Opzioni di spostamento per SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="8329b-130">Navigation options for SharePoint Online</span></span>](navigation-options-for-sharepoint-online.md)
    
- [<span data-ttu-id="8329b-131">Minimizzazione e creazione di bundle in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="8329b-131">Minification and bundling in SharePoint Online</span></span>](minification-and-bundling-in-sharepoint-online.md)
    
- [<span data-ttu-id="8329b-132">Usare la rete per la distribuzione di contenuti di Office 365 con SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="8329b-132">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-microsoft-365-cdn-with-spo.md)
    
- [<span data-ttu-id="8329b-133">Ritardo caricamento immagini e JavaScript in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="8329b-133">Delay loading images and JavaScript in SharePoint Online</span></span>](delay-loading-images-and-javascript-in-sharepoint-online.md)
    

