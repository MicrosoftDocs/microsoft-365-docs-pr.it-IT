---
title: Codici di errore dell'API REST comuni di Microsoft 365 Defender
description: Informazioni sui codici di errore dell'API REST di Microsoft 365 Defender comuni
keywords: API, errore, codici, errori comuni, MTP, codici di errore dell'API
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 0df741efb7555d587a6033acc23716e93f542d5e
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719215"
---
# <a name="common-microsoft-365-defender-rest-api-error-codes"></a><span data-ttu-id="d69a3-104">Codici di errore dell'API REST comuni di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d69a3-104">Common Microsoft 365 Defender REST API error codes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="d69a3-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="d69a3-105">**Applies to:**</span></span>

- <span data-ttu-id="d69a3-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="d69a3-106">Microsoft Threat Protection</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d69a3-107">Alcune informazioni si riferiscono al prodotto prerilasciato che può essere modificato in modo sostanziale prima che venga rilasciato commercialmente.</span><span class="sxs-lookup"><span data-stu-id="d69a3-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="d69a3-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="d69a3-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="d69a3-109">È possibile che i codici di errore vengano restituiti da un'operazione in una qualsiasi delle API di Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="d69a3-109">Error codes may be returned by an operation on any of the Microsoft 365 Defender APIs.</span></span> <span data-ttu-id="d69a3-110">Ogni risposta di errore conterrà un messaggio di errore che può contribuire a risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="d69a3-110">Every error response will contain an error message, which can help resolve the problem.</span></span> <span data-ttu-id="d69a3-111">Nella colonna messaggio di errore della sezione tabella sono disponibili alcuni messaggi di esempio.</span><span class="sxs-lookup"><span data-stu-id="d69a3-111">The error message column in the table section provides some sample messages.</span></span> <span data-ttu-id="d69a3-112">Il contenuto dei messaggi effettivi varia in base ai fattori che hanno attivato la risposta.</span><span class="sxs-lookup"><span data-stu-id="d69a3-112">The content of actual messages will vary based on the factors that triggered the response.</span></span> <span data-ttu-id="d69a3-113">Il contenuto variabile viene indicato nella tabella in base all'angolo tra parentesi quadre.</span><span class="sxs-lookup"><span data-stu-id="d69a3-113">Variable content is indicated in the table by angle brackets.</span></span>

## <a name="error-codes"></a><span data-ttu-id="d69a3-114">Codici di errore</span><span class="sxs-lookup"><span data-stu-id="d69a3-114">Error codes</span></span>

