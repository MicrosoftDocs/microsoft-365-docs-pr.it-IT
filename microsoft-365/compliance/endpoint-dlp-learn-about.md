---
title: Informazioni sulla Prevenzione della perdita di dati degli endpoint di Microsoft 365
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: 'La Prevenzione della perdita di dati degli endpoint di Microsoft 365 estende il monitoraggio delle attività dei file e le azioni di protezione agli endpoint. I file vengono resi visibili nelle soluzioni di conformità di Microsoft 365 '
ms.openlocfilehash: b5aa6c737bc54129ce49378a7dcaf81e9d5c612f
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114104"
---
# <a name="learn-about-microsoft-365-endpoint-data-loss-prevention"></a><span data-ttu-id="ba962-104">Informazioni sulla prevenzione della perdita di dati degli endpoint di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ba962-104">Learn about Microsoft 365 Endpoint data loss prevention</span></span>

<span data-ttu-id="ba962-105">È possibile usare la prevenzione della perdita dei dati (DLP) di Microsoft 365 per monitorare le azioni intraprese sugli elementi che si considerano sensibili e per evitare la condivisione involontaria di tali elementi.</span><span class="sxs-lookup"><span data-stu-id="ba962-105">You can use Microsoft 365 data loss prevention (DLP) to monitor the actions that are being taken on items you've determined to be sensitive and to help prevent the unintentional sharing of those items.</span></span> <span data-ttu-id="ba962-106">Per altre informazioni su DLP, vedere [Informazioni sulla prevenzione della perdita di dati](dlp-learn-about-dlp.md).</span><span class="sxs-lookup"><span data-stu-id="ba962-106">For more information on DLP, see [Learn about data loss prevention](dlp-learn-about-dlp.md).</span></span>

<span data-ttu-id="ba962-107">La **prevenzione della perdita di dati degli endpoint** (Endpoint DLP) estende le funzionalità di monitoraggio e protezione delle attività di DLP agli elementi sensibili presenti nei dispositivi Windows 10.</span><span class="sxs-lookup"><span data-stu-id="ba962-107">**Endpoint data loss prevention** (Endpoint DLP) extends the activity monitoring and protection capabilities of DLP to sensitive items that are on Windows 10 devices.</span></span> <span data-ttu-id="ba962-108">Dopo aver eseguito l'onboarding dei dispositivi nelle soluzioni del Centro conformità Microsoft 365, le informazioni sulle azioni che gli utenti stanno eseguendo sugli elementi sensibili sono rese visibili in [Esplora attività](data-classification-activity-explorer.md) ed è possibile applicare azioni di protezione su tali elementi tramite [criteri DLP](create-test-tune-dlp-policy.md).</span><span class="sxs-lookup"><span data-stu-id="ba962-108">Once devices are onboarded into the Microsoft 365 compliance solutions, the information about what users are doing with sensitive items is made visible in [activity explorer](data-classification-activity-explorer.md) and you can enforce protective actions on those items via [DLP policies](create-test-tune-dlp-policy.md).</span></span>

## <a name="endpoint-activities-you-can-monitor-and-take-action-on"></a><span data-ttu-id="ba962-109">Attività endpoint che è possibile monitorare e su cui si può intervenire</span><span class="sxs-lookup"><span data-stu-id="ba962-109">Endpoint activities you can monitor and take action on</span></span>

<span data-ttu-id="ba962-110">Microsoft Endpoint DLP consente di controllare e gestire i tipi di attività seguenti, che gli utenti possono eseguire sugli elementi sensibili nei dispositivi che eseguono Windows 10.</span><span class="sxs-lookup"><span data-stu-id="ba962-110">Microsoft Endpoint DLP enables you to audit and manage the following types of activities users take on sensitive items on devices running Windows 10.</span></span> 

