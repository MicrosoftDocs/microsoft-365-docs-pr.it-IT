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
ms.openlocfilehash: 3da15f1ac35ca448a76638c31f047c6a2132ad7a
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454006"
---
# <a name="learn-about-microsoft-365-endpoint-data-loss-prevention"></a><span data-ttu-id="2b10e-104">Informazioni sulla prevenzione della perdita di dati degli endpoint di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2b10e-104">Learn about Microsoft 365 Endpoint data loss prevention</span></span>

<span data-ttu-id="2b10e-105">È possibile usare la prevenzione della perdita dei dati (DLP) di Microsoft 365 per monitorare le azioni intraprese sugli elementi che si considerano sensibili e per evitare la condivisione involontaria di tali elementi.</span><span class="sxs-lookup"><span data-stu-id="2b10e-105">You can use Microsoft 365 data loss prevention (DLP) to monitor the actions that are being taken on items you've determined to be sensitive and to help prevent the unintentional sharing of those items.</span></span> <span data-ttu-id="2b10e-106">Per altre informazioni su DLP, vedere [Informazioni sulla prevenzione della perdita di dati](dlp-learn-about-dlp.md).</span><span class="sxs-lookup"><span data-stu-id="2b10e-106">For more information on DLP, see [Learn about data loss prevention](dlp-learn-about-dlp.md).</span></span>

<span data-ttu-id="2b10e-107">La **prevenzione della perdita di dati degli endpoint** (Endpoint DLP) estende le funzionalità di monitoraggio e protezione delle attività di DLP agli elementi sensibili presenti nei dispositivi Windows 10.</span><span class="sxs-lookup"><span data-stu-id="2b10e-107">**Endpoint data loss prevention** (Endpoint DLP) extends the activity monitoring and protection capabilities of DLP to sensitive items that are on Windows 10 devices.</span></span> <span data-ttu-id="2b10e-108">Dopo aver eseguito l'onboarding dei dispositivi nelle soluzioni del Centro conformità Microsoft 365, le informazioni sulle azioni che gli utenti stanno eseguendo sugli elementi sensibili sono rese visibili in [Esplora attività](data-classification-activity-explorer.md) ed è possibile applicare azioni di protezione su tali elementi tramite [criteri DLP](create-test-tune-dlp-policy.md).</span><span class="sxs-lookup"><span data-stu-id="2b10e-108">Once devices are onboarded into the Microsoft 365 compliance solutions, the information about what users are doing with sensitive items is made visible in [activity explorer](data-classification-activity-explorer.md) and you can enforce protective actions on those items via [DLP policies](create-test-tune-dlp-policy.md).</span></span>

> [!TIP]
> <span data-ttu-id="2b10e-109">Se si sta cercando il controllo del dispositivo per l'archiviazione rimovibile, vedere [Controllo degli accessi alle risorse di archiviazione rimovibili di Microsoft Defender per endpoint](../security/defender-endpoint/device-control-removable-storage-access-control.md#microsoft-defender-for-endpoint-device-control-removable-storage-access-control).</span><span class="sxs-lookup"><span data-stu-id="2b10e-109">If you are looking for device control for removable storage, see [Microsoft Defender for Endpoint Device Control Removable Storage Access Control](../security/defender-endpoint/device-control-removable-storage-access-control.md#microsoft-defender-for-endpoint-device-control-removable-storage-access-control).</span></span>

## <a name="endpoint-activities-you-can-monitor-and-take-action-on"></a><span data-ttu-id="2b10e-110">Attività endpoint che è possibile monitorare e su cui si può intervenire</span><span class="sxs-lookup"><span data-stu-id="2b10e-110">Endpoint activities you can monitor and take action on</span></span>

<span data-ttu-id="2b10e-111">Microsoft Endpoint DLP consente di controllare e gestire i tipi di attività seguenti, che gli utenti possono eseguire sugli elementi sensibili nei dispositivi che eseguono Windows 10.</span><span class="sxs-lookup"><span data-stu-id="2b10e-111">Microsoft Endpoint DLP enables you to audit and manage the following types of activities users take on sensitive items on devices running Windows 10.</span></span>

