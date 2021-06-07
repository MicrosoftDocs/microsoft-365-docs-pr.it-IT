---
title: API per ottenere avvisi correlati ai file
description: Scopri come usare l'API Get file-related alerts per ottenere una raccolta di avvisi correlati a un determinato hash di file in Microsoft Defender for Endpoint.
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
ms.openlocfilehash: b77946f4bfdb793ffbfdf102a7221df083fb92eb
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770300"
---
# <a name="get-file-related-alerts-api"></a><span data-ttu-id="24105-104">API per ottenere avvisi correlati ai file</span><span class="sxs-lookup"><span data-stu-id="24105-104">Get file-related alerts API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="24105-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="24105-105">**Applies to:**</span></span>
- [<span data-ttu-id="24105-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="24105-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="24105-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="24105-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="24105-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="24105-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="24105-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="24105-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="24105-110">Descrizione API</span><span class="sxs-lookup"><span data-stu-id="24105-110">API description</span></span>
<span data-ttu-id="24105-111">Recupera una raccolta di avvisi correlati a un determinato hash di file.</span><span class="sxs-lookup"><span data-stu-id="24105-111">Retrieves a collection of alerts related to a given file hash.</span></span>


## <a name="limitations"></a><span data-ttu-id="24105-112">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="24105-112">Limitations</span></span>
1. <span data-ttu-id="24105-113">I limiti di frequenza per questa API sono 100 chiamate al minuto e 1500 chiamate all'ora.</span><span class="sxs-lookup"><span data-stu-id="24105-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="24105-114">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="24105-114">Permissions</span></span>
<span data-ttu-id="24105-115">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="24105-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="24105-116">Per altre informazioni, incluso come scegliere le autorizzazioni, vedi [Usare Defender per le API endpoint](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="24105-116">To learn more, including how to choose permissions, see [Use Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="24105-117">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="24105-117">Permission type</span></span> |   <span data-ttu-id="24105-118">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="24105-118">Permission</span></span>  |   <span data-ttu-id="24105-119">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="24105-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="24105-120">Applicazione</span><span class="sxs-lookup"><span data-stu-id="24105-120">Application</span></span> |   <span data-ttu-id="24105-121">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="24105-121">Alert.Read.All</span></span> |    <span data-ttu-id="24105-122">"Leggi tutti gli avvisi"</span><span class="sxs-lookup"><span data-stu-id="24105-122">'Read all alerts'</span></span>
<span data-ttu-id="24105-123">Applicazione</span><span class="sxs-lookup"><span data-stu-id="24105-123">Application</span></span> |   <span data-ttu-id="24105-124">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="24105-124">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="24105-125">"Lettura e scrittura di tutti gli avvisi"</span><span class="sxs-lookup"><span data-stu-id="24105-125">'Read and write all alerts'</span></span>
<span data-ttu-id="24105-126">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="24105-126">Delegated (work or school account)</span></span> | <span data-ttu-id="24105-127">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="24105-127">Alert.Read</span></span> | <span data-ttu-id="24105-128">"Avvisi di lettura"</span><span class="sxs-lookup"><span data-stu-id="24105-128">'Read alerts'</span></span>
<span data-ttu-id="24105-129">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="24105-129">Delegated (work or school account)</span></span> | <span data-ttu-id="24105-130">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="24105-130">Alert.ReadWrite</span></span> | <span data-ttu-id="24105-131">"Avvisi di lettura e scrittura"</span><span class="sxs-lookup"><span data-stu-id="24105-131">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="24105-132">Quando si ottiene un token utilizzando le credenziali utente:</span><span class="sxs-lookup"><span data-stu-id="24105-132">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="24105-133">L'utente deve disporre almeno dell'autorizzazione di ruolo seguente: 'Visualizza dati' (per ulteriori informazioni, vedere [Creare](user-roles.md) e gestire ruoli)</span><span class="sxs-lookup"><span data-stu-id="24105-133">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="24105-134">La risposta includerà solo gli avvisi, associati ai dispositivi, a cui l'utente ha accesso, in base alle impostazioni del gruppo di dispositivi (per ulteriori informazioni, vedere [Creare](machine-groups.md) e gestire gruppi di dispositivi)</span><span class="sxs-lookup"><span data-stu-id="24105-134">Response will include only alerts, associated with devices, that the user have access to, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="24105-135">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="24105-135">HTTP request</span></span>
```
GET /api/files/{id}/alerts
```

## <a name="request-headers"></a><span data-ttu-id="24105-136">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="24105-136">Request headers</span></span>

<span data-ttu-id="24105-137">Name</span><span class="sxs-lookup"><span data-stu-id="24105-137">Name</span></span> | <span data-ttu-id="24105-138">Tipo</span><span class="sxs-lookup"><span data-stu-id="24105-138">Type</span></span> | <span data-ttu-id="24105-139">Descrizione</span><span class="sxs-lookup"><span data-stu-id="24105-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="24105-140">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="24105-140">Authorization</span></span> | <span data-ttu-id="24105-141">Stringa</span><span class="sxs-lookup"><span data-stu-id="24105-141">String</span></span> | <span data-ttu-id="24105-142">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="24105-142">Bearer {token}.</span></span> <span data-ttu-id="24105-143">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="24105-143">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="24105-144">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="24105-144">Request body</span></span>
<span data-ttu-id="24105-145">Vuoto</span><span class="sxs-lookup"><span data-stu-id="24105-145">Empty</span></span>

## <a name="response"></a><span data-ttu-id="24105-146">Risposta</span><span class="sxs-lookup"><span data-stu-id="24105-146">Response</span></span>
<span data-ttu-id="24105-147">Se ha esito positivo e il file [](alerts.md) esiste- 200 OK con l'elenco delle entità di avviso nel corpo.</span><span class="sxs-lookup"><span data-stu-id="24105-147">If successful and file exists - 200 OK with list of [alert](alerts.md) entities in the body.</span></span> <span data-ttu-id="24105-148">Se il file non esiste - 404 Non trovato.</span><span class="sxs-lookup"><span data-stu-id="24105-148">If file does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="24105-149">Esempio</span><span class="sxs-lookup"><span data-stu-id="24105-149">Example</span></span>

<span data-ttu-id="24105-150">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="24105-150">**Request**</span></span>

<span data-ttu-id="24105-151">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="24105-151">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/files/6532ec91d513acc05f43ee0aa3002599729fd3e1/alerts
```
