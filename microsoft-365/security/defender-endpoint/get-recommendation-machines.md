---
title: Elencare i dispositivi in base ai suggerimenti
description: Recupera un elenco di dispositivi associati al suggerimento per la sicurezza.
keywords: api, api del grafico, api supportate, ottenere, suggerimenti per la sicurezza per dispositivi vulnerabili, gestione delle minacce e delle vulnerabilità, api di gestione delle minacce e delle vulnerabilità
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
ms.openlocfilehash: 515542f6eca208e92228a8d0b344b6013b11a148
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198270"
---
# <a name="list-devices-by-recommendation"></a><span data-ttu-id="b4f33-104">Elencare i dispositivi in base ai suggerimenti</span><span class="sxs-lookup"><span data-stu-id="b4f33-104">List devices by recommendation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b4f33-105">**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="b4f33-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="b4f33-106">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="b4f33-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b4f33-107">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="b4f33-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="b4f33-108">Recupera un elenco di dispositivi associati al suggerimento per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="b4f33-108">Retrieves a list of devices associated with the security recommendation.</span></span>

## <a name="permissions"></a><span data-ttu-id="b4f33-109">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="b4f33-109">Permissions</span></span>
<span data-ttu-id="b4f33-110">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="b4f33-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="b4f33-111">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi Usare Le API di [Microsoft Defender per endpoint](apis-intro.md) per i dettagli.</span><span class="sxs-lookup"><span data-stu-id="b4f33-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="b4f33-112">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="b4f33-112">Permission type</span></span> |   <span data-ttu-id="b4f33-113">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="b4f33-113">Permission</span></span>  |   <span data-ttu-id="b4f33-114">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="b4f33-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="b4f33-115">Applicazione</span><span class="sxs-lookup"><span data-stu-id="b4f33-115">Application</span></span> |   <span data-ttu-id="b4f33-116">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="b4f33-116">SecurityRecommendation.Read.All</span></span> |   <span data-ttu-id="b4f33-117">"Leggere le informazioni sui suggerimenti per la sicurezza per la gestione delle minacce e delle vulnerabilità"</span><span class="sxs-lookup"><span data-stu-id="b4f33-117">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="b4f33-118">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="b4f33-118">Delegated (work or school account)</span></span> | <span data-ttu-id="b4f33-119">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="b4f33-119">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="b4f33-120">"Leggere le informazioni sui suggerimenti per la sicurezza per la gestione delle minacce e delle vulnerabilità"</span><span class="sxs-lookup"><span data-stu-id="b4f33-120">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="b4f33-121">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="b4f33-121">HTTP request</span></span>
```
GET /api/recommendations/{id}/machineReferences
```

## <a name="request-headers"></a><span data-ttu-id="b4f33-122">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="b4f33-122">Request headers</span></span>

<span data-ttu-id="b4f33-123">Name</span><span class="sxs-lookup"><span data-stu-id="b4f33-123">Name</span></span> | <span data-ttu-id="b4f33-124">Tipo</span><span class="sxs-lookup"><span data-stu-id="b4f33-124">Type</span></span> | <span data-ttu-id="b4f33-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b4f33-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="b4f33-126">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="b4f33-126">Authorization</span></span> | <span data-ttu-id="b4f33-127">Stringa</span><span class="sxs-lookup"><span data-stu-id="b4f33-127">String</span></span> | <span data-ttu-id="b4f33-128">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="b4f33-128">Bearer {token}.</span></span> <span data-ttu-id="b4f33-129">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="b4f33-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="b4f33-130">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="b4f33-130">Request body</span></span>
<span data-ttu-id="b4f33-131">Vuoto</span><span class="sxs-lookup"><span data-stu-id="b4f33-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="b4f33-132">Risposta</span><span class="sxs-lookup"><span data-stu-id="b4f33-132">Response</span></span>
<span data-ttu-id="b4f33-133">Se ha esito positivo, questo metodo restituisce 200 OK con l'elenco dei dispositivi associati al suggerimento per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="b4f33-133">If successful, this method returns 200 OK with the list of devices associated with the security recommendation.</span></span>


## <a name="example"></a><span data-ttu-id="b4f33-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="b4f33-134">Example</span></span>

<span data-ttu-id="b4f33-135">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="b4f33-135">**Request**</span></span>

<span data-ttu-id="b4f33-136">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="b4f33-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/recommendations/va-_-google-_-chrome/machineReferences
```

<span data-ttu-id="b4f33-137">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="b4f33-137">**Response**</span></span>

<span data-ttu-id="b4f33-138">Ecco un esempio di risposta.</span><span class="sxs-lookup"><span data-stu-id="b4f33-138">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineReferences",
    "value": [
        {
            "id": "e058770379bc199a9c179ce52a23e16fd44fd2ee",
            "computerDnsName": "niw_pc",
            "osPlatform": "Windows10",
            "rbacGroupName": "GroupTwo"
        }
        ...
    ]
}
```

## <a name="related-topics"></a><span data-ttu-id="b4f33-139">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="b4f33-139">Related topics</span></span>
- [<span data-ttu-id="b4f33-140">Gestione delle vulnerabilità basata sui rischi & rischio</span><span class="sxs-lookup"><span data-stu-id="b4f33-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="b4f33-141">Raccomandazione per la sicurezza & rischio di vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="b4f33-141">Threat & Vulnerability security recommendation</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)
