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
description: Il Centro sicurezza e conformità di Office 365 fornisce consigli per la governance dei dati in base alla configurazione corrente dell'organizzazione e consente di impostare le opzioni necessarie con pochi clic. Alcuni di questi consigli rilevano specifici contenuti nell'organizzazione e propongono le azioni consigliate per gestirli. Ad esempio, un consiglio potrebbe rilevare elementi che includono contenuti di importanza strategica, come informazioni sul privilegio avvocato-cliente o su un accordo di riservatezza, e quindi consentire l'applicazione automatica di un'etichetta di conservazione a tali elementi per assicurare che vengano opportunamente classificati e conservati. Questo argomento fornisce un elenco dei consigli sulla governance dei dati che possono essere visualizzati e descrive il contenuto che viene rilevato per attivare ciascuno di essi.
ms.openlocfilehash: af3c08f568bb0b44e8454ee345a84308b53cf01f
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595433"
---
# <a name="how-content-is-identified-for-data-governance-recommendations"></a><span data-ttu-id="6cb99-106">Come viene identificato il contenuto per i consigli sulla governance dei dati</span><span class="sxs-lookup"><span data-stu-id="6cb99-106">How content is identified for data-governance recommendations</span></span>

<span data-ttu-id="6cb99-p102">Il Centro sicurezza e conformità di Office 365 fornisce consigli per la governance dei dati in base alla configurazione corrente dell'organizzazione e consente di impostare le opzioni necessarie con pochi clic. Alcuni di questi consigli rilevano specifici contenuti nell'organizzazione e propongono le azioni consigliate per gestirli. Ad esempio, un consiglio potrebbe rilevare elementi che includono contenuti di importanza strategica, come informazioni sul privilegio avvocato-cliente o su un accordo di riservatezza, e quindi consentire l'applicazione automatica di un'etichetta di conservazione a tali elementi per assicurare che vengano opportunamente classificati e conservati.</span><span class="sxs-lookup"><span data-stu-id="6cb99-p102">The Office 365 Security & Compliance Center provides recommendations for data governance based on your org's current setup and lets you set things up in a couple clicks. Some of these recommendations detect specific content in your organization and then provide recommended steps for managing that content. For example, a recommendation might detect items that contain business-critical content (such as attorney-client privilege or NDA info), and then let you automatically apply a retention label to those items to ensure that they’re classified and retained as needed.</span></span>

<span data-ttu-id="6cb99-110">Questo argomento fornisce un elenco dei consigli sulla governance dei dati che possono essere visualizzati e descrive il contenuto che viene rilevato per attivare ciascuno di essi.</span><span class="sxs-lookup"><span data-stu-id="6cb99-110">This topic lists the data-governance recommendations you might see and describes what content is detected to trigger each one.</span></span>

## <a name="clean-up-voicemail"></a><span data-ttu-id="6cb99-111">Pulisci la segreteria telefonica</span><span class="sxs-lookup"><span data-stu-id="6cb99-111">Clean up voicemail</span></span>

<span data-ttu-id="6cb99-p103">Questo consiglio viene visualizzato quando nelle cassette postali degli utenti vengono rilevati messaggi di posta elettronica identificati come messaggi di tipo ‘postavocale’. Per saperne di più, vedere l'argomento relativo alle [proprietà dei messaggi in Exchange](https://docs.microsoft.com/exchange/policy-and-compliance/ediscovery/message-properties-and-search-operators?view=exchserver-2019#searchable-properties-in-exchange).</span><span class="sxs-lookup"><span data-stu-id="6cb99-p103">This recommendation appears when email messages identified as the message type ‘voicemail’ are detected in users’ mailboxes. Learn more about [message properties in Exchange](https://docs.microsoft.com/exchange/policy-and-compliance/ediscovery/message-properties-and-search-operators?view=exchserver-2019#searchable-properties-in-exchange).</span></span>

