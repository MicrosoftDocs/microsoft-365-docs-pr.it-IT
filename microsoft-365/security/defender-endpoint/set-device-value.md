---
title: API per l'impostazione del valore del dispositivo
description: Scopri come specificare il valore di un dispositivo usando un'API di Microsoft Defender per endpoint.
keywords: api, api del grafico, api supportate, tag, tag del computer
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: e14e696169a2d1cd76e4fb5b2ee8de951e9e1280
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771408"
---
# <a name="set-device-value-api"></a><span data-ttu-id="1e98b-104">API per l'impostazione del valore del dispositivo</span><span class="sxs-lookup"><span data-stu-id="1e98b-104">Set device value API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1e98b-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="1e98b-105">**Applies to:**</span></span>
- [<span data-ttu-id="1e98b-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="1e98b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1e98b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1e98b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="1e98b-108">**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="1e98b-108">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="1e98b-109">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="1e98b-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1e98b-110">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="1e98b-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="1e98b-111">Descrizione API</span><span class="sxs-lookup"><span data-stu-id="1e98b-111">API description</span></span>

<span data-ttu-id="1e98b-112">Imposta il valore del dispositivo di un computer [specifico.](machine.md)</span><span class="sxs-lookup"><span data-stu-id="1e98b-112">Set the device value of a specific [Machine](machine.md).</span></span><br>
<span data-ttu-id="1e98b-113">Per [altre informazioni, vedi assegnare](tvm-assign-device-value.md) i valori dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="1e98b-113">See [assign device values](tvm-assign-device-value.md) for more information.</span></span>

## <a name="limitations"></a><span data-ttu-id="1e98b-114">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="1e98b-114">Limitations</span></span>

1. <span data-ttu-id="1e98b-115">Puoi pubblicare nei dispositivi l'ultima volta che hai visto in base al periodo di conservazione configurato.</span><span class="sxs-lookup"><span data-stu-id="1e98b-115">You can post on devices last seen according to your configured retention period.</span></span>

2. <span data-ttu-id="1e98b-116">I limiti di frequenza per questa API sono 100 chiamate al minuto e 1500 chiamate all'ora.</span><span class="sxs-lookup"><span data-stu-id="1e98b-116">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="1e98b-117">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="1e98b-117">Permissions</span></span>

<span data-ttu-id="1e98b-118">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="1e98b-118">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="1e98b-119">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi [Usare Microsoft Defender per le API endpoint](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="1e98b-119">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="1e98b-120">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="1e98b-120">Permission type</span></span> |    <span data-ttu-id="1e98b-121">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="1e98b-121">Permission</span></span>    |    <span data-ttu-id="1e98b-122">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="1e98b-122">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="1e98b-123">Applicazione</span><span class="sxs-lookup"><span data-stu-id="1e98b-123">Application</span></span> |    <span data-ttu-id="1e98b-124">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="1e98b-124">Machine.ReadWrite.All</span></span> |    <span data-ttu-id="1e98b-125">"Leggere e scrivere tutte le informazioni sul computer"</span><span class="sxs-lookup"><span data-stu-id="1e98b-125">'Read and write all machine information'</span></span>
<span data-ttu-id="1e98b-126">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="1e98b-126">Delegated (work or school account)</span></span> | <span data-ttu-id="1e98b-127">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="1e98b-127">Machine.ReadWrite</span></span> | <span data-ttu-id="1e98b-128">"Leggere e scrivere informazioni sul computer"</span><span class="sxs-lookup"><span data-stu-id="1e98b-128">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="1e98b-129">Quando si ottiene un token utilizzando le credenziali utente:</span><span class="sxs-lookup"><span data-stu-id="1e98b-129">When obtaining a token using user credentials:</span></span>
>
>- <span data-ttu-id="1e98b-130">L'utente deve disporre almeno dell'autorizzazione di ruolo seguente: "Gestisci impostazione di sicurezza".</span><span class="sxs-lookup"><span data-stu-id="1e98b-130">The user needs to have at least the following role permission: 'Manage security setting'.</span></span> <span data-ttu-id="1e98b-131">Per ulteriori informazioni, vedere [Creare e gestire ruoli.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="1e98b-131">For more  (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="1e98b-132">L'utente deve avere accesso al computer in base alle impostazioni del gruppo di computer (per ulteriori informazioni, vedere [Creare](machine-groups.md) e gestire gruppi di computer)</span><span class="sxs-lookup"><span data-stu-id="1e98b-132">User needs to have access to the machine, based on machine group settings (See [Create and manage machine groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="1e98b-133">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="1e98b-133">HTTP request</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/{machineId}/setDeviceValue
```

## <a name="request-headers"></a><span data-ttu-id="1e98b-134">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="1e98b-134">Request headers</span></span>

<span data-ttu-id="1e98b-135">Name</span><span class="sxs-lookup"><span data-stu-id="1e98b-135">Name</span></span> | <span data-ttu-id="1e98b-136">Tipo</span><span class="sxs-lookup"><span data-stu-id="1e98b-136">Type</span></span> | <span data-ttu-id="1e98b-137">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1e98b-137">Description</span></span>
:---|:---|:---
<span data-ttu-id="1e98b-138">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="1e98b-138">Authorization</span></span> | <span data-ttu-id="1e98b-139">Stringa</span><span class="sxs-lookup"><span data-stu-id="1e98b-139">String</span></span> | <span data-ttu-id="1e98b-140">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="1e98b-140">Bearer {token}.</span></span> <span data-ttu-id="1e98b-141">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="1e98b-141">**Required**.</span></span>
<span data-ttu-id="1e98b-142">Content-Type</span><span class="sxs-lookup"><span data-stu-id="1e98b-142">Content-Type</span></span> | <span data-ttu-id="1e98b-143">stringa</span><span class="sxs-lookup"><span data-stu-id="1e98b-143">string</span></span> | <span data-ttu-id="1e98b-144">application/json.</span><span class="sxs-lookup"><span data-stu-id="1e98b-144">application/json.</span></span> <span data-ttu-id="1e98b-145">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="1e98b-145">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="1e98b-146">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="1e98b-146">Request body</span></span>

<span data-ttu-id="1e98b-147">Nel corpo della richiesta, fornire un oggetto JSON con i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="1e98b-147">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="1e98b-148">Parametro</span><span class="sxs-lookup"><span data-stu-id="1e98b-148">Parameter</span></span> |    <span data-ttu-id="1e98b-149">Tipo</span><span class="sxs-lookup"><span data-stu-id="1e98b-149">Type</span></span>    | <span data-ttu-id="1e98b-150">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1e98b-150">Description</span></span>
:---|:---|:---
<span data-ttu-id="1e98b-151">DeviceValue</span><span class="sxs-lookup"><span data-stu-id="1e98b-151">DeviceValue</span></span> |    <span data-ttu-id="1e98b-152">Enum</span><span class="sxs-lookup"><span data-stu-id="1e98b-152">Enum</span></span> |    <span data-ttu-id="1e98b-153">Valore del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1e98b-153">Device value.</span></span> <span data-ttu-id="1e98b-154">I valori consentiti sono: 'Normal', 'Low' e 'High'.</span><span class="sxs-lookup"><span data-stu-id="1e98b-154">Allowed values are: 'Normal', 'Low' and 'High'.</span></span> <span data-ttu-id="1e98b-155">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="1e98b-155">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="1e98b-156">Risposta</span><span class="sxs-lookup"><span data-stu-id="1e98b-156">Response</span></span>

<span data-ttu-id="1e98b-157">Se ha esito positivo, questo metodo restituisce 200 - Ok codice di risposta e computer aggiornato nel corpo della risposta.</span><span class="sxs-lookup"><span data-stu-id="1e98b-157">If successful, this method returns 200 - Ok response code and the updated Machine in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="1e98b-158">Esempio</span><span class="sxs-lookup"><span data-stu-id="1e98b-158">Example</span></span>

<span data-ttu-id="1e98b-159">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="1e98b-159">**Request**</span></span>

<span data-ttu-id="1e98b-160">Ecco un esempio di richiesta che aggiunge tag computer.</span><span class="sxs-lookup"><span data-stu-id="1e98b-160">Here is an example of a request that adds machine tag.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/setDeviceValue
```

```json
{
  "DeviceValue" : "High"
}
```
