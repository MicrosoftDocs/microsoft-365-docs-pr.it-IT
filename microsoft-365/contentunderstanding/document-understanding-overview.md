---
title: Panoramica sull'analisi dei documenti
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: Ottenere una panoramica dell'analisi dei documenti in Microsoft SharePoint Syntex.
ms.openlocfilehash: 1265dfa06db323e23d63a044a1a95a6b67c525cf
ms.sourcegitcommit: b06a4f21da247edb03fdf6a01eafb7d4fb387b33
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2020
ms.locfileid: "48333559"
---
# <a name="document-understanding-overview"></a><span data-ttu-id="9d4e2-103">Panoramica sull'analisi dei documenti</span><span class="sxs-lookup"><span data-stu-id="9d4e2-103">Document understanding overview</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

<span data-ttu-id="9d4e2-104">L’analisi dei documenti utilizza modelli di intelligenza artificiale (AI) per automatizzare la classificazione dei file e l'estrazione delle informazioni.</span><span class="sxs-lookup"><span data-stu-id="9d4e2-104">Document understanding uses artificial intelligence (AI) models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="9d4e2-105">Funziona meglio con documenti non strutturati, ad esempio lettere o contratti.</span><span class="sxs-lookup"><span data-stu-id="9d4e2-105">It works best with unstructured documents, such as letters or contracts.</span></span> <span data-ttu-id="9d4e2-106">Questi documenti devono contenere un testo che possa essere identificato in base a frasi o schemi.</span><span class="sxs-lookup"><span data-stu-id="9d4e2-106">These documents must have text that can be identified based on phrases or patterns.</span></span> <span data-ttu-id="9d4e2-107">Il testo identificato designa sia il tipo di file (la classificazione) che l'elemento che si vuole estrarre (l’estrattore).</span><span class="sxs-lookup"><span data-stu-id="9d4e2-107">The identified text designates both the type of file it is (its classification) and what you'd like to extract (its extractors).</span></span>

