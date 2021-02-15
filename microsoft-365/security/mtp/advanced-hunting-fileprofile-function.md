---
title: Funzione FileProfile() nella ricerca avanzata per Microsoft 365 Defender
description: Informazioni su come usare FileProfile() per migliorare le informazioni sui file nei risultati delle query di ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca delle minacce informatiche, protezione dalle minacce Microsoft, Microsoft 365, mtp, m365, ricerca, query, telemetria, riferimento allo schema, kusto, FileProfile, profilo file, funzione, arricchimento
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 68196f126ac470088d7ba5e2923accc492d8764c
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929551"
---
# <a name="fileprofile"></a><span data-ttu-id="7e832-104">FileProfile()</span><span class="sxs-lookup"><span data-stu-id="7e832-104">FileProfile()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="7e832-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="7e832-105">**Applies to:**</span></span>
- <span data-ttu-id="7e832-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7e832-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="7e832-107">La funzione è una funzione di arricchimento nella ricerca `FileProfile()` [avanzata](advanced-hunting-overview.md) che aggiunge i dati seguenti ai file trovati dalla query.</span><span class="sxs-lookup"><span data-stu-id="7e832-107">The `FileProfile()` function is an enrichment function in [advanced hunting](advanced-hunting-overview.md) that adds the following data to files found by the query.</span></span>

