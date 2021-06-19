---
title: Esportare la valutazione delle vulnerabilità software per dispositivo
description: La risposta api è per dispositivo e contiene software vulnerabile installato nei dispositivi esposti, nonché eventuali vulnerabilità note in questi prodotti software. La tabella include anche informazioni su sistema operativo, ID CVE ID e grado di vulnerabilità.
keywords: api, api, valutazione dell'esportazione, valutazione per dispositivo, report di valutazione delle vulnerabilità, valutazione della vulnerabilità del dispositivo, report di vulnerabilità del dispositivo, valutazione della configurazione sicura, report di configurazione sicura, valutazione delle vulnerabilità software, report di vulnerabilità software, report sulle vulnerabilità in base al computer,
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.custom: api
ms.openlocfilehash: 6243da415c5cc509be33eabffd12516367164bff
ms.sourcegitcommit: bc64d9f619259bd0a94e43a9010aae5cffb4d6c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2021
ms.locfileid: "53022871"
---
# <a name="export-software-vulnerabilities-assessment-per-device"></a><span data-ttu-id="91bcb-105">Esportare la valutazione delle vulnerabilità software per dispositivo</span><span class="sxs-lookup"><span data-stu-id="91bcb-105">Export software vulnerabilities assessment per device</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="91bcb-106">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="91bcb-106">**Applies to:**</span></span>

