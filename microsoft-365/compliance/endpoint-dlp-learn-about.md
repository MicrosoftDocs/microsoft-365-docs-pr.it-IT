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
- SPO_Content
search.appverid:
- MET150
description: 'La prevenzione della perdita di dati degli endpoint di Microsoft 365 estende il monitoraggio delle attività dei file e le azioni di protezione agli endpoint. I file vengono resi visibili nelle soluzioni di conformità di Microsoft 365 '
ms.openlocfilehash: 2423f45fefe994fbaf5704074c49ce862a59340e
ms.sourcegitcommit: df59c83174d845b8ddec48b9be2659fbfb58bb7f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/29/2020
ms.locfileid: "46517497"
---
# <a name="learn-about-microsoft-365-endpoint-data-loss-prevention-preview"></a><span data-ttu-id="4b1ff-104">Informazioni sulla prevenzione della perdita di dati degli endpoint di Microsoft 365 (anteprima)</span><span class="sxs-lookup"><span data-stu-id="4b1ff-104">Learn about Microsoft 365 Endpoint data loss prevention (preview)</span></span>

<span data-ttu-id="4b1ff-105">È possibile usare la prevenzione della perdita dei dati (DLP) di Microsoft 365 per monitorare le azioni intraprese sugli elementi che si considerano sensibili e per evitare la condivisione involontaria di tali elementi.</span><span class="sxs-lookup"><span data-stu-id="4b1ff-105">You can use Microsoft 365 data loss prevention (DLP) to monitor the actions that are being taken on items you've determined to be sensitive and to help prevent the unintentional sharing of those items.</span></span> <span data-ttu-id="4b1ff-106">Per altre informazioni, vedere [Panoramica sulla prevenzione della perdita dei dati](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="4b1ff-106">For more information on DLP, see [Overview of data loss prevention](data-loss-prevention-policies.md).</span></span>

<span data-ttu-id="4b1ff-107">La **prevenzione della perdita di dati degli endpoint** (Endpoint DLP) estende le funzionalità di monitoraggio e protezione delle attività di DLP agli elementi sensibili presenti nei dispositivi Windows 10.</span><span class="sxs-lookup"><span data-stu-id="4b1ff-107">**Endpoint data loss prevention** (Endpoint DLP) extends the activity monitoring and protection capabilities of DLP to sensitive items that are on Windows 10 devices.</span></span> <span data-ttu-id="4b1ff-108">Dopo aver eseguito l'onboarding dei dispositivi nelle soluzioni del Centro conformità Microsoft 365, le informazioni sulle azioni che gli utenti stanno eseguendo sugli elementi sensibili sono rese visibili in [Esplora attività](data-classification-activity-explorer.md) ed è possibile applicare azioni di protezione su tali elementi tramite [criteri DLP](create-test-tune-dlp-policy.md).</span><span class="sxs-lookup"><span data-stu-id="4b1ff-108">Once devices are onboarded into the Microsoft 365 compliance solutions, the information about what users are doing with sensitive items is made visible in [activity explorer](data-classification-activity-explorer.md) and you can enforce protective actions on those items via [DLP policies](create-test-tune-dlp-policy.md).</span></span>

## <a name="endpoint-activities-you-can-monitor-and-take-action-on"></a><span data-ttu-id="4b1ff-109">Attività endpoint che è possibile monitorare e su cui si può intervenire</span><span class="sxs-lookup"><span data-stu-id="4b1ff-109">Endpoint activities you can monitor and take action on</span></span>

<span data-ttu-id="4b1ff-110">Microsoft Endpoint DLP consente di controllare e gestire i tipi di attività seguenti, che gli utenti possono eseguire sugli elementi sensibili nei dispositivi che eseguono Windows 10.</span><span class="sxs-lookup"><span data-stu-id="4b1ff-110">Microsoft Endpoint DLP enables you to audit and manage the following types of activities users take on sensitive items on devices running Windows 10.</span></span> <span data-ttu-id="4b1ff-111">Questo include:</span><span class="sxs-lookup"><span data-stu-id="4b1ff-111">This includes:</span></span>


