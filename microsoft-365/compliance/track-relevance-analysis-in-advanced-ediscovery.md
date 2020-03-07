---
title: Monitorare l'analisi della pertinenza in Office 365 Advanced eDiscovery
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
ms.assetid: 3ab1e2c3-28cf-4bf5-b0a8-c0222f32bdf5
description: 'Informazioni su come visualizzare e interpretare lo stato e i risultati della formazione sulla pertinenza per i problemi di caso in Office 365 Advanced eDiscovery.  '
ms.openlocfilehash: 9c15bd285848d1906243137bfba451b19900b28e
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/07/2020
ms.locfileid: "42557676"
---
# <a name="track-relevance-analysis-in-advanced-ediscovery-classic"></a><span data-ttu-id="6eb36-103">Monitorare l'analisi della pertinenza in Advanced eDiscovery (Classic)</span><span class="sxs-lookup"><span data-stu-id="6eb36-103">Track Relevance analysis in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="6eb36-p101">Per usare Advanced eDiscovery è necessario avere Office 365 E3 con il componente aggiuntivo Advanced Compliance o un abbonamento E5 dell'organizzazione. Se non si ha questo piano e si desidera provare Advanced eDiscovery, è possibile [richiedere una valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="6eb36-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="6eb36-106">In Advanced eDiscovery, la scheda della pista di pertinenza Visualizza la validità calcolata dell'allenamento di pertinenza eseguito nella scheda Tag e indica il passaggio successivo da eseguire nel processo di formazione iterativo in rilevanza.</span><span class="sxs-lookup"><span data-stu-id="6eb36-106">In Advanced eDiscovery, the Relevance Track tab displays the calculated validity of the Relevance training performed in the Tag tab and indicates the next step to take in the iterative training process in Relevance.</span></span> 
  
## <a name="tracking-relevance-training-status"></a><span data-ttu-id="6eb36-107">Verifica dello stato di formazione per pertinenza</span><span class="sxs-lookup"><span data-stu-id="6eb36-107">Tracking Relevance training status</span></span>

