---
title: Limiti del sito portale moderno di SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 10/9/2019
audience: Admin
ms.topic: interactive-tutorial
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_Enterprise
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
description: Informazioni sui consigli sulle prestazioni per i siti moderni in SharePoint Online, ad esempio la limitazione delle chiamate a SharePoint e gli endpoint esterni.
ms.openlocfilehash: 2afca20183bef8c8f6dda9bdc35a44e5153ef07c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691406"
---
# <a name="sharepoint-online-modern-portal-site-limits"></a>Limiti del sito portale moderno di SharePoint Online

In questo articolo vengono fornite indicazioni per le prestazioni per i siti portale moderni in SharePoint Online. Utilizzare le linee guida contenute in questo articolo per ottimizzare le prestazioni dei siti portale moderni ed evitare problemi di prestazioni comuni.

## <a name="performance-considerations-for-modern-portal-sites"></a>Considerazioni sulle prestazioni per i siti portale moderni

Dal punto di vista dell'ottimizzazione delle prestazioni, esistono alcune caratteristiche che rendono i siti portale moderni unici. La differenza principale tra la collaborazione e i siti portale in SharePoint Online è la scalabilità. I siti portale generalmente dovrebbero servire altre visualizzazioni di pagina a un numero maggiore di utenti rispetto ai siti di collaborazione e probabilmente conterranno contenuto più statico e meno risorse modificabili. Inoltre, l'architettura dei siti moderni è diversa da quella classica, in quanto la maggior parte dei processi coinvolti nelle pagine di rendering e l'esecuzione di codice avviene sul client anziché sul server.

L'ottimizzazione delle prestazioni per i siti portale moderni è principalmente incentrata su alcuni obiettivi generali:

- Ridurre le dimensioni totali dei componenti di ogni pagina del sito
- Scaricare l'hosting di file statici comuni, ad esempio immagini, fogli di stile e script, per la rete CDN
- Limitare le chiamate a SharePoint e endpoint esterni solo a ciò che è necessario
- Evitare richieste duplicate per lo stesso contenuto

Molte delle linee guida contenute in questo articolo sono incentrate sulla riduzione a icona e sull'ottimizzazione delle chiamate a SharePoint Online. Effettuare chiamate ripetitive ogni volta che viene caricata una pagina avrà un impatto sulle prestazioni per gli utenti, in quanto le informazioni verranno recuperate dal servizio ogni volta, anche se non è stata modificata. In questo modo, le richieste a SharePoint possono essere categorizzate come chiamate comuni a tutti gli utenti o chiamate richieste per ogni singolo utente. I risultati di queste due categorie di chiamate devono essere memorizzati nella cache per ottimizzare l'esperienza dell'utente.

