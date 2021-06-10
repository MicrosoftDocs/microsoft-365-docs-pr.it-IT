---
title: API delle entità di avviso per l'aggiornamento in batch
description: Scopri come aggiornare gli avvisi di Microsoft Defender for Endpoint in un batch usando questa API. È possibile aggiornare lo stato, la determinazione, la classificazione e le proprietà assignedTo.
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
ms.technology: mde
ms.openlocfilehash: db745c1b12c64baff5bf2c0a212446ce0f773709
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167090"
---
# <a name="batch-update-alerts"></a><span data-ttu-id="aa355-105">Avvisi di aggiornamento in batch</span><span class="sxs-lookup"><span data-stu-id="aa355-105">Batch update alerts</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="aa355-106">**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="aa355-106">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span></span>

- <span data-ttu-id="aa355-107">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="aa355-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="aa355-108">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="aa355-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="aa355-109">Descrizione API</span><span class="sxs-lookup"><span data-stu-id="aa355-109">API description</span></span>
<span data-ttu-id="aa355-110">Aggiorna le proprietà di un batch di [avvisi esistenti.](alerts.md)</span><span class="sxs-lookup"><span data-stu-id="aa355-110">Updates properties of a batch of existing [Alerts](alerts.md).</span></span>
<br><span data-ttu-id="aa355-111">**L'invio di** commenti è disponibile con o senza aggiornare le proprietà.</span><span class="sxs-lookup"><span data-stu-id="aa355-111">Submission of **comment** is available with or without updating properties.</span></span>
<br><span data-ttu-id="aa355-112">Le proprietà aggiornabili sono: `status` `determination` , e `classification` `assignedTo` .</span><span class="sxs-lookup"><span data-stu-id="aa355-112">Updatable properties are: `status`, `determination`, `classification` and `assignedTo`.</span></span>


