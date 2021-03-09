---
title: Modifiche di denominazione nello schema di ricerca avanzata di Microsoft 365 Defender
description: Tenere traccia e rivedere le tabelle e le colonne delle modifiche di denominazione nello schema di ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca delle minacce informatiche, microsoft threat protection, Microsoft 365, mtp, m365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, dati, modifiche dei nomi, rinominare, Microsoft Threat Protection
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
ms.openlocfilehash: 948c8bb5c1e6b67f6de355bc532c6b14d5a83933
ms.sourcegitcommit: 6e260f5f5842debe1098138eecea9068330dc17f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/08/2021
ms.locfileid: "50551873"
---
# <a name="advanced-hunting-schema---naming-changes"></a><span data-ttu-id="6be24-104">Schema ricerca avanzata - Modifiche alla denominazione</span><span class="sxs-lookup"><span data-stu-id="6be24-104">Advanced hunting schema - Naming changes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="6be24-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="6be24-105">**Applies to:**</span></span>
- <span data-ttu-id="6be24-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6be24-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="6be24-107">Lo [schema di ricerca](advanced-hunting-schema-tables.md) avanzata viene aggiornato regolarmente per aggiungere nuove tabelle e colonne.</span><span class="sxs-lookup"><span data-stu-id="6be24-107">The [advanced hunting schema](advanced-hunting-schema-tables.md) is updated regularly to add new tables and columns.</span></span> <span data-ttu-id="6be24-108">In alcuni casi, i nomi delle colonne esistenti vengono rinominati o sostituiti per migliorare l'esperienza utente.</span><span class="sxs-lookup"><span data-stu-id="6be24-108">In some cases, existing columns names are renamed or replaced to improve the user experience.</span></span> <span data-ttu-id="6be24-109">Fare riferimento a questo articolo per esaminare le modifiche di denominazione che potrebbero influire sulle query.</span><span class="sxs-lookup"><span data-stu-id="6be24-109">Refer to this article to review naming changes that could impact your queries.</span></span>

<span data-ttu-id="6be24-110">Le modifiche di denominazione vengono applicate automaticamente alle query salvate nel Centro sicurezza, incluse le query utilizzate dalle regole di rilevamento personalizzate.</span><span class="sxs-lookup"><span data-stu-id="6be24-110">Naming changes are automatically applied to queries that are saved in the security center, including queries used by custom detection rules.</span></span> <span data-ttu-id="6be24-111">Non è necessario aggiornare manualmente queste query.</span><span class="sxs-lookup"><span data-stu-id="6be24-111">You don't need to update these queries manually.</span></span> <span data-ttu-id="6be24-112">Sarà tuttavia necessario aggiornare le query seguenti:</span><span class="sxs-lookup"><span data-stu-id="6be24-112">However, you will need to update the following queries:</span></span>
- <span data-ttu-id="6be24-113">Query eseguite con l'API</span><span class="sxs-lookup"><span data-stu-id="6be24-113">Queries that are run using the API</span></span>
- <span data-ttu-id="6be24-114">Query salvate altrove all'esterno del Centro sicurezza</span><span class="sxs-lookup"><span data-stu-id="6be24-114">Queries that are saved elsewhere outside the security center</span></span>

## <a name="december-2020"></a><span data-ttu-id="6be24-115">Dicembre 2020</span><span class="sxs-lookup"><span data-stu-id="6be24-115">December 2020</span></span>