|<span data-ttu-id="2b10e-112">Attività</span><span class="sxs-lookup"><span data-stu-id="2b10e-112">Activity</span></span> |<span data-ttu-id="2b10e-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2b10e-113">Description</span></span>  | <span data-ttu-id="2b10e-114">Controllabile/limitabile</span><span class="sxs-lookup"><span data-stu-id="2b10e-114">Auditable/restictable</span></span>|
|---------|---------|---------|
|<span data-ttu-id="2b10e-115">caricare su servizio cloud o accedere con browser non consentiti</span><span class="sxs-lookup"><span data-stu-id="2b10e-115">upload to cloud service, or access by unallowed browsers</span></span>    | <span data-ttu-id="2b10e-116">Rileva quando un utente tenta di caricare un elemento in un dominio di servizio riservato o di accedere a un elemento attraverso un browser.</span><span class="sxs-lookup"><span data-stu-id="2b10e-116">Detects when a user attempts to upload an item to a restricted service domain or access an item through a browser.</span></span>  <span data-ttu-id="2b10e-117">Se si utilizza un browser che è elencato in DLP come browser non consentito, l'attività di upload verrà bloccata e l'utente verrà reindirizzato all'utilizzo di Edge Chromium.</span><span class="sxs-lookup"><span data-stu-id="2b10e-117">If they are using a browser that is listed in DLP as an being an unallowed browser, the upload activity will be blocked and the user is redirected to use Edge Chromium.</span></span> <span data-ttu-id="2b10e-118">Edge Chromium permetterà o bloccherà il caricamento o l'accesso in base alla configurazione dei criteri DLP</span><span class="sxs-lookup"><span data-stu-id="2b10e-118">Edge Chromium will then either allow or block the upload or access based on the DLP policy configuration</span></span>         |<span data-ttu-id="2b10e-119">controllabile e limitabile</span><span class="sxs-lookup"><span data-stu-id="2b10e-119">auditable and restrictable</span></span>|
|<span data-ttu-id="2b10e-120">copiare su altra app</span><span class="sxs-lookup"><span data-stu-id="2b10e-120">copy to other app</span></span>    |<span data-ttu-id="2b10e-121">Rileva quando un utente tenta di copiare le informazioni da un elemento protetto e poi le incolla in un'altra applicazione, processo o elemento.</span><span class="sxs-lookup"><span data-stu-id="2b10e-121">Detects when a user attempts to copy information from a protected item and then paste it into another app, process or item.</span></span> <span data-ttu-id="2b10e-122">Il processo di copiare e incollare informazioni all'interno della stessa applicazione, processo o elemento non viene rilevato da questa attività.</span><span class="sxs-lookup"><span data-stu-id="2b10e-122">Copying and pasting information within the same app, process, or item is not detected by this activity.</span></span>         | <span data-ttu-id="2b10e-123">controllabile e limitabile</span><span class="sxs-lookup"><span data-stu-id="2b10e-123">auditable and restrictable</span></span>|
|<span data-ttu-id="2b10e-124">copiare su supporto rimovibile USB</span><span class="sxs-lookup"><span data-stu-id="2b10e-124">copy to USB removable media</span></span> |<span data-ttu-id="2b10e-125">Rileva quando un utente tenta di copiare un elemento o un'informazione su un supporto rimovibile o un dispositivo USB.</span><span class="sxs-lookup"><span data-stu-id="2b10e-125">Detects when a user attempts to copy an item or information to removable media or USB device.</span></span>         | <span data-ttu-id="2b10e-126">controllabile e limitabile</span><span class="sxs-lookup"><span data-stu-id="2b10e-126">auditable and restrictable</span></span>|
|<span data-ttu-id="2b10e-127">copiare su condivisione di rete</span><span class="sxs-lookup"><span data-stu-id="2b10e-127">copy to a network share</span></span>    |<span data-ttu-id="2b10e-128">Rileva quando un utente tenta di copiare un elemento in una condivisione di rete o in un'unità di rete mappata</span><span class="sxs-lookup"><span data-stu-id="2b10e-128">Detects when a user attempts to copy an item to a network share or mapped network drive</span></span>         |<span data-ttu-id="2b10e-129">controllabile e limitabile</span><span class="sxs-lookup"><span data-stu-id="2b10e-129">auditable and restrictable</span></span>|
|<span data-ttu-id="2b10e-130">stampare un documento</span><span class="sxs-lookup"><span data-stu-id="2b10e-130">print a document</span></span>    |<span data-ttu-id="2b10e-131">Rileva quando un utente tenta di stampare un elemento protetto su una stampante locale o di rete.</span><span class="sxs-lookup"><span data-stu-id="2b10e-131">Detects when a user attempts to print a protected item to a local or network printer.</span></span>| <span data-ttu-id="2b10e-132">controllabile e limitabile</span><span class="sxs-lookup"><span data-stu-id="2b10e-132">auditable and restrictable</span></span>         |
|<span data-ttu-id="2b10e-133">copiare in una sessione remota</span><span class="sxs-lookup"><span data-stu-id="2b10e-133">copy to a remote session</span></span>|<span data-ttu-id="2b10e-134">Rileva quando un utente tenta di copiare un elemento in una sessione desktop remota</span><span class="sxs-lookup"><span data-stu-id="2b10e-134">Detects when a user attempts to copy an item to a remote desktop session</span></span> |  <span data-ttu-id="2b10e-135">controllabile e limitabile</span><span class="sxs-lookup"><span data-stu-id="2b10e-135">auditable and restrictable</span></span>|
|<span data-ttu-id="2b10e-136">copiare in un dispositivo Bluetooth</span><span class="sxs-lookup"><span data-stu-id="2b10e-136">copy to a Bluetooth device</span></span>|<span data-ttu-id="2b10e-137">Rileva quando un utente cerca di copiare un elemento in un'app Bluetooth non consentita (come definito nell'elenco delle app Bluetooth non consentite nelle impostazioni Endpoint DLP).</span><span class="sxs-lookup"><span data-stu-id="2b10e-137">Detects when a user attempts to copy an item to an unallowed Bluetooth app (as defined in the list of unallowed Bluetooth aps in Endpoint DLP settings).</span></span>| <span data-ttu-id="2b10e-138">controllabile e limitabile</span><span class="sxs-lookup"><span data-stu-id="2b10e-138">auditable and restrictable</span></span>|
|<span data-ttu-id="2b10e-139">creare un elemento.</span><span class="sxs-lookup"><span data-stu-id="2b10e-139">create an item</span></span>|<span data-ttu-id="2b10e-140">Rileva quando un utente crea un elemento</span><span class="sxs-lookup"><span data-stu-id="2b10e-140">Detects when a user creates an item</span></span>| <span data-ttu-id="2b10e-141">controllabile</span><span class="sxs-lookup"><span data-stu-id="2b10e-141">auditable</span></span>|
|<span data-ttu-id="2b10e-142">rinominare un elemento</span><span class="sxs-lookup"><span data-stu-id="2b10e-142">rename an item</span></span>|<span data-ttu-id="2b10e-143">Rileva quando un utente rinomina un elemento</span><span class="sxs-lookup"><span data-stu-id="2b10e-143">Detects when a user renames an item</span></span>| <span data-ttu-id="2b10e-144">controllabile</span><span class="sxs-lookup"><span data-stu-id="2b10e-144">auditable</span></span>|

