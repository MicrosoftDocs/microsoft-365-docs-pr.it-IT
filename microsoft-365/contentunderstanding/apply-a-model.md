---
title: Applicare un modello di comprensione del documento a una raccolta documenti (anteprima)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Informazioni su come applicare un modello pubblicato a una raccolta documenti di SharePoint.
ms.openlocfilehash: 7e5f3f02c2679769515b27026918a15c901c896e
ms.sourcegitcommit: ea5e2f85bd6b609658545b120c7e08789b9686fd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/01/2020
ms.locfileid: "46537617"
---
# <a name="apply-a-document-understanding-model-preview"></a><span data-ttu-id="e133d-103">Applicazione di un modello di comprensione del documento (anteprima)</span><span class="sxs-lookup"><span data-stu-id="e133d-103">Apply a document understanding model (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="e133d-104">Il contenuto di questo articolo è relativo all'anteprima privata di Project Cortex.</span><span class="sxs-lookup"><span data-stu-id="e133d-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="e133d-105">[Per ulteriori informazioni, vedere Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="e133d-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

<span data-ttu-id="e133d-106">Dopo aver pubblicato il modello di conoscenza del documento, è possibile applicarlo a una raccolta documenti di SharePoint nel tenant Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e133d-106">After publishing your document understanding model, you can apply it to a SharePoint document library in your Microsoft 365 tenant.</span></span>

> [!Note]
> <span data-ttu-id="e133d-107">Sarà possibile applicare il modello solo alle raccolte documenti a cui è possibile accedere.</span><span class="sxs-lookup"><span data-stu-id="e133d-107">You will only be able to apply the model to document libraries that you have access to.</span></span>


## <a name="apply-your-model-to-a-document-library"></a><span data-ttu-id="e133d-108">Applicare il modello a una raccolta documenti.</span><span class="sxs-lookup"><span data-stu-id="e133d-108">Apply your model to a document library.</span></span>

<span data-ttu-id="e133d-109">Per applicare il modello a una raccolta documenti di SharePoint:</span><span class="sxs-lookup"><span data-stu-id="e133d-109">To apply your model to to a SharePoint document library:</span></span>

1. <span data-ttu-id="e133d-110">Nella Home page del modello fare clic su **Pubblica modello**nella sezione **Applica modello a raccolte** .</span><span class="sxs-lookup"><span data-stu-id="e133d-110">On the model home page, on the **Apply model to libraries** tile, select **Publish model**.</span></span> <span data-ttu-id="e133d-111">In alternativa, è possibile selezionare **+ Aggiungi raccolta** nella sezione **raccolte con questo modello** .</span><span class="sxs-lookup"><span data-stu-id="e133d-111">Or you can  select  **+Add Library** in the **Libraries with this model** section.</span></span> </br>

    ![Aggiungere un modello alla raccolta](../media/content-understanding/apply-to-library.png)</br>

2. <span data-ttu-id="e133d-113">È quindi possibile selezionare il sito di SharePoint contenente la raccolta documenti a cui si desidera applicare il modello.</span><span class="sxs-lookup"><span data-stu-id="e133d-113">You can then select the SharePoint site that contains the document library that you want to apply the model to.</span></span> <span data-ttu-id="e133d-114">Se il sito non viene visualizzato nell'elenco, utilizzare la casella di ricerca per individuarlo.</span><span class="sxs-lookup"><span data-stu-id="e133d-114">If the site does not show in the list, use the search box to find it.</span></span></br>

    ![Selezionare un sito](../media/content-understanding/site-search.png)</br>

    > [!Note]
    > <span data-ttu-id="e133d-116">È necessario disporre delle autorizzazioni *Gestisci elenco* o *modifica* diritti per la raccolta documenti a cui si sta applicando il modello.</span><span class="sxs-lookup"><span data-stu-id="e133d-116">You must have *Manage List* permissions or *Edit* rights to the document library you are applying the model to.</span></span></br>

3. <span data-ttu-id="e133d-117">Dopo aver selezionato il sito, è necessario selezionare la raccolta documenti in cui si desidera applicare il modello.</span><span class="sxs-lookup"><span data-stu-id="e133d-117">After selecting the site, you then need to select the document library to which you want to apply the model.</span></span> <span data-ttu-id="e133d-118">In questo esempio viene selezionata la raccolta *documenti* del documento dal sito di *Verifica dei casi di Contoso* .</span><span class="sxs-lookup"><span data-stu-id="e133d-118">In the example, we are selecting the *Documents* document library from the *Contoso Case Tracking* site.</span></span></br>

    ![Selezionare una raccolta documenti](../media/content-understanding/select-doc-library.png)</br>

4. <span data-ttu-id="e133d-120">Poiché il modello è associato a un tipo di contenuto, quando lo si applica alla raccolta, viene creata una visualizzazione per il tipo di contenuto con le etichette estratte come colonne.</span><span class="sxs-lookup"><span data-stu-id="e133d-120">Since the model is associated to a content type, when you apply it to the library it will create a view for the content type with the labels you extracted showing as columns.</span></span> <span data-ttu-id="e133d-121">Questa visualizzazione sarà la visualizzazione predefinita della raccolta per impostazione predefinita, ma è possibile scegliere di non averlo come visualizzazione predefinita selezionando **Impostazioni avanzate** e deselezionando **imposta questa nuova visualizzazione come predefinita**.</span><span class="sxs-lookup"><span data-stu-id="e133d-121">This view will be the library's default view by default, but you can optionally choose to not have it be the default view by selecting **Advanced settings** and deselecting **Set this new view as default**.</span></span></br>

    ![Visualizzazione libreria](../media/content-understanding/library-view.png)</br>

