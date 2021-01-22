---
title: Tabella CloudAppEvents nello schema di ricerca avanzata
description: Informazioni sugli eventi dalle app e dai servizi cloud nella tabella CloudAppEvents dello schema di ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca delle minacce informatiche, microsoft threat protection, microsoft 365, mtp, m365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, CloudAppEvents, Cloud App Security, MCAS
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
ms.openlocfilehash: 021a8210bbe5886021e980b33ade0b9e2ded7b5b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928454"
---
# <a name="cloudappevents"></a><span data-ttu-id="2a6d4-104">CloudAppEvents</span><span class="sxs-lookup"><span data-stu-id="2a6d4-104">CloudAppEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="2a6d4-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="2a6d4-105">**Applies to:**</span></span>
- <span data-ttu-id="2a6d4-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2a6d4-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="2a6d4-107">Attualmente disponibile in anteprima, la tabella nello schema di ricerca avanzata contiene informazioni sulle attività in varie app e servizi cloud, in particolare `CloudAppEvents` Microsoft Teams ed Exchange Online. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="2a6d4-107">Currently available in preview, the `CloudAppEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about activities in various cloud apps and services, specifically Microsoft Teams and Exchange Online.</span></span> <span data-ttu-id="2a6d4-108">Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="2a6d4-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="2a6d4-109">Questa tabella verrà espansa per includere più attività monitorate da Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="2a6d4-109">This table will expand to include more activities monitored by Microsoft Cloud App Security.</span></span> <span data-ttu-id="2a6d4-110">In seguito, questa tabella includerà l'attività di file attualmente archiviata nella [tabella AppFileEvents.](advanced-hunting-appfileevents-table.md)</span><span class="sxs-lookup"><span data-stu-id="2a6d4-110">Eventually, this table will include file activity currently stored in the [AppFileEvents](advanced-hunting-appfileevents-table.md) table.</span></span> <span data-ttu-id="2a6d4-111">Microsoft fornirà indicazioni aggiuntive man quando si spostano più dati in questa tabella.</span><span class="sxs-lookup"><span data-stu-id="2a6d4-111">Microsoft will provide additional guidance as more data moves to this table.</span></span>

