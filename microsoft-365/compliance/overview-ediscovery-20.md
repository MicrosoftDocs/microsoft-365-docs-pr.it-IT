---
title: Panoramica della soluzione Advanced eDiscovery in Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-aed
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Informazioni sulla soluzione Advanced eDiscovery in Microsoft 365. In questo articolo viene fornita una panoramica di Advanced eDiscovery in Microsoft 365, uno strumento che consente di gestire le indagini interne ed esterne. Vengono inoltre incorniciati i motivi aziendali per l'utilizzo di Advanced eDiscovery per gestire le indagini legali.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1b2fa0b42a7f439aa65ae53e76e377ded92f97b7
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840879"
---
# <a name="overview-of-microsoft-365-advanced-ediscovery"></a>Panoramica di Microsoft 365 Advanced eDiscovery

La soluzione Advanced eDiscovery in Microsoft 365 si basa sulle funzionalità di analisi e eDiscovery di Microsoft esistenti. Advanced eDiscovery fornisce un flusso di lavoro end-to-end per conservare, raccogliere, analizzare, esaminare, analizzare ed esportare contenuti reattivi alle indagini interne ed esterne dell'organizzazione. Consente inoltre ai team legali di gestire l'intero flusso di lavoro di notifica della conservazione per comunicare con i responsabile coinvolti in un caso.

Advanced eDiscovery consente all'organizzazione di rispondere a questioni legali o indagini interne individuando i dati in cui si trova. È possibile gestire senza problemi i flussi di lavoro di eDiscovery identificando le persone di interesse e le relative origini dati, applicare facilmente i blocchi per conservare i dati e quindi gestire il processo di comunicazione della conservazione a livello legale. Raccogliendo i dati dall'origine, è possibile eseguire ricerche nella piattaforma Microsoft 365 in tempo reale per trovare rapidamente le informazioni necessarie. Le funzionalità di apprendimento automatico intelligenti, come l'indicizzazione approfondita, il threading della posta elettronica e il rilevamento quasi duplicato, consentono inoltre di ridurre grandi volumi di dati a un set di dati pertinente.

Nelle sezioni seguenti viene descritto in che modo queste funzionalità di Advanced eDiscovery possono aiutare l'organizzazione.

## <a name="discover-and-collect-data-in-place"></a>Individuare e raccogliere dati sul posto

Tradizionalmente, le organizzazioni che si basano su più soluzioni eDiscovery di terze parti richiedono di copiare grandi volumi di dati da Microsoft 365 per elaborare e dover ospitare dati duplicati. Questa necessità aumenta il tempo necessario per trovare i dati rilevanti e il rischio, i costi e la complessità della gestione di più soluzioni.

Advanced eDiscovery in Microsoft 365 consente di individuare i dati all'origine e di rimanere all'interno del limite di sicurezza e conformità di Microsoft 365.  Raccogliendo i dati sul posto dal sistema reale, Advanced eDiscovery riduce l'attrito di tornare all'origine e riduce il lavoro non necessario di dover trovare contenuto mancante, che spesso si verifica quando l'inserimento nel journal è in ritardo nelle soluzioni eDiscovery tradizionali.

Le funzionalità di ricerca e raccolta native per i dati in Teams, Yammer, SharePoint Online, OneDrive for Business ed Exchange Online migliorano ulteriormente l'individuazione dei dati. Ad esempio, Advanced eDiscovery:

- Ricostruisce le conversazioni di Teams (anziché restituire singoli messaggi dalle conversazioni).

- Raccoglie i contenuti basati sul cloud condivisi con gli utenti tramite collegamenti o allegati moderni nei messaggi di posta elettronica e nelle chat di Teams.

- Ha un supporto incorporato per centinaia di tipi di file non Microsoft 365.

- Raccoglie dati da origini di terze parti (ad esempio Bloomberg, Facebook, Slack e Riunioni zoom) importati e archiviati in Microsoft 365 dai connettori [dati.](archiving-third-party-data.md)

