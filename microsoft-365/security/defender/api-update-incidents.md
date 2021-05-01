---
title: API per gli eventi imprevisti di aggiornamento
description: Scopri come aggiornare gli eventi imprevisti con Microsoft 365 Defender API
keywords: aggiornamento, api, evento imprevisto
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: d6872a7a4b1b2d2c131066076af02a65b4ef6d8a
ms.sourcegitcommit: 794f9767aaebe13ab1aead830b214ea674289d19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2021
ms.locfileid: "52107605"
---
# <a name="update-incidents-api"></a><span data-ttu-id="67cb8-104">API per gli eventi imprevisti di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="67cb8-104">Update incidents API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="67cb8-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="67cb8-105">**Applies to:**</span></span>

- <span data-ttu-id="67cb8-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="67cb8-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="67cb8-107">Alcune informazioni fanno riferimento alle caratteristiche del prodotto prima del rilascio, e possono essere modificate sostanzialmente prima della distribuzione al pubblico.</span><span class="sxs-lookup"><span data-stu-id="67cb8-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="67cb8-108">Microsoft non fornisce alcuna garanzia, esplicita o implicita, in relazione alle informazioni contenute in questo documento.</span><span class="sxs-lookup"><span data-stu-id="67cb8-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="api-description"></a><span data-ttu-id="67cb8-109">Descrizione API</span><span class="sxs-lookup"><span data-stu-id="67cb8-109">API description</span></span>

<span data-ttu-id="67cb8-110">Aggiorna le proprietà dell'evento imprevisto esistente.</span><span class="sxs-lookup"><span data-stu-id="67cb8-110">Updates properties of existing incident.</span></span> <span data-ttu-id="67cb8-111">Le proprietà aggiornabili sono: ```status``` , , , e ```determination``` ```classification``` ```assignedTo``` ```tags``` .</span><span class="sxs-lookup"><span data-stu-id="67cb8-111">Updatable properties are: ```status```, ```determination```, ```classification```, ```assignedTo```, and ```tags```.</span></span>

### <a name="quotas-resource-allocation-and-other-constraints"></a><span data-ttu-id="67cb8-112">Quote, allocazione delle risorse e altri vincoli</span><span class="sxs-lookup"><span data-stu-id="67cb8-112">Quotas, resource allocation, and other constraints</span></span>

1. <span data-ttu-id="67cb8-113">È possibile effettuare fino a 50 chiamate al minuto o 1500 chiamate all'ora prima di ottenere la soglia di limitazione.</span><span class="sxs-lookup"><span data-stu-id="67cb8-113">You can make up to 50 calls per minute or 1500 calls per hour before you hit the throttling threshold.</span></span>
2. <span data-ttu-id="67cb8-114">È possibile impostare `determination` la proprietà solo se è `classification` impostata su TruePositive.</span><span class="sxs-lookup"><span data-stu-id="67cb8-114">You can set the `determination` property only if `classification` is set to TruePositive.</span></span>

<span data-ttu-id="67cb8-115">Se la richiesta viene limitato, restituirà un codice `429` di risposta.</span><span class="sxs-lookup"><span data-stu-id="67cb8-115">If your request is throttled, it will return a `429` response code.</span></span> <span data-ttu-id="67cb8-116">Il corpo della risposta indicherà l'ora in cui è possibile iniziare a effettuare nuove chiamate.</span><span class="sxs-lookup"><span data-stu-id="67cb8-116">The response body will indicate the time when you can begin making new calls.</span></span>

## <a name="permissions"></a><span data-ttu-id="67cb8-117">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="67cb8-117">Permissions</span></span>

<span data-ttu-id="67cb8-118">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="67cb8-118">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="67cb8-119">Per altre informazioni, inclusa la scelta delle autorizzazioni, [vedi Accedere alle API Microsoft 365 Defender](api-access.md).</span><span class="sxs-lookup"><span data-stu-id="67cb8-119">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender APIs](api-access.md).</span></span>

<span data-ttu-id="67cb8-120">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="67cb8-120">Permission type</span></span> | <span data-ttu-id="67cb8-121">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="67cb8-121">Permission</span></span> | <span data-ttu-id="67cb8-122">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="67cb8-122">Permission display name</span></span>
-|-|-
<span data-ttu-id="67cb8-123">Applicazione</span><span class="sxs-lookup"><span data-stu-id="67cb8-123">Application</span></span> | <span data-ttu-id="67cb8-124">Incident.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="67cb8-124">Incident.ReadWrite.All</span></span> | <span data-ttu-id="67cb8-125">Lettura e scrittura di tutti gli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="67cb8-125">Read and write all incidents</span></span>
<span data-ttu-id="67cb8-126">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="67cb8-126">Delegated (work or school account)</span></span> | <span data-ttu-id="67cb8-127">Incident.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="67cb8-127">Incident.ReadWrite</span></span> | <span data-ttu-id="67cb8-128">Eventi imprevisti di lettura e scrittura</span><span class="sxs-lookup"><span data-stu-id="67cb8-128">Read and write incidents</span></span>

