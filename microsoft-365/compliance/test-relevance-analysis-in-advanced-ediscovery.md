---
title: Verifica dell'analisi della pertinenza in Office 365 Advanced eDiscovery
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
ms.date: 09/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 1b092f7c-ea55-44f5-b419-63f3458fd7e0
description: "Informazioni su come utilizzare la scheda test dopo il calcolo batch in Office 365 Advanced eDiscovery per testare, confrontare e convalidare la qualità complessiva dell'elaborazione.  "
ms.openlocfilehash: cda959c77b2d51f85f1396eb27d16d2690321bb6
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2019
ms.locfileid: "40802629"
---
# <a name="test-relevance-analysis-in-office-365-advanced-ediscovery"></a><span data-ttu-id="5ae80-103">Verifica dell'analisi della pertinenza in Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="5ae80-103">Test Relevance analysis in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="5ae80-p101">Per usare Advanced eDiscovery è necessario avere Office 365 E3 con il componente aggiuntivo Advanced Compliance o un abbonamento E5 dell'organizzazione. Se non si ha questo piano e si desidera provare Advanced eDiscovery, è possibile [richiedere una valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="5ae80-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="5ae80-106">La scheda test in Advanced eDiscovery consente di testare, confrontare e convalidare la qualità complessiva dell'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="5ae80-106">The Test tab in Advanced eDiscovery enables you to test, compare, and validate the overall quality of processing.</span></span> <span data-ttu-id="5ae80-107">Questi test vengono eseguiti dopo il calcolo in batch.</span><span class="sxs-lookup"><span data-stu-id="5ae80-107">These tests are performed after Batch calculation.</span></span> <span data-ttu-id="5ae80-108">Contrassegnando i file della raccolta, un esperto rende il giudizio finale sul fatto che ogni file contrassegnato è effettivamente pertinente per il caso.</span><span class="sxs-lookup"><span data-stu-id="5ae80-108">By tagging the files in the collection, an expert makes the final judgment about whether each tagged file is actually relevant to the case.</span></span> 
  
<span data-ttu-id="5ae80-109">In scenari con problemi singoli e multipli i test vengono in genere eseguiti per ogni problema.</span><span class="sxs-lookup"><span data-stu-id="5ae80-109">In single and multiple-issue scenarios, tests are typically performed per issue.</span></span> <span data-ttu-id="5ae80-110">I risultati possono essere visualizzati dopo ogni test e i risultati dei test possono essere rielaborati con i file di test di esempio specificati.</span><span class="sxs-lookup"><span data-stu-id="5ae80-110">Results can be viewed after each test, and test results can be reworked with specified sample test files.</span></span>
  
## <a name="testing-the-rest"></a><span data-ttu-id="5ae80-111">Verifica del resto</span><span class="sxs-lookup"><span data-stu-id="5ae80-111">Testing the rest</span></span>

<span data-ttu-id="5ae80-112">Il test "test the rest" viene utilizzato per convalidare le decisioni di eliminazione, ad esempio per esaminare solo i file al di sopra di un punteggio di taglio di rilevanza specifico in base ai risultati avanzati di eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="5ae80-112">The "Test the Rest" test is used to validate culling decisions, for example, to review only files above a specific Relevance cutoff score based on the final Advanced eDiscovery results.</span></span> <span data-ttu-id="5ae80-113">L'esperto esamina un campione di file con un punteggio di taglio selezionato per valutare il numero di file rilevanti all'interno di tale set.</span><span class="sxs-lookup"><span data-stu-id="5ae80-113">The expert reviews a sample of files under a selected cutoff score to evaluate the number of relevant files within that set.</span></span>
  
<span data-ttu-id="5ae80-114">Questo test fornisce statistiche e un confronto tra il set di revisione e il test del popolamento Rest.</span><span class="sxs-lookup"><span data-stu-id="5ae80-114">This test provides statistics and a comparison between the Review set and the Test the Rest population.</span></span> <span data-ttu-id="5ae80-115">I risultati del set di revisione sono quelli calcolati per pertinenza durante l'allenamento.</span><span class="sxs-lookup"><span data-stu-id="5ae80-115">The results of the review set are those calculated by Relevance during Training.</span></span> <span data-ttu-id="5ae80-116">I risultati includono calcoli, in base alle impostazioni e ai parametri di input, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="5ae80-116">The results include calculations , based on settings and input parameters, such as:</span></span>
  
