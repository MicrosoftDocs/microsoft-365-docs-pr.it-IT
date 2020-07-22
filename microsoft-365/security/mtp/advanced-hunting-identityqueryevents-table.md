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
ms.openlocfilehash: 436c4d7306f9f5febd614489090a0a10929ba3c9
ms.sourcegitcommit: b4119682bd3c036289e851fff56fde869c816479
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/22/2020
ms.locfileid: "45204876"
---
# <a name="identityqueryevents"></a><span data-ttu-id="1fa6a-104">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="1fa6a-104">IdentityQueryEvents</span></span>

<span data-ttu-id="1fa6a-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="1fa6a-105">**Applies to:**</span></span>
- <span data-ttu-id="1fa6a-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="1fa6a-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="1fa6a-107">La `IdentityQueryEvents` tabella nello schema di [ricerca avanzata](advanced-hunting-overview.md) contiene informazioni sulle query eseguite su oggetti di Active Directory, ad esempio utenti, gruppi, dispositivi e domini.</span><span class="sxs-lookup"><span data-stu-id="1fa6a-107">The `IdentityQueryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about queries performed against Active Directory objects, such as users, groups, devices, and domains.</span></span> <span data-ttu-id="1fa6a-108">Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="1fa6a-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="1fa6a-109">Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="1fa6a-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="1fa6a-110">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="1fa6a-110">Column name</span></span> | <span data-ttu-id="1fa6a-111">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="1fa6a-111">Data type</span></span> | <span data-ttu-id="1fa6a-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1fa6a-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="1fa6a-113">datetime</span><span class="sxs-lookup"><span data-stu-id="1fa6a-113">datetime</span></span> | <span data-ttu-id="1fa6a-114">Data e ora di registrazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="1fa6a-114">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="1fa6a-115">stringa</span><span class="sxs-lookup"><span data-stu-id="1fa6a-115">string</span></span> | <span data-ttu-id="1fa6a-116">Tipo di attività che ha attivato l'evento</span><span class="sxs-lookup"><span data-stu-id="1fa6a-116">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="1fa6a-117">stringa</span><span class="sxs-lookup"><span data-stu-id="1fa6a-117">string</span></span> | <span data-ttu-id="1fa6a-118">Applicazione in cui è stata eseguita l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="1fa6a-118">Application that performed the recorded action</span></span> |
| `QueryType` | <span data-ttu-id="1fa6a-119">stringa</span><span class="sxs-lookup"><span data-stu-id="1fa6a-119">string</span></span> | <span data-ttu-id="1fa6a-120">Tipo di query, ad esempio QueryGroup, QueryUser o EnumerateUsers</span><span class="sxs-lookup"><span data-stu-id="1fa6a-120">Type of query, such as QueryGroup, QueryUser, or EnumerateUsers</span></span> |
| `QueryTarget` | <span data-ttu-id="1fa6a-121">stringa</span><span class="sxs-lookup"><span data-stu-id="1fa6a-121">string</span></span> | <span data-ttu-id="1fa6a-122">Nome dell'utente, del gruppo, del dispositivo, del dominio o di qualsiasi altro tipo di entità su cui viene eseguita la query</span><span class="sxs-lookup"><span data-stu-id="1fa6a-122">Name of user, group, device, domain, or any other entity type being queried</span></span> |
| `Query` | <span data-ttu-id="1fa6a-123">stringa</span><span class="sxs-lookup"><span data-stu-id="1fa6a-123">string</span></span> | <span data-ttu-id="1fa6a-124">Stringa utilizzata per eseguire la query</span><span class="sxs-lookup"><span data-stu-id="1fa6a-124">String used to run the query</span></span> |
| `Protocol` | <span data-ttu-id="1fa6a-125">stringa</span><span class="sxs-lookup"><span data-stu-id="1fa6a-125">string</span></span> | <span data-ttu-id="1fa6a-126">Protocollo utilizzato durante la comunicazione</span><span class="sxs-lookup"><span data-stu-id="1fa6a-126">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="1fa6a-127">stringa</span><span class="sxs-lookup"><span data-stu-id="1fa6a-127">string</span></span> | <span data-ttu-id="1fa6a-128">Nome utente dell'account</span><span class="sxs-lookup"><span data-stu-id="1fa6a-128">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="1fa6a-129">stringa</span><span class="sxs-lookup"><span data-stu-id="1fa6a-129">string</span></span> | <span data-ttu-id="1fa6a-130">Dominio dell'account</span><span class="sxs-lookup"><span data-stu-id="1fa6a-130">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="1fa6a-131">stringa</span><span class="sxs-lookup"><span data-stu-id="1fa6a-131">string</span></span> | <span data-ttu-id="1fa6a-132">Nome dell'entità utente (UPN) dell'account</span><span class="sxs-lookup"><span data-stu-id="1fa6a-132">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="1fa6a-133">stringa</span><span class="sxs-lookup"><span data-stu-id="1fa6a-133">string</span></span> | <span data-ttu-id="1fa6a-134">ID di sicurezza (SID) dell'account</span><span class="sxs-lookup"><span data-stu-id="1fa6a-134">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="1fa6a-135">stringa</span><span class="sxs-lookup"><span data-stu-id="1fa6a-135">string</span></span> | <span data-ttu-id="1fa6a-136">Identificatore univoco per l'account in Azure AD</span><span class="sxs-lookup"><span data-stu-id="1fa6a-136">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="1fa6a-137">stringa</span><span class="sxs-lookup"><span data-stu-id="1fa6a-137">string</span></span> | <span data-ttu-id="1fa6a-138">Nome dell'account utente visualizzato nella rubrica.</span><span class="sxs-lookup"><span data-stu-id="1fa6a-138">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="1fa6a-139">In genere una combinazione di un nome o di un cognome, di un'iniziazione centrale e di un ultimo nome.</span><span class="sxs-lookup"><span data-stu-id="1fa6a-139">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="1fa6a-140">stringa</span><span class="sxs-lookup"><span data-stu-id="1fa6a-140">string</span></span> | <span data-ttu-id="1fa6a-141">Nome di dominio completo (FQDN) dell'endpoint</span><span class="sxs-lookup"><span data-stu-id="1fa6a-141">Fully qualified domain name (FQDN) of the endpoint</span></span> |
| `IPAddress` | <span data-ttu-id="1fa6a-142">stringa</span><span class="sxs-lookup"><span data-stu-id="1fa6a-142">string</span></span> | <span data-ttu-id="1fa6a-143">Indirizzo IP assegnato all'endpoint e utilizzato durante le comunicazioni di rete correlate</span><span class="sxs-lookup"><span data-stu-id="1fa6a-143">IP address assigned to the endpoint and used during related network communications</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="1fa6a-144">stringa</span><span class="sxs-lookup"><span data-stu-id="1fa6a-144">string</span></span> | <span data-ttu-id="1fa6a-145">Nome del dispositivo che esegue l'applicazione server che ha elaborato l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="1fa6a-145">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="1fa6a-146">stringa</span><span class="sxs-lookup"><span data-stu-id="1fa6a-146">string</span></span> | <span data-ttu-id="1fa6a-147">Indirizzo IP del dispositivo che esegue l'applicazione server che ha elaborato l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="1fa6a-147">IP address of the device running the server application that processed the recorded action</span></span> |
| `TargetDeviceName` | <span data-ttu-id="1fa6a-148">stringa</span><span class="sxs-lookup"><span data-stu-id="1fa6a-148">string</span></span> | <span data-ttu-id="1fa6a-149">Nome di dominio completo (FQDN) del dispositivo a cui è stata applicata l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="1fa6a-149">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `TargetAccountUpn` | <span data-ttu-id="1fa6a-150">stringa</span><span class="sxs-lookup"><span data-stu-id="1fa6a-150">string</span></span> | <span data-ttu-id="1fa6a-151">Nome dell'entità utente (UPN) dell'account a cui è stata applicata l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="1fa6a-151">User principal name (UPN) of the account that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="1fa6a-152">stringa</span><span class="sxs-lookup"><span data-stu-id="1fa6a-152">string</span></span> | <span data-ttu-id="1fa6a-153">Nome visualizzato dell'account a cui è stata applicata l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="1fa6a-153">Display name of the account that the recorded action was applied to</span></span> |
| `Location` | <span data-ttu-id="1fa6a-154">stringa</span><span class="sxs-lookup"><span data-stu-id="1fa6a-154">string</span></span> | <span data-ttu-id="1fa6a-155">Città, paese o altra località geografica associata all'evento</span><span class="sxs-lookup"><span data-stu-id="1fa6a-155">City, country, or other geographic location associated with the event</span></span> |
| `ReportId` | <span data-ttu-id="1fa6a-156">long</span><span class="sxs-lookup"><span data-stu-id="1fa6a-156">long</span></span> | <span data-ttu-id="1fa6a-157">Identificatore univoco per l'evento</span><span class="sxs-lookup"><span data-stu-id="1fa6a-157">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="1fa6a-158">stringa</span><span class="sxs-lookup"><span data-stu-id="1fa6a-158">string</span></span> | <span data-ttu-id="1fa6a-159">Ulteriori informazioni sull'entità o sull'evento</span><span class="sxs-lookup"><span data-stu-id="1fa6a-159">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="1fa6a-160">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="1fa6a-160">Related topics</span></span>
- [<span data-ttu-id="1fa6a-161">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="1fa6a-161">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="1fa6a-162">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="1fa6a-162">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="1fa6a-163">Utilizzare le query condivise</span><span class="sxs-lookup"><span data-stu-id="1fa6a-163">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="1fa6a-164">Ricerca delle minacce attraverso dispositivi e posta elettronica</span><span class="sxs-lookup"><span data-stu-id="1fa6a-164">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="1fa6a-165">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="1fa6a-165">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="1fa6a-166">Applicare le procedure consigliate per le query</span><span class="sxs-lookup"><span data-stu-id="1fa6a-166">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
