---
title: API dell'entità computer di aggiornamento
description: Scopri come aggiornare i tag del computer usando questa API. Puoi aggiornare i tag e le proprietà devicevalue.
keywords: api, api del grafico, api supportate, ottenere, avviso, informazioni, id
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
ms.openlocfilehash: 8f08b1fdafd653561ac2aae10a73f37b21874b59
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985752"
---
# <a name="update-machine"></a><span data-ttu-id="9a60f-105">Aggiorna computer</span><span class="sxs-lookup"><span data-stu-id="9a60f-105">Update machine</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9a60f-106">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="9a60f-106">**Applies to:**</span></span>
- [<span data-ttu-id="9a60f-107">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="9a60f-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="9a60f-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9a60f-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="9a60f-109">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="9a60f-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="9a60f-110">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="9a60f-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="9a60f-111">Descrizione API</span><span class="sxs-lookup"><span data-stu-id="9a60f-111">API description</span></span>
<span data-ttu-id="9a60f-112">Aggiorna le proprietà del computer [esistente.](machine.md)</span><span class="sxs-lookup"><span data-stu-id="9a60f-112">Updates properties of existing [Machine](machine.md).</span></span>
<br><span data-ttu-id="9a60f-113">Le proprietà aggiornabili sono: ```machineTags``` e ```deviceValue``` .</span><span class="sxs-lookup"><span data-stu-id="9a60f-113">Updatable properties are: ```machineTags``` and ```deviceValue```.</span></span>


## <a name="limitations"></a><span data-ttu-id="9a60f-114">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="9a60f-114">Limitations</span></span>
1. <span data-ttu-id="9a60f-115">Puoi aggiornare i computer disponibili nell'API.</span><span class="sxs-lookup"><span data-stu-id="9a60f-115">You can update machines that are available in the API.</span></span> 
2. <span data-ttu-id="9a60f-116">Il computer di aggiornamento aggiunge solo tag alla raccolta di tag.</span><span class="sxs-lookup"><span data-stu-id="9a60f-116">Update machine only appends tags to the tag collection.</span></span> <span data-ttu-id="9a60f-117">Se i tag esistono, devono essere inclusi nell'insieme tags nel corpo.</span><span class="sxs-lookup"><span data-stu-id="9a60f-117">If tags exist, they must be included in the tags collection in the body.</span></span>
3. <span data-ttu-id="9a60f-118">I limiti di frequenza per questa API sono 100 chiamate al minuto e 1500 chiamate all'ora.</span><span class="sxs-lookup"><span data-stu-id="9a60f-118">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="9a60f-119">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="9a60f-119">Permissions</span></span>
<span data-ttu-id="9a60f-120">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="9a60f-120">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="9a60f-121">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi [Usare Microsoft Defender per le API endpoint](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="9a60f-121">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="9a60f-122">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="9a60f-122">Permission type</span></span> |   <span data-ttu-id="9a60f-123">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="9a60f-123">Permission</span></span>  |   <span data-ttu-id="9a60f-124">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="9a60f-124">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="9a60f-125">Applicazione</span><span class="sxs-lookup"><span data-stu-id="9a60f-125">Application</span></span> |   <span data-ttu-id="9a60f-126">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="9a60f-126">Machine.ReadWrite.All</span></span> | <span data-ttu-id="9a60f-127">"Leggere e scrivere informazioni sul computer per tutti i computer"</span><span class="sxs-lookup"><span data-stu-id="9a60f-127">'Read and write machine information for all machines'</span></span>
<span data-ttu-id="9a60f-128">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="9a60f-128">Delegated (work or school account)</span></span> | <span data-ttu-id="9a60f-129">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="9a60f-129">Machine.ReadWrite</span></span> | <span data-ttu-id="9a60f-130">"Leggere e scrivere informazioni sul computer"</span><span class="sxs-lookup"><span data-stu-id="9a60f-130">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="9a60f-131">Quando si ottiene un token utilizzando le credenziali utente:</span><span class="sxs-lookup"><span data-stu-id="9a60f-131">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="9a60f-132">L'utente deve disporre almeno dell'autorizzazione di ruolo seguente: "Avvisi indagine".</span><span class="sxs-lookup"><span data-stu-id="9a60f-132">The user needs to have at least the following role permission: 'Alerts investigation'.</span></span> <span data-ttu-id="9a60f-133">Per ulteriori informazioni, vedere [Create and manage roles](user-roles.md).</span><span class="sxs-lookup"><span data-stu-id="9a60f-133">For more information, see [Create and manage roles](user-roles.md).</span></span>
>- <span data-ttu-id="9a60f-134">L'utente deve avere accesso al dispositivo associato all'avviso, in base alle impostazioni del gruppo di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="9a60f-134">The user needs to have access to the device associated with the alert, based on device group settings.</span></span> <span data-ttu-id="9a60f-135">Per altre informazioni, vedi [Creare e gestire gruppi di dispositivi.](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="9a60f-135">For more information, see [Create and manage device groups](machine-groups.md).</span></span>

## <a name="http-request"></a><span data-ttu-id="9a60f-136">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="9a60f-136">HTTP request</span></span>
```
PATCH /api/machines/{machineId}
```

## <a name="request-headers"></a><span data-ttu-id="9a60f-137">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="9a60f-137">Request headers</span></span>

<span data-ttu-id="9a60f-138">Nome</span><span class="sxs-lookup"><span data-stu-id="9a60f-138">Name</span></span> | <span data-ttu-id="9a60f-139">Tipo</span><span class="sxs-lookup"><span data-stu-id="9a60f-139">Type</span></span> | <span data-ttu-id="9a60f-140">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9a60f-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="9a60f-141">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="9a60f-141">Authorization</span></span> | <span data-ttu-id="9a60f-142">Stringa</span><span class="sxs-lookup"><span data-stu-id="9a60f-142">String</span></span> | <span data-ttu-id="9a60f-143">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="9a60f-143">Bearer {token}.</span></span> <span data-ttu-id="9a60f-144">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="9a60f-144">**Required**.</span></span>
<span data-ttu-id="9a60f-145">Content-Type</span><span class="sxs-lookup"><span data-stu-id="9a60f-145">Content-Type</span></span> | <span data-ttu-id="9a60f-146">Stringa</span><span class="sxs-lookup"><span data-stu-id="9a60f-146">String</span></span> | <span data-ttu-id="9a60f-147">application/json.</span><span class="sxs-lookup"><span data-stu-id="9a60f-147">application/json.</span></span> <span data-ttu-id="9a60f-148">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="9a60f-148">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="9a60f-149">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="9a60f-149">Request body</span></span>
<span data-ttu-id="9a60f-150">Nel corpo della richiesta specificare i valori per i campi rilevanti da aggiornare.</span><span class="sxs-lookup"><span data-stu-id="9a60f-150">In the request body, supply the values for the relevant fields that should be updated.</span></span>
<br><span data-ttu-id="9a60f-151">Le proprietà esistenti non incluse nel corpo della richiesta manterranno i valori precedenti o verranno ricalcolate in base alle modifiche apportate ad altri valori di proprietà.</span><span class="sxs-lookup"><span data-stu-id="9a60f-151">Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values.</span></span> 
<br><span data-ttu-id="9a60f-152">Per ottenere prestazioni ottimali, non è consigliabile includere valori esistenti che non sono stati modificate.</span><span class="sxs-lookup"><span data-stu-id="9a60f-152">For best performance, you shouldn't include existing values that haven't change.</span></span>

<span data-ttu-id="9a60f-153">Proprietà</span><span class="sxs-lookup"><span data-stu-id="9a60f-153">Property</span></span> | <span data-ttu-id="9a60f-154">Tipo</span><span class="sxs-lookup"><span data-stu-id="9a60f-154">Type</span></span> | <span data-ttu-id="9a60f-155">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9a60f-155">Description</span></span>
:---|:---|:---
<span data-ttu-id="9a60f-156">machineTags</span><span class="sxs-lookup"><span data-stu-id="9a60f-156">machineTags</span></span> | <span data-ttu-id="9a60f-157">Insieme String</span><span class="sxs-lookup"><span data-stu-id="9a60f-157">String collection</span></span> | <span data-ttu-id="9a60f-158">Set di [tag del](machine.md) computer.</span><span class="sxs-lookup"><span data-stu-id="9a60f-158">Set of [machine](machine.md) tags.</span></span>
<span data-ttu-id="9a60f-159">deviceValue</span><span class="sxs-lookup"><span data-stu-id="9a60f-159">deviceValue</span></span> | <span data-ttu-id="9a60f-160">Enumerazione Nullable</span><span class="sxs-lookup"><span data-stu-id="9a60f-160">Nullable Enum</span></span> | <span data-ttu-id="9a60f-161">Valore [del dispositivo](tvm-assign-device-value.md).</span><span class="sxs-lookup"><span data-stu-id="9a60f-161">The [value of the device](tvm-assign-device-value.md).</span></span> <span data-ttu-id="9a60f-162">I valori possibili sono: 'Normal', 'Low' e 'High'.</span><span class="sxs-lookup"><span data-stu-id="9a60f-162">Possible values are: 'Normal', 'Low' and 'High'.</span></span>

## <a name="response"></a><span data-ttu-id="9a60f-163">Risposta</span><span class="sxs-lookup"><span data-stu-id="9a60f-163">Response</span></span>
<span data-ttu-id="9a60f-164">Se ha esito positivo, questo metodo restituisce [](machine.md) 200 OK e l'entità computer nel corpo della risposta con le proprietà aggiornate.</span><span class="sxs-lookup"><span data-stu-id="9a60f-164">If successful, this method returns 200 OK, and the [machine](machine.md) entity in the response body with the updated properties.</span></span> <span data-ttu-id="9a60f-165">Se la raccolta di tag di computer nel corpo non contiene tag di computer esistenti- 400 Input non valido e un messaggio che informa del tag/i mancante.</span><span class="sxs-lookup"><span data-stu-id="9a60f-165">If machine tags collection in body doesn't contain existing machine tags - 400 Invalid Input and a message informing of the missing tag/s.</span></span>
<span data-ttu-id="9a60f-166">Se il computer con l'ID specificato non è stato trovato - 404 Non trovato.</span><span class="sxs-lookup"><span data-stu-id="9a60f-166">If machine with the specified ID was not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="9a60f-167">Esempio</span><span class="sxs-lookup"><span data-stu-id="9a60f-167">Example</span></span>

<span data-ttu-id="9a60f-168">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="9a60f-168">**Request**</span></span>

<span data-ttu-id="9a60f-169">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="9a60f-169">Here's an example of the request.</span></span>

```http
PATCH https://api.securitycenter.microsoft.com/api/machines/{machineId}
```

```json
{
    "deviceValue": "Normal",
    "machineTags": [
                     "Demo Device",
                     "Generic User Machine - Attack Source",
                     "Windows 10",
                     "Windows Insider - Fast"
    ]
}
```
