---
title: Funzione fileprofile () in Advanced Hunting for Microsoft Threat Protection
description: Informazioni su come utilizzare il fileprofile () per arricchire i dati dei file nei risultati della query di ricerca avanzata
keywords: caccia avanzata, caccia alle minacce, Cyber-caccia alle minacce, Microsoft Threat Protection, Microsoft 365, MTP, M365, ricerca, query, telemetria, riferimento allo schema, kusto, fileprofile, profilo file, funzione, arricchimento
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 3fc563c762e7cd00888665b63e66159e4d3d9612
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196978"
---
# <a name="fileprofile"></a><span data-ttu-id="e1093-104">FileProfile()</span><span class="sxs-lookup"><span data-stu-id="e1093-104">FileProfile()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e1093-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="e1093-105">**Applies to:**</span></span>
- <span data-ttu-id="e1093-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="e1093-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="e1093-107">La `FileProfile()` funzione è una funzione di arricchimento nella [ricerca avanzata](advanced-hunting-overview.md) che consente di aggiungere i dati seguenti ai file trovati dalla query.</span><span class="sxs-lookup"><span data-stu-id="e1093-107">The `FileProfile()` function is an enrichment function in [advanced hunting](advanced-hunting-overview.md) that adds the following data to files found by the query.</span></span>

