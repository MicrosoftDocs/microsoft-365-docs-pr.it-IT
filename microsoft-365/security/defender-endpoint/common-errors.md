---
title: Errori comuni delle API di Microsoft Defender ATP
description: Elenco degli errori comuni delle API di Microsoft Defender ATP con le descrizioni.
keywords: api, api mdatp, errori, risoluzione dei problemi
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ddbbe07bc477ae3a5016feb795b5bad5ed82a30a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064378"
---
# <a name="common-rest-api-error-codes"></a><span data-ttu-id="74739-104">Codici di errore API REST comuni</span><span class="sxs-lookup"><span data-stu-id="74739-104">Common REST API error codes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


* <span data-ttu-id="74739-105">I codici di errore elencati nella tabella seguente possono essere restituiti da un'operazione su qualsiasi API di Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="74739-105">The error codes listed in the following table may be returned by an operation on any of Microsoft Defender for Endpoint APIs.</span></span>
* <span data-ttu-id="74739-106">Oltre al codice di errore, ogni risposta di errore contiene un messaggio di errore che consente di risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="74739-106">In addition to the error code, every error response contains an error message, which can help resolve the problem.</span></span>
* <span data-ttu-id="74739-107">Il messaggio è un testo libero che può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="74739-107">The message is a free text that can be changed.</span></span>
* <span data-ttu-id="74739-108">Nella parte inferiore della pagina sono disponibili esempi di risposta.</span><span class="sxs-lookup"><span data-stu-id="74739-108">At the bottom of the page, you can find response examples.</span></span>

