---
title: Applicare un modello di analisi dei documenti a una raccolta documenti
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: Informazioni su come applicare un modello pubblicato a una raccolta documenti di SharePoint
ms.openlocfilehash: 8b7d6cf21f422ba54933c2d3ac29b4b34171059e
ms.sourcegitcommit: f7ca339bdcad38796c550064fb152ea09687d0f3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2020
ms.locfileid: "48322154"
---
# <a name="apply-a-document-understanding-model-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="bd2ae-103">Applicare un modello di analisi dei documenti in Microsoft SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="bd2ae-103">Apply a document understanding model in Microsoft SharePoint Syntex</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

<span data-ttu-id="bd2ae-104">Dopo aver pubblicato il modello di analisi dei documenti, è possibile applicarlo a una o più raccolte documenti di SharePoint nel tenant di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bd2ae-104">After publishing your document understanding model, you can apply it to one or more SharePoint document library in your Microsoft 365 tenant.</span></span>

> [!NOTE]
> <span data-ttu-id="bd2ae-105">È possibile applicare il modello solo alle raccolte documenti a cui si ha accesso.</span><span class="sxs-lookup"><span data-stu-id="bd2ae-105">You are only able to apply the model to document libraries that you have access to.</span></span>


## <a name="apply-your-model-to-a-document-library"></a><span data-ttu-id="bd2ae-106">Applicare il modello a una raccolta documenti.</span><span class="sxs-lookup"><span data-stu-id="bd2ae-106">Apply your model to a document library.</span></span>

<span data-ttu-id="bd2ae-107">Per applicare il modello a una raccolta documenti di SharePoint:</span><span class="sxs-lookup"><span data-stu-id="bd2ae-107">To apply your model to to a SharePoint document library:</span></span>

1. <span data-ttu-id="bd2ae-108">Nella home page del modello, nel riquadro **Applica modello alle raccolte**, selezionare **Pubblica modello**.</span><span class="sxs-lookup"><span data-stu-id="bd2ae-108">On model home page, on the **Apply model to libraries** tile, select **Publish model**.</span></span> <span data-ttu-id="bd2ae-109">In alternativa, è possibile selezionare **+Aggiungi raccolta** nella sezione **Raccolte con questo modello**.</span><span class="sxs-lookup"><span data-stu-id="bd2ae-109">Or you can select  **+Add Library** in the **Libraries with this model** section.</span></span> </br>

    ![Aggiungere un modello a una raccolta](../media/content-understanding/apply-to-library.png)</br>

2. <span data-ttu-id="bd2ae-111">È possibile selezionare il sito di SharePoint che contiene la raccolta a cui si vuole applicare il modello.</span><span class="sxs-lookup"><span data-stu-id="bd2ae-111">You can then select the SharePoint site that contains the document library that you want to apply the model to.</span></span> <span data-ttu-id="bd2ae-112">Se il sito non viene visualizzato nell'elenco, usare la casella di ricerca per trovarlo.</span><span class="sxs-lookup"><span data-stu-id="bd2ae-112">If the site does not show in the list, use the search box to find it.</span></span></br>

    ![Selezionare un sito](../media/content-understanding/site-search.png)</br>

    > [!NOTE]
    > <span data-ttu-id="bd2ae-114">È necessario disporre delle autorizzazioni di *Gestione dell'elenco* o dei diritti di *modifica* per la raccolta documenti a cui si sta applicando il modello.</span><span class="sxs-lookup"><span data-stu-id="bd2ae-114">You must have *Manage List* permissions or *Edit* rights to the document library you are applying the model to.</span></span></br>

3. <span data-ttu-id="bd2ae-115">Dopo aver selezionato il sito, selezionare la raccolta in cui si vuole applicare il modello.</span><span class="sxs-lookup"><span data-stu-id="bd2ae-115">After selecting the site, select the document library to which you want to apply the model.</span></span> <span data-ttu-id="bd2ae-116">Nell'esempio selezionare la raccolta documenti *Documenti* dal sito *Rilevamento casi di Contoso*.</span><span class="sxs-lookup"><span data-stu-id="bd2ae-116">In the sample, select the *Documents* document library from the *Contoso Case Tracking* site.</span></span></br>

    ![Selezionare una raccolta documenti](../media/content-understanding/select-doc-library.png)</br>

4. <span data-ttu-id="bd2ae-118">Poiché il modello è associato a un tipo di contenuto, quando viene applicato alla raccolta aggiungerà il tipo di contenuto e la relativa visualizzazione con le etichette estratte come colonne.</span><span class="sxs-lookup"><span data-stu-id="bd2ae-118">Since the model is associated to a content type, when you apply it to the library it will add the content type and its view with the labels you extracted showing as columns.</span></span> <span data-ttu-id="bd2ae-119">Questa è la visualizzazione predefinita della raccolta per impostazione predefinita, ma è possibile scegliere facoltativamente di non impostarla come visualizzazione predefinita selezionando **Impostazioni avanzate** e deselezionando **Imposta questa nuova visualizzazione come predefinita**.</span><span class="sxs-lookup"><span data-stu-id="bd2ae-119">This view is the library's default view by default, but you can optionally choose to not have it be the default view by selecting **Advanced settings** and deselecting **Set this new view as default**.</span></span></br>

    ![Visualizzazione della raccolta](../media/content-understanding/library-view.png)</br>

