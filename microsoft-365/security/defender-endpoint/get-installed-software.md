---
title: Ottenere il software installato
description: Recupera una raccolta di software installato correlato a un DETERMINATO ID dispositivo.
keywords: api, api del grafico, api supportate, ottenere, elenco, file, informazioni, inventario software, software installato per dispositivo, api di & gestione delle vulnerabilità delle minacce, Api tvm di Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: e13e2072ad1c18f3c6bf1abbbe95c95bb519dc3e
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841111"
---
# <a name="get-installed-software"></a><span data-ttu-id="e9690-104">Ottenere il software installato</span><span class="sxs-lookup"><span data-stu-id="e9690-104">Get installed software</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e9690-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="e9690-105">**Applies to:**</span></span>
- [<span data-ttu-id="e9690-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="e9690-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e9690-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e9690-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="e9690-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="e9690-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e9690-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="e9690-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="e9690-110">Recupera una raccolta di software installato correlato a un DETERMINATO ID dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e9690-110">Retrieves a collection of installed software related to a given device ID.</span></span>

## <a name="permissions"></a><span data-ttu-id="e9690-111">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="e9690-111">Permissions</span></span>
<span data-ttu-id="e9690-112">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="e9690-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="e9690-113">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi [Usare Microsoft Defender per le API endpoint](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="e9690-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="e9690-114">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="e9690-114">Permission type</span></span> |   <span data-ttu-id="e9690-115">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="e9690-115">Permission</span></span>  |   <span data-ttu-id="e9690-116">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="e9690-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="e9690-117">Applicazione</span><span class="sxs-lookup"><span data-stu-id="e9690-117">Application</span></span> |<span data-ttu-id="e9690-118">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="e9690-118">Software.Read.All</span></span> |    <span data-ttu-id="e9690-119">"Leggere informazioni sul software di gestione delle minacce e delle vulnerabilità"</span><span class="sxs-lookup"><span data-stu-id="e9690-119">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="e9690-120">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="e9690-120">Delegated (work or school account)</span></span> | <span data-ttu-id="e9690-121">Software.Read</span><span class="sxs-lookup"><span data-stu-id="e9690-121">Software.Read</span></span> |    <span data-ttu-id="e9690-122">"Leggere informazioni sul software di gestione delle minacce e delle vulnerabilità"</span><span class="sxs-lookup"><span data-stu-id="e9690-122">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="e9690-123">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="e9690-123">HTTP request</span></span>
```
GET /api/machines/{machineId}/software
```

## <a name="request-headers"></a><span data-ttu-id="e9690-124">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="e9690-124">Request headers</span></span>

<span data-ttu-id="e9690-125">Name</span><span class="sxs-lookup"><span data-stu-id="e9690-125">Name</span></span> | <span data-ttu-id="e9690-126">Tipo</span><span class="sxs-lookup"><span data-stu-id="e9690-126">Type</span></span> | <span data-ttu-id="e9690-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e9690-127">Description</span></span>
:---|:---|:---
<span data-ttu-id="e9690-128">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="e9690-128">Authorization</span></span> | <span data-ttu-id="e9690-129">Stringa</span><span class="sxs-lookup"><span data-stu-id="e9690-129">String</span></span> | <span data-ttu-id="e9690-130">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="e9690-130">Bearer {token}.</span></span> <span data-ttu-id="e9690-131">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="e9690-131">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="e9690-132">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="e9690-132">Request body</span></span>
<span data-ttu-id="e9690-133">Vuoto</span><span class="sxs-lookup"><span data-stu-id="e9690-133">Empty</span></span>

## <a name="response"></a><span data-ttu-id="e9690-134">Risposta</span><span class="sxs-lookup"><span data-stu-id="e9690-134">Response</span></span>
<span data-ttu-id="e9690-135">Se ha esito positivo, questo metodo restituisce 200 OK con le informazioni sul software installato nel corpo.</span><span class="sxs-lookup"><span data-stu-id="e9690-135">If successful, this method returns 200 OK with the installed software information in the body.</span></span>


## <a name="example"></a><span data-ttu-id="e9690-136">Esempio</span><span class="sxs-lookup"><span data-stu-id="e9690-136">Example</span></span>

<span data-ttu-id="e9690-137">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="e9690-137">**Request**</span></span>

<span data-ttu-id="e9690-138">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="e9690-138">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/ac233fa6208e1579620bf44207c4006ed7cc4501/software
```

<span data-ttu-id="e9690-139">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="e9690-139">**Response**</span></span>

<span data-ttu-id="e9690-140">Ecco un esempio di risposta.</span><span class="sxs-lookup"><span data-stu-id="e9690-140">Here is an example of the response.</span></span>


```
{
"@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Software",
"value": [
        {
"id": "microsoft-_-internet_explorer",
"name": "internet_explorer",
"vendor": "microsoft",
"weaknesses": 67,
"publicExploit": true,
"activeAlert": false,
"exposedMachines": 42115,
"impactScore": 46.2037163
        }
    ]
}
```

## <a name="see-also"></a><span data-ttu-id="e9690-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e9690-141">See also</span></span>

- [<span data-ttu-id="e9690-142">Gestione delle vulnerabilità basata sui rischi & rischio</span><span class="sxs-lookup"><span data-stu-id="e9690-142">Risk-based Threat & Vulnerability Management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="e9690-143">Threat & Vulnerability software inventory</span><span class="sxs-lookup"><span data-stu-id="e9690-143">Threat & Vulnerability software inventory</span></span>](/microsoft-365/security/defender-endpoint/tvm-software-inventory)
