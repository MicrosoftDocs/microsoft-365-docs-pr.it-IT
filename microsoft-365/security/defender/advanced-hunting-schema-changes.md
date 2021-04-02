---
title: Modifiche di denominazione nello schema di ricerca avanzata di Microsoft 365 Defender
description: Tenere traccia e rivedere le tabelle e le colonne delle modifiche di denominazione nello schema di ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, protezione dalle minacce Microsoft, Microsoft 365, mtp, m365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, dati, modifiche di denominazione, rinominare, Microsoft Threat Protection
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
ms.openlocfilehash: ab6bdefb457fb31df98d829ee801b72f4c8ae70a
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499696"
---
# <a name="advanced-hunting-schema---naming-changes"></a><span data-ttu-id="07525-104">Schema di ricerca avanzata - Modifiche di denominazione</span><span class="sxs-lookup"><span data-stu-id="07525-104">Advanced hunting schema - Naming changes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="07525-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="07525-105">**Applies to:**</span></span>
- <span data-ttu-id="07525-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="07525-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="07525-107">Lo [schema di ricerca](advanced-hunting-schema-tables.md) avanzata viene aggiornato regolarmente per aggiungere nuove tabelle e colonne.</span><span class="sxs-lookup"><span data-stu-id="07525-107">The [advanced hunting schema](advanced-hunting-schema-tables.md) is updated regularly to add new tables and columns.</span></span> <span data-ttu-id="07525-108">In alcuni casi, i nomi delle colonne esistenti vengono rinominati o sostituiti per migliorare l'esperienza utente.</span><span class="sxs-lookup"><span data-stu-id="07525-108">In some cases, existing columns names are renamed or replaced to improve the user experience.</span></span> <span data-ttu-id="07525-109">Fare riferimento a questo articolo per esaminare le modifiche di denominazione che potrebbero influire sulle query.</span><span class="sxs-lookup"><span data-stu-id="07525-109">Refer to this article to review naming changes that could impact your queries.</span></span>

<span data-ttu-id="07525-110">Le modifiche di denominazione vengono applicate automaticamente alle query salvate nel Centro sicurezza, incluse le query utilizzate dalle regole di rilevamento personalizzate.</span><span class="sxs-lookup"><span data-stu-id="07525-110">Naming changes are automatically applied to queries that are saved in the security center, including queries used by custom detection rules.</span></span> <span data-ttu-id="07525-111">Non è necessario aggiornare manualmente queste query.</span><span class="sxs-lookup"><span data-stu-id="07525-111">You don't need to update these queries manually.</span></span> <span data-ttu-id="07525-112">Sarà tuttavia necessario aggiornare le query seguenti:</span><span class="sxs-lookup"><span data-stu-id="07525-112">However, you will need to update the following queries:</span></span>
- <span data-ttu-id="07525-113">Query eseguite con l'API</span><span class="sxs-lookup"><span data-stu-id="07525-113">Queries that are run using the API</span></span>
- <span data-ttu-id="07525-114">Query salvate altrove all'esterno del Centro sicurezza</span><span class="sxs-lookup"><span data-stu-id="07525-114">Queries that are saved elsewhere outside the security center</span></span>

## <a name="december-2020"></a><span data-ttu-id="07525-115">Dicembre 2020</span><span class="sxs-lookup"><span data-stu-id="07525-115">December 2020</span></span>

