---
title: Tenere traccia dell'analisi di rilevanza in Advanced eDiscovery
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
description: Informazioni su come visualizzare e interpretare lo stato di formazione per la pertinenza e i risultati per i problemi relativi ai casi in Advanced eDiscovery.
ms.openlocfilehash: 224337969b5e662d45c5b804fa5a0ee045f4fb84
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769181"
---
# <a name="track-relevance-analysis-in-advanced-ediscovery"></a><span data-ttu-id="7e17f-103">Tenere traccia dell'analisi di rilevanza in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="7e17f-103">Track Relevance analysis in Advanced eDiscovery</span></span>
  
<span data-ttu-id="7e17f-104">In Advanced eDiscovery, nella scheda Traccia di pertinenza viene visualizzata la validità calcolata del training di pertinenza eseguito nella scheda Tag e viene indicato il passaggio successivo da eseguire nel processo di formazione iterativa in Pertinenza.</span><span class="sxs-lookup"><span data-stu-id="7e17f-104">In Advanced eDiscovery, the Relevance Track tab displays the calculated validity of the Relevance training performed in the Tag tab and indicates the next step to take in the iterative training process in Relevance.</span></span> 
  
## <a name="tracking-relevance-training-status"></a><span data-ttu-id="7e17f-105">Monitoraggio dello stato di formazione per la pertinenza</span><span class="sxs-lookup"><span data-stu-id="7e17f-105">Tracking Relevance training status</span></span>