## <a name="label-attorney-client-privilege-content"></a><span data-ttu-id="6cb99-114">Applica etichetta ai contenuti coperti da privilegio avvocato-cliente</span><span class="sxs-lookup"><span data-stu-id="6cb99-114">Label attorney-client privilege content</span></span> 

<span data-ttu-id="6cb99-115">Questo consiglio viene visualizzato quando è soddisfatto uno dei criteri seguenti.</span><span class="sxs-lookup"><span data-stu-id="6cb99-115">This recommendation appears when either of the following criteria are met.</span></span>

- <span data-ttu-id="6cb99-116">Nel corpo del messaggio di posta elettronica viene rilevata una qualsiasi combinazione di queste parole chiave:</span><span class="sxs-lookup"><span data-stu-id="6cb99-116">Any of combination of these keywords is detected in the body of an email message:</span></span>
    - <span data-ttu-id="6cb99-117">PAC</span><span class="sxs-lookup"><span data-stu-id="6cb99-117">ACP</span></span>
    - <span data-ttu-id="6cb99-118">Privilegio avvocato cliente</span><span class="sxs-lookup"><span data-stu-id="6cb99-118">Attorney Client Privilege</span></span>
    - <span data-ttu-id="6cb99-119">Privilegio avvocato-cliente</span><span class="sxs-lookup"><span data-stu-id="6cb99-119">Attorney-Client Privilege</span></span>
    - <span data-ttu-id="6cb99-120">Coperto dal privilegio avvocato-cliente</span><span class="sxs-lookup"><span data-stu-id="6cb99-120">Attorney-Client Privileged</span></span>

- <span data-ttu-id="6cb99-121">Nei file di SharePoint o OneDrive viene rilevata una qualsiasi combinazione di queste parole chiave:</span><span class="sxs-lookup"><span data-stu-id="6cb99-121">Any combination of these keywords are detected in SharePoint or OneDrive files:</span></span>
    - <span data-ttu-id="6cb99-122">PAC</span><span class="sxs-lookup"><span data-stu-id="6cb99-122">ACP</span></span>
    - <span data-ttu-id="6cb99-123">Privilegio avvocato-cliente\*</span><span class="sxs-lookup"><span data-stu-id="6cb99-123">Attorney Client Privilege\*</span></span>
    - <span data-ttu-id="6cb99-124">Privilegio AC</span><span class="sxs-lookup"><span data-stu-id="6cb99-124">AC Privilege</span></span>

## <a name="retain-audio-files"></a><span data-ttu-id="6cb99-125">Conserva file audio</span><span class="sxs-lookup"><span data-stu-id="6cb99-125">Retain audio files</span></span>

<span data-ttu-id="6cb99-126">Questo consiglio viene visualizzato quando viene rilevato uno qualsiasi dei seguenti tipi di file in SharePoint o OneDrive.</span><span class="sxs-lookup"><span data-stu-id="6cb99-126">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="6cb99-127">.MP3</span><span class="sxs-lookup"><span data-stu-id="6cb99-127">.MP3</span></span>
- <span data-ttu-id="6cb99-128">.WMA</span><span class="sxs-lookup"><span data-stu-id="6cb99-128">.WMA</span></span>
- <span data-ttu-id="6cb99-129">.WAV</span><span class="sxs-lookup"><span data-stu-id="6cb99-129">.WAV</span></span>
- <span data-ttu-id="6cb99-130">.RA</span><span class="sxs-lookup"><span data-stu-id="6cb99-130">.RA</span></span>
- <span data-ttu-id="6cb99-131">.RAM</span><span class="sxs-lookup"><span data-stu-id="6cb99-131">.RAM</span></span>
- <span data-ttu-id="6cb99-132">.RM</span><span class="sxs-lookup"><span data-stu-id="6cb99-132">.RM</span></span>
- <span data-ttu-id="6cb99-133">.MID</span><span class="sxs-lookup"><span data-stu-id="6cb99-133">.MID</span></span>
- <span data-ttu-id="6cb99-134">.OGG</span><span class="sxs-lookup"><span data-stu-id="6cb99-134">.OGG</span></span>
- <span data-ttu-id="6cb99-135">.AIFF</span><span class="sxs-lookup"><span data-stu-id="6cb99-135">.AIFF</span></span>
- <span data-ttu-id="6cb99-136">.PCM</span><span class="sxs-lookup"><span data-stu-id="6cb99-136">.PCM</span></span>
- <span data-ttu-id="6cb99-137">.AAC</span><span class="sxs-lookup"><span data-stu-id="6cb99-137">.AAC</span></span>
- <span data-ttu-id="6cb99-138">.FLAC</span><span class="sxs-lookup"><span data-stu-id="6cb99-138">.FLAC</span></span>
- <span data-ttu-id="6cb99-139">.ALAC</span><span class="sxs-lookup"><span data-stu-id="6cb99-139">.ALAC</span></span>

