---
title: Passaggio 1. Usare SharePoint Syntex per identificare i file di contratto ed estrarre i dati
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.date: 05/17/2021
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Informazioni su come usare SharePoint Syntex per identificare i file di contratto ed estrarre i dati utilizzando una Microsoft 365 soluzione.
ms.openlocfilehash: f246dd4ed619dd9885d2c45c69d607cfa9c2483f
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538556"
---
# <a name="step-1-use-sharepoint-syntex-to-identify-contract-files-and-extract-data"></a><span data-ttu-id="81852-104">Passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="81852-104">Step 1.</span></span> <span data-ttu-id="81852-105">Usare SharePoint Syntex per identificare i file di contratto ed estrarre i dati</span><span class="sxs-lookup"><span data-stu-id="81852-105">Use SharePoint Syntex to identify contract files and extract data</span></span>

<span data-ttu-id="81852-106">L'organizzazione ha bisogno di un modo per identificare e classificare tutti i documenti di contratto dai numerosi file ricevuti.</span><span class="sxs-lookup"><span data-stu-id="81852-106">Your organization needs a way to identify and classify all contract documents from the many files you receive.</span></span> <span data-ttu-id="81852-107">È inoltre possibile visualizzare rapidamente diversi elementi chiave in ognuno dei file di contratto identificati (ad esempio, *Cliente,* Appaltatore e *Importo commissione).*</span><span class="sxs-lookup"><span data-stu-id="81852-107">You also want to be able to quickly view several key elements in each of the contract files identified (for example, *Client*, *Contractor*, and *Fee amount*).</span></span> <span data-ttu-id="81852-108">A tale scopo, utilizzare [SharePoint Syntex](index.md) per creare un modello di comprensione dei documenti e applicarlo a una raccolta documenti.</span><span class="sxs-lookup"><span data-stu-id="81852-108">You can do this by using [SharePoint Syntex](index.md) to create a document understanding model and applying it to a document library.</span></span>

## <a name="overview-of-the-process"></a><span data-ttu-id="81852-109">Panoramica del processo</span><span class="sxs-lookup"><span data-stu-id="81852-109">Overview of the process</span></span>

<span data-ttu-id="81852-110">[La comprensione dei](document-understanding-overview.md) documenti usa modelli di intelligenza artificiale (AI) per automatizzare la classificazione dei file e l'estrazione delle informazioni.</span><span class="sxs-lookup"><span data-stu-id="81852-110">[Document understanding](document-understanding-overview.md) uses artificial intelligence (AI) models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="81852-111">I modelli di comprensione dei documenti sono inoltre ottimali nell'estrazione di informazioni da documenti non strutturati e semistrutturati in cui le informazioni necessarie non sono contenute in tabelle o moduli, ad esempio contratti.</span><span class="sxs-lookup"><span data-stu-id="81852-111">Document understanding models are also optimal in extracting information from unstructured and semi-structured documents where the information you need isn't contained in tables or forms, such as contracts.</span></span>

1. <span data-ttu-id="81852-112">Innanzitutto, è necessario trovare almeno cinque file di esempio che è possibile utilizzare per "formare" il modello per cercare caratteristiche specifiche del tipo di contenuto che si sta tentando di identificare (un contratto).</span><span class="sxs-lookup"><span data-stu-id="81852-112">First, you need to find at least five example files that you can use to "train" the model to search for characteristics that are specific to the content type you're trying to identify (a contract).</span></span> 

