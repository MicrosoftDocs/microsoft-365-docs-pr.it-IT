---
title: API per ottenere avvisi correlati al computer
description: Scopri come usare l'API Ottieni avvisi correlati al computer per recuperare tutti gli avvisi relativi a un dispositivo specifico in Microsoft Defender per Endpoint.
keywords: api, api del grafico, api supportate, get, dispositivi, correlati, avvisi
search.product: eADQiWindows 10XVcnh
ms.prod: w10
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
ms.openlocfilehash: 837643bf5793437380a6f33c0eeca55ccef2100b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199252"
---
# <a name="get-machine-related-alerts--api"></a><span data-ttu-id="38a81-104">API per ottenere avvisi correlati al computer</span><span class="sxs-lookup"><span data-stu-id="38a81-104">Get machine related alerts  API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="38a81-105">**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="38a81-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="38a81-106">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="38a81-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="38a81-107">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="38a81-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="38a81-108">Descrizione API</span><span class="sxs-lookup"><span data-stu-id="38a81-108">API description</span></span>
<span data-ttu-id="38a81-109">Recupera tutti gli [avvisi](alerts.md) correlati a un dispositivo specifico.</span><span class="sxs-lookup"><span data-stu-id="38a81-109">Retrieves all [Alerts](alerts.md) related to a specific device.</span></span>


## <a name="limitations"></a><span data-ttu-id="38a81-110">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="38a81-110">Limitations</span></span>
1. <span data-ttu-id="38a81-111">È possibile eseguire query sui dispositivi aggiornati per l'ultimo aggiornamento in base al periodo di conservazione configurato.</span><span class="sxs-lookup"><span data-stu-id="38a81-111">You can query on devices last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="38a81-112">I limiti di frequenza per questa API sono 100 chiamate al minuto e 1500 chiamate all'ora.</span><span class="sxs-lookup"><span data-stu-id="38a81-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


<span data-ttu-id="38a81-113">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="38a81-113">Permission type</span></span> |   <span data-ttu-id="38a81-114">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="38a81-114">Permission</span></span>  |   <span data-ttu-id="38a81-115">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="38a81-115">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="38a81-116">Applicazione</span><span class="sxs-lookup"><span data-stu-id="38a81-116">Application</span></span> |   <span data-ttu-id="38a81-117">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="38a81-117">Alert.Read.All</span></span> |    <span data-ttu-id="38a81-118">"Leggi tutti gli avvisi"</span><span class="sxs-lookup"><span data-stu-id="38a81-118">'Read all alerts'</span></span>
<span data-ttu-id="38a81-119">Applicazione</span><span class="sxs-lookup"><span data-stu-id="38a81-119">Application</span></span> |   <span data-ttu-id="38a81-120">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="38a81-120">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="38a81-121">"Lettura e scrittura di tutti gli avvisi"</span><span class="sxs-lookup"><span data-stu-id="38a81-121">'Read and write all alerts'</span></span>
<span data-ttu-id="38a81-122">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="38a81-122">Delegated (work or school account)</span></span> | <span data-ttu-id="38a81-123">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="38a81-123">Alert.Read</span></span> | <span data-ttu-id="38a81-124">"Avvisi di lettura"</span><span class="sxs-lookup"><span data-stu-id="38a81-124">'Read alerts'</span></span>
<span data-ttu-id="38a81-125">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="38a81-125">Delegated (work or school account)</span></span> | <span data-ttu-id="38a81-126">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="38a81-126">Alert.ReadWrite</span></span> | <span data-ttu-id="38a81-127">"Avvisi di lettura e scrittura"</span><span class="sxs-lookup"><span data-stu-id="38a81-127">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="38a81-128">Quando si ottiene un token utilizzando le credenziali utente:</span><span class="sxs-lookup"><span data-stu-id="38a81-128">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="38a81-129">L'utente deve disporre almeno dell'autorizzazione di ruolo seguente: 'Visualizza dati' (per ulteriori informazioni, vedere [Creare](user-roles.md) e gestire ruoli)</span><span class="sxs-lookup"><span data-stu-id="38a81-129">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="38a81-130">L'utente deve avere accesso al dispositivo in base alle impostazioni del gruppo di dispositivi (per ulteriori informazioni, vedere [Creare](machine-groups.md) e gestire gruppi di dispositivi)</span><span class="sxs-lookup"><span data-stu-id="38a81-130">User needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="38a81-131">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="38a81-131">HTTP request</span></span>
```http
GET /api/machines/{id}/alerts
```

## <a name="request-headers"></a><span data-ttu-id="38a81-132">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="38a81-132">Request headers</span></span>

<span data-ttu-id="38a81-133">Name</span><span class="sxs-lookup"><span data-stu-id="38a81-133">Name</span></span> | <span data-ttu-id="38a81-134">Tipo</span><span class="sxs-lookup"><span data-stu-id="38a81-134">Type</span></span> | <span data-ttu-id="38a81-135">Descrizione</span><span class="sxs-lookup"><span data-stu-id="38a81-135">Description</span></span>
:---|:---|:---
<span data-ttu-id="38a81-136">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="38a81-136">Authorization</span></span> | <span data-ttu-id="38a81-137">Stringa</span><span class="sxs-lookup"><span data-stu-id="38a81-137">String</span></span> | <span data-ttu-id="38a81-138">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="38a81-138">Bearer {token}.</span></span> <span data-ttu-id="38a81-139">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="38a81-139">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="38a81-140">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="38a81-140">Request body</span></span>
<span data-ttu-id="38a81-141">Vuoto</span><span class="sxs-lookup"><span data-stu-id="38a81-141">Empty</span></span>

## <a name="response"></a><span data-ttu-id="38a81-142">Risposta</span><span class="sxs-lookup"><span data-stu-id="38a81-142">Response</span></span>
<span data-ttu-id="38a81-143">Se l'operazione ha esito positivo e [](alerts.md) il dispositivo esiste: 200 OK con l'elenco delle entità di avviso nel corpo.</span><span class="sxs-lookup"><span data-stu-id="38a81-143">If successful and device exists - 200 OK with list of [alert](alerts.md) entities in the body.</span></span> <span data-ttu-id="38a81-144">Se il dispositivo non è stato trovato - 404 Non trovato.</span><span class="sxs-lookup"><span data-stu-id="38a81-144">If device was not found - 404 Not Found.</span></span>
