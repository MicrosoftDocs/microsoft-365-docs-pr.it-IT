---
title: API per ottenere avvisi correlati al dominio
description: Scopri come usare l'API Ottieni avvisi correlati al dominio per recuperare gli avvisi relativi a un determinato indirizzo di dominio in Microsoft Defender per Endpoint.
keywords: api, api del grafico, api supportate, ottenere, dominio, correlate, avvisi
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
ms.openlocfilehash: c5de779566f1aa8e53da10b9aa5bceb92f5a0a3c
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772258"
---
# <a name="get-domain-related-alerts-api"></a><span data-ttu-id="b0795-104">API per ottenere avvisi correlati al dominio</span><span class="sxs-lookup"><span data-stu-id="b0795-104">Get domain-related alerts API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b0795-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="b0795-105">**Applies to:**</span></span>
- [<span data-ttu-id="b0795-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="b0795-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b0795-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b0795-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="b0795-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="b0795-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b0795-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="b0795-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="b0795-110">Descrizione API</span><span class="sxs-lookup"><span data-stu-id="b0795-110">API description</span></span>
<span data-ttu-id="b0795-111">Recupera una raccolta di [avvisi correlati](alerts.md) a un determinato indirizzo di dominio.</span><span class="sxs-lookup"><span data-stu-id="b0795-111">Retrieves a collection of [Alerts](alerts.md) related to a given domain address.</span></span>


## <a name="limitations"></a><span data-ttu-id="b0795-112">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="b0795-112">Limitations</span></span>
1. <span data-ttu-id="b0795-113">È possibile eseguire query sugli avvisi aggiornati per l'ultimo aggiornamento in base al periodo di conservazione configurato.</span><span class="sxs-lookup"><span data-stu-id="b0795-113">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="b0795-114">I limiti di frequenza per questa API sono 100 chiamate al minuto e 1500 chiamate all'ora.</span><span class="sxs-lookup"><span data-stu-id="b0795-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="b0795-115">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="b0795-115">Permissions</span></span>
<span data-ttu-id="b0795-116">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="b0795-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="b0795-117">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi [Usare Microsoft Defender per le API endpoint](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="b0795-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="b0795-118">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="b0795-118">Permission type</span></span> |   <span data-ttu-id="b0795-119">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="b0795-119">Permission</span></span>  |   <span data-ttu-id="b0795-120">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="b0795-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="b0795-121">Applicazione</span><span class="sxs-lookup"><span data-stu-id="b0795-121">Application</span></span> |   <span data-ttu-id="b0795-122">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="b0795-122">Alert.Read.All</span></span> |    <span data-ttu-id="b0795-123">"Leggi tutti gli avvisi"</span><span class="sxs-lookup"><span data-stu-id="b0795-123">'Read all alerts'</span></span>
<span data-ttu-id="b0795-124">Applicazione</span><span class="sxs-lookup"><span data-stu-id="b0795-124">Application</span></span> |   <span data-ttu-id="b0795-125">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="b0795-125">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="b0795-126">"Lettura e scrittura di tutti gli avvisi"</span><span class="sxs-lookup"><span data-stu-id="b0795-126">'Read and write all alerts'</span></span>
<span data-ttu-id="b0795-127">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="b0795-127">Delegated (work or school account)</span></span> | <span data-ttu-id="b0795-128">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="b0795-128">Alert.Read</span></span> | <span data-ttu-id="b0795-129">"Avvisi di lettura"</span><span class="sxs-lookup"><span data-stu-id="b0795-129">'Read alerts'</span></span>
<span data-ttu-id="b0795-130">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="b0795-130">Delegated (work or school account)</span></span> | <span data-ttu-id="b0795-131">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="b0795-131">Alert.ReadWrite</span></span> | <span data-ttu-id="b0795-132">"Avvisi di lettura e scrittura"</span><span class="sxs-lookup"><span data-stu-id="b0795-132">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="b0795-133">Quando si ottiene un token utilizzando le credenziali utente:</span><span class="sxs-lookup"><span data-stu-id="b0795-133">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="b0795-134">L'utente deve disporre almeno dell'autorizzazione di ruolo seguente: 'Visualizza dati' (per ulteriori informazioni, vedere [Creare](user-roles.md) e gestire ruoli)</span><span class="sxs-lookup"><span data-stu-id="b0795-134">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="b0795-135">La risposta includerà solo gli avvisi, associati ai dispositivi, a cui l'utente ha accesso, in base alle impostazioni del gruppo di dispositivi (per ulteriori informazioni, vedere [Creare](machine-groups.md) e gestire gruppi di dispositivi)</span><span class="sxs-lookup"><span data-stu-id="b0795-135">Response will include only alerts, associated with devices, that the user have access to, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="b0795-136">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="b0795-136">HTTP request</span></span>
```http
GET /api/domains/{domain}/alerts
```

## <a name="request-headers"></a><span data-ttu-id="b0795-137">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="b0795-137">Request headers</span></span>

| <span data-ttu-id="b0795-138">Intestazione</span><span class="sxs-lookup"><span data-stu-id="b0795-138">Header</span></span>        | <span data-ttu-id="b0795-139">Valore</span><span class="sxs-lookup"><span data-stu-id="b0795-139">Value</span></span>  |
|:--------------|:-------|
| <span data-ttu-id="b0795-140">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="b0795-140">Authorization</span></span> | <span data-ttu-id="b0795-141">Stringa</span><span class="sxs-lookup"><span data-stu-id="b0795-141">String</span></span> |

## <a name="request-body"></a><span data-ttu-id="b0795-142">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="b0795-142">Request body</span></span>
<span data-ttu-id="b0795-143">Vuoto</span><span class="sxs-lookup"><span data-stu-id="b0795-143">Empty</span></span>

## <a name="response"></a><span data-ttu-id="b0795-144">Risposta</span><span class="sxs-lookup"><span data-stu-id="b0795-144">Response</span></span>
<span data-ttu-id="b0795-145">Se l'operazione ha esito positivo e il dominio esiste: 200 OK con l'elenco delle [entità](alerts.md) di avviso.</span><span class="sxs-lookup"><span data-stu-id="b0795-145">If successful and domain exists - 200 OK with list of [alert](alerts.md) entities.</span></span> <span data-ttu-id="b0795-146">Se il dominio non esiste - 404 Non trovato.</span><span class="sxs-lookup"><span data-stu-id="b0795-146">If domain does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="b0795-147">Esempio</span><span class="sxs-lookup"><span data-stu-id="b0795-147">Example</span></span>

<span data-ttu-id="b0795-148">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="b0795-148">**Request**</span></span>

<span data-ttu-id="b0795-149">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="b0795-149">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/domains/client.wns.windows.com/alerts
```
