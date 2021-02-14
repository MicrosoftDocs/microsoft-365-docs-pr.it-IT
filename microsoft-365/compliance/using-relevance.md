---
title: Usare il modulo Rilevanza per analizzare i dati in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Informazioni su come il modulo Pertinenza analizza i dati in evidenza con una descrizione dei passaggi di formazione e flusso di lavoro per pertinenza in Advanced eDiscovery.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 4a05ec47a4a6b2100c062912e7668c2bf785caf7
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2020
ms.locfileid: "48286062"
---
# <a name="use-the-relevance-module-to-analyze-data-in-advanced-ediscovery"></a>Usare il modulo Rilevanza per analizzare i dati in Advanced eDiscovery

In Advanced eDiscovery, il modulo Pertinenza include la formazione sulla rilevanza e la revisione dei file correlati a un caso. Per usare il flusso di lavoro Pertinenza, passare a Gestire il set di recensioni all'interno di un insieme di recensioni e fare clic su Mostra pertinenza. Per avviare il flusso di lavoro, è necessario eseguire alcuni passaggi:

- Processo: ogni set di carico aggiunto al set da rivedere verrà visualizzato come "contenitore" qui. È necessario elaborare questi documenti prima di poterli aggiungere al modulo Pertinenza; questo è anche il punto in cui è possibile contrassegnarli come seed o pre-tagged per un problema specifico.

- Aggiungi alla pertinenza: in Carichi di pertinenza è possibile aggiungere documenti elaborati alla rilevanza per renderli \> disponibili per la formazione.

Il flusso di lavoro Pertinenza viene visualizzato e descritto come segue:
  
![Flusso di lavoro di pertinenza](../media/44c67dd2-7a20-40a9-b0ed-784364845c77.gif)
  
- **Cicli di valutazione e verifica:**
    
  - **Valutazione:** consente la valutazione anticipata in base a un campione casuale di file e utilizza questa valutazione per applicare le decisioni per determinare le prestazioni del processo di codifica predittivo. 
    
  - **Traccia:** calcolare e visualizzare i risultati provvisori della valutazione monitorando la validità statistica del processo. 
    
- **Cicli di formazione e tracciamento**
    
  - **Tag:** Advanced eDiscovery apprende i criteri di rilevanza specifici per ogni problema in base alla revisione iterativa dell'esperto e al tagging dei singoli file.
    
  - **Traccia:** calcolare e visualizzare i risultati provvisori della formazione sulla rilevanza monitorando la validità statistica del processo. 
    
- **Calcolo in** batch: i criteri di rilevanza accumulati e appresi vengono applicati all'intera raccolta di file e viene generato un punteggio di rilevanza per ogni file.
    
- **Decidere**: i risultati dell'analisi applicata all'intero caso vengono visualizzati dopo il calcolo batch e vengono visualizzati i dati utilizzati per prendere decisioni di revisione dei documenti.
    
- **Test:** i risultati possono essere testati per verificare la validità e l'efficacia dell'elaborazione di Advanced eDiscovery.

- **Ricerca:** una volta completato il flusso di lavoro Pertinenza, è possibile utilizzare l'output, ad esempio il percentile di lettura di un documento per il problema, quando si esegue una query all'interno del set di revisioni.
    
## <a name="guidelines-for-relevance-training-and-review"></a>Linee guida per la formazione e la revisione della rilevanza

Di seguito è riportata una panoramica delle linee guida per la formazione e la revisione della rilevanza:
  
- **Errori e incoerenze:** se durante il training vengono effettuati errori di tagging, tornare agli esempi di file precedenti per correggerli. Se sono presenti troppi errori da correggere o esiste una nuova prospettiva del caso o del problema, i criteri di pertinenza devono essere ridefiniti dall'amministratore e il training della rilevanza viene riavviato.
    
- **Tagging e formazione:** 
    
  - I file devono essere contrassegnati solo in base al contenuto. Non considerare i metadati, ad esempio il responsabile, la data o il percorso del file. 
    
  - Non considerare le indicazioni dell'intervallo di date nel testo durante l'aggiunta di tag ai file.
    
  - Non considerare le immagini grafiche incorporate durante il tagging dei file.
     
  - Il testo ignorato applicato alla rilevanza verrà rimosso nel contenuto del file visualizzato nella visualizzazione testo in Pertinenza. Se i valori per Ignora testo sono stati definiti dopo l'inizio del training della rilevanza, il nuovo testo ignorato verrà applicato ai file di esempio creati dal punto in cui è stato definito. La funzionalità Ignora testo deve essere utilizzata con cautela, in quanto il suo utilizzo può ridurre le prestazioni dell'analisi dei file
    
  - Utilizzare **l'opzione Ignora tagging** solo se necessario. Advanced eDiscovery non si forma in base ai file ignorati. Nella valutazione, se è difficile stabilire se un file è rilevante, è meglio contrassegnare come rilevante (R) o Non rilevante (NR) quando possibile anziché selezionare **Ignora.** Quando Advanced eDiscovery valuta la formazione, si può vedere quanto bene sono stati elaborati questi tipi di file.
    
  - Anche i file con una quantità molto ridotta di testo estratto devono essere contrassegnati come R/NR, anziché come "Skip", quando possibile. 
    
  - Il tagging può influire sul classificatore, purché il file sia leggibile e possa essere contrassegnato come R/NR.
    
  - Il numero di sequenza del file nell'elenco dei file di esempio visualizzato nella scheda **Tag** consente all'utente di tornare all'ordine di visualizzazione originale dei file. 
    
  - È possibile tornare a qualsiasi esempio e modificare il tagging dei file del set di valutazione e formazione. Le modifiche verranno applicate durante la creazione dell'esempio successivo.
    
  - I file Excel analizzati in formato PDF devono essere considerati come i file di Excel nativi durante l'aggiunta di tag ai file.
    
  - In caso di dubbi sul tagging per pertinenza di un file, rivolgersi a un esperto. Il tagging non corretto durante la formazione sulla rilevanza può causare una perdita di tempo più avanti nel processo e può avere un impatto negativo sulla qualità dei risultati complessivi.
    
  - Le parole chiave definite negli elenchi di parole chiave verranno visualizzate in colori per consentire all'utente di identificare i file rilevanti durante l'aggiunta di tag.
    
