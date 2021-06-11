---
title: API annulla azione computer
description: Informazioni su come annullare un'azione del computer già avviata
keywords: api, api del grafico,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 490ee91d5f2d2c02174be94c52fc83fd0ec0fc5e
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879756"
---
#   <a name="cancel-machine-action-api"></a><span data-ttu-id="943fd-104">API annulla azione computer</span><span class="sxs-lookup"><span data-stu-id="943fd-104">Cancel machine action API</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="943fd-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="943fd-105">**Applies to:**</span></span>
- [<span data-ttu-id="943fd-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="943fd-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)

[!include[Prerelease information](../../includes/prerelease.md)]

><span data-ttu-id="943fd-107">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="943fd-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="943fd-108">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="943fd-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="943fd-109">Descrizione API</span><span class="sxs-lookup"><span data-stu-id="943fd-109">API description</span></span>

<span data-ttu-id="943fd-110">Annullare un'azione del computer già avviata che non è ancora in stato finale (completata, annullata, non riuscita).</span><span class="sxs-lookup"><span data-stu-id="943fd-110">Cancel an already launched machine action that are not yet in final state (completed, cancelled, failed).</span></span>

## <a name="limitations"></a><span data-ttu-id="943fd-111">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="943fd-111">Limitations</span></span>

1.  <span data-ttu-id="943fd-112">I limiti di frequenza per questa API sono 100 chiamate al minuto e 1500 chiamate all'ora.</span><span class="sxs-lookup"><span data-stu-id="943fd-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="943fd-113">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="943fd-113">Permissions</span></span>

<span data-ttu-id="943fd-114">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="943fd-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="943fd-115">Per ulteriori informazioni, inclusa la scelta delle autorizzazioni, vedere [Introduzione.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="943fd-115">To learn more, including how to choose permissions, see [Get started](apis-intro.md).</span></span>