|<span data-ttu-id="ba962-111">Attività</span><span class="sxs-lookup"><span data-stu-id="ba962-111">Activity</span></span> |<span data-ttu-id="ba962-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ba962-112">Description</span></span>  | <span data-ttu-id="ba962-113">Controllabile/limitabile</span><span class="sxs-lookup"><span data-stu-id="ba962-113">Auditable/restictable</span></span>|
|---------|---------|---------|
|<span data-ttu-id="ba962-114">caricare su servizio cloud o accedere con browser non consentiti</span><span class="sxs-lookup"><span data-stu-id="ba962-114">upload to cloud service, or access by unallowed browsers</span></span>    | <span data-ttu-id="ba962-115">Rileva quando un utente tenta di caricare un elemento in un dominio di servizio riservato o di accedere a un elemento attraverso un browser.</span><span class="sxs-lookup"><span data-stu-id="ba962-115">Detects when a user attempts to upload an item to a restricted service domain or access an item through a browser.</span></span>  <span data-ttu-id="ba962-116">Se si utilizza un browser che è elencato in DLP come browser non consentito, l'attività di upload verrà bloccata e l'utente verrà reindirizzato all'utilizzo di Edge Chromium.</span><span class="sxs-lookup"><span data-stu-id="ba962-116">If they are using a browser that is listed in DLP as an being an unallowed browser, the upload activity will be blocked and the user is redirected to use Edge Chromium.</span></span> <span data-ttu-id="ba962-117">Edge Chromium permetterà o bloccherà il caricamento o l'accesso in base alla configurazione dei criteri DLP</span><span class="sxs-lookup"><span data-stu-id="ba962-117">Edge Chromium will then either allow or block the upload or access based on the DLP policy configuration</span></span>         |<span data-ttu-id="ba962-118">controllabile e limitabile</span><span class="sxs-lookup"><span data-stu-id="ba962-118">auditable and restrictable</span></span>|
|<span data-ttu-id="ba962-119">copiare su altra app</span><span class="sxs-lookup"><span data-stu-id="ba962-119">copy to other app</span></span>    |<span data-ttu-id="ba962-120">Rileva quando un utente tenta di copiare le informazioni da un elemento protetto e poi le incolla in un'altra applicazione, processo o elemento.</span><span class="sxs-lookup"><span data-stu-id="ba962-120">Detects when a user attempts to copy information from a protected item and then paste it into another app, process or item.</span></span> <span data-ttu-id="ba962-121">Il processo di copiare e incollare informazioni all'interno della stessa applicazione, processo o elemento non viene rilevato da questa attività.</span><span class="sxs-lookup"><span data-stu-id="ba962-121">Copying and pasting information within the same app, process, or item is not detected by this activity.</span></span>         | <span data-ttu-id="ba962-122">controllabile e limitabile</span><span class="sxs-lookup"><span data-stu-id="ba962-122">auditable and restrictable</span></span>|
|<span data-ttu-id="ba962-123">copiare su supporto rimovibile USB</span><span class="sxs-lookup"><span data-stu-id="ba962-123">copy to USB removable media</span></span> |<span data-ttu-id="ba962-124">Rileva quando un utente tenta di copiare un elemento o un'informazione su un supporto rimovibile o un dispositivo USB.</span><span class="sxs-lookup"><span data-stu-id="ba962-124">Detects when a user attempts to copy an item or information to removable media or USB device.</span></span>         | <span data-ttu-id="ba962-125">controllabile e limitabile</span><span class="sxs-lookup"><span data-stu-id="ba962-125">auditable and restrictable</span></span>|
|<span data-ttu-id="ba962-126">copiare su condivisione di rete</span><span class="sxs-lookup"><span data-stu-id="ba962-126">copy to a network share</span></span>    |<span data-ttu-id="ba962-127">Rileva quando un utente tenta di copiare un elemento in una condivisione di rete o in un'unità di rete mappata</span><span class="sxs-lookup"><span data-stu-id="ba962-127">Detects when a user attempts to copy an item to a network share or mapped network drive</span></span>         |<span data-ttu-id="ba962-128">controllabile e limitabile</span><span class="sxs-lookup"><span data-stu-id="ba962-128">auditable and restrictable</span></span>|
|<span data-ttu-id="ba962-129">stampare un documento</span><span class="sxs-lookup"><span data-stu-id="ba962-129">print a document</span></span>    |<span data-ttu-id="ba962-130">Rileva quando un utente tenta di stampare un elemento protetto su una stampante locale o di rete.</span><span class="sxs-lookup"><span data-stu-id="ba962-130">Detects when a user attempts to print a protected item to a local or network printer.</span></span>| <span data-ttu-id="ba962-131">controllabile e limitabile</span><span class="sxs-lookup"><span data-stu-id="ba962-131">auditable and restrictable</span></span>         |
|<span data-ttu-id="ba962-132">copiare in una sessione remota</span><span class="sxs-lookup"><span data-stu-id="ba962-132">copy to a remote session</span></span>|<span data-ttu-id="ba962-133">Rileva quando un utente tenta di copiare un elemento in una sessione desktop remota</span><span class="sxs-lookup"><span data-stu-id="ba962-133">Detects when a user attempts to copy an item to a remote desktop session</span></span> |  <span data-ttu-id="ba962-134">controllabile e limitabile</span><span class="sxs-lookup"><span data-stu-id="ba962-134">auditable and restrictable</span></span>|
|<span data-ttu-id="ba962-135">copiare in un dispositivo Bluetooth</span><span class="sxs-lookup"><span data-stu-id="ba962-135">copy to a Bluetooth device</span></span>|<span data-ttu-id="ba962-136">Rileva quando un utente cerca di copiare un elemento in un'app Bluetooth non consentita (come definito nell'elenco delle app Bluetooth non consentite nelle impostazioni Endpoint DLP).</span><span class="sxs-lookup"><span data-stu-id="ba962-136">Detects when a user attempts to copy an item to an unallowed Bluetooth app (as defined in the list of unallowed Bluetooth aps in Endpoint DLP settings).</span></span>| <span data-ttu-id="ba962-137">controllabile e limitabile</span><span class="sxs-lookup"><span data-stu-id="ba962-137">auditable and restrictable</span></span>|
|<span data-ttu-id="ba962-138">creare un elemento.</span><span class="sxs-lookup"><span data-stu-id="ba962-138">create an item</span></span>|<span data-ttu-id="ba962-139">Rileva quando un utente crea un elemento</span><span class="sxs-lookup"><span data-stu-id="ba962-139">Detects when a user creates an item</span></span>| <span data-ttu-id="ba962-140">controllabile</span><span class="sxs-lookup"><span data-stu-id="ba962-140">auditable</span></span>|
|<span data-ttu-id="ba962-141">rinominare un elemento</span><span class="sxs-lookup"><span data-stu-id="ba962-141">rename an item</span></span>|<span data-ttu-id="ba962-142">Rileva quando un utente rinomina un elemento</span><span class="sxs-lookup"><span data-stu-id="ba962-142">Detects when a user renames an item</span></span>| <span data-ttu-id="ba962-143">controllabile</span><span class="sxs-lookup"><span data-stu-id="ba962-143">auditable</span></span>|

 ## <a name="monitored-files"></a><span data-ttu-id="ba962-144">File monitorati</span><span class="sxs-lookup"><span data-stu-id="ba962-144">Monitored files</span></span>

