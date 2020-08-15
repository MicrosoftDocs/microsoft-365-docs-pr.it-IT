---
title: Pianificazione del piano di avvio del portale per il lancio in SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
description: In questo articolo viene descritto come pianificare il lancio del portale in SharePoint Online e quali operazioni eseguire per un'operazione di avvio con esito positivo
ms.openlocfilehash: e22fa4d9cbfed79841d844f111e3eb91a708512e
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691535"
---
# <a name="planning-your-portal-launch-roll-out-plan-in-sharepoint-online"></a>Pianificazione del piano di avvio del portale per il lancio in SharePoint Online

Un portale è un sito di SharePoint nell’Intranet con un numero elevato di utenti che ne usano il contenuto. Nelle organizzazioni di grandi dimensioni potrebbero essercene diversi, come ad esempio un portale aziendale e un portale risorse umane. In genere i portali hanno relativamente poche persone che creano il sito e il contenuto. La maggior parte dei visitatori del portale si limita a leggere e usare il contenuto.

In questo articolo viene descritto come pianificare la distribuzione e il piano di implementazione di SharePoint Online. Sono inoltre disponibili approcci da seguire come test di carico tradizionale non consentiti in SharePoint Online. SharePoint Online è un servizio cloud e le funzionalità di carico, integrità e bilanciamento del carico generale nel servizio sono gestite da Microsoft.

