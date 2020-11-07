---
title: Informazioni sulla prevenzione della perdita di dati degli endpoint di Microsoft 365 (anteprima)
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
description: 'La prevenzione della perdita di dati degli endpoint di Microsoft 365 estende il monitoraggio delle attività dei file e le azioni di protezione agli endpoint. I file vengono resi visibili nelle soluzioni di conformità di Microsoft 365 '
ms.openlocfilehash: 3dedf8f3134dbdd00c45e6b0aed741a3b3173984
ms.sourcegitcommit: 24826e1b61e7aace12fc9e8ae84ae3e760658b50
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/06/2020
ms.locfileid: "48931970"
---
# <a name="learn-about-microsoft-365-endpoint-data-loss-prevention-preview"></a><span data-ttu-id="0b9af-104">Informazioni sulla prevenzione della perdita di dati degli endpoint di Microsoft 365 (anteprima)</span><span class="sxs-lookup"><span data-stu-id="0b9af-104">Learn about Microsoft 365 Endpoint data loss prevention (preview)</span></span>

<span data-ttu-id="0b9af-105">È possibile usare la prevenzione della perdita dei dati (DLP) di Microsoft 365 per monitorare le azioni intraprese sugli elementi che si considerano sensibili e per evitare la condivisione involontaria di tali elementi.</span><span class="sxs-lookup"><span data-stu-id="0b9af-105">You can use Microsoft 365 data loss prevention (DLP) to monitor the actions that are being taken on items you've determined to be sensitive and to help prevent the unintentional sharing of those items.</span></span> <span data-ttu-id="0b9af-106">Per altre informazioni, vedere [Panoramica sulla prevenzione della perdita dei dati](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="0b9af-106">For more information on DLP, see [Overview of data loss prevention](data-loss-prevention-policies.md).</span></span>

<span data-ttu-id="0b9af-107">La **prevenzione della perdita di dati degli endpoint** (Endpoint DLP) estende le funzionalità di monitoraggio e protezione delle attività di DLP agli elementi sensibili presenti nei dispositivi Windows 10.</span><span class="sxs-lookup"><span data-stu-id="0b9af-107">**Endpoint data loss prevention** (Endpoint DLP) extends the activity monitoring and protection capabilities of DLP to sensitive items that are on Windows 10 devices.</span></span> <span data-ttu-id="0b9af-108">Dopo aver eseguito l'onboarding dei dispositivi nelle soluzioni del Centro conformità Microsoft 365, le informazioni sulle azioni che gli utenti stanno eseguendo sugli elementi sensibili sono rese visibili in [Esplora attività](data-classification-activity-explorer.md) ed è possibile applicare azioni di protezione su tali elementi tramite [criteri DLP](create-test-tune-dlp-policy.md).</span><span class="sxs-lookup"><span data-stu-id="0b9af-108">Once devices are onboarded into the Microsoft 365 compliance solutions, the information about what users are doing with sensitive items is made visible in [activity explorer](data-classification-activity-explorer.md) and you can enforce protective actions on those items via [DLP policies](create-test-tune-dlp-policy.md).</span></span>

## <a name="endpoint-activities-you-can-monitor-and-take-action-on"></a><span data-ttu-id="0b9af-109">Attività endpoint che è possibile monitorare e su cui si può intervenire</span><span class="sxs-lookup"><span data-stu-id="0b9af-109">Endpoint activities you can monitor and take action on</span></span>

<span data-ttu-id="0b9af-110">Microsoft Endpoint DLP consente di controllare e gestire i tipi di attività seguenti, che gli utenti possono eseguire sugli elementi sensibili nei dispositivi che eseguono Windows 10.</span><span class="sxs-lookup"><span data-stu-id="0b9af-110">Microsoft Endpoint DLP enables you to audit and manage the following types of activities users take on sensitive items on devices running Windows 10.</span></span> <span data-ttu-id="0b9af-111">Questo include:</span><span class="sxs-lookup"><span data-stu-id="0b9af-111">This includes:</span></span>