<span data-ttu-id="ba962-145">Endpoint DLP supporta il monitoraggio di questi tipi di file:</span><span class="sxs-lookup"><span data-stu-id="ba962-145">Endpoint DLP supports monitoring of these file types:</span></span>

- <span data-ttu-id="ba962-146">File di Word</span><span class="sxs-lookup"><span data-stu-id="ba962-146">Word files</span></span>
- <span data-ttu-id="ba962-147">File di PowerPoint</span><span class="sxs-lookup"><span data-stu-id="ba962-147">PowerPoint files</span></span>
- <span data-ttu-id="ba962-148">File di Excel</span><span class="sxs-lookup"><span data-stu-id="ba962-148">Excel files</span></span>
- <span data-ttu-id="ba962-149">File PDF</span><span class="sxs-lookup"><span data-stu-id="ba962-149">PDF files</span></span>
- <span data-ttu-id="ba962-150">File CSV</span><span class="sxs-lookup"><span data-stu-id="ba962-150">.csv files</span></span>
- <span data-ttu-id="ba962-151">File TSV</span><span class="sxs-lookup"><span data-stu-id="ba962-151">.tsv files</span></span>
- <span data-ttu-id="ba962-152">File TXT</span><span class="sxs-lookup"><span data-stu-id="ba962-152">.txt files</span></span>
- <span data-ttu-id="ba962-153">File RTF</span><span class="sxs-lookup"><span data-stu-id="ba962-153">.rtf files</span></span>
- <span data-ttu-id="ba962-154">File C</span><span class="sxs-lookup"><span data-stu-id="ba962-154">.c files</span></span>
- <span data-ttu-id="ba962-155">File CLASS</span><span class="sxs-lookup"><span data-stu-id="ba962-155">.class files</span></span>
- <span data-ttu-id="ba962-156">File CPP</span><span class="sxs-lookup"><span data-stu-id="ba962-156">.cpp files</span></span>
- <span data-ttu-id="ba962-157">File CS</span><span class="sxs-lookup"><span data-stu-id="ba962-157">.cs files</span></span>
- <span data-ttu-id="ba962-158">File H</span><span class="sxs-lookup"><span data-stu-id="ba962-158">.h files</span></span>
- <span data-ttu-id="ba962-159">File Java</span><span class="sxs-lookup"><span data-stu-id="ba962-159">.java files</span></span>
 
