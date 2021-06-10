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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: eaef6b25e2db72149a1a1128899d8a79a38a4c60
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771022"
---
# <a name="delete-indicator-api"></a><span data-ttu-id="279be-104">API indicatore di eliminazione</span><span class="sxs-lookup"><span data-stu-id="279be-104">Delete Indicator API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="279be-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="279be-105">**Applies to:**</span></span>
- [<span data-ttu-id="279be-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="279be-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="279be-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="279be-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="279be-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="279be-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="279be-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="279be-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)  

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="279be-110">Descrizione API</span><span class="sxs-lookup"><span data-stu-id="279be-110">API description</span></span>
<span data-ttu-id="279be-111">Elimina [un'entità Indicator](ti-indicator.md) in base all'ID.</span><span class="sxs-lookup"><span data-stu-id="279be-111">Deletes an [Indicator](ti-indicator.md) entity by ID.</span></span>


## <a name="limitations"></a><span data-ttu-id="279be-112">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="279be-112">Limitations</span></span>
1. <span data-ttu-id="279be-113">I limiti di frequenza per questa API sono 100 chiamate al minuto e 1500 chiamate all'ora.</span><span class="sxs-lookup"><span data-stu-id="279be-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="279be-114">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="279be-114">Permissions</span></span>
<span data-ttu-id="279be-115">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="279be-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="279be-116">Per ulteriori informazioni, inclusa la scelta delle autorizzazioni, vedere [Introduzione](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="279be-116">To learn more, including how to choose permissions, see [Get started](apis-intro.md)</span></span>

<span data-ttu-id="279be-117">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="279be-117">Permission type</span></span> |   <span data-ttu-id="279be-118">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="279be-118">Permission</span></span>  |   <span data-ttu-id="279be-119">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="279be-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="279be-120">Applicazione</span><span class="sxs-lookup"><span data-stu-id="279be-120">Application</span></span> |   <span data-ttu-id="279be-121">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="279be-121">Ti.ReadWrite</span></span> |  <span data-ttu-id="279be-122">"Indicatori TI di lettura e scrittura"</span><span class="sxs-lookup"><span data-stu-id="279be-122">'Read and write TI Indicators'</span></span>
<span data-ttu-id="279be-123">Applicazione</span><span class="sxs-lookup"><span data-stu-id="279be-123">Application</span></span> |   <span data-ttu-id="279be-124">Ti.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="279be-124">Ti.ReadWrite.All</span></span> |  <span data-ttu-id="279be-125">"Indicatori di lettura e scrittura"</span><span class="sxs-lookup"><span data-stu-id="279be-125">'Read and write Indicators'</span></span>


## <a name="http-request"></a><span data-ttu-id="279be-126">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="279be-126">HTTP request</span></span>
```
Delete https://api.securitycenter.microsoft.com/api/indicators/{id}
```

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="request-headers"></a><span data-ttu-id="279be-127">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="279be-127">Request headers</span></span>

<span data-ttu-id="279be-128">Name</span><span class="sxs-lookup"><span data-stu-id="279be-128">Name</span></span> | <span data-ttu-id="279be-129">Tipo</span><span class="sxs-lookup"><span data-stu-id="279be-129">Type</span></span> | <span data-ttu-id="279be-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="279be-130">Description</span></span>
:---|:---|:---
<span data-ttu-id="279be-131">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="279be-131">Authorization</span></span> | <span data-ttu-id="279be-132">Stringa</span><span class="sxs-lookup"><span data-stu-id="279be-132">String</span></span> | <span data-ttu-id="279be-133">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="279be-133">Bearer {token}.</span></span> <span data-ttu-id="279be-134">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="279be-134">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="279be-135">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="279be-135">Request body</span></span>
<span data-ttu-id="279be-136">Vuoto</span><span class="sxs-lookup"><span data-stu-id="279be-136">Empty</span></span>

## <a name="response"></a><span data-ttu-id="279be-137">Risposta</span><span class="sxs-lookup"><span data-stu-id="279be-137">Response</span></span>
<span data-ttu-id="279be-138">If Indicator exist and deleted successfully - 204 OK without content.</span><span class="sxs-lookup"><span data-stu-id="279be-138">If Indicator exist and deleted successfully - 204 OK without content.</span></span>
<span data-ttu-id="279be-139">Se l'indicatore con l'ID specificato non è stato trovato - 404 Non trovato.</span><span class="sxs-lookup"><span data-stu-id="279be-139">If Indicator with the specified id was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="279be-140">Esempio</span><span class="sxs-lookup"><span data-stu-id="279be-140">Example</span></span>

<span data-ttu-id="279be-141">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="279be-141">**Request**</span></span>

<span data-ttu-id="279be-142">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="279be-142">Here is an example of the request.</span></span>

```http
DELETE https://api.securitycenter.microsoft.com/api/indicators/995
```