|<span data-ttu-id="0b9af-112">attività sull'elemento</span><span class="sxs-lookup"><span data-stu-id="0b9af-112">activity on item</span></span> |<span data-ttu-id="0b9af-113">controllabile/limitabile</span><span class="sxs-lookup"><span data-stu-id="0b9af-113">auditable/restrictable</span></span>  |
|---------|---------|
|<span data-ttu-id="0b9af-114">creazione</span><span class="sxs-lookup"><span data-stu-id="0b9af-114">created</span></span>    | <span data-ttu-id="0b9af-115">controllabile</span><span class="sxs-lookup"><span data-stu-id="0b9af-115">auditable</span></span>      |
|<span data-ttu-id="0b9af-116">ridenominazione</span><span class="sxs-lookup"><span data-stu-id="0b9af-116">renamed</span></span>    |  <span data-ttu-id="0b9af-117">controllabile</span><span class="sxs-lookup"><span data-stu-id="0b9af-117">auditable</span></span>       |
|<span data-ttu-id="0b9af-118">copia o creazione su supporti rimovibili</span><span class="sxs-lookup"><span data-stu-id="0b9af-118">copied to or created on removable media</span></span>     |     <span data-ttu-id="0b9af-119">controllabile e limitabile</span><span class="sxs-lookup"><span data-stu-id="0b9af-119">auditable and restrictable</span></span>|
|<span data-ttu-id="0b9af-120">copia in condivisione di rete, ad esempio \\mio-server\fileshare</span><span class="sxs-lookup"><span data-stu-id="0b9af-120">copied to network share, e.g. \\my-server\fileshare</span></span>   |     <span data-ttu-id="0b9af-121">controllabile e limitabile</span><span class="sxs-lookup"><span data-stu-id="0b9af-121">auditable and restrictable</span></span>    |
|<span data-ttu-id="0b9af-122">stampa</span><span class="sxs-lookup"><span data-stu-id="0b9af-122">printed</span></span> |    <span data-ttu-id="0b9af-123">controllabile e limitabile</span><span class="sxs-lookup"><span data-stu-id="0b9af-123">auditable and restrictable</span></span>       |
|<span data-ttu-id="0b9af-124">copia nel cloud tramite Microsoft Edge Chromium</span><span class="sxs-lookup"><span data-stu-id="0b9af-124">copied to cloud via Chromium Edge</span></span>    |   <span data-ttu-id="0b9af-125">controllabile e limitabile</span><span class="sxs-lookup"><span data-stu-id="0b9af-125">auditable and restrictable</span></span>        |
|<span data-ttu-id="0b9af-126">accesso da app e browser non consentiti</span><span class="sxs-lookup"><span data-stu-id="0b9af-126">accessed by unallowed apps and browsers</span></span>    |  <span data-ttu-id="0b9af-127">controllabile e limitabile</span><span class="sxs-lookup"><span data-stu-id="0b9af-127">auditable and restrictable</span></span>       |

## <a name="whats-different-in-endpoint-dlp"></a><span data-ttu-id="0b9af-128">Cosa distingue Endpoint DLP</span><span class="sxs-lookup"><span data-stu-id="0b9af-128">What's different in Endpoint DLP</span></span>

<span data-ttu-id="0b9af-129">Ci sono alcuni concetti aggiuntivi che è necessario conoscere prima di approfondire l'utilizzo di Endpoint DLP.</span><span class="sxs-lookup"><span data-stu-id="0b9af-129">There are a few extra concepts that you need to be aware of before you dig into Endpoint DLP.</span></span>

### <a name="enabling-device-management"></a><span data-ttu-id="0b9af-130">Abilitare la gestione dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="0b9af-130">Enabling Device management</span></span>

<span data-ttu-id="0b9af-131">La gestione dei dispositivi è la funzionalità che consente la raccolta di dati di telemetria dai dispositivi e la introduce nelle soluzioni di conformità di Microsoft 365, come Endpoint DLP e [Gestione dei rischi Insider](insider-risk-management.md).</span><span class="sxs-lookup"><span data-stu-id="0b9af-131">Device management is the functionality that enables the collection of telemetry from devices and brings it into Microsoft 365 compliance solutions like Endpoint DLP and [Insider Risk management](insider-risk-management.md).</span></span> <span data-ttu-id="0b9af-132">È necessario eseguire l'onboarding di tutti i dispositivi che si vogliono usare come posizioni nei criteri DLP.</span><span class="sxs-lookup"><span data-stu-id="0b9af-132">You'll need to onboard all devices you want to use as locations in DLP policies.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0b9af-133">![abilitare la gestione dei dispositivi](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="0b9af-133">![enable device management](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span></span>

<span data-ttu-id="0b9af-134">Onboarding e offboarding vengono gestiti tramite script scaricati dal centro gestione dispositivi.</span><span class="sxs-lookup"><span data-stu-id="0b9af-134">Onboarding and offboarding are handled via scripts you download from the Device management center.</span></span> <span data-ttu-id="0b9af-135">Nel centro sono disponibili script personalizzati per ognuno di questi metodi di distribuzione:</span><span class="sxs-lookup"><span data-stu-id="0b9af-135">The center has custom scripts for each of these deployment methods:</span></span>

