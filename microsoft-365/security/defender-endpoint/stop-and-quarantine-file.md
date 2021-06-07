---
title: API per arrestare e mettere in quarantena i file
description: Scopri come interrompere l'esecuzione di un file in un dispositivo ed eliminare il file in Microsoft Defender per Endpoint. Vedi un esempio.
keywords: api, api del grafico, api supportate, file di arresto e quarantena
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
ms.openlocfilehash: ac14f1ecda2b6256dc19223869b8878e6e725b96
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771407"
---
# <a name="stop-and-quarantine-file-api"></a><span data-ttu-id="c9198-105">API per arrestare e mettere in quarantena i file</span><span class="sxs-lookup"><span data-stu-id="c9198-105">Stop and quarantine file API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c9198-106">**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="c9198-106">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="c9198-107">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="c9198-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c9198-108">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="c9198-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="c9198-109">Descrizione API</span><span class="sxs-lookup"><span data-stu-id="c9198-109">API description</span></span>
<span data-ttu-id="c9198-110">Interrompere l'esecuzione di un file in un dispositivo ed eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="c9198-110">Stop execution of a file on a device and delete it.</span></span>


## <a name="limitations"></a><span data-ttu-id="c9198-111">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="c9198-111">Limitations</span></span>
1. <span data-ttu-id="c9198-112">I limiti di frequenza per questa API sono 100 chiamate al minuto e 1500 chiamate all'ora.</span><span class="sxs-lookup"><span data-stu-id="c9198-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a><span data-ttu-id="c9198-113">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="c9198-113">Permissions</span></span>
<span data-ttu-id="c9198-114">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="c9198-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="c9198-115">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi [Usare Microsoft Defender per le API endpoint](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="c9198-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="c9198-116">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="c9198-116">Permission type</span></span> |   <span data-ttu-id="c9198-117">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="c9198-117">Permission</span></span>  |   <span data-ttu-id="c9198-118">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="c9198-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="c9198-119">Applicazione</span><span class="sxs-lookup"><span data-stu-id="c9198-119">Application</span></span> |   <span data-ttu-id="c9198-120">Machine.StopAndQuarantine</span><span class="sxs-lookup"><span data-stu-id="c9198-120">Machine.StopAndQuarantine</span></span> | <span data-ttu-id="c9198-121">"Interrompi e metti in quarantena"</span><span class="sxs-lookup"><span data-stu-id="c9198-121">'Stop And Quarantine'</span></span>
<span data-ttu-id="c9198-122">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="c9198-122">Delegated (work or school account)</span></span> | <span data-ttu-id="c9198-123">Machine.StopAndQuarantine</span><span class="sxs-lookup"><span data-stu-id="c9198-123">Machine.StopAndQuarantine</span></span> | <span data-ttu-id="c9198-124">"Interrompi e metti in quarantena"</span><span class="sxs-lookup"><span data-stu-id="c9198-124">'Stop And Quarantine'</span></span>

