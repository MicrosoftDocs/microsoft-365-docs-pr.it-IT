---
title: API dell'entità di avviso di aggiornamento
description: Scopri come aggiornare un avviso di Microsoft Defender per Endpoint usando questa API. È possibile aggiornare lo stato, la determinazione, la classificazione e le proprietà assignedTo.
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
ms.openlocfilehash: 043d423e1016d77cad4a175aa41718329f464252
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "52768927"
---
# <a name="update-alert"></a><span data-ttu-id="23cc2-105">Avviso di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="23cc2-105">Update alert</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="23cc2-106">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="23cc2-106">**Applies to:**</span></span>
- [<span data-ttu-id="23cc2-107">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="23cc2-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="23cc2-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="23cc2-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="23cc2-109">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="23cc2-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="23cc2-110">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="23cc2-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="23cc2-111">Descrizione API</span><span class="sxs-lookup"><span data-stu-id="23cc2-111">API description</span></span>
<span data-ttu-id="23cc2-112">Aggiorna le proprietà dell'oggetto [Alert esistente.](alerts.md)</span><span class="sxs-lookup"><span data-stu-id="23cc2-112">Updates properties of existing [Alert](alerts.md).</span></span>
<br><span data-ttu-id="23cc2-113">**L'invio di** commenti è disponibile con o senza aggiornare le proprietà.</span><span class="sxs-lookup"><span data-stu-id="23cc2-113">Submission of **comment** is available with or without updating properties.</span></span>
<br><span data-ttu-id="23cc2-114">Le proprietà aggiornabili sono: ```status``` ```determination``` , e ```classification``` ```assignedTo``` .</span><span class="sxs-lookup"><span data-stu-id="23cc2-114">Updatable properties are: ```status```, ```determination```, ```classification``` and ```assignedTo```.</span></span>


## <a name="limitations"></a><span data-ttu-id="23cc2-115">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="23cc2-115">Limitations</span></span>
1. <span data-ttu-id="23cc2-116">Puoi aggiornare gli avvisi disponibili nell'API.</span><span class="sxs-lookup"><span data-stu-id="23cc2-116">You can update alerts that available in the API.</span></span> <span data-ttu-id="23cc2-117">Per [ulteriori informazioni, vedere Avvisi](get-alerts.md) elenco.</span><span class="sxs-lookup"><span data-stu-id="23cc2-117">See [List Alerts](get-alerts.md) for more information.</span></span>
2. <span data-ttu-id="23cc2-118">I limiti di frequenza per questa API sono 100 chiamate al minuto e 1500 chiamate all'ora.</span><span class="sxs-lookup"><span data-stu-id="23cc2-118">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="23cc2-119">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="23cc2-119">Permissions</span></span>
<span data-ttu-id="23cc2-120">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="23cc2-120">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="23cc2-121">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi [Usare Microsoft Defender per le API endpoint](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="23cc2-121">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="23cc2-122">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="23cc2-122">Permission type</span></span> |   <span data-ttu-id="23cc2-123">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="23cc2-123">Permission</span></span>  |   <span data-ttu-id="23cc2-124">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="23cc2-124">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="23cc2-125">Applicazione</span><span class="sxs-lookup"><span data-stu-id="23cc2-125">Application</span></span> |   <span data-ttu-id="23cc2-126">Alerts.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="23cc2-126">Alerts.ReadWrite.All</span></span> |  <span data-ttu-id="23cc2-127">"Lettura e scrittura di tutti gli avvisi"</span><span class="sxs-lookup"><span data-stu-id="23cc2-127">'Read and write all alerts'</span></span>
<span data-ttu-id="23cc2-128">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="23cc2-128">Delegated (work or school account)</span></span> | <span data-ttu-id="23cc2-129">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="23cc2-129">Alert.ReadWrite</span></span> | <span data-ttu-id="23cc2-130">"Avvisi di lettura e scrittura"</span><span class="sxs-lookup"><span data-stu-id="23cc2-130">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="23cc2-131">Quando si ottiene un token utilizzando le credenziali utente:</span><span class="sxs-lookup"><span data-stu-id="23cc2-131">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="23cc2-132">L'utente deve disporre almeno dell'autorizzazione di ruolo seguente: "Analisi degli avvisi" (per ulteriori informazioni, vedere [Creare](user-roles.md) e gestire ruoli)</span><span class="sxs-lookup"><span data-stu-id="23cc2-132">The user needs to have at least the following role permission: 'Alerts investigation' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="23cc2-133">L'utente deve avere accesso al dispositivo associato all'avviso, in base alle impostazioni del gruppo di dispositivi (per ulteriori informazioni, vedere [Creare](machine-groups.md) e gestire gruppi di dispositivi)</span><span class="sxs-lookup"><span data-stu-id="23cc2-133">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="23cc2-134">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="23cc2-134">HTTP request</span></span>
```
PATCH /api/alerts/{id}
```

## <a name="request-headers"></a><span data-ttu-id="23cc2-135">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="23cc2-135">Request headers</span></span>

<span data-ttu-id="23cc2-136">Name</span><span class="sxs-lookup"><span data-stu-id="23cc2-136">Name</span></span> | <span data-ttu-id="23cc2-137">Tipo</span><span class="sxs-lookup"><span data-stu-id="23cc2-137">Type</span></span> | <span data-ttu-id="23cc2-138">Descrizione</span><span class="sxs-lookup"><span data-stu-id="23cc2-138">Description</span></span>
:---|:---|:---
<span data-ttu-id="23cc2-139">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="23cc2-139">Authorization</span></span> | <span data-ttu-id="23cc2-140">Stringa</span><span class="sxs-lookup"><span data-stu-id="23cc2-140">String</span></span> | <span data-ttu-id="23cc2-141">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="23cc2-141">Bearer {token}.</span></span> <span data-ttu-id="23cc2-142">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="23cc2-142">**Required**.</span></span>
<span data-ttu-id="23cc2-143">Content-Type</span><span class="sxs-lookup"><span data-stu-id="23cc2-143">Content-Type</span></span> | <span data-ttu-id="23cc2-144">Stringa</span><span class="sxs-lookup"><span data-stu-id="23cc2-144">String</span></span> | <span data-ttu-id="23cc2-145">application/json.</span><span class="sxs-lookup"><span data-stu-id="23cc2-145">application/json.</span></span> <span data-ttu-id="23cc2-146">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="23cc2-146">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="23cc2-147">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="23cc2-147">Request body</span></span>
<span data-ttu-id="23cc2-148">Nel corpo della richiesta specificare i valori per i campi rilevanti da aggiornare.</span><span class="sxs-lookup"><span data-stu-id="23cc2-148">In the request body, supply the values for the relevant fields that should be updated.</span></span>
<br><span data-ttu-id="23cc2-149">Le proprietà esistenti non incluse nel corpo della richiesta manterranno i valori precedenti o verranno ricalcolate in base alle modifiche apportate ad altri valori di proprietà.</span><span class="sxs-lookup"><span data-stu-id="23cc2-149">Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values.</span></span> 
<br><span data-ttu-id="23cc2-150">Per ottenere prestazioni ottimali, non è consigliabile includere valori esistenti che non sono stati modificate.</span><span class="sxs-lookup"><span data-stu-id="23cc2-150">For best performance you shouldn't include existing values that haven't change.</span></span>

<span data-ttu-id="23cc2-151">Proprietà</span><span class="sxs-lookup"><span data-stu-id="23cc2-151">Property</span></span> | <span data-ttu-id="23cc2-152">Tipo</span><span class="sxs-lookup"><span data-stu-id="23cc2-152">Type</span></span> | <span data-ttu-id="23cc2-153">Descrizione</span><span class="sxs-lookup"><span data-stu-id="23cc2-153">Description</span></span>
:---|:---|:---
<span data-ttu-id="23cc2-154">status</span><span class="sxs-lookup"><span data-stu-id="23cc2-154">status</span></span> | <span data-ttu-id="23cc2-155">Stringa</span><span class="sxs-lookup"><span data-stu-id="23cc2-155">String</span></span> | <span data-ttu-id="23cc2-156">Specifica lo stato corrente dell'avviso.</span><span class="sxs-lookup"><span data-stu-id="23cc2-156">Specifies the current status of the alert.</span></span> <span data-ttu-id="23cc2-157">I valori delle proprietà sono: 'New', 'InProgress' e 'Resolved'.</span><span class="sxs-lookup"><span data-stu-id="23cc2-157">The property values are: 'New', 'InProgress' and 'Resolved'.</span></span>
<span data-ttu-id="23cc2-158">assignedTo</span><span class="sxs-lookup"><span data-stu-id="23cc2-158">assignedTo</span></span> | <span data-ttu-id="23cc2-159">Stringa</span><span class="sxs-lookup"><span data-stu-id="23cc2-159">String</span></span> | <span data-ttu-id="23cc2-160">Proprietario dell'avviso</span><span class="sxs-lookup"><span data-stu-id="23cc2-160">Owner of the alert</span></span>
<span data-ttu-id="23cc2-161">classificazione</span><span class="sxs-lookup"><span data-stu-id="23cc2-161">classification</span></span> | <span data-ttu-id="23cc2-162">Stringa</span><span class="sxs-lookup"><span data-stu-id="23cc2-162">String</span></span> | <span data-ttu-id="23cc2-163">Specifica la specifica dell'avviso.</span><span class="sxs-lookup"><span data-stu-id="23cc2-163">Specifies the specification of the alert.</span></span> <span data-ttu-id="23cc2-164">I valori delle proprietà sono: 'Unknown', 'FalsePositive', 'TruePositive'.</span><span class="sxs-lookup"><span data-stu-id="23cc2-164">The property values are: 'Unknown', 'FalsePositive', 'TruePositive'.</span></span> 
<span data-ttu-id="23cc2-165">determinazione</span><span class="sxs-lookup"><span data-stu-id="23cc2-165">determination</span></span> | <span data-ttu-id="23cc2-166">Stringa</span><span class="sxs-lookup"><span data-stu-id="23cc2-166">String</span></span> | <span data-ttu-id="23cc2-167">Specifica la determinazione dell'avviso.</span><span class="sxs-lookup"><span data-stu-id="23cc2-167">Specifies the determination of the alert.</span></span> <span data-ttu-id="23cc2-168">I valori delle proprietà sono: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'</span><span class="sxs-lookup"><span data-stu-id="23cc2-168">The property values are: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'</span></span>
<span data-ttu-id="23cc2-169">comment</span><span class="sxs-lookup"><span data-stu-id="23cc2-169">comment</span></span> | <span data-ttu-id="23cc2-170">Stringa</span><span class="sxs-lookup"><span data-stu-id="23cc2-170">String</span></span> | <span data-ttu-id="23cc2-171">Commento da aggiungere all'avviso.</span><span class="sxs-lookup"><span data-stu-id="23cc2-171">Comment to be added to the alert.</span></span>

## <a name="response"></a><span data-ttu-id="23cc2-172">Risposta</span><span class="sxs-lookup"><span data-stu-id="23cc2-172">Response</span></span>
<span data-ttu-id="23cc2-173">Se ha esito positivo, questo metodo restituisce [](alerts.md) 200 OK e l'entità di avviso nel corpo della risposta con le proprietà aggiornate.</span><span class="sxs-lookup"><span data-stu-id="23cc2-173">If successful, this method returns 200 OK, and the [alert](alerts.md) entity in the response body with the updated properties.</span></span> <span data-ttu-id="23cc2-174">Se l'avviso con l'ID specificato non è stato trovato - 404 Non trovato.</span><span class="sxs-lookup"><span data-stu-id="23cc2-174">If alert with the specified id was not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="23cc2-175">Esempio</span><span class="sxs-lookup"><span data-stu-id="23cc2-175">Example</span></span>

<span data-ttu-id="23cc2-176">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="23cc2-176">**Request**</span></span>

<span data-ttu-id="23cc2-177">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="23cc2-177">Here is an example of the request.</span></span>

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
