---
title: Aggiornare l'API degli incidenti
description: Informazioni su come aggiornare gli eventi non consentiti tramite Microsoft 365 Defender API
keywords: Update, API, Incident
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 3f77980863b0c232166d736a6b557444df98c8ac
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844837"
---
# <a name="update-incidents-api"></a><span data-ttu-id="d6037-104">Aggiornare l'API degli incidenti</span><span class="sxs-lookup"><span data-stu-id="d6037-104">Update incidents API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="d6037-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="d6037-105">**Applies to:**</span></span>
- <span data-ttu-id="d6037-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d6037-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT] 
><span data-ttu-id="d6037-107">Alcune informazioni si riferiscono al prodotto prerilasciato che può essere modificato in modo sostanziale prima che venga rilasciato commercialmente.</span><span class="sxs-lookup"><span data-stu-id="d6037-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="d6037-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="d6037-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


## <a name="api-description"></a><span data-ttu-id="d6037-109">Descrizione API</span><span class="sxs-lookup"><span data-stu-id="d6037-109">API description</span></span>
<span data-ttu-id="d6037-110">Aggiorna le proprietà dell'evento Incident esistente.</span><span class="sxs-lookup"><span data-stu-id="d6037-110">Updates properties of existing incident.</span></span>
<br><span data-ttu-id="d6037-111">Le proprietà aggiornabili sono: ```status``` ,, ```determination``` ```classification``` ```assignedTo``` e ```tags``` .</span><span class="sxs-lookup"><span data-stu-id="d6037-111">Updatable properties are: ```status```, ```determination```, ```classification```, ```assignedTo``` and ```tags```.</span></span>


## <a name="limitations"></a><span data-ttu-id="d6037-112">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="d6037-112">Limitations</span></span>
1. <span data-ttu-id="d6037-113">Le limitazioni delle tariffe per questa API sono 50 chiamate al minuto e 1500 chiamate all'ora.</span><span class="sxs-lookup"><span data-stu-id="d6037-113">Rate limitations for this API are 50 calls per minute and 1500 calls per hour.</span></span>
2. <span data-ttu-id="d6037-114">È possibile impostare ```determination``` solo se la classificazione è impostata su TruePositive.</span><span class="sxs-lookup"><span data-stu-id="d6037-114">You can set the ```determination``` only if the classification is set to TruePositive.</span></span>


## <a name="permissions"></a><span data-ttu-id="d6037-115">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="d6037-115">Permissions</span></span>
<span data-ttu-id="d6037-116">Per chiamare l'API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="d6037-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="d6037-117">Per ulteriori informazioni, tra cui la scelta delle autorizzazioni, vedere [Access the Microsoft 365 Defender Apis](api-access.md).</span><span class="sxs-lookup"><span data-stu-id="d6037-117">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender APIs](api-access.md).</span></span>

