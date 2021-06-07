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
ms.openlocfilehash: 951f78ba361a12e404a5cce2071f931eab30c43f
ms.sourcegitcommit: 83df0be7144c9c5d606f70b4efa65369e86693d2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/05/2021
ms.locfileid: "52778327"
---
# <a name="export-software-vulnerabilities-assessment-per-device"></a><span data-ttu-id="6d76f-105">Esportare la valutazione delle vulnerabilità software per dispositivo</span><span class="sxs-lookup"><span data-stu-id="6d76f-105">Export software vulnerabilities assessment per device</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6d76f-106">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="6d76f-106">**Applies to:**</span></span>

- [<span data-ttu-id="6d76f-107">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="6d76f-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6d76f-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6d76f-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="6d76f-109">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="6d76f-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6d76f-110">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="6d76f-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]
>
>
<span data-ttu-id="6d76f-111">Restituisce tutte le vulnerabilità software note e i relativi dettagli per tutti i dispositivi, in base al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6d76f-111">Returns all known software vulnerabilities and their details for all devices, on a per-device basis.</span></span>

<span data-ttu-id="6d76f-112">Esistono diverse chiamate API per ottenere diversi tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="6d76f-112">There are different API calls to get different types of data.</span></span> <span data-ttu-id="6d76f-113">Poiché la quantità di dati può essere molto grande, è possibile recuperarla in due modi:</span><span class="sxs-lookup"><span data-stu-id="6d76f-113">Because the amount of data can be very large, there are two ways it can be retrieved:</span></span>

