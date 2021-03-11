---
title: Tabella IdentityQueryEvents nello schema di ricerca avanzata
description: Informazioni sugli eventi di query di Active Directory nella tabella IdentityQueryEvents dello schema di ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca delle minacce informatiche, Microsoft Threat Protection, Microsoft 365, mtp, m365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, IdentityQueryEvents, Azure AD, Active Directory, Azure ATP, identità, query LDAP
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
ms.openlocfilehash: eb1f408b61444771f5d450b46dbc9c2b4a009e4c
ms.sourcegitcommit: 88ab08c0fa1acbc9e066009e131b9f2b0d506c64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/10/2021
ms.locfileid: "50712331"
---
# <a name="identityqueryevents"></a><span data-ttu-id="55d82-104">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="55d82-104">IdentityQueryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="55d82-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="55d82-105">**Applies to:**</span></span>
- <span data-ttu-id="55d82-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="55d82-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="55d82-107">La tabella nello schema di ricerca avanzata contiene informazioni sulle query eseguite su oggetti Active Directory, ad esempio `IdentityQueryEvents` utenti, gruppi, dispositivi [](advanced-hunting-overview.md) e domini.</span><span class="sxs-lookup"><span data-stu-id="55d82-107">The `IdentityQueryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about queries performed against Active Directory objects, such as users, groups, devices, and domains.</span></span> <span data-ttu-id="55d82-108">Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="55d82-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="55d82-109">Per informazioni dettagliate sui tipi di eventi (valori) supportati da una tabella, utilizzare il riferimento allo schema predefinito `ActionType` disponibile nel Centro sicurezza.</span><span class="sxs-lookup"><span data-stu-id="55d82-109">For detailed information about the events types (`ActionType` values) supported by a table, use the built-in schema reference available in the security center.</span></span>

<span data-ttu-id="55d82-110">Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="55d82-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="55d82-111">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="55d82-111">Column name</span></span> | <span data-ttu-id="55d82-112">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="55d82-112">Data type</span></span> | <span data-ttu-id="55d82-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="55d82-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="55d82-114">datetime</span><span class="sxs-lookup"><span data-stu-id="55d82-114">datetime</span></span> | <span data-ttu-id="55d82-115">Data e ora di registrazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="55d82-115">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="55d82-116">stringa</span><span class="sxs-lookup"><span data-stu-id="55d82-116">string</span></span> | <span data-ttu-id="55d82-117">Tipo di attività che ha attivato l'evento.</span><span class="sxs-lookup"><span data-stu-id="55d82-117">Type of activity that triggered the event.</span></span> <span data-ttu-id="55d82-118">Per informazioni [dettagliate, vedere la guida di riferimento](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) allo schema nel portale</span><span class="sxs-lookup"><span data-stu-id="55d82-118">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="55d82-119">stringa</span><span class="sxs-lookup"><span data-stu-id="55d82-119">string</span></span> | <span data-ttu-id="55d82-120">Applicazione che ha eseguito l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="55d82-120">Application that performed the recorded action</span></span> |
| `QueryType` | <span data-ttu-id="55d82-121">stringa</span><span class="sxs-lookup"><span data-stu-id="55d82-121">string</span></span> | <span data-ttu-id="55d82-122">Tipo di query, ad esempio QueryGroup, QueryUser o EnumerateUsers</span><span class="sxs-lookup"><span data-stu-id="55d82-122">Type of query, such as QueryGroup, QueryUser, or EnumerateUsers</span></span> |
| `QueryTarget` | <span data-ttu-id="55d82-123">stringa</span><span class="sxs-lookup"><span data-stu-id="55d82-123">string</span></span> | <span data-ttu-id="55d82-124">Nome dell'utente, del gruppo, del dispositivo, del dominio o di qualsiasi altro tipo di entità su cui viene eseguita la query</span><span class="sxs-lookup"><span data-stu-id="55d82-124">Name of user, group, device, domain, or any other entity type being queried</span></span> |
| `Query` | <span data-ttu-id="55d82-125">stringa</span><span class="sxs-lookup"><span data-stu-id="55d82-125">string</span></span> | <span data-ttu-id="55d82-126">Stringa utilizzata per eseguire la query</span><span class="sxs-lookup"><span data-stu-id="55d82-126">String used to run the query</span></span> |
| `Protocol` | <span data-ttu-id="55d82-127">stringa</span><span class="sxs-lookup"><span data-stu-id="55d82-127">string</span></span> | <span data-ttu-id="55d82-128">Protocollo utilizzato durante la comunicazione</span><span class="sxs-lookup"><span data-stu-id="55d82-128">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="55d82-129">stringa</span><span class="sxs-lookup"><span data-stu-id="55d82-129">string</span></span> | <span data-ttu-id="55d82-130">Nome utente dell'account</span><span class="sxs-lookup"><span data-stu-id="55d82-130">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="55d82-131">stringa</span><span class="sxs-lookup"><span data-stu-id="55d82-131">string</span></span> | <span data-ttu-id="55d82-132">Dominio dell'account</span><span class="sxs-lookup"><span data-stu-id="55d82-132">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="55d82-133">stringa</span><span class="sxs-lookup"><span data-stu-id="55d82-133">string</span></span> | <span data-ttu-id="55d82-134">Nome dell'entità utente (UPN) dell'account</span><span class="sxs-lookup"><span data-stu-id="55d82-134">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="55d82-135">stringa</span><span class="sxs-lookup"><span data-stu-id="55d82-135">string</span></span> | <span data-ttu-id="55d82-136">Identificatore di sicurezza (SID) dell'account</span><span class="sxs-lookup"><span data-stu-id="55d82-136">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="55d82-137">stringa</span><span class="sxs-lookup"><span data-stu-id="55d82-137">string</span></span> | <span data-ttu-id="55d82-138">Identificatore univoco per l'account in Azure AD</span><span class="sxs-lookup"><span data-stu-id="55d82-138">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="55d82-139">stringa</span><span class="sxs-lookup"><span data-stu-id="55d82-139">string</span></span> | <span data-ttu-id="55d82-140">Nome dell'utente dell'account visualizzato nella rubrica.</span><span class="sxs-lookup"><span data-stu-id="55d82-140">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="55d82-141">In genere una combinazione di un nome o di un dato nome, un'iniziazione intermedia e un cognome o un cognome.</span><span class="sxs-lookup"><span data-stu-id="55d82-141">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="55d82-142">stringa</span><span class="sxs-lookup"><span data-stu-id="55d82-142">string</span></span> | <span data-ttu-id="55d82-143">Nome di dominio completo (FQDN) dell'endpoint</span><span class="sxs-lookup"><span data-stu-id="55d82-143">Fully qualified domain name (FQDN) of the endpoint</span></span> |
| `IPAddress` | <span data-ttu-id="55d82-144">stringa</span><span class="sxs-lookup"><span data-stu-id="55d82-144">string</span></span> | <span data-ttu-id="55d82-145">Indirizzo IP assegnato all'endpoint e utilizzato durante le comunicazioni di rete correlate</span><span class="sxs-lookup"><span data-stu-id="55d82-145">IP address assigned to the endpoint and used during related network communications</span></span> |
| `Port` | <span data-ttu-id="55d82-146">stringa</span><span class="sxs-lookup"><span data-stu-id="55d82-146">string</span></span> | <span data-ttu-id="55d82-147">Porta TCP utilizzata durante la comunicazione</span><span class="sxs-lookup"><span data-stu-id="55d82-147">TCP port used during communication</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="55d82-148">stringa</span><span class="sxs-lookup"><span data-stu-id="55d82-148">string</span></span> | <span data-ttu-id="55d82-149">Nome del dispositivo che esegue l'applicazione server che ha elaborato l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="55d82-149">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="55d82-150">stringa</span><span class="sxs-lookup"><span data-stu-id="55d82-150">string</span></span> | <span data-ttu-id="55d82-151">Indirizzo IP del dispositivo che esegue l'applicazione server che ha elaborato l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="55d82-151">IP address of the device running the server application that processed the recorded action</span></span> |
| `DestinationPort` | <span data-ttu-id="55d82-152">stringa</span><span class="sxs-lookup"><span data-stu-id="55d82-152">string</span></span> | <span data-ttu-id="55d82-153">Porta di destinazione delle comunicazioni di rete correlate</span><span class="sxs-lookup"><span data-stu-id="55d82-153">Destination port of related network communications</span></span> |
| `TargetDeviceName` | <span data-ttu-id="55d82-154">stringa</span><span class="sxs-lookup"><span data-stu-id="55d82-154">string</span></span> | <span data-ttu-id="55d82-155">Nome di dominio completo (FQDN) del dispositivo a cui è stata applicata l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="55d82-155">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `TargetAccountUpn` | <span data-ttu-id="55d82-156">stringa</span><span class="sxs-lookup"><span data-stu-id="55d82-156">string</span></span> | <span data-ttu-id="55d82-157">Nome dell'entità utente (UPN) dell'account a cui è stata applicata l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="55d82-157">User principal name (UPN) of the account that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="55d82-158">stringa</span><span class="sxs-lookup"><span data-stu-id="55d82-158">string</span></span> | <span data-ttu-id="55d82-159">Nome visualizzato dell'account a cui è stata applicata l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="55d82-159">Display name of the account that the recorded action was applied to</span></span> |
| `Location` | <span data-ttu-id="55d82-160">stringa</span><span class="sxs-lookup"><span data-stu-id="55d82-160">string</span></span> | <span data-ttu-id="55d82-161">Città, paese o altra posizione geografica associata all'evento</span><span class="sxs-lookup"><span data-stu-id="55d82-161">City, country, or other geographic location associated with the event</span></span> |
| `ReportId` | <span data-ttu-id="55d82-162">long</span><span class="sxs-lookup"><span data-stu-id="55d82-162">long</span></span> | <span data-ttu-id="55d82-163">Identificatore univoco dell'evento</span><span class="sxs-lookup"><span data-stu-id="55d82-163">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="55d82-164">stringa</span><span class="sxs-lookup"><span data-stu-id="55d82-164">string</span></span> | <span data-ttu-id="55d82-165">Ulteriori informazioni sull'entità o sull'evento</span><span class="sxs-lookup"><span data-stu-id="55d82-165">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="55d82-166">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="55d82-166">Related topics</span></span>
- [<span data-ttu-id="55d82-167">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="55d82-167">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="55d82-168">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="55d82-168">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="55d82-169">Utilizzare le query condivise</span><span class="sxs-lookup"><span data-stu-id="55d82-169">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="55d82-170">Cercare tra dispositivi, posta elettronica, app e identità</span><span class="sxs-lookup"><span data-stu-id="55d82-170">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="55d82-171">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="55d82-171">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="55d82-172">Applicare le procedure consigliate per le query</span><span class="sxs-lookup"><span data-stu-id="55d82-172">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
