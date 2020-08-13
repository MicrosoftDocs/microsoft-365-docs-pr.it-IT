---
title: Tabella AppFileEvents nello schema di caccia avanzato
description: Informazioni sugli eventi correlati ai file associati alle app e ai servizi cloud nella tabella AppFileEvents dello schema di caccia avanzato
keywords: caccia avanzata, caccia alle minacce, Cyber-caccia alle minacce, Microsoft Threat Protection, Microsoft 365, MTP, M365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, AppFileEvents, cloud app Security, MCAS
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
ms.openlocfilehash: 4221af6b0378e67e12852dbef0bbc0a11ff56511
ms.sourcegitcommit: 51097b18d94da20aa727ebfbeb6ec84c263b25c3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2020
ms.locfileid: "46649476"
---
# <a name="appfileevents"></a><span data-ttu-id="7e03b-104">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="7e03b-104">AppFileEvents</span></span>

<span data-ttu-id="7e03b-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="7e03b-105">**Applies to:**</span></span>
- <span data-ttu-id="7e03b-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="7e03b-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="7e03b-107">La `AppFileEvents` tabella nello schema di [ricerca avanzata](advanced-hunting-overview.md) contiene informazioni sulle attività correlate ai file nelle app e nei servizi cloud monitorati da Microsoft cloud app Security.</span><span class="sxs-lookup"><span data-stu-id="7e03b-107">The `AppFileEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file-related activities in cloud apps and services monitored by Microsoft Cloud App Security.</span></span> <span data-ttu-id="7e03b-108">Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="7e03b-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="7e03b-109">Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="7e03b-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="7e03b-110">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="7e03b-110">Column name</span></span> | <span data-ttu-id="7e03b-111">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="7e03b-111">Data type</span></span> | <span data-ttu-id="7e03b-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7e03b-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="7e03b-113">datetime</span><span class="sxs-lookup"><span data-stu-id="7e03b-113">datetime</span></span> | <span data-ttu-id="7e03b-114">Data e ora di registrazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="7e03b-114">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="7e03b-115">stringa</span><span class="sxs-lookup"><span data-stu-id="7e03b-115">string</span></span> | <span data-ttu-id="7e03b-116">Tipo di attività che ha attivato l'evento</span><span class="sxs-lookup"><span data-stu-id="7e03b-116">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="7e03b-117">stringa</span><span class="sxs-lookup"><span data-stu-id="7e03b-117">string</span></span> | <span data-ttu-id="7e03b-118">Applicazione in cui è stata eseguita l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="7e03b-118">Application that performed the recorded action</span></span> |
| `FileName` | <span data-ttu-id="7e03b-119">stringa</span><span class="sxs-lookup"><span data-stu-id="7e03b-119">string</span></span> | <span data-ttu-id="7e03b-120">Nome del file a cui è stata applicata l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="7e03b-120">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="7e03b-121">stringa</span><span class="sxs-lookup"><span data-stu-id="7e03b-121">string</span></span> | <span data-ttu-id="7e03b-122">Cartella contenente il file a cui è stata applicata l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="7e03b-122">Folder containing the file that the recorded action was applied to</span></span> |
| `PreviousFileName` | <span data-ttu-id="7e03b-123">stringa</span><span class="sxs-lookup"><span data-stu-id="7e03b-123">string</span></span> | <span data-ttu-id="7e03b-124">Nome originale del file che è stato rinominato come risultato dell'azione</span><span class="sxs-lookup"><span data-stu-id="7e03b-124">Original name of the file that was renamed as a result of the action</span></span> |
| `PreviousFolderPath` | <span data-ttu-id="7e03b-125">stringa</span><span class="sxs-lookup"><span data-stu-id="7e03b-125">string</span></span> | <span data-ttu-id="7e03b-126">Cartella originale contenente il file prima dell'applicazione dell'azione registrata</span><span class="sxs-lookup"><span data-stu-id="7e03b-126">Original folder containing the file before the recorded action was applied</span></span> |
| `Protocol` | <span data-ttu-id="7e03b-127">stringa</span><span class="sxs-lookup"><span data-stu-id="7e03b-127">string</span></span> | <span data-ttu-id="7e03b-128">Protocollo di rete utilizzato</span><span class="sxs-lookup"><span data-stu-id="7e03b-128">Network protocol used</span></span> |
| `AccountName` | <span data-ttu-id="7e03b-129">stringa</span><span class="sxs-lookup"><span data-stu-id="7e03b-129">string</span></span> | <span data-ttu-id="7e03b-130">Nome utente dell'account</span><span class="sxs-lookup"><span data-stu-id="7e03b-130">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="7e03b-131">stringa</span><span class="sxs-lookup"><span data-stu-id="7e03b-131">string</span></span> | <span data-ttu-id="7e03b-132">Dominio dell'account</span><span class="sxs-lookup"><span data-stu-id="7e03b-132">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="7e03b-133">stringa</span><span class="sxs-lookup"><span data-stu-id="7e03b-133">string</span></span> | <span data-ttu-id="7e03b-134">Nome dell'entità utente (UPN) dell'account</span><span class="sxs-lookup"><span data-stu-id="7e03b-134">User principal name (UPN) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="7e03b-135">stringa</span><span class="sxs-lookup"><span data-stu-id="7e03b-135">string</span></span> | <span data-ttu-id="7e03b-136">Identificatore univoco per l'account in Azure AD</span><span class="sxs-lookup"><span data-stu-id="7e03b-136">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="7e03b-137">stringa</span><span class="sxs-lookup"><span data-stu-id="7e03b-137">string</span></span> | <span data-ttu-id="7e03b-138">Nome dell'account utente visualizzato nella rubrica.</span><span class="sxs-lookup"><span data-stu-id="7e03b-138">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="7e03b-139">In genere una combinazione di un nome o di un cognome, di un'iniziazione centrale e di un ultimo nome.</span><span class="sxs-lookup"><span data-stu-id="7e03b-139">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="7e03b-140">stringa</span><span class="sxs-lookup"><span data-stu-id="7e03b-140">string</span></span> | <span data-ttu-id="7e03b-141">Nome di dominio completo (FQDN) del dispositivo</span><span class="sxs-lookup"><span data-stu-id="7e03b-141">Fully qualified domain name (FQDN) of the device</span></span> |
| `DeviceType` | <span data-ttu-id="7e03b-142">stringa</span><span class="sxs-lookup"><span data-stu-id="7e03b-142">string</span></span> | <span data-ttu-id="7e03b-143">Tipo di dispositivo</span><span class="sxs-lookup"><span data-stu-id="7e03b-143">Type of device</span></span> | 
| `OSPlatform` | <span data-ttu-id="7e03b-144">stringa</span><span class="sxs-lookup"><span data-stu-id="7e03b-144">string</span></span> | <span data-ttu-id="7e03b-145">Piattaforma del sistema operativo in esecuzione nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7e03b-145">Platform of the operating system running on the device.</span></span> <span data-ttu-id="7e03b-146">Ciò indica specifici sistemi operativi, incluse variazioni all'interno della stessa famiglia di prodotti, come Windows 10 e Windows 7.</span><span class="sxs-lookup"><span data-stu-id="7e03b-146">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="7e03b-147">stringa</span><span class="sxs-lookup"><span data-stu-id="7e03b-147">string</span></span> | <span data-ttu-id="7e03b-148">Indirizzo IP assegnato all'endpoint e utilizzato durante le comunicazioni di rete correlate</span><span class="sxs-lookup"><span data-stu-id="7e03b-148">IP address assigned to the endpoint and used during related network communications</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="7e03b-149">stringa</span><span class="sxs-lookup"><span data-stu-id="7e03b-149">string</span></span> | <span data-ttu-id="7e03b-150">Nome del dispositivo che esegue l'applicazione server che ha elaborato l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="7e03b-150">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="7e03b-151">stringa</span><span class="sxs-lookup"><span data-stu-id="7e03b-151">string</span></span> | <span data-ttu-id="7e03b-152">Indirizzo IP del dispositivo che esegue l'applicazione server che ha elaborato l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="7e03b-152">IP address of the device running the server application that processed the recorded action</span></span> |
| `Location` | <span data-ttu-id="7e03b-153">stringa</span><span class="sxs-lookup"><span data-stu-id="7e03b-153">string</span></span> | <span data-ttu-id="7e03b-154">Città, paese o altra località geografica associata all'evento</span><span class="sxs-lookup"><span data-stu-id="7e03b-154">City, country, or other geographic location associated with the event</span></span> |
| `Isp` | <span data-ttu-id="7e03b-155">stringa</span><span class="sxs-lookup"><span data-stu-id="7e03b-155">string</span></span> | <span data-ttu-id="7e03b-156">Provider di servizi Internet (ISP) associato all'indirizzo IP dell'endpoint</span><span class="sxs-lookup"><span data-stu-id="7e03b-156">Internet service provider (ISP) associated with the endpoint IP address</span></span> |
| `ReportId` | <span data-ttu-id="7e03b-157">long</span><span class="sxs-lookup"><span data-stu-id="7e03b-157">long</span></span> | <span data-ttu-id="7e03b-158">Identificatore univoco per l'evento</span><span class="sxs-lookup"><span data-stu-id="7e03b-158">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="7e03b-159">stringa</span><span class="sxs-lookup"><span data-stu-id="7e03b-159">string</span></span> | <span data-ttu-id="7e03b-160">Ulteriori informazioni sull'entità o sull'evento</span><span class="sxs-lookup"><span data-stu-id="7e03b-160">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="7e03b-161">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="7e03b-161">Related topics</span></span>
- [<span data-ttu-id="7e03b-162">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="7e03b-162">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="7e03b-163">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="7e03b-163">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="7e03b-164">Utilizzare le query condivise</span><span class="sxs-lookup"><span data-stu-id="7e03b-164">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="7e03b-165">Cercare tra i dispositivi, i messaggi di posta elettronica, le app e le identità</span><span class="sxs-lookup"><span data-stu-id="7e03b-165">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="7e03b-166">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="7e03b-166">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="7e03b-167">Applicare le procedure consigliate per le query</span><span class="sxs-lookup"><span data-stu-id="7e03b-167">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