5. <span data-ttu-id="e133d-123">Selezionare **Aggiungi** per applicare il modello alla raccolta.</span><span class="sxs-lookup"><span data-stu-id="e133d-123">Select **Add** to apply the model to the library.</span></span> 
6. <span data-ttu-id="e133d-124">Nella sezione **raccolte con questo modello** della Home page del modello verrà visualizzato l'URL del sito di SharePoint elencato.</span><span class="sxs-lookup"><span data-stu-id="e133d-124">On the model home page, in the **Libraries with this model** section, you will see the URL to the SharePoint site listed.</span></span></br>

    ![Visualizzazione libreria](../media/content-understanding/selected-library.png)</br>

7. <span data-ttu-id="e133d-126">Passare alla raccolta documenti e verificare di trovarsi nella visualizzazione della raccolta documenti del modello.</span><span class="sxs-lookup"><span data-stu-id="e133d-126">Go to your document library and make sure you are in the model's document library view.</span></span> <span data-ttu-id="e133d-127">Se si seleziona il pulsante informazioni accanto al nome della raccolta documenti, verrà visualizzato un messaggio che indica che il modello è stato applicato alla raccolta documenti.</span><span class="sxs-lookup"><span data-stu-id="e133d-127">You'll notice that if you select the information button next to the document library name, a message will note that your model has been applied to the document library.</span></span>

    ![Visualizzazione libreria](../media/content-understanding/info-du.png)</br> 


<span data-ttu-id="e133d-129">Dopo aver applicato il modello alla raccolta documenti, è possibile iniziare a caricare i documenti nel sito e visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="e133d-129">After applying the model to the document library, you can begin uploading documents to the site and see the results.</span></span>

<span data-ttu-id="e133d-130">Il modello identificherà tutti i file con il tipo di contenuto associato del modello e li visualizzerà nella visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="e133d-130">The model will identify any files with model’s associated content type and will list them in your view.</span></span> <span data-ttu-id="e133d-131">Se nel modello sono presenti estrattori, la visualizzazione visualizzerà le colonne per i dati da estrarre da ogni file.</span><span class="sxs-lookup"><span data-stu-id="e133d-131">If your model has any extractors, the view will display columns for the data you are extracting from each file.</span></span>

### <a name="apply-the-model-to-files-already-in-the-document-library"></a><span data-ttu-id="e133d-132">Applicazione del modello ai file già presenti nella raccolta documenti</span><span class="sxs-lookup"><span data-stu-id="e133d-132">Apply the model to files already in the document library</span></span>

<span data-ttu-id="e133d-133">Mentre un modello applicato elaborerà tutti i file caricati nella raccolta documenti dopo l'applicazione, è anche possibile eseguire le operazioni seguenti per l'esecuzione del modello nei file già esistenti nella raccolta documenti prima del modello applicato:</span><span class="sxs-lookup"><span data-stu-id="e133d-133">While an applied model will process all files uploaded to the document library after it is applied, you can also do the following to run the model on files that already existed in the document library prior to the model being applied:</span></span>

1. <span data-ttu-id="e133d-134">Nella raccolta documenti selezionare i file che si desidera vengano elaborati dal modello.</span><span class="sxs-lookup"><span data-stu-id="e133d-134">In your document library, select the files that you want to be processed by your model.</span></span>
2. <span data-ttu-id="e133d-135">Dopo aver selezionato i file, **classificare ed estrarre** verranno visualizzati nella barra multifunzione della raccolta documenti.</span><span class="sxs-lookup"><span data-stu-id="e133d-135">After selecting your files, **Classify and extract** will appear in the document library ribbon.</span></span> <span data-ttu-id="e133d-136">Selezionare **classifica ed Estrai**.</span><span class="sxs-lookup"><span data-stu-id="e133d-136">Select **Classify and extract**.</span></span>
3. <span data-ttu-id="e133d-137">I file selezionati verranno aggiunti alla coda per l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="e133d-137">The files you selected will be added to the queue to be processed.</span></span>

      ![Classificare ed estrarre](../media/content-understanding/extract-classify.png)</br> 





## <a name="see-also"></a><span data-ttu-id="e133d-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e133d-139">See Also</span></span>
[<span data-ttu-id="e133d-140">Creare un classificatore</span><span class="sxs-lookup"><span data-stu-id="e133d-140">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="e133d-141">Creare un estrattore</span><span class="sxs-lookup"><span data-stu-id="e133d-141">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="e133d-142">Panoramica della comprensione del documento</span><span class="sxs-lookup"><span data-stu-id="e133d-142">Document Understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="e133d-143">Creare un modello di elaborazione dei moduli</span><span class="sxs-lookup"><span data-stu-id="e133d-143">Create a form processing model</span></span>](create-a-form-processing-model.md)  