## <a name="manage-ediscovery-workflow-in-one-platform"></a>Gestire il flusso di lavoro di eDiscovery in un'unica piattaforma

Advanced eDiscovery consente di ridurre il numero di soluzioni eDiscovery su cui è necessario fare affidamento. Offre un flusso di lavoro end-to-end semplificato, che si verifica all'interno di Microsoft 365. Advanced eDiscovery consente di ridurre l'attrito di identificare e raccogliere potenziali origini di informazioni rilevanti mappando automaticamente origini dati univoche e condivise alla persona di interesse (nota come *responsabile)* e fornendo report e analisi su dati potenzialmente rilevanti prima di raccoglierla per l'analisi e la revisione.

Inoltre, le API di Microsoft Graph consentono di automatizzare il flusso di lavoro di eDiscovery ed estendere Advanced eDiscovery per soluzioni personalizzate.

## <a name="cull-data-intelligently"></a>Cul i dati in modo intelligente

Le funzionalità di apprendimento automatico intelligenti in Advanced eDiscovery consentono di ridurre la quantità di dati da esaminare. Queste funzionalità intelligenti consentono di ridurre e cullare grandi volumi di dati in un set pertinente. Ad esempio, una query di insieme da rivedere incorporata consente di filtrare solo il contenuto univoco identificando i duplicati vicini. Questa funzionalità può ridurre notevolmente la quantità di dati da esaminare.

Ulteriori funzionalità di apprendimento automatico possono perfezionare e identificare ulteriormente i dati rilevanti utilizzando smart tag e strumenti di revisione assistiti dalla tecnologia, come i moduli di rilevanza.

## <a name="advanced-ediscovery-architecture"></a>Architettura avanzata di eDiscovery

Ecco un diagramma dell'architettura di Advanced eDiscovery che mostra il flusso di lavoro end-to-end in un ambiente geografico singolo e in un ambiente multi-geografico e il flusso di dati end-to-end allineato al modello EDRM [(Electronic Discovery Reference Model).](advanced-ediscovery-edrm.md)

[![Poster modello: Architettura avanzata di eDiscovery in Microsoft 365](../media/solutions-architecture-center/ediscovery-poster-thumb.png)](../media/solutions-architecture-center/m365-advanced-ediscovery-architecture.png)

[Visualizzazione come immagine](../media/solutions-architecture-center/m365-advanced-ediscovery-architecture.png)

