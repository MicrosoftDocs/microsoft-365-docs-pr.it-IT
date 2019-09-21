---
title: Gestire i processi in Advanced eDiscovery
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
description: ''
ms.openlocfilehash: c0dd3b19f1fb666e07f70c36db05ed520093bfac
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37083775"
---
# <a name="manage-jobs-in-advanced-ediscovery"></a>Gestire i processi in Advanced eDiscovery

Di seguito è indicato un elenco dei processi (che in genere sono di lunga durata) che vengono registrati nella scheda **processi** di un caso in Advanced eDiscovery. Questi processi vengono attivati dalle azioni dell'utente durante l'utilizzo e la gestione dei casi.

| Tipo processo            | Descrizione     |
| :----------------- | :----------     |
|Aggiunta di dati a un set di Revisione | Un utente aggiunge i risultati di una ricerca a un set di revisione. Questo processo è costituito da due processi secondari: </br> </br>• **GatheringItems** -viene generato un elenco di elementi che corrispondono alla query di ricerca (e all'origine dati di Office 365 in cui si trovano). </br>• **Ingestione & indicizzazione** -gli elementi che corrispondono alla query di ricerca vengono copiati in un percorso di archiviazione di Azure (in un processo denominato *ingestione*) e quindi gli elementi nel percorso di archiviazione di Azure vengono reindicizzati. Questo nuovo indice viene utilizzato per l'esecuzione di query e l'analisi degli elementi nel set di dati. </br></br>Per ulteriori informazioni, vedere [Add Search results to a Review set](add-data-to-review-set.md). |
|Aggiunta di dati a un altro set di Revisione | Un utente aggiunge i documenti da un set di revisione a un diverso set di revisione nello stesso caso. Per ulteriori informazioni, vedere [aggiungere dati a un set di revisione da un altro set di revisione](add-data-to-review-set-from-another-review-set.md).|
|Aggiunta di dati non di Office 365 a un set di Revisione | Un utente carica i dati non di Office 365 in un set di revisione. I dati vengono indicizzati anche durante questo processo. Ad esempio, i file provenienti da un server di file locale o da un computer client vengono caricati in un set di revisione. Per ulteriori informazioni, vedere [caricare i dati non di Office 365 in un set di revisione](load-non-office365-data.md).| 
|Aggiunta di dati corretti a un set di Revisione | I dati con errori di elaborazione vengono corretti e caricati di nuovo in un set di revisione. Per ulteriori informazioni, vedere [correzione degli errori durante l'elaborazione dei dati](error-remediation.md). | 
|Confronto tra set di carico | Un utente esamina le differenze tra set di carico diversi in un set di revisione. Un set di carichi è un'istanza di aggiunta di dati a un set di revisione. Ad esempio, se si aggiungono i risultati di due ricerche diverse allo stesso set di revisione, ognuno di essi rappresenterà un set di carico. Per ulteriori informazioni, vedere [gestire i set di carico](manage-load-sets.md). |
|Conversione di documenti redatti in formato PDF|Dopo che un utente ha annotato un documento in un set di revisione e ne redacts una parte, può scegliere di convertire il documento redatto in un file PDF. Questo garantisce che la parte redatta non sarà visibile se il documento viene esportato per la presentazione. Per ulteriori informazioni, vedere [visualizzare i documenti in un set di revisione](annotating-and-redacting-documents.md). |
|Stima dei risultati della ricerca | Dopo che un utente ha creato ed eseguito una nuova ricerca (o ha rieseguito una ricerca esistente), lo strumento di ricerca Cerca l'indice per gli elementi che corrispondono alla query di ricerca e prepara una stima che include il numero e la dimensione totale di tutti gli elementi in base alla ricerca e il numero di origini dati che bruciano Ched.  Per ulteriori informazioni, vedere [Collect Data for a case](collecting-data-for-ediscovery.md). | 
|Preparazione dei dati per l'esportazione | Un utente esporta i documenti da un set di revisione. Al termine del processo di esportazione, è possibile scaricare i dati esportati in un computer locale. Per ulteriori informazioni, vedere [Export case data](exporting-data-ediscover20.md). | 
|Preparazione per la risoluzione degli errori |Quando un utente seleziona un file e crea una nuova correzione degli errori nella visualizzazione errori nella scheda **elaborazione** di un caso, il primo passaggio del processo consiste nel caricare il file che ha l'errore di elaborazione in una posizione di archiviazione di Azure nel cloud Microsoft. Questo processo tiene traccia dello stato di avanzamento della procedura di caricamento. Per ulteriori informazioni sul flusso di lavoro per la correzione degli errori, vedere correzione degli [errori durante l'elaborazione dei dati](error-remediation.md). | 
|Preparazione dell'anteprima di ricerca | Dopo che un utente ha creato ed eseguito una nuova ricerca (o ha rieseguito una ricerca esistente), lo strumento di ricerca prepara un sottoinsieme di elementi di esempio (che corrispondono alla query di ricerca) che è possibile visualizzare in anteprima. La visualizzazione in anteprima dei risultati della ricerca consente di determinare l'efficacia della ricerca.  Per ulteriori informazioni, vedere [Collect Data for a case](collecting-data-for-ediscovery.md#view-search-results-and-statistics). | 
|Reindicizzazione dei dati del custode | Quando si aggiunge un custode a un caso, tutti gli elementi parzialmente indicizzati nelle origini dati selezionate del custode vengono reindicizzati da un processo denominato *Advanced indicizzazione*. Questo processo viene attivato anche quando si fa clic su **Aggiorna indice** nella visualizzazione indice nella scheda **elaborazione** di un caso. Per ulteriori informazioni, vedere [Advanced indicizzazione dei dati del custode](indexing-custodian-data.md).
|Esecuzione di analisi | Un utente analizza i dati in un set di revisione eseguendo strumenti di analisi avanzata di eDiscovery, ad esempio vicino al rilevamento duplicato, all'analisi del threading di posta elettronica e all'analisi dei temi. Per ulteriori informazioni, vedere [analyze data in a Review set](analyzing-data-in-review-set.md). | 
|Contrassegnare i documenti | Questo processo viene attivato quando un utente fa clic su **Avvia processo di tagging** nel **Pannello di tagging** quando si esaminano i documenti in un set di revisione. Un utente può avviare questo processo dopo aver eseguito il tag dei documenti in un set di revisione e quindi selezionarli in blocco nel pannello Visualizza documento. Per ulteriori informazioni, vedere [tag Documents in a Review set](tagging-documents.md). | 
|||


## <a name="job-status"></a>Stato processo

Nella tabella seguente vengono descritti i diversi Stati di stato per i processi.

| Stato           | Descrizione     |
| :----------------- | :----------     |
| Inserita | È stato creato un nuovo processo.  La data e l'ora in cui il processo è stato inviato viene visualizzato nella colonna **creato** nella scheda **processi** . |
| Invio non riuscito | L'invio dei processi ha avuto esito negativo.  È consigliabile tentare di rieseguire l'azione che ha attivato il processo. |
| In corso | Il processo è in corso, è possibile monitorare lo stato del processo nella scheda **processi** . |
| Corretta | Il processo è stato completato correttamente. La data e l'ora in cui il processo è stato completato viene visualizzato nella colonna **completato** nella scheda **processi** . |
| Parzialmente completata | Il processo ha avuto esito positivo. |
| Failed | Il processo ha avuto esito negativo.  È consigliabile tentare di rieseguire l'azione che ha attivato il processo. Se il processo ha esito negativo una seconda volta, è consigliabile contattare il supporto tecnico Microsoft e fornire le informazioni sul supporto del processo. |
