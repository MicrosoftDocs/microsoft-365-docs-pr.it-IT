---
title: Tabella CloudAppEvents nello schema di ricerca avanzata
description: Informazioni sugli eventi da app e servizi cloud nella tabella CloudAppEvents dello schema di ricerca avanzata
keywords: ricerca avanzata, ricerca di minacce, ricerca di minacce informatiche, protezione dalle minacce Microsoft, Microsoft 365, mtp, m365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, CloudAppEvents, Cloud App Security, MCAS
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 2aa592e70bce7bb469f851bedc542ee58cac0037
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498670"
---
# <a name="cloudappevents"></a><span data-ttu-id="936bd-104">CloudAppEvents</span><span class="sxs-lookup"><span data-stu-id="936bd-104">CloudAppEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="936bd-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="936bd-105">**Applies to:**</span></span>
- <span data-ttu-id="936bd-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="936bd-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="936bd-107">La tabella nello schema di ricerca avanzata contiene informazioni sulle attività in varie app e servizi cloud trattati da Microsoft Cloud App Security, in particolare `CloudAppEvents` Dropbox, Exchange Online, [](advanced-hunting-overview.md) OneDrive, Microsoft Teams e SharePoint.</span><span class="sxs-lookup"><span data-stu-id="936bd-107">The `CloudAppEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about activities in various cloud apps and services covered by Microsoft Cloud App Security, specifically Dropbox, Exchange Online, OneDrive, Microsoft Teams, and SharePoint.</span></span> <span data-ttu-id="936bd-108">Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="936bd-108">Use this reference to construct queries that return information from this table.</span></span>

>[!IMPORTANT]
><span data-ttu-id="936bd-109">In questa tabella sono incluse le informazioni disponibili nella `AppFileEvents` tabella.</span><span class="sxs-lookup"><span data-stu-id="936bd-109">This table includes information that used to be available in the `AppFileEvents` table.</span></span> <span data-ttu-id="936bd-110">A partire dal 7 marzo 2021, gli utenti che ricercano le attività correlate ai file nei servizi cloud entro e oltre questa data devono utilizzare la `CloudAppEvents` tabella.</span><span class="sxs-lookup"><span data-stu-id="936bd-110">Starting March 7, 2021, users hunting through file-related activities in cloud services on and beyond this date should use the `CloudAppEvents` table instead.</span></span> <br><br><span data-ttu-id="936bd-111">Assicurarsi di cercare query e regole di rilevamento personalizzate che ancora usano la tabella e `AppFileEvents` modificarle per utilizzare la `CloudAppEvents` tabella.</span><span class="sxs-lookup"><span data-stu-id="936bd-111">Make sure to search for queries and custom detection rules that still use the `AppFileEvents` table and edit them to use the `CloudAppEvents` table.</span></span> <span data-ttu-id="936bd-112">Altre indicazioni sulla conversione delle query interessate sono disponibili in [Hunt across cloud app activities with Microsoft 365 Defender advanced hunting.](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857)</span><span class="sxs-lookup"><span data-stu-id="936bd-112">More guidance about converting affected queries can be found in [Hunt across cloud app activities with Microsoft 365 Defender advanced hunting](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857).</span></span>


<span data-ttu-id="936bd-113">Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="936bd-113">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="936bd-114">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="936bd-114">Column name</span></span> | <span data-ttu-id="936bd-115">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="936bd-115">Data type</span></span> | <span data-ttu-id="936bd-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="936bd-116">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="936bd-117">datetime</span><span class="sxs-lookup"><span data-stu-id="936bd-117">datetime</span></span> | <span data-ttu-id="936bd-118">Data e ora di registrazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="936bd-118">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="936bd-119">stringa</span><span class="sxs-lookup"><span data-stu-id="936bd-119">string</span></span> | <span data-ttu-id="936bd-120">Tipo di attività che ha attivato l'evento</span><span class="sxs-lookup"><span data-stu-id="936bd-120">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="936bd-121">stringa</span><span class="sxs-lookup"><span data-stu-id="936bd-121">string</span></span> | <span data-ttu-id="936bd-122">Applicazione che ha eseguito l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="936bd-122">Application that performed the recorded action</span></span> |
| `ApplicationId` | <span data-ttu-id="936bd-123">stringa</span><span class="sxs-lookup"><span data-stu-id="936bd-123">string</span></span> | <span data-ttu-id="936bd-124">Identificatore univoco dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="936bd-124">Unique identifier for the application</span></span> |
| `AccountObjectId` | <span data-ttu-id="936bd-125">stringa</span><span class="sxs-lookup"><span data-stu-id="936bd-125">string</span></span> | <span data-ttu-id="936bd-126">Identificatore univoco dell'account in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="936bd-126">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountDisplayName` | <span data-ttu-id="936bd-127">stringa</span><span class="sxs-lookup"><span data-stu-id="936bd-127">string</span></span> | <span data-ttu-id="936bd-128">Nome dell'utente dell'account visualizzato nella rubrica.</span><span class="sxs-lookup"><span data-stu-id="936bd-128">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="936bd-129">In genere una combinazione di un nome o di un dato nome, un'iniziazione intermedia e un cognome o un cognome.</span><span class="sxs-lookup"><span data-stu-id="936bd-129">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `IsAdminOperation` | <span data-ttu-id="936bd-130">stringa</span><span class="sxs-lookup"><span data-stu-id="936bd-130">string</span></span> | <span data-ttu-id="936bd-131">Indica se l'attività è stata eseguita da un amministratore</span><span class="sxs-lookup"><span data-stu-id="936bd-131">Indicates whether the activity was performed by an administrator</span></span> |
| `DeviceType` | <span data-ttu-id="936bd-132">stringa</span><span class="sxs-lookup"><span data-stu-id="936bd-132">string</span></span> | <span data-ttu-id="936bd-133">Tipo di dispositivo basato su scopo e funzionalità, ad esempio "Dispositivo di rete", "Workstation", "Server", "Mobile", "Console di gioco" o "Stampante"</span><span class="sxs-lookup"><span data-stu-id="936bd-133">Type of device based on purpose and functionality, such as "Network device", "Workstation", "Server", "Mobile", "Gaming console", or "Printer"</span></span> | 
| `OSPlatform` | <span data-ttu-id="936bd-134">stringa</span><span class="sxs-lookup"><span data-stu-id="936bd-134">string</span></span> | <span data-ttu-id="936bd-135">Piattaforma del sistema operativo in esecuzione nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="936bd-135">Platform of the operating system running on the device.</span></span> <span data-ttu-id="936bd-136">Questa colonna indica sistemi operativi specifici, incluse le varianti della stessa famiglia, ad esempio Windows 10 e Windows 7.</span><span class="sxs-lookup"><span data-stu-id="936bd-136">This column indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="936bd-137">stringa</span><span class="sxs-lookup"><span data-stu-id="936bd-137">string</span></span> | <span data-ttu-id="936bd-138">Indirizzo IP assegnato all'endpoint e utilizzato durante le comunicazioni di rete correlate</span><span class="sxs-lookup"><span data-stu-id="936bd-138">IP address assigned to the endpoint and used during related network communications</span></span> |
| `IsAnonymousProxy` | <span data-ttu-id="936bd-139">stringa</span><span class="sxs-lookup"><span data-stu-id="936bd-139">string</span></span> | <span data-ttu-id="936bd-140">Indica se l'indirizzo IP appartiene a un proxy anonimo noto</span><span class="sxs-lookup"><span data-stu-id="936bd-140">Indicates whether the IP address belongs to a known anonymous proxy</span></span> |
| `CountryCode` | <span data-ttu-id="936bd-141">stringa</span><span class="sxs-lookup"><span data-stu-id="936bd-141">string</span></span> | <span data-ttu-id="936bd-142">Codice di due lettere che indica il paese in cui l'indirizzo IP del client è geolocale</span><span class="sxs-lookup"><span data-stu-id="936bd-142">Two-letter code indicating the country where the client IP address is geolocated</span></span> |
| `City` | <span data-ttu-id="936bd-143">stringa</span><span class="sxs-lookup"><span data-stu-id="936bd-143">string</span></span> | <span data-ttu-id="936bd-144">Città in cui l'indirizzo IP del client è geolocato</span><span class="sxs-lookup"><span data-stu-id="936bd-144">City where the client IP address is geolocated</span></span> |
| `Isp` | <span data-ttu-id="936bd-145">stringa</span><span class="sxs-lookup"><span data-stu-id="936bd-145">string</span></span> | <span data-ttu-id="936bd-146">Provider di servizi Internet (ISP) associato all'indirizzo IP</span><span class="sxs-lookup"><span data-stu-id="936bd-146">Internet service provider (ISP) associated with the IP address</span></span> |
| `UserAgent` | <span data-ttu-id="936bd-147">stringa</span><span class="sxs-lookup"><span data-stu-id="936bd-147">string</span></span> | <span data-ttu-id="936bd-148">Informazioni agente utente dal Web browser o da un'altra applicazione client</span><span class="sxs-lookup"><span data-stu-id="936bd-148">User agent information from the web browser or other client application</span></span> |
| `ActivityType` | <span data-ttu-id="936bd-149">stringa</span><span class="sxs-lookup"><span data-stu-id="936bd-149">string</span></span> | <span data-ttu-id="936bd-150">Tipo di attività che ha attivato l'evento</span><span class="sxs-lookup"><span data-stu-id="936bd-150">Type of activity that triggered the event</span></span> |
| `ActivityObjects` | <span data-ttu-id="936bd-151">stringa</span><span class="sxs-lookup"><span data-stu-id="936bd-151">string</span></span> | <span data-ttu-id="936bd-152">Elenco di oggetti, ad esempio file o cartelle, coinvolti nell'attività registrata</span><span class="sxs-lookup"><span data-stu-id="936bd-152">List of objects, such as files or folders, that were involved in the recorded activity</span></span> |
| `ObjectName` | <span data-ttu-id="936bd-153">stringa</span><span class="sxs-lookup"><span data-stu-id="936bd-153">string</span></span> | <span data-ttu-id="936bd-154">Nome dell'oggetto a cui è stata applicata l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="936bd-154">Name of the object that the recorded action was applied to</span></span> |
| `ObjectType` | <span data-ttu-id="936bd-155">stringa</span><span class="sxs-lookup"><span data-stu-id="936bd-155">string</span></span> | <span data-ttu-id="936bd-156">Tipo di oggetto, ad esempio un file o una cartella, a cui è stata applicata l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="936bd-156">Type of object, such as a file or a folder, that the recorded action was applied to</span></span> |
| `ObjectId` | <span data-ttu-id="936bd-157">stringa</span><span class="sxs-lookup"><span data-stu-id="936bd-157">string</span></span> | <span data-ttu-id="936bd-158">Identificatore univoco dell'oggetto a cui è stata applicata l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="936bd-158">Unique identifier of the object that the recorded action was applied to</span></span> |
| `ReportId` | <span data-ttu-id="936bd-159">stringa</span><span class="sxs-lookup"><span data-stu-id="936bd-159">string</span></span> | <span data-ttu-id="936bd-160">Identificatore univoco dell'evento</span><span class="sxs-lookup"><span data-stu-id="936bd-160">Unique identifier for the event</span></span> |
| `RawEventData` | <span data-ttu-id="936bd-161">stringa</span><span class="sxs-lookup"><span data-stu-id="936bd-161">string</span></span> | <span data-ttu-id="936bd-162">Informazioni sugli eventi non elaborati dall'applicazione o dal servizio di origine in formato JSON</span><span class="sxs-lookup"><span data-stu-id="936bd-162">Raw event information from the source application or service in JSON format</span></span> |
| `AdditionalFields` | <span data-ttu-id="936bd-163">stringa</span><span class="sxs-lookup"><span data-stu-id="936bd-163">string</span></span> | <span data-ttu-id="936bd-164">Informazioni aggiuntive sull'entità o sull'evento</span><span class="sxs-lookup"><span data-stu-id="936bd-164">Additional information about the entity or event</span></span> |


## <a name="related-topics"></a><span data-ttu-id="936bd-165">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="936bd-165">Related topics</span></span>
- [<span data-ttu-id="936bd-166">Panoramica della rilevazione avanzata</span><span class="sxs-lookup"><span data-stu-id="936bd-166">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="936bd-167">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="936bd-167">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="936bd-168">Utilizzare le query condivise</span><span class="sxs-lookup"><span data-stu-id="936bd-168">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="936bd-169">Cercare tra dispositivi, posta elettronica, app e identità</span><span class="sxs-lookup"><span data-stu-id="936bd-169">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="936bd-170">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="936bd-170">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="936bd-171">Applicare le procedure consigliate per le query</span><span class="sxs-lookup"><span data-stu-id="936bd-171">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
