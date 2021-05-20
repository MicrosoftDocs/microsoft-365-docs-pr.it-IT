---
title: Aggiornare l'API degli incidenti
description: Informazioni su come aggiornare gli incidenti utilizzando l'API Microsoft 365 Defender
keywords: aggiornamento, api, incidente
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
ms.openlocfilehash: e3f3919d067078ef1fd1e116dc52e8a73c0726d9
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571782"
---
# <a name="update-incident-api"></a><span data-ttu-id="19e54-104">Aggiornare l'API degli incidenti</span><span class="sxs-lookup"><span data-stu-id="19e54-104">Update incident API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="19e54-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="19e54-105">**Applies to:**</span></span>

- <span data-ttu-id="19e54-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="19e54-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="19e54-107">Alcune informazioni fanno riferimento alle caratteristiche del prodotto prima del rilascio, e possono essere modificate sostanzialmente prima della distribuzione al pubblico.</span><span class="sxs-lookup"><span data-stu-id="19e54-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="19e54-108">Microsoft non fornisce alcuna garanzia, esplicita o implicita, in relazione alle informazioni contenute in questo documento.</span><span class="sxs-lookup"><span data-stu-id="19e54-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="api-description"></a><span data-ttu-id="19e54-109">Descrizione API</span><span class="sxs-lookup"><span data-stu-id="19e54-109">API description</span></span>

<span data-ttu-id="19e54-110">Aggiorna le proprietà dell'incidente esistente.</span><span class="sxs-lookup"><span data-stu-id="19e54-110">Updates properties of existing incident.</span></span> <span data-ttu-id="19e54-111">Le proprietà aggiornabili sono: ```status``` , , , , e ```determination``` ```classification``` ```assignedTo``` ```tags``` ```comments``` .</span><span class="sxs-lookup"><span data-stu-id="19e54-111">Updatable properties are: ```status```, ```determination```, ```classification```, ```assignedTo```, ```tags```, and ```comments```.</span></span>

### <a name="quotas-resource-allocation-and-other-constraints"></a><span data-ttu-id="19e54-112">Quote, allocazione delle risorse e altri vincoli</span><span class="sxs-lookup"><span data-stu-id="19e54-112">Quotas, resource allocation, and other constraints</span></span>

1. <span data-ttu-id="19e54-113">È possibile effettuare fino a 50 chiamate al minuto o 1500 chiamate all'ora prima di raggiungere la soglia di limitazione.</span><span class="sxs-lookup"><span data-stu-id="19e54-113">You can make up to 50 calls per minute or 1500 calls per hour before you hit the throttling threshold.</span></span>
2. <span data-ttu-id="19e54-114">È possibile impostare la `determination` proprietà solo se è `classification` impostata su TruePositive.</span><span class="sxs-lookup"><span data-stu-id="19e54-114">You can set the `determination` property only if `classification` is set to TruePositive.</span></span>

<span data-ttu-id="19e54-115">Se la richiesta è limitata, restituirà un codice `429` di risposta.</span><span class="sxs-lookup"><span data-stu-id="19e54-115">If your request is throttled, it will return a `429` response code.</span></span> <span data-ttu-id="19e54-116">Il corpo della risposta indicherà l'ora in cui è possibile iniziare a effettuare nuove chiamate.</span><span class="sxs-lookup"><span data-stu-id="19e54-116">The response body will indicate the time when you can begin making new calls.</span></span>

## <a name="permissions"></a><span data-ttu-id="19e54-117">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="19e54-117">Permissions</span></span>

<span data-ttu-id="19e54-118">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="19e54-118">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="19e54-119">Per ulteriori informazioni, incluso come scegliere le autorizzazioni, [vedere Accedere alle API Microsoft 365 Defender](api-access.md).</span><span class="sxs-lookup"><span data-stu-id="19e54-119">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender APIs](api-access.md).</span></span>

<span data-ttu-id="19e54-120">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="19e54-120">Permission type</span></span> | <span data-ttu-id="19e54-121">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="19e54-121">Permission</span></span> | <span data-ttu-id="19e54-122">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="19e54-122">Permission display name</span></span>
-|-|-
<span data-ttu-id="19e54-123">Applicazione</span><span class="sxs-lookup"><span data-stu-id="19e54-123">Application</span></span> | <span data-ttu-id="19e54-124">Incident.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="19e54-124">Incident.ReadWrite.All</span></span> | <span data-ttu-id="19e54-125">Leggere e scrivere tutti gli incidenti</span><span class="sxs-lookup"><span data-stu-id="19e54-125">Read and write all incidents</span></span>
<span data-ttu-id="19e54-126">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="19e54-126">Delegated (work or school account)</span></span> | <span data-ttu-id="19e54-127">Incident.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="19e54-127">Incident.ReadWrite</span></span> | <span data-ttu-id="19e54-128">Leggere e scrivere incidenti</span><span class="sxs-lookup"><span data-stu-id="19e54-128">Read and write incidents</span></span>

