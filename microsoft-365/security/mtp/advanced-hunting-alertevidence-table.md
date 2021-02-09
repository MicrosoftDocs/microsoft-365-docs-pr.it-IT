---
title: Tabella AlertEvidence nello schema di ricerca avanzata
description: Informazioni sulle informazioni associate agli avvisi nella tabella AlertEvidence dello schema di ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca delle minacce informatiche, microsoft threat protection, Microsoft 365, mtp, m365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, AlertInfo, avviso, entità, prova, file, indirizzo IP, dispositivo, computer, utente, account
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
ms.openlocfilehash: 7457084d49c5a9fef4ef79abc7702c6b473efcd2
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145302"
---
# <a name="alertevidence"></a><span data-ttu-id="fdf8b-104">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="fdf8b-104">AlertEvidence</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="fdf8b-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="fdf8b-105">**Applies to:**</span></span>
- <span data-ttu-id="fdf8b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fdf8b-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="fdf8b-107">La tabella nello schema di ricerca avanzata contiene informazioni su varie entità( file, indirizzi IP, URL, utenti o dispositivi) associate agli avvisi di `AlertEvidence` Microsoft Defender per Endpoint, Microsoft Defender per Office 365, Microsoft Cloud App Security e Microsoft Defender for Identity. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="fdf8b-107">The `AlertEvidence` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about various entities—files, IP addresses, URLs, users, or devices—associated with alerts from Microsoft  Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="fdf8b-108">Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="fdf8b-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="fdf8b-109">Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="fdf8b-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="fdf8b-110">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="fdf8b-110">Column name</span></span> | <span data-ttu-id="fdf8b-111">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="fdf8b-111">Data type</span></span> | <span data-ttu-id="fdf8b-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fdf8b-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="fdf8b-113">datetime</span><span class="sxs-lookup"><span data-stu-id="fdf8b-113">datetime</span></span> | <span data-ttu-id="fdf8b-114">Data e ora di registrazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="fdf8b-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="fdf8b-115">stringa</span><span class="sxs-lookup"><span data-stu-id="fdf8b-115">string</span></span> | <span data-ttu-id="fdf8b-116">Identificatore univoco dell'avviso</span><span class="sxs-lookup"><span data-stu-id="fdf8b-116">Unique identifier for the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="fdf8b-117">stringa</span><span class="sxs-lookup"><span data-stu-id="fdf8b-117">string</span></span> | <span data-ttu-id="fdf8b-118">Prodotto o servizio che ha fornito le informazioni sull'avviso</span><span class="sxs-lookup"><span data-stu-id="fdf8b-118">Product or service that provided the alert information</span></span> |
| `EntityType` | <span data-ttu-id="fdf8b-119">stringa</span><span class="sxs-lookup"><span data-stu-id="fdf8b-119">string</span></span> | <span data-ttu-id="fdf8b-120">Tipo di oggetto, ad esempio un file, un processo, un dispositivo o un utente</span><span class="sxs-lookup"><span data-stu-id="fdf8b-120">Type of object, such as a file, a process, a device, or a user</span></span> |
| `EvidenceRole` | <span data-ttu-id="fdf8b-121">stringa</span><span class="sxs-lookup"><span data-stu-id="fdf8b-121">string</span></span> | <span data-ttu-id="fdf8b-122">In che modo l'entità è coinvolta in un avviso, che indica se è influenzata o è semplicemente correlata</span><span class="sxs-lookup"><span data-stu-id="fdf8b-122">How the entity is involved in an alert, indicating whether it is impacted or is merely related</span></span> |
| `EvidenceDirection` | <span data-ttu-id="fdf8b-123">stringa</span><span class="sxs-lookup"><span data-stu-id="fdf8b-123">string</span></span> | <span data-ttu-id="fdf8b-124">Indica se l'entità è l'origine o la destinazione di una connessione di rete</span><span class="sxs-lookup"><span data-stu-id="fdf8b-124">Indicates whether the entity is the source or the destination of a network connection</span></span> |
| `FileName` | <span data-ttu-id="fdf8b-125">stringa</span><span class="sxs-lookup"><span data-stu-id="fdf8b-125">string</span></span> | <span data-ttu-id="fdf8b-126">Nome del file a cui è stata applicata l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="fdf8b-126">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="fdf8b-127">stringa</span><span class="sxs-lookup"><span data-stu-id="fdf8b-127">string</span></span> | <span data-ttu-id="fdf8b-128">Cartella contenente il file a cui è stata applicata l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="fdf8b-128">Folder containing the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="fdf8b-129">stringa</span><span class="sxs-lookup"><span data-stu-id="fdf8b-129">string</span></span> | <span data-ttu-id="fdf8b-130">SHA-1 del file a cui è stata applicata l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="fdf8b-130">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="fdf8b-131">stringa</span><span class="sxs-lookup"><span data-stu-id="fdf8b-131">string</span></span> | <span data-ttu-id="fdf8b-132">SHA-256 del file a cui è stata applicata l'azione registrata.</span><span class="sxs-lookup"><span data-stu-id="fdf8b-132">SHA-256 of the file that the recorded action was applied to.</span></span> <span data-ttu-id="fdf8b-133">Questo campo in genere non viene popolato: usa la colonna SHA1 quando disponibile.</span><span class="sxs-lookup"><span data-stu-id="fdf8b-133">This field is usually not populated—use the SHA1 column when available.</span></span> |
| `FileSize` | <span data-ttu-id="fdf8b-134">int</span><span class="sxs-lookup"><span data-stu-id="fdf8b-134">int</span></span> | <span data-ttu-id="fdf8b-135">Dimensioni del file in byte</span><span class="sxs-lookup"><span data-stu-id="fdf8b-135">Size of the file in bytes</span></span> |
| `ThreatFamily` | <span data-ttu-id="fdf8b-136">stringa</span><span class="sxs-lookup"><span data-stu-id="fdf8b-136">string</span></span> | <span data-ttu-id="fdf8b-137">Famiglia di malware in cui è stato classificato il file o il processo sospetto o dannoso</span><span class="sxs-lookup"><span data-stu-id="fdf8b-137">Malware family that the suspicious or malicious file or process has been classified under</span></span> |
| `RemoteIP` | <span data-ttu-id="fdf8b-138">stringa</span><span class="sxs-lookup"><span data-stu-id="fdf8b-138">string</span></span> | <span data-ttu-id="fdf8b-139">Indirizzo IP connesso a</span><span class="sxs-lookup"><span data-stu-id="fdf8b-139">IP address that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="fdf8b-140">stringa</span><span class="sxs-lookup"><span data-stu-id="fdf8b-140">string</span></span> | <span data-ttu-id="fdf8b-141">URL o nome di dominio completo (FQDN) connesso a</span><span class="sxs-lookup"><span data-stu-id="fdf8b-141">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `AccountName` | <span data-ttu-id="fdf8b-142">stringa</span><span class="sxs-lookup"><span data-stu-id="fdf8b-142">string</span></span> | <span data-ttu-id="fdf8b-143">Nome utente dell'account</span><span class="sxs-lookup"><span data-stu-id="fdf8b-143">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="fdf8b-144">stringa</span><span class="sxs-lookup"><span data-stu-id="fdf8b-144">string</span></span> | <span data-ttu-id="fdf8b-145">Dominio dell'account</span><span class="sxs-lookup"><span data-stu-id="fdf8b-145">Domain of the account</span></span> |
| `AccountSid` | <span data-ttu-id="fdf8b-146">stringa</span><span class="sxs-lookup"><span data-stu-id="fdf8b-146">string</span></span> | <span data-ttu-id="fdf8b-147">Identificatore di sicurezza (SID) dell'account</span><span class="sxs-lookup"><span data-stu-id="fdf8b-147">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="fdf8b-148">stringa</span><span class="sxs-lookup"><span data-stu-id="fdf8b-148">string</span></span> | <span data-ttu-id="fdf8b-149">Identificatore univoco per l'account in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="fdf8b-149">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountUpn` | <span data-ttu-id="fdf8b-150">stringa</span><span class="sxs-lookup"><span data-stu-id="fdf8b-150">string</span></span> | <span data-ttu-id="fdf8b-151">Nome dell'entità utente (UPN) dell'account</span><span class="sxs-lookup"><span data-stu-id="fdf8b-151">User principal name (UPN) of the account</span></span> |
| `DeviceId` | <span data-ttu-id="fdf8b-152">stringa</span><span class="sxs-lookup"><span data-stu-id="fdf8b-152">string</span></span> | <span data-ttu-id="fdf8b-153">Identificatore univoco del dispositivo nel servizio</span><span class="sxs-lookup"><span data-stu-id="fdf8b-153">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="fdf8b-154">stringa</span><span class="sxs-lookup"><span data-stu-id="fdf8b-154">string</span></span> | <span data-ttu-id="fdf8b-155">Nome di dominio completo (FQDN) del computer</span><span class="sxs-lookup"><span data-stu-id="fdf8b-155">Fully qualified domain name (FQDN) of the machine</span></span> |
| `LocalIP` | <span data-ttu-id="fdf8b-156">stringa</span><span class="sxs-lookup"><span data-stu-id="fdf8b-156">string</span></span> | <span data-ttu-id="fdf8b-157">Indirizzo IP assegnato al dispositivo locale utilizzato durante la comunicazione</span><span class="sxs-lookup"><span data-stu-id="fdf8b-157">IP address assigned to the local device used during communication</span></span> |
| `NetworkMessageId` | <span data-ttu-id="fdf8b-158">stringa</span><span class="sxs-lookup"><span data-stu-id="fdf8b-158">string</span></span> | <span data-ttu-id="fdf8b-159">Identificatore univoco per la posta elettronica, generato da Office 365</span><span class="sxs-lookup"><span data-stu-id="fdf8b-159">Unique identifier for the email, generated by Office 365</span></span> |
| `EmailSubject` | <span data-ttu-id="fdf8b-160">stringa</span><span class="sxs-lookup"><span data-stu-id="fdf8b-160">string</span></span> | <span data-ttu-id="fdf8b-161">Oggetto del messaggio di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="fdf8b-161">Subject of the email</span></span> |
| `ApplicationId` | <span data-ttu-id="fdf8b-162">stringa</span><span class="sxs-lookup"><span data-stu-id="fdf8b-162">string</span></span> | <span data-ttu-id="fdf8b-163">Identificatore univoco dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="fdf8b-163">Unique identifier for the application</span></span> |
| `Application` | <span data-ttu-id="fdf8b-164">stringa</span><span class="sxs-lookup"><span data-stu-id="fdf8b-164">string</span></span> | <span data-ttu-id="fdf8b-165">Applicazione che ha eseguito l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="fdf8b-165">Application that performed the recorded action</span></span> |
| `ProcessCommandLine` | <span data-ttu-id="fdf8b-166">stringa</span><span class="sxs-lookup"><span data-stu-id="fdf8b-166">string</span></span> | <span data-ttu-id="fdf8b-167">Riga di comando utilizzata per creare il nuovo processo</span><span class="sxs-lookup"><span data-stu-id="fdf8b-167">Command line used to create the new process</span></span> |
| `AdditionalFields` | <span data-ttu-id="fdf8b-168">stringa</span><span class="sxs-lookup"><span data-stu-id="fdf8b-168">string</span></span> | <span data-ttu-id="fdf8b-169">Ulteriori informazioni sull'evento in formato matrice JSON</span><span class="sxs-lookup"><span data-stu-id="fdf8b-169">Additional information about the event in JSON array format</span></span> |
| `RegistryKey` |<span data-ttu-id="fdf8b-170">stringa</span><span class="sxs-lookup"><span data-stu-id="fdf8b-170">string</span></span> | <span data-ttu-id="fdf8b-171">Chiave del Registro di sistema a cui è stata applicata l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="fdf8b-171">Registry key that the recorded action was applied to</span></span> |
| `RegistryValueName` |<span data-ttu-id="fdf8b-172">stringa</span><span class="sxs-lookup"><span data-stu-id="fdf8b-172">string</span></span> | <span data-ttu-id="fdf8b-173">Nome del valore del Registro di sistema a cui è stata applicata l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="fdf8b-173">Name of the registry value that the recorded action was applied to</span></span> |
| `RegistryValueData` |<span data-ttu-id="fdf8b-174">stringa</span><span class="sxs-lookup"><span data-stu-id="fdf8b-174">string</span></span> | <span data-ttu-id="fdf8b-175">Dati del valore del Registro di sistema a cui è stata applicata l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="fdf8b-175">Data of the registry value that the recorded action was applied to</span></span> |

## <a name="related-topics"></a><span data-ttu-id="fdf8b-176">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="fdf8b-176">Related topics</span></span>
- [<span data-ttu-id="fdf8b-177">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="fdf8b-177">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="fdf8b-178">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="fdf8b-178">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="fdf8b-179">Utilizzare le query condivise</span><span class="sxs-lookup"><span data-stu-id="fdf8b-179">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="fdf8b-180">Cercare tra dispositivi, posta elettronica, app e identità</span><span class="sxs-lookup"><span data-stu-id="fdf8b-180">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="fdf8b-181">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="fdf8b-181">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="fdf8b-182">Applicare le procedure consigliate per le query</span><span class="sxs-lookup"><span data-stu-id="fdf8b-182">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
