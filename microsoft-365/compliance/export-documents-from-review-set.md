---
title: Esportare i documenti da un insieme da rivedere
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Informazioni su come selezionare ed esportare il contenuto da un set di revisione per presentazioni o recensioni esterne.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b3be21d4c90c861c83acf612e9aadc373189f7ba
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285362"
---
# <a name="export-documents-from-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="e7c30-103">Esportare documenti da un set di revisione in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="e7c30-103">Export documents from a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="e7c30-104">Export consente agli utenti di personalizzare il contenuto incluso nel pacchetto di download.</span><span class="sxs-lookup"><span data-stu-id="e7c30-104">Export allows users to customize the content that is included in the download package.</span></span> <span data-ttu-id="e7c30-105">Lo strumento di esportazione fornisce una pagina di configurazione con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="e7c30-105">The Export tool provides a configuration page with the following settings:</span></span>

![Opzioni per l'esportazione di elementi da un set di Revisione](../media/bcfc72c7-4a01-4697-9e16-2965b7f04fdb.png)

## <a name="export-options"></a><span data-ttu-id="e7c30-107">Opzioni di esportazione</span><span class="sxs-lookup"><span data-stu-id="e7c30-107">Export options</span></span>

- <span data-ttu-id="e7c30-108">Nome esportazione: nome del processo di esportazione.</span><span class="sxs-lookup"><span data-stu-id="e7c30-108">Export name: Name of the export job.</span></span>

- <span data-ttu-id="e7c30-109">Descrizione: campo di testo libero che consente di aggiungere una descrizione.</span><span class="sxs-lookup"><span data-stu-id="e7c30-109">Description: Free-text field for you to add a description.</span></span>

- <span data-ttu-id="e7c30-110">Esportare questi documenti:</span><span class="sxs-lookup"><span data-stu-id="e7c30-110">Export these documents:</span></span>

  - <span data-ttu-id="e7c30-111">Solo documenti selezionati: consente di esportare solo i documenti attualmente selezionati.</span><span class="sxs-lookup"><span data-stu-id="e7c30-111">Selected documents only - Exports only the documents that are currently selected.</span></span>
  
  - <span data-ttu-id="e7c30-112">Tutti i documenti nel set di revisione-Esporta tutti i documenti nel set di Revisione</span><span class="sxs-lookup"><span data-stu-id="e7c30-112">All documents in the review set - Exports all documents in the review set</span></span>

- <span data-ttu-id="e7c30-113">Metadati</span><span class="sxs-lookup"><span data-stu-id="e7c30-113">Metadata</span></span>
  
  - <span data-ttu-id="e7c30-114">Load file: questo file contiene i metadati per ogni file.</span><span class="sxs-lookup"><span data-stu-id="e7c30-114">Load file - This file contains metadata for each file.</span></span> <span data-ttu-id="e7c30-115">Per ulteriori informazioni sui campi inclusi, vedere [Document Metadata Fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md) .</span><span class="sxs-lookup"><span data-stu-id="e7c30-115">see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md) for more information about what fields are included.</span></span> <span data-ttu-id="e7c30-116">Questo file può in genere essere ingerito da strumenti di eDiscovery di terze parti.</span><span class="sxs-lookup"><span data-stu-id="e7c30-116">This file can typically be ingested by third-party eDiscovery tools.</span></span>
  
  - <span data-ttu-id="e7c30-117">Tag: quando vengono selezionati, le informazioni di tagging verranno incluse nel file di caricamento.</span><span class="sxs-lookup"><span data-stu-id="e7c30-117">Tags - When selected, tagging information will be included in the load file.</span></span>

- <span data-ttu-id="e7c30-118">Contenuto</span><span class="sxs-lookup"><span data-stu-id="e7c30-118">Content</span></span>
  
  - <span data-ttu-id="e7c30-119">File nativi: selezionare questa casella di controllo per includere i file nativi.</span><span class="sxs-lookup"><span data-stu-id="e7c30-119">Native files - Select this checkbox to include the native files.</span></span>
  
  - <span data-ttu-id="e7c30-120">Opzioni di conversazione</span><span class="sxs-lookup"><span data-stu-id="e7c30-120">Conversation options</span></span>
    
    - <span data-ttu-id="e7c30-121">File di conversazione: esportare i messaggi di chat ricostruiti.</span><span class="sxs-lookup"><span data-stu-id="e7c30-121">Conversation files - Export reconstructed chat messages.</span></span> <span data-ttu-id="e7c30-122">Questo formato presenta conversazioni in un modulo simile a quello che gli utenti vedono nell'applicazione nativa.</span><span class="sxs-lookup"><span data-stu-id="e7c30-122">This format presents conversations in a form that resembles what users see in the native application.</span></span>
    
    - <span data-ttu-id="e7c30-123">Messaggi di chat individuali: esportare i file di conversazione originali come archiviati in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e7c30-123">Individual chat messages - Export the original conversation files as they are stored in Microsoft 365.</span></span>

