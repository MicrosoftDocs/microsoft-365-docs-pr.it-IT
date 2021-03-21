---
title: Come viene identificato il contenuto per i consigli sulla governance dei dati
f1.keywords:
- NOCSH
ms.author: brendonb
author: cabailey
manager: laurawi
ms.date: 1/15/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
ms.collection:
- SPO_Content
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ROBOTS: NOINDEX, NOFOLLOW
description: Il Centro sicurezza Microsoft 365 e il Centro sicurezza e conformità di Microsoft 365 fornisce consigli per la governance dei dati in base alla configurazione corrente dell'organizzazione e consente di impostare le opzioni necessarie con pochi clic. Alcuni di questi consigli rilevano specifici contenuti nell'organizzazione e propongono le azioni consigliate per gestirli. Ad esempio, un consiglio potrebbe rilevare elementi che includono contenuti di importanza strategica, come informazioni sul privilegio avvocato-cliente o su un accordo di riservatezza, e quindi consentire l'applicazione automatica di un'etichetta di conservazione a tali elementi per assicurare che vengano opportunamente classificati e conservati. Questo argomento fornisce un elenco dei consigli sulla governance dei dati che possono essere visualizzati e descrive il contenuto che viene rilevato per attivare ciascuno di essi.
ms.openlocfilehash: 9a022369fb783a498971c91664fa6532472d8589
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922610"
---
# <a name="how-content-is-identified-for-data-governance-recommendations"></a><span data-ttu-id="46d53-106">Come viene identificato il contenuto per i consigli sulla governance dei dati</span><span class="sxs-lookup"><span data-stu-id="46d53-106">How content is identified for data-governance recommendations</span></span>

<span data-ttu-id="46d53-p102">Il Centro sicurezza Microsoft 365 e il Centro sicurezza e conformità di Microsoft 365 fornisce consigli per la governance dei dati in base alla configurazione corrente dell'organizzazione e consente di impostare le opzioni necessarie con pochi clic. Alcuni di questi consigli rilevano specifici contenuti nell'organizzazione e propongono le azioni consigliate per gestirli. Ad esempio, un consiglio potrebbe rilevare elementi che includono contenuti di importanza strategica, come informazioni sul privilegio avvocato-cliente o su un accordo di riservatezza, e quindi consentire l'applicazione automatica di un'etichetta di conservazione a tali elementi per assicurare che vengano opportunamente classificati e conservati.</span><span class="sxs-lookup"><span data-stu-id="46d53-p102">The Microsoft 365 security center and Microsoft 365 compliance center provide recommendations for data governance based on your org's current setup and lets you set things up in a couple clicks. Some of these recommendations detect specific content in your organization and then provide recommended steps for managing that content. For example, a recommendation might detect items that contain business-critical content (such as attorney-client privilege or NDA info), and then let you automatically apply a retention label to those items to ensure that they're classified and retained as needed.</span></span>

<span data-ttu-id="46d53-110">Questo argomento fornisce un elenco dei consigli sulla governance dei dati che possono essere visualizzati e descrive il contenuto che viene rilevato per attivare ciascuno di essi.</span><span class="sxs-lookup"><span data-stu-id="46d53-110">This topic lists the data-governance recommendations you might see and describes what content is detected to trigger each one.</span></span>

## <a name="clean-up-voicemail"></a><span data-ttu-id="46d53-111">Pulisci la segreteria telefonica</span><span class="sxs-lookup"><span data-stu-id="46d53-111">Clean up voicemail</span></span>

