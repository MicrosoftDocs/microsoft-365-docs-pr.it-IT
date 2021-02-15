---
title: Ottimizzare le prestazioni delle web part nelle pagine moderne di siti di SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 03/11/2020
audience: Admin
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
description: Informazioni su come usare Diagnostica pagine per ottimizzare le prestazioni delle web part nelle pagine moderne dei siti di SharePoint Online.
ms.openlocfilehash: f7b72aa8ed212147c06660585c4e58e548762c35
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519752"
---
# <a name="optimize-web-part-performance-in-sharepoint-online-modern-site-pages"></a>Ottimizzare le prestazioni delle web part nelle pagine moderne di siti di SharePoint Online

Le pagine moderne dei siti di SharePoint Online contengono web part che possono influire sui tempi di caricamento complessivi delle pagine. Questo articolo spiega come determinare l'impatto delle web part presenti nelle pagine sulla latenza percepita dall'utente e come risolvere problemi comuni.

>[!NOTE]
>Per altre informazioni sulle prestazioni nei portali moderni di SharePoint Online, vedere [Prestazioni nell'esperienza moderna di SharePoint](https://docs.microsoft.com/sharepoint/modern-experience-performance).

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-web-parts"></a>Usare lo strumento Diagnostica pagine per SharePoint per analizzare le web part

Lo strumento Diagnostica pagine per SharePoint è un'estensione del browser per il nuovo browser Microsoft Edge (https://www.microsoft.com/edge) e per Chrome che consente di analizzare le pagine del sito di pubblicazione di SharePoint Online sia classiche che dei portali moderni. Per ogni pagina analizzata lo strumento fornisce un report che mostra le prestazioni della pagina rispetto a un set definiti di criteri delle prestazioni. Per installare e conoscere lo strumento Diagnostica pagine per SharePoint, visitare [Usare lo strumento Diagnostica pagine per SharePoint Online](page-diagnostics-for-spo.md).

>[!NOTE]
>Lo strumento Diagnostica pagine funziona solo per SharePoint Online e non può essere usato in una pagina di sistema di SharePoint.

Quando si analizza una pagina del sito di SharePoint con lo strumento Diagnostica pagine per SharePoint, è possibile visualizzare informazioni sulle web part che superano la metrica di base nel risultato **Le web part influiscono sul tempo di caricamento delle pagine** del riquadro _Test diagnostici_.

I risultati possibili includono:

- **Attenzione richiesta** (rosso): qualsiasi web part _personalizzata_ visibile nel viewport (parte visibile della schermata della pagina caricata per prima) che richiede più di **due** secondi per essere caricata. Qualsiasi web part _personalizzata_ all'esterno del viewport che richiede più di **quattro** secondi per essere caricata. Il tempo di caricamento totale viene visualizzato nei risultati del test ed è suddiviso per caricamento del modulo, caricamento lazy, inizializzazione e rendering.
- **Possibilità di miglioramento** (giallo): in questa sezione sono visualizzati gli elementi che potrebbero influire sul tempo di caricamento delle pagine e che devono essere esaminati e monitorati. Tali elementi possono includere le web part Microsoft predefinite. I risultati relativi a tutte le web part Microsoft mostrati in questa sezione vengono segnalati automaticamente a Microsoft, di conseguenza **non è richiesta alcuna azione**. È opportuno aprire un ticket di supporto per l'analisi solo se si riscontra una notevole lentezza nel caricamento della pagina e **tutte le web part Microsoft** nella pagina vengono visualizzate nei risultati della sezione **Possibilità di miglioramento**. In un futuro aggiornamento dello strumento Diagnostica pagine per SharePoint i risultati verranno suddivisi ulteriormente in base alla specifica configurazione della web part Microsoft.
- **Non è richiesto alcun intervento** (verde): nessuna web part impiega più di **due** secondi per restituire dati.

Se il risultato **Le web part influiscono sul tempo di caricamento delle pagine** viene visualizzato nella sezione dei risultati **Attenzione** o **Possibilità di miglioramento**, fare clic sul risultato per visualizzare i dettagli relativi alle web part che vengono caricate lentamente. Gli aggiornamenti futuri dello strumento Diagnostica pagine per SharePoint potrebbero includere novità relative alle regole di analisi, di conseguenza assicurarsi di usare sempre la versione più recente dello strumento.

![Risultati dello strumento Diagnostica pagine](../media/modern-portal-optimization/pagediag-web-part.png)

Le informazioni disponibili nei risultati includono:

- **Autore**: indica se la web part è personalizzata oppure predefinita Microsoft
- **Nome e ID**: informazioni di identificazione utili per trovare la web part nella pagina
- **Totale**: tempo totale di caricamento della web part
- **Caricamento modulo**: tempo necessario per recuperare e caricare i componenti della web part
- **Caricamento lazy**: tempo per il caricamento posticipato delle web part non visualizzate nella sezione principale della pagina
- **Inizializzazione**: tempo necessario per l'inizializzazione della web part
- **Rendering**: tempo necessario per consentire alla web part di recuperare ed eseguire il rendering dei risultati

Queste informazioni vengono fornite per consentire a progettisti e sviluppatori di risolvere i problemi. Devono essere fornite al team di progettazione e sviluppo.

## <a name="remediate-web-part-performance-issues"></a>Risolvere i problemi di prestazioni delle web part

Seguire le indicazioni fornite in questa sezione per identificare e correggere i problemi di prestazioni relative alle web part elencati nei risultati **Le web part influiscono sul tempo di caricamento delle pagine**.

Sono tre le categorie delle possibili cause dei problemi di prestazioni delle web part. Usare le informazioni seguenti per determinare e risolvere i problemi applicabili alla propria situazione.

- Dimensioni e dipendenze dello script della web part
  - Ottimizzare lo script iniziale che esegue il rendering dello scenario principale per la _modalità di sola visualizzazione_.
  - Spostare gli scenari meno frequenti e modificare il codice della modalità, ad esempio il riquadro delle proprietà, per separare i blocchi con l'istruzione _import()_.
  - Esaminare le dipendenze del file _package.json_ per rimuovere completamente il codice inutilizzato. Spostare tutte le dipendenze relative solo a test/compilazione in devDependencies.
  - Per il download ottimale delle risorse statiche è necessario usare la rete per la distribuzione di contenuti di Office 365. Per i file _js/css_ sono preferibili origini pubbliche della rete per la distribuzione di contenuti. Per altre informazioni sull'uso della rete CDN di Office 365, vedere [Usare la rete per la distribuzione di contenuti di Office 365 con SharePoint Online](use-microsoft-365-cdn-with-spo.md).
  - Riutilizzare framework come _React_ e _Fabric imports_, che fanno parte di SharePoint Framework (SPFx). Per altre informazioni, vedere [Panoramica di SharePoint Framework](https://docs.microsoft.com/sharepoint/dev/spfx/sharepoint-framework-overview).
  - Assicurarsi di usare la versione più recente di SharePoint Framework e di eseguire l'aggiornamento alle nuove versioni non appena disponibili.
- Recupero e memorizzazione dei dati nella cache
  - Se la web part si basa su chiamate aggiuntive al server per recuperare i dati per la visualizzazione, verificare che tali API server siano veloci e/o implementare la memorizzazione nella cache sul lato client (ad esempio, l'uso di _localStorage_ o _IndexedDB_ per set più grandi).
  - Se sono necessarie più chiamate per eseguire il rendering dei dati critici, provare a eseguirle in batch nel server o a usare altri metodi per consolidare le richieste in un'unica chiamata.
  - In alternativa, se alcuni elementi dei dati richiedono una API più lenta, ma non sono essenziali per il rendering iniziale, sdoppiarli in una chiamata separata che viene eseguita dopo il rendering dei dati critici.
  - Se più parti usano gli stessi dati, usare un livello dati comune per evitare chiamate duplicate.
- Tempo di rendering
  - Qualsiasi origine di file multimediale, ad esempio immagini e video, dovrebbe essere adeguata ai limiti del contenitore, del dispositivo e/o della rete per evitare il download non necessario di risorse di grandi dimensioni. Per altre informazioni sulle dipendenze di contenuto, vedere [Usare la rete per la distribuzione di contenuti di Office 365 con SharePoint Online](use-microsoft-365-cdn-with-spo.md).
  - Evitare chiamate API che causano un adattamento dinamico del contenuto, regole CSS complesse o animazioni complicate. Per altre informazioni, vedere l'articolo su come [ridurre l'adattamento dinamico del contenuto nel browser](https://developers.google.com/speed/docs/insights/browser-reflow).
  - Evitare l'uso di attività concatenate a esecuzione prolungata. In alternativa, suddividere le attività a esecuzione prolungata in diverse code. Per altre informazioni, vedere l'articolo su come [ottimizzare l'esecuzione di JavaScript](https://developers.google.com/web/fundamentals/performance/rendering/optimize-javascript-execution).
  - Riservare lo spazio corrispondente per il rendering asincrono di elementi multimediali o visivi per evitare che i frame e gli stuttering (noti anche come _jank_) vengano ignorati.
  - Se un determinato browser non supporta una caratteristica usata nel rendering, caricare un polyfill o escludere il codice dipendente in esecuzione. Se la funzionalità non è critica, eliminare risorse quali i gestori eventi per evitare perdite di memoria.

Prima di revisionare le pagine per correggere i problemi di prestazioni, prendere nota del tempo di caricamento delle pagine nei risultati dell'analisi. Eseguire di nuovo lo strumento dopo la revisione per verificare se il nuovo risultato è compreso nello standard di base e controllare il nuovo tempo di caricamento della pagina per verificare se c'è stato un miglioramento.

![Risultati del tempo di caricamento delle pagine](../media/modern-portal-optimization/pagediag-page-load-time.png)

>[!NOTE]
>Il tempo di caricamento delle pagine dipende da numerosi fattori, ad esempio il carico di rete, l'ora del giorno e altre condizioni transitorie. È consigliabile verificare il tempo di caricamento delle pagine alcune volte prima e dopo aver apportato modifiche in modo da ottenere una media dei risultati.

## <a name="related-topics"></a>Argomenti correlati

[Ottimizzare le prestazioni di SharePoint Online](tune-sharepoint-online-performance.md)

[Ottimizzare le prestazioni di Office 365](tune-microsoft-365-performance.md)

[Prestazioni nell'esperienza moderna di SharePoint](https://docs.microsoft.com/sharepoint/modern-experience-performance)

[Reti per la distribuzione di contenuti](content-delivery-networks.md)

[Usare la rete per la distribuzione di contenuti di Office 365 con SharePoint Online](use-microsoft-365-cdn-with-spo.md)
