---
title: Tagging e valutazione in Office 365 Advanced eDiscovery
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 09/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: b5c82de7-ed2f-4cc6-becd-db403faf4d18
description: 'Esaminare i passaggi necessari per eseguire la formazione di valutazione, compresi i file di tagging, e la revisione dei risultati della valutazione in Office 365 Advanced eDiscovery. '
ms.openlocfilehash: 067f8933bd7fc1286e468d664bf4dbd754e64f00
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37084094"
---
# <a name="tagging-and-assessment-in-office-365-advanced-ediscovery"></a><span data-ttu-id="a8168-103">Tagging e valutazione in Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="a8168-103">Tagging and Assessment in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="a8168-p101">Per usare Advanced eDiscovery è necessario avere Office 365 E3 con il componente aggiuntivo Advanced Compliance o un abbonamento E5 dell'organizzazione. Se non si ha questo piano e si desidera provare Advanced eDiscovery, è possibile [richiedere una valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="a8168-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="a8168-106">In questa sezione viene descritta la procedura per il modulo di valutazione della pertinenza avanzata di eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="a8168-106">This section describes the procedure for the Advanced eDiscovery Relevance Assessment module.</span></span> 
  
## <a name="performing-assessment-training-and-analysis"></a><span data-ttu-id="a8168-107">Formazione e analisi per l'esecuzione di valutazioni</span><span class="sxs-lookup"><span data-stu-id="a8168-107">Performing Assessment training and analysis</span></span>

1. <span data-ttu-id="a8168-108">Nella scheda \*\* \> rilevamento pertinenza\*\* fare clic su **valutazione** per avviare la valutazione dei casi.</span><span class="sxs-lookup"><span data-stu-id="a8168-108">In the **Relevance \> Track** tab, click **Assessment** to start case assessment.</span></span> 
    
    <span data-ttu-id="a8168-109">Ad esempio, in questa procedura viene creato un set di valutazione di esempio di 500 file e viene visualizzata la scheda **tag** , che contiene il pannello di tagging, il contenuto del file visualizzato e altre opzioni di tagging.</span><span class="sxs-lookup"><span data-stu-id="a8168-109">For example purposes in this procedure, a sample assessment set of 500 files is created and the **Tag** tab is displayed, which contains the Tagging panel, displayed file content and other tagging options.</span></span> 
    
    ![Scheda Tag pertinenza per la valutazione](media/c8acf891-b1cd-4344-816c-eabb8cbbe742.png)
  
2. <span data-ttu-id="a8168-111">Esaminare ogni file nell'esempio, determinare la pertinenza del file per ogni problema di caso e contrassegnare il file utilizzando i pulsanti pertinenza (R), non rilevanti (NR) e Ignora nel riquadro del **Pannello di tagging** .</span><span class="sxs-lookup"><span data-stu-id="a8168-111">Review each file in the sample, determine the file's relevance for each case issue, and tag the file using the Relevance (R), Not relevant (NR) and Skip buttons in the **Tagging panel** pane.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="a8168-112">La valutazione richiede 500 file contrassegnati.</span><span class="sxs-lookup"><span data-stu-id="a8168-112">Assessment requires 500 tagged files.</span></span> <span data-ttu-id="a8168-113">Se i file vengono "ignorati", verranno visualizzati altri file da contrassegnare.</span><span class="sxs-lookup"><span data-stu-id="a8168-113">If files are "skipped", you will receive more files to tag.</span></span> 
  
3. <span data-ttu-id="a8168-114">Dopo aver codificato tutti i file nell'esempio, fare clic su **Calcola**.</span><span class="sxs-lookup"><span data-stu-id="a8168-114">After tagging all files in the sample, click **Calculate**.</span></span> 
    
    <span data-ttu-id="a8168-115">La valutazione del margine e della ricchezza degli errori correnti viene calcolata e visualizzata nella scheda **pertinenza** , con dettagli espansi per ogni problema, come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="a8168-115">The Assessment current error margin and richness are calculated and displayed in the **Relevance Track** tab, with expanded details per issue, as shown below.</span></span> <span data-ttu-id="a8168-116">Ulteriori informazioni su questa finestra di dialogo sono descritte nella sezione successiva "revisione dei risultati delle valutazioni".</span><span class="sxs-lookup"><span data-stu-id="a8168-116">More details about this dialog are described in the later section "Reviewing Assessments results".</span></span> 
    
    ![Traccia di pertinenza: valutazione](media/da911ba5-8678-40d6-9ad5-fd0b058355c1.png)
  
    > [!TIP]
    > <span data-ttu-id="a8168-118">Per impostazione predefinita, si consiglia di procedere con il passaggio successivo predefinito quando l'indicatore di stato di valutazione del problema è stato completato, indicando che il campione di valutazione è stato esaminato e che sono stati contrassegnati i file rilevanti sufficienti.</span><span class="sxs-lookup"><span data-stu-id="a8168-118">By default, we recommend that you proceed to the default Next step when the Assessment progress indicator for the issue has completed, indicating that the assessment sample was reviewed and sufficient relevant files were tagged.</span></span> <span data-ttu-id="a8168-119">> altrimenti, se si desidera visualizzare i risultati della scheda **pista** e controllare il margine di errore e il passaggio successivo, fare clic su **modifica** adiacente al **passaggio successivo**, selezionare **continua valutazione**e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a8168-119">> Otherwise, if you want to view the **Track** tab results and control the margin of error and the next step, click **Modify** adjacent to **Next Step**, select **Continue assessment**, and then click **OK**.</span></span> 
  
