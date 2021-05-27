---
title: Esportare la valutazione dell'inventario software per dispositivo
description: Restituisce una tabella con una voce per ogni combinazione univoca di DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion.
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
ms.openlocfilehash: 5663a17de2e601c506b4d1b9ac44eaab6ae6245f
ms.sourcegitcommit: 82a4d74020cd93ba444006317cfecc178c6d41dc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689190"
---
# <a name="export-software-inventory-assessment-per-device"></a><span data-ttu-id="8c4b2-104">Esportare la valutazione dell'inventario software per dispositivo</span><span class="sxs-lookup"><span data-stu-id="8c4b2-104">Export software inventory assessment per device</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8c4b2-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="8c4b2-105">**Applies to:**</span></span>

- [<span data-ttu-id="8c4b2-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="8c4b2-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8c4b2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8c4b2-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="8c4b2-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="8c4b2-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="8c4b2-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="8c4b2-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]
>
>
<span data-ttu-id="8c4b2-110">Esistono diverse chiamate API per ottenere diversi tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="8c4b2-110">There are different API calls to get different types of data.</span></span> <span data-ttu-id="8c4b2-111">Poiché la quantità di dati può essere molto grande, è possibile recuperarla in due modi:</span><span class="sxs-lookup"><span data-stu-id="8c4b2-111">Because the amount of data can be very large, there are two ways it can be retrieved:</span></span>

