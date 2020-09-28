---
title: Creare un classificatore
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
description: Informazioni su come creare un classificatore
ms.openlocfilehash: 29b2a4775bec12649c66b4cb4a07fe5f0fc93ae2
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294903"
---
# <a name="create-a-classifier-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="7366d-103">Creare un classificatore in Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="7366d-103">Create a classifier in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="7366d-104">Il contenuto di questo articolo è relativo all'anteprima privata di Project Cortex.</span><span class="sxs-lookup"><span data-stu-id="7366d-104">The content in this article is for the Project Cortex Private Preview.</span></span> <span data-ttu-id="7366d-105">[Per ulteriori informazioni, vedere Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="7366d-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL0R]  

</br>

<span data-ttu-id="7366d-106">Un classificatore è un tipo di modello che è possibile utilizzare per automatizzare l'identificazione e la classificazione di un tipo di documento.</span><span class="sxs-lookup"><span data-stu-id="7366d-106">A classifier is a type of model that you can use to automate identification and classification of a document type.</span></span> <span data-ttu-id="7366d-107">Ad esempio, è possibile identificare tutti i documenti di *rinnovo del contratto* che vengono aggiunti alla raccolta documenti, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="7366d-107">For example, you may want to identify all *Contract Renewal* documents that are added to your document library, such as is shown in the following illustration.</span></span>

![Documento di rinnovo del contratto](../media/content-understanding/contract-renewal.png)

<span data-ttu-id="7366d-109">La creazione di un classificatore consente di creare un nuovo [tipo di contenuto di SharePoint](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) che verrà associato al modello.</span><span class="sxs-lookup"><span data-stu-id="7366d-109">Creating a classifier enables you to create a new [SharePoint Content Type](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) that will be associated to the model.</span></span>

<span data-ttu-id="7366d-110">Quando si crea il classificatore, è necessario creare *spiegazioni* per definire il modello.</span><span class="sxs-lookup"><span data-stu-id="7366d-110">When creating the classifier, you need to create *explanations* to define the model.</span></span> <span data-ttu-id="7366d-111">In questo modo è possibile notare i dati comuni che si prevede di trovare sempre questo tipo di documento.</span><span class="sxs-lookup"><span data-stu-id="7366d-111">This enables you to note common data that you would expect to consistently find this document type.</span></span> 

<span data-ttu-id="7366d-112">Utilizzare esempi del tipo di documento ("file di esempio") per "formare" il modello per identificare i file con lo stesso tipo di contenuto.</span><span class="sxs-lookup"><span data-stu-id="7366d-112">Use examples of the document type ("example files") to "train" your model to identify files that have the same content type.</span></span>

<span data-ttu-id="7366d-113">Per creare un classificatore, è necessario eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7366d-113">To create a classifier, you need to:</span></span>
1. <span data-ttu-id="7366d-114">Assegnare un nome al modello.</span><span class="sxs-lookup"><span data-stu-id="7366d-114">Name your model.</span></span>
2. <span data-ttu-id="7366d-115">Aggiungere i file di esempio.</span><span class="sxs-lookup"><span data-stu-id="7366d-115">Add your example files.</span></span>
3. <span data-ttu-id="7366d-116">Contrassegnare i file di esempio.</span><span class="sxs-lookup"><span data-stu-id="7366d-116">Label your example files.</span></span>
4. <span data-ttu-id="7366d-117">Creare una spiegazione.</span><span class="sxs-lookup"><span data-stu-id="7366d-117">Create an explanation.</span></span>
5. <span data-ttu-id="7366d-118">Eseguire il test del modello.</span><span class="sxs-lookup"><span data-stu-id="7366d-118">Test your model.</span></span>

> [!NOTE]
> <span data-ttu-id="7366d-119">Mentre il modello utilizza un classificatore per identificare e classificare i tipi di documenti, è anche possibile scegliere di estrarre informazioni specifiche da ogni file identificato dal modello.</span><span class="sxs-lookup"><span data-stu-id="7366d-119">While your model uses a classifier to identify and classify document types, you can also choose to pull specific pieces of information from each file identified by the model.</span></span> <span data-ttu-id="7366d-120">A tale scopo, è possibile creare un **estrattore** da aggiungere al modello.</span><span class="sxs-lookup"><span data-stu-id="7366d-120">Do this by creating an **extractor** to add to your model.</span></span> <span data-ttu-id="7366d-121">Vedere [creare un estrattore](create-an-extractor.md).</span><span class="sxs-lookup"><span data-stu-id="7366d-121">See [Create an extractor](create-an-extractor.md).</span></span>

