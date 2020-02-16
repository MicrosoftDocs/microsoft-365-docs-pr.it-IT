---
title: Utilizzare il modulo pertinenza per analizzare i dati in evidenza
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
description: ''
ms.openlocfilehash: 0b6c42f594ef10c868051d81b0a7ea4b7ff84e00
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42080613"
---
# <a name="use-the-relevance-module-to-analyze-data-in-evidence"></a><span data-ttu-id="8bc2a-102">Utilizzare il modulo pertinenza per analizzare i dati in evidenza</span><span class="sxs-lookup"><span data-stu-id="8bc2a-102">Use the Relevance module to analyze data in evidence</span></span>

<span data-ttu-id="8bc2a-103">In indagini sui dati (Preview), il modulo pertinenza include la formazione sulla pertinenza e la revisione dei file relativi a un'indagine.</span><span class="sxs-lookup"><span data-stu-id="8bc2a-103">In Data Investigations (Preview), the Relevance module includes the Relevance training and review of files related to an investigation.</span></span> <span data-ttu-id="8bc2a-104">Il flusso di lavoro di pertinenza è illustrato e descritto nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="8bc2a-104">The Relevance workflow is shown and described as follows:</span></span>
  
![Flusso di lavoro di pertinenza](../media/44c67dd2-7a20-40a9-b0ed-784364845c77.gif)
  
- <span data-ttu-id="8bc2a-106">**Cicli di valutazione e tracciabilità**:</span><span class="sxs-lookup"><span data-stu-id="8bc2a-106">**Cycles of assessment and tracking**:</span></span>
    
  - <span data-ttu-id="8bc2a-107">**Valutazione**: consente la valutazione precoce basata su un campione casuale di file e utilizza questa valutazione per applicare le decisioni per determinare le prestazioni del processo di codifica predittiva.</span><span class="sxs-lookup"><span data-stu-id="8bc2a-107">**Assessment**: Enables early assessment based on a random sample of files and uses this assessment to apply decisions to determine the performance of the predictive coding process.</span></span> 
    
  - <span data-ttu-id="8bc2a-108">**Track**: calcolare e visualizzare i risultati intermedi della valutazione monitorando la validità statistica del processo.</span><span class="sxs-lookup"><span data-stu-id="8bc2a-108">**Track**: Calculate and display interim results of the assessment while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="8bc2a-109">**Cicli di training e Tracking**</span><span class="sxs-lookup"><span data-stu-id="8bc2a-109">**Cycles of training and tracking**</span></span>
    
  - <span data-ttu-id="8bc2a-110">**Tag**: indagini sui dati (Preview) vengono fornite informazioni sui criteri di pertinenza specifici per ogni problema in base alla revisione iterativa dell'esperto e al tagging di singoli file.</span><span class="sxs-lookup"><span data-stu-id="8bc2a-110">**Tag**: Data Investigations (Preview) learns Relevance criteria specific to each issue based on the expert's iterative review and tagging of individual files.</span></span>
    
  - <span data-ttu-id="8bc2a-111">**Track**: calcola e Visualizza i risultati intermedi della formazione relativa alla pertinenza monitorando la validità statistica del processo.</span><span class="sxs-lookup"><span data-stu-id="8bc2a-111">**Track**: Calculate and display interim results of the Relevance training while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="8bc2a-112">**Calcolo batch**: i criteri di pertinenza accumulati e appresi vengono applicati all'intera raccolta file e viene generato un punteggio di pertinenza per ogni file.</span><span class="sxs-lookup"><span data-stu-id="8bc2a-112">**Batch calculation**: The accumulated and learned Relevance criteria is applied to the entire file collection, and a Relevance score is generated for each file.</span></span>
    
- <span data-ttu-id="8bc2a-113">**Decidere**: i risultati dell'analisi applicata all'intero caso vengono visualizzati dopo il calcolo del batch e vengono visualizzati i dati utilizzati per definire le decisioni relative alla revisione dei documenti.</span><span class="sxs-lookup"><span data-stu-id="8bc2a-113">**Decide**: The results of the analysis applied to the entire case is displayed after Batch calculation, and data used to make document review decisions is displayed.</span></span>
    
