---
title: Creare una richiesta di classificazione
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
description: Usa l'API REST per creare una richiesta per classificare uno o più file usando un modello di analisi dei documenti qualificato.
ms.openlocfilehash: 6a218db181368c2837d570062b6101bc3bacfb05
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904212"
---
# <a name="create-classification-request"></a><span data-ttu-id="92d10-103">Creare una richiesta di classificazione</span><span class="sxs-lookup"><span data-stu-id="92d10-103">Create classification request</span></span>

<span data-ttu-id="92d10-104">Crea una richiesta per classificare uno o più file usando il modello di analisi dei documenti applicato (vedi [esempio](rest-createclassificationrequest.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="92d10-104">Creates a request to classify one or more files using the applied document understanding model (see [example](rest-createclassificationrequest.md#examples)).</span></span>

<span data-ttu-id="92d10-105">Il servizio REST di SharePoint Online (e SharePoint 2016 e versioni successive locali) supporta la combinazione di più richieste.</span><span class="sxs-lookup"><span data-stu-id="92d10-105">The SharePoint Online (and SharePoint 2016 and later on-premises) REST service supports combining multiple requests.</span></span> <span data-ttu-id="92d10-106">Le richieste vengono combinate in un'unica chiamata al servizio usando l'opzione di query $batch OData.</span><span class="sxs-lookup"><span data-stu-id="92d10-106">Requests are combined into a single call to the service by using the OData $batch query option.</span></span> <span data-ttu-id="92d10-107">Questo metodo può essere usato per mettere in coda gli elementi di lavoro di classificazione per centinaia di documenti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="92d10-107">This method can be used to enqueue classification work items for hundreds of documents at one time.</span></span>

## <a name="http-request"></a><span data-ttu-id="92d10-108">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="92d10-108">HTTP request</span></span>

```
POST /_api/machinelearning/workItems HTTP/1.1
```
## <a name="uri-parameters"></a><span data-ttu-id="92d10-109">Parametri URI</span><span class="sxs-lookup"><span data-stu-id="92d10-109">URI Parameters</span></span>

<span data-ttu-id="92d10-110">Nessuno</span><span class="sxs-lookup"><span data-stu-id="92d10-110">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="92d10-111">Intestazioni della richiesta</span><span class="sxs-lookup"><span data-stu-id="92d10-111">Request headers</span></span>

| <span data-ttu-id="92d10-112">Intestazione</span><span class="sxs-lookup"><span data-stu-id="92d10-112">Header</span></span> | <span data-ttu-id="92d10-113">Valore</span><span class="sxs-lookup"><span data-stu-id="92d10-113">Value</span></span> |
|--------|-------|
|<span data-ttu-id="92d10-114">Accept</span><span class="sxs-lookup"><span data-stu-id="92d10-114">Accept</span></span>|<span data-ttu-id="92d10-115">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="92d10-115">application/json;odata=verbose</span></span>|
|<span data-ttu-id="92d10-116">Content-Type</span><span class="sxs-lookup"><span data-stu-id="92d10-116">Content-Type</span></span>|<span data-ttu-id="92d10-117">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="92d10-117">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="92d10-118">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="92d10-118">x-requestdigest</span></span>|<span data-ttu-id="92d10-119">Riepilogo appropriato per il sito corrente</span><span class="sxs-lookup"><span data-stu-id="92d10-119">The appropriate digest for current site</span></span>|

## <a name="request-body"></a><span data-ttu-id="92d10-120">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="92d10-120">Request body</span></span>

|<span data-ttu-id="92d10-121">Nome</span><span class="sxs-lookup"><span data-stu-id="92d10-121">Name</span></span>    |<span data-ttu-id="92d10-122">Tipo</span><span class="sxs-lookup"><span data-stu-id="92d10-122">Type</span></span>   |<span data-ttu-id="92d10-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="92d10-123">Description</span></span> |
|--------|-------|------------|
|<span data-ttu-id="92d10-124">_metadata</span><span class="sxs-lookup"><span data-stu-id="92d10-124">_metadata</span></span>|<span data-ttu-id="92d10-125">stringa</span><span class="sxs-lookup"><span data-stu-id="92d10-125">string</span></span> |<span data-ttu-id="92d10-126">Imposta i metadati dell'oggetto in SPO.</span><span class="sxs-lookup"><span data-stu-id="92d10-126">Set the object meta on the SPO.</span></span> <span data-ttu-id="92d10-127">Usare sempre il valore: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"}.</span><span class="sxs-lookup"><span data-stu-id="92d10-127">Always use the value: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"}.</span></span> |
|<span data-ttu-id="92d10-128">TargetSiteId</span><span class="sxs-lookup"><span data-stu-id="92d10-128">TargetSiteId</span></span>|<span data-ttu-id="92d10-129">guid</span><span class="sxs-lookup"><span data-stu-id="92d10-129">guid</span></span>|<span data-ttu-id="92d10-130">ID del sito in cui si trova il file da classificare.</span><span class="sxs-lookup"><span data-stu-id="92d10-130">The id of the site where the file to classify is located.</span></span>|
|<span data-ttu-id="92d10-131">TargetWebId</span><span class="sxs-lookup"><span data-stu-id="92d10-131">TargetWebId</span></span>|<span data-ttu-id="92d10-132">guid</span><span class="sxs-lookup"><span data-stu-id="92d10-132">guid</span></span>|<span data-ttu-id="92d10-133">ID della pagina Web in cui si trova il file da classificare.</span><span class="sxs-lookup"><span data-stu-id="92d10-133">The id of the web where the file to classify is located.</span></span>|
|<span data-ttu-id="92d10-134">TargetUniqueId</span><span class="sxs-lookup"><span data-stu-id="92d10-134">TargetUniqueId</span></span>|<span data-ttu-id="92d10-135">guid</span><span class="sxs-lookup"><span data-stu-id="92d10-135">guid</span></span>|<span data-ttu-id="92d10-136">ID del file da classificare.</span><span class="sxs-lookup"><span data-stu-id="92d10-136">The id of the file to classify.</span></span>|

## <a name="responses"></a><span data-ttu-id="92d10-137">Risposte</span><span class="sxs-lookup"><span data-stu-id="92d10-137">Responses</span></span>

| <span data-ttu-id="92d10-138">Nome</span><span class="sxs-lookup"><span data-stu-id="92d10-138">Name</span></span>   | <span data-ttu-id="92d10-139">Tipo</span><span class="sxs-lookup"><span data-stu-id="92d10-139">Type</span></span>  | <span data-ttu-id="92d10-140">Descrizione</span><span class="sxs-lookup"><span data-stu-id="92d10-140">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="92d10-141">201 Created</span><span class="sxs-lookup"><span data-stu-id="92d10-141">201 Created</span></span>| |<span data-ttu-id="92d10-142">Operazione completata</span><span class="sxs-lookup"><span data-stu-id="92d10-142">Success</span></span>|

## <a name="examples"></a><span data-ttu-id="92d10-143">Esempi</span><span class="sxs-lookup"><span data-stu-id="92d10-143">Examples</span></span>

### <a name="enqueue-a-request-to-classify-a-file-of-id-e6cff8b7-c90c-4564-b5b8-033449090932"></a><span data-ttu-id="92d10-144">Mettere in coda una richiesta per classificare un file con ID "e6cff8b7-c90c-4564-b5b8-033449090932"</span><span class="sxs-lookup"><span data-stu-id="92d10-144">Enqueue a request to classify a file of id "e6cff8b7-c90c-4564-b5b8-033449090932"</span></span>

#### <a name="sample-request"></a><span data-ttu-id="92d10-145">Richiesta di esempio</span><span class="sxs-lookup"><span data-stu-id="92d10-145">Sample request</span></span>

```
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"
    },
    "TargetSiteId": "f686e63b-aba7-48e5-97c7-68c4c1df292f",
    "TargetWebId": "66d6b64d-6f88-4dd9-b3db-47e6f00c53e8",
    "TargetUniqueId": "e6cff8b7-c90c-4564-b5b8-033449090932"
}
```

#### <a name="sample-response"></a><span data-ttu-id="92d10-146">Risposta di esempio</span><span class="sxs-lookup"><span data-stu-id="92d10-146">Sample response</span></span>

<span data-ttu-id="92d10-147">**Codice di stato:** 201</span><span class="sxs-lookup"><span data-stu-id="92d10-147">**Status code:** 201</span></span>

## <a name="see-also"></a><span data-ttu-id="92d10-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="92d10-148">See also</span></span>

[<span data-ttu-id="92d10-149">API REST del modello di analisi dei documenti di Syntex</span><span class="sxs-lookup"><span data-stu-id="92d10-149">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
