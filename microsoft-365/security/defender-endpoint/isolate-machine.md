---
title: ISOLA API del computer
description: Scopri come usare l'API Isola computer per isolare un dispositivo dall'accesso alla rete esterna in Microsoft Defender per Endpoint.
keywords: api, api del grafico, api supportate, isolare il dispositivo
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
ms.openlocfilehash: b9c8d4da528ba065dc1b4a68ddaa816a1ad78c4a
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187833"
---
# <a name="isolate-machine-api"></a><span data-ttu-id="a189c-104">ISOLA API del computer</span><span class="sxs-lookup"><span data-stu-id="a189c-104">Isolate machine API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a189c-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="a189c-105">**Applies to:**</span></span>
- [<span data-ttu-id="a189c-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="a189c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a189c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a189c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="a189c-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="a189c-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a189c-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="a189c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="a189c-110">Descrizione API</span><span class="sxs-lookup"><span data-stu-id="a189c-110">API description</span></span>
<span data-ttu-id="a189c-111">Isola un dispositivo dall'accesso alla rete esterna.</span><span class="sxs-lookup"><span data-stu-id="a189c-111">Isolates a device from accessing external network.</span></span>


## <a name="limitations"></a><span data-ttu-id="a189c-112">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="a189c-112">Limitations</span></span>
1. <span data-ttu-id="a189c-113">I limiti di frequenza per questa API sono 100 chiamate al minuto e 1500 chiamate all'ora.</span><span class="sxs-lookup"><span data-stu-id="a189c-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a><span data-ttu-id="a189c-114">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="a189c-114">Permissions</span></span>
<span data-ttu-id="a189c-115">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="a189c-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="a189c-116">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi [Usare Microsoft Defender per le API endpoint](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="a189c-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="a189c-117">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="a189c-117">Permission type</span></span> |   <span data-ttu-id="a189c-118">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="a189c-118">Permission</span></span>  |   <span data-ttu-id="a189c-119">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="a189c-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="a189c-120">Applicazione</span><span class="sxs-lookup"><span data-stu-id="a189c-120">Application</span></span> |   <span data-ttu-id="a189c-121">Machine.Isolate</span><span class="sxs-lookup"><span data-stu-id="a189c-121">Machine.Isolate</span></span> |   <span data-ttu-id="a189c-122">"Isola computer"</span><span class="sxs-lookup"><span data-stu-id="a189c-122">'Isolate machine'</span></span>
<span data-ttu-id="a189c-123">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="a189c-123">Delegated (work or school account)</span></span> | <span data-ttu-id="a189c-124">Machine.Isolate</span><span class="sxs-lookup"><span data-stu-id="a189c-124">Machine.Isolate</span></span> |  <span data-ttu-id="a189c-125">"Isola computer"</span><span class="sxs-lookup"><span data-stu-id="a189c-125">'Isolate machine'</span></span>

>[!Note]
> <span data-ttu-id="a189c-126">Quando si ottiene un token utilizzando le credenziali utente:</span><span class="sxs-lookup"><span data-stu-id="a189c-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="a189c-127">L'utente deve disporre almeno dell'autorizzazione di ruolo seguente: "Azioni di correzione attive" (per ulteriori informazioni, vedere [Creare](user-roles.md) e gestire ruoli)</span><span class="sxs-lookup"><span data-stu-id="a189c-127">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="a189c-128">L'utente deve avere accesso al dispositivo in base alle impostazioni del gruppo di dispositivi (per ulteriori informazioni, vedere [Creare](machine-groups.md) e gestire gruppi di dispositivi)</span><span class="sxs-lookup"><span data-stu-id="a189c-128">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>


## <a name="http-request"></a><span data-ttu-id="a189c-129">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="a189c-129">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/isolate
```

## <a name="request-headers"></a><span data-ttu-id="a189c-130">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="a189c-130">Request headers</span></span>

<span data-ttu-id="a189c-131">Name</span><span class="sxs-lookup"><span data-stu-id="a189c-131">Name</span></span> | <span data-ttu-id="a189c-132">Tipo</span><span class="sxs-lookup"><span data-stu-id="a189c-132">Type</span></span> | <span data-ttu-id="a189c-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a189c-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="a189c-134">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="a189c-134">Authorization</span></span> | <span data-ttu-id="a189c-135">Stringa</span><span class="sxs-lookup"><span data-stu-id="a189c-135">String</span></span> | <span data-ttu-id="a189c-136">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="a189c-136">Bearer {token}.</span></span> <span data-ttu-id="a189c-137">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="a189c-137">**Required**.</span></span>
<span data-ttu-id="a189c-138">Content-Type</span><span class="sxs-lookup"><span data-stu-id="a189c-138">Content-Type</span></span> | <span data-ttu-id="a189c-139">stringa</span><span class="sxs-lookup"><span data-stu-id="a189c-139">string</span></span> | <span data-ttu-id="a189c-140">application/json.</span><span class="sxs-lookup"><span data-stu-id="a189c-140">application/json.</span></span> <span data-ttu-id="a189c-141">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="a189c-141">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="a189c-142">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="a189c-142">Request body</span></span>
<span data-ttu-id="a189c-143">Nel corpo della richiesta, fornire un oggetto JSON con i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="a189c-143">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="a189c-144">Parametro</span><span class="sxs-lookup"><span data-stu-id="a189c-144">Parameter</span></span> | <span data-ttu-id="a189c-145">Tipo</span><span class="sxs-lookup"><span data-stu-id="a189c-145">Type</span></span>    | <span data-ttu-id="a189c-146">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a189c-146">Description</span></span>
:---|:---|:---
<span data-ttu-id="a189c-147">Comment</span><span class="sxs-lookup"><span data-stu-id="a189c-147">Comment</span></span> |   <span data-ttu-id="a189c-148">Stringa</span><span class="sxs-lookup"><span data-stu-id="a189c-148">String</span></span> |    <span data-ttu-id="a189c-149">Commento da associare all'azione.</span><span class="sxs-lookup"><span data-stu-id="a189c-149">Comment to associate with the action.</span></span> <span data-ttu-id="a189c-150">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="a189c-150">**Required**.</span></span>
<span data-ttu-id="a189c-151">IsolationType</span><span class="sxs-lookup"><span data-stu-id="a189c-151">IsolationType</span></span>   | <span data-ttu-id="a189c-152">Stringa</span><span class="sxs-lookup"><span data-stu-id="a189c-152">String</span></span> |  <span data-ttu-id="a189c-153">Tipo di isolamento.</span><span class="sxs-lookup"><span data-stu-id="a189c-153">Type of the isolation.</span></span> <span data-ttu-id="a189c-154">I valori consentiti sono: "Full" o "Selective".</span><span class="sxs-lookup"><span data-stu-id="a189c-154">Allowed values are: 'Full' or 'Selective'.</span></span>

<span data-ttu-id="a189c-155">**IsolationType** controlla il tipo di isolamento da eseguire e può essere uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="a189c-155">**IsolationType** controls the type of isolation to perform and can be one of the following:</span></span>
- <span data-ttu-id="a189c-156">Completo - Isolamento completo</span><span class="sxs-lookup"><span data-stu-id="a189c-156">Full – Full isolation</span></span>
- <span data-ttu-id="a189c-157">Selettivo: limitare l'accesso alla rete solo a un set limitato di applicazioni (per ulteriori dettagli, vedere [Isolare](respond-machine-alerts.md#isolate-devices-from-the-network) i dispositivi dalla rete)</span><span class="sxs-lookup"><span data-stu-id="a189c-157">Selective – Restrict only limited set of applications from accessing the network (see [Isolate devices from the network](respond-machine-alerts.md#isolate-devices-from-the-network) for more details)</span></span>


## <a name="response"></a><span data-ttu-id="a189c-158">Risposta</span><span class="sxs-lookup"><span data-stu-id="a189c-158">Response</span></span>
<span data-ttu-id="a189c-159">Se ha esito positivo, questo metodo restituisce 201 - Codice di risposta creato e [Azione del](machineaction.md) computer nel corpo della risposta.</span><span class="sxs-lookup"><span data-stu-id="a189c-159">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="a189c-160">Esempio</span><span class="sxs-lookup"><span data-stu-id="a189c-160">Example</span></span>

<span data-ttu-id="a189c-161">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="a189c-161">**Request**</span></span>

<span data-ttu-id="a189c-162">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="a189c-162">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/isolate
```

```json
{
  "Comment": "Isolate machine due to alert 1234",
  "IsolationType": "Full" 
}
```

- <span data-ttu-id="a189c-163">Per rilasciare un dispositivo dall'isolamento, vedi [Rilasciare il dispositivo dall'isolamento.](unisolate-machine.md)</span><span class="sxs-lookup"><span data-stu-id="a189c-163">To release a device from isolation, see [Release device from isolation](unisolate-machine.md).</span></span>