## <a name="monitored-files"></a><span data-ttu-id="2b10e-145">File monitorati</span><span class="sxs-lookup"><span data-stu-id="2b10e-145">Monitored files</span></span>

<span data-ttu-id="2b10e-146">Endpoint DLP supporta il monitoraggio di questi tipi di file.</span><span class="sxs-lookup"><span data-stu-id="2b10e-146">Endpoint DLP supports monitoring of these file types.</span></span> <span data-ttu-id="2b10e-147">DLP controlla le attività per questi tipi di file anche in mancanza di una corrispondenza dei criteri.</span><span class="sxs-lookup"><span data-stu-id="2b10e-147">DLP audits the activities for these file types, even if there isn't a policy match.</span></span> 

- <span data-ttu-id="2b10e-148">File di Word</span><span class="sxs-lookup"><span data-stu-id="2b10e-148">Word files</span></span>
- <span data-ttu-id="2b10e-149">File di PowerPoint</span><span class="sxs-lookup"><span data-stu-id="2b10e-149">PowerPoint files</span></span>
- <span data-ttu-id="2b10e-150">File di Excel</span><span class="sxs-lookup"><span data-stu-id="2b10e-150">Excel files</span></span>
- <span data-ttu-id="2b10e-151">File PDF</span><span class="sxs-lookup"><span data-stu-id="2b10e-151">PDF files</span></span>
- <span data-ttu-id="2b10e-152">File CSV</span><span class="sxs-lookup"><span data-stu-id="2b10e-152">.csv files</span></span>
- <span data-ttu-id="2b10e-153">File TSV</span><span class="sxs-lookup"><span data-stu-id="2b10e-153">.tsv files</span></span>
- <span data-ttu-id="2b10e-154">File TXT</span><span class="sxs-lookup"><span data-stu-id="2b10e-154">.txt files</span></span>
- <span data-ttu-id="2b10e-155">File RTF</span><span class="sxs-lookup"><span data-stu-id="2b10e-155">.rtf files</span></span>
- <span data-ttu-id="2b10e-156">File C</span><span class="sxs-lookup"><span data-stu-id="2b10e-156">.c files</span></span>
- <span data-ttu-id="2b10e-157">File CLASS</span><span class="sxs-lookup"><span data-stu-id="2b10e-157">.class files</span></span>
- <span data-ttu-id="2b10e-158">File CPP</span><span class="sxs-lookup"><span data-stu-id="2b10e-158">.cpp files</span></span>
- <span data-ttu-id="2b10e-159">File CS</span><span class="sxs-lookup"><span data-stu-id="2b10e-159">.cs files</span></span>
- <span data-ttu-id="2b10e-160">File H</span><span class="sxs-lookup"><span data-stu-id="2b10e-160">.h files</span></span>
- <span data-ttu-id="2b10e-161">File Java</span><span class="sxs-lookup"><span data-stu-id="2b10e-161">.java files</span></span>
 
