---
title: API del computer offboard
description: Scopri come usare un'API per eseguire l'offboard di un dispositivo da Microsoft Defender per Endpoint.
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
ms.openlocfilehash: 03a1ef11224021703a6f33f82fa2c4f135a317a7
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934178"
---
# <a name="offboard-machine-api"></a><span data-ttu-id="399b0-104">API del computer offboard</span><span class="sxs-lookup"><span data-stu-id="399b0-104">Offboard machine API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="399b0-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="399b0-105">**Applies to:**</span></span>
- [<span data-ttu-id="399b0-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="399b0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="399b0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="399b0-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="399b0-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="399b0-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="399b0-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="399b0-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 



[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="399b0-110">Descrizione API</span><span class="sxs-lookup"><span data-stu-id="399b0-110">API description</span></span>
<span data-ttu-id="399b0-111">Dispositivo offboard da Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="399b0-111">Offboard device from Defender for Endpoint.</span></span>


## <a name="limitations"></a><span data-ttu-id="399b0-112">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="399b0-112">Limitations</span></span>
 - <span data-ttu-id="399b0-113">I limiti di frequenza per questa API sono 100 chiamate al minuto e 1500 chiamate all'ora.</span><span class="sxs-lookup"><span data-stu-id="399b0-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Machine actions note](../../includes/machineactionsnote.md)]

>[!Note]
> <span data-ttu-id="399b0-114">Questa API è supportata in Windows 10, versione 1703 e successive o Windows Server 2019 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="399b0-114">This API is supported on Windows 10, version 1703 and later, or Windows Server 2019 and later.</span></span> <span data-ttu-id="399b0-115">Questa API non è supportata nei dispositivi MacOS o Linux.</span><span class="sxs-lookup"><span data-stu-id="399b0-115">This API is not supported on MacOS or Linux devices.</span></span>

## <a name="permissions"></a><span data-ttu-id="399b0-116">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="399b0-116">Permissions</span></span>
<span data-ttu-id="399b0-117">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="399b0-117">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="399b0-118">Per altre informazioni, incluso come scegliere le autorizzazioni, vedi [Usare Defender per le API endpoint](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="399b0-118">To learn more, including how to choose permissions, see [Use Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="399b0-119">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="399b0-119">Permission type</span></span> |   <span data-ttu-id="399b0-120">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="399b0-120">Permission</span></span>  |   <span data-ttu-id="399b0-121">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="399b0-121">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="399b0-122">Applicazione</span><span class="sxs-lookup"><span data-stu-id="399b0-122">Application</span></span> |   <span data-ttu-id="399b0-123">Machine.Offboard</span><span class="sxs-lookup"><span data-stu-id="399b0-123">Machine.Offboard</span></span> |  <span data-ttu-id="399b0-124">"Computer offboard"</span><span class="sxs-lookup"><span data-stu-id="399b0-124">'Offboard machine'</span></span>
<span data-ttu-id="399b0-125">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="399b0-125">Delegated (work or school account)</span></span> |    <span data-ttu-id="399b0-126">Machine.Offboard</span><span class="sxs-lookup"><span data-stu-id="399b0-126">Machine.Offboard</span></span> |  <span data-ttu-id="399b0-127">"Computer offboard"</span><span class="sxs-lookup"><span data-stu-id="399b0-127">'Offboard machine'</span></span>

>[!Note]
> <span data-ttu-id="399b0-128">Quando si ottiene un token utilizzando le credenziali utente:</span><span class="sxs-lookup"><span data-stu-id="399b0-128">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="399b0-129">L'utente deve avere il ruolo AD "Amministratore globale"</span><span class="sxs-lookup"><span data-stu-id="399b0-129">The user needs to 'Global Admin' AD role</span></span>
>- <span data-ttu-id="399b0-130">L'utente deve avere accesso al dispositivo in base alle impostazioni del gruppo di dispositivi (per ulteriori informazioni, vedere [Creare](machine-groups.md) e gestire gruppi di dispositivi)</span><span class="sxs-lookup"><span data-stu-id="399b0-130">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="399b0-131">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="399b0-131">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/offboard
```

## <a name="request-headers"></a><span data-ttu-id="399b0-132">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="399b0-132">Request headers</span></span>

<span data-ttu-id="399b0-133">Name</span><span class="sxs-lookup"><span data-stu-id="399b0-133">Name</span></span> | <span data-ttu-id="399b0-134">Tipo</span><span class="sxs-lookup"><span data-stu-id="399b0-134">Type</span></span> | <span data-ttu-id="399b0-135">Descrizione</span><span class="sxs-lookup"><span data-stu-id="399b0-135">Description</span></span>
:---|:---|:---
<span data-ttu-id="399b0-136">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="399b0-136">Authorization</span></span> | <span data-ttu-id="399b0-137">Stringa</span><span class="sxs-lookup"><span data-stu-id="399b0-137">String</span></span> | <span data-ttu-id="399b0-138">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="399b0-138">Bearer {token}.</span></span> <span data-ttu-id="399b0-139">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="399b0-139">**Required**.</span></span>
<span data-ttu-id="399b0-140">Content-Type</span><span class="sxs-lookup"><span data-stu-id="399b0-140">Content-Type</span></span> | <span data-ttu-id="399b0-141">stringa</span><span class="sxs-lookup"><span data-stu-id="399b0-141">string</span></span> | <span data-ttu-id="399b0-142">application/json.</span><span class="sxs-lookup"><span data-stu-id="399b0-142">application/json.</span></span> <span data-ttu-id="399b0-143">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="399b0-143">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="399b0-144">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="399b0-144">Request body</span></span>
<span data-ttu-id="399b0-145">Nel corpo della richiesta, fornire un oggetto JSON con i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="399b0-145">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="399b0-146">Parametro</span><span class="sxs-lookup"><span data-stu-id="399b0-146">Parameter</span></span> | <span data-ttu-id="399b0-147">Tipo</span><span class="sxs-lookup"><span data-stu-id="399b0-147">Type</span></span>    | <span data-ttu-id="399b0-148">Descrizione</span><span class="sxs-lookup"><span data-stu-id="399b0-148">Description</span></span>
:---|:---|:---
<span data-ttu-id="399b0-149">Comment</span><span class="sxs-lookup"><span data-stu-id="399b0-149">Comment</span></span> |   <span data-ttu-id="399b0-150">Stringa</span><span class="sxs-lookup"><span data-stu-id="399b0-150">String</span></span> |    <span data-ttu-id="399b0-151">Commento da associare all'azione.</span><span class="sxs-lookup"><span data-stu-id="399b0-151">Comment to associate with the action.</span></span> <span data-ttu-id="399b0-152">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="399b0-152">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="399b0-153">Risposta</span><span class="sxs-lookup"><span data-stu-id="399b0-153">Response</span></span>
<span data-ttu-id="399b0-154">Se ha esito positivo, questo metodo restituisce 201 - Codice di risposta creato e [Azione del](machineaction.md) computer nel corpo della risposta.</span><span class="sxs-lookup"><span data-stu-id="399b0-154">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="399b0-155">Esempio</span><span class="sxs-lookup"><span data-stu-id="399b0-155">Example</span></span>

<span data-ttu-id="399b0-156">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="399b0-156">**Request**</span></span>

<span data-ttu-id="399b0-157">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="399b0-157">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/offboard
```

```json
{
  "Comment": "Offboard machine by automation"
}
```
