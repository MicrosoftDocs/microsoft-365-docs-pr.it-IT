---
title: Elencare tutte le attività di correzione
description: Restituisce informazioni su tutte le attività di correzione.
keywords: api, correzione, api di correzione, ottenere, attività di correzione,
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
ms.technology: mde
ms.openlocfilehash: ac4a777136dcdfc5d7ab61ddc8d496b7452f69e2
ms.sourcegitcommit: e5b1a900043e2e41650ea1cbf4227043729c6053
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2021
ms.locfileid: "52061126"
---
# <a name="list-all-remediation-activities"></a><span data-ttu-id="bb79b-104">Elencare tutte le attività di correzione</span><span class="sxs-lookup"><span data-stu-id="bb79b-104">List all remediation activities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="bb79b-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="bb79b-105">**Applies to:**</span></span>

- [<span data-ttu-id="bb79b-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="bb79b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="bb79b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bb79b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="bb79b-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="bb79b-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="bb79b-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="bb79b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="bb79b-110">Descrizione API</span><span class="sxs-lookup"><span data-stu-id="bb79b-110">API description</span></span>

<span data-ttu-id="bb79b-111">Restituisce informazioni su tutte le attività di correzione.</span><span class="sxs-lookup"><span data-stu-id="bb79b-111">Returns information about all remediation activities.</span></span>

<span data-ttu-id="bb79b-112">[Ulteriori informazioni sulle attività di correzione.](tvm-remediation.md)</span><span class="sxs-lookup"><span data-stu-id="bb79b-112">[Learn more about remediation activities](tvm-remediation.md).</span></span>

<span data-ttu-id="bb79b-113">**URL:** GET: /api/remediationTasks</span><span class="sxs-lookup"><span data-stu-id="bb79b-113">**URL:** GET: /api/remediationTasks</span></span>

<span data-ttu-id="bb79b-114">**Dettagli proprietà**</span><span class="sxs-lookup"><span data-stu-id="bb79b-114">**Properties** details</span></span>

<span data-ttu-id="bb79b-115">Proprietà (id)</span><span class="sxs-lookup"><span data-stu-id="bb79b-115">Property (id)</span></span> | <span data-ttu-id="bb79b-116">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="bb79b-116">Data type</span></span> | <span data-ttu-id="bb79b-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bb79b-117">Description</span></span> | <span data-ttu-id="bb79b-118">Esempio di valore restituito</span><span class="sxs-lookup"><span data-stu-id="bb79b-118">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="bb79b-119">category</span><span class="sxs-lookup"><span data-stu-id="bb79b-119">category</span></span> | <span data-ttu-id="bb79b-120">Stringa</span><span class="sxs-lookup"><span data-stu-id="bb79b-120">String</span></span> | <span data-ttu-id="bb79b-121">Categoria dell'attività di correzione (configurazione software/sicurezza)</span><span class="sxs-lookup"><span data-stu-id="bb79b-121">Category of the remediation activity (Software/Security configuration)</span></span> | <span data-ttu-id="bb79b-122">Software</span><span class="sxs-lookup"><span data-stu-id="bb79b-122">Software</span></span>
<span data-ttu-id="bb79b-123">completerEmail</span><span class="sxs-lookup"><span data-stu-id="bb79b-123">completerEmail</span></span> | <span data-ttu-id="bb79b-124">Stringa</span><span class="sxs-lookup"><span data-stu-id="bb79b-124">String</span></span> | <span data-ttu-id="bb79b-125">Se l'attività di correzione è stata completata manualmente da un utente, questa colonna contiene il messaggio di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="bb79b-125">If the remediation activity was manually completed by someone, this column contains their email</span></span> | <span data-ttu-id="bb79b-126">null</span><span class="sxs-lookup"><span data-stu-id="bb79b-126">null</span></span>
<span data-ttu-id="bb79b-127">completerId</span><span class="sxs-lookup"><span data-stu-id="bb79b-127">completerId</span></span> | <span data-ttu-id="bb79b-128">Stringa</span><span class="sxs-lookup"><span data-stu-id="bb79b-128">String</span></span> | <span data-ttu-id="bb79b-129">Se l'attività di correzione è stata completata manualmente da un utente, questa colonna contiene l'ID oggetto</span><span class="sxs-lookup"><span data-stu-id="bb79b-129">If the remediation activity was manually completed by someone, this column contains their object id</span></span> | <span data-ttu-id="bb79b-130">null</span><span class="sxs-lookup"><span data-stu-id="bb79b-130">null</span></span>
<span data-ttu-id="bb79b-131">completionMethod</span><span class="sxs-lookup"><span data-stu-id="bb79b-131">completionMethod</span></span> | <span data-ttu-id="bb79b-132">Stringa</span><span class="sxs-lookup"><span data-stu-id="bb79b-132">String</span></span> | <span data-ttu-id="bb79b-133">Un'attività di correzione può essere completata "automaticamente" (se tutti i dispositivi sono patchati) o "manualmente" da una persona che seleziona "contrassegna come completata"</span><span class="sxs-lookup"><span data-stu-id="bb79b-133">A remediation activity can be completed “automatically” (if all the devices are patched) or “manually” by a person who selects “mark as completed”</span></span> | <span data-ttu-id="bb79b-134">Automatica</span><span class="sxs-lookup"><span data-stu-id="bb79b-134">Automatic</span></span>
<span data-ttu-id="bb79b-135">createdOn</span><span class="sxs-lookup"><span data-stu-id="bb79b-135">createdOn</span></span> | <span data-ttu-id="bb79b-136">DateTime</span><span class="sxs-lookup"><span data-stu-id="bb79b-136">DateTime</span></span> | <span data-ttu-id="bb79b-137">Ora in cui è stata creata questa attività di correzione</span><span class="sxs-lookup"><span data-stu-id="bb79b-137">Time this remediation activity was created</span></span> | <span data-ttu-id="bb79b-138">2021-01-12T18:54:11.5499478Z</span><span class="sxs-lookup"><span data-stu-id="bb79b-138">2021-01-12T18:54:11.5499478Z</span></span>
<span data-ttu-id="bb79b-139">descrizione</span><span class="sxs-lookup"><span data-stu-id="bb79b-139">description</span></span> | <span data-ttu-id="bb79b-140">Stringa</span><span class="sxs-lookup"><span data-stu-id="bb79b-140">String</span></span> | <span data-ttu-id="bb79b-141">Descrizione di questa attività di correzione</span><span class="sxs-lookup"><span data-stu-id="bb79b-141">Description of this remediation activity</span></span> | <span data-ttu-id="bb79b-142">Aggiornare Chrome a una versione successiva per ridurre le 1248 vulnerabilità note che interessano i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="bb79b-142">Update Chrome to a later version to mitigate 1248 known vulnerabilities affecting your devices.</span></span>
<span data-ttu-id="bb79b-143">dueOn</span><span class="sxs-lookup"><span data-stu-id="bb79b-143">dueOn</span></span> | <span data-ttu-id="bb79b-144">DateTime</span><span class="sxs-lookup"><span data-stu-id="bb79b-144">DateTime</span></span> | <span data-ttu-id="bb79b-145">Data di scadenza impostata dal creatore per questa attività di correzione</span><span class="sxs-lookup"><span data-stu-id="bb79b-145">Due date the creator set for this remediation activity</span></span> | <span data-ttu-id="bb79b-146">2021-01-13T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="bb79b-146">2021-01-13T00:00:00Z</span></span>
<span data-ttu-id="bb79b-147">fixedDevices</span><span class="sxs-lookup"><span data-stu-id="bb79b-147">fixedDevices</span></span> | <span data-ttu-id="bb79b-148">.</span><span class="sxs-lookup"><span data-stu-id="bb79b-148">.</span></span> | <span data-ttu-id="bb79b-149">Il numero di dispositivi che sono stati corretti</span><span class="sxs-lookup"><span data-stu-id="bb79b-149">The number of devices that have been fixed</span></span> | <span data-ttu-id="bb79b-150">2</span><span class="sxs-lookup"><span data-stu-id="bb79b-150">2</span></span>
<span data-ttu-id="bb79b-151">id</span><span class="sxs-lookup"><span data-stu-id="bb79b-151">id</span></span> | <span data-ttu-id="bb79b-152">Stringa</span><span class="sxs-lookup"><span data-stu-id="bb79b-152">String</span></span> | <span data-ttu-id="bb79b-153">ID di questa attività di correzione</span><span class="sxs-lookup"><span data-stu-id="bb79b-153">ID of this remediation activity</span></span> | <span data-ttu-id="bb79b-154">097d9735-5479-4899-b1b7-77398899df92</span><span class="sxs-lookup"><span data-stu-id="bb79b-154">097d9735-5479-4899-b1b7-77398899df92</span></span>
<span data-ttu-id="bb79b-155">nameId</span><span class="sxs-lookup"><span data-stu-id="bb79b-155">nameId</span></span> | <span data-ttu-id="bb79b-156">Stringa</span><span class="sxs-lookup"><span data-stu-id="bb79b-156">String</span></span> | <span data-ttu-id="bb79b-157">Nome prodotto correlato</span><span class="sxs-lookup"><span data-stu-id="bb79b-157">Related product name</span></span> | <span data-ttu-id="bb79b-158">chrome</span><span class="sxs-lookup"><span data-stu-id="bb79b-158">chrome</span></span>
<span data-ttu-id="bb79b-159">priority</span><span class="sxs-lookup"><span data-stu-id="bb79b-159">priority</span></span> | <span data-ttu-id="bb79b-160">Stringa</span><span class="sxs-lookup"><span data-stu-id="bb79b-160">String</span></span> | <span data-ttu-id="bb79b-161">Priorità impostata dal creatore per questa attività di correzione (High\Medium\Low)</span><span class="sxs-lookup"><span data-stu-id="bb79b-161">Priority the creator set for this remediation activity (High\Medium\Low)</span></span> | <span data-ttu-id="bb79b-162">Alto</span><span class="sxs-lookup"><span data-stu-id="bb79b-162">High</span></span>
<span data-ttu-id="bb79b-163">productId</span><span class="sxs-lookup"><span data-stu-id="bb79b-163">productId</span></span> | <span data-ttu-id="bb79b-164">Stringa</span><span class="sxs-lookup"><span data-stu-id="bb79b-164">String</span></span> | <span data-ttu-id="bb79b-165">ID prodotto correlato</span><span class="sxs-lookup"><span data-stu-id="bb79b-165">Related product ID</span></span> | <span data-ttu-id="bb79b-166">google-_-chrome</span><span class="sxs-lookup"><span data-stu-id="bb79b-166">google-_-chrome</span></span>
<span data-ttu-id="bb79b-167">productivityImpactRemediationType</span><span class="sxs-lookup"><span data-stu-id="bb79b-167">productivityImpactRemediationType</span></span> | <span data-ttu-id="bb79b-168">Stringa</span><span class="sxs-lookup"><span data-stu-id="bb79b-168">String</span></span> | <span data-ttu-id="bb79b-169">Alcune modifiche alla configurazione potrebbero essere richieste solo per i dispositivi senza alcun impatto sull'utente.</span><span class="sxs-lookup"><span data-stu-id="bb79b-169">A few configuration changes could be requested only for devices with no user impact.</span></span> <span data-ttu-id="bb79b-170">Questo valore indica la selezione tra "tutti i dispositivi esposti" o "solo i dispositivi senza impatto sull'utente".</span><span class="sxs-lookup"><span data-stu-id="bb79b-170">This value indicate the selection between “all exposed devices” or “only devices with no user impact.”</span></span> | <span data-ttu-id="bb79b-171">AllExposedAssets</span><span class="sxs-lookup"><span data-stu-id="bb79b-171">AllExposedAssets</span></span>
<span data-ttu-id="bb79b-172">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="bb79b-172">rbacGroupNames</span></span> | <span data-ttu-id="bb79b-173">Stringa</span><span class="sxs-lookup"><span data-stu-id="bb79b-173">String</span></span> | <span data-ttu-id="bb79b-174">Nomi dei gruppi di dispositivi correlati</span><span class="sxs-lookup"><span data-stu-id="bb79b-174">Related device group names</span></span> | <span data-ttu-id="bb79b-175">[ "Windows Servers", "Windows 10" ]</span><span class="sxs-lookup"><span data-stu-id="bb79b-175">[ "Windows Servers", "Windows 10" ]</span></span>
<span data-ttu-id="bb79b-176">recommendedProgram</span><span class="sxs-lookup"><span data-stu-id="bb79b-176">recommendedProgram</span></span> | <span data-ttu-id="bb79b-177">Stringa</span><span class="sxs-lookup"><span data-stu-id="bb79b-177">String</span></span> | <span data-ttu-id="bb79b-178">Programma consigliato a cui eseguire l'aggiornamento</span><span class="sxs-lookup"><span data-stu-id="bb79b-178">Recommended program to upgrade to</span></span> | <span data-ttu-id="bb79b-179">null</span><span class="sxs-lookup"><span data-stu-id="bb79b-179">null</span></span>
<span data-ttu-id="bb79b-180">recommendedVendor</span><span class="sxs-lookup"><span data-stu-id="bb79b-180">recommendedVendor</span></span> | <span data-ttu-id="bb79b-181">Stringa</span><span class="sxs-lookup"><span data-stu-id="bb79b-181">String</span></span> | <span data-ttu-id="bb79b-182">Fornitore consigliato a cui eseguire l'aggiornamento</span><span class="sxs-lookup"><span data-stu-id="bb79b-182">Recommended vendor to upgrade to</span></span> | <span data-ttu-id="bb79b-183">null</span><span class="sxs-lookup"><span data-stu-id="bb79b-183">null</span></span>
<span data-ttu-id="bb79b-184">recommendedVersion</span><span class="sxs-lookup"><span data-stu-id="bb79b-184">recommendedVersion</span></span> | <span data-ttu-id="bb79b-185">Stringa</span><span class="sxs-lookup"><span data-stu-id="bb79b-185">String</span></span> | <span data-ttu-id="bb79b-186">Versione consigliata per l'aggiornamento/aggiornamento</span><span class="sxs-lookup"><span data-stu-id="bb79b-186">Recommended version to update/upgrade to</span></span> | <span data-ttu-id="bb79b-187">null</span><span class="sxs-lookup"><span data-stu-id="bb79b-187">null</span></span>
<span data-ttu-id="bb79b-188">relatedComponent</span><span class="sxs-lookup"><span data-stu-id="bb79b-188">relatedComponent</span></span> | <span data-ttu-id="bb79b-189">Stringa</span><span class="sxs-lookup"><span data-stu-id="bb79b-189">String</span></span> | <span data-ttu-id="bb79b-190">Componente correlato di questa attività di correzione (simile al componente correlato per una raccomandazione sulla sicurezza)</span><span class="sxs-lookup"><span data-stu-id="bb79b-190">Related component of this remediation activity (similar to the related component for a security recommendation)</span></span> | <span data-ttu-id="bb79b-191">Google Chrome</span><span class="sxs-lookup"><span data-stu-id="bb79b-191">Google Chrome</span></span>
<span data-ttu-id="bb79b-192">requesterEmail</span><span class="sxs-lookup"><span data-stu-id="bb79b-192">requesterEmail</span></span> | <span data-ttu-id="bb79b-193">Stringa</span><span class="sxs-lookup"><span data-stu-id="bb79b-193">String</span></span> | <span data-ttu-id="bb79b-194">Indirizzo di posta elettronica creatore</span><span class="sxs-lookup"><span data-stu-id="bb79b-194">Creator email address</span></span> | <span data-ttu-id="bb79b-195">globaladmin@UserName.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bb79b-195">globaladmin@UserName.contoso.com</span></span>
<span data-ttu-id="bb79b-196">requesterId</span><span class="sxs-lookup"><span data-stu-id="bb79b-196">requesterId</span></span> | <span data-ttu-id="bb79b-197">Stringa</span><span class="sxs-lookup"><span data-stu-id="bb79b-197">String</span></span> | <span data-ttu-id="bb79b-198">ID oggetto creatore</span><span class="sxs-lookup"><span data-stu-id="bb79b-198">Creator object id</span></span> | <span data-ttu-id="bb79b-199">r647211f-2e16-43f2-a480-16ar3a2a796r</span><span class="sxs-lookup"><span data-stu-id="bb79b-199">r647211f-2e16-43f2-a480-16ar3a2a796r</span></span>
<span data-ttu-id="bb79b-200">requesterNotes</span><span class="sxs-lookup"><span data-stu-id="bb79b-200">requesterNotes</span></span> | <span data-ttu-id="bb79b-201">Stringa</span><span class="sxs-lookup"><span data-stu-id="bb79b-201">String</span></span> | <span data-ttu-id="bb79b-202">Note (testo libero) aggiunte dall'autore per questa attività di correzione</span><span class="sxs-lookup"><span data-stu-id="bb79b-202">The notes (free text) the creator added for this remediation activity</span></span> | <span data-ttu-id="bb79b-203">null</span><span class="sxs-lookup"><span data-stu-id="bb79b-203">null</span></span>
<span data-ttu-id="bb79b-204">scid</span><span class="sxs-lookup"><span data-stu-id="bb79b-204">scid</span></span> | <span data-ttu-id="bb79b-205">Stringa</span><span class="sxs-lookup"><span data-stu-id="bb79b-205">String</span></span> | <span data-ttu-id="bb79b-206">SCID della raccomandazione relativa alla sicurezza</span><span class="sxs-lookup"><span data-stu-id="bb79b-206">SCID of the related security recommendation</span></span> | <span data-ttu-id="bb79b-207">null</span><span class="sxs-lookup"><span data-stu-id="bb79b-207">null</span></span>
<span data-ttu-id="bb79b-208">status</span><span class="sxs-lookup"><span data-stu-id="bb79b-208">status</span></span> | <span data-ttu-id="bb79b-209">Stringa</span><span class="sxs-lookup"><span data-stu-id="bb79b-209">String</span></span> | <span data-ttu-id="bb79b-210">Stato attività di correzione (Attivo/Completato)</span><span class="sxs-lookup"><span data-stu-id="bb79b-210">Remediation activity status (Active/Completed)</span></span> | <span data-ttu-id="bb79b-211">Attivo</span><span class="sxs-lookup"><span data-stu-id="bb79b-211">Active</span></span>
<span data-ttu-id="bb79b-212">statusLastModifiedOn</span><span class="sxs-lookup"><span data-stu-id="bb79b-212">statusLastModifiedOn</span></span> | <span data-ttu-id="bb79b-213">DateTime</span><span class="sxs-lookup"><span data-stu-id="bb79b-213">DateTime</span></span> | <span data-ttu-id="bb79b-214">Data in cui il campo stato è stato aggiornato</span><span class="sxs-lookup"><span data-stu-id="bb79b-214">Date when the status field was updated</span></span> | <span data-ttu-id="bb79b-215">2021-01-12T18:54:11.5499487Z</span><span class="sxs-lookup"><span data-stu-id="bb79b-215">2021-01-12T18:54:11.5499487Z</span></span>
<span data-ttu-id="bb79b-216">targetDevices</span><span class="sxs-lookup"><span data-stu-id="bb79b-216">targetDevices</span></span> | <span data-ttu-id="bb79b-217">Long</span><span class="sxs-lookup"><span data-stu-id="bb79b-217">Long</span></span> | <span data-ttu-id="bb79b-218">Numero di dispositivi esposti a cui è applicabile questa correzione</span><span class="sxs-lookup"><span data-stu-id="bb79b-218">Number of exposed devices that this remediation is applicable to</span></span> | <span data-ttu-id="bb79b-219">43</span><span class="sxs-lookup"><span data-stu-id="bb79b-219">43</span></span>
<span data-ttu-id="bb79b-220">title</span><span class="sxs-lookup"><span data-stu-id="bb79b-220">title</span></span> | <span data-ttu-id="bb79b-221">Stringa</span><span class="sxs-lookup"><span data-stu-id="bb79b-221">String</span></span> | <span data-ttu-id="bb79b-222">Titolo di questa attività di correzione</span><span class="sxs-lookup"><span data-stu-id="bb79b-222">Title of this remediation activity</span></span> | <span data-ttu-id="bb79b-223">Aggiornare Google Chrome</span><span class="sxs-lookup"><span data-stu-id="bb79b-223">Update Google Chrome</span></span>
<span data-ttu-id="bb79b-224">type</span><span class="sxs-lookup"><span data-stu-id="bb79b-224">type</span></span> | <span data-ttu-id="bb79b-225">Stringa</span><span class="sxs-lookup"><span data-stu-id="bb79b-225">String</span></span> | <span data-ttu-id="bb79b-226">Tipo di correzione</span><span class="sxs-lookup"><span data-stu-id="bb79b-226">Remediation type</span></span> | <span data-ttu-id="bb79b-227">Update</span><span class="sxs-lookup"><span data-stu-id="bb79b-227">Update</span></span>
<span data-ttu-id="bb79b-228">vendorId</span><span class="sxs-lookup"><span data-stu-id="bb79b-228">vendorId</span></span> | <span data-ttu-id="bb79b-229">Stringa</span><span class="sxs-lookup"><span data-stu-id="bb79b-229">String</span></span> | <span data-ttu-id="bb79b-230">Nome fornitore correlato</span><span class="sxs-lookup"><span data-stu-id="bb79b-230">Related vendor name</span></span> | <span data-ttu-id="bb79b-231">google</span><span class="sxs-lookup"><span data-stu-id="bb79b-231">google</span></span>

## <a name="example"></a><span data-ttu-id="bb79b-232">Esempio</span><span class="sxs-lookup"><span data-stu-id="bb79b-232">Example</span></span>

<span data-ttu-id="bb79b-233">**Esempio di** richiesta</span><span class="sxs-lookup"><span data-stu-id="bb79b-233">**Request** example</span></span>

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/
```

<span data-ttu-id="bb79b-234">**Esempio di** risposta</span><span class="sxs-lookup"><span data-stu-id="bb79b-234">**Response** example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="bb79b-235">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bb79b-235">See also</span></span>

- [<span data-ttu-id="bb79b-236">Metodi e proprietà di correzione</span><span class="sxs-lookup"><span data-stu-id="bb79b-236">Remediation methods and properties</span></span>](get-remediation-methods-properties.md)

- [<span data-ttu-id="bb79b-237">Ottenere un'attività di correzione in base all'ID</span><span class="sxs-lookup"><span data-stu-id="bb79b-237">Get one remediation activity by Id</span></span>](get-remediation-one-activity.md)

- [<span data-ttu-id="bb79b-238">Elencare i dispositivi esposti di un'attività di correzione</span><span class="sxs-lookup"><span data-stu-id="bb79b-238">List exposed devices of one remediation activity</span></span>](get-remediation-exposed-devices-activities.md)

- [<span data-ttu-id="bb79b-239">Gestione delle vulnerabilità & rischio</span><span class="sxs-lookup"><span data-stu-id="bb79b-239">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="bb79b-240">Vulnerabilità nell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="bb79b-240">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
