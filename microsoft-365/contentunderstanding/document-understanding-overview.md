---
title: Panoramica della comprensione del documento
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 08/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Ottenere una panoramica della comprensione del documento in Microsoft SharePoint Syntex.
ms.openlocfilehash: dd8731759d8f1cbea57d171fa7a803ffc4f1baa7
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294761"
---
# <a name="document-understanding-overview"></a><span data-ttu-id="121dd-103">Panoramica della comprensione del documento</span><span class="sxs-lookup"><span data-stu-id="121dd-103">Document understanding overview</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

<span data-ttu-id="121dd-104">Informazioni sui documenti vengono utilizzati modelli di intelligenza artificiale (AI) per automatizzare la classificazione dei file e l'estrazione delle informazioni.</span><span class="sxs-lookup"><span data-stu-id="121dd-104">Document understanding uses artificial intelligence (AI) models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="121dd-105">Funziona meglio con documenti non strutturati, ad esempio lettere o contratti.</span><span class="sxs-lookup"><span data-stu-id="121dd-105">It works best with unstructured documents, such as letters or contracts.</span></span> <span data-ttu-id="121dd-106">Questi documenti devono avere testo che può essere identificato in base a frasi o modelli.</span><span class="sxs-lookup"><span data-stu-id="121dd-106">These documents must have text that can be identified based on phrases or patterns.</span></span> <span data-ttu-id="121dd-107">Il testo identificato designa sia il tipo di file che è (la classificazione) che quello che si desidera estrarre (gli estrattori).</span><span class="sxs-lookup"><span data-stu-id="121dd-107">The identified text designates both the type of file it is (its classification) and what you'd like to extract (its extractors).</span></span>

<span data-ttu-id="121dd-108">I modelli di comprensione dei documenti vengono creati e gestiti in un tipo di sito di SharePoint denominato *Content Center*.</span><span class="sxs-lookup"><span data-stu-id="121dd-108">Document understanding models are created and managed in a type of SharePoint site called a *content center*.</span></span> <span data-ttu-id="121dd-109">Quando viene applicato a una raccolta documenti di SharePoint, il modello è associato a un tipo di contenuto con colonne in cui archiviare le informazioni estratte.</span><span class="sxs-lookup"><span data-stu-id="121dd-109">When applied to a SharePoint document library, the model is associated with a content type has columns to store the information being extracted.</span></span> <span data-ttu-id="121dd-110">Il tipo di contenuto creato è archiviato nella raccolta tipi di contenuto di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="121dd-110">The content type you create is stored in the SharePoint content type gallery.</span></span> <span data-ttu-id="121dd-111">È inoltre possibile scegliere di utilizzare i tipi di contenuto esistenti per utilizzarne lo schema.</span><span class="sxs-lookup"><span data-stu-id="121dd-111">You can also choose to use existing content types to use their schema.</span></span>

<span data-ttu-id="121dd-112">Aggiungere *classificatori* ed *estrattori* al documento informazioni sui modelli per eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="121dd-112">Add *classifiers* and *extractors* to your document understanding models to do the following:</span></span> 

- <span data-ttu-id="121dd-113">I classificatori vengono utilizzati per identificare e classificare i documenti caricati nella raccolta documenti.</span><span class="sxs-lookup"><span data-stu-id="121dd-113">Classifiers are used to identify and classify documents that are uploaded to the document library.</span></span> <span data-ttu-id="121dd-114">Ad esempio, un classificatore può essere "addestrato" per identificare tutti i documenti di *rinnovo del contratto* caricati nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="121dd-114">For example, a classifier can be "trained" to identify all *contract renewal* documents that are uploaded to the library.</span></span> <span data-ttu-id="121dd-115">Il tipo di contenuto relativo al rinnovo del contratto è definito dall'utente quando si crea il classificatore.</span><span class="sxs-lookup"><span data-stu-id="121dd-115">The contract renewal content type is defined by you when you create your classifier.</span></span>

