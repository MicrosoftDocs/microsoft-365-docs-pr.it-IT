---
title: Tabella IdentityInfo nello schema di ricerca avanzata
description: Informazioni sulle informazioni sull'account utente nella tabella IdentityInfo dello schema di ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, Microsoft 365 Defender, Microsoft 365, m365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, AccountInfo, IdentityInfo, account
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: ce1a3d5153d324d008d2d46048838351eb7bc047
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935822"
---
# <a name="identityinfo"></a><span data-ttu-id="a52e5-104">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="a52e5-104">IdentityInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="a52e5-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="a52e5-105">**Applies to:**</span></span>
- <span data-ttu-id="a52e5-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a52e5-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="a52e5-107">La `IdentityInfo` tabella nello schema di ricerca [avanzata](advanced-hunting-overview.md) contiene informazioni sugli account utente ottenuti da vari servizi, tra cui Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a52e5-107">The `IdentityInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about user accounts obtained from various services, including Azure Active Directory.</span></span> <span data-ttu-id="a52e5-108">Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="a52e5-108">Use this reference to construct queries that return information from this table.</span></span>

>[!NOTE]
><span data-ttu-id="a52e5-109">Questa tabella è stata rinominata da `AccountInfo` .</span><span class="sxs-lookup"><span data-stu-id="a52e5-109">This table was renamed from `AccountInfo`.</span></span> <span data-ttu-id="a52e5-110">Durante le ridenominazioni, tutte le query salvate nel portale vengono aggiornate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="a52e5-110">During renames, all queries saved in the portal are automatically updated.</span></span> <span data-ttu-id="a52e5-111">Controllare le query salvate altrove.</span><span class="sxs-lookup"><span data-stu-id="a52e5-111">Check queries you have saved elsewhere.</span></span>

<span data-ttu-id="a52e5-112">Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="a52e5-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="a52e5-113">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="a52e5-113">Column name</span></span> | <span data-ttu-id="a52e5-114">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="a52e5-114">Data type</span></span> | <span data-ttu-id="a52e5-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a52e5-115">Description</span></span> |
|-------------|-----------|-------------|
| `AccountObjectId` | <span data-ttu-id="a52e5-116">stringa</span><span class="sxs-lookup"><span data-stu-id="a52e5-116">string</span></span> | <span data-ttu-id="a52e5-117">Identificatore univoco dell'account in Azure AD</span><span class="sxs-lookup"><span data-stu-id="a52e5-117">Unique identifier for the account in Azure AD</span></span> |
| `AccountUpn` | <span data-ttu-id="a52e5-118">stringa</span><span class="sxs-lookup"><span data-stu-id="a52e5-118">string</span></span> | <span data-ttu-id="a52e5-119">Nome dell'entità utente (UPN) dell'account</span><span class="sxs-lookup"><span data-stu-id="a52e5-119">User principal name (UPN) of the account</span></span> |
| `OnPremSid` | <span data-ttu-id="a52e5-120">stringa</span><span class="sxs-lookup"><span data-stu-id="a52e5-120">string</span></span> | <span data-ttu-id="a52e5-121">Identificatore di sicurezza (SID) locale dell'account</span><span class="sxs-lookup"><span data-stu-id="a52e5-121">On-premises security identifier (SID) of the account</span></span> |
| `CloudSid` | <span data-ttu-id="a52e5-122">stringa</span><span class="sxs-lookup"><span data-stu-id="a52e5-122">string</span></span> | <span data-ttu-id="a52e5-123">Identificatore di sicurezza cloud dell'account</span><span class="sxs-lookup"><span data-stu-id="a52e5-123">Cloud security identifier of the account</span></span> |
| `GivenName` | <span data-ttu-id="a52e5-124">stringa</span><span class="sxs-lookup"><span data-stu-id="a52e5-124">string</span></span> | <span data-ttu-id="a52e5-125">Nome o nome specificato dell'utente dell'account</span><span class="sxs-lookup"><span data-stu-id="a52e5-125">Given name or first name of the account user</span></span> |
| `Surname` | <span data-ttu-id="a52e5-126">stringa</span><span class="sxs-lookup"><span data-stu-id="a52e5-126">string</span></span> | <span data-ttu-id="a52e5-127">Cognome, cognome o cognome dell'utente dell'account</span><span class="sxs-lookup"><span data-stu-id="a52e5-127">Surname, family name, or last name of the account user</span></span> |
| `AccountDisplayName` | <span data-ttu-id="a52e5-128">stringa</span><span class="sxs-lookup"><span data-stu-id="a52e5-128">string</span></span> | <span data-ttu-id="a52e5-129">Nome dell'utente dell'account visualizzato nella rubrica.</span><span class="sxs-lookup"><span data-stu-id="a52e5-129">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="a52e5-130">In genere una combinazione di un nome o di un dato nome, un'iniziazione intermedia e un cognome o un cognome.</span><span class="sxs-lookup"><span data-stu-id="a52e5-130">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `Department` | <span data-ttu-id="a52e5-131">stringa</span><span class="sxs-lookup"><span data-stu-id="a52e5-131">string</span></span> | <span data-ttu-id="a52e5-132">Nome del reparto a cui appartiene l'utente dell'account</span><span class="sxs-lookup"><span data-stu-id="a52e5-132">Name of the department that the account user belongs to</span></span> |
| `JobTitle` | <span data-ttu-id="a52e5-133">stringa</span><span class="sxs-lookup"><span data-stu-id="a52e5-133">string</span></span> | <span data-ttu-id="a52e5-134">Posizione dell'utente dell'account</span><span class="sxs-lookup"><span data-stu-id="a52e5-134">Job title of the account user</span></span> |
| `AccountName` | <span data-ttu-id="a52e5-135">stringa</span><span class="sxs-lookup"><span data-stu-id="a52e5-135">string</span></span> | <span data-ttu-id="a52e5-136">Nome utente dell'account</span><span class="sxs-lookup"><span data-stu-id="a52e5-136">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="a52e5-137">stringa</span><span class="sxs-lookup"><span data-stu-id="a52e5-137">string</span></span> | <span data-ttu-id="a52e5-138">Dominio dell'account</span><span class="sxs-lookup"><span data-stu-id="a52e5-138">Domain of the account</span></span> |
| `EmailAddress` | <span data-ttu-id="a52e5-139">stringa</span><span class="sxs-lookup"><span data-stu-id="a52e5-139">string</span></span> | <span data-ttu-id="a52e5-140">Indirizzo SMTP dell'account</span><span class="sxs-lookup"><span data-stu-id="a52e5-140">SMTP address of the account</span></span> |
| `SipProxyAddress` | <span data-ttu-id="a52e5-141">stringa</span><span class="sxs-lookup"><span data-stu-id="a52e5-141">string</span></span> | <span data-ttu-id="a52e5-142">Indirizzo SIP (Voice over IP) dell'account</span><span class="sxs-lookup"><span data-stu-id="a52e5-142">Voice over IP (VOIP) session initiation protocol (SIP) address of the account</span></span> |
| `City` | <span data-ttu-id="a52e5-143">stringa</span><span class="sxs-lookup"><span data-stu-id="a52e5-143">string</span></span> | <span data-ttu-id="a52e5-144">Città in cui si trova l'utente dell'account</span><span class="sxs-lookup"><span data-stu-id="a52e5-144">City where the account user is located</span></span> |
| `Country` | <span data-ttu-id="a52e5-145">stringa</span><span class="sxs-lookup"><span data-stu-id="a52e5-145">string</span></span> | <span data-ttu-id="a52e5-146">Paese/area geografica in cui si trova l'utente dell'account</span><span class="sxs-lookup"><span data-stu-id="a52e5-146">Country/Region where the account user is located</span></span> |
| `IsAccountEnabled` | <span data-ttu-id="a52e5-147">boolean</span><span class="sxs-lookup"><span data-stu-id="a52e5-147">boolean</span></span> | <span data-ttu-id="a52e5-148">Indica se l'account è abilitato o meno</span><span class="sxs-lookup"><span data-stu-id="a52e5-148">Indicates whether the account is enabled or not</span></span> |

## <a name="related-topics"></a><span data-ttu-id="a52e5-149">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="a52e5-149">Related topics</span></span>
- [<span data-ttu-id="a52e5-150">Panoramica della rilevazione avanzata</span><span class="sxs-lookup"><span data-stu-id="a52e5-150">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="a52e5-151">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="a52e5-151">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="a52e5-152">Utilizzare le query condivise</span><span class="sxs-lookup"><span data-stu-id="a52e5-152">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="a52e5-153">Cercare tra dispositivi, posta elettronica, app e identità</span><span class="sxs-lookup"><span data-stu-id="a52e5-153">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="a52e5-154">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="a52e5-154">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="a52e5-155">Applicare le procedure consigliate per le query</span><span class="sxs-lookup"><span data-stu-id="a52e5-155">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
