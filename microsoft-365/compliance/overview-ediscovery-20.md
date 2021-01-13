---
title: Panoramica della soluzione avanzata di eDiscovery in Microsoft 365
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
description: Informazioni sulla soluzione avanzata di eDiscovery in Microsoft 365. In questo articolo viene fornita una panoramica delle funzionalità avanzate di eDiscovery in Microsoft 365, uno strumento che consente di gestire le indagini interne ed esterne. Inoltre, inquadra i motivi aziendali per l'utilizzo di Advanced eDiscovery per gestire le indagini legali.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1b2fa0b42a7f439aa65ae53e76e377ded92f97b7
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840879"
---
# <a name="overview-of-microsoft-365-advanced-ediscovery"></a>Panoramica di Microsoft 365 Advanced eDiscovery

La soluzione avanzata di eDiscovery in Microsoft 365 si basa sulle funzionalità di Microsoft eDiscovery e Analytics esistenti. Advanced eDiscovery offre un flusso di lavoro end-to-end per conservare, raccogliere, analizzare, esaminare, analizzare ed esportare contenuti rispondenti alle indagini interne ed esterne dell'organizzazione. Consente inoltre ai team legali di gestire l'intero flusso di lavoro di notifica per la conservazione legale per comunicare con i depositari coinvolti in un caso.

Advanced eDiscovery può aiutare l'organizzazione a rispondere a questioni legali o indagini interne scoprendo i dati in cui vive. È possibile gestire senza problemi i flussi di lavoro di eDiscovery identificando le persone di interesse e le relative origini dati, applicando senza problemi le esenzioni per conservare i dati e quindi gestire il processo di comunicazione per la conservazione legale. Raccogliendo i dati dall'origine, è possibile cercare la piattaforma Live Microsoft 365 per trovare rapidamente ciò che è necessario. Le funzionalità di apprendimento automatico, ad esempio l'indicizzazione profonda, il threading di posta elettronica e il rilevamento duplicati consentono inoltre di ridurre i grandi volumi di dati in un set di dati pertinente.

Nelle sezioni seguenti viene descritto il modo in cui queste funzionalità avanzate di eDiscovery possono aiutare la propria organizzazione.

## <a name="discover-and-collect-data-in-place"></a>Individuare e raccogliere dati sul posto

Tradizionalmente, le organizzazioni che si basano su più soluzioni di eDiscovery di terze parti richiedono la copia di grandi volumi di dati da Microsoft 365 per l'elaborazione e la necessità di ospitare dati duplicati. Questa necessità aumenta il tempo necessario per individuare i dati rilevanti e il rischio, il costo e la complessità della gestione di più soluzioni.

Advanced eDiscovery in Microsoft 365 consente di individuare i dati all'origine e di rimanere all'interno del limite di sicurezza e conformità di Microsoft 365.  Tramite la raccolta dei dati sul posto dal sistema Live, Advanced eDiscovery riduce l'attrito del rientro all'origine e riduce il lavoro non necessario per individuare il contenuto mancante, cosa che spesso accade quando l'inserimento nel journal è in ritardo nelle soluzioni di eDiscovery tradizionali.

Le funzionalità di ricerca e raccolta native per i dati in teams, Yammer, SharePoint Online, OneDrive for business e Exchange Online aumentano ulteriormente l'individuazione dei dati. Ad esempio, Advanced eDiscovery:

- Ricostruisce le conversazioni dei team (invece di restituire singoli messaggi dalle conversazioni).

- Raccoglie i contenuti basati su cloud condivisi con gli utenti tramite collegamenti o allegati moderni nelle chat dei messaggi di posta elettronica e dei team.

- Il supporto incorporato è costituito da centinaia di tipi di file non Microsoft 365.

- Raccoglie i dati provenienti da origini di terze parti (come Bloomberg, Facebook, slack e zoom meeting) importati e archiviati in Microsoft 365 da [Data Connectors](archiving-third-party-data.md).

