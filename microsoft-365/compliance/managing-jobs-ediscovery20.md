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
description: I processi avanzati di eDiscovery consentono di tenere traccia dello stato dei processi di lunga durata correlati all'esecuzione di varie attività di eDiscovery avanzate.
ms.openlocfilehash: 27ac98d1f98e85800c8ca3dfc91cc5e0803ae2e8
ms.sourcegitcommit: d4604e333507c6f57d5bf327531a241b649052de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "51471079"
---
# <a name="manage-jobs-in-advanced-ediscovery"></a>Gestire i processi in Advanced eDiscovery

Ecco un elenco dei processi (che in genere sono processi di lunga durata) che vengono monitorati nella scheda **Processi** di un caso in Advanced eDiscovery. Questi processi vengono attivati dalle azioni dell'utente durante l'utilizzo e la gestione dei casi.

| Tipo processo            | Descrizione     |
| :----------------- | :----------     |
|Aggiunta di dati a un set di recensioni | Un utente aggiunge una raccolta a un set di recensioni. Questo processo è costituito da due processi secondari: </br>• **Export:** viene generato un elenco di elementi nella raccolta. </br>• **Inserimento & indicizzazione** - Gli elementi nella raccolta che corrispondono alla query di ricerca vengono copiati in un percorso di archiviazione di Azure (in un processo denominato *inserimento)* e quindi tali elementi nel percorso di archiviazione di Azure vengono reindicizzati. Questo nuovo indice viene utilizzato durante l'esecuzione di query e l'analisi di elementi nel set di dati. </br></br>Per ulteriori informazioni, vedere [Add search results to a review set](add-data-to-review-set.md). |
|Aggiunta di dati a un altro set di revisione | Un utente aggiunge documenti da un set di revisione a un set di revisione diverso nello stesso caso. Per ulteriori informazioni, vedere [Aggiungere dati a un set di recensioni da un altro set di recensioni.](add-data-to-review-set-from-another-review-set.md)|
|Aggiunta di dati non Microsoft 365 a un set di recensioni | Un utente carica dati non Di Microsoft 365 in un set di recensioni. Anche i dati vengono indicizzati durante questo processo. Ad esempio, i file di un file server locale o di un computer client vengono caricati in un set di revisione. Per ulteriori informazioni, vedere [Load non-Microsoft 365 data into a review set](load-non-office-365-data-into-a-review-set.md).| 
|Aggiunta di dati corretti a un set di revisioni | I dati con errori di elaborazione vengono corretti e caricati di nuovo in un set di revisione. Per altre informazioni, vedere:</br>• [Correzione degli errori durante l'elaborazione dei dati](error-remediation-when-processing-data-in-advanced-ediscovery.md)</br>• [Correzione degli errori di un singolo elemento](single-item-error-remediation.md)| 
|Confronto dei set di carico | Un utente esamina le differenze tra diversi set di carico in un set di revisione. Un set di carico è un'istanza di aggiunta di dati a un set di revisione. Se ad esempio si aggiungono i risultati di due ricerche diverse allo stesso set di revisioni, ognuna rappresenterebbe un set di carico. |
|Ricostruzione delle conversazioni|Quando un utente aggiunge i risultati di una ricerca a un set di revisione delle conversazioni, le conversazioni istantanee (denominate anche conversazioni a *thread)* in servizi come Microsoft Teams vengono ricostruite in un file PDF. Questo processo viene attivato anche quando un utente fa clic su **Azione > CREARE** PDF di conversazione in un set di recensioni. Per ulteriori informazioni, vedere [Review conversations in Advanced eDiscovery.](conversation-review-sets.md)
|Conversione di documenti redatti in PDF|Dopo che un utente ha annotato un documento in un set di revisioni e ne ha redatto una parte, può scegliere di convertire il documento redatto in un file PDF. In questo modo si garantisce che la parte redatta non sia visibile se il documento viene esportato per la presentazione. Per ulteriori informazioni, vedere [View documents in a review set.](annotating-and-redacting-documents.md) |
|Stima dei risultati della ricerca | Dopo che un utente ha creato ed eseguito o eseguito di nuovo una bozza di raccolta, lo strumento di ricerca cerca nell'indice gli elementi che corrispondono alla query di ricerca e prepara una stima che include il numero e la dimensione totale di tutti gli elementi in base alla ricerca e il numero di origini dati ricercate.  Per ulteriori informazioni, vedere [Raccogliere dati per un caso.](collecting-data-for-ediscovery.md) | 
|Preparazione dei dati per l'esportazione | Un utente esporta documenti da un set di revisioni. Al termine del processo di esportazione, possono scaricare i dati esportati in un computer locale. Per ulteriori informazioni, vedere [Export case data](exporting-data-ediscover20.md). | 
|Preparazione per la risoluzione degli errori |Quando un utente seleziona un file e crea una nuova correzione  degli errori nella visualizzazione Errori nella scheda Elaborazione di un caso, il primo passaggio del processo consiste nel caricare il file con l'errore di elaborazione in un percorso di Archiviazione di Azure nel cloud Microsoft. Questo processo tiene traccia dello stato del processo di caricamento. Per ulteriori informazioni sul flusso di lavoro di correzione degli errori, vedere [Correzione degli errori durante l'elaborazione dei dati.](error-remediation-when-processing-data-in-advanced-ediscovery.md) | 
|Preparazione dell'anteprima della ricerca | Dopo che un utente crea ed esegue una nuova raccolta bozze (o riesegui una raccolta di bozze esistente), lo strumento di ricerca prepara un sottoinsieme di elementi di esempio (che corrispondono alla query di ricerca) che possono essere visualizzati in anteprima. L'anteprima dei risultati della ricerca consente di determinare l'efficacia della ricerca.  Per ulteriori informazioni, vedere [Raccogliere dati per un caso.](collecting-data-for-ediscovery.md#view-search-results-and-statistics) | 
|Re-indexing custodian data | Quando si aggiunge un responsabile a un caso, tutti gli elementi parzialmente indicizzati nelle origini dati selezionate del responsabile vengono reindicizzati da un processo denominato *Indicizzazione avanzata.* Questo processo viene attivato anche  quando si  fa clic su Aggiorna indice nella scheda Elaborazione di un caso e quando si aggiorna l'indice per un responsabile specifico nella pagina a comparsa delle proprietà del responsabile. Per ulteriori informazioni, vedere [Indicizzazione avanzata dei dati di custodia.](indexing-custodian-data.md)
|Esecuzione dell'analisi | Un utente analizza i dati in un set di revisione eseguendo strumenti di analisi avanzata di eDiscovery, ad esempio il rilevamento quasi duplicato, l'analisi del threading della posta elettronica e l'analisi dei temi. Per ulteriori informazioni, vedere [Analyze data in a review set.](analyzing-data-in-review-set.md) | 
|Applicazione di tag ai documenti | Questo processo viene attivato quando un utente fa clic su Avvia **processo di tagging** nel pannello **Tagging** durante la revisione dei documenti in un set di revisioni. Un utente può avviare questo processo dopo aver taggato i documenti in un set di revisioni e quindi averli selezionati in blocco nel riquadro dei documenti di visualizzazione. Per ulteriori informazioni, vedere [Tag documents in a review set](tagging-documents.md). | 
|||

