---
title: Pianificazione del piano di implementazione dell'avvio del portale in SharePoint Online
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
description: In questo articolo viene descritto come pianificare l'avvio del portale in SharePoint Online e i passaggi da eseguire per un avvio corretto
ms.openlocfilehash: e22fa4d9cbfed79841d844f111e3eb91a708512e
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691535"
---
# <a name="planning-your-portal-launch-roll-out-plan-in-sharepoint-online"></a>Pianificazione del piano di implementazione dell'avvio del portale in SharePoint Online

Un portale è un sito di SharePoint nell’Intranet con un numero elevato di utenti che ne usano il contenuto. Nelle organizzazioni di grandi dimensioni potrebbero essercene diversi, come ad esempio un portale aziendale e un portale risorse umane. In genere i portali hanno relativamente poche persone che creano il sito e il contenuto. La maggior parte dei visitatori del portale si limita a leggere e usare il contenuto.

In questo articolo viene descritto come pianificare il piano di distribuzione e implementazione in SharePoint Online. Vengono inoltre forniti approcci da seguire poiché il test di carico tradizionale non è consentito in SharePoint Online. SharePoint Online è un servizio cloud e le funzionalità di carico, l'integrità e l'equilibrio complessivo del carico nel servizio sono gestiti da Microsoft.

