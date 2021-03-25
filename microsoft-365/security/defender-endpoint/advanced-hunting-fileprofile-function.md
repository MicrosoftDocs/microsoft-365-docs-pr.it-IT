---
title: Funzione FileProfile() nella ricerca avanzata per Microsoft Defender for Endpoint
description: Informazioni su come utilizzare FileProfile() per migliorare le informazioni sui file nei risultati delle query di ricerca avanzate
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, mdatp, Microsoft Defender ATP, Microsoft Defender for Endpoint, Windows Defender, Windows Defender ATP, Windows Defender Advanced Threat Protection, ricerca, query, telemetria, riferimento allo schema, kusto, FileProfile, profilo file, funzione, arricchimento
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 09/20/2020
ms.technology: mde
ms.openlocfilehash: 668b3fe503268c46e4a1313f0c4cfb8a6a3dd602
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51067970"
---
# <a name="fileprofile"></a><span data-ttu-id="337aa-104">FileProfile()</span><span class="sxs-lookup"><span data-stu-id="337aa-104">FileProfile()</span></span>

<span data-ttu-id="337aa-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="337aa-105">**Applies to:**</span></span>
- [<span data-ttu-id="337aa-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="337aa-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

<span data-ttu-id="337aa-107">La funzione è una funzione di arricchimento nella ricerca avanzata che aggiunge i dati seguenti ai `FileProfile()` file trovati dalla query. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="337aa-107">The `FileProfile()` function is an enrichment function in [advanced hunting](advanced-hunting-overview.md) that adds the following data to files found by the query.</span></span>

<span data-ttu-id="337aa-108">Colonna</span><span class="sxs-lookup"><span data-stu-id="337aa-108">Column</span></span> | <span data-ttu-id="337aa-109">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="337aa-109">Data type</span></span> | <span data-ttu-id="337aa-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="337aa-110">Description</span></span>
-|-|-
<span data-ttu-id="337aa-111">SHA1</span><span class="sxs-lookup"><span data-stu-id="337aa-111">SHA1</span></span> | <span data-ttu-id="337aa-112">stringa</span><span class="sxs-lookup"><span data-stu-id="337aa-112">string</span></span> | <span data-ttu-id="337aa-113">SHA-1 del file a cui è stata applicata l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="337aa-113">SHA-1 of the file that the recorded action was applied to</span></span>
<span data-ttu-id="337aa-114">SHA256</span><span class="sxs-lookup"><span data-stu-id="337aa-114">SHA256</span></span> | <span data-ttu-id="337aa-115">stringa</span><span class="sxs-lookup"><span data-stu-id="337aa-115">string</span></span> | <span data-ttu-id="337aa-116">SHA-256 del file a cui è stata applicata l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="337aa-116">SHA-256 of the file that the recorded action was applied to</span></span>
<span data-ttu-id="337aa-117">MD5</span><span class="sxs-lookup"><span data-stu-id="337aa-117">MD5</span></span> | <span data-ttu-id="337aa-118">stringa</span><span class="sxs-lookup"><span data-stu-id="337aa-118">string</span></span> | <span data-ttu-id="337aa-119">Hash MD5 del file a cui è stata applicata l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="337aa-119">MD5 hash of the file that the recorded action was applied to</span></span>
<span data-ttu-id="337aa-120">FileSize</span><span class="sxs-lookup"><span data-stu-id="337aa-120">FileSize</span></span> | <span data-ttu-id="337aa-121">int</span><span class="sxs-lookup"><span data-stu-id="337aa-121">int</span></span> | <span data-ttu-id="337aa-122">Dimensioni del file in byte</span><span class="sxs-lookup"><span data-stu-id="337aa-122">Size of the file in bytes</span></span>
<span data-ttu-id="337aa-123">GlobalPrevalence</span><span class="sxs-lookup"><span data-stu-id="337aa-123">GlobalPrevalence</span></span> | <span data-ttu-id="337aa-124">int</span><span class="sxs-lookup"><span data-stu-id="337aa-124">int</span></span> | <span data-ttu-id="337aa-125">Numero di istanze dell'entità osservate da Microsoft a livello globale</span><span class="sxs-lookup"><span data-stu-id="337aa-125">Number of instances of the entity observed by Microsoft globally</span></span>
<span data-ttu-id="337aa-126">GlobalFirstSeen</span><span class="sxs-lookup"><span data-stu-id="337aa-126">GlobalFirstSeen</span></span> | <span data-ttu-id="337aa-127">datetime</span><span class="sxs-lookup"><span data-stu-id="337aa-127">datetime</span></span> | <span data-ttu-id="337aa-128">Data e ora in cui l'entità è stata osservata per la prima volta da Microsoft a livello globale</span><span class="sxs-lookup"><span data-stu-id="337aa-128">Date and time when the entity was first observed by Microsoft globally</span></span>
<span data-ttu-id="337aa-129">GlobalLastSeen</span><span class="sxs-lookup"><span data-stu-id="337aa-129">GlobalLastSeen</span></span> | <span data-ttu-id="337aa-130">datetime</span><span class="sxs-lookup"><span data-stu-id="337aa-130">datetime</span></span> | <span data-ttu-id="337aa-131">Data e ora dell'ultima osservazione dell'entità da parte di Microsoft a livello globale</span><span class="sxs-lookup"><span data-stu-id="337aa-131">Date and time when the entity was last observed by Microsoft globally</span></span>
<span data-ttu-id="337aa-132">Firmatario</span><span class="sxs-lookup"><span data-stu-id="337aa-132">Signer</span></span> | <span data-ttu-id="337aa-133">stringa</span><span class="sxs-lookup"><span data-stu-id="337aa-133">string</span></span> | <span data-ttu-id="337aa-134">Informazioni sul firmatario del file</span><span class="sxs-lookup"><span data-stu-id="337aa-134">Information about the signer of the file</span></span>
<span data-ttu-id="337aa-135">Autorità di certificazione</span><span class="sxs-lookup"><span data-stu-id="337aa-135">Issuer</span></span> | <span data-ttu-id="337aa-136">stringa</span><span class="sxs-lookup"><span data-stu-id="337aa-136">string</span></span> | <span data-ttu-id="337aa-137">Informazioni sull'autorità di certificazione (CA) emittente</span><span class="sxs-lookup"><span data-stu-id="337aa-137">Information about the issuing certificate authority (CA)</span></span>
<span data-ttu-id="337aa-138">SignerHash</span><span class="sxs-lookup"><span data-stu-id="337aa-138">SignerHash</span></span> | <span data-ttu-id="337aa-139">stringa</span><span class="sxs-lookup"><span data-stu-id="337aa-139">string</span></span> | <span data-ttu-id="337aa-140">Valore hash univoco che identifica il firmatario</span><span class="sxs-lookup"><span data-stu-id="337aa-140">Unique hash value identifying the signer</span></span>
<span data-ttu-id="337aa-141">IsCertificateValid</span><span class="sxs-lookup"><span data-stu-id="337aa-141">IsCertificateValid</span></span> | <span data-ttu-id="337aa-142">boolean</span><span class="sxs-lookup"><span data-stu-id="337aa-142">boolean</span></span> | <span data-ttu-id="337aa-143">Indica se il certificato utilizzato per firmare il file è valido</span><span class="sxs-lookup"><span data-stu-id="337aa-143">Whether the certificate used to sign the file is valid</span></span>
<span data-ttu-id="337aa-144">IsRootSignerMicrosoft</span><span class="sxs-lookup"><span data-stu-id="337aa-144">IsRootSignerMicrosoft</span></span> | <span data-ttu-id="337aa-145">boolean</span><span class="sxs-lookup"><span data-stu-id="337aa-145">boolean</span></span> | <span data-ttu-id="337aa-146">Indica se il firmatario del certificato radice è Microsoft</span><span class="sxs-lookup"><span data-stu-id="337aa-146">Indicates whether the signer of the root certificate is Microsoft</span></span>
<span data-ttu-id="337aa-147">IsExecutable</span><span class="sxs-lookup"><span data-stu-id="337aa-147">IsExecutable</span></span> | <span data-ttu-id="337aa-148">boolean</span><span class="sxs-lookup"><span data-stu-id="337aa-148">boolean</span></span> | <span data-ttu-id="337aa-149">Indica se il file è un file PE (Portable Executable)</span><span class="sxs-lookup"><span data-stu-id="337aa-149">Whether the file is a Portable Executable (PE) file</span></span>
<span data-ttu-id="337aa-150">ThreatName</span><span class="sxs-lookup"><span data-stu-id="337aa-150">ThreatName</span></span> | <span data-ttu-id="337aa-151">stringa</span><span class="sxs-lookup"><span data-stu-id="337aa-151">string</span></span> | <span data-ttu-id="337aa-152">Nome di rilevamento per qualsiasi malware o altre minacce rilevate</span><span class="sxs-lookup"><span data-stu-id="337aa-152">Detection name for any malware or other threats found</span></span>
<span data-ttu-id="337aa-153">Publisher</span><span class="sxs-lookup"><span data-stu-id="337aa-153">Publisher</span></span> | <span data-ttu-id="337aa-154">stringa</span><span class="sxs-lookup"><span data-stu-id="337aa-154">string</span></span> | <span data-ttu-id="337aa-155">Nome dell'organizzazione che ha pubblicato il file</span><span class="sxs-lookup"><span data-stu-id="337aa-155">Name of the organization that published the file</span></span>
<span data-ttu-id="337aa-156">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="337aa-156">SoftwareName</span></span> | <span data-ttu-id="337aa-157">stringa</span><span class="sxs-lookup"><span data-stu-id="337aa-157">string</span></span> | <span data-ttu-id="337aa-158">Nome del prodotto software</span><span class="sxs-lookup"><span data-stu-id="337aa-158">Name of the software product</span></span>

## <a name="syntax"></a><span data-ttu-id="337aa-159">Sintassi</span><span class="sxs-lookup"><span data-stu-id="337aa-159">Syntax</span></span>

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a><span data-ttu-id="337aa-160">Argomenti</span><span class="sxs-lookup"><span data-stu-id="337aa-160">Arguments</span></span>

- <span data-ttu-id="337aa-161">**x** - Colonna ID file da utilizzare: `SHA1` , o ; se non `SHA256` `InitiatingProcessSHA1` `InitiatingProcessSHA256` `SHA1` specificata, viene utilizzata la funzione</span><span class="sxs-lookup"><span data-stu-id="337aa-161">**x** — file ID column to use: `SHA1`, `SHA256`, `InitiatingProcessSHA1` or `InitiatingProcessSHA256`; function uses `SHA1` if unspecified</span></span>
- <span data-ttu-id="337aa-162">**y** — limite al numero di record da arricchire, da 1 a 1000; la funzione utilizza 100 se non specificato</span><span class="sxs-lookup"><span data-stu-id="337aa-162">**y** — limit to the number of records to enrich, 1-1000; function uses 100 if unspecified</span></span>

## <a name="examples"></a><span data-ttu-id="337aa-163">Esempi</span><span class="sxs-lookup"><span data-stu-id="337aa-163">Examples</span></span>

### <a name="project-only-the-sha1-column-and-enrich-it"></a><span data-ttu-id="337aa-164">Proiettare solo la colonna SHA1 e arricchirla</span><span class="sxs-lookup"><span data-stu-id="337aa-164">Project only the SHA1 column and enrich it</span></span>

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a><span data-ttu-id="337aa-165">Arricchire i primi 500 record ed elencare i file a bassa prevalenza</span><span class="sxs-lookup"><span data-stu-id="337aa-165">Enrich the first 500 records and list low-prevalence files</span></span>

```kusto
DeviceFileEvents
| where ActionType == "FileCreated" and Timestamp > ago(1d)
| project CreatedOn = Timestamp, FileName, FolderPath, SHA1
| invoke FileProfile("SHA1", 500) 
| where GlobalPrevalence < 15
```

## <a name="related-topics"></a><span data-ttu-id="337aa-166">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="337aa-166">Related topics</span></span>

- [<span data-ttu-id="337aa-167">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="337aa-167">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="337aa-168">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="337aa-168">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="337aa-169">Comprensione dello schema</span><span class="sxs-lookup"><span data-stu-id="337aa-169">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
