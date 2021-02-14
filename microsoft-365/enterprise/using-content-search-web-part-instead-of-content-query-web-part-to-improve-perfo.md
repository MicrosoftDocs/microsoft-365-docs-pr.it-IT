---
title: Utilizzo della web part Ricerca contenuto anziché della web part Query contenuto per migliorare le prestazioni in SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 4/20/2015
audience: Admin
ms.topic: article
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
- MET150
- SPO160
ms.assetid: e8ce6b72-745b-464a-85c7-cbf6eb53391b
description: Informazioni su come migliorare le prestazioni sostituendo la web part Query contenuto con la web part Ricerca contenuto in SharePoint Server 2013 e SharePoint Online.
ms.openlocfilehash: e5f57e59a421d79302f447e229091fdfc96f1237
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691553"
---
# <a name="using-content-search-web-part-instead-of-content-query-web-part-to-improve-performance-in-sharepoint-online"></a><span data-ttu-id="70b71-103">Utilizzo della web part Ricerca contenuto anziché della web part Query contenuto per migliorare le prestazioni in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="70b71-103">Using Content Search Web Part instead of Content Query Web Part to improve performance in SharePoint Online</span></span>

<span data-ttu-id="70b71-104">In questo articolo viene descritto come migliorare le prestazioni sostituendo la web part Query contenuto con la web part Ricerca contenuto in SharePoint Server 2013 e SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="70b71-104">This article describes how to increase performance by replacing the Content Query Web Part with the Content Search Web Part in SharePoint Server 2013 and SharePoint Online.</span></span>
  
<span data-ttu-id="70b71-105">Una delle nuove funzionalità più potenti di SharePoint Server 2013 e SharePoint Online è la web part Ricerca contenuto.</span><span class="sxs-lookup"><span data-stu-id="70b71-105">One of the most powerful new features of SharePoint Server 2013 and SharePoint Online is the Content Search Web Part (CSWP).</span></span> <span data-ttu-id="70b71-106">Questa web part utilizza l'indice di ricerca per recuperare rapidamente i risultati visualizzati all'utente.</span><span class="sxs-lookup"><span data-stu-id="70b71-106">This Web Part uses the search index to quickly retrieve results which are shown to the user.</span></span> <span data-ttu-id="70b71-107">Utilizzare la web part Ricerca contenuto anziché la web part Query contenuto (CQWP) nelle pagine per migliorare le prestazioni per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="70b71-107">Use the Content Search Web Part instead of the Content Query Web Part (CQWP) in your pages to improve performance for your users.</span></span>
  
<span data-ttu-id="70b71-108">L'utilizzo di una web part Ricerca contenuto in una web part Query contenuto comporta quasi sempre prestazioni di caricamento delle pagine significativamente migliori in SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="70b71-108">Using a Content Search Web Part over a Content Query Web Part will almost always result in significantly better page load performance on SharePoint Online.</span></span> <span data-ttu-id="70b71-109">C'è un po' di configurazione aggiuntiva per ottenere la query giusta, ma i vantaggi sono prestazioni migliorate e utenti soddisfatti.</span><span class="sxs-lookup"><span data-stu-id="70b71-109">There is a little additional configuration to get the right query, but the rewards are improved performance and happier users.</span></span>
  
## <a name="comparing-the-performance-gain-you-get-from-using-content-search-web-part-instead-of-content-query-web-part"></a><span data-ttu-id="70b71-110">Confronto tra il miglioramento delle prestazioni derivato dall'utilizzo della web part Ricerca contenuto anziché della web part Query contenuto</span><span class="sxs-lookup"><span data-stu-id="70b71-110">Comparing the performance gain you get from using Content Search Web Part instead of Content Query Web Part</span></span>