> [!NOTE]
> <span data-ttu-id="19e54-129">Quando si ottiene un token utilizzando le credenziali utente, l'utente deve avere l'autorizzazione per aggiornare l'incidente nel portale.</span><span class="sxs-lookup"><span data-stu-id="19e54-129">When obtaining a token using user credentials, the user needs to have permission to update the incident in the portal.</span></span>

## <a name="http-request"></a><span data-ttu-id="19e54-130">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="19e54-130">HTTP request</span></span>

```HTTP
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a><span data-ttu-id="19e54-131">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="19e54-131">Request headers</span></span>

<span data-ttu-id="19e54-132">Name</span><span class="sxs-lookup"><span data-stu-id="19e54-132">Name</span></span> | <span data-ttu-id="19e54-133">Tipo</span><span class="sxs-lookup"><span data-stu-id="19e54-133">Type</span></span> | <span data-ttu-id="19e54-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="19e54-134">Description</span></span>
-|-|-
<span data-ttu-id="19e54-135">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="19e54-135">Authorization</span></span> | <span data-ttu-id="19e54-136">Stringa</span><span class="sxs-lookup"><span data-stu-id="19e54-136">String</span></span> | <span data-ttu-id="19e54-137">Portatore {token}.</span><span class="sxs-lookup"><span data-stu-id="19e54-137">Bearer {token}.</span></span> <span data-ttu-id="19e54-138">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="19e54-138">**Required**.</span></span>
<span data-ttu-id="19e54-139">Content-Type</span><span class="sxs-lookup"><span data-stu-id="19e54-139">Content-Type</span></span> | <span data-ttu-id="19e54-140">Stringa</span><span class="sxs-lookup"><span data-stu-id="19e54-140">String</span></span> | <span data-ttu-id="19e54-141">domanda/json.</span><span class="sxs-lookup"><span data-stu-id="19e54-141">application/json.</span></span> <span data-ttu-id="19e54-142">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="19e54-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="19e54-143">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="19e54-143">Request body</span></span>

<span data-ttu-id="19e54-144">Nel corpo della richiesta fornire i valori per i campi da aggiornare.</span><span class="sxs-lookup"><span data-stu-id="19e54-144">In the request body, supply the values for the fields that should be updated.</span></span> <span data-ttu-id="19e54-145">Le proprietà esistenti che non sono incluse nel corpo della richiesta manterranno i relativi valori, a meno che non rocali a causa di modifiche ai valori correlati.</span><span class="sxs-lookup"><span data-stu-id="19e54-145">Existing properties that aren't included in the request body will maintain their values, unless they have to be recalculated due to changes to related values.</span></span> <span data-ttu-id="19e54-146">Per ottenere prestazioni ottimali, è necessario omettere i valori esistenti che non sono stati modificati.</span><span class="sxs-lookup"><span data-stu-id="19e54-146">For best performance, you should omit existing values that haven't changed.</span></span>

<span data-ttu-id="19e54-147">Proprietà</span><span class="sxs-lookup"><span data-stu-id="19e54-147">Property</span></span> | <span data-ttu-id="19e54-148">Tipo</span><span class="sxs-lookup"><span data-stu-id="19e54-148">Type</span></span> | <span data-ttu-id="19e54-149">Descrizione</span><span class="sxs-lookup"><span data-stu-id="19e54-149">Description</span></span>
-|-|-
<span data-ttu-id="19e54-150">stato</span><span class="sxs-lookup"><span data-stu-id="19e54-150">status</span></span> | <span data-ttu-id="19e54-151">Enum</span><span class="sxs-lookup"><span data-stu-id="19e54-151">Enum</span></span> | <span data-ttu-id="19e54-152">Specifica lo stato corrente dell'incidente.</span><span class="sxs-lookup"><span data-stu-id="19e54-152">Specifies the current status of the incident.</span></span> <span data-ttu-id="19e54-153">I valori possibili sono: ```Active``` ```Resolved``` , e ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="19e54-153">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="19e54-154">assegnatoA</span><span class="sxs-lookup"><span data-stu-id="19e54-154">assignedTo</span></span> | <span data-ttu-id="19e54-155">stringa</span><span class="sxs-lookup"><span data-stu-id="19e54-155">string</span></span> | <span data-ttu-id="19e54-156">Proprietario dell'incidente.</span><span class="sxs-lookup"><span data-stu-id="19e54-156">Owner of the incident.</span></span>
<span data-ttu-id="19e54-157">classificazione</span><span class="sxs-lookup"><span data-stu-id="19e54-157">classification</span></span> | <span data-ttu-id="19e54-158">Enum</span><span class="sxs-lookup"><span data-stu-id="19e54-158">Enum</span></span> | <span data-ttu-id="19e54-159">Specifica dell'incidente.</span><span class="sxs-lookup"><span data-stu-id="19e54-159">Specification of the incident.</span></span> <span data-ttu-id="19e54-160">I valori possibili sono: ```Unknown``` , ```FalsePositive``` , ```TruePositive``` .</span><span class="sxs-lookup"><span data-stu-id="19e54-160">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="19e54-161">determinazione</span><span class="sxs-lookup"><span data-stu-id="19e54-161">determination</span></span> | <span data-ttu-id="19e54-162">Enum</span><span class="sxs-lookup"><span data-stu-id="19e54-162">Enum</span></span> | <span data-ttu-id="19e54-163">Specifica la determinazione dell'incidente.</span><span class="sxs-lookup"><span data-stu-id="19e54-163">Specifies the determination of the incident.</span></span> <span data-ttu-id="19e54-164">I valori possibili sono: ```NotAvailable``` , , , , , , ```Apt``` ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` ```UnwantedSoftware``` ```Other``` .</span><span class="sxs-lookup"><span data-stu-id="19e54-164">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="19e54-165">Tag</span><span class="sxs-lookup"><span data-stu-id="19e54-165">tags</span></span> | <span data-ttu-id="19e54-166">elenco di stringhe</span><span class="sxs-lookup"><span data-stu-id="19e54-166">string List</span></span> | <span data-ttu-id="19e54-167">Elenco di tag Incidente.</span><span class="sxs-lookup"><span data-stu-id="19e54-167">List of Incident tags.</span></span>
<span data-ttu-id="19e54-168">commento</span><span class="sxs-lookup"><span data-stu-id="19e54-168">comment</span></span> | <span data-ttu-id="19e54-169">stringa</span><span class="sxs-lookup"><span data-stu-id="19e54-169">string</span></span> | <span data-ttu-id="19e54-170">Commento da aggiungere all'incidente.</span><span class="sxs-lookup"><span data-stu-id="19e54-170">Comment to be added to the incident.</span></span>