- <span data-ttu-id="5ae80-117">Testare le statistiche di esempio del numero di file in un esempio e identificare i file rilevanti.</span><span class="sxs-lookup"><span data-stu-id="5ae80-117">Test sample statistics of the number of files in a sample and identified relevant files.</span></span> 
    
- <span data-ttu-id="5ae80-118">Confronto tabulare dei parametri di popolazione del set di revisione e del resto, ad esempio, il numero di file, il numero stimato di file rilevanti, la ricchezza stimata e il costo medio per la ricerca di un altro file pertinente.</span><span class="sxs-lookup"><span data-stu-id="5ae80-118">Tabular comparison of the Population parameters of the Review set and the Rest, for example, the number of files, estimated number of relevant files, estimated richness, and the average cost of finding an additional relevant file.</span></span> <span data-ttu-id="5ae80-119">Le impostazioni dei parametri di costo possono essere impostate dall'amministratore.</span><span class="sxs-lookup"><span data-stu-id="5ae80-119">Cost parameter settings can be set by the administrator.</span></span>
    
1. <span data-ttu-id="5ae80-120">Aprire la scheda \*\* \> test pertinenza\*\* .</span><span class="sxs-lookup"><span data-stu-id="5ae80-120">Open the **Relevance \> Test** tab.</span></span> 
    
