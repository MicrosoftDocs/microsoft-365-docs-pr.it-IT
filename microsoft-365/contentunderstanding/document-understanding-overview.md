---
title: Panoramica sull'analisi dei documenti
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Ottenere una panoramica dell'analisi dei documenti in Microsoft SharePoint Syntex.
ms.openlocfilehash: 7e5818a929fa0f4554a7ee4ece460b4fe0d691aa
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683824"
---
# <a name="document-understanding-overview"></a><span data-ttu-id="a2be9-103">Panoramica sull'analisi dei documenti</span><span class="sxs-lookup"><span data-stu-id="a2be9-103">Document understanding overview</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

<span data-ttu-id="a2be9-104">L’analisi dei documenti utilizza modelli di intelligenza artificiale (AI) per automatizzare la classificazione dei file e l'estrazione delle informazioni.</span><span class="sxs-lookup"><span data-stu-id="a2be9-104">Document understanding uses artificial intelligence (AI) models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="a2be9-105">Funziona meglio con documenti non strutturati, ad esempio lettere o contratti.</span><span class="sxs-lookup"><span data-stu-id="a2be9-105">It works best with unstructured documents, such as letters or contracts.</span></span> <span data-ttu-id="a2be9-106">Questi documenti devono contenere un testo che possa essere identificato in base a frasi o schemi.</span><span class="sxs-lookup"><span data-stu-id="a2be9-106">These documents must have text that can be identified based on phrases or patterns.</span></span> <span data-ttu-id="a2be9-107">Il testo identificato designa sia il tipo di file (la classificazione) che l'elemento che si vuole estrarre (l’estrattore).</span><span class="sxs-lookup"><span data-stu-id="a2be9-107">The identified text designates both the type of file it is (its classification) and what you'd like to extract (its extractors).</span></span>

> [!NOTE]
> <span data-ttu-id="a2be9-108">Per altri esempi sull’analisi dei documenti, vedere[Adozione di SharePoint Syntex: guida introduttiva](./adoption-getstarted.md).</span><span class="sxs-lookup"><span data-stu-id="a2be9-108">See the [SharePoint Syntex adoption: Get started guide](./adoption-getstarted.md) for more information about document understanding scenario examples.</span></span>

<span data-ttu-id="a2be9-109">I modelli di analisi dei documenti vengono creati e gestiti in un tipo di sito di SharePoint denominato *centro contenuti*.</span><span class="sxs-lookup"><span data-stu-id="a2be9-109">Document understanding models are created and managed in a type of SharePoint site called a *content center*.</span></span> <span data-ttu-id="a2be9-110">Se applicato a una raccolta documenti di SharePoint, il modello è associato a un tipo di contenuto con colonne in cui archiviare le informazioni estratte.</span><span class="sxs-lookup"><span data-stu-id="a2be9-110">When applied to a SharePoint document library, the model is associated with a content type has columns to store the information being extracted.</span></span> <span data-ttu-id="a2be9-111">Il tipo di contenuto creato è archiviato nella raccolta tipi di contenuto di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a2be9-111">The content type you create is stored in the SharePoint content type gallery.</span></span> <span data-ttu-id="a2be9-112">È anche possibile scegliere di usare i tipi di contenuto esistenti per usare il loro schema.</span><span class="sxs-lookup"><span data-stu-id="a2be9-112">You can also choose to use existing content types to use their schema.</span></span>

> [!NOTE]
> <span data-ttu-id="a2be9-113">I tipi di contenuto in sola lettura o sigillati non possono essere aggiornati, quindi non possono essere usati in un modello.</span><span class="sxs-lookup"><span data-stu-id="a2be9-113">Read-only or sealed content types cannot be updated, so they can't be used in a model.</span></span>

<span data-ttu-id="a2be9-114">Aggiungere *classificatori* ed *estrattori* ai modelli di analisi dei documento per eseguire le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="a2be9-114">Add *classifiers* and *extractors* to your document understanding models to do the following:</span></span> 

- <span data-ttu-id="a2be9-115">I classificatori vengono usati per identificare e classificare i documenti caricati nella raccolta documenti.</span><span class="sxs-lookup"><span data-stu-id="a2be9-115">Classifiers are used to identify and classify documents that are uploaded to the document library.</span></span> <span data-ttu-id="a2be9-116">Ad esempio, un classificatore può essere "addestrato" per identificare tutto i documenti di *rinnovo del contratto* caricati nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="a2be9-116">For example, a classifier can be "trained" to identify all *contract renewal* documents that are uploaded to the library.</span></span> <span data-ttu-id="a2be9-117">Il tipo di contenuto per il rinnovo del contratto viene definito dall'utente quando si crea il classificatore.</span><span class="sxs-lookup"><span data-stu-id="a2be9-117">The contract renewal content type is defined by you when you create your classifier.</span></span>

