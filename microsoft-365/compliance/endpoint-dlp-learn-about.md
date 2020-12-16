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
ms.openlocfilehash: 1dac32505144c3966ad2219cc69a33ba29f194dc
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/15/2020
ms.locfileid: "49682627"
---
# <a name="learn-about-microsoft-365-endpoint-data-loss-prevention"></a><span data-ttu-id="29b04-104">Informazioni sulla prevenzione della perdita di dati degli endpoint di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="29b04-104">Learn about Microsoft 365 Endpoint data loss prevention</span></span>

<span data-ttu-id="29b04-105">È possibile usare la prevenzione della perdita dei dati (DLP) di Microsoft 365 per monitorare le azioni intraprese sugli elementi che si considerano sensibili e per evitare la condivisione involontaria di tali elementi.</span><span class="sxs-lookup"><span data-stu-id="29b04-105">You can use Microsoft 365 data loss prevention (DLP) to monitor the actions that are being taken on items you've determined to be sensitive and to help prevent the unintentional sharing of those items.</span></span> <span data-ttu-id="29b04-106">Per altre informazioni, vedere [Panoramica sulla prevenzione della perdita dei dati](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="29b04-106">For more information on DLP, see [Overview of data loss prevention](data-loss-prevention-policies.md).</span></span>

<span data-ttu-id="29b04-107">La **prevenzione della perdita di dati degli endpoint** (Endpoint DLP) estende le funzionalità di monitoraggio e protezione delle attività di DLP agli elementi sensibili presenti nei dispositivi Windows 10.</span><span class="sxs-lookup"><span data-stu-id="29b04-107">**Endpoint data loss prevention** (Endpoint DLP) extends the activity monitoring and protection capabilities of DLP to sensitive items that are on Windows 10 devices.</span></span> <span data-ttu-id="29b04-108">Dopo aver eseguito l'onboarding dei dispositivi nelle soluzioni del Centro conformità Microsoft 365, le informazioni sulle azioni che gli utenti stanno eseguendo sugli elementi sensibili sono rese visibili in [Esplora attività](data-classification-activity-explorer.md) ed è possibile applicare azioni di protezione su tali elementi tramite [criteri DLP](create-test-tune-dlp-policy.md).</span><span class="sxs-lookup"><span data-stu-id="29b04-108">Once devices are onboarded into the Microsoft 365 compliance solutions, the information about what users are doing with sensitive items is made visible in [activity explorer](data-classification-activity-explorer.md) and you can enforce protective actions on those items via [DLP policies](create-test-tune-dlp-policy.md).</span></span>

## <a name="endpoint-activities-you-can-monitor-and-take-action-on"></a><span data-ttu-id="29b04-109">Attività endpoint che è possibile monitorare e su cui si può intervenire</span><span class="sxs-lookup"><span data-stu-id="29b04-109">Endpoint activities you can monitor and take action on</span></span>

<span data-ttu-id="29b04-110">Microsoft Endpoint DLP consente di controllare e gestire i tipi di attività seguenti, che gli utenti possono eseguire sugli elementi sensibili nei dispositivi che eseguono Windows 10.</span><span class="sxs-lookup"><span data-stu-id="29b04-110">Microsoft Endpoint DLP enables you to audit and manage the following types of activities users take on sensitive items on devices running Windows 10.</span></span>


