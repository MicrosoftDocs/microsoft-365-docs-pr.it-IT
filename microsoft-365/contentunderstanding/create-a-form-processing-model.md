---
title: Creare un modello di elaborazione dei moduli
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Creare un modello di elaborazione dei moduli in Microsoft SharePoint Syntex.
ms.openlocfilehash: d71273e416bf7922627e44d9423eaa8903411689
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905847"
---
# <a name="create-a-form-processing-model-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="456a5-103">Creare un modello di elaborazione dei moduli in Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="456a5-103">Create a form processing model in Microsoft SharePoint Syntex</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GnhN]  

</br>

<span data-ttu-id="456a5-104">Con [AI Builder](/ai-builder/overview), una funzionalità di Microsoft PowerApps, gli utenti di SharePoint Syntex possono creare un [modello di elaborazione dei moduli](form-processing-overview.md) direttamente da una raccolta documenti di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="456a5-104">Using [AI Builder](/ai-builder/overview) - a feature in Microsoft PowerApps - SharePoint Syntex users can create a [form processing model](form-processing-overview.md) directly from a SharePoint document library.</span></span> 

<span data-ttu-id="456a5-105">La creazione di un modello di elaborazione dei moduli prevede i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="456a5-105">Creating a form processing model involves the following:</span></span>
 - <span data-ttu-id="456a5-106">Passaggio 1: creare il modello di elaborazione moduli per creare il tipo di contenuto</span><span class="sxs-lookup"><span data-stu-id="456a5-106">Step 1: Create the from processing model to create the content type</span></span>
 - <span data-ttu-id="456a5-107">Passaggio 2: aggiungere e analizzare file di esempio</span><span class="sxs-lookup"><span data-stu-id="456a5-107">Step 2: Add and analyze example files</span></span>
 - <span data-ttu-id="456a5-108">Passaggio 3: selezionare i campi del modulo</span><span class="sxs-lookup"><span data-stu-id="456a5-108">Step 3: Select your form fields</span></span>
 - <span data-ttu-id="456a5-109">Passaggio 4: eseguire il training e il test del modello</span><span class="sxs-lookup"><span data-stu-id="456a5-109">Step 4: Train and test your model</span></span>
 - <span data-ttu-id="456a5-110">Passaggio 5: pubblicare il modello</span><span class="sxs-lookup"><span data-stu-id="456a5-110">Step 5: Publish your model</span></span>
 - <span data-ttu-id="456a5-111">Passaggio 6: usare il modello</span><span class="sxs-lookup"><span data-stu-id="456a5-111">Step 6: Use your model</span></span>

## <a name="requirements"></a><span data-ttu-id="456a5-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="456a5-112">Requirements</span></span>

<span data-ttu-id="456a5-113">È possibile creare un modello di elaborazione dei moduli solo nelle raccolte documenti di SharePoint per le quali è abilitata.</span><span class="sxs-lookup"><span data-stu-id="456a5-113">You can only create a form processing model in SharePoint document libraries for which it is enabled.</span></span> <span data-ttu-id="456a5-114">Se l'elaborazione dei moduli è abilitata, sarà presente l'opzione **AI Builder** **Crea un modello di elaborazione dei moduli** nel menu **Automatizza** nella raccolta documenti.</span><span class="sxs-lookup"><span data-stu-id="456a5-114">If form processing is enabled, you are able to see the **AI Builder** **"Create a form processing model'** under the **Automate** menu in your document library.</span></span>  <span data-ttu-id="456a5-115">Se è necessario abilitare l'elaborazione nella raccolta documenti, contattare l'amministratore di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="456a5-115">If you need processing enabled on your document library, you must contact your SharePoint administrator.</span></span>

 ![Creare un modello di AI Builder](../media/content-understanding/create-ai-builder-model.png)</br>

## <a name="step-1-create-a-form-processing-model"></a><span data-ttu-id="456a5-117">Passaggio 1: creare un modello di elaborazione dei moduli</span><span class="sxs-lookup"><span data-stu-id="456a5-117">Step 1: Create a form processing model</span></span>

<span data-ttu-id="456a5-118">Per creare un modello di elaborazione dei moduli, occorre prima di tutto assegnare un nome al modello, creare e definire il nuovo tipo di contenuto e creare una specifica visualizzazione della raccolta documenti.</span><span class="sxs-lookup"><span data-stu-id="456a5-118">The first step in creating a form processing model is to name it and create the define the new content type and create a new document library view for it.</span></span>