1. <span data-ttu-id="a8168-120">Fare clic su **modifica** a destra della casella di controllo **valutazione** per visualizzare e specificare i parametri di valutazione per ogni problema.</span><span class="sxs-lookup"><span data-stu-id="a8168-120">Click **Modify** to the right of the **Assessment** check box to view and specify assessment parameters per issue.</span></span> <span data-ttu-id="a8168-121">Viene visualizzata una finestra di dialogo a **livello di valutazione** per ogni problema, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="a8168-121">An **Assessment level** dialog for each issue is displayed, as shown in the following example:</span></span> 
    
    ![Problema relativo al livello di valutazione per il caso](media/b7113fef-d125-4617-ae1b-c9eb0bf79aec.png)
  
    <span data-ttu-id="a8168-123">I parametri seguenti per il problema vengono calcolati e visualizzati nella finestra di dialogo **livello di valutazione** :</span><span class="sxs-lookup"><span data-stu-id="a8168-123">The following parameters for the issue are calculated and displayed in the **Assessment level** dialog:</span></span> 
    
    <span data-ttu-id="a8168-124">**Margine di errore di destinazione per le stime del richiamo**: sulla base di questo valore, viene calcolato il numero stimato di file aggiuntivi necessari per la revisione.</span><span class="sxs-lookup"><span data-stu-id="a8168-124">**Target error margin for recall estimates**: Based on this value, the estimated number of additional files necessary to review is calculated.</span></span> <span data-ttu-id="a8168-125">Il margine utilizzato per il richiamo è maggiore di 75% e con un livello di confidenza del 95%.</span><span class="sxs-lookup"><span data-stu-id="a8168-125">The margin used for recall is greater than 75% and with a 95% confidence level.</span></span> 
    
    <span data-ttu-id="a8168-126">**File di valutazione aggiuntivi necessari**: indica quanti altri file sono necessari se i requisiti del margine di errore corrente non sono stati soddisfatti.</span><span class="sxs-lookup"><span data-stu-id="a8168-126">**Additional assessment files required**: Indicates how many more files are necessary if the current error margin's requirements have not been met.</span></span> 
    
2. <span data-ttu-id="a8168-127">Per modificare il margine di errore corrente e vedere l'effetto dei diversi margini di errore (per problema):</span><span class="sxs-lookup"><span data-stu-id="a8168-127">To adjust the current error margin and see the effect of different error margins (per issue):</span></span>
    
1. <span data-ttu-id="a8168-128">Nell'elenco **selezionare** un problema selezionare un problema.</span><span class="sxs-lookup"><span data-stu-id="a8168-128">In the **Select issue** list, select an issue.</span></span> 
    
2. <span data-ttu-id="a8168-129">Nel **margine di errore di destinazione per le stime di richiamo**, immettere un nuovo valore.</span><span class="sxs-lookup"><span data-stu-id="a8168-129">In **Target error margin for recall estimates**, enter a new value.</span></span>
    
3. <span data-ttu-id="a8168-130">Fare clic su **Aggiorna valori** per visualizzare l'impatto delle rettifiche.</span><span class="sxs-lookup"><span data-stu-id="a8168-130">Click **Update values** to see the impact of the adjustments.</span></span> 
    
