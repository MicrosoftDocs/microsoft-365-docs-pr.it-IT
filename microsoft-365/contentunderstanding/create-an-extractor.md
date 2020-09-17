---
title: Creare un estrattore (anteprima)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Informazioni su come creare un estrattore
ms.openlocfilehash: 7219726fb385d0b67f7ee0614f5075ba226140ab
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950085"
---
# <a name="create-an-extractor-preview"></a><span data-ttu-id="0c2d1-103">Creare un estrattore (anteprima)</span><span class="sxs-lookup"><span data-stu-id="0c2d1-103">Create an extractor (Preview)</span></span>
> [!Note] 
> <span data-ttu-id="0c2d1-104">Il contenuto di questo articolo è relativo all'anteprima privata di Project Cortex.</span><span class="sxs-lookup"><span data-stu-id="0c2d1-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="0c2d1-105">[Per ulteriori informazioni, vedere Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="0c2d1-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL2G]

</br> 

<span data-ttu-id="0c2d1-106">Prima o dopo aver creato un modello di classificazione per automatizzare l'identificazione e la classifica dei tipi di documento specifici, è possibile scegliere di aggiungere estrattori al modello per estrarre informazioni specifiche da tali documenti.</span><span class="sxs-lookup"><span data-stu-id="0c2d1-106">Either before or after you create a classifier model to automate identification and classification of specific document types, you can optionally choose to add extractors to your model to pull out specific information from these documents.</span></span> <span data-ttu-id="0c2d1-107">Ad esempio, è possibile che il modello non solo identifichi tutti i documenti di *rinnovo del contratto* aggiunti alla raccolta documenti, ma visualizzi anche la data di *inizio del servizio* per ogni documento come colonna nella raccolta documenti.</span><span class="sxs-lookup"><span data-stu-id="0c2d1-107">For example, you may want your model not only to identify all *Contract Renewal* documents that are added to your document library, but to also display the *Service Start date* for each document as a column in the document library.</span></span>

<span data-ttu-id="0c2d1-108">È necessario creare un estrattore per ogni entità del documento che si desidera estrarre.</span><span class="sxs-lookup"><span data-stu-id="0c2d1-108">You need to create an extractor for each entity in the document that you want to extract.</span></span> <span data-ttu-id="0c2d1-109">In questo esempio, si desidera estrarre la *Data di inizio del servizio* per ogni documento di rinnovo del *contratto* identificato dal modello.</span><span class="sxs-lookup"><span data-stu-id="0c2d1-109">In our example, we want to extract the *Service Start Date* for each *Contract Renewal* document that is identified by the model.</span></span> <span data-ttu-id="0c2d1-110">Si desidera essere in grado di visualizzare una visualizzazione nella raccolta documenti di tutti i documenti di *rinnovo del contratto* , con una colonna che Visualizza il valore di data di inizio del servizio di ogni documento.</span><span class="sxs-lookup"><span data-stu-id="0c2d1-110">We want to be able to see a view in the document library of all *Contract Renewal* documents, with a column that shows the Service Start date value of each document.</span></span>