1. <span data-ttu-id="7e17f-106">Visualizzare i dettagli seguenti in Traccia di pertinenza per i problemi relativi ai casi, come illustrato nell'esempio seguente di una finestra di dialogo Nome **problema** riportata di seguito.</span><span class="sxs-lookup"><span data-stu-id="7e17f-106">View the following details in Relevance Track for the case issues, as shown in the following example of an **Issue name** dialog below.</span></span>

   - <span data-ttu-id="7e17f-107">**Valutazione**: questo indicatore di stato mostra in che misura il training di pertinenza eseguito fino a questo punto ha raggiunto l'obiettivo di valutazione in termini di margine di errore.</span><span class="sxs-lookup"><span data-stu-id="7e17f-107">**Assessment**: This progress indicator shows to what degree the Relevance training performed to this point has achieved the assessment target in terms of margin of error.</span></span> <span data-ttu-id="7e17f-108">Viene inoltre visualizzata la ricchezza dei risultati di formazione per la pertinenza.</span><span class="sxs-lookup"><span data-stu-id="7e17f-108">The richness of the Relevance training results is also displayed.</span></span>

   - <span data-ttu-id="7e17f-109">**Formazione:** questo indicatore di stato con codice a colori e la descrizione comando indicano la stabilità dei risultati del training per la pertinenza e una scala numerica che mostra il numero di esempi di formazione per la pertinenza contrassegnati per ogni problema.</span><span class="sxs-lookup"><span data-stu-id="7e17f-109">**Training**: This color-coded progress indicator and tool-tip indicates the Relevance training results stability and a numeric scale showing the number of Relevance training samples tagged for each issue.</span></span> <span data-ttu-id="7e17f-110">L'esperto monitora l'avanzamento del processo iterativo di formazione sulla rilevanza.</span><span class="sxs-lookup"><span data-stu-id="7e17f-110">The expert monitors the progress of the iterative Relevance training process.</span></span> 
  
   - <span data-ttu-id="7e17f-111">**Calcolo batch:** questo indicatore di stato fornisce informazioni sul completamento del calcolo batch.</span><span class="sxs-lookup"><span data-stu-id="7e17f-111">**Batch calculation**: This progress indicator provides information about the completion of Batch calculation.</span></span>
  
   - <span data-ttu-id="7e17f-112">**Passaggio successivo**: visualizza il suggerimento per il passaggio successivo da eseguire.</span><span class="sxs-lookup"><span data-stu-id="7e17f-112">**Next step**: Displays the recommendation for the next step to be performed.</span></span> 
  
    <span data-ttu-id="7e17f-113">Nell'esempio viene visualizzata una valutazione completata correttamente per un problema, indicata dall'indicatore di stato del colore completato e dal segno di spunta.</span><span class="sxs-lookup"><span data-stu-id="7e17f-113">In the example, a successfully completed Assessment for an issue is shown, indicated by the completed color progress indicator and the checkmark.</span></span> <span data-ttu-id="7e17f-114">È in corso il tagging, ma il caso è ancora considerato instabile (lo stato di stabilità viene visualizzato anche in una descrizione comando).</span><span class="sxs-lookup"><span data-stu-id="7e17f-114">Tagging is underway, but the case is still considered unstable (stability status also shown in a tool-tip).</span></span> <span data-ttu-id="7e17f-115">Il passaggio successivo è "Training".</span><span class="sxs-lookup"><span data-stu-id="7e17f-115">The next step recommendation is "Training".</span></span> 
  
    ![Fase 1 del corso di formazione sulla traccia di pertinenza](../media/a00fe607-680a-48eb-9d61-4565319f7ab6.png)
  
    <span data-ttu-id="7e17f-117">La visualizzazione espansa visualizza informazioni e opzioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="7e17f-117">The expanded view displays additional information and options.</span></span> <span data-ttu-id="7e17f-118">Il margine di errore corrente visualizzato è il margine di errore del richiamo nello stato corrente di valutazione, dati i file di valutazione esistenti (già contrassegnati).</span><span class="sxs-lookup"><span data-stu-id="7e17f-118">The displayed current error margin is the error margin of the recall in the current state of assessment, given the existing (already tagged) assessment files.</span></span>
  
    > [!NOTE]
    >  <span data-ttu-id="7e17f-119">La fase di valutazione può essere ignorata deselezionando la casella **di** controllo Valutazione per ogni problema e quindi per "tutti i problemi".</span><span class="sxs-lookup"><span data-stu-id="7e17f-119">The Assessment stage can be bypassed by clearing the **Assessment** check box per issue and then for "all issues".</span></span> <span data-ttu-id="7e17f-120">Tuttavia, di conseguenza, non ci saranno statistiche per questo problema.</span><span class="sxs-lookup"><span data-stu-id="7e17f-120">However, as a result, there will be no statistics for this issue.</span></span> <span data-ttu-id="7e17f-121">> la casella di controllo **Valutazione** può essere eseguita solo prima dell'esecuzione della valutazione.</span><span class="sxs-lookup"><span data-stu-id="7e17f-121">> Clearing the **Assessment** check box can only be done before assessment is performed.</span></span> <span data-ttu-id="7e17f-122">Se in un caso esistono più problemi, la valutazione viene ignorata solo se la casella di controllo è deselezionata per ogni problema</span><span class="sxs-lookup"><span data-stu-id="7e17f-122">Where multiple issues exist in a case, assessment is bypassed only if the check box is cleared for each issue</span></span> 
  
    <span data-ttu-id="7e17f-123">Quando la valutazione non viene completata con il primo set di file di esempio, la valutazione potrebbe essere il passaggio successivo per contrassegnare più file.</span><span class="sxs-lookup"><span data-stu-id="7e17f-123">When assessment is not completed with the first sample set of files, assessment might be the next step for tagging more files.</span></span>
  
    <span data-ttu-id="7e17f-124">In **Traccia di rilevanza,** l'indicatore di avanzamento del training e la descrizione comando indicano il numero stimato di campioni aggiuntivi necessari per \> raggiungere la stabilità.</span><span class="sxs-lookup"><span data-stu-id="7e17f-124">In **Relevance** \> **Track**, the training progress indicator and tool-tip indicate the estimated number of additional samples needed to reach stability.</span></span> <span data-ttu-id="7e17f-125">Questa stima fornisce una linea guida per la formazione aggiuntiva necessaria.</span><span class="sxs-lookup"><span data-stu-id="7e17f-125">This estimate provides a guideline for the additional training needed.</span></span>
  
    ![Corso di formazione sulla traccia di pertinenza](../media/98dbc3f5-5238-4d73-9f88-1aa4d77ea729.png)
  
2. <span data-ttu-id="7e17f-127">Al termine del tagging e se è necessario continuare la formazione, fare clic su **Formazione**.</span><span class="sxs-lookup"><span data-stu-id="7e17f-127">When you're done tagging and if you need to continue training, click **Training**.</span></span> <span data-ttu-id="7e17f-128">Un altro set di file di esempio viene generato dal set di file caricato per ulteriore formazione.</span><span class="sxs-lookup"><span data-stu-id="7e17f-128">Another sample set of files is generated from the loaded file set for additional training.</span></span> <span data-ttu-id="7e17f-129">Viene quindi restituita la scheda Tag per contrassegnare e formare altri file.</span><span class="sxs-lookup"><span data-stu-id="7e17f-129">You are then returned to the Tag tab to tag and train more files.</span></span>

