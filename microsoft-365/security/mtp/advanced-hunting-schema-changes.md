---
title: Modifiche di denominazione nello schema di ricerca avanzata di Microsoft 365 Defender
description: Tenere traccia e rivedere le tabelle e le colonne delle modifiche di denominazione nello schema di ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca delle minacce informatiche, microsoft threat protection, Microsoft 365, mtp, m365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, dati, modifiche di denominazione, rinominare, Microsoft Threat Protection
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
ms.openlocfilehash: 3f03543b03dca5fe426700ffff4f5c6edb8fa3c7
ms.sourcegitcommit: c550c1b5b9e67398fd95bfb0256c4f5c7930b2be
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2021
ms.locfileid: "50066870"
---
# <a name="advanced-hunting-schema---naming-changes"></a><span data-ttu-id="48822-104">Schema ricerca avanzata - Modifiche alla denominazione</span><span class="sxs-lookup"><span data-stu-id="48822-104">Advanced hunting schema - Naming changes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="48822-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="48822-105">**Applies to:**</span></span>
- <span data-ttu-id="48822-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="48822-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="48822-107">Lo [schema di ricerca](advanced-hunting-schema-tables.md) avanzata viene aggiornato regolarmente per aggiungere nuove tabelle e colonne.</span><span class="sxs-lookup"><span data-stu-id="48822-107">The [advanced hunting schema](advanced-hunting-schema-tables.md) is updated regularly to add new tables and columns.</span></span> <span data-ttu-id="48822-108">In alcuni casi, i nomi delle colonne esistenti vengono rinominati o sostituiti per migliorare l'esperienza utente.</span><span class="sxs-lookup"><span data-stu-id="48822-108">In some cases, existing columns names are renamed or replaced to improve the user experience.</span></span> <span data-ttu-id="48822-109">Fare riferimento a questo articolo per esaminare le modifiche di denominazione che potrebbero influire sulle query.</span><span class="sxs-lookup"><span data-stu-id="48822-109">Refer to this article to review naming changes that could impact your queries.</span></span>

<span data-ttu-id="48822-110">Le modifiche di denominazione vengono applicate automaticamente alle query salvate nel Centro sicurezza, incluse le query utilizzate dalle regole di rilevamento personalizzate.</span><span class="sxs-lookup"><span data-stu-id="48822-110">Naming changes are automatically applied to queries that are saved in the security center, including queries used by custom detection rules.</span></span> <span data-ttu-id="48822-111">Non è necessario aggiornare manualmente queste query.</span><span class="sxs-lookup"><span data-stu-id="48822-111">You don't need to update these queries manually.</span></span> <span data-ttu-id="48822-112">Sarà tuttavia necessario aggiornare le query seguenti:</span><span class="sxs-lookup"><span data-stu-id="48822-112">However, you will need to update the following queries:</span></span>
- <span data-ttu-id="48822-113">Query eseguite con l'API</span><span class="sxs-lookup"><span data-stu-id="48822-113">Queries that are run using the API</span></span>
- <span data-ttu-id="48822-114">Query salvate altrove all'esterno del Centro sicurezza</span><span class="sxs-lookup"><span data-stu-id="48822-114">Queries that are saved elsewhere outside the security center</span></span>

## <a name="december-2020"></a><span data-ttu-id="48822-115">Dicembre 2020</span><span class="sxs-lookup"><span data-stu-id="48822-115">December 2020</span></span>