<span data-ttu-id="70b71-111">Negli esempi seguenti vengono illustrati i miglioramenti relativi alle prestazioni che è possibile ottenere quando si utilizza una web part Ricerca contenuto anziché una web part Query contenuto.</span><span class="sxs-lookup"><span data-stu-id="70b71-111">The following examples show the relative performance gains you may receive when you use a Content Search Web Part instead of a Content Query Web Part.</span></span> <span data-ttu-id="70b71-112">Gli effetti sono più ovvi con una struttura di sito complessa e query di contenuto molto ampie.</span><span class="sxs-lookup"><span data-stu-id="70b71-112">The effects are more obvious with a complex site structure and very broad content queries.</span></span>
  
<span data-ttu-id="70b71-113">Questo sito di esempio presenta le caratteristiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="70b71-113">This example site has the following characteristics:</span></span>
  
- <span data-ttu-id="70b71-114">8 livelli di siti secondari.</span><span class="sxs-lookup"><span data-stu-id="70b71-114">8 levels of subsites.</span></span>
    
- <span data-ttu-id="70b71-115">Elenchi che usano un tipo di contenuto "fruit" personalizzato.</span><span class="sxs-lookup"><span data-stu-id="70b71-115">Lists using a custom "fruit" content type.</span></span>
    
- <span data-ttu-id="70b71-116">Nella web part la query sul contenuto è ampia e restituisce tutti gli elementi con il tipo di contenuto "fruit".</span><span class="sxs-lookup"><span data-stu-id="70b71-116">In the Web Part, the content query is broad, returning all items with the content type of "fruit".</span></span>
    
- <span data-ttu-id="70b71-117">Nell'esempio vengono utilizzati solo 50 elementi tra gli 8 siti.</span><span class="sxs-lookup"><span data-stu-id="70b71-117">The example only uses 50 items across the 8 sites.</span></span> <span data-ttu-id="70b71-118">Gli effetti saranno ancora più pronunciati per i siti con più contenuto.</span><span class="sxs-lookup"><span data-stu-id="70b71-118">The effects will be even more pronounced for sites with more content.</span></span>
    
<span data-ttu-id="70b71-119">Ecco una cattura di schermata dei risultati della web part Query contenuto.</span><span class="sxs-lookup"><span data-stu-id="70b71-119">Here is a screen shot of the results of the Content Query Web Part.</span></span>
  
![Grafico con la query contenuto della web part](../media/b3d41f20-dfe5-46ed-9c0a-31057e82de33.png)
  
<span data-ttu-id="70b71-121">In Internet Explorer usa la scheda **Rete** degli strumenti di sviluppo F12 per esaminare i dettagli dell'intestazione della risposta.</span><span class="sxs-lookup"><span data-stu-id="70b71-121">In Internet Explorer, use the **Network** tab of the F12 developer tools to look at the details for the response header.</span></span> <span data-ttu-id="70b71-122">Nella cattura di schermata seguente il valore di **SPRequestDuration** per il caricamento della pagina è 924 millisecondi.</span><span class="sxs-lookup"><span data-stu-id="70b71-122">In the following screen shot, the value for the **SPRequestDuration** for this page load is 924 milliseconds.</span></span> 
  
![Schermata durata della richiesta di 924](../media/343571f2-a249-4de2-bc11-2cee93498aea.png)
  
 <span data-ttu-id="70b71-124">**SPRequestDuration** indica la quantità di lavoro eseguita sul server per preparare la pagina.</span><span class="sxs-lookup"><span data-stu-id="70b71-124">**SPRequestDuration** indicates the amount of work that is done on the server to prepare the page.</span></span> <span data-ttu-id="70b71-125">Il passaggio del contenuto tramite query Web part contenuto tramite ricerca Web part riduce notevolmente il tempo necessario per il rendering della pagina.</span><span class="sxs-lookup"><span data-stu-id="70b71-125">Switching Content by Query Web Parts with Content by Search Web Parts dramatically reduces the time it takes to render the page.</span></span> <span data-ttu-id="70b71-126">Al contrario, una pagina con una web part Ricerca contenuto equivalente, che restituisce lo stesso numero di risultati, ha un valore **SPRequestDuration** di 106 millisecondi, come illustrato in questa cattura di schermata:</span><span class="sxs-lookup"><span data-stu-id="70b71-126">By contrast, a page with an equivalent Content Search Web Part, returning the same number of results has an **SPRequestDuration** value of 106 milliseconds as shown in this screen shot:</span></span> 
  