### <a name="reaching-stable-training-levels"></a><span data-ttu-id="7e17f-130">Raggiungere livelli di formazione stabili</span><span class="sxs-lookup"><span data-stu-id="7e17f-130">Reaching stable training levels</span></span>

<span data-ttu-id="7e17f-131">Dopo che i file di valutazione hanno raggiunto un livello stabile di formazione, Advanced eDiscovery è pronto per il calcolo batch.</span><span class="sxs-lookup"><span data-stu-id="7e17f-131">After the assessment files have attained a stable level of training, Advanced eDiscovery is ready for Batch calculation.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7e17f-132">In genere, dopo tre campioni di formazione stabili, il passaggio successivo è "Calcolo batch".</span><span class="sxs-lookup"><span data-stu-id="7e17f-132">Usually, after three stable training samples, the next step is "Batch calculation".</span></span> <span data-ttu-id="7e17f-133">Possono esserci eccezioni, ad esempio, quando sono state apportate modifiche al tagging dei file di esempi precedenti o quando sono stati aggiunti file di seeding.</span><span class="sxs-lookup"><span data-stu-id="7e17f-133">There may be exceptions, for example, when there were changes to the tagging of files from earlier samples or when seed files were added.</span></span> 
  
### <a name="performing-batch-calculation"></a><span data-ttu-id="7e17f-134">Esecuzione del calcolo batch</span><span class="sxs-lookup"><span data-stu-id="7e17f-134">Performing Batch calculation</span></span>

<span data-ttu-id="7e17f-135">Il calcolo batch viene eseguito come passaggio successivo dopo il completamento dell'addestramento (quando viene visualizzato uno stato di formazione stabile dall'indicatore di stato, un segno di spunta e uno stato stabile nella descrizione comando). Il calcolo batch applica le conoscenze acquisite durante la formazione sulla pertinenza all'intera popolazione di file, per valutare la pertinenza dei file e per assegnare i punteggi di pertinenza.</span><span class="sxs-lookup"><span data-stu-id="7e17f-135">Batch calculation is executed as the next step after training is successfully completed (when a stable training status is shown by the progress bar, a checkmark and stable status in the tool-tip.) Batch calculation applies the knowledge acquired during the Relevance training to the entire file population, to assess the files' relevance and to assign Relevance scores.</span></span>
  
<span data-ttu-id="7e17f-136">Quando è presente più di un problema, il calcolo batch viene eseguito per ogni problema.</span><span class="sxs-lookup"><span data-stu-id="7e17f-136">When there is more than one issue, Batch calculation is done per issue.</span></span> <span data-ttu-id="7e17f-137">Durante il calcolo batch, l'avanzamento viene monitorato durante l'elaborazione di tutti i file.</span><span class="sxs-lookup"><span data-stu-id="7e17f-137">During Batch calculation, progress is monitored while processing all of the files.</span></span> 
  
<span data-ttu-id="7e17f-138">In questo caso, il passaggio successivo consigliato è "None", che indica che non è necessario un ulteriore training iterativo per la pertinenza a questo punto.</span><span class="sxs-lookup"><span data-stu-id="7e17f-138">Here, the recommended next step is "None", which indicates that no additional iterative Relevance training is required at this point.</span></span> <span data-ttu-id="7e17f-139">La fase successiva è la **scheda \> Pertinenza Decidi.**</span><span class="sxs-lookup"><span data-stu-id="7e17f-139">The next phase is the **Relevance \> Decide** tab.</span></span> 
  
<span data-ttu-id="7e17f-140">Se si desidera importare nuovi file dopo il calcolo batch, l'amministratore può aggiungere i file importati a un nuovo carico.</span><span class="sxs-lookup"><span data-stu-id="7e17f-140">If you want to import new files after Batch calculation, the administrator can add the imported files to a new load.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7e17f-141">Se si fa **clic su Annulla** durante il calcolo batch, il processo salva ciò che è già stato eseguito.</span><span class="sxs-lookup"><span data-stu-id="7e17f-141">If you click **Cancel** during Batch calculation, the process saves what was already executed.</span></span> <span data-ttu-id="7e17f-142">Se si esegue di nuovo il calcolo batch, il processo continuerà dall'ultimo punto eseguito.</span><span class="sxs-lookup"><span data-stu-id="7e17f-142">If you run Batch calculation again, the process will continue from the last executed point.</span></span> 
  
