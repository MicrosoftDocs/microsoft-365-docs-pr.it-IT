---
title: Codici di errore comuni di Microsoft Threat Protection REST API
description: Informazioni sui codici di errore dell'API REST comuni di Microsoft Threat Protection
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
ms.openlocfilehash: 36a1cedacc5f16c422e2b0d458b0d1767cf08b64
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650377"
---
# <a name="common-microsoft-threat-protection-rest-api-error-codes"></a><span data-ttu-id="34556-104">Codici di errore comuni di Microsoft Threat Protection REST API</span><span class="sxs-lookup"><span data-stu-id="34556-104">Common Microsoft Threat Protection REST API error codes</span></span>

<span data-ttu-id="34556-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="34556-105">**Applies to:**</span></span>
- <span data-ttu-id="34556-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="34556-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="34556-107">Alcune informazioni si riferiscono al prodotto prerilasciato che può essere modificato in modo sostanziale prima che venga rilasciato commercialmente.</span><span class="sxs-lookup"><span data-stu-id="34556-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="34556-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="34556-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="34556-109">I codici di errore elencati nella tabella riportata di seguito possono essere restituiti da un'operazione in una qualsiasi delle API di Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="34556-109">The error codes listed in the following table may be returned by an operation on any of Microsoft Threat Protection APIs.</span></span>

<span data-ttu-id="34556-110">Ogni risposta di errore contiene un messaggio di errore che può contribuire alla risoluzione del problema.</span><span class="sxs-lookup"><span data-stu-id="34556-110">Every error response contains an error message, which can help resolving the problem.</span></span>

<span data-ttu-id="34556-111">Il messaggio è un testo gratuito che può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="34556-111">The message is a free text that can be changed.</span></span>

<span data-ttu-id="34556-112">Nella parte inferiore della pagina, è possibile trovare gli esempi di risposta.</span><span class="sxs-lookup"><span data-stu-id="34556-112">At the bottom of the page, you can find response examples.</span></span>

