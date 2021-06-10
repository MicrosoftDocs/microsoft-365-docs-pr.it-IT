---
title: Codici di errore comuni Microsoft 365'API REST di Defender
description: Informazioni sui codici di errore comuni Microsoft 365'API REST di Defender
keywords: api, error, codes, common errors, Microsoft 365 Defender, api error codes
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: e621b79d37a2c3a22394bd51e0493334eff461c7
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932882"
---
# <a name="common-microsoft-365-defender-rest-api-error-codes"></a><span data-ttu-id="f2758-104">Codici di errore comuni Microsoft 365'API REST di Defender</span><span class="sxs-lookup"><span data-stu-id="f2758-104">Common Microsoft 365 Defender REST API error codes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="f2758-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="f2758-105">**Applies to:**</span></span>

- <span data-ttu-id="f2758-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f2758-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f2758-107">Alcune informazioni fanno riferimento alle caratteristiche del prodotto prima del rilascio, e possono essere modificate sostanzialmente prima della distribuzione al pubblico.</span><span class="sxs-lookup"><span data-stu-id="f2758-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="f2758-108">Microsoft non fornisce alcuna garanzia, esplicita o implicita, in relazione alle informazioni contenute in questo documento.</span><span class="sxs-lookup"><span data-stu-id="f2758-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="f2758-109">I codici di errore possono essere restituiti da un'operazione in una delle API Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="f2758-109">Error codes may be returned by an operation on any of the Microsoft 365 Defender APIs.</span></span> <span data-ttu-id="f2758-110">Ogni risposta di errore conterrà un messaggio di errore che consente di risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="f2758-110">Every error response will contain an error message, which can help resolve the problem.</span></span> <span data-ttu-id="f2758-111">Nella colonna messaggio di errore nella sezione tabella sono disponibili alcuni messaggi di esempio.</span><span class="sxs-lookup"><span data-stu-id="f2758-111">The error message column in the table section provides some sample messages.</span></span> <span data-ttu-id="f2758-112">Il contenuto dei messaggi effettivi varia in base ai fattori che hanno attivato la risposta.</span><span class="sxs-lookup"><span data-stu-id="f2758-112">The content of actual messages will vary based on the factors that triggered the response.</span></span> <span data-ttu-id="f2758-113">Il contenuto delle variabili è indicato nella tabella da parentesi angolari.</span><span class="sxs-lookup"><span data-stu-id="f2758-113">Variable content is indicated in the table by angle brackets.</span></span>

## <a name="error-codes"></a><span data-ttu-id="f2758-114">Codici di errore</span><span class="sxs-lookup"><span data-stu-id="f2758-114">Error codes</span></span>

