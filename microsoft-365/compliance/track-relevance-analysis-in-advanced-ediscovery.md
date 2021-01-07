---
title: Monitorare l'analisi della pertinenza in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 3ab1e2c3-28cf-4bf5-b0a8-c0222f32bdf5
ROBOTS: NOINDEX, NOFOLLOW
description: Informazioni su come visualizzare e interpretare lo stato e i risultati della formazione sulla pertinenza per i problemi di caso in Advanced eDiscovery.
ms.openlocfilehash: 224337969b5e662d45c5b804fa5a0ee045f4fb84
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769181"
---
# <a name="track-relevance-analysis-in-advanced-ediscovery"></a><span data-ttu-id="15edf-103">Monitorare l'analisi della pertinenza in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="15edf-103">Track Relevance analysis in Advanced eDiscovery</span></span>
  
<span data-ttu-id="15edf-104">In Advanced eDiscovery, la scheda della pista di pertinenza Visualizza la validità calcolata dell'allenamento di pertinenza eseguito nella scheda Tag e indica il passaggio successivo da eseguire nel processo di formazione iterativo in rilevanza.</span><span class="sxs-lookup"><span data-stu-id="15edf-104">In Advanced eDiscovery, the Relevance Track tab displays the calculated validity of the Relevance training performed in the Tag tab and indicates the next step to take in the iterative training process in Relevance.</span></span> 
  
## <a name="tracking-relevance-training-status"></a><span data-ttu-id="15edf-105">Verifica dello stato di formazione per pertinenza</span><span class="sxs-lookup"><span data-stu-id="15edf-105">Tracking Relevance training status</span></span>

