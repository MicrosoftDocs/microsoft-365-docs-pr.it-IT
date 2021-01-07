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
description: Esaminare i passaggi necessari per eseguire la formazione di valutazione, compresi i file di tagging, e la revisione dei risultati della valutazione in Advanced eDiscovery.
ms.openlocfilehash: 15bc8254ea1589d9afa17a74eaf3bfbcdfd4bba0
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769191"
---
# <a name="tagging-and-assessment-in-the-relevance-module-in-advanced-ediscovery"></a><span data-ttu-id="c31b7-103">Tagging e valutazione nel modulo pertinenza in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="c31b7-103">Tagging and Assessment in the Relevance module in Advanced eDiscovery</span></span>
  
<span data-ttu-id="c31b7-104">In questa sezione viene descritta la procedura per la valutazione del modulo pertinenza in Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="c31b7-104">This section describes the procedure for Assessment in the Relevance module in Advanced eDiscovery.</span></span>
  
## <a name="performing-assessment-training-and-analysis"></a><span data-ttu-id="c31b7-105">Formazione e analisi per l'esecuzione di valutazioni</span><span class="sxs-lookup"><span data-stu-id="c31b7-105">Performing Assessment training and analysis</span></span>

1. <span data-ttu-id="c31b7-106">Nella scheda **\> rilevamento pertinenza** fare clic su **valutazione** per avviare la valutazione dei casi.</span><span class="sxs-lookup"><span data-stu-id="c31b7-106">In the **Relevance \> Track** tab, click **Assessment** to start case assessment.</span></span>

    <span data-ttu-id="c31b7-107">Ad esempio, in questa procedura viene creato un set di valutazione di esempio di 500 file e viene visualizzata la scheda **tag** , che contiene il pannello di tagging, il contenuto del file visualizzato e altre opzioni di tagging.</span><span class="sxs-lookup"><span data-stu-id="c31b7-107">For example purposes in this procedure, a sample assessment set of 500 files is created and the **Tag** tab is displayed, which contains the Tagging panel, displayed file content and other tagging options.</span></span> 

    ![Scheda Tag pertinenza per la valutazione](../media/c8acf891-b1cd-4344-816c-eabb8cbbe742.png)
  
2. <span data-ttu-id="c31b7-109">Esaminare ogni file nell'esempio, determinare la pertinenza del file per ogni problema di caso e contrassegnare il file utilizzando i pulsanti pertinenza (R), non rilevanti (NR) e Ignora nel riquadro del **Pannello di tagging** .</span><span class="sxs-lookup"><span data-stu-id="c31b7-109">Review each file in the sample, determine the file's relevance for each case issue, and tag the file using the Relevance (R), Not relevant (NR) and Skip buttons in the **Tagging panel** pane.</span></span> 

    > [!NOTE]
    >  <span data-ttu-id="c31b7-110">La valutazione richiede 500 file contrassegnati.</span><span class="sxs-lookup"><span data-stu-id="c31b7-110">Assessment requires 500 tagged files.</span></span> <span data-ttu-id="c31b7-111">Se i file vengono "ignorati", verranno visualizzati altri file da contrassegnare.</span><span class="sxs-lookup"><span data-stu-id="c31b7-111">If files are "skipped", you will receive more files to tag.</span></span> 
  
