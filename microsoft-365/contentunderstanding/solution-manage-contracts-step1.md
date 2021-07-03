---
title: Passaggio 1. Usare SharePoint Syntex per identificare i file di contratto ed estrarre i dati
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.date: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: ''
description: Informazioni su come usare SharePoint Syntex per identificare i file di contratto ed estrarre i dati utilizzando una Microsoft 365 soluzione.
ms.openlocfilehash: b73f7b96a1f1a9159770fb1bfb20bf2718f08c07
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287354"
---
# <a name="step-1-use-sharepoint-syntex-to-identify-contract-files-and-extract-data"></a><span data-ttu-id="ee4a5-104">Passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-104">Step 1.</span></span> <span data-ttu-id="ee4a5-105">Usare SharePoint Syntex per identificare i file di contratto ed estrarre i dati</span><span class="sxs-lookup"><span data-stu-id="ee4a5-105">Use SharePoint Syntex to identify contract files and extract data</span></span>

<span data-ttu-id="ee4a5-106">L'organizzazione ha bisogno di un modo per identificare e classificare tutti i documenti di contratto dai numerosi file ricevuti.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-106">Your organization needs a way to identify and classify all contract documents from the many files you receive.</span></span> <span data-ttu-id="ee4a5-107">È inoltre possibile visualizzare rapidamente diversi elementi chiave in ognuno dei file di contratto identificati (ad esempio, *Cliente,* Appaltatore e *Importo commissione).*</span><span class="sxs-lookup"><span data-stu-id="ee4a5-107">You also want to be able to quickly view several key elements in each of the contract files identified (for example, *Client*, *Contractor*, and *Fee amount*).</span></span> <span data-ttu-id="ee4a5-108">A tale scopo, è [possibile SharePoint Syntex](index.md) per creare un modello di comprensione dei documenti e applicarlo a una raccolta documenti.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-108">You can do this by using [SharePoint Syntex](index.md) to create a document understanding model and applying it to a document library.</span></span>

## <a name="overview-of-the-process"></a><span data-ttu-id="ee4a5-109">Panoramica del processo</span><span class="sxs-lookup"><span data-stu-id="ee4a5-109">Overview of the process</span></span>

<span data-ttu-id="ee4a5-110">[La comprensione dei](document-understanding-overview.md) documenti usa modelli di intelligenza artificiale (AI) per automatizzare la classificazione dei file e l'estrazione delle informazioni.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-110">[Document understanding](document-understanding-overview.md) uses artificial intelligence (AI) models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="ee4a5-111">I modelli di comprensione dei documenti sono inoltre ottimali nell'estrazione di informazioni da documenti non strutturati e semistrutturati in cui le informazioni necessarie non sono contenute in tabelle o moduli, ad esempio contratti.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-111">Document understanding models are also optimal in extracting information from unstructured and semi-structured documents where the information you need isn't contained in tables or forms, such as contracts.</span></span> 

<span data-ttu-id="ee4a5-112">I modelli di analisi dei documenti usano la tecnologia di riconoscimento ottico dei caratteri (OCR) per analizzare file PDF, immagini e file TIFF, sia quando si esegue il training di un modello con file di esempio, sia quando si esegue il modello sui file di una raccolta documenti.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-112">Document understanding models use Optical Character Recognition (OCR) technology to scan PDFs, images, and TIFF files, both when you train a model with example files and when you run the model against files in a document library.</span></span>

1. <span data-ttu-id="ee4a5-113">Innanzitutto, è necessario trovare almeno cinque file di esempio che è possibile utilizzare per "formare" il modello per cercare caratteristiche specifiche del tipo di contenuto che si sta tentando di identificare (un contratto).</span><span class="sxs-lookup"><span data-stu-id="ee4a5-113">First, you need to find at least five example files that you can use to "train" the model to search for characteristics that are specific to the content type you're trying to identify (a contract).</span></span> 

