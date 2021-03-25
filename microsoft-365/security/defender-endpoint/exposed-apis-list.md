---
title: API di Microsoft Defender per endpoint supportate
ms.reviewer: ''
description: Informazioni sulle entità di Microsoft Defender for Endpoint supportate specifiche a cui puoi creare chiamate API.
keywords: api, api supportate, attore, avvisi, dispositivo, utente, dominio, ip, file, query avanzate, ricerca avanzata
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
ms.openlocfilehash: 77491620f7efa88f8ab249c2b76cd2532ba679dd
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198324"
---
# <a name="supported-microsoft-defender-for-endpoint-apis"></a><span data-ttu-id="4f66b-104">API di Microsoft Defender per endpoint supportate</span><span class="sxs-lookup"><span data-stu-id="4f66b-104">Supported Microsoft Defender for Endpoint APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="4f66b-105">**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="4f66b-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="4f66b-106">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="4f66b-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="4f66b-107">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="4f66b-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

## <a name="endpoint-uri-and-versioning"></a><span data-ttu-id="4f66b-108">URI endpoint e controllo delle versioni</span><span class="sxs-lookup"><span data-stu-id="4f66b-108">Endpoint URI and versioning</span></span>

### <a name="endpoint-uri"></a><span data-ttu-id="4f66b-109">URI endpoint:</span><span class="sxs-lookup"><span data-stu-id="4f66b-109">Endpoint URI:</span></span>

> <span data-ttu-id="4f66b-110">L'URI di base del servizio è: https://api.securitycenter.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="4f66b-110">The service base URI is: https://api.securitycenter.microsoft.com</span></span>
> 
> <span data-ttu-id="4f66b-111">I dati OData basati su query hanno il prefisso '/api'.</span><span class="sxs-lookup"><span data-stu-id="4f66b-111">The queries based OData have the '/api' prefix.</span></span> <span data-ttu-id="4f66b-112">Ad esempio, per ottenere avvisi è possibile inviare la richiesta GET a https://api.securitycenter.microsoft.com/api/alerts</span><span class="sxs-lookup"><span data-stu-id="4f66b-112">For example, to get Alerts you can send GET request to https://api.securitycenter.microsoft.com/api/alerts</span></span>

### <a name="versioning"></a><span data-ttu-id="4f66b-113">Controllo delle versioni:</span><span class="sxs-lookup"><span data-stu-id="4f66b-113">Versioning:</span></span>

> <span data-ttu-id="4f66b-114">L'API supporta il controllo delle versioni.</span><span class="sxs-lookup"><span data-stu-id="4f66b-114">The API supports versioning.</span></span>
> 
> <span data-ttu-id="4f66b-115">La versione corrente è **V1.0.**</span><span class="sxs-lookup"><span data-stu-id="4f66b-115">The current version is **V1.0**.</span></span>
> 
> <span data-ttu-id="4f66b-116">Per utilizzare una versione specifica, utilizzare il formato seguente: `https://api.securitycenter.microsoft.com/api/{Version}` .</span><span class="sxs-lookup"><span data-stu-id="4f66b-116">To use a specific version, use this format: `https://api.securitycenter.microsoft.com/api/{Version}`.</span></span> <span data-ttu-id="4f66b-117">Ad esempio: `https://api.securitycenter.microsoft.com/api/v1.0/alerts`</span><span class="sxs-lookup"><span data-stu-id="4f66b-117">For example: `https://api.securitycenter.microsoft.com/api/v1.0/alerts`</span></span>
> 
> <span data-ttu-id="4f66b-118">Se non si specifica alcuna versione (ad esempio ) si otterrà https://api.securitycenter.microsoft.com/api/alerts la versione più recente.</span><span class="sxs-lookup"><span data-stu-id="4f66b-118">If you don't specify any version (e.g. https://api.securitycenter.microsoft.com/api/alerts ) you will get to the latest version.</span></span>


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="4f66b-119">Altre informazioni sulle singole entità supportate in cui puoi eseguire chiamate API e dettagli come i valori delle richieste HTTP, le intestazioni delle richieste e le risposte previste.</span><span class="sxs-lookup"><span data-stu-id="4f66b-119">Learn more about the individual supported entities where you can run API calls to and details such as HTTP request values, request headers and expected responses.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="4f66b-120">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="4f66b-120">In this section</span></span>