### <a name="assessing-tagging-consistency"></a><span data-ttu-id="7e17f-143">Valutazione della coerenza dei tag</span><span class="sxs-lookup"><span data-stu-id="7e17f-143">Assessing tagging consistency</span></span>

<span data-ttu-id="7e17f-144">Se sono presenti incoerenze nel tagging dei file, può influire sull'analisi.</span><span class="sxs-lookup"><span data-stu-id="7e17f-144">If there are inconsistencies in file tagging, it can affect the analysis.</span></span> <span data-ttu-id="7e17f-145">Il Advanced eDiscovery di coerenza dei tag può essere utilizzato quando i risultati non sono ottimali o se la coerenza è in dubbio.</span><span class="sxs-lookup"><span data-stu-id="7e17f-145">The Advanced eDiscovery tagging consistency process can be used when results are not optimal or consistency is in doubt.</span></span> <span data-ttu-id="7e17f-146">Viene restituito un elenco dei possibili file contrassegnati in modo incoerente e possono essere esaminati e ritantati, se necessario.</span><span class="sxs-lookup"><span data-stu-id="7e17f-146">A list of possible inconsistently tagged files is returned, and they can be reviewed and retagged, as necessary.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7e17f-147">Dopo sette o più round di formazione dopo la valutazione, la coerenza dei tag può essere visualizzata in **Pertinenza** \> **Track** \> **Issue** \> **Detailed results** Training \> **progress**.</span><span class="sxs-lookup"><span data-stu-id="7e17f-147">After seven or more training rounds following assessment, tagging consistency can be viewed in **Relevance** \> **Track** \> **Issue** \> **Detailed results** \> **Training progress**.</span></span> <span data-ttu-id="7e17f-148">Questa revisione viene eseguita per un problema alla volta.</span><span class="sxs-lookup"><span data-stu-id="7e17f-148">This review is done for one issue at a time.</span></span>
  
1. <span data-ttu-id="7e17f-149">In **Traccia di \> pertinenza** espandere la riga di un problema.</span><span class="sxs-lookup"><span data-stu-id="7e17f-149">In **Relevance \> Track**, expand an issue's row.</span></span>
  
2. <span data-ttu-id="7e17f-150">A destra di **Passaggio successivo** fare clic su **Modifica.**</span><span class="sxs-lookup"><span data-stu-id="7e17f-150">To the right of **Next step**, click **Modify**.</span></span>
  
3. <span data-ttu-id="7e17f-151">Seleziona **Tag incoerenze** come opzione Passaggio **successivo,** dopo sette esempi di formazione e fai clic su **OK.**</span><span class="sxs-lookup"><span data-stu-id="7e17f-151">Select **Tag inconsistencies** as the **Next step** option, after seven training samples and click **OK**.</span></span>
  
4. <span data-ttu-id="7e17f-152">Selezionare **Incoerenze tag.**</span><span class="sxs-lookup"><span data-stu-id="7e17f-152">Select **Tag inconsistencies**.</span></span> <span data-ttu-id="7e17f-153">Verrà **visualizzata** la scheda Tag con un elenco delle incoerenze da ritagare in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="7e17f-153">The **Tag** tab opens displaying a list of the inconsistencies to retag as necessary.</span></span>
  
5. <span data-ttu-id="7e17f-154">Fare **clic su** Calcola per inviare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="7e17f-154">Click **Calculate** to submit the changes.</span></span> <span data-ttu-id="7e17f-155">Il passaggio successivo dopo l'applicazione di tag alle incoerenze è "Formazione".</span><span class="sxs-lookup"><span data-stu-id="7e17f-155">The next step after tagging inconsistencies is "Training".</span></span> 
  
## <a name="viewing-and-using-relevance-results"></a><span data-ttu-id="7e17f-156">Visualizzazione e utilizzo dei risultati di pertinenza</span><span class="sxs-lookup"><span data-stu-id="7e17f-156">Viewing and using Relevance results</span></span>