## <a name="name-your-model"></a><span data-ttu-id="7366d-122">Assegnare un nome al modello</span><span class="sxs-lookup"><span data-stu-id="7366d-122">Name your model</span></span>

<span data-ttu-id="7366d-123">Il primo passaggio per creare il modello consiste nel assegnargli un nome:</span><span class="sxs-lookup"><span data-stu-id="7366d-123">The first step to create your model is to give it a name:</span></span>

1. <span data-ttu-id="7366d-124">Dal centro contenuto, selezionare **nuovo**e quindi **creare un modello**.</span><span class="sxs-lookup"><span data-stu-id="7366d-124">From the Content Center, select **New**, and then **Create a model**.</span></span>
2. <span data-ttu-id="7366d-125">Nel riquadro **nuovo modello di informazioni sul documento** , nel campo **nome** digitare il nome del modello.</span><span class="sxs-lookup"><span data-stu-id="7366d-125">In the **New document understanding model** pane, in the **Name** field type the name of the model.</span></span> <span data-ttu-id="7366d-126">Ad esempio, se si desidera identificare i documenti di rinnovo del contratto, è possibile assegnare un nome al modello di *rinnovo del contratto*.</span><span class="sxs-lookup"><span data-stu-id="7366d-126">For example, if you want to identify contract renewal documents, you could name the model *Contract Renewal*.</span></span>
3. <span data-ttu-id="7366d-127">	Selezionare *\*Crea*\*.</span><span class="sxs-lookup"><span data-stu-id="7366d-127">Choose **Create**.</span></span> <span data-ttu-id="7366d-128">In questo modo viene creata una Home page per il modello.</span><span class="sxs-lookup"><span data-stu-id="7366d-128">This creates a home page for the model.</span></span></br>

    ![Home page del modello di classificazione](../media/content-understanding/model-home.png)

<span data-ttu-id="7366d-130">Quando si crea un modello, si crea anche un nuovo tipo di contenuto di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="7366d-130">When you create a model, you are also creating a new SharePoint content type.</span></span> <span data-ttu-id="7366d-131">Un tipo di contenuto di SharePoint rappresenta una categoria di documenti con caratteristiche comuni e la condivisione di una raccolta di colonne o proprietà dei metadati per il contenuto specifico.</span><span class="sxs-lookup"><span data-stu-id="7366d-131">A SharePoint content type represents a category of documents that have common characteristics and share a collection of columns or metadata properties for that particular content.</span></span> <span data-ttu-id="7366d-132">I tipi di contenuto di SharePoint vengono gestiti tramite la [raccolta tipi di contenuto](https://support.microsoft.com/office/create-or-customize-a-site-content-type-27eb6551-9867-4201-a819-620c5658a60f).</span><span class="sxs-lookup"><span data-stu-id="7366d-132">SharePoint Content Types are managed through the [Content types gallery](https://support.microsoft.com/office/create-or-customize-a-site-content-type-27eb6551-9867-4201-a819-620c5658a60f).</span></span> <span data-ttu-id="7366d-133">In questo esempio, quando si crea il modello, si crea un nuovo tipo di contenuto per il *rinnovo del contratto* .</span><span class="sxs-lookup"><span data-stu-id="7366d-133">For this example, when you create the model, you are creating a new *Contract Renewal* content type.</span></span>

<span data-ttu-id="7366d-134">Selezionare **Impostazioni avanzate** se si desidera eseguire il mapping di questo modello a un tipo di contenuto esistente nella raccolta tipi di contenuto di SharePoint per utilizzarne lo schema.</span><span class="sxs-lookup"><span data-stu-id="7366d-134">Select **Advanced settings** if you want to map this model to an existing content type in the SharePoint Content types gallery to use its schema.</span></span> <span data-ttu-id="7366d-135">Si noti che, sebbene sia possibile utilizzare un tipo di contenuto esistente per sfruttare il relativo schema per facilitare l'identificazione e la classificazione, è comunque necessario addestrare il modello per estrarre informazioni dai file identificati.</span><span class="sxs-lookup"><span data-stu-id="7366d-135">Note that while you can use an existing content type to leverage its schema to help with identification and classification, you still need to train your model to extract information from files it identifies.</span></span></br>

![Impostazioni avanzate](../media/content-understanding/advanced-settings.png)

## <a name="add-your-example-files"></a><span data-ttu-id="7366d-137">Aggiungere i file di esempio</span><span class="sxs-lookup"><span data-stu-id="7366d-137">Add your example files</span></span>

<span data-ttu-id="7366d-138">Nella Home page del modello aggiungere i file degli esempi necessari per la formazione del modello per identificare il tipo di documento.</span><span class="sxs-lookup"><span data-stu-id="7366d-138">On the model home page, add your examples files you will need to help train the model to identify your document type.</span></span> </br>
</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4D0iX] 