## <a name="retain-cad-files"></a><span data-ttu-id="6cb99-140">Conserva file CAD</span><span class="sxs-lookup"><span data-stu-id="6cb99-140">Retain CAD files</span></span>

<span data-ttu-id="6cb99-141">Questo consiglio viene visualizzato quando viene rilevato uno qualsiasi dei seguenti tipi di file in SharePoint o OneDrive.</span><span class="sxs-lookup"><span data-stu-id="6cb99-141">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="6cb99-142">.3DXML</span><span class="sxs-lookup"><span data-stu-id="6cb99-142">.3DXML</span></span>
- <span data-ttu-id="6cb99-143">.ACIS</span><span class="sxs-lookup"><span data-stu-id="6cb99-143">.ACIS</span></span>
- <span data-ttu-id="6cb99-144">.ARC</span><span class="sxs-lookup"><span data-stu-id="6cb99-144">.ARC</span></span>
- <span data-ttu-id="6cb99-145">.ASM</span><span class="sxs-lookup"><span data-stu-id="6cb99-145">.ASM</span></span>
- <span data-ttu-id="6cb99-146">.CAT\*</span><span class="sxs-lookup"><span data-stu-id="6cb99-146">.CAT\*</span></span>
- <span data-ttu-id="6cb99-147">.CGR</span><span class="sxs-lookup"><span data-stu-id="6cb99-147">.CGR</span></span>
- <span data-ttu-id="6cb99-148">.DW\*</span><span class="sxs-lookup"><span data-stu-id="6cb99-148">.DW\*</span></span>
- <span data-ttu-id="6cb99-149">.DX\*</span><span class="sxs-lookup"><span data-stu-id="6cb99-149">.DX\*</span></span>
- <span data-ttu-id="6cb99-150">.EDRW</span><span class="sxs-lookup"><span data-stu-id="6cb99-150">.EDRW</span></span>
- <span data-ttu-id="6cb99-151">.IAM</span><span class="sxs-lookup"><span data-stu-id="6cb99-151">.IAM</span></span>
- <span data-ttu-id="6cb99-152">.IGES</span><span class="sxs-lookup"><span data-stu-id="6cb99-152">.IGES</span></span>
- <span data-ttu-id="6cb99-153">.IGS</span><span class="sxs-lookup"><span data-stu-id="6cb99-153">.IGS</span></span>
- <span data-ttu-id="6cb99-154">.IPT</span><span class="sxs-lookup"><span data-stu-id="6cb99-154">.IPT</span></span>
- <span data-ttu-id="6cb99-155">.JT</span><span class="sxs-lookup"><span data-stu-id="6cb99-155">.JT</span></span>
- <span data-ttu-id="6cb99-156">.MF1</span><span class="sxs-lookup"><span data-stu-id="6cb99-156">.MF1</span></span>
- <span data-ttu-id="6cb99-157">.NEU</span><span class="sxs-lookup"><span data-stu-id="6cb99-157">.NEU</span></span>
- <span data-ttu-id="6cb99-158">.PAR</span><span class="sxs-lookup"><span data-stu-id="6cb99-158">.PAR</span></span>
- <span data-ttu-id="6cb99-159">.PKG</span><span class="sxs-lookup"><span data-stu-id="6cb99-159">.PKG</span></span>
- <span data-ttu-id="6cb99-160">.PRC</span><span class="sxs-lookup"><span data-stu-id="6cb99-160">.PRC</span></span>
- <span data-ttu-id="6cb99-161">.PRT</span><span class="sxs-lookup"><span data-stu-id="6cb99-161">.PRT</span></span>
- <span data-ttu-id="6cb99-162">.PSM</span><span class="sxs-lookup"><span data-stu-id="6cb99-162">.PSM</span></span>
- <span data-ttu-id="6cb99-163">.PWD</span><span class="sxs-lookup"><span data-stu-id="6cb99-163">.PWD</span></span>
- <span data-ttu-id="6cb99-164">.SLD\*</span><span class="sxs-lookup"><span data-stu-id="6cb99-164">.SLD\*</span></span>
- <span data-ttu-id="6cb99-165">.STEP</span><span class="sxs-lookup"><span data-stu-id="6cb99-165">.STEP</span></span>
- <span data-ttu-id="6cb99-166">.STL</span><span class="sxs-lookup"><span data-stu-id="6cb99-166">.STL</span></span>
- <span data-ttu-id="6cb99-167">.STP</span><span class="sxs-lookup"><span data-stu-id="6cb99-167">.STP</span></span>
- <span data-ttu-id="6cb99-168">.U3D</span><span class="sxs-lookup"><span data-stu-id="6cb99-168">.U3D</span></span>
- <span data-ttu-id="6cb99-169">.UNV</span><span class="sxs-lookup"><span data-stu-id="6cb99-169">.UNV</span></span>
- <span data-ttu-id="6cb99-170">.VRML</span><span class="sxs-lookup"><span data-stu-id="6cb99-170">.VRML</span></span>
- <span data-ttu-id="6cb99-171">.WRL</span><span class="sxs-lookup"><span data-stu-id="6cb99-171">.WRL</span></span>
- <span data-ttu-id="6cb99-172">.X_\*</span><span class="sxs-lookup"><span data-stu-id="6cb99-172">.X_\*</span></span>
- <span data-ttu-id="6cb99-173">.XAS</span><span class="sxs-lookup"><span data-stu-id="6cb99-173">.XAS</span></span>
- <span data-ttu-id="6cb99-174">.XMT\*</span><span class="sxs-lookup"><span data-stu-id="6cb99-174">.XMT\*</span></span>
- <span data-ttu-id="6cb99-175">.XPR</span><span class="sxs-lookup"><span data-stu-id="6cb99-175">.XPR</span></span>

