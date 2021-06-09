---
title: Tagging e valutazione in Advanced eDiscovery
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
ms.assetid: b5c82de7-ed2f-4cc6-becd-db403faf4d18
ROBOTS: NOINDEX, NOFOLLOW
description: Esaminare i passaggi per eseguire la formazione sulla valutazione, inclusi i file di tagging, e rivedere i risultati della valutazione in Advanced eDiscovery.
ms.openlocfilehash: 15bc8254ea1589d9afa17a74eaf3bfbcdfd4bba0
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769191"
---
# <a name="tagging-and-assessment-in-the-relevance-module-in-advanced-ediscovery"></a><span data-ttu-id="15ab4-103">Tagging e valutazione nel modulo Pertinenza in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="15ab4-103">Tagging and Assessment in the Relevance module in Advanced eDiscovery</span></span>
  
<span data-ttu-id="15ab4-104">In questa sezione viene descritta la procedura per la valutazione nel modulo Pertinenza in Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="15ab4-104">This section describes the procedure for Assessment in the Relevance module in Advanced eDiscovery.</span></span>
  
## <a name="performing-assessment-training-and-analysis"></a><span data-ttu-id="15ab4-105">Esecuzione della formazione e dell'analisi di valutazione</span><span class="sxs-lookup"><span data-stu-id="15ab4-105">Performing Assessment training and analysis</span></span>

1. <span data-ttu-id="15ab4-106">Nella scheda **Traccia di \> pertinenza** fare clic su **Valutazione** per avviare la valutazione del caso.</span><span class="sxs-lookup"><span data-stu-id="15ab4-106">In the **Relevance \> Track** tab, click **Assessment** to start case assessment.</span></span>

    <span data-ttu-id="15ab4-107">Ad esempio, in questa procedura viene creato un set di valutazione di esempio di 500 file e viene visualizzata la scheda **Tag,** che contiene il pannello Tagging, il contenuto dei file visualizzati e altre opzioni di tagging.</span><span class="sxs-lookup"><span data-stu-id="15ab4-107">For example purposes in this procedure, a sample assessment set of 500 files is created and the **Tag** tab is displayed, which contains the Tagging panel, displayed file content and other tagging options.</span></span> 

    ![Scheda Tag pertinenza per la valutazione](../media/c8acf891-b1cd-4344-816c-eabb8cbbe742.png)
  
2. <span data-ttu-id="15ab4-109">Esaminare ogni file nell'esempio, determinare la pertinenza del file per ogni problema relativo al caso e contrassegnare il file con i pulsanti Pertinenza (R), Non rilevante (NR) e Ignora nel riquadro del pannello **Tagging.**</span><span class="sxs-lookup"><span data-stu-id="15ab4-109">Review each file in the sample, determine the file's relevance for each case issue, and tag the file using the Relevance (R), Not relevant (NR) and Skip buttons in the **Tagging panel** pane.</span></span> 

    > [!NOTE]
    >  <span data-ttu-id="15ab4-110">La valutazione richiede 500 file con tag.</span><span class="sxs-lookup"><span data-stu-id="15ab4-110">Assessment requires 500 tagged files.</span></span> <span data-ttu-id="15ab4-111">Se i file vengono "ignorati", riceverai più file da contrassegnare.</span><span class="sxs-lookup"><span data-stu-id="15ab4-111">If files are "skipped", you will receive more files to tag.</span></span> 
  
