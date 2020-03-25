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
ms.openlocfilehash: b2fc94d6ac6606c97b4824bc556b7299a2bd8ec7
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929274"
---
# <a name="identityqueryevents"></a><span data-ttu-id="88acd-104">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="88acd-104">IdentityQueryEvents</span></span>

<span data-ttu-id="88acd-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="88acd-105">**Applies to:**</span></span>
- <span data-ttu-id="88acd-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="88acd-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="88acd-107">La `IdentityQueryEvents` tabella nello schema di [ricerca avanzata](advanced-hunting-overview.md) contiene informazioni sulle query eseguite su oggetti di Active Directory, ad esempio utenti, gruppi, dispositivi e domini.</span><span class="sxs-lookup"><span data-stu-id="88acd-107">The `IdentityQueryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about queries performed against Active Directory objects, such as users, groups, devices, and domains.</span></span> <span data-ttu-id="88acd-108">Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="88acd-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="88acd-109">Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="88acd-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="88acd-110">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="88acd-110">Column name</span></span> | <span data-ttu-id="88acd-111">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="88acd-111">Data type</span></span> | <span data-ttu-id="88acd-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="88acd-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="88acd-113">datetime</span><span class="sxs-lookup"><span data-stu-id="88acd-113">datetime</span></span> | <span data-ttu-id="88acd-114">Data e ora di registrazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="88acd-114">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="88acd-115">stringa</span><span class="sxs-lookup"><span data-stu-id="88acd-115">string</span></span> | <span data-ttu-id="88acd-116">Tipo di attività che ha attivato l'evento</span><span class="sxs-lookup"><span data-stu-id="88acd-116">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="88acd-117">stringa</span><span class="sxs-lookup"><span data-stu-id="88acd-117">string</span></span> | <span data-ttu-id="88acd-118">Applicazione in cui è stata eseguita l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="88acd-118">Application that performed the recorded action</span></span> |
| `Query` | <span data-ttu-id="88acd-119">stringa</span><span class="sxs-lookup"><span data-stu-id="88acd-119">string</span></span> | <span data-ttu-id="88acd-120">Tipo di query: QueryGroup, QueryUser o EnumerateUsers</span><span class="sxs-lookup"><span data-stu-id="88acd-120">Type of query: QueryGroup, QueryUser, or EnumerateUsers</span></span> |
| `QueryObject` | <span data-ttu-id="88acd-121">stringa</span><span class="sxs-lookup"><span data-stu-id="88acd-121">string</span></span> | <span data-ttu-id="88acd-122">Nome dell'utente, del gruppo, del dispositivo, del dominio o di qualsiasi altro tipo di entità su cui viene eseguita la query</span><span class="sxs-lookup"><span data-stu-id="88acd-122">Name of the user, group, device, domain, or any other entity type being queried</span></span> |
| `Protocol` | <span data-ttu-id="88acd-123">stringa</span><span class="sxs-lookup"><span data-stu-id="88acd-123">string</span></span> | <span data-ttu-id="88acd-124">Protocollo utilizzato durante la comunicazione</span><span class="sxs-lookup"><span data-stu-id="88acd-124">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="88acd-125">stringa</span><span class="sxs-lookup"><span data-stu-id="88acd-125">string</span></span> | <span data-ttu-id="88acd-126">Nome utente dell'account</span><span class="sxs-lookup"><span data-stu-id="88acd-126">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="88acd-127">stringa</span><span class="sxs-lookup"><span data-stu-id="88acd-127">string</span></span> | <span data-ttu-id="88acd-128">Dominio dell'account</span><span class="sxs-lookup"><span data-stu-id="88acd-128">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="88acd-129">stringa</span><span class="sxs-lookup"><span data-stu-id="88acd-129">string</span></span> | <span data-ttu-id="88acd-130">Nome dell'entità utente (UPN) dell'account</span><span class="sxs-lookup"><span data-stu-id="88acd-130">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="88acd-131">stringa</span><span class="sxs-lookup"><span data-stu-id="88acd-131">string</span></span> | <span data-ttu-id="88acd-132">ID di sicurezza (SID) dell'account</span><span class="sxs-lookup"><span data-stu-id="88acd-132">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="88acd-133">stringa</span><span class="sxs-lookup"><span data-stu-id="88acd-133">string</span></span> | <span data-ttu-id="88acd-134">Identificatore univoco per l'account in Azure AD</span><span class="sxs-lookup"><span data-stu-id="88acd-134">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="88acd-135">stringa</span><span class="sxs-lookup"><span data-stu-id="88acd-135">string</span></span> | <span data-ttu-id="88acd-136">Nome dell'account utente visualizzato nella rubrica.</span><span class="sxs-lookup"><span data-stu-id="88acd-136">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="88acd-137">In genere una combinazione di un nome o di un cognome, di un'iniziazione centrale e di un ultimo nome.</span><span class="sxs-lookup"><span data-stu-id="88acd-137">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="88acd-138">stringa</span><span class="sxs-lookup"><span data-stu-id="88acd-138">string</span></span> | <span data-ttu-id="88acd-139">Nome di dominio completo (FQDN) dell'endpoint</span><span class="sxs-lookup"><span data-stu-id="88acd-139">Fully qualified domain name (FQDN) of the endpoint</span></span> |
| `IPAddress` | <span data-ttu-id="88acd-140">stringa</span><span class="sxs-lookup"><span data-stu-id="88acd-140">string</span></span> | <span data-ttu-id="88acd-141">Indirizzo IP assegnato all'endpoint e utilizzato durante le comunicazioni di rete correlate</span><span class="sxs-lookup"><span data-stu-id="88acd-141">IP address assigned to the endpoint and used during related network communications</span></span> |
| `Location` | <span data-ttu-id="88acd-142">stringa</span><span class="sxs-lookup"><span data-stu-id="88acd-142">string</span></span> | <span data-ttu-id="88acd-143">Città, paese o altra località geografica associata all'evento</span><span class="sxs-lookup"><span data-stu-id="88acd-143">City, country, or other geographic location associated with the event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="88acd-144">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="88acd-144">Related topics</span></span>
- [<span data-ttu-id="88acd-145">Ricerca proattiva delle minacce</span><span class="sxs-lookup"><span data-stu-id="88acd-145">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="88acd-146">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="88acd-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="88acd-147">Utilizzare le query condivise</span><span class="sxs-lookup"><span data-stu-id="88acd-147">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="88acd-148">Ricerca delle minacce attraverso dispositivi e posta elettronica</span><span class="sxs-lookup"><span data-stu-id="88acd-148">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="88acd-149">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="88acd-149">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="88acd-150">Applicare le procedure consigliate per le query</span><span class="sxs-lookup"><span data-stu-id="88acd-150">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