## <a name="retain-image-files"></a><span data-ttu-id="6cb99-176">Conserva file di immagine</span><span class="sxs-lookup"><span data-stu-id="6cb99-176">Retain image files</span></span>

<span data-ttu-id="6cb99-177">Questo consiglio viene visualizzato quando viene rilevato uno qualsiasi dei seguenti tipi di file in SharePoint o OneDrive.</span><span class="sxs-lookup"><span data-stu-id="6cb99-177">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="6cb99-178">.JPEG</span><span class="sxs-lookup"><span data-stu-id="6cb99-178">.JPEG</span></span>
- <span data-ttu-id="6cb99-179">.GIF</span><span class="sxs-lookup"><span data-stu-id="6cb99-179">.GIF</span></span>
- <span data-ttu-id="6cb99-180">.TIF\*</span><span class="sxs-lookup"><span data-stu-id="6cb99-180">.TIF\*</span></span>
- <span data-ttu-id="6cb99-181">.BMP</span><span class="sxs-lookup"><span data-stu-id="6cb99-181">.BMP</span></span>
- <span data-ttu-id="6cb99-182">.PNG</span><span class="sxs-lookup"><span data-stu-id="6cb99-182">.PNG</span></span>
- <span data-ttu-id="6cb99-183">.RAW</span><span class="sxs-lookup"><span data-stu-id="6cb99-183">.RAW</span></span>
- <span data-ttu-id="6cb99-184">.PSD</span><span class="sxs-lookup"><span data-stu-id="6cb99-184">.PSD</span></span>
- <span data-ttu-id="6cb99-185">.PSP</span><span class="sxs-lookup"><span data-stu-id="6cb99-185">.PSP</span></span>
- <span data-ttu-id="6cb99-186">.JPG</span><span class="sxs-lookup"><span data-stu-id="6cb99-186">.JPG</span></span>
- <span data-ttu-id="6cb99-187">.EXIF</span><span class="sxs-lookup"><span data-stu-id="6cb99-187">.EXIF</span></span>
- <span data-ttu-id="6cb99-188">.PPM</span><span class="sxs-lookup"><span data-stu-id="6cb99-188">.PPM</span></span>
- <span data-ttu-id="6cb99-189">.PGM</span><span class="sxs-lookup"><span data-stu-id="6cb99-189">.PGM</span></span>
- <span data-ttu-id="6cb99-190">.PBM</span><span class="sxs-lookup"><span data-stu-id="6cb99-190">.PBM</span></span>
- <span data-ttu-id="6cb99-191">.PNM</span><span class="sxs-lookup"><span data-stu-id="6cb99-191">.PNM</span></span>
- <span data-ttu-id="6cb99-192">.WEBP</span><span class="sxs-lookup"><span data-stu-id="6cb99-192">.WEBP</span></span>