| <span data-ttu-id="48822-116">Nome della tabella</span><span class="sxs-lookup"><span data-stu-id="48822-116">Table name</span></span> | <span data-ttu-id="48822-117">Nome colonna originale</span><span class="sxs-lookup"><span data-stu-id="48822-117">Original column name</span></span> | <span data-ttu-id="48822-118">Nome nuova colonna</span><span class="sxs-lookup"><span data-stu-id="48822-118">New column name</span></span> | <span data-ttu-id="48822-119">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="48822-119">Reason for change</span></span>
|--|--|--|--|
| [<span data-ttu-id="48822-120">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="48822-120">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailAction` | `EmailAction` | <span data-ttu-id="48822-121">Feedback dei clienti</span><span class="sxs-lookup"><span data-stu-id="48822-121">Customer feedback</span></span> |
| [<span data-ttu-id="48822-122">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="48822-122">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicy` | `EmailActionPolicy` | <span data-ttu-id="48822-123">Feedback dei clienti</span><span class="sxs-lookup"><span data-stu-id="48822-123">Customer feedback</span></span> |
| [<span data-ttu-id="48822-124">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="48822-124">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicyGuid` | `EmailActionPolicyGuid` | <span data-ttu-id="48822-125">Feedback dei clienti</span><span class="sxs-lookup"><span data-stu-id="48822-125">Customer feedback</span></span> |

## <a name="january-2021"></a><span data-ttu-id="48822-126">Gennaio 2021</span><span class="sxs-lookup"><span data-stu-id="48822-126">January 2021</span></span>

| <span data-ttu-id="48822-127">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="48822-127">Column name</span></span> | <span data-ttu-id="48822-128">Nome valore originale</span><span class="sxs-lookup"><span data-stu-id="48822-128">Original value name</span></span> | <span data-ttu-id="48822-129">Nome nuovo valore</span><span class="sxs-lookup"><span data-stu-id="48822-129">New value name</span></span> | <span data-ttu-id="48822-130">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="48822-130">Reason for change</span></span>
|--|--|--|--|
| `DetectionSource` | <span data-ttu-id="48822-131">MCAS</span><span class="sxs-lookup"><span data-stu-id="48822-131">MCAS</span></span> |    <span data-ttu-id="48822-132">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="48822-132">Microsoft Cloud App Security</span></span> | <span data-ttu-id="48822-133">Rebranding</span><span class="sxs-lookup"><span data-stu-id="48822-133">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="48822-134">WindowsDefenderAtp</span><span class="sxs-lookup"><span data-stu-id="48822-134">WindowsDefenderAtp</span></span>|   <span data-ttu-id="48822-135">EDR</span><span class="sxs-lookup"><span data-stu-id="48822-135">EDR</span></span>| <span data-ttu-id="48822-136">Rebranding</span><span class="sxs-lookup"><span data-stu-id="48822-136">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="48822-137">WindowsDefenderAv</span><span class="sxs-lookup"><span data-stu-id="48822-137">WindowsDefenderAv</span></span> | <span data-ttu-id="48822-138">Antivirus</span><span class="sxs-lookup"><span data-stu-id="48822-138">Antivirus</span></span> | <span data-ttu-id="48822-139">Rebranding</span><span class="sxs-lookup"><span data-stu-id="48822-139">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="48822-140">WindowsDefenderSmartScreen</span><span class="sxs-lookup"><span data-stu-id="48822-140">WindowsDefenderSmartScreen</span></span> |  <span data-ttu-id="48822-141">SmartScreen</span><span class="sxs-lookup"><span data-stu-id="48822-141">SmartScreen</span></span> | <span data-ttu-id="48822-142">Rebranding</span><span class="sxs-lookup"><span data-stu-id="48822-142">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="48822-143">CustomerTI</span><span class="sxs-lookup"><span data-stu-id="48822-143">CustomerTI</span></span> |  <span data-ttu-id="48822-144">Ti personalizzato</span><span class="sxs-lookup"><span data-stu-id="48822-144">Custom TI</span></span> | <span data-ttu-id="48822-145">Rebranding</span><span class="sxs-lookup"><span data-stu-id="48822-145">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="48822-146">OfficeATP</span><span class="sxs-lookup"><span data-stu-id="48822-146">OfficeATP</span></span> | <span data-ttu-id="48822-147">Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="48822-147">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="48822-148">Rebranding</span><span class="sxs-lookup"><span data-stu-id="48822-148">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="48822-149">MTP</span><span class="sxs-lookup"><span data-stu-id="48822-149">MTP</span></span>   | <span data-ttu-id="48822-150">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="48822-150">Microsoft 365 Defender</span></span> | <span data-ttu-id="48822-151">Rebranding</span><span class="sxs-lookup"><span data-stu-id="48822-151">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="48822-152">AzureATP</span><span class="sxs-lookup"><span data-stu-id="48822-152">AzureATP</span></span> |    <span data-ttu-id="48822-153">Che cosa è Microsoft Defender per identità?</span><span class="sxs-lookup"><span data-stu-id="48822-153">Microsoft Defender for Identity</span></span> | <span data-ttu-id="48822-154">Rebranding</span><span class="sxs-lookup"><span data-stu-id="48822-154">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="48822-155">CustomDetection</span><span class="sxs-lookup"><span data-stu-id="48822-155">CustomDetection</span></span>   | <span data-ttu-id="48822-156">Rilevamento personalizzato</span><span class="sxs-lookup"><span data-stu-id="48822-156">Custom detection</span></span> | <span data-ttu-id="48822-157">Rebranding</span><span class="sxs-lookup"><span data-stu-id="48822-157">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="48822-158">AutomatedInvestigation</span><span class="sxs-lookup"><span data-stu-id="48822-158">AutomatedInvestigation</span></span> |<span data-ttu-id="48822-159">Indagine automatizzata</span><span class="sxs-lookup"><span data-stu-id="48822-159">Automated investigation</span></span> | <span data-ttu-id="48822-160">Rebranding</span><span class="sxs-lookup"><span data-stu-id="48822-160">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="48822-161">ThreatExperts</span><span class="sxs-lookup"><span data-stu-id="48822-161">ThreatExperts</span></span> | <span data-ttu-id="48822-162">Microsoft Threat Experts</span><span class="sxs-lookup"><span data-stu-id="48822-162">Microsoft Threat Experts</span></span> | <span data-ttu-id="48822-163">Rebranding</span><span class="sxs-lookup"><span data-stu-id="48822-163">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="48822-164">TI di terze parti</span><span class="sxs-lookup"><span data-stu-id="48822-164">3rd party TI</span></span> | <span data-ttu-id="48822-165">Sensori di terze parti</span><span class="sxs-lookup"><span data-stu-id="48822-165">3rd Party sensors</span></span> | <span data-ttu-id="48822-166">Rebranding</span><span class="sxs-lookup"><span data-stu-id="48822-166">Rebranding</span></span> |
| `ServiceSource` | <span data-ttu-id="48822-167">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="48822-167">Microsoft Defender ATP</span></span>| <span data-ttu-id="48822-168">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="48822-168">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="48822-169">Rebranding</span><span class="sxs-lookup"><span data-stu-id="48822-169">Rebranding</span></span> |
|`ServiceSource` |<span data-ttu-id="48822-170">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="48822-170">Microsoft Threat Protection</span></span>   | <span data-ttu-id="48822-171">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="48822-171">Microsoft 365 Defender</span></span> | <span data-ttu-id="48822-172">Rebranding</span><span class="sxs-lookup"><span data-stu-id="48822-172">Rebranding</span></span> |
| `ServiceSource` | <span data-ttu-id="48822-173">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="48822-173">Office 365 ATP</span></span>  |<span data-ttu-id="48822-174">Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="48822-174">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="48822-175">Rebranding</span><span class="sxs-lookup"><span data-stu-id="48822-175">Rebranding</span></span> |
| `ServiceSource` |<span data-ttu-id="48822-176">Azure ATP</span><span class="sxs-lookup"><span data-stu-id="48822-176">Azure ATP</span></span>    |<span data-ttu-id="48822-177">Che cosa è Microsoft Defender per identità?</span><span class="sxs-lookup"><span data-stu-id="48822-177">Microsoft Defender for Identity</span></span> | <span data-ttu-id="48822-178">Rebranding</span><span class="sxs-lookup"><span data-stu-id="48822-178">Rebranding</span></span> |

<span data-ttu-id="48822-179">`DetectionSource`è disponibile nella [tabella AlertInfo.](advanced-hunting-alertinfo-table.md)</span><span class="sxs-lookup"><span data-stu-id="48822-179">`DetectionSource` is available in the [AlertInfo](advanced-hunting-alertinfo-table.md) table.</span></span> <span data-ttu-id="48822-180">`ServiceSource`è disponibile nelle tabelle [AlertEvidence](advanced-hunting-alertevidence-table.md) [e AlertInfo.](advanced-hunting-alertinfo-table.md)</span><span class="sxs-lookup"><span data-stu-id="48822-180">`ServiceSource` is available in the [AlertEvidence](advanced-hunting-alertevidence-table.md) and [AlertInfo](advanced-hunting-alertinfo-table.md) tables.</span></span> 
## <a name="related-topics"></a><span data-ttu-id="48822-181">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="48822-181">Related topics</span></span>
- [<span data-ttu-id="48822-182">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="48822-182">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="48822-183">Comprensione dello schema</span><span class="sxs-lookup"><span data-stu-id="48822-183">Understand the schema</span></span>](advanced-hunting-schema-tables.md)