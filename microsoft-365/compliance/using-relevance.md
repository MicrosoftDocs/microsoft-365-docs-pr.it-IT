---
title: Utilizzare il modulo pertinenza per analizzare i dati in Advanced eDiscovery
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
description: Informazioni sul modo in cui il modulo pertinenza analizza i dati in evidenza con una descrizione del flusso di lavoro di pertinenza e dei passaggi di formazione in Advanced eDiscovery.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 4babb0aa7693bc1107cc7594da967bca2d307228
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034468"
---
# <a name="use-the-relevance-module-to-analyze-data-in-advanced-ediscovery"></a><span data-ttu-id="21e21-103">Utilizzare il modulo pertinenza per analizzare i dati in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="21e21-103">Use the Relevance module to analyze data in Advanced eDiscovery</span></span>

<span data-ttu-id="21e21-104">In Advanced eDiscovery, il modulo pertinenza include la formazione sulla pertinenza e la revisione dei file correlati a un caso.</span><span class="sxs-lookup"><span data-stu-id="21e21-104">In Advanced eDiscovery, the Relevance module includes the Relevance training and review of files related to a case.</span></span> <span data-ttu-id="21e21-105">Per utilizzare il flusso di lavoro pertinenza, andare a Manage Review set all'interno di un set di revisione e fare clic su Mostra pertinenza.</span><span class="sxs-lookup"><span data-stu-id="21e21-105">In order to use the Relevance workflow, go to Manage review set within a review set and click on Show Relevance.</span></span> <span data-ttu-id="21e21-106">Prima di avviare il flusso di lavoro, è necessario eseguire un paio di passaggi:</span><span class="sxs-lookup"><span data-stu-id="21e21-106">There are a couple of steps you need to complete before you can start the workflow:</span></span>

- <span data-ttu-id="21e21-107">Processo: ogni set di carico aggiunto al set di revisione verrà visualizzato come un "contenitore" qui.</span><span class="sxs-lookup"><span data-stu-id="21e21-107">Process: each load set added to the review set will show up as a "container" here.</span></span> <span data-ttu-id="21e21-108">È necessario elaborare questi documenti prima di poterli aggiungere al modulo pertinenza. Questo è anche il luogo in cui è possibile contrassegnarli come Seed o come precontrassegnati per un problema specifico.</span><span class="sxs-lookup"><span data-stu-id="21e21-108">You need to process these documents before you can add them to Relevance module; this is also where you can mark them as seed or pre-tagged for a specific issue.</span></span>

- <span data-ttu-id="21e21-109">Aggiungi a pertinenza: in \> carichi di pertinenza, è possibile aggiungere documenti elaborati alla pertinenza per renderli disponibili per la formazione.</span><span class="sxs-lookup"><span data-stu-id="21e21-109">Add to Relevance: Under Relevance \> Loads, you can add documents that have been processed to Relevance to make them available for training.</span></span>

<span data-ttu-id="21e21-110">Il flusso di lavoro di pertinenza è illustrato e descritto nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="21e21-110">The Relevance workflow is shown and described as follows:</span></span>
  
![Flusso di lavoro di pertinenza](../media/44c67dd2-7a20-40a9-b0ed-784364845c77.gif)
  
- <span data-ttu-id="21e21-112">**Cicli di valutazione e tracciabilità**:</span><span class="sxs-lookup"><span data-stu-id="21e21-112">**Cycles of assessment and tracking**:</span></span>
    
  - <span data-ttu-id="21e21-113">**Valutazione**: consente la valutazione precoce basata su un campione casuale di file e utilizza questa valutazione per applicare le decisioni per determinare le prestazioni del processo di codifica predittiva.</span><span class="sxs-lookup"><span data-stu-id="21e21-113">**Assessment**: Enables early assessment based on a random sample of files and uses this assessment to apply decisions to determine the performance of the predictive coding process.</span></span> 
    
  - <span data-ttu-id="21e21-114">**Track**: calcolare e visualizzare i risultati intermedi della valutazione monitorando la validità statistica del processo.</span><span class="sxs-lookup"><span data-stu-id="21e21-114">**Track**: Calculate and display interim results of the assessment while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="21e21-115">**Cicli di training e Tracking**</span><span class="sxs-lookup"><span data-stu-id="21e21-115">**Cycles of training and tracking**</span></span>
    
  - <span data-ttu-id="21e21-116">**Tag**: Advanced eDiscovery apprende criteri di pertinenza specifici per ogni problema in base alla revisione iterativa dell'esperto e al tagging di singoli file.</span><span class="sxs-lookup"><span data-stu-id="21e21-116">**Tag**: Advanced eDiscovery learns Relevance criteria specific to each issue based on the expert's iterative review and tagging of individual files.</span></span>
    
  - <span data-ttu-id="21e21-117">**Track**: calcola e Visualizza i risultati intermedi della formazione relativa alla pertinenza monitorando la validità statistica del processo.</span><span class="sxs-lookup"><span data-stu-id="21e21-117">**Track**: Calculate and display interim results of the Relevance training while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="21e21-118">**Calcolo batch**: i criteri di pertinenza accumulati e appresi vengono applicati all'intera raccolta file e viene generato un punteggio di pertinenza per ogni file.</span><span class="sxs-lookup"><span data-stu-id="21e21-118">**Batch calculation**: The accumulated and learned Relevance criteria is applied to the entire file collection, and a Relevance score is generated for each file.</span></span>
    
