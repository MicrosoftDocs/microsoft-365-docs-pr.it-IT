---
title: Creare un estrattore
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
description: Informazioni su come creare un estrattore in Microsoft SharePoint Syntex.
ms.openlocfilehash: 99d2a4602c03d8a7207736ea17ed500626ce43ac
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087464"
---
# <a name="create-an-extractor-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="33dc2-103">Creare un estrattore in Microsoft SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="33dc2-103">Create an extractor in Microsoft SharePoint Syntex</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL2G]

</br> 

<span data-ttu-id="33dc2-104">Prima o dopo aver creato un modello di classificazione per automatizzare l'identificazione e la classificazione di tipi di documento specifici, è possibile scegliere di aggiungere degli estrattori al modello al fine di estrarre informazioni specifiche da tali documenti.</span><span class="sxs-lookup"><span data-stu-id="33dc2-104">Before or after you create a classifier model to automate identification and classification of specific document types, you can optionally choose to add extractors to your model to pull out specific information from these documents.</span></span> <span data-ttu-id="33dc2-105">Ad esempio, si può fare in modo che il modello non solo identifichi tutti i documenti *Rinnovo del contratto* aggiunti alla raccolta documenti, ma visualizzi anche la *Data di avvio del servizio* per ogni documento come valore di colonna nella raccolta documenti.</span><span class="sxs-lookup"><span data-stu-id="33dc2-105">For example, you may want your model not only to identify all *Contract Renewal* documents added to your document library, but also to display the *Service Start date* for each document as a column value in the document library.</span></span>

<span data-ttu-id="33dc2-106">È necessario creare un estrattore per ogni entità nel documento che si vuole estrarre.</span><span class="sxs-lookup"><span data-stu-id="33dc2-106">You need to create an extractor for each entity in the document that you want to extract.</span></span> <span data-ttu-id="33dc2-107">In questo esempio si vuole estrarre la  **Data di avvio del servizio**  per ogni documento  **Rinnovo del contratto**  identificato dal modello.</span><span class="sxs-lookup"><span data-stu-id="33dc2-107">In our example, we want to extract the **Service Start Date** for each **Contract Renewal** document that is identified by the model.</span></span> <span data-ttu-id="33dc2-108">Si vuole ottenere una vista di tutti i documenti  **Rinnovo del contratto**  nella raccolta documenti, con una colonna che mostra il valore della data di **Avvio del servizio** per ogni documento.</span><span class="sxs-lookup"><span data-stu-id="33dc2-108">We want to be able to see a view in the document library of all  **Contract Renewal** documents, with a column that shows the **Service Start** date value of each document.</span></span> 

> [!NOTE]
> <span data-ttu-id="33dc2-109">Per creare un estrattore, è possibile usare gli stessi file caricati in precedenza per il training del classificatore.</span><span class="sxs-lookup"><span data-stu-id="33dc2-109">In order to create an extractor, you use the same files you previously uploaded to train the classifier.</span></span> 

## <a name="name-your-extractor"></a><span data-ttu-id="33dc2-110">Assegnare un nome all'estrattore</span><span class="sxs-lookup"><span data-stu-id="33dc2-110">Name your extractor</span></span>