<span data-ttu-id="ba962-160">Per impostazione predefinita, Endpoint DLP controlla le attività per questi tipi di file anche in mancanza di una corrispondenza dei criteri.</span><span class="sxs-lookup"><span data-stu-id="ba962-160">By default, endpoint DLP audits the activities for these file types, even if there isn't a policy match.</span></span> <span data-ttu-id="ba962-161">Se si vogliono monitorare i dati solo se c'è una corrispondenza dei criteri, è possibile disattivare l'opzione **Controllare sempre le attività dei file per i dispositivi** nelle impostazioni globali di Endpoint DLP.</span><span class="sxs-lookup"><span data-stu-id="ba962-161">If you only want monitoring data from policy matches, you can turn off the **Always audit file activity for devices** in the endpoint DLP global settings.</span></span> <span data-ttu-id="ba962-162">Se questa impostazione è attiva, le attività su qualsiasi file Word, PowerPoint, Excel, PDF e .csv vengono sempre controllate, anche se il dispositivo non dispone di alcun criterio.</span><span class="sxs-lookup"><span data-stu-id="ba962-162">If this setting is on, activities on any Word, PowerPoint, Excel, PDF, and .csv file are always audited even if the device is not targeted by any policy.</span></span>

<span data-ttu-id="ba962-163">Endpoint DLP monitora le attività in base al tipo MIME, pertanto le attività verranno acquisite anche se l'estensione del file viene cambiata.</span><span class="sxs-lookup"><span data-stu-id="ba962-163">Endpoint DLP monitors activity-based on MIME type, so activities will be captured even if the file extension is changed.</span></span> 

## <a name="whats-different-in-endpoint-dlp"></a><span data-ttu-id="ba962-164">Cosa distingue Endpoint DLP</span><span class="sxs-lookup"><span data-stu-id="ba962-164">What's different in Endpoint DLP</span></span>

<span data-ttu-id="ba962-165">Ci sono alcuni concetti aggiuntivi che è necessario conoscere prima di approfondire l'utilizzo di Endpoint DLP.</span><span class="sxs-lookup"><span data-stu-id="ba962-165">There are a few extra concepts that you need to be aware of before you dig into Endpoint DLP.</span></span>

### <a name="enabling-device-management"></a><span data-ttu-id="ba962-166">Abilitare la gestione dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="ba962-166">Enabling Device management</span></span>

