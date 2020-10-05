---
title: Creare un classificatore
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: Informazioni su come creare un classificatore
ms.openlocfilehash: 948ece1a19b7e6049167c373b3200efd316a60cd
ms.sourcegitcommit: 0f48beaca3afa4df12d41847014975d50a4ebe7d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/02/2020
ms.locfileid: "48338638"
---
# <a name="create-a-classifier-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="f6738-103">Creare un classificatore in Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="f6738-103">Create a classifier in Microsoft SharePoint Syntex</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL0R]  

</br>

<span data-ttu-id="f6738-104">Un classificatore è un tipo di modello che è possibile usare per automatizzare l'identificazione e la classificazione di un tipo di documento.</span><span class="sxs-lookup"><span data-stu-id="f6738-104">A classifier is a type of model that you can use to automate identification and classification of a document type.</span></span> <span data-ttu-id="f6738-105">Ad esempio, si può decidere di identificare tutti i documenti *Rinnovo del contratto* aggiunti alla raccolta documenti, come mostrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="f6738-105">For example, you may want to identify all *Contract Renewal* documents that are added to your document library, such as is shown in the following illustration.</span></span>

![Documento Rinnovo del contratto](../media/content-understanding/contract-renewal.png)

<span data-ttu-id="f6738-107">La creazione di un classificatore consente di creare un nuovo [tipo di contenuto di SharePoint](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) che verrà associato al modello.</span><span class="sxs-lookup"><span data-stu-id="f6738-107">Creating a classifier enables you to create a new [SharePoint Content Type](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) that will be associated to the model.</span></span>

<span data-ttu-id="f6738-108">Quando si crea il classificatore, è necessario creare *spiegazioni* per definire il modello.</span><span class="sxs-lookup"><span data-stu-id="f6738-108">When creating the classifier, you need to create *explanations* to define the model.</span></span> <span data-ttu-id="f6738-109">In questo modo è possibile identificare i dati comuni che si prevede di trovare in modo coerente in questo tipo di documento.</span><span class="sxs-lookup"><span data-stu-id="f6738-109">This enables you to note common data that you would expect to consistently find this document type.</span></span> 

<span data-ttu-id="f6738-110">Usare esempi del tipo di documento ("file di esempio") per "addestrare" il modello a identificare file con lo stesso tipo di contenuto.</span><span class="sxs-lookup"><span data-stu-id="f6738-110">Use examples of the document type ("example files") to "train" your model to identify files that have the same content type.</span></span>

<span data-ttu-id="f6738-111">Per creare un classificatore, è necessario:</span><span class="sxs-lookup"><span data-stu-id="f6738-111">To create a classifier, you need to:</span></span>
1. <span data-ttu-id="f6738-112">Assegnare un nome al modello.</span><span class="sxs-lookup"><span data-stu-id="f6738-112">Name your model.</span></span>
2. <span data-ttu-id="f6738-113">Aggiungere file di esempio.</span><span class="sxs-lookup"><span data-stu-id="f6738-113">Add your example files.</span></span>
3. <span data-ttu-id="f6738-114">Etichettare i file di esempio.</span><span class="sxs-lookup"><span data-stu-id="f6738-114">Label your example files.</span></span>
4. <span data-ttu-id="f6738-115">Creare una spiegazione.</span><span class="sxs-lookup"><span data-stu-id="f6738-115">Create an explanation.</span></span>
5. <span data-ttu-id="f6738-116">Testare il modello.</span><span class="sxs-lookup"><span data-stu-id="f6738-116">Test your model.</span></span>

> [!NOTE]
> <span data-ttu-id="f6738-117">Anche se il modello usa un classificatore per identificare e classificare i tipi di documento, si può anche decidere di estrarre informazioni specifiche da ogni file identificato dal modello.</span><span class="sxs-lookup"><span data-stu-id="f6738-117">While your model uses a classifier to identify and classify document types, you can also choose to pull specific pieces of information from each file identified by the model.</span></span> <span data-ttu-id="f6738-118">A questo scopo, occorre creare un **estrattore** da aggiungere al modello.</span><span class="sxs-lookup"><span data-stu-id="f6738-118">Do this by creating an **extractor** to add to your model.</span></span> <span data-ttu-id="f6738-119">Vedere [Creare un estrattore](create-an-extractor.md).</span><span class="sxs-lookup"><span data-stu-id="f6738-119">See [Create an extractor](create-an-extractor.md).</span></span>

