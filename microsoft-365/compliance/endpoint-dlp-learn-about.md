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
ms.openlocfilehash: d5394499b5514e6e0a49f958a62e70cde61ebf44
ms.sourcegitcommit: 88820cd2536a7da868e472d10b4d265c52e5692b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/17/2021
ms.locfileid: "50279310"
---
# <a name="learn-about-microsoft-365-endpoint-data-loss-prevention"></a><span data-ttu-id="23915-104">Informazioni sulla prevenzione della perdita di dati degli endpoint di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="23915-104">Learn about Microsoft 365 Endpoint data loss prevention</span></span>

<span data-ttu-id="23915-105">È possibile usare la prevenzione della perdita dei dati (DLP) di Microsoft 365 per monitorare le azioni intraprese sugli elementi che si considerano sensibili e per evitare la condivisione involontaria di tali elementi.</span><span class="sxs-lookup"><span data-stu-id="23915-105">You can use Microsoft 365 data loss prevention (DLP) to monitor the actions that are being taken on items you've determined to be sensitive and to help prevent the unintentional sharing of those items.</span></span> <span data-ttu-id="23915-106">Per altre informazioni, vedere [Panoramica sulla prevenzione della perdita dei dati](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="23915-106">For more information on DLP, see [Overview of data loss prevention](data-loss-prevention-policies.md).</span></span>

<span data-ttu-id="23915-107">La **prevenzione della perdita di dati degli endpoint** (Endpoint DLP) estende le funzionalità di monitoraggio e protezione delle attività di DLP agli elementi sensibili presenti nei dispositivi Windows 10.</span><span class="sxs-lookup"><span data-stu-id="23915-107">**Endpoint data loss prevention** (Endpoint DLP) extends the activity monitoring and protection capabilities of DLP to sensitive items that are on Windows 10 devices.</span></span> <span data-ttu-id="23915-108">Dopo aver eseguito l'onboarding dei dispositivi nelle soluzioni del Centro conformità Microsoft 365, le informazioni sulle azioni che gli utenti stanno eseguendo sugli elementi sensibili sono rese visibili in [Esplora attività](data-classification-activity-explorer.md) ed è possibile applicare azioni di protezione su tali elementi tramite [criteri DLP](create-test-tune-dlp-policy.md).</span><span class="sxs-lookup"><span data-stu-id="23915-108">Once devices are onboarded into the Microsoft 365 compliance solutions, the information about what users are doing with sensitive items is made visible in [activity explorer](data-classification-activity-explorer.md) and you can enforce protective actions on those items via [DLP policies](create-test-tune-dlp-policy.md).</span></span>

## <a name="endpoint-activities-you-can-monitor-and-take-action-on"></a><span data-ttu-id="23915-109">Attività endpoint che è possibile monitorare e su cui si può intervenire</span><span class="sxs-lookup"><span data-stu-id="23915-109">Endpoint activities you can monitor and take action on</span></span>

<span data-ttu-id="23915-110">Microsoft Endpoint DLP consente di controllare e gestire i tipi di attività seguenti, che gli utenti possono eseguire sugli elementi sensibili nei dispositivi che eseguono Windows 10.</span><span class="sxs-lookup"><span data-stu-id="23915-110">Microsoft Endpoint DLP enables you to audit and manage the following types of activities users take on sensitive items on devices running Windows 10.</span></span> 

