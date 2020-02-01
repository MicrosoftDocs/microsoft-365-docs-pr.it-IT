---
title: Tabella AlertEvents nello schema di ricerca avanzata
description: Informazioni sugli eventi di generazione di avvisi nella tabella AlertEvents dello schema per Ricerca avanzata
keywords: caccia avanzata, caccia alle minacce, Cyber-caccia alle minacce, Microsoft Threat Protection, Microsoft 365, MTP, M365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, alertevents, avviso, gravità, categoria
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
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 02a3f50019321f68390d3eb9b76576f4e6dfdd8a
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41602773"
---
# <a name="alertevents"></a><span data-ttu-id="82cef-104">AlertEvents</span><span class="sxs-lookup"><span data-stu-id="82cef-104">AlertEvents</span></span>

<span data-ttu-id="82cef-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="82cef-105">**Applies to:**</span></span>
- <span data-ttu-id="82cef-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="82cef-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="82cef-107">La tabella `AlertEvents` nello schema per [Ricerca avanzata](advanced-hunting-overview.md) contiene informazioni sugli avvisi di Microsoft Defender Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="82cef-107">The `AlertEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about Microsoft Defender ATP alerts.</span></span> <span data-ttu-id="82cef-108">Utilizzare questo riferimento per creare query che forniscano informazioni da questa tabella.</span><span class="sxs-lookup"><span data-stu-id="82cef-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="82cef-109">Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="82cef-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="82cef-110">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="82cef-110">Column name</span></span> | <span data-ttu-id="82cef-111">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="82cef-111">Data type</span></span> | <span data-ttu-id="82cef-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="82cef-112">Description</span></span> |
|-------------|-----------|-------------|
| `AlertId` | <span data-ttu-id="82cef-113">stringa</span><span class="sxs-lookup"><span data-stu-id="82cef-113">string</span></span> | <span data-ttu-id="82cef-114">Identificatore univoco dell'avviso</span><span class="sxs-lookup"><span data-stu-id="82cef-114">Unique identifier for the alert</span></span> |
| `Timestamp` | <span data-ttu-id="82cef-115">datetime</span><span class="sxs-lookup"><span data-stu-id="82cef-115">datetime</span></span> | <span data-ttu-id="82cef-116">Data e ora in cui è stato registrato l’evento</span><span class="sxs-lookup"><span data-stu-id="82cef-116">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="82cef-117">stringa</span><span class="sxs-lookup"><span data-stu-id="82cef-117">string</span></span> | <span data-ttu-id="82cef-118">Identificatore univoco per il computer nel servizio</span><span class="sxs-lookup"><span data-stu-id="82cef-118">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="82cef-119">stringa</span><span class="sxs-lookup"><span data-stu-id="82cef-119">string</span></span> | <span data-ttu-id="82cef-120">Nome di dominio completo (FQDN) del computer</span><span class="sxs-lookup"><span data-stu-id="82cef-120">Fully qualified domain name (FQDN) of the machine</span></span> |
| `Severity` | <span data-ttu-id="82cef-121">stringa</span><span class="sxs-lookup"><span data-stu-id="82cef-121">string</span></span> | <span data-ttu-id="82cef-122">Indica il potenziale impatto (alto, medio o basso) dell'indicatore di minaccia o della violazione identificata dall'avviso</span><span class="sxs-lookup"><span data-stu-id="82cef-122">Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert</span></span> |
| `Category` | <span data-ttu-id="82cef-123">stringa</span><span class="sxs-lookup"><span data-stu-id="82cef-123">string</span></span> | <span data-ttu-id="82cef-124">Tipo di indicatore di minaccia o di attività di violazione identificate dall'avviso</span><span class="sxs-lookup"><span data-stu-id="82cef-124">Type of threat indicator or breach activity identified by the alert</span></span> |
| `Title` | <span data-ttu-id="82cef-125">stringa</span><span class="sxs-lookup"><span data-stu-id="82cef-125">string</span></span> | <span data-ttu-id="82cef-126">Titolo dell'avviso</span><span class="sxs-lookup"><span data-stu-id="82cef-126">Title of the alert</span></span> |
| `FileName` | <span data-ttu-id="82cef-127">stringa</span><span class="sxs-lookup"><span data-stu-id="82cef-127">string</span></span> | <span data-ttu-id="82cef-128">Nome del file a cui è stata applicata l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="82cef-128">Name of the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="82cef-129">stringa</span><span class="sxs-lookup"><span data-stu-id="82cef-129">string</span></span> | <span data-ttu-id="82cef-130">SHA-1 del file a cui è stata applicata l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="82cef-130">SHA-1 of the file that the recorded action was applied to</span></span> |
| `RemoteUrl` | <span data-ttu-id="82cef-131">stringa</span><span class="sxs-lookup"><span data-stu-id="82cef-131">string</span></span> | <span data-ttu-id="82cef-132">URL o nome di dominio completo (FQDN) connesso a</span><span class="sxs-lookup"><span data-stu-id="82cef-132">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `RemoteIP` | <span data-ttu-id="82cef-133">stringa</span><span class="sxs-lookup"><span data-stu-id="82cef-133">string</span></span> | <span data-ttu-id="82cef-134">Indirizzo IP connesso a</span><span class="sxs-lookup"><span data-stu-id="82cef-134">IP address that was being connected to</span></span> |
| `ReportId` | <span data-ttu-id="82cef-135">long</span><span class="sxs-lookup"><span data-stu-id="82cef-135">long</span></span> | <span data-ttu-id="82cef-136">Identificatore di evento basato su un contatore ripetuto.</span><span class="sxs-lookup"><span data-stu-id="82cef-136">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="82cef-137">Per identificare gli eventi univoci, è necessario utilizzare questa colonna insieme alle colonne DeviceName e timestamp.</span><span class="sxs-lookup"><span data-stu-id="82cef-137">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `Table` | <span data-ttu-id="82cef-138">stringa</span><span class="sxs-lookup"><span data-stu-id="82cef-138">string</span></span> | <span data-ttu-id="82cef-139">Tabella che contiene i dettagli dell'evento</span><span class="sxs-lookup"><span data-stu-id="82cef-139">Table that contains the details of the event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="82cef-140">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="82cef-140">Related topics</span></span>
- [<span data-ttu-id="82cef-141">Ricerca proattiva delle minacce</span><span class="sxs-lookup"><span data-stu-id="82cef-141">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="82cef-142">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="82cef-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="82cef-143">Utilizzare le query condivise</span><span class="sxs-lookup"><span data-stu-id="82cef-143">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="82cef-144">Ricerca delle minacce attraverso dispositivi e email</span><span class="sxs-lookup"><span data-stu-id="82cef-144">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="82cef-145">Comprensione dello schema</span><span class="sxs-lookup"><span data-stu-id="82cef-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="82cef-146">Applicazione delle procedure consigliate per le query</span><span class="sxs-lookup"><span data-stu-id="82cef-146">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
