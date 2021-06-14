---
title: Ottieni informazioni su modelli e raccolte
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
description: Usa l'API REST per ottenere informazioni su un modello e sulla raccolta in cui è stato applicato.
ms.openlocfilehash: 6cd61364ed3b360ef235aaba21a2735002fe481e
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904224"
---
# <a name="get-model-and-library-information"></a><span data-ttu-id="eb999-103">Ottieni informazioni su modelli e raccolte</span><span class="sxs-lookup"><span data-stu-id="eb999-103">Get model and library information</span></span>

<span data-ttu-id="eb999-104">Ottiene informazioni su un modello e sulla raccolta in cui è stato applicato (vedi [esempio](rest-getmodelandlibraryinfo.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="eb999-104">Gets information about a model and the library where it has been applied (see [example](rest-getmodelandlibraryinfo.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="eb999-105">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="eb999-105">HTTP request</span></span>

```HTTP
GET /_api/machinelearning/publications/getbyuniqueid(‘{modelUniqueId}’) HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="eb999-106">Parametri URI</span><span class="sxs-lookup"><span data-stu-id="eb999-106">URI parameters</span></span>

| <span data-ttu-id="eb999-107">Nome</span><span class="sxs-lookup"><span data-stu-id="eb999-107">Name</span></span> | <span data-ttu-id="eb999-108">In</span><span class="sxs-lookup"><span data-stu-id="eb999-108">In</span></span> | <span data-ttu-id="eb999-109">Obbligatoria</span><span class="sxs-lookup"><span data-stu-id="eb999-109">Required</span></span> | <span data-ttu-id="eb999-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="eb999-110">Type</span></span> | <span data-ttu-id="eb999-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="eb999-111">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="eb999-112">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="eb999-112">ModelUniqueId</span></span>|<span data-ttu-id="eb999-113">query</span><span class="sxs-lookup"><span data-stu-id="eb999-113">query</span></span>|<span data-ttu-id="eb999-114">Vero</span><span class="sxs-lookup"><span data-stu-id="eb999-114">True</span></span>|<span data-ttu-id="eb999-115">GUID</span><span class="sxs-lookup"><span data-stu-id="eb999-115">GUID</span></span>|<span data-ttu-id="eb999-116">ID univoco del file di modello.</span><span class="sxs-lookup"><span data-stu-id="eb999-116">The unique id of the model file.</span></span>|

## <a name="request-headers"></a><span data-ttu-id="eb999-117">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="eb999-117">Request headers</span></span>

| <span data-ttu-id="eb999-118">Intestazione</span><span class="sxs-lookup"><span data-stu-id="eb999-118">Header</span></span> | <span data-ttu-id="eb999-119">Valore</span><span class="sxs-lookup"><span data-stu-id="eb999-119">Value</span></span> |
|--------|-------|
|<span data-ttu-id="eb999-120">Accetta</span><span class="sxs-lookup"><span data-stu-id="eb999-120">Accept</span></span>|<span data-ttu-id="eb999-121">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="eb999-121">application/json;odata=verbose</span></span>|


## <a name="request-body"></a><span data-ttu-id="eb999-122">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="eb999-122">Request body</span></span>

| <span data-ttu-id="eb999-123">Nome</span><span class="sxs-lookup"><span data-stu-id="eb999-123">Name</span></span> | <span data-ttu-id="eb999-124">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="eb999-124">Required</span></span> | <span data-ttu-id="eb999-125">Tipo</span><span class="sxs-lookup"><span data-stu-id="eb999-125">Type</span></span> | <span data-ttu-id="eb999-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="eb999-126">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="eb999-127">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="eb999-127">ModelUniqueId</span></span>|<span data-ttu-id="eb999-128">sì</span><span class="sxs-lookup"><span data-stu-id="eb999-128">yes</span></span>|<span data-ttu-id="eb999-129">stringa</span><span class="sxs-lookup"><span data-stu-id="eb999-129">string</span></span>|<span data-ttu-id="eb999-130">ID univoco del file di modello.</span><span class="sxs-lookup"><span data-stu-id="eb999-130">The unique ID of the model file.</span></span>|
|<span data-ttu-id="eb999-131">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="eb999-131">TargetSiteUrl</span></span>|<span data-ttu-id="eb999-132">sì</span><span class="sxs-lookup"><span data-stu-id="eb999-132">yes</span></span>|<span data-ttu-id="eb999-133">stringa</span><span class="sxs-lookup"><span data-stu-id="eb999-133">string</span></span>|<span data-ttu-id="eb999-134">URL completo del sito della raccolta di destinazione.</span><span class="sxs-lookup"><span data-stu-id="eb999-134">The full URL of the target library site.</span></span>|
|<span data-ttu-id="eb999-135">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="eb999-135">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="eb999-136">sì</span><span class="sxs-lookup"><span data-stu-id="eb999-136">yes</span></span>|<span data-ttu-id="eb999-137">stringa</span><span class="sxs-lookup"><span data-stu-id="eb999-137">string</span></span>|<span data-ttu-id="eb999-138">URL relativo al server Web per la raccolta di destinazione.</span><span class="sxs-lookup"><span data-stu-id="eb999-138">The server relative URL of the web for the target library.</span></span>|
|<span data-ttu-id="eb999-139">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="eb999-139">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="eb999-140">sì</span><span class="sxs-lookup"><span data-stu-id="eb999-140">yes</span></span>|<span data-ttu-id="eb999-141">stringa</span><span class="sxs-lookup"><span data-stu-id="eb999-141">string</span></span>|<span data-ttu-id="eb999-142">URL relativo al server per la raccolta di destinazione.</span><span class="sxs-lookup"><span data-stu-id="eb999-142">The server relative URL of the target library.</span></span>|
|<span data-ttu-id="eb999-143">TargetLibraryRemoved</span><span class="sxs-lookup"><span data-stu-id="eb999-143">TargetLibraryRemoved</span></span>|<span data-ttu-id="eb999-144">sì</span><span class="sxs-lookup"><span data-stu-id="eb999-144">yes</span></span>|<span data-ttu-id="eb999-145">int</span><span class="sxs-lookup"><span data-stu-id="eb999-145">int</span></span>|<span data-ttu-id="eb999-146">Il contrassegno che indica se la raccolta di destinazione è stata rimossa o meno.</span><span class="sxs-lookup"><span data-stu-id="eb999-146">The flag that indicates if the target library has been removed or not.</span></span>|

## <a name="response"></a><span data-ttu-id="eb999-147">Risposta</span><span class="sxs-lookup"><span data-stu-id="eb999-147">Response</span></span>

| <span data-ttu-id="eb999-148">Nome</span><span class="sxs-lookup"><span data-stu-id="eb999-148">Name</span></span>   | <span data-ttu-id="eb999-149">Tipo</span><span class="sxs-lookup"><span data-stu-id="eb999-149">Type</span></span>  | <span data-ttu-id="eb999-150">Descrizione</span><span class="sxs-lookup"><span data-stu-id="eb999-150">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="eb999-151">200 OK</span><span class="sxs-lookup"><span data-stu-id="eb999-151">200 OK</span></span>| |<span data-ttu-id="eb999-152">Operazione completata</span><span class="sxs-lookup"><span data-stu-id="eb999-152">Success</span></span>|
|<span data-ttu-id="eb999-153">201 Created</span><span class="sxs-lookup"><span data-stu-id="eb999-153">201 Created</span></span>| |<span data-ttu-id="eb999-154">Nota che poiché questa API supporta l'applicazione del modello a più raccolte, è possibile che sia restituito 201 anche se si verifica un errore nell'applicazione del modello a una delle raccolte.</span><span class="sxs-lookup"><span data-stu-id="eb999-154">Note that because this API supports applying model to multiple libraries, a 201 could be returned even if there's a failure applying the model to one of the libraries.</span></span> <br><span data-ttu-id="eb999-155">Controlla il corpo della risposta per determinare se il modello è stato applicato correttamente a tutte le raccolte specificate.</span><span class="sxs-lookup"><span data-stu-id="eb999-155">Check the response body to understand if the model has been successfully applied to all the specified libraries.</span></span> <span data-ttu-id="eb999-156">Per informazioni dettagliate, vedi [Corpo della richiesta](rest-getmodelandlibraryinfo.md#request-body).</span><span class="sxs-lookup"><span data-stu-id="eb999-156">See [Request body](rest-getmodelandlibraryinfo.md#request-body) for details.</span></span>|

## <a name="examples"></a><span data-ttu-id="eb999-157">Esempi</span><span class="sxs-lookup"><span data-stu-id="eb999-157">Examples</span></span>

### <a name="get-information-about-the-contracts-model-and-primed-document-library-in-the-repository-site"></a><span data-ttu-id="eb999-158">Ottieni informazioni sul modello di contratti e sulla raccolta documenti primed nel sito del repository</span><span class="sxs-lookup"><span data-stu-id="eb999-158">Get information about the contracts model and primed document library in the repository site</span></span>

<span data-ttu-id="eb999-159">In questo esempio, l'ID del modello di analisi dei documenti Contoso Contract è `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span><span class="sxs-lookup"><span data-stu-id="eb999-159">In this sample, the ID of the Contoso Contract document understanding model is `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="eb999-160">Richiesta di esempio</span><span class="sxs-lookup"><span data-stu-id="eb999-160">Sample request</span></span>

```HTTP
GET /sites/TestCC/_api/machinelearning/publications/getbymodeluniqueid(‘{7645e69d-21fb-4a24-a17a-9bdfa7cb63dc}’) HTTP/1.1
```
#### <a name="sample-response"></a><span data-ttu-id="eb999-161">Risposta di esempio</span><span class="sxs-lookup"><span data-stu-id="eb999-161">Sample response</span></span>

<span data-ttu-id="eb999-162">**Codice di stato:** 200</span><span class="sxs-lookup"><span data-stu-id="eb999-162">**Status code:** 200</span></span>

```JSON
{
    "@odata.context": "https://contoso.sharepoint.com/sites/TestCC/_api/$metadata#publications",
    "value": [
        {
            "@odata.type": "#Microsoft.Office.Server.ContentCenter.SPMachineLearningPublication",
            "@odata.id": "https://contoso.sharepoint.com/sites/repository /_api/machinelearning/publications/getbyuniqueId('7645e69d-21fb-4a24-a17a-9bdfa7cb63dc')",
            "@odata.etag": "\"7645e69d-21fb-4a24-a17a-9bdfa7cb63dc,94\"",
            "@odata.editLink": " https://contoso.sharepoint.com/sites/TestCC /_api/machinelearning/publications/getbyuniqueId('7645e69d-21fb-4a24-a17a-9bdfa7cb63dc')",
            "Created": "2021-04-27T03:05:25Z",
            "CreatedBy": "i:0#.f|membership|meganb@contoso.com",
            "DriveId": "b!O-aG9qer5UiXx2jEwd8pL0221maIb9lNs9tH5vAMU-gPy9BrxT7GTrtXtdtv1Uzb",
            "ID": 26,
            "ModelId": 16,
            "ModelName": "contosocontract.classifier",
            "ModelType": 0,
            "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
            "ModelVersion": "8.0",
            "Modified": "2021-03-17T17:56:42Z",
            "ModifiedBy": "i:0#.f|membership|joedoe@contoso.com",
            "ObjectId": "01ZBWEM5FZRILGLXTEB5CZ2NNNSCTWBJMQ",
            "PublicationType": 1,
            "TargetLibraryRemoved": false,
            "TargetLibraryServerRelativeUrl": "/sites/repository/contracts",
            "TargetLibraryUrl": " https://contoso.sharepoint.com/sites/repository/contracts",
            "TargetSiteUrl": "https://contoso.sharepoint.com/sites/repository",
            "TargetWebServerRelativeUrl": "/sites/repository",
            "UniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
            "ViewOption": "NewViewAsDefault"
        },
        {
            "@odata.type": "#Microsoft.Office.Server.ContentCenter.SPMachineLearningPublication",
            "@odata.id": "https://contoso.sharepoint.com /sites/legal/_api/machinelearning/publications/getbyuniqueId('7645e69d-21fb-4a24-a17a-9bdfa7cb63dc')",
            "@odata.etag": "\"7645e69d-21fb-4a24-a17a-9bdfa7cb63dc,101\"",
            "@odata.editLink": "https://contoso.sharepoint.com /sites/legal/_api/machinelearning/publications/getbyuniqueId('7645e69d-21fb-4a24-a17a-9bdfa7cb63dc')",
            "Created": "2021-01-27T03:17:44Z",
            "CreatedBy": "i:0#.f|membership|esherman@contoso.com ",
            "DriveId": "b!O-aG9qer5UiXx2jEwd8pL0221maIb9lNs9tH5vAMU-gPy9BrxT7GTrtXtdtv1Uzb",
            "ID": 27,
            "ModelId": 16,
            "ModelName": "dispositions.classifier",
            "ModelType": 0,
            "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
            "ModelVersion": "8.0",
            "Modified": "2021-03-17T23:17:46Z",
            "ModifiedBy": "i:0#.f|membership|esherman@contoso.com ",
            "ObjectId": "01ZBWEM5B3ERSZK4PAARGLFZ7JP6GMXG2R",
            "PublicationType": 1,
            "TargetLibraryRemoved": false,
            "TargetLibraryServerRelativeUrl": "/sites/legal/dispositions",
            "TargetLibraryUrl": "https://contoso.sharepoint.com/sites/legal/dispositions",
            "TargetSiteUrl": " https://contoso.sharepoint.com/sites/legal",
            "TargetWebServerRelativeUrl": "/sites/legal",
            "UniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
            "ViewOption": "NewViewAsDefault"
        }
    ]
}```
```

## <a name="see-also"></a><span data-ttu-id="eb999-163">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eb999-163">See also</span></span>

[<span data-ttu-id="eb999-164">API REST del modello di analisi dei documenti di Syntex</span><span class="sxs-lookup"><span data-stu-id="eb999-164">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
