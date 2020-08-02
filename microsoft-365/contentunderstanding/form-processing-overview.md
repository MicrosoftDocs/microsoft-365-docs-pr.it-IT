---
title: Panoramica dell'elaborazione dei moduli (anteprima)
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
description: Informazioni sull'elaborazione dei moduli in Project Cortex.
ms.openlocfilehash: 9709c8170f5dc6ce0edbeb2d90cb4e1f6d759c64
ms.sourcegitcommit: 3a47efcbdf3d2b39caa2798ea5be806839b05ed1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/01/2020
ms.locfileid: "46540059"
---
# <a name="form-processing-overview-preview"></a><span data-ttu-id="077a8-103">Panoramica dell'elaborazione dei moduli (anteprima)</span><span class="sxs-lookup"><span data-stu-id="077a8-103">Form Processing overview (Preview)</span></span>
> [!Note]
> <span data-ttu-id="077a8-104">Il contenuto di questo articolo è relativo all'anteprima privata di Project Cortex.</span><span class="sxs-lookup"><span data-stu-id="077a8-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="077a8-105">[Per ulteriori informazioni, vedere Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="077a8-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="077a8-106">Project Cortex utilizza l'elaborazione dei moduli di Microsoft PowerApps [ai Builder](https://docs.microsoft.com/ai-builder/overview) per creare modelli all'interno delle raccolte documenti di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="077a8-106">Project Cortex uses Microsoft PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview) form processing to create models within SharePoint document libraries.</span></span>
<span data-ttu-id="077a8-107">È possibile utilizzare l'elaborazione dei moduli di AI Builder per creare modelli AI che utilizzano la tecnologia di apprendimento automatico per identificare ed estrarre le coppie chiave/valore e i dati di tabella da documenti strutturati o semistrutturati, come la maschera e le fatture.</span><span class="sxs-lookup"><span data-stu-id="077a8-107">You can use AI Builder form processing to create AI models that use machine learning technology to identify and extract key-value pairs and table data from structured or semi-structured  documents, like form and invoices.</span></span>

<span data-ttu-id="077a8-108">Le aziende spesso ricevono fatture in grandi quantità e da una vasta gamma di fonti, come posta elettronica, fax, posta elettronica o di persona.</span><span class="sxs-lookup"><span data-stu-id="077a8-108">Companies often receive invoices in large quantities and from a variety of sources, such as mail, fax, email, or in person.</span></span> <span data-ttu-id="077a8-109">L'elaborazione di questi documenti e l'immissione manuale nel database può richiedere molto tempo.</span><span class="sxs-lookup"><span data-stu-id="077a8-109">Processing these documents and manually entering them into your database can take a considerable amount of time.</span></span> <span data-ttu-id="077a8-110">Utilizzando Ia per estrarre le coppie testo, chiave/valore e le tabelle dei documenti, l'elaborazione dei moduli automatizza questo processo.</span><span class="sxs-lookup"><span data-stu-id="077a8-110">By using AI to extract the text, key/value pairs, and tables from your documents, form processing will automate this process.</span></span> 

<span data-ttu-id="077a8-111">Ad esempio, è possibile creare un modello di elaborazione dei moduli che identifichi tutti i documenti degli ordini di acquisto caricati nella raccolta documenti.</span><span class="sxs-lookup"><span data-stu-id="077a8-111">For example, you can create a form processing model that will identify all purchase order documents that are uploaded to the document library.</span></span> <span data-ttu-id="077a8-112">E da ogni ordine di acquisto è possibile estrarre e visualizzare dati specifici che sono importanti per l'utente, ad esempio il *numero di po*, la *Data*o il *costo totale*.</span><span class="sxs-lookup"><span data-stu-id="077a8-112">And from each purchase order you can extract and display specific data that is important to you, such as *PO Number*, *Date*, or *Total Cost*.</span></span>

<span data-ttu-id="077a8-113">È possibile utilizzare file di esempio per formare il modello e definire le informazioni da estrarre dal modulo.</span><span class="sxs-lookup"><span data-stu-id="077a8-113">You use example files to train your model and define the information to be extracted from your form.</span></span> <span data-ttu-id="077a8-114">Il layout del documento viene imparato mediante la formazione del modello.</span><span class="sxs-lookup"><span data-stu-id="077a8-114">The layout of your document is learned by training your model.</span></span> <span data-ttu-id="077a8-115">Per iniziare, sono necessari solo cinque documenti del modulo.</span><span class="sxs-lookup"><span data-stu-id="077a8-115">You only need five form documents to get started.</span></span> <span data-ttu-id="077a8-116">AI Building analizzerà i file di esempio per le coppie chiave-valore ed è anche possibile identificare manualmente quelli che potrebbero non essere stati rilevati.</span><span class="sxs-lookup"><span data-stu-id="077a8-116">AI building will analyze your example files for key-value pairs, and you can also manually identify ones that may not have been detected.</span></span>  <span data-ttu-id="077a8-117">AI Builder è possibile testare l'accuratezza del modello nei file di esempio.</span><span class="sxs-lookup"><span data-stu-id="077a8-117">AI builder lets you test the accuracy of your model on your sample files.</span></span>

<span data-ttu-id="077a8-118">Dopo aver eseguito la formazione e la pubblicazione del modello, per utilizzarlo è necessario creare un [flusso automatico di alimentazione automatizzato](https://docs.microsoft.com/power-automate/getting-started) che verrà utilizzato quando un file viene caricato nella raccolta documenti di SharePoint e verranno estratti i dati che sono stati identificati nel modello.</span><span class="sxs-lookup"><span data-stu-id="077a8-118">After you train and publish your model, to use it you create a [Power Automate Flow](https://docs.microsoft.com/power-automate/getting-started) that will run when a file is uploaded to the SharePoint document library and will extract data that has been identified in the model.</span></span> <span data-ttu-id="077a8-119">I dati estratti verranno visualizzati nelle colonne della visualizzazione raccolta documenti del modello.</span><span class="sxs-lookup"><span data-stu-id="077a8-119">The extracted data will display in columns in your model's document library view.</span></span>

<span data-ttu-id="077a8-120">Un amministratore di Office 365 deve [abilitare l'elaborazione dei moduli](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding?view=o365-worldwide#to-set-up-content-understanding) per la raccolta documenti di SharePoint affinché gli utenti siano in grado di [creare un modello di elaborazione dei moduli](create-a-form-processing-model.md) .</span><span class="sxs-lookup"><span data-stu-id="077a8-120">An Office 365 admin needs to [enable Form processing](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding?view=o365-worldwide#to-set-up-content-understanding) for the SharePoint document library for users to be able to [create a form processing model](create-a-form-processing-model.md) in it.</span></span>



## <a name="see-also"></a><span data-ttu-id="077a8-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="077a8-121">See Also</span></span>
  
[<span data-ttu-id="077a8-122">Documentazione su Power automatizzate</span><span class="sxs-lookup"><span data-stu-id="077a8-122">Power Automate documentation</span></span>](https://docs.microsoft.com/power-automate/)</br>
[<span data-ttu-id="077a8-123">Creare un modello di elaborazione dei moduli</span><span class="sxs-lookup"><span data-stu-id="077a8-123">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>
[<span data-ttu-id="077a8-124">Panoramica della comprensione del documento</span><span class="sxs-lookup"><span data-stu-id="077a8-124">Document understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="077a8-125">Formazione: migliorare le prestazioni aziendali con AI Builder</span><span class="sxs-lookup"><span data-stu-id="077a8-125">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>