> [!Note]
> <span data-ttu-id="0c2d1-111">Prima di creare un estrattore, è necessario [aggiungere i file di esempio](https://docs.microsoft.com/microsoft-365/contentunderstanding/create-a-classifier?view=o365-worldwide#add-your-example-files) necessari per addestrare il modello per identificare le informazioni che si desidera estrarre.</span><span class="sxs-lookup"><span data-stu-id="0c2d1-111">Before creating an extractor, you need to [add your example files](https://docs.microsoft.com/microsoft-365/contentunderstanding/create-a-classifier?view=o365-worldwide#add-your-example-files) you will need to help train the model to identify the information you want to extract.</span></span> <span data-ttu-id="0c2d1-112">Utilizzare gli stessi file di esempio utilizzati per creare il classificatore.</span><span class="sxs-lookup"><span data-stu-id="0c2d1-112">Use the same example files you used to create your classifier.</span></span>


## <a name="name-your-extractor"></a><span data-ttu-id="0c2d1-113">Assegnare un nome all'estrattore</span><span class="sxs-lookup"><span data-stu-id="0c2d1-113">Name your extractor</span></span>

1. <span data-ttu-id="0c2d1-114">Nella sezione **Crea e addestra estrattori** della Home page del modello fare clic su **Train Extractor**.</span><span class="sxs-lookup"><span data-stu-id="0c2d1-114">On the model home page, in the **Create and train extractors** tile, click **Train extractor**.</span></span>
2. <span data-ttu-id="0c2d1-115">Nella schermata **nuovo estrattore di entità** , digitare il nome dell'estrattore nel campo **nuovo nome estrattore** .</span><span class="sxs-lookup"><span data-stu-id="0c2d1-115">On the **New entity extractor** screen, type the name of your extractor in the **New extractor name** field.</span></span> <span data-ttu-id="0c2d1-116">Ad esempio, è possibile denominarlo **Data di inizio del servizio** se si desidera estrarre la data di inizio del servizio da ogni documento di rinnovo del contratto.</span><span class="sxs-lookup"><span data-stu-id="0c2d1-116">For example, we can name it **Service Start Date** if we want to extract the service start date from each Contract Renewal document.</span></span>
3. <span data-ttu-id="0c2d1-117">Fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="0c2d1-117">Click **Create**.</span></span>

## <a name="add-a-label"></a><span data-ttu-id="0c2d1-118">Aggiungere un'etichetta</span><span class="sxs-lookup"><span data-stu-id="0c2d1-118">Add a label</span></span>

<span data-ttu-id="0c2d1-119">Il passaggio successivo consiste nell'assegnare un'etichetta alle informazioni che si desidera estrarre nei file di training di esempio.</span><span class="sxs-lookup"><span data-stu-id="0c2d1-119">The next step is to label the information you want to extract in your example training files.</span></span>

<span data-ttu-id="0c2d1-120">Se si crea l'estrattore, verrà aperta la pagina estrattore in cui verrà visualizzato un elenco dei file di esempio, con il primo file nell'elenco mostrato nel visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="0c2d1-120">Creating the extractor will open the extractor page in which you will see a list of your example files, with the first file on the list displayed in the viewer.</span></span>

1. <span data-ttu-id="0c2d1-121">Nel Visualizzatore selezionare i dati che si desidera estrarre dai file.</span><span class="sxs-lookup"><span data-stu-id="0c2d1-121">In the viewer, select the data that you want to extract from the files.</span></span> <span data-ttu-id="0c2d1-122">Ad esempio, se si desidera estrarre la *Data di inizio del servizio*, si evidenzierà il valore della data per il primo file (*lunedì 14 ottobre 2019*).</span><span class="sxs-lookup"><span data-stu-id="0c2d1-122">For example, if you want to extract the *Start Service Date*, you will highlight the date value for it in the first file (*Monday, October 14, 2019*).</span></span> <span data-ttu-id="0c2d1-123">Fare quindi clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="0c2d1-123">Then click **Save**.</span></span>  <span data-ttu-id="0c2d1-124">Verrà visualizzata la visualizzazione del valore per il file nell'elenco degli esempi etichettati sotto la colonna **etichetta** .</span><span class="sxs-lookup"><span data-stu-id="0c2d1-124">You will see the value display for the file in the Labeled examples list under the **Label** column.</span></span>
2. <span data-ttu-id="0c2d1-125">Selezionare il **file successivo** per il salvataggio automatico e aprire il file successivo nell'elenco nel Visualizzatore oppure è possibile selezionare **Salva** e selezionare un altro file nell'elenco **esempi etichettati** .</span><span class="sxs-lookup"><span data-stu-id="0c2d1-125">Select **Next file** to autosave and open the next file in the list in the viewer, or you can select **Save** and select another file from the **Labeled examples** list.</span></span>
3. <span data-ttu-id="0c2d1-126">Nel Visualizzatore, ripetere i passaggi 1 e 2 e procedere fino a quando non è stata salvata l'etichetta in cinque file.</span><span class="sxs-lookup"><span data-stu-id="0c2d1-126">In the viewer, repeat steps 1 and 2, and do this until you have saved the label in five files.</span></span>

    ![Impostazioni avanzate](../media/content-understanding/select-service-start-date.png) 


### <a name="add-a-negative-example"></a><span data-ttu-id="0c2d1-128">Aggiungere un esempio negativo</span><span class="sxs-lookup"><span data-stu-id="0c2d1-128">Add a negative example</span></span>

<span data-ttu-id="0c2d1-129">Analogamente alla modalità di aggiunta di un file di esempio negativo durante la creazione di un classificatore, è necessario aggiungere un esempio negativo per l'estrattore.</span><span class="sxs-lookup"><span data-stu-id="0c2d1-129">Similar to how you would add a negative example file when creating a classifier, you need to add a negative example for the extractor.</span></span> <span data-ttu-id="0c2d1-130">Ad esempio, dovrebbe trattarsi di un file che non contiene un valore di data di inizio del servizio.</span><span class="sxs-lookup"><span data-stu-id="0c2d1-130">For our example, it should be a file that does not contain a Service Start Date value.</span></span>

1. <span data-ttu-id="0c2d1-131">Nell'elenco **esempi etichettati** selezionare un esempio negativo.</span><span class="sxs-lookup"><span data-stu-id="0c2d1-131">From the **Labeled examples** list, select a negative example.</span></span>
2. <span data-ttu-id="0c2d1-132">Nel Visualizzatore, nella parte superiore dell'articolo, selezionare **no label present**.</span><span class="sxs-lookup"><span data-stu-id="0c2d1-132">In the viewer, on the top of the article, select **No label present**.</span></span>
3. <span data-ttu-id="0c2d1-133">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="0c2d1-133">Click **Save**.</span></span>
 
<span data-ttu-id="0c2d1-134">Dopo aver identificato cinque file, verrà visualizzato un banner di notifica che informa di passare all'allenamento.</span><span class="sxs-lookup"><span data-stu-id="0c2d1-134">Once you have labeled five files, a notification banner will display informing you to move to training.</span></span> <span data-ttu-id="0c2d1-135">È possibile scegliere di visualizzare più documenti o passare all'allenamento.</span><span class="sxs-lookup"><span data-stu-id="0c2d1-135">You can choose to more documents or advance to training.</span></span> 

## <a name="add-an-explanation"></a><span data-ttu-id="0c2d1-136">Aggiungere una spiegazione</span><span class="sxs-lookup"><span data-stu-id="0c2d1-136">Add an explanation</span></span>

<span data-ttu-id="0c2d1-137">Ad esempio, viene creata una spiegazione che fornisce un suggerimento relativo al formato di entità e alle varianti che può avere nei documenti di esempio.</span><span class="sxs-lookup"><span data-stu-id="0c2d1-137">For our example, we are going to create an explanation that provides a hint about the entity format itself and variations it may have in the example documents.</span></span> <span data-ttu-id="0c2d1-138">Ad esempio, un valore date può essere in un certo numero di formati diversi, come:</span><span class="sxs-lookup"><span data-stu-id="0c2d1-138">For example,a date value can be in a number of different formats, such as:</span></span>
- <span data-ttu-id="0c2d1-139">10/14/2019</span><span class="sxs-lookup"><span data-stu-id="0c2d1-139">10/14/2019</span></span>
- <span data-ttu-id="0c2d1-140">14 ottobre 2019</span><span class="sxs-lookup"><span data-stu-id="0c2d1-140">October 14, 2019</span></span>
- <span data-ttu-id="0c2d1-141">Lunedì 14 ottobre 2019</span><span class="sxs-lookup"><span data-stu-id="0c2d1-141">Monday, October 14, 2019</span></span>
 

<span data-ttu-id="0c2d1-142">Per identificare la *Data di inizio del servizio* , è possibile creare una descrizione del modello.</span><span class="sxs-lookup"><span data-stu-id="0c2d1-142">To help identify the *Service Start Date* you can create a pattern explanation.</span></span>

1. <span data-ttu-id="0c2d1-143">Nella sezione spiegazione selezionare **nuovo**e quindi digitare un nome, ad esempio *Data*.</span><span class="sxs-lookup"><span data-stu-id="0c2d1-143">In the Explanation section, select **New**, and then type a name (for example, *Date*).</span></span>
2. <span data-ttu-id="0c2d1-144">Per il tipo, selezionare **elenco modelli**.</span><span class="sxs-lookup"><span data-stu-id="0c2d1-144">For the Type, select **Pattern list**.</span></span>
3. <span data-ttu-id="0c2d1-145">Per il valore, è necessario fornire la variazione di data come vengono visualizzati nei file di esempio.</span><span class="sxs-lookup"><span data-stu-id="0c2d1-145">For the value, you need to provide the date variation as they appear in the sample files.</span></span> <span data-ttu-id="0c2d1-146">Ad esempio, se si dispone di formati di data visualizzati come 0/00/0000, è necessario immettere qualsiasi variante che potrebbe essere visualizzata nei documenti, come:</span><span class="sxs-lookup"><span data-stu-id="0c2d1-146">For example, if you have date formats that appear as 0/00/0000, you would enter any variations that might appear in your documents, such as:</span></span>
    - <span data-ttu-id="0c2d1-147">0/0/0000</span><span class="sxs-lookup"><span data-stu-id="0c2d1-147">0/0/0000</span></span>
    - <span data-ttu-id="0c2d1-148">0/00/0000</span><span class="sxs-lookup"><span data-stu-id="0c2d1-148">0/00/0000</span></span>
    - <span data-ttu-id="0c2d1-149">00/0/0000</span><span class="sxs-lookup"><span data-stu-id="0c2d1-149">00/0/0000</span></span>
    - <span data-ttu-id="0c2d1-150">00/00/0000</span><span class="sxs-lookup"><span data-stu-id="0c2d1-150">00/00/0000</span></span>
4. <span data-ttu-id="0c2d1-151">Seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="0c2d1-151">Select **Save**.</span></span>


### <a name="use-the-explanation-library"></a><span data-ttu-id="0c2d1-152">Utilizzare la raccolta di spiegazioni</span><span class="sxs-lookup"><span data-stu-id="0c2d1-152">Use the Explanation library</span></span>

<span data-ttu-id="0c2d1-153">Per la creazione di spiegazioni per elementi quali date, è molto più facile usare la libreria delle spiegazioni piuttosto che immettere manualmente tutte le varianti.</span><span class="sxs-lookup"><span data-stu-id="0c2d1-153">For creating explanations for things such as dates, it is much easier to use the explanation library than to manually enter all variations.</span></span> <span data-ttu-id="0c2d1-154">La raccolta di spiegazioni è un insieme di spiegazioni di modelli e frasi predefinite.</span><span class="sxs-lookup"><span data-stu-id="0c2d1-154">The explanation library is a set of pre-built phrase and pattern explanations.</span></span> <span data-ttu-id="0c2d1-155">La raccolta cerca di fornire tutti i formati per gli elenchi di frasi o schemi comuni, ad esempio date, numeri di telefono, CAP e molti altri.</span><span class="sxs-lookup"><span data-stu-id="0c2d1-155">The library tries to provide all formats for common phrase or pattern lists, such as dates, phone numbers, zip code, and many others.</span></span> 

<span data-ttu-id="0c2d1-156">Per l'esempio di *Data di inizio del servizio* , è più efficiente utilizzare la spiegazione predefinita per la *Data* nella raccolta di spiegazioni:</span><span class="sxs-lookup"><span data-stu-id="0c2d1-156">For our *Service Start Date* example, it is more efficient to use the pre-built explanation for *Date* in the explanation library:</span></span>

1. <span data-ttu-id="0c2d1-157">Nella **sezione spiegazione**, \* \* selezionare **nuovo**e quindi selezionare **dalla raccolta di spiegazioni**.</span><span class="sxs-lookup"><span data-stu-id="0c2d1-157">In the **Explanation section**,\*\* select **New**, and then select **From explanation library**.</span></span>
2. <span data-ttu-id="0c2d1-158">Nella raccolta delle spiegazioni selezionare **Data**.</span><span class="sxs-lookup"><span data-stu-id="0c2d1-158">From the explanation library, select **Date**.</span></span> <span data-ttu-id="0c2d1-159">È possibile visualizzare tutte le varianti di data che verranno riconosciute.</span><span class="sxs-lookup"><span data-stu-id="0c2d1-159">You can view all variations of date that will be recognized.</span></span>
3. <span data-ttu-id="0c2d1-160">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="0c2d1-160">Select **Add**.</span></span></br>

    ![Raccolta di spiegazioni](../media/content-understanding/explanation-library.png) 

4. <span data-ttu-id="0c2d1-162">Nella pagina **Crea una spiegazione** le informazioni relative alla *Data* della raccolta delle spiegazioni verranno riempite automaticamente nei campi.</span><span class="sxs-lookup"><span data-stu-id="0c2d1-162">On the **Create an explanation** page, the *Date* information from the explanation library will autofill the fields.</span></span> <span data-ttu-id="0c2d1-163">Seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="0c2d1-163">Select **Save**.</span></span></br>

    ![Raccolta di spiegazioni](../media/content-understanding/date-explanation-library.png) 

 
## <a name="train-the-model"></a><span data-ttu-id="0c2d1-165">Addestramento del modello</span><span class="sxs-lookup"><span data-stu-id="0c2d1-165">Train the model</span></span> 

<span data-ttu-id="0c2d1-166">Il salvataggio delle spiegazioni inizierà la formazione.</span><span class="sxs-lookup"><span data-stu-id="0c2d1-166">Saving your explanation will start the training.</span></span> <span data-ttu-id="0c2d1-167">Se il modello contiene informazioni sufficienti per estrarre i dati dai file di esempio etichettati, verranno visualizzati tutti i file contrassegnati con la **corrispondenza**.</span><span class="sxs-lookup"><span data-stu-id="0c2d1-167">If your model has enough information to extract the data from your labeled example files, you will see each file labeled with **Match**.</span></span>  

![Raccolta di spiegazioni](../media/content-understanding/match2.png) 

<span data-ttu-id="0c2d1-169">Se la spiegazione non contiene informazioni sufficienti per individuare i dati che si desidera estrarre, ogni file verrà etichettato con la **mancata corrispondenza**.</span><span class="sxs-lookup"><span data-stu-id="0c2d1-169">If the explanation does not have enough information to find the data you want to extract, each file will be labeled with **Mismatch**.</span></span> <span data-ttu-id="0c2d1-170">È possibile fare clic sui file non corrispondenti per visualizzare altre informazioni sul motivo della mancata corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="0c2d1-170">You can click on the Mismatched files to see more information about why there was a mismatch.</span></span>


## <a name="add-another-explanation"></a><span data-ttu-id="0c2d1-171">Aggiungere un'altra spiegazione</span><span class="sxs-lookup"><span data-stu-id="0c2d1-171">Add another explanation</span></span>

<span data-ttu-id="0c2d1-172">Spesso la mancata corrispondenza indica che la spiegazione fornita non ha fornito informazioni sufficienti per estrarre il valore della data di inizio del servizio in modo che corrisponda ai file etichettati.</span><span class="sxs-lookup"><span data-stu-id="0c2d1-172">Often the mismatch is an indication that the explanation we provided did not provide enough information to extract the service start date value to match our labeled files.</span></span> <span data-ttu-id="0c2d1-173">Potrebbe essere necessario modificarlo oppure aggiungere un'altra spiegazione.</span><span class="sxs-lookup"><span data-stu-id="0c2d1-173">You may need to edit it, or add another explanation.</span></span>

<span data-ttu-id="0c2d1-174">Ad esempio, si noti che la stringa di testo *inizia la data di servizio di* sempre precede il valore effettivo.</span><span class="sxs-lookup"><span data-stu-id="0c2d1-174">For our example, we notice that the text string *Start Service date of* always precedes the actual value.</span></span> <span data-ttu-id="0c2d1-175">Per identificare la data di inizio del servizio, è possibile creare una spiegazione delle frasi.</span><span class="sxs-lookup"><span data-stu-id="0c2d1-175">To help identify the Service Start Date we can create a phrase explanation.</span></span>

1. <span data-ttu-id="0c2d1-176">Nella sezione spiegazione selezionare **nuovo**e quindi digitare un nome, ad esempio *stringa di prefisso*.</span><span class="sxs-lookup"><span data-stu-id="0c2d1-176">In the Explanation section, select **New**, and then type a name (for example, *Prefix String*).</span></span>
2. <span data-ttu-id="0c2d1-177">Per il tipo selezionare l' **elenco delle frasi**.</span><span class="sxs-lookup"><span data-stu-id="0c2d1-177">For the Type, select **Phrase list**.</span></span>
3. <span data-ttu-id="0c2d1-178">Utilizzare la *Data di inizio del servizio* come valore.</span><span class="sxs-lookup"><span data-stu-id="0c2d1-178">Use *Service Start Date of* as the value.</span></span>
4. <span data-ttu-id="0c2d1-179">Seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="0c2d1-179">Select **Save**.</span></span>

    ![Raccolta di spiegazioni](../media/content-understanding/prefix-string.png) 


## <a name="train-the-model"></a><span data-ttu-id="0c2d1-181">Addestramento del modello</span><span class="sxs-lookup"><span data-stu-id="0c2d1-181">Train the model</span></span>

<span data-ttu-id="0c2d1-182">Se si salva la spiegazione, la formazione verrà riavviata, questa volta utilizzando entrambe le spiegazioni in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="0c2d1-182">Saving your explanation will start the training again, this time using both explanations in our example.</span></span> <span data-ttu-id="0c2d1-183">Se il modello contiene informazioni sufficienti per estrarre i dati dai file di esempio etichettati, verranno visualizzati tutti i file contrassegnati con la **corrispondenza**.</span><span class="sxs-lookup"><span data-stu-id="0c2d1-183">If your model has enough information to extract the data from your labeled example files, you will see each file labeled with **Match**.</span></span> 

<span data-ttu-id="0c2d1-184">Se si riceve di nuovo una **mancata corrispondenza** nei file contrassegnati, potrebbe essere necessario creare un'altra spiegazione per fornire al modello ulteriori informazioni per identificare il tipo di documento oppure esaminare le modifiche apportate a quelle esistenti.</span><span class="sxs-lookup"><span data-stu-id="0c2d1-184">If you again receive a **Mismatch** on your labeled files, you may need to create another explanation to provide the model more information to identify the document type, or look at making changes to your existing ones.</span></span>

## <a name="test-your-model"></a><span data-ttu-id="0c2d1-185">Testare il modello</span><span class="sxs-lookup"><span data-stu-id="0c2d1-185">Test your model</span></span>

<span data-ttu-id="0c2d1-186">Se è stata ricevuta una corrispondenza nei file di esempio contrassegnati, è ora possibile testare il modello nei file di esempio senza etichetta rimanenti.</span><span class="sxs-lookup"><span data-stu-id="0c2d1-186">If you received a match on your labeled example files, you can now test your model on your remaining unlabeled example files.</span></span>

1. <span data-ttu-id="0c2d1-187">Nella Home page del modello fare clic sulla scheda **test** .  Verrà eseguito il modello nei file di esempio senza etichetta.</span><span class="sxs-lookup"><span data-stu-id="0c2d1-187">On the model home page, click the **Test** tab.  This will run the model on your unlabeled example files.</span></span>
2. <span data-ttu-id="0c2d1-188">Nell'elenco **file di test** , i file di esempio verranno visualizzati e mostreranno se il modello è in grado di estrarre le informazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="0c2d1-188">In the **Test files** list, your example files will display and will show if the model is able to extract the information you need from them.</span></span> <span data-ttu-id="0c2d1-189">È possibile utilizzare queste informazioni per determinare l'efficacia del classificatore per identificare i documenti.</span><span class="sxs-lookup"><span data-stu-id="0c2d1-189">You can use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![Test sui file](../media/content-understanding/test-filies-extractor.png) 

## <a name="see-also"></a><span data-ttu-id="0c2d1-191">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0c2d1-191">See Also</span></span>
  