- <span data-ttu-id="8bc2a-114">**Test**: i risultati possono essere testati per verificare la validità e l'efficacia dell'elaborazione delle indagini sui dati (Preview).</span><span class="sxs-lookup"><span data-stu-id="8bc2a-114">**Test**: Results can be tested to verify the validity and effectiveness of the Data Investigations (Preview) processing.</span></span>

- <span data-ttu-id="8bc2a-115">**Ricerca**: dopo aver completato il flusso di lavoro della pertinenza, è possibile utilizzare l'output, ad esempio il percentile di un documento, per il problema, quando si esegue una query all'interno del working set.</span><span class="sxs-lookup"><span data-stu-id="8bc2a-115">**Search**: Once the Relevance workflow is complete, you can use the output such as read percentile of a document for your issue when you run a query within your working set.</span></span>
    
## <a name="guidelines-for-relevance-training-and-review"></a><span data-ttu-id="8bc2a-116">Linee guida per la formazione e la revisione della pertinenza</span><span class="sxs-lookup"><span data-stu-id="8bc2a-116">Guidelines for Relevance training and review</span></span>

<span data-ttu-id="8bc2a-117">Di seguito è riportata una panoramica delle linee guida per la formazione e la revisione della pertinenza:</span><span class="sxs-lookup"><span data-stu-id="8bc2a-117">Following is an overview of guidelines for Relevance training and review:</span></span>
  
- <span data-ttu-id="8bc2a-118">**Errori e incoerenze**: se durante l'allenamento vengono eseguiti gli errori di tagging, tornare agli esempi di file precedenti per correggerli.</span><span class="sxs-lookup"><span data-stu-id="8bc2a-118">**Errors and inconsistencies**: If tagging errors are made during training, return to previous file samples to correct them.</span></span> <span data-ttu-id="8bc2a-119">Se si verifica un numero eccessivo di errori da correggere oppure è presente una nuova prospettiva del caso o del problema, i criteri di pertinenza devono essere ridefiniti dall'amministratore e riavviato il Training relativo alla pertinenza.</span><span class="sxs-lookup"><span data-stu-id="8bc2a-119">If there are too many errors to correct or there is a new perspective of the case or issue, the Relevance criteria should be redefined by the Administrator, and the Relevance training restarted.</span></span>
    