|     <span data-ttu-id="943fd-116">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="943fd-116">Permission    type</span></span>     |     <span data-ttu-id="943fd-117">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="943fd-117">Permission</span></span>     |    <span data-ttu-id="943fd-118">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="943fd-118">Permission    display name</span></span>     |
|-|-|-|
|    <br><span data-ttu-id="943fd-119">Applicazione</span><span class="sxs-lookup"><span data-stu-id="943fd-119">Application</span></span>    |    <br><span data-ttu-id="943fd-120">Machine.CollectForensic</span><span class="sxs-lookup"><span data-stu-id="943fd-120">Machine.CollectForensic</span></span><br>   <span data-ttu-id="943fd-121">Machine.Isolate</span><span class="sxs-lookup"><span data-stu-id="943fd-121">Machine.Isolate</span></span>   <br><span data-ttu-id="943fd-122">Machine.RestrictExecution</span><span class="sxs-lookup"><span data-stu-id="943fd-122">Machine.RestrictExecution</span></span><br>   <span data-ttu-id="943fd-123">Machine.Scan</span><span class="sxs-lookup"><span data-stu-id="943fd-123">Machine.Scan</span></span><br>   <span data-ttu-id="943fd-124">Machine.Offboard</span><span class="sxs-lookup"><span data-stu-id="943fd-124">Machine.Offboard</span></span><br>   <span data-ttu-id="943fd-125">Machine.StopAndQuarantine</span><span class="sxs-lookup"><span data-stu-id="943fd-125">Machine.StopAndQuarantine</span></span><br>   <span data-ttu-id="943fd-126">Machine.LiveResponse</span><span class="sxs-lookup"><span data-stu-id="943fd-126">Machine.LiveResponse</span></span>    |    <span data-ttu-id="943fd-127">Raccogliere dati forensi</span><span class="sxs-lookup"><span data-stu-id="943fd-127">Collect   forensics</span></span>   <br><span data-ttu-id="943fd-128">Isola computer</span><span class="sxs-lookup"><span data-stu-id="943fd-128">Isolate   machine</span></span><br><span data-ttu-id="943fd-129">Limitare l'esecuzione del codice</span><span class="sxs-lookup"><span data-stu-id="943fd-129">Restrict   code execution</span></span><br>  <span data-ttu-id="943fd-130">Computer di analisi</span><span class="sxs-lookup"><span data-stu-id="943fd-130">Scan   machine</span></span><br>  <span data-ttu-id="943fd-131">Computer offboard</span><span class="sxs-lookup"><span data-stu-id="943fd-131">Offboard   machine</span></span><br>   <span data-ttu-id="943fd-132">Interrompi e metti in quarantena</span><span class="sxs-lookup"><span data-stu-id="943fd-132">Stop And   Quarantine</span></span><br>   <span data-ttu-id="943fd-133">Eseguire la risposta in tempo reale in un computer specifico</span><span class="sxs-lookup"><span data-stu-id="943fd-133">Run live   response on a specific machine</span></span>    |
|    <br><span data-ttu-id="943fd-134">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="943fd-134">Delegated   (work or school account)</span></span>    |    <span data-ttu-id="943fd-135">Machine.CollectForensic</span><span class="sxs-lookup"><span data-stu-id="943fd-135">Machine.CollectForensic</span></span><br>   <span data-ttu-id="943fd-136">Machine.Isolate</span><span class="sxs-lookup"><span data-stu-id="943fd-136">Machine.Isolate</span></span>    <br><span data-ttu-id="943fd-137">Machine.RestrictExecution</span><span class="sxs-lookup"><span data-stu-id="943fd-137">Machine.RestrictExecution</span></span><br>   <span data-ttu-id="943fd-138">Machine.Scan</span><span class="sxs-lookup"><span data-stu-id="943fd-138">Machine.Scan</span></span><br>   <span data-ttu-id="943fd-139">Machine.Offboard</span><span class="sxs-lookup"><span data-stu-id="943fd-139">Machine.Offboard</span></span><br>   <span data-ttu-id="943fd-140">Machine.StopAndQuarantineMachine.LiveResponse</span><span class="sxs-lookup"><span data-stu-id="943fd-140">Machine.StopAndQuarantineMachine.LiveResponse</span></span>    |    <span data-ttu-id="943fd-141">Raccogliere dati forensi</span><span class="sxs-lookup"><span data-stu-id="943fd-141">Collect   forensics</span></span><br>   <span data-ttu-id="943fd-142">Isola computer</span><span class="sxs-lookup"><span data-stu-id="943fd-142">Isolate   machine</span></span><br>  <span data-ttu-id="943fd-143">Limitare l'esecuzione del codice</span><span class="sxs-lookup"><span data-stu-id="943fd-143">Restrict   code execution</span></span><br> <span data-ttu-id="943fd-144">Computer di analisi</span><span class="sxs-lookup"><span data-stu-id="943fd-144">Scan   machine</span></span><br><span data-ttu-id="943fd-145">Computer offboard</span><span class="sxs-lookup"><span data-stu-id="943fd-145">Offboard   machine</span></span><br> <span data-ttu-id="943fd-146">Interrompi e metti in quarantena</span><span class="sxs-lookup"><span data-stu-id="943fd-146">Stop And   Quarantine</span></span><br> <span data-ttu-id="943fd-147">Eseguire la risposta in tempo reale in un computer specifico</span><span class="sxs-lookup"><span data-stu-id="943fd-147">Run live   response on a specific machine</span></span>    |


## <a name="http-request"></a><span data-ttu-id="943fd-148">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="943fd-148">HTTP request</span></span>

```
POST https://api.securitycenter.microsoft.com/api/machineactions/<machineactionid>/cancel  
```


## <a name="request-headers"></a><span data-ttu-id="943fd-149">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="943fd-149">Request headers</span></span>

