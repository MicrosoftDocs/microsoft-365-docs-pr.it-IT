---
title: API di avvio dell'analisi
description: Usa questa API per avviare l'analisi in un dispositivo.
keywords: api, api del grafico, api supportate, analisi
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
ms.openlocfilehash: b7a6a3e7f6f705f322ee3eb1c1b561bc01c55d29
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770890"
---
# <a name="start-investigation-api"></a><span data-ttu-id="db5b0-104">API di avvio dell'analisi</span><span class="sxs-lookup"><span data-stu-id="db5b0-104">Start Investigation API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="db5b0-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="db5b0-105">**Applies to:**</span></span>
- [<span data-ttu-id="db5b0-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="db5b0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="db5b0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="db5b0-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="db5b0-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="db5b0-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="db5b0-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="db5b0-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="db5b0-110">Descrizione API</span><span class="sxs-lookup"><span data-stu-id="db5b0-110">API description</span></span>
<span data-ttu-id="db5b0-111">Avviare un'indagine automatizzata su un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="db5b0-111">Start automated investigation on a device.</span></span>
<br><span data-ttu-id="db5b0-112">Per [ulteriori informazioni, vedere](automated-investigations.md) Panoramica delle indagini automatizzate.</span><span class="sxs-lookup"><span data-stu-id="db5b0-112">See [Overview of automated investigations](automated-investigations.md) for more information.</span></span>


## <a name="limitations"></a><span data-ttu-id="db5b0-113">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="db5b0-113">Limitations</span></span>
1. <span data-ttu-id="db5b0-114">I limiti di frequenza per questa API sono 50 chiamate all'ora.</span><span class="sxs-lookup"><span data-stu-id="db5b0-114">Rate limitations for this API are 50 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="db5b0-115">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="db5b0-115">Permissions</span></span>
<span data-ttu-id="db5b0-116">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="db5b0-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="db5b0-117">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi [Usare Microsoft Defender per le API endpoint](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="db5b0-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="db5b0-118">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="db5b0-118">Permission type</span></span> |   <span data-ttu-id="db5b0-119">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="db5b0-119">Permission</span></span>  |   <span data-ttu-id="db5b0-120">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="db5b0-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="db5b0-121">Applicazione</span><span class="sxs-lookup"><span data-stu-id="db5b0-121">Application</span></span> |   <span data-ttu-id="db5b0-122">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="db5b0-122">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="db5b0-123">"Lettura e scrittura di tutti gli avvisi"</span><span class="sxs-lookup"><span data-stu-id="db5b0-123">'Read and write all alerts'</span></span>
<span data-ttu-id="db5b0-124">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="db5b0-124">Delegated (work or school account)</span></span> | <span data-ttu-id="db5b0-125">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="db5b0-125">Alert.ReadWrite</span></span> | <span data-ttu-id="db5b0-126">"Avvisi di lettura e scrittura"</span><span class="sxs-lookup"><span data-stu-id="db5b0-126">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="db5b0-127">Quando si ottiene un token utilizzando le credenziali utente:</span><span class="sxs-lookup"><span data-stu-id="db5b0-127">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="db5b0-128">L'utente deve disporre almeno dell'autorizzazione di ruolo seguente: "Azioni di correzione attive" (per ulteriori informazioni, vedere [Creare](user-roles.md) e gestire ruoli)</span><span class="sxs-lookup"><span data-stu-id="db5b0-128">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="db5b0-129">L'utente deve avere accesso al dispositivo in base alle impostazioni del gruppo di dispositivi (per ulteriori informazioni, vedere [Creare](machine-groups.md) e gestire gruppi di dispositivi)</span><span class="sxs-lookup"><span data-stu-id="db5b0-129">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>


## <a name="http-request"></a><span data-ttu-id="db5b0-130">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="db5b0-130">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/startInvestigation
```

## <a name="request-headers"></a><span data-ttu-id="db5b0-131">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="db5b0-131">Request headers</span></span>

<span data-ttu-id="db5b0-132">Name</span><span class="sxs-lookup"><span data-stu-id="db5b0-132">Name</span></span> | <span data-ttu-id="db5b0-133">Tipo</span><span class="sxs-lookup"><span data-stu-id="db5b0-133">Type</span></span> | <span data-ttu-id="db5b0-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="db5b0-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="db5b0-135">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="db5b0-135">Authorization</span></span> | <span data-ttu-id="db5b0-136">Stringa</span><span class="sxs-lookup"><span data-stu-id="db5b0-136">String</span></span> | <span data-ttu-id="db5b0-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="db5b0-137">Bearer {token}.</span></span> <span data-ttu-id="db5b0-138">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="db5b0-138">**Required**.</span></span>
<span data-ttu-id="db5b0-139">Content-Type</span><span class="sxs-lookup"><span data-stu-id="db5b0-139">Content-Type</span></span> | <span data-ttu-id="db5b0-140">stringa</span><span class="sxs-lookup"><span data-stu-id="db5b0-140">string</span></span> | <span data-ttu-id="db5b0-141">application/json.</span><span class="sxs-lookup"><span data-stu-id="db5b0-141">application/json.</span></span> <span data-ttu-id="db5b0-142">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="db5b0-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="db5b0-143">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="db5b0-143">Request body</span></span>
<span data-ttu-id="db5b0-144">Nel corpo della richiesta, fornire un oggetto JSON con i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="db5b0-144">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="db5b0-145">Parametro</span><span class="sxs-lookup"><span data-stu-id="db5b0-145">Parameter</span></span> | <span data-ttu-id="db5b0-146">Tipo</span><span class="sxs-lookup"><span data-stu-id="db5b0-146">Type</span></span>    | <span data-ttu-id="db5b0-147">Descrizione</span><span class="sxs-lookup"><span data-stu-id="db5b0-147">Description</span></span>
:---|:---|:---
<span data-ttu-id="db5b0-148">Comment</span><span class="sxs-lookup"><span data-stu-id="db5b0-148">Comment</span></span> |   <span data-ttu-id="db5b0-149">Stringa</span><span class="sxs-lookup"><span data-stu-id="db5b0-149">String</span></span> |    <span data-ttu-id="db5b0-150">Commento da associare all'azione.</span><span class="sxs-lookup"><span data-stu-id="db5b0-150">Comment to associate with the action.</span></span> <span data-ttu-id="db5b0-151">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="db5b0-151">**Required**.</span></span>


## <a name="response"></a><span data-ttu-id="db5b0-152">Risposta</span><span class="sxs-lookup"><span data-stu-id="db5b0-152">Response</span></span>
<span data-ttu-id="db5b0-153">Se ha esito positivo, questo metodo restituisce 201 - Codice di risposta creato [e Analisi](investigation.md) nel corpo della risposta.</span><span class="sxs-lookup"><span data-stu-id="db5b0-153">If successful, this method returns 201 - Created response code and [Investigation](investigation.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="db5b0-154">Esempio</span><span class="sxs-lookup"><span data-stu-id="db5b0-154">Example</span></span>

<span data-ttu-id="db5b0-155">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="db5b0-155">**Request**</span></span>

<span data-ttu-id="db5b0-156">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="db5b0-156">Here is an example of the request.</span></span>

```https
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/startInvestigation
```

```json
{
  "Comment": "Test investigation"
}
```