| <span data-ttu-id="e1093-108">Colonna</span><span class="sxs-lookup"><span data-stu-id="e1093-108">Column</span></span> | <span data-ttu-id="e1093-109">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="e1093-109">Data type</span></span> | <span data-ttu-id="e1093-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e1093-110">Description</span></span> |
|------------|-------------|-------------|
| <span data-ttu-id="e1093-111">SHA1</span><span class="sxs-lookup"><span data-stu-id="e1093-111">SHA1</span></span> | <span data-ttu-id="e1093-112">stringa</span><span class="sxs-lookup"><span data-stu-id="e1093-112">string</span></span> | <span data-ttu-id="e1093-113">SHA-1 del file a cui è stata applicata l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="e1093-113">SHA-1 of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="e1093-114">SHA256</span><span class="sxs-lookup"><span data-stu-id="e1093-114">SHA256</span></span> | <span data-ttu-id="e1093-115">stringa</span><span class="sxs-lookup"><span data-stu-id="e1093-115">string</span></span> | <span data-ttu-id="e1093-116">SHA-256 del file a cui è stata applicata l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="e1093-116">SHA-256 of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="e1093-117">MD5</span><span class="sxs-lookup"><span data-stu-id="e1093-117">MD5</span></span> | <span data-ttu-id="e1093-118">stringa</span><span class="sxs-lookup"><span data-stu-id="e1093-118">string</span></span> | <span data-ttu-id="e1093-119">Hash MD5 del file a cui è stata applicata l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="e1093-119">MD5 hash of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="e1093-120">FileSize</span><span class="sxs-lookup"><span data-stu-id="e1093-120">FileSize</span></span> | <span data-ttu-id="e1093-121">int</span><span class="sxs-lookup"><span data-stu-id="e1093-121">int</span></span> | <span data-ttu-id="e1093-122">Dimensione del file in byte</span><span class="sxs-lookup"><span data-stu-id="e1093-122">Size of the file in bytes</span></span> |
| <span data-ttu-id="e1093-123">GlobalPrevalence</span><span class="sxs-lookup"><span data-stu-id="e1093-123">GlobalPrevalence</span></span> | <span data-ttu-id="e1093-124">int</span><span class="sxs-lookup"><span data-stu-id="e1093-124">int</span></span> | <span data-ttu-id="e1093-125">Numero di istanze dell'entità osservate da Microsoft a livello globale</span><span class="sxs-lookup"><span data-stu-id="e1093-125">Number of instances of the entity observed by Microsoft globally</span></span> |
| <span data-ttu-id="e1093-126">GlobalFirstSeen</span><span class="sxs-lookup"><span data-stu-id="e1093-126">GlobalFirstSeen</span></span> | <span data-ttu-id="e1093-127">datetime</span><span class="sxs-lookup"><span data-stu-id="e1093-127">datetime</span></span> | <span data-ttu-id="e1093-128">Data e ora in cui l'entità è stata osservata per la prima volta da Microsoft globalmente</span><span class="sxs-lookup"><span data-stu-id="e1093-128">Date and time when the entity was first observed by Microsoft globally</span></span> |
| <span data-ttu-id="e1093-129">GlobalLastSeen</span><span class="sxs-lookup"><span data-stu-id="e1093-129">GlobalLastSeen</span></span> | <span data-ttu-id="e1093-130">datetime</span><span class="sxs-lookup"><span data-stu-id="e1093-130">datetime</span></span> | <span data-ttu-id="e1093-131">Data e ora in cui l'entità è stata osservata per l'ultima volta da Microsoft globalmente</span><span class="sxs-lookup"><span data-stu-id="e1093-131">Date and time when the entity was last observed by Microsoft globally</span></span> |
| <span data-ttu-id="e1093-132">Firmatario</span><span class="sxs-lookup"><span data-stu-id="e1093-132">Signer</span></span> | <span data-ttu-id="e1093-133">stringa</span><span class="sxs-lookup"><span data-stu-id="e1093-133">string</span></span> | <span data-ttu-id="e1093-134">Informazioni sul firmatario del file</span><span class="sxs-lookup"><span data-stu-id="e1093-134">Information about the signer of the file</span></span> |
| <span data-ttu-id="e1093-135">Autorità di certificazione</span><span class="sxs-lookup"><span data-stu-id="e1093-135">Issuer</span></span> | <span data-ttu-id="e1093-136">stringa</span><span class="sxs-lookup"><span data-stu-id="e1093-136">string</span></span> | <span data-ttu-id="e1093-137">Informazioni sull'autorità di certificazione (CA) di emissione</span><span class="sxs-lookup"><span data-stu-id="e1093-137">Information about the issuing certificate authority (CA)</span></span> |
| <span data-ttu-id="e1093-138">SignerHash</span><span class="sxs-lookup"><span data-stu-id="e1093-138">SignerHash</span></span> | <span data-ttu-id="e1093-139">stringa</span><span class="sxs-lookup"><span data-stu-id="e1093-139">string</span></span> | <span data-ttu-id="e1093-140">Valore hash univoco che identifica il firmatario</span><span class="sxs-lookup"><span data-stu-id="e1093-140">Unique hash value identifying the signer</span></span> |
| <span data-ttu-id="e1093-141">IsCertificateValid</span><span class="sxs-lookup"><span data-stu-id="e1093-141">IsCertificateValid</span></span> | <span data-ttu-id="e1093-142">boolean</span><span class="sxs-lookup"><span data-stu-id="e1093-142">boolean</span></span> | <span data-ttu-id="e1093-143">Se il certificato utilizzato per firmare il file è valido</span><span class="sxs-lookup"><span data-stu-id="e1093-143">Whether the certificate used to sign the file is valid</span></span> |
| <span data-ttu-id="e1093-144">IsRootSignerMicrosoft</span><span class="sxs-lookup"><span data-stu-id="e1093-144">IsRootSignerMicrosoft</span></span> | <span data-ttu-id="e1093-145">boolean</span><span class="sxs-lookup"><span data-stu-id="e1093-145">boolean</span></span> | <span data-ttu-id="e1093-146">Indica se il firmatario del certificato radice è Microsoft</span><span class="sxs-lookup"><span data-stu-id="e1093-146">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| <span data-ttu-id="e1093-147">IsExecutable</span><span class="sxs-lookup"><span data-stu-id="e1093-147">IsExecutable</span></span> | <span data-ttu-id="e1093-148">boolean</span><span class="sxs-lookup"><span data-stu-id="e1093-148">boolean</span></span> | <span data-ttu-id="e1093-149">Se il file è un file eseguibile (PE) portatile</span><span class="sxs-lookup"><span data-stu-id="e1093-149">Whether the file is a Portable Executable (PE) file</span></span> |
| <span data-ttu-id="e1093-150">Threatname</span><span class="sxs-lookup"><span data-stu-id="e1093-150">ThreatName</span></span> | <span data-ttu-id="e1093-151">stringa</span><span class="sxs-lookup"><span data-stu-id="e1093-151">string</span></span> | <span data-ttu-id="e1093-152">Nome del rilevamento per qualsiasi malware o altre minacce trovate</span><span class="sxs-lookup"><span data-stu-id="e1093-152">Detection name for any malware or other threats found</span></span> |
| <span data-ttu-id="e1093-153">Publisher</span><span class="sxs-lookup"><span data-stu-id="e1093-153">Publisher</span></span> | <span data-ttu-id="e1093-154">stringa</span><span class="sxs-lookup"><span data-stu-id="e1093-154">string</span></span> | <span data-ttu-id="e1093-155">Nome dell'organizzazione che ha pubblicato il file</span><span class="sxs-lookup"><span data-stu-id="e1093-155">Name of the organization that published the file</span></span> |
| <span data-ttu-id="e1093-156">Softwarename</span><span class="sxs-lookup"><span data-stu-id="e1093-156">SoftwareName</span></span> | <span data-ttu-id="e1093-157">stringa</span><span class="sxs-lookup"><span data-stu-id="e1093-157">string</span></span> | <span data-ttu-id="e1093-158">Nome del prodotto software</span><span class="sxs-lookup"><span data-stu-id="e1093-158">Name of the software product</span></span> |