2. <span data-ttu-id="81852-113">Usando SharePoint Syntex, crea un nuovo modello di comprensione dei documenti.</span><span class="sxs-lookup"><span data-stu-id="81852-113">Using SharePoint Syntex, create a new document understanding model.</span></span> <span data-ttu-id="81852-114">Usando i file di esempio, è necessario [creare un classificatore](create-a-classifier.md).</span><span class="sxs-lookup"><span data-stu-id="81852-114">Using your example files, you need to [create a classifier](create-a-classifier.md).</span></span> <span data-ttu-id="81852-115">Formando il classificatore con i file di esempio, viene insegnato a cercare caratteristiche specifiche di ciò che si potrebbe vedere nei contratti dell'azienda.</span><span class="sxs-lookup"><span data-stu-id="81852-115">By training the classifier with your example files, you teach it to search for characteristics that are specific to what you would see in your company's contracts.</span></span> <span data-ttu-id="81852-116">Ad esempio, [creare una "spiegazione"](create-a-classifier.md#create-an-explanation) che cerca stringhe specifiche presenti nei contratti, ad esempio Contratto di *servizio,* *Condizioni* del contratto e *Compensazione.*</span><span class="sxs-lookup"><span data-stu-id="81852-116">For example, [create an "explanation"](create-a-classifier.md#create-an-explanation) that searches for specific strings that are in your contracts, such as *Service Agreement*, *Terms of Agreement*, and *Compensation*.</span></span> <span data-ttu-id="81852-117">Puoi anche formare la tua spiegazione per cercare queste stringhe in sezioni specifiche del documento o posizionate accanto ad altre stringhe.</span><span class="sxs-lookup"><span data-stu-id="81852-117">You can even train your explanation to look for these strings in specific sections of the document, or located next to other strings.</span></span> <span data-ttu-id="81852-118">Quando si pensa di aver addestrato il classificatore con le informazioni necessarie, è possibile testare il modello su un set di file di esempio di esempio per verificare l'efficienza.</span><span class="sxs-lookup"><span data-stu-id="81852-118">When you think you have trained your classifier with the information it needs, you can test your model on a sample set of example files to see how efficient it is.</span></span> <span data-ttu-id="81852-119">Dopo il test, se necessario, è possibile scegliere di apportare modifiche alle spiegazioni per renderle più efficienti.</span><span class="sxs-lookup"><span data-stu-id="81852-119">After testing, if needed you can choose to make changes to your explanations to make them more efficient.</span></span> 

3. <span data-ttu-id="81852-120">Nel modello puoi creare un [estrattore](create-an-extractor.md) per estrarre parti specifiche di dati da ogni contratto.</span><span class="sxs-lookup"><span data-stu-id="81852-120">In your model, you can [create an extractor](create-an-extractor.md) to pull out specific pieces of data from each contract.</span></span> <span data-ttu-id="81852-121">Ad esempio, per ogni contratto, le informazioni più preoccupate sono chi è il cliente, il nome dell'appaltatore e il costo totale.</span><span class="sxs-lookup"><span data-stu-id="81852-121">For example, for each contract, the information you're most concerned about is who the client is, the name of the contractor, and the total cost.</span></span>

4. <span data-ttu-id="81852-122">Dopo aver creato correttamente il modello, applicarlo a una [raccolta SharePoint documenti.](apply-a-model.md)</span><span class="sxs-lookup"><span data-stu-id="81852-122">After you successfully create your model, [apply it to a SharePoint document library](apply-a-model.md).</span></span> <span data-ttu-id="81852-123">Quando si caricano documenti nella raccolta documenti, verrà eseguito il modello di comprensione dei documenti e verranno identificati e classificati tutti i file che corrispondono al tipo di contenuto dei contratti definito nel modello.</span><span class="sxs-lookup"><span data-stu-id="81852-123">As you upload documents to the document library, your document understanding model will run and will identify and classify all files that match the contracts content type you defined in your model.</span></span> <span data-ttu-id="81852-124">Tutti i file classificati come contratti verranno visualizzati in una visualizzazione raccolta personalizzata.</span><span class="sxs-lookup"><span data-stu-id="81852-124">All files that are classified as contracts will display in a custom library view.</span></span> <span data-ttu-id="81852-125">I file visualizzano anche i valori di ogni contratto definito nell'estrattore.</span><span class="sxs-lookup"><span data-stu-id="81852-125">The files will also display the values from each contract that you defined in your extractor.</span></span>

   ![Contratti nella raccolta documenti](../media/content-understanding/doc-lib-solution.png)

5. <span data-ttu-id="81852-127">Se hai requisiti di conservazione per i contratti, [](apply-a-retention-label-to-a-model.md) puoi anche usare il modello per applicare un'etichetta di conservazione che impedirà l'eliminazione dei contratti per un periodo di tempo specificato.</span><span class="sxs-lookup"><span data-stu-id="81852-127">If you have retention requirements for your contracts, you can also use your model to [apply a retention label](apply-a-retention-label-to-a-model.md) that will prevent your contracts from being deleted for a specified period of time.</span></span>

## <a name="steps-to-create-and-train-your-model"></a><span data-ttu-id="81852-128">Passaggi per creare ed eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="81852-128">Steps to create and train your model</span></span>

> [!NOTE]
> <span data-ttu-id="81852-129">Per questi passaggi, è possibile utilizzare i file di esempio nel [repository microsoft SharePoint Syntex Samples.](https://github.com/pnp/syntex-samples)</span><span class="sxs-lookup"><span data-stu-id="81852-129">For these steps, you can use the example files in the [Microsoft SharePoint Syntex Samples repository](https://github.com/pnp/syntex-samples).</span></span> <span data-ttu-id="81852-130">Gli esempi in questo repository contengono sia i file del modello di comprensione dei documenti che i file utilizzati per eseguire il training del modello.</span><span class="sxs-lookup"><span data-stu-id="81852-130">The samples in this repository contain both the document understanding model files and the files used to train the model.</span></span>

### <a name="create-a-contract-model"></a><span data-ttu-id="81852-131">Creare un modello di contratto</span><span class="sxs-lookup"><span data-stu-id="81852-131">Create a Contract model</span></span>

<span data-ttu-id="81852-132">Il primo passaggio consiste nel creare il modello di contratto.</span><span class="sxs-lookup"><span data-stu-id="81852-132">The first step is to create your Contract model.</span></span>

1. <span data-ttu-id="81852-133">Nel centro contenuti selezionare **Nuovo** e quindi **Crea un modello**.</span><span class="sxs-lookup"><span data-stu-id="81852-133">From the content center, select **New**, and then **Create a model**.</span></span>

2. <span data-ttu-id="81852-134">Nel riquadro **Nuovo modello** di comprensione documento digitare **il** nome del modello nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="81852-134">On the **New document understanding model** pane, in the **Name** field, type the name of the model.</span></span> <span data-ttu-id="81852-135">Per questa soluzione di gestione dei contratti, è possibile assegnare al modello il nome *Contract*.</span><span class="sxs-lookup"><span data-stu-id="81852-135">For this contract management solution, you can name the model *Contract*.</span></span>

4. <span data-ttu-id="81852-136">Scegliere **Crea**.</span><span class="sxs-lookup"><span data-stu-id="81852-136">Choose **Create**.</span></span> <span data-ttu-id="81852-137">Verrà creata una home page per il modello.</span><span class="sxs-lookup"><span data-stu-id="81852-137">This creates a home page for the model.</span></span></br>

    ![Screenshot della home page contratto.](../media/content-understanding/models-contract-home-page.png)


### <a name="train-your-model-to-classify-a-type-of-file"></a><span data-ttu-id="81852-139">Eseguire il training del modello per classificare un tipo di file</span><span class="sxs-lookup"><span data-stu-id="81852-139">Train your model to classify a type of file</span></span>

#### <a name="add-example-files-for-your-model"></a><span data-ttu-id="81852-140">Aggiungere file di esempio per il modello</span><span class="sxs-lookup"><span data-stu-id="81852-140">Add example files for your model</span></span>

<span data-ttu-id="81852-141">È necessario aggiungere almeno cinque file di esempio che sono documenti di contratto e un file di esempio che non è un documento di contratto (ad esempio, una dichiarazione di lavoro).</span><span class="sxs-lookup"><span data-stu-id="81852-141">You need to add at least five example files that are contract documents, and one example file that's not a contract document (for example, a statement of work).</span></span> 

1. <span data-ttu-id="81852-142">Nella pagina **Modelli > Contratto,** in Azioni **chiave** Aggiungi file  >  **di esempio,** selezionare **Aggiungi file**.</span><span class="sxs-lookup"><span data-stu-id="81852-142">On the **Models > Contract** page, under **Key actions** > **Add example files**, select **Add files**.</span></span>

   ![Screenshot che mostra la pagina Contratti con l'opzione Aggiungi file di esempio evidenziata.](../media/content-understanding/key-actions-add-example-files.png)

2. <span data-ttu-id="81852-144">Nella pagina **Seleziona file di esempio per il modello** aprire la cartella Contratto, selezionare i file che si desidera utilizzare e quindi selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="81852-144">On the **Select example files for your model** page, open the Contract folder, select files you want to use, and then select **Add**.</span></span> <span data-ttu-id="81852-145">Se non si dispone di file di esempio, **selezionare Upload** per aggiungerli.</span><span class="sxs-lookup"><span data-stu-id="81852-145">If you don't have example files there, select **Upload** to add them.</span></span>

#### <a name="label-the-files-as-positive-or-negative-examples"></a><span data-ttu-id="81852-146">Etichettare i file come esempi positivi o negativi</span><span class="sxs-lookup"><span data-stu-id="81852-146">Label the files as positive or negative examples</span></span>

1. <span data-ttu-id="81852-147">Nella pagina **Modelli > contratto,** in Azioni **chiave** Classificare i file ed eseguire  >  **la formazione,** selezionare **Classificatore di training.**</span><span class="sxs-lookup"><span data-stu-id="81852-147">On the **Models > Contract** page, under **Key actions** > **Classify files and run training**, select **Train classifier**.</span></span>

   ![Screenshot showing the Contracts page with Classify files and run training option highlighted.](../media/content-understanding/key-actions-classify-files.png)

2. <span data-ttu-id="81852-149">Nella pagina Model **> Contract > Contract classifier,** nel visualizzatore nella parte superiore del primo file di esempio verrà visualizzato un testo che richiede se il file è un esempio del modello di contratto creato.</span><span class="sxs-lookup"><span data-stu-id="81852-149">On the **Models > Contract > Contract classifier** page, in the viewer on the top of the first example file, you'll see text asking if the file is an example of the Contract model you created.</span></span> <span data-ttu-id="81852-150">Se è un esempio positivo, selezionare **Sì**.</span><span class="sxs-lookup"><span data-stu-id="81852-150">If it is a positive example, select **Yes**.</span></span> <span data-ttu-id="81852-151">Se è un esempio negativo, selezionare **No**.</span><span class="sxs-lookup"><span data-stu-id="81852-151">If it is a negative example, select **No**.</span></span>

3. <span data-ttu-id="81852-152">**Nell'elenco Esempi con** etichetta a sinistra seleziona gli altri file che vuoi usare come esempi ed etichettali.</span><span class="sxs-lookup"><span data-stu-id="81852-152">From the **Labeled examples** list on the left, select other files that you want to use as examples, and label them.</span></span> 

    ![Home page del classificatore](../media/content-understanding/models-contract-classifier.png) 

#### <a name="add-at-least-one-explanation-to-train-the-classifier&quot;></a><span data-ttu-id=&quot;81852-154&quot;>Aggiungere almeno una spiegazione per il training del classificatore</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;81852-154&quot;>Add at least one explanation to train the classifier</span></span> 

1. <span data-ttu-id=&quot;81852-155&quot;>Nella pagina **Model > Contract > Contract classifier** selezionare la scheda **Train.**</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;81852-155&quot;>On the **Models > Contract > Contract classifier** page, select the **Train** tab.</span></span>

2. <span data-ttu-id=&quot;81852-156&quot;>Nella sezione **File con training** verrà visualizzato un elenco dei file di esempio etichettati in precedenza.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;81852-156&quot;>In the **Trained files** section, you'll see a list of the example files that you previously labeled.</span></span> <span data-ttu-id=&quot;81852-157&quot;>Seleziona uno dei file positivi dall'elenco per visualizzarlo nel visualizzatore.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;81852-157&quot;>Select one of the positive files from the list to display it in the viewer.</span></span>

3. <span data-ttu-id=&quot;81852-158&quot;>Nella sezione **Spiegazioni** selezionare **Nuovo** e quindi **Vuoto.**</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;81852-158&quot;>In the **Explanations** section, select **New** and then **Blank**.</span></span>

4. <span data-ttu-id=&quot;81852-159&quot;>Nella pagina **Crea spiegazione**:</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;81852-159&quot;>On the **Create an explanation** page:</span></span>

    <span data-ttu-id=&quot;81852-160&quot;>a.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;81852-160&quot;>a.</span></span> <span data-ttu-id=&quot;81852-161&quot;>Nel campo **Nome** digitare il nome della spiegazione, ad esempio &quot;Contratto&quot;.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;81852-161&quot;>In the **Name** field, type the name of the explanation (such as &quot;Agreement").</span></span>

    <span data-ttu-id="81852-162">b.</span><span class="sxs-lookup"><span data-stu-id="81852-162">b.</span></span> <span data-ttu-id="81852-163">Nel campo **Tipo di spiegazione** selezionare Elenco **frasi** perché si aggiunge una stringa di testo.</span><span class="sxs-lookup"><span data-stu-id="81852-163">In the **Explanation type** field, select **Phrase list**, because you add a text string.</span></span>

    <span data-ttu-id="81852-164">c.</span><span class="sxs-lookup"><span data-stu-id="81852-164">c.</span></span> <span data-ttu-id="81852-165">Nella casella **di riepilogo** Frase digitare la stringa, ad esempio "CONTRATTO".</span><span class="sxs-lookup"><span data-stu-id="81852-165">In the **Phrase list** box, type the string (such as "AGREEMENT").</span></span> <span data-ttu-id="81852-166">È possibile selezionare **Maiuscole/minuscole** se la stringa deve fare distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="81852-166">You can select **Case sensitive** if the string needs to be case-sensitive.</span></span>

    <span data-ttu-id="81852-167">d.</span><span class="sxs-lookup"><span data-stu-id="81852-167">d.</span></span> <span data-ttu-id="81852-168">Selezionare **Salva e allena**.</span><span class="sxs-lookup"><span data-stu-id="81852-168">Select **Save and train**.</span></span>

    ![Screenshot of the Create an explanation panel.](../media/content-understanding/contract-classifier-create-explanation.png) 

#### <a name="test-your-model"></a><span data-ttu-id="81852-170">Testare il modello</span><span class="sxs-lookup"><span data-stu-id="81852-170">Test your model</span></span>

<span data-ttu-id="81852-171">Puoi testare il modello di contratto su file di esempio che non sono stati mai visti prima.</span><span class="sxs-lookup"><span data-stu-id="81852-171">You can test your Contract model on example files it hasn’t seen before.</span></span> <span data-ttu-id="81852-172">Questo è facoltativo, ma può essere una procedura consigliata utile.</span><span class="sxs-lookup"><span data-stu-id="81852-172">This is optional, but it can be a useful best practice.</span></span>

1. <span data-ttu-id="81852-173">Nella pagina **Model > Contract > Contract classifier** selezionare la scheda **Test.** Il modello viene eseguito nei file di esempio senza etichetta.</span><span class="sxs-lookup"><span data-stu-id="81852-173">On the **Models > Contract > Contract classifier** page, select the **Test** tab. This runs the model on your unlabeled example files.</span></span>

2. <span data-ttu-id="81852-174">**Nell'elenco Test Files** vengono visualizzati i file di esempio e viene indicato se il modello li ha previsti come positivi o negativi.</span><span class="sxs-lookup"><span data-stu-id="81852-174">In the **Test Files** list, your example files display and shows if the model predicted them to be positive or negative.</span></span> <span data-ttu-id="81852-175">Usare queste informazioni per determinare l'efficacia del classificatore nell'identificazione dei documenti.</span><span class="sxs-lookup"><span data-stu-id="81852-175">Use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![Screenshot dei file senza etichetta nell'elenco File di testo](../media/content-understanding/test-on-files.png) 

3. <span data-ttu-id="81852-177">Al termine, selezionare **Esci da training**.</span><span class="sxs-lookup"><span data-stu-id="81852-177">When done, select **Exit Training**.</span></span>

### <a name="create-and-train-an-extractor"></a><span data-ttu-id="81852-178">Creare e formare un estrattore</span><span class="sxs-lookup"><span data-stu-id="81852-178">Create and train an extractor</span></span>

1. <span data-ttu-id="81852-179">Nella pagina **Modelli > contratto,** in **Azioni chiave** Creare e formare  >  **estrattori,** selezionare Crea **estrattore.**</span><span class="sxs-lookup"><span data-stu-id="81852-179">On the **Models > Contract** page, under **Key actions** > **Create and train extractors**, select **Create extractor**.</span></span>

   ![Screenshot che mostra la pagina Contratti con l'opzione Crea e addestra estrattori evidenziata.](../media/content-understanding/key-actions-create-extractors.png)

2. <span data-ttu-id="81852-181">Nel **campo Nuovo** nome del  pannello Nuovo estrattore di entità digitare il nome dell'estrattore.</span><span class="sxs-lookup"><span data-stu-id="81852-181">On the **New entity extractor** panel, in the **New name** field, type the name of your extractor.</span></span> <span data-ttu-id="81852-182">Ad esempio, assegnare il *nome Client* se si desidera estrarre il nome del client da ogni contratto.</span><span class="sxs-lookup"><span data-stu-id="81852-182">For example, name it *Client* if you want to extract the name of the client from each contract.</span></span>

3. <span data-ttu-id="81852-183">Al termine, selezionare **Crea**.</span><span class="sxs-lookup"><span data-stu-id="81852-183">When you're done, select **Create**.</span></span>

#### <a name="label-the-entity-you-want-to-extract"></a><span data-ttu-id="81852-184">Etichettare l'entità che si desidera estrarre</span><span class="sxs-lookup"><span data-stu-id="81852-184">Label the entity you want to extract</span></span>

<span data-ttu-id="81852-185">Quando si crea l'estrattore, viene aperta la pagina dell'estrattore.</span><span class="sxs-lookup"><span data-stu-id="81852-185">When you create the extractor, the extractor page opens.</span></span> <span data-ttu-id="81852-186">In questa pagina è presente un elenco dei file di esempio e nel visualizzatore viene mostrato il primo file nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="81852-186">Here you see a list of your sample files, with the first file on the list displayed in the viewer.</span></span>

![Screenshot of the Client extractor Labeled examples page.](../media/content-understanding/client-extractor-labeled-examples.png) 

<span data-ttu-id="81852-188">Per etichettare l'entità:</span><span class="sxs-lookup"><span data-stu-id="81852-188">To label the entity:</span></span>

1. <span data-ttu-id="81852-189">Nel visualizzatore selezionare i dati da estrarre dai file.</span><span class="sxs-lookup"><span data-stu-id="81852-189">From the viewer, select the data that you want to extract from the files.</span></span> <span data-ttu-id="81852-190">Ad esempio, se si desidera estrarre *il client*, evidenziare il valore del client nel primo file (in questo esempio, Best For *You Organics*) e quindi selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="81852-190">For example, if you want to extract the *Client*, you highlight the client value in the first file (in this example, *Best For You Organics*), and then select **Save**.</span></span> <span data-ttu-id="81852-191">Vedrai il valore visualizzato dal file nell'elenco **Esempi** con etichetta, sotto la **colonna Etichetta.**</span><span class="sxs-lookup"><span data-stu-id="81852-191">You'll see the value display from the file in the **Labeled examples** list, under the **Label** column.</span></span>

2. <span data-ttu-id="81852-192">Selezionare **File successivo** per salvare automaticamente e aprire il file successivo nell'elenco nel visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="81852-192">Select **Next file** to autosave and open the next file in the list in the viewer.</span></span> <span data-ttu-id="81852-193">In caso **contrario,** selezionare Salva e quindi selezionare un altro file **nell'elenco Esempi con** etichetta.</span><span class="sxs-lookup"><span data-stu-id="81852-193">Or select **Save**, and then select another file from the **Labeled examples** list.</span></span>

3. <span data-ttu-id="81852-194">Nel visualizzatore ripetere i passaggi 1 e 2, quindi ripetere fino a salvare l'etichetta in tutti i file.</span><span class="sxs-lookup"><span data-stu-id="81852-194">In the viewer, repeat steps 1 and 2, then repeat until you saved the label in all the files.</span></span>

<span data-ttu-id="81852-195">Dopo aver etichettato i file, viene visualizzato un banner di notifica che informa di passare alla formazione.</span><span class="sxs-lookup"><span data-stu-id="81852-195">After you've labeled the files, a notification banner displays informing you to move to training.</span></span> <span data-ttu-id="81852-196">È possibile scegliere di etichettare più documenti o passare alla formazione.</span><span class="sxs-lookup"><span data-stu-id="81852-196">You can choose to label more documents or advance to training.</span></span>

#### <a name="add-an-explanation"></a><span data-ttu-id="81852-197">Aggiungere una spiegazione</span><span class="sxs-lookup"><span data-stu-id="81852-197">Add an explanation</span></span>

<span data-ttu-id="81852-198">Puoi creare una spiegazione che fornisce un suggerimento sul formato dell'entità stessa e sulle varianti che potrebbe avere nei file di esempio.</span><span class="sxs-lookup"><span data-stu-id="81852-198">You can create an explanation that provides a hint about the entity format itself and variations it might have in the example files.</span></span> <span data-ttu-id="81852-199">Ad esempio, un valore di data può essere in molti formati diversi, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="81852-199">For example, a date value can be in many different formats, such as:</span></span>

- <span data-ttu-id="81852-200">14/10/2019</span><span class="sxs-lookup"><span data-stu-id="81852-200">10/14/2019</span></span>
- <span data-ttu-id="81852-201">14 ottobre 2019</span><span class="sxs-lookup"><span data-stu-id="81852-201">October 14, 2019</span></span>
- <span data-ttu-id="81852-202">Lunedì 14 ottobre 2019</span><span class="sxs-lookup"><span data-stu-id="81852-202">Monday, October 14, 2019</span></span>

<span data-ttu-id="81852-203">Per identificare la data *di inizio del contratto,* è possibile creare una spiegazione del modello.</span><span class="sxs-lookup"><span data-stu-id="81852-203">To help identify the *Contract Start Date*, you can create a pattern explanation.</span></span>

1. <span data-ttu-id="81852-204">Nella sezione **Spiegazioni** selezionare **Nuovo** e quindi **Vuoto.**</span><span class="sxs-lookup"><span data-stu-id="81852-204">In the **Explanations** section, select **New** and then **Blank**.</span></span>

2. <span data-ttu-id="81852-205">Nella pagina **Crea spiegazione**:</span><span class="sxs-lookup"><span data-stu-id="81852-205">On the **Create an explanation** page:</span></span>

    <span data-ttu-id="81852-206">a.</span><span class="sxs-lookup"><span data-stu-id="81852-206">a.</span></span> <span data-ttu-id="81852-207">Nel campo **Nome** digitare il nome della spiegazione, ad esempio *Data.*</span><span class="sxs-lookup"><span data-stu-id="81852-207">In the **Name** field, type the name of the explanation (such as *Date*).</span></span>

    <span data-ttu-id="81852-208">b.</span><span class="sxs-lookup"><span data-stu-id="81852-208">b.</span></span> <span data-ttu-id="81852-209">Nel campo **Tipo di spiegazione** selezionare Elenco **motivo.**</span><span class="sxs-lookup"><span data-stu-id="81852-209">In the **Explanation type** field, select **Pattern list**.</span></span>

    <span data-ttu-id="81852-210">c.</span><span class="sxs-lookup"><span data-stu-id="81852-210">c.</span></span> <span data-ttu-id="81852-211">Nel campo **Valore** specificare la variazione della data così come vengono visualizzate nei file di esempio.</span><span class="sxs-lookup"><span data-stu-id="81852-211">In the **Value** field, provide the date variation as they appear in the sample files.</span></span> <span data-ttu-id="81852-212">Ad esempio, se sono presenti formati di data visualizzati come 0/00/0000, immettere tutte le varianti presenti nei documenti, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="81852-212">For example, if you have date formats that appear as 0/00/0000, you enter any variations that appear in your documents, such as:</span></span>

    - <span data-ttu-id="81852-213">0/0/0000</span><span class="sxs-lookup"><span data-stu-id="81852-213">0/0/0000</span></span>
    - <span data-ttu-id="81852-214">0/00/0000</span><span class="sxs-lookup"><span data-stu-id="81852-214">0/00/0000</span></span>
    - <span data-ttu-id="81852-215">00/0/0000</span><span class="sxs-lookup"><span data-stu-id="81852-215">00/0/0000</span></span>
    - <span data-ttu-id="81852-216">00/00/0000</span><span class="sxs-lookup"><span data-stu-id="81852-216">00/00/0000</span></span>

4. <span data-ttu-id="81852-217">Selezionare **Salva e allena**.</span><span class="sxs-lookup"><span data-stu-id="81852-217">Select **Save and train**.</span></span>

#### <a name="test-your-model-again"></a><span data-ttu-id="81852-218">Testare di nuovo il modello</span><span class="sxs-lookup"><span data-stu-id="81852-218">Test your model again</span></span>

<span data-ttu-id="81852-219">Puoi testare il modello di contratto su file di esempio che non sono stati mai visti prima.</span><span class="sxs-lookup"><span data-stu-id="81852-219">You can test your Contract model on example files it hasn’t seen before.</span></span> <span data-ttu-id="81852-220">Questo è facoltativo, ma può essere una procedura consigliata utile.</span><span class="sxs-lookup"><span data-stu-id="81852-220">This is optional, but it can be a useful best practice.</span></span>

1. <span data-ttu-id="81852-221">Nella pagina **Model > Contract > Contract classifier** selezionare la scheda **Test.** Il modello viene eseguito nei file di esempio senza etichetta.</span><span class="sxs-lookup"><span data-stu-id="81852-221">On the **Models > Contract > Contract classifier** page, select the **Test** tab. This runs the model on your unlabeled example files.</span></span>

2. <span data-ttu-id="81852-222">**Nell'elenco File di** test vengono visualizzati i file di esempio e viene indicato se il modello è in grado di estrarre le informazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="81852-222">In the **Test files** list, your example files display and shows if the model is able to extract the information you need.</span></span> <span data-ttu-id="81852-223">Usare queste informazioni per determinare l'efficacia del classificatore nell'identificazione dei documenti.</span><span class="sxs-lookup"><span data-stu-id="81852-223">Use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

3. <span data-ttu-id="81852-224">Al termine, selezionare **Esci da training**.</span><span class="sxs-lookup"><span data-stu-id="81852-224">When done, select **Exit Training**.</span></span>

### <a name="apply-your-model-to-a-document-library"></a><span data-ttu-id="81852-225">Applicare il modello a una raccolta documenti</span><span class="sxs-lookup"><span data-stu-id="81852-225">Apply your model to a document library</span></span>

<span data-ttu-id="81852-226">Per applicare il modello a una raccolta SharePoint documenti:</span><span class="sxs-lookup"><span data-stu-id="81852-226">To apply your model to a SharePoint document library:</span></span>

1. <span data-ttu-id="81852-227">Nella pagina **Modelli > contratto,** in Azioni **chiave** Applica  >  **modello alle** raccolte, selezionare **Applica modello.**</span><span class="sxs-lookup"><span data-stu-id="81852-227">On the **Models > Contract** page, under **Key actions** > **Apply model to libraries**, select **Apply model**.</span></span>

   ![Screenshot che mostra la pagina Contratti con l'opzione Applica modello alle raccolte evidenziata.](../media/content-understanding/key-actions-apply-model.png)

2. <span data-ttu-id="81852-229">Nel riquadro **Aggiungi contratto** selezionare il SharePoint contenente la raccolta documenti a cui si desidera applicare il modello.</span><span class="sxs-lookup"><span data-stu-id="81852-229">On the **Add Contract** panel, select the SharePoint site that contains the document library that you want to apply the model to.</span></span> <span data-ttu-id="81852-230">Se il sito non viene visualizzato nell'elenco, usare la casella di ricerca per trovarlo.</span><span class="sxs-lookup"><span data-stu-id="81852-230">If the site does not show in the list, use the search box to find it.</span></span> <span data-ttu-id="81852-231">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="81852-231">Select **Add**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="81852-232">È necessario disporre delle autorizzazioni di *Gestione dell'elenco* o dei diritti di *modifica* per la raccolta documenti a cui si sta applicando il modello.</span><span class="sxs-lookup"><span data-stu-id="81852-232">You must have *Manage List* permissions or *Edit* rights to the document library you are applying the model to.</span></span>

3. <span data-ttu-id="81852-233">Dopo aver selezionato il sito, selezionare la raccolta documenti a cui si desidera applicare il modello.</span><span class="sxs-lookup"><span data-stu-id="81852-233">After you select the site, select the document library to which you want to apply the model.</span></span>

4. <span data-ttu-id="81852-234">Poiché il modello è associato a un tipo di contenuto, quando lo si applica alla raccolta verrà aggiunto il tipo di contenuto e la relativa visualizzazione con le etichette estratte che vengono visualizzate come colonne.</span><span class="sxs-lookup"><span data-stu-id="81852-234">Because the model is associated to a content type, when you apply it to the library it will add the content type and its view with the labels you extracted showing as columns.</span></span> <span data-ttu-id="81852-235">Questa visualizzazione è la visualizzazione predefinita della raccolta per impostazione predefinita, ma è possibile  scegliere di non  impostarla come predefinita selezionando Impostazioni avanzate e deselezionando la casella di controllo Imposta questa nuova visualizzazione come predefinita.</span><span class="sxs-lookup"><span data-stu-id="81852-235">This view is the library's default view by default, but you can optionally choose to have it not be the default view by selecting **Advanced settings** and clearing the **Set this new view as default** check box.</span></span>

5. <span data-ttu-id="81852-236">Selezionare **Aggiungi** per applicare il modello alla raccolta.</span><span class="sxs-lookup"><span data-stu-id="81852-236">Select **Add** to apply the model to the library.</span></span>

6. <span data-ttu-id="81852-237">Nella **sezione Raccolte con questo** modello  della pagina Modelli > contratto verrà visualizzato l'URL del sito SharePoint sito.</span><span class="sxs-lookup"><span data-stu-id="81852-237">On the **Models > Contract** page, in the **Libraries with this model** section, you'll see the URL to the SharePoint site listed.</span></span>

    ![Screenshot della home page contratto che mostra la sezione Librerie con questo modello.](../media/content-understanding/contract-libraries-with-this-model.png)

<span data-ttu-id="81852-239">Dopo aver applicato il modello alla raccolta documenti, è possibile iniziare a caricare documenti nel sito e visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="81852-239">After you apply the model to the document library, you can begin uploading documents to the site and see the results.</span></span>

## <a name="next-step"></a><span data-ttu-id="81852-240">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="81852-240">Next step</span></span>

[<span data-ttu-id="81852-241">Passaggio 2. Usare Microsoft Teams per creare il canale di gestione dei contratti</span><span class="sxs-lookup"><span data-stu-id="81852-241">Step 2. Use Microsoft Teams to create your contract management channel</span></span>](solution-manage-contracts-step2.md)