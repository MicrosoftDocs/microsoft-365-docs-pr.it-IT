---
title: Analisi della pertinenza del test in Advanced eDiscovery
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
ms.assetid: 1b092f7c-ea55-44f5-b419-63f3458fd7e0
ROBOTS: NOINDEX, NOFOLLOW
description: Informazioni su come utilizzare la scheda test dopo il calcolo batch in Advanced eDiscovery per testare, confrontare e convalidare la qualità complessiva dell'elaborazione.
ms.openlocfilehash: 3ac12c176f2e46ac0321976a7e0689fbd8893bba
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769171"
---
# <a name="test-relevance-analysis-in-advanced-ediscovery"></a><span data-ttu-id="a4e2f-103">Analisi della pertinenza del test in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="a4e2f-103">Test Relevance analysis in Advanced eDiscovery</span></span>
  
<span data-ttu-id="a4e2f-104">La scheda test in Advanced eDiscovery consente di testare, confrontare e convalidare la qualità complessiva dell'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="a4e2f-104">The Test tab in Advanced eDiscovery enables you to test, compare, and validate the overall quality of processing.</span></span> <span data-ttu-id="a4e2f-105">Questi test vengono eseguiti dopo il calcolo in batch.</span><span class="sxs-lookup"><span data-stu-id="a4e2f-105">These tests are performed after Batch calculation.</span></span> <span data-ttu-id="a4e2f-106">Contrassegnando i file della raccolta, un esperto prende il giudizio finale sul fatto che ogni file Tagged è pertinente per il caso.</span><span class="sxs-lookup"><span data-stu-id="a4e2f-106">By tagging the files in the collection, an expert makes the final judgment about whether each tagged file is relevant to the case.</span></span>
  
<span data-ttu-id="a4e2f-107">In scenari con problemi singoli e multipli i test vengono in genere eseguiti per ogni problema.</span><span class="sxs-lookup"><span data-stu-id="a4e2f-107">In single and multiple-issue scenarios, tests are typically performed per issue.</span></span> <span data-ttu-id="a4e2f-108">I risultati possono essere visualizzati dopo ogni test e i risultati dei test possono essere rielaborati con i file di test di esempio specificati.</span><span class="sxs-lookup"><span data-stu-id="a4e2f-108">Results can be viewed after each test, and test results can be reworked with specified sample test files.</span></span>
  
## <a name="testing-the-rest"></a><span data-ttu-id="a4e2f-109">Verifica del resto</span><span class="sxs-lookup"><span data-stu-id="a4e2f-109">Testing the rest</span></span>

<span data-ttu-id="a4e2f-110">Il test "test the rest" viene utilizzato per convalidare le decisioni di eliminazione, ad esempio per esaminare solo i file al di sopra di un punteggio di taglio di rilevanza specifico in base ai risultati avanzati di eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="a4e2f-110">The "Test the Rest" test is used to validate culling decisions, for example, to review only files above a specific Relevance cutoff score based on the final Advanced eDiscovery results.</span></span> <span data-ttu-id="a4e2f-111">L'esperto esamina un campione di file con un punteggio di taglio selezionato per valutare il numero di file rilevanti all'interno di tale set.</span><span class="sxs-lookup"><span data-stu-id="a4e2f-111">The expert reviews a sample of files under a selected cutoff score to evaluate the number of relevant files within that set.</span></span>
  
<span data-ttu-id="a4e2f-112">Questo test fornisce statistiche e un confronto tra il set di revisione e il test del popolamento Rest.</span><span class="sxs-lookup"><span data-stu-id="a4e2f-112">This test provides statistics and a comparison between the Review set and the Test the Rest population.</span></span> <span data-ttu-id="a4e2f-113">I risultati del set di revisione sono quelli calcolati per pertinenza durante l'allenamento.</span><span class="sxs-lookup"><span data-stu-id="a4e2f-113">The results of the review set are those calculated by Relevance during Training.</span></span> <span data-ttu-id="a4e2f-114">I risultati includono calcoli basati su impostazioni e parametri di input, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="a4e2f-114">The results include calculations based on settings and input parameters, such as:</span></span>
  