<span data-ttu-id="4f66b-121">Argomento</span><span class="sxs-lookup"><span data-stu-id="4f66b-121">Topic</span></span> | <span data-ttu-id="4f66b-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4f66b-122">Description</span></span>
:---|:---
<span data-ttu-id="4f66b-123">Ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="4f66b-123">Advanced Hunting</span></span> | <span data-ttu-id="4f66b-124">Eseguire query dall'API.</span><span class="sxs-lookup"><span data-stu-id="4f66b-124">Run queries from API.</span></span>
<span data-ttu-id="4f66b-125">Avvisi</span><span class="sxs-lookup"><span data-stu-id="4f66b-125">Alerts</span></span> | <span data-ttu-id="4f66b-126">Esegui chiamate API come ottenere avvisi, creare avvisi, aggiornare avvisi e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="4f66b-126">Run API calls such as get alerts, create alert, update alert and more.</span></span>
<span data-ttu-id="4f66b-127">Domini</span><span class="sxs-lookup"><span data-stu-id="4f66b-127">Domains</span></span> | <span data-ttu-id="4f66b-128">Esegui chiamate API come ottenere dispositivi correlati al dominio, statistiche del dominio e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="4f66b-128">Run API calls such as get domain-related devices, domain statistics and more.</span></span>
<span data-ttu-id="4f66b-129">File</span><span class="sxs-lookup"><span data-stu-id="4f66b-129">Files</span></span> | <span data-ttu-id="4f66b-130">Esegui chiamate API come ottenere informazioni sui file, avvisi correlati ai file, dispositivi correlati ai file e statistiche sui file.</span><span class="sxs-lookup"><span data-stu-id="4f66b-130">Run API calls such as get file information, file related alerts, file related devices, and file statistics.</span></span>
<span data-ttu-id="4f66b-131">IP</span><span class="sxs-lookup"><span data-stu-id="4f66b-131">IPs</span></span> | <span data-ttu-id="4f66b-132">Eseguire chiamate API, ad esempio ottenere avvisi relativi all'IP e ottenere statistiche IP.</span><span class="sxs-lookup"><span data-stu-id="4f66b-132">Run API calls such as get IP-related alerts and get IP statistics.</span></span>
<span data-ttu-id="4f66b-133">Computer</span><span class="sxs-lookup"><span data-stu-id="4f66b-133">Machines</span></span> | <span data-ttu-id="4f66b-134">Esegui chiamate API come ottenere dispositivi, ottenere dispositivi in base all'ID, informazioni sugli utenti connessi, modificare tag e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="4f66b-134">Run API calls such as get devices, get devices by ID, information about logged on users, edit tags and more.</span></span>
<span data-ttu-id="4f66b-135">Azioni del computer</span><span class="sxs-lookup"><span data-stu-id="4f66b-135">Machine Actions</span></span> | <span data-ttu-id="4f66b-136">Esegui chiamata API come Isolamento, Esegui analisi antivirus e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="4f66b-136">Run API call such as Isolation, Run anti-virus scan and more.</span></span>
<span data-ttu-id="4f66b-137">Indicatori</span><span class="sxs-lookup"><span data-stu-id="4f66b-137">Indicators</span></span> | <span data-ttu-id="4f66b-138">Esegui una chiamata API, ad esempio crea indicatore, ottieni indicatori ed elimina indicatori.</span><span class="sxs-lookup"><span data-stu-id="4f66b-138">Run API call such as create Indicator, get Indicators and delete Indicators.</span></span>
<span data-ttu-id="4f66b-139">Utenti</span><span class="sxs-lookup"><span data-stu-id="4f66b-139">Users</span></span> | <span data-ttu-id="4f66b-140">Esegui chiamate API come ottenere avvisi correlati all'utente e dispositivi correlati all'utente.</span><span class="sxs-lookup"><span data-stu-id="4f66b-140">Run API calls such as get user-related alerts and user-related devices.</span></span>
<span data-ttu-id="4f66b-141">Punteggio</span><span class="sxs-lookup"><span data-stu-id="4f66b-141">Score</span></span> | <span data-ttu-id="4f66b-142">Esegui chiamate API come ottenere il punteggio di esposizione o ottenere il punteggio di sicurezza del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4f66b-142">Run API calls such as get exposure score or get device secure score.</span></span>
<span data-ttu-id="4f66b-143">Software</span><span class="sxs-lookup"><span data-stu-id="4f66b-143">Software</span></span> | <span data-ttu-id="4f66b-144">Esegui chiamate API, ad esempio le vulnerabilità dell'elenco da parte del software.</span><span class="sxs-lookup"><span data-stu-id="4f66b-144">Run API calls such as list vulnerabilities by software.</span></span>
<span data-ttu-id="4f66b-145">Vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="4f66b-145">Vulnerability</span></span> | <span data-ttu-id="4f66b-146">Eseguire chiamate API, ad esempio elencare i dispositivi per vulnerabilità.</span><span class="sxs-lookup"><span data-stu-id="4f66b-146">Run API calls such as list devices by vulnerability.</span></span>
<span data-ttu-id="4f66b-147">Consiglio</span><span class="sxs-lookup"><span data-stu-id="4f66b-147">Recommendation</span></span> | <span data-ttu-id="4f66b-148">Esegui chiamate API, ad esempio Ottieni suggerimenti in base all'ID.</span><span class="sxs-lookup"><span data-stu-id="4f66b-148">Run API calls such as Get recommendation by ID.</span></span>

## <a name="see-also"></a><span data-ttu-id="4f66b-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4f66b-149">See also</span></span>
- [<span data-ttu-id="4f66b-150">API di Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="4f66b-150">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)
