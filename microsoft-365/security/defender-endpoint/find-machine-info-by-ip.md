---
title: Trovare informazioni sul dispositivo per API IP interna
description: Usa questa API per creare chiamate correlate alla ricerca di una voce del dispositivo intorno a un timestamp specifico tramite IP interno.
keywords: ip, api, api del grafico, api supportate, trovare il dispositivo, informazioni sul dispositivo
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
ms.openlocfilehash: fa1973d1c53048b04c9135a72e55ec4759412b18
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167141"
---
# <a name="find-device-information-by-internal-ip-api"></a><span data-ttu-id="84427-104">Trovare informazioni sul dispositivo per API IP interna</span><span class="sxs-lookup"><span data-stu-id="84427-104">Find device information by internal IP API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="84427-105">**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="84427-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span></span>

- <span data-ttu-id="84427-106">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="84427-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="84427-107">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="84427-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="84427-108">Trovare un dispositivo in base all'IP interno.</span><span class="sxs-lookup"><span data-stu-id="84427-108">Find a device by internal IP.</span></span>

>[!NOTE]
><span data-ttu-id="84427-109">Il timestamp deve essere compreso negli ultimi 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="84427-109">The timestamp must be within the last 30 days.</span></span>

## <a name="permissions"></a><span data-ttu-id="84427-110">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="84427-110">Permissions</span></span>
<span data-ttu-id="84427-111">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="84427-111">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="84427-112">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi [Usare Microsoft Defender per le API endpoint](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="84427-112">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="84427-113">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="84427-113">Permission type</span></span> | <span data-ttu-id="84427-114">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="84427-114">Permission</span></span> | <span data-ttu-id="84427-115">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="84427-115">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="84427-116">Applicazione</span><span class="sxs-lookup"><span data-stu-id="84427-116">Application</span></span> | <span data-ttu-id="84427-117">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="84427-117">Machine.Read.All</span></span> | <span data-ttu-id="84427-118">"Leggi tutti i profili computer"</span><span class="sxs-lookup"><span data-stu-id="84427-118">'Read all machine profiles'</span></span>
<span data-ttu-id="84427-119">Applicazione</span><span class="sxs-lookup"><span data-stu-id="84427-119">Application</span></span> | <span data-ttu-id="84427-120">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="84427-120">Machine.ReadWrite.All</span></span> | <span data-ttu-id="84427-121">"Leggere e scrivere tutte le informazioni sul computer"</span><span class="sxs-lookup"><span data-stu-id="84427-121">'Read and write all machine information'</span></span>

## <a name="http-request"></a><span data-ttu-id="84427-122">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="84427-122">HTTP request</span></span>
```
GET /api/machines/find(timestamp={time},key={IP})
```

## <a name="request-headers"></a><span data-ttu-id="84427-123">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="84427-123">Request headers</span></span>

<span data-ttu-id="84427-124">Name</span><span class="sxs-lookup"><span data-stu-id="84427-124">Name</span></span> | <span data-ttu-id="84427-125">Tipo</span><span class="sxs-lookup"><span data-stu-id="84427-125">Type</span></span> | <span data-ttu-id="84427-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="84427-126">Description</span></span>
:---|:---|:---
<span data-ttu-id="84427-127">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="84427-127">Authorization</span></span> | <span data-ttu-id="84427-128">Stringa</span><span class="sxs-lookup"><span data-stu-id="84427-128">String</span></span> | <span data-ttu-id="84427-129">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="84427-129">Bearer {token}.</span></span> <span data-ttu-id="84427-130">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="84427-130">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="84427-131">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="84427-131">Request body</span></span>
<span data-ttu-id="84427-132">Vuoto</span><span class="sxs-lookup"><span data-stu-id="84427-132">Empty</span></span>

## <a name="response"></a><span data-ttu-id="84427-133">Risposta</span><span class="sxs-lookup"><span data-stu-id="84427-133">Response</span></span>
<span data-ttu-id="84427-134">Se ha esito positivo e il computer esiste - 200 OK.</span><span class="sxs-lookup"><span data-stu-id="84427-134">If successful and machine exists - 200 OK.</span></span>
<span data-ttu-id="84427-135">Se nessun computer trovato - 404 Non trovato.</span><span class="sxs-lookup"><span data-stu-id="84427-135">If no machine found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="84427-136">Esempio</span><span class="sxs-lookup"><span data-stu-id="84427-136">Example</span></span>

<span data-ttu-id="84427-137">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="84427-137">**Request**</span></span>

<span data-ttu-id="84427-138">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="84427-138">Here is an example of the request.</span></span>

```
GET https://graph.microsoft.com/testwdatppreview/machines/find(timestamp=2018-06-19T10:00:00Z,key='10.166.93.61')
Content-type: application/json
```

<span data-ttu-id="84427-139">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="84427-139">**Response**</span></span>

<span data-ttu-id="84427-140">Ecco un esempio di risposta.</span><span class="sxs-lookup"><span data-stu-id="84427-140">Here is an example of the response.</span></span>

<span data-ttu-id="84427-141">La risposta restituirà un elenco di tutti i dispositivi che hanno segnalato questo indirizzo IP entro 16 minuti prima e dopo il timestamp.</span><span class="sxs-lookup"><span data-stu-id="84427-141">The response will return a list of all devices that reported this IP address within sixteen minutes prior and after the timestamp.</span></span> 

```
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://graph.microsoft.com/testwdatppreview/$metadata#Machines",
    "value": [
        {
            "id": "04c99d46599f078f1c3da3783cf5b95f01ac61bb",
            "computerDnsName": "",
            "firstSeen": "2017-07-06T01:25:04.9480498Z",
            "osPlatform": "Windows10",
…
}
```
