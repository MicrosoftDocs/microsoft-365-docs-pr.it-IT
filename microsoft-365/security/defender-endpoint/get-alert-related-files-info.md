---
title: Ottenere informazioni sui file correlati agli avvisi
description: Recupera tutti i file correlati a un avviso specifico usando Microsoft Defender for Endpoint.
keywords: api, api del grafico, api supportate, ottenere informazioni sugli avvisi, informazioni sugli avvisi, file correlati
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
ms.openlocfilehash: 31cbbaee9a97c061b61cc9f7ecc71bb759aea081
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166994"
---
# <a name="get-alert-related-files-information-api"></a><span data-ttu-id="4976d-104">API per ottenere informazioni sui file correlati agli avvisi</span><span class="sxs-lookup"><span data-stu-id="4976d-104">Get alert related files information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4976d-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="4976d-105">**Applies to:**</span></span>
- [<span data-ttu-id="4976d-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="4976d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4976d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4976d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
 
> <span data-ttu-id="4976d-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="4976d-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="4976d-109">Iscriviti per la versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="4976d-109">Sign up for free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="4976d-110">Descrizione API</span><span class="sxs-lookup"><span data-stu-id="4976d-110">API description</span></span>
<span data-ttu-id="4976d-111">Recupera tutti i file correlati a un avviso specifico.</span><span class="sxs-lookup"><span data-stu-id="4976d-111">Retrieves all files related to a specific alert.</span></span>


## <a name="limitations"></a><span data-ttu-id="4976d-112">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="4976d-112">Limitations</span></span>
1. <span data-ttu-id="4976d-113">È possibile eseguire query sugli avvisi aggiornati per l'ultimo aggiornamento in base al periodo di conservazione configurato.</span><span class="sxs-lookup"><span data-stu-id="4976d-113">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="4976d-114">I limiti di frequenza per questa API sono 100 chiamate al minuto e 1500 chiamate all'ora.</span><span class="sxs-lookup"><span data-stu-id="4976d-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="4976d-115">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="4976d-115">Permissions</span></span>
<span data-ttu-id="4976d-116">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="4976d-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="4976d-117">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi [Usare Microsoft Defender per le API endpoint](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="4976d-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="4976d-118">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="4976d-118">Permission type</span></span> | <span data-ttu-id="4976d-119">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="4976d-119">Permission</span></span> | <span data-ttu-id="4976d-120">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="4976d-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="4976d-121">Applicazione</span><span class="sxs-lookup"><span data-stu-id="4976d-121">Application</span></span> | <span data-ttu-id="4976d-122">File.Read.All</span><span class="sxs-lookup"><span data-stu-id="4976d-122">File.Read.All</span></span> | <span data-ttu-id="4976d-123">"Lettura profili file"</span><span class="sxs-lookup"><span data-stu-id="4976d-123">'Read file profiles'</span></span>
<span data-ttu-id="4976d-124">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="4976d-124">Delegated (work or school account)</span></span> | <span data-ttu-id="4976d-125">File.Read.All</span><span class="sxs-lookup"><span data-stu-id="4976d-125">File.Read.All</span></span> | <span data-ttu-id="4976d-126">"Lettura profili file"</span><span class="sxs-lookup"><span data-stu-id="4976d-126">'Read file profiles'</span></span>

>[!Note]
> <span data-ttu-id="4976d-127">Quando si ottiene un token utilizzando le credenziali utente:</span><span class="sxs-lookup"><span data-stu-id="4976d-127">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="4976d-128">L'utente deve disporre almeno dell'autorizzazione di ruolo seguente: 'Visualizza dati' (per ulteriori informazioni, vedere [Creare](user-roles.md) e gestire ruoli)</span><span class="sxs-lookup"><span data-stu-id="4976d-128">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="4976d-129">L'utente deve avere accesso al dispositivo associato all'avviso, in base alle impostazioni del gruppo di dispositivi (per ulteriori informazioni, vedere [Creare](machine-groups.md) e gestire gruppi di dispositivi)</span><span class="sxs-lookup"><span data-stu-id="4976d-129">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="4976d-130">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="4976d-130">HTTP request</span></span>
```
GET /api/alerts/{id}/files
```

## <a name="request-headers"></a><span data-ttu-id="4976d-131">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="4976d-131">Request headers</span></span>

<span data-ttu-id="4976d-132">Name</span><span class="sxs-lookup"><span data-stu-id="4976d-132">Name</span></span> | <span data-ttu-id="4976d-133">Tipo</span><span class="sxs-lookup"><span data-stu-id="4976d-133">Type</span></span> | <span data-ttu-id="4976d-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4976d-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="4976d-135">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="4976d-135">Authorization</span></span> | <span data-ttu-id="4976d-136">Stringa</span><span class="sxs-lookup"><span data-stu-id="4976d-136">String</span></span> | <span data-ttu-id="4976d-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="4976d-137">Bearer {token}.</span></span> <span data-ttu-id="4976d-138">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="4976d-138">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="4976d-139">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="4976d-139">Request body</span></span>
<span data-ttu-id="4976d-140">Vuoto</span><span class="sxs-lookup"><span data-stu-id="4976d-140">Empty</span></span>

## <a name="response"></a><span data-ttu-id="4976d-141">Risposta</span><span class="sxs-lookup"><span data-stu-id="4976d-141">Response</span></span>
<span data-ttu-id="4976d-142">Se l'operazione ha esito positivo e l'avviso e i file sono presenti- 200 OK.</span><span class="sxs-lookup"><span data-stu-id="4976d-142">If successful and alert and files exist - 200 OK.</span></span> <span data-ttu-id="4976d-143">Se l'avviso non viene trovato - 404 Non trovato.</span><span class="sxs-lookup"><span data-stu-id="4976d-143">If alert not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="4976d-144">Esempio</span><span class="sxs-lookup"><span data-stu-id="4976d-144">Example</span></span>

<span data-ttu-id="4976d-145">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="4976d-145">**Request**</span></span>

<span data-ttu-id="4976d-146">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="4976d-146">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/alerts/636688558380765161_2136280442/files
```

<span data-ttu-id="4976d-147">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="4976d-147">**Response**</span></span>

<span data-ttu-id="4976d-148">Ecco un esempio di risposta.</span><span class="sxs-lookup"><span data-stu-id="4976d-148">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Files",
    "value": [
        {
            "sha1": "f2a00fd2f2de1be0214b8529f1e9f67096c1aa70",
            "sha256": "dcd71ef5fff4362a9f64cf3f96f14f2b11d6f428f3badbedcb9ff3361e7079aa",
            "md5": "8d5b7cc9a832e21d22503057e1fec8e9",
            "globalPrevalence": 29,
            "globalFirstObserved": "2019-03-23T23:54:06.0135204Z",
            "globalLastObserved": "2019-04-23T00:43:20.0489831Z",
            "size": 113984,
            "fileType": null,
            "isPeFile": true,
            "filePublisher": "Microsoft Corporation",
            "fileProductName": "Microsoft� Windows� Operating System",
            "signer": "Microsoft Corporation",
            "issuer": "Microsoft Code Signing PCA",
            "signerHash": "9dc17888b5cfad98b3cb35c1994e96227f061675",
            "isValidCertificate": true,
            "determinationType": "Unknown",
            "determinationValue": null
        }
        ...
    ]
}
```