<span data-ttu-id="2a6d4-112">Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="2a6d4-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="2a6d4-113">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="2a6d4-113">Column name</span></span> | <span data-ttu-id="2a6d4-114">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="2a6d4-114">Data type</span></span> | <span data-ttu-id="2a6d4-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2a6d4-115">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="2a6d4-116">datetime</span><span class="sxs-lookup"><span data-stu-id="2a6d4-116">datetime</span></span> | <span data-ttu-id="2a6d4-117">Data e ora di registrazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="2a6d4-117">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="2a6d4-118">stringa</span><span class="sxs-lookup"><span data-stu-id="2a6d4-118">string</span></span> | <span data-ttu-id="2a6d4-119">Tipo di attività che ha attivato l'evento</span><span class="sxs-lookup"><span data-stu-id="2a6d4-119">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="2a6d4-120">stringa</span><span class="sxs-lookup"><span data-stu-id="2a6d4-120">string</span></span> | <span data-ttu-id="2a6d4-121">Applicazione che ha eseguito l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="2a6d4-121">Application that performed the recorded action</span></span> |
| `ApplicationId` | <span data-ttu-id="2a6d4-122">stringa</span><span class="sxs-lookup"><span data-stu-id="2a6d4-122">string</span></span> | <span data-ttu-id="2a6d4-123">Identificatore univoco dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="2a6d4-123">Unique identifier for the application</span></span> |
| `AccountObjectId` | <span data-ttu-id="2a6d4-124">stringa</span><span class="sxs-lookup"><span data-stu-id="2a6d4-124">string</span></span> | <span data-ttu-id="2a6d4-125">Identificatore univoco per l'account in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="2a6d4-125">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountDisplayName` | <span data-ttu-id="2a6d4-126">stringa</span><span class="sxs-lookup"><span data-stu-id="2a6d4-126">string</span></span> | <span data-ttu-id="2a6d4-127">Nome dell'utente dell'account visualizzato nella rubrica.</span><span class="sxs-lookup"><span data-stu-id="2a6d4-127">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="2a6d4-128">In genere una combinazione di un nome o di un dato nome, un'iniziazione intermedia e un cognome o un cognome.</span><span class="sxs-lookup"><span data-stu-id="2a6d4-128">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `IsAdminOperation` | <span data-ttu-id="2a6d4-129">stringa</span><span class="sxs-lookup"><span data-stu-id="2a6d4-129">string</span></span> | <span data-ttu-id="2a6d4-130">Indica se l'attività è stata eseguita da un amministratore</span><span class="sxs-lookup"><span data-stu-id="2a6d4-130">Indicates whether the activity was performed by an administrator</span></span> |
| `DeviceType` | <span data-ttu-id="2a6d4-131">stringa</span><span class="sxs-lookup"><span data-stu-id="2a6d4-131">string</span></span> | <span data-ttu-id="2a6d4-132">Tipo di dispositivo basato su scopo e funzionalità, ad esempio "Dispositivo di rete", "Workstation", "Server", "Mobile", "Console di gioco" o "Stampante"</span><span class="sxs-lookup"><span data-stu-id="2a6d4-132">Type of device based on purpose and functionality, such as "Network device", "Workstation", "Server", "Mobile", "Gaming console", or "Printer"</span></span> | 
| `OSPlatform` | <span data-ttu-id="2a6d4-133">stringa</span><span class="sxs-lookup"><span data-stu-id="2a6d4-133">string</span></span> | <span data-ttu-id="2a6d4-134">Piattaforma del sistema operativo in esecuzione nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2a6d4-134">Platform of the operating system running on the device.</span></span> <span data-ttu-id="2a6d4-135">Questa colonna indica sistemi operativi specifici, incluse le varianti all'interno della stessa famiglia, ad esempio Windows 10 e Windows 7.</span><span class="sxs-lookup"><span data-stu-id="2a6d4-135">This column indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="2a6d4-136">stringa</span><span class="sxs-lookup"><span data-stu-id="2a6d4-136">string</span></span> | <span data-ttu-id="2a6d4-137">Indirizzo IP assegnato all'endpoint e utilizzato durante le comunicazioni di rete correlate</span><span class="sxs-lookup"><span data-stu-id="2a6d4-137">IP address assigned to the endpoint and used during related network communications</span></span> |
| `IsAnonymousProxy` | <span data-ttu-id="2a6d4-138">stringa</span><span class="sxs-lookup"><span data-stu-id="2a6d4-138">string</span></span> | <span data-ttu-id="2a6d4-139">Indica se l'indirizzo IP appartiene a un proxy anonimo noto</span><span class="sxs-lookup"><span data-stu-id="2a6d4-139">Indicates whether the IP address belongs to a known anonymous proxy</span></span> |
| `CountryCode` | <span data-ttu-id="2a6d4-140">stringa</span><span class="sxs-lookup"><span data-stu-id="2a6d4-140">string</span></span> | <span data-ttu-id="2a6d4-141">Codice di due lettere che indica il paese in cui l'indirizzo IP del client è geolocato</span><span class="sxs-lookup"><span data-stu-id="2a6d4-141">Two-letter code indicating the country where the client IP address is geolocated</span></span> |
| `City` | <span data-ttu-id="2a6d4-142">stringa</span><span class="sxs-lookup"><span data-stu-id="2a6d4-142">string</span></span> | <span data-ttu-id="2a6d4-143">Città in cui l'indirizzo IP del client è geolocato</span><span class="sxs-lookup"><span data-stu-id="2a6d4-143">City where the client IP address is geolocated</span></span> |
| `Isp` | <span data-ttu-id="2a6d4-144">stringa</span><span class="sxs-lookup"><span data-stu-id="2a6d4-144">string</span></span> | <span data-ttu-id="2a6d4-145">Provider di servizi Internet (ISP) associato all'indirizzo IP</span><span class="sxs-lookup"><span data-stu-id="2a6d4-145">Internet service provider (ISP) associated with the IP address</span></span> |
| `UserAgent` | <span data-ttu-id="2a6d4-146">stringa</span><span class="sxs-lookup"><span data-stu-id="2a6d4-146">string</span></span> | <span data-ttu-id="2a6d4-147">Informazioni sull'agente utente dal Web browser o da un'altra applicazione client</span><span class="sxs-lookup"><span data-stu-id="2a6d4-147">User agent information from the web browser or other client application</span></span> |
| `ActivityType` | <span data-ttu-id="2a6d4-148">stringa</span><span class="sxs-lookup"><span data-stu-id="2a6d4-148">string</span></span> | <span data-ttu-id="2a6d4-149">Tipo di attività che ha attivato l'evento</span><span class="sxs-lookup"><span data-stu-id="2a6d4-149">Type of activity that triggered the event</span></span> |
| `ActivityObjects` | <span data-ttu-id="2a6d4-150">stringa</span><span class="sxs-lookup"><span data-stu-id="2a6d4-150">string</span></span> | <span data-ttu-id="2a6d4-151">Elenco di oggetti, ad esempio file o cartelle, coinvolti nell'attività registrata</span><span class="sxs-lookup"><span data-stu-id="2a6d4-151">List of objects, such as files or folders, that were involved in the recorded activity</span></span> |
| `ObjectName` | <span data-ttu-id="2a6d4-152">stringa</span><span class="sxs-lookup"><span data-stu-id="2a6d4-152">string</span></span> | <span data-ttu-id="2a6d4-153">Nome dell'oggetto a cui è stata applicata l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="2a6d4-153">Name of the object that the recorded action was applied to</span></span> |
| `ObjectType` | <span data-ttu-id="2a6d4-154">stringa</span><span class="sxs-lookup"><span data-stu-id="2a6d4-154">string</span></span> | <span data-ttu-id="2a6d4-155">Tipo di oggetto, ad esempio un file o una cartella, a cui è stata applicata l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="2a6d4-155">Type of object, such as a file or a folder, that the recorded action was applied to</span></span> |
| `ObjectId` | <span data-ttu-id="2a6d4-156">stringa</span><span class="sxs-lookup"><span data-stu-id="2a6d4-156">string</span></span> | <span data-ttu-id="2a6d4-157">Identificatore univoco dell'oggetto a cui è stata applicata l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="2a6d4-157">Unique identifier of the object that the recorded action was applied to</span></span> |
| `ReportId` | <span data-ttu-id="2a6d4-158">stringa</span><span class="sxs-lookup"><span data-stu-id="2a6d4-158">string</span></span> | <span data-ttu-id="2a6d4-159">Identificatore univoco dell'evento</span><span class="sxs-lookup"><span data-stu-id="2a6d4-159">Unique identifier for the event</span></span> |
| `RawEventData` | <span data-ttu-id="2a6d4-160">stringa</span><span class="sxs-lookup"><span data-stu-id="2a6d4-160">string</span></span> | <span data-ttu-id="2a6d4-161">Informazioni sugli eventi non elaborati dall'applicazione o dal servizio di origine in formato JSON</span><span class="sxs-lookup"><span data-stu-id="2a6d4-161">Raw event information from the source application or service in JSON format</span></span> |
| `AdditionalFields` | <span data-ttu-id="2a6d4-162">stringa</span><span class="sxs-lookup"><span data-stu-id="2a6d4-162">string</span></span> | <span data-ttu-id="2a6d4-163">Ulteriori informazioni sull'entità o sull'evento</span><span class="sxs-lookup"><span data-stu-id="2a6d4-163">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="2a6d4-164">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="2a6d4-164">Related topics</span></span>
- [<span data-ttu-id="2a6d4-165">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="2a6d4-165">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="2a6d4-166">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="2a6d4-166">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="2a6d4-167">Utilizzare le query condivise</span><span class="sxs-lookup"><span data-stu-id="2a6d4-167">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="2a6d4-168">Cercare tra dispositivi, posta elettronica, app e identità</span><span class="sxs-lookup"><span data-stu-id="2a6d4-168">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="2a6d4-169">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="2a6d4-169">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="2a6d4-170">Applicare le procedure consigliate per le query</span><span class="sxs-lookup"><span data-stu-id="2a6d4-170">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
