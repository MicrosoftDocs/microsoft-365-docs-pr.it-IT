---
title: Modifiche di denominazione nello schema di ricerca avanzata di Microsoft 365 Defender
description: Tenere traccia e rivedere le tabelle e le colonne delle modifiche di denominazione nello schema di ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca delle minacce informatiche, protezione dalle minacce Microsoft, Microsoft 365, mtp, m365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, dati, modifiche dei nomi, rinominare, Microsoft Threat Protection
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
# <a name="advanced-hunting-schema---naming-changes"></a><span data-ttu-id="3714b-104">Schema ricerca avanzata - Modifiche alla denominazione</span><span class="sxs-lookup"><span data-stu-id="3714b-104">Advanced hunting schema - Naming changes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="3714b-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="3714b-105">**Applies to:**</span></span>
- <span data-ttu-id="3714b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3714b-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="3714b-107">Lo [schema di ricerca](advanced-hunting-schema-tables.md) avanzata viene aggiornato regolarmente per aggiungere nuove tabelle e colonne.</span><span class="sxs-lookup"><span data-stu-id="3714b-107">The [advanced hunting schema](advanced-hunting-schema-tables.md) is updated regularly to add new tables and columns.</span></span> <span data-ttu-id="3714b-108">In alcuni casi, i nomi delle colonne esistenti vengono rinominati o sostituiti per migliorare l'esperienza utente.</span><span class="sxs-lookup"><span data-stu-id="3714b-108">In some cases, existing columns names are renamed or replaced to improve the user experience.</span></span> <span data-ttu-id="3714b-109">Fare riferimento a questo articolo per esaminare le modifiche di denominazione che potrebbero influire sulle query.</span><span class="sxs-lookup"><span data-stu-id="3714b-109">Refer to this article to review naming changes that could impact your queries.</span></span>

<span data-ttu-id="3714b-110">Le modifiche di denominazione vengono applicate automaticamente alle query salvate nel Centro sicurezza, incluse le query utilizzate dalle regole di rilevamento personalizzate.</span><span class="sxs-lookup"><span data-stu-id="3714b-110">Naming changes are automatically applied to queries that are saved in the security center, including queries used by custom detection rules.</span></span> <span data-ttu-id="3714b-111">Non è necessario aggiornare manualmente queste query.</span><span class="sxs-lookup"><span data-stu-id="3714b-111">You don't need to update these queries manually.</span></span> <span data-ttu-id="3714b-112">Sarà tuttavia necessario aggiornare le query seguenti:</span><span class="sxs-lookup"><span data-stu-id="3714b-112">However, you will need to update the following queries:</span></span>
- <span data-ttu-id="3714b-113">Query eseguite con l'API</span><span class="sxs-lookup"><span data-stu-id="3714b-113">Queries that are run using the API</span></span>
- <span data-ttu-id="3714b-114">Query salvate altrove all'esterno del Centro sicurezza</span><span class="sxs-lookup"><span data-stu-id="3714b-114">Queries that are saved elsewhere outside the security center</span></span>

## <a name="december-2020"></a><span data-ttu-id="3714b-115">Dicembre 2020</span><span class="sxs-lookup"><span data-stu-id="3714b-115">December 2020</span></span>

