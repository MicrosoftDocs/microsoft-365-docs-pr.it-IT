---
title: eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: 143b3ab8-8cb0-4036-a5fc-6536d837bfce
description: Microsoft 365 offre diversi strumenti di eDiscovery che è possibile usare per cercare e contenere i contenuti trovati in diverse posizioni, ad esempio cassette postali di Exchange, siti di SharePoint e OneDrive for Business, gruppi di Microsoft 365, Microsoft Teams e conversazioni skype for Business.
ms.openlocfilehash: 633679c32b12b0ce6f00ec20723360d911decbb4
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841107"
---
# <a name="ediscovery-solutions-in-microsoft-365"></a>Soluzioni eDiscovery in Microsoft 365

Il rilevamento elettronico o eDiscovery, è il processo di identificazione e consegna di dati elettronici che possono essere utilizzati come prove in casi legali. È possibile utilizzare gli strumenti di eDiscovery in Microsoft 365 per cercare contenuti nelle cassette postali di Exchange Online, nei gruppi di Microsoft 365, nei siti di Microsoft Teams, SharePoint Online e OneDrive for Business, nelle conversazioni di Skype for Business e nei team di Yammer. È possibile eseguire ricerche nelle cassette postali e nei siti nella stessa ricerca eDiscovery utilizzando lo strumento Ricerca contenuto. È inoltre possibile utilizzare i casi di eDiscovery di base per identificare, contenere ed esportare il contenuto presente nelle cassette postali e nei siti. Se l'organizzazione ha un abbonamento a Office 365 E5 o Microsoft 365 E5 (o ad abbonamenti a componenti aggiuntivi E5 correlati), è possibile gestire ulteriormente i responsabile e analizzare il contenuto utilizzando la soluzione Advanced eDiscovery in Microsoft 365.
  
Microsoft 365 offre i seguenti strumenti di eDiscovery:
  
