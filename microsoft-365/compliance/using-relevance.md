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
# <a name="use-the-relevance-module-to-analyze-data-in-advanced-ediscovery"></a><span data-ttu-id="cd141-103">Usare il modulo Rilevanza per analizzare i dati in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="cd141-103">Use the Relevance module to analyze data in Advanced eDiscovery</span></span>

<span data-ttu-id="cd141-104">In Advanced eDiscovery, il modulo Pertinenza include la formazione sulla rilevanza e la revisione dei file correlati a un caso.</span><span class="sxs-lookup"><span data-stu-id="cd141-104">In Advanced eDiscovery, the Relevance module includes the Relevance training and review of files related to a case.</span></span> <span data-ttu-id="cd141-105">Per usare il flusso di lavoro Pertinenza, passare a Gestire il set di recensioni all'interno di un insieme di recensioni e fare clic su Mostra pertinenza.</span><span class="sxs-lookup"><span data-stu-id="cd141-105">In order to use the Relevance workflow, go to Manage review set within a review set and click on Show Relevance.</span></span> <span data-ttu-id="cd141-106">Per avviare il flusso di lavoro, è necessario eseguire alcuni passaggi:</span><span class="sxs-lookup"><span data-stu-id="cd141-106">There are a couple of steps you need to complete before you can start the workflow:</span></span>

- <span data-ttu-id="cd141-107">Processo: ogni set di carico aggiunto al set da rivedere verrà visualizzato come "contenitore" qui.</span><span class="sxs-lookup"><span data-stu-id="cd141-107">Process: each load set added to the review set will show up as a "container" here.</span></span> <span data-ttu-id="cd141-108">È necessario elaborare questi documenti prima di poterli aggiungere al modulo Pertinenza; questo è anche il punto in cui è possibile contrassegnarli come seed o pre-tagged per un problema specifico.</span><span class="sxs-lookup"><span data-stu-id="cd141-108">You need to process these documents before you can add them to Relevance module; this is also where you can mark them as seed or pre-tagged for a specific issue.</span></span>

- <span data-ttu-id="cd141-109">Aggiungi alla pertinenza: in Carichi di pertinenza è possibile aggiungere documenti elaborati alla rilevanza per renderli \> disponibili per la formazione.</span><span class="sxs-lookup"><span data-stu-id="cd141-109">Add to Relevance: Under Relevance \> Loads, you can add documents that have been processed to Relevance to make them available for training.</span></span>

<span data-ttu-id="cd141-110">Il flusso di lavoro Pertinenza viene visualizzato e descritto come segue:</span><span class="sxs-lookup"><span data-stu-id="cd141-110">The Relevance workflow is shown and described as follows:</span></span>
  
![Flusso di lavoro di pertinenza](../media/44c67dd2-7a20-40a9-b0ed-784364845c77.gif)
  
- <span data-ttu-id="cd141-112">**Cicli di valutazione e verifica:**</span><span class="sxs-lookup"><span data-stu-id="cd141-112">**Cycles of assessment and tracking**:</span></span>
    
  - <span data-ttu-id="cd141-113">**Valutazione:** consente la valutazione anticipata in base a un campione casuale di file e utilizza questa valutazione per applicare le decisioni per determinare le prestazioni del processo di codifica predittivo.</span><span class="sxs-lookup"><span data-stu-id="cd141-113">**Assessment**: Enables early assessment based on a random sample of files and uses this assessment to apply decisions to determine the performance of the predictive coding process.</span></span> 
    
  - <span data-ttu-id="cd141-114">**Traccia:** calcolare e visualizzare i risultati provvisori della valutazione monitorando la validità statistica del processo.</span><span class="sxs-lookup"><span data-stu-id="cd141-114">**Track**: Calculate and display interim results of the assessment while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="cd141-115">**Cicli di formazione e tracciamento**</span><span class="sxs-lookup"><span data-stu-id="cd141-115">**Cycles of training and tracking**</span></span>
    
  - <span data-ttu-id="cd141-116">**Tag:** Advanced eDiscovery apprende i criteri di rilevanza specifici per ogni problema in base alla revisione iterativa dell'esperto e al tagging dei singoli file.</span><span class="sxs-lookup"><span data-stu-id="cd141-116">**Tag**: Advanced eDiscovery learns Relevance criteria specific to each issue based on the expert's iterative review and tagging of individual files.</span></span>
    
  - <span data-ttu-id="cd141-117">**Traccia:** calcolare e visualizzare i risultati provvisori della formazione sulla rilevanza monitorando la validità statistica del processo.</span><span class="sxs-lookup"><span data-stu-id="cd141-117">**Track**: Calculate and display interim results of the Relevance training while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="cd141-118">**Calcolo in** batch: i criteri di rilevanza accumulati e appresi vengono applicati all'intera raccolta di file e viene generato un punteggio di rilevanza per ogni file.</span><span class="sxs-lookup"><span data-stu-id="cd141-118">**Batch calculation**: The accumulated and learned Relevance criteria is applied to the entire file collection, and a Relevance score is generated for each file.</span></span>
    