><span data-ttu-id="74739-109">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="74739-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="74739-110">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="74739-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="74739-111">Codice di errore</span><span class="sxs-lookup"><span data-stu-id="74739-111">Error code</span></span> |<span data-ttu-id="74739-112">Codice di stato HTTP</span><span class="sxs-lookup"><span data-stu-id="74739-112">HTTP status code</span></span> |<span data-ttu-id="74739-113">Messaggio</span><span class="sxs-lookup"><span data-stu-id="74739-113">Message</span></span> 
:---|:---|:---
<span data-ttu-id="74739-114">BadRequest</span><span class="sxs-lookup"><span data-stu-id="74739-114">BadRequest</span></span> | <span data-ttu-id="74739-115">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="74739-115">BadRequest (400)</span></span> | <span data-ttu-id="74739-116">Messaggio di errore Generale richiesta non valida.</span><span class="sxs-lookup"><span data-stu-id="74739-116">General Bad Request error message.</span></span>
<span data-ttu-id="74739-117">ODataError</span><span class="sxs-lookup"><span data-stu-id="74739-117">ODataError</span></span> | <span data-ttu-id="74739-118">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="74739-118">BadRequest (400)</span></span> | <span data-ttu-id="74739-119">Query URI OData non valida (viene specificato l'errore specifico).</span><span class="sxs-lookup"><span data-stu-id="74739-119">Invalid OData URI query (the specific error is specified).</span></span>
<span data-ttu-id="74739-120">InvalidInput</span><span class="sxs-lookup"><span data-stu-id="74739-120">InvalidInput</span></span> | <span data-ttu-id="74739-121">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="74739-121">BadRequest (400)</span></span> | <span data-ttu-id="74739-122">Input non valido {input non valido}.</span><span class="sxs-lookup"><span data-stu-id="74739-122">Invalid input {the invalid input}.</span></span>
<span data-ttu-id="74739-123">InvalidRequestBody</span><span class="sxs-lookup"><span data-stu-id="74739-123">InvalidRequestBody</span></span> | <span data-ttu-id="74739-124">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="74739-124">BadRequest (400)</span></span> | <span data-ttu-id="74739-125">Corpo della richiesta non valido.</span><span class="sxs-lookup"><span data-stu-id="74739-125">Invalid request body.</span></span>
<span data-ttu-id="74739-126">InvalidHashValue</span><span class="sxs-lookup"><span data-stu-id="74739-126">InvalidHashValue</span></span> | <span data-ttu-id="74739-127">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="74739-127">BadRequest (400)</span></span> | <span data-ttu-id="74739-128">Valore hash {hash non valido} non valido.</span><span class="sxs-lookup"><span data-stu-id="74739-128">Hash value {the invalid hash} is invalid.</span></span>
<span data-ttu-id="74739-129">InvalidDomainName</span><span class="sxs-lookup"><span data-stu-id="74739-129">InvalidDomainName</span></span> | <span data-ttu-id="74739-130">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="74739-130">BadRequest (400)</span></span> | <span data-ttu-id="74739-131">Nome di dominio {dominio non valido} non valido.</span><span class="sxs-lookup"><span data-stu-id="74739-131">Domain name {the invalid domain} is invalid.</span></span>
<span data-ttu-id="74739-132">InvalidIpAddress</span><span class="sxs-lookup"><span data-stu-id="74739-132">InvalidIpAddress</span></span> | <span data-ttu-id="74739-133">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="74739-133">BadRequest (400)</span></span> | <span data-ttu-id="74739-134">L'indirizzo IP {l'IP non valido} non è valido.</span><span class="sxs-lookup"><span data-stu-id="74739-134">IP address {the invalid IP} is invalid.</span></span>
<span data-ttu-id="74739-135">InvalidUrl</span><span class="sxs-lookup"><span data-stu-id="74739-135">InvalidUrl</span></span> | <span data-ttu-id="74739-136">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="74739-136">BadRequest (400)</span></span> | <span data-ttu-id="74739-137">L'URL {l'URL non valido} non è valido.</span><span class="sxs-lookup"><span data-stu-id="74739-137">URL {the invalid URL} is invalid.</span></span>
<span data-ttu-id="74739-138">MaximumBatchSizeExceeded</span><span class="sxs-lookup"><span data-stu-id="74739-138">MaximumBatchSizeExceeded</span></span> | <span data-ttu-id="74739-139">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="74739-139">BadRequest (400)</span></span> | <span data-ttu-id="74739-140">Dimensione massima batch superata.</span><span class="sxs-lookup"><span data-stu-id="74739-140">Maximum batch size exceeded.</span></span> <span data-ttu-id="74739-141">Received: {batch size received}, allowed: {batch size allowed}.</span><span class="sxs-lookup"><span data-stu-id="74739-141">Received: {batch size received}, allowed: {batch size allowed}.</span></span>
<span data-ttu-id="74739-142">MissingRequiredParameter</span><span class="sxs-lookup"><span data-stu-id="74739-142">MissingRequiredParameter</span></span> | <span data-ttu-id="74739-143">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="74739-143">BadRequest (400)</span></span> | <span data-ttu-id="74739-144">Parametro {parametro mancante} mancante.</span><span class="sxs-lookup"><span data-stu-id="74739-144">Parameter {the missing parameter} is missing.</span></span>
<span data-ttu-id="74739-145">OsPlatformNotSupported</span><span class="sxs-lookup"><span data-stu-id="74739-145">OsPlatformNotSupported</span></span> | <span data-ttu-id="74739-146">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="74739-146">BadRequest (400)</span></span> | <span data-ttu-id="74739-147">Piattaforma del sistema operativo {piattaforma del sistema operativo client} non supportata per questa azione.</span><span class="sxs-lookup"><span data-stu-id="74739-147">OS Platform {the client OS Platform} is not supported for this action.</span></span>
<span data-ttu-id="74739-148">ClientVersionNotSupported</span><span class="sxs-lookup"><span data-stu-id="74739-148">ClientVersionNotSupported</span></span> | <span data-ttu-id="74739-149">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="74739-149">BadRequest (400)</span></span> | <span data-ttu-id="74739-150">{L'azione richiesta} è supportata nella versione client {versione client supportata} e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="74739-150">{The requested action} is supported on client version {supported client version} and above.</span></span>
<span data-ttu-id="74739-151">Non autorizzato</span><span class="sxs-lookup"><span data-stu-id="74739-151">Unauthorized</span></span> | <span data-ttu-id="74739-152">Non autorizzato (401)</span><span class="sxs-lookup"><span data-stu-id="74739-152">Unauthorized (401)</span></span> | <span data-ttu-id="74739-153">Non autorizzato (intestazione di autorizzazione non valida o scaduta).</span><span class="sxs-lookup"><span data-stu-id="74739-153">Unauthorized (invalid or expired authorization header).</span></span>
<span data-ttu-id="74739-154">Accesso negato</span><span class="sxs-lookup"><span data-stu-id="74739-154">Forbidden</span></span> | <span data-ttu-id="74739-155">Accesso negato (403)</span><span class="sxs-lookup"><span data-stu-id="74739-155">Forbidden (403)</span></span> | <span data-ttu-id="74739-156">Accesso negato (token valido ma autorizzazione insufficiente per l'azione).</span><span class="sxs-lookup"><span data-stu-id="74739-156">Forbidden (valid token but insufficient permission for the action).</span></span>
<span data-ttu-id="74739-157">DisabledFeature</span><span class="sxs-lookup"><span data-stu-id="74739-157">DisabledFeature</span></span> | <span data-ttu-id="74739-158">Accesso negato (403)</span><span class="sxs-lookup"><span data-stu-id="74739-158">Forbidden (403)</span></span> | <span data-ttu-id="74739-159">La funzionalità tenant non è abilitata.</span><span class="sxs-lookup"><span data-stu-id="74739-159">Tenant feature is not enabled.</span></span>
<span data-ttu-id="74739-160">DisallowedOperation</span><span class="sxs-lookup"><span data-stu-id="74739-160">DisallowedOperation</span></span> | <span data-ttu-id="74739-161">Accesso negato (403)</span><span class="sxs-lookup"><span data-stu-id="74739-161">Forbidden (403)</span></span> | <span data-ttu-id="74739-162">{l'operazione non consentita e il motivo}.</span><span class="sxs-lookup"><span data-stu-id="74739-162">{the disallowed operation and the reason}.</span></span>
<span data-ttu-id="74739-163">NotFound</span><span class="sxs-lookup"><span data-stu-id="74739-163">NotFound</span></span> | <span data-ttu-id="74739-164">Non trovato (404)</span><span class="sxs-lookup"><span data-stu-id="74739-164">Not Found (404)</span></span> | <span data-ttu-id="74739-165">Messaggio di errore Generale non trovato.</span><span class="sxs-lookup"><span data-stu-id="74739-165">General Not Found error message.</span></span>
<span data-ttu-id="74739-166">ResourceNotFound</span><span class="sxs-lookup"><span data-stu-id="74739-166">ResourceNotFound</span></span> | <span data-ttu-id="74739-167">Non trovato (404)</span><span class="sxs-lookup"><span data-stu-id="74739-167">Not Found (404)</span></span> | <span data-ttu-id="74739-168">Impossibile trovare la risorsa {la risorsa richiesta}.</span><span class="sxs-lookup"><span data-stu-id="74739-168">Resource {the requested resource} was not found.</span></span>
<span data-ttu-id="74739-169">InternalServerError</span><span class="sxs-lookup"><span data-stu-id="74739-169">InternalServerError</span></span> | <span data-ttu-id="74739-170">Errore interno del server (500)</span><span class="sxs-lookup"><span data-stu-id="74739-170">Internal Server Error (500)</span></span> | <span data-ttu-id="74739-171">(Nessun messaggio di errore, ritentare l'operazione)</span><span class="sxs-lookup"><span data-stu-id="74739-171">(No error message, retry the operation)</span></span>
<span data-ttu-id="74739-172">TooManyRequests</span><span class="sxs-lookup"><span data-stu-id="74739-172">TooManyRequests</span></span> | <span data-ttu-id="74739-173">Troppe richieste (429)</span><span class="sxs-lookup"><span data-stu-id="74739-173">Too Many Requests (429)</span></span> | <span data-ttu-id="74739-174">La risposta rappresenterà il raggiungimento del limite di quota in base al numero di richieste o alla CPU.</span><span class="sxs-lookup"><span data-stu-id="74739-174">Response will represent reaching quota limit either by number of requests or by CPU.</span></span>

## <a name="body-parameters-are-case-sensitive"></a><span data-ttu-id="74739-175">Per i parametri corpo viene distinzione tra maiuscole e minuscole</span><span class="sxs-lookup"><span data-stu-id="74739-175">Body parameters are case-sensitive</span></span>

<span data-ttu-id="74739-176">Per i parametri del corpo inviato viene attualmente fatto distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="74739-176">The submitted body parameters are currently case-sensitive.</span></span>
<br><span data-ttu-id="74739-177">Se si verifica un **errore InvalidRequestBody** o **MissingRequiredParameter,** potrebbe essere causato da un parametro errato maiuscolo o minuscolo.</span><span class="sxs-lookup"><span data-stu-id="74739-177">If you experience an **InvalidRequestBody** or **MissingRequiredParameter** errors, it might be caused from a wrong parameter capital or lower-case letter.</span></span>
<br><span data-ttu-id="74739-178">Esaminare la pagina della documentazione dell'API e verificare che i parametri inviati corrispondano all'esempio pertinente.</span><span class="sxs-lookup"><span data-stu-id="74739-178">Review the API documentation page and check that the submitted parameters match the relevant example.</span></span>

## <a name="correlation-request-id"></a><span data-ttu-id="74739-179">ID richiesta di correlazione</span><span class="sxs-lookup"><span data-stu-id="74739-179">Correlation request ID</span></span>

<span data-ttu-id="74739-180">Ogni risposta di errore contiene un parametro ID univoco per il rilevamento.</span><span class="sxs-lookup"><span data-stu-id="74739-180">Each error response contains a unique ID parameter for tracking.</span></span>
<br><span data-ttu-id="74739-181">Il nome della proprietà di questo parametro è "target".</span><span class="sxs-lookup"><span data-stu-id="74739-181">The property name of this parameter is "target".</span></span>
<br><span data-ttu-id="74739-182">Quando ci viene contattato per un errore, l'associazione di questo ID consente di individuare la causa radice del problema.</span><span class="sxs-lookup"><span data-stu-id="74739-182">When contacting us about an error, attaching this ID will help find the root cause of the problem.</span></span>

## <a name="examples"></a><span data-ttu-id="74739-183">Esempi</span><span class="sxs-lookup"><span data-stu-id="74739-183">Examples</span></span>

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