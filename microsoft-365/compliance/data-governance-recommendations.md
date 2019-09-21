---
title: Come viene identificato il contenuto per i consigli sulla governance dei dati
ms.author: brendonb
author: stephow-MSFT
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
ms.openlocfilehash: 3d96b7c15d5b6a0f6ec3bbf467bd8a1099af559a
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37083004"
---
# <a name="how-content-is-identified-for-data-governance-recommendations"></a><span data-ttu-id="2cd0b-106">Come viene identificato il contenuto per i consigli sulla governance dei dati</span><span class="sxs-lookup"><span data-stu-id="2cd0b-106">How content is identified for data-governance recommendations</span></span>

<span data-ttu-id="2cd0b-p102">Il Centro sicurezza e conformità di Office 365 fornisce consigli per la governance dei dati in base alla configurazione corrente dell'organizzazione e consente di impostare le opzioni necessarie con pochi clic. Alcuni di questi consigli rilevano specifici contenuti nell'organizzazione e propongono le azioni consigliate per gestirli. Ad esempio, un consiglio potrebbe rilevare elementi che includono contenuti di importanza strategica, come informazioni sul privilegio avvocato-cliente o su un accordo di riservatezza, e quindi consentire l'applicazione automatica di un'etichetta di conservazione a tali elementi per assicurare che vengano opportunamente classificati e conservati.</span><span class="sxs-lookup"><span data-stu-id="2cd0b-p102">The Office 365 Security & Compliance Center provides recommendations for data governance based on your org's current setup and lets you set things up in a couple clicks. Some of these recommendations detect specific content in your organization and then provide recommended steps for managing that content. For example, a recommendation might detect items that contain business-critical content (such as attorney-client privilege or NDA info), and then let you automatically apply a retention label to those items to ensure that they’re classified and retained as needed.</span></span>

<span data-ttu-id="2cd0b-110">Questo argomento fornisce un elenco dei consigli sulla governance dei dati che possono essere visualizzati e descrive il contenuto che viene rilevato per attivare ciascuno di essi.</span><span class="sxs-lookup"><span data-stu-id="2cd0b-110">This topic lists the data-governance recommendations you might see and describes what content is detected to trigger each one.</span></span>

## <a name="clean-up-voicemail"></a><span data-ttu-id="2cd0b-111">Pulisci la segreteria telefonica</span><span class="sxs-lookup"><span data-stu-id="2cd0b-111">Clean up voicemail</span></span>

<span data-ttu-id="2cd0b-p103">Questo consiglio viene visualizzato quando nelle cassette postali degli utenti vengono rilevati messaggi di posta elettronica identificati come messaggi di tipo ‘postavocale’. Per saperne di più, vedere l'argomento relativo alle [proprietà dei messaggi in Exchange](https://docs.microsoft.com/it-IT/exchange/policy-and-compliance/ediscovery/message-properties-and-search-operators?view=exchserver-2019#searchable-properties-in-exchange).</span><span class="sxs-lookup"><span data-stu-id="2cd0b-p103">This recommendation appears when email messages identified as the message type ‘voicemail’ are detected in users’ mailboxes. Learn more about [message properties in Exchange](https://docs.microsoft.com/en-us/exchange/policy-and-compliance/ediscovery/message-properties-and-search-operators?view=exchserver-2019#searchable-properties-in-exchange).</span></span>

## <a name="label-attorney-client-privilege-content"></a><span data-ttu-id="2cd0b-114">Applica etichetta ai contenuti coperti da privilegio avvocato-cliente</span><span class="sxs-lookup"><span data-stu-id="2cd0b-114">Label attorney-client privilege content</span></span> 

<span data-ttu-id="2cd0b-115">Questo consiglio viene visualizzato quando è soddisfatto uno dei criteri seguenti.</span><span class="sxs-lookup"><span data-stu-id="2cd0b-115">This recommendation appears when either of the following criteria are met.</span></span>

