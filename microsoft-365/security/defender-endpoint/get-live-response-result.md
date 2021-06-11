---
title: Ottenere risultati di risposta in tempo reale
description: Informazioni su come recuperare un risultato del comando di risposta in tempo reale specifico in base al relativo indice.
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
ms.openlocfilehash: d58fc87d16bb58199c95933d85752008a08a0e81
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879731"
---
#  <a name="get-live-response-results"></a><span data-ttu-id="edb76-104">Ottenere risultati di risposta in tempo reale</span><span class="sxs-lookup"><span data-stu-id="edb76-104">Get live response results</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="edb76-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="edb76-105">**Applies to:**</span></span>
- [<span data-ttu-id="edb76-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="edb76-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)

[!include[Prerelease information](../../includes/prerelease.md)]

><span data-ttu-id="edb76-107">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="edb76-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="edb76-108">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="edb76-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="edb76-109">Descrizione API</span><span class="sxs-lookup"><span data-stu-id="edb76-109">API description</span></span>

<span data-ttu-id="edb76-110">Recupera un risultato del comando di risposta in tempo reale specifico in base al relativo indice.</span><span class="sxs-lookup"><span data-stu-id="edb76-110">Retrieves a specific live response command result by its index.</span></span>

## <a name="limitations"></a><span data-ttu-id="edb76-111">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="edb76-111">Limitations</span></span>

1.  <span data-ttu-id="edb76-112">I limiti di frequenza per questa API sono 100 chiamate al minuto e 1500 chiamate all'ora.</span><span class="sxs-lookup"><span data-stu-id="edb76-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="edb76-113">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="edb76-113">Permissions</span></span>

<span data-ttu-id="edb76-114">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="edb76-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="edb76-115">Per ulteriori informazioni, inclusa la scelta delle autorizzazioni, vedere [Introduzione.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="edb76-115">To learn more, including how to choose permissions, see [Get started](apis-intro.md).</span></span>

| <span data-ttu-id="edb76-116">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="edb76-116">Permission type</span></span>                    | <span data-ttu-id="edb76-117">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="edb76-117">Permission</span></span>           | <span data-ttu-id="edb76-118">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="edb76-118">Permission display name</span></span>                   |
|------------------------------------|----------------------|-------------------------------------------|
| <span data-ttu-id="edb76-119">Applicazione</span><span class="sxs-lookup"><span data-stu-id="edb76-119">Application</span></span>                        | <span data-ttu-id="edb76-120">Machine.LiveResponse</span><span class="sxs-lookup"><span data-stu-id="edb76-120">Machine.LiveResponse</span></span> | <span data-ttu-id="edb76-121">Eseguire la risposta in tempo reale in un computer specifico</span><span class="sxs-lookup"><span data-stu-id="edb76-121">Run live response on a specific machine</span></span> |
| <span data-ttu-id="edb76-122">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="edb76-122">Delegated (work or school account)</span></span> | <span data-ttu-id="edb76-123">Machine.LiveResponse</span><span class="sxs-lookup"><span data-stu-id="edb76-123">Machine.LiveResponse</span></span> | <span data-ttu-id="edb76-124">Eseguire la risposta in tempo reale in un computer specifico</span><span class="sxs-lookup"><span data-stu-id="edb76-124">Run live response on a specific machine</span></span> |

## <a name="http-request"></a><span data-ttu-id="edb76-125">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="edb76-125">HTTP request</span></span>

```HTTP
GET https://api.securitycenter.microsoft.com/api/machineactions/{machine action
id}/GetLiveResponseResultDownloadLink(index={command-index})
```

## <a name="request-headers"></a><span data-ttu-id="edb76-126">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="edb76-126">Request headers</span></span>

| <span data-ttu-id="edb76-127">Name</span><span class="sxs-lookup"><span data-stu-id="edb76-127">Name</span></span>      | <span data-ttu-id="edb76-128">Tipo</span><span class="sxs-lookup"><span data-stu-id="edb76-128">Type</span></span> | <span data-ttu-id="edb76-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="edb76-129">Description</span></span>               |
|---------------|----------|-------------------------------|
| <span data-ttu-id="edb76-130">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="edb76-130">Authorization</span></span> | <span data-ttu-id="edb76-131">Stringa</span><span class="sxs-lookup"><span data-stu-id="edb76-131">String</span></span>   | <span data-ttu-id="edb76-132">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="edb76-132">Bearer {token}.</span></span> <span data-ttu-id="edb76-133">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="edb76-133">Required.</span></span> |

## <a name="request-body"></a><span data-ttu-id="edb76-134">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="edb76-134">Request body</span></span>

<span data-ttu-id="edb76-135">Vuoto</span><span class="sxs-lookup"><span data-stu-id="edb76-135">Empty</span></span>

## <a name="response"></a><span data-ttu-id="edb76-136">Risposta</span><span class="sxs-lookup"><span data-stu-id="edb76-136">Response</span></span>