>[!NOTE]
>Utilizzare lo [strumento page Diagnostics for SharePoint](https://aka.ms/perftool) come punto di partenza per analizzare specifiche metriche delle prestazioni nelle pagine del sito di SharePoint Online.

## <a name="modern-portal-site-limits-and-recommendations"></a>Limiti e suggerimenti per i siti portale moderni

|**Tipo di limite**|**Valore massimo consigliato**|**Note**|
|:-----|:-----|:-----|:-----|
|Pagine e elementi di notizie  <br/> |5.000 per sito  <br/> |È consigliabile limitare il numero di pagine e di notizie presenti in un sito portale moderno al di sotto di 5.000.  <br/> |
|Web part in una pagina  <br/> |20 per pagina  <br/> |È consigliabile utilizzare 20 o meno Web part totali per pagina, incluse le web part Microsoft e le web part personalizzate. <br/> Per ulteriori informazioni, vedere [ottimizzare le prestazioni delle web part nelle pagine del sito di SharePoint Online moderne](modern-web-part-optimization.md).  <br/> |
|Web part dinamiche in una pagina  <br/> |4 per pagina  <br/> |Le web part dinamiche che effettuano una o più query a SharePoint per recuperare i dati più recenti devono essere limitate a 4 per pagina. La Web part _notizie_ è un esempio di una Web part dinamica. <br/> Per ulteriori informazioni, vedere [ottimizzare le prestazioni delle web part nelle pagine del sito di SharePoint Online moderne](modern-web-part-optimization.md).    <br/> |
|Gruppi di sicurezza  <br/> |20 per sito  <br/> |Il numero di gruppi di sicurezza influisce sulla scala di numerose query nei siti portale moderni. È consigliabile limitare il numero di gruppi di sicurezza a un insieme di dimensioni più piccole possibile, con un massimo di 20 per sito.  <br/> |
|Elementi nella struttura di spostamento del sito  <br/> |100 per sito  <br/> |È consigliabile aggiungere meno di 100 elementi alla struttura di spostamento del sito e utilizzare i controlli di spostamento non consentiti.  <br/> Per ulteriori informazioni, vedere [ottimizzare la ponderazione della pagina nelle pagine del sito di SharePoint Online moderne](modern-page-weight-optimization.md). <br/> |
|Dimensioni massime dell'immagine  <br/> |300 KB per immagine  <br/> |È consigliabile limitare le dimensioni delle immagini a 300kb o più piccole e utilizzare una rete CDN per ospitare immagini, fogli di stile e script. <br/>Per ulteriori informazioni, vedere [ottimizzare le immagini nelle pagine del sito di SharePoint Online](modern-image-optimization.md) e [utilizzare la rete di distribuzione dei contenuti (CDN) di Office 365 con SharePoint Online](use-microsoft-365-cdn-with-spo.md).  <br/> |
|Utenti con diritti di modifica  <br/> |200 utenti per sito  <br/> |I siti portale di SharePoint sono ottimizzati per la visualizzazione e l'utilizzo di contenuto. Le autorizzazioni di modifica per un portale devono essere limitate a un gruppo limitato di utenti, perché le autorizzazioni di modifica scaricano ulteriori controlli e quindi eseguono una maggiore lentezza per tali utenti. Un numero eccessivo di utenti con autorizzazioni di modifica influenzerà pertanto l'esperienza complessiva. <br/> |
|IFrame di terze parti  <br/> |2 per pagina  <br/> |gli iFrame sono inaspettatamente lenti perché caricano una pagina esterna separata, inclusi tutti i contenuti associati, ad esempio JavaScript, CSS e gli elementi del Framework. Se è necessario utilizzare gli iFrame, limitare il numero a 2 o meno per ogni pagina.<br/> Per ulteriori informazioni, vedere [optimize iframes in SharePoint Online Modern and Classic Publishing site pages](modern-iframe-optimization.md). <br/> |
|Chiamate al servizio UPA  <br/> |1 per utente all'ora  <br/> |Si consiglia di non effettuare chiamate per _richiesta_ al servizio UPA (user profile Application). È possibile utilizzare l' [API di Microsoft Graph](https://docs.microsoft.com/graph/call-api) e [PageContext](https://docs.microsoft.com/javascript/api/sp-page-context/pagecontext?view=sp-typescript-latest) per eseguire una query per informazioni sugli utenti.  <br/> Se è necessaria una chiamata di servizio UPA, effettuare una singola chiamata quando necessario e quindi memorizzare nella cache le informazioni per il riutilizzo nella stessa sessione. |
|Chiamate al servizio di tassonomia  <br/> |5 per utente all'ora  <br/> |Si consiglia di non effettuare chiamate per _richiesta_ al servizio di tassonomia. Se le chiamate al servizio di tassonomia sono necessarie, memorizzare le informazioni riutilizzate nella stessa sessione. <br/> Per ulteriori informazioni, vedere [optimize page calls in SharePoint Online Modern and Classic Publishing site pages](modern-page-call-optimization.md). <br/> |

## <a name="related-topics"></a>Argomenti correlati

[Creazione di un portale SharePoint integro](https://docs.microsoft.com/sharepoint/portal-health)

[Ottimizzare le prestazioni di SharePoint Online](tune-sharepoint-online-performance.md)

[Ottimizzare le prestazioni di Office 365](tune-microsoft-365-performance.md)

[Limiti di SharePoint Online](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)

[Prestazioni nell'esperienza moderna di SharePoint](https://docs.microsoft.com/sharepoint/modern-experience-performance)

[Indicazioni sulle prestazioni per i portali di SharePoint Online](https://docs.microsoft.com/sharepoint/dev/solution-guidance/portal-performance)
