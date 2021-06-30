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
ms.openlocfilehash: 3a796bcdb38a9a6930b51f7d585febb69082732e
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177082"
---
# <a name="create-classification-request"></a><span data-ttu-id="8890d-103">Creare una richiesta di classificazione</span><span class="sxs-lookup"><span data-stu-id="8890d-103">Create classification request</span></span>

<span data-ttu-id="8890d-104">Crea una richiesta per classificare uno o più file usando il modello di analisi dei documenti applicato (vedi [esempio](rest-createclassificationrequest.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="8890d-104">Creates a request to classify one or more files using the applied document understanding model (see [example](rest-createclassificationrequest.md#examples)).</span></span>

<span data-ttu-id="8890d-105">Il servizio REST di SharePoint Online (e SharePoint 2016 e versioni successive locali) supporta la combinazione di più richieste.</span><span class="sxs-lookup"><span data-stu-id="8890d-105">The SharePoint Online (and SharePoint 2016 and later on-premises) REST service supports combining multiple requests.</span></span> <span data-ttu-id="8890d-106">Le richieste vengono combinate in un'unica chiamata al servizio usando l'opzione di query $batch OData.</span><span class="sxs-lookup"><span data-stu-id="8890d-106">Requests are combined into a single call to the service by using the OData $batch query option.</span></span> <span data-ttu-id="8890d-107">Questo metodo può essere usato per mettere in coda gli elementi di lavoro di classificazione per centinaia di documenti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="8890d-107">This method can be used to enqueue classification work items for hundreds of documents at one time.</span></span>

## <a name="http-request"></a><span data-ttu-id="8890d-108">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="8890d-108">HTTP request</span></span>

```
POST /_api/machinelearning/workItems HTTP/1.1
```
## <a name="uri-parameters"></a><span data-ttu-id="8890d-109">Parametri URI</span><span class="sxs-lookup"><span data-stu-id="8890d-109">URI Parameters</span></span>

<span data-ttu-id="8890d-110">Nessuno</span><span class="sxs-lookup"><span data-stu-id="8890d-110">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="8890d-111">Intestazioni della richiesta</span><span class="sxs-lookup"><span data-stu-id="8890d-111">Request headers</span></span>

| <span data-ttu-id="8890d-112">Intestazione</span><span class="sxs-lookup"><span data-stu-id="8890d-112">Header</span></span> | <span data-ttu-id="8890d-113">Valore</span><span class="sxs-lookup"><span data-stu-id="8890d-113">Value</span></span> |
|--------|-------|
|<span data-ttu-id="8890d-114">Accept</span><span class="sxs-lookup"><span data-stu-id="8890d-114">Accept</span></span>|<span data-ttu-id="8890d-115">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="8890d-115">application/json;odata=verbose</span></span>|
|<span data-ttu-id="8890d-116">Content-Type</span><span class="sxs-lookup"><span data-stu-id="8890d-116">Content-Type</span></span>|<span data-ttu-id="8890d-117">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="8890d-117">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="8890d-118">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="8890d-118">x-requestdigest</span></span>|<span data-ttu-id="8890d-119">Riepilogo appropriato per il sito corrente</span><span class="sxs-lookup"><span data-stu-id="8890d-119">The appropriate digest for current site</span></span>|

## <a name="request-body"></a><span data-ttu-id="8890d-120">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="8890d-120">Request body</span></span>

|<span data-ttu-id="8890d-121">Nome</span><span class="sxs-lookup"><span data-stu-id="8890d-121">Name</span></span>    |<span data-ttu-id="8890d-122">Tipo</span><span class="sxs-lookup"><span data-stu-id="8890d-122">Type</span></span>   |<span data-ttu-id="8890d-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8890d-123">Description</span></span> |
|--------|-------|------------|
|<span data-ttu-id="8890d-124">_metadata</span><span class="sxs-lookup"><span data-stu-id="8890d-124">_metadata</span></span>|<span data-ttu-id="8890d-125">stringa</span><span class="sxs-lookup"><span data-stu-id="8890d-125">string</span></span> |<span data-ttu-id="8890d-126">Imposta i metadati dell'oggetto in SPO.</span><span class="sxs-lookup"><span data-stu-id="8890d-126">Set the object meta on the SPO.</span></span> <span data-ttu-id="8890d-127">Usare sempre il valore: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningWorkItemEntityData"}.</span><span class="sxs-lookup"><span data-stu-id="8890d-127">Always use the value: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningWorkItemEntityData"}.</span></span> |
|<span data-ttu-id="8890d-128">TargetSiteId</span><span class="sxs-lookup"><span data-stu-id="8890d-128">TargetSiteId</span></span>|<span data-ttu-id="8890d-129">guid</span><span class="sxs-lookup"><span data-stu-id="8890d-129">guid</span></span>|<span data-ttu-id="8890d-130">ID del sito in cui si trova il file da classificare.</span><span class="sxs-lookup"><span data-stu-id="8890d-130">The id of the site where the file to classify is located.</span></span>|
|<span data-ttu-id="8890d-131">TargetWebId</span><span class="sxs-lookup"><span data-stu-id="8890d-131">TargetWebId</span></span>|<span data-ttu-id="8890d-132">guid</span><span class="sxs-lookup"><span data-stu-id="8890d-132">guid</span></span>|<span data-ttu-id="8890d-133">ID della pagina Web in cui si trova il file da classificare.</span><span class="sxs-lookup"><span data-stu-id="8890d-133">The id of the web where the file to classify is located.</span></span>|
|<span data-ttu-id="8890d-134">TargetUniqueId</span><span class="sxs-lookup"><span data-stu-id="8890d-134">TargetUniqueId</span></span>|<span data-ttu-id="8890d-135">guid</span><span class="sxs-lookup"><span data-stu-id="8890d-135">guid</span></span>|<span data-ttu-id="8890d-136">ID del file da classificare.</span><span class="sxs-lookup"><span data-stu-id="8890d-136">The id of the file to classify.</span></span>|

## <a name="responses"></a><span data-ttu-id="8890d-137">Risposte</span><span class="sxs-lookup"><span data-stu-id="8890d-137">Responses</span></span>

| <span data-ttu-id="8890d-138">Nome</span><span class="sxs-lookup"><span data-stu-id="8890d-138">Name</span></span>   | <span data-ttu-id="8890d-139">Tipo</span><span class="sxs-lookup"><span data-stu-id="8890d-139">Type</span></span>  | <span data-ttu-id="8890d-140">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8890d-140">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="8890d-141">201 Created</span><span class="sxs-lookup"><span data-stu-id="8890d-141">201 Created</span></span>| |<span data-ttu-id="8890d-142">Operazione completata</span><span class="sxs-lookup"><span data-stu-id="8890d-142">Success</span></span>|

## <a name="examples"></a><span data-ttu-id="8890d-143">Esempi</span><span class="sxs-lookup"><span data-stu-id="8890d-143">Examples</span></span>

### <a name="enqueue-a-request-to-classify-a-file-of-id-e6cff8b7-c90c-4564-b5b8-033449090932"></a><span data-ttu-id="8890d-144">Mettere in coda una richiesta per classificare un file con ID "e6cff8b7-c90c-4564-b5b8-033449090932"</span><span class="sxs-lookup"><span data-stu-id="8890d-144">Enqueue a request to classify a file of id "e6cff8b7-c90c-4564-b5b8-033449090932"</span></span>

#### <a name="sample-request"></a><span data-ttu-id="8890d-145">Richiesta di esempio</span><span class="sxs-lookup"><span data-stu-id="8890d-145">Sample request</span></span>

```
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningWorkItemEntityData"
    },
    "TargetSiteId": "f686e63b-aba7-48e5-97c7-68c4c1df292f",
    "TargetWebId": "66d6b64d-6f88-4dd9-b3db-47e6f00c53e8",
    "TargetUniqueId": "e6cff8b7-c90c-4564-b5b8-033449090932"
}
```

#### <a name="sample-response"></a><span data-ttu-id="8890d-146">Risposta di esempio</span><span class="sxs-lookup"><span data-stu-id="8890d-146">Sample response</span></span>

<span data-ttu-id="8890d-147">**Codice di stato:** 201</span><span class="sxs-lookup"><span data-stu-id="8890d-147">**Status code:** 201</span></span>

## <a name="see-also"></a><span data-ttu-id="8890d-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8890d-148">See also</span></span>

[<span data-ttu-id="8890d-149">API REST del modello di analisi dei documenti di Syntex</span><span class="sxs-lookup"><span data-stu-id="8890d-149">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
