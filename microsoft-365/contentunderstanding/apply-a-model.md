---
title: Applicare un modello di analisi dei documenti a una raccolta documenti
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
localization_priority: Normal
description: Informazioni su come applicare un modello pubblicato a una raccolta documenti di SharePoint
ms.openlocfilehash: cda9de43d0139c52f950527eb75d050602005fd2
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843295"
---
# <a name="apply-a-document-understanding-model-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="5e944-103">Applicare un modello di analisi dei documenti in Microsoft SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="5e944-103">Apply a document understanding model in Microsoft SharePoint Syntex</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

<span data-ttu-id="5e944-104">Dopo aver pubblicato il modello di analisi dei documenti, è possibile applicarlo a una o più raccolte documenti di SharePoint nel tenant di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5e944-104">After publishing your document understanding model, you can apply it to one or more SharePoint document library in your Microsoft 365 tenant.</span></span>

> [!NOTE]
> <span data-ttu-id="5e944-105">È possibile applicare il modello solo alle raccolte documenti a cui si ha accesso.</span><span class="sxs-lookup"><span data-stu-id="5e944-105">You are only able to apply the model to document libraries that you have access to.</span></span>


## <a name="apply-your-model-to-a-document-library"></a><span data-ttu-id="5e944-106">Applicare il modello a una raccolta documenti.</span><span class="sxs-lookup"><span data-stu-id="5e944-106">Apply your model to a document library.</span></span>

<span data-ttu-id="5e944-107">Per applicare il modello a una raccolta documenti di SharePoint:</span><span class="sxs-lookup"><span data-stu-id="5e944-107">To apply your model to to a SharePoint document library:</span></span>

1. <span data-ttu-id="5e944-108">Nella home page del modello, nel riquadro **Applica modello alle raccolte**, selezionare **Pubblica modello**.</span><span class="sxs-lookup"><span data-stu-id="5e944-108">On model home page, on the **Apply model to libraries** tile, select **Publish model**.</span></span> <span data-ttu-id="5e944-109">In alternativa, è possibile selezionare **+Aggiungi raccolta** nella sezione **Raccolte con questo modello**.</span><span class="sxs-lookup"><span data-stu-id="5e944-109">Or you can select  **+Add Library** in the **Libraries with this model** section.</span></span> </br>

    ![Aggiungere un modello a una raccolta](../media/content-understanding/apply-to-library.png)</br>

2. <span data-ttu-id="5e944-111">È possibile selezionare il sito di SharePoint che contiene la raccolta a cui si vuole applicare il modello.</span><span class="sxs-lookup"><span data-stu-id="5e944-111">You can then select the SharePoint site that contains the document library that you want to apply the model to.</span></span> <span data-ttu-id="5e944-112">Se il sito non viene visualizzato nell'elenco, usare la casella di ricerca per trovarlo.</span><span class="sxs-lookup"><span data-stu-id="5e944-112">If the site does not show in the list, use the search box to find it.</span></span></br>

    ![Selezionare un sito](../media/content-understanding/site-search.png)</br>

    > [!NOTE]
    > <span data-ttu-id="5e944-114">È necessario disporre delle autorizzazioni di *Gestione dell'elenco* o dei diritti di *modifica* per la raccolta documenti a cui si sta applicando il modello.</span><span class="sxs-lookup"><span data-stu-id="5e944-114">You must have *Manage List* permissions or *Edit* rights to the document library you are applying the model to.</span></span></br>

3. <span data-ttu-id="5e944-115">Dopo aver selezionato il sito, selezionare la raccolta in cui si vuole applicare il modello.</span><span class="sxs-lookup"><span data-stu-id="5e944-115">After selecting the site, select the document library to which you want to apply the model.</span></span> <span data-ttu-id="5e944-116">Nell'esempio selezionare la raccolta documenti *Documenti* dal sito *Rilevamento casi di Contoso*.</span><span class="sxs-lookup"><span data-stu-id="5e944-116">In the sample, select the *Documents* document library from the *Contoso Case Tracking* site.</span></span></br>

    ![Selezionare una raccolta documenti](../media/content-understanding/select-doc-library.png)</br>

