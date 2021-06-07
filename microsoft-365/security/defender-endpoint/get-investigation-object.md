---
title: API dell'oggetto Get Investigation
description: Usa questa API per creare chiamate correlate al get dell'oggetto Investigation
keywords: api, api del grafico, api supportate, oggetto Investigation
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
ms.openlocfilehash: 001b8dcf4b0bfd2550f41454fc840602a6e4361f
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770134"
---
# <a name="get-investigation-api"></a><span data-ttu-id="daba5-104">Get Investigation API</span><span class="sxs-lookup"><span data-stu-id="daba5-104">Get Investigation API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="daba5-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="daba5-105">**Applies to:**</span></span>
- [<span data-ttu-id="daba5-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="daba5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="daba5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="daba5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="daba5-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="daba5-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="daba5-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="daba5-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="daba5-110">Descrizione API</span><span class="sxs-lookup"><span data-stu-id="daba5-110">API description</span></span>
<span data-ttu-id="daba5-111">Recupera un'indagine [specifica in](investigation.md) base al relativo ID.</span><span class="sxs-lookup"><span data-stu-id="daba5-111">Retrieves specific [Investigation](investigation.md) by its ID.</span></span>
<br> <span data-ttu-id="daba5-112">L'ID può essere l'ID dell'indagine o l'ID dell'avviso che attiva l'indagine.</span><span class="sxs-lookup"><span data-stu-id="daba5-112">ID can be the investigation ID or the investigation triggering alert ID.</span></span>


## <a name="limitations"></a><span data-ttu-id="daba5-113">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="daba5-113">Limitations</span></span>
1. <span data-ttu-id="daba5-114">I limiti di frequenza per questa API sono 100 chiamate al minuto e 1500 chiamate all'ora.</span><span class="sxs-lookup"><span data-stu-id="daba5-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="daba5-115">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="daba5-115">Permissions</span></span>
<span data-ttu-id="daba5-116">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="daba5-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="daba5-117">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi [Usare Microsoft Defender per le API endpoint](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="daba5-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="daba5-118">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="daba5-118">Permission type</span></span> |   <span data-ttu-id="daba5-119">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="daba5-119">Permission</span></span>  |   <span data-ttu-id="daba5-120">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="daba5-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="daba5-121">Applicazione</span><span class="sxs-lookup"><span data-stu-id="daba5-121">Application</span></span> |   <span data-ttu-id="daba5-122">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="daba5-122">Alert.Read.All</span></span> |    <span data-ttu-id="daba5-123">"Leggi tutti gli avvisi"</span><span class="sxs-lookup"><span data-stu-id="daba5-123">'Read all alerts'</span></span>
<span data-ttu-id="daba5-124">Applicazione</span><span class="sxs-lookup"><span data-stu-id="daba5-124">Application</span></span> |   <span data-ttu-id="daba5-125">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="daba5-125">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="daba5-126">"Lettura e scrittura di tutti gli avvisi"</span><span class="sxs-lookup"><span data-stu-id="daba5-126">'Read and write all alerts'</span></span>
<span data-ttu-id="daba5-127">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="daba5-127">Delegated (work or school account)</span></span> | <span data-ttu-id="daba5-128">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="daba5-128">Alert.Read</span></span> | <span data-ttu-id="daba5-129">"Avvisi di lettura"</span><span class="sxs-lookup"><span data-stu-id="daba5-129">'Read alerts'</span></span>
<span data-ttu-id="daba5-130">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="daba5-130">Delegated (work or school account)</span></span> | <span data-ttu-id="daba5-131">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="daba5-131">Alert.ReadWrite</span></span> | <span data-ttu-id="daba5-132">"Avvisi di lettura e scrittura"</span><span class="sxs-lookup"><span data-stu-id="daba5-132">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="daba5-133">Quando si ottiene un token utilizzando le credenziali utente:</span><span class="sxs-lookup"><span data-stu-id="daba5-133">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="daba5-134">L'utente deve disporre almeno dell'autorizzazione di ruolo seguente: 'Visualizza dati' (per ulteriori informazioni, vedere [Creare](user-roles.md) e gestire ruoli)</span><span class="sxs-lookup"><span data-stu-id="daba5-134">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="daba5-135">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="daba5-135">HTTP request</span></span>
```
GET https://api.securitycenter.microsoft.com/api/investigations/{id}
```

## <a name="request-headers"></a><span data-ttu-id="daba5-136">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="daba5-136">Request headers</span></span>

<span data-ttu-id="daba5-137">Name</span><span class="sxs-lookup"><span data-stu-id="daba5-137">Name</span></span> | <span data-ttu-id="daba5-138">Tipo</span><span class="sxs-lookup"><span data-stu-id="daba5-138">Type</span></span> | <span data-ttu-id="daba5-139">Descrizione</span><span class="sxs-lookup"><span data-stu-id="daba5-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="daba5-140">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="daba5-140">Authorization</span></span> | <span data-ttu-id="daba5-141">Stringa</span><span class="sxs-lookup"><span data-stu-id="daba5-141">String</span></span> | <span data-ttu-id="daba5-142">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="daba5-142">Bearer {token}.</span></span> <span data-ttu-id="daba5-143">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="daba5-143">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="daba5-144">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="daba5-144">Request body</span></span>
<span data-ttu-id="daba5-145">Vuoto</span><span class="sxs-lookup"><span data-stu-id="daba5-145">Empty</span></span>

## <a name="response"></a><span data-ttu-id="daba5-146">Risposta</span><span class="sxs-lookup"><span data-stu-id="daba5-146">Response</span></span>
<span data-ttu-id="daba5-147">Se ha esito positivo, questo metodo restituisce 200 codice di risposta Ok con [un'entità Investigations.](investigation.md)</span><span class="sxs-lookup"><span data-stu-id="daba5-147">If successful, this method returns 200, Ok response code with a [Investigations](investigation.md) entity.</span></span>

