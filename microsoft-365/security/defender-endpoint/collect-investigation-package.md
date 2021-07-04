---
title: API per la raccolta dei pacchetti di analisi
description: Usa questa API per creare chiamate correlate alla raccolta di un pacchetto di indagine da un dispositivo.
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
ms.openlocfilehash: 4cf60ea73ea907be9c10b2dd9562a0ea60127f2d
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289896"
---
# <a name="collect-investigation-package-api"></a><span data-ttu-id="8d204-104">API per la raccolta dei pacchetti di analisi</span><span class="sxs-lookup"><span data-stu-id="8d204-104">Collect investigation package API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8d204-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="8d204-105">**Applies to:**</span></span>
- [<span data-ttu-id="8d204-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="8d204-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8d204-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8d204-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


- <span data-ttu-id="8d204-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="8d204-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="8d204-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="8d204-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="8d204-110">Descrizione API</span><span class="sxs-lookup"><span data-stu-id="8d204-110">API description</span></span>

<span data-ttu-id="8d204-111">Raccogliere il pacchetto di analisi da un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8d204-111">Collect investigation package from a device.</span></span>

## <a name="limitations"></a><span data-ttu-id="8d204-112">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="8d204-112">Limitations</span></span>

1. <span data-ttu-id="8d204-113">I limiti di frequenza per questa API sono 100 chiamate al minuto e 1500 chiamate all'ora.</span><span class="sxs-lookup"><span data-stu-id="8d204-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="8d204-114">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="8d204-114">Permissions</span></span>

<span data-ttu-id="8d204-115">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="8d204-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="8d204-116">Per altre informazioni, incluso come scegliere le autorizzazioni, vedi [Usare Defender per le API endpoint](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="8d204-116">To learn more, including how to choose permissions, see [Use Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="8d204-117">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="8d204-117">Permission type</span></span> | <span data-ttu-id="8d204-118">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="8d204-118">Permission</span></span> | <span data-ttu-id="8d204-119">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="8d204-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="8d204-120">Applicazione</span><span class="sxs-lookup"><span data-stu-id="8d204-120">Application</span></span> | <span data-ttu-id="8d204-121">Machine.CollectForensics</span><span class="sxs-lookup"><span data-stu-id="8d204-121">Machine.CollectForensics</span></span> | <span data-ttu-id="8d204-122">"Raccogliere dati forensi"</span><span class="sxs-lookup"><span data-stu-id="8d204-122">'Collect forensics'</span></span>
<span data-ttu-id="8d204-123">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="8d204-123">Delegated (work or school account)</span></span> | <span data-ttu-id="8d204-124">Machine.CollectForensics</span><span class="sxs-lookup"><span data-stu-id="8d204-124">Machine.CollectForensics</span></span> | <span data-ttu-id="8d204-125">"Raccogliere dati forensi"</span><span class="sxs-lookup"><span data-stu-id="8d204-125">'Collect forensics'</span></span>

> [!NOTE]
> <span data-ttu-id="8d204-126">Quando si ottiene un token utilizzando le credenziali utente:</span><span class="sxs-lookup"><span data-stu-id="8d204-126">When obtaining a token using user credentials:</span></span>
>
> - <span data-ttu-id="8d204-127">L'utente deve disporre almeno dell'autorizzazione di ruolo seguente: 'Alerts Investigation' (Per ulteriori informazioni, vedere [Create and manage roles)](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="8d204-127">The user needs to have at least the following role permission: 'Alerts Investigation' (See [Create and manage roles](user-roles.md) for more information)</span></span>
> - <span data-ttu-id="8d204-128">L'utente deve avere accesso al dispositivo in base alle impostazioni del gruppo di dispositivi (per ulteriori informazioni, vedere [Creare](machine-groups.md) e gestire gruppi di dispositivi)</span><span class="sxs-lookup"><span data-stu-id="8d204-128">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="8d204-129">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="8d204-129">HTTP request</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/{id}/collectInvestigationPackage
```

## <a name="request-headers"></a><span data-ttu-id="8d204-130">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="8d204-130">Request headers</span></span>

<span data-ttu-id="8d204-131">Nome</span><span class="sxs-lookup"><span data-stu-id="8d204-131">Name</span></span> | <span data-ttu-id="8d204-132">Tipo</span><span class="sxs-lookup"><span data-stu-id="8d204-132">Type</span></span> | <span data-ttu-id="8d204-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8d204-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="8d204-134">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="8d204-134">Authorization</span></span> | <span data-ttu-id="8d204-135">Stringa</span><span class="sxs-lookup"><span data-stu-id="8d204-135">String</span></span> | <span data-ttu-id="8d204-136">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="8d204-136">Bearer {token}.</span></span> <span data-ttu-id="8d204-137">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="8d204-137">**Required**.</span></span>
<span data-ttu-id="8d204-138">Content-Type</span><span class="sxs-lookup"><span data-stu-id="8d204-138">Content-Type</span></span> | <span data-ttu-id="8d204-139">stringa</span><span class="sxs-lookup"><span data-stu-id="8d204-139">string</span></span> | <span data-ttu-id="8d204-140">application/json.</span><span class="sxs-lookup"><span data-stu-id="8d204-140">application/json.</span></span> <span data-ttu-id="8d204-141">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="8d204-141">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="8d204-142">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="8d204-142">Request body</span></span>

<span data-ttu-id="8d204-143">Nel corpo della richiesta, fornire un oggetto JSON con i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="8d204-143">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="8d204-144">Parametro</span><span class="sxs-lookup"><span data-stu-id="8d204-144">Parameter</span></span> | <span data-ttu-id="8d204-145">Tipo</span><span class="sxs-lookup"><span data-stu-id="8d204-145">Type</span></span> | <span data-ttu-id="8d204-146">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8d204-146">Description</span></span>
:---|:---|:---
<span data-ttu-id="8d204-147">Comment</span><span class="sxs-lookup"><span data-stu-id="8d204-147">Comment</span></span> | <span data-ttu-id="8d204-148">Stringa</span><span class="sxs-lookup"><span data-stu-id="8d204-148">String</span></span> | <span data-ttu-id="8d204-149">Commento da associare all'azione.</span><span class="sxs-lookup"><span data-stu-id="8d204-149">Comment to associate with the action.</span></span> <span data-ttu-id="8d204-150">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="8d204-150">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="8d204-151">Risposta</span><span class="sxs-lookup"><span data-stu-id="8d204-151">Response</span></span>

<span data-ttu-id="8d204-152">Se ha esito positivo, questo metodo restituisce 201 - Codice di risposta creato e [Azione del](machineaction.md) computer nel corpo della risposta.</span><span class="sxs-lookup"><span data-stu-id="8d204-152">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="8d204-153">Esempio</span><span class="sxs-lookup"><span data-stu-id="8d204-153">Example</span></span>

### <a name="request"></a><span data-ttu-id="8d204-154">Richiesta</span><span class="sxs-lookup"><span data-stu-id="8d204-154">Request</span></span>

<span data-ttu-id="8d204-155">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="8d204-155">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/fb9ab6be3965095a09c057be7c90f0a2/collectInvestigationPackage
```

```json
{
  "Comment": "Collect forensics due to alert 1234"
}
```