1. <span data-ttu-id="6eb36-108">Visualizzare i dettagli seguenti in base alla pertinenza per i problemi di caso, come illustrato nell'esempio seguente di una finestra di dialogo **nome problema** .</span><span class="sxs-lookup"><span data-stu-id="6eb36-108">View the following details in Relevance Track for the case issues, as shown in the following example of an **Issue name** dialog below.</span></span> 
    
  - <span data-ttu-id="6eb36-109">**Valutazione**: questo indicatore di stato indica in quale misura la formazione sulla pertinenza eseguita a questo punto ha raggiunto l'obiettivo di valutazione in termini di margine di errore.</span><span class="sxs-lookup"><span data-stu-id="6eb36-109">**Assessment**: This progress indicator shows to what degree the Relevance training performed to this point has achieved the assessment target in terms of margin of error.</span></span> <span data-ttu-id="6eb36-110">Viene visualizzata anche la ricchezza dei risultati della formazione di pertinenza.</span><span class="sxs-lookup"><span data-stu-id="6eb36-110">The richness of the Relevance training results is also displayed.</span></span> 
    
  - <span data-ttu-id="6eb36-111">**Training**: questo indicatore di stato con codice a colori e la visualizzazione della descrizione comandi indicano la stabilità dei risultati di formazione e una scala numerica che mostra il numero di esempi di formazione sulla pertinenza contrassegnati per ogni problema.</span><span class="sxs-lookup"><span data-stu-id="6eb36-111">**Training**: This color-coded progress indicator and tool-tip display indicates the Relevance training results stability and a numeric scale showing the number of Relevance training samples tagged for each issue.</span></span> <span data-ttu-id="6eb36-112">L'esperto monitora lo stato di avanzamento del processo di formazione per la pertinenza iterativa.</span><span class="sxs-lookup"><span data-stu-id="6eb36-112">The expert monitors the progress of the iterative Relevance training process.</span></span> 
    
  - <span data-ttu-id="6eb36-113">**Calcolo batch**: questo indicatore di stato fornisce informazioni sul completamento del calcolo batch.</span><span class="sxs-lookup"><span data-stu-id="6eb36-113">**Batch calculation**: This progress indicator provides information about the completion of Batch calculation.</span></span>
    
  - <span data-ttu-id="6eb36-114">**Passaggio successivo**: Visualizza la raccomandazione per il passaggio successivo da eseguire.</span><span class="sxs-lookup"><span data-stu-id="6eb36-114">**Next step**: Displays the recommendation for the next step to be performed.</span></span> 
    
    <span data-ttu-id="6eb36-115">In questo esempio viene mostrata una valutazione completata correttamente per un problema, indicata dall'indicatore di stato dei colori completato e dal segno di spunta.</span><span class="sxs-lookup"><span data-stu-id="6eb36-115">In the example, a successfully completed Assessment for an issue is shown, indicated by the completed color progress indicator and the checkmark.</span></span> <span data-ttu-id="6eb36-116">Il tagging è in corso, ma il caso è ancora considerato instabile (stato di stabilità mostrato anche in un suggerimento per gli strumenti).</span><span class="sxs-lookup"><span data-stu-id="6eb36-116">Tagging is underway, but the case is still considered unstable (stability status also shown in a tool-tip).</span></span> <span data-ttu-id="6eb36-117">La raccomandazione per il passaggio successivo è "formazione".</span><span class="sxs-lookup"><span data-stu-id="6eb36-117">The next step recommendation is "Training".</span></span> 
    
    ![Fase 1 del corso di formazione sulla traccia di pertinenza](../media/a00fe607-680a-48eb-9d61-4565319f7ab6.png)
  
    <span data-ttu-id="6eb36-119">La visualizzazione espansa Visualizza ulteriori informazioni e opzioni.</span><span class="sxs-lookup"><span data-stu-id="6eb36-119">The expanded view displays additional information and options.</span></span> <span data-ttu-id="6eb36-120">Il margine di errore corrente visualizzato è il margine di errore del richiamo nello stato corrente di valutazione, in base ai file di valutazione esistenti (già contrassegnati).</span><span class="sxs-lookup"><span data-stu-id="6eb36-120">The displayed current error margin is the error margin of the recall in the current state of assessment, given the existing (already tagged) assessment files.</span></span>
    
    > [!NOTE]
    >  <span data-ttu-id="6eb36-121">La fase di valutazione può essere ignorata deselezionando la casella di controllo **valutazione** per ogni problema e quindi per "tutti i problemi".</span><span class="sxs-lookup"><span data-stu-id="6eb36-121">The Assessment stage can be bypassed by clearing the **Assessment** check box per issue and then for "all issues".</span></span> <span data-ttu-id="6eb36-122">Tuttavia, di conseguenza, non saranno disponibili statistiche per questo problema.</span><span class="sxs-lookup"><span data-stu-id="6eb36-122">However, as a result, there will be no statistics for this issue.</span></span> <span data-ttu-id="6eb36-123">> deselezionando la casella di controllo **valutazione** può essere eseguita solo prima di eseguire la valutazione.</span><span class="sxs-lookup"><span data-stu-id="6eb36-123">> Clearing the **Assessment** check box can only be done before assessment is performed.</span></span> <span data-ttu-id="6eb36-124">Se in un caso esistono più problemi, la valutazione viene ignorata solo se la casella di controllo è deselezionata per ogni problema.</span><span class="sxs-lookup"><span data-stu-id="6eb36-124">Where multiple issues exist in a case, assessment is bypassed only if the check box is cleared for each issue</span></span> 
  
    <span data-ttu-id="6eb36-125">Quando la valutazione non viene completata con il primo set di file di esempio, la valutazione potrebbe essere il passaggio successivo per la codifica di altri file.</span><span class="sxs-lookup"><span data-stu-id="6eb36-125">When assessment is not completed with the first sample set of files, assessment might be the next step for tagging more files.</span></span> 
    
    <span data-ttu-id="6eb36-126">In **pista** **pertinenza** \> , l'indicatore di avanzamento della formazione e il suggerimento per gli strumenti indicano il numero stimato di esempi aggiuntivi necessari per raggiungere la stabilità.</span><span class="sxs-lookup"><span data-stu-id="6eb36-126">In **Relevance** \> **Track**, the training progress indicator and tool-tip indicate the estimated number of additional samples needed to reach stability.</span></span> <span data-ttu-id="6eb36-127">Questa stima fornisce una guida di riferimento per l'addestramento supplementare necessario.</span><span class="sxs-lookup"><span data-stu-id="6eb36-127">This estimate provides a guideline for the additional training needed.</span></span>
    
    ![Corso di formazione sulla traccia di pertinenza](../media/98dbc3f5-5238-4d73-9f88-1aa4d77ea729.png)
  