<span data-ttu-id="d69a3-115">Codice errore</span><span class="sxs-lookup"><span data-stu-id="d69a3-115">Error code</span></span> | <span data-ttu-id="d69a3-116">Codice di stato HTTP</span><span class="sxs-lookup"><span data-stu-id="d69a3-116">HTTP status code</span></span> | <span data-ttu-id="d69a3-117">Messaggio</span><span class="sxs-lookup"><span data-stu-id="d69a3-117">Message</span></span>
-|-|-
<span data-ttu-id="d69a3-118">BadRequest</span><span class="sxs-lookup"><span data-stu-id="d69a3-118">BadRequest</span></span> | <span data-ttu-id="d69a3-119">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="d69a3-119">BadRequest (400)</span></span> | <span data-ttu-id="d69a3-120">Messaggio di errore generale di richiesta non valida.</span><span class="sxs-lookup"><span data-stu-id="d69a3-120">General Bad Request error message.</span></span>
<span data-ttu-id="d69a3-121">ODataError</span><span class="sxs-lookup"><span data-stu-id="d69a3-121">ODataError</span></span> | <span data-ttu-id="d69a3-122">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="d69a3-122">BadRequest (400)</span></span> | <span data-ttu-id="d69a3-123">Query URI OData non valida \<the specific error is specified\> .</span><span class="sxs-lookup"><span data-stu-id="d69a3-123">Invalid OData URI query \<the specific error is specified\>.</span></span>
<span data-ttu-id="d69a3-124">InvalidInput</span><span class="sxs-lookup"><span data-stu-id="d69a3-124">InvalidInput</span></span> | <span data-ttu-id="d69a3-125">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="d69a3-125">BadRequest (400)</span></span> | <span data-ttu-id="d69a3-126">Input non valido \<the invalid input\> .</span><span class="sxs-lookup"><span data-stu-id="d69a3-126">Invalid input \<the invalid input\>.</span></span>
<span data-ttu-id="d69a3-127">InvalidRequestBody</span><span class="sxs-lookup"><span data-stu-id="d69a3-127">InvalidRequestBody</span></span> | <span data-ttu-id="d69a3-128">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="d69a3-128">BadRequest (400)</span></span> | <span data-ttu-id="d69a3-129">Corpo richiesta non valida.</span><span class="sxs-lookup"><span data-stu-id="d69a3-129">Invalid request body.</span></span>
<span data-ttu-id="d69a3-130">InvalidHashValue</span><span class="sxs-lookup"><span data-stu-id="d69a3-130">InvalidHashValue</span></span> | <span data-ttu-id="d69a3-131">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="d69a3-131">BadRequest (400)</span></span> | <span data-ttu-id="d69a3-132">Il valore hash \<the invalid hash\> non è valido.</span><span class="sxs-lookup"><span data-stu-id="d69a3-132">Hash value \<the invalid hash\> is invalid.</span></span>
<span data-ttu-id="d69a3-133">InvalidDomainName</span><span class="sxs-lookup"><span data-stu-id="d69a3-133">InvalidDomainName</span></span> | <span data-ttu-id="d69a3-134">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="d69a3-134">BadRequest (400)</span></span> | <span data-ttu-id="d69a3-135">Il nome di dominio \<the invalid domain\> non è valido.</span><span class="sxs-lookup"><span data-stu-id="d69a3-135">Domain name \<the invalid domain\> is invalid.</span></span>
<span data-ttu-id="d69a3-136">InvalidIpAddress</span><span class="sxs-lookup"><span data-stu-id="d69a3-136">InvalidIpAddress</span></span> | <span data-ttu-id="d69a3-137">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="d69a3-137">BadRequest (400)</span></span> | <span data-ttu-id="d69a3-138">L'indirizzo IP \<the invalid IP\> non è valido.</span><span class="sxs-lookup"><span data-stu-id="d69a3-138">IP address \<the invalid IP\> is invalid.</span></span>
<span data-ttu-id="d69a3-139">InvalidUrl</span><span class="sxs-lookup"><span data-stu-id="d69a3-139">InvalidUrl</span></span> | <span data-ttu-id="d69a3-140">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="d69a3-140">BadRequest (400)</span></span> | <span data-ttu-id="d69a3-141">L'URL \<the invalid URL\> non è valido.</span><span class="sxs-lookup"><span data-stu-id="d69a3-141">URL \<the invalid URL\> is invalid.</span></span>
<span data-ttu-id="d69a3-142">MaximumBatchSizeExceeded</span><span class="sxs-lookup"><span data-stu-id="d69a3-142">MaximumBatchSizeExceeded</span></span> | <span data-ttu-id="d69a3-143">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="d69a3-143">BadRequest (400)</span></span> | <span data-ttu-id="d69a3-144">Dimensioni massime del batch superate.</span><span class="sxs-lookup"><span data-stu-id="d69a3-144">Maximum batch size exceeded.</span></span> <span data-ttu-id="d69a3-145">Ricevuto: \<batch size received\> , consentito: {dimensioni batch consentite}.</span><span class="sxs-lookup"><span data-stu-id="d69a3-145">Received: \<batch size received\>, allowed: {batch size allowed}.</span></span>
<span data-ttu-id="d69a3-146">MissingRequiredParameter</span><span class="sxs-lookup"><span data-stu-id="d69a3-146">MissingRequiredParameter</span></span> | <span data-ttu-id="d69a3-147">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="d69a3-147">BadRequest (400)</span></span> | <span data-ttu-id="d69a3-148">Il parametro \<the missing parameter\> è mancante.</span><span class="sxs-lookup"><span data-stu-id="d69a3-148">Parameter \<the missing parameter\> is missing.</span></span>
<span data-ttu-id="d69a3-149">OsPlatformNotSupported</span><span class="sxs-lookup"><span data-stu-id="d69a3-149">OsPlatformNotSupported</span></span> | <span data-ttu-id="d69a3-150">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="d69a3-150">BadRequest (400)</span></span> | <span data-ttu-id="d69a3-151">La piattaforma OS \<the client OS Platform\> non è supportata per questa azione.</span><span class="sxs-lookup"><span data-stu-id="d69a3-151">OS Platform \<the client OS Platform\> is not supported for this action.</span></span>
<span data-ttu-id="d69a3-152">ClientVersionNotSupported</span><span class="sxs-lookup"><span data-stu-id="d69a3-152">ClientVersionNotSupported</span></span> | <span data-ttu-id="d69a3-153">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="d69a3-153">BadRequest (400)</span></span> | <span data-ttu-id="d69a3-154">\<The requested action\> è supportato sulla versione client \<supported client version\> e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="d69a3-154">\<The requested action\> is supported on client version \<supported client version\> and above.</span></span>
<span data-ttu-id="d69a3-155">Non autorizzato</span><span class="sxs-lookup"><span data-stu-id="d69a3-155">Unauthorized</span></span> | <span data-ttu-id="d69a3-156">Non autorizzato (401)</span><span class="sxs-lookup"><span data-stu-id="d69a3-156">Unauthorized (401)</span></span> | <span data-ttu-id="d69a3-157">Non autorizzato</span><span class="sxs-lookup"><span data-stu-id="d69a3-157">Unauthorized</span></span> <br /><br /><span data-ttu-id="d69a3-158">*Nota: generalmente causata da un'intestazione di autorizzazione non valida o scaduta.*</span><span class="sxs-lookup"><span data-stu-id="d69a3-158">*Note: Usually caused by an invalid or expired authorization header.*</span></span>
<span data-ttu-id="d69a3-159">Proibito</span><span class="sxs-lookup"><span data-stu-id="d69a3-159">Forbidden</span></span> | <span data-ttu-id="d69a3-160">Forbidden (403)</span><span class="sxs-lookup"><span data-stu-id="d69a3-160">Forbidden (403)</span></span> | <span data-ttu-id="d69a3-161">Proibito</span><span class="sxs-lookup"><span data-stu-id="d69a3-161">Forbidden</span></span> <br /><br /><span data-ttu-id="d69a3-162">*Nota: token valido ma autorizzazione insufficiente per l'azione*.</span><span class="sxs-lookup"><span data-stu-id="d69a3-162">*Note: Valid token but insufficient permission for the action*.</span></span>
<span data-ttu-id="d69a3-163">DisabledFeature</span><span class="sxs-lookup"><span data-stu-id="d69a3-163">DisabledFeature</span></span> | <span data-ttu-id="d69a3-164">Forbidden (403)</span><span class="sxs-lookup"><span data-stu-id="d69a3-164">Forbidden (403)</span></span> | <span data-ttu-id="d69a3-165">La caratteristica tenant non è abilitata.</span><span class="sxs-lookup"><span data-stu-id="d69a3-165">Tenant feature is not enabled.</span></span>
<span data-ttu-id="d69a3-166">DisallowedOperation</span><span class="sxs-lookup"><span data-stu-id="d69a3-166">DisallowedOperation</span></span> | <span data-ttu-id="d69a3-167">Forbidden (403)</span><span class="sxs-lookup"><span data-stu-id="d69a3-167">Forbidden (403)</span></span> | <span data-ttu-id="d69a3-168">\<the disallowed operation and the reason\>.</span><span class="sxs-lookup"><span data-stu-id="d69a3-168">\<the disallowed operation and the reason\>.</span></span>
<span data-ttu-id="d69a3-169">NotFound</span><span class="sxs-lookup"><span data-stu-id="d69a3-169">NotFound</span></span> | <span data-ttu-id="d69a3-170">Non trovato (404)</span><span class="sxs-lookup"><span data-stu-id="d69a3-170">Not Found (404)</span></span> | <span data-ttu-id="d69a3-171">Messaggio di errore generale non trovato.</span><span class="sxs-lookup"><span data-stu-id="d69a3-171">General Not Found error message.</span></span>
<span data-ttu-id="d69a3-172">ResourceNotFound</span><span class="sxs-lookup"><span data-stu-id="d69a3-172">ResourceNotFound</span></span> | <span data-ttu-id="d69a3-173">Non trovato (404)</span><span class="sxs-lookup"><span data-stu-id="d69a3-173">Not Found (404)</span></span> | <span data-ttu-id="d69a3-174">La risorsa \<the requested resource\> non è stata trovata.</span><span class="sxs-lookup"><span data-stu-id="d69a3-174">Resource \<the requested resource\> was not found.</span></span>
<span data-ttu-id="d69a3-175">InternalServerError</span><span class="sxs-lookup"><span data-stu-id="d69a3-175">InternalServerError</span></span> | <span data-ttu-id="d69a3-176">Errore interno del server (500)</span><span class="sxs-lookup"><span data-stu-id="d69a3-176">Internal Server Error (500)</span></span> | <span data-ttu-id="d69a3-177">*Nota: nessun messaggio di errore, riprovare l'operazione o contattare Microsoft se non viene risolto*</span><span class="sxs-lookup"><span data-stu-id="d69a3-177">*Note: No error message,  retry the operation or contact Microsoft if it does not get resolved*</span></span>