<span data-ttu-id="2b10e-162">Se si vogliono monitorare i dati solo se c'è una corrispondenza dei criteri, è possibile disattivare l'opzione **Controllare sempre le attività dei file per i dispositivi** nelle impostazioni globali di Endpoint DLP.</span><span class="sxs-lookup"><span data-stu-id="2b10e-162">If you only want monitoring data from policy matches, you can turn off the **Always audit file activity for devices** in the endpoint DLP global settings.</span></span>

> [!NOTE]
> <span data-ttu-id="2b10e-163">Se l'impostazione **Controllare sempre le attività dei file per i dispositivi** è attiva, le attività su qualsiasi file Word, PowerPoint, Excel, PDF e CSV vengono sempre controllate, anche se il dispositivo non dispone di alcun criterio.</span><span class="sxs-lookup"><span data-stu-id="2b10e-163">If the **Always audit file activity for devices** setting is on, activities on any Word, PowerPoint, Excel, PDF, and .csv file are always audited even if the device is not targeted by any policy.</span></span>

<span data-ttu-id="2b10e-164">Endpoint DLP monitora le attività in base al tipo MIME, pertanto le attività verranno acquisite anche se l'estensione del file viene cambiata.</span><span class="sxs-lookup"><span data-stu-id="2b10e-164">Endpoint DLP monitors activity-based on MIME type, so activities will be captured even if the file extension is changed.</span></span>

## <a name="whats-different-in-endpoint-dlp"></a><span data-ttu-id="2b10e-165">Cosa distingue Endpoint DLP</span><span class="sxs-lookup"><span data-stu-id="2b10e-165">What's different in Endpoint DLP</span></span>

<span data-ttu-id="2b10e-166">Ci sono alcuni concetti aggiuntivi che è necessario conoscere prima di approfondire l'utilizzo di Endpoint DLP.</span><span class="sxs-lookup"><span data-stu-id="2b10e-166">There are a few extra concepts that you need to be aware of before you dig into Endpoint DLP.</span></span>

### <a name="enabling-device-management"></a><span data-ttu-id="2b10e-167">Abilitare la gestione dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="2b10e-167">Enabling Device management</span></span>

