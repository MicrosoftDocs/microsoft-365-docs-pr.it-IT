---
title: API Per ottenere i computer correlati al dominio
description: Scopri come usare l'API Get domain related machines per ottenere i computer che comunicano con o da un dominio in Microsoft Defender for Endpoint.
keywords: api, api del grafico, api supportate, get, dominio, correlati, dispositivi
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
ms.openlocfilehash: 3fffb87c486e8b6b89b5e868b96d02dfae496e0b
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166877"
---
# <a name="get-domain-related-machines-api"></a><span data-ttu-id="1121f-104">API Per ottenere i computer correlati al dominio</span><span class="sxs-lookup"><span data-stu-id="1121f-104">Get domain related machines API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1121f-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="1121f-105">**Applies to:**</span></span>
- [<span data-ttu-id="1121f-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="1121f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1121f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1121f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="1121f-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="1121f-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1121f-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="1121f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="1121f-110">Descrizione API</span><span class="sxs-lookup"><span data-stu-id="1121f-110">API description</span></span>
<span data-ttu-id="1121f-111">Recupera una raccolta di [computer](machine.md) che hanno comunicato a o da un determinato indirizzo di dominio.</span><span class="sxs-lookup"><span data-stu-id="1121f-111">Retrieves a collection of [Machines](machine.md) that have communicated to or from a given domain address.</span></span>


## <a name="limitations"></a><span data-ttu-id="1121f-112">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="1121f-112">Limitations</span></span>
1. <span data-ttu-id="1121f-113">È possibile eseguire query sui dispositivi aggiornati per l'ultimo aggiornamento in base al periodo di conservazione configurato.</span><span class="sxs-lookup"><span data-stu-id="1121f-113">You can query on devices last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="1121f-114">I limiti di frequenza per questa API sono 100 chiamate al minuto e 1500 chiamate all'ora.</span><span class="sxs-lookup"><span data-stu-id="1121f-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="1121f-115">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="1121f-115">Permissions</span></span>
<span data-ttu-id="1121f-116">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="1121f-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="1121f-117">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi [Usare Microsoft Defender per le API endpoint](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="1121f-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="1121f-118">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="1121f-118">Permission type</span></span> |   <span data-ttu-id="1121f-119">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="1121f-119">Permission</span></span>  |   <span data-ttu-id="1121f-120">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="1121f-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="1121f-121">Applicazione</span><span class="sxs-lookup"><span data-stu-id="1121f-121">Application</span></span> |   <span data-ttu-id="1121f-122">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="1121f-122">Machine.Read.All</span></span> |  <span data-ttu-id="1121f-123">"Leggi tutti i profili computer"</span><span class="sxs-lookup"><span data-stu-id="1121f-123">'Read all machine profiles'</span></span>
<span data-ttu-id="1121f-124">Applicazione</span><span class="sxs-lookup"><span data-stu-id="1121f-124">Application</span></span> |   <span data-ttu-id="1121f-125">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="1121f-125">Machine.ReadWrite.All</span></span> | <span data-ttu-id="1121f-126">"Leggere e scrivere tutte le informazioni sul computer"</span><span class="sxs-lookup"><span data-stu-id="1121f-126">'Read and write all machine information'</span></span>
<span data-ttu-id="1121f-127">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="1121f-127">Delegated (work or school account)</span></span> | <span data-ttu-id="1121f-128">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="1121f-128">Machine.Read</span></span> | <span data-ttu-id="1121f-129">"Leggere le informazioni sul computer"</span><span class="sxs-lookup"><span data-stu-id="1121f-129">'Read machine information'</span></span>
<span data-ttu-id="1121f-130">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="1121f-130">Delegated (work or school account)</span></span> | <span data-ttu-id="1121f-131">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="1121f-131">Machine.ReadWrite</span></span> | <span data-ttu-id="1121f-132">"Leggere e scrivere informazioni sul computer"</span><span class="sxs-lookup"><span data-stu-id="1121f-132">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="1121f-133">Quando si ottiene un token utilizzando le credenziali utente:</span><span class="sxs-lookup"><span data-stu-id="1121f-133">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="1121f-134">L'utente deve disporre almeno dell'autorizzazione di ruolo seguente: 'Visualizza dati' (per ulteriori informazioni, vedere [Creare](user-roles.md) e gestire ruoli)</span><span class="sxs-lookup"><span data-stu-id="1121f-134">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="1121f-135">La risposta includerà solo i dispositivi a cui l'utente può accedere, in base alle impostazioni del gruppo di dispositivi (per ulteriori informazioni, vedere [Creare](machine-groups.md) e gestire gruppi di dispositivi)</span><span class="sxs-lookup"><span data-stu-id="1121f-135">Response will include only devices that the user can access, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="1121f-136">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="1121f-136">HTTP request</span></span>
```http
GET /api/domains/{domain}/machines
```

## <a name="request-headers"></a><span data-ttu-id="1121f-137">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="1121f-137">Request headers</span></span>

<span data-ttu-id="1121f-138">Name</span><span class="sxs-lookup"><span data-stu-id="1121f-138">Name</span></span> | <span data-ttu-id="1121f-139">Tipo</span><span class="sxs-lookup"><span data-stu-id="1121f-139">Type</span></span> | <span data-ttu-id="1121f-140">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1121f-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="1121f-141">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="1121f-141">Authorization</span></span> | <span data-ttu-id="1121f-142">Stringa</span><span class="sxs-lookup"><span data-stu-id="1121f-142">String</span></span> | <span data-ttu-id="1121f-143">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="1121f-143">Bearer {token}.</span></span> <span data-ttu-id="1121f-144">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="1121f-144">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="1121f-145">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="1121f-145">Request body</span></span>
<span data-ttu-id="1121f-146">Vuoto</span><span class="sxs-lookup"><span data-stu-id="1121f-146">Empty</span></span>

## <a name="response"></a><span data-ttu-id="1121f-147">Risposta</span><span class="sxs-lookup"><span data-stu-id="1121f-147">Response</span></span>
<span data-ttu-id="1121f-148">Se l'operazione ha esito positivo e il dominio esiste: 200 OK con l'elenco delle [entità](machine.md) computer.</span><span class="sxs-lookup"><span data-stu-id="1121f-148">If successful and domain exists - 200 OK with list of [machine](machine.md) entities.</span></span> <span data-ttu-id="1121f-149">Se il dominio non esiste - 404 Non trovato.</span><span class="sxs-lookup"><span data-stu-id="1121f-149">If domain do not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="1121f-150">Esempio</span><span class="sxs-lookup"><span data-stu-id="1121f-150">Example</span></span>

<span data-ttu-id="1121f-151">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="1121f-151">**Request**</span></span>

<span data-ttu-id="1121f-152">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="1121f-152">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/domains/api.securitycenter.microsoft.com/machines
```