- <span data-ttu-id="8bc2a-120">**Tagging e formazione**:</span><span class="sxs-lookup"><span data-stu-id="8bc2a-120">**Tagging and training**:</span></span> 
    
  - <span data-ttu-id="8bc2a-121">I file devono essere contrassegnati in base solo al contenuto.</span><span class="sxs-lookup"><span data-stu-id="8bc2a-121">Files should be tagged based on content only.</span></span> <span data-ttu-id="8bc2a-122">Non considerare i metadati, ad esempio il custode, la data o il percorso del file.</span><span class="sxs-lookup"><span data-stu-id="8bc2a-122">Do not consider metadata, such as custodian, date, or file path.</span></span> 
    
  - <span data-ttu-id="8bc2a-123">Non prendere in considerazione le indicazioni dell'intervallo di date nel testo durante il tagging dei file.</span><span class="sxs-lookup"><span data-stu-id="8bc2a-123">Do not consider date range indications in the text when tagging files.</span></span>
    
  - <span data-ttu-id="8bc2a-124">Non considerare le immagini grafiche incorporate durante il tagging dei file.</span><span class="sxs-lookup"><span data-stu-id="8bc2a-124">Do not consider embedded graphical images when tagging files.</span></span>
     
  - <span data-ttu-id="8bc2a-125">Ignorare il testo applicato alla pertinenza verrà rimosso nel contenuto del file visualizzato nella visualizzazione di testo in pertinenza.</span><span class="sxs-lookup"><span data-stu-id="8bc2a-125">Ignore text applied to Relevance will be removed in the displayed file content in the text view in Relevance.</span></span> <span data-ttu-id="8bc2a-126">Se i valori per il testo Ignora sono stati definiti dopo la formazione di pertinenza già avviata, il nuovo testo ignorato verrà applicato ai file di esempio creati dal punto in cui è stata definita.</span><span class="sxs-lookup"><span data-stu-id="8bc2a-126">If the values for Ignore text were defined after Relevance training already started, the new ignored text will be applied to sample files created from the point in which it was defined.</span></span> <span data-ttu-id="8bc2a-127">La funzionalità Ignora testo deve essere utilizzata con cautela, in quanto il relativo utilizzo può ridurre le prestazioni dell'analisi dei file</span><span class="sxs-lookup"><span data-stu-id="8bc2a-127">The Ignore Text feature should be used cautiously, as its use may reduce the performance of file analysis</span></span>
    
  - <span data-ttu-id="8bc2a-128">Utilizzare l'opzione **Ignora Tag** solo se necessario.</span><span class="sxs-lookup"><span data-stu-id="8bc2a-128">Use the **Skip tagging** option only when necessary.</span></span> <span data-ttu-id="8bc2a-129">Le indagini sui dati (Preview) non si basano sui file ignorati.</span><span class="sxs-lookup"><span data-stu-id="8bc2a-129">Data Investigations (Preview) does not train based on skipped files.</span></span> <span data-ttu-id="8bc2a-130">In valutazione, se è difficile stabilire se un file è pertinente, è consigliabile contrassegnarlo come pertinente (R) o non pertinente (NR) quando possibile anziché selezionando **Ignora**.</span><span class="sxs-lookup"><span data-stu-id="8bc2a-130">In assessment, if it's hard to tell whether a file is relevant, it is better to tag as Relevant (R) or Not relevant (NR) whenever possible rather than selecting **Skip**.</span></span> <span data-ttu-id="8bc2a-131">Quando le indagini sui dati (Preview) valutano la formazione, è possibile vedere in che modo sono stati elaborati questi tipi di file.</span><span class="sxs-lookup"><span data-stu-id="8bc2a-131">When Data Investigations (Preview) evaluates training, it can then be seen how well these types of files were processed.</span></span>
    
  - <span data-ttu-id="8bc2a-132">Anche i file con una quantità minima di testo estratto devono essere contrassegnati in formazione come R/NR, anziché come "Skip", quando possibile.</span><span class="sxs-lookup"><span data-stu-id="8bc2a-132">Even files with a very small amount of extracted text should be tagged in training as R/NR, rather than as "Skip", when possible.</span></span> 
    
  - <span data-ttu-id="8bc2a-133">Il tagging può influire sul classificatore fino a quando il file è leggibile e può essere contrassegnato come R/NR.</span><span class="sxs-lookup"><span data-stu-id="8bc2a-133">Tagging can impact the classifier as long as the file is readable and can be tagged as R/NR.</span></span>
    
  - <span data-ttu-id="8bc2a-134">Il numero di sequenza dei file nell'elenco di file di esempio visualizzato nella scheda **tag** consente all'utente di tornare all'ordine di file originale visualizzato.</span><span class="sxs-lookup"><span data-stu-id="8bc2a-134">The file sequence number on the displayed Sample files list on the **Tag** tab allows the user to return to the original displayed order of the files.</span></span> 
    
  - <span data-ttu-id="8bc2a-135">È possibile tornare a qualsiasi campione e modificare il tagging dei file di set di valutazione e formazione.</span><span class="sxs-lookup"><span data-stu-id="8bc2a-135">You can go back to any sample and change the tagging of the assessment and training set files.</span></span> <span data-ttu-id="8bc2a-136">Le modifiche verranno applicate quando si crea l'esempio successivo.</span><span class="sxs-lookup"><span data-stu-id="8bc2a-136">The changes will be applied when creating the next sample.</span></span>
    
  - <span data-ttu-id="8bc2a-137">I file di Excel analizzati in formato PDF devono essere considerati come file di Excel nativo durante il tagging dei file.</span><span class="sxs-lookup"><span data-stu-id="8bc2a-137">Scanned Excel files in PDF format should be treated the same as native Excel files when tagging files.</span></span>
    
  - <span data-ttu-id="8bc2a-138">In caso di dubbi sul tagging della pertinenza di un file, consultare un esperto.</span><span class="sxs-lookup"><span data-stu-id="8bc2a-138">When in doubt regarding the Relevance tagging of a file, consult an expert.</span></span> <span data-ttu-id="8bc2a-139">L'utilizzo di tag non corretti durante la formazione di pertinenza può comportare una perdita di tempo nel corso del processo e potrebbe anche avere un impatto negativo sulla qualità dei risultati complessivi.</span><span class="sxs-lookup"><span data-stu-id="8bc2a-139">Incorrect tagging during the Relevance training can lead to lost time later in the process and may also have a negative impact on the quality of the overall results.</span></span>
    
  - <span data-ttu-id="8bc2a-140">Le parole chiave definite negli elenchi di parole chiave verranno visualizzate nei colori per consentire all'utente di identificare i file rilevanti durante il tagging.</span><span class="sxs-lookup"><span data-stu-id="8bc2a-140">Keywords that were defined in Keyword lists will be displayed in colors to help the user identify relevant files while tagging.</span></span>
    