## <a name="retain-nda-content"></a><span data-ttu-id="6cb99-193">Conserva i contenuti con accordo di riservatezza</span><span class="sxs-lookup"><span data-stu-id="6cb99-193">Retain NDA content</span></span> 

<span data-ttu-id="6cb99-194">Questo consiglio viene visualizzato quando è soddisfatto uno dei criteri seguenti.</span><span class="sxs-lookup"><span data-stu-id="6cb99-194">This recommendation appears when either of the following criteria are met.</span></span>

- <span data-ttu-id="6cb99-195">Nel corpo del messaggio di posta elettronica viene rilevata una qualsiasi combinazione di queste parole chiave:</span><span class="sxs-lookup"><span data-stu-id="6cb99-195">Any of combination of these keywords is detected in the body of an email message:</span></span>
    - <span data-ttu-id="6cb99-196">Accordo di riservatezza</span><span class="sxs-lookup"><span data-stu-id="6cb99-196">NDA</span></span>
    - <span data-ttu-id="6cb99-197">"Accordo di riservatezza"</span><span class="sxs-lookup"><span data-stu-id="6cb99-197">“Non-Disclosure Agreement”</span></span>
    - <span data-ttu-id="6cb99-198">"Accordo riservatezza"</span><span class="sxs-lookup"><span data-stu-id="6cb99-198">“Non Disclosure Agreement”</span></span>

- <span data-ttu-id="6cb99-199">Nei file PDF o DOC in SharePoint o OneDrive viene rilevata una qualsiasi combinazione di queste parole chiave:</span><span class="sxs-lookup"><span data-stu-id="6cb99-199">Any combination of these keywords are detected in .PDF or .DOC files in SharePoint or OneDrive:</span></span>
    - <span data-ttu-id="6cb99-200">Accordo di riservatezza</span><span class="sxs-lookup"><span data-stu-id="6cb99-200">NDA</span></span>
    - <span data-ttu-id="6cb99-201">Accordo riservatezza</span><span class="sxs-lookup"><span data-stu-id="6cb99-201">Non Disclosure Agreement</span></span>

## <a name="retain-software-development-files"></a><span data-ttu-id="6cb99-202">Conserva i file di sviluppo software</span><span class="sxs-lookup"><span data-stu-id="6cb99-202">Retain software development files</span></span>