|<span data-ttu-id="29b04-111">attività</span><span class="sxs-lookup"><span data-stu-id="29b04-111">activity</span></span> |<span data-ttu-id="29b04-112">descrizione</span><span class="sxs-lookup"><span data-stu-id="29b04-112">description</span></span>  | <span data-ttu-id="29b04-113">controllabile/limitabile</span><span class="sxs-lookup"><span data-stu-id="29b04-113">auditable/restictable</span></span>|
|---------|---------|---------|
|<span data-ttu-id="29b04-114">caricare su servizio cloud o accedere con browser non consentiti</span><span class="sxs-lookup"><span data-stu-id="29b04-114">upload to cloud service, or access by unallowed browsers</span></span>    | <span data-ttu-id="29b04-115">Rileva quando un utente tenta di caricare un elemento in un dominio di servizio riservato o di accedere a un elemento attraverso un browser.</span><span class="sxs-lookup"><span data-stu-id="29b04-115">Detects when a user attempts to upload an item to a restricted service domain or access an item through a browser.</span></span>  <span data-ttu-id="29b04-116">Se si utilizza un browser che è elencato in DLP come browser non consentito, l'attività di upload verrà bloccata e l'utente verrà reindirizzato all'utilizzo di Edge Chromium.</span><span class="sxs-lookup"><span data-stu-id="29b04-116">If they are using a browser that is listed in DLP as an being an unallowed browser, the upload activity will be blocked and the user is redirected to use Edge Chromium.</span></span> <span data-ttu-id="29b04-117">Edge Chromium permetterà o bloccherà il caricamento o l'accesso in base alla configurazione dei criteri DLP</span><span class="sxs-lookup"><span data-stu-id="29b04-117">Edge Chromium will then either allow or block the upload or access based on the DLP policy configuration</span></span>         |<span data-ttu-id="29b04-118">controllabile e limitabile</span><span class="sxs-lookup"><span data-stu-id="29b04-118">auditable and restrictable</span></span>|
|<span data-ttu-id="29b04-119">copiare su altra app</span><span class="sxs-lookup"><span data-stu-id="29b04-119">copy to other app</span></span>    |<span data-ttu-id="29b04-120">Rileva quando un utente tenta di copiare le informazioni da un elemento protetto e poi le incolla in un'altra applicazione, processo o elemento.</span><span class="sxs-lookup"><span data-stu-id="29b04-120">Detects when a user attempts to copy information from a protected item and then paste it into another app, process or item.</span></span> <span data-ttu-id="29b04-121">Il processo di copiare e incollare informazioni all'interno della stessa applicazione, processo o elemento non viene rilevato da questa attività.</span><span class="sxs-lookup"><span data-stu-id="29b04-121">Copying and pasting information within the same app, process, or item is not detected by this activity.</span></span>         | <span data-ttu-id="29b04-122">controllabile e limitabile</span><span class="sxs-lookup"><span data-stu-id="29b04-122">auditable and restrictable</span></span>|
|<span data-ttu-id="29b04-123">copiare su supporto rimovibile USB</span><span class="sxs-lookup"><span data-stu-id="29b04-123">copy to USB removable media</span></span> |<span data-ttu-id="29b04-124">Rileva quando un utente tenta di copiare un elemento o un'informazione su un supporto rimovibile o un dispositivo USB.</span><span class="sxs-lookup"><span data-stu-id="29b04-124">Detects when a user attempts to copy an item or information to removable media or USB device.</span></span>         | <span data-ttu-id="29b04-125">controllabile e limitabile</span><span class="sxs-lookup"><span data-stu-id="29b04-125">auditable and restrictable</span></span>|
|<span data-ttu-id="29b04-126">copiare su condivisione di rete</span><span class="sxs-lookup"><span data-stu-id="29b04-126">copy to a network share</span></span>    |<span data-ttu-id="29b04-127">Rileva quando un utente tenta di copiare un elemento in una condivisione di rete o in un'unità di rete mappata</span><span class="sxs-lookup"><span data-stu-id="29b04-127">Detects when a user attempts to copy an item to a network share or mapped network drive</span></span>         |<span data-ttu-id="29b04-128">controllabile e limitabile</span><span class="sxs-lookup"><span data-stu-id="29b04-128">auditable and restrictable</span></span>|
|<span data-ttu-id="29b04-129">stampare un documento</span><span class="sxs-lookup"><span data-stu-id="29b04-129">print a document</span></span>    |<span data-ttu-id="29b04-130">Rileva quando un utente tenta di stampare un elemento protetto su una stampante locale o di rete.</span><span class="sxs-lookup"><span data-stu-id="29b04-130">Detects when a user attempts to print a protected item to a local or network printer.</span></span>| <span data-ttu-id="29b04-131">controllabile e limitabile</span><span class="sxs-lookup"><span data-stu-id="29b04-131">auditable and restrictable</span></span>         |
|<span data-ttu-id="29b04-132">creare un elemento.</span><span class="sxs-lookup"><span data-stu-id="29b04-132">create an item</span></span>|<span data-ttu-id="29b04-133">Rileva quando un utente crea un elemento</span><span class="sxs-lookup"><span data-stu-id="29b04-133">Detects when a user creates an item</span></span>| <span data-ttu-id="29b04-134">controllabile</span><span class="sxs-lookup"><span data-stu-id="29b04-134">auditable</span></span>|
|<span data-ttu-id="29b04-135">rinominare un elemento</span><span class="sxs-lookup"><span data-stu-id="29b04-135">rename an item</span></span>|<span data-ttu-id="29b04-136">Rileva quando un utente rinomina un elemento</span><span class="sxs-lookup"><span data-stu-id="29b04-136">Detects when a user renames an item</span></span>| <span data-ttu-id="29b04-137">controllabile</span><span class="sxs-lookup"><span data-stu-id="29b04-137">auditable</span></span>|