- <span data-ttu-id="2cd0b-116">Nel corpo del messaggio di posta elettronica viene rilevata una qualsiasi combinazione di queste parole chiave:</span><span class="sxs-lookup"><span data-stu-id="2cd0b-116">Any of combination of these keywords is detected in the body of an email message:</span></span>
    - <span data-ttu-id="2cd0b-117">PAC</span><span class="sxs-lookup"><span data-stu-id="2cd0b-117">ACP</span></span>
    - <span data-ttu-id="2cd0b-118">Privilegio avvocato cliente</span><span class="sxs-lookup"><span data-stu-id="2cd0b-118">Attorney Client Privilege</span></span>
    - <span data-ttu-id="2cd0b-119">Privilegio avvocato-cliente</span><span class="sxs-lookup"><span data-stu-id="2cd0b-119">Attorney-Client Privilege</span></span>
    - <span data-ttu-id="2cd0b-120">Coperto dal privilegio avvocato-cliente</span><span class="sxs-lookup"><span data-stu-id="2cd0b-120">Attorney-Client Privileged</span></span>

- <span data-ttu-id="2cd0b-121">Nei file di SharePoint o OneDrive viene rilevata una qualsiasi combinazione di queste parole chiave:</span><span class="sxs-lookup"><span data-stu-id="2cd0b-121">Any combination of these keywords are detected in SharePoint or OneDrive files:</span></span>
    - <span data-ttu-id="2cd0b-122">PAC</span><span class="sxs-lookup"><span data-stu-id="2cd0b-122">ACP</span></span>
    - <span data-ttu-id="2cd0b-123">Privilegio avvocato-cliente\*</span><span class="sxs-lookup"><span data-stu-id="2cd0b-123">Attorney Client Privilege\*</span></span>
    - <span data-ttu-id="2cd0b-124">Privilegio AC</span><span class="sxs-lookup"><span data-stu-id="2cd0b-124">AC Privilege</span></span>

## <a name="retain-audio-files"></a><span data-ttu-id="2cd0b-125">Conserva file audio</span><span class="sxs-lookup"><span data-stu-id="2cd0b-125">Retain audio files</span></span>

<span data-ttu-id="2cd0b-126">Questo consiglio viene visualizzato quando viene rilevato uno qualsiasi dei seguenti tipi di file in SharePoint o OneDrive.</span><span class="sxs-lookup"><span data-stu-id="2cd0b-126">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="2cd0b-127">.MP3</span><span class="sxs-lookup"><span data-stu-id="2cd0b-127">.MP3</span></span>
- <span data-ttu-id="2cd0b-128">.WMA</span><span class="sxs-lookup"><span data-stu-id="2cd0b-128">.WMA</span></span>
- <span data-ttu-id="2cd0b-129">.WAV</span><span class="sxs-lookup"><span data-stu-id="2cd0b-129">.WAV</span></span>
- <span data-ttu-id="2cd0b-130">.RA</span><span class="sxs-lookup"><span data-stu-id="2cd0b-130">.RA</span></span>
- <span data-ttu-id="2cd0b-131">.RAM</span><span class="sxs-lookup"><span data-stu-id="2cd0b-131">.RAM</span></span>
- <span data-ttu-id="2cd0b-132">.RM</span><span class="sxs-lookup"><span data-stu-id="2cd0b-132">.RM</span></span>
- <span data-ttu-id="2cd0b-133">.MID</span><span class="sxs-lookup"><span data-stu-id="2cd0b-133">.MID</span></span>
- <span data-ttu-id="2cd0b-134">.OGG</span><span class="sxs-lookup"><span data-stu-id="2cd0b-134">.OGG</span></span>
- <span data-ttu-id="2cd0b-135">.AIFF</span><span class="sxs-lookup"><span data-stu-id="2cd0b-135">.AIFF</span></span>
- <span data-ttu-id="2cd0b-136">.PCM</span><span class="sxs-lookup"><span data-stu-id="2cd0b-136">.PCM</span></span>
- <span data-ttu-id="2cd0b-137">.AAC</span><span class="sxs-lookup"><span data-stu-id="2cd0b-137">.AAC</span></span>
- <span data-ttu-id="2cd0b-138">.FLAC</span><span class="sxs-lookup"><span data-stu-id="2cd0b-138">.FLAC</span></span>
- <span data-ttu-id="2cd0b-139">.ALAC</span><span class="sxs-lookup"><span data-stu-id="2cd0b-139">.ALAC</span></span>