3. <span data-ttu-id="c31b7-112">Dopo aver codificato tutti i file nell'esempio, fare clic su **Calcola**.</span><span class="sxs-lookup"><span data-stu-id="c31b7-112">After tagging all files in the sample, click **Calculate**.</span></span>

    <span data-ttu-id="c31b7-113">La valutazione del margine e della ricchezza degli errori correnti viene calcolata e visualizzata nella scheda **pertinenza** , con dettagli espansi per ogni problema, come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="c31b7-113">The Assessment current error margin and richness are calculated and displayed in the **Relevance Track** tab, with expanded details per issue, as shown below.</span></span> <span data-ttu-id="c31b7-114">Ulteriori informazioni su questa finestra di dialogo sono descritte nella sezione [revisione dei risultati della valutazione](#reviewing-assessment-results) .</span><span class="sxs-lookup"><span data-stu-id="c31b7-114">More details about this dialog are described in the [Reviewing assessment results](#reviewing-assessment-results) section.</span></span>

    ![Traccia di pertinenza: valutazione](../media/da911ba5-8678-40d6-9ad5-fd0b058355c1.png)
  
    > [!TIP]
    > <span data-ttu-id="c31b7-116">Per impostazione predefinita, si consiglia di procedere con il passaggio successivo predefinito quando l'indicatore di stato di valutazione del problema è stato completato, indicando che il campione di valutazione è stato esaminato e che sono stati contrassegnati i file rilevanti sufficienti.</span><span class="sxs-lookup"><span data-stu-id="c31b7-116">By default, we recommend that you proceed to the default Next step when the Assessment progress indicator for the issue has completed, indicating that the assessment sample was reviewed and sufficient relevant files were tagged.</span></span> <span data-ttu-id="c31b7-117">> altrimenti, se si desidera visualizzare i risultati della scheda **pista** e controllare il margine di errore e il passaggio successivo, fare clic su **modifica** adiacente al **passaggio successivo**, selezionare **continua valutazione** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="c31b7-117">> Otherwise, if you want to view the **Track** tab results and control the margin of error and the next step, click **Modify** adjacent to **Next Step**, select **Continue assessment**, and then click **OK**.</span></span>
  
4. <span data-ttu-id="c31b7-118">Fare clic su **modifica** a destra della casella di controllo **valutazione** per visualizzare e specificare i parametri di valutazione per ogni problema.</span><span class="sxs-lookup"><span data-stu-id="c31b7-118">Click **Modify** to the right of the **Assessment** check box to view and specify assessment parameters per issue.</span></span> <span data-ttu-id="c31b7-119">Viene visualizzata una finestra di dialogo a **livello di valutazione** per ogni problema, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="c31b7-119">An **Assessment level** dialog for each issue is displayed, as shown in the following example:</span></span> 

    ![Problema relativo al livello di valutazione per il caso](../media/b7113fef-d125-4617-ae1b-c9eb0bf79aec.png)
  
    <span data-ttu-id="c31b7-121">I parametri seguenti per il problema vengono calcolati e visualizzati nella finestra di dialogo **livello di valutazione** :</span><span class="sxs-lookup"><span data-stu-id="c31b7-121">The following parameters for the issue are calculated and displayed in the **Assessment level** dialog:</span></span> 

    <span data-ttu-id="c31b7-122">**Margine di errore di destinazione per le stime del richiamo**: sulla base di questo valore, viene calcolato il numero stimato di file aggiuntivi necessari per la revisione.</span><span class="sxs-lookup"><span data-stu-id="c31b7-122">**Target error margin for recall estimates**: Based on this value, the estimated number of additional files necessary to review is calculated.</span></span> <span data-ttu-id="c31b7-123">Il margine utilizzato per il richiamo è maggiore di 75% e con un livello di confidenza del 95%.</span><span class="sxs-lookup"><span data-stu-id="c31b7-123">The margin used for recall is greater than 75% and with a 95% confidence level.</span></span>

    <span data-ttu-id="c31b7-124">**File di valutazione aggiuntivi necessari**: indica quanti altri file sono necessari se i requisiti del margine di errore corrente non sono stati soddisfatti.</span><span class="sxs-lookup"><span data-stu-id="c31b7-124">**Additional assessment files required**: Indicates how many more files are necessary if the current error margin's requirements have not been met.</span></span> 

5. <span data-ttu-id="c31b7-125">Per modificare il margine di errore corrente e vedere l'effetto dei diversi margini di errore (per problema):</span><span class="sxs-lookup"><span data-stu-id="c31b7-125">To adjust the current error margin and see the effect of different error margins (per issue):</span></span>

6. <span data-ttu-id="c31b7-126">Nell'elenco **selezionare** un problema selezionare un problema.</span><span class="sxs-lookup"><span data-stu-id="c31b7-126">In the **Select issue** list, select an issue.</span></span> 

7. <span data-ttu-id="c31b7-127">Nel **margine di errore di destinazione per le stime di richiamo**, immettere un nuovo valore.</span><span class="sxs-lookup"><span data-stu-id="c31b7-127">In **Target error margin for recall estimates**, enter a new value.</span></span>

8. <span data-ttu-id="c31b7-128">Fare clic su **Aggiorna valori** per visualizzare l'impatto delle rettifiche.</span><span class="sxs-lookup"><span data-stu-id="c31b7-128">Click **Update values** to see the impact of the adjustments.</span></span> 

9. <span data-ttu-id="c31b7-129">Fare clic su **Avanzate** nella finestra di dialogo **livello di valutazione** per visualizzare i parametri e i dettagli aggiuntivi seguenti:</span><span class="sxs-lookup"><span data-stu-id="c31b7-129">Click **Advanced** in the **Assessment level** dialog to see the following additional parameters and details:</span></span> 

    ![Visualizzazione avanzata dei problemi relativi al livello di valutazione per il caso](../media/577d7e0e-95df-48c2-9dec-bdeab5e801d8.png)
  
    - <span data-ttu-id="c31b7-131">**Ricchezza stimata**: ricchezza stimata in base ai risultati di valutazione correnti</span><span class="sxs-lookup"><span data-stu-id="c31b7-131">**Estimated richness**: Estimated richness according to the current assessment results</span></span>

    - <span data-ttu-id="c31b7-132">**Per il richiamo assunto**: per impostazione predefinita, il margine di errore di destinazione si applica a richiamo sopra 75%.</span><span class="sxs-lookup"><span data-stu-id="c31b7-132">**For assumed recall**: By default, the target error margin applies to recall above 75%.</span></span> <span data-ttu-id="c31b7-133">Fare clic su **modifica** se si desidera modificare questo parametro e controllare il margine di errore su un intervallo diverso di valori di richiamo.</span><span class="sxs-lookup"><span data-stu-id="c31b7-133">Click **Edit** if you want to change this parameter and control the margin of error on a different range of recall values.</span></span> 

    - <span data-ttu-id="c31b7-134">**Livello di confidenza**: per impostazione predefinita, il margine di errore consigliato per la sicurezza è 95%.</span><span class="sxs-lookup"><span data-stu-id="c31b7-134">**Confidence level**: By default, the recommended error margin for confidence is 95%.</span></span> <span data-ttu-id="c31b7-135">Se si desidera modificare questo parametro, fare clic su **modifica** .</span><span class="sxs-lookup"><span data-stu-id="c31b7-135">Click **Edit** if you want to change this parameter.</span></span>

    - <span data-ttu-id="c31b7-136">**Margine errore previsto** per la ricchezza: in base ai valori aggiornati, si tratta del margine di errore previsto per la ricchezza, dopo la revisione di tutti i file di valutazione aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="c31b7-136">**Expected richness error margin**: Given the updated values, this is the expected margin of error of the richness, after all additional assessment files are reviewed.</span></span>

    - <span data-ttu-id="c31b7-137">**File di valutazione aggiuntivi necessari**: dati i valori aggiornati, il numero di file di valutazione aggiuntivi che devono essere esaminati per raggiungere l'obiettivo.</span><span class="sxs-lookup"><span data-stu-id="c31b7-137">**Additional assessment files required**: Given the updated values, the number of additional assessment files that need to be reviewed to reach the target.</span></span>

    - <span data-ttu-id="c31b7-138">**Totale file di valutazione necessari**: dati i valori aggiornati, i file di valutazione totali necessari per la revisione.</span><span class="sxs-lookup"><span data-stu-id="c31b7-138">**Total assessment files required**: Given the updated values, total assessment files required for review.</span></span>

    - <span data-ttu-id="c31b7-139">**Numero previsto di file rilevanti nella valutazione**: dati i valori aggiornati, il numero previsto di file rilevanti nell'intera valutazione dopo che sono stati esaminati tutti i file di valutazione aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="c31b7-139">**Expected number of relevant files in assessment**: Given the updated values, the expected number of relevant files in the entire assessment after all additional assessment files are reviewed.</span></span>

10. <span data-ttu-id="c31b7-140">Se si modificano i parametri, fare clic su **Ricalcola valori**.</span><span class="sxs-lookup"><span data-stu-id="c31b7-140">Click **Recalculate values**, if parameters are changed.</span></span> <span data-ttu-id="c31b7-141">Al termine, se si verifica un problema, fare clic su **OK** per salvare le modifiche o su **Avanti** quando sono presenti più problemi da rivedere o modificare e quindi **terminare**.</span><span class="sxs-lookup"><span data-stu-id="c31b7-141">When you're done, if there is one issue, click **OK** to save the changes (or **Next** when there are multiple issues to review or modify and then **Finish**).</span></span> 

    <span data-ttu-id="c31b7-142">Quando sono presenti più problemi, dopo che tutti i problemi sono stati esaminati o modificati, viene visualizzato un **livello di valutazione:** viene visualizzata la finestra di riepilogo, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="c31b7-142">When there are multiple issues, after all issues have been reviewed or adjusted, an **Assessment level: summary** dialog is displayed, as shown in the following example.</span></span> 

    ![Riepilogo del livello di valutazione](../media/4997b46d-10a5-4abc-b3b2-7b75a370eb9e.png)
  
    <span data-ttu-id="c31b7-144">Dopo aver completato il processo di valutazione, passare alla fase successiva di formazione per pertinenza.</span><span class="sxs-lookup"><span data-stu-id="c31b7-144">On successful completion of assessment, proceed to the next stage in Relevance training.</span></span>

## <a name="reviewing-assessment-results"></a><span data-ttu-id="c31b7-145">Revisione dei risultati della valutazione</span><span class="sxs-lookup"><span data-stu-id="c31b7-145">Reviewing assessment results</span></span>

<span data-ttu-id="c31b7-146">Dopo aver aggiunto un campione di valutazione, i risultati della valutazione vengono calcolati e visualizzati nella scheda Tracking pertinenza.</span><span class="sxs-lookup"><span data-stu-id="c31b7-146">After an Assessment sample is tagged, the assessment results are calculated and displayed in the Relevance Track tab.</span></span>
  
<span data-ttu-id="c31b7-147">I risultati seguenti sono visualizzati nella visualizzazione espansa della pista:</span><span class="sxs-lookup"><span data-stu-id="c31b7-147">The following results are displayed in the expanded Track display:</span></span>
  
- <span data-ttu-id="c31b7-148">Valutazione del margine di errore corrente per le stime del richiamo</span><span class="sxs-lookup"><span data-stu-id="c31b7-148">Assessment current error margin for recall estimates</span></span>

- <span data-ttu-id="c31b7-149">Ricchezza stimata</span><span class="sxs-lookup"><span data-stu-id="c31b7-149">Estimated richness</span></span>

- <span data-ttu-id="c31b7-150">File di valutazione aggiuntivi necessari (per la revisione)</span><span class="sxs-lookup"><span data-stu-id="c31b7-150">Additional assessment files required (for review)</span></span>

<span data-ttu-id="c31b7-151">Il margine di errore di valutazione corrente è il margine di errore consigliato da Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="c31b7-151">The Assessment current error margin is the error margin recommended by Advanced eDiscovery.</span></span> <span data-ttu-id="c31b7-152">Il numero visualizzato per i "file di valutazione aggiuntivi richiesti" corrisponde a tale raccomandazione.</span><span class="sxs-lookup"><span data-stu-id="c31b7-152">The number displayed for the "Additional assessment files required" corresponds to that recommendation.</span></span>
  
<span data-ttu-id="c31b7-153">L'indicatore di avanzamento della valutazione indica il livello di completamento della valutazione, in base al margine di errore corrente.</span><span class="sxs-lookup"><span data-stu-id="c31b7-153">The Assessment progress indicator shows the level of completion of the assessment, given the current error margin.</span></span> <span data-ttu-id="c31b7-154">Quando la valutazione è in corso, l'utente Tag un altro campione di valutazione.</span><span class="sxs-lookup"><span data-stu-id="c31b7-154">When assessment is underway, the user will tag another assessment sample.</span></span>
  
<span data-ttu-id="c31b7-155">Quando l'indicatore di avanzamento della valutazione Visualizza la valutazione come completata, significa che la revisione del campione di valutazione è stata completata e che sono stati contrassegnati i file rilevanti sufficienti.</span><span class="sxs-lookup"><span data-stu-id="c31b7-155">When the assessment progress indicator shows assessment as complete, that means the assessment sample review was completed and sufficient relevant files were tagged.</span></span> 
  
<span data-ttu-id="c31b7-156">La visualizzazione estesa della pista Mostra il passaggio successivo consigliato, le statistiche di valutazione e l'accesso ai risultati dettagliati.</span><span class="sxs-lookup"><span data-stu-id="c31b7-156">The expanded Track display shows the recommended next step, the assessment statistics, and access to detailed results.</span></span>
  
<span data-ttu-id="c31b7-157">Quando la ricchezza è molto bassa, il numero di file di valutazione aggiuntivi necessari per raggiungere un numero minimo di file rilevanti per produrre statistiche utili è molto elevato.</span><span class="sxs-lookup"><span data-stu-id="c31b7-157">When richness is very low, the number of additional assessment files needed to reach a minimal number of relevant files to produce useful statistics is very high.</span></span> <span data-ttu-id="c31b7-158">Advanced eDiscovery consiglia di passare all'allenamento.</span><span class="sxs-lookup"><span data-stu-id="c31b7-158">Advanced eDiscovery will then recommend moving on to training.</span></span> <span data-ttu-id="c31b7-159">L'indicatore di avanzamento della valutazione verrà ombreggiato e non saranno disponibili statistiche.</span><span class="sxs-lookup"><span data-stu-id="c31b7-159">The assessment progress indicator will be shaded, and no statistics will be available.</span></span>
  
<span data-ttu-id="c31b7-160">In assenza di stabilizzazione basata statisticamente, vi saranno risultati con un livello di precisione e confidenza inferiore.</span><span class="sxs-lookup"><span data-stu-id="c31b7-160">In the absence of statistically based stabilization, there will be results with a lower level of accuracy and confidence level.</span></span> <span data-ttu-id="c31b7-161">Tuttavia, questi risultati possono essere utilizzati per trovare i file rilevanti quando non è necessario conoscere la percentuale di file rilevanti trovati.</span><span class="sxs-lookup"><span data-stu-id="c31b7-161">However, these results can be used to find relevant files when you do not need to know the percentage of relevant files found.</span></span> <span data-ttu-id="c31b7-162">Analogamente, questo stato può essere utilizzato per formare problemi con una ricchezza bassa, in cui i punteggi rilevati possono accelerare l'accesso ai file rilevanti per un problema specifico.</span><span class="sxs-lookup"><span data-stu-id="c31b7-162">Similarly, this status can be used to train issues with low richness, where Relevance scores can accelerate access to files relevant to a specific issue.</span></span>
  
> [!TIP]
> <span data-ttu-id="c31b7-163">Nella scheda **\> Tracking pertinenza** , espansione visualizzazione dei problemi, sono disponibili le seguenti opzioni di visualizzazione:</span><span class="sxs-lookup"><span data-stu-id="c31b7-163">In the **Relevance \> Track** tab, expanded issue display, the following viewing options are available:</span></span> 
> 
> <span data-ttu-id="c31b7-164">Il passaggio successivo consigliato, ad esempio il **passaggio successivo:** la funzionalità di tagging può essere ignorata (per problema) facendo clic sul pulsante **modifica** a destra e quindi selezionando un passaggio diverso nel **passaggio successivo**.</span><span class="sxs-lookup"><span data-stu-id="c31b7-164">The recommended next step, such as **Next step: Tagging** can be bypassed (per issue) by clicking the **Modify** button to its right, and then selecting an different step in the **Next step**.</span></span> <span data-ttu-id="c31b7-165">Quando l'indicatore di stato di valutazione non è stato completato, la valutazione sarà la successiva opzione consigliata per contrassegnare i file di valutazione e aumentare l'accuratezza delle statistiche.</span><span class="sxs-lookup"><span data-stu-id="c31b7-165">When the assessment progress indicator has not completed, assessment will be the next recommended option, to tag more assessment files and increase statistics accuracy.</span></span> 
> 
> <span data-ttu-id="c31b7-166">È possibile modificare il margine di errore e valutarne l'impatto, facendo clic su **modifica** e nella **finestra di dialogo livello di valutazione**, modificando il **margine di errore di destinazione per le stime di richiamo** e facendo clic su **Aggiorna valori**.</span><span class="sxs-lookup"><span data-stu-id="c31b7-166">You can change the error margin and assess its impact, by clicking **Modify**, and in the **Assessment level dialog**, changing the **Target error margin for recall estimates**, and clicking **Update values**.</span></span> <span data-ttu-id="c31b7-167">Inoltre, in questa finestra di dialogo, è possibile visualizzare le opzioni avanzate facendo clic su **Avanzate**.</span><span class="sxs-lookup"><span data-stu-id="c31b7-167">Also, in this dialog, you can view advanced options, by clicking **Advanced**.</span></span> 
> 
> <span data-ttu-id="c31b7-168">È possibile visualizzare le statistiche aggiuntive a livello di valutazione e il relativo impatto facendo clic su **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="c31b7-168">You can view additional assessment level statistics and their impact by clicking **View**.</span></span> <span data-ttu-id="c31b7-169">Nella finestra di dialogo Risultati dettagli visualizzati, le statistiche sono disponibili per ogni problema, quando sono presenti almeno 500 file di valutazione contrassegnati e almeno 18 file sono contrassegnati come rilevanti per il problema.</span><span class="sxs-lookup"><span data-stu-id="c31b7-169">In the displayed Detail results dialog, statistics are available per issue, when there are at least 500 tagged assessment files and at least 18 files are tagged as Relevant for the issue.</span></span> 
