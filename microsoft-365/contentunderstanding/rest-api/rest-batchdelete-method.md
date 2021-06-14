---
title: BatchDelete
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
description: Usa l'API REST per rimuovere un modello di analisi dei documenti applicato da una o più raccolte.
ms.openlocfilehash: 8c7aeb449da161fe49050631643c63c93268a13f
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904211"
---
# <a name="batchdelete"></a><span data-ttu-id="7c5d9-103">BatchDelete</span><span class="sxs-lookup"><span data-stu-id="7c5d9-103">BatchDelete</span></span>

<span data-ttu-id="7c5d9-104">Rimuove un modello di analisi dei documenti applicato da una o più raccolte.</span><span class="sxs-lookup"><span data-stu-id="7c5d9-104">Removes an applied document understanding model from one or more libraries.</span></span> <span data-ttu-id="7c5d9-105">Nota che un modello deve essere rimosso da tutte le raccolte prima di essere eliminato (vedi [esempio](rest-batchdelete-method.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="7c5d9-105">Note that a model must be removed from all libraries before it can be deleted (see [example](rest-batchdelete-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="7c5d9-106">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="7c5d9-106">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/publications/batchdelete HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="7c5d9-107">Parametri URI</span><span class="sxs-lookup"><span data-stu-id="7c5d9-107">URI parameters</span></span>

<span data-ttu-id="7c5d9-108">Nessuno</span><span class="sxs-lookup"><span data-stu-id="7c5d9-108">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="7c5d9-109">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="7c5d9-109">Request headers</span></span>

| <span data-ttu-id="7c5d9-110">Intestazione</span><span class="sxs-lookup"><span data-stu-id="7c5d9-110">Header</span></span> | <span data-ttu-id="7c5d9-111">Valore</span><span class="sxs-lookup"><span data-stu-id="7c5d9-111">Value</span></span> |
|--------|-------|
|<span data-ttu-id="7c5d9-112">Accetta</span><span class="sxs-lookup"><span data-stu-id="7c5d9-112">Accept</span></span>|<span data-ttu-id="7c5d9-113">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="7c5d9-113">application/json;odata=verbose</span></span>|
|<span data-ttu-id="7c5d9-114">Content-Type</span><span class="sxs-lookup"><span data-stu-id="7c5d9-114">Content-Type</span></span>|<span data-ttu-id="7c5d9-115">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="7c5d9-115">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="7c5d9-116">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="7c5d9-116">x-requestdigest</span></span>|<span data-ttu-id="7c5d9-117">Digest appropriato per il sito corrente.</span><span class="sxs-lookup"><span data-stu-id="7c5d9-117">The appropriate digest for current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="7c5d9-118">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="7c5d9-118">Request body</span></span>

| <span data-ttu-id="7c5d9-119">Nome</span><span class="sxs-lookup"><span data-stu-id="7c5d9-119">Name</span></span> | <span data-ttu-id="7c5d9-120">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="7c5d9-120">Required</span></span> | <span data-ttu-id="7c5d9-121">Tipo</span><span class="sxs-lookup"><span data-stu-id="7c5d9-121">Type</span></span> | <span data-ttu-id="7c5d9-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7c5d9-122">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="7c5d9-123">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="7c5d9-123">ModelUniqueId</span></span>|<span data-ttu-id="7c5d9-124">sì</span><span class="sxs-lookup"><span data-stu-id="7c5d9-124">yes</span></span>|<span data-ttu-id="7c5d9-125">stringa</span><span class="sxs-lookup"><span data-stu-id="7c5d9-125">string</span></span>|<span data-ttu-id="7c5d9-126">ID univoco del file di modello.</span><span class="sxs-lookup"><span data-stu-id="7c5d9-126">The unique ID of the model file.</span></span>|
<span data-ttu-id="7c5d9-127">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="7c5d9-127">TargetSiteUrl</span></span>|<span data-ttu-id="7c5d9-128">sì</span><span class="sxs-lookup"><span data-stu-id="7c5d9-128">yes</span></span>|<span data-ttu-id="7c5d9-129">stringa</span><span class="sxs-lookup"><span data-stu-id="7c5d9-129">string</span></span>|<span data-ttu-id="7c5d9-130">URL completo del sito della raccolta di destinazione.</span><span class="sxs-lookup"><span data-stu-id="7c5d9-130">The full URL of the target library site.</span></span>|
<span data-ttu-id="7c5d9-131">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="7c5d9-131">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="7c5d9-132">sì</span><span class="sxs-lookup"><span data-stu-id="7c5d9-132">yes</span></span>|<span data-ttu-id="7c5d9-133">stringa</span><span class="sxs-lookup"><span data-stu-id="7c5d9-133">string</span></span>|<span data-ttu-id="7c5d9-134">URL relativo al server Web per la raccolta di destinazione.</span><span class="sxs-lookup"><span data-stu-id="7c5d9-134">The server relative URL of the web for the target library.</span></span>|
<span data-ttu-id="7c5d9-135">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="7c5d9-135">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="7c5d9-136">sì</span><span class="sxs-lookup"><span data-stu-id="7c5d9-136">yes</span></span>|<span data-ttu-id="7c5d9-137">stringa</span><span class="sxs-lookup"><span data-stu-id="7c5d9-137">string</span></span>|<span data-ttu-id="7c5d9-138">URL relativo al server per la raccolta di destinazione.</span><span class="sxs-lookup"><span data-stu-id="7c5d9-138">The server relative URL of the target library.</span></span>|
<span data-ttu-id="7c5d9-139">ViewOption</span><span class="sxs-lookup"><span data-stu-id="7c5d9-139">ViewOption</span></span>|<span data-ttu-id="7c5d9-140">no</span><span class="sxs-lookup"><span data-stu-id="7c5d9-140">no</span></span>|<span data-ttu-id="7c5d9-141">stringa</span><span class="sxs-lookup"><span data-stu-id="7c5d9-141">string</span></span>|<span data-ttu-id="7c5d9-142">Specifica se impostare la nuova visualizzazione modello come predefinita per la raccolta.</span><span class="sxs-lookup"><span data-stu-id="7c5d9-142">Specifies whether to set new model view as the library default.</span></span>|

## <a name="response"></a><span data-ttu-id="7c5d9-143">Risposta</span><span class="sxs-lookup"><span data-stu-id="7c5d9-143">Response</span></span>

| <span data-ttu-id="7c5d9-144">Nome</span><span class="sxs-lookup"><span data-stu-id="7c5d9-144">Name</span></span>   | <span data-ttu-id="7c5d9-145">Tipo</span><span class="sxs-lookup"><span data-stu-id="7c5d9-145">Type</span></span>  | <span data-ttu-id="7c5d9-146">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7c5d9-146">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="7c5d9-147">200 OK</span><span class="sxs-lookup"><span data-stu-id="7c5d9-147">200 OK</span></span>| |<span data-ttu-id="7c5d9-148">Operazione completata</span><span class="sxs-lookup"><span data-stu-id="7c5d9-148">Success</span></span>|


## <a name="examples"></a><span data-ttu-id="7c5d9-149">Esempi</span><span class="sxs-lookup"><span data-stu-id="7c5d9-149">Examples</span></span>

### <a name="remove-a-model-from-the-contracts-document-library-in-the-repository-site"></a><span data-ttu-id="7c5d9-150">Rimuovi un modello dalla raccolta documenti di contratti nel sito repository</span><span class="sxs-lookup"><span data-stu-id="7c5d9-150">Remove a model from the contracts document library in the repository site</span></span>

<span data-ttu-id="7c5d9-151">In questo esempio, l'ID del modello di analisi dei documenti Contoso Contract è `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span><span class="sxs-lookup"><span data-stu-id="7c5d9-151">In this sample, the ID of the Contoso Contract document understanding model is `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="7c5d9-152">Richiesta di esempio</span><span class="sxs-lookup"><span data-stu-id="7c5d9-152">Sample request</span></span>

```HTTP
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningPublicationsEntityData"
    },
    "Publications": {
        "results": [
            {
                "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
                "TargetSiteUrl": "https://contoso.sharepoint.com/sites/repository/",
                "TargetWebServerRelativeUrl": "/sites/repository",
                "TargetLibraryServerRelativeUrl": "/sites/repository/contracts",
                "ViewOption": "NewViewAsDefault"
            }
        ]
    }
}
```


#### <a name="sample-response"></a><span data-ttu-id="7c5d9-153">Risposta di esempio</span><span class="sxs-lookup"><span data-stu-id="7c5d9-153">Sample response</span></span>

<span data-ttu-id="7c5d9-154">Nella risposta, TotalFailures e TotalSuccesses fanno riferimento al numero di errori e successi del modello applicato alle raccolte specificate.</span><span class="sxs-lookup"><span data-stu-id="7c5d9-154">In the response, TotalFailures and TotalSuccesses refer to the number of failures and successes of the model being applies to the specified libraries.</span></span>

<span data-ttu-id="7c5d9-155">**Codice di stato:** 200</span><span class="sxs-lookup"><span data-stu-id="7c5d9-155">**Status code:** 200</span></span>

```JSON
{
    "Details": [
        {
            "ErrorMessage": null,
            "Publication": {
                "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
                "TargetSiteUrl": "https://contoso.sharepoint.com/sites/repository/",
                "TargetWebServerRelativeUrl": "/sites/repository",
                "TargetLibraryServerRelativeUrl": "/sites/repository/contracts",
                "ViewOption": "NewViewAsDefault"
            },
            "StatusCode": 200
        }
    ],
    "TotalFailures": 0,
    "TotalSuccesses": 1
}
```

## <a name="see-also"></a><span data-ttu-id="7c5d9-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7c5d9-156">See also</span></span>

[<span data-ttu-id="7c5d9-157">API REST del modello di analisi dei documenti di Syntex</span><span class="sxs-lookup"><span data-stu-id="7c5d9-157">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