## <a name="name-your-model"></a><span data-ttu-id="f6738-120">Assegnare un nome al modello</span><span class="sxs-lookup"><span data-stu-id="f6738-120">Name your model</span></span>

<span data-ttu-id="f6738-121">Per creare un modello occorre prima di tutto assegnargli un nome:</span><span class="sxs-lookup"><span data-stu-id="f6738-121">The first step to create your model is to give it a name:</span></span>

1. <span data-ttu-id="f6738-122">Nel Centro contenuti selezionare **Nuovo** e quindi **Crea un modello**.</span><span class="sxs-lookup"><span data-stu-id="f6738-122">From the Content Center, select **New**, and then **Create a model**.</span></span>
2. <span data-ttu-id="f6738-123">Nel riquadro **Nuovo modello di comprensione dei documenti** digitare il nome del modello nel campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="f6738-123">In the **New document understanding model** pane, in the **Name** field type the name of the model.</span></span> <span data-ttu-id="f6738-124">Ad esempio, se si vogliono identificare i documenti di rinnovo del contratto, è possibile denominare il modello *Rinnovo del contratto*.</span><span class="sxs-lookup"><span data-stu-id="f6738-124">For example, if you want to identify contract renewal documents, you could name the model *Contract Renewal*.</span></span>
3. <span data-ttu-id="f6738-125">Scegliere **Crea**.</span><span class="sxs-lookup"><span data-stu-id="f6738-125">Choose **Create**.</span></span> <span data-ttu-id="f6738-126">Verrà creata una home page per il modello.</span><span class="sxs-lookup"><span data-stu-id="f6738-126">This creates a home page for the model.</span></span></br>

    ![Home page del modello di classificatore](../media/content-understanding/model-home.png)

<span data-ttu-id="f6738-128">Quando si crea un modello, viene creato anche un nuovo tipo di contenuto del sito.</span><span class="sxs-lookup"><span data-stu-id="f6738-128">When you create a model, you are also creating a new site content type.</span></span> <span data-ttu-id="f6738-129">Un tipo di contenuto rappresenta una categoria di documenti che hanno caratteristiche comuni e condividono una raccolta di colonne o proprietà dei metadati per quel particolare contenuto.</span><span class="sxs-lookup"><span data-stu-id="f6738-129">A content type represents a category of documents that have common characteristics and share a collection of columns or metadata properties for that particular content.</span></span> <span data-ttu-id="f6738-130">I tipi di contenuto di SharePoint vengono gestiti tramite la [Raccolta tipi di contenuto](https://support.microsoft.com/office/create-or-customize-a-site-content-type-27eb6551-9867-4201-a819-620c5658a60f).</span><span class="sxs-lookup"><span data-stu-id="f6738-130">SharePoint Content Types are managed through the [Content types gallery](https://support.microsoft.com/office/create-or-customize-a-site-content-type-27eb6551-9867-4201-a819-620c5658a60f).</span></span> <span data-ttu-id="f6738-131">In questo esempio, quando si crea il modello, si crea un nuovo tipo di contenuto *Rinnovo del contratto*.</span><span class="sxs-lookup"><span data-stu-id="f6738-131">For this example, when you create the model, you are creating a new *Contract Renewal* content type.</span></span>

<span data-ttu-id="f6738-132">Selezionare **Impostazioni avanzate** se si vuole associare questo modello a un tipo di contenuto aziendale esistente nella Raccolta tipi di contenuto di SharePoint per usarne lo schema.</span><span class="sxs-lookup"><span data-stu-id="f6738-132">Select **Advanced settings** if you want to map this model to an existing enterprise content type in the SharePoint Content types gallery to use its schema.</span></span> <span data-ttu-id="f6738-133">I tipi di contenuto aziendale sono archiviati nell'hub del tipo di contenuto nell'interfaccia di amministrazione di SharePoint e vengono diffusi a tutti i siti del tenant.</span><span class="sxs-lookup"><span data-stu-id="f6738-133">Enterprise content types are stored in the Content Type Hub in the SharePoint admin center and are syndicated to all sites in the tenant.</span></span> <span data-ttu-id="f6738-134">Tenere presente che, anche se è possibile usare un tipo di contenuto esistente per utilizzarne lo schema e agevolare l'identificazione e la classificazione, è comunque necessario addestrare il modello a estrarre le informazioni dai file identificati.</span><span class="sxs-lookup"><span data-stu-id="f6738-134">Note that while you can use an existing content type to leverage its schema to help with identification and classification, you still need to train your model to extract information from files it identifies.</span></span></br>

![Impostazioni avanzate](../media/content-understanding/advanced-settings.png)

## <a name="add-your-example-files"></a><span data-ttu-id="f6738-136">Aggiungere file di esempio</span><span class="sxs-lookup"><span data-stu-id="f6738-136">Add your example files</span></span>

<span data-ttu-id="f6738-137">Nella home page del modello aggiungere i file di esempio necessari per addestrare il modello a identificare il tipo di documento.</span><span class="sxs-lookup"><span data-stu-id="f6738-137">On the model home page, add your examples files you will need to help train the model to identify your document type.</span></span> </br>
</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4D0iX] 