## <a name="retain-cad-files"></a><span data-ttu-id="2cd0b-140">Conserva file CAD</span><span class="sxs-lookup"><span data-stu-id="2cd0b-140">Retain CAD files</span></span>

<span data-ttu-id="2cd0b-141">Questo consiglio viene visualizzato quando viene rilevato uno qualsiasi dei seguenti tipi di file in SharePoint o OneDrive.</span><span class="sxs-lookup"><span data-stu-id="2cd0b-141">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="2cd0b-142">.3DXML</span><span class="sxs-lookup"><span data-stu-id="2cd0b-142">.3DXML</span></span>
- <span data-ttu-id="2cd0b-143">.ACIS</span><span class="sxs-lookup"><span data-stu-id="2cd0b-143">.ACIS</span></span>
- <span data-ttu-id="2cd0b-144">.ARC</span><span class="sxs-lookup"><span data-stu-id="2cd0b-144">.ARC</span></span>
- <span data-ttu-id="2cd0b-145">.ASM</span><span class="sxs-lookup"><span data-stu-id="2cd0b-145">.ASM</span></span>
- <span data-ttu-id="2cd0b-146">.CAT\*</span><span class="sxs-lookup"><span data-stu-id="2cd0b-146">.CAT\*</span></span>
- <span data-ttu-id="2cd0b-147">.CGR</span><span class="sxs-lookup"><span data-stu-id="2cd0b-147">.CGR</span></span>
- <span data-ttu-id="2cd0b-148">.DW\*</span><span class="sxs-lookup"><span data-stu-id="2cd0b-148">.DW\*</span></span>
- <span data-ttu-id="2cd0b-149">.DX\*</span><span class="sxs-lookup"><span data-stu-id="2cd0b-149">.DX\*</span></span>
- <span data-ttu-id="2cd0b-150">.EDRW</span><span class="sxs-lookup"><span data-stu-id="2cd0b-150">.EDRW</span></span>
- <span data-ttu-id="2cd0b-151">.IAM</span><span class="sxs-lookup"><span data-stu-id="2cd0b-151">.IAM</span></span>
- <span data-ttu-id="2cd0b-152">.IGES</span><span class="sxs-lookup"><span data-stu-id="2cd0b-152">.IGES</span></span>
- <span data-ttu-id="2cd0b-153">.IGS</span><span class="sxs-lookup"><span data-stu-id="2cd0b-153">.IGS</span></span>
- <span data-ttu-id="2cd0b-154">.IPT</span><span class="sxs-lookup"><span data-stu-id="2cd0b-154">.IPT</span></span>
- <span data-ttu-id="2cd0b-155">.JT</span><span class="sxs-lookup"><span data-stu-id="2cd0b-155">.JT</span></span>
- <span data-ttu-id="2cd0b-156">.MF1</span><span class="sxs-lookup"><span data-stu-id="2cd0b-156">.MF1</span></span>
- <span data-ttu-id="2cd0b-157">.NEU</span><span class="sxs-lookup"><span data-stu-id="2cd0b-157">.NEU</span></span>
- <span data-ttu-id="2cd0b-158">.PAR</span><span class="sxs-lookup"><span data-stu-id="2cd0b-158">.PAR</span></span>
- <span data-ttu-id="2cd0b-159">.PKG</span><span class="sxs-lookup"><span data-stu-id="2cd0b-159">.PKG</span></span>
- <span data-ttu-id="2cd0b-160">.PRC</span><span class="sxs-lookup"><span data-stu-id="2cd0b-160">.PRC</span></span>
- <span data-ttu-id="2cd0b-161">.PRT</span><span class="sxs-lookup"><span data-stu-id="2cd0b-161">.PRT</span></span>
- <span data-ttu-id="2cd0b-162">.PSM</span><span class="sxs-lookup"><span data-stu-id="2cd0b-162">.PSM</span></span>
- <span data-ttu-id="2cd0b-163">.PWD</span><span class="sxs-lookup"><span data-stu-id="2cd0b-163">.PWD</span></span>
- <span data-ttu-id="2cd0b-164">.SLD\*</span><span class="sxs-lookup"><span data-stu-id="2cd0b-164">.SLD\*</span></span>
- <span data-ttu-id="2cd0b-165">.STEP</span><span class="sxs-lookup"><span data-stu-id="2cd0b-165">.STEP</span></span>
- <span data-ttu-id="2cd0b-166">.STL</span><span class="sxs-lookup"><span data-stu-id="2cd0b-166">.STL</span></span>
- <span data-ttu-id="2cd0b-167">.STP</span><span class="sxs-lookup"><span data-stu-id="2cd0b-167">.STP</span></span>
- <span data-ttu-id="2cd0b-168">.U3D</span><span class="sxs-lookup"><span data-stu-id="2cd0b-168">.U3D</span></span>
- <span data-ttu-id="2cd0b-169">.UNV</span><span class="sxs-lookup"><span data-stu-id="2cd0b-169">.UNV</span></span>
- <span data-ttu-id="2cd0b-170">.VRML</span><span class="sxs-lookup"><span data-stu-id="2cd0b-170">.VRML</span></span>
- <span data-ttu-id="2cd0b-171">.WRL</span><span class="sxs-lookup"><span data-stu-id="2cd0b-171">.WRL</span></span>
- <span data-ttu-id="2cd0b-172">.X_\*</span><span class="sxs-lookup"><span data-stu-id="2cd0b-172">.X_\*</span></span>
- <span data-ttu-id="2cd0b-173">.XAS</span><span class="sxs-lookup"><span data-stu-id="2cd0b-173">.XAS</span></span>
- <span data-ttu-id="2cd0b-174">.XMT\*</span><span class="sxs-lookup"><span data-stu-id="2cd0b-174">.XMT\*</span></span>
- <span data-ttu-id="2cd0b-175">.XPR</span><span class="sxs-lookup"><span data-stu-id="2cd0b-175">.XPR</span></span>