1. <span data-ttu-id="33dc2-111">Nella sezione **Creare ed eseguire il training di estrattori** della home page del modello fare clic su **Eseguire il training dell'estrattore**.</span><span class="sxs-lookup"><span data-stu-id="33dc2-111">From the model home page, in the **Create and train extractors** tile, click **Train extractor**.</span></span>
2. <span data-ttu-id="33dc2-112">Nella schermata **Nuovo estrattore di entità** digitare il nome dell'estrattore nel campo **Nome del nuovo estrattore**.</span><span class="sxs-lookup"><span data-stu-id="33dc2-112">On the **New entity extractor** screen, type the name of your extractor in the **New extractor name** field.</span></span> <span data-ttu-id="33dc2-113">Ad esempio, assegnare il nome **Data di avvio del servizio** per estrarre la data di avvio del servizio da ogni documento Rinnovo del contratto.</span><span class="sxs-lookup"><span data-stu-id="33dc2-113">For example, name it **Service Start Date** if you want to extract the service start date from each Contract Renewal document.</span></span> <span data-ttu-id="33dc2-114">Si può anche decidere di riutilizzare una colonna creata in precedenza, ad esempio una colonna di metadati gestiti.</span><span class="sxs-lookup"><span data-stu-id="33dc2-114">You can also choose to reuse a previously created column (for example, a managed metadata column).</span></span>
3. <span data-ttu-id="33dc2-115">Fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="33dc2-115">Click **Create**.</span></span>

## <a name="add-a-label"></a><span data-ttu-id="33dc2-116">Aggiungere un'etichetta</span><span class="sxs-lookup"><span data-stu-id="33dc2-116">Add a label</span></span>

<span data-ttu-id="33dc2-117">Il passaggio successivo consiste nell'etichettare l'entità da estrarre nei file di training di esempio.</span><span class="sxs-lookup"><span data-stu-id="33dc2-117">The next step is to label the entity you want to extract in your example training files.</span></span>

<span data-ttu-id="33dc2-118">Quando si crea l'estrattore, viene aperta la pagina dell'estrattore.</span><span class="sxs-lookup"><span data-stu-id="33dc2-118">Creating the extractor opens the extractor page.</span></span> <span data-ttu-id="33dc2-119">In questa pagina è presente un elenco dei file di esempio e nel visualizzatore viene mostrato il primo file nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="33dc2-119">Here you see a list of your sample files, with the first file on the list displayed in the viewer.</span></span>

1. <span data-ttu-id="33dc2-120">Nel visualizzatore selezionare i dati da estrarre dai file.</span><span class="sxs-lookup"><span data-stu-id="33dc2-120">From the viewer, select the data that you want to extract from the files.</span></span> <span data-ttu-id="33dc2-121">Ad esempio, se si vuole estrarre la *Data di avvio del servizio*, evidenziare il valore della data nel primo file (*lunedì 14 ottobre 2019*),</span><span class="sxs-lookup"><span data-stu-id="33dc2-121">For example, if you want to extract the *Start Service Date*, you highlight the date value in the first file (*Monday, October 14, 2019*).</span></span> <span data-ttu-id="33dc2-122">quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="33dc2-122">and then click **Save**.</span></span>  <span data-ttu-id="33dc2-123">Il valore presente nel file dovrebbe essere visualizzato nell'elenco Esempi etichettati, nella colonna **Etichetta**.</span><span class="sxs-lookup"><span data-stu-id="33dc2-123">You should see the value display from the file in the Labeled examples list, under the **Label** column.</span></span>
2. <span data-ttu-id="33dc2-124">Selezionare **File successivo** per salvare automaticamente e aprire nel visualizzatore il file successivo nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="33dc2-124">Select **Next file** to auto save and open the next file in the list in the viewer.</span></span> <span data-ttu-id="33dc2-125">In alternativa, selezionare **Salva** e quindi selezionare un altro file nell'elenco **Esempi etichettati**.</span><span class="sxs-lookup"><span data-stu-id="33dc2-125">Or select **Save** and then select another file from the **Labeled examples** list.</span></span>
3. <span data-ttu-id="33dc2-126">Nel visualizzatore ripetere i passaggi 1 e 2, quindi ripetere fino a salvare l'etichetta in tutti e cinque i file.</span><span class="sxs-lookup"><span data-stu-id="33dc2-126">In the viewer, repeat steps 1 and 2, then repeat until you saved the label in all five files.</span></span>

    ![Impostazioni avanzate](../media/content-understanding/select-service-start-date.png) 

 