- <span data-ttu-id="6d76f-114">[Valutazione delle vulnerabilità del software di esportazione OData](#1-export-software-vulnerabilities-assessment-odata)  L'API estrae tutti i dati nell'organizzazione come risposte Json, seguendo il protocollo OData.</span><span class="sxs-lookup"><span data-stu-id="6d76f-114">[Export software vulnerabilities assessment OData](#1-export-software-vulnerabilities-assessment-odata)  The API pulls all data in your organization as Json responses, following the OData protocol.</span></span> <span data-ttu-id="6d76f-115">Questo metodo è ideale per _organizzazioni di piccole dimensioni con meno di 100 K dispositivi._</span><span class="sxs-lookup"><span data-stu-id="6d76f-115">This method is best for _small organizations with less than 100 K devices_.</span></span> <span data-ttu-id="6d76f-116">La risposta viene impaginata, quindi è possibile utilizzare il campo \@ odata.nextLink dalla risposta per recuperare i risultati successivi.</span><span class="sxs-lookup"><span data-stu-id="6d76f-116">The response is paginated, so you can use the \@odata.nextLink field from the response to fetch the next results.</span></span>

- <span data-ttu-id="6d76f-117">[Esportare la valutazione delle vulnerabilità software tramite file](#2-export-software-vulnerabilities-assessment-via-files) Questa soluzione API consente di estrarre grandi quantità di dati in modo più rapido e affidabile.</span><span class="sxs-lookup"><span data-stu-id="6d76f-117">[Export software vulnerabilities assessment via files](#2-export-software-vulnerabilities-assessment-via-files) This API solution enables pulling larger amounts of data faster and more reliably.</span></span> <span data-ttu-id="6d76f-118">Pertanto, è consigliabile per le organizzazioni di grandi dimensioni, con più di 100 dispositivi K.</span><span class="sxs-lookup"><span data-stu-id="6d76f-118">Therefore, it is recommended for large organizations, with more than 100 K devices.</span></span> <span data-ttu-id="6d76f-119">Questa API estrae tutti i dati dell'organizzazione come file di download.</span><span class="sxs-lookup"><span data-stu-id="6d76f-119">This API pulls all data in your organization as download files.</span></span> <span data-ttu-id="6d76f-120">La risposta contiene URL per scaricare tutti i dati da Archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="6d76f-120">The response contains URLs to download all the data from Azure Storage.</span></span> <span data-ttu-id="6d76f-121">Questa API consente di scaricare tutti i dati da Archiviazione di Azure come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="6d76f-121">This API enables you to download all your data from Azure Storage as follows:</span></span>

  - <span data-ttu-id="6d76f-122">Chiama l'API per ottenere un elenco di URL di download con tutti i dati dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="6d76f-122">Call the API to get a list of download URLs with all your organization data.</span></span>

  - <span data-ttu-id="6d76f-123">Scarica tutti i file usando gli URL di download ed elabora i dati come vuoi.</span><span class="sxs-lookup"><span data-stu-id="6d76f-123">Download all the files using the download URLs and process the data as you like.</span></span>

<span data-ttu-id="6d76f-124">I dati raccolti (tramite _OData_ o _tramite file)_ sono lo snapshot corrente dello stato corrente e non contengono dati storici.</span><span class="sxs-lookup"><span data-stu-id="6d76f-124">Data that is collected (using either _OData_ or _via files_) is the current snapshot of the current state, and does not contain historic data.</span></span> <span data-ttu-id="6d76f-125">Per raccogliere i dati storici, i clienti devono salvare i dati nei propri archivi dati.</span><span class="sxs-lookup"><span data-stu-id="6d76f-125">In order to collect historic data, customers must save the data in their own data storages.</span></span>

> [!Note]
>
> <span data-ttu-id="6d76f-126">Se non diversamente indicato, tutti i metodi di valutazione dell'esportazione elencati sono **_l'esportazione_** completa e per dispositivo **_(noto_** anche **_come per dispositivo)._**</span><span class="sxs-lookup"><span data-stu-id="6d76f-126">Unless indicated otherwise, all export assessment methods listed are **_full export_** and **_by device_** (also referred to as **_per device_**).</span></span>

## <a name="1-export-software-vulnerabilities-assessment-odata"></a><span data-ttu-id="6d76f-127">1. Esportare la valutazione delle vulnerabilità software (OData)</span><span class="sxs-lookup"><span data-stu-id="6d76f-127">1. Export software vulnerabilities assessment (OData)</span></span>

### <a name="11-api-method-description"></a><span data-ttu-id="6d76f-128">1.1 Descrizione del metodo API</span><span class="sxs-lookup"><span data-stu-id="6d76f-128">1.1 API method description</span></span>

<span data-ttu-id="6d76f-129">Questa risposta API contiene tutti i dati del software installato per dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6d76f-129">This API response contains all the data of installed software per device.</span></span> <span data-ttu-id="6d76f-130">Restituisce una tabella con una voce per ogni combinazione univoca di DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.</span><span class="sxs-lookup"><span data-stu-id="6d76f-130">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.</span></span>

#### <a name="limitations"></a><span data-ttu-id="6d76f-131">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="6d76f-131">Limitations</span></span>

>- <span data-ttu-id="6d76f-132">La dimensione massima della pagina è 200.000.</span><span class="sxs-lookup"><span data-stu-id="6d76f-132">Maximum page size is 200,000.</span></span>
>
>- <span data-ttu-id="6d76f-133">I limiti di frequenza per questa API sono 30 chiamate al minuto e 1000 chiamate all'ora.</span><span class="sxs-lookup"><span data-stu-id="6d76f-133">Rate limitations for this API are 30 calls per minute and 1000 calls per hour.</span></span>

### <a name="12-permissions"></a><span data-ttu-id="6d76f-134">1.2 Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="6d76f-134">1.2 Permissions</span></span>

<span data-ttu-id="6d76f-135">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="6d76f-135">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="6d76f-136">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi Usare Le API di [Microsoft Defender per endpoint per i dettagli.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="6d76f-136">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="6d76f-137">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="6d76f-137">Permission type</span></span> | <span data-ttu-id="6d76f-138">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="6d76f-138">Permission</span></span> | <span data-ttu-id="6d76f-139">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="6d76f-139">Permission display name</span></span>
---|---|---
<span data-ttu-id="6d76f-140">Applicazione</span><span class="sxs-lookup"><span data-stu-id="6d76f-140">Application</span></span> | <span data-ttu-id="6d76f-141">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="6d76f-141">Vulnerability.Read.All</span></span> | <span data-ttu-id="6d76f-142">\'Leggere informazioni sulla vulnerabilità di Gestione minacce e vulnerabilità\'</span><span class="sxs-lookup"><span data-stu-id="6d76f-142">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="6d76f-143">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="6d76f-143">Delegated (work or school account)</span></span> | <span data-ttu-id="6d76f-144">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="6d76f-144">Vulnerability.Read</span></span> | <span data-ttu-id="6d76f-145">\'Leggere informazioni sulla vulnerabilità di Gestione minacce e vulnerabilità\'</span><span class="sxs-lookup"><span data-stu-id="6d76f-145">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="13-url"></a><span data-ttu-id="6d76f-146">1.3 URL</span><span class="sxs-lookup"><span data-stu-id="6d76f-146">1.3 URL</span></span>

```http
GET /api/machines/SoftwareVulnerabilitiesByMachine
```

### <a name="14-parameters"></a><span data-ttu-id="6d76f-147">1.4 Parametri</span><span class="sxs-lookup"><span data-stu-id="6d76f-147">1.4 Parameters</span></span>

- <span data-ttu-id="6d76f-148">pageSize (impostazione predefinita = 50.000): numero di risultati in risposta</span><span class="sxs-lookup"><span data-stu-id="6d76f-148">pageSize (default = 50,000) – number of results in response</span></span>
- <span data-ttu-id="6d76f-149">$top - Numero di risultati da restituire (non restituisce @odata.nextLink e pertanto non estrae tutti i dati)</span><span class="sxs-lookup"><span data-stu-id="6d76f-149">$top – number of results to return (doesn’t return @odata.nextLink and therefore doesn’t pull all the data)</span></span>

### <a name="15-properties"></a><span data-ttu-id="6d76f-150">1.5 Proprietà</span><span class="sxs-lookup"><span data-stu-id="6d76f-150">1.5 Properties</span></span>
>
>[!Note]
>
>- <span data-ttu-id="6d76f-151">Ogni record è di circa 1 KB di dati.</span><span class="sxs-lookup"><span data-stu-id="6d76f-151">Each record is approximately 1KB of data.</span></span> <span data-ttu-id="6d76f-152">È consigliabile prendere in considerazione questo parametro quando si sceglie il parametro pageSize corretto.</span><span class="sxs-lookup"><span data-stu-id="6d76f-152">You should take this into account when choosing the correct pageSize parameter for you.</span></span>
>
>- <span data-ttu-id="6d76f-153">Nella risposta potrebbero essere restituite alcune colonne aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="6d76f-153">Some additional columns might be returned in the response.</span></span> <span data-ttu-id="6d76f-154">Queste colonne sono temporanee e potrebbero essere rimosse, utilizzare solo le colonne documentate.</span><span class="sxs-lookup"><span data-stu-id="6d76f-154">These columns are temporary and might be removed, please use only the documented columns.</span></span>
>
>- <span data-ttu-id="6d76f-155">Le proprietà definite nella tabella seguente sono elencate in ordine alfabetico in base all'ID proprietà.</span><span class="sxs-lookup"><span data-stu-id="6d76f-155">The properties defined in the following table are listed alphabetically, by property ID.</span></span>  <span data-ttu-id="6d76f-156">Quando si esegue questa API, l'output risultante non verrà necessariamente restituito nello stesso ordine elencato in questa tabella.</span><span class="sxs-lookup"><span data-stu-id="6d76f-156">When running this API, the resulting output will not necessarily be returned in the same order listed in this table.</span></span>
>

<span data-ttu-id="6d76f-157">Proprietà (ID)</span><span class="sxs-lookup"><span data-stu-id="6d76f-157">Property (ID)</span></span> | <span data-ttu-id="6d76f-158">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="6d76f-158">Data type</span></span> | <span data-ttu-id="6d76f-159">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6d76f-159">Description</span></span> | <span data-ttu-id="6d76f-160">Esempio di valore restituito</span><span class="sxs-lookup"><span data-stu-id="6d76f-160">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="6d76f-161">CveId</span><span class="sxs-lookup"><span data-stu-id="6d76f-161">CveId</span></span> | <span data-ttu-id="6d76f-162">stringa</span><span class="sxs-lookup"><span data-stu-id="6d76f-162">string</span></span> | <span data-ttu-id="6d76f-163">Identificatore univoco assegnato alla vulnerabilità della sicurezza nel sistema CVE (Common Vulnerabilities and Exposures).</span><span class="sxs-lookup"><span data-stu-id="6d76f-163">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system.</span></span> | <span data-ttu-id="6d76f-164">CVE-2020-15992</span><span class="sxs-lookup"><span data-stu-id="6d76f-164">CVE-2020-15992</span></span>
<span data-ttu-id="6d76f-165">CvssScore</span><span class="sxs-lookup"><span data-stu-id="6d76f-165">CvssScore</span></span> | <span data-ttu-id="6d76f-166">stringa</span><span class="sxs-lookup"><span data-stu-id="6d76f-166">string</span></span> | <span data-ttu-id="6d76f-167">Punteggio CVSS del CVE.</span><span class="sxs-lookup"><span data-stu-id="6d76f-167">The CVSS score of the CVE.</span></span> | <span data-ttu-id="6d76f-168">6.2</span><span class="sxs-lookup"><span data-stu-id="6d76f-168">6.2</span></span>
<span data-ttu-id="6d76f-169">DeviceId</span><span class="sxs-lookup"><span data-stu-id="6d76f-169">DeviceId</span></span> | <span data-ttu-id="6d76f-170">stringa</span><span class="sxs-lookup"><span data-stu-id="6d76f-170">string</span></span> | <span data-ttu-id="6d76f-171">Identificatore univoco del dispositivo nel servizio.</span><span class="sxs-lookup"><span data-stu-id="6d76f-171">Unique identifier for the device in the service.</span></span> | <span data-ttu-id="6d76f-172">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span><span class="sxs-lookup"><span data-stu-id="6d76f-172">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span></span>
<span data-ttu-id="6d76f-173">DeviceName</span><span class="sxs-lookup"><span data-stu-id="6d76f-173">DeviceName</span></span> | <span data-ttu-id="6d76f-174">stringa</span><span class="sxs-lookup"><span data-stu-id="6d76f-174">string</span></span> | <span data-ttu-id="6d76f-175">Nome di dominio completo (FQDN) del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6d76f-175">Fully qualified domain name (FQDN) of the device.</span></span> | <span data-ttu-id="6d76f-176">johnlaptop.europe.contoso.com</span><span class="sxs-lookup"><span data-stu-id="6d76f-176">johnlaptop.europe.contoso.com</span></span>
<span data-ttu-id="6d76f-177">DiskPaths</span><span class="sxs-lookup"><span data-stu-id="6d76f-177">DiskPaths</span></span>  | <span data-ttu-id="6d76f-178">Stringa \[ matrice\]</span><span class="sxs-lookup"><span data-stu-id="6d76f-178">Array\[string\]</span></span> | <span data-ttu-id="6d76f-179">Prova su disco che il prodotto è installato nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6d76f-179">Disk evidence that the product is installed on the device.</span></span> | <span data-ttu-id="6d76f-180">[ "C:\Programmi (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]</span><span class="sxs-lookup"><span data-stu-id="6d76f-180">[ "C:\Program Files (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]</span></span>
<span data-ttu-id="6d76f-181">ExploitabilityLevel</span><span class="sxs-lookup"><span data-stu-id="6d76f-181">ExploitabilityLevel</span></span> | <span data-ttu-id="6d76f-182">stringa</span><span class="sxs-lookup"><span data-stu-id="6d76f-182">string</span></span> | <span data-ttu-id="6d76f-183">Livello di sfruttabilità di questa vulnerabilità (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)</span><span class="sxs-lookup"><span data-stu-id="6d76f-183">The exploitability level of this vulnerability (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)</span></span> | <span data-ttu-id="6d76f-184">ExploitIsInKit</span><span class="sxs-lookup"><span data-stu-id="6d76f-184">ExploitIsInKit</span></span>
<span data-ttu-id="6d76f-185">FirstSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="6d76f-185">FirstSeenTimestamp</span></span> | <span data-ttu-id="6d76f-186">stringa</span><span class="sxs-lookup"><span data-stu-id="6d76f-186">string</span></span> | <span data-ttu-id="6d76f-187">La prima volta che il CVE di questo prodotto è stato visualizzato nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6d76f-187">First time the CVE of this product was seen on the device.</span></span> | <span data-ttu-id="6d76f-188">2020-11-03 10:13:34.8476880</span><span class="sxs-lookup"><span data-stu-id="6d76f-188">2020-11-03 10:13:34.8476880</span></span>
<span data-ttu-id="6d76f-189">Id</span><span class="sxs-lookup"><span data-stu-id="6d76f-189">Id</span></span> | <span data-ttu-id="6d76f-190">stringa</span><span class="sxs-lookup"><span data-stu-id="6d76f-190">string</span></span> | <span data-ttu-id="6d76f-191">Identificatore univoco del record.</span><span class="sxs-lookup"><span data-stu-id="6d76f-191">Unique identifier for the record.</span></span> | <span data-ttu-id="6d76f-192">123ABG55_573AG&mnp!</span><span class="sxs-lookup"><span data-stu-id="6d76f-192">123ABG55_573AG&mnp!</span></span>
<span data-ttu-id="6d76f-193">LastSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="6d76f-193">LastSeenTimestamp</span></span> | <span data-ttu-id="6d76f-194">stringa</span><span class="sxs-lookup"><span data-stu-id="6d76f-194">string</span></span> | <span data-ttu-id="6d76f-195">Ultima volta che il CVE è stato visualizzato nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6d76f-195">Last time the CVE was seen on the device.</span></span> | <span data-ttu-id="6d76f-196">2020-11-03 10:13:34.8476880</span><span class="sxs-lookup"><span data-stu-id="6d76f-196">2020-11-03 10:13:34.8476880</span></span>
<span data-ttu-id="6d76f-197">OSPlatform</span><span class="sxs-lookup"><span data-stu-id="6d76f-197">OSPlatform</span></span> | <span data-ttu-id="6d76f-198">stringa</span><span class="sxs-lookup"><span data-stu-id="6d76f-198">string</span></span> | <span data-ttu-id="6d76f-199">Piattaforma del sistema operativo in esecuzione nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6d76f-199">Platform of the operating system running on the device.</span></span> <span data-ttu-id="6d76f-200">Ciò indica specifici sistemi operativi, incluse variazioni all'interno della stessa famiglia di prodotti, come Windows 10 e Windows 7.</span><span class="sxs-lookup"><span data-stu-id="6d76f-200">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> <span data-ttu-id="6d76f-201">Per informazioni dettagliate, vedere tvm supported operating systems and platforms.</span><span class="sxs-lookup"><span data-stu-id="6d76f-201">See tvm supported operating systems and platforms for details.</span></span> | <span data-ttu-id="6d76f-202">Windows10</span><span class="sxs-lookup"><span data-stu-id="6d76f-202">Windows10</span></span>
<span data-ttu-id="6d76f-203">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="6d76f-203">RbacGroupName</span></span>  | <span data-ttu-id="6d76f-204">stringa</span><span class="sxs-lookup"><span data-stu-id="6d76f-204">string</span></span> | <span data-ttu-id="6d76f-205">Gruppo RBAC (Role-Based Access Control).</span><span class="sxs-lookup"><span data-stu-id="6d76f-205">The role-based access control (RBAC) group.</span></span> <span data-ttu-id="6d76f-206">Se questo dispositivo non è assegnato ad alcun gruppo RBAC, il valore sarà "Non assegnato".</span><span class="sxs-lookup"><span data-stu-id="6d76f-206">If this device is not assigned to any RBAC group, the value will be “Unassigned.”</span></span> <span data-ttu-id="6d76f-207">Se l'organizzazione non contiene gruppi RBAC, il valore sarà "None".</span><span class="sxs-lookup"><span data-stu-id="6d76f-207">If the organization doesn’t contain any RBAC groups, the value will be “None.”</span></span> | <span data-ttu-id="6d76f-208">Server</span><span class="sxs-lookup"><span data-stu-id="6d76f-208">Servers</span></span>
<span data-ttu-id="6d76f-209">RecommendationReference</span><span class="sxs-lookup"><span data-stu-id="6d76f-209">RecommendationReference</span></span> | <span data-ttu-id="6d76f-210">stringa</span><span class="sxs-lookup"><span data-stu-id="6d76f-210">string</span></span> | <span data-ttu-id="6d76f-211">Riferimento all'ID suggerimento relativo a questo software.</span><span class="sxs-lookup"><span data-stu-id="6d76f-211">A reference to the recommendation ID related to this software.</span></span> | <span data-ttu-id="6d76f-212">va-_-microsoft-_-silverlight</span><span class="sxs-lookup"><span data-stu-id="6d76f-212">va-_-microsoft-_-silverlight</span></span>
<span data-ttu-id="6d76f-213">RecommendedSecurityUpdate (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="6d76f-213">RecommendedSecurityUpdate (optional)</span></span> | <span data-ttu-id="6d76f-214">stringa</span><span class="sxs-lookup"><span data-stu-id="6d76f-214">string</span></span> | <span data-ttu-id="6d76f-215">Nome o descrizione dell'aggiornamento della sicurezza fornito dal fornitore del software per risolvere la vulnerabilità.</span><span class="sxs-lookup"><span data-stu-id="6d76f-215">Name or description of the security update provided by the software vendor to address the vulnerability.</span></span> | <span data-ttu-id="6d76f-216">Aggiornamenti della sicurezza di aprile 2020</span><span class="sxs-lookup"><span data-stu-id="6d76f-216">April 2020 Security Updates</span></span>
<span data-ttu-id="6d76f-217">RecommendedSecurityUpdateId (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="6d76f-217">RecommendedSecurityUpdateId (optional)</span></span> | <span data-ttu-id="6d76f-218">stringa</span><span class="sxs-lookup"><span data-stu-id="6d76f-218">string</span></span> | <span data-ttu-id="6d76f-219">Identificatore degli aggiornamenti della sicurezza applicabili o dell'identificatore per gli articoli della Knowledge Base (KB) corrispondenti</span><span class="sxs-lookup"><span data-stu-id="6d76f-219">Identifier of the applicable security updates or identifier for the corresponding guidance or knowledge base (KB) articles</span></span> | <span data-ttu-id="6d76f-220">4550961</span><span class="sxs-lookup"><span data-stu-id="6d76f-220">4550961</span></span>
<span data-ttu-id="6d76f-221">RegistryPaths</span><span class="sxs-lookup"><span data-stu-id="6d76f-221">RegistryPaths</span></span>  | <span data-ttu-id="6d76f-222">Stringa \[ matrice\]</span><span class="sxs-lookup"><span data-stu-id="6d76f-222">Array\[string\]</span></span> | <span data-ttu-id="6d76f-223">Prova del Registro di sistema che il prodotto è installato nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6d76f-223">Registry evidence that the product is installed in the device.</span></span> | <span data-ttu-id="6d76f-224">[ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\MicrosoftSilverlight" ]</span><span class="sxs-lookup"><span data-stu-id="6d76f-224">[ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\MicrosoftSilverlight" ]</span></span>
<span data-ttu-id="6d76f-225">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="6d76f-225">SoftwareName</span></span> | <span data-ttu-id="6d76f-226">stringa</span><span class="sxs-lookup"><span data-stu-id="6d76f-226">string</span></span> | <span data-ttu-id="6d76f-227">Nome del prodotto software.</span><span class="sxs-lookup"><span data-stu-id="6d76f-227">Name of the software product.</span></span> | <span data-ttu-id="6d76f-228">chrome</span><span class="sxs-lookup"><span data-stu-id="6d76f-228">chrome</span></span>
<span data-ttu-id="6d76f-229">SoftwareVendor</span><span class="sxs-lookup"><span data-stu-id="6d76f-229">SoftwareVendor</span></span> | <span data-ttu-id="6d76f-230">stringa</span><span class="sxs-lookup"><span data-stu-id="6d76f-230">string</span></span> | <span data-ttu-id="6d76f-231">Nome del fornitore del software.</span><span class="sxs-lookup"><span data-stu-id="6d76f-231">Name of the software vendor.</span></span> | <span data-ttu-id="6d76f-232">google</span><span class="sxs-lookup"><span data-stu-id="6d76f-232">google</span></span>
<span data-ttu-id="6d76f-233">SoftwareVersion</span><span class="sxs-lookup"><span data-stu-id="6d76f-233">SoftwareVersion</span></span> | <span data-ttu-id="6d76f-234">stringa</span><span class="sxs-lookup"><span data-stu-id="6d76f-234">string</span></span> | <span data-ttu-id="6d76f-235">Numero di versione del prodotto software.</span><span class="sxs-lookup"><span data-stu-id="6d76f-235">Version number of the software product.</span></span> | <span data-ttu-id="6d76f-236">81.0.4044.138</span><span class="sxs-lookup"><span data-stu-id="6d76f-236">81.0.4044.138</span></span>
<span data-ttu-id="6d76f-237">VulnerabilitySeverityLevel</span><span class="sxs-lookup"><span data-stu-id="6d76f-237">VulnerabilitySeverityLevel</span></span>  | <span data-ttu-id="6d76f-238">stringa</span><span class="sxs-lookup"><span data-stu-id="6d76f-238">string</span></span> | <span data-ttu-id="6d76f-239">Livello di gravità assegnato alla vulnerabilità della sicurezza in base al punteggio CVSS e ai fattori dinamici influenzati dal panorama delle minacce.</span><span class="sxs-lookup"><span data-stu-id="6d76f-239">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape.</span></span> | <span data-ttu-id="6d76f-240">Medio</span><span class="sxs-lookup"><span data-stu-id="6d76f-240">Medium</span></span>

### <a name="16-examples"></a><span data-ttu-id="6d76f-241">1.6 Esempi</span><span class="sxs-lookup"><span data-stu-id="6d76f-241">1.6 Examples</span></span>

#### <a name="161-request-example"></a><span data-ttu-id="6d76f-242">1.6.1 Esempio di richiesta</span><span class="sxs-lookup"><span data-stu-id="6d76f-242">1.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilitiesByMachine?pageSize=5
```

#### <a name="162-response-example"></a><span data-ttu-id="6d76f-243">1.6.2 Esempio di risposta</span><span class="sxs-lookup"><span data-stu-id="6d76f-243">1.6.2 Response example</span></span>

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

## <a name="2-export-software-vulnerabilities-assessment-via-files"></a><span data-ttu-id="6d76f-244">2. Esportare la valutazione delle vulnerabilità software (tramite file)</span><span class="sxs-lookup"><span data-stu-id="6d76f-244">2. Export software vulnerabilities assessment (via files)</span></span>

### <a name="21-api-method-description"></a><span data-ttu-id="6d76f-245">2.1 Descrizione del metodo API</span><span class="sxs-lookup"><span data-stu-id="6d76f-245">2.1 API method description</span></span>

<span data-ttu-id="6d76f-246">Questa risposta API contiene tutti i dati del software installato per dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6d76f-246">This API response contains all the data of installed software per device.</span></span> <span data-ttu-id="6d76f-247">Restituisce una tabella con una voce per ogni combinazione univoca di DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.</span><span class="sxs-lookup"><span data-stu-id="6d76f-247">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.</span></span>

#### <a name="212-limitations"></a><span data-ttu-id="6d76f-248">2.1.2 Limitazioni</span><span class="sxs-lookup"><span data-stu-id="6d76f-248">2.1.2 Limitations</span></span>

<span data-ttu-id="6d76f-249">I limiti di frequenza per questa API sono 5 chiamate al minuto e 20 chiamate all'ora.</span><span class="sxs-lookup"><span data-stu-id="6d76f-249">Rate limitations for this API are 5 calls per minute and 20 calls per hour.</span></span>

### <a name="22-permissions"></a><span data-ttu-id="6d76f-250">2.2 Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="6d76f-250">2.2 Permissions</span></span>

<span data-ttu-id="6d76f-251">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="6d76f-251">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="6d76f-252">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi Usare Le API di [Microsoft Defender per endpoint per i dettagli.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="6d76f-252">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details](apis-intro.md).</span></span>

<span data-ttu-id="6d76f-253">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="6d76f-253">Permission type</span></span> | <span data-ttu-id="6d76f-254">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="6d76f-254">Permission</span></span> | <span data-ttu-id="6d76f-255">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="6d76f-255">Permission display name</span></span>
---|---|---
<span data-ttu-id="6d76f-256">Applicazione</span><span class="sxs-lookup"><span data-stu-id="6d76f-256">Application</span></span> | <span data-ttu-id="6d76f-257">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="6d76f-257">Vulnerability.Read.All</span></span> | <span data-ttu-id="6d76f-258">\'Leggere informazioni sulla vulnerabilità di Gestione minacce e vulnerabilità\'</span><span class="sxs-lookup"><span data-stu-id="6d76f-258">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="6d76f-259">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="6d76f-259">Delegated (work or school account)</span></span> | <span data-ttu-id="6d76f-260">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="6d76f-260">Vulnerability.Read</span></span> | <span data-ttu-id="6d76f-261">\'Leggere informazioni sulla vulnerabilità di Gestione minacce e vulnerabilità\'</span><span class="sxs-lookup"><span data-stu-id="6d76f-261">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="23-url"></a><span data-ttu-id="6d76f-262">2.3 URL</span><span class="sxs-lookup"><span data-stu-id="6d76f-262">2.3 URL</span></span>

```http
GET /api/machines/SoftwareVulnerabilitiesExport
```

### <a name="24-parameters"></a><span data-ttu-id="6d76f-263">2.4 Parametri</span><span class="sxs-lookup"><span data-stu-id="6d76f-263">2.4 Parameters</span></span>

- <span data-ttu-id="6d76f-264">sasValidHours: numero di ore per cui saranno validi gli URL di download (massimo 24 ore)</span><span class="sxs-lookup"><span data-stu-id="6d76f-264">sasValidHours – The number of hours that the download URLs will be valid for (Maximum 24 hours)</span></span>

### <a name="25-properties"></a><span data-ttu-id="6d76f-265">2.5 Proprietà</span><span class="sxs-lookup"><span data-stu-id="6d76f-265">2.5 Properties</span></span>

>[!Note]
>
>- <span data-ttu-id="6d76f-266">I file sono compressi con gzip & in formato Json multilinea.</span><span class="sxs-lookup"><span data-stu-id="6d76f-266">The files are gzip compressed & in multiline Json format.</span></span>
>
>- <span data-ttu-id="6d76f-267">Gli URL di download sono validi solo per 3 ore. in caso contrario, è possibile utilizzare il parametro .</span><span class="sxs-lookup"><span data-stu-id="6d76f-267">The download URLs are only valid for 3 hours; otherwise you can use the parameter.</span></span>
>
>- <span data-ttu-id="6d76f-268">Per ottenere la massima velocità di download dei dati, puoi assicurarti di eseguire il download dalla stessa area di Azure in cui si trovano i dati.</span><span class="sxs-lookup"><span data-stu-id="6d76f-268">For maximum download speed of your data, you can make sure you are downloading from the same Azure region that your data resides.</span></span>
>

>[!Note]
>
>- <span data-ttu-id="6d76f-269">Ogni record è di circa 1 KB di dati.</span><span class="sxs-lookup"><span data-stu-id="6d76f-269">Each record is approximately 1KB of data.</span></span> <span data-ttu-id="6d76f-270">È consigliabile prendere in considerazione questo parametro quando si sceglie il parametro pageSize corretto.</span><span class="sxs-lookup"><span data-stu-id="6d76f-270">You should take this into account when choosing the correct pageSize parameter for you.</span></span>
>
>- <span data-ttu-id="6d76f-271">Nella risposta potrebbero essere restituite alcune colonne aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="6d76f-271">Some additional columns might be returned in the response.</span></span> <span data-ttu-id="6d76f-272">Queste colonne sono temporanee e potrebbero essere rimosse, utilizzare solo le colonne documentate.</span><span class="sxs-lookup"><span data-stu-id="6d76f-272">These columns are temporary and might be removed, please use only the documented columns.</span></span>
>

<span data-ttu-id="6d76f-273">Proprietà (ID)</span><span class="sxs-lookup"><span data-stu-id="6d76f-273">Property (ID)</span></span> | <span data-ttu-id="6d76f-274">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="6d76f-274">Data type</span></span> | <span data-ttu-id="6d76f-275">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6d76f-275">Description</span></span> | <span data-ttu-id="6d76f-276">Esempio di valore restituito</span><span class="sxs-lookup"><span data-stu-id="6d76f-276">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="6d76f-277">Esportare file</span><span class="sxs-lookup"><span data-stu-id="6d76f-277">Export files</span></span> | <span data-ttu-id="6d76f-278">stringa \[ di matrice\]</span><span class="sxs-lookup"><span data-stu-id="6d76f-278">array\[string\]</span></span>  | <span data-ttu-id="6d76f-279">Elenco di URL di download per i file che tengono lo snapshot corrente dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="6d76f-279">A list of download URLs for files holding the current snapshot of the organization.</span></span> | <span data-ttu-id="6d76f-280">[  “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2”  ]</span><span class="sxs-lookup"><span data-stu-id="6d76f-280">[  “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2”  ]</span></span>
<span data-ttu-id="6d76f-281">GeneratedTime</span><span class="sxs-lookup"><span data-stu-id="6d76f-281">GeneratedTime</span></span> | <span data-ttu-id="6d76f-282">stringa</span><span class="sxs-lookup"><span data-stu-id="6d76f-282">string</span></span> | <span data-ttu-id="6d76f-283">Ora in cui è stata generata l'esportazione.</span><span class="sxs-lookup"><span data-stu-id="6d76f-283">The time that the export was generated.</span></span> | <span data-ttu-id="6d76f-284">2021-05-20T08:00:00Z</span><span class="sxs-lookup"><span data-stu-id="6d76f-284">2021-05-20T08:00:00Z</span></span>

### <a name="26-examples"></a><span data-ttu-id="6d76f-285">2.6 Esempi</span><span class="sxs-lookup"><span data-stu-id="6d76f-285">2.6 Examples</span></span>

#### <a name="261-request-example"></a><span data-ttu-id="6d76f-286">2.6.1 Esempio di richiesta</span><span class="sxs-lookup"><span data-stu-id="6d76f-286">2.6.1 Request example</span></span>

```http
GET https://api-us.securitycenter.contoso.com/api/machines/SoftwareVulnerabilitiesExport
```

#### <a name="262-response-example"></a><span data-ttu-id="6d76f-287">2.6.2 Esempio di risposta</span><span class="sxs-lookup"><span data-stu-id="6d76f-287">2.6.2 Response example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="6d76f-288">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6d76f-288">See also</span></span>

- [<span data-ttu-id="6d76f-289">Esportare proprietà e metodi di valutazione per dispositivo</span><span class="sxs-lookup"><span data-stu-id="6d76f-289">Export assessment methods and properties per device</span></span>](get-assessmnt-1methods-properties.md)

- [<span data-ttu-id="6d76f-290">Esportare la valutazione della configurazione sicura per dispositivo</span><span class="sxs-lookup"><span data-stu-id="6d76f-290">Export secure configuration assessment per device</span></span>](get-assessmnt-secure-cfg.md)

- [<span data-ttu-id="6d76f-291">Esportare la valutazione dell'inventario software per dispositivo</span><span class="sxs-lookup"><span data-stu-id="6d76f-291">Export software inventory assessment per device</span></span>](get-assessmnt-software-inventory.md)

<span data-ttu-id="6d76f-292">Altre informazioni correlate</span><span class="sxs-lookup"><span data-stu-id="6d76f-292">Other related</span></span>

- [<span data-ttu-id="6d76f-293">Rischio basato sulle minacce & gestione delle vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="6d76f-293">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="6d76f-294">Vulnerabilità nell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="6d76f-294">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
