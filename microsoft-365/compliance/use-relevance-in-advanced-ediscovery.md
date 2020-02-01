---
title: Utilizzare il modulo pertinenza in Office 365 Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 5d671821-d188-42da-a9ce-9cfe92beedfd
description: 'Informazioni sul modulo pertinenza in Office 365 Advanced eDiscovery, tra cui un flusso di lavoro e le linee guida e i passaggi per la formazione e la revisione dei file.  '
ms.openlocfilehash: 5151c94d2b0bd1824abb499f6cb27bbfbc7618b7
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601303"
---
# <a name="use-the-relevance-module-in-office-365-advanced-ediscovery"></a><span data-ttu-id="0922e-103">Utilizzare il modulo pertinenza in Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="0922e-103">Use the Relevance module in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="0922e-p101">Per usare Advanced eDiscovery è necessario avere Office 365 E3 con il componente aggiuntivo Advanced Compliance o un abbonamento E5 dell'organizzazione. Se non si ha questo piano e si desidera provare Advanced eDiscovery, è possibile [richiedere una valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="0922e-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="0922e-106">In Advanced eDiscovery, il modulo pertinenza include la formazione sulla pertinenza e la revisione dei file correlati a un caso.</span><span class="sxs-lookup"><span data-stu-id="0922e-106">In Advanced eDiscovery, the Relevance module includes the Relevance training and review of files related to a case.</span></span> <span data-ttu-id="0922e-107">Il flusso di lavoro di pertinenza è illustrato e descritto nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="0922e-107">The Relevance workflow is shown and described as follows:</span></span>
  
![Flusso di lavoro di pertinenza](media/44c67dd2-7a20-40a9-b0ed-784364845c77.gif)
  
- <span data-ttu-id="0922e-109">**Cicli di valutazione e tracciabilità**:</span><span class="sxs-lookup"><span data-stu-id="0922e-109">**Cycles of assessment and tracking**:</span></span>
    
  - <span data-ttu-id="0922e-110">**Valutazione**: Advanced eDiscovery consente una valutazione precoce basata su un campione casuale di file e utilizza questa valutazione per applicare le decisioni per determinare le prestazioni del processo di codifica predittiva.</span><span class="sxs-lookup"><span data-stu-id="0922e-110">**Assessment**: Advanced eDiscovery enables early assessment based on a random sample of files and uses this assessment to apply decisions to determine the performance of the predictive coding process.</span></span> 
    
  - <span data-ttu-id="0922e-111">**Track**: Advanced eDiscovery calcola e Visualizza i risultati intermedi della valutazione monitorando la validità statistica del processo.</span><span class="sxs-lookup"><span data-stu-id="0922e-111">**Track**: Advanced eDiscovery calculates and displays interim results of the assessment while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="0922e-112">**Cicli di formazione e tracciabilità**:</span><span class="sxs-lookup"><span data-stu-id="0922e-112">**Cycles of training and tracking**:</span></span>
    
  - <span data-ttu-id="0922e-113">**Tag**: Advanced eDiscovery apprende criteri di pertinenza specifici per ogni problema in base alla revisione iterativa dell'esperto e al tagging di singoli file.</span><span class="sxs-lookup"><span data-stu-id="0922e-113">**Tag**: Advanced eDiscovery learns Relevance criteria specific to each issue based on the expert's iterative review and tagging of individual files.</span></span>
    
  - <span data-ttu-id="0922e-114">**Track**: Advanced eDiscovery calcola e Visualizza i risultati intermedi della formazione sulla pertinenza monitorando la validità statistica del processo.</span><span class="sxs-lookup"><span data-stu-id="0922e-114">**Track**: Advanced eDiscovery calculates and displays interim results of the Relevance training while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="0922e-115">**Calcolo batch**: Advanced eDiscovery accetta i criteri di pertinenza accumulati e appresi, lo applica all'intera raccolta di file e genera punteggi di pertinenza per ogni file.</span><span class="sxs-lookup"><span data-stu-id="0922e-115">**Batch calculation**: Advanced eDiscovery takes the accumulated and learned Relevance criteria, applies it to the entire file collection, and generates Relevance scores for each file.</span></span>
    
