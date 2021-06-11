---
title: Eseguire comandi di risposta in tempo reale in un dispositivo
description: Scopri come eseguire una sequenza di comandi di risposta in tempo reale in un dispositivo.
keywords: api, api del grafico, api supportate, caricamento nella raccolta
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
ms.openlocfilehash: 2a7daf18b1a1d791e7b92ded0a6b839bba1fd4c2
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879701"
---
#  <a name="run-live-response-commands-on-a-device"></a><span data-ttu-id="9373c-104">Eseguire comandi di risposta in tempo reale in un dispositivo</span><span class="sxs-lookup"><span data-stu-id="9373c-104">Run live response commands on a device</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9373c-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="9373c-105">**Applies to:**</span></span>
- [<span data-ttu-id="9373c-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="9373c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)


[!include[Prerelease information](../../includes/prerelease.md)]

><span data-ttu-id="9373c-107">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="9373c-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="9373c-108">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="9373c-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="9373c-109">Descrizione API</span><span class="sxs-lookup"><span data-stu-id="9373c-109">API description</span></span>

<span data-ttu-id="9373c-110">Esegue una sequenza di comandi di risposta in tempo reale in un dispositivo</span><span class="sxs-lookup"><span data-stu-id="9373c-110">Runs a sequence of live response commands on a device</span></span>

## <a name="limitations"></a><span data-ttu-id="9373c-111">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="9373c-111">Limitations</span></span>

1.  <span data-ttu-id="9373c-112">I limiti di frequenza per questa API sono 10 chiamate al minuto (le richieste aggiuntive vengono inviate con HTTP 429).</span><span class="sxs-lookup"><span data-stu-id="9373c-112">Rate limitations for this API are 10 calls per minute (additional requests are responded with HTTP 429).</span></span>

2.  <span data-ttu-id="9373c-113">25 sessioni in esecuzione contemporaneamente (le richieste che superano il limite di limitazione riceveranno una risposta "429 - Troppe richieste").</span><span class="sxs-lookup"><span data-stu-id="9373c-113">25 concurrently running sessions (requests exceeding the throttling limit will receive a "429 - Too many requests" response).</span></span>

3.  <span data-ttu-id="9373c-114">Se il computer non è disponibile, la sessione verrà accodata per un massimo di 3 giorni.</span><span class="sxs-lookup"><span data-stu-id="9373c-114">If the machine is not available, the session will be queued for up to 3 days.</span></span>

4.  <span data-ttu-id="9373c-115">Timeout del comando RunScript dopo 10 minuti.</span><span class="sxs-lookup"><span data-stu-id="9373c-115">RunScript command timeouts after 10 minutes.</span></span>

5.  <span data-ttu-id="9373c-116">Quando un comando di risposta in tempo reale ha esito negativo, tutte le azioni seguite non verranno eseguite.</span><span class="sxs-lookup"><span data-stu-id="9373c-116">When a live response command fails all followed actions will not be executed.</span></span>

## <a name="permissions"></a><span data-ttu-id="9373c-117">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="9373c-117">Permissions</span></span>

