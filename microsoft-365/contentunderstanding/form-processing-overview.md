---
title: Panoramica dell'elaborazione di moduli
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
description: Informazioni sull'elaborazione di moduli in Microsoft SharePoint Syntex
ms.openlocfilehash: 84aeb7c4e3fc850e5e4c2336e576ff3bce3ecf4b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928309"
---
# <a name="form-processing-overview"></a><span data-ttu-id="35422-103">Panoramica dell'elaborazione di moduli</span><span class="sxs-lookup"><span data-stu-id="35422-103">Form processing overview</span></span>

 ![AI Builder](../media/content-understanding/ai-builder.png)</br>

<span data-ttu-id="35422-105">Microsoft SharePoint Syntex usa l’elaborazione di moduli di [AI Builder](/ai-builder/overview) in Microsoft PowerApps per creare modelli all'interno delle raccolte documenti di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="35422-105">Microsoft SharePoint Syntex uses Microsoft PowerApps [AI Builder](/ai-builder/overview) form processing to create models within SharePoint document libraries.</span></span>

<span data-ttu-id="35422-106">È possibile usare l'elaborazione dei moduli di AI Builder per creare modelli di intelligenza artificiale che usano la tecnologia di apprendimento automatico per identificare ed estrarre coppie chiave-valore e dati tabella da documenti strutturati o semi strutturati, ad esempio moduli e fatture.</span><span class="sxs-lookup"><span data-stu-id="35422-106">You can use AI Builder form processing to create AI models that use machine learning technology to identify and extract key-value pairs and table data from structured or semi-structured  documents, like forms and invoices.</span></span>

<span data-ttu-id="35422-107">Spesso le organizzazioni ricevono un gran numero di fatture da diverse origini, ad esempio via posta, fax, posta elettronica e così via. L'elaborazione di tali documenti e la loro immissione manuale in un database possono richiedere una considerevole quantità di tempo.</span><span class="sxs-lookup"><span data-stu-id="35422-107">Organizations often receive invoices in large quantities from a variety of sources, such as mail, fax, email, etc. Processing these documents and manually entering them into a database can take a considerable amount of time.</span></span> <span data-ttu-id="35422-108">Tramite l’uso dell’intelligenza artificiale, l'elaborazione dei moduli automatizza il processo di estrazione del testo, le coppie chiave-valore e le tabelle dai documenti.</span><span class="sxs-lookup"><span data-stu-id="35422-108">By using AI to extract the text, key/value pairs, and tables from your documents, form processing automates this process.</span></span> 