1. <span data-ttu-id="15edf-106">Visualizzare i dettagli seguenti in base alla pertinenza per i problemi di caso, come illustrato nell'esempio seguente di una finestra di dialogo **nome problema** .</span><span class="sxs-lookup"><span data-stu-id="15edf-106">View the following details in Relevance Track for the case issues, as shown in the following example of an **Issue name** dialog below.</span></span>

   - <span data-ttu-id="15edf-107">**Valutazione**: questo indicatore di stato indica in quale misura la formazione sulla pertinenza eseguita a questo punto ha raggiunto l'obiettivo di valutazione in termini di margine di errore.</span><span class="sxs-lookup"><span data-stu-id="15edf-107">**Assessment**: This progress indicator shows to what degree the Relevance training performed to this point has achieved the assessment target in terms of margin of error.</span></span> <span data-ttu-id="15edf-108">Viene visualizzata anche la ricchezza dei risultati della formazione di pertinenza.</span><span class="sxs-lookup"><span data-stu-id="15edf-108">The richness of the Relevance training results is also displayed.</span></span>

   - <span data-ttu-id="15edf-109">**Training**: questo indicatore di stato e il suggerimento per gli strumenti con codice a colori indica la stabilità dei risultati di formazione e una scala numerica che mostra il numero di esempi di formazione sulla pertinenza contrassegnati per ogni problema.</span><span class="sxs-lookup"><span data-stu-id="15edf-109">**Training**: This color-coded progress indicator and tool-tip indicates the Relevance training results stability and a numeric scale showing the number of Relevance training samples tagged for each issue.</span></span> <span data-ttu-id="15edf-110">L'esperto monitora lo stato di avanzamento del processo di formazione per la pertinenza iterativa.</span><span class="sxs-lookup"><span data-stu-id="15edf-110">The expert monitors the progress of the iterative Relevance training process.</span></span> 
  
   - <span data-ttu-id="15edf-111">**Calcolo batch**: questo indicatore di stato fornisce informazioni sul completamento del calcolo batch.</span><span class="sxs-lookup"><span data-stu-id="15edf-111">**Batch calculation**: This progress indicator provides information about the completion of Batch calculation.</span></span>
  
   - <span data-ttu-id="15edf-112">**Passaggio successivo**: Visualizza la raccomandazione per il passaggio successivo da eseguire.</span><span class="sxs-lookup"><span data-stu-id="15edf-112">**Next step**: Displays the recommendation for the next step to be performed.</span></span> 
  
    <span data-ttu-id="15edf-113">In questo esempio viene mostrata una valutazione completata correttamente per un problema, indicata dall'indicatore di stato dei colori completato e dal segno di spunta.</span><span class="sxs-lookup"><span data-stu-id="15edf-113">In the example, a successfully completed Assessment for an issue is shown, indicated by the completed color progress indicator and the checkmark.</span></span> <span data-ttu-id="15edf-114">Il tagging è in corso, ma il caso è ancora considerato instabile (stato di stabilità mostrato anche in un suggerimento per gli strumenti).</span><span class="sxs-lookup"><span data-stu-id="15edf-114">Tagging is underway, but the case is still considered unstable (stability status also shown in a tool-tip).</span></span> <span data-ttu-id="15edf-115">La raccomandazione per il passaggio successivo è "formazione".</span><span class="sxs-lookup"><span data-stu-id="15edf-115">The next step recommendation is "Training".</span></span> 
  
    ![Fase 1 del corso di formazione sulla traccia di pertinenza](../media/a00fe607-680a-48eb-9d61-4565319f7ab6.png)
  
    <span data-ttu-id="15edf-117">La visualizzazione espansa Visualizza ulteriori informazioni e opzioni.</span><span class="sxs-lookup"><span data-stu-id="15edf-117">The expanded view displays additional information and options.</span></span> <span data-ttu-id="15edf-118">Il margine di errore corrente visualizzato è il margine di errore del richiamo nello stato corrente di valutazione, in base ai file di valutazione esistenti (già contrassegnati).</span><span class="sxs-lookup"><span data-stu-id="15edf-118">The displayed current error margin is the error margin of the recall in the current state of assessment, given the existing (already tagged) assessment files.</span></span>
  
    > [!NOTE]
    >  <span data-ttu-id="15edf-119">La fase di valutazione può essere ignorata deselezionando la casella di controllo **valutazione** per ogni problema e quindi per "tutti i problemi".</span><span class="sxs-lookup"><span data-stu-id="15edf-119">The Assessment stage can be bypassed by clearing the **Assessment** check box per issue and then for "all issues".</span></span> <span data-ttu-id="15edf-120">Tuttavia, di conseguenza, non saranno disponibili statistiche per questo problema.</span><span class="sxs-lookup"><span data-stu-id="15edf-120">However, as a result, there will be no statistics for this issue.</span></span> <span data-ttu-id="15edf-121">> deselezionando la casella di controllo **valutazione** può essere eseguita solo prima di eseguire la valutazione.</span><span class="sxs-lookup"><span data-stu-id="15edf-121">> Clearing the **Assessment** check box can only be done before assessment is performed.</span></span> <span data-ttu-id="15edf-122">Se in un caso esistono più problemi, la valutazione viene ignorata solo se la casella di controllo è deselezionata per ogni problema.</span><span class="sxs-lookup"><span data-stu-id="15edf-122">Where multiple issues exist in a case, assessment is bypassed only if the check box is cleared for each issue</span></span> 
  
    <span data-ttu-id="15edf-123">Quando la valutazione non viene completata con il primo set di file di esempio, la valutazione potrebbe essere il passaggio successivo per la codifica di altri file.</span><span class="sxs-lookup"><span data-stu-id="15edf-123">When assessment is not completed with the first sample set of files, assessment might be the next step for tagging more files.</span></span>
  
    <span data-ttu-id="15edf-124">In **pista pertinenza** \> , l'indicatore di avanzamento della formazione e il suggerimento per gli strumenti indicano il numero stimato di esempi aggiuntivi necessari per raggiungere la stabilità.</span><span class="sxs-lookup"><span data-stu-id="15edf-124">In **Relevance** \> **Track**, the training progress indicator and tool-tip indicate the estimated number of additional samples needed to reach stability.</span></span> <span data-ttu-id="15edf-125">Questa stima fornisce una guida di riferimento per l'addestramento supplementare necessario.</span><span class="sxs-lookup"><span data-stu-id="15edf-125">This estimate provides a guideline for the additional training needed.</span></span>
  
    ![Corso di formazione sulla traccia di pertinenza](../media/98dbc3f5-5238-4d73-9f88-1aa4d77ea729.png)
  
