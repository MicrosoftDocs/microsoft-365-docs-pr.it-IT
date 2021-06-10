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
description: Microsoft 365 offre diversi strumenti di eDiscovery che è possibile utilizzare per cercare e contenere il contenuto presente in posizioni diverse, ad esempio cassette postali di Exchange, siti SharePoint e OneDrive for Business, gruppi di Microsoft 365, Microsoft Teams e conversazioni Skype for Business.
ms.openlocfilehash: a7f8a4a7de6c03d37ffa7ac1c66113da63a13775
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925582"
---
# <a name="ediscovery-solutions-in-microsoft-365"></a>Soluzioni eDiscovery in Microsoft 365

Il rilevamento elettronico o eDiscovery, è il processo di identificazione e consegna di dati elettronici che possono essere utilizzati come prove in casi legali. È possibile utilizzare gli strumenti di eDiscovery in Microsoft 365 per cercare contenuto nelle cassette postali di Exchange Online, nei gruppi di Microsoft 365, nei siti Microsoft Teams, SharePoint Online e OneDrive for Business, nelle conversazioni Skype for Business e nei team di Yammer. È possibile eseguire ricerche nelle cassette postali e nei siti nella stessa ricerca eDiscovery utilizzando lo strumento Ricerca contenuto. È inoltre possibile utilizzare i casi di eDiscovery di base per identificare, mantenere ed esportare il contenuto presente nelle cassette postali e nei siti. Se l'organizzazione dispone di una sottoscrizione Office 365 E5 o Microsoft 365 E5 (o sottoscrizioni di componenti aggiuntivi E5 correlate), è possibile gestire ulteriormente i depositario e analizzare il contenuto utilizzando la soluzione Advanced eDiscovery in Microsoft 365.
  
Microsoft 365 fornisce i seguenti strumenti di eDiscovery:
  
