---
title: Codici di errore comuni dell'API REST di Microsoft 365 Defender
description: Informazioni sui codici di errore comuni dell'API REST di Microsoft 365 Defender
keywords: api, error, codes, common errors, mtp, api error codes
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 15eabc8ff28e7cc0313e2a1cb701403de0eab120
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928391"
---
# <a name="common-microsoft-365-defender-rest-api-error-codes"></a><span data-ttu-id="b74a3-104">Codici di errore comuni dell'API REST di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b74a3-104">Common Microsoft 365 Defender REST API error codes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="b74a3-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="b74a3-105">**Applies to:**</span></span>

- <span data-ttu-id="b74a3-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b74a3-106">Microsoft Threat Protection</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b74a3-107">Alcune informazioni riguardano prodotti non rilasciati in precedenza che potrebbero essere sostanzialmente modificati prima del rilascio sul mercato.</span><span class="sxs-lookup"><span data-stu-id="b74a3-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="b74a3-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="b74a3-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="b74a3-109">I codici di errore possono essere restituiti da un'operazione su una qualsiasi delle API di Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="b74a3-109">Error codes may be returned by an operation on any of the Microsoft 365 Defender APIs.</span></span> <span data-ttu-id="b74a3-110">Ogni risposta di errore conterrà un messaggio di errore che può aiutare a risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="b74a3-110">Every error response will contain an error message, which can help resolve the problem.</span></span> <span data-ttu-id="b74a3-111">Nella colonna dei messaggi di errore nella sezione della tabella sono disponibili alcuni messaggi di esempio.</span><span class="sxs-lookup"><span data-stu-id="b74a3-111">The error message column in the table section provides some sample messages.</span></span> <span data-ttu-id="b74a3-112">Il contenuto dei messaggi effettivi varia in base ai fattori che hanno attivato la risposta.</span><span class="sxs-lookup"><span data-stu-id="b74a3-112">The content of actual messages will vary based on the factors that triggered the response.</span></span> <span data-ttu-id="b74a3-113">Il contenuto delle variabili è indicato nella tabella da parentesi angolari.</span><span class="sxs-lookup"><span data-stu-id="b74a3-113">Variable content is indicated in the table by angle brackets.</span></span>

## <a name="error-codes"></a><span data-ttu-id="b74a3-114">Codici di errore</span><span class="sxs-lookup"><span data-stu-id="b74a3-114">Error codes</span></span>

