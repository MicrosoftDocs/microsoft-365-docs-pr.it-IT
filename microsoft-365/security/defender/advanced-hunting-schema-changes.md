---
title: Modifiche di denominazione nello schema di ricerca avanzata di Microsoft 365 Defender
description: Tenere traccia e rivedere le tabelle e le colonne delle modifiche di denominazione nello schema di ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, Microsoft 365 Defender, Microsoft 365, m365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, dati, modifiche di denominazione, rinominare
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
ms.openlocfilehash: 22d26dac6b7ee502d6934349d22b1d40532f575f
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935774"
---
# <a name="advanced-hunting-schema---naming-changes"></a><span data-ttu-id="e7e3a-104">Schema di ricerca avanzata - Modifiche di denominazione</span><span class="sxs-lookup"><span data-stu-id="e7e3a-104">Advanced hunting schema - Naming changes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e7e3a-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="e7e3a-105">**Applies to:**</span></span>
- <span data-ttu-id="e7e3a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e7e3a-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="e7e3a-107">Lo [schema di ricerca](advanced-hunting-schema-tables.md) avanzata viene aggiornato regolarmente per aggiungere nuove tabelle e colonne.</span><span class="sxs-lookup"><span data-stu-id="e7e3a-107">The [advanced hunting schema](advanced-hunting-schema-tables.md) is updated regularly to add new tables and columns.</span></span> <span data-ttu-id="e7e3a-108">In alcuni casi, i nomi delle colonne esistenti vengono rinominati o sostituiti per migliorare l'esperienza utente.</span><span class="sxs-lookup"><span data-stu-id="e7e3a-108">In some cases, existing columns names are renamed or replaced to improve the user experience.</span></span> <span data-ttu-id="e7e3a-109">Fare riferimento a questo articolo per esaminare le modifiche di denominazione che potrebbero influire sulle query.</span><span class="sxs-lookup"><span data-stu-id="e7e3a-109">Refer to this article to review naming changes that could impact your queries.</span></span>

<span data-ttu-id="e7e3a-110">Le modifiche di denominazione vengono applicate automaticamente alle query salvate nel Centro sicurezza, incluse le query utilizzate dalle regole di rilevamento personalizzate.</span><span class="sxs-lookup"><span data-stu-id="e7e3a-110">Naming changes are automatically applied to queries that are saved in the security center, including queries used by custom detection rules.</span></span> <span data-ttu-id="e7e3a-111">Non è necessario aggiornare manualmente queste query.</span><span class="sxs-lookup"><span data-stu-id="e7e3a-111">You don't need to update these queries manually.</span></span> <span data-ttu-id="e7e3a-112">Sarà tuttavia necessario aggiornare le query seguenti:</span><span class="sxs-lookup"><span data-stu-id="e7e3a-112">However, you will need to update the following queries:</span></span>
- <span data-ttu-id="e7e3a-113">Query eseguite con l'API</span><span class="sxs-lookup"><span data-stu-id="e7e3a-113">Queries that are run using the API</span></span>
- <span data-ttu-id="e7e3a-114">Query salvate altrove all'esterno del Centro sicurezza</span><span class="sxs-lookup"><span data-stu-id="e7e3a-114">Queries that are saved elsewhere outside the security center</span></span>

## <a name="december-2020"></a><span data-ttu-id="e7e3a-115">Dicembre 2020</span><span class="sxs-lookup"><span data-stu-id="e7e3a-115">December 2020</span></span>