- <span data-ttu-id="8bc2a-141">**Calcolo batch**: i file contrassegnati come R/Nr dall'esperto riceveranno un punteggio pari a 0 o 100.</span><span class="sxs-lookup"><span data-stu-id="8bc2a-141">**Batch calculation**: Files that were tagged as R/NR by the expert will receive a score of either 0 or 100.</span></span> <span data-ttu-id="8bc2a-142">Questo si applica al tagging eseguito prima del calcolo del batch.</span><span class="sxs-lookup"><span data-stu-id="8bc2a-142">This applies to tagging made before Batch calculation.</span></span> <span data-ttu-id="8bc2a-143">Se l'esperto ha passato il problema a inattività dopo il calcolo del batch e ha continuato a contrassegnare questo problema, i punteggi appena contrassegnati non saranno 100/0 ma piuttosto la partitura originale.</span><span class="sxs-lookup"><span data-stu-id="8bc2a-143">If the expert switched the issue to Idle after Batch Calculation and continued tagging this issue, the newly tagged scores will not be 100/0 but rather the original score.</span></span>
    
- <span data-ttu-id="8bc2a-144">**Problemi e modalità di campionamento**: i problemi vengono in genere disattivati durante il completamento del lavoro (la formazione di pertinenza è stabilizzata e il calcolo in batch è stato eseguito), quando i problemi vengono annullati o quando un altro utente sta lavorando sui problemi.</span><span class="sxs-lookup"><span data-stu-id="8bc2a-144">**Issues and sampling mode**: Issues are usually turned Off when work on them is completed (Relevance training is stabilized and Batch calculation was performed), when the issues are canceled, or when another user is working on the issues.</span></span>
    
## <a name="steps-in-relevance-training"></a><span data-ttu-id="8bc2a-145">Passaggi per la formazione sulla pertinenza</span><span class="sxs-lookup"><span data-stu-id="8bc2a-145">Steps in Relevance training</span></span>

<span data-ttu-id="8bc2a-146">Nella scheda \*\* \> Tracking pertinenza\*\* , le indagini sui dati forniscono suggerimenti su come procedere nell'elaborazione, con i passaggi successivi seguenti.</span><span class="sxs-lookup"><span data-stu-id="8bc2a-146">In the **Relevance \> Track** tab, Data investigations provides recommendations on how to proceed in the processing, with the following next steps.</span></span> <span data-ttu-id="8bc2a-147">Le implicazioni sono descritte di seguito quando si consiglia di eseguire ciascuna delle operazioni seguenti nel processo di formazione per pertinenza.</span><span class="sxs-lookup"><span data-stu-id="8bc2a-147">The implications are described below when each of the following steps is recommended in the Relevance training process.</span></span> 
  
- <span data-ttu-id="8bc2a-148">Tagging/continua tagging: revisione dei file e tagging della pertinenza eseguito da un esperto per ogni file e problema all'interno di un esempio.</span><span class="sxs-lookup"><span data-stu-id="8bc2a-148">Tagging / Continue tagging: File review and Relevance tagging performed by an expert for each file and issue within a sample.</span></span>
    
  - <span data-ttu-id="8bc2a-149">Implicazione: è necessario contrassegnare un esempio esistente.</span><span class="sxs-lookup"><span data-stu-id="8bc2a-149">Implication: An existing sample needs to be tagged.</span></span>
    