1. <span data-ttu-id="456a5-119">Nella raccolta documenti scegliere **AI Builder**, dal menu **Automatizza**, quindi selezionare **Crea un modello di elaborazione dei moduli**.</span><span class="sxs-lookup"><span data-stu-id="456a5-119">From the document library, select the **Automate** menu, select **AI Builder**, and then select **Create a Form Processing model**.</span></span>

    ![Creare un modello](../media/content-understanding/create-ai-builder-model.png)</br>

2. <span data-ttu-id="456a5-121">Nel riquadro **Nuovo modello di elaborazione dei moduli** digitare un nome per il modello nel campo **Nome**, ad esempio *Ordini di acquisto*.</span><span class="sxs-lookup"><span data-stu-id="456a5-121">In the **New form processing model** pane, in the  **Name** field, type a name for your model (for example, *Purchase Orders*).</span></span>

    ![Nuovo modello di elaborazione dei moduli](../media/content-understanding/new-form-model.png)</br> 

3. <span data-ttu-id="456a5-123">Quando si crea un modello di elaborazione dei moduli, si crea un nuovo tipo di contenuto di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="456a5-123">When you create a form processing model, you create a new SharePoint content type.</span></span> <span data-ttu-id="456a5-124">Un tipo di contenuto di SharePoint rappresenta una categoria di documenti che hanno caratteristiche comuni e condividono una raccolta di colonne o proprietà dei metadati per quel particolare contenuto.</span><span class="sxs-lookup"><span data-stu-id="456a5-124">A SharePoint content type represents a category of documents that have common characteristics and share a collection of columns or metadata properties for that particular content.</span></span> <span data-ttu-id="456a5-125">I tipi di contenuto di SharePoint vengono gestiti tramite la [Raccolta tipi di contenuto]().</span><span class="sxs-lookup"><span data-stu-id="456a5-125">SharePoint Content Types are managed through the [Content types gallery]().</span></span>

    <span data-ttu-id="456a5-126">Selezionare **Impostazioni avanzate** se si vuole associare questo modello a un tipo di contenuto esistente nella Raccolta tipi di contenuto di SharePoint per usarne lo schema.</span><span class="sxs-lookup"><span data-stu-id="456a5-126">Select **Advanced settings** if you want to map this model to an existing content type in the SharePoint Content types gallery to use its schema.</span></span> 

4. <span data-ttu-id="456a5-127">Il modello crea una nuova visualizzazione nella raccolta documenti per i dati estratti.</span><span class="sxs-lookup"><span data-stu-id="456a5-127">Your model creates a new view in your document library for your extracted data.</span></span> <span data-ttu-id="456a5-128">Se non si vuole impostarla come visualizzazione predefinita, deselezionare **Imposta la visualizzazione come predefinita**.</span><span class="sxs-lookup"><span data-stu-id="456a5-128">If you do not want it to the default view, deselect **Set the view as default**.</span></span>

5. <span data-ttu-id="456a5-129">Selezionare **Crea**.</span><span class="sxs-lookup"><span data-stu-id="456a5-129">Select **Create**.</span></span>

## <a name="step-2-add-and-analyze-documents"></a><span data-ttu-id="456a5-130">Passaggio 2: aggiungere e analizzare documenti</span><span class="sxs-lookup"><span data-stu-id="456a5-130">Step 2: Add and analyze documents</span></span>

<span data-ttu-id="456a5-131">Dopo aver creato il nuovo modello di elaborazione dei moduli, nel browser viene aperta una nuova pagina del modello di elaborazione dei moduli di PowerApps AI Builder.</span><span class="sxs-lookup"><span data-stu-id="456a5-131">After you create your new form processing model, your browser opens a new PowerApps AI Builder forms processing model page.</span></span> <span data-ttu-id="456a5-132">In questa pagina è possibile aggiungere e analizzare i documenti di esempio.</span><span class="sxs-lookup"><span data-stu-id="456a5-132">On this page you can add and analyze your example documents.</span></span> </br>

