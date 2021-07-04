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
ms.openlocfilehash: bbd3e496b50d3fddb31342fbc07d30984544e744
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287454"
---
# <a name="batchdelete"></a><span data-ttu-id="6a457-103">BatchDelete</span><span class="sxs-lookup"><span data-stu-id="6a457-103">BatchDelete</span></span>

<span data-ttu-id="6a457-104">Rimuove un modello di analisi dei documenti applicato da una o più raccolte.</span><span class="sxs-lookup"><span data-stu-id="6a457-104">Removes an applied document understanding model from one or more libraries.</span></span> <span data-ttu-id="6a457-105">Nota che un modello deve essere rimosso da tutte le raccolte prima di essere eliminato (vedi [esempio](rest-batchdelete-method.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="6a457-105">Note that a model must be removed from all libraries before it can be deleted (see [example](rest-batchdelete-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="6a457-106">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="6a457-106">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/publications/batchdelete HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="6a457-107">Parametri URI</span><span class="sxs-lookup"><span data-stu-id="6a457-107">URI parameters</span></span>

<span data-ttu-id="6a457-108">Nessuno</span><span class="sxs-lookup"><span data-stu-id="6a457-108">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="6a457-109">Intestazioni della richiesta</span><span class="sxs-lookup"><span data-stu-id="6a457-109">Request headers</span></span>

| <span data-ttu-id="6a457-110">Intestazione</span><span class="sxs-lookup"><span data-stu-id="6a457-110">Header</span></span> | <span data-ttu-id="6a457-111">Valore</span><span class="sxs-lookup"><span data-stu-id="6a457-111">Value</span></span> |
|--------|-------|
|<span data-ttu-id="6a457-112">Accept</span><span class="sxs-lookup"><span data-stu-id="6a457-112">Accept</span></span>|<span data-ttu-id="6a457-113">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="6a457-113">application/json;odata=verbose</span></span>|
|<span data-ttu-id="6a457-114">Content-Type</span><span class="sxs-lookup"><span data-stu-id="6a457-114">Content-Type</span></span>|<span data-ttu-id="6a457-115">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="6a457-115">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="6a457-116">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="6a457-116">x-requestdigest</span></span>|<span data-ttu-id="6a457-117">Digest appropriato per il sito corrente.</span><span class="sxs-lookup"><span data-stu-id="6a457-117">The appropriate digest for current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="6a457-118">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="6a457-118">Request body</span></span>

| <span data-ttu-id="6a457-119">Nome</span><span class="sxs-lookup"><span data-stu-id="6a457-119">Name</span></span> | <span data-ttu-id="6a457-120">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="6a457-120">Required</span></span> | <span data-ttu-id="6a457-121">Tipo</span><span class="sxs-lookup"><span data-stu-id="6a457-121">Type</span></span> | <span data-ttu-id="6a457-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6a457-122">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="6a457-123">Pubblicazioni</span><span class="sxs-lookup"><span data-stu-id="6a457-123">Publications</span></span>|<span data-ttu-id="6a457-124">sì</span><span class="sxs-lookup"><span data-stu-id="6a457-124">yes</span></span>|<span data-ttu-id="6a457-125">MachineLearningPublicationEntityData[]</span><span class="sxs-lookup"><span data-stu-id="6a457-125">MachineLearningPublicationEntityData[]</span></span>|<span data-ttu-id="6a457-126">Raccolta di MachineLearningPublicationEntityData, ognuno dei quali specifica il modello e la raccolta documenti di destinazione.</span><span class="sxs-lookup"><span data-stu-id="6a457-126">The collection of MachineLearningPublicationEntityData each of which specifies the model and target document library.</span></span>|

### <a name="machinelearningpublicationentitydata"></a><span data-ttu-id="6a457-127">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="6a457-127">MachineLearningPublicationEntityData</span></span>

| <span data-ttu-id="6a457-128">Nome</span><span class="sxs-lookup"><span data-stu-id="6a457-128">Name</span></span> | <span data-ttu-id="6a457-129">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="6a457-129">Required</span></span> | <span data-ttu-id="6a457-130">Tipo</span><span class="sxs-lookup"><span data-stu-id="6a457-130">Type</span></span> | <span data-ttu-id="6a457-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6a457-131">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="6a457-132">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="6a457-132">ModelUniqueId</span></span>|<span data-ttu-id="6a457-133">sì</span><span class="sxs-lookup"><span data-stu-id="6a457-133">yes</span></span>|<span data-ttu-id="6a457-134">stringa</span><span class="sxs-lookup"><span data-stu-id="6a457-134">string</span></span>|<span data-ttu-id="6a457-135">ID univoco del file di modello.</span><span class="sxs-lookup"><span data-stu-id="6a457-135">The unique ID of the model file.</span></span>|
|<span data-ttu-id="6a457-136">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="6a457-136">TargetSiteUrl</span></span>|<span data-ttu-id="6a457-137">sì</span><span class="sxs-lookup"><span data-stu-id="6a457-137">yes</span></span>|<span data-ttu-id="6a457-138">stringa</span><span class="sxs-lookup"><span data-stu-id="6a457-138">string</span></span>|<span data-ttu-id="6a457-139">URL completo del sito della raccolta di destinazione.</span><span class="sxs-lookup"><span data-stu-id="6a457-139">The full URL of the target library site.</span></span>|
|<span data-ttu-id="6a457-140">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="6a457-140">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="6a457-141">sì</span><span class="sxs-lookup"><span data-stu-id="6a457-141">yes</span></span>|<span data-ttu-id="6a457-142">stringa</span><span class="sxs-lookup"><span data-stu-id="6a457-142">string</span></span>|<span data-ttu-id="6a457-143">URL relativo al server Web per la raccolta di destinazione.</span><span class="sxs-lookup"><span data-stu-id="6a457-143">The server relative URL of the web for the target library.</span></span>|
|<span data-ttu-id="6a457-144">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="6a457-144">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="6a457-145">sì</span><span class="sxs-lookup"><span data-stu-id="6a457-145">yes</span></span>|<span data-ttu-id="6a457-146">stringa</span><span class="sxs-lookup"><span data-stu-id="6a457-146">string</span></span>|<span data-ttu-id="6a457-147">URL relativo al server per la raccolta di destinazione.</span><span class="sxs-lookup"><span data-stu-id="6a457-147">The server relative URL of the target library.</span></span>|

## <a name="response"></a><span data-ttu-id="6a457-148">Risposta</span><span class="sxs-lookup"><span data-stu-id="6a457-148">Response</span></span>

| <span data-ttu-id="6a457-149">Nome</span><span class="sxs-lookup"><span data-stu-id="6a457-149">Name</span></span>   | <span data-ttu-id="6a457-150">Tipo</span><span class="sxs-lookup"><span data-stu-id="6a457-150">Type</span></span>  | <span data-ttu-id="6a457-151">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6a457-151">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="6a457-152">200 OK</span><span class="sxs-lookup"><span data-stu-id="6a457-152">200 OK</span></span>||<span data-ttu-id="6a457-p102">Si tratta di un'API personalizzata per supportare la rimozione di un modello da una raccolta di più documenti. In caso di esito positivo parziale, potrebbe comunque essere restituito 200 OK e il chiamante deve esaminare il corpo della risposta per capire se il modello è stato rimosso correttamente da una raccolta documenti.</span><span class="sxs-lookup"><span data-stu-id="6a457-p102">This is a customized API to support removing a model from multi document libraries. In the case of partial success, 200 OK could still be returned and the caller needs to inspect the response body to understand if the model has been successfully removed from a document library.</span></span>|

## <a name="response-body"></a><span data-ttu-id="6a457-155">Corpo della risposta</span><span class="sxs-lookup"><span data-stu-id="6a457-155">Response Body</span></span>

| <span data-ttu-id="6a457-156">Nome</span><span class="sxs-lookup"><span data-stu-id="6a457-156">Name</span></span>   | <span data-ttu-id="6a457-157">Tipo</span><span class="sxs-lookup"><span data-stu-id="6a457-157">Type</span></span>  | <span data-ttu-id="6a457-158">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6a457-158">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="6a457-159">TotalSuccesses</span><span class="sxs-lookup"><span data-stu-id="6a457-159">TotalSuccesses</span></span>|<span data-ttu-id="6a457-160">int</span><span class="sxs-lookup"><span data-stu-id="6a457-160">int</span></span>|<span data-ttu-id="6a457-161">Numero totale di modelli rimossi correttamente da una raccolta documenti.</span><span class="sxs-lookup"><span data-stu-id="6a457-161">The total number of a model being successfully removed from a document library.</span></span>|
|<span data-ttu-id="6a457-162">TotalFailures</span><span class="sxs-lookup"><span data-stu-id="6a457-162">TotalFailures</span></span>|<span data-ttu-id="6a457-163">int</span><span class="sxs-lookup"><span data-stu-id="6a457-163">int</span></span>|<span data-ttu-id="6a457-164">Numero totale di modelli che non possono essere rimossi da una raccolta documenti.</span><span class="sxs-lookup"><span data-stu-id="6a457-164">The total number of a model failing to be removed from a document library.</span></span>|
|<span data-ttu-id="6a457-165">Dettagli</span><span class="sxs-lookup"><span data-stu-id="6a457-165">Details</span></span>|<span data-ttu-id="6a457-166">MachineLearningPublicationResult[]</span><span class="sxs-lookup"><span data-stu-id="6a457-166">MachineLearningPublicationResult[]</span></span>|<span data-ttu-id="6a457-167">Raccolta di MachineLearningPublicationResult, ognuno dei quali specifica il risultato dettagliato della rimozione del modello da una raccolta documenti.</span><span class="sxs-lookup"><span data-stu-id="6a457-167">The collection of MachineLearningPublicationResult each of which specifies the detailed result of removing the model from a document library.</span></span>|

### <a name="machinelearningpublicationresult"></a><span data-ttu-id="6a457-168">MachineLearningPublicationResult</span><span class="sxs-lookup"><span data-stu-id="6a457-168">MachineLearningPublicationResult</span></span>

| <span data-ttu-id="6a457-169">Nome</span><span class="sxs-lookup"><span data-stu-id="6a457-169">Name</span></span>   | <span data-ttu-id="6a457-170">Tipo</span><span class="sxs-lookup"><span data-stu-id="6a457-170">Type</span></span>  | <span data-ttu-id="6a457-171">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6a457-171">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="6a457-172">StatusCode</span><span class="sxs-lookup"><span data-stu-id="6a457-172">StatusCode</span></span>|<span data-ttu-id="6a457-173">int</span><span class="sxs-lookup"><span data-stu-id="6a457-173">int</span></span>|<span data-ttu-id="6a457-174">Codice di stato HTTP.</span><span class="sxs-lookup"><span data-stu-id="6a457-174">The HTTP status code.</span></span>|
|<span data-ttu-id="6a457-175">ErrorMessage</span><span class="sxs-lookup"><span data-stu-id="6a457-175">ErrorMessage</span></span>|<span data-ttu-id="6a457-176">stringa</span><span class="sxs-lookup"><span data-stu-id="6a457-176">string</span></span>|<span data-ttu-id="6a457-177">Messaggio di errore che indica cosa non va quando si applica il modello alla raccolta documenti.</span><span class="sxs-lookup"><span data-stu-id="6a457-177">The error message which tells what's wrong when apply the model to the document library.</span></span>|
|<span data-ttu-id="6a457-178">Pubblicazione</span><span class="sxs-lookup"><span data-stu-id="6a457-178">Publication</span></span>|<span data-ttu-id="6a457-179">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="6a457-179">MachineLearningPublicationEntityData</span></span>|<span data-ttu-id="6a457-180">Specifica le informazioni sul modello e la raccolta documenti di destinazione.</span><span class="sxs-lookup"><span data-stu-id="6a457-180">It specifies the model info and the target document library.</span></span>| 

### <a name="machinelearningpublicationentitydata"></a><span data-ttu-id="6a457-181">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="6a457-181">MachineLearningPublicationEntityData</span></span>

| <span data-ttu-id="6a457-182">Nome</span><span class="sxs-lookup"><span data-stu-id="6a457-182">Name</span></span> | <span data-ttu-id="6a457-183">Tipo</span><span class="sxs-lookup"><span data-stu-id="6a457-183">Type</span></span> | <span data-ttu-id="6a457-184">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6a457-184">Description</span></span> |
|--------|--------|------------|
|<span data-ttu-id="6a457-185">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="6a457-185">ModelUniqueId</span></span>|<span data-ttu-id="6a457-186">stringa</span><span class="sxs-lookup"><span data-stu-id="6a457-186">string</span></span>|<span data-ttu-id="6a457-187">ID univoco del file di modello.</span><span class="sxs-lookup"><span data-stu-id="6a457-187">The unique ID of the model file.</span></span>|
|<span data-ttu-id="6a457-188">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="6a457-188">TargetSiteUrl</span></span>|<span data-ttu-id="6a457-189">stringa</span><span class="sxs-lookup"><span data-stu-id="6a457-189">string</span></span>|<span data-ttu-id="6a457-190">URL completo del sito della raccolta di destinazione.</span><span class="sxs-lookup"><span data-stu-id="6a457-190">The full URL of the target library site.</span></span>|
|<span data-ttu-id="6a457-191">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="6a457-191">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="6a457-192">stringa</span><span class="sxs-lookup"><span data-stu-id="6a457-192">string</span></span>|<span data-ttu-id="6a457-193">URL relativo al server Web per la raccolta di destinazione.</span><span class="sxs-lookup"><span data-stu-id="6a457-193">The server relative URL of the web for the target library.</span></span>|
|<span data-ttu-id="6a457-194">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="6a457-194">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="6a457-195">stringa</span><span class="sxs-lookup"><span data-stu-id="6a457-195">string</span></span>|<span data-ttu-id="6a457-196">URL relativo al server per la raccolta di destinazione.</span><span class="sxs-lookup"><span data-stu-id="6a457-196">The server relative URL of the target library.</span></span>|

## <a name="examples"></a><span data-ttu-id="6a457-197">Esempi</span><span class="sxs-lookup"><span data-stu-id="6a457-197">Examples</span></span>

### <a name="remove-a-model-from-the-contracts-document-library-in-the-repository-site"></a><span data-ttu-id="6a457-198">Rimuovi un modello dalla raccolta documenti di contratti nel sito repository</span><span class="sxs-lookup"><span data-stu-id="6a457-198">Remove a model from the contracts document library in the repository site</span></span>

<span data-ttu-id="6a457-199">In questo esempio, l'ID del modello di analisi dei documenti Contoso Contract è `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span><span class="sxs-lookup"><span data-stu-id="6a457-199">In this sample, the ID of the Contoso Contract document understanding model is `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="6a457-200">Richiesta di esempio</span><span class="sxs-lookup"><span data-stu-id="6a457-200">Sample request</span></span>

```HTTP
{ 
    "publications": [ 
        { 
            "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc", 
            "TargetSiteUrl": "https://constco.sharepoint-df.com/sites/docsite", 
            "TargetWebServerRelativeUrl": "/sites/docsite ", 
            "TargetLibraryServerRelativeUrl": "/sites/dcocsite/joedcos" 
        } 
    ] 
} 
```

#### <a name="sample-response"></a><span data-ttu-id="6a457-201">Risposta di esempio</span><span class="sxs-lookup"><span data-stu-id="6a457-201">Sample response</span></span>

<span data-ttu-id="6a457-202">Nella risposta, TotalFailures e TotalSuccesses fanno riferimento al numero di errori e di successi del modello rimosso dalle librerie specificate.</span><span class="sxs-lookup"><span data-stu-id="6a457-202">In the response, TotalFailures and TotalSuccesses refer to the number of failures and successes of the model being removed from the specified libraries.</span></span>

<span data-ttu-id="6a457-203">**Codice di stato:** 200</span><span class="sxs-lookup"><span data-stu-id="6a457-203">**Status code:** 200</span></span>

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

## <a name="see-also"></a><span data-ttu-id="6a457-204">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6a457-204">See also</span></span>

[<span data-ttu-id="6a457-205">API REST del modello di analisi dei documenti di Syntex</span><span class="sxs-lookup"><span data-stu-id="6a457-205">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
