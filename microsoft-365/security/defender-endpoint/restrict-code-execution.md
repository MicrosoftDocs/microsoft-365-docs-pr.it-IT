---
title: Limitare l'API di esecuzione delle app
description: Usa questa API per creare chiamate correlate alla limitazione dell'esecuzione di un'applicazione.
keywords: api, api del grafico, api supportate, raccogliere pacchetto di analisi
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
ms.openlocfilehash: 149f3aefd963f15eafa15030a322ec588c0615ed
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186781"
---
# <a name="restrict-app-execution-api"></a><span data-ttu-id="2fb5e-104">Limitare l'API di esecuzione delle app</span><span class="sxs-lookup"><span data-stu-id="2fb5e-104">Restrict app execution API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2fb5e-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="2fb5e-105">**Applies to:**</span></span>
- [<span data-ttu-id="2fb5e-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="2fb5e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2fb5e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2fb5e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="2fb5e-108">**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="2fb5e-108">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="2fb5e-109">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="2fb5e-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2fb5e-110">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="2fb5e-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="2fb5e-111">Descrizione API</span><span class="sxs-lookup"><span data-stu-id="2fb5e-111">API description</span></span>
<span data-ttu-id="2fb5e-112">Limitare l'esecuzione di tutte le applicazioni nel dispositivo ad eccezione di un set predefinito.</span><span class="sxs-lookup"><span data-stu-id="2fb5e-112">Restrict execution of all applications on the device except a predefined set.</span></span>


## <a name="limitations"></a><span data-ttu-id="2fb5e-113">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="2fb5e-113">Limitations</span></span>
1. <span data-ttu-id="2fb5e-114">I limiti di frequenza per questa API sono 100 chiamate al minuto e 1500 chiamate all'ora.</span><span class="sxs-lookup"><span data-stu-id="2fb5e-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a><span data-ttu-id="2fb5e-115">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="2fb5e-115">Permissions</span></span>
<span data-ttu-id="2fb5e-116">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="2fb5e-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="2fb5e-117">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi [Usare Microsoft Defender per le API endpoint](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="2fb5e-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="2fb5e-118">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="2fb5e-118">Permission type</span></span> |   <span data-ttu-id="2fb5e-119">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="2fb5e-119">Permission</span></span>  |   <span data-ttu-id="2fb5e-120">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="2fb5e-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="2fb5e-121">Applicazione</span><span class="sxs-lookup"><span data-stu-id="2fb5e-121">Application</span></span> |   <span data-ttu-id="2fb5e-122">Machine.RestrictExecution</span><span class="sxs-lookup"><span data-stu-id="2fb5e-122">Machine.RestrictExecution</span></span> | <span data-ttu-id="2fb5e-123">"Limita l'esecuzione del codice"</span><span class="sxs-lookup"><span data-stu-id="2fb5e-123">'Restrict code execution'</span></span>
<span data-ttu-id="2fb5e-124">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="2fb5e-124">Delegated (work or school account)</span></span> | <span data-ttu-id="2fb5e-125">Machine.RestrictExecution</span><span class="sxs-lookup"><span data-stu-id="2fb5e-125">Machine.RestrictExecution</span></span> | <span data-ttu-id="2fb5e-126">"Limita l'esecuzione del codice"</span><span class="sxs-lookup"><span data-stu-id="2fb5e-126">'Restrict code execution'</span></span>

>[!Note]
> <span data-ttu-id="2fb5e-127">Quando si ottiene un token utilizzando le credenziali utente:</span><span class="sxs-lookup"><span data-stu-id="2fb5e-127">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="2fb5e-128">L'utente deve disporre almeno dell'autorizzazione di ruolo seguente: "Azioni di correzione attive" (per ulteriori informazioni, vedere [Creare](user-roles.md) e gestire ruoli)</span><span class="sxs-lookup"><span data-stu-id="2fb5e-128">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="2fb5e-129">L'utente deve avere accesso al dispositivo in base alle impostazioni del gruppo di dispositivi (per ulteriori informazioni, vedere [Creare](machine-groups.md) e gestire gruppi di dispositivi)</span><span class="sxs-lookup"><span data-stu-id="2fb5e-129">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="2fb5e-130">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="2fb5e-130">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/restrictCodeExecution
```

## <a name="request-headers"></a><span data-ttu-id="2fb5e-131">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="2fb5e-131">Request headers</span></span>

<span data-ttu-id="2fb5e-132">Name</span><span class="sxs-lookup"><span data-stu-id="2fb5e-132">Name</span></span> | <span data-ttu-id="2fb5e-133">Tipo</span><span class="sxs-lookup"><span data-stu-id="2fb5e-133">Type</span></span> | <span data-ttu-id="2fb5e-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2fb5e-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="2fb5e-135">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="2fb5e-135">Authorization</span></span> | <span data-ttu-id="2fb5e-136">Stringa</span><span class="sxs-lookup"><span data-stu-id="2fb5e-136">String</span></span> | <span data-ttu-id="2fb5e-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="2fb5e-137">Bearer {token}.</span></span> <span data-ttu-id="2fb5e-138">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="2fb5e-138">**Required**.</span></span>
<span data-ttu-id="2fb5e-139">Content-Type</span><span class="sxs-lookup"><span data-stu-id="2fb5e-139">Content-Type</span></span> | <span data-ttu-id="2fb5e-140">stringa</span><span class="sxs-lookup"><span data-stu-id="2fb5e-140">string</span></span> | <span data-ttu-id="2fb5e-141">application/json.</span><span class="sxs-lookup"><span data-stu-id="2fb5e-141">application/json.</span></span> <span data-ttu-id="2fb5e-142">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="2fb5e-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="2fb5e-143">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="2fb5e-143">Request body</span></span>
<span data-ttu-id="2fb5e-144">Nel corpo della richiesta, fornire un oggetto JSON con i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="2fb5e-144">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="2fb5e-145">Parametro</span><span class="sxs-lookup"><span data-stu-id="2fb5e-145">Parameter</span></span> | <span data-ttu-id="2fb5e-146">Tipo</span><span class="sxs-lookup"><span data-stu-id="2fb5e-146">Type</span></span>    | <span data-ttu-id="2fb5e-147">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2fb5e-147">Description</span></span>
:---|:---|:---
<span data-ttu-id="2fb5e-148">Comment</span><span class="sxs-lookup"><span data-stu-id="2fb5e-148">Comment</span></span> |   <span data-ttu-id="2fb5e-149">Stringa</span><span class="sxs-lookup"><span data-stu-id="2fb5e-149">String</span></span> |    <span data-ttu-id="2fb5e-150">Commento da associare all'azione.</span><span class="sxs-lookup"><span data-stu-id="2fb5e-150">Comment to associate with the action.</span></span> <span data-ttu-id="2fb5e-151">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="2fb5e-151">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="2fb5e-152">Risposta</span><span class="sxs-lookup"><span data-stu-id="2fb5e-152">Response</span></span>
<span data-ttu-id="2fb5e-153">Se ha esito positivo, questo metodo restituisce 201 - Codice di risposta creato e [Azione del](machineaction.md) computer nel corpo della risposta.</span><span class="sxs-lookup"><span data-stu-id="2fb5e-153">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="2fb5e-154">Esempio</span><span class="sxs-lookup"><span data-stu-id="2fb5e-154">Example</span></span>

<span data-ttu-id="2fb5e-155">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="2fb5e-155">**Request**</span></span>

<span data-ttu-id="2fb5e-156">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="2fb5e-156">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/restrictCodeExecution 
```

```json
{
  "Comment": "Restrict code execution due to alert 1234"
}

```

- <span data-ttu-id="2fb5e-157">Per rimuovere la restrizione di esecuzione del codice da un dispositivo, vedi [Rimuovere la restrizione dell'app.](unrestrict-code-execution.md)</span><span class="sxs-lookup"><span data-stu-id="2fb5e-157">To remove code execution restriction from a device, see [Remove app restriction](unrestrict-code-execution.md).</span></span>