2. <span data-ttu-id="ee4a5-114">Usando SharePoint Syntex, crea un nuovo modello di comprensione dei documenti.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-114">Using SharePoint Syntex, create a new document understanding model.</span></span> <span data-ttu-id="ee4a5-115">Usando i file di esempio, è necessario [creare un classificatore](create-a-classifier.md).</span><span class="sxs-lookup"><span data-stu-id="ee4a5-115">Using your example files, you need to [create a classifier](create-a-classifier.md).</span></span> <span data-ttu-id="ee4a5-116">Formando il classificatore con i file di esempio, viene insegnato a cercare caratteristiche specifiche di ciò che si potrebbe vedere nei contratti dell'azienda.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-116">By training the classifier with your example files, you teach it to search for characteristics that are specific to what you would see in your company's contracts.</span></span> <span data-ttu-id="ee4a5-117">Ad esempio, [creare una "spiegazione"](create-a-classifier.md#create-an-explanation) che cerca stringhe specifiche presenti nei contratti, ad esempio Contratto di *servizio,* *Condizioni* del contratto e *Compensazione.*</span><span class="sxs-lookup"><span data-stu-id="ee4a5-117">For example, [create an "explanation"](create-a-classifier.md#create-an-explanation) that searches for specific strings that are in your contracts, such as *Service Agreement*, *Terms of Agreement*, and *Compensation*.</span></span> <span data-ttu-id="ee4a5-118">Puoi anche formare la tua spiegazione per cercare queste stringhe in sezioni specifiche del documento o posizionate accanto ad altre stringhe.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-118">You can even train your explanation to look for these strings in specific sections of the document, or located next to other strings.</span></span> <span data-ttu-id="ee4a5-119">Quando si pensa di aver addestrato il classificatore con le informazioni necessarie, è possibile testare il modello su un set di file di esempio di esempio per verificare l'efficienza.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-119">When you think you have trained your classifier with the information it needs, you can test your model on a sample set of example files to see how efficient it is.</span></span> <span data-ttu-id="ee4a5-120">Dopo il test, se necessario, è possibile scegliere di apportare modifiche alle spiegazioni per renderle più efficienti.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-120">After testing, if needed you can choose to make changes to your explanations to make them more efficient.</span></span> 

3. <span data-ttu-id="ee4a5-121">Nel modello puoi creare un [estrattore](create-an-extractor.md) per estrarre parti specifiche di dati da ogni contratto.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-121">In your model, you can [create an extractor](create-an-extractor.md) to pull out specific pieces of data from each contract.</span></span> <span data-ttu-id="ee4a5-122">Ad esempio, per ogni contratto, le informazioni più preoccupate sono chi è il cliente, il nome dell'appaltatore e il costo totale.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-122">For example, for each contract, the information you're most concerned about is who the client is, the name of the contractor, and the total cost.</span></span>

4. <span data-ttu-id="ee4a5-123">Dopo aver creato correttamente il modello, applicarlo a una [raccolta SharePoint documenti.](apply-a-model.md)</span><span class="sxs-lookup"><span data-stu-id="ee4a5-123">After you successfully create your model, [apply it to a SharePoint document library](apply-a-model.md).</span></span> <span data-ttu-id="ee4a5-124">Quando si caricano documenti nella raccolta documenti, verrà eseguito il modello di comprensione dei documenti e verranno identificati e classificati tutti i file che corrispondono al tipo di contenuto dei contratti definito nel modello.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-124">As you upload documents to the document library, your document understanding model will run and will identify and classify all files that match the contracts content type you defined in your model.</span></span> <span data-ttu-id="ee4a5-125">Tutti i file classificati come contratti verranno visualizzati in una visualizzazione raccolta personalizzata.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-125">All files that are classified as contracts will display in a custom library view.</span></span> <span data-ttu-id="ee4a5-126">I file visualizzano anche i valori di ogni contratto definito nell'estrattore.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-126">The files will also display the values from each contract that you defined in your extractor.</span></span>

   ![Contratti nella raccolta documenti](../media/content-understanding/doc-lib-solution.png)

5. <span data-ttu-id="ee4a5-128">Se hai requisiti di conservazione o sicurezza per i tuoi contratti, puoi [](apply-a-sensitivity-label-to-a-model.md) anche usare il modello per applicare un'etichetta di conservazione o un'etichetta di riservatezza che impedirà l'eliminazione dei contratti per un periodo di tempo specificato o per limitare chi può accedere ai contratti. [](apply-a-retention-label-to-a-model.md)</span><span class="sxs-lookup"><span data-stu-id="ee4a5-128">If you have retention or security requirements for your contracts, you can also use your model to apply a [retention label](apply-a-retention-label-to-a-model.md) or a [sensitivity label](apply-a-sensitivity-label-to-a-model.md) that will prevent your contracts from being deleted for a specified period of time or to restrict who can access the contracts.</span></span>

