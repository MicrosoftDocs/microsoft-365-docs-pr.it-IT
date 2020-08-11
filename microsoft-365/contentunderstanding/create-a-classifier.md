---
title: Creare un classificatore (anteprima)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Informazioni su come creare un classificatore
ms.openlocfilehash: 088770ace8914b583b184c78c3ce110d9d68b4c7
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612609"
---
# <a name="create-a-classifier-preview"></a><span data-ttu-id="27f66-103">Creare un classificatore (anteprima)</span><span class="sxs-lookup"><span data-stu-id="27f66-103">Create a classifier (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="27f66-104">Il contenuto di questo articolo è relativo all'anteprima privata di Project Cortex.</span><span class="sxs-lookup"><span data-stu-id="27f66-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="27f66-105">[Per ulteriori informazioni, vedere Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="27f66-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL0R]  

</br>

<span data-ttu-id="27f66-106">Un classificatore è un tipo di modello che automatizza l'identificazione e la classificazione di un tipo di documento.</span><span class="sxs-lookup"><span data-stu-id="27f66-106">A classifier is a type of model that automates identification and classification of a document type.</span></span> <span data-ttu-id="27f66-107">Ad esempio, è possibile identificare tutti i documenti di *rinnovo del contratto* che vengono aggiunti alla raccolta documenti, come quelli riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="27f66-107">For example, you may want to identify all *Contract Renewal* documents that are added to your document library, such as the following.</span></span>

![Documento di rinnovo del contratto](../media/content-understanding/contract-renewal.png)

<span data-ttu-id="27f66-109">La creazione di un classificatore creerà un nuovo [tipo di contenuto di SharePoint](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) che verrà associato al modello.</span><span class="sxs-lookup"><span data-stu-id="27f66-109">Creating a classifier will create a new [SharePoint Content Type](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) that will be associated to the model.</span></span>

<span data-ttu-id="27f66-110">Quando si crea il classificatore, è necessario creare *spiegazioni* che consentano di definire il modello osservando i dati comuni che si prevede di trovare in modo coerente per questo tipo di documento.</span><span class="sxs-lookup"><span data-stu-id="27f66-110">When creating the classifier, you need to create *explanations* that help to define the model by noting common data that you would expect to find consistently for this document type.</span></span> 

<span data-ttu-id="27f66-111">È possibile utilizzare esempi del tipo di documento ("file di esempio") per facilitare la formazione del modello per identificare i file con lo stesso tipo di contenuto.</span><span class="sxs-lookup"><span data-stu-id="27f66-111">You use examples of the document type ("example files") to help "train" your model to identify files that have the same content type.</span></span>

<span data-ttu-id="27f66-112">Per creare un classificatore, è necessario eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="27f66-112">To create a classifier, you need to:</span></span>
1. <span data-ttu-id="27f66-113">Assegnare un nome al modello</span><span class="sxs-lookup"><span data-stu-id="27f66-113">Name your model</span></span>
2. <span data-ttu-id="27f66-114">Aggiungere i file di esempio</span><span class="sxs-lookup"><span data-stu-id="27f66-114">Add your example files</span></span>
3. <span data-ttu-id="27f66-115">Contrassegnare i file di esempio</span><span class="sxs-lookup"><span data-stu-id="27f66-115">Label your example files</span></span>
4. <span data-ttu-id="27f66-116">Creare una spiegazione</span><span class="sxs-lookup"><span data-stu-id="27f66-116">Create an explanation</span></span>
5. <span data-ttu-id="27f66-117">Testare il modello</span><span class="sxs-lookup"><span data-stu-id="27f66-117">Test your model</span></span> 

> [!Note]
> <span data-ttu-id="27f66-118">Mentre un classificatore viene utilizzato dal modello per identificare e classificare i tipi di documenti, è anche possibile scegliere di estrarre informazioni specifiche da ogni file identificato dal modello.</span><span class="sxs-lookup"><span data-stu-id="27f66-118">While a classifier is used by your model to identify and classify document types, you can also choose to pull specific pieces of information from each file identified by the model.</span></span> <span data-ttu-id="27f66-119">A tale scopo, è possibile creare un **estrattore** da aggiungere al modello e questo viene descritto in [creare un estrattore](create-an-extractor.md).</span><span class="sxs-lookup"><span data-stu-id="27f66-119">You do this by creating an **extractor** to add to your model, and this is described in [Create an extractor](create-an-extractor.md).</span></span>