| <span data-ttu-id="3714b-116">Nome della tabella</span><span class="sxs-lookup"><span data-stu-id="3714b-116">Table name</span></span> | <span data-ttu-id="3714b-117">Nome colonna originale</span><span class="sxs-lookup"><span data-stu-id="3714b-117">Original column name</span></span> | <span data-ttu-id="3714b-118">Nome nuova colonna</span><span class="sxs-lookup"><span data-stu-id="3714b-118">New column name</span></span> | <span data-ttu-id="3714b-119">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="3714b-119">Reason for change</span></span>
|--|--|--|--|
| [<span data-ttu-id="3714b-120">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="3714b-120">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailAction` | `EmailAction` | <span data-ttu-id="3714b-121">Feedback dei clienti</span><span class="sxs-lookup"><span data-stu-id="3714b-121">Customer feedback</span></span> |
| [<span data-ttu-id="3714b-122">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="3714b-122">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicy` | `EmailActionPolicy` | <span data-ttu-id="3714b-123">Feedback dei clienti</span><span class="sxs-lookup"><span data-stu-id="3714b-123">Customer feedback</span></span> |
| [<span data-ttu-id="3714b-124">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="3714b-124">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicyGuid` | `EmailActionPolicyGuid` | <span data-ttu-id="3714b-125">Feedback dei clienti</span><span class="sxs-lookup"><span data-stu-id="3714b-125">Customer feedback</span></span> |

## <a name="january-2021"></a><span data-ttu-id="3714b-126">Gennaio 2021</span><span class="sxs-lookup"><span data-stu-id="3714b-126">January 2021</span></span>

| <span data-ttu-id="3714b-127">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="3714b-127">Column name</span></span> | <span data-ttu-id="3714b-128">Nome valore originale</span><span class="sxs-lookup"><span data-stu-id="3714b-128">Original value name</span></span> | <span data-ttu-id="3714b-129">Nome nuovo valore</span><span class="sxs-lookup"><span data-stu-id="3714b-129">New value name</span></span> | <span data-ttu-id="3714b-130">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="3714b-130">Reason for change</span></span>
|--|--|--|--|
| `DetectionSource` | <span data-ttu-id="3714b-131">MCAS</span><span class="sxs-lookup"><span data-stu-id="3714b-131">MCAS</span></span> |    <span data-ttu-id="3714b-132">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="3714b-132">Microsoft Cloud App Security</span></span> | <span data-ttu-id="3714b-133">Rebranding</span><span class="sxs-lookup"><span data-stu-id="3714b-133">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="3714b-134">WindowsDefenderAtp</span><span class="sxs-lookup"><span data-stu-id="3714b-134">WindowsDefenderAtp</span></span>|   <span data-ttu-id="3714b-135">EDR</span><span class="sxs-lookup"><span data-stu-id="3714b-135">EDR</span></span>| <span data-ttu-id="3714b-136">Rebranding</span><span class="sxs-lookup"><span data-stu-id="3714b-136">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="3714b-137">WindowsDefenderAv</span><span class="sxs-lookup"><span data-stu-id="3714b-137">WindowsDefenderAv</span></span> | <span data-ttu-id="3714b-138">Antivirus</span><span class="sxs-lookup"><span data-stu-id="3714b-138">Antivirus</span></span> | <span data-ttu-id="3714b-139">Rebranding</span><span class="sxs-lookup"><span data-stu-id="3714b-139">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="3714b-140">WindowsDefenderSmartScreen</span><span class="sxs-lookup"><span data-stu-id="3714b-140">WindowsDefenderSmartScreen</span></span> |  <span data-ttu-id="3714b-141">SmartScreen</span><span class="sxs-lookup"><span data-stu-id="3714b-141">SmartScreen</span></span> | <span data-ttu-id="3714b-142">Rebranding</span><span class="sxs-lookup"><span data-stu-id="3714b-142">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="3714b-143">CustomerTI</span><span class="sxs-lookup"><span data-stu-id="3714b-143">CustomerTI</span></span> |  <span data-ttu-id="3714b-144">Ti personalizzato</span><span class="sxs-lookup"><span data-stu-id="3714b-144">Custom TI</span></span> | <span data-ttu-id="3714b-145">Rebranding</span><span class="sxs-lookup"><span data-stu-id="3714b-145">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="3714b-146">OfficeATP</span><span class="sxs-lookup"><span data-stu-id="3714b-146">OfficeATP</span></span> | <span data-ttu-id="3714b-147">Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="3714b-147">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="3714b-148">Rebranding</span><span class="sxs-lookup"><span data-stu-id="3714b-148">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="3714b-149">MTP</span><span class="sxs-lookup"><span data-stu-id="3714b-149">MTP</span></span>   | <span data-ttu-id="3714b-150">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3714b-150">Microsoft 365 Defender</span></span> | <span data-ttu-id="3714b-151">Rebranding</span><span class="sxs-lookup"><span data-stu-id="3714b-151">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="3714b-152">AzureATP</span><span class="sxs-lookup"><span data-stu-id="3714b-152">AzureATP</span></span> |    <span data-ttu-id="3714b-153">Che cosa è Microsoft Defender per identità?</span><span class="sxs-lookup"><span data-stu-id="3714b-153">Microsoft Defender for Identity</span></span> | <span data-ttu-id="3714b-154">Rebranding</span><span class="sxs-lookup"><span data-stu-id="3714b-154">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="3714b-155">CustomDetection</span><span class="sxs-lookup"><span data-stu-id="3714b-155">CustomDetection</span></span>   | <span data-ttu-id="3714b-156">Rilevamento personalizzato</span><span class="sxs-lookup"><span data-stu-id="3714b-156">Custom detection</span></span> | <span data-ttu-id="3714b-157">Rebranding</span><span class="sxs-lookup"><span data-stu-id="3714b-157">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="3714b-158">AutomatedInvestigation</span><span class="sxs-lookup"><span data-stu-id="3714b-158">AutomatedInvestigation</span></span> |<span data-ttu-id="3714b-159">Indagine automatizzata</span><span class="sxs-lookup"><span data-stu-id="3714b-159">Automated investigation</span></span> | <span data-ttu-id="3714b-160">Rebranding</span><span class="sxs-lookup"><span data-stu-id="3714b-160">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="3714b-161">ThreatExperts</span><span class="sxs-lookup"><span data-stu-id="3714b-161">ThreatExperts</span></span> | <span data-ttu-id="3714b-162">Microsoft Threat Experts</span><span class="sxs-lookup"><span data-stu-id="3714b-162">Microsoft Threat Experts</span></span> | <span data-ttu-id="3714b-163">Rebranding</span><span class="sxs-lookup"><span data-stu-id="3714b-163">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="3714b-164">TI di terze parti</span><span class="sxs-lookup"><span data-stu-id="3714b-164">3rd party TI</span></span> | <span data-ttu-id="3714b-165">Sensori di terze parti</span><span class="sxs-lookup"><span data-stu-id="3714b-165">3rd Party sensors</span></span> | <span data-ttu-id="3714b-166">Rebranding</span><span class="sxs-lookup"><span data-stu-id="3714b-166">Rebranding</span></span> |
| `ServiceSource` | <span data-ttu-id="3714b-167">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="3714b-167">Microsoft Defender ATP</span></span>| <span data-ttu-id="3714b-168">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="3714b-168">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="3714b-169">Rebranding</span><span class="sxs-lookup"><span data-stu-id="3714b-169">Rebranding</span></span> |
|`ServiceSource` |<span data-ttu-id="3714b-170">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="3714b-170">Microsoft Threat Protection</span></span>   | <span data-ttu-id="3714b-171">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3714b-171">Microsoft 365 Defender</span></span> | <span data-ttu-id="3714b-172">Rebranding</span><span class="sxs-lookup"><span data-stu-id="3714b-172">Rebranding</span></span> |
| `ServiceSource` | <span data-ttu-id="3714b-173">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="3714b-173">Office 365 ATP</span></span>  |<span data-ttu-id="3714b-174">Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="3714b-174">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="3714b-175">Rebranding</span><span class="sxs-lookup"><span data-stu-id="3714b-175">Rebranding</span></span> |
| `ServiceSource` |<span data-ttu-id="3714b-176">Azure ATP</span><span class="sxs-lookup"><span data-stu-id="3714b-176">Azure ATP</span></span>    |<span data-ttu-id="3714b-177">Che cosa è Microsoft Defender per identità?</span><span class="sxs-lookup"><span data-stu-id="3714b-177">Microsoft Defender for Identity</span></span> | <span data-ttu-id="3714b-178">Rebranding</span><span class="sxs-lookup"><span data-stu-id="3714b-178">Rebranding</span></span> |

<span data-ttu-id="3714b-179">`DetectionSource`è disponibile nella [tabella AlertInfo.](advanced-hunting-alertinfo-table.md)</span><span class="sxs-lookup"><span data-stu-id="3714b-179">`DetectionSource` is available in the [AlertInfo](advanced-hunting-alertinfo-table.md) table.</span></span> <span data-ttu-id="3714b-180">`ServiceSource`è disponibile nelle tabelle [AlertEvidence](advanced-hunting-alertevidence-table.md) [e AlertInfo.](advanced-hunting-alertinfo-table.md)</span><span class="sxs-lookup"><span data-stu-id="3714b-180">`ServiceSource` is available in the [AlertEvidence](advanced-hunting-alertevidence-table.md) and [AlertInfo](advanced-hunting-alertinfo-table.md) tables.</span></span> 
## <a name="related-topics"></a><span data-ttu-id="3714b-181">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="3714b-181">Related topics</span></span>
- [<span data-ttu-id="3714b-182">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="3714b-182">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="3714b-183">Comprensione dello schema</span><span class="sxs-lookup"><span data-stu-id="3714b-183">Understand the schema</span></span>](advanced-hunting-schema-tables.md)