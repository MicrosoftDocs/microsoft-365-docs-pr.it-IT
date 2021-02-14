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
ms.openlocfilehash: d3a9dedbd5812774b81494af0f8defa5568f7dac
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691453"
---
# <a name="introduction-to-performance-tuning-for-sharepoint-online"></a>Introduzione all'ottimizzazione delle prestazioni per SharePoint Online

In questo articolo vengono illustrati gli aspetti specifici da considerare quando si progettano pagine per ottenere prestazioni ottimali in SharePoint Online.
     
## <a name="sharepoint-online-metrics"></a>Metriche di SharePoint Online

Le seguenti metriche generali per SharePoint Online forniscono dati reali sulle prestazioni:
  
- Velocità di caricamento delle pagine
    
- Numero di round trip necessari per ogni pagina
    
- Problemi con il servizio
    
- Altri aspetti che causano la riduzione delle prestazioni
    
### <a name="conclusions-reached-because-of-the-data"></a>Conclusioni in base ai dati

I dati dicono:
  
- La maggior parte delle pagine garantisce buone prestazioni con SharePoint Online.
    
- Le pagine non personalizzate si caricano molto rapidamente.
    
- OneDrive for Business, i siti del team e le pagine di sistema, ad esempio _layouts e così via, si caricano tutti rapidamente.
    
- La pagina più lenta di 1% di SharePoint Online impiega più di 5.000 millisecondi per caricarsi.
    
È possibile utilizzare un semplice test di benchmark per misurare le prestazioni confrontando il tempo di caricamento del proprio portale con il tempo di caricamento della home page di OneDrive for Business, perché utilizza alcune funzionalità personalizzate. Questo spesso sarà il primo passaggio che il supporto chiederà di completare durante la risoluzione dei problemi relativi alle prestazioni di rete.
  
## <a name="use-a-standard-user-account-when-checking-performance"></a>Utilizzare un account utente standard per il controllo delle prestazioni

Un amministratore della raccolta siti, un proprietario del sito, un editor o un collaboratore appartengono a gruppi di sicurezza aggiuntivi, dispongono di autorizzazioni aggiuntive e pertanto dispongono di elementi aggiuntivi caricati da SharePoint in una pagina.
  
Ciò è applicabile a SharePoint locale e SharePoint Online, ma in uno scenario locale le differenze non saranno facilmente notate come in SharePoint Online.
  
Per valutare correttamente le prestazioni di una pagina per gli utenti, è consigliabile utilizzare un account utente standard per evitare di caricare i controlli di creazione e modifica e il traffico aggiuntivo correlato ai gruppi di sicurezza.
  
## <a name="connection-categories-for-performance-tuning"></a>Categorie di connessione per l'ottimizzazione delle prestazioni

È possibile classificare le connessioni tra il server e l'utente in tre componenti principali. Prendere in considerazione tali componenti durante la progettazione delle pagine di SharePoint Online per comprendere i tempi di caricamento.
  
- **Server** I server ospitati da Microsoft nei datacenter.
    
- **Rete** La rete Microsoft, Internet e la rete locale tra il datacenter e gli utenti.
    
- **Browser** Posizione in cui viene caricata la pagina.
    
All'interno di queste tre connessioni in genere esistono cinque motivi che causano il 95% delle pagine lente. Ciascuna di queste situazioni è illustrata in questo articolo:
  
- Problemi di navigazione
    
- Rollup contenuto
    
- File di grandi dimensioni
    
- Numero elevato di richieste al server
    
- Elaborazione di Web Part
    
### <a name="server-connection"></a>Connessione al server

Molti dei problemi che influiscono sulle prestazioni di SharePoint locale valgono anche per SharePoint Online.
  
Come previsto, è necessario prestare maggiore controllo sul funzionamento dei server con SharePoint locale. Con SharePoint Online le cose sono leggermente diverse. Più lavoro si fa fare al server, maggiore sarà il tempo necessario per il rendering di una pagina. Con SharePoint, la causa principale a questo proposito sono le pagine complesse con più web part.
  
SharePoint Server locale
  
![Schermata del server in locale](../media/a8e9b646-cdff-4131-976a-b5f891da44ac.png)
  
SharePoint Online
  
![Schermata del server online](../media/46b27ded-d8a4-4287-b3e0-2603a764b8f8.png)
  
Con SharePoint Online, alcune richieste di pagine potrebbero effettivamente finire per chiamare più server. Si potrebbe finire con una matrice di richieste tra i server per una singola richiesta. Tali interazioni sono costose da una prospettiva di caricamento della pagina e rendono le operazioni lente.
  