4. <span data-ttu-id="5e944-118">Poiché il modello è associato a un tipo di contenuto, quando viene applicato alla raccolta aggiungerà il tipo di contenuto e la relativa visualizzazione con le etichette estratte come colonne.</span><span class="sxs-lookup"><span data-stu-id="5e944-118">Since the model is associated to a content type, when you apply it to the library it will add the content type and its view with the labels you extracted showing as columns.</span></span> <span data-ttu-id="5e944-119">Questa è la visualizzazione predefinita della raccolta per impostazione predefinita, ma è possibile scegliere facoltativamente di non impostarla come visualizzazione predefinita selezionando **Impostazioni avanzate** e deselezionando **Imposta questa nuova visualizzazione come predefinita**.</span><span class="sxs-lookup"><span data-stu-id="5e944-119">This view is the library's default view by default, but you can optionally choose to not have it be the default view by selecting **Advanced settings** and deselecting **Set this new view as default**.</span></span></br>

    ![Visualizzazione della raccolta](../media/content-understanding/library-view.png)</br>

5. <span data-ttu-id="5e944-121">Selezionare **Aggiungi** per applicare il modello alla raccolta.</span><span class="sxs-lookup"><span data-stu-id="5e944-121">Select **Add** to apply the model to the library.</span></span> 
6. <span data-ttu-id="5e944-122">Nella home page del modello, nella sezione **Raccolte con questo modello**, dovrebbe essere visualizzato l'URL del sito di SharePoint elencato.</span><span class="sxs-lookup"><span data-stu-id="5e944-122">On the model home page, in the **Libraries with this model** section, you should see the URL to the SharePoint site listed.</span></span></br>

    ![Raccolta selezionata](../media/content-understanding/selected-library.png)</br>

7. <span data-ttu-id="5e944-124">Passare alla tua raccolta documenti e assicurarsi di essere nella visualizzazione raccolta documenti del modello.</span><span class="sxs-lookup"><span data-stu-id="5e944-124">Go to your document library and make sure you are in the model's document library view.</span></span> <span data-ttu-id="5e944-125">Se si seleziona il pulsante informazioni accanto al nome della raccolta documenti, viene visualizzato un messaggio che informa che un modello è stato applicato alla raccolta documenti.</span><span class="sxs-lookup"><span data-stu-id="5e944-125">Notice that if you select the information button next to the document library name, a message notes that the document library has a model applied to it.</span></span>

    ![Visualizzazione delle informazioni](../media/content-understanding/info-du.png)</br> 

    <span data-ttu-id="5e944-127">È possibile selezionare **Visualizza modelli attivi** per visualizzare i dettagli di tutti i modelli applicati alla raccolta documenti.</span><span class="sxs-lookup"><span data-stu-id="5e944-127">You can the select **View active models** to see details about any models that are applied to the document library.</span></span>

8. <span data-ttu-id="5e944-128">Nel riquadro **Modelli attivi** è possibile visualizzare i modelli applicati alla raccolta documenti.</span><span class="sxs-lookup"><span data-stu-id="5e944-128">In the **Active models** pane, you can see the models that are applied to the document library.</span></span> <span data-ttu-id="5e944-129">Selezionare un modello per visualizzare altri dettagli, ad esempio una descrizione del modello, chi lo ha pubblicato e se il modello applica un'etichetta di conservazione ai file che classifica.</span><span class="sxs-lookup"><span data-stu-id="5e944-129">Select a model to see more details about it, such as a description of the model, who published the model, and if the model applies a retention label to the files it classifies.</span></span>

    ![Riquadro Modelli attivi](../media/content-understanding/active-models.png)</br> 

<span data-ttu-id="5e944-131">Dopo aver applicato il modello nella raccolta documenti, è possibile iniziare a caricare documenti nel sito e visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="5e944-131">After applying the model to the document library, you can begin uploading documents to the site and see the results.</span></span>

<span data-ttu-id="5e944-132">Il modello identifica i file con tipo di contenuto associato al modello e li elenca nella visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="5e944-132">The model identifies any files with model’s associated content type and lists them in your view.</span></span> <span data-ttu-id="5e944-133">Se il modello è dotato di estrattori, nella visualizzazione verranno mostrate le colonne dei dati da estrarre da ogni file.</span><span class="sxs-lookup"><span data-stu-id="5e944-133">If your model has any extractors, the view displays columns for the data you are extracting from each file.</span></span>

### <a name="apply-the-model-to-files-already-in-the-document-library"></a><span data-ttu-id="5e944-134">Applicare il modello ai file già presenti nella raccolta documenti</span><span class="sxs-lookup"><span data-stu-id="5e944-134">Apply the model to files already in the document library</span></span>

<span data-ttu-id="5e944-135">Anche se un modello applicato elabora tutti i file caricati nella raccolta documenti dopo l'applicazione, è possibile eseguire le operazioni seguenti per eseguire il modello sui file già esistenti nella raccolta documenti prima di applicare il modello:</span><span class="sxs-lookup"><span data-stu-id="5e944-135">While an applied model processes all files uploaded to the document library after it is applied, you can also do the following to run the model on files that already exists in the document library prior to the model being applied:</span></span>

