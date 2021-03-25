---
title: Ottenere gli indicatori KPI mancanti in base all'ID software
description: Recupera gli aggiornamenti della sicurezza mancanti in base all'ID software
keywords: api, api del grafico, api supportate, ottenere, elenco, file, informazioni, ID software, api di gestione delle minacce & vulnerabilità, api mdatp tvm
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: c90854b043674a61c4996456c9d718b3c25afd1c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51197788"
---
# <a name="get-missing-kbs-by-software-id"></a><span data-ttu-id="fc60f-104">Ottenere gli indicatori KPI mancanti in base all'ID software</span><span class="sxs-lookup"><span data-stu-id="fc60f-104">Get missing KBs by software ID</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="fc60f-105">**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="fc60f-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="fc60f-106">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="fc60f-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="fc60f-107">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="fc60f-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="fc60f-108">Recupera gli indicatori KPI mancanti (aggiornamenti della sicurezza) in base all'ID software</span><span class="sxs-lookup"><span data-stu-id="fc60f-108">Retrieves missing KBs (security updates) by software ID</span></span>

## <a name="permissions"></a><span data-ttu-id="fc60f-109">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="fc60f-109">Permissions</span></span>

<span data-ttu-id="fc60f-110">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="fc60f-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="fc60f-111">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi Usare Le API di [Microsoft Defender per endpoint](apis-intro.md) per i dettagli.</span><span class="sxs-lookup"><span data-stu-id="fc60f-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="fc60f-112">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="fc60f-112">Permission type</span></span> |   <span data-ttu-id="fc60f-113">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="fc60f-113">Permission</span></span>   |   <span data-ttu-id="fc60f-114">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="fc60f-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="fc60f-115">Applicazione</span><span class="sxs-lookup"><span data-stu-id="fc60f-115">Application</span></span> |<span data-ttu-id="fc60f-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="fc60f-116">Software.Read.All</span></span> |   <span data-ttu-id="fc60f-117">"Leggere informazioni sul software di gestione delle minacce e delle vulnerabilità"</span><span class="sxs-lookup"><span data-stu-id="fc60f-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="fc60f-118">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="fc60f-118">Delegated (work or school account)</span></span> | <span data-ttu-id="fc60f-119">Software.Read</span><span class="sxs-lookup"><span data-stu-id="fc60f-119">Software.Read</span></span> |   <span data-ttu-id="fc60f-120">"Leggere informazioni sul software di gestione delle minacce e delle vulnerabilità"</span><span class="sxs-lookup"><span data-stu-id="fc60f-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="fc60f-121">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="fc60f-121">HTTP request</span></span>

```
GET /api/Software/{Id}/getmissingkbs
```

## <a name="request-header"></a><span data-ttu-id="fc60f-122">Intestazione della richiesta</span><span class="sxs-lookup"><span data-stu-id="fc60f-122">Request header</span></span>

<span data-ttu-id="fc60f-123">Nome</span><span class="sxs-lookup"><span data-stu-id="fc60f-123">Name</span></span> | <span data-ttu-id="fc60f-124">Tipo</span><span class="sxs-lookup"><span data-stu-id="fc60f-124">Type</span></span> | <span data-ttu-id="fc60f-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fc60f-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="fc60f-126">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="fc60f-126">Authorization</span></span> | <span data-ttu-id="fc60f-127">Stringa</span><span class="sxs-lookup"><span data-stu-id="fc60f-127">String</span></span> | <span data-ttu-id="fc60f-128">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="fc60f-128">Bearer {token}.</span></span> <span data-ttu-id="fc60f-129">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="fc60f-129">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="fc60f-130">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="fc60f-130">Request body</span></span>

<span data-ttu-id="fc60f-131">Vuoto</span><span class="sxs-lookup"><span data-stu-id="fc60f-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="fc60f-132">Risposta</span><span class="sxs-lookup"><span data-stu-id="fc60f-132">Response</span></span>

<span data-ttu-id="fc60f-133">Se ha esito positivo, questo metodo restituisce 200 OK, con i dati kb mancanti del software specificato nel corpo.</span><span class="sxs-lookup"><span data-stu-id="fc60f-133">If successful, this method returns 200 OK, with the specified software missing kb data in the body.</span></span>

## <a name="example"></a><span data-ttu-id="fc60f-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="fc60f-134">Example</span></span>

### <a name="request"></a><span data-ttu-id="fc60f-135">Richiesta</span><span class="sxs-lookup"><span data-stu-id="fc60f-135">Request</span></span>

<span data-ttu-id="fc60f-136">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="fc60f-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/getmissingkbs
```

### <a name="response"></a><span data-ttu-id="fc60f-137">Risposta</span><span class="sxs-lookup"><span data-stu-id="fc60f-137">Response</span></span>

<span data-ttu-id="fc60f-138">Ecco un esempio di risposta.</span><span class="sxs-lookup"><span data-stu-id="fc60f-138">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.PublicProductFixDto)",
    "value": [
         {
            "id": "4540673",
            "name": "March 2020 Security Updates",
            "productsNames": [
                "edge"
            ],
            "url": "https://catalog.update.microsoft.com/v7/site/Search.aspx?q=KB4540673",
            "machineMissedOn": 240,
            "cveAddressed": 14
         },
         ...
        ]
}
```

## <a name="related-topics"></a><span data-ttu-id="fc60f-139">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="fc60f-139">Related topics</span></span>

- [<span data-ttu-id="fc60f-140">Gestione delle vulnerabilità basata sui rischi & rischio</span><span class="sxs-lookup"><span data-stu-id="fc60f-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="fc60f-141">Threat & Vulnerability software inventory</span><span class="sxs-lookup"><span data-stu-id="fc60f-141">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