- <span data-ttu-id="0b9af-136">script locale (fino a 10 computer)</span><span class="sxs-lookup"><span data-stu-id="0b9af-136">local script (up to 10 machines)</span></span>
- <span data-ttu-id="0b9af-137">Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="0b9af-137">Group policy</span></span>
- <span data-ttu-id="0b9af-138">System Center Configuration Manager (versione 1610 o successiva)</span><span class="sxs-lookup"><span data-stu-id="0b9af-138">System Center Configuration Manager (version 1610 or later)</span></span>
- <span data-ttu-id="0b9af-139">Gestione dispositivi mobili/Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="0b9af-139">Mobile Device Management/Microsoft Intune</span></span>
- <span data-ttu-id="0b9af-140">Script di onboarding VDI per dispositivi non persistenti</span><span class="sxs-lookup"><span data-stu-id="0b9af-140">VDI onboarding scripts for non-persistent machines</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0b9af-141">![pagina di onboarding dispositivi](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span><span class="sxs-lookup"><span data-stu-id="0b9af-141">![device onboarding page](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span></span>

 <span data-ttu-id="0b9af-142">Seguire le procedure in [Informazioni sulla prevenzione della perdita di dati degli endpoint di Microsoft 365](endpoint-dlp-getting-started.md) per l'onboarding dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="0b9af-142">Use the procedures in [Getting started with Microsoft 365 Endpoint DLP](endpoint-dlp-getting-started.md) to onboard devices.</span></span>

<span data-ttu-id="0b9af-143">Se è stato eseguito l'onboarding di dispositivi tramite [Microsoft Defender per endpoint](https://docs.microsoft.com/windows/security/threat-protection/), questi dispositivi verranno visualizzati automaticamente nell'elenco dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="0b9af-143">If you have onboarded devices through [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/), those devices will automatically show up in the list of devices.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0b9af-144">![elenco dispositivi gestiti](../media/endpoint-dlp-learn-about-2-device-list.png)</span><span class="sxs-lookup"><span data-stu-id="0b9af-144">![managed devices list](../media/endpoint-dlp-learn-about-2-device-list.png)</span></span>

### <a name="viewing-endpoint-dlp-data"></a><span data-ttu-id="0b9af-145">Visualizzazione dei dati di prevenzione della perdita di dati degli endpoint</span><span class="sxs-lookup"><span data-stu-id="0b9af-145">Viewing Endpoint DLP data</span></span>

 <span data-ttu-id="0b9af-146">La prevenzione della perdita di dati degli endpoint monitora le attività in base al tipo MIME, in modo che le attività vengano acquisite anche se l'estensione del file viene cambiata.</span><span class="sxs-lookup"><span data-stu-id="0b9af-146">Endpoint DLP monitors activity-based on MIME type, so activities will be captured even if the file extension is changed.</span></span> <span data-ttu-id="0b9af-147">Nell'anteprima pubblica viene controllato tutto:</span><span class="sxs-lookup"><span data-stu-id="0b9af-147">At public preview it watches all:</span></span>

- <span data-ttu-id="0b9af-148">File di Word</span><span class="sxs-lookup"><span data-stu-id="0b9af-148">Word files</span></span>
- <span data-ttu-id="0b9af-149">File di PowerPoint</span><span class="sxs-lookup"><span data-stu-id="0b9af-149">PowerPoint files</span></span>
- <span data-ttu-id="0b9af-150">File di Excel</span><span class="sxs-lookup"><span data-stu-id="0b9af-150">Excel files</span></span>
- <span data-ttu-id="0b9af-151">File PDF</span><span class="sxs-lookup"><span data-stu-id="0b9af-151">PDF files</span></span>
- <span data-ttu-id="0b9af-152">File CSV</span><span class="sxs-lookup"><span data-stu-id="0b9af-152">.csv files</span></span>
- <span data-ttu-id="0b9af-153">File TSV</span><span class="sxs-lookup"><span data-stu-id="0b9af-153">.tsv files</span></span>
- <span data-ttu-id="0b9af-154">File TXT</span><span class="sxs-lookup"><span data-stu-id="0b9af-154">.txt files</span></span>
- <span data-ttu-id="0b9af-155">File RTF</span><span class="sxs-lookup"><span data-stu-id="0b9af-155">.rtf files</span></span>
- <span data-ttu-id="0b9af-156">File C</span><span class="sxs-lookup"><span data-stu-id="0b9af-156">.c files</span></span>
- <span data-ttu-id="0b9af-157">File CLASS</span><span class="sxs-lookup"><span data-stu-id="0b9af-157">.class files</span></span>
- <span data-ttu-id="0b9af-158">File CPP</span><span class="sxs-lookup"><span data-stu-id="0b9af-158">.cpp files</span></span>
- <span data-ttu-id="0b9af-159">File CS</span><span class="sxs-lookup"><span data-stu-id="0b9af-159">.cs files</span></span>
- <span data-ttu-id="0b9af-160">File H</span><span class="sxs-lookup"><span data-stu-id="0b9af-160">.h files</span></span>
- <span data-ttu-id="0b9af-161">File Java</span><span class="sxs-lookup"><span data-stu-id="0b9af-161">.java files</span></span>