<span data-ttu-id="7e17f-157">Nella scheda **Traccia di \> pertinenza** espandere la riga di un problema e accanto a **Risultati dettagliati** fare clic su **Visualizza.**</span><span class="sxs-lookup"><span data-stu-id="7e17f-157">In the **Relevance \> Track** tab, expand an issue's row, and next to **Detailed results**, click **View**.</span></span> <span data-ttu-id="7e17f-158">Vengono visualizzati i riquadri dei risultati dettagliati, come illustrato e descritto di seguito.</span><span class="sxs-lookup"><span data-stu-id="7e17f-158">The Detailed results panes are displayed, as shown and described below.</span></span>
  
![Risultati dettagliati della formazione sulla pertinenza](../media/495c04a9-ed1e-4355-8cab-c14270ca2bbb.png)
  
### <a name="tagging-summary"></a><span data-ttu-id="7e17f-160">Riepilogo tagging</span><span class="sxs-lookup"><span data-stu-id="7e17f-160">Tagging summary</span></span>

 <span data-ttu-id="7e17f-161">Nell'esempio riportato di seguito, nel riepilogo **tagging** vengono visualizzati i totali per ogni processo di tagging dei file di valutazione, formazione e di ripristino.</span><span class="sxs-lookup"><span data-stu-id="7e17f-161">In the example shown below, the **Tagging summary** displays totals for each of Assessment, Training, and Catch-up file tagging processes.</span></span>
  
![Riepilogo tagging della traccia di pertinenza](../media/0ec906fc-bc84-4245-a964-fb3ca37891db.png)
  
### <a name="keywords"></a><span data-ttu-id="7e17f-163">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e17f-163">Keywords</span></span>

<span data-ttu-id="7e17f-164">Una parola chiave è una stringa univoca, una parola, una frase o una sequenza di parole in un file identificato da Advanced eDiscovery come indicatore significativo dell'eventuale pertinente di un file.</span><span class="sxs-lookup"><span data-stu-id="7e17f-164">A keyword is a unique string, word, phrase, or sequence of words in a file identified by Advanced eDiscovery as a significant indicator of whether a file is relevant.</span></span> <span data-ttu-id="7e17f-165">La parola chiave dell'elenco di colonne "Includi" e i pesi nei file contrassegnati come rilevanti e le colonne "Escludi" elencano parole chiave e pesi nei file contrassegnati come Non rilevante.</span><span class="sxs-lookup"><span data-stu-id="7e17f-165">The "Include" columns list keyword and weights in files tagged as Relevant, and the "Exclude" columns lists keywords and weights in files tagged as Not relevant.</span></span>
  
<span data-ttu-id="7e17f-166">Advanced eDiscovery assegna valori negativi o positivi del peso delle parole chiave.</span><span class="sxs-lookup"><span data-stu-id="7e17f-166">Advanced eDiscovery assigns negative or positive keyword weight values.</span></span> <span data-ttu-id="7e17f-167">Maggiore è il peso, maggiore è la probabilità che a un file in cui viene visualizzata la parola chiave venga assegnato un punteggio di rilevanza più alto durante il calcolo batch.</span><span class="sxs-lookup"><span data-stu-id="7e17f-167">The higher the weight, the higher the likelihood that a file in which the keyword appears is assigned a higher Relevance score during Batch calculation.</span></span>
  
<span data-ttu-id="7e17f-168">L Advanced eDiscovery di parole chiave può essere usato per integrare un elenco creato da un esperto o come controllo di sanità mentale indiretta in qualsiasi momento del processo di revisione dei file.</span><span class="sxs-lookup"><span data-stu-id="7e17f-168">The Advanced eDiscovery list of keywords can be used to supplement a list built by an expert or as an indirect sanity check at any point in the file review process.</span></span>
  
### <a name="training-progress"></a><span data-ttu-id="7e17f-169">Avanzamento della formazione</span><span class="sxs-lookup"><span data-stu-id="7e17f-169">Training progress</span></span>

<span data-ttu-id="7e17f-170">Il **riquadro Avanzamento formazione** include un grafico sullo stato di avanzamento del training e la visualizzazione dell'indicatore di qualità, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="7e17f-170">The **Training Progress** pane includes a training progress graph and quality indicator display, as shown in the example below.</span></span>
  
![Stato di avanzamento del corso di formazione sulla traccia di pertinenza](../media/8a5089f5-a162-4246-ae09-bc1921859860.png)
  
