---
title: Gestire i processi in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: I processi di Advanced eDiscovery consentono di tenere traccia dello stato dei processi di lunga durata correlati all'esecuzione di varie attività di Advanced eDiscovery.
ms.openlocfilehash: 7b80df3f9891105d59a1741e9e0288ef0e67c25e
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2021
ms.locfileid: "50454657"
---
# <a name="manage-jobs-in-advanced-ediscovery"></a>Gestire i processi in Advanced eDiscovery

Ecco un elenco dei processi (che in genere sono processi di lunga durata) che vengono monitorati nella scheda **Processi** di un caso in Advanced eDiscovery. Questi processi vengono attivati dalle azioni dell'utente durante l'utilizzo e la gestione dei casi.

| Tipo processo            | Descrizione     |
| :----------------- | :----------     |
|Aggiunta di dati a un insieme da rivedere | Un utente aggiunge i risultati di una ricerca a un insieme da rivedere. Questo processo è costituito da due processi secondari: </br>• **GatheringItems:** viene generato un elenco di elementi che corrispondono alla query di ricerca (e all'origine dati di Microsoft 365 in cui si trovano). </br>• **Inserimento &** indicizzazione: gli elementi che corrispondono alla query di ricerca vengono copiati in un percorso di archiviazione di Azure (in un processo denominato *inserimento)* e quindi gli elementi nel percorso di archiviazione di Azure vengono reindicizzati. Questo nuovo indice viene utilizzato durante l'esecuzione di query e l'analisi degli elementi nel set di dati. </br></br>Per ulteriori informazioni, vedere [Aggiungere risultati di ricerca a un insieme da rivedere.](add-data-to-review-set.md) |
|Aggiunta di dati a un altro insieme da rivedere | Un utente aggiunge documenti da un insieme di recensioni a un altro insieme di revisioni nello stesso caso. Per ulteriori informazioni, vedere [Aggiungere dati a un insieme da rivedere da un altro insieme da rivedere.](add-data-to-review-set-from-another-review-set.md)|
|Aggiunta di dati non Di Microsoft 365 a un insieme da rivedere | Un utente carica dati non Di Microsoft 365 in un insieme da rivedere. Anche i dati vengono indicizzati durante questo processo. Ad esempio, i file di un file server locale o di un computer client vengono caricati in un insieme da rivedere. Per ulteriori informazioni, vedere [Caricare dati non Di Microsoft 365 in un insieme da rivedere.](load-non-office-365-data-into-a-review-set.md)| 
|Aggiunta di dati corretti a un insieme da rivedere | I dati con errori di elaborazione vengono corretti e caricati di nuovo in un insieme da rivedere. Per altre informazioni, vedere:</br>• [Correzione degli errori durante l'elaborazione dei dati](error-remediation-when-processing-data-in-advanced-ediscovery.md)</br>• [Correzione degli errori di un singolo elemento](single-item-error-remediation.md)| 
|Confronto dei set di carico | Un utente esamina le differenze tra diversi set di carico in un insieme da rivedere. Un set di carico è un'istanza di aggiunta di dati a un insieme da rivedere. Ad esempio, se si aggiungono i risultati di due ricerche diverse allo stesso insieme da rivedere, ognuna rappresenta un set di carico. |
|Ricostruzione della conversazione|Quando un utente aggiunge i risultati di una ricerca a un insieme di recensioni di conversazione, le conversazioni istantanee (denominate anche conversazioni in *thread)* in servizi come Microsoft Teams vengono ricostruite in un file PDF. Questo processo viene attivato anche quando un utente fa clic su **Azione > creare** PDF di conversazione in un insieme da rivedere. Per ulteriori informazioni, vedere [Esaminare le conversazioni in Advanced eDiscovery.](conversation-review-sets.md)
|Conversione di documenti redatti in PDF|Dopo che un utente ha annotato un documento in un insieme da rivedere e ne redigere una parte, può scegliere di convertire il documento redatto in un file PDF. In questo modo la parte redatta non sarà visibile se il documento viene esportato per la presentazione. Per ulteriori informazioni, vedere [Visualizzare documenti in un insieme da rivedere.](annotating-and-redacting-documents.md) |
|Stima dei risultati della ricerca | Dopo che un utente crea ed esegue una nuova ricerca (o esegue di nuovo una ricerca esistente), lo strumento di ricerca cerca nell'indice gli elementi che corrispondono alla query di ricerca e prepara una stima che include il numero e le dimensioni totali di tutti gli elementi in base alla ricerca e il numero di origini dati ricercate.  Per ulteriori informazioni, vedere [Raccogliere dati per un caso.](collecting-data-for-ediscovery.md) | 
|Preparazione dei dati per l'esportazione | Un utente esporta documenti da un insieme da rivedere. Al termine del processo di esportazione, possono scaricare i dati esportati in un computer locale. Per ulteriori informazioni, vedere [Esportare i dati del caso.](exporting-data-ediscover20.md) | 
|Preparazione per la risoluzione degli errori |Quando un utente seleziona un file e crea una nuova correzione  degli errori nella visualizzazione Errori nella scheda Elaborazione di un caso, il primo passaggio del processo consiste nel caricare il file con l'errore di elaborazione in un percorso di Archiviazione di Azure nel cloud Microsoft. Questo processo tiene traccia dello stato del processo di caricamento. Per ulteriori informazioni sul flusso di lavoro di correzione degli errori, vedere [Correzione degli errori durante l'elaborazione dei dati.](error-remediation-when-processing-data-in-advanced-ediscovery.md) | 
|Preparazione dell'anteprima della ricerca | Dopo che un utente crea ed esegue una nuova ricerca (o esegue di nuovo una ricerca esistente), lo strumento di ricerca prepara un sottoinsieme di elementi di esempio (corrispondenti alla query di ricerca) che possono essere visualizzati in anteprima. L'anteprima dei risultati della ricerca consente di determinare l'efficacia della ricerca.  Per ulteriori informazioni, vedere [Raccogliere dati per un caso.](collecting-data-for-ediscovery.md#view-search-results-and-statistics) | 
|Re-indexing custodian data | Quando si aggiunge un responsabile a un caso, tutti gli elementi parzialmente indicizzati nelle origini dati selezionate del responsabile vengono reindicizzati da un processo denominato *Indicizzazione avanzata.* Questo processo viene attivato anche  quando si  fa clic su Aggiorna indice nella scheda Elaborazione di un caso e quando si aggiorna l'indice per un responsabile specifico nella pagina a comparsa delle proprietà dei responsabile. Per ulteriori informazioni, vedere [Indicizzazione avanzata dei dati dei depositario.](indexing-custodian-data.md)
|Esecuzione dell'analisi | Un utente analizza i dati in un insieme da rivedere eseguendo strumenti di analisi di Advanced eDiscovery come il rilevamento quasi duplicato, l'analisi del threading della posta elettronica e l'analisi dei temi. Per ulteriori informazioni, vedere [Analizzare i dati in un insieme da rivedere.](analyzing-data-in-review-set.md) | 
|Applicazione di tag ai documenti | Questo processo viene attivato quando un utente fa clic su Avvia processo **di tagging** nel riquadro Di **tagging** durante la revisione dei documenti in un insieme da rivedere. Un utente può avviare questo processo dopo aver taggato i documenti in un insieme da rivedere e quindi averli selezionati in blocco nel riquadro dei documenti di visualizzazione. Per ulteriori informazioni, vedere [Aggiungere tag ai documenti in un insieme da rivedere.](tagging-documents.md) | 
|||

## <a name="job-status"></a>Stato processo

Nella tabella seguente vengono descritti i diversi stati di stato dei processi.

| Stato           | Descrizione     |
| :----------------- | :----------     |
| Inviato | È stato creato un nuovo processo.  La data e l'ora di invio del processo vengono visualizzate nella **colonna Creato** della **scheda** Processi. |
| Invio non riuscito | Invio del processo non riuscito.  È consigliabile tentare di eseguire di nuovo l'azione che ha attivato il processo. |
| In corso | Il processo è in corso, è possibile monitorare lo stato del processo nella **scheda** Processi. |
| Operazione riuscita | Il processo è stato completato correttamente. La data e l'ora di completamento del processo vengono visualizzate nella **colonna** Completato della **scheda** Processi. |
| Parzialmente riuscito | Il processo ha avuto esito positivo. Questo stato viene in genere restituito quando il processo non ha trovato dati parzialmente indicizzati (detti anche dati non indicizzati) in alcune delle origini dati dei responsabile.  |
| Non riuscito | Il processo non è riuscito.  È consigliabile tentare di eseguire di nuovo l'azione che ha attivato il processo. Se il processo non riesce una seconda volta, è consigliabile contattare il supporto tecnico Microsoft e fornire le informazioni di supporto del processo. |
|||
