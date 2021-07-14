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
description: In questo articolo viene descritto come pianificare l'avvio del portale in SharePoint Online e quali operazioni eseguire per un avvio corretto
ms.openlocfilehash: 280aa76c41e7ef72d23b22877482a92d981fe29d
ms.sourcegitcommit: 69d28334e01ec757c794cf3f8b8c0d85713f975e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2021
ms.locfileid: "53424023"
---
# <a name="planning-your-portal-launch-roll-out-plan-in-sharepoint-online"></a>Pianificazione del piano di implementazione dell'avvio del portale in SharePoint Online

Un portale è un SharePoint sulla rete Intranet con molti visualizzatori del sito che utilizzano il contenuto del sito. Le organizzazioni di grandi dimensioni potrebbero avere diversi portali. Ad esempio, un portale aziendale e un portale risorse umane. In genere i portali hanno relativamente poche persone che creano il sito e il contenuto. La maggior parte dei visitatori del portale si limita a leggere e usare il contenuto.

In questo articolo viene descritto come pianificare il piano di distribuzione e implementazione per SharePoint Online. Fornisce inoltre approcci da seguire poiché i test di carico tradizionali non sono consentiti SharePoint Online. SharePoint Online è un servizio cloud e le funzionalità di carico, l'integrità e il bilanciamento generale del carico nel servizio sono gestiti da Microsoft.

Per facilitare la creazione di un portale corretto, seguire i principi, le procedure e i suggerimenti di base riportati in Creazione, avvio e gestione di [un portale integro](/sharepoint/portal-health) 

L'approccio alla distribuzione è evidenziato di seguito.

## <a name="portal-launch-scheduler"></a>Utilità di pianificazione avvio portale

Utilizzare l'utilità di pianificazione di avvio del portale per rilasciare il portale agli utenti dell'organizzazione in fasi pianificate. Ulteriori informazioni: 

