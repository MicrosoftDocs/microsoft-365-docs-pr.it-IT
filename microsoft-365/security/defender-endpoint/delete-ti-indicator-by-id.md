---
title: API indicatore di eliminazione.
description: Scopri come usare l'API dell'indicatore di eliminazione per eliminare un'entità Indicatore in base all'ID in Microsoft Defender per Endpoint.
keywords: api, api pubbliche, api supportate, eliminare, indicatore ti, entità, id
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
ms.technology: mde
ms.openlocfilehash: 1305be897dff6932713cf294eb4e5cd53692681c
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167105"
---
# <a name="delete-indicator-api"></a><span data-ttu-id="767d9-104">API indicatore di eliminazione</span><span class="sxs-lookup"><span data-stu-id="767d9-104">Delete Indicator API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="767d9-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="767d9-105">**Applies to:**</span></span>
- [<span data-ttu-id="767d9-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="767d9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="767d9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="767d9-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="767d9-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="767d9-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="767d9-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="767d9-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)  

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="767d9-110">Descrizione API</span><span class="sxs-lookup"><span data-stu-id="767d9-110">API description</span></span>
<span data-ttu-id="767d9-111">Elimina [un'entità Indicator](ti-indicator.md) in base all'ID.</span><span class="sxs-lookup"><span data-stu-id="767d9-111">Deletes an [Indicator](ti-indicator.md) entity by ID.</span></span>


## <a name="limitations"></a><span data-ttu-id="767d9-112">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="767d9-112">Limitations</span></span>
1. <span data-ttu-id="767d9-113">I limiti di frequenza per questa API sono 100 chiamate al minuto e 1500 chiamate all'ora.</span><span class="sxs-lookup"><span data-stu-id="767d9-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="767d9-114">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="767d9-114">Permissions</span></span>
<span data-ttu-id="767d9-115">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="767d9-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="767d9-116">Per ulteriori informazioni, inclusa la scelta delle autorizzazioni, vedere [Introduzione](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="767d9-116">To learn more, including how to choose permissions, see [Get started](apis-intro.md)</span></span>

<span data-ttu-id="767d9-117">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="767d9-117">Permission type</span></span> |   <span data-ttu-id="767d9-118">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="767d9-118">Permission</span></span>  |   <span data-ttu-id="767d9-119">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="767d9-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="767d9-120">Applicazione</span><span class="sxs-lookup"><span data-stu-id="767d9-120">Application</span></span> |   <span data-ttu-id="767d9-121">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="767d9-121">Ti.ReadWrite</span></span> |  <span data-ttu-id="767d9-122">"Indicatori TI di lettura e scrittura"</span><span class="sxs-lookup"><span data-stu-id="767d9-122">'Read and write TI Indicators'</span></span>
<span data-ttu-id="767d9-123">Applicazione</span><span class="sxs-lookup"><span data-stu-id="767d9-123">Application</span></span> |   <span data-ttu-id="767d9-124">Ti.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="767d9-124">Ti.ReadWrite.All</span></span> |  <span data-ttu-id="767d9-125">"Indicatori di lettura e scrittura"</span><span class="sxs-lookup"><span data-stu-id="767d9-125">'Read and write Indicators'</span></span>


## <a name="http-request"></a><span data-ttu-id="767d9-126">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="767d9-126">HTTP request</span></span>
```
Delete https://api.securitycenter.microsoft.com/api/indicators/{id}
```

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="request-headers"></a><span data-ttu-id="767d9-127">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="767d9-127">Request headers</span></span>

<span data-ttu-id="767d9-128">Name</span><span class="sxs-lookup"><span data-stu-id="767d9-128">Name</span></span> | <span data-ttu-id="767d9-129">Tipo</span><span class="sxs-lookup"><span data-stu-id="767d9-129">Type</span></span> | <span data-ttu-id="767d9-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="767d9-130">Description</span></span>
:---|:---|:---
<span data-ttu-id="767d9-131">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="767d9-131">Authorization</span></span> | <span data-ttu-id="767d9-132">Stringa</span><span class="sxs-lookup"><span data-stu-id="767d9-132">String</span></span> | <span data-ttu-id="767d9-133">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="767d9-133">Bearer {token}.</span></span> <span data-ttu-id="767d9-134">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="767d9-134">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="767d9-135">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="767d9-135">Request body</span></span>
<span data-ttu-id="767d9-136">Vuoto</span><span class="sxs-lookup"><span data-stu-id="767d9-136">Empty</span></span>

## <a name="response"></a><span data-ttu-id="767d9-137">Risposta</span><span class="sxs-lookup"><span data-stu-id="767d9-137">Response</span></span>
<span data-ttu-id="767d9-138">If Indicator exist and deleted successfully - 204 OK without content.</span><span class="sxs-lookup"><span data-stu-id="767d9-138">If Indicator exist and deleted successfully - 204 OK without content.</span></span>
<span data-ttu-id="767d9-139">Se l'indicatore con l'ID specificato non è stato trovato - 404 Non trovato.</span><span class="sxs-lookup"><span data-stu-id="767d9-139">If Indicator with the specified id was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="767d9-140">Esempio</span><span class="sxs-lookup"><span data-stu-id="767d9-140">Example</span></span>

<span data-ttu-id="767d9-141">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="767d9-141">**Request**</span></span>

<span data-ttu-id="767d9-142">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="767d9-142">Here is an example of the request.</span></span>

```http
DELETE https://api.securitycenter.microsoft.com/api/indicators/995
```
