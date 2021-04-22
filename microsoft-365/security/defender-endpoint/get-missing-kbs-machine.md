---
title: Ottenere gli indicatori KPI mancanti in base all'ID dispositivo
description: Recupera gli aggiornamenti di sicurezza mancanti in base all'ID dispositivo
keywords: api, api del grafico, api supportate, ottenere, elenco, file, informazioni, ID dispositivo, api di gestione delle minacce & vulnerabilità, Api di Microsoft Defender per Endpoint tvm
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
ms.openlocfilehash: aa22b90b95788d9f5a65d54c7a335a2e0f4c3091
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933578"
---
# <a name="get-missing-kbs-by-device-id"></a><span data-ttu-id="ee754-104">Ottenere gli indicatori KPI mancanti in base all'ID dispositivo</span><span class="sxs-lookup"><span data-stu-id="ee754-104">Get missing KBs by device ID</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ee754-105">**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="ee754-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="ee754-106">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="ee754-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ee754-107">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="ee754-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="ee754-108">Recupera gli indicatori KPI mancanti (aggiornamenti della sicurezza) in base all'ID dispositivo</span><span class="sxs-lookup"><span data-stu-id="ee754-108">Retrieves missing KBs (security updates) by device ID</span></span>

## <a name="http-request"></a><span data-ttu-id="ee754-109">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="ee754-109">HTTP request</span></span>

```
GET /api/machines/{machineId}/getmissingkbs
```

## <a name="request-header"></a><span data-ttu-id="ee754-110">Intestazione della richiesta</span><span class="sxs-lookup"><span data-stu-id="ee754-110">Request header</span></span>

<span data-ttu-id="ee754-111">Nome</span><span class="sxs-lookup"><span data-stu-id="ee754-111">Name</span></span> | <span data-ttu-id="ee754-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="ee754-112">Type</span></span> | <span data-ttu-id="ee754-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ee754-113">Description</span></span>
:---|:---|:---
<span data-ttu-id="ee754-114">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="ee754-114">Authorization</span></span> | <span data-ttu-id="ee754-115">Stringa</span><span class="sxs-lookup"><span data-stu-id="ee754-115">String</span></span> | <span data-ttu-id="ee754-116">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="ee754-116">Bearer {token}.</span></span> <span data-ttu-id="ee754-117">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="ee754-117">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="ee754-118">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="ee754-118">Request body</span></span>

<span data-ttu-id="ee754-119">Vuoto</span><span class="sxs-lookup"><span data-stu-id="ee754-119">Empty</span></span>

## <a name="response"></a><span data-ttu-id="ee754-120">Risposta</span><span class="sxs-lookup"><span data-stu-id="ee754-120">Response</span></span>

<span data-ttu-id="ee754-121">Se ha esito positivo, questo metodo restituisce 200 OK, con i dati kb mancanti nel dispositivo specificato nel corpo.</span><span class="sxs-lookup"><span data-stu-id="ee754-121">If successful, this method returns 200 OK, with the specified device missing kb data in the body.</span></span>

## <a name="example"></a><span data-ttu-id="ee754-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="ee754-122">Example</span></span>

### <a name="request"></a><span data-ttu-id="ee754-123">Richiesta</span><span class="sxs-lookup"><span data-stu-id="ee754-123">Request</span></span>

<span data-ttu-id="ee754-124">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="ee754-124">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/machines/2339ad14a01bd0299afb93dfa2550136057bff96/getmissingkbs 
```

### <a name="response"></a><span data-ttu-id="ee754-125">Risposta</span><span class="sxs-lookup"><span data-stu-id="ee754-125">Response</span></span>

<span data-ttu-id="ee754-126">Ecco un esempio di risposta.</span><span class="sxs-lookup"><span data-stu-id="ee754-126">Here is an example of the response.</span></span>


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

## <a name="related-topics"></a><span data-ttu-id="ee754-127">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="ee754-127">Related topics</span></span>

- [<span data-ttu-id="ee754-128">Gestione delle vulnerabilità basata sui rischi & rischio</span><span class="sxs-lookup"><span data-stu-id="ee754-128">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="ee754-129">Threat & Vulnerability software inventory</span><span class="sxs-lookup"><span data-stu-id="ee754-129">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