## <a name="response"></a><span data-ttu-id="19e54-171">Risposta</span><span class="sxs-lookup"><span data-stu-id="19e54-171">Response</span></span>

<span data-ttu-id="19e54-172">In caso di esito positivo, questo metodo restituisce `200 OK` .</span><span class="sxs-lookup"><span data-stu-id="19e54-172">If successful, this method returns `200 OK`.</span></span> <span data-ttu-id="19e54-173">Il corpo della risposta conterrà l'entità incidente con proprietà aggiornate.</span><span class="sxs-lookup"><span data-stu-id="19e54-173">The response body will contain the incident entity with updated properties.</span></span> <span data-ttu-id="19e54-174">Se non è stato trovato un incidente con l'ID specificato, il metodo restituisce `404 Not Found` .</span><span class="sxs-lookup"><span data-stu-id="19e54-174">If an incident with the specified ID wasn't found, the method returns `404 Not Found`.</span></span>

## <a name="example"></a><span data-ttu-id="19e54-175">Esempio</span><span class="sxs-lookup"><span data-stu-id="19e54-175">Example</span></span>

<span data-ttu-id="19e54-176">**richiesta**</span><span class="sxs-lookup"><span data-stu-id="19e54-176">**Request**</span></span>

<span data-ttu-id="19e54-177">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="19e54-177">Here's an example of the request.</span></span>

```HTTP
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

<span data-ttu-id="19e54-178">**risposta**</span><span class="sxs-lookup"><span data-stu-id="19e54-178">**Response**</span></span>

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "TruePositive",
    "determination": "Malware",
    "tags": ["Yossi's playground", "Don't mess with the Zohan"],
    "comments": [
          {
              "comment": "pen testing",
              "createdBy": "secop2@contoso.com",
              "createdTime": "2021-05-02T09:34:21.5519738Z"
          },
          {
              "comment": "valid incident",
              "createdBy": "secop2@contoso.comt",
              "createdTime": "2021-05-02T09:36:27.6652581Z"
          }
      ]
}
```

## <a name="related-articles"></a><span data-ttu-id="19e54-179">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="19e54-179">Related articles</span></span>

- [<span data-ttu-id="19e54-180">Accedere alle API Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="19e54-180">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="19e54-181">Informazioni sui limiti e le licenze delle API</span><span class="sxs-lookup"><span data-stu-id="19e54-181">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="19e54-182">Informazioni i codici di errore</span><span class="sxs-lookup"><span data-stu-id="19e54-182">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="19e54-183">Incidenti delle API</span><span class="sxs-lookup"><span data-stu-id="19e54-183">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="19e54-184">Elencare incidenti</span><span class="sxs-lookup"><span data-stu-id="19e54-184">List incidents</span></span>](api-list-incidents.md)
- [<span data-ttu-id="19e54-185">Panoramica degli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="19e54-185">Incidents overview</span></span>](incidents-overview.md)