<span data-ttu-id="9373c-118">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="9373c-118">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="9373c-119">Per ulteriori informazioni, inclusa la scelta delle autorizzazioni, vedere [Introduzione.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="9373c-119">To learn more, including how to choose permissions, see [Get started](apis-intro.md).</span></span>

| <span data-ttu-id="9373c-120">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="9373c-120">Permission type</span></span>                    | <span data-ttu-id="9373c-121">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="9373c-121">Permission</span></span>           | <span data-ttu-id="9373c-122">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="9373c-122">Permission display name</span></span>                   |
|------------------------------------|----------------------|-------------------------------------------|
| <span data-ttu-id="9373c-123">Applicazione</span><span class="sxs-lookup"><span data-stu-id="9373c-123">Application</span></span>                        | <span data-ttu-id="9373c-124">Machine.LiveResponse</span><span class="sxs-lookup"><span data-stu-id="9373c-124">Machine.LiveResponse</span></span> | <span data-ttu-id="9373c-125">Eseguire la risposta in tempo reale in un computer specifico</span><span class="sxs-lookup"><span data-stu-id="9373c-125">Run live response on a specific machine</span></span> |
| <span data-ttu-id="9373c-126">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="9373c-126">Delegated (work or school account)</span></span> | <span data-ttu-id="9373c-127">Machine.LiveResponse</span><span class="sxs-lookup"><span data-stu-id="9373c-127">Machine.LiveResponse</span></span> | <span data-ttu-id="9373c-128">Eseguire la risposta in tempo reale in un computer specifico</span><span class="sxs-lookup"><span data-stu-id="9373c-128">Run live response on a specific machine</span></span> |

## <a name="http-request"></a><span data-ttu-id="9373c-129">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="9373c-129">HTTP request</span></span>

```HTTP
POST
https://api.securitycenter.microsoft.com/API/machines/{machine_id}/runliveresponse
```

## <a name="request-headers"></a><span data-ttu-id="9373c-130">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="9373c-130">Request headers</span></span>

| <span data-ttu-id="9373c-131">Name</span><span class="sxs-lookup"><span data-stu-id="9373c-131">Name</span></span>      | <span data-ttu-id="9373c-132">Tipo</span><span class="sxs-lookup"><span data-stu-id="9373c-132">Type</span></span> | <span data-ttu-id="9373c-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9373c-133">Description</span></span>                 |
|---------------|----------|---------------------------------|
| <span data-ttu-id="9373c-134">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="9373c-134">Authorization</span></span> | <span data-ttu-id="9373c-135">Stringa</span><span class="sxs-lookup"><span data-stu-id="9373c-135">String</span></span>   | <span data-ttu-id="9373c-136">Bearer\<token>\.</span><span class="sxs-lookup"><span data-stu-id="9373c-136">Bearer\<token>\.</span></span> <span data-ttu-id="9373c-137">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="9373c-137">Required.</span></span>   |
| <span data-ttu-id="9373c-138">Content-Type</span><span class="sxs-lookup"><span data-stu-id="9373c-138">Content-Type</span></span>  | <span data-ttu-id="9373c-139">stringa</span><span class="sxs-lookup"><span data-stu-id="9373c-139">string</span></span>   | <span data-ttu-id="9373c-140">application/json.</span><span class="sxs-lookup"><span data-stu-id="9373c-140">application/json.</span></span> <span data-ttu-id="9373c-141">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="9373c-141">Required.</span></span> |

## <a name="request-body"></a><span data-ttu-id="9373c-142">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="9373c-142">Request body</span></span>

| <span data-ttu-id="9373c-143">Parametro</span><span class="sxs-lookup"><span data-stu-id="9373c-143">Parameter</span></span> | <span data-ttu-id="9373c-144">Tipo</span><span class="sxs-lookup"><span data-stu-id="9373c-144">Type</span></span> | <span data-ttu-id="9373c-145">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9373c-145">Description</span></span>                                                        |
|---------------|----------|------------------------------------------------------------------------|
| <span data-ttu-id="9373c-146">Comment</span><span class="sxs-lookup"><span data-stu-id="9373c-146">Comment</span></span>       | <span data-ttu-id="9373c-147">Stringa</span><span class="sxs-lookup"><span data-stu-id="9373c-147">String</span></span>   | <span data-ttu-id="9373c-148">Commento da associare all'azione.</span><span class="sxs-lookup"><span data-stu-id="9373c-148">Comment to associate with the action.</span></span>                                 |
| <span data-ttu-id="9373c-149">Comandi</span><span class="sxs-lookup"><span data-stu-id="9373c-149">Commands</span></span>      | <span data-ttu-id="9373c-150">Array</span><span class="sxs-lookup"><span data-stu-id="9373c-150">Array</span></span>    | <span data-ttu-id="9373c-151">Comandi da eseguire.</span><span class="sxs-lookup"><span data-stu-id="9373c-151">Commands to run.</span></span> <span data-ttu-id="9373c-152">I valori consentiti sono PutFile, RunScript, GetFile.</span><span class="sxs-lookup"><span data-stu-id="9373c-152">Allowed values are PutFile, RunScript, GetFile.</span></span> |

<span data-ttu-id="9373c-153">Comandi:</span><span class="sxs-lookup"><span data-stu-id="9373c-153">Commands:</span></span>

| <span data-ttu-id="9373c-154">Tipo di comando</span><span class="sxs-lookup"><span data-stu-id="9373c-154">Command Type</span></span> | <span data-ttu-id="9373c-155">Parametri</span><span class="sxs-lookup"><span data-stu-id="9373c-155">Parameters</span></span>                                                                          | <span data-ttu-id="9373c-156">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9373c-156">Description</span></span>                                                                                                                      |
|------------------|-----------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="9373c-157">PutFile</span><span class="sxs-lookup"><span data-stu-id="9373c-157">PutFile</span></span>      | <span data-ttu-id="9373c-158">Chiave: FileName</span><span class="sxs-lookup"><span data-stu-id="9373c-158">Key: FileName</span></span>  <br><br>  <span data-ttu-id="9373c-159">Valore: \<file name\></span><span class="sxs-lookup"><span data-stu-id="9373c-159">Value: \<file name\></span></span>                                                                          | <span data-ttu-id="9373c-160">Inserisce un file dalla raccolta al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9373c-160">Puts a file from the library to the device.</span></span> <span data-ttu-id="9373c-161">I file vengono salvati in una cartella di lavoro e vengono eliminati al riavvio del dispositivo per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="9373c-161">Files are saved in a working folder and are deleted when the device restarts by default.</span></span>
| <span data-ttu-id="9373c-162">RunScript</span><span class="sxs-lookup"><span data-stu-id="9373c-162">RunScript</span></span>    | <span data-ttu-id="9373c-163">Chiave: ScriptName</span><span class="sxs-lookup"><span data-stu-id="9373c-163">Key: ScriptName</span></span><br><span data-ttu-id="9373c-164">Valore: \<Script from library\></span><span class="sxs-lookup"><span data-stu-id="9373c-164">Value: \<Script from library\></span></span> <br><br> <span data-ttu-id="9373c-165">Key: Args</span><span class="sxs-lookup"><span data-stu-id="9373c-165">Key: Args</span></span>  <br> <span data-ttu-id="9373c-166">Valore: \<Script arguments\></span><span class="sxs-lookup"><span data-stu-id="9373c-166">Value: \<Script arguments\></span></span>                          | <span data-ttu-id="9373c-167">Esegue uno script dalla raccolta in un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9373c-167">Runs a script from the library on a device.</span></span>    <br><br>  <span data-ttu-id="9373c-168">Il parametro Args viene passato allo script.</span><span class="sxs-lookup"><span data-stu-id="9373c-168">The Args parameter is passed to your script.</span></span> <br><br> <span data-ttu-id="9373c-169">Timeout dopo 10 minuti.</span><span class="sxs-lookup"><span data-stu-id="9373c-169">Timeouts after 10 minutes.</span></span>     
| <span data-ttu-id="9373c-170">GetFile</span><span class="sxs-lookup"><span data-stu-id="9373c-170">GetFile</span></span>      | <span data-ttu-id="9373c-171">Chiave: Path</span><span class="sxs-lookup"><span data-stu-id="9373c-171">Key: Path</span></span> <br> <span data-ttu-id="9373c-172">Valore: \<File path\></span><span class="sxs-lookup"><span data-stu-id="9373c-172">Value: \<File path\></span></span>                                                        | <span data-ttu-id="9373c-173">Raccogliere file da un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9373c-173">Collect file from a device.</span></span> <span data-ttu-id="9373c-174">NOTA: le barre rovesciate nel percorso devono essere precedute da caratteri di escape.</span><span class="sxs-lookup"><span data-stu-id="9373c-174">NOTE: Backslashes in path must be escaped.</span></span>                                                                      |

## <a name="response"></a><span data-ttu-id="9373c-175">Risposta</span><span class="sxs-lookup"><span data-stu-id="9373c-175">Response</span></span>

-   <span data-ttu-id="9373c-176">Se ha esito positivo, questo metodo restituisce 200, Ok.</span><span class="sxs-lookup"><span data-stu-id="9373c-176">If successful, this method returns 200, Ok.</span></span>
    <span data-ttu-id="9373c-177">Entità Azione.</span><span class="sxs-lookup"><span data-stu-id="9373c-177">Action entity.</span></span> <span data-ttu-id="9373c-178">Se il computer con l'ID specificato non è stato trovato - 404 Non trovato.</span><span class="sxs-lookup"><span data-stu-id="9373c-178">If machine with the specified ID was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="9373c-179">Esempio</span><span class="sxs-lookup"><span data-stu-id="9373c-179">Example</span></span>

<span data-ttu-id="9373c-180">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="9373c-180">**Request**</span></span>

<span data-ttu-id="9373c-181">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="9373c-181">Here is an example of the request.</span></span>

```HTTP

POST
https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/runliveresponse

```
<span data-ttu-id="9373c-182">**JSON**</span><span class="sxs-lookup"><span data-stu-id="9373c-182">**JSON**</span></span>

```JSON
{
   "Commands":[
      {
         "type":"RunScript",
         "params":[
            {
               "key":"ScriptName",
               "value":"minidump.ps1"
            },
            {
               "key":"Args",
               "value":"OfficeClickToRun"
            }

         ]
      },
      {
         "type":"GetFile",
         "params":[
            {
               "key":"Path",
               "value":"C:\\windows\\TEMP\\OfficeClickToRun.dmp.zip"
            }
         ]
      }
   ],
   "Comment":"Testing Live Response API"
}
```

<span data-ttu-id="9373c-183">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="9373c-183">**Response**</span></span>

<span data-ttu-id="9373c-184">Ecco un esempio di risposta.</span><span class="sxs-lookup"><span data-stu-id="9373c-184">Here is an example of the response.</span></span>

```HTTP
HTTP/1.1 200 Ok
```

<span data-ttu-id="9373c-185">Content-type: application/json</span><span class="sxs-lookup"><span data-stu-id="9373c-185">Content-type: application/json</span></span>

```JSON
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineActions/$entity",
    "id": "{machine_action_id}",
    "type": "LiveResponse",
    "requestor": "analyst@microsoft.com",
    "requestorComment": "Testing Live Response API",
    "status": "Pending",
    "machineId": "{machine_id}",
    "computerDnsName": "hostname",
    "creationDateTimeUtc": "2021-02-04T15:36:52.7788848Z",
    "lastUpdateDateTimeUtc": "2021-02-04T15:36:52.7788848Z",
    "errorHResult": 0,
    "commands": [
        {
            "index": 0,
            "startTime": null,
            "endTime": null,
            "commandStatus": "Created",
            "errors": [],
            "command": {
                "type": "RunScript",
                "params": [
                    {
                        "key": "ScriptName",
                        "value": "minidump.ps1"
                    },{
                        "key": "Args",
                        "value": "OfficeClickToRun"
                    }
                ]
            }
        }, {
            "index": 1,
            "startTime": null,
            "endTime": null,
            "commandStatus": "Created",
            "errors": [],
            "command": {
                "type": "GetFile",
                "params": [{
                        "key": "Path", "value": "C:\\windows\\TEMP\\OfficeClickToRun.dmp.zip"
                    }
                ]
            }
        }
    ]
}


```

## <a name="related-topics"></a><span data-ttu-id="9373c-186">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="9373c-186">Related topics</span></span>
- [<span data-ttu-id="9373c-187">API per l'azione del computer</span><span class="sxs-lookup"><span data-stu-id="9373c-187">Get machine action API</span></span>](get-machineaction-object.md)
- [<span data-ttu-id="9373c-188">Ottenere il risultato della risposta in tempo reale</span><span class="sxs-lookup"><span data-stu-id="9373c-188">Get live response result</span></span>](get-live-response-result.md)
- [<span data-ttu-id="9373c-189">Annullare l'azione del computer</span><span class="sxs-lookup"><span data-stu-id="9373c-189">Cancel machine action</span></span>](cancel-machine-action.md)