> [!NOTE]
> <span data-ttu-id="0b9af-162">La prevenzione della perdita di dati degli endpoint valuta i file di tutti i tipi precedenti rispetto ai criteri DLP e applica le azioni di protezione di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="0b9af-162">Endpoint DLP evaluates files of all the above types against the DLP policy and applies protection actions accordingly.</span></span> <span data-ttu-id="0b9af-163">Tutti i file che corrispondono a un criterio DLP vengono controllati per tutte le azioni supportate, anche se non vengono bloccati.</span><span class="sxs-lookup"><span data-stu-id="0b9af-163">All files that match a DLP policy are audited for all supported actions, even if they aren't blocked.</span></span> <span data-ttu-id="0b9af-164">Inoltre, le attività sui file eseguite in qualsiasi file di Word, PowerPoint, Excel, PDF e CSV vengono controllate per impostazione predefinita, indipendentemente dal fatto che esista un criterio DLP o che corrisponda a questi file.</span><span class="sxs-lookup"><span data-stu-id="0b9af-164">In addition, file activity performed on any Word, PowerPoint, Excel, PDF, and .csv file is audited by default, independent of whether a DLP policy exists or matches these files.</span></span>

<span data-ttu-id="0b9af-165">Dopo l'onboarding di un dispositivo, le informazioni sulle attività controllate fluiscono in Esplora attività anche prima che vengano configurati e distribuiti criteri DLP che usano dispositivi come posizione.</span><span class="sxs-lookup"><span data-stu-id="0b9af-165">Once a device is onboarded, information about audited activities flows into Activity explorer even before you configure and deploy any DLP policies that have devices as a location.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0b9af-166">![eventi di prevenzione della perdita di dati degli endpoint in Esplora attività](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="0b9af-166">![endpoint dlp events in activity explorer](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span></span>

<span data-ttu-id="0b9af-167">La prevenzione della perdita di dati degli endpoint raccoglie informazioni complete sulle attività controllate.</span><span class="sxs-lookup"><span data-stu-id="0b9af-167">Endpoint DLP collects extensive information on audited activity.</span></span>

<span data-ttu-id="0b9af-168">Ad esempio, se un file viene copiato in un supporto USB rimovibile, nei dettagli attività vengono visualizzati questi attributi:</span><span class="sxs-lookup"><span data-stu-id="0b9af-168">For example, if a file is copied to removable USB media, you'd see these attributes in the activity details:</span></span>