- [Ricerca contenuto](#content-search)

- [Core eDiscovery](#core-ediscovery)

- [Advanced eDiscovery](#advanced-ediscovery)

## <a name="content-search"></a>Ricerca contenuto

Nella tabella seguente sono contenuti collegamenti ad articoli che consentono di utilizzare lo strumento ricerca contenuto.
  
|**Articolo**|**Descrizione**|
|:-----|:-----|
|[Eseguire una ricerca](content-search.md) <br/> |Informazioni su come utilizzare lo strumento Ricerca contenuto per cercare cassette postali, cartelle pubbliche, gruppi di Microsoft 365, Microsoft Teams, siti di SharePoint Online, posizioni di One Drive for Business e conversazioni di Skype for Business nell'organizzazione in una singola ricerca.  <br/> |
|[Query con parole chiave e condizioni di ricerca](keyword-queries-and-search-conditions.md) <br/> |Informazioni sulle proprietà di posta elettronica e file e sulle condizioni di ricerca che è possibile utilizzare per cercare contenuto nelle cassette postali e nei siti dell'organizzazione.  <br/> |
|[Visualizzare le statistiche delle parole chiave per i risultati della ricerca](view-keyword-statistics-for-content-search.md) <br/> |Informazioni su come utilizzare le statistiche di ricerca per visualizzare e confrontare le statistiche per una o più ricerche di contenuto e per configurare ricerche nuove ed esistenti per restituire statistiche per ogni parola chiave nella query di ricerca.  <br/> |
|[Esportare i risultati della ricerca](export-search-results.md) <br/> |Informazioni su come esportare i risultati di una ricerca contenuto.  <br/> |
|[Configurare il filtro delle autorizzazioni per Ricerca contenuto](permissions-filtering-for-content-search.md) <br/> |Informazioni su come utilizzare il filtro delle autorizzazioni per consentire a un responsabile di eDiscovery di cercare solo un sottoinsieme di cassette postali e siti nell'organizzazione.  <br/> |
|[Esportare un report sulle ricerche](export-a-content-search-report.md) <br/> |Informazioni su come scaricare il report di esportazione senza dover esportare i risultati della ricerca effettivi.  <br/> |
|[Limiti di Ricerca contenuto](limits-for-content-search.md) <br/> |Informazioni sui limiti dello strumento ricerca contenuto, ad esempio il numero massimo di ricerche che è possibile eseguire contemporaneamente.  <br/> |
|[Elementi non indicizzati in Ricerca contenuto](partially-indexed-items-in-content-search.md) <br/> |Informazioni sugli elementi non indicizzati in Exchange e SharePoint che è possibile includere nelle statistiche dei risultati di ricerca stimate quando si esegue una ricerca. È inoltre possibile includere elementi non indicizzati quando si esportano i risultati della ricerca.  <br/> |
|[Cercare ed eliminare i messaggi di posta elettronica](search-for-and-delete-messages-in-your-organization.md) <br/> |Informazioni su come utilizzare Ricerca contenuto per cercare ed eliminare un messaggio di posta elettronica da  *tutte le*  cassette postali dell'organizzazione. In questo modo è possibile individuare e rimuovere messaggi di posta elettronica potenzialmente dannosi o ad alto rischio.  <br/> |
|[Cercare nella cassetta postale e OneDrive un elenco di utenti](search-the-mailbox-and-onedrive-for-business-for-a-list-of-users.md) <br/> |Informazioni su come utilizzare uno script per cercare un gruppo di utenti nella cassetta postale e nel sito One Drive for Business. Per informazioni su come generare rapidamente un elenco di indirizzi di posta elettronica che è possibile utilizzare per i percorsi di contenuto di origine durante la creazione e l'esecuzione di ricerche di contenuto, vedere Create [a list of all OneDrive locations.](/onedrive/list-onedrive-urls)  <br/> |
|[Usare Ricerca contenuto per raccolte di destinazione](use-content-search-for-targeted-collections.md) <br/> |Informazioni su come usare lo script di Windows PowerShell in questo articolo per eseguire raccolte mirate tramite Ricerca contenuto. Una raccolta di destinazione significa che si desidera eseguire una ricerca in una cartella specifica perché si è certi che gli elementi che responso a un caso (o elementi con privilegi) si trovino in tale cartella. Utilizzare lo script in questo articolo per ottenere l'ID cartella o il percorso per la cassetta postale o le cartelle del sito specifiche in cui si desidera eseguire la ricerca.  <br/> |
|||
  
## <a name="core-ediscovery"></a>Core eDiscovery

La tabella seguente contiene collegamenti ad argomenti utili per l'utilizzo dei casi di eDiscovery di base. È possibile utilizzare i casi di eDiscovery di base per aggiungere responsabili di eDiscovery che possono accedere al caso, inserire un blocco di eDiscovery sui percorsi di contenuto rilevanti per il caso, cercare contenuto ed esportare i risultati della ricerca dal caso.
  
|**Articolo**|**Descrizione**|
|:-----|:-----|
|[Introduzione a Core eDiscovery](get-started-core-ediscovery.md) |Informazioni su come assegnare autorizzazioni di eDiscovery e creare casi di eDiscovery di base. In questo argomento viene inoltre fornita una panoramica del flusso di lavoro di eDiscovery di base.<br/> |
|[Assegnare le autorizzazioni di eDiscovery](assign-ediscovery-permissions.md)|Informazioni su come assegnare autorizzazioni agli utenti in modo che possano cercare contenuto, mettere in attesa le posizioni del contenuto ed eseguire altre attività correlate a eDiscovery in un caso di eDiscovery di base.|
|[Configurare i limiti di conformità per Core eDiscovery](set-up-compliance-boundaries.md)|Informazioni su come utilizzare i limiti di conformità per creare limiti logici all'interno di un'organizzazione che controllano le posizioni di contenuto in cui un responsabile di eDiscovery può eseguire ricerche.|
|[Creare un blocco di eDiscovery](create-ediscovery-holds.md)|Informazioni su come creare blocchi di eDiscovery associati a un caso di eDiscovery di base per conservare il contenuto rilevante per il caso in cui si sta esaminando.|
|[Cercare il contenuto in un caso](search-for-content-in-core-ediscovery.md)|Informazioni su come cercare contenuto rilevante per un caso. È possibile creare rapidamente ricerche che esere in attesa nei percorsi di contenuto.|
|[Esportare il contenuto da un caso](export-content-in-core-ediscovery.md)|Informazioni su come esportare e scaricare contenuto da un caso di eDiscovery di base.|
|[Chiudere, riaprire ed eliminare un caso](close-reopen-delete-core-ediscovery-cases.md)|Informazioni su come gestire il ciclo di vita di un caso di eDiscovery di base.|
|||
  
## <a name="advanced-ediscovery"></a>Advanced eDiscovery

La soluzione Advanced eDiscovery in Microsoft 365 (denominata anche *Advanced eDiscovery v2.0)* si basa sulle funzionalità di eDiscovery e di analisi esistenti in Microsoft 365. Questa soluzione eDiscovery offre un flusso di lavoro end-to-end per conservare, raccogliere, esaminare, analizzare ed esportare contenuto reattivo alle indagini interne ed esterne dell'organizzazione. Consente inoltre ai team legali di gestire i custodi e l'intero flusso di lavoro di notifica del blocco legale per comunicare con i custodi coinvolti in un caso.

|**Articolo**|**Descrizione**|
|:-----|:-----|
|[Panoramica di Advanced eDiscovery](overview-ediscovery-20.md)|In questo articolo viene Advanced eDiscovery, vengono illustrate le motivazioni aziendali per l'utilizzo di questo strumento, viene presentata l'architettura Advanced eDiscovery e viene fornita una panoramica generale del flusso di lavoro predefinito di Advanced eDiscovery.|
|[Configurare Advanced eDiscovery](get-started-with-advanced-ediscovery.md)|Informazioni su come iniziare a usare Advanced eDiscovery, incluse le licenze necessarie e le autorizzazioni necessarie per eDiscovery.|
|[Creazione e gestione di un caso](create-and-manage-advanced-ediscoveryv2-case.md)|In questo articolo viene illustrato come creare un caso Advanced eDiscovery e viene fornita una procedura dettagliata del flusso Advanced eDiscovery flusso di lavoro.|
|[Gestire i responsabili](managing-custodians.md)|Informazioni sull'utilizzo dei custodi in un Advanced eDiscovery. In questo argomento vengono fornite istruzioni dettagliate per aggiungere i custodi a un caso, gestire i custodi in un caso e visualizzare l'attività dei custodi in Microsoft 365 eseguendo una ricerca nel log di controllo.|
|[Gestire le comunicazioni con il responsabile](managing-custodian-communications.md)|Informazioni sulla gestione del processo di notifica di blocco legale in Advanced eDiscovery. Ciò include la creazione e l'automazione del flusso di lavoro delle notifiche e il modo in cui un utente ha riconosciuto una notifica di blocco.
|[Gestire errori di elaborazione](processing-data-for-case.md)|Informazioni sull'indicizzazione avanzata e su come correggere gli errori di indicizzazione nel contenuto da posizioni di contenuto di tipo depositario e non, ad esempio cassette postali di Exchange, siti di SharePoint e account OneDrive. È possibile correggere in blocco gli errori e quindi caricare i file corretti in un set di revisione o correggere i singoli errori di elaborazione all'interno di un set di revisione.|
|[Raccogliere i dati per un caso](collecting-data-for-ediscovery.md)|Informazioni sulla ricerca di contenuto in posizioni di contenuto di custodia e quindi sull'aggiunta di dati relativi ai casi pertinenti a un set di recensioni. Quando si copia il contenuto in un set di revisioni, i dati vengono copiati dai percorsi del contenuto originale in un percorso Archiviazione di Azure fornito da Microsoft. In questo modo viene fornito un set statico di documenti per il processo di revisione.|
|[Gestire gli insiemi da rivedere](managing-review-sets.md)|Informazioni sulla revisione dei dati dei casi in un set di recensioni. Ciò include la visualizzazione, l'esecuzione di query, il filtro e l'applicazione di tag ai documenti in un set di revisioni.
|[Analizzare i dati in un set di recensioni](analyzing-data-in-review-set.md)|Informazioni sull'esecuzione dell'analisi dei documenti in un set di revisioni. I risultati dell'analisi in esecuzione includono rilevamento quasi duplicato, threading della posta elettronica e identificazione dei temi.|
|[Esportare i dati del caso](exporting-data-ediscover20.md)|Informazioni sull'esportazione di dati da un caso per la revisione esterna.|
|||

## <a name="ediscovery-roadmap"></a>Roadmap di eDiscovery

Per sapere quali funzionalità di eDiscovery sono state avviate, in fase di implementazione o in fase di sviluppo, vedere Microsoft 365 [Roadmap](https://aka.ms/eDiscoRoadMap).