## <a name="whats-different-in-endpoint-dlp"></a><span data-ttu-id="29b04-138">Cosa distingue Endpoint DLP</span><span class="sxs-lookup"><span data-stu-id="29b04-138">What's different in Endpoint DLP</span></span>

<span data-ttu-id="29b04-139">Ci sono alcuni concetti aggiuntivi che è necessario conoscere prima di approfondire l'utilizzo di Endpoint DLP.</span><span class="sxs-lookup"><span data-stu-id="29b04-139">There are a few extra concepts that you need to be aware of before you dig into Endpoint DLP.</span></span>

### <a name="enabling-device-management"></a><span data-ttu-id="29b04-140">Abilitare la gestione dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="29b04-140">Enabling Device management</span></span>

<span data-ttu-id="29b04-141">La gestione dei dispositivi è la funzionalità che consente la raccolta di dati di telemetria dai dispositivi e la introduce nelle soluzioni di conformità di Microsoft 365, come Endpoint DLP e [Gestione dei rischi Insider](insider-risk-management.md).</span><span class="sxs-lookup"><span data-stu-id="29b04-141">Device management is the functionality that enables the collection of telemetry from devices and brings it into Microsoft 365 compliance solutions like Endpoint DLP and [Insider Risk management](insider-risk-management.md).</span></span> <span data-ttu-id="29b04-142">È necessario eseguire l'onboarding di tutti i dispositivi che si vogliono usare come posizioni nei criteri DLP.</span><span class="sxs-lookup"><span data-stu-id="29b04-142">You'll need to onboard all devices you want to use as locations in DLP policies.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="29b04-143">![abilitare la gestione dei dispositivi](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="29b04-143">![enable device management](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span></span>

<span data-ttu-id="29b04-144">Onboarding e offboarding vengono gestiti tramite script scaricati dal centro gestione dispositivi.</span><span class="sxs-lookup"><span data-stu-id="29b04-144">Onboarding and offboarding are handled via scripts you download from the Device management center.</span></span> <span data-ttu-id="29b04-145">Nel centro sono disponibili script personalizzati per ognuno di questi metodi di distribuzione:</span><span class="sxs-lookup"><span data-stu-id="29b04-145">The center has custom scripts for each of these deployment methods:</span></span>

- <span data-ttu-id="29b04-146">script locale (fino a 10 computer)</span><span class="sxs-lookup"><span data-stu-id="29b04-146">local script (up to 10 machines)</span></span>
- <span data-ttu-id="29b04-147">Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="29b04-147">Group policy</span></span>
- <span data-ttu-id="29b04-148">System Center Configuration Manager (versione 1610 o successiva)</span><span class="sxs-lookup"><span data-stu-id="29b04-148">System Center Configuration Manager (version 1610 or later)</span></span>
- <span data-ttu-id="29b04-149">Gestione dispositivi mobili/Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="29b04-149">Mobile Device Management/Microsoft Intune</span></span>
- <span data-ttu-id="29b04-150">Script di onboarding VDI per dispositivi non persistenti</span><span class="sxs-lookup"><span data-stu-id="29b04-150">VDI onboarding scripts for non-persistent machines</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="29b04-151">![pagina di onboarding dispositivi](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span><span class="sxs-lookup"><span data-stu-id="29b04-151">![device onboarding page](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span></span>

 <span data-ttu-id="29b04-152">Seguire le procedure in [Introduzione a Microsoft 365 Endpoint DLP](endpoint-dlp-getting-started.md) per l'onboarding dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="29b04-152">Use the procedures in [Getting started with Microsoft 365 Endpoint DLP](endpoint-dlp-getting-started.md) to onboard devices.</span></span>

<span data-ttu-id="29b04-153">Se è stato eseguito l'onboarding di dispositivi tramite [Microsoft Defender per endpoint](https://docs.microsoft.com/windows/security/threat-protection/), questi dispositivi verranno visualizzati automaticamente nell'elenco dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="29b04-153">If you have onboarded devices through [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/), those devices will automatically show up in the list of devices.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="29b04-154">![elenco dispositivi gestiti](../media/endpoint-dlp-learn-about-2-device-list.png)</span><span class="sxs-lookup"><span data-stu-id="29b04-154">![managed devices list](../media/endpoint-dlp-learn-about-2-device-list.png)</span></span>

### <a name="viewing-endpoint-dlp-data"></a><span data-ttu-id="29b04-155">Visualizzazione dei dati di Endpoint DLP</span><span class="sxs-lookup"><span data-stu-id="29b04-155">Viewing Endpoint DLP data</span></span>

 <span data-ttu-id="29b04-156">La Prevenzione della perdita di dati degli endpoint monitora le attività in base al tipo MIME, in modo che le attività vengano acquisite anche se l'estensione del file viene cambiata.</span><span class="sxs-lookup"><span data-stu-id="29b04-156">Endpoint DLP monitors activity-based on MIME type, so activities will be captured even if the file extension is changed.</span></span> <span data-ttu-id="29b04-157">Al momento sono supportati i seguenti tipi di file:</span><span class="sxs-lookup"><span data-stu-id="29b04-157">At this time the following file types are supported:</span></span>

- <span data-ttu-id="29b04-158">File di Word</span><span class="sxs-lookup"><span data-stu-id="29b04-158">Word files</span></span>
- <span data-ttu-id="29b04-159">File di PowerPoint</span><span class="sxs-lookup"><span data-stu-id="29b04-159">PowerPoint files</span></span>
- <span data-ttu-id="29b04-160">File di Excel</span><span class="sxs-lookup"><span data-stu-id="29b04-160">Excel files</span></span>
- <span data-ttu-id="29b04-161">File PDF</span><span class="sxs-lookup"><span data-stu-id="29b04-161">PDF files</span></span>
- <span data-ttu-id="29b04-162">File CSV</span><span class="sxs-lookup"><span data-stu-id="29b04-162">.csv files</span></span>
- <span data-ttu-id="29b04-163">File TSV</span><span class="sxs-lookup"><span data-stu-id="29b04-163">.tsv files</span></span>
- <span data-ttu-id="29b04-164">File TXT</span><span class="sxs-lookup"><span data-stu-id="29b04-164">.txt files</span></span>
- <span data-ttu-id="29b04-165">File RTF</span><span class="sxs-lookup"><span data-stu-id="29b04-165">.rtf files</span></span>
- <span data-ttu-id="29b04-166">File C</span><span class="sxs-lookup"><span data-stu-id="29b04-166">.c files</span></span>
- <span data-ttu-id="29b04-167">File CLASS</span><span class="sxs-lookup"><span data-stu-id="29b04-167">.class files</span></span>
- <span data-ttu-id="29b04-168">File CPP</span><span class="sxs-lookup"><span data-stu-id="29b04-168">.cpp files</span></span>
- <span data-ttu-id="29b04-169">File CS</span><span class="sxs-lookup"><span data-stu-id="29b04-169">.cs files</span></span>
- <span data-ttu-id="29b04-170">File H</span><span class="sxs-lookup"><span data-stu-id="29b04-170">.h files</span></span>
- <span data-ttu-id="29b04-171">File Java</span><span class="sxs-lookup"><span data-stu-id="29b04-171">.java files</span></span>

> [!NOTE]
> <span data-ttu-id="29b04-172">La prevenzione della perdita di dati degli endpoint valuta i file di tutti i tipi precedenti rispetto ai criteri DLP e applica le azioni di protezione di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="29b04-172">Endpoint DLP evaluates files of all the above types against the DLP policy and applies protection actions accordingly.</span></span> <span data-ttu-id="29b04-173">Tutti i file che corrispondono a un criterio DLP vengono controllati per tutte le azioni supportate, anche se non vengono bloccati.</span><span class="sxs-lookup"><span data-stu-id="29b04-173">All files that match a DLP policy are audited for all supported actions, even if they aren't blocked.</span></span> <span data-ttu-id="29b04-174">Inoltre, le attività sui file eseguite in qualsiasi file di Word, PowerPoint, Excel, PDF e CSV vengono controllate per impostazione predefinita, indipendentemente dal fatto che esista un criterio DLP o che corrisponda a questi file.</span><span class="sxs-lookup"><span data-stu-id="29b04-174">In addition, file activity performed on any Word, PowerPoint, Excel, PDF, and .csv file is audited by default, independent of whether a DLP policy exists or matches these files.</span></span>

<span data-ttu-id="29b04-175">È possibile visualizzare gli avvisi correlati ai criteri di prevenzione della perdita dei dati applicati ai dispositivi endpoint passando al [Dashboard di gestione avvisi DLP](dlp-configure-view-alerts-policies.md).</span><span class="sxs-lookup"><span data-stu-id="29b04-175">You can view alerts related to DLP policies enforced on endpoint devices by going to the [DLP Alerts Management Dashboard](dlp-configure-view-alerts-policies.md).</span></span>

![Info sugli avvisi](../media/Alert-info-1.png)

<span data-ttu-id="29b04-177">È anche possibile visualizzare i dettagli dell'evento associato con metadati completi nello stesso dashboard</span><span class="sxs-lookup"><span data-stu-id="29b04-177">You can also view details of the associated event with rich metadata in the same dashboard</span></span>

![info sull'evento](../media/Event-info-1.png)

<span data-ttu-id="29b04-179">Dopo l'onboarding di un dispositivo, le informazioni sulle attività controllate fluiscono in Esplora attività anche prima che vengano configurati e distribuiti criteri di prevenzione della perdita dei dati che usano dispositivi come posizione.</span><span class="sxs-lookup"><span data-stu-id="29b04-179">Once a device is onboarded, information about audited activities flows into Activity explorer even before you configure and deploy any DLP policies that have devices as a location.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="29b04-180">![eventi di prevenzione della perdita di dati degli endpoint in Esplora attività](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="29b04-180">![endpoint dlp events in activity explorer](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span></span>

<span data-ttu-id="29b04-181">Endpoint DLP raccoglie informazioni complete sulle attività controllate.</span><span class="sxs-lookup"><span data-stu-id="29b04-181">Endpoint DLP collects extensive information on audited activity.</span></span>

<span data-ttu-id="29b04-182">Ad esempio, se un file viene copiato in un supporto USB rimovibile, nei dettagli attività vengono visualizzati questi attributi:</span><span class="sxs-lookup"><span data-stu-id="29b04-182">For example, if a file is copied to removable USB media, you'd see these attributes in the activity details:</span></span>

- <span data-ttu-id="29b04-183">tipo di attività</span><span class="sxs-lookup"><span data-stu-id="29b04-183">activity type</span></span>
- <span data-ttu-id="29b04-184">IP client</span><span class="sxs-lookup"><span data-stu-id="29b04-184">client IP</span></span>
- <span data-ttu-id="29b04-185">percorso file di destinazione</span><span class="sxs-lookup"><span data-stu-id="29b04-185">target file path</span></span>
- <span data-ttu-id="29b04-186">timestamp dell'attività</span><span class="sxs-lookup"><span data-stu-id="29b04-186">happened timestamp</span></span>
- <span data-ttu-id="29b04-187">nome del file</span><span class="sxs-lookup"><span data-stu-id="29b04-187">file name</span></span>
- <span data-ttu-id="29b04-188">utente</span><span class="sxs-lookup"><span data-stu-id="29b04-188">user</span></span>
- <span data-ttu-id="29b04-189">estensione del file</span><span class="sxs-lookup"><span data-stu-id="29b04-189">file extension</span></span>
- <span data-ttu-id="29b04-190">dimensioni del file</span><span class="sxs-lookup"><span data-stu-id="29b04-190">file size</span></span>
- <span data-ttu-id="29b04-191">tipo di informazioni sensibili (se applicabile)</span><span class="sxs-lookup"><span data-stu-id="29b04-191">sensitive information type (if applicable)</span></span>
- <span data-ttu-id="29b04-192">valore SHA1</span><span class="sxs-lookup"><span data-stu-id="29b04-192">sha1 value</span></span>
- <span data-ttu-id="29b04-193">valore SHA256</span><span class="sxs-lookup"><span data-stu-id="29b04-193">sha256 value</span></span>
- <span data-ttu-id="29b04-194">nome file precedente</span><span class="sxs-lookup"><span data-stu-id="29b04-194">previous file name</span></span>
- <span data-ttu-id="29b04-195">posizione</span><span class="sxs-lookup"><span data-stu-id="29b04-195">location</span></span>
- <span data-ttu-id="29b04-196">padre</span><span class="sxs-lookup"><span data-stu-id="29b04-196">parent</span></span>
- <span data-ttu-id="29b04-197">percorso file</span><span class="sxs-lookup"><span data-stu-id="29b04-197">filepath</span></span>
- <span data-ttu-id="29b04-198">tipo di percorso di origine</span><span class="sxs-lookup"><span data-stu-id="29b04-198">source location type</span></span>
- <span data-ttu-id="29b04-199">piattaforma</span><span class="sxs-lookup"><span data-stu-id="29b04-199">platform</span></span>
- <span data-ttu-id="29b04-200">nome dispositivo</span><span class="sxs-lookup"><span data-stu-id="29b04-200">device name</span></span>
- <span data-ttu-id="29b04-201">tipo di percorso di destinazione</span><span class="sxs-lookup"><span data-stu-id="29b04-201">destination location type</span></span>
- <span data-ttu-id="29b04-202">applicazione che ha eseguito la copia</span><span class="sxs-lookup"><span data-stu-id="29b04-202">application that performed the copy</span></span>
- <span data-ttu-id="29b04-203">ID dispositivo di Microsoft Defender per endpoint (se applicabile)</span><span class="sxs-lookup"><span data-stu-id="29b04-203">Microsoft Defender for Endpoint device ID (if applicable)</span></span>
- <span data-ttu-id="29b04-204">produttore del dispositivo multimediale rimovibile</span><span class="sxs-lookup"><span data-stu-id="29b04-204">removable media device manufacturer</span></span>
- <span data-ttu-id="29b04-205">modello di dispositivo multimediale rimovibile</span><span class="sxs-lookup"><span data-stu-id="29b04-205">removable media device model</span></span>
- <span data-ttu-id="29b04-206">numero di serie del dispositivo multimediale rimovibile</span><span class="sxs-lookup"><span data-stu-id="29b04-206">removable media device serial number</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="29b04-207">![attributi dell'attività di copia su USB](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span><span class="sxs-lookup"><span data-stu-id="29b04-207">![copy to usb activity attributes](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span></span>

## <a name="next-steps"></a><span data-ttu-id="29b04-208">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="29b04-208">Next steps</span></span>

<span data-ttu-id="29b04-209">Dopo avere acquisito familiarità con Endpoint DLP, è possibile proseguire con questi argomenti:</span><span class="sxs-lookup"><span data-stu-id="29b04-209">Now that you've learned about Endpoint DLP, your next steps are:</span></span>

1) [<span data-ttu-id="29b04-210">Introduzione alla prevenzione della perdita di dati degli endpoint Microsoft</span><span class="sxs-lookup"><span data-stu-id="29b04-210">Getting started with Microsoft Endpoint data loss prevention </span></span>](endpoint-dlp-getting-started.md)
2) [<span data-ttu-id="29b04-211">Uso della prevenzione della perdita di dati degli endpoint Microsoft</span><span class="sxs-lookup"><span data-stu-id="29b04-211">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="29b04-212">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="29b04-212">See also</span></span>

- [<span data-ttu-id="29b04-213">Introduzione alla prevenzione della perdita di dati degli endpoint Microsoft</span><span class="sxs-lookup"><span data-stu-id="29b04-213">Getting started with Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="29b04-214">Uso della prevenzione della perdita di dati degli endpoint Microsoft</span><span class="sxs-lookup"><span data-stu-id="29b04-214">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="29b04-215">Panoramica sulla prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="29b04-215">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="29b04-216">Creare, testare e ottimizzare un criterio di prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="29b04-216">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="29b04-217">Introduzione a Esplora attività</span><span class="sxs-lookup"><span data-stu-id="29b04-217">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="29b04-218">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="29b04-218">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="29b04-219">Gestione dei rischi Insider</span><span class="sxs-lookup"><span data-stu-id="29b04-219">Insider Risk management</span></span>](insider-risk-management.md)