<span data-ttu-id="d6037-118">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="d6037-118">Permission type</span></span> |   <span data-ttu-id="d6037-119">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="d6037-119">Permission</span></span>  |   <span data-ttu-id="d6037-120">Nome visualizzato per le autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="d6037-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="d6037-121">Applicazione</span><span class="sxs-lookup"><span data-stu-id="d6037-121">Application</span></span> |   <span data-ttu-id="d6037-122">Incident. ReadWrite. All</span><span class="sxs-lookup"><span data-stu-id="d6037-122">Incident.ReadWrite.All</span></span> |    <span data-ttu-id="d6037-123">' Leggi e Scrivi tutti gli incidenti '</span><span class="sxs-lookup"><span data-stu-id="d6037-123">'Read and write all incidents'</span></span>
<span data-ttu-id="d6037-124">Delegati (account aziendale o dell'Istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="d6037-124">Delegated (work or school account)</span></span> | <span data-ttu-id="d6037-125">Incident. ReadWrite</span><span class="sxs-lookup"><span data-stu-id="d6037-125">Incident.ReadWrite</span></span> | <span data-ttu-id="d6037-126">' Operazioni di lettura e scrittura degli incidenti '</span><span class="sxs-lookup"><span data-stu-id="d6037-126">'Read and write incidents'</span></span>

>[!NOTE]
> <span data-ttu-id="d6037-127">Quando si ottiene un token utilizzando le credenziali utente:</span><span class="sxs-lookup"><span data-stu-id="d6037-127">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="d6037-128">L'utente deve disporre dell'autorizzazione necessaria per aggiornare l'evento Incident nel portale.</span><span class="sxs-lookup"><span data-stu-id="d6037-128">The user needs to have permission to update the incident in the portal.</span></span>


## <a name="http-request"></a><span data-ttu-id="d6037-129">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="d6037-129">HTTP request</span></span>

```
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a><span data-ttu-id="d6037-130">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="d6037-130">Request headers</span></span>

<span data-ttu-id="d6037-131">Name</span><span class="sxs-lookup"><span data-stu-id="d6037-131">Name</span></span> | <span data-ttu-id="d6037-132">Tipo</span><span class="sxs-lookup"><span data-stu-id="d6037-132">Type</span></span> | <span data-ttu-id="d6037-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d6037-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="d6037-134">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="d6037-134">Authorization</span></span> | <span data-ttu-id="d6037-135">Stringa</span><span class="sxs-lookup"><span data-stu-id="d6037-135">String</span></span> | <span data-ttu-id="d6037-136">Portatore {token}.</span><span class="sxs-lookup"><span data-stu-id="d6037-136">Bearer {token}.</span></span> <span data-ttu-id="d6037-137">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="d6037-137">**Required**.</span></span>
<span data-ttu-id="d6037-138">Content-Type</span><span class="sxs-lookup"><span data-stu-id="d6037-138">Content-Type</span></span> | <span data-ttu-id="d6037-139">Stringa</span><span class="sxs-lookup"><span data-stu-id="d6037-139">String</span></span> | <span data-ttu-id="d6037-140">applicazione/JSON.</span><span class="sxs-lookup"><span data-stu-id="d6037-140">application/json.</span></span> <span data-ttu-id="d6037-141">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="d6037-141">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="d6037-142">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="d6037-142">Request body</span></span>
<span data-ttu-id="d6037-143">Nel corpo della richiesta fornire i valori per i campi rilevanti che devono essere aggiornati.</span><span class="sxs-lookup"><span data-stu-id="d6037-143">In the request body, supply the values for the relevant fields that should be updated.</span></span>
<br><span data-ttu-id="d6037-144">Le proprietà esistenti che non sono incluse nel corpo della richiesta manterranno i valori precedenti o verranno ricalcolate in base alle modifiche apportate ad altri valori di proprietà.</span><span class="sxs-lookup"><span data-stu-id="d6037-144">Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values.</span></span> 
<br><span data-ttu-id="d6037-145">Per prestazioni ottimali, non è necessario includere i valori esistenti che non sono cambiati.</span><span class="sxs-lookup"><span data-stu-id="d6037-145">For best performance you shouldn't include existing values that haven't change.</span></span>

<span data-ttu-id="d6037-146">Proprietà</span><span class="sxs-lookup"><span data-stu-id="d6037-146">Property</span></span> | <span data-ttu-id="d6037-147">Tipo</span><span class="sxs-lookup"><span data-stu-id="d6037-147">Type</span></span> | <span data-ttu-id="d6037-148">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d6037-148">Description</span></span>
:---|:---|:---
<span data-ttu-id="d6037-149">stato</span><span class="sxs-lookup"><span data-stu-id="d6037-149">status</span></span> | <span data-ttu-id="d6037-150">Enum</span><span class="sxs-lookup"><span data-stu-id="d6037-150">Enum</span></span> | <span data-ttu-id="d6037-151">Specifica lo stato corrente dell'avviso.</span><span class="sxs-lookup"><span data-stu-id="d6037-151">Specifies the current status of the alert.</span></span> <span data-ttu-id="d6037-152">I valori possibili sono ```Active``` : ```Resolved``` e ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="d6037-152">Possible values are: ```Active```, ```Resolved``` and ```Redirected```.</span></span>
<span data-ttu-id="d6037-153">AssegnatoA</span><span class="sxs-lookup"><span data-stu-id="d6037-153">assignedTo</span></span> | <span data-ttu-id="d6037-154">stringa</span><span class="sxs-lookup"><span data-stu-id="d6037-154">string</span></span> | <span data-ttu-id="d6037-155">Proprietario dell'evento Incident.</span><span class="sxs-lookup"><span data-stu-id="d6037-155">Owner of the incident.</span></span>
<span data-ttu-id="d6037-156">classificazione</span><span class="sxs-lookup"><span data-stu-id="d6037-156">classification</span></span> | <span data-ttu-id="d6037-157">Enum</span><span class="sxs-lookup"><span data-stu-id="d6037-157">Enum</span></span> | <span data-ttu-id="d6037-158">Specifica dell'avviso.</span><span class="sxs-lookup"><span data-stu-id="d6037-158">Specification of the alert.</span></span> <span data-ttu-id="d6037-159">I valori possibili sono: ```Unknown``` , ```FalsePositive``` , ```TruePositive``` .</span><span class="sxs-lookup"><span data-stu-id="d6037-159">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="d6037-160">determinazione</span><span class="sxs-lookup"><span data-stu-id="d6037-160">determination</span></span> | <span data-ttu-id="d6037-161">Enum</span><span class="sxs-lookup"><span data-stu-id="d6037-161">Enum</span></span> | <span data-ttu-id="d6037-162">Specifica la determinazione dell'avviso.</span><span class="sxs-lookup"><span data-stu-id="d6037-162">Specifies the determination of the alert.</span></span> <span data-ttu-id="d6037-163">I valori possibili sono:,,,,,, ```NotAvailable``` ```Apt``` ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` ```UnwantedSoftware``` ```Other``` .</span><span class="sxs-lookup"><span data-stu-id="d6037-163">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="d6037-164">Tag</span><span class="sxs-lookup"><span data-stu-id="d6037-164">tags</span></span> | <span data-ttu-id="d6037-165">Elenco di stringhe</span><span class="sxs-lookup"><span data-stu-id="d6037-165">string List</span></span> | <span data-ttu-id="d6037-166">Elenco dei tag Incident.</span><span class="sxs-lookup"><span data-stu-id="d6037-166">List of Incident tags.</span></span>



## <a name="response"></a><span data-ttu-id="d6037-167">Risposta</span><span class="sxs-lookup"><span data-stu-id="d6037-167">Response</span></span>
<span data-ttu-id="d6037-168">Se l'operazione ha esito positivo, questo metodo restituisce 200 OK e l'entità Incident nel corpo della risposta con le proprietà aggiornate.</span><span class="sxs-lookup"><span data-stu-id="d6037-168">If successful, this method returns 200 OK, and the incident entity in the response body with the updated properties.</span></span> <span data-ttu-id="d6037-169">Se non è stato trovato un problema con l'ID specificato-404 non è stato trovato.</span><span class="sxs-lookup"><span data-stu-id="d6037-169">If incident with the specified id was not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="d6037-170">Esempio</span><span class="sxs-lookup"><span data-stu-id="d6037-170">Example</span></span>

<span data-ttu-id="d6037-171">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="d6037-171">**Request**</span></span>

<span data-ttu-id="d6037-172">Di seguito è riportato un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="d6037-172">Here is an example of the request.</span></span>

```
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "TruePositive",
    "determination": "Malware",
    "tags": ["Yossi's playground", "Don't mess with the Zohan"]
}
```


## <a name="related-topic"></a><span data-ttu-id="d6037-173">Argomento correlato</span><span class="sxs-lookup"><span data-stu-id="d6037-173">Related topic</span></span>
- [<span data-ttu-id="d6037-174">Incidenti delle API</span><span class="sxs-lookup"><span data-stu-id="d6037-174">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="d6037-175">Elencare incidenti</span><span class="sxs-lookup"><span data-stu-id="d6037-175">List incidents</span></span>](api-list-incidents.md)
