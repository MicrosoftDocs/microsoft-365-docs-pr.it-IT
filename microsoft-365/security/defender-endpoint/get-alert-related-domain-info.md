---
title: Ottenere informazioni sui domini correlati agli avvisi
description: Recupera tutti i domini correlati a un avviso specifico usando Microsoft Defender for Endpoint.
keywords: api, api del grafico, api supportate, ottenere informazioni sugli avvisi, informazioni sugli avvisi, dominio correlato
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: a5f3db65b42d8dc98c11f2ef2c3c5d509340e386
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771262"
---
# <a name="get-alert-related-domain-information-api"></a><span data-ttu-id="a1801-104">API per ottenere informazioni sul dominio correlate agli avvisi</span><span class="sxs-lookup"><span data-stu-id="a1801-104">Get alert related domain information API</span></span>

<span data-ttu-id="a1801-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="a1801-105">**Applies to:**</span></span> 
- [<span data-ttu-id="a1801-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="a1801-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

- <span data-ttu-id="a1801-107">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="a1801-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a1801-108">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="a1801-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="a1801-109">Descrizione API</span><span class="sxs-lookup"><span data-stu-id="a1801-109">API description</span></span>
<span data-ttu-id="a1801-110">Recupera tutti i domini correlati a un avviso specifico.</span><span class="sxs-lookup"><span data-stu-id="a1801-110">Retrieves all domains related to a specific alert.</span></span>


## <a name="limitations"></a><span data-ttu-id="a1801-111">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="a1801-111">Limitations</span></span>
1. <span data-ttu-id="a1801-112">È possibile eseguire query sugli avvisi aggiornati per l'ultimo aggiornamento in base al periodo di conservazione configurato.</span><span class="sxs-lookup"><span data-stu-id="a1801-112">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="a1801-113">I limiti di frequenza per questa API sono 100 chiamate al minuto e 1500 chiamate all'ora.</span><span class="sxs-lookup"><span data-stu-id="a1801-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="a1801-114">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="a1801-114">Permissions</span></span>
<span data-ttu-id="a1801-115">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="a1801-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="a1801-116">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi [Usare Microsoft Defender per le API endpoint](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="a1801-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="a1801-117">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="a1801-117">Permission type</span></span> | <span data-ttu-id="a1801-118">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="a1801-118">Permission</span></span> | <span data-ttu-id="a1801-119">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="a1801-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="a1801-120">Applicazione</span><span class="sxs-lookup"><span data-stu-id="a1801-120">Application</span></span> | <span data-ttu-id="a1801-121">URL. Read.All</span><span class="sxs-lookup"><span data-stu-id="a1801-121">URL.Read.All</span></span> | <span data-ttu-id="a1801-122">"Leggi URL"</span><span class="sxs-lookup"><span data-stu-id="a1801-122">'Read URLs'</span></span>
<span data-ttu-id="a1801-123">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="a1801-123">Delegated (work or school account)</span></span> | <span data-ttu-id="a1801-124">URL. Read.All</span><span class="sxs-lookup"><span data-stu-id="a1801-124">URL.Read.All</span></span> | <span data-ttu-id="a1801-125">"Leggi URL"</span><span class="sxs-lookup"><span data-stu-id="a1801-125">'Read URLs'</span></span>

>[!Note]
> <span data-ttu-id="a1801-126">Quando si ottiene un token utilizzando le credenziali utente:</span><span class="sxs-lookup"><span data-stu-id="a1801-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="a1801-127">L'utente deve disporre almeno dell'autorizzazione di ruolo seguente: 'Visualizza dati' (per ulteriori informazioni, vedere [Creare](user-roles.md) e gestire ruoli)</span><span class="sxs-lookup"><span data-stu-id="a1801-127">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="a1801-128">L'utente deve avere accesso al dispositivo associato all'avviso, in base alle impostazioni del gruppo di dispositivi (per ulteriori informazioni, vedere [Creare](machine-groups.md) e gestire gruppi di dispositivi)</span><span class="sxs-lookup"><span data-stu-id="a1801-128">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="a1801-129">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="a1801-129">HTTP request</span></span>
```
GET /api/alerts/{id}/domains
```

## <a name="request-headers"></a><span data-ttu-id="a1801-130">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="a1801-130">Request headers</span></span>

<span data-ttu-id="a1801-131">Name</span><span class="sxs-lookup"><span data-stu-id="a1801-131">Name</span></span> | <span data-ttu-id="a1801-132">Tipo</span><span class="sxs-lookup"><span data-stu-id="a1801-132">Type</span></span> | <span data-ttu-id="a1801-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a1801-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="a1801-134">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="a1801-134">Authorization</span></span> | <span data-ttu-id="a1801-135">Stringa</span><span class="sxs-lookup"><span data-stu-id="a1801-135">String</span></span> | <span data-ttu-id="a1801-136">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="a1801-136">Bearer {token}.</span></span> <span data-ttu-id="a1801-137">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="a1801-137">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="a1801-138">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="a1801-138">Request body</span></span>
<span data-ttu-id="a1801-139">Vuoto</span><span class="sxs-lookup"><span data-stu-id="a1801-139">Empty</span></span>

## <a name="response"></a><span data-ttu-id="a1801-140">Risposta</span><span class="sxs-lookup"><span data-stu-id="a1801-140">Response</span></span>
<span data-ttu-id="a1801-141">Se l'operazione ha esito positivo e l'avviso e il dominio esistono- 200 OK.</span><span class="sxs-lookup"><span data-stu-id="a1801-141">If successful and alert and domain exist - 200 OK.</span></span> <span data-ttu-id="a1801-142">Se l'avviso non viene trovato - 404 Non trovato.</span><span class="sxs-lookup"><span data-stu-id="a1801-142">If alert not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="a1801-143">Esempio</span><span class="sxs-lookup"><span data-stu-id="a1801-143">Example</span></span>

<span data-ttu-id="a1801-144">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="a1801-144">**Request**</span></span>

<span data-ttu-id="a1801-145">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="a1801-145">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/alerts/636688558380765161_2136280442/domains
```

<span data-ttu-id="a1801-146">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="a1801-146">**Response**</span></span>

<span data-ttu-id="a1801-147">Ecco un esempio di risposta.</span><span class="sxs-lookup"><span data-stu-id="a1801-147">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/$metadata#Domains",
    "value": [
        {
            "host": "www.example.com"
        },
        {
            "host": "www.example2.com"
        }
        ...
    ]
}

```