2. <span data-ttu-id="6eb36-129">Dopo aver completato il tagging e, se è necessario continuare l'allenamento, fare clic su **formazione**.</span><span class="sxs-lookup"><span data-stu-id="6eb36-129">When you're done tagging and if you need to continue training, click **Training**.</span></span> <span data-ttu-id="6eb36-130">Un altro set di file di esempio viene generato dal set di file caricati per una formazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="6eb36-130">Another sample set of files is generated from the loaded file set for additional training.</span></span> <span data-ttu-id="6eb36-131">Viene quindi restituito alla scheda Tag per contrassegnare e formare più file.</span><span class="sxs-lookup"><span data-stu-id="6eb36-131">You are then returned to the Tag tab to tag and train more files.</span></span>
    
### <a name="reaching-stable-training-levels"></a><span data-ttu-id="6eb36-132">Raggiungimento di livelli di formazione stabili</span><span class="sxs-lookup"><span data-stu-id="6eb36-132">Reaching stable training levels</span></span>

<span data-ttu-id="6eb36-133">Dopo che i file di valutazione hanno raggiunto un livello di formazione stabile, Advanced eDiscovery è pronto per il calcolo in batch.</span><span class="sxs-lookup"><span data-stu-id="6eb36-133">After the assessment files have attained a stable level of training, Advanced eDiscovery is ready for Batch calculation.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6eb36-134">In genere, dopo tre esempi di formazione stabili, il passaggio successivo è "calcolo batch".</span><span class="sxs-lookup"><span data-stu-id="6eb36-134">Usually, after three stable training samples, the next step is "Batch calculation".</span></span> <span data-ttu-id="6eb36-135">Possono verificarsi eccezioni, ad esempio, quando sono state apportate modifiche al tagging dei file da esempi precedenti o quando sono stati aggiunti file di seeding.</span><span class="sxs-lookup"><span data-stu-id="6eb36-135">There may be exceptions, for example, when there were changes to the tagging of files from earlier samples or when seed files were added.</span></span> 
  
### <a name="performing-batch-calculation"></a><span data-ttu-id="6eb36-136">Esecuzione del calcolo batch</span><span class="sxs-lookup"><span data-stu-id="6eb36-136">Performing Batch calculation</span></span>

<span data-ttu-id="6eb36-137">Il calcolo batch viene eseguito come passaggio successivo dopo che l'allenamento è stato completato correttamente (quando uno stato di formazione stabile è visualizzato dall'indicatore di stato, un segno di spunta e uno stato stabile nella descrizione comando.) Il calcolo in batch applica le conoscenze acquisite durante la formazione di pertinenza all'intera popolazione dei file, per valutare la pertinenza dei file e assegnare punteggi di pertinenza.</span><span class="sxs-lookup"><span data-stu-id="6eb36-137">Batch calculation is executed as the next step after training is successfully completed (when a stable training status is shown by the progress bar, a checkmark and stable status in the tool-tip.) Batch calculation applies the knowledge acquired during the Relevance training to the entire file population, to assess the files' relevance and to assign Relevance scores.</span></span>
  