## <a name="limitations"></a><span data-ttu-id="aa355-113">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="aa355-113">Limitations</span></span>
1. <span data-ttu-id="aa355-114">Puoi aggiornare gli avvisi disponibili nell'API.</span><span class="sxs-lookup"><span data-stu-id="aa355-114">You can update alerts that are available in the API.</span></span> <span data-ttu-id="aa355-115">Per [ulteriori informazioni, vedere Avvisi](get-alerts.md) elenco.</span><span class="sxs-lookup"><span data-stu-id="aa355-115">See [List Alerts](get-alerts.md) for more information.</span></span>
2. <span data-ttu-id="aa355-116">I limiti di frequenza per questa API sono 10 chiamate al minuto e 500 chiamate all'ora.</span><span class="sxs-lookup"><span data-stu-id="aa355-116">Rate limitations for this API are 10 calls per minute and 500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="aa355-117">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="aa355-117">Permissions</span></span>
<span data-ttu-id="aa355-118">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="aa355-118">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="aa355-119">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi [Usare Microsoft Defender per le API endpoint](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="aa355-119">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="aa355-120">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="aa355-120">Permission type</span></span> |   <span data-ttu-id="aa355-121">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="aa355-121">Permission</span></span>  |   <span data-ttu-id="aa355-122">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="aa355-122">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="aa355-123">Applicazione</span><span class="sxs-lookup"><span data-stu-id="aa355-123">Application</span></span> |   <span data-ttu-id="aa355-124">Alerts.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="aa355-124">Alerts.ReadWrite.All</span></span> |  <span data-ttu-id="aa355-125">"Lettura e scrittura di tutti gli avvisi"</span><span class="sxs-lookup"><span data-stu-id="aa355-125">'Read and write all alerts'</span></span>
<span data-ttu-id="aa355-126">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="aa355-126">Delegated (work or school account)</span></span> | <span data-ttu-id="aa355-127">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="aa355-127">Alert.ReadWrite</span></span> | <span data-ttu-id="aa355-128">"Avvisi di lettura e scrittura"</span><span class="sxs-lookup"><span data-stu-id="aa355-128">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="aa355-129">Quando si ottiene un token utilizzando le credenziali utente:</span><span class="sxs-lookup"><span data-stu-id="aa355-129">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="aa355-130">L'utente deve disporre almeno dell'autorizzazione di ruolo seguente: "Analisi degli avvisi" (per ulteriori informazioni, vedere [Creare](user-roles.md) e gestire ruoli)</span><span class="sxs-lookup"><span data-stu-id="aa355-130">The user needs to have at least the following role permission: 'Alerts investigation' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="aa355-131">L'utente deve avere accesso al dispositivo associato all'avviso, in base alle impostazioni del gruppo di dispositivi (per ulteriori informazioni, vedere [Creare](machine-groups.md) e gestire gruppi di dispositivi)</span><span class="sxs-lookup"><span data-stu-id="aa355-131">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="aa355-132">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="aa355-132">HTTP request</span></span>
```http
POST /api/alerts/batchUpdate
```

## <a name="request-headers"></a><span data-ttu-id="aa355-133">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="aa355-133">Request headers</span></span>

<span data-ttu-id="aa355-134">Name</span><span class="sxs-lookup"><span data-stu-id="aa355-134">Name</span></span> | <span data-ttu-id="aa355-135">Tipo</span><span class="sxs-lookup"><span data-stu-id="aa355-135">Type</span></span> | <span data-ttu-id="aa355-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="aa355-136">Description</span></span>
:---|:---|:---
<span data-ttu-id="aa355-137">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="aa355-137">Authorization</span></span> | <span data-ttu-id="aa355-138">Stringa</span><span class="sxs-lookup"><span data-stu-id="aa355-138">String</span></span> | <span data-ttu-id="aa355-139">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="aa355-139">Bearer {token}.</span></span> <span data-ttu-id="aa355-140">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="aa355-140">**Required**.</span></span>
<span data-ttu-id="aa355-141">Content-Type</span><span class="sxs-lookup"><span data-stu-id="aa355-141">Content-Type</span></span> | <span data-ttu-id="aa355-142">Stringa</span><span class="sxs-lookup"><span data-stu-id="aa355-142">String</span></span> | <span data-ttu-id="aa355-143">application/json.</span><span class="sxs-lookup"><span data-stu-id="aa355-143">application/json.</span></span> <span data-ttu-id="aa355-144">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="aa355-144">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="aa355-145">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="aa355-145">Request body</span></span>
<span data-ttu-id="aa355-146">Nel corpo della richiesta specificare gli ID degli avvisi da aggiornare e i valori dei campi rilevanti che si desidera aggiornare per tali avvisi.</span><span class="sxs-lookup"><span data-stu-id="aa355-146">In the request body, supply the IDs of the alerts to be updated and the values of the relevant fields that you wish to update for these alerts.</span></span>
<br><span data-ttu-id="aa355-147">Le proprietà esistenti non incluse nel corpo della richiesta manterranno i valori precedenti o verranno ricalcolate in base alle modifiche apportate ad altri valori di proprietà.</span><span class="sxs-lookup"><span data-stu-id="aa355-147">Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values.</span></span> 
<br><span data-ttu-id="aa355-148">Per ottenere prestazioni ottimali, non è consigliabile includere valori esistenti che non sono stati modificati.</span><span class="sxs-lookup"><span data-stu-id="aa355-148">For best performance you shouldn't include existing values that haven't changed.</span></span>

<span data-ttu-id="aa355-149">Proprietà</span><span class="sxs-lookup"><span data-stu-id="aa355-149">Property</span></span> | <span data-ttu-id="aa355-150">Tipo</span><span class="sxs-lookup"><span data-stu-id="aa355-150">Type</span></span> | <span data-ttu-id="aa355-151">Descrizione</span><span class="sxs-lookup"><span data-stu-id="aa355-151">Description</span></span>
:---|:---|:---
<span data-ttu-id="aa355-152">alertIds</span><span class="sxs-lookup"><span data-stu-id="aa355-152">alertIds</span></span> | <span data-ttu-id="aa355-153">Stringa &lt; elenco&gt;</span><span class="sxs-lookup"><span data-stu-id="aa355-153">List&lt;String&gt;</span></span>| <span data-ttu-id="aa355-154">Elenco degli ID degli avvisi da aggiornare.</span><span class="sxs-lookup"><span data-stu-id="aa355-154">A list of the IDs of the alerts to be updated.</span></span> <span data-ttu-id="aa355-155">**Obbligatorio**</span><span class="sxs-lookup"><span data-stu-id="aa355-155">**Required**</span></span>
<span data-ttu-id="aa355-156">status</span><span class="sxs-lookup"><span data-stu-id="aa355-156">status</span></span> | <span data-ttu-id="aa355-157">Stringa</span><span class="sxs-lookup"><span data-stu-id="aa355-157">String</span></span> | <span data-ttu-id="aa355-158">Specifica lo stato aggiornato degli avvisi specificati.</span><span class="sxs-lookup"><span data-stu-id="aa355-158">Specifies the updated status of the specified alerts.</span></span> <span data-ttu-id="aa355-159">I valori delle proprietà sono: 'New', 'InProgress' e 'Resolved'.</span><span class="sxs-lookup"><span data-stu-id="aa355-159">The property values are: 'New', 'InProgress' and 'Resolved'.</span></span>
<span data-ttu-id="aa355-160">assignedTo</span><span class="sxs-lookup"><span data-stu-id="aa355-160">assignedTo</span></span> | <span data-ttu-id="aa355-161">Stringa</span><span class="sxs-lookup"><span data-stu-id="aa355-161">String</span></span> | <span data-ttu-id="aa355-162">Proprietario degli avvisi specificati</span><span class="sxs-lookup"><span data-stu-id="aa355-162">Owner of the specified alerts</span></span>
<span data-ttu-id="aa355-163">classificazione</span><span class="sxs-lookup"><span data-stu-id="aa355-163">classification</span></span> | <span data-ttu-id="aa355-164">Stringa</span><span class="sxs-lookup"><span data-stu-id="aa355-164">String</span></span> | <span data-ttu-id="aa355-165">Specifica la specifica degli avvisi specificati.</span><span class="sxs-lookup"><span data-stu-id="aa355-165">Specifies the specification of the specified alerts.</span></span> <span data-ttu-id="aa355-166">I valori delle proprietà sono: 'Unknown', 'FalsePositive', 'TruePositive'.</span><span class="sxs-lookup"><span data-stu-id="aa355-166">The property values are: 'Unknown', 'FalsePositive', 'TruePositive'.</span></span> 
<span data-ttu-id="aa355-167">determinazione</span><span class="sxs-lookup"><span data-stu-id="aa355-167">determination</span></span> | <span data-ttu-id="aa355-168">Stringa</span><span class="sxs-lookup"><span data-stu-id="aa355-168">String</span></span> | <span data-ttu-id="aa355-169">Specifica la determinazione degli avvisi specificati.</span><span class="sxs-lookup"><span data-stu-id="aa355-169">Specifies the determination of the specified alerts.</span></span> <span data-ttu-id="aa355-170">I valori delle proprietà sono: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'</span><span class="sxs-lookup"><span data-stu-id="aa355-170">The property values are: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'</span></span>
<span data-ttu-id="aa355-171">comment</span><span class="sxs-lookup"><span data-stu-id="aa355-171">comment</span></span> | <span data-ttu-id="aa355-172">Stringa</span><span class="sxs-lookup"><span data-stu-id="aa355-172">String</span></span> | <span data-ttu-id="aa355-173">Commento da aggiungere agli avvisi specificati.</span><span class="sxs-lookup"><span data-stu-id="aa355-173">Comment to be added to the specified alerts.</span></span>

## <a name="response"></a><span data-ttu-id="aa355-174">Risposta</span><span class="sxs-lookup"><span data-stu-id="aa355-174">Response</span></span>
<span data-ttu-id="aa355-175">Se ha esito positivo, questo metodo restituisce 200 OK, con un corpo di risposta vuoto.</span><span class="sxs-lookup"><span data-stu-id="aa355-175">If successful, this method returns 200 OK, with an empty response body.</span></span>


## <a name="example"></a><span data-ttu-id="aa355-176">Esempio</span><span class="sxs-lookup"><span data-stu-id="aa355-176">Example</span></span>

<span data-ttu-id="aa355-177">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="aa355-177">**Request**</span></span>

<span data-ttu-id="aa355-178">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="aa355-178">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/alerts/batchUpdate
```

```json
{
    "alertIds": ["da637399794050273582_760707377", "da637399989469816469_51697947354"],
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "FalsePositive",
    "determination": "Malware",
    "comment": "Resolve my alert and assign to secop2"
}
```
