---
title: API Per ottenere i computer correlati ai file
description: Scopri come usare l'API Get file-related machines per ottenere una raccolta di computer correlati a un hash di file in Microsoft Defender for Endpoint.
keywords: api, api del grafico, api supportate, get, dispositivi, hash
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
ms.openlocfilehash: 051bdad362e142446d248e90fad608fe5c0f016f
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166538"
---
# <a name="get-file-related-machines-api"></a><span data-ttu-id="49de9-104">API Per ottenere i computer correlati ai file</span><span class="sxs-lookup"><span data-stu-id="49de9-104">Get file-related machines API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="49de9-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="49de9-105">**Applies to:**</span></span>
- [<span data-ttu-id="49de9-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="49de9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="49de9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="49de9-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="49de9-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="49de9-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="49de9-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="49de9-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="49de9-110">Descrizione API</span><span class="sxs-lookup"><span data-stu-id="49de9-110">API description</span></span>
<span data-ttu-id="49de9-111">Recupera una raccolta di [machines correlati](machine.md) a un determinato hash di file.</span><span class="sxs-lookup"><span data-stu-id="49de9-111">Retrieves a collection of [Machines](machine.md) related to a given file hash.</span></span>


## <a name="limitations"></a><span data-ttu-id="49de9-112">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="49de9-112">Limitations</span></span>
1. <span data-ttu-id="49de9-113">I limiti di frequenza per questa API sono 100 chiamate al minuto e 1500 chiamate all'ora.</span><span class="sxs-lookup"><span data-stu-id="49de9-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="49de9-114">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="49de9-114">Permissions</span></span>
<span data-ttu-id="49de9-115">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="49de9-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="49de9-116">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi [Usare Microsoft Defender per le API endpoint](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="49de9-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="49de9-117">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="49de9-117">Permission type</span></span> |   <span data-ttu-id="49de9-118">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="49de9-118">Permission</span></span>  |   <span data-ttu-id="49de9-119">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="49de9-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="49de9-120">Applicazione</span><span class="sxs-lookup"><span data-stu-id="49de9-120">Application</span></span> |   <span data-ttu-id="49de9-121">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="49de9-121">Machine.Read.All</span></span> |  <span data-ttu-id="49de9-122">"Leggi tutti i profili computer"</span><span class="sxs-lookup"><span data-stu-id="49de9-122">'Read all machine profiles'</span></span>
<span data-ttu-id="49de9-123">Applicazione</span><span class="sxs-lookup"><span data-stu-id="49de9-123">Application</span></span> |   <span data-ttu-id="49de9-124">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="49de9-124">Machine.ReadWrite.All</span></span> | <span data-ttu-id="49de9-125">"Leggere e scrivere tutte le informazioni sul computer"</span><span class="sxs-lookup"><span data-stu-id="49de9-125">'Read and write all machine information'</span></span>
<span data-ttu-id="49de9-126">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="49de9-126">Delegated (work or school account)</span></span> | <span data-ttu-id="49de9-127">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="49de9-127">Machine.Read</span></span> | <span data-ttu-id="49de9-128">"Leggere le informazioni sul computer"</span><span class="sxs-lookup"><span data-stu-id="49de9-128">'Read machine information'</span></span>
<span data-ttu-id="49de9-129">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="49de9-129">Delegated (work or school account)</span></span> | <span data-ttu-id="49de9-130">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="49de9-130">Machine.ReadWrite</span></span> | <span data-ttu-id="49de9-131">"Leggere e scrivere informazioni sul computer"</span><span class="sxs-lookup"><span data-stu-id="49de9-131">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="49de9-132">Quando si ottiene un token utilizzando le credenziali utente:</span><span class="sxs-lookup"><span data-stu-id="49de9-132">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="49de9-133">L'utente deve disporre almeno dell'autorizzazione di ruolo seguente: 'Visualizza dati' (per ulteriori informazioni, vedere [Creare](user-roles.md) e gestire ruoli)</span><span class="sxs-lookup"><span data-stu-id="49de9-133">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="49de9-134">La risposta includerà solo i dispositivi a cui l'utente ha accesso, in base alle impostazioni del gruppo di dispositivi (per ulteriori informazioni, vedere [Creare](machine-groups.md) e gestire gruppi di dispositivi)</span><span class="sxs-lookup"><span data-stu-id="49de9-134">Response will include only devices, that the user have access to, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="49de9-135">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="49de9-135">HTTP request</span></span>
```
GET /api/files/{id}/machines
```

## <a name="request-headers"></a><span data-ttu-id="49de9-136">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="49de9-136">Request headers</span></span>

<span data-ttu-id="49de9-137">Name</span><span class="sxs-lookup"><span data-stu-id="49de9-137">Name</span></span> | <span data-ttu-id="49de9-138">Tipo</span><span class="sxs-lookup"><span data-stu-id="49de9-138">Type</span></span> | <span data-ttu-id="49de9-139">Descrizione</span><span class="sxs-lookup"><span data-stu-id="49de9-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="49de9-140">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="49de9-140">Authorization</span></span> | <span data-ttu-id="49de9-141">Stringa</span><span class="sxs-lookup"><span data-stu-id="49de9-141">String</span></span> | <span data-ttu-id="49de9-142">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="49de9-142">Bearer {token}.</span></span> <span data-ttu-id="49de9-143">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="49de9-143">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="49de9-144">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="49de9-144">Request body</span></span>
<span data-ttu-id="49de9-145">Vuoto</span><span class="sxs-lookup"><span data-stu-id="49de9-145">Empty</span></span>

## <a name="response"></a><span data-ttu-id="49de9-146">Risposta</span><span class="sxs-lookup"><span data-stu-id="49de9-146">Response</span></span>
<span data-ttu-id="49de9-147">Se ha esito positivo e il file [](machine.md) esiste- 200 OK con l'elenco delle entità del computer nel corpo.</span><span class="sxs-lookup"><span data-stu-id="49de9-147">If successful and file exists - 200 OK with list of [machine](machine.md) entities in the body.</span></span> <span data-ttu-id="49de9-148">Se il file non esiste - 404 Non trovato.</span><span class="sxs-lookup"><span data-stu-id="49de9-148">If file does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="49de9-149">Esempio</span><span class="sxs-lookup"><span data-stu-id="49de9-149">Example</span></span>

<span data-ttu-id="49de9-150">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="49de9-150">**Request**</span></span>

<span data-ttu-id="49de9-151">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="49de9-151">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/files/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/machines
```