|<span data-ttu-id="4b1ff-112">attività sull'elemento</span><span class="sxs-lookup"><span data-stu-id="4b1ff-112">activity on item</span></span> |<span data-ttu-id="4b1ff-113">controllabile/limitabile</span><span class="sxs-lookup"><span data-stu-id="4b1ff-113">auditable/restrictable</span></span>  |
|---------|---------|
|<span data-ttu-id="4b1ff-114">creazione</span><span class="sxs-lookup"><span data-stu-id="4b1ff-114">created</span></span>    | <span data-ttu-id="4b1ff-115">controllabile</span><span class="sxs-lookup"><span data-stu-id="4b1ff-115">auditable</span></span>      |
|<span data-ttu-id="4b1ff-116">ridenominazione</span><span class="sxs-lookup"><span data-stu-id="4b1ff-116">renamed</span></span>    |  <span data-ttu-id="4b1ff-117">controllabile</span><span class="sxs-lookup"><span data-stu-id="4b1ff-117">auditable</span></span>       |
|<span data-ttu-id="4b1ff-118">copia o creazione su supporti rimovibili</span><span class="sxs-lookup"><span data-stu-id="4b1ff-118">copied to or created on removable media</span></span>     |     <span data-ttu-id="4b1ff-119">controllabile e limitabile</span><span class="sxs-lookup"><span data-stu-id="4b1ff-119">auditable and restrictable</span></span>|
|<span data-ttu-id="4b1ff-120">copia in condivisione di rete, ad esempio \\mio-server\fileshare</span><span class="sxs-lookup"><span data-stu-id="4b1ff-120">copied to network share, e.g. \\my-server\fileshare</span></span>   |     <span data-ttu-id="4b1ff-121">controllabile e limitabile</span><span class="sxs-lookup"><span data-stu-id="4b1ff-121">auditable and restrictable</span></span>    |
|<span data-ttu-id="4b1ff-122">stampa</span><span class="sxs-lookup"><span data-stu-id="4b1ff-122">printed</span></span> |    <span data-ttu-id="4b1ff-123">controllabile e limitabile</span><span class="sxs-lookup"><span data-stu-id="4b1ff-123">auditable and restrictable</span></span>       |
|<span data-ttu-id="4b1ff-124">copia nel cloud tramite Microsoft Edge Chromium</span><span class="sxs-lookup"><span data-stu-id="4b1ff-124">copied to cloud via Chromium Edge</span></span>    |   <span data-ttu-id="4b1ff-125">controllabile e limitabile</span><span class="sxs-lookup"><span data-stu-id="4b1ff-125">auditable and restrictable</span></span>        |
|<span data-ttu-id="4b1ff-126">accesso da app e browser non consentiti</span><span class="sxs-lookup"><span data-stu-id="4b1ff-126">accessed by unallowed apps and browsers</span></span>    |  <span data-ttu-id="4b1ff-127">controllabile e limitabile</span><span class="sxs-lookup"><span data-stu-id="4b1ff-127">auditable and restrictable</span></span>       |

## <a name="whats-different-in-endpoint-dlp"></a><span data-ttu-id="4b1ff-128">Cosa distingue Endpoint DLP</span><span class="sxs-lookup"><span data-stu-id="4b1ff-128">What's different in Endpoint DLP</span></span>

<span data-ttu-id="4b1ff-129">Ci sono alcuni concetti aggiuntivi che è necessario conoscere prima di approfondire l'utilizzo di Endpoint DLP.</span><span class="sxs-lookup"><span data-stu-id="4b1ff-129">There are a few extra concepts that you need to be aware of before you dig into Endpoint DLP.</span></span>

### <a name="enabling-device-management"></a><span data-ttu-id="4b1ff-130">Abilitare la gestione dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="4b1ff-130">Enabling Device management</span></span>

<span data-ttu-id="4b1ff-131">La gestione dei dispositivi è la funzionalità che consente la raccolta di dati di telemetria dai dispositivi e la introduce nelle soluzioni di conformità di Microsoft 365, come Endpoint DLP e [Gestione dei rischi Insider](insider-risk-management.md).</span><span class="sxs-lookup"><span data-stu-id="4b1ff-131">Device management is the functionality that enables the collection of telemetry from devices and brings it into Microsoft 365 compliance solutions like Endpoint DLP and [Insider Risk management](insider-risk-management.md).</span></span> <span data-ttu-id="4b1ff-132">È necessario eseguire l'onboarding di tutti i dispositivi che si vogliono usare come posizioni nei criteri DLP.</span><span class="sxs-lookup"><span data-stu-id="4b1ff-132">You'll need to onboard all devices you want to use as locations in DLP policies.</span></span>