<span data-ttu-id="2b10e-168">La gestione dei dispositivi è la funzionalità che consente la raccolta di dati di telemetria dai dispositivi e la introduce nelle soluzioni di conformità di Microsoft 365, come Endpoint DLP e [Gestione dei rischi Insider](insider-risk-management.md).</span><span class="sxs-lookup"><span data-stu-id="2b10e-168">Device management is the functionality that enables the collection of telemetry from devices and brings it into Microsoft 365 compliance solutions like Endpoint DLP and [Insider Risk management](insider-risk-management.md).</span></span> <span data-ttu-id="2b10e-169">È necessario eseguire l'onboarding di tutti i dispositivi che si vogliono usare come posizioni nei criteri DLP.</span><span class="sxs-lookup"><span data-stu-id="2b10e-169">You'll need to onboard all devices you want to use as locations in DLP policies.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2b10e-170">![abilitare la gestione dei dispositivi](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="2b10e-170">![enable device management](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span></span>

<span data-ttu-id="2b10e-171">Onboarding e offboarding vengono gestiti tramite script scaricati dal centro gestione dispositivi.</span><span class="sxs-lookup"><span data-stu-id="2b10e-171">Onboarding and offboarding are handled via scripts you download from the Device management center.</span></span> <span data-ttu-id="2b10e-172">Nel centro sono disponibili script personalizzati per ognuno di questi metodi di distribuzione:</span><span class="sxs-lookup"><span data-stu-id="2b10e-172">The center has custom scripts for each of these deployment methods:</span></span>

- <span data-ttu-id="2b10e-173">script locale (fino a 10 computer)</span><span class="sxs-lookup"><span data-stu-id="2b10e-173">local script (up to 10 machines)</span></span>
- <span data-ttu-id="2b10e-174">Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="2b10e-174">Group policy</span></span>
- <span data-ttu-id="2b10e-175">System Center Configuration Manager (versione 1610 o successiva)</span><span class="sxs-lookup"><span data-stu-id="2b10e-175">System Center Configuration Manager (version 1610 or later)</span></span>
- <span data-ttu-id="2b10e-176">Gestione dispositivi mobili/Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="2b10e-176">Mobile Device Management/Microsoft Intune</span></span>
- <span data-ttu-id="2b10e-177">Script di onboarding VDI per dispositivi non persistenti</span><span class="sxs-lookup"><span data-stu-id="2b10e-177">VDI onboarding scripts for non-persistent machines</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2b10e-178">![pagina di onboarding dispositivi](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span><span class="sxs-lookup"><span data-stu-id="2b10e-178">![device onboarding page](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span></span>

 <span data-ttu-id="2b10e-179">Seguire le procedure in [Introduzione a Microsoft 365 Endpoint DLP](endpoint-dlp-getting-started.md) per l'onboarding dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="2b10e-179">Use the procedures in [Getting started with Microsoft 365 Endpoint DLP](endpoint-dlp-getting-started.md) to onboard devices.</span></span>

<span data-ttu-id="2b10e-180">Se è stato eseguito l'onboarding di dispositivi tramite [Microsoft Defender per endpoint](/windows/security/threat-protection/), questi dispositivi verranno visualizzati automaticamente nell'elenco dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="2b10e-180">If you have onboarded devices through [Microsoft Defender for Endpoint](/windows/security/threat-protection/), those devices will automatically show up in the list of devices.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2b10e-181">![elenco dispositivi gestiti](../media/endpoint-dlp-learn-about-2-device-list.png)</span><span class="sxs-lookup"><span data-stu-id="2b10e-181">![managed devices list](../media/endpoint-dlp-learn-about-2-device-list.png)</span></span>

### <a name="viewing-endpoint-dlp-data"></a><span data-ttu-id="2b10e-182">Visualizzazione dei dati di Endpoint DLP</span><span class="sxs-lookup"><span data-stu-id="2b10e-182">Viewing Endpoint DLP data</span></span>