- [<span data-ttu-id="91bcb-107">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="91bcb-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="91bcb-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="91bcb-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="91bcb-109">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="91bcb-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="91bcb-110">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="91bcb-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

>
<span data-ttu-id="91bcb-111">Restituisce tutte le vulnerabilità software note e i relativi dettagli per tutti i dispositivi, in base al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="91bcb-111">Returns all known software vulnerabilities and their details for all devices, on a per-device basis.</span></span>

<span data-ttu-id="91bcb-112">Esistono diverse chiamate API per ottenere diversi tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="91bcb-112">There are different API calls to get different types of data.</span></span> <span data-ttu-id="91bcb-113">Poiché la quantità di dati può essere molto grande, è possibile recuperarla in due modi:</span><span class="sxs-lookup"><span data-stu-id="91bcb-113">Because the amount of data can be very large, there are two ways it can be retrieved:</span></span>

1. <span data-ttu-id="91bcb-114">[Esportare la risposta JSON di valutazione **delle vulnerabilità software**](#1-export-software-vulnerabilities-assessment-json-response)  L'API estrae tutti i dati nell'organizzazione come risposte Json.</span><span class="sxs-lookup"><span data-stu-id="91bcb-114">[Export software vulnerabilities assessment **JSON response**](#1-export-software-vulnerabilities-assessment-json-response)  The API pulls all data in your organization as Json responses.</span></span> <span data-ttu-id="91bcb-115">Questo metodo è ideale per _organizzazioni di piccole dimensioni con meno di 100 K dispositivi._</span><span class="sxs-lookup"><span data-stu-id="91bcb-115">This method is best for _small organizations with less than 100 K devices_.</span></span> <span data-ttu-id="91bcb-116">La risposta viene impaginata, quindi è possibile utilizzare il campo \@ odata.nextLink dalla risposta per recuperare i risultati successivi.</span><span class="sxs-lookup"><span data-stu-id="91bcb-116">The response is paginated, so you can use the \@odata.nextLink field from the response to fetch the next results.</span></span>

2. <span data-ttu-id="91bcb-117">[Esportare la valutazione delle vulnerabilità software **tramite file**](#2-export-software-vulnerabilities-assessment-via-files) Questa soluzione API consente di estrarre grandi quantità di dati in modo più rapido e affidabile.</span><span class="sxs-lookup"><span data-stu-id="91bcb-117">[Export software vulnerabilities assessment **via files**](#2-export-software-vulnerabilities-assessment-via-files) This API solution enables pulling larger amounts of data faster and more reliably.</span></span> <span data-ttu-id="91bcb-118">I file via sono consigliati per organizzazioni di grandi dimensioni, con più di 100 dispositivi K.</span><span class="sxs-lookup"><span data-stu-id="91bcb-118">Via-files is recommended for large organizations, with more than 100 K devices.</span></span> <span data-ttu-id="91bcb-119">Questa API estrae tutti i dati dell'organizzazione come file di download.</span><span class="sxs-lookup"><span data-stu-id="91bcb-119">This API pulls all data in your organization as download files.</span></span> <span data-ttu-id="91bcb-120">La risposta contiene URL per scaricare tutti i dati da Archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="91bcb-120">The response contains URLs to download all the data from Azure Storage.</span></span> <span data-ttu-id="91bcb-121">Questa API consente di scaricare tutti i dati da Archiviazione di Azure come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="91bcb-121">This API enables you to download all your data from Azure Storage as follows:</span></span>

   - <span data-ttu-id="91bcb-122">Chiama l'API per ottenere un elenco di URL di download con tutti i dati dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="91bcb-122">Call the API to get a list of download URLs with all your organization data.</span></span>

   - <span data-ttu-id="91bcb-123">Scarica tutti i file usando gli URL di download ed elabora i dati come vuoi.</span><span class="sxs-lookup"><span data-stu-id="91bcb-123">Download all the files using the download URLs and process the data as you like.</span></span>

3. <span data-ttu-id="91bcb-124">[Risposta JSON per la valutazione delle vulnerabilità software **di esportazione delta**](#3-delta-export-software-vulnerabilities-assessment-json-response)  Restituisce una tabella con una voce per ogni combinazione univoca di: DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId ed EventTimestamp.</span><span class="sxs-lookup"><span data-stu-id="91bcb-124">[Delta export software vulnerabilities assessment **JSON response**](#3-delta-export-software-vulnerabilities-assessment-json-response)  Returns a table with an entry for every unique combination of: DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId, and EventTimestamp.</span></span>
<span data-ttu-id="91bcb-125">L'API estrae i dati nell'organizzazione come risposte Json.</span><span class="sxs-lookup"><span data-stu-id="91bcb-125">The API pulls data in your organization as Json responses.</span></span> <span data-ttu-id="91bcb-126">La risposta viene impaginata, quindi è possibile utilizzare il campo @odata.nextLink dalla risposta per recuperare i risultati successivi.</span><span class="sxs-lookup"><span data-stu-id="91bcb-126">The response is paginated, so you can use the @odata.nextLink field from the response to fetch the next results.</span></span> <br><br> <span data-ttu-id="91bcb-127">A differenza della "valutazione completa delle vulnerabilità software (risposta JSON)", che viene utilizzata per ottenere un'intera istantanea della valutazione delle vulnerabilità software dell'organizzazione tramite dispositivo, la chiamata API OData per l'esportazione delta viene utilizzata per recuperare solo le modifiche che si sono verificate tra una data selezionata e la data corrente (chiamata API "delta").</span><span class="sxs-lookup"><span data-stu-id="91bcb-127">Unlike the full "software vulnerabilities assessment (JSON response)" - which is used to obtain an entire snapshot of the software vulnerabilities assessment of your organization by device - the delta export OData API call is used to fetch only the changes that have happened between a selected date and the current date (the “delta” API call).</span></span> <span data-ttu-id="91bcb-128">Invece di ottenere un'esportazione completa con una grande quantità di dati ogni volta, si otterrà solo informazioni specifiche sulle vulnerabilità nuove, fisse e aggiornate.</span><span class="sxs-lookup"><span data-stu-id="91bcb-128">Instead of getting a full export with a large amount of data every time, you’ll only get specific information on new, fixed, and updated vulnerabilities.</span></span> <span data-ttu-id="91bcb-129">È inoltre possibile utilizzare la chiamata API di risposta JSON per l'esportazione delta per calcolare diversi indicatori KPI, ad esempio "quante vulnerabilità sono state risolvete?"</span><span class="sxs-lookup"><span data-stu-id="91bcb-129">Delta export JSON response API call can also be used to calculate different KPIs such as “how many vulnerabilities were fixed?”</span></span> <span data-ttu-id="91bcb-130">o "Quante nuove vulnerabilità sono state aggiunte all'organizzazione?"</span><span class="sxs-lookup"><span data-stu-id="91bcb-130">or “how many new vulnerabilities were added to my organization?”</span></span> <br><br> <span data-ttu-id="91bcb-131">Poiché la chiamata dell'API di risposta JSON di esportazione Delta per le vulnerabilità software restituisce dati solo per un intervallo di date mirato, non è considerata _un'esportazione completa._</span><span class="sxs-lookup"><span data-stu-id="91bcb-131">Because the Delta export JSON response API call for software vulnerabilities returns data for only a targeted date range, it is not considered a _full export_.</span></span>

<span data-ttu-id="91bcb-132">I dati raccolti (tramite _OData_ o _tramite file)_ sono lo snapshot corrente dello stato corrente e non contengono dati storici.</span><span class="sxs-lookup"><span data-stu-id="91bcb-132">Data that is collected (using either _OData_ or _via files_) is the current snapshot of the current state, and does not contain historic data.</span></span> <span data-ttu-id="91bcb-133">Per raccogliere i dati storici, i clienti devono salvare i dati nei propri archivi dati.</span><span class="sxs-lookup"><span data-stu-id="91bcb-133">In order to collect historic data, customers must save the data in their own data storages.</span></span>

> [!Note]
>
> <span data-ttu-id="91bcb-134">Se non diversamente indicato, tutti i metodi di valutazione dell'esportazione elencati sono **_l'esportazione_** completa e per dispositivo **_(noto_** anche **_come per dispositivo)._**</span><span class="sxs-lookup"><span data-stu-id="91bcb-134">Unless indicated otherwise, all export assessment methods listed are **_full export_** and **_by device_** (also referred to as **_per device_**).</span></span>

## <a name="1-export-software-vulnerabilities-assessment-json-response"></a><span data-ttu-id="91bcb-135">1. Esportare la valutazione delle vulnerabilità software (risposta JSON)</span><span class="sxs-lookup"><span data-stu-id="91bcb-135">1. Export software vulnerabilities assessment (JSON response)</span></span>

### <a name="11-api-method-description"></a><span data-ttu-id="91bcb-136">1.1 Descrizione del metodo API</span><span class="sxs-lookup"><span data-stu-id="91bcb-136">1.1 API method description</span></span>

<span data-ttu-id="91bcb-137">Questa risposta API contiene tutti i dati del software installato per dispositivo.</span><span class="sxs-lookup"><span data-stu-id="91bcb-137">This API response contains all the data of installed software per device.</span></span> <span data-ttu-id="91bcb-138">Restituisce una tabella con una voce per ogni combinazione univoca di DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.</span><span class="sxs-lookup"><span data-stu-id="91bcb-138">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.</span></span>

#### <a name="111-limitations"></a><span data-ttu-id="91bcb-139">1.1.1 Limitazioni</span><span class="sxs-lookup"><span data-stu-id="91bcb-139">1.1.1 Limitations</span></span>

- <span data-ttu-id="91bcb-140">La dimensione massima della pagina è 200.000.</span><span class="sxs-lookup"><span data-stu-id="91bcb-140">Maximum page size is 200,000.</span></span>

- <span data-ttu-id="91bcb-141">I limiti di frequenza per questa API sono 30 chiamate al minuto e 1000 chiamate all'ora.</span><span class="sxs-lookup"><span data-stu-id="91bcb-141">Rate limitations for this API are 30 calls per minute and 1000 calls per hour.</span></span>

### <a name="12-permissions"></a><span data-ttu-id="91bcb-142">1.2 Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="91bcb-142">1.2 Permissions</span></span>

<span data-ttu-id="91bcb-143">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="91bcb-143">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="91bcb-144">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi Usare Le API di [Microsoft Defender per endpoint per i dettagli.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="91bcb-144">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="91bcb-145">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="91bcb-145">Permission type</span></span> | <span data-ttu-id="91bcb-146">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="91bcb-146">Permission</span></span> | <span data-ttu-id="91bcb-147">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="91bcb-147">Permission display name</span></span>
---|---|---
<span data-ttu-id="91bcb-148">Applicazione</span><span class="sxs-lookup"><span data-stu-id="91bcb-148">Application</span></span> | <span data-ttu-id="91bcb-149">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="91bcb-149">Vulnerability.Read.All</span></span> | <span data-ttu-id="91bcb-150">\'Leggere informazioni sulla vulnerabilità di Gestione minacce e vulnerabilità\'</span><span class="sxs-lookup"><span data-stu-id="91bcb-150">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="91bcb-151">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="91bcb-151">Delegated (work or school account)</span></span> | <span data-ttu-id="91bcb-152">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="91bcb-152">Vulnerability.Read</span></span> | <span data-ttu-id="91bcb-153">\'Leggere informazioni sulla vulnerabilità di Gestione minacce e vulnerabilità\'</span><span class="sxs-lookup"><span data-stu-id="91bcb-153">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="13-url"></a><span data-ttu-id="91bcb-154">1.3 URL</span><span class="sxs-lookup"><span data-stu-id="91bcb-154">1.3 URL</span></span>

```http
GET /api/machines/SoftwareVulnerabilitiesByMachine
```

### <a name="14-parameters"></a><span data-ttu-id="91bcb-155">1.4 Parametri</span><span class="sxs-lookup"><span data-stu-id="91bcb-155">1.4 Parameters</span></span>

- <span data-ttu-id="91bcb-156">pageSize (impostazione predefinita = 50.000): numero di risultati in risposta</span><span class="sxs-lookup"><span data-stu-id="91bcb-156">pageSize (default = 50,000) – number of results in response</span></span>
- <span data-ttu-id="91bcb-157">$top - Numero di risultati da restituire (non restituisce @odata.nextLink e pertanto non estrae tutti i dati)</span><span class="sxs-lookup"><span data-stu-id="91bcb-157">$top – number of results to return (doesn’t return @odata.nextLink and therefore doesn’t pull all the data)</span></span>

### <a name="15-properties"></a><span data-ttu-id="91bcb-158">1.5 Proprietà</span><span class="sxs-lookup"><span data-stu-id="91bcb-158">1.5 Properties</span></span>

>[!Note]
>
>- <span data-ttu-id="91bcb-159">Ogni record è di circa 1 KB di dati.</span><span class="sxs-lookup"><span data-stu-id="91bcb-159">Each record is approximately 1 KB of data.</span></span> <span data-ttu-id="91bcb-160">È consigliabile prendere in considerazione questo parametro quando si sceglie il parametro pageSize corretto.</span><span class="sxs-lookup"><span data-stu-id="91bcb-160">You should take this into account when choosing the correct pageSize parameter for you.</span></span>
>
>- <span data-ttu-id="91bcb-161">Nella risposta potrebbero essere restituite alcune colonne aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="91bcb-161">Some additional columns might be returned in the response.</span></span> <span data-ttu-id="91bcb-162">Queste colonne sono temporanee e potrebbero essere rimosse, utilizzare solo le colonne documentate.</span><span class="sxs-lookup"><span data-stu-id="91bcb-162">These columns are temporary and might be removed, please use only the documented columns.</span></span>
>
>- <span data-ttu-id="91bcb-163">Le proprietà definite nella tabella seguente sono elencate in ordine alfabetico in base all'ID proprietà.</span><span class="sxs-lookup"><span data-stu-id="91bcb-163">The properties defined in the following table are listed alphabetically, by property ID.</span></span>  <span data-ttu-id="91bcb-164">Quando si esegue questa API, l'output risultante non verrà necessariamente restituito nello stesso ordine elencato in questa tabella.</span><span class="sxs-lookup"><span data-stu-id="91bcb-164">When running this API, the resulting output will not necessarily be returned in the same order listed in this table.</span></span>

<br/>

<span data-ttu-id="91bcb-165">Proprietà (ID)</span><span class="sxs-lookup"><span data-stu-id="91bcb-165">Property (ID)</span></span> | <span data-ttu-id="91bcb-166">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="91bcb-166">Data type</span></span> | <span data-ttu-id="91bcb-167">Descrizione</span><span class="sxs-lookup"><span data-stu-id="91bcb-167">Description</span></span> | <span data-ttu-id="91bcb-168">Esempio di valore restituito</span><span class="sxs-lookup"><span data-stu-id="91bcb-168">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="91bcb-169">CveId</span><span class="sxs-lookup"><span data-stu-id="91bcb-169">CveId</span></span> | <span data-ttu-id="91bcb-170">stringa</span><span class="sxs-lookup"><span data-stu-id="91bcb-170">string</span></span> | <span data-ttu-id="91bcb-171">Identificatore univoco assegnato alla vulnerabilità della sicurezza nel sistema CVE (Common Vulnerabilities and Exposures).</span><span class="sxs-lookup"><span data-stu-id="91bcb-171">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system.</span></span> | <span data-ttu-id="91bcb-172">CVE-2020-15992</span><span class="sxs-lookup"><span data-stu-id="91bcb-172">CVE-2020-15992</span></span>
<span data-ttu-id="91bcb-173">CvssScore</span><span class="sxs-lookup"><span data-stu-id="91bcb-173">CvssScore</span></span> | <span data-ttu-id="91bcb-174">stringa</span><span class="sxs-lookup"><span data-stu-id="91bcb-174">string</span></span> | <span data-ttu-id="91bcb-175">Punteggio CVSS del CVE.</span><span class="sxs-lookup"><span data-stu-id="91bcb-175">The CVSS score of the CVE.</span></span> | <span data-ttu-id="91bcb-176">6.2</span><span class="sxs-lookup"><span data-stu-id="91bcb-176">6.2</span></span>
<span data-ttu-id="91bcb-177">DeviceId</span><span class="sxs-lookup"><span data-stu-id="91bcb-177">DeviceId</span></span> | <span data-ttu-id="91bcb-178">stringa</span><span class="sxs-lookup"><span data-stu-id="91bcb-178">string</span></span> | <span data-ttu-id="91bcb-179">Identificatore univoco del dispositivo nel servizio.</span><span class="sxs-lookup"><span data-stu-id="91bcb-179">Unique identifier for the device in the service.</span></span> | <span data-ttu-id="91bcb-180">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span><span class="sxs-lookup"><span data-stu-id="91bcb-180">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span></span>
<span data-ttu-id="91bcb-181">DeviceName</span><span class="sxs-lookup"><span data-stu-id="91bcb-181">DeviceName</span></span> | <span data-ttu-id="91bcb-182">stringa</span><span class="sxs-lookup"><span data-stu-id="91bcb-182">string</span></span> | <span data-ttu-id="91bcb-183">Nome di dominio completo (FQDN) del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="91bcb-183">Fully qualified domain name (FQDN) of the device.</span></span> | <span data-ttu-id="91bcb-184">johnlaptop.europe.contoso.com</span><span class="sxs-lookup"><span data-stu-id="91bcb-184">johnlaptop.europe.contoso.com</span></span>
<span data-ttu-id="91bcb-185">DiskPaths</span><span class="sxs-lookup"><span data-stu-id="91bcb-185">DiskPaths</span></span>  | <span data-ttu-id="91bcb-186">Stringa \[ matrice\]</span><span class="sxs-lookup"><span data-stu-id="91bcb-186">Array\[string\]</span></span> | <span data-ttu-id="91bcb-187">Prova su disco che il prodotto è installato nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="91bcb-187">Disk evidence that the product is installed on the device.</span></span> | <span data-ttu-id="91bcb-188">[ "C:\Programmi (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]</span><span class="sxs-lookup"><span data-stu-id="91bcb-188">[ "C:\Program Files (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]</span></span>
<span data-ttu-id="91bcb-189">ExploitabilityLevel</span><span class="sxs-lookup"><span data-stu-id="91bcb-189">ExploitabilityLevel</span></span> | <span data-ttu-id="91bcb-190">stringa</span><span class="sxs-lookup"><span data-stu-id="91bcb-190">string</span></span> | <span data-ttu-id="91bcb-191">Livello di sfruttabilità di questa vulnerabilità (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)</span><span class="sxs-lookup"><span data-stu-id="91bcb-191">The exploitability level of this vulnerability (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)</span></span> | <span data-ttu-id="91bcb-192">ExploitIsInKit</span><span class="sxs-lookup"><span data-stu-id="91bcb-192">ExploitIsInKit</span></span>
<span data-ttu-id="91bcb-193">FirstSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="91bcb-193">FirstSeenTimestamp</span></span> | <span data-ttu-id="91bcb-194">stringa</span><span class="sxs-lookup"><span data-stu-id="91bcb-194">string</span></span> | <span data-ttu-id="91bcb-195">La prima volta che il CVE di questo prodotto è stato visualizzato nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="91bcb-195">First time the CVE of this product was seen on the device.</span></span> | <span data-ttu-id="91bcb-196">2020-11-03 10:13:34.8476880</span><span class="sxs-lookup"><span data-stu-id="91bcb-196">2020-11-03 10:13:34.8476880</span></span>
<span data-ttu-id="91bcb-197">Id</span><span class="sxs-lookup"><span data-stu-id="91bcb-197">Id</span></span> | <span data-ttu-id="91bcb-198">stringa</span><span class="sxs-lookup"><span data-stu-id="91bcb-198">string</span></span> | <span data-ttu-id="91bcb-199">Identificatore univoco del record.</span><span class="sxs-lookup"><span data-stu-id="91bcb-199">Unique identifier for the record.</span></span> | <span data-ttu-id="91bcb-200">123ABG55_573AG&mnp!</span><span class="sxs-lookup"><span data-stu-id="91bcb-200">123ABG55_573AG&mnp!</span></span>
<span data-ttu-id="91bcb-201">LastSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="91bcb-201">LastSeenTimestamp</span></span> | <span data-ttu-id="91bcb-202">stringa</span><span class="sxs-lookup"><span data-stu-id="91bcb-202">string</span></span> | <span data-ttu-id="91bcb-203">Ultima volta che il CVE è stato visualizzato nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="91bcb-203">Last time the CVE was seen on the device.</span></span> | <span data-ttu-id="91bcb-204">2020-11-03 10:13:34.8476880</span><span class="sxs-lookup"><span data-stu-id="91bcb-204">2020-11-03 10:13:34.8476880</span></span>
<span data-ttu-id="91bcb-205">OSPlatform</span><span class="sxs-lookup"><span data-stu-id="91bcb-205">OSPlatform</span></span> | <span data-ttu-id="91bcb-206">stringa</span><span class="sxs-lookup"><span data-stu-id="91bcb-206">string</span></span> | <span data-ttu-id="91bcb-207">Piattaforma del sistema operativo in esecuzione nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="91bcb-207">Platform of the operating system running on the device.</span></span> <span data-ttu-id="91bcb-208">Questa proprietà indica sistemi operativi specifici, incluse le varianti all'interno della stessa famiglia, ad esempio Windows 10 e Windows 7.</span><span class="sxs-lookup"><span data-stu-id="91bcb-208">This property indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> <span data-ttu-id="91bcb-209">Per informazioni dettagliate, vedere tvm supported operating systems and platforms.</span><span class="sxs-lookup"><span data-stu-id="91bcb-209">See tvm supported operating systems and platforms for details.</span></span> | <span data-ttu-id="91bcb-210">Windows10</span><span class="sxs-lookup"><span data-stu-id="91bcb-210">Windows10</span></span>
<span data-ttu-id="91bcb-211">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="91bcb-211">RbacGroupName</span></span>  | <span data-ttu-id="91bcb-212">stringa</span><span class="sxs-lookup"><span data-stu-id="91bcb-212">string</span></span> | <span data-ttu-id="91bcb-213">Gruppo RBAC (Role-Based Access Control).</span><span class="sxs-lookup"><span data-stu-id="91bcb-213">The role-based access control (RBAC) group.</span></span> <span data-ttu-id="91bcb-214">Se questo dispositivo non è assegnato ad alcun gruppo RBAC, il valore sarà "Non assegnato".</span><span class="sxs-lookup"><span data-stu-id="91bcb-214">If this device is not assigned to any RBAC group, the value will be “Unassigned.”</span></span> <span data-ttu-id="91bcb-215">Se l'organizzazione non contiene gruppi RBAC, il valore sarà "None".</span><span class="sxs-lookup"><span data-stu-id="91bcb-215">If the organization doesn’t contain any RBAC groups, the value will be “None.”</span></span> | <span data-ttu-id="91bcb-216">Server</span><span class="sxs-lookup"><span data-stu-id="91bcb-216">Servers</span></span>
<span data-ttu-id="91bcb-217">RecommendationReference</span><span class="sxs-lookup"><span data-stu-id="91bcb-217">RecommendationReference</span></span> | <span data-ttu-id="91bcb-218">stringa</span><span class="sxs-lookup"><span data-stu-id="91bcb-218">string</span></span> | <span data-ttu-id="91bcb-219">Riferimento all'ID suggerimento relativo a questo software.</span><span class="sxs-lookup"><span data-stu-id="91bcb-219">A reference to the recommendation ID related to this software.</span></span> | <span data-ttu-id="91bcb-220">va-_-microsoft-_-silverlight</span><span class="sxs-lookup"><span data-stu-id="91bcb-220">va-_-microsoft-_-silverlight</span></span>
<span data-ttu-id="91bcb-221">RecommendedSecurityUpdate (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="91bcb-221">RecommendedSecurityUpdate (optional)</span></span> | <span data-ttu-id="91bcb-222">stringa</span><span class="sxs-lookup"><span data-stu-id="91bcb-222">string</span></span> | <span data-ttu-id="91bcb-223">Nome o descrizione dell'aggiornamento della sicurezza fornito dal fornitore del software per risolvere la vulnerabilità.</span><span class="sxs-lookup"><span data-stu-id="91bcb-223">Name or description of the security update provided by the software vendor to address the vulnerability.</span></span> | <span data-ttu-id="91bcb-224">Aggiornamenti della sicurezza di aprile 2020</span><span class="sxs-lookup"><span data-stu-id="91bcb-224">April 2020 Security Updates</span></span>
<span data-ttu-id="91bcb-225">RecommendedSecurityUpdateId (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="91bcb-225">RecommendedSecurityUpdateId (optional)</span></span> | <span data-ttu-id="91bcb-226">stringa</span><span class="sxs-lookup"><span data-stu-id="91bcb-226">string</span></span> | <span data-ttu-id="91bcb-227">Identificatore degli aggiornamenti della sicurezza applicabili o dell'identificatore per gli articoli della Knowledge Base (KB) corrispondenti</span><span class="sxs-lookup"><span data-stu-id="91bcb-227">Identifier of the applicable security updates or identifier for the corresponding guidance or knowledge base (KB) articles</span></span> | <span data-ttu-id="91bcb-228">4550961</span><span class="sxs-lookup"><span data-stu-id="91bcb-228">4550961</span></span>
<span data-ttu-id="91bcb-229">RegistryPaths</span><span class="sxs-lookup"><span data-stu-id="91bcb-229">RegistryPaths</span></span>  | <span data-ttu-id="91bcb-230">Stringa \[ matrice\]</span><span class="sxs-lookup"><span data-stu-id="91bcb-230">Array\[string\]</span></span> | <span data-ttu-id="91bcb-231">Prova del Registro di sistema che il prodotto è installato nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="91bcb-231">Registry evidence that the product is installed in the device.</span></span> | <span data-ttu-id="91bcb-232">[ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\MicrosoftSilverlight" ]</span><span class="sxs-lookup"><span data-stu-id="91bcb-232">[ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\MicrosoftSilverlight" ]</span></span>
<span data-ttu-id="91bcb-233">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="91bcb-233">SoftwareName</span></span> | <span data-ttu-id="91bcb-234">stringa</span><span class="sxs-lookup"><span data-stu-id="91bcb-234">string</span></span> | <span data-ttu-id="91bcb-235">Nome del prodotto software.</span><span class="sxs-lookup"><span data-stu-id="91bcb-235">Name of the software product.</span></span> | <span data-ttu-id="91bcb-236">chrome</span><span class="sxs-lookup"><span data-stu-id="91bcb-236">chrome</span></span>
<span data-ttu-id="91bcb-237">SoftwareVendor</span><span class="sxs-lookup"><span data-stu-id="91bcb-237">SoftwareVendor</span></span> | <span data-ttu-id="91bcb-238">stringa</span><span class="sxs-lookup"><span data-stu-id="91bcb-238">string</span></span> | <span data-ttu-id="91bcb-239">Nome del fornitore del software.</span><span class="sxs-lookup"><span data-stu-id="91bcb-239">Name of the software vendor.</span></span> | <span data-ttu-id="91bcb-240">google</span><span class="sxs-lookup"><span data-stu-id="91bcb-240">google</span></span>
<span data-ttu-id="91bcb-241">SoftwareVersion</span><span class="sxs-lookup"><span data-stu-id="91bcb-241">SoftwareVersion</span></span> | <span data-ttu-id="91bcb-242">stringa</span><span class="sxs-lookup"><span data-stu-id="91bcb-242">string</span></span> | <span data-ttu-id="91bcb-243">Numero di versione del prodotto software.</span><span class="sxs-lookup"><span data-stu-id="91bcb-243">Version number of the software product.</span></span> | <span data-ttu-id="91bcb-244">81.0.4044.138</span><span class="sxs-lookup"><span data-stu-id="91bcb-244">81.0.4044.138</span></span>
<span data-ttu-id="91bcb-245">VulnerabilitySeverityLevel</span><span class="sxs-lookup"><span data-stu-id="91bcb-245">VulnerabilitySeverityLevel</span></span>  | <span data-ttu-id="91bcb-246">stringa</span><span class="sxs-lookup"><span data-stu-id="91bcb-246">string</span></span> | <span data-ttu-id="91bcb-247">Livello di gravità assegnato alla vulnerabilità della sicurezza in base al punteggio CVSS e ai fattori dinamici influenzati dal panorama delle minacce.</span><span class="sxs-lookup"><span data-stu-id="91bcb-247">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape.</span></span> | <span data-ttu-id="91bcb-248">Medio</span><span class="sxs-lookup"><span data-stu-id="91bcb-248">Medium</span></span>

### <a name="16-examples"></a><span data-ttu-id="91bcb-249">1.6 Esempi</span><span class="sxs-lookup"><span data-stu-id="91bcb-249">1.6 Examples</span></span>

#### <a name="161-request-example"></a><span data-ttu-id="91bcb-250">1.6.1 Esempio di richiesta</span><span class="sxs-lookup"><span data-stu-id="91bcb-250">1.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilitiesByMachine?pageSize=5
```

#### <a name="162-response-example"></a><span data-ttu-id="91bcb-251">1.6.2 Esempio di risposta</span><span class="sxs-lookup"><span data-stu-id="91bcb-251">1.6.2 Response example</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.AssetVulnerability)",
    "value": [
        {
            "id": "00044f612345baf759462dbe6db733b6a9c59ab4_edge_10.0.17763.1637__",
            "deviceId": "00044f612345daf756462bde6bd733b9a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eed224b2de2f5ea3142726e63f16a.DomainPII_21eeb80d089e79bdfa178eabfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "edge",
            "softwareVersion": "10.0.17763.1637",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [],
            "lastSeenTimestamp": "2020-12-30 14:17:26",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-edge"
        },
        {
            "id": "00044f912345baf756462bde6db733b9a9c56ad4_.net_framework_4.0.0.0__",
            "deviceId": "00044f912345daf756462bde6db733b6a9c59ad4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eed224b2be2f5ea3142726e63f16a.DomainPII_21eeb80b086e79bdfa178eabfa25e8de6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": ".net_framework",
            "softwareVersion": "4.0.0.0",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [
                "SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4.0\\Client\\Install"
            ],
            "lastSeenTimestamp": "2020-12-30 13:18:33",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-.net_framework"
        },
        {
            "id": "00044f912345baf756462dbe6db733d6a9c59ab4_system_center_2012_endpoint_protection_4.10.209.0__",
            "deviceId": "00044f912345daf756462bde6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eed224b2be2f5ea3142726e63f16a.DomainPII_21eed80b089e79bdfa178eadfa25e8be6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "system_center_2012_endpoint_protection",
            "softwareVersion": "4.10.209.0",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Security Client"
            ],
            "lastSeenTimestamp": "2020-12-30 14:17:26",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-system_center_2012_endpoint_protection"
        },
        {
            "id": "00044f612345bdaf759462dbe6bd733b6a9c59ab4_onedrive_20.245.1206.2__",
            "deviceId": "00044f91234daf759492dbe6bd733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_189663d45612eed224b2be2f5ea3142729e63f16a.DomainPII_21eed80b086e79bdfa178eadfa25e8de6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "onedrive",
            "softwareVersion": "20.245.1206.2",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_USERS\\S-1-5-21-2944539346-1310925172-2349113062-1001\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\OneDriveSetup.exe"
            ],
            "lastSeenTimestamp": "2020-12-30 13:18:33",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-onedrive"
        },
        {
            "id": "00044f912345daf759462bde6db733b6a9c56ab4_windows_10_10.0.17763.1637__",
            "deviceId": "00044f912345daf756462dbe6db733d6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eeb224d2be2f5ea3142729e63f16a.DomainPII_21eeb80d086e79bdfa178eadfa25e8de6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "windows_10",
            "softwareVersion": "10.0.17763.1637",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [],
            "lastSeenTimestamp": "2020-12-30 14:17:26",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-windows_10"
        }
    ],
    "@odata.nextLink": "https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilitiesByMachine?pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0xMS8xMTAxLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}
```

## <a name="2-export-software-vulnerabilities-assessment-via-files"></a><span data-ttu-id="91bcb-252">2. Esportare la valutazione delle vulnerabilità software (tramite file)</span><span class="sxs-lookup"><span data-stu-id="91bcb-252">2. Export software vulnerabilities assessment (via files)</span></span>

### <a name="21-api-method-description"></a><span data-ttu-id="91bcb-253">2.1 Descrizione del metodo API</span><span class="sxs-lookup"><span data-stu-id="91bcb-253">2.1 API method description</span></span>

<span data-ttu-id="91bcb-254">Questa risposta API contiene tutti i dati del software installato per dispositivo.</span><span class="sxs-lookup"><span data-stu-id="91bcb-254">This API response contains all the data of installed software per device.</span></span> <span data-ttu-id="91bcb-255">Restituisce una tabella con una voce per ogni combinazione univoca di DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.</span><span class="sxs-lookup"><span data-stu-id="91bcb-255">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.</span></span>

#### <a name="212-limitations"></a><span data-ttu-id="91bcb-256">2.1.2 Limitazioni</span><span class="sxs-lookup"><span data-stu-id="91bcb-256">2.1.2 Limitations</span></span>

<span data-ttu-id="91bcb-257">I limiti di frequenza per questa API sono 5 chiamate al minuto e 20 chiamate all'ora.</span><span class="sxs-lookup"><span data-stu-id="91bcb-257">Rate limitations for this API are 5 calls per minute and 20 calls per hour.</span></span>

### <a name="22-permissions"></a><span data-ttu-id="91bcb-258">2.2 Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="91bcb-258">2.2 Permissions</span></span>

<span data-ttu-id="91bcb-259">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="91bcb-259">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="91bcb-260">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi Usare Le API di [Microsoft Defender per endpoint per i dettagli.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="91bcb-260">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details](apis-intro.md).</span></span>

<span data-ttu-id="91bcb-261">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="91bcb-261">Permission type</span></span> | <span data-ttu-id="91bcb-262">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="91bcb-262">Permission</span></span> | <span data-ttu-id="91bcb-263">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="91bcb-263">Permission display name</span></span>
---|---|---
<span data-ttu-id="91bcb-264">Applicazione</span><span class="sxs-lookup"><span data-stu-id="91bcb-264">Application</span></span> | <span data-ttu-id="91bcb-265">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="91bcb-265">Vulnerability.Read.All</span></span> | <span data-ttu-id="91bcb-266">\'Leggere informazioni sulla vulnerabilità di Gestione minacce e vulnerabilità\'</span><span class="sxs-lookup"><span data-stu-id="91bcb-266">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="91bcb-267">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="91bcb-267">Delegated (work or school account)</span></span> | <span data-ttu-id="91bcb-268">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="91bcb-268">Vulnerability.Read</span></span> | <span data-ttu-id="91bcb-269">\'Leggere informazioni sulla vulnerabilità di Gestione minacce e vulnerabilità\'</span><span class="sxs-lookup"><span data-stu-id="91bcb-269">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="23-url"></a><span data-ttu-id="91bcb-270">2.3 URL</span><span class="sxs-lookup"><span data-stu-id="91bcb-270">2.3 URL</span></span>

```http
GET /api/machines/SoftwareVulnerabilitiesExport
```

### <a name="24-parameters"></a><span data-ttu-id="91bcb-271">2.4 Parametri</span><span class="sxs-lookup"><span data-stu-id="91bcb-271">2.4 Parameters</span></span>

- <span data-ttu-id="91bcb-272">sasValidHours: numero di ore per cui saranno validi gli URL di download (massimo 24 ore)</span><span class="sxs-lookup"><span data-stu-id="91bcb-272">sasValidHours – The number of hours that the download URLs will be valid for (Maximum 24 hours)</span></span>

### <a name="25-properties"></a><span data-ttu-id="91bcb-273">2.5 Proprietà</span><span class="sxs-lookup"><span data-stu-id="91bcb-273">2.5 Properties</span></span>

>[!Note]
>
>- <span data-ttu-id="91bcb-274">I file sono compressi con gzip & in formato Json multilinea.</span><span class="sxs-lookup"><span data-stu-id="91bcb-274">The files are gzip compressed & in multiline Json format.</span></span>
>
>- <span data-ttu-id="91bcb-275">Gli URL di download sono validi solo per 3 ore. in caso contrario, è possibile utilizzare il parametro .</span><span class="sxs-lookup"><span data-stu-id="91bcb-275">The download URLs are only valid for 3 hours; otherwise you can use the parameter.</span></span>
>
>- <span data-ttu-id="91bcb-276">Per ottenere la massima velocità di download dei dati, puoi assicurarti di eseguire il download dalla stessa area di Azure in cui si trovano i dati.</span><span class="sxs-lookup"><span data-stu-id="91bcb-276">For maximum download speed of your data, you can make sure you are downloading from the same Azure region that your data resides.</span></span>
>

>[!Note]
>
>- <span data-ttu-id="91bcb-277">Ogni record è di circa 1 KB di dati.</span><span class="sxs-lookup"><span data-stu-id="91bcb-277">Each record is approximately 1KB of data.</span></span> <span data-ttu-id="91bcb-278">È consigliabile prendere in considerazione questo parametro quando si sceglie il parametro pageSize corretto.</span><span class="sxs-lookup"><span data-stu-id="91bcb-278">You should take this into account when choosing the correct pageSize parameter for you.</span></span>
>
>- <span data-ttu-id="91bcb-279">Nella risposta potrebbero essere restituite alcune colonne aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="91bcb-279">Some additional columns might be returned in the response.</span></span> <span data-ttu-id="91bcb-280">Queste colonne sono temporanee e potrebbero essere rimosse, utilizzare solo le colonne documentate.</span><span class="sxs-lookup"><span data-stu-id="91bcb-280">These columns are temporary and might be removed, please use only the documented columns.</span></span>
>

<span data-ttu-id="91bcb-281">Proprietà (ID)</span><span class="sxs-lookup"><span data-stu-id="91bcb-281">Property (ID)</span></span> | <span data-ttu-id="91bcb-282">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="91bcb-282">Data type</span></span> | <span data-ttu-id="91bcb-283">Descrizione</span><span class="sxs-lookup"><span data-stu-id="91bcb-283">Description</span></span> | <span data-ttu-id="91bcb-284">Esempio di valore restituito</span><span class="sxs-lookup"><span data-stu-id="91bcb-284">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="91bcb-285">Esportare file</span><span class="sxs-lookup"><span data-stu-id="91bcb-285">Export files</span></span> | <span data-ttu-id="91bcb-286">stringa \[ di matrice\]</span><span class="sxs-lookup"><span data-stu-id="91bcb-286">array\[string\]</span></span>  | <span data-ttu-id="91bcb-287">Elenco di URL di download per i file che tengono lo snapshot corrente dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="91bcb-287">A list of download URLs for files holding the current snapshot of the organization.</span></span> | <span data-ttu-id="91bcb-288">[  “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2”  ]</span><span class="sxs-lookup"><span data-stu-id="91bcb-288">[  “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2”  ]</span></span>
<span data-ttu-id="91bcb-289">GeneratedTime</span><span class="sxs-lookup"><span data-stu-id="91bcb-289">GeneratedTime</span></span> | <span data-ttu-id="91bcb-290">stringa</span><span class="sxs-lookup"><span data-stu-id="91bcb-290">string</span></span> | <span data-ttu-id="91bcb-291">Ora in cui è stata generata l'esportazione.</span><span class="sxs-lookup"><span data-stu-id="91bcb-291">The time that the export was generated.</span></span> | <span data-ttu-id="91bcb-292">2021-05-20T08:00:00Z</span><span class="sxs-lookup"><span data-stu-id="91bcb-292">2021-05-20T08:00:00Z</span></span>

### <a name="26-examples"></a><span data-ttu-id="91bcb-293">2.6 Esempi</span><span class="sxs-lookup"><span data-stu-id="91bcb-293">2.6 Examples</span></span>

#### <a name="261-request-example"></a><span data-ttu-id="91bcb-294">2.6.1 Esempio di richiesta</span><span class="sxs-lookup"><span data-stu-id="91bcb-294">2.6.1 Request example</span></span>

```http
GET https://api-us.securitycenter.contoso.com/api/machines/SoftwareVulnerabilitiesExport
```

#### <a name="262-response-example"></a><span data-ttu-id="91bcb-295">2.6.2 Esempio di risposta</span><span class="sxs-lookup"><span data-stu-id="91bcb-295">2.6.2 Response example</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": [
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/VaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-bcc26c4f-e531-48db-9892-c93ac5d72d5c.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A35%3A13Z&se=2021-01-11T14%3A35%3A13Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/VaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-bcc26c4f-e531-48db-9892-c93ac5d72d5c.c001.json.gz?sv=2019-12-12&st=2021-01-11T11%3A35%3A13Z&se=2021-01-11T14%3A35%3A13Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/VaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-bcc26c4f-e531-48db-9892-c93ac5d72d5c.c002.json.gz?sv=2019-12-12&st=2021-01-11T11%3A35%3A13Z&se=2021-01-11T14%3A35%3A13Z&sr=b&sp=r&sig=..."
    ],
    "generatedTime": "2021-01-11T11:01:00Z"
}
```

## <a name="3-delta-export-software-vulnerabilities-assessment-json-response"></a><span data-ttu-id="91bcb-296">3. Valutazione delle vulnerabilità del software di esportazione delta (risposta JSON)</span><span class="sxs-lookup"><span data-stu-id="91bcb-296">3. Delta export software vulnerabilities assessment (JSON response)</span></span>

### <a name="31-api-method-description"></a><span data-ttu-id="91bcb-297">3.1 Descrizione del metodo API</span><span class="sxs-lookup"><span data-stu-id="91bcb-297">3.1 API method description</span></span>

<span data-ttu-id="91bcb-298">Restituisce una tabella con una voce per ogni combinazione univoca di DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId.</span><span class="sxs-lookup"><span data-stu-id="91bcb-298">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId.</span></span> <span data-ttu-id="91bcb-299">L'API estrae i dati nell'organizzazione come risposte Json.</span><span class="sxs-lookup"><span data-stu-id="91bcb-299">The API pulls data in your organization as Json responses.</span></span> <span data-ttu-id="91bcb-300">La risposta viene impaginata, quindi è possibile utilizzare il campo @odata.nextLink dalla risposta per recuperare i risultati successivi.</span><span class="sxs-lookup"><span data-stu-id="91bcb-300">The response is paginated, so you can use the @odata.nextLink field from the response to fetch the next results.</span></span> <span data-ttu-id="91bcb-301">A differenza della valutazione completa delle vulnerabilità software (risposta JSON), che viene utilizzata per ottenere un'intera istantanea della valutazione delle vulnerabilità software dell'organizzazione tramite dispositivo, la chiamata API di risposta JSON di esportazione delta viene utilizzata per recuperare solo le modifiche che si sono verificate tra una data selezionata e la data corrente (chiamata API "delta").</span><span class="sxs-lookup"><span data-stu-id="91bcb-301">Unlike the full software vulnerabilities assessment (JSON response)—which is used to obtain an entire snapshot of the software vulnerabilities assessment of your organization by device—the delta export JSON response API call is used to fetch only the changes that have happened between a selected date and the current date (the “delta” API call).</span></span> <span data-ttu-id="91bcb-302">Invece di ottenere un'esportazione completa con una grande quantità di dati ogni volta, si otterrà solo informazioni specifiche sulle vulnerabilità nuove, fisse e aggiornate.</span><span class="sxs-lookup"><span data-stu-id="91bcb-302">Instead of getting a full export with a large amount of data every time, you’ll only get specific information on new, fixed, and updated vulnerabilities.</span></span> <span data-ttu-id="91bcb-303">È inoltre possibile utilizzare la chiamata API di risposta JSON per l'esportazione delta per calcolare diversi indicatori KPI, ad esempio "quante vulnerabilità sono state risolvete?"</span><span class="sxs-lookup"><span data-stu-id="91bcb-303">Delta export JSON response API call can also be used to calculate different KPIs such as “how many vulnerabilities were fixed?”</span></span> <span data-ttu-id="91bcb-304">o "Quante nuove vulnerabilità sono state aggiunte all'organizzazione?"</span><span class="sxs-lookup"><span data-stu-id="91bcb-304">or “how many new vulnerabilities were added to my organization?”</span></span>

>[!NOTE]
>
><span data-ttu-id="91bcb-305">È consigliabile usare la valutazione completa delle vulnerabilità del software di esportazione in base alla chiamata API del dispositivo almeno una volta alla settimana e questa ulteriore vulnerabilità del software di esportazione cambia in base alle chiamate API del dispositivo (delta) per tutti gli altri giorni della settimana.</span><span class="sxs-lookup"><span data-stu-id="91bcb-305">It is highly recommended you use the full export software vulnerabilities assessment by device API call at least once a week, and this additional export software vulnerabilities changes by device (delta) API call all the other days of the week.</span></span>  <span data-ttu-id="91bcb-306">A differenza delle altre API di risposta JSON assessments, l'esportazione delta non è un'esportazione completa.</span><span class="sxs-lookup"><span data-stu-id="91bcb-306">Unlike the other Assessments JSON response APIs, the “delta export” is not a full export.</span></span> <span data-ttu-id="91bcb-307">L'esportazione delta include solo le modifiche apportate tra una data selezionata e la data corrente (chiamata API "delta").</span><span class="sxs-lookup"><span data-stu-id="91bcb-307">The delta export includes only the changes that have happened between a selected date and the current date (the “delta” API call).</span></span>

#### <a name="311-limitations"></a><span data-ttu-id="91bcb-308">3.1.1 Limitazioni</span><span class="sxs-lookup"><span data-stu-id="91bcb-308">3.1.1 Limitations</span></span>

- <span data-ttu-id="91bcb-309">La dimensione massima della pagina è 200.000.</span><span class="sxs-lookup"><span data-stu-id="91bcb-309">Maximum page size is 200,000.</span></span>

- <span data-ttu-id="91bcb-310">Il parametro sinceTime ha un massimo di 14 giorni.</span><span class="sxs-lookup"><span data-stu-id="91bcb-310">The sinceTime parameter has a maximum of 14 days.</span></span>

- <span data-ttu-id="91bcb-311">I limiti di frequenza per questa API sono 30 chiamate al minuto e 1000 chiamate all'ora.</span><span class="sxs-lookup"><span data-stu-id="91bcb-311">Rate limitations for this API are 30 calls per minute and 1000 calls per hour.</span></span>

### <a name="32-permissions"></a><span data-ttu-id="91bcb-312">3.2 Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="91bcb-312">3.2 Permissions</span></span>

<span data-ttu-id="91bcb-313">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="91bcb-313">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="91bcb-314">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi Usare Le API di [Microsoft Defender per endpoint per i dettagli.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="91bcb-314">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="91bcb-315">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="91bcb-315">Permission type</span></span> | <span data-ttu-id="91bcb-316">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="91bcb-316">Permission</span></span> | <span data-ttu-id="91bcb-317">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="91bcb-317">Permission display name</span></span>
---|---|---
<span data-ttu-id="91bcb-318">Applicazione</span><span class="sxs-lookup"><span data-stu-id="91bcb-318">Application</span></span> | <span data-ttu-id="91bcb-319">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="91bcb-319">Vulnerability.Read.All</span></span> | <span data-ttu-id="91bcb-320">"Leggere le informazioni sulla vulnerabilità di Gestione delle minacce e delle vulnerabilità"</span><span class="sxs-lookup"><span data-stu-id="91bcb-320">'Read Threat and Vulnerability Management vulnerability information'</span></span>
<span data-ttu-id="91bcb-321">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="91bcb-321">Delegated (work or school account)</span></span> | <span data-ttu-id="91bcb-322">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="91bcb-322">Vulnerability.Read</span></span> | <span data-ttu-id="91bcb-323">"Leggere le informazioni sulla vulnerabilità di Gestione delle minacce e delle vulnerabilità"</span><span class="sxs-lookup"><span data-stu-id="91bcb-323">'Read Threat and Vulnerability Management vulnerability information'</span></span>

### <a name="33-url"></a><span data-ttu-id="91bcb-324">3.3 URL</span><span class="sxs-lookup"><span data-stu-id="91bcb-324">3.3 URL</span></span>

```http
GET /api/machines/SoftwareVulnerabilityChangesByMachine 
```

### <a name="34-parameters"></a><span data-ttu-id="91bcb-325">3.4 Parametri</span><span class="sxs-lookup"><span data-stu-id="91bcb-325">3.4 Parameters</span></span>

- <span data-ttu-id="91bcb-326">sinceTime (obbligatorio): dati compresi tra un'ora selezionata e oggi.</span><span class="sxs-lookup"><span data-stu-id="91bcb-326">sinceTime (required) – The data between a selected time and today.</span></span>
- <span data-ttu-id="91bcb-327">pageSize (impostazione predefinita = 50.000): numero di risultati in risposta</span><span class="sxs-lookup"><span data-stu-id="91bcb-327">pageSize (default = 50,000) – number of results in response</span></span>
- <span data-ttu-id="91bcb-328">$top - Numero di risultati da restituire (non restituisce @odata.nextLink e pertanto non estrae tutti i dati)</span><span class="sxs-lookup"><span data-stu-id="91bcb-328">$top – number of results to return (doesn’t return @odata.nextLink and therefore doesn’t pull all the data)</span></span>

### <a name="35-properties"></a><span data-ttu-id="91bcb-329">3.5 Proprietà</span><span class="sxs-lookup"><span data-stu-id="91bcb-329">3.5 Properties</span></span>

<span data-ttu-id="91bcb-330">Ogni record restituito contiene tutti i dati della valutazione completa delle vulnerabilità del software di esportazione da parte dell'API OData del dispositivo, oltre a due campi aggiuntivi: _**EventTimestamp**_ e _**Status.**_</span><span class="sxs-lookup"><span data-stu-id="91bcb-330">Each returned record contains all the data from the full export software vulnerabilities assessment by device OData API, plus two additional fields:  _**EventTimestamp**_ and _**Status**_.</span></span>

>[!NOTE]
>- <span data-ttu-id="91bcb-331">Nella risposta potrebbero essere restituite alcune colonne aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="91bcb-331">Some additional columns might be returned in the response.</span></span> <span data-ttu-id="91bcb-332">Queste colonne sono temporanee e potrebbero essere rimosse, quindi usa solo le colonne documentate.</span><span class="sxs-lookup"><span data-stu-id="91bcb-332">These columns are temporary and might be removed, so please use only the documented columns.</span></span>
>
>- <span data-ttu-id="91bcb-333">Le proprietà definite nella tabella seguente sono elencate in ordine alfabetico in base all'ID proprietà.</span><span class="sxs-lookup"><span data-stu-id="91bcb-333">The properties defined in the following table are listed alphabetically, by property ID.</span></span>  <span data-ttu-id="91bcb-334">Quando si esegue questa API, l'output risultante non verrà necessariamente restituito nello stesso ordine elencato in questa tabella.</span><span class="sxs-lookup"><span data-stu-id="91bcb-334">When running this API, the resulting output will not necessarily be returned in the same order listed in this table.</span></span>
<br><br/>

<span data-ttu-id="91bcb-335">Proprietà (ID)</span><span class="sxs-lookup"><span data-stu-id="91bcb-335">Property (ID)</span></span> | <span data-ttu-id="91bcb-336">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="91bcb-336">Data type</span></span> | <span data-ttu-id="91bcb-337">Descrizione</span><span class="sxs-lookup"><span data-stu-id="91bcb-337">Description</span></span> | <span data-ttu-id="91bcb-338">Esempio di valore restituito</span><span class="sxs-lookup"><span data-stu-id="91bcb-338">Example of returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="91bcb-339">CveId</span><span class="sxs-lookup"><span data-stu-id="91bcb-339">CveId</span></span> | <span data-ttu-id="91bcb-340">stringa</span><span class="sxs-lookup"><span data-stu-id="91bcb-340">string</span></span> | <span data-ttu-id="91bcb-341">Identificatore univoco assegnato alla vulnerabilità della sicurezza nel sistema CVE (Common Vulnerabilities and Exposures).</span><span class="sxs-lookup"><span data-stu-id="91bcb-341">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system.</span></span> | <span data-ttu-id="91bcb-342">CVE-2020-15992</span><span class="sxs-lookup"><span data-stu-id="91bcb-342">CVE-2020-15992</span></span>  
<span data-ttu-id="91bcb-343">CvssScore</span><span class="sxs-lookup"><span data-stu-id="91bcb-343">CvssScore</span></span> | <span data-ttu-id="91bcb-344">stringa</span><span class="sxs-lookup"><span data-stu-id="91bcb-344">string</span></span> | <span data-ttu-id="91bcb-345">Punteggio CVSS del CVE.</span><span class="sxs-lookup"><span data-stu-id="91bcb-345">The CVSS score of the CVE.</span></span> | <span data-ttu-id="91bcb-346">6.2</span><span class="sxs-lookup"><span data-stu-id="91bcb-346">6.2</span></span>  
<span data-ttu-id="91bcb-347">DeviceId</span><span class="sxs-lookup"><span data-stu-id="91bcb-347">DeviceId</span></span> | <span data-ttu-id="91bcb-348">stringa</span><span class="sxs-lookup"><span data-stu-id="91bcb-348">string</span></span> | <span data-ttu-id="91bcb-349">Identificatore univoco del dispositivo nel servizio.</span><span class="sxs-lookup"><span data-stu-id="91bcb-349">Unique identifier for the device in the service.</span></span> | <span data-ttu-id="91bcb-350">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span><span class="sxs-lookup"><span data-stu-id="91bcb-350">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span></span>  
<span data-ttu-id="91bcb-351">DeviceName</span><span class="sxs-lookup"><span data-stu-id="91bcb-351">DeviceName</span></span> | <span data-ttu-id="91bcb-352">stringa</span><span class="sxs-lookup"><span data-stu-id="91bcb-352">string</span></span> | <span data-ttu-id="91bcb-353">Nome di dominio completo (FQDN) del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="91bcb-353">Fully qualified domain name (FQDN) of the device.</span></span> | <span data-ttu-id="91bcb-354">johnlaptop.europe.contoso.com</span><span class="sxs-lookup"><span data-stu-id="91bcb-354">johnlaptop.europe.contoso.com</span></span>  
<span data-ttu-id="91bcb-355">DiskPaths</span><span class="sxs-lookup"><span data-stu-id="91bcb-355">DiskPaths</span></span> | <span data-ttu-id="91bcb-356">Array[string]</span><span class="sxs-lookup"><span data-stu-id="91bcb-356">Array[string]</span></span> | <span data-ttu-id="91bcb-357">Prova su disco che il prodotto è installato nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="91bcb-357">Disk evidence that the product is installed on the device.</span></span> | <span data-ttu-id="91bcb-358">[ "C:\Programmi (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]</span><span class="sxs-lookup"><span data-stu-id="91bcb-358">[ "C:\Program Files (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]</span></span>  
<span data-ttu-id="91bcb-359">EventTimestamp</span><span class="sxs-lookup"><span data-stu-id="91bcb-359">EventTimestamp</span></span> | <span data-ttu-id="91bcb-360">Stringa</span><span class="sxs-lookup"><span data-stu-id="91bcb-360">String</span></span> | <span data-ttu-id="91bcb-361">Ora in cui è stato trovato questo evento delta.</span><span class="sxs-lookup"><span data-stu-id="91bcb-361">The time this delta event was found.</span></span> | <span data-ttu-id="91bcb-362">2021-01-11T11:06:08.291Z</span><span class="sxs-lookup"><span data-stu-id="91bcb-362">2021-01-11T11:06:08.291Z</span></span>
<span data-ttu-id="91bcb-363">ExploitabilityLevel</span><span class="sxs-lookup"><span data-stu-id="91bcb-363">ExploitabilityLevel</span></span> | <span data-ttu-id="91bcb-364">stringa</span><span class="sxs-lookup"><span data-stu-id="91bcb-364">string</span></span> | <span data-ttu-id="91bcb-365">Livello di sfruttabilità di questa vulnerabilità (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)</span><span class="sxs-lookup"><span data-stu-id="91bcb-365">The exploitability level of this vulnerability (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)</span></span> | <span data-ttu-id="91bcb-366">ExploitIsInKit</span><span class="sxs-lookup"><span data-stu-id="91bcb-366">ExploitIsInKit</span></span>  
<span data-ttu-id="91bcb-367">FirstSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="91bcb-367">FirstSeenTimestamp</span></span> | <span data-ttu-id="91bcb-368">stringa</span><span class="sxs-lookup"><span data-stu-id="91bcb-368">string</span></span> | <span data-ttu-id="91bcb-369">La prima volta che il CVE di questo prodotto è stato visualizzato nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="91bcb-369">First time the CVE of this product was seen on the device.</span></span> | <span data-ttu-id="91bcb-370">2020-11-03 10:13:34.8476880</span><span class="sxs-lookup"><span data-stu-id="91bcb-370">2020-11-03 10:13:34.8476880</span></span>  
<span data-ttu-id="91bcb-371">Id</span><span class="sxs-lookup"><span data-stu-id="91bcb-371">Id</span></span> | <span data-ttu-id="91bcb-372">stringa</span><span class="sxs-lookup"><span data-stu-id="91bcb-372">string</span></span> | <span data-ttu-id="91bcb-373">Identificatore univoco del record.</span><span class="sxs-lookup"><span data-stu-id="91bcb-373">Unique identifier for the record.</span></span> | <span data-ttu-id="91bcb-374">123ABG55_573AG&mnp!</span><span class="sxs-lookup"><span data-stu-id="91bcb-374">123ABG55_573AG&mnp!</span></span>  
<span data-ttu-id="91bcb-375">LastSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="91bcb-375">LastSeenTimestamp</span></span> | <span data-ttu-id="91bcb-376">stringa</span><span class="sxs-lookup"><span data-stu-id="91bcb-376">string</span></span> | <span data-ttu-id="91bcb-377">Ultima volta che il CVE è stato visualizzato nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="91bcb-377">Last time the CVE was seen on the device.</span></span> | <span data-ttu-id="91bcb-378">2020-11-03 10:13:34.8476880</span><span class="sxs-lookup"><span data-stu-id="91bcb-378">2020-11-03 10:13:34.8476880</span></span>  
<span data-ttu-id="91bcb-379">OSPlatform</span><span class="sxs-lookup"><span data-stu-id="91bcb-379">OSPlatform</span></span> | <span data-ttu-id="91bcb-380">stringa</span><span class="sxs-lookup"><span data-stu-id="91bcb-380">string</span></span> | <span data-ttu-id="91bcb-381">Piattaforma del sistema operativo in esecuzione nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="91bcb-381">Platform of the operating system running on the device.</span></span> <span data-ttu-id="91bcb-382">Ciò indica specifici sistemi operativi, incluse variazioni all'interno della stessa famiglia di prodotti, come Windows 10 e Windows 7.</span><span class="sxs-lookup"><span data-stu-id="91bcb-382">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> <span data-ttu-id="91bcb-383">Per informazioni dettagliate, vedere tvm supported operating systems and platforms.</span><span class="sxs-lookup"><span data-stu-id="91bcb-383">See tvm supported operating systems and platforms for details.</span></span> | <span data-ttu-id="91bcb-384">Windows10</span><span class="sxs-lookup"><span data-stu-id="91bcb-384">Windows10</span></span>  
<span data-ttu-id="91bcb-385">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="91bcb-385">RbacGroupName</span></span> | <span data-ttu-id="91bcb-386">stringa</span><span class="sxs-lookup"><span data-stu-id="91bcb-386">string</span></span> | <span data-ttu-id="91bcb-387">Gruppo RBAC (Role-Based Access Control).</span><span class="sxs-lookup"><span data-stu-id="91bcb-387">The role-based access control (RBAC) group.</span></span> <span data-ttu-id="91bcb-388">Se questo dispositivo non è assegnato ad alcun gruppo RBAC, il valore sarà "Non assegnato".</span><span class="sxs-lookup"><span data-stu-id="91bcb-388">If this device is not assigned to any RBAC group, the value will be “Unassigned.”</span></span> <span data-ttu-id="91bcb-389">Se l'organizzazione non contiene gruppi RBAC, il valore sarà "None".</span><span class="sxs-lookup"><span data-stu-id="91bcb-389">If the organization doesn’t contain any RBAC groups, the value will be “None.”</span></span> | <span data-ttu-id="91bcb-390">Server</span><span class="sxs-lookup"><span data-stu-id="91bcb-390">Servers</span></span>  
<span data-ttu-id="91bcb-391">RecommendationReference</span><span class="sxs-lookup"><span data-stu-id="91bcb-391">RecommendationReference</span></span> | <span data-ttu-id="91bcb-392">stringa</span><span class="sxs-lookup"><span data-stu-id="91bcb-392">string</span></span> | <span data-ttu-id="91bcb-393">Riferimento all'ID suggerimento relativo a questo software.</span><span class="sxs-lookup"><span data-stu-id="91bcb-393">A reference to the recommendation ID related to this software.</span></span> | <span data-ttu-id="91bcb-394">va--microsoft--silverlight</span><span class="sxs-lookup"><span data-stu-id="91bcb-394">va--microsoft--silverlight</span></span>  
<span data-ttu-id="91bcb-395">RecommendedSecurityUpdate</span><span class="sxs-lookup"><span data-stu-id="91bcb-395">RecommendedSecurityUpdate</span></span>  | <span data-ttu-id="91bcb-396">stringa</span><span class="sxs-lookup"><span data-stu-id="91bcb-396">string</span></span> | <span data-ttu-id="91bcb-397">Nome o descrizione dell'aggiornamento della sicurezza fornito dal fornitore del software per risolvere la vulnerabilità.</span><span class="sxs-lookup"><span data-stu-id="91bcb-397">Name or description of the security update provided by the software vendor to address the vulnerability.</span></span> | <span data-ttu-id="91bcb-398">Aggiornamenti della sicurezza di aprile 2020</span><span class="sxs-lookup"><span data-stu-id="91bcb-398">April 2020 Security Updates</span></span>  
<span data-ttu-id="91bcb-399">RecommendedSecurityUpdateId</span><span class="sxs-lookup"><span data-stu-id="91bcb-399">RecommendedSecurityUpdateId</span></span>  | <span data-ttu-id="91bcb-400">stringa</span><span class="sxs-lookup"><span data-stu-id="91bcb-400">string</span></span> | <span data-ttu-id="91bcb-401">Identificatore degli aggiornamenti della sicurezza applicabili o dell'identificatore per gli articoli della Knowledge Base (KB) corrispondenti</span><span class="sxs-lookup"><span data-stu-id="91bcb-401">Identifier of the applicable security updates or identifier for the corresponding guidance or knowledge base (KB) articles</span></span> | <span data-ttu-id="91bcb-402">4550961</span><span class="sxs-lookup"><span data-stu-id="91bcb-402">4550961</span></span>  
<span data-ttu-id="91bcb-403">RegistryPaths</span><span class="sxs-lookup"><span data-stu-id="91bcb-403">RegistryPaths</span></span>  | <span data-ttu-id="91bcb-404">Array[string]</span><span class="sxs-lookup"><span data-stu-id="91bcb-404">Array[string]</span></span> | <span data-ttu-id="91bcb-405">Prova del Registro di sistema che il prodotto è installato nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="91bcb-405">Registry evidence that the product is installed in the device.</span></span> | <span data-ttu-id="91bcb-406">[ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\Google Chrome" ]</span><span class="sxs-lookup"><span data-stu-id="91bcb-406">[ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\Google Chrome" ]</span></span>  
<span data-ttu-id="91bcb-407">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="91bcb-407">SoftwareName</span></span> | <span data-ttu-id="91bcb-408">stringa</span><span class="sxs-lookup"><span data-stu-id="91bcb-408">string</span></span> | <span data-ttu-id="91bcb-409">Nome del prodotto software.</span><span class="sxs-lookup"><span data-stu-id="91bcb-409">Name of the software product.</span></span> | <span data-ttu-id="91bcb-410">chrome</span><span class="sxs-lookup"><span data-stu-id="91bcb-410">chrome</span></span>  
<span data-ttu-id="91bcb-411">SoftwareVendor</span><span class="sxs-lookup"><span data-stu-id="91bcb-411">SoftwareVendor</span></span> | <span data-ttu-id="91bcb-412">stringa</span><span class="sxs-lookup"><span data-stu-id="91bcb-412">string</span></span> | <span data-ttu-id="91bcb-413">Nome del fornitore del software.</span><span class="sxs-lookup"><span data-stu-id="91bcb-413">Name of the software vendor.</span></span> | <span data-ttu-id="91bcb-414">google</span><span class="sxs-lookup"><span data-stu-id="91bcb-414">google</span></span>  
<span data-ttu-id="91bcb-415">SoftwareVersion</span><span class="sxs-lookup"><span data-stu-id="91bcb-415">SoftwareVersion</span></span> | <span data-ttu-id="91bcb-416">stringa</span><span class="sxs-lookup"><span data-stu-id="91bcb-416">string</span></span> | <span data-ttu-id="91bcb-417">Numero di versione del prodotto software.</span><span class="sxs-lookup"><span data-stu-id="91bcb-417">Version number of the software product.</span></span> | <span data-ttu-id="91bcb-418">81.0.4044.138</span><span class="sxs-lookup"><span data-stu-id="91bcb-418">81.0.4044.138</span></span>  
<span data-ttu-id="91bcb-419">Stato</span><span class="sxs-lookup"><span data-stu-id="91bcb-419">Status</span></span> | <span data-ttu-id="91bcb-420">Stringa</span><span class="sxs-lookup"><span data-stu-id="91bcb-420">String</span></span> | <span data-ttu-id="91bcb-421">**Nuovo**   (per una nuova vulnerabilità introdotta in un dispositivo)  (1) **Risolto**(se questa vulnerabilità non esiste più nel dispositivo, il che significa che è   stata corretta).</span><span class="sxs-lookup"><span data-stu-id="91bcb-421">**New** (for a new vulnerability introduced on a device)  (1) **Fixed** (if this vulnerability doesn’t exist anymore on the device, which means it was remediated).</span></span> <span data-ttu-id="91bcb-422">(2)  **Aggiornato**   (se una vulnerabilità in un dispositivo è cambiata.</span><span class="sxs-lookup"><span data-stu-id="91bcb-422">(2) **Updated** (if a vulnerability on a device has changed.</span></span> <span data-ttu-id="91bcb-423">Le possibili modifiche sono: punteggio CVSS, livello di exploit, livello di gravità, DiskPaths, RegistryPaths, RecommendedSecurityUpdate).</span><span class="sxs-lookup"><span data-stu-id="91bcb-423">The possible changes are: CVSS score, exploitability level, severity level, DiskPaths, RegistryPaths, RecommendedSecurityUpdate).</span></span> | <span data-ttu-id="91bcb-424">Risolto</span><span class="sxs-lookup"><span data-stu-id="91bcb-424">Fixed</span></span>
<span data-ttu-id="91bcb-425">VulnerabilitySeverityLevel</span><span class="sxs-lookup"><span data-stu-id="91bcb-425">VulnerabilitySeverityLevel</span></span> | <span data-ttu-id="91bcb-426">stringa</span><span class="sxs-lookup"><span data-stu-id="91bcb-426">string</span></span> | <span data-ttu-id="91bcb-427">Livello di gravità assegnato alla vulnerabilità della sicurezza in base al punteggio CVSS e ai fattori dinamici influenzati dal panorama delle minacce.</span><span class="sxs-lookup"><span data-stu-id="91bcb-427">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape.</span></span> | <span data-ttu-id="91bcb-428">Medio</span><span class="sxs-lookup"><span data-stu-id="91bcb-428">Medium</span></span>  

#### <a name="clarifications"></a><span data-ttu-id="91bcb-429">Chiarimenti</span><span class="sxs-lookup"><span data-stu-id="91bcb-429">Clarifications</span></span>

- <span data-ttu-id="91bcb-430">Se il software è stato aggiornato dalla versione 1.0 alla versione 2.0 ed entrambe le versioni sono esposte a CVE-A, si riceveranno due eventi distinti:</span><span class="sxs-lookup"><span data-stu-id="91bcb-430">If the software was updated from version 1.0 to version 2.0, and both versions are exposed to CVE-A, you will receive 2 separate events:</span></span>  
   1. <span data-ttu-id="91bcb-431">Risolto : CVE-A versione 1.0 è stata corretta</span><span class="sxs-lookup"><span data-stu-id="91bcb-431">Fixed – CVE-A on version 1.0 was fixed</span></span>  
   1. <span data-ttu-id="91bcb-432">New : È stato aggiunto CVE-A versione 2.0</span><span class="sxs-lookup"><span data-stu-id="91bcb-432">New – CVE-A on version 2.0 was added</span></span>

- <span data-ttu-id="91bcb-433">Se una vulnerabilità specifica (ad esempio, CVE-A) è stata vista per la prima volta in un momento specifico (ad esempio, il 10 gennaio) nel software con la versione 1.0 e pochi giorni dopo tale software è stato aggiornato alla versione 2.0 che è stata anche esposta allo stesso CVE-A, si riceveranno questi due eventi separati:</span><span class="sxs-lookup"><span data-stu-id="91bcb-433">If a specific vulnerability (for example, CVE-A) was first seen at a specific time (for example, January 10) on software with version 1.0, and a few days later that software was updated to version 2.0 which also exposed to the same CVE-A, you will receive these two separated events:</span></span>  
   1. <span data-ttu-id="91bcb-434">Risolto : CVE-X, FirstSeenTimestamp il 10 gennaio, versione 1,0.</span><span class="sxs-lookup"><span data-stu-id="91bcb-434">Fixed – CVE-X, FirstSeenTimestamp January 10, version 1,0.</span></span>  
   1. <span data-ttu-id="91bcb-435">New : CVE-X, FirstSeenTimestamp il 10 gennaio, versione 2.0.</span><span class="sxs-lookup"><span data-stu-id="91bcb-435">New – CVE-X, FirstSeenTimestamp January 10, version 2.0.</span></span>

### <a name="36-examples"></a><span data-ttu-id="91bcb-436">3.6 Esempi</span><span class="sxs-lookup"><span data-stu-id="91bcb-436">3.6 Examples</span></span>

#### <a name="361-request-example"></a><span data-ttu-id="91bcb-437">3.6.1 Esempio di richiesta</span><span class="sxs-lookup"><span data-stu-id="91bcb-437">3.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilityChangesByMachine?pageSize=5&sinceTime=2021-05-19T18%3A35%3A49.924Z
```

#### <a name="362-response-example"></a><span data-ttu-id="91bcb-438">3.6.2 Esempio di risposta</span><span class="sxs-lookup"><span data-stu-id="91bcb-438">3.6.2 Response example</span></span>

```json
{ 
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.DeltaAssetVulnerability)", 
    "value": [ 
        { 
            "id": "008198251234544f7dfa715e278d4cec0c16c171_chrome_87.0.4280.88__", 
            "deviceId": "008198251234544f7dfa715e278b4cec0c19c171",  
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_1c8fee370690ca24b6a0d3f34d193b0424943a8b8.DomainPII_0dc1aee0fa366d175e514bd91a9e7a5b2b07ee8e.corp.contoso.com", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.19042.685", 
            "osArchitecture": "x64", 
            "softwareVendor": "google", 
            "softwareName": "chrome", 
            "softwareVersion": "87.0.4280.88", 
            "cveId": null, 
            "vulnerabilitySeverityLevel": null, 
            "recommendedSecurityUpdate": null, 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [ 
                "C:\\Program Files (x86)\\Google\\Chrome\\Application\\chrome.exe" 
            ], 
            "registryPaths": [ 
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\WOW6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Google Chrome" 
            ], 
            "lastSeenTimestamp": "2021-01-04 00:29:42", 
            "firstSeenTimestamp": "2020-11-06 03:12:44", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-google-_-chrome", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        }, 
        { 
            "id": "00e59c61234533860738ecf488eec8abf296e41e_onedrive_20.64.329.3__", 
            "deviceId": "00e56c91234533860738ecf488eec8abf296e41e",  
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_82c13a8ad8cf3dbaf7bf34fada9fa3aebc124116.DomainPII_21eeb80d086e79dbfa178eadfa25e8de9acfa346.corp.contoso.com", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.18363.1256", 
            "osArchitecture": "x64", 
            "softwareVendor": "microsoft", 
            "softwareName": "onedrive", 
            "softwareVersion": "20.64.329.3", 
            "cveId": null, 
            "vulnerabilitySeverityLevel": null, 
            "recommendedSecurityUpdate": null, 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [], 
            "registryPaths": [ 
                "HKEY_USERS\\S-1-5-21-2127521184-1604012920-1887927527-24918864\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\OneDriveSetup.exe" 
            ], 
            "lastSeenTimestamp": "2020-12-11 19:49:48", 
            "firstSeenTimestamp": "2020-12-07 18:25:47", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-microsoft-_-onedrive", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        }, 
        { 
            "id": "01aa8c73095bb12345918663f3f94ce322107d24_firefox_83.0.0.0_CVE-2020-26971_", 
            "deviceId": "01aa8c73065bb12345918693f3f94ce322107d24", 
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_42684eb981bea2d670027e7ad2caafd3f2b381a3.DomainPII_21eed80b086e76dbfa178eabfa25e8de9acfa346.corp.contoso.com", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.19042.685", 
            "osArchitecture": "x64", 
            "softwareVendor": "mozilla", 
            "softwareName": "firefox", 
            "softwareVersion": "83.0.0.0", 
            "cveId": "CVE-2020-26971", 
            "vulnerabilitySeverityLevel": "High", 
            "recommendedSecurityUpdate": "193220", 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [ 
                "C:\\Program Files (x86)\\Mozilla Firefox\\firefox.exe" 
            ], 
            "registryPaths": [ 
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\WOW6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Mozilla Firefox 83.0 (x86 en-US)" 
            ], 
            "lastSeenTimestamp": "2021-01-05 17:04:30", 
            "firstSeenTimestamp": "2020-05-06 12:42:19", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-mozilla-_-firefox", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        }, 
        { 
            "id": "026f0fcb12345fbd2decd1a339702131422d362e_project_16.0.13701.20000__", 
            "deviceId": "029f0fcb13245fbd2decd1a336702131422d392e", 
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_a5706750acba75f15d69cd17f4a7fcd268d6422c.DomainPII_f290e982685f7e8eee168b4332e0ae5d2a069cd6.corp.contoso.com", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.19042.685", 
            "osArchitecture": "x64", 
            "softwareVendor": "microsoft", 
            "softwareName": "project", 
            "softwareVersion": "16.0.13701.20000", 
            "cveId": null, 
            "vulnerabilitySeverityLevel": null, 
            "recommendedSecurityUpdate": null, 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [], 
            "registryPaths": [ 
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\ProjectProRetail - en-us" 
            ], 
            "lastSeenTimestamp": "2021-01-03 23:38:03", 
            "firstSeenTimestamp": "2019-08-01 22:56:12", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-microsoft-_-project", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        }, 
        { 
            "id": "038df381234510b357ac19d0113ef622e4e212b3_chrome_81.0.4044.138_CVE-2020-16011_", 
            "deviceId": "038df381234510d357ac19b0113ef922e4e212b3",  
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_365f5c0bb7202c163937dad3d017969b2d760eb4.DomainPII_29596a43a2ef2bbfa00f6a16c0cb1d108bc63e32.DomainPII_3c5fefd2e6fda2f36257359404f6c1092aa6d4b8.net", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.18363.1256", 
            "osArchitecture": "x64", 
            "softwareVendor": "google", 
            "softwareName": "chrome", 
            "softwareVersion": "81.0.4044.138", 
            "cveId": "CVE-2020-16011", 
            "vulnerabilitySeverityLevel": "High", 
            "recommendedSecurityUpdate": "ADV 200002", 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [ 
                "C:\\Program Files (x86)\\Google\\Chrome\\Application\\chrome.exe" 
            ], 
            "registryPaths": [ 
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\{C4EBFDFD-0C55-3E5F-A919-E3C54949024A}" 
            ], 
            "lastSeenTimestamp": "2020-12-10 22:45:41", 
            "firstSeenTimestamp": "2020-07-26 02:13:43", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-google-_-chrome", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        } 
    ], 
    "@odata.nextLink": "https://wpatdadi-eus-stg.cloudapp.net/api/machines/SoftwareVulnerabilitiesTimeline?sincetime=2021-01-11&pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0xMS8xMTAxLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9" 
} 
```

## <a name="see-also"></a><span data-ttu-id="91bcb-439">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="91bcb-439">See also</span></span>

- [<span data-ttu-id="91bcb-440">Esportare proprietà e metodi di valutazione per dispositivo</span><span class="sxs-lookup"><span data-stu-id="91bcb-440">Export assessment methods and properties per device</span></span>](get-assessment-methods-properties.md)

- [<span data-ttu-id="91bcb-441">Esportare la valutazione della configurazione sicura per dispositivo</span><span class="sxs-lookup"><span data-stu-id="91bcb-441">Export secure configuration assessment per device</span></span>](get-assessment-secure-config.md)

- [<span data-ttu-id="91bcb-442">Esportare la valutazione dell'inventario software per dispositivo</span><span class="sxs-lookup"><span data-stu-id="91bcb-442">Export software inventory assessment per device</span></span>](get-assessment-software-inventory.md)

<span data-ttu-id="91bcb-443">Altre informazioni correlate</span><span class="sxs-lookup"><span data-stu-id="91bcb-443">Other related</span></span>

- [<span data-ttu-id="91bcb-444">Rischio basato sulle minacce & gestione delle vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="91bcb-444">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="91bcb-445">Vulnerabilità nell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="91bcb-445">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