<span data-ttu-id="33dc2-128">Dopo avere etichettato cinque file, viene visualizzato un banner di notifica che indica di passare al training.</span><span class="sxs-lookup"><span data-stu-id="33dc2-128">Once you labeled five files, a notification banner displays informing you to move to training.</span></span> <span data-ttu-id="33dc2-129">È possibile decidere di etichettare altri documenti o procedere al training.</span><span class="sxs-lookup"><span data-stu-id="33dc2-129">You can choose to more label more documents or advance to training.</span></span> 

## <a name="add-an-explanation"></a><span data-ttu-id="33dc2-130">Aggiungere una spiegazione</span><span class="sxs-lookup"><span data-stu-id="33dc2-130">Add an explanation</span></span>

<span data-ttu-id="33dc2-131">In questo esempio si creerà una spiegazione che offre un suggerimento sul formato dell'entità e sulle varianti che può avere nei documenti di esempio.</span><span class="sxs-lookup"><span data-stu-id="33dc2-131">For our example, we are going to create an explanation that provides a hint about the entity format itself and variations it may have in the sample documents.</span></span> <span data-ttu-id="33dc2-132">Ad esempio, un valore di data può essere espresso in diversi formati, quali:</span><span class="sxs-lookup"><span data-stu-id="33dc2-132">For example, a date value can be in a number of different formats, such as:</span></span>
- <span data-ttu-id="33dc2-133">14/10/2019</span><span class="sxs-lookup"><span data-stu-id="33dc2-133">10/14/2019</span></span>
- <span data-ttu-id="33dc2-134">14 ottobre 2019</span><span class="sxs-lookup"><span data-stu-id="33dc2-134">October 14, 2019</span></span>
- <span data-ttu-id="33dc2-135">Lunedì 14 ottobre 2019</span><span class="sxs-lookup"><span data-stu-id="33dc2-135">Monday, October 14, 2019</span></span>
 

<span data-ttu-id="33dc2-136">Per identificare la *Data di avvio del servizio*, è possibile creare una spiegazione di tipo criteri.</span><span class="sxs-lookup"><span data-stu-id="33dc2-136">To help identify the *Service Start Date* you can create a pattern explanation.</span></span>

1. <span data-ttu-id="33dc2-137">Nella sezione Spiegazione selezionare **Nuovo** e digitare un nome, ad esempio *Data*.</span><span class="sxs-lookup"><span data-stu-id="33dc2-137">In the Explanation section, select **New** and type a name (for example, *Date*).</span></span>
2. <span data-ttu-id="33dc2-138">In Tipo selezionare **Elenco criteri**.</span><span class="sxs-lookup"><span data-stu-id="33dc2-138">For Type, select **Pattern list**.</span></span>
3. <span data-ttu-id="33dc2-139">In Valore specificare le varianti della data che appaiono nei file di esempio.</span><span class="sxs-lookup"><span data-stu-id="33dc2-139">For Value, provide the date variation as they appear in the sample files.</span></span> <span data-ttu-id="33dc2-140">Ad esempio, se sono presenti formati di data visualizzati come 0/00/0000, immettere tutte le varianti presenti nei documenti, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="33dc2-140">For example, if you have date formats that appear as 0/00/0000, you enter any variations that appear in your documents, such as:</span></span>
    - <span data-ttu-id="33dc2-141">0/0/0000</span><span class="sxs-lookup"><span data-stu-id="33dc2-141">0/0/0000</span></span>
    - <span data-ttu-id="33dc2-142">0/00/0000</span><span class="sxs-lookup"><span data-stu-id="33dc2-142">0/00/0000</span></span>
    - <span data-ttu-id="33dc2-143">00/0/0000</span><span class="sxs-lookup"><span data-stu-id="33dc2-143">00/0/0000</span></span>
    - <span data-ttu-id="33dc2-144">00/00/0000</span><span class="sxs-lookup"><span data-stu-id="33dc2-144">00/00/0000</span></span>
