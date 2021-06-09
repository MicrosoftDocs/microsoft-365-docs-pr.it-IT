---
title: Ottimizzare il peso delle pagine moderne del sito in SharePoint Online
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
description: Informazioni su come usare lo strumento Diagnostica pagine per ottimizzare il peso delle pagine SharePoint pagine moderne del sito online.
ms.openlocfilehash: 780d8ca0debbc5efb834f8f3543b9a5a8d168108
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907445"
---
# <a name="optimize-page-weight-in-sharepoint-online-modern-site-pages"></a>Ottimizzare il peso delle pagine moderne del sito in SharePoint Online

Le pagine moderne del sito di SharePoint Online contengono codice serializzato necessario per il rendering del contenuto della pagina, incluse le immagini, il testo, gli oggetti nell'area del contenuto sotto le barre di spostamento e di comando e altri codici HTML che formano la struttura della pagina. Il peso della pagina è una misura di questo codice HTML e deve essere limitato per garantire tempi di caricamento delle pagine ottimali.

Questo articolo spiega come ridurre il peso della pagina nelle pagine moderne del sito.

>[!NOTE]
>Per ulteriori informazioni sulle prestazioni nei portali moderni di SharePoint Online, vedere [Prestazioni nell'esperienza moderna di SharePoint](/sharepoint/modern-experience-performance).

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-page-weight"></a>Usare lo strumento Diagnostica pagine per SharePoint per analizzare il peso delle pagine

Lo strumento Diagnostica pagine per SharePoint è un'estensione del browser per il nuovo browser Microsoft Edge (https://www.microsoft.com/edge) e per Chrome che consente di analizzare le pagine del sito di pubblicazione di SharePoint Online sia classiche che dei portali moderni. Per ogni pagina analizzata lo strumento fornisce un report che mostra le prestazioni della pagina rispetto a un set definiti di criteri delle prestazioni. Per installare e conoscere lo strumento Diagnostica pagine per SharePoint, visitare [Usare lo strumento Diagnostica pagine per SharePoint Online](page-diagnostics-for-spo.md).

>[!NOTE]
>Lo strumento Diagnostica pagine funziona solo per SharePoint Online e non può essere usato in una pagina di sistema di SharePoint.

Quando si analizza una pagina del sito di SharePoint con lo strumento Diagnostica pagine per SharePoint, è possibile visualizzare le informazioni sulla pagina nel risultato **Peso della pagina inferiore a 500 KB** del riquadro _Test diagnostici_. Il risultato sarà verde se il peso della pagina è inferiore al valore della linea di base, mentre sarà rosso se il peso della pagina supera il valore della linea di base.

I risultati possibili includono:

- **Attenzione richiesta** (rosso): il peso della pagina supera 500 KB
- **Nessuna azione richiesta** (verde): il peso della pagina è inferiore a 500 KB

Se il risultato del **Peso della pagina inferiore a 500 KB** viene visualizzato nella sezione **Attenzione richiesta**, è possibile fare clic sul risultato per consultare le informazioni dettagliate.

![Risultati delle Richieste a SharePoint](../media/modern-portal-optimization/pagediag-page-weight.png)

## <a name="remediate-page-weight-issues"></a>Risolvere i problemi di peso delle pagine

Se il peso della pagina supera 500 KB, è possibile migliorare i tempi complessivi di caricamento delle pagine, riducendo il numero di Web part e limitando il contenuto della pagina a un livello appropriato.

Le indicazioni generali per ridurre il peso della pagina includono:

- Limitare il contenuto della pagina a un livello ragionevole e usare più pagine per i contenuti correlati.
- Ridurre al minimo l'uso delle Web part con contenitori delle proprietà di grandi dimensioni.
- Usare le viste di rollup non interattive, se possibile.
- Ottimizzare le dimensioni delle immagini ridimensionando le immagini in modo appropriato, usando formati di immagine compressi e verificando che vengano scaricati da una rete CDN.

Per altre informazioni sulle indicazioni per ridurre il peso della pagina, vedere l'articolo seguente:

- [Ottimizzare le prestazioni delle pagine in SharePoint](/sharepoint/dev/general-development/optimize-page-performance-in-sharepoint)

Prima di eseguire le revisioni delle pagine per correggere i problemi di prestazioni, prendere nota del tempo di caricamento delle pagine nei risultati dell'analisi. Eseguire di nuovo lo strumento dopo la revisione per verificare se il nuovo risultato è compreso nello standard di base e controllare il nuovo tempo di caricamento della pagina per verificare se c'è stato un miglioramento.

![Risultati del tempo di caricamento delle pagine](../media/modern-portal-optimization/pagediag-page-load-time.png)

>[!NOTE]
>Il tempo di caricamento delle pagine dipende da numerosi fattori, ad esempio il carico di rete, l'ora del giorno e altre condizioni transitorie. È consigliabile verificare il tempo di caricamento delle pagine alcune volte prima e dopo aver apportato modifiche in modo da ottenere una media dei risultati.

## <a name="related-topics"></a>Argomenti correlati

[Ottimizzare le prestazioni di SharePoint Online](tune-sharepoint-online-performance.md)

[Ottimizzare le prestazioni di Office 365](tune-microsoft-365-performance.md)

[Prestazioni nell'esperienza moderna di SharePoint](/sharepoint/modern-experience-performance)

[Reti per la distribuzione di contenuti](content-delivery-networks.md)

[Usare la rete per la distribuzione di contenuti di Office 365 con SharePoint Online](use-microsoft-365-cdn-with-spo.md)