> [!NOTE]
> <span data-ttu-id="456a5-133">Quando si cercano file di esempio da usare, vedere i [requisiti dei documenti di input per il modello di elaborazione moduli e suggerimenti per l'ottimizzazione](/ai-builder/form-processing-model-requirements).</span><span class="sxs-lookup"><span data-stu-id="456a5-133">When looking for example files to use, see the [form processing model input document requirements and optimization tips](/ai-builder/form-processing-model-requirements).</span></span> 

   ![Power Apps AI Builder](../media/content-understanding/powerapps.png)</br> 
 
1. <span data-ttu-id="456a5-135">Selezionare **Aggiungi documenti** per iniziare ad aggiungere documenti di esempio analizzati per determinare le coppie di valori denominate che è possibile estrarre.</span><span class="sxs-lookup"><span data-stu-id="456a5-135">Select **Add documents** to begin adding example documents analyzed to determine the named value pairs that can be extracted.</span></span> <span data-ttu-id="456a5-136">È quindi possibile scegliere **Carica dalla risorsa di archiviazione locale**, **SharePoint** o **Archiviazione BLOB di Azure**.</span><span class="sxs-lookup"><span data-stu-id="456a5-136">You can then choose either **Upload from local storage**, **SharePoint**, or **Azure Blob storage**.</span></span> <span data-ttu-id="456a5-137">È necessario usare almeno cinque file per il training.</span><span class="sxs-lookup"><span data-stu-id="456a5-137">You need to use at least five files for training.</span></span>

2. <span data-ttu-id="456a5-138">Dopo aver aggiunto i file, selezionare **Analizza** per verificare se esistono informazioni comuni a tutti i file.</span><span class="sxs-lookup"><span data-stu-id="456a5-138">After adding files, select **Analyze** to check for any information common is all files.</span></span> <span data-ttu-id="456a5-139">Questo processo potrebbe richiedere alcuni minuti.</span><span class="sxs-lookup"><span data-stu-id="456a5-139">This may take several minutes to complete.</span></span></br> 
 
    ![Analizzare i file](../media/content-understanding/analyze.png)</br> 

3. <span data-ttu-id="456a5-141">Terminata l'analisi dei file, nella pagina **Selezionare i campi del modulo da salvare** selezionare il file per visualizzare i campi rilevati.</span><span class="sxs-lookup"><span data-stu-id="456a5-141">After the files have been analyzed, in the **Select the form fields you want to save** page select the file to view the detected fields.</span></span></br>

    ![Selezionare i campi del modulo](../media/content-understanding/select-form-fields.png)</br> 

## <a name="step-3-select-your-form-fields"></a><span data-ttu-id="456a5-143">Passaggio 3: selezionare i campi del modulo</span><span class="sxs-lookup"><span data-stu-id="456a5-143">Step 3: Select your form fields</span></span>

<span data-ttu-id="456a5-144">Una volta analizzati i documenti per individuare i campi, è possibile vedere i campi rilevati e identificare quelli da salvare.</span><span class="sxs-lookup"><span data-stu-id="456a5-144">After analyzing the documents for fields, you can now see the fields that were found, and identify the ones that you want to save.</span></span> <span data-ttu-id="456a5-145">I campi salvati vengono visualizzati come colonne nella visualizzazione della raccolta documenti del modello e mostrano i valori estratti da ogni documento.</span><span class="sxs-lookup"><span data-stu-id="456a5-145">Saved fields display as columns in your model's document library view and show the values extracted from each document.</span></span>

1. <span data-ttu-id="456a5-146">Nella pagina successiva viene visualizzato uno dei file di esempio e vengono evidenziati tutti i campi comuni che sono stati rilevati automaticamente dal sistema.</span><span class="sxs-lookup"><span data-stu-id="456a5-146">The next page displays one of your sample files and will highlight all common fields that were automatically detected by the system.</span></span> </br>

    ![Pagina Seleziona campi](../media/content-understanding/select-fields-page.png)</br> 

2. <span data-ttu-id="456a5-148">Selezionare i campi a salvare e selezionare la casella di controllo per confermare la selezione.</span><span class="sxs-lookup"><span data-stu-id="456a5-148">Select the fields that you want to save and select the checkbox to confirm your selection.</span></span> <span data-ttu-id="456a5-149">Ad esempio, nel modello di ordine di acquisto selezionare i campi *Data*, *Ordine d'acquisto* e *Totale*.</span><span class="sxs-lookup"><span data-stu-id="456a5-149">For example, in the Purchase Order model, choose to select the *Date*, *PO*, and *Total* fields.</span></span>  <span data-ttu-id="456a5-150">Se si vuole, è possibile anche decidere di rinominare un campo.</span><span class="sxs-lookup"><span data-stu-id="456a5-150">Note that you can also choose to rename a field if you choose.</span></span> </br>

    ![Selezionare il numero dell'ordine d'acquisto](../media/content-understanding/po.png)</br> 

3. <span data-ttu-id="456a5-152">Se un campo non è stato rilevato dall'analisi, è comunque possibile scegliere di aggiungerlo.</span><span class="sxs-lookup"><span data-stu-id="456a5-152">If a field was not detected by analysis, you can still choose to add it.</span></span> <span data-ttu-id="456a5-153">Evidenziare le informazioni da estrarre, quindi immettere il nome desiderato nella casella relativa al nome.</span><span class="sxs-lookup"><span data-stu-id="456a5-153">Highlight the information you want to extract, and in the name box type in the name you want.</span></span> <span data-ttu-id="456a5-154">Selezionare quindi la casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="456a5-154">Then select the check box.</span></span> <span data-ttu-id="456a5-155">Tenere presente che è necessario confermare i campi non rilevati nei file di esempio rimanenti.</span><span class="sxs-lookup"><span data-stu-id="456a5-155">Note that you need to confirm undetected fields in your remaining sample files.</span></span>

4. <span data-ttu-id="456a5-156">Dopo aver selezionato i campi da salvare, fare clic su **Conferma campi**.</span><span class="sxs-lookup"><span data-stu-id="456a5-156">Click **Confirm fields** after you have selected the fields that you want to save.</span></span> </br>
 
    ![Conferma campi dopo aver selezionato i campi](../media/content-understanding/confirm-fields.png)</br> 
 
5. <span data-ttu-id="456a5-158">Nella pagina **Selezionare i campi del modulo da salvare** viene visualizzato il numero di campi selezionati.</span><span class="sxs-lookup"><span data-stu-id="456a5-158">On the **Select the form fields you want to save** page, it shows the number of fields you have selected.</span></span> <span data-ttu-id="456a5-159">Scegliere **Fatto**.</span><span class="sxs-lookup"><span data-stu-id="456a5-159">Select **Done**.</span></span>

## <a name="step-4-train-and-test-your-model"></a><span data-ttu-id="456a5-160">Passaggio 4: eseguire il training e il test del modello</span><span class="sxs-lookup"><span data-stu-id="456a5-160">Step 4: Train and test your model</span></span>

<span data-ttu-id="456a5-161">Dopo aver selezionato i campi da salvare, nella pagina **Riepilogo modelli** è possibile eseguire il training e il test del modello.</span><span class="sxs-lookup"><span data-stu-id="456a5-161">After selecting the fields you want to save, the **Model Summary** page lets you train and test your model.</span></span>

1. <span data-ttu-id="456a5-162">Nella pagina **Riepilogo modelli** i campi salvati vengono visualizzati nella sezione **Campi selezionati**.</span><span class="sxs-lookup"><span data-stu-id="456a5-162">On the **Model Summary** page, the saved fields will show in the **Selected fields** section.</span></span> <span data-ttu-id="456a5-163">Selezionare **Avvia training** per avviare il training sul file di esempio.</span><span class="sxs-lookup"><span data-stu-id="456a5-163">Select **Train** to begin training on your example files.</span></span> <span data-ttu-id="456a5-164">Tenere presente che questo processo potrebbe richiedere alcuni minuti.</span><span class="sxs-lookup"><span data-stu-id="456a5-164">Note that this may take a few minutes to complete.</span></span></br>

     ![Training dei file selezionati](../media/content-understanding/select-fields-train.png)</br> 

2. <span data-ttu-id="456a5-166">Quando viene indicato che il training è terminato, selezionare **Vai alla pagina Dettagli**.</span><span class="sxs-lookup"><span data-stu-id="456a5-166">When you see the notification that training has completed, select **Go to details page**.</span></span> 

3. <span data-ttu-id="456a5-167">Nella pagina **Dettagli modello** si può decidere di testare il funzionamento del modello selezionando **Test rapido**.</span><span class="sxs-lookup"><span data-stu-id="456a5-167">On the **Model details** page, you can choose to test how your model works by selecting **Quick test**.</span></span> <span data-ttu-id="456a5-168">Questo consente di trascinare i file nella pagina e verificare se i campi vengono rilevati.</span><span class="sxs-lookup"><span data-stu-id="456a5-168">This lets you drag and drop files to the page and see if the fields are detected.</span></span>

    ![Confermare i campi](../media/content-understanding/select-fields-train.png)</br> 

2. <span data-ttu-id="456a5-170">Quando viene indicato che il training è terminato, selezionare **Vai alla pagina Dettagli**.</span><span class="sxs-lookup"><span data-stu-id="456a5-170">When you see the notification that training has completed, select **Go to details page**.</span></span> 

3. <span data-ttu-id="456a5-171">Nella pagina **Dettagli modello**, scegliere di testare il funzionamento del modello selezionando **Test rapido**.</span><span class="sxs-lookup"><span data-stu-id="456a5-171">On the **Model details** page, choose to test how your model works by selecting **Quick test**.</span></span> <span data-ttu-id="456a5-172">Questo consente di trascinare i file nella pagina e verificare se i campi vengono rilevati.</span><span class="sxs-lookup"><span data-stu-id="456a5-172">This lets you drag and drop files to the page and see if the fields are detected.</span></span>

## <a name="step-5-publish-your-model"></a><span data-ttu-id="456a5-173">Passaggio 5: pubblicare il modello</span><span class="sxs-lookup"><span data-stu-id="456a5-173">Step 5: Publish your model</span></span>

1. <span data-ttu-id="456a5-174">Se i risultati del modello sono soddisfacenti, selezionare **Pubblica** per metterlo a disposizione.</span><span class="sxs-lookup"><span data-stu-id="456a5-174">If you are satisfied with the results of your model, select **Publish** to make it available for use.</span></span>

2. <span data-ttu-id="456a5-175">Dopo avere pubblicato il modello, selezionare **Usa modello**.</span><span class="sxs-lookup"><span data-stu-id="456a5-175">After the model is published, select **Use model**.</span></span> <span data-ttu-id="456a5-176">In questo modo viene creato un flusso di PowerAutomate che può essere eseguito nella raccolta documenti di SharePoint ed estrae i campi identificati nel modello, quindi selezionare **Crea flusso**.</span><span class="sxs-lookup"><span data-stu-id="456a5-176">This creates a PowerAutomate flow that can run in your SharePoint document library and extracts the fields that have been identified in the model, then select **Create Flow**.</span></span>
  
3. <span data-ttu-id="456a5-177">Al termine, viene visualizzato il messaggio **Il flusso è stato creato**.</span><span class="sxs-lookup"><span data-stu-id="456a5-177">When completed, you will see the message **Your flow has been successfully created**.</span></span>
 
## <a name="step-6-use-your-model"></a><span data-ttu-id="456a5-178">Passaggio 6: usare il modello</span><span class="sxs-lookup"><span data-stu-id="456a5-178">Step 6: Use your model</span></span>

<span data-ttu-id="456a5-179">Dopo aver pubblicato il modello e avere creato il relativo flusso di PowerAutomate, è possibile usare il modello nella raccolta documenti di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="456a5-179">After publishing your model and creating it's PowerAutomate flow, you can use your model in your SharePoint document library.</span></span>

1. <span data-ttu-id="456a5-180">Dopo la pubblicazione del modello, selezionare **Vai a SharePoint** per passare alla raccolta documenti.</span><span class="sxs-lookup"><span data-stu-id="456a5-180">After publishing your model, select **Go to SharePoint** to go to your document library.</span></span>

2. <span data-ttu-id="456a5-181">Nella visualizzazione modello della raccolta documenti notare che i campi selezionati sono visualizzati in colonne.</span><span class="sxs-lookup"><span data-stu-id="456a5-181">In the document library model view, notice that the fields you selected now display as columns.</span></span></br>

    ![Modello della raccolta documenti applicato](../media/content-understanding/doc-lib-view.png)</br> 

3. <span data-ttu-id="456a5-183">Il collegamento alle informazioni accanto a **Documenti** indica che alla raccolta documenti è applicato un modello di elaborazione dei moduli.</span><span class="sxs-lookup"><span data-stu-id="456a5-183">Notice that the information link next to **Documents** notes that a forms processing model is applied to this document library.</span></span>

    ![Pulsante Informazioni](../media/content-understanding/info-button.png)</br>  

4. <span data-ttu-id="456a5-185">Caricare i file nella raccolta documenti.</span><span class="sxs-lookup"><span data-stu-id="456a5-185">Upload files to your document library.</span></span> <span data-ttu-id="456a5-186">Qualsiasi file che il modello identifica come corrispondente al suo tipo di contenuto elenca i file nella visualizzazione e mostra i dati estratti nelle colonne.</span><span class="sxs-lookup"><span data-stu-id="456a5-186">Any files that the model identifies as it's content type lists the files in your view and displays the extracted data in the columns.</span></span></br>

    ![Fatto](../media/content-understanding/doc-lib-done.png)</br>  

## <a name="see-also"></a><span data-ttu-id="456a5-188">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="456a5-188">See Also</span></span>
  
[<span data-ttu-id="456a5-189">Documentazione di Power Automate</span><span class="sxs-lookup"><span data-stu-id="456a5-189">Power Automate documentation</span></span>](/power-automate/)

[<span data-ttu-id="456a5-190">Formazione: migliorare le prestazioni aziendali con AI Builder</span><span class="sxs-lookup"><span data-stu-id="456a5-190">Training: Improve business performance with AI Builder</span></span>](/learn/paths/improve-business-performance-ai-builder/?source=learn)