## <a name="name-your-model"></a><span data-ttu-id="27f66-120">Assegnare un nome al modello</span><span class="sxs-lookup"><span data-stu-id="27f66-120">Name your model</span></span>

<span data-ttu-id="27f66-121">Il primo passaggio consiste nel creare il modello nel centro di contenuto assegnando un nome:</span><span class="sxs-lookup"><span data-stu-id="27f66-121">The first step is to create your model in your Content Center by giving it a name:</span></span>

1. <span data-ttu-id="27f66-122">Nel centro contenuto fare clic su **nuovo**e quindi su **Crea un modello**.</span><span class="sxs-lookup"><span data-stu-id="27f66-122">In your Content Center, click **New**, and then click **Create a model**.</span></span>
2. <span data-ttu-id="27f66-123">Nel riquadro **nuovo modello di informazioni sul documento** , nel campo **nome** , digitare il nome del modello.</span><span class="sxs-lookup"><span data-stu-id="27f66-123">In the **New document understanding model** pane, in the **Name** field, type the name of the model.</span></span> <span data-ttu-id="27f66-124">Ad esempio, se si desidera identificare i documenti di rinnovo del contratto, è possibile assegnare un nome al *rinnovo del contratto*del modello.</span><span class="sxs-lookup"><span data-stu-id="27f66-124">For our example, if we want to identify contract renewal documents, we might name this model *Contract Renewal*.</span></span>
3. <span data-ttu-id="27f66-125">Fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="27f66-125">Click **Create**.</span></span> <span data-ttu-id="27f66-126">Verrà creata una Home page per il modello.</span><span class="sxs-lookup"><span data-stu-id="27f66-126">This will create a home page for the model.</span></span></br>

    ![Home page del modello di classificazione](../media/content-understanding/model-home.png)

<span data-ttu-id="27f66-128">Quando si crea un modello, si crea un nuovo tipo di contenuto di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="27f66-128">When you create a model, you are creating a new SharePoint content type.</span></span> <span data-ttu-id="27f66-129">Un tipo di contenuto di SharePoint rappresenta una categoria di documenti con caratteristiche comuni e la condivisione di una raccolta di colonne o proprietà dei metadati per il contenuto specifico.</span><span class="sxs-lookup"><span data-stu-id="27f66-129">A SharePoint content type represents a category of documents that have common characteristics and share a collection of columns or metadata properties for that particular content.</span></span> <span data-ttu-id="27f66-130">I tipi di contenuto di SharePoint vengono gestiti tramite la [raccolta tipi di contenuto]().</span><span class="sxs-lookup"><span data-stu-id="27f66-130">SharePoint Content Types are managed through the [Content types gallery]().</span></span> <span data-ttu-id="27f66-131">Ad esempio, quando si crea il modello, verrà creato un nuovo tipo di contenuto per il *rinnovo del contratto* .</span><span class="sxs-lookup"><span data-stu-id="27f66-131">For our example, when we create the model, we will be creating a new *Contract Renewal* content type.</span></span>

<span data-ttu-id="27f66-132">Selezionare **Impostazioni avanzate** se si desidera eseguire il mapping di questo modello a un tipo di contenuto esistente nella raccolta tipi di contenuto di SharePoint per utilizzarne lo schema.</span><span class="sxs-lookup"><span data-stu-id="27f66-132">Select **Advanced settings** if you want to map this model to an existing content type in the SharePoint Content types gallery to use its schema.</span></span> <span data-ttu-id="27f66-133">Si noti che, sebbene sia possibile utilizzare un tipo di contenuto esistente per sfruttare il relativo schema per facilitare l'identificazione e la classificazione, sarà comunque necessario addestrare il modello per estrarre informazioni dai file identificati.</span><span class="sxs-lookup"><span data-stu-id="27f66-133">Note that while you can use an existing content type to leverage its schema to help with identification and classification, you will still need to train your model to extract information from files it identifies.</span></span></br>

