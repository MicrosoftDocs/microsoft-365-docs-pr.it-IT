---
title: API Per ottenere avvisi
description: Informazioni sui metodi e le proprietà del tipo di risorsa Avviso in Microsoft Defender per Endpoint.
keywords: api, api del grafico, api supportate, ottenere, avvisi, recenti
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: c935df1abddc3d0ebee74e09280d6e3ec961ca97
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769810"
---
# <a name="alert-resource-type"></a><span data-ttu-id="cfcf5-104">Tipo di risorsa avviso</span><span class="sxs-lookup"><span data-stu-id="cfcf5-104">Alert resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="cfcf5-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="cfcf5-105">**Applies to:**</span></span>
- [<span data-ttu-id="cfcf5-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="cfcf5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

- <span data-ttu-id="cfcf5-107">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="cfcf5-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="cfcf5-108">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="cfcf5-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="methods"></a><span data-ttu-id="cfcf5-109">Metodi</span><span class="sxs-lookup"><span data-stu-id="cfcf5-109">Methods</span></span>

<span data-ttu-id="cfcf5-110">Metodo</span><span class="sxs-lookup"><span data-stu-id="cfcf5-110">Method</span></span> |<span data-ttu-id="cfcf5-111">Tipo restituito</span><span class="sxs-lookup"><span data-stu-id="cfcf5-111">Return Type</span></span> |<span data-ttu-id="cfcf5-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cfcf5-112">Description</span></span>
:---|:---|:---
[<span data-ttu-id="cfcf5-113">Ottenere un avviso</span><span class="sxs-lookup"><span data-stu-id="cfcf5-113">Get alert</span></span>](get-alert-info-by-id.md) | [<span data-ttu-id="cfcf5-114">Avviso</span><span class="sxs-lookup"><span data-stu-id="cfcf5-114">Alert</span></span>](alerts.md) | <span data-ttu-id="cfcf5-115">Ottenere un singolo [oggetto](alerts.md) avviso.</span><span class="sxs-lookup"><span data-stu-id="cfcf5-115">Get a single [alert](alerts.md) object.</span></span>
[<span data-ttu-id="cfcf5-116">Elencare avvisi</span><span class="sxs-lookup"><span data-stu-id="cfcf5-116">List alerts</span></span>](get-alerts.md) | <span data-ttu-id="cfcf5-117">[Raccolta avvisi](alerts.md)</span><span class="sxs-lookup"><span data-stu-id="cfcf5-117">[Alert](alerts.md) collection</span></span> | <span data-ttu-id="cfcf5-118">Raccolta [avvisi elenco.](alerts.md)</span><span class="sxs-lookup"><span data-stu-id="cfcf5-118">List [alert](alerts.md) collection.</span></span>
[<span data-ttu-id="cfcf5-119">Avviso di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="cfcf5-119">Update alert</span></span>](update-alert.md) | [<span data-ttu-id="cfcf5-120">Avviso</span><span class="sxs-lookup"><span data-stu-id="cfcf5-120">Alert</span></span>](alerts.md) | <span data-ttu-id="cfcf5-121">Aggiorna avviso [specifico](alerts.md).</span><span class="sxs-lookup"><span data-stu-id="cfcf5-121">Update specific [alert](alerts.md).</span></span>
[<span data-ttu-id="cfcf5-122">Avvisi di aggiornamento in batch</span><span class="sxs-lookup"><span data-stu-id="cfcf5-122">Batch update alerts</span></span>](batch-update-alerts.md) | | <span data-ttu-id="cfcf5-123">Aggiornare un batch di [avvisi](alerts.md).</span><span class="sxs-lookup"><span data-stu-id="cfcf5-123">Update a batch of [alerts](alerts.md).</span></span>
[<span data-ttu-id="cfcf5-124">Creare un avviso</span><span class="sxs-lookup"><span data-stu-id="cfcf5-124">Create alert</span></span>](create-alert-by-reference.md)|[<span data-ttu-id="cfcf5-125">Avviso</span><span class="sxs-lookup"><span data-stu-id="cfcf5-125">Alert</span></span>](alerts.md)|<span data-ttu-id="cfcf5-126">Crea un avviso in base ai dati dell'evento ottenuti da [Advanced Hunting.](run-advanced-query-api.md)</span><span class="sxs-lookup"><span data-stu-id="cfcf5-126">Create an alert based on event data obtained from [Advanced Hunting](run-advanced-query-api.md).</span></span>
[<span data-ttu-id="cfcf5-127">Elencare i domini correlati</span><span class="sxs-lookup"><span data-stu-id="cfcf5-127">List related domains</span></span>](get-alert-related-domain-info.md)|<span data-ttu-id="cfcf5-128">Raccolta di domini</span><span class="sxs-lookup"><span data-stu-id="cfcf5-128">Domain collection</span></span>| <span data-ttu-id="cfcf5-129">Url elenco associati all'avviso.</span><span class="sxs-lookup"><span data-stu-id="cfcf5-129">List URLs associated with the alert.</span></span>
[<span data-ttu-id="cfcf5-130">Elencare i file correlati</span><span class="sxs-lookup"><span data-stu-id="cfcf5-130">List related files</span></span>](get-alert-related-files-info.md) | <span data-ttu-id="cfcf5-131">[Raccolta file](files.md)</span><span class="sxs-lookup"><span data-stu-id="cfcf5-131">[File](files.md) collection</span></span> |  <span data-ttu-id="cfcf5-132">Elencare [le entità](files.md) file associate all'avviso . [](alerts.md)</span><span class="sxs-lookup"><span data-stu-id="cfcf5-132">List the [file](files.md) entities that are associated with the [alert](alerts.md).</span></span>
[<span data-ttu-id="cfcf5-133">Elenco indirizzi IP correlati</span><span class="sxs-lookup"><span data-stu-id="cfcf5-133">List related IPs</span></span>](get-alert-related-ip-info.md) | <span data-ttu-id="cfcf5-134">Raccolta IP</span><span class="sxs-lookup"><span data-stu-id="cfcf5-134">IP collection</span></span> | <span data-ttu-id="cfcf5-135">Elencare gli INDIRIZZI IP associati all'avviso.</span><span class="sxs-lookup"><span data-stu-id="cfcf5-135">List IPs that are associated with the alert.</span></span>
[<span data-ttu-id="cfcf5-136">Ottenere i computer correlati</span><span class="sxs-lookup"><span data-stu-id="cfcf5-136">Get related machines</span></span>](get-alert-related-machine-info.md) | [<span data-ttu-id="cfcf5-137">Computer</span><span class="sxs-lookup"><span data-stu-id="cfcf5-137">Machine</span></span>](machine.md) | <span data-ttu-id="cfcf5-138">Computer [associato](machine.md) [all'avviso](alerts.md).</span><span class="sxs-lookup"><span data-stu-id="cfcf5-138">The [machine](machine.md) that is associated with the [alert](alerts.md).</span></span>
[<span data-ttu-id="cfcf5-139">Ottenere utenti correlati</span><span class="sxs-lookup"><span data-stu-id="cfcf5-139">Get related users</span></span>](get-alert-related-user-info.md) | [<span data-ttu-id="cfcf5-140">Utente</span><span class="sxs-lookup"><span data-stu-id="cfcf5-140">User</span></span>](user.md) | <span data-ttu-id="cfcf5-141">[L'utente](user.md) associato [all'avviso](alerts.md).</span><span class="sxs-lookup"><span data-stu-id="cfcf5-141">The [user](user.md) that is associated with the [alert](alerts.md).</span></span>


## <a name="properties"></a><span data-ttu-id="cfcf5-142">Proprietà</span><span class="sxs-lookup"><span data-stu-id="cfcf5-142">Properties</span></span>

<span data-ttu-id="cfcf5-143">Proprietà</span><span class="sxs-lookup"><span data-stu-id="cfcf5-143">Property</span></span> |    <span data-ttu-id="cfcf5-144">Tipo</span><span class="sxs-lookup"><span data-stu-id="cfcf5-144">Type</span></span>    |    <span data-ttu-id="cfcf5-145">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cfcf5-145">Description</span></span>
:---|:---|:---
<span data-ttu-id="cfcf5-146">id</span><span class="sxs-lookup"><span data-stu-id="cfcf5-146">id</span></span> | <span data-ttu-id="cfcf5-147">Stringa</span><span class="sxs-lookup"><span data-stu-id="cfcf5-147">String</span></span> | <span data-ttu-id="cfcf5-148">ID avviso.</span><span class="sxs-lookup"><span data-stu-id="cfcf5-148">Alert ID.</span></span>
<span data-ttu-id="cfcf5-149">title</span><span class="sxs-lookup"><span data-stu-id="cfcf5-149">title</span></span> | <span data-ttu-id="cfcf5-150">Stringa</span><span class="sxs-lookup"><span data-stu-id="cfcf5-150">String</span></span> | <span data-ttu-id="cfcf5-151">Titolo dell'avviso.</span><span class="sxs-lookup"><span data-stu-id="cfcf5-151">Alert title.</span></span>
<span data-ttu-id="cfcf5-152">descrizione</span><span class="sxs-lookup"><span data-stu-id="cfcf5-152">description</span></span> | <span data-ttu-id="cfcf5-153">Stringa</span><span class="sxs-lookup"><span data-stu-id="cfcf5-153">String</span></span> | <span data-ttu-id="cfcf5-154">Descrizione dell'avviso.</span><span class="sxs-lookup"><span data-stu-id="cfcf5-154">Alert description.</span></span>
<span data-ttu-id="cfcf5-155">alertCreationTime</span><span class="sxs-lookup"><span data-stu-id="cfcf5-155">alertCreationTime</span></span> | <span data-ttu-id="cfcf5-156">Nullable DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="cfcf5-156">Nullable DateTimeOffset</span></span> | <span data-ttu-id="cfcf5-157">Data e ora (in UTC) in cui è stato creato l'avviso.</span><span class="sxs-lookup"><span data-stu-id="cfcf5-157">The date and time (in UTC) the alert was created.</span></span>
<span data-ttu-id="cfcf5-158">lastEventTime</span><span class="sxs-lookup"><span data-stu-id="cfcf5-158">lastEventTime</span></span> | <span data-ttu-id="cfcf5-159">Nullable DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="cfcf5-159">Nullable DateTimeOffset</span></span> | <span data-ttu-id="cfcf5-160">Ultima occorrenza dell'evento che ha attivato l'avviso sullo stesso dispositivo.</span><span class="sxs-lookup"><span data-stu-id="cfcf5-160">The last occurrence of the event that triggered the alert on the same device.</span></span>
<span data-ttu-id="cfcf5-161">firstEventTime</span><span class="sxs-lookup"><span data-stu-id="cfcf5-161">firstEventTime</span></span> | <span data-ttu-id="cfcf5-162">Nullable DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="cfcf5-162">Nullable DateTimeOffset</span></span> | <span data-ttu-id="cfcf5-163">Prima occorrenza dell'evento che ha attivato l'avviso nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="cfcf5-163">The first occurrence of the event that triggered the alert on that device.</span></span>
<span data-ttu-id="cfcf5-164">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="cfcf5-164">lastUpdateTime</span></span> | <span data-ttu-id="cfcf5-165">Nullable DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="cfcf5-165">Nullable DateTimeOffset</span></span> | <span data-ttu-id="cfcf5-166">Data e ora (in UTC) dell'ultimo aggiornamento dell'avviso.</span><span class="sxs-lookup"><span data-stu-id="cfcf5-166">The date and time (in UTC) the alert was last updated.</span></span>
<span data-ttu-id="cfcf5-167">resolvedTime</span><span class="sxs-lookup"><span data-stu-id="cfcf5-167">resolvedTime</span></span> | <span data-ttu-id="cfcf5-168">Nullable DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="cfcf5-168">Nullable DateTimeOffset</span></span> | <span data-ttu-id="cfcf5-169">Data e ora in cui lo stato dell'avviso è stato modificato in "Risolto".</span><span class="sxs-lookup"><span data-stu-id="cfcf5-169">The date and time in which the status of the alert was changed to 'Resolved'.</span></span>
<span data-ttu-id="cfcf5-170">incidentId</span><span class="sxs-lookup"><span data-stu-id="cfcf5-170">incidentId</span></span> | <span data-ttu-id="cfcf5-171">Nullable Long</span><span class="sxs-lookup"><span data-stu-id="cfcf5-171">Nullable Long</span></span> | <span data-ttu-id="cfcf5-172">ID [evento](view-incidents-queue.md) imprevisto dell'avviso.</span><span class="sxs-lookup"><span data-stu-id="cfcf5-172">The [Incident](view-incidents-queue.md) ID of the Alert.</span></span>
<span data-ttu-id="cfcf5-173">investigationId</span><span class="sxs-lookup"><span data-stu-id="cfcf5-173">investigationId</span></span> | <span data-ttu-id="cfcf5-174">Nullable Long</span><span class="sxs-lookup"><span data-stu-id="cfcf5-174">Nullable Long</span></span> | <span data-ttu-id="cfcf5-175">ID [dell'indagine](automated-investigations.md) correlato all'avviso.</span><span class="sxs-lookup"><span data-stu-id="cfcf5-175">The [Investigation](automated-investigations.md) ID related to the Alert.</span></span>
<span data-ttu-id="cfcf5-176">investigationState</span><span class="sxs-lookup"><span data-stu-id="cfcf5-176">investigationState</span></span> | <span data-ttu-id="cfcf5-177">Enumerazione Nullable</span><span class="sxs-lookup"><span data-stu-id="cfcf5-177">Nullable Enum</span></span> | <span data-ttu-id="cfcf5-178">Stato corrente dell'oggetto [Investigation.](automated-investigations.md)</span><span class="sxs-lookup"><span data-stu-id="cfcf5-178">The current state of the [Investigation](automated-investigations.md).</span></span> <span data-ttu-id="cfcf5-179">I valori possibili sono: "Unknown", "Terminated", 'SuccessfullyRemediated', 'Benign', 'Failed', 'PartiallyRemediated', 'Running', 'PendingApproval', 'PendingResource', 'PartiallyInvestigated', 'TerminatedByUser', 'TerminatedBySystem', 'Queued', 'InnerFailure', 'PreexistingAlert', 'UnsupportedOs', 'UnsupportedAlertType', 'SuppressedAlert'.</span><span class="sxs-lookup"><span data-stu-id="cfcf5-179">Possible values are: 'Unknown', 'Terminated', 'SuccessfullyRemediated', 'Benign', 'Failed', 'PartiallyRemediated', 'Running', 'PendingApproval', 'PendingResource', 'PartiallyInvestigated', 'TerminatedByUser', 'TerminatedBySystem', 'Queued', 'InnerFailure', 'PreexistingAlert', 'UnsupportedOs', 'UnsupportedAlertType', 'SuppressedAlert'.</span></span>
<span data-ttu-id="cfcf5-180">assignedTo</span><span class="sxs-lookup"><span data-stu-id="cfcf5-180">assignedTo</span></span> | <span data-ttu-id="cfcf5-181">Stringa</span><span class="sxs-lookup"><span data-stu-id="cfcf5-181">String</span></span> | <span data-ttu-id="cfcf5-182">Proprietario dell'avviso.</span><span class="sxs-lookup"><span data-stu-id="cfcf5-182">Owner of the alert.</span></span>
<span data-ttu-id="cfcf5-183">gravità</span><span class="sxs-lookup"><span data-stu-id="cfcf5-183">severity</span></span> | <span data-ttu-id="cfcf5-184">Enum</span><span class="sxs-lookup"><span data-stu-id="cfcf5-184">Enum</span></span> | <span data-ttu-id="cfcf5-185">Gravità dell'avviso.</span><span class="sxs-lookup"><span data-stu-id="cfcf5-185">Severity of the alert.</span></span> <span data-ttu-id="cfcf5-186">I valori possibili sono: 'UnSpecified', 'Informational', 'Low', 'Medium' e 'High'.</span><span class="sxs-lookup"><span data-stu-id="cfcf5-186">Possible values are: 'UnSpecified', 'Informational', 'Low', 'Medium' and 'High'.</span></span>
<span data-ttu-id="cfcf5-187">status</span><span class="sxs-lookup"><span data-stu-id="cfcf5-187">status</span></span> | <span data-ttu-id="cfcf5-188">Enum</span><span class="sxs-lookup"><span data-stu-id="cfcf5-188">Enum</span></span> | <span data-ttu-id="cfcf5-189">Specifica lo stato corrente dell'avviso.</span><span class="sxs-lookup"><span data-stu-id="cfcf5-189">Specifies the current status of the alert.</span></span> <span data-ttu-id="cfcf5-190">I valori possibili sono: 'Unknown', 'New', 'InProgress' e 'Resolved'.</span><span class="sxs-lookup"><span data-stu-id="cfcf5-190">Possible values are: 'Unknown', 'New', 'InProgress' and 'Resolved'.</span></span>
<span data-ttu-id="cfcf5-191">classificazione</span><span class="sxs-lookup"><span data-stu-id="cfcf5-191">classification</span></span> | <span data-ttu-id="cfcf5-192">Enumerazione Nullable</span><span class="sxs-lookup"><span data-stu-id="cfcf5-192">Nullable Enum</span></span> | <span data-ttu-id="cfcf5-193">Specifica dell'avviso.</span><span class="sxs-lookup"><span data-stu-id="cfcf5-193">Specification of the alert.</span></span> <span data-ttu-id="cfcf5-194">I valori possibili sono: 'Unknown', 'FalsePositive', 'TruePositive'.</span><span class="sxs-lookup"><span data-stu-id="cfcf5-194">Possible values are: 'Unknown', 'FalsePositive', 'TruePositive'.</span></span>
<span data-ttu-id="cfcf5-195">determinazione</span><span class="sxs-lookup"><span data-stu-id="cfcf5-195">determination</span></span> | <span data-ttu-id="cfcf5-196">Enumerazione Nullable</span><span class="sxs-lookup"><span data-stu-id="cfcf5-196">Nullable Enum</span></span> | <span data-ttu-id="cfcf5-197">Specifica la determinazione dell'avviso.</span><span class="sxs-lookup"><span data-stu-id="cfcf5-197">Specifies the determination of the alert.</span></span> <span data-ttu-id="cfcf5-198">I valori possibili sono: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'.</span><span class="sxs-lookup"><span data-stu-id="cfcf5-198">Possible values are: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'.</span></span>
<span data-ttu-id="cfcf5-199">category</span><span class="sxs-lookup"><span data-stu-id="cfcf5-199">category</span></span>| <span data-ttu-id="cfcf5-200">Stringa</span><span class="sxs-lookup"><span data-stu-id="cfcf5-200">String</span></span> | <span data-ttu-id="cfcf5-201">Categoria dell'avviso.</span><span class="sxs-lookup"><span data-stu-id="cfcf5-201">Category of the alert.</span></span>
<span data-ttu-id="cfcf5-202">detectionSource</span><span class="sxs-lookup"><span data-stu-id="cfcf5-202">detectionSource</span></span> | <span data-ttu-id="cfcf5-203">Stringa</span><span class="sxs-lookup"><span data-stu-id="cfcf5-203">String</span></span> | <span data-ttu-id="cfcf5-204">Origine di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="cfcf5-204">Detection source.</span></span>
<span data-ttu-id="cfcf5-205">threatFamilyName</span><span class="sxs-lookup"><span data-stu-id="cfcf5-205">threatFamilyName</span></span> | <span data-ttu-id="cfcf5-206">Stringa</span><span class="sxs-lookup"><span data-stu-id="cfcf5-206">String</span></span> | <span data-ttu-id="cfcf5-207">Famiglia di minacce.</span><span class="sxs-lookup"><span data-stu-id="cfcf5-207">Threat family.</span></span>
<span data-ttu-id="cfcf5-208">threatName</span><span class="sxs-lookup"><span data-stu-id="cfcf5-208">threatName</span></span> | <span data-ttu-id="cfcf5-209">Stringa</span><span class="sxs-lookup"><span data-stu-id="cfcf5-209">String</span></span> | <span data-ttu-id="cfcf5-210">Nome della minaccia.</span><span class="sxs-lookup"><span data-stu-id="cfcf5-210">Threat name.</span></span>
<span data-ttu-id="cfcf5-211">machineId</span><span class="sxs-lookup"><span data-stu-id="cfcf5-211">machineId</span></span> | <span data-ttu-id="cfcf5-212">Stringa</span><span class="sxs-lookup"><span data-stu-id="cfcf5-212">String</span></span> | <span data-ttu-id="cfcf5-213">ID di [un'entità](machine.md) computer associata all'avviso.</span><span class="sxs-lookup"><span data-stu-id="cfcf5-213">ID of a [machine](machine.md) entity that is associated with the alert.</span></span>
<span data-ttu-id="cfcf5-214">computerDnsName</span><span class="sxs-lookup"><span data-stu-id="cfcf5-214">computerDnsName</span></span> | <span data-ttu-id="cfcf5-215">Stringa</span><span class="sxs-lookup"><span data-stu-id="cfcf5-215">String</span></span> | <span data-ttu-id="cfcf5-216">[nome](machine.md) completo del computer.</span><span class="sxs-lookup"><span data-stu-id="cfcf5-216">[machine](machine.md) fully qualified name.</span></span>
<span data-ttu-id="cfcf5-217">aadTenantId</span><span class="sxs-lookup"><span data-stu-id="cfcf5-217">aadTenantId</span></span> | <span data-ttu-id="cfcf5-218">Stringa</span><span class="sxs-lookup"><span data-stu-id="cfcf5-218">String</span></span> | <span data-ttu-id="cfcf5-219">ID Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="cfcf5-219">The Azure Active Directory ID.</span></span>
<span data-ttu-id="cfcf5-220">detectorId</span><span class="sxs-lookup"><span data-stu-id="cfcf5-220">detectorId</span></span> | <span data-ttu-id="cfcf5-221">Stringa</span><span class="sxs-lookup"><span data-stu-id="cfcf5-221">String</span></span> | <span data-ttu-id="cfcf5-222">ID del rilevatore che ha attivato l'avviso.</span><span class="sxs-lookup"><span data-stu-id="cfcf5-222">The ID of the detector that triggered the alert.</span></span>
<span data-ttu-id="cfcf5-223">commenti</span><span class="sxs-lookup"><span data-stu-id="cfcf5-223">comments</span></span> | <span data-ttu-id="cfcf5-224">Elenco dei commenti degli avvisi</span><span class="sxs-lookup"><span data-stu-id="cfcf5-224">List of Alert comments</span></span> | <span data-ttu-id="cfcf5-225">L'oggetto Alert Comment contiene: stringa di commento, stringa createdBy e createTime date time.</span><span class="sxs-lookup"><span data-stu-id="cfcf5-225">Alert Comment object contains: comment string, createdBy string and createTime date time.</span></span>
<span data-ttu-id="cfcf5-226">Prove</span><span class="sxs-lookup"><span data-stu-id="cfcf5-226">Evidence</span></span> | <span data-ttu-id="cfcf5-227">Elenco delle prove di avviso</span><span class="sxs-lookup"><span data-stu-id="cfcf5-227">List of Alert evidence</span></span> | <span data-ttu-id="cfcf5-228">Prova relativa all'avviso.</span><span class="sxs-lookup"><span data-stu-id="cfcf5-228">Evidence related to the alert.</span></span> <span data-ttu-id="cfcf5-229">Vedere l'esempio che segue.</span><span class="sxs-lookup"><span data-stu-id="cfcf5-229">See example below.</span></span>

### <a name="response-example-for-getting-single-alert"></a><span data-ttu-id="cfcf5-230">Esempio di risposta per ottenere un singolo avviso:</span><span class="sxs-lookup"><span data-stu-id="cfcf5-230">Response example for getting single alert:</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/alerts/da637472900382838869_1364969609
```

```json
{
    "id": "da637472900382838869_1364969609",
    "incidentId": 1126093,
    "investigationId": null,
    "assignedTo": null,
    "severity": "Low",
    "status": "New",
    "classification": null,
    "determination": null,
    "investigationState": "Queued",
    "detectionSource": "WindowsDefenderAtp",
    "detectorId": "17e10bbc-3a68-474a-8aad-faef14d43952",
    "category": "Execution",
    "threatFamilyName": null,
    "title": "Low-reputation arbitrary code executed by signed executable",
    "description": "Binaries signed by Microsoft can be used to run low-reputation arbitrary code. This technique hides the execution of malicious code within a trusted process. As a result, the trusted process might exhibit suspicious behaviors, such as opening a listening port or connecting to a command-and-control (C&C) server.",
    "alertCreationTime": "2021-01-26T20:33:57.7220239Z",
    "firstEventTime": "2021-01-26T20:31:32.9562661Z",
    "lastEventTime": "2021-01-26T20:31:33.0577322Z",
    "lastUpdateTime": "2021-01-26T20:33:59.2Z",
    "resolvedTime": null,
    "machineId": "111e6dd8c833c8a052ea231ec1b19adaf497b625",
    "computerDnsName": "temp123.middleeast.corp.microsoft.com",
    "rbacGroupName": "A",
    "aadTenantId": "a839b112-1253-6432-9bf6-94542403f21c",
    "threatName": null,
    "mitreTechniques": [
        "T1064",
        "T1085",
        "T1220"
    ],
    "relatedUser": {
        "userName": "temp123",
        "domainName": "MIDDLEEAST"
    },
    "comments": [
        {
            "comment": "test comment for docs",
            "createdBy": "secop123@contoso.com",
            "createdTime": "2021-01-26T01:00:37.8404534Z"
        }
    ],
    "evidence": [
        {
            "entityType": "User",
            "evidenceCreationTime": "2021-01-26T20:33:58.42Z",
            "sha1": null,
            "sha256": null,
            "fileName": null,
            "filePath": null,
            "processId": null,
            "processCommandLine": null,
            "processCreationTime": null,
            "parentProcessId": null,
            "parentProcessCreationTime": null,
            "parentProcessFileName": null,
            "parentProcessFilePath": null,
            "ipAddress": null,
            "url": null,
            "registryKey": null,
            "registryHive": null,
            "registryValueType": null,
            "registryValue": null,
            "accountName": "eranb",
            "domainName": "MIDDLEEAST",
            "userSid": "S-1-5-21-11111607-1111760036-109187956-75141",
            "aadUserId": "11118379-2a59-1111-ac3c-a51eb4a3c627",
            "userPrincipalName": "temp123@microsoft.com",
            "detectionStatus": null
        },
        {
            "entityType": "Process",
            "evidenceCreationTime": "2021-01-26T20:33:58.6133333Z",
            "sha1": "ff836cfb1af40252bd2a2ea843032e99a5b262ed",
            "sha256": "a4752c71d81afd3d5865d24ddb11a6b0c615062fcc448d24050c2172d2cbccd6",
            "fileName": "rundll32.exe",
            "filePath": "C:\\Windows\\SysWOW64",
            "processId": 3276,
            "processCommandLine": "rundll32.exe  c:\\temp\\suspicious.dll,RepeatAfterMe",
            "processCreationTime": "2021-01-26T20:31:32.9581596Z",
            "parentProcessId": 8420,
            "parentProcessCreationTime": "2021-01-26T20:31:32.9004163Z",
            "parentProcessFileName": "rundll32.exe",
            "parentProcessFilePath": "C:\\Windows\\System32",
            "ipAddress": null,
            "url": null,
            "registryKey": null,
            "registryHive": null,
            "registryValueType": null,
            "registryValue": null,
            "accountName": null,
            "domainName": null,
            "userSid": null,
            "aadUserId": null,
            "userPrincipalName": null,
            "detectionStatus": "Detected"
        },
        {
            "entityType": "File",
            "evidenceCreationTime": "2021-01-26T20:33:58.42Z",
            "sha1": "8563f95b2f8a284fc99da44500cd51a77c1ff36c",
            "sha256": "dc0ade0c95d6db98882bc8fa6707e64353cd6f7767ff48d6a81a6c2aef21c608",
            "fileName": "suspicious.dll",
            "filePath": "c:\\temp",
            "processId": null,
            "processCommandLine": null,
            "processCreationTime": null,
            "parentProcessId": null,
            "parentProcessCreationTime": null,
            "parentProcessFileName": null,
            "parentProcessFilePath": null,
            "ipAddress": null,
            "url": null,
            "registryKey": null,
            "registryHive": null,
            "registryValueType": null,
            "registryValue": null,
            "accountName": null,
            "domainName": null,
            "userSid": null,
            "aadUserId": null,
            "userPrincipalName": null,
            "detectionStatus": "Detected"
        }
    ]
}
```