<span data-ttu-id="6cb99-203">Questo consiglio viene visualizzato quando viene rilevato uno qualsiasi dei seguenti tipi di file in SharePoint o OneDrive.</span><span class="sxs-lookup"><span data-stu-id="6cb99-203">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="6cb99-204">.ASAX</span><span class="sxs-lookup"><span data-stu-id="6cb99-204">.ASAX</span></span>
- <span data-ttu-id="6cb99-205">.ASM</span><span class="sxs-lookup"><span data-stu-id="6cb99-205">.ASM</span></span>
- <span data-ttu-id="6cb99-206">.ASP\*</span><span class="sxs-lookup"><span data-stu-id="6cb99-206">.ASP\*</span></span>
- <span data-ttu-id="6cb99-207">.BAT</span><span class="sxs-lookup"><span data-stu-id="6cb99-207">.BAT</span></span>
- <span data-ttu-id="6cb99-208">.CONFIG</span><span class="sxs-lookup"><span data-stu-id="6cb99-208">.CONFIG</span></span>
- <span data-ttu-id="6cb99-209">.CS</span><span class="sxs-lookup"><span data-stu-id="6cb99-209">.CS</span></span>
- <span data-ttu-id="6cb99-210">.CSS</span><span class="sxs-lookup"><span data-stu-id="6cb99-210">.CSS</span></span>
- <span data-ttu-id="6cb99-211">.DISCO</span><span class="sxs-lookup"><span data-stu-id="6cb99-211">.DISCO</span></span>
- <span data-ttu-id="6cb99-212">.HTM\*</span><span class="sxs-lookup"><span data-stu-id="6cb99-212">.HTM\*</span></span>
- <span data-ttu-id="6cb99-213">.INC</span><span class="sxs-lookup"><span data-stu-id="6cb99-213">.INC</span></span>
- <span data-ttu-id="6cb99-214">.JAD</span><span class="sxs-lookup"><span data-stu-id="6cb99-214">.JAD</span></span>
- <span data-ttu-id="6cb99-215">.JAVA</span><span class="sxs-lookup"><span data-stu-id="6cb99-215">.JAVA</span></span>
- <span data-ttu-id="6cb99-216">.JS\*</span><span class="sxs-lookup"><span data-stu-id="6cb99-216">.JS\*</span></span>
- <span data-ttu-id="6cb99-217">.LIB</span><span class="sxs-lookup"><span data-stu-id="6cb99-217">.LIB</span></span>
- <span data-ttu-id="6cb99-218">.O</span><span class="sxs-lookup"><span data-stu-id="6cb99-218">.O</span></span>
- <span data-ttu-id="6cb99-219">.PHP</span><span class="sxs-lookup"><span data-stu-id="6cb99-219">.PHP</span></span>
- <span data-ttu-id="6cb99-220">.RC</span><span class="sxs-lookup"><span data-stu-id="6cb99-220">.RC</span></span>
- <span data-ttu-id="6cb99-221">.RESX</span><span class="sxs-lookup"><span data-stu-id="6cb99-221">.RESX</span></span>
- <span data-ttu-id="6cb99-222">.RPT</span><span class="sxs-lookup"><span data-stu-id="6cb99-222">.RPT</span></span>
- <span data-ttu-id="6cb99-223">.RSS</span><span class="sxs-lookup"><span data-stu-id="6cb99-223">.RSS</span></span>
- <span data-ttu-id="6cb99-224">.SCPT</span><span class="sxs-lookup"><span data-stu-id="6cb99-224">.SCPT</span></span>
- <span data-ttu-id="6cb99-225">.SRC</span><span class="sxs-lookup"><span data-stu-id="6cb99-225">.SRC</span></span>
- <span data-ttu-id="6cb99-226">.VB\*</span><span class="sxs-lookup"><span data-stu-id="6cb99-226">.VB\*</span></span>
- <span data-ttu-id="6cb99-227">.WSF</span><span class="sxs-lookup"><span data-stu-id="6cb99-227">.WSF</span></span>
- <span data-ttu-id="6cb99-228">.XCODEPROJ</span><span class="sxs-lookup"><span data-stu-id="6cb99-228">.XCODEPROJ</span></span>
- <span data-ttu-id="6cb99-229">.XML</span><span class="sxs-lookup"><span data-stu-id="6cb99-229">.XML</span></span>
- <span data-ttu-id="6cb99-230">.XSD</span><span class="sxs-lookup"><span data-stu-id="6cb99-230">.XSD</span></span>
- <span data-ttu-id="6cb99-231">.XSL\*</span><span class="sxs-lookup"><span data-stu-id="6cb99-231">.XSL\*</span></span>

