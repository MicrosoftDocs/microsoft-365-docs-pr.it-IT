---
title: Funzione FileProfile() nella ricerca avanzata per Microsoft 365 Defender
description: Informazioni su come utilizzare FileProfile() per migliorare le informazioni sui file nei risultati delle query di ricerca avanzate
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, protezione dalle minacce Microsoft, Microsoft 365, mtp, m365, ricerca, query, telemetria, riferimento allo schema, kusto, FileProfile, profilo file, funzione, arricchimento
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: a9ca0af0c522205309ffdcbfd1ac28638bd197c7
ms.sourcegitcommit: ef98b8a18d275e5b5961e63d2b0743d046321737
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/26/2021
ms.locfileid: "51382794"
---
# <a name="fileprofile"></a><span data-ttu-id="c4b56-104">FileProfile()</span><span class="sxs-lookup"><span data-stu-id="c4b56-104">FileProfile()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c4b56-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="c4b56-105">**Applies to:**</span></span>
- <span data-ttu-id="c4b56-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c4b56-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="c4b56-107">La funzione è una funzione di arricchimento nella ricerca avanzata che aggiunge i dati seguenti ai `FileProfile()` file trovati dalla query. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="c4b56-107">The `FileProfile()` function is an enrichment function in [advanced hunting](advanced-hunting-overview.md) that adds the following data to files found by the query.</span></span>

