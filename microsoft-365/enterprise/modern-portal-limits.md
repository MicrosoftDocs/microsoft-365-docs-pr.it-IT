---
title: Limiti dei siti portale moderni di SharePoint Online
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
description: Informazioni sui suggerimenti sulle prestazioni per i siti moderni in SharePoint Online, ad esempio la limitazione delle chiamate a SharePoint e agli endpoint esterni.
ms.openlocfilehash: 2afca20183bef8c8f6dda9bdc35a44e5153ef07c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691406"
---
# <a name="sharepoint-online-modern-portal-site-limits"></a>Limiti dei siti portale moderni di SharePoint Online

In questo articolo vengono forniti suggerimenti sulle prestazioni per i siti portale moderni in SharePoint Online. Utilizzare le linee guida riportate in questo articolo per ottimizzare le prestazioni moderne del sito portale ed evitare problemi comuni relativi alle prestazioni.

## <a name="performance-considerations-for-modern-portal-sites"></a>Considerazioni sulle prestazioni per i siti portale moderni

Dal punto di vista dell'ottimizzazione delle prestazioni, esistono alcune caratteristiche che rendono univoci i siti portale moderni. La differenza principale tra la collaborazione e i siti portale in SharePoint Online è la scalabilità. In genere, i siti portale servono più visualizzazioni di pagina a un numero maggiore di utenti rispetto ai siti di collaborazione e probabilmente conterranno più contenuto statico e meno risorse modificabili. Inoltre, l'architettura dei siti moderni è diversa dai siti classici, in quanto la maggior parte dell'elaborazione coinvolta nel rendering delle pagine e nell'esecuzione del codice avviene nel client anziché nel server.

L'ottimizzazione delle prestazioni per i siti portale moderni si concentra principalmente su alcuni obiettivi generali:

- Ridurre le dimensioni totali dei componenti di ogni pagina del sito
- Offload hosting of common static files such as images, stylesheets and scripts to CDN
- Limitare le chiamate a SharePoint e agli endpoint esterni solo a ciò che è necessario
- Evitare richieste duplicate per lo stesso contenuto

Molte delle linee guida in questo articolo sono incentrate sulla riduzione al minimo e sull'ottimizzazione delle chiamate a SharePoint Online. L'esecuzione di chiamate ripetitive ogni volta che viene caricata una pagina inciderà sulle prestazioni per gli utenti, in quanto le informazioni verranno recuperate dal servizio ogni volta, anche se non sono state modificate. Di conseguenza, le richieste a SharePoint possono essere categorizzate come chiamate comuni per tutti gli utenti o chiamate richieste per ogni singolo utente. I risultati di queste due categorie di chiamata devono essere memorizzati nella cache per ottimizzare l'esperienza utente.

