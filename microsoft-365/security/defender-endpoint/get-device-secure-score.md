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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: dd9def688619b6079d947cb76069aa0f77d768de
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772306"
---
# <a name="get-device-secure-score"></a><span data-ttu-id="050a3-104">Ottenere punteggio di sicurezza dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="050a3-104">Get device secure score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="050a3-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="050a3-105">**Applies to:**</span></span>
- [<span data-ttu-id="050a3-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="050a3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="050a3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="050a3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="050a3-108">**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="050a3-108">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="050a3-109">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="050a3-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="050a3-110">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="050a3-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="050a3-111">Recupera il [punteggio microsoft secure per i dispositivi](tvm-microsoft-secure-score-devices.md).</span><span class="sxs-lookup"><span data-stu-id="050a3-111">Retrieves your [Microsoft Secure Score for Devices](tvm-microsoft-secure-score-devices.md).</span></span> <span data-ttu-id="050a3-112">Un punteggio microsoft sicuro più alto per i dispositivi significa che gli endpoint sono più resilienti dagli attacchi di minacce alla cybersecurity.</span><span class="sxs-lookup"><span data-stu-id="050a3-112">A higher Microsoft Secure Score for Devices means your endpoints are more resilient from cybersecurity threat attacks.</span></span> 

## <a name="permissions"></a><span data-ttu-id="050a3-113">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="050a3-113">Permissions</span></span>

<span data-ttu-id="050a3-114">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="050a3-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="050a3-115">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi Usare Le API di [Microsoft Defender per endpoint](apis-intro.md) per i dettagli.</span><span class="sxs-lookup"><span data-stu-id="050a3-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="050a3-116">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="050a3-116">Permission type</span></span> |   <span data-ttu-id="050a3-117">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="050a3-117">Permission</span></span>  |   <span data-ttu-id="050a3-118">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="050a3-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="050a3-119">Applicazione</span><span class="sxs-lookup"><span data-stu-id="050a3-119">Application</span></span> |   <span data-ttu-id="050a3-120">Score.Read.Alll</span><span class="sxs-lookup"><span data-stu-id="050a3-120">Score.Read.Alll</span></span> |   <span data-ttu-id="050a3-121">"Read Threat and Vulnerability Management score"</span><span class="sxs-lookup"><span data-stu-id="050a3-121">'Read Threat and Vulnerability Management score'</span></span>
<span data-ttu-id="050a3-122">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="050a3-122">Delegated (work or school account)</span></span> | <span data-ttu-id="050a3-123">Score.Read</span><span class="sxs-lookup"><span data-stu-id="050a3-123">Score.Read</span></span> | <span data-ttu-id="050a3-124">"Read Threat and Vulnerability Management score"</span><span class="sxs-lookup"><span data-stu-id="050a3-124">'Read Threat and Vulnerability Management score'</span></span>

## <a name="http-request"></a><span data-ttu-id="050a3-125">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="050a3-125">HTTP request</span></span>

```
GET /api/configurationScore
```

## <a name="request-headers"></a><span data-ttu-id="050a3-126">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="050a3-126">Request headers</span></span>

<span data-ttu-id="050a3-127">Name</span><span class="sxs-lookup"><span data-stu-id="050a3-127">Name</span></span> | <span data-ttu-id="050a3-128">Tipo</span><span class="sxs-lookup"><span data-stu-id="050a3-128">Type</span></span> | <span data-ttu-id="050a3-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="050a3-129">Description</span></span>
:---|:---|:---
<span data-ttu-id="050a3-130">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="050a3-130">Authorization</span></span> | <span data-ttu-id="050a3-131">Stringa</span><span class="sxs-lookup"><span data-stu-id="050a3-131">String</span></span> | <span data-ttu-id="050a3-132">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="050a3-132">Bearer {token}.</span></span> <span data-ttu-id="050a3-133">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="050a3-133">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="050a3-134">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="050a3-134">Request body</span></span>

<span data-ttu-id="050a3-135">Vuoto</span><span class="sxs-lookup"><span data-stu-id="050a3-135">Empty</span></span>

## <a name="response"></a><span data-ttu-id="050a3-136">Risposta</span><span class="sxs-lookup"><span data-stu-id="050a3-136">Response</span></span>

<span data-ttu-id="050a3-137">Se ha esito positivo, questo metodo restituisce 200 OK, con i dati del punteggio sicuro del dispositivo nel corpo della risposta.</span><span class="sxs-lookup"><span data-stu-id="050a3-137">If successful, this method returns 200 OK, with the device secure score data in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="050a3-138">Esempio</span><span class="sxs-lookup"><span data-stu-id="050a3-138">Example</span></span>

### <a name="request"></a><span data-ttu-id="050a3-139">Richiesta</span><span class="sxs-lookup"><span data-stu-id="050a3-139">Request</span></span>

<span data-ttu-id="050a3-140">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="050a3-140">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/configurationScore
```

### <a name="response"></a><span data-ttu-id="050a3-141">Risposta</span><span class="sxs-lookup"><span data-stu-id="050a3-141">Response</span></span>

<span data-ttu-id="050a3-142">Ecco un esempio di risposta.</span><span class="sxs-lookup"><span data-stu-id="050a3-142">Here is an example of the response.</span></span>

>[!NOTE]
><span data-ttu-id="050a3-143">L'elenco delle risposte mostrato qui potrebbe essere troncato per brevità.</span><span class="sxs-lookup"><span data-stu-id="050a3-143">The response list shown here may be truncated for brevity.</span></span> 

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#ConfigurationScore/$entity",
    "time": "2019-12-03T09:15:58.1665846Z",
    "score": 340
}
```

## <a name="see-also"></a><span data-ttu-id="050a3-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="050a3-144">See also</span></span>

- [<span data-ttu-id="050a3-145">Query OData con Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="050a3-145">OData queries with Microsoft Defender for Endpoint</span></span>](exposed-apis-odata-samples.md)