4. <span data-ttu-id="33dc2-145">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="33dc2-145">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="33dc2-146">Per altre informazioni sui tipi di spiegazione, vedere [Tipi di spiegazione](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview).</span><span class="sxs-lookup"><span data-stu-id="33dc2-146">For more learn more about explanation types, see [Explanation types](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview).</span></span>  


### <a name="use-the-explanation-library"></a><span data-ttu-id="33dc2-147">Usare la raccolta di spiegazioni</span><span class="sxs-lookup"><span data-stu-id="33dc2-147">Use the Explanation library</span></span>

<span data-ttu-id="33dc2-148">Per creare spiegazioni per elementi come le date, è più facile [usare la raccolta di spiegazioni](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-the-explanation-library) piuttosto che immettere manualmente tutte le varianti.</span><span class="sxs-lookup"><span data-stu-id="33dc2-148">For creating explanations for items such as dates, it is easier to [use the explanation library](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-the-explanation-library) than to manually enter all variations.</span></span> <span data-ttu-id="33dc2-149">La raccolta di spiegazioni è un set di spiegazioni predefinite di tipo frase o criteri.</span><span class="sxs-lookup"><span data-stu-id="33dc2-149">The explanation library is a set of pre-built phrase and pattern explanations.</span></span> <span data-ttu-id="33dc2-150">La raccolta cerca di fornire tutti i formati per elenchi di frasi o criteri comuni, come date, numeri di telefono, codici postali e molti altri.</span><span class="sxs-lookup"><span data-stu-id="33dc2-150">The library tries to provides all formats for common phrase or pattern lists, such as dates, phone numbers, zip codes, and many others.</span></span> 

<span data-ttu-id="33dc2-151">Per l'esempio *Data di avvio del servizio*, è più efficace usare la spiegazione predefinita per *Data* nella raccolta di spiegazioni:</span><span class="sxs-lookup"><span data-stu-id="33dc2-151">For the *Service Start Date* sample, it is more efficient to use the pre-built explanation for *Date* in the explanation library:</span></span>

1. <span data-ttu-id="33dc2-152">Nella **sezione Spiegazione** selezionare **Nuovo** e quindi **Da raccolta spiegazioni**.</span><span class="sxs-lookup"><span data-stu-id="33dc2-152">In the **Explanation section**, select **New**, and then select **From explanation library**.</span></span>
2. <span data-ttu-id="33dc2-153">Nella raccolta di spiegazioni selezionare **Data**.</span><span class="sxs-lookup"><span data-stu-id="33dc2-153">From the explanation library, select **Date**.</span></span> <span data-ttu-id="33dc2-154">Vengono visualizzate tutte le varianti di data riconosciute.</span><span class="sxs-lookup"><span data-stu-id="33dc2-154">You can view all variations of date that are recognized.</span></span>
3. <span data-ttu-id="33dc2-155">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="33dc2-155">Select **Add**.</span></span></br>

    ![Raccolta di spiegazioni](../media/content-understanding/explanation-library.png) 

4. <span data-ttu-id="33dc2-157">Nella pagina **Crea spiegazione** i campi vengono compilati automaticamente con le informazioni *Data* presenti nella raccolta di spiegazioni.</span><span class="sxs-lookup"><span data-stu-id="33dc2-157">On the **Create an explanation** page, the *Date* information from the explanation library auto fills the fields.</span></span> <span data-ttu-id="33dc2-158">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="33dc2-158">Select **Save**.</span></span></br>

    ![Data](../media/content-understanding/date-explanation-library.png) 

## <a name="train-the-model"></a><span data-ttu-id="33dc2-160">Eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="33dc2-160">Train the model</span></span> 

<span data-ttu-id="33dc2-161">Quando si salva la spiegazione, viene avviato il training.</span><span class="sxs-lookup"><span data-stu-id="33dc2-161">Saving your explanation start the training.</span></span> <span data-ttu-id="33dc2-162">Se il modello contiene informazioni sufficienti per estrarre i dati dai file di esempio etichettati, a ogni file sarà associata l'etichetta **Corrisponde**.</span><span class="sxs-lookup"><span data-stu-id="33dc2-162">If your model has enough information to extract the data from your labeled example files, you will see each file labeled with **Match**.</span></span>  