- <span data-ttu-id="0b9af-169">tipo di attività</span><span class="sxs-lookup"><span data-stu-id="0b9af-169">activity type</span></span>
- <span data-ttu-id="0b9af-170">IP client</span><span class="sxs-lookup"><span data-stu-id="0b9af-170">client IP</span></span>
- <span data-ttu-id="0b9af-171">percorso file di destinazione</span><span class="sxs-lookup"><span data-stu-id="0b9af-171">target file path</span></span>
- <span data-ttu-id="0b9af-172">timestamp dell'attività</span><span class="sxs-lookup"><span data-stu-id="0b9af-172">happened timestamp</span></span>
- <span data-ttu-id="0b9af-173">nome del file</span><span class="sxs-lookup"><span data-stu-id="0b9af-173">file name</span></span>
- <span data-ttu-id="0b9af-174">utente</span><span class="sxs-lookup"><span data-stu-id="0b9af-174">user</span></span>
- <span data-ttu-id="0b9af-175">estensione del file</span><span class="sxs-lookup"><span data-stu-id="0b9af-175">file extension</span></span>
- <span data-ttu-id="0b9af-176">dimensioni del file</span><span class="sxs-lookup"><span data-stu-id="0b9af-176">file size</span></span>
- <span data-ttu-id="0b9af-177">tipo di informazioni sensibili (se applicabile)</span><span class="sxs-lookup"><span data-stu-id="0b9af-177">sensitive information type (if applicable)</span></span>
- <span data-ttu-id="0b9af-178">valore SHA1</span><span class="sxs-lookup"><span data-stu-id="0b9af-178">sha1 value</span></span>
- <span data-ttu-id="0b9af-179">valore SHA256</span><span class="sxs-lookup"><span data-stu-id="0b9af-179">sha256 value</span></span>
- <span data-ttu-id="0b9af-180">nome file precedente</span><span class="sxs-lookup"><span data-stu-id="0b9af-180">previous file name</span></span>
- <span data-ttu-id="0b9af-181">posizione</span><span class="sxs-lookup"><span data-stu-id="0b9af-181">location</span></span>
- <span data-ttu-id="0b9af-182">padre</span><span class="sxs-lookup"><span data-stu-id="0b9af-182">parent</span></span>
- <span data-ttu-id="0b9af-183">percorso file</span><span class="sxs-lookup"><span data-stu-id="0b9af-183">filepath</span></span>
- <span data-ttu-id="0b9af-184">tipo di percorso di origine</span><span class="sxs-lookup"><span data-stu-id="0b9af-184">source location type</span></span>
- <span data-ttu-id="0b9af-185">piattaforma</span><span class="sxs-lookup"><span data-stu-id="0b9af-185">platform</span></span>
- <span data-ttu-id="0b9af-186">nome dispositivo</span><span class="sxs-lookup"><span data-stu-id="0b9af-186">device name</span></span>
- <span data-ttu-id="0b9af-187">tipo di percorso di destinazione</span><span class="sxs-lookup"><span data-stu-id="0b9af-187">destination location type</span></span>
- <span data-ttu-id="0b9af-188">applicazione che ha eseguito la copia</span><span class="sxs-lookup"><span data-stu-id="0b9af-188">application that performed the copy</span></span>
- <span data-ttu-id="0b9af-189">ID dispositivo di Microsoft Defender per endpoint (se applicabile)</span><span class="sxs-lookup"><span data-stu-id="0b9af-189">Microsoft Defender for Endpoint device ID (if applicable)</span></span>
- <span data-ttu-id="0b9af-190">produttore del dispositivo multimediale rimovibile</span><span class="sxs-lookup"><span data-stu-id="0b9af-190">removable media device manufacturer</span></span>
- <span data-ttu-id="0b9af-191">modello di dispositivo multimediale rimovibile</span><span class="sxs-lookup"><span data-stu-id="0b9af-191">removable media device model</span></span>
- <span data-ttu-id="0b9af-192">numero di serie del dispositivo multimediale rimovibile</span><span class="sxs-lookup"><span data-stu-id="0b9af-192">removable media device serial number</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0b9af-193">![attributi dell'attività di copia su USB](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span><span class="sxs-lookup"><span data-stu-id="0b9af-193">![copy to usb activity attributes](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span></span>

## <a name="next-steps"></a><span data-ttu-id="0b9af-194">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="0b9af-194">Next steps</span></span>

<span data-ttu-id="0b9af-195">Dopo avere acquisito familiarità con Endpoint DLP, è possibile proseguire con questi argomenti:</span><span class="sxs-lookup"><span data-stu-id="0b9af-195">Now that you've learned about Endpoint DLP, your next steps are:</span></span>

1) [<span data-ttu-id="0b9af-196">Introduzione alla prevenzione della perdita di dati degli endpoint Microsoft (anteprima)</span><span class="sxs-lookup"><span data-stu-id="0b9af-196">Getting started with Microsoft Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-getting-started.md)
2) [<span data-ttu-id="0b9af-197">Uso della prevenzione della perdita di dati degli endpoint Microsoft (anteprima)</span><span class="sxs-lookup"><span data-stu-id="0b9af-197">Using Microsoft Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="0b9af-198">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0b9af-198">See also</span></span>

- [<span data-ttu-id="0b9af-199">Introduzione alla prevenzione della perdita di dati degli endpoint Microsoft (anteprima)</span><span class="sxs-lookup"><span data-stu-id="0b9af-199">Getting started with Microsoft Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="0b9af-200">Uso della prevenzione della perdita di dati degli endpoint Microsoft (anteprima)</span><span class="sxs-lookup"><span data-stu-id="0b9af-200">Using Microsoft Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="0b9af-201">Panoramica sulla prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="0b9af-201">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="0b9af-202">Creare, testare e ottimizzare un criterio di prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="0b9af-202">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="0b9af-203">Introduzione a Esplora attività</span><span class="sxs-lookup"><span data-stu-id="0b9af-203">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="0b9af-204">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="0b9af-204">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="0b9af-205">Gestione dei rischi Insider</span><span class="sxs-lookup"><span data-stu-id="0b9af-205">Insider Risk management</span></span>](insider-risk-management.md)
