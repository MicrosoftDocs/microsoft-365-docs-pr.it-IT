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
ms.openlocfilehash: da3b331d4f607aa0961e275db9444aadbec4fcf2
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899340"
---
# <a name="appfileevents"></a><span data-ttu-id="7398f-104">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="7398f-104">AppFileEvents</span></span>

<span data-ttu-id="7398f-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="7398f-105">**Applies to:**</span></span>
- <span data-ttu-id="7398f-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="7398f-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="7398f-107">La `AppFileEvents` tabella nello schema di [ricerca avanzata](advanced-hunting-overview.md) contiene informazioni sulle attività correlate ai file nelle app e nei servizi cloud monitorati da Microsoft cloud app Security.</span><span class="sxs-lookup"><span data-stu-id="7398f-107">The `AppFileEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file-related activities in cloud apps and services monitored by Microsoft Cloud App Security.</span></span> <span data-ttu-id="7398f-108">Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="7398f-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="7398f-109">Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="7398f-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="7398f-110">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="7398f-110">Column name</span></span> | <span data-ttu-id="7398f-111">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="7398f-111">Data type</span></span> | <span data-ttu-id="7398f-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7398f-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="7398f-113">datetime</span><span class="sxs-lookup"><span data-stu-id="7398f-113">datetime</span></span> | <span data-ttu-id="7398f-114">Data e ora di registrazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="7398f-114">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="7398f-115">stringa</span><span class="sxs-lookup"><span data-stu-id="7398f-115">string</span></span> | <span data-ttu-id="7398f-116">Tipo di attività che ha attivato l'evento</span><span class="sxs-lookup"><span data-stu-id="7398f-116">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="7398f-117">stringa</span><span class="sxs-lookup"><span data-stu-id="7398f-117">string</span></span> | <span data-ttu-id="7398f-118">Applicazione in cui è stata eseguita l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="7398f-118">Application that performed the recorded action</span></span> |
| `FileName` | <span data-ttu-id="7398f-119">stringa</span><span class="sxs-lookup"><span data-stu-id="7398f-119">string</span></span> | <span data-ttu-id="7398f-120">Nome del file a cui è stata applicata l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="7398f-120">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="7398f-121">stringa</span><span class="sxs-lookup"><span data-stu-id="7398f-121">string</span></span> | <span data-ttu-id="7398f-122">Cartella contenente il file a cui è stata applicata l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="7398f-122">Folder containing the file that the recorded action was applied to</span></span> |
| `PreviousFileName` | <span data-ttu-id="7398f-123">stringa</span><span class="sxs-lookup"><span data-stu-id="7398f-123">string</span></span> | <span data-ttu-id="7398f-124">Nome originale del file che è stato rinominato come risultato dell'azione</span><span class="sxs-lookup"><span data-stu-id="7398f-124">Original name of the file that was renamed as a result of the action</span></span> |
| `AccountName` | <span data-ttu-id="7398f-125">stringa</span><span class="sxs-lookup"><span data-stu-id="7398f-125">string</span></span> | <span data-ttu-id="7398f-126">Nome utente dell'account</span><span class="sxs-lookup"><span data-stu-id="7398f-126">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="7398f-127">stringa</span><span class="sxs-lookup"><span data-stu-id="7398f-127">string</span></span> | <span data-ttu-id="7398f-128">Dominio dell'account</span><span class="sxs-lookup"><span data-stu-id="7398f-128">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="7398f-129">stringa</span><span class="sxs-lookup"><span data-stu-id="7398f-129">string</span></span> | <span data-ttu-id="7398f-130">Nome dell'entità utente (UPN) dell'account</span><span class="sxs-lookup"><span data-stu-id="7398f-130">User principal name (UPN) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="7398f-131">stringa</span><span class="sxs-lookup"><span data-stu-id="7398f-131">string</span></span> | <span data-ttu-id="7398f-132">Identificatore univoco per l'account in Azure AD</span><span class="sxs-lookup"><span data-stu-id="7398f-132">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="7398f-133">stringa</span><span class="sxs-lookup"><span data-stu-id="7398f-133">string</span></span> | <span data-ttu-id="7398f-134">Nome dell'account utente visualizzato nella rubrica.</span><span class="sxs-lookup"><span data-stu-id="7398f-134">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="7398f-135">In genere una combinazione di un nome o di un cognome, di un'iniziazione centrale e di un ultimo nome.</span><span class="sxs-lookup"><span data-stu-id="7398f-135">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `IPAddress` | <span data-ttu-id="7398f-136">stringa</span><span class="sxs-lookup"><span data-stu-id="7398f-136">string</span></span> | <span data-ttu-id="7398f-137">Indirizzo IP assegnato all'endpoint e utilizzato durante le comunicazioni di rete correlate</span><span class="sxs-lookup"><span data-stu-id="7398f-137">IP address assigned to the endpoint and used during related network communications</span></span> |
| `Location` | <span data-ttu-id="7398f-138">stringa</span><span class="sxs-lookup"><span data-stu-id="7398f-138">string</span></span> | <span data-ttu-id="7398f-139">Città, paese o altra località geografica associata all'evento</span><span class="sxs-lookup"><span data-stu-id="7398f-139">City, country, or other geographic location associated with the event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="7398f-140">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="7398f-140">Related topics</span></span>
- [<span data-ttu-id="7398f-141">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="7398f-141">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="7398f-142">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="7398f-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="7398f-143">Utilizzare le query condivise</span><span class="sxs-lookup"><span data-stu-id="7398f-143">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="7398f-144">Ricerca delle minacce attraverso dispositivi e posta elettronica</span><span class="sxs-lookup"><span data-stu-id="7398f-144">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="7398f-145">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="7398f-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="7398f-146">Applicare le procedure consigliate per le query</span><span class="sxs-lookup"><span data-stu-id="7398f-146">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
