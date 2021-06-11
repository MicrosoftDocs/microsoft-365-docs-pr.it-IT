---
title: API per ottenere eventi imprevisti
description: Scopri come usare l'API Get incidents per ottenere un singolo evento imprevisto in Microsoft 365 Defender.
keywords: api, api del grafico, api supportate, get, file, hash
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
ms.openlocfilehash: c578a353501ac7b38ac541b0200ffaad1d6743e1
ms.sourcegitcommit: 03aa8ed22d9ef685a851e28c7d0cfb725732fe4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2021
ms.locfileid: "52888449"
---
# <a name="get-incident-information-api"></a><span data-ttu-id="f890d-104">API per ottenere informazioni sugli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="f890d-104">Get incident information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f890d-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="f890d-105">**Applies to:**</span></span>
- [<span data-ttu-id="f890d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f890d-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f890d-107">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="f890d-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f890d-108">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="f890d-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="f890d-109">Descrizione API</span><span class="sxs-lookup"><span data-stu-id="f890d-109">API description</span></span>
<span data-ttu-id="f890d-110">Recupera un evento imprevisto specifico in base al relativo ID</span><span class="sxs-lookup"><span data-stu-id="f890d-110">Retrieves a specific incident by its ID</span></span>


## <a name="limitations"></a><span data-ttu-id="f890d-111">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="f890d-111">Limitations</span></span>
1. <span data-ttu-id="f890d-112">I limiti di frequenza per questa API sono 100 chiamate al minuto e 1500 chiamate all'ora.</span><span class="sxs-lookup"><span data-stu-id="f890d-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="f890d-113">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="f890d-113">Permissions</span></span>
<span data-ttu-id="f890d-114">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="f890d-114">One of the following permissions is required to call this API.</span></span> 

<span data-ttu-id="f890d-115">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="f890d-115">Permission type</span></span> |   <span data-ttu-id="f890d-116">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="f890d-116">Permission</span></span>  |   <span data-ttu-id="f890d-117">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="f890d-117">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="f890d-118">Applicazione</span><span class="sxs-lookup"><span data-stu-id="f890d-118">Application</span></span> |   <span data-ttu-id="f890d-119">Incident.Read.All</span><span class="sxs-lookup"><span data-stu-id="f890d-119">Incident.Read.All</span></span> | <span data-ttu-id="f890d-120">"Leggi tutti gli eventi imprevisti"</span><span class="sxs-lookup"><span data-stu-id="f890d-120">'Read all Incidents'</span></span>
<span data-ttu-id="f890d-121">Applicazione</span><span class="sxs-lookup"><span data-stu-id="f890d-121">Application</span></span> |   <span data-ttu-id="f890d-122">Incident.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="f890d-122">Incident.ReadWrite.All</span></span> |    <span data-ttu-id="f890d-123">"Lettura e scrittura di tutti gli eventi imprevisti"</span><span class="sxs-lookup"><span data-stu-id="f890d-123">'Read and write all Incidents'</span></span>
<span data-ttu-id="f890d-124">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="f890d-124">Delegated (work or school account)</span></span> | <span data-ttu-id="f890d-125">Incident.Read</span><span class="sxs-lookup"><span data-stu-id="f890d-125">Incident.Read</span></span> | <span data-ttu-id="f890d-126">"Operazioni non consentite di lettura"</span><span class="sxs-lookup"><span data-stu-id="f890d-126">'Read Incidents'</span></span>
<span data-ttu-id="f890d-127">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="f890d-127">Delegated (work or school account)</span></span> | <span data-ttu-id="f890d-128">Incident.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="f890d-128">Incident.ReadWrite</span></span> | <span data-ttu-id="f890d-129">"Eventi imprevisti di lettura e scrittura"</span><span class="sxs-lookup"><span data-stu-id="f890d-129">'Read and write Incidents'</span></span>

>[!Note]
> <span data-ttu-id="f890d-130">Quando si ottiene un token utilizzando le credenziali utente:</span><span class="sxs-lookup"><span data-stu-id="f890d-130">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="f890d-131">L'utente deve disporre almeno dell'autorizzazione di ruolo seguente: 'Visualizza dati'</span><span class="sxs-lookup"><span data-stu-id="f890d-131">The user needs to have at least the following role permission: 'View Data'</span></span>
>- <span data-ttu-id="f890d-132">La risposta includerà solo gli eventi imprevisti a cui l'utente è esposto</span><span class="sxs-lookup"><span data-stu-id="f890d-132">The response will only include incidents that the user is exposed to</span></span>

## <a name="http-request"></a><span data-ttu-id="f890d-133">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="f890d-133">HTTP request</span></span>

```console
GET .../api/incidents/{id} 
```

## <a name="request-headers"></a><span data-ttu-id="f890d-134">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="f890d-134">Request headers</span></span>

<span data-ttu-id="f890d-135">Name</span><span class="sxs-lookup"><span data-stu-id="f890d-135">Name</span></span> | <span data-ttu-id="f890d-136">Tipo</span><span class="sxs-lookup"><span data-stu-id="f890d-136">Type</span></span> | <span data-ttu-id="f890d-137">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f890d-137">Description</span></span>
:---|:---|:---
<span data-ttu-id="f890d-138">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="f890d-138">Authorization</span></span> | <span data-ttu-id="f890d-139">Stringa</span><span class="sxs-lookup"><span data-stu-id="f890d-139">String</span></span> | <span data-ttu-id="f890d-140">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="f890d-140">Bearer {token}.</span></span> <span data-ttu-id="f890d-141">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="f890d-141">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="f890d-142">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="f890d-142">Request body</span></span>
<span data-ttu-id="f890d-143">Vuoto</span><span class="sxs-lookup"><span data-stu-id="f890d-143">Empty</span></span>

## <a name="response"></a><span data-ttu-id="f890d-144">Risposta</span><span class="sxs-lookup"><span data-stu-id="f890d-144">Response</span></span>

<span data-ttu-id="f890d-145">Se ha esito positivo, questo metodo restituisce 200 OK e l'entità evento imprevisto nel corpo della risposta.</span><span class="sxs-lookup"><span data-stu-id="f890d-145">If successful, this method returns 200 OK, and the incident entity in the response body.</span></span> <span data-ttu-id="f890d-146">Se non è stato trovato un evento imprevisto con l'ID specificato - 404 Non trovato.</span><span class="sxs-lookup"><span data-stu-id="f890d-146">If incident with the specified id was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="f890d-147">Esempio</span><span class="sxs-lookup"><span data-stu-id="f890d-147">Example</span></span>

<span data-ttu-id="f890d-148">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="f890d-148">**Request**</span></span>

<span data-ttu-id="f890d-149">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="f890d-149">Here is an example of the request.</span></span>

```http
GET https://api.security.microsoft.com/api/incidents/{id}
```
