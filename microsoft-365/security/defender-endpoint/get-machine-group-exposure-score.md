---
title: Elencare il punteggio di esposizione per gruppo di dispositivi
description: Recupera un elenco di punteggi di esposizione per gruppo di dispositivi.
keywords: api, api del grafico, api supportate, ottenere, punteggio di esposizione, gruppo di dispositivi, punteggio di esposizione del gruppo di dispositivi
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: dansimp
ms.author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 71daccdbcb223ac48d80721bf0a296d9c1a7c98c
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770098"
---
# <a name="list-exposure-score-by-device-group"></a><span data-ttu-id="8a3ff-104">Elencare il punteggio di esposizione per gruppo di dispositivi</span><span class="sxs-lookup"><span data-stu-id="8a3ff-104">List exposure score by device group</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8a3ff-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="8a3ff-105">**Applies to:**</span></span>
- [<span data-ttu-id="8a3ff-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="8a3ff-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8a3ff-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8a3ff-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="8a3ff-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="8a3ff-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="8a3ff-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="8a3ff-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="8a3ff-110">Recupera una raccolta di avvisi correlati a un determinato indirizzo di dominio.</span><span class="sxs-lookup"><span data-stu-id="8a3ff-110">Retrieves a collection of alerts related to a given domain address.</span></span>

## <a name="permissions"></a><span data-ttu-id="8a3ff-111">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="8a3ff-111">Permissions</span></span>

<span data-ttu-id="8a3ff-112">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="8a3ff-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="8a3ff-113">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi [Usare Microsoft Defender per le API endpoint](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="8a3ff-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="8a3ff-114">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="8a3ff-114">Permission type</span></span> |   <span data-ttu-id="8a3ff-115">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="8a3ff-115">Permission</span></span>  |   <span data-ttu-id="8a3ff-116">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="8a3ff-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="8a3ff-117">Applicazione</span><span class="sxs-lookup"><span data-stu-id="8a3ff-117">Application</span></span> | <span data-ttu-id="8a3ff-118">Score.Read.All</span><span class="sxs-lookup"><span data-stu-id="8a3ff-118">Score.Read.All</span></span> | <span data-ttu-id="8a3ff-119">"Read Threat and Vulnerability Management score"</span><span class="sxs-lookup"><span data-stu-id="8a3ff-119">'Read Threat and Vulnerability Management score'</span></span>
<span data-ttu-id="8a3ff-120">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="8a3ff-120">Delegated (work or school account)</span></span> | <span data-ttu-id="8a3ff-121">Score.Read</span><span class="sxs-lookup"><span data-stu-id="8a3ff-121">Score.Read</span></span> | <span data-ttu-id="8a3ff-122">"Read Threat and Vulnerability Management score"</span><span class="sxs-lookup"><span data-stu-id="8a3ff-122">'Read Threat and Vulnerability Management score'</span></span>

## <a name="http-request"></a><span data-ttu-id="8a3ff-123">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="8a3ff-123">HTTP request</span></span>

```
GET /api/exposureScore/ByMachineGroups
```

## <a name="request-headers"></a><span data-ttu-id="8a3ff-124">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="8a3ff-124">Request headers</span></span>

| <span data-ttu-id="8a3ff-125">Name</span><span class="sxs-lookup"><span data-stu-id="8a3ff-125">Name</span></span>        | <span data-ttu-id="8a3ff-126">Tipo</span><span class="sxs-lookup"><span data-stu-id="8a3ff-126">Type</span></span> | <span data-ttu-id="8a3ff-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8a3ff-127">Description</span></span>
|:--------------|:-------|:--------------|
| <span data-ttu-id="8a3ff-128">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="8a3ff-128">Authorization</span></span> | <span data-ttu-id="8a3ff-129">Stringa</span><span class="sxs-lookup"><span data-stu-id="8a3ff-129">String</span></span> | <span data-ttu-id="8a3ff-130">Bearer {token}. **Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="8a3ff-130">Bearer {token}.**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="8a3ff-131">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="8a3ff-131">Request body</span></span>

<span data-ttu-id="8a3ff-132">Vuoto</span><span class="sxs-lookup"><span data-stu-id="8a3ff-132">Empty</span></span>

## <a name="response"></a><span data-ttu-id="8a3ff-133">Risposta</span><span class="sxs-lookup"><span data-stu-id="8a3ff-133">Response</span></span>

<span data-ttu-id="8a3ff-134">Se ha esito positivo, questo metodo restituisce 200 OK, con un elenco del punteggio di esposizione per i dati del gruppo di dispositivi nel corpo della risposta.</span><span class="sxs-lookup"><span data-stu-id="8a3ff-134">If successful, this method returns 200 OK, with a list of exposure score per device group data in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="8a3ff-135">Esempio</span><span class="sxs-lookup"><span data-stu-id="8a3ff-135">Example</span></span>

### <a name="request"></a><span data-ttu-id="8a3ff-136">Richiesta</span><span class="sxs-lookup"><span data-stu-id="8a3ff-136">Request</span></span>

<span data-ttu-id="8a3ff-137">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="8a3ff-137">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/exposureScore/ByMachineGroups
```

### <a name="response"></a><span data-ttu-id="8a3ff-138">Risposta</span><span class="sxs-lookup"><span data-stu-id="8a3ff-138">Response</span></span>

<span data-ttu-id="8a3ff-139">Ecco un esempio di risposta.</span><span class="sxs-lookup"><span data-stu-id="8a3ff-139">Here is an example of the response.</span></span>

```json

{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#ExposureScore",
    "value": [
        {
            "time": "2019-12-03T09:51:28.214338Z",
            "score": 41.38041766305988,
            "rbacGroupName": "GroupOne"
        },
        {
            "time": "2019-12-03T09:51:28.2143399Z",
            "score": 37.403726933165366,
            "rbacGroupName": "GroupTwo"
        }
        ...
    ]
}
```

## <a name="related-topics"></a><span data-ttu-id="8a3ff-140">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="8a3ff-140">Related topics</span></span>

- [<span data-ttu-id="8a3ff-141">Gestione delle vulnerabilità basata sui rischi & rischio</span><span class="sxs-lookup"><span data-stu-id="8a3ff-141">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="8a3ff-142">Punteggio di esposizione & rischio di vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="8a3ff-142">Threat & Vulnerability exposure score</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-exposure-score)
