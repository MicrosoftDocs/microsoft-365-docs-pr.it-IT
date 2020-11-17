---
title: Tabella CloudAppEvents nello schema di caccia avanzato
description: Informazioni sugli eventi delle app e dei servizi cloud nella tabella CloudAppEvents dello schema di caccia avanzato
keywords: caccia avanzata, caccia alle minacce, Cyber-caccia alle minacce, Microsoft Threat Protection, Microsoft 365, MTP, M365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, CloudAppEvents, cloud app Security, MCAS
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
ms.openlocfilehash: 3cb4498e5db6a7752e99b8c677bc8936d2c975ef
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087767"
---
# <a name="cloudappevents"></a><span data-ttu-id="f7f0e-104">CloudAppEvents</span><span class="sxs-lookup"><span data-stu-id="f7f0e-104">CloudAppEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f7f0e-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="f7f0e-105">**Applies to:**</span></span>
- <span data-ttu-id="f7f0e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f7f0e-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="f7f0e-107">Attualmente disponibile in anteprima, la `CloudAppEvents` tabella nello schema di [caccia avanzato](advanced-hunting-overview.md) contiene informazioni sulle attività in diverse app e servizi cloud, in particolare Microsoft teams ed Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="f7f0e-107">Currently available in preview, the `CloudAppEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about activities in various cloud apps and services, specifically Microsoft Teams and Exchange Online.</span></span> <span data-ttu-id="f7f0e-108">Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="f7f0e-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="f7f0e-109">La tabella verrà espansa per includere più attività monitorate da Microsoft cloud app Security.</span><span class="sxs-lookup"><span data-stu-id="f7f0e-109">This table will expand to include more activities monitored by Microsoft Cloud App Security.</span></span> <span data-ttu-id="f7f0e-110">Alla fine, questa tabella includerà l'attività dei file attualmente archiviati nella tabella [AppFileEvents](advanced-hunting-appfileevents-table.md) .</span><span class="sxs-lookup"><span data-stu-id="f7f0e-110">Eventually, this table will include file activity currently stored in the [AppFileEvents](advanced-hunting-appfileevents-table.md) table.</span></span> <span data-ttu-id="f7f0e-111">Microsoft fornirà indicazioni aggiuntive per spostare i dati in questa tabella.</span><span class="sxs-lookup"><span data-stu-id="f7f0e-111">Microsoft will provide additional guidance as more data moves to this table.</span></span>