>[!Note]
> <span data-ttu-id="c9198-125">Quando si ottiene un token utilizzando le credenziali utente:</span><span class="sxs-lookup"><span data-stu-id="c9198-125">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="c9198-126">L'utente deve disporre almeno dell'autorizzazione di ruolo seguente: "Azioni di correzione attive" (per ulteriori informazioni, vedere [Creare](user-roles.md) e gestire ruoli)</span><span class="sxs-lookup"><span data-stu-id="c9198-126">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="c9198-127">L'utente deve avere accesso al dispositivo in base alle impostazioni del gruppo di dispositivi (per ulteriori informazioni, vedere [Creare](machine-groups.md) e gestire gruppi di dispositivi)</span><span class="sxs-lookup"><span data-stu-id="c9198-127">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="c9198-128">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="c9198-128">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/StopAndQuarantineFile
```

## <a name="request-headers"></a><span data-ttu-id="c9198-129">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="c9198-129">Request headers</span></span>

<span data-ttu-id="c9198-130">Name</span><span class="sxs-lookup"><span data-stu-id="c9198-130">Name</span></span> | <span data-ttu-id="c9198-131">Tipo</span><span class="sxs-lookup"><span data-stu-id="c9198-131">Type</span></span> | <span data-ttu-id="c9198-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c9198-132">Description</span></span>
:---|:---|:---
<span data-ttu-id="c9198-133">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="c9198-133">Authorization</span></span> | <span data-ttu-id="c9198-134">Stringa</span><span class="sxs-lookup"><span data-stu-id="c9198-134">String</span></span> | <span data-ttu-id="c9198-135">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="c9198-135">Bearer {token}.</span></span> <span data-ttu-id="c9198-136">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="c9198-136">**Required**.</span></span>
<span data-ttu-id="c9198-137">Content-Type</span><span class="sxs-lookup"><span data-stu-id="c9198-137">Content-Type</span></span> | <span data-ttu-id="c9198-138">stringa</span><span class="sxs-lookup"><span data-stu-id="c9198-138">string</span></span> | <span data-ttu-id="c9198-139">application/json.</span><span class="sxs-lookup"><span data-stu-id="c9198-139">application/json.</span></span> <span data-ttu-id="c9198-140">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="c9198-140">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="c9198-141">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="c9198-141">Request body</span></span>
<span data-ttu-id="c9198-142">Nel corpo della richiesta, fornire un oggetto JSON con i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="c9198-142">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="c9198-143">Parametro</span><span class="sxs-lookup"><span data-stu-id="c9198-143">Parameter</span></span> | <span data-ttu-id="c9198-144">Tipo</span><span class="sxs-lookup"><span data-stu-id="c9198-144">Type</span></span>    | <span data-ttu-id="c9198-145">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c9198-145">Description</span></span>
:---|:---|:---
<span data-ttu-id="c9198-146">Comment</span><span class="sxs-lookup"><span data-stu-id="c9198-146">Comment</span></span> |   <span data-ttu-id="c9198-147">Stringa</span><span class="sxs-lookup"><span data-stu-id="c9198-147">String</span></span> |    <span data-ttu-id="c9198-148">Commento da associare all'azione.</span><span class="sxs-lookup"><span data-stu-id="c9198-148">Comment to associate with the action.</span></span> <span data-ttu-id="c9198-149">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="c9198-149">**Required**.</span></span>
<span data-ttu-id="c9198-150">Sha1</span><span class="sxs-lookup"><span data-stu-id="c9198-150">Sha1</span></span> |  <span data-ttu-id="c9198-151">Stringa</span><span class="sxs-lookup"><span data-stu-id="c9198-151">String</span></span>   | <span data-ttu-id="c9198-152">Sha1 del file da arrestare e mettere in quarantena nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c9198-152">Sha1 of the file to stop and quarantine on the device.</span></span> <span data-ttu-id="c9198-153">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="c9198-153">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="c9198-154">Risposta</span><span class="sxs-lookup"><span data-stu-id="c9198-154">Response</span></span>
<span data-ttu-id="c9198-155">Se ha esito positivo, questo metodo restituisce 201 - Codice di risposta creato e [Azione del](machineaction.md) computer nel corpo della risposta.</span><span class="sxs-lookup"><span data-stu-id="c9198-155">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="c9198-156">Esempio</span><span class="sxs-lookup"><span data-stu-id="c9198-156">Example</span></span>

<span data-ttu-id="c9198-157">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="c9198-157">**Request**</span></span>

<span data-ttu-id="c9198-158">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="c9198-158">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/StopAndQuarantineFile 
```

```json
{
  "Comment": "Stop and quarantine file on machine due to alert 441688558380765161_2136280442",
  "Sha1": "87662bc3d60e4200ceaf7aae249d1c343f4b83c9"
}

```