<span data-ttu-id="f2758-115">Codice di errore</span><span class="sxs-lookup"><span data-stu-id="f2758-115">Error code</span></span> | <span data-ttu-id="f2758-116">Codice di stato HTTP</span><span class="sxs-lookup"><span data-stu-id="f2758-116">HTTP status code</span></span> | <span data-ttu-id="f2758-117">Messaggio</span><span class="sxs-lookup"><span data-stu-id="f2758-117">Message</span></span>
-|-|-
<span data-ttu-id="f2758-118">BadRequest</span><span class="sxs-lookup"><span data-stu-id="f2758-118">BadRequest</span></span> | <span data-ttu-id="f2758-119">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="f2758-119">BadRequest (400)</span></span> | <span data-ttu-id="f2758-120">Messaggio di errore Generale richiesta non valida.</span><span class="sxs-lookup"><span data-stu-id="f2758-120">General Bad Request error message.</span></span>
<span data-ttu-id="f2758-121">ODataError</span><span class="sxs-lookup"><span data-stu-id="f2758-121">ODataError</span></span> | <span data-ttu-id="f2758-122">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="f2758-122">BadRequest (400)</span></span> | <span data-ttu-id="f2758-123">Query URI OData non \<the specific error is specified\> valida.</span><span class="sxs-lookup"><span data-stu-id="f2758-123">Invalid OData URI query \<the specific error is specified\>.</span></span>
<span data-ttu-id="f2758-124">InvalidInput</span><span class="sxs-lookup"><span data-stu-id="f2758-124">InvalidInput</span></span> | <span data-ttu-id="f2758-125">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="f2758-125">BadRequest (400)</span></span> | <span data-ttu-id="f2758-126">Input non \<the invalid input\> valido.</span><span class="sxs-lookup"><span data-stu-id="f2758-126">Invalid input \<the invalid input\>.</span></span>
<span data-ttu-id="f2758-127">InvalidRequestBody</span><span class="sxs-lookup"><span data-stu-id="f2758-127">InvalidRequestBody</span></span> | <span data-ttu-id="f2758-128">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="f2758-128">BadRequest (400)</span></span> | <span data-ttu-id="f2758-129">Corpo della richiesta non valido.</span><span class="sxs-lookup"><span data-stu-id="f2758-129">Invalid request body.</span></span>
<span data-ttu-id="f2758-130">InvalidHashValue</span><span class="sxs-lookup"><span data-stu-id="f2758-130">InvalidHashValue</span></span> | <span data-ttu-id="f2758-131">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="f2758-131">BadRequest (400)</span></span> | <span data-ttu-id="f2758-132">Valore hash \<the invalid hash\> non valido.</span><span class="sxs-lookup"><span data-stu-id="f2758-132">Hash value \<the invalid hash\> is invalid.</span></span>
<span data-ttu-id="f2758-133">InvalidDomainName</span><span class="sxs-lookup"><span data-stu-id="f2758-133">InvalidDomainName</span></span> | <span data-ttu-id="f2758-134">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="f2758-134">BadRequest (400)</span></span> | <span data-ttu-id="f2758-135">Nome di \<the invalid domain\> dominio non valido.</span><span class="sxs-lookup"><span data-stu-id="f2758-135">Domain name \<the invalid domain\> is invalid.</span></span>
<span data-ttu-id="f2758-136">InvalidIpAddress</span><span class="sxs-lookup"><span data-stu-id="f2758-136">InvalidIpAddress</span></span> | <span data-ttu-id="f2758-137">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="f2758-137">BadRequest (400)</span></span> | <span data-ttu-id="f2758-138">Indirizzo IP \<the invalid IP\> non valido.</span><span class="sxs-lookup"><span data-stu-id="f2758-138">IP address \<the invalid IP\> is invalid.</span></span>
<span data-ttu-id="f2758-139">InvalidUrl</span><span class="sxs-lookup"><span data-stu-id="f2758-139">InvalidUrl</span></span> | <span data-ttu-id="f2758-140">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="f2758-140">BadRequest (400)</span></span> | <span data-ttu-id="f2758-141">URL \<the invalid URL\> non valido.</span><span class="sxs-lookup"><span data-stu-id="f2758-141">URL \<the invalid URL\> is invalid.</span></span>
<span data-ttu-id="f2758-142">MaximumBatchSizeExceeded</span><span class="sxs-lookup"><span data-stu-id="f2758-142">MaximumBatchSizeExceeded</span></span> | <span data-ttu-id="f2758-143">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="f2758-143">BadRequest (400)</span></span> | <span data-ttu-id="f2758-144">Dimensione massima batch superata.</span><span class="sxs-lookup"><span data-stu-id="f2758-144">Maximum batch size exceeded.</span></span> <span data-ttu-id="f2758-145">Ricevuto: \<batch size received\> , consentito: {dimensione batch consentita}.</span><span class="sxs-lookup"><span data-stu-id="f2758-145">Received: \<batch size received\>, allowed: {batch size allowed}.</span></span>
<span data-ttu-id="f2758-146">MissingRequiredParameter</span><span class="sxs-lookup"><span data-stu-id="f2758-146">MissingRequiredParameter</span></span> | <span data-ttu-id="f2758-147">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="f2758-147">BadRequest (400)</span></span> | <span data-ttu-id="f2758-148">Parametro \<the missing parameter\> mancante.</span><span class="sxs-lookup"><span data-stu-id="f2758-148">Parameter \<the missing parameter\> is missing.</span></span>
<span data-ttu-id="f2758-149">OsPlatformNotSupported</span><span class="sxs-lookup"><span data-stu-id="f2758-149">OsPlatformNotSupported</span></span> | <span data-ttu-id="f2758-150">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="f2758-150">BadRequest (400)</span></span> | <span data-ttu-id="f2758-151">Piattaforma del \<the client OS Platform\> sistema operativo non supportata per questa azione.</span><span class="sxs-lookup"><span data-stu-id="f2758-151">OS Platform \<the client OS Platform\> is not supported for this action.</span></span>
<span data-ttu-id="f2758-152">ClientVersionNotSupported</span><span class="sxs-lookup"><span data-stu-id="f2758-152">ClientVersionNotSupported</span></span> | <span data-ttu-id="f2758-153">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="f2758-153">BadRequest (400)</span></span> | <span data-ttu-id="f2758-154">\<The requested action\> è supportato nella versione client \<supported client version\> e versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="f2758-154">\<The requested action\> is supported on client version \<supported client version\> and above.</span></span>
<span data-ttu-id="f2758-155">Non autorizzato</span><span class="sxs-lookup"><span data-stu-id="f2758-155">Unauthorized</span></span> | <span data-ttu-id="f2758-156">Non autorizzato (401)</span><span class="sxs-lookup"><span data-stu-id="f2758-156">Unauthorized (401)</span></span> | <span data-ttu-id="f2758-157">Non autorizzato</span><span class="sxs-lookup"><span data-stu-id="f2758-157">Unauthorized</span></span> <br /><br /><span data-ttu-id="f2758-158">*Nota: in genere causata da un'intestazione di autorizzazione non valida o scaduta.*</span><span class="sxs-lookup"><span data-stu-id="f2758-158">*Note: Usually caused by an invalid or expired authorization header.*</span></span>
<span data-ttu-id="f2758-159">Accesso negato</span><span class="sxs-lookup"><span data-stu-id="f2758-159">Forbidden</span></span> | <span data-ttu-id="f2758-160">Accesso negato (403)</span><span class="sxs-lookup"><span data-stu-id="f2758-160">Forbidden (403)</span></span> | <span data-ttu-id="f2758-161">Accesso negato</span><span class="sxs-lookup"><span data-stu-id="f2758-161">Forbidden</span></span> <br /><br /><span data-ttu-id="f2758-162">*Nota: token valido ma autorizzazione insufficiente per l'azione.*</span><span class="sxs-lookup"><span data-stu-id="f2758-162">*Note: Valid token but insufficient permission for the action*.</span></span>
<span data-ttu-id="f2758-163">DisabledFeature</span><span class="sxs-lookup"><span data-stu-id="f2758-163">DisabledFeature</span></span> | <span data-ttu-id="f2758-164">Accesso negato (403)</span><span class="sxs-lookup"><span data-stu-id="f2758-164">Forbidden (403)</span></span> | <span data-ttu-id="f2758-165">La funzionalità tenant non è abilitata.</span><span class="sxs-lookup"><span data-stu-id="f2758-165">Tenant feature is not enabled.</span></span>
<span data-ttu-id="f2758-166">DisallowedOperation</span><span class="sxs-lookup"><span data-stu-id="f2758-166">DisallowedOperation</span></span> | <span data-ttu-id="f2758-167">Accesso negato (403)</span><span class="sxs-lookup"><span data-stu-id="f2758-167">Forbidden (403)</span></span> | <span data-ttu-id="f2758-168">\<the disallowed operation and the reason\>.</span><span class="sxs-lookup"><span data-stu-id="f2758-168">\<the disallowed operation and the reason\>.</span></span>
<span data-ttu-id="f2758-169">NotFound</span><span class="sxs-lookup"><span data-stu-id="f2758-169">NotFound</span></span> | <span data-ttu-id="f2758-170">Non trovato (404)</span><span class="sxs-lookup"><span data-stu-id="f2758-170">Not Found (404)</span></span> | <span data-ttu-id="f2758-171">Messaggio di errore Generale non trovato.</span><span class="sxs-lookup"><span data-stu-id="f2758-171">General Not Found error message.</span></span>
<span data-ttu-id="f2758-172">ResourceNotFound</span><span class="sxs-lookup"><span data-stu-id="f2758-172">ResourceNotFound</span></span> | <span data-ttu-id="f2758-173">Non trovato (404)</span><span class="sxs-lookup"><span data-stu-id="f2758-173">Not Found (404)</span></span> | <span data-ttu-id="f2758-174">Risorsa \<the requested resource\> non trovata.</span><span class="sxs-lookup"><span data-stu-id="f2758-174">Resource \<the requested resource\> was not found.</span></span>
<span data-ttu-id="f2758-175">InternalServerError</span><span class="sxs-lookup"><span data-stu-id="f2758-175">InternalServerError</span></span> | <span data-ttu-id="f2758-176">Errore interno del server (500)</span><span class="sxs-lookup"><span data-stu-id="f2758-176">Internal Server Error (500)</span></span> | <span data-ttu-id="f2758-177">*Nota: nessun messaggio di errore, ritentare l'operazione o contattare Microsoft se non viene risolto*</span><span class="sxs-lookup"><span data-stu-id="f2758-177">*Note: No error message,  retry the operation or contact Microsoft if it does not get resolved*</span></span>