3. <span data-ttu-id="a8168-131">Fare clic su **Avanzate** nella finestra di dialogo **livello di valutazione** per visualizzare i parametri e i dettagli aggiuntivi seguenti:</span><span class="sxs-lookup"><span data-stu-id="a8168-131">Click **Advanced** in the **Assessment level** dialog to see the following additional parameters and details:</span></span> 
    
    ![Visualizzazione avanzata dei problemi relativi al livello di valutazione per il caso](media/577d7e0e-95df-48c2-9dec-bdeab5e801d8.png)
  
    <span data-ttu-id="a8168-133">**Ricchezza stimata**: ricchezza stimata in base ai risultati di valutazione correnti</span><span class="sxs-lookup"><span data-stu-id="a8168-133">**Estimated richness**: Estimated richness according to the current assessment results</span></span>
    
    <span data-ttu-id="a8168-134">**Per il richiamo assunto**: per impostazione predefinita, il margine di errore di destinazione si applica a richiamo sopra 75%.</span><span class="sxs-lookup"><span data-stu-id="a8168-134">**For assumed recall**: By default, the target error margin applies to recall above 75%.</span></span> <span data-ttu-id="a8168-135">Fare clic su **modifica** se si desidera modificare questo parametro e controllare il margine di errore su un intervallo diverso di valori di richiamo.</span><span class="sxs-lookup"><span data-stu-id="a8168-135">Click **Edit** if you want to change this parameter and control the margin of error on a different range of recall values.</span></span> 
    
    <span data-ttu-id="a8168-136">**Livello di confidenza**: per impostazione predefinita, il margine di errore consigliato per la sicurezza è 95%.</span><span class="sxs-lookup"><span data-stu-id="a8168-136">**Confidence level**: By default, the recommended error margin for confidence is 95%.</span></span> <span data-ttu-id="a8168-137">Se si desidera modificare questo parametro, fare clic su **modifica** .</span><span class="sxs-lookup"><span data-stu-id="a8168-137">Click **Edit** if you want to change this parameter.</span></span> 
    
    <span data-ttu-id="a8168-138">**Margine errore previsto**per la ricchezza: in base ai valori aggiornati, si tratta del margine di errore previsto per la ricchezza, dopo la revisione di tutti i file di valutazione aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="a8168-138">**Expected richness error margin**: Given the updated values, this is the expected margin of error of the richness, after all additional assessment files are reviewed.</span></span>
    
    <span data-ttu-id="a8168-139">**File di valutazione aggiuntivi necessari**: dati i valori aggiornati, il numero di file di valutazione aggiuntivi che devono essere esaminati per raggiungere l'obiettivo.</span><span class="sxs-lookup"><span data-stu-id="a8168-139">**Additional assessment files required**: Given the updated values, the number of additional assessment files that need to be reviewed to reach the target.</span></span>
    
    <span data-ttu-id="a8168-140">**Totale file di valutazione necessari**: dati i valori aggiornati, i file di valutazione totali necessari per la revisione.</span><span class="sxs-lookup"><span data-stu-id="a8168-140">**Total assessment files required**: Given the updated values, total assessment files required for review.</span></span>
    
    <span data-ttu-id="a8168-141">**Numero previsto di file rilevanti nella valutazione**: dati i valori aggiornati, il numero previsto di file rilevanti nell'intera valutazione dopo che sono stati esaminati tutti i file di valutazione aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="a8168-141">**Expected number of relevant files in assessment**: Given the updated values, the expected number of relevant files in the entire assessment after all additional assessment files are reviewed.</span></span>
    
4. <span data-ttu-id="a8168-142">Se si modificano i parametri, fare clic su **Ricalcola valori**.</span><span class="sxs-lookup"><span data-stu-id="a8168-142">Click **Recalculate values**, if parameters are changed.</span></span> <span data-ttu-id="a8168-143">Al termine, se si verifica un problema, fare clic su **OK** per salvare le modifiche (o su **Avanti** quando sono presenti più problemi da rivedere o modificare e quindi **terminare**).</span><span class="sxs-lookup"><span data-stu-id="a8168-143">When you are done, if there is one issue, click **OK** to save the changes (or **Next** when there are multiple issues to review or modify and then **Finish**).</span></span> 
    
    <span data-ttu-id="a8168-144">Quando sono presenti più problemi, dopo che tutti i problemi sono stati esaminati o modificati, viene visualizzato un **livello di valutazione:** viene visualizzata la finestra di riepilogo, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="a8168-144">When there are multiple issues, after all issues have been reviewed or adjusted, an **Assessment level: summary** dialog is displayed, as shown in the following example.</span></span> 
    
    ![Riepilogo del livello di valutazione](media/4997b46d-10a5-4abc-b3b2-7b75a370eb9e.png)
  
    <span data-ttu-id="a8168-146">Dopo aver completato il processo di valutazione, passare alla fase successiva per la formazione sulla pertinenza.</span><span class="sxs-lookup"><span data-stu-id="a8168-146">Upon successful completion of assessment, proceed to the next stage in Relevance training.</span></span>
    
