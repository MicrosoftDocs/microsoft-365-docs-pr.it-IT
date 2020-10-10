---
title: Tabella AlertInfo nello schema di caccia avanzato
description: Informazioni sugli eventi di generazione degli avvisi nella tabella AlertInfo dello schema di caccia avanzato
keywords: caccia avanzata, caccia alle minacce, Cyber-caccia alle minacce, Microsoft Threat Protection, Microsoft 365, MTP, M365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, AlertInfo, avviso, gravità, categoria, MITRE, ATT&CK, Microsoft Defender ATP, MDATP, Office 365 ATP, Microsoft cloud app Security, MCAS
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
ms.collection:
- M365-security-compliance
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: ca89630a940ea56fd7ad968d1cba8a50dd9f4fa0
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/09/2020
ms.locfileid: "48413187"
---
# <a name="alertinfo"></a><span data-ttu-id="20661-104">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="20661-104">AlertInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="20661-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="20661-105">**Applies to:**</span></span>
- <span data-ttu-id="20661-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="20661-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="20661-107">La `AlertInfo` tabella nello schema di [ricerca avanzata](advanced-hunting-overview.md) contiene informazioni sugli avvisi di Microsoft Defender atp, Office 365 ATP, Microsoft cloud app Security e Azure ATP.</span><span class="sxs-lookup"><span data-stu-id="20661-107">The `AlertInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about alerts from Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="20661-108">Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="20661-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="20661-109">Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="20661-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="20661-110">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="20661-110">Column name</span></span> | <span data-ttu-id="20661-111">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="20661-111">Data type</span></span> | <span data-ttu-id="20661-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="20661-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="20661-113">datetime</span><span class="sxs-lookup"><span data-stu-id="20661-113">datetime</span></span> | <span data-ttu-id="20661-114">Data e ora di registrazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="20661-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="20661-115">stringa</span><span class="sxs-lookup"><span data-stu-id="20661-115">string</span></span> | <span data-ttu-id="20661-116">Identificatore univoco dell'avviso</span><span class="sxs-lookup"><span data-stu-id="20661-116">Unique identifier for the alert</span></span> |
| `Title` | <span data-ttu-id="20661-117">stringa</span><span class="sxs-lookup"><span data-stu-id="20661-117">string</span></span> | <span data-ttu-id="20661-118">Titolo dell'avviso</span><span class="sxs-lookup"><span data-stu-id="20661-118">Title of the alert</span></span> |
| `Category` | <span data-ttu-id="20661-119">stringa</span><span class="sxs-lookup"><span data-stu-id="20661-119">string</span></span> | <span data-ttu-id="20661-120">Tipo di indicatore di minaccia o di attività di violazione identificate dall'avviso</span><span class="sxs-lookup"><span data-stu-id="20661-120">Type of threat indicator or breach activity identified by the alert</span></span> |
| `Severity` | <span data-ttu-id="20661-121">stringa</span><span class="sxs-lookup"><span data-stu-id="20661-121">string</span></span> | <span data-ttu-id="20661-122">Indica il potenziale impatto (alto, medio o basso) dell'indicatore di minaccia o della violazione identificata dall'avviso</span><span class="sxs-lookup"><span data-stu-id="20661-122">Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="20661-123">stringa</span><span class="sxs-lookup"><span data-stu-id="20661-123">string</span></span> | <span data-ttu-id="20661-124">Prodotto o servizio che ha fornito le informazioni sugli avvisi</span><span class="sxs-lookup"><span data-stu-id="20661-124">Product or service that provided the alert information</span></span> |
| `DetectionSource` | <span data-ttu-id="20661-125">stringa</span><span class="sxs-lookup"><span data-stu-id="20661-125">string</span></span> | <span data-ttu-id="20661-126">Tecnologia di rilevamento o sensore che ha identificato la componente o l'attività importante</span><span class="sxs-lookup"><span data-stu-id="20661-126">Detection technology or sensor that identified the notable component or activity</span></span> |
| `AttackTechniques` | <span data-ttu-id="20661-127">stringa</span><span class="sxs-lookup"><span data-stu-id="20661-127">string</span></span> | <span data-ttu-id="20661-128">Le tecniche di MITRE ATT&CK associate all'attività che ha attivato l'avviso</span><span class="sxs-lookup"><span data-stu-id="20661-128">MITRE ATT&CK techniques associated with the activity that triggered the alert</span></span> |

## <a name="related-topics"></a><span data-ttu-id="20661-129">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="20661-129">Related topics</span></span>
- [<span data-ttu-id="20661-130">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="20661-130">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="20661-131">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="20661-131">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="20661-132">Utilizzare le query condivise</span><span class="sxs-lookup"><span data-stu-id="20661-132">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="20661-133">Cercare tra dispositivi, posta elettronica, app e identità</span><span class="sxs-lookup"><span data-stu-id="20661-133">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="20661-134">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="20661-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="20661-135">Applicare le procedure consigliate per le query</span><span class="sxs-lookup"><span data-stu-id="20661-135">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