</br>

> [!NOTE]
> <span data-ttu-id="7366d-139">È consigliabile utilizzare gli stessi file per la formazione del classificatore e dell' [estrattore](create-an-extractor.md).</span><span class="sxs-lookup"><span data-stu-id="7366d-139">You should use the same files for both classifier and [extractor training](create-an-extractor.md).</span></span> <span data-ttu-id="7366d-140">Si ha sempre la possibilità di aggiungere altre versioni successive, ma in genere si aggiunge una serie completa di file di esempio.</span><span class="sxs-lookup"><span data-stu-id="7366d-140">You always have the option to add more later, but typically you add a full set of sample files.</span></span> <span data-ttu-id="7366d-141">Etichetta alcuni per formare il modello e testare quelli restanti senza etichetta per valutare la forma fisica del modello.</span><span class="sxs-lookup"><span data-stu-id="7366d-141">Label some to train your model, and test the remaining unlabeled ones to evaluate model fitness.</span></span> 

<span data-ttu-id="7366d-142">Per il set di training, si desidera utilizzare esempi positivi e negativi:</span><span class="sxs-lookup"><span data-stu-id="7366d-142">For your training set, you want to use both positive and negative examples:</span></span>
- <span data-ttu-id="7366d-143">Esempio positivo: documenti che rappresentano il tipo di documento.</span><span class="sxs-lookup"><span data-stu-id="7366d-143">Positive example: Documents that represent the document type.</span></span> <span data-ttu-id="7366d-144">Contengono stringhe e informazioni che sarebbero sempre presenti in questo tipo di documento.</span><span class="sxs-lookup"><span data-stu-id="7366d-144">These contain strings and information that would always be in this type of document.</span></span>
- <span data-ttu-id="7366d-145">Esempio negativo: documenti che non rappresentano il tipo di documento.</span><span class="sxs-lookup"><span data-stu-id="7366d-145">Negative example: Documents that do not represent the document type.</span></span> <span data-ttu-id="7366d-146">Si tratta di stringhe mancanti e di informazioni che devono essere presenti in questo tipo di documento.</span><span class="sxs-lookup"><span data-stu-id="7366d-146">These are missing strings and information that needs to be present in this type of document.</span></span>

<span data-ttu-id="7366d-147">Assicurarsi di utilizzare almeno cinque esempi positivi e almeno un esempio negativo per la formazione del modello.</span><span class="sxs-lookup"><span data-stu-id="7366d-147">Be sure to use at least five positive examples and at least one negative example to train your model.</span></span>  <span data-ttu-id="7366d-148">Si desidera crearne di nuovi per testare il modello dopo il processo di formazione.</span><span class="sxs-lookup"><span data-stu-id="7366d-148">You want to create additional ones to test your model after the training process.</span></span>

<span data-ttu-id="7366d-149">Per aggiungere file di esempio:</span><span class="sxs-lookup"><span data-stu-id="7366d-149">To add sample files:</span></span>

