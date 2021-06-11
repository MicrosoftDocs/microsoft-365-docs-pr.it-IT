---
title: Ottenere gli indicatori KPI mancanti in base all'ID dispositivo
description: Recupera gli aggiornamenti di sicurezza mancanti in base all'ID dispositivo
keywords: api, api del grafico, api supportate, ottenere, elenco, file, informazioni, ID dispositivo, api & gestione delle vulnerabilità minacce, Api di Microsoft Defender per Endpoint tvm
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 63400295061cd7adc58a4ddebf73f4c82b0cc969
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845235"
---
# <a name="get-missing-kbs-by-device-id"></a><span data-ttu-id="e6f80-104">Ottenere gli indicatori KPI mancanti in base all'ID dispositivo</span><span class="sxs-lookup"><span data-stu-id="e6f80-104">Get missing KBs by device ID</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e6f80-105">**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="e6f80-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="e6f80-106">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="e6f80-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e6f80-107">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="e6f80-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="e6f80-108">Recupera gli indicatori KPI mancanti (aggiornamenti della sicurezza) in base all'ID dispositivo</span><span class="sxs-lookup"><span data-stu-id="e6f80-108">Retrieves missing KBs (security updates) by device ID</span></span>

## <a name="http-request"></a><span data-ttu-id="e6f80-109">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="e6f80-109">HTTP request</span></span>

```
GET /api/machines/{machineId}/getmissingkbs
```

## <a name="request-header"></a><span data-ttu-id="e6f80-110">Intestazione della richiesta</span><span class="sxs-lookup"><span data-stu-id="e6f80-110">Request header</span></span>

<span data-ttu-id="e6f80-111">Nome</span><span class="sxs-lookup"><span data-stu-id="e6f80-111">Name</span></span> | <span data-ttu-id="e6f80-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="e6f80-112">Type</span></span> | <span data-ttu-id="e6f80-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e6f80-113">Description</span></span>
:---|:---|:---
<span data-ttu-id="e6f80-114">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="e6f80-114">Authorization</span></span> | <span data-ttu-id="e6f80-115">Stringa</span><span class="sxs-lookup"><span data-stu-id="e6f80-115">String</span></span> | <span data-ttu-id="e6f80-116">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="e6f80-116">Bearer {token}.</span></span> <span data-ttu-id="e6f80-117">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="e6f80-117">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="e6f80-118">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="e6f80-118">Request body</span></span>

<span data-ttu-id="e6f80-119">Vuoto</span><span class="sxs-lookup"><span data-stu-id="e6f80-119">Empty</span></span>

## <a name="response"></a><span data-ttu-id="e6f80-120">Risposta</span><span class="sxs-lookup"><span data-stu-id="e6f80-120">Response</span></span>

<span data-ttu-id="e6f80-121">Se ha esito positivo, questo metodo restituisce 200 OK, con i dati kb mancanti nel dispositivo specificato nel corpo.</span><span class="sxs-lookup"><span data-stu-id="e6f80-121">If successful, this method returns 200 OK, with the specified device missing kb data in the body.</span></span>

## <a name="example"></a><span data-ttu-id="e6f80-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="e6f80-122">Example</span></span>

### <a name="request"></a><span data-ttu-id="e6f80-123">Richiesta</span><span class="sxs-lookup"><span data-stu-id="e6f80-123">Request</span></span>

<span data-ttu-id="e6f80-124">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="e6f80-124">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/machines/2339ad14a01bd0299afb93dfa2550136057bff96/getmissingkbs 
```

### <a name="response"></a><span data-ttu-id="e6f80-125">Risposta</span><span class="sxs-lookup"><span data-stu-id="e6f80-125">Response</span></span>

<span data-ttu-id="e6f80-126">Ecco un esempio di risposta.</span><span class="sxs-lookup"><span data-stu-id="e6f80-126">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.PublicProductFixDto)",
    "value": [
        {
            "id": "4540673",
            "name": "March 2020 Security Updates",
            "productsNames": [
                "windows_10",
                "edge",
                "internet_explorer"
            ],
            "url": "https://catalog.update.microsoft.com/v7/site/Search.aspx?q=KB4540673",
            "machineMissedOn": 1,
            "cveAddressed": 97
        },
         ...
        ]
}
```

## <a name="related-topics"></a><span data-ttu-id="e6f80-127">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="e6f80-127">Related topics</span></span>

- [<span data-ttu-id="e6f80-128">Gestione delle vulnerabilità basata sui rischi & rischio</span><span class="sxs-lookup"><span data-stu-id="e6f80-128">Risk-based Threat & Vulnerability Management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="e6f80-129">Threat & Vulnerability software inventory</span><span class="sxs-lookup"><span data-stu-id="e6f80-129">Threat & Vulnerability software inventory</span></span>](/microsoft-365/security/defender-endpoint/tvm-software-inventory)
