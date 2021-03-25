---
title: Eseguire l'API di analisi antivirus
description: Usa questa API per creare chiamate correlate all'esecuzione di un'analisi antivirus in un dispositivo.
keywords: api, api del grafico, api supportate, rimuovere il dispositivo dall'isolamento
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
ms.openlocfilehash: d0db45daa786c1a44272e4d02153af3fe658e781
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200210"
---
# <a name="run-antivirus-scan-api"></a><span data-ttu-id="40d04-104">Eseguire l'API di analisi antivirus</span><span class="sxs-lookup"><span data-stu-id="40d04-104">Run antivirus scan API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="40d04-105">**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="40d04-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="40d04-106">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="40d04-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="40d04-107">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="40d04-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="40d04-108">Descrizione API</span><span class="sxs-lookup"><span data-stu-id="40d04-108">API description</span></span>
<span data-ttu-id="40d04-109">Avviare l'analisi di Microsoft Defender Antivirus in un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="40d04-109">Initiate Microsoft Defender Antivirus scan on a device.</span></span>


## <a name="limitations"></a><span data-ttu-id="40d04-110">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="40d04-110">Limitations</span></span>
1. <span data-ttu-id="40d04-111">I limiti di frequenza per questa API sono 100 chiamate al minuto e 1500 chiamate all'ora.</span><span class="sxs-lookup"><span data-stu-id="40d04-111">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a><span data-ttu-id="40d04-112">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="40d04-112">Permissions</span></span>
<span data-ttu-id="40d04-113">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="40d04-113">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="40d04-114">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi [Usare Microsoft Defender per le API endpoint](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="40d04-114">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="40d04-115">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="40d04-115">Permission type</span></span> |   <span data-ttu-id="40d04-116">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="40d04-116">Permission</span></span>  |   <span data-ttu-id="40d04-117">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="40d04-117">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="40d04-118">Applicazione</span><span class="sxs-lookup"><span data-stu-id="40d04-118">Application</span></span> |   <span data-ttu-id="40d04-119">Machine.Scan</span><span class="sxs-lookup"><span data-stu-id="40d04-119">Machine.Scan</span></span> |  <span data-ttu-id="40d04-120">"Computer di analisi"</span><span class="sxs-lookup"><span data-stu-id="40d04-120">'Scan machine'</span></span>
<span data-ttu-id="40d04-121">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="40d04-121">Delegated (work or school account)</span></span> |    <span data-ttu-id="40d04-122">Machine.Scan</span><span class="sxs-lookup"><span data-stu-id="40d04-122">Machine.Scan</span></span> |  <span data-ttu-id="40d04-123">"Computer di analisi"</span><span class="sxs-lookup"><span data-stu-id="40d04-123">'Scan machine'</span></span>

>[!Note]
> <span data-ttu-id="40d04-124">Quando si ottiene un token utilizzando le credenziali utente:</span><span class="sxs-lookup"><span data-stu-id="40d04-124">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="40d04-125">L'utente deve disporre almeno dell'autorizzazione di ruolo seguente: "Azioni di correzione attive" (per ulteriori informazioni, vedere [Creare](user-roles.md) e gestire ruoli)</span><span class="sxs-lookup"><span data-stu-id="40d04-125">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="40d04-126">L'utente deve avere accesso al dispositivo in base alle impostazioni del gruppo di dispositivi (per ulteriori informazioni, vedere [Creare](machine-groups.md) e gestire gruppi di dispositivi)</span><span class="sxs-lookup"><span data-stu-id="40d04-126">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="40d04-127">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="40d04-127">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/runAntiVirusScan
```

## <a name="request-headers"></a><span data-ttu-id="40d04-128">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="40d04-128">Request headers</span></span>

<span data-ttu-id="40d04-129">Name</span><span class="sxs-lookup"><span data-stu-id="40d04-129">Name</span></span> | <span data-ttu-id="40d04-130">Tipo</span><span class="sxs-lookup"><span data-stu-id="40d04-130">Type</span></span> | <span data-ttu-id="40d04-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="40d04-131">Description</span></span>
:---|:---|:---
<span data-ttu-id="40d04-132">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="40d04-132">Authorization</span></span> | <span data-ttu-id="40d04-133">Stringa</span><span class="sxs-lookup"><span data-stu-id="40d04-133">String</span></span> | <span data-ttu-id="40d04-134">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="40d04-134">Bearer {token}.</span></span> <span data-ttu-id="40d04-135">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="40d04-135">**Required**.</span></span>
<span data-ttu-id="40d04-136">Content-Type</span><span class="sxs-lookup"><span data-stu-id="40d04-136">Content-Type</span></span> | <span data-ttu-id="40d04-137">stringa</span><span class="sxs-lookup"><span data-stu-id="40d04-137">string</span></span> | <span data-ttu-id="40d04-138">application/json</span><span class="sxs-lookup"><span data-stu-id="40d04-138">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="40d04-139">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="40d04-139">Request body</span></span>
<span data-ttu-id="40d04-140">Nel corpo della richiesta, fornire un oggetto JSON con i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="40d04-140">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="40d04-141">Parametro</span><span class="sxs-lookup"><span data-stu-id="40d04-141">Parameter</span></span> | <span data-ttu-id="40d04-142">Tipo</span><span class="sxs-lookup"><span data-stu-id="40d04-142">Type</span></span>    | <span data-ttu-id="40d04-143">Descrizione</span><span class="sxs-lookup"><span data-stu-id="40d04-143">Description</span></span>
:---|:---|:---
<span data-ttu-id="40d04-144">Comment</span><span class="sxs-lookup"><span data-stu-id="40d04-144">Comment</span></span> |   <span data-ttu-id="40d04-145">Stringa</span><span class="sxs-lookup"><span data-stu-id="40d04-145">String</span></span> | <span data-ttu-id="40d04-146">Commento da associare all'azione.</span><span class="sxs-lookup"><span data-stu-id="40d04-146">Comment to associate with the action.</span></span> <span data-ttu-id="40d04-147">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="40d04-147">**Required**.</span></span>
<span data-ttu-id="40d04-148">ScanType</span><span class="sxs-lookup"><span data-stu-id="40d04-148">ScanType</span></span>|   <span data-ttu-id="40d04-149">Stringa</span><span class="sxs-lookup"><span data-stu-id="40d04-149">String</span></span>  | <span data-ttu-id="40d04-150">Definisce il tipo di analisi.</span><span class="sxs-lookup"><span data-stu-id="40d04-150">Defines the type of the Scan.</span></span> <span data-ttu-id="40d04-151">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="40d04-151">**Required**.</span></span>

<span data-ttu-id="40d04-152">**ScanType** controlla il tipo di analisi da eseguire e può essere uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="40d04-152">**ScanType** controls the type of scan to perform and can be one of the following:</span></span>

- <span data-ttu-id="40d04-153">**Rapido:** eseguire un'analisi rapida nel dispositivo</span><span class="sxs-lookup"><span data-stu-id="40d04-153">**Quick** – Perform quick scan on the device</span></span>
- <span data-ttu-id="40d04-154">**Completo:** eseguire l'analisi completa nel dispositivo</span><span class="sxs-lookup"><span data-stu-id="40d04-154">**Full** – Perform full scan on the device</span></span>



## <a name="response"></a><span data-ttu-id="40d04-155">Risposta</span><span class="sxs-lookup"><span data-stu-id="40d04-155">Response</span></span>
<span data-ttu-id="40d04-156">Se ha esito positivo, questo metodo restituisce 201, Codice di risposta creato e _Oggetto MachineAction_ nel corpo della risposta.</span><span class="sxs-lookup"><span data-stu-id="40d04-156">If successful, this method returns 201, Created response code and _MachineAction_ object in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="40d04-157">Esempio</span><span class="sxs-lookup"><span data-stu-id="40d04-157">Example</span></span>

<span data-ttu-id="40d04-158">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="40d04-158">**Request**</span></span>

<span data-ttu-id="40d04-159">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="40d04-159">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/runAntiVirusScan 
```

```json
{
  "Comment": "Check machine for viruses due to alert 3212",
  "ScanType": "Full"
}
```