<span data-ttu-id="b74a3-115">Codice di errore</span><span class="sxs-lookup"><span data-stu-id="b74a3-115">Error code</span></span> | <span data-ttu-id="b74a3-116">Codice di stato HTTP</span><span class="sxs-lookup"><span data-stu-id="b74a3-116">HTTP status code</span></span> | <span data-ttu-id="b74a3-117">Messaggio</span><span class="sxs-lookup"><span data-stu-id="b74a3-117">Message</span></span>
-|-|-
<span data-ttu-id="b74a3-118">BadRequest</span><span class="sxs-lookup"><span data-stu-id="b74a3-118">BadRequest</span></span> | <span data-ttu-id="b74a3-119">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="b74a3-119">BadRequest (400)</span></span> | <span data-ttu-id="b74a3-120">Messaggio di errore Generale richiesta non valida.</span><span class="sxs-lookup"><span data-stu-id="b74a3-120">General Bad Request error message.</span></span>
<span data-ttu-id="b74a3-121">ODataError</span><span class="sxs-lookup"><span data-stu-id="b74a3-121">ODataError</span></span> | <span data-ttu-id="b74a3-122">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="b74a3-122">BadRequest (400)</span></span> | <span data-ttu-id="b74a3-123">Query URI OData non \<the specific error is specified\> valida.</span><span class="sxs-lookup"><span data-stu-id="b74a3-123">Invalid OData URI query \<the specific error is specified\>.</span></span>
<span data-ttu-id="b74a3-124">InvalidInput</span><span class="sxs-lookup"><span data-stu-id="b74a3-124">InvalidInput</span></span> | <span data-ttu-id="b74a3-125">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="b74a3-125">BadRequest (400)</span></span> | <span data-ttu-id="b74a3-126">Input non \<the invalid input\> valido.</span><span class="sxs-lookup"><span data-stu-id="b74a3-126">Invalid input \<the invalid input\>.</span></span>
<span data-ttu-id="b74a3-127">InvalidRequestBody</span><span class="sxs-lookup"><span data-stu-id="b74a3-127">InvalidRequestBody</span></span> | <span data-ttu-id="b74a3-128">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="b74a3-128">BadRequest (400)</span></span> | <span data-ttu-id="b74a3-129">Corpo della richiesta non valido.</span><span class="sxs-lookup"><span data-stu-id="b74a3-129">Invalid request body.</span></span>
<span data-ttu-id="b74a3-130">InvalidHashValue</span><span class="sxs-lookup"><span data-stu-id="b74a3-130">InvalidHashValue</span></span> | <span data-ttu-id="b74a3-131">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="b74a3-131">BadRequest (400)</span></span> | <span data-ttu-id="b74a3-132">Valore hash \<the invalid hash\> non valido.</span><span class="sxs-lookup"><span data-stu-id="b74a3-132">Hash value \<the invalid hash\> is invalid.</span></span>
<span data-ttu-id="b74a3-133">InvalidDomainName</span><span class="sxs-lookup"><span data-stu-id="b74a3-133">InvalidDomainName</span></span> | <span data-ttu-id="b74a3-134">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="b74a3-134">BadRequest (400)</span></span> | <span data-ttu-id="b74a3-135">Nome di dominio \<the invalid domain\> non valido.</span><span class="sxs-lookup"><span data-stu-id="b74a3-135">Domain name \<the invalid domain\> is invalid.</span></span>
<span data-ttu-id="b74a3-136">InvalidIpAddress</span><span class="sxs-lookup"><span data-stu-id="b74a3-136">InvalidIpAddress</span></span> | <span data-ttu-id="b74a3-137">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="b74a3-137">BadRequest (400)</span></span> | <span data-ttu-id="b74a3-138">Indirizzo IP \<the invalid IP\> non valido.</span><span class="sxs-lookup"><span data-stu-id="b74a3-138">IP address \<the invalid IP\> is invalid.</span></span>
<span data-ttu-id="b74a3-139">InvalidUrl</span><span class="sxs-lookup"><span data-stu-id="b74a3-139">InvalidUrl</span></span> | <span data-ttu-id="b74a3-140">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="b74a3-140">BadRequest (400)</span></span> | <span data-ttu-id="b74a3-141">URL \<the invalid URL\> non valido.</span><span class="sxs-lookup"><span data-stu-id="b74a3-141">URL \<the invalid URL\> is invalid.</span></span>
<span data-ttu-id="b74a3-142">MaximumBatchSizeExceeded</span><span class="sxs-lookup"><span data-stu-id="b74a3-142">MaximumBatchSizeExceeded</span></span> | <span data-ttu-id="b74a3-143">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="b74a3-143">BadRequest (400)</span></span> | <span data-ttu-id="b74a3-144">Dimensione massima batch superata.</span><span class="sxs-lookup"><span data-stu-id="b74a3-144">Maximum batch size exceeded.</span></span> <span data-ttu-id="b74a3-145">Ricevuto: \<batch size received\> , consentito: {dimensione batch consentita}.</span><span class="sxs-lookup"><span data-stu-id="b74a3-145">Received: \<batch size received\>, allowed: {batch size allowed}.</span></span>
<span data-ttu-id="b74a3-146">MissingRequiredParameter</span><span class="sxs-lookup"><span data-stu-id="b74a3-146">MissingRequiredParameter</span></span> | <span data-ttu-id="b74a3-147">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="b74a3-147">BadRequest (400)</span></span> | <span data-ttu-id="b74a3-148">Parametro \<the missing parameter\> mancante.</span><span class="sxs-lookup"><span data-stu-id="b74a3-148">Parameter \<the missing parameter\> is missing.</span></span>
<span data-ttu-id="b74a3-149">OsPlatformNotSupported</span><span class="sxs-lookup"><span data-stu-id="b74a3-149">OsPlatformNotSupported</span></span> | <span data-ttu-id="b74a3-150">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="b74a3-150">BadRequest (400)</span></span> | <span data-ttu-id="b74a3-151">Piattaforma del sistema \<the client OS Platform\> operativo non supportata per questa azione.</span><span class="sxs-lookup"><span data-stu-id="b74a3-151">OS Platform \<the client OS Platform\> is not supported for this action.</span></span>
<span data-ttu-id="b74a3-152">ClientVersionNotSupported</span><span class="sxs-lookup"><span data-stu-id="b74a3-152">ClientVersionNotSupported</span></span> | <span data-ttu-id="b74a3-153">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="b74a3-153">BadRequest (400)</span></span> | <span data-ttu-id="b74a3-154">\<The requested action\> è supportato nella versione client \<supported client version\> e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="b74a3-154">\<The requested action\> is supported on client version \<supported client version\> and above.</span></span>
<span data-ttu-id="b74a3-155">Non autorizzato</span><span class="sxs-lookup"><span data-stu-id="b74a3-155">Unauthorized</span></span> | <span data-ttu-id="b74a3-156">Non autorizzato (401)</span><span class="sxs-lookup"><span data-stu-id="b74a3-156">Unauthorized (401)</span></span> | <span data-ttu-id="b74a3-157">Non autorizzato</span><span class="sxs-lookup"><span data-stu-id="b74a3-157">Unauthorized</span></span> <br /><br /><span data-ttu-id="b74a3-158">*Nota: in genere causata da un'intestazione di autorizzazione non valida o scaduta.*</span><span class="sxs-lookup"><span data-stu-id="b74a3-158">*Note: Usually caused by an invalid or expired authorization header.*</span></span>
<span data-ttu-id="b74a3-159">Accesso negato</span><span class="sxs-lookup"><span data-stu-id="b74a3-159">Forbidden</span></span> | <span data-ttu-id="b74a3-160">Accesso negato (403)</span><span class="sxs-lookup"><span data-stu-id="b74a3-160">Forbidden (403)</span></span> | <span data-ttu-id="b74a3-161">Accesso negato</span><span class="sxs-lookup"><span data-stu-id="b74a3-161">Forbidden</span></span> <br /><br /><span data-ttu-id="b74a3-162">*Nota: token valido ma autorizzazioni insufficienti per l'azione.*</span><span class="sxs-lookup"><span data-stu-id="b74a3-162">*Note: Valid token but insufficient permission for the action*.</span></span>
<span data-ttu-id="b74a3-163">DisabledFeature</span><span class="sxs-lookup"><span data-stu-id="b74a3-163">DisabledFeature</span></span> | <span data-ttu-id="b74a3-164">Accesso negato (403)</span><span class="sxs-lookup"><span data-stu-id="b74a3-164">Forbidden (403)</span></span> | <span data-ttu-id="b74a3-165">La funzionalità tenant non è abilitata.</span><span class="sxs-lookup"><span data-stu-id="b74a3-165">Tenant feature is not enabled.</span></span>
<span data-ttu-id="b74a3-166">DisallowedOperation</span><span class="sxs-lookup"><span data-stu-id="b74a3-166">DisallowedOperation</span></span> | <span data-ttu-id="b74a3-167">Accesso negato (403)</span><span class="sxs-lookup"><span data-stu-id="b74a3-167">Forbidden (403)</span></span> | <span data-ttu-id="b74a3-168">\<the disallowed operation and the reason\>.</span><span class="sxs-lookup"><span data-stu-id="b74a3-168">\<the disallowed operation and the reason\>.</span></span>
<span data-ttu-id="b74a3-169">NotFound</span><span class="sxs-lookup"><span data-stu-id="b74a3-169">NotFound</span></span> | <span data-ttu-id="b74a3-170">Non trovato (404)</span><span class="sxs-lookup"><span data-stu-id="b74a3-170">Not Found (404)</span></span> | <span data-ttu-id="b74a3-171">Messaggio di errore Generale non trovato.</span><span class="sxs-lookup"><span data-stu-id="b74a3-171">General Not Found error message.</span></span>
<span data-ttu-id="b74a3-172">ResourceNotFound</span><span class="sxs-lookup"><span data-stu-id="b74a3-172">ResourceNotFound</span></span> | <span data-ttu-id="b74a3-173">Non trovato (404)</span><span class="sxs-lookup"><span data-stu-id="b74a3-173">Not Found (404)</span></span> | <span data-ttu-id="b74a3-174">Risorsa \<the requested resource\> non trovata.</span><span class="sxs-lookup"><span data-stu-id="b74a3-174">Resource \<the requested resource\> was not found.</span></span>
<span data-ttu-id="b74a3-175">InternalServerError</span><span class="sxs-lookup"><span data-stu-id="b74a3-175">InternalServerError</span></span> | <span data-ttu-id="b74a3-176">Errore interno del server (500)</span><span class="sxs-lookup"><span data-stu-id="b74a3-176">Internal Server Error (500)</span></span> | <span data-ttu-id="b74a3-177">*Nota: nessun messaggio di errore, ritenta l'operazione o contatta Microsoft se non viene risolto*</span><span class="sxs-lookup"><span data-stu-id="b74a3-177">*Note: No error message,  retry the operation or contact Microsoft if it does not get resolved*</span></span>