- <span data-ttu-id="a4e2f-115">Testare le statistiche di esempio del numero di file in un esempio e identificare i file rilevanti.</span><span class="sxs-lookup"><span data-stu-id="a4e2f-115">Test sample statistics of the number of files in a sample and identified relevant files.</span></span>

- <span data-ttu-id="a4e2f-116">Confronto tabulare dei parametri di popolazione del set di revisione e del resto, ad esempio, il numero di file, il numero stimato di file rilevanti, la ricchezza stimata e il costo medio per la ricerca di un altro file pertinente.</span><span class="sxs-lookup"><span data-stu-id="a4e2f-116">Tabular comparison of the Population parameters of the Review set and the Rest, for example, the number of files, estimated number of relevant files, estimated richness, and the average cost of finding another relevant file.</span></span> <span data-ttu-id="a4e2f-117">Le impostazioni dei parametri di costo possono essere impostate dall'amministratore.</span><span class="sxs-lookup"><span data-stu-id="a4e2f-117">Cost parameter settings can be set by the administrator.</span></span>

<span data-ttu-id="a4e2f-118">Per eseguire il test "test the rest":</span><span class="sxs-lookup"><span data-stu-id="a4e2f-118">To run the "Test the Rest" test:</span></span>

1. <span data-ttu-id="a4e2f-119">Aprire la scheda **\> test pertinenza** .</span><span class="sxs-lookup"><span data-stu-id="a4e2f-119">Open the **Relevance \> Test** tab.</span></span>