5. <span data-ttu-id="bd2ae-121">Selezionare **Aggiungi** per applicare il modello alla raccolta.</span><span class="sxs-lookup"><span data-stu-id="bd2ae-121">Select **Add** to apply the model to the library.</span></span> 
6. <span data-ttu-id="bd2ae-122">Nella home page del modello, nella sezione **Raccolte con questo modello**, dovrebbe essere visualizzato l'URL del sito di SharePoint elencato.</span><span class="sxs-lookup"><span data-stu-id="bd2ae-122">On the model home page, in the **Libraries with this model** section, you should see the URL to the SharePoint site listed.</span></span></br>

    ![Raccolta selezionata](../media/content-understanding/selected-library.png)</br>

7. <span data-ttu-id="bd2ae-124">Passare alla tua raccolta documenti e assicurarsi di essere nella visualizzazione raccolta documenti del modello.</span><span class="sxs-lookup"><span data-stu-id="bd2ae-124">Go to your document library and make sure you are in the model's document library view.</span></span> <span data-ttu-id="bd2ae-125">Se si seleziona il pulsante informazioni accanto al nome della raccolta documenti, viene visualizzato un messaggio che informa che il modello è stato applicato alla raccolta documenti.</span><span class="sxs-lookup"><span data-stu-id="bd2ae-125">Notice that if you select the information button next to the document library name, a message notes that your model has been applied to the document library.</span></span>

    ![Visualizzazione delle informazioni](../media/content-understanding/info-du.png)</br> 


<span data-ttu-id="bd2ae-127">Dopo aver applicato il modello nella raccolta documenti, è possibile iniziare a caricare documenti nel sito e visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="bd2ae-127">After applying the model to the document library, you can begin uploading documents to the site and see the results.</span></span>

<span data-ttu-id="bd2ae-128">Il modello identifica i file con tipo di contenuto associato al modello e li elenca nella visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="bd2ae-128">The model identifies any files with model’s associated content type and lists them in your view.</span></span> <span data-ttu-id="bd2ae-129">Se il modello è dotato di estrattori, nella visualizzazione verranno mostrate le colonne dei dati da estrarre da ogni file.</span><span class="sxs-lookup"><span data-stu-id="bd2ae-129">If your model has any extractors, the view displays columns for the data you are extracting from each file.</span></span>

### <a name="apply-the-model-to-files-already-in-the-document-library"></a><span data-ttu-id="bd2ae-130">Applicare il modello ai file già presenti nella raccolta documenti</span><span class="sxs-lookup"><span data-stu-id="bd2ae-130">Apply the model to files already in the document library</span></span>

<span data-ttu-id="bd2ae-131">Anche se un modello applicato elabora tutti i file caricati nella raccolta documenti dopo l'applicazione, è possibile eseguire le operazioni seguenti per eseguire il modello sui file già esistenti nella raccolta documenti prima di applicare il modello:</span><span class="sxs-lookup"><span data-stu-id="bd2ae-131">While an applied model processes all files uploaded to the document library after it is applied, you can also do the following to run the model on files that already exists in the document library prior to the model being applied:</span></span>

1. <span data-ttu-id="bd2ae-132">Nella raccolta documenti selezionare i file che si vuole far elaborare dal modello.</span><span class="sxs-lookup"><span data-stu-id="bd2ae-132">In your document library, select the files that you want to be processed by your model.</span></span>
2. <span data-ttu-id="bd2ae-133">Dopo aver selezionato i file, **Classifica ed estrai** verrà visualizzati nella barra multifunzione della raccolta documenti.</span><span class="sxs-lookup"><span data-stu-id="bd2ae-133">After selecting your files, **Classify and extract** will appear in the document library ribbon.</span></span> <span data-ttu-id="bd2ae-134">Selezionare **Classifica ed estrai**.</span><span class="sxs-lookup"><span data-stu-id="bd2ae-134">Select **Classify and extract**.</span></span>
3. <span data-ttu-id="bd2ae-135">I file selezionati verranno aggiunti alla coda per essere elaborati.</span><span class="sxs-lookup"><span data-stu-id="bd2ae-135">The files you selected will be added to the queue to be processed.</span></span>

      ![Classificare ed estrarre](../media/content-understanding/extract-classify.png)</br> 

## <a name="see-also"></a><span data-ttu-id="bd2ae-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bd2ae-137">See Also</span></span>
[<span data-ttu-id="bd2ae-138">Creare un classificatore</span><span class="sxs-lookup"><span data-stu-id="bd2ae-138">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="bd2ae-139">Creare un estrattore</span><span class="sxs-lookup"><span data-stu-id="bd2ae-139">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="bd2ae-140">Panoramica dell'analisi dei documenti</span><span class="sxs-lookup"><span data-stu-id="bd2ae-140">Document Understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="bd2ae-141">Creare un modello di elaborazione moduli</span><span class="sxs-lookup"><span data-stu-id="bd2ae-141">Create a form processing model</span></span>](create-a-form-processing-model.md)  
