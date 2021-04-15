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
ms.openlocfilehash: 83b9eec37648ba48aa8e6931e836e8a5e22458c8
ms.sourcegitcommit: 07dea2aa98daf0c4086f8590375167830027c802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "51760027"
---
# <a name="cloudappevents"></a><span data-ttu-id="79c9d-104">CloudAppEvents</span><span class="sxs-lookup"><span data-stu-id="79c9d-104">CloudAppEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="79c9d-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="79c9d-105">**Applies to:**</span></span>
- <span data-ttu-id="79c9d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="79c9d-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="79c9d-107">La tabella nello schema di ricerca avanzata contiene informazioni sulle attività in varie app e servizi `CloudAppEvents` cloud trattati da Microsoft Cloud App Security. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="79c9d-107">The `CloudAppEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about activities in various cloud apps and services covered by Microsoft Cloud App Security.</span></span> <span data-ttu-id="79c9d-108">Per un elenco completo, passare ad [App e servizi trattati](#apps-and-services-covered).</span><span class="sxs-lookup"><span data-stu-id="79c9d-108">For a complete list, jump to [Apps and services covered](#apps-and-services-covered).</span></span> <span data-ttu-id="79c9d-109">Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="79c9d-109">Use this reference to construct queries that return information from this table.</span></span> 

>[!IMPORTANT]
><span data-ttu-id="79c9d-110">In questa tabella sono incluse le informazioni disponibili nella `AppFileEvents` tabella.</span><span class="sxs-lookup"><span data-stu-id="79c9d-110">This table includes information that used to be available in the `AppFileEvents` table.</span></span> <span data-ttu-id="79c9d-111">A partire dal 7 marzo 2021, gli utenti che ricercano le attività correlate ai file nei servizi cloud entro e oltre questa data devono utilizzare la `CloudAppEvents` tabella.</span><span class="sxs-lookup"><span data-stu-id="79c9d-111">Starting March 7, 2021, users hunting through file-related activities in cloud services on and beyond this date should use the `CloudAppEvents` table instead.</span></span> <br><br><span data-ttu-id="79c9d-112">Assicurarsi di cercare query e regole di rilevamento personalizzate che ancora usano la tabella e `AppFileEvents` modificarle per utilizzare la `CloudAppEvents` tabella.</span><span class="sxs-lookup"><span data-stu-id="79c9d-112">Make sure to search for queries and custom detection rules that still use the `AppFileEvents` table and edit them to use the `CloudAppEvents` table.</span></span> <span data-ttu-id="79c9d-113">Altre indicazioni sulla conversione delle query interessate sono disponibili in [Hunt across cloud app activities with Microsoft 365 Defender advanced hunting.](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857)</span><span class="sxs-lookup"><span data-stu-id="79c9d-113">More guidance about converting affected queries can be found in [Hunt across cloud app activities with Microsoft 365 Defender advanced hunting](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857).</span></span>


<span data-ttu-id="79c9d-114">Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="79c9d-114">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="79c9d-115">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="79c9d-115">Column name</span></span> | <span data-ttu-id="79c9d-116">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="79c9d-116">Data type</span></span> | <span data-ttu-id="79c9d-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="79c9d-117">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="79c9d-118">datetime</span><span class="sxs-lookup"><span data-stu-id="79c9d-118">datetime</span></span> | <span data-ttu-id="79c9d-119">Data e ora di registrazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="79c9d-119">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="79c9d-120">stringa</span><span class="sxs-lookup"><span data-stu-id="79c9d-120">string</span></span> | <span data-ttu-id="79c9d-121">Tipo di attività che ha attivato l'evento</span><span class="sxs-lookup"><span data-stu-id="79c9d-121">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="79c9d-122">stringa</span><span class="sxs-lookup"><span data-stu-id="79c9d-122">string</span></span> | <span data-ttu-id="79c9d-123">Applicazione che ha eseguito l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="79c9d-123">Application that performed the recorded action</span></span> |
| `ApplicationId` | <span data-ttu-id="79c9d-124">stringa</span><span class="sxs-lookup"><span data-stu-id="79c9d-124">string</span></span> | <span data-ttu-id="79c9d-125">Identificatore univoco dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="79c9d-125">Unique identifier for the application</span></span> |
| `AccountObjectId` | <span data-ttu-id="79c9d-126">stringa</span><span class="sxs-lookup"><span data-stu-id="79c9d-126">string</span></span> | <span data-ttu-id="79c9d-127">Identificatore univoco dell'account in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="79c9d-127">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountDisplayName` | <span data-ttu-id="79c9d-128">stringa</span><span class="sxs-lookup"><span data-stu-id="79c9d-128">string</span></span> | <span data-ttu-id="79c9d-129">Nome dell'utente dell'account visualizzato nella rubrica.</span><span class="sxs-lookup"><span data-stu-id="79c9d-129">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="79c9d-130">In genere una combinazione di un nome o di un dato nome, un'iniziazione intermedia e un cognome o un cognome.</span><span class="sxs-lookup"><span data-stu-id="79c9d-130">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `IsAdminOperation` | <span data-ttu-id="79c9d-131">stringa</span><span class="sxs-lookup"><span data-stu-id="79c9d-131">string</span></span> | <span data-ttu-id="79c9d-132">Indica se l'attività è stata eseguita da un amministratore</span><span class="sxs-lookup"><span data-stu-id="79c9d-132">Indicates whether the activity was performed by an administrator</span></span> |
| `DeviceType` | <span data-ttu-id="79c9d-133">stringa</span><span class="sxs-lookup"><span data-stu-id="79c9d-133">string</span></span> | <span data-ttu-id="79c9d-134">Tipo di dispositivo basato su scopo e funzionalità, ad esempio "Dispositivo di rete", "Workstation", "Server", "Mobile", "Console di gioco" o "Stampante"</span><span class="sxs-lookup"><span data-stu-id="79c9d-134">Type of device based on purpose and functionality, such as "Network device", "Workstation", "Server", "Mobile", "Gaming console", or "Printer"</span></span> | 
| `OSPlatform` | <span data-ttu-id="79c9d-135">stringa</span><span class="sxs-lookup"><span data-stu-id="79c9d-135">string</span></span> | <span data-ttu-id="79c9d-136">Piattaforma del sistema operativo in esecuzione nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="79c9d-136">Platform of the operating system running on the device.</span></span> <span data-ttu-id="79c9d-137">Questa colonna indica sistemi operativi specifici, incluse le varianti della stessa famiglia, ad esempio Windows 10 e Windows 7.</span><span class="sxs-lookup"><span data-stu-id="79c9d-137">This column indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="79c9d-138">stringa</span><span class="sxs-lookup"><span data-stu-id="79c9d-138">string</span></span> | <span data-ttu-id="79c9d-139">Indirizzo IP assegnato all'endpoint e utilizzato durante le comunicazioni di rete correlate</span><span class="sxs-lookup"><span data-stu-id="79c9d-139">IP address assigned to the endpoint and used during related network communications</span></span> |
| `IsAnonymousProxy` | <span data-ttu-id="79c9d-140">stringa</span><span class="sxs-lookup"><span data-stu-id="79c9d-140">string</span></span> | <span data-ttu-id="79c9d-141">Indica se l'indirizzo IP appartiene a un proxy anonimo noto</span><span class="sxs-lookup"><span data-stu-id="79c9d-141">Indicates whether the IP address belongs to a known anonymous proxy</span></span> |
| `CountryCode` | <span data-ttu-id="79c9d-142">stringa</span><span class="sxs-lookup"><span data-stu-id="79c9d-142">string</span></span> | <span data-ttu-id="79c9d-143">Codice di due lettere che indica il paese in cui l'indirizzo IP del client è geolocale</span><span class="sxs-lookup"><span data-stu-id="79c9d-143">Two-letter code indicating the country where the client IP address is geolocated</span></span> |
| `City` | <span data-ttu-id="79c9d-144">stringa</span><span class="sxs-lookup"><span data-stu-id="79c9d-144">string</span></span> | <span data-ttu-id="79c9d-145">Città in cui l'indirizzo IP del client è geolocato</span><span class="sxs-lookup"><span data-stu-id="79c9d-145">City where the client IP address is geolocated</span></span> |
| `Isp` | <span data-ttu-id="79c9d-146">stringa</span><span class="sxs-lookup"><span data-stu-id="79c9d-146">string</span></span> | <span data-ttu-id="79c9d-147">Provider di servizi Internet (ISP) associato all'indirizzo IP</span><span class="sxs-lookup"><span data-stu-id="79c9d-147">Internet service provider (ISP) associated with the IP address</span></span> |
| `UserAgent` | <span data-ttu-id="79c9d-148">stringa</span><span class="sxs-lookup"><span data-stu-id="79c9d-148">string</span></span> | <span data-ttu-id="79c9d-149">Informazioni agente utente dal Web browser o da un'altra applicazione client</span><span class="sxs-lookup"><span data-stu-id="79c9d-149">User agent information from the web browser or other client application</span></span> |
| `ActivityType` | <span data-ttu-id="79c9d-150">stringa</span><span class="sxs-lookup"><span data-stu-id="79c9d-150">string</span></span> | <span data-ttu-id="79c9d-151">Tipo di attività che ha attivato l'evento</span><span class="sxs-lookup"><span data-stu-id="79c9d-151">Type of activity that triggered the event</span></span> |
| `ActivityObjects` | <span data-ttu-id="79c9d-152">stringa</span><span class="sxs-lookup"><span data-stu-id="79c9d-152">string</span></span> | <span data-ttu-id="79c9d-153">Elenco di oggetti, ad esempio file o cartelle, coinvolti nell'attività registrata</span><span class="sxs-lookup"><span data-stu-id="79c9d-153">List of objects, such as files or folders, that were involved in the recorded activity</span></span> |
| `ObjectName` | <span data-ttu-id="79c9d-154">stringa</span><span class="sxs-lookup"><span data-stu-id="79c9d-154">string</span></span> | <span data-ttu-id="79c9d-155">Nome dell'oggetto a cui è stata applicata l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="79c9d-155">Name of the object that the recorded action was applied to</span></span> |
| `ObjectType` | <span data-ttu-id="79c9d-156">stringa</span><span class="sxs-lookup"><span data-stu-id="79c9d-156">string</span></span> | <span data-ttu-id="79c9d-157">Tipo di oggetto, ad esempio un file o una cartella, a cui è stata applicata l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="79c9d-157">Type of object, such as a file or a folder, that the recorded action was applied to</span></span> |
| `ObjectId` | <span data-ttu-id="79c9d-158">stringa</span><span class="sxs-lookup"><span data-stu-id="79c9d-158">string</span></span> | <span data-ttu-id="79c9d-159">Identificatore univoco dell'oggetto a cui è stata applicata l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="79c9d-159">Unique identifier of the object that the recorded action was applied to</span></span> |
| `ReportId` | <span data-ttu-id="79c9d-160">stringa</span><span class="sxs-lookup"><span data-stu-id="79c9d-160">string</span></span> | <span data-ttu-id="79c9d-161">Identificatore univoco dell'evento</span><span class="sxs-lookup"><span data-stu-id="79c9d-161">Unique identifier for the event</span></span> |
| `RawEventData` | <span data-ttu-id="79c9d-162">stringa</span><span class="sxs-lookup"><span data-stu-id="79c9d-162">string</span></span> | <span data-ttu-id="79c9d-163">Informazioni sugli eventi non elaborati dall'applicazione o dal servizio di origine in formato JSON</span><span class="sxs-lookup"><span data-stu-id="79c9d-163">Raw event information from the source application or service in JSON format</span></span> |
| `AdditionalFields` | <span data-ttu-id="79c9d-164">stringa</span><span class="sxs-lookup"><span data-stu-id="79c9d-164">string</span></span> | <span data-ttu-id="79c9d-165">Informazioni aggiuntive sull'entità o sull'evento</span><span class="sxs-lookup"><span data-stu-id="79c9d-165">Additional information about the entity or event</span></span> |

