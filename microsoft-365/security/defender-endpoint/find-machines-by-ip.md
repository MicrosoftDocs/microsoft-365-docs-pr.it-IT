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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 46afa945ce86c35e3af1c542eb1a9770041b3430
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769438"
---
# <a name="find-devices-by-internal-ip-api"></a><span data-ttu-id="61533-104">Trovare i dispositivi in base all'API IP interna</span><span class="sxs-lookup"><span data-stu-id="61533-104">Find devices by internal IP API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="61533-105">**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="61533-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="61533-106">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="61533-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="61533-107">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="61533-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="61533-108">Descrizione API</span><span class="sxs-lookup"><span data-stu-id="61533-108">API description</span></span>
<span data-ttu-id="61533-109">Trova [i](machine.md) computer visti con l'IP interno richiesto nell'intervallo di tempo di 15 minuti prima e dopo un determinato timestamp.</span><span class="sxs-lookup"><span data-stu-id="61533-109">Find [Machines](machine.md) seen with the requested internal IP in the time range of 15 minutes prior and after a given timestamp.</span></span>


## <a name="limitations"></a><span data-ttu-id="61533-110">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="61533-110">Limitations</span></span>
1. <span data-ttu-id="61533-111">Il timestamp specificato deve essere negli ultimi 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="61533-111">The given timestamp must be in the past 30 days.</span></span>
2. <span data-ttu-id="61533-112">I limiti di frequenza per questa API sono 100 chiamate al minuto e 1500 chiamate all'ora.</span><span class="sxs-lookup"><span data-stu-id="61533-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="61533-113">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="61533-113">Permissions</span></span>
<span data-ttu-id="61533-114">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="61533-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="61533-115">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi [Usare Microsoft Defender per le API endpoint](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="61533-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="61533-116">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="61533-116">Permission type</span></span> |   <span data-ttu-id="61533-117">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="61533-117">Permission</span></span>  |   <span data-ttu-id="61533-118">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="61533-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="61533-119">Applicazione</span><span class="sxs-lookup"><span data-stu-id="61533-119">Application</span></span> |   <span data-ttu-id="61533-120">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="61533-120">Machine.Read.All</span></span> |  <span data-ttu-id="61533-121">"Leggi tutti i profili computer"</span><span class="sxs-lookup"><span data-stu-id="61533-121">'Read all machine profiles'</span></span>
<span data-ttu-id="61533-122">Applicazione</span><span class="sxs-lookup"><span data-stu-id="61533-122">Application</span></span> |   <span data-ttu-id="61533-123">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="61533-123">Machine.ReadWrite.All</span></span> | <span data-ttu-id="61533-124">"Leggere e scrivere tutte le informazioni sul computer"</span><span class="sxs-lookup"><span data-stu-id="61533-124">'Read and write all machine information'</span></span>
<span data-ttu-id="61533-125">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="61533-125">Delegated (work or school account)</span></span> | <span data-ttu-id="61533-126">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="61533-126">Machine.Read</span></span> | <span data-ttu-id="61533-127">"Leggere le informazioni sul computer"</span><span class="sxs-lookup"><span data-stu-id="61533-127">'Read machine information'</span></span>
<span data-ttu-id="61533-128">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="61533-128">Delegated (work or school account)</span></span> | <span data-ttu-id="61533-129">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="61533-129">Machine.ReadWrite</span></span> | <span data-ttu-id="61533-130">"Leggere e scrivere informazioni sul computer"</span><span class="sxs-lookup"><span data-stu-id="61533-130">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="61533-131">Quando si ottiene un token utilizzando le credenziali utente:</span><span class="sxs-lookup"><span data-stu-id="61533-131">When obtaining a token using user credentials:</span></span>
> - <span data-ttu-id="61533-132">La risposta includerà solo i dispositivi a cui l'utente ha accesso in base alle impostazioni del gruppo di dispositivi (per ulteriori informazioni, vedere [Creare](machine-groups.md) e gestire gruppi di dispositivi)</span><span class="sxs-lookup"><span data-stu-id="61533-132">Response will include only devices that the user have access to based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>
> - <span data-ttu-id="61533-133">L'utente deve disporre almeno dell'autorizzazione di ruolo seguente: 'Visualizza dati' (per ulteriori informazioni, vedere [Creare](user-roles.md) e gestire ruoli)</span><span class="sxs-lookup"><span data-stu-id="61533-133">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
> - <span data-ttu-id="61533-134">La risposta includerà solo i dispositivi a cui l'utente ha accesso in base alle impostazioni del gruppo di dispositivi (per ulteriori informazioni, vedere [Creare](machine-groups.md) e gestire gruppi di dispositivi)</span><span class="sxs-lookup"><span data-stu-id="61533-134">Response will include only devices that the user have access to based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="61533-135">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="61533-135">HTTP request</span></span>
```
GET /api/machines/findbyip(ip='{IP}',timestamp={TimeStamp})
```

## <a name="request-headers"></a><span data-ttu-id="61533-136">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="61533-136">Request headers</span></span>

<span data-ttu-id="61533-137">Name</span><span class="sxs-lookup"><span data-stu-id="61533-137">Name</span></span> | <span data-ttu-id="61533-138">Tipo</span><span class="sxs-lookup"><span data-stu-id="61533-138">Type</span></span> | <span data-ttu-id="61533-139">Descrizione</span><span class="sxs-lookup"><span data-stu-id="61533-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="61533-140">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="61533-140">Authorization</span></span> | <span data-ttu-id="61533-141">Stringa</span><span class="sxs-lookup"><span data-stu-id="61533-141">String</span></span> | <span data-ttu-id="61533-142">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="61533-142">Bearer {token}.</span></span> <span data-ttu-id="61533-143">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="61533-143">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="61533-144">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="61533-144">Request body</span></span>
<span data-ttu-id="61533-145">Vuoto</span><span class="sxs-lookup"><span data-stu-id="61533-145">Empty</span></span>

## <a name="response"></a><span data-ttu-id="61533-146">Risposta</span><span class="sxs-lookup"><span data-stu-id="61533-146">Response</span></span>
<span data-ttu-id="61533-147">Se ha esito positivo- 200 OK con l'elenco dei computer nel corpo della risposta.</span><span class="sxs-lookup"><span data-stu-id="61533-147">If successful - 200 OK with list of the machines in the response body.</span></span>
<span data-ttu-id="61533-148">Se il timestamp non è negli ultimi 30 giorni- 400 Richiesta non valida.</span><span class="sxs-lookup"><span data-stu-id="61533-148">If the timestamp is not in the past 30 days - 400 Bad Request.</span></span>

## <a name="example"></a><span data-ttu-id="61533-149">Esempio</span><span class="sxs-lookup"><span data-stu-id="61533-149">Example</span></span>

<span data-ttu-id="61533-150">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="61533-150">**Request**</span></span>

<span data-ttu-id="61533-151">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="61533-151">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/findbyip(ip='10.248.240.38',timestamp=2019-09-22T08:44:05Z)
```
