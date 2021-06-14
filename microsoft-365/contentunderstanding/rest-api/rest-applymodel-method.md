---
title: Applica modello
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
description: Usare l'API REST per applicare un modello di analisi dei documenti a una o più raccolte.
ms.openlocfilehash: d4cadad3c45dd7af0cdaeb4e1b367426289db870
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904267"
---
# <a name="apply-model"></a><span data-ttu-id="a9440-103">Applica modello</span><span class="sxs-lookup"><span data-stu-id="a9440-103">Apply model</span></span>

<span data-ttu-id="a9440-104">Applica (o sincronizza) un modello di analisi dei documenti sottoposto a training a una o più raccolte (vedere l'[esempio](rest-applymodel-method.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="a9440-104">Applies (or syncs) a trained document understanding model to one or more libraries (see [example](rest-applymodel-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="a9440-105">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="a9440-105">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/publications HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="a9440-106">Parametri URI</span><span class="sxs-lookup"><span data-stu-id="a9440-106">URI parameters</span></span>

<span data-ttu-id="a9440-107">Nessuno</span><span class="sxs-lookup"><span data-stu-id="a9440-107">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="a9440-108">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="a9440-108">Request headers</span></span>

| <span data-ttu-id="a9440-109">Intestazione</span><span class="sxs-lookup"><span data-stu-id="a9440-109">Header</span></span> | <span data-ttu-id="a9440-110">Valore</span><span class="sxs-lookup"><span data-stu-id="a9440-110">Value</span></span> |
|--------|-------|
|<span data-ttu-id="a9440-111">Accept</span><span class="sxs-lookup"><span data-stu-id="a9440-111">Accept</span></span>|<span data-ttu-id="a9440-112">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="a9440-112">application/json;odata=verbose</span></span>|
|<span data-ttu-id="a9440-113">Content-Type</span><span class="sxs-lookup"><span data-stu-id="a9440-113">Content-Type</span></span>|<span data-ttu-id="a9440-114">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="a9440-114">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="a9440-115">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="a9440-115">x-requestdigest</span></span>|<span data-ttu-id="a9440-116">Digest appropriato per il sito corrente.</span><span class="sxs-lookup"><span data-stu-id="a9440-116">The appropriate digest for current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="a9440-117">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="a9440-117">Request body</span></span>

| <span data-ttu-id="a9440-118">Nome</span><span class="sxs-lookup"><span data-stu-id="a9440-118">Name</span></span> | <span data-ttu-id="a9440-119">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="a9440-119">Required</span></span> | <span data-ttu-id="a9440-120">Tipo</span><span class="sxs-lookup"><span data-stu-id="a9440-120">Type</span></span> | <span data-ttu-id="a9440-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a9440-121">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="a9440-122">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="a9440-122">ModelUniqueId</span></span>|<span data-ttu-id="a9440-123">sì</span><span class="sxs-lookup"><span data-stu-id="a9440-123">yes</span></span>|<span data-ttu-id="a9440-124">stringa</span><span class="sxs-lookup"><span data-stu-id="a9440-124">string</span></span>|<span data-ttu-id="a9440-125">ID univoco del file di modello.</span><span class="sxs-lookup"><span data-stu-id="a9440-125">The unique ID of the model file.</span></span>|
<span data-ttu-id="a9440-126">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="a9440-126">TargetSiteUrl</span></span>|<span data-ttu-id="a9440-127">sì</span><span class="sxs-lookup"><span data-stu-id="a9440-127">yes</span></span>|<span data-ttu-id="a9440-128">stringa</span><span class="sxs-lookup"><span data-stu-id="a9440-128">string</span></span>|<span data-ttu-id="a9440-129">URL completo del sito della raccolta di destinazione.</span><span class="sxs-lookup"><span data-stu-id="a9440-129">The full URL of the target library site.</span></span>|
<span data-ttu-id="a9440-130">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="a9440-130">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="a9440-131">sì</span><span class="sxs-lookup"><span data-stu-id="a9440-131">yes</span></span>|<span data-ttu-id="a9440-132">stringa</span><span class="sxs-lookup"><span data-stu-id="a9440-132">string</span></span>|<span data-ttu-id="a9440-133">URL relativo al server Web per la raccolta di destinazione.</span><span class="sxs-lookup"><span data-stu-id="a9440-133">The server relative URL of the web for the target library.</span></span>|
<span data-ttu-id="a9440-134">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="a9440-134">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="a9440-135">sì</span><span class="sxs-lookup"><span data-stu-id="a9440-135">yes</span></span>|<span data-ttu-id="a9440-136">stringa</span><span class="sxs-lookup"><span data-stu-id="a9440-136">string</span></span>|<span data-ttu-id="a9440-137">URL relativo al server per la raccolta di destinazione.</span><span class="sxs-lookup"><span data-stu-id="a9440-137">The server relative URL of the target library.</span></span>|
<span data-ttu-id="a9440-138">ViewOption</span><span class="sxs-lookup"><span data-stu-id="a9440-138">ViewOption</span></span>|<span data-ttu-id="a9440-139">no</span><span class="sxs-lookup"><span data-stu-id="a9440-139">no</span></span>|<span data-ttu-id="a9440-140">stringa</span><span class="sxs-lookup"><span data-stu-id="a9440-140">string</span></span>|<span data-ttu-id="a9440-141">Specifica se impostare la nuova visualizzazione modello come predefinita per la raccolta.</span><span class="sxs-lookup"><span data-stu-id="a9440-141">Specifies whether to set new model view as the library default.</span></span>|

## <a name="response"></a><span data-ttu-id="a9440-142">Risposta</span><span class="sxs-lookup"><span data-stu-id="a9440-142">Response</span></span>

| <span data-ttu-id="a9440-143">Nome</span><span class="sxs-lookup"><span data-stu-id="a9440-143">Name</span></span>   | <span data-ttu-id="a9440-144">Tipo</span><span class="sxs-lookup"><span data-stu-id="a9440-144">Type</span></span>  | <span data-ttu-id="a9440-145">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a9440-145">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="a9440-146">200 OK</span><span class="sxs-lookup"><span data-stu-id="a9440-146">200 OK</span></span>| |<span data-ttu-id="a9440-147">Operazione completata</span><span class="sxs-lookup"><span data-stu-id="a9440-147">Success</span></span>|
|<span data-ttu-id="a9440-148">201 Created</span><span class="sxs-lookup"><span data-stu-id="a9440-148">201 Created</span></span>| |<span data-ttu-id="a9440-149">Si noti che poiché questa API supporta l'applicazione del modello a più raccolte, è possibile che sia restituito 201 anche se si verifica un errore nell'applicazione del modello a una delle raccolte.</span><span class="sxs-lookup"><span data-stu-id="a9440-149">Note that because this API supports applying model to multiple libraries, a 201 could be returned even if there's a failure applying the model to one of the libraries.</span></span> <br><span data-ttu-id="a9440-150">Controllare il corpo della risposta per determinare se il modello è stato applicato correttamente a tutte le raccolte specificate.</span><span class="sxs-lookup"><span data-stu-id="a9440-150">Check the response body to understand if the model has been successfully applied to all the specified libraries.</span></span> <span data-ttu-id="a9440-151">Per informazioni dettagliate, vedere [Corpo della richiesta](rest-applymodel-method.md#request-body).</span><span class="sxs-lookup"><span data-stu-id="a9440-151">See [Request body](rest-applymodel-method.md#request-body) for details.</span></span>|

## <a name="examples"></a><span data-ttu-id="a9440-152">Esempi</span><span class="sxs-lookup"><span data-stu-id="a9440-152">Examples</span></span>

### <a name="apply-a-model-to-the-contracts-document-library-in-the-repository-site"></a><span data-ttu-id="a9440-153">Applicare un modello alla raccolta documenti dei contratti nel sito repository</span><span class="sxs-lookup"><span data-stu-id="a9440-153">Apply a model to the contracts document library in the repository site</span></span>

<span data-ttu-id="a9440-154">In questo esempio l'ID del modello di analisi dei documenti Contoso Contract è `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span><span class="sxs-lookup"><span data-stu-id="a9440-154">In this sample, the ID of the Contoso Contract document understanding model is `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="a9440-155">Richiesta di esempio</span><span class="sxs-lookup"><span data-stu-id="a9440-155">Sample request</span></span>

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


#### <a name="sample-response"></a><span data-ttu-id="a9440-156">Risposta di esempio</span><span class="sxs-lookup"><span data-stu-id="a9440-156">Sample response</span></span>

<span data-ttu-id="a9440-157">Nella risposta, TotalFailures e TotalSuccesses fanno riferimento al numero di errori e successi nell'applicazione del modello alle raccolte specificate.</span><span class="sxs-lookup"><span data-stu-id="a9440-157">In the response, TotalFailures and TotalSuccesses refers to the number of failures and successes of the model being applies to the specified libraries.</span></span>

<span data-ttu-id="a9440-158">**Codice di stato:** 200</span><span class="sxs-lookup"><span data-stu-id="a9440-158">**Status code:** 200</span></span>

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

## <a name="see-also"></a><span data-ttu-id="a9440-159">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a9440-159">See also</span></span>

[<span data-ttu-id="a9440-160">API REST del modello di analisi dei documenti di Syntex</span><span class="sxs-lookup"><span data-stu-id="a9440-160">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
