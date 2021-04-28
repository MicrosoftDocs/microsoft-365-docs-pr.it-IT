---
title: Accedere a API di Microsoft Defender per endpoint
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
ms.openlocfilehash: ab3d3aa9a13b71f65d3d4335646e32a7e4270242
ms.sourcegitcommit: e5b1a900043e2e41650ea1cbf4227043729c6053
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2021
ms.locfileid: "52061050"
---
# <a name="supported-microsoft-defender-for-endpoint-apis"></a><span data-ttu-id="b46c5-104">Accedere a API di Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="b46c5-104">Supported Microsoft Defender for Endpoint APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b46c5-105">**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="b46c5-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="b46c5-106">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="b46c5-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b46c5-107">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="b46c5-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="endpoint-uri-and-versioning"></a><span data-ttu-id="b46c5-108">URI endpoint e controllo delle versioni</span><span class="sxs-lookup"><span data-stu-id="b46c5-108">Endpoint URI and versioning</span></span>

### <a name="endpoint-uri"></a><span data-ttu-id="b46c5-109">Endpoint URI</span><span class="sxs-lookup"><span data-stu-id="b46c5-109">Endpoint URI</span></span>

> <span data-ttu-id="b46c5-110">L'URI di base del servizio è: [https://api.securitycenter.microsoft.com](https://api.securitycenter.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="b46c5-110">The service base URI is: [https://api.securitycenter.microsoft.com](https://api.securitycenter.microsoft.com)</span></span>
>
> <span data-ttu-id="b46c5-111">I dati OData basati su query hanno il prefisso '/api'.</span><span class="sxs-lookup"><span data-stu-id="b46c5-111">The queries based OData have the '/api' prefix.</span></span> <span data-ttu-id="b46c5-112">Ad esempio, per ottenere avvisi è possibile inviare la richiesta GET a [https://api.securitycenter.microsoft.com/api/alerts](https://api.securitycenter.microsoft.com/api/alerts)</span><span class="sxs-lookup"><span data-stu-id="b46c5-112">For example, to get Alerts you can send GET request to [https://api.securitycenter.microsoft.com/api/alerts](https://api.securitycenter.microsoft.com/api/alerts)</span></span>

### <a name="versioning"></a><span data-ttu-id="b46c5-113">Controllo delle versioni</span><span class="sxs-lookup"><span data-stu-id="b46c5-113">Versioning</span></span>

> <span data-ttu-id="b46c5-114">L'API supporta il controllo delle versioni.</span><span class="sxs-lookup"><span data-stu-id="b46c5-114">The API supports versioning.</span></span>
>
> <span data-ttu-id="b46c5-115">La versione corrente è **V1.0.**</span><span class="sxs-lookup"><span data-stu-id="b46c5-115">The current version is **V1.0**.</span></span>
>
> <span data-ttu-id="b46c5-116">Per utilizzare una versione specifica, utilizzare il formato seguente: `https://api.securitycenter.microsoft.com/api/{Version}` .</span><span class="sxs-lookup"><span data-stu-id="b46c5-116">To use a specific version, use this format: `https://api.securitycenter.microsoft.com/api/{Version}`.</span></span> <span data-ttu-id="b46c5-117">Ad esempio: `https://api.securitycenter.microsoft.com/api/v1.0/alerts`</span><span class="sxs-lookup"><span data-stu-id="b46c5-117">For example: `https://api.securitycenter.microsoft.com/api/v1.0/alerts`</span></span>
>
> <span data-ttu-id="b46c5-118">Se non si specifica alcuna versione (ad esempio ) si otterrà `https://api.securitycenter.microsoft.com/api/alerts` la versione più recente.</span><span class="sxs-lookup"><span data-stu-id="b46c5-118">If you don't specify any version (e.g. `https://api.securitycenter.microsoft.com/api/alerts` ) you will get to the latest version.</span></span>

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="b46c5-119">Altre informazioni sulle singole entità supportate in cui puoi eseguire chiamate API e dettagli come i valori delle richieste HTTP, le intestazioni delle richieste e le risposte previste.</span><span class="sxs-lookup"><span data-stu-id="b46c5-119">Learn more about the individual supported entities where you can run API calls to and details such as HTTP request values, request headers and expected responses.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="b46c5-120">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="b46c5-120">In this section</span></span>

<span data-ttu-id="b46c5-121">Argomento</span><span class="sxs-lookup"><span data-stu-id="b46c5-121">Topic</span></span> | <span data-ttu-id="b46c5-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b46c5-122">Description</span></span>
:---|:---
[<span data-ttu-id="b46c5-123">Rilevazione avanzata</span><span class="sxs-lookup"><span data-stu-id="b46c5-123">Advanced Hunting</span></span>](run-advanced-query-api.md) | <span data-ttu-id="b46c5-124">Eseguire query dall'API.</span><span class="sxs-lookup"><span data-stu-id="b46c5-124">Run queries from API.</span></span>
[<span data-ttu-id="b46c5-125">Metodi e proprietà di avviso</span><span class="sxs-lookup"><span data-stu-id="b46c5-125">Alert methods and properties</span></span>](alerts.md) | <span data-ttu-id="b46c5-126">Esegui chiamate API come \- ottenere avvisi, creare avvisi, aggiornare avvisi e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="b46c5-126">Run API calls such as \- get alerts, create alert, update alert and more.</span></span>
[<span data-ttu-id="b46c5-127">Metodi e proprietà dell'indagine automatizzata</span><span class="sxs-lookup"><span data-stu-id="b46c5-127">Automated Investigation methods and properties</span></span>](investigation.md) | <span data-ttu-id="b46c5-128">Esegui chiamate API, ad \- esempio ottieni raccolta di indagini.</span><span class="sxs-lookup"><span data-stu-id="b46c5-128">Run API calls such as \- get collection of Investigation.</span></span>
[<span data-ttu-id="b46c5-129">Ottenere avvisi correlati al dominio</span><span class="sxs-lookup"><span data-stu-id="b46c5-129">Get domain related alerts</span></span>](get-domain-related-alerts.md) | <span data-ttu-id="b46c5-130">Esegui chiamate API come \- ottenere dispositivi correlati al dominio, statistiche del dominio e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="b46c5-130">Run API calls such as \- get domain-related devices, domain statistics and more.</span></span>
[<span data-ttu-id="b46c5-131">Metodi e proprietà di file</span><span class="sxs-lookup"><span data-stu-id="b46c5-131">File methods and properties</span></span>](files.md) | <span data-ttu-id="b46c5-132">Esegui chiamate API come ottenere informazioni sui file, avvisi correlati ai file, dispositivi correlati \- ai file e statistiche sui file.</span><span class="sxs-lookup"><span data-stu-id="b46c5-132">Run API calls such as \- get file information, file related alerts, file related devices, and file statistics.</span></span>
[<span data-ttu-id="b46c5-133">Metodi e proprietà degli indicatori</span><span class="sxs-lookup"><span data-stu-id="b46c5-133">Indicators methods and properties</span></span>](ti-indicator.md) | <span data-ttu-id="b46c5-134">Eseguire una chiamata API, ad \- esempio ottenere indicatori, creare indicatori ed eliminare indicatori.</span><span class="sxs-lookup"><span data-stu-id="b46c5-134">Run API call such as \- get Indicators, create Indicator, and delete Indicators.</span></span>
[<span data-ttu-id="b46c5-135">Ottenere avvisi correlati agli IP</span><span class="sxs-lookup"><span data-stu-id="b46c5-135">Get IP related alerts</span></span>](get-ip-related-alerts.md) | <span data-ttu-id="b46c5-136">Eseguire chiamate API, ad esempio \- ottenere avvisi relativi all'IP e ottenere statistiche IP.</span><span class="sxs-lookup"><span data-stu-id="b46c5-136">Run API calls such as \- get IP-related alerts and get IP statistics.</span></span>
[<span data-ttu-id="b46c5-137">Metodi e proprietà dei computer</span><span class="sxs-lookup"><span data-stu-id="b46c5-137">Machine methods and properties</span></span>](machine.md) | <span data-ttu-id="b46c5-138">Esegui chiamate API come ottenere dispositivi, ottenere dispositivi in base all'ID, informazioni sugli utenti \- connessi, modificare tag e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="b46c5-138">Run API calls such as \- get devices, get devices by ID, information about logged on users, edit tags and more.</span></span>
[<span data-ttu-id="b46c5-139">Metodi e proprietà di azioni dei computer</span><span class="sxs-lookup"><span data-stu-id="b46c5-139">Machine Action methods and properties</span></span>](machineaction.md) | <span data-ttu-id="b46c5-140">Esegui chiamata API come \- Isolamento, Esegui analisi antivirus e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="b46c5-140">Run API call such as \- Isolation, Run anti-virus scan and more.</span></span>
[<span data-ttu-id="b46c5-141">Metodi e proprietà di consiglio</span><span class="sxs-lookup"><span data-stu-id="b46c5-141">Recommendation methods and properties</span></span>](recommendation.md) | <span data-ttu-id="b46c5-142">Eseguire chiamate API, ad esempio \- ottenere consigli in base all'ID.</span><span class="sxs-lookup"><span data-stu-id="b46c5-142">Run API calls such as \- get recommendation by ID.</span></span>
[<span data-ttu-id="b46c5-143">Metodi e proprietà dell'attività di correzione</span><span class="sxs-lookup"><span data-stu-id="b46c5-143">Remediation activity methods and properties</span></span>](get-remediation-methods-properties.md) | <span data-ttu-id="b46c5-144">Eseguire una chiamata API, ad esempio ottenere tutte le attività di correzione, ottenere l'attività di correzione dei dispositivi esposti e ottenere un'attività di correzione \- in base all'ID.</span><span class="sxs-lookup"><span data-stu-id="b46c5-144">Run API call such as \- get all remediation tasks, get exposed devices remediation task and get one remediation task by id.</span></span>
[<span data-ttu-id="b46c5-145">Metodi e proprietà di punteggio</span><span class="sxs-lookup"><span data-stu-id="b46c5-145">Score methods and properties</span></span>](score.md) | <span data-ttu-id="b46c5-146">Esegui chiamate API come \- ottenere il punteggio di esposizione o ottenere il punteggio di sicurezza del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b46c5-146">Run API calls such as \- get exposure score or get device secure score.</span></span>
[<span data-ttu-id="b46c5-147">Metodi e proprietà di software</span><span class="sxs-lookup"><span data-stu-id="b46c5-147">Software methods and properties</span></span>](software.md) | <span data-ttu-id="b46c5-148">Esegui chiamate API, ad esempio \- le vulnerabilità dell'elenco da parte del software.</span><span class="sxs-lookup"><span data-stu-id="b46c5-148">Run API calls such as \- list vulnerabilities by software.</span></span>
[<span data-ttu-id="b46c5-149">Metodi utente</span><span class="sxs-lookup"><span data-stu-id="b46c5-149">User methods</span></span>](user.md) | <span data-ttu-id="b46c5-150">Esegui chiamate API come \- ottenere avvisi correlati all'utente e dispositivi correlati all'utente.</span><span class="sxs-lookup"><span data-stu-id="b46c5-150">Run API calls such as \- get user-related alerts and user-related devices.</span></span>
[<span data-ttu-id="b46c5-151">Metodi e proprietà di vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="b46c5-151">Vulnerability methods and properties</span></span>](vulnerability.md) | <span data-ttu-id="b46c5-152">Eseguire chiamate API, ad esempio \- elencare i dispositivi per vulnerabilità.</span><span class="sxs-lookup"><span data-stu-id="b46c5-152">Run API calls such as \- list devices by vulnerability.</span></span>

## <a name="see-also"></a><span data-ttu-id="b46c5-153">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b46c5-153">See also</span></span>

- [<span data-ttu-id="b46c5-154">API di Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="b46c5-154">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)

- [<span data-ttu-id="b46c5-155">Note sulla versione di Microsoft Defender for Endpoint API</span><span class="sxs-lookup"><span data-stu-id="b46c5-155">Microsoft Defender for Endpoint API release notes</span></span>](api-release-notes.md)