![Impostazioni avanzate](../media/content-understanding/advanced-settings.png)

## <a name="add-your-example-files"></a><span data-ttu-id="27f66-135">Aggiungere i file di esempio</span><span class="sxs-lookup"><span data-stu-id="27f66-135">Add your example files</span></span>

<span data-ttu-id="27f66-136">Nella Home page del modello è possibile aggiungere i file degli esempi necessari per la formazione del modello per identificare il tipo di documento.</span><span class="sxs-lookup"><span data-stu-id="27f66-136">On the model home page, you can add your examples files you will need to help train the model to identify your document type.</span></span> </br>
</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4D0iX] 

</br>

> [!Note]
> <span data-ttu-id="27f66-137">Gli stessi file devono essere utilizzati sia per i corsi di classificazione che per gli [estrattori](create-an-extractor.md).</span><span class="sxs-lookup"><span data-stu-id="27f66-137">The same files should be used for both classifier and [extractor training](create-an-extractor.md).</span></span> <span data-ttu-id="27f66-138">Si ha sempre la possibilità di aggiungere altre versioni successive, ma in genere è necessario aggiungere un set completo di file di esempio.</span><span class="sxs-lookup"><span data-stu-id="27f66-138">You always have the option to add more later, but typically you should add a full set of example files.</span></span> <span data-ttu-id="27f66-139">Sarà necessario etichettarne alcuni per formare il modello e testare quelli restanti senza etichetta per valutare la forma fisica del modello.</span><span class="sxs-lookup"><span data-stu-id="27f66-139">You will label some to train your model, and test the remaining unlabeled ones to evaluate model fitness.</span></span> 

<span data-ttu-id="27f66-140">Per il set di formazione, è consigliabile utilizzare esempi positivi e esempi negativi:</span><span class="sxs-lookup"><span data-stu-id="27f66-140">For your training set, you will want to use both positive examples, and negative examples:</span></span>
- <span data-ttu-id="27f66-141">Esempio positivo: documenti che rappresentano il tipo di documento.</span><span class="sxs-lookup"><span data-stu-id="27f66-141">Positive example: Documents that represent the document type.</span></span> <span data-ttu-id="27f66-142">Contengono stringhe e informazioni che sarebbero sempre presenti in questo tipo di documento.</span><span class="sxs-lookup"><span data-stu-id="27f66-142">They contain strings and information that would always be in this type of document.</span></span>
- <span data-ttu-id="27f66-143">Esempio negativo: documenti che non rappresentano il tipo di documento.</span><span class="sxs-lookup"><span data-stu-id="27f66-143">Negative example: Documents that do not represent the document type.</span></span>  <span data-ttu-id="27f66-144">Si tratta di stringhe mancanti e di informazioni che devono essere presenti in questo tipo di documento.</span><span class="sxs-lookup"><span data-stu-id="27f66-144">They are missing strings and information that needs to be present in this type of document.</span></span>

<span data-ttu-id="27f66-145">Sarà necessario utilizzare almeno cinque esempi positivi e un esempio negativo per la formazione del modello.</span><span class="sxs-lookup"><span data-stu-id="27f66-145">You will want to use at least five positive examples and one negative examples to train your model.</span></span>  <span data-ttu-id="27f66-146">Dopo l'allenamento, è necessario avere altre informazioni per testare il modello.</span><span class="sxs-lookup"><span data-stu-id="27f66-146">You will want to have additional ones to test your model after training.</span></span>

<span data-ttu-id="27f66-147">Per aggiungere file di esempio:</span><span class="sxs-lookup"><span data-stu-id="27f66-147">To add sample files:</span></span>