- <span data-ttu-id="8bc2a-150">Assessment/continue assessment: consente la convalida precoce della pertinenza del problema del caso e una visualizzazione preliminare della pertinenza del popolamento dei file importato per il caso corrente.</span><span class="sxs-lookup"><span data-stu-id="8bc2a-150">Assessment / Continue assessment: Enables early validation of case issue relevance and a preliminary view of the relevance of the file population imported for the current case.</span></span>
    
  - <span data-ttu-id="8bc2a-151">Implicazioni: è richiesta o consigliata una maggiore valutazione.</span><span class="sxs-lookup"><span data-stu-id="8bc2a-151">Implication: More assessment is required or recommended.</span></span>
    
- <span data-ttu-id="8bc2a-152">Training/continue Training: processo durante il quale le indagini sui dati vengono apprese dall'esperto che è in grado di contrassegnare gli esempi di file e acquisisce la possibilità di identificare i criteri di pertinenza pertinenti a ogni problema nel contesto di ogni caso.</span><span class="sxs-lookup"><span data-stu-id="8bc2a-152">Training / Continue training: Process during which Data investigations learns from the expert who is tagging the file samples and acquires the ability to identify Relevance criteria pertinent to each issue within the context of each case.</span></span>
    
  - <span data-ttu-id="8bc2a-153">Implicazione: il problema richiede una formazione maggiore; è necessario creare e contrassegnare l'esempio successivo.</span><span class="sxs-lookup"><span data-stu-id="8bc2a-153">Implication: The issue needs more training; the next sample should be created and tagged.</span></span> 
    
- <span data-ttu-id="8bc2a-154">Calcolo batch: processo di pertinenza in cui le indagini sui dati prendono le conoscenze acquisite durante la fase di formazione e lo applicano all'intera popolazione dei file.</span><span class="sxs-lookup"><span data-stu-id="8bc2a-154">Batch calculation: Relevance process in which Data investigations takes the knowledge acquired during the training stage and applies it to the entire file population.</span></span> <span data-ttu-id="8bc2a-155">Tutti i file del gruppo di file pertinente sono valutati per pertinenza e assegnato un punteggio di pertinenza.</span><span class="sxs-lookup"><span data-stu-id="8bc2a-155">All files in the pertinent file group are assessed for relevance and assigned a Relevance score.</span></span>
    
  - <span data-ttu-id="8bc2a-156">Implicazione: il problema si è stabilizzato e il calcolo in batch può essere eseguito.</span><span class="sxs-lookup"><span data-stu-id="8bc2a-156">Implication: The issue has stabilized, and Batch calculation can be performed.</span></span>
    
- <span data-ttu-id="8bc2a-157">Catch-up: pertinenza indica quando un esperto esamina e contrassegna un campione di file selezionati da un ulteriore caricamento di file durante uno scenario di carichi di rotolamento.</span><span class="sxs-lookup"><span data-stu-id="8bc2a-157">Catch-up: Relevance indicates when an expert reviews and tags a sample of files selected from an additional file load during a Rolling Loads scenario.</span></span>
    
  - <span data-ttu-id="8bc2a-158">Implicazione: è stato aggiunto un nuovo carico e il recupero è necessario per continuare a funzionare.</span><span class="sxs-lookup"><span data-stu-id="8bc2a-158">Implication: A new load has been added, and Catch-up is required to continue working.</span></span>
    
- <span data-ttu-id="8bc2a-159">Inconsistenze Tag: Process identifica, tramite un algoritmo di analisi dei dati, incoerenze nel processo di tagging del file che potrebbe influire negativamente sull'analisi.</span><span class="sxs-lookup"><span data-stu-id="8bc2a-159">Tag inconsistencies: Process identifies, via an Data investigations algorithm, inconsistencies in the file tagging process that may negatively impact the analysis.</span></span>
    
  - <span data-ttu-id="8bc2a-160">Implicazioni: nell'esempio seguente vengono inclusi i file contrassegnati in esempi precedenti e il loro tagging deve essere rifatto.</span><span class="sxs-lookup"><span data-stu-id="8bc2a-160">Implication: The next sample will include files that have been tagged in previous samples, and their tagging must be redone.</span></span>
    
