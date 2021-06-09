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
ms.openlocfilehash: 071b0e7597d334fe06d5045e06a5c4d82dd65609
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845391"
---
# <a name="get-exposure-score"></a><span data-ttu-id="c113a-104">Ottenere punteggio di esposizione</span><span class="sxs-lookup"><span data-stu-id="c113a-104">Get exposure score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c113a-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="c113a-105">**Applies to:**</span></span>
- [<span data-ttu-id="c113a-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="c113a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c113a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c113a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="c113a-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="c113a-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c113a-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="c113a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="c113a-110">Recupera il punteggio di esposizione dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c113a-110">Retrieves the organizational exposure score.</span></span>

## <a name="permissions"></a><span data-ttu-id="c113a-111">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="c113a-111">Permissions</span></span>

<span data-ttu-id="c113a-112">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="c113a-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="c113a-113">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi [Usare Microsoft Defender per le API endpoint](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="c113a-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="c113a-114">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="c113a-114">Permission type</span></span> | <span data-ttu-id="c113a-115">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="c113a-115">Permission</span></span> | <span data-ttu-id="c113a-116">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="c113a-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="c113a-117">Applicazione</span><span class="sxs-lookup"><span data-stu-id="c113a-117">Application</span></span> | <span data-ttu-id="c113a-118">Score.Read.All</span><span class="sxs-lookup"><span data-stu-id="c113a-118">Score.Read.All</span></span> | <span data-ttu-id="c113a-119">"Read Threat and Vulnerability Management score"</span><span class="sxs-lookup"><span data-stu-id="c113a-119">'Read Threat and Vulnerability Management score'</span></span>
<span data-ttu-id="c113a-120">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="c113a-120">Delegated (work or school account)</span></span> | <span data-ttu-id="c113a-121">Score.Read</span><span class="sxs-lookup"><span data-stu-id="c113a-121">Score.Read</span></span> | <span data-ttu-id="c113a-122">"Read Threat and Vulnerability Management score"</span><span class="sxs-lookup"><span data-stu-id="c113a-122">'Read Threat and Vulnerability Management score'</span></span>

## <a name="http-request"></a><span data-ttu-id="c113a-123">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="c113a-123">HTTP request</span></span>

```
GET /api/exposureScore
```

## <a name="request-headers"></a><span data-ttu-id="c113a-124">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="c113a-124">Request headers</span></span>

<span data-ttu-id="c113a-125">Name</span><span class="sxs-lookup"><span data-stu-id="c113a-125">Name</span></span> | <span data-ttu-id="c113a-126">Tipo</span><span class="sxs-lookup"><span data-stu-id="c113a-126">Type</span></span> | <span data-ttu-id="c113a-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c113a-127">Description</span></span>
:---|:---|:---
<span data-ttu-id="c113a-128">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="c113a-128">Authorization</span></span> | <span data-ttu-id="c113a-129">Stringa</span><span class="sxs-lookup"><span data-stu-id="c113a-129">String</span></span> | <span data-ttu-id="c113a-130">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="c113a-130">Bearer {token}.</span></span> <span data-ttu-id="c113a-131">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="c113a-131">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="c113a-132">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="c113a-132">Request body</span></span>

<span data-ttu-id="c113a-133">Vuoto</span><span class="sxs-lookup"><span data-stu-id="c113a-133">Empty</span></span>

## <a name="response"></a><span data-ttu-id="c113a-134">Risposta</span><span class="sxs-lookup"><span data-stu-id="c113a-134">Response</span></span>

<span data-ttu-id="c113a-135">Se ha esito positivo, questo metodo restituisce 200 OK, con i dati di esposizione nel corpo della risposta.</span><span class="sxs-lookup"><span data-stu-id="c113a-135">If successful, this method returns 200 OK, with the exposure data in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="c113a-136">Esempio</span><span class="sxs-lookup"><span data-stu-id="c113a-136">Example</span></span>

### <a name="request"></a><span data-ttu-id="c113a-137">Richiesta</span><span class="sxs-lookup"><span data-stu-id="c113a-137">Request</span></span>

<span data-ttu-id="c113a-138">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="c113a-138">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/exposureScore
```

### <a name="response"></a><span data-ttu-id="c113a-139">Risposta</span><span class="sxs-lookup"><span data-stu-id="c113a-139">Response</span></span>

<span data-ttu-id="c113a-140">Ecco un esempio di risposta.</span><span class="sxs-lookup"><span data-stu-id="c113a-140">Here is an example of the response.</span></span>

>[!NOTE]
><span data-ttu-id="c113a-141">L'elenco delle risposte mostrato qui potrebbe essere troncato per brevità.</span><span class="sxs-lookup"><span data-stu-id="c113a-141">The response list shown here may be truncated for brevity.</span></span> 

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#ExposureScore/$entity",
    "time": "2019-12-03T07:23:53.280499Z",
    "score": 33.491554051195706
}

```

## <a name="see-also"></a><span data-ttu-id="c113a-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c113a-142">See also</span></span>

- [<span data-ttu-id="c113a-143">Gestione delle vulnerabilità basata sui rischi & rischio</span><span class="sxs-lookup"><span data-stu-id="c113a-143">Risk-based Threat & Vulnerability Management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="c113a-144">Punteggio di esposizione & rischio di vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="c113a-144">Threat & Vulnerability exposure score</span></span>](/microsoft-365/security/defender-endpoint/tvm-exposure-score)