<span data-ttu-id="f7f0e-112">Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="f7f0e-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="f7f0e-113">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="f7f0e-113">Column name</span></span> | <span data-ttu-id="f7f0e-114">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="f7f0e-114">Data type</span></span> | <span data-ttu-id="f7f0e-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f7f0e-115">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="f7f0e-116">datetime</span><span class="sxs-lookup"><span data-stu-id="f7f0e-116">datetime</span></span> | <span data-ttu-id="f7f0e-117">Data e ora di registrazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="f7f0e-117">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="f7f0e-118">stringa</span><span class="sxs-lookup"><span data-stu-id="f7f0e-118">string</span></span> | <span data-ttu-id="f7f0e-119">Tipo di attività che ha attivato l'evento</span><span class="sxs-lookup"><span data-stu-id="f7f0e-119">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="f7f0e-120">stringa</span><span class="sxs-lookup"><span data-stu-id="f7f0e-120">string</span></span> | <span data-ttu-id="f7f0e-121">Applicazione in cui è stata eseguita l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="f7f0e-121">Application that performed the recorded action</span></span> |
| `ApplicationId` | <span data-ttu-id="f7f0e-122">stringa</span><span class="sxs-lookup"><span data-stu-id="f7f0e-122">string</span></span> | <span data-ttu-id="f7f0e-123">Identificatore univoco per l'applicazione</span><span class="sxs-lookup"><span data-stu-id="f7f0e-123">Unique identifier for the application</span></span> |
| `AccountObjectId` | <span data-ttu-id="f7f0e-124">stringa</span><span class="sxs-lookup"><span data-stu-id="f7f0e-124">string</span></span> | <span data-ttu-id="f7f0e-125">Identificatore univoco per l'account in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="f7f0e-125">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountDisplayName` | <span data-ttu-id="f7f0e-126">stringa</span><span class="sxs-lookup"><span data-stu-id="f7f0e-126">string</span></span> | <span data-ttu-id="f7f0e-127">Nome dell'account utente visualizzato nella rubrica.</span><span class="sxs-lookup"><span data-stu-id="f7f0e-127">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="f7f0e-128">In genere una combinazione di un nome o di un cognome, di un'iniziazione centrale e di un ultimo nome.</span><span class="sxs-lookup"><span data-stu-id="f7f0e-128">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `IsAdminOperation` | <span data-ttu-id="f7f0e-129">stringa</span><span class="sxs-lookup"><span data-stu-id="f7f0e-129">string</span></span> | <span data-ttu-id="f7f0e-130">Indica se l'attività è stata eseguita da un amministratore</span><span class="sxs-lookup"><span data-stu-id="f7f0e-130">Indicates whether the activity was performed by an administrator</span></span> |
| `DeviceType` | <span data-ttu-id="f7f0e-131">stringa</span><span class="sxs-lookup"><span data-stu-id="f7f0e-131">string</span></span> | <span data-ttu-id="f7f0e-132">Tipo di dispositivo basato su scopo e funzionalità, ad esempio "Network Device", "workstation", "Server", "mobile", "Gaming Console" o "Printer"</span><span class="sxs-lookup"><span data-stu-id="f7f0e-132">Type of device based on purpose and functionality, such as "Network device", "Workstation", "Server", "Mobile", "Gaming console", or "Printer"</span></span> | 
| `OSPlatform` | <span data-ttu-id="f7f0e-133">stringa</span><span class="sxs-lookup"><span data-stu-id="f7f0e-133">string</span></span> | <span data-ttu-id="f7f0e-134">Piattaforma del sistema operativo in esecuzione nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f7f0e-134">Platform of the operating system running on the device.</span></span> <span data-ttu-id="f7f0e-135">In questa colonna sono indicati sistemi operativi specifici, tra cui le varianti all'interno della stessa famiglia, ad esempio Windows 10 e Windows 7.</span><span class="sxs-lookup"><span data-stu-id="f7f0e-135">This column indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="f7f0e-136">stringa</span><span class="sxs-lookup"><span data-stu-id="f7f0e-136">string</span></span> | <span data-ttu-id="f7f0e-137">Indirizzo IP assegnato all'endpoint e utilizzato durante le comunicazioni di rete correlate</span><span class="sxs-lookup"><span data-stu-id="f7f0e-137">IP address assigned to the endpoint and used during related network communications</span></span> |
| `IsAnonymousProxy` | <span data-ttu-id="f7f0e-138">stringa</span><span class="sxs-lookup"><span data-stu-id="f7f0e-138">string</span></span> | <span data-ttu-id="f7f0e-139">Indica se l'indirizzo IP appartiene a un proxy anonimo conosciuto</span><span class="sxs-lookup"><span data-stu-id="f7f0e-139">Indicates whether the IP address belongs to a known anonymous proxy</span></span> |
| `CountryCode` | <span data-ttu-id="f7f0e-140">stringa</span><span class="sxs-lookup"><span data-stu-id="f7f0e-140">string</span></span> | <span data-ttu-id="f7f0e-141">Codice di due lettere che indica il paese in cui l'indirizzo IP del client è Geolocated</span><span class="sxs-lookup"><span data-stu-id="f7f0e-141">Two-letter code indicating the country where the client IP address is geolocated</span></span> |
| `City` | <span data-ttu-id="f7f0e-142">stringa</span><span class="sxs-lookup"><span data-stu-id="f7f0e-142">string</span></span> | <span data-ttu-id="f7f0e-143">Città in cui l'indirizzo IP del client è Geolocated</span><span class="sxs-lookup"><span data-stu-id="f7f0e-143">City where the client IP address is geolocated</span></span> |
| `Isp` | <span data-ttu-id="f7f0e-144">stringa</span><span class="sxs-lookup"><span data-stu-id="f7f0e-144">string</span></span> | <span data-ttu-id="f7f0e-145">Provider di servizi Internet (ISP) associato all'indirizzo IP</span><span class="sxs-lookup"><span data-stu-id="f7f0e-145">Internet service provider (ISP) associated with the IP address</span></span> |
| `UserAgent` | <span data-ttu-id="f7f0e-146">stringa</span><span class="sxs-lookup"><span data-stu-id="f7f0e-146">string</span></span> | <span data-ttu-id="f7f0e-147">Informazioni sull'agente utente dal Web browser o da un'altra applicazione client</span><span class="sxs-lookup"><span data-stu-id="f7f0e-147">User agent information from the web browser or other client application</span></span> |
| `ActivityType` | <span data-ttu-id="f7f0e-148">stringa</span><span class="sxs-lookup"><span data-stu-id="f7f0e-148">string</span></span> | <span data-ttu-id="f7f0e-149">Tipo di attività che ha attivato l'evento</span><span class="sxs-lookup"><span data-stu-id="f7f0e-149">Type of activity that triggered the event</span></span> |
| `ActivityObjects` | <span data-ttu-id="f7f0e-150">stringa</span><span class="sxs-lookup"><span data-stu-id="f7f0e-150">string</span></span> | <span data-ttu-id="f7f0e-151">Elenco di oggetti, ad esempio file o cartelle, che sono stati coinvolti nell'attività registrata</span><span class="sxs-lookup"><span data-stu-id="f7f0e-151">List of objects, such as files or folders, that were involved in the recorded activity</span></span> |
| `ObjectName` | <span data-ttu-id="f7f0e-152">stringa</span><span class="sxs-lookup"><span data-stu-id="f7f0e-152">string</span></span> | <span data-ttu-id="f7f0e-153">Nome dell'oggetto a cui è stata applicata l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="f7f0e-153">Name of the object that the recorded action was applied to</span></span> |
| `ObjectType` | <span data-ttu-id="f7f0e-154">stringa</span><span class="sxs-lookup"><span data-stu-id="f7f0e-154">string</span></span> | <span data-ttu-id="f7f0e-155">Tipo di oggetto, ad esempio un file o una cartella, a cui è stata applicata l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="f7f0e-155">Type of object, such as a file or a folder, that the recorded action was applied to</span></span> |
| `ObjectId` | <span data-ttu-id="f7f0e-156">stringa</span><span class="sxs-lookup"><span data-stu-id="f7f0e-156">string</span></span> | <span data-ttu-id="f7f0e-157">Identificatore univoco dell'oggetto a cui è stata applicata l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="f7f0e-157">Unique identifier of the object that the recorded action was applied to</span></span> |
| `ReportId` | <span data-ttu-id="f7f0e-158">stringa</span><span class="sxs-lookup"><span data-stu-id="f7f0e-158">string</span></span> | <span data-ttu-id="f7f0e-159">Identificatore univoco per l'evento</span><span class="sxs-lookup"><span data-stu-id="f7f0e-159">Unique identifier for the event</span></span> |
| `RawEventData` | <span data-ttu-id="f7f0e-160">stringa</span><span class="sxs-lookup"><span data-stu-id="f7f0e-160">string</span></span> | <span data-ttu-id="f7f0e-161">Informazioni sugli eventi RAW dall'applicazione o dal servizio di origine in formato JSON</span><span class="sxs-lookup"><span data-stu-id="f7f0e-161">Raw event information from the source application or service in JSON format</span></span> |
| `AdditionalFields` | <span data-ttu-id="f7f0e-162">stringa</span><span class="sxs-lookup"><span data-stu-id="f7f0e-162">string</span></span> | <span data-ttu-id="f7f0e-163">Ulteriori informazioni sull'entità o sull'evento</span><span class="sxs-lookup"><span data-stu-id="f7f0e-163">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="f7f0e-164">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="f7f0e-164">Related topics</span></span>
- [<span data-ttu-id="f7f0e-165">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="f7f0e-165">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="f7f0e-166">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="f7f0e-166">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="f7f0e-167">Utilizzare le query condivise</span><span class="sxs-lookup"><span data-stu-id="f7f0e-167">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="f7f0e-168">Cercare tra dispositivi, posta elettronica, app e identità</span><span class="sxs-lookup"><span data-stu-id="f7f0e-168">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="f7f0e-169">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="f7f0e-169">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="f7f0e-170">Applicare le procedure consigliate per le query</span><span class="sxs-lookup"><span data-stu-id="f7f0e-170">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