- <span data-ttu-id="0922e-116">**Decidere**: Advanced eDiscovery consente di visualizzare i risultati dell'analisi applicata all'intero caso dopo il calcolo batch e di visualizzare i dati per le decisioni relative alla revisione dei documenti.</span><span class="sxs-lookup"><span data-stu-id="0922e-116">**Decide**: Advanced eDiscovery displays the results of the analysis applied to the entire case after Batch calculation and displays data for making document review decisions.</span></span>
    
- <span data-ttu-id="0922e-117">**Test**: i risultati di Advanced eDiscovery possono essere testati per verificare la validità e l'efficacia dell'elaborazione avanzata di eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="0922e-117">**Test**: Advanced eDiscovery results can be tested to verify the validity and effectiveness of the Advanced eDiscovery processing.</span></span>
    
## <a name="guidelines-for-relevance-training-and-review"></a><span data-ttu-id="0922e-118">Linee guida per la formazione e la revisione della pertinenza</span><span class="sxs-lookup"><span data-stu-id="0922e-118">Guidelines for Relevance training and review</span></span>

<span data-ttu-id="0922e-119">Di seguito è riportata una panoramica delle linee guida per la formazione e la revisione della pertinenza:</span><span class="sxs-lookup"><span data-stu-id="0922e-119">Following is an overview of guidelines for Relevance training and review:</span></span>
  
- <span data-ttu-id="0922e-120">**Errori e incoerenze**: se durante l'allenamento vengono eseguiti gli errori di tagging, tornare agli esempi di file precedenti per correggerli.</span><span class="sxs-lookup"><span data-stu-id="0922e-120">**Errors and inconsistencies**: If tagging errors are made during training, return to previous file samples to correct them.</span></span> <span data-ttu-id="0922e-121">Se si verifica un numero eccessivo di errori da correggere oppure è presente una nuova prospettiva del caso o del problema, i criteri di pertinenza devono essere ridefiniti dall'amministratore e riavviato il Training relativo alla pertinenza.</span><span class="sxs-lookup"><span data-stu-id="0922e-121">If there are too many errors to correct or there is a new perspective of the case or issue, the Relevance criteria should be redefined by the Administrator, and the Relevance training restarted.</span></span>
    