- **Calcolo batch:** i file contrassegnati come R/NR dall'esperto riceveranno un punteggio pari a 0 o 100. Questo vale per il tagging eseguito prima del calcolo batch. Se l'esperto ha commutato il problema su Inattivo dopo il calcolo del batch e ha continuato a contrassegnare questo problema, i nuovi punteggi contrassegnati non saranno 100/0, ma il punteggio originale.
    
- Problemi **e** modalità di campionamento: i problemi vengono in genere disattivati al termine del lavoro su di essi (la formazione sulla pertinenza viene stabilizzata e viene eseguito il calcolo batch), quando i problemi vengono annullati o quando un altro utente sta lavorando sui problemi.
    
## <a name="steps-in-relevance-training"></a>Passaggi della formazione sulla rilevanza

Nella scheda **Traccia di \> pertinenza,** Advanced eDiscovery fornisce suggerimenti su come procedere con l'elaborazione, con i passaggi successivi seguenti. Le implicazioni sono descritte di seguito quando ognuno dei passaggi seguenti è consigliato nel processo di formazione sulla rilevanza. 
  
- Tagging /Continua tagging: revisione dei file e tagging per pertinenza eseguiti da un esperto per ogni file e problema all'interno di un campione.
    
  - Implicazione: un esempio esistente deve essere contrassegnato.
    
- Valutazione/valutazione continua: consente la convalida anticipata della pertinenza del caso e una visualizzazione preliminare della pertinenza della popolazione di file importata per il caso corrente.
    
  - Implicazione: è necessaria o consigliata una valutazione maggiore.
    
- Formazione e formazione continua: processo durante il quale Advanced eDiscovery apprende dall'esperto che contrassegna gli esempi di file e acquisisce la possibilità di identificare i criteri di pertinenza pertinenti a ogni problema nel contesto di ogni caso.
    
  - Implication: The issue needs more training; L'esempio successivo deve essere creato e contrassegnato. 
    
- Calcolo batch: processo di pertinenza in cui Advanced eDiscovery acquisisce le conoscenze acquisite durante la fase di formazione e la applica all'intera popolazione di file. Tutti i file nel gruppo di file pertinente vengono valutati per pertinenza e assegnati a un punteggio di pertinenza.
    
  - Implicazione: il problema si è stabilizzato ed è possibile eseguire il calcolo batch.
    
- Catch-up: La rilevanza indica quando un esperto rivede e contrassegna un campione di file selezionati da un carico di file aggiuntivo durante uno scenario di caricamento in sequenza.
    
  - Implicazione: è stato aggiunto un nuovo carico ed è necessario recuperare il carico per continuare a funzionare.
    
- Incoerenze dei tag: il processo identifica, tramite un algoritmo di Advanced eDiscovery, le incoerenze nel processo di tagging dei file che possono influire negativamente sull'analisi.
    
  - Implicazione: l'esempio successivo includerà i file che sono stati contrassegnati negli esempi precedenti e il tagging deve essere riecluso.
    
- Classificatore di aggiornamento: consente all'utente di applicare modifiche di tagging o seeding.
    
  - Implicazione: le modifiche di tagging e seeding possono essere applicate senza dover eseguire manualmente un altro esempio di pertinenza.
    
- In attesa: il processo di formazione sulla rilevanza è stato completato.
    
  - Implicazione: a questo punto non è richiesto alcun corso di formazione sulla rilevanza.
    
Anche se Advanced eDiscovery guida l'utente attraverso il processo, con i passaggi successivi consigliati in diverse fasi, consente anche di spostarsi tra schede e pagine e di effettuare scelte per affrontare le situazioni che possono essere pertinenti al singolo caso, problema o processo di revisione dei documenti. 
  
È possibile accettare o sostituire le scelte di elaborazione del passaggio successivo di Advanced eDiscovery. Se si desidera eseguire un passaggio diverso dal  passaggio successivo consigliato, fare clic sul passaggio  successivo elencato nella visualizzazione del problema espanso nella finestra di dialogo, fare clic sul pulsante Modifica accanto al passaggio successivo e selezionare un'altra opzione passaggio successivo. 
  
> [!NOTE]
> Alcune opzioni potrebbero rimanere disabilitate dopo lo sblocco perché non sono supportate per l'uso a quel punto del processo. 
  
## <a name="more-information"></a>Altre informazioni

[Informazioni sulla valutazione della rilevanza](assessment-in-relevance-in-advanced-ediscovery.md)
  
[Tagging e valutazione](tagging-and-assessment-in-advanced-ediscovery.md)
  
[Formazione su tagging e pertinenza](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[Monitoraggio dell'analisi della rilevanza](track-relevance-analysis-in-advanced-ediscovery.md)
  
[Decidere in base ai risultati](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[Test dell'analisi di rilevanza](test-relevance-analysis-in-advanced-ediscovery.md)

[Eseguire query sui dati in un insieme da rivedere](review-set-search.md)