Esempi di tali interazioni da server a server sono:
  
- Da Web a SQL Server
    
- Da Web ai server applicazioni
    
L'altra operazione che può rallentare le interazioni del server è la mancanza della cache. A differenza di SharePoint locale, esiste una possibilità molto piccola di raggiungere lo stesso server di una pagina visitata in precedenza. Ciò rende la memorizzazione degli oggetti nella cache obsoleta.
  
### <a name="network-connection"></a>Connessione di rete

Con SharePoint locale che non utilizza una rete WAN, è possibile utilizzare una connessione ad alta velocità tra datacenter e utenti finali. In genere, le operazioni sono facili da gestire da un punto di vista della rete.
  
Con SharePoint Online, esistono alcuni ulteriori fattori da considerare; ad esempio:
  
- La rete Microsoft
    
- Internet
    
- Il provider di servizi Internet
    
Indipendentemente dalla versione di SharePoint (e di rete) utilizzata, le operazioni che in genere rendono la rete occupata sono:
  
- Payload di grandi dimensioni
    
- Numero elevato di file
    
- Grande distanza fisica con il server
    
Una funzionalità da sfruttare in SharePoint Online è Microsoft CDN (CDN, rete per la distribuzione di contenuti). Una rete CDN è fondamentalmente un insieme di server distribuiti su più datacenter. Con una rete CDN, il contenuto delle pagine può essere ospitato su un server più vicino al client anche se il client è lontano dal server di SharePoint di origine. Microsoft utilizzerà ancora questa funzionalità in futuro per l'archiviazione locale di istanze di pagine che non possono essere personalizzate, ad esempio la home page di amministrazione di SharePoint Online. Per ulteriori informazioni sulle reti CDN, vedere [Reti per la distribuzione di contenuti.](content-delivery-networks.md)
  
Un elemento che è necessario tenere presente ma sul quale potrebbe non essere possibile agire, è la velocità della connessione del provider di servizi Internet. Uno strumento di test di velocità semplice indica la velocità della connessione.
  
### <a name="browser-connection"></a>Connessione del browser

Esistono alcuni fattori da considerare con il browser Web dal punto di vista delle prestazioni.
  
L'esplorazione pagine complesse influisce sulle prestazioni. La maggior parte dei browser presentano solo una piccola cache (circa 90 MB), mentre la media delle pagina Web in genere è di circa 1,6 MB. Questa operazione non richiede molto tempo per essere usata.
  
Anche la larghezza di banda potrebbe essere un problema. Ad esempio, se un utente sta guardando video in un'altra sessione, ciò influirà sulle prestazioni della pagina SharePoint. Anche se non puoi impedire agli utenti di trasmettere contenuti multimediali, puoi controllare il modo in cui una pagina verrà caricata per gli utenti.
  
Vedere gli articoli seguenti per le diverse tecniche di personalizzazione delle pagine di SharePoint Online e altre procedure consigliate per ottenere prestazioni ottimali.
  
- [Opzioni di spostamento per SharePoint Online](navigation-options-for-sharepoint-online.md)
    
- [Usare lo strumento Diagnostica pagine per SharePoint Online](page-diagnostics-for-spo.md)
    
- [Ottimizzazione delle immagini per SharePoint Online](image-optimization-for-sharepoint-online.md)
    
- [Ritardo caricamento immagini e JavaScript in SharePoint Online](delay-loading-images-and-javascript-in-sharepoint-online.md)
    
- [Minimizzazione e creazione di bundle in SharePoint Online](minification-and-bundling-in-sharepoint-online.md)
    
- [Usare la rete per la distribuzione di contenuti di Office 365 con SharePoint Online](use-microsoft-365-cdn-with-spo.md)
    
- [Utilizzo della web part Ricerca contenuto anziché della web part Query contenuto per migliorare le prestazioni in SharePoint Online](using-content-search-web-part-instead-of-content-query-web-part-to-improve-perfo.md)
    
- [Pianificazione della capacità e test di carico di SharePoint Online](capacity-planning-and-load-testing-sharepoint-online.md)
    
- [Diagnosi dei problemi delle prestazioni con SharePoint Online](diagnosing-performance-issues-with-sharepoint-online.md)
    
- [Utilizzo della cache oggetti con SharePoint Online](using-the-object-cache-with-sharepoint-online.md)
    
- [Procedura: Evitare la limitazione o il blocco in SharePoint Online](https://msdn.microsoft.com/library/office/dn889829.aspx)
    