## <a name="apps-and-services-covered"></a><span data-ttu-id="79c9d-166">App e servizi coperti</span><span class="sxs-lookup"><span data-stu-id="79c9d-166">Apps and services covered</span></span>

- <span data-ttu-id="79c9d-167">Dropbox</span><span class="sxs-lookup"><span data-stu-id="79c9d-167">Dropbox</span></span>
- <span data-ttu-id="79c9d-168">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="79c9d-168">Dynamics 365</span></span>
- <span data-ttu-id="79c9d-169">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="79c9d-169">Exchange Online</span></span>
- <span data-ttu-id="79c9d-170">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="79c9d-170">Microsoft Teams</span></span>
- <span data-ttu-id="79c9d-171">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="79c9d-171">OneDrive for Business</span></span>
- <span data-ttu-id="79c9d-172">Power Automate</span><span class="sxs-lookup"><span data-stu-id="79c9d-172">Power Automate</span></span>
- <span data-ttu-id="79c9d-173">Power BI</span><span class="sxs-lookup"><span data-stu-id="79c9d-173">Power BI</span></span>
- <span data-ttu-id="79c9d-174">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="79c9d-174">SharePoint Online</span></span>
- <span data-ttu-id="79c9d-175">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="79c9d-175">Skype for Business</span></span>
- <span data-ttu-id="79c9d-176">Office 365</span><span class="sxs-lookup"><span data-stu-id="79c9d-176">Office 365</span></span>
- <span data-ttu-id="79c9d-177">Yammer</span><span class="sxs-lookup"><span data-stu-id="79c9d-177">Yammer</span></span> 

## <a name="related-topics"></a><span data-ttu-id="79c9d-178">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="79c9d-178">Related topics</span></span>
- [<span data-ttu-id="79c9d-179">Panoramica della rilevazione avanzata</span><span class="sxs-lookup"><span data-stu-id="79c9d-179">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="79c9d-180">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="79c9d-180">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="79c9d-181">Utilizzare le query condivise</span><span class="sxs-lookup"><span data-stu-id="79c9d-181">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="79c9d-182">Cercare tra dispositivi, posta elettronica, app e identità</span><span class="sxs-lookup"><span data-stu-id="79c9d-182">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="79c9d-183">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="79c9d-183">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="79c9d-184">Applicare le procedure consigliate per le query</span><span class="sxs-lookup"><span data-stu-id="79c9d-184">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