3. <span data-ttu-id="15ab4-112">Dopo aver taggato tutti i file nell'esempio, fare clic su **Calcola**.</span><span class="sxs-lookup"><span data-stu-id="15ab4-112">After tagging all files in the sample, click **Calculate**.</span></span>

    <span data-ttu-id="15ab4-113">Il margine di errore corrente di valutazione e la ricchezza vengono calcolati e visualizzati nella scheda **Traccia** di pertinenza, con dettagli espansi per problema, come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="15ab4-113">The Assessment current error margin and richness are calculated and displayed in the **Relevance Track** tab, with expanded details per issue, as shown below.</span></span> <span data-ttu-id="15ab4-114">Ulteriori dettagli su questa finestra di dialogo sono descritti nella sezione [Revisione dei risultati della](#reviewing-assessment-results) valutazione.</span><span class="sxs-lookup"><span data-stu-id="15ab4-114">More details about this dialog are described in the [Reviewing assessment results](#reviewing-assessment-results) section.</span></span>

    ![Traccia di pertinenza: valutazione](../media/da911ba5-8678-40d6-9ad5-fd0b058355c1.png)
  
    > [!TIP]
    > <span data-ttu-id="15ab4-116">Per impostazione predefinita, è consigliabile passare al passaggio successivo predefinito al termine dell'indicatore di stato della valutazione per il problema, a indicare che l'esempio di valutazione è stato esaminato e che sono stati contrassegnati file pertinenti sufficienti.</span><span class="sxs-lookup"><span data-stu-id="15ab4-116">By default, we recommend that you proceed to the default Next step when the Assessment progress indicator for the issue has completed, indicating that the assessment sample was reviewed and sufficient relevant files were tagged.</span></span> <span data-ttu-id="15ab4-117">> In caso contrario, se si  desidera visualizzare i risultati della scheda Traccia  e controllare il margine di errore e il passaggio successivo, fare clic su Modifica accanto a Passaggio **successivo,** selezionare **Continua** valutazione e quindi fare clic su **OK.**</span><span class="sxs-lookup"><span data-stu-id="15ab4-117">> Otherwise, if you want to view the **Track** tab results and control the margin of error and the next step, click **Modify** adjacent to **Next Step**, select **Continue assessment**, and then click **OK**.</span></span>
  
4. <span data-ttu-id="15ab4-118">Fare **clic su** Modifica a destra della casella **di** controllo Valutazione per visualizzare e specificare i parametri di valutazione per problema.</span><span class="sxs-lookup"><span data-stu-id="15ab4-118">Click **Modify** to the right of the **Assessment** check box to view and specify assessment parameters per issue.</span></span> <span data-ttu-id="15ab4-119">Viene **visualizzata una** finestra di dialogo a livello di valutazione per ogni problema, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="15ab4-119">An **Assessment level** dialog for each issue is displayed, as shown in the following example:</span></span> 

    ![Problema relativo al livello di valutazione per il caso](../media/b7113fef-d125-4617-ae1b-c9eb0bf79aec.png)
  
    <span data-ttu-id="15ab4-121">I parametri seguenti per il problema vengono calcolati e visualizzati nella finestra **di dialogo Livello di** valutazione:</span><span class="sxs-lookup"><span data-stu-id="15ab4-121">The following parameters for the issue are calculated and displayed in the **Assessment level** dialog:</span></span> 

    <span data-ttu-id="15ab4-122">**Margine di errore di destinazione per le** stime di richiamo: in base a questo valore, viene calcolato il numero stimato di file aggiuntivi necessari per la revisione.</span><span class="sxs-lookup"><span data-stu-id="15ab4-122">**Target error margin for recall estimates**: Based on this value, the estimated number of additional files necessary to review is calculated.</span></span> <span data-ttu-id="15ab4-123">Il margine utilizzato per il richiamo è superiore al 75% e con un livello di probabilità del 95%.</span><span class="sxs-lookup"><span data-stu-id="15ab4-123">The margin used for recall is greater than 75% and with a 95% confidence level.</span></span>

    <span data-ttu-id="15ab4-124">**File di valutazione aggiuntivi necessari:** indica quanti altri file sono necessari se non sono stati soddisfatti i requisiti del margine di errore corrente.</span><span class="sxs-lookup"><span data-stu-id="15ab4-124">**Additional assessment files required**: Indicates how many more files are necessary if the current error margin's requirements have not been met.</span></span> 

5. <span data-ttu-id="15ab4-125">Per regolare il margine di errore corrente e vedere l'effetto di margini di errore diversi (per problema):</span><span class="sxs-lookup"><span data-stu-id="15ab4-125">To adjust the current error margin and see the effect of different error margins (per issue):</span></span>

6. <span data-ttu-id="15ab4-126">**Nell'elenco Seleziona problema** selezionare un problema.</span><span class="sxs-lookup"><span data-stu-id="15ab4-126">In the **Select issue** list, select an issue.</span></span> 

7. <span data-ttu-id="15ab4-127">In **Margine di errore di destinazione per le stime di richiamo** immettere un nuovo valore.</span><span class="sxs-lookup"><span data-stu-id="15ab4-127">In **Target error margin for recall estimates**, enter a new value.</span></span>

8. <span data-ttu-id="15ab4-128">Fare **clic su Aggiorna** valori per visualizzare l'impatto delle rettifiche.</span><span class="sxs-lookup"><span data-stu-id="15ab4-128">Click **Update values** to see the impact of the adjustments.</span></span> 

9. <span data-ttu-id="15ab4-129">Fare **clic su** Avanzate nella finestra di **dialogo** Livello di valutazione per visualizzare i seguenti parametri e dettagli aggiuntivi:</span><span class="sxs-lookup"><span data-stu-id="15ab4-129">Click **Advanced** in the **Assessment level** dialog to see the following additional parameters and details:</span></span> 

    ![Visualizzazione avanzata dei problemi relativi al livello di valutazione per il caso](../media/577d7e0e-95df-48c2-9dec-bdeab5e801d8.png)
  
    - <span data-ttu-id="15ab4-131">**Richness stimata**: ricchezza stimata in base ai risultati della valutazione corrente</span><span class="sxs-lookup"><span data-stu-id="15ab4-131">**Estimated richness**: Estimated richness according to the current assessment results</span></span>

    - <span data-ttu-id="15ab4-132">**Per il richiamo presunto:** per impostazione predefinita, il margine di errore di destinazione si applica al richiamo superiore al 75%.</span><span class="sxs-lookup"><span data-stu-id="15ab4-132">**For assumed recall**: By default, the target error margin applies to recall above 75%.</span></span> <span data-ttu-id="15ab4-133">Fare **clic su** Modifica se si desidera modificare questo parametro e controllare il margine di errore in un intervallo diverso di valori di richiamo.</span><span class="sxs-lookup"><span data-stu-id="15ab4-133">Click **Edit** if you want to change this parameter and control the margin of error on a different range of recall values.</span></span> 

    - <span data-ttu-id="15ab4-134">**Livello di probabilità**: per impostazione predefinita, il margine di errore consigliato per la probabilità è 95%.</span><span class="sxs-lookup"><span data-stu-id="15ab4-134">**Confidence level**: By default, the recommended error margin for confidence is 95%.</span></span> <span data-ttu-id="15ab4-135">Fare **clic su** Modifica se si desidera modificare questo parametro.</span><span class="sxs-lookup"><span data-stu-id="15ab4-135">Click **Edit** if you want to change this parameter.</span></span>

    - <span data-ttu-id="15ab4-136">**Margine di errore di richness previsto:** dati i valori aggiornati, questo è il margine di errore previsto della ricchezza, dopo la revisione di tutti i file di valutazione aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="15ab4-136">**Expected richness error margin**: Given the updated values, this is the expected margin of error of the richness, after all additional assessment files are reviewed.</span></span>

    - <span data-ttu-id="15ab4-137">**File di valutazione aggiuntivi necessari:** dati i valori aggiornati, il numero di file di valutazione aggiuntivi che devono essere esaminati per raggiungere l'obiettivo.</span><span class="sxs-lookup"><span data-stu-id="15ab4-137">**Additional assessment files required**: Given the updated values, the number of additional assessment files that need to be reviewed to reach the target.</span></span>

    - <span data-ttu-id="15ab4-138">**Totale file di valutazione necessari:** dati i valori aggiornati, i file di valutazione totali necessari per la revisione.</span><span class="sxs-lookup"><span data-stu-id="15ab4-138">**Total assessment files required**: Given the updated values, total assessment files required for review.</span></span>

    - <span data-ttu-id="15ab4-139">**Numero previsto di file pertinenti nella** valutazione: dati i valori aggiornati, il numero previsto di file pertinenti nell'intera valutazione dopo la revisione di tutti i file di valutazione aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="15ab4-139">**Expected number of relevant files in assessment**: Given the updated values, the expected number of relevant files in the entire assessment after all additional assessment files are reviewed.</span></span>

10. <span data-ttu-id="15ab4-140">Fare **clic su Ricalcola valori** se i parametri vengono modificati.</span><span class="sxs-lookup"><span data-stu-id="15ab4-140">Click **Recalculate values**, if parameters are changed.</span></span> <span data-ttu-id="15ab4-141">Al termine, se è presente un problema, fare clic  su **OK** per salvare le modifiche oppure su Avanti quando sono presenti più problemi da esaminare o modificare e quindi **su Fine.**</span><span class="sxs-lookup"><span data-stu-id="15ab4-141">When you're done, if there is one issue, click **OK** to save the changes (or **Next** when there are multiple issues to review or modify and then **Finish**).</span></span> 

    <span data-ttu-id="15ab4-142">In caso di più problemi, dopo che tutti  i problemi sono stati esaminati o modificati, viene visualizzata una finestra di dialogo Di riepilogo, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="15ab4-142">When there are multiple issues, after all issues have been reviewed or adjusted, an **Assessment level: summary** dialog is displayed, as shown in the following example.</span></span> 

    ![Riepilogo del livello di valutazione](../media/4997b46d-10a5-4abc-b3b2-7b75a370eb9e.png)
  
    <span data-ttu-id="15ab4-144">Al termine della valutazione, passare alla fase successiva della formazione sulla pertinenza.</span><span class="sxs-lookup"><span data-stu-id="15ab4-144">On successful completion of assessment, proceed to the next stage in Relevance training.</span></span>

## <a name="reviewing-assessment-results"></a><span data-ttu-id="15ab4-145">Revisione dei risultati della valutazione</span><span class="sxs-lookup"><span data-stu-id="15ab4-145">Reviewing assessment results</span></span>

<span data-ttu-id="15ab4-146">Dopo aver taggato un campione di valutazione, i risultati della valutazione vengono calcolati e visualizzati nella scheda Traccia di pertinenza.</span><span class="sxs-lookup"><span data-stu-id="15ab4-146">After an Assessment sample is tagged, the assessment results are calculated and displayed in the Relevance Track tab.</span></span>
  
<span data-ttu-id="15ab4-147">Nella visualizzazione traccia espansa vengono visualizzati i risultati seguenti:</span><span class="sxs-lookup"><span data-stu-id="15ab4-147">The following results are displayed in the expanded Track display:</span></span>
  
- <span data-ttu-id="15ab4-148">Margine di errore corrente di valutazione per le stime di richiamo</span><span class="sxs-lookup"><span data-stu-id="15ab4-148">Assessment current error margin for recall estimates</span></span>

- <span data-ttu-id="15ab4-149">Ricchezza stimata</span><span class="sxs-lookup"><span data-stu-id="15ab4-149">Estimated richness</span></span>

- <span data-ttu-id="15ab4-150">File di valutazione aggiuntivi necessari (per la revisione)</span><span class="sxs-lookup"><span data-stu-id="15ab4-150">Additional assessment files required (for review)</span></span>

<span data-ttu-id="15ab4-151">Il margine di errore corrente di valutazione è il margine di errore consigliato Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="15ab4-151">The Assessment current error margin is the error margin recommended by Advanced eDiscovery.</span></span> <span data-ttu-id="15ab4-152">Il numero visualizzato per i "File di valutazione aggiuntivi necessari" corrisponde a tale raccomandazione.</span><span class="sxs-lookup"><span data-stu-id="15ab4-152">The number displayed for the "Additional assessment files required" corresponds to that recommendation.</span></span>
  
<span data-ttu-id="15ab4-153">L'indicatore di stato della valutazione mostra il livello di completamento della valutazione, dato il margine di errore corrente.</span><span class="sxs-lookup"><span data-stu-id="15ab4-153">The Assessment progress indicator shows the level of completion of the assessment, given the current error margin.</span></span> <span data-ttu-id="15ab4-154">Quando è in corso la valutazione, l'utente contrassegnerà un altro campione di valutazione.</span><span class="sxs-lookup"><span data-stu-id="15ab4-154">When assessment is underway, the user will tag another assessment sample.</span></span>
  
<span data-ttu-id="15ab4-155">Quando l'indicatore di stato della valutazione mostra che la valutazione è stata completata, significa che la revisione del campione di valutazione è stata completata e sono stati taggati file pertinenti sufficienti.</span><span class="sxs-lookup"><span data-stu-id="15ab4-155">When the assessment progress indicator shows assessment as complete, that means the assessment sample review was completed and sufficient relevant files were tagged.</span></span> 
  
<span data-ttu-id="15ab4-156">La visualizzazione traccia espansa mostra il passaggio successivo consigliato, le statistiche di valutazione e l'accesso ai risultati dettagliati.</span><span class="sxs-lookup"><span data-stu-id="15ab4-156">The expanded Track display shows the recommended next step, the assessment statistics, and access to detailed results.</span></span>
  
<span data-ttu-id="15ab4-157">Quando la ricchezza è molto bassa, il numero di file di valutazione aggiuntivi necessari per raggiungere un numero minimo di file rilevanti per produrre statistiche utili è molto elevato.</span><span class="sxs-lookup"><span data-stu-id="15ab4-157">When richness is very low, the number of additional assessment files needed to reach a minimal number of relevant files to produce useful statistics is very high.</span></span> <span data-ttu-id="15ab4-158">Advanced eDiscovery sarà quindi consigliabile passare alla formazione.</span><span class="sxs-lookup"><span data-stu-id="15ab4-158">Advanced eDiscovery will then recommend moving on to training.</span></span> <span data-ttu-id="15ab4-159">L'indicatore di stato della valutazione sarà ombreggiato e non saranno disponibili statistiche.</span><span class="sxs-lookup"><span data-stu-id="15ab4-159">The assessment progress indicator will be shaded, and no statistics will be available.</span></span>
  
<span data-ttu-id="15ab4-160">In assenza di stabilizzazione basata su statistiche, i risultati avranno un livello inferiore di accuratezza e livello di confidenza.</span><span class="sxs-lookup"><span data-stu-id="15ab4-160">In the absence of statistically based stabilization, there will be results with a lower level of accuracy and confidence level.</span></span> <span data-ttu-id="15ab4-161">Tuttavia, questi risultati possono essere utilizzati per trovare i file pertinenti quando non è necessario conoscere la percentuale di file pertinenti trovati.</span><span class="sxs-lookup"><span data-stu-id="15ab4-161">However, these results can be used to find relevant files when you do not need to know the percentage of relevant files found.</span></span> <span data-ttu-id="15ab4-162">Analogamente, questo stato può essere usato per formare i problemi con scarsa ricchezza, in cui i punteggi di pertinenza possono accelerare l'accesso ai file rilevanti per un problema specifico.</span><span class="sxs-lookup"><span data-stu-id="15ab4-162">Similarly, this status can be used to train issues with low richness, where Relevance scores can accelerate access to files relevant to a specific issue.</span></span>
  
> [!TIP]
> <span data-ttu-id="15ab4-163">Nella scheda **Traccia di \> pertinenza,** visualizzazione dei problemi espansa, sono disponibili le opzioni di visualizzazione seguenti:</span><span class="sxs-lookup"><span data-stu-id="15ab4-163">In the **Relevance \> Track** tab, expanded issue display, the following viewing options are available:</span></span> 
> 
> <span data-ttu-id="15ab4-164">Il passaggio successivo consigliato, ad esempio Passaggio **successivo: Tagging** può essere ignorato (per problema) facendo clic sul pulsante **Modifica** a destra e quindi selezionando un passaggio diverso nel **passaggio Successivo.**</span><span class="sxs-lookup"><span data-stu-id="15ab4-164">The recommended next step, such as **Next step: Tagging** can be bypassed (per issue) by clicking the **Modify** button to its right, and then selecting an different step in the **Next step**.</span></span> <span data-ttu-id="15ab4-165">Quando l'indicatore di stato della valutazione non è stato completato, la valutazione sarà l'opzione consigliata successiva, per contrassegnare più file di valutazione e aumentare l'accuratezza delle statistiche.</span><span class="sxs-lookup"><span data-stu-id="15ab4-165">When the assessment progress indicator has not completed, assessment will be the next recommended option, to tag more assessment files and increase statistics accuracy.</span></span> 
> 
> <span data-ttu-id="15ab4-166">È possibile modificare il margine di errore e valutarne l'impatto facendo clic su Modifica e nella finestra di dialogo Livello di **valutazione,** modificando il margine di errore target per le stime di richiamo e facendo clic su **Aggiorna valori.**</span><span class="sxs-lookup"><span data-stu-id="15ab4-166">You can change the error margin and assess its impact, by clicking **Modify**, and in the **Assessment level dialog**, changing the **Target error margin for recall estimates**, and clicking **Update values**.</span></span> <span data-ttu-id="15ab4-167">Inoltre, in questa finestra di dialogo è possibile visualizzare le opzioni avanzate facendo clic su **Avanzate.**</span><span class="sxs-lookup"><span data-stu-id="15ab4-167">Also, in this dialog, you can view advanced options, by clicking **Advanced**.</span></span> 
> 
> <span data-ttu-id="15ab4-168">È possibile visualizzare ulteriori statistiche del livello di valutazione e il relativo impatto facendo clic su **Visualizza.**</span><span class="sxs-lookup"><span data-stu-id="15ab4-168">You can view additional assessment level statistics and their impact by clicking **View**.</span></span> <span data-ttu-id="15ab4-169">Nella finestra di dialogo Dei risultati dettagliati, le statistiche sono disponibili per ogni problema, quando sono presenti almeno 500 file di valutazione con tag e almeno 18 file sono contrassegnati come rilevanti per il problema.</span><span class="sxs-lookup"><span data-stu-id="15ab4-169">In the displayed Detail results dialog, statistics are available per issue, when there are at least 500 tagged assessment files and at least 18 files are tagged as Relevant for the issue.</span></span> 