## <a name="retain-image-files"></a><span data-ttu-id="2cd0b-176">Conserva file di immagine</span><span class="sxs-lookup"><span data-stu-id="2cd0b-176">Retain image files</span></span>

<span data-ttu-id="2cd0b-177">Questo consiglio viene visualizzato quando viene rilevato uno qualsiasi dei seguenti tipi di file in SharePoint o OneDrive.</span><span class="sxs-lookup"><span data-stu-id="2cd0b-177">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="2cd0b-178">.JPEG</span><span class="sxs-lookup"><span data-stu-id="2cd0b-178">.JPEG</span></span>
- <span data-ttu-id="2cd0b-179">.GIF</span><span class="sxs-lookup"><span data-stu-id="2cd0b-179">.GIF</span></span>
- <span data-ttu-id="2cd0b-180">.TIF\*</span><span class="sxs-lookup"><span data-stu-id="2cd0b-180">.TIF\*</span></span>
- <span data-ttu-id="2cd0b-181">.BMP</span><span class="sxs-lookup"><span data-stu-id="2cd0b-181">.BMP</span></span>
- <span data-ttu-id="2cd0b-182">.PNG</span><span class="sxs-lookup"><span data-stu-id="2cd0b-182">.PNG</span></span>
- <span data-ttu-id="2cd0b-183">.RAW</span><span class="sxs-lookup"><span data-stu-id="2cd0b-183">.RAW</span></span>
- <span data-ttu-id="2cd0b-184">.PSD</span><span class="sxs-lookup"><span data-stu-id="2cd0b-184">.PSD</span></span>
- <span data-ttu-id="2cd0b-185">.PSP</span><span class="sxs-lookup"><span data-stu-id="2cd0b-185">.PSP</span></span>
- <span data-ttu-id="2cd0b-186">.JPG</span><span class="sxs-lookup"><span data-stu-id="2cd0b-186">.JPG</span></span>
- <span data-ttu-id="2cd0b-187">.EXIF</span><span class="sxs-lookup"><span data-stu-id="2cd0b-187">.EXIF</span></span>
- <span data-ttu-id="2cd0b-188">.PPM</span><span class="sxs-lookup"><span data-stu-id="2cd0b-188">.PPM</span></span>
- <span data-ttu-id="2cd0b-189">.PGM</span><span class="sxs-lookup"><span data-stu-id="2cd0b-189">.PGM</span></span>
- <span data-ttu-id="2cd0b-190">.PBM</span><span class="sxs-lookup"><span data-stu-id="2cd0b-190">.PBM</span></span>
- <span data-ttu-id="2cd0b-191">.PNM</span><span class="sxs-lookup"><span data-stu-id="2cd0b-191">.PNM</span></span>
- <span data-ttu-id="2cd0b-192">.WEBP</span><span class="sxs-lookup"><span data-stu-id="2cd0b-192">.WEBP</span></span>