> [!NOTE]
> <span data-ttu-id="67cb8-129">Quando si ottiene un token utilizzando le credenziali utente, l'utente deve disporre dell'autorizzazione per aggiornare l'evento imprevisto nel portale.</span><span class="sxs-lookup"><span data-stu-id="67cb8-129">When obtaining a token using user credentials, the user needs to have permission to update the incident in the portal.</span></span>

## <a name="http-request"></a><span data-ttu-id="67cb8-130">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="67cb8-130">HTTP request</span></span>

```HTTP
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a><span data-ttu-id="67cb8-131">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="67cb8-131">Request headers</span></span>

<span data-ttu-id="67cb8-132">Name</span><span class="sxs-lookup"><span data-stu-id="67cb8-132">Name</span></span> | <span data-ttu-id="67cb8-133">Tipo</span><span class="sxs-lookup"><span data-stu-id="67cb8-133">Type</span></span> | <span data-ttu-id="67cb8-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="67cb8-134">Description</span></span>
-|-|-
<span data-ttu-id="67cb8-135">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="67cb8-135">Authorization</span></span> | <span data-ttu-id="67cb8-136">Stringa</span><span class="sxs-lookup"><span data-stu-id="67cb8-136">String</span></span> | <span data-ttu-id="67cb8-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="67cb8-137">Bearer {token}.</span></span> <span data-ttu-id="67cb8-138">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="67cb8-138">**Required**.</span></span>
<span data-ttu-id="67cb8-139">Content-Type</span><span class="sxs-lookup"><span data-stu-id="67cb8-139">Content-Type</span></span> | <span data-ttu-id="67cb8-140">Stringa</span><span class="sxs-lookup"><span data-stu-id="67cb8-140">String</span></span> | <span data-ttu-id="67cb8-141">application/json.</span><span class="sxs-lookup"><span data-stu-id="67cb8-141">application/json.</span></span> <span data-ttu-id="67cb8-142">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="67cb8-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="67cb8-143">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="67cb8-143">Request body</span></span>

<span data-ttu-id="67cb8-144">Nel corpo della richiesta specificare i valori per i campi da aggiornare.</span><span class="sxs-lookup"><span data-stu-id="67cb8-144">In the request body, supply the values for the fields that should be updated.</span></span> <span data-ttu-id="67cb8-145">Le proprietà esistenti non incluse nel corpo della richiesta manterranno i relativi valori, a meno che non sia necessario ricalcolarne il ricalcolo a causa di modifiche ai valori correlati.</span><span class="sxs-lookup"><span data-stu-id="67cb8-145">Existing properties that aren't included in the request body will maintain their values, unless they have to be recalculated due to changes to related values.</span></span> <span data-ttu-id="67cb8-146">Per ottenere prestazioni ottimali, è consigliabile omettere i valori esistenti che non sono stati modificati.</span><span class="sxs-lookup"><span data-stu-id="67cb8-146">For best performance, you should omit existing values that haven't changed.</span></span>

<span data-ttu-id="67cb8-147">Proprietà</span><span class="sxs-lookup"><span data-stu-id="67cb8-147">Property</span></span> | <span data-ttu-id="67cb8-148">Tipo</span><span class="sxs-lookup"><span data-stu-id="67cb8-148">Type</span></span> | <span data-ttu-id="67cb8-149">Descrizione</span><span class="sxs-lookup"><span data-stu-id="67cb8-149">Description</span></span>
-|-|-
<span data-ttu-id="67cb8-150">status</span><span class="sxs-lookup"><span data-stu-id="67cb8-150">status</span></span> | <span data-ttu-id="67cb8-151">Enum</span><span class="sxs-lookup"><span data-stu-id="67cb8-151">Enum</span></span> | <span data-ttu-id="67cb8-152">Specifica lo stato corrente dell'evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="67cb8-152">Specifies the current status of the incident.</span></span> <span data-ttu-id="67cb8-153">I valori possibili sono: ```Active``` ```Resolved``` , e ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="67cb8-153">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="67cb8-154">assignedTo</span><span class="sxs-lookup"><span data-stu-id="67cb8-154">assignedTo</span></span> | <span data-ttu-id="67cb8-155">stringa</span><span class="sxs-lookup"><span data-stu-id="67cb8-155">string</span></span> | <span data-ttu-id="67cb8-156">Proprietario dell'evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="67cb8-156">Owner of the incident.</span></span>
<span data-ttu-id="67cb8-157">classificazione</span><span class="sxs-lookup"><span data-stu-id="67cb8-157">classification</span></span> | <span data-ttu-id="67cb8-158">Enum</span><span class="sxs-lookup"><span data-stu-id="67cb8-158">Enum</span></span> | <span data-ttu-id="67cb8-159">Specifica dell'evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="67cb8-159">Specification of the incident.</span></span> <span data-ttu-id="67cb8-160">I valori possibili sono: ```Unknown``` , ```FalsePositive``` , ```TruePositive``` .</span><span class="sxs-lookup"><span data-stu-id="67cb8-160">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="67cb8-161">determinazione</span><span class="sxs-lookup"><span data-stu-id="67cb8-161">determination</span></span> | <span data-ttu-id="67cb8-162">Enum</span><span class="sxs-lookup"><span data-stu-id="67cb8-162">Enum</span></span> | <span data-ttu-id="67cb8-163">Specifica la determinazione dell'evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="67cb8-163">Specifies the determination of the incident.</span></span> <span data-ttu-id="67cb8-164">I valori possibili sono: ```NotAvailable``` , , , , , , ```Apt``` ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` ```UnwantedSoftware``` ```Other``` .</span><span class="sxs-lookup"><span data-stu-id="67cb8-164">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="67cb8-165">tag</span><span class="sxs-lookup"><span data-stu-id="67cb8-165">tags</span></span> | <span data-ttu-id="67cb8-166">string List</span><span class="sxs-lookup"><span data-stu-id="67cb8-166">string List</span></span> | <span data-ttu-id="67cb8-167">Elenco di tag Evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="67cb8-167">List of Incident tags.</span></span>

