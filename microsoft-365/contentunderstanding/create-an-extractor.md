---
title: Creare un estrattore
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Informazioni su come creare un estrattore in Microsoft SharePoint Syntex.
ms.openlocfilehash: 740df6769b3a1675e4e1691f84d164312b15567c
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295457"
---
# <a name="create-an-extractor-preview"></a><span data-ttu-id="ff96a-103">Creare un estrattore (anteprima)</span><span class="sxs-lookup"><span data-stu-id="ff96a-103">Create an extractor (Preview)</span></span>

<span data-ttu-id="ff96a-104">Il contenuto di questo articolo è relativo all'anteprima privata di Project Cortex.</span><span class="sxs-lookup"><span data-stu-id="ff96a-104">The content in this article is for the Project Cortex Private Preview.</span></span> <span data-ttu-id="ff96a-105">[Per ulteriori informazioni, vedere Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="ff96a-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL2G]

</br> 

<span data-ttu-id="ff96a-106">Prima o dopo la creazione di un modello di classificazione per automatizzare l'identificazione e la classificazione di tipi di documento specifici, è possibile scegliere di aggiungere estrattori al modello per estrarre informazioni specifiche da tali documenti.</span><span class="sxs-lookup"><span data-stu-id="ff96a-106">Before or after you create a classifier model to automate identification and classification of specific document types, you can optionally choose to add extractors to your model to pull out specific information from these documents.</span></span> <span data-ttu-id="ff96a-107">Ad esempio, è possibile che il modello non solo identifichi tutti i documenti di *rinnovo del contratto* aggiunti alla raccolta documenti, ma anche per visualizzare la data di *inizio del servizio* per ogni documento come colonna nella raccolta documenti.</span><span class="sxs-lookup"><span data-stu-id="ff96a-107">For example, you may want your model not only to identify all *Contract Renewal* documents added to your document library, but also to display the *Service Start date* for each document as a column in the document library.</span></span>

<span data-ttu-id="ff96a-108">È necessario creare un estrattore per ogni entità del documento che si desidera estrarre.</span><span class="sxs-lookup"><span data-stu-id="ff96a-108">You need to create an extractor for each entity in the document that you want to extract.</span></span> <span data-ttu-id="ff96a-109">Nell'esempio, si desidera estrarre la data di *inizio del servizio* per ogni documento di *rinnovo del contratto* identificato dal modello.</span><span class="sxs-lookup"><span data-stu-id="ff96a-109">In the sample, you want to extract the *Service Start Date* for each *Contract Renewal* document that is identified by the model.</span></span> <span data-ttu-id="ff96a-110">Questa operazione deve essere eseguita quando si desidera visualizzare una visualizzazione nella raccolta documenti di tutti i documenti di *rinnovo del contratto* con una colonna che mostra il valore della data di inizio del servizio per ogni documento.</span><span class="sxs-lookup"><span data-stu-id="ff96a-110">This must happen when you want to see a view in the document library of all the *Contract Renewal* documents with a column showing the Service Start date value for each document.</span></span>

