---
title: Ottenere un'attività di correzione in base all'ID
description: Restituisce informazioni per l'attività di correzione specificata.
keywords: api, correzione, api di correzione, ottenere, attività di correzione, correzione per ID,
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
ms.openlocfilehash: c2b7afef2c090df709f9209f450d8d3aab0424bf
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772150"
---
# <a name="get-one-remediation-activity-by-id"></a><span data-ttu-id="d647c-104">Ottenere un'attività di correzione in base all'ID</span><span class="sxs-lookup"><span data-stu-id="d647c-104">Get one remediation activity by Id</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d647c-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="d647c-105">**Applies to:**</span></span>

- [<span data-ttu-id="d647c-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="d647c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d647c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d647c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="d647c-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="d647c-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d647c-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="d647c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="d647c-110">Descrizione API</span><span class="sxs-lookup"><span data-stu-id="d647c-110">API description</span></span>

<span data-ttu-id="d647c-111">Restituisce informazioni per l'attività di correzione specificata.</span><span class="sxs-lookup"><span data-stu-id="d647c-111">Returns information for the specified remediation activity.</span></span> <span data-ttu-id="d647c-112">Presenta le stesse colonne di [Get all remediation activity](get-remediation-all-activities.md), ma restituisce i risultati solo per l'attività di correzione _specificata._</span><span class="sxs-lookup"><span data-stu-id="d647c-112">Presents the same columns as [Get all remediation activity](get-remediation-all-activities.md)", but returns results _only for the one specified remediation activity_.</span></span>

<span data-ttu-id="d647c-113">[Ulteriori informazioni sulle attività di correzione.](tvm-remediation.md)</span><span class="sxs-lookup"><span data-stu-id="d647c-113">[Learn more about remediation activities](tvm-remediation.md).</span></span>

## <a name="list-a-specified-remediation-activity-for-id"></a><span data-ttu-id="d647c-114">Elencare un'attività di correzione specificata per (id)</span><span class="sxs-lookup"><span data-stu-id="d647c-114">List a specified remediation activity for (id)</span></span>

<span data-ttu-id="d647c-115">**URL:** GET: /api/remediationTasks/ \{ id\}</span><span class="sxs-lookup"><span data-stu-id="d647c-115">**URL:** GET: /api/remediationTasks/\{id\}</span></span>

## <a name="permissions"></a><span data-ttu-id="d647c-116">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="d647c-116">Permissions</span></span>

<span data-ttu-id="d647c-117">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="d647c-117">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="d647c-118">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi Usare Le API di [Microsoft Defender per endpoint per i dettagli.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="d647c-118">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="d647c-119">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="d647c-119">Permission type</span></span> | <span data-ttu-id="d647c-120">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="d647c-120">Permission</span></span> | <span data-ttu-id="d647c-121">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="d647c-121">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="d647c-122">Applicazione</span><span class="sxs-lookup"><span data-stu-id="d647c-122">Application</span></span> | <span data-ttu-id="d647c-123">RemediationTask.Read.All</span><span class="sxs-lookup"><span data-stu-id="d647c-123">RemediationTask.Read.All</span></span> | <span data-ttu-id="d647c-124">\'Leggere informazioni sulla vulnerabilità di Gestione minacce e vulnerabilità\'</span><span class="sxs-lookup"><span data-stu-id="d647c-124">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="d647c-125">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="d647c-125">Delegated (work or school account)</span></span> | <span data-ttu-id="d647c-126">RemediationTask.Read.Read</span><span class="sxs-lookup"><span data-stu-id="d647c-126">RemediationTask.Read.Read</span></span> | <span data-ttu-id="d647c-127">\'Leggere informazioni sulla vulnerabilità di Gestione minacce e vulnerabilità\'</span><span class="sxs-lookup"><span data-stu-id="d647c-127">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

## <a name="properties"></a><span data-ttu-id="d647c-128">Proprietà</span><span class="sxs-lookup"><span data-stu-id="d647c-128">Properties</span></span>

<span data-ttu-id="d647c-129">Proprietà (id)</span><span class="sxs-lookup"><span data-stu-id="d647c-129">Property (id)</span></span> | <span data-ttu-id="d647c-130">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="d647c-130">Data type</span></span> | <span data-ttu-id="d647c-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d647c-131">Description</span></span> | <span data-ttu-id="d647c-132">Esempio di valore restituito</span><span class="sxs-lookup"><span data-stu-id="d647c-132">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="d647c-133">category</span><span class="sxs-lookup"><span data-stu-id="d647c-133">category</span></span> | <span data-ttu-id="d647c-134">Stringa</span><span class="sxs-lookup"><span data-stu-id="d647c-134">String</span></span> | <span data-ttu-id="d647c-135">Categoria dell'attività di correzione (configurazione software/sicurezza)</span><span class="sxs-lookup"><span data-stu-id="d647c-135">Category of the remediation activity (Software/Security configuration)</span></span> | <span data-ttu-id="d647c-136">Software</span><span class="sxs-lookup"><span data-stu-id="d647c-136">Software</span></span>
<span data-ttu-id="d647c-137">completerEmail</span><span class="sxs-lookup"><span data-stu-id="d647c-137">completerEmail</span></span> | <span data-ttu-id="d647c-138">Stringa</span><span class="sxs-lookup"><span data-stu-id="d647c-138">String</span></span> | <span data-ttu-id="d647c-139">Se l'attività di correzione è stata completata manualmente da un utente, questa colonna contiene il messaggio di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="d647c-139">If the remediation activity was manually completed by someone, this column contains their email</span></span> | <span data-ttu-id="d647c-140">null</span><span class="sxs-lookup"><span data-stu-id="d647c-140">null</span></span>
<span data-ttu-id="d647c-141">completerId</span><span class="sxs-lookup"><span data-stu-id="d647c-141">completerId</span></span> | <span data-ttu-id="d647c-142">Stringa</span><span class="sxs-lookup"><span data-stu-id="d647c-142">String</span></span> | <span data-ttu-id="d647c-143">Se l'attività di correzione è stata completata manualmente da un utente, questa colonna contiene l'ID oggetto</span><span class="sxs-lookup"><span data-stu-id="d647c-143">If the remediation activity was manually completed by someone, this column contains their object id</span></span> | <span data-ttu-id="d647c-144">null</span><span class="sxs-lookup"><span data-stu-id="d647c-144">null</span></span>
<span data-ttu-id="d647c-145">completionMethod</span><span class="sxs-lookup"><span data-stu-id="d647c-145">completionMethod</span></span> | <span data-ttu-id="d647c-146">Stringa</span><span class="sxs-lookup"><span data-stu-id="d647c-146">String</span></span> | <span data-ttu-id="d647c-147">Un'attività di correzione può essere completata "automaticamente" (se tutti i dispositivi sono patchati) o "manualmente" da una persona che seleziona "contrassegna come completata"</span><span class="sxs-lookup"><span data-stu-id="d647c-147">A remediation activity can be completed “automatically” (if all the devices are patched) or “manually” by a person who selects “mark as completed”</span></span> | <span data-ttu-id="d647c-148">Automatica</span><span class="sxs-lookup"><span data-stu-id="d647c-148">Automatic</span></span>
<span data-ttu-id="d647c-149">createdOn</span><span class="sxs-lookup"><span data-stu-id="d647c-149">createdOn</span></span> | <span data-ttu-id="d647c-150">DateTime</span><span class="sxs-lookup"><span data-stu-id="d647c-150">DateTime</span></span> | <span data-ttu-id="d647c-151">Ora in cui è stata creata questa attività di correzione</span><span class="sxs-lookup"><span data-stu-id="d647c-151">Time this remediation activity was created</span></span> | <span data-ttu-id="d647c-152">2021-01-12T18:54:11.5499478Z</span><span class="sxs-lookup"><span data-stu-id="d647c-152">2021-01-12T18:54:11.5499478Z</span></span>
<span data-ttu-id="d647c-153">descrizione</span><span class="sxs-lookup"><span data-stu-id="d647c-153">description</span></span> | <span data-ttu-id="d647c-154">Stringa</span><span class="sxs-lookup"><span data-stu-id="d647c-154">String</span></span> | <span data-ttu-id="d647c-155">Descrizione di questa attività di correzione</span><span class="sxs-lookup"><span data-stu-id="d647c-155">Description of this remediation activity</span></span> | <span data-ttu-id="d647c-156">Aggiornare Microsoft Silverlight a una versione successiva per ridurre le vulnerabilità note che interessano i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="d647c-156">Update Microsoft Silverlight  to a later version to mitigate known vulnerabilities affecting your devices.</span></span>
<span data-ttu-id="d647c-157">dueOn</span><span class="sxs-lookup"><span data-stu-id="d647c-157">dueOn</span></span> | <span data-ttu-id="d647c-158">DateTime</span><span class="sxs-lookup"><span data-stu-id="d647c-158">DateTime</span></span> | <span data-ttu-id="d647c-159">Data di scadenza impostata dal creatore per questa attività di correzione</span><span class="sxs-lookup"><span data-stu-id="d647c-159">Due date the creator set for this remediation activity</span></span> | <span data-ttu-id="d647c-160">2021-01-13T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="d647c-160">2021-01-13T00:00:00Z</span></span>
<span data-ttu-id="d647c-161">fixedDevices</span><span class="sxs-lookup"><span data-stu-id="d647c-161">fixedDevices</span></span> |  | <span data-ttu-id="d647c-162">Il numero di dispositivi che sono stati corretti</span><span class="sxs-lookup"><span data-stu-id="d647c-162">The number of devices that have been fixed</span></span> | <span data-ttu-id="d647c-163">2</span><span class="sxs-lookup"><span data-stu-id="d647c-163">2</span></span>
<span data-ttu-id="d647c-164">id</span><span class="sxs-lookup"><span data-stu-id="d647c-164">id</span></span> | <span data-ttu-id="d647c-165">Stringa</span><span class="sxs-lookup"><span data-stu-id="d647c-165">String</span></span> | <span data-ttu-id="d647c-166">ID di questa attività di correzione</span><span class="sxs-lookup"><span data-stu-id="d647c-166">ID of this remediation activity</span></span> | <span data-ttu-id="d647c-167">097d9735-5479-4899-b1b7-77398899df92</span><span class="sxs-lookup"><span data-stu-id="d647c-167">097d9735-5479-4899-b1b7-77398899df92</span></span>
<span data-ttu-id="d647c-168">nameId</span><span class="sxs-lookup"><span data-stu-id="d647c-168">nameId</span></span> | <span data-ttu-id="d647c-169">Stringa</span><span class="sxs-lookup"><span data-stu-id="d647c-169">String</span></span> | <span data-ttu-id="d647c-170">Nome prodotto correlato</span><span class="sxs-lookup"><span data-stu-id="d647c-170">Related product name</span></span> | <span data-ttu-id="d647c-171">Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="d647c-171">Microsoft Silverlight</span></span>
<span data-ttu-id="d647c-172">priority</span><span class="sxs-lookup"><span data-stu-id="d647c-172">priority</span></span> | <span data-ttu-id="d647c-173">Stringa</span><span class="sxs-lookup"><span data-stu-id="d647c-173">String</span></span> | <span data-ttu-id="d647c-174">Priorità impostata dal creatore per questa attività di correzione (High\Medium\Low)</span><span class="sxs-lookup"><span data-stu-id="d647c-174">Priority the creator set for this remediation activity (High\Medium\Low)</span></span> | <span data-ttu-id="d647c-175">Fortemente</span><span class="sxs-lookup"><span data-stu-id="d647c-175">High</span></span>
<span data-ttu-id="d647c-176">productId</span><span class="sxs-lookup"><span data-stu-id="d647c-176">productId</span></span> | <span data-ttu-id="d647c-177">Stringa</span><span class="sxs-lookup"><span data-stu-id="d647c-177">String</span></span> | <span data-ttu-id="d647c-178">ID prodotto correlato</span><span class="sxs-lookup"><span data-stu-id="d647c-178">Related product ID</span></span> | <span data-ttu-id="d647c-179">microsoft-_-silverlight</span><span class="sxs-lookup"><span data-stu-id="d647c-179">microsoft-_-silverlight</span></span>
<span data-ttu-id="d647c-180">productivityImpactRemediationType</span><span class="sxs-lookup"><span data-stu-id="d647c-180">productivityImpactRemediationType</span></span> | <span data-ttu-id="d647c-181">Stringa</span><span class="sxs-lookup"><span data-stu-id="d647c-181">String</span></span> | <span data-ttu-id="d647c-182">Alcune modifiche alla configurazione potrebbero essere richieste solo per i dispositivi senza alcun impatto sull'utente.</span><span class="sxs-lookup"><span data-stu-id="d647c-182">A few configuration changes could be requested only for devices with no user impact.</span></span> <span data-ttu-id="d647c-183">Questo valore indica la selezione tra "tutti i dispositivi esposti" o "solo i dispositivi senza impatto sull'utente".</span><span class="sxs-lookup"><span data-stu-id="d647c-183">This value indicate the selection between “all exposed devices” or “only devices with no user impact.”</span></span> | <span data-ttu-id="d647c-184">AllExposedAssets</span><span class="sxs-lookup"><span data-stu-id="d647c-184">AllExposedAssets</span></span>
<span data-ttu-id="d647c-185">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="d647c-185">rbacGroupNames</span></span> | <span data-ttu-id="d647c-186">Stringa</span><span class="sxs-lookup"><span data-stu-id="d647c-186">String</span></span> | <span data-ttu-id="d647c-187">Nomi dei gruppi di dispositivi correlati</span><span class="sxs-lookup"><span data-stu-id="d647c-187">Related device group names</span></span> | <span data-ttu-id="d647c-188">[ "Windows Servers", "Windows 10" ]</span><span class="sxs-lookup"><span data-stu-id="d647c-188">[ "Windows Servers", "Windows 10" ]</span></span>
<span data-ttu-id="d647c-189">recommendedProgram</span><span class="sxs-lookup"><span data-stu-id="d647c-189">recommendedProgram</span></span> | <span data-ttu-id="d647c-190">Stringa</span><span class="sxs-lookup"><span data-stu-id="d647c-190">String</span></span> | <span data-ttu-id="d647c-191">Programma consigliato a cui eseguire l'aggiornamento</span><span class="sxs-lookup"><span data-stu-id="d647c-191">Recommended program to upgrade to</span></span> | <span data-ttu-id="d647c-192">null</span><span class="sxs-lookup"><span data-stu-id="d647c-192">null</span></span>
<span data-ttu-id="d647c-193">recommendedVendor</span><span class="sxs-lookup"><span data-stu-id="d647c-193">recommendedVendor</span></span> | <span data-ttu-id="d647c-194">Stringa</span><span class="sxs-lookup"><span data-stu-id="d647c-194">String</span></span> | <span data-ttu-id="d647c-195">Fornitore consigliato a cui eseguire l'aggiornamento</span><span class="sxs-lookup"><span data-stu-id="d647c-195">Recommended vendor to upgrade to</span></span> | <span data-ttu-id="d647c-196">null</span><span class="sxs-lookup"><span data-stu-id="d647c-196">null</span></span>
<span data-ttu-id="d647c-197">recommendedVersion</span><span class="sxs-lookup"><span data-stu-id="d647c-197">recommendedVersion</span></span> | <span data-ttu-id="d647c-198">Stringa</span><span class="sxs-lookup"><span data-stu-id="d647c-198">String</span></span> | <span data-ttu-id="d647c-199">Versione consigliata per l'aggiornamento/aggiornamento</span><span class="sxs-lookup"><span data-stu-id="d647c-199">Recommended version to update/upgrade to</span></span> | <span data-ttu-id="d647c-200">null</span><span class="sxs-lookup"><span data-stu-id="d647c-200">null</span></span>
<span data-ttu-id="d647c-201">relatedComponent</span><span class="sxs-lookup"><span data-stu-id="d647c-201">relatedComponent</span></span> | <span data-ttu-id="d647c-202">Stringa</span><span class="sxs-lookup"><span data-stu-id="d647c-202">String</span></span> | <span data-ttu-id="d647c-203">Componente correlato di questa attività di correzione (simile al componente correlato per una raccomandazione sulla sicurezza)</span><span class="sxs-lookup"><span data-stu-id="d647c-203">Related component of this remediation activity (similar to the related component for a security recommendation)</span></span> | <span data-ttu-id="d647c-204">Microsoft Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="d647c-204">Microsoft Microsoft Silverlight</span></span>
<span data-ttu-id="d647c-205">requesterEmail</span><span class="sxs-lookup"><span data-stu-id="d647c-205">requesterEmail</span></span> | <span data-ttu-id="d647c-206">Stringa</span><span class="sxs-lookup"><span data-stu-id="d647c-206">String</span></span> | <span data-ttu-id="d647c-207">Indirizzo di posta elettronica creatore</span><span class="sxs-lookup"><span data-stu-id="d647c-207">Creator email address</span></span> | <span data-ttu-id="d647c-208">globaladmin@UserName.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d647c-208">globaladmin@UserName.contoso.com</span></span>
<span data-ttu-id="d647c-209">requesterId</span><span class="sxs-lookup"><span data-stu-id="d647c-209">requesterId</span></span> | <span data-ttu-id="d647c-210">Stringa</span><span class="sxs-lookup"><span data-stu-id="d647c-210">String</span></span> | <span data-ttu-id="d647c-211">ID oggetto creatore</span><span class="sxs-lookup"><span data-stu-id="d647c-211">Creator object id</span></span> | <span data-ttu-id="d647c-212">r647211f-2e16-43f2-a480-16ar3a2a796r</span><span class="sxs-lookup"><span data-stu-id="d647c-212">r647211f-2e16-43f2-a480-16ar3a2a796r</span></span>
<span data-ttu-id="d647c-213">requesterNotes</span><span class="sxs-lookup"><span data-stu-id="d647c-213">requesterNotes</span></span> | <span data-ttu-id="d647c-214">Stringa</span><span class="sxs-lookup"><span data-stu-id="d647c-214">String</span></span> | <span data-ttu-id="d647c-215">Note (testo libero) aggiunte dall'autore per questa attività di correzione</span><span class="sxs-lookup"><span data-stu-id="d647c-215">The notes (free text) the creator added for this remediation activity</span></span> | <span data-ttu-id="d647c-216">null</span><span class="sxs-lookup"><span data-stu-id="d647c-216">null</span></span>
<span data-ttu-id="d647c-217">scid</span><span class="sxs-lookup"><span data-stu-id="d647c-217">scid</span></span> | <span data-ttu-id="d647c-218">Stringa</span><span class="sxs-lookup"><span data-stu-id="d647c-218">String</span></span> | <span data-ttu-id="d647c-219">SCID della raccomandazione relativa alla sicurezza</span><span class="sxs-lookup"><span data-stu-id="d647c-219">SCID of the related security recommendation</span></span> | <span data-ttu-id="d647c-220">null</span><span class="sxs-lookup"><span data-stu-id="d647c-220">null</span></span>
<span data-ttu-id="d647c-221">status</span><span class="sxs-lookup"><span data-stu-id="d647c-221">status</span></span> | <span data-ttu-id="d647c-222">Stringa</span><span class="sxs-lookup"><span data-stu-id="d647c-222">String</span></span> | <span data-ttu-id="d647c-223">Stato attività di correzione (Attivo/Completato)</span><span class="sxs-lookup"><span data-stu-id="d647c-223">Remediation activity status (Active/Completed)</span></span> | <span data-ttu-id="d647c-224">Attivazione</span><span class="sxs-lookup"><span data-stu-id="d647c-224">Active</span></span>
<span data-ttu-id="d647c-225">statusLastModifiedOn</span><span class="sxs-lookup"><span data-stu-id="d647c-225">statusLastModifiedOn</span></span> | <span data-ttu-id="d647c-226">DateTime</span><span class="sxs-lookup"><span data-stu-id="d647c-226">DateTime</span></span> | <span data-ttu-id="d647c-227">Data in cui il campo stato è stato aggiornato</span><span class="sxs-lookup"><span data-stu-id="d647c-227">Date when the status field was updated</span></span> | <span data-ttu-id="d647c-228">2021-01-12T18:54:11.5499487Z</span><span class="sxs-lookup"><span data-stu-id="d647c-228">2021-01-12T18:54:11.5499487Z</span></span>
<span data-ttu-id="d647c-229">targetDevices</span><span class="sxs-lookup"><span data-stu-id="d647c-229">targetDevices</span></span> | <span data-ttu-id="d647c-230">Long</span><span class="sxs-lookup"><span data-stu-id="d647c-230">Long</span></span> | <span data-ttu-id="d647c-231">Numero di dispositivi esposti a cui è applicabile questa correzione</span><span class="sxs-lookup"><span data-stu-id="d647c-231">Number of exposed devices that this remediation is applicable to</span></span> | <span data-ttu-id="d647c-232">43</span><span class="sxs-lookup"><span data-stu-id="d647c-232">43</span></span>
<span data-ttu-id="d647c-233">title</span><span class="sxs-lookup"><span data-stu-id="d647c-233">title</span></span> | <span data-ttu-id="d647c-234">Stringa</span><span class="sxs-lookup"><span data-stu-id="d647c-234">String</span></span> | <span data-ttu-id="d647c-235">Titolo di questa attività di correzione</span><span class="sxs-lookup"><span data-stu-id="d647c-235">Title of this remediation activity</span></span> | <span data-ttu-id="d647c-236">Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="d647c-236">Microsoft Silverlight</span></span>
<span data-ttu-id="d647c-237">type</span><span class="sxs-lookup"><span data-stu-id="d647c-237">type</span></span> | <span data-ttu-id="d647c-238">Stringa</span><span class="sxs-lookup"><span data-stu-id="d647c-238">String</span></span> | <span data-ttu-id="d647c-239">Tipo di correzione</span><span class="sxs-lookup"><span data-stu-id="d647c-239">Remediation type</span></span> | <span data-ttu-id="d647c-240">Update</span><span class="sxs-lookup"><span data-stu-id="d647c-240">Update</span></span>
<span data-ttu-id="d647c-241">vendorId</span><span class="sxs-lookup"><span data-stu-id="d647c-241">vendorId</span></span> | <span data-ttu-id="d647c-242">Stringa</span><span class="sxs-lookup"><span data-stu-id="d647c-242">String</span></span> | <span data-ttu-id="d647c-243">Nome fornitore correlato</span><span class="sxs-lookup"><span data-stu-id="d647c-243">Related vendor name</span></span> | <span data-ttu-id="d647c-244">Microsoft</span><span class="sxs-lookup"><span data-stu-id="d647c-244">Microsoft</span></span>

## <a name="example"></a><span data-ttu-id="d647c-245">Esempio</span><span class="sxs-lookup"><span data-stu-id="d647c-245">Example</span></span>

### <a name="request-example"></a><span data-ttu-id="d647c-246">Esempio di richiesta</span><span class="sxs-lookup"><span data-stu-id="d647c-246">Request example</span></span>

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/03942ef5-aecb-4c6e-b555-d6a97013844c
```

### <a name="response-example"></a><span data-ttu-id="d647c-247">Esempio di risposta</span><span class="sxs-lookup"><span data-stu-id="d647c-247">Response example</span></span>

```json
{ 
    "@odata.context": "https://wpatdadi-luna-stg.cloudapp.net/api/$metadata#RemediationTasks/$entity", 
    "id": "03942ef5-aecb-4c6e-b555-d6a97013844c", 
    "title": "Update Microsoft Silverlight", 
    "createdOn": "2021-02-10T13:20:36.4718166Z", 
    "requesterId": "65548a1d-efo0-4a7a-8d19-1b967b5c36f4", 
    "requesterEmail": "user1@contoso.com", 
    "status": "Active", 
    "statusLastModifiedOn": "2021-02-10T13:20:36.4719698Z", 
    "description": "Update Silverlight to a later version to mitigate 55 known vulnerabilities affecting your devices. Doing so can help lessen the security risk to your organization due to versions which have reached their end-of-support.  ", 
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
```

## <a name="see-also"></a><span data-ttu-id="d647c-248">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d647c-248">See also</span></span>

- [<span data-ttu-id="d647c-249">Metodi e proprietà di correzione</span><span class="sxs-lookup"><span data-stu-id="d647c-249">Remediation methods and properties</span></span>](get-remediation-methods-properties.md)

- [<span data-ttu-id="d647c-250">Elencare tutte le attività correttive</span><span class="sxs-lookup"><span data-stu-id="d647c-250">List all remediation activities</span></span>](get-remediation-all-activities.md)

- [<span data-ttu-id="d647c-251">Elencare i dispositivi esposti a un'attività correttiva</span><span class="sxs-lookup"><span data-stu-id="d647c-251">List exposed devices of one remediation activity</span></span>](get-remediation-exposed-devices-activities.md)

- [<span data-ttu-id="d647c-252">Rischio basato sulle minacce & gestione delle vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="d647c-252">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="d647c-253">Vulnerabilità nell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="d647c-253">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
