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
description: Informazioni su come migliorare le prestazioni sostituendo la Web part Query contenuto con la Web part Ricerca contenuto in SharePoint Server 2013 e SharePoint Online.
ms.openlocfilehash: e5f57e59a421d79302f447e229091fdfc96f1237
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691553"
---
# <a name="using-content-search-web-part-instead-of-content-query-web-part-to-improve-performance-in-sharepoint-online"></a>Utilizzo della web part Ricerca contenuto anziché della web part Query contenuto per migliorare le prestazioni in SharePoint Online

In questo articolo viene descritto come migliorare le prestazioni sostituendo la Web part Query contenuto con la Web part Ricerca contenuto in SharePoint Server 2013 e SharePoint Online.
  
Una delle nuove caratteristiche più potenti di SharePoint Server 2013 e SharePoint Online è la Web part Ricerca contenuto (CSWP). Questa web part utilizza l'indice di ricerca per recuperare rapidamente i risultati che vengono visualizzati all'utente. Utilizzare la Web part Ricerca contenuto anziché la Web part Query contenuto (CQWP) nelle pagine per migliorare le prestazioni per gli utenti.
  
L'utilizzo di una Web part Ricerca contenuto in una Web part Query contenuto comporta quasi sempre risultati di caricamento delle pagine significativamente migliori in SharePoint Online. Per ottenere la query corretta è disponibile una configurazione aggiuntiva, ma i ricompense migliorano le prestazioni e gli utenti più contenti.
  
## <a name="comparing-the-performance-gain-you-get-from-using-content-search-web-part-instead-of-content-query-web-part"></a>Confronto dei vantaggi delle prestazioni ottenibili dall'utilizzo della web part Ricerca contenuto anziché dalla web part Query contenuto

Negli esempi seguenti vengono illustrati i vantaggi relativi alle prestazioni che è possibile ricevere quando si utilizza una Web part Ricerca contenuto anziché una Web part Query contenuto. Gli effetti sono più evidenti con una struttura complessa del sito e query di contenuto molto ampie.
  
In questo sito di esempio sono disponibili le caratteristiche seguenti:
  
- 8 livelli di siti secondari.
    
- Elenchi che utilizzano un tipo di contenuto personalizzato "Fruit".
    
- Nella web part, la query di contenuto è ampia, restituendo tutti gli elementi con il tipo di contenuto "Fruit".
    
- Nell'esempio vengono utilizzati solo 50 elementi tra gli 8 siti. Gli effetti saranno ancora più evidenti per i siti con più contenuto.
    
Di seguito è riportato un screenshot dei risultati della web part Query contenuto.
  
![Grafico con la query contenuto della web part](../media/b3d41f20-dfe5-46ed-9c0a-31057e82de33.png)
  
In Internet Explorer, utilizzare la scheda **rete** degli strumenti di sviluppo F12 per esaminare i dettagli per l'intestazione della risposta. Nella schermata seguente, il valore di **SPRequestDuration** per il caricamento della pagina è 924 millisecondi. 
  
![Schermata durata della richiesta di 924](../media/343571f2-a249-4de2-bc11-2cee93498aea.png)
  
 **SPRequestDuration** indica la quantità di lavoro che viene fatta sul server per preparare la pagina. Il passaggio di contenuto in base alle web part di query con contenuto dalle web part di ricerca riduce drasticamente il tempo necessario per il rendering della pagina. Al contrario, una pagina con una Web part Ricerca contenuto equivalente, restituendo lo stesso numero di risultati, ha un valore di **SPRequestDuration** di 106 millisecondi, come mostrato in questa schermata: 
  
![Schermata durata della richiesta di 106](../media/b46387ac-660d-4e5e-a11c-cc430e912962.png)
  
## <a name="adding-a-content-search-web-part-in-sharepoint-online"></a>Aggiunta di una Web part Ricerca contenuto in SharePoint Online

L'aggiunta di una Web part Ricerca contenuto è molto simile a una Web part query di contenuto normale. Vedere la sezione  *"aggiungere una Web part Ricerca contenuto"*  in [configurare una Web part Ricerca contenuto in SharePoint](https://support.office.com/article/Configure-a-Content-Search-Web-Part-in-SharePoint-0dc16de1-dbe4-462b-babb-bf8338c36c9a).
  
## <a name="creating-the-right-search-query-for-your-content-search-web-part"></a>Creazione della query di ricerca corretta per la Web part Ricerca contenuto

Dopo aver aggiunto una Web part Ricerca contenuto, è possibile affinare la ricerca e restituire gli elementi desiderati. Per istruzioni dettagliate su come eseguire questa operazione, vedere la sezione  *"visualizzazione di contenuto configurando una query avanzata in una Web part Ricerca contenuto"*  in [configurare una Web part Ricerca contenuto in SharePoint](https://support.office.com/article/Configure-a-Content-Search-Web-Part-in-SharePoint-0dc16de1-dbe4-462b-babb-bf8338c36c9a).
  
## <a name="query-building-and-testing-tool"></a>Strumento di compilazione e testing delle query

Per creare e testare query complesse in uno strumento, vedere lo [strumento di query di ricerca](https://sp2013searchtool.codeplex.com/) in CodePlex. 
  