1. <span data-ttu-id="27f66-148">Nella Home page del modello fare clic su **Aggiungi file**nel riquadro della **raccolta di esempi di compilazione** .</span><span class="sxs-lookup"><span data-stu-id="27f66-148">On the model home page, in the **Build sample library** tile, click **Add files**.</span></span>
2. <span data-ttu-id="27f66-149">Nella pagina **selezionare** i file di esempio della pagina del modello selezionare i file degli esempi dalla libreria file di esempio nel centro contenuto.</span><span class="sxs-lookup"><span data-stu-id="27f66-149">On the **Select sample files for your model** page, select your example files from the Sample files library in the Content Center.</span></span> <span data-ttu-id="27f66-150">Se non li hai già caricati, puoi scegliere di caricarli subito facendo clic su **carica** per spostarli nella raccolta file di esempio.</span><span class="sxs-lookup"><span data-stu-id="27f66-150">If you had not already uploaded them there, you can choose to upload them now by clicking **Upload** to move them the Sample file library.</span></span>
3. <span data-ttu-id="27f66-151">Dopo aver selezionato i file di esempio da utilizzare per la formazione del modello, fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="27f66-151">After selecting your example files to use to train the model, click **Add**.</span></span>

    ![Selezionare i file di esempio](../media/content-understanding/select-sample.png) 

## <a name="label-your-example-files"></a><span data-ttu-id="27f66-153">Contrassegnare i file di esempio</span><span class="sxs-lookup"><span data-stu-id="27f66-153">Label your example files</span></span>

<span data-ttu-id="27f66-154">Dopo aver aggiunto i file di esempio, è necessario etichettarli come esempi positivi o esempi negativi.</span><span class="sxs-lookup"><span data-stu-id="27f66-154">After adding your example files, you then need to label them as either positive examples or negative examples.</span></span>

1. <span data-ttu-id="27f66-155">Nella Home page del modello fare clic su **classificazione**dei **file e sull'esecuzione** del riquadro di addestramento.</span><span class="sxs-lookup"><span data-stu-id="27f66-155">On the model home page, on the **Classify files and run training** tile, click **Train Classifier**.</span></span>
   <span data-ttu-id="27f66-156">Verrà visualizzata la pagina etichetta che mostra un elenco dei file di esempio, con il primo file visibile nel visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="27f66-156">This will display the label page that shows a listing of your example files, with the first file visible in the viewer.</span></span>
2. <span data-ttu-id="27f66-157">Nel Visualizzatore, nella parte superiore del primo file di esempio, verrà visualizzato un messaggio in cui viene chiesto se il file è un esempio del modello appena creato.</span><span class="sxs-lookup"><span data-stu-id="27f66-157">In the viewer, on the top of the first example file, you will see text asking you if the file is an example of the model you just created.</span></span> <span data-ttu-id="27f66-158">Se si tratta di un esempio positivo, selezionare **Sì**.</span><span class="sxs-lookup"><span data-stu-id="27f66-158">If it is a positive example, select **Yes**.</span></span> <span data-ttu-id="27f66-159">Se si tratta di un esempio negativo, selezionare **No**.</span><span class="sxs-lookup"><span data-stu-id="27f66-159">If it is a negative example, select **No**.</span></span>
3. <span data-ttu-id="27f66-160">Nell'elenco degli **esempi etichettati** a sinistra, selezionare altri file che si desidera utilizzare come esempi ed etichettarli.</span><span class="sxs-lookup"><span data-stu-id="27f66-160">From the **Labeled examples** list on the left, select additional files that you want to use as examples, and label them as well.</span></span> 

    ![Home page del modello di classificazione](../media/content-understanding/classifier-home-page.png) 


> [!Note]
> <span data-ttu-id="27f66-162">Etichettare almeno cinque esempi positivi e un esempio negativo.</span><span class="sxs-lookup"><span data-stu-id="27f66-162">Label at least five positive examples, and one negative example.</span></span> 

## <a name="create-an-explanation"></a><span data-ttu-id="27f66-163">Creare una spiegazione</span><span class="sxs-lookup"><span data-stu-id="27f66-163">Create an explanation</span></span>

<span data-ttu-id="27f66-164">Il passaggio successivo consiste nel creare una spiegazione sulla pagina del treno.</span><span class="sxs-lookup"><span data-stu-id="27f66-164">The next step is to create an explanation on the Train page.</span></span>  <span data-ttu-id="27f66-165">Una spiegazione è un suggerimento o un indizio per aiutare il modello a capire come riconoscere questo documento.</span><span class="sxs-lookup"><span data-stu-id="27f66-165">An explanation is a hint or clue to help the model understand how to recognize this document.</span></span> <span data-ttu-id="27f66-166">Ad esempio, i documenti di rinnovo del contratto contengono sempre una *richiesta per una stringa di testo di divulgazione aggiuntiva* .</span><span class="sxs-lookup"><span data-stu-id="27f66-166">For example, our Contract Renewal documents always contain a *Request for additional disclosure* text string.</span></span>

