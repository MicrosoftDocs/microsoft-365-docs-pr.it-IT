---
title: Creare un modello di elaborazione dei moduli (anteprima)
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
description: Creare un modello di elaborazione dei moduli in Project Cortex.
ms.openlocfilehash: cec3b9a8b1b58237c4beb745377709d4938a2dba
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950145"
---
# <a name="create-a-form-processing-model-preview"></a><span data-ttu-id="9d1f4-103">Creare un modello di elaborazione dei moduli (anteprima)</span><span class="sxs-lookup"><span data-stu-id="9d1f4-103">Create a form processing model (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="9d1f4-104">Il contenuto di questo articolo è relativo all'anteprima privata di Project Cortex.</span><span class="sxs-lookup"><span data-stu-id="9d1f4-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="9d1f4-105">[Per ulteriori informazioni, vedere Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="9d1f4-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="9d1f4-106">Utilizzo di [ai Builder](https://docs.microsoft.com/ai-builder/overview) -caratteristica di Microsoft PowerApps-Project Cortex gli utenti possono creare un [modello di elaborazione dei moduli](form-processing-overview.md) direttamente da una raccolta documenti di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="9d1f4-106">Using [AI Builder](https://docs.microsoft.com/ai-builder/overview) - a feature in Microsoft PowerApps - Project Cortex users can create a [form processing model](form-processing-overview.md) directly from a SharePoint document library.</span></span> 

<span data-ttu-id="9d1f4-107">La creazione di un modello di elaborazione dei moduli comporta quanto segue:</span><span class="sxs-lookup"><span data-stu-id="9d1f4-107">Creating a form processing model involves the following:</span></span>
 - <span data-ttu-id="9d1f4-108">Passaggio 1: creare il modello di elaborazione da per creare il tipo di contenuto</span><span class="sxs-lookup"><span data-stu-id="9d1f4-108">Step 1: Create the from processing model to create the content type</span></span>
 - <span data-ttu-id="9d1f4-109">Passaggio 2: aggiungere e analizzare file di esempio</span><span class="sxs-lookup"><span data-stu-id="9d1f4-109">Step 2: Add and analyze example files</span></span>
 - <span data-ttu-id="9d1f4-110">Passaggio 3: selezionare i campi del modulo</span><span class="sxs-lookup"><span data-stu-id="9d1f4-110">Step 3: Select your form fields</span></span>
 - <span data-ttu-id="9d1f4-111">Passaggio 4: formare e testare il modello</span><span class="sxs-lookup"><span data-stu-id="9d1f4-111">Step 4: Train and test your model</span></span>
 - <span data-ttu-id="9d1f4-112">Passaggio 5: pubblicare il modello</span><span class="sxs-lookup"><span data-stu-id="9d1f4-112">Step 5: Publish your model</span></span>
 - <span data-ttu-id="9d1f4-113">Passaggio 6: utilizzare il modello</span><span class="sxs-lookup"><span data-stu-id="9d1f4-113">Step 6: Use your model</span></span>


## <a name="requirements"></a><span data-ttu-id="9d1f4-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9d1f4-114">Requirements</span></span>

<span data-ttu-id="9d1f4-115">È possibile creare un modello di elaborazione dei moduli solo nelle raccolte documenti di SharePoint in cui è abilitata.</span><span class="sxs-lookup"><span data-stu-id="9d1f4-115">You can only create a form processing model in SharePoint document libraries in which it is enabled.</span></span> <span data-ttu-id="9d1f4-116">Se l'elaborazione dei moduli è abilitata, sarà possibile visualizzare il **Generatore di ai** **"creare un modello di elaborazione dei moduli"** nel menu **automatizza** nella raccolta documenti.</span><span class="sxs-lookup"><span data-stu-id="9d1f4-116">If form processing is enabled, you will be able to see the **AI Builder** **"Create a form processing model'** under the **Automate** menu in your document library.</span></span>  <span data-ttu-id="9d1f4-117">Se è necessario l'elaborazione abilitata nella raccolta documenti, contattare l'amministratore.</span><span class="sxs-lookup"><span data-stu-id="9d1f4-117">If you need from processing enabled on your document library, contact your admin.</span></span>

 ![Creare un modello AI Builder](../media/content-understanding/create-ai-builder-model.png)</br>