- <span data-ttu-id="21e21-119">**Decidere**: i risultati dell'analisi applicata all'intero caso vengono visualizzati dopo il calcolo del batch e vengono visualizzati i dati utilizzati per definire le decisioni relative alla revisione dei documenti.</span><span class="sxs-lookup"><span data-stu-id="21e21-119">**Decide**: The results of the analysis applied to the entire case is displayed after Batch calculation, and data used to make document review decisions is displayed.</span></span>
    
- <span data-ttu-id="21e21-120">**Test**: i risultati possono essere testati per verificare la validità e l'efficacia dell'elaborazione avanzata di eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="21e21-120">**Test**: Results can be tested to verify the validity and effectiveness of the Advanced eDiscovery processing.</span></span>

- <span data-ttu-id="21e21-121">**Ricerca**: dopo aver completato il flusso di lavoro della pertinenza, è possibile utilizzare l'output, ad esempio leggere il percentile di un documento per il problema, quando si esegue una query all'interno del set di revisione.</span><span class="sxs-lookup"><span data-stu-id="21e21-121">**Search**: Once the Relevance workflow is complete, you can use the output such as read percentile of a document for your issue when you run a query within your review set.</span></span>
    
## <a name="guidelines-for-relevance-training-and-review"></a><span data-ttu-id="21e21-122">Linee guida per la formazione e la revisione della pertinenza</span><span class="sxs-lookup"><span data-stu-id="21e21-122">Guidelines for Relevance training and review</span></span>

<span data-ttu-id="21e21-123">Di seguito è riportata una panoramica delle linee guida per la formazione e la revisione della pertinenza:</span><span class="sxs-lookup"><span data-stu-id="21e21-123">Following is an overview of guidelines for Relevance training and review:</span></span>
  
- <span data-ttu-id="21e21-124">**Errori e incoerenze**: se durante l'allenamento vengono eseguiti gli errori di tagging, tornare agli esempi di file precedenti per correggerli.</span><span class="sxs-lookup"><span data-stu-id="21e21-124">**Errors and inconsistencies**: If tagging errors are made during training, return to previous file samples to correct them.</span></span> <span data-ttu-id="21e21-125">Se si verifica un numero eccessivo di errori da correggere oppure è presente una nuova prospettiva del caso o del problema, i criteri di pertinenza devono essere ridefiniti dall'amministratore e riavviato il Training relativo alla pertinenza.</span><span class="sxs-lookup"><span data-stu-id="21e21-125">If there are too many errors to correct or there is a new perspective of the case or issue, the Relevance criteria should be redefined by the Administrator, and the Relevance training restarted.</span></span>
    