## <a name="retain-nda-content"></a><span data-ttu-id="2cd0b-193">Conserva i contenuti con accordo di riservatezza</span><span class="sxs-lookup"><span data-stu-id="2cd0b-193">Retain NDA content</span></span> 

<span data-ttu-id="2cd0b-194">Questo consiglio viene visualizzato quando è soddisfatto uno dei criteri seguenti.</span><span class="sxs-lookup"><span data-stu-id="2cd0b-194">This recommendation appears when either of the following criteria are met.</span></span>

- <span data-ttu-id="2cd0b-195">Nel corpo del messaggio di posta elettronica viene rilevata una qualsiasi combinazione di queste parole chiave:</span><span class="sxs-lookup"><span data-stu-id="2cd0b-195">Any of combination of these keywords is detected in the body of an email message:</span></span>
    - <span data-ttu-id="2cd0b-196">Accordo di riservatezza</span><span class="sxs-lookup"><span data-stu-id="2cd0b-196">NDA</span></span>
    - <span data-ttu-id="2cd0b-197">"Accordo di riservatezza"</span><span class="sxs-lookup"><span data-stu-id="2cd0b-197">“Non-Disclosure Agreement”</span></span>
    - <span data-ttu-id="2cd0b-198">"Accordo riservatezza"</span><span class="sxs-lookup"><span data-stu-id="2cd0b-198">“Non Disclosure Agreement”</span></span>

- <span data-ttu-id="2cd0b-199">Nei file PDF o DOC in SharePoint o OneDrive viene rilevata una qualsiasi combinazione di queste parole chiave:</span><span class="sxs-lookup"><span data-stu-id="2cd0b-199">Any combination of these keywords are detected in .PDF or .DOC files in SharePoint or OneDrive:</span></span>
    - <span data-ttu-id="2cd0b-200">Accordo di riservatezza</span><span class="sxs-lookup"><span data-stu-id="2cd0b-200">NDA</span></span>
    - <span data-ttu-id="2cd0b-201">Accordo riservatezza</span><span class="sxs-lookup"><span data-stu-id="2cd0b-201">Non Disclosure Agreement</span></span>

## <a name="retain-software-development-files"></a><span data-ttu-id="2cd0b-202">Conserva i file di sviluppo software</span><span class="sxs-lookup"><span data-stu-id="2cd0b-202">Retain software development files</span></span>