- <span data-ttu-id="cd141-119">**Decidere**: i risultati dell'analisi applicata all'intero caso vengono visualizzati dopo il calcolo batch e vengono visualizzati i dati utilizzati per prendere decisioni di revisione dei documenti.</span><span class="sxs-lookup"><span data-stu-id="cd141-119">**Decide**: The results of the analysis applied to the entire case is displayed after Batch calculation, and data used to make document review decisions is displayed.</span></span>
    
- <span data-ttu-id="cd141-120">**Test:** i risultati possono essere testati per verificare la validità e l'efficacia dell'elaborazione di Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="cd141-120">**Test**: Results can be tested to verify the validity and effectiveness of the Advanced eDiscovery processing.</span></span>

- <span data-ttu-id="cd141-121">**Ricerca:** una volta completato il flusso di lavoro Pertinenza, è possibile utilizzare l'output, ad esempio il percentile di lettura di un documento per il problema, quando si esegue una query all'interno del set di revisioni.</span><span class="sxs-lookup"><span data-stu-id="cd141-121">**Search**: Once the Relevance workflow is complete, you can use the output such as read percentile of a document for your issue when you run a query within your review set.</span></span>
    
## <a name="guidelines-for-relevance-training-and-review"></a><span data-ttu-id="cd141-122">Linee guida per la formazione e la revisione della rilevanza</span><span class="sxs-lookup"><span data-stu-id="cd141-122">Guidelines for Relevance training and review</span></span>

<span data-ttu-id="cd141-123">Di seguito è riportata una panoramica delle linee guida per la formazione e la revisione della rilevanza:</span><span class="sxs-lookup"><span data-stu-id="cd141-123">Following is an overview of guidelines for Relevance training and review:</span></span>
  
- <span data-ttu-id="cd141-124">**Errori e incoerenze:** se durante il training vengono effettuati errori di tagging, tornare agli esempi di file precedenti per correggerli.</span><span class="sxs-lookup"><span data-stu-id="cd141-124">**Errors and inconsistencies**: If tagging errors are made during training, return to previous file samples to correct them.</span></span> <span data-ttu-id="cd141-125">Se sono presenti troppi errori da correggere o esiste una nuova prospettiva del caso o del problema, i criteri di pertinenza devono essere ridefiniti dall'amministratore e il training della rilevanza viene riavviato.</span><span class="sxs-lookup"><span data-stu-id="cd141-125">If there are too many errors to correct or there is a new perspective of the case or issue, the Relevance criteria should be redefined by the Administrator, and the Relevance training restarted.</span></span>
    