- <span data-ttu-id="a2be9-118">Gli estrattori estraggono informazioni da questi documenti.</span><span class="sxs-lookup"><span data-stu-id="a2be9-118">Extractors pull information from these documents.</span></span> <span data-ttu-id="a2be9-119">Ad esempio, per tutti i documenti di rinnovo del contratto identificati nella raccolta documenti, nella visualizzazione ci sono delle colonne che mostrano anche la *Data di inizio servizio* e il *Cliente* per ogni documento di rinnovo del contratto.</span><span class="sxs-lookup"><span data-stu-id="a2be9-119">For example, for all contract renewal documents identified in your document library, columns display in your view that also show the *Service Start Date* and  *Client* for each contract renewal document.</span></span> 

<span data-ttu-id="a2be9-120">È possibile usare i file di esempio per formare e testare i classificatori e gli estrattori nel modello.</span><span class="sxs-lookup"><span data-stu-id="a2be9-120">You can use example files to train and test your classifiers and extractors in your model.</span></span> <span data-ttu-id="a2be9-121">I file di esempio forniscono esempi di modelli su cosa cercare quando si prova a identificare ed estrarre dati da file.</span><span class="sxs-lookup"><span data-stu-id="a2be9-121">Example files provide your model examples of what to look for when trying to identify and extract data from files.</span></span> <span data-ttu-id="a2be9-122">Ad esempio, è necessario formare i classificatori e gli estrattori del rinnovo del contratto con esempi di documenti di rinnovo del contratto con cui lavora l’azienda.</span><span class="sxs-lookup"><span data-stu-id="a2be9-122">For example, you would train your contract renewal classifiers and extractors with examples of contract renewal documents your company works with.</span></span> <span data-ttu-id="a2be9-123">È anche possibile usare i file di esempio per testare l'efficacia del modello.</span><span class="sxs-lookup"><span data-stu-id="a2be9-123">You can also use example files to test the effectiveness of your model.</span></span>

<span data-ttu-id="a2be9-124">Dopo aver pubblicato il modello, usare il centro contenuto per applicarlo a qualsiasi raccolta documenti di SharePoint a cui si ha accesso.</span><span class="sxs-lookup"><span data-stu-id="a2be9-124">After publishing your model, use the content center to apply it to any SharePoint document library that you have access to.</span></span>  

## <a name="file-limitations"></a><span data-ttu-id="a2be9-125">Limitazioni relative ai file</span><span class="sxs-lookup"><span data-stu-id="a2be9-125">File limitations</span></span>

<span data-ttu-id="a2be9-126">I modelli di analisi dei documenti usano la tecnologia di riconoscimento ottico dei caratteri (OCR) per analizzare file PDF, immagini e file TIFF, sia quando si esegue il training di un modello con file di esempio, sia quando si esegue il modello sui file di una raccolta documenti.</span><span class="sxs-lookup"><span data-stu-id="a2be9-126">Document understanding models use Optical Character Recognition (OCR) technology to scan PDFs, images, and TIFF files, both when you train a model with example files and when you run the model against files in a document library.</span></span>

<span data-ttu-id="a2be9-127">Notare le differenze seguenti per quanto riguarda i file basati su testo di Microsoft Office e i file digitalizzati con OCR (PDF, immagini o TIFF):</span><span class="sxs-lookup"><span data-stu-id="a2be9-127">Note the following differences with regard to Microsoft Office text-based files and OCR-scanned files (PDF, image, or TIFF):</span></span>

- <span data-ttu-id="a2be9-128">File di Office: troncati a 64.000 caratteri (durante il training e se eseguito sui file in una raccolta documenti).</span><span class="sxs-lookup"><span data-stu-id="a2be9-128">Office files: Truncated at 64,000 characters (in training and when run against files in a document library).</span></span>

- <span data-ttu-id="a2be9-129">File digitalizzati con OCR: è previsto un limite di 20 pagine.</span><span class="sxs-lookup"><span data-stu-id="a2be9-129">OCR-scanned files: There's a 20-page limit.</span></span>  

### <a name="requirements"></a><span data-ttu-id="a2be9-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a2be9-130">Requirements</span></span>

<span data-ttu-id="a2be9-131">L'elaborazione OCR funziona meglio su documenti che soddisfano i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="a2be9-131">OCR processing works best on documents that meet the following requirements:</span></span>