<span data-ttu-id="7e17f-172">**Indicatore qualità formazione**: Visualizza la classificazione della coerenza di tagging nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="7e17f-172">**Training quality indicator**: Displays the rating of the tagging consistency as follows:</span></span>
  
- <span data-ttu-id="7e17f-173">**Buona:** i file sono contrassegnati in modo coerente.</span><span class="sxs-lookup"><span data-stu-id="7e17f-173">**Good**: Files are tagged consistently.</span></span> <span data-ttu-id="7e17f-174">(Luce verde visualizzata)</span><span class="sxs-lookup"><span data-stu-id="7e17f-174">(Green light displayed)</span></span>
  
- <span data-ttu-id="7e17f-175">**Medio:** alcuni file potrebbero essere contrassegnati in modo incoerente.</span><span class="sxs-lookup"><span data-stu-id="7e17f-175">**Medium**: Some files may be tagged inconsistently.</span></span> <span data-ttu-id="7e17f-176">(Luce gialla visualizzata)</span><span class="sxs-lookup"><span data-stu-id="7e17f-176">(Yellow light displayed)</span></span>

- <span data-ttu-id="7e17f-177">**Avviso:** molti file potrebbero essere contrassegnati in modo incoerente.</span><span class="sxs-lookup"><span data-stu-id="7e17f-177">**Warning**: Many files may be tagged inconsistently.</span></span> <span data-ttu-id="7e17f-178">(Luce rossa visualizzata)</span><span class="sxs-lookup"><span data-stu-id="7e17f-178">(Red light displayed)</span></span>

<span data-ttu-id="7e17f-179">**Grafico dello stato di** avanzamento della formazione : mostra il grado di stabilità del training di rilevanza dopo molti cicli di formazione per la pertinenza rispetto al valore di misurazione F.</span><span class="sxs-lookup"><span data-stu-id="7e17f-179">**Training progress graph**: Shows the degree of Relevance training stability after many Relevance training cycles in comparison to the F-measure value.</span></span> <span data-ttu-id="7e17f-180">Quando ci spostiamo da sinistra a destra nel grafico, l'intervallo di confidenza si restringe e viene usato, insieme alla misura F, da Advanced eDiscovery Relevance per determinare la stabilità quando i risultati del training per la pertinenza sono ottimizzati.</span><span class="sxs-lookup"><span data-stu-id="7e17f-180">As we move from the left to the right across the graph, the confidence interval narrows and is used, along with the F-measure, by Advanced eDiscovery Relevance to determine stability when the Relevance training results are optimized.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7e17f-181">Per la pertinenza viene utilizzato F2, una metrica di misurazione F in cui il richiamo riceve il doppio del peso della precisione.</span><span class="sxs-lookup"><span data-stu-id="7e17f-181">Relevance uses F2, an F-measure metric where Recall receives twice as much weight as Precision.</span></span> <span data-ttu-id="7e17f-182">Per i casi di elevata ricchezza (oltre il 25%), per rilevanza viene utilizzato F1 (rapporto 1:1).</span><span class="sxs-lookup"><span data-stu-id="7e17f-182">For cases with high richness (over 25%), Relevance uses F1 (1:1 ratio).</span></span> <span data-ttu-id="7e17f-183">Il rapporto di misurazione F può essere configurato in **Configurazione per pertinenza** \> **Impostazioni avanzate.**</span><span class="sxs-lookup"><span data-stu-id="7e17f-183">The F-measure ratio can be configured in **Relevance setup** \> **Advanced settings**.</span></span>
  
### <a name="batch-calculation-results"></a><span data-ttu-id="7e17f-184">Risultati del calcolo batch</span><span class="sxs-lookup"><span data-stu-id="7e17f-184">Batch calculation results</span></span>

<span data-ttu-id="7e17f-185">Il **riquadro Risultati calcolo batch** include il numero di file con punteggio per Rilevanza, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="7e17f-185">The **Batch calculation results** pane includes the number of files that were scored for Relevance, as follows:</span></span> 
  
- <span data-ttu-id="7e17f-186">**Esito positivo**</span><span class="sxs-lookup"><span data-stu-id="7e17f-186">**Success**</span></span>
  
- <span data-ttu-id="7e17f-187">**Vuoto**: non contiene testo, ad esempio solo spazi/tabulazioni</span><span class="sxs-lookup"><span data-stu-id="7e17f-187">**Empty**: Contains no text, for example, only spaces/tabs</span></span>
  
