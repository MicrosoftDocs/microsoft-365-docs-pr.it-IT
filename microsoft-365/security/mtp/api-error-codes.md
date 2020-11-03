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
ms.openlocfilehash: aceb376662f2b27397aa2332f8929a57d5a3ee03
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846009"
---
# <a name="common-microsoft-365-defender-rest-api-error-codes"></a><span data-ttu-id="e44c8-104">Codici di errore dell'API REST comuni di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e44c8-104">Common Microsoft 365 Defender REST API error codes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e44c8-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="e44c8-105">**Applies to:**</span></span>
- <span data-ttu-id="e44c8-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e44c8-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT] 
><span data-ttu-id="e44c8-107">Alcune informazioni si riferiscono al prodotto prerilasciato che può essere modificato in modo sostanziale prima che venga rilasciato commercialmente.</span><span class="sxs-lookup"><span data-stu-id="e44c8-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="e44c8-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="e44c8-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="e44c8-109">I codici di errore elencati nella tabella riportata di seguito possono essere restituiti da un'operazione in una qualsiasi delle API di Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="e44c8-109">The error codes listed in the following table may be returned by an operation on any of Microsoft 365 Defender APIs.</span></span>

<span data-ttu-id="e44c8-110">Ogni risposta di errore contiene un messaggio di errore che può contribuire alla risoluzione del problema.</span><span class="sxs-lookup"><span data-stu-id="e44c8-110">Every error response contains an error message, which can help resolving the problem.</span></span>

<span data-ttu-id="e44c8-111">Il messaggio è un testo gratuito che può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="e44c8-111">The message is a free text that can be changed.</span></span>

<span data-ttu-id="e44c8-112">Nella parte inferiore della pagina, è possibile trovare gli esempi di risposta.</span><span class="sxs-lookup"><span data-stu-id="e44c8-112">At the bottom of the page, you can find response examples.</span></span>