## <a name="examples"></a><span data-ttu-id="f2758-178">Esempi</span><span class="sxs-lookup"><span data-stu-id="f2758-178">Examples</span></span>

```json
{
    "error": {
        "code": "ResourceNotFound",
        "message": "Machine 123123123 was not found",
        "target": "43f4cb08-8fac-4b65-9db1-745c2ae65f3a"
    }
}
```

```json
{
    "error": {
        "code": "InvalidRequestBody",
        "message": "Request body is incorrect",
        "target": "1fa66c0f-18bd-4133-b378-36d76f3a2ba0"
    }
}
```

## <a name="body-parameters"></a><span data-ttu-id="f2758-179">Parametri corpo</span><span class="sxs-lookup"><span data-stu-id="f2758-179">Body parameters</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f2758-180">Per i parametri corpo viene fatto distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="f2758-180">Body parameters are case-sensitive.</span></span>

<span data-ttu-id="f2758-181">Se si verifica un *errore InvalidRequestBody* o *MissingRequiredParameter,* potrebbe essere causato da un errore di digitazione.</span><span class="sxs-lookup"><span data-stu-id="f2758-181">If you experience an *InvalidRequestBody* or *MissingRequiredParameter* error, it might be caused by a typo.</span></span> <span data-ttu-id="f2758-182">Esaminare la documentazione dell'API e verificare che i parametri inviati corrispondano all'esempio pertinente.</span><span class="sxs-lookup"><span data-stu-id="f2758-182">Review the API documentation and check that the submitted parameters match the relevant example.</span></span>

