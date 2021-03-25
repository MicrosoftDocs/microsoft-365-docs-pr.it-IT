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
ms.technology: mde
ms.openlocfilehash: 4bdbfbb20f3abb9829b2c8be83b9eaa6ec92cde7
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187224"
---
# <a name="start-investigation-api"></a><span data-ttu-id="89921-104">API di avvio dell'analisi</span><span class="sxs-lookup"><span data-stu-id="89921-104">Start Investigation API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="89921-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="89921-105">**Applies to:**</span></span>
- [<span data-ttu-id="89921-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="89921-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="89921-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="89921-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="89921-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="89921-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="89921-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="89921-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="89921-110">Descrizione API</span><span class="sxs-lookup"><span data-stu-id="89921-110">API description</span></span>
<span data-ttu-id="89921-111">Avviare un'indagine automatizzata su un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="89921-111">Start automated investigation on a device.</span></span>
<br><span data-ttu-id="89921-112">Per [ulteriori informazioni, vedere](automated-investigations.md) Panoramica delle indagini automatizzate.</span><span class="sxs-lookup"><span data-stu-id="89921-112">See [Overview of automated investigations](automated-investigations.md) for more information.</span></span>


## <a name="limitations"></a><span data-ttu-id="89921-113">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="89921-113">Limitations</span></span>
1. <span data-ttu-id="89921-114">I limiti di frequenza per questa API sono 50 chiamate all'ora.</span><span class="sxs-lookup"><span data-stu-id="89921-114">Rate limitations for this API are 50 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="89921-115">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="89921-115">Permissions</span></span>
<span data-ttu-id="89921-116">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="89921-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="89921-117">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi [Usare Microsoft Defender per le API endpoint](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="89921-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="89921-118">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="89921-118">Permission type</span></span> |   <span data-ttu-id="89921-119">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="89921-119">Permission</span></span>  |   <span data-ttu-id="89921-120">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="89921-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="89921-121">Applicazione</span><span class="sxs-lookup"><span data-stu-id="89921-121">Application</span></span> |   <span data-ttu-id="89921-122">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="89921-122">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="89921-123">"Lettura e scrittura di tutti gli avvisi"</span><span class="sxs-lookup"><span data-stu-id="89921-123">'Read and write all alerts'</span></span>
<span data-ttu-id="89921-124">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="89921-124">Delegated (work or school account)</span></span> | <span data-ttu-id="89921-125">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="89921-125">Alert.ReadWrite</span></span> | <span data-ttu-id="89921-126">"Avvisi di lettura e scrittura"</span><span class="sxs-lookup"><span data-stu-id="89921-126">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="89921-127">Quando si ottiene un token utilizzando le credenziali utente:</span><span class="sxs-lookup"><span data-stu-id="89921-127">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="89921-128">L'utente deve disporre almeno dell'autorizzazione di ruolo seguente: "Azioni di correzione attive" (per ulteriori informazioni, vedere [Creare](user-roles.md) e gestire ruoli)</span><span class="sxs-lookup"><span data-stu-id="89921-128">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="89921-129">L'utente deve avere accesso al dispositivo in base alle impostazioni del gruppo di dispositivi (per ulteriori informazioni, vedere [Creare](machine-groups.md) e gestire gruppi di dispositivi)</span><span class="sxs-lookup"><span data-stu-id="89921-129">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>


## <a name="http-request"></a><span data-ttu-id="89921-130">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="89921-130">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/startInvestigation
```

## <a name="request-headers"></a><span data-ttu-id="89921-131">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="89921-131">Request headers</span></span>

<span data-ttu-id="89921-132">Name</span><span class="sxs-lookup"><span data-stu-id="89921-132">Name</span></span> | <span data-ttu-id="89921-133">Tipo</span><span class="sxs-lookup"><span data-stu-id="89921-133">Type</span></span> | <span data-ttu-id="89921-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="89921-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="89921-135">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="89921-135">Authorization</span></span> | <span data-ttu-id="89921-136">Stringa</span><span class="sxs-lookup"><span data-stu-id="89921-136">String</span></span> | <span data-ttu-id="89921-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="89921-137">Bearer {token}.</span></span> <span data-ttu-id="89921-138">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="89921-138">**Required**.</span></span>
<span data-ttu-id="89921-139">Content-Type</span><span class="sxs-lookup"><span data-stu-id="89921-139">Content-Type</span></span> | <span data-ttu-id="89921-140">stringa</span><span class="sxs-lookup"><span data-stu-id="89921-140">string</span></span> | <span data-ttu-id="89921-141">application/json.</span><span class="sxs-lookup"><span data-stu-id="89921-141">application/json.</span></span> <span data-ttu-id="89921-142">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="89921-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="89921-143">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="89921-143">Request body</span></span>
<span data-ttu-id="89921-144">Nel corpo della richiesta, fornire un oggetto JSON con i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="89921-144">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="89921-145">Parametro</span><span class="sxs-lookup"><span data-stu-id="89921-145">Parameter</span></span> | <span data-ttu-id="89921-146">Tipo</span><span class="sxs-lookup"><span data-stu-id="89921-146">Type</span></span>    | <span data-ttu-id="89921-147">Descrizione</span><span class="sxs-lookup"><span data-stu-id="89921-147">Description</span></span>
:---|:---|:---
<span data-ttu-id="89921-148">Comment</span><span class="sxs-lookup"><span data-stu-id="89921-148">Comment</span></span> |   <span data-ttu-id="89921-149">Stringa</span><span class="sxs-lookup"><span data-stu-id="89921-149">String</span></span> |    <span data-ttu-id="89921-150">Commento da associare all'azione.</span><span class="sxs-lookup"><span data-stu-id="89921-150">Comment to associate with the action.</span></span> <span data-ttu-id="89921-151">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="89921-151">**Required**.</span></span>


## <a name="response"></a><span data-ttu-id="89921-152">Risposta</span><span class="sxs-lookup"><span data-stu-id="89921-152">Response</span></span>
<span data-ttu-id="89921-153">Se ha esito positivo, questo metodo restituisce 201 - Codice di risposta creato [e Analisi](investigation.md) nel corpo della risposta.</span><span class="sxs-lookup"><span data-stu-id="89921-153">If successful, this method returns 201 - Created response code and [Investigation](investigation.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="89921-154">Esempio</span><span class="sxs-lookup"><span data-stu-id="89921-154">Example</span></span>

<span data-ttu-id="89921-155">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="89921-155">**Request**</span></span>

<span data-ttu-id="89921-156">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="89921-156">Here is an example of the request.</span></span>

```https
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/startInvestigation
```

```json
{
  "Comment": "Test investigation"
}
```