| <span data-ttu-id="7e832-108">Colonna</span><span class="sxs-lookup"><span data-stu-id="7e832-108">Column</span></span> | <span data-ttu-id="7e832-109">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="7e832-109">Data type</span></span> | <span data-ttu-id="7e832-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7e832-110">Description</span></span> |
|------------|-------------|-------------|
| <span data-ttu-id="7e832-111">SHA1</span><span class="sxs-lookup"><span data-stu-id="7e832-111">SHA1</span></span> | <span data-ttu-id="7e832-112">stringa</span><span class="sxs-lookup"><span data-stu-id="7e832-112">string</span></span> | <span data-ttu-id="7e832-113">SHA-1 del file a cui è stata applicata l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="7e832-113">SHA-1 of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="7e832-114">SHA256</span><span class="sxs-lookup"><span data-stu-id="7e832-114">SHA256</span></span> | <span data-ttu-id="7e832-115">stringa</span><span class="sxs-lookup"><span data-stu-id="7e832-115">string</span></span> | <span data-ttu-id="7e832-116">SHA-256 del file a cui è stata applicata l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="7e832-116">SHA-256 of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="7e832-117">MD5</span><span class="sxs-lookup"><span data-stu-id="7e832-117">MD5</span></span> | <span data-ttu-id="7e832-118">stringa</span><span class="sxs-lookup"><span data-stu-id="7e832-118">string</span></span> | <span data-ttu-id="7e832-119">Hash MD5 del file a cui è stata applicata l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="7e832-119">MD5 hash of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="7e832-120">FileSize</span><span class="sxs-lookup"><span data-stu-id="7e832-120">FileSize</span></span> | <span data-ttu-id="7e832-121">int</span><span class="sxs-lookup"><span data-stu-id="7e832-121">int</span></span> | <span data-ttu-id="7e832-122">Dimensioni del file in byte</span><span class="sxs-lookup"><span data-stu-id="7e832-122">Size of the file in bytes</span></span> |
| <span data-ttu-id="7e832-123">GlobalPrevalence</span><span class="sxs-lookup"><span data-stu-id="7e832-123">GlobalPrevalence</span></span> | <span data-ttu-id="7e832-124">int</span><span class="sxs-lookup"><span data-stu-id="7e832-124">int</span></span> | <span data-ttu-id="7e832-125">Numero di istanze dell'entità osservate da Microsoft a livello globale</span><span class="sxs-lookup"><span data-stu-id="7e832-125">Number of instances of the entity observed by Microsoft globally</span></span> |
| <span data-ttu-id="7e832-126">GlobalFirstSeen</span><span class="sxs-lookup"><span data-stu-id="7e832-126">GlobalFirstSeen</span></span> | <span data-ttu-id="7e832-127">datetime</span><span class="sxs-lookup"><span data-stu-id="7e832-127">datetime</span></span> | <span data-ttu-id="7e832-128">Data e ora in cui l'entità è stata osservata per la prima volta da Microsoft a livello globale</span><span class="sxs-lookup"><span data-stu-id="7e832-128">Date and time when the entity was first observed by Microsoft globally</span></span> |
| <span data-ttu-id="7e832-129">GlobalLastSeen</span><span class="sxs-lookup"><span data-stu-id="7e832-129">GlobalLastSeen</span></span> | <span data-ttu-id="7e832-130">datetime</span><span class="sxs-lookup"><span data-stu-id="7e832-130">datetime</span></span> | <span data-ttu-id="7e832-131">Data e ora dell'ultima osservazione dell'entità da parte di Microsoft a livello globale</span><span class="sxs-lookup"><span data-stu-id="7e832-131">Date and time when the entity was last observed by Microsoft globally</span></span> |
| <span data-ttu-id="7e832-132">Firmatario</span><span class="sxs-lookup"><span data-stu-id="7e832-132">Signer</span></span> | <span data-ttu-id="7e832-133">stringa</span><span class="sxs-lookup"><span data-stu-id="7e832-133">string</span></span> | <span data-ttu-id="7e832-134">Informazioni sul firmatario del file</span><span class="sxs-lookup"><span data-stu-id="7e832-134">Information about the signer of the file</span></span> |
| <span data-ttu-id="7e832-135">Autorità di certificazione</span><span class="sxs-lookup"><span data-stu-id="7e832-135">Issuer</span></span> | <span data-ttu-id="7e832-136">stringa</span><span class="sxs-lookup"><span data-stu-id="7e832-136">string</span></span> | <span data-ttu-id="7e832-137">Informazioni sull'autorità di certificazione (CA) emittente</span><span class="sxs-lookup"><span data-stu-id="7e832-137">Information about the issuing certificate authority (CA)</span></span> |
| <span data-ttu-id="7e832-138">SignerHash</span><span class="sxs-lookup"><span data-stu-id="7e832-138">SignerHash</span></span> | <span data-ttu-id="7e832-139">stringa</span><span class="sxs-lookup"><span data-stu-id="7e832-139">string</span></span> | <span data-ttu-id="7e832-140">Valore hash univoco che identifica il firmatario</span><span class="sxs-lookup"><span data-stu-id="7e832-140">Unique hash value identifying the signer</span></span> |
| <span data-ttu-id="7e832-141">IsCertificateValid</span><span class="sxs-lookup"><span data-stu-id="7e832-141">IsCertificateValid</span></span> | <span data-ttu-id="7e832-142">boolean</span><span class="sxs-lookup"><span data-stu-id="7e832-142">boolean</span></span> | <span data-ttu-id="7e832-143">Indica se il certificato utilizzato per firmare il file è valido</span><span class="sxs-lookup"><span data-stu-id="7e832-143">Whether the certificate used to sign the file is valid</span></span> |
| <span data-ttu-id="7e832-144">IsRootSignerMicrosoft</span><span class="sxs-lookup"><span data-stu-id="7e832-144">IsRootSignerMicrosoft</span></span> | <span data-ttu-id="7e832-145">boolean</span><span class="sxs-lookup"><span data-stu-id="7e832-145">boolean</span></span> | <span data-ttu-id="7e832-146">Indica se il firmatario del certificato radice è Microsoft</span><span class="sxs-lookup"><span data-stu-id="7e832-146">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| <span data-ttu-id="7e832-147">IsExecutable</span><span class="sxs-lookup"><span data-stu-id="7e832-147">IsExecutable</span></span> | <span data-ttu-id="7e832-148">boolean</span><span class="sxs-lookup"><span data-stu-id="7e832-148">boolean</span></span> | <span data-ttu-id="7e832-149">Indica se il file è un file PE (Portable Executable)</span><span class="sxs-lookup"><span data-stu-id="7e832-149">Whether the file is a Portable Executable (PE) file</span></span> |
| <span data-ttu-id="7e832-150">ThreatName</span><span class="sxs-lookup"><span data-stu-id="7e832-150">ThreatName</span></span> | <span data-ttu-id="7e832-151">stringa</span><span class="sxs-lookup"><span data-stu-id="7e832-151">string</span></span> | <span data-ttu-id="7e832-152">Nome di rilevamento per qualsiasi malware o altre minacce rilevate</span><span class="sxs-lookup"><span data-stu-id="7e832-152">Detection name for any malware or other threats found</span></span> |
| <span data-ttu-id="7e832-153">Publisher</span><span class="sxs-lookup"><span data-stu-id="7e832-153">Publisher</span></span> | <span data-ttu-id="7e832-154">stringa</span><span class="sxs-lookup"><span data-stu-id="7e832-154">string</span></span> | <span data-ttu-id="7e832-155">Nome dell'organizzazione che ha pubblicato il file</span><span class="sxs-lookup"><span data-stu-id="7e832-155">Name of the organization that published the file</span></span> |
| <span data-ttu-id="7e832-156">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="7e832-156">SoftwareName</span></span> | <span data-ttu-id="7e832-157">stringa</span><span class="sxs-lookup"><span data-stu-id="7e832-157">string</span></span> | <span data-ttu-id="7e832-158">Nome del prodotto software</span><span class="sxs-lookup"><span data-stu-id="7e832-158">Name of the software product</span></span> |

