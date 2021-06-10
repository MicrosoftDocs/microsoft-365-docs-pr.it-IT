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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 9f3313a08b072f4fb2f699148ab801207e56fc09
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772114"
---
# <a name="isolate-machine-api"></a><span data-ttu-id="973cd-104">ISOLA API del computer</span><span class="sxs-lookup"><span data-stu-id="973cd-104">Isolate machine API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="973cd-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="973cd-105">**Applies to:**</span></span>
- [<span data-ttu-id="973cd-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="973cd-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="973cd-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="973cd-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="973cd-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="973cd-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="973cd-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="973cd-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="973cd-110">Descrizione API</span><span class="sxs-lookup"><span data-stu-id="973cd-110">API description</span></span>
<span data-ttu-id="973cd-111">Isola un dispositivo dall'accesso alla rete esterna.</span><span class="sxs-lookup"><span data-stu-id="973cd-111">Isolates a device from accessing external network.</span></span>


## <a name="limitations"></a><span data-ttu-id="973cd-112">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="973cd-112">Limitations</span></span>
1. <span data-ttu-id="973cd-113">I limiti di frequenza per questa API sono 100 chiamate al minuto e 1500 chiamate all'ora.</span><span class="sxs-lookup"><span data-stu-id="973cd-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a><span data-ttu-id="973cd-114">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="973cd-114">Permissions</span></span>
<span data-ttu-id="973cd-115">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="973cd-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="973cd-116">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi [Usare Microsoft Defender per le API endpoint](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="973cd-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="973cd-117">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="973cd-117">Permission type</span></span> |   <span data-ttu-id="973cd-118">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="973cd-118">Permission</span></span>  |   <span data-ttu-id="973cd-119">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="973cd-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="973cd-120">Applicazione</span><span class="sxs-lookup"><span data-stu-id="973cd-120">Application</span></span> |   <span data-ttu-id="973cd-121">Machine.Isolate</span><span class="sxs-lookup"><span data-stu-id="973cd-121">Machine.Isolate</span></span> |   <span data-ttu-id="973cd-122">"Isola computer"</span><span class="sxs-lookup"><span data-stu-id="973cd-122">'Isolate machine'</span></span>
<span data-ttu-id="973cd-123">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="973cd-123">Delegated (work or school account)</span></span> | <span data-ttu-id="973cd-124">Machine.Isolate</span><span class="sxs-lookup"><span data-stu-id="973cd-124">Machine.Isolate</span></span> |  <span data-ttu-id="973cd-125">"Isola computer"</span><span class="sxs-lookup"><span data-stu-id="973cd-125">'Isolate machine'</span></span>

>[!Note]
> <span data-ttu-id="973cd-126">Quando si ottiene un token utilizzando le credenziali utente:</span><span class="sxs-lookup"><span data-stu-id="973cd-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="973cd-127">L'utente deve disporre almeno dell'autorizzazione di ruolo seguente: "Azioni di correzione attive" (per ulteriori informazioni, vedere [Creare](user-roles.md) e gestire ruoli)</span><span class="sxs-lookup"><span data-stu-id="973cd-127">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="973cd-128">L'utente deve avere accesso al dispositivo in base alle impostazioni del gruppo di dispositivi (per ulteriori informazioni, vedere [Creare](machine-groups.md) e gestire gruppi di dispositivi)</span><span class="sxs-lookup"><span data-stu-id="973cd-128">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>


## <a name="http-request"></a><span data-ttu-id="973cd-129">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="973cd-129">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/isolate
```

## <a name="request-headers"></a><span data-ttu-id="973cd-130">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="973cd-130">Request headers</span></span>

<span data-ttu-id="973cd-131">Name</span><span class="sxs-lookup"><span data-stu-id="973cd-131">Name</span></span> | <span data-ttu-id="973cd-132">Tipo</span><span class="sxs-lookup"><span data-stu-id="973cd-132">Type</span></span> | <span data-ttu-id="973cd-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="973cd-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="973cd-134">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="973cd-134">Authorization</span></span> | <span data-ttu-id="973cd-135">Stringa</span><span class="sxs-lookup"><span data-stu-id="973cd-135">String</span></span> | <span data-ttu-id="973cd-136">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="973cd-136">Bearer {token}.</span></span> <span data-ttu-id="973cd-137">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="973cd-137">**Required**.</span></span>
<span data-ttu-id="973cd-138">Content-Type</span><span class="sxs-lookup"><span data-stu-id="973cd-138">Content-Type</span></span> | <span data-ttu-id="973cd-139">stringa</span><span class="sxs-lookup"><span data-stu-id="973cd-139">string</span></span> | <span data-ttu-id="973cd-140">application/json.</span><span class="sxs-lookup"><span data-stu-id="973cd-140">application/json.</span></span> <span data-ttu-id="973cd-141">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="973cd-141">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="973cd-142">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="973cd-142">Request body</span></span>
<span data-ttu-id="973cd-143">Nel corpo della richiesta, fornire un oggetto JSON con i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="973cd-143">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="973cd-144">Parametro</span><span class="sxs-lookup"><span data-stu-id="973cd-144">Parameter</span></span> | <span data-ttu-id="973cd-145">Tipo</span><span class="sxs-lookup"><span data-stu-id="973cd-145">Type</span></span>    | <span data-ttu-id="973cd-146">Descrizione</span><span class="sxs-lookup"><span data-stu-id="973cd-146">Description</span></span>
:---|:---|:---
<span data-ttu-id="973cd-147">Comment</span><span class="sxs-lookup"><span data-stu-id="973cd-147">Comment</span></span> |   <span data-ttu-id="973cd-148">Stringa</span><span class="sxs-lookup"><span data-stu-id="973cd-148">String</span></span> |    <span data-ttu-id="973cd-149">Commento da associare all'azione.</span><span class="sxs-lookup"><span data-stu-id="973cd-149">Comment to associate with the action.</span></span> <span data-ttu-id="973cd-150">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="973cd-150">**Required**.</span></span>
<span data-ttu-id="973cd-151">IsolationType</span><span class="sxs-lookup"><span data-stu-id="973cd-151">IsolationType</span></span>   | <span data-ttu-id="973cd-152">Stringa</span><span class="sxs-lookup"><span data-stu-id="973cd-152">String</span></span> |  <span data-ttu-id="973cd-153">Tipo di isolamento.</span><span class="sxs-lookup"><span data-stu-id="973cd-153">Type of the isolation.</span></span> <span data-ttu-id="973cd-154">I valori consentiti sono: "Full" o "Selective".</span><span class="sxs-lookup"><span data-stu-id="973cd-154">Allowed values are: 'Full' or 'Selective'.</span></span>

<span data-ttu-id="973cd-155">**IsolationType** controlla il tipo di isolamento da eseguire e può essere uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="973cd-155">**IsolationType** controls the type of isolation to perform and can be one of the following:</span></span>
- <span data-ttu-id="973cd-156">Completo - Isolamento completo</span><span class="sxs-lookup"><span data-stu-id="973cd-156">Full – Full isolation</span></span>
- <span data-ttu-id="973cd-157">Selettivo: limitare l'accesso alla rete solo a un set limitato di applicazioni (per ulteriori dettagli, vedere [Isolare](respond-machine-alerts.md#isolate-devices-from-the-network) i dispositivi dalla rete)</span><span class="sxs-lookup"><span data-stu-id="973cd-157">Selective – Restrict only limited set of applications from accessing the network (see [Isolate devices from the network](respond-machine-alerts.md#isolate-devices-from-the-network) for more details)</span></span>


## <a name="response"></a><span data-ttu-id="973cd-158">Risposta</span><span class="sxs-lookup"><span data-stu-id="973cd-158">Response</span></span>
<span data-ttu-id="973cd-159">Se ha esito positivo, questo metodo restituisce 201 - Codice di risposta creato e [Azione del](machineaction.md) computer nel corpo della risposta.</span><span class="sxs-lookup"><span data-stu-id="973cd-159">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="973cd-160">Esempio</span><span class="sxs-lookup"><span data-stu-id="973cd-160">Example</span></span>

<span data-ttu-id="973cd-161">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="973cd-161">**Request**</span></span>

<span data-ttu-id="973cd-162">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="973cd-162">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/isolate
```

```json
{
  "Comment": "Isolate machine due to alert 1234",
  "IsolationType": "Full" 
}
```

- <span data-ttu-id="973cd-163">Per rilasciare un dispositivo dall'isolamento, vedi [Rilasciare il dispositivo dall'isolamento.](unisolate-machine.md)</span><span class="sxs-lookup"><span data-stu-id="973cd-163">To release a device from isolation, see [Release device from isolation](unisolate-machine.md).</span></span>
