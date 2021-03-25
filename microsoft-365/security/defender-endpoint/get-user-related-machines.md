---
title: API Per ottenere i computer correlati agli utenti
description: Scopri come usare l'API Get user-related machines per recuperare una raccolta di dispositivi correlati a un ID utente in Microsoft Defender for Endpoint.
keywords: api, api del grafico, api supportate, ottenere, utente, avvisi correlati all'utente
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
ms.openlocfilehash: 135dc1d76a1a90cd7fffba0638211d716865cb0c
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166530"
---
# <a name="get-user-related-machines-api"></a><span data-ttu-id="b516b-104">API Per ottenere i computer correlati agli utenti</span><span class="sxs-lookup"><span data-stu-id="b516b-104">Get user-related machines API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b516b-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="b516b-105">**Applies to:**</span></span>
- [<span data-ttu-id="b516b-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="b516b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b516b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b516b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="b516b-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="b516b-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b516b-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="b516b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="b516b-110">Descrizione API</span><span class="sxs-lookup"><span data-stu-id="b516b-110">API description</span></span>
<span data-ttu-id="b516b-111">Recupera una raccolta di dispositivi correlati a un DETERMINATO ID utente.</span><span class="sxs-lookup"><span data-stu-id="b516b-111">Retrieves a collection of devices related to a given user ID.</span></span>


## <a name="limitations"></a><span data-ttu-id="b516b-112">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="b516b-112">Limitations</span></span>
1. <span data-ttu-id="b516b-113">I limiti di frequenza per questa API sono 100 chiamate al minuto e 1500 chiamate all'ora.</span><span class="sxs-lookup"><span data-stu-id="b516b-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="b516b-114">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="b516b-114">Permissions</span></span>
<span data-ttu-id="b516b-115">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="b516b-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="b516b-116">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi [Usare Microsoft Defender per le API endpoint](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="b516b-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="b516b-117">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="b516b-117">Permission type</span></span> |   <span data-ttu-id="b516b-118">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="b516b-118">Permission</span></span>  |   <span data-ttu-id="b516b-119">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="b516b-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="b516b-120">Applicazione</span><span class="sxs-lookup"><span data-stu-id="b516b-120">Application</span></span> |   <span data-ttu-id="b516b-121">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="b516b-121">Machine.Read.All</span></span> |  <span data-ttu-id="b516b-122">"Leggi tutti i profili computer"</span><span class="sxs-lookup"><span data-stu-id="b516b-122">'Read all machine profiles'</span></span>
<span data-ttu-id="b516b-123">Applicazione</span><span class="sxs-lookup"><span data-stu-id="b516b-123">Application</span></span> |   <span data-ttu-id="b516b-124">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="b516b-124">Machine.ReadWrite.All</span></span> | <span data-ttu-id="b516b-125">"Leggere e scrivere tutte le informazioni sul computer"</span><span class="sxs-lookup"><span data-stu-id="b516b-125">'Read and write all machine information'</span></span>
<span data-ttu-id="b516b-126">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="b516b-126">Delegated (work or school account)</span></span> | <span data-ttu-id="b516b-127">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="b516b-127">Machine.Read</span></span> | <span data-ttu-id="b516b-128">"Leggere le informazioni sul computer"</span><span class="sxs-lookup"><span data-stu-id="b516b-128">'Read machine information'</span></span>
<span data-ttu-id="b516b-129">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="b516b-129">Delegated (work or school account)</span></span> | <span data-ttu-id="b516b-130">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="b516b-130">Machine.ReadWrite</span></span> | <span data-ttu-id="b516b-131">"Leggere e scrivere informazioni sul computer"</span><span class="sxs-lookup"><span data-stu-id="b516b-131">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="b516b-132">Quando si ottiene un token utilizzando le credenziali utente:</span><span class="sxs-lookup"><span data-stu-id="b516b-132">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="b516b-133">L'utente deve disporre almeno dell'autorizzazione di ruolo seguente: "Visualizza dati".</span><span class="sxs-lookup"><span data-stu-id="b516b-133">The user needs to have at least the following role permission: 'View Data'.</span></span> <span data-ttu-id="b516b-134">Per ulteriori informazioni, vedere [Create and manage roles](user-roles.md) )</span><span class="sxs-lookup"><span data-stu-id="b516b-134">For more information, see [Create and manage roles](user-roles.md) )</span></span>
>- <span data-ttu-id="b516b-135">La risposta includerà solo i dispositivi a cui l'utente può accedere, in base alle impostazioni del gruppo di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="b516b-135">Response will include only devices that the user can access, based on device group settings.</span></span> <span data-ttu-id="b516b-136">Per altre informazioni, vedi [Creare e gestire gruppi di dispositivi.](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="b516b-136">For more information, see [Create and manage device groups](machine-groups.md).</span></span>

## <a name="http-request"></a><span data-ttu-id="b516b-137">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="b516b-137">HTTP request</span></span>
```
GET /api/users/{id}/machines
```

<span data-ttu-id="b516b-138">**L'ID non è l'UPN completo, ma solo il nome utente. (ad esempio, per recuperare i computer user1@contoso.com usare /api/users/user1/machines)**</span><span class="sxs-lookup"><span data-stu-id="b516b-138">**The ID is not the full UPN, but only the user name. (for example, to retrieve machines for user1@contoso.com use /api/users/user1/machines)**</span></span>


## <a name="request-headers"></a><span data-ttu-id="b516b-139">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="b516b-139">Request headers</span></span>

<span data-ttu-id="b516b-140">Name</span><span class="sxs-lookup"><span data-stu-id="b516b-140">Name</span></span> | <span data-ttu-id="b516b-141">Tipo</span><span class="sxs-lookup"><span data-stu-id="b516b-141">Type</span></span> | <span data-ttu-id="b516b-142">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b516b-142">Description</span></span>
:---|:---|:---
<span data-ttu-id="b516b-143">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="b516b-143">Authorization</span></span> | <span data-ttu-id="b516b-144">Stringa</span><span class="sxs-lookup"><span data-stu-id="b516b-144">String</span></span> | <span data-ttu-id="b516b-145">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="b516b-145">Bearer {token}.</span></span> <span data-ttu-id="b516b-146">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="b516b-146">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="b516b-147">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="b516b-147">Request body</span></span>
<span data-ttu-id="b516b-148">Vuoto</span><span class="sxs-lookup"><span data-stu-id="b516b-148">Empty</span></span>

## <a name="response"></a><span data-ttu-id="b516b-149">Risposta</span><span class="sxs-lookup"><span data-stu-id="b516b-149">Response</span></span>
<span data-ttu-id="b516b-150">Se l'operazione ha esito positivo e [](machine.md) l'utente esiste: 200 OK con l'elenco delle entità computer nel corpo.</span><span class="sxs-lookup"><span data-stu-id="b516b-150">If successful and user exists - 200 OK with list of [machine](machine.md) entities in the body.</span></span> <span data-ttu-id="b516b-151">Se l'utente non esiste- 404 Non trovato.</span><span class="sxs-lookup"><span data-stu-id="b516b-151">If user does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="b516b-152">Esempio</span><span class="sxs-lookup"><span data-stu-id="b516b-152">Example</span></span>

<span data-ttu-id="b516b-153">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="b516b-153">**Request**</span></span>

<span data-ttu-id="b516b-154">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="b516b-154">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/users/user1/machines
```