2. <span data-ttu-id="15edf-127">Dopo aver completato il tagging e, se è necessario continuare l'allenamento, fare clic su **formazione**.</span><span class="sxs-lookup"><span data-stu-id="15edf-127">When you're done tagging and if you need to continue training, click **Training**.</span></span> <span data-ttu-id="15edf-128">Un altro set di file di esempio viene generato dal set di file caricati per una formazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="15edf-128">Another sample set of files is generated from the loaded file set for additional training.</span></span> <span data-ttu-id="15edf-129">Viene quindi restituito alla scheda Tag per contrassegnare e formare più file.</span><span class="sxs-lookup"><span data-stu-id="15edf-129">You are then returned to the Tag tab to tag and train more files.</span></span>

### <a name="reaching-stable-training-levels"></a><span data-ttu-id="15edf-130">Raggiungimento di livelli di formazione stabili</span><span class="sxs-lookup"><span data-stu-id="15edf-130">Reaching stable training levels</span></span>

<span data-ttu-id="15edf-131">Dopo che i file di valutazione hanno raggiunto un livello di formazione stabile, Advanced eDiscovery è pronto per il calcolo in batch.</span><span class="sxs-lookup"><span data-stu-id="15edf-131">After the assessment files have attained a stable level of training, Advanced eDiscovery is ready for Batch calculation.</span></span>
  
> [!NOTE]
> <span data-ttu-id="15edf-132">In genere, dopo tre esempi di formazione stabili, il passaggio successivo è "calcolo batch".</span><span class="sxs-lookup"><span data-stu-id="15edf-132">Usually, after three stable training samples, the next step is "Batch calculation".</span></span> <span data-ttu-id="15edf-133">Possono verificarsi eccezioni, ad esempio, quando sono state apportate modifiche al tagging dei file da esempi precedenti o quando sono stati aggiunti file di seeding.</span><span class="sxs-lookup"><span data-stu-id="15edf-133">There may be exceptions, for example, when there were changes to the tagging of files from earlier samples or when seed files were added.</span></span> 
  
### <a name="performing-batch-calculation"></a><span data-ttu-id="15edf-134">Esecuzione del calcolo batch</span><span class="sxs-lookup"><span data-stu-id="15edf-134">Performing Batch calculation</span></span>

<span data-ttu-id="15edf-135">Il calcolo batch viene eseguito come passaggio successivo dopo che l'allenamento è stato completato correttamente (quando uno stato di formazione stabile è visualizzato dall'indicatore di stato, un segno di spunta e uno stato stabile nella descrizione comando.) Il calcolo in batch applica le conoscenze acquisite durante la formazione di pertinenza all'intera popolazione dei file, per valutare la pertinenza dei file e assegnare punteggi di pertinenza.</span><span class="sxs-lookup"><span data-stu-id="15edf-135">Batch calculation is executed as the next step after training is successfully completed (when a stable training status is shown by the progress bar, a checkmark and stable status in the tool-tip.) Batch calculation applies the knowledge acquired during the Relevance training to the entire file population, to assess the files' relevance and to assign Relevance scores.</span></span>
  
<span data-ttu-id="15edf-136">In caso di più di un problema, il calcolo del batch viene effettuato per ogni problema.</span><span class="sxs-lookup"><span data-stu-id="15edf-136">When there is more than one issue, Batch calculation is done per issue.</span></span> <span data-ttu-id="15edf-137">Durante il calcolo batch, durante l'elaborazione di tutti i file viene monitorato lo stato di avanzamento.</span><span class="sxs-lookup"><span data-stu-id="15edf-137">During Batch calculation, progress is monitored while processing all of the files.</span></span> 
  
<span data-ttu-id="15edf-138">In questo caso, il passaggio successivo consigliato è "None", che indica che a questo punto non sono necessari ulteriori corsi di rilevanza iterativa.</span><span class="sxs-lookup"><span data-stu-id="15edf-138">Here, the recommended next step is "None", which indicates that no additional iterative Relevance training is required at this point.</span></span> <span data-ttu-id="15edf-139">La fase successiva è la scheda **rilevanza \> decidere** .</span><span class="sxs-lookup"><span data-stu-id="15edf-139">The next phase is the **Relevance \> Decide** tab.</span></span> 
  
<span data-ttu-id="15edf-140">Se si desidera importare nuovi file dopo il calcolo del batch, l'amministratore può aggiungere i file importati a un nuovo carico.</span><span class="sxs-lookup"><span data-stu-id="15edf-140">If you want to import new files after Batch calculation, the administrator can add the imported files to a new load.</span></span>
  
