---
title: Come viene identificato il contenuto per i consigli sulla governance dei dati
ms.author: brendonb
author: laurawi
manager: laurawi
ms.date: 1/15/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ROBOTS: NOINDEX, NOFOLLOW
description: Il Centro sicurezza e conformità di Office 365 fornisce consigli per la governance dei dati in base alla configurazione corrente dell'organizzazione e consente di impostare le opzioni necessarie con pochi clic. Alcuni di questi consigli rilevano specifici contenuti nell'organizzazione e propongono le azioni consigliate per gestirli. Ad esempio, un consiglio potrebbe rilevare elementi che includono contenuti di importanza strategica, come informazioni sul privilegio avvocato-cliente o su un accordo di riservatezza, e quindi consentire l'applicazione automatica di un'etichetta di conservazione a tali elementi per assicurare che vengano opportunamente classificati e conservati. Questo argomento fornisce un elenco dei consigli sulla governance dei dati che possono essere visualizzati e descrive il contenuto che viene rilevato per attivare ciascuno di essi.
ms.openlocfilehash: 10752afb97fd0ae2993d88b4e3af9159d61de708
ms.sourcegitcommit: 1eecd7b127462585c35b0c96a179d37db45f6013
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "37342939"
---
# <a name="how-content-is-identified-for-data-governance-recommendations"></a><span data-ttu-id="c5086-106">Come viene identificato il contenuto per i consigli sulla governance dei dati</span><span class="sxs-lookup"><span data-stu-id="c5086-106">How content is identified for data-governance recommendations</span></span>

<span data-ttu-id="c5086-p102">Il Centro sicurezza e conformità di Office 365 fornisce consigli per la governance dei dati in base alla configurazione corrente dell'organizzazione e consente di impostare le opzioni necessarie con pochi clic. Alcuni di questi consigli rilevano specifici contenuti nell'organizzazione e propongono le azioni consigliate per gestirli. Ad esempio, un consiglio potrebbe rilevare elementi che includono contenuti di importanza strategica, come informazioni sul privilegio avvocato-cliente o su un accordo di riservatezza, e quindi consentire l'applicazione automatica di un'etichetta di conservazione a tali elementi per assicurare che vengano opportunamente classificati e conservati.</span><span class="sxs-lookup"><span data-stu-id="c5086-p102">The Office 365 Security & Compliance Center provides recommendations for data governance based on your org's current setup and lets you set things up in a couple clicks. Some of these recommendations detect specific content in your organization and then provide recommended steps for managing that content. For example, a recommendation might detect items that contain business-critical content (such as attorney-client privilege or NDA info), and then let you automatically apply a retention label to those items to ensure that they’re classified and retained as needed.</span></span>

<span data-ttu-id="c5086-110">Questo argomento fornisce un elenco dei consigli sulla governance dei dati che possono essere visualizzati e descrive il contenuto che viene rilevato per attivare ciascuno di essi.</span><span class="sxs-lookup"><span data-stu-id="c5086-110">This topic lists the data-governance recommendations you might see and describes what content is detected to trigger each one.</span></span>

## <a name="clean-up-voicemail"></a><span data-ttu-id="c5086-111">Pulisci la segreteria telefonica</span><span class="sxs-lookup"><span data-stu-id="c5086-111">Clean up voicemail</span></span>

<span data-ttu-id="c5086-p103">Questo consiglio viene visualizzato quando nelle cassette postali degli utenti vengono rilevati messaggi di posta elettronica identificati come messaggi di tipo ‘postavocale’. Per saperne di più, vedere l'argomento relativo alle [proprietà dei messaggi in Exchange](https://docs.microsoft.com/en-us/exchange/policy-and-compliance/ediscovery/message-properties-and-search-operators?view=exchserver-2019#searchable-properties-in-exchange).</span><span class="sxs-lookup"><span data-stu-id="c5086-p103">This recommendation appears when email messages identified as the message type ‘voicemail’ are detected in users’ mailboxes. Learn more about [message properties in Exchange](https://docs.microsoft.com/en-us/exchange/policy-and-compliance/ediscovery/message-properties-and-search-operators?view=exchserver-2019#searchable-properties-in-exchange).</span></span>

