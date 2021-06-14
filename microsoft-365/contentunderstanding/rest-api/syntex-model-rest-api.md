---
title: API REST del modello di analisi dei documenti di SharePoint Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: reference
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: m365initiative-syntex
localization_priority: Priority
description: Panoramica dell’API REST del modello di analisi dei documenti di SharePoint Syntex.
ms.openlocfilehash: e661df76828db0d05f7c3492880259117b9f8bf1
ms.sourcegitcommit: 3e197d1ff7d8100faeaf1f5a33f1ad4ed2f72e99
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/11/2021
ms.locfileid: "52908090"
---
# <a name="sharepoint-syntex-document-understanding-model-rest-api"></a><span data-ttu-id="220ac-103">API REST del modello di analisi dei documenti di SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="220ac-103">SharePoint Syntex document understanding model REST API</span></span>

<span data-ttu-id="220ac-104">È possibile usare l'interfaccia REST di SharePoint per creare un modello di analisi dei documenti, applicare il modello a una o più raccolte o rimuoverlo e ottenere o aggiornare le informazioni sul modello.</span><span class="sxs-lookup"><span data-stu-id="220ac-104">You can use the SharePoint REST interface to create a document understanding model, apply or remove the model to one or more libraries, and obtain or update information about the model.</span></span> 

<span data-ttu-id="220ac-105">Il servizio REST di SharePoint Online (e SharePoint 2016 e versioni successive locali) supporta la combinazione di più richieste in una singola chiamata al servizio tramite l'opzione di query $batch di OData.</span><span class="sxs-lookup"><span data-stu-id="220ac-105">The SharePoint Online (and SharePoint 2016 and later on-premises) REST service supports combining multiple requests into a single call to the service by using the OData $batch query option.</span></span> 