> [!NOTE]
> <span data-ttu-id="15edf-141">Se si fa clic su **Annulla** durante il calcolo batch, il processo Salva ciò che è già stato eseguito.</span><span class="sxs-lookup"><span data-stu-id="15edf-141">If you click **Cancel** during Batch calculation, the process saves what was already executed.</span></span> <span data-ttu-id="15edf-142">Se si esegue di nuovo il calcolo batch, il processo continuerà dall'ultimo punto eseguito.</span><span class="sxs-lookup"><span data-stu-id="15edf-142">If you run Batch calculation again, the process will continue from the last executed point.</span></span> 
  
### <a name="assessing-tagging-consistency"></a><span data-ttu-id="15edf-143">Valutazione della coerenza di tagging</span><span class="sxs-lookup"><span data-stu-id="15edf-143">Assessing tagging consistency</span></span>

<span data-ttu-id="15edf-144">Se sono presenti incoerenze nel tagging dei file, può influire sull'analisi.</span><span class="sxs-lookup"><span data-stu-id="15edf-144">If there are inconsistencies in file tagging, it can affect the analysis.</span></span> <span data-ttu-id="15edf-145">Il processo di coerenza tagging avanzato di eDiscovery può essere utilizzato quando i risultati non sono ottimali o la coerenza è in dubbio.</span><span class="sxs-lookup"><span data-stu-id="15edf-145">The Advanced eDiscovery tagging consistency process can be used when results are not optimal or consistency is in doubt.</span></span> <span data-ttu-id="15edf-146">Viene restituito un elenco dei possibili file contrassegnati con incoerenza, che possono essere esaminati e retagged, se necessario.</span><span class="sxs-lookup"><span data-stu-id="15edf-146">A list of possible inconsistently tagged files is returned, and they can be reviewed and retagged, as necessary.</span></span>
  
> [!NOTE]
> <span data-ttu-id="15edf-147">Dopo sette o più turni di allenamento dopo la valutazione, la coerenza di tagging può essere visualizzata in caso di **rilevanza** \>  \>  \> **dei risultati dettagliati** \> **avanzamento della formazione**.</span><span class="sxs-lookup"><span data-stu-id="15edf-147">After seven or more training rounds following assessment, tagging consistency can be viewed in **Relevance** \> **Track** \> **Issue** \> **Detailed results** \> **Training progress**.</span></span> <span data-ttu-id="15edf-148">Questa revisione viene fatta per un problema alla volta.</span><span class="sxs-lookup"><span data-stu-id="15edf-148">This review is done for one issue at a time.</span></span>
  
1. <span data-ttu-id="15edf-149">Nella **\> colonna pertinenza** espandere la riga di un problema.</span><span class="sxs-lookup"><span data-stu-id="15edf-149">In **Relevance \> Track**, expand an issue's row.</span></span>
  
2. <span data-ttu-id="15edf-150">A destra del **passaggio successivo**, fare clic su **modifica**.</span><span class="sxs-lookup"><span data-stu-id="15edf-150">To the right of **Next step**, click **Modify**.</span></span>
  
3. <span data-ttu-id="15edf-151">Selezionare **incoerenze dei tag** come opzione del **passaggio successivo** , dopo sette esempi di formazione e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="15edf-151">Select **Tag inconsistencies** as the **Next step** option, after seven training samples and click **OK**.</span></span>
  
4. <span data-ttu-id="15edf-152">Selezionare **incoerenze Tag**.</span><span class="sxs-lookup"><span data-stu-id="15edf-152">Select **Tag inconsistencies**.</span></span> <span data-ttu-id="15edf-153">La scheda **tag** apre la visualizzazione di un elenco delle incoerenze di riapplicare in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="15edf-153">The **Tag** tab opens displaying a list of the inconsistencies to retag as necessary.</span></span>
  
5. <span data-ttu-id="15edf-154">Fare clic su **Calcola** per inviare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="15edf-154">Click **Calculate** to submit the changes.</span></span> <span data-ttu-id="15edf-155">Il passaggio successivo dopo la codifica delle incoerenze è "formazione".</span><span class="sxs-lookup"><span data-stu-id="15edf-155">The next step after tagging inconsistencies is "Training".</span></span> 
  