## <a name="job-status"></a>Stato processo

Nella tabella seguente vengono descritti i diversi stati di stato dei processi.

| Stato           | Descrizione     |
| :----------------- | :----------     |
| Inviato | È stato creato un nuovo processo.  La data e l'ora di invio del processo vengono visualizzate nella **colonna Creato** della **scheda** Processi. |
| Invio non riuscito | Invio del processo non riuscito.  È consigliabile tentare di eseguire di nuovo l'azione che ha attivato il processo. |
| In corso | Il processo è in corso, è possibile monitorare lo stato del processo nella **scheda** Processi. |
| Riuscito | Il processo è stato completato correttamente. La data e l'ora di completamento del processo vengono visualizzate nella **colonna Completato** della **scheda** Processi. |
| Parzialmente riuscito | Il processo ha avuto esito positivo. Questo stato viene in genere restituito quando il processo non ha trovato dati parzialmente indicizzati (detti anche dati non indicizzati) in alcune delle origini dati di cui è responsabile.  |
| Esito negativo | Processo non riuscito.  È consigliabile tentare di eseguire di nuovo l'azione che ha attivato il processo. Se il processo ha esito negativo una seconda volta, è consigliabile contattare il supporto Tecnico Microsoft e fornire le informazioni di supporto del processo. |
|||
