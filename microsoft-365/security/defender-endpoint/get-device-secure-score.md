---
title: Ottenere punteggio di sicurezza dei dispositivi
description: Recupera il punteggio di sicurezza del dispositivo dell'organizzazione.
keywords: api, api del grafico, api supportate, ottenere, avvisi, recenti
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
ms.technology: mde
ms.openlocfilehash: db4682d0d2fccd7504eb46d9099a9783408cfb73
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51570937"
---
# <a name="get-device-secure-score"></a><span data-ttu-id="46706-104">Ottenere punteggio di sicurezza dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="46706-104">Get device secure score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="46706-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="46706-105">**Applies to:**</span></span>
- [<span data-ttu-id="46706-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="46706-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="46706-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="46706-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="46706-108">**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="46706-108">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="46706-109">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="46706-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="46706-110">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="46706-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="46706-111">Recupera il [punteggio microsoft secure per i dispositivi](tvm-microsoft-secure-score-devices.md).</span><span class="sxs-lookup"><span data-stu-id="46706-111">Retrieves your [Microsoft Secure Score for Devices](tvm-microsoft-secure-score-devices.md).</span></span> <span data-ttu-id="46706-112">Un punteggio microsoft sicuro più alto per i dispositivi significa che gli endpoint sono più resilienti dagli attacchi di minacce alla cybersecurity.</span><span class="sxs-lookup"><span data-stu-id="46706-112">A higher Microsoft Secure Score for Devices means your endpoints are more resilient from cybersecurity threat attacks.</span></span> 

## <a name="permissions"></a><span data-ttu-id="46706-113">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="46706-113">Permissions</span></span>

<span data-ttu-id="46706-114">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="46706-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="46706-115">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi Usare Le API di [Microsoft Defender per endpoint](apis-intro.md) per i dettagli.</span><span class="sxs-lookup"><span data-stu-id="46706-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="46706-116">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="46706-116">Permission type</span></span> |   <span data-ttu-id="46706-117">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="46706-117">Permission</span></span>  |   <span data-ttu-id="46706-118">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="46706-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="46706-119">Applicazione</span><span class="sxs-lookup"><span data-stu-id="46706-119">Application</span></span> |   <span data-ttu-id="46706-120">Score.Read.Alll</span><span class="sxs-lookup"><span data-stu-id="46706-120">Score.Read.Alll</span></span> |   <span data-ttu-id="46706-121">"Read Threat and Vulnerability Management score"</span><span class="sxs-lookup"><span data-stu-id="46706-121">'Read Threat and Vulnerability Management score'</span></span>
<span data-ttu-id="46706-122">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="46706-122">Delegated (work or school account)</span></span> | <span data-ttu-id="46706-123">Score.Read</span><span class="sxs-lookup"><span data-stu-id="46706-123">Score.Read</span></span> | <span data-ttu-id="46706-124">"Read Threat and Vulnerability Management score"</span><span class="sxs-lookup"><span data-stu-id="46706-124">'Read Threat and Vulnerability Management score'</span></span>

## <a name="http-request"></a><span data-ttu-id="46706-125">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="46706-125">HTTP request</span></span>

```
GET /api/configurationScore
```

## <a name="request-headers"></a><span data-ttu-id="46706-126">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="46706-126">Request headers</span></span>

<span data-ttu-id="46706-127">Name</span><span class="sxs-lookup"><span data-stu-id="46706-127">Name</span></span> | <span data-ttu-id="46706-128">Tipo</span><span class="sxs-lookup"><span data-stu-id="46706-128">Type</span></span> | <span data-ttu-id="46706-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="46706-129">Description</span></span>
:---|:---|:---
<span data-ttu-id="46706-130">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="46706-130">Authorization</span></span> | <span data-ttu-id="46706-131">Stringa</span><span class="sxs-lookup"><span data-stu-id="46706-131">String</span></span> | <span data-ttu-id="46706-132">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="46706-132">Bearer {token}.</span></span> <span data-ttu-id="46706-133">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="46706-133">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="46706-134">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="46706-134">Request body</span></span>

<span data-ttu-id="46706-135">Vuoto</span><span class="sxs-lookup"><span data-stu-id="46706-135">Empty</span></span>

## <a name="response"></a><span data-ttu-id="46706-136">Risposta</span><span class="sxs-lookup"><span data-stu-id="46706-136">Response</span></span>

<span data-ttu-id="46706-137">Se ha esito positivo, questo metodo restituisce 200 OK, con i dati del punteggio sicuro del dispositivo nel corpo della risposta.</span><span class="sxs-lookup"><span data-stu-id="46706-137">If successful, this method returns 200 OK, with the device secure score data in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="46706-138">Esempio</span><span class="sxs-lookup"><span data-stu-id="46706-138">Example</span></span>

### <a name="request"></a><span data-ttu-id="46706-139">Richiesta</span><span class="sxs-lookup"><span data-stu-id="46706-139">Request</span></span>

<span data-ttu-id="46706-140">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="46706-140">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/configurationScore
```

### <a name="response"></a><span data-ttu-id="46706-141">Risposta</span><span class="sxs-lookup"><span data-stu-id="46706-141">Response</span></span>

<span data-ttu-id="46706-142">Ecco un esempio di risposta.</span><span class="sxs-lookup"><span data-stu-id="46706-142">Here is an example of the response.</span></span>

>[!NOTE]
><span data-ttu-id="46706-143">L'elenco delle risposte mostrato qui potrebbe essere troncato per brevità.</span><span class="sxs-lookup"><span data-stu-id="46706-143">The response list shown here may be truncated for brevity.</span></span> 

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#ConfigurationScore/$entity",
    "time": "2019-12-03T09:15:58.1665846Z",
    "score": 340
}
```

## <a name="see-also"></a><span data-ttu-id="46706-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="46706-144">See also</span></span>

- [<span data-ttu-id="46706-145">Query OData con Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="46706-145">OData queries with Microsoft Defender for Endpoint</span></span>](exposed-apis-odata-samples.md)