| <span data-ttu-id="6be24-116">Nome della tabella</span><span class="sxs-lookup"><span data-stu-id="6be24-116">Table name</span></span> | <span data-ttu-id="6be24-117">Nome colonna originale</span><span class="sxs-lookup"><span data-stu-id="6be24-117">Original column name</span></span> | <span data-ttu-id="6be24-118">Nome nuova colonna</span><span class="sxs-lookup"><span data-stu-id="6be24-118">New column name</span></span> | <span data-ttu-id="6be24-119">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="6be24-119">Reason for change</span></span>
|--|--|--|--|
| [<span data-ttu-id="6be24-120">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="6be24-120">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailAction` | `EmailAction` | <span data-ttu-id="6be24-121">Feedback dei clienti</span><span class="sxs-lookup"><span data-stu-id="6be24-121">Customer feedback</span></span> |
| [<span data-ttu-id="6be24-122">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="6be24-122">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicy` | `EmailActionPolicy` | <span data-ttu-id="6be24-123">Feedback dei clienti</span><span class="sxs-lookup"><span data-stu-id="6be24-123">Customer feedback</span></span> |
| [<span data-ttu-id="6be24-124">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="6be24-124">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicyGuid` | `EmailActionPolicyGuid` | <span data-ttu-id="6be24-125">Feedback dei clienti</span><span class="sxs-lookup"><span data-stu-id="6be24-125">Customer feedback</span></span> |

## <a name="january-2021"></a><span data-ttu-id="6be24-126">Gennaio 2021</span><span class="sxs-lookup"><span data-stu-id="6be24-126">January 2021</span></span>

| <span data-ttu-id="6be24-127">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="6be24-127">Column name</span></span> | <span data-ttu-id="6be24-128">Nome valore originale</span><span class="sxs-lookup"><span data-stu-id="6be24-128">Original value name</span></span> | <span data-ttu-id="6be24-129">Nome nuovo valore</span><span class="sxs-lookup"><span data-stu-id="6be24-129">New value name</span></span> | <span data-ttu-id="6be24-130">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="6be24-130">Reason for change</span></span>
|--|--|--|--|
| `DetectionSource` | <span data-ttu-id="6be24-131">MCAS</span><span class="sxs-lookup"><span data-stu-id="6be24-131">MCAS</span></span> |    <span data-ttu-id="6be24-132">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="6be24-132">Microsoft Cloud App Security</span></span> | <span data-ttu-id="6be24-133">Rebranding</span><span class="sxs-lookup"><span data-stu-id="6be24-133">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="6be24-134">WindowsDefenderAtp</span><span class="sxs-lookup"><span data-stu-id="6be24-134">WindowsDefenderAtp</span></span>|   <span data-ttu-id="6be24-135">EDR</span><span class="sxs-lookup"><span data-stu-id="6be24-135">EDR</span></span>| <span data-ttu-id="6be24-136">Rebranding</span><span class="sxs-lookup"><span data-stu-id="6be24-136">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="6be24-137">WindowsDefenderAv</span><span class="sxs-lookup"><span data-stu-id="6be24-137">WindowsDefenderAv</span></span> | <span data-ttu-id="6be24-138">Antivirus</span><span class="sxs-lookup"><span data-stu-id="6be24-138">Antivirus</span></span> | <span data-ttu-id="6be24-139">Rebranding</span><span class="sxs-lookup"><span data-stu-id="6be24-139">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="6be24-140">WindowsDefenderSmartScreen</span><span class="sxs-lookup"><span data-stu-id="6be24-140">WindowsDefenderSmartScreen</span></span> |  <span data-ttu-id="6be24-141">SmartScreen</span><span class="sxs-lookup"><span data-stu-id="6be24-141">SmartScreen</span></span> | <span data-ttu-id="6be24-142">Rebranding</span><span class="sxs-lookup"><span data-stu-id="6be24-142">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="6be24-143">CustomerTI</span><span class="sxs-lookup"><span data-stu-id="6be24-143">CustomerTI</span></span> |  <span data-ttu-id="6be24-144">Ti personalizzato</span><span class="sxs-lookup"><span data-stu-id="6be24-144">Custom TI</span></span> | <span data-ttu-id="6be24-145">Rebranding</span><span class="sxs-lookup"><span data-stu-id="6be24-145">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="6be24-146">OfficeATP</span><span class="sxs-lookup"><span data-stu-id="6be24-146">OfficeATP</span></span> | <span data-ttu-id="6be24-147">Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="6be24-147">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="6be24-148">Rebranding</span><span class="sxs-lookup"><span data-stu-id="6be24-148">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="6be24-149">MTP</span><span class="sxs-lookup"><span data-stu-id="6be24-149">MTP</span></span>   | <span data-ttu-id="6be24-150">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6be24-150">Microsoft 365 Defender</span></span> | <span data-ttu-id="6be24-151">Rebranding</span><span class="sxs-lookup"><span data-stu-id="6be24-151">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="6be24-152">AzureATP</span><span class="sxs-lookup"><span data-stu-id="6be24-152">AzureATP</span></span> |    <span data-ttu-id="6be24-153">Che cosa è Microsoft Defender per identità?</span><span class="sxs-lookup"><span data-stu-id="6be24-153">Microsoft Defender for Identity</span></span> | <span data-ttu-id="6be24-154">Rebranding</span><span class="sxs-lookup"><span data-stu-id="6be24-154">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="6be24-155">CustomDetection</span><span class="sxs-lookup"><span data-stu-id="6be24-155">CustomDetection</span></span>   | <span data-ttu-id="6be24-156">Rilevamento personalizzato</span><span class="sxs-lookup"><span data-stu-id="6be24-156">Custom detection</span></span> | <span data-ttu-id="6be24-157">Rebranding</span><span class="sxs-lookup"><span data-stu-id="6be24-157">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="6be24-158">AutomatedInvestigation</span><span class="sxs-lookup"><span data-stu-id="6be24-158">AutomatedInvestigation</span></span> |<span data-ttu-id="6be24-159">Indagine automatizzata</span><span class="sxs-lookup"><span data-stu-id="6be24-159">Automated investigation</span></span> | <span data-ttu-id="6be24-160">Rebranding</span><span class="sxs-lookup"><span data-stu-id="6be24-160">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="6be24-161">ThreatExperts</span><span class="sxs-lookup"><span data-stu-id="6be24-161">ThreatExperts</span></span> | <span data-ttu-id="6be24-162">Microsoft Threat Experts</span><span class="sxs-lookup"><span data-stu-id="6be24-162">Microsoft Threat Experts</span></span> | <span data-ttu-id="6be24-163">Rebranding</span><span class="sxs-lookup"><span data-stu-id="6be24-163">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="6be24-164">TI di terze parti</span><span class="sxs-lookup"><span data-stu-id="6be24-164">3rd party TI</span></span> | <span data-ttu-id="6be24-165">Sensori di terze parti</span><span class="sxs-lookup"><span data-stu-id="6be24-165">3rd Party sensors</span></span> | <span data-ttu-id="6be24-166">Rebranding</span><span class="sxs-lookup"><span data-stu-id="6be24-166">Rebranding</span></span> |
| `ServiceSource` | <span data-ttu-id="6be24-167">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="6be24-167">Microsoft Defender ATP</span></span>| <span data-ttu-id="6be24-168">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="6be24-168">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="6be24-169">Rebranding</span><span class="sxs-lookup"><span data-stu-id="6be24-169">Rebranding</span></span> |
|`ServiceSource` |<span data-ttu-id="6be24-170">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="6be24-170">Microsoft Threat Protection</span></span>   | <span data-ttu-id="6be24-171">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6be24-171">Microsoft 365 Defender</span></span> | <span data-ttu-id="6be24-172">Rebranding</span><span class="sxs-lookup"><span data-stu-id="6be24-172">Rebranding</span></span> |
| `ServiceSource` | <span data-ttu-id="6be24-173">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="6be24-173">Office 365 ATP</span></span>  |<span data-ttu-id="6be24-174">Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="6be24-174">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="6be24-175">Rebranding</span><span class="sxs-lookup"><span data-stu-id="6be24-175">Rebranding</span></span> |
| `ServiceSource` |<span data-ttu-id="6be24-176">Azure ATP</span><span class="sxs-lookup"><span data-stu-id="6be24-176">Azure ATP</span></span>    |<span data-ttu-id="6be24-177">Che cosa è Microsoft Defender per identità?</span><span class="sxs-lookup"><span data-stu-id="6be24-177">Microsoft Defender for Identity</span></span> | <span data-ttu-id="6be24-178">Rebranding</span><span class="sxs-lookup"><span data-stu-id="6be24-178">Rebranding</span></span> |

<span data-ttu-id="6be24-179">`DetectionSource`è disponibile nella [tabella AlertInfo.](advanced-hunting-alertinfo-table.md)</span><span class="sxs-lookup"><span data-stu-id="6be24-179">`DetectionSource` is available in the [AlertInfo](advanced-hunting-alertinfo-table.md) table.</span></span> <span data-ttu-id="6be24-180">`ServiceSource`è disponibile nelle tabelle [AlertEvidence](advanced-hunting-alertevidence-table.md) [e AlertInfo.](advanced-hunting-alertinfo-table.md)</span><span class="sxs-lookup"><span data-stu-id="6be24-180">`ServiceSource` is available in the [AlertEvidence](advanced-hunting-alertevidence-table.md) and [AlertInfo](advanced-hunting-alertinfo-table.md) tables.</span></span> 

## <a name="february-2021"></a><span data-ttu-id="6be24-181">Febbraio 2021</span><span class="sxs-lookup"><span data-stu-id="6be24-181">February 2021</span></span>

1. <span data-ttu-id="6be24-182">Nelle tabelle [EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) e [EmailEvents,](advanced-hunting-emailevents-table.md) le colonne e sono `MalwareFilterVerdict` state `PhishFilterVerdict` sostituite dalla `ThreatTypes` colonna.</span><span class="sxs-lookup"><span data-stu-id="6be24-182">In the [EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) and [EmailEvents](advanced-hunting-emailevents-table.md) tables, the `MalwareFilterVerdict`and `PhishFilterVerdict` columns have been replaced by the `ThreatTypes` column.</span></span> <span data-ttu-id="6be24-183">Anche `MalwareDetectionMethod` le colonne e le colonne sono state `PhishDetectionMethod` sostituite dalla `DetectionMethods` colonna.</span><span class="sxs-lookup"><span data-stu-id="6be24-183">The `MalwareDetectionMethod` and `PhishDetectionMethod` columns were also replaced by the `DetectionMethods` column.</span></span> <span data-ttu-id="6be24-184">Questa snellizione consente di fornire ulteriori informazioni nelle nuove colonne.</span><span class="sxs-lookup"><span data-stu-id="6be24-184">This streamlining allows us to provide more information under the new columns.</span></span> <span data-ttu-id="6be24-185">Il mapping viene fornito di seguito.</span><span class="sxs-lookup"><span data-stu-id="6be24-185">The mapping is provided below.</span></span>

| <span data-ttu-id="6be24-186">Nome della tabella</span><span class="sxs-lookup"><span data-stu-id="6be24-186">Table name</span></span> | <span data-ttu-id="6be24-187">Nome colonna originale</span><span class="sxs-lookup"><span data-stu-id="6be24-187">Original column name</span></span> | <span data-ttu-id="6be24-188">Nome nuova colonna</span><span class="sxs-lookup"><span data-stu-id="6be24-188">New column name</span></span> | <span data-ttu-id="6be24-189">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="6be24-189">Reason for change</span></span>
|--|--|--|--|
| `EmailAttachmentInfo` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | <span data-ttu-id="6be24-190">Includere altri metodi di rilevamento</span><span class="sxs-lookup"><span data-stu-id="6be24-190">Include more detection methods</span></span> |
| `EmailAttachmentInfo`  | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | <span data-ttu-id="6be24-191">Includere altri tipi di minaccia</span><span class="sxs-lookup"><span data-stu-id="6be24-191">Include more threat types</span></span> |
| `EmailEvents` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | <span data-ttu-id="6be24-192">Includere altri metodi di rilevamento</span><span class="sxs-lookup"><span data-stu-id="6be24-192">Include more detection methods</span></span> |
| `EmailEvents` | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | <span data-ttu-id="6be24-193">Includere altri tipi di minaccia</span><span class="sxs-lookup"><span data-stu-id="6be24-193">Include more threat types</span></span> |


2. <span data-ttu-id="6be24-194">Nelle tabelle `EmailAttachmentInfo` e `EmailEvents` nelle tabelle, la colonna è stata `ThreatNames` aggiunta per fornire ulteriori informazioni sulla minaccia di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="6be24-194">In the `EmailAttachmentInfo` and `EmailEvents` tables, the `ThreatNames` column was added to give more information about the email threat.</span></span> <span data-ttu-id="6be24-195">Questa colonna contiene valori come Posta indesiderata o Phish.</span><span class="sxs-lookup"><span data-stu-id="6be24-195">This column contains values like Spam or Phish.</span></span>

3. <span data-ttu-id="6be24-196">Nella tabella [DeviceInfo](advanced-hunting-deviceinfo-table.md) la colonna è stata sostituita dalla colonna in base `DeviceObjectId` al feedback dei `AadDeviceId` clienti.</span><span class="sxs-lookup"><span data-stu-id="6be24-196">In the [DeviceInfo](advanced-hunting-deviceinfo-table.md) table, the `DeviceObjectId` column was replaced by the `AadDeviceId` column based on customer feedback.</span></span>

4. <span data-ttu-id="6be24-197">Nella tabella [DeviceEvents](advanced-hunting-deviceevents-table.md) sono stati modificati diversi nomi ActionType per riflettere meglio la descrizione dell'azione.</span><span class="sxs-lookup"><span data-stu-id="6be24-197">In the [DeviceEvents](advanced-hunting-deviceevents-table.md) table, several ActionType names were modified to better reflect the description of the action.</span></span> <span data-ttu-id="6be24-198">I dettagli delle modifiche sono disponibili di seguito.</span><span class="sxs-lookup"><span data-stu-id="6be24-198">Details of the changes can be found below.</span></span>

| <span data-ttu-id="6be24-199">Nome della tabella</span><span class="sxs-lookup"><span data-stu-id="6be24-199">Table name</span></span> | <span data-ttu-id="6be24-200">Nome ActionType originale</span><span class="sxs-lookup"><span data-stu-id="6be24-200">Original ActionType name</span></span> | <span data-ttu-id="6be24-201">Nuovo nome ActionType</span><span class="sxs-lookup"><span data-stu-id="6be24-201">New ActionType name</span></span> | <span data-ttu-id="6be24-202">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="6be24-202">Reason for change</span></span>
|--|--|--|--|
| `DeviceEvents` | `DlpPocPrintJob` | `FilePrinted` | <span data-ttu-id="6be24-203">Feedback dei clienti</span><span class="sxs-lookup"><span data-stu-id="6be24-203">Customer feedback</span></span> |
| `DeviceEvents` | `UsbDriveMount` | `UsbDriveMounted` | <span data-ttu-id="6be24-204">Feedback dei clienti</span><span class="sxs-lookup"><span data-stu-id="6be24-204">Customer feedback</span></span> |
| `DeviceEvents` | `UsbDriveUnmount` | `UsbDriveUnmounted` | <span data-ttu-id="6be24-205">Feedback dei clienti</span><span class="sxs-lookup"><span data-stu-id="6be24-205">Customer feedback</span></span> |
| `DeviceEvents` | `WriteProcessMemoryApiCall` | `WriteToLsassProcessMemory` | <span data-ttu-id="6be24-206">Feedback dei clienti</span><span class="sxs-lookup"><span data-stu-id="6be24-206">Customer feedback</span></span> |






## <a name="related-topics"></a><span data-ttu-id="6be24-207">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="6be24-207">Related topics</span></span>
- [<span data-ttu-id="6be24-208">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="6be24-208">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="6be24-209">Comprensione dello schema</span><span class="sxs-lookup"><span data-stu-id="6be24-209">Understand the schema</span></span>](advanced-hunting-schema-tables.md)