<span data-ttu-id="6eb36-138">In caso di più di un problema, il calcolo del batch viene effettuato per ogni problema.</span><span class="sxs-lookup"><span data-stu-id="6eb36-138">When there is more than one issue, Batch calculation is done per issue.</span></span> <span data-ttu-id="6eb36-139">Durante il calcolo batch, durante l'elaborazione di tutti i file viene monitorato lo stato di avanzamento.</span><span class="sxs-lookup"><span data-stu-id="6eb36-139">During Batch calculation, progress is monitored while processing all of the files.</span></span> 
  
<span data-ttu-id="6eb36-140">In questo caso, il passaggio successivo consigliato è "None", che indica che a questo punto non sono necessari ulteriori corsi di rilevanza iterativa.</span><span class="sxs-lookup"><span data-stu-id="6eb36-140">Here, the recommended next step is "None", which indicates that no additional iterative Relevance training is required at this point.</span></span> <span data-ttu-id="6eb36-141">La fase successiva è la scheda **rilevanza \> decidere** .</span><span class="sxs-lookup"><span data-stu-id="6eb36-141">The next phase is the **Relevance \> Decide** tab.</span></span> 
  
<span data-ttu-id="6eb36-142">Se si desidera importare nuovi file dopo il calcolo del batch, l'amministratore può aggiungere i file importati a un nuovo carico.</span><span class="sxs-lookup"><span data-stu-id="6eb36-142">If you want to import new files after Batch calculation, the administrator can add the imported files to a new load.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6eb36-143">Se si fa clic su **Annulla** durante il calcolo batch, il processo Salva ciò che è già stato eseguito.</span><span class="sxs-lookup"><span data-stu-id="6eb36-143">If you click **Cancel** during Batch calculation, the process saves what was already executed.</span></span> <span data-ttu-id="6eb36-144">Se si esegue di nuovo il calcolo batch, il processo continuerà dall'ultimo punto eseguito.</span><span class="sxs-lookup"><span data-stu-id="6eb36-144">If you run Batch calculation again, the process will continue from the last executed point.</span></span> 
  
### <a name="assessing-tagging-consistency"></a><span data-ttu-id="6eb36-145">Valutazione della coerenza di tagging</span><span class="sxs-lookup"><span data-stu-id="6eb36-145">Assessing tagging consistency</span></span>

<span data-ttu-id="6eb36-146">Se sono presenti incoerenze nel tagging dei file, può influire sull'analisi.</span><span class="sxs-lookup"><span data-stu-id="6eb36-146">If there are inconsistencies in file tagging, it can affect the analysis.</span></span> <span data-ttu-id="6eb36-147">Il processo di coerenza tagging avanzato di eDiscovery può essere utilizzato quando i risultati non sono ottimali o la coerenza è in dubbio.</span><span class="sxs-lookup"><span data-stu-id="6eb36-147">The Advanced eDiscovery tagging consistency process can be used when results are not optimal or consistency is in doubt.</span></span> <span data-ttu-id="6eb36-148">Viene restituito un elenco dei possibili file contrassegnati con incoerenza, che possono essere esaminati e contrassegnati nuovamente, se necessario.</span><span class="sxs-lookup"><span data-stu-id="6eb36-148">A list of possible inconsistently tagged files is returned, and they can be reviewed and re-tagged, as necessary.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6eb36-149">Dopo sette o più turni di allenamento dopo la valutazione, la coerenza di tagging può essere visualizzata in caso di **rilevanza** \> \*\*\*\* \> \*\*\*\* \> **dei risultati** \> dettagliati **avanzamento della formazione**.</span><span class="sxs-lookup"><span data-stu-id="6eb36-149">After seven or more training rounds following assessment, tagging consistency can be viewed in **Relevance** \> **Track** \> **Issue** \> **Detailed results** \> **Training progress**.</span></span> <span data-ttu-id="6eb36-150">Questa revisione viene fatta per un problema alla volta.</span><span class="sxs-lookup"><span data-stu-id="6eb36-150">This review is done for one issue at a time.</span></span> 
  
