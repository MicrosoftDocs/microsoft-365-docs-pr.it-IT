---
title: Panoramica della soluzione avanzata di eDiscovery in Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: In questo articolo viene descritta la nuova versione di Advanced eDiscovery in Microsoft 365.
ms.openlocfilehash: 0057b77b140d05093686029addc29e72e59cae11
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601773"
---
# <a name="overview-of-the-advanced-ediscovery-solution-in-microsoft-365"></a>Panoramica della soluzione avanzata di eDiscovery in Microsoft 365

La soluzione avanzata di eDiscovery in Microsoft 365 si basa sulle funzionalità esistenti di eDiscovery e analisi di Office 365. Questa nuova soluzione, denominata *Advanced eDiscovery*, offre un flusso di lavoro end-to-end per conservare, raccogliere, rivedere, analizzare ed esportare il contenuto rispondente alle indagini interne ed esterne dell'organizzazione. Consente inoltre ai team legali di gestire l'intero flusso di lavoro di notifica per la conservazione legale per comunicare con i depositari coinvolti in un caso. 

## <a name="alignment-with-edrm"></a>Allineamento con EDRM

Il flusso di lavoro incorporato di Advanced eDiscovery è allineato al processo eDiscovery descritto dal modello di riferimento di Electronic Discovery (EDRM). 

![EDRM (Electronic Discovery Reference Model)](media/EDRMv1.png)

(Fonte di immagini per gentile concessione di edrm.net. L'immagine di origine è stata resa disponibile nella licenza Creative Commons Attribution 3,0 Unported.

A livello elevato, ecco come Advanced eDiscovery supporta il flusso di lavoro di EDRM:

- **Identificazione.** Dopo aver identificato potenziali persone di interesse in un'indagine, è possibile aggiungerle come depositari (denominate anche *depositari dei dati*, in quanto potrebbero essere in possesso di informazioni rilevanti per l'indagine) in un caso di eDiscovery avanzato. Dopo che gli utenti vengono aggiunti come depositari, è facile conservare, raccogliere e rivedere i documenti del custode.

- **Conservazione.** Per conservare e proteggere i dati rilevanti per un'indagine, Advanced eDiscovery consente di inserire una conservazione legale sulle origini dati associate ai depositari in un caso. È inoltre possibile inserire i dati non detentivi in attesa. Advanced eDiscovery dispone anche di un flusso di lavoro di comunicazione incorporato in modo da poter inviare notifiche di archiviazione legale ai depositari e tenere conto dei loro ringraziamenti.

- **Raccolta.** Dopo aver identificato (e conservato) le origini dati rilevanti per l'analisi, è possibile utilizzare lo strumento di ricerca incorporato in Advanced eDiscovery Search for and Collect Live Data from the affidatario Data Sources (e non-affidatario Data Sources, se applicabile) potrebbe essere pertinente per il caso.

- **Elaborazione.** Dopo aver raccolto tutti i dati rilevanti per il caso, il passaggio successivo consiste nel processo per ulteriori riesami e analisi. In Advanced eDiscovery, i dati sul posto identificati nella fase di raccolta vengono copiati in un percorso di archiviazione di Azure (denominato *set di revisione*), in cui viene fornita una visualizzazione statica dei dati del caso. 
 
- **Recensione.** Dopo aver aggiunto i dati a un set di revisione, è possibile visualizzare documenti specifici ed eseguire un'altra query per ridurre i dati a ciò che è più pertinente per il caso. Inoltre, è possibile annotare e contrassegnare documenti specifici.
 
- **Analisi.** Advanced eDiscovery fornisce uno strumento di analisi integrata che consente di eliminare i dati dall'insieme di revisione che si determina non è pertinente per l'indagine. Oltre a ridurre il volume dei dati rilevanti, Advance eDiscovery aiuta anche a salvare i costi di revisione legale, consentendo di organizzare il contenuto per semplificare e rendere più efficiente il processo di revisione.

- **Produzione** e **presentazione.** Quando si è pronti, è possibile esportare i documenti da un set di revisione per la revisione legale. È possibile esportare documenti nel formato nativo o in un formato specificato per EDRM in modo che possano essere importati in applicazioni di revisione di terze parti.

## <a name="advanced-ediscovery-workflow"></a>Flusso di lavoro avanzato di eDiscovery