- <span data-ttu-id="7e17f-188">**Failed**: A causa di dimensioni eccessive o non è stato possibile leggere</span><span class="sxs-lookup"><span data-stu-id="7e17f-188">**Failed**: Due to excessive size or could not be read</span></span>
  
- <span data-ttu-id="7e17f-189">**Ignorato:** a causa di dimensioni eccessive</span><span class="sxs-lookup"><span data-stu-id="7e17f-189">**Ignored**: Due to excessive size</span></span>
  
- <span data-ttu-id="7e17f-190">**Nebuloso:** contiene testo senza significato o nessuna funzionalità rilevante per il problema</span><span class="sxs-lookup"><span data-stu-id="7e17f-190">**Nebulous**: Contains meaningless text or no features relevant to the issue</span></span>
  
> [!NOTE]
> <span data-ttu-id="7e17f-191">Vuoto, Non riuscito, Ignorato o Nebuloso riceverà un punteggio di pertinenza pari a -1.</span><span class="sxs-lookup"><span data-stu-id="7e17f-191">Empty, Failed, Ignored, or Nebulous will receive a Relevance score of -1.</span></span>
  
### <a name="training-statistics"></a><span data-ttu-id="7e17f-192">Statistiche di formazione</span><span class="sxs-lookup"><span data-stu-id="7e17f-192">Training statistics</span></span>

<span data-ttu-id="7e17f-193">Nel **riquadro Statistiche formazione** vengono visualizzate statistiche e grafici in base ai risultati Advanced eDiscovery formazione sulla pertinenza.</span><span class="sxs-lookup"><span data-stu-id="7e17f-193">The **Training statistics** pane displays statistics and graphs based on results from Advanced eDiscovery Relevance training.</span></span> 
  
![Statistiche del corso di formazione sulla traccia di pertinenza](../media/9a07740e-20d3-49fb-b9b9-84265e0a1836.png)
  
<span data-ttu-id="7e17f-195">Questa visualizzazione mostra quanto segue:</span><span class="sxs-lookup"><span data-stu-id="7e17f-195">This view shows the following:</span></span>
  
- <span data-ttu-id="7e17f-196">**Rapporto revisione-richiamo**: confronto dei risultati in base ai punteggi di pertinenza in una revisione ipoteticamente lineare.</span><span class="sxs-lookup"><span data-stu-id="7e17f-196">**Review-recall ratio**: Comparison of results according to Relevance scores in a hypothetically linear review.</span></span> <span data-ttu-id="7e17f-197">Il richiamo viene stimato in base al set di dimensioni impostato per la revisione.</span><span class="sxs-lookup"><span data-stu-id="7e17f-197">Recall is estimated given the review set size set.</span></span>
  
- <span data-ttu-id="7e17f-198">**Parametri**: statistiche calcolate cumulative relative al set di revisione in relazione alla popolazione di file per l'intero caso.</span><span class="sxs-lookup"><span data-stu-id="7e17f-198">**Parameters**: Cumulative calculated statistics pertaining to the review set in relation to the file population for the entire case.</span></span>
  
- <span data-ttu-id="7e17f-199">**Review:** percentuale di file da esaminare in base a questo limite.</span><span class="sxs-lookup"><span data-stu-id="7e17f-199">**Review**: Percentage of files to review based on this cutoff.</span></span>
  
- <span data-ttu-id="7e17f-200">**Richiamo:** percentuale di file rilevanti nel set di revisioni.</span><span class="sxs-lookup"><span data-stu-id="7e17f-200">**Recall**: Percentage of Relevant files in the review set.</span></span> 
  
- <span data-ttu-id="7e17f-201">**Distribuzione in base al punteggio di pertinenza**: i file nella visualizzazione grigio scuro a sinistra sono al di sotto del punteggio di pertinenza.</span><span class="sxs-lookup"><span data-stu-id="7e17f-201">**Distribution by relevance score**: Files in the dark gray display to the left are below the cutoff score.</span></span> <span data-ttu-id="7e17f-202">Una descrizione comando visualizza il punteggio di pertinenza e la percentuale correlata di file nel set di file di revisione in relazione al totale dei file.</span><span class="sxs-lookup"><span data-stu-id="7e17f-202">A tool-tip displays the Relevance score and the related percentage of files in the review file set in relation to the total files.</span></span>
