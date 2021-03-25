---
title: API Per aggiungere o rimuovere tag computer
description: Scopri come usare l'API Add or Remove machine tags per aggiungere o rimuovere un tag per un computer in Microsoft Defender for Endpoint.
keywords: api, api del grafico, api supportate, tag, tag del computer
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
ms.openlocfilehash: 98dd513cc66683ff1b95f66d6d7b89916ce54bab
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199777"
---
# <a name="add-or-remove-machine-tags-api"></a><span data-ttu-id="4af2d-104">API Per aggiungere o rimuovere tag computer</span><span class="sxs-lookup"><span data-stu-id="4af2d-104">Add or Remove Machine Tags API</span></span>

<span data-ttu-id="4af2d-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="4af2d-105">**Applies to:**</span></span>

- [<span data-ttu-id="4af2d-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="4af2d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

> <span data-ttu-id="4af2d-107">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="4af2d-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="4af2d-108">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="4af2d-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="4af2d-109">Descrizione API</span><span class="sxs-lookup"><span data-stu-id="4af2d-109">API description</span></span>

<span data-ttu-id="4af2d-110">Aggiunge o rimuove tag a un computer [specifico.](machine.md)</span><span class="sxs-lookup"><span data-stu-id="4af2d-110">Adds or remove tag to a specific [Machine](machine.md).</span></span>

## <a name="limitations"></a><span data-ttu-id="4af2d-111">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="4af2d-111">Limitations</span></span>

1. <span data-ttu-id="4af2d-112">È possibile pubblicare nei computer l'ultima volta che si è visto in base al periodo di conservazione configurato.</span><span class="sxs-lookup"><span data-stu-id="4af2d-112">You can post on machines last seen according to your configured retention period.</span></span>

2. <span data-ttu-id="4af2d-113">I limiti di frequenza per questa API sono 100 chiamate al minuto e 1500 chiamate all'ora.</span><span class="sxs-lookup"><span data-stu-id="4af2d-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="4af2d-114">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="4af2d-114">Permissions</span></span>

<span data-ttu-id="4af2d-115">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="4af2d-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="4af2d-116">Per altre informazioni, incluso come scegliere le autorizzazioni, vedi [Usare Defender per le API endpoint](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="4af2d-116">To learn more, including how to choose permissions, see [Use Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="4af2d-117">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="4af2d-117">Permission type</span></span> |    <span data-ttu-id="4af2d-118">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="4af2d-118">Permission</span></span>    |    <span data-ttu-id="4af2d-119">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="4af2d-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="4af2d-120">Applicazione</span><span class="sxs-lookup"><span data-stu-id="4af2d-120">Application</span></span> |    <span data-ttu-id="4af2d-121">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="4af2d-121">Machine.ReadWrite.All</span></span> |    <span data-ttu-id="4af2d-122">"Leggere e scrivere tutte le informazioni sul computer"</span><span class="sxs-lookup"><span data-stu-id="4af2d-122">'Read and write all machine information'</span></span>
<span data-ttu-id="4af2d-123">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="4af2d-123">Delegated (work or school account)</span></span> | <span data-ttu-id="4af2d-124">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="4af2d-124">Machine.ReadWrite</span></span> | <span data-ttu-id="4af2d-125">"Leggere e scrivere informazioni sul computer"</span><span class="sxs-lookup"><span data-stu-id="4af2d-125">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="4af2d-126">Quando si ottiene un token utilizzando le credenziali utente:</span><span class="sxs-lookup"><span data-stu-id="4af2d-126">When obtaining a token using user credentials:</span></span>
>
>- <span data-ttu-id="4af2d-127">L'utente deve disporre almeno dell'autorizzazione di ruolo seguente: "Gestisci impostazione di sicurezza".</span><span class="sxs-lookup"><span data-stu-id="4af2d-127">The user needs to have at least the following role permission: 'Manage security setting'.</span></span> <span data-ttu-id="4af2d-128">Per ulteriori informazioni, vedere [Creare e gestire ruoli.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="4af2d-128">For more  (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="4af2d-129">L'utente deve avere accesso al computer in base alle impostazioni del gruppo di computer (per ulteriori informazioni, vedere [Creare](machine-groups.md) e gestire gruppi di computer)</span><span class="sxs-lookup"><span data-stu-id="4af2d-129">User needs to have access to the machine, based on machine group settings (See [Create and manage machine groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="4af2d-130">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="4af2d-130">HTTP request</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/{id}/tags
```

## <a name="request-headers"></a><span data-ttu-id="4af2d-131">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="4af2d-131">Request headers</span></span>

<span data-ttu-id="4af2d-132">Name</span><span class="sxs-lookup"><span data-stu-id="4af2d-132">Name</span></span> | <span data-ttu-id="4af2d-133">Tipo</span><span class="sxs-lookup"><span data-stu-id="4af2d-133">Type</span></span> | <span data-ttu-id="4af2d-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4af2d-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="4af2d-135">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="4af2d-135">Authorization</span></span> | <span data-ttu-id="4af2d-136">Stringa</span><span class="sxs-lookup"><span data-stu-id="4af2d-136">String</span></span> | <span data-ttu-id="4af2d-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="4af2d-137">Bearer {token}.</span></span> <span data-ttu-id="4af2d-138">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="4af2d-138">**Required**.</span></span>
<span data-ttu-id="4af2d-139">Content-Type</span><span class="sxs-lookup"><span data-stu-id="4af2d-139">Content-Type</span></span> | <span data-ttu-id="4af2d-140">stringa</span><span class="sxs-lookup"><span data-stu-id="4af2d-140">string</span></span> | <span data-ttu-id="4af2d-141">application/json.</span><span class="sxs-lookup"><span data-stu-id="4af2d-141">application/json.</span></span> <span data-ttu-id="4af2d-142">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="4af2d-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="4af2d-143">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="4af2d-143">Request body</span></span>

<span data-ttu-id="4af2d-144">Nel corpo della richiesta, fornire un oggetto JSON con i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="4af2d-144">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="4af2d-145">Parametro</span><span class="sxs-lookup"><span data-stu-id="4af2d-145">Parameter</span></span> |    <span data-ttu-id="4af2d-146">Tipo</span><span class="sxs-lookup"><span data-stu-id="4af2d-146">Type</span></span>    | <span data-ttu-id="4af2d-147">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4af2d-147">Description</span></span>
:---|:---|:---
<span data-ttu-id="4af2d-148">Valore</span><span class="sxs-lookup"><span data-stu-id="4af2d-148">Value</span></span> |    <span data-ttu-id="4af2d-149">Stringa</span><span class="sxs-lookup"><span data-stu-id="4af2d-149">String</span></span> |    <span data-ttu-id="4af2d-150">Nome del tag.</span><span class="sxs-lookup"><span data-stu-id="4af2d-150">The tag name.</span></span> <span data-ttu-id="4af2d-151">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="4af2d-151">**Required**.</span></span>
<span data-ttu-id="4af2d-152">Azione</span><span class="sxs-lookup"><span data-stu-id="4af2d-152">Action</span></span>    | <span data-ttu-id="4af2d-153">Enum</span><span class="sxs-lookup"><span data-stu-id="4af2d-153">Enum</span></span> |    <span data-ttu-id="4af2d-154">Aggiungi o Rimuovi.</span><span class="sxs-lookup"><span data-stu-id="4af2d-154">Add or Remove.</span></span> <span data-ttu-id="4af2d-155">I valori consentiti sono: 'Add' o 'Remove'.</span><span class="sxs-lookup"><span data-stu-id="4af2d-155">Allowed values are: 'Add' or 'Remove'.</span></span> <span data-ttu-id="4af2d-156">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="4af2d-156">**Required**.</span></span>


## <a name="response"></a><span data-ttu-id="4af2d-157">Risposta</span><span class="sxs-lookup"><span data-stu-id="4af2d-157">Response</span></span>

<span data-ttu-id="4af2d-158">Se ha esito positivo, questo metodo restituisce 200 - Ok codice di risposta e computer aggiornato nel corpo della risposta.</span><span class="sxs-lookup"><span data-stu-id="4af2d-158">If successful, this method returns 200 - Ok response code and the updated Machine in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="4af2d-159">Esempio</span><span class="sxs-lookup"><span data-stu-id="4af2d-159">Example</span></span>

<span data-ttu-id="4af2d-160">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="4af2d-160">**Request**</span></span>

<span data-ttu-id="4af2d-161">Ecco un esempio di richiesta che aggiunge tag computer.</span><span class="sxs-lookup"><span data-stu-id="4af2d-161">Here is an example of a request that adds machine tag.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/tags
```

```json
{
  "Value" : "test Tag 2",
  "Action": "Add"
}
```

- <span data-ttu-id="4af2d-162">Per rimuovere il tag machine, imposta Action su 'Remove' invece di 'Add' nel corpo della richiesta.</span><span class="sxs-lookup"><span data-stu-id="4af2d-162">To remove machine tag, set the Action to 'Remove' instead of 'Add' in the request body.</span></span>