> [!Note]
> <span data-ttu-id="27f66-167">Se utilizzato con gli estrattori, viene utilizzata una spiegazione per identificare la stringa che si desidera estrarre dal documento.</span><span class="sxs-lookup"><span data-stu-id="27f66-167">When used with extractors, an explanation is use to identify the string that you want to extract from the document.</span></span> 

<span data-ttu-id="27f66-168">Per creare una spiegazione:</span><span class="sxs-lookup"><span data-stu-id="27f66-168">To create an explanation:</span></span>

1. <span data-ttu-id="27f66-169">Nella Home page del modello fare clic sulla scheda **treno** per andare alla pagina del treno.</span><span class="sxs-lookup"><span data-stu-id="27f66-169">On the model home page, click the **Train** tab to go to the Train page.</span></span>
2. <span data-ttu-id="27f66-170">Nella sezione **file addestrati** della pagina del treno verrà visualizzato un elenco dei file di esempio precedentemente etichettati.</span><span class="sxs-lookup"><span data-stu-id="27f66-170">On the Train page, in the **Trained files** section, you will see a list of the example files that you had labeled previously.</span></span> <span data-ttu-id="27f66-171">Selezionare uno dei file positivi dall'elenco, che verrà visualizzato nel visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="27f66-171">Select one of your positive files from the list, and it will display in the viewer.</span></span>
3. <span data-ttu-id="27f66-172">Nella sezione spiegazione fare clic su **nuovo**e quindi su **vuoto**.</span><span class="sxs-lookup"><span data-stu-id="27f66-172">In the Explanation section, click **New**, then click **Blank**.</span></span>
4. <span data-ttu-id="27f66-173">Nella pagina **Crea una spiegazione** :</span><span class="sxs-lookup"><span data-stu-id="27f66-173">On the **Create an explanation** page:</span></span></br>
    <span data-ttu-id="27f66-174">a.</span><span class="sxs-lookup"><span data-stu-id="27f66-174">a.</span></span> <span data-ttu-id="27f66-175">Digitare il **nome** (ad esempio, "blocco di disclosure").</span><span class="sxs-lookup"><span data-stu-id="27f66-175">Type the **Name** (for example, "Disclosure Block").</span></span></br>
    <span data-ttu-id="27f66-176">b.</span><span class="sxs-lookup"><span data-stu-id="27f66-176">b.</span></span> <span data-ttu-id="27f66-177">Selezionare il **tipo**.</span><span class="sxs-lookup"><span data-stu-id="27f66-177">Select the **Type**.</span></span> <span data-ttu-id="27f66-178">In questo esempio, si selezionerà l' **elenco delle frasi**, poiché si aggiunge una stringa di testo.</span><span class="sxs-lookup"><span data-stu-id="27f66-178">For our example, we'll select **Phrase list**, since we are adding a text string.</span></span></br>
    <span data-ttu-id="27f66-179">c.</span><span class="sxs-lookup"><span data-stu-id="27f66-179">c.</span></span> <span data-ttu-id="27f66-180">Nella casella **digitare qui** Digitare la stringa.</span><span class="sxs-lookup"><span data-stu-id="27f66-180">In the **Type here** box, type the string.</span></span>  <span data-ttu-id="27f66-181">In questo esempio, verrà aggiunta la richiesta di informazioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="27f66-181">For our example, we'll add "Request for additional disclosure".</span></span> <span data-ttu-id="27f66-182">È **possibile selezionare maiuscole/minuscole** se la stringa deve essere distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="27f66-182">You can select **Case sensitive** if the string needs to be case sensitive.</span></span></br>
    <span data-ttu-id="27f66-183">d.</span><span class="sxs-lookup"><span data-stu-id="27f66-183">d.</span></span> <span data-ttu-id="27f66-184">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="27f66-184">Click **Save**.</span></span>

    ![Creare una spiegazione](../media/content-understanding/explanation.png) 
    
 