- <span data-ttu-id="21e21-126">**Tagging e formazione**:</span><span class="sxs-lookup"><span data-stu-id="21e21-126">**Tagging and training**:</span></span> 
    
  - <span data-ttu-id="21e21-127">I file devono essere contrassegnati in base solo al contenuto.</span><span class="sxs-lookup"><span data-stu-id="21e21-127">Files should be tagged based on content only.</span></span> <span data-ttu-id="21e21-128">Non considerare i metadati, ad esempio il custode, la data o il percorso del file.</span><span class="sxs-lookup"><span data-stu-id="21e21-128">Do not consider metadata, such as custodian, date, or file path.</span></span> 
    
  - <span data-ttu-id="21e21-129">Non prendere in considerazione le indicazioni dell'intervallo di date nel testo durante il tagging dei file.</span><span class="sxs-lookup"><span data-stu-id="21e21-129">Do not consider date range indications in the text when tagging files.</span></span>
    
  - <span data-ttu-id="21e21-130">Non considerare le immagini grafiche incorporate durante il tagging dei file.</span><span class="sxs-lookup"><span data-stu-id="21e21-130">Do not consider embedded graphical images when tagging files.</span></span>
     
  - <span data-ttu-id="21e21-131">Ignorare il testo applicato alla pertinenza verrà rimosso nel contenuto del file visualizzato nella visualizzazione di testo in pertinenza.</span><span class="sxs-lookup"><span data-stu-id="21e21-131">Ignore text applied to Relevance will be removed in the displayed file content in the text view in Relevance.</span></span> <span data-ttu-id="21e21-132">Se i valori per il testo Ignora sono stati definiti dopo la formazione di pertinenza già avviata, il nuovo testo ignorato verrà applicato ai file di esempio creati dal punto in cui è stata definita.</span><span class="sxs-lookup"><span data-stu-id="21e21-132">If the values for Ignore text were defined after Relevance training already started, the new ignored text will be applied to sample files created from the point in which it was defined.</span></span> <span data-ttu-id="21e21-133">La funzionalità Ignora testo deve essere utilizzata con cautela, in quanto il relativo utilizzo può ridurre le prestazioni dell'analisi dei file</span><span class="sxs-lookup"><span data-stu-id="21e21-133">The Ignore Text feature should be used cautiously, as its use may reduce the performance of file analysis</span></span>
    
  - <span data-ttu-id="21e21-134">Utilizzare l'opzione **Ignora Tag** solo se necessario.</span><span class="sxs-lookup"><span data-stu-id="21e21-134">Use the **Skip tagging** option only when necessary.</span></span> <span data-ttu-id="21e21-135">Advanced eDiscovery non si allena in base ai file ignorati.</span><span class="sxs-lookup"><span data-stu-id="21e21-135">Advanced eDiscovery does not train based on skipped files.</span></span> <span data-ttu-id="21e21-136">In valutazione, se è difficile stabilire se un file è pertinente, è consigliabile contrassegnarlo come pertinente (R) o non pertinente (NR) quando possibile anziché selezionando **Ignora**.</span><span class="sxs-lookup"><span data-stu-id="21e21-136">In assessment, if it's hard to tell whether a file is relevant, it is better to tag as Relevant (R) or Not relevant (NR) whenever possible rather than selecting **Skip**.</span></span> <span data-ttu-id="21e21-137">Quando Advanced eDiscovery valuta la formazione, può essere visto bene come sono stati elaborati questi tipi di file.</span><span class="sxs-lookup"><span data-stu-id="21e21-137">When Advanced eDiscovery evaluates training, it can then be seen how well these types of files were processed.</span></span>
    
  - <span data-ttu-id="21e21-138">Anche i file con una quantità minima di testo estratto devono essere contrassegnati in formazione come R/NR, anziché come "Skip", quando possibile.</span><span class="sxs-lookup"><span data-stu-id="21e21-138">Even files with a very small amount of extracted text should be tagged in training as R/NR, rather than as "Skip", when possible.</span></span> 
    
  - <span data-ttu-id="21e21-139">Il tagging può influire sul classificatore fino a quando il file è leggibile e può essere contrassegnato come R/NR.</span><span class="sxs-lookup"><span data-stu-id="21e21-139">Tagging can impact the classifier as long as the file is readable and can be tagged as R/NR.</span></span>
    
  - <span data-ttu-id="21e21-140">Il numero di sequenza dei file nell'elenco di file di esempio visualizzato nella scheda **tag** consente all'utente di tornare all'ordine di file originale visualizzato.</span><span class="sxs-lookup"><span data-stu-id="21e21-140">The file sequence number on the displayed Sample files list on the **Tag** tab allows the user to return to the original displayed order of the files.</span></span> 
    
  - <span data-ttu-id="21e21-141">È possibile tornare a qualsiasi campione e modificare il tagging dei file di set di valutazione e formazione.</span><span class="sxs-lookup"><span data-stu-id="21e21-141">You can go back to any sample and change the tagging of the assessment and training set files.</span></span> <span data-ttu-id="21e21-142">Le modifiche verranno applicate quando si crea l'esempio successivo.</span><span class="sxs-lookup"><span data-stu-id="21e21-142">The changes will be applied when creating the next sample.</span></span>
    
  - <span data-ttu-id="21e21-143">I file di Excel analizzati in formato PDF devono essere considerati come file di Excel nativo durante il tagging dei file.</span><span class="sxs-lookup"><span data-stu-id="21e21-143">Scanned Excel files in PDF format should be treated the same as native Excel files when tagging files.</span></span>
    
  - <span data-ttu-id="21e21-144">In caso di dubbi sul tagging della pertinenza di un file, consultare un esperto.</span><span class="sxs-lookup"><span data-stu-id="21e21-144">When in doubt regarding the Relevance tagging of a file, consult an expert.</span></span> <span data-ttu-id="21e21-145">L'utilizzo di tag non corretti durante la formazione di pertinenza può comportare una perdita di tempo nel corso del processo e potrebbe anche avere un impatto negativo sulla qualità dei risultati complessivi.</span><span class="sxs-lookup"><span data-stu-id="21e21-145">Incorrect tagging during the Relevance training can lead to lost time later in the process and may also have a negative impact on the quality of the overall results.</span></span>
    
  - <span data-ttu-id="21e21-146">Le parole chiave definite negli elenchi di parole chiave verranno visualizzate nei colori per consentire all'utente di identificare i file rilevanti durante il tagging.</span><span class="sxs-lookup"><span data-stu-id="21e21-146">Keywords that were defined in Keyword lists will be displayed in colors to help the user identify relevant files while tagging.</span></span>
    