> [!NOTE]
> <span data-ttu-id="35422-109">Per altri esempi di scenari di elaborazione dei moduli, vedere[Adozione di SharePoint Syntex: guida introduttiva](./adoption-getstarted.md#form-processing-scenario-example).</span><span class="sxs-lookup"><span data-stu-id="35422-109">See the [SharePoint Syntex adoption: Get started guide](./adoption-getstarted.md#form-processing-scenario-example) for more information about form processing scenario examples.</span></span>

<span data-ttu-id="35422-110">Ad esempio, è possibile creare un modello di elaborazione moduli che identifichi tutti i documenti relativi agli ordini di acquisto caricati nella raccolta documenti.</span><span class="sxs-lookup"><span data-stu-id="35422-110">For example, you can create a form processing model that identifies all purchase order documents that are uploaded to the document library.</span></span> <span data-ttu-id="35422-111">Da ogni ordine di acquisto è quindi possibile estrarre e visualizzare dati specifici importanti per l'utente, come il *numero ordine d’acquisto*, la *data* o l’*ammontare totale*.</span><span class="sxs-lookup"><span data-stu-id="35422-111">From each purchase order you can then extract and display specific data that is important to you, such as *PO Number*, *Date*, or *Total Cost*.</span></span>

![Visualizzazione della raccolta documenti](../media/content-understanding/doc-lib-done.png)</br>  

<span data-ttu-id="35422-113">L’utente usa i file di esempio per eseguire il training del modello e definire le informazioni da estrarre dal modulo.</span><span class="sxs-lookup"><span data-stu-id="35422-113">You use example files to train your model and define the information to be extracted from your form.</span></span> <span data-ttu-id="35422-114">Il layout del documento viene acquisito eseguendo il training del modello.</span><span class="sxs-lookup"><span data-stu-id="35422-114">The layout of your document is learned by training your model.</span></span> <span data-ttu-id="35422-115">Per iniziare, sono necessari solo cinque moduli.</span><span class="sxs-lookup"><span data-stu-id="35422-115">You only need five form documents to get started.</span></span> <span data-ttu-id="35422-116">AI Builder analizza i file di esempio per individuare le coppie chiave-valore e l’utente può identificare manualmente quelli che non sono stati rilevati.</span><span class="sxs-lookup"><span data-stu-id="35422-116">AI Builder will analyze your example files for key-value pairs, and you can also manually identify ones that may not have been detected.</span></span>  <span data-ttu-id="35422-117">AI Builder consente di testare l’accuratezza del modello nei file di esempio.</span><span class="sxs-lookup"><span data-stu-id="35422-117">AI builder lets you test the accuracy of your model on your example files.</span></span>

<span data-ttu-id="35422-118">Dopo aver eseguito il training del modello e averlo pubblicato, quest’ultimo crea un [flusso di Power Automate](/power-automate/getting-started).</span><span class="sxs-lookup"><span data-stu-id="35422-118">After you train and publish your model, your model creates a [Power Automate Flow](/power-automate/getting-started).</span></span> <span data-ttu-id="35422-119">Il flusso viene eseguito quando un file è caricato nella raccolta documenti di SharePoint ed estrarrà i dati che sono stati identificati nel modello.</span><span class="sxs-lookup"><span data-stu-id="35422-119">The flow runs when a file is uploaded to the SharePoint document library and will extract data that has been identified in the model.</span></span> <span data-ttu-id="35422-120">I dati estratti saranno visualizzati nelle colonne di visualizzazione della raccolta documenti del modello.</span><span class="sxs-lookup"><span data-stu-id="35422-120">The extracted data will display in columns in your model's document library view.</span></span>

<span data-ttu-id="35422-121">Gli amministratori di Office 365 devono [abilitare l'elaborazione del modulo](./set-up-content-understanding.md#to-set-up-content-understanding) per la raccolta documenti di SharePoint in modo che gli utenti possano [creare un modello di elaborazione moduli](create-a-form-processing-model.md) in essa.</span><span class="sxs-lookup"><span data-stu-id="35422-121">An Office 365 admin needs to [enable Form processing](./set-up-content-understanding.md#to-set-up-content-understanding) for the SharePoint document library for users to be able to [create a form processing model](create-a-form-processing-model.md) in it.</span></span> <span data-ttu-id="35422-122">È possibile selezionare i siti durante l'installazione o dopo la configurazione nelle impostazioni di gestione.</span><span class="sxs-lookup"><span data-stu-id="35422-122">You can select the sites during setup, or after setup in your management settings.</span></span>

### <a name="file-limitations"></a><span data-ttu-id="35422-123">Limitazioni relative ai file</span><span class="sxs-lookup"><span data-stu-id="35422-123">File limitations</span></span>

<span data-ttu-id="35422-124">Quando si usano modelli di elaborazione dei moduli, assicurarsi di prendere nota dei [requisiti e delle limitazioni per l'utilizzo dei file](/ai-builder/form-processing-model-requirements).</span><span class="sxs-lookup"><span data-stu-id="35422-124">When using form processing models, make sure to note the [requirements and limitations for file usage](/ai-builder/form-processing-model-requirements).</span></span>

### <a name="multi-geo-environments"></a><span data-ttu-id="35422-125">Ambienti multi-geografici</span><span class="sxs-lookup"><span data-stu-id="35422-125">Multi-Geo environments</span></span>

<span data-ttu-id="35422-126">Quando si configura SharePoint Syntex in un [ambiente Microsoft 365 Multi-Geo](../enterprise/microsoft-365-multi-geo.md), è possibile configurarlo solo per usare l'elaborazione dei moduli nella posizione centrale.</span><span class="sxs-lookup"><span data-stu-id="35422-126">When setting up SharePoint Syntex in a [Microsoft 365 Multi-Geo environment](../enterprise/microsoft-365-multi-geo.md), you can only configure it to use form processing in the central location.</span></span> <span data-ttu-id="35422-127">Se si vuole usare l'elaborazione dei moduli in una località satellitare, contattare il supporto Microsoft.</span><span class="sxs-lookup"><span data-stu-id="35422-127">If you want to use form processing in a satellite location, contact Microsoft support.</span></span>






## <a name="see-also"></a><span data-ttu-id="35422-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="35422-128">See Also</span></span>
  
[<span data-ttu-id="35422-129">Documentazione di Power Automate</span><span class="sxs-lookup"><span data-stu-id="35422-129">Power Automate documentation</span></span>](/power-automate/)

[<span data-ttu-id="35422-130">Creare un modello di elaborazione moduli</span><span class="sxs-lookup"><span data-stu-id="35422-130">Create a form processing model</span></span>](create-a-form-processing-model.md)

[<span data-ttu-id="35422-131">Panoramica sull'analisi dei documenti</span><span class="sxs-lookup"><span data-stu-id="35422-131">Document understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="35422-132">Formazione: migliorare le prestazioni aziendali con AI Builder</span><span class="sxs-lookup"><span data-stu-id="35422-132">Training: Improve business performance with AI Builder</span></span>](/learn/paths/improve-business-performance-ai-builder/?source=learn)