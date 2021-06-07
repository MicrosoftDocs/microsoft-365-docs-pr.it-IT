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
ms.openlocfilehash: b95fa2da177a3ecb93bcf3e2085be6111c2c641e
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770518"
---
# <a name="list-all-remediation-activities"></a><span data-ttu-id="dd329-104">Elencare tutte le attività correttive</span><span class="sxs-lookup"><span data-stu-id="dd329-104">List all remediation activities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="dd329-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="dd329-105">**Applies to:**</span></span>

- [<span data-ttu-id="dd329-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="dd329-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="dd329-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dd329-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="dd329-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="dd329-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="dd329-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="dd329-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="dd329-110">Descrizione API</span><span class="sxs-lookup"><span data-stu-id="dd329-110">API description</span></span>

<span data-ttu-id="dd329-111">Restituisce informazioni su tutte le attività di correzione.</span><span class="sxs-lookup"><span data-stu-id="dd329-111">Returns information about all remediation activities.</span></span>

<span data-ttu-id="dd329-112">[Ulteriori informazioni sulle attività di correzione.](tvm-remediation.md)</span><span class="sxs-lookup"><span data-stu-id="dd329-112">[Learn more about remediation activities](tvm-remediation.md).</span></span>

<span data-ttu-id="dd329-113">**URL:** GET: /api/remediationTasks</span><span class="sxs-lookup"><span data-stu-id="dd329-113">**URL:** GET: /api/remediationTasks</span></span>

## <a name="permissions"></a><span data-ttu-id="dd329-114">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="dd329-114">Permissions</span></span>

<span data-ttu-id="dd329-115">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="dd329-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="dd329-116">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi Usare Le API di [Microsoft Defender per endpoint per i dettagli.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="dd329-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="dd329-117">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="dd329-117">Permission type</span></span> | <span data-ttu-id="dd329-118">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="dd329-118">Permission</span></span> | <span data-ttu-id="dd329-119">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="dd329-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="dd329-120">Applicazione</span><span class="sxs-lookup"><span data-stu-id="dd329-120">Application</span></span> | <span data-ttu-id="dd329-121">RemediationTask.Read.All</span><span class="sxs-lookup"><span data-stu-id="dd329-121">RemediationTask.Read.All</span></span> | <span data-ttu-id="dd329-122">\'Leggere informazioni sulla vulnerabilità di Gestione minacce e vulnerabilità\'</span><span class="sxs-lookup"><span data-stu-id="dd329-122">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="dd329-123">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="dd329-123">Delegated (work or school account)</span></span> | <span data-ttu-id="dd329-124">RemediationTask.Read.Read</span><span class="sxs-lookup"><span data-stu-id="dd329-124">RemediationTask.Read.Read</span></span> | <span data-ttu-id="dd329-125">\'Leggere informazioni sulla vulnerabilità di Gestione minacce e vulnerabilità\'</span><span class="sxs-lookup"><span data-stu-id="dd329-125">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

## <a name="properties"></a><span data-ttu-id="dd329-126">Proprietà</span><span class="sxs-lookup"><span data-stu-id="dd329-126">Properties</span></span>

<span data-ttu-id="dd329-127">Proprietà (id)</span><span class="sxs-lookup"><span data-stu-id="dd329-127">Property (id)</span></span> | <span data-ttu-id="dd329-128">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="dd329-128">Data type</span></span> | <span data-ttu-id="dd329-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dd329-129">Description</span></span> | <span data-ttu-id="dd329-130">Esempio di valore restituito</span><span class="sxs-lookup"><span data-stu-id="dd329-130">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="dd329-131">category</span><span class="sxs-lookup"><span data-stu-id="dd329-131">category</span></span> | <span data-ttu-id="dd329-132">Stringa</span><span class="sxs-lookup"><span data-stu-id="dd329-132">String</span></span> | <span data-ttu-id="dd329-133">Categoria dell'attività di correzione (configurazione software/sicurezza)</span><span class="sxs-lookup"><span data-stu-id="dd329-133">Category of the remediation activity (Software/Security configuration)</span></span> | <span data-ttu-id="dd329-134">Software</span><span class="sxs-lookup"><span data-stu-id="dd329-134">Software</span></span>
<span data-ttu-id="dd329-135">completerEmail</span><span class="sxs-lookup"><span data-stu-id="dd329-135">completerEmail</span></span> | <span data-ttu-id="dd329-136">Stringa</span><span class="sxs-lookup"><span data-stu-id="dd329-136">String</span></span> | <span data-ttu-id="dd329-137">Se l'attività di correzione è stata completata manualmente da un utente, questa colonna contiene il messaggio di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="dd329-137">If the remediation activity was manually completed by someone, this column contains their email</span></span> | <span data-ttu-id="dd329-138">null</span><span class="sxs-lookup"><span data-stu-id="dd329-138">null</span></span>
<span data-ttu-id="dd329-139">completerId</span><span class="sxs-lookup"><span data-stu-id="dd329-139">completerId</span></span> | <span data-ttu-id="dd329-140">Stringa</span><span class="sxs-lookup"><span data-stu-id="dd329-140">String</span></span> | <span data-ttu-id="dd329-141">Se l'attività di correzione è stata completata manualmente da un utente, questa colonna contiene l'ID oggetto</span><span class="sxs-lookup"><span data-stu-id="dd329-141">If the remediation activity was manually completed by someone, this column contains their object id</span></span> | <span data-ttu-id="dd329-142">null</span><span class="sxs-lookup"><span data-stu-id="dd329-142">null</span></span>
<span data-ttu-id="dd329-143">completionMethod</span><span class="sxs-lookup"><span data-stu-id="dd329-143">completionMethod</span></span> | <span data-ttu-id="dd329-144">Stringa</span><span class="sxs-lookup"><span data-stu-id="dd329-144">String</span></span> | <span data-ttu-id="dd329-145">Un'attività di correzione può essere completata "automaticamente" (se tutti i dispositivi sono patchati) o "manualmente" da una persona che seleziona "contrassegna come completata"</span><span class="sxs-lookup"><span data-stu-id="dd329-145">A remediation activity can be completed “automatically” (if all the devices are patched) or “manually” by a person who selects “mark as completed”</span></span> | <span data-ttu-id="dd329-146">Automatica</span><span class="sxs-lookup"><span data-stu-id="dd329-146">Automatic</span></span>
<span data-ttu-id="dd329-147">createdOn</span><span class="sxs-lookup"><span data-stu-id="dd329-147">createdOn</span></span> | <span data-ttu-id="dd329-148">DateTime</span><span class="sxs-lookup"><span data-stu-id="dd329-148">DateTime</span></span> | <span data-ttu-id="dd329-149">Ora in cui è stata creata questa attività di correzione</span><span class="sxs-lookup"><span data-stu-id="dd329-149">Time this remediation activity was created</span></span> | <span data-ttu-id="dd329-150">2021-01-12T18:54:11.5499478Z</span><span class="sxs-lookup"><span data-stu-id="dd329-150">2021-01-12T18:54:11.5499478Z</span></span>
<span data-ttu-id="dd329-151">descrizione</span><span class="sxs-lookup"><span data-stu-id="dd329-151">description</span></span> | <span data-ttu-id="dd329-152">Stringa</span><span class="sxs-lookup"><span data-stu-id="dd329-152">String</span></span> | <span data-ttu-id="dd329-153">Descrizione di questa attività di correzione</span><span class="sxs-lookup"><span data-stu-id="dd329-153">Description of this remediation activity</span></span> | <span data-ttu-id="dd329-154">Aggiornare Microsoft Silverlight a una versione successiva per ridurre le vulnerabilità note che interessano i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="dd329-154">Update Microsoft Silverlight  to a later version to mitigate known vulnerabilities affecting your devices.</span></span>
<span data-ttu-id="dd329-155">dueOn</span><span class="sxs-lookup"><span data-stu-id="dd329-155">dueOn</span></span> | <span data-ttu-id="dd329-156">DateTime</span><span class="sxs-lookup"><span data-stu-id="dd329-156">DateTime</span></span> | <span data-ttu-id="dd329-157">Data di scadenza impostata dal creatore per questa attività di correzione</span><span class="sxs-lookup"><span data-stu-id="dd329-157">Due date the creator set for this remediation activity</span></span> | <span data-ttu-id="dd329-158">2021-01-13T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="dd329-158">2021-01-13T00:00:00Z</span></span>
<span data-ttu-id="dd329-159">fixedDevices</span><span class="sxs-lookup"><span data-stu-id="dd329-159">fixedDevices</span></span> | <span data-ttu-id="dd329-160">.</span><span class="sxs-lookup"><span data-stu-id="dd329-160">.</span></span> | <span data-ttu-id="dd329-161">Il numero di dispositivi che sono stati corretti</span><span class="sxs-lookup"><span data-stu-id="dd329-161">The number of devices that have been fixed</span></span> | <span data-ttu-id="dd329-162">2</span><span class="sxs-lookup"><span data-stu-id="dd329-162">2</span></span>
<span data-ttu-id="dd329-163">id</span><span class="sxs-lookup"><span data-stu-id="dd329-163">id</span></span> | <span data-ttu-id="dd329-164">Stringa</span><span class="sxs-lookup"><span data-stu-id="dd329-164">String</span></span> | <span data-ttu-id="dd329-165">ID di questa attività di correzione</span><span class="sxs-lookup"><span data-stu-id="dd329-165">ID of this remediation activity</span></span> | <span data-ttu-id="dd329-166">097d9735-5479-4899-b1b7-77398899df92</span><span class="sxs-lookup"><span data-stu-id="dd329-166">097d9735-5479-4899-b1b7-77398899df92</span></span>
<span data-ttu-id="dd329-167">nameId</span><span class="sxs-lookup"><span data-stu-id="dd329-167">nameId</span></span> | <span data-ttu-id="dd329-168">Stringa</span><span class="sxs-lookup"><span data-stu-id="dd329-168">String</span></span> | <span data-ttu-id="dd329-169">Nome prodotto correlato</span><span class="sxs-lookup"><span data-stu-id="dd329-169">Related product name</span></span> | <span data-ttu-id="dd329-170">Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="dd329-170">Microsoft Silverlight</span></span>
<span data-ttu-id="dd329-171">priority</span><span class="sxs-lookup"><span data-stu-id="dd329-171">priority</span></span> | <span data-ttu-id="dd329-172">Stringa</span><span class="sxs-lookup"><span data-stu-id="dd329-172">String</span></span> | <span data-ttu-id="dd329-173">Priorità impostata dal creatore per questa attività di correzione (High\Medium\Low)</span><span class="sxs-lookup"><span data-stu-id="dd329-173">Priority the creator set for this remediation activity (High\Medium\Low)</span></span> | <span data-ttu-id="dd329-174">Alta</span><span class="sxs-lookup"><span data-stu-id="dd329-174">High</span></span>
<span data-ttu-id="dd329-175">productId</span><span class="sxs-lookup"><span data-stu-id="dd329-175">productId</span></span> | <span data-ttu-id="dd329-176">Stringa</span><span class="sxs-lookup"><span data-stu-id="dd329-176">String</span></span> | <span data-ttu-id="dd329-177">ID prodotto correlato</span><span class="sxs-lookup"><span data-stu-id="dd329-177">Related product ID</span></span> | <span data-ttu-id="dd329-178">microsoft-_-silverlight</span><span class="sxs-lookup"><span data-stu-id="dd329-178">microsoft-_-silverlight</span></span>
<span data-ttu-id="dd329-179">productivityImpactRemediationType</span><span class="sxs-lookup"><span data-stu-id="dd329-179">productivityImpactRemediationType</span></span> | <span data-ttu-id="dd329-180">Stringa</span><span class="sxs-lookup"><span data-stu-id="dd329-180">String</span></span> | <span data-ttu-id="dd329-181">Alcune modifiche alla configurazione potrebbero essere richieste solo per i dispositivi senza alcun impatto sull'utente.</span><span class="sxs-lookup"><span data-stu-id="dd329-181">A few configuration changes could be requested only for devices with no user impact.</span></span> <span data-ttu-id="dd329-182">Questo valore indica la selezione tra "tutti i dispositivi esposti" o "solo i dispositivi senza impatto sull'utente".</span><span class="sxs-lookup"><span data-stu-id="dd329-182">This value indicate the selection between “all exposed devices” or “only devices with no user impact.”</span></span> | <span data-ttu-id="dd329-183">AllExposedAssets</span><span class="sxs-lookup"><span data-stu-id="dd329-183">AllExposedAssets</span></span>
<span data-ttu-id="dd329-184">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="dd329-184">rbacGroupNames</span></span> | <span data-ttu-id="dd329-185">Stringa</span><span class="sxs-lookup"><span data-stu-id="dd329-185">String</span></span> | <span data-ttu-id="dd329-186">Nomi dei gruppi di dispositivi correlati</span><span class="sxs-lookup"><span data-stu-id="dd329-186">Related device group names</span></span> | <span data-ttu-id="dd329-187">[ "Windows Servers", "Windows 10" ]</span><span class="sxs-lookup"><span data-stu-id="dd329-187">[ "Windows Servers", "Windows 10" ]</span></span>
<span data-ttu-id="dd329-188">recommendedProgram</span><span class="sxs-lookup"><span data-stu-id="dd329-188">recommendedProgram</span></span> | <span data-ttu-id="dd329-189">Stringa</span><span class="sxs-lookup"><span data-stu-id="dd329-189">String</span></span> | <span data-ttu-id="dd329-190">Programma consigliato a cui eseguire l'aggiornamento</span><span class="sxs-lookup"><span data-stu-id="dd329-190">Recommended program to upgrade to</span></span> | <span data-ttu-id="dd329-191">null</span><span class="sxs-lookup"><span data-stu-id="dd329-191">null</span></span>
<span data-ttu-id="dd329-192">recommendedVendor</span><span class="sxs-lookup"><span data-stu-id="dd329-192">recommendedVendor</span></span> | <span data-ttu-id="dd329-193">Stringa</span><span class="sxs-lookup"><span data-stu-id="dd329-193">String</span></span> | <span data-ttu-id="dd329-194">Fornitore consigliato a cui eseguire l'aggiornamento</span><span class="sxs-lookup"><span data-stu-id="dd329-194">Recommended vendor to upgrade to</span></span> | <span data-ttu-id="dd329-195">null</span><span class="sxs-lookup"><span data-stu-id="dd329-195">null</span></span>
<span data-ttu-id="dd329-196">recommendedVersion</span><span class="sxs-lookup"><span data-stu-id="dd329-196">recommendedVersion</span></span> | <span data-ttu-id="dd329-197">Stringa</span><span class="sxs-lookup"><span data-stu-id="dd329-197">String</span></span> | <span data-ttu-id="dd329-198">Versione consigliata per l'aggiornamento/aggiornamento</span><span class="sxs-lookup"><span data-stu-id="dd329-198">Recommended version to update/upgrade to</span></span> | <span data-ttu-id="dd329-199">null</span><span class="sxs-lookup"><span data-stu-id="dd329-199">null</span></span>
<span data-ttu-id="dd329-200">relatedComponent</span><span class="sxs-lookup"><span data-stu-id="dd329-200">relatedComponent</span></span> | <span data-ttu-id="dd329-201">Stringa</span><span class="sxs-lookup"><span data-stu-id="dd329-201">String</span></span> | <span data-ttu-id="dd329-202">Componente correlato di questa attività di correzione (simile al componente correlato per una raccomandazione sulla sicurezza)</span><span class="sxs-lookup"><span data-stu-id="dd329-202">Related component of this remediation activity (similar to the related component for a security recommendation)</span></span> | <span data-ttu-id="dd329-203">Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="dd329-203">Microsoft Silverlight</span></span>
<span data-ttu-id="dd329-204">requesterEmail</span><span class="sxs-lookup"><span data-stu-id="dd329-204">requesterEmail</span></span> | <span data-ttu-id="dd329-205">Stringa</span><span class="sxs-lookup"><span data-stu-id="dd329-205">String</span></span> | <span data-ttu-id="dd329-206">Indirizzo di posta elettronica creatore</span><span class="sxs-lookup"><span data-stu-id="dd329-206">Creator email address</span></span> | <span data-ttu-id="dd329-207">globaladmin@UserName.contoso.com</span><span class="sxs-lookup"><span data-stu-id="dd329-207">globaladmin@UserName.contoso.com</span></span>
<span data-ttu-id="dd329-208">requesterId</span><span class="sxs-lookup"><span data-stu-id="dd329-208">requesterId</span></span> | <span data-ttu-id="dd329-209">Stringa</span><span class="sxs-lookup"><span data-stu-id="dd329-209">String</span></span> | <span data-ttu-id="dd329-210">ID oggetto creatore</span><span class="sxs-lookup"><span data-stu-id="dd329-210">Creator object id</span></span> | <span data-ttu-id="dd329-211">r647211f-2e16-43f2-a480-16ar3a2a796r</span><span class="sxs-lookup"><span data-stu-id="dd329-211">r647211f-2e16-43f2-a480-16ar3a2a796r</span></span>
<span data-ttu-id="dd329-212">requesterNotes</span><span class="sxs-lookup"><span data-stu-id="dd329-212">requesterNotes</span></span> | <span data-ttu-id="dd329-213">Stringa</span><span class="sxs-lookup"><span data-stu-id="dd329-213">String</span></span> | <span data-ttu-id="dd329-214">Note (testo libero) aggiunte dall'autore per questa attività di correzione</span><span class="sxs-lookup"><span data-stu-id="dd329-214">The notes (free text) the creator added for this remediation activity</span></span> | <span data-ttu-id="dd329-215">null</span><span class="sxs-lookup"><span data-stu-id="dd329-215">null</span></span>
<span data-ttu-id="dd329-216">scid</span><span class="sxs-lookup"><span data-stu-id="dd329-216">scid</span></span> | <span data-ttu-id="dd329-217">Stringa</span><span class="sxs-lookup"><span data-stu-id="dd329-217">String</span></span> | <span data-ttu-id="dd329-218">SCID della raccomandazione relativa alla sicurezza</span><span class="sxs-lookup"><span data-stu-id="dd329-218">SCID of the related security recommendation</span></span> | <span data-ttu-id="dd329-219">null</span><span class="sxs-lookup"><span data-stu-id="dd329-219">null</span></span>
<span data-ttu-id="dd329-220">status</span><span class="sxs-lookup"><span data-stu-id="dd329-220">status</span></span> | <span data-ttu-id="dd329-221">Stringa</span><span class="sxs-lookup"><span data-stu-id="dd329-221">String</span></span> | <span data-ttu-id="dd329-222">Stato attività di correzione (Attivo/Completato)</span><span class="sxs-lookup"><span data-stu-id="dd329-222">Remediation activity status (Active/Completed)</span></span> | <span data-ttu-id="dd329-223">Attivo</span><span class="sxs-lookup"><span data-stu-id="dd329-223">Active</span></span>
<span data-ttu-id="dd329-224">statusLastModifiedOn</span><span class="sxs-lookup"><span data-stu-id="dd329-224">statusLastModifiedOn</span></span> | <span data-ttu-id="dd329-225">DateTime</span><span class="sxs-lookup"><span data-stu-id="dd329-225">DateTime</span></span> | <span data-ttu-id="dd329-226">Data in cui il campo stato è stato aggiornato</span><span class="sxs-lookup"><span data-stu-id="dd329-226">Date when the status field was updated</span></span> | <span data-ttu-id="dd329-227">2021-01-12T18:54:11.5499487Z</span><span class="sxs-lookup"><span data-stu-id="dd329-227">2021-01-12T18:54:11.5499487Z</span></span>
<span data-ttu-id="dd329-228">targetDevices</span><span class="sxs-lookup"><span data-stu-id="dd329-228">targetDevices</span></span> | <span data-ttu-id="dd329-229">Long</span><span class="sxs-lookup"><span data-stu-id="dd329-229">Long</span></span> | <span data-ttu-id="dd329-230">Numero di dispositivi esposti a cui è applicabile questa correzione</span><span class="sxs-lookup"><span data-stu-id="dd329-230">Number of exposed devices that this remediation is applicable to</span></span> | <span data-ttu-id="dd329-231">43</span><span class="sxs-lookup"><span data-stu-id="dd329-231">43</span></span>
<span data-ttu-id="dd329-232">title</span><span class="sxs-lookup"><span data-stu-id="dd329-232">title</span></span> | <span data-ttu-id="dd329-233">Stringa</span><span class="sxs-lookup"><span data-stu-id="dd329-233">String</span></span> | <span data-ttu-id="dd329-234">Titolo di questa attività di correzione</span><span class="sxs-lookup"><span data-stu-id="dd329-234">Title of this remediation activity</span></span> | <span data-ttu-id="dd329-235">Aggiornare Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="dd329-235">Update Microsoft Silverlight</span></span>
<span data-ttu-id="dd329-236">type</span><span class="sxs-lookup"><span data-stu-id="dd329-236">type</span></span> | <span data-ttu-id="dd329-237">Stringa</span><span class="sxs-lookup"><span data-stu-id="dd329-237">String</span></span> | <span data-ttu-id="dd329-238">Tipo di correzione</span><span class="sxs-lookup"><span data-stu-id="dd329-238">Remediation type</span></span> | <span data-ttu-id="dd329-239">Update</span><span class="sxs-lookup"><span data-stu-id="dd329-239">Update</span></span>
<span data-ttu-id="dd329-240">vendorId</span><span class="sxs-lookup"><span data-stu-id="dd329-240">vendorId</span></span> | <span data-ttu-id="dd329-241">Stringa</span><span class="sxs-lookup"><span data-stu-id="dd329-241">String</span></span> | <span data-ttu-id="dd329-242">Nome fornitore correlato</span><span class="sxs-lookup"><span data-stu-id="dd329-242">Related vendor name</span></span> | <span data-ttu-id="dd329-243">Microsoft</span><span class="sxs-lookup"><span data-stu-id="dd329-243">Microsoft</span></span>

## <a name="example"></a><span data-ttu-id="dd329-244">Esempio</span><span class="sxs-lookup"><span data-stu-id="dd329-244">Example</span></span>

### <a name="request-example"></a><span data-ttu-id="dd329-245">Esempio di richiesta</span><span class="sxs-lookup"><span data-stu-id="dd329-245">Request example</span></span>

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/
```

### <a name="response-example"></a><span data-ttu-id="dd329-246">Esempio di risposta</span><span class="sxs-lookup"><span data-stu-id="dd329-246">Response example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="dd329-247">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dd329-247">See also</span></span>

- [<span data-ttu-id="dd329-248">Metodi e proprietà di correzione</span><span class="sxs-lookup"><span data-stu-id="dd329-248">Remediation methods and properties</span></span>](get-remediation-methods-properties.md)

- [<span data-ttu-id="dd329-249">Ottenere un'attività correttiva per ID</span><span class="sxs-lookup"><span data-stu-id="dd329-249">Get one remediation activity by Id</span></span>](get-remediation-one-activity.md)

- [<span data-ttu-id="dd329-250">Elencare i dispositivi esposti a un'attività correttiva</span><span class="sxs-lookup"><span data-stu-id="dd329-250">List exposed devices of one remediation activity</span></span>](get-remediation-exposed-devices-activities.md)

- [<span data-ttu-id="dd329-251">Rischio basato sulle minacce & gestione delle vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="dd329-251">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="dd329-252">Vulnerabilità nell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="dd329-252">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