<span data-ttu-id="ba962-167">La gestione dei dispositivi è la funzionalità che consente la raccolta di dati di telemetria dai dispositivi e la introduce nelle soluzioni di conformità di Microsoft 365, come Endpoint DLP e [Gestione dei rischi Insider](insider-risk-management.md).</span><span class="sxs-lookup"><span data-stu-id="ba962-167">Device management is the functionality that enables the collection of telemetry from devices and brings it into Microsoft 365 compliance solutions like Endpoint DLP and [Insider Risk management](insider-risk-management.md).</span></span> <span data-ttu-id="ba962-168">È necessario eseguire l'onboarding di tutti i dispositivi che si vogliono usare come posizioni nei criteri DLP.</span><span class="sxs-lookup"><span data-stu-id="ba962-168">You'll need to onboard all devices you want to use as locations in DLP policies.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ba962-169">![abilitare la gestione dei dispositivi](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="ba962-169">![enable device management](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span></span>

<span data-ttu-id="ba962-170">Onboarding e offboarding vengono gestiti tramite script scaricati dal centro gestione dispositivi.</span><span class="sxs-lookup"><span data-stu-id="ba962-170">Onboarding and offboarding are handled via scripts you download from the Device management center.</span></span> <span data-ttu-id="ba962-171">Nel centro sono disponibili script personalizzati per ognuno di questi metodi di distribuzione:</span><span class="sxs-lookup"><span data-stu-id="ba962-171">The center has custom scripts for each of these deployment methods:</span></span>

- <span data-ttu-id="ba962-172">script locale (fino a 10 computer)</span><span class="sxs-lookup"><span data-stu-id="ba962-172">local script (up to 10 machines)</span></span>
- <span data-ttu-id="ba962-173">Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="ba962-173">Group policy</span></span>
- <span data-ttu-id="ba962-174">System Center Configuration Manager (versione 1610 o successiva)</span><span class="sxs-lookup"><span data-stu-id="ba962-174">System Center Configuration Manager (version 1610 or later)</span></span>
- <span data-ttu-id="ba962-175">Gestione dispositivi mobili/Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="ba962-175">Mobile Device Management/Microsoft Intune</span></span>
- <span data-ttu-id="ba962-176">Script di onboarding VDI per dispositivi non persistenti</span><span class="sxs-lookup"><span data-stu-id="ba962-176">VDI onboarding scripts for non-persistent machines</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ba962-177">![pagina di onboarding dispositivi](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span><span class="sxs-lookup"><span data-stu-id="ba962-177">![device onboarding page](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span></span>

 <span data-ttu-id="ba962-178">Seguire le procedure in [Introduzione a Microsoft 365 Endpoint DLP](endpoint-dlp-getting-started.md) per l'onboarding dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="ba962-178">Use the procedures in [Getting started with Microsoft 365 Endpoint DLP](endpoint-dlp-getting-started.md) to onboard devices.</span></span>

<span data-ttu-id="ba962-179">Se è stato eseguito l'onboarding di dispositivi tramite [Microsoft Defender per endpoint](/windows/security/threat-protection/), questi dispositivi verranno visualizzati automaticamente nell'elenco dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="ba962-179">If you have onboarded devices through [Microsoft Defender for Endpoint](/windows/security/threat-protection/), those devices will automatically show up in the list of devices.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ba962-180">![elenco dispositivi gestiti](../media/endpoint-dlp-learn-about-2-device-list.png)</span><span class="sxs-lookup"><span data-stu-id="ba962-180">![managed devices list](../media/endpoint-dlp-learn-about-2-device-list.png)</span></span>

### <a name="viewing-endpoint-dlp-data"></a><span data-ttu-id="ba962-181">Visualizzazione dei dati di Endpoint DLP</span><span class="sxs-lookup"><span data-stu-id="ba962-181">Viewing Endpoint DLP data</span></span>

<span data-ttu-id="ba962-182">È possibile visualizzare gli avvisi correlati ai criteri di prevenzione della perdita dei dati applicati ai dispositivi endpoint passando al [Dashboard di gestione avvisi DLP](dlp-configure-view-alerts-policies.md).</span><span class="sxs-lookup"><span data-stu-id="ba962-182">You can view alerts related to DLP policies enforced on endpoint devices by going to the [DLP Alerts Management Dashboard](dlp-configure-view-alerts-policies.md).</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ba962-183">![Info sugli avvisi](../media/Alert-info-1.png)</span><span class="sxs-lookup"><span data-stu-id="ba962-183">![Alert info](../media/Alert-info-1.png)</span></span>