- <span data-ttu-id="cd141-126">**Tagging e formazione:**</span><span class="sxs-lookup"><span data-stu-id="cd141-126">**Tagging and training**:</span></span> 
    
  - <span data-ttu-id="cd141-127">I file devono essere contrassegnati solo in base al contenuto.</span><span class="sxs-lookup"><span data-stu-id="cd141-127">Files should be tagged based on content only.</span></span> <span data-ttu-id="cd141-128">Non considerare i metadati, ad esempio il responsabile, la data o il percorso del file.</span><span class="sxs-lookup"><span data-stu-id="cd141-128">Do not consider metadata, such as custodian, date, or file path.</span></span> 
    
  - <span data-ttu-id="cd141-129">Non considerare le indicazioni dell'intervallo di date nel testo durante l'aggiunta di tag ai file.</span><span class="sxs-lookup"><span data-stu-id="cd141-129">Do not consider date range indications in the text when tagging files.</span></span>
    
  - <span data-ttu-id="cd141-130">Non considerare le immagini grafiche incorporate durante il tagging dei file.</span><span class="sxs-lookup"><span data-stu-id="cd141-130">Do not consider embedded graphical images when tagging files.</span></span>
     
  - <span data-ttu-id="cd141-131">Il testo ignorato applicato alla rilevanza verrà rimosso nel contenuto del file visualizzato nella visualizzazione testo in Pertinenza.</span><span class="sxs-lookup"><span data-stu-id="cd141-131">Ignore text applied to Relevance will be removed in the displayed file content in the text view in Relevance.</span></span> <span data-ttu-id="cd141-132">Se i valori per Ignora testo sono stati definiti dopo l'inizio del training della rilevanza, il nuovo testo ignorato verrà applicato ai file di esempio creati dal punto in cui è stato definito.</span><span class="sxs-lookup"><span data-stu-id="cd141-132">If the values for Ignore text were defined after Relevance training already started, the new ignored text will be applied to sample files created from the point in which it was defined.</span></span> <span data-ttu-id="cd141-133">La funzionalità Ignora testo deve essere utilizzata con cautela, in quanto il suo utilizzo può ridurre le prestazioni dell'analisi dei file</span><span class="sxs-lookup"><span data-stu-id="cd141-133">The Ignore Text feature should be used cautiously, as its use may reduce the performance of file analysis</span></span>
    
  - <span data-ttu-id="cd141-134">Utilizzare **l'opzione Ignora tagging** solo se necessario.</span><span class="sxs-lookup"><span data-stu-id="cd141-134">Use the **Skip tagging** option only when necessary.</span></span> <span data-ttu-id="cd141-135">Advanced eDiscovery non si forma in base ai file ignorati.</span><span class="sxs-lookup"><span data-stu-id="cd141-135">Advanced eDiscovery does not train based on skipped files.</span></span> <span data-ttu-id="cd141-136">Nella valutazione, se è difficile stabilire se un file è rilevante, è meglio contrassegnare come rilevante (R) o Non rilevante (NR) quando possibile anziché selezionare **Ignora.**</span><span class="sxs-lookup"><span data-stu-id="cd141-136">In assessment, if it's hard to tell whether a file is relevant, it is better to tag as Relevant (R) or Not relevant (NR) whenever possible rather than selecting **Skip**.</span></span> <span data-ttu-id="cd141-137">Quando Advanced eDiscovery valuta la formazione, si può vedere quanto bene sono stati elaborati questi tipi di file.</span><span class="sxs-lookup"><span data-stu-id="cd141-137">When Advanced eDiscovery evaluates training, it can then be seen how well these types of files were processed.</span></span>
    
  - <span data-ttu-id="cd141-138">Anche i file con una quantità molto ridotta di testo estratto devono essere contrassegnati come R/NR, anziché come "Skip", quando possibile.</span><span class="sxs-lookup"><span data-stu-id="cd141-138">Even files with a very small amount of extracted text should be tagged in training as R/NR, rather than as "Skip", when possible.</span></span> 
    
  - <span data-ttu-id="cd141-139">Il tagging può influire sul classificatore, purché il file sia leggibile e possa essere contrassegnato come R/NR.</span><span class="sxs-lookup"><span data-stu-id="cd141-139">Tagging can impact the classifier as long as the file is readable and can be tagged as R/NR.</span></span>
    
  - <span data-ttu-id="cd141-140">Il numero di sequenza del file nell'elenco dei file di esempio visualizzato nella scheda **Tag** consente all'utente di tornare all'ordine di visualizzazione originale dei file.</span><span class="sxs-lookup"><span data-stu-id="cd141-140">The file sequence number on the displayed Sample files list on the **Tag** tab allows the user to return to the original displayed order of the files.</span></span> 
    
  - <span data-ttu-id="cd141-141">È possibile tornare a qualsiasi esempio e modificare il tagging dei file del set di valutazione e formazione.</span><span class="sxs-lookup"><span data-stu-id="cd141-141">You can go back to any sample and change the tagging of the assessment and training set files.</span></span> <span data-ttu-id="cd141-142">Le modifiche verranno applicate durante la creazione dell'esempio successivo.</span><span class="sxs-lookup"><span data-stu-id="cd141-142">The changes will be applied when creating the next sample.</span></span>
    
  - <span data-ttu-id="cd141-143">I file Excel analizzati in formato PDF devono essere considerati come i file di Excel nativi durante l'aggiunta di tag ai file.</span><span class="sxs-lookup"><span data-stu-id="cd141-143">Scanned Excel files in PDF format should be treated the same as native Excel files when tagging files.</span></span>
    
  - <span data-ttu-id="cd141-144">In caso di dubbi sul tagging per pertinenza di un file, rivolgersi a un esperto.</span><span class="sxs-lookup"><span data-stu-id="cd141-144">When in doubt regarding the Relevance tagging of a file, consult an expert.</span></span> <span data-ttu-id="cd141-145">Il tagging non corretto durante la formazione sulla rilevanza può causare una perdita di tempo più avanti nel processo e può avere un impatto negativo sulla qualità dei risultati complessivi.</span><span class="sxs-lookup"><span data-stu-id="cd141-145">Incorrect tagging during the Relevance training can lead to lost time later in the process and may also have a negative impact on the quality of the overall results.</span></span>
    
  - <span data-ttu-id="cd141-146">Le parole chiave definite negli elenchi di parole chiave verranno visualizzate in colori per consentire all'utente di identificare i file rilevanti durante l'aggiunta di tag.</span><span class="sxs-lookup"><span data-stu-id="cd141-146">Keywords that were defined in Keyword lists will be displayed in colors to help the user identify relevant files while tagging.</span></span>
    