Per facilitare la creazione di un portale efficace, seguire i principi di base, le procedure e i consigli dettagliati in Creazione, avvio e [gestione di un portale integro](https://go.microsoft.com/fwlink/?linkid=2105838) 

L'approccio alla distribuzione è evidenziato di seguito.

## <a name="overview-of-capacity-planning-in-sharepoint-online"></a>Panoramica della pianificazione della capacità in SharePoint Online
Per utilizzare in modo efficiente la capacità e gestire una crescita imprevista, in qualsiasi farm è disponibile un'automazione che tiene traccia di determinati scenari di utilizzo. Anche se la crescita esatta è imprevedibile per qualsiasi tenant in una farm, la somma aggregata delle richieste è prevedibile nel tempo. Identificando le tendenze di crescita in SharePoint Online, è possibile pianificare un'espansione futura. Per ulteriori informazioni sulla [pianificazione della capacità e sui test di carico di SharePoint Online.](capacity-planning-and-load-testing-sharepoint-online.md)

Una parte fondamentale di un avvio riuscito è l'approccio "wave" o "phased roll-out" descritto di seguito. 

## <a name="can-i-load-test-sharepoint-online"></a>È possibile eseguire il test di carico di SharePoint Online?
SharePoint Online è un ambiente multi-tenant condiviso bilanciato tra farm e la scalabilità viene adattata in modo continuativo. Il test di carico di un ambiente, come SharePoint Online, la cui scalabilità cambia continuamente non solo darà risultati imprevisti, ma non è consentito. 

Ulteriori informazioni:  [Pianificazione della capacità e test di carico di SharePoint Online](capacity-planning-and-load-testing-sharepoint-online.md)

## <a name="optimize-pages-by-following-recommended-guidelines"></a>Ottimizzare le pagine seguendo le linee guida consigliate
Le pagine di una distribuzione locale non devono semplicemente essere spostate in SharePoint Online senza esaminarle in base alle linee guida consigliate per SharePoint Online. L'approccio migliore consiste nell'ottimizzare sempre qualsiasi home page per qualsiasi sito o portale in SharePoint, in quanto la maggior parte degli utenti dell'organizzazione accederà come punto di partenza per i siti.

È necessario considerare alcuni fattori di base:
- Le distribuzioni locali possono sfruttare le cache lato server tradizionali come la cache oggetti, la cache di output e la cache BLOB. Con le differenze di topologia nel cloud, queste opzioni non sono necessariamente disponibili perché le differenze di scalabilità rendono gli approcci meno praticabili.
- Tutte le pagine/funzionalità/personalizzazioni usate per l'uso del cloud devono essere ottimizzate per una latenza maggiore e per le posizioni distribuite degli utenti, in modo che gli utenti in aree o aree geografiche diverse hanno un'esperienza più coerente. Cloud offre ottimizzazioni come reti per la distribuzione di contenuti (CDN) per ottimizzare una base di utenti distribuita e per SharePoint moderno, l'ultima buona nota (LKG) viene utilizzata dalle web part out-of-the-box (OOTB).

### <a name="what-to-do"></a>cosa fare:
 - Per tutte le pagine del sito in SharePoint Online utilizzare lo strumento [Diagnostica](https://aka.ms/perftool)pagine, che è un'estensione Chromium che assisterà nell'analisi e nella fornitura di indicazioni. Può essere usato da proprietari di siti, editor, amministratori e sviluppatori perché è progettato per essere un punto di partenza per l'analisi e l'ottimizzazione.
 - Gli sviluppatori devono anche usare strumenti di sviluppo come lo strumento di sviluppo di browser F12 e CTRL+F12 nel browser nelle pagine moderne. [Fiddler](https://www.telerik.com/download/fiddler) può essere usato anche per esaminare il peso delle dimensioni (la dimensione della pagina in megabyte) della pagina e il numero di chiamate ed elementi che influiscono sul carico complessivo della pagina. 

Questa sezione è stata un breve riepilogo per l'ottimizzazione delle pagine.  Per altre informazioni, vedi: [Creazione, avvio e gestione di un portale integro.](https://go.microsoft.com/fwlink/?linkid=2105838)

## <a name="follow-a-wave--phased-roll-out-approach"></a>Seguire un approccio di implementazione wave/in fasi
Il tradizionale approccio big bang per gli avvii dei siti non consentirà di verificare che personalizzazioni, origini esterne, servizi o processi siano stati testati sulla scala giusta. Questo non significa che l'avvio richiederà mesi, ma è consigliabile per almeno diversi giorni a seconda delle dimensioni dell'organizzazione. L'esecuzione di un piano di implementazione delle onde offre pertanto la possibilità di sospendere e risolvere i problemi prima di procedere con la fase successiva e quindi di ridurre il numero potenziale di utenti influenzati da eventuali problemi. SharePoint as a Service ridimensiona la capacità in base all'utilizzo e all'utilizzo previsto e, sebbene non sia necessario informare Microsoft dell'avvio, è consigliabile attenersi alle linee guida per garantire il successo.
  
Come illustrato nell'immagine seguente, spesso il numero di utenti invitati è significativamente superiore a quello degli utenti che utilizzano effettivamente il sito. Questa immagine mostra una strategia su come implementare una versione. Questo metodo consente di identificare i modi per migliorare il sito di SharePoint prima che venga visualizzato dalla maggior parte degli utenti.
  
![Grafico degli utenti invitati e attivi](../media/0bc14a20-9420-4986-b9b9-fbcd2c6e0fb9.png)
  
Nella fase pilota, è bene ricevere feedback dagli utenti che l'organizzazione considera attendibili e sa che verranno coinvolti. In questo modo è possibile valutare le modalità di utilizzo del sistema e le prestazioni.
  
Durante ognuna delle ondate, raccogliere il feedback degli utenti sulle funzionalità e sulle prestazioni durante ogni ondata di distribuzione. Ciò ha il vantaggio di introdurre lentamente il sistema e di apportare miglioramenti man quando il sistema diventa più utilizzato. In questo modo, inoltre, microsoft può rispondere all'aumento del carico man quando il sito viene eseguito a un numero sempre maggiore di utenti e, in combinazione con le linee guida per l'ottimizzazione delle pagine, garantisce un'esperienza positiva per gli utenti.

### <a name="what-to-do"></a>cosa fare:
- Decidere la tempistica di ogni fase e assicurarsi di avere un'opportunità di emergenza/pausa, se è necessario apportare modifiche prima di continuare
- Pianificare il primo gruppo di utenti che si desidera abilitare, per assicurarsi di ricevere il feedback necessario per procedere. Ciò significa che, se possibile, selezionare un gruppo attivo di utenti che fornirà commenti e suggerimenti in modo immediato
- Durante la pianificazione di ogni ondata, provare a iniziare con una piccola base di utenti (meno di 5.000 utenti) e quindi aumentare le dimensioni del gruppo man mano che si procede con ogni ondata. Ciò consente di creare un approccio scaglionare e di semplificare le opportunità di pausa che potrebbero essere necessarie.