</br>

> [!NOTE]
> <span data-ttu-id="f6738-138">È consigliabile usare gli stessi file sia per il classificatore che per l'[addestramento dell'estrattore](create-an-extractor.md).</span><span class="sxs-lookup"><span data-stu-id="f6738-138">You should use the same files for both classifier and [extractor training](create-an-extractor.md).</span></span> <span data-ttu-id="f6738-139">È sempre possibile aggiungere altre informazioni in seguito, ma in genere si aggiunge un set completo di file di esempio.</span><span class="sxs-lookup"><span data-stu-id="f6738-139">You always have the option to add more later, but typically you add a full set of example files.</span></span> <span data-ttu-id="f6738-140">Etichettarne alcuni per eseguire il training del modello e testare i file restanti senza etichetta per valutare l'adeguatezza del modello.</span><span class="sxs-lookup"><span data-stu-id="f6738-140">Label some to train your model, and test the remaining unlabeled ones to evaluate model fitness.</span></span> 

<span data-ttu-id="f6738-141">Per il set di training, è bene usare esempi sia positivi sia negativi:</span><span class="sxs-lookup"><span data-stu-id="f6738-141">For your training set, you want to use both positive and negative examples:</span></span>
- <span data-ttu-id="f6738-142">Esempio positivo: documenti che rappresentano il tipo di documento.</span><span class="sxs-lookup"><span data-stu-id="f6738-142">Positive example: Documents that represent the document type.</span></span> <span data-ttu-id="f6738-143">Contengono stringhe e informazioni che sono sempre presenti nei documenti di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="f6738-143">These contain strings and information that would always be in this type of document.</span></span>
- <span data-ttu-id="f6738-144">Esempio negativo: qualsiasi altro documento che non rappresenta il documento da classificare.</span><span class="sxs-lookup"><span data-stu-id="f6738-144">Negative example: Any other document that does not represent the document you want to classify.</span></span> 

<span data-ttu-id="f6738-145">Usare almeno cinque esempi positivi e almeno un esempio negativo per addestrare il modello.</span><span class="sxs-lookup"><span data-stu-id="f6738-145">Be sure to use at least five positive examples and at least one negative example to train your model.</span></span>  <span data-ttu-id="f6738-146">Dopo il processo di training, è possibile crearne altri per testare il modello.</span><span class="sxs-lookup"><span data-stu-id="f6738-146">You want to create additional ones to test your model after the training process.</span></span>

<span data-ttu-id="f6738-147">Per aggiungere file di esempio:</span><span class="sxs-lookup"><span data-stu-id="f6738-147">To add example files:</span></span>