<span data-ttu-id="edb76-137">Se ha esito positivo, questo metodo restituisce il codice di risposta 200 Ok con l'oggetto che contiene il collegamento al comando che restituisce la *proprietà value.*</span><span class="sxs-lookup"><span data-stu-id="edb76-137">If successful, this method returns 200, Ok response code with object that holds the link to the command result in the *value* property.</span></span> <span data-ttu-id="edb76-138">Questo collegamento è valido per 30 minuti e deve essere usato immediatamente per scaricare il pacchetto in un archivio locale.</span><span class="sxs-lookup"><span data-stu-id="edb76-138">This link is valid for 30 minutes and should be used immediately for downloading the package to a local storage.</span></span> <span data-ttu-id="edb76-139">Un collegamento scaduto può essere ri-creato da un'altra chiamata e non è necessario eseguire di nuovo la risposta in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="edb76-139">An expired link can be re-created by another call, and there is no need to run live response again.</span></span>

<span data-ttu-id="edb76-140">*Proprietà trascrizione Runscript:*</span><span class="sxs-lookup"><span data-stu-id="edb76-140">*Runscript transcript properties:*</span></span>

| <span data-ttu-id="edb76-141">Proprietà</span><span class="sxs-lookup"><span data-stu-id="edb76-141">Property</span></span>  | <span data-ttu-id="edb76-142">Descrizione</span><span class="sxs-lookup"><span data-stu-id="edb76-142">Description</span></span>                       |
|---------------|---------------------------------------|
| <span data-ttu-id="edb76-143">name</span><span class="sxs-lookup"><span data-stu-id="edb76-143">name</span></span>          | <span data-ttu-id="edb76-144">Nome script eseguito</span><span class="sxs-lookup"><span data-stu-id="edb76-144">Executed script name</span></span>                  |
| <span data-ttu-id="edb76-145">exit_code</span><span class="sxs-lookup"><span data-stu-id="edb76-145">exit_code</span></span>     | <span data-ttu-id="edb76-146">Codice di uscita script eseguito</span><span class="sxs-lookup"><span data-stu-id="edb76-146">Executed script exit code</span></span>             |
| <span data-ttu-id="edb76-147">script_output</span><span class="sxs-lookup"><span data-stu-id="edb76-147">script_output</span></span> | <span data-ttu-id="edb76-148">Output standard dello script eseguito</span><span class="sxs-lookup"><span data-stu-id="edb76-148">Executed script standard output</span></span>       |
| <span data-ttu-id="edb76-149">script_error</span><span class="sxs-lookup"><span data-stu-id="edb76-149">script_error</span></span>  | <span data-ttu-id="edb76-150">Output degli errori standard dello script eseguito</span><span class="sxs-lookup"><span data-stu-id="edb76-150">Executed script standard error output</span></span> |

## <a name="example"></a><span data-ttu-id="edb76-151">Esempio</span><span class="sxs-lookup"><span data-stu-id="edb76-151">Example</span></span>

<span data-ttu-id="edb76-152">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="edb76-152">**Request**</span></span>

<span data-ttu-id="edb76-153">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="edb76-153">Here is an example of the request.</span></span>

```HTTP
GET
https://api.securitycenter.microsoft.com/api/machineactions/988cc94e-7a8f-4b28-ab65-54970c5d5018/GetLiveResponseResultDownloadLink(index=0)
```

<span data-ttu-id="edb76-154">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="edb76-154">**Response**</span></span>

<span data-ttu-id="edb76-155">Ecco un esempio di risposta.</span><span class="sxs-lookup"><span data-stu-id="edb76-155">Here is an example of the response.</span></span>

<span data-ttu-id="edb76-156">HTTP/1.1 200 Ok</span><span class="sxs-lookup"><span data-stu-id="edb76-156">HTTP/1.1 200 Ok</span></span>

<span data-ttu-id="edb76-157">Content-type: application/json</span><span class="sxs-lookup"><span data-stu-id="edb76-157">Content-type: application/json</span></span>

```JSON
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Edm.String",
    "value": "https://core.windows.net/investigation-actions-data/ID/CustomPlaybookCommandOutput/4ed5e7807ad1fe59b00b664fe06a0f07?se=2021-02-04T16%3A13%3A50Z&sp=r&sv=2019-07-07&sr=b&sig=1dYGe9rPvUlXBPvYSmr6/OLXPY98m8qWqfIQCBbyZTY%3D"
}
```

<span data-ttu-id="edb76-158">*Contenuto file:*</span><span class="sxs-lookup"><span data-stu-id="edb76-158">*File content:*</span></span> 

```JSON
{
    "script_name": "minidump.ps1",
    "exit_code": 0,
    "script_output": "Transcript started, output file is C:\\ProgramData\\Microsoft\\Windows Defender Advanced Threat Protection\\Temp\\PSScriptOutputs\\PSScript_Transcript_{TRANSCRIPT_ID}.txt
C:\\windows\\TEMP\\OfficeClickToRun.dmp.zip\n51 MB\n\u0000\u0000\u0000",
    "script_error":""
}
```

## <a name="related-topics"></a><span data-ttu-id="edb76-159">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="edb76-159">Related topics</span></span>

- [<span data-ttu-id="edb76-160">API per l'azione del computer</span><span class="sxs-lookup"><span data-stu-id="edb76-160">Get machine action API</span></span>](get-machineaction-object.md)
- [<span data-ttu-id="edb76-161">Annullare l'azione del computer</span><span class="sxs-lookup"><span data-stu-id="edb76-161">Cancel machine action</span></span>](cancel-machine-action.md)
- [<span data-ttu-id="edb76-162">Esegui risposta in tempo reale</span><span class="sxs-lookup"><span data-stu-id="edb76-162">Run live response</span></span>](run-live-response.md) 