## <a name="examples"></a><span data-ttu-id="b74a3-178">Esempi</span><span class="sxs-lookup"><span data-stu-id="b74a3-178">Examples</span></span>

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

## <a name="body-parameters"></a><span data-ttu-id="b74a3-179">Parametri del corpo</span><span class="sxs-lookup"><span data-stu-id="b74a3-179">Body parameters</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b74a3-180">Per i parametri del corpo viene fatto distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="b74a3-180">Body parameters are case-sensitive.</span></span>

<span data-ttu-id="b74a3-181">Se si verifica un *errore InvalidRequestBody* o *MissingRequiredParameter,* potrebbe essere causato da un errore di digitazione.</span><span class="sxs-lookup"><span data-stu-id="b74a3-181">If you experience an *InvalidRequestBody* or *MissingRequiredParameter* error, it might be caused by a typo.</span></span> <span data-ttu-id="b74a3-182">Esaminare la documentazione dell'API e verificare che i parametri inviati corrispondano all'esempio pertinente.</span><span class="sxs-lookup"><span data-stu-id="b74a3-182">Review the API documentation and check that the submitted parameters match the relevant example.</span></span>

## <a name="tracking-id"></a><span data-ttu-id="b74a3-183">ID tracciabilità</span><span class="sxs-lookup"><span data-stu-id="b74a3-183">Tracking ID</span></span>