1. <span data-ttu-id="f6738-148">Nella home page del modello fare clic su **Aggiungi file** nel riquadro **Aggiungi file di esempio**.</span><span class="sxs-lookup"><span data-stu-id="f6738-148">On the model home page, in the **Add example files** tile, click **Add files**.</span></span>
2. <span data-ttu-id="f6738-149">Nella pagina **Selezionare i file di esempio per il modello** selezionare i file di esempio nella raccolta di file di training nel centro contenuti.</span><span class="sxs-lookup"><span data-stu-id="f6738-149">On the **Select example files for your model** page, select your example files from the Training files library in the content center.</span></span> <span data-ttu-id="f6738-150">Se non sono ancora stati caricati, scegliere di caricarli subito facendo clic su **Carica** per copiarli nella raccolta di file di training.</span><span class="sxs-lookup"><span data-stu-id="f6738-150">If you had not already uploaded them there, choose to upload them now by clicking **Upload** to copy them to the Training files library.</span></span>
3. <span data-ttu-id="f6738-151">Dopo aver selezionato i file di esempio da usare per il modello, fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="f6738-151">After selecting your example files to use to train the model, click **Add**.</span></span>

    ![Selezionare i file di esempio](../media/content-understanding/select-sample.png) 

## <a name="label-your-example-files"></a><span data-ttu-id="f6738-153">Etichettare i file di esempio</span><span class="sxs-lookup"><span data-stu-id="f6738-153">Label your example files</span></span>

<span data-ttu-id="f6738-154">Dopo aver aggiunto i file di esempio, è necessario etichettarli come esempi positivi o negativi.</span><span class="sxs-lookup"><span data-stu-id="f6738-154">After adding your example files, you need to label them as either positive or negative examples.</span></span>

1. <span data-ttu-id="f6738-155">Nella home page del modello, fare clic su **Eseguire il training del classificatore** nel riquadro **Classificare i file ed eseguire il training**.</span><span class="sxs-lookup"><span data-stu-id="f6738-155">From the model home page, on the **Classify files and run training** tile, click **Train Classifier**.</span></span>
   <span data-ttu-id="f6738-156">Verrà visualizzata la pagina dell'etichetta con un elenco dei file di esempio e il primo file mostrato nel visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="f6738-156">This displays the label page that shows a listing of your example files, with the first file visible in the viewer.</span></span>
2. <span data-ttu-id="f6738-157">Nel visualizzatore nella parte superiore del primo file di esempio dovrebbe essere presente un testo che chiede se il file è un esempio del modello appena creato.</span><span class="sxs-lookup"><span data-stu-id="f6738-157">In the viewer on the top of the first example file, you should see text asking if the file is an example of the model you just created.</span></span> <span data-ttu-id="f6738-158">Se è un esempio positivo, selezionare **Sì**.</span><span class="sxs-lookup"><span data-stu-id="f6738-158">If it is a positive example, select **Yes**.</span></span> <span data-ttu-id="f6738-159">Se è un esempio negativo, selezionare **No**.</span><span class="sxs-lookup"><span data-stu-id="f6738-159">If it is a negative example, select **No**.</span></span>
3. <span data-ttu-id="f6738-160">Nell'elenco **Esempi etichettati** a sinistra selezionare altri file da usare come esempi ed etichettarli.</span><span class="sxs-lookup"><span data-stu-id="f6738-160">From the **Labeled examples** list on the left, select additional files that you want to use as examples, and label them.</span></span> 

    ![Home page del classificatore](../media/content-understanding/classifier-home-page.png) 


> [!NOTE]
> <span data-ttu-id="f6738-162">Etichettare almeno cinque esempi positivi.</span><span class="sxs-lookup"><span data-stu-id="f6738-162">Label at least five positive examples.</span></span> <span data-ttu-id="f6738-163">È anche necessario etichettare almeno un esempio negativo.</span><span class="sxs-lookup"><span data-stu-id="f6738-163">You must also label at least one negative example.</span></span> 

## <a name="create-an-explanation"></a><span data-ttu-id="f6738-164">Creare una spiegazione</span><span class="sxs-lookup"><span data-stu-id="f6738-164">Create an explanation</span></span>

<span data-ttu-id="f6738-165">Il passaggio successivo consiste nel creare una spiegazione nella pagina Avvia training.</span><span class="sxs-lookup"><span data-stu-id="f6738-165">The next step is for you to create an explanation on the Train page.</span></span> <span data-ttu-id="f6738-166">Una spiegazione aiuta il modello a comprendere come riconoscere il documento.</span><span class="sxs-lookup"><span data-stu-id="f6738-166">An explanation helps the model understand how to recognize the document.</span></span> <span data-ttu-id="f6738-167">Ad esempio, i documenti relativi al rinnovo del contratto contengono sempre una stringa di testo *Richiesta di informazioni aggiuntive*.</span><span class="sxs-lookup"><span data-stu-id="f6738-167">For example, the Contract Renewal documents always contain a *Request for additional disclosure* text string.</span></span>