## <a name="label-attorney-client-privilege-content"></a><span data-ttu-id="c5086-114">Applica etichetta ai contenuti coperti da privilegio avvocato-cliente</span><span class="sxs-lookup"><span data-stu-id="c5086-114">Label attorney-client privilege content</span></span> 

<span data-ttu-id="c5086-115">Questo consiglio viene visualizzato quando è soddisfatto uno dei criteri seguenti.</span><span class="sxs-lookup"><span data-stu-id="c5086-115">This recommendation appears when either of the following criteria are met.</span></span>

- <span data-ttu-id="c5086-116">Nel corpo del messaggio di posta elettronica viene rilevata una qualsiasi combinazione di queste parole chiave:</span><span class="sxs-lookup"><span data-stu-id="c5086-116">Any of combination of these keywords is detected in the body of an email message:</span></span>
    - <span data-ttu-id="c5086-117">PAC</span><span class="sxs-lookup"><span data-stu-id="c5086-117">ACP</span></span>
    - <span data-ttu-id="c5086-118">Privilegio avvocato cliente</span><span class="sxs-lookup"><span data-stu-id="c5086-118">Attorney Client Privilege</span></span>
    - <span data-ttu-id="c5086-119">Privilegio avvocato-cliente</span><span class="sxs-lookup"><span data-stu-id="c5086-119">Attorney-Client Privilege</span></span>
    - <span data-ttu-id="c5086-120">Coperto dal privilegio avvocato-cliente</span><span class="sxs-lookup"><span data-stu-id="c5086-120">Attorney-Client Privileged</span></span>

- <span data-ttu-id="c5086-121">Nei file di SharePoint o OneDrive viene rilevata una qualsiasi combinazione di queste parole chiave:</span><span class="sxs-lookup"><span data-stu-id="c5086-121">Any combination of these keywords are detected in SharePoint or OneDrive files:</span></span>
    - <span data-ttu-id="c5086-122">PAC</span><span class="sxs-lookup"><span data-stu-id="c5086-122">ACP</span></span>
    - <span data-ttu-id="c5086-123">Privilegio avvocato-cliente\*</span><span class="sxs-lookup"><span data-stu-id="c5086-123">Attorney Client Privilege\*</span></span>
    - <span data-ttu-id="c5086-124">Privilegio AC</span><span class="sxs-lookup"><span data-stu-id="c5086-124">AC Privilege</span></span>

## <a name="retain-audio-files"></a><span data-ttu-id="c5086-125">Conserva file audio</span><span class="sxs-lookup"><span data-stu-id="c5086-125">Retain audio files</span></span>