1. <span data-ttu-id="6eb36-151">Nella \*\* \> colonna pertinenza\*\*espandere la riga di un problema.</span><span class="sxs-lookup"><span data-stu-id="6eb36-151">In **Relevance \> Track**, expand an issue's row.</span></span>
    
2. <span data-ttu-id="6eb36-152">A destra del **passaggio successivo**, fare clic su **modifica**.</span><span class="sxs-lookup"><span data-stu-id="6eb36-152">To the right of **Next step**, click **Modify**.</span></span>
    
3. <span data-ttu-id="6eb36-153">Selezionare **incoerenze dei tag** come opzione del **passaggio successivo** , dopo sette esempi di formazione e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="6eb36-153">Select **Tag inconsistencies** as the **Next step** option, after seven training samples and click **OK**.</span></span>
    
4. <span data-ttu-id="6eb36-154">Selezionare **incoerenze Tag**.</span><span class="sxs-lookup"><span data-stu-id="6eb36-154">Select **Tag inconsistencies**.</span></span> <span data-ttu-id="6eb36-155">La scheda **tag** apre la visualizzazione di un elenco delle incoerenze da ricontrassegnare in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="6eb36-155">The **Tag** tab opens displaying a list of the inconsistencies to re-tag as necessary.</span></span> 
    
5. <span data-ttu-id="6eb36-156">Fare clic su **Calcola** per inviare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="6eb36-156">Click **Calculate** to submit the changes.</span></span> <span data-ttu-id="6eb36-157">Il passaggio successivo dopo la codifica delle incoerenze è "formazione".</span><span class="sxs-lookup"><span data-stu-id="6eb36-157">The next step after tagging inconsistencies is "Training".</span></span> 
    
## <a name="viewing-and-using-relevance-results"></a><span data-ttu-id="6eb36-158">Visualizzazione e utilizzo dei risultati di pertinenza</span><span class="sxs-lookup"><span data-stu-id="6eb36-158">Viewing and using Relevance results</span></span>

<span data-ttu-id="6eb36-159">Nella scheda \*\* \> rilevamento pertinenza\*\* espandere la riga di un problema e, accanto a **risultati dettagliati**, fare clic su **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="6eb36-159">In the **Relevance \> Track** tab, expand an issue's row, and next to **Detailed results**, click **View**.</span></span> <span data-ttu-id="6eb36-160">Vengono visualizzati i riquadri dei risultati dettagliati, come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="6eb36-160">The Detailed results panes are displayed, as shown and described below.</span></span>
  
![Risultati dettagliati della formazione sulla pertinenza](../media/495c04a9-ed1e-4355-8cab-c14270ca2bbb.png)
  
### <a name="tagging-summary"></a><span data-ttu-id="6eb36-162">Riepilogo di tagging</span><span class="sxs-lookup"><span data-stu-id="6eb36-162">Tagging summary</span></span>

 <span data-ttu-id="6eb36-163">Nell'esempio riportato di seguito, il **Riepilogo di tagging** Visualizza i totali per ogni processo di valutazione, formazione e recupero dei file di tagging.</span><span class="sxs-lookup"><span data-stu-id="6eb36-163">In the example shown below, the **Tagging summary** displays totals for each of Assessment, Training, and Catch-up file tagging processes.</span></span> 
  
![Riepilogo tagging della traccia di pertinenza](../media/0ec906fc-bc84-4245-a964-fb3ca37891db.png)
  
### <a name="keywords"></a><span data-ttu-id="6eb36-165">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="6eb36-165">Keywords</span></span>