> [!Note]
> <span data-ttu-id="f6738-168">Quando viene usata con gli estrattori, una spiegazione identifica la stringa da estrarre dal documento.</span><span class="sxs-lookup"><span data-stu-id="f6738-168">When used with extractors, an explanation identifies the string that you want to extract from the document.</span></span> 

<span data-ttu-id="f6738-169">Per creare una spiegazione:</span><span class="sxs-lookup"><span data-stu-id="f6738-169">To create an explanation:</span></span>

1. <span data-ttu-id="f6738-170">Nella home page del modello selezionare la scheda **Avvia training** per passare alla pagina corrispondente.</span><span class="sxs-lookup"><span data-stu-id="f6738-170">From the model home page, select the **Train** tab to go to the Train page.</span></span>
2. <span data-ttu-id="f6738-171">Nella sezione **File con training** della pagina Avvia training dovrebbe essere presente un elenco dei file di esempio precedentemente etichettati.</span><span class="sxs-lookup"><span data-stu-id="f6738-171">On the Train page, in the **Trained files** section you should see a list of the sample files that you previously labeled.</span></span> <span data-ttu-id="f6738-172">Selezionare uno dei file positivi nell'elenco. Verrà visualizzato nel visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="f6738-172">Select one of the positive files from the list, and it displays in the viewer.</span></span>
3. <span data-ttu-id="f6738-173">Nella sezione Spiegazione selezionare **Nuovo** e quindi **Vuoto**.</span><span class="sxs-lookup"><span data-stu-id="f6738-173">In the Explanation section, select **New** and then **Blank**.</span></span>
4. <span data-ttu-id="f6738-174">Nella pagina **Crea spiegazione**:</span><span class="sxs-lookup"><span data-stu-id="f6738-174">On the **Create an explanation** page:</span></span></br>
    <span data-ttu-id="f6738-175">a.</span><span class="sxs-lookup"><span data-stu-id="f6738-175">a.</span></span> <span data-ttu-id="f6738-176">Digitare il **Nome**, ad esempio "Blocco divulgazione".</span><span class="sxs-lookup"><span data-stu-id="f6738-176">Type the **Name** (for example, "Disclosure Block").</span></span></br>
    <span data-ttu-id="f6738-177">b.</span><span class="sxs-lookup"><span data-stu-id="f6738-177">b.</span></span> <span data-ttu-id="f6738-178">Selezionare il **Tipo**.</span><span class="sxs-lookup"><span data-stu-id="f6738-178">Select the **Type**.</span></span> <span data-ttu-id="f6738-179">In questo caso selezionare **Elenco frasi** perché viene aggiunta una stringa di testo.</span><span class="sxs-lookup"><span data-stu-id="f6738-179">For the sample, select **Phrase list**, since you add a text string.</span></span></br>
    <span data-ttu-id="f6738-180">c.</span><span class="sxs-lookup"><span data-stu-id="f6738-180">c.</span></span> <span data-ttu-id="f6738-181">Digitare la stringa nella casella **Digitare qui**.</span><span class="sxs-lookup"><span data-stu-id="f6738-181">In the **Type here** box, type the string.</span></span> <span data-ttu-id="f6738-182">Per questo esempio, aggiungere "Richiesta di informazioni aggiuntive".</span><span class="sxs-lookup"><span data-stu-id="f6738-182">For the sample, add "Request for additional disclosure".</span></span> <span data-ttu-id="f6738-183">È possibile selezionare **Maiuscole/Minuscole** se è necessario distinguere tra maiuscole e minuscole nella stringa.</span><span class="sxs-lookup"><span data-stu-id="f6738-183">You can select **Case sensitive** if the string needs to be case sensitive.</span></span></br>
    <span data-ttu-id="f6738-184">d.</span><span class="sxs-lookup"><span data-stu-id="f6738-184">d.</span></span> <span data-ttu-id="f6738-185">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f6738-185">Click **Save**.</span></span>

    ![Creare una spiegazione](../media/content-understanding/explanation.png) 
    
 