## <a name="examples"></a><span data-ttu-id="d69a3-178">Esempi</span><span class="sxs-lookup"><span data-stu-id="d69a3-178">Examples</span></span>

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

## <a name="body-parameters"></a><span data-ttu-id="d69a3-179">Parametri corpo</span><span class="sxs-lookup"><span data-stu-id="d69a3-179">Body parameters</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d69a3-180">I parametri corpo sono distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="d69a3-180">Body parameters are case-sensitive.</span></span>

<span data-ttu-id="d69a3-181">Se si verifica un errore di *InvalidRequestBody* o *MissingRequiredParameter* , potrebbe essere causato da una typo.</span><span class="sxs-lookup"><span data-stu-id="d69a3-181">If you experience an *InvalidRequestBody* or *MissingRequiredParameter* error, it might be caused by a typo.</span></span> <span data-ttu-id="d69a3-182">Esaminare la documentazione relativa all'API e verificare che i parametri inviati corrispondano all'esempio pertinente.</span><span class="sxs-lookup"><span data-stu-id="d69a3-182">Review the API documentation and check that the submitted parameters match the relevant example.</span></span>

## <a name="tracking-id"></a><span data-ttu-id="d69a3-183">ID di rilevamento</span><span class="sxs-lookup"><span data-stu-id="d69a3-183">Tracking ID</span></span>