<span data-ttu-id="6eb36-166">Una parola chiave è una stringa univoca, una parola, una frase o una sequenza di parole in un file identificato da Advanced eDiscovery come un indicatore significativo del fatto che un file sia pertinente.</span><span class="sxs-lookup"><span data-stu-id="6eb36-166">A keyword is a unique string, word, phrase, or sequence of words in a file identified by Advanced eDiscovery as a significant indicator of whether a file is relevant.</span></span> <span data-ttu-id="6eb36-167">La parola chiave di elenco "Includi" colonne e pesi nei file contrassegnati come rilevanti e le colonne "Escludi" elenca le parole chiave e i pesi nei file contrassegnati come non rilevanti.</span><span class="sxs-lookup"><span data-stu-id="6eb36-167">The "Include" columns list keyword and weights in files tagged as Relevant, and the "Exclude" columns lists keywords and weights in files tagged as Not relevant.</span></span>
  
<span data-ttu-id="6eb36-168">Advanced eDiscovery assegna valori di peso a parole chiave negative o positive.</span><span class="sxs-lookup"><span data-stu-id="6eb36-168">Advanced eDiscovery assigns negative or positive keyword weight values.</span></span> <span data-ttu-id="6eb36-169">Maggiore è il peso, maggiore è la probabilità che a un file in cui viene visualizzata la parola chiave sia assegnato un punteggio di pertinenza maggiore durante il calcolo in batch.</span><span class="sxs-lookup"><span data-stu-id="6eb36-169">The higher the weight, the higher the likelihood that a file in which the keyword appears is assigned a higher Relevance score during Batch calculation.</span></span> 
  
<span data-ttu-id="6eb36-170">L'elenco avanzato di parole chiave di eDiscovery può essere utilizzato per completare un elenco compilato da un esperto o come verifica di integrità indiretta in qualsiasi punto del processo di revisione dei file.</span><span class="sxs-lookup"><span data-stu-id="6eb36-170">The Advanced eDiscovery list of keywords can be used to supplement a list built by an expert or as an indirect sanity check at any point in the file review process.</span></span>
  
### <a name="training-progress"></a><span data-ttu-id="6eb36-171">Avanzamento della formazione</span><span class="sxs-lookup"><span data-stu-id="6eb36-171">Training progress</span></span>

<span data-ttu-id="6eb36-172">Nel riquadro **avanzamento formazione** è incluso un grafico dello stato di avanzamento della formazione e un indicatore di qualità, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="6eb36-172">The **Training Progress** pane includes a training progress graph and quality indicator display, as shown in the example below.</span></span> 
  
![Stato di avanzamento del corso di formazione sulla traccia di pertinenza](../media/8a5089f5-a162-4246-ae09-bc1921859860.png)
  
 <span data-ttu-id="6eb36-174">**Indicatore qualità formazione**: Visualizza la classificazione della coerenza di tagging come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="6eb36-174">**Training quality indicator**: Displays the rating of the tagging consistency as follows:</span></span>
  
- <span data-ttu-id="6eb36-175">**Good**: i file vengono contrassegnati in modo coerente.</span><span class="sxs-lookup"><span data-stu-id="6eb36-175">**Good**: Files are tagged consistently.</span></span> <span data-ttu-id="6eb36-176">(Luce verde visualizzata)</span><span class="sxs-lookup"><span data-stu-id="6eb36-176">(Green light displayed)</span></span>
    
- <span data-ttu-id="6eb36-177">**Medium**: alcuni file possono essere contrassegnati in maniera incoerente.</span><span class="sxs-lookup"><span data-stu-id="6eb36-177">**Medium**: Some files may be tagged inconsistently.</span></span> <span data-ttu-id="6eb36-178">(Indicatore luminoso giallo visualizzato)</span><span class="sxs-lookup"><span data-stu-id="6eb36-178">(Yellow light displayed)</span></span>
    
