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
ms.openlocfilehash: 6fc1ff730994f03aa500ad9a4559b66970e32d87
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719405"
---
# <a name="update-incidents-api"></a><span data-ttu-id="5c0ce-104">Aggiornare l'API degli incidenti</span><span class="sxs-lookup"><span data-stu-id="5c0ce-104">Update incidents API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="5c0ce-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="5c0ce-105">**Applies to:**</span></span>

- <span data-ttu-id="5c0ce-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5c0ce-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5c0ce-107">Alcune informazioni si riferiscono al prodotto prerilasciato che può essere modificato in modo sostanziale prima che venga rilasciato commercialmente.</span><span class="sxs-lookup"><span data-stu-id="5c0ce-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="5c0ce-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="5c0ce-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="api-description"></a><span data-ttu-id="5c0ce-109">Descrizione API</span><span class="sxs-lookup"><span data-stu-id="5c0ce-109">API description</span></span>

<span data-ttu-id="5c0ce-110">Aggiorna le proprietà dell'evento Incident esistente.</span><span class="sxs-lookup"><span data-stu-id="5c0ce-110">Updates properties of existing incident.</span></span> <span data-ttu-id="5c0ce-111">Le proprietà aggiornabili sono:,,, ```status``` ```determination``` ```classification``` ```assignedTo``` e ```tags``` .</span><span class="sxs-lookup"><span data-stu-id="5c0ce-111">Updatable properties are: ```status```, ```determination```, ```classification```, ```assignedTo```, and ```tags```.</span></span>

### <a name="quotas-resource-allocation-and-other-constraints"></a><span data-ttu-id="5c0ce-112">Quote, allocazione delle risorse e altri vincoli</span><span class="sxs-lookup"><span data-stu-id="5c0ce-112">Quotas, resource allocation, and other constraints</span></span>

1. <span data-ttu-id="5c0ce-113">È possibile effettuare fino a 50 chiamate al minuto o 1500 chiamate all'ora prima di colpire la soglia di limitazione.</span><span class="sxs-lookup"><span data-stu-id="5c0ce-113">You can make up to 50 calls per minute or 1500 calls per hour before you hit the throttling threshold.</span></span>
2. <span data-ttu-id="5c0ce-114">È possibile impostare la `determination` proprietà solo se `classification` è impostata su TruePositive.</span><span class="sxs-lookup"><span data-stu-id="5c0ce-114">You can set the `determination` property only if `classification` is set to TruePositive.</span></span>

<span data-ttu-id="5c0ce-115">Se la richiesta viene sottoposta a limitazione, restituirà un `429` codice di risposta.</span><span class="sxs-lookup"><span data-stu-id="5c0ce-115">If your request is throttled, it will return a `429` response code.</span></span> <span data-ttu-id="5c0ce-116">Il corpo di risposta indicherà l'ora in cui è possibile iniziare a effettuare nuove chiamate.</span><span class="sxs-lookup"><span data-stu-id="5c0ce-116">The response body will indicate the time when you can begin making new calls.</span></span>

## <a name="permissions"></a><span data-ttu-id="5c0ce-117">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="5c0ce-117">Permissions</span></span>

<span data-ttu-id="5c0ce-118">Per chiamare l'API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="5c0ce-118">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="5c0ce-119">Per ulteriori informazioni, tra cui la scelta delle autorizzazioni, vedere [Access the Microsoft 365 Defender Apis](api-access.md).</span><span class="sxs-lookup"><span data-stu-id="5c0ce-119">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender APIs](api-access.md).</span></span>