1. <span data-ttu-id="5e944-136">Nella raccolta documenti selezionare i file che si vuole far elaborare dal modello.</span><span class="sxs-lookup"><span data-stu-id="5e944-136">In your document library, select the files that you want to be processed by your model.</span></span>
2. <span data-ttu-id="5e944-137">Dopo aver selezionato i file, **Classifica ed estrai** verrà visualizzati nella barra multifunzione della raccolta documenti.</span><span class="sxs-lookup"><span data-stu-id="5e944-137">After selecting your files, **Classify and extract** will appear in the document library ribbon.</span></span> <span data-ttu-id="5e944-138">Selezionare **Classifica ed estrai**.</span><span class="sxs-lookup"><span data-stu-id="5e944-138">Select **Classify and extract**.</span></span>
3. <span data-ttu-id="5e944-139">I file selezionati verranno aggiunti alla coda per essere elaborati.</span><span class="sxs-lookup"><span data-stu-id="5e944-139">The files you selected will be added to the queue to be processed.</span></span>

      ![Classificare ed estrarre](../media/content-understanding/extract-classify.png)</br> 

> [!NOTE]
> <span data-ttu-id="5e944-141">È possibile copiare file singoli in una raccolta e applicarli a un modello, ma non è possibile eseguire la stessa operazione con le cartelle.</span><span class="sxs-lookup"><span data-stu-id="5e944-141">You can copy individual files to a library and apply them to a model, but not folders.</span></span>

### <a name="the-classification-date-field"></a><span data-ttu-id="5e944-142">Il campo Data di classificazione</span><span class="sxs-lookup"><span data-stu-id="5e944-142">The Classification Date field</span></span>

<span data-ttu-id="5e944-143">Quando a una raccolta documenti viene applicato un modello di analisi dei documenti o di elaborazione moduli di SharePoint Syntex, nello schema della raccolta viene incluso un campo <b>Data di classificazione</b>.</span><span class="sxs-lookup"><span data-stu-id="5e944-143">When a SharePoint Syntex document understanding or form processing model is applied to a document library, a <b> Classification date </b> field is included in the library schema.</span></span> <span data-ttu-id="5e944-144">Per impostazione predefinita, questo campo è vuoto, ma quando i documenti vengono elaborati e classificati da un modello, questo campo viene aggiornato con un indicatore di data e ora di completamento.</span><span class="sxs-lookup"><span data-stu-id="5e944-144">By default this field is empty, but when documents are processed and classified by a model, this field is updated with a date-time stamp of completion.</span></span> 

   ![Colonna Data di classificazione](../media/content-understanding/class-date-column.png)</br> 

<span data-ttu-id="5e944-146">Il campo Data di classificazione viene usato dal trigger [<b>Quando un file viene classificato da un modello di comprensione dei contenuti</b>](/connectors/sharepointonline/#when-a-file-is-classified-by-a-content-understanding-model) per eseguire un flusso di Power Automate dopo che un modello di comprensione dei contenuti Syntex ha completato l'elaborazione di un file e aggiornato il campo "Data di classificazione".</span><span class="sxs-lookup"><span data-stu-id="5e944-146">The Classification date field is used by the [<b>When a file is classified by a content understanding model</b> trigger](/connectors/sharepointonline/#when-a-file-is-classified-by-a-content-understanding-model) to run a Power Automate flow after a Syntex content understanding model has finished processing a file and updated the "Classification date" field.</span></span>

   ![Trigger di flusso](../media/content-understanding/trigger.png)</br>

<span data-ttu-id="5e944-148">Il trigger <b>Quando un file viene classificato da un modello di comprensione dei contenuti</b> può quindi essere usato per avviare un altro flusso di lavoro usando qualsiasi informazione estratta dal file.</span><span class="sxs-lookup"><span data-stu-id="5e944-148">The <b>When a file is classified by a content understanding model</b> trigger can then be used to start another workflow using any  extracted information from the file.</span></span>



## <a name="see-also"></a><span data-ttu-id="5e944-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5e944-149">See Also</span></span>
[<span data-ttu-id="5e944-150">Creare un classificatore</span><span class="sxs-lookup"><span data-stu-id="5e944-150">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="5e944-151">Creare un estrattore</span><span class="sxs-lookup"><span data-stu-id="5e944-151">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="5e944-152">Panoramica sull'analisi dei documenti</span><span class="sxs-lookup"><span data-stu-id="5e944-152">Document Understanding overview</span></span>](document-understanding-overview.md)