- <span data-ttu-id="a2be9-132">Formato JPG, PNG o PDF (testo o digitalizzato).</span><span class="sxs-lookup"><span data-stu-id="a2be9-132">JPG, PNG, or PDF format (text or scanned).</span></span> <span data-ttu-id="a2be9-133">I PDF con testo incorporato sono migliori, perché non si verificheranno errori nell'estrazione e nella posizione dei caratteri.</span><span class="sxs-lookup"><span data-stu-id="a2be9-133">Text-embedded PDFs are better, because there won't be any errors in character extraction and location.</span></span>

- <span data-ttu-id="a2be9-134">Se i PDF sono protetti da password, è necessario rimuovere il blocco prima di inviarli.</span><span class="sxs-lookup"><span data-stu-id="a2be9-134">If your PDFs are password-locked, you must remove the lock before submitting them.</span></span>

- <span data-ttu-id="a2be9-135">Le dimensioni combinate dei file di documenti usati per il training non devono superare i 50 MB per ogni raccolta e i documenti PDF non devono avere più di 500 pagine.</span><span class="sxs-lookup"><span data-stu-id="a2be9-135">The combined file size of the documents used for training per collection must not exceed 50 MB, and PDF documents shouldn't have more than 500 pages.</span></span>

- <span data-ttu-id="a2be9-136">Per le immagini, le dimensioni devono essere comprese tra 50 × 50 e 10.000 × 10.000 pixel.</span><span class="sxs-lookup"><span data-stu-id="a2be9-136">For images, dimensions must be between 50 × 50 and 10,000 × 10,000 pixels.</span></span>
   > [!NOTE]
   > <span data-ttu-id="a2be9-137">Le immagini con dimensioni molto ampie o particolari, ad esempio le planimetrie dei piani, possono risultare troncate nel processo OCR e perdere l'accuratezza.</span><span class="sxs-lookup"><span data-stu-id="a2be9-137">Images that are very wide or have odd dimensions (for example, floor plans) might get truncated in the OCR process and lose accuracy.</span></span>
 
- <span data-ttu-id="a2be9-138">Per i file PDF, le dimensioni devono essere al massimo di 43 x 43 cm, corrispondente al formato carta legale o A3 o dimensioni inferiori.</span><span class="sxs-lookup"><span data-stu-id="a2be9-138">For PDF files, dimensions must be at most 17 x 17 inches, corresponding to Legal or A3 paper sizes and smaller.</span></span>

- <span data-ttu-id="a2be9-139">Se si esegue la digitalizzazione da documenti cartacei, le scansioni devono essere immagini di alta qualità.</span><span class="sxs-lookup"><span data-stu-id="a2be9-139">If scanned from paper documents, scans should be high-quality images.</span></span>

- <span data-ttu-id="a2be9-140">Occorre usare l'alfabeto latino (caratteri inglesi).</span><span class="sxs-lookup"><span data-stu-id="a2be9-140">Must use the Latin alphabet (English characters).</span></span>

> [!NOTE]
> <span data-ttu-id="a2be9-141">AI Builder al momento non supporta i tipi di dati di input per l'elaborazione di moduli seguenti:</span><span class="sxs-lookup"><span data-stu-id="a2be9-141">AI Builder doesn't currently support the following types of form processing input data:</span></span><br><span data-ttu-id="a2be9-142">- Caselle di controllo o pulsanti di opzione</span><span class="sxs-lookup"><span data-stu-id="a2be9-142">- Check boxes or radio buttons</span></span><br><span data-ttu-id="a2be9-143">- Firme</span><span class="sxs-lookup"><span data-stu-id="a2be9-143">- Signatures</span></span><br><span data-ttu-id="a2be9-144">- PDF compilabili</span><span class="sxs-lookup"><span data-stu-id="a2be9-144">- Fillable PDFs</span></span>

### <a name="supported-file-types"></a><span data-ttu-id="a2be9-145">Tipi di file supportati</span><span class="sxs-lookup"><span data-stu-id="a2be9-145">Supported file types</span></span>

<span data-ttu-id="a2be9-146">I modelli di analisi dei documenti supportano i tipi di file seguenti:</span><span class="sxs-lookup"><span data-stu-id="a2be9-146">Document understanding models support the following file types:</span></span>

