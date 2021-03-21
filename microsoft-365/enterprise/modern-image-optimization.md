---
title: Ottimizzare le immagini nelle pagine moderne di siti di SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 03/11/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.reviewer: sstewart
search.appverid:
- MET150
description: Informazioni su come usare gli strumenti inclusi in SharePoint Online per ottimizzare le immagini nelle pagine dei siti moderni di SharePoint Online.
ms.openlocfilehash: a4f2def86e1378a9fb76ae9ecbe6a55da75ecffc
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923017"
---
# <a name="optimize-images-in-sharepoint-online-modern-site-pages"></a>Ottimizzare le immagini nelle pagine moderne di siti di SharePoint Online

Questo articolo spiega come ottimizzare le immagini nelle pagine moderne di siti di SharePoint Online.

Per informazioni su come ottimizzare le immagini in siti di pubblicazione classici, vedere [Ottimizzazione delle immagini per SharePoint Online](image-optimization-for-sharepoint-online.md).

>[!NOTE]
>Per altre informazioni sulle prestazioni nei portali moderni di SharePoint Online, vedere [Prestazioni nell'esperienza moderna di SharePoint](/sharepoint/modern-experience-performance).

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-image-optimization"></a>Usare lo strumento Diagnostica pagine per SharePoint per analizzare l'ottimizzazione delle immagini

Lo strumento Diagnostica pagine per SharePoint è un'estensione del browser per il nuovo browser Microsoft Edge (https://www.microsoft.com/edge) e per Chrome che consente di analizzare le pagine del sito di pubblicazione di SharePoint Online sia classiche che dei portali moderni. Per ogni pagina analizzata lo strumento fornisce un report che mostra le prestazioni della pagina rispetto a un set definiti di criteri delle prestazioni. Per installare e conoscere lo strumento Diagnostica pagine per SharePoint, visitare [Usare lo strumento Diagnostica pagine per SharePoint Online](page-diagnostics-for-spo.md).

>[!NOTE]
>Lo strumento Diagnostica pagine funziona solo per SharePoint Online e non può essere usato in una pagina di sistema di SharePoint.

Quando si analizza un sito moderno di SharePoint con lo strumento Diagnostica pagine per SharePoint, è possibile visualizzare le informazioni sulle immagini di grandi dimensioni nel riquadro _Test diagnostici_.

I risultati possibili includono:

- **Attenzione** (rosso): la pagina contiene **una o più** immagini di dimensioni superiori a 300 KB
- **Non è richiesto alcun intervento** (verde): la pagina non contiene immagini di dimensioni superiori a 300 KB

Se nella sezione dei risultati **Attenzione** viene visualizzato il risultato **Sono state rilevate immagini di grandi dimensioni**, è possibile fare clic sul risultato per visualizzare altri dettagli.

![Risultati dello strumento Diagnostica pagine](../media/modern-portal-optimization/pagediag-large-images.png)

## <a name="remediate-large-image-issues"></a>Risolvere i problemi relativi a immagini di grandi dimensioni

Se una pagina contiene immagini di dimensioni superiori a 300 KB, selezionare il risultato **Sono state rilevate immagini di grandi dimensioni** per visualizzare le immagini di dimensioni eccessive. Nelle pagine moderne di SharePoint Online i rendering delle immagini vengono forniti e ridimensionati automaticamente a seconda delle dimensioni della finestra del browser e della risoluzione del monitor client. È consigliabile ottimizzare sempre le immagini per l'uso Web prima di caricarle in SharePoint Online. Le dimensioni e la risoluzione di immagini di grandi dimensioni verranno ridotte automaticamente e questa riduzione può influire sul rendering.

Prima di revisionare le pagine per correggere i problemi di prestazioni, prendere nota del tempo di caricamento delle pagine nei risultati dell'analisi. Eseguire di nuovo lo strumento dopo la revisione per verificare se il nuovo risultato è compreso nello standard di base e controllare il nuovo tempo di caricamento della pagina per verificare se c'è stato un miglioramento.

![Risultati del tempo di caricamento delle pagine](../media/modern-portal-optimization/pagediag-page-load-time.png)

>[!NOTE]
>Il tempo di caricamento delle pagine dipende da numerosi fattori, ad esempio il carico di rete, l'ora del giorno e altre condizioni transitorie. È consigliabile verificare il tempo di caricamento delle pagine alcune volte prima e dopo aver apportato modifiche in modo da ottenere una media dei risultati.

## <a name="related-topics"></a>Argomenti correlati

[Ottimizzare le prestazioni di SharePoint Online](tune-sharepoint-online-performance.md)

[Ottimizzare le prestazioni di Office 365](tune-microsoft-365-performance.md)

[Prestazioni nell'esperienza moderna di SharePoint](/sharepoint/modern-experience-performance)

[Reti per la distribuzione di contenuti](content-delivery-networks.md)

[Usare la rete per la distribuzione di contenuti di Office 365 con SharePoint Online](use-microsoft-365-cdn-with-spo.md)