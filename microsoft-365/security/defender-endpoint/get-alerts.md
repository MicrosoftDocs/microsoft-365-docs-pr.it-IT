---
title: API avvisi elenco
description: Scopri come usare l'API Degli avvisi elenco per recuperare una raccolta di avvisi in Microsoft Defender per Endpoint.
keywords: api, api del grafico, api supportate, ottenere, avvisi, recenti
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 4da646a52392871cde99271a17ed6eb9111f51ab
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769246"
---
# <a name="list-alerts-api"></a><span data-ttu-id="76451-104">API avvisi elenco</span><span class="sxs-lookup"><span data-stu-id="76451-104">List alerts API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="76451-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="76451-105">**Applies to:**</span></span>
- [<span data-ttu-id="76451-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="76451-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="76451-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="76451-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="76451-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="76451-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="76451-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="76451-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="76451-110">Descrizione API</span><span class="sxs-lookup"><span data-stu-id="76451-110">API description</span></span>
<span data-ttu-id="76451-111">Recupera una raccolta di avvisi.</span><span class="sxs-lookup"><span data-stu-id="76451-111">Retrieves a collection of Alerts.</span></span>
<br><span data-ttu-id="76451-112">Supporta le [query OData V4.](https://www.odata.org/documentation/)</span><span class="sxs-lookup"><span data-stu-id="76451-112">Supports [OData V4 queries](https://www.odata.org/documentation/).</span></span>
<br><span data-ttu-id="76451-113">Operatori supportati da OData:</span><span class="sxs-lookup"><span data-stu-id="76451-113">OData supported operators:</span></span>
<br><span data-ttu-id="76451-114">```$filter``` on: ```alertCreationTime``` ```lastUpdateTime``` , , , , ```incidentId``` e ```InvestigationId``` le ```status``` ```severity``` ```category``` proprietà.</span><span class="sxs-lookup"><span data-stu-id="76451-114">```$filter``` on: ```alertCreationTime```, ```lastUpdateTime```, ```incidentId```,```InvestigationId```, ```status```, ```severity``` and ```category``` properties.</span></span>
<br><span data-ttu-id="76451-115">```$top``` con valore massimo di 10.000</span><span class="sxs-lookup"><span data-stu-id="76451-115">```$top``` with max value of 10,000</span></span>
<br>```$skip```
<br><span data-ttu-id="76451-116">```$expand``` di ```evidence```</span><span class="sxs-lookup"><span data-stu-id="76451-116">```$expand``` of ```evidence```</span></span>
<br><span data-ttu-id="76451-117">Vedi esempi in [Query OData con Microsoft Defender for Endpoint](exposed-apis-odata-samples.md)</span><span class="sxs-lookup"><span data-stu-id="76451-117">See examples at [OData queries with Microsoft Defender for Endpoint](exposed-apis-odata-samples.md)</span></span>


## <a name="limitations"></a><span data-ttu-id="76451-118">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="76451-118">Limitations</span></span>
1. <span data-ttu-id="76451-119">È possibile ottenere gli avvisi aggiornati per l'ultima volta in base al periodo di conservazione configurato.</span><span class="sxs-lookup"><span data-stu-id="76451-119">You can get alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="76451-120">Le dimensioni massime della pagina sono 10.000.</span><span class="sxs-lookup"><span data-stu-id="76451-120">Maximum page size is 10,000.</span></span>
3. <span data-ttu-id="76451-121">I limiti di frequenza per questa API sono 100 chiamate al minuto e 1500 chiamate all'ora.</span><span class="sxs-lookup"><span data-stu-id="76451-121">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span> 


## <a name="permissions"></a><span data-ttu-id="76451-122">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="76451-122">Permissions</span></span>
<span data-ttu-id="76451-123">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="76451-123">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="76451-124">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi [Usare Microsoft Defender per le API endpoint](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="76451-124">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="76451-125">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="76451-125">Permission type</span></span> |   <span data-ttu-id="76451-126">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="76451-126">Permission</span></span>  |   <span data-ttu-id="76451-127">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="76451-127">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="76451-128">Applicazione</span><span class="sxs-lookup"><span data-stu-id="76451-128">Application</span></span> |   <span data-ttu-id="76451-129">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="76451-129">Alert.Read.All</span></span> |    <span data-ttu-id="76451-130">"Leggi tutti gli avvisi"</span><span class="sxs-lookup"><span data-stu-id="76451-130">'Read all alerts'</span></span>
<span data-ttu-id="76451-131">Applicazione</span><span class="sxs-lookup"><span data-stu-id="76451-131">Application</span></span> |   <span data-ttu-id="76451-132">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="76451-132">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="76451-133">"Lettura e scrittura di tutti gli avvisi"</span><span class="sxs-lookup"><span data-stu-id="76451-133">'Read and write all alerts'</span></span>
<span data-ttu-id="76451-134">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="76451-134">Delegated (work or school account)</span></span> | <span data-ttu-id="76451-135">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="76451-135">Alert.Read</span></span> | <span data-ttu-id="76451-136">"Avvisi di lettura"</span><span class="sxs-lookup"><span data-stu-id="76451-136">'Read alerts'</span></span>
<span data-ttu-id="76451-137">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="76451-137">Delegated (work or school account)</span></span> | <span data-ttu-id="76451-138">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="76451-138">Alert.ReadWrite</span></span> | <span data-ttu-id="76451-139">"Avvisi di lettura e scrittura"</span><span class="sxs-lookup"><span data-stu-id="76451-139">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="76451-140">Quando si ottiene un token utilizzando le credenziali utente:</span><span class="sxs-lookup"><span data-stu-id="76451-140">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="76451-141">L'utente deve disporre almeno dell'autorizzazione di ruolo seguente: 'Visualizza dati' (per ulteriori informazioni, vedere [Creare](user-roles.md) e gestire ruoli)</span><span class="sxs-lookup"><span data-stu-id="76451-141">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="76451-142">La risposta includerà solo gli avvisi associati ai dispositivi a cui l'utente può accedere, in base alle impostazioni del gruppo di dispositivi (per ulteriori informazioni, vedere [Creare](machine-groups.md) e gestire gruppi di dispositivi)</span><span class="sxs-lookup"><span data-stu-id="76451-142">The response will include only alerts that are associated with devices that the user can access, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="76451-143">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="76451-143">HTTP request</span></span>
```
GET /api/alerts
```

## <a name="request-headers"></a><span data-ttu-id="76451-144">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="76451-144">Request headers</span></span>

<span data-ttu-id="76451-145">Name</span><span class="sxs-lookup"><span data-stu-id="76451-145">Name</span></span> | <span data-ttu-id="76451-146">Tipo</span><span class="sxs-lookup"><span data-stu-id="76451-146">Type</span></span> | <span data-ttu-id="76451-147">Descrizione</span><span class="sxs-lookup"><span data-stu-id="76451-147">Description</span></span>
:---|:---|:---
<span data-ttu-id="76451-148">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="76451-148">Authorization</span></span> | <span data-ttu-id="76451-149">Stringa</span><span class="sxs-lookup"><span data-stu-id="76451-149">String</span></span> | <span data-ttu-id="76451-150">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="76451-150">Bearer {token}.</span></span> <span data-ttu-id="76451-151">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="76451-151">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="76451-152">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="76451-152">Request body</span></span>
<span data-ttu-id="76451-153">Vuoto</span><span class="sxs-lookup"><span data-stu-id="76451-153">Empty</span></span>

## <a name="response"></a><span data-ttu-id="76451-154">Risposta</span><span class="sxs-lookup"><span data-stu-id="76451-154">Response</span></span>
<span data-ttu-id="76451-155">Se ha esito positivo, questo metodo restituisce 200 OK e un elenco di oggetti [avviso](alerts.md) nel corpo della risposta.</span><span class="sxs-lookup"><span data-stu-id="76451-155">If successful, this method returns 200 OK, and a list of [alert](alerts.md) objects in the response body.</span></span>


## <a name="example-1---default"></a><span data-ttu-id="76451-156">Esempio 1 - Impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="76451-156">Example 1 - Default</span></span>

<span data-ttu-id="76451-157">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="76451-157">**Request**</span></span>

<span data-ttu-id="76451-158">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="76451-158">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/alerts
```

<span data-ttu-id="76451-159">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="76451-159">**Response**</span></span>

<span data-ttu-id="76451-160">Ecco un esempio di risposta.</span><span class="sxs-lookup"><span data-stu-id="76451-160">Here is an example of the response.</span></span>

>[!NOTE]
><span data-ttu-id="76451-161">L'elenco delle risposte mostrato qui potrebbe essere troncato per brevità.</span><span class="sxs-lookup"><span data-stu-id="76451-161">The response list shown here may be truncated for brevity.</span></span> <span data-ttu-id="76451-162">Tutti gli avvisi verranno restituiti da una chiamata effettiva.</span><span class="sxs-lookup"><span data-stu-id="76451-162">All alerts will be returned from an actual call.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Alerts",
    "value": [
        {
            "id": "da637308392288907382_-880718168",
            "incidentId": 7587,
            "investigationId": 723156,
            "assignedTo": "secop123@contoso.com",
            "severity": "Low",
            "status": "New",
            "classification": "TruePositive",
            "determination": null,
            "investigationState": "Queued",
            "detectionSource": "WindowsDefenderAv",
            "category": "SuspiciousActivity",
            "threatFamilyName": "Meterpreter",
            "title": "Suspicious 'Meterpreter' behavior was detected",
            "description": "Malware and unwanted software are undesirable applications that perform annoying, disruptive, or harmful actions on affected machines. Some of these undesirable applications can replicate and spread from one machine to another. Others are able to receive commands from remote attackers and perform activities associated with cyber attacks.\n\nA malware is considered active if it is found running on the machine or it already has persistence mechanisms in place. Active malware detections are assigned higher severity ratings.\n\nBecause this malware was active, take precautionary measures and check for residual signs of infection.",
            "alertCreationTime": "2020-07-20T10:53:48.7657932Z",
            "firstEventTime": "2020-07-20T10:52:17.6654369Z",
            "lastEventTime": "2020-07-20T10:52:18.1362905Z",
            "lastUpdateTime": "2020-07-20T10:53:50.19Z",
            "resolvedTime": null,
            "machineId": "12ee6dd8c833c8a052ea231ec1b19adaf497b625",
            "computerDnsName": "temp123.middleeast.corp.microsoft.com",
            "rbacGroupName": "MiddleEast",
            "aadTenantId": "a839b112-1253-6432-9bf6-94542403f21c",
            "threatName": null,
            "mitreTechniques": [
                "T1064",
                "T1085",
                "T1220"
            ],
            "relatedUser": {
                "userName": "temp123",
                "domainName": "MIDDLEEAST"
            },
            "comments": [
                {
                    "comment": "test comment for docs",
                    "createdBy": "secop123@contoso.com",
                    "createdTime": "2020-07-21T01:00:37.8404534Z"
                }
            ],
            "evidence": []
        }
        ...
    ]
}
```

## <a name="example-2---get-10-latest-alerts-with-related-evidence"></a><span data-ttu-id="76451-163">Esempio 2 - Ottenere 10 avvisi più recenti con prove correlate</span><span class="sxs-lookup"><span data-stu-id="76451-163">Example 2 - Get 10 latest Alerts with related Evidence</span></span>

<span data-ttu-id="76451-164">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="76451-164">**Request**</span></span>

<span data-ttu-id="76451-165">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="76451-165">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/alerts?$top=10&$expand=evidence
```


<span data-ttu-id="76451-166">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="76451-166">**Response**</span></span>

<span data-ttu-id="76451-167">Ecco un esempio di risposta.</span><span class="sxs-lookup"><span data-stu-id="76451-167">Here is an example of the response.</span></span>

>[!NOTE]
><span data-ttu-id="76451-168">L'elenco delle risposte mostrato qui potrebbe essere troncato per brevità.</span><span class="sxs-lookup"><span data-stu-id="76451-168">The response list shown here may be truncated for brevity.</span></span> <span data-ttu-id="76451-169">Tutti gli avvisi verranno restituiti da una chiamata effettiva.</span><span class="sxs-lookup"><span data-stu-id="76451-169">All alerts will be returned from an actual call.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Alerts",
    "value": [
        {
            "id": "da637472900382838869_1364969609",
            "incidentId": 1126093,
            "investigationId": null,
            "assignedTo": null,
            "severity": "Low",
            "status": "New",
            "classification": null,
            "determination": null,
            "investigationState": "Queued",
            "detectionSource": "WindowsDefenderAtp",
            "detectorId": "17e10bbc-3a68-474a-8aad-faef14d43952",
            "category": "Execution",
            "threatFamilyName": null,
            "title": "Low-reputation arbitrary code executed by signed executable",
            "description": "Binaries signed by Microsoft can be used to run low-reputation arbitrary code. This technique hides the execution of malicious code within a trusted process. As a result, the trusted process might exhibit suspicious behaviors, such as opening a listening port or connecting to a command-and-control (C&C) server.",
            "alertCreationTime": "2021-01-26T20:33:57.7220239Z",
            "firstEventTime": "2021-01-26T20:31:32.9562661Z",
            "lastEventTime": "2021-01-26T20:31:33.0577322Z",
            "lastUpdateTime": "2021-01-26T20:33:59.2Z",
            "resolvedTime": null,
            "machineId": "111e6dd8c833c8a052ea231ec1b19adaf497b625",
            "computerDnsName": "temp123.middleeast.corp.microsoft.com",
            "rbacGroupName": "A",
            "aadTenantId": "a839b112-1253-6432-9bf6-94542403f21c",
            "threatName": null,
            "mitreTechniques": [
                "T1064",
                "T1085",
                "T1220"
            ],
            "relatedUser": {
                "userName": "temp123",
                "domainName": "MIDDLEEAST"
            },
            "comments": [
                {
                    "comment": "test comment for docs",
                    "createdBy": "secop123@contoso.com",
                    "createdTime": "2021-01-26T01:00:37.8404534Z"
                }
            ],
            "evidence": [
                {
                    "entityType": "User",
                    "evidenceCreationTime": "2021-01-26T20:33:58.42Z",
                    "sha1": null,
                    "sha256": null,
                    "fileName": null,
                    "filePath": null,
                    "processId": null,
                    "processCommandLine": null,
                    "processCreationTime": null,
                    "parentProcessId": null,
                    "parentProcessCreationTime": null,
                    "parentProcessFileName": null,
                    "parentProcessFilePath": null,
                    "ipAddress": null,
                    "url": null,
                    "registryKey": null,
                    "registryHive": null,
                    "registryValueType": null,
                    "registryValue": null,
                    "accountName": "eranb",
                    "domainName": "MIDDLEEAST",
                    "userSid": "S-1-5-21-11111607-1111760036-109187956-75141",
                    "aadUserId": "11118379-2a59-1111-ac3c-a51eb4a3c627",
                    "userPrincipalName": "temp123@microsoft.com",
                    "detectionStatus": null
                },
                {
                    "entityType": "Process",
                    "evidenceCreationTime": "2021-01-26T20:33:58.6133333Z",
                    "sha1": "ff836cfb1af40252bd2a2ea843032e99a5b262ed",
                    "sha256": "a4752c71d81afd3d5865d24ddb11a6b0c615062fcc448d24050c2172d2cbccd6",
                    "fileName": "rundll32.exe",
                    "filePath": "C:\\Windows\\SysWOW64",
                    "processId": 3276,
                    "processCommandLine": "rundll32.exe  c:\\temp\\suspicious.dll,RepeatAfterMe",
                    "processCreationTime": "2021-01-26T20:31:32.9581596Z",
                    "parentProcessId": 8420,
                    "parentProcessCreationTime": "2021-01-26T20:31:32.9004163Z",
                    "parentProcessFileName": "rundll32.exe",
                    "parentProcessFilePath": "C:\\Windows\\System32",
                    "ipAddress": null,
                    "url": null,
                    "registryKey": null,
                    "registryHive": null,
                    "registryValueType": null,
                    "registryValue": null,
                    "accountName": null,
                    "domainName": null,
                    "userSid": null,
                    "aadUserId": null,
                    "userPrincipalName": null,
                    "detectionStatus": "Detected"
                },
                {
                    "entityType": "File",
                    "evidenceCreationTime": "2021-01-26T20:33:58.42Z",
                    "sha1": "8563f95b2f8a284fc99da44500cd51a77c1ff36c",
                    "sha256": "dc0ade0c95d6db98882bc8fa6707e64353cd6f7767ff48d6a81a6c2aef21c608",
                    "fileName": "suspicious.dll",
                    "filePath": "c:\\temp",
                    "processId": null,
                    "processCommandLine": null,
                    "processCreationTime": null,
                    "parentProcessId": null,
                    "parentProcessCreationTime": null,
                    "parentProcessFileName": null,
                    "parentProcessFilePath": null,
                    "ipAddress": null,
                    "url": null,
                    "registryKey": null,
                    "registryHive": null,
                    "registryValueType": null,
                    "registryValue": null,
                    "accountName": null,
                    "domainName": null,
                    "userSid": null,
                    "aadUserId": null,
                    "userPrincipalName": null,
                    "detectionStatus": "Detected"
                }
            ]
        },
        ...
    ]
}
```


## <a name="see-also"></a><span data-ttu-id="76451-170">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="76451-170">See also</span></span>
- [<span data-ttu-id="76451-171">Query OData con Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="76451-171">OData queries with Microsoft Defender for Endpoint</span></span>](exposed-apis-odata-samples.md)