- <span data-ttu-id="cd141-147">**Calcolo batch:** i file contrassegnati come R/NR dall'esperto riceveranno un punteggio pari a 0 o 100.</span><span class="sxs-lookup"><span data-stu-id="cd141-147">**Batch calculation**: Files that were tagged as R/NR by the expert will receive a score of either 0 or 100.</span></span> <span data-ttu-id="cd141-148">Questo vale per il tagging eseguito prima del calcolo batch.</span><span class="sxs-lookup"><span data-stu-id="cd141-148">This applies to tagging made before Batch calculation.</span></span> <span data-ttu-id="cd141-149">Se l'esperto ha commutato il problema su Inattivo dopo il calcolo del batch e ha continuato a contrassegnare questo problema, i nuovi punteggi contrassegnati non saranno 100/0, ma il punteggio originale.</span><span class="sxs-lookup"><span data-stu-id="cd141-149">If the expert switched the issue to Idle after Batch Calculation and continued tagging this issue, the newly tagged scores will not be 100/0 but rather the original score.</span></span>
    
- <span data-ttu-id="cd141-150">Problemi **e** modalità di campionamento: i problemi vengono in genere disattivati al termine del lavoro su di essi (la formazione sulla pertinenza viene stabilizzata e viene eseguito il calcolo batch), quando i problemi vengono annullati o quando un altro utente sta lavorando sui problemi.</span><span class="sxs-lookup"><span data-stu-id="cd141-150">**Issues and sampling mode**: Issues are usually turned Off when work on them is completed (Relevance training is stabilized and Batch calculation was performed), when the issues are canceled, or when another user is working on the issues.</span></span>
    
## <a name="steps-in-relevance-training"></a><span data-ttu-id="cd141-151">Passaggi della formazione sulla rilevanza</span><span class="sxs-lookup"><span data-stu-id="cd141-151">Steps in Relevance training</span></span>

<span data-ttu-id="cd141-152">Nella scheda **Traccia di \> pertinenza,** Advanced eDiscovery fornisce suggerimenti su come procedere con l'elaborazione, con i passaggi successivi seguenti.</span><span class="sxs-lookup"><span data-stu-id="cd141-152">In the **Relevance \> Track** tab, Advanced eDiscovery provides recommendations on how to proceed in the processing, with the following next steps.</span></span> <span data-ttu-id="cd141-153">Le implicazioni sono descritte di seguito quando ognuno dei passaggi seguenti è consigliato nel processo di formazione sulla rilevanza.</span><span class="sxs-lookup"><span data-stu-id="cd141-153">The implications are described below when each of the following steps is recommended in the Relevance training process.</span></span> 
  
