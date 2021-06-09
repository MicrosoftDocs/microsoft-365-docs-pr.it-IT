---
title: Testare l'analisi della rilevanza in Advanced eDiscovery
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
description: Informazioni su come usare la scheda Test dopo il calcolo batch in Advanced eDiscovery per testare, confrontare e convalidare la qualità complessiva dell'elaborazione.
ms.openlocfilehash: 3ac12c176f2e46ac0321976a7e0689fbd8893bba
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769171"
---
# <a name="test-relevance-analysis-in-advanced-ediscovery"></a><span data-ttu-id="bd251-103">Testare l'analisi della rilevanza in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="bd251-103">Test Relevance analysis in Advanced eDiscovery</span></span>
  
<span data-ttu-id="bd251-104">La scheda Test in Advanced eDiscovery consente di testare, confrontare e convalidare la qualità complessiva dell'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="bd251-104">The Test tab in Advanced eDiscovery enables you to test, compare, and validate the overall quality of processing.</span></span> <span data-ttu-id="bd251-105">Questi test vengono eseguiti dopo il calcolo batch.</span><span class="sxs-lookup"><span data-stu-id="bd251-105">These tests are performed after Batch calculation.</span></span> <span data-ttu-id="bd251-106">Contrassegnando i file nella raccolta, un esperto prende il giudizio finale sull'eventuale pertinente caso di ogni file con tag.</span><span class="sxs-lookup"><span data-stu-id="bd251-106">By tagging the files in the collection, an expert makes the final judgment about whether each tagged file is relevant to the case.</span></span>
  
<span data-ttu-id="bd251-107">In scenari a singolo e a più problemi, i test vengono in genere eseguiti per ogni problema.</span><span class="sxs-lookup"><span data-stu-id="bd251-107">In single and multiple-issue scenarios, tests are typically performed per issue.</span></span> <span data-ttu-id="bd251-108">I risultati possono essere visualizzati dopo ogni test e i risultati dei test possono essere rielaborati con i file di test di esempio specificati.</span><span class="sxs-lookup"><span data-stu-id="bd251-108">Results can be viewed after each test, and test results can be reworked with specified sample test files.</span></span>
  
## <a name="testing-the-rest"></a><span data-ttu-id="bd251-109">Test del resto</span><span class="sxs-lookup"><span data-stu-id="bd251-109">Testing the rest</span></span>

<span data-ttu-id="bd251-110">Il test "Test the Rest" viene utilizzato per convalidare le decisioni diculling, ad esempio per esaminare solo i file al di sopra di uno specifico punteggio di pertinenza in base ai risultati Advanced eDiscovery finale.</span><span class="sxs-lookup"><span data-stu-id="bd251-110">The "Test the Rest" test is used to validate culling decisions, for example, to review only files above a specific Relevance cutoff score based on the final Advanced eDiscovery results.</span></span> <span data-ttu-id="bd251-111">L'esperto esamina un campione di file con un punteggio di cutoff selezionato per valutare il numero di file pertinenti all'interno del set.</span><span class="sxs-lookup"><span data-stu-id="bd251-111">The expert reviews a sample of files under a selected cutoff score to evaluate the number of relevant files within that set.</span></span>
  
<span data-ttu-id="bd251-112">Questo test fornisce statistiche e un confronto tra l'insieme Review e la popolazione Test the Rest.</span><span class="sxs-lookup"><span data-stu-id="bd251-112">This test provides statistics and a comparison between the Review set and the Test the Rest population.</span></span> <span data-ttu-id="bd251-113">I risultati del set di revisioni sono quelli calcolati in base alla pertinenza durante la formazione.</span><span class="sxs-lookup"><span data-stu-id="bd251-113">The results of the review set are those calculated by Relevance during Training.</span></span> <span data-ttu-id="bd251-114">I risultati includono calcoli basati su impostazioni e parametri di input, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="bd251-114">The results include calculations based on settings and input parameters, such as:</span></span>
  
- <span data-ttu-id="bd251-115">Testare le statistiche di esempio del numero di file in un esempio e identificare i file pertinenti.</span><span class="sxs-lookup"><span data-stu-id="bd251-115">Test sample statistics of the number of files in a sample and identified relevant files.</span></span>

- <span data-ttu-id="bd251-116">Confronto tabulare dei parametri Population dell'insieme Review e rest, ad esempio, il numero di file, il numero stimato di file pertinenti, la quantità stimata e il costo medio di ricerca di un altro file rilevante.</span><span class="sxs-lookup"><span data-stu-id="bd251-116">Tabular comparison of the Population parameters of the Review set and the Rest, for example, the number of files, estimated number of relevant files, estimated richness, and the average cost of finding another relevant file.</span></span> <span data-ttu-id="bd251-117">Le impostazioni dei parametri di costo possono essere impostate dall'amministratore.</span><span class="sxs-lookup"><span data-stu-id="bd251-117">Cost parameter settings can be set by the administrator.</span></span>