<span data-ttu-id="46d53-p103">Questo consiglio viene visualizzato quando nelle cassette postali degli utenti vengono rilevati messaggi di posta elettronica identificati come messaggi di tipo "vocale". Per saperne di più, vedere l'argomento relativo alle [proprietà dei messaggi in Exchange](/exchange/policy-and-compliance/ediscovery/message-properties-and-search-operators?view=exchserver-2019#searchable-properties-in-exchange).</span><span class="sxs-lookup"><span data-stu-id="46d53-p103">This recommendation appears when email messages identified as the message type 'voicemail' are detected in users' mailboxes. Learn more about [message properties in Exchange](/exchange/policy-and-compliance/ediscovery/message-properties-and-search-operators?view=exchserver-2019#searchable-properties-in-exchange).</span></span>

## <a name="label-attorney-client-privilege-content"></a><span data-ttu-id="46d53-114">Applica etichetta ai contenuti coperti da privilegio avvocato-cliente</span><span class="sxs-lookup"><span data-stu-id="46d53-114">Label attorney-client privilege content</span></span> 

<span data-ttu-id="46d53-115">Questo consiglio viene visualizzato quando è soddisfatto uno dei criteri seguenti.</span><span class="sxs-lookup"><span data-stu-id="46d53-115">This recommendation appears when either of the following criteria are met.</span></span>

- <span data-ttu-id="46d53-116">Nel corpo del messaggio di posta elettronica viene rilevata una qualsiasi combinazione di queste parole chiave:</span><span class="sxs-lookup"><span data-stu-id="46d53-116">Any of combination of these keywords is detected in the body of an email message:</span></span>
    - <span data-ttu-id="46d53-117">PAC</span><span class="sxs-lookup"><span data-stu-id="46d53-117">ACP</span></span>
    - <span data-ttu-id="46d53-118">Privilegio avvocato cliente</span><span class="sxs-lookup"><span data-stu-id="46d53-118">Attorney Client Privilege</span></span>
    - <span data-ttu-id="46d53-119">Privilegio avvocato-cliente</span><span class="sxs-lookup"><span data-stu-id="46d53-119">Attorney-Client Privilege</span></span>
    - <span data-ttu-id="46d53-120">Coperto dal privilegio avvocato-cliente</span><span class="sxs-lookup"><span data-stu-id="46d53-120">Attorney-Client Privileged</span></span>

- <span data-ttu-id="46d53-121">Nei file di SharePoint o OneDrive viene rilevata una qualsiasi combinazione di queste parole chiave:</span><span class="sxs-lookup"><span data-stu-id="46d53-121">Any combination of these keywords are detected in SharePoint or OneDrive files:</span></span>
    - <span data-ttu-id="46d53-122">PAC</span><span class="sxs-lookup"><span data-stu-id="46d53-122">ACP</span></span>
    - <span data-ttu-id="46d53-123">Privilegio avvocato-cliente\*</span><span class="sxs-lookup"><span data-stu-id="46d53-123">Attorney Client Privilege\*</span></span>
    - <span data-ttu-id="46d53-124">Privilegio AC</span><span class="sxs-lookup"><span data-stu-id="46d53-124">AC Privilege</span></span>

## <a name="retain-audio-files"></a><span data-ttu-id="46d53-125">Conserva file audio</span><span class="sxs-lookup"><span data-stu-id="46d53-125">Retain audio files</span></span>

<span data-ttu-id="46d53-126">Questo consiglio viene visualizzato quando viene rilevato uno qualsiasi dei seguenti tipi di file in SharePoint o OneDrive.</span><span class="sxs-lookup"><span data-stu-id="46d53-126">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="46d53-127">.MP3</span><span class="sxs-lookup"><span data-stu-id="46d53-127">.MP3</span></span>
- <span data-ttu-id="46d53-128">.WMA</span><span class="sxs-lookup"><span data-stu-id="46d53-128">.WMA</span></span>
- <span data-ttu-id="46d53-129">.WAV</span><span class="sxs-lookup"><span data-stu-id="46d53-129">.WAV</span></span>
- <span data-ttu-id="46d53-130">.RA</span><span class="sxs-lookup"><span data-stu-id="46d53-130">.RA</span></span>
- <span data-ttu-id="46d53-131">.RAM</span><span class="sxs-lookup"><span data-stu-id="46d53-131">.RAM</span></span>
- <span data-ttu-id="46d53-132">.RM</span><span class="sxs-lookup"><span data-stu-id="46d53-132">.RM</span></span>
- <span data-ttu-id="46d53-133">.MID</span><span class="sxs-lookup"><span data-stu-id="46d53-133">.MID</span></span>
- <span data-ttu-id="46d53-134">.OGG</span><span class="sxs-lookup"><span data-stu-id="46d53-134">.OGG</span></span>
- <span data-ttu-id="46d53-135">.AIFF</span><span class="sxs-lookup"><span data-stu-id="46d53-135">.AIFF</span></span>
- <span data-ttu-id="46d53-136">.PCM</span><span class="sxs-lookup"><span data-stu-id="46d53-136">.PCM</span></span>
- <span data-ttu-id="46d53-137">.AAC</span><span class="sxs-lookup"><span data-stu-id="46d53-137">.AAC</span></span>
- <span data-ttu-id="46d53-138">.FLAC</span><span class="sxs-lookup"><span data-stu-id="46d53-138">.FLAC</span></span>
- <span data-ttu-id="46d53-139">.ALAC</span><span class="sxs-lookup"><span data-stu-id="46d53-139">.ALAC</span></span>

## <a name="retain-cad-files"></a><span data-ttu-id="46d53-140">Conserva file CAD</span><span class="sxs-lookup"><span data-stu-id="46d53-140">Retain CAD files</span></span>

<span data-ttu-id="46d53-141">Questo consiglio viene visualizzato quando viene rilevato uno qualsiasi dei seguenti tipi di file in SharePoint o OneDrive.</span><span class="sxs-lookup"><span data-stu-id="46d53-141">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="46d53-142">.3DXML</span><span class="sxs-lookup"><span data-stu-id="46d53-142">.3DXML</span></span>
- <span data-ttu-id="46d53-143">.ACIS</span><span class="sxs-lookup"><span data-stu-id="46d53-143">.ACIS</span></span>
- <span data-ttu-id="46d53-144">.ARC</span><span class="sxs-lookup"><span data-stu-id="46d53-144">.ARC</span></span>
- <span data-ttu-id="46d53-145">.ASM</span><span class="sxs-lookup"><span data-stu-id="46d53-145">.ASM</span></span>
- <span data-ttu-id="46d53-146">.CAT\*</span><span class="sxs-lookup"><span data-stu-id="46d53-146">.CAT\*</span></span>
- <span data-ttu-id="46d53-147">.CGR</span><span class="sxs-lookup"><span data-stu-id="46d53-147">.CGR</span></span>
- <span data-ttu-id="46d53-148">.DW\*</span><span class="sxs-lookup"><span data-stu-id="46d53-148">.DW\*</span></span>
- <span data-ttu-id="46d53-149">.DX\*</span><span class="sxs-lookup"><span data-stu-id="46d53-149">.DX\*</span></span>
- <span data-ttu-id="46d53-150">.EDRW</span><span class="sxs-lookup"><span data-stu-id="46d53-150">.EDRW</span></span>
- <span data-ttu-id="46d53-151">.IAM</span><span class="sxs-lookup"><span data-stu-id="46d53-151">.IAM</span></span>
- <span data-ttu-id="46d53-152">.IGES</span><span class="sxs-lookup"><span data-stu-id="46d53-152">.IGES</span></span>
- <span data-ttu-id="46d53-153">.IGS</span><span class="sxs-lookup"><span data-stu-id="46d53-153">.IGS</span></span>
- <span data-ttu-id="46d53-154">.IPT</span><span class="sxs-lookup"><span data-stu-id="46d53-154">.IPT</span></span>
- <span data-ttu-id="46d53-155">.JT</span><span class="sxs-lookup"><span data-stu-id="46d53-155">.JT</span></span>
- <span data-ttu-id="46d53-156">.MF1</span><span class="sxs-lookup"><span data-stu-id="46d53-156">.MF1</span></span>
- <span data-ttu-id="46d53-157">.NEU</span><span class="sxs-lookup"><span data-stu-id="46d53-157">.NEU</span></span>
- <span data-ttu-id="46d53-158">.PAR</span><span class="sxs-lookup"><span data-stu-id="46d53-158">.PAR</span></span>
- <span data-ttu-id="46d53-159">.PKG</span><span class="sxs-lookup"><span data-stu-id="46d53-159">.PKG</span></span>
- <span data-ttu-id="46d53-160">.PRC</span><span class="sxs-lookup"><span data-stu-id="46d53-160">.PRC</span></span>
- <span data-ttu-id="46d53-161">.PRT</span><span class="sxs-lookup"><span data-stu-id="46d53-161">.PRT</span></span>
- <span data-ttu-id="46d53-162">.PSM</span><span class="sxs-lookup"><span data-stu-id="46d53-162">.PSM</span></span>
- <span data-ttu-id="46d53-163">.PWD</span><span class="sxs-lookup"><span data-stu-id="46d53-163">.PWD</span></span>
- <span data-ttu-id="46d53-164">.SLD\*</span><span class="sxs-lookup"><span data-stu-id="46d53-164">.SLD\*</span></span>
- <span data-ttu-id="46d53-165">.STEP</span><span class="sxs-lookup"><span data-stu-id="46d53-165">.STEP</span></span>
- <span data-ttu-id="46d53-166">.STL</span><span class="sxs-lookup"><span data-stu-id="46d53-166">.STL</span></span>
- <span data-ttu-id="46d53-167">.STP</span><span class="sxs-lookup"><span data-stu-id="46d53-167">.STP</span></span>
- <span data-ttu-id="46d53-168">.U3D</span><span class="sxs-lookup"><span data-stu-id="46d53-168">.U3D</span></span>
- <span data-ttu-id="46d53-169">.UNV</span><span class="sxs-lookup"><span data-stu-id="46d53-169">.UNV</span></span>
- <span data-ttu-id="46d53-170">.VRML</span><span class="sxs-lookup"><span data-stu-id="46d53-170">.VRML</span></span>
- <span data-ttu-id="46d53-171">.WRL</span><span class="sxs-lookup"><span data-stu-id="46d53-171">.WRL</span></span>
- <span data-ttu-id="46d53-172">.X_\*</span><span class="sxs-lookup"><span data-stu-id="46d53-172">.X_\*</span></span>
- <span data-ttu-id="46d53-173">.XAS</span><span class="sxs-lookup"><span data-stu-id="46d53-173">.XAS</span></span>
- <span data-ttu-id="46d53-174">.XMT\*</span><span class="sxs-lookup"><span data-stu-id="46d53-174">.XMT\*</span></span>
- <span data-ttu-id="46d53-175">.XPR</span><span class="sxs-lookup"><span data-stu-id="46d53-175">.XPR</span></span>

## <a name="retain-image-files"></a><span data-ttu-id="46d53-176">Conserva file di immagine</span><span class="sxs-lookup"><span data-stu-id="46d53-176">Retain image files</span></span>

<span data-ttu-id="46d53-177">Questo consiglio viene visualizzato quando viene rilevato uno qualsiasi dei seguenti tipi di file in SharePoint o OneDrive.</span><span class="sxs-lookup"><span data-stu-id="46d53-177">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="46d53-178">.JPEG</span><span class="sxs-lookup"><span data-stu-id="46d53-178">.JPEG</span></span>
- <span data-ttu-id="46d53-179">.GIF</span><span class="sxs-lookup"><span data-stu-id="46d53-179">.GIF</span></span>
- <span data-ttu-id="46d53-180">.TIF\*</span><span class="sxs-lookup"><span data-stu-id="46d53-180">.TIF\*</span></span>
- <span data-ttu-id="46d53-181">.BMP</span><span class="sxs-lookup"><span data-stu-id="46d53-181">.BMP</span></span>
- <span data-ttu-id="46d53-182">.PNG</span><span class="sxs-lookup"><span data-stu-id="46d53-182">.PNG</span></span>
- <span data-ttu-id="46d53-183">.RAW</span><span class="sxs-lookup"><span data-stu-id="46d53-183">.RAW</span></span>
- <span data-ttu-id="46d53-184">.PSD</span><span class="sxs-lookup"><span data-stu-id="46d53-184">.PSD</span></span>
- <span data-ttu-id="46d53-185">.PSP</span><span class="sxs-lookup"><span data-stu-id="46d53-185">.PSP</span></span>
- <span data-ttu-id="46d53-186">.JPG</span><span class="sxs-lookup"><span data-stu-id="46d53-186">.JPG</span></span>
- <span data-ttu-id="46d53-187">.EXIF</span><span class="sxs-lookup"><span data-stu-id="46d53-187">.EXIF</span></span>
- <span data-ttu-id="46d53-188">.PPM</span><span class="sxs-lookup"><span data-stu-id="46d53-188">.PPM</span></span>
- <span data-ttu-id="46d53-189">.PGM</span><span class="sxs-lookup"><span data-stu-id="46d53-189">.PGM</span></span>
- <span data-ttu-id="46d53-190">.PBM</span><span class="sxs-lookup"><span data-stu-id="46d53-190">.PBM</span></span>
- <span data-ttu-id="46d53-191">.PNM</span><span class="sxs-lookup"><span data-stu-id="46d53-191">.PNM</span></span>
- <span data-ttu-id="46d53-192">.WEBP</span><span class="sxs-lookup"><span data-stu-id="46d53-192">.WEBP</span></span>

## <a name="retain-nda-content"></a><span data-ttu-id="46d53-193">Conserva i contenuti con accordo di riservatezza</span><span class="sxs-lookup"><span data-stu-id="46d53-193">Retain NDA content</span></span> 

<span data-ttu-id="46d53-194">Questo consiglio viene visualizzato quando è soddisfatto uno dei criteri seguenti.</span><span class="sxs-lookup"><span data-stu-id="46d53-194">This recommendation appears when either of the following criteria are met.</span></span>

- <span data-ttu-id="46d53-195">Nel corpo del messaggio di posta elettronica viene rilevata una qualsiasi combinazione di queste parole chiave:</span><span class="sxs-lookup"><span data-stu-id="46d53-195">Any of combination of these keywords is detected in the body of an email message:</span></span>
    - <span data-ttu-id="46d53-196">Accordo di riservatezza</span><span class="sxs-lookup"><span data-stu-id="46d53-196">NDA</span></span>
    - <span data-ttu-id="46d53-197">"Accordo di riservatezza"</span><span class="sxs-lookup"><span data-stu-id="46d53-197">"Non-Disclosure Agreement"</span></span>
    - <span data-ttu-id="46d53-198">"Accordo di riservatezza"</span><span class="sxs-lookup"><span data-stu-id="46d53-198">"Non Disclosure Agreement"</span></span>

- <span data-ttu-id="46d53-199">Nei file PDF o DOC in SharePoint o OneDrive viene rilevata una qualsiasi combinazione di queste parole chiave:</span><span class="sxs-lookup"><span data-stu-id="46d53-199">Any combination of these keywords are detected in .PDF or .DOC files in SharePoint or OneDrive:</span></span>
    - <span data-ttu-id="46d53-200">Accordo di riservatezza</span><span class="sxs-lookup"><span data-stu-id="46d53-200">NDA</span></span>
    - <span data-ttu-id="46d53-201">Accordo riservatezza</span><span class="sxs-lookup"><span data-stu-id="46d53-201">Non Disclosure Agreement</span></span>

## <a name="retain-software-development-files"></a><span data-ttu-id="46d53-202">Conserva i file di sviluppo software</span><span class="sxs-lookup"><span data-stu-id="46d53-202">Retain software development files</span></span>

<span data-ttu-id="46d53-203">Questo consiglio viene visualizzato quando viene rilevato uno qualsiasi dei seguenti tipi di file in SharePoint o OneDrive.</span><span class="sxs-lookup"><span data-stu-id="46d53-203">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="46d53-204">.ASAX</span><span class="sxs-lookup"><span data-stu-id="46d53-204">.ASAX</span></span>
- <span data-ttu-id="46d53-205">.ASM</span><span class="sxs-lookup"><span data-stu-id="46d53-205">.ASM</span></span>
- <span data-ttu-id="46d53-206">.ASP\*</span><span class="sxs-lookup"><span data-stu-id="46d53-206">.ASP\*</span></span>
- <span data-ttu-id="46d53-207">.BAT</span><span class="sxs-lookup"><span data-stu-id="46d53-207">.BAT</span></span>
- <span data-ttu-id="46d53-208">.CONFIG</span><span class="sxs-lookup"><span data-stu-id="46d53-208">.CONFIG</span></span>
- <span data-ttu-id="46d53-209">.CS</span><span class="sxs-lookup"><span data-stu-id="46d53-209">.CS</span></span>
- <span data-ttu-id="46d53-210">.CSS</span><span class="sxs-lookup"><span data-stu-id="46d53-210">.CSS</span></span>
- <span data-ttu-id="46d53-211">.DISCO</span><span class="sxs-lookup"><span data-stu-id="46d53-211">.DISCO</span></span>
- <span data-ttu-id="46d53-212">.HTM\*</span><span class="sxs-lookup"><span data-stu-id="46d53-212">.HTM\*</span></span>
- <span data-ttu-id="46d53-213">.INC</span><span class="sxs-lookup"><span data-stu-id="46d53-213">.INC</span></span>
- <span data-ttu-id="46d53-214">.JAD</span><span class="sxs-lookup"><span data-stu-id="46d53-214">.JAD</span></span>
- <span data-ttu-id="46d53-215">.JAVA</span><span class="sxs-lookup"><span data-stu-id="46d53-215">.JAVA</span></span>
- <span data-ttu-id="46d53-216">.JS\*</span><span class="sxs-lookup"><span data-stu-id="46d53-216">.JS\*</span></span>
- <span data-ttu-id="46d53-217">.LIB</span><span class="sxs-lookup"><span data-stu-id="46d53-217">.LIB</span></span>
- <span data-ttu-id="46d53-218">.O</span><span class="sxs-lookup"><span data-stu-id="46d53-218">.O</span></span>
- <span data-ttu-id="46d53-219">.PHP</span><span class="sxs-lookup"><span data-stu-id="46d53-219">.PHP</span></span>
- <span data-ttu-id="46d53-220">.RC</span><span class="sxs-lookup"><span data-stu-id="46d53-220">.RC</span></span>
- <span data-ttu-id="46d53-221">.RESX</span><span class="sxs-lookup"><span data-stu-id="46d53-221">.RESX</span></span>
- <span data-ttu-id="46d53-222">.RPT</span><span class="sxs-lookup"><span data-stu-id="46d53-222">.RPT</span></span>
- <span data-ttu-id="46d53-223">.RSS</span><span class="sxs-lookup"><span data-stu-id="46d53-223">.RSS</span></span>
- <span data-ttu-id="46d53-224">.SCPT</span><span class="sxs-lookup"><span data-stu-id="46d53-224">.SCPT</span></span>
- <span data-ttu-id="46d53-225">.SRC</span><span class="sxs-lookup"><span data-stu-id="46d53-225">.SRC</span></span>
- <span data-ttu-id="46d53-226">.VB\*</span><span class="sxs-lookup"><span data-stu-id="46d53-226">.VB\*</span></span>
- <span data-ttu-id="46d53-227">.WSF</span><span class="sxs-lookup"><span data-stu-id="46d53-227">.WSF</span></span>
- <span data-ttu-id="46d53-228">.XCODEPROJ</span><span class="sxs-lookup"><span data-stu-id="46d53-228">.XCODEPROJ</span></span>
- <span data-ttu-id="46d53-229">.XML</span><span class="sxs-lookup"><span data-stu-id="46d53-229">.XML</span></span>
- <span data-ttu-id="46d53-230">.XSD</span><span class="sxs-lookup"><span data-stu-id="46d53-230">.XSD</span></span>
- <span data-ttu-id="46d53-231">.XSL\*</span><span class="sxs-lookup"><span data-stu-id="46d53-231">.XSL\*</span></span>

## <a name="retain-video-files"></a><span data-ttu-id="46d53-232">Conserva i file video</span><span class="sxs-lookup"><span data-stu-id="46d53-232">Retain video files</span></span>

<span data-ttu-id="46d53-233">Questo consiglio viene visualizzato quando viene rilevato uno qualsiasi dei seguenti tipi di file in SharePoint o OneDrive.</span><span class="sxs-lookup"><span data-stu-id="46d53-233">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="46d53-234">.AVCHD</span><span class="sxs-lookup"><span data-stu-id="46d53-234">.AVCHD</span></span>
- <span data-ttu-id="46d53-235">.AVI</span><span class="sxs-lookup"><span data-stu-id="46d53-235">.AVI</span></span>
- <span data-ttu-id="46d53-236">.FLV</span><span class="sxs-lookup"><span data-stu-id="46d53-236">.FLV</span></span>
- <span data-ttu-id="46d53-237">.MOV</span><span class="sxs-lookup"><span data-stu-id="46d53-237">.MOV</span></span>
- <span data-ttu-id="46d53-238">.MP2V</span><span class="sxs-lookup"><span data-stu-id="46d53-238">.MP2V</span></span>
- <span data-ttu-id="46d53-239">.MP4</span><span class="sxs-lookup"><span data-stu-id="46d53-239">.MP4</span></span>
- <span data-ttu-id="46d53-240">.MP4V</span><span class="sxs-lookup"><span data-stu-id="46d53-240">.MP4V</span></span>
- <span data-ttu-id="46d53-241">.MPE</span><span class="sxs-lookup"><span data-stu-id="46d53-241">.MPE</span></span>
- <span data-ttu-id="46d53-242">.MPEG</span><span class="sxs-lookup"><span data-stu-id="46d53-242">.MPEG</span></span>
- <span data-ttu-id="46d53-243">.MPEG1</span><span class="sxs-lookup"><span data-stu-id="46d53-243">.MPEG1</span></span>
- <span data-ttu-id="46d53-244">.MPEG2</span><span class="sxs-lookup"><span data-stu-id="46d53-244">.MPEG2</span></span>
- <span data-ttu-id="46d53-245">.MPEG4</span><span class="sxs-lookup"><span data-stu-id="46d53-245">.MPEG4</span></span>
- <span data-ttu-id="46d53-246">.MPG</span><span class="sxs-lookup"><span data-stu-id="46d53-246">.MPG</span></span>
- <span data-ttu-id="46d53-247">.MPG2</span><span class="sxs-lookup"><span data-stu-id="46d53-247">.MPG2</span></span>
- <span data-ttu-id="46d53-248">.MPG4</span><span class="sxs-lookup"><span data-stu-id="46d53-248">.MPG4</span></span>
- <span data-ttu-id="46d53-249">.WMV</span><span class="sxs-lookup"><span data-stu-id="46d53-249">.WMV</span></span>
- <span data-ttu-id="46d53-250">.XMV</span><span class="sxs-lookup"><span data-stu-id="46d53-250">.XMV</span></span>