<span data-ttu-id="c5086-126">Questo consiglio viene visualizzato quando viene rilevato uno qualsiasi dei seguenti tipi di file in SharePoint o OneDrive.</span><span class="sxs-lookup"><span data-stu-id="c5086-126">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="c5086-127">.MP3</span><span class="sxs-lookup"><span data-stu-id="c5086-127">.MP3</span></span>
- <span data-ttu-id="c5086-128">.WMA</span><span class="sxs-lookup"><span data-stu-id="c5086-128">.WMA</span></span>
- <span data-ttu-id="c5086-129">.WAV</span><span class="sxs-lookup"><span data-stu-id="c5086-129">.WAV</span></span>
- <span data-ttu-id="c5086-130">.RA</span><span class="sxs-lookup"><span data-stu-id="c5086-130">.RA</span></span>
- <span data-ttu-id="c5086-131">.RAM</span><span class="sxs-lookup"><span data-stu-id="c5086-131">.RAM</span></span>
- <span data-ttu-id="c5086-132">.RM</span><span class="sxs-lookup"><span data-stu-id="c5086-132">.RM</span></span>
- <span data-ttu-id="c5086-133">.MID</span><span class="sxs-lookup"><span data-stu-id="c5086-133">.MID</span></span>
- <span data-ttu-id="c5086-134">.OGG</span><span class="sxs-lookup"><span data-stu-id="c5086-134">.OGG</span></span>
- <span data-ttu-id="c5086-135">.AIFF</span><span class="sxs-lookup"><span data-stu-id="c5086-135">.AIFF</span></span>
- <span data-ttu-id="c5086-136">.PCM</span><span class="sxs-lookup"><span data-stu-id="c5086-136">.PCM</span></span>
- <span data-ttu-id="c5086-137">.AAC</span><span class="sxs-lookup"><span data-stu-id="c5086-137">.AAC</span></span>
- <span data-ttu-id="c5086-138">.FLAC</span><span class="sxs-lookup"><span data-stu-id="c5086-138">.FLAC</span></span>
- <span data-ttu-id="c5086-139">.ALAC</span><span class="sxs-lookup"><span data-stu-id="c5086-139">.ALAC</span></span>

## <a name="retain-cad-files"></a><span data-ttu-id="c5086-140">Conserva file CAD</span><span class="sxs-lookup"><span data-stu-id="c5086-140">Retain CAD files</span></span>