>[!NOTE]
>Utilizzare lo [strumento Diagnostica pagine per SharePoint](https://aka.ms/perftool) come punto di partenza per analizzare metriche delle prestazioni specifiche nelle pagine del sito di SharePoint Online.

## <a name="modern-portal-site-limits-and-recommendations"></a>Suggerimenti e limiti per i siti portale moderni

|**Tipo di limite**|**Valore massimo consigliato**|**Note**|
|:-----|:-----|:-----|:-----|
|Pagine ed elementi di notizie  <br/> |5.000 per sito  <br/> |È consigliabile limitare il numero di pagine e notizie in un sito portale moderno a un numero inferiore a 5.000.  <br/> |
|Web part in una pagina  <br/> |20 per pagina  <br/> |È consigliabile utilizzare un totale di 20 web part per pagina, incluse web part Microsoft e web part personalizzate. <br/> Per ulteriori informazioni, vedere [Ottimizzare le prestazioni delle web part nelle pagine moderne dei siti di SharePoint Online.](modern-web-part-optimization.md)  <br/> |
|Web part dinamiche in una pagina  <br/> |4 per pagina  <br/> |Le web part dinamiche che effettuano una o più query in SharePoint per recuperare i dati più recenti devono essere limitate a 4 per pagina. La _web_ part Notizie è un esempio di web part dinamica. <br/> Per ulteriori informazioni, vedere [Ottimizzare le prestazioni delle web part nelle pagine moderne dei siti di SharePoint Online.](modern-web-part-optimization.md)    <br/> |
|Gruppi di sicurezza  <br/> |20 per sito  <br/> |Il numero di gruppi di sicurezza influisce sulla scala di molte query nei siti portale moderni. È consigliabile limitare il numero di gruppi di sicurezza a un set il più piccolo possibile, con un massimo di 20 per sito.  <br/> |
|Elementi nella struttura di spostamento del sito  <br/> |100 per sito  <br/> |È consigliabile aggiungere meno di 100 elementi alla struttura di spostamento del sito e utilizzare i controlli di spostamento personalizzati.  <br/> Per ulteriori informazioni, vedere [Ottimizzare il peso della pagina nelle pagine moderne del sito di SharePoint Online.](modern-page-weight-optimization.md) <br/> |
|Dimensioni massime immagine  <br/> |300 Kb per immagine  <br/> |È consigliabile limitare le dimensioni delle immagini a 300 kb o a dimensioni inferiori e utilizzare una rete CDN per ospitare immagini, fogli di stile e script. <br/>Per ulteriori informazioni, vedere Ottimizzare le immagini nelle pagine moderne del sito di [SharePoint Online](modern-image-optimization.md) e Usare la rete per la distribuzione di contenuti [(CDN) di Office 365 con SharePoint Online.](use-microsoft-365-cdn-with-spo.md)  <br/> |
|Utenti con diritti di modifica  <br/> |200 utenti per sito  <br/> |I siti portale di SharePoint sono ottimizzati per la visualizzazione e l'utilizzo del contenuto. Le autorizzazioni di modifica in un portale devono essere limitate a un gruppo limitato di utenti, perché le autorizzazioni di modifica scaricano controlli aggiuntivi e pertanto avranno prestazioni più lente per tali utenti. Un numero eccessivo di utenti con autorizzazioni di modifica influirà pertanto sull'esperienza complessiva. <br/> |
|IFrame di terze parti  <br/> |2 per pagina  <br/> |Gli iFrame sono imprevedibilmente lenti perché caricano una pagina esterna separata, incluso tutto il contenuto associato, ad esempio gli elementi javascript, CSS e framework. Se devi usare gli iFrame, limitane il numero a 2 o meno per pagina.<br/> Per ulteriori informazioni, vedere Ottimizzare gli iFrame nelle pagine moderne e classiche del sito [di pubblicazione di SharePoint Online.](modern-iframe-optimization.md) <br/> |
|Chiamate al servizio UPA  <br/> |1 per utente all'ora  <br/> |È consigliabile non effettuare _chiamate per_ richiesta al servizio UPA (User Profile Application). [L'API di Microsoft Graph](https://docs.microsoft.com/graph/call-api) e [PageContext](https://docs.microsoft.com/javascript/api/sp-page-context/pagecontext?view=sp-typescript-latest) possono essere usati per eseguire query per ottenere informazioni sull'utente.  <br/> Se è necessaria una chiamata al servizio UPA, effettuare una singola chiamata quando necessario e quindi memorizzare nella cache le informazioni per il riutilizzo nella stessa sessione. |
|Chiamate al servizio tassonomia  <br/> |5 per utente all'ora  <br/> |È consigliabile non effettuare _chiamate per_ richiesta al servizio tassonomia. Se sono necessarie chiamate al servizio tassonomia, memorizzare nella cache le informazioni per il riutilizzo nella stessa sessione. <br/> Per ulteriori informazioni, vedere Ottimizzare le chiamate di pagina nelle pagine moderne e classiche del sito [di pubblicazione di SharePoint Online.](modern-page-call-optimization.md) <br/> |

## <a name="related-topics"></a>Argomenti correlati

[Creazione di un portale di SharePoint integro](https://docs.microsoft.com/sharepoint/portal-health)

[Ottimizzare le prestazioni di SharePoint Online](tune-sharepoint-online-performance.md)

[Ottimizzare le prestazioni di Office 365](tune-microsoft-365-performance.md)

[Limiti di SharePoint Online](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)

[Prestazioni nell'esperienza moderna di SharePoint](https://docs.microsoft.com/sharepoint/modern-experience-performance)

[Indicazioni sulle prestazioni per i portali di SharePoint Online](https://docs.microsoft.com/sharepoint/dev/solution-guidance/portal-performance)