> [!NOTE]
> <span data-ttu-id="9d4e2-108">Per altri esempi sull’analisi dei documenti, vedere[Adozione di SharePoint Syntex: guida introduttiva](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#document-understanding-scenario-example).</span><span class="sxs-lookup"><span data-stu-id="9d4e2-108">See the [SharePoint Syntex adoption: Get started guide](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#document-understanding-scenario-example) for more information about document understanding scenario examples.</span></span>

<span data-ttu-id="9d4e2-109">I modelli di analisi dei documenti vengono creati e gestiti in un tipo di sito di SharePoint denominato *centro contenuti*.</span><span class="sxs-lookup"><span data-stu-id="9d4e2-109">Document understanding models are created and managed in a type of SharePoint site called a *content center*.</span></span> <span data-ttu-id="9d4e2-110">Se applicato a una raccolta documenti di SharePoint, il modello è associato a un tipo di contenuto con colonne in cui archiviare le informazioni estratte.</span><span class="sxs-lookup"><span data-stu-id="9d4e2-110">When applied to a SharePoint document library, the model is associated with a content type has columns to store the information being extracted.</span></span> <span data-ttu-id="9d4e2-111">Il tipo di contenuto creato è archiviato nella raccolta tipi di contenuto di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="9d4e2-111">The content type you create is stored in the SharePoint content type gallery.</span></span> <span data-ttu-id="9d4e2-112">È anche possibile scegliere di usare i tipi di contenuto esistenti per usare il loro schema.</span><span class="sxs-lookup"><span data-stu-id="9d4e2-112">You can also choose to use existing content types to use their schema.</span></span>

<span data-ttu-id="9d4e2-113">Aggiungere *classificatori* ed *estrattori* ai modelli di analisi dei documento per eseguire le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="9d4e2-113">Add *classifiers* and *extractors* to your document understanding models to do the following:</span></span> 

- <span data-ttu-id="9d4e2-114">I classificatori vengono usati per identificare e classificare i documenti caricati nella raccolta documenti.</span><span class="sxs-lookup"><span data-stu-id="9d4e2-114">Classifiers are used to identify and classify documents that are uploaded to the document library.</span></span> <span data-ttu-id="9d4e2-115">Ad esempio, un classificatore può essere "addestrato" per identificare tutto i documenti di *rinnovo del contratto* caricati nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="9d4e2-115">For example, a classifier can be "trained" to identify all *contract renewal* documents that are uploaded to the library.</span></span> <span data-ttu-id="9d4e2-116">Il tipo di contenuto per il rinnovo del contratto viene definito dall'utente quando si crea il classificatore.</span><span class="sxs-lookup"><span data-stu-id="9d4e2-116">The contract renewal content type is defined by you when you create your classifier.</span></span>

- <span data-ttu-id="9d4e2-117">Gli estrattori estraggono informazioni da questi documenti.</span><span class="sxs-lookup"><span data-stu-id="9d4e2-117">Extractors pull information from these documents.</span></span> <span data-ttu-id="9d4e2-118">Ad esempio, per tutti i documenti di rinnovo del contratto identificati nella raccolta documenti, nella visualizzazione ci sono delle colonne che mostrano anche la *Data di inizio servizio* e il *Cliente* per ogni documento di rinnovo del contratto.</span><span class="sxs-lookup"><span data-stu-id="9d4e2-118">For example, for all contract renewal documents identified in your document library, columns display in your view that also show the *Service Start Date* and  *Client* for each contract renewal document.</span></span> 

<span data-ttu-id="9d4e2-119">È possibile usare i file di esempio per formare e testare i classificatori e gli estrattori nel modello.</span><span class="sxs-lookup"><span data-stu-id="9d4e2-119">You can use example files to train and test your classifiers and extractors in your model.</span></span> <span data-ttu-id="9d4e2-120">I file di esempio forniscono esempi di modelli su cosa cercare quando si prova a identificare ed estrarre dati da file.</span><span class="sxs-lookup"><span data-stu-id="9d4e2-120">Example files provide your model examples of what to look for when trying to identify and extract data from files.</span></span> <span data-ttu-id="9d4e2-121">Ad esempio, è necessario formare i classificatori e gli estrattori del rinnovo del contratto con esempi di documenti di rinnovo del contratto con cui lavora l’azienda.</span><span class="sxs-lookup"><span data-stu-id="9d4e2-121">For example, you would train your contract renewal classifiers and extractors with examples of contract renewal documents your company works with.</span></span> <span data-ttu-id="9d4e2-122">È anche possibile usare i file di esempio per testare l'efficacia del modello.</span><span class="sxs-lookup"><span data-stu-id="9d4e2-122">You can also use example files to test the effectiveness of your model.</span></span>

<span data-ttu-id="9d4e2-123">Dopo aver pubblicato il modello, usare il centro contenuto per applicarlo a qualsiasi raccolta documenti di SharePoint a cui si ha accesso.</span><span class="sxs-lookup"><span data-stu-id="9d4e2-123">After publishing your model, use the content center to apply it to any SharePoint document library that you have access to.</span></span>  



## <a name="see-also"></a><span data-ttu-id="9d4e2-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9d4e2-124">See Also</span></span>
[<span data-ttu-id="9d4e2-125">Creare un classificatore</span><span class="sxs-lookup"><span data-stu-id="9d4e2-125">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="9d4e2-126">Creare un estrattore</span><span class="sxs-lookup"><span data-stu-id="9d4e2-126">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="9d4e2-127">Creare un centro contenuti</span><span class="sxs-lookup"><span data-stu-id="9d4e2-127">Create a content center</span></span>](create-a-content-center.md)

[<span data-ttu-id="9d4e2-128">Creare un modello di elaborazione moduli</span><span class="sxs-lookup"><span data-stu-id="9d4e2-128">Create a form processing model</span></span>](create-a-form-processing-model.md)

[<span data-ttu-id="9d4e2-129">Applicare un modello</span><span class="sxs-lookup"><span data-stu-id="9d4e2-129">Apply a model</span></span>](apply-a-model.md)   

[<span data-ttu-id="9d4e2-130">Differenza tra un modello di analisi dei documenti e dell’elaborazione dei moduli</span><span class="sxs-lookup"><span data-stu-id="9d4e2-130">Difference between a document understanding and a form processing model</span></span>](difference-between-document-understanding-and-form-processing-model.md)
  
[<span data-ttu-id="9d4e2-131">Panoramica sull'elaborazione dei moduli</span><span class="sxs-lookup"><span data-stu-id="9d4e2-131">Form processing overview</span></span>](form-processing-overview.md)
