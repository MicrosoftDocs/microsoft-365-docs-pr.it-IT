---
title: Ottenere il punteggio di esposizione
description: Recupera il punteggio di esposizione dell'organizzazione.
keywords: api, api del grafico, api supportate, ottenere, punteggio di esposizione, punteggio di esposizione dell'organizzazione
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: levinec
ms.author: ellevin
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: e7037e49a7f750597af15cfb16e1552aeb98859a
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166862"
---
# <a name="get-exposure-score"></a><span data-ttu-id="03d3e-104">Ottenere il punteggio di esposizione</span><span class="sxs-lookup"><span data-stu-id="03d3e-104">Get exposure score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="03d3e-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="03d3e-105">**Applies to:**</span></span>
- [<span data-ttu-id="03d3e-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="03d3e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="03d3e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="03d3e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="03d3e-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="03d3e-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="03d3e-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="03d3e-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="03d3e-110">Recupera il punteggio di esposizione dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="03d3e-110">Retrieves the organizational exposure score.</span></span>

## <a name="permissions"></a><span data-ttu-id="03d3e-111">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="03d3e-111">Permissions</span></span>

<span data-ttu-id="03d3e-112">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="03d3e-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="03d3e-113">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi [Usare Microsoft Defender per le API endpoint](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="03d3e-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="03d3e-114">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="03d3e-114">Permission type</span></span> | <span data-ttu-id="03d3e-115">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="03d3e-115">Permission</span></span> | <span data-ttu-id="03d3e-116">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="03d3e-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="03d3e-117">Applicazione</span><span class="sxs-lookup"><span data-stu-id="03d3e-117">Application</span></span> | <span data-ttu-id="03d3e-118">Score.Read.All</span><span class="sxs-lookup"><span data-stu-id="03d3e-118">Score.Read.All</span></span> | <span data-ttu-id="03d3e-119">"Read Threat and Vulnerability Management score"</span><span class="sxs-lookup"><span data-stu-id="03d3e-119">'Read Threat and Vulnerability Management score'</span></span>
<span data-ttu-id="03d3e-120">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="03d3e-120">Delegated (work or school account)</span></span> | <span data-ttu-id="03d3e-121">Score.Read</span><span class="sxs-lookup"><span data-stu-id="03d3e-121">Score.Read</span></span> | <span data-ttu-id="03d3e-122">"Read Threat and Vulnerability Management score"</span><span class="sxs-lookup"><span data-stu-id="03d3e-122">'Read Threat and Vulnerability Management score'</span></span>

## <a name="http-request"></a><span data-ttu-id="03d3e-123">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="03d3e-123">HTTP request</span></span>

```
GET /api/exposureScore
```

## <a name="request-headers"></a><span data-ttu-id="03d3e-124">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="03d3e-124">Request headers</span></span>

<span data-ttu-id="03d3e-125">Name</span><span class="sxs-lookup"><span data-stu-id="03d3e-125">Name</span></span> | <span data-ttu-id="03d3e-126">Tipo</span><span class="sxs-lookup"><span data-stu-id="03d3e-126">Type</span></span> | <span data-ttu-id="03d3e-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="03d3e-127">Description</span></span>
:---|:---|:---
<span data-ttu-id="03d3e-128">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="03d3e-128">Authorization</span></span> | <span data-ttu-id="03d3e-129">Stringa</span><span class="sxs-lookup"><span data-stu-id="03d3e-129">String</span></span> | <span data-ttu-id="03d3e-130">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="03d3e-130">Bearer {token}.</span></span> <span data-ttu-id="03d3e-131">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="03d3e-131">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="03d3e-132">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="03d3e-132">Request body</span></span>

<span data-ttu-id="03d3e-133">Vuoto</span><span class="sxs-lookup"><span data-stu-id="03d3e-133">Empty</span></span>

## <a name="response"></a><span data-ttu-id="03d3e-134">Risposta</span><span class="sxs-lookup"><span data-stu-id="03d3e-134">Response</span></span>

<span data-ttu-id="03d3e-135">Se ha esito positivo, questo metodo restituisce 200 OK, con i dati di esposizione nel corpo della risposta.</span><span class="sxs-lookup"><span data-stu-id="03d3e-135">If successful, this method returns 200 OK, with the exposure data in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="03d3e-136">Esempio</span><span class="sxs-lookup"><span data-stu-id="03d3e-136">Example</span></span>

### <a name="request"></a><span data-ttu-id="03d3e-137">Richiesta</span><span class="sxs-lookup"><span data-stu-id="03d3e-137">Request</span></span>

<span data-ttu-id="03d3e-138">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="03d3e-138">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/exposureScore
```

### <a name="response"></a><span data-ttu-id="03d3e-139">Risposta</span><span class="sxs-lookup"><span data-stu-id="03d3e-139">Response</span></span>

<span data-ttu-id="03d3e-140">Ecco un esempio di risposta.</span><span class="sxs-lookup"><span data-stu-id="03d3e-140">Here is an example of the response.</span></span>

>[!NOTE]
><span data-ttu-id="03d3e-141">L'elenco delle risposte mostrato qui potrebbe essere troncato per brevità.</span><span class="sxs-lookup"><span data-stu-id="03d3e-141">The response list shown here may be truncated for brevity.</span></span> 

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#ExposureScore/$entity",
    "time": "2019-12-03T07:23:53.280499Z",
    "score": 33.491554051195706
}

```

## <a name="see-also"></a><span data-ttu-id="03d3e-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="03d3e-142">See also</span></span>

- [<span data-ttu-id="03d3e-143">Gestione delle vulnerabilità basata sui rischi & rischio</span><span class="sxs-lookup"><span data-stu-id="03d3e-143">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="03d3e-144">Punteggio di esposizione & rischio di vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="03d3e-144">Threat & Vulnerability exposure score</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-exposure-score)