<span data-ttu-id="b74a3-184">Ogni risposta di errore contiene un parametro ID univoco per la verifica.</span><span class="sxs-lookup"><span data-stu-id="b74a3-184">Each error response contains a unique ID parameter for tracking.</span></span> <span data-ttu-id="b74a3-185">Il nome della proprietà di questo parametro è *target.*</span><span class="sxs-lookup"><span data-stu-id="b74a3-185">The property name of this parameter is *target*.</span></span> <span data-ttu-id="b74a3-186">Quando ci viene contattato per un errore, l'associazione di questo ID ci consente di individuare la causa principale del problema.</span><span class="sxs-lookup"><span data-stu-id="b74a3-186">When contacting us about an error, attaching this ID will help us find the root cause of the problem.</span></span>

## <a name="related-articles"></a><span data-ttu-id="b74a3-187">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="b74a3-187">Related articles</span></span>

- [<span data-ttu-id="b74a3-188">Panoramica delle API di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b74a3-188">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="b74a3-189">API supportate di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b74a3-189">Supported Microsoft 365 Defender APIs</span></span>](api-supported.md)
- [<span data-ttu-id="b74a3-190">Accedere alle API di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b74a3-190">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="b74a3-191">Informazioni sui limiti delle API e sulle licenze</span><span class="sxs-lookup"><span data-stu-id="b74a3-191">Learn about API limits and licensing</span></span>](api-terms.md)