## <a name="viewing-and-using-relevance-results"></a><span data-ttu-id="15edf-156">Visualizzazione e utilizzo dei risultati di pertinenza</span><span class="sxs-lookup"><span data-stu-id="15edf-156">Viewing and using Relevance results</span></span>

<span data-ttu-id="15edf-157">Nella scheda **\> rilevamento pertinenza** espandere la riga di un problema e, accanto a **risultati dettagliati**, fare clic su **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="15edf-157">In the **Relevance \> Track** tab, expand an issue's row, and next to **Detailed results**, click **View**.</span></span> <span data-ttu-id="15edf-158">Vengono visualizzati i riquadri dei risultati dettagliati, come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="15edf-158">The Detailed results panes are displayed, as shown and described below.</span></span>
  
![Risultati dettagliati della formazione sulla pertinenza](../media/495c04a9-ed1e-4355-8cab-c14270ca2bbb.png)
  
### <a name="tagging-summary"></a><span data-ttu-id="15edf-160">Riepilogo di tagging</span><span class="sxs-lookup"><span data-stu-id="15edf-160">Tagging summary</span></span>

 <span data-ttu-id="15edf-161">Nell'esempio riportato di seguito, il **Riepilogo di tagging** Visualizza i totali per ogni processo di valutazione, formazione e recupero dei file di tagging.</span><span class="sxs-lookup"><span data-stu-id="15edf-161">In the example shown below, the **Tagging summary** displays totals for each of Assessment, Training, and Catch-up file tagging processes.</span></span>
  
![Riepilogo tagging della traccia di pertinenza](../media/0ec906fc-bc84-4245-a964-fb3ca37891db.png)
  
### <a name="keywords"></a><span data-ttu-id="15edf-163">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="15edf-163">Keywords</span></span>

<span data-ttu-id="15edf-164">Una parola chiave è una stringa univoca, una parola, una frase o una sequenza di parole in un file identificato da Advanced eDiscovery come un indicatore significativo del fatto che un file sia pertinente.</span><span class="sxs-lookup"><span data-stu-id="15edf-164">A keyword is a unique string, word, phrase, or sequence of words in a file identified by Advanced eDiscovery as a significant indicator of whether a file is relevant.</span></span> <span data-ttu-id="15edf-165">La parola chiave di elenco "Includi" colonne e pesi nei file contrassegnati come rilevanti e le colonne "Escludi" elenca le parole chiave e i pesi nei file contrassegnati come non rilevanti.</span><span class="sxs-lookup"><span data-stu-id="15edf-165">The "Include" columns list keyword and weights in files tagged as Relevant, and the "Exclude" columns lists keywords and weights in files tagged as Not relevant.</span></span>
  
<span data-ttu-id="15edf-166">Advanced eDiscovery assegna valori di peso a parole chiave negative o positive.</span><span class="sxs-lookup"><span data-stu-id="15edf-166">Advanced eDiscovery assigns negative or positive keyword weight values.</span></span> <span data-ttu-id="15edf-167">Maggiore è il peso, maggiore è la probabilità che a un file in cui viene visualizzata la parola chiave sia assegnato un punteggio di pertinenza maggiore durante il calcolo in batch.</span><span class="sxs-lookup"><span data-stu-id="15edf-167">The higher the weight, the higher the likelihood that a file in which the keyword appears is assigned a higher Relevance score during Batch calculation.</span></span>
  
<span data-ttu-id="15edf-168">L'elenco avanzato di parole chiave di eDiscovery può essere utilizzato per completare un elenco compilato da un esperto o come verifica di integrità indiretta in qualsiasi punto del processo di revisione dei file.</span><span class="sxs-lookup"><span data-stu-id="15edf-168">The Advanced eDiscovery list of keywords can be used to supplement a list built by an expert or as an indirect sanity check at any point in the file review process.</span></span>
  
### <a name="training-progress"></a><span data-ttu-id="15edf-169">Avanzamento della formazione</span><span class="sxs-lookup"><span data-stu-id="15edf-169">Training progress</span></span>

<span data-ttu-id="15edf-170">Nel riquadro **avanzamento formazione** è incluso un grafico dello stato di avanzamento della formazione e un indicatore di qualità, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="15edf-170">The **Training Progress** pane includes a training progress graph and quality indicator display, as shown in the example below.</span></span>
  
![Stato di avanzamento del corso di formazione sulla traccia di pertinenza](../media/8a5089f5-a162-4246-ae09-bc1921859860.png)
  
