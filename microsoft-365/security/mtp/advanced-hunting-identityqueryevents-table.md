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
ms.openlocfilehash: bec7f13d49e2ccf4e3a9121d5e5a2fecd1b10aa2
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899114"
---
# <a name="identityqueryevents"></a><span data-ttu-id="46864-104">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="46864-104">IdentityQueryEvents</span></span>

<span data-ttu-id="46864-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="46864-105">**Applies to:**</span></span>
- <span data-ttu-id="46864-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="46864-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="46864-107">La `IdentityQueryEvents` tabella nello schema di [ricerca avanzata](advanced-hunting-overview.md) contiene informazioni sulle query eseguite su oggetti di Active Directory, ad esempio utenti, gruppi, dispositivi e domini.</span><span class="sxs-lookup"><span data-stu-id="46864-107">The `IdentityQueryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about queries performed against Active Directory objects, such as users, groups, devices, and domains.</span></span> <span data-ttu-id="46864-108">Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="46864-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="46864-109">Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="46864-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="46864-110">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="46864-110">Column name</span></span> | <span data-ttu-id="46864-111">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="46864-111">Data type</span></span> | <span data-ttu-id="46864-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="46864-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="46864-113">datetime</span><span class="sxs-lookup"><span data-stu-id="46864-113">datetime</span></span> | <span data-ttu-id="46864-114">Data e ora di registrazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="46864-114">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="46864-115">stringa</span><span class="sxs-lookup"><span data-stu-id="46864-115">string</span></span> | <span data-ttu-id="46864-116">Tipo di attività che ha attivato l'evento</span><span class="sxs-lookup"><span data-stu-id="46864-116">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="46864-117">stringa</span><span class="sxs-lookup"><span data-stu-id="46864-117">string</span></span> | <span data-ttu-id="46864-118">Applicazione in cui è stata eseguita l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="46864-118">Application that performed the recorded action</span></span> |
| `Query` | <span data-ttu-id="46864-119">stringa</span><span class="sxs-lookup"><span data-stu-id="46864-119">string</span></span> | <span data-ttu-id="46864-120">Tipo di query: QueryGroup, QueryUser o EnumerateUsers</span><span class="sxs-lookup"><span data-stu-id="46864-120">Type of query: QueryGroup, QueryUser, or EnumerateUsers</span></span> |
| `QueryObject` | <span data-ttu-id="46864-121">stringa</span><span class="sxs-lookup"><span data-stu-id="46864-121">string</span></span> | <span data-ttu-id="46864-122">Nome dell'utente, del gruppo, del dispositivo, del dominio o di qualsiasi altro tipo di entità su cui viene eseguita la query</span><span class="sxs-lookup"><span data-stu-id="46864-122">Name of the user, group, device, domain, or any other entity type being queried</span></span> |
| `Protocol` | <span data-ttu-id="46864-123">stringa</span><span class="sxs-lookup"><span data-stu-id="46864-123">string</span></span> | <span data-ttu-id="46864-124">Protocollo utilizzato durante la comunicazione</span><span class="sxs-lookup"><span data-stu-id="46864-124">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="46864-125">stringa</span><span class="sxs-lookup"><span data-stu-id="46864-125">string</span></span> | <span data-ttu-id="46864-126">Nome utente dell'account</span><span class="sxs-lookup"><span data-stu-id="46864-126">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="46864-127">stringa</span><span class="sxs-lookup"><span data-stu-id="46864-127">string</span></span> | <span data-ttu-id="46864-128">Dominio dell'account</span><span class="sxs-lookup"><span data-stu-id="46864-128">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="46864-129">stringa</span><span class="sxs-lookup"><span data-stu-id="46864-129">string</span></span> | <span data-ttu-id="46864-130">Nome dell'entità utente (UPN) dell'account</span><span class="sxs-lookup"><span data-stu-id="46864-130">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="46864-131">stringa</span><span class="sxs-lookup"><span data-stu-id="46864-131">string</span></span> | <span data-ttu-id="46864-132">ID di sicurezza (SID) dell'account</span><span class="sxs-lookup"><span data-stu-id="46864-132">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="46864-133">stringa</span><span class="sxs-lookup"><span data-stu-id="46864-133">string</span></span> | <span data-ttu-id="46864-134">Identificatore univoco per l'account in Azure AD</span><span class="sxs-lookup"><span data-stu-id="46864-134">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="46864-135">stringa</span><span class="sxs-lookup"><span data-stu-id="46864-135">string</span></span> | <span data-ttu-id="46864-136">Nome dell'account utente visualizzato nella rubrica.</span><span class="sxs-lookup"><span data-stu-id="46864-136">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="46864-137">In genere una combinazione di un nome o di un cognome, di un'iniziazione centrale e di un ultimo nome.</span><span class="sxs-lookup"><span data-stu-id="46864-137">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="46864-138">stringa</span><span class="sxs-lookup"><span data-stu-id="46864-138">string</span></span> | <span data-ttu-id="46864-139">Nome di dominio completo (FQDN) dell'endpoint</span><span class="sxs-lookup"><span data-stu-id="46864-139">Fully qualified domain name (FQDN) of the endpoint</span></span> |
| `IPAddress` | <span data-ttu-id="46864-140">stringa</span><span class="sxs-lookup"><span data-stu-id="46864-140">string</span></span> | <span data-ttu-id="46864-141">Indirizzo IP assegnato all'endpoint e utilizzato durante le comunicazioni di rete correlate</span><span class="sxs-lookup"><span data-stu-id="46864-141">IP address assigned to the endpoint and used during related network communications</span></span> |
| `Location` | <span data-ttu-id="46864-142">stringa</span><span class="sxs-lookup"><span data-stu-id="46864-142">string</span></span> | <span data-ttu-id="46864-143">Città, paese o altra località geografica associata all'evento</span><span class="sxs-lookup"><span data-stu-id="46864-143">City, country, or other geographic location associated with the event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="46864-144">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="46864-144">Related topics</span></span>
- [<span data-ttu-id="46864-145">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="46864-145">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="46864-146">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="46864-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="46864-147">Utilizzare le query condivise</span><span class="sxs-lookup"><span data-stu-id="46864-147">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="46864-148">Ricerca delle minacce attraverso dispositivi e posta elettronica</span><span class="sxs-lookup"><span data-stu-id="46864-148">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="46864-149">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="46864-149">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="46864-150">Applicare le procedure consigliate per le query</span><span class="sxs-lookup"><span data-stu-id="46864-150">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