<span data-ttu-id="2b10e-183">È possibile visualizzare gli avvisi correlati ai criteri di prevenzione della perdita dei dati applicati ai dispositivi endpoint passando al [Dashboard di gestione avvisi DLP](dlp-configure-view-alerts-policies.md).</span><span class="sxs-lookup"><span data-stu-id="2b10e-183">You can view alerts related to DLP policies enforced on endpoint devices by going to the [DLP Alerts Management Dashboard](dlp-configure-view-alerts-policies.md).</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2b10e-184">![Info sugli avvisi](../media/Alert-info-1.png)</span><span class="sxs-lookup"><span data-stu-id="2b10e-184">![Alert info](../media/Alert-info-1.png)</span></span>

<span data-ttu-id="2b10e-185">È anche possibile visualizzare i dettagli dell'evento associato con metadati completi nello stesso dashboard</span><span class="sxs-lookup"><span data-stu-id="2b10e-185">You can also view details of the associated event with rich metadata in the same dashboard</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2b10e-186">![info sull'evento](../media/Event-info-1.png)</span><span class="sxs-lookup"><span data-stu-id="2b10e-186">![event info](../media/Event-info-1.png)</span></span>

<span data-ttu-id="2b10e-187">Dopo l'onboarding di un dispositivo, le informazioni sulle attività controllate fluiscono in Esplora attività anche prima che vengano configurati e distribuiti criteri di prevenzione della perdita dei dati che usano dispositivi come posizione.</span><span class="sxs-lookup"><span data-stu-id="2b10e-187">Once a device is onboarded, information about audited activities flows into Activity explorer even before you configure and deploy any DLP policies that have devices as a location.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2b10e-188">![eventi di prevenzione della perdita di dati degli endpoint in Esplora attività](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="2b10e-188">![endpoint dlp events in activity explorer](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span></span>

<span data-ttu-id="2b10e-189">Endpoint DLP raccoglie informazioni complete sulle attività controllate.</span><span class="sxs-lookup"><span data-stu-id="2b10e-189">Endpoint DLP collects extensive information on audited activity.</span></span>

<span data-ttu-id="2b10e-190">Ad esempio, se un file viene copiato in un supporto USB rimovibile, nei dettagli attività vengono visualizzati questi attributi:</span><span class="sxs-lookup"><span data-stu-id="2b10e-190">For example, if a file is copied to removable USB media, you'd see these attributes in the activity details:</span></span>

