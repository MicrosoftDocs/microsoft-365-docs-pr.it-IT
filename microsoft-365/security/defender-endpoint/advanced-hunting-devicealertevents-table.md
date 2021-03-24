---
title: Tabella DeviceAlertEvents nello schema di ricerca avanzata
description: Informazioni sugli eventi di generazione degli avvisi nella tabella DeviceAlertEvents dello schema di ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, mdatp, microsoft defender atp, ricerca wdatp, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, DeviceAlertEvents, avviso, gravità, categoria
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 01/22/2020
ms.technology: mde
ms.openlocfilehash: c22e4b754f9d28156c3d26c567581572e59d718d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064389"
---
# <a name="devicealertevents"></a><span data-ttu-id="37b15-104">DeviceAlertEvents</span><span class="sxs-lookup"><span data-stu-id="37b15-104">DeviceAlertEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="37b15-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="37b15-105">**Applies to:**</span></span>
- [<span data-ttu-id="37b15-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="37b15-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)



><span data-ttu-id="37b15-107">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="37b15-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="37b15-108">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="37b15-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="37b15-109">La `DeviceAlertEvents` tabella nello schema di ricerca [avanzata](advanced-hunting-overview.md) contiene informazioni sugli avvisi in Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="37b15-109">The `DeviceAlertEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about alerts in Microsoft Defender Security Center.</span></span> <span data-ttu-id="37b15-110">Utilizzare questo riferimento per creare query che forniscano informazioni dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="37b15-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="37b15-111">Per informazioni sulle altre tabelle nello schema di ricerca avanzata, vedere la guida di riferimento [allo schema di ricerca avanzata.](advanced-hunting-schema-reference.md)</span><span class="sxs-lookup"><span data-stu-id="37b15-111">For information on other tables in the advanced hunting schema, see [the advanced hunting schema reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="37b15-112">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="37b15-112">Column name</span></span> | <span data-ttu-id="37b15-113">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="37b15-113">Data type</span></span> | <span data-ttu-id="37b15-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="37b15-114">Description</span></span> |
|-------------|-----------|-------------|
| `AlertId` | <span data-ttu-id="37b15-115">stringa</span><span class="sxs-lookup"><span data-stu-id="37b15-115">string</span></span> | <span data-ttu-id="37b15-116">Identificatore univoco dell'avviso</span><span class="sxs-lookup"><span data-stu-id="37b15-116">Unique identifier for the alert</span></span> |
| `Timestamp` | <span data-ttu-id="37b15-117">datetime</span><span class="sxs-lookup"><span data-stu-id="37b15-117">datetime</span></span> | <span data-ttu-id="37b15-118">Data e ora di registrazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="37b15-118">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="37b15-119">stringa</span><span class="sxs-lookup"><span data-stu-id="37b15-119">string</span></span> | <span data-ttu-id="37b15-120">Identificatore univoco del dispositivo nel servizio</span><span class="sxs-lookup"><span data-stu-id="37b15-120">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="37b15-121">stringa</span><span class="sxs-lookup"><span data-stu-id="37b15-121">string</span></span> | <span data-ttu-id="37b15-122">Nome di dominio completo (FQDN) del dispositivo</span><span class="sxs-lookup"><span data-stu-id="37b15-122">Fully qualified domain name (FQDN) of the device</span></span> |
| `Severity` | <span data-ttu-id="37b15-123">stringa</span><span class="sxs-lookup"><span data-stu-id="37b15-123">string</span></span> | <span data-ttu-id="37b15-124">Indica il potenziale impatto (alto, medio o basso) dell'indicatore di minaccia o della violazione identificata dall'avviso</span><span class="sxs-lookup"><span data-stu-id="37b15-124">Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert</span></span> |
| `Category` | <span data-ttu-id="37b15-125">stringa</span><span class="sxs-lookup"><span data-stu-id="37b15-125">string</span></span> | <span data-ttu-id="37b15-126">Tipo di indicatore di minaccia o di attività di violazione identificate dall'avviso</span><span class="sxs-lookup"><span data-stu-id="37b15-126">Type of threat indicator or breach activity identified by the alert</span></span> |
| `Title` | <span data-ttu-id="37b15-127">stringa</span><span class="sxs-lookup"><span data-stu-id="37b15-127">string</span></span> | <span data-ttu-id="37b15-128">Titolo dell'avviso</span><span class="sxs-lookup"><span data-stu-id="37b15-128">Title of the alert</span></span> |
| `FileName` | <span data-ttu-id="37b15-129">stringa</span><span class="sxs-lookup"><span data-stu-id="37b15-129">string</span></span> | <span data-ttu-id="37b15-130">Nome del file a cui è stata applicata l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="37b15-130">Name of the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="37b15-131">stringa</span><span class="sxs-lookup"><span data-stu-id="37b15-131">string</span></span> | <span data-ttu-id="37b15-132">SHA-1 del file a cui è stata applicata l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="37b15-132">SHA-1 of the file that the recorded action was applied to</span></span> |
| `RemoteUrl` | <span data-ttu-id="37b15-133">stringa</span><span class="sxs-lookup"><span data-stu-id="37b15-133">string</span></span> | <span data-ttu-id="37b15-134">URL o nome di dominio completo (FQDN) connesso a</span><span class="sxs-lookup"><span data-stu-id="37b15-134">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `RemoteIP` | <span data-ttu-id="37b15-135">stringa</span><span class="sxs-lookup"><span data-stu-id="37b15-135">string</span></span> | <span data-ttu-id="37b15-136">Indirizzo IP connesso a</span><span class="sxs-lookup"><span data-stu-id="37b15-136">IP address that was being connected to</span></span> |
| `AttackTechniques` | <span data-ttu-id="37b15-137">stringa</span><span class="sxs-lookup"><span data-stu-id="37b15-137">string</span></span> | <span data-ttu-id="37b15-138">MITRE ATT&tecniche CK associate all'attività che ha attivato l'avviso</span><span class="sxs-lookup"><span data-stu-id="37b15-138">MITRE ATT&CK techniques associated with the activity that triggered the alert</span></span> |
| `ReportId` | <span data-ttu-id="37b15-139">long</span><span class="sxs-lookup"><span data-stu-id="37b15-139">long</span></span> | <span data-ttu-id="37b15-140">Identificatore di evento basato su un contatore ripetuto.</span><span class="sxs-lookup"><span data-stu-id="37b15-140">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="37b15-141">Per identificare eventi univoci, è necessario utilizzare questa colonna insieme alle `DeviceName` colonne e `Timestamp`</span><span class="sxs-lookup"><span data-stu-id="37b15-141">To identify unique events, this column must be used in conjunction with the `DeviceName` and `Timestamp` columns</span></span> |
| `Table` | <span data-ttu-id="37b15-142">stringa</span><span class="sxs-lookup"><span data-stu-id="37b15-142">string</span></span> | <span data-ttu-id="37b15-143">Tabella che contiene i dettagli dell'evento</span><span class="sxs-lookup"><span data-stu-id="37b15-143">Table that contains the details of the event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="37b15-144">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="37b15-144">Related topics</span></span>
- [<span data-ttu-id="37b15-145">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="37b15-145">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="37b15-146">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="37b15-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="37b15-147">Comprensione dello schema</span><span class="sxs-lookup"><span data-stu-id="37b15-147">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
