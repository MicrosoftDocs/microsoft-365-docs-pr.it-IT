---
title: Esportare la valutazione della configurazione sicura per dispositivo
description: Restituisce una voce per ogni combinazione univoca di DeviceId, ConfigurationId.
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
ms.openlocfilehash: ad8b2030da4fb4815eb71ca53fb2dbac67a05d79
ms.sourcegitcommit: bc64d9f619259bd0a94e43a9010aae5cffb4d6c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2021
ms.locfileid: "53022391"
---
# <a name="export-secure-configuration-assessment-per-device"></a><span data-ttu-id="83a18-104">Esportare la valutazione della configurazione sicura per dispositivo</span><span class="sxs-lookup"><span data-stu-id="83a18-104">Export secure configuration assessment per device</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="83a18-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="83a18-105">**Applies to:**</span></span>

- [<span data-ttu-id="83a18-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="83a18-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="83a18-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="83a18-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="83a18-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="83a18-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="83a18-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="83a18-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

>
<span data-ttu-id="83a18-110">Restituisce tutte le configurazioni e il relativo stato, in base al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="83a18-110">Returns all of the configurations and their status, on a per-device basis.</span></span>

<span data-ttu-id="83a18-111">Esistono diverse chiamate API per ottenere diversi tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="83a18-111">There are different API calls to get different types of data.</span></span> <span data-ttu-id="83a18-112">Poiché la quantità di dati può essere di grandi dimensioni, è possibile recuperarla in due modi:</span><span class="sxs-lookup"><span data-stu-id="83a18-112">Because the amount of data can be large, there are two ways it can be retrieved:</span></span>

- <span data-ttu-id="83a18-113">[Esportare la risposta **JSON** per la valutazione della](#1-export-secure-configuration-assessment-json-response)configurazione sicura : l'API estrae tutti i dati nell'organizzazione come risposte Json.</span><span class="sxs-lookup"><span data-stu-id="83a18-113">[Export secure configuration assessment **JSON response**](#1-export-secure-configuration-assessment-json-response):  The API pulls all data in your organization as Json responses.</span></span> <span data-ttu-id="83a18-114">Questo metodo è ideale _per organizzazioni di piccole dimensioni con meno di 100 K dispositivi._</span><span class="sxs-lookup"><span data-stu-id="83a18-114">This method is best for _small organizations with less than 100-K devices_.</span></span> <span data-ttu-id="83a18-115">La risposta viene impaginata, quindi è possibile utilizzare il campo \@ odata.nextLink dalla risposta per recuperare i risultati successivi.</span><span class="sxs-lookup"><span data-stu-id="83a18-115">The response is paginated, so you can use the \@odata.nextLink field from the response to fetch the next results.</span></span>

- <span data-ttu-id="83a18-116">[Esportare la valutazione della configurazione sicura tramite **file:**](#2-export-secure-configuration-assessment-via-files)questa soluzione API consente di estrarre grandi quantità di dati in modo più rapido e affidabile.</span><span class="sxs-lookup"><span data-stu-id="83a18-116">[Export secure configuration assessment **via files**](#2-export-secure-configuration-assessment-via-files): This API solution enables pulling larger amounts of data faster and more reliably.</span></span> <span data-ttu-id="83a18-117">Pertanto, è consigliabile per le organizzazioni di grandi dimensioni, con più di 100 dispositivi K.</span><span class="sxs-lookup"><span data-stu-id="83a18-117">Therefore, it is recommended for large organizations, with more than 100-K devices.</span></span> <span data-ttu-id="83a18-118">Questa API estrae tutti i dati dell'organizzazione come file di download.</span><span class="sxs-lookup"><span data-stu-id="83a18-118">This API pulls all data in your organization as download files.</span></span> <span data-ttu-id="83a18-119">La risposta contiene URL per scaricare tutti i dati da Archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="83a18-119">The response contains URLs to download all the data from Azure Storage.</span></span> <span data-ttu-id="83a18-120">Questa API consente di scaricare tutti i dati da Archiviazione di Azure come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="83a18-120">This API enables you to download all your data from Azure Storage as follows:</span></span>

  - <span data-ttu-id="83a18-121">Chiama l'API per ottenere un elenco di URL di download con tutti i dati dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="83a18-121">Call the API to get a list of download URLs with all your organization data.</span></span>

  - <span data-ttu-id="83a18-122">Scarica tutti i file usando gli URL di download ed elabora i dati come vuoi.</span><span class="sxs-lookup"><span data-stu-id="83a18-122">Download all the files using the download URLs and process the data as you like.</span></span>

<span data-ttu-id="83a18-123">I dati raccolti (tramite _OData_ o _tramite file)_ sono lo snapshot corrente dello stato corrente e non contengono dati storici.</span><span class="sxs-lookup"><span data-stu-id="83a18-123">Data that is collected (using either _OData_ or _via files_) is the current snapshot of the current state, and does not contain historic data.</span></span> <span data-ttu-id="83a18-124">Per raccogliere i dati storici, i clienti devono salvare i dati nei propri archivi dati.</span><span class="sxs-lookup"><span data-stu-id="83a18-124">In order to collect historic data, customers must save the data in their own data storages.</span></span>

> [!Note]
>
> <span data-ttu-id="83a18-125">Se non diversamente indicato, tutti i metodi di valutazione dell'esportazione elencati sono **_l'esportazione_** completa e per dispositivo **_(noto_** anche **_come per dispositivo)._**</span><span class="sxs-lookup"><span data-stu-id="83a18-125">Unless indicated otherwise, all export assessment methods listed are **_full export_** and **_by device_** (also referred to as **_per device_**).</span></span>

## <a name="1-export-secure-configuration-assessment-json-response"></a><span data-ttu-id="83a18-126">1. Esportare la valutazione della configurazione sicura (risposta JSON)</span><span class="sxs-lookup"><span data-stu-id="83a18-126">1. Export secure configuration assessment (JSON response)</span></span>

### <a name="11-api-method-description"></a><span data-ttu-id="83a18-127">1.1 Descrizione del metodo API</span><span class="sxs-lookup"><span data-stu-id="83a18-127">1.1 API method description</span></span>

<span data-ttu-id="83a18-128">Questa risposta API contiene la valutazione della configurazione sicura nei dispositivi esposti e restituisce una voce per ogni combinazione univoca di DeviceId, ConfigurationId.</span><span class="sxs-lookup"><span data-stu-id="83a18-128">This API response contains the Secure Configuration Assessment on your exposed devices, and returns an entry for every unique combination of DeviceId, ConfigurationId.</span></span>

#### <a name="111-limitations"></a><span data-ttu-id="83a18-129">1.1.1 Limitazioni</span><span class="sxs-lookup"><span data-stu-id="83a18-129">1.1.1 Limitations</span></span>

- <span data-ttu-id="83a18-130">La dimensione massima della pagina è 200.000.</span><span class="sxs-lookup"><span data-stu-id="83a18-130">Maximum page size is 200,000.</span></span>

- <span data-ttu-id="83a18-131">I limiti di frequenza per questa API sono 30 chiamate al minuto e 1000 chiamate all'ora.</span><span class="sxs-lookup"><span data-stu-id="83a18-131">Rate limitations for this API are 30 calls per minute and 1000 calls per hour.</span></span>

### <a name="12-permissions"></a><span data-ttu-id="83a18-132">1.2 Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="83a18-132">1.2 Permissions</span></span>

<span data-ttu-id="83a18-133">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="83a18-133">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="83a18-134">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi Usare Le API di [Microsoft Defender per endpoint](apis-intro.md) per i dettagli.</span><span class="sxs-lookup"><span data-stu-id="83a18-134">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="83a18-135">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="83a18-135">Permission type</span></span> | <span data-ttu-id="83a18-136">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="83a18-136">Permission</span></span> | <span data-ttu-id="83a18-137">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="83a18-137">Permission display name</span></span>
---|---|---
<span data-ttu-id="83a18-138">Applicazione</span><span class="sxs-lookup"><span data-stu-id="83a18-138">Application</span></span> | <span data-ttu-id="83a18-139">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="83a18-139">Vulnerability.Read.All</span></span> | <span data-ttu-id="83a18-140">\'Leggere informazioni sulla vulnerabilità di Gestione minacce e vulnerabilità\'</span><span class="sxs-lookup"><span data-stu-id="83a18-140">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="83a18-141">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="83a18-141">Delegated (work or school account)</span></span> | <span data-ttu-id="83a18-142">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="83a18-142">Vulnerability.Read</span></span> | <span data-ttu-id="83a18-143">\'Leggere informazioni sulla vulnerabilità di Gestione minacce e vulnerabilità\'</span><span class="sxs-lookup"><span data-stu-id="83a18-143">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="13-url"></a><span data-ttu-id="83a18-144">1.3 URL</span><span class="sxs-lookup"><span data-stu-id="83a18-144">1.3 URL</span></span>

```http
GET /api/machines/SecureConfigurationsAssessmentByMachine
```

### <a name="14-parameters"></a><span data-ttu-id="83a18-145">1.4 Parametri</span><span class="sxs-lookup"><span data-stu-id="83a18-145">1.4 Parameters</span></span>

- <span data-ttu-id="83a18-146">pageSize \( default = 50.000 \) – numero di risultati in risposta</span><span class="sxs-lookup"><span data-stu-id="83a18-146">pageSize \(default = 50,000\) – number of results in response</span></span>

- <span data-ttu-id="83a18-147">\$top : il numero di risultati da restituire non \( restituisce \@ odata.nextLink e pertanto non estrae tutti i dati\)</span><span class="sxs-lookup"><span data-stu-id="83a18-147">\$top – number of results to return \(doesn’t return \@odata.nextLink and therefore doesn’t pull all the data\)</span></span>

### <a name="15-properties"></a><span data-ttu-id="83a18-148">1.5 Proprietà</span><span class="sxs-lookup"><span data-stu-id="83a18-148">1.5 Properties</span></span>

>[!Note]
>
>- <span data-ttu-id="83a18-149">Le proprietà definite nella tabella seguente sono elencate in ordine alfabetico in base all'ID proprietà.</span><span class="sxs-lookup"><span data-stu-id="83a18-149">The properties defined in the following table are listed alphabetically, by property ID.</span></span>  <span data-ttu-id="83a18-150">Quando si esegue questa API, l'output risultante non verrà necessariamente restituito nello stesso ordine elencato in questa tabella.</span><span class="sxs-lookup"><span data-stu-id="83a18-150">When running this API, the resulting output will not necessarily be returned in the same order listed in this table.</span></span>
>
>- <span data-ttu-id="83a18-151">Nella risposta potrebbero essere restituite alcune colonne aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="83a18-151">Some additional columns might be returned in the response.</span></span> <span data-ttu-id="83a18-152">Queste colonne sono temporanee e potrebbero essere rimosse, utilizzare solo le colonne documentate.</span><span class="sxs-lookup"><span data-stu-id="83a18-152">These columns are temporary and might be removed, please use only the documented columns.</span></span>
>

<span data-ttu-id="83a18-153">Proprietà (ID)</span><span class="sxs-lookup"><span data-stu-id="83a18-153">Property (ID)</span></span> | <span data-ttu-id="83a18-154">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="83a18-154">Data type</span></span> | <span data-ttu-id="83a18-155">Descrizione</span><span class="sxs-lookup"><span data-stu-id="83a18-155">Description</span></span> | <span data-ttu-id="83a18-156">Esempio di valore restituito</span><span class="sxs-lookup"><span data-stu-id="83a18-156">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="83a18-157">ConfigurationCategory</span><span class="sxs-lookup"><span data-stu-id="83a18-157">ConfigurationCategory</span></span> | <span data-ttu-id="83a18-158">stringa</span><span class="sxs-lookup"><span data-stu-id="83a18-158">string</span></span> | <span data-ttu-id="83a18-159">Categoria o raggruppamento a cui appartiene la configurazione: Applicazione, Sistema operativo, Rete, Account, Controlli di sicurezza</span><span class="sxs-lookup"><span data-stu-id="83a18-159">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> | <span data-ttu-id="83a18-160">Controlli di sicurezza</span><span class="sxs-lookup"><span data-stu-id="83a18-160">Security controls</span></span>
<span data-ttu-id="83a18-161">ConfigurationId</span><span class="sxs-lookup"><span data-stu-id="83a18-161">ConfigurationId</span></span> | <span data-ttu-id="83a18-162">stringa</span><span class="sxs-lookup"><span data-stu-id="83a18-162">string</span></span> | <span data-ttu-id="83a18-163">Identificatore univoco di una configurazione specifica</span><span class="sxs-lookup"><span data-stu-id="83a18-163">Unique identifier for a specific configuration</span></span> | <span data-ttu-id="83a18-164">scid-10000</span><span class="sxs-lookup"><span data-stu-id="83a18-164">scid-10000</span></span>
<span data-ttu-id="83a18-165">ConfigurationImpact</span><span class="sxs-lookup"><span data-stu-id="83a18-165">ConfigurationImpact</span></span> | <span data-ttu-id="83a18-166">stringa</span><span class="sxs-lookup"><span data-stu-id="83a18-166">string</span></span> | <span data-ttu-id="83a18-167">Impatto nominale della configurazione sul punteggio di configurazione complessivo (1-10)</span><span class="sxs-lookup"><span data-stu-id="83a18-167">Rated impact of the configuration to the overall configuration score (1-10)</span></span> | <span data-ttu-id="83a18-168">9 </span><span class="sxs-lookup"><span data-stu-id="83a18-168">9</span></span>
<span data-ttu-id="83a18-169">ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="83a18-169">ConfigurationName</span></span> | <span data-ttu-id="83a18-170">stringa</span><span class="sxs-lookup"><span data-stu-id="83a18-170">string</span></span> | <span data-ttu-id="83a18-171">Nome visualizzato della configurazione</span><span class="sxs-lookup"><span data-stu-id="83a18-171">Display name of the configuration</span></span> | <span data-ttu-id="83a18-172">Aggiungere dispositivi a Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="83a18-172">Onboard devices to Microsoft Defender for Endpoint</span></span>
<span data-ttu-id="83a18-173">ConfigurationSubcategory</span><span class="sxs-lookup"><span data-stu-id="83a18-173">ConfigurationSubcategory</span></span> | <span data-ttu-id="83a18-174">stringa</span><span class="sxs-lookup"><span data-stu-id="83a18-174">string</span></span> | <span data-ttu-id="83a18-175">Sottocategoria o sottoraggruppamento a cui appartiene la configurazione.</span><span class="sxs-lookup"><span data-stu-id="83a18-175">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="83a18-176">In molti casi qui vengono descritte capacità o funzionalità specifiche.</span><span class="sxs-lookup"><span data-stu-id="83a18-176">In many cases, this describes specific capabilities or features.</span></span> | <span data-ttu-id="83a18-177">Dispositivi onboard</span><span class="sxs-lookup"><span data-stu-id="83a18-177">Onboard Devices</span></span>
<span data-ttu-id="83a18-178">DeviceId</span><span class="sxs-lookup"><span data-stu-id="83a18-178">DeviceId</span></span> | <span data-ttu-id="83a18-179">stringa</span><span class="sxs-lookup"><span data-stu-id="83a18-179">string</span></span> | <span data-ttu-id="83a18-180">Identificatore univoco del dispositivo nel servizio.</span><span class="sxs-lookup"><span data-stu-id="83a18-180">Unique identifier for the device in the service.</span></span> | <span data-ttu-id="83a18-181">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span><span class="sxs-lookup"><span data-stu-id="83a18-181">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span></span>
<span data-ttu-id="83a18-182">DeviceName</span><span class="sxs-lookup"><span data-stu-id="83a18-182">DeviceName</span></span> | <span data-ttu-id="83a18-183">stringa</span><span class="sxs-lookup"><span data-stu-id="83a18-183">string</span></span> | <span data-ttu-id="83a18-184">Nome di dominio completo (FQDN) del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="83a18-184">Fully qualified domain name (FQDN) of the device.</span></span> | <span data-ttu-id="83a18-185">johnlaptop.europe.contoso.com</span><span class="sxs-lookup"><span data-stu-id="83a18-185">johnlaptop.europe.contoso.com</span></span>
<span data-ttu-id="83a18-186">IsApplicable</span><span class="sxs-lookup"><span data-stu-id="83a18-186">IsApplicable</span></span> | <span data-ttu-id="83a18-187">bool</span><span class="sxs-lookup"><span data-stu-id="83a18-187">bool</span></span> | <span data-ttu-id="83a18-188">Indica se la configurazione o il criterio è applicabile</span><span class="sxs-lookup"><span data-stu-id="83a18-188">Indicates whether the configuration or policy is applicable</span></span> | <span data-ttu-id="83a18-189">true</span><span class="sxs-lookup"><span data-stu-id="83a18-189">true</span></span>
<span data-ttu-id="83a18-190">IsCompliant</span><span class="sxs-lookup"><span data-stu-id="83a18-190">IsCompliant</span></span> | <span data-ttu-id="83a18-191">bool</span><span class="sxs-lookup"><span data-stu-id="83a18-191">bool</span></span> | <span data-ttu-id="83a18-192">Indica se la configurazione o i criteri sono configurati correttamente</span><span class="sxs-lookup"><span data-stu-id="83a18-192">Indicates whether the configuration or policy is properly configured</span></span> | <span data-ttu-id="83a18-193">false</span><span class="sxs-lookup"><span data-stu-id="83a18-193">false</span></span>
<span data-ttu-id="83a18-194">IsExpectedUserImpact</span><span class="sxs-lookup"><span data-stu-id="83a18-194">IsExpectedUserImpact</span></span> | <span data-ttu-id="83a18-195">bool</span><span class="sxs-lookup"><span data-stu-id="83a18-195">bool</span></span> | <span data-ttu-id="83a18-196">Indica se ci sarà un impatto sull'utente se la configurazione verrà applicata</span><span class="sxs-lookup"><span data-stu-id="83a18-196">Indicates whether there will be user impact if the configuration will be applied</span></span> | <span data-ttu-id="83a18-197">true</span><span class="sxs-lookup"><span data-stu-id="83a18-197">true</span></span>
<span data-ttu-id="83a18-198">OSPlatform</span><span class="sxs-lookup"><span data-stu-id="83a18-198">OSPlatform</span></span> | <span data-ttu-id="83a18-199">stringa</span><span class="sxs-lookup"><span data-stu-id="83a18-199">string</span></span> | <span data-ttu-id="83a18-200">Piattaforma del sistema operativo in esecuzione nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="83a18-200">Platform of the operating system running on the device.</span></span> <span data-ttu-id="83a18-201">Ciò indica specifici sistemi operativi, incluse variazioni all'interno della stessa famiglia di prodotti, come Windows 10 e Windows 7.</span><span class="sxs-lookup"><span data-stu-id="83a18-201">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> <span data-ttu-id="83a18-202">Per informazioni dettagliate, vedere tvm supported operating systems and platforms.</span><span class="sxs-lookup"><span data-stu-id="83a18-202">See tvm supported operating systems and platforms for details.</span></span> | <span data-ttu-id="83a18-203">Windows10</span><span class="sxs-lookup"><span data-stu-id="83a18-203">Windows10</span></span>
<span data-ttu-id="83a18-204">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="83a18-204">RbacGroupName</span></span> | <span data-ttu-id="83a18-205">stringa</span><span class="sxs-lookup"><span data-stu-id="83a18-205">string</span></span> | <span data-ttu-id="83a18-206">Gruppo RBAC (Role-Based Access Control).</span><span class="sxs-lookup"><span data-stu-id="83a18-206">The role-based access control (RBAC) group.</span></span> <span data-ttu-id="83a18-207">Se questo dispositivo non è assegnato ad alcun gruppo RBAC, il valore sarà "Non assegnato".</span><span class="sxs-lookup"><span data-stu-id="83a18-207">If this device is not assigned to any RBAC group, the value will be “Unassigned.”</span></span> <span data-ttu-id="83a18-208">Se l'organizzazione non contiene gruppi RBAC, il valore sarà "None".</span><span class="sxs-lookup"><span data-stu-id="83a18-208">If the organization doesn’t contain any RBAC groups, the value will be “None.”</span></span> | <span data-ttu-id="83a18-209">Server</span><span class="sxs-lookup"><span data-stu-id="83a18-209">Servers</span></span>
<span data-ttu-id="83a18-210">RecommendationReference</span><span class="sxs-lookup"><span data-stu-id="83a18-210">RecommendationReference</span></span> | <span data-ttu-id="83a18-211">stringa</span><span class="sxs-lookup"><span data-stu-id="83a18-211">string</span></span> | <span data-ttu-id="83a18-212">Riferimento all'ID suggerimento relativo a questo software.</span><span class="sxs-lookup"><span data-stu-id="83a18-212">A reference to the recommendation ID related to this software.</span></span> | <span data-ttu-id="83a18-213">sca-_-scid-20000</span><span class="sxs-lookup"><span data-stu-id="83a18-213">sca-_-scid-20000</span></span>
<span data-ttu-id="83a18-214">Timestamp</span><span class="sxs-lookup"><span data-stu-id="83a18-214">Timestamp</span></span> | <span data-ttu-id="83a18-215">stringa</span><span class="sxs-lookup"><span data-stu-id="83a18-215">string</span></span> | <span data-ttu-id="83a18-216">Ultima volta che la configurazione è stata vista nel dispositivo</span><span class="sxs-lookup"><span data-stu-id="83a18-216">Last time the configuration was seen on the device</span></span> | <span data-ttu-id="83a18-217">2020-11-03 10:13:34.8476880</span><span class="sxs-lookup"><span data-stu-id="83a18-217">2020-11-03 10:13:34.8476880</span></span>

### <a name="16-examples"></a><span data-ttu-id="83a18-218">1.6 Esempi</span><span class="sxs-lookup"><span data-stu-id="83a18-218">1.6 Examples</span></span>

#### <a name="161-request-example"></a><span data-ttu-id="83a18-219">1.6.1 Esempio di richiesta</span><span class="sxs-lookup"><span data-stu-id="83a18-219">1.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SecureConfigurationsAssessmentByMachine?pageSize=5 
```

#### <a name="162-response-example"></a><span data-ttu-id="83a18-220">1.6.2 Esempio di risposta</span><span class="sxs-lookup"><span data-stu-id="83a18-220">1.6.2 Response example</span></span>

```json
{
    "@odata.context": "api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.AssetConfiguration)",
    "value": [
        {
            "deviceId": "00013ee62c6b12345b10214e1801b217b50ab455c293d",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_5d96860d69c73fdd06fc8d1679e1eb73eceb8330",
            "osPlatform": "Windows10",
            "osVersion": "NT kernel 6.x",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-10000",
            "configurationCategory": "Network",
            "configurationSubcategory": "",
            "configurationImpact": 5,
            "isCompliant": true,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Disable insecure administration protocol – Telnet",
            "recommendationReference": "sca-_-scid-10000"
        },
        {
            "deviceId": "0002a1be533813b9a8c6de739785365bce7910",
            "rbacGroupName": "hhh",
            "deviceName": null,
            "osPlatform": "Windows10",
            "osVersion": "10.0",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-20000",
            "configurationCategory": "Security controls",
            "configurationSubcategory": "Onboard Devices",
            "configurationImpact": 9,
            "isCompliant": false,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Onboard devices to Microsoft Defender for Endpoint",
            "recommendationReference": "sca-_-scid-20000"
        },
        {
            "deviceId": "0002a1de123456a8c06de736785395d4ce7610",
            "rbacGroupName": "hhh",
            "deviceName": null,
            "osPlatform": "Windows10",
            "osVersion": "10.0",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-10000",
            "configurationCategory": "Network",
            "configurationSubcategory": "",
            "configurationImpact": 5,
            "isCompliant": true,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Disable insecure administration protocol – Telnet",
            "recommendationReference": "sca-_-scid-10000"
        },
        {
            "deviceId": "00044f912345bdaf756492dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663d45912eed224b2be2f5ea3142726e63f16a.DomainPII_21eeb80b086e76bdfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-39",
            "configurationCategory": "OS",
            "configurationSubcategory": "",
            "configurationImpact": 5,
            "isCompliant": true,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Enable 'Domain member: Digitally sign secure channel data (when possible)'",
            "recommendationReference": "sca-_-scid-39"
        },
        {
            "deviceId": "00044f912345daf759462bde6bd733d6a9c56ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45612eeb224d2de2f5ea3142726e63f16a.DomainPII_21eed80d086e76dbfa178eadfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-6093",
            "configurationCategory": "Security controls",
            "configurationSubcategory": "Antivirus",
            "configurationImpact": 5,
            "isCompliant": false,
            "isApplicable": false,
            "isExpectedUserImpact": false,
            "configurationName": "Enable Microsoft Defender Antivirus real-time behavior monitoring for Linux",
            "recommendationReference": "sca-_-scid-6093"
        }
    ],
    "@odata.nextLink": "https://api.securitycenter.microsoft.com/api/machines/SecureConfigurationsAssessmentByMachine?pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0xMS8xMTAxLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}
```

## <a name="2-export-secure-configuration-assessment-via-files"></a><span data-ttu-id="83a18-221">2. Esportare la valutazione della configurazione sicura (tramite file)</span><span class="sxs-lookup"><span data-stu-id="83a18-221">2. Export secure configuration assessment (via files)</span></span>

### <a name="21-api-method-description"></a><span data-ttu-id="83a18-222">2.1 Descrizione del metodo API</span><span class="sxs-lookup"><span data-stu-id="83a18-222">2.1 API method description</span></span>

<span data-ttu-id="83a18-223">Questa risposta API contiene la valutazione della configurazione sicura nei dispositivi esposti e restituisce una voce per ogni combinazione univoca di DeviceId, ConfigurationId.</span><span class="sxs-lookup"><span data-stu-id="83a18-223">This API response contains the Secure Configuration Assessment on your exposed devices, and returns an entry for every unique combination of DeviceId, ConfigurationId.</span></span>

#### <a name="212-limitations"></a><span data-ttu-id="83a18-224">2.1.2 Limitazioni</span><span class="sxs-lookup"><span data-stu-id="83a18-224">2.1.2 Limitations</span></span>

<span data-ttu-id="83a18-225">I limiti di frequenza per questa API sono 5 chiamate al minuto e 20 chiamate all'ora.</span><span class="sxs-lookup"><span data-stu-id="83a18-225">Rate limitations for this API are 5 calls per minute and 20 calls per hour.</span></span>

### <a name="22-permissions"></a><span data-ttu-id="83a18-226">2.2 Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="83a18-226">2.2 Permissions</span></span>

<span data-ttu-id="83a18-227">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="83a18-227">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="83a18-228">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi Usare Le API di [Microsoft Defender per endpoint per i dettagli.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="83a18-228">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="83a18-229">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="83a18-229">Permission type</span></span> | <span data-ttu-id="83a18-230">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="83a18-230">Permission</span></span> | <span data-ttu-id="83a18-231">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="83a18-231">Permission display name</span></span>
---|---|---
<span data-ttu-id="83a18-232">Applicazione</span><span class="sxs-lookup"><span data-stu-id="83a18-232">Application</span></span> | <span data-ttu-id="83a18-233">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="83a18-233">Vulnerability.Read.All</span></span> | <span data-ttu-id="83a18-234">\'Leggere le informazioni gestione di minacce e vulnerabilità vulnerabilità\'</span><span class="sxs-lookup"><span data-stu-id="83a18-234">\'Read "threat and vulnerability management" vulnerability information\'</span></span>
<span data-ttu-id="83a18-235">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="83a18-235">Delegated (work or school account)</span></span> | <span data-ttu-id="83a18-236">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="83a18-236">Vulnerability.Read</span></span> | <span data-ttu-id="83a18-237">\'Leggere le informazioni gestione di minacce e vulnerabilità vulnerabilità\'</span><span class="sxs-lookup"><span data-stu-id="83a18-237">\'Read "threat and vulnerability management" vulnerability information\'</span></span>

### <a name="23-url"></a><span data-ttu-id="83a18-238">2.3 URL</span><span class="sxs-lookup"><span data-stu-id="83a18-238">2.3 URL</span></span>

```http
GET /api/machines/SecureConfigurationsAssessmentExport
```

### <a name="parameters"></a><span data-ttu-id="83a18-239">Parametri</span><span class="sxs-lookup"><span data-stu-id="83a18-239">Parameters</span></span>

- <span data-ttu-id="83a18-240">sasValidHours: numero di ore per cui saranno validi gli URL di download (massimo 24 ore).</span><span class="sxs-lookup"><span data-stu-id="83a18-240">sasValidHours – The number of hours that the download URLs will be valid for (Maximum 24 hours).</span></span>

### <a name="25-properties"></a><span data-ttu-id="83a18-241">2.5 Proprietà</span><span class="sxs-lookup"><span data-stu-id="83a18-241">2.5 Properties</span></span>

>[!Note]
>
>- <span data-ttu-id="83a18-242">I file sono compressi con gzip & in formato Json multilinea.</span><span class="sxs-lookup"><span data-stu-id="83a18-242">The files are gzip compressed & in multiline Json format.</span></span>
>
>- <span data-ttu-id="83a18-243">Gli URL di download sono validi solo per 3 ore. in caso contrario, è possibile utilizzare il parametro .</span><span class="sxs-lookup"><span data-stu-id="83a18-243">The download URLs are only valid for 3 hours; otherwise you can use the parameter.</span></span>
>
>- <span data-ttu-id="83a18-244">Per ottenere la massima velocità di download dei dati, puoi assicurarti di eseguire il download dalla stessa area di Azure in cui si trovano i dati.</span><span class="sxs-lookup"><span data-stu-id="83a18-244">For maximum download speed of your data, you can make sure you are downloading from the same Azure region in which your data resides.</span></span>
>
<span data-ttu-id="83a18-245">Proprietà (ID)</span><span class="sxs-lookup"><span data-stu-id="83a18-245">Property (ID)</span></span> | <span data-ttu-id="83a18-246">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="83a18-246">Data type</span></span> | <span data-ttu-id="83a18-247">Descrizione</span><span class="sxs-lookup"><span data-stu-id="83a18-247">Description</span></span> | <span data-ttu-id="83a18-248">Esempio di valore restituito</span><span class="sxs-lookup"><span data-stu-id="83a18-248">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="83a18-249">Esportare file</span><span class="sxs-lookup"><span data-stu-id="83a18-249">Export files</span></span> | <span data-ttu-id="83a18-250">stringa \[ di matrice\]</span><span class="sxs-lookup"><span data-stu-id="83a18-250">array\[string\]</span></span> | <span data-ttu-id="83a18-251">Elenco degli URL di download per i file che tengono lo snapshot corrente dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="83a18-251">A list of download URLs for files holding the current snapshot of the organization</span></span> | <span data-ttu-id="83a18-252">[  Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2” ]</span><span class="sxs-lookup"><span data-stu-id="83a18-252">[  Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2” ]</span></span>
<span data-ttu-id="83a18-253">GeneratedTime</span><span class="sxs-lookup"><span data-stu-id="83a18-253">GeneratedTime</span></span> | <span data-ttu-id="83a18-254">stringa</span><span class="sxs-lookup"><span data-stu-id="83a18-254">string</span></span> | <span data-ttu-id="83a18-255">Ora in cui è stata generata l'esportazione.</span><span class="sxs-lookup"><span data-stu-id="83a18-255">The time that the export was generated.</span></span> | <span data-ttu-id="83a18-256">2021-05-20T08:00:00Z ]</span><span class="sxs-lookup"><span data-stu-id="83a18-256">2021-05-20T08:00:00Z  ]</span></span>

### <a name="26-examples"></a><span data-ttu-id="83a18-257">2.6 Esempi</span><span class="sxs-lookup"><span data-stu-id="83a18-257">2.6 Examples</span></span>

#### <a name="261-request-example"></a><span data-ttu-id="83a18-258">2.6.1 Esempio di richiesta</span><span class="sxs-lookup"><span data-stu-id="83a18-258">2.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SecureConfigurationsAssessmentExport
```

#### <a name="262-response-example"></a><span data-ttu-id="83a18-259">2.6.2 Esempio di risposta</span><span class="sxs-lookup"><span data-stu-id="83a18-259">2.6.2 Response example</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#contoso.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": [
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/ScaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/ScaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/ScaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c001.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=..."
    ],
    "generatedTime": "2021-01-11T11:01:00Z"
}
```

## <a name="see-also"></a><span data-ttu-id="83a18-260">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="83a18-260">See also</span></span>

- [<span data-ttu-id="83a18-261">Esportare proprietà e metodi di valutazione per dispositivo</span><span class="sxs-lookup"><span data-stu-id="83a18-261">Export assessment methods and properties per device</span></span>](get-assessment-methods-properties.md)

- [<span data-ttu-id="83a18-262">Esportare la valutazione dell'inventario software per dispositivo</span><span class="sxs-lookup"><span data-stu-id="83a18-262">Export software inventory assessment per device</span></span>](get-assessment-software-inventory.md)

- [<span data-ttu-id="83a18-263">Esportare la valutazione delle vulnerabilità software per dispositivo</span><span class="sxs-lookup"><span data-stu-id="83a18-263">Export software vulnerabilities assessment per device</span></span>](get-assessment-software-vulnerabilities.md)

<span data-ttu-id="83a18-264">Altre informazioni correlate</span><span class="sxs-lookup"><span data-stu-id="83a18-264">Other related</span></span>

- [<span data-ttu-id="83a18-265">Rischio basato sulle minacce & gestione delle vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="83a18-265">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="83a18-266">Vulnerabilità nell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="83a18-266">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