5. <span data-ttu-id="f6738-187">A questo punto, il modello verifica se la spiegazione creata consente di identificare correttamente gli altri file di esempio etichettati come esempi positivi e negativi.</span><span class="sxs-lookup"><span data-stu-id="f6738-187">The model now checks to see if the explanation you created was good enough to identify the remaining labeled example files correctly, as positive and negative examples.</span></span> <span data-ttu-id="f6738-188">Al termine del training, controllare la colonna **Valutazione** nella sezione File con training per visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="f6738-188">In the Trained Files section, check the **Evaluation** column after the training has completed to see the results.</span></span> <span data-ttu-id="f6738-189">I file mostrano il valore **Corrisponde** se le spiegazioni create sono risultate sufficienti per trovare una corrispondenza con ciò che è stato etichettato come positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="f6738-189">The files show a value of **Match**, if the explanations you created was enough to match what you labeled as positive or negative.</span></span>

    ![Valore Corrisponde](../media/content-understanding/match.png) 

<span data-ttu-id="f6738-191">Se i file etichettati risultano **Non corrispondenti**, può essere necessario creare un'ulteriore spiegazione per fornire altre informazioni al modello per identificare il tipo di documento.</span><span class="sxs-lookup"><span data-stu-id="f6738-191">If you receive a **Mismatch** on the labeled files, you may need to create an additional explanation to provide the model more information to identify the document type.</span></span> <span data-ttu-id="f6738-192">In questo caso, fare clic sul file per ottenere altre informazioni sul motivo della mancata corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="f6738-192">If this happens, click on the file to get more information about why the mismatch occurred.</span></span>

## <a name="test-your-model"></a><span data-ttu-id="f6738-193">Testare il modello</span><span class="sxs-lookup"><span data-stu-id="f6738-193">Test your model</span></span>

<span data-ttu-id="f6738-194">Se è stata rilevata una corrispondenza nei file di esempio etichettati, è possibile testare il modello nei rimanenti file di esempio non etichettati, non ancora esaminati dal modello.</span><span class="sxs-lookup"><span data-stu-id="f6738-194">If you received a match on your labeled sample files, you can now  test your model on your remaining unlabeled example files that the model has not seen before.</span></span>  <span data-ttu-id="f6738-195">Questo è un passaggio opzionale, ma utile per valutare l'adeguatezza del modello prima di usarlo, testandolo sui file che il modello non ha ancora esaminato.</span><span class="sxs-lookup"><span data-stu-id="f6738-195">This is optional, but a useful step to evaluate the “fitness” or readiness of the model before using it, by testing it on files the model hasn’t seen before.</span></span>

1. <span data-ttu-id="f6738-196">Nella home page del modello selezionare la scheda **Test**. Il modello viene eseguito nei file di esempio non etichettati.</span><span class="sxs-lookup"><span data-stu-id="f6738-196">From the model home page, select the **Test** tab.  This runs the model on your unlabeled sample files.</span></span>
2. <span data-ttu-id="f6738-197">Nell'elenco **Testa i file** vengono visualizzati i file di esempio e viene indicato se il modello prevede che siano positivi o negativi.</span><span class="sxs-lookup"><span data-stu-id="f6738-197">In the **Test files** list, your example files display and shows if the model predicted them to be positive or negative.</span></span> <span data-ttu-id="f6738-198">Usare queste informazioni per determinare l'efficacia del classificatore nell'identificazione dei documenti.</span><span class="sxs-lookup"><span data-stu-id="f6738-198">Use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![Test di file non etichettati](../media/content-understanding/test-on-files.png) 

## <a name="see-also"></a><span data-ttu-id="f6738-200">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f6738-200">See Also</span></span>
[<span data-ttu-id="f6738-201">Creare un estrattore</span><span class="sxs-lookup"><span data-stu-id="f6738-201">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="f6738-202">Panoramica sull'analisi dei documenti</span><span class="sxs-lookup"><span data-stu-id="f6738-202">Document Understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="f6738-203">Tipi di spiegazione</span><span class="sxs-lookup"><span data-stu-id="f6738-203">Explanation types</span></span>](explanation-types-overview.md)

[<span data-ttu-id="f6738-204">Applicare un modello</span><span class="sxs-lookup"><span data-stu-id="f6738-204">Apply a model</span></span>](apply-a-model.md) 