## <a name="manage-ediscovery-workflow-in-one-platform"></a>Gestire il flusso di lavoro di eDiscovery in una piattaforma

Advanced eDiscovery può contribuire a ridurre il numero di soluzioni di eDiscovery di cui è necessario fare affidamento. Offre un flusso di lavoro end-to-end semplificato, tutto ciò che si verifica all'interno di Microsoft 365. Advanced eDiscovery contribuisce alla riduzione dell'attrito di identificazione e raccolta di potenziali fonti di informazioni rilevanti tramite la mappatura automatica delle origini dati condivise e univoche alla persona interessata (nota come *custode*), nonché fornendo relazioni e analisi su dati potenzialmente rilevanti prima di raccoglierla per l'analisi e la revisione.

Inoltre, le API di Microsoft Graph consentono di automatizzare il flusso di lavoro di eDiscovery e di estendere Advanced eDiscovery per soluzioni personalizzate.

## <a name="cull-data-intelligently"></a>Eliminazione dei dati in modo intelligente

Le funzionalità Intelligent Learning Machine in Advanced eDiscovery consentono di ridurre la quantità di dati da esaminare. Queste funzionalità intelligenti consentono di ridurre e abbattere grandi volumi di dati in un set pertinente. Ad esempio, una query set di revisione integrata consente di filtrare solo il contenuto univoco identificando i duplicati nei pressi. Questa funzionalità può ridurre in modo sostanziale la quantità di dati da esaminare.

Altre funzionalità di apprendimento automatico consentono di affinare e identificare i dati rilevanti tramite smart tag e strumenti di revisione assistita dalla tecnologia come i moduli di pertinenza.

## <a name="advanced-ediscovery-architecture"></a>Architettura di eDiscovery avanzata

Di seguito è riportato un diagramma di architettura di eDiscovery avanzato che consente di visualizzare il flusso di lavoro end-to-end in un ambiente geo singolo e in un ambiente multi-geografico e il flusso di dati end-to-end allineato al [modello di riferimento di Electronic Discovery](advanced-ediscovery-edrm.md) (EDRM).

[![Poster del modello: Advanced eDiscovery Architecture in Microsoft 365](../media/solutions-architecture-center/ediscovery-poster-thumb.png)](../media/solutions-architecture-center/m365-advanced-ediscovery-architecture.png)

[Visualizzazione come immagine](../media/solutions-architecture-center/m365-advanced-ediscovery-architecture.png)