- <span data-ttu-id="21e21-147">**Calcolo batch**: i file contrassegnati come R/Nr dall'esperto riceveranno un punteggio pari a 0 o 100.</span><span class="sxs-lookup"><span data-stu-id="21e21-147">**Batch calculation**: Files that were tagged as R/NR by the expert will receive a score of either 0 or 100.</span></span> <span data-ttu-id="21e21-148">Questo si applica al tagging eseguito prima del calcolo del batch.</span><span class="sxs-lookup"><span data-stu-id="21e21-148">This applies to tagging made before Batch calculation.</span></span> <span data-ttu-id="21e21-149">Se l'esperto ha passato il problema a inattività dopo il calcolo del batch e ha continuato a contrassegnare questo problema, i punteggi appena contrassegnati non saranno 100/0 ma piuttosto la partitura originale.</span><span class="sxs-lookup"><span data-stu-id="21e21-149">If the expert switched the issue to Idle after Batch Calculation and continued tagging this issue, the newly tagged scores will not be 100/0 but rather the original score.</span></span>
    
- <span data-ttu-id="21e21-150">**Problemi e modalità di campionamento**: i problemi vengono in genere disattivati durante il completamento del lavoro (la formazione di pertinenza è stabilizzata e il calcolo in batch è stato eseguito), quando i problemi vengono annullati o quando un altro utente sta lavorando sui problemi.</span><span class="sxs-lookup"><span data-stu-id="21e21-150">**Issues and sampling mode**: Issues are usually turned Off when work on them is completed (Relevance training is stabilized and Batch calculation was performed), when the issues are canceled, or when another user is working on the issues.</span></span>
    
## <a name="steps-in-relevance-training"></a><span data-ttu-id="21e21-151">Passaggi per la formazione sulla pertinenza</span><span class="sxs-lookup"><span data-stu-id="21e21-151">Steps in Relevance training</span></span>

<span data-ttu-id="21e21-152">Nella scheda \*\* \> rilevamento di pertinenza\*\* Advanced eDiscovery fornisce consigli su come procedere nell'elaborazione, con i passaggi successivi seguenti.</span><span class="sxs-lookup"><span data-stu-id="21e21-152">In the **Relevance \> Track** tab, Advanced eDiscovery provides recommendations on how to proceed in the processing, with the following next steps.</span></span> <span data-ttu-id="21e21-153">Le implicazioni sono descritte di seguito quando si consiglia di eseguire ciascuna delle operazioni seguenti nel processo di formazione per pertinenza.</span><span class="sxs-lookup"><span data-stu-id="21e21-153">The implications are described below when each of the following steps is recommended in the Relevance training process.</span></span> 
  
