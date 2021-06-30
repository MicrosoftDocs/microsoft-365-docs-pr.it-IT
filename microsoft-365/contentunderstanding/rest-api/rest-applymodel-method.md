---
title: Modello di applicazione batch
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
ms.openlocfilehash: 24ea9a480bc3ce5a7745857de17a6fab6ed97685
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177262"
---
# <a name="batch-apply-model"></a><span data-ttu-id="4212f-103">Modello di Applicazione Batch</span><span class="sxs-lookup"><span data-stu-id="4212f-103">Batch Apply model</span></span>

<span data-ttu-id="4212f-104">Applica (o sincronizza) un modello di analisi dei documenti sottoposto a training a una o più raccolte (vedere l'[esempio](rest-applymodel-method.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="4212f-104">Applies (or syncs) a trained document understanding model to one or more libraries (see [example](rest-applymodel-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="4212f-105">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="4212f-105">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/publications HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="4212f-106">Parametri URI</span><span class="sxs-lookup"><span data-stu-id="4212f-106">URI parameters</span></span>

<span data-ttu-id="4212f-107">Nessuno</span><span class="sxs-lookup"><span data-stu-id="4212f-107">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="4212f-108">Intestazioni della richiesta</span><span class="sxs-lookup"><span data-stu-id="4212f-108">Request headers</span></span>

| <span data-ttu-id="4212f-109">Intestazione</span><span class="sxs-lookup"><span data-stu-id="4212f-109">Header</span></span> | <span data-ttu-id="4212f-110">Valore</span><span class="sxs-lookup"><span data-stu-id="4212f-110">Value</span></span> |
|--------|-------|
|<span data-ttu-id="4212f-111">Accept</span><span class="sxs-lookup"><span data-stu-id="4212f-111">Accept</span></span>|<span data-ttu-id="4212f-112">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="4212f-112">application/json;odata=verbose</span></span>|
|<span data-ttu-id="4212f-113">Content-Type</span><span class="sxs-lookup"><span data-stu-id="4212f-113">Content-Type</span></span>|<span data-ttu-id="4212f-114">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="4212f-114">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="4212f-115">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="4212f-115">x-requestdigest</span></span>|<span data-ttu-id="4212f-116">Digest appropriato per il sito corrente.</span><span class="sxs-lookup"><span data-stu-id="4212f-116">The appropriate digest for current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="4212f-117">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="4212f-117">Request body</span></span>

| <span data-ttu-id="4212f-118">Nome</span><span class="sxs-lookup"><span data-stu-id="4212f-118">Name</span></span> | <span data-ttu-id="4212f-119">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="4212f-119">Required</span></span> | <span data-ttu-id="4212f-120">Tipo</span><span class="sxs-lookup"><span data-stu-id="4212f-120">Type</span></span> | <span data-ttu-id="4212f-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4212f-121">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="4212f-122">__metadata</span><span class="sxs-lookup"><span data-stu-id="4212f-122">__metadata</span></span>|<span data-ttu-id="4212f-123">sì</span><span class="sxs-lookup"><span data-stu-id="4212f-123">yes</span></span>|<span data-ttu-id="4212f-124">stringa</span><span class="sxs-lookup"><span data-stu-id="4212f-124">string</span></span>|<span data-ttu-id="4212f-125">Imposta i metadati dell'oggetto in SPO.</span><span class="sxs-lookup"><span data-stu-id="4212f-125">Set the object meta on the SPO.</span></span> <span data-ttu-id="4212f-126">Usare sempre il valore: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningPublicationsEntityData"}.</span><span class="sxs-lookup"><span data-stu-id="4212f-126">Always use the value: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningPublicationsEntityData"}.</span></span>|
|<span data-ttu-id="4212f-127">Pubblicazioni</span><span class="sxs-lookup"><span data-stu-id="4212f-127">Publications</span></span>|<span data-ttu-id="4212f-128">sì</span><span class="sxs-lookup"><span data-stu-id="4212f-128">yes</span></span>|<span data-ttu-id="4212f-129">MachineLearningPublicationEntityData[]</span><span class="sxs-lookup"><span data-stu-id="4212f-129">MachineLearningPublicationEntityData[]</span></span>|<span data-ttu-id="4212f-130">Raccolta di MachineLearningPublicationEntityData, ognuno dei quali specifica il modello e la raccolta documenti di destinazione.</span><span class="sxs-lookup"><span data-stu-id="4212f-130">The collection of MachineLearningPublicationEntityData each of which specifies the model and target document library.</span></span>|

### <a name="machinelearningpublicationentitydata"></a><span data-ttu-id="4212f-131">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="4212f-131">MachineLearningPublicationEntityData</span></span>
| <span data-ttu-id="4212f-132">Nome</span><span class="sxs-lookup"><span data-stu-id="4212f-132">Name</span></span> | <span data-ttu-id="4212f-133">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="4212f-133">Required</span></span> | <span data-ttu-id="4212f-134">Tipo</span><span class="sxs-lookup"><span data-stu-id="4212f-134">Type</span></span> | <span data-ttu-id="4212f-135">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4212f-135">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="4212f-136">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="4212f-136">ModelUniqueId</span></span>|<span data-ttu-id="4212f-137">sì</span><span class="sxs-lookup"><span data-stu-id="4212f-137">yes</span></span>|<span data-ttu-id="4212f-138">stringa</span><span class="sxs-lookup"><span data-stu-id="4212f-138">string</span></span>|<span data-ttu-id="4212f-139">ID univoco del file di modello.</span><span class="sxs-lookup"><span data-stu-id="4212f-139">The unique ID of the model file.</span></span>|
|<span data-ttu-id="4212f-140">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="4212f-140">TargetSiteUrl</span></span>|<span data-ttu-id="4212f-141">sì</span><span class="sxs-lookup"><span data-stu-id="4212f-141">yes</span></span>|<span data-ttu-id="4212f-142">stringa</span><span class="sxs-lookup"><span data-stu-id="4212f-142">string</span></span>|<span data-ttu-id="4212f-143">URL completo del sito della raccolta di destinazione.</span><span class="sxs-lookup"><span data-stu-id="4212f-143">The full URL of the target library site.</span></span>|
|<span data-ttu-id="4212f-144">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="4212f-144">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="4212f-145">sì</span><span class="sxs-lookup"><span data-stu-id="4212f-145">yes</span></span>|<span data-ttu-id="4212f-146">stringa</span><span class="sxs-lookup"><span data-stu-id="4212f-146">string</span></span>|<span data-ttu-id="4212f-147">URL relativo al server Web per la raccolta di destinazione.</span><span class="sxs-lookup"><span data-stu-id="4212f-147">The server relative URL of the web for the target library.</span></span>|
|<span data-ttu-id="4212f-148">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="4212f-148">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="4212f-149">sì</span><span class="sxs-lookup"><span data-stu-id="4212f-149">yes</span></span>|<span data-ttu-id="4212f-150">stringa</span><span class="sxs-lookup"><span data-stu-id="4212f-150">string</span></span>|<span data-ttu-id="4212f-151">URL relativo al server per la raccolta di destinazione.</span><span class="sxs-lookup"><span data-stu-id="4212f-151">The server relative URL of the target library.</span></span>|
|<span data-ttu-id="4212f-152">ViewOption</span><span class="sxs-lookup"><span data-stu-id="4212f-152">ViewOption</span></span>|<span data-ttu-id="4212f-153">no</span><span class="sxs-lookup"><span data-stu-id="4212f-153">no</span></span>|<span data-ttu-id="4212f-154">stringa</span><span class="sxs-lookup"><span data-stu-id="4212f-154">string</span></span>|<span data-ttu-id="4212f-155">Specifica se impostare la nuova visualizzazione modello come predefinita per la raccolta.</span><span class="sxs-lookup"><span data-stu-id="4212f-155">Specifies whether to set new model view as the library default.</span></span>|

## <a name="response"></a><span data-ttu-id="4212f-156">Risposta</span><span class="sxs-lookup"><span data-stu-id="4212f-156">Response</span></span>

| <span data-ttu-id="4212f-157">Nome</span><span class="sxs-lookup"><span data-stu-id="4212f-157">Name</span></span>   | <span data-ttu-id="4212f-158">Tipo</span><span class="sxs-lookup"><span data-stu-id="4212f-158">Type</span></span>  | <span data-ttu-id="4212f-159">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4212f-159">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="4212f-160">201 Created</span><span class="sxs-lookup"><span data-stu-id="4212f-160">201 Created</span></span>||<span data-ttu-id="4212f-161">Si tratta di un'API personalizzata per supportare l'applicazione di un modello a più raccolte documenti.</span><span class="sxs-lookup"><span data-stu-id="4212f-161">This is a customized API to support applying a model to multi document libraries.</span></span> <span data-ttu-id="4212f-162">In caso di esito positivo parziale, è comunque possibile che venga restituito il 201 creato e il chiamante deve controllare il corpo della risposta per capire se il modello è stato applicato correttamente a una raccolta documenti.</span><span class="sxs-lookup"><span data-stu-id="4212f-162">In the case of partial success, 201 created could still be returned and the caller needs to inspect the response body to understand if the model has been successfully applied to a document library.</span></span>|

## <a name="response-body"></a><span data-ttu-id="4212f-163">Contenuto risposta</span><span class="sxs-lookup"><span data-stu-id="4212f-163">Response Body</span></span>
| <span data-ttu-id="4212f-164">Nome</span><span class="sxs-lookup"><span data-stu-id="4212f-164">Name</span></span>   | <span data-ttu-id="4212f-165">Tipo</span><span class="sxs-lookup"><span data-stu-id="4212f-165">Type</span></span>  | <span data-ttu-id="4212f-166">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4212f-166">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="4212f-167">TotalSuccesses</span><span class="sxs-lookup"><span data-stu-id="4212f-167">TotalSuccesses</span></span>|<span data-ttu-id="4212f-168">int</span><span class="sxs-lookup"><span data-stu-id="4212f-168">int</span></span>|<span data-ttu-id="4212f-169">Numero totale di un modello applicato correttamente a una raccolta documenti.</span><span class="sxs-lookup"><span data-stu-id="4212f-169">The total number of a model being successfully applied to a document library.</span></span>|
|<span data-ttu-id="4212f-170">TotalFailures</span><span class="sxs-lookup"><span data-stu-id="4212f-170">TotalFailures</span></span>|<span data-ttu-id="4212f-171">int</span><span class="sxs-lookup"><span data-stu-id="4212f-171">int</span></span>|<span data-ttu-id="4212f-172">Numero totale di un modello non applicato a una raccolta documenti.</span><span class="sxs-lookup"><span data-stu-id="4212f-172">The total number of a model failing to be applied to a document library.</span></span>|
|<span data-ttu-id="4212f-173">Dettagli</span><span class="sxs-lookup"><span data-stu-id="4212f-173">Details</span></span>|<span data-ttu-id="4212f-174">MachineLearningPublicationResult[]</span><span class="sxs-lookup"><span data-stu-id="4212f-174">MachineLearningPublicationResult[]</span></span>|<span data-ttu-id="4212f-175">Raccolta di MachineLearningPublicationResult, ognuno dei quali specifica il risultato dettagliato dell'applicazione del modello alla raccolta documenti.</span><span class="sxs-lookup"><span data-stu-id="4212f-175">The collection of MachineLearningPublicationResult each of which specifies the detailed result of applying the model to the document library.</span></span>|

### <a name="machinelearningpublicationresult"></a><span data-ttu-id="4212f-176">MachineLearningPublicationResult</span><span class="sxs-lookup"><span data-stu-id="4212f-176">MachineLearningPublicationResult</span></span>
| <span data-ttu-id="4212f-177">Nome</span><span class="sxs-lookup"><span data-stu-id="4212f-177">Name</span></span>   | <span data-ttu-id="4212f-178">Tipo</span><span class="sxs-lookup"><span data-stu-id="4212f-178">Type</span></span>  | <span data-ttu-id="4212f-179">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4212f-179">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="4212f-180">StatusCode</span><span class="sxs-lookup"><span data-stu-id="4212f-180">StatusCode</span></span>|<span data-ttu-id="4212f-181">int</span><span class="sxs-lookup"><span data-stu-id="4212f-181">int</span></span>|<span data-ttu-id="4212f-182">Codice di stato HTTP.</span><span class="sxs-lookup"><span data-stu-id="4212f-182">The HTTP status code.</span></span>|
|<span data-ttu-id="4212f-183">ErrorMessage</span><span class="sxs-lookup"><span data-stu-id="4212f-183">ErrorMessage</span></span>|<span data-ttu-id="4212f-184">stringa</span><span class="sxs-lookup"><span data-stu-id="4212f-184">string</span></span>|<span data-ttu-id="4212f-185">Messaggio di errore che indica cosa non va quando si applica il modello alla raccolta documenti.</span><span class="sxs-lookup"><span data-stu-id="4212f-185">The error message which tells what's wrong when apply the model to the document library.</span></span>|
|<span data-ttu-id="4212f-186">Pubblicazione</span><span class="sxs-lookup"><span data-stu-id="4212f-186">Publication</span></span>|<span data-ttu-id="4212f-187">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="4212f-187">MachineLearningPublicationEntityData</span></span>|<span data-ttu-id="4212f-188">Specifica le informazioni sul modello e la raccolta documenti di destinazione.</span><span class="sxs-lookup"><span data-stu-id="4212f-188">It specifies the model info and the target document library.</span></span>| 

### <a name="machinelearningpublicationentitydata"></a><span data-ttu-id="4212f-189">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="4212f-189">MachineLearningPublicationEntityData</span></span>
| <span data-ttu-id="4212f-190">Nome</span><span class="sxs-lookup"><span data-stu-id="4212f-190">Name</span></span> | <span data-ttu-id="4212f-191">Tipo</span><span class="sxs-lookup"><span data-stu-id="4212f-191">Type</span></span> | <span data-ttu-id="4212f-192">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4212f-192">Description</span></span> |
|--------|--------|------------|
|<span data-ttu-id="4212f-193">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="4212f-193">ModelUniqueId</span></span>|<span data-ttu-id="4212f-194">stringa</span><span class="sxs-lookup"><span data-stu-id="4212f-194">string</span></span>|<span data-ttu-id="4212f-195">ID univoco del file di modello.</span><span class="sxs-lookup"><span data-stu-id="4212f-195">The unique ID of the model file.</span></span>|
|<span data-ttu-id="4212f-196">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="4212f-196">TargetSiteUrl</span></span>|<span data-ttu-id="4212f-197">stringa</span><span class="sxs-lookup"><span data-stu-id="4212f-197">string</span></span>|<span data-ttu-id="4212f-198">URL completo del sito della raccolta di destinazione.</span><span class="sxs-lookup"><span data-stu-id="4212f-198">The full URL of the target library site.</span></span>|
|<span data-ttu-id="4212f-199">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="4212f-199">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="4212f-200">stringa</span><span class="sxs-lookup"><span data-stu-id="4212f-200">string</span></span>|<span data-ttu-id="4212f-201">URL relativo al server Web per la raccolta di destinazione.</span><span class="sxs-lookup"><span data-stu-id="4212f-201">The server relative URL of the web for the target library.</span></span>|
|<span data-ttu-id="4212f-202">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="4212f-202">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="4212f-203">stringa</span><span class="sxs-lookup"><span data-stu-id="4212f-203">string</span></span>|<span data-ttu-id="4212f-204">URL relativo al server per la raccolta di destinazione.</span><span class="sxs-lookup"><span data-stu-id="4212f-204">The server relative URL of the target library.</span></span>|

## <a name="examples"></a><span data-ttu-id="4212f-205">Esempi</span><span class="sxs-lookup"><span data-stu-id="4212f-205">Examples</span></span>

### <a name="apply-a-model-to-the-contracts-document-library-in-the-repository-site"></a><span data-ttu-id="4212f-206">Applicare un modello alla raccolta documenti dei contratti nel sito repository</span><span class="sxs-lookup"><span data-stu-id="4212f-206">Apply a model to the contracts document library in the repository site</span></span>

<span data-ttu-id="4212f-207">In questo esempio l'ID del modello di analisi dei documenti Contoso Contract è `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span><span class="sxs-lookup"><span data-stu-id="4212f-207">In this sample, the ID of the Contoso Contract document understanding model is `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="4212f-208">Richiesta di esempio</span><span class="sxs-lookup"><span data-stu-id="4212f-208">Sample request</span></span>

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


#### <a name="sample-response"></a><span data-ttu-id="4212f-209">Risposta di esempio</span><span class="sxs-lookup"><span data-stu-id="4212f-209">Sample response</span></span>

<span data-ttu-id="4212f-210">Nella risposta, TotalFailures e TotalSuccesses fanno riferimento al numero di errori e successi nell'applicazione del modello alle raccolte specificate.</span><span class="sxs-lookup"><span data-stu-id="4212f-210">In the response, TotalFailures and TotalSuccesses refers to the number of failures and successes of the model being applies to the specified libraries.</span></span>

<span data-ttu-id="4212f-211">**Codice di stato:** 201</span><span class="sxs-lookup"><span data-stu-id="4212f-211">**Status code:** 201</span></span>

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
            "StatusCode": 201
        }
    ],
    "TotalFailures": 0,
    "TotalSuccesses": 1
}
```

## <a name="see-also"></a><span data-ttu-id="4212f-212">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4212f-212">See also</span></span>

[<span data-ttu-id="4212f-213">API REST del modello di analisi dei documenti di Syntex</span><span class="sxs-lookup"><span data-stu-id="4212f-213">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