## <a name="step-1-create-a-form-processing-model"></a><span data-ttu-id="9d1f4-119">Passaggio 1: creare un modello di elaborazione dei moduli</span><span class="sxs-lookup"><span data-stu-id="9d1f4-119">Step 1: Create a Form Processing model</span></span>

<span data-ttu-id="9d1f4-120">Il primo passaggio per la creazione di un modello di elaborazione dei moduli consiste nel denominarlo per creare il nuovo tipo di contenuto e creare una nuova visualizzazione della raccolta documenti.</span><span class="sxs-lookup"><span data-stu-id="9d1f4-120">The first step in creating a form processing model is to name it to create the define the new content type and create a new document library view for it.</span></span>

1. <span data-ttu-id="9d1f4-121">Nella raccolta documenti, selezionare il menu **automatizza** , selezionare Generatore di **ai**e quindi fare clic su **Crea modello di elaborazione del modulo**.</span><span class="sxs-lookup"><span data-stu-id="9d1f4-121">In your document library, select the **Automate** menu, select **AI Builder**, and then select **Create a Form Processing model**.</span></span>

    ![Creare un modello AI Builder](../media/content-understanding/create-ai-builder-model.png)</br>
2. <span data-ttu-id="9d1f4-123">Nel riquadro **nuovo modello di elaborazione del modulo** , nel campo  **nome** , digitare un nome per il modello (ad esempio, *ordini di acquisto*).</span><span class="sxs-lookup"><span data-stu-id="9d1f4-123">In the **New form processing model** pane, in the  **Name** field, type a name for your model (for example, *Purchase Orders*).</span></span>

    ![Nuovo modello di elaborazione dei moduli](../media/content-understanding/new-form-model.png)</br> 

3. <span data-ttu-id="9d1f4-125">Quando si crea un modello di elaborazione del modulo, si crea un nuovo tipo di contenuto di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="9d1f4-125">When you create a form processing model, you are creating a new SharePoint content type.</span></span> <span data-ttu-id="9d1f4-126">Un tipo di contenuto di SharePoint rappresenta una categoria di documenti con caratteristiche comuni e la condivisione di una raccolta di colonne o proprietà dei metadati per il contenuto specifico.</span><span class="sxs-lookup"><span data-stu-id="9d1f4-126">A SharePoint content type represents a category of documents that have common characteristics and share a collection of columns or metadata properties for that particular content.</span></span> <span data-ttu-id="9d1f4-127">I tipi di contenuto di SharePoint vengono gestiti tramite la [raccolta tipi di contenuto]().</span><span class="sxs-lookup"><span data-stu-id="9d1f4-127">SharePoint Content Types are managed through the [Content types gallery]().</span></span>

    <span data-ttu-id="9d1f4-128">Selezionare **Impostazioni avanzate** se si desidera eseguire il mapping di questo modello a un tipo di contenuto esistente nella raccolta tipi di contenuto di SharePoint per utilizzarne lo schema.</span><span class="sxs-lookup"><span data-stu-id="9d1f4-128">Select **Advanced settings** if you want to map this model to an existing content type in the SharePoint Content types gallery to use its schema.</span></span> 

4. <span data-ttu-id="9d1f4-129">Il modello creerà una nuova visualizzazione nella raccolta documenti per i dati estratti.</span><span class="sxs-lookup"><span data-stu-id="9d1f4-129">Your model will create a new view in your document library for your extracted data.</span></span> <span data-ttu-id="9d1f4-130">Se non si desidera che venga visualizzata la visualizzazione predefinita, deselezionare **imposta la visualizzazione come predefinita**.</span><span class="sxs-lookup"><span data-stu-id="9d1f4-130">If you do not want it to the default view, deselect **Set the view as default**.</span></span>
5. <span data-ttu-id="9d1f4-131">Selezionare **Crea**.</span><span class="sxs-lookup"><span data-stu-id="9d1f4-131">Select **Create**.</span></span>