<span data-ttu-id="2cd0b-203">Questo consiglio viene visualizzato quando viene rilevato uno qualsiasi dei seguenti tipi di file in SharePoint o OneDrive.</span><span class="sxs-lookup"><span data-stu-id="2cd0b-203">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="2cd0b-204">.ASAX</span><span class="sxs-lookup"><span data-stu-id="2cd0b-204">.ASAX</span></span>
- <span data-ttu-id="2cd0b-205">.ASM</span><span class="sxs-lookup"><span data-stu-id="2cd0b-205">.ASM</span></span>
- <span data-ttu-id="2cd0b-206">.ASP\*</span><span class="sxs-lookup"><span data-stu-id="2cd0b-206">.ASP\*</span></span>
- <span data-ttu-id="2cd0b-207">.BAT</span><span class="sxs-lookup"><span data-stu-id="2cd0b-207">.BAT</span></span>
- <span data-ttu-id="2cd0b-208">.CONFIG</span><span class="sxs-lookup"><span data-stu-id="2cd0b-208">.CONFIG</span></span>
- <span data-ttu-id="2cd0b-209">.CS</span><span class="sxs-lookup"><span data-stu-id="2cd0b-209">.CS</span></span>
- <span data-ttu-id="2cd0b-210">.CSS</span><span class="sxs-lookup"><span data-stu-id="2cd0b-210">.CSS</span></span>
- <span data-ttu-id="2cd0b-211">.DISCO</span><span class="sxs-lookup"><span data-stu-id="2cd0b-211">.DISCO</span></span>
- <span data-ttu-id="2cd0b-212">.HTM\*</span><span class="sxs-lookup"><span data-stu-id="2cd0b-212">.HTM\*</span></span>
- <span data-ttu-id="2cd0b-213">.INC</span><span class="sxs-lookup"><span data-stu-id="2cd0b-213">.INC</span></span>
- <span data-ttu-id="2cd0b-214">.JAD</span><span class="sxs-lookup"><span data-stu-id="2cd0b-214">.JAD</span></span>
- <span data-ttu-id="2cd0b-215">.JAVA</span><span class="sxs-lookup"><span data-stu-id="2cd0b-215">.JAVA</span></span>
- <span data-ttu-id="2cd0b-216">.JS\*</span><span class="sxs-lookup"><span data-stu-id="2cd0b-216">.JS\*</span></span>
- <span data-ttu-id="2cd0b-217">.LIB</span><span class="sxs-lookup"><span data-stu-id="2cd0b-217">.LIB</span></span>
- <span data-ttu-id="2cd0b-218">.O</span><span class="sxs-lookup"><span data-stu-id="2cd0b-218">.O</span></span>
- <span data-ttu-id="2cd0b-219">.PHP</span><span class="sxs-lookup"><span data-stu-id="2cd0b-219">.PHP</span></span>
- <span data-ttu-id="2cd0b-220">.RC</span><span class="sxs-lookup"><span data-stu-id="2cd0b-220">.RC</span></span>
- <span data-ttu-id="2cd0b-221">.RESX</span><span class="sxs-lookup"><span data-stu-id="2cd0b-221">.RESX</span></span>
- <span data-ttu-id="2cd0b-222">.RPT</span><span class="sxs-lookup"><span data-stu-id="2cd0b-222">.RPT</span></span>
- <span data-ttu-id="2cd0b-223">.RSS</span><span class="sxs-lookup"><span data-stu-id="2cd0b-223">.RSS</span></span>
- <span data-ttu-id="2cd0b-224">.SCPT</span><span class="sxs-lookup"><span data-stu-id="2cd0b-224">.SCPT</span></span>
- <span data-ttu-id="2cd0b-225">.SRC</span><span class="sxs-lookup"><span data-stu-id="2cd0b-225">.SRC</span></span>
- <span data-ttu-id="2cd0b-226">.VB\*</span><span class="sxs-lookup"><span data-stu-id="2cd0b-226">.VB\*</span></span>
- <span data-ttu-id="2cd0b-227">.WSF</span><span class="sxs-lookup"><span data-stu-id="2cd0b-227">.WSF</span></span>
- <span data-ttu-id="2cd0b-228">.XCODEPROJ</span><span class="sxs-lookup"><span data-stu-id="2cd0b-228">.XCODEPROJ</span></span>
- <span data-ttu-id="2cd0b-229">.XML</span><span class="sxs-lookup"><span data-stu-id="2cd0b-229">.XML</span></span>
- <span data-ttu-id="2cd0b-230">.XSD</span><span class="sxs-lookup"><span data-stu-id="2cd0b-230">.XSD</span></span>
- <span data-ttu-id="2cd0b-231">.XSL\*</span><span class="sxs-lookup"><span data-stu-id="2cd0b-231">.XSL\*</span></span>