> [!NOTE]
> <span data-ttu-id="ff96a-111">Prima di creare un estrattore, è necessario [aggiungere i file di esempio](https://docs.microsoft.com/microsoft-365/contentunderstanding/create-a-classifier#add-your-example-files) per agevolare il training del modello per identificare le informazioni che si desidera estrarre.</span><span class="sxs-lookup"><span data-stu-id="ff96a-111">Before creating an extractor, you need to [add your example files](https://docs.microsoft.com/microsoft-365/contentunderstanding/create-a-classifier#add-your-example-files) to help train the model to identify the information you want to extract.</span></span> <span data-ttu-id="ff96a-112">Utilizzare gli stessi file di esempio utilizzati per creare il classificatore.</span><span class="sxs-lookup"><span data-stu-id="ff96a-112">Use the same sample files you used to create your classifier.</span></span>

## <a name="name-your-extractor"></a><span data-ttu-id="ff96a-113">Assegnare un nome all'estrattore</span><span class="sxs-lookup"><span data-stu-id="ff96a-113">Name your extractor</span></span>

1. <span data-ttu-id="ff96a-114">Nella sezione **Crea e addestra estrattori** della Home page del modello fare clic su **Train Extractor**.</span><span class="sxs-lookup"><span data-stu-id="ff96a-114">From the model home page, in the **Create and train extractors** tile, click **Train extractor**.</span></span>
2. <span data-ttu-id="ff96a-115">Nella schermata **nuovo estrattore di entità** , digitare il nome dell'estrattore nel campo **nuovo nome estrattore** .</span><span class="sxs-lookup"><span data-stu-id="ff96a-115">On the **New entity extractor** screen, type the name of your extractor in the **New extractor name** field.</span></span> <span data-ttu-id="ff96a-116">Ad esempio, denominarlo **Data di inizio del servizio** se si desidera estrarre la data di inizio del servizio da ogni documento di rinnovo del contratto.</span><span class="sxs-lookup"><span data-stu-id="ff96a-116">For example, name it **Service Start Date** if you want to extract the service start date from each Contract Renewal document.</span></span>
3. <span data-ttu-id="ff96a-117">Fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="ff96a-117">Click **Create**.</span></span>

## <a name="add-a-label"></a><span data-ttu-id="ff96a-118">Aggiungere un'etichetta</span><span class="sxs-lookup"><span data-stu-id="ff96a-118">Add a label</span></span>

<span data-ttu-id="ff96a-119">Il passaggio successivo consiste nell'assegnare un'etichetta alle informazioni che si desidera estrarre nei file di addestramento di esempio.</span><span class="sxs-lookup"><span data-stu-id="ff96a-119">The next step is to label the information you want to extract in your sample training files.</span></span>

<span data-ttu-id="ff96a-120">La creazione dell'estrattore apre la pagina estrattore.</span><span class="sxs-lookup"><span data-stu-id="ff96a-120">Creating the extractor opens the extractor page.</span></span> <span data-ttu-id="ff96a-121">Di seguito viene mostrato un elenco dei file di esempio, con il primo file nell'elenco visualizzato nel visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="ff96a-121">Here you see a list of your sample files, with the first file on the list displayed in the viewer.</span></span>

1. <span data-ttu-id="ff96a-122">Dal Visualizzatore selezionare i dati che si desidera estrarre dai file.</span><span class="sxs-lookup"><span data-stu-id="ff96a-122">From the viewer, select the data that you want to extract from the files.</span></span> <span data-ttu-id="ff96a-123">Ad esempio, se si desidera estrarre la *Data di inizio del servizio*, è necessario evidenziare il valore data nel primo file (*lunedì 14 ottobre 2019*).</span><span class="sxs-lookup"><span data-stu-id="ff96a-123">For example, if you want to extract the *Start Service Date*, you highlight the date value in the first file (*Monday, October 14, 2019*).</span></span> <span data-ttu-id="ff96a-124">e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ff96a-124">and then click **Save**.</span></span>  <span data-ttu-id="ff96a-125">Nella colonna **Label** dovrebbe essere visualizzato il valore visualizzato nel file nell'elenco degli esempi etichettati.</span><span class="sxs-lookup"><span data-stu-id="ff96a-125">You should see the value display from the file in the Labeled examples list, under the **Label** column.</span></span>
2. <span data-ttu-id="ff96a-126">Selezionare il **file successivo** per il salvataggio automatico e aprire il file successivo nell'elenco nel visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="ff96a-126">Select **Next file** to auto save and open the next file in the list in the viewer.</span></span> <span data-ttu-id="ff96a-127">Oppure seleziona **Salva** e quindi seleziona un altro file dall'elenco degli **esempi etichettati** .</span><span class="sxs-lookup"><span data-stu-id="ff96a-127">Or select **Save** and then select another file from the **Labeled examples** list.</span></span>
3. <span data-ttu-id="ff96a-128">Nel Visualizzatore, ripetere i passaggi 1 e 2, quindi ripetere fino a quando non è stata salvata l'etichetta in tutti e cinque i file.</span><span class="sxs-lookup"><span data-stu-id="ff96a-128">In the viewer, repeat steps 1 and 2, then repeat until you saved the label in all five files.</span></span>

    ![Impostazioni avanzate](../media/content-understanding/select-service-start-date.png) 

### <a name="add-a-negative-example"></a><span data-ttu-id="ff96a-130">Aggiungere un esempio negativo</span><span class="sxs-lookup"><span data-stu-id="ff96a-130">Add a negative example</span></span>

<span data-ttu-id="ff96a-131">Analogamente alla modalità di aggiunta di un file di esempio negativo durante la creazione di un classificatore, è necessario aggiungere un campione negativo per l'estrattore.</span><span class="sxs-lookup"><span data-stu-id="ff96a-131">Similar to how you add a negative sample file when creating a classifier, you need to add a negative sample for the extractor.</span></span> <span data-ttu-id="ff96a-132">Dovrebbe essere un file che non contiene un valore di data di inizio del servizio.</span><span class="sxs-lookup"><span data-stu-id="ff96a-132">It should be a file that does not contain a "Service Start" date value.</span></span>

1. <span data-ttu-id="ff96a-133">Nell'elenco **esempi etichettati** selezionare un esempio negativo.</span><span class="sxs-lookup"><span data-stu-id="ff96a-133">From the **Labeled examples** list, select a negative example.</span></span>
2. <span data-ttu-id="ff96a-134">Nel Visualizzatore all'inizio dell'articolo selezionare **Nessuna etichetta presente**.</span><span class="sxs-lookup"><span data-stu-id="ff96a-134">In the viewer on the top of the article, select **No label present**.</span></span>
3. <span data-ttu-id="ff96a-135">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ff96a-135">Click **Save**.</span></span>
 
<span data-ttu-id="ff96a-136">Dopo aver identificato cinque file, viene visualizzato un banner di notifica che informa di passare all'allenamento.</span><span class="sxs-lookup"><span data-stu-id="ff96a-136">Once you labeled five files, a notification banner displays informing you to move to training.</span></span> <span data-ttu-id="ff96a-137">È possibile scegliere di visualizzare più documenti o passare all'allenamento.</span><span class="sxs-lookup"><span data-stu-id="ff96a-137">You can choose to more documents or advance to training.</span></span> 

## <a name="add-an-explanation"></a><span data-ttu-id="ff96a-138">Aggiungere una spiegazione</span><span class="sxs-lookup"><span data-stu-id="ff96a-138">Add an explanation</span></span>

<span data-ttu-id="ff96a-139">In questo esempio viene creata una spiegazione che fornisce un suggerimento relativo al formato di entità stesso e alle varianti che può avere nei documenti di esempio.</span><span class="sxs-lookup"><span data-stu-id="ff96a-139">For the example, you create an explanation that provides a hint about the entity format itself and variations it may have in the sample documents.</span></span> <span data-ttu-id="ff96a-140">Ad esempio, un valore date può essere in un certo numero di formati diversi, come:</span><span class="sxs-lookup"><span data-stu-id="ff96a-140">For example, a date value can be in a number of different formats, such as:</span></span>
- <span data-ttu-id="ff96a-141">10/14/2019</span><span class="sxs-lookup"><span data-stu-id="ff96a-141">10/14/2019</span></span>
- <span data-ttu-id="ff96a-142">14 ottobre 2019</span><span class="sxs-lookup"><span data-stu-id="ff96a-142">October 14, 2019</span></span>
- <span data-ttu-id="ff96a-143">Lunedì 14 ottobre 2019</span><span class="sxs-lookup"><span data-stu-id="ff96a-143">Monday, October 14, 2019</span></span>
 

<span data-ttu-id="ff96a-144">Per identificare la *Data di inizio del servizio* , è possibile creare una spiegazione del modello.</span><span class="sxs-lookup"><span data-stu-id="ff96a-144">To help identify the *Service Start Date* you create a pattern explanation.</span></span>

1. <span data-ttu-id="ff96a-145">Nella sezione spiegazione selezionare **nuovo** e digitare un nome, ad esempio *Data*.</span><span class="sxs-lookup"><span data-stu-id="ff96a-145">In the Explanation section, select **New** and type a name (for example, *Date*).</span></span>
2. <span data-ttu-id="ff96a-146">Per tipo, selezionare **elenco modelli**.</span><span class="sxs-lookup"><span data-stu-id="ff96a-146">For Type, select **Pattern list**.</span></span>
3. <span data-ttu-id="ff96a-147">Per valore, specificare la variazione di data come viene visualizzata nei file di esempio.</span><span class="sxs-lookup"><span data-stu-id="ff96a-147">For Value, provide the date variation as they appear in the sample files.</span></span> <span data-ttu-id="ff96a-148">Ad esempio, se si dispone di formati di data visualizzati come 0/00/0000, si immettono tutte le varianti presenti nei documenti, quali:</span><span class="sxs-lookup"><span data-stu-id="ff96a-148">For example, if you have date formats that appear as 0/00/0000, you enter any variations that appear in your documents, such as:</span></span>
    - <span data-ttu-id="ff96a-149">0/0/0000</span><span class="sxs-lookup"><span data-stu-id="ff96a-149">0/0/0000</span></span>
    - <span data-ttu-id="ff96a-150">0/00/0000</span><span class="sxs-lookup"><span data-stu-id="ff96a-150">0/00/0000</span></span>
    - <span data-ttu-id="ff96a-151">00/0/0000</span><span class="sxs-lookup"><span data-stu-id="ff96a-151">00/0/0000</span></span>
    - <span data-ttu-id="ff96a-152">00/00/0000</span><span class="sxs-lookup"><span data-stu-id="ff96a-152">00/00/0000</span></span>
4. <span data-ttu-id="ff96a-153">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ff96a-153">Select **Save**.</span></span>

### <a name="use-the-explanation-library"></a><span data-ttu-id="ff96a-154">Utilizzare la raccolta di spiegazioni</span><span class="sxs-lookup"><span data-stu-id="ff96a-154">Use the Explanation library</span></span>

<span data-ttu-id="ff96a-155">Per la creazione di spiegazioni per gli elementi, ad esempio le date, è più facile usare la libreria delle spiegazioni piuttosto che immettere manualmente tutte le varianti.</span><span class="sxs-lookup"><span data-stu-id="ff96a-155">For creating explanations for items such as dates, it is easier to use the explanation library than to manually enter all variations.</span></span> <span data-ttu-id="ff96a-156">La raccolta di spiegazioni è un insieme di spiegazioni di modelli e frasi predefinite.</span><span class="sxs-lookup"><span data-stu-id="ff96a-156">The explanation library is a set of pre-built phrase and pattern explanations.</span></span> <span data-ttu-id="ff96a-157">La raccolta fornisce tutti i formati per gli elenchi di frasi o schemi comuni, ad esempio le date, i numeri di telefono, il CAP e così via.</span><span class="sxs-lookup"><span data-stu-id="ff96a-157">The library provides all formats for common phrase or pattern lists, such as dates, phone numbers, zip code, etc.</span></span> 

<span data-ttu-id="ff96a-158">Per l'esempio di *Data di inizio del servizio* , è più efficiente utilizzare la spiegazione predefinita per la *Data* nella raccolta di spiegazioni:</span><span class="sxs-lookup"><span data-stu-id="ff96a-158">For the *Service Start Date* sample, it is more efficient to use the pre-built explanation for *Date* in the explanation library:</span></span>

1. <span data-ttu-id="ff96a-159">Nella **sezione spiegazione**selezionare **nuovo**e quindi fare clic su **dalla raccolta delle spiegazioni**.</span><span class="sxs-lookup"><span data-stu-id="ff96a-159">In the **Explanation section**, select **New**, and then select **From explanation library**.</span></span>
2. <span data-ttu-id="ff96a-160">Nella raccolta delle spiegazioni selezionare **Data**.</span><span class="sxs-lookup"><span data-stu-id="ff96a-160">From the explanation library, select **Date**.</span></span> <span data-ttu-id="ff96a-161">È possibile visualizzare tutte le varianti di data riconosciute.</span><span class="sxs-lookup"><span data-stu-id="ff96a-161">You can view all variations of date that are recognized.</span></span>
3. <span data-ttu-id="ff96a-162">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="ff96a-162">Select **Add**.</span></span></br>

    ![Raccolta di spiegazioni](../media/content-understanding/explanation-library.png) 

4. <span data-ttu-id="ff96a-164">Nella pagina **Crea una spiegazione** le informazioni relative alla *Data* della raccolta delle spiegazioni vengono riempite automaticamente dai campi.</span><span class="sxs-lookup"><span data-stu-id="ff96a-164">On the **Create an explanation** page, the *Date* information from the explanation library auto fills the fields.</span></span> <span data-ttu-id="ff96a-165">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ff96a-165">Select **Save**.</span></span></br>

    ![Data](../media/content-understanding/date-explanation-library.png) 

## <a name="train-the-model"></a><span data-ttu-id="ff96a-167">Addestramento del modello</span><span class="sxs-lookup"><span data-stu-id="ff96a-167">Train the model</span></span> 

<span data-ttu-id="ff96a-168">Salvataggio delle spiegazioni avviare la formazione.</span><span class="sxs-lookup"><span data-stu-id="ff96a-168">Saving your explanation start the training.</span></span> <span data-ttu-id="ff96a-169">Se il modello contiene informazioni sufficienti per estrarre i dati dai file di esempio etichettati, verranno visualizzati tutti i file contrassegnati con la **corrispondenza**.</span><span class="sxs-lookup"><span data-stu-id="ff96a-169">If your model has enough information to extract the data from your labeled example files, you will see each file labeled with **Match**.</span></span>  

![Match](../media/content-understanding/match2.png) 

<span data-ttu-id="ff96a-171">Se la spiegazione non contiene informazioni sufficienti per individuare i dati che si desidera estrarre, ogni file verrà etichettato con la **mancata corrispondenza**.</span><span class="sxs-lookup"><span data-stu-id="ff96a-171">If the explanation does not have enough information to find the data you want to extract, each file will be labeled with **Mismatch**.</span></span> <span data-ttu-id="ff96a-172">È possibile fare clic sui file non **corrispondenti** per visualizzare altre informazioni sul motivo della mancata corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="ff96a-172">You can click on the **Mismatched** files to see more information about why there was a mismatch.</span></span>


## <a name="add-another-explanation"></a><span data-ttu-id="ff96a-173">Aggiungere un'altra spiegazione</span><span class="sxs-lookup"><span data-stu-id="ff96a-173">Add another explanation</span></span>

<span data-ttu-id="ff96a-174">Spesso la mancata corrispondenza indica che la spiegazione fornita non ha fornito informazioni sufficienti per estrarre il valore della data di inizio del servizio in modo che corrisponda ai file etichettati.</span><span class="sxs-lookup"><span data-stu-id="ff96a-174">Often the mismatch is an indication that the explanation we provided did not provide enough information to extract the service start date value to match our labeled files.</span></span> <span data-ttu-id="ff96a-175">Potrebbe essere necessario modificarlo oppure aggiungere un'altra spiegazione.</span><span class="sxs-lookup"><span data-stu-id="ff96a-175">You may need to edit it, or add another explanation.</span></span>

<span data-ttu-id="ff96a-176">Per l'esempio, si noti che la *Data di inizio del servizio della stringa di* testo precede sempre il valore effettivo.</span><span class="sxs-lookup"><span data-stu-id="ff96a-176">For the sample, notice that the text string *Start Service date of* always precedes the actual value.</span></span> <span data-ttu-id="ff96a-177">Per identificare la data di inizio del servizio, è necessario creare una spiegazione per la frase.</span><span class="sxs-lookup"><span data-stu-id="ff96a-177">To help identify the Service Start Date, you need ot create a phrase explanation.</span></span>

1. <span data-ttu-id="ff96a-178">Nella sezione spiegazione selezionare **nuovo**e quindi digitare un nome, ad esempio *stringa di prefisso*.</span><span class="sxs-lookup"><span data-stu-id="ff96a-178">In the Explanation section, select **New**, and then type a name (for example, *Prefix String*).</span></span>
2. <span data-ttu-id="ff96a-179">Per il tipo selezionare l' **elenco delle frasi**.</span><span class="sxs-lookup"><span data-stu-id="ff96a-179">For the Type, select **Phrase list**.</span></span>
3. <span data-ttu-id="ff96a-180">Utilizzare la *Data di inizio del servizio* come valore.</span><span class="sxs-lookup"><span data-stu-id="ff96a-180">Use *Service Start Date of* as the value.</span></span>
4. <span data-ttu-id="ff96a-181">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ff96a-181">Select **Save**.</span></span>

    ![Stringa di prefisso](../media/content-understanding/prefix-string.png) 

## <a name="train-the-model-again"></a><span data-ttu-id="ff96a-183">Eseguire di nuovo il training del modello</span><span class="sxs-lookup"><span data-stu-id="ff96a-183">Train the model again</span></span>

<span data-ttu-id="ff96a-184">Salvando la spiegazione viene riavviata la formazione, questa volta utilizzando entrambe le spiegazioni del campione.</span><span class="sxs-lookup"><span data-stu-id="ff96a-184">Saving the explanation starts the training again, this time using both explanations in the sample.</span></span> <span data-ttu-id="ff96a-185">Se il modello contiene informazioni sufficienti per estrarre i dati dai file di esempio etichettati, è possibile visualizzare ogni file con l'etichetta **corrispondente**.</span><span class="sxs-lookup"><span data-stu-id="ff96a-185">If your model has enough information to extract the data from the labeled sample files, you see each file labeled with **Match**.</span></span> 

<span data-ttu-id="ff96a-186">Se si riceve di nuovo una **mancata corrispondenza** nei file etichettati, è probabile che sia necessario creare un'altra spiegazione per fornire al modello ulteriori informazioni per identificare il tipo di documento oppure prendere in considerazione le modifiche apportate al modello di esempio.</span><span class="sxs-lookup"><span data-stu-id="ff96a-186">If you again receive a **Mismatch** on your labeled files, you likely need to create another explanation to provide the model more information to identify the document type, or consider making changes to your sample model.</span></span>

## <a name="test-your-model"></a><span data-ttu-id="ff96a-187">Testare il modello</span><span class="sxs-lookup"><span data-stu-id="ff96a-187">Test your model</span></span>

<span data-ttu-id="ff96a-188">Se si riceve una corrispondenza nei file di esempio etichettati, è ora possibile testare il modello nei file di esempio senza etichetta rimanenti.</span><span class="sxs-lookup"><span data-stu-id="ff96a-188">If you receive a match on your labeled sample files, you can now test your model on the remaining unlabeled sample files.</span></span>

1. <span data-ttu-id="ff96a-189">Nella Home page del modello fare clic sulla scheda **test** .  Questo esegue il modello nei file di esempio senza etichetta.</span><span class="sxs-lookup"><span data-stu-id="ff96a-189">From the model home page, click the **Test** tab.  This runs the model on your unlabeled sample files.</span></span>
2. <span data-ttu-id="ff96a-190">Nell'elenco **file di test** , i file di esempio vengono visualizzati per mostrare se il modello è in grado di estrarre le informazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="ff96a-190">In the **Test files** list, your example files display to show if the model is able to extract the information you need.</span></span> <span data-ttu-id="ff96a-191">Utilizzare queste informazioni per determinare l'efficacia del classificatore per identificare i documenti.</span><span class="sxs-lookup"><span data-stu-id="ff96a-191">Use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![Test sui file](../media/content-understanding/test-filies-extractor.png) 