## <a name="reviewing-assessment-results"></a><span data-ttu-id="a8168-147">Revisione dei risultati della valutazione</span><span class="sxs-lookup"><span data-stu-id="a8168-147">Reviewing assessment results</span></span>

<span data-ttu-id="a8168-148">Dopo aver aggiunto un campione di valutazione, i risultati della valutazione vengono calcolati e visualizzati nella scheda Tracking pertinenza.</span><span class="sxs-lookup"><span data-stu-id="a8168-148">After an Assessment sample is tagged, the assessment results are calculated and displayed in the Relevance Track tab.</span></span>
  
<span data-ttu-id="a8168-149">I risultati seguenti sono visualizzati nella visualizzazione espansa della pista:</span><span class="sxs-lookup"><span data-stu-id="a8168-149">The following results are displayed in the expanded Track display:</span></span> 
  
- <span data-ttu-id="a8168-150">Valutazione del margine di errore corrente per le stime del richiamo</span><span class="sxs-lookup"><span data-stu-id="a8168-150">Assessment current error margin for recall estimates</span></span>
    
- <span data-ttu-id="a8168-151">Ricchezza stimata</span><span class="sxs-lookup"><span data-stu-id="a8168-151">Estimated richness</span></span>
    
- <span data-ttu-id="a8168-152">File di valutazione aggiuntivi necessari (per la revisione)</span><span class="sxs-lookup"><span data-stu-id="a8168-152">Additional assessment files required (for review)</span></span>
    
<span data-ttu-id="a8168-153">Il margine di errore di valutazione corrente è il margine di errore consigliato da Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="a8168-153">The Assessment current error margin is the error margin recommended by Advanced eDiscovery.</span></span> <span data-ttu-id="a8168-154">Il numero visualizzato per i "file di valutazione aggiuntivi richiesti" corrisponde a tale raccomandazione.</span><span class="sxs-lookup"><span data-stu-id="a8168-154">The number displayed for the "Additional assessment files required" corresponds to that recommendation.</span></span>
  
<span data-ttu-id="a8168-155">L'indicatore di avanzamento della valutazione indica il livello di completamento della valutazione, in base al margine di errore corrente.</span><span class="sxs-lookup"><span data-stu-id="a8168-155">The Assessment progress indicator shows the level of completion of the assessment, given the current error margin.</span></span> <span data-ttu-id="a8168-156">Quando la valutazione è in corso, l'utente Tag un altro campione di valutazione.</span><span class="sxs-lookup"><span data-stu-id="a8168-156">When assessment is underway, the user will tag another assessment sample.</span></span>
  
<span data-ttu-id="a8168-157">Quando l'indicatore di avanzamento della valutazione Visualizza la valutazione come completata, significa che la revisione del campione di valutazione è stata completata e che sono stati contrassegnati i file rilevanti sufficienti.</span><span class="sxs-lookup"><span data-stu-id="a8168-157">When the assessment progress indicator shows assessment as complete, that means the assessment sample review was completed and sufficient relevant files were tagged.</span></span> 
  
<span data-ttu-id="a8168-158">La visualizzazione estesa della pista Mostra il passaggio successivo consigliato, le statistiche di valutazione e l'accesso ai risultati dettagliati.</span><span class="sxs-lookup"><span data-stu-id="a8168-158">The expanded Track display shows the recommended next step, the assessment statistics, and access to detailed results.</span></span>
  
<span data-ttu-id="a8168-159">Quando la ricchezza è molto bassa, il numero di file di valutazione aggiuntivi necessari per raggiungere un numero minimo di file rilevanti per produrre statistiche utili è molto elevato.</span><span class="sxs-lookup"><span data-stu-id="a8168-159">When richness is very low, the number of additional assessment files needed to reach a minimal number of relevant files to produce useful statistics is very high.</span></span> <span data-ttu-id="a8168-160">Advanced eDiscovery consiglia di passare all'allenamento.</span><span class="sxs-lookup"><span data-stu-id="a8168-160">Advanced eDiscovery will then recommend moving on to training.</span></span> <span data-ttu-id="a8168-161">L'indicatore di avanzamento della valutazione verrà ombreggiato e non saranno disponibili statistiche.</span><span class="sxs-lookup"><span data-stu-id="a8168-161">The assessment progress indicator will be shaded, and no statistics will be available.</span></span> 
  