![Corrisponde](../media/content-understanding/match2.png) 

<span data-ttu-id="33dc2-164">Se la spiegazione non contiene informazioni sufficienti per individuare i dati da estrarre, a ogni file sarà associata l'etichetta **Non corrispondenti**.</span><span class="sxs-lookup"><span data-stu-id="33dc2-164">If the explanation does not have enough information to find the data you want to extract, each file will be labeled with **Mismatch**.</span></span> <span data-ttu-id="33dc2-165">È possibile fare clic sui file **Non corrispondenti** per ottenere altre informazioni sul motivo della mancata corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="33dc2-165">You can click on the **Mismatched** files to see more information about why there was a mismatch.</span></span>


## <a name="add-another-explanation"></a><span data-ttu-id="33dc2-166">Aggiungere un'altra spiegazione</span><span class="sxs-lookup"><span data-stu-id="33dc2-166">Add another explanation</span></span>

<span data-ttu-id="33dc2-167">Spesso la mancata corrispondenza indica che la spiegazione fornita non conteneva informazioni sufficienti per estrarre il valore della data di avvio del servizio per trovare una corrispondenza nei file etichettati.</span><span class="sxs-lookup"><span data-stu-id="33dc2-167">Often the mismatch is an indication that the explanation we provided did not provide enough information to extract the service start date value to match our labeled files.</span></span> <span data-ttu-id="33dc2-168">Potrebbe essere necessario modificarla o aggiungerne un'altra.</span><span class="sxs-lookup"><span data-stu-id="33dc2-168">You may need to edit it, or add another explanation.</span></span>

<span data-ttu-id="33dc2-169">In questo esempio, la stringa di testo *Data di avvio del servizio di* precede sempre il valore effettivo.</span><span class="sxs-lookup"><span data-stu-id="33dc2-169">For our example, notice that the text string *Start Service date of* always precedes the actual value.</span></span> <span data-ttu-id="33dc2-170">Per identificare la Data di avvio del servizio, è necessario creare una spiegazione di tipo frase.</span><span class="sxs-lookup"><span data-stu-id="33dc2-170">To help identify the Service Start Date, you need to create a phrase explanation.</span></span>

1. <span data-ttu-id="33dc2-171">Nella sezione Spiegazione selezionare **Nuovo** e digitare un nome, ad esempio *Stringa prefisso*.</span><span class="sxs-lookup"><span data-stu-id="33dc2-171">In the Explanation section, select **New**, and then type a name (for example, *Prefix String*).</span></span>
2. <span data-ttu-id="33dc2-172">In Tipo selezionare **Elenco frasi**.</span><span class="sxs-lookup"><span data-stu-id="33dc2-172">For the Type, select **Phrase list**.</span></span>
3. <span data-ttu-id="33dc2-173">Usare *Data di avvio del servizio di* come valore.</span><span class="sxs-lookup"><span data-stu-id="33dc2-173">Use *Service Start Date of* as the value.</span></span>
4. <span data-ttu-id="33dc2-174">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="33dc2-174">Select **Save**.</span></span>

    ![Stringa prefisso](../media/content-understanding/prefix-string.png) 

## <a name="train-the-model-again"></a><span data-ttu-id="33dc2-176">Ripetere il training del modello</span><span class="sxs-lookup"><span data-stu-id="33dc2-176">Train the model again</span></span>

