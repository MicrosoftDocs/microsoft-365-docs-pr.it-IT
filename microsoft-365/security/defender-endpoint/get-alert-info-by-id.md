---
title: Ottenere informazioni sugli avvisi tramite l'API ID
description: Scopri come usare l'API Get alert information by ID per recuperare un avviso specifico in base al relativo ID in Microsoft Defender for Endpoint.
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
ms.openlocfilehash: f9130b054ccea762e6c5cc4f2952bbfa82d24b83
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200426"
---
# <a name="get-alert-information-by-id-api"></a><span data-ttu-id="cf366-104">Ottenere informazioni sugli avvisi tramite l'API ID</span><span class="sxs-lookup"><span data-stu-id="cf366-104">Get alert information by ID API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="cf366-105">**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="cf366-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="cf366-106">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="cf366-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="cf366-107">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="cf366-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="cf366-108">Descrizione API</span><span class="sxs-lookup"><span data-stu-id="cf366-108">API description</span></span>
<span data-ttu-id="cf366-109">Recupera un avviso [specifico in](alerts.md) base al relativo ID.</span><span class="sxs-lookup"><span data-stu-id="cf366-109">Retrieves specific [Alert](alerts.md) by its ID.</span></span>


## <a name="limitations"></a><span data-ttu-id="cf366-110">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="cf366-110">Limitations</span></span>
1. <span data-ttu-id="cf366-111">È possibile ottenere gli avvisi aggiornati per l'ultima volta in base al periodo di conservazione configurato.</span><span class="sxs-lookup"><span data-stu-id="cf366-111">You can get alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="cf366-112">I limiti di frequenza per questa API sono 100 chiamate al minuto e 1500 chiamate all'ora.</span><span class="sxs-lookup"><span data-stu-id="cf366-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="cf366-113">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="cf366-113">Permissions</span></span>
<span data-ttu-id="cf366-114">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="cf366-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="cf366-115">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi [Usare Microsoft Defender per le API endpoint](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="cf366-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="cf366-116">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="cf366-116">Permission type</span></span> |   <span data-ttu-id="cf366-117">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="cf366-117">Permission</span></span>  |   <span data-ttu-id="cf366-118">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="cf366-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="cf366-119">Applicazione</span><span class="sxs-lookup"><span data-stu-id="cf366-119">Application</span></span> |   <span data-ttu-id="cf366-120">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="cf366-120">Alert.Read.All</span></span> |    <span data-ttu-id="cf366-121">"Leggi tutti gli avvisi"</span><span class="sxs-lookup"><span data-stu-id="cf366-121">'Read all alerts'</span></span>
<span data-ttu-id="cf366-122">Applicazione</span><span class="sxs-lookup"><span data-stu-id="cf366-122">Application</span></span> |   <span data-ttu-id="cf366-123">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="cf366-123">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="cf366-124">"Lettura e scrittura di tutti gli avvisi"</span><span class="sxs-lookup"><span data-stu-id="cf366-124">'Read and write all alerts'</span></span>
<span data-ttu-id="cf366-125">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="cf366-125">Delegated (work or school account)</span></span> | <span data-ttu-id="cf366-126">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="cf366-126">Alert.Read</span></span> | <span data-ttu-id="cf366-127">"Avvisi di lettura"</span><span class="sxs-lookup"><span data-stu-id="cf366-127">'Read alerts'</span></span>
<span data-ttu-id="cf366-128">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="cf366-128">Delegated (work or school account)</span></span> | <span data-ttu-id="cf366-129">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="cf366-129">Alert.ReadWrite</span></span> | <span data-ttu-id="cf366-130">"Avvisi di lettura e scrittura"</span><span class="sxs-lookup"><span data-stu-id="cf366-130">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="cf366-131">Quando si ottiene un token utilizzando le credenziali utente:</span><span class="sxs-lookup"><span data-stu-id="cf366-131">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="cf366-132">L'utente deve disporre almeno dell'autorizzazione di ruolo seguente: 'Visualizza dati' (per ulteriori informazioni, vedere [Creare](user-roles.md) e gestire ruoli)</span><span class="sxs-lookup"><span data-stu-id="cf366-132">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="cf366-133">L'utente deve avere accesso al dispositivo associato all'avviso, in base alle impostazioni del gruppo di dispositivi (per ulteriori informazioni, vedere [Creare](machine-groups.md) e gestire gruppi di dispositivi)</span><span class="sxs-lookup"><span data-stu-id="cf366-133">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="cf366-134">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="cf366-134">HTTP request</span></span>
```
GET /api/alerts/{id}
```

## <a name="request-headers"></a><span data-ttu-id="cf366-135">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="cf366-135">Request headers</span></span>

<span data-ttu-id="cf366-136">Name</span><span class="sxs-lookup"><span data-stu-id="cf366-136">Name</span></span> | <span data-ttu-id="cf366-137">Tipo</span><span class="sxs-lookup"><span data-stu-id="cf366-137">Type</span></span> | <span data-ttu-id="cf366-138">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cf366-138">Description</span></span>
:---|:---|:---
<span data-ttu-id="cf366-139">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="cf366-139">Authorization</span></span> | <span data-ttu-id="cf366-140">Stringa</span><span class="sxs-lookup"><span data-stu-id="cf366-140">String</span></span> | <span data-ttu-id="cf366-141">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="cf366-141">Bearer {token}.</span></span> <span data-ttu-id="cf366-142">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="cf366-142">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="cf366-143">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="cf366-143">Request body</span></span>
<span data-ttu-id="cf366-144">Vuoto</span><span class="sxs-lookup"><span data-stu-id="cf366-144">Empty</span></span>

## <a name="response"></a><span data-ttu-id="cf366-145">Risposta</span><span class="sxs-lookup"><span data-stu-id="cf366-145">Response</span></span>
<span data-ttu-id="cf366-146">Se ha esito positivo, questo metodo restituisce 200 OK e l'entità [di](alerts.md) avviso nel corpo della risposta.</span><span class="sxs-lookup"><span data-stu-id="cf366-146">If successful, this method returns 200 OK, and the [alert](alerts.md) entity in the response body.</span></span> <span data-ttu-id="cf366-147">Se l'avviso con l'ID specificato non è stato trovato - 404 Non trovato.</span><span class="sxs-lookup"><span data-stu-id="cf366-147">If alert with the specified id was not found - 404 Not Found.</span></span>