- <span data-ttu-id="cd141-154">Tagging /Continua tagging: revisione dei file e tagging per pertinenza eseguiti da un esperto per ogni file e problema all'interno di un campione.</span><span class="sxs-lookup"><span data-stu-id="cd141-154">Tagging / Continue tagging: File review and Relevance tagging performed by an expert for each file and issue within a sample.</span></span>
    
  - <span data-ttu-id="cd141-155">Implicazione: un esempio esistente deve essere contrassegnato.</span><span class="sxs-lookup"><span data-stu-id="cd141-155">Implication: An existing sample needs to be tagged.</span></span>
    
- <span data-ttu-id="cd141-156">Valutazione/valutazione continua: consente la convalida anticipata della pertinenza del caso e una visualizzazione preliminare della pertinenza della popolazione di file importata per il caso corrente.</span><span class="sxs-lookup"><span data-stu-id="cd141-156">Assessment / Continue assessment: Enables early validation of case issue relevance and a preliminary view of the relevance of the file population imported for the current case.</span></span>
    
  - <span data-ttu-id="cd141-157">Implicazione: è necessaria o consigliata una valutazione maggiore.</span><span class="sxs-lookup"><span data-stu-id="cd141-157">Implication: More assessment is required or recommended.</span></span>
    
- <span data-ttu-id="cd141-158">Formazione e formazione continua: processo durante il quale Advanced eDiscovery apprende dall'esperto che contrassegna gli esempi di file e acquisisce la possibilità di identificare i criteri di pertinenza pertinenti a ogni problema nel contesto di ogni caso.</span><span class="sxs-lookup"><span data-stu-id="cd141-158">Training / Continue training: Process during which Advanced eDiscovery learns from the expert who is tagging the file samples and acquires the ability to identify Relevance criteria pertinent to each issue within the context of each case.</span></span>
    
  - <span data-ttu-id="cd141-159">Implication: The issue needs more training; L'esempio successivo deve essere creato e contrassegnato.</span><span class="sxs-lookup"><span data-stu-id="cd141-159">Implication: The issue needs more training; the next sample should be created and tagged.</span></span> 
    
- <span data-ttu-id="cd141-160">Calcolo batch: processo di pertinenza in cui Advanced eDiscovery acquisisce le conoscenze acquisite durante la fase di formazione e la applica all'intera popolazione di file.</span><span class="sxs-lookup"><span data-stu-id="cd141-160">Batch calculation: Relevance process in which Advanced eDiscovery takes the knowledge acquired during the training stage and applies it to the entire file population.</span></span> <span data-ttu-id="cd141-161">Tutti i file nel gruppo di file pertinente vengono valutati per pertinenza e assegnati a un punteggio di pertinenza.</span><span class="sxs-lookup"><span data-stu-id="cd141-161">All files in the pertinent file group are assessed for relevance and assigned a Relevance score.</span></span>
    
  - <span data-ttu-id="cd141-162">Implicazione: il problema si è stabilizzato ed è possibile eseguire il calcolo batch.</span><span class="sxs-lookup"><span data-stu-id="cd141-162">Implication: The issue has stabilized, and Batch calculation can be performed.</span></span>
    
- <span data-ttu-id="cd141-163">Catch-up: La rilevanza indica quando un esperto rivede e contrassegna un campione di file selezionati da un carico di file aggiuntivo durante uno scenario di caricamento in sequenza.</span><span class="sxs-lookup"><span data-stu-id="cd141-163">Catch-up: Relevance indicates when an expert reviews and tags a sample of files selected from an additional file load during a Rolling Loads scenario.</span></span>
    
  - <span data-ttu-id="cd141-164">Implicazione: è stato aggiunto un nuovo carico ed è necessario recuperare il carico per continuare a funzionare.</span><span class="sxs-lookup"><span data-stu-id="cd141-164">Implication: A new load has been added, and Catch-up is required to continue working.</span></span>
    
- <span data-ttu-id="cd141-165">Incoerenze dei tag: il processo identifica, tramite un algoritmo di Advanced eDiscovery, le incoerenze nel processo di tagging dei file che possono influire negativamente sull'analisi.</span><span class="sxs-lookup"><span data-stu-id="cd141-165">Tag inconsistencies: Process identifies, via an Advanced eDiscovery algorithm, inconsistencies in the file tagging process that may negatively impact the analysis.</span></span>
    
  - <span data-ttu-id="cd141-166">Implicazione: l'esempio successivo includerà i file che sono stati contrassegnati negli esempi precedenti e il tagging deve essere riecluso.</span><span class="sxs-lookup"><span data-stu-id="cd141-166">Implication: The next sample will include files that have been tagged in previous samples, and their tagging must be redone.</span></span>
    
