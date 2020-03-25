---
title: Tabella AccountInfo nello schema di caccia avanzato
description: Informazioni sugli account utente nella tabella AccountInfo dello schema di caccia avanzato
keywords: caccia avanzata, caccia alle minacce, Cyber-caccia alle minacce, Microsoft Threat Protection, Microsoft 365, MTP, M365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, AlertInfo, avviso, entità, evidenza, file, indirizzo IP, dispositivo, computer, utente, account
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
ms.openlocfilehash: 9e4503ab297c7a584a548faa36ca6102c1b8dda6
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929529"
---
# <a name="accountinfo"></a><span data-ttu-id="761a9-104">AccountInfo</span><span class="sxs-lookup"><span data-stu-id="761a9-104">AccountInfo</span></span>

<span data-ttu-id="761a9-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="761a9-105">**Applies to:**</span></span>
- <span data-ttu-id="761a9-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="761a9-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="761a9-107">La `AccountInfo` tabella nello schema di [ricerca avanzata](advanced-hunting-overview.md) contiene informazioni sugli account utente ottenuti da vari servizi, tra cui Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="761a9-107">The `AccountInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about user accounts obtained from various services, including Azure Active Directory.</span></span> <span data-ttu-id="761a9-108">Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="761a9-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="761a9-109">Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="761a9-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="761a9-110">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="761a9-110">Column name</span></span> | <span data-ttu-id="761a9-111">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="761a9-111">Data type</span></span> | <span data-ttu-id="761a9-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="761a9-112">Description</span></span> |
|-------------|-----------|-------------|
| `AccountObjectId` | <span data-ttu-id="761a9-113">stringa</span><span class="sxs-lookup"><span data-stu-id="761a9-113">string</span></span> | <span data-ttu-id="761a9-114">Identificatore univoco per l'account in Azure AD</span><span class="sxs-lookup"><span data-stu-id="761a9-114">Unique identifier for the account in Azure AD</span></span> |
| `AccountUpn` | <span data-ttu-id="761a9-115">stringa</span><span class="sxs-lookup"><span data-stu-id="761a9-115">string</span></span> | <span data-ttu-id="761a9-116">Nome dell'entità utente (UPN) dell'account</span><span class="sxs-lookup"><span data-stu-id="761a9-116">User principal name (UPN) of the account</span></span> |
| `OnPremSid` | <span data-ttu-id="761a9-117">stringa</span><span class="sxs-lookup"><span data-stu-id="761a9-117">string</span></span> | <span data-ttu-id="761a9-118">ID di sicurezza locale (SID) dell'account</span><span class="sxs-lookup"><span data-stu-id="761a9-118">On-premises security identifier (SID) of the account</span></span> |
| `CloudSid` | <span data-ttu-id="761a9-119">stringa</span><span class="sxs-lookup"><span data-stu-id="761a9-119">string</span></span> | <span data-ttu-id="761a9-120">Identificatore di sicurezza cloud dell'account</span><span class="sxs-lookup"><span data-stu-id="761a9-120">Cloud security identifier of the account</span></span> |
| `GivenName` | <span data-ttu-id="761a9-121">stringa</span><span class="sxs-lookup"><span data-stu-id="761a9-121">string</span></span> | <span data-ttu-id="761a9-122">Nome o nome specificato dell'utente dell'account</span><span class="sxs-lookup"><span data-stu-id="761a9-122">Given name or first name of the account user</span></span> |
| `Surname` | <span data-ttu-id="761a9-123">stringa</span><span class="sxs-lookup"><span data-stu-id="761a9-123">string</span></span> | <span data-ttu-id="761a9-124">Cognome, nome della famiglia o cognome dell'utente dell'account</span><span class="sxs-lookup"><span data-stu-id="761a9-124">Surname, family name, or last name of the account user</span></span> |
| `AccountDisplayName` | <span data-ttu-id="761a9-125">stringa</span><span class="sxs-lookup"><span data-stu-id="761a9-125">string</span></span> | <span data-ttu-id="761a9-126">Nome dell'account utente visualizzato nella rubrica.</span><span class="sxs-lookup"><span data-stu-id="761a9-126">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="761a9-127">In genere una combinazione di un nome o di un cognome, di un'iniziazione centrale e di un ultimo nome.</span><span class="sxs-lookup"><span data-stu-id="761a9-127">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `Department` | <span data-ttu-id="761a9-128">stringa</span><span class="sxs-lookup"><span data-stu-id="761a9-128">string</span></span> | <span data-ttu-id="761a9-129">Nome del reparto a cui appartiene l'utente dell'account</span><span class="sxs-lookup"><span data-stu-id="761a9-129">Name of the department that the account user belongs to</span></span> |
| `JobTitle` | <span data-ttu-id="761a9-130">stringa</span><span class="sxs-lookup"><span data-stu-id="761a9-130">string</span></span> | <span data-ttu-id="761a9-131">Titolo del processo dell'utente dell'account</span><span class="sxs-lookup"><span data-stu-id="761a9-131">Job title of the account user</span></span> |
| `AccountName` | <span data-ttu-id="761a9-132">stringa</span><span class="sxs-lookup"><span data-stu-id="761a9-132">string</span></span> | <span data-ttu-id="761a9-133">Nome utente dell'account</span><span class="sxs-lookup"><span data-stu-id="761a9-133">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="761a9-134">stringa</span><span class="sxs-lookup"><span data-stu-id="761a9-134">string</span></span> | <span data-ttu-id="761a9-135">Dominio dell'account</span><span class="sxs-lookup"><span data-stu-id="761a9-135">Domain of the account</span></span> |
| `EmailAddress` | <span data-ttu-id="761a9-136">stringa</span><span class="sxs-lookup"><span data-stu-id="761a9-136">string</span></span> | <span data-ttu-id="761a9-137">Indirizzo SMTP dell'account</span><span class="sxs-lookup"><span data-stu-id="761a9-137">SMTP address of the account</span></span> |
| `SipProxyAddress` | <span data-ttu-id="761a9-138">stringa</span><span class="sxs-lookup"><span data-stu-id="761a9-138">string</span></span> | <span data-ttu-id="761a9-139">Indirizzo SIP (Voice of over IP (VOIP) Session Initiation Protocol of the account</span><span class="sxs-lookup"><span data-stu-id="761a9-139">Voice of over IP (VOIP) session initiation protocol (SIP) address of the account</span></span> |
| `City` | <span data-ttu-id="761a9-140">stringa</span><span class="sxs-lookup"><span data-stu-id="761a9-140">string</span></span> | <span data-ttu-id="761a9-141">Città in cui si trova l'utente dell'account</span><span class="sxs-lookup"><span data-stu-id="761a9-141">City where the account user is located</span></span> |
| `Country` | <span data-ttu-id="761a9-142">stringa</span><span class="sxs-lookup"><span data-stu-id="761a9-142">string</span></span> | <span data-ttu-id="761a9-143">Paese/area geografica in cui si trova l'account utente</span><span class="sxs-lookup"><span data-stu-id="761a9-143">Country/Region where the account user is located</span></span> |
| `IsAccountEnabled` | <span data-ttu-id="761a9-144">boolean</span><span class="sxs-lookup"><span data-stu-id="761a9-144">boolean</span></span> | <span data-ttu-id="761a9-145">Indica se l'account è abilitato o meno.</span><span class="sxs-lookup"><span data-stu-id="761a9-145">Indicates whether the account is enabled or not</span></span> |

## <a name="related-topics"></a><span data-ttu-id="761a9-146">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="761a9-146">Related topics</span></span>
- [<span data-ttu-id="761a9-147">Ricerca proattiva delle minacce</span><span class="sxs-lookup"><span data-stu-id="761a9-147">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="761a9-148">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="761a9-148">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="761a9-149">Utilizzare le query condivise</span><span class="sxs-lookup"><span data-stu-id="761a9-149">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="761a9-150">Ricerca delle minacce attraverso dispositivi e posta elettronica</span><span class="sxs-lookup"><span data-stu-id="761a9-150">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="761a9-151">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="761a9-151">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="761a9-152">Applicare le procedure consigliate per le query</span><span class="sxs-lookup"><span data-stu-id="761a9-152">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
