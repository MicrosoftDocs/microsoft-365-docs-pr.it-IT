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
ms.openlocfilehash: 663dc2a3de676fa2daeab3d9621254e956d42fc4
ms.sourcegitcommit: b4119682bd3c036289e851fff56fde869c816479
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/22/2020
ms.locfileid: "45204756"
---
# <a name="appfileevents"></a><span data-ttu-id="0a138-104">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="0a138-104">AppFileEvents</span></span>

<span data-ttu-id="0a138-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="0a138-105">**Applies to:**</span></span>
- <span data-ttu-id="0a138-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="0a138-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="0a138-107">La `AppFileEvents` tabella nello schema di [ricerca avanzata](advanced-hunting-overview.md) contiene informazioni sulle attività correlate ai file nelle app e nei servizi cloud monitorati da Microsoft cloud app Security.</span><span class="sxs-lookup"><span data-stu-id="0a138-107">The `AppFileEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file-related activities in cloud apps and services monitored by Microsoft Cloud App Security.</span></span> <span data-ttu-id="0a138-108">Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="0a138-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="0a138-109">Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="0a138-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="0a138-110">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="0a138-110">Column name</span></span> | <span data-ttu-id="0a138-111">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="0a138-111">Data type</span></span> | <span data-ttu-id="0a138-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0a138-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="0a138-113">datetime</span><span class="sxs-lookup"><span data-stu-id="0a138-113">datetime</span></span> | <span data-ttu-id="0a138-114">Data e ora di registrazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="0a138-114">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="0a138-115">stringa</span><span class="sxs-lookup"><span data-stu-id="0a138-115">string</span></span> | <span data-ttu-id="0a138-116">Tipo di attività che ha attivato l'evento</span><span class="sxs-lookup"><span data-stu-id="0a138-116">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="0a138-117">stringa</span><span class="sxs-lookup"><span data-stu-id="0a138-117">string</span></span> | <span data-ttu-id="0a138-118">Applicazione in cui è stata eseguita l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="0a138-118">Application that performed the recorded action</span></span> |
| `FileName` | <span data-ttu-id="0a138-119">stringa</span><span class="sxs-lookup"><span data-stu-id="0a138-119">string</span></span> | <span data-ttu-id="0a138-120">Nome del file a cui è stata applicata l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="0a138-120">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="0a138-121">stringa</span><span class="sxs-lookup"><span data-stu-id="0a138-121">string</span></span> | <span data-ttu-id="0a138-122">Cartella contenente il file a cui è stata applicata l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="0a138-122">Folder containing the file that the recorded action was applied to</span></span> |
| `PreviousFileName` | <span data-ttu-id="0a138-123">stringa</span><span class="sxs-lookup"><span data-stu-id="0a138-123">string</span></span> | <span data-ttu-id="0a138-124">Nome originale del file che è stato rinominato come risultato dell'azione</span><span class="sxs-lookup"><span data-stu-id="0a138-124">Original name of the file that was renamed as a result of the action</span></span> |
| `PreviousFolderPath` | <span data-ttu-id="0a138-125">stringa</span><span class="sxs-lookup"><span data-stu-id="0a138-125">string</span></span> | <span data-ttu-id="0a138-126">Cartella originale contenente il file prima dell'applicazione dell'azione registrata</span><span class="sxs-lookup"><span data-stu-id="0a138-126">Original folder containing the file before the recorded action was applied</span></span> |
| `Protocol` | <span data-ttu-id="0a138-127">stringa</span><span class="sxs-lookup"><span data-stu-id="0a138-127">string</span></span> | <span data-ttu-id="0a138-128">Protocollo di rete utilizzato</span><span class="sxs-lookup"><span data-stu-id="0a138-128">Network protocol used</span></span> |
| `AccountName` | <span data-ttu-id="0a138-129">stringa</span><span class="sxs-lookup"><span data-stu-id="0a138-129">string</span></span> | <span data-ttu-id="0a138-130">Nome utente dell'account</span><span class="sxs-lookup"><span data-stu-id="0a138-130">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="0a138-131">stringa</span><span class="sxs-lookup"><span data-stu-id="0a138-131">string</span></span> | <span data-ttu-id="0a138-132">Dominio dell'account</span><span class="sxs-lookup"><span data-stu-id="0a138-132">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="0a138-133">stringa</span><span class="sxs-lookup"><span data-stu-id="0a138-133">string</span></span> | <span data-ttu-id="0a138-134">Nome dell'entità utente (UPN) dell'account</span><span class="sxs-lookup"><span data-stu-id="0a138-134">User principal name (UPN) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="0a138-135">stringa</span><span class="sxs-lookup"><span data-stu-id="0a138-135">string</span></span> | <span data-ttu-id="0a138-136">Identificatore univoco per l'account in Azure AD</span><span class="sxs-lookup"><span data-stu-id="0a138-136">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="0a138-137">stringa</span><span class="sxs-lookup"><span data-stu-id="0a138-137">string</span></span> | <span data-ttu-id="0a138-138">Nome dell'account utente visualizzato nella rubrica.</span><span class="sxs-lookup"><span data-stu-id="0a138-138">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="0a138-139">In genere una combinazione di un nome o di un cognome, di un'iniziazione centrale e di un ultimo nome.</span><span class="sxs-lookup"><span data-stu-id="0a138-139">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="0a138-140">stringa</span><span class="sxs-lookup"><span data-stu-id="0a138-140">string</span></span> | <span data-ttu-id="0a138-141">Nome di dominio completo (FQDN) del dispositivo</span><span class="sxs-lookup"><span data-stu-id="0a138-141">Fully qualified domain name (FQDN) of the device</span></span> |
| `DeviceType` | <span data-ttu-id="0a138-142">stringa</span><span class="sxs-lookup"><span data-stu-id="0a138-142">string</span></span> | <span data-ttu-id="0a138-143">Tipo di dispositivo</span><span class="sxs-lookup"><span data-stu-id="0a138-143">Type of device</span></span> | 
| `OSPlatform` | <span data-ttu-id="0a138-144">stringa</span><span class="sxs-lookup"><span data-stu-id="0a138-144">string</span></span> | <span data-ttu-id="0a138-145">Piattaforma del sistema operativo in esecuzione nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0a138-145">Platform of the operating system running on the device.</span></span> <span data-ttu-id="0a138-146">Ciò indica specifici sistemi operativi, incluse variazioni all'interno della stessa famiglia di prodotti, come Windows 10 e Windows 7.</span><span class="sxs-lookup"><span data-stu-id="0a138-146">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="0a138-147">stringa</span><span class="sxs-lookup"><span data-stu-id="0a138-147">string</span></span> | <span data-ttu-id="0a138-148">Indirizzo IP assegnato all'endpoint e utilizzato durante le comunicazioni di rete correlate</span><span class="sxs-lookup"><span data-stu-id="0a138-148">IP address assigned to the endpoint and used during related network communications</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="0a138-149">stringa</span><span class="sxs-lookup"><span data-stu-id="0a138-149">string</span></span> | <span data-ttu-id="0a138-150">Nome del dispositivo che esegue l'applicazione server che ha elaborato l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="0a138-150">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="0a138-151">stringa</span><span class="sxs-lookup"><span data-stu-id="0a138-151">string</span></span> | <span data-ttu-id="0a138-152">Indirizzo IP del dispositivo che esegue l'applicazione server che ha elaborato l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="0a138-152">IP address of the device running the server application that processed the recorded action</span></span> |
| `Location` | <span data-ttu-id="0a138-153">stringa</span><span class="sxs-lookup"><span data-stu-id="0a138-153">string</span></span> | <span data-ttu-id="0a138-154">Città, paese o altra località geografica associata all'evento</span><span class="sxs-lookup"><span data-stu-id="0a138-154">City, country, or other geographic location associated with the event</span></span> |
| `Isp` | <span data-ttu-id="0a138-155">stringa</span><span class="sxs-lookup"><span data-stu-id="0a138-155">string</span></span> | <span data-ttu-id="0a138-156">Provider di servizi Internet (ISP) associato all'indirizzo IP dell'endpoint</span><span class="sxs-lookup"><span data-stu-id="0a138-156">Internet service provider (ISP) associated with the endpoint IP address</span></span> |
| `ReportId` | <span data-ttu-id="0a138-157">long</span><span class="sxs-lookup"><span data-stu-id="0a138-157">long</span></span> | <span data-ttu-id="0a138-158">Identificatore univoco per l'evento</span><span class="sxs-lookup"><span data-stu-id="0a138-158">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="0a138-159">stringa</span><span class="sxs-lookup"><span data-stu-id="0a138-159">string</span></span> | <span data-ttu-id="0a138-160">Ulteriori informazioni sull'entità o sull'evento</span><span class="sxs-lookup"><span data-stu-id="0a138-160">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="0a138-161">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="0a138-161">Related topics</span></span>
- [<span data-ttu-id="0a138-162">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="0a138-162">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="0a138-163">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="0a138-163">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="0a138-164">Utilizzare le query condivise</span><span class="sxs-lookup"><span data-stu-id="0a138-164">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="0a138-165">Ricerca delle minacce attraverso dispositivi e posta elettronica</span><span class="sxs-lookup"><span data-stu-id="0a138-165">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="0a138-166">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="0a138-166">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="0a138-167">Applicare le procedure consigliate per le query</span><span class="sxs-lookup"><span data-stu-id="0a138-167">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
