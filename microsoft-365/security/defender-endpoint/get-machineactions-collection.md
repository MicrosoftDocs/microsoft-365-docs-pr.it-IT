---
title: List machineActions API
description: Scopri come usare l'API List MachineActions per recuperare una raccolta di azioni del computer in Microsoft Defender per Endpoint.
keywords: api, api del grafico, api supportate, raccolta machineaction
search.product: eADQiWindows 10XVcnh
ms.prod: w10
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 2ee9a4e29dded3e299ffbb2c2997fd02f32d1abf
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771118"
---
# <a name="list-machineactions-api"></a><span data-ttu-id="7da4e-104">List MachineActions API</span><span class="sxs-lookup"><span data-stu-id="7da4e-104">List MachineActions API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="7da4e-105">**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="7da4e-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="7da4e-106">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="7da4e-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="7da4e-107">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="7da4e-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="7da4e-108">Descrizione API</span><span class="sxs-lookup"><span data-stu-id="7da4e-108">API description</span></span>
<span data-ttu-id="7da4e-109">Recupera un insieme di [azioni del computer.](machineaction.md)</span><span class="sxs-lookup"><span data-stu-id="7da4e-109">Retrieves a collection of [Machine Actions](machineaction.md).</span></span>
<br><span data-ttu-id="7da4e-110">Supporta le [query OData V4.](https://www.odata.org/documentation/)</span><span class="sxs-lookup"><span data-stu-id="7da4e-110">Supports [OData V4 queries](https://www.odata.org/documentation/).</span></span>
<br><span data-ttu-id="7da4e-111">La query di OData ```$filter``` è supportata su: ```status``` , , e sulle ```machineId``` ```type``` ```requestor``` ```creationDateTimeUtc``` proprietà.</span><span class="sxs-lookup"><span data-stu-id="7da4e-111">The OData's ```$filter``` query is supported on: ```status```, ```machineId```, ```type```, ```requestor``` and ```creationDateTimeUtc``` properties.</span></span>
<br><span data-ttu-id="7da4e-112">Vedi esempi in [Query OData con Microsoft Defender for Endpoint](exposed-apis-odata-samples.md)</span><span class="sxs-lookup"><span data-stu-id="7da4e-112">See examples at [OData queries with Microsoft Defender for Endpoint](exposed-apis-odata-samples.md)</span></span>


## <a name="limitations"></a><span data-ttu-id="7da4e-113">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="7da4e-113">Limitations</span></span>
1. <span data-ttu-id="7da4e-114">Le dimensioni massime della pagina sono 10.000.</span><span class="sxs-lookup"><span data-stu-id="7da4e-114">Maximum page size is 10,000.</span></span>
2. <span data-ttu-id="7da4e-115">I limiti di frequenza per questa API sono 100 chiamate al minuto e 1500 chiamate all'ora.</span><span class="sxs-lookup"><span data-stu-id="7da4e-115">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span> 


## <a name="permissions"></a><span data-ttu-id="7da4e-116">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="7da4e-116">Permissions</span></span>
<span data-ttu-id="7da4e-117">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="7da4e-117">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="7da4e-118">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi [Usare Microsoft Defender per le API endpoint](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="7da4e-118">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="7da4e-119">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="7da4e-119">Permission type</span></span> |   <span data-ttu-id="7da4e-120">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="7da4e-120">Permission</span></span>  |   <span data-ttu-id="7da4e-121">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="7da4e-121">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="7da4e-122">Applicazione</span><span class="sxs-lookup"><span data-stu-id="7da4e-122">Application</span></span> |   <span data-ttu-id="7da4e-123">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="7da4e-123">Machine.Read.All</span></span> |  <span data-ttu-id="7da4e-124">"Leggi tutti i profili computer"</span><span class="sxs-lookup"><span data-stu-id="7da4e-124">'Read all machine profiles'</span></span>
<span data-ttu-id="7da4e-125">Applicazione</span><span class="sxs-lookup"><span data-stu-id="7da4e-125">Application</span></span> |   <span data-ttu-id="7da4e-126">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="7da4e-126">Machine.ReadWrite.All</span></span> | <span data-ttu-id="7da4e-127">"Leggere e scrivere tutte le informazioni sul computer"</span><span class="sxs-lookup"><span data-stu-id="7da4e-127">'Read and write all machine information'</span></span>
<span data-ttu-id="7da4e-128">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="7da4e-128">Delegated (work or school account)</span></span> | <span data-ttu-id="7da4e-129">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="7da4e-129">Machine.Read</span></span> | <span data-ttu-id="7da4e-130">"Leggere le informazioni sul computer"</span><span class="sxs-lookup"><span data-stu-id="7da4e-130">'Read machine information'</span></span>
<span data-ttu-id="7da4e-131">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="7da4e-131">Delegated (work or school account)</span></span> | <span data-ttu-id="7da4e-132">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="7da4e-132">Machine.ReadWrite</span></span> | <span data-ttu-id="7da4e-133">"Leggere e scrivere informazioni sul computer"</span><span class="sxs-lookup"><span data-stu-id="7da4e-133">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="7da4e-134">Quando si ottiene un token utilizzando le credenziali utente:</span><span class="sxs-lookup"><span data-stu-id="7da4e-134">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="7da4e-135">L'utente deve disporre almeno dell'autorizzazione di ruolo seguente: 'Visualizza dati' (per ulteriori informazioni, vedere [Creare](user-roles.md) e gestire ruoli)</span><span class="sxs-lookup"><span data-stu-id="7da4e-135">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="7da4e-136">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="7da4e-136">HTTP request</span></span>
```
GET https://api.securitycenter.microsoft.com/api/machineactions
```

## <a name="request-headers"></a><span data-ttu-id="7da4e-137">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="7da4e-137">Request headers</span></span>

<span data-ttu-id="7da4e-138">Name</span><span class="sxs-lookup"><span data-stu-id="7da4e-138">Name</span></span> | <span data-ttu-id="7da4e-139">Tipo</span><span class="sxs-lookup"><span data-stu-id="7da4e-139">Type</span></span> | <span data-ttu-id="7da4e-140">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7da4e-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="7da4e-141">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="7da4e-141">Authorization</span></span> | <span data-ttu-id="7da4e-142">Stringa</span><span class="sxs-lookup"><span data-stu-id="7da4e-142">String</span></span> | <span data-ttu-id="7da4e-143">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="7da4e-143">Bearer {token}.</span></span> <span data-ttu-id="7da4e-144">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="7da4e-144">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="7da4e-145">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="7da4e-145">Request body</span></span>
<span data-ttu-id="7da4e-146">Vuoto</span><span class="sxs-lookup"><span data-stu-id="7da4e-146">Empty</span></span>

## <a name="response"></a><span data-ttu-id="7da4e-147">Risposta</span><span class="sxs-lookup"><span data-stu-id="7da4e-147">Response</span></span>
<span data-ttu-id="7da4e-148">Se ha esito positivo, questo metodo restituisce 200 codice di risposta Ok con una raccolta di [entità machineAction.](machineaction.md)</span><span class="sxs-lookup"><span data-stu-id="7da4e-148">If successful, this method returns 200, Ok response code with a collection of [machineAction](machineaction.md) entities.</span></span>


## <a name="example-1"></a><span data-ttu-id="7da4e-149">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="7da4e-149">Example 1</span></span>

<span data-ttu-id="7da4e-150">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="7da4e-150">**Request**</span></span>

<span data-ttu-id="7da4e-151">Ecco un esempio della richiesta in un'organizzazione con tre MachineActions.</span><span class="sxs-lookup"><span data-stu-id="7da4e-151">Here is an example of the request on an organization that has three MachineActions.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/machineactions
```

<span data-ttu-id="7da4e-152">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="7da4e-152">**Response**</span></span>

<span data-ttu-id="7da4e-153">Ecco un esempio di risposta.</span><span class="sxs-lookup"><span data-stu-id="7da4e-153">Here is an example of the response.</span></span>


```
HTTP/1.1 200 Ok
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineActions",
    "value": [
        {
            "id": "69dc3630-1ccc-4342-acf3-35286eec741d",
            "type": "CollectInvestigationPackage",
            "scope": null,
            "requestor": "Analyst@contoso.com",
            "requestorComment": "test",
            "status": "Succeeded",
            "machineId": "f46b9bb259ed4a7fb9981b73510e3cc7aa81ec1f",
            "computerDnsName": "desktop-39g9tgl",
            "creationDateTimeUtc": "2018-12-04T12:43:57.2011911Z",
            "lastUpdateTimeUtc": "2018-12-04T12:45:25.4049122Z",
            "relatedFileInfo": null
        },
        {
            "id": "2e9da30d-27f6-4208-81f2-9cd3d67893ba",
            "type": "RunAntiVirusScan",
            "scope": "Full",
            "requestor": "Analyst@contoso.com",
            "requestorComment": "Check machine for viruses due to alert 3212",
            "status": "Succeeded",
            "machineId": "f46b9bb259ed4a7fb9981b73510e3cc7aa81ec1f",
            "computerDnsName": "desktop-39g9tgl",
            "creationDateTimeUtc": "2018-12-04T12:18:27.1293487Z",
            "lastUpdateTimeUtc": "2018-12-04T12:18:57.5511934Z",
            "relatedFileInfo": null
        },
        {
            "id": "44cffc15-0e3d-4cbf-96aa-bf76f9b27f5e",
            "type": "StopAndQuarantineFile",
            "scope": null,
            "requestor": "Analyst@contoso.com",
            "requestorComment": "test",
            "status": "Succeeded",
            "machineId": "f46b9bb259ed4a7fb9981b73510e3cc7aa81ec1f",
            "computerDnsName": "desktop-39g9tgl",
            "creationDateTimeUtc": "2018-12-04T12:15:40.6052029Z",
            "lastUpdateTimeUtc": "2018-12-04T12:16:14.2899973Z",
            "relatedFileInfo": {
                "fileIdentifier": "a0c659857ccbe457fdaf5fe21d54efdcbf6f6508",
                "fileIdentifierType": "Sha1"
            }
        }
    ]
}
```

## <a name="example-2"></a><span data-ttu-id="7da4e-154">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="7da4e-154">Example 2</span></span>

<span data-ttu-id="7da4e-155">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="7da4e-155">**Request**</span></span>

<span data-ttu-id="7da4e-156">Ecco un esempio di richiesta che filtra MachineActions in base all'ID computer e mostra le ultime due MachineActions.</span><span class="sxs-lookup"><span data-stu-id="7da4e-156">Here is an example of a request that filters the MachineActions by machine ID and shows the latest two MachineActions.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/machineactions?$filter=machineId eq 'f46b9bb259ed4a7fb9981b73510e3cc7aa81ec1f'&$top=2
```

<span data-ttu-id="7da4e-157">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="7da4e-157">**Response**</span></span>

<span data-ttu-id="7da4e-158">Ecco un esempio di risposta.</span><span class="sxs-lookup"><span data-stu-id="7da4e-158">Here is an example of the response.</span></span>

```
HTTP/1.1 200 Ok
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineActions",
    "value": [
        {
            "id": "69dc3630-1ccc-4342-acf3-35286eec741d",
            "type": "CollectInvestigationPackage",
            "scope": null,
            "requestor": "Analyst@contoso.com",
            "requestorComment": "test",
            "status": "Succeeded",
            "machineId": "f46b9bb259ed4a7fb9981b73510e3cc7aa81ec1f",
            "computerDnsName": "desktop-39g9tgl",
            "creationDateTimeUtc": "2018-12-04T12:43:57.2011911Z",
            "lastUpdateTimeUtc": "2018-12-04T12:45:25.4049122Z",
            "relatedFileInfo": null
        },
        {
            "id": "2e9da30d-27f6-4208-81f2-9cd3d67893ba",
            "type": "RunAntiVirusScan",
            "scope": "Full",
            "requestor": "Analyst@contoso.com",
            "requestorComment": "Check machine for viruses due to alert 3212",
            "status": "Succeeded",
            "machineId": "f46b9bb259ed4a7fb9981b73510e3cc7aa81ec1f",
            "computerDnsName": "desktop-39g9tgl",
            "creationDateTimeUtc": "2018-12-04T12:18:27.1293487Z",
            "lastUpdateTimeUtc": "2018-12-04T12:18:57.5511934Z",
            "relatedFileInfo": null
        }
    ]
}
```

## <a name="related-topics"></a><span data-ttu-id="7da4e-159">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="7da4e-159">Related topics</span></span>
- [<span data-ttu-id="7da4e-160">Query OData con Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="7da4e-160">OData queries with Microsoft Defender for Endpoint</span></span>](exposed-apis-odata-samples.md)
