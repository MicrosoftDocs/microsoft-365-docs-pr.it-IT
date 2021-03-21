---
title: Ottimizzare gli iFrame nelle pagine classiche e moderne del sito di pubblicazione di SharePoint Online
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
ms.custom: Adm_O365
ms.reviewer: sstewart
search.appverid:
- MET150
description: Informazioni su come ottimizzare le prestazioni degli iFrame nelle pagine classiche e moderne del sito di pubblicazione di SharePoint Online.
ms.openlocfilehash: d6e9aefa23972589c752540959b17f5d20ed0889
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923060"
---
# <a name="optimize-iframes-in-sharepoint-online-modern-and-classic-publishing-site-pages"></a>Ottimizzare gli iFrame nelle pagine classiche e moderne del sito di pubblicazione di SharePoint Online

Gli iFrame possono essere utili per visualizzare in anteprima contenuto complesso, ad esempio video o altri elementi multimediali. Tuttavia, poiché gli iFrame caricano una pagina distinta nella pagina del sito di SharePoint, il contenuto caricato nell'iFrame potrebbe contenere immagini, video o altri elementi di grandi dimensioni che incidono sui tempi di caricamento complessivi della pagina e che non è possibile controllare nella pagina. Questo articolo illustra come determinare il modo in cui gli iFrame nelle pagine influiscono sulla latenza percepita dall'utente e su come risolvere i problemi comuni.

>[!NOTE]
>Per altre informazioni sulle prestazioni nei siti moderni di SharePoint Online, vedere [Prestazioni nell'esperienza moderna di SharePoint](/sharepoint/modern-experience-performance).

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-web-parts-using-iframes"></a>Usare lo strumento Diagnostica pagine per SharePoint per analizzare le Web part che usano iFrame

Lo strumento Diagnostica pagine per SharePoint è un'estensione del browser per il nuovo browser Microsoft Edge (https://www.microsoft.com/edge) e per Chrome che consente di analizzare le pagine del sito di pubblicazione di SharePoint Online sia classiche che dei portali moderni. Per ogni pagina analizzata lo strumento fornisce un report che mostra le prestazioni della pagina rispetto a un set definiti di criteri delle prestazioni. Per installare e conoscere lo strumento Diagnostica pagine per SharePoint, visitare [Usare lo strumento Diagnostica pagine per SharePoint Online](page-diagnostics-for-spo.md).

>[!NOTE]
>Lo strumento Diagnostica pagine funziona solo per SharePoint Online e non può essere usato in una pagina di sistema di SharePoint.

Quando si analizza una pagina del sito di SharePoint con lo strumento Diagnostica pagine per SharePoint, è possibile visualizzare le informazioni sulle Web part che contengono iFrame nel riquadro _Diagnostic tests_ (Test diagnostici). La metrica di base è la stessa per le pagine classiche e moderne.

I risultati possibili includono:

- **Attention required** (rosso): attenzione richiesta, la pagina contiene **tre o più** Web part che usano iFrame
- **Improvement opportunities** (giallo): opportunità di miglioramento, la pagina contiene **una o due** Web part che usano iFrame
- **No action required** (verde): nessuna azione necessaria, la pagina non contiene Web part che usano iFrame

Se il risultato **Web parts using iFrames detected** (Rilevate Web che usano iFrame) compare nella sezione **Improvement opportunities** o **Attention required** dei risultati, fare clic sul risultato per vedere le Web part che contengono iFrame.

![Risultato dello strumento Diagnostica pagine](../media/modern-portal-optimization/pagediag-iframe-yellow.png)

## <a name="remediate-iframe-performance-issues"></a>Risolvere i problemi di prestazioni degli iFrame

Usare il risultato **Web parts using iFrames detected** (Rilevate Web che usano iFrame) nello strumento Diagnostica pagine per determinare quali Web part contengono iFrame e potrebbero contribuire a rallentare i tempi di caricamento delle pagine.

Gli iFrame sono intrinsecamente lenti perché caricano una pagina esterna separata che include tutto il contenuto associato, come elementi JavaScript, CSS e framework, aumentando potenzialmente il sovraccarico della pagina del sito di un fattore di due o più.

Seguire le indicazioni riportate di seguito per garantire un uso ottimale degli iFrame.

- Se possibile, usare immagini al posto degli iFrame se l'anteprima è piccola o non interattiva.
- Se è necessario usare gli iFrame, ridurne il numero al minimo e/o spostarli all’esterno del viewport.
- I file di Office incorporati, come i file di Word, Excel e PowerPoint, sono interattivi, ma sono lenti da caricare. Anteprime delle immagini con un collegamento al documento completo offriranno spesso prestazioni migliori.
- I video di YouTube e i feed di Twitter incorporati tendono a offrire prestazioni migliori negli iFrame, ma questi tipi di incorporamento vanno usati con giudizio.
- Le Web part isolate rappresentano un'eccezione accettabile, ma ridurne al minimo il numero e l'impiego nel viewport.
- Se un iFrame si trova all'esterno del viewport, è consigliabile usare un _IntersectionObserver_ per posticipare il rendering dell'iFrame al momento in cui diventa visibile.

Prima di eseguire le revisioni delle pagine per correggere i problemi di prestazioni, prendere nota del tempo di caricamento delle pagine nei risultati dell'analisi. Eseguire di nuovo lo strumento dopo la revisione per verificare se il nuovo risultato è compreso nello standard di base e controllare il nuovo tempo di caricamento della pagina per verificare se c'è stato un miglioramento.

![Risultati del tempo di caricamento delle pagine](../media/modern-portal-optimization/pagediag-page-load-time.png)

>[!NOTE]
>Il tempo di caricamento delle pagine dipende da numerosi fattori, ad esempio il carico di rete, l'ora del giorno e altre condizioni transitorie. È consigliabile verificare il tempo di caricamento delle pagine alcune volte prima e dopo aver apportato modifiche in modo da ottenere una media dei risultati.

## <a name="related-topics"></a>Argomenti correlati

[Ottimizzare le prestazioni di SharePoint Online](tune-sharepoint-online-performance.md)

[Ottimizzare le prestazioni di Office 365](tune-microsoft-365-performance.md)

[Prestazioni nell'esperienza moderna di SharePoint](/sharepoint/modern-experience-performance)