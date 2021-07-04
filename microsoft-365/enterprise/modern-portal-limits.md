---
title: SharePoint Limiti del sito portale moderno online
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
description: Informazioni sui suggerimenti sulle prestazioni per i siti moderni in SharePoint Online, ad esempio la limitazione delle chiamate a Sharepoint e agli endpoint esterni.
ms.openlocfilehash: 2429869c5397e0260876ee5a765ea18ae3fc42a1
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288876"
---
# <a name="sharepoint-online-modern-portal-site-limits"></a>SharePoint Limiti del sito portale moderno online

In questo articolo vengono forniti suggerimenti sulle prestazioni per i siti portale moderni in SharePoint Online. Utilizzare le linee guida in questo articolo per ottimizzare le prestazioni moderne del sito portale ed evitare problemi comuni relativi alle prestazioni.

## <a name="performance-considerations-for-modern-portal-sites"></a>Considerazioni sulle prestazioni per i siti portale moderni

Dal punto di vista dell'ottimizzazione delle prestazioni, esistono alcune caratteristiche che rendono unici i siti portale moderni. La differenza principale tra la collaborazione e i siti portale in SharePoint Online è la scalabilità. In genere, i siti portale serviranno più visualizzazioni di pagina a un numero maggiore di utenti rispetto ai siti di collaborazione e probabilmente conterranno più contenuto statico e meno risorse modificabili. Inoltre, l'architettura dei siti moderni è diversa dai siti classici, in quanto la maggior parte dell'elaborazione implicata nel rendering delle pagine e nell'esecuzione del codice avviene sul client anziché sul server.

L'ottimizzazione delle prestazioni per i siti portale moderni è incentrata principalmente su alcuni obiettivi generali:

- Ridurre le dimensioni totali dei componenti di ogni pagina del sito
- Offload hosting di file statici comuni, ad esempio immagini, fogli di stile e script rete CDN
- Limitare le chiamate SharePoint endpoint esterni solo a ciò che è necessario
- Evitare richieste duplicate per lo stesso contenuto

Molte delle linee guida in questo articolo sono incentrate sulla riduzione al minimo e sull'ottimizzazione delle chiamate a SharePoint Online. L'esecuzione di chiamate ripetitive ogni volta che viene caricata una pagina influisce sulle prestazioni per gli utenti, in quanto le informazioni verranno recuperate dal servizio ogni volta, anche se non sono state modificate. Di conseguenza, le richieste SharePoint possono essere classificate come chiamate comuni per tutti gli utenti o chiamate necessarie per ogni singolo utente. I risultati di queste due categorie di chiamate devono essere memorizzati nella cache per ottimizzare l'esperienza utente.

>[!NOTE]
>Usare lo [strumento Diagnostica pagine per SharePoint come](./page-diagnostics-for-spo.md) punto di partenza per analizzare metriche delle prestazioni specifiche nelle pagine del sito SharePoint Online.

## <a name="modern-portal-site-limits-and-recommendations"></a>Suggerimenti e limiti per i siti portale moderni