1. <span data-ttu-id="7366d-150">Dalla Home page del modello fare clic su **Aggiungi file**nel riquadro della **raccolta di esempi di compilazione** .</span><span class="sxs-lookup"><span data-stu-id="7366d-150">From the model home page, in the **Build sample library** tile, click **Add files**.</span></span>
2. <span data-ttu-id="7366d-151">Nella pagina **selezionare** i file di esempio della pagina del modello selezionare i file degli esempi dalla libreria file di esempio nel centro contenuto.</span><span class="sxs-lookup"><span data-stu-id="7366d-151">On the **Select sample files for your model** page, select your example files from the Sample files library in the Content Center.</span></span> <span data-ttu-id="7366d-152">Se non li hai già caricati, scegli di caricarli subito facendo clic su **carica** per spostarli nella raccolta file di esempio.</span><span class="sxs-lookup"><span data-stu-id="7366d-152">If you had not already uploaded them there, choose to upload them now by clicking **Upload** to move them the Sample file library.</span></span>
3. <span data-ttu-id="7366d-153">Dopo aver selezionato i file di esempio da utilizzare per la formazione del modello, fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="7366d-153">After selecting your example files to use to train the model, click **Add**.</span></span>

    ![Selezionare i file di esempio](../media/content-understanding/select-sample.png) 

## <a name="label-your-example-files"></a><span data-ttu-id="7366d-155">Contrassegnare i file di esempio</span><span class="sxs-lookup"><span data-stu-id="7366d-155">Label your example files</span></span>

<span data-ttu-id="7366d-156">Dopo aver aggiunto i file di esempio, è necessario etichettarli come esempi positivi o negativi.</span><span class="sxs-lookup"><span data-stu-id="7366d-156">After adding your example files, you need to label them as either positive or negative examples.</span></span>

1. <span data-ttu-id="7366d-157">Nella Home page del modello fare clic su **classificazione**dei **file e quindi eseguire il training** Tile.</span><span class="sxs-lookup"><span data-stu-id="7366d-157">From the model home page, on the **Classify files and run training** tile, click **Train Classifier**.</span></span>
   <span data-ttu-id="7366d-158">Viene visualizzata la pagina etichetta che mostra un elenco dei file di esempio, con il primo file visibile nel visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="7366d-158">This displays the label page that shows a listing of your example files, with the first file visible in the viewer.</span></span>
2. <span data-ttu-id="7366d-159">Nel Visualizzatore nella parte superiore del primo file di esempio, dovrebbe essere visualizzato il testo che chiede se il file è un esempio del modello appena creato.</span><span class="sxs-lookup"><span data-stu-id="7366d-159">In the viewer on the top of the first example file, you should see text asking if the file is an example of the model you just created.</span></span> <span data-ttu-id="7366d-160">Se si tratta di un esempio positivo, selezionare **Sì**.</span><span class="sxs-lookup"><span data-stu-id="7366d-160">If it is a positive example, select **Yes**.</span></span> <span data-ttu-id="7366d-161">Se si tratta di un esempio negativo, selezionare **No**.</span><span class="sxs-lookup"><span data-stu-id="7366d-161">If it is a negative example, select **No**.</span></span>
3. <span data-ttu-id="7366d-162">Nell'elenco degli **esempi etichettati** a sinistra, selezionare altri file che si desidera utilizzare come esempi ed etichettarli.</span><span class="sxs-lookup"><span data-stu-id="7366d-162">From the **Labeled examples** list on the left, select additional files that you want to use as examples, and label them.</span></span> 

    ![Home page di classificazione](../media/content-understanding/classifier-home-page.png) 


> [!NOTE]
> <span data-ttu-id="7366d-164">Etichettare almeno cinque esempi positivi e un esempio negativo.</span><span class="sxs-lookup"><span data-stu-id="7366d-164">Label at least five positive examples, and one negative example.</span></span> 

## <a name="create-an-explanation"></a><span data-ttu-id="7366d-165">Creare una spiegazione</span><span class="sxs-lookup"><span data-stu-id="7366d-165">Create an explanation</span></span>