<span data-ttu-id="ba962-184">È anche possibile visualizzare i dettagli dell'evento associato con metadati completi nello stesso dashboard</span><span class="sxs-lookup"><span data-stu-id="ba962-184">You can also view details of the associated event with rich metadata in the same dashboard</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ba962-185">![info sull'evento](../media/Event-info-1.png)</span><span class="sxs-lookup"><span data-stu-id="ba962-185">![event info](../media/Event-info-1.png)</span></span>

<span data-ttu-id="ba962-186">Dopo l'onboarding di un dispositivo, le informazioni sulle attività controllate fluiscono in Esplora attività anche prima che vengano configurati e distribuiti criteri di prevenzione della perdita dei dati che usano dispositivi come posizione.</span><span class="sxs-lookup"><span data-stu-id="ba962-186">Once a device is onboarded, information about audited activities flows into Activity explorer even before you configure and deploy any DLP policies that have devices as a location.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ba962-187">![eventi di prevenzione della perdita di dati degli endpoint in Esplora attività](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="ba962-187">![endpoint dlp events in activity explorer](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span></span>

<span data-ttu-id="ba962-188">Endpoint DLP raccoglie informazioni complete sulle attività controllate.</span><span class="sxs-lookup"><span data-stu-id="ba962-188">Endpoint DLP collects extensive information on audited activity.</span></span>

<span data-ttu-id="ba962-189">Ad esempio, se un file viene copiato in un supporto USB rimovibile, nei dettagli attività vengono visualizzati questi attributi:</span><span class="sxs-lookup"><span data-stu-id="ba962-189">For example, if a file is copied to removable USB media, you'd see these attributes in the activity details:</span></span>