2. <span data-ttu-id="a4e2f-120">Nella scheda **test** fare clic su **nuovo test**.</span><span class="sxs-lookup"><span data-stu-id="a4e2f-120">In the **Test** tab, click **New test**.</span></span> <span data-ttu-id="a4e2f-121">Viene visualizzata la finestra di dialogo **Crea test** , come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="a4e2f-121">The **Create test** dialog is displayed, as shown in the following example.</span></span>

    ![Risultati del test sull'inattività di pertinenza](../media/46e6898a-f929-4fd0-88d9-6f91d04b6ce2.png)
  
3. <span data-ttu-id="a4e2f-123">In **nome test** e **Descrizione** digitare il nome e la descrizione.</span><span class="sxs-lookup"><span data-stu-id="a4e2f-123">In **Test name**, and **Description**, type the name and description.</span></span>

4. <span data-ttu-id="a4e2f-124">Nell'elenco **tipo di test** , selezionare **test the rest**</span><span class="sxs-lookup"><span data-stu-id="a4e2f-124">In the **Test type** list, select **Test the Rest**</span></span>

5. <span data-ttu-id="a4e2f-125">Nell'elenco **problema/categoria** selezionare il nome del problema.</span><span class="sxs-lookup"><span data-stu-id="a4e2f-125">In the **Issue / Category** list, select the issue name.</span></span>

6. <span data-ttu-id="a4e2f-126">Nell'elenco **carico** selezionare il carico.</span><span class="sxs-lookup"><span data-stu-id="a4e2f-126">In the **Load** list, select the load.</span></span> 

7. <span data-ttu-id="a4e2f-127">In **lettura%**, accettare il valore predefinito o selezionare un valore per il Punteggio di pertinenza del cutoff.</span><span class="sxs-lookup"><span data-stu-id="a4e2f-127">In **Read %**, accept the default value or select a value for the cutoff Relevance score.</span></span> 

8. <span data-ttu-id="a4e2f-128">In **Dimensioni set** oppure accettare il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="a4e2f-128">In **Set size**, or accept the default value.</span></span> <span data-ttu-id="a4e2f-129">Le icone di ripristino ripristineranno i valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="a4e2f-129">The restore icons will restore the default values.</span></span>

9. <span data-ttu-id="a4e2f-130">Fare clic su **Avvia tagging**.</span><span class="sxs-lookup"><span data-stu-id="a4e2f-130">Click **Start tagging**.</span></span> <span data-ttu-id="a4e2f-131">Viene generato un esempio di test.</span><span class="sxs-lookup"><span data-stu-id="a4e2f-131">A test sample is generated.</span></span>

10. <span data-ttu-id="a4e2f-132">Esaminare e contrassegnare ognuno dei file nella scheda **\> tag pertinenza** e, al termine, fare clic su **Calcola**.</span><span class="sxs-lookup"><span data-stu-id="a4e2f-132">Review and tag each of the files in the **Relevance \> Tag** tab and when done, click **Calculate**.</span></span>

11. <span data-ttu-id="a4e2f-133">Nella scheda test è possibile fare clic su **Visualizza risultati** per visualizzare i risultati dei test.</span><span class="sxs-lookup"><span data-stu-id="a4e2f-133">In the Test tab, you can click **View results** to see the test results.</span></span> <span data-ttu-id="a4e2f-134">Un esempio è illustrato nella schermata seguente.</span><span class="sxs-lookup"><span data-stu-id="a4e2f-134">An example is shown in the following screenshot.</span></span>

    ![Risultati del test sull'inattività](../media/b95744a9-047d-4c29-992d-04fa7e58e58a.png)
  
<span data-ttu-id="a4e2f-136">Nella schermata precedente la sezione **parametri di esempio** della tabella contiene informazioni dettagliate sul numero di file nell'esempio contrassegnati dall'esperto e sul numero di file rilevanti trovati in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="a4e2f-136">In the previous screenshot, the **Sample parameters** section of the table contains details about the number of files in the sample tagged by the expert, and the number of relevant files found in that sample.</span></span>
  
<span data-ttu-id="a4e2f-137">La sezione relativa ai **parametri di popolamento** della tabella contiene i risultati dei test, tra cui la popolazione del set di riesame di file con un punteggio al di sotto del cutoff selezionato e la popolazione di file con un punteggio sopra il taglio selezionato.</span><span class="sxs-lookup"><span data-stu-id="a4e2f-137">The **Population parameters** section of the table contains the test results, including the Review set population of files with a score below the selected cutoff and "The Rest" population of files with a score above the selected cutoff.</span></span> <span data-ttu-id="a4e2f-138">Per ogni popolazione, vengono visualizzati i risultati seguenti:</span><span class="sxs-lookup"><span data-stu-id="a4e2f-138">For each population, the following results are displayed:</span></span>
  
- <span data-ttu-id="a4e2f-139">Include i file con il cutoff lettura%-dichiarato</span><span class="sxs-lookup"><span data-stu-id="a4e2f-139">Includes files with read % - Stated cutoff</span></span>

- <span data-ttu-id="a4e2f-140">Il numero totale di file</span><span class="sxs-lookup"><span data-stu-id="a4e2f-140">The total number of files</span></span>

- <span data-ttu-id="a4e2f-141">Il numero stimato di file rilevanti</span><span class="sxs-lookup"><span data-stu-id="a4e2f-141">The estimated number of relevant files</span></span>

- <span data-ttu-id="a4e2f-142">La ricchezza stimata</span><span class="sxs-lookup"><span data-stu-id="a4e2f-142">The estimated richness</span></span>

- <span data-ttu-id="a4e2f-143">Il costo di revisione medio per la ricerca di un altro file pertinente</span><span class="sxs-lookup"><span data-stu-id="a4e2f-143">The average review cost of finding another relevant file</span></span>

## <a name="testing-the-slice"></a><span data-ttu-id="a4e2f-144">Test della sezione</span><span class="sxs-lookup"><span data-stu-id="a4e2f-144">Testing the slice</span></span>

<span data-ttu-id="a4e2f-145">Il test "test Slice" esegue test analogo al test "test the rest", ma a un segmento del set di file specificato dalla pertinenza lettura%.</span><span class="sxs-lookup"><span data-stu-id="a4e2f-145">The "Test the Slice" test performs testing similar to the "Test the Rest" test, but to a segment of the file set as specified by Relevance Read %.</span></span>

<span data-ttu-id="a4e2f-146">Per eseguire il test "testare la sezione":</span><span class="sxs-lookup"><span data-stu-id="a4e2f-146">To run the "Test the Slice" test:</span></span>
  
1. <span data-ttu-id="a4e2f-147">Aprire la scheda **\> test pertinenza** .</span><span class="sxs-lookup"><span data-stu-id="a4e2f-147">Open the **Relevance \> Test** tab.</span></span>

2. <span data-ttu-id="a4e2f-148">Nella scheda **test** fare clic su **nuovo test**.</span><span class="sxs-lookup"><span data-stu-id="a4e2f-148">In the **Test** tab, click **New test**.</span></span> <span data-ttu-id="a4e2f-149">Viene visualizzata la finestra di dialogo **Crea test** .</span><span class="sxs-lookup"><span data-stu-id="a4e2f-149">The **Create test** dialog is displayed.</span></span>

3. <span data-ttu-id="a4e2f-150">In **nome** e **Descrizione** del test, digitare le informazioni.</span><span class="sxs-lookup"><span data-stu-id="a4e2f-150">In **Test name** and **Description**, type the information.</span></span>

4. <span data-ttu-id="a4e2f-151">Nell'elenco **tipo di test** selezionare **Verifica la sezione**.</span><span class="sxs-lookup"><span data-stu-id="a4e2f-151">In the **Test type** list, select **Test the Slice**.</span></span>

5. <span data-ttu-id="a4e2f-152">Nell'elenco **problema** selezionare il nome del problema.</span><span class="sxs-lookup"><span data-stu-id="a4e2f-152">In the **Issue** list, select the issue name.</span></span>

6. <span data-ttu-id="a4e2f-153">Nell'elenco **carico** selezionare il carico.</span><span class="sxs-lookup"><span data-stu-id="a4e2f-153">In the **Load** list, select the load.</span></span>

7. <span data-ttu-id="a4e2f-154">In **lettura% tra**, accettare i valori predefiniti di intervallo basso e alto o selezionare i valori per i punteggi di rilevanza del cutoff.</span><span class="sxs-lookup"><span data-stu-id="a4e2f-154">In **Read % between**, accept the default low and high range values or select values for the cutoff Relevance scores.</span></span>

8. <span data-ttu-id="a4e2f-155">In **Dimensioni set** selezionare un valore o accettare il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="a4e2f-155">In **Set size**, select a value or accept the default value.</span></span>

    <span data-ttu-id="a4e2f-156">Le icone di ripristino ripristineranno il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="a4e2f-156">The restore icons will restore the default value.</span></span>

9. <span data-ttu-id="a4e2f-157">Fare clic su **Avvia tagging**.</span><span class="sxs-lookup"><span data-stu-id="a4e2f-157">Click **Start tagging**.</span></span> <span data-ttu-id="a4e2f-158">Viene generato un esempio di test.</span><span class="sxs-lookup"><span data-stu-id="a4e2f-158">A test sample is generated.</span></span>

10. <span data-ttu-id="a4e2f-159">Esaminare e contrassegnare ognuno dei file nella scheda **\> tag pertinenza** e, al termine, fare clic su **Calcola**.</span><span class="sxs-lookup"><span data-stu-id="a4e2f-159">Review and tag each of the files in the **Relevance \> Tag** tab and when done, click **Calculate**.</span></span>

11. <span data-ttu-id="a4e2f-160">Nella scheda test è possibile fare clic su **Visualizza risultati** per visualizzare i risultati dei test.</span><span class="sxs-lookup"><span data-stu-id="a4e2f-160">In the Test tab, you can click **View results** to see the test results.</span></span>