<span data-ttu-id="7366d-166">Il passaggio successivo consiste nel creare una spiegazione sulla pagina del treno.</span><span class="sxs-lookup"><span data-stu-id="7366d-166">The next step is for you to create an explanation on the Train page.</span></span> <span data-ttu-id="7366d-167">Una spiegazione aiuta il modello a comprendere come riconoscere il documento.</span><span class="sxs-lookup"><span data-stu-id="7366d-167">An explanation helps the model understand how to recognize the document.</span></span> <span data-ttu-id="7366d-168">Ad esempio, i documenti di rinnovo del contratto contengono sempre una *richiesta per una stringa di testo di divulgazione aggiuntiva* .</span><span class="sxs-lookup"><span data-stu-id="7366d-168">For example, the Contract Renewal documents always contain a *Request for additional disclosure* text string.</span></span>

> [!Note]
> <span data-ttu-id="7366d-169">Se utilizzata con gli estrattori, una spiegazione identifica la stringa che si desidera estrarre dal documento.</span><span class="sxs-lookup"><span data-stu-id="7366d-169">When used with extractors, an explanation identifies the string that you want to extract from the document.</span></span> 

<span data-ttu-id="7366d-170">Per creare una spiegazione:</span><span class="sxs-lookup"><span data-stu-id="7366d-170">To create an explanation:</span></span>

1. <span data-ttu-id="7366d-171">Nella Home page del modello selezionare la scheda **treno** per andare alla pagina del treno.</span><span class="sxs-lookup"><span data-stu-id="7366d-171">From the model home page, select the **Train** tab to go to the Train page.</span></span>
2. <span data-ttu-id="7366d-172">Nella sezione **file addestrati** della pagina del treno dovrebbe essere visualizzato un elenco dei file di esempio che sono stati precedentemente etichettati.</span><span class="sxs-lookup"><span data-stu-id="7366d-172">On the Train page, in the **Trained files** section you should see a list of the sample files that you previously labeled.</span></span> <span data-ttu-id="7366d-173">Selezionare uno dei file positivi nell'elenco e visualizzarlo nel visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="7366d-173">Select one of the positive files from the list, and it displays in the viewer.</span></span>
3. <span data-ttu-id="7366d-174">Nella sezione spiegazione selezionare **nuovo** e quindi **vuoto**.</span><span class="sxs-lookup"><span data-stu-id="7366d-174">In the Explanation section, select **New** and then **Blank**.</span></span>
4. <span data-ttu-id="7366d-175">Nella pagina **Crea una spiegazione** :</span><span class="sxs-lookup"><span data-stu-id="7366d-175">On the **Create an explanation** page:</span></span></br>
    <span data-ttu-id="7366d-176">a.</span><span class="sxs-lookup"><span data-stu-id="7366d-176">a.</span></span> <span data-ttu-id="7366d-177">Digitare il **nome** (ad esempio, "blocco di disclosure").</span><span class="sxs-lookup"><span data-stu-id="7366d-177">Type the **Name** (for example, "Disclosure Block").</span></span></br>
    <span data-ttu-id="7366d-178">b.</span><span class="sxs-lookup"><span data-stu-id="7366d-178">b.</span></span> <span data-ttu-id="7366d-179">Selezionare il **tipo**.</span><span class="sxs-lookup"><span data-stu-id="7366d-179">Select the **Type**.</span></span> <span data-ttu-id="7366d-180">Per l'esempio, selezionare l' **elenco delle frasi**, poiché si aggiunge una stringa di testo.</span><span class="sxs-lookup"><span data-stu-id="7366d-180">For the sample, select **Phrase list**, since you add a text string.</span></span></br>
    <span data-ttu-id="7366d-181">c.</span><span class="sxs-lookup"><span data-stu-id="7366d-181">c.</span></span> <span data-ttu-id="7366d-182">Nella casella **digitare qui** Digitare la stringa.</span><span class="sxs-lookup"><span data-stu-id="7366d-182">In the **Type here** box, type the string.</span></span> <span data-ttu-id="7366d-183">Per l'esempio, aggiungere "richiesta di ulteriore divulgazione".</span><span class="sxs-lookup"><span data-stu-id="7366d-183">For the sample, add "Request for additional disclosure".</span></span> <span data-ttu-id="7366d-184">È **possibile selezionare maiuscole/minuscole** se la stringa deve essere distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="7366d-184">You can select **Case sensitive** if the string needs to be case sensitive.</span></span></br>
    <span data-ttu-id="7366d-185">d.</span><span class="sxs-lookup"><span data-stu-id="7366d-185">d.</span></span> <span data-ttu-id="7366d-186">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="7366d-186">Click **Save**.</span></span>

    ![Creare una spiegazione](../media/content-understanding/explanation.png) 
    
 