<span data-ttu-id="e44c8-113">Codice errore</span><span class="sxs-lookup"><span data-stu-id="e44c8-113">Error code</span></span> |<span data-ttu-id="e44c8-114">Codice di stato HTTP</span><span class="sxs-lookup"><span data-stu-id="e44c8-114">HTTP status code</span></span> |<span data-ttu-id="e44c8-115">Messaggio</span><span class="sxs-lookup"><span data-stu-id="e44c8-115">Message</span></span> 
:---|:---|:---
<span data-ttu-id="e44c8-116">BadRequest</span><span class="sxs-lookup"><span data-stu-id="e44c8-116">BadRequest</span></span> | <span data-ttu-id="e44c8-117">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="e44c8-117">BadRequest (400)</span></span> | <span data-ttu-id="e44c8-118">Messaggio di errore generale di richiesta non valida.</span><span class="sxs-lookup"><span data-stu-id="e44c8-118">General Bad Request error message.</span></span>
<span data-ttu-id="e44c8-119">ODataError</span><span class="sxs-lookup"><span data-stu-id="e44c8-119">ODataError</span></span> | <span data-ttu-id="e44c8-120">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="e44c8-120">BadRequest (400)</span></span> | <span data-ttu-id="e44c8-121">Query URI OData non valida (è specificato l'errore specifico).</span><span class="sxs-lookup"><span data-stu-id="e44c8-121">Invalid OData URI query (the specific error is specified).</span></span>
<span data-ttu-id="e44c8-122">InvalidInput</span><span class="sxs-lookup"><span data-stu-id="e44c8-122">InvalidInput</span></span> | <span data-ttu-id="e44c8-123">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="e44c8-123">BadRequest (400)</span></span> | <span data-ttu-id="e44c8-124">Input non valido {l'input non valido}.</span><span class="sxs-lookup"><span data-stu-id="e44c8-124">Invalid input {the invalid input}.</span></span>
<span data-ttu-id="e44c8-125">InvalidRequestBody</span><span class="sxs-lookup"><span data-stu-id="e44c8-125">InvalidRequestBody</span></span> | <span data-ttu-id="e44c8-126">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="e44c8-126">BadRequest (400)</span></span> | <span data-ttu-id="e44c8-127">Corpo richiesta non valida.</span><span class="sxs-lookup"><span data-stu-id="e44c8-127">Invalid request body.</span></span>
<span data-ttu-id="e44c8-128">InvalidHashValue</span><span class="sxs-lookup"><span data-stu-id="e44c8-128">InvalidHashValue</span></span> | <span data-ttu-id="e44c8-129">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="e44c8-129">BadRequest (400)</span></span> | <span data-ttu-id="e44c8-130">Valore hash {l'hash non valido} non è valido.</span><span class="sxs-lookup"><span data-stu-id="e44c8-130">Hash value {the invalid hash} is invalid.</span></span>
<span data-ttu-id="e44c8-131">InvalidDomainName</span><span class="sxs-lookup"><span data-stu-id="e44c8-131">InvalidDomainName</span></span> | <span data-ttu-id="e44c8-132">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="e44c8-132">BadRequest (400)</span></span> | <span data-ttu-id="e44c8-133">Nome di dominio {il dominio non valido} non è valido.</span><span class="sxs-lookup"><span data-stu-id="e44c8-133">Domain name {the invalid domain} is invalid.</span></span>
<span data-ttu-id="e44c8-134">InvalidIpAddress</span><span class="sxs-lookup"><span data-stu-id="e44c8-134">InvalidIpAddress</span></span> | <span data-ttu-id="e44c8-135">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="e44c8-135">BadRequest (400)</span></span> | <span data-ttu-id="e44c8-136">Indirizzo IP {l'IP non valido} non è valido.</span><span class="sxs-lookup"><span data-stu-id="e44c8-136">IP address {the invalid IP} is invalid.</span></span>
<span data-ttu-id="e44c8-137">InvalidUrl</span><span class="sxs-lookup"><span data-stu-id="e44c8-137">InvalidUrl</span></span> | <span data-ttu-id="e44c8-138">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="e44c8-138">BadRequest (400)</span></span> | <span data-ttu-id="e44c8-139">URL {l'URL non valido} non è valido.</span><span class="sxs-lookup"><span data-stu-id="e44c8-139">URL {the invalid URL} is invalid.</span></span>
<span data-ttu-id="e44c8-140">MaximumBatchSizeExceeded</span><span class="sxs-lookup"><span data-stu-id="e44c8-140">MaximumBatchSizeExceeded</span></span> | <span data-ttu-id="e44c8-141">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="e44c8-141">BadRequest (400)</span></span> | <span data-ttu-id="e44c8-142">Dimensioni massime del batch superate.</span><span class="sxs-lookup"><span data-stu-id="e44c8-142">Maximum batch size exceeded.</span></span> <span data-ttu-id="e44c8-143">Received: {dimensioni batch ricevute}, consentito: {dimensioni batch consentite}.</span><span class="sxs-lookup"><span data-stu-id="e44c8-143">Received: {batch size received}, allowed: {batch size allowed}.</span></span>
<span data-ttu-id="e44c8-144">MissingRequiredParameter</span><span class="sxs-lookup"><span data-stu-id="e44c8-144">MissingRequiredParameter</span></span> | <span data-ttu-id="e44c8-145">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="e44c8-145">BadRequest (400)</span></span> | <span data-ttu-id="e44c8-146">Parametro {il parametro mancante} è mancante.</span><span class="sxs-lookup"><span data-stu-id="e44c8-146">Parameter {the missing parameter} is missing.</span></span>
<span data-ttu-id="e44c8-147">OsPlatformNotSupported</span><span class="sxs-lookup"><span data-stu-id="e44c8-147">OsPlatformNotSupported</span></span> | <span data-ttu-id="e44c8-148">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="e44c8-148">BadRequest (400)</span></span> | <span data-ttu-id="e44c8-149">Piattaforma OS {la piattaforma del sistema operativo client} non è supportata per questa azione.</span><span class="sxs-lookup"><span data-stu-id="e44c8-149">OS Platform {the client OS Platform} is not supported for this action.</span></span>
<span data-ttu-id="e44c8-150">ClientVersionNotSupported</span><span class="sxs-lookup"><span data-stu-id="e44c8-150">ClientVersionNotSupported</span></span> | <span data-ttu-id="e44c8-151">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="e44c8-151">BadRequest (400)</span></span> | <span data-ttu-id="e44c8-152">{L'azione richiesta} è supportata nella versione client {versione client supportata} e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="e44c8-152">{The requested action} is supported on client version {supported client version} and above.</span></span>
<span data-ttu-id="e44c8-153">Non autorizzato</span><span class="sxs-lookup"><span data-stu-id="e44c8-153">Unauthorized</span></span> | <span data-ttu-id="e44c8-154">Non autorizzato (401)</span><span class="sxs-lookup"><span data-stu-id="e44c8-154">Unauthorized (401)</span></span> | <span data-ttu-id="e44c8-155">Non autorizzato (di solito non valido o scaduto l'intestazione di autorizzazione).</span><span class="sxs-lookup"><span data-stu-id="e44c8-155">Unauthorized (usually invalid or expired authorization header).</span></span>
<span data-ttu-id="e44c8-156">Proibito</span><span class="sxs-lookup"><span data-stu-id="e44c8-156">Forbidden</span></span> | <span data-ttu-id="e44c8-157">Forbidden (403)</span><span class="sxs-lookup"><span data-stu-id="e44c8-157">Forbidden (403)</span></span> | <span data-ttu-id="e44c8-158">Forbidden (token valido ma autorizzazione insufficiente per l'azione).</span><span class="sxs-lookup"><span data-stu-id="e44c8-158">Forbidden (valid token but insufficient permission for the action).</span></span>
<span data-ttu-id="e44c8-159">DisabledFeature</span><span class="sxs-lookup"><span data-stu-id="e44c8-159">DisabledFeature</span></span> | <span data-ttu-id="e44c8-160">Forbidden (403)</span><span class="sxs-lookup"><span data-stu-id="e44c8-160">Forbidden (403)</span></span> | <span data-ttu-id="e44c8-161">La caratteristica tenant non è abilitata.</span><span class="sxs-lookup"><span data-stu-id="e44c8-161">Tenant feature is not enabled.</span></span>
<span data-ttu-id="e44c8-162">DisallowedOperation</span><span class="sxs-lookup"><span data-stu-id="e44c8-162">DisallowedOperation</span></span> | <span data-ttu-id="e44c8-163">Forbidden (403)</span><span class="sxs-lookup"><span data-stu-id="e44c8-163">Forbidden (403)</span></span> | <span data-ttu-id="e44c8-164">{l'operazione non consentita e il motivo}.</span><span class="sxs-lookup"><span data-stu-id="e44c8-164">{the disallowed operation and the reason}.</span></span>
<span data-ttu-id="e44c8-165">NotFound</span><span class="sxs-lookup"><span data-stu-id="e44c8-165">NotFound</span></span> | <span data-ttu-id="e44c8-166">Non trovato (404)</span><span class="sxs-lookup"><span data-stu-id="e44c8-166">Not Found (404)</span></span> | <span data-ttu-id="e44c8-167">Messaggio di errore generale non trovato.</span><span class="sxs-lookup"><span data-stu-id="e44c8-167">General Not Found error message.</span></span>
<span data-ttu-id="e44c8-168">ResourceNotFound</span><span class="sxs-lookup"><span data-stu-id="e44c8-168">ResourceNotFound</span></span> | <span data-ttu-id="e44c8-169">Non trovato (404)</span><span class="sxs-lookup"><span data-stu-id="e44c8-169">Not Found (404)</span></span> | <span data-ttu-id="e44c8-170">Risorsa {la risorsa richiesta} non è stata trovata.</span><span class="sxs-lookup"><span data-stu-id="e44c8-170">Resource {the requested resource} was not found.</span></span>
<span data-ttu-id="e44c8-171">InternalServerError</span><span class="sxs-lookup"><span data-stu-id="e44c8-171">InternalServerError</span></span> | <span data-ttu-id="e44c8-172">Errore interno del server (500)</span><span class="sxs-lookup"><span data-stu-id="e44c8-172">Internal Server Error (500)</span></span> | <span data-ttu-id="e44c8-173">(Nessun messaggio di errore, riprova l'operazione o contattaci se non viene risolto)</span><span class="sxs-lookup"><span data-stu-id="e44c8-173">(No error message,  retry the operation or contact us if it does not get resolved)</span></span>

## <a name="body-parameters-are-case-sensitive"></a><span data-ttu-id="e44c8-174">I parametri corpo sono con distinzione tra maiuscole e minuscole</span><span class="sxs-lookup"><span data-stu-id="e44c8-174">Body parameters are case-sensitive</span></span>

<span data-ttu-id="e44c8-175">I parametri del corpo inviati sono attualmente con distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="e44c8-175">The submitted body parameters are currently case-sensitive.</span></span>
<br><span data-ttu-id="e44c8-176">Se si verifica un errore di **InvalidRequestBody** o **MissingRequiredParameter** , potrebbe essere causato da un valore maiuscolo o minuscolo di un parametro errato.</span><span class="sxs-lookup"><span data-stu-id="e44c8-176">If you experience an **InvalidRequestBody** or **MissingRequiredParameter** errors, it might be caused from a wrong parameter capital or lower-case letter.</span></span>
<br><span data-ttu-id="e44c8-177">È consigliabile esaminare la pagina relativa alla documentazione dell'API e verificare che i parametri inviati corrispondano all'esempio pertinente.</span><span class="sxs-lookup"><span data-stu-id="e44c8-177">We recommend that you review the API documentation page and check that the submitted parameters match the relevant example.</span></span>

## <a name="correlation-request-id"></a><span data-ttu-id="e44c8-178">ID richiesta di correlazione</span><span class="sxs-lookup"><span data-stu-id="e44c8-178">Correlation request ID</span></span>

<span data-ttu-id="e44c8-179">Ogni risposta di errore contiene un parametro ID univoco per la verifica.</span><span class="sxs-lookup"><span data-stu-id="e44c8-179">Each error response contains a unique ID parameter for tracking.</span></span>
<br><span data-ttu-id="e44c8-180">Il nome della proprietà di questo parametro è "target".</span><span class="sxs-lookup"><span data-stu-id="e44c8-180">The property name of this parameter is "target".</span></span>
<br><span data-ttu-id="e44c8-181">Quando ci si mette in contatto con informazioni su un errore, l'associazione di questo ID consentirà di individuare la causa principale del problema.</span><span class="sxs-lookup"><span data-stu-id="e44c8-181">When contacting us about an error, attaching this ID will help find the root cause of the problem.</span></span>

## <a name="examples"></a><span data-ttu-id="e44c8-182">Esempi</span><span class="sxs-lookup"><span data-stu-id="e44c8-182">Examples</span></span>

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