| <span data-ttu-id="c4b56-108">Colonna</span><span class="sxs-lookup"><span data-stu-id="c4b56-108">Column</span></span> | <span data-ttu-id="c4b56-109">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="c4b56-109">Data type</span></span> | <span data-ttu-id="c4b56-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c4b56-110">Description</span></span> |
|------------|---------------|-------------|
| `SHA1` | <span data-ttu-id="c4b56-111">stringa</span><span class="sxs-lookup"><span data-stu-id="c4b56-111">string</span></span> | <span data-ttu-id="c4b56-112">SHA-1 del file a cui è stata applicata l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="c4b56-112">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="c4b56-113">stringa</span><span class="sxs-lookup"><span data-stu-id="c4b56-113">string</span></span> | <span data-ttu-id="c4b56-114">SHA-256 del file a cui è stata applicata l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="c4b56-114">SHA-256 of the file that the recorded action was applied to</span></span> |
| `MD5` | <span data-ttu-id="c4b56-115">stringa</span><span class="sxs-lookup"><span data-stu-id="c4b56-115">string</span></span> | <span data-ttu-id="c4b56-116">Hash MD5 del file a cui è stata applicata l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="c4b56-116">MD5 hash of the file that the recorded action was applied to</span></span> |
| `FileSize` | <span data-ttu-id="c4b56-117">int</span><span class="sxs-lookup"><span data-stu-id="c4b56-117">int</span></span> | <span data-ttu-id="c4b56-118">Dimensioni del file in byte</span><span class="sxs-lookup"><span data-stu-id="c4b56-118">Size of the file in bytes</span></span> |
| `GlobalPrevalence` | <span data-ttu-id="c4b56-119">int</span><span class="sxs-lookup"><span data-stu-id="c4b56-119">int</span></span> | <span data-ttu-id="c4b56-120">Numero di istanze dell'entità osservate da Microsoft a livello globale</span><span class="sxs-lookup"><span data-stu-id="c4b56-120">Number of instances of the entity observed by Microsoft globally</span></span> |
| `GlobalFirstSeen` | <span data-ttu-id="c4b56-121">datetime</span><span class="sxs-lookup"><span data-stu-id="c4b56-121">datetime</span></span> | <span data-ttu-id="c4b56-122">Data e ora in cui l'entità è stata osservata per la prima volta da Microsoft a livello globale</span><span class="sxs-lookup"><span data-stu-id="c4b56-122">Date and time when the entity was first observed by Microsoft globally</span></span> |
| `GlobalLastSeen` | <span data-ttu-id="c4b56-123">datetime</span><span class="sxs-lookup"><span data-stu-id="c4b56-123">datetime</span></span> | <span data-ttu-id="c4b56-124">Data e ora dell'ultima osservazione dell'entità da parte di Microsoft a livello globale</span><span class="sxs-lookup"><span data-stu-id="c4b56-124">Date and time when the entity was last observed by Microsoft globally</span></span> |
| `Signer` | <span data-ttu-id="c4b56-125">stringa</span><span class="sxs-lookup"><span data-stu-id="c4b56-125">string</span></span> | <span data-ttu-id="c4b56-126">Informazioni sul firmatario del file</span><span class="sxs-lookup"><span data-stu-id="c4b56-126">Information about the signer of the file</span></span> |
| `Issuer` | <span data-ttu-id="c4b56-127">stringa</span><span class="sxs-lookup"><span data-stu-id="c4b56-127">string</span></span> | <span data-ttu-id="c4b56-128">Informazioni sull'autorità di certificazione (CA) emittente</span><span class="sxs-lookup"><span data-stu-id="c4b56-128">Information about the issuing certificate authority (CA)</span></span> |
| `SignerHash` | <span data-ttu-id="c4b56-129">stringa</span><span class="sxs-lookup"><span data-stu-id="c4b56-129">string</span></span> | <span data-ttu-id="c4b56-130">Valore hash univoco che identifica il firmatario</span><span class="sxs-lookup"><span data-stu-id="c4b56-130">Unique hash value identifying the signer</span></span> |
| `IsCertificateValid` | <span data-ttu-id="c4b56-131">boolean</span><span class="sxs-lookup"><span data-stu-id="c4b56-131">boolean</span></span> | <span data-ttu-id="c4b56-132">Indica se il certificato utilizzato per firmare il file è valido</span><span class="sxs-lookup"><span data-stu-id="c4b56-132">Whether the certificate used to sign the file is valid</span></span> |
| `IsRootSignerMicrosoft` | <span data-ttu-id="c4b56-133">boolean</span><span class="sxs-lookup"><span data-stu-id="c4b56-133">boolean</span></span> | <span data-ttu-id="c4b56-134">Indica se il firmatario del certificato radice è Microsoft</span><span class="sxs-lookup"><span data-stu-id="c4b56-134">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| `SignatureState` | <span data-ttu-id="c4b56-135">stringa</span><span class="sxs-lookup"><span data-stu-id="c4b56-135">string</span></span> | <span data-ttu-id="c4b56-136">Stato della firma del file: SignedValid - Il file è firmato con una firma valida, SignedInvalid - il file è firmato ma il certificato non è valido, Unsigned - il file non è firmato, Unknown - Le informazioni sul file non possono essere recuperate</span><span class="sxs-lookup"><span data-stu-id="c4b56-136">State of the file signature: SignedValid - the file is signed with a valid signature, SignedInvalid - the file is signed but the certificate is invalid, Unsigned - the file is not signed, Unknown - information about the file cannot be retrieved</span></span>
| `IsExecutable` | <span data-ttu-id="c4b56-137">boolean</span><span class="sxs-lookup"><span data-stu-id="c4b56-137">boolean</span></span> | <span data-ttu-id="c4b56-138">Indica se il file è un file PE (Portable Executable)</span><span class="sxs-lookup"><span data-stu-id="c4b56-138">Whether the file is a Portable Executable (PE) file</span></span> |
| `ThreatName` | <span data-ttu-id="c4b56-139">stringa</span><span class="sxs-lookup"><span data-stu-id="c4b56-139">string</span></span> | <span data-ttu-id="c4b56-140">Nome di rilevamento per qualsiasi malware o altre minacce rilevate</span><span class="sxs-lookup"><span data-stu-id="c4b56-140">Detection name for any malware or other threats found</span></span> |
| `Publisher` | <span data-ttu-id="c4b56-141">stringa</span><span class="sxs-lookup"><span data-stu-id="c4b56-141">string</span></span> | <span data-ttu-id="c4b56-142">Nome dell'organizzazione che ha pubblicato il file</span><span class="sxs-lookup"><span data-stu-id="c4b56-142">Name of the organization that published the file</span></span> |
| `SoftwareName` | <span data-ttu-id="c4b56-143">stringa</span><span class="sxs-lookup"><span data-stu-id="c4b56-143">string</span></span> | <span data-ttu-id="c4b56-144">Nome del prodotto software</span><span class="sxs-lookup"><span data-stu-id="c4b56-144">Name of the software product</span></span> |

