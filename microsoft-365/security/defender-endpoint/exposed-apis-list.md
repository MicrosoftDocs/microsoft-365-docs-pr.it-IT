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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 63e38d5c9cfe50d1fa4cda1f7ae9c7df55a45083
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2021
ms.locfileid: "52788836"
---
# <a name="supported-microsoft-defender-for-endpoint-apis"></a><span data-ttu-id="5526c-104">Accedere a API di Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="5526c-104">Supported Microsoft Defender for Endpoint APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5526c-105">**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="5526c-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="5526c-106">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="5526c-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5526c-107">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="5526c-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="endpoint-uri-and-versioning"></a><span data-ttu-id="5526c-108">URI endpoint e controllo delle versioni</span><span class="sxs-lookup"><span data-stu-id="5526c-108">Endpoint URI and versioning</span></span>

### <a name="endpoint-uri"></a><span data-ttu-id="5526c-109">Endpoint URI</span><span class="sxs-lookup"><span data-stu-id="5526c-109">Endpoint URI</span></span>

> <span data-ttu-id="5526c-110">L'URI di base del servizio è: [https://api.securitycenter.microsoft.com](https://api.securitycenter.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="5526c-110">The service base URI is: [https://api.securitycenter.microsoft.com](https://api.securitycenter.microsoft.com)</span></span>
>
> <span data-ttu-id="5526c-111">I dati OData basati su query hanno il prefisso '/api'.</span><span class="sxs-lookup"><span data-stu-id="5526c-111">The queries based OData have the '/api' prefix.</span></span> <span data-ttu-id="5526c-112">Ad esempio, per ottenere avvisi è possibile inviare la richiesta GET a [https://api.securitycenter.microsoft.com/api/alerts](https://api.securitycenter.microsoft.com/api/alerts)</span><span class="sxs-lookup"><span data-stu-id="5526c-112">For example, to get Alerts you can send GET request to [https://api.securitycenter.microsoft.com/api/alerts](https://api.securitycenter.microsoft.com/api/alerts)</span></span>

### <a name="versioning"></a><span data-ttu-id="5526c-113">Controllo delle versioni</span><span class="sxs-lookup"><span data-stu-id="5526c-113">Versioning</span></span>

> <span data-ttu-id="5526c-114">L'API supporta il controllo delle versioni.</span><span class="sxs-lookup"><span data-stu-id="5526c-114">The API supports versioning.</span></span>
>
> <span data-ttu-id="5526c-115">La versione corrente è **V1.0.**</span><span class="sxs-lookup"><span data-stu-id="5526c-115">The current version is **V1.0**.</span></span>
>
> <span data-ttu-id="5526c-116">Per utilizzare una versione specifica, utilizzare il formato seguente: `https://api.securitycenter.microsoft.com/api/{Version}` .</span><span class="sxs-lookup"><span data-stu-id="5526c-116">To use a specific version, use this format: `https://api.securitycenter.microsoft.com/api/{Version}`.</span></span> <span data-ttu-id="5526c-117">Ad esempio: `https://api.securitycenter.microsoft.com/api/v1.0/alerts`</span><span class="sxs-lookup"><span data-stu-id="5526c-117">For example: `https://api.securitycenter.microsoft.com/api/v1.0/alerts`</span></span>
>
> <span data-ttu-id="5526c-118">Se non si specifica alcuna versione (ad esempio ) si otterrà `https://api.securitycenter.microsoft.com/api/alerts` la versione più recente.</span><span class="sxs-lookup"><span data-stu-id="5526c-118">If you don't specify any version (e.g. `https://api.securitycenter.microsoft.com/api/alerts` ) you will get to the latest version.</span></span>

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="5526c-119">Altre informazioni sulle singole entità supportate in cui puoi eseguire chiamate API e dettagli come i valori delle richieste HTTP, le intestazioni delle richieste e le risposte previste.</span><span class="sxs-lookup"><span data-stu-id="5526c-119">Learn more about the individual supported entities where you can run API calls to and details such as HTTP request values, request headers and expected responses.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="5526c-120">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="5526c-120">In this section</span></span>

<span data-ttu-id="5526c-121">Argomento</span><span class="sxs-lookup"><span data-stu-id="5526c-121">Topic</span></span> | <span data-ttu-id="5526c-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5526c-122">Description</span></span>
:---|:---
[<span data-ttu-id="5526c-123">Rilevazione avanzata</span><span class="sxs-lookup"><span data-stu-id="5526c-123">Advanced Hunting</span></span>](run-advanced-query-api.md) | <span data-ttu-id="5526c-124">Eseguire query dall'API.</span><span class="sxs-lookup"><span data-stu-id="5526c-124">Run queries from API.</span></span>
[<span data-ttu-id="5526c-125">Metodi e proprietà di avviso</span><span class="sxs-lookup"><span data-stu-id="5526c-125">Alert methods and properties</span></span>](alerts.md) | <span data-ttu-id="5526c-126">Esegui chiamate API come \- ottenere avvisi, creare avvisi, aggiornare avvisi e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="5526c-126">Run API calls such as \- get alerts, create alert, update alert and more.</span></span>
[<span data-ttu-id="5526c-127">Esportare proprietà e metodi di valutazione per dispositivo</span><span class="sxs-lookup"><span data-stu-id="5526c-127">Export assessment methods and properties per device</span></span>](get-assessment-methods-properties.md) | <span data-ttu-id="5526c-128">Eseguire chiamate API come esportare la valutazione della configurazione sicura, esportare la valutazione dell'inventario \- software ed esportare la valutazione delle vulnerabilità del software.</span><span class="sxs-lookup"><span data-stu-id="5526c-128">Run API calls such as \- export secure configuration assessment, export software inventory assessment,  and export software vulnerabilities assessment.</span></span>
[<span data-ttu-id="5526c-129">Metodi e proprietà dell'indagine automatizzata</span><span class="sxs-lookup"><span data-stu-id="5526c-129">Automated Investigation methods and properties</span></span>](investigation.md) | <span data-ttu-id="5526c-130">Esegui chiamate API, ad \- esempio ottieni raccolta di indagini.</span><span class="sxs-lookup"><span data-stu-id="5526c-130">Run API calls such as \- get collection of Investigation.</span></span>
[<span data-ttu-id="5526c-131">Ottenere avvisi correlati al dominio</span><span class="sxs-lookup"><span data-stu-id="5526c-131">Get domain related alerts</span></span>](get-domain-related-alerts.md) | <span data-ttu-id="5526c-132">Esegui chiamate API come \- ottenere dispositivi correlati al dominio, statistiche del dominio e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="5526c-132">Run API calls such as \- get domain-related devices, domain statistics and more.</span></span>
[<span data-ttu-id="5526c-133">Metodi e proprietà di file</span><span class="sxs-lookup"><span data-stu-id="5526c-133">File methods and properties</span></span>](files.md) | <span data-ttu-id="5526c-134">Esegui chiamate API come ottenere informazioni sui file, avvisi correlati ai file, dispositivi correlati \- ai file e statistiche sui file.</span><span class="sxs-lookup"><span data-stu-id="5526c-134">Run API calls such as \- get file information, file related alerts, file related devices, and file statistics.</span></span>
[<span data-ttu-id="5526c-135">Metodi e proprietà degli indicatori</span><span class="sxs-lookup"><span data-stu-id="5526c-135">Indicators methods and properties</span></span>](ti-indicator.md) | <span data-ttu-id="5526c-136">Eseguire una chiamata API, ad \- esempio ottenere indicatori, creare indicatori ed eliminare indicatori.</span><span class="sxs-lookup"><span data-stu-id="5526c-136">Run API call such as \- get Indicators, create Indicator, and delete Indicators.</span></span>
[<span data-ttu-id="5526c-137">Ottenere avvisi correlati agli IP</span><span class="sxs-lookup"><span data-stu-id="5526c-137">Get IP related alerts</span></span>](get-ip-related-alerts.md) | <span data-ttu-id="5526c-138">Eseguire chiamate API, ad esempio \- ottenere avvisi relativi all'IP e ottenere statistiche IP.</span><span class="sxs-lookup"><span data-stu-id="5526c-138">Run API calls such as \- get IP-related alerts and get IP statistics.</span></span>
[<span data-ttu-id="5526c-139">Metodi e proprietà dei computer</span><span class="sxs-lookup"><span data-stu-id="5526c-139">Machine methods and properties</span></span>](machine.md) | <span data-ttu-id="5526c-140">Esegui chiamate API come ottenere dispositivi, ottenere dispositivi in base all'ID, informazioni sugli utenti \- connessi, modificare tag e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="5526c-140">Run API calls such as \- get devices, get devices by ID, information about logged on users, edit tags and more.</span></span>
[<span data-ttu-id="5526c-141">Metodi e proprietà di azioni dei computer</span><span class="sxs-lookup"><span data-stu-id="5526c-141">Machine Action methods and properties</span></span>](machineaction.md) | <span data-ttu-id="5526c-142">Esegui chiamata API come \- Isolamento, Esegui analisi antivirus e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="5526c-142">Run API call such as \- Isolation, Run anti-virus scan and more.</span></span>
[<span data-ttu-id="5526c-143">Metodi e proprietà di consiglio</span><span class="sxs-lookup"><span data-stu-id="5526c-143">Recommendation methods and properties</span></span>](recommendation.md) | <span data-ttu-id="5526c-144">Eseguire chiamate API, ad esempio \- ottenere consigli in base all'ID.</span><span class="sxs-lookup"><span data-stu-id="5526c-144">Run API calls such as \- get recommendation by ID.</span></span>
[<span data-ttu-id="5526c-145">Metodi e proprietà delle attività correttive</span><span class="sxs-lookup"><span data-stu-id="5526c-145">Remediation activity methods and properties</span></span>](get-remediation-methods-properties.md) | <span data-ttu-id="5526c-146">Eseguire una chiamata API, ad esempio ottenere tutte le attività di correzione, ottenere l'attività di correzione dei dispositivi esposti e ottenere un'attività di correzione \- in base all'ID.</span><span class="sxs-lookup"><span data-stu-id="5526c-146">Run API call such as \- get all remediation tasks, get exposed devices remediation task and get one remediation task by id.</span></span>
[<span data-ttu-id="5526c-147">Metodi e proprietà di punteggio</span><span class="sxs-lookup"><span data-stu-id="5526c-147">Score methods and properties</span></span>](score.md) | <span data-ttu-id="5526c-148">Esegui chiamate API come \- ottenere il punteggio di esposizione o ottenere il punteggio di sicurezza del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5526c-148">Run API calls such as \- get exposure score or get device secure score.</span></span>
[<span data-ttu-id="5526c-149">Metodi e proprietà di software</span><span class="sxs-lookup"><span data-stu-id="5526c-149">Software methods and properties</span></span>](software.md) | <span data-ttu-id="5526c-150">Esegui chiamate API, ad esempio \- le vulnerabilità dell'elenco da parte del software.</span><span class="sxs-lookup"><span data-stu-id="5526c-150">Run API calls such as \- list vulnerabilities by software.</span></span>
[<span data-ttu-id="5526c-151">Metodi utente</span><span class="sxs-lookup"><span data-stu-id="5526c-151">User methods</span></span>](user.md) | <span data-ttu-id="5526c-152">Esegui chiamate API come \- ottenere avvisi correlati all'utente e dispositivi correlati all'utente.</span><span class="sxs-lookup"><span data-stu-id="5526c-152">Run API calls such as \- get user-related alerts and user-related devices.</span></span>
[<span data-ttu-id="5526c-153">Metodi e proprietà di vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="5526c-153">Vulnerability methods and properties</span></span>](vulnerability.md) | <span data-ttu-id="5526c-154">Eseguire chiamate API, ad esempio \- elencare i dispositivi per vulnerabilità.</span><span class="sxs-lookup"><span data-stu-id="5526c-154">Run API calls such as \- list devices by vulnerability.</span></span>

## <a name="see-also"></a><span data-ttu-id="5526c-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5526c-155">See also</span></span>

- [<span data-ttu-id="5526c-156">API di Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="5526c-156">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)

- [<span data-ttu-id="5526c-157">Note sulla versione di Microsoft Defender for Endpoint API</span><span class="sxs-lookup"><span data-stu-id="5526c-157">Microsoft Defender for Endpoint API release notes</span></span>](api-release-notes.md)
