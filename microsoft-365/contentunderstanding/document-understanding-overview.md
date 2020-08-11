---
title: Panoramica delle informazioni sui documenti (anteprima)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 08/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Ottenere una panoramica della comprensione del documento in Project Cortex.
ms.openlocfilehash: bdebc8a8726a7b9a77eb9a1095f83e937cf36cb1
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612715"
---
# <a name="document-understanding-overview-preview"></a><span data-ttu-id="db22c-103">Panoramica delle informazioni sui documenti (anteprima)</span><span class="sxs-lookup"><span data-stu-id="db22c-103">Document understanding overview (Preview)</span></span>
> [!Note] 
> <span data-ttu-id="db22c-104">La corteccia del progetto è attualmente in anteprima.</span><span class="sxs-lookup"><span data-stu-id="db22c-104">Project Cortex is currently in Preview.</span></span> <span data-ttu-id="db22c-105">[Per ulteriori informazioni, vedere Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="db22c-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

<span data-ttu-id="db22c-106">Informazioni sui documenti vengono utilizzati i modelli AI per automatizzare la classificazione dei file e l'estrazione delle informazioni.</span><span class="sxs-lookup"><span data-stu-id="db22c-106">Document understanding uses AI models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="db22c-107">Funziona meglio con documenti non strutturati, come lettere o contratti.</span><span class="sxs-lookup"><span data-stu-id="db22c-107">It works best with unstructured documents, like letters or contracts.</span></span> <span data-ttu-id="db22c-108">I documenti devono avere testo che può essere identificato in base a frasi o modelli.</span><span class="sxs-lookup"><span data-stu-id="db22c-108">The documents should have text that can be identified based on phrases or patterns.</span></span> <span data-ttu-id="db22c-109">Il testo identificato può indicare sia il tipo di file che è (la classificazione) che quello che si desidera estrarre (gli estrattori).</span><span class="sxs-lookup"><span data-stu-id="db22c-109">The identified text can designate both the type of file it is (its classification) and what you'd like to extract (its extractors).</span></span>

<span data-ttu-id="db22c-110">I modelli di comprensione dei documenti vengono creati e gestiti in un tipo di sito di SharePoint denominato Content Center.</span><span class="sxs-lookup"><span data-stu-id="db22c-110">Document understanding models are created and managed in a type of SharePoint site called a content center.</span></span> <span data-ttu-id="db22c-111">Quando viene applicato a una raccolta documenti di SharePoint, il modello è associato a un tipo di contenuto che include colonne per archiviare le informazioni estratte.</span><span class="sxs-lookup"><span data-stu-id="db22c-111">When applied to a SharePoint document library, the model is associated with a content type which has columns to store the information extracted.</span></span> <span data-ttu-id="db22c-112">Il tipo di contenuto creato è archiviato nella raccolta tipi di contenuto di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="db22c-112">The content type you create is stored in the SharePoint content type gallery.</span></span> <span data-ttu-id="db22c-113">È inoltre possibile scegliere di utilizzare i tipi di contenuto esistenti per utilizzarne lo schema.</span><span class="sxs-lookup"><span data-stu-id="db22c-113">You can also choose to use existing content types in order to use their schema.</span></span>

<span data-ttu-id="db22c-114">È possibile aggiungere *classificatori* ed *estrattori* al documento per comprendere i modelli per eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="db22c-114">You can add *classifiers* and *extractors* to your document understanding models to do the following:</span></span> 

- <span data-ttu-id="db22c-115">I classificatori vengono utilizzati per identificare e classificare i documenti caricati nella raccolta documenti.</span><span class="sxs-lookup"><span data-stu-id="db22c-115">Classifiers are used to identify and classify documents that are uploaded to the document library.</span></span> <span data-ttu-id="db22c-116">Ad esempio, un classificatore può essere "addestrato" per identificare tutti i documenti di *rinnovo del contratto* caricati nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="db22c-116">For example, a classifier can be "trained" to identify all *contract renewal* documents that are uploaded to the library.</span></span> <span data-ttu-id="db22c-117">Il tipo di contenuto relativo al rinnovo del contratto è definito dall'utente quando si crea il classificatore.</span><span class="sxs-lookup"><span data-stu-id="db22c-117">The contract renewal content type is defined by you when you create your classifier.</span></span>

- <span data-ttu-id="db22c-118">Estrazioni estrarre informazioni da questi documenti.</span><span class="sxs-lookup"><span data-stu-id="db22c-118">Extractors pull information from these documents.</span></span> <span data-ttu-id="db22c-119">Ad esempio, per tutti i documenti di rinnovo del contratto identificati nella raccolta documenti, le colonne verranno visualizzate nella visualizzazione che mostrerà anche la *Data di inizio del servizio* e il *client* per ogni documento di rinnovo del contratto.</span><span class="sxs-lookup"><span data-stu-id="db22c-119">For example, for all contract renewal documents that are identified in your document library, columns will display in your view that will also show the *Service Start Date* and  *Client* for each contract renewal document.</span></span> 

<span data-ttu-id="db22c-120">È possibile utilizzare file di esempio per formare e testare i classificatori e gli estrattori nel modello.</span><span class="sxs-lookup"><span data-stu-id="db22c-120">You use example files to train and test your classifiers and extractors in your model.</span></span> <span data-ttu-id="db22c-121">Nei file di esempio vengono forniti esempi del modello di elementi da cercare quando si tenta di identificare ed estrarre dati dai file.</span><span class="sxs-lookup"><span data-stu-id="db22c-121">Example files provide your model examples of what to look for when trying to identify and extract data from files.</span></span> <span data-ttu-id="db22c-122">Ad esempio, è consigliabile formare i classificatori e gli estrattori del rinnovo del contratto con esempi di documenti di rinnovo del contratto che la società utilizza.</span><span class="sxs-lookup"><span data-stu-id="db22c-122">For example, you would train your contract renewal classifiers and extractors with examples of contract renewal documents your company works with.</span></span> <span data-ttu-id="db22c-123">È inoltre possibile utilizzare i file di esempio per testare l'efficacia del modello.</span><span class="sxs-lookup"><span data-stu-id="db22c-123">You can also use example files to test the effectiveness of your model.</span></span>

<span data-ttu-id="db22c-124">Dopo aver pubblicato il modello, utilizzare il centro contenuto per applicarlo a qualsiasi raccolta documenti di SharePoint a cui si ha accesso.</span><span class="sxs-lookup"><span data-stu-id="db22c-124">After publishing your model, use the content center to apply it to any SharePoint document library that you have access to.</span></span>  


## <a name="see-also"></a><span data-ttu-id="db22c-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="db22c-125">See Also</span></span>
[<span data-ttu-id="db22c-126">Creare un classificatore</span><span class="sxs-lookup"><span data-stu-id="db22c-126">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="db22c-127">Creare un estrattore</span><span class="sxs-lookup"><span data-stu-id="db22c-127">Create an extractor</span></span>](create-an-extractor.md)</br>
<span data-ttu-id="db22c-128">[Creare un centro contenuto](create-a-content-center.md) 
 [Creare un modello di elaborazione dei moduli](create-a-form-processing-model.md)</span><span class="sxs-lookup"><span data-stu-id="db22c-128">[Create a content center](create-a-content-center.md)
[Create a form processing model](create-a-form-processing-model.md)</span></span></br>
<span data-ttu-id="db22c-129">[Applicazione di un modello](apply-a-model.md) </span><span class="sxs-lookup"><span data-stu-id="db22c-129">[Apply a model](apply-a-model.md) </span></span>  
[<span data-ttu-id="db22c-130">Differenza tra una comprensione del documento e un modello di elaborazione dei moduli</span><span class="sxs-lookup"><span data-stu-id="db22c-130">Difference between a document understanding and a form processing model</span></span>](difference-between-document-understanding-and-form-processing-model.md)  
[<span data-ttu-id="db22c-131">Panoramica dell'elaborazione dei moduli</span><span class="sxs-lookup"><span data-stu-id="db22c-131">Form processing overview</span></span>](form-processing-overview.md)