- <span data-ttu-id="6eb36-179">**Avviso**: molti file possono essere contrassegnati in maniera incoerente.</span><span class="sxs-lookup"><span data-stu-id="6eb36-179">**Warning**: Many files may be tagged inconsistently.</span></span> <span data-ttu-id="6eb36-180">(Luce rossa visualizzata)</span><span class="sxs-lookup"><span data-stu-id="6eb36-180">(Red light displayed)</span></span>
    
 <span data-ttu-id="6eb36-181">**Grafico Progress Training**: indica il grado di stabilità della formazione di pertinenza dopo un certo numero di cicli di formazione rilevanza rispetto al valore della misura F.</span><span class="sxs-lookup"><span data-stu-id="6eb36-181">**Training progress graph**: Shows the degree of Relevance training stability after a number of Relevance training cycles in comparison to the F-measure value.</span></span> <span data-ttu-id="6eb36-182">Quando si passa da sinistra a destra all'interno del grafico, l'intervallo di confidenza si restringe e viene utilizzato, insieme alla misura F, dalla pertinenza avanzata di eDiscovery per determinare la stabilità quando i risultati della formazione sulla pertinenza sono ottimizzati.</span><span class="sxs-lookup"><span data-stu-id="6eb36-182">As we move from the left to the right across the graph, the confidence interval narrows and is used, along with the F-measure, by Advanced eDiscovery Relevance to determine stability when the Relevance training results are optimized.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6eb36-183">La pertinenza utilizza F2, una metrica di misura F in cui il richiamo riceve il doppio del peso di precisione.</span><span class="sxs-lookup"><span data-stu-id="6eb36-183">Relevance uses F2, an F-measure metric where Recall receives twice as much weight as Precision.</span></span> <span data-ttu-id="6eb36-184">Per i casi con elevata ricchezza (oltre il 25%), la pertinenza utilizza la F1 (rapporto 1:1).</span><span class="sxs-lookup"><span data-stu-id="6eb36-184">For cases with high richness (over 25%), Relevance uses F1 (1:1 ratio).</span></span> <span data-ttu-id="6eb36-185">Il rapporto di misura F può essere configurato in \> **Impostazioni avanzate**per l' **installazione di pertinenza** .</span><span class="sxs-lookup"><span data-stu-id="6eb36-185">The F-measure ratio can be configured in **Relevance setup** \> **Advanced settings**.</span></span> 
  
### <a name="batch-calculation-results"></a><span data-ttu-id="6eb36-186">Risultati del calcolo batch</span><span class="sxs-lookup"><span data-stu-id="6eb36-186">Batch calculation results</span></span>

<span data-ttu-id="6eb36-187">Nel riquadro dei **risultati del calcolo batch** è incluso il numero di file che sono stati segnati per pertinenza, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="6eb36-187">The **Batch calculation results** pane includes the number of files that were scored for Relevance, as follows:</span></span> 
  
- <span data-ttu-id="6eb36-188">**Success**</span><span class="sxs-lookup"><span data-stu-id="6eb36-188">**Success**</span></span>
    
- <span data-ttu-id="6eb36-189">**Empty**: non contiene testo, ad esempio solo spazi/tabulazioni</span><span class="sxs-lookup"><span data-stu-id="6eb36-189">**Empty**: Contains no text, for example, only spaces/tabs</span></span>
    
- <span data-ttu-id="6eb36-190">**Errore**: a causa delle dimensioni eccessive o non è stato possibile leggerlo</span><span class="sxs-lookup"><span data-stu-id="6eb36-190">**Failed**: Due to excessive size or could not be read</span></span>
    
- <span data-ttu-id="6eb36-191">**Ignorato**: a causa delle dimensioni eccessive</span><span class="sxs-lookup"><span data-stu-id="6eb36-191">**Ignored**: Due to excessive size</span></span>
    
- <span data-ttu-id="6eb36-192">**Nebuloso**: contiene testo privo di significato o caratteristiche rilevanti per il problema</span><span class="sxs-lookup"><span data-stu-id="6eb36-192">**Nebulous**: Contains meaningless text or no features relevant to the issue</span></span>
    
> [!NOTE]
> <span data-ttu-id="6eb36-193">Empty, failed, ignorato o nebuloso riceverà un punteggio di pertinenza pari a-1.</span><span class="sxs-lookup"><span data-stu-id="6eb36-193">Empty, Failed, Ignored, or Nebulous will receive a Relevance score of -1.</span></span> 
  
