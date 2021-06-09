---
title: Ottenere l'API URI di firma di accesso condiviso del pacchetto
description: Usa questa API per ottenere un URI che consente il download di un pacchetto di analisi.
keywords: api, api del grafico, api supportate, ottenere pacchetto, sas, uri
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 054db1766cdab3aa5b49da4940dcdddfe6086434
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770686"
---
# <a name="get-package-sas-uri-api"></a><span data-ttu-id="5d43d-104">Ottenere l'API URI di firma di accesso condiviso del pacchetto</span><span class="sxs-lookup"><span data-stu-id="5d43d-104">Get package SAS URI API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5d43d-105">**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="5d43d-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="5d43d-106">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="5d43d-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5d43d-107">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="5d43d-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="5d43d-108">Descrizione API</span><span class="sxs-lookup"><span data-stu-id="5d43d-108">API description</span></span>
<span data-ttu-id="5d43d-109">Ottieni un URI che consente il download di un [pacchetto di analisi.](collect-investigation-package.md)</span><span class="sxs-lookup"><span data-stu-id="5d43d-109">Get a URI that allows downloading of an [Investigation package](collect-investigation-package.md).</span></span>


## <a name="permissions"></a><span data-ttu-id="5d43d-110">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="5d43d-110">Permissions</span></span>
<span data-ttu-id="5d43d-111">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="5d43d-111">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="5d43d-112">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi [Accedere alle API di Microsoft Defender per endpoint](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="5d43d-112">To learn more, including how to choose permissions, see [Access the Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="5d43d-113">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="5d43d-113">Permission type</span></span> |   <span data-ttu-id="5d43d-114">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="5d43d-114">Permission</span></span>  |   <span data-ttu-id="5d43d-115">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="5d43d-115">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="5d43d-116">Applicazione</span><span class="sxs-lookup"><span data-stu-id="5d43d-116">Application</span></span> |   <span data-ttu-id="5d43d-117">Machine.CollectForensics</span><span class="sxs-lookup"><span data-stu-id="5d43d-117">Machine.CollectForensics</span></span> |  <span data-ttu-id="5d43d-118">"Raccogliere dati forensi"</span><span class="sxs-lookup"><span data-stu-id="5d43d-118">'Collect forensics'</span></span>
<span data-ttu-id="5d43d-119">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="5d43d-119">Delegated (work or school account)</span></span> | <span data-ttu-id="5d43d-120">Machine.CollectForensics</span><span class="sxs-lookup"><span data-stu-id="5d43d-120">Machine.CollectForensics</span></span> | <span data-ttu-id="5d43d-121">"Raccogliere dati forensi"</span><span class="sxs-lookup"><span data-stu-id="5d43d-121">'Collect forensics'</span></span>

>[!Note]
> <span data-ttu-id="5d43d-122">Quando si ottiene un token utilizzando le credenziali utente:</span><span class="sxs-lookup"><span data-stu-id="5d43d-122">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="5d43d-123">L'utente deve disporre almeno dell'autorizzazione di ruolo seguente: 'Alerts Investigation' (Per ulteriori informazioni, vedere [Create and manage roles)](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="5d43d-123">The user needs to have at least the following role permission: 'Alerts Investigation' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="5d43d-124">L'utente deve avere accesso al dispositivo in base alle impostazioni del gruppo di dispositivi (per ulteriori informazioni, vedere [Creare](machine-groups.md) e gestire gruppi di dispositivi)</span><span class="sxs-lookup"><span data-stu-id="5d43d-124">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="5d43d-125">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="5d43d-125">HTTP request</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machineactions/{machine action id}/getPackageUri
```

## <a name="request-headers"></a><span data-ttu-id="5d43d-126">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="5d43d-126">Request headers</span></span>

<span data-ttu-id="5d43d-127">Name</span><span class="sxs-lookup"><span data-stu-id="5d43d-127">Name</span></span> | <span data-ttu-id="5d43d-128">Tipo</span><span class="sxs-lookup"><span data-stu-id="5d43d-128">Type</span></span> | <span data-ttu-id="5d43d-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5d43d-129">Description</span></span>
:---|:---|:---
<span data-ttu-id="5d43d-130">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="5d43d-130">Authorization</span></span> | <span data-ttu-id="5d43d-131">Stringa</span><span class="sxs-lookup"><span data-stu-id="5d43d-131">String</span></span> | <span data-ttu-id="5d43d-132">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="5d43d-132">Bearer {token}.</span></span> <span data-ttu-id="5d43d-133">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="5d43d-133">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="5d43d-134">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="5d43d-134">Request body</span></span>

<span data-ttu-id="5d43d-135">Vuoto</span><span class="sxs-lookup"><span data-stu-id="5d43d-135">Empty</span></span>

## <a name="response"></a><span data-ttu-id="5d43d-136">Risposta</span><span class="sxs-lookup"><span data-stu-id="5d43d-136">Response</span></span>

<span data-ttu-id="5d43d-137">Se ha esito positivo, questo metodo restituisce il codice di risposta 200 Ok con l'oggetto che contiene il collegamento al pacchetto nel parametro "value".</span><span class="sxs-lookup"><span data-stu-id="5d43d-137">If successful, this method returns 200, Ok response code with object that holds the link to the package in the “value” parameter.</span></span> <span data-ttu-id="5d43d-138">Questo collegamento è valido per un periodo di tempo molto breve e deve essere usato immediatamente per scaricare il pacchetto in un archivio locale.</span><span class="sxs-lookup"><span data-stu-id="5d43d-138">This link is valid for a very short time and should be used immediately for downloading the package to a local storage.</span></span>


## <a name="example"></a><span data-ttu-id="5d43d-139">Esempio</span><span class="sxs-lookup"><span data-stu-id="5d43d-139">Example</span></span>

<span data-ttu-id="5d43d-140">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="5d43d-140">**Request**</span></span>

<span data-ttu-id="5d43d-141">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="5d43d-141">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machineactions/7327b54fd718525cbca07dacde913b5ac3c85673/GetPackageUri

```

<span data-ttu-id="5d43d-142">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="5d43d-142">**Response**</span></span>

<span data-ttu-id="5d43d-143">Ecco un esempio di risposta.</span><span class="sxs-lookup"><span data-stu-id="5d43d-143">Here is an example of the response.</span></span>

```http
HTTP/1.1 200 Ok
Content-type: application/json

{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Edm.String",
    "value": "\"https://userrequests-us.securitycenter.windows.com:443/safedownload/WDATP_Investigation_Package.zip?token=gbDyj7y%2fbWGAZjn2sFiZXlliBTXOCVG7yiJ6mXNaQ9pLByC2Wxeno9mENsPFP3xMk5l%2bZiJXjLvqAyNEzUNROxoM2I1er9dxzfVeBsxSmclJjPsAx%2btiNyxSz1Ax%2b5jaT5cL5bZg%2b8wgbwY9urXbTpGjAKh6FB1e%2b0ypcWkPm8UkfOwsmtC%2biZJ2%2bPqnkkeQk7SKMNoAvmh9%2fcqDIPKXGIBjMa0D9auzypOqd8bQXp7p2BnLSH136BxST8n9IHR4PILvRjAYW9kvtHkBpBitfydAsUW4g2oDZSPN3kCLBOoo1C4w4Lkc9Bc3GNU2IW6dfB7SHcp7G9p4BDkeJl3VuDs6esCaeBorpn9FKJ%2fXo7o9pdcI0hUPZ6Ds9hiPpwPUtz5J29CBE3QAopCK%2fsWlf6OW2WyXsrNRSnF1tVE5H3wXpREzuhD7S4AIA3OIEZKzC4jIPLeMu%2bazZU9xGwuc3gICOaokbwMJiZTqcUuK%2fV9YdBdjdg8wJ16NDU96Pl6%2fgew2KYuk6Wo7ZuHotgHI1abcsvdlpe4AvixDbqcRJthsg2PpLRaFLm5av44UGkeK6TJpFvxUn%2f9fg6Zk5yM1KUTHb8XGmutoCM8U9er6AzXZlY0gGc3D3bQOg41EJZkEZLyUEbk1hXJB36ku2%2bW01cG71t7MxMBYz7%2bdXobxpdo%3d%3bRWS%2bCeoDfTyDcfH5pkCg6hYDmCOPr%2fHYQuaUWUBNVnXURYkdyOzVHqp%2fe%2f1BNyPdVoVkpQHpz1pPS3b5g9h7IMmNKCk5gFq5m2nPx6kk9EYtzx8Ndoa2m9Yj%2bSaf8zIFke86YnfQL4AYewsnQNJJh4wc%2bXxGlBq7axDcoiOdX91rKzVicH3GSBkFoLFAKoegWWsF%2fEDZcVpF%2fXUA1K8HvB6dwyfy4y0sAqnNPxYTQ97mG7yHhxPt4Pe9YF2UPPAJVuEf8LNlQ%2bWHC9%2f7msF6UUI4%2fca%2ftpjFs%2fSNeRE8%2fyQj21TI8YTF1SowvaJuDc1ivEoeopNNGG%2bGI%2fX0SckaVxU9Hdkh0zbydSlT5SZwbSwescs0IpzECitBbaLUz4aT8KTs8T0lvx8D7Te3wVsKAJ1r3iFMQZrlk%2bS1WW8rvac7oHRx2HKURn1v7fDIQWgJr9aNsNlFz4fLJ50T2qSHuuepkLVbe93Va072aMGhvr09WVKoTpAf1j2bcFZZU6Za5PxI32mr0k90FgiYFJ1F%2f1vRDrGwvWVWUkR3Z33m4g0gHa52W1FMxQY0TJIwbovD6FaSNDx7xhKZSd5IJ7r6P91Gez49PaZRcAZPjd%2bfbul3JNm1VqQPTLohT7wa0ymRiXpSST74xtFzuEBzNSNATdbngj3%2fwV4JesTjZjIj5Dc%3d%3blumqauVlFuuO8MQffZgs0tLJ4Fq6fpeozPTdDf8Ll6XLegi079%2b4mSPFjTK0y6eohstxdoOdom2wAHiZwk0u4KLKmRkfYOdT1wHY79qKoBQ3ZDHFTys9V%2fcwKGl%2bl8IenWDutHygn5IcA1y7GTZj4g%3d%3d\""
}
```
