---
title: Tabella AlertEvidence nello schema di caccia avanzato
description: Informazioni sui file, sull'indirizzo di rete, sull'utente o sul dispositivo associati a avvisi generati nella tabella AlertEvidence dello schema di caccia avanzato
keywords: caccia avanzata, caccia alle minacce, Cyber-caccia alle minacce, Microsoft Threat Protection, Microsoft 365, MTP, M365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, AlertInfo, avviso, entità, evidenza, file, indirizzo IP, dispositivo, computer, utente, account
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
ms.openlocfilehash: 1a58d1e5db2ea8689d4909e6e9c47b08a6e94d34
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929242"
---
# <a name="alertevidence"></a><span data-ttu-id="0c264-104">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="0c264-104">AlertEvidence</span></span>

<span data-ttu-id="0c264-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="0c264-105">**Applies to:**</span></span>
- <span data-ttu-id="0c264-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="0c264-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="0c264-107">La `AlertEvidence` tabella nello schema di [ricerca avanzata](advanced-hunting-overview.md) contiene informazioni su diverse entità, ovvero file, indirizzi IP, URL, utenti o dispositivi, associati a avvisi di Microsoft Defender ATP, Office 365 ATP, Microsoft cloud app Security e Azure ATP.</span><span class="sxs-lookup"><span data-stu-id="0c264-107">The `AlertEvidence` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about various entities — files, IP addresses, URLs, users, or devices — associated with alerts from Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="0c264-108">Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="0c264-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="0c264-109">Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="0c264-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="0c264-110">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="0c264-110">Column name</span></span> | <span data-ttu-id="0c264-111">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="0c264-111">Data type</span></span> | <span data-ttu-id="0c264-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0c264-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="0c264-113">datetime</span><span class="sxs-lookup"><span data-stu-id="0c264-113">datetime</span></span> | <span data-ttu-id="0c264-114">Data e ora di registrazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="0c264-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="0c264-115">stringa</span><span class="sxs-lookup"><span data-stu-id="0c264-115">string</span></span> | <span data-ttu-id="0c264-116">Identificatore univoco dell'avviso</span><span class="sxs-lookup"><span data-stu-id="0c264-116">Unique identifier for the alert</span></span> |
| `EntityType` | <span data-ttu-id="0c264-117">stringa</span><span class="sxs-lookup"><span data-stu-id="0c264-117">string</span></span> | <span data-ttu-id="0c264-118">Tipo di oggetto, ad esempio un file, un processo, un dispositivo o un utente</span><span class="sxs-lookup"><span data-stu-id="0c264-118">Type of object, such as a file, a process, a device, or a user</span></span> |
| `EvidenceRole` | <span data-ttu-id="0c264-119">stringa</span><span class="sxs-lookup"><span data-stu-id="0c264-119">string</span></span> | <span data-ttu-id="0c264-120">In che modo l'entità è coinvolta in un avviso, che indica se ha un impatto o è semplicemente correlato</span><span class="sxs-lookup"><span data-stu-id="0c264-120">How the entity is involved in an alert, indicating whether it is impacted or is merely related</span></span> |
| `SHA1` | <span data-ttu-id="0c264-121">stringa</span><span class="sxs-lookup"><span data-stu-id="0c264-121">string</span></span> | <span data-ttu-id="0c264-122">SHA-1 del file a cui è stata applicata l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="0c264-122">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="0c264-123">stringa</span><span class="sxs-lookup"><span data-stu-id="0c264-123">string</span></span> | <span data-ttu-id="0c264-124">SHA-256 del file a cui è stata applicata l'azione registrata.</span><span class="sxs-lookup"><span data-stu-id="0c264-124">SHA-256 of the file that the recorded action was applied to.</span></span> <span data-ttu-id="0c264-125">Questo campo in genere non viene popolato, se disponibile, utilizzare la colonna SHA1.</span><span class="sxs-lookup"><span data-stu-id="0c264-125">This field is usually not populated—use the SHA1 column when available.</span></span> |
| `RemoteIP` | <span data-ttu-id="0c264-126">stringa</span><span class="sxs-lookup"><span data-stu-id="0c264-126">string</span></span> | <span data-ttu-id="0c264-127">Indirizzo IP connesso a</span><span class="sxs-lookup"><span data-stu-id="0c264-127">IP address that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="0c264-128">stringa</span><span class="sxs-lookup"><span data-stu-id="0c264-128">string</span></span> | <span data-ttu-id="0c264-129">URL o nome di dominio completo (FQDN) connesso a</span><span class="sxs-lookup"><span data-stu-id="0c264-129">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `AccountName` | <span data-ttu-id="0c264-130">stringa</span><span class="sxs-lookup"><span data-stu-id="0c264-130">string</span></span> | <span data-ttu-id="0c264-131">Nome utente dell'account</span><span class="sxs-lookup"><span data-stu-id="0c264-131">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="0c264-132">stringa</span><span class="sxs-lookup"><span data-stu-id="0c264-132">string</span></span> | <span data-ttu-id="0c264-133">Dominio dell'account</span><span class="sxs-lookup"><span data-stu-id="0c264-133">Domain of the account</span></span> |
| `AccountSid` | <span data-ttu-id="0c264-134">stringa</span><span class="sxs-lookup"><span data-stu-id="0c264-134">string</span></span> | <span data-ttu-id="0c264-135">ID di sicurezza (SID) dell'account</span><span class="sxs-lookup"><span data-stu-id="0c264-135">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="0c264-136">stringa</span><span class="sxs-lookup"><span data-stu-id="0c264-136">string</span></span> | <span data-ttu-id="0c264-137">Identificatore univoco per l'account in Azure AD</span><span class="sxs-lookup"><span data-stu-id="0c264-137">Unique identifier for the account in Azure AD</span></span> |
| `DeviceId` | <span data-ttu-id="0c264-138">stringa</span><span class="sxs-lookup"><span data-stu-id="0c264-138">string</span></span> | <span data-ttu-id="0c264-139">Identificatore univoco per il computer nel servizio</span><span class="sxs-lookup"><span data-stu-id="0c264-139">Unique identifier for the machine in the service</span></span> |
| `ThreatFamily` | <span data-ttu-id="0c264-140">stringa</span><span class="sxs-lookup"><span data-stu-id="0c264-140">string</span></span> | <span data-ttu-id="0c264-141">Famiglia di malware che il processo o il file sospetto o dannoso sono stati classificati in</span><span class="sxs-lookup"><span data-stu-id="0c264-141">Malware family that the suspicious or malicious file or process has been classified under</span></span> |
| `EvidenceDirection` | <span data-ttu-id="0c264-142">stringa</span><span class="sxs-lookup"><span data-stu-id="0c264-142">string</span></span> | <span data-ttu-id="0c264-143">Indica se l'entità è l'origine o la destinazione di una connessione di rete</span><span class="sxs-lookup"><span data-stu-id="0c264-143">Indicates whether the entity is the source or the destination of a network connection</span></span> |
| `AdditionalFields` | <span data-ttu-id="0c264-144">stringa</span><span class="sxs-lookup"><span data-stu-id="0c264-144">string</span></span> | <span data-ttu-id="0c264-145">Ulteriori informazioni sull'evento nel formato di matrice JSON</span><span class="sxs-lookup"><span data-stu-id="0c264-145">Additional information about the event in JSON array format</span></span> |

## <a name="related-topics"></a><span data-ttu-id="0c264-146">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="0c264-146">Related topics</span></span>
- [<span data-ttu-id="0c264-147">Ricerca proattiva delle minacce</span><span class="sxs-lookup"><span data-stu-id="0c264-147">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="0c264-148">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="0c264-148">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="0c264-149">Utilizzare le query condivise</span><span class="sxs-lookup"><span data-stu-id="0c264-149">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="0c264-150">Ricerca delle minacce attraverso dispositivi e posta elettronica</span><span class="sxs-lookup"><span data-stu-id="0c264-150">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="0c264-151">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="0c264-151">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="0c264-152">Applicare le procedure consigliate per le query</span><span class="sxs-lookup"><span data-stu-id="0c264-152">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
