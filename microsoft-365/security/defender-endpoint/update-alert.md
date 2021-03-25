---
title: API dell'entità di avviso di aggiornamento
description: Scopri come aggiornare un avviso di Microsoft Defender ATP usando questa API. È possibile aggiornare lo stato, la determinazione, la classificazione e le proprietà assignedTo.
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
ms.openlocfilehash: 7dd3ab3da34efa6cb954db2a596d7a1e48efedf1
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199310"
---
# <a name="update-alert"></a><span data-ttu-id="64ebb-105">Avviso di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="64ebb-105">Update alert</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="64ebb-106">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="64ebb-106">**Applies to:**</span></span>
- [<span data-ttu-id="64ebb-107">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="64ebb-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="64ebb-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="64ebb-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="64ebb-109">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="64ebb-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="64ebb-110">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="64ebb-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="64ebb-111">Descrizione API</span><span class="sxs-lookup"><span data-stu-id="64ebb-111">API description</span></span>
<span data-ttu-id="64ebb-112">Aggiorna le proprietà dell'oggetto [Alert esistente.](alerts.md)</span><span class="sxs-lookup"><span data-stu-id="64ebb-112">Updates properties of existing [Alert](alerts.md).</span></span>
<br><span data-ttu-id="64ebb-113">**L'invio di** commenti è disponibile con o senza aggiornare le proprietà.</span><span class="sxs-lookup"><span data-stu-id="64ebb-113">Submission of **comment** is available with or without updating properties.</span></span>
<br><span data-ttu-id="64ebb-114">Le proprietà aggiornabili sono: ```status``` ```determination``` , e ```classification``` ```assignedTo``` .</span><span class="sxs-lookup"><span data-stu-id="64ebb-114">Updatable properties are: ```status```, ```determination```, ```classification``` and ```assignedTo```.</span></span>


## <a name="limitations"></a><span data-ttu-id="64ebb-115">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="64ebb-115">Limitations</span></span>
1. <span data-ttu-id="64ebb-116">Puoi aggiornare gli avvisi disponibili nell'API.</span><span class="sxs-lookup"><span data-stu-id="64ebb-116">You can update alerts that available in the API.</span></span> <span data-ttu-id="64ebb-117">Per [ulteriori informazioni, vedere Avvisi](get-alerts.md) elenco.</span><span class="sxs-lookup"><span data-stu-id="64ebb-117">See [List Alerts](get-alerts.md) for more information.</span></span>
2. <span data-ttu-id="64ebb-118">I limiti di frequenza per questa API sono 100 chiamate al minuto e 1500 chiamate all'ora.</span><span class="sxs-lookup"><span data-stu-id="64ebb-118">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="64ebb-119">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="64ebb-119">Permissions</span></span>
<span data-ttu-id="64ebb-120">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="64ebb-120">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="64ebb-121">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi [Usare Microsoft Defender per le API endpoint](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="64ebb-121">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="64ebb-122">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="64ebb-122">Permission type</span></span> |   <span data-ttu-id="64ebb-123">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="64ebb-123">Permission</span></span>  |   <span data-ttu-id="64ebb-124">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="64ebb-124">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="64ebb-125">Applicazione</span><span class="sxs-lookup"><span data-stu-id="64ebb-125">Application</span></span> |   <span data-ttu-id="64ebb-126">Alerts.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="64ebb-126">Alerts.ReadWrite.All</span></span> |  <span data-ttu-id="64ebb-127">"Lettura e scrittura di tutti gli avvisi"</span><span class="sxs-lookup"><span data-stu-id="64ebb-127">'Read and write all alerts'</span></span>
<span data-ttu-id="64ebb-128">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="64ebb-128">Delegated (work or school account)</span></span> | <span data-ttu-id="64ebb-129">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="64ebb-129">Alert.ReadWrite</span></span> | <span data-ttu-id="64ebb-130">"Avvisi di lettura e scrittura"</span><span class="sxs-lookup"><span data-stu-id="64ebb-130">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="64ebb-131">Quando si ottiene un token utilizzando le credenziali utente:</span><span class="sxs-lookup"><span data-stu-id="64ebb-131">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="64ebb-132">L'utente deve disporre almeno dell'autorizzazione di ruolo seguente: "Analisi degli avvisi" (per ulteriori informazioni, vedere [Creare](user-roles.md) e gestire ruoli)</span><span class="sxs-lookup"><span data-stu-id="64ebb-132">The user needs to have at least the following role permission: 'Alerts investigation' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="64ebb-133">L'utente deve avere accesso al dispositivo associato all'avviso, in base alle impostazioni del gruppo di dispositivi (per ulteriori informazioni, vedere [Creare](machine-groups.md) e gestire gruppi di dispositivi)</span><span class="sxs-lookup"><span data-stu-id="64ebb-133">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="64ebb-134">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="64ebb-134">HTTP request</span></span>
```
PATCH /api/alerts/{id}
```

## <a name="request-headers"></a><span data-ttu-id="64ebb-135">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="64ebb-135">Request headers</span></span>

<span data-ttu-id="64ebb-136">Name</span><span class="sxs-lookup"><span data-stu-id="64ebb-136">Name</span></span> | <span data-ttu-id="64ebb-137">Tipo</span><span class="sxs-lookup"><span data-stu-id="64ebb-137">Type</span></span> | <span data-ttu-id="64ebb-138">Descrizione</span><span class="sxs-lookup"><span data-stu-id="64ebb-138">Description</span></span>
:---|:---|:---
<span data-ttu-id="64ebb-139">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="64ebb-139">Authorization</span></span> | <span data-ttu-id="64ebb-140">Stringa</span><span class="sxs-lookup"><span data-stu-id="64ebb-140">String</span></span> | <span data-ttu-id="64ebb-141">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="64ebb-141">Bearer {token}.</span></span> <span data-ttu-id="64ebb-142">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="64ebb-142">**Required**.</span></span>
<span data-ttu-id="64ebb-143">Content-Type</span><span class="sxs-lookup"><span data-stu-id="64ebb-143">Content-Type</span></span> | <span data-ttu-id="64ebb-144">Stringa</span><span class="sxs-lookup"><span data-stu-id="64ebb-144">String</span></span> | <span data-ttu-id="64ebb-145">application/json.</span><span class="sxs-lookup"><span data-stu-id="64ebb-145">application/json.</span></span> <span data-ttu-id="64ebb-146">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="64ebb-146">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="64ebb-147">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="64ebb-147">Request body</span></span>
<span data-ttu-id="64ebb-148">Nel corpo della richiesta specificare i valori per i campi rilevanti da aggiornare.</span><span class="sxs-lookup"><span data-stu-id="64ebb-148">In the request body, supply the values for the relevant fields that should be updated.</span></span>
<br><span data-ttu-id="64ebb-149">Le proprietà esistenti non incluse nel corpo della richiesta manterranno i valori precedenti o verranno ricalcolate in base alle modifiche apportate ad altri valori di proprietà.</span><span class="sxs-lookup"><span data-stu-id="64ebb-149">Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values.</span></span> 
<br><span data-ttu-id="64ebb-150">Per ottenere prestazioni ottimali, non è consigliabile includere valori esistenti che non sono stati modificate.</span><span class="sxs-lookup"><span data-stu-id="64ebb-150">For best performance you shouldn't include existing values that haven't change.</span></span>

<span data-ttu-id="64ebb-151">Proprietà</span><span class="sxs-lookup"><span data-stu-id="64ebb-151">Property</span></span> | <span data-ttu-id="64ebb-152">Tipo</span><span class="sxs-lookup"><span data-stu-id="64ebb-152">Type</span></span> | <span data-ttu-id="64ebb-153">Descrizione</span><span class="sxs-lookup"><span data-stu-id="64ebb-153">Description</span></span>
:---|:---|:---
<span data-ttu-id="64ebb-154">status</span><span class="sxs-lookup"><span data-stu-id="64ebb-154">status</span></span> | <span data-ttu-id="64ebb-155">Stringa</span><span class="sxs-lookup"><span data-stu-id="64ebb-155">String</span></span> | <span data-ttu-id="64ebb-156">Specifica lo stato corrente dell'avviso.</span><span class="sxs-lookup"><span data-stu-id="64ebb-156">Specifies the current status of the alert.</span></span> <span data-ttu-id="64ebb-157">I valori delle proprietà sono: 'New', 'InProgress' e 'Resolved'.</span><span class="sxs-lookup"><span data-stu-id="64ebb-157">The property values are: 'New', 'InProgress' and 'Resolved'.</span></span>
<span data-ttu-id="64ebb-158">assignedTo</span><span class="sxs-lookup"><span data-stu-id="64ebb-158">assignedTo</span></span> | <span data-ttu-id="64ebb-159">Stringa</span><span class="sxs-lookup"><span data-stu-id="64ebb-159">String</span></span> | <span data-ttu-id="64ebb-160">Proprietario dell'avviso</span><span class="sxs-lookup"><span data-stu-id="64ebb-160">Owner of the alert</span></span>
<span data-ttu-id="64ebb-161">classificazione</span><span class="sxs-lookup"><span data-stu-id="64ebb-161">classification</span></span> | <span data-ttu-id="64ebb-162">Stringa</span><span class="sxs-lookup"><span data-stu-id="64ebb-162">String</span></span> | <span data-ttu-id="64ebb-163">Specifica la specifica dell'avviso.</span><span class="sxs-lookup"><span data-stu-id="64ebb-163">Specifies the specification of the alert.</span></span> <span data-ttu-id="64ebb-164">I valori delle proprietà sono: 'Unknown', 'FalsePositive', 'TruePositive'.</span><span class="sxs-lookup"><span data-stu-id="64ebb-164">The property values are: 'Unknown', 'FalsePositive', 'TruePositive'.</span></span> 
<span data-ttu-id="64ebb-165">determinazione</span><span class="sxs-lookup"><span data-stu-id="64ebb-165">determination</span></span> | <span data-ttu-id="64ebb-166">Stringa</span><span class="sxs-lookup"><span data-stu-id="64ebb-166">String</span></span> | <span data-ttu-id="64ebb-167">Specifica la determinazione dell'avviso.</span><span class="sxs-lookup"><span data-stu-id="64ebb-167">Specifies the determination of the alert.</span></span> <span data-ttu-id="64ebb-168">I valori delle proprietà sono: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'</span><span class="sxs-lookup"><span data-stu-id="64ebb-168">The property values are: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'</span></span>
<span data-ttu-id="64ebb-169">comment</span><span class="sxs-lookup"><span data-stu-id="64ebb-169">comment</span></span> | <span data-ttu-id="64ebb-170">Stringa</span><span class="sxs-lookup"><span data-stu-id="64ebb-170">String</span></span> | <span data-ttu-id="64ebb-171">Commento da aggiungere all'avviso.</span><span class="sxs-lookup"><span data-stu-id="64ebb-171">Comment to be added to the alert.</span></span>

## <a name="response"></a><span data-ttu-id="64ebb-172">Risposta</span><span class="sxs-lookup"><span data-stu-id="64ebb-172">Response</span></span>
<span data-ttu-id="64ebb-173">Se ha esito positivo, questo metodo restituisce [](alerts.md) 200 OK e l'entità di avviso nel corpo della risposta con le proprietà aggiornate.</span><span class="sxs-lookup"><span data-stu-id="64ebb-173">If successful, this method returns 200 OK, and the [alert](alerts.md) entity in the response body with the updated properties.</span></span> <span data-ttu-id="64ebb-174">Se l'avviso con l'ID specificato non è stato trovato - 404 Non trovato.</span><span class="sxs-lookup"><span data-stu-id="64ebb-174">If alert with the specified id was not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="64ebb-175">Esempio</span><span class="sxs-lookup"><span data-stu-id="64ebb-175">Example</span></span>

<span data-ttu-id="64ebb-176">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="64ebb-176">**Request**</span></span>

<span data-ttu-id="64ebb-177">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="64ebb-177">Here is an example of the request.</span></span>

```http
PATCH https://api.securitycenter.microsoft.com/api/alerts/121688558380765161_2136280442
```

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "FalsePositive",
    "determination": "Malware",
    "comment": "Resolve my alert and assign to secop2"
}
```
