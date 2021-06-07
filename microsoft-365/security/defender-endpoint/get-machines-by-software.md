---
title: Elencare i dispositivi in base al software
description: Recuperare un elenco di dispositivi in cui è installato questo software.
keywords: api, api del grafico, api supportate, ottenere, elencare i dispositivi, elenco dei dispositivi, elencare i dispositivi in base al software, Api di Microsoft Defender for Endpoint tvm
search.product: eADQiWindows 10XVcnh
ms.prod: w10
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
ms.openlocfilehash: e1adf28823d6b86417c32578a89480958946c50d
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770561"
---
# <a name="list-devices-by-software"></a><span data-ttu-id="2f52b-104">Elencare i dispositivi in base al software</span><span class="sxs-lookup"><span data-stu-id="2f52b-104">List devices by software</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2f52b-105">**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="2f52b-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="2f52b-106">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="2f52b-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2f52b-107">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="2f52b-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="2f52b-108">Recuperare un elenco di riferimenti ai dispositivi in cui è installato questo software.</span><span class="sxs-lookup"><span data-stu-id="2f52b-108">Retrieve a list of device references that has this software installed.</span></span>

## <a name="permissions"></a><span data-ttu-id="2f52b-109">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="2f52b-109">Permissions</span></span>
<span data-ttu-id="2f52b-110">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="2f52b-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="2f52b-111">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi Usare Le API di [Microsoft Defender per endpoint](apis-intro.md) per i dettagli.</span><span class="sxs-lookup"><span data-stu-id="2f52b-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="2f52b-112">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="2f52b-112">Permission type</span></span> |   <span data-ttu-id="2f52b-113">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="2f52b-113">Permission</span></span>  |   <span data-ttu-id="2f52b-114">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="2f52b-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="2f52b-115">Applicazione</span><span class="sxs-lookup"><span data-stu-id="2f52b-115">Application</span></span> | <span data-ttu-id="2f52b-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="2f52b-116">Software.Read.All</span></span> | <span data-ttu-id="2f52b-117">"Leggere informazioni sul software di gestione delle minacce e delle vulnerabilità"</span><span class="sxs-lookup"><span data-stu-id="2f52b-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="2f52b-118">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="2f52b-118">Delegated (work or school account)</span></span> | <span data-ttu-id="2f52b-119">Software.Read</span><span class="sxs-lookup"><span data-stu-id="2f52b-119">Software.Read</span></span> | <span data-ttu-id="2f52b-120">"Leggere informazioni sul software di gestione delle minacce e delle vulnerabilità"</span><span class="sxs-lookup"><span data-stu-id="2f52b-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="2f52b-121">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="2f52b-121">HTTP request</span></span>
```
GET /api/Software/{Id}/machineReferences 
```

## <a name="request-headers"></a><span data-ttu-id="2f52b-122">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="2f52b-122">Request headers</span></span>

| <span data-ttu-id="2f52b-123">Name</span><span class="sxs-lookup"><span data-stu-id="2f52b-123">Name</span></span>        | <span data-ttu-id="2f52b-124">Tipo</span><span class="sxs-lookup"><span data-stu-id="2f52b-124">Type</span></span> | <span data-ttu-id="2f52b-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2f52b-125">Description</span></span>
|:--------------|:-------|:--------------|
| <span data-ttu-id="2f52b-126">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="2f52b-126">Authorization</span></span> | <span data-ttu-id="2f52b-127">Stringa</span><span class="sxs-lookup"><span data-stu-id="2f52b-127">String</span></span> | <span data-ttu-id="2f52b-128">Bearer {token}. **Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="2f52b-128">Bearer {token}.**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="2f52b-129">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="2f52b-129">Request body</span></span>
<span data-ttu-id="2f52b-130">Vuoto</span><span class="sxs-lookup"><span data-stu-id="2f52b-130">Empty</span></span>

## <a name="response"></a><span data-ttu-id="2f52b-131">Risposta</span><span class="sxs-lookup"><span data-stu-id="2f52b-131">Response</span></span>
<span data-ttu-id="2f52b-132">Se ha esito positivo, questo metodo restituisce 200 OK e un elenco di dispositivi con il software installato nel corpo.</span><span class="sxs-lookup"><span data-stu-id="2f52b-132">If successful, this method returns 200 OK and a list of devices with the software installed in the body.</span></span> 


## <a name="example"></a><span data-ttu-id="2f52b-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="2f52b-133">Example</span></span>

<span data-ttu-id="2f52b-134">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="2f52b-134">**Request**</span></span>

<span data-ttu-id="2f52b-135">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="2f52b-135">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/machineReferences
```

<span data-ttu-id="2f52b-136">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="2f52b-136">**Response**</span></span>

<span data-ttu-id="2f52b-137">Ecco un esempio di risposta.</span><span class="sxs-lookup"><span data-stu-id="2f52b-137">Here is an example of the response.</span></span>

```json

{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineReferences",
    "value": [
        {
            "id": "7c7e1896fa39efb0a32a2cf421d837af1b9bf762",
            "computerDnsName": "dave_desktop",
            "osPlatform": "Windows10",
            "rbacGroupName": "GroupTwo"
        },
        {
            "id": "7d5cc2e7c305e4a0a290392abf6707f9888fda0d",
            "computerDnsName": "jane_PC",
            "osPlatform": "Windows10",
            "rbacGroupName": "GroupTwo"
        }
        ...
    ]
}
```

## <a name="related-topics"></a><span data-ttu-id="2f52b-138">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="2f52b-138">Related topics</span></span>
- [<span data-ttu-id="2f52b-139">Gestione delle vulnerabilità basata sui rischi & rischio</span><span class="sxs-lookup"><span data-stu-id="2f52b-139">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="2f52b-140">Threat & Vulnerability software inventory</span><span class="sxs-lookup"><span data-stu-id="2f52b-140">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