<span data-ttu-id="34556-113">Codice errore</span><span class="sxs-lookup"><span data-stu-id="34556-113">Error code</span></span> |<span data-ttu-id="34556-114">Codice di stato HTTP</span><span class="sxs-lookup"><span data-stu-id="34556-114">HTTP status code</span></span> |<span data-ttu-id="34556-115">Messaggio</span><span class="sxs-lookup"><span data-stu-id="34556-115">Message</span></span> 
:---|:---|:---
<span data-ttu-id="34556-116">BadRequest</span><span class="sxs-lookup"><span data-stu-id="34556-116">BadRequest</span></span> | <span data-ttu-id="34556-117">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="34556-117">BadRequest (400)</span></span> | <span data-ttu-id="34556-118">Messaggio di errore generale di richiesta non valida.</span><span class="sxs-lookup"><span data-stu-id="34556-118">General Bad Request error message.</span></span>
<span data-ttu-id="34556-119">ODataError</span><span class="sxs-lookup"><span data-stu-id="34556-119">ODataError</span></span> | <span data-ttu-id="34556-120">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="34556-120">BadRequest (400)</span></span> | <span data-ttu-id="34556-121">Query URI OData non valida (è specificato l'errore specifico).</span><span class="sxs-lookup"><span data-stu-id="34556-121">Invalid OData URI query (the specific error is specified).</span></span>
<span data-ttu-id="34556-122">InvalidInput</span><span class="sxs-lookup"><span data-stu-id="34556-122">InvalidInput</span></span> | <span data-ttu-id="34556-123">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="34556-123">BadRequest (400)</span></span> | <span data-ttu-id="34556-124">Input non valido {l'input non valido}.</span><span class="sxs-lookup"><span data-stu-id="34556-124">Invalid input {the invalid input}.</span></span>
<span data-ttu-id="34556-125">InvalidRequestBody</span><span class="sxs-lookup"><span data-stu-id="34556-125">InvalidRequestBody</span></span> | <span data-ttu-id="34556-126">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="34556-126">BadRequest (400)</span></span> | <span data-ttu-id="34556-127">Corpo richiesta non valida.</span><span class="sxs-lookup"><span data-stu-id="34556-127">Invalid request body.</span></span>
<span data-ttu-id="34556-128">InvalidHashValue</span><span class="sxs-lookup"><span data-stu-id="34556-128">InvalidHashValue</span></span> | <span data-ttu-id="34556-129">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="34556-129">BadRequest (400)</span></span> | <span data-ttu-id="34556-130">Valore hash {l'hash non valido} non è valido.</span><span class="sxs-lookup"><span data-stu-id="34556-130">Hash value {the invalid hash} is invalid.</span></span>
<span data-ttu-id="34556-131">InvalidDomainName</span><span class="sxs-lookup"><span data-stu-id="34556-131">InvalidDomainName</span></span> | <span data-ttu-id="34556-132">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="34556-132">BadRequest (400)</span></span> | <span data-ttu-id="34556-133">Nome di dominio {il dominio non valido} non è valido.</span><span class="sxs-lookup"><span data-stu-id="34556-133">Domain name {the invalid domain} is invalid.</span></span>
<span data-ttu-id="34556-134">InvalidIpAddress</span><span class="sxs-lookup"><span data-stu-id="34556-134">InvalidIpAddress</span></span> | <span data-ttu-id="34556-135">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="34556-135">BadRequest (400)</span></span> | <span data-ttu-id="34556-136">Indirizzo IP {l'IP non valido} non è valido.</span><span class="sxs-lookup"><span data-stu-id="34556-136">IP address {the invalid IP} is invalid.</span></span>
<span data-ttu-id="34556-137">InvalidUrl</span><span class="sxs-lookup"><span data-stu-id="34556-137">InvalidUrl</span></span> | <span data-ttu-id="34556-138">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="34556-138">BadRequest (400)</span></span> | <span data-ttu-id="34556-139">URL {l'URL non valido} non è valido.</span><span class="sxs-lookup"><span data-stu-id="34556-139">URL {the invalid URL} is invalid.</span></span>
<span data-ttu-id="34556-140">MaximumBatchSizeExceeded</span><span class="sxs-lookup"><span data-stu-id="34556-140">MaximumBatchSizeExceeded</span></span> | <span data-ttu-id="34556-141">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="34556-141">BadRequest (400)</span></span> | <span data-ttu-id="34556-142">Dimensioni massime del batch superate.</span><span class="sxs-lookup"><span data-stu-id="34556-142">Maximum batch size exceeded.</span></span> <span data-ttu-id="34556-143">Received: {dimensioni batch ricevute}, consentito: {dimensioni batch consentite}.</span><span class="sxs-lookup"><span data-stu-id="34556-143">Received: {batch size received}, allowed: {batch size allowed}.</span></span>
<span data-ttu-id="34556-144">MissingRequiredParameter</span><span class="sxs-lookup"><span data-stu-id="34556-144">MissingRequiredParameter</span></span> | <span data-ttu-id="34556-145">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="34556-145">BadRequest (400)</span></span> | <span data-ttu-id="34556-146">Parametro {il parametro mancante} è mancante.</span><span class="sxs-lookup"><span data-stu-id="34556-146">Parameter {the missing parameter} is missing.</span></span>
<span data-ttu-id="34556-147">OsPlatformNotSupported</span><span class="sxs-lookup"><span data-stu-id="34556-147">OsPlatformNotSupported</span></span> | <span data-ttu-id="34556-148">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="34556-148">BadRequest (400)</span></span> | <span data-ttu-id="34556-149">Piattaforma OS {la piattaforma del sistema operativo client} non è supportata per questa azione.</span><span class="sxs-lookup"><span data-stu-id="34556-149">OS Platform {the client OS Platform} is not supported for this action.</span></span>
<span data-ttu-id="34556-150">ClientVersionNotSupported</span><span class="sxs-lookup"><span data-stu-id="34556-150">ClientVersionNotSupported</span></span> | <span data-ttu-id="34556-151">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="34556-151">BadRequest (400)</span></span> | <span data-ttu-id="34556-152">{L'azione richiesta} è supportata nella versione client {versione client supportata} e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="34556-152">{The requested action} is supported on client version {supported client version} and above.</span></span>
<span data-ttu-id="34556-153">Non autorizzato</span><span class="sxs-lookup"><span data-stu-id="34556-153">Unauthorized</span></span> | <span data-ttu-id="34556-154">Non autorizzato (401)</span><span class="sxs-lookup"><span data-stu-id="34556-154">Unauthorized (401)</span></span> | <span data-ttu-id="34556-155">Non autorizzato (di solito non valido o scaduto l'intestazione di autorizzazione).</span><span class="sxs-lookup"><span data-stu-id="34556-155">Unauthorized (usually invalid or expired authorization header).</span></span>
<span data-ttu-id="34556-156">Proibito</span><span class="sxs-lookup"><span data-stu-id="34556-156">Forbidden</span></span> | <span data-ttu-id="34556-157">Forbidden (403)</span><span class="sxs-lookup"><span data-stu-id="34556-157">Forbidden (403)</span></span> | <span data-ttu-id="34556-158">Forbidden (token valido ma autorizzazione insufficiente per l'azione).</span><span class="sxs-lookup"><span data-stu-id="34556-158">Forbidden (valid token but insufficient permission for the action).</span></span>
<span data-ttu-id="34556-159">DisabledFeature</span><span class="sxs-lookup"><span data-stu-id="34556-159">DisabledFeature</span></span> | <span data-ttu-id="34556-160">Forbidden (403)</span><span class="sxs-lookup"><span data-stu-id="34556-160">Forbidden (403)</span></span> | <span data-ttu-id="34556-161">La caratteristica tenant non è abilitata.</span><span class="sxs-lookup"><span data-stu-id="34556-161">Tenant feature is not enabled.</span></span>
<span data-ttu-id="34556-162">DisallowedOperation</span><span class="sxs-lookup"><span data-stu-id="34556-162">DisallowedOperation</span></span> | <span data-ttu-id="34556-163">Forbidden (403)</span><span class="sxs-lookup"><span data-stu-id="34556-163">Forbidden (403)</span></span> | <span data-ttu-id="34556-164">{l'operazione non consentita e il motivo}.</span><span class="sxs-lookup"><span data-stu-id="34556-164">{the disallowed operation and the reason}.</span></span>
<span data-ttu-id="34556-165">NotFound</span><span class="sxs-lookup"><span data-stu-id="34556-165">NotFound</span></span> | <span data-ttu-id="34556-166">Non trovato (404)</span><span class="sxs-lookup"><span data-stu-id="34556-166">Not Found (404)</span></span> | <span data-ttu-id="34556-167">Messaggio di errore generale non trovato.</span><span class="sxs-lookup"><span data-stu-id="34556-167">General Not Found error message.</span></span>
<span data-ttu-id="34556-168">ResourceNotFound</span><span class="sxs-lookup"><span data-stu-id="34556-168">ResourceNotFound</span></span> | <span data-ttu-id="34556-169">Non trovato (404)</span><span class="sxs-lookup"><span data-stu-id="34556-169">Not Found (404)</span></span> | <span data-ttu-id="34556-170">Risorsa {la risorsa richiesta} non è stata trovata.</span><span class="sxs-lookup"><span data-stu-id="34556-170">Resource {the requested resource} was not found.</span></span>
<span data-ttu-id="34556-171">InternalServerError</span><span class="sxs-lookup"><span data-stu-id="34556-171">InternalServerError</span></span> | <span data-ttu-id="34556-172">Errore interno del server (500)</span><span class="sxs-lookup"><span data-stu-id="34556-172">Internal Server Error (500)</span></span> | <span data-ttu-id="34556-173">(Nessun messaggio di errore, riprova l'operazione o contattaci se non viene risolto)</span><span class="sxs-lookup"><span data-stu-id="34556-173">(No error message,  retry the operation or contact us if it does not get resolved)</span></span>

## <a name="body-parameters-are-case-sensitive"></a><span data-ttu-id="34556-174">I parametri corpo sono con distinzione tra maiuscole e minuscole</span><span class="sxs-lookup"><span data-stu-id="34556-174">Body parameters are case-sensitive</span></span>

<span data-ttu-id="34556-175">I parametri del corpo inviati sono attualmente con distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="34556-175">The submitted body parameters are currently case-sensitive.</span></span>
<br><span data-ttu-id="34556-176">Se si verifica un errore di **InvalidRequestBody** o **MissingRequiredParameter** , potrebbe essere causato da un valore maiuscolo o minuscolo di un parametro errato.</span><span class="sxs-lookup"><span data-stu-id="34556-176">If you experience an **InvalidRequestBody** or **MissingRequiredParameter** errors, it might be caused from a wrong parameter capital or lower-case letter.</span></span>
<br><span data-ttu-id="34556-177">È consigliabile esaminare la pagina relativa alla documentazione dell'API e verificare che i parametri inviati corrispondano all'esempio pertinente.</span><span class="sxs-lookup"><span data-stu-id="34556-177">We recommend that you review the API documentation page and check that the submitted parameters match the relevant example.</span></span>

## <a name="correlation-request-id"></a><span data-ttu-id="34556-178">ID richiesta di correlazione</span><span class="sxs-lookup"><span data-stu-id="34556-178">Correlation request ID</span></span>

<span data-ttu-id="34556-179">Ogni risposta di errore contiene un parametro ID univoco per la verifica.</span><span class="sxs-lookup"><span data-stu-id="34556-179">Each error response contains a unique ID parameter for tracking.</span></span>
<br><span data-ttu-id="34556-180">Il nome della proprietà di questo parametro è "target".</span><span class="sxs-lookup"><span data-stu-id="34556-180">The property name of this parameter is "target".</span></span>
<br><span data-ttu-id="34556-181">Quando ci si mette in contatto con informazioni su un errore, l'associazione di questo ID consentirà di individuare la causa principale del problema.</span><span class="sxs-lookup"><span data-stu-id="34556-181">When contacting us about an error, attaching this ID will help find the root cause of the problem.</span></span>

## <a name="examples"></a><span data-ttu-id="34556-182">Esempi</span><span class="sxs-lookup"><span data-stu-id="34556-182">Examples</span></span>

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