| <span data-ttu-id="07525-116">Nome della tabella</span><span class="sxs-lookup"><span data-stu-id="07525-116">Table name</span></span> | <span data-ttu-id="07525-117">Nome colonna originale</span><span class="sxs-lookup"><span data-stu-id="07525-117">Original column name</span></span> | <span data-ttu-id="07525-118">Nome nuova colonna</span><span class="sxs-lookup"><span data-stu-id="07525-118">New column name</span></span> | <span data-ttu-id="07525-119">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="07525-119">Reason for change</span></span>
|--|--|--|--|
| [<span data-ttu-id="07525-120">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="07525-120">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailAction` | `EmailAction` | <span data-ttu-id="07525-121">Feedback dei clienti</span><span class="sxs-lookup"><span data-stu-id="07525-121">Customer feedback</span></span> |
| [<span data-ttu-id="07525-122">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="07525-122">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicy` | `EmailActionPolicy` | <span data-ttu-id="07525-123">Feedback dei clienti</span><span class="sxs-lookup"><span data-stu-id="07525-123">Customer feedback</span></span> |
| [<span data-ttu-id="07525-124">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="07525-124">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicyGuid` | `EmailActionPolicyGuid` | <span data-ttu-id="07525-125">Feedback dei clienti</span><span class="sxs-lookup"><span data-stu-id="07525-125">Customer feedback</span></span> |

## <a name="january-2021"></a><span data-ttu-id="07525-126">Gennaio 2021</span><span class="sxs-lookup"><span data-stu-id="07525-126">January 2021</span></span>

| <span data-ttu-id="07525-127">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="07525-127">Column name</span></span> | <span data-ttu-id="07525-128">Nome valore originale</span><span class="sxs-lookup"><span data-stu-id="07525-128">Original value name</span></span> | <span data-ttu-id="07525-129">Nuovo nome valore</span><span class="sxs-lookup"><span data-stu-id="07525-129">New value name</span></span> | <span data-ttu-id="07525-130">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="07525-130">Reason for change</span></span>
|--|--|--|--|
| `DetectionSource` | <span data-ttu-id="07525-131">MCAS</span><span class="sxs-lookup"><span data-stu-id="07525-131">MCAS</span></span> |    <span data-ttu-id="07525-132">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="07525-132">Microsoft Cloud App Security</span></span> | <span data-ttu-id="07525-133">Rebranding</span><span class="sxs-lookup"><span data-stu-id="07525-133">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="07525-134">WindowsDefenderAtp</span><span class="sxs-lookup"><span data-stu-id="07525-134">WindowsDefenderAtp</span></span>|   <span data-ttu-id="07525-135">EDR</span><span class="sxs-lookup"><span data-stu-id="07525-135">EDR</span></span>| <span data-ttu-id="07525-136">Rebranding</span><span class="sxs-lookup"><span data-stu-id="07525-136">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="07525-137">WindowsDefenderAv</span><span class="sxs-lookup"><span data-stu-id="07525-137">WindowsDefenderAv</span></span> | <span data-ttu-id="07525-138">Antivirus</span><span class="sxs-lookup"><span data-stu-id="07525-138">Antivirus</span></span> | <span data-ttu-id="07525-139">Rebranding</span><span class="sxs-lookup"><span data-stu-id="07525-139">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="07525-140">WindowsDefenderSmartScreen</span><span class="sxs-lookup"><span data-stu-id="07525-140">WindowsDefenderSmartScreen</span></span> |  <span data-ttu-id="07525-141">SmartScreen</span><span class="sxs-lookup"><span data-stu-id="07525-141">SmartScreen</span></span> | <span data-ttu-id="07525-142">Rebranding</span><span class="sxs-lookup"><span data-stu-id="07525-142">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="07525-143">CustomerTI</span><span class="sxs-lookup"><span data-stu-id="07525-143">CustomerTI</span></span> |  <span data-ttu-id="07525-144">Ti personalizzato</span><span class="sxs-lookup"><span data-stu-id="07525-144">Custom TI</span></span> | <span data-ttu-id="07525-145">Rebranding</span><span class="sxs-lookup"><span data-stu-id="07525-145">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="07525-146">OfficeATP</span><span class="sxs-lookup"><span data-stu-id="07525-146">OfficeATP</span></span> | <span data-ttu-id="07525-147">Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="07525-147">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="07525-148">Rebranding</span><span class="sxs-lookup"><span data-stu-id="07525-148">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="07525-149">MTP</span><span class="sxs-lookup"><span data-stu-id="07525-149">MTP</span></span>   | <span data-ttu-id="07525-150">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="07525-150">Microsoft 365 Defender</span></span> | <span data-ttu-id="07525-151">Rebranding</span><span class="sxs-lookup"><span data-stu-id="07525-151">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="07525-152">AzureATP</span><span class="sxs-lookup"><span data-stu-id="07525-152">AzureATP</span></span> |    <span data-ttu-id="07525-153">Che cosa è Microsoft Defender per identità?</span><span class="sxs-lookup"><span data-stu-id="07525-153">Microsoft Defender for Identity</span></span> | <span data-ttu-id="07525-154">Rebranding</span><span class="sxs-lookup"><span data-stu-id="07525-154">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="07525-155">CustomDetection</span><span class="sxs-lookup"><span data-stu-id="07525-155">CustomDetection</span></span>   | <span data-ttu-id="07525-156">Rilevamento personalizzato</span><span class="sxs-lookup"><span data-stu-id="07525-156">Custom detection</span></span> | <span data-ttu-id="07525-157">Rebranding</span><span class="sxs-lookup"><span data-stu-id="07525-157">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="07525-158">AutomatedInvestigation</span><span class="sxs-lookup"><span data-stu-id="07525-158">AutomatedInvestigation</span></span> |<span data-ttu-id="07525-159">Indagine automatizzata</span><span class="sxs-lookup"><span data-stu-id="07525-159">Automated investigation</span></span> | <span data-ttu-id="07525-160">Rebranding</span><span class="sxs-lookup"><span data-stu-id="07525-160">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="07525-161">ThreatExperts</span><span class="sxs-lookup"><span data-stu-id="07525-161">ThreatExperts</span></span> | <span data-ttu-id="07525-162">Microsoft Threat Experts</span><span class="sxs-lookup"><span data-stu-id="07525-162">Microsoft Threat Experts</span></span> | <span data-ttu-id="07525-163">Rebranding</span><span class="sxs-lookup"><span data-stu-id="07525-163">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="07525-164">TI di terze parti</span><span class="sxs-lookup"><span data-stu-id="07525-164">3rd party TI</span></span> | <span data-ttu-id="07525-165">Sensori di terze parti</span><span class="sxs-lookup"><span data-stu-id="07525-165">3rd Party sensors</span></span> | <span data-ttu-id="07525-166">Rebranding</span><span class="sxs-lookup"><span data-stu-id="07525-166">Rebranding</span></span> |
| `ServiceSource` | <span data-ttu-id="07525-167">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="07525-167">Microsoft Defender ATP</span></span>| <span data-ttu-id="07525-168">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="07525-168">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="07525-169">Rebranding</span><span class="sxs-lookup"><span data-stu-id="07525-169">Rebranding</span></span> |
|`ServiceSource` |<span data-ttu-id="07525-170">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="07525-170">Microsoft Threat Protection</span></span>   | <span data-ttu-id="07525-171">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="07525-171">Microsoft 365 Defender</span></span> | <span data-ttu-id="07525-172">Rebranding</span><span class="sxs-lookup"><span data-stu-id="07525-172">Rebranding</span></span> |
| `ServiceSource` | <span data-ttu-id="07525-173">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="07525-173">Office 365 ATP</span></span>  |<span data-ttu-id="07525-174">Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="07525-174">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="07525-175">Rebranding</span><span class="sxs-lookup"><span data-stu-id="07525-175">Rebranding</span></span> |
| `ServiceSource` |<span data-ttu-id="07525-176">Azure ATP</span><span class="sxs-lookup"><span data-stu-id="07525-176">Azure ATP</span></span>    |<span data-ttu-id="07525-177">Che cosa è Microsoft Defender per identità?</span><span class="sxs-lookup"><span data-stu-id="07525-177">Microsoft Defender for Identity</span></span> | <span data-ttu-id="07525-178">Rebranding</span><span class="sxs-lookup"><span data-stu-id="07525-178">Rebranding</span></span> |

<span data-ttu-id="07525-179">`DetectionSource`è disponibile nella [tabella AlertInfo.](advanced-hunting-alertinfo-table.md)</span><span class="sxs-lookup"><span data-stu-id="07525-179">`DetectionSource` is available in the [AlertInfo](advanced-hunting-alertinfo-table.md) table.</span></span> <span data-ttu-id="07525-180">`ServiceSource`è disponibile nelle [tabelle AlertEvidence](advanced-hunting-alertevidence-table.md) [e AlertInfo.](advanced-hunting-alertinfo-table.md)</span><span class="sxs-lookup"><span data-stu-id="07525-180">`ServiceSource` is available in the [AlertEvidence](advanced-hunting-alertevidence-table.md) and [AlertInfo](advanced-hunting-alertinfo-table.md) tables.</span></span> 

## <a name="february-2021"></a><span data-ttu-id="07525-181">Febbraio 2021</span><span class="sxs-lookup"><span data-stu-id="07525-181">February 2021</span></span>

1. <span data-ttu-id="07525-182">Nelle tabelle [EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) [e EmailEvents](advanced-hunting-emailevents-table.md) le colonne e sono `MalwareFilterVerdict` state `PhishFilterVerdict` sostituite dalla `ThreatTypes` colonna.</span><span class="sxs-lookup"><span data-stu-id="07525-182">In the [EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) and [EmailEvents](advanced-hunting-emailevents-table.md) tables, the `MalwareFilterVerdict`and `PhishFilterVerdict` columns have been replaced by the `ThreatTypes` column.</span></span> <span data-ttu-id="07525-183">Anche `MalwareDetectionMethod` le colonne e sono state `PhishDetectionMethod` sostituite dalla `DetectionMethods` colonna.</span><span class="sxs-lookup"><span data-stu-id="07525-183">The `MalwareDetectionMethod` and `PhishDetectionMethod` columns were also replaced by the `DetectionMethods` column.</span></span> <span data-ttu-id="07525-184">Questa struttura consente di fornire ulteriori informazioni nelle nuove colonne.</span><span class="sxs-lookup"><span data-stu-id="07525-184">This streamlining allows us to provide more information under the new columns.</span></span> <span data-ttu-id="07525-185">Il mapping viene fornito di seguito.</span><span class="sxs-lookup"><span data-stu-id="07525-185">The mapping is provided below.</span></span>

| <span data-ttu-id="07525-186">Nome della tabella</span><span class="sxs-lookup"><span data-stu-id="07525-186">Table name</span></span> | <span data-ttu-id="07525-187">Nome colonna originale</span><span class="sxs-lookup"><span data-stu-id="07525-187">Original column name</span></span> | <span data-ttu-id="07525-188">Nome nuova colonna</span><span class="sxs-lookup"><span data-stu-id="07525-188">New column name</span></span> | <span data-ttu-id="07525-189">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="07525-189">Reason for change</span></span>
|--|--|--|--|
| `EmailAttachmentInfo` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | <span data-ttu-id="07525-190">Includere altri metodi di rilevamento</span><span class="sxs-lookup"><span data-stu-id="07525-190">Include more detection methods</span></span> |
| `EmailAttachmentInfo`  | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | <span data-ttu-id="07525-191">Includere altri tipi di minacce</span><span class="sxs-lookup"><span data-stu-id="07525-191">Include more threat types</span></span> |
| `EmailEvents` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | <span data-ttu-id="07525-192">Includere altri metodi di rilevamento</span><span class="sxs-lookup"><span data-stu-id="07525-192">Include more detection methods</span></span> |
| `EmailEvents` | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | <span data-ttu-id="07525-193">Includere altri tipi di minacce</span><span class="sxs-lookup"><span data-stu-id="07525-193">Include more threat types</span></span> |


2. <span data-ttu-id="07525-194">Nelle tabelle `EmailAttachmentInfo` e , la colonna è stata aggiunta per fornire ulteriori informazioni sulla minaccia di posta `EmailEvents` `ThreatNames` elettronica.</span><span class="sxs-lookup"><span data-stu-id="07525-194">In the `EmailAttachmentInfo` and `EmailEvents` tables, the `ThreatNames` column was added to give more information about the email threat.</span></span> <span data-ttu-id="07525-195">Questa colonna contiene valori come Spam o Phish.</span><span class="sxs-lookup"><span data-stu-id="07525-195">This column contains values like Spam or Phish.</span></span>

3. <span data-ttu-id="07525-196">Nella tabella [DeviceInfo](advanced-hunting-deviceinfo-table.md) la colonna `DeviceObjectId` è stata sostituita dalla `AadDeviceId` colonna in base al feedback dei clienti.</span><span class="sxs-lookup"><span data-stu-id="07525-196">In the [DeviceInfo](advanced-hunting-deviceinfo-table.md) table, the `DeviceObjectId` column was replaced by the `AadDeviceId` column based on customer feedback.</span></span>

4. <span data-ttu-id="07525-197">Nella tabella [DeviceEvents](advanced-hunting-deviceevents-table.md) sono stati modificati diversi nomi ActionType per riflettere meglio la descrizione dell'azione.</span><span class="sxs-lookup"><span data-stu-id="07525-197">In the [DeviceEvents](advanced-hunting-deviceevents-table.md) table, several ActionType names were modified to better reflect the description of the action.</span></span> <span data-ttu-id="07525-198">I dettagli delle modifiche sono disponibili di seguito.</span><span class="sxs-lookup"><span data-stu-id="07525-198">Details of the changes can be found below.</span></span>

| <span data-ttu-id="07525-199">Nome della tabella</span><span class="sxs-lookup"><span data-stu-id="07525-199">Table name</span></span> | <span data-ttu-id="07525-200">Nome ActionType originale</span><span class="sxs-lookup"><span data-stu-id="07525-200">Original ActionType name</span></span> | <span data-ttu-id="07525-201">Nuovo nome ActionType</span><span class="sxs-lookup"><span data-stu-id="07525-201">New ActionType name</span></span> | <span data-ttu-id="07525-202">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="07525-202">Reason for change</span></span>
|--|--|--|--|
| `DeviceEvents` | `DlpPocPrintJob` | `FilePrinted` | <span data-ttu-id="07525-203">Feedback dei clienti</span><span class="sxs-lookup"><span data-stu-id="07525-203">Customer feedback</span></span> |
| `DeviceEvents` | `UsbDriveMount` | `UsbDriveMounted` | <span data-ttu-id="07525-204">Feedback dei clienti</span><span class="sxs-lookup"><span data-stu-id="07525-204">Customer feedback</span></span> |
| `DeviceEvents` | `UsbDriveUnmount` | `UsbDriveUnmounted` | <span data-ttu-id="07525-205">Feedback dei clienti</span><span class="sxs-lookup"><span data-stu-id="07525-205">Customer feedback</span></span> |
| `DeviceEvents` | `WriteProcessMemoryApiCall` | `WriteToLsassProcessMemory` | <span data-ttu-id="07525-206">Feedback dei clienti</span><span class="sxs-lookup"><span data-stu-id="07525-206">Customer feedback</span></span> |






## <a name="related-topics"></a><span data-ttu-id="07525-207">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="07525-207">Related topics</span></span>
- [<span data-ttu-id="07525-208">Panoramica della rilevazione avanzata</span><span class="sxs-lookup"><span data-stu-id="07525-208">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="07525-209">Comprensione dello schema</span><span class="sxs-lookup"><span data-stu-id="07525-209">Understand the schema</span></span>](advanced-hunting-schema-tables.md)