<span data-ttu-id="220ac-106">Per informazioni dettagliate e collegamenti a esempi di codice, vedere [Effettuare richieste di batch con l'API REST](/sharepoint/dev/sp-add-ins/make-batch-requests-with-the-rest-apis).</span><span class="sxs-lookup"><span data-stu-id="220ac-106">For details and links to code samples, see [Make batch requests with the REST APIs](/sharepoint/dev/sp-add-ins/make-batch-requests-with-the-rest-apis).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="220ac-107">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="220ac-107">Prerequisites</span></span>

<span data-ttu-id="220ac-108">Prima di iniziare, è indispensabile conoscere e avere dimestichezza con quanto segue:</span><span class="sxs-lookup"><span data-stu-id="220ac-108">Before you get started, make sure that you're familiar with the following:</span></span>

- [<span data-ttu-id="220ac-109">Informazioni sul servizio REST di SharePoint</span><span class="sxs-lookup"><span data-stu-id="220ac-109">Get to know the SharePoint REST service</span></span>](/sharepoint/dev/sp-add-ins/get-to-know-the-sharepoint-rest-service) 
- [<span data-ttu-id="220ac-110">Completare le operazioni di base usando gli endpoint REST di SharePoint</span><span class="sxs-lookup"><span data-stu-id="220ac-110">Complete basic operations using SharePoint REST endpoints</span></span>](/sharepoint/dev/sp-add-ins/complete-basic-operations-using-sharepoint-rest-endpoints)

## <a name="rest-commands"></a><span data-ttu-id="220ac-111">Comandi REST</span><span class="sxs-lookup"><span data-stu-id="220ac-111">REST commands</span></span>

<span data-ttu-id="220ac-112">I comandi REST seguenti sono disponibili per l'uso con i modelli di analisi dei documenti Syntex:</span><span class="sxs-lookup"><span data-stu-id="220ac-112">The following REST commands are available for working with Syntex document understanding models:</span></span>

- <span data-ttu-id="220ac-113">[Crea un modello](rest-createmodel-method.md): crea un modello e il tipo di contenuto associato.</span><span class="sxs-lookup"><span data-stu-id="220ac-113">[Create model](rest-createmodel-method.md) – Creates a model and its associated content type.</span></span>
- <span data-ttu-id="220ac-114">[GetByUniqueId](rest-getbyuniqueid-method.md): ottiene o aggiorna le informazioni su un modello di analisi dei documenti di SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="220ac-114">[GetByUniqueId](rest-getbyuniqueid-method.md) – Gets or updates information about a SharePoint Syntex document understanding model.</span></span>
- <span data-ttu-id="220ac-115">[GetByTitle](rest-getbytitle-method.md): ottiene o aggiorna le informazioni su un modello di analisi dei documenti di SharePoint Syntex usando il titolo del modello.</span><span class="sxs-lookup"><span data-stu-id="220ac-115">[GetByTitle](rest-getbytitle-method.md) – Gets or updates information about a SharePoint Syntex document understanding model using the model title.</span></span>
- <span data-ttu-id="220ac-116">[Applica modello](rest-applymodel-method.md): applica (o sincronizza) un modello di analisi dei documenti sottoposto a training a una o più raccolte.</span><span class="sxs-lookup"><span data-stu-id="220ac-116">[Apply model](rest-applymodel-method.md) – Applies (or syncs) a trained document understanding model to one or more libraries.</span></span>
- <span data-ttu-id="220ac-117">[Ottieni informazioni su modelli e raccolte](rest-getmodelandlibraryinfo.md): ottiene informazioni su un modello e sulla raccolta in cui è stato applicato.</span><span class="sxs-lookup"><span data-stu-id="220ac-117">[Get model and library information](rest-getmodelandlibraryinfo.md) – Gets information about a model and the library where it has been applied.</span></span>
- <span data-ttu-id="220ac-118">[UpdateModelSettings](rest-updatemodelsettings-method.md): aggiorna le impostazioni dei modelli disponibili (etichetta di conservazione associata e descrizione del modello) per un modello di analisi dei documenti di SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="220ac-118">[UpdateModelSettings](rest-updatemodelsettings-method.md) – Updates available models settings (associated retention label and model description) for a SharePoint Syntex document understanding model.</span></span>
- <span data-ttu-id="220ac-119">[BatchDelete](rest-batchdelete-method.md): rimuove un modello di analisi dei documenti applicato da una o più raccolte.</span><span class="sxs-lookup"><span data-stu-id="220ac-119">[BatchDelete](rest-batchdelete-method.md) – Removes an applied document understanding model from one or more libraries.</span></span>
- <span data-ttu-id="220ac-120">[Crea una richiesta di classificazione](rest-createclassificationrequest.md): crea una richiesta per classificare uno o più file specificati usando il modello applicato.</span><span class="sxs-lookup"><span data-stu-id="220ac-120">[Create classification request](rest-createclassificationrequest.md) – Creates a request to classify a specified file or files using the applied model.</span></span>

## <a name="scenarios"></a><span data-ttu-id="220ac-121">Scenari</span><span class="sxs-lookup"><span data-stu-id="220ac-121">Scenarios</span></span>

<span data-ttu-id="220ac-122">Si noti che gli esempi di scenari seguenti non sono intuitivi dal nome del metodo.</span><span class="sxs-lookup"><span data-stu-id="220ac-122">Note the following scenario examples that aren't intuitive from the method name.</span></span> <span data-ttu-id="220ac-123">Per altre informazioni, vedere ciascun articolo.</span><span class="sxs-lookup"><span data-stu-id="220ac-123">For more information, see each article.</span></span>

<span data-ttu-id="220ac-124">Il metodo di creazione modello crea solo l'oggetto modello e il tipo di contenuto associato.</span><span class="sxs-lookup"><span data-stu-id="220ac-124">The create model method only creates the model object and its associated content type.</span></span> <span data-ttu-id="220ac-125">Prima di poterlo applicare a una raccolta, è necessario eseguire il training del modello nel Centro contenuti.</span><span class="sxs-lookup"><span data-stu-id="220ac-125">You'll need to first train the model in the content center before it can be applied to a library.</span></span>

<span data-ttu-id="220ac-126">Il metodo di applicazione del modello viene usato per configurare il modello nella raccolta di destinazione per classificare i documenti e, facoltativamente, estrarre informazioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="220ac-126">The apply model method is used to configure the model on the target library to classify documents and optionally extract additional information.</span></span> <span data-ttu-id="220ac-127">Questa API supporta anche l'applicazione in batch del modello a più raccolte.</span><span class="sxs-lookup"><span data-stu-id="220ac-127">This API also supports batch applying the model to multiple libraries.</span></span>

<span data-ttu-id="220ac-128">Il metodo di rimozione del modello rimuove semplicemente il modello da una o più raccolte in cui è stato applicato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="220ac-128">The remove model method just removes the model from one or more libraries where it was previously applied.</span></span> <span data-ttu-id="220ac-129">Per eliminare il modello, è necessario prima di tutto rimuoverlo da tutte le raccolte in cui è stato applicato.</span><span class="sxs-lookup"><span data-stu-id="220ac-129">If you want to delete the model, it must first be removed from all the libraries where it was applied.</span></span>


## <a name="see-also"></a><span data-ttu-id="220ac-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="220ac-130">See also</span></span>

[<span data-ttu-id="220ac-131">Panoramica sull’analisi dei documenti</span><span class="sxs-lookup"><span data-stu-id="220ac-131">Document understanding overview</span></span>](../document-understanding-overview.md)