- <span data-ttu-id="121dd-116">Estrazioni estrarre informazioni da questi documenti.</span><span class="sxs-lookup"><span data-stu-id="121dd-116">Extractors pull information from these documents.</span></span> <span data-ttu-id="121dd-117">Ad esempio, per tutti i documenti di rinnovo del contratto identificati nella raccolta documenti, le colonne vengono visualizzate nella visualizzazione che mostrano anche la *Data di inizio del servizio* e il  *client* per ogni documento di rinnovo del contratto.</span><span class="sxs-lookup"><span data-stu-id="121dd-117">For example, for all contract renewal documents identified in your document library, columns display in your view that also show the *Service Start Date* and  *Client* for each contract renewal document.</span></span> 

<span data-ttu-id="121dd-118">È possibile utilizzare i file di esempio per formare e testare i classificatori e gli estrattori nel modello.</span><span class="sxs-lookup"><span data-stu-id="121dd-118">You can use sample files to train and test your classifiers and extractors in your model.</span></span> <span data-ttu-id="121dd-119">I file di esempio forniscono agli esempi di modello gli elementi da cercare quando si tenta di identificare ed estrarre dati dai file.</span><span class="sxs-lookup"><span data-stu-id="121dd-119">Sample files provide your model examples of what to look for when trying to identify and extract data from files.</span></span> <span data-ttu-id="121dd-120">Ad esempio, è consigliabile formare i classificatori e gli estrattori del rinnovo del contratto con esempi di documenti di rinnovo del contratto con cui la società lavora.</span><span class="sxs-lookup"><span data-stu-id="121dd-120">For example, you would train your contract renewal classifiers and extractors with samples of contract renewal documents your company works with.</span></span> <span data-ttu-id="121dd-121">È inoltre possibile utilizzare i file di esempio per testare l'efficacia del modello.</span><span class="sxs-lookup"><span data-stu-id="121dd-121">You can also use sample files to test the effectiveness of your model.</span></span>

<span data-ttu-id="121dd-122">Dopo aver pubblicato il modello, utilizzare il centro contenuto per applicarlo a qualsiasi raccolta documenti di SharePoint a cui si ha accesso.</span><span class="sxs-lookup"><span data-stu-id="121dd-122">After publishing your model, use the content center to apply it to any SharePoint document library that you have access to.</span></span>  


## <a name="see-also"></a><span data-ttu-id="121dd-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="121dd-123">See Also</span></span>
[<span data-ttu-id="121dd-124">Creare un classificatore</span><span class="sxs-lookup"><span data-stu-id="121dd-124">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="121dd-125">Creare un estrattore</span><span class="sxs-lookup"><span data-stu-id="121dd-125">Create an extractor</span></span>](create-an-extractor.md)</br>
<span data-ttu-id="121dd-126">[Creare un centro contenuto](create-a-content-center.md) 
 [Creare un modello di elaborazione dei moduli](create-a-form-processing-model.md)</span><span class="sxs-lookup"><span data-stu-id="121dd-126">[Create a content center](create-a-content-center.md)
[Create a form processing model](create-a-form-processing-model.md)</span></span></br>
<span data-ttu-id="121dd-127">[Applicazione di un modello](apply-a-model.md) </span><span class="sxs-lookup"><span data-stu-id="121dd-127">[Apply a model](apply-a-model.md) </span></span>  
[<span data-ttu-id="121dd-128">Differenza tra una comprensione del documento e un modello di elaborazione dei moduli</span><span class="sxs-lookup"><span data-stu-id="121dd-128">Difference between a document understanding and a form processing model</span></span>](difference-between-document-understanding-and-form-processing-model.md)  
[<span data-ttu-id="121dd-129">Panoramica dell'elaborazione dei moduli</span><span class="sxs-lookup"><span data-stu-id="121dd-129">Form processing overview</span></span>](form-processing-overview.md)
