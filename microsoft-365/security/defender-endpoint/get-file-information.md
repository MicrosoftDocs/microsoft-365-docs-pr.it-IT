---
title: API per ottenere informazioni sui file
description: Scopri come usare l'API Get file information per ottenere un file tramite l'identificatore Sha1, Sha256 o MD5 in Microsoft Defender for Endpoint.
keywords: api, api del grafico, api supportate, get, file, informazioni, sha1, sha256, md5
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
ms.openlocfilehash: 181d808b465bfbf26eeff48a564e231b00a9a77f
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166853"
---
# <a name="get-file-information-api"></a><span data-ttu-id="77b55-104">API per ottenere informazioni sui file</span><span class="sxs-lookup"><span data-stu-id="77b55-104">Get file information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="77b55-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="77b55-105">**Applies to:**</span></span>
- [<span data-ttu-id="77b55-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="77b55-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="77b55-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="77b55-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="77b55-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="77b55-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="77b55-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="77b55-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="77b55-110">Descrizione API</span><span class="sxs-lookup"><span data-stu-id="77b55-110">API description</span></span>
<span data-ttu-id="77b55-111">Recupera un [file in](files.md) base all'identificatore Sha1 o Sha256</span><span class="sxs-lookup"><span data-stu-id="77b55-111">Retrieves a [File](files.md) by identifier Sha1, or Sha256</span></span>


## <a name="limitations"></a><span data-ttu-id="77b55-112">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="77b55-112">Limitations</span></span>
1. <span data-ttu-id="77b55-113">I limiti di frequenza per questa API sono 100 chiamate al minuto e 1500 chiamate all'ora.</span><span class="sxs-lookup"><span data-stu-id="77b55-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="77b55-114">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="77b55-114">Permissions</span></span>
<span data-ttu-id="77b55-115">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="77b55-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="77b55-116">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi [Usare Microsoft Defender per le API endpoint](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="77b55-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="77b55-117">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="77b55-117">Permission type</span></span> |   <span data-ttu-id="77b55-118">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="77b55-118">Permission</span></span>  |   <span data-ttu-id="77b55-119">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="77b55-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="77b55-120">Applicazione</span><span class="sxs-lookup"><span data-stu-id="77b55-120">Application</span></span> |   <span data-ttu-id="77b55-121">File.Read.All</span><span class="sxs-lookup"><span data-stu-id="77b55-121">File.Read.All</span></span> | <span data-ttu-id="77b55-122">"Leggi tutti i profili file"</span><span class="sxs-lookup"><span data-stu-id="77b55-122">'Read all file profiles'</span></span>
<span data-ttu-id="77b55-123">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="77b55-123">Delegated (work or school account)</span></span> | <span data-ttu-id="77b55-124">File.Read.All</span><span class="sxs-lookup"><span data-stu-id="77b55-124">File.Read.All</span></span> |    <span data-ttu-id="77b55-125">"Leggi tutti i profili file"</span><span class="sxs-lookup"><span data-stu-id="77b55-125">'Read all file profiles'</span></span>

>[!Note]
> <span data-ttu-id="77b55-126">Quando si ottiene un token utilizzando le credenziali utente:</span><span class="sxs-lookup"><span data-stu-id="77b55-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="77b55-127">L'utente deve disporre almeno dell'autorizzazione di ruolo seguente: 'Visualizza dati' (per ulteriori informazioni, vedere [Creare](user-roles.md) e gestire ruoli)</span><span class="sxs-lookup"><span data-stu-id="77b55-127">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="77b55-128">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="77b55-128">HTTP request</span></span>
```
GET /api/files/{id}
```

## <a name="request-headers"></a><span data-ttu-id="77b55-129">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="77b55-129">Request headers</span></span>

<span data-ttu-id="77b55-130">Name</span><span class="sxs-lookup"><span data-stu-id="77b55-130">Name</span></span> | <span data-ttu-id="77b55-131">Tipo</span><span class="sxs-lookup"><span data-stu-id="77b55-131">Type</span></span> | <span data-ttu-id="77b55-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="77b55-132">Description</span></span>
:---|:---|:---
<span data-ttu-id="77b55-133">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="77b55-133">Authorization</span></span> | <span data-ttu-id="77b55-134">Stringa</span><span class="sxs-lookup"><span data-stu-id="77b55-134">String</span></span> | <span data-ttu-id="77b55-135">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="77b55-135">Bearer {token}.</span></span> <span data-ttu-id="77b55-136">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="77b55-136">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="77b55-137">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="77b55-137">Request body</span></span>
<span data-ttu-id="77b55-138">Vuoto</span><span class="sxs-lookup"><span data-stu-id="77b55-138">Empty</span></span>

## <a name="response"></a><span data-ttu-id="77b55-139">Risposta</span><span class="sxs-lookup"><span data-stu-id="77b55-139">Response</span></span>
<span data-ttu-id="77b55-140">Se ha esito positivo e il file esiste- 200 OK con [l'entità file](files.md) nel corpo.</span><span class="sxs-lookup"><span data-stu-id="77b55-140">If successful and file exists - 200 OK with the [file](files.md) entity in the body.</span></span> <span data-ttu-id="77b55-141">Se il file non esiste - 404 Non trovato.</span><span class="sxs-lookup"><span data-stu-id="77b55-141">If file does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="77b55-142">Esempio</span><span class="sxs-lookup"><span data-stu-id="77b55-142">Example</span></span>

<span data-ttu-id="77b55-143">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="77b55-143">**Request**</span></span>

<span data-ttu-id="77b55-144">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="77b55-144">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/files/4388963aaa83afe2042a46a3c017ad50bdcdafb3
```

<span data-ttu-id="77b55-145">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="77b55-145">**Response**</span></span>

<span data-ttu-id="77b55-146">Ecco un esempio di risposta.</span><span class="sxs-lookup"><span data-stu-id="77b55-146">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Files/$entity",
    "sha1": "4388963aaa83afe2042a46a3c017ad50bdcdafb3",
    "sha256": "413c58c8267d2c8648d8f6384bacc2ae9c929b2b96578b6860b5087cd1bd6462",
    "globalPrevalence": 180022,
    "globalFirstObserved": "2017-09-19T03:51:27.6785431Z",
    "globalLastObserved": "2020-01-06T03:59:21.3229314Z",
    "size": 22139496,
    "fileType": "APP",
    "isPeFile": true,
    "filePublisher": "CHENGDU YIWO Tech Development Co., Ltd.",
    "fileProductName": "EaseUS MobiSaver for Android",
    "signer": "CHENGDU YIWO Tech Development Co., Ltd.",
    "issuer": "VeriSign Class 3 Code Signing 2010 CA",
    "signerHash": "6c3245d4a9bc0244d99dff27af259cbbae2e2d16",
    "isValidCertificate": false,
    "determinationType": "Pua",
    "determinationValue": "PUA:Win32/FusionCore"
}
```