<span data-ttu-id="d69a3-184">Ogni risposta di errore contiene un parametro ID univoco per la verifica.</span><span class="sxs-lookup"><span data-stu-id="d69a3-184">Each error response contains a unique ID parameter for tracking.</span></span> <span data-ttu-id="d69a3-185">Il nome della proprietà di questo parametro è *target*.</span><span class="sxs-lookup"><span data-stu-id="d69a3-185">The property name of this parameter is *target*.</span></span> <span data-ttu-id="d69a3-186">Quando ci si mette in contatto con informazioni su un errore, l'associazione di questo ID ci aiuterà a trovare la causa principale del problema.</span><span class="sxs-lookup"><span data-stu-id="d69a3-186">When contacting us about an error, attaching this ID will help us find the root cause of the problem.</span></span>

## <a name="related-articles"></a><span data-ttu-id="d69a3-187">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="d69a3-187">Related articles</span></span>

- [<span data-ttu-id="d69a3-188">Panoramica delle API di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d69a3-188">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="d69a3-189">API supportate di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d69a3-189">Supported Microsoft 365 Defender APIs</span></span>](api-supported.md)
- [<span data-ttu-id="d69a3-190">Accedere alle API di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d69a3-190">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="d69a3-191">Informazioni sui limiti delle API e sulle licenze</span><span class="sxs-lookup"><span data-stu-id="d69a3-191">Learn about API limits and licensing</span></span>](api-terms.md)