- <span data-ttu-id="21e21-154">Tagging/continua tagging: revisione dei file e tagging della pertinenza eseguito da un esperto per ogni file e problema all'interno di un esempio.</span><span class="sxs-lookup"><span data-stu-id="21e21-154">Tagging / Continue tagging: File review and Relevance tagging performed by an expert for each file and issue within a sample.</span></span>
    
  - <span data-ttu-id="21e21-155">Implicazione: è necessario contrassegnare un esempio esistente.</span><span class="sxs-lookup"><span data-stu-id="21e21-155">Implication: An existing sample needs to be tagged.</span></span>
    
- <span data-ttu-id="21e21-156">Assessment/continue assessment: consente la convalida precoce della pertinenza del problema del caso e una visualizzazione preliminare della pertinenza del popolamento dei file importato per il caso corrente.</span><span class="sxs-lookup"><span data-stu-id="21e21-156">Assessment / Continue assessment: Enables early validation of case issue relevance and a preliminary view of the relevance of the file population imported for the current case.</span></span>
    
  - <span data-ttu-id="21e21-157">Implicazioni: è richiesta o consigliata una maggiore valutazione.</span><span class="sxs-lookup"><span data-stu-id="21e21-157">Implication: More assessment is required or recommended.</span></span>
    
- <span data-ttu-id="21e21-158">Training/continue Training: processo durante il quale Advanced eDiscovery apprende dall'esperto che è in grado di contrassegnare gli esempi di file e acquisisce la capacità di identificare i criteri di pertinenza rilevanti per ogni problema nel contesto di ogni caso.</span><span class="sxs-lookup"><span data-stu-id="21e21-158">Training / Continue training: Process during which Advanced eDiscovery learns from the expert who is tagging the file samples and acquires the ability to identify Relevance criteria pertinent to each issue within the context of each case.</span></span>
    
  - <span data-ttu-id="21e21-159">Implicazione: il problema richiede una formazione maggiore; è necessario creare e contrassegnare l'esempio successivo.</span><span class="sxs-lookup"><span data-stu-id="21e21-159">Implication: The issue needs more training; the next sample should be created and tagged.</span></span> 
    
- <span data-ttu-id="21e21-160">Calcolo batch: processo di pertinenza in cui Advanced eDiscovery acquisisce le conoscenze acquisite durante la fase di formazione e lo applica all'intera popolazione dei file.</span><span class="sxs-lookup"><span data-stu-id="21e21-160">Batch calculation: Relevance process in which Advanced eDiscovery takes the knowledge acquired during the training stage and applies it to the entire file population.</span></span> <span data-ttu-id="21e21-161">Tutti i file del gruppo di file pertinente sono valutati per pertinenza e assegnato un punteggio di pertinenza.</span><span class="sxs-lookup"><span data-stu-id="21e21-161">All files in the pertinent file group are assessed for relevance and assigned a Relevance score.</span></span>
    
  - <span data-ttu-id="21e21-162">Implicazione: il problema si è stabilizzato e il calcolo in batch può essere eseguito.</span><span class="sxs-lookup"><span data-stu-id="21e21-162">Implication: The issue has stabilized, and Batch calculation can be performed.</span></span>
    
- <span data-ttu-id="21e21-163">Catch-up: pertinenza indica quando un esperto esamina e contrassegna un campione di file selezionati da un ulteriore caricamento di file durante uno scenario di carichi di rotolamento.</span><span class="sxs-lookup"><span data-stu-id="21e21-163">Catch-up: Relevance indicates when an expert reviews and tags a sample of files selected from an additional file load during a Rolling Loads scenario.</span></span>
    
  - <span data-ttu-id="21e21-164">Implicazione: è stato aggiunto un nuovo carico e il recupero è necessario per continuare a funzionare.</span><span class="sxs-lookup"><span data-stu-id="21e21-164">Implication: A new load has been added, and Catch-up is required to continue working.</span></span>
    
- <span data-ttu-id="21e21-165">Incoerenze dei tag: Process identifica, tramite un algoritmo avanzato di eDiscovery, incoerenze nel processo di tagging dei file che potrebbe influire negativamente sull'analisi.</span><span class="sxs-lookup"><span data-stu-id="21e21-165">Tag inconsistencies: Process identifies, via an Advanced eDiscovery algorithm, inconsistencies in the file tagging process that may negatively impact the analysis.</span></span>
    
  - <span data-ttu-id="21e21-166">Implicazioni: nell'esempio seguente vengono inclusi i file contrassegnati in esempi precedenti e il loro tagging deve essere rifatto.</span><span class="sxs-lookup"><span data-stu-id="21e21-166">Implication: The next sample will include files that have been tagged in previous samples, and their tagging must be redone.</span></span>
    
