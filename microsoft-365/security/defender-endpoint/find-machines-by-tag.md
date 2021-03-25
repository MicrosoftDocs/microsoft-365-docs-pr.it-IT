---
title: Trovare i dispositivi in base all'API tag
description: Trovare tutti i dispositivi che contengono tag specifc
keywords: api, api supportate, get, dispositivo, trovare, trovare dispositivo, per tag, tag
search.product: eADQiWindows 10XVcnh
ms.prod: w10
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
ms.openlocfilehash: 6460860828acd5ea0c3509e9eb06061d2a9a0cc2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200150"
---
# <a name="find-devices-by-tag-api"></a><span data-ttu-id="f37bc-104">Trovare i dispositivi in base all'API tag</span><span class="sxs-lookup"><span data-stu-id="f37bc-104">Find devices by tag API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="f37bc-105">**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="f37bc-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="f37bc-106">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="f37bc-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f37bc-107">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="f37bc-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="f37bc-108">Descrizione API</span><span class="sxs-lookup"><span data-stu-id="f37bc-108">API description</span></span>
<span data-ttu-id="f37bc-109">Trova [computer](machine.md) per [tag](machine-tags.md).</span><span class="sxs-lookup"><span data-stu-id="f37bc-109">Find [Machines](machine.md) by [Tag](machine-tags.md).</span></span>
<br><span data-ttu-id="f37bc-110">```startswith``` query è supportata.</span><span class="sxs-lookup"><span data-stu-id="f37bc-110">```startswith``` query is supported.</span></span> 

## <a name="limitations"></a><span data-ttu-id="f37bc-111">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="f37bc-111">Limitations</span></span>
1. <span data-ttu-id="f37bc-112">I limiti di frequenza per questa API sono 100 chiamate al minuto e 1500 chiamate all'ora.</span><span class="sxs-lookup"><span data-stu-id="f37bc-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="f37bc-113">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="f37bc-113">Permissions</span></span>
<span data-ttu-id="f37bc-114">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="f37bc-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="f37bc-115">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi [Usare Microsoft Defender per le API endpoint](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="f37bc-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="f37bc-116">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="f37bc-116">Permission type</span></span> |   <span data-ttu-id="f37bc-117">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="f37bc-117">Permission</span></span>  |   <span data-ttu-id="f37bc-118">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="f37bc-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="f37bc-119">Applicazione</span><span class="sxs-lookup"><span data-stu-id="f37bc-119">Application</span></span> |   <span data-ttu-id="f37bc-120">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="f37bc-120">Machine.Read.All</span></span> |  <span data-ttu-id="f37bc-121">"Leggi tutti i profili computer"</span><span class="sxs-lookup"><span data-stu-id="f37bc-121">'Read all machine profiles'</span></span>
<span data-ttu-id="f37bc-122">Applicazione</span><span class="sxs-lookup"><span data-stu-id="f37bc-122">Application</span></span> |   <span data-ttu-id="f37bc-123">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="f37bc-123">Machine.ReadWrite.All</span></span> | <span data-ttu-id="f37bc-124">"Leggere e scrivere tutte le informazioni sul computer"</span><span class="sxs-lookup"><span data-stu-id="f37bc-124">'Read and write all machine information'</span></span>
<span data-ttu-id="f37bc-125">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="f37bc-125">Delegated (work or school account)</span></span> | <span data-ttu-id="f37bc-126">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="f37bc-126">Machine.Read</span></span> | <span data-ttu-id="f37bc-127">"Leggere le informazioni sul computer"</span><span class="sxs-lookup"><span data-stu-id="f37bc-127">'Read machine information'</span></span>
<span data-ttu-id="f37bc-128">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="f37bc-128">Delegated (work or school account)</span></span> | <span data-ttu-id="f37bc-129">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="f37bc-129">Machine.ReadWrite</span></span> | <span data-ttu-id="f37bc-130">"Leggere e scrivere informazioni sul computer"</span><span class="sxs-lookup"><span data-stu-id="f37bc-130">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="f37bc-131">Quando si ottiene un token utilizzando le credenziali utente:</span><span class="sxs-lookup"><span data-stu-id="f37bc-131">When obtaining a token using user credentials:</span></span>
> - <span data-ttu-id="f37bc-132">La risposta includerà solo i dispositivi a cui l'utente ha accesso in base alle impostazioni del gruppo di dispositivi (per ulteriori informazioni, vedere [Creare](machine-groups.md) e gestire gruppi di dispositivi)</span><span class="sxs-lookup"><span data-stu-id="f37bc-132">Response will include only devices that the user have access to based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>
> - <span data-ttu-id="f37bc-133">L'utente deve disporre almeno dell'autorizzazione di ruolo seguente: 'Visualizza dati' (per ulteriori informazioni, vedere [Creare](user-roles.md) e gestire ruoli)</span><span class="sxs-lookup"><span data-stu-id="f37bc-133">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
> - <span data-ttu-id="f37bc-134">La risposta includerà solo i dispositivi a cui l'utente ha accesso in base alle impostazioni del gruppo di dispositivi (per ulteriori informazioni, vedere [Creare](machine-groups.md) e gestire gruppi di dispositivi)</span><span class="sxs-lookup"><span data-stu-id="f37bc-134">Response will include only devices that the user have access to based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="f37bc-135">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="f37bc-135">HTTP request</span></span>
```
GET /api/machines/findbytag?tag={tag}&useStartsWithFilter={true/false}
```