<span data-ttu-id="c5086-141">Questo consiglio viene visualizzato quando viene rilevato uno qualsiasi dei seguenti tipi di file in SharePoint o OneDrive.</span><span class="sxs-lookup"><span data-stu-id="c5086-141">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="c5086-142">.3DXML</span><span class="sxs-lookup"><span data-stu-id="c5086-142">.3DXML</span></span>
- <span data-ttu-id="c5086-143">.ACIS</span><span class="sxs-lookup"><span data-stu-id="c5086-143">.ACIS</span></span>
- <span data-ttu-id="c5086-144">.ARC</span><span class="sxs-lookup"><span data-stu-id="c5086-144">.ARC</span></span>
- <span data-ttu-id="c5086-145">.ASM</span><span class="sxs-lookup"><span data-stu-id="c5086-145">.ASM</span></span>
- <span data-ttu-id="c5086-146">.CAT\*</span><span class="sxs-lookup"><span data-stu-id="c5086-146">.CAT\*</span></span>
- <span data-ttu-id="c5086-147">.CGR</span><span class="sxs-lookup"><span data-stu-id="c5086-147">.CGR</span></span>
- <span data-ttu-id="c5086-148">.DW\*</span><span class="sxs-lookup"><span data-stu-id="c5086-148">.DW\*</span></span>
- <span data-ttu-id="c5086-149">.DX\*</span><span class="sxs-lookup"><span data-stu-id="c5086-149">.DX\*</span></span>
- <span data-ttu-id="c5086-150">.EDRW</span><span class="sxs-lookup"><span data-stu-id="c5086-150">.EDRW</span></span>
- <span data-ttu-id="c5086-151">.IAM</span><span class="sxs-lookup"><span data-stu-id="c5086-151">.IAM</span></span>
- <span data-ttu-id="c5086-152">.IGES</span><span class="sxs-lookup"><span data-stu-id="c5086-152">.IGES</span></span>
- <span data-ttu-id="c5086-153">.IGS</span><span class="sxs-lookup"><span data-stu-id="c5086-153">.IGS</span></span>
- <span data-ttu-id="c5086-154">.IPT</span><span class="sxs-lookup"><span data-stu-id="c5086-154">.IPT</span></span>
- <span data-ttu-id="c5086-155">.JT</span><span class="sxs-lookup"><span data-stu-id="c5086-155">.JT</span></span>
- <span data-ttu-id="c5086-156">.MF1</span><span class="sxs-lookup"><span data-stu-id="c5086-156">.MF1</span></span>
- <span data-ttu-id="c5086-157">.NEU</span><span class="sxs-lookup"><span data-stu-id="c5086-157">.NEU</span></span>
- <span data-ttu-id="c5086-158">.PAR</span><span class="sxs-lookup"><span data-stu-id="c5086-158">.PAR</span></span>
- <span data-ttu-id="c5086-159">.PKG</span><span class="sxs-lookup"><span data-stu-id="c5086-159">.PKG</span></span>
- <span data-ttu-id="c5086-160">.PRC</span><span class="sxs-lookup"><span data-stu-id="c5086-160">.PRC</span></span>
- <span data-ttu-id="c5086-161">.PRT</span><span class="sxs-lookup"><span data-stu-id="c5086-161">.PRT</span></span>
- <span data-ttu-id="c5086-162">.PSM</span><span class="sxs-lookup"><span data-stu-id="c5086-162">.PSM</span></span>
- <span data-ttu-id="c5086-163">.PWD</span><span class="sxs-lookup"><span data-stu-id="c5086-163">.PWD</span></span>
- <span data-ttu-id="c5086-164">.SLD\*</span><span class="sxs-lookup"><span data-stu-id="c5086-164">.SLD\*</span></span>
- <span data-ttu-id="c5086-165">.STEP</span><span class="sxs-lookup"><span data-stu-id="c5086-165">.STEP</span></span>
- <span data-ttu-id="c5086-166">.STL</span><span class="sxs-lookup"><span data-stu-id="c5086-166">.STL</span></span>
- <span data-ttu-id="c5086-167">.STP</span><span class="sxs-lookup"><span data-stu-id="c5086-167">.STP</span></span>
- <span data-ttu-id="c5086-168">.U3D</span><span class="sxs-lookup"><span data-stu-id="c5086-168">.U3D</span></span>
- <span data-ttu-id="c5086-169">.UNV</span><span class="sxs-lookup"><span data-stu-id="c5086-169">.UNV</span></span>
- <span data-ttu-id="c5086-170">.VRML</span><span class="sxs-lookup"><span data-stu-id="c5086-170">.VRML</span></span>
- <span data-ttu-id="c5086-171">.WRL</span><span class="sxs-lookup"><span data-stu-id="c5086-171">.WRL</span></span>
- <span data-ttu-id="c5086-172">.X_\*</span><span class="sxs-lookup"><span data-stu-id="c5086-172">.X_\*</span></span>
- <span data-ttu-id="c5086-173">.XAS</span><span class="sxs-lookup"><span data-stu-id="c5086-173">.XAS</span></span>
- <span data-ttu-id="c5086-174">.XMT\*</span><span class="sxs-lookup"><span data-stu-id="c5086-174">.XMT\*</span></span>
- <span data-ttu-id="c5086-175">.XPR</span><span class="sxs-lookup"><span data-stu-id="c5086-175">.XPR</span></span>

## <a name="retain-image-files"></a><span data-ttu-id="c5086-176">Conserva file di immagine</span><span class="sxs-lookup"><span data-stu-id="c5086-176">Retain image files</span></span>