<span data-ttu-id="15edf-172">**Indicatore qualità formazione**: Visualizza la classificazione della coerenza di tagging come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="15edf-172">**Training quality indicator**: Displays the rating of the tagging consistency as follows:</span></span>
  
- <span data-ttu-id="15edf-173">**Good**: i file vengono contrassegnati in modo coerente.</span><span class="sxs-lookup"><span data-stu-id="15edf-173">**Good**: Files are tagged consistently.</span></span> <span data-ttu-id="15edf-174">(Luce verde visualizzata)</span><span class="sxs-lookup"><span data-stu-id="15edf-174">(Green light displayed)</span></span>
  
- <span data-ttu-id="15edf-175">**Medium**: alcuni file possono essere contrassegnati in maniera incoerente.</span><span class="sxs-lookup"><span data-stu-id="15edf-175">**Medium**: Some files may be tagged inconsistently.</span></span> <span data-ttu-id="15edf-176">(Indicatore luminoso giallo visualizzato)</span><span class="sxs-lookup"><span data-stu-id="15edf-176">(Yellow light displayed)</span></span>

- <span data-ttu-id="15edf-177">**Avviso**: molti file possono essere contrassegnati in maniera incoerente.</span><span class="sxs-lookup"><span data-stu-id="15edf-177">**Warning**: Many files may be tagged inconsistently.</span></span> <span data-ttu-id="15edf-178">(Luce rossa visualizzata)</span><span class="sxs-lookup"><span data-stu-id="15edf-178">(Red light displayed)</span></span>

<span data-ttu-id="15edf-179">**Grafico dello stato di avanzamento** della formazione: indica il grado di stabilità della formazione di pertinenza dopo numerosi cicli di formazione di pertinenza rispetto al valore di F-Measure.</span><span class="sxs-lookup"><span data-stu-id="15edf-179">**Training progress graph**: Shows the degree of Relevance training stability after many Relevance training cycles in comparison to the F-measure value.</span></span> <span data-ttu-id="15edf-180">Quando si passa da sinistra a destra all'interno del grafico, l'intervallo di confidenza si restringe e viene utilizzato, insieme alla misura F, dalla pertinenza avanzata di eDiscovery per determinare la stabilità quando i risultati della formazione sulla pertinenza sono ottimizzati.</span><span class="sxs-lookup"><span data-stu-id="15edf-180">As we move from the left to the right across the graph, the confidence interval narrows and is used, along with the F-measure, by Advanced eDiscovery Relevance to determine stability when the Relevance training results are optimized.</span></span>
  
> [!NOTE]
> <span data-ttu-id="15edf-181">La pertinenza utilizza F2, una metrica di misura F in cui il richiamo riceve il doppio del peso di precisione.</span><span class="sxs-lookup"><span data-stu-id="15edf-181">Relevance uses F2, an F-measure metric where Recall receives twice as much weight as Precision.</span></span> <span data-ttu-id="15edf-182">Per i casi con elevata ricchezza (oltre il 25%), la pertinenza utilizza la F1 (rapporto 1:1).</span><span class="sxs-lookup"><span data-stu-id="15edf-182">For cases with high richness (over 25%), Relevance uses F1 (1:1 ratio).</span></span> <span data-ttu-id="15edf-183">Il rapporto di misura F può essere configurato in impostazioni avanzate per l' **installazione di pertinenza** \> .</span><span class="sxs-lookup"><span data-stu-id="15edf-183">The F-measure ratio can be configured in **Relevance setup** \> **Advanced settings**.</span></span>
  
### <a name="batch-calculation-results"></a><span data-ttu-id="15edf-184">Risultati del calcolo batch</span><span class="sxs-lookup"><span data-stu-id="15edf-184">Batch calculation results</span></span>

<span data-ttu-id="15edf-185">Nel riquadro dei **risultati del calcolo batch** è incluso il numero di file che sono stati segnati per pertinenza, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="15edf-185">The **Batch calculation results** pane includes the number of files that were scored for Relevance, as follows:</span></span> 
  
- <span data-ttu-id="15edf-186">**Successo**</span><span class="sxs-lookup"><span data-stu-id="15edf-186">**Success**</span></span>
  
