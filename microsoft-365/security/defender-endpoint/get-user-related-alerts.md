---
title: API per ottenere avvisi correlati all'utente
description: Recupera una raccolta di avvisi relativi a un determinato ID utente usando Microsoft Defender for Endpoint.
keywords: api, api del grafico, api supportate, ottenere, utente, correlate, avvisi
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
ms.openlocfilehash: cff4530cfa4ecd6b0d918a9112e7be3c0f30209c
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166522"
---
# <a name="get-user-related-alerts-api"></a><span data-ttu-id="34b62-104">API per ottenere avvisi correlati all'utente</span><span class="sxs-lookup"><span data-stu-id="34b62-104">Get user-related alerts API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="34b62-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="34b62-105">**Applies to:**</span></span>
- [<span data-ttu-id="34b62-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="34b62-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="34b62-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="34b62-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="34b62-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="34b62-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="34b62-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="34b62-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="34b62-110">Descrizione API</span><span class="sxs-lookup"><span data-stu-id="34b62-110">API description</span></span>
<span data-ttu-id="34b62-111">Recupera una raccolta di avvisi correlati a un DETERMINATO ID utente.</span><span class="sxs-lookup"><span data-stu-id="34b62-111">Retrieves a collection of alerts related to a given user ID.</span></span>


## <a name="limitations"></a><span data-ttu-id="34b62-112">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="34b62-112">Limitations</span></span>
1. <span data-ttu-id="34b62-113">I limiti di frequenza per questa API sono 100 chiamate al minuto e 1500 chiamate all'ora.</span><span class="sxs-lookup"><span data-stu-id="34b62-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="34b62-114">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="34b62-114">Permissions</span></span>
<span data-ttu-id="34b62-115">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="34b62-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="34b62-116">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi [Usare Microsoft Defender per le API endpoint](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="34b62-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="34b62-117">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="34b62-117">Permission type</span></span> |   <span data-ttu-id="34b62-118">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="34b62-118">Permission</span></span>  |   <span data-ttu-id="34b62-119">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="34b62-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="34b62-120">Applicazione</span><span class="sxs-lookup"><span data-stu-id="34b62-120">Application</span></span> |   <span data-ttu-id="34b62-121">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="34b62-121">Alert.Read.All</span></span> |    <span data-ttu-id="34b62-122">"Leggi tutti gli avvisi"</span><span class="sxs-lookup"><span data-stu-id="34b62-122">'Read all alerts'</span></span>
<span data-ttu-id="34b62-123">Applicazione</span><span class="sxs-lookup"><span data-stu-id="34b62-123">Application</span></span> |   <span data-ttu-id="34b62-124">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="34b62-124">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="34b62-125">"Lettura e scrittura di tutti gli avvisi"</span><span class="sxs-lookup"><span data-stu-id="34b62-125">'Read and write all alerts'</span></span>
<span data-ttu-id="34b62-126">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="34b62-126">Delegated (work or school account)</span></span> | <span data-ttu-id="34b62-127">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="34b62-127">Alert.Read</span></span> | <span data-ttu-id="34b62-128">"Avvisi di lettura"</span><span class="sxs-lookup"><span data-stu-id="34b62-128">'Read alerts'</span></span>
<span data-ttu-id="34b62-129">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="34b62-129">Delegated (work or school account)</span></span> | <span data-ttu-id="34b62-130">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="34b62-130">Alert.ReadWrite</span></span> | <span data-ttu-id="34b62-131">"Avvisi di lettura e scrittura"</span><span class="sxs-lookup"><span data-stu-id="34b62-131">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="34b62-132">Quando si ottiene un token utilizzando le credenziali utente:</span><span class="sxs-lookup"><span data-stu-id="34b62-132">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="34b62-133">L'utente deve disporre almeno dell'autorizzazione di ruolo seguente: "Visualizza dati".</span><span class="sxs-lookup"><span data-stu-id="34b62-133">The user needs to have at least the following role permission: 'View Data'.</span></span> <span data-ttu-id="34b62-134">Per ulteriori informazioni, vedere [Create and manage roles](user-roles.md).</span><span class="sxs-lookup"><span data-stu-id="34b62-134">For more information, see [Create and manage roles](user-roles.md).</span></span>
>- <span data-ttu-id="34b62-135">La risposta includerà solo gli avvisi, associati ai dispositivi, a cui l'utente ha accesso, in base alle impostazioni del gruppo di dispositivi (per ulteriori informazioni, vedere [Creare](machine-groups.md) e gestire gruppi di dispositivi)</span><span class="sxs-lookup"><span data-stu-id="34b62-135">Response will include only alerts, associated with devices, that the user have access to, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="34b62-136">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="34b62-136">HTTP request</span></span>
```
GET /api/users/{id}/alerts
```

<span data-ttu-id="34b62-137">**L'ID non è l'UPN completo, ma solo il nome utente. (ad esempio, per recuperare gli avvisi user1@contoso.com usare /api/users/user1/alerts)**</span><span class="sxs-lookup"><span data-stu-id="34b62-137">**The ID is not the full UPN, but only the user name. (for example, to retrieve alerts for user1@contoso.com use /api/users/user1/alerts)**</span></span>

## <a name="request-headers"></a><span data-ttu-id="34b62-138">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="34b62-138">Request headers</span></span>

<span data-ttu-id="34b62-139">Name</span><span class="sxs-lookup"><span data-stu-id="34b62-139">Name</span></span> | <span data-ttu-id="34b62-140">Tipo</span><span class="sxs-lookup"><span data-stu-id="34b62-140">Type</span></span> | <span data-ttu-id="34b62-141">Descrizione</span><span class="sxs-lookup"><span data-stu-id="34b62-141">Description</span></span>
:---|:---|:---
<span data-ttu-id="34b62-142">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="34b62-142">Authorization</span></span> | <span data-ttu-id="34b62-143">Stringa</span><span class="sxs-lookup"><span data-stu-id="34b62-143">String</span></span> | <span data-ttu-id="34b62-144">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="34b62-144">Bearer {token}.</span></span> <span data-ttu-id="34b62-145">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="34b62-145">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="34b62-146">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="34b62-146">Request body</span></span>
<span data-ttu-id="34b62-147">Vuoto</span><span class="sxs-lookup"><span data-stu-id="34b62-147">Empty</span></span>

## <a name="response"></a><span data-ttu-id="34b62-148">Risposta</span><span class="sxs-lookup"><span data-stu-id="34b62-148">Response</span></span>
<span data-ttu-id="34b62-149">Se ha esito positivo e l'utente esiste - 200 OK.</span><span class="sxs-lookup"><span data-stu-id="34b62-149">If successful and user exists - 200 OK.</span></span> <span data-ttu-id="34b62-150">Se l'utente non esiste- 404 Non trovato.</span><span class="sxs-lookup"><span data-stu-id="34b62-150">If the user does not exist - 404 Not Found.</span></span> 


## <a name="example"></a><span data-ttu-id="34b62-151">Esempio</span><span class="sxs-lookup"><span data-stu-id="34b62-151">Example</span></span>

<span data-ttu-id="34b62-152">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="34b62-152">**Request**</span></span>

<span data-ttu-id="34b62-153">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="34b62-153">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/users/user1/alerts
```