## <a name="syntax"></a><span data-ttu-id="c4b56-145">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c4b56-145">Syntax</span></span>

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a><span data-ttu-id="c4b56-146">Argomenti</span><span class="sxs-lookup"><span data-stu-id="c4b56-146">Arguments</span></span>

- <span data-ttu-id="c4b56-147">**x**- Colonna ID file da utilizzare: , , o ; se non specificata, viene utilizzata `SHA1` `SHA256` la `InitiatingProcessSHA1` `InitiatingProcessSHA256` `SHA1` funzione</span><span class="sxs-lookup"><span data-stu-id="c4b56-147">**x**—file ID column to use: `SHA1`, `SHA256`, `InitiatingProcessSHA1`, or `InitiatingProcessSHA256`; function uses `SHA1` if unspecified</span></span>
- <span data-ttu-id="c4b56-148">**y**: limite al numero di record da arricchire, da 1 a 1000; la funzione utilizza 100 se non specificato</span><span class="sxs-lookup"><span data-stu-id="c4b56-148">**y**—limit to the number of records to enrich, 1-1000; function uses 100 if unspecified</span></span>


>[!TIP]
> <span data-ttu-id="c4b56-149">Le funzioni di arricchimento mostreranno informazioni aggiuntive solo quando sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="c4b56-149">Enrichment functions will show supplemental information only when they are available.</span></span> <span data-ttu-id="c4b56-150">La disponibilità delle informazioni è varia e dipende da molti fattori.</span><span class="sxs-lookup"><span data-stu-id="c4b56-150">Availability of information is varied and depends on a lot of factors.</span></span> <span data-ttu-id="c4b56-151">Tenere presente questa considerazione quando si usa FileProfile() nelle query o nella creazione di rilevamenti personalizzati.</span><span class="sxs-lookup"><span data-stu-id="c4b56-151">Make sure to consider this when using FileProfile() in your queries or in creating custom detections.</span></span> <span data-ttu-id="c4b56-152">Per ottenere risultati ottimali, è consigliabile utilizzare la funzione FileProfile() con SHA1.</span><span class="sxs-lookup"><span data-stu-id="c4b56-152">For best results, we recommend using the FileProfile() function with SHA1.</span></span>

## <a name="examples"></a><span data-ttu-id="c4b56-153">Esempi</span><span class="sxs-lookup"><span data-stu-id="c4b56-153">Examples</span></span>

### <a name="project-only-the-sha1-column-and-enrich-it"></a><span data-ttu-id="c4b56-154">Proiettare solo la colonna SHA1 e arricchirla</span><span class="sxs-lookup"><span data-stu-id="c4b56-154">Project only the SHA1 column and enrich it</span></span>

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a><span data-ttu-id="c4b56-155">Arricchire i primi 500 record ed elencare i file a bassa prevalenza</span><span class="sxs-lookup"><span data-stu-id="c4b56-155">Enrich the first 500 records and list low-prevalence files</span></span>

```kusto
DeviceFileEvents
| where ActionType == "FileCreated" and Timestamp > ago(1d)
| project CreatedOn = Timestamp, FileName, FolderPath, SHA1
| invoke FileProfile("SHA1", 500) 
| where GlobalPrevalence < 15
```

## <a name="related-topics"></a><span data-ttu-id="c4b56-156">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="c4b56-156">Related topics</span></span>
- [<span data-ttu-id="c4b56-157">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="c4b56-157">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="c4b56-158">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="c4b56-158">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="c4b56-159">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="c4b56-159">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="c4b56-160">Ottenere altri esempi di query</span><span class="sxs-lookup"><span data-stu-id="c4b56-160">Get more query examples</span></span>](advanced-hunting-shared-queries.md)