## <a name="retain-video-files"></a><span data-ttu-id="2cd0b-232">Conserva i file video</span><span class="sxs-lookup"><span data-stu-id="2cd0b-232">Retain video files</span></span>

<span data-ttu-id="2cd0b-233">Questo consiglio viene visualizzato quando viene rilevato uno qualsiasi dei seguenti tipi di file in SharePoint o OneDrive.</span><span class="sxs-lookup"><span data-stu-id="2cd0b-233">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="2cd0b-234">.AVCHD</span><span class="sxs-lookup"><span data-stu-id="2cd0b-234">.AVCHD</span></span>
- <span data-ttu-id="2cd0b-235">.AVI</span><span class="sxs-lookup"><span data-stu-id="2cd0b-235">.AVI</span></span>
- <span data-ttu-id="2cd0b-236">.FLV</span><span class="sxs-lookup"><span data-stu-id="2cd0b-236">.FLV</span></span>
- <span data-ttu-id="2cd0b-237">.MOV</span><span class="sxs-lookup"><span data-stu-id="2cd0b-237">.MOV</span></span>
- <span data-ttu-id="2cd0b-238">.MP2V</span><span class="sxs-lookup"><span data-stu-id="2cd0b-238">.MP2V</span></span>
- <span data-ttu-id="2cd0b-239">.MP4</span><span class="sxs-lookup"><span data-stu-id="2cd0b-239">.MP4</span></span>
- <span data-ttu-id="2cd0b-240">.MP4V</span><span class="sxs-lookup"><span data-stu-id="2cd0b-240">.MP4V</span></span>
- <span data-ttu-id="2cd0b-241">.MPE</span><span class="sxs-lookup"><span data-stu-id="2cd0b-241">.MPE</span></span>
- <span data-ttu-id="2cd0b-242">.MPEG</span><span class="sxs-lookup"><span data-stu-id="2cd0b-242">.MPEG</span></span>
- <span data-ttu-id="2cd0b-243">.MPEG1</span><span class="sxs-lookup"><span data-stu-id="2cd0b-243">.MPEG1</span></span>
- <span data-ttu-id="2cd0b-244">.MPEG2</span><span class="sxs-lookup"><span data-stu-id="2cd0b-244">.MPEG2</span></span>
- <span data-ttu-id="2cd0b-245">.MPEG4</span><span class="sxs-lookup"><span data-stu-id="2cd0b-245">.MPEG4</span></span>
- <span data-ttu-id="2cd0b-246">.MPG</span><span class="sxs-lookup"><span data-stu-id="2cd0b-246">.MPG</span></span>
- <span data-ttu-id="2cd0b-247">.MPG2</span><span class="sxs-lookup"><span data-stu-id="2cd0b-247">.MPG2</span></span>
- <span data-ttu-id="2cd0b-248">.MPG4</span><span class="sxs-lookup"><span data-stu-id="2cd0b-248">.MPG4</span></span>
- <span data-ttu-id="2cd0b-249">.WMV</span><span class="sxs-lookup"><span data-stu-id="2cd0b-249">.WMV</span></span>
- <span data-ttu-id="2cd0b-250">.XMV</span><span class="sxs-lookup"><span data-stu-id="2cd0b-250">.XMV</span></span>