- <span data-ttu-id="e7c30-124">Opzioni</span><span class="sxs-lookup"><span data-stu-id="e7c30-124">Options</span></span>

  - <span data-ttu-id="e7c30-125">File di testo-includere le versioni di testo estratte dei file nativi.</span><span class="sxs-lookup"><span data-stu-id="e7c30-125">Text files - Include extracted text versions of native files.</span></span>
  
  - <span data-ttu-id="e7c30-126">Sostituisci nativi ritirati con i file PDF convertiti-se durante la revisione sono stati generati i documenti di modifica, questi file sono disponibili per l'esportazione.</span><span class="sxs-lookup"><span data-stu-id="e7c30-126">Replace redacted natives with converted PDFs - If redacted PDF files are generated during review, these files are available for export.</span></span> <span data-ttu-id="e7c30-127">È possibile scegliere di esportare solo i file nativi che sono stati redatti (non selezionando questa opzione) oppure è possibile selezionare questa opzione per esportare i file PDF che contengono le redazioni effettive.</span><span class="sxs-lookup"><span data-stu-id="e7c30-127">You can choose to export only the native files that were redacted (by not selecting this option) or you can select this option to export the PDF files that contain the actual redactions.</span></span>

- <span data-ttu-id="e7c30-128">Opzioni di output (il contenuto esportato è disponibile per il download direttamente tramite un Web browser o può essere inviato a un account di archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="e7c30-128">Output options (Exported content is either available for download directly through a web browser or can be sent to an Azure Storage account.</span></span> <span data-ttu-id="e7c30-129">Le prime due opzioni consentono il download diretto.</span><span class="sxs-lookup"><span data-stu-id="e7c30-129">The first two options enable direct download.)</span></span>
  
  - <span data-ttu-id="e7c30-130">File allentati e PST (la posta elettronica viene aggiunta a PST quando possibile): i file vengono esportati in un formato simile alla struttura di directory originale visualizzata dagli utenti nelle applicazioni native.</span><span class="sxs-lookup"><span data-stu-id="e7c30-130">Loose files and PSTs (email is added to PSTs when possible) - Files are exported in a format that resembles the original directory structure seen by users in their native applications.</span></span>  <span data-ttu-id="e7c30-131">Per ulteriori informazioni, vedere la sezione [file Loose and PST Export Structure](#loose-files-and-pst-export-structure) .</span><span class="sxs-lookup"><span data-stu-id="e7c30-131">For more information, see the [Loose files and PST export structure](#loose-files-and-pst-export-structure) section.</span></span>
  
  - <span data-ttu-id="e7c30-132">Struttura di directory condensata-i file vengono esportati e inclusi nel download.</span><span class="sxs-lookup"><span data-stu-id="e7c30-132">Condensed directory structure - Files are exported and included in the download.</span></span>
  
  - <span data-ttu-id="e7c30-133">Struttura di directory ridotta esportata nell'account di archiviazione di Azure-i file vengono esportati nell'accouunt di archiviazione di Azure dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e7c30-133">Condensed directory structure exported to your Azure Storage account - Files are exported to your organization's Azure Storage accouunt.</span></span>

## <a name="loose-files-and-pst-export-structure"></a><span data-ttu-id="e7c30-134">File Loose e struttura di esportazione PST</span><span class="sxs-lookup"><span data-stu-id="e7c30-134">Loose files and PST export structure</span></span>

<span data-ttu-id="e7c30-135">Se si seleziona questa opzione di esportazione, il contenuto esportato è organizzato nella struttura seguente:</span><span class="sxs-lookup"><span data-stu-id="e7c30-135">If you select this export option, the exported content is organized in the following structure:</span></span>

- <span data-ttu-id="e7c30-136">Cartella radice – questa cartella denominata ExportName.zip</span><span class="sxs-lookup"><span data-stu-id="e7c30-136">Root folder – This folder in named ExportName.zip</span></span>
  
  - <span data-ttu-id="e7c30-137">Export_load_file.csv-file di metadati.</span><span class="sxs-lookup"><span data-stu-id="e7c30-137">Export_load_file.csv - Metadata file.</span></span>
  
  - <span data-ttu-id="e7c30-138">Summary.csv-un file di riepilogo contenente anche le statistiche di esportazione.</span><span class="sxs-lookup"><span data-stu-id="e7c30-138">Summary.csv - A summary file that also contains export statistics.</span></span>
  
  - <span data-ttu-id="e7c30-139">Exchange: questa cartella contiene tutto il contenuto di Exchange nel formato di file nativo.</span><span class="sxs-lookup"><span data-stu-id="e7c30-139">Exchange - This folder contains all content from Exchange in native file format.</span></span> <span data-ttu-id="e7c30-140">Se è stata selezionata l'opzione **Sostituisci nativi con file PDF convertiti** , i file nativi vengono sostituiti con documenti PDF ritirati.</span><span class="sxs-lookup"><span data-stu-id="e7c30-140">Natives files are replaced with redacted PDFs if you selected the **Replace redacted natives with converted PDFs** option.</span></span>
  
  - <span data-ttu-id="e7c30-141">SharePoint = questa cartella contiene tutto il contenuto nativo di SharePoint in un formato di file nativo.</span><span class="sxs-lookup"><span data-stu-id="e7c30-141">SharePoint = This folder contains all native content from SharePoint in a native file format.</span></span> <span data-ttu-id="e7c30-142">Se è stata selezionata l'opzione **Sostituisci nativi con file PDF convertiti** , i file nativi vengono sostituiti con documenti PDF ritirati.</span><span class="sxs-lookup"><span data-stu-id="e7c30-142">Natives files are replaced with redacted PDFs if you selected the **Replace redacted natives with converted PDFs** option.</span></span>

## <a name="condensed-directory-structure"></a><span data-ttu-id="e7c30-143">Struttura di directory ridotta</span><span class="sxs-lookup"><span data-stu-id="e7c30-143">Condensed directory structure</span></span>

- <span data-ttu-id="e7c30-144">Cartella radice-questa cartella è denominata ExportName.zip</span><span class="sxs-lookup"><span data-stu-id="e7c30-144">Root folder - This folder is named ExportName.zip</span></span>
  
  - <span data-ttu-id="e7c30-145">Export_load_file.csv-file di metadati.</span><span class="sxs-lookup"><span data-stu-id="e7c30-145">Export_load_file.csv - Metadata file.</span></span>
  
  - <span data-ttu-id="e7c30-146">Summary.txt-un file di riepilogo contenente anche le statistiche di esportazione.</span><span class="sxs-lookup"><span data-stu-id="e7c30-146">Summary.txt - A summary file that also contains export statistics.</span></span>
  
  - <span data-ttu-id="e7c30-147">Input_or_native_files: questa cartella contiene tutti i file nativi che sono stati esportati.</span><span class="sxs-lookup"><span data-stu-id="e7c30-147">Input_or_native_files - This folder contains all the native files that were exported.</span></span> <span data-ttu-id="e7c30-148">Se si esportano file PDF redatti, non vengono inseriti nei file PST.</span><span class="sxs-lookup"><span data-stu-id="e7c30-148">If you export redacted PDF files, they are not put in PST files.</span></span> <span data-ttu-id="e7c30-149">Al contrario, vengono aggiunti a una cartella separata.</span><span class="sxs-lookup"><span data-stu-id="e7c30-149">Instead, they're added to a separated folder.</span></span>
  
  - <span data-ttu-id="e7c30-150">Error_files-questa cartella contiene i file di errore seguenti, se sono inclusi nell'esportazione:</span><span class="sxs-lookup"><span data-stu-id="e7c30-150">Error_files - This folder contains the following error files, if they are included in the export:</span></span>
    
    - <span data-ttu-id="e7c30-151">ExtractionError.</span><span class="sxs-lookup"><span data-stu-id="e7c30-151">ExtractionError.</span></span> <span data-ttu-id="e7c30-152">File CSV che contiene i metadati disponibili dei file che non sono stati estratti correttamente dai file padre.</span><span class="sxs-lookup"><span data-stu-id="e7c30-152">A CSV file that contains any available metadata of files that weren't properly extracted from parent files.</span></span>
    
    - <span data-ttu-id="e7c30-153">ProcessingError – questo file contiene un elenco di documenti con errori di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="e7c30-153">ProcessingError – This file contains a list of documents with processing errors.</span></span> <span data-ttu-id="e7c30-154">Questo contenuto è a livello di elemento, ovvero se un allegato ha generato un errore di elaborazione, il messaggio di posta elettronica che contiene l'allegato è incluso in questa cartella.</span><span class="sxs-lookup"><span data-stu-id="e7c30-154">This content is item-level, meaning if an attachment resulted in a processing error, the email message that contains the attachment is included in this folder.</span></span>
  
  - <span data-ttu-id="e7c30-155">Extracted_text_files: questa cartella contiene tutti i file di testo estratti che sono stati generati durante l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="e7c30-155">Extracted_text_files - This folder contains all of the extracted text files that were generated at processing.</span></span>

> [!NOTE]
> <span data-ttu-id="e7c30-156">I processi di esportazione vengono mantenuti per tutta la durata del caso e possono essere scaricati purché il caso non venga eliminato.</span><span class="sxs-lookup"><span data-stu-id="e7c30-156">Export jobs are retained for the life of the case and can be downloaded as long as the case isn't deleted.</span></span>