- <span data-ttu-id="8c4b2-112">[Esportare OData di valutazione **dell'inventario software**](#1-export-software-inventory-assessment-odata)  L'API estrae tutti i dati nell'organizzazione come risposte Json, seguendo il protocollo OData.</span><span class="sxs-lookup"><span data-stu-id="8c4b2-112">[Export software inventory assessment **OData**](#1-export-software-inventory-assessment-odata)  The API pulls all data in your organization as Json responses, following the OData protocol.</span></span> <span data-ttu-id="8c4b2-113">Questo metodo è ideale per _organizzazioni di piccole dimensioni con meno di 100 K dispositivi._</span><span class="sxs-lookup"><span data-stu-id="8c4b2-113">This method is best for _small organizations with less than 100 K devices_.</span></span> <span data-ttu-id="8c4b2-114">La risposta viene impaginata, quindi è possibile utilizzare il campo \@ odata.nextLink dalla risposta per recuperare i risultati successivi.</span><span class="sxs-lookup"><span data-stu-id="8c4b2-114">The response is paginated, so you can use the \@odata.nextLink field from the response to fetch the next results.</span></span>

- <span data-ttu-id="8c4b2-115">[Esportare la valutazione dell'inventario **software tramite file**](#2-export-software-inventory-assessment-via-files)  Questa soluzione API consente di estrarre grandi quantità di dati in modo più rapido e affidabile.</span><span class="sxs-lookup"><span data-stu-id="8c4b2-115">[Export software inventory assessment **via files**](#2-export-software-inventory-assessment-via-files)  This API solution enables pulling larger amounts of data faster and more reliably.</span></span> <span data-ttu-id="8c4b2-116">Pertanto, è consigliabile per le organizzazioni di grandi dimensioni, con più di 100 dispositivi K.</span><span class="sxs-lookup"><span data-stu-id="8c4b2-116">Therefore, it is recommended for large organizations, with more than 100 K devices.</span></span> <span data-ttu-id="8c4b2-117">Questa API estrae tutti i dati dell'organizzazione come file di download.</span><span class="sxs-lookup"><span data-stu-id="8c4b2-117">This API pulls all data in your organization as download files.</span></span> <span data-ttu-id="8c4b2-118">La risposta contiene URL per scaricare tutti i dati da Archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="8c4b2-118">The response contains URLs to download all the data from Azure Storage.</span></span> <span data-ttu-id="8c4b2-119">Questa API consente di scaricare tutti i dati da Archiviazione di Azure come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="8c4b2-119">This API enables you to download all your data from Azure Storage as follows:</span></span>

  - <span data-ttu-id="8c4b2-120">Chiama l'API per ottenere un elenco di URL di download con tutti i dati dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8c4b2-120">Call the API to get a list of download URLs with all your organization data.</span></span>

  - <span data-ttu-id="8c4b2-121">Scarica tutti i file usando gli URL di download ed elabora i dati come vuoi.</span><span class="sxs-lookup"><span data-stu-id="8c4b2-121">Download all the files using the download URLs and process the data as you like.</span></span>

<span data-ttu-id="8c4b2-122">I dati raccolti (tramite _OData_ o _tramite file)_ sono lo snapshot corrente dello stato corrente e non contengono dati storici.</span><span class="sxs-lookup"><span data-stu-id="8c4b2-122">Data that is collected (using either _OData_ or _via files_) is the current snapshot of the current state, and does not contain historic data.</span></span> <span data-ttu-id="8c4b2-123">Per raccogliere i dati storici, i clienti devono salvare i dati nei propri archivi dati.</span><span class="sxs-lookup"><span data-stu-id="8c4b2-123">In order to collect historic data, customers must save the data in their own data storages.</span></span>

> [!Note]
>
> <span data-ttu-id="8c4b2-124">Se non diversamente indicato, tutti i metodi di valutazione dell'esportazione elencati sono **_l'esportazione_** completa e per dispositivo **_(noto_** anche **_come per dispositivo)._**</span><span class="sxs-lookup"><span data-stu-id="8c4b2-124">Unless indicated otherwise, all export assessment methods listed are **_full export_** and **_by device_** (also referred to as **_per device_**).</span></span>

## <a name="1-export-software-inventory-assessment-odata"></a><span data-ttu-id="8c4b2-125">1. Esportare la valutazione dell'inventario software (OData)</span><span class="sxs-lookup"><span data-stu-id="8c4b2-125">1. Export software inventory assessment (OData)</span></span>

### <a name="11-api-method-description"></a><span data-ttu-id="8c4b2-126">1.1 Descrizione del metodo API</span><span class="sxs-lookup"><span data-stu-id="8c4b2-126">1.1 API method description</span></span>

<span data-ttu-id="8c4b2-127">Questa risposta API contiene tutti i dati del software installato per dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8c4b2-127">This API response contains all the data of installed software per device.</span></span> <span data-ttu-id="8c4b2-128">Restituisce una tabella con una voce per ogni combinazione univoca di DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion.</span><span class="sxs-lookup"><span data-stu-id="8c4b2-128">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion.</span></span>

#### <a name="limitations"></a><span data-ttu-id="8c4b2-129">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="8c4b2-129">Limitations</span></span>

- <span data-ttu-id="8c4b2-130">La dimensione massima della pagina è 200.000.</span><span class="sxs-lookup"><span data-stu-id="8c4b2-130">Maximum page size is 200,000.</span></span>

- <span data-ttu-id="8c4b2-131">I limiti di frequenza per questa API sono 30 chiamate al minuto e 1000 chiamate all'ora.</span><span class="sxs-lookup"><span data-stu-id="8c4b2-131">Rate limitations for this API are 30 calls per minute and 1000 calls per hour.</span></span>

### <a name="12-permissions"></a><span data-ttu-id="8c4b2-132">1.2 Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="8c4b2-132">1.2 Permissions</span></span>

<span data-ttu-id="8c4b2-133">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="8c4b2-133">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="8c4b2-134">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi Usare Le API di [Microsoft Defender per endpoint per i dettagli.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="8c4b2-134">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="8c4b2-135">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="8c4b2-135">Permission type</span></span> | <span data-ttu-id="8c4b2-136">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="8c4b2-136">Permission</span></span> | <span data-ttu-id="8c4b2-137">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="8c4b2-137">Permission display name</span></span>
---|---|---
<span data-ttu-id="8c4b2-138">Applicazione</span><span class="sxs-lookup"><span data-stu-id="8c4b2-138">Application</span></span> | <span data-ttu-id="8c4b2-139">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="8c4b2-139">Software.Read.All</span></span> | <span data-ttu-id="8c4b2-140">\'Leggere informazioni sulla vulnerabilità di Gestione minacce e vulnerabilità\'</span><span class="sxs-lookup"><span data-stu-id="8c4b2-140">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="8c4b2-141">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="8c4b2-141">Delegated (work or school account)</span></span> | <span data-ttu-id="8c4b2-142">Software.Read</span><span class="sxs-lookup"><span data-stu-id="8c4b2-142">Software.Read</span></span> | <span data-ttu-id="8c4b2-143">\'Leggere informazioni sulla vulnerabilità di Gestione minacce e vulnerabilità\'</span><span class="sxs-lookup"><span data-stu-id="8c4b2-143">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="13-url"></a><span data-ttu-id="8c4b2-144">1.3 URL</span><span class="sxs-lookup"><span data-stu-id="8c4b2-144">1.3 URL</span></span>

```http
GET /api/machines/SoftwareInventoryByMachine
```

### <a name="14-parameters"></a><span data-ttu-id="8c4b2-145">1.4 Parametri</span><span class="sxs-lookup"><span data-stu-id="8c4b2-145">1.4 Parameters</span></span>

- <span data-ttu-id="8c4b2-146">pageSize (impostazione predefinita = 50.000): numero di risultati in risposta.</span><span class="sxs-lookup"><span data-stu-id="8c4b2-146">pageSize (default = 50,000) – number of results in response.</span></span>

- <span data-ttu-id="8c4b2-147">$top - Numero di risultati da restituire (non restituisce @odata.nextLink e pertanto non estrae tutti i dati)</span><span class="sxs-lookup"><span data-stu-id="8c4b2-147">$top – number of results to return (doesn’t return @odata.nextLink and therefore doesn’t pull all the data)</span></span>

### <a name="15-properties"></a><span data-ttu-id="8c4b2-148">1.5 Proprietà</span><span class="sxs-lookup"><span data-stu-id="8c4b2-148">1.5 Properties</span></span>

>[!NOTE]
>
><span data-ttu-id="8c4b2-149">-Ogni record è di circa 0,5 KB di dati.</span><span class="sxs-lookup"><span data-stu-id="8c4b2-149">-Each record is approximately 0.5KB of data.</span></span> <span data-ttu-id="8c4b2-150">È consigliabile prendere in considerazione questo parametro quando si sceglie il parametro pageSize corretto.</span><span class="sxs-lookup"><span data-stu-id="8c4b2-150">You should take this into account when choosing the correct pageSize parameter for you.</span></span>

><span data-ttu-id="8c4b2-151">-Le proprietà definite nella tabella seguente sono elencate in ordine alfabetico, in base all'ID proprietà.</span><span class="sxs-lookup"><span data-stu-id="8c4b2-151">-The properties defined in the following table are listed alphabetically, by property ID.</span></span> <span data-ttu-id="8c4b2-152">Quando si esegue questa API, l'output risultante non verrà necessariamente restituito nello stesso ordine elencato in questa tabella.</span><span class="sxs-lookup"><span data-stu-id="8c4b2-152">When running this API, the resulting output will not necessarily be returned in the same order listed in this table.</span></span>
>
><span data-ttu-id="8c4b2-153">-Alcune colonne aggiuntive potrebbero essere restituite nella risposta.</span><span class="sxs-lookup"><span data-stu-id="8c4b2-153">-Some additional columns might be returned in the response.</span></span> <span data-ttu-id="8c4b2-154">Queste colonne sono temporanee e potrebbero essere rimosse, utilizzare solo le colonne documentate.</span><span class="sxs-lookup"><span data-stu-id="8c4b2-154">These columns are temporary and might be removed, please use only the documented columns.</span></span>

<span data-ttu-id="8c4b2-155">Proprietà (ID)</span><span class="sxs-lookup"><span data-stu-id="8c4b2-155">Property (ID)</span></span> | <span data-ttu-id="8c4b2-156">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="8c4b2-156">Data type</span></span> | <span data-ttu-id="8c4b2-157">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8c4b2-157">Description</span></span> | <span data-ttu-id="8c4b2-158">Esempio di valore restituito</span><span class="sxs-lookup"><span data-stu-id="8c4b2-158">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="8c4b2-159">DeviceId</span><span class="sxs-lookup"><span data-stu-id="8c4b2-159">DeviceId</span></span> | <span data-ttu-id="8c4b2-160">stringa</span><span class="sxs-lookup"><span data-stu-id="8c4b2-160">string</span></span> | <span data-ttu-id="8c4b2-161">Identificatore univoco del dispositivo nel servizio.</span><span class="sxs-lookup"><span data-stu-id="8c4b2-161">Unique identifier for the device in the service.</span></span> | <span data-ttu-id="8c4b2-162">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span><span class="sxs-lookup"><span data-stu-id="8c4b2-162">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span></span>
<span data-ttu-id="8c4b2-163">DeviceName</span><span class="sxs-lookup"><span data-stu-id="8c4b2-163">DeviceName</span></span> | <span data-ttu-id="8c4b2-164">stringa</span><span class="sxs-lookup"><span data-stu-id="8c4b2-164">string</span></span> | <span data-ttu-id="8c4b2-165">Nome di dominio completo (FQDN) del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8c4b2-165">Fully qualified domain name (FQDN) of the device.</span></span> | <span data-ttu-id="8c4b2-166">johnlaptop.europe.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8c4b2-166">johnlaptop.europe.contoso.com</span></span>
<span data-ttu-id="8c4b2-167">DiskPaths</span><span class="sxs-lookup"><span data-stu-id="8c4b2-167">DiskPaths</span></span> | <span data-ttu-id="8c4b2-168">Array[string]</span><span class="sxs-lookup"><span data-stu-id="8c4b2-168">Array[string]</span></span>  | <span data-ttu-id="8c4b2-169">Prova su disco che il prodotto è installato nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8c4b2-169">Disk evidence that the product is installed on the device.</span></span> | <span data-ttu-id="8c4b2-170">[ "C: \\ Programmi (x86) \\ Microsoft Silverlight Application \\ \\ \\silverlight.exe" ]</span><span class="sxs-lookup"><span data-stu-id="8c4b2-170">[ "C:\\Program Files (x86)\\Microsoft\\Silverlight\\Application\\silverlight.exe" ]</span></span>
<span data-ttu-id="8c4b2-171">EndOfSupportDate</span><span class="sxs-lookup"><span data-stu-id="8c4b2-171">EndOfSupportDate</span></span> | <span data-ttu-id="8c4b2-172">stringa</span><span class="sxs-lookup"><span data-stu-id="8c4b2-172">string</span></span> | <span data-ttu-id="8c4b2-173">Data in cui il supporto per questo software ha o terminerà.</span><span class="sxs-lookup"><span data-stu-id="8c4b2-173">The date in which support for this software has or will end.</span></span> | <span data-ttu-id="8c4b2-174">2020-12-30</span><span class="sxs-lookup"><span data-stu-id="8c4b2-174">2020-12-30</span></span>
<span data-ttu-id="8c4b2-175">EndOfSupportStatus</span><span class="sxs-lookup"><span data-stu-id="8c4b2-175">EndOfSupportStatus</span></span> | <span data-ttu-id="8c4b2-176">stringa</span><span class="sxs-lookup"><span data-stu-id="8c4b2-176">string</span></span> | <span data-ttu-id="8c4b2-177">Stato della fine del supporto.</span><span class="sxs-lookup"><span data-stu-id="8c4b2-177">End of support status.</span></span> <span data-ttu-id="8c4b2-178">Può contenere questi valori possibili: None, EOS Version, Upcoming EOS Version, EOS Software, Upcoming EOS Software.</span><span class="sxs-lookup"><span data-stu-id="8c4b2-178">Can contain these possible values: None, EOS Version, Upcoming EOS Version, EOS Software, Upcoming EOS Software.</span></span> | <span data-ttu-id="8c4b2-179">EOS imminente</span><span class="sxs-lookup"><span data-stu-id="8c4b2-179">Upcoming EOS</span></span>
<span data-ttu-id="8c4b2-180">Id</span><span class="sxs-lookup"><span data-stu-id="8c4b2-180">Id</span></span> | <span data-ttu-id="8c4b2-181">stringa</span><span class="sxs-lookup"><span data-stu-id="8c4b2-181">string</span></span> | <span data-ttu-id="8c4b2-182">Identificatore univoco del record.</span><span class="sxs-lookup"><span data-stu-id="8c4b2-182">Unique identifier for the record.</span></span> | <span data-ttu-id="8c4b2-183">123ABG55_573AG&mnp!</span><span class="sxs-lookup"><span data-stu-id="8c4b2-183">123ABG55_573AG&mnp!</span></span>
<span data-ttu-id="8c4b2-184">NumberOfWeaknesses</span><span class="sxs-lookup"><span data-stu-id="8c4b2-184">NumberOfWeaknesses</span></span> | <span data-ttu-id="8c4b2-185">int</span><span class="sxs-lookup"><span data-stu-id="8c4b2-185">int</span></span> | <span data-ttu-id="8c4b2-186">Numero di punti deboli su questo software in questo dispositivo</span><span class="sxs-lookup"><span data-stu-id="8c4b2-186">Number of weaknesses on this software on this device</span></span> | <span data-ttu-id="8c4b2-187">3</span><span class="sxs-lookup"><span data-stu-id="8c4b2-187">3</span></span>
<span data-ttu-id="8c4b2-188">OSPlatform</span><span class="sxs-lookup"><span data-stu-id="8c4b2-188">OSPlatform</span></span> | <span data-ttu-id="8c4b2-189">stringa</span><span class="sxs-lookup"><span data-stu-id="8c4b2-189">string</span></span> | <span data-ttu-id="8c4b2-190">Piattaforma del sistema operativo in esecuzione nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8c4b2-190">Platform of the operating system running on the device.</span></span> <span data-ttu-id="8c4b2-191">Ciò indica specifici sistemi operativi, incluse variazioni all'interno della stessa famiglia di prodotti, come Windows 10 e Windows 7.</span><span class="sxs-lookup"><span data-stu-id="8c4b2-191">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> <span data-ttu-id="8c4b2-192">Per informazioni dettagliate, vedere tvm supported operating systems and platforms.</span><span class="sxs-lookup"><span data-stu-id="8c4b2-192">See tvm supported operating systems and platforms for details.</span></span> | <span data-ttu-id="8c4b2-193">Windows10</span><span class="sxs-lookup"><span data-stu-id="8c4b2-193">Windows10</span></span>
<span data-ttu-id="8c4b2-194">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="8c4b2-194">RbacGroupName</span></span> | <span data-ttu-id="8c4b2-195">stringa</span><span class="sxs-lookup"><span data-stu-id="8c4b2-195">string</span></span> | <span data-ttu-id="8c4b2-196">Gruppo RBAC (Role-Based Access Control).</span><span class="sxs-lookup"><span data-stu-id="8c4b2-196">The role-based access control (RBAC) group.</span></span> <span data-ttu-id="8c4b2-197">Se questo dispositivo non è assegnato ad alcun gruppo RBAC, il valore sarà "Non assegnato".</span><span class="sxs-lookup"><span data-stu-id="8c4b2-197">If this device is not assigned to any RBAC group, the value will be “Unassigned.”</span></span> <span data-ttu-id="8c4b2-198">Se l'organizzazione non contiene gruppi RBAC, il valore sarà "None".</span><span class="sxs-lookup"><span data-stu-id="8c4b2-198">If the organization doesn’t contain any RBAC groups, the value will be “None.”</span></span> | <span data-ttu-id="8c4b2-199">Server</span><span class="sxs-lookup"><span data-stu-id="8c4b2-199">Servers</span></span>
<span data-ttu-id="8c4b2-200">RegistryPaths</span><span class="sxs-lookup"><span data-stu-id="8c4b2-200">RegistryPaths</span></span> | <span data-ttu-id="8c4b2-201">Array[string]</span><span class="sxs-lookup"><span data-stu-id="8c4b2-201">Array[string]</span></span> | <span data-ttu-id="8c4b2-202">Prova del Registro di sistema che il prodotto è installato nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8c4b2-202">Registry evidence that the product is installed in the device.</span></span> | <span data-ttu-id="8c4b2-203">[ "HKEY_LOCAL_MACHINE \\ SOFTWARE \\ WOW6432Node \\ Microsoft Windows \\ \\ CurrentVersion Uninstall Microsoft \\ \\ Silverlight" ]</span><span class="sxs-lookup"><span data-stu-id="8c4b2-203">[ "HKEY_LOCAL_MACHINE\\SOFTWARE\\WOW6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Silverlight" ]</span></span>
<span data-ttu-id="8c4b2-204">SoftwareFirstSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="8c4b2-204">SoftwareFirstSeenTimestamp</span></span> | <span data-ttu-id="8c4b2-205">stringa</span><span class="sxs-lookup"><span data-stu-id="8c4b2-205">string</span></span> | <span data-ttu-id="8c4b2-206">La prima volta che questo software è stato visto nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8c4b2-206">The first time this software was seen on the device.</span></span> | <span data-ttu-id="8c4b2-207">2019-04-07 02:06:47</span><span class="sxs-lookup"><span data-stu-id="8c4b2-207">2019-04-07 02:06:47</span></span>
<span data-ttu-id="8c4b2-208">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="8c4b2-208">SoftwareName</span></span> | <span data-ttu-id="8c4b2-209">stringa</span><span class="sxs-lookup"><span data-stu-id="8c4b2-209">string</span></span> | <span data-ttu-id="8c4b2-210">Nome del prodotto software.</span><span class="sxs-lookup"><span data-stu-id="8c4b2-210">Name of the software product.</span></span> | <span data-ttu-id="8c4b2-211">Silverlight</span><span class="sxs-lookup"><span data-stu-id="8c4b2-211">Silverlight</span></span>
<span data-ttu-id="8c4b2-212">SoftwareVendor</span><span class="sxs-lookup"><span data-stu-id="8c4b2-212">SoftwareVendor</span></span> | <span data-ttu-id="8c4b2-213">stringa</span><span class="sxs-lookup"><span data-stu-id="8c4b2-213">string</span></span> | <span data-ttu-id="8c4b2-214">Nome del fornitore del software.</span><span class="sxs-lookup"><span data-stu-id="8c4b2-214">Name of the software vendor.</span></span> | <span data-ttu-id="8c4b2-215">microsoft</span><span class="sxs-lookup"><span data-stu-id="8c4b2-215">microsoft</span></span>
<span data-ttu-id="8c4b2-216">SoftwareVersion</span><span class="sxs-lookup"><span data-stu-id="8c4b2-216">SoftwareVersion</span></span> | <span data-ttu-id="8c4b2-217">stringa</span><span class="sxs-lookup"><span data-stu-id="8c4b2-217">string</span></span> | <span data-ttu-id="8c4b2-218">Numero di versione del prodotto software.</span><span class="sxs-lookup"><span data-stu-id="8c4b2-218">Version number of the software product.</span></span> | <span data-ttu-id="8c4b2-219">81.0.4044.138</span><span class="sxs-lookup"><span data-stu-id="8c4b2-219">81.0.4044.138</span></span>

### <a name="16-examples"></a><span data-ttu-id="8c4b2-220">1.6 Esempi</span><span class="sxs-lookup"><span data-stu-id="8c4b2-220">1.6 Examples</span></span>

#### <a name="161-request-example"></a><span data-ttu-id="8c4b2-221">1.6.1 Esempio di richiesta</span><span class="sxs-lookup"><span data-stu-id="8c4b2-221">1.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryByMachine?pageSize=5  &sinceTime=2021-05-19T18%3A35%3A49.924Z 
```

#### <a name="162-response-example"></a><span data-ttu-id="8c4b2-222">1.6.2 Esempio di risposta</span><span class="sxs-lookup"><span data-stu-id="8c4b2-222">1.6.2 Response example</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(contoso.windowsDefenderATP.api.AssetSoftware)",
    "value": [
        {
            "deviceId": "00044f68765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eeb80d086e79dbfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "windows_10",
            "softwareVersion": "10.0.17763.1637",
            "numberOfWeaknesses": 58,
            "diskPaths": [],
            "registryPaths": [],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "Upcoming EOS Version",
            "endOfSupportDate": "2021-05-11T00:00:00+00:00"
        },
        {
            "deviceId": "00044f68765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eeb80d086e79dbfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": ".net_framework",
            "softwareVersion": "4.0.0.0",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4.0\\Client\\Install"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        },
        {
            "deviceId": "00044f68765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eed80d086e79bdfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "system_center_2012_endpoint_protection",
            "softwareVersion": "4.7.214.0",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Security Client"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        },
        {
            "deviceId": "00044f68765ddaf71234bde6bd733d6a9c59ad4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eeb80d086e79dbfa178aedfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "configuration_manager",
            "softwareVersion": "5.0.8634.1000",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\{B7D3A842-E826-4542-B39B-1D883264B279}"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        },
        {
            "deviceId": "00044f38765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2de2f5ea3142726e63f16a.DomainPII_21eeb80d086e79bdfa178eadfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "system_center_2012_endpoint_protection",
            "softwareVersion": "4.10.209.0",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Security Client"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        }
    ],
    "@odata.nextLink": "https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryByMachine?pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0yNS8wMjAwLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}
```

## <a name="2-export-software-inventory-assessment-via-files"></a><span data-ttu-id="8c4b2-223">2. Esportare la valutazione dell'inventario software (tramite file)</span><span class="sxs-lookup"><span data-stu-id="8c4b2-223">2. Export software inventory assessment (via files)</span></span>

### <a name="21-api-method-description"></a><span data-ttu-id="8c4b2-224">2.1 Descrizione del metodo API</span><span class="sxs-lookup"><span data-stu-id="8c4b2-224">2.1 API method description</span></span>

<span data-ttu-id="8c4b2-225">Questa risposta API contiene tutti i dati del software installato per dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8c4b2-225">This API response contains all the data of installed software per device.</span></span> <span data-ttu-id="8c4b2-226">Restituisce una tabella con una voce per ogni combinazione univoca di DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion.</span><span class="sxs-lookup"><span data-stu-id="8c4b2-226">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion.</span></span>

#### <a name="211-limitations"></a><span data-ttu-id="8c4b2-227">2.1.1 Limitazioni</span><span class="sxs-lookup"><span data-stu-id="8c4b2-227">2.1.1 Limitations</span></span>

<span data-ttu-id="8c4b2-228">I limiti di frequenza per questa API sono 5 chiamate al minuto e 20 chiamate all'ora.</span><span class="sxs-lookup"><span data-stu-id="8c4b2-228">Rate limitations for this API are 5 calls per minute and 20 calls per hour.</span></span>

### <a name="22-permissions"></a><span data-ttu-id="8c4b2-229">2.2 Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="8c4b2-229">2.2 Permissions</span></span>

<span data-ttu-id="8c4b2-230">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="8c4b2-230">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="8c4b2-231">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi Usare Le API di [Microsoft Defender per endpoint per i dettagli.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="8c4b2-231">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="8c4b2-232">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="8c4b2-232">Permission type</span></span> | <span data-ttu-id="8c4b2-233">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="8c4b2-233">Permission</span></span> | <span data-ttu-id="8c4b2-234">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="8c4b2-234">Permission display name</span></span>
---|---|---
<span data-ttu-id="8c4b2-235">Applicazione</span><span class="sxs-lookup"><span data-stu-id="8c4b2-235">Application</span></span> | <span data-ttu-id="8c4b2-236">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="8c4b2-236">Software.Read.All</span></span> | <span data-ttu-id="8c4b2-237">\'Leggere informazioni sulla vulnerabilità di Gestione minacce e vulnerabilità\'</span><span class="sxs-lookup"><span data-stu-id="8c4b2-237">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="8c4b2-238">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="8c4b2-238">Delegated (work or school account)</span></span> | <span data-ttu-id="8c4b2-239">Software.Read</span><span class="sxs-lookup"><span data-stu-id="8c4b2-239">Software.Read</span></span> | <span data-ttu-id="8c4b2-240">\'Leggere informazioni sulla vulnerabilità di Gestione minacce e vulnerabilità\'</span><span class="sxs-lookup"><span data-stu-id="8c4b2-240">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="23-url"></a><span data-ttu-id="8c4b2-241">2.3 URL</span><span class="sxs-lookup"><span data-stu-id="8c4b2-241">2.3 URL</span></span>

```http
GET /api/machines/SoftwareInventoryExport
```

### <a name="parameters"></a><span data-ttu-id="8c4b2-242">Parametri</span><span class="sxs-lookup"><span data-stu-id="8c4b2-242">Parameters</span></span>

- <span data-ttu-id="8c4b2-243">sasValidHours: numero di ore per cui saranno validi gli URL di download (massimo 24 ore)</span><span class="sxs-lookup"><span data-stu-id="8c4b2-243">sasValidHours – The number of hours that the download URLs will be valid for (Maximum 24 hours)</span></span>

### <a name="25-properties"></a><span data-ttu-id="8c4b2-244">2.5 Proprietà</span><span class="sxs-lookup"><span data-stu-id="8c4b2-244">2.5 Properties</span></span>

>[!Note]
>
>- <span data-ttu-id="8c4b2-245">I file sono compressi con gzip & in formato Json multilinea.</span><span class="sxs-lookup"><span data-stu-id="8c4b2-245">The files are gzip compressed & in multiline Json format.</span></span>
>
>- <span data-ttu-id="8c4b2-246">Gli URL di download sono validi solo per 3 ore.</span><span class="sxs-lookup"><span data-stu-id="8c4b2-246">The download URLs are only valid for 3 hours.</span></span> <span data-ttu-id="8c4b2-247">In caso contrario, è possibile utilizzare il parametro .</span><span class="sxs-lookup"><span data-stu-id="8c4b2-247">Otherwise you can use the parameter.</span></span>
>
><span data-ttu-id="8c4b2-248">_ Per la massima velocità di download dei dati, puoi assicurarti di eseguire il download dalla stessa area di Azure in cui si trovano i dati.</span><span class="sxs-lookup"><span data-stu-id="8c4b2-248">_ For maximum download speed of your data, you can make sure you are downloading from the same Azure region that your data resides.</span></span>
>
<span data-ttu-id="8c4b2-249">Proprietà (ID)</span><span class="sxs-lookup"><span data-stu-id="8c4b2-249">Property (ID)</span></span> | <span data-ttu-id="8c4b2-250">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="8c4b2-250">Data type</span></span> | <span data-ttu-id="8c4b2-251">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8c4b2-251">Description</span></span> | <span data-ttu-id="8c4b2-252">Esempio di valore restituito</span><span class="sxs-lookup"><span data-stu-id="8c4b2-252">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="8c4b2-253">Esportare file</span><span class="sxs-lookup"><span data-stu-id="8c4b2-253">Export files</span></span> | <span data-ttu-id="8c4b2-254">stringa \[ di matrice\]</span><span class="sxs-lookup"><span data-stu-id="8c4b2-254">array\[string\]</span></span> | <span data-ttu-id="8c4b2-255">Elenco degli URL di download per i file che tengono lo snapshot corrente dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="8c4b2-255">A list of download URLs for files holding the current snapshot of the organization</span></span> | <span data-ttu-id="8c4b2-256">[  Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2” ]</span><span class="sxs-lookup"><span data-stu-id="8c4b2-256">[  Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2” ]</span></span>
<span data-ttu-id="8c4b2-257">GeneratedTime</span><span class="sxs-lookup"><span data-stu-id="8c4b2-257">GeneratedTime</span></span> | <span data-ttu-id="8c4b2-258">stringa</span><span class="sxs-lookup"><span data-stu-id="8c4b2-258">string</span></span> | <span data-ttu-id="8c4b2-259">Ora in cui è stata generata l'esportazione.</span><span class="sxs-lookup"><span data-stu-id="8c4b2-259">The time that the export was generated.</span></span> | <span data-ttu-id="8c4b2-260">2021-05-20T08:00:00Z ]</span><span class="sxs-lookup"><span data-stu-id="8c4b2-260">2021-05-20T08:00:00Z  ]</span></span>

### <a name="26-examples"></a><span data-ttu-id="8c4b2-261">2.6 Esempi</span><span class="sxs-lookup"><span data-stu-id="8c4b2-261">2.6 Examples</span></span>

#### <a name="261-request-example"></a><span data-ttu-id="8c4b2-262">2.6.1 Esempio di richiesta</span><span class="sxs-lookup"><span data-stu-id="8c4b2-262">2.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryExport
```

#### <a name="262-response-example"></a><span data-ttu-id="8c4b2-263">2.6.2 Esempio di risposta</span><span class="sxs-lookup"><span data-stu-id="8c4b2-263">2.6.2 Response example</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": [
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/SoftwareInventory/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/SoftwareInventory/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/SoftwareInventory/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c001.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=..."
    ],
    "generatedTime": "2021-01-11T11:01:00Z"
}
```

## <a name="see-also"></a><span data-ttu-id="8c4b2-264">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8c4b2-264">See also</span></span>

- [<span data-ttu-id="8c4b2-265">Esportare proprietà e metodi di valutazione per dispositivo</span><span class="sxs-lookup"><span data-stu-id="8c4b2-265">Export assessment methods and properties per device</span></span>](get-assessmnt-1methods-properties.md)

- [<span data-ttu-id="8c4b2-266">Esportare la valutazione della configurazione sicura per dispositivo</span><span class="sxs-lookup"><span data-stu-id="8c4b2-266">Export secure configuration assessment per device</span></span>](get-assessmnt-secure-cfg.md)

- [<span data-ttu-id="8c4b2-267">Esportare la valutazione delle vulnerabilità software per dispositivo</span><span class="sxs-lookup"><span data-stu-id="8c4b2-267">Export software vulnerabilities assessment per device</span></span>](get-assessmnt-software-vulnerabilities.md)

<span data-ttu-id="8c4b2-268">Altre informazioni correlate</span><span class="sxs-lookup"><span data-stu-id="8c4b2-268">Other related</span></span>

- [<span data-ttu-id="8c4b2-269">Rischio basato sulle minacce & gestione delle vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="8c4b2-269">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="8c4b2-270">Vulnerabilità nell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="8c4b2-270">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
