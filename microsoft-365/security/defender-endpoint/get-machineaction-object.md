---
title: API dell'oggetto Get MachineAction
description: Scopri come usare l'API Get MachineAction per recuperare un'azione del computer specifica in base al relativo ID in Microsoft Defender for Endpoint.
keywords: api, api del grafico, api supportate, oggetto machineaction
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
ms.openlocfilehash: 180179d5b1362ad4952618148b11007aa9efe91c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200066"
---
# <a name="get-machineaction-api"></a><span data-ttu-id="c16cf-104">Get machineAction API</span><span class="sxs-lookup"><span data-stu-id="c16cf-104">Get machineAction API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c16cf-105">**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="c16cf-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="c16cf-106">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="c16cf-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c16cf-107">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="c16cf-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="c16cf-108">Descrizione API</span><span class="sxs-lookup"><span data-stu-id="c16cf-108">API description</span></span>
<span data-ttu-id="c16cf-109">Recupera [un'azione del computer specifica](machineaction.md) in base al relativo ID.</span><span class="sxs-lookup"><span data-stu-id="c16cf-109">Retrieves specific [Machine Action](machineaction.md) by its ID.</span></span>


## <a name="limitations"></a><span data-ttu-id="c16cf-110">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="c16cf-110">Limitations</span></span>
1. <span data-ttu-id="c16cf-111">I limiti di frequenza per questa API sono 100 chiamate al minuto e 1500 chiamate all'ora.</span><span class="sxs-lookup"><span data-stu-id="c16cf-111">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="c16cf-112">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="c16cf-112">Permissions</span></span>
<span data-ttu-id="c16cf-113">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="c16cf-113">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="c16cf-114">Per altre informazioni, incluso come scegliere le autorizzazioni, vedi [Usare Defender per le API endpoint](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="c16cf-114">To learn more, including how to choose permissions, see [Use Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="c16cf-115">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="c16cf-115">Permission type</span></span> |   <span data-ttu-id="c16cf-116">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="c16cf-116">Permission</span></span>  |   <span data-ttu-id="c16cf-117">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="c16cf-117">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="c16cf-118">Applicazione</span><span class="sxs-lookup"><span data-stu-id="c16cf-118">Application</span></span> |   <span data-ttu-id="c16cf-119">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="c16cf-119">Machine.Read.All</span></span> |  <span data-ttu-id="c16cf-120">"Leggi tutti i profili computer"</span><span class="sxs-lookup"><span data-stu-id="c16cf-120">'Read all machine profiles'</span></span>
<span data-ttu-id="c16cf-121">Applicazione</span><span class="sxs-lookup"><span data-stu-id="c16cf-121">Application</span></span> |   <span data-ttu-id="c16cf-122">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="c16cf-122">Machine.ReadWrite.All</span></span> | <span data-ttu-id="c16cf-123">"Leggere e scrivere tutte le informazioni sul computer"</span><span class="sxs-lookup"><span data-stu-id="c16cf-123">'Read and write all machine information'</span></span>
<span data-ttu-id="c16cf-124">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="c16cf-124">Delegated (work or school account)</span></span> | <span data-ttu-id="c16cf-125">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="c16cf-125">Machine.Read</span></span> | <span data-ttu-id="c16cf-126">"Leggere le informazioni sul computer"</span><span class="sxs-lookup"><span data-stu-id="c16cf-126">'Read machine information'</span></span>
<span data-ttu-id="c16cf-127">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="c16cf-127">Delegated (work or school account)</span></span> | <span data-ttu-id="c16cf-128">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="c16cf-128">Machine.ReadWrite</span></span> | <span data-ttu-id="c16cf-129">"Leggere e scrivere informazioni sul computer"</span><span class="sxs-lookup"><span data-stu-id="c16cf-129">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="c16cf-130">Quando si ottiene un token utilizzando le credenziali utente:</span><span class="sxs-lookup"><span data-stu-id="c16cf-130">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="c16cf-131">L'utente deve disporre almeno dell'autorizzazione di ruolo seguente: 'Visualizza dati' (per ulteriori informazioni, vedere [Creare](user-roles.md) e gestire ruoli)</span><span class="sxs-lookup"><span data-stu-id="c16cf-131">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="c16cf-132">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="c16cf-132">HTTP request</span></span>
```
GET https://api.securitycenter.microsoft.com/api/machineactions/{id}
```

## <a name="request-headers"></a><span data-ttu-id="c16cf-133">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="c16cf-133">Request headers</span></span>

<span data-ttu-id="c16cf-134">Name</span><span class="sxs-lookup"><span data-stu-id="c16cf-134">Name</span></span> | <span data-ttu-id="c16cf-135">Tipo</span><span class="sxs-lookup"><span data-stu-id="c16cf-135">Type</span></span> | <span data-ttu-id="c16cf-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c16cf-136">Description</span></span>
:---|:---|:---
<span data-ttu-id="c16cf-137">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="c16cf-137">Authorization</span></span> | <span data-ttu-id="c16cf-138">Stringa</span><span class="sxs-lookup"><span data-stu-id="c16cf-138">String</span></span> | <span data-ttu-id="c16cf-139">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="c16cf-139">Bearer {token}.</span></span> <span data-ttu-id="c16cf-140">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="c16cf-140">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="c16cf-141">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="c16cf-141">Request body</span></span>
<span data-ttu-id="c16cf-142">Vuoto</span><span class="sxs-lookup"><span data-stu-id="c16cf-142">Empty</span></span>

## <a name="response"></a><span data-ttu-id="c16cf-143">Risposta</span><span class="sxs-lookup"><span data-stu-id="c16cf-143">Response</span></span>
<span data-ttu-id="c16cf-144">Se ha esito positivo, questo metodo restituisce 200 codice di risposta Ok con [un'entità Machine Action.](machineaction.md)</span><span class="sxs-lookup"><span data-stu-id="c16cf-144">If successful, this method returns 200, Ok response code with a [Machine Action](machineaction.md) entity.</span></span> <span data-ttu-id="c16cf-145">Se l'entità azione del computer con l'ID specificato non è stata trovata - 404 Non trovato.</span><span class="sxs-lookup"><span data-stu-id="c16cf-145">If machine action entity with the specified id was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="c16cf-146">Esempio</span><span class="sxs-lookup"><span data-stu-id="c16cf-146">Example</span></span>

<span data-ttu-id="c16cf-147">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="c16cf-147">**Request**</span></span>

<span data-ttu-id="c16cf-148">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="c16cf-148">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/machineactions/2e9da30d-27f6-4208-81f2-9cd3d67893ba
```

<span data-ttu-id="c16cf-149">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="c16cf-149">**Response**</span></span>

<span data-ttu-id="c16cf-150">Ecco un esempio di risposta.</span><span class="sxs-lookup"><span data-stu-id="c16cf-150">Here is an example of the response.</span></span>


```
HTTP/1.1 200 Ok
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineActions/$entity",
    "id": "5382f7ea-7557-4ab7-9782-d50480024a4e",
    "type": "Isolate",
    "scope": "Selective",
    "requestor": "Analyst@TestPrd.onmicrosoft.com",
    "requestorComment": "test for docs",
    "status": "Succeeded",
    "machineId": "7b1f4967d9728e5aa3c06a9e617a22a4a5a17378",
    "computerDnsName": "desktop-test",
    "creationDateTimeUtc": "2019-01-02T14:39:38.2262283Z",
    "lastUpdateDateTimeUtc": "2019-01-02T14:40:44.6596267Z",
    "relatedFileInfo": null
}


```