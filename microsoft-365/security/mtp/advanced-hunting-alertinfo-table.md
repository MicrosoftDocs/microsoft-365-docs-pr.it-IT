---
title: Tabella AlertInfo nello schema di ricerca avanzata
description: Informazioni sugli eventi di generazione degli avvisi nella tabella AlertInfo dello schema di ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca delle minacce informatiche, microsoft threat protection, Microsoft 365, mtp, m365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, AlertInfo, avviso, gravità, categoria, MITRE, ATT&CK, Microsoft Defender ATP, MDATP, Office 365 ATP, Microsoft Cloud App Security, MCAS e Azure ATP
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: ac1e28987a944a8f7786af4f10a85362f2f92a80
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929971"
---
# <a name="alertinfo"></a><span data-ttu-id="cbf38-104">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="cbf38-104">AlertInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="cbf38-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="cbf38-105">**Applies to:**</span></span>
- <span data-ttu-id="cbf38-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cbf38-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="cbf38-107">La tabella nello schema di ricerca avanzata contiene informazioni sugli avvisi di `AlertInfo` Microsoft Defender per Endpoint, Microsoft Defender per Office 365, Microsoft Cloud App Security e Microsoft Defender for Identity. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="cbf38-107">The `AlertInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about alerts from Microsoft  Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="cbf38-108">Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="cbf38-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="cbf38-109">Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="cbf38-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="cbf38-110">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="cbf38-110">Column name</span></span> | <span data-ttu-id="cbf38-111">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="cbf38-111">Data type</span></span> | <span data-ttu-id="cbf38-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cbf38-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="cbf38-113">datetime</span><span class="sxs-lookup"><span data-stu-id="cbf38-113">datetime</span></span> | <span data-ttu-id="cbf38-114">Data e ora di registrazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="cbf38-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="cbf38-115">stringa</span><span class="sxs-lookup"><span data-stu-id="cbf38-115">string</span></span> | <span data-ttu-id="cbf38-116">Identificatore univoco dell'avviso</span><span class="sxs-lookup"><span data-stu-id="cbf38-116">Unique identifier for the alert</span></span> |
| `Title` | <span data-ttu-id="cbf38-117">stringa</span><span class="sxs-lookup"><span data-stu-id="cbf38-117">string</span></span> | <span data-ttu-id="cbf38-118">Titolo dell'avviso</span><span class="sxs-lookup"><span data-stu-id="cbf38-118">Title of the alert</span></span> |
| `Category` | <span data-ttu-id="cbf38-119">stringa</span><span class="sxs-lookup"><span data-stu-id="cbf38-119">string</span></span> | <span data-ttu-id="cbf38-120">Tipo di indicatore di minaccia o di attività di violazione identificate dall'avviso</span><span class="sxs-lookup"><span data-stu-id="cbf38-120">Type of threat indicator or breach activity identified by the alert</span></span> |
| `Severity` | <span data-ttu-id="cbf38-121">stringa</span><span class="sxs-lookup"><span data-stu-id="cbf38-121">string</span></span> | <span data-ttu-id="cbf38-122">Indica il potenziale impatto (alto, medio o basso) dell'indicatore di minaccia o della violazione identificata dall'avviso</span><span class="sxs-lookup"><span data-stu-id="cbf38-122">Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="cbf38-123">stringa</span><span class="sxs-lookup"><span data-stu-id="cbf38-123">string</span></span> | <span data-ttu-id="cbf38-124">Prodotto o servizio che ha fornito le informazioni sull'avviso</span><span class="sxs-lookup"><span data-stu-id="cbf38-124">Product or service that provided the alert information</span></span> |
| `DetectionSource` | <span data-ttu-id="cbf38-125">stringa</span><span class="sxs-lookup"><span data-stu-id="cbf38-125">string</span></span> | <span data-ttu-id="cbf38-126">Tecnologia di rilevamento o sensore che ha identificato il componente o l'attività più importante</span><span class="sxs-lookup"><span data-stu-id="cbf38-126">Detection technology or sensor that identified the notable component or activity</span></span> |
| `AttackTechniques` | <span data-ttu-id="cbf38-127">stringa</span><span class="sxs-lookup"><span data-stu-id="cbf38-127">string</span></span> | <span data-ttu-id="cbf38-128">MiTRE ATT&tecniche CK associate all'attività che ha attivato l'avviso</span><span class="sxs-lookup"><span data-stu-id="cbf38-128">MITRE ATT&CK techniques associated with the activity that triggered the alert</span></span> |

## <a name="related-topics"></a><span data-ttu-id="cbf38-129">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="cbf38-129">Related topics</span></span>
- [<span data-ttu-id="cbf38-130">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="cbf38-130">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="cbf38-131">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="cbf38-131">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="cbf38-132">Utilizzare le query condivise</span><span class="sxs-lookup"><span data-stu-id="cbf38-132">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="cbf38-133">Cercare tra dispositivi, posta elettronica, app e identità</span><span class="sxs-lookup"><span data-stu-id="cbf38-133">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="cbf38-134">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="cbf38-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="cbf38-135">Applicare le procedure consigliate per le query</span><span class="sxs-lookup"><span data-stu-id="cbf38-135">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
