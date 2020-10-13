---
title: Tabella AlertEvidence nello schema di caccia avanzato
description: Informazioni sui dati associati agli avvisi nella tabella AlertEvidence dello schema di caccia avanzato
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 7f6a4f7592e6a8fde0b7ae6269f07ce7f76a5730
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430164"
---
# <a name="alertevidence"></a><span data-ttu-id="54dea-104">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="54dea-104">AlertEvidence</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="54dea-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="54dea-105">**Applies to:**</span></span>
- <span data-ttu-id="54dea-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="54dea-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="54dea-107">La `AlertEvidence` tabella nello schema di [ricerca avanzata](advanced-hunting-overview.md) contiene informazioni su diverse entità, ovvero file, indirizzi IP, URL, utenti o dispositivi, associati a avvisi di Microsoft Defender atp, Office 365 ATP, Microsoft cloud app Security e Azure ATP.</span><span class="sxs-lookup"><span data-stu-id="54dea-107">The `AlertEvidence` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about various entities—files, IP addresses, URLs, users, or devices—associated with alerts from Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="54dea-108">Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="54dea-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="54dea-109">Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="54dea-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="54dea-110">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="54dea-110">Column name</span></span> | <span data-ttu-id="54dea-111">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="54dea-111">Data type</span></span> | <span data-ttu-id="54dea-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="54dea-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="54dea-113">datetime</span><span class="sxs-lookup"><span data-stu-id="54dea-113">datetime</span></span> | <span data-ttu-id="54dea-114">Data e ora di registrazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="54dea-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="54dea-115">stringa</span><span class="sxs-lookup"><span data-stu-id="54dea-115">string</span></span> | <span data-ttu-id="54dea-116">Identificatore univoco dell'avviso</span><span class="sxs-lookup"><span data-stu-id="54dea-116">Unique identifier for the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="54dea-117">stringa</span><span class="sxs-lookup"><span data-stu-id="54dea-117">string</span></span> | <span data-ttu-id="54dea-118">Prodotto o servizio che ha fornito le informazioni sugli avvisi</span><span class="sxs-lookup"><span data-stu-id="54dea-118">Product or service that provided the alert information</span></span> |
| `EntityType` | <span data-ttu-id="54dea-119">stringa</span><span class="sxs-lookup"><span data-stu-id="54dea-119">string</span></span> | <span data-ttu-id="54dea-120">Tipo di oggetto, ad esempio un file, un processo, un dispositivo o un utente</span><span class="sxs-lookup"><span data-stu-id="54dea-120">Type of object, such as a file, a process, a device, or a user</span></span> |
| `EvidenceRole` | <span data-ttu-id="54dea-121">stringa</span><span class="sxs-lookup"><span data-stu-id="54dea-121">string</span></span> | <span data-ttu-id="54dea-122">In che modo l'entità è coinvolta in un avviso, che indica se ha un impatto o è semplicemente correlato</span><span class="sxs-lookup"><span data-stu-id="54dea-122">How the entity is involved in an alert, indicating whether it is impacted or is merely related</span></span> |
| `EvidenceDirection` | <span data-ttu-id="54dea-123">stringa</span><span class="sxs-lookup"><span data-stu-id="54dea-123">string</span></span> | <span data-ttu-id="54dea-124">Indica se l'entità è l'origine o la destinazione di una connessione di rete</span><span class="sxs-lookup"><span data-stu-id="54dea-124">Indicates whether the entity is the source or the destination of a network connection</span></span> |
| `FileName` | <span data-ttu-id="54dea-125">stringa</span><span class="sxs-lookup"><span data-stu-id="54dea-125">string</span></span> | <span data-ttu-id="54dea-126">Nome del file a cui è stata applicata l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="54dea-126">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="54dea-127">stringa</span><span class="sxs-lookup"><span data-stu-id="54dea-127">string</span></span> | <span data-ttu-id="54dea-128">Cartella contenente il file a cui è stata applicata l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="54dea-128">Folder containing the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="54dea-129">stringa</span><span class="sxs-lookup"><span data-stu-id="54dea-129">string</span></span> | <span data-ttu-id="54dea-130">SHA-1 del file a cui è stata applicata l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="54dea-130">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="54dea-131">stringa</span><span class="sxs-lookup"><span data-stu-id="54dea-131">string</span></span> | <span data-ttu-id="54dea-132">SHA-256 del file a cui è stata applicata l'azione registrata.</span><span class="sxs-lookup"><span data-stu-id="54dea-132">SHA-256 of the file that the recorded action was applied to.</span></span> <span data-ttu-id="54dea-133">Questo campo in genere non viene popolato, se disponibile, utilizzare la colonna SHA1.</span><span class="sxs-lookup"><span data-stu-id="54dea-133">This field is usually not populated—use the SHA1 column when available.</span></span> |
| `FileSize` | <span data-ttu-id="54dea-134">int</span><span class="sxs-lookup"><span data-stu-id="54dea-134">int</span></span> | <span data-ttu-id="54dea-135">Dimensione del file in byte</span><span class="sxs-lookup"><span data-stu-id="54dea-135">Size of the file in bytes</span></span> |
| `ThreatFamily` | <span data-ttu-id="54dea-136">stringa</span><span class="sxs-lookup"><span data-stu-id="54dea-136">string</span></span> | <span data-ttu-id="54dea-137">Famiglia di malware che il processo o il file sospetto o dannoso sono stati classificati in</span><span class="sxs-lookup"><span data-stu-id="54dea-137">Malware family that the suspicious or malicious file or process has been classified under</span></span> |
| `RemoteIP` | <span data-ttu-id="54dea-138">stringa</span><span class="sxs-lookup"><span data-stu-id="54dea-138">string</span></span> | <span data-ttu-id="54dea-139">Indirizzo IP connesso a</span><span class="sxs-lookup"><span data-stu-id="54dea-139">IP address that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="54dea-140">stringa</span><span class="sxs-lookup"><span data-stu-id="54dea-140">string</span></span> | <span data-ttu-id="54dea-141">URL o nome di dominio completo (FQDN) connesso a</span><span class="sxs-lookup"><span data-stu-id="54dea-141">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `AccountName` | <span data-ttu-id="54dea-142">stringa</span><span class="sxs-lookup"><span data-stu-id="54dea-142">string</span></span> | <span data-ttu-id="54dea-143">Nome utente dell'account</span><span class="sxs-lookup"><span data-stu-id="54dea-143">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="54dea-144">stringa</span><span class="sxs-lookup"><span data-stu-id="54dea-144">string</span></span> | <span data-ttu-id="54dea-145">Dominio dell'account</span><span class="sxs-lookup"><span data-stu-id="54dea-145">Domain of the account</span></span> |
| `AccountSid` | <span data-ttu-id="54dea-146">stringa</span><span class="sxs-lookup"><span data-stu-id="54dea-146">string</span></span> | <span data-ttu-id="54dea-147">ID di sicurezza (SID) dell'account</span><span class="sxs-lookup"><span data-stu-id="54dea-147">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="54dea-148">stringa</span><span class="sxs-lookup"><span data-stu-id="54dea-148">string</span></span> | <span data-ttu-id="54dea-149">Identificatore univoco per l'account in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="54dea-149">Unique identifier for the account in Azure Active Directory</span></span> |
| `DeviceId` | <span data-ttu-id="54dea-150">stringa</span><span class="sxs-lookup"><span data-stu-id="54dea-150">string</span></span> | <span data-ttu-id="54dea-151">Identificatore univoco per il dispositivo nel servizio</span><span class="sxs-lookup"><span data-stu-id="54dea-151">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="54dea-152">stringa</span><span class="sxs-lookup"><span data-stu-id="54dea-152">string</span></span> | <span data-ttu-id="54dea-153">Nome di dominio completo (FQDN) del computer</span><span class="sxs-lookup"><span data-stu-id="54dea-153">Fully qualified domain name (FQDN) of the machine</span></span> |
| `LocalIP` | <span data-ttu-id="54dea-154">stringa</span><span class="sxs-lookup"><span data-stu-id="54dea-154">string</span></span> | <span data-ttu-id="54dea-155">Indirizzo IP assegnato al dispositivo locale utilizzato durante la comunicazione</span><span class="sxs-lookup"><span data-stu-id="54dea-155">IP address assigned to the local device used during communication</span></span> |
| `NetworkMessageId` | <span data-ttu-id="54dea-156">stringa</span><span class="sxs-lookup"><span data-stu-id="54dea-156">string</span></span> | <span data-ttu-id="54dea-157">Identificatore univoco per la posta elettronica, generato da Office 365</span><span class="sxs-lookup"><span data-stu-id="54dea-157">Unique identifier for the email, generated by Office 365</span></span> |
| `EmailSubject` | <span data-ttu-id="54dea-158">stringa</span><span class="sxs-lookup"><span data-stu-id="54dea-158">string</span></span> | <span data-ttu-id="54dea-159">Oggetto del messaggio di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="54dea-159">Subject of the email</span></span> |
| `ApplicationId` | <span data-ttu-id="54dea-160">stringa</span><span class="sxs-lookup"><span data-stu-id="54dea-160">string</span></span> | <span data-ttu-id="54dea-161">Identificatore univoco per l'applicazione</span><span class="sxs-lookup"><span data-stu-id="54dea-161">Unique identifier for the application</span></span> |
| `Application` | <span data-ttu-id="54dea-162">stringa</span><span class="sxs-lookup"><span data-stu-id="54dea-162">string</span></span> | <span data-ttu-id="54dea-163">Applicazione in cui è stata eseguita l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="54dea-163">Application that performed the recorded action</span></span> |
| `ProcessCommandLine` | <span data-ttu-id="54dea-164">stringa</span><span class="sxs-lookup"><span data-stu-id="54dea-164">string</span></span> | <span data-ttu-id="54dea-165">Riga di comando utilizzata per creare il nuovo processo</span><span class="sxs-lookup"><span data-stu-id="54dea-165">Command line used to create the new process</span></span> |
| `AdditionalFields` | <span data-ttu-id="54dea-166">stringa</span><span class="sxs-lookup"><span data-stu-id="54dea-166">string</span></span> | <span data-ttu-id="54dea-167">Ulteriori informazioni sull'evento nel formato di matrice JSON</span><span class="sxs-lookup"><span data-stu-id="54dea-167">Additional information about the event in JSON array format</span></span> |

## <a name="related-topics"></a><span data-ttu-id="54dea-168">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="54dea-168">Related topics</span></span>
- [<span data-ttu-id="54dea-169">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="54dea-169">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="54dea-170">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="54dea-170">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="54dea-171">Utilizzare le query condivise</span><span class="sxs-lookup"><span data-stu-id="54dea-171">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="54dea-172">Cercare tra dispositivi, posta elettronica, app e identità</span><span class="sxs-lookup"><span data-stu-id="54dea-172">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="54dea-173">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="54dea-173">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="54dea-174">Applicare le procedure consigliate per le query</span><span class="sxs-lookup"><span data-stu-id="54dea-174">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