- <span data-ttu-id="ba962-190">tipo di attività</span><span class="sxs-lookup"><span data-stu-id="ba962-190">activity type</span></span>
- <span data-ttu-id="ba962-191">IP client</span><span class="sxs-lookup"><span data-stu-id="ba962-191">client IP</span></span>
- <span data-ttu-id="ba962-192">percorso file di destinazione</span><span class="sxs-lookup"><span data-stu-id="ba962-192">target file path</span></span>
- <span data-ttu-id="ba962-193">timestamp dell'attività</span><span class="sxs-lookup"><span data-stu-id="ba962-193">happened timestamp</span></span>
- <span data-ttu-id="ba962-194">nome del file</span><span class="sxs-lookup"><span data-stu-id="ba962-194">file name</span></span>
- <span data-ttu-id="ba962-195">utente</span><span class="sxs-lookup"><span data-stu-id="ba962-195">user</span></span>
- <span data-ttu-id="ba962-196">estensione del file</span><span class="sxs-lookup"><span data-stu-id="ba962-196">file extension</span></span>
- <span data-ttu-id="ba962-197">dimensioni del file</span><span class="sxs-lookup"><span data-stu-id="ba962-197">file size</span></span>
- <span data-ttu-id="ba962-198">tipo di informazioni sensibili (se applicabile)</span><span class="sxs-lookup"><span data-stu-id="ba962-198">sensitive information type (if applicable)</span></span>
- <span data-ttu-id="ba962-199">valore SHA1</span><span class="sxs-lookup"><span data-stu-id="ba962-199">sha1 value</span></span>
- <span data-ttu-id="ba962-200">valore SHA256</span><span class="sxs-lookup"><span data-stu-id="ba962-200">sha256 value</span></span>
- <span data-ttu-id="ba962-201">nome file precedente</span><span class="sxs-lookup"><span data-stu-id="ba962-201">previous file name</span></span>
- <span data-ttu-id="ba962-202">posizione</span><span class="sxs-lookup"><span data-stu-id="ba962-202">location</span></span>
- <span data-ttu-id="ba962-203">padre</span><span class="sxs-lookup"><span data-stu-id="ba962-203">parent</span></span>
- <span data-ttu-id="ba962-204">percorso file</span><span class="sxs-lookup"><span data-stu-id="ba962-204">filepath</span></span>
- <span data-ttu-id="ba962-205">tipo di percorso di origine</span><span class="sxs-lookup"><span data-stu-id="ba962-205">source location type</span></span>
- <span data-ttu-id="ba962-206">piattaforma</span><span class="sxs-lookup"><span data-stu-id="ba962-206">platform</span></span>
- <span data-ttu-id="ba962-207">nome dispositivo</span><span class="sxs-lookup"><span data-stu-id="ba962-207">device name</span></span>
- <span data-ttu-id="ba962-208">tipo di percorso di destinazione</span><span class="sxs-lookup"><span data-stu-id="ba962-208">destination location type</span></span>
- <span data-ttu-id="ba962-209">applicazione che ha eseguito la copia</span><span class="sxs-lookup"><span data-stu-id="ba962-209">application that performed the copy</span></span>
- <span data-ttu-id="ba962-210">ID dispositivo di Microsoft Defender per endpoint (se applicabile)</span><span class="sxs-lookup"><span data-stu-id="ba962-210">Microsoft Defender for Endpoint device ID (if applicable)</span></span>
- <span data-ttu-id="ba962-211">produttore del dispositivo multimediale rimovibile</span><span class="sxs-lookup"><span data-stu-id="ba962-211">removable media device manufacturer</span></span>
- <span data-ttu-id="ba962-212">modello di dispositivo multimediale rimovibile</span><span class="sxs-lookup"><span data-stu-id="ba962-212">removable media device model</span></span>
- <span data-ttu-id="ba962-213">numero di serie del dispositivo multimediale rimovibile</span><span class="sxs-lookup"><span data-stu-id="ba962-213">removable media device serial number</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ba962-214">![attributi dell'attività di copia su USB](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span><span class="sxs-lookup"><span data-stu-id="ba962-214">![copy to usb activity attributes](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span></span>

## <a name="next-steps"></a><span data-ttu-id="ba962-215">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="ba962-215">Next steps</span></span>

<span data-ttu-id="ba962-216">Dopo avere acquisito familiarità con Endpoint DLP, è possibile proseguire con questi argomenti:</span><span class="sxs-lookup"><span data-stu-id="ba962-216">Now that you've learned about Endpoint DLP, your next steps are:</span></span>

1) [<span data-ttu-id="ba962-217">Introduzione alla prevenzione della perdita di dati degli endpoint Microsoft</span><span class="sxs-lookup"><span data-stu-id="ba962-217">Getting started with Microsoft Endpoint data loss prevention </span></span>](endpoint-dlp-getting-started.md)
2) [<span data-ttu-id="ba962-218">Uso della prevenzione della perdita di dati degli endpoint Microsoft</span><span class="sxs-lookup"><span data-stu-id="ba962-218">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="ba962-219">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ba962-219">See also</span></span>

- [<span data-ttu-id="ba962-220">Introduzione alla prevenzione della perdita di dati degli endpoint Microsoft</span><span class="sxs-lookup"><span data-stu-id="ba962-220">Getting started with Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="ba962-221">Uso della prevenzione della perdita di dati degli endpoint Microsoft</span><span class="sxs-lookup"><span data-stu-id="ba962-221">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="ba962-222">Informazioni sulla prevenzione della perdita di dati</span><span class="sxs-lookup"><span data-stu-id="ba962-222">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="ba962-223">Creare, testare e ottimizzare un criterio di prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="ba962-223">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="ba962-224">Introduzione a Esplora attività</span><span class="sxs-lookup"><span data-stu-id="ba962-224">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="ba962-225">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="ba962-225">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/)
- [<span data-ttu-id="ba962-226">Gestione dei rischi Insider</span><span class="sxs-lookup"><span data-stu-id="ba962-226">Insider Risk management</span></span>](insider-risk-management.md)