- [Ricerca contenuto](#content-search)

- [Core eDiscovery](#core-ediscovery)

- [Advanced eDiscovery](#advanced-ediscovery)

## <a name="content-search"></a>Ricerca contenuto

Nella tabella seguente sono contenuti collegamenti ad articoli che consentono di utilizzare lo strumento ricerca contenuto.
  
|**Articolo**|**Descrizione**|
|:-----|:-----|
|[Eseguire una ricerca](content-search.md) <br/> |Informazioni su come usare lo strumento Ricerca contenuto per cercare cassette postali, cartelle pubbliche, gruppi di Microsoft 365, Microsoft Teams, siti di SharePoint Online, posizioni di One Drive for Business e conversazioni Skype for Business nell'organizzazione in un'unica ricerca.  <br/> |
|[Query con parole chiave e condizioni di ricerca](keyword-queries-and-search-conditions.md) <br/> |Informazioni sulle proprietà di posta elettronica e file e sulle condizioni di ricerca che è possibile utilizzare per cercare contenuto nelle cassette postali e nei siti dell'organizzazione.  <br/> |
|[Visualizzare le statistiche delle parole chiave per i risultati della ricerca](view-keyword-statistics-for-content-search.md) <br/> |Informazioni su come utilizzare le statistiche di ricerca per visualizzare e confrontare le statistiche per una o più ricerche di contenuto e su come configurare ricerche nuove ed esistenti per restituire statistiche per ogni parola chiave nella query di ricerca.  <br/> |
|[Esportare i risultati della ricerca](export-search-results.md) <br/> |Informazioni su come esportare i risultati di una ricerca di contenuto.  <br/> |
|[Configurare il filtro delle autorizzazioni per Ricerca contenuto](permissions-filtering-for-content-search.md) <br/> |Informazioni su come utilizzare il filtro delle autorizzazioni per consentire a un responsabile di eDiscovery di cercare solo un sottoinsieme di cassette postali e siti nell'organizzazione.  <br/> |
|[Esportare un report sulle ricerche](export-a-content-search-report.md) <br/> |Informazioni su come scaricare il report di esportazione senza dover esportare i risultati della ricerca effettivi.  <br/> |
|[Limiti di Ricerca contenuto](limits-for-content-search.md) <br/> |Informazioni sui limiti dello strumento Ricerca contenuto, ad esempio il numero massimo di ricerche che è possibile eseguire contemporaneamente.  <br/> |
|[Elementi non indicizzati in Ricerca contenuto](partially-indexed-items-in-content-search.md) <br/> |Informazioni sugli elementi non indicizzati in Exchange e SharePoint che è possibile includere nelle statistiche dei risultati di ricerca stimati quando si esegue una ricerca. È inoltre possibile includere elementi non indicizzati quando si esportano i risultati della ricerca.  <br/> |
|[Cercare ed eliminare i messaggi di posta elettronica](search-for-and-delete-messages-in-your-organization.md) <br/> |Informazioni su come utilizzare Ricerca contenuto per cercare ed eliminare un messaggio di posta elettronica da  *tutte le cassette*  postali dell'organizzazione. In questo modo è possibile individuare e rimuovere messaggi di posta elettronica potenzialmente dannosi o ad alto rischio.  <br/> |
|[Cercare un elenco di utenti nella cassetta postale e nell'account di OneDrive](search-the-mailbox-and-onedrive-for-business-for-a-list-of-users.md) <br/> |Informazioni su come utilizzare uno script per cercare un gruppo di utenti nella cassetta postale e nel sito di One Drive for Business. Vedere Creare un elenco di tutti i percorsi di [OneDrive](https://docs.microsoft.com/onedrive/list-onedrive-urls) per istruzioni su come generare rapidamente un elenco di indirizzi di posta elettronica che è possibile usare per i percorsi di contenuto di origine quando si creano ed eseguono ricerche di contenuto.  <br/> |
|[Usare Ricerca contenuto per le raccolte di destinazione](use-content-search-for-targeted-collections.md) <br/> |Informazioni su come usare lo script Windows PowerShell contenuto in questo articolo per eseguire raccolte mirate tramite Ricerca contenuto. Una raccolta di destinazione significa che vuoi eseguire una ricerca in una cartella specifica perché sei certo che gli elementi che responsino a un caso (o elementi con privilegi) si trovino in tale cartella. Utilizzare lo script riportato in questo articolo per ottenere l'ID o il percorso della cartella specifica della cassetta postale o delle cartelle del sito in cui si desidera eseguire la ricerca.  <br/> |
|||
  
## <a name="core-ediscovery"></a>Core eDiscovery

Nella tabella seguente sono riportati i collegamenti agli argomenti che consentono di utilizzare i casi di eDiscovery di base. È possibile utilizzare i casi di eDiscovery di base per aggiungere responsabili di eDiscovery che possono accedere al caso, inserire un blocco eDiscovery sui percorsi dei contenuti rilevanti per il caso, cercare contenuto ed esportare i risultati della ricerca dal caso.
  
|**Articolo**|**Descrizione**|
|:-----|:-----|
|[Introduzione a Core eDiscovery](get-started-core-ediscovery.md) |Informazioni su come assegnare le autorizzazioni di eDiscovery e creare casi di eDiscovery di base. In questo argomento viene inoltre fornita una panoramica del flusso di lavoro core eDiscovery.<br/> |
|[Assegnare le autorizzazioni di eDiscovery](assign-ediscovery-permissions.md)|Informazioni su come assegnare autorizzazioni agli utenti in modo che possano cercare contenuto, mettere in attesa i percorsi dei contenuti ed eseguire altre attività correlate a eDiscovery in un caso di eDiscovery di base.|
|[Configurare i limiti di conformità per Core eDiscovery](set-up-compliance-boundaries.md)|Informazioni su come utilizzare i limiti di conformità per creare limiti logici all'interno di un'organizzazione che controllano i percorsi dei contenuti che un responsabile di eDiscovery può cercare.|
|[Creare un blocco di eDiscovery](create-ediscovery-holds.md)|Informazioni su come creare blocchi di eDiscovery associati a un caso di eDiscovery di base per conservare i contenuti rilevanti per il caso in cui si sta esaminando.|
|[Cercare il contenuto in un caso](search-for-content-in-core-ediscovery.md)|Informazioni su come cercare contenuti rilevanti per un caso. È possibile creare rapidamente ricerche per la ricerca nei percorsi di contenuto in attesa.|
|[Esportare il contenuto da un caso](export-content-in-core-ediscovery.md)|Informazioni su come esportare e scaricare contenuto da un caso di eDiscovery di base.|
|[Chiudere, riaprire ed eliminare un caso](close-reopen-delete-core-ediscovery-cases.md)|Informazioni su come gestire il ciclo di vita di un caso di eDiscovery di base.|
|||
  
## <a name="advanced-ediscovery"></a>Advanced eDiscovery

La soluzione Advanced eDiscovery in Microsoft 365 (denominata anche *Advanced eDiscovery v2.0)* si basa sulle funzionalità di eDiscovery e analisi esistenti in Microsoft 365. Questa soluzione eDiscovery offre un flusso di lavoro end-to-end per conservare, raccogliere, esaminare, analizzare ed esportare contenuti reattivi alle indagini interne ed esterne dell'organizzazione. Consente inoltre ai team legali di gestire i responsabile e l'intero flusso di lavoro di notifica della conservazione per comunicare con i responsabile coinvolti in un caso.

|**Articolo**|**Descrizione**|
|:-----|:-----|
|[Panoramica di Advanced eDiscovery](overview-ediscovery-20.md)|In questo articolo viene presentato Advanced eDiscovery, vengono descritte le motivazioni aziendali per l'utilizzo di questo strumento, viene presentata l'architettura di Advanced eDiscovery e viene fornita una panoramica generale del flusso di lavoro incorporato di Advanced eDiscovery.|
|[Configurare Advanced eDiscovery](get-started-with-advanced-ediscovery.md)|Informazioni su come iniziare a usare Advanced eDiscovery, incluse le licenze necessarie e le autorizzazioni di eDiscovery necessarie.|
|[Creare e gestire un caso](create-and-manage-advanced-ediscoveryv2-case.md)|In questo articolo viene illustrato come creare un caso di Advanced eDiscovery e viene fornita una procedura dettagliata per il flusso di lavoro advanced eDiscovery.|
|[Gestire i responsabili](managing-custodians.md)|Informazioni sull'utilizzo dei responsabile in advanced eDiscovery. Questo argomento contiene collegamenti a istruzioni dettagliate per aggiungere i responsabile a un caso, gestire i responsabile in un caso e visualizzare le attività dei responsabile in Microsoft 365 eseguendo una ricerca nel log di controllo.|
|[Gestire le comunicazioni con il responsabile](managing-custodian-communications.md)|Informazioni sulla gestione del processo di notifica di blocco legale in Advanced eDiscovery. Ciò include la creazione e l'automazione del flusso di lavoro delle notifiche e il modo in cui un utente ha riconosciuto una notifica di blocco.
|[Gestire errori di elaborazione](processing-data-for-case.md)|Informazioni sull'indicizzazione avanzata e su come correggere gli errori di indicizzazione nel contenuto da posizioni di contenuto di tipo responsabile e non, ad esempio cassette postali di Exchange, siti di SharePoint e account di OneDrive. È possibile correggere in blocco gli errori e quindi caricare i file corretti in un insieme da rivedere o correggere i singoli errori di elaborazione all'interno di un insieme da rivedere.|
|[Raccogliere i dati per un caso](collecting-data-for-ediscovery.md)|Informazioni sulla ricerca di contenuto nei percorsi dei contenuti dei depositario e sull'aggiunta di dati del caso pertinenti a un insieme da rivedere. Quando si copia il contenuto in un insieme da rivedere, i dati vengono copiati dai percorsi dei contenuti originali in un percorso di Archiviazione di Azure fornito da Microsoft. In questo modo viene fornito un set statico di documenti per il processo di revisione.|
|[Gestire gli insiemi da rivedere](managing-review-sets.md)|Informazioni sulla revisione dei dati del caso in un insieme da rivedere. Sono incluse la visualizzazione, l'esecuzione di query, l'applicazione di filtri e l'aggiunta di tag ai documenti in un insieme da rivedere.
|[Analizzare i dati in un insieme da rivedere](analyzing-data-in-review-set.md)|Informazioni sull'esecuzione dell'analisi sui documenti in un insieme da rivedere. I risultati dell'analisi in esecuzione includono il rilevamento quasi duplicato, il threading della posta elettronica e l'identificazione dei temi.|
|[Esportare i dati del caso](exporting-data-ediscover20.md)|Informazioni sull'esportazione di dati da un caso per la revisione esterna.|
|||

## <a name="ediscovery-roadmap"></a>Roadmap di eDiscovery

Per sapere quali funzionalità di eDiscovery sono state avviate, sono in fase di distribuzione o in fase di sviluppo, vedere la roadmap di [Microsoft 365.](https://aka.ms/eDiscoRoadMap)