- <span data-ttu-id="0922e-122">**Tagging e formazione**:</span><span class="sxs-lookup"><span data-stu-id="0922e-122">**Tagging and training**:</span></span> 
    
  - <span data-ttu-id="0922e-123">I file devono essere contrassegnati in base solo al contenuto.</span><span class="sxs-lookup"><span data-stu-id="0922e-123">Files should be tagged based on content only.</span></span> <span data-ttu-id="0922e-124">Non considerare i metadati, ad esempio il custode, la data o il percorso del file.</span><span class="sxs-lookup"><span data-stu-id="0922e-124">Do not consider metadata, such as custodian, date, or file path.</span></span> 
    
  - <span data-ttu-id="0922e-125">Non prendere in considerazione le indicazioni dell'intervallo di date nel testo durante il tagging dei file.</span><span class="sxs-lookup"><span data-stu-id="0922e-125">Do not consider date range indications in the text when tagging files.</span></span>
    
  - <span data-ttu-id="0922e-126">Non considerare le immagini grafiche incorporate durante il tagging dei file.</span><span class="sxs-lookup"><span data-stu-id="0922e-126">Do not consider embedded graphical images when tagging files.</span></span>
    
  - <span data-ttu-id="0922e-127">Se si visualizza un file utilizzando l'icona di **visualizzazione testo formattato** durante il tagging, non prendere in considerazione la formattazione del testo.</span><span class="sxs-lookup"><span data-stu-id="0922e-127">If viewing a file using the **formatted text view** icon while tagging, do not consider the formatting of text.</span></span> <span data-ttu-id="0922e-128">Ad esempio, una parola visualizzata con un barrato (una linea orizzontale attraverso il centro indicante l'eliminazione) è ancora considerata come parte del testo analizzato per pertinenza.</span><span class="sxs-lookup"><span data-stu-id="0922e-128">For example, a word displayed with a strikethrough (a horizontal line through its center indicating deletion) is still considered by Relevance as part of the analyzed text.</span></span> 
    
  - <span data-ttu-id="0922e-129">Ignorare il testo applicato alla pertinenza (come stabilito dal responsabile del caso o dall'amministratore) verrà rimosso nel contenuto del file visualizzato nella visualizzazione di testo in pertinenza.</span><span class="sxs-lookup"><span data-stu-id="0922e-129">Ignore text applied to Relevance (as set by the Case Manager or Administrator) will be removed in the displayed file content in the text view in Relevance.</span></span> <span data-ttu-id="0922e-130">Se i valori per il testo Ignora sono stati definiti dopo la formazione di pertinenza già avviata, il nuovo testo ignorato verrà applicato ai file di esempio creati dal punto in cui è stata definita.</span><span class="sxs-lookup"><span data-stu-id="0922e-130">If the values for Ignore text were defined after Relevance training already started, the new ignored text will be applied to sample files created from the point in which it was defined.</span></span> <span data-ttu-id="0922e-131">La funzionalità Ignora testo deve essere utilizzata con cautela, in quanto il relativo utilizzo può ridurre le prestazioni dell'analisi dei file</span><span class="sxs-lookup"><span data-stu-id="0922e-131">The Ignore Text feature should be used cautiously, as its use may reduce the performance of file analysis</span></span>
    
  - <span data-ttu-id="0922e-132">Utilizzare l'opzione **Ignora Tag** solo se necessario.</span><span class="sxs-lookup"><span data-stu-id="0922e-132">Use the **Skip tagging** option only when necessary.</span></span> <span data-ttu-id="0922e-133">Advanced eDiscovery non si allena in base ai file ignorati.</span><span class="sxs-lookup"><span data-stu-id="0922e-133">Advanced eDiscovery does not train based on skipped files.</span></span> <span data-ttu-id="0922e-134">In valutazione, se è difficile stabilire se un file è pertinente, è consigliabile contrassegnarlo come pertinente (R) o non pertinente (NR) quando possibile anziché selezionando **Ignora**.</span><span class="sxs-lookup"><span data-stu-id="0922e-134">In assessment, if it's hard to tell whether a file is relevant, it is better to tag as Relevant (R) or Not relevant (NR) whenever possible rather than selecting **Skip**.</span></span> <span data-ttu-id="0922e-135">Quando Advanced eDiscovery valuta la formazione, può essere visto bene come sono stati elaborati questi tipi di file.</span><span class="sxs-lookup"><span data-stu-id="0922e-135">When Advanced eDiscovery evaluates training, it can then be seen how well these types of files were processed.</span></span>
    
  - <span data-ttu-id="0922e-136">Anche i file con una quantità minima di testo estratto devono essere contrassegnati in formazione come R/NR, anziché come "Skip", quando possibile.</span><span class="sxs-lookup"><span data-stu-id="0922e-136">Even files with a very small amount of extracted text should be tagged in training as R/NR, rather than as "Skip", when possible.</span></span> 
    
  - <span data-ttu-id="0922e-137">Il tagging può influire sul classificatore fino a quando il file è leggibile e può essere contrassegnato come R/NR.</span><span class="sxs-lookup"><span data-stu-id="0922e-137">Tagging can impact the classifier as long as the file is readable and can be tagged as R/NR.</span></span>
    
  - <span data-ttu-id="0922e-138">Il numero di sequenza dei file nell'elenco di file di esempio visualizzato nella scheda **tag** consente all'utente di tornare all'ordine di file originale visualizzato.</span><span class="sxs-lookup"><span data-stu-id="0922e-138">The file sequence number on the displayed Sample files list on the **Tag** tab allows the user to return to the original displayed order of the files.</span></span> 
    
  - <span data-ttu-id="0922e-139">È possibile tornare a qualsiasi campione e modificare il tagging dei file di set di valutazione e formazione.</span><span class="sxs-lookup"><span data-stu-id="0922e-139">You can go back to any sample and change the tagging of the assessment and training set files.</span></span> <span data-ttu-id="0922e-140">Le modifiche verranno applicate quando si crea l'esempio successivo.</span><span class="sxs-lookup"><span data-stu-id="0922e-140">The changes will be applied when creating the next sample.</span></span>
    
  - <span data-ttu-id="0922e-141">I file di Excel analizzati in formato PDF devono essere considerati come file di Excel nativo durante il tagging dei file.</span><span class="sxs-lookup"><span data-stu-id="0922e-141">Scanned Excel files in PDF format should be treated the same as native Excel files when tagging files.</span></span>
    
  - <span data-ttu-id="0922e-142">In caso di dubbi sul tagging della pertinenza di un file, consultare un esperto.</span><span class="sxs-lookup"><span data-stu-id="0922e-142">When in doubt regarding the Relevance tagging of a file, consult an expert.</span></span> <span data-ttu-id="0922e-143">L'utilizzo di tag non corretti durante la formazione di pertinenza può comportare una perdita di tempo nel corso del processo e potrebbe anche avere un impatto negativo sulla qualità dei risultati complessivi.</span><span class="sxs-lookup"><span data-stu-id="0922e-143">Incorrect tagging during the Relevance training can lead to lost time later in the process and may also have a negative impact on the quality of the overall results.</span></span>
    
  - <span data-ttu-id="0922e-144">Le parole chiave definite negli elenchi di parole chiave verranno visualizzate nei colori per consentire all'utente di identificare i file rilevanti durante il tagging.</span><span class="sxs-lookup"><span data-stu-id="0922e-144">Keywords that were defined in Keyword lists will be displayed in colors to help the user identify relevant files while tagging.</span></span>
    
- <span data-ttu-id="0922e-145">**Calcolo batch**: i file contrassegnati come R/Nr dall'esperto riceveranno un punteggio pari a 0 o 100.</span><span class="sxs-lookup"><span data-stu-id="0922e-145">**Batch calculation**: Files that were tagged as R/NR by the expert will receive a score of either 0 or 100.</span></span> <span data-ttu-id="0922e-146">Questo si applica al tagging eseguito prima del calcolo del batch.</span><span class="sxs-lookup"><span data-stu-id="0922e-146">This applies to tagging made before Batch calculation.</span></span> <span data-ttu-id="0922e-147">Se l'esperto ha passato il problema a inattività dopo il calcolo del batch e ha continuato a contrassegnare questo problema, i punteggi appena contrassegnati non saranno 100/0 ma piuttosto la partitura originale.</span><span class="sxs-lookup"><span data-stu-id="0922e-147">If the expert switched the issue to Idle after Batch Calculation and continued tagging this issue, the newly tagged scores will not be 100/0 but rather the original score.</span></span>
    
- <span data-ttu-id="0922e-148">**Problemi e modalità di campionamento**: i problemi vengono in genere disattivati durante il completamento del lavoro (la formazione di pertinenza è stabilizzata e il calcolo in batch è stato eseguito), quando i problemi vengono annullati o quando un altro utente sta lavorando sui problemi.</span><span class="sxs-lookup"><span data-stu-id="0922e-148">**Issues and sampling mode**: Issues are usually turned Off when work on them is completed (Relevance training is stabilized and Batch calculation was performed), when the issues are canceled, or when another user is working on the issues.</span></span>
    
## <a name="steps-in-relevance-training"></a><span data-ttu-id="0922e-149">Passaggi per la formazione sulla pertinenza</span><span class="sxs-lookup"><span data-stu-id="0922e-149">Steps in Relevance training</span></span>

<span data-ttu-id="0922e-150">Nella scheda \*\* \> rilevamento di pertinenza\*\* Advanced eDiscovery fornisce consigli su come procedere nell'elaborazione, con i passaggi successivi seguenti.</span><span class="sxs-lookup"><span data-stu-id="0922e-150">In the **Relevance \> Track** tab, Advanced eDiscovery provides recommendations on how to proceed in the processing, with the following next steps.</span></span> <span data-ttu-id="0922e-151">Le implicazioni sono descritte di seguito quando si consiglia di eseguire ciascuna delle operazioni seguenti nel processo di formazione per pertinenza.</span><span class="sxs-lookup"><span data-stu-id="0922e-151">The implications are described below when each of the following steps is recommended in the Relevance training process.</span></span> 
  
- <span data-ttu-id="0922e-152">Tagging/continua tagging: revisione dei file e tagging della pertinenza eseguito da un esperto per ogni file e problema all'interno di un esempio.</span><span class="sxs-lookup"><span data-stu-id="0922e-152">Tagging / Continue tagging: File review and Relevance tagging performed by an expert for each file and issue within a sample.</span></span>
    
  - <span data-ttu-id="0922e-153">Implicazione: è necessario contrassegnare un esempio esistente.</span><span class="sxs-lookup"><span data-stu-id="0922e-153">Implication: An existing sample needs to be tagged.</span></span>
    
- <span data-ttu-id="0922e-154">Assessment/continue assessment: consente la convalida precoce della pertinenza del problema del caso e una visualizzazione preliminare della pertinenza del popolamento dei file importato per il caso corrente.</span><span class="sxs-lookup"><span data-stu-id="0922e-154">Assessment / Continue assessment: Enables early validation of case issue relevance and a preliminary view of the relevance of the file population imported for the current case.</span></span>
    
  - <span data-ttu-id="0922e-155">Implicazioni: è richiesta o consigliata una maggiore valutazione.</span><span class="sxs-lookup"><span data-stu-id="0922e-155">Implication: More assessment is required or recommended.</span></span>
    
- <span data-ttu-id="0922e-156">Training/continue Training: processo durante il quale Advanced eDiscovery apprende dall'esperto che è in grado di contrassegnare gli esempi di file e acquisisce la capacità di identificare i criteri di pertinenza rilevanti per ogni problema nel contesto di ogni caso.</span><span class="sxs-lookup"><span data-stu-id="0922e-156">Training / Continue training: Process during which Advanced eDiscovery learns from the expert who is tagging the file samples and acquires the ability to identify Relevance criteria pertinent to each issue within the context of each case.</span></span>
    
  - <span data-ttu-id="0922e-157">Implicazione: il problema richiede una formazione maggiore; è necessario creare e contrassegnare l'esempio successivo.</span><span class="sxs-lookup"><span data-stu-id="0922e-157">Implication: The issue needs more training; the next sample should be created and tagged.</span></span> 
    
- <span data-ttu-id="0922e-158">Calcolo batch: processo di pertinenza in cui Advanced eDiscovery acquisisce le conoscenze acquisite durante la fase di formazione e lo applica all'intera popolazione dei file.</span><span class="sxs-lookup"><span data-stu-id="0922e-158">Batch calculation: Relevance process in which Advanced eDiscovery takes the knowledge acquired during the training stage and applies it to the entire file population.</span></span> <span data-ttu-id="0922e-159">Tutti i file del gruppo di file pertinente sono valutati per pertinenza e assegnato un punteggio di pertinenza.</span><span class="sxs-lookup"><span data-stu-id="0922e-159">All files in the pertinent file group are assessed for relevance and assigned a Relevance score.</span></span>
    
  - <span data-ttu-id="0922e-160">Implicazione: il problema si è stabilizzato e il calcolo in batch può essere eseguito.</span><span class="sxs-lookup"><span data-stu-id="0922e-160">Implication: The issue has stabilized, and Batch calculation can be performed.</span></span>
    
- <span data-ttu-id="0922e-161">Catch-up: pertinenza indica quando un esperto esamina e contrassegna un campione di file selezionati da un ulteriore caricamento di file durante uno scenario di carichi di rotolamento.</span><span class="sxs-lookup"><span data-stu-id="0922e-161">Catch-up: Relevance indicates when an expert reviews and tags a sample of files selected from an additional file load during a Rolling Loads scenario.</span></span>
    
  - <span data-ttu-id="0922e-162">Implicazione: è stato aggiunto un nuovo carico e il recupero è necessario per continuare a funzionare.</span><span class="sxs-lookup"><span data-stu-id="0922e-162">Implication: A new load has been added, and Catch-up is required to continue working.</span></span>
    
- <span data-ttu-id="0922e-163">Incoerenze dei tag: Process identifica, tramite un algoritmo avanzato di eDiscovery, incoerenze nel processo di tagging dei file che potrebbe influire negativamente sull'analisi.</span><span class="sxs-lookup"><span data-stu-id="0922e-163">Tag inconsistencies: Process identifies, via an Advanced eDiscovery algorithm, inconsistencies in the file tagging process that may negatively impact the analysis.</span></span>
    
  - <span data-ttu-id="0922e-164">Implicazioni: nell'esempio seguente vengono inclusi i file contrassegnati in esempi precedenti e il loro tagging deve essere rifatto.</span><span class="sxs-lookup"><span data-stu-id="0922e-164">Implication: The next sample will include files that have been tagged in previous samples, and their tagging must be redone.</span></span>
    
- <span data-ttu-id="0922e-165">Aggiorna classificatore: consente all'utente di applicare le modifiche di tagging o seeding.</span><span class="sxs-lookup"><span data-stu-id="0922e-165">Update classifier: Allows the user to apply tagging or seeding changes.</span></span>
    
  - <span data-ttu-id="0922e-166">Implicazioni: è possibile applicare le modifiche di tagging e seeding senza dover eseguire manualmente un altro esempio di pertinenza.</span><span class="sxs-lookup"><span data-stu-id="0922e-166">Implication: Tagging and seeding changes can be applied without needing to manually run another Relevance sample.</span></span>
    
- <span data-ttu-id="0922e-167">In attesa: il processo di formazione sulla pertinenza è stato completato.</span><span class="sxs-lookup"><span data-stu-id="0922e-167">On hold: The Relevance training process is completed.</span></span>
    
  - <span data-ttu-id="0922e-168">Implicazione: non è necessaria alcuna formazione di pertinenza a questo punto.</span><span class="sxs-lookup"><span data-stu-id="0922e-168">Implication: No Relevance training is required at this point.</span></span>
    
<span data-ttu-id="0922e-169">Anche se Advanced eDiscovery guida l'utente attraverso il processo, con i passaggi successivi consigliati nelle diverse fasi, consente anche di spostarsi tra le schede e le pagine e di fare scelte per risolvere le situazioni che potrebbero essere rilevanti per il singolo caso, problema o processo di revisione del documento.</span><span class="sxs-lookup"><span data-stu-id="0922e-169">Although Advanced eDiscovery guides you through the process, with recommended Next steps at different stages, it also allows you to navigate between tabs and pages, and to make choices to address situations that may be pertinent to your individual case, issue, or document review process.</span></span> 
  
<span data-ttu-id="0922e-170">È possibile accettare o sostituire le scelte avanzate di elaborazione dei passaggi successivi di eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="0922e-170">It is possible to accept or override Advanced eDiscovery Next step processing choices.</span></span> <span data-ttu-id="0922e-171">Se si desidera eseguire una procedura diversa da quella consigliata, fare clic sul **passaggio successivo** elencato nella visualizzazione del problema espanso nella finestra di dialogo, fare clic sul pulsante **modifica** accanto al passaggio successivo e selezionare un'altra opzione per il passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="0922e-171">If you want to perform a step other than the recommended Next step, click the **Next step** listed in the expanded issue display in the dialog, click the **Modify** button next to the Next step, and select another Next step option.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="0922e-172">Alcune opzioni potrebbero rimanere disabilitate dopo lo sblocco, in quanto non sono supportate per l'utilizzo in quel momento del processo.</span><span class="sxs-lookup"><span data-stu-id="0922e-172">Some options may remain disabled after unlocking as they are not supported for use at that point in the process.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="0922e-173">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0922e-173">See also</span></span>

[<span data-ttu-id="0922e-174">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="0922e-174">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="0922e-175">Informazioni sulla valutazione in rilevanza</span><span class="sxs-lookup"><span data-stu-id="0922e-175">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="0922e-176">Tagging e valutazione</span><span class="sxs-lookup"><span data-stu-id="0922e-176">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="0922e-177">Formazione di tagging e pertinenza</span><span class="sxs-lookup"><span data-stu-id="0922e-177">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="0922e-178">Verifica dell'analisi della pertinenza</span><span class="sxs-lookup"><span data-stu-id="0922e-178">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="0922e-179">Decidere in base ai risultati</span><span class="sxs-lookup"><span data-stu-id="0922e-179">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="0922e-180">Verifica dell'analisi della pertinenza</span><span class="sxs-lookup"><span data-stu-id="0922e-180">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