<span data-ttu-id="c5086-177">Questo consiglio viene visualizzato quando viene rilevato uno qualsiasi dei seguenti tipi di file in SharePoint o OneDrive.</span><span class="sxs-lookup"><span data-stu-id="c5086-177">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="c5086-178">.JPEG</span><span class="sxs-lookup"><span data-stu-id="c5086-178">.JPEG</span></span>
- <span data-ttu-id="c5086-179">.GIF</span><span class="sxs-lookup"><span data-stu-id="c5086-179">.GIF</span></span>
- <span data-ttu-id="c5086-180">.TIF\*</span><span class="sxs-lookup"><span data-stu-id="c5086-180">.TIF\*</span></span>
- <span data-ttu-id="c5086-181">.BMP</span><span class="sxs-lookup"><span data-stu-id="c5086-181">.BMP</span></span>
- <span data-ttu-id="c5086-182">.PNG</span><span class="sxs-lookup"><span data-stu-id="c5086-182">.PNG</span></span>
- <span data-ttu-id="c5086-183">.RAW</span><span class="sxs-lookup"><span data-stu-id="c5086-183">.RAW</span></span>
- <span data-ttu-id="c5086-184">.PSD</span><span class="sxs-lookup"><span data-stu-id="c5086-184">.PSD</span></span>
- <span data-ttu-id="c5086-185">.PSP</span><span class="sxs-lookup"><span data-stu-id="c5086-185">.PSP</span></span>
- <span data-ttu-id="c5086-186">.JPG</span><span class="sxs-lookup"><span data-stu-id="c5086-186">.JPG</span></span>
- <span data-ttu-id="c5086-187">.EXIF</span><span class="sxs-lookup"><span data-stu-id="c5086-187">.EXIF</span></span>
- <span data-ttu-id="c5086-188">.PPM</span><span class="sxs-lookup"><span data-stu-id="c5086-188">.PPM</span></span>
- <span data-ttu-id="c5086-189">.PGM</span><span class="sxs-lookup"><span data-stu-id="c5086-189">.PGM</span></span>
- <span data-ttu-id="c5086-190">.PBM</span><span class="sxs-lookup"><span data-stu-id="c5086-190">.PBM</span></span>
- <span data-ttu-id="c5086-191">.PNM</span><span class="sxs-lookup"><span data-stu-id="c5086-191">.PNM</span></span>
- <span data-ttu-id="c5086-192">.WEBP</span><span class="sxs-lookup"><span data-stu-id="c5086-192">.WEBP</span></span>

## <a name="retain-nda-content"></a><span data-ttu-id="c5086-193">Conserva i contenuti con accordo di riservatezza</span><span class="sxs-lookup"><span data-stu-id="c5086-193">Retain NDA content</span></span> 

<span data-ttu-id="c5086-194">Questo consiglio viene visualizzato quando è soddisfatto uno dei criteri seguenti.</span><span class="sxs-lookup"><span data-stu-id="c5086-194">This recommendation appears when either of the following criteria are met.</span></span>

- <span data-ttu-id="c5086-195">Nel corpo del messaggio di posta elettronica viene rilevata una qualsiasi combinazione di queste parole chiave:</span><span class="sxs-lookup"><span data-stu-id="c5086-195">Any of combination of these keywords is detected in the body of an email message:</span></span>
    - <span data-ttu-id="c5086-196">Accordo di riservatezza</span><span class="sxs-lookup"><span data-stu-id="c5086-196">NDA</span></span>
    - <span data-ttu-id="c5086-197">"Accordo di riservatezza"</span><span class="sxs-lookup"><span data-stu-id="c5086-197">“Non-Disclosure Agreement”</span></span>
    - <span data-ttu-id="c5086-198">"Accordo riservatezza"</span><span class="sxs-lookup"><span data-stu-id="c5086-198">“Non Disclosure Agreement”</span></span>

- <span data-ttu-id="c5086-199">Nei file PDF o DOC in SharePoint o OneDrive viene rilevata una qualsiasi combinazione di queste parole chiave:</span><span class="sxs-lookup"><span data-stu-id="c5086-199">Any combination of these keywords are detected in .PDF or .DOC files in SharePoint or OneDrive:</span></span>
    - <span data-ttu-id="c5086-200">Accordo di riservatezza</span><span class="sxs-lookup"><span data-stu-id="c5086-200">NDA</span></span>
    - <span data-ttu-id="c5086-201">Accordo riservatezza</span><span class="sxs-lookup"><span data-stu-id="c5086-201">Non Disclosure Agreement</span></span>