## <a name="response"></a><span data-ttu-id="67cb8-168">Risposta</span><span class="sxs-lookup"><span data-stu-id="67cb8-168">Response</span></span>

<span data-ttu-id="67cb8-169">Se ha esito positivo, questo metodo restituisce `200 OK` .</span><span class="sxs-lookup"><span data-stu-id="67cb8-169">If successful, this method returns `200 OK`.</span></span> <span data-ttu-id="67cb8-170">Il corpo della risposta conterrà l'entità evento imprevisto con proprietà aggiornate.</span><span class="sxs-lookup"><span data-stu-id="67cb8-170">The response body will contain the incident entity with updated properties.</span></span> <span data-ttu-id="67cb8-171">Se non è stato trovato un evento imprevisto con l'ID specificato, il metodo restituisce `404 Not Found` .</span><span class="sxs-lookup"><span data-stu-id="67cb8-171">If an incident with the specified ID wasn't found, the method returns `404 Not Found`.</span></span>

## <a name="example"></a><span data-ttu-id="67cb8-172">Esempio</span><span class="sxs-lookup"><span data-stu-id="67cb8-172">Example</span></span>

<span data-ttu-id="67cb8-173">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="67cb8-173">**Request**</span></span>

<span data-ttu-id="67cb8-174">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="67cb8-174">Here's an example of the request.</span></span>

```HTTP
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

<span data-ttu-id="67cb8-175">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="67cb8-175">**Response**</span></span>

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "TruePositive",
    "determination": "Malware",
    "tags": ["Yossi's playground", "Don't mess with the Zohan"]
}
```

## <a name="related-articles"></a><span data-ttu-id="67cb8-176">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="67cb8-176">Related articles</span></span>

- [<span data-ttu-id="67cb8-177">Accedere alle API di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="67cb8-177">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="67cb8-178">Informazioni sui limiti delle API e sulle licenze</span><span class="sxs-lookup"><span data-stu-id="67cb8-178">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="67cb8-179">Comprendere i codici di errore</span><span class="sxs-lookup"><span data-stu-id="67cb8-179">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="67cb8-180">Incidenti delle API</span><span class="sxs-lookup"><span data-stu-id="67cb8-180">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="67cb8-181">Elencare incidenti</span><span class="sxs-lookup"><span data-stu-id="67cb8-181">List incidents</span></span>](api-list-incidents.md)
- [<span data-ttu-id="67cb8-182">Panoramica degli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="67cb8-182">Incidents overview</span></span>](incidents-overview.md)