5. <span data-ttu-id="7366d-188">Il modello ora controlla se la spiegazione creata è stata sufficiente per identificare correttamente i file di esempio con etichetta rimanenti, come esempi positivi e negativi.</span><span class="sxs-lookup"><span data-stu-id="7366d-188">The model now checks to see if the explanation you created was good enough to identify the remaining labeled example files correctly, as positive and negative examples.</span></span> <span data-ttu-id="7366d-189">Nella sezione file addestrati controllare la colonna **valutazione** dopo aver completato il training per visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="7366d-189">In the Trained Files section, check the **Evaluation** column after the training has completed to see the results.</span></span> <span data-ttu-id="7366d-190">I file mostrano un valore di **corrispondenza**, se le spiegazioni create sono sufficienti per corrispondere a quelle contrassegnate come positive o negative.</span><span class="sxs-lookup"><span data-stu-id="7366d-190">The files show a value of **Match**, if the explanations you created was enough to match what you labeled as positive or negative.</span></span>

    ![Valore di corrispondenza](../media/content-understanding/match.png) 

<span data-ttu-id="7366d-192">Se si riceve una **mancata corrispondenza** nei file contrassegnati, potrebbe essere necessario creare una spiegazione aggiuntiva per fornire al modello ulteriori informazioni per identificare il tipo di documento.</span><span class="sxs-lookup"><span data-stu-id="7366d-192">If you receive a **Mismatch** on the labeled files, you may need to create an additional explanation to provide the model more information to identify the document type.</span></span> <span data-ttu-id="7366d-193">In questo caso, fare clic sul file per ottenere ulteriori informazioni sul motivo per cui la mancata corrispondenza si è verificata.</span><span class="sxs-lookup"><span data-stu-id="7366d-193">If this happens, click on the file to get more information about why the mismatch occurred.</span></span>

## <a name="test-your-model"></a><span data-ttu-id="7366d-194">Testare il modello</span><span class="sxs-lookup"><span data-stu-id="7366d-194">Test your model</span></span>

<span data-ttu-id="7366d-195">Se è stata ricevuta una corrispondenza nei file di esempio etichettati, è ora possibile testare il modello nei file di esempio senza etichetta rimanenti.</span><span class="sxs-lookup"><span data-stu-id="7366d-195">If you received a match on your labeled sample files, you can now test your model on your remaining unlabeled example files.</span></span>

1. <span data-ttu-id="7366d-196">Nella Home page del modello selezionare la scheda **test** .  Questo esegue il modello nei file di esempio senza etichetta.</span><span class="sxs-lookup"><span data-stu-id="7366d-196">From the model home page, select the **Test** tab.  This runs the model on your unlabeled sample files.</span></span>
2. <span data-ttu-id="7366d-197">Nell'elenco **file di test** , i file di esempio vengono visualizzati e mostrati se il modello ha previsto che siano positivi o negativi.</span><span class="sxs-lookup"><span data-stu-id="7366d-197">In the **Test files** list, your example files display and shows if the model predicted them to be positive or negative.</span></span> <span data-ttu-id="7366d-198">Utilizzare queste informazioni per determinare l'efficacia del classificatore per identificare i documenti.</span><span class="sxs-lookup"><span data-stu-id="7366d-198">Use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![Test dei file senza etichetta](../media/content-understanding/test-on-files.png) 

## <a name="see-also"></a><span data-ttu-id="7366d-200">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7366d-200">See Also</span></span>
[<span data-ttu-id="7366d-201">Creare un estrattore</span><span class="sxs-lookup"><span data-stu-id="7366d-201">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="7366d-202">Panoramica della comprensione del documento</span><span class="sxs-lookup"><span data-stu-id="7366d-202">Document Understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="7366d-203">Creare un modello di elaborazione dei moduli</span><span class="sxs-lookup"><span data-stu-id="7366d-203">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>
[<span data-ttu-id="7366d-204">Applicazione di un modello</span><span class="sxs-lookup"><span data-stu-id="7366d-204">Apply a model</span></span>](apply-a-model.md) 
