---
title: Elencare tutte le attività correttive
description: Restituisce informazioni su tutte le attività di correzione.
keywords: api, correzione, api di correzione, ottenere, attività di correzione, tutte le correzioni,
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 60f80e78a5f5c7da44a218c30f4b0173d4ecc829
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845134"
---
# <a name="list-all-remediation-activities"></a><span data-ttu-id="6c295-104">Elencare tutte le attività correttive</span><span class="sxs-lookup"><span data-stu-id="6c295-104">List all remediation activities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6c295-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="6c295-105">**Applies to:**</span></span>

- [<span data-ttu-id="6c295-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="6c295-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6c295-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6c295-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="6c295-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="6c295-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6c295-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="6c295-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="6c295-110">Descrizione API</span><span class="sxs-lookup"><span data-stu-id="6c295-110">API description</span></span>

<span data-ttu-id="6c295-111">Restituisce informazioni su tutte le attività di correzione.</span><span class="sxs-lookup"><span data-stu-id="6c295-111">Returns information about all remediation activities.</span></span>

<span data-ttu-id="6c295-112">[Ulteriori informazioni sulle attività di correzione.](tvm-remediation.md)</span><span class="sxs-lookup"><span data-stu-id="6c295-112">[Learn more about remediation activities](tvm-remediation.md).</span></span>

<span data-ttu-id="6c295-113">**URL:** GET: /api/remediationTasks</span><span class="sxs-lookup"><span data-stu-id="6c295-113">**URL:** GET: /api/remediationTasks</span></span>

## <a name="permissions"></a><span data-ttu-id="6c295-114">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="6c295-114">Permissions</span></span>

<span data-ttu-id="6c295-115">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="6c295-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="6c295-116">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi Usare Le API di [Microsoft Defender per endpoint per i dettagli.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="6c295-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="6c295-117">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="6c295-117">Permission type</span></span> | <span data-ttu-id="6c295-118">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="6c295-118">Permission</span></span> | <span data-ttu-id="6c295-119">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="6c295-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="6c295-120">Applicazione</span><span class="sxs-lookup"><span data-stu-id="6c295-120">Application</span></span> | <span data-ttu-id="6c295-121">RemediationTask.Read.All</span><span class="sxs-lookup"><span data-stu-id="6c295-121">RemediationTask.Read.All</span></span> | <span data-ttu-id="6c295-122">\'Leggere informazioni sulla vulnerabilità di Gestione minacce e vulnerabilità\'</span><span class="sxs-lookup"><span data-stu-id="6c295-122">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="6c295-123">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="6c295-123">Delegated (work or school account)</span></span> | <span data-ttu-id="6c295-124">RemediationTask.Read</span><span class="sxs-lookup"><span data-stu-id="6c295-124">RemediationTask.Read</span></span> | <span data-ttu-id="6c295-125">\'Leggere informazioni sulla vulnerabilità di Gestione minacce e vulnerabilità\'</span><span class="sxs-lookup"><span data-stu-id="6c295-125">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

## <a name="properties"></a><span data-ttu-id="6c295-126">Proprietà</span><span class="sxs-lookup"><span data-stu-id="6c295-126">Properties</span></span>

<span data-ttu-id="6c295-127">Proprietà (id)</span><span class="sxs-lookup"><span data-stu-id="6c295-127">Property (id)</span></span> | <span data-ttu-id="6c295-128">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="6c295-128">Data type</span></span> | <span data-ttu-id="6c295-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6c295-129">Description</span></span> | <span data-ttu-id="6c295-130">Esempio di valore restituito</span><span class="sxs-lookup"><span data-stu-id="6c295-130">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="6c295-131">category</span><span class="sxs-lookup"><span data-stu-id="6c295-131">category</span></span> | <span data-ttu-id="6c295-132">Stringa</span><span class="sxs-lookup"><span data-stu-id="6c295-132">String</span></span> | <span data-ttu-id="6c295-133">Categoria dell'attività di correzione (configurazione software/sicurezza)</span><span class="sxs-lookup"><span data-stu-id="6c295-133">Category of the remediation activity (Software/Security configuration)</span></span> | <span data-ttu-id="6c295-134">Software</span><span class="sxs-lookup"><span data-stu-id="6c295-134">Software</span></span>
<span data-ttu-id="6c295-135">completerEmail</span><span class="sxs-lookup"><span data-stu-id="6c295-135">completerEmail</span></span> | <span data-ttu-id="6c295-136">Stringa</span><span class="sxs-lookup"><span data-stu-id="6c295-136">String</span></span> | <span data-ttu-id="6c295-137">Se l'attività di correzione è stata completata manualmente da un utente, questa colonna contiene il messaggio di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="6c295-137">If the remediation activity was manually completed by someone, this column contains their email</span></span> | <span data-ttu-id="6c295-138">null</span><span class="sxs-lookup"><span data-stu-id="6c295-138">null</span></span>
<span data-ttu-id="6c295-139">completerId</span><span class="sxs-lookup"><span data-stu-id="6c295-139">completerId</span></span> | <span data-ttu-id="6c295-140">Stringa</span><span class="sxs-lookup"><span data-stu-id="6c295-140">String</span></span> | <span data-ttu-id="6c295-141">Se l'attività di correzione è stata completata manualmente da un utente, questa colonna contiene l'ID oggetto</span><span class="sxs-lookup"><span data-stu-id="6c295-141">If the remediation activity was manually completed by someone, this column contains their object id</span></span> | <span data-ttu-id="6c295-142">null</span><span class="sxs-lookup"><span data-stu-id="6c295-142">null</span></span>
<span data-ttu-id="6c295-143">completionMethod</span><span class="sxs-lookup"><span data-stu-id="6c295-143">completionMethod</span></span> | <span data-ttu-id="6c295-144">Stringa</span><span class="sxs-lookup"><span data-stu-id="6c295-144">String</span></span> | <span data-ttu-id="6c295-145">Un'attività di correzione può essere completata "automaticamente" (se tutti i dispositivi sono patchati) o "manualmente" da una persona che seleziona "contrassegna come completata"</span><span class="sxs-lookup"><span data-stu-id="6c295-145">A remediation activity can be completed “automatically” (if all the devices are patched) or “manually” by a person who selects “mark as completed”</span></span> | <span data-ttu-id="6c295-146">Automatica</span><span class="sxs-lookup"><span data-stu-id="6c295-146">Automatic</span></span>
<span data-ttu-id="6c295-147">createdOn</span><span class="sxs-lookup"><span data-stu-id="6c295-147">createdOn</span></span> | <span data-ttu-id="6c295-148">DateTime</span><span class="sxs-lookup"><span data-stu-id="6c295-148">DateTime</span></span> | <span data-ttu-id="6c295-149">Ora in cui è stata creata questa attività di correzione</span><span class="sxs-lookup"><span data-stu-id="6c295-149">Time this remediation activity was created</span></span> | <span data-ttu-id="6c295-150">2021-01-12T18:54:11.5499478Z</span><span class="sxs-lookup"><span data-stu-id="6c295-150">2021-01-12T18:54:11.5499478Z</span></span>
<span data-ttu-id="6c295-151">descrizione</span><span class="sxs-lookup"><span data-stu-id="6c295-151">description</span></span> | <span data-ttu-id="6c295-152">Stringa</span><span class="sxs-lookup"><span data-stu-id="6c295-152">String</span></span> | <span data-ttu-id="6c295-153">Descrizione di questa attività di correzione</span><span class="sxs-lookup"><span data-stu-id="6c295-153">Description of this remediation activity</span></span> | <span data-ttu-id="6c295-154">Aggiornare Microsoft Silverlight a una versione successiva per ridurre le vulnerabilità note che interessano i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="6c295-154">Update Microsoft Silverlight  to a later version to mitigate known vulnerabilities affecting your devices.</span></span>
<span data-ttu-id="6c295-155">dueOn</span><span class="sxs-lookup"><span data-stu-id="6c295-155">dueOn</span></span> | <span data-ttu-id="6c295-156">DateTime</span><span class="sxs-lookup"><span data-stu-id="6c295-156">DateTime</span></span> | <span data-ttu-id="6c295-157">Data di scadenza impostata dal creatore per questa attività di correzione</span><span class="sxs-lookup"><span data-stu-id="6c295-157">Due date the creator set for this remediation activity</span></span> | <span data-ttu-id="6c295-158">2021-01-13T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="6c295-158">2021-01-13T00:00:00Z</span></span>
<span data-ttu-id="6c295-159">fixedDevices</span><span class="sxs-lookup"><span data-stu-id="6c295-159">fixedDevices</span></span> | <span data-ttu-id="6c295-160">.</span><span class="sxs-lookup"><span data-stu-id="6c295-160">.</span></span> | <span data-ttu-id="6c295-161">Il numero di dispositivi che sono stati corretti</span><span class="sxs-lookup"><span data-stu-id="6c295-161">The number of devices that have been fixed</span></span> | <span data-ttu-id="6c295-162">2</span><span class="sxs-lookup"><span data-stu-id="6c295-162">2</span></span>
<span data-ttu-id="6c295-163">id</span><span class="sxs-lookup"><span data-stu-id="6c295-163">id</span></span> | <span data-ttu-id="6c295-164">Stringa</span><span class="sxs-lookup"><span data-stu-id="6c295-164">String</span></span> | <span data-ttu-id="6c295-165">ID di questa attività di correzione</span><span class="sxs-lookup"><span data-stu-id="6c295-165">ID of this remediation activity</span></span> | <span data-ttu-id="6c295-166">097d9735-5479-4899-b1b7-77398899df92</span><span class="sxs-lookup"><span data-stu-id="6c295-166">097d9735-5479-4899-b1b7-77398899df92</span></span>
<span data-ttu-id="6c295-167">nameId</span><span class="sxs-lookup"><span data-stu-id="6c295-167">nameId</span></span> | <span data-ttu-id="6c295-168">Stringa</span><span class="sxs-lookup"><span data-stu-id="6c295-168">String</span></span> | <span data-ttu-id="6c295-169">Nome prodotto correlato</span><span class="sxs-lookup"><span data-stu-id="6c295-169">Related product name</span></span> | <span data-ttu-id="6c295-170">Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="6c295-170">Microsoft Silverlight</span></span>
<span data-ttu-id="6c295-171">priority</span><span class="sxs-lookup"><span data-stu-id="6c295-171">priority</span></span> | <span data-ttu-id="6c295-172">Stringa</span><span class="sxs-lookup"><span data-stu-id="6c295-172">String</span></span> | <span data-ttu-id="6c295-173">Priorità impostata dal creatore per questa attività di correzione (High\Medium\Low)</span><span class="sxs-lookup"><span data-stu-id="6c295-173">Priority the creator set for this remediation activity (High\Medium\Low)</span></span> | <span data-ttu-id="6c295-174">Fortemente</span><span class="sxs-lookup"><span data-stu-id="6c295-174">High</span></span>
<span data-ttu-id="6c295-175">productId</span><span class="sxs-lookup"><span data-stu-id="6c295-175">productId</span></span> | <span data-ttu-id="6c295-176">Stringa</span><span class="sxs-lookup"><span data-stu-id="6c295-176">String</span></span> | <span data-ttu-id="6c295-177">ID prodotto correlato</span><span class="sxs-lookup"><span data-stu-id="6c295-177">Related product ID</span></span> | <span data-ttu-id="6c295-178">microsoft-_-silverlight</span><span class="sxs-lookup"><span data-stu-id="6c295-178">microsoft-_-silverlight</span></span>
<span data-ttu-id="6c295-179">productivityImpactRemediationType</span><span class="sxs-lookup"><span data-stu-id="6c295-179">productivityImpactRemediationType</span></span> | <span data-ttu-id="6c295-180">Stringa</span><span class="sxs-lookup"><span data-stu-id="6c295-180">String</span></span> | <span data-ttu-id="6c295-181">Alcune modifiche alla configurazione potrebbero essere richieste solo per i dispositivi senza alcun impatto sull'utente.</span><span class="sxs-lookup"><span data-stu-id="6c295-181">A few configuration changes could be requested only for devices with no user impact.</span></span> <span data-ttu-id="6c295-182">Questo valore indica la selezione tra "tutti i dispositivi esposti" o "solo i dispositivi senza impatto sull'utente".</span><span class="sxs-lookup"><span data-stu-id="6c295-182">This value indicates the selection between “all exposed devices” or “only devices with no user impact.”</span></span> | <span data-ttu-id="6c295-183">AllExposedAssets</span><span class="sxs-lookup"><span data-stu-id="6c295-183">AllExposedAssets</span></span>
<span data-ttu-id="6c295-184">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="6c295-184">rbacGroupNames</span></span> | <span data-ttu-id="6c295-185">Stringa</span><span class="sxs-lookup"><span data-stu-id="6c295-185">String</span></span> | <span data-ttu-id="6c295-186">Nomi dei gruppi di dispositivi correlati</span><span class="sxs-lookup"><span data-stu-id="6c295-186">Related device group names</span></span> | <span data-ttu-id="6c295-187">[ "Windows Servers", "Windows 10" ]</span><span class="sxs-lookup"><span data-stu-id="6c295-187">[ "Windows Servers", "Windows 10" ]</span></span>
<span data-ttu-id="6c295-188">recommendedProgram</span><span class="sxs-lookup"><span data-stu-id="6c295-188">recommendedProgram</span></span> | <span data-ttu-id="6c295-189">Stringa</span><span class="sxs-lookup"><span data-stu-id="6c295-189">String</span></span> | <span data-ttu-id="6c295-190">Programma consigliato a cui eseguire l'aggiornamento</span><span class="sxs-lookup"><span data-stu-id="6c295-190">Recommended program to upgrade to</span></span> | <span data-ttu-id="6c295-191">null</span><span class="sxs-lookup"><span data-stu-id="6c295-191">null</span></span>
<span data-ttu-id="6c295-192">recommendedVendor</span><span class="sxs-lookup"><span data-stu-id="6c295-192">recommendedVendor</span></span> | <span data-ttu-id="6c295-193">Stringa</span><span class="sxs-lookup"><span data-stu-id="6c295-193">String</span></span> | <span data-ttu-id="6c295-194">Fornitore consigliato a cui eseguire l'aggiornamento</span><span class="sxs-lookup"><span data-stu-id="6c295-194">Recommended vendor to upgrade to</span></span> | <span data-ttu-id="6c295-195">null</span><span class="sxs-lookup"><span data-stu-id="6c295-195">null</span></span>
<span data-ttu-id="6c295-196">recommendedVersion</span><span class="sxs-lookup"><span data-stu-id="6c295-196">recommendedVersion</span></span> | <span data-ttu-id="6c295-197">Stringa</span><span class="sxs-lookup"><span data-stu-id="6c295-197">String</span></span> | <span data-ttu-id="6c295-198">Versione consigliata per l'aggiornamento/aggiornamento</span><span class="sxs-lookup"><span data-stu-id="6c295-198">Recommended version to update/upgrade to</span></span> | <span data-ttu-id="6c295-199">null</span><span class="sxs-lookup"><span data-stu-id="6c295-199">null</span></span>
<span data-ttu-id="6c295-200">relatedComponent</span><span class="sxs-lookup"><span data-stu-id="6c295-200">relatedComponent</span></span> | <span data-ttu-id="6c295-201">Stringa</span><span class="sxs-lookup"><span data-stu-id="6c295-201">String</span></span> | <span data-ttu-id="6c295-202">Componente correlato di questa attività di correzione (simile al componente correlato per una raccomandazione sulla sicurezza)</span><span class="sxs-lookup"><span data-stu-id="6c295-202">Related component of this remediation activity (similar to the related component for a security recommendation)</span></span> | <span data-ttu-id="6c295-203">Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="6c295-203">Microsoft Silverlight</span></span>
<span data-ttu-id="6c295-204">requesterEmail</span><span class="sxs-lookup"><span data-stu-id="6c295-204">requesterEmail</span></span> | <span data-ttu-id="6c295-205">Stringa</span><span class="sxs-lookup"><span data-stu-id="6c295-205">String</span></span> | <span data-ttu-id="6c295-206">Indirizzo di posta elettronica creatore</span><span class="sxs-lookup"><span data-stu-id="6c295-206">Creator email address</span></span> | <span data-ttu-id="6c295-207">globaladmin@UserName.contoso.com</span><span class="sxs-lookup"><span data-stu-id="6c295-207">globaladmin@UserName.contoso.com</span></span>
<span data-ttu-id="6c295-208">requesterId</span><span class="sxs-lookup"><span data-stu-id="6c295-208">requesterId</span></span> | <span data-ttu-id="6c295-209">Stringa</span><span class="sxs-lookup"><span data-stu-id="6c295-209">String</span></span> | <span data-ttu-id="6c295-210">ID oggetto creatore</span><span class="sxs-lookup"><span data-stu-id="6c295-210">Creator object id</span></span> | <span data-ttu-id="6c295-211">r647211f-2e16-43f2-a480-16ar3a2a796r</span><span class="sxs-lookup"><span data-stu-id="6c295-211">r647211f-2e16-43f2-a480-16ar3a2a796r</span></span>
<span data-ttu-id="6c295-212">requesterNotes</span><span class="sxs-lookup"><span data-stu-id="6c295-212">requesterNotes</span></span> | <span data-ttu-id="6c295-213">Stringa</span><span class="sxs-lookup"><span data-stu-id="6c295-213">String</span></span> | <span data-ttu-id="6c295-214">Note (testo libero) aggiunte dall'autore per questa attività di correzione</span><span class="sxs-lookup"><span data-stu-id="6c295-214">The notes (free text) the creator added for this remediation activity</span></span> | <span data-ttu-id="6c295-215">null</span><span class="sxs-lookup"><span data-stu-id="6c295-215">null</span></span>
<span data-ttu-id="6c295-216">scid</span><span class="sxs-lookup"><span data-stu-id="6c295-216">scid</span></span> | <span data-ttu-id="6c295-217">Stringa</span><span class="sxs-lookup"><span data-stu-id="6c295-217">String</span></span> | <span data-ttu-id="6c295-218">SCID della raccomandazione relativa alla sicurezza</span><span class="sxs-lookup"><span data-stu-id="6c295-218">SCID of the related security recommendation</span></span> | <span data-ttu-id="6c295-219">null</span><span class="sxs-lookup"><span data-stu-id="6c295-219">null</span></span>
<span data-ttu-id="6c295-220">status</span><span class="sxs-lookup"><span data-stu-id="6c295-220">status</span></span> | <span data-ttu-id="6c295-221">Stringa</span><span class="sxs-lookup"><span data-stu-id="6c295-221">String</span></span> | <span data-ttu-id="6c295-222">Stato attività di correzione (Attivo/Completato)</span><span class="sxs-lookup"><span data-stu-id="6c295-222">Remediation activity status (Active/Completed)</span></span> | <span data-ttu-id="6c295-223">Attivazione</span><span class="sxs-lookup"><span data-stu-id="6c295-223">Active</span></span>
<span data-ttu-id="6c295-224">statusLastModifiedOn</span><span class="sxs-lookup"><span data-stu-id="6c295-224">statusLastModifiedOn</span></span> | <span data-ttu-id="6c295-225">DateTime</span><span class="sxs-lookup"><span data-stu-id="6c295-225">DateTime</span></span> | <span data-ttu-id="6c295-226">Data in cui il campo stato è stato aggiornato</span><span class="sxs-lookup"><span data-stu-id="6c295-226">Date when the status field was updated</span></span> | <span data-ttu-id="6c295-227">2021-01-12T18:54:11.5499487Z</span><span class="sxs-lookup"><span data-stu-id="6c295-227">2021-01-12T18:54:11.5499487Z</span></span>
<span data-ttu-id="6c295-228">targetDevices</span><span class="sxs-lookup"><span data-stu-id="6c295-228">targetDevices</span></span> | <span data-ttu-id="6c295-229">Long</span><span class="sxs-lookup"><span data-stu-id="6c295-229">Long</span></span> | <span data-ttu-id="6c295-230">Numero di dispositivi esposti a cui è applicabile questa correzione</span><span class="sxs-lookup"><span data-stu-id="6c295-230">Number of exposed devices that this remediation is applicable to</span></span> | <span data-ttu-id="6c295-231">43</span><span class="sxs-lookup"><span data-stu-id="6c295-231">43</span></span>
<span data-ttu-id="6c295-232">title</span><span class="sxs-lookup"><span data-stu-id="6c295-232">title</span></span> | <span data-ttu-id="6c295-233">Stringa</span><span class="sxs-lookup"><span data-stu-id="6c295-233">String</span></span> | <span data-ttu-id="6c295-234">Titolo di questa attività di correzione</span><span class="sxs-lookup"><span data-stu-id="6c295-234">Title of this remediation activity</span></span> | <span data-ttu-id="6c295-235">Aggiornare Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="6c295-235">Update Microsoft Silverlight</span></span>
<span data-ttu-id="6c295-236">type</span><span class="sxs-lookup"><span data-stu-id="6c295-236">type</span></span> | <span data-ttu-id="6c295-237">Stringa</span><span class="sxs-lookup"><span data-stu-id="6c295-237">String</span></span> | <span data-ttu-id="6c295-238">Tipo di correzione</span><span class="sxs-lookup"><span data-stu-id="6c295-238">Remediation type</span></span> | <span data-ttu-id="6c295-239">Update</span><span class="sxs-lookup"><span data-stu-id="6c295-239">Update</span></span>
<span data-ttu-id="6c295-240">vendorId</span><span class="sxs-lookup"><span data-stu-id="6c295-240">vendorId</span></span> | <span data-ttu-id="6c295-241">Stringa</span><span class="sxs-lookup"><span data-stu-id="6c295-241">String</span></span> | <span data-ttu-id="6c295-242">Nome fornitore correlato</span><span class="sxs-lookup"><span data-stu-id="6c295-242">Related vendor name</span></span> | <span data-ttu-id="6c295-243">Microsoft</span><span class="sxs-lookup"><span data-stu-id="6c295-243">Microsoft</span></span>

## <a name="example"></a><span data-ttu-id="6c295-244">Esempio</span><span class="sxs-lookup"><span data-stu-id="6c295-244">Example</span></span>

### <a name="request-example"></a><span data-ttu-id="6c295-245">Esempio di richiesta</span><span class="sxs-lookup"><span data-stu-id="6c295-245">Request example</span></span>

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/
```

### <a name="response-example"></a><span data-ttu-id="6c295-246">Esempio di risposta</span><span class="sxs-lookup"><span data-stu-id="6c295-246">Response example</span></span>

```json
{
    "@odata.context": "https://wpatdadi-luna-stg.cloudapp.net/api/$metadata#RemediationTasks",
    "value": [
        {
            "id": "03942ef5-aewb-4w6e-b555-d6a97013844w",
            "title": "Update Microsoft Silverlight",
            "createdOn": "2021-02-10T13:20:36.4718166Z",
            "requesterId": "65548a1d-ef00-4a7a-8d19-1b967b5c36f4",
            "requesterEmail": "user1@contoso.com",
            "status": "Active",
            "statusLastModifiedOn": "2021-02-10T13:20:36.4719698Z",
            "description": "Update Silverlight to a later version  to mitigate 55 known vulnerabilities affecting your devices. Doing so can help lessen the security risk to your organization due to versions which have reached their end-of-support.  ",
            "relatedComponent": "Microsoft Silverlight",
            "targetDevices": 18511,
            "rbacGroupNames": [
                "UnassignedGroup",
                "hhh"
            ],
            "fixedDevices": 2866,
            "requesterNotes": "test",
            "dueOn": "2021-02-11T00:00:00Z",
            "category": "Software",
            "productivityImpactRemediationType": null,
            "priority": "Medium",
            "completionMethod": null,
            "completerId": null,
            "completerEmail": null,
            "scid": null,
            "type": "Update",
            "productId": "microsoft-_-silverlight",
            "vendorId": "microsoft",
            "nameId": "silverlight",
            "recommendedVersion": null,
            "recommendedVendor": null,
            "recommendedProgram": null
        }
    ]
}
```

## <a name="see-also"></a><span data-ttu-id="6c295-247">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6c295-247">See also</span></span>

- [<span data-ttu-id="6c295-248">Metodi e proprietà di correzione</span><span class="sxs-lookup"><span data-stu-id="6c295-248">Remediation methods and properties</span></span>](get-remediation-methods-properties.md)

- [<span data-ttu-id="6c295-249">Ottenere un'attività correttiva per ID</span><span class="sxs-lookup"><span data-stu-id="6c295-249">Get one remediation activity by Id</span></span>](get-remediation-one-activity.md)

- [<span data-ttu-id="6c295-250">Elencare i dispositivi esposti a un'attività correttiva</span><span class="sxs-lookup"><span data-stu-id="6c295-250">List exposed devices of one remediation activity</span></span>](get-remediation-exposed-devices-activities.md)

- [<span data-ttu-id="6c295-251">Rischio basato sulle minacce & gestione delle vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="6c295-251">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="6c295-252">Vulnerabilità nell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="6c295-252">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