<span data-ttu-id="a8168-162">In assenza di stabilizzazione basata statisticamente, vi saranno risultati con un livello di precisione e confidenza inferiore.</span><span class="sxs-lookup"><span data-stu-id="a8168-162">In the absence of statistically based stabilization, there will be results with a lower level of accuracy and confidence level.</span></span> <span data-ttu-id="a8168-163">Tuttavia, questi risultati possono essere utilizzati per trovare i file rilevanti quando non è necessario conoscere la percentuale di file rilevanti trovati.</span><span class="sxs-lookup"><span data-stu-id="a8168-163">However, these results can be used to find relevant files when you do not need to know the percentage of relevant files found.</span></span> <span data-ttu-id="a8168-164">Analogamente, questo stato può essere utilizzato per formare problemi con una ricchezza bassa, in cui i punteggi rilevati possono accelerare l'accesso ai file rilevanti per un problema specifico.</span><span class="sxs-lookup"><span data-stu-id="a8168-164">Similarly, this status can be used to train issues with low richness, where Relevance scores can accelerate access to files relevant to a specific issue.</span></span>
  
> [!TIP]
> <span data-ttu-id="a8168-165">Nella scheda \*\* \> Tracking pertinenza\*\* , espansione visualizzazione problema, sono disponibili le seguenti opzioni di visualizzazione: > il passaggio successivo consigliato, ad esempio il **passaggio successivo: il tagging** può essere ignorato (per ogni problema) facendo clic sul pulsante **modifica** alla sua destra e quindi selezionando un passaggio diverso nel **passaggio successivo**.</span><span class="sxs-lookup"><span data-stu-id="a8168-165">In the **Relevance \> Track** tab, expanded issue display, the following viewing options are available: > The recommended next step, such as **Next step: Tagging** can be bypassed (per issue) by clicking the **Modify** button to its right, and then selecting an different step in the **Next step**.</span></span> <span data-ttu-id="a8168-166">Quando l'indicatore di stato di valutazione non è stato completato, la valutazione sarà la successiva opzione consigliata per contrassegnare i file di valutazione e aumentare l'accuratezza delle statistiche.</span><span class="sxs-lookup"><span data-stu-id="a8168-166">When the assessment progress indicator has not completed, assessment will be the next recommended option, to tag more assessment files and increase statistics accuracy.</span></span> <span data-ttu-id="a8168-167">> è possibile modificare il margine di errore e valutarne l'impatto, facendo clic su **modifica**e nella **finestra di dialogo livello di valutazione**, modificando il **margine di errore di destinazione per le stime di richiamo**e facendo clic su **Aggiorna valori**.</span><span class="sxs-lookup"><span data-stu-id="a8168-167">> You can change the error margin and assess its impact, by clicking **Modify**, and in the **Assessment level dialog**, changing the **Target error margin for recall estimates**, and clicking **Update values**.</span></span> <span data-ttu-id="a8168-168">Inoltre, in questa finestra di dialogo, è possibile visualizzare le opzioni avanzate facendo clic su **Avanzate**.</span><span class="sxs-lookup"><span data-stu-id="a8168-168">Also, in this dialog, you can view advanced options, by clicking **Advanced**.</span></span> <span data-ttu-id="a8168-169">> è possibile visualizzare le statistiche aggiuntive a livello di valutazione e il relativo impatto facendo clic su **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="a8168-169">> You can view additional assessment level statistics and their impact by clicking **View**.</span></span> <span data-ttu-id="a8168-170">Nella finestra di dialogo Risultati dettagli visualizzati, le statistiche sono disponibili per ogni problema, quando sono presenti almeno 500 file di valutazione contrassegnati e almeno 18 file sono contrassegnati come rilevanti per il problema.</span><span class="sxs-lookup"><span data-stu-id="a8168-170">In the displayed Detail results dialog, statistics are available per issue, when there are at least 500 tagged assessment files and at least 18 files are tagged as Relevant for the issue.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="a8168-171">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a8168-171">See also</span></span>

[<span data-ttu-id="a8168-172">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="a8168-172">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="a8168-173">Informazioni sulla valutazione in rilevanza</span><span class="sxs-lookup"><span data-stu-id="a8168-173">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="a8168-174">Formazione di tagging e pertinenza</span><span class="sxs-lookup"><span data-stu-id="a8168-174">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="a8168-175">Verifica dell'analisi della pertinenza</span><span class="sxs-lookup"><span data-stu-id="a8168-175">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="a8168-176">Decidere in base ai risultati</span><span class="sxs-lookup"><span data-stu-id="a8168-176">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="a8168-177">Verifica dell'analisi della pertinenza</span><span class="sxs-lookup"><span data-stu-id="a8168-177">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

