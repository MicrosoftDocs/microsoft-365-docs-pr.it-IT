---
title: Tabella IdentityQueryEvents nello schema di caccia avanzato
description: Informazioni sugli eventi di query di Active Directory nella tabella IdentityQueryEvents dello schema di caccia avanzato
keywords: caccia avanzata, caccia alle minacce, Cyber-caccia alle minacce, Microsoft Threat Protection, Microsoft 365, MTP, M365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, IdentityQueryEvents, Azure AD, Active Directory, Azure ATP, identità, query LDAP
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
ms.openlocfilehash: 3b2459d0d90f6160bcbac7efbb5c0cc0683ae8c2
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196810"
---
# <a name="identityqueryevents"></a><span data-ttu-id="4d55d-104">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="4d55d-104">IdentityQueryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="4d55d-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="4d55d-105">**Applies to:**</span></span>
- <span data-ttu-id="4d55d-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="4d55d-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="4d55d-107">La `IdentityQueryEvents` tabella nello schema di [ricerca avanzata](advanced-hunting-overview.md) contiene informazioni sulle query eseguite su oggetti di Active Directory, ad esempio utenti, gruppi, dispositivi e domini.</span><span class="sxs-lookup"><span data-stu-id="4d55d-107">The `IdentityQueryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about queries performed against Active Directory objects, such as users, groups, devices, and domains.</span></span> <span data-ttu-id="4d55d-108">Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="4d55d-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="4d55d-109">Per informazioni dettagliate sui tipi di eventi ( `ActionType` valori) supportati da una tabella, utilizzare la Guida di [riferimento allo schema incorporata](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) disponibile nel centro sicurezza.</span><span class="sxs-lookup"><span data-stu-id="4d55d-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="4d55d-110">Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="4d55d-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="4d55d-111">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="4d55d-111">Column name</span></span> | <span data-ttu-id="4d55d-112">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="4d55d-112">Data type</span></span> | <span data-ttu-id="4d55d-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4d55d-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="4d55d-114">datetime</span><span class="sxs-lookup"><span data-stu-id="4d55d-114">datetime</span></span> | <span data-ttu-id="4d55d-115">Data e ora di registrazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="4d55d-115">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="4d55d-116">stringa</span><span class="sxs-lookup"><span data-stu-id="4d55d-116">string</span></span> | <span data-ttu-id="4d55d-117">Tipo di attività che ha attivato l'evento.</span><span class="sxs-lookup"><span data-stu-id="4d55d-117">Type of activity that triggered the event.</span></span> <span data-ttu-id="4d55d-118">Per informazioni dettagliate, vedere la Guida [di riferimento allo schema in-Portal.](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)</span><span class="sxs-lookup"><span data-stu-id="4d55d-118">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="4d55d-119">stringa</span><span class="sxs-lookup"><span data-stu-id="4d55d-119">string</span></span> | <span data-ttu-id="4d55d-120">Applicazione in cui è stata eseguita l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="4d55d-120">Application that performed the recorded action</span></span> |
| `QueryType` | <span data-ttu-id="4d55d-121">stringa</span><span class="sxs-lookup"><span data-stu-id="4d55d-121">string</span></span> | <span data-ttu-id="4d55d-122">Tipo di query, ad esempio QueryGroup, QueryUser o EnumerateUsers</span><span class="sxs-lookup"><span data-stu-id="4d55d-122">Type of query, such as QueryGroup, QueryUser, or EnumerateUsers</span></span> |
| `QueryTarget` | <span data-ttu-id="4d55d-123">stringa</span><span class="sxs-lookup"><span data-stu-id="4d55d-123">string</span></span> | <span data-ttu-id="4d55d-124">Nome dell'utente, del gruppo, del dispositivo, del dominio o di qualsiasi altro tipo di entità su cui viene eseguita la query</span><span class="sxs-lookup"><span data-stu-id="4d55d-124">Name of user, group, device, domain, or any other entity type being queried</span></span> |
| `Query` | <span data-ttu-id="4d55d-125">stringa</span><span class="sxs-lookup"><span data-stu-id="4d55d-125">string</span></span> | <span data-ttu-id="4d55d-126">Stringa utilizzata per eseguire la query</span><span class="sxs-lookup"><span data-stu-id="4d55d-126">String used to run the query</span></span> |
| `Protocol` | <span data-ttu-id="4d55d-127">stringa</span><span class="sxs-lookup"><span data-stu-id="4d55d-127">string</span></span> | <span data-ttu-id="4d55d-128">Protocollo utilizzato durante la comunicazione</span><span class="sxs-lookup"><span data-stu-id="4d55d-128">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="4d55d-129">stringa</span><span class="sxs-lookup"><span data-stu-id="4d55d-129">string</span></span> | <span data-ttu-id="4d55d-130">Nome utente dell'account</span><span class="sxs-lookup"><span data-stu-id="4d55d-130">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="4d55d-131">stringa</span><span class="sxs-lookup"><span data-stu-id="4d55d-131">string</span></span> | <span data-ttu-id="4d55d-132">Dominio dell'account</span><span class="sxs-lookup"><span data-stu-id="4d55d-132">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="4d55d-133">stringa</span><span class="sxs-lookup"><span data-stu-id="4d55d-133">string</span></span> | <span data-ttu-id="4d55d-134">Nome dell'entità utente (UPN) dell'account</span><span class="sxs-lookup"><span data-stu-id="4d55d-134">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="4d55d-135">stringa</span><span class="sxs-lookup"><span data-stu-id="4d55d-135">string</span></span> | <span data-ttu-id="4d55d-136">ID di sicurezza (SID) dell'account</span><span class="sxs-lookup"><span data-stu-id="4d55d-136">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="4d55d-137">stringa</span><span class="sxs-lookup"><span data-stu-id="4d55d-137">string</span></span> | <span data-ttu-id="4d55d-138">Identificatore univoco per l'account in Azure AD</span><span class="sxs-lookup"><span data-stu-id="4d55d-138">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="4d55d-139">stringa</span><span class="sxs-lookup"><span data-stu-id="4d55d-139">string</span></span> | <span data-ttu-id="4d55d-140">Nome dell'account utente visualizzato nella rubrica.</span><span class="sxs-lookup"><span data-stu-id="4d55d-140">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="4d55d-141">In genere una combinazione di un nome o di un cognome, di un'iniziazione centrale e di un ultimo nome.</span><span class="sxs-lookup"><span data-stu-id="4d55d-141">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="4d55d-142">stringa</span><span class="sxs-lookup"><span data-stu-id="4d55d-142">string</span></span> | <span data-ttu-id="4d55d-143">Nome di dominio completo (FQDN) dell'endpoint</span><span class="sxs-lookup"><span data-stu-id="4d55d-143">Fully qualified domain name (FQDN) of the endpoint</span></span> |
| `IPAddress` | <span data-ttu-id="4d55d-144">stringa</span><span class="sxs-lookup"><span data-stu-id="4d55d-144">string</span></span> | <span data-ttu-id="4d55d-145">Indirizzo IP assegnato all'endpoint e utilizzato durante le comunicazioni di rete correlate</span><span class="sxs-lookup"><span data-stu-id="4d55d-145">IP address assigned to the endpoint and used during related network communications</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="4d55d-146">stringa</span><span class="sxs-lookup"><span data-stu-id="4d55d-146">string</span></span> | <span data-ttu-id="4d55d-147">Nome del dispositivo che esegue l'applicazione server che ha elaborato l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="4d55d-147">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="4d55d-148">stringa</span><span class="sxs-lookup"><span data-stu-id="4d55d-148">string</span></span> | <span data-ttu-id="4d55d-149">Indirizzo IP del dispositivo che esegue l'applicazione server che ha elaborato l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="4d55d-149">IP address of the device running the server application that processed the recorded action</span></span> |
| `TargetDeviceName` | <span data-ttu-id="4d55d-150">stringa</span><span class="sxs-lookup"><span data-stu-id="4d55d-150">string</span></span> | <span data-ttu-id="4d55d-151">Nome di dominio completo (FQDN) del dispositivo a cui è stata applicata l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="4d55d-151">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `TargetAccountUpn` | <span data-ttu-id="4d55d-152">stringa</span><span class="sxs-lookup"><span data-stu-id="4d55d-152">string</span></span> | <span data-ttu-id="4d55d-153">Nome dell'entità utente (UPN) dell'account a cui è stata applicata l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="4d55d-153">User principal name (UPN) of the account that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="4d55d-154">stringa</span><span class="sxs-lookup"><span data-stu-id="4d55d-154">string</span></span> | <span data-ttu-id="4d55d-155">Nome visualizzato dell'account a cui è stata applicata l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="4d55d-155">Display name of the account that the recorded action was applied to</span></span> |
| `Location` | <span data-ttu-id="4d55d-156">stringa</span><span class="sxs-lookup"><span data-stu-id="4d55d-156">string</span></span> | <span data-ttu-id="4d55d-157">Città, paese o altra località geografica associata all'evento</span><span class="sxs-lookup"><span data-stu-id="4d55d-157">City, country, or other geographic location associated with the event</span></span> |
| `ReportId` | <span data-ttu-id="4d55d-158">long</span><span class="sxs-lookup"><span data-stu-id="4d55d-158">long</span></span> | <span data-ttu-id="4d55d-159">Identificatore univoco per l'evento</span><span class="sxs-lookup"><span data-stu-id="4d55d-159">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="4d55d-160">stringa</span><span class="sxs-lookup"><span data-stu-id="4d55d-160">string</span></span> | <span data-ttu-id="4d55d-161">Ulteriori informazioni sull'entità o sull'evento</span><span class="sxs-lookup"><span data-stu-id="4d55d-161">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="4d55d-162">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="4d55d-162">Related topics</span></span>
- [<span data-ttu-id="4d55d-163">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="4d55d-163">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="4d55d-164">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="4d55d-164">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="4d55d-165">Utilizzare le query condivise</span><span class="sxs-lookup"><span data-stu-id="4d55d-165">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="4d55d-166">Cercare tra dispositivi, posta elettronica, app e identità</span><span class="sxs-lookup"><span data-stu-id="4d55d-166">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="4d55d-167">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="4d55d-167">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="4d55d-168">Applicare le procedure consigliate per le query</span><span class="sxs-lookup"><span data-stu-id="4d55d-168">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