5.  <span data-ttu-id="27f66-186">Il modello controllerà ora se la spiegazione creata è stata sufficiente per identificare correttamente i file di esempio con etichetta rimanenti come esempi positivi e negativi.</span><span class="sxs-lookup"><span data-stu-id="27f66-186">The model will now check to see if the explanation you created was good enough to identify your remaining labeled example files correctly as positive and negative examples.</span></span> <span data-ttu-id="27f66-187">Nella sezione file addestrati selezionare la colonna **valutazione** dopo aver completato il training per visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="27f66-187">In Trained Files section, check the **Evaluation** column after the training has completed to see the results.</span></span>  <span data-ttu-id="27f66-188">I file visualizzeranno un valore **corrispondente** se la spiegazione creata è sufficiente per soddisfare le etichette come (positive o negative).</span><span class="sxs-lookup"><span data-stu-id="27f66-188">The files will show a value of **Match** if the explanation you created was enough to match what you had labeled them as (positive or negative).</span></span>

    ![Creare una spiegazione](../media/content-understanding/match.png) 

<span data-ttu-id="27f66-190">Se si riceve una **mancata corrispondenza** nei file etichettati, potrebbe essere necessario creare una spiegazione aggiuntiva per fornire al modello ulteriori informazioni per identificare il tipo di documento.</span><span class="sxs-lookup"><span data-stu-id="27f66-190">If you receive a **Mismatch** on your labeled files, you may need to create an additional explanation to provide the model more information to identify the document type.</span></span> <span data-ttu-id="27f66-191">È possibile fare clic sul file per ottenere ulteriori informazioni sul motivo per cui è stata eseguita la mancata corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="27f66-191">You can click on the file to get more information about why the mismatch occurred.</span></span>

## <a name="test-your-model"></a><span data-ttu-id="27f66-192">Testare il modello</span><span class="sxs-lookup"><span data-stu-id="27f66-192">Test your model</span></span>

<span data-ttu-id="27f66-193">Se è stata ricevuta una corrispondenza nei file di esempio contrassegnati, è ora possibile testare il modello nei file di esempio senza etichetta rimanenti.</span><span class="sxs-lookup"><span data-stu-id="27f66-193">If you received a match on your labeled example files, you can now test your model on your remaining unlabeled example files.</span></span>

1. <span data-ttu-id="27f66-194">Nella Home page del modello fare clic sulla scheda **test** .  Verrà eseguito il modello nei file di esempio senza etichetta.</span><span class="sxs-lookup"><span data-stu-id="27f66-194">On the model home page, click the **Test** tab.  This will run the model on your unlabeled example files.</span></span>
2. <span data-ttu-id="27f66-195">Nell'elenco **file di test** , i file di esempio verranno visualizzati e mostreranno se il modello ha previsto che siano esempi positivi o negativi.</span><span class="sxs-lookup"><span data-stu-id="27f66-195">In the **Test files** list, your example files will display and will show if the model predicted them to be positive or negative examples.</span></span> <span data-ttu-id="27f66-196">È possibile utilizzare queste informazioni per determinare l'efficacia del classificatore per identificare i documenti.</span><span class="sxs-lookup"><span data-stu-id="27f66-196">You can use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![Test dei file senza etichetta](../media/content-understanding/test-on-files.png) 



## <a name="see-also"></a><span data-ttu-id="27f66-198">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="27f66-198">See Also</span></span>
[<span data-ttu-id="27f66-199">Creare un estrattore</span><span class="sxs-lookup"><span data-stu-id="27f66-199">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="27f66-200">Panoramica della comprensione del documento</span><span class="sxs-lookup"><span data-stu-id="27f66-200">Document Understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="27f66-201">Creare un modello di elaborazione dei moduli</span><span class="sxs-lookup"><span data-stu-id="27f66-201">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>
[<span data-ttu-id="27f66-202">Applicazione di un modello</span><span class="sxs-lookup"><span data-stu-id="27f66-202">Apply a model</span></span>](apply-a-model.md) 




