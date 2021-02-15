---
title: Panoramica sull'analisi dei documenti
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
description: Ottenere una panoramica dell'analisi dei documenti in Microsoft SharePoint Syntex.
ms.openlocfilehash: d2bf581468eeee008d09a242876bed5ad07ae01f
ms.sourcegitcommit: 78f48304f990e969a052fe6536b2e8d6856e1086
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2021
ms.locfileid: "50242411"
---
# <a name="document-understanding-overview"></a><span data-ttu-id="bc08d-103">Panoramica sull'analisi dei documenti</span><span class="sxs-lookup"><span data-stu-id="bc08d-103">Document understanding overview</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

<span data-ttu-id="bc08d-104">L’analisi dei documenti utilizza modelli di intelligenza artificiale (AI) per automatizzare la classificazione dei file e l'estrazione delle informazioni.</span><span class="sxs-lookup"><span data-stu-id="bc08d-104">Document understanding uses artificial intelligence (AI) models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="bc08d-105">Funziona meglio con documenti non strutturati, ad esempio lettere o contratti.</span><span class="sxs-lookup"><span data-stu-id="bc08d-105">It works best with unstructured documents, such as letters or contracts.</span></span> <span data-ttu-id="bc08d-106">Questi documenti devono contenere un testo che possa essere identificato in base a frasi o schemi.</span><span class="sxs-lookup"><span data-stu-id="bc08d-106">These documents must have text that can be identified based on phrases or patterns.</span></span> <span data-ttu-id="bc08d-107">Il testo identificato designa sia il tipo di file (la classificazione) che l'elemento che si vuole estrarre (l’estrattore).</span><span class="sxs-lookup"><span data-stu-id="bc08d-107">The identified text designates both the type of file it is (its classification) and what you'd like to extract (its extractors).</span></span>