- <span data-ttu-id="21e21-167">Aggiorna classificatore: consente all'utente di applicare le modifiche di tagging o seeding.</span><span class="sxs-lookup"><span data-stu-id="21e21-167">Update classifier: Allows the user to apply tagging or seeding changes.</span></span>
    
  - <span data-ttu-id="21e21-168">Implicazioni: è possibile applicare le modifiche di tagging e seeding senza dover eseguire manualmente un altro esempio di pertinenza.</span><span class="sxs-lookup"><span data-stu-id="21e21-168">Implication: Tagging and seeding changes can be applied without needing to manually run another Relevance sample.</span></span>
    
- <span data-ttu-id="21e21-169">In attesa: il processo di formazione sulla pertinenza è stato completato.</span><span class="sxs-lookup"><span data-stu-id="21e21-169">On hold: The Relevance training process is completed.</span></span>
    
  - <span data-ttu-id="21e21-170">Implicazione: non è necessaria alcuna formazione di pertinenza a questo punto.</span><span class="sxs-lookup"><span data-stu-id="21e21-170">Implication: No Relevance training is required at this point.</span></span>
    
<span data-ttu-id="21e21-171">Anche se Advanced eDiscovery guida l'utente attraverso il processo, con i passaggi successivi consigliati nelle diverse fasi, consente anche di spostarsi tra le schede e le pagine e di fare scelte per risolvere le situazioni che possono essere pertinenti per il processo individuale, di problema o di revisione dei documenti.</span><span class="sxs-lookup"><span data-stu-id="21e21-171">Although Advanced eDiscovery guides you through the process, with recommended Next steps at different stages, it also allows you to navigate between tabs and pages, and to make choices to address situations that may be pertinent to your individual case, issue, or document review process.</span></span> 
  
<span data-ttu-id="21e21-172">È possibile accettare o sostituire le scelte avanzate di elaborazione dei passaggi successivi di eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="21e21-172">It is possible to accept or override Advanced eDiscovery Next step processing choices.</span></span> <span data-ttu-id="21e21-173">Se si desidera eseguire una procedura diversa da quella consigliata, fare clic sul **passaggio successivo** elencato nella visualizzazione del problema espanso nella finestra di dialogo, fare clic sul pulsante **modifica** accanto al passaggio successivo e selezionare un'altra opzione per il passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="21e21-173">If you want to perform a step other than the recommended Next step, click the **Next step** listed in the expanded issue display in the dialog, click the **Modify** button next to the Next step, and select another Next step option.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="21e21-174">Alcune opzioni potrebbero rimanere disabilitate dopo lo sblocco, in quanto non sono supportate per l'utilizzo in quel momento del processo.</span><span class="sxs-lookup"><span data-stu-id="21e21-174">Some options may remain disabled after unlocking as they are not supported for use at that point in the process.</span></span> 
  
## <a name="more-information"></a><span data-ttu-id="21e21-175">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="21e21-175">More information</span></span>

[<span data-ttu-id="21e21-176">Informazioni sulla valutazione in rilevanza</span><span class="sxs-lookup"><span data-stu-id="21e21-176">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="21e21-177">Tagging e valutazione</span><span class="sxs-lookup"><span data-stu-id="21e21-177">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="21e21-178">Formazione di tagging e pertinenza</span><span class="sxs-lookup"><span data-stu-id="21e21-178">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="21e21-179">Verifica dell'analisi della pertinenza</span><span class="sxs-lookup"><span data-stu-id="21e21-179">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="21e21-180">Decidere in base ai risultati</span><span class="sxs-lookup"><span data-stu-id="21e21-180">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="21e21-181">Verifica dell'analisi della pertinenza</span><span class="sxs-lookup"><span data-stu-id="21e21-181">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

[<span data-ttu-id="21e21-182">Eseguire query sui dati in un insieme da rivedere</span><span class="sxs-lookup"><span data-stu-id="21e21-182">Query the data in a review set</span></span>](review-set-search.md)