### <a name="training-statistics"></a><span data-ttu-id="6eb36-194">Statistiche sulla formazione</span><span class="sxs-lookup"><span data-stu-id="6eb36-194">Training statistics</span></span>

<span data-ttu-id="6eb36-195">Nel riquadro **statistiche formazione** vengono visualizzate statistiche e grafici basati sui risultati di una formazione di pertinenza avanzata di eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="6eb36-195">The **Training statistics** pane displays statistics and graphs based on results from Advanced eDiscovery Relevance training.</span></span> 
  
![Statistiche del corso di formazione sulla traccia di pertinenza](../media/9a07740e-20d3-49fb-b9b9-84265e0a1836.png)
  
<span data-ttu-id="6eb36-197">Questa visualizzazione Mostra gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="6eb36-197">This view shows the following:</span></span>
  
- <span data-ttu-id="6eb36-198">**Rapporto Revisione-richiamo**: confronto dei risultati in base ai punteggi di rilevanza in una revisione ipotetica lineare.</span><span class="sxs-lookup"><span data-stu-id="6eb36-198">**Review-recall ratio**: Comparison of results according to Relevance scores in a hypothetically linear review.</span></span> <span data-ttu-id="6eb36-199">Il richiamo è stimato in base al set di dimensioni del set di revisione.</span><span class="sxs-lookup"><span data-stu-id="6eb36-199">Recall is estimated given the review set size set.</span></span>
    
- <span data-ttu-id="6eb36-200">**Parametri**: statistiche calcolate cumulative relative al set di riesame in relazione alla popolazione dei file per l'intero caso.</span><span class="sxs-lookup"><span data-stu-id="6eb36-200">**Parameters**: Cumulative calculated statistics pertaining to the review set in relation to the file population for the entire case.</span></span>
    
- <span data-ttu-id="6eb36-201">**Recensione**: percentuale di file da esaminare in base a questo cutoff.</span><span class="sxs-lookup"><span data-stu-id="6eb36-201">**Review**: Percentage of files to review based on this cutoff.</span></span>
    
- <span data-ttu-id="6eb36-202">**Richiamo**: percentuale dei file rilevanti nel set di revisione.</span><span class="sxs-lookup"><span data-stu-id="6eb36-202">**Recall**: Percentage of Relevant files in the review set.</span></span> 
    
- <span data-ttu-id="6eb36-203">**Distribuzione per Punteggio di pertinenza**: i file nel display grigio scuro a sinistra sono al di sotto del Punteggio di taglio.</span><span class="sxs-lookup"><span data-stu-id="6eb36-203">**Distribution by relevance score**: Files in the dark gray display to the left are below the cutoff score.</span></span> <span data-ttu-id="6eb36-204">Un suggerimento per gli strumenti Visualizza il Punteggio di pertinenza e la percentuale relativa di file nel set di file di revisione in relazione ai file totali.</span><span class="sxs-lookup"><span data-stu-id="6eb36-204">A tool-tip displays the Relevance score and the related percentage of files in the review file set in relation to the total files.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="6eb36-205">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6eb36-205">See also</span></span>

[<span data-ttu-id="6eb36-206">Advanced eDiscovery (classica)</span><span class="sxs-lookup"><span data-stu-id="6eb36-206">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="6eb36-207">Informazioni sulla valutazione in rilevanza</span><span class="sxs-lookup"><span data-stu-id="6eb36-207">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="6eb36-208">Esecuzione e revisione della valutazione</span><span class="sxs-lookup"><span data-stu-id="6eb36-208">Performing and reviewing Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="6eb36-209">Esecuzione della formazione sulla pertinenza</span><span class="sxs-lookup"><span data-stu-id="6eb36-209">Performing Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="6eb36-210">Prendere decisioni in base ai risultati</span><span class="sxs-lookup"><span data-stu-id="6eb36-210">Making decisions based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="6eb36-211">Verifica dell'analisi della pertinenza</span><span class="sxs-lookup"><span data-stu-id="6eb36-211">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