## <a name="tracking-id"></a><span data-ttu-id="f2758-183">ID tracciabilità</span><span class="sxs-lookup"><span data-stu-id="f2758-183">Tracking ID</span></span>

<span data-ttu-id="f2758-184">Ogni risposta di errore contiene un parametro ID univoco per il rilevamento.</span><span class="sxs-lookup"><span data-stu-id="f2758-184">Each error response contains a unique ID parameter for tracking.</span></span> <span data-ttu-id="f2758-185">Il nome della proprietà di questo parametro è *target*.</span><span class="sxs-lookup"><span data-stu-id="f2758-185">The property name of this parameter is *target*.</span></span> <span data-ttu-id="f2758-186">Quando ci viene contattato per un errore, l'associazione di questo ID ci aiuterà a trovare la causa principale del problema.</span><span class="sxs-lookup"><span data-stu-id="f2758-186">When contacting us about an error, attaching this ID will help us find the root cause of the problem.</span></span>

## <a name="related-articles"></a><span data-ttu-id="f2758-187">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="f2758-187">Related articles</span></span>

- [<span data-ttu-id="f2758-188">Microsoft 365 Panoramica delle API defender</span><span class="sxs-lookup"><span data-stu-id="f2758-188">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="f2758-189">API supportate di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f2758-189">Supported Microsoft 365 Defender APIs</span></span>](api-supported.md)
- [<span data-ttu-id="f2758-190">Accedere alle API di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f2758-190">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="f2758-191">Informazioni sui limiti delle API e sulle licenze</span><span class="sxs-lookup"><span data-stu-id="f2758-191">Learn about API limits and licensing</span></span>](api-terms.md)