Nelle sezioni seguenti vengono descritti i singoli passaggi del flusso di lavoro incorporato in Advanced eDiscovery. Nella schermata seguente viene illustrata la scheda **Home** di un caso denominato *Product passivity 2019002*. Nota le schede del flusso di lavoro nella parte superiore della pagina vengono sequenziate per essere allineate al processo EDRM. 

Per ulteriori informazioni sul flusso di lavoro end-to-end in Advanced eDiscovery, vedere this [Microsoft Mechanics video](https://go.microsoft.com/fwlink/?linkid=2066133). 

![Le schede in Advanced eDiscovery seguono il flusso di lavoro di EDRM](media/aedisco-homepage-1.png)

## <a name="managing-custodians"></a>Gestione dei depositari

Utilizzare la scheda **depositari** per aggiungere e gestire le persone che sono state identificate come persone di interesse nel caso. Quando si aggiungono depositari, è possibile eseguire rapidamente azioni relative a un custode come l'archiviazione di un blocco legale su origini dati depositarie, la comunicazione con i depositari e la ricerca di origini dati depositarie per raccogliere contenuti rilevanti per il caso. Quando il caso progredisce, è facile aggiungere nuovi depositari o rilasciarli dal caso. Per ulteriori informazioni, vedere [lavorare con i depositari in Advanced eDiscovery](managing-custodians.md).

## <a name="managing-legal-hold-notifications"></a>Gestione delle notifiche di blocco legale

Utilizzare la scheda **comunicazioni** per gestire il processo di comunicazione con i depositari nel caso. Un avviso per la conservazione legale indica ai depositari di conservare i contenuti rilevanti per il caso. I team legali devono essere in grado di tenere conto delle notifiche ricevute, lette e riconosciute dai depositari. Il flusso di lavoro per le comunicazioni in Advanced eDiscovery consente di creare e inviare notifiche iniziali, promemoria, notifiche di rilascio e escalation se i depositari non riescono a riconoscere una notifica di blocco. Per ulteriori informazioni, vedere [work with Communications in Advanced eDiscovery](managing-custodian-communications.md).

## <a name="managing-content-preservation"></a>Gestione della conservazione dei contenuti

Quando si aggiunge un custode a un caso, è possibile applicare un blocco ai dati della custodia. Utilizzare la scheda **esenzioni** per gestire il blocco creato quando si aggiungono i depositari e per gestire altre esenzioni legali associate al caso. ad esempio, è possibile identificare e applicare un'esenzione su origini dati non detentive. È inoltre possibile modificare qualsiasi blocco nel caso e renderlo un blocco basato su query per conservare solo il contenuto che corrisponde alla query. Ad esempio, è possibile aggiungere un intervallo di date alla conservazione in modo che solo il contenuto creato all'interno di una data specifica sia stato conservato. È anche possibile ottenere statistiche sul contenuto che è in attesa, rimuovere il blocco dopo che non è più pertinente al caso o eliminarlo. Per ulteriori informazioni, vedere [Manage holds in Advanced eDiscovery](managing-holds.md).

## <a name="indexing-custodian-data"></a>Indicizzazione dei dati del custode

Quando si aggiunge un custode e le origini dati di custodia corrispondenti a un caso, qualsiasi elemento parzialmente indicizzato da un'origine dati di un oggetto depositaria viene reindicizzato tramite un processo denominato *Advanced indicizzazione*. In questo modo, è possibile eseguire ricerche per raccogliere i dati per il caso in cui vengano eseguiti contenuti di archiviazione, ad esempio immagini, tipi di file non supportati e altro contenuto potenzialmente non indicizzato. Utilizzare la scheda **elaborazione** per monitorare lo stato dell'indicizzazione avanzata e correggere gli errori di elaborazione utilizzando un *processo denominato correzione degli errori.* Per ulteriori informazioni, vedere [correggere gli errori di elaborazione in Advanced eDiscovery](processing-data-for-case.md).

## <a name="collecting-case-data"></a>Raccolta dei dati del caso

Utilizzare la scheda **ricerche** per creare ricerche per cercare le origini dati in locale e non detentive in Office 365 per i contenuti rilevanti per il caso. È possibile creare ed eseguire ricerche basate su query (utilizzando parole chiave e condizioni) per identificare un insieme di messaggi di posta elettronica e documenti rilevanti per il caso e che si desidera esaminare e analizzare ulteriormente nei passaggi successivi del flusso di lavoro di eDiscovery. È possibile creare una o più ricerche associate al caso. È inoltre possibile utilizzare lo strumento di ricerca per visualizzare in anteprima i documenti di esempio e visualizzare le statistiche di ricerca che consentono di affinare e migliorare i risultati della ricerca. Dopo aver soddisfatto i risultati della ricerca contengono tutti i dati rilevanti per il caso, è possibile aggiungere i risultati della ricerca a un set di revisione per ulteriori riesami, analisi e eliminazione. Per ulteriori informazioni, vedere [raccolta di dati per un caso in Advanced eDiscovery](collecting-data-for-ediscovery.md).

## <a name="reviewing-and-analyzing-case-data"></a>Revisione e analisi dei dati del caso

Utilizzare la scheda **revisione dei set** per esaminare e analizzare il contenuto raccolto dal sistema Live e aggiungerlo a un set di revisione. Un *set di revisione* è una raccolta statica di tali dati (in altre parole, una copia offline di dati) dei dati di custodia (e, se applicabile, i dati non detentivi) raccolti nella fase precedente del flusso di lavoro di eDiscovery. Quando si aggiungono i risultati di ricerca a un set di revisione, viene attivato un processo che estrae i file dai contenitori, estrae i metadati ed estrae il testo. Al termine del processo, il sistema crea un nuovo indice di tutti i dati raccolti dai depositari e lo aggiunge al set di revisione. Dopo aver aggiunto i dati al set di revisione, è possibile eseguire altre query per limitare i dati del caso, visualizzare i dati come testo o nel formato di file nativo e annotare, redigere e contrassegnare i documenti nel set di revisione. È inoltre possibile eseguire analisi avanzate, ad esempio la duplicazione dei documenti, il threading di posta elettronica e i temi. Dopo aver abbattuto i dati solo su ciò che è pertinente per il caso, è possibile scaricare i documenti direttamente o esportarli insieme ai metadati, alle annotazioni e ai tag dei file. Per altre informazioni, vedere:

- [Visualizzare i documenti in un insieme da rivedere](view-documents-in-review-set.md)
- [Eseguire query sui dati in un insieme da rivedere](review-set-search.md)
- [Contrassegnare i documenti in un insieme da rivedere](tagging-documents.md)
- [Analizzare i dati in un set di Revisione](analyzing-data-in-review-set.md)

## <a name="exporting-data-for-review-and-presentation"></a>Esportazione di dati per la revisione e la presentazione

Dopo aver esportato i dati da un set di revisione, utilizzare la scheda **Esporta** per gestire un processo di esportazione e scaricare i dati da un set di revisione. Quando si esporta un set di revisione, i dati vengono caricati in una posizione di archiviazione di Azure fornita da Microsoft (o in un percorso di archiviazione di Azure gestito dall'organizzazione). Dopo che è stato caricato in Azure, è disponibile per il download in un computer locale. È possibile ottenere la chiave di valutazione dell'archiviazione necessaria per scaricare i dati esportati nella scheda **esportazioni** . Per ulteriori informazioni, vedere [esportare i dati del caso in Advanced eDiscovery](exporting-data-ediscover20.md).

## <a name="managing-jobs"></a>Gestione dei processi

Utilizzare la scheda **processi** per monitorare i processi a esecuzione prolungata per le attività correlate al caso che sono state avviate. Alcuni esempi di processi includono quelli relativi alla reindicizzazione, alla ricerca e all'esportazione dei dati del caso. Ad esempio, se si crea una ricerca nella scheda **ricerche** che include molte origini dati, lo stato del processo di ricerca verrà visualizzato nella scheda **processi** . Per ulteriori informazioni, vedere [gestire i processi in Advanced eDiscovery](managing-jobs-ediscovery20.md).

## <a name="configuring-case-settings"></a>Configurazione delle impostazioni del caso

Utilizzare la scheda **Impostazioni** per configurare le impostazioni a livello di maiuscole e minuscole. Questo include l'aggiunta di membri a un caso, la chiusura o l'eliminazione di un caso e la configurazione delle impostazioni di ricerca e analisi.