| <span data-ttu-id="943fd-150">Name</span><span class="sxs-lookup"><span data-stu-id="943fd-150">Name</span></span>      | <span data-ttu-id="943fd-151">Tipo</span><span class="sxs-lookup"><span data-stu-id="943fd-151">Type</span></span> | <span data-ttu-id="943fd-152">Descrizione</span><span class="sxs-lookup"><span data-stu-id="943fd-152">Description</span></span>                 |
|---------------|----------|---------------------------------|
| <span data-ttu-id="943fd-153">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="943fd-153">Authorization</span></span> | <span data-ttu-id="943fd-154">Stringa</span><span class="sxs-lookup"><span data-stu-id="943fd-154">String</span></span>   | <span data-ttu-id="943fd-155">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="943fd-155">Bearer {token}.</span></span> <span data-ttu-id="943fd-156">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="943fd-156">Required.</span></span>   |
| <span data-ttu-id="943fd-157">Content-Type</span><span class="sxs-lookup"><span data-stu-id="943fd-157">Content-Type</span></span>  | <span data-ttu-id="943fd-158">stringa</span><span class="sxs-lookup"><span data-stu-id="943fd-158">string</span></span>   | <span data-ttu-id="943fd-159">application/json.</span><span class="sxs-lookup"><span data-stu-id="943fd-159">application/json.</span></span> <span data-ttu-id="943fd-160">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="943fd-160">Required.</span></span> |

## <a name="request-body"></a><span data-ttu-id="943fd-161">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="943fd-161">Request body</span></span>

| <span data-ttu-id="943fd-162">Parametro</span><span class="sxs-lookup"><span data-stu-id="943fd-162">Parameter</span></span> | <span data-ttu-id="943fd-163">Tipo</span><span class="sxs-lookup"><span data-stu-id="943fd-163">Type</span></span> | <span data-ttu-id="943fd-164">Descrizione</span><span class="sxs-lookup"><span data-stu-id="943fd-164">Description</span></span>                        |
|---------------|----------|----------------------------------------|
| <span data-ttu-id="943fd-165">Comment</span><span class="sxs-lookup"><span data-stu-id="943fd-165">Comment</span></span>       | <span data-ttu-id="943fd-166">Stringa</span><span class="sxs-lookup"><span data-stu-id="943fd-166">String</span></span>   | <span data-ttu-id="943fd-167">Commento da associare all'azione di annullamento.</span><span class="sxs-lookup"><span data-stu-id="943fd-167">Comment to associate with the cancellation action.</span></span>  |

## <a name="response"></a><span data-ttu-id="943fd-168">Risposta</span><span class="sxs-lookup"><span data-stu-id="943fd-168">Response</span></span>

<span data-ttu-id="943fd-169">Se ha esito positivo, questo metodo restituisce 200 codice di risposta Ok con un'entità Machine Action.</span><span class="sxs-lookup"><span data-stu-id="943fd-169">If successful, this method returns 200, Ok response code with a Machine Action entity.</span></span> <span data-ttu-id="943fd-170">Se l'entità azione del computer con l'ID specificato non è stata trovata - 404 Non trovato.</span><span class="sxs-lookup"><span data-stu-id="943fd-170">If machine action entity with the specified id was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="943fd-171">Esempio</span><span class="sxs-lookup"><span data-stu-id="943fd-171">Example</span></span>

<span data-ttu-id="943fd-172">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="943fd-172">**Request**</span></span>

<span data-ttu-id="943fd-173">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="943fd-173">Here is an example of the request.</span></span>

```HTTP
POST
https://api.securitycenter.microsoft.com/api/machineactions/988cc94e-7a8f-4b28-ab65-54970c5d5018/cancel
```


```JSON
{
    "Comment": "Machine action was canceled by automation"
}
```

## <a name="related-topic"></a><span data-ttu-id="943fd-174">Argomento correlato</span><span class="sxs-lookup"><span data-stu-id="943fd-174">Related topic</span></span>

- [<span data-ttu-id="943fd-175">API per l'azione del computer</span><span class="sxs-lookup"><span data-stu-id="943fd-175">Get machine action API</span></span>](get-machineaction-object.md)