---
title: Trovare i dispositivi in base all'API IP interna
description: Trovare i dispositivi visti con l'IP interno richiesto nell'intervallo di tempo di 15 minuti prima e dopo un determinato timestamp
keywords: api, api del grafico, api supportate, get, dispositivo, IP, trovare, trovare dispositivo, per ip, ip
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
ms.openlocfilehash: fa523a7f9b997f3a8d36dff42d10c1229e7a467f
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200438"
---
# <a name="find-devices-by-internal-ip-api"></a><span data-ttu-id="89125-104">Trovare i dispositivi in base all'API IP interna</span><span class="sxs-lookup"><span data-stu-id="89125-104">Find devices by internal IP API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="89125-105">**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="89125-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="89125-106">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="89125-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="89125-107">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="89125-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="89125-108">Descrizione API</span><span class="sxs-lookup"><span data-stu-id="89125-108">API description</span></span>
<span data-ttu-id="89125-109">Trova [i](machine.md) computer visti con l'IP interno richiesto nell'intervallo di tempo di 15 minuti prima e dopo un determinato timestamp.</span><span class="sxs-lookup"><span data-stu-id="89125-109">Find [Machines](machine.md) seen with the requested internal IP in the time range of 15 minutes prior and after a given timestamp.</span></span>


## <a name="limitations"></a><span data-ttu-id="89125-110">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="89125-110">Limitations</span></span>
1. <span data-ttu-id="89125-111">Il timestamp specificato deve essere negli ultimi 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="89125-111">The given timestamp must be in the past 30 days.</span></span>
2. <span data-ttu-id="89125-112">I limiti di frequenza per questa API sono 100 chiamate al minuto e 1500 chiamate all'ora.</span><span class="sxs-lookup"><span data-stu-id="89125-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="89125-113">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="89125-113">Permissions</span></span>
<span data-ttu-id="89125-114">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="89125-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="89125-115">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi [Usare Microsoft Defender per le API endpoint](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="89125-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="89125-116">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="89125-116">Permission type</span></span> |   <span data-ttu-id="89125-117">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="89125-117">Permission</span></span>  |   <span data-ttu-id="89125-118">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="89125-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="89125-119">Applicazione</span><span class="sxs-lookup"><span data-stu-id="89125-119">Application</span></span> |   <span data-ttu-id="89125-120">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="89125-120">Machine.Read.All</span></span> |  <span data-ttu-id="89125-121">"Leggi tutti i profili computer"</span><span class="sxs-lookup"><span data-stu-id="89125-121">'Read all machine profiles'</span></span>
<span data-ttu-id="89125-122">Applicazione</span><span class="sxs-lookup"><span data-stu-id="89125-122">Application</span></span> |   <span data-ttu-id="89125-123">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="89125-123">Machine.ReadWrite.All</span></span> | <span data-ttu-id="89125-124">"Leggere e scrivere tutte le informazioni sul computer"</span><span class="sxs-lookup"><span data-stu-id="89125-124">'Read and write all machine information'</span></span>
<span data-ttu-id="89125-125">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="89125-125">Delegated (work or school account)</span></span> | <span data-ttu-id="89125-126">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="89125-126">Machine.Read</span></span> | <span data-ttu-id="89125-127">"Leggere le informazioni sul computer"</span><span class="sxs-lookup"><span data-stu-id="89125-127">'Read machine information'</span></span>
<span data-ttu-id="89125-128">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="89125-128">Delegated (work or school account)</span></span> | <span data-ttu-id="89125-129">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="89125-129">Machine.ReadWrite</span></span> | <span data-ttu-id="89125-130">"Leggere e scrivere informazioni sul computer"</span><span class="sxs-lookup"><span data-stu-id="89125-130">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="89125-131">Quando si ottiene un token utilizzando le credenziali utente:</span><span class="sxs-lookup"><span data-stu-id="89125-131">When obtaining a token using user credentials:</span></span>
> - <span data-ttu-id="89125-132">La risposta includerà solo i dispositivi a cui l'utente ha accesso in base alle impostazioni del gruppo di dispositivi (per ulteriori informazioni, vedere [Creare](machine-groups.md) e gestire gruppi di dispositivi)</span><span class="sxs-lookup"><span data-stu-id="89125-132">Response will include only devices that the user have access to based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>
> - <span data-ttu-id="89125-133">L'utente deve disporre almeno dell'autorizzazione di ruolo seguente: 'Visualizza dati' (per ulteriori informazioni, vedere [Creare](user-roles.md) e gestire ruoli)</span><span class="sxs-lookup"><span data-stu-id="89125-133">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
> - <span data-ttu-id="89125-134">La risposta includerà solo i dispositivi a cui l'utente ha accesso in base alle impostazioni del gruppo di dispositivi (per ulteriori informazioni, vedere [Creare](machine-groups.md) e gestire gruppi di dispositivi)</span><span class="sxs-lookup"><span data-stu-id="89125-134">Response will include only devices that the user have access to based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="89125-135">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="89125-135">HTTP request</span></span>
```
GET /api/machines/findbyip(ip='{IP}',timestamp={TimeStamp})
```

## <a name="request-headers"></a><span data-ttu-id="89125-136">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="89125-136">Request headers</span></span>

<span data-ttu-id="89125-137">Name</span><span class="sxs-lookup"><span data-stu-id="89125-137">Name</span></span> | <span data-ttu-id="89125-138">Tipo</span><span class="sxs-lookup"><span data-stu-id="89125-138">Type</span></span> | <span data-ttu-id="89125-139">Descrizione</span><span class="sxs-lookup"><span data-stu-id="89125-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="89125-140">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="89125-140">Authorization</span></span> | <span data-ttu-id="89125-141">Stringa</span><span class="sxs-lookup"><span data-stu-id="89125-141">String</span></span> | <span data-ttu-id="89125-142">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="89125-142">Bearer {token}.</span></span> <span data-ttu-id="89125-143">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="89125-143">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="89125-144">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="89125-144">Request body</span></span>
<span data-ttu-id="89125-145">Vuoto</span><span class="sxs-lookup"><span data-stu-id="89125-145">Empty</span></span>

## <a name="response"></a><span data-ttu-id="89125-146">Risposta</span><span class="sxs-lookup"><span data-stu-id="89125-146">Response</span></span>
<span data-ttu-id="89125-147">Se ha esito positivo- 200 OK con l'elenco dei computer nel corpo della risposta.</span><span class="sxs-lookup"><span data-stu-id="89125-147">If successful - 200 OK with list of the machines in the response body.</span></span>
<span data-ttu-id="89125-148">Se il timestamp non è negli ultimi 30 giorni- 400 Richiesta non valida.</span><span class="sxs-lookup"><span data-stu-id="89125-148">If the timestamp is not in the past 30 days - 400 Bad Request.</span></span>

## <a name="example"></a><span data-ttu-id="89125-149">Esempio</span><span class="sxs-lookup"><span data-stu-id="89125-149">Example</span></span>

<span data-ttu-id="89125-150">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="89125-150">**Request**</span></span>

<span data-ttu-id="89125-151">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="89125-151">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/findbyip(ip='10.248.240.38',timestamp=2019-09-22T08:44:05Z)
```