## <a name="syntax"></a><span data-ttu-id="e1093-159">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e1093-159">Syntax</span></span>

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a><span data-ttu-id="e1093-160">Argomenti</span><span class="sxs-lookup"><span data-stu-id="e1093-160">Arguments</span></span>

- <span data-ttu-id="e1093-161">**x** -colonna ID file da utilizzare: `SHA1` , `SHA256` `InitiatingProcessSHA1` o, `InitiatingProcessSHA256` se non specificata, viene utilizzata una funzione. `SHA1`</span><span class="sxs-lookup"><span data-stu-id="e1093-161">**x** — file ID column to use: `SHA1`, `SHA256`, `InitiatingProcessSHA1` or `InitiatingProcessSHA256`; function uses `SHA1` if unspecified</span></span>
- <span data-ttu-id="e1093-162">**y** -limitare il numero di record da arricchire, 1-1000; la funzione utilizza 100 se non specificata</span><span class="sxs-lookup"><span data-stu-id="e1093-162">**y** — limit to the number of records to enrich, 1-1000; function uses 100 if unspecified</span></span>

## <a name="examples"></a><span data-ttu-id="e1093-163">Esempi</span><span class="sxs-lookup"><span data-stu-id="e1093-163">Examples</span></span>

### <a name="project-only-the-sha1-column-and-enrich-it"></a><span data-ttu-id="e1093-164">Proiettare solo la colonna SHA1 e arricchirla</span><span class="sxs-lookup"><span data-stu-id="e1093-164">Project only the SHA1 column and enrich it</span></span>

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a><span data-ttu-id="e1093-165">Arricchire i primi 500 record ed elencare i file di bassa prevalenza</span><span class="sxs-lookup"><span data-stu-id="e1093-165">Enrich the first 500 records and list low-prevalence files</span></span>

```kusto
DeviceFileEvents
| where ActionType == "FileCreated" and Timestamp > ago(1d)
| project CreatedOn = Timestamp, FileName, FolderPath, SHA1
| invoke FileProfile("SHA1", 500) 
| where GlobalPrevalence < 15
```

## <a name="related-topics"></a><span data-ttu-id="e1093-166">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="e1093-166">Related topics</span></span>
- [<span data-ttu-id="e1093-167">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="e1093-167">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="e1093-168">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="e1093-168">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="e1093-169">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="e1093-169">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="e1093-170">Ottenere altri esempi di query</span><span class="sxs-lookup"><span data-stu-id="e1093-170">Get more query examples</span></span>](advanced-hunting-shared-queries.md)