![Schermata durata della richiesta di 106](../media/b46387ac-660d-4e5e-a11c-cc430e912962.png)
  
## <a name="adding-a-content-search-web-part-in-sharepoint-online"></a><span data-ttu-id="70b71-128">Aggiunta di una web part Ricerca contenuto in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="70b71-128">Adding a Content Search Web Part in SharePoint Online</span></span>

<span data-ttu-id="70b71-129">L'aggiunta di una web part Ricerca contenuto è molto simile a una normale web part Query contenuto.</span><span class="sxs-lookup"><span data-stu-id="70b71-129">Adding a Content Search Web Part is very similar to a regular Content Query Web Part.</span></span> <span data-ttu-id="70b71-130">Vedere la sezione *"Aggiungere una web part Ricerca contenuto"* in [Configurare una web part Ricerca contenuto in SharePoint.](https://support.office.com/article/Configure-a-Content-Search-Web-Part-in-SharePoint-0dc16de1-dbe4-462b-babb-bf8338c36c9a)</span><span class="sxs-lookup"><span data-stu-id="70b71-130">See the section  *"Add a Content Search Web Part"*  in [Configure a Content Search Web Part in SharePoint](https://support.office.com/article/Configure-a-Content-Search-Web-Part-in-SharePoint-0dc16de1-dbe4-462b-babb-bf8338c36c9a).</span></span>
  
## <a name="creating-the-right-search-query-for-your-content-search-web-part"></a><span data-ttu-id="70b71-131">Creazione della query di ricerca giusta per la web part Ricerca contenuto</span><span class="sxs-lookup"><span data-stu-id="70b71-131">Creating the right search query for your Content Search Web Part</span></span>

<span data-ttu-id="70b71-132">Dopo aver aggiunto una web part Ricerca contenuto, è possibile perfezionare la ricerca e restituire gli elementi desiderati.</span><span class="sxs-lookup"><span data-stu-id="70b71-132">Once you have added a Content Search Web Part, you can refine the search and return the items you want.</span></span> <span data-ttu-id="70b71-133">Per istruzioni dettagliate su come eseguire questa operazione, vedere la sezione "Visualizzare il contenuto configurando una query avanzata in una web part Ricerca *contenuto" in* Configurare una web part Ricerca contenuto [in SharePoint.](https://support.office.com/article/Configure-a-Content-Search-Web-Part-in-SharePoint-0dc16de1-dbe4-462b-babb-bf8338c36c9a)</span><span class="sxs-lookup"><span data-stu-id="70b71-133">For detailed instructions on how to do this, see the section,  *"Display content by configuring an advanced query in a Content Search Web Part"*  in [Configure a Content Search Web Part in SharePoint](https://support.office.com/article/Configure-a-Content-Search-Web-Part-in-SharePoint-0dc16de1-dbe4-462b-babb-bf8338c36c9a).</span></span>
  
## <a name="query-building-and-testing-tool"></a><span data-ttu-id="70b71-134">Strumento di creazione e test di query</span><span class="sxs-lookup"><span data-stu-id="70b71-134">Query building and testing tool</span></span>

<span data-ttu-id="70b71-135">Per uno strumento per creare e testare query complesse, vedere [lo strumento query di ricerca](https://sp2013searchtool.codeplex.com/) in Codeplex.</span><span class="sxs-lookup"><span data-stu-id="70b71-135">For a tool to build and test complex queries, see the [Search Query Tool](https://sp2013searchtool.codeplex.com/) on Codeplex.</span></span> 
  