2. <span data-ttu-id="5ae80-121">Nella scheda **test** fare clic su **nuovo test**.</span><span class="sxs-lookup"><span data-stu-id="5ae80-121">In the **Test** tab, click **New test**.</span></span> <span data-ttu-id="5ae80-122">Viene visualizzata la finestra di dialogo **Crea test** , come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="5ae80-122">The **Create test** dialog is displayed, as shown in the following example.</span></span> 
    
    ![Risultati del test sull'inattività di pertinenza](media/46e6898a-f929-4fd0-88d9-6f91d04b6ce2.png)
  
3. <span data-ttu-id="5ae80-124">In **nome test**e **Descrizione**digitare il nome e la descrizione.</span><span class="sxs-lookup"><span data-stu-id="5ae80-124">In **Test name**, and **Description**, type the name and description.</span></span>
    
4. <span data-ttu-id="5ae80-125">Nell'elenco **tipo di test** , selezionare **test the rest**</span><span class="sxs-lookup"><span data-stu-id="5ae80-125">In the **Test type** list, select **Test the Rest**</span></span>
    
5. <span data-ttu-id="5ae80-126">Nell'elenco **problema/categoria** selezionare il nome del problema.</span><span class="sxs-lookup"><span data-stu-id="5ae80-126">In the **Issue / Category** list, select the issue name.</span></span> 
    
6. <span data-ttu-id="5ae80-127">Nell'elenco **carico** selezionare il carico.</span><span class="sxs-lookup"><span data-stu-id="5ae80-127">In the **Load** list, select the load.</span></span> 
    
7. <span data-ttu-id="5ae80-128">In **lettura%**, accettare il valore predefinito o selezionare un valore per il Punteggio di pertinenza del cutoff.</span><span class="sxs-lookup"><span data-stu-id="5ae80-128">In **Read %**, accept the default value or select a value for the cutoff Relevance score.</span></span> 
    
8. <span data-ttu-id="5ae80-129">In **Dimensioni set**oppure accettare il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="5ae80-129">In **Set size**, or accept the default value.</span></span> <span data-ttu-id="5ae80-130">Si noti che le icone di ripristino ripristineranno i valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="5ae80-130">Note that the restore icons will restore the default values.</span></span>
    
9. <span data-ttu-id="5ae80-131">Fare clic su **Avvia tagging**.</span><span class="sxs-lookup"><span data-stu-id="5ae80-131">Click **Start tagging**.</span></span> <span data-ttu-id="5ae80-132">Viene generato un esempio di test.</span><span class="sxs-lookup"><span data-stu-id="5ae80-132">A test sample is generated.</span></span>
    
10. <span data-ttu-id="5ae80-133">Esaminare e contrassegnare ognuno dei file nella scheda \*\* \> Tag pertinenza\*\* e, al termine, fare clic su **Calcola**.</span><span class="sxs-lookup"><span data-stu-id="5ae80-133">Review and tag each of the files in the **Relevance \> Tag** tab and when done, click **Calculate**.</span></span>
    
11. <span data-ttu-id="5ae80-134">Nella scheda test è possibile fare clic su **Visualizza risultati** per visualizzare i risultati dei test.</span><span class="sxs-lookup"><span data-stu-id="5ae80-134">In the Test tab, you can click **View results** to see the test results.</span></span> <span data-ttu-id="5ae80-135">Un esempio è illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="5ae80-135">An example is shown in the following figure.</span></span> 
    
    ![Risultati del test sull'inattività](media/b95744a9-047d-4c29-992d-04fa7e58e58a.png)
  
<span data-ttu-id="5ae80-137">Nella figura precedente la sezione **parametri di esempio** della tabella contiene informazioni dettagliate sul numero di file nell'esempio contrassegnati dall'esperto e sul numero di file rilevanti presenti in tale esempio.</span><span class="sxs-lookup"><span data-stu-id="5ae80-137">In the figure above, the **Sample parameters** section of the table contains details about the number of files in the sample tagged by the expert, and the number of relevant files found in that sample.</span></span> 
  
<span data-ttu-id="5ae80-138">La sezione relativa ai **parametri di popolamento** della tabella contiene i risultati dei test, tra cui la popolazione del set di riesame di file con un punteggio al di sotto del cutoff selezionato e la popolazione di file con un punteggio sopra il taglio selezionato.</span><span class="sxs-lookup"><span data-stu-id="5ae80-138">The **Population parameters** section of the table contains the test results, including the Review set population of files with a score below the selected cutoff and "The Rest" population of files with a score above the selected cutoff.</span></span> <span data-ttu-id="5ae80-139">Per ogni popolazione, vengono visualizzati i risultati seguenti:</span><span class="sxs-lookup"><span data-stu-id="5ae80-139">For each population, the following results are displayed:</span></span> 
  
- <span data-ttu-id="5ae80-140">Include i file con il cutoff lettura%-dichiarato</span><span class="sxs-lookup"><span data-stu-id="5ae80-140">Includes files with read % - Stated cutoff</span></span>
    
- <span data-ttu-id="5ae80-141">Il numero totale di file</span><span class="sxs-lookup"><span data-stu-id="5ae80-141">The total number of files</span></span> 
    
- <span data-ttu-id="5ae80-142">Il numero stimato di file rilevanti</span><span class="sxs-lookup"><span data-stu-id="5ae80-142">The estimated number of relevant files</span></span> 
    
- <span data-ttu-id="5ae80-143">La ricchezza stimata</span><span class="sxs-lookup"><span data-stu-id="5ae80-143">The estimated richness</span></span> 
    
- <span data-ttu-id="5ae80-144">Il costo di revisione medio per la ricerca di un altro file pertinente</span><span class="sxs-lookup"><span data-stu-id="5ae80-144">The average review cost of finding another relevant file</span></span>
    
## <a name="testing-the-slice"></a><span data-ttu-id="5ae80-145">Test della sezione</span><span class="sxs-lookup"><span data-stu-id="5ae80-145">Testing the slice</span></span>

<span data-ttu-id="5ae80-146">Il test "test Slice" esegue test analogo al test "test the rest", ma a un segmento del set di file specificato dalla pertinenza lettura%.</span><span class="sxs-lookup"><span data-stu-id="5ae80-146">The "Test the Slice" test performs testing similar to the "Test the Rest" test, but to a segment of the file set as specified by Relevance Read %.</span></span>
  
1. <span data-ttu-id="5ae80-147">Aprire la scheda \*\* \> test pertinenza\*\* .</span><span class="sxs-lookup"><span data-stu-id="5ae80-147">Open the **Relevance \> Test** tab.</span></span> 
    
2. <span data-ttu-id="5ae80-148">Nella scheda **test** fare clic su **nuovo test**.</span><span class="sxs-lookup"><span data-stu-id="5ae80-148">In the **Test** tab, click **New test**.</span></span> <span data-ttu-id="5ae80-149">Viene visualizzata la finestra di dialogo **Crea test** .</span><span class="sxs-lookup"><span data-stu-id="5ae80-149">The **Create test** dialog is displayed.</span></span> 
    
3. <span data-ttu-id="5ae80-150">In **nome** e **Descrizione**del test, digitare le informazioni.</span><span class="sxs-lookup"><span data-stu-id="5ae80-150">In **Test name** and **Description**, type the information.</span></span>
    
4. <span data-ttu-id="5ae80-151">Nell'elenco **tipo di test** selezionare **Verifica la sezione**.</span><span class="sxs-lookup"><span data-stu-id="5ae80-151">In the **Test type** list, select **Test the Slice**.</span></span>
    
5. <span data-ttu-id="5ae80-152">Nell'elenco **problema** selezionare il nome del problema.</span><span class="sxs-lookup"><span data-stu-id="5ae80-152">In the **Issue** list, select the issue name.</span></span> 
    
6. <span data-ttu-id="5ae80-153">Nell'elenco **carico** selezionare il carico.</span><span class="sxs-lookup"><span data-stu-id="5ae80-153">In the **Load** list, select the load.</span></span> 
    
7. <span data-ttu-id="5ae80-154">In **lettura% tra**, accettare i valori predefiniti di intervallo basso e alto o selezionare i valori per i punteggi di rilevanza del cutoff.</span><span class="sxs-lookup"><span data-stu-id="5ae80-154">In **Read % between**, accept the default low and high range values or select values for the cutoff Relevance scores.</span></span> 
    
8. <span data-ttu-id="5ae80-155">In **Dimensioni set**selezionare un valore o accettare il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="5ae80-155">In **Set size**, select a value or accept the default value.</span></span>
    
    <span data-ttu-id="5ae80-156">Le icone di ripristino ripristineranno il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="5ae80-156">The restore icons will restore the default value.</span></span>
    
9. <span data-ttu-id="5ae80-157">Fare clic su **Avvia tagging**.</span><span class="sxs-lookup"><span data-stu-id="5ae80-157">Click **Start tagging**.</span></span> <span data-ttu-id="5ae80-158">Viene generato un esempio di test.</span><span class="sxs-lookup"><span data-stu-id="5ae80-158">A test sample is generated.</span></span>
    
10. <span data-ttu-id="5ae80-159">Esaminare e contrassegnare ognuno dei file nella scheda \*\* \> Tag pertinenza\*\* e, al termine, fare clic su **Calcola**.</span><span class="sxs-lookup"><span data-stu-id="5ae80-159">Review and tag each of the files in the **Relevance \> Tag** tab and when done, click **Calculate**.</span></span> 
    
11. <span data-ttu-id="5ae80-160">Nella scheda test è possibile fare clic su **Visualizza risultati** per visualizzare i risultati dei test.</span><span class="sxs-lookup"><span data-stu-id="5ae80-160">In the Test tab, you can click **View results** to see the test results.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="5ae80-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5ae80-161">See also</span></span>

[<span data-ttu-id="5ae80-162">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="5ae80-162">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="5ae80-163">Informazioni sulla valutazione in rilevanza</span><span class="sxs-lookup"><span data-stu-id="5ae80-163">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="5ae80-164">Tagging e valutazione</span><span class="sxs-lookup"><span data-stu-id="5ae80-164">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="5ae80-165">Formazione di tagging e pertinenza</span><span class="sxs-lookup"><span data-stu-id="5ae80-165">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="5ae80-166">Verifica dell'analisi della pertinenza</span><span class="sxs-lookup"><span data-stu-id="5ae80-166">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="5ae80-167">Decidere in base ai risultati</span><span class="sxs-lookup"><span data-stu-id="5ae80-167">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)