<span data-ttu-id="5c0ce-120">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="5c0ce-120">Permission type</span></span> | <span data-ttu-id="5c0ce-121">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="5c0ce-121">Permission</span></span> | <span data-ttu-id="5c0ce-122">Nome visualizzato per le autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="5c0ce-122">Permission display name</span></span>
-|-|-
<span data-ttu-id="5c0ce-123">Applicazione</span><span class="sxs-lookup"><span data-stu-id="5c0ce-123">Application</span></span> | <span data-ttu-id="5c0ce-124">Incident. ReadWrite. All</span><span class="sxs-lookup"><span data-stu-id="5c0ce-124">Incident.ReadWrite.All</span></span> | <span data-ttu-id="5c0ce-125">Leggere e scrivere tutti gli eventi non consentiti</span><span class="sxs-lookup"><span data-stu-id="5c0ce-125">Read and write all incidents</span></span>
<span data-ttu-id="5c0ce-126">Delegati (account aziendale o dell'Istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="5c0ce-126">Delegated (work or school account)</span></span> | <span data-ttu-id="5c0ce-127">Incident. ReadWrite</span><span class="sxs-lookup"><span data-stu-id="5c0ce-127">Incident.ReadWrite</span></span> | <span data-ttu-id="5c0ce-128">Operazioni di lettura e scrittura degli incidenti</span><span class="sxs-lookup"><span data-stu-id="5c0ce-128">Read and write incidents</span></span>

> [!NOTE]
> <span data-ttu-id="5c0ce-129">Quando si ottiene un token utilizzando le credenziali utente, l'utente deve disporre dell'autorizzazione necessaria per aggiornare l'evento Incident nel portale.</span><span class="sxs-lookup"><span data-stu-id="5c0ce-129">When obtaining a token using user credentials, the user needs to have permission to update the incident in the portal.</span></span>

## <a name="http-request"></a><span data-ttu-id="5c0ce-130">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="5c0ce-130">HTTP request</span></span>

```HTTP
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a><span data-ttu-id="5c0ce-131">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="5c0ce-131">Request headers</span></span>

<span data-ttu-id="5c0ce-132">Name</span><span class="sxs-lookup"><span data-stu-id="5c0ce-132">Name</span></span> | <span data-ttu-id="5c0ce-133">Tipo</span><span class="sxs-lookup"><span data-stu-id="5c0ce-133">Type</span></span> | <span data-ttu-id="5c0ce-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5c0ce-134">Description</span></span>
-|-|-
<span data-ttu-id="5c0ce-135">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="5c0ce-135">Authorization</span></span> | <span data-ttu-id="5c0ce-136">Stringa</span><span class="sxs-lookup"><span data-stu-id="5c0ce-136">String</span></span> | <span data-ttu-id="5c0ce-137">Portatore {token}.</span><span class="sxs-lookup"><span data-stu-id="5c0ce-137">Bearer {token}.</span></span> <span data-ttu-id="5c0ce-138">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="5c0ce-138">**Required**.</span></span>
<span data-ttu-id="5c0ce-139">Content-Type</span><span class="sxs-lookup"><span data-stu-id="5c0ce-139">Content-Type</span></span> | <span data-ttu-id="5c0ce-140">Stringa</span><span class="sxs-lookup"><span data-stu-id="5c0ce-140">String</span></span> | <span data-ttu-id="5c0ce-141">applicazione/JSON.</span><span class="sxs-lookup"><span data-stu-id="5c0ce-141">application/json.</span></span> <span data-ttu-id="5c0ce-142">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="5c0ce-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="5c0ce-143">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="5c0ce-143">Request body</span></span>

<span data-ttu-id="5c0ce-144">Nel corpo della richiesta fornire i valori per i campi che devono essere aggiornati.</span><span class="sxs-lookup"><span data-stu-id="5c0ce-144">In the request body, supply the values for the fields that should be updated.</span></span> <span data-ttu-id="5c0ce-145">Le proprietà esistenti che non sono incluse nel corpo della richiesta manterranno i propri valori, a meno che non debbano essere ricalcolate a causa delle modifiche apportate ai valori correlati.</span><span class="sxs-lookup"><span data-stu-id="5c0ce-145">Existing properties that aren't included in the request body will maintain their values, unless they have to be recalculated due to changes to related values.</span></span> <span data-ttu-id="5c0ce-146">Per prestazioni ottimali, è consigliabile omettere i valori esistenti che non sono stati modificati.</span><span class="sxs-lookup"><span data-stu-id="5c0ce-146">For best performance, you should omit existing values that haven't changed.</span></span>

<span data-ttu-id="5c0ce-147">Proprietà</span><span class="sxs-lookup"><span data-stu-id="5c0ce-147">Property</span></span> | <span data-ttu-id="5c0ce-148">Tipo</span><span class="sxs-lookup"><span data-stu-id="5c0ce-148">Type</span></span> | <span data-ttu-id="5c0ce-149">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5c0ce-149">Description</span></span>
-|-|-
<span data-ttu-id="5c0ce-150">stato</span><span class="sxs-lookup"><span data-stu-id="5c0ce-150">status</span></span> | <span data-ttu-id="5c0ce-151">Enum</span><span class="sxs-lookup"><span data-stu-id="5c0ce-151">Enum</span></span> | <span data-ttu-id="5c0ce-152">Specifica lo stato corrente dell'avviso.</span><span class="sxs-lookup"><span data-stu-id="5c0ce-152">Specifies the current status of the alert.</span></span> <span data-ttu-id="5c0ce-153">I valori possibili sono: ```Active``` , ```Resolved``` e ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="5c0ce-153">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="5c0ce-154">AssegnatoA</span><span class="sxs-lookup"><span data-stu-id="5c0ce-154">assignedTo</span></span> | <span data-ttu-id="5c0ce-155">stringa</span><span class="sxs-lookup"><span data-stu-id="5c0ce-155">string</span></span> | <span data-ttu-id="5c0ce-156">Proprietario dell'evento Incident.</span><span class="sxs-lookup"><span data-stu-id="5c0ce-156">Owner of the incident.</span></span>
<span data-ttu-id="5c0ce-157">classificazione</span><span class="sxs-lookup"><span data-stu-id="5c0ce-157">classification</span></span> | <span data-ttu-id="5c0ce-158">Enum</span><span class="sxs-lookup"><span data-stu-id="5c0ce-158">Enum</span></span> | <span data-ttu-id="5c0ce-159">Specifica dell'avviso.</span><span class="sxs-lookup"><span data-stu-id="5c0ce-159">Specification of the alert.</span></span> <span data-ttu-id="5c0ce-160">I valori possibili sono: ```Unknown``` , ```FalsePositive``` , ```TruePositive``` .</span><span class="sxs-lookup"><span data-stu-id="5c0ce-160">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="5c0ce-161">determinazione</span><span class="sxs-lookup"><span data-stu-id="5c0ce-161">determination</span></span> | <span data-ttu-id="5c0ce-162">Enum</span><span class="sxs-lookup"><span data-stu-id="5c0ce-162">Enum</span></span> | <span data-ttu-id="5c0ce-163">Specifica la determinazione dell'avviso.</span><span class="sxs-lookup"><span data-stu-id="5c0ce-163">Specifies the determination of the alert.</span></span> <span data-ttu-id="5c0ce-164">I valori possibili sono:,,,,,, ```NotAvailable``` ```Apt``` ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` ```UnwantedSoftware``` ```Other``` .</span><span class="sxs-lookup"><span data-stu-id="5c0ce-164">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="5c0ce-165">Tag</span><span class="sxs-lookup"><span data-stu-id="5c0ce-165">tags</span></span> | <span data-ttu-id="5c0ce-166">Elenco di stringhe</span><span class="sxs-lookup"><span data-stu-id="5c0ce-166">string List</span></span> | <span data-ttu-id="5c0ce-167">Elenco dei tag Incident.</span><span class="sxs-lookup"><span data-stu-id="5c0ce-167">List of Incident tags.</span></span>

## <a name="response"></a><span data-ttu-id="5c0ce-168">Risposta</span><span class="sxs-lookup"><span data-stu-id="5c0ce-168">Response</span></span>

<span data-ttu-id="5c0ce-169">Se l'operazione ha esito positivo, il metodo restituisce `200 OK` .</span><span class="sxs-lookup"><span data-stu-id="5c0ce-169">If successful, this method returns `200 OK`.</span></span> <span data-ttu-id="5c0ce-170">Il corpo di risposta conterrà l'entità Incident con le proprietà aggiornate.</span><span class="sxs-lookup"><span data-stu-id="5c0ce-170">The response body will contain the incident entity with updated properties.</span></span> <span data-ttu-id="5c0ce-171">Se non è stato trovato un problema con l'ID specificato, il metodo restituisce `404 Not Found` .</span><span class="sxs-lookup"><span data-stu-id="5c0ce-171">If an incident with the specified ID wasn't found, the method returns `404 Not Found`.</span></span>

## <a name="example"></a><span data-ttu-id="5c0ce-172">Esempio</span><span class="sxs-lookup"><span data-stu-id="5c0ce-172">Example</span></span>

<span data-ttu-id="5c0ce-173">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="5c0ce-173">**Request**</span></span>

<span data-ttu-id="5c0ce-174">Di seguito è riportato un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="5c0ce-174">Here's an example of the request.</span></span>

```HTTP
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

<span data-ttu-id="5c0ce-175">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="5c0ce-175">**Response**</span></span>

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "TruePositive",
    "determination": "Malware",
    "tags": ["Yossi's playground", "Don't mess with the Zohan"]
}
```

## <a name="related-articles"></a><span data-ttu-id="5c0ce-176">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="5c0ce-176">Related articles</span></span>

- [<span data-ttu-id="5c0ce-177">Accedere alle API di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5c0ce-177">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="5c0ce-178">Informazioni sui limiti delle API e sulle licenze</span><span class="sxs-lookup"><span data-stu-id="5c0ce-178">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="5c0ce-179">Informazioni sui codici di errore</span><span class="sxs-lookup"><span data-stu-id="5c0ce-179">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="5c0ce-180">Incidenti delle API</span><span class="sxs-lookup"><span data-stu-id="5c0ce-180">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="5c0ce-181">Elencare incidenti</span><span class="sxs-lookup"><span data-stu-id="5c0ce-181">List incidents</span></span>](api-list-incidents.md)
- [<span data-ttu-id="5c0ce-182">Panoramica degli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="5c0ce-182">Incidents overview</span></span>](incidents-overview.md)