<span data-ttu-id="33dc2-177">Quando si salva la spiegazione, viene eseguito nuovamente il training, questa volta usando entrambe le spiegazioni nell'esempio.</span><span class="sxs-lookup"><span data-stu-id="33dc2-177">Saving the explanation starts the training again, this time using both explanations in the example.</span></span> <span data-ttu-id="33dc2-178">Se il modello contiene informazioni sufficienti per estrarre i dati dai file di esempio etichettati, a ogni file sarà associata l'etichetta **Corrisponde**.</span><span class="sxs-lookup"><span data-stu-id="33dc2-178">If your model has enough information to extract the data from the labeled example files, you see each file labeled with **Match**.</span></span> 

<span data-ttu-id="33dc2-179">Se i file etichettati risultano nuovamente **Non corrispondenti**, probabilmente è necessario creare un'altra spiegazione per fornire ulteriori informazioni al modello per identificare il tipo di documento oppure valutare la possibilità di modificare quelle esistenti.</span><span class="sxs-lookup"><span data-stu-id="33dc2-179">If you again receive a **Mismatch** on your labeled files, you likely need to create another explanation to provide the model more information to identify the document type, or consider making changes to your existing ones.</span></span>

## <a name="test-your-model"></a><span data-ttu-id="33dc2-180">Testare il modello</span><span class="sxs-lookup"><span data-stu-id="33dc2-180">Test your model</span></span>

<span data-ttu-id="33dc2-181">Se viene rilevata una corrispondenza nei file di esempio etichettati, è possibile testare il modello sui rimanenti file di esempio non etichettati.</span><span class="sxs-lookup"><span data-stu-id="33dc2-181">If you receive a match on your labeled sample files, you can now test your model on the remaining unlabeled example files.</span></span> <span data-ttu-id="33dc2-182">Questo è un passaggio opzionale, ma utile per valutare l'adeguatezza del modello prima di usarlo, testandolo sui file che il modello non ha ancora esaminato.</span><span class="sxs-lookup"><span data-stu-id="33dc2-182">This is optional, but a useful step to evaluate the “fitness” or readiness of the model before using it, by testing it on files the model hasn’t seen before.</span></span>

1. <span data-ttu-id="33dc2-183">Nella home page del modello fare clic sulla scheda **Test**. Il modello viene eseguito sui file di esempio non etichettati.</span><span class="sxs-lookup"><span data-stu-id="33dc2-183">From the model home page, click the **Test** tab.  This runs the model on your unlabeled sample files.</span></span>
2. <span data-ttu-id="33dc2-184">Nell'elenco **Testa i file** vengono visualizzati i file di esempio e viene mostrato se il modello è in grado di estrarre le informazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="33dc2-184">In the **Test files** list, your example files display to show if the model is able to extract the information you need.</span></span> <span data-ttu-id="33dc2-185">Usare queste informazioni per determinare l'efficacia del classificatore nell'identificazione dei documenti.</span><span class="sxs-lookup"><span data-stu-id="33dc2-185">Use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![Test sui file](../media/content-understanding/test-filies-extractor.png) 

## <a name="see-also"></a><span data-ttu-id="33dc2-187">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="33dc2-187">See Also</span></span>
[<span data-ttu-id="33dc2-188">Creare un classificatore</span><span class="sxs-lookup"><span data-stu-id="33dc2-188">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="33dc2-189">Tipi di spiegazione</span><span class="sxs-lookup"><span data-stu-id="33dc2-189">Explanation types</span></span>](explanation-types-overview.md)

[<span data-ttu-id="33dc2-190">Sfruttare la tassonomia dell'archivio termini durante la creazione di un estrattore</span><span class="sxs-lookup"><span data-stu-id="33dc2-190">Leverage term store taxonomy when creating an extractor</span></span>](leverage-term-store-taxonomy.md)

[<span data-ttu-id="33dc2-191">Panoramica sull'analisi dei documenti</span><span class="sxs-lookup"><span data-stu-id="33dc2-191">Document Understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="33dc2-192">Applicare un modello</span><span class="sxs-lookup"><span data-stu-id="33dc2-192">Apply a model</span></span>](apply-a-model.md) 