[Scarica come file PDF](https://download.microsoft.com/download/d/1/c/d1ce536d-9bcf-4d31-b75b-fcf0dc560665/m365-advanced-ediscovery-architecture.pdf)

[Download come file di Visio](https://download.microsoft.com/download/d/1/c/d1ce536d-9bcf-4d31-b75b-fcf0dc560665/m365-advanced-ediscovery-architecture.vsdx)

Per ulteriori informazioni sul flusso di lavoro end-to-end in Advanced eDiscovery, vedere questo [video di Microsoft Mechanics.](https://go.microsoft.com/fwlink/?linkid=2066133)

## <a name="advanced-ediscovery-workflow"></a>Flusso di lavoro advanced eDiscovery

Le sezioni seguenti descrivono ogni passaggio del flusso di lavoro incorporato nello strumento Advanced eDiscovery nel Centro conformità Microsoft 365. Lo screenshot seguente mostra la **scheda Panoramica** di un caso denominato *2020.11.03 - Contoso v. Fabrikam.*

![Schede nel flusso di lavoro advanced eDiscovery predefinito](../media/AeD-Case-Screenshot1.png)

Per informazioni più dettagliate, vedere [Gestire il flusso di lavoro advanced eDiscovery.](create-and-manage-advanced-ediscoveryv2-case.md#manage-the-workflow)

### <a name="managing-custodians-and-non-custodial-data-sources"></a>Gestione dei responsabile e delle origini dati non dei depositario

Usare la **scheda** Origini dati per aggiungere e gestire le persone identificate come persone di interesse nel caso e altre origini dati che potrebbero non essere associate a un responsabile. Quando si aggiungono responsabile o origini dati non di tipo responsabile, è possibile eseguire rapidamente azioni come l'applicazione di un blocco legale alle origini dati dei depositario e non, la comunicazione con i responsabile e la ricerca di origini dati di tipo responsabile e non responsabile per raccogliere contenuti rilevanti per il caso. Con l'avanzamento del caso, è facile aggiungere nuovi responsabile o origini di data non-custodial o rilasciarle dal caso. Per ulteriori informazioni, vedere [Collaborare con i responsabile.](managing-custodians.md)

### <a name="managing-legal-hold-notifications"></a>Gestione delle notifiche di blocco legale

Utilizzare la **scheda** Comunicazioni per gestire il processo di comunicazione con i responsabile del caso. Un avviso di blocco legale indica ai depositnti di conservare qualsiasi contenuto pertinente al caso. I team legali devono essere in grado di tenere traccia degli avvisi ricevuti, letti e riconosciuti dai responsabile. Il flusso di lavoro delle comunicazioni in Advanced eDiscovery consente di creare e inviare notifiche iniziali, promemoria, notifiche di rilascio e escalation se i responsabile non riconoscono una notifica di blocco. Per ulteriori informazioni, vedere [Utilizzare le comunicazioni.](managing-custodian-communications.md)

### <a name="managing-content-preservation"></a>Gestione dell'archiviazione del contenuto

Quando si aggiunge un responsabile a un caso, è possibile inserire un blocco sui dati del responsabile. Usare la **scheda Esenzione** per gestire il blocco creato quando si aggiungono i responsabile e per gestire altre conservazioni legali associate al caso; Ad esempio, è possibile identificare e impostare un blocco per le origini dati non di tipo depositario. È inoltre possibile modificare qualsiasi blocco nel caso e renderlo un blocco basato su query per mantenere solo il contenuto che corrisponde alla query. Ad esempio, è possibile aggiungere un intervallo di date all'esenzione in modo che solo il contenuto creato entro un intervallo di date specifico sia conservato. È anche possibile ottenere statistiche sul contenuto in attesa, rimuovere il blocco dopo che non è più rilevante per il caso o eliminarlo. Per ulteriori informazioni, vedere [Gestire i blocchi.](managing-holds.md)

### <a name="indexing-custodian-data"></a>Indicizzazione dei dati dei depositario

Quando si aggiungono un responsabile e le origini dati del responsabile corrispondenti a un caso, qualsiasi elemento parzialmente indicizzato da un'origine dati responsabile viene reindicizzato da un processo denominato *Indicizzazione avanzata.* In questo modo il contenuto dei depositario, ad esempio immagini, tipi di file non supportati e altri contenuti potenzialmente non indicizzati, può essere completamente ricercabile quando si eseguono ricerche per raccogliere dati per il caso. Utilizzare la **scheda Elaborazione** per monitorare lo stato dell'indicizzazione avanzata e correggere gli errori di elaborazione utilizzando un processo denominato correzione *degli errori.* Per ulteriori informazioni, vedere [Correggere gli errori di elaborazione.](processing-data-for-case.md)

### <a name="collecting-case-data"></a>Raccolta dei dati del caso

Utilizzare la **scheda Ricerche** per creare ricerche per cercare il contenuto pertinente al caso nelle origini dati del responsabile sul posto e non. È possibile creare ed eseguire ricerche basate su query (utilizzando parole chiave e condizioni) per identificare un insieme di messaggi di posta elettronica e documenti rilevanti per il caso e che si desidera esaminare e analizzare ulteriormente nei passaggi successivi del flusso di lavoro di eDiscovery. È possibile creare una o più ricerche associate al caso. È inoltre possibile utilizzare lo strumento di ricerca per visualizzare in anteprima i documenti di esempio e visualizzare le statistiche di ricerca per perfezionare e migliorare i risultati della ricerca. Dopo aver soddisfatto che i risultati della ricerca contengano tutti i dati rilevanti per il caso, è necessario aggiungere i risultati della ricerca a un insieme di recensioni per un'ulteriore revisione, analisi e culling. Per ulteriori informazioni, vedere [Raccogliere dati per un caso.](collecting-data-for-ediscovery.md)

### <a name="reviewing-and-analyzing-case-data"></a>Revisione e analisi dei dati del caso

Usa la **scheda Review sets** per esaminare e analizzare il contenuto raccolto dal sistema live e aggiunto a un set di recensioni. Un *insieme* da rivedere è una raccolta statica di questi dati (in altre parole, una copia offline dei dati) dei dati dei depositario (e, se applicabile, i dati non relativi ai depositario) raccolti nella fase precedente del flusso di lavoro di eDiscovery. Quando si aggiungono risultati di ricerca a un insieme da rivedere, viene attivato un processo per estrarre i file dai contenitori, estrarre metadati ed estrarre testo. Al termine di questo processo, il sistema crea un nuovo indice di tutti i dati raccolti dai responsabile e lo aggiunge al set di recensioni. Dopo aver aggiunto i dati al set di revisioni, è possibile eseguire più query per restringere i dati del caso, visualizzare i dati come testo o nel formato di file nativo e annotare, redigere e contrassegnare i documenti nel set di revisioni. È inoltre possibile eseguire analisi avanzate, ad esempio identificare la duplicazione dei documenti, il threading della posta elettronica e i temi. Dopo aver definito i dati solo per quanto riguarda il caso, è possibile scaricare direttamente i documenti o esportarli insieme a metadati di file, annotazioni ed eventuali tag. Per altre informazioni, vedere:

- [Visualizzare i documenti in un insieme da rivedere](view-documents-in-review-set.md)

- [Eseguire query sui dati in un insieme da rivedere](review-set-search.md)

- [Contrassegnare i documenti in un insieme da rivedere](tagging-documents.md)

- [Analizzare i dati in un insieme da rivedere](analyzing-data-in-review-set.md)

### <a name="exporting-data-for-review-and-presentation"></a>Esportazione dei dati per la revisione e la presentazione

Dopo aver esportato i dati da un insieme da rivedere, utilizzare la scheda **Esportazioni** per gestire un processo di esportazione e scaricare i dati da un insieme da rivedere. Quando si esporta un set di recensioni, i dati vengono caricati in una posizione di Archiviazione di Azure fornita da Microsoft (o in una posizione di Archiviazione di Azure gestita dall'organizzazione). Dopo essere stato caricato in Azure, sarà quindi disponibile per il download in un computer locale. È possibile ottenere la chiave di valutazione di archiviazione necessaria per scaricare i dati esportati nella **scheda** Esportazioni. Per ulteriori informazioni, vedere [Esportare i dati del caso.](exporting-data-ediscover20.md)

### <a name="managing-jobs"></a>Gestione dei processi

Utilizzare la **scheda Processi** per monitorare i processi di lunga durata per le attività correlate ai casi avviate. Alcuni esempi di processi sono quelli relativi alla reindicizzazione, alla ricerca e all'esportazione dei dati del caso. Se ad esempio si crea  una ricerca nella scheda Ricerche che include molte origini dati, lo stato di questo processo di ricerca verrà visualizzato nella **scheda** Processi. Per ulteriori informazioni, vedere [Manage jobs.](managing-jobs-ediscovery20.md)

### <a name="configuring-case-settings"></a>Configurazione delle impostazioni del caso

Utilizzare la **scheda Impostazioni** per configurare le impostazioni per l'intero caso. Ciò include l'aggiunta di membri a un caso, la chiusura o l'eliminazione di un caso e la configurazione delle impostazioni di ricerca e analisi. Per altre informazioni, vedere:

- [Aggiungere membri a un caso](add-or-remove-members-from-a-case-in-advanced-ediscovery.md)

- [Chiudere o eliminare un caso](close-or-delete-case.md)

- [Configurare le impostazioni di ricerca e analisi](configure-search-and-analytics-settings-in-advanced-ediscovery.md)