|<span data-ttu-id="23915-111">attività</span><span class="sxs-lookup"><span data-stu-id="23915-111">activity</span></span> |<span data-ttu-id="23915-112">descrizione</span><span class="sxs-lookup"><span data-stu-id="23915-112">description</span></span>  | <span data-ttu-id="23915-113">controllabile/limitabile</span><span class="sxs-lookup"><span data-stu-id="23915-113">auditable/restictable</span></span>|
|---------|---------|---------|
|<span data-ttu-id="23915-114">caricare su servizio cloud o accedere con browser non consentiti</span><span class="sxs-lookup"><span data-stu-id="23915-114">upload to cloud service, or access by unallowed browsers</span></span>    | <span data-ttu-id="23915-115">Rileva quando un utente tenta di caricare un elemento in un dominio di servizio riservato o di accedere a un elemento attraverso un browser.</span><span class="sxs-lookup"><span data-stu-id="23915-115">Detects when a user attempts to upload an item to a restricted service domain or access an item through a browser.</span></span>  <span data-ttu-id="23915-116">Se si utilizza un browser che è elencato in DLP come browser non consentito, l'attività di upload verrà bloccata e l'utente verrà reindirizzato all'utilizzo di Edge Chromium.</span><span class="sxs-lookup"><span data-stu-id="23915-116">If they are using a browser that is listed in DLP as an being an unallowed browser, the upload activity will be blocked and the user is redirected to use Edge Chromium.</span></span> <span data-ttu-id="23915-117">Edge Chromium permetterà o bloccherà il caricamento o l'accesso in base alla configurazione dei criteri DLP</span><span class="sxs-lookup"><span data-stu-id="23915-117">Edge Chromium will then either allow or block the upload or access based on the DLP policy configuration</span></span>         |<span data-ttu-id="23915-118">controllabile e limitabile</span><span class="sxs-lookup"><span data-stu-id="23915-118">auditable and restrictable</span></span>|
|<span data-ttu-id="23915-119">copiare su altra app</span><span class="sxs-lookup"><span data-stu-id="23915-119">copy to other app</span></span>    |<span data-ttu-id="23915-120">Rileva quando un utente tenta di copiare le informazioni da un elemento protetto e poi le incolla in un'altra applicazione, processo o elemento.</span><span class="sxs-lookup"><span data-stu-id="23915-120">Detects when a user attempts to copy information from a protected item and then paste it into another app, process or item.</span></span> <span data-ttu-id="23915-121">Il processo di copiare e incollare informazioni all'interno della stessa applicazione, processo o elemento non viene rilevato da questa attività.</span><span class="sxs-lookup"><span data-stu-id="23915-121">Copying and pasting information within the same app, process, or item is not detected by this activity.</span></span>         | <span data-ttu-id="23915-122">controllabile e limitabile</span><span class="sxs-lookup"><span data-stu-id="23915-122">auditable and restrictable</span></span>|
|<span data-ttu-id="23915-123">copiare su supporto rimovibile USB</span><span class="sxs-lookup"><span data-stu-id="23915-123">copy to USB removable media</span></span> |<span data-ttu-id="23915-124">Rileva quando un utente tenta di copiare un elemento o un'informazione su un supporto rimovibile o un dispositivo USB.</span><span class="sxs-lookup"><span data-stu-id="23915-124">Detects when a user attempts to copy an item or information to removable media or USB device.</span></span>         | <span data-ttu-id="23915-125">controllabile e limitabile</span><span class="sxs-lookup"><span data-stu-id="23915-125">auditable and restrictable</span></span>|
|<span data-ttu-id="23915-126">copiare su condivisione di rete</span><span class="sxs-lookup"><span data-stu-id="23915-126">copy to a network share</span></span>    |<span data-ttu-id="23915-127">Rileva quando un utente tenta di copiare un elemento in una condivisione di rete o in un'unità di rete mappata</span><span class="sxs-lookup"><span data-stu-id="23915-127">Detects when a user attempts to copy an item to a network share or mapped network drive</span></span>         |<span data-ttu-id="23915-128">controllabile e limitabile</span><span class="sxs-lookup"><span data-stu-id="23915-128">auditable and restrictable</span></span>|
|<span data-ttu-id="23915-129">stampare un documento</span><span class="sxs-lookup"><span data-stu-id="23915-129">print a document</span></span>    |<span data-ttu-id="23915-130">Rileva quando un utente tenta di stampare un elemento protetto su una stampante locale o di rete.</span><span class="sxs-lookup"><span data-stu-id="23915-130">Detects when a user attempts to print a protected item to a local or network printer.</span></span>| <span data-ttu-id="23915-131">controllabile e limitabile</span><span class="sxs-lookup"><span data-stu-id="23915-131">auditable and restrictable</span></span>         |
|<span data-ttu-id="23915-132">creare un elemento.</span><span class="sxs-lookup"><span data-stu-id="23915-132">create an item</span></span>|<span data-ttu-id="23915-133">Rileva quando un utente crea un elemento</span><span class="sxs-lookup"><span data-stu-id="23915-133">Detects when a user creates an item</span></span>| <span data-ttu-id="23915-134">controllabile</span><span class="sxs-lookup"><span data-stu-id="23915-134">auditable</span></span>|
|<span data-ttu-id="23915-135">rinominare un elemento</span><span class="sxs-lookup"><span data-stu-id="23915-135">rename an item</span></span>|<span data-ttu-id="23915-136">Rileva quando un utente rinomina un elemento</span><span class="sxs-lookup"><span data-stu-id="23915-136">Detects when a user renames an item</span></span>| <span data-ttu-id="23915-137">controllabile</span><span class="sxs-lookup"><span data-stu-id="23915-137">auditable</span></span>|

 ## <a name="monitored-files"></a><span data-ttu-id="23915-138">File monitorati</span><span class="sxs-lookup"><span data-stu-id="23915-138">Monitored files</span></span>