## <a name="retain-software-development-files"></a><span data-ttu-id="c5086-202">Conserva i file di sviluppo software</span><span class="sxs-lookup"><span data-stu-id="c5086-202">Retain software development files</span></span>

<span data-ttu-id="c5086-203">Questo consiglio viene visualizzato quando viene rilevato uno qualsiasi dei seguenti tipi di file in SharePoint o OneDrive.</span><span class="sxs-lookup"><span data-stu-id="c5086-203">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="c5086-204">.ASAX</span><span class="sxs-lookup"><span data-stu-id="c5086-204">.ASAX</span></span>
- <span data-ttu-id="c5086-205">.ASM</span><span class="sxs-lookup"><span data-stu-id="c5086-205">.ASM</span></span>
- <span data-ttu-id="c5086-206">.ASP\*</span><span class="sxs-lookup"><span data-stu-id="c5086-206">.ASP\*</span></span>
- <span data-ttu-id="c5086-207">.BAT</span><span class="sxs-lookup"><span data-stu-id="c5086-207">.BAT</span></span>
- <span data-ttu-id="c5086-208">.CONFIG</span><span class="sxs-lookup"><span data-stu-id="c5086-208">.CONFIG</span></span>
- <span data-ttu-id="c5086-209">.CS</span><span class="sxs-lookup"><span data-stu-id="c5086-209">.CS</span></span>
- <span data-ttu-id="c5086-210">.CSS</span><span class="sxs-lookup"><span data-stu-id="c5086-210">.CSS</span></span>
- <span data-ttu-id="c5086-211">.DISCO</span><span class="sxs-lookup"><span data-stu-id="c5086-211">.DISCO</span></span>
- <span data-ttu-id="c5086-212">.HTM\*</span><span class="sxs-lookup"><span data-stu-id="c5086-212">.HTM\*</span></span>
- <span data-ttu-id="c5086-213">.INC</span><span class="sxs-lookup"><span data-stu-id="c5086-213">.INC</span></span>
- <span data-ttu-id="c5086-214">.JAD</span><span class="sxs-lookup"><span data-stu-id="c5086-214">.JAD</span></span>
- <span data-ttu-id="c5086-215">.JAVA</span><span class="sxs-lookup"><span data-stu-id="c5086-215">.JAVA</span></span>
- <span data-ttu-id="c5086-216">.JS\*</span><span class="sxs-lookup"><span data-stu-id="c5086-216">.JS\*</span></span>
- <span data-ttu-id="c5086-217">.LIB</span><span class="sxs-lookup"><span data-stu-id="c5086-217">.LIB</span></span>
- <span data-ttu-id="c5086-218">.O</span><span class="sxs-lookup"><span data-stu-id="c5086-218">.O</span></span>
- <span data-ttu-id="c5086-219">.PHP</span><span class="sxs-lookup"><span data-stu-id="c5086-219">.PHP</span></span>
- <span data-ttu-id="c5086-220">.RC</span><span class="sxs-lookup"><span data-stu-id="c5086-220">.RC</span></span>
- <span data-ttu-id="c5086-221">.RESX</span><span class="sxs-lookup"><span data-stu-id="c5086-221">.RESX</span></span>
- <span data-ttu-id="c5086-222">.RPT</span><span class="sxs-lookup"><span data-stu-id="c5086-222">.RPT</span></span>
- <span data-ttu-id="c5086-223">.RSS</span><span class="sxs-lookup"><span data-stu-id="c5086-223">.RSS</span></span>
- <span data-ttu-id="c5086-224">.SCPT</span><span class="sxs-lookup"><span data-stu-id="c5086-224">.SCPT</span></span>
- <span data-ttu-id="c5086-225">.SRC</span><span class="sxs-lookup"><span data-stu-id="c5086-225">.SRC</span></span>
- <span data-ttu-id="c5086-226">.VB\*</span><span class="sxs-lookup"><span data-stu-id="c5086-226">.VB\*</span></span>
- <span data-ttu-id="c5086-227">.WSF</span><span class="sxs-lookup"><span data-stu-id="c5086-227">.WSF</span></span>
- <span data-ttu-id="c5086-228">.XCODEPROJ</span><span class="sxs-lookup"><span data-stu-id="c5086-228">.XCODEPROJ</span></span>
- <span data-ttu-id="c5086-229">.XML</span><span class="sxs-lookup"><span data-stu-id="c5086-229">.XML</span></span>
- <span data-ttu-id="c5086-230">.XSD</span><span class="sxs-lookup"><span data-stu-id="c5086-230">.XSD</span></span>
- <span data-ttu-id="c5086-231">.XSL\*</span><span class="sxs-lookup"><span data-stu-id="c5086-231">.XSL\*</span></span>

