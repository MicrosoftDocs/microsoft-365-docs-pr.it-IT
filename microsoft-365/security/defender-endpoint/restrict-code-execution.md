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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 7195e91a3a9b7aef6977c925f2c8689d3e461815
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771574"
---
# <a name="restrict-app-execution-api"></a><span data-ttu-id="08a0a-104">Limitare l'API di esecuzione delle app</span><span class="sxs-lookup"><span data-stu-id="08a0a-104">Restrict app execution API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="08a0a-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="08a0a-105">**Applies to:**</span></span>
- [<span data-ttu-id="08a0a-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="08a0a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="08a0a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="08a0a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="08a0a-108">**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="08a0a-108">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="08a0a-109">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="08a0a-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="08a0a-110">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="08a0a-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="08a0a-111">Descrizione API</span><span class="sxs-lookup"><span data-stu-id="08a0a-111">API description</span></span>
<span data-ttu-id="08a0a-112">Limitare l'esecuzione di tutte le applicazioni nel dispositivo ad eccezione di un set predefinito.</span><span class="sxs-lookup"><span data-stu-id="08a0a-112">Restrict execution of all applications on the device except a predefined set.</span></span>


## <a name="limitations"></a><span data-ttu-id="08a0a-113">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="08a0a-113">Limitations</span></span>
1. <span data-ttu-id="08a0a-114">I limiti di frequenza per questa API sono 100 chiamate al minuto e 1500 chiamate all'ora.</span><span class="sxs-lookup"><span data-stu-id="08a0a-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a><span data-ttu-id="08a0a-115">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="08a0a-115">Permissions</span></span>
<span data-ttu-id="08a0a-116">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="08a0a-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="08a0a-117">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi [Usare Microsoft Defender per le API endpoint](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="08a0a-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="08a0a-118">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="08a0a-118">Permission type</span></span> |   <span data-ttu-id="08a0a-119">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="08a0a-119">Permission</span></span>  |   <span data-ttu-id="08a0a-120">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="08a0a-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="08a0a-121">Applicazione</span><span class="sxs-lookup"><span data-stu-id="08a0a-121">Application</span></span> |   <span data-ttu-id="08a0a-122">Machine.RestrictExecution</span><span class="sxs-lookup"><span data-stu-id="08a0a-122">Machine.RestrictExecution</span></span> | <span data-ttu-id="08a0a-123">"Limita l'esecuzione del codice"</span><span class="sxs-lookup"><span data-stu-id="08a0a-123">'Restrict code execution'</span></span>
<span data-ttu-id="08a0a-124">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="08a0a-124">Delegated (work or school account)</span></span> | <span data-ttu-id="08a0a-125">Machine.RestrictExecution</span><span class="sxs-lookup"><span data-stu-id="08a0a-125">Machine.RestrictExecution</span></span> | <span data-ttu-id="08a0a-126">"Limita l'esecuzione del codice"</span><span class="sxs-lookup"><span data-stu-id="08a0a-126">'Restrict code execution'</span></span>

>[!Note]
> <span data-ttu-id="08a0a-127">Quando si ottiene un token utilizzando le credenziali utente:</span><span class="sxs-lookup"><span data-stu-id="08a0a-127">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="08a0a-128">L'utente deve disporre almeno dell'autorizzazione di ruolo seguente: "Azioni di correzione attive" (per ulteriori informazioni, vedere [Creare](user-roles.md) e gestire ruoli)</span><span class="sxs-lookup"><span data-stu-id="08a0a-128">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="08a0a-129">L'utente deve avere accesso al dispositivo in base alle impostazioni del gruppo di dispositivi (per ulteriori informazioni, vedere [Creare](machine-groups.md) e gestire gruppi di dispositivi)</span><span class="sxs-lookup"><span data-stu-id="08a0a-129">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="08a0a-130">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="08a0a-130">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/restrictCodeExecution
```

## <a name="request-headers"></a><span data-ttu-id="08a0a-131">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="08a0a-131">Request headers</span></span>

<span data-ttu-id="08a0a-132">Name</span><span class="sxs-lookup"><span data-stu-id="08a0a-132">Name</span></span> | <span data-ttu-id="08a0a-133">Tipo</span><span class="sxs-lookup"><span data-stu-id="08a0a-133">Type</span></span> | <span data-ttu-id="08a0a-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="08a0a-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="08a0a-135">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="08a0a-135">Authorization</span></span> | <span data-ttu-id="08a0a-136">Stringa</span><span class="sxs-lookup"><span data-stu-id="08a0a-136">String</span></span> | <span data-ttu-id="08a0a-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="08a0a-137">Bearer {token}.</span></span> <span data-ttu-id="08a0a-138">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="08a0a-138">**Required**.</span></span>
<span data-ttu-id="08a0a-139">Content-Type</span><span class="sxs-lookup"><span data-stu-id="08a0a-139">Content-Type</span></span> | <span data-ttu-id="08a0a-140">stringa</span><span class="sxs-lookup"><span data-stu-id="08a0a-140">string</span></span> | <span data-ttu-id="08a0a-141">application/json.</span><span class="sxs-lookup"><span data-stu-id="08a0a-141">application/json.</span></span> <span data-ttu-id="08a0a-142">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="08a0a-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="08a0a-143">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="08a0a-143">Request body</span></span>
<span data-ttu-id="08a0a-144">Nel corpo della richiesta, fornire un oggetto JSON con i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="08a0a-144">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="08a0a-145">Parametro</span><span class="sxs-lookup"><span data-stu-id="08a0a-145">Parameter</span></span> | <span data-ttu-id="08a0a-146">Tipo</span><span class="sxs-lookup"><span data-stu-id="08a0a-146">Type</span></span>    | <span data-ttu-id="08a0a-147">Descrizione</span><span class="sxs-lookup"><span data-stu-id="08a0a-147">Description</span></span>
:---|:---|:---
<span data-ttu-id="08a0a-148">Comment</span><span class="sxs-lookup"><span data-stu-id="08a0a-148">Comment</span></span> |   <span data-ttu-id="08a0a-149">Stringa</span><span class="sxs-lookup"><span data-stu-id="08a0a-149">String</span></span> |    <span data-ttu-id="08a0a-150">Commento da associare all'azione.</span><span class="sxs-lookup"><span data-stu-id="08a0a-150">Comment to associate with the action.</span></span> <span data-ttu-id="08a0a-151">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="08a0a-151">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="08a0a-152">Risposta</span><span class="sxs-lookup"><span data-stu-id="08a0a-152">Response</span></span>
<span data-ttu-id="08a0a-153">Se ha esito positivo, questo metodo restituisce 201 - Codice di risposta creato e [Azione del](machineaction.md) computer nel corpo della risposta.</span><span class="sxs-lookup"><span data-stu-id="08a0a-153">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="08a0a-154">Esempio</span><span class="sxs-lookup"><span data-stu-id="08a0a-154">Example</span></span>

<span data-ttu-id="08a0a-155">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="08a0a-155">**Request**</span></span>

<span data-ttu-id="08a0a-156">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="08a0a-156">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/restrictCodeExecution 
```

```json
{
  "Comment": "Restrict code execution due to alert 1234"
}

```

- <span data-ttu-id="08a0a-157">Per rimuovere la restrizione di esecuzione del codice da un dispositivo, vedi [Rimuovere la restrizione dell'app.](unrestrict-code-execution.md)</span><span class="sxs-lookup"><span data-stu-id="08a0a-157">To remove code execution restriction from a device, see [Remove app restriction](unrestrict-code-execution.md).</span></span>
