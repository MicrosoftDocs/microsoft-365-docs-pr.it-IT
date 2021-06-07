---
title: Ottenere punteggio di esposizione
description: Recupera il punteggio di esposizione dell'organizzazione.
keywords: api, api del grafico, api supportate, ottenere, punteggio di esposizione, punteggio di esposizione dell'organizzazione
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.openlocfilehash: 9da87dcb64f8c62966382e3a2888f03c49149a09
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770432"
---
# <a name="get-exposure-score"></a><span data-ttu-id="dffb0-104">Ottenere punteggio di esposizione</span><span class="sxs-lookup"><span data-stu-id="dffb0-104">Get exposure score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="dffb0-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="dffb0-105">**Applies to:**</span></span>
- [<span data-ttu-id="dffb0-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="dffb0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="dffb0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dffb0-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="dffb0-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="dffb0-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="dffb0-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="dffb0-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="dffb0-110">Recupera il punteggio di esposizione dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="dffb0-110">Retrieves the organizational exposure score.</span></span>

## <a name="permissions"></a><span data-ttu-id="dffb0-111">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="dffb0-111">Permissions</span></span>

<span data-ttu-id="dffb0-112">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="dffb0-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="dffb0-113">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi [Usare Microsoft Defender per le API endpoint](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="dffb0-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="dffb0-114">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="dffb0-114">Permission type</span></span> | <span data-ttu-id="dffb0-115">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="dffb0-115">Permission</span></span> | <span data-ttu-id="dffb0-116">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="dffb0-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="dffb0-117">Applicazione</span><span class="sxs-lookup"><span data-stu-id="dffb0-117">Application</span></span> | <span data-ttu-id="dffb0-118">Score.Read.All</span><span class="sxs-lookup"><span data-stu-id="dffb0-118">Score.Read.All</span></span> | <span data-ttu-id="dffb0-119">"Read Threat and Vulnerability Management score"</span><span class="sxs-lookup"><span data-stu-id="dffb0-119">'Read Threat and Vulnerability Management score'</span></span>
<span data-ttu-id="dffb0-120">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="dffb0-120">Delegated (work or school account)</span></span> | <span data-ttu-id="dffb0-121">Score.Read</span><span class="sxs-lookup"><span data-stu-id="dffb0-121">Score.Read</span></span> | <span data-ttu-id="dffb0-122">"Read Threat and Vulnerability Management score"</span><span class="sxs-lookup"><span data-stu-id="dffb0-122">'Read Threat and Vulnerability Management score'</span></span>

## <a name="http-request"></a><span data-ttu-id="dffb0-123">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="dffb0-123">HTTP request</span></span>

```
GET /api/exposureScore
```

## <a name="request-headers"></a><span data-ttu-id="dffb0-124">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="dffb0-124">Request headers</span></span>

<span data-ttu-id="dffb0-125">Name</span><span class="sxs-lookup"><span data-stu-id="dffb0-125">Name</span></span> | <span data-ttu-id="dffb0-126">Tipo</span><span class="sxs-lookup"><span data-stu-id="dffb0-126">Type</span></span> | <span data-ttu-id="dffb0-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dffb0-127">Description</span></span>
:---|:---|:---
<span data-ttu-id="dffb0-128">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="dffb0-128">Authorization</span></span> | <span data-ttu-id="dffb0-129">Stringa</span><span class="sxs-lookup"><span data-stu-id="dffb0-129">String</span></span> | <span data-ttu-id="dffb0-130">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="dffb0-130">Bearer {token}.</span></span> <span data-ttu-id="dffb0-131">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="dffb0-131">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="dffb0-132">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="dffb0-132">Request body</span></span>

<span data-ttu-id="dffb0-133">Vuoto</span><span class="sxs-lookup"><span data-stu-id="dffb0-133">Empty</span></span>

## <a name="response"></a><span data-ttu-id="dffb0-134">Risposta</span><span class="sxs-lookup"><span data-stu-id="dffb0-134">Response</span></span>

<span data-ttu-id="dffb0-135">Se ha esito positivo, questo metodo restituisce 200 OK, con i dati di esposizione nel corpo della risposta.</span><span class="sxs-lookup"><span data-stu-id="dffb0-135">If successful, this method returns 200 OK, with the exposure data in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="dffb0-136">Esempio</span><span class="sxs-lookup"><span data-stu-id="dffb0-136">Example</span></span>

### <a name="request"></a><span data-ttu-id="dffb0-137">Richiesta</span><span class="sxs-lookup"><span data-stu-id="dffb0-137">Request</span></span>

<span data-ttu-id="dffb0-138">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="dffb0-138">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/exposureScore
```

### <a name="response"></a><span data-ttu-id="dffb0-139">Risposta</span><span class="sxs-lookup"><span data-stu-id="dffb0-139">Response</span></span>

<span data-ttu-id="dffb0-140">Ecco un esempio di risposta.</span><span class="sxs-lookup"><span data-stu-id="dffb0-140">Here is an example of the response.</span></span>

>[!NOTE]
><span data-ttu-id="dffb0-141">L'elenco delle risposte mostrato qui potrebbe essere troncato per brevità.</span><span class="sxs-lookup"><span data-stu-id="dffb0-141">The response list shown here may be truncated for brevity.</span></span> 

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#ExposureScore/$entity",
    "time": "2019-12-03T07:23:53.280499Z",
    "score": 33.491554051195706
}

```

## <a name="see-also"></a><span data-ttu-id="dffb0-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dffb0-142">See also</span></span>

- [<span data-ttu-id="dffb0-143">Gestione delle vulnerabilità basata sui rischi & rischio</span><span class="sxs-lookup"><span data-stu-id="dffb0-143">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="dffb0-144">Punteggio di esposizione & rischio di vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="dffb0-144">Threat & Vulnerability exposure score</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-exposure-score)