<span data-ttu-id="23915-139">Endpoint DLP supporta il monitoraggio di questi tipi di file:</span><span class="sxs-lookup"><span data-stu-id="23915-139">Endpoint DLP supports monitoring of these file types:</span></span>

- <span data-ttu-id="23915-140">File di Word</span><span class="sxs-lookup"><span data-stu-id="23915-140">Word files</span></span>
- <span data-ttu-id="23915-141">File di PowerPoint</span><span class="sxs-lookup"><span data-stu-id="23915-141">PowerPoint files</span></span>
- <span data-ttu-id="23915-142">File di Excel</span><span class="sxs-lookup"><span data-stu-id="23915-142">Excel files</span></span>
- <span data-ttu-id="23915-143">File PDF</span><span class="sxs-lookup"><span data-stu-id="23915-143">PDF files</span></span>
- <span data-ttu-id="23915-144">File CSV</span><span class="sxs-lookup"><span data-stu-id="23915-144">.csv files</span></span>
- <span data-ttu-id="23915-145">File TSV</span><span class="sxs-lookup"><span data-stu-id="23915-145">.tsv files</span></span>
- <span data-ttu-id="23915-146">File TXT</span><span class="sxs-lookup"><span data-stu-id="23915-146">.txt files</span></span>
- <span data-ttu-id="23915-147">File RTF</span><span class="sxs-lookup"><span data-stu-id="23915-147">.rtf files</span></span>
- <span data-ttu-id="23915-148">File C</span><span class="sxs-lookup"><span data-stu-id="23915-148">.c files</span></span>
- <span data-ttu-id="23915-149">File CLASS</span><span class="sxs-lookup"><span data-stu-id="23915-149">.class files</span></span>
- <span data-ttu-id="23915-150">File CPP</span><span class="sxs-lookup"><span data-stu-id="23915-150">.cpp files</span></span>
- <span data-ttu-id="23915-151">File CS</span><span class="sxs-lookup"><span data-stu-id="23915-151">.cs files</span></span>
- <span data-ttu-id="23915-152">File H</span><span class="sxs-lookup"><span data-stu-id="23915-152">.h files</span></span>
- <span data-ttu-id="23915-153">File Java</span><span class="sxs-lookup"><span data-stu-id="23915-153">.java files</span></span>
 
<span data-ttu-id="23915-154">Per impostazione predefinita, Endpoint DLP controlla le attività per questi tipi di file anche in mancanza di una corrispondenza dei criteri.</span><span class="sxs-lookup"><span data-stu-id="23915-154">By default, endpoint DLP audits the activities for these file types, even if there isn't a policy match.</span></span> <span data-ttu-id="23915-155">Se si vogliono monitorare i dati solo se c'è una corrispondenza dei criteri, è possibile disattivare l'opzione **Controllare sempre le attività dei file per i dispositivi** nelle impostazioni globali di Endpoint DLP.</span><span class="sxs-lookup"><span data-stu-id="23915-155">If you only want monitoring data from policy matches, you can turn off the **Always audit file activity for devices** in the endpoint DLP global settings.</span></span> <span data-ttu-id="23915-156">Le attività in qualsiasi file di Word, PowerPoint, Excel, PDF e CSV vengono comunque sempre controllate.</span><span class="sxs-lookup"><span data-stu-id="23915-156">No matter what, activities on any Word, PowerPoint, Excel, PDF, and .csv file are always audited.</span></span>