![abilitare la gestione dei dispositivi](../media/endpoint-dlp-learn-about-1-enable-device-management.png)

<span data-ttu-id="4b1ff-134">Onboarding e offboarding vengono gestiti tramite script scaricati dal centro gestione dispositivi.</span><span class="sxs-lookup"><span data-stu-id="4b1ff-134">Onboarding and offboarding are handled via scripts you download from the Device management center.</span></span> <span data-ttu-id="4b1ff-135">Nel centro sono disponibili script personalizzati per ognuno di questi metodi di distribuzione:</span><span class="sxs-lookup"><span data-stu-id="4b1ff-135">The center has custom scripts for each of these deployment methods:</span></span>

- <span data-ttu-id="4b1ff-136">script locale (fino a 10 computer)</span><span class="sxs-lookup"><span data-stu-id="4b1ff-136">local script (up to 10 machines)</span></span>
- <span data-ttu-id="4b1ff-137">Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="4b1ff-137">Group policy</span></span>
- <span data-ttu-id="4b1ff-138">System Center Configuration Manager (versione 1610 o successiva)</span><span class="sxs-lookup"><span data-stu-id="4b1ff-138">System Center Configuration Manager (version 1610 or later)</span></span>
- <span data-ttu-id="4b1ff-139">Gestione dispositivi mobili/Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="4b1ff-139">Mobile Device Management/Microsoft Intune</span></span>
- <span data-ttu-id="4b1ff-140">Script di onboarding VDI per dispositivi non persistenti</span><span class="sxs-lookup"><span data-stu-id="4b1ff-140">VDI onboarding scripts for non-persistent machines</span></span>

![pagina di onboarding dispositivi](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)

 <span data-ttu-id="4b1ff-142">Seguire le procedure in [Introduzione a Microsoft 365 Endpoint DLP](endpoint-dlp-getting-started.md) per l'onboarding dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="4b1ff-142">Use the procedures in [Getting started with Microsoft 365 Endpoint DLP](endpoint-dlp-getting-started.md) to onboard devices.</span></span>