- <span data-ttu-id="15edf-187">**Empty**: non contiene testo, ad esempio solo spazi/tabulazioni</span><span class="sxs-lookup"><span data-stu-id="15edf-187">**Empty**: Contains no text, for example, only spaces/tabs</span></span>
  
- <span data-ttu-id="15edf-188">**Errore**: a causa delle dimensioni eccessive o non è stato possibile leggerlo</span><span class="sxs-lookup"><span data-stu-id="15edf-188">**Failed**: Due to excessive size or could not be read</span></span>
  
- <span data-ttu-id="15edf-189">**Ignorato**: a causa delle dimensioni eccessive</span><span class="sxs-lookup"><span data-stu-id="15edf-189">**Ignored**: Due to excessive size</span></span>
  
- <span data-ttu-id="15edf-190">**Nebuloso**: contiene testo privo di significato o caratteristiche rilevanti per il problema</span><span class="sxs-lookup"><span data-stu-id="15edf-190">**Nebulous**: Contains meaningless text or no features relevant to the issue</span></span>
  
> [!NOTE]
> <span data-ttu-id="15edf-191">Empty, failed, ignorato o nebuloso riceverà un punteggio di pertinenza pari a-1.</span><span class="sxs-lookup"><span data-stu-id="15edf-191">Empty, Failed, Ignored, or Nebulous will receive a Relevance score of -1.</span></span>
  
### <a name="training-statistics"></a><span data-ttu-id="15edf-192">Statistiche sulla formazione</span><span class="sxs-lookup"><span data-stu-id="15edf-192">Training statistics</span></span>

<span data-ttu-id="15edf-193">Nel riquadro **statistiche formazione** vengono visualizzate statistiche e grafici basati sui risultati di una formazione di pertinenza avanzata di eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="15edf-193">The **Training statistics** pane displays statistics and graphs based on results from Advanced eDiscovery Relevance training.</span></span> 
  
![Statistiche del corso di formazione sulla traccia di pertinenza](../media/9a07740e-20d3-49fb-b9b9-84265e0a1836.png)
  
<span data-ttu-id="15edf-195">Questa visualizzazione Mostra gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="15edf-195">This view shows the following:</span></span>
  
- <span data-ttu-id="15edf-196">**Rapporto Revisione-richiamo**: confronto dei risultati in base ai punteggi di rilevanza in una revisione ipotetica lineare.</span><span class="sxs-lookup"><span data-stu-id="15edf-196">**Review-recall ratio**: Comparison of results according to Relevance scores in a hypothetically linear review.</span></span> <span data-ttu-id="15edf-197">Il richiamo è stimato in base al set di dimensioni del set di revisione.</span><span class="sxs-lookup"><span data-stu-id="15edf-197">Recall is estimated given the review set size set.</span></span>
  
- <span data-ttu-id="15edf-198">**Parametri**: statistiche calcolate cumulative relative al set di riesame in relazione alla popolazione dei file per l'intero caso.</span><span class="sxs-lookup"><span data-stu-id="15edf-198">**Parameters**: Cumulative calculated statistics pertaining to the review set in relation to the file population for the entire case.</span></span>
  
- <span data-ttu-id="15edf-199">**Recensione**: percentuale di file da esaminare in base a questo cutoff.</span><span class="sxs-lookup"><span data-stu-id="15edf-199">**Review**: Percentage of files to review based on this cutoff.</span></span>
  
- <span data-ttu-id="15edf-200">**Richiamo**: percentuale dei file rilevanti nel set di revisione.</span><span class="sxs-lookup"><span data-stu-id="15edf-200">**Recall**: Percentage of Relevant files in the review set.</span></span> 
  
- <span data-ttu-id="15edf-201">**Distribuzione per Punteggio di pertinenza**: i file nel display grigio scuro a sinistra sono al di sotto del Punteggio di taglio.</span><span class="sxs-lookup"><span data-stu-id="15edf-201">**Distribution by relevance score**: Files in the dark gray display to the left are below the cutoff score.</span></span> <span data-ttu-id="15edf-202">Un suggerimento per gli strumenti Visualizza il Punteggio di pertinenza e la percentuale relativa di file nel set di file di revisione in relazione ai file totali.</span><span class="sxs-lookup"><span data-stu-id="15edf-202">A tool-tip displays the Relevance score and the related percentage of files in the review file set in relation to the total files.</span></span>
