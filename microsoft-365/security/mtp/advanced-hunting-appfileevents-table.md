---
title: Tabella AppFileEvents nello schema di ricerca avanzata
description: Informazioni sugli eventi correlati ai file associati alle app e ai servizi cloud nella tabella AppFileEvents dello schema di ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca delle minacce informatiche, microsoft threat protection, microsoft 365, mtp, m365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, AppFileEvents, Cloud App Security, MCAS
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
ms.openlocfilehash: 8406d1f9e3d56555b1699d191933c6f9735c9574
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145488"
---
# <a name="appfileevents"></a><span data-ttu-id="6f51f-104">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="6f51f-104">AppFileEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="6f51f-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="6f51f-105">**Applies to:**</span></span>
- <span data-ttu-id="6f51f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6f51f-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="6f51f-107">La tabella nello schema di ricerca avanzata contiene informazioni sulle attività correlate ai file nelle app cloud e nei servizi `AppFileEvents` monitorati da Microsoft Cloud App Security. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="6f51f-107">The `AppFileEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file-related activities in cloud apps and services monitored by Microsoft Cloud App Security.</span></span> <span data-ttu-id="6f51f-108">Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="6f51f-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="6f51f-109">Per informazioni dettagliate sui tipi di eventi (valori) supportati da una tabella, utilizzare il riferimento allo schema predefinito `ActionType` disponibile nel Centro sicurezza. [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)</span><span class="sxs-lookup"><span data-stu-id="6f51f-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="6f51f-110">Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="6f51f-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="6f51f-111">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="6f51f-111">Column name</span></span> | <span data-ttu-id="6f51f-112">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="6f51f-112">Data type</span></span> | <span data-ttu-id="6f51f-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6f51f-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="6f51f-114">datetime</span><span class="sxs-lookup"><span data-stu-id="6f51f-114">datetime</span></span> | <span data-ttu-id="6f51f-115">Data e ora di registrazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="6f51f-115">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="6f51f-116">stringa</span><span class="sxs-lookup"><span data-stu-id="6f51f-116">string</span></span> | <span data-ttu-id="6f51f-117">Tipo di attività che ha attivato l'evento.</span><span class="sxs-lookup"><span data-stu-id="6f51f-117">Type of activity that triggered the event.</span></span> <span data-ttu-id="6f51f-118">Per informazioni [dettagliate, vedere le informazioni di riferimento](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) sullo schema nel portale</span><span class="sxs-lookup"><span data-stu-id="6f51f-118">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="6f51f-119">stringa</span><span class="sxs-lookup"><span data-stu-id="6f51f-119">string</span></span> | <span data-ttu-id="6f51f-120">Applicazione che ha eseguito l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="6f51f-120">Application that performed the recorded action</span></span> |
| `FileName` | <span data-ttu-id="6f51f-121">stringa</span><span class="sxs-lookup"><span data-stu-id="6f51f-121">string</span></span> | <span data-ttu-id="6f51f-122">Nome del file a cui è stata applicata l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="6f51f-122">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="6f51f-123">stringa</span><span class="sxs-lookup"><span data-stu-id="6f51f-123">string</span></span> | <span data-ttu-id="6f51f-124">Cartella contenente il file a cui è stata applicata l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="6f51f-124">Folder containing the file that the recorded action was applied to</span></span> |
| `PreviousFileName` | <span data-ttu-id="6f51f-125">stringa</span><span class="sxs-lookup"><span data-stu-id="6f51f-125">string</span></span> | <span data-ttu-id="6f51f-126">Nome originale del file rinominato in seguito all'azione</span><span class="sxs-lookup"><span data-stu-id="6f51f-126">Original name of the file that was renamed as a result of the action</span></span> |
| `PreviousFolderPath` | <span data-ttu-id="6f51f-127">stringa</span><span class="sxs-lookup"><span data-stu-id="6f51f-127">string</span></span> | <span data-ttu-id="6f51f-128">Cartella originale contenente il file prima dell'applicazione dell'azione registrata</span><span class="sxs-lookup"><span data-stu-id="6f51f-128">Original folder containing the file before the recorded action was applied</span></span> |
| `Protocol` | <span data-ttu-id="6f51f-129">stringa</span><span class="sxs-lookup"><span data-stu-id="6f51f-129">string</span></span> | <span data-ttu-id="6f51f-130">Protocollo di rete utilizzato</span><span class="sxs-lookup"><span data-stu-id="6f51f-130">Network protocol used</span></span> |
| `AccountName` | <span data-ttu-id="6f51f-131">stringa</span><span class="sxs-lookup"><span data-stu-id="6f51f-131">string</span></span> | <span data-ttu-id="6f51f-132">Nome utente dell'account</span><span class="sxs-lookup"><span data-stu-id="6f51f-132">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="6f51f-133">stringa</span><span class="sxs-lookup"><span data-stu-id="6f51f-133">string</span></span> | <span data-ttu-id="6f51f-134">Dominio dell'account</span><span class="sxs-lookup"><span data-stu-id="6f51f-134">Domain of the account</span></span> |
| `AccountSid` | <span data-ttu-id="6f51f-135">stringa</span><span class="sxs-lookup"><span data-stu-id="6f51f-135">string</span></span> | <span data-ttu-id="6f51f-136">Identificatore di sicurezza (SID) dell'account</span><span class="sxs-lookup"><span data-stu-id="6f51f-136">Security Identifier (SID) of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="6f51f-137">stringa</span><span class="sxs-lookup"><span data-stu-id="6f51f-137">string</span></span> | <span data-ttu-id="6f51f-138">Nome dell'entità utente (UPN) dell'account</span><span class="sxs-lookup"><span data-stu-id="6f51f-138">User principal name (UPN) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="6f51f-139">stringa</span><span class="sxs-lookup"><span data-stu-id="6f51f-139">string</span></span> | <span data-ttu-id="6f51f-140">Identificatore univoco per l'account in Azure AD</span><span class="sxs-lookup"><span data-stu-id="6f51f-140">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="6f51f-141">stringa</span><span class="sxs-lookup"><span data-stu-id="6f51f-141">string</span></span> | <span data-ttu-id="6f51f-142">Nome dell'utente dell'account visualizzato nella rubrica.</span><span class="sxs-lookup"><span data-stu-id="6f51f-142">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="6f51f-143">In genere una combinazione di un nome o di un dato nome, un'iniziazione intermedia e un cognome o un cognome.</span><span class="sxs-lookup"><span data-stu-id="6f51f-143">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="6f51f-144">stringa</span><span class="sxs-lookup"><span data-stu-id="6f51f-144">string</span></span> | <span data-ttu-id="6f51f-145">Nome di dominio completo (FQDN) del dispositivo</span><span class="sxs-lookup"><span data-stu-id="6f51f-145">Fully qualified domain name (FQDN) of the device</span></span> |
| `DeviceType` | <span data-ttu-id="6f51f-146">stringa</span><span class="sxs-lookup"><span data-stu-id="6f51f-146">string</span></span> | <span data-ttu-id="6f51f-147">Tipo di dispositivo</span><span class="sxs-lookup"><span data-stu-id="6f51f-147">Type of device</span></span> | 
| `OSPlatform` | <span data-ttu-id="6f51f-148">stringa</span><span class="sxs-lookup"><span data-stu-id="6f51f-148">string</span></span> | <span data-ttu-id="6f51f-149">Piattaforma del sistema operativo in esecuzione nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6f51f-149">Platform of the operating system running on the device.</span></span> <span data-ttu-id="6f51f-150">Ciò indica specifici sistemi operativi, incluse variazioni all'interno della stessa famiglia di prodotti, come Windows 10 e Windows 7.</span><span class="sxs-lookup"><span data-stu-id="6f51f-150">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="6f51f-151">stringa</span><span class="sxs-lookup"><span data-stu-id="6f51f-151">string</span></span> | <span data-ttu-id="6f51f-152">Indirizzo IP assegnato all'endpoint e utilizzato durante le comunicazioni di rete correlate</span><span class="sxs-lookup"><span data-stu-id="6f51f-152">IP address assigned to the endpoint and used during related network communications</span></span> |
| `Port` | <span data-ttu-id="6f51f-153">stringa</span><span class="sxs-lookup"><span data-stu-id="6f51f-153">string</span></span> | <span data-ttu-id="6f51f-154">Porta TCP utilizzata durante la comunicazione</span><span class="sxs-lookup"><span data-stu-id="6f51f-154">TCP port used during communication</span></span>  |
| `DestinationDeviceName` | <span data-ttu-id="6f51f-155">stringa</span><span class="sxs-lookup"><span data-stu-id="6f51f-155">string</span></span> | <span data-ttu-id="6f51f-156">Nome del dispositivo che esegue l'applicazione server che ha elaborato l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="6f51f-156">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="6f51f-157">stringa</span><span class="sxs-lookup"><span data-stu-id="6f51f-157">string</span></span> | <span data-ttu-id="6f51f-158">Indirizzo IP del dispositivo che esegue l'applicazione server che ha elaborato l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="6f51f-158">IP address of the device running the server application that processed the recorded action</span></span> |
| `DestinationPort` | <span data-ttu-id="6f51f-159">stringa</span><span class="sxs-lookup"><span data-stu-id="6f51f-159">string</span></span> | <span data-ttu-id="6f51f-160">Porta di destinazione delle comunicazioni di rete correlate</span><span class="sxs-lookup"><span data-stu-id="6f51f-160">Destination port of related network communications</span></span> |
| `Location` | <span data-ttu-id="6f51f-161">stringa</span><span class="sxs-lookup"><span data-stu-id="6f51f-161">string</span></span> | <span data-ttu-id="6f51f-162">Città, paese o altra posizione geografica associata all'evento</span><span class="sxs-lookup"><span data-stu-id="6f51f-162">City, country, or other geographic location associated with the event</span></span> |
| `Isp` | <span data-ttu-id="6f51f-163">stringa</span><span class="sxs-lookup"><span data-stu-id="6f51f-163">string</span></span> | <span data-ttu-id="6f51f-164">Provider di servizi Internet (ISP) associato all'indirizzo IP dell'endpoint</span><span class="sxs-lookup"><span data-stu-id="6f51f-164">Internet service provider (ISP) associated with the endpoint IP address</span></span> |
| `ReportId` | <span data-ttu-id="6f51f-165">long</span><span class="sxs-lookup"><span data-stu-id="6f51f-165">long</span></span> | <span data-ttu-id="6f51f-166">Identificatore univoco dell'evento</span><span class="sxs-lookup"><span data-stu-id="6f51f-166">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="6f51f-167">stringa</span><span class="sxs-lookup"><span data-stu-id="6f51f-167">string</span></span> | <span data-ttu-id="6f51f-168">Ulteriori informazioni sull'entità o sull'evento</span><span class="sxs-lookup"><span data-stu-id="6f51f-168">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="6f51f-169">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="6f51f-169">Related topics</span></span>
- [<span data-ttu-id="6f51f-170">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="6f51f-170">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="6f51f-171">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="6f51f-171">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="6f51f-172">Utilizzare le query condivise</span><span class="sxs-lookup"><span data-stu-id="6f51f-172">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="6f51f-173">Cercare tra dispositivi, posta elettronica, app e identità</span><span class="sxs-lookup"><span data-stu-id="6f51f-173">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="6f51f-174">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="6f51f-174">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="6f51f-175">Applicare le procedure consigliate per le query</span><span class="sxs-lookup"><span data-stu-id="6f51f-175">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
