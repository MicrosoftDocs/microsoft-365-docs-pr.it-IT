---
title: Creare un modello di elaborazione dei moduli
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
description: Creare un modello di elaborazione dei moduli in Microsoft SharePoint Syntex.
ms.openlocfilehash: aed918d899fe7c5e3c49b733d2411c178e9b98d0
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087692"
---
# <a name="create-a-form-processing-model-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="77ae4-103">Creare un modello di elaborazione dei moduli in Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="77ae4-103">Create a form processing model in Microsoft SharePoint Syntex</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GnhN]  

</br>

<span data-ttu-id="77ae4-104">Con [AI Builder](https://docs.microsoft.com/ai-builder/overview), una funzionalità di Microsoft PowerApps, gli utenti di SharePoint Syntex possono creare un [modello di elaborazione dei moduli](form-processing-overview.md) direttamente da una raccolta documenti di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="77ae4-104">Using [AI Builder](https://docs.microsoft.com/ai-builder/overview) - a feature in Microsoft PowerApps - SharePoint Syntex users can create a [form processing model](form-processing-overview.md) directly from a SharePoint document library.</span></span> 

<span data-ttu-id="77ae4-105">La creazione di un modello di elaborazione dei moduli prevede i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="77ae4-105">Creating a form processing model involves the following:</span></span>
 - <span data-ttu-id="77ae4-106">Passaggio 1: creare il modello di elaborazione moduli per creare il tipo di contenuto</span><span class="sxs-lookup"><span data-stu-id="77ae4-106">Step 1: Create the from processing model to create the content type</span></span>
 - <span data-ttu-id="77ae4-107">Passaggio 2: aggiungere e analizzare file di esempio</span><span class="sxs-lookup"><span data-stu-id="77ae4-107">Step 2: Add and analyze example files</span></span>
 - <span data-ttu-id="77ae4-108">Passaggio 3: selezionare i campi del modulo</span><span class="sxs-lookup"><span data-stu-id="77ae4-108">Step 3: Select your form fields</span></span>
 - <span data-ttu-id="77ae4-109">Passaggio 4: eseguire il training e il test del modello</span><span class="sxs-lookup"><span data-stu-id="77ae4-109">Step 4: Train and test your model</span></span>
 - <span data-ttu-id="77ae4-110">Passaggio 5: pubblicare il modello</span><span class="sxs-lookup"><span data-stu-id="77ae4-110">Step 5: Publish your model</span></span>
 - <span data-ttu-id="77ae4-111">Passaggio 6: usare il modello</span><span class="sxs-lookup"><span data-stu-id="77ae4-111">Step 6: Use your model</span></span>

## <a name="requirements"></a><span data-ttu-id="77ae4-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="77ae4-112">Requirements</span></span>

<span data-ttu-id="77ae4-p101">È possibile unicamente creare un modello di elaborazione modulo nelle raccolte documenti di SharePoint per cui è abilitato. Se l'elaborazione modulo è abilitata, è possibile vedere l'**AI Builder** **"Creare un modello di elaborazione modulo"** nel menu **Automatizza** della raccolta documenti. Se desideri abilitare l'elaborazione sulla raccolta documenti, è necessario contattare l'amministratore di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="77ae4-p101">You can only create a form processing model in SharePoint document libraries for which it is enabled. If form processing is enabled, you are able to see the **AI Builder** **"Create a form processing model'** under the **Automate** menu in your document library.  If you need processing enabled on your document library, you must contact your SharePoint administrator.</span></span>

 ![Creare un modello di AI Builder](../media/content-understanding/create-ai-builder-model.png)</br>

## <a name="step-1-create-a-form-processing-model"></a><span data-ttu-id="77ae4-117">Passaggio 1: creare un modello di elaborazione dei moduli</span><span class="sxs-lookup"><span data-stu-id="77ae4-117">Step 1: Create a form processing model</span></span>

<span data-ttu-id="77ae4-118">Per creare un modello di elaborazione dei moduli, occorre prima di tutto assegnare un nome al modello, creare e definire il nuovo tipo di contenuto e creare una specifica visualizzazione della raccolta documenti.</span><span class="sxs-lookup"><span data-stu-id="77ae4-118">The first step in creating a form processing model is to name it and create the define the new content type and create a new document library view for it.</span></span>

1. <span data-ttu-id="77ae4-119">Nella raccolta documenti scegliere **AI Builder**, dal menu **Automatizza**, quindi selezionare **Crea un modello di elaborazione dei moduli**.</span><span class="sxs-lookup"><span data-stu-id="77ae4-119">From the document library, select the **Automate** menu, select **AI Builder**, and then select **Create a Form Processing model**.</span></span>

    ![Creare un modello](../media/content-understanding/create-ai-builder-model.png)</br>

2. <span data-ttu-id="77ae4-121">Nel riquadro **Nuovo modello di elaborazione dei moduli** digitare un nome per il modello nel campo **Nome**, ad esempio *Ordini di acquisto*.</span><span class="sxs-lookup"><span data-stu-id="77ae4-121">In the **New form processing model** pane, in the  **Name** field, type a name for your model (for example, *Purchase Orders*).</span></span>

    ![Nuovo modello di elaborazione dei moduli](../media/content-understanding/new-form-model.png)</br> 

3. <span data-ttu-id="77ae4-p102">Quando si crea un modello di elaborazione modulo, viene creato un nuovo tipo di contenuto di SharePoint. Un tipo di contenuto di SharePoint rappresenta una categoria di documenti che vantano caratteristiche comuni e condividono una raccolta di colonne o proprietà dei metadati per quel contenuto specifico. I tipi di contenuto di SharePoint vengono gestiti tramite la [galleria dei tipi di contenuto]().</span><span class="sxs-lookup"><span data-stu-id="77ae4-p102">When you create a form processing model, you create a new SharePoint content type. A SharePoint content type represents a category of documents that have common characteristics and share a collection of columns or metadata properties for that particular content. SharePoint Content Types are managed through the [Content types gallery]().</span></span>

    <span data-ttu-id="77ae4-126">Selezionare **Impostazioni avanzate** se si desidera associare questo modello a un tipo di contenuto esistente nella Raccolta tipi di contenuto di SharePoint per usarne lo schema.</span><span class="sxs-lookup"><span data-stu-id="77ae4-126">Select **Advanced settings** if you want to map this model to an existing content type in the SharePoint Content types gallery to use its schema.</span></span> 

4. <span data-ttu-id="77ae4-p103">Il modello crea una nuova visualizzazione nella raccolta documenti per i dati estratti. Se non si desidera impostarla come visualizzazione predefinita, deselezionare **Imposta visualizzazione come predefinita**.</span><span class="sxs-lookup"><span data-stu-id="77ae4-p103">Your model creates a new view in your document library for your extracted data. If you do not want it to the default view, deselect **Set the view as default**.</span></span>

5. <span data-ttu-id="77ae4-129">Selezionare **Crea**.</span><span class="sxs-lookup"><span data-stu-id="77ae4-129">Select **Create**.</span></span>

## <a name="step-2-add-and-analyze-documents"></a><span data-ttu-id="77ae4-130">Passaggio 2: aggiungere e analizzare documenti</span><span class="sxs-lookup"><span data-stu-id="77ae4-130">Step 2: Add and analyze documents</span></span>

<span data-ttu-id="77ae4-p104">Dopo aver creato il nuovo modello di elaborazione modulo, il browser apre una nuova pagina del modello di elaborazione moduli di PowerApps AI Builder. In questa pagina è possibile aggiungere e analizzare i documenti di esempio.</span><span class="sxs-lookup"><span data-stu-id="77ae4-p104">After you create your new form processing model, your browser opens a new PowerApps AI Builder forms processing model page. On this page you can add and analyze your example documents.</span></span> </br>

> [!NOTE]
> <span data-ttu-id="77ae4-133">Quando si cercano file di esempio da usare, vedere i [requisiti dei documenti di input per il modello di elaborazione moduli e suggerimenti per l'ottimizzazione](https://docs.microsoft.com/ai-builder/form-processing-model-requirements).</span><span class="sxs-lookup"><span data-stu-id="77ae4-133">When looking for example files to use, see the [form processing model input document requirements and optimization tips](https://docs.microsoft.com/ai-builder/form-processing-model-requirements).</span></span> 

   ![Power Apps AI Builder](../media/content-understanding/powerapps.png)</br> 
 
1. <span data-ttu-id="77ae4-p105">Selezionare **Aggiungi documenti** per iniziare ad aggiungere documenti di esempio analizzati per determinare le coppie di valori denominate che possono essere estratte. È quindi possibile scegliere o **Carica da risorsa di archiviazione locale**, **SharePoint** o **Risorsa di archiviazione Azure Blob**. È necessario usare almeno cinque file per il training.</span><span class="sxs-lookup"><span data-stu-id="77ae4-p105">Select **Add documents** to begin adding example documents analyzed to determine the named value pairs that can be extracted. You can then choose either **Upload from local storage**, **SharePoint**, or **Azure Blob storage**. You need to use at least five files for training.</span></span>

2. <span data-ttu-id="77ae4-p106">Dopo aver aggiunto i file, selezionare **Analizza** per verificare le informazioni comuni in tutti i file. Il completamento potrebbe richiedere alcuni minuti.</span><span class="sxs-lookup"><span data-stu-id="77ae4-p106">After adding files, select **Analyze** to check for any information common is all files. This may take several minutes to complete.</span></span></br> 
 
    ![Analizzare i file](../media/content-understanding/analyze.png)</br> 

3. <span data-ttu-id="77ae4-141">Terminata l'analisi dei file, nella pagina **Selezionare i campi del modulo da salvare** selezionare il file per visualizzare i campi rilevati.</span><span class="sxs-lookup"><span data-stu-id="77ae4-141">After the files have been analyzed, in the **Select the form fields you want to save** page select the file to view the detected fields.</span></span></br>

    ![Selezionare i campi del modulo](../media/content-understanding/select-form-fields.png)</br> 

## <a name="step-3-select-your-form-fields"></a><span data-ttu-id="77ae4-143">Passaggio 3: selezionare i campi del modulo</span><span class="sxs-lookup"><span data-stu-id="77ae4-143">Step 3: Select your form fields</span></span>

<span data-ttu-id="77ae4-p107">Dopo aver analizzato i documenti per i campi, è possibile visualizzare i campi trovati e identificare quelli che si desidera salvare. I campi salvati vengono visualizzati come colonne nella visualizzazione della raccolta documenti dei modello e mostrano i valori estratti da ogni documento.</span><span class="sxs-lookup"><span data-stu-id="77ae4-p107">After analyzing the documents for fields, you can now see the fields that were found, and identify the ones that you want to save. Saved fields display as columns in your model's document library view and show the values extracted from each document.</span></span>

1. <span data-ttu-id="77ae4-146">Nella pagina successiva viene visualizzato uno dei file di esempio e vengono evidenziati tutti i campi comuni che sono stati rilevati automaticamente dal sistema.</span><span class="sxs-lookup"><span data-stu-id="77ae4-146">The next page displays one of your sample files and will highlight all common fields that were automatically detected by the system.</span></span> </br>

    ![Pagina Seleziona campi](../media/content-understanding/select-fields-page.png)</br> 

2. <span data-ttu-id="77ae4-p108">Selezionare i campi che si desidera salvare, quindi la casella di controllo per confermare la selezione. Ad esempio, nel modello dell'Ordine di acquisto, scegliere di selezionare *Data*, *PO* e *Campi* totali. Si noti che è possibile decidere di rinominare un campo, se del caso.</span><span class="sxs-lookup"><span data-stu-id="77ae4-p108">Select the fields that you want to save and select the checkbox to confirm your selection. For example, in the Purchase Order model, choose to select the *Date*, *PO*, and *Total* fields.  Note that you can also choose to rename a field if you choose. </span></span></br>

    ![Selezionare il numero dell'ordine d'acquisto](../media/content-understanding/po.png)</br> 

3. <span data-ttu-id="77ae4-p109">Qualora un campo non venisse rilevato dall'analisi, sarà ancora possibile aggiungerlo. Evidenziare l'informazione che si desidera estrarre e, nel riquadro relativo al nome digitare il nome desiderato. Quindi selezionare la casella di controllo. Si noti che è necessario confermare i campi non rilevati nei file di esempio rimanenti.</span><span class="sxs-lookup"><span data-stu-id="77ae4-p109">If a field was not detected by analysis, you can still choose to add it. Highlight the information you want to extract, and in the name box type in the name you want. Then select the check box. Note that you need to confirm undetected fields in your remaining sample files.</span></span>

4. <span data-ttu-id="77ae4-156">Dopo aver selezionato i campi da salvare, fare clic su **Conferma campi**.</span><span class="sxs-lookup"><span data-stu-id="77ae4-156">Click **Confirm fields** after you have selected the fields that you want to save.</span></span> </br>
 
    ![Conferma campi dopo aver selezionato i campi](../media/content-understanding/confirm-fields.png)</br> 
 
5. <span data-ttu-id="77ae4-p110">Nella pagina **Selezionare i campi del modulo che si desidera salvare**, mostrerà il numero di campi selezionati. Selezionare **Fatto**.</span><span class="sxs-lookup"><span data-stu-id="77ae4-p110">On the **Select the form fields you want to save** page, it shows the number of fields you have selected. Select **Done**.</span></span>

## <a name="step-4-train-and-test-your-model"></a><span data-ttu-id="77ae4-160">Passaggio 4: eseguire il training e il test del modello</span><span class="sxs-lookup"><span data-stu-id="77ae4-160">Step 4: Train and test your model</span></span>

<span data-ttu-id="77ae4-161">Dopo aver selezionato i campi da salvare, nella pagina **Riepilogo modelli** è possibile eseguire il training e il test del modello.</span><span class="sxs-lookup"><span data-stu-id="77ae4-161">After selecting the fields you want to save, the **Model Summary** page lets you train and test your model.</span></span>

1. <span data-ttu-id="77ae4-p111">Nella pagina **Riepilogo modello**, i campi salvati verranno visualizzati nella sezione **Campi selezionati**. Selezionare **Eseguire il training** per iniziare il training sui file di esempio. Si noti che il completamento potrebbe richiedere alcuni minuti.</span><span class="sxs-lookup"><span data-stu-id="77ae4-p111">On the **Model Summary** page, the saved fields will show in the **Selected fields** section. Select **Train** to begin training on your example files. Note that this may take a few minutes to complete.</span></span></br>

     ![Training dei file selezionati](../media/content-understanding/select-fields-train.png)</br> 

2. <span data-ttu-id="77ae4-166">Quando viene indicato che il training è terminato, selezionare **Vai alla pagina Dettagli**.</span><span class="sxs-lookup"><span data-stu-id="77ae4-166">When you see the notification that training has completed, select **Go to details page**.</span></span> 

3. <span data-ttu-id="77ae4-p112">Nella pagina **Dettagli modello** è possibile scegliere di testare il funzionamento del modello selezionando **Test rapido**. Questa operazione consentirà di trascinare i file nella pagina e vedere se vengono rilevati i campi.</span><span class="sxs-lookup"><span data-stu-id="77ae4-p112">On the **Model details** page, you can choose to test how your model works by selecting **Quick test**. This lets you drag and drop files to the page and see if the fields are detected.</span></span>

    ![Confermare i campi](../media/content-understanding/select-fields-train.png)</br> 

2. <span data-ttu-id="77ae4-170">Quando viene indicato che il training è terminato, selezionare **Vai alla pagina Dettagli**.</span><span class="sxs-lookup"><span data-stu-id="77ae4-170">When you see the notification that training has completed, select **Go to details page**.</span></span> 

3. <span data-ttu-id="77ae4-p113">Nella pagina **Dettagli modello** scegliere di testare il funzionamento del modello selezionando **Test rapido**. Questa operazione consentirà di trascinare i file nella pagina e vedere se vengono rilevati i campi.</span><span class="sxs-lookup"><span data-stu-id="77ae4-p113">On the **Model details** page, choose to test how your model works by selecting **Quick test**. This lets you drag and drop files to the page and see if the fields are detected.</span></span>

## <a name="step-5-publish-your-model"></a><span data-ttu-id="77ae4-173">Passaggio 5: pubblicare il modello</span><span class="sxs-lookup"><span data-stu-id="77ae4-173">Step 5: Publish your model</span></span>

1. <span data-ttu-id="77ae4-174">Se i risultati del modello sono soddisfacenti, selezionare **Pubblica** per metterlo a disposizione.</span><span class="sxs-lookup"><span data-stu-id="77ae4-174">If you are satisfied with the results of your model, select **Publish** to make it available for use.</span></span>

2. <span data-ttu-id="77ae4-p114">Una volta pubblicato il modello, selezionare **Usa modello**. Questa operazione crea un flusso PowerAutomate che può essere eseguito nella raccolta documenti di SharePoint ed estrae i campi che sono stati identificati nel modello, quindi selezionare **Crea flusso**.</span><span class="sxs-lookup"><span data-stu-id="77ae4-p114">After the model is published, select **Use model**. This creates a PowerAutomate flow that can run in your SharePoint document library and extracts the fields that have been identified in the model, then select **Create Flow**.</span></span>
  
3. <span data-ttu-id="77ae4-177">Al termine, viene visualizzato il messaggio **Il flusso è stato creato**.</span><span class="sxs-lookup"><span data-stu-id="77ae4-177">When completed, you will see the message **Your flow has been successfully created**.</span></span>
 
## <a name="step-6-use-your-model"></a><span data-ttu-id="77ae4-178">Passaggio 6: usare il modello</span><span class="sxs-lookup"><span data-stu-id="77ae4-178">Step 6: Use your model</span></span>

<span data-ttu-id="77ae4-179">Dopo aver pubblicato il modello e avere creato il relativo flusso di PowerAutomate, è possibile usare il modello nella raccolta documenti di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="77ae4-179">After publishing your model and creating it's PowerAutomate flow, you can use your model in your SharePoint document library.</span></span>

1. <span data-ttu-id="77ae4-180">Dopo la pubblicazione del modello, selezionare **Vai a SharePoint** per passare alla raccolta documenti.</span><span class="sxs-lookup"><span data-stu-id="77ae4-180">After publishing your model, select **Go to SharePoint** to go to your document library.</span></span>

2. <span data-ttu-id="77ae4-181">Nella visualizzazione modello della raccolta documenti notare che i campi selezionati sono visualizzati in colonne.</span><span class="sxs-lookup"><span data-stu-id="77ae4-181">In the document library model view, notice that the fields you selected now display as columns.</span></span></br>

    ![Modello della raccolta documenti applicato](../media/content-understanding/doc-lib-view.png)</br> 

3. <span data-ttu-id="77ae4-183">Il collegamento alle informazioni accanto a **Documenti** indica che alla raccolta documenti è applicato un modello di elaborazione dei moduli.</span><span class="sxs-lookup"><span data-stu-id="77ae4-183">Notice that the information link next to **Documents** notes that a forms processing model is applied to this document library.</span></span>

    ![Pulsante Informazioni](../media/content-understanding/info-button.png)</br>  

4. <span data-ttu-id="77ae4-p115">Caricare i file nella raccolta documenti. Qualsiasi file identificato dal modello come corrispondente al suo tipo di contenuto elenca i file nella visualizzazione e mostra i dati estratti nelle colonne.</span><span class="sxs-lookup"><span data-stu-id="77ae4-p115">Upload files to your document library. Any files that the model identifies as it's content type lists the files in your view and displays the extracted data in the columns.</span></span></br>

    ![Fatto](../media/content-understanding/doc-lib-done.png)</br>  

## <a name="see-also"></a><span data-ttu-id="77ae4-188">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="77ae4-188">See Also</span></span>
  
[<span data-ttu-id="77ae4-189">Documentazione di Power Automate</span><span class="sxs-lookup"><span data-stu-id="77ae4-189">Power Automate documentation</span></span>](https://docs.microsoft.com/power-automate/)

[<span data-ttu-id="77ae4-190">Formazione: migliorare le prestazioni aziendali con AI Builder</span><span class="sxs-lookup"><span data-stu-id="77ae4-190">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)