Per facilitare la creazione di un portale di successo, seguire i principi di base, le procedure e i consigli illustrati nella [creazione, l'avvio e la gestione di un portale integro](https://go.microsoft.com/fwlink/?linkid=2105838) 

L'approccio di distribuzione è evidenziato di seguito.

## <a name="overview-of-capacity-planning-in-sharepoint-online"></a>Panoramica della pianificazione della capacità in SharePoint Online
Per utilizzare in modo efficiente la capacità e gestire la crescita imprevista, in qualsiasi farm, è presente un'automazione che consente di tenere traccia di determinati scenari di utilizzo. Anche se la crescita esatta non è prevedibile per un tenant in una farm, la somma aggregata delle richieste è prevedibile nel tempo. Identificando le tendenze di sviluppo in SharePoint Online, è possibile pianificare la futura espansione. Per ulteriori informazioni sulla [pianificazione della capacità e sul test di carico di SharePoint Online](capacity-planning-and-load-testing-sharepoint-online.md).

Una parte fondamentale di un lancio efficace è l'approccio "Wave" o "phased roll-out" dettagliato. 

## <a name="can-i-load-test-sharepoint-online"></a>È possibile caricare test di SharePoint Online?
SharePoint Online è un ambiente multi-tenant condiviso che è bilanciato tra farm e la scala è regolata in maniera continuativa. Load testing un ambiente, come SharePoint Online, la cui scala cambia continuamente non solo darà risultati imprevisti, ma non è consentita. 

Ulteriori informazioni:  [pianificazione della capacità e test di carico di SharePoint Online](capacity-planning-and-load-testing-sharepoint-online.md)

## <a name="optimize-pages-by-following-recommended-guidelines"></a>Ottimizzare le pagine seguendo le linee guida consigliate
Le pagine di una distribuzione locale non devono essere semplicemente spostate come sono su SharePoint Online senza rivederle in base alle linee guida consigliate per SharePoint Online. L'approccio migliore consiste nell'ottimizzare sempre qualsiasi Home page per qualsiasi sito o portale in SharePoint, in quanto la maggior parte degli utenti dell'organizzazione accederà come punto di partenza per i siti.

Alcuni fattori di base devono essere considerati:
- Le distribuzioni locali possono sfruttare le cache tradizionali sul fianco del server, come la cache degli oggetti, la cache di output e la cache BLOB. Con le differenze di topologia nel cloud, queste opzioni non sono necessariamente disponibili, in quanto le differenze di scalabilità rendono gli approcci meno sostenibili.
- Tutte le pagine/caratteristiche/personalizzazioni utilizzate per il consumo di cloud devono essere ottimizzate per una latenza superiore e per i percorsi distribuiti degli utenti, in modo che gli utenti in aree geografiche diverse abbiano un'esperienza più coerente. Cloud offre ottimizzazioni come la rete per la distribuzione dei contenuti (CDN) per ottimizzare la base di utenti distribuiti e per la moderna SharePoint, l'ultimo bene conosciuto (LKG) viene utilizzato dalle web part fuori dalla casella (OOTB).

### <a name="what-to-do"></a>cosa fare:
 - Per tutte le pagine del sito in SharePoint Online, utilizzare lo [strumento di diagnostica](https://aka.ms/perftool)delle pagine, che è un'estensione Chromium che fornirà assistenza per l'analisi e la fornitura di linee guida. Questo può essere utilizzato da proprietari di siti, editori, amministratori e sviluppatori perché è stato creato come punto di partenza per l'analisi e l'ottimizzazione.
 - Gli sviluppatori dovrebbero anche usare strumenti di sviluppo come lo strumento di sviluppatore del browser F12 così come CTRL-F12 nel browser nelle pagine moderne. [Fiddler](https://www.telerik.com/download/fiddler) può anche essere utilizzato per esaminare il peso delle dimensioni, ovvero la dimensione della pagina in megabyte, e il numero di chiamate e di elementi che influiscono sul caricamento generale della pagina. 

Questa sezione è stata un breve riepilogo per ottimizzare le pagine.  Per ulteriori informazioni, vedere:  [creazione, avvio e gestione di un portale integro](https://go.microsoft.com/fwlink/?linkid=2105838).

## <a name="follow-a-wave--phased-roll-out-approach"></a>Seguire un approccio Wave/phased roll-out
L'approccio tradizionale del Big Bang per i lanci dei siti non consentirà di verificare che le personalizzazioni, le origini esterne, i servizi o i processi siano stati testati sulla scala giusta. Questo non significa che richiederà mesi per l'avvio, ma è consigliabile almeno alcuni giorni a seconda della dimensione dell'organizzazione. A seguito di un piano di roll-out Wave è pertanto possibile sospendere e risolvere i problemi prima di procedere con la fase successiva e quindi abbassare il potenziale numero di utenti che hanno un impatto su eventuali problemi. SharePoint come servizio consente di ridimensionare la capacità in base all'utilizzo e all'utilizzo previsto e anche se non è necessario avvisarci del lancio, è consigliabile seguire le linee guida per garantire il successo.
  
Come illustrato nella figura seguente, spesso il numero di utenti invitati è significativamente più elevato rispetto a quelli che utilizzano effettivamente il sito. In questa immagine viene illustrata una strategia su come eseguire il rollback di una versione. Questo metodo consente di identificare i modi per migliorare il sito di SharePoint prima che la maggior parte degli utenti lo veda.
  
![Grafico degli utenti invitati e attivi](../media/0bc14a20-9420-4986-b9b9-fbcd2c6e0fb9.png)
  
Nella fase pilota, è opportuno ottenere commenti e suggerimenti da parte degli utenti che l'organizzazione ha fiducia e sa che verranno coinvolti. In questo modo è possibile valutare la modalità di utilizzo del sistema, nonché la modalità di esecuzione.
  
Durante ciascuna delle onde, raccogliere i commenti degli utenti in merito alle caratteristiche e le prestazioni durante ogni ondata di distribuzione. Questo ha il vantaggio di introdurre lentamente il sistema e apportare miglioramenti man mano che il sistema viene utilizzato. Questo consente inoltre di reagire al carico aumentato dato che il sito viene implementato per sempre più utenti e, in combinazione con le linee guida per l'ottimizzazione delle pagine, garantisce un'esperienza positiva per gli utenti.

### <a name="what-to-do"></a>cosa fare:
- Decidere in merito alla tempistica di ogni fase e assicurarsi di avere una possibilità di contingenza/pausa, se è necessario effettuare le modifiche prima di continuare
- Pianificare il primo gruppo di utenti che si desidera abilitare, per assicurarsi di ricevere i commenti e suggerimenti necessari per andare avanti. Questo significa che, se possibile, selezionare un gruppo di utenti attivo che fornirà commenti e suggerimenti in modo tempestivo.
- Quando si pianifica ogni onda, provare a iniziare con una piccola base di utenti (meno di 5000 utenti) e quindi aumentare le dimensioni del gruppo Man mano che si procede con ogni onda. In questo modo è possibile creare un approccio scaglionato e consentire più facilmente le opportunità di pausa che potrebbero essere necessarie.