|**Tipo di limite**|**Valore massimo consigliato**|**Note**|
|:-----|:-----|:-----|:-----|
|Pagine ed elementi di notizie  <br/> |5.000 per sito  <br/> |È consigliabile limitare il numero di pagine ed elementi di notizie in un sito portale moderno a un valore inferiore a 5.000.  <br/> |
|Web part in una pagina  <br/> |20 per pagina  <br/> |È consigliabile utilizzare 20 o meno web part totali per pagina, incluse sia le web part Microsoft che le web part personalizzate. <br/> Per ulteriori informazioni, vedere [Optimize web part performance in SharePoint Online modern site pages](modern-web-part-optimization.md).  <br/> |
|Web part dinamiche in una pagina  <br/> |4 per pagina  <br/> |Le web part dinamiche che effettuano una o più query SharePoint recuperare i dati più recenti devono essere limitate a 4 per pagina. La _web_ part Notizie è un esempio di web part dinamica. <br/> Per ulteriori informazioni, vedere [Optimize web part performance in SharePoint Online modern site pages](modern-web-part-optimization.md).    <br/> |
|Gruppi di sicurezza  <br/> |20 per sito  <br/> |Il numero di gruppi di sicurezza influisce sulla scala di molte query nei siti portale moderni. È consigliabile limitare il numero di gruppi di sicurezza a un set il più piccolo possibile, con non più di 20 per sito.  <br/> |
|Elementi nella struttura di spostamento del sito  <br/> |100 per sito  <br/> |È consigliabile aggiungere meno di 100 elementi alla struttura di spostamento del sito e utilizzare i controlli di spostamento personalizzati.  <br/> Per ulteriori informazioni, vedere [Optimize page weight in SharePoint Online modern site pages](modern-page-weight-optimization.md). <br/> |
|Dimensioni massime immagine  <br/> |300 Kb per immagine  <br/> |È consigliabile limitare le dimensioni delle immagini a 300 kb o a dimensioni inferiori e usare un rete CDN per ospitare immagini, fogli di stile e script. <br/>Per ulteriori informazioni, vedere [Optimize images in SharePoint Online modern site pages](modern-image-optimization.md) e Use the Office 365 rete per la distribuzione di contenuti [(rete CDN) with SharePoint Online.](use-microsoft-365-cdn-with-spo.md)  <br/> |
|Utenti con diritti di modifica  <br/> |200 utenti per sito  <br/> |SharePoint siti portale sono ottimizzati per la visualizzazione e l'utilizzo del contenuto. Le autorizzazioni di modifica in un portale devono essere limitate a un gruppo limitato di utenti, perché le autorizzazioni di modifica scaricano controlli aggiuntivi e pertanto avranno prestazioni più lente per tali utenti. Un numero eccessivo di utenti con autorizzazioni di modifica influirà pertanto sull'esperienza complessiva. <br/> |
|IFrame di terze parti  <br/> |2 per pagina  <br/> |Gli iFrame sono imprevedibilmente lenti perché caricano una pagina esterna separata, incluso tutto il contenuto associato, ad esempio elementi javascript, CSS ed elementi framework. Se devi usare iFrame, limitane il numero a 2 o meno per pagina.<br/> Per ulteriori informazioni, vedere [Optimize iFrames in SharePoint online modern and classic publishing site pages](modern-iframe-optimization.md). <br/> |
|Chiamate al servizio UPA  <br/> |1 per utente all'ora  <br/> |È consigliabile non effettuare chiamate _per richiesta_ al servizio UPA (User Profile Application). [L'API Graph](/graph/call-api) Microsoft e [PageContext](/javascript/api/sp-page-context/pagecontext) possono essere usati per eseguire query per ottenere informazioni sull'utente.  <br/> Se è necessaria una chiamata al servizio UPA, effettuare una singola chiamata quando necessario e quindi memorizzare nella cache le informazioni per il riutilizzo nella stessa sessione. |
|Chiamate al servizio tassonomia  <br/> |5 per utente all'ora  <br/> |È consigliabile non effettuare chiamate _per richiesta_ al servizio tassonomia. Se sono necessarie chiamate al servizio tassonomia, memorizzare nella cache le informazioni per il riutilizzo nella stessa sessione. <br/> Per ulteriori informazioni, vedere [Optimize page calls in SharePoint Online modern and classic publishing site pages](modern-page-call-optimization.md). <br/> |

## <a name="related-topics"></a>Argomenti correlati

[Creazione di un portale SharePoint integro](/sharepoint/portal-health)

[Ottimizzare le prestazioni di SharePoint Online](tune-sharepoint-online-performance.md)

[Ottimizzare le prestazioni di Office 365](tune-microsoft-365-performance.md)

[Limiti di SharePoint Online](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)

[Prestazioni nell'esperienza moderna di SharePoint](/sharepoint/modern-experience-performance)

[Indicazioni sulle prestazioni per i portali di SharePoint Online](/sharepoint/dev/solution-guidance/portal-performance)