| <span data-ttu-id="e7e3a-116">Nome della tabella</span><span class="sxs-lookup"><span data-stu-id="e7e3a-116">Table name</span></span> | <span data-ttu-id="e7e3a-117">Nome colonna originale</span><span class="sxs-lookup"><span data-stu-id="e7e3a-117">Original column name</span></span> | <span data-ttu-id="e7e3a-118">Nome nuova colonna</span><span class="sxs-lookup"><span data-stu-id="e7e3a-118">New column name</span></span> | <span data-ttu-id="e7e3a-119">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="e7e3a-119">Reason for change</span></span>
|--|--|--|--|
| [<span data-ttu-id="e7e3a-120">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="e7e3a-120">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailAction` | `EmailAction` | <span data-ttu-id="e7e3a-121">Feedback dei clienti</span><span class="sxs-lookup"><span data-stu-id="e7e3a-121">Customer feedback</span></span> |
| [<span data-ttu-id="e7e3a-122">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="e7e3a-122">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicy` | `EmailActionPolicy` | <span data-ttu-id="e7e3a-123">Feedback dei clienti</span><span class="sxs-lookup"><span data-stu-id="e7e3a-123">Customer feedback</span></span> |
| [<span data-ttu-id="e7e3a-124">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="e7e3a-124">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicyGuid` | `EmailActionPolicyGuid` | <span data-ttu-id="e7e3a-125">Feedback dei clienti</span><span class="sxs-lookup"><span data-stu-id="e7e3a-125">Customer feedback</span></span> |

## <a name="january-2021"></a><span data-ttu-id="e7e3a-126">Gennaio 2021</span><span class="sxs-lookup"><span data-stu-id="e7e3a-126">January 2021</span></span>

| <span data-ttu-id="e7e3a-127">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="e7e3a-127">Column name</span></span> | <span data-ttu-id="e7e3a-128">Nome valore originale</span><span class="sxs-lookup"><span data-stu-id="e7e3a-128">Original value name</span></span> | <span data-ttu-id="e7e3a-129">Nuovo nome valore</span><span class="sxs-lookup"><span data-stu-id="e7e3a-129">New value name</span></span> | <span data-ttu-id="e7e3a-130">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="e7e3a-130">Reason for change</span></span>
|--|--|--|--|
| `DetectionSource` | <span data-ttu-id="e7e3a-131">MCAS</span><span class="sxs-lookup"><span data-stu-id="e7e3a-131">MCAS</span></span> |    <span data-ttu-id="e7e3a-132">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="e7e3a-132">Microsoft Cloud App Security</span></span> | <span data-ttu-id="e7e3a-133">Rebranding</span><span class="sxs-lookup"><span data-stu-id="e7e3a-133">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="e7e3a-134">WindowsDefenderAtp</span><span class="sxs-lookup"><span data-stu-id="e7e3a-134">WindowsDefenderAtp</span></span>|   <span data-ttu-id="e7e3a-135">EDR</span><span class="sxs-lookup"><span data-stu-id="e7e3a-135">EDR</span></span>| <span data-ttu-id="e7e3a-136">Rebranding</span><span class="sxs-lookup"><span data-stu-id="e7e3a-136">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="e7e3a-137">WindowsDefenderAv</span><span class="sxs-lookup"><span data-stu-id="e7e3a-137">WindowsDefenderAv</span></span> | <span data-ttu-id="e7e3a-138">Antivirus</span><span class="sxs-lookup"><span data-stu-id="e7e3a-138">Antivirus</span></span> | <span data-ttu-id="e7e3a-139">Rebranding</span><span class="sxs-lookup"><span data-stu-id="e7e3a-139">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="e7e3a-140">WindowsDefenderSmartScreen</span><span class="sxs-lookup"><span data-stu-id="e7e3a-140">WindowsDefenderSmartScreen</span></span> |  <span data-ttu-id="e7e3a-141">SmartScreen</span><span class="sxs-lookup"><span data-stu-id="e7e3a-141">SmartScreen</span></span> | <span data-ttu-id="e7e3a-142">Rebranding</span><span class="sxs-lookup"><span data-stu-id="e7e3a-142">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="e7e3a-143">CustomerTI</span><span class="sxs-lookup"><span data-stu-id="e7e3a-143">CustomerTI</span></span> |  <span data-ttu-id="e7e3a-144">Ti personalizzato</span><span class="sxs-lookup"><span data-stu-id="e7e3a-144">Custom TI</span></span> | <span data-ttu-id="e7e3a-145">Rebranding</span><span class="sxs-lookup"><span data-stu-id="e7e3a-145">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="e7e3a-146">OfficeATP</span><span class="sxs-lookup"><span data-stu-id="e7e3a-146">OfficeATP</span></span> | <span data-ttu-id="e7e3a-147">Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="e7e3a-147">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="e7e3a-148">Rebranding</span><span class="sxs-lookup"><span data-stu-id="e7e3a-148">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="e7e3a-149">MTP</span><span class="sxs-lookup"><span data-stu-id="e7e3a-149">MTP</span></span>   | <span data-ttu-id="e7e3a-150">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e7e3a-150">Microsoft 365 Defender</span></span> | <span data-ttu-id="e7e3a-151">Rebranding</span><span class="sxs-lookup"><span data-stu-id="e7e3a-151">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="e7e3a-152">AzureATP</span><span class="sxs-lookup"><span data-stu-id="e7e3a-152">AzureATP</span></span> |    <span data-ttu-id="e7e3a-153">Microsoft Defender per identità</span><span class="sxs-lookup"><span data-stu-id="e7e3a-153">Microsoft Defender for Identity</span></span> | <span data-ttu-id="e7e3a-154">Rebranding</span><span class="sxs-lookup"><span data-stu-id="e7e3a-154">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="e7e3a-155">CustomDetection</span><span class="sxs-lookup"><span data-stu-id="e7e3a-155">CustomDetection</span></span>   | <span data-ttu-id="e7e3a-156">Rilevamento personalizzato</span><span class="sxs-lookup"><span data-stu-id="e7e3a-156">Custom detection</span></span> | <span data-ttu-id="e7e3a-157">Rebranding</span><span class="sxs-lookup"><span data-stu-id="e7e3a-157">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="e7e3a-158">AutomatedInvestigation</span><span class="sxs-lookup"><span data-stu-id="e7e3a-158">AutomatedInvestigation</span></span> |<span data-ttu-id="e7e3a-159">Indagine automatizzata</span><span class="sxs-lookup"><span data-stu-id="e7e3a-159">Automated investigation</span></span> | <span data-ttu-id="e7e3a-160">Rebranding</span><span class="sxs-lookup"><span data-stu-id="e7e3a-160">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="e7e3a-161">ThreatExperts</span><span class="sxs-lookup"><span data-stu-id="e7e3a-161">ThreatExperts</span></span> | <span data-ttu-id="e7e3a-162">Microsoft Threat Experts</span><span class="sxs-lookup"><span data-stu-id="e7e3a-162">Microsoft Threat Experts</span></span> | <span data-ttu-id="e7e3a-163">Rebranding</span><span class="sxs-lookup"><span data-stu-id="e7e3a-163">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="e7e3a-164">TI di terze parti</span><span class="sxs-lookup"><span data-stu-id="e7e3a-164">3rd party TI</span></span> | <span data-ttu-id="e7e3a-165">Sensori di terze parti</span><span class="sxs-lookup"><span data-stu-id="e7e3a-165">3rd Party sensors</span></span> | <span data-ttu-id="e7e3a-166">Rebranding</span><span class="sxs-lookup"><span data-stu-id="e7e3a-166">Rebranding</span></span> |
| `ServiceSource` | <span data-ttu-id="e7e3a-167">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="e7e3a-167">Microsoft Defender ATP</span></span>| <span data-ttu-id="e7e3a-168">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="e7e3a-168">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="e7e3a-169">Rebranding</span><span class="sxs-lookup"><span data-stu-id="e7e3a-169">Rebranding</span></span> |
|`ServiceSource` |<span data-ttu-id="e7e3a-170">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="e7e3a-170">Microsoft Threat Protection</span></span>   | <span data-ttu-id="e7e3a-171">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e7e3a-171">Microsoft 365 Defender</span></span> | <span data-ttu-id="e7e3a-172">Rebranding</span><span class="sxs-lookup"><span data-stu-id="e7e3a-172">Rebranding</span></span> |
| `ServiceSource` | <span data-ttu-id="e7e3a-173">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="e7e3a-173">Office 365 ATP</span></span>  |<span data-ttu-id="e7e3a-174">Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="e7e3a-174">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="e7e3a-175">Rebranding</span><span class="sxs-lookup"><span data-stu-id="e7e3a-175">Rebranding</span></span> |
| `ServiceSource` |<span data-ttu-id="e7e3a-176">Azure ATP</span><span class="sxs-lookup"><span data-stu-id="e7e3a-176">Azure ATP</span></span>    |<span data-ttu-id="e7e3a-177">Microsoft Defender per identità</span><span class="sxs-lookup"><span data-stu-id="e7e3a-177">Microsoft Defender for Identity</span></span> | <span data-ttu-id="e7e3a-178">Rebranding</span><span class="sxs-lookup"><span data-stu-id="e7e3a-178">Rebranding</span></span> |

<span data-ttu-id="e7e3a-179">`DetectionSource`è disponibile nella [tabella AlertInfo.](advanced-hunting-alertinfo-table.md)</span><span class="sxs-lookup"><span data-stu-id="e7e3a-179">`DetectionSource` is available in the [AlertInfo](advanced-hunting-alertinfo-table.md) table.</span></span> <span data-ttu-id="e7e3a-180">`ServiceSource`è disponibile nelle [tabelle AlertEvidence](advanced-hunting-alertevidence-table.md) [e AlertInfo.](advanced-hunting-alertinfo-table.md)</span><span class="sxs-lookup"><span data-stu-id="e7e3a-180">`ServiceSource` is available in the [AlertEvidence](advanced-hunting-alertevidence-table.md) and [AlertInfo](advanced-hunting-alertinfo-table.md) tables.</span></span> 

## <a name="february-2021"></a><span data-ttu-id="e7e3a-181">Febbraio 2021</span><span class="sxs-lookup"><span data-stu-id="e7e3a-181">February 2021</span></span>

1. <span data-ttu-id="e7e3a-182">Nelle tabelle [EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) [e EmailEvents](advanced-hunting-emailevents-table.md) le colonne e sono `MalwareFilterVerdict` state `PhishFilterVerdict` sostituite dalla `ThreatTypes` colonna.</span><span class="sxs-lookup"><span data-stu-id="e7e3a-182">In the [EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) and [EmailEvents](advanced-hunting-emailevents-table.md) tables, the `MalwareFilterVerdict`and `PhishFilterVerdict` columns have been replaced by the `ThreatTypes` column.</span></span> <span data-ttu-id="e7e3a-183">Anche `MalwareDetectionMethod` le colonne e sono state `PhishDetectionMethod` sostituite dalla `DetectionMethods` colonna.</span><span class="sxs-lookup"><span data-stu-id="e7e3a-183">The `MalwareDetectionMethod` and `PhishDetectionMethod` columns were also replaced by the `DetectionMethods` column.</span></span> <span data-ttu-id="e7e3a-184">Questa struttura consente di fornire ulteriori informazioni nelle nuove colonne.</span><span class="sxs-lookup"><span data-stu-id="e7e3a-184">This streamlining allows us to provide more information under the new columns.</span></span> <span data-ttu-id="e7e3a-185">Il mapping viene fornito di seguito.</span><span class="sxs-lookup"><span data-stu-id="e7e3a-185">The mapping is provided below.</span></span>

| <span data-ttu-id="e7e3a-186">Nome della tabella</span><span class="sxs-lookup"><span data-stu-id="e7e3a-186">Table name</span></span> | <span data-ttu-id="e7e3a-187">Nome colonna originale</span><span class="sxs-lookup"><span data-stu-id="e7e3a-187">Original column name</span></span> | <span data-ttu-id="e7e3a-188">Nome nuova colonna</span><span class="sxs-lookup"><span data-stu-id="e7e3a-188">New column name</span></span> | <span data-ttu-id="e7e3a-189">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="e7e3a-189">Reason for change</span></span>
|--|--|--|--|
| `EmailAttachmentInfo` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | <span data-ttu-id="e7e3a-190">Includere altri metodi di rilevamento</span><span class="sxs-lookup"><span data-stu-id="e7e3a-190">Include more detection methods</span></span> |
| `EmailAttachmentInfo`  | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | <span data-ttu-id="e7e3a-191">Includere altri tipi di minacce</span><span class="sxs-lookup"><span data-stu-id="e7e3a-191">Include more threat types</span></span> |
| `EmailEvents` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | <span data-ttu-id="e7e3a-192">Includere altri metodi di rilevamento</span><span class="sxs-lookup"><span data-stu-id="e7e3a-192">Include more detection methods</span></span> |
| `EmailEvents` | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | <span data-ttu-id="e7e3a-193">Includere altri tipi di minacce</span><span class="sxs-lookup"><span data-stu-id="e7e3a-193">Include more threat types</span></span> |


2. <span data-ttu-id="e7e3a-194">Nelle tabelle `EmailAttachmentInfo` e , la colonna è stata aggiunta per fornire ulteriori informazioni sulla minaccia di posta `EmailEvents` `ThreatNames` elettronica.</span><span class="sxs-lookup"><span data-stu-id="e7e3a-194">In the `EmailAttachmentInfo` and `EmailEvents` tables, the `ThreatNames` column was added to give more information about the email threat.</span></span> <span data-ttu-id="e7e3a-195">Questa colonna contiene valori come Spam o Phish.</span><span class="sxs-lookup"><span data-stu-id="e7e3a-195">This column contains values like Spam or Phish.</span></span>

3. <span data-ttu-id="e7e3a-196">Nella tabella [DeviceInfo](advanced-hunting-deviceinfo-table.md) la colonna `DeviceObjectId` è stata sostituita dalla `AadDeviceId` colonna in base al feedback dei clienti.</span><span class="sxs-lookup"><span data-stu-id="e7e3a-196">In the [DeviceInfo](advanced-hunting-deviceinfo-table.md) table, the `DeviceObjectId` column was replaced by the `AadDeviceId` column based on customer feedback.</span></span>

4. <span data-ttu-id="e7e3a-197">Nella tabella [DeviceEvents](advanced-hunting-deviceevents-table.md) sono stati modificati diversi nomi ActionType per riflettere meglio la descrizione dell'azione.</span><span class="sxs-lookup"><span data-stu-id="e7e3a-197">In the [DeviceEvents](advanced-hunting-deviceevents-table.md) table, several ActionType names were modified to better reflect the description of the action.</span></span> <span data-ttu-id="e7e3a-198">I dettagli delle modifiche sono disponibili di seguito.</span><span class="sxs-lookup"><span data-stu-id="e7e3a-198">Details of the changes can be found below.</span></span>

| <span data-ttu-id="e7e3a-199">Nome della tabella</span><span class="sxs-lookup"><span data-stu-id="e7e3a-199">Table name</span></span> | <span data-ttu-id="e7e3a-200">Nome ActionType originale</span><span class="sxs-lookup"><span data-stu-id="e7e3a-200">Original ActionType name</span></span> | <span data-ttu-id="e7e3a-201">Nuovo nome ActionType</span><span class="sxs-lookup"><span data-stu-id="e7e3a-201">New ActionType name</span></span> | <span data-ttu-id="e7e3a-202">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="e7e3a-202">Reason for change</span></span>
|--|--|--|--|
| `DeviceEvents` | `DlpPocPrintJob` | `FilePrinted` | <span data-ttu-id="e7e3a-203">Feedback dei clienti</span><span class="sxs-lookup"><span data-stu-id="e7e3a-203">Customer feedback</span></span> |
| `DeviceEvents` | `UsbDriveMount` | `UsbDriveMounted` | <span data-ttu-id="e7e3a-204">Feedback dei clienti</span><span class="sxs-lookup"><span data-stu-id="e7e3a-204">Customer feedback</span></span> |
| `DeviceEvents` | `UsbDriveUnmount` | `UsbDriveUnmounted` | <span data-ttu-id="e7e3a-205">Feedback dei clienti</span><span class="sxs-lookup"><span data-stu-id="e7e3a-205">Customer feedback</span></span> |
| `DeviceEvents` | `WriteProcessMemoryApiCall` | `WriteToLsassProcessMemory` | <span data-ttu-id="e7e3a-206">Feedback dei clienti</span><span class="sxs-lookup"><span data-stu-id="e7e3a-206">Customer feedback</span></span> |






## <a name="related-topics"></a><span data-ttu-id="e7e3a-207">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="e7e3a-207">Related topics</span></span>
- [<span data-ttu-id="e7e3a-208">Panoramica della rilevazione avanzata</span><span class="sxs-lookup"><span data-stu-id="e7e3a-208">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="e7e3a-209">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="e7e3a-209">Understand the schema</span></span>](advanced-hunting-schema-tables.md)