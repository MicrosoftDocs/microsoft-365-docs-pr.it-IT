---
title: Ottenere un'attività di correzione in base all'ID
description: Restituisce informazioni per l'attività di correzione specificata.
keywords: api, correzione, api di correzione, ottenere, attività di correzione, elenco
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
ms.openlocfilehash: 40a7102a8c7dbf63641daaf47bbd9aa9f2e54649
ms.sourcegitcommit: e5b1a900043e2e41650ea1cbf4227043729c6053
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2021
ms.locfileid: "52061165"
---
# <a name="get-one-remediation-activity-by-id"></a><span data-ttu-id="df15f-104">Ottenere un'attività di correzione in base all'ID</span><span class="sxs-lookup"><span data-stu-id="df15f-104">Get one remediation activity by Id</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="df15f-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="df15f-105">**Applies to:**</span></span>

- [<span data-ttu-id="df15f-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="df15f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="df15f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="df15f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="df15f-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="df15f-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="df15f-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="df15f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="df15f-110">Descrizione API</span><span class="sxs-lookup"><span data-stu-id="df15f-110">API description</span></span>

<span data-ttu-id="df15f-111">Restituisce informazioni per l'attività di correzione specificata.</span><span class="sxs-lookup"><span data-stu-id="df15f-111">Returns information for the specified remediation activity.</span></span> <span data-ttu-id="df15f-112">Presenta le stesse colonne di [Get all remediation activity](get-remediation-all-activities.md), ma restituisce i risultati solo per l'attività di correzione _specificata._</span><span class="sxs-lookup"><span data-stu-id="df15f-112">Presents the same columns as [Get all remediation activity](get-remediation-all-activities.md)", but returns results _only for the one specified remediation activity_.</span></span>

<span data-ttu-id="df15f-113">[Ulteriori informazioni sulle attività di correzione.](tvm-remediation.md)</span><span class="sxs-lookup"><span data-stu-id="df15f-113">[Learn more about remediation activities](tvm-remediation.md).</span></span>

## <a name="list-a-specified-remediation-activity-for-id"></a><span data-ttu-id="df15f-114">Elencare un'attività di correzione specificata per (id)</span><span class="sxs-lookup"><span data-stu-id="df15f-114">List a specified remediation activity for (id)</span></span>

<span data-ttu-id="df15f-115">**URL:** GET: /api/remediationTasks/ \{ id\}</span><span class="sxs-lookup"><span data-stu-id="df15f-115">**URL:** GET: /api/remediationTasks/\{id\}</span></span>

<span data-ttu-id="df15f-116">**Dettagli proprietà**</span><span class="sxs-lookup"><span data-stu-id="df15f-116">**Properties** details</span></span>

<span data-ttu-id="df15f-117">Proprietà (id)</span><span class="sxs-lookup"><span data-stu-id="df15f-117">Property (id)</span></span> | <span data-ttu-id="df15f-118">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="df15f-118">Data type</span></span> | <span data-ttu-id="df15f-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="df15f-119">Description</span></span> | <span data-ttu-id="df15f-120">Esempio di valore restituito</span><span class="sxs-lookup"><span data-stu-id="df15f-120">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="df15f-121">category</span><span class="sxs-lookup"><span data-stu-id="df15f-121">category</span></span> | <span data-ttu-id="df15f-122">Stringa</span><span class="sxs-lookup"><span data-stu-id="df15f-122">String</span></span> | <span data-ttu-id="df15f-123">Categoria dell'attività di correzione (configurazione software/sicurezza)</span><span class="sxs-lookup"><span data-stu-id="df15f-123">Category of the remediation activity (Software/Security configuration)</span></span> | <span data-ttu-id="df15f-124">Software</span><span class="sxs-lookup"><span data-stu-id="df15f-124">Software</span></span>
<span data-ttu-id="df15f-125">completerEmail</span><span class="sxs-lookup"><span data-stu-id="df15f-125">completerEmail</span></span> | <span data-ttu-id="df15f-126">Stringa</span><span class="sxs-lookup"><span data-stu-id="df15f-126">String</span></span> | <span data-ttu-id="df15f-127">Se l'attività di correzione è stata completata manualmente da un utente, questa colonna contiene il messaggio di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="df15f-127">If the remediation activity was manually completed by someone, this column contains their email</span></span> | <span data-ttu-id="df15f-128">null</span><span class="sxs-lookup"><span data-stu-id="df15f-128">null</span></span>
<span data-ttu-id="df15f-129">completerId</span><span class="sxs-lookup"><span data-stu-id="df15f-129">completerId</span></span> | <span data-ttu-id="df15f-130">Stringa</span><span class="sxs-lookup"><span data-stu-id="df15f-130">String</span></span> | <span data-ttu-id="df15f-131">Se l'attività di correzione è stata completata manualmente da un utente, questa colonna contiene l'ID oggetto</span><span class="sxs-lookup"><span data-stu-id="df15f-131">If the remediation activity was manually completed by someone, this column contains their object id</span></span> | <span data-ttu-id="df15f-132">null</span><span class="sxs-lookup"><span data-stu-id="df15f-132">null</span></span>
<span data-ttu-id="df15f-133">completionMethod</span><span class="sxs-lookup"><span data-stu-id="df15f-133">completionMethod</span></span> | <span data-ttu-id="df15f-134">Stringa</span><span class="sxs-lookup"><span data-stu-id="df15f-134">String</span></span> | <span data-ttu-id="df15f-135">Un'attività di correzione può essere completata "automaticamente" (se tutti i dispositivi sono patchati) o "manualmente" da una persona che seleziona "contrassegna come completata"</span><span class="sxs-lookup"><span data-stu-id="df15f-135">A remediation activity can be completed “automatically” (if all the devices are patched) or “manually” by a person who selects “mark as completed”</span></span> | <span data-ttu-id="df15f-136">Automatica</span><span class="sxs-lookup"><span data-stu-id="df15f-136">Automatic</span></span>
<span data-ttu-id="df15f-137">createdOn</span><span class="sxs-lookup"><span data-stu-id="df15f-137">createdOn</span></span> | <span data-ttu-id="df15f-138">DateTime</span><span class="sxs-lookup"><span data-stu-id="df15f-138">DateTime</span></span> | <span data-ttu-id="df15f-139">Ora in cui è stata creata questa attività di correzione</span><span class="sxs-lookup"><span data-stu-id="df15f-139">Time this remediation activity was created</span></span> | <span data-ttu-id="df15f-140">2021-01-12T18:54:11.5499478Z</span><span class="sxs-lookup"><span data-stu-id="df15f-140">2021-01-12T18:54:11.5499478Z</span></span>
<span data-ttu-id="df15f-141">descrizione</span><span class="sxs-lookup"><span data-stu-id="df15f-141">description</span></span> | <span data-ttu-id="df15f-142">Stringa</span><span class="sxs-lookup"><span data-stu-id="df15f-142">String</span></span> | <span data-ttu-id="df15f-143">Descrizione di questa attività di correzione</span><span class="sxs-lookup"><span data-stu-id="df15f-143">Description of this remediation activity</span></span> | <span data-ttu-id="df15f-144">Aggiornare Chrome a una versione successiva per ridurre le 1248 vulnerabilità note che interessano i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="df15f-144">Update Chrome to a later version to mitigate 1248 known vulnerabilities affecting your devices.</span></span>
<span data-ttu-id="df15f-145">dueOn</span><span class="sxs-lookup"><span data-stu-id="df15f-145">dueOn</span></span> | <span data-ttu-id="df15f-146">DateTime</span><span class="sxs-lookup"><span data-stu-id="df15f-146">DateTime</span></span> | <span data-ttu-id="df15f-147">Data di scadenza impostata dal creatore per questa attività di correzione</span><span class="sxs-lookup"><span data-stu-id="df15f-147">Due date the creator set for this remediation activity</span></span> | <span data-ttu-id="df15f-148">2021-01-13T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="df15f-148">2021-01-13T00:00:00Z</span></span>
<span data-ttu-id="df15f-149">fixedDevices</span><span class="sxs-lookup"><span data-stu-id="df15f-149">fixedDevices</span></span> |  | <span data-ttu-id="df15f-150">Il numero di dispositivi che sono stati corretti</span><span class="sxs-lookup"><span data-stu-id="df15f-150">The number of devices that have been fixed</span></span> | <span data-ttu-id="df15f-151">2</span><span class="sxs-lookup"><span data-stu-id="df15f-151">2</span></span>
<span data-ttu-id="df15f-152">id</span><span class="sxs-lookup"><span data-stu-id="df15f-152">id</span></span> | <span data-ttu-id="df15f-153">Stringa</span><span class="sxs-lookup"><span data-stu-id="df15f-153">String</span></span> | <span data-ttu-id="df15f-154">ID di questa attività di correzione</span><span class="sxs-lookup"><span data-stu-id="df15f-154">ID of this remediation activity</span></span> | <span data-ttu-id="df15f-155">097d9735-5479-4899-b1b7-77398899df92</span><span class="sxs-lookup"><span data-stu-id="df15f-155">097d9735-5479-4899-b1b7-77398899df92</span></span>
<span data-ttu-id="df15f-156">nameId</span><span class="sxs-lookup"><span data-stu-id="df15f-156">nameId</span></span> | <span data-ttu-id="df15f-157">Stringa</span><span class="sxs-lookup"><span data-stu-id="df15f-157">String</span></span> | <span data-ttu-id="df15f-158">Nome prodotto correlato</span><span class="sxs-lookup"><span data-stu-id="df15f-158">Related product name</span></span> | <span data-ttu-id="df15f-159">chrome</span><span class="sxs-lookup"><span data-stu-id="df15f-159">chrome</span></span>
<span data-ttu-id="df15f-160">priority</span><span class="sxs-lookup"><span data-stu-id="df15f-160">priority</span></span> | <span data-ttu-id="df15f-161">Stringa</span><span class="sxs-lookup"><span data-stu-id="df15f-161">String</span></span> | <span data-ttu-id="df15f-162">Priorità impostata dal creatore per questa attività di correzione (High\Medium\Low)</span><span class="sxs-lookup"><span data-stu-id="df15f-162">Priority the creator set for this remediation activity (High\Medium\Low)</span></span> | <span data-ttu-id="df15f-163">Alto</span><span class="sxs-lookup"><span data-stu-id="df15f-163">High</span></span>
<span data-ttu-id="df15f-164">productId</span><span class="sxs-lookup"><span data-stu-id="df15f-164">productId</span></span> | <span data-ttu-id="df15f-165">Stringa</span><span class="sxs-lookup"><span data-stu-id="df15f-165">String</span></span> | <span data-ttu-id="df15f-166">ID prodotto correlato</span><span class="sxs-lookup"><span data-stu-id="df15f-166">Related product ID</span></span> | <span data-ttu-id="df15f-167">google-_-chrome</span><span class="sxs-lookup"><span data-stu-id="df15f-167">google-_-chrome</span></span>
<span data-ttu-id="df15f-168">productivityImpactRemediationType</span><span class="sxs-lookup"><span data-stu-id="df15f-168">productivityImpactRemediationType</span></span> | <span data-ttu-id="df15f-169">Stringa</span><span class="sxs-lookup"><span data-stu-id="df15f-169">String</span></span> | <span data-ttu-id="df15f-170">Alcune modifiche alla configurazione potrebbero essere richieste solo per i dispositivi senza alcun impatto sull'utente.</span><span class="sxs-lookup"><span data-stu-id="df15f-170">A few configuration changes could be requested only for devices with no user impact.</span></span> <span data-ttu-id="df15f-171">Questo valore indica la selezione tra "tutti i dispositivi esposti" o "solo i dispositivi senza impatto sull'utente".</span><span class="sxs-lookup"><span data-stu-id="df15f-171">This value indicate the selection between “all exposed devices” or “only devices with no user impact.”</span></span> | <span data-ttu-id="df15f-172">AllExposedAssets</span><span class="sxs-lookup"><span data-stu-id="df15f-172">AllExposedAssets</span></span>
<span data-ttu-id="df15f-173">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="df15f-173">rbacGroupNames</span></span> | <span data-ttu-id="df15f-174">Stringa</span><span class="sxs-lookup"><span data-stu-id="df15f-174">String</span></span> | <span data-ttu-id="df15f-175">Nomi dei gruppi di dispositivi correlati</span><span class="sxs-lookup"><span data-stu-id="df15f-175">Related device group names</span></span> | <span data-ttu-id="df15f-176">[ "Windows Servers", "Windows 10" ]</span><span class="sxs-lookup"><span data-stu-id="df15f-176">[ "Windows Servers", "Windows 10" ]</span></span>
<span data-ttu-id="df15f-177">recommendedProgram</span><span class="sxs-lookup"><span data-stu-id="df15f-177">recommendedProgram</span></span> | <span data-ttu-id="df15f-178">Stringa</span><span class="sxs-lookup"><span data-stu-id="df15f-178">String</span></span> | <span data-ttu-id="df15f-179">Programma consigliato a cui eseguire l'aggiornamento</span><span class="sxs-lookup"><span data-stu-id="df15f-179">Recommended program to upgrade to</span></span> | <span data-ttu-id="df15f-180">null</span><span class="sxs-lookup"><span data-stu-id="df15f-180">null</span></span>
<span data-ttu-id="df15f-181">recommendedVendor</span><span class="sxs-lookup"><span data-stu-id="df15f-181">recommendedVendor</span></span> | <span data-ttu-id="df15f-182">Stringa</span><span class="sxs-lookup"><span data-stu-id="df15f-182">String</span></span> | <span data-ttu-id="df15f-183">Fornitore consigliato a cui eseguire l'aggiornamento</span><span class="sxs-lookup"><span data-stu-id="df15f-183">Recommended vendor to upgrade to</span></span> | <span data-ttu-id="df15f-184">null</span><span class="sxs-lookup"><span data-stu-id="df15f-184">null</span></span>
<span data-ttu-id="df15f-185">recommendedVersion</span><span class="sxs-lookup"><span data-stu-id="df15f-185">recommendedVersion</span></span> | <span data-ttu-id="df15f-186">Stringa</span><span class="sxs-lookup"><span data-stu-id="df15f-186">String</span></span> | <span data-ttu-id="df15f-187">Versione consigliata per l'aggiornamento/aggiornamento</span><span class="sxs-lookup"><span data-stu-id="df15f-187">Recommended version to update/upgrade to</span></span> | <span data-ttu-id="df15f-188">null</span><span class="sxs-lookup"><span data-stu-id="df15f-188">null</span></span>
<span data-ttu-id="df15f-189">relatedComponent</span><span class="sxs-lookup"><span data-stu-id="df15f-189">relatedComponent</span></span> | <span data-ttu-id="df15f-190">Stringa</span><span class="sxs-lookup"><span data-stu-id="df15f-190">String</span></span> | <span data-ttu-id="df15f-191">Componente correlato di questa attività di correzione (simile al componente correlato per una raccomandazione sulla sicurezza)</span><span class="sxs-lookup"><span data-stu-id="df15f-191">Related component of this remediation activity (similar to the related component for a security recommendation)</span></span> | <span data-ttu-id="df15f-192">Google Chrome</span><span class="sxs-lookup"><span data-stu-id="df15f-192">Google Chrome</span></span>
<span data-ttu-id="df15f-193">requesterEmail</span><span class="sxs-lookup"><span data-stu-id="df15f-193">requesterEmail</span></span> | <span data-ttu-id="df15f-194">Stringa</span><span class="sxs-lookup"><span data-stu-id="df15f-194">String</span></span> | <span data-ttu-id="df15f-195">Indirizzo di posta elettronica creatore</span><span class="sxs-lookup"><span data-stu-id="df15f-195">Creator email address</span></span> | <span data-ttu-id="df15f-196">globaladmin@UserName.contoso.com</span><span class="sxs-lookup"><span data-stu-id="df15f-196">globaladmin@UserName.contoso.com</span></span>
<span data-ttu-id="df15f-197">requesterId</span><span class="sxs-lookup"><span data-stu-id="df15f-197">requesterId</span></span> | <span data-ttu-id="df15f-198">Stringa</span><span class="sxs-lookup"><span data-stu-id="df15f-198">String</span></span> | <span data-ttu-id="df15f-199">ID oggetto creatore</span><span class="sxs-lookup"><span data-stu-id="df15f-199">Creator object id</span></span> | <span data-ttu-id="df15f-200">r647211f-2e16-43f2-a480-16ar3a2a796r</span><span class="sxs-lookup"><span data-stu-id="df15f-200">r647211f-2e16-43f2-a480-16ar3a2a796r</span></span>
<span data-ttu-id="df15f-201">requesterNotes</span><span class="sxs-lookup"><span data-stu-id="df15f-201">requesterNotes</span></span> | <span data-ttu-id="df15f-202">Stringa</span><span class="sxs-lookup"><span data-stu-id="df15f-202">String</span></span> | <span data-ttu-id="df15f-203">Note (testo libero) aggiunte dall'autore per questa attività di correzione</span><span class="sxs-lookup"><span data-stu-id="df15f-203">The notes (free text) the creator added for this remediation activity</span></span> | <span data-ttu-id="df15f-204">null</span><span class="sxs-lookup"><span data-stu-id="df15f-204">null</span></span>
<span data-ttu-id="df15f-205">scid</span><span class="sxs-lookup"><span data-stu-id="df15f-205">scid</span></span> | <span data-ttu-id="df15f-206">Stringa</span><span class="sxs-lookup"><span data-stu-id="df15f-206">String</span></span> | <span data-ttu-id="df15f-207">SCID della raccomandazione relativa alla sicurezza</span><span class="sxs-lookup"><span data-stu-id="df15f-207">SCID of the related security recommendation</span></span> | <span data-ttu-id="df15f-208">null</span><span class="sxs-lookup"><span data-stu-id="df15f-208">null</span></span>
<span data-ttu-id="df15f-209">status</span><span class="sxs-lookup"><span data-stu-id="df15f-209">status</span></span> | <span data-ttu-id="df15f-210">Stringa</span><span class="sxs-lookup"><span data-stu-id="df15f-210">String</span></span> | <span data-ttu-id="df15f-211">Stato attività di correzione (Attivo/Completato)</span><span class="sxs-lookup"><span data-stu-id="df15f-211">Remediation activity status (Active/Completed)</span></span> | <span data-ttu-id="df15f-212">Attivo</span><span class="sxs-lookup"><span data-stu-id="df15f-212">Active</span></span>
<span data-ttu-id="df15f-213">statusLastModifiedOn</span><span class="sxs-lookup"><span data-stu-id="df15f-213">statusLastModifiedOn</span></span> | <span data-ttu-id="df15f-214">DateTime</span><span class="sxs-lookup"><span data-stu-id="df15f-214">DateTime</span></span> | <span data-ttu-id="df15f-215">Data in cui il campo stato è stato aggiornato</span><span class="sxs-lookup"><span data-stu-id="df15f-215">Date when the status field was updated</span></span> | <span data-ttu-id="df15f-216">2021-01-12T18:54:11.5499487Z</span><span class="sxs-lookup"><span data-stu-id="df15f-216">2021-01-12T18:54:11.5499487Z</span></span>
<span data-ttu-id="df15f-217">targetDevices</span><span class="sxs-lookup"><span data-stu-id="df15f-217">targetDevices</span></span> | <span data-ttu-id="df15f-218">Long</span><span class="sxs-lookup"><span data-stu-id="df15f-218">Long</span></span> | <span data-ttu-id="df15f-219">Numero di dispositivi esposti a cui è applicabile questa correzione</span><span class="sxs-lookup"><span data-stu-id="df15f-219">Number of exposed devices that this remediation is applicable to</span></span> | <span data-ttu-id="df15f-220">43</span><span class="sxs-lookup"><span data-stu-id="df15f-220">43</span></span>
<span data-ttu-id="df15f-221">title</span><span class="sxs-lookup"><span data-stu-id="df15f-221">title</span></span> | <span data-ttu-id="df15f-222">Stringa</span><span class="sxs-lookup"><span data-stu-id="df15f-222">String</span></span> | <span data-ttu-id="df15f-223">Titolo di questa attività di correzione</span><span class="sxs-lookup"><span data-stu-id="df15f-223">Title of this remediation activity</span></span> | <span data-ttu-id="df15f-224">Aggiornare Google Chrome</span><span class="sxs-lookup"><span data-stu-id="df15f-224">Update Google Chrome</span></span>
<span data-ttu-id="df15f-225">type</span><span class="sxs-lookup"><span data-stu-id="df15f-225">type</span></span> | <span data-ttu-id="df15f-226">Stringa</span><span class="sxs-lookup"><span data-stu-id="df15f-226">String</span></span> | <span data-ttu-id="df15f-227">Tipo di correzione</span><span class="sxs-lookup"><span data-stu-id="df15f-227">Remediation type</span></span> | <span data-ttu-id="df15f-228">Update</span><span class="sxs-lookup"><span data-stu-id="df15f-228">Update</span></span>
<span data-ttu-id="df15f-229">vendorId</span><span class="sxs-lookup"><span data-stu-id="df15f-229">vendorId</span></span> | <span data-ttu-id="df15f-230">Stringa</span><span class="sxs-lookup"><span data-stu-id="df15f-230">String</span></span> | <span data-ttu-id="df15f-231">Nome fornitore correlato</span><span class="sxs-lookup"><span data-stu-id="df15f-231">Related vendor name</span></span> | <span data-ttu-id="df15f-232">google</span><span class="sxs-lookup"><span data-stu-id="df15f-232">google</span></span>

## <a name="example"></a><span data-ttu-id="df15f-233">Esempio</span><span class="sxs-lookup"><span data-stu-id="df15f-233">Example</span></span>

<span data-ttu-id="df15f-234">**Esempio di** richiesta</span><span class="sxs-lookup"><span data-stu-id="df15f-234">**Request** example</span></span>

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/03942ef5-aecb-4c6e-b555-d6a97013844c
```

<span data-ttu-id="df15f-235">**Esempio di** risposta</span><span class="sxs-lookup"><span data-stu-id="df15f-235">**Response** example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="df15f-236">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="df15f-236">See also</span></span>

- [<span data-ttu-id="df15f-237">Metodi e proprietà di correzione</span><span class="sxs-lookup"><span data-stu-id="df15f-237">Remediation methods and properties</span></span>](get-remediation-methods-properties.md)

- [<span data-ttu-id="df15f-238">Elencare tutte le attività di correzione</span><span class="sxs-lookup"><span data-stu-id="df15f-238">List all remediation activities</span></span>](get-remediation-all-activities.md)

- [<span data-ttu-id="df15f-239">Elencare i dispositivi esposti di un'attività di correzione</span><span class="sxs-lookup"><span data-stu-id="df15f-239">List exposed devices of one remediation activity</span></span>](get-remediation-exposed-devices-activities.md)

- [<span data-ttu-id="df15f-240">Gestione delle vulnerabilità & rischio</span><span class="sxs-lookup"><span data-stu-id="df15f-240">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="df15f-241">Vulnerabilità nell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="df15f-241">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