## <a name="retain-video-files"></a><span data-ttu-id="6cb99-232">Conserva i file video</span><span class="sxs-lookup"><span data-stu-id="6cb99-232">Retain video files</span></span>

<span data-ttu-id="6cb99-233">Questo consiglio viene visualizzato quando viene rilevato uno qualsiasi dei seguenti tipi di file in SharePoint o OneDrive.</span><span class="sxs-lookup"><span data-stu-id="6cb99-233">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="6cb99-234">.AVCHD</span><span class="sxs-lookup"><span data-stu-id="6cb99-234">.AVCHD</span></span>
- <span data-ttu-id="6cb99-235">.AVI</span><span class="sxs-lookup"><span data-stu-id="6cb99-235">.AVI</span></span>
- <span data-ttu-id="6cb99-236">.FLV</span><span class="sxs-lookup"><span data-stu-id="6cb99-236">.FLV</span></span>
- <span data-ttu-id="6cb99-237">.MOV</span><span class="sxs-lookup"><span data-stu-id="6cb99-237">.MOV</span></span>
- <span data-ttu-id="6cb99-238">.MP2V</span><span class="sxs-lookup"><span data-stu-id="6cb99-238">.MP2V</span></span>
- <span data-ttu-id="6cb99-239">.MP4</span><span class="sxs-lookup"><span data-stu-id="6cb99-239">.MP4</span></span>
- <span data-ttu-id="6cb99-240">.MP4V</span><span class="sxs-lookup"><span data-stu-id="6cb99-240">.MP4V</span></span>
- <span data-ttu-id="6cb99-241">.MPE</span><span class="sxs-lookup"><span data-stu-id="6cb99-241">.MPE</span></span>
- <span data-ttu-id="6cb99-242">.MPEG</span><span class="sxs-lookup"><span data-stu-id="6cb99-242">.MPEG</span></span>
- <span data-ttu-id="6cb99-243">.MPEG1</span><span class="sxs-lookup"><span data-stu-id="6cb99-243">.MPEG1</span></span>
- <span data-ttu-id="6cb99-244">.MPEG2</span><span class="sxs-lookup"><span data-stu-id="6cb99-244">.MPEG2</span></span>
- <span data-ttu-id="6cb99-245">.MPEG4</span><span class="sxs-lookup"><span data-stu-id="6cb99-245">.MPEG4</span></span>
- <span data-ttu-id="6cb99-246">.MPG</span><span class="sxs-lookup"><span data-stu-id="6cb99-246">.MPG</span></span>
- <span data-ttu-id="6cb99-247">.MPG2</span><span class="sxs-lookup"><span data-stu-id="6cb99-247">.MPG2</span></span>
- <span data-ttu-id="6cb99-248">.MPG4</span><span class="sxs-lookup"><span data-stu-id="6cb99-248">.MPG4</span></span>
- <span data-ttu-id="6cb99-249">.WMV</span><span class="sxs-lookup"><span data-stu-id="6cb99-249">.WMV</span></span>
- <span data-ttu-id="6cb99-250">.XMV</span><span class="sxs-lookup"><span data-stu-id="6cb99-250">.XMV</span></span>