[Scaricare come file PDF](https://download.microsoft.com/download/d/1/c/d1ce536d-9bcf-4d31-b75b-fcf0dc560665/m365-advanced-ediscovery-architecture.pdf)

[Scaricare come file di Visio](https://download.microsoft.com/download/d/1/c/d1ce536d-9bcf-4d31-b75b-fcf0dc560665/m365-advanced-ediscovery-architecture.vsdx)

Per ulteriori informazioni sul flusso di lavoro end-to-end in Advanced eDiscovery, vedere this [Microsoft Mechanics video](https://go.microsoft.com/fwlink/?linkid=2066133).

## <a name="advanced-ediscovery-workflow"></a>Flusso di lavoro avanzato di eDiscovery

Nelle sezioni seguenti vengono descritti i singoli passaggi del flusso di lavoro incorporato nello strumento Advanced eDiscovery nel centro conformità di Microsoft 365. Nella schermata seguente viene illustrata la scheda **Panoramica** di un caso denominato *2020.11.03-contoso v. fabrikam*.

![Schede del flusso di lavoro avanzato di eDiscovery incorporato](../media/AeD-Case-Screenshot1.png)

Per informazioni più dettagliate, vedere [Manage the Advanced eDiscovery Workflow](create-and-manage-advanced-ediscoveryv2-case.md#manage-the-workflow).

### <a name="managing-custodians-and-non-custodial-data-sources"></a>Gestione di depositari e origini dati non detentive

Utilizzare la scheda **origini dati** per aggiungere e gestire le persone che sono state identificate come persone di interesse nel caso e altre origini dati che potrebbero non essere associate a un custode. Quando si aggiungono conservanti o origini dati non detentive, è possibile eseguire rapidamente azioni come l'archiviazione legale su fonti di dati depositarie e non detentive, la comunicazione con i depositari e la ricerca di fonti di dati depositarie e non detentive per raccogliere contenuti rilevanti per il caso. Quando il caso progredisce, è facile aggiungere nuovi depositari o fonti di data non detentive o rilasciarli dal caso. Per ulteriori informazioni, vedere [lavorare con i depositari](managing-custodians.md).

### <a name="managing-legal-hold-notifications"></a>Gestione delle notifiche di blocco legale

Utilizzare la scheda **comunicazioni** per gestire il processo di comunicazione con i depositari nel caso. Un avviso per la conservazione legale indica ai depositari di conservare i contenuti rilevanti per il caso. I team legali devono essere in grado di tenere conto delle notifiche ricevute, lette e riconosciute dai depositari. Il flusso di lavoro per le comunicazioni in Advanced eDiscovery consente di creare e inviare notifiche iniziali, promemoria, notifiche di rilascio e escalation se i depositari non riescono a riconoscere una notifica di blocco. Per ulteriori informazioni, vedere [lavorare con le comunicazioni](managing-custodian-communications.md).

### <a name="managing-content-preservation"></a>Gestione della conservazione dei contenuti

Quando si aggiunge un custode a un caso, è possibile applicare un blocco ai dati della custodia. Utilizzare la scheda **blocco** per gestire il blocco creato quando si aggiungono i depositari e per gestire altre esenzioni legali associate al caso. ad esempio, è possibile identificare e applicare un'esenzione su origini dati non detentive. È inoltre possibile modificare qualsiasi blocco nel caso e renderlo un blocco basato su query per conservare solo il contenuto che corrisponde alla query. Ad esempio, è possibile aggiungere un intervallo di date alla conservazione in modo che solo il contenuto creato all'interno di una data specifica sia stato conservato. È anche possibile ottenere statistiche sul contenuto che è in attesa, rimuovere il blocco dopo che non è più pertinente al caso o eliminarlo. Per ulteriori informazioni, vedere [gestione delle esenzioni](managing-holds.md).

### <a name="indexing-custodian-data"></a>Indicizzazione dei dati del custode

Quando si aggiunge un custode e le origini dati di custodia corrispondenti a un caso, tutti gli elementi parzialmente indicizzati provenienti da un'origine dati di un oggetto depositaria vengono reindicizzati tramite un processo denominato *Advanced indicizzazione*. In questo modo, è possibile eseguire ricerche per raccogliere i dati per il caso in cui vengano eseguiti contenuti di archiviazione, ad esempio immagini, tipi di file non supportati e altro contenuto potenzialmente non indicizzato. Utilizzare la scheda **elaborazione** per monitorare lo stato dell'indicizzazione avanzata e correggere gli errori di elaborazione utilizzando un *processo denominato correzione degli errori.* Per ulteriori informazioni, vedere [correggere gli errori di elaborazione](processing-data-for-case.md).

### <a name="collecting-case-data"></a>Raccolta dei dati del caso

Utilizzare la scheda **ricerche** per creare ricerche per cercare le origini dati in locale e non detentive per il contenuto pertinente del caso. È possibile creare ed eseguire ricerche basate su query (utilizzando parole chiave e condizioni) per identificare un insieme di messaggi di posta elettronica e documenti rilevanti per il caso e che si desidera esaminare e analizzare ulteriormente nei passaggi successivi del flusso di lavoro di eDiscovery. È possibile creare una o più ricerche associate al caso. È inoltre possibile utilizzare lo strumento di ricerca per visualizzare in anteprima i documenti di esempio e visualizzare le statistiche di ricerca che consentono di affinare e migliorare i risultati della ricerca. Dopo aver soddisfatto i risultati della ricerca contengono tutti i dati rilevanti per il caso, è possibile aggiungere i risultati della ricerca a un set di revisione per ulteriori riesami, analisi e eliminazione. Per ulteriori informazioni, vedere [Collect Data for a case](collecting-data-for-ediscovery.md).

### <a name="reviewing-and-analyzing-case-data"></a>Revisione e analisi dei dati del caso

Utilizzare la scheda **revisione dei set** per esaminare e analizzare il contenuto raccolto dal sistema Live e aggiungerlo a un set di revisione. Un *set di revisione* è una raccolta statica di tali dati (in altre parole, una copia offline di dati) dei dati di custodia (e, se applicabile, i dati non detentivi) raccolti nella fase precedente del flusso di lavoro di eDiscovery. Quando si aggiungono i risultati di ricerca a un set di revisione, viene attivato un processo per estrarre i file dai contenitori, estrarre i metadati ed estrarre il testo. Al termine del processo, il sistema crea un nuovo indice di tutti i dati raccolti dai depositari e lo aggiunge al set di revisione. Dopo aver aggiunto i dati al set di revisione, è possibile eseguire altre query per limitare i dati del caso, visualizzare i dati come testo o nel formato di file nativo e annotare, redigere e contrassegnare i documenti nel set di revisione. È inoltre possibile eseguire analisi avanzate, ad esempio la duplicazione dei documenti, il threading di posta elettronica e i temi. Dopo aver abbattuto i dati solo su ciò che è pertinente per il caso, è possibile scaricare i documenti direttamente o esportarli insieme ai metadati, alle annotazioni e ai tag dei file. Per altre informazioni, vedere:

- [Visualizzare i documenti in un insieme da rivedere](view-documents-in-review-set.md)

- [Eseguire query sui dati in un insieme da rivedere](review-set-search.md)

- [Contrassegnare i documenti in un insieme da rivedere](tagging-documents.md)

- [Analizzare i dati in un set di Revisione](analyzing-data-in-review-set.md)

### <a name="exporting-data-for-review-and-presentation"></a>Esportazione di dati per la revisione e la presentazione

Dopo aver esportato i dati da un set di revisione, utilizzare la scheda **Esporta** per gestire un processo di esportazione e scaricare i dati da un set di revisione. Quando si esporta un set di revisione, i dati vengono caricati in una posizione di archiviazione di Azure fornita da Microsoft (o in un percorso di archiviazione di Azure gestito dall'organizzazione). Dopo che è stato caricato in Azure, è disponibile per il download in un computer locale. È possibile ottenere la chiave di valutazione dell'archiviazione necessaria per scaricare i dati esportati nella scheda **esportazioni** . Per ulteriori informazioni, vedere [Export case data](exporting-data-ediscover20.md).

### <a name="managing-jobs"></a>Gestione dei processi

Utilizzare la scheda **processi** per monitorare i processi a esecuzione prolungata per le attività correlate al caso che sono state avviate. Alcuni esempi di processi includono quelli relativi alla reindicizzazione, alla ricerca e all'esportazione dei dati del caso. Ad esempio, se si crea una ricerca nella scheda **ricerche** che include molte origini dati, lo stato del processo di ricerca verrà visualizzato nella scheda **processi** . Per ulteriori informazioni, vedere [gestire i processi](managing-jobs-ediscovery20.md).

### <a name="configuring-case-settings"></a>Configurazione delle impostazioni del caso

Utilizzare la scheda **Impostazioni** per configurare le impostazioni a livello di maiuscole e minuscole. Questo include l'aggiunta di membri a un caso, la chiusura o l'eliminazione di un caso e la configurazione delle impostazioni di ricerca e analisi. Per altre informazioni, vedere:

- [Aggiungere membri a un caso](add-or-remove-members-from-a-case-in-advanced-ediscovery.md)

- [Chiudere o eliminare un caso](close-or-delete-case.md)

- [Configurare le impostazioni di ricerca e analisi](configure-search-and-analytics-settings-in-advanced-ediscovery.md)
