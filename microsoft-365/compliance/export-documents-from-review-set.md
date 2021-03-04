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
description: Informazioni su come selezionare ed esportare il contenuto da un insieme di recensioni per presentazioni o recensioni esterne.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a2ca8e2f400d9f257549e59305d1fd56586185e2
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423647"
---
# <a name="export-documents-from-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="d7956-103">Esportare documenti da un insieme di recensioni in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="d7956-103">Export documents from a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="d7956-104">L'esportazione consente agli utenti di personalizzare il contenuto incluso nel pacchetto di download.</span><span class="sxs-lookup"><span data-stu-id="d7956-104">Export allows users to customize the content that is included in the download package.</span></span> <span data-ttu-id="d7956-105">Lo strumento di esportazione fornisce una pagina di configurazione con le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d7956-105">The Export tool provides a configuration page with the following settings:</span></span>

![Opzioni per l'esportazione di elementi da un insieme da rivedere](../media/bcfc72c7-4a01-4697-9e16-2965b7f04fdb.png)

## <a name="export-options"></a><span data-ttu-id="d7956-107">Opzioni di esportazione</span><span class="sxs-lookup"><span data-stu-id="d7956-107">Export options</span></span>

- <span data-ttu-id="d7956-108">Nome esportazione: Nome del processo di esportazione.</span><span class="sxs-lookup"><span data-stu-id="d7956-108">Export name: Name of the export job.</span></span>

- <span data-ttu-id="d7956-109">Descrizione: campo di testo libero per aggiungere una descrizione.</span><span class="sxs-lookup"><span data-stu-id="d7956-109">Description: Free-text field for you to add a description.</span></span>

- <span data-ttu-id="d7956-110">Esportare questi documenti:</span><span class="sxs-lookup"><span data-stu-id="d7956-110">Export these documents:</span></span>

  - <span data-ttu-id="d7956-111">Solo documenti selezionati: esporta solo i documenti attualmente selezionati.</span><span class="sxs-lookup"><span data-stu-id="d7956-111">Selected documents only - Exports only the documents that are currently selected.</span></span>
  
  - <span data-ttu-id="d7956-112">Tutti i documenti nell'insieme da rivedere - Esporta tutti i documenti nel set di revisioni</span><span class="sxs-lookup"><span data-stu-id="d7956-112">All documents in the review set - Exports all documents in the review set</span></span>

- <span data-ttu-id="d7956-113">Metadati</span><span class="sxs-lookup"><span data-stu-id="d7956-113">Metadata</span></span>
  
  - <span data-ttu-id="d7956-114">Carica file: questo file contiene i metadati per ogni file.</span><span class="sxs-lookup"><span data-stu-id="d7956-114">Load file - This file contains metadata for each file.</span></span> <span data-ttu-id="d7956-115">Per ulteriori informazioni sui campi inclusi, vedere [Campi dei metadati del documento in Advanced eDiscovery.](document-metadata-fields-in-Advanced-eDiscovery.md)</span><span class="sxs-lookup"><span data-stu-id="d7956-115">For more information about what fields are included, see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span></span> <span data-ttu-id="d7956-116">Questo file può in genere essere ingerito da strumenti di eDiscovery di terze parti.</span><span class="sxs-lookup"><span data-stu-id="d7956-116">This file can typically be ingested by third-party eDiscovery tools.</span></span>
  
  - <span data-ttu-id="d7956-117">Tag: se selezionata, le informazioni di tagging verranno incluse nel file di caricamento.</span><span class="sxs-lookup"><span data-stu-id="d7956-117">Tags - When selected, tagging information will be included in the load file.</span></span>

- <span data-ttu-id="d7956-118">Contenuto</span><span class="sxs-lookup"><span data-stu-id="d7956-118">Content</span></span>
  
  - <span data-ttu-id="d7956-119">File nativi: selezionare questa casella di controllo per includere i file nativi.</span><span class="sxs-lookup"><span data-stu-id="d7956-119">Native files - Select this checkbox to include the native files.</span></span>
  
  - <span data-ttu-id="d7956-120">Opzioni di conversazione</span><span class="sxs-lookup"><span data-stu-id="d7956-120">Conversation options</span></span>
    
    - <span data-ttu-id="d7956-121">File di conversazione - Esportare i messaggi di chat ricostruiti.</span><span class="sxs-lookup"><span data-stu-id="d7956-121">Conversation files - Export reconstructed chat messages.</span></span> <span data-ttu-id="d7956-122">Questo formato presenta le conversazioni in un formato simile a quello visualizzato dagli utenti nell'applicazione nativa.</span><span class="sxs-lookup"><span data-stu-id="d7956-122">This format presents conversations in a form that resembles what users see in the native application.</span></span>
    
    - <span data-ttu-id="d7956-123">Singoli messaggi di chat: esportare i file di conversazione originali così come sono archiviati in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d7956-123">Individual chat messages - Export the original conversation files as they are stored in Microsoft 365.</span></span>

- <span data-ttu-id="d7956-124">Opzioni</span><span class="sxs-lookup"><span data-stu-id="d7956-124">Options</span></span>

  - <span data-ttu-id="d7956-125">File di testo: includi versioni di testo estratte di file nativi.</span><span class="sxs-lookup"><span data-stu-id="d7956-125">Text files - Include extracted text versions of native files.</span></span>
  
  - <span data-ttu-id="d7956-126">Sostituisci i nativi con PDF convertiti: se i file PDF redatti vengono generati durante la revisione, questi file sono disponibili per l'esportazione.</span><span class="sxs-lookup"><span data-stu-id="d7956-126">Replace redacted natives with converted PDFs - If redacted PDF files are generated during review, these files are available for export.</span></span> <span data-ttu-id="d7956-127">È possibile scegliere di esportare solo i file nativi che sono stati redatti (non selezionando questa opzione) oppure è possibile selezionare questa opzione per esportare i file PDF che contengono le azioni effettive.</span><span class="sxs-lookup"><span data-stu-id="d7956-127">You can choose to export only the native files that were redacted (by not selecting this option) or you can select this option to export the PDF files that contain the actual redactions.</span></span>

- <span data-ttu-id="d7956-128">Opzioni di output (il contenuto esportato è disponibile per il download direttamente tramite un Web browser o può essere inviato a un account di archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="d7956-128">Output options (Exported content is either available for download directly through a web browser or can be sent to an Azure Storage account.</span></span> <span data-ttu-id="d7956-129">Le prime due opzioni abilitano il download diretto.</span><span class="sxs-lookup"><span data-stu-id="d7956-129">The first two options enable direct download.)</span></span>
  
  - <span data-ttu-id="d7956-130">File e file PST (la posta elettronica viene aggiunta ai file PST quando possibile) - I file vengono esportati in un formato simile alla struttura di directory originale visualizzata dagli utenti nelle applicazioni native.</span><span class="sxs-lookup"><span data-stu-id="d7956-130">Loose files and PSTs (email is added to PSTs when possible) - Files are exported in a format that resembles the original directory structure seen by users in their native applications.</span></span>  <span data-ttu-id="d7956-131">Per ulteriori informazioni, vedere la sezione [Relativa ai file con estensione loose e alla struttura di esportazione PST.](#loose-files-and-pst-export-structure)</span><span class="sxs-lookup"><span data-stu-id="d7956-131">For more information, see the [Loose files and PST export structure](#loose-files-and-pst-export-structure) section.</span></span>
  
  - <span data-ttu-id="d7956-132">Struttura di directory ridotto: i file vengono esportati e inclusi nel download.</span><span class="sxs-lookup"><span data-stu-id="d7956-132">Condensed directory structure - Files are exported and included in the download.</span></span>
  
  - <span data-ttu-id="d7956-133">Struttura di directory ridotto esportata nell'account di archiviazione di Azure: i file vengono esportati nell'account di archiviazione di Azure dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d7956-133">Condensed directory structure exported to your Azure Storage account - Files are exported to your organization's Azure Storage account.</span></span>

## <a name="loose-files-and-pst-export-structure"></a><span data-ttu-id="d7956-134">File con estensione loose e struttura di esportazione PST</span><span class="sxs-lookup"><span data-stu-id="d7956-134">Loose files and PST export structure</span></span>

<span data-ttu-id="d7956-135">Se si seleziona questa opzione di esportazione, il contenuto esportato viene organizzato nella struttura seguente:</span><span class="sxs-lookup"><span data-stu-id="d7956-135">If you select this export option, the exported content is organized in the following structure:</span></span>

- <span data-ttu-id="d7956-136">Cartella radice- Cartella denominata ExportName.zip</span><span class="sxs-lookup"><span data-stu-id="d7956-136">Root folder – This folder in named ExportName.zip</span></span>
  
  - <span data-ttu-id="d7956-137">Export_load_file.csv - File di metadati.</span><span class="sxs-lookup"><span data-stu-id="d7956-137">Export_load_file.csv - Metadata file.</span></span>
  
  - <span data-ttu-id="d7956-138">Summary.csv - Un file di riepilogo che contiene anche le statistiche di esportazione.</span><span class="sxs-lookup"><span data-stu-id="d7956-138">Summary.csv - A summary file that also contains export statistics.</span></span>
  
  - <span data-ttu-id="d7956-139">Exchange: questa cartella contiene tutto il contenuto di Exchange in formato di file nativo.</span><span class="sxs-lookup"><span data-stu-id="d7956-139">Exchange - This folder contains all content from Exchange in native file format.</span></span> <span data-ttu-id="d7956-140">I file nativi vengono sostituiti con PDF redatti se hai selezionato l'opzione Sostituisci i file nativi con PDF **convertiti.**</span><span class="sxs-lookup"><span data-stu-id="d7956-140">Natives files are replaced with redacted PDFs if you selected the **Replace redacted natives with converted PDFs** option.</span></span>
  
  - <span data-ttu-id="d7956-141">SharePoint = Questa cartella contiene tutto il contenuto nativo di SharePoint in un formato di file nativo.</span><span class="sxs-lookup"><span data-stu-id="d7956-141">SharePoint = This folder contains all native content from SharePoint in a native file format.</span></span> <span data-ttu-id="d7956-142">I file nativi vengono sostituiti con PDF redatti se hai selezionato l'opzione Sostituisci i file nativi con PDF **convertiti.**</span><span class="sxs-lookup"><span data-stu-id="d7956-142">Natives files are replaced with redacted PDFs if you selected the **Replace redacted natives with converted PDFs** option.</span></span>

## <a name="condensed-directory-structure"></a><span data-ttu-id="d7956-143">Struttura di directory compressa</span><span class="sxs-lookup"><span data-stu-id="d7956-143">Condensed directory structure</span></span>

- <span data-ttu-id="d7956-144">Cartella radice - Questa cartella è denominata ExportName.zip</span><span class="sxs-lookup"><span data-stu-id="d7956-144">Root folder - This folder is named ExportName.zip</span></span>
  
  - <span data-ttu-id="d7956-145">Export_load_file.csv - File di metadati.</span><span class="sxs-lookup"><span data-stu-id="d7956-145">Export_load_file.csv - Metadata file.</span></span>
  
  - <span data-ttu-id="d7956-146">Summary.txt - Un file di riepilogo che contiene anche le statistiche di esportazione.</span><span class="sxs-lookup"><span data-stu-id="d7956-146">Summary.txt - A summary file that also contains export statistics.</span></span>
  
  - <span data-ttu-id="d7956-147">Input_or_native_files- Questa cartella contiene tutti i file nativi esportati.</span><span class="sxs-lookup"><span data-stu-id="d7956-147">Input_or_native_files - This folder contains all the native files that were exported.</span></span> <span data-ttu-id="d7956-148">Se si esportano file PDF redatti, questi non vengono inseriti nei file PST.</span><span class="sxs-lookup"><span data-stu-id="d7956-148">If you export redacted PDF files, they are not put in PST files.</span></span> <span data-ttu-id="d7956-149">Vengono invece aggiunti a una cartella separata.</span><span class="sxs-lookup"><span data-stu-id="d7956-149">Instead, they're added to a separated folder.</span></span>
  
  - <span data-ttu-id="d7956-150">Error_files- Questa cartella contiene i file di errore seguenti, se inclusi nell'esportazione:</span><span class="sxs-lookup"><span data-stu-id="d7956-150">Error_files - This folder contains the following error files, if they are included in the export:</span></span>
    
    - <span data-ttu-id="d7956-151">ExtractionError.</span><span class="sxs-lookup"><span data-stu-id="d7956-151">ExtractionError.</span></span> <span data-ttu-id="d7956-152">Un file CSV che contiene i metadati disponibili dei file che non sono stati estratti correttamente dai file padre.</span><span class="sxs-lookup"><span data-stu-id="d7956-152">A CSV file that contains any available metadata of files that weren't properly extracted from parent files.</span></span>
    
    - <span data-ttu-id="d7956-153">ProcessingError: questo file contiene un elenco di documenti con errori di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="d7956-153">ProcessingError – This file contains a list of documents with processing errors.</span></span> <span data-ttu-id="d7956-154">Questo contenuto è a livello di elemento, ovvero se un allegato ha generato un errore di elaborazione, il messaggio di posta elettronica contenente l'allegato viene incluso in questa cartella.</span><span class="sxs-lookup"><span data-stu-id="d7956-154">This content is item-level, meaning if an attachment resulted in a processing error, the email message that contains the attachment is included in this folder.</span></span>
  
  - <span data-ttu-id="d7956-155">Extracted_text_files- Questa cartella contiene tutti i file di testo estratti che sono stati generati durante l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="d7956-155">Extracted_text_files - This folder contains all of the extracted text files that were generated at processing.</span></span>

> [!NOTE]
> <span data-ttu-id="d7956-156">I processi di esportazione vengono conservati per tutta la durata del caso.</span><span class="sxs-lookup"><span data-stu-id="d7956-156">Export jobs are retained for the life of the case.</span></span> <span data-ttu-id="d7956-157">Tuttavia, è necessario scaricare il contenuto da un processo di esportazione entro 30 giorni dal completamento del processo di esportazione.</span><span class="sxs-lookup"><span data-stu-id="d7956-157">However, you must download the content from an export job within 30 days after the export job is complete.</span></span>