## <a name="step-2-add-and-analyze-documents"></a><span data-ttu-id="9d1f4-132">Passaggio 2: aggiungere e analizzare documenti</span><span class="sxs-lookup"><span data-stu-id="9d1f4-132">Step 2: Add and analyze documents</span></span>

<span data-ttu-id="9d1f4-133">Dopo aver creato il nuovo modello di elaborazione del modulo, nel browser verrà aperta una nuova pagina del modello di elaborazione moduli di PowerApps AI Builder.</span><span class="sxs-lookup"><span data-stu-id="9d1f4-133">After you create your new form processing model, your browser will open a new PowerApps AI Builder forms processing model page.</span></span> <span data-ttu-id="9d1f4-134">In questa pagina è possibile aggiungere e analizzare i documenti di esempio.</span><span class="sxs-lookup"><span data-stu-id="9d1f4-134">On this page you can add and analyze your example documents.</span></span> </br>

> [!Note]
> <span data-ttu-id="9d1f4-135">Quando si cercano file di esempio da utilizzare, vedere il [modello di elaborazione dei moduli di input e suggerimenti](https://docs.microsoft.com/ai-builder/form-processing-model-requirements)per l'ottimizzazione.</span><span class="sxs-lookup"><span data-stu-id="9d1f4-135">When looking for example files to use, see the [form processing model input document requirements and optimization tips](https://docs.microsoft.com/ai-builder/form-processing-model-requirements).</span></span> 

   ![Power Apps AI Builder](../media/content-understanding/powerapps.png)</br> 
 

1. <span data-ttu-id="9d1f4-137">Fare clic su **Aggiungi documenti** per iniziare ad aggiungere documenti di esempio analizzati per determinare le coppie di valori denominabili che è possibile estrarre.</span><span class="sxs-lookup"><span data-stu-id="9d1f4-137">Click **Add documents** to begin adding example documents that are analyzed to determine what named value pairs can be extracted.</span></span> <span data-ttu-id="9d1f4-138">È possibile scegliere **carica da archiviazione locale**, **SharePoint**o **archiviazione BLOB di Azure**.</span><span class="sxs-lookup"><span data-stu-id="9d1f4-138">You can choose either **Upload from local storage**, **SharePoint**, or **Azure Blob storage**.</span></span> <span data-ttu-id="9d1f4-139">Sarà necessario utilizzare almeno cinque file per la formazione.</span><span class="sxs-lookup"><span data-stu-id="9d1f4-139">You will need to use at least five files for training.</span></span>
2. <span data-ttu-id="9d1f4-140">Dopo aver aggiunto i file, selezionare **Analyze** per controllare che tutte le informazioni comuni siano tutti i file.</span><span class="sxs-lookup"><span data-stu-id="9d1f4-140">After adding your files, select **Analyze** to check for any information that is common is all files.</span></span> <span data-ttu-id="9d1f4-141">Tenere presente che potrebbero essere necessari alcuni minuti per il completamento.</span><span class="sxs-lookup"><span data-stu-id="9d1f4-141">Note that this may take several minutes to complete.</span></span></br> 
 
    ![Analizzare i file](../media/content-understanding/analyze.png)</br> 

3. <span data-ttu-id="9d1f4-143">Una volta analizzati, nella pagina **selezionare i campi del modulo che si desidera salvare** fare clic sul file per visualizzare i campi rilevati.</span><span class="sxs-lookup"><span data-stu-id="9d1f4-143">After they have been analyzed, in the **Select the form fields you want to save** page, click the file to see the fields that were detected.</span></span></br>

    ![Seleziona campi modulo](../media/content-understanding/select-form-fields.png)</br> 

## <a name="step-3-select-your-form-fields"></a><span data-ttu-id="9d1f4-145">Passaggio 3: selezionare i campi del modulo</span><span class="sxs-lookup"><span data-stu-id="9d1f4-145">Step 3: Select your form fields</span></span>

<span data-ttu-id="9d1f4-146">Dopo aver analizzato i documenti per i campi, è ora possibile vedere quali campi sono stati trovati e quali si desidera salvare.</span><span class="sxs-lookup"><span data-stu-id="9d1f4-146">After analyzing your documents for fields, you can now see which fields were found, and which ones you want to save.</span></span> <span data-ttu-id="9d1f4-147">I campi salvati verranno visualizzati come colonne nella visualizzazione raccolta documenti del modello e verranno visualizzati i valori estratti da ogni documento.</span><span class="sxs-lookup"><span data-stu-id="9d1f4-147">Saved fields will display as columns in your model's document library view and will show the values extracted from each document.</span></span>

1. <span data-ttu-id="9d1f4-148">Nella pagina successiva verrà visualizzato uno dei file di esempio e verranno evidenziati tutti i campi comuni che sono stati rilevati automaticamente dal sistema.</span><span class="sxs-lookup"><span data-stu-id="9d1f4-148">The next page will display one of your sample files and will highlight all common fields that were automatically detected by the system.</span></span> </br>

    ![Seleziona campi modulo](../media/content-understanding/select-fields-page.png)</br> 

2. <span data-ttu-id="9d1f4-150">Selezionare i campi che si desidera salvare e selezionare la casella di controllo per confermare la selezione.</span><span class="sxs-lookup"><span data-stu-id="9d1f4-150">Select the fields you want to save, and select the checkbox to confirm your selection.</span></span> <span data-ttu-id="9d1f4-151">Ad esempio, nel modello ordine di acquisto è possibile scegliere di selezionare i campi *Data*, *po*e *totale* .</span><span class="sxs-lookup"><span data-stu-id="9d1f4-151">For example, in the Purchase Order model, you can choose to select the *Date*, *PO*, and *Total* fields.</span></span>  <span data-ttu-id="9d1f4-152">Si noti che è anche possibile scegliere di rinominare un campo se si sceglie.</span><span class="sxs-lookup"><span data-stu-id="9d1f4-152">Note that you can also choose to rename a field if you choose.</span></span> </br>

    ![Seleziona PO #](../media/content-understanding/po.png)</br> 

3. <span data-ttu-id="9d1f4-154">Se un campo non è stato rilevato dall'analisi, è comunque possibile scegliere di aggiungerlo.</span><span class="sxs-lookup"><span data-stu-id="9d1f4-154">If a field was not detected by analysis, you can still choose to add it.</span></span> <span data-ttu-id="9d1f4-155">Evidenziare le informazioni che si desidera estrarre e nella casella nome digitare il nome che si desidera assegnare.</span><span class="sxs-lookup"><span data-stu-id="9d1f4-155">Highlight the information you want to extract, and in the name box type in the name you want to give it.</span></span> <span data-ttu-id="9d1f4-156">Selezionare quindi la casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="9d1f4-156">Then select the check.</span></span> <span data-ttu-id="9d1f4-157">Tenere presente che è necessario confermare i campi non rilevati nei file di esempio rimanenti.</span><span class="sxs-lookup"><span data-stu-id="9d1f4-157">Note that you will need to confirm undetected fields in your remaining example files.</span></span>
4. <span data-ttu-id="9d1f4-158">Dopo aver selezionato i campi che si desidera salvare, fare clic su **Conferma campi** .</span><span class="sxs-lookup"><span data-stu-id="9d1f4-158">Click **Confirm fields** after you have selected the fields you want to save.</span></span> </br>
 
    ![Conferma campi](../media/content-understanding/confirm-fields.png)</br> 
 
5. <span data-ttu-id="9d1f4-160">Nella pagina **selezionare i campi del modulo che si desidera salvare** , verrà visualizzato il numero di campi selezionati.</span><span class="sxs-lookup"><span data-stu-id="9d1f4-160">On the **Select the form fields you want to save** page, it will show the number of fields you have selected.</span></span> <span data-ttu-id="9d1f4-161">Scegliere **Fine**.</span><span class="sxs-lookup"><span data-stu-id="9d1f4-161">Select **Done**.</span></span>

## <a name="step-4-train-and-test-your-model"></a><span data-ttu-id="9d1f4-162">Passaggio 4: formare e testare il modello</span><span class="sxs-lookup"><span data-stu-id="9d1f4-162">Step 4: Train and test your model</span></span>

<span data-ttu-id="9d1f4-163">Dopo aver selezionato i campi che si desidera salvare, la pagina di **Riepilogo del modello** consentirà di formare e testare il modello.</span><span class="sxs-lookup"><span data-stu-id="9d1f4-163">After selecting the fields you want to save, the **Model Summary** page will let you train and test your model.</span></span>

1. <span data-ttu-id="9d1f4-164">Nella pagina **Riepilogo modello** verranno visualizzati i campi salvati nella sezione **campi selezionati** .</span><span class="sxs-lookup"><span data-stu-id="9d1f4-164">On the **Model Summary** page, the saved fields will show in the **Selected fields** section.</span></span> <span data-ttu-id="9d1f4-165">Selezionare **treno** per iniziare a eseguire la formazione sui file di esempio.</span><span class="sxs-lookup"><span data-stu-id="9d1f4-165">Select **Train** to begin training on your example files.</span></span> <span data-ttu-id="9d1f4-166">Tenere presente che potrebbero essere necessari alcuni minuti per il completamento.</span><span class="sxs-lookup"><span data-stu-id="9d1f4-166">Note that this may take a few minutes to complete.</span></span></br>
    <span data-ttu-id="9d1f4-167">![Conferma campi](../media/content-understanding/select-fields-train.png)</span><span class="sxs-lookup"><span data-stu-id="9d1f4-167">![Confirm fields](../media/content-understanding/select-fields-train.png)</span></span></br> 
2. <span data-ttu-id="9d1f4-168">Quando viene visualizzata la notifica che la formazione è stata completata, selezionare **Vai alla pagina dei dettagli**.</span><span class="sxs-lookup"><span data-stu-id="9d1f4-168">When you see the notification that training has completed, select **Go to details page**.</span></span> 
3. <span data-ttu-id="9d1f4-169">Nella pagina **Dettagli modello** è possibile scegliere di testare il funzionamento del modello selezionando **test rapido**.</span><span class="sxs-lookup"><span data-stu-id="9d1f4-169">On the **Model details** page, you can choose to test how your model works by selecting **Quick test**.</span></span> <span data-ttu-id="9d1f4-170">In questo modo è possibile trascinare i file nella pagina e verificare se i campi sono stati rilevati.</span><span class="sxs-lookup"><span data-stu-id="9d1f4-170">This lets you drag and drop files to the page and see if the fields are detected.</span></span>

## <a name="step-5-publish-your-model"></a><span data-ttu-id="9d1f4-171">Passaggio 5: pubblicare il modello</span><span class="sxs-lookup"><span data-stu-id="9d1f4-171">Step 5: Publish your model</span></span>



1. <span data-ttu-id="9d1f4-172">Se si è soddisfatti dei risultati del modello selezionato, fare clic su **pubblica** per renderlo disponibile per l'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="9d1f4-172">If you are satisfied with the results of your model, select **Publish** to make it available for use.</span></span>
2. <span data-ttu-id="9d1f4-173">Dopo la pubblicazione del modello, selezionare **Usa modello**.</span><span class="sxs-lookup"><span data-stu-id="9d1f4-173">After the model published, select **Use model**.</span></span> <span data-ttu-id="9d1f4-174">In questo modo viene creato un flusso PowerAutomate che verrà eseguito nella raccolta documenti di SharePoint e verranno estratti i campi che sono stati identificati nel modello.</span><span class="sxs-lookup"><span data-stu-id="9d1f4-174">This creates a PowerAutomate flow that will run in your SharePoint document library and will extract the fields that have been identified in the model.</span></span> <span data-ttu-id="9d1f4-175">Selezionare **Crea flusso**.</span><span class="sxs-lookup"><span data-stu-id="9d1f4-175">Select **Create Flow**.</span></span>  
3. <span data-ttu-id="9d1f4-176">Al termine, verrà visualizzato il messaggio che il **flusso è stato creato correttamente**.</span><span class="sxs-lookup"><span data-stu-id="9d1f4-176">When completed, you will see the message **Your flow has been successfully created**.</span></span>
 
 
## <a name="step-6-use-your-model"></a><span data-ttu-id="9d1f4-177">Passaggio 6: utilizzare il modello</span><span class="sxs-lookup"><span data-stu-id="9d1f4-177">Step 6: Use your model</span></span>

<span data-ttu-id="9d1f4-178">Dopo la pubblicazione del modello e la creazione del flusso di PowerAutomate, è possibile utilizzare il modello nella raccolta documenti di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="9d1f4-178">After publishing your model and creating it's PowerAutomate flow, you can use your model in your SharePoint document library.</span></span>

1. <span data-ttu-id="9d1f4-179">Dopo aver pubblicato il modello, selezionare **Vai a SharePoint** per andare alla raccolta documenti.</span><span class="sxs-lookup"><span data-stu-id="9d1f4-179">After publishing your model , select **Go to SharePoint** to go to your document library.</span></span>
2. <span data-ttu-id="9d1f4-180">Nella visualizzazione modello raccolta documenti, tenere presente che i campi selezionati vengono visualizzati come colonne.</span><span class="sxs-lookup"><span data-stu-id="9d1f4-180">On your document library model view, notice that the fields you selected now display as columns.</span></span></br>

    ![Raccolta documenti con modello applicato](../media/content-understanding/doc-lib-view.png)</br> 

    <span data-ttu-id="9d1f4-182">Si noti inoltre che il collegamento alle informazioni accanto a **documenti** noterà che un modello di elaborazione dei moduli viene applicato a questa raccolta documenti.</span><span class="sxs-lookup"><span data-stu-id="9d1f4-182">Also notice that the information link next to **Documents** will note that a forms processing model is applied to this document library.</span></span>

    ![Estratto](../media/content-understanding/info-button.png)</br>  

3. <span data-ttu-id="9d1f4-184">Caricare i file nella raccolta documenti.</span><span class="sxs-lookup"><span data-stu-id="9d1f4-184">Upload files to your document library.</span></span> <span data-ttu-id="9d1f4-185">Tutti i file identificati dal modello come tipo di contenuto consentiranno di elencare i file nella visualizzazione e verranno visualizzati i dati estratti nelle colonne.</span><span class="sxs-lookup"><span data-stu-id="9d1f4-185">Any files that the model identifies as it's content type will list the files in your view, and will display the extracted data in the columns.</span></span></br>

    ![Estratto](../media/content-understanding/doc-lib-done.png)</br>  



## <a name="see-also"></a><span data-ttu-id="9d1f4-187">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9d1f4-187">See Also</span></span>
  
[<span data-ttu-id="9d1f4-188">Documentazione su Power automatizzate</span><span class="sxs-lookup"><span data-stu-id="9d1f4-188">Power Automate documentation</span></span>](https://docs.microsoft.com/power-automate/)</br>
[<span data-ttu-id="9d1f4-189">Formazione: migliorare le prestazioni aziendali con AI Builder</span><span class="sxs-lookup"><span data-stu-id="9d1f4-189">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>