## <a name="retain-video-files"></a><span data-ttu-id="c5086-232">Conserva i file video</span><span class="sxs-lookup"><span data-stu-id="c5086-232">Retain video files</span></span>

<span data-ttu-id="c5086-233">Questo consiglio viene visualizzato quando viene rilevato uno qualsiasi dei seguenti tipi di file in SharePoint o OneDrive.</span><span class="sxs-lookup"><span data-stu-id="c5086-233">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="c5086-234">.AVCHD</span><span class="sxs-lookup"><span data-stu-id="c5086-234">.AVCHD</span></span>
- <span data-ttu-id="c5086-235">.AVI</span><span class="sxs-lookup"><span data-stu-id="c5086-235">.AVI</span></span>
- <span data-ttu-id="c5086-236">.FLV</span><span class="sxs-lookup"><span data-stu-id="c5086-236">.FLV</span></span>
- <span data-ttu-id="c5086-237">.MOV</span><span class="sxs-lookup"><span data-stu-id="c5086-237">.MOV</span></span>
- <span data-ttu-id="c5086-238">.MP2V</span><span class="sxs-lookup"><span data-stu-id="c5086-238">.MP2V</span></span>
- <span data-ttu-id="c5086-239">.MP4</span><span class="sxs-lookup"><span data-stu-id="c5086-239">.MP4</span></span>
- <span data-ttu-id="c5086-240">.MP4V</span><span class="sxs-lookup"><span data-stu-id="c5086-240">.MP4V</span></span>
- <span data-ttu-id="c5086-241">.MPE</span><span class="sxs-lookup"><span data-stu-id="c5086-241">.MPE</span></span>
- <span data-ttu-id="c5086-242">.MPEG</span><span class="sxs-lookup"><span data-stu-id="c5086-242">.MPEG</span></span>
- <span data-ttu-id="c5086-243">.MPEG1</span><span class="sxs-lookup"><span data-stu-id="c5086-243">.MPEG1</span></span>
- <span data-ttu-id="c5086-244">.MPEG2</span><span class="sxs-lookup"><span data-stu-id="c5086-244">.MPEG2</span></span>
- <span data-ttu-id="c5086-245">.MPEG4</span><span class="sxs-lookup"><span data-stu-id="c5086-245">.MPEG4</span></span>
- <span data-ttu-id="c5086-246">.MPG</span><span class="sxs-lookup"><span data-stu-id="c5086-246">.MPG</span></span>
- <span data-ttu-id="c5086-247">.MPG2</span><span class="sxs-lookup"><span data-stu-id="c5086-247">.MPG2</span></span>
- <span data-ttu-id="c5086-248">.MPG4</span><span class="sxs-lookup"><span data-stu-id="c5086-248">.MPG4</span></span>
- <span data-ttu-id="c5086-249">.WMV</span><span class="sxs-lookup"><span data-stu-id="c5086-249">.WMV</span></span>
- <span data-ttu-id="c5086-250">.XMV</span><span class="sxs-lookup"><span data-stu-id="c5086-250">.XMV</span></span>