<span data-ttu-id="bd251-118">Per eseguire il test "Test the Rest":</span><span class="sxs-lookup"><span data-stu-id="bd251-118">To run the "Test the Rest" test:</span></span>

1. <span data-ttu-id="bd251-119">Aprire la **scheda Test \> di pertinenza.**</span><span class="sxs-lookup"><span data-stu-id="bd251-119">Open the **Relevance \> Test** tab.</span></span>

2. <span data-ttu-id="bd251-120">Nella scheda **Test** fare clic su **Nuovo test.**</span><span class="sxs-lookup"><span data-stu-id="bd251-120">In the **Test** tab, click **New test**.</span></span> <span data-ttu-id="bd251-121">Viene **visualizzata la** finestra di dialogo Crea test, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="bd251-121">The **Create test** dialog is displayed, as shown in the following example.</span></span>

    ![Risultati del test sull'inattività di pertinenza](../media/46e6898a-f929-4fd0-88d9-6f91d04b6ce2.png)
  
3. <span data-ttu-id="bd251-123">In **Nome test** e **Descrizione** digitare il nome e la descrizione.</span><span class="sxs-lookup"><span data-stu-id="bd251-123">In **Test name**, and **Description**, type the name and description.</span></span>

4. <span data-ttu-id="bd251-124">**Nell'elenco Tipo di** test selezionare Test il **resto**</span><span class="sxs-lookup"><span data-stu-id="bd251-124">In the **Test type** list, select **Test the Rest**</span></span>

5. <span data-ttu-id="bd251-125">**Nell'elenco Problema/Categoria** selezionare il nome del problema.</span><span class="sxs-lookup"><span data-stu-id="bd251-125">In the **Issue / Category** list, select the issue name.</span></span>

6. <span data-ttu-id="bd251-126">**Nell'elenco Carica** selezionare il carico.</span><span class="sxs-lookup"><span data-stu-id="bd251-126">In the **Load** list, select the load.</span></span> 

7. <span data-ttu-id="bd251-127">In **Lettura %** accettare il valore predefinito o selezionare un valore per il punteggio di rilevanza limite.</span><span class="sxs-lookup"><span data-stu-id="bd251-127">In **Read %**, accept the default value or select a value for the cutoff Relevance score.</span></span> 

8. <span data-ttu-id="bd251-128">In **Imposta dimensioni** o accetta il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="bd251-128">In **Set size**, or accept the default value.</span></span> <span data-ttu-id="bd251-129">Le icone di ripristino ripristinano i valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="bd251-129">The restore icons will restore the default values.</span></span>

9. <span data-ttu-id="bd251-130">Fare **clic su Avvia tagging**.</span><span class="sxs-lookup"><span data-stu-id="bd251-130">Click **Start tagging**.</span></span> <span data-ttu-id="bd251-131">Viene generato un esempio di test.</span><span class="sxs-lookup"><span data-stu-id="bd251-131">A test sample is generated.</span></span>

10. <span data-ttu-id="bd251-132">Esaminare e contrassegnare ogni file nella scheda **Tag \>** di pertinenza e, al termine, fare clic su **Calcola**.</span><span class="sxs-lookup"><span data-stu-id="bd251-132">Review and tag each of the files in the **Relevance \> Tag** tab and when done, click **Calculate**.</span></span>

11. <span data-ttu-id="bd251-133">Nella scheda Test è possibile fare clic **su Visualizza risultati** per visualizzare i risultati del test.</span><span class="sxs-lookup"><span data-stu-id="bd251-133">In the Test tab, you can click **View results** to see the test results.</span></span> <span data-ttu-id="bd251-134">Nella schermata seguente viene mostrato un esempio.</span><span class="sxs-lookup"><span data-stu-id="bd251-134">An example is shown in the following screenshot.</span></span>

    ![Risultati del test sull'inattività](../media/b95744a9-047d-4c29-992d-04fa7e58e58a.png)
  
<span data-ttu-id="bd251-136">Nello screenshot precedente, la sezione **Parametri** di esempio della tabella contiene informazioni dettagliate sul numero di file nell'esempio contrassegnati dall'esperto e sul numero di file pertinenti trovati nell'esempio.</span><span class="sxs-lookup"><span data-stu-id="bd251-136">In the previous screenshot, the **Sample parameters** section of the table contains details about the number of files in the sample tagged by the expert, and the number of relevant files found in that sample.</span></span>
  
<span data-ttu-id="bd251-137">La  sezione Parametri di popolamento della tabella contiene i risultati del test, inclusa la popolazione impostata di revisione dei file con un punteggio al di sotto del limite selezionato e la popolazione "Resto" di file con un punteggio sopra il limite selezionato.</span><span class="sxs-lookup"><span data-stu-id="bd251-137">The **Population parameters** section of the table contains the test results, including the Review set population of files with a score below the selected cutoff and "The Rest" population of files with a score above the selected cutoff.</span></span> <span data-ttu-id="bd251-138">Per ogni popolazione vengono visualizzati i risultati seguenti:</span><span class="sxs-lookup"><span data-stu-id="bd251-138">For each population, the following results are displayed:</span></span>
  
- <span data-ttu-id="bd251-139">Include i file con lettura % - Cutoff dichiarato</span><span class="sxs-lookup"><span data-stu-id="bd251-139">Includes files with read % - Stated cutoff</span></span>

- <span data-ttu-id="bd251-140">Numero totale di file</span><span class="sxs-lookup"><span data-stu-id="bd251-140">The total number of files</span></span>

- <span data-ttu-id="bd251-141">Numero stimato di file pertinenti</span><span class="sxs-lookup"><span data-stu-id="bd251-141">The estimated number of relevant files</span></span>

- <span data-ttu-id="bd251-142">La ricchezza stimata</span><span class="sxs-lookup"><span data-stu-id="bd251-142">The estimated richness</span></span>

- <span data-ttu-id="bd251-143">Costo medio di revisione della ricerca di un altro file pertinente</span><span class="sxs-lookup"><span data-stu-id="bd251-143">The average review cost of finding another relevant file</span></span>

## <a name="testing-the-slice"></a><span data-ttu-id="bd251-144">Test della sezione</span><span class="sxs-lookup"><span data-stu-id="bd251-144">Testing the slice</span></span>

<span data-ttu-id="bd251-145">Il test "Test the Slice" esegue test simili al test "Test the Rest", ma a un segmento del set di file come specificato da Relevance Read %.</span><span class="sxs-lookup"><span data-stu-id="bd251-145">The "Test the Slice" test performs testing similar to the "Test the Rest" test, but to a segment of the file set as specified by Relevance Read %.</span></span>

<span data-ttu-id="bd251-146">Per eseguire il test "Test the Slice":</span><span class="sxs-lookup"><span data-stu-id="bd251-146">To run the "Test the Slice" test:</span></span>
  
1. <span data-ttu-id="bd251-147">Aprire la **scheda Test \> di pertinenza.**</span><span class="sxs-lookup"><span data-stu-id="bd251-147">Open the **Relevance \> Test** tab.</span></span>

2. <span data-ttu-id="bd251-148">Nella scheda **Test** fare clic su **Nuovo test.**</span><span class="sxs-lookup"><span data-stu-id="bd251-148">In the **Test** tab, click **New test**.</span></span> <span data-ttu-id="bd251-149">Verrà **visualizzata la finestra** di dialogo Crea test.</span><span class="sxs-lookup"><span data-stu-id="bd251-149">The **Create test** dialog is displayed.</span></span>

3. <span data-ttu-id="bd251-150">In **Nome test** e **Descrizione** digitare le informazioni.</span><span class="sxs-lookup"><span data-stu-id="bd251-150">In **Test name** and **Description**, type the information.</span></span>

4. <span data-ttu-id="bd251-151">**Nell'elenco Tipo di** test selezionare Testa la **sezione**.</span><span class="sxs-lookup"><span data-stu-id="bd251-151">In the **Test type** list, select **Test the Slice**.</span></span>

5. <span data-ttu-id="bd251-152">**Nell'elenco Problema** selezionare il nome del problema.</span><span class="sxs-lookup"><span data-stu-id="bd251-152">In the **Issue** list, select the issue name.</span></span>

6. <span data-ttu-id="bd251-153">**Nell'elenco Carica** selezionare il carico.</span><span class="sxs-lookup"><span data-stu-id="bd251-153">In the **Load** list, select the load.</span></span>

7. <span data-ttu-id="bd251-154">In **Lettura % tra**, accettare i valori di intervallo basso e alto predefiniti o selezionare i valori per i punteggi di rilevanza limite.</span><span class="sxs-lookup"><span data-stu-id="bd251-154">In **Read % between**, accept the default low and high range values or select values for the cutoff Relevance scores.</span></span>

8. <span data-ttu-id="bd251-155">In **Imposta dimensioni** selezionare un valore o accettare il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="bd251-155">In **Set size**, select a value or accept the default value.</span></span>

    <span data-ttu-id="bd251-156">Le icone di ripristino ripristinano il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="bd251-156">The restore icons will restore the default value.</span></span>

9. <span data-ttu-id="bd251-157">Fare **clic su Avvia tagging**.</span><span class="sxs-lookup"><span data-stu-id="bd251-157">Click **Start tagging**.</span></span> <span data-ttu-id="bd251-158">Viene generato un esempio di test.</span><span class="sxs-lookup"><span data-stu-id="bd251-158">A test sample is generated.</span></span>

10. <span data-ttu-id="bd251-159">Esaminare e contrassegnare ogni file nella scheda **Tag \>** di pertinenza e, al termine, fare clic su **Calcola**.</span><span class="sxs-lookup"><span data-stu-id="bd251-159">Review and tag each of the files in the **Relevance \> Tag** tab and when done, click **Calculate**.</span></span>

11. <span data-ttu-id="bd251-160">Nella scheda Test è possibile fare clic **su Visualizza risultati** per visualizzare i risultati del test.</span><span class="sxs-lookup"><span data-stu-id="bd251-160">In the Test tab, you can click **View results** to see the test results.</span></span>