## <a name="request-headers"></a><span data-ttu-id="f37bc-136">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="f37bc-136">Request headers</span></span>

<span data-ttu-id="f37bc-137">Name</span><span class="sxs-lookup"><span data-stu-id="f37bc-137">Name</span></span> | <span data-ttu-id="f37bc-138">Tipo</span><span class="sxs-lookup"><span data-stu-id="f37bc-138">Type</span></span> | <span data-ttu-id="f37bc-139">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f37bc-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="f37bc-140">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="f37bc-140">Authorization</span></span> | <span data-ttu-id="f37bc-141">Stringa</span><span class="sxs-lookup"><span data-stu-id="f37bc-141">String</span></span> | <span data-ttu-id="f37bc-142">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="f37bc-142">Bearer {token}.</span></span> <span data-ttu-id="f37bc-143">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="f37bc-143">**Required**.</span></span>

## <a name="request-uri-parameters"></a><span data-ttu-id="f37bc-144">Parametri URI di richiesta</span><span class="sxs-lookup"><span data-stu-id="f37bc-144">Request URI parameters</span></span>

<span data-ttu-id="f37bc-145">Nome</span><span class="sxs-lookup"><span data-stu-id="f37bc-145">Name</span></span> | <span data-ttu-id="f37bc-146">Tipo</span><span class="sxs-lookup"><span data-stu-id="f37bc-146">Type</span></span> | <span data-ttu-id="f37bc-147">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f37bc-147">Description</span></span>
:---|:---|:---
<span data-ttu-id="f37bc-148">tag</span><span class="sxs-lookup"><span data-stu-id="f37bc-148">tag</span></span> | <span data-ttu-id="f37bc-149">Stringa</span><span class="sxs-lookup"><span data-stu-id="f37bc-149">String</span></span> | <span data-ttu-id="f37bc-150">Nome del tag.</span><span class="sxs-lookup"><span data-stu-id="f37bc-150">The tag name.</span></span> <span data-ttu-id="f37bc-151">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="f37bc-151">**Required**.</span></span>
<span data-ttu-id="f37bc-152">useStartsWithFilter</span><span class="sxs-lookup"><span data-stu-id="f37bc-152">useStartsWithFilter</span></span> | <span data-ttu-id="f37bc-153">Booleano</span><span class="sxs-lookup"><span data-stu-id="f37bc-153">Boolean</span></span> | <span data-ttu-id="f37bc-154">Se impostato su true, la ricerca troverà tutti i dispositivi con il nome tag che inizia con il tag specificato nella query.</span><span class="sxs-lookup"><span data-stu-id="f37bc-154">When set to true, the search will find all devices with tag name that starts with the given tag in the query.</span></span> <span data-ttu-id="f37bc-155">Il valore predefinito è false.</span><span class="sxs-lookup"><span data-stu-id="f37bc-155">Defaults to false.</span></span> <span data-ttu-id="f37bc-156">**Facoltativo**.</span><span class="sxs-lookup"><span data-stu-id="f37bc-156">**Optional**.</span></span>

## <a name="request-body"></a><span data-ttu-id="f37bc-157">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="f37bc-157">Request body</span></span>
<span data-ttu-id="f37bc-158">Vuoto</span><span class="sxs-lookup"><span data-stu-id="f37bc-158">Empty</span></span>

## <a name="response"></a><span data-ttu-id="f37bc-159">Risposta</span><span class="sxs-lookup"><span data-stu-id="f37bc-159">Response</span></span>
<span data-ttu-id="f37bc-160">Se ha esito positivo- 200 OK con l'elenco dei computer nel corpo della risposta.</span><span class="sxs-lookup"><span data-stu-id="f37bc-160">If successful - 200 OK with list of the machines in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="f37bc-161">Esempio</span><span class="sxs-lookup"><span data-stu-id="f37bc-161">Example</span></span>

<span data-ttu-id="f37bc-162">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="f37bc-162">**Request**</span></span>

<span data-ttu-id="f37bc-163">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="f37bc-163">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/findbytag?tag=testTag&useStartsWithFilter=true
```