## <a name="steps-to-create-and-train-your-model"></a><span data-ttu-id="ee4a5-129">Passaggi per creare ed eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="ee4a5-129">Steps to create and train your model</span></span>

> [!NOTE]
> <span data-ttu-id="ee4a5-130">Per questi passaggi, è possibile utilizzare i file di esempio [nell'archivio Contracts Management Solution Assets.](https://github.com/pnp/syntex-samples/tree/main/scenario%20assets/Contracts%20Management)</span><span class="sxs-lookup"><span data-stu-id="ee4a5-130">For these steps, you can use the example files in the [Contracts Management Solution Assets repository](https://github.com/pnp/syntex-samples/tree/main/scenario%20assets/Contracts%20Management).</span></span> <span data-ttu-id="ee4a5-131">Gli esempi in questo repository contengono sia i file del modello di comprensione dei documenti che i file utilizzati per eseguire il training del modello.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-131">The examples in this repository contain both the document understanding model files and the files used to train the model.</span></span>

### <a name="create-a-contract-model"></a><span data-ttu-id="ee4a5-132">Creare un modello di contratto</span><span class="sxs-lookup"><span data-stu-id="ee4a5-132">Create a Contract model</span></span>

<span data-ttu-id="ee4a5-133">Il primo passaggio consiste nel creare il modello di contratto.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-133">The first step is to create your Contract model.</span></span>

1. <span data-ttu-id="ee4a5-134">Nel centro contenuti selezionare **Nuovo** e quindi **Crea un modello**.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-134">From the content center, select **New**, and then **Create a model**.</span></span>

2. <span data-ttu-id="ee4a5-135">Nel riquadro **Nuovo modello** di comprensione documento digitare **il** nome del modello nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-135">On the **New document understanding model** pane, in the **Name** field, type the name of the model.</span></span> <span data-ttu-id="ee4a5-136">Per questa soluzione di gestione dei contratti, è possibile assegnare al modello il nome *Contract*.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-136">For this contract management solution, you can name the model *Contract*.</span></span>

4. <span data-ttu-id="ee4a5-137">Scegliere **Crea**.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-137">Choose **Create**.</span></span> <span data-ttu-id="ee4a5-138">Verrà creata una home page per il modello.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-138">This creates a home page for the model.</span></span></br>

    ![Screenshot della home page contratto.](../media/content-understanding/models-contract-home-page.png)


### <a name="train-your-model-to-classify-a-type-of-file"></a><span data-ttu-id="ee4a5-140">Eseguire il training del modello per classificare un tipo di file</span><span class="sxs-lookup"><span data-stu-id="ee4a5-140">Train your model to classify a type of file</span></span>

#### <a name="add-example-files-for-your-model"></a><span data-ttu-id="ee4a5-141">Aggiungere file di esempio per il modello</span><span class="sxs-lookup"><span data-stu-id="ee4a5-141">Add example files for your model</span></span>

<span data-ttu-id="ee4a5-142">È necessario aggiungere almeno cinque file di esempio che sono documenti di contratto e un file di esempio che non è un documento di contratto (ad esempio, una dichiarazione di lavoro).</span><span class="sxs-lookup"><span data-stu-id="ee4a5-142">You need to add at least five example files that are contract documents, and one example file that's not a contract document (for example, a statement of work).</span></span> 

1. <span data-ttu-id="ee4a5-143">Nella pagina **Modelli > Contratto,** in Azioni **chiave** Aggiungi file  >  **di esempio,** selezionare **Aggiungi file**.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-143">On the **Models > Contract** page, under **Key actions** > **Add example files**, select **Add files**.</span></span>

   ![Screenshot che mostra la pagina Contratti con l'opzione Aggiungi file di esempio evidenziata.](../media/content-understanding/key-actions-add-example-files.png)

2. <span data-ttu-id="ee4a5-145">Nella pagina **Seleziona file di esempio per il modello** aprire la cartella Contratto, selezionare i file che si desidera utilizzare e quindi selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-145">On the **Select example files for your model** page, open the Contract folder, select files you want to use, and then select **Add**.</span></span> <span data-ttu-id="ee4a5-146">Se non si dispone di file di esempio, **selezionare Upload** per aggiungerli.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-146">If you don't have example files there, select **Upload** to add them.</span></span>

#### <a name="label-the-files-as-positive-or-negative-examples"></a><span data-ttu-id="ee4a5-147">Etichettare i file come esempi positivi o negativi</span><span class="sxs-lookup"><span data-stu-id="ee4a5-147">Label the files as positive or negative examples</span></span>

1. <span data-ttu-id="ee4a5-148">Nella pagina **Modelli > contratto,** in Azioni **chiave** Classificare i file ed eseguire  >  **la formazione,** selezionare **Classificatore di training.**</span><span class="sxs-lookup"><span data-stu-id="ee4a5-148">On the **Models > Contract** page, under **Key actions** > **Classify files and run training**, select **Train classifier**.</span></span>

   ![Screenshot showing the Contracts page with Classify files and run training option highlighted.](../media/content-understanding/key-actions-classify-files.png)

2. <span data-ttu-id="ee4a5-150">Nella pagina Model **> Contract > Contract classifier,** nel visualizzatore nella parte superiore del primo file di esempio verrà visualizzato un testo che richiede se il file è un esempio del modello di contratto creato.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-150">On the **Models > Contract > Contract classifier** page, in the viewer on the top of the first example file, you'll see text asking if the file is an example of the Contract model you created.</span></span> <span data-ttu-id="ee4a5-151">Se è un esempio positivo, selezionare **Sì**.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-151">If it is a positive example, select **Yes**.</span></span> <span data-ttu-id="ee4a5-152">Se è un esempio negativo, selezionare **No**.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-152">If it is a negative example, select **No**.</span></span>

3. <span data-ttu-id="ee4a5-153">**Nell'elenco Esempi con** etichetta a sinistra seleziona gli altri file che vuoi usare come esempi ed etichettali.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-153">From the **Labeled examples** list on the left, select other files that you want to use as examples, and label them.</span></span> 

    ![Home page del classificatore](../media/content-understanding/models-contract-classifier.png) 

#### <a name="add-at-least-one-explanation-to-train-the-classifier&quot;></a><span data-ttu-id=&quot;ee4a5-155&quot;>Aggiungere almeno una spiegazione per il training del classificatore</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;ee4a5-155&quot;>Add at least one explanation to train the classifier</span></span> 

1. <span data-ttu-id=&quot;ee4a5-156&quot;>Nella pagina **Model > Contract > Contract classifier** selezionare la scheda **Train.**</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;ee4a5-156&quot;>On the **Models > Contract > Contract classifier** page, select the **Train** tab.</span></span>

2. <span data-ttu-id=&quot;ee4a5-157&quot;>Nella sezione **File con training** verrà visualizzato un elenco dei file di esempio etichettati in precedenza.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;ee4a5-157&quot;>In the **Trained files** section, you'll see a list of the example files that you previously labeled.</span></span> <span data-ttu-id=&quot;ee4a5-158&quot;>Seleziona uno dei file positivi dall'elenco per visualizzarlo nel visualizzatore.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;ee4a5-158&quot;>Select one of the positive files from the list to display it in the viewer.</span></span>

3. <span data-ttu-id=&quot;ee4a5-159&quot;>Nella sezione **Spiegazioni** selezionare **Nuovo** e quindi **Vuoto.**</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;ee4a5-159&quot;>In the **Explanations** section, select **New** and then **Blank**.</span></span>

4. <span data-ttu-id=&quot;ee4a5-160&quot;>Nella pagina **Crea spiegazione**:</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;ee4a5-160&quot;>On the **Create an explanation** page:</span></span>

    <span data-ttu-id=&quot;ee4a5-161&quot;>a.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;ee4a5-161&quot;>a.</span></span> <span data-ttu-id=&quot;ee4a5-162&quot;>Nel campo **Nome** digitare il nome della spiegazione, ad esempio &quot;Contratto&quot;.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;ee4a5-162&quot;>In the **Name** field, type the name of the explanation (such as &quot;Agreement").</span></span>

    <span data-ttu-id="ee4a5-163">b.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-163">b.</span></span> <span data-ttu-id="ee4a5-164">Nel campo **Tipo di spiegazione** selezionare Elenco **frasi** perché si aggiunge una stringa di testo.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-164">In the **Explanation type** field, select **Phrase list**, because you add a text string.</span></span>

    <span data-ttu-id="ee4a5-165">c.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-165">c.</span></span> <span data-ttu-id="ee4a5-166">Nella casella **di riepilogo** Frase digitare la stringa, ad esempio "CONTRATTO".</span><span class="sxs-lookup"><span data-stu-id="ee4a5-166">In the **Phrase list** box, type the string (such as "AGREEMENT").</span></span> <span data-ttu-id="ee4a5-167">È possibile selezionare **Maiuscole/minuscole** se la stringa deve fare distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-167">You can select **Case sensitive** if the string needs to be case-sensitive.</span></span>

    <span data-ttu-id="ee4a5-168">d.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-168">d.</span></span> <span data-ttu-id="ee4a5-169">Selezionare **Salva e allena**.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-169">Select **Save and train**.</span></span>

    ![Screenshot of the Create an explanation panel.](../media/content-understanding/contract-classifier-create-explanation.png) 

#### <a name="test-your-model"></a><span data-ttu-id="ee4a5-171">Testare il modello</span><span class="sxs-lookup"><span data-stu-id="ee4a5-171">Test your model</span></span>

<span data-ttu-id="ee4a5-172">Puoi testare il modello di contratto su file di esempio che non sono stati mai visti prima.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-172">You can test your Contract model on example files it hasn’t seen before.</span></span> <span data-ttu-id="ee4a5-173">Questo è facoltativo, ma può essere una procedura consigliata utile.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-173">This is optional, but it can be a useful best practice.</span></span>

1. <span data-ttu-id="ee4a5-174">Nella pagina **Model > Contract > Contract classifier** selezionare la scheda **Test.** Il modello viene eseguito nei file di esempio senza etichetta.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-174">On the **Models > Contract > Contract classifier** page, select the **Test** tab. This runs the model on your unlabeled example files.</span></span>

2. <span data-ttu-id="ee4a5-175">**Nell'elenco Test Files** vengono visualizzati i file di esempio e viene indicato se il modello li ha previsti come positivi o negativi.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-175">In the **Test Files** list, your example files display and shows if the model predicted them to be positive or negative.</span></span> <span data-ttu-id="ee4a5-176">Usare queste informazioni per determinare l'efficacia del classificatore nell'identificazione dei documenti.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-176">Use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![Screenshot dei file senza etichetta nell'elenco File di testo](../media/content-understanding/test-on-files.png) 

3. <span data-ttu-id="ee4a5-178">Al termine, selezionare **Esci da training**.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-178">When done, select **Exit Training**.</span></span>

### <a name="create-and-train-an-extractor"></a><span data-ttu-id="ee4a5-179">Creare e formare un estrattore</span><span class="sxs-lookup"><span data-stu-id="ee4a5-179">Create and train an extractor</span></span>

1. <span data-ttu-id="ee4a5-180">Nella pagina **Modelli > contratto,** in **Azioni chiave** Creare e formare  >  **estrattori,** selezionare Crea **estrattore.**</span><span class="sxs-lookup"><span data-stu-id="ee4a5-180">On the **Models > Contract** page, under **Key actions** > **Create and train extractors**, select **Create extractor**.</span></span>

   ![Screenshot che mostra la pagina Contratti con l'opzione Crea e addestra estrattori evidenziata.](../media/content-understanding/key-actions-create-extractors.png)

2. <span data-ttu-id="ee4a5-182">Nel **campo Nuovo** nome del  pannello Nuovo estrattore di entità digitare il nome dell'estrattore.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-182">On the **New entity extractor** panel, in the **New name** field, type the name of your extractor.</span></span> <span data-ttu-id="ee4a5-183">Ad esempio, assegnare il *nome Client* se si desidera estrarre il nome del client da ogni contratto.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-183">For example, name it *Client* if you want to extract the name of the client from each contract.</span></span>

3. <span data-ttu-id="ee4a5-184">Al termine, selezionare **Crea**.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-184">When you're done, select **Create**.</span></span>

#### <a name="label-the-entity-you-want-to-extract"></a><span data-ttu-id="ee4a5-185">Etichettare l'entità che si desidera estrarre</span><span class="sxs-lookup"><span data-stu-id="ee4a5-185">Label the entity you want to extract</span></span>

<span data-ttu-id="ee4a5-186">Quando si crea l'estrattore, viene aperta la pagina dell'estrattore.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-186">When you create the extractor, the extractor page opens.</span></span> <span data-ttu-id="ee4a5-187">In questa pagina è presente un elenco dei file di esempio e nel visualizzatore viene mostrato il primo file nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-187">Here you see a list of your sample files, with the first file on the list displayed in the viewer.</span></span>

![Screenshot of the Client extractor Labeled examples page.](../media/content-understanding/client-extractor-labeled-examples.png) 

<span data-ttu-id="ee4a5-189">Per etichettare l'entità:</span><span class="sxs-lookup"><span data-stu-id="ee4a5-189">To label the entity:</span></span>

1. <span data-ttu-id="ee4a5-190">Nel visualizzatore selezionare i dati da estrarre dai file.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-190">From the viewer, select the data that you want to extract from the files.</span></span> <span data-ttu-id="ee4a5-191">Ad esempio, se si desidera estrarre *il client*, evidenziare il valore del client nel primo file (in questo esempio, Best For *You Organics*) e quindi selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-191">For example, if you want to extract the *Client*, you highlight the client value in the first file (in this example, *Best For You Organics*), and then select **Save**.</span></span> <span data-ttu-id="ee4a5-192">Vedrai il valore visualizzato dal file nell'elenco **Esempi** con etichetta, sotto la **colonna Etichetta.**</span><span class="sxs-lookup"><span data-stu-id="ee4a5-192">You'll see the value display from the file in the **Labeled examples** list, under the **Label** column.</span></span>

2. <span data-ttu-id="ee4a5-193">Selezionare **File successivo** per salvare automaticamente e aprire il file successivo nell'elenco nel visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-193">Select **Next file** to autosave and open the next file in the list in the viewer.</span></span> <span data-ttu-id="ee4a5-194">In caso **contrario,** selezionare Salva e quindi selezionare un altro file **nell'elenco Esempi con** etichetta.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-194">Or select **Save**, and then select another file from the **Labeled examples** list.</span></span>

3. <span data-ttu-id="ee4a5-195">Nel visualizzatore ripetere i passaggi 1 e 2, quindi ripetere fino a salvare l'etichetta in tutti i file.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-195">In the viewer, repeat steps 1 and 2, then repeat until you saved the label in all the files.</span></span>

<span data-ttu-id="ee4a5-196">Dopo aver etichettato i file, viene visualizzato un banner di notifica che informa di passare alla formazione.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-196">After you've labeled the files, a notification banner displays informing you to move to training.</span></span> <span data-ttu-id="ee4a5-197">È possibile scegliere di etichettare più documenti o passare alla formazione.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-197">You can choose to label more documents or advance to training.</span></span>

#### <a name="add-an-explanation"></a><span data-ttu-id="ee4a5-198">Aggiungere una spiegazione</span><span class="sxs-lookup"><span data-stu-id="ee4a5-198">Add an explanation</span></span>

<span data-ttu-id="ee4a5-199">Puoi creare una spiegazione che fornisce un suggerimento sul formato dell'entità stessa e sulle varianti che potrebbe avere nei file di esempio.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-199">You can create an explanation that provides a hint about the entity format itself and variations it might have in the example files.</span></span> <span data-ttu-id="ee4a5-200">Ad esempio, un valore di data può essere in molti formati diversi, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="ee4a5-200">For example, a date value can be in many different formats, such as:</span></span>

- <span data-ttu-id="ee4a5-201">14/10/2019</span><span class="sxs-lookup"><span data-stu-id="ee4a5-201">10/14/2019</span></span>
- <span data-ttu-id="ee4a5-202">14 ottobre 2019</span><span class="sxs-lookup"><span data-stu-id="ee4a5-202">October 14, 2019</span></span>
- <span data-ttu-id="ee4a5-203">Lunedì 14 ottobre 2019</span><span class="sxs-lookup"><span data-stu-id="ee4a5-203">Monday, October 14, 2019</span></span>

<span data-ttu-id="ee4a5-204">Per identificare la data *di inizio del contratto,* è possibile creare una spiegazione del modello.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-204">To help identify the *Contract Start Date*, you can create a pattern explanation.</span></span>

1. <span data-ttu-id="ee4a5-205">Nella sezione **Spiegazioni** selezionare **Nuovo** e quindi **Vuoto.**</span><span class="sxs-lookup"><span data-stu-id="ee4a5-205">In the **Explanations** section, select **New** and then **Blank**.</span></span>

2. <span data-ttu-id="ee4a5-206">Nella pagina **Crea spiegazione**:</span><span class="sxs-lookup"><span data-stu-id="ee4a5-206">On the **Create an explanation** page:</span></span>

    <span data-ttu-id="ee4a5-207">a.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-207">a.</span></span> <span data-ttu-id="ee4a5-208">Nel campo **Nome** digitare il nome della spiegazione, ad esempio *Data.*</span><span class="sxs-lookup"><span data-stu-id="ee4a5-208">In the **Name** field, type the name of the explanation (such as *Date*).</span></span>

    <span data-ttu-id="ee4a5-209">b.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-209">b.</span></span> <span data-ttu-id="ee4a5-210">Nel campo **Tipo di spiegazione** selezionare Elenco **motivo.**</span><span class="sxs-lookup"><span data-stu-id="ee4a5-210">In the **Explanation type** field, select **Pattern list**.</span></span>

    <span data-ttu-id="ee4a5-211">c.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-211">c.</span></span> <span data-ttu-id="ee4a5-212">Nel campo **Valore** specificare la variazione della data così come vengono visualizzate nei file di esempio.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-212">In the **Value** field, provide the date variation as they appear in the sample files.</span></span> <span data-ttu-id="ee4a5-213">Ad esempio, se sono presenti formati di data visualizzati come 0/00/0000, immettere tutte le varianti presenti nei documenti, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="ee4a5-213">For example, if you have date formats that appear as 0/00/0000, you enter any variations that appear in your documents, such as:</span></span>

    - <span data-ttu-id="ee4a5-214">0/0/0000</span><span class="sxs-lookup"><span data-stu-id="ee4a5-214">0/0/0000</span></span>
    - <span data-ttu-id="ee4a5-215">0/00/0000</span><span class="sxs-lookup"><span data-stu-id="ee4a5-215">0/00/0000</span></span>
    - <span data-ttu-id="ee4a5-216">00/0/0000</span><span class="sxs-lookup"><span data-stu-id="ee4a5-216">00/0/0000</span></span>
    - <span data-ttu-id="ee4a5-217">00/00/0000</span><span class="sxs-lookup"><span data-stu-id="ee4a5-217">00/00/0000</span></span>

4. <span data-ttu-id="ee4a5-218">Selezionare **Salva e allena**.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-218">Select **Save and train**.</span></span>

#### <a name="test-your-model-again"></a><span data-ttu-id="ee4a5-219">Testare di nuovo il modello</span><span class="sxs-lookup"><span data-stu-id="ee4a5-219">Test your model again</span></span>

<span data-ttu-id="ee4a5-220">Puoi testare il modello di contratto su file di esempio che non sono stati mai visti prima.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-220">You can test your Contract model on example files it hasn’t seen before.</span></span> <span data-ttu-id="ee4a5-221">Questo è facoltativo, ma può essere una procedura consigliata utile.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-221">This is optional, but it can be a useful best practice.</span></span>

1. <span data-ttu-id="ee4a5-222">Nella pagina **Model > Contract > Contract classifier** selezionare la scheda **Test.** Il modello viene eseguito nei file di esempio senza etichetta.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-222">On the **Models > Contract > Contract classifier** page, select the **Test** tab. This runs the model on your unlabeled example files.</span></span>

2. <span data-ttu-id="ee4a5-223">**Nell'elenco File di** test vengono visualizzati i file di esempio e viene indicato se il modello è in grado di estrarre le informazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-223">In the **Test files** list, your example files display and shows if the model is able to extract the information you need.</span></span> <span data-ttu-id="ee4a5-224">Usare queste informazioni per determinare l'efficacia del classificatore nell'identificazione dei documenti.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-224">Use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

3. <span data-ttu-id="ee4a5-225">Al termine, selezionare **Esci da training**.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-225">When done, select **Exit Training**.</span></span>

### <a name="apply-your-model-to-a-document-library"></a><span data-ttu-id="ee4a5-226">Applicare il modello a una raccolta documenti</span><span class="sxs-lookup"><span data-stu-id="ee4a5-226">Apply your model to a document library</span></span>

<span data-ttu-id="ee4a5-227">Per applicare il modello a una raccolta SharePoint documenti:</span><span class="sxs-lookup"><span data-stu-id="ee4a5-227">To apply your model to a SharePoint document library:</span></span>

1. <span data-ttu-id="ee4a5-228">Nella pagina **Modelli > contratto,** in Azioni **chiave** Applica  >  **modello alle** raccolte, selezionare **Applica modello.**</span><span class="sxs-lookup"><span data-stu-id="ee4a5-228">On the **Models > Contract** page, under **Key actions** > **Apply model to libraries**, select **Apply model**.</span></span>

   ![Screenshot che mostra la pagina Contratti con l'opzione Applica modello alle raccolte evidenziata.](../media/content-understanding/key-actions-apply-model.png)

2. <span data-ttu-id="ee4a5-230">Nel riquadro **Aggiungi contratto** selezionare il SharePoint contenente la raccolta documenti a cui si desidera applicare il modello.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-230">On the **Add Contract** panel, select the SharePoint site that contains the document library that you want to apply the model to.</span></span> <span data-ttu-id="ee4a5-231">Se il sito non viene visualizzato nell'elenco, usare la casella di ricerca per trovarlo.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-231">If the site does not show in the list, use the search box to find it.</span></span> <span data-ttu-id="ee4a5-232">Seleziona **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-232">Select **Add**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ee4a5-233">È necessario disporre delle autorizzazioni di *Gestione dell'elenco* o dei diritti di *modifica* per la raccolta documenti a cui si sta applicando il modello.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-233">You must have *Manage List* permissions or *Edit* rights to the document library you are applying the model to.</span></span>

3. <span data-ttu-id="ee4a5-234">Dopo aver selezionato il sito, selezionare la raccolta documenti a cui si desidera applicare il modello.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-234">After you select the site, select the document library to which you want to apply the model.</span></span>

4. <span data-ttu-id="ee4a5-235">Poiché il modello è associato a un tipo di contenuto, quando lo si applica alla raccolta verrà aggiunto il tipo di contenuto e la relativa visualizzazione con le etichette estratte che vengono visualizzate come colonne.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-235">Because the model is associated to a content type, when you apply it to the library it will add the content type and its view with the labels you extracted showing as columns.</span></span> <span data-ttu-id="ee4a5-236">Questa visualizzazione è la visualizzazione predefinita della raccolta per impostazione predefinita, ma è possibile  scegliere di non  impostarla come predefinita selezionando Impostazioni avanzate e deselezionando la casella di controllo Imposta questa nuova visualizzazione come predefinita.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-236">This view is the library's default view by default, but you can optionally choose to have it not be the default view by selecting **Advanced settings** and clearing the **Set this new view as default** check box.</span></span>

5. <span data-ttu-id="ee4a5-237">Selezionare **Aggiungi** per applicare il modello alla raccolta.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-237">Select **Add** to apply the model to the library.</span></span>

6. <span data-ttu-id="ee4a5-238">Nella **sezione Raccolte con questo** modello  della pagina Modelli > contratto verrà visualizzato l'URL del sito SharePoint sito.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-238">On the **Models > Contract** page, in the **Libraries with this model** section, you'll see the URL to the SharePoint site listed.</span></span>

    ![Screenshot della home page contratto che mostra la sezione Librerie con questo modello.](../media/content-understanding/contract-libraries-with-this-model.png)

7. <span data-ttu-id="ee4a5-240">In **Impostazioni**  >  **impostazioni raccolta:**</span><span class="sxs-lookup"><span data-stu-id="ee4a5-240">Under **Settings** > **Library settings**:</span></span>

   - <span data-ttu-id="ee4a5-241">Aggiungere una colonna denominata **Status** e selezionare **Choice** come tipo di colonna.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-241">Add a column named **Status** and select **Choice** as the column type.</span></span>
   - <span data-ttu-id="ee4a5-242">Applicare i **valori In revisione,** **Approvato** **e Rifiutato.**</span><span class="sxs-lookup"><span data-stu-id="ee4a5-242">Apply the **In review**, **Approved**, and **Rejected** values.</span></span>

<span data-ttu-id="ee4a5-243">Dopo aver applicato il modello alla raccolta documenti, è possibile iniziare a caricare documenti nel sito e visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-243">After you apply the model to the document library, you can begin uploading documents to the site and see the results.</span></span>

## <a name="next-step"></a><span data-ttu-id="ee4a5-244">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="ee4a5-244">Next step</span></span>

[<span data-ttu-id="ee4a5-245">Passaggio 2. Usare Microsoft Teams per creare il canale di gestione dei contratti</span><span class="sxs-lookup"><span data-stu-id="ee4a5-245">Step 2. Use Microsoft Teams to create your contract management channel</span></span>](solution-manage-contracts-step2.md)