- <span data-ttu-id="a2be9-147">doc</span><span class="sxs-lookup"><span data-stu-id="a2be9-147">doc</span></span>
- <span data-ttu-id="a2be9-148">docx</span><span class="sxs-lookup"><span data-stu-id="a2be9-148">docx</span></span>
- <span data-ttu-id="a2be9-149">eml</span><span class="sxs-lookup"><span data-stu-id="a2be9-149">eml</span></span>
- <span data-ttu-id="a2be9-150">heic</span><span class="sxs-lookup"><span data-stu-id="a2be9-150">heic</span></span>
- <span data-ttu-id="a2be9-151">heif</span><span class="sxs-lookup"><span data-stu-id="a2be9-151">heif</span></span>
- <span data-ttu-id="a2be9-152">htm</span><span class="sxs-lookup"><span data-stu-id="a2be9-152">htm</span></span>
- <span data-ttu-id="a2be9-153">html</span><span class="sxs-lookup"><span data-stu-id="a2be9-153">html</span></span>
- <span data-ttu-id="a2be9-154">jpeg</span><span class="sxs-lookup"><span data-stu-id="a2be9-154">jpeg</span></span>
- <span data-ttu-id="a2be9-155">jpg</span><span class="sxs-lookup"><span data-stu-id="a2be9-155">jpg</span></span>
- <span data-ttu-id="a2be9-156">markdown</span><span class="sxs-lookup"><span data-stu-id="a2be9-156">markdown</span></span>
- <span data-ttu-id="a2be9-157">md</span><span class="sxs-lookup"><span data-stu-id="a2be9-157">md</span></span>
- <span data-ttu-id="a2be9-158">msg</span><span class="sxs-lookup"><span data-stu-id="a2be9-158">msg</span></span>
- <span data-ttu-id="a2be9-159">pdf</span><span class="sxs-lookup"><span data-stu-id="a2be9-159">pdf</span></span>
- <span data-ttu-id="a2be9-160">png</span><span class="sxs-lookup"><span data-stu-id="a2be9-160">png</span></span>
- <span data-ttu-id="a2be9-161">ppt</span><span class="sxs-lookup"><span data-stu-id="a2be9-161">ppt</span></span>
- <span data-ttu-id="a2be9-162">pptx</span><span class="sxs-lookup"><span data-stu-id="a2be9-162">pptx</span></span>
- <span data-ttu-id="a2be9-163">rtf</span><span class="sxs-lookup"><span data-stu-id="a2be9-163">rtf</span></span>
- <span data-ttu-id="a2be9-164">tif</span><span class="sxs-lookup"><span data-stu-id="a2be9-164">tif</span></span>
- <span data-ttu-id="a2be9-165">tiff</span><span class="sxs-lookup"><span data-stu-id="a2be9-165">tiff</span></span>
- <span data-ttu-id="a2be9-166">txt</span><span class="sxs-lookup"><span data-stu-id="a2be9-166">txt</span></span>
- <span data-ttu-id="a2be9-167">xls</span><span class="sxs-lookup"><span data-stu-id="a2be9-167">xls</span></span>
- <span data-ttu-id="a2be9-168">xlsx</span><span class="sxs-lookup"><span data-stu-id="a2be9-168">xlsx</span></span>



## <a name="see-also"></a><span data-ttu-id="a2be9-169">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a2be9-169">See Also</span></span>
[<span data-ttu-id="a2be9-170">Creare un classificatore</span><span class="sxs-lookup"><span data-stu-id="a2be9-170">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="a2be9-171">Creare un estrattore</span><span class="sxs-lookup"><span data-stu-id="a2be9-171">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="a2be9-172">Creare un centro contenuti</span><span class="sxs-lookup"><span data-stu-id="a2be9-172">Create a content center</span></span>](create-a-content-center.md)

[<span data-ttu-id="a2be9-173">Creare un modello di elaborazione moduli</span><span class="sxs-lookup"><span data-stu-id="a2be9-173">Create a form processing model</span></span>](create-a-form-processing-model.md)

[<span data-ttu-id="a2be9-174">Applicare un modello</span><span class="sxs-lookup"><span data-stu-id="a2be9-174">Apply a model</span></span>](apply-a-model.md)   

[<span data-ttu-id="a2be9-175">Differenza tra un modello di analisi dei documenti e dell’elaborazione dei moduli</span><span class="sxs-lookup"><span data-stu-id="a2be9-175">Difference between a document understanding and a form processing model</span></span>](difference-between-document-understanding-and-form-processing-model.md)
  
[<span data-ttu-id="a2be9-176">Panoramica sull'elaborazione dei moduli</span><span class="sxs-lookup"><span data-stu-id="a2be9-176">Form processing overview</span></span>](form-processing-overview.md)

[<span data-ttu-id="a2be9-177">Modalità di accessibilità di SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="a2be9-177">SharePoint Syntex Accessibility Mode</span></span>](accessibility-mode.md)