## <a name="syntax"></a><span data-ttu-id="7e832-159">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7e832-159">Syntax</span></span>

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a><span data-ttu-id="7e832-160">Argomenti</span><span class="sxs-lookup"><span data-stu-id="7e832-160">Arguments</span></span>

- <span data-ttu-id="7e832-161">**x**-colonna ID file da utilizzare: `SHA1` , , o ; funzione utilizzata se non `SHA256` `InitiatingProcessSHA1` `InitiatingProcessSHA256` `SHA1` specificata</span><span class="sxs-lookup"><span data-stu-id="7e832-161">**x**—file ID column to use: `SHA1`, `SHA256`, `InitiatingProcessSHA1`, or `InitiatingProcessSHA256`; function uses `SHA1` if unspecified</span></span>
- <span data-ttu-id="7e832-162">**y**: limite al numero di record da arricchire, da 1 a 1000; utilizza 100 se non specificato</span><span class="sxs-lookup"><span data-stu-id="7e832-162">**y**—limit to the number of records to enrich, 1-1000; function uses 100 if unspecified</span></span>

## <a name="examples"></a><span data-ttu-id="7e832-163">Esempi</span><span class="sxs-lookup"><span data-stu-id="7e832-163">Examples</span></span>

### <a name="project-only-the-sha1-column-and-enrich-it"></a><span data-ttu-id="7e832-164">Proiettare solo la colonna SHA1 e arricchirla</span><span class="sxs-lookup"><span data-stu-id="7e832-164">Project only the SHA1 column and enrich it</span></span>

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a><span data-ttu-id="7e832-165">Arricchire i primi 500 record ed elencare i file a bassa diffusione</span><span class="sxs-lookup"><span data-stu-id="7e832-165">Enrich the first 500 records and list low-prevalence files</span></span>

```kusto
DeviceFileEvents
| where ActionType == "FileCreated" and Timestamp > ago(1d)
| project CreatedOn = Timestamp, FileName, FolderPath, SHA1
| invoke FileProfile("SHA1", 500) 
| where GlobalPrevalence < 15
```

## <a name="related-topics"></a><span data-ttu-id="7e832-166">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="7e832-166">Related topics</span></span>
- [<span data-ttu-id="7e832-167">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="7e832-167">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="7e832-168">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="7e832-168">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="7e832-169">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="7e832-169">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="7e832-170">Ottenere altri esempi di query</span><span class="sxs-lookup"><span data-stu-id="7e832-170">Get more query examples</span></span>](advanced-hunting-shared-queries.md)