![Icona Calendario](https://docs.microsoft.com/Office/media/icons/calendar.png "Utilità di pianificazione avvio portale")  [Utilità di pianificazione avvio portale](https://docs.microsoft.com/microsoft-365/enterprise/portallaunchscheduler)



## <a name="overview-of-capacity-planning-in-sharepoint-online"></a>Panoramica della pianificazione della capacità in SharePoint Online
Per utilizzare in modo efficiente la capacità e gestire una crescita imprevista, in qualsiasi farm è disponibile un'automazione che tiene traccia di determinati scenari di utilizzo. Anche se la crescita esatta è imprevedibile per qualsiasi tenant in una farm, la somma aggregata delle richieste è prevedibile nel tempo. Identificando le tendenze di crescita in SharePoint Online, possiamo pianificare l'espansione futura. Per ulteriori informazioni sulla [pianificazione della capacità e sui test di carico SharePoint Online.](capacity-planning-and-load-testing-sharepoint-online.md)

Una parte fondamentale di un avvio riuscito è l'approccio "ondata" o "implementazione graduale" descritto di seguito. 

## <a name="can-i-load-test-sharepoint-online"></a>È possibile caricare test di SharePoint Online?
SharePoint Online è un ambiente multi-tenant condiviso bilanciato tra farm e la scalabilità viene modificata in modo continuativo. Test di carico di un ambiente, come SharePoint Online, le cui modifiche di scala continuamente non solo offrono risultati imprevisti, ma non sono consentiti. 

Ulteriori informazioni: [Pianificazione della capacità e test di carico SharePoint Online](capacity-planning-and-load-testing-sharepoint-online.md)

## <a name="optimize-pages-by-following-recommended-guidelines"></a>Ottimizzare le pagine seguendo le linee guida consigliate
Le pagine di una distribuzione locale non devono semplicemente essere spostate in SharePoint Online senza esaminarle in base alle linee guida consigliate per SharePoint Online. L'approccio migliore consiste nell'ottimizzare sempre qualsiasi home page per qualsiasi sito o portale in SharePoint, poiché la maggior parte degli utenti dell'organizzazione accederà come punto di partenza per i siti.

È necessario considerare alcuni fattori di base:
- Le distribuzioni locali possono usare cache lato server tradizionali come la cache degli oggetti, la cache di output e la cache BLOB. Con le differenze di topologia nel cloud, queste opzioni non sono necessariamente disponibili perché le differenze di scalabilità rendono gli approcci meno praticabili.
- Tutte le pagine/funzionalità/personalizzazioni utilizzate per l'utilizzo del cloud devono essere ottimizzate per una latenza maggiore e le posizioni distribuite degli utenti, in modo che gli utenti in aree o aree geografiche diverse hanno un'esperienza più coerente. Cloud offre ottimizzazioni come le reti per la distribuzione di contenuti (rete CDN) per ottimizzare una base di utenti distribuita e per la SharePoint moderna, l'ultima buona nota (LKG) viene utilizzata dalle web part out-of-the-box (OOTB).

### <a name="what-to-do"></a>cosa fare:
 - Per tutte le pagine del sito in SharePoint Online usa lo strumento [Diagnostica pagine,](./page-diagnostics-for-spo.md)che è un'estensione Chromium che consente di analizzare e fornire indicazioni. Può essere utilizzato dai proprietari, dagli editori, dagli amministratori e dagli sviluppatori del sito perché è progettato per essere un punto di partenza per l'analisi e l'ottimizzazione.
 - Gli sviluppatori devono inoltre usare strumenti di sviluppo come lo strumento di sviluppo di browser F12 e CTRL-F12 nel browser nelle pagine moderne. [Fiddler](https://www.telerik.com/download/fiddler) può essere usato anche per esaminare il peso delle dimensioni (la dimensione della pagina in megabyte) della pagina e il numero di chiamate ed elementi che influiscono sul carico complessivo della pagina. 

Questa sezione è un breve riepilogo per l'ottimizzazione delle pagine.  Per ulteriori informazioni, vedere: [Creazione, avvio e gestione di un portale integro.](/sharepoint/portal-health)

## <a name="follow-a-wave--phased-roll-out-approach"></a>Seguire un approccio di implementazione wave/phased
L'approccio tradizionale del big bang per gli avvii di siti non consente di verificare che personalizzazioni, origini esterne, servizi o processi siano stati testati sulla scala giusta. Questo approccio non significa che l'avvio richiederà mesi, ma è consigliabile per almeno diversi giorni a seconda delle dimensioni dell'organizzazione. In seguito a un piano di implementazione ondata, è quindi possibile sospendere e risolvere i problemi prima di procedere con la fase successiva e quindi ridurre il numero potenziale di utenti a cui sono stati associati problemi. SharePoint servizio ridimensiona la capacità in base all'utilizzo e all'utilizzo previsto e, anche se non è necessario che ci informi dell'avvio, è consigliabile seguire le linee guida per garantire il successo.
  
Come illustrato nell'immagine seguente, spesso il numero di utenti invitati è notevolmente superiore a quelli che utilizzano effettivamente il sito. Questa immagine mostra una strategia su come implementare una versione. Questo metodo consente di identificare i modi per migliorare SharePoint sito prima che la maggior parte degli utenti lo veda.
  
![Grafico degli utenti invitati e attivi](../media/0bc14a20-9420-4986-b9b9-fbcd2c6e0fb9.png)
  
Nella fase pilota, è bene ricevere feedback dagli utenti che l'organizzazione considera attendibili e sa che verranno coinvolti. In questo modo è possibile valutare il modo in cui viene utilizzato il sistema e le prestazioni.
  
Durante ognuna delle ondate, raccogliere il feedback degli utenti sulle funzionalità e sulle prestazioni durante ogni ondata di distribuzione. La raccolta di feedback ha il vantaggio di introdurre lentamente il sistema e di apportare miglioramenti man appena il sistema diventa più utilizzato. Ciò ci consente anche di reagire all'aumento del carico quando il sito viene steso a un numero maggiore di utenti e, in combinazione con le linee guida per l'ottimizzazione delle pagine, garantisce un'esperienza positiva per gli utenti.

### <a name="what-to-do"></a>cosa fare:
- Decidere i tempi di ogni fase e assicurarsi di avere un'opportunità di emergenza/pausa, se è necessario apportare modifiche prima di continuare
- Pianificare il primo gruppo di utenti che si desidera abilitare, per assicurarsi di ricevere il feedback necessario per andare avanti.  Se possibile, selezionare un gruppo attivo di utenti che forniranno commenti e suggerimenti in modo immediato
- Durante la pianificazione di ogni ondata, provare a iniziare con una piccola base di utenti (meno di 5000 utenti). Aumenta le dimensioni del gruppo man mano che procedi con ogni onda. Creando un approccio sfalsato, consente di mettere in pausa più facilmente le opportunità in base alle esigenze.