<span data-ttu-id="4b1ff-143">Se si è già eseguito l'onboarding di dispositivi tramite [Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP)](https://docs.microsoft.com/windows/security/threat-protection/), verranno visualizzati automaticamente nell'elenco di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="4b1ff-143">If you have onboarded devices through [Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP)](https://docs.microsoft.com/windows/security/threat-protection/), those devices will automatically show up in the list of devices.</span></span>

![elenco dispositivi gestiti](../media/endpoint-dlp-learn-about-2-device-list.png)

### <a name="viewing-endpoint-dlp-data"></a><span data-ttu-id="4b1ff-145">Visualizzazione dei dati di Endpoint DLP</span><span class="sxs-lookup"><span data-stu-id="4b1ff-145">Viewing Endpoint DLP data</span></span>

 <span data-ttu-id="4b1ff-146">Endpoint DLP monitora le attività in base al tipo MIME, in modo che le attività vengano acquisite anche se l'estensione del file viene cambiata.</span><span class="sxs-lookup"><span data-stu-id="4b1ff-146">Endpoint DLP monitors activity based om MIME type, so activities will be captured even if the file extension is changed.</span></span> <span data-ttu-id="4b1ff-147">Nell'anteprima pubblica viene controllato tutto:</span><span class="sxs-lookup"><span data-stu-id="4b1ff-147">At public preview it watches all:</span></span>

- <span data-ttu-id="4b1ff-148">File di Word</span><span class="sxs-lookup"><span data-stu-id="4b1ff-148">Word files</span></span>
- <span data-ttu-id="4b1ff-149">File di PowerPoint</span><span class="sxs-lookup"><span data-stu-id="4b1ff-149">PowerPoint files</span></span>
- <span data-ttu-id="4b1ff-150">File di Excel</span><span class="sxs-lookup"><span data-stu-id="4b1ff-150">Excel files</span></span>
- <span data-ttu-id="4b1ff-151">File PDF</span><span class="sxs-lookup"><span data-stu-id="4b1ff-151">PDF files</span></span>
- <span data-ttu-id="4b1ff-152">File CSV</span><span class="sxs-lookup"><span data-stu-id="4b1ff-152">.csv files</span></span>
- <span data-ttu-id="4b1ff-153">File TSV</span><span class="sxs-lookup"><span data-stu-id="4b1ff-153">.tsv files</span></span>
- <span data-ttu-id="4b1ff-154">File C</span><span class="sxs-lookup"><span data-stu-id="4b1ff-154">c files</span></span>
- <span data-ttu-id="4b1ff-155">File di classe</span><span class="sxs-lookup"><span data-stu-id="4b1ff-155">class files</span></span>
- <span data-ttu-id="4b1ff-156">File CPP</span><span class="sxs-lookup"><span data-stu-id="4b1ff-156">cpp files</span></span>
- <span data-ttu-id="4b1ff-157">File CS</span><span class="sxs-lookup"><span data-stu-id="4b1ff-157">cs files</span></span>
- <span data-ttu-id="4b1ff-158">File H</span><span class="sxs-lookup"><span data-stu-id="4b1ff-158">h files</span></span>
- <span data-ttu-id="4b1ff-159">File Java</span><span class="sxs-lookup"><span data-stu-id="4b1ff-159">java files</span></span>

> [!NOTE]
> <span data-ttu-id="4b1ff-160">I file TXT e di codice sorgente non vengono controllati per impostazione predefinita, DLP li valuta in base ai criteri applicati e le azioni utente vengono controllate o bloccate di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="4b1ff-160">.txt and source code files are not audited by default, DLP evaluates them against the applied policies and then user actions are audited or blocked accordingly.</span></span>

<span data-ttu-id="4b1ff-161">Dopo l'onboarding di un dispositivo, le informazioni sulle attività controllate fluiscono in Esplora attività anche prima che vengano configurati e distribuiti criteri di prevenzione della perdita dei dati che usano dispositivi come posizione.</span><span class="sxs-lookup"><span data-stu-id="4b1ff-161">Once a device is onboarded, information about audited activities flows into Activity explorer even before you configure and deploy any DLP policies that have devices as a location.</span></span>

![Eventi di Endpoint DLP in Esplora attività](../media/endpoint-dlp-learn-about-4-activity-explorer.png)

<span data-ttu-id="4b1ff-163">Endpoint DLP raccoglie informazioni complete sulle attività controllate.</span><span class="sxs-lookup"><span data-stu-id="4b1ff-163">Endpoint DLP collects extensive information on audited activity.</span></span>

<span data-ttu-id="4b1ff-164">Ad esempio, se un file viene copiato in un supporto USB rimovibile, nei dettagli attività vengono visualizzati questi attributi:</span><span class="sxs-lookup"><span data-stu-id="4b1ff-164">For example, if a file is copied to removable USB media, you'd see these attributes in the activity details:</span></span>

- <span data-ttu-id="4b1ff-165">tipo di attività</span><span class="sxs-lookup"><span data-stu-id="4b1ff-165">activity type</span></span>
- <span data-ttu-id="4b1ff-166">IP client</span><span class="sxs-lookup"><span data-stu-id="4b1ff-166">client IP</span></span>
- <span data-ttu-id="4b1ff-167">percorso file di destinazione</span><span class="sxs-lookup"><span data-stu-id="4b1ff-167">target file path</span></span>
- <span data-ttu-id="4b1ff-168">timestamp dell'attività</span><span class="sxs-lookup"><span data-stu-id="4b1ff-168">happened timestamp</span></span>
- <span data-ttu-id="4b1ff-169">nome del file</span><span class="sxs-lookup"><span data-stu-id="4b1ff-169">file name</span></span>
- <span data-ttu-id="4b1ff-170">utente</span><span class="sxs-lookup"><span data-stu-id="4b1ff-170">user</span></span>
- <span data-ttu-id="4b1ff-171">estensione del file</span><span class="sxs-lookup"><span data-stu-id="4b1ff-171">file extension</span></span>
- <span data-ttu-id="4b1ff-172">dimensioni del file</span><span class="sxs-lookup"><span data-stu-id="4b1ff-172">file size</span></span>
- <span data-ttu-id="4b1ff-173">tipo di informazioni sensibili (se applicabile)</span><span class="sxs-lookup"><span data-stu-id="4b1ff-173">sensitive information type (if applicable)</span></span>
- <span data-ttu-id="4b1ff-174">valore SHA1</span><span class="sxs-lookup"><span data-stu-id="4b1ff-174">sha1 value</span></span>
- <span data-ttu-id="4b1ff-175">valore SHA256</span><span class="sxs-lookup"><span data-stu-id="4b1ff-175">sha256 value</span></span>
- <span data-ttu-id="4b1ff-176">nome file precedente</span><span class="sxs-lookup"><span data-stu-id="4b1ff-176">previous file name</span></span>
- <span data-ttu-id="4b1ff-177">posizione</span><span class="sxs-lookup"><span data-stu-id="4b1ff-177">location</span></span>
- <span data-ttu-id="4b1ff-178">padre</span><span class="sxs-lookup"><span data-stu-id="4b1ff-178">parent</span></span>
- <span data-ttu-id="4b1ff-179">percorso file</span><span class="sxs-lookup"><span data-stu-id="4b1ff-179">filepath</span></span>
- <span data-ttu-id="4b1ff-180">tipo di percorso di origine</span><span class="sxs-lookup"><span data-stu-id="4b1ff-180">source location type</span></span>
- <span data-ttu-id="4b1ff-181">piattaforma</span><span class="sxs-lookup"><span data-stu-id="4b1ff-181">platform</span></span>
- <span data-ttu-id="4b1ff-182">nome dispositivo</span><span class="sxs-lookup"><span data-stu-id="4b1ff-182">device name</span></span>
- <span data-ttu-id="4b1ff-183">tipo di percorso di destinazione</span><span class="sxs-lookup"><span data-stu-id="4b1ff-183">destination location type</span></span>
- <span data-ttu-id="4b1ff-184">applicazione che ha eseguito la copia</span><span class="sxs-lookup"><span data-stu-id="4b1ff-184">application that performed the copy</span></span>
- <span data-ttu-id="4b1ff-185">ID dispositivo MDATP (se applicabile)</span><span class="sxs-lookup"><span data-stu-id="4b1ff-185">MDATP device ID (if applicable)</span></span>
- <span data-ttu-id="4b1ff-186">produttore del dispositivo multimediale rimovibile</span><span class="sxs-lookup"><span data-stu-id="4b1ff-186">removable media device manufacturer</span></span>
- <span data-ttu-id="4b1ff-187">modello di dispositivo multimediale rimovibile</span><span class="sxs-lookup"><span data-stu-id="4b1ff-187">removable media device model</span></span>
- <span data-ttu-id="4b1ff-188">numero di serie del dispositivo multimediale rimovibile</span><span class="sxs-lookup"><span data-stu-id="4b1ff-188">removable media device serial number</span></span>

![attributi dell'attività di copia su USB](../media/endpoint-dlp-learn-about-5-activity-attributes.png)

## <a name="next-steps"></a><span data-ttu-id="4b1ff-190">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="4b1ff-190">Next steps</span></span>

<span data-ttu-id="4b1ff-191">Dopo avere acquisito familiarità con Endpoint DLP, è possibile proseguire con questi argomenti:</span><span class="sxs-lookup"><span data-stu-id="4b1ff-191">Now that you've learned about Endpoint DLP, your next steps are:</span></span>

1) [<span data-ttu-id="4b1ff-192">Introduzione alla prevenzione della perdita di dati degli endpoint Microsoft (anteprima)</span><span class="sxs-lookup"><span data-stu-id="4b1ff-192">Getting started with Microsoft Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-getting-started.md)
2) [<span data-ttu-id="4b1ff-193">Uso della prevenzione della perdita di dati degli endpoint Microsoft (anteprima)</span><span class="sxs-lookup"><span data-stu-id="4b1ff-193">Using Microsoft Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="4b1ff-194">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4b1ff-194">See also</span></span>

- [<span data-ttu-id="4b1ff-195">Introduzione alla prevenzione della perdita di dati degli endpoint Microsoft (anteprima)</span><span class="sxs-lookup"><span data-stu-id="4b1ff-195">Getting started with Microsoft Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="4b1ff-196">Uso della prevenzione della perdita di dati degli endpoint Microsoft (anteprima)</span><span class="sxs-lookup"><span data-stu-id="4b1ff-196">Using Microsoft Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="4b1ff-197">Panoramica sulla prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="4b1ff-197">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="4b1ff-198">Creare, testare e ottimizzare un criterio di prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="4b1ff-198">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="4b1ff-199">Introduzione a Esplora attività</span><span class="sxs-lookup"><span data-stu-id="4b1ff-199">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="4b1ff-200">Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP)</span><span class="sxs-lookup"><span data-stu-id="4b1ff-200">Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP)</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="4b1ff-201">Gestione dei rischi Insider</span><span class="sxs-lookup"><span data-stu-id="4b1ff-201">Insider Risk management</span></span>](insider-risk-management.md)