- <span data-ttu-id="cd141-167">Classificatore di aggiornamento: consente all'utente di applicare modifiche di tagging o seeding.</span><span class="sxs-lookup"><span data-stu-id="cd141-167">Update classifier: Allows the user to apply tagging or seeding changes.</span></span>
    
  - <span data-ttu-id="cd141-168">Implicazione: le modifiche di tagging e seeding possono essere applicate senza dover eseguire manualmente un altro esempio di pertinenza.</span><span class="sxs-lookup"><span data-stu-id="cd141-168">Implication: Tagging and seeding changes can be applied without needing to manually run another Relevance sample.</span></span>
    
- <span data-ttu-id="cd141-169">In attesa: il processo di formazione sulla rilevanza è stato completato.</span><span class="sxs-lookup"><span data-stu-id="cd141-169">On hold: The Relevance training process is completed.</span></span>
    
  - <span data-ttu-id="cd141-170">Implicazione: a questo punto non è richiesto alcun corso di formazione sulla rilevanza.</span><span class="sxs-lookup"><span data-stu-id="cd141-170">Implication: No Relevance training is required at this point.</span></span>
    
<span data-ttu-id="cd141-171">Anche se Advanced eDiscovery guida l'utente attraverso il processo, con i passaggi successivi consigliati in diverse fasi, consente anche di spostarsi tra schede e pagine e di effettuare scelte per affrontare le situazioni che possono essere pertinenti al singolo caso, problema o processo di revisione dei documenti.</span><span class="sxs-lookup"><span data-stu-id="cd141-171">Although Advanced eDiscovery guides you through the process, with recommended Next steps at different stages, it also allows you to navigate between tabs and pages, and to make choices to address situations that may be pertinent to your individual case, issue, or document review process.</span></span> 
  
<span data-ttu-id="cd141-172">È possibile accettare o sostituire le scelte di elaborazione del passaggio successivo di Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="cd141-172">It is possible to accept or override Advanced eDiscovery Next step processing choices.</span></span> <span data-ttu-id="cd141-173">Se si desidera eseguire un passaggio diverso dal  passaggio successivo consigliato, fare clic sul passaggio  successivo elencato nella visualizzazione del problema espanso nella finestra di dialogo, fare clic sul pulsante Modifica accanto al passaggio successivo e selezionare un'altra opzione passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="cd141-173">If you want to perform a step other than the recommended Next step, click the **Next step** listed in the expanded issue display in the dialog, click the **Modify** button next to the Next step, and select another Next step option.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="cd141-174">Alcune opzioni potrebbero rimanere disabilitate dopo lo sblocco perché non sono supportate per l'uso a quel punto del processo.</span><span class="sxs-lookup"><span data-stu-id="cd141-174">Some options may remain disabled after unlocking as they are not supported for use at that point in the process.</span></span> 
  
## <a name="more-information"></a><span data-ttu-id="cd141-175">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="cd141-175">More information</span></span>

[<span data-ttu-id="cd141-176">Informazioni sulla valutazione della rilevanza</span><span class="sxs-lookup"><span data-stu-id="cd141-176">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="cd141-177">Tagging e valutazione</span><span class="sxs-lookup"><span data-stu-id="cd141-177">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="cd141-178">Formazione su tagging e pertinenza</span><span class="sxs-lookup"><span data-stu-id="cd141-178">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="cd141-179">Monitoraggio dell'analisi della rilevanza</span><span class="sxs-lookup"><span data-stu-id="cd141-179">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="cd141-180">Decidere in base ai risultati</span><span class="sxs-lookup"><span data-stu-id="cd141-180">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="cd141-181">Test dell'analisi di rilevanza</span><span class="sxs-lookup"><span data-stu-id="cd141-181">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

[<span data-ttu-id="cd141-182">Eseguire query sui dati in un insieme da rivedere</span><span class="sxs-lookup"><span data-stu-id="cd141-182">Query the data in a review set</span></span>](review-set-search.md)