> [!NOTE]
> <span data-ttu-id="bc08d-108">Per altri esempi sull’analisi dei documenti, vedere[Adozione di SharePoint Syntex: guida introduttiva](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#document-understanding-scenario-example).</span><span class="sxs-lookup"><span data-stu-id="bc08d-108">See the [SharePoint Syntex adoption: Get started guide](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#document-understanding-scenario-example) for more information about document understanding scenario examples.</span></span>

<span data-ttu-id="bc08d-109">I modelli di analisi dei documenti vengono creati e gestiti in un tipo di sito di SharePoint denominato *centro contenuti*.</span><span class="sxs-lookup"><span data-stu-id="bc08d-109">Document understanding models are created and managed in a type of SharePoint site called a *content center*.</span></span> <span data-ttu-id="bc08d-110">Se applicato a una raccolta documenti di SharePoint, il modello è associato a un tipo di contenuto con colonne in cui archiviare le informazioni estratte.</span><span class="sxs-lookup"><span data-stu-id="bc08d-110">When applied to a SharePoint document library, the model is associated with a content type has columns to store the information being extracted.</span></span> <span data-ttu-id="bc08d-111">Il tipo di contenuto creato è archiviato nella raccolta tipi di contenuto di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="bc08d-111">The content type you create is stored in the SharePoint content type gallery.</span></span> <span data-ttu-id="bc08d-112">È anche possibile scegliere di usare i tipi di contenuto esistenti per usare il loro schema.</span><span class="sxs-lookup"><span data-stu-id="bc08d-112">You can also choose to use existing content types to use their schema.</span></span>

> [!NOTE]
> <span data-ttu-id="bc08d-113">I tipi di contenuto in sola lettura o bloccati non possono essere aggiornati, quindi non possono essere usati in un modello.</span><span class="sxs-lookup"><span data-stu-id="bc08d-113">Read-only or sealed content types cannot be updated, so they cannot be used in a model.</span></span>

<span data-ttu-id="bc08d-114">Aggiungere *classificatori* ed *estrattori* ai modelli di analisi dei documento per eseguire le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="bc08d-114">Add *classifiers* and *extractors* to your document understanding models to do the following:</span></span> 

- <span data-ttu-id="bc08d-115">I classificatori vengono usati per identificare e classificare i documenti caricati nella raccolta documenti.</span><span class="sxs-lookup"><span data-stu-id="bc08d-115">Classifiers are used to identify and classify documents that are uploaded to the document library.</span></span> <span data-ttu-id="bc08d-116">Ad esempio, un classificatore può essere "addestrato" per identificare tutto i documenti di *rinnovo del contratto* caricati nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="bc08d-116">For example, a classifier can be "trained" to identify all *contract renewal* documents that are uploaded to the library.</span></span> <span data-ttu-id="bc08d-117">Il tipo di contenuto per il rinnovo del contratto viene definito dall'utente quando si crea il classificatore.</span><span class="sxs-lookup"><span data-stu-id="bc08d-117">The contract renewal content type is defined by you when you create your classifier.</span></span>

- <span data-ttu-id="bc08d-118">Gli estrattori estraggono informazioni da questi documenti.</span><span class="sxs-lookup"><span data-stu-id="bc08d-118">Extractors pull information from these documents.</span></span> <span data-ttu-id="bc08d-119">Ad esempio, per tutti i documenti di rinnovo del contratto identificati nella raccolta documenti, nella visualizzazione ci sono delle colonne che mostrano anche la *Data di inizio servizio* e il *Cliente* per ogni documento di rinnovo del contratto.</span><span class="sxs-lookup"><span data-stu-id="bc08d-119">For example, for all contract renewal documents identified in your document library, columns display in your view that also show the *Service Start Date* and  *Client* for each contract renewal document.</span></span> 

<span data-ttu-id="bc08d-120">È possibile usare i file di esempio per formare e testare i classificatori e gli estrattori nel modello.</span><span class="sxs-lookup"><span data-stu-id="bc08d-120">You can use example files to train and test your classifiers and extractors in your model.</span></span> <span data-ttu-id="bc08d-121">I file di esempio forniscono esempi di modelli su cosa cercare quando si prova a identificare ed estrarre dati da file.</span><span class="sxs-lookup"><span data-stu-id="bc08d-121">Example files provide your model examples of what to look for when trying to identify and extract data from files.</span></span> <span data-ttu-id="bc08d-122">Ad esempio, è necessario formare i classificatori e gli estrattori del rinnovo del contratto con esempi di documenti di rinnovo del contratto con cui lavora l’azienda.</span><span class="sxs-lookup"><span data-stu-id="bc08d-122">For example, you would train your contract renewal classifiers and extractors with examples of contract renewal documents your company works with.</span></span> <span data-ttu-id="bc08d-123">È anche possibile usare i file di esempio per testare l'efficacia del modello.</span><span class="sxs-lookup"><span data-stu-id="bc08d-123">You can also use example files to test the effectiveness of your model.</span></span>

<span data-ttu-id="bc08d-124">Dopo aver pubblicato il modello, usare il centro contenuto per applicarlo a qualsiasi raccolta documenti di SharePoint a cui si ha accesso.</span><span class="sxs-lookup"><span data-stu-id="bc08d-124">After publishing your model, use the content center to apply it to any SharePoint document library that you have access to.</span></span>  

### <a name="file-limitations"></a><span data-ttu-id="bc08d-125">Limitazioni relative ai file</span><span class="sxs-lookup"><span data-stu-id="bc08d-125">File limitations</span></span>

<span data-ttu-id="bc08d-126">I modelli di analisi dei documenti usano la tecnologia di riconoscimento ottico dei caratteri (OCR) per analizzare file PDF, immagini e file TIFF, sia quando si esegue il training di un modello con file di esempio, sia quando si esegue il modello sui file di una raccolta documenti.</span><span class="sxs-lookup"><span data-stu-id="bc08d-126">Document understanding models use Optical Character Recognition (OCR) technology to scan PDFs, images, and TIFF files, both when you train a model with example files and when you run the model against files in a document library.</span></span>

<span data-ttu-id="bc08d-127">Notare le differenze seguenti per quanto riguarda i file basati su testo di Microsoft Office e i file digitalizzati con OCR (PDF, immagini o TIFF):</span><span class="sxs-lookup"><span data-stu-id="bc08d-127">Note the following differences in regards to Microsoft Office text-based files and OCR-scanned files (PDF, image, or TIFF):</span></span>

- <span data-ttu-id="bc08d-128">File di Office: troncamento a 64.000 caratteri (durante il training e se eseguito sui file in una raccolta documenti).</span><span class="sxs-lookup"><span data-stu-id="bc08d-128">Office files: We truncate at 64K characters (in training and when run against files in a document library).</span></span>
- <span data-ttu-id="bc08d-129">File digitalizzati con OCR: è previsto un limite di 20 pagine.</span><span class="sxs-lookup"><span data-stu-id="bc08d-129">OCR-scanned files: There is a 20 page limit.</span></span>  

#### <a name="supported-file-types"></a><span data-ttu-id="bc08d-130">Tipi di file supportati</span><span class="sxs-lookup"><span data-stu-id="bc08d-130">Supported file types</span></span>

<span data-ttu-id="bc08d-131">I modelli di analisi dei documenti supportano i tipi di file seguenti:</span><span class="sxs-lookup"><span data-stu-id="bc08d-131">Document understanding models support the following file types:</span></span>

- <span data-ttu-id="bc08d-132">doc</span><span class="sxs-lookup"><span data-stu-id="bc08d-132">doc</span></span>
- <span data-ttu-id="bc08d-133">docx</span><span class="sxs-lookup"><span data-stu-id="bc08d-133">docx</span></span>
- <span data-ttu-id="bc08d-134">eml</span><span class="sxs-lookup"><span data-stu-id="bc08d-134">eml</span></span>
- <span data-ttu-id="bc08d-135">heic</span><span class="sxs-lookup"><span data-stu-id="bc08d-135">heic</span></span>
- <span data-ttu-id="bc08d-136">heif</span><span class="sxs-lookup"><span data-stu-id="bc08d-136">heif</span></span>
- <span data-ttu-id="bc08d-137">htm</span><span class="sxs-lookup"><span data-stu-id="bc08d-137">htm</span></span>
- <span data-ttu-id="bc08d-138">html</span><span class="sxs-lookup"><span data-stu-id="bc08d-138">html</span></span>
- <span data-ttu-id="bc08d-139">jpeg</span><span class="sxs-lookup"><span data-stu-id="bc08d-139">jpeg</span></span>
- <span data-ttu-id="bc08d-140">jpg</span><span class="sxs-lookup"><span data-stu-id="bc08d-140">jpg</span></span>
- <span data-ttu-id="bc08d-141">markdown</span><span class="sxs-lookup"><span data-stu-id="bc08d-141">markdown</span></span>
- <span data-ttu-id="bc08d-142">md</span><span class="sxs-lookup"><span data-stu-id="bc08d-142">md</span></span>
- <span data-ttu-id="bc08d-143">msg</span><span class="sxs-lookup"><span data-stu-id="bc08d-143">msg</span></span>
- <span data-ttu-id="bc08d-144">pdf</span><span class="sxs-lookup"><span data-stu-id="bc08d-144">pdf</span></span>
- <span data-ttu-id="bc08d-145">png</span><span class="sxs-lookup"><span data-stu-id="bc08d-145">png</span></span>
- <span data-ttu-id="bc08d-146">ppt</span><span class="sxs-lookup"><span data-stu-id="bc08d-146">ppt</span></span>
- <span data-ttu-id="bc08d-147">pptx</span><span class="sxs-lookup"><span data-stu-id="bc08d-147">pptx</span></span>
- <span data-ttu-id="bc08d-148">rtf</span><span class="sxs-lookup"><span data-stu-id="bc08d-148">rtf</span></span>
- <span data-ttu-id="bc08d-149">tif</span><span class="sxs-lookup"><span data-stu-id="bc08d-149">tif</span></span>
- <span data-ttu-id="bc08d-150">tiff</span><span class="sxs-lookup"><span data-stu-id="bc08d-150">tiff</span></span>
- <span data-ttu-id="bc08d-151">txt</span><span class="sxs-lookup"><span data-stu-id="bc08d-151">txt</span></span>
- <span data-ttu-id="bc08d-152">xls</span><span class="sxs-lookup"><span data-stu-id="bc08d-152">xls</span></span>
- <span data-ttu-id="bc08d-153">xlsx</span><span class="sxs-lookup"><span data-stu-id="bc08d-153">xlsx</span></span>



## <a name="see-also"></a><span data-ttu-id="bc08d-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bc08d-154">See Also</span></span>
[<span data-ttu-id="bc08d-155">Creare un classificatore</span><span class="sxs-lookup"><span data-stu-id="bc08d-155">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="bc08d-156">Creare un estrattore</span><span class="sxs-lookup"><span data-stu-id="bc08d-156">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="bc08d-157">Creare un centro contenuti</span><span class="sxs-lookup"><span data-stu-id="bc08d-157">Create a content center</span></span>](create-a-content-center.md)

[<span data-ttu-id="bc08d-158">Creare un modello di elaborazione moduli</span><span class="sxs-lookup"><span data-stu-id="bc08d-158">Create a form processing model</span></span>](create-a-form-processing-model.md)

[<span data-ttu-id="bc08d-159">Applicare un modello</span><span class="sxs-lookup"><span data-stu-id="bc08d-159">Apply a model</span></span>](apply-a-model.md)   

[<span data-ttu-id="bc08d-160">Differenza tra un modello di analisi dei documenti e dell’elaborazione dei moduli</span><span class="sxs-lookup"><span data-stu-id="bc08d-160">Difference between a document understanding and a form processing model</span></span>](difference-between-document-understanding-and-form-processing-model.md)
  
[<span data-ttu-id="bc08d-161">Panoramica sull'elaborazione dei moduli</span><span class="sxs-lookup"><span data-stu-id="bc08d-161">Form processing overview</span></span>](form-processing-overview.md)

[<span data-ttu-id="bc08d-162">Modalità di accessibilità di SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="bc08d-162">SharePoint Syntex Accessibility Mode</span></span>](accessibility-mode.md)