- <span data-ttu-id="2b10e-191">tipo di attività</span><span class="sxs-lookup"><span data-stu-id="2b10e-191">activity type</span></span>
- <span data-ttu-id="2b10e-192">IP client</span><span class="sxs-lookup"><span data-stu-id="2b10e-192">client IP</span></span>
- <span data-ttu-id="2b10e-193">percorso file di destinazione</span><span class="sxs-lookup"><span data-stu-id="2b10e-193">target file path</span></span>
- <span data-ttu-id="2b10e-194">timestamp dell'attività</span><span class="sxs-lookup"><span data-stu-id="2b10e-194">happened timestamp</span></span>
- <span data-ttu-id="2b10e-195">nome del file</span><span class="sxs-lookup"><span data-stu-id="2b10e-195">file name</span></span>
- <span data-ttu-id="2b10e-196">utente</span><span class="sxs-lookup"><span data-stu-id="2b10e-196">user</span></span>
- <span data-ttu-id="2b10e-197">estensione del file</span><span class="sxs-lookup"><span data-stu-id="2b10e-197">file extension</span></span>
- <span data-ttu-id="2b10e-198">dimensioni del file</span><span class="sxs-lookup"><span data-stu-id="2b10e-198">file size</span></span>
- <span data-ttu-id="2b10e-199">tipo di informazioni sensibili (se applicabile)</span><span class="sxs-lookup"><span data-stu-id="2b10e-199">sensitive information type (if applicable)</span></span>
- <span data-ttu-id="2b10e-200">valore SHA1</span><span class="sxs-lookup"><span data-stu-id="2b10e-200">sha1 value</span></span>
- <span data-ttu-id="2b10e-201">valore SHA256</span><span class="sxs-lookup"><span data-stu-id="2b10e-201">sha256 value</span></span>
- <span data-ttu-id="2b10e-202">nome file precedente</span><span class="sxs-lookup"><span data-stu-id="2b10e-202">previous file name</span></span>
- <span data-ttu-id="2b10e-203">posizione</span><span class="sxs-lookup"><span data-stu-id="2b10e-203">location</span></span>
- <span data-ttu-id="2b10e-204">padre</span><span class="sxs-lookup"><span data-stu-id="2b10e-204">parent</span></span>
- <span data-ttu-id="2b10e-205">percorso file</span><span class="sxs-lookup"><span data-stu-id="2b10e-205">filepath</span></span>
- <span data-ttu-id="2b10e-206">tipo di percorso di origine</span><span class="sxs-lookup"><span data-stu-id="2b10e-206">source location type</span></span>
- <span data-ttu-id="2b10e-207">piattaforma</span><span class="sxs-lookup"><span data-stu-id="2b10e-207">platform</span></span>
- <span data-ttu-id="2b10e-208">nome dispositivo</span><span class="sxs-lookup"><span data-stu-id="2b10e-208">device name</span></span>
- <span data-ttu-id="2b10e-209">tipo di percorso di destinazione</span><span class="sxs-lookup"><span data-stu-id="2b10e-209">destination location type</span></span>
- <span data-ttu-id="2b10e-210">applicazione che ha eseguito la copia</span><span class="sxs-lookup"><span data-stu-id="2b10e-210">application that performed the copy</span></span>
- <span data-ttu-id="2b10e-211">ID dispositivo di Microsoft Defender per endpoint (se applicabile)</span><span class="sxs-lookup"><span data-stu-id="2b10e-211">Microsoft Defender for Endpoint device ID (if applicable)</span></span>
- <span data-ttu-id="2b10e-212">produttore del dispositivo multimediale rimovibile</span><span class="sxs-lookup"><span data-stu-id="2b10e-212">removable media device manufacturer</span></span>
- <span data-ttu-id="2b10e-213">modello di dispositivo multimediale rimovibile</span><span class="sxs-lookup"><span data-stu-id="2b10e-213">removable media device model</span></span>
- <span data-ttu-id="2b10e-214">numero di serie del dispositivo multimediale rimovibile</span><span class="sxs-lookup"><span data-stu-id="2b10e-214">removable media device serial number</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2b10e-215">![attributi dell'attività di copia su USB](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span><span class="sxs-lookup"><span data-stu-id="2b10e-215">![copy to usb activity attributes](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span></span>

## <a name="next-steps"></a><span data-ttu-id="2b10e-216">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="2b10e-216">Next steps</span></span>

<span data-ttu-id="2b10e-217">Dopo avere acquisito familiarità con Endpoint DLP, è possibile proseguire con questi argomenti:</span><span class="sxs-lookup"><span data-stu-id="2b10e-217">Now that you've learned about Endpoint DLP, your next steps are:</span></span>

1. [<span data-ttu-id="2b10e-218">Introduzione alla prevenzione della perdita di dati degli endpoint Microsoft</span><span class="sxs-lookup"><span data-stu-id="2b10e-218">Getting started with Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
2. [<span data-ttu-id="2b10e-219">Uso della prevenzione della perdita di dati degli endpoint Microsoft</span><span class="sxs-lookup"><span data-stu-id="2b10e-219">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="2b10e-220">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2b10e-220">See also</span></span>

- [<span data-ttu-id="2b10e-221">Introduzione alla prevenzione della perdita di dati degli endpoint Microsoft</span><span class="sxs-lookup"><span data-stu-id="2b10e-221">Getting started with Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="2b10e-222">Uso della prevenzione della perdita di dati degli endpoint Microsoft</span><span class="sxs-lookup"><span data-stu-id="2b10e-222">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="2b10e-223">Informazioni sulla prevenzione della perdita di dati</span><span class="sxs-lookup"><span data-stu-id="2b10e-223">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="2b10e-224">Creare, testare e ottimizzare un criterio di prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="2b10e-224">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="2b10e-225">Introduzione a Esplora attività</span><span class="sxs-lookup"><span data-stu-id="2b10e-225">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="2b10e-226">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="2b10e-226">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/)
- [<span data-ttu-id="2b10e-227">Gestione dei rischi Insider</span><span class="sxs-lookup"><span data-stu-id="2b10e-227">Insider Risk management</span></span>](insider-risk-management.md)