<span data-ttu-id="23915-157">Endpoint DLP monitora le attività in base al tipo MIME, pertanto le attività verranno acquisite anche se l'estensione del file viene cambiata.</span><span class="sxs-lookup"><span data-stu-id="23915-157">Endpoint DLP monitors activity-based on MIME type, so activities will be captured even if the file extension is changed.</span></span> 

## <a name="whats-different-in-endpoint-dlp"></a><span data-ttu-id="23915-158">Cosa distingue Endpoint DLP</span><span class="sxs-lookup"><span data-stu-id="23915-158">What's different in Endpoint DLP</span></span>

<span data-ttu-id="23915-159">Ci sono alcuni concetti aggiuntivi che è necessario conoscere prima di approfondire l'utilizzo di Endpoint DLP.</span><span class="sxs-lookup"><span data-stu-id="23915-159">There are a few extra concepts that you need to be aware of before you dig into Endpoint DLP.</span></span>

### <a name="enabling-device-management"></a><span data-ttu-id="23915-160">Abilitare la gestione dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="23915-160">Enabling Device management</span></span>

<span data-ttu-id="23915-161">La gestione dei dispositivi è la funzionalità che consente la raccolta di dati di telemetria dai dispositivi e la introduce nelle soluzioni di conformità di Microsoft 365, come Endpoint DLP e [Gestione dei rischi Insider](insider-risk-management.md).</span><span class="sxs-lookup"><span data-stu-id="23915-161">Device management is the functionality that enables the collection of telemetry from devices and brings it into Microsoft 365 compliance solutions like Endpoint DLP and [Insider Risk management](insider-risk-management.md).</span></span> <span data-ttu-id="23915-162">È necessario eseguire l'onboarding di tutti i dispositivi che si vogliono usare come posizioni nei criteri DLP.</span><span class="sxs-lookup"><span data-stu-id="23915-162">You'll need to onboard all devices you want to use as locations in DLP policies.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="23915-163">![abilitare la gestione dei dispositivi](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="23915-163">![enable device management](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span></span>

<span data-ttu-id="23915-164">Onboarding e offboarding vengono gestiti tramite script scaricati dal centro gestione dispositivi.</span><span class="sxs-lookup"><span data-stu-id="23915-164">Onboarding and offboarding are handled via scripts you download from the Device management center.</span></span> <span data-ttu-id="23915-165">Nel centro sono disponibili script personalizzati per ognuno di questi metodi di distribuzione:</span><span class="sxs-lookup"><span data-stu-id="23915-165">The center has custom scripts for each of these deployment methods:</span></span>

- <span data-ttu-id="23915-166">script locale (fino a 10 computer)</span><span class="sxs-lookup"><span data-stu-id="23915-166">local script (up to 10 machines)</span></span>
- <span data-ttu-id="23915-167">Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="23915-167">Group policy</span></span>
- <span data-ttu-id="23915-168">System Center Configuration Manager (versione 1610 o successiva)</span><span class="sxs-lookup"><span data-stu-id="23915-168">System Center Configuration Manager (version 1610 or later)</span></span>
- <span data-ttu-id="23915-169">Gestione dispositivi mobili/Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="23915-169">Mobile Device Management/Microsoft Intune</span></span>
- <span data-ttu-id="23915-170">Script di onboarding VDI per dispositivi non persistenti</span><span class="sxs-lookup"><span data-stu-id="23915-170">VDI onboarding scripts for non-persistent machines</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="23915-171">![pagina di onboarding dispositivi](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span><span class="sxs-lookup"><span data-stu-id="23915-171">![device onboarding page](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span></span>

 <span data-ttu-id="23915-172">Seguire le procedure in [Introduzione a Microsoft 365 Endpoint DLP](endpoint-dlp-getting-started.md) per l'onboarding dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="23915-172">Use the procedures in [Getting started with Microsoft 365 Endpoint DLP](endpoint-dlp-getting-started.md) to onboard devices.</span></span>

<span data-ttu-id="23915-173">Se è stato eseguito l'onboarding di dispositivi tramite [Microsoft Defender per endpoint](https://docs.microsoft.com/windows/security/threat-protection/), questi dispositivi verranno visualizzati automaticamente nell'elenco dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="23915-173">If you have onboarded devices through [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/), those devices will automatically show up in the list of devices.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="23915-174">![elenco dispositivi gestiti](../media/endpoint-dlp-learn-about-2-device-list.png)</span><span class="sxs-lookup"><span data-stu-id="23915-174">![managed devices list](../media/endpoint-dlp-learn-about-2-device-list.png)</span></span>

### <a name="viewing-endpoint-dlp-data"></a><span data-ttu-id="23915-175">Visualizzazione dei dati di Endpoint DLP</span><span class="sxs-lookup"><span data-stu-id="23915-175">Viewing Endpoint DLP data</span></span>



<span data-ttu-id="23915-176">È possibile visualizzare gli avvisi correlati ai criteri di prevenzione della perdita dei dati applicati ai dispositivi endpoint passando al [Dashboard di gestione avvisi DLP](dlp-configure-view-alerts-policies.md).</span><span class="sxs-lookup"><span data-stu-id="23915-176">You can view alerts related to DLP policies enforced on endpoint devices by going to the [DLP Alerts Management Dashboard](dlp-configure-view-alerts-policies.md).</span></span>

![Info sugli avvisi](../media/Alert-info-1.png)

<span data-ttu-id="23915-178">È anche possibile visualizzare i dettagli dell'evento associato con metadati completi nello stesso dashboard</span><span class="sxs-lookup"><span data-stu-id="23915-178">You can also view details of the associated event with rich metadata in the same dashboard</span></span>

![info sull'evento](../media/Event-info-1.png)

<span data-ttu-id="23915-180">Dopo l'onboarding di un dispositivo, le informazioni sulle attività controllate fluiscono in Esplora attività anche prima che vengano configurati e distribuiti criteri di prevenzione della perdita dei dati che usano dispositivi come posizione.</span><span class="sxs-lookup"><span data-stu-id="23915-180">Once a device is onboarded, information about audited activities flows into Activity explorer even before you configure and deploy any DLP policies that have devices as a location.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="23915-181">![eventi di prevenzione della perdita di dati degli endpoint in Esplora attività](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="23915-181">![endpoint dlp events in activity explorer](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span></span>

<span data-ttu-id="23915-182">Endpoint DLP raccoglie informazioni complete sulle attività controllate.</span><span class="sxs-lookup"><span data-stu-id="23915-182">Endpoint DLP collects extensive information on audited activity.</span></span>

<span data-ttu-id="23915-183">Ad esempio, se un file viene copiato in un supporto USB rimovibile, nei dettagli attività vengono visualizzati questi attributi:</span><span class="sxs-lookup"><span data-stu-id="23915-183">For example, if a file is copied to removable USB media, you'd see these attributes in the activity details:</span></span>

- <span data-ttu-id="23915-184">tipo di attività</span><span class="sxs-lookup"><span data-stu-id="23915-184">activity type</span></span>
- <span data-ttu-id="23915-185">IP client</span><span class="sxs-lookup"><span data-stu-id="23915-185">client IP</span></span>
- <span data-ttu-id="23915-186">percorso file di destinazione</span><span class="sxs-lookup"><span data-stu-id="23915-186">target file path</span></span>
- <span data-ttu-id="23915-187">timestamp dell'attività</span><span class="sxs-lookup"><span data-stu-id="23915-187">happened timestamp</span></span>
- <span data-ttu-id="23915-188">nome del file</span><span class="sxs-lookup"><span data-stu-id="23915-188">file name</span></span>
- <span data-ttu-id="23915-189">utente</span><span class="sxs-lookup"><span data-stu-id="23915-189">user</span></span>
- <span data-ttu-id="23915-190">estensione del file</span><span class="sxs-lookup"><span data-stu-id="23915-190">file extension</span></span>
- <span data-ttu-id="23915-191">dimensioni del file</span><span class="sxs-lookup"><span data-stu-id="23915-191">file size</span></span>
- <span data-ttu-id="23915-192">tipo di informazioni sensibili (se applicabile)</span><span class="sxs-lookup"><span data-stu-id="23915-192">sensitive information type (if applicable)</span></span>
- <span data-ttu-id="23915-193">valore SHA1</span><span class="sxs-lookup"><span data-stu-id="23915-193">sha1 value</span></span>
- <span data-ttu-id="23915-194">valore SHA256</span><span class="sxs-lookup"><span data-stu-id="23915-194">sha256 value</span></span>
- <span data-ttu-id="23915-195">nome file precedente</span><span class="sxs-lookup"><span data-stu-id="23915-195">previous file name</span></span>
- <span data-ttu-id="23915-196">posizione</span><span class="sxs-lookup"><span data-stu-id="23915-196">location</span></span>
- <span data-ttu-id="23915-197">padre</span><span class="sxs-lookup"><span data-stu-id="23915-197">parent</span></span>
- <span data-ttu-id="23915-198">percorso file</span><span class="sxs-lookup"><span data-stu-id="23915-198">filepath</span></span>
- <span data-ttu-id="23915-199">tipo di percorso di origine</span><span class="sxs-lookup"><span data-stu-id="23915-199">source location type</span></span>
- <span data-ttu-id="23915-200">piattaforma</span><span class="sxs-lookup"><span data-stu-id="23915-200">platform</span></span>
- <span data-ttu-id="23915-201">nome dispositivo</span><span class="sxs-lookup"><span data-stu-id="23915-201">device name</span></span>
- <span data-ttu-id="23915-202">tipo di percorso di destinazione</span><span class="sxs-lookup"><span data-stu-id="23915-202">destination location type</span></span>
- <span data-ttu-id="23915-203">applicazione che ha eseguito la copia</span><span class="sxs-lookup"><span data-stu-id="23915-203">application that performed the copy</span></span>
- <span data-ttu-id="23915-204">ID dispositivo di Microsoft Defender per endpoint (se applicabile)</span><span class="sxs-lookup"><span data-stu-id="23915-204">Microsoft Defender for Endpoint device ID (if applicable)</span></span>
- <span data-ttu-id="23915-205">produttore del dispositivo multimediale rimovibile</span><span class="sxs-lookup"><span data-stu-id="23915-205">removable media device manufacturer</span></span>
- <span data-ttu-id="23915-206">modello di dispositivo multimediale rimovibile</span><span class="sxs-lookup"><span data-stu-id="23915-206">removable media device model</span></span>
- <span data-ttu-id="23915-207">numero di serie del dispositivo multimediale rimovibile</span><span class="sxs-lookup"><span data-stu-id="23915-207">removable media device serial number</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="23915-208">![attributi dell'attività di copia su USB](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span><span class="sxs-lookup"><span data-stu-id="23915-208">![copy to usb activity attributes](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span></span>

## <a name="next-steps"></a><span data-ttu-id="23915-209">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="23915-209">Next steps</span></span>

<span data-ttu-id="23915-210">Dopo avere acquisito familiarità con Endpoint DLP, è possibile proseguire con questi argomenti:</span><span class="sxs-lookup"><span data-stu-id="23915-210">Now that you've learned about Endpoint DLP, your next steps are:</span></span>

1) [<span data-ttu-id="23915-211">Introduzione alla prevenzione della perdita di dati degli endpoint Microsoft</span><span class="sxs-lookup"><span data-stu-id="23915-211">Getting started with Microsoft Endpoint data loss prevention </span></span>](endpoint-dlp-getting-started.md)
2) [<span data-ttu-id="23915-212">Uso della prevenzione della perdita di dati degli endpoint Microsoft</span><span class="sxs-lookup"><span data-stu-id="23915-212">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="23915-213">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="23915-213">See also</span></span>

- [<span data-ttu-id="23915-214">Introduzione alla prevenzione della perdita di dati degli endpoint Microsoft</span><span class="sxs-lookup"><span data-stu-id="23915-214">Getting started with Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="23915-215">Uso della prevenzione della perdita di dati degli endpoint Microsoft</span><span class="sxs-lookup"><span data-stu-id="23915-215">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="23915-216">Panoramica sulla prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="23915-216">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="23915-217">Creare, testare e ottimizzare un criterio di prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="23915-217">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="23915-218">Introduzione a Esplora attività</span><span class="sxs-lookup"><span data-stu-id="23915-218">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="23915-219">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="23915-219">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="23915-220">Gestione dei rischi Insider</span><span class="sxs-lookup"><span data-stu-id="23915-220">Insider Risk management</span></span>](insider-risk-management.md)
