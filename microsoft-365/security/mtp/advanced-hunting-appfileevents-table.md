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
ms.openlocfilehash: 385011382d20919b219cf84e13cda4993826691b
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48197062"
---
# <a name="appfileevents"></a><span data-ttu-id="f9f94-104">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="f9f94-104">AppFileEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f9f94-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="f9f94-105">**Applies to:**</span></span>
- <span data-ttu-id="f9f94-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="f9f94-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="f9f94-107">La `AppFileEvents` tabella nello schema di [ricerca avanzata](advanced-hunting-overview.md) contiene informazioni sulle attività correlate ai file nelle app e nei servizi cloud monitorati da Microsoft cloud app Security.</span><span class="sxs-lookup"><span data-stu-id="f9f94-107">The `AppFileEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file-related activities in cloud apps and services monitored by Microsoft Cloud App Security.</span></span> <span data-ttu-id="f9f94-108">Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="f9f94-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="f9f94-109">Per informazioni dettagliate sui tipi di eventi ( `ActionType` valori) supportati da una tabella, utilizzare la Guida di [riferimento allo schema incorporata](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) disponibile nel centro sicurezza.</span><span class="sxs-lookup"><span data-stu-id="f9f94-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="f9f94-110">Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="f9f94-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="f9f94-111">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="f9f94-111">Column name</span></span> | <span data-ttu-id="f9f94-112">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="f9f94-112">Data type</span></span> | <span data-ttu-id="f9f94-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f9f94-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="f9f94-114">datetime</span><span class="sxs-lookup"><span data-stu-id="f9f94-114">datetime</span></span> | <span data-ttu-id="f9f94-115">Data e ora di registrazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="f9f94-115">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="f9f94-116">stringa</span><span class="sxs-lookup"><span data-stu-id="f9f94-116">string</span></span> | <span data-ttu-id="f9f94-117">Tipo di attività che ha attivato l'evento.</span><span class="sxs-lookup"><span data-stu-id="f9f94-117">Type of activity that triggered the event.</span></span> <span data-ttu-id="f9f94-118">Per informazioni dettagliate, vedere la Guida [di riferimento allo schema in-Portal.](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)</span><span class="sxs-lookup"><span data-stu-id="f9f94-118">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="f9f94-119">stringa</span><span class="sxs-lookup"><span data-stu-id="f9f94-119">string</span></span> | <span data-ttu-id="f9f94-120">Applicazione in cui è stata eseguita l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="f9f94-120">Application that performed the recorded action</span></span> |
| `FileName` | <span data-ttu-id="f9f94-121">stringa</span><span class="sxs-lookup"><span data-stu-id="f9f94-121">string</span></span> | <span data-ttu-id="f9f94-122">Nome del file a cui è stata applicata l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="f9f94-122">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="f9f94-123">stringa</span><span class="sxs-lookup"><span data-stu-id="f9f94-123">string</span></span> | <span data-ttu-id="f9f94-124">Cartella contenente il file a cui è stata applicata l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="f9f94-124">Folder containing the file that the recorded action was applied to</span></span> |
| `PreviousFileName` | <span data-ttu-id="f9f94-125">stringa</span><span class="sxs-lookup"><span data-stu-id="f9f94-125">string</span></span> | <span data-ttu-id="f9f94-126">Nome originale del file che è stato rinominato come risultato dell'azione</span><span class="sxs-lookup"><span data-stu-id="f9f94-126">Original name of the file that was renamed as a result of the action</span></span> |
| `PreviousFolderPath` | <span data-ttu-id="f9f94-127">stringa</span><span class="sxs-lookup"><span data-stu-id="f9f94-127">string</span></span> | <span data-ttu-id="f9f94-128">Cartella originale contenente il file prima dell'applicazione dell'azione registrata</span><span class="sxs-lookup"><span data-stu-id="f9f94-128">Original folder containing the file before the recorded action was applied</span></span> |
| `Protocol` | <span data-ttu-id="f9f94-129">stringa</span><span class="sxs-lookup"><span data-stu-id="f9f94-129">string</span></span> | <span data-ttu-id="f9f94-130">Protocollo di rete utilizzato</span><span class="sxs-lookup"><span data-stu-id="f9f94-130">Network protocol used</span></span> |
| `AccountName` | <span data-ttu-id="f9f94-131">stringa</span><span class="sxs-lookup"><span data-stu-id="f9f94-131">string</span></span> | <span data-ttu-id="f9f94-132">Nome utente dell'account</span><span class="sxs-lookup"><span data-stu-id="f9f94-132">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="f9f94-133">stringa</span><span class="sxs-lookup"><span data-stu-id="f9f94-133">string</span></span> | <span data-ttu-id="f9f94-134">Dominio dell'account</span><span class="sxs-lookup"><span data-stu-id="f9f94-134">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="f9f94-135">stringa</span><span class="sxs-lookup"><span data-stu-id="f9f94-135">string</span></span> | <span data-ttu-id="f9f94-136">Nome dell'entità utente (UPN) dell'account</span><span class="sxs-lookup"><span data-stu-id="f9f94-136">User principal name (UPN) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="f9f94-137">stringa</span><span class="sxs-lookup"><span data-stu-id="f9f94-137">string</span></span> | <span data-ttu-id="f9f94-138">Identificatore univoco per l'account in Azure AD</span><span class="sxs-lookup"><span data-stu-id="f9f94-138">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="f9f94-139">stringa</span><span class="sxs-lookup"><span data-stu-id="f9f94-139">string</span></span> | <span data-ttu-id="f9f94-140">Nome dell'account utente visualizzato nella rubrica.</span><span class="sxs-lookup"><span data-stu-id="f9f94-140">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="f9f94-141">In genere una combinazione di un nome o di un cognome, di un'iniziazione centrale e di un ultimo nome.</span><span class="sxs-lookup"><span data-stu-id="f9f94-141">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="f9f94-142">stringa</span><span class="sxs-lookup"><span data-stu-id="f9f94-142">string</span></span> | <span data-ttu-id="f9f94-143">Nome di dominio completo (FQDN) del dispositivo</span><span class="sxs-lookup"><span data-stu-id="f9f94-143">Fully qualified domain name (FQDN) of the device</span></span> |
| `DeviceType` | <span data-ttu-id="f9f94-144">stringa</span><span class="sxs-lookup"><span data-stu-id="f9f94-144">string</span></span> | <span data-ttu-id="f9f94-145">Tipo di dispositivo</span><span class="sxs-lookup"><span data-stu-id="f9f94-145">Type of device</span></span> | 
| `OSPlatform` | <span data-ttu-id="f9f94-146">stringa</span><span class="sxs-lookup"><span data-stu-id="f9f94-146">string</span></span> | <span data-ttu-id="f9f94-147">Piattaforma del sistema operativo in esecuzione nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f9f94-147">Platform of the operating system running on the device.</span></span> <span data-ttu-id="f9f94-148">Ciò indica specifici sistemi operativi, incluse variazioni all'interno della stessa famiglia di prodotti, come Windows 10 e Windows 7.</span><span class="sxs-lookup"><span data-stu-id="f9f94-148">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="f9f94-149">stringa</span><span class="sxs-lookup"><span data-stu-id="f9f94-149">string</span></span> | <span data-ttu-id="f9f94-150">Indirizzo IP assegnato all'endpoint e utilizzato durante le comunicazioni di rete correlate</span><span class="sxs-lookup"><span data-stu-id="f9f94-150">IP address assigned to the endpoint and used during related network communications</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="f9f94-151">stringa</span><span class="sxs-lookup"><span data-stu-id="f9f94-151">string</span></span> | <span data-ttu-id="f9f94-152">Nome del dispositivo che esegue l'applicazione server che ha elaborato l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="f9f94-152">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="f9f94-153">stringa</span><span class="sxs-lookup"><span data-stu-id="f9f94-153">string</span></span> | <span data-ttu-id="f9f94-154">Indirizzo IP del dispositivo che esegue l'applicazione server che ha elaborato l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="f9f94-154">IP address of the device running the server application that processed the recorded action</span></span> |
| `Location` | <span data-ttu-id="f9f94-155">stringa</span><span class="sxs-lookup"><span data-stu-id="f9f94-155">string</span></span> | <span data-ttu-id="f9f94-156">Città, paese o altra località geografica associata all'evento</span><span class="sxs-lookup"><span data-stu-id="f9f94-156">City, country, or other geographic location associated with the event</span></span> |
| `Isp` | <span data-ttu-id="f9f94-157">stringa</span><span class="sxs-lookup"><span data-stu-id="f9f94-157">string</span></span> | <span data-ttu-id="f9f94-158">Provider di servizi Internet (ISP) associato all'indirizzo IP dell'endpoint</span><span class="sxs-lookup"><span data-stu-id="f9f94-158">Internet service provider (ISP) associated with the endpoint IP address</span></span> |
| `ReportId` | <span data-ttu-id="f9f94-159">long</span><span class="sxs-lookup"><span data-stu-id="f9f94-159">long</span></span> | <span data-ttu-id="f9f94-160">Identificatore univoco per l'evento</span><span class="sxs-lookup"><span data-stu-id="f9f94-160">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="f9f94-161">stringa</span><span class="sxs-lookup"><span data-stu-id="f9f94-161">string</span></span> | <span data-ttu-id="f9f94-162">Ulteriori informazioni sull'entità o sull'evento</span><span class="sxs-lookup"><span data-stu-id="f9f94-162">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="f9f94-163">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="f9f94-163">Related topics</span></span>
- [<span data-ttu-id="f9f94-164">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="f9f94-164">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="f9f94-165">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="f9f94-165">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="f9f94-166">Utilizzare le query condivise</span><span class="sxs-lookup"><span data-stu-id="f9f94-166">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="f9f94-167">Cercare tra dispositivi, posta elettronica, app e identità</span><span class="sxs-lookup"><span data-stu-id="f9f94-167">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="f9f94-168">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="f9f94-168">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="f9f94-169">Applicare le procedure consigliate per le query</span><span class="sxs-lookup"><span data-stu-id="f9f94-169">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