- <span data-ttu-id="8bc2a-161">Aggiorna classificatore: consente all'utente di applicare le modifiche di tagging o seeding.</span><span class="sxs-lookup"><span data-stu-id="8bc2a-161">Update classifier: Allows the user to apply tagging or seeding changes.</span></span>
    
  - <span data-ttu-id="8bc2a-162">Implicazioni: è possibile applicare le modifiche di tagging e seeding senza dover eseguire manualmente un altro esempio di pertinenza.</span><span class="sxs-lookup"><span data-stu-id="8bc2a-162">Implication: Tagging and seeding changes can be applied without needing to manually run another Relevance sample.</span></span>
    
- <span data-ttu-id="8bc2a-163">In attesa: il processo di formazione sulla pertinenza è stato completato.</span><span class="sxs-lookup"><span data-stu-id="8bc2a-163">On hold: The Relevance training process is completed.</span></span>
    
  - <span data-ttu-id="8bc2a-164">Implicazione: non è necessaria alcuna formazione di pertinenza a questo punto.</span><span class="sxs-lookup"><span data-stu-id="8bc2a-164">Implication: No Relevance training is required at this point.</span></span>
    
<span data-ttu-id="8bc2a-165">Anche se le indagini sui dati guidano il processo, con i passaggi successivi consigliati nelle diverse fasi, consente anche di spostarsi tra le schede e le pagine e di fare scelte per risolvere le situazioni che potrebbero essere rilevanti per il singolo caso, il problema o processo di revisione del documento.</span><span class="sxs-lookup"><span data-stu-id="8bc2a-165">Although Data investigations guides you through the process, with recommended Next steps at different stages, it also allows you to navigate between tabs and pages, and to make choices to address situations that may be pertinent to your individual case, issue, or document review process.</span></span> 
  
<span data-ttu-id="8bc2a-166">È possibile accettare o sostituire le indagini sui dati nelle scelte successive all'elaborazione dei passaggi.</span><span class="sxs-lookup"><span data-stu-id="8bc2a-166">It is possible to accept or override Data investigations Next step processing choices.</span></span> <span data-ttu-id="8bc2a-167">Se si desidera eseguire una procedura diversa da quella consigliata, fare clic sul **passaggio successivo** elencato nella visualizzazione del problema espanso nella finestra di dialogo, fare clic sul pulsante **modifica** accanto al passaggio successivo e selezionare un'altra opzione per il passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="8bc2a-167">If you want to perform a step other than the recommended Next step, click the **Next step** listed in the expanded issue display in the dialog, click the **Modify** button next to the Next step, and select another Next step option.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="8bc2a-168">Alcune opzioni potrebbero rimanere disabilitate dopo lo sblocco, in quanto non sono supportate per l'utilizzo in quel momento del processo.</span><span class="sxs-lookup"><span data-stu-id="8bc2a-168">Some options may remain disabled after unlocking as they are not supported for use at that point in the process.</span></span> 
  
## <a name="more-information"></a><span data-ttu-id="8bc2a-169">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="8bc2a-169">More information</span></span>

[<span data-ttu-id="8bc2a-170">Informazioni sulla valutazione in rilevanza</span><span class="sxs-lookup"><span data-stu-id="8bc2a-170">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="8bc2a-171">Tagging e valutazione</span><span class="sxs-lookup"><span data-stu-id="8bc2a-171">Tagging and assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="8bc2a-172">Formazione di tagging e pertinenza</span><span class="sxs-lookup"><span data-stu-id="8bc2a-172">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="8bc2a-173">Verifica dell'analisi della pertinenza</span><span class="sxs-lookup"><span data-stu-id="8bc2a-173">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="8bc2a-174">Decidere in base ai risultati</span><span class="sxs-lookup"><span data-stu-id="8bc2a-174">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="8bc2a-175">Verifica dell'analisi della pertinenza</span><span class="sxs-lookup"><span data-stu-id="8bc2a-175">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

[<span data-ttu-id="8bc2a-176">Eseguire una query sui dati in evidenza</span><span class="sxs-lookup"><span data-stu-id="8bc2a-176">Query the data in evidence</span></span>](evidence-query.md)
