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
ms.openlocfilehash: 9f341705d8247183b7e8a5271231c82faf8b386a
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/24/2020
ms.locfileid: "42235095"
---
# <a name="alertevents"></a><span data-ttu-id="2a5a8-104">AlertEvents</span><span class="sxs-lookup"><span data-stu-id="2a5a8-104">AlertEvents</span></span>

<span data-ttu-id="2a5a8-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="2a5a8-105">**Applies to:**</span></span>
- <span data-ttu-id="2a5a8-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="2a5a8-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="2a5a8-107">La tabella `AlertEvents` nello schema per [Ricerca avanzata](advanced-hunting-overview.md) contiene informazioni sugli avvisi di Microsoft Defender Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="2a5a8-107">The `AlertEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about Microsoft Defender ATP alerts.</span></span> <span data-ttu-id="2a5a8-108">Utilizzare questo riferimento per creare query che forniscano informazioni da questa tabella.</span><span class="sxs-lookup"><span data-stu-id="2a5a8-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="2a5a8-109">Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="2a5a8-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="2a5a8-110">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="2a5a8-110">Column name</span></span> | <span data-ttu-id="2a5a8-111">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="2a5a8-111">Data type</span></span> | <span data-ttu-id="2a5a8-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2a5a8-112">Description</span></span> |
|-------------|-----------|-------------|
| `AlertId` | <span data-ttu-id="2a5a8-113">stringa</span><span class="sxs-lookup"><span data-stu-id="2a5a8-113">string</span></span> | <span data-ttu-id="2a5a8-114">Identificatore univoco dell'avviso</span><span class="sxs-lookup"><span data-stu-id="2a5a8-114">Unique identifier for the alert</span></span> |
| `Timestamp` | <span data-ttu-id="2a5a8-115">datetime</span><span class="sxs-lookup"><span data-stu-id="2a5a8-115">datetime</span></span> | <span data-ttu-id="2a5a8-116">Data e ora in cui è stato registrato l’evento</span><span class="sxs-lookup"><span data-stu-id="2a5a8-116">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="2a5a8-117">stringa</span><span class="sxs-lookup"><span data-stu-id="2a5a8-117">string</span></span> | <span data-ttu-id="2a5a8-118">Identificatore univoco per il computer nel servizio</span><span class="sxs-lookup"><span data-stu-id="2a5a8-118">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="2a5a8-119">stringa</span><span class="sxs-lookup"><span data-stu-id="2a5a8-119">string</span></span> | <span data-ttu-id="2a5a8-120">Nome di dominio completo (FQDN) del computer</span><span class="sxs-lookup"><span data-stu-id="2a5a8-120">Fully qualified domain name (FQDN) of the machine</span></span> |
| `Severity` | <span data-ttu-id="2a5a8-121">stringa</span><span class="sxs-lookup"><span data-stu-id="2a5a8-121">string</span></span> | <span data-ttu-id="2a5a8-122">Indica il potenziale impatto (alto, medio o basso) dell'indicatore di minaccia o della violazione identificata dall'avviso</span><span class="sxs-lookup"><span data-stu-id="2a5a8-122">Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert</span></span> |
| `Category` | <span data-ttu-id="2a5a8-123">stringa</span><span class="sxs-lookup"><span data-stu-id="2a5a8-123">string</span></span> | <span data-ttu-id="2a5a8-124">Tipo di indicatore di minaccia o di attività di violazione identificate dall'avviso</span><span class="sxs-lookup"><span data-stu-id="2a5a8-124">Type of threat indicator or breach activity identified by the alert</span></span> |
| `Title` | <span data-ttu-id="2a5a8-125">stringa</span><span class="sxs-lookup"><span data-stu-id="2a5a8-125">string</span></span> | <span data-ttu-id="2a5a8-126">Titolo dell'avviso</span><span class="sxs-lookup"><span data-stu-id="2a5a8-126">Title of the alert</span></span> |
| `FileName` | <span data-ttu-id="2a5a8-127">stringa</span><span class="sxs-lookup"><span data-stu-id="2a5a8-127">string</span></span> | <span data-ttu-id="2a5a8-128">Nome del file a cui è stata applicata l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="2a5a8-128">Name of the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="2a5a8-129">stringa</span><span class="sxs-lookup"><span data-stu-id="2a5a8-129">string</span></span> | <span data-ttu-id="2a5a8-130">SHA-1 del file a cui è stata applicata l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="2a5a8-130">SHA-1 of the file that the recorded action was applied to</span></span> |
| `RemoteUrl` | <span data-ttu-id="2a5a8-131">stringa</span><span class="sxs-lookup"><span data-stu-id="2a5a8-131">string</span></span> | <span data-ttu-id="2a5a8-132">URL o nome di dominio completo (FQDN) connesso a</span><span class="sxs-lookup"><span data-stu-id="2a5a8-132">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `RemoteIP` | <span data-ttu-id="2a5a8-133">stringa</span><span class="sxs-lookup"><span data-stu-id="2a5a8-133">string</span></span> | <span data-ttu-id="2a5a8-134">Indirizzo IP connesso a</span><span class="sxs-lookup"><span data-stu-id="2a5a8-134">IP address that was being connected to</span></span> |
| `ReportId` | <span data-ttu-id="2a5a8-135">long</span><span class="sxs-lookup"><span data-stu-id="2a5a8-135">long</span></span> | <span data-ttu-id="2a5a8-136">Identificatore di evento basato su un contatore ripetuto.</span><span class="sxs-lookup"><span data-stu-id="2a5a8-136">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="2a5a8-137">Per identificare gli eventi univoci, è necessario utilizzare questa colonna insieme alle colonne DeviceName e timestamp.</span><span class="sxs-lookup"><span data-stu-id="2a5a8-137">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `Table` | <span data-ttu-id="2a5a8-138">stringa</span><span class="sxs-lookup"><span data-stu-id="2a5a8-138">string</span></span> | <span data-ttu-id="2a5a8-139">Tabella che contiene i dettagli dell'evento</span><span class="sxs-lookup"><span data-stu-id="2a5a8-139">Table that contains the details of the event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="2a5a8-140">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="2a5a8-140">Related topics</span></span>
- [<span data-ttu-id="2a5a8-141">Ricerca proattiva delle minacce</span><span class="sxs-lookup"><span data-stu-id="2a5a8-141">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="2a5a8-142">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="2a5a8-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="2a5a8-143">Utilizzare le query condivise</span><span class="sxs-lookup"><span data-stu-id="2a5a8-143">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="2a5a8-144">Ricerca delle minacce attraverso dispositivi e email</span><span class="sxs-lookup"><span data-stu-id="2a5a8-144">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="2a5a8-145">Comprensione dello schema</span><span class="sxs-lookup"><span data-stu-id="2a5a8-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="2a5a8-146">Applicazione delle procedure consigliate per le query</span><span class="sxs-lookup"><span data-stu-id="2a5a8-146">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
