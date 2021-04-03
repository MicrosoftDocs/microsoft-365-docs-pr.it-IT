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
description: Informazioni su come selezionare ed esportare il contenuto da un set di recensioni avanzate di eDiscovery per presentazioni o recensioni esterne.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 0752c5272d078e75e3bdbfb9cf7af7e49c78e65c
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51581028"
---
# <a name="export-documents-from-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="694f7-103">Esportare documenti da un set di revisione in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="694f7-103">Export documents from a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="694f7-104">L'esportazione consente agli utenti di personalizzare il contenuto incluso nel pacchetto di download quando si esporta un documento da un set di revisioni in Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="694f7-104">Export allows users to customize the content that is included in the download package when you export document from a review set in Advanced eDiscovery.</span></span>

<span data-ttu-id="694f7-105">Per esportare documenti da un set di revisioni:</span><span class="sxs-lookup"><span data-stu-id="694f7-105">To export documents from a review set:</span></span>

1. <span data-ttu-id="694f7-106">Nel Centro conformità Microsoft 365 aprire il caso Advanced eDiscovery, selezionare la scheda **Review sets** e quindi selezionare il set di revisione che si desidera esportare.</span><span class="sxs-lookup"><span data-stu-id="694f7-106">In the Microsoft 365 compliance center, open the Advanced eDiscovery case, select the **Review sets** tab, and then select the review set that you want to export.</span></span>

2. <span data-ttu-id="694f7-107">Nel set di revisioni fare clic **su Azione**  >  **Esporta.**</span><span class="sxs-lookup"><span data-stu-id="694f7-107">In the review set, click **Action** > **Export**.</span></span>

   <span data-ttu-id="694f7-108">Lo strumento di esportazione visualizza la pagina a comparsa con le impostazioni per configurare l'esportazione.</span><span class="sxs-lookup"><span data-stu-id="694f7-108">The Export tool displays the flyout page with the settings to configure the export.</span></span> <span data-ttu-id="694f7-109">Alcune opzioni sono selezionate per impostazione predefinita, ma è possibile modificarle.</span><span class="sxs-lookup"><span data-stu-id="694f7-109">Some options are selected by default, but you can change these.</span></span> <span data-ttu-id="694f7-110">Per le descrizioni delle opzioni di esportazione che è possibile configurare, vedere la sezione seguente.</span><span class="sxs-lookup"><span data-stu-id="694f7-110">See the following section for descriptions of the export options that you can configure.</span></span>

   ![Opzioni di configurazione per l'esportazione di elementi da un set di revisione](../media/bcfc72c7-4a01-4697-9e16-2965b7f04fdb.png)

3. <span data-ttu-id="694f7-112">Dopo aver configurato l'esportazione, fare clic **su Esporta** per avviare il processo di esportazione.</span><span class="sxs-lookup"><span data-stu-id="694f7-112">After you configure the export, click **Export** to start the export process.</span></span> <span data-ttu-id="694f7-113">A seconda dell'opzione selezionata nella sezione **Opzioni** di output, è possibile accedere ai file di esportazione tramite download diretto o nell'account di archiviazione di Azure dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="694f7-113">Depending on the option that you selected in **Output options** section, you can access the export files by direct download or in your organization's Azure Storage account.</span></span>

> [!NOTE]
> <span data-ttu-id="694f7-114">I processi di esportazione vengono conservati per tutta la durata del caso.</span><span class="sxs-lookup"><span data-stu-id="694f7-114">Export jobs are retained for the life of the case.</span></span> <span data-ttu-id="694f7-115">Tuttavia, è necessario scaricare il contenuto da un processo di esportazione entro 30 giorni dal completamento del processo di esportazione.</span><span class="sxs-lookup"><span data-stu-id="694f7-115">However, you must download the content from an export job within 30 days after the export job is complete.</span></span>

## <a name="export-options"></a><span data-ttu-id="694f7-116">Opzioni di esportazione</span><span class="sxs-lookup"><span data-stu-id="694f7-116">Export options</span></span>

<span data-ttu-id="694f7-117">Utilizzare le opzioni seguenti per configurare l'esportazione.</span><span class="sxs-lookup"><span data-stu-id="694f7-117">Use the following options to configure the export.</span></span>

- <span data-ttu-id="694f7-118">**Nome esportazione**: Nome del processo di esportazione.</span><span class="sxs-lookup"><span data-stu-id="694f7-118">**Export name**: Name of the export job.</span></span>

- <span data-ttu-id="694f7-119">**Descrizione**: campo a testo libero che consente di aggiungere una descrizione.</span><span class="sxs-lookup"><span data-stu-id="694f7-119">**Description**: Free-text field for you to add a description.</span></span>

- <span data-ttu-id="694f7-120">**Esportare questi documenti**</span><span class="sxs-lookup"><span data-stu-id="694f7-120">**Export these documents**</span></span>

  - <span data-ttu-id="694f7-121">**Solo documenti selezionati:** questa opzione esporta solo i documenti attualmente selezionati.</span><span class="sxs-lookup"><span data-stu-id="694f7-121">**Selected documents only**: This option exports only the documents that are currently selected.</span></span>
  
  - <span data-ttu-id="694f7-122">**Tutti i documenti nel set di revisioni**: questa opzione esporta tutti i documenti nel set di revisioni.</span><span class="sxs-lookup"><span data-stu-id="694f7-122">**All documents in the review set**: This option exports all documents in the review set.</span></span>

- <span data-ttu-id="694f7-123">**Metadati**</span><span class="sxs-lookup"><span data-stu-id="694f7-123">**Metadata**</span></span>
  
  - <span data-ttu-id="694f7-124">**Carica file:** questo file contiene i metadati per ogni file.</span><span class="sxs-lookup"><span data-stu-id="694f7-124">**Load file**: This file contains metadata for each file.</span></span> <span data-ttu-id="694f7-125">Questo file in genere può essere ingerito da strumenti di eDiscovery di terze parti.</span><span class="sxs-lookup"><span data-stu-id="694f7-125">This file can typically be ingested by third-party eDiscovery tools.</span></span> <span data-ttu-id="694f7-126">Per ulteriori informazioni sui campi inclusi, vedere [Campi dei metadati del documento in Advanced eDiscovery.](document-metadata-fields-in-Advanced-eDiscovery.md)</span><span class="sxs-lookup"><span data-stu-id="694f7-126">For more information about what fields are included, see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span></span>
  
  - <span data-ttu-id="694f7-127">**Tag**: se selezionata, le informazioni di tagging vengono incluse nel file di caricamento.</span><span class="sxs-lookup"><span data-stu-id="694f7-127">**Tags**: When selected, tagging information is included in the load file.</span></span>

- <span data-ttu-id="694f7-128">**Contenuto**</span><span class="sxs-lookup"><span data-stu-id="694f7-128">**Content**</span></span>
  
  - <span data-ttu-id="694f7-129">**File nativi:** selezionare questa casella di controllo per includere i file nativi dei documenti nel set di revisioni.</span><span class="sxs-lookup"><span data-stu-id="694f7-129">**Native files**: Select this checkbox to include the native files of the documents in the review set.</span></span> <span data-ttu-id="694f7-130">Se si sceglie di esportare file nativi, sono disponibili le opzioni seguenti per l'esportazione delle conversazioni di chat.</span><span class="sxs-lookup"><span data-stu-id="694f7-130">If you choose to export native files, you have the following options for how export chat conversations.</span></span>
  
  - <span data-ttu-id="694f7-131">**Opzioni di conversazione**</span><span class="sxs-lookup"><span data-stu-id="694f7-131">**Conversation options**</span></span>

    - <span data-ttu-id="694f7-132">**File di conversazione**: questa opzione esporta conversazioni di chat ricostruite.</span><span class="sxs-lookup"><span data-stu-id="694f7-132">**Conversation files**: This option exports reconstructed chat conversations.</span></span> <span data-ttu-id="694f7-133">Questo formato presenta le conversazioni in un formato simile a quello visualizzato dagli utenti nell'applicazione nativa.</span><span class="sxs-lookup"><span data-stu-id="694f7-133">This format presents conversations in a form that resembles what users see in the native application.</span></span>

    - <span data-ttu-id="694f7-134">**Singoli messaggi di chat:** questa opzione esporta i file di conversazione originali così come sono archiviati in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="694f7-134">**Individual chat messages**: This option exports the original conversation files as they are stored in Microsoft 365.</span></span>

- <span data-ttu-id="694f7-135">**Opzioni**</span><span class="sxs-lookup"><span data-stu-id="694f7-135">**Options**</span></span>

  - <span data-ttu-id="694f7-136">**File di** testo : - Questa opzione include le versioni di testo estratte dei file nativi nell'esportazione.</span><span class="sxs-lookup"><span data-stu-id="694f7-136">**Text files**: - This option includes the extracted text versions of native files in the export.</span></span>
  
  - <span data-ttu-id="694f7-137">**Sostituire i nativi con** PDF convertiti: se i file PDF redatti vengono generati durante la revisione, questi file sono disponibili per l'esportazione.</span><span class="sxs-lookup"><span data-stu-id="694f7-137">**Replace redacted natives with converted PDFs**: If redacted PDF files are generated during review, these files are available for export.</span></span> <span data-ttu-id="694f7-138">È possibile scegliere di esportare solo i file nativi che sono stati redatti (non selezionando questa opzione) oppure è possibile selezionare questa opzione per esportare i file PDF che contengono le azioni effettive.</span><span class="sxs-lookup"><span data-stu-id="694f7-138">You can choose to export only the native files that were redacted (by not selecting this option) or you can select this option to export the PDF files that contain the actual redactions.</span></span>

- <span data-ttu-id="694f7-139">**Opzioni di** output: il contenuto esportato è disponibile per il download direttamente tramite un Web browser o può essere inviato a un account di archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="694f7-139">**Output options**: Exported content is either available for download directly through a web browser or can be sent to an Azure Storage account.</span></span> <span data-ttu-id="694f7-140">Le prime due opzioni consentono il download diretto.</span><span class="sxs-lookup"><span data-stu-id="694f7-140">The first two options enable direct download.</span></span>
  
  - <span data-ttu-id="694f7-141">**File e FILE PST (la** posta elettronica viene aggiunta ai file PST quando possibile): i file vengono esportati in un formato simile alla struttura di directory originale visualizzata dagli utenti nelle applicazioni native.</span><span class="sxs-lookup"><span data-stu-id="694f7-141">**Loose files and PSTs (email is added to PSTs when possible)**: Files are exported in a format that resembles the original directory structure seen by users in their native applications.</span></span>  <span data-ttu-id="694f7-142">Per ulteriori informazioni, vedere la [sezione Loose files and PST export structure.](#loose-files-and-pst-export-structure)</span><span class="sxs-lookup"><span data-stu-id="694f7-142">For more information, see the [Loose files and PST export structure](#loose-files-and-pst-export-structure) section.</span></span>
  
  - <span data-ttu-id="694f7-143">**Struttura della directory compressa:** i file vengono esportati e inclusi nel download.</span><span class="sxs-lookup"><span data-stu-id="694f7-143">**Condensed directory structure**: Files are exported and included in the download.</span></span>
  
  - <span data-ttu-id="694f7-144">**Struttura di directory compressa esportata nell'account di archiviazione** di Azure: i file vengono esportati nell'account di archiviazione di Azure dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="694f7-144">**Condensed directory structure exported to your Azure Storage account**: Files are exported to your organization's Azure Storage account.</span></span> <span data-ttu-id="694f7-145">Per questa opzione, devi fornire l'URL per il contenitore nel tuo account di archiviazione di Azure in cui esportare i file.</span><span class="sxs-lookup"><span data-stu-id="694f7-145">For this option, you have to provide the URL for the container in your Azure Storage account to export the files to.</span></span> <span data-ttu-id="694f7-146">È inoltre necessario fornire il token di firma di accesso condiviso (SAS) per l'account di archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="694f7-146">You also have to provide the shared access signature (SAS) token for your Azure Storage account.</span></span> <span data-ttu-id="694f7-147">Per ulteriori informazioni, vedere [Export documents in a review set to an Azure Storage account](download-export-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="694f7-147">For more information, see [Export documents in a review set to an Azure Storage account](download-export-jobs.md).</span></span>

<span data-ttu-id="694f7-148">Nelle sezioni seguenti viene descritta la struttura delle cartelle per i file con estensione loose e le opzioni della struttura di directory compressa.</span><span class="sxs-lookup"><span data-stu-id="694f7-148">The following sections describe the folder structure for loose files and condensed directory structure options.</span></span>

### <a name="loose-files-and-pst-export-structure"></a><span data-ttu-id="694f7-149">File con estensione loose e struttura di esportazione PST</span><span class="sxs-lookup"><span data-stu-id="694f7-149">Loose files and PST export structure</span></span>

<span data-ttu-id="694f7-150">Se si seleziona questa opzione di esportazione, il contenuto esportato viene organizzato nella struttura seguente:</span><span class="sxs-lookup"><span data-stu-id="694f7-150">If you select this export option, the exported content is organized in the following structure:</span></span>

- <span data-ttu-id="694f7-151">Cartella radice: cartella denominata ExportName.zip</span><span class="sxs-lookup"><span data-stu-id="694f7-151">Root folder: This folder in named ExportName.zip</span></span>
  
  - <span data-ttu-id="694f7-152">Export_load_file.csv: il file di metadati.</span><span class="sxs-lookup"><span data-stu-id="694f7-152">Export_load_file.csv: The metadata file.</span></span>
  
  - <span data-ttu-id="694f7-153">Summary.csv: un file di riepilogo che contiene anche le statistiche di esportazione.</span><span class="sxs-lookup"><span data-stu-id="694f7-153">Summary.csv: A summary file that also contains export statistics.</span></span>
  
  - <span data-ttu-id="694f7-154">Exchange: questa cartella contiene tutto il contenuto di Exchange in formato di file nativo.</span><span class="sxs-lookup"><span data-stu-id="694f7-154">Exchange: This folder contains all content from Exchange in native file format.</span></span> <span data-ttu-id="694f7-155">I file nativi vengono sostituiti con PDF redatti se è stata selezionata l'opzione Sostituisci i nativi con i **PDF convertiti.**</span><span class="sxs-lookup"><span data-stu-id="694f7-155">Natives files are replaced with redacted PDFs if you selected the **Replace redacted natives with converted PDFs** option.</span></span>
  
  - <span data-ttu-id="694f7-156">SharePoint: questa cartella contiene tutto il contenuto nativo di SharePoint in un formato di file nativo.</span><span class="sxs-lookup"><span data-stu-id="694f7-156">SharePoint: This folder contains all native content from SharePoint in a native file format.</span></span> <span data-ttu-id="694f7-157">I file nativi vengono sostituiti con PDF redatti se è stata selezionata l'opzione Sostituisci i nativi con i **PDF convertiti.**</span><span class="sxs-lookup"><span data-stu-id="694f7-157">Natives files are replaced with redacted PDFs if you selected the **Replace redacted natives with converted PDFs** option.</span></span>

### <a name="condensed-directory-structure"></a><span data-ttu-id="694f7-158">Struttura di directory compressa</span><span class="sxs-lookup"><span data-stu-id="694f7-158">Condensed directory structure</span></span>

- <span data-ttu-id="694f7-159">Cartella radice: questa cartella è denominata ExportName.zip</span><span class="sxs-lookup"><span data-stu-id="694f7-159">Root folder: This folder is named ExportName.zip</span></span>
  
  - <span data-ttu-id="694f7-160">Export_load_file.csv: il file di metadati.</span><span class="sxs-lookup"><span data-stu-id="694f7-160">Export_load_file.csv: The metadata file.</span></span>
  
  - <span data-ttu-id="694f7-161">Summary.txt: un file di riepilogo che contiene anche le statistiche di esportazione.</span><span class="sxs-lookup"><span data-stu-id="694f7-161">Summary.txt: A summary file that also contains export statistics.</span></span>
  
  - <span data-ttu-id="694f7-162">NativeFiles: questa cartella contiene tutti i file nativi esportati.</span><span class="sxs-lookup"><span data-stu-id="694f7-162">NativeFiles: This folder contains all the native files that were exported.</span></span> <span data-ttu-id="694f7-163">Se si esportano file PDF redatti, questi non vengono inseriti nei file PST.</span><span class="sxs-lookup"><span data-stu-id="694f7-163">If you export redacted PDF files, they are not put in PST files.</span></span> <span data-ttu-id="694f7-164">Vengono invece aggiunti a una cartella separata.</span><span class="sxs-lookup"><span data-stu-id="694f7-164">Instead, they're added to a separated folder.</span></span>
  
  - <span data-ttu-id="694f7-165">Error_files: questa cartella contiene i file di errore seguenti, se inclusi nell'esportazione:</span><span class="sxs-lookup"><span data-stu-id="694f7-165">Error_files: This folder contains the following error files, if they are included in the export:</span></span>

    - <span data-ttu-id="694f7-166">ExtractionError: file CSV contenente i metadati disponibili dei file che non sono stati estratti correttamente dai file padre.</span><span class="sxs-lookup"><span data-stu-id="694f7-166">ExtractionError: A CSV file that contains any available metadata of files that weren't properly extracted from parent files.</span></span>

    - <span data-ttu-id="694f7-167">ProcessingError: questo file contiene un elenco di documenti con errori di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="694f7-167">ProcessingError: This file contains a list of documents with processing errors.</span></span> <span data-ttu-id="694f7-168">Questo contenuto è a livello di elemento, ovvero se un allegato ha generato un errore di elaborazione, il messaggio di posta elettronica contenente l'allegato viene incluso in questa cartella.</span><span class="sxs-lookup"><span data-stu-id="694f7-168">This content is item-level, meaning if an attachment resulted in a processing error, the email message that contains the attachment is included in this folder.</span></span>
  
  - <span data-ttu-id="694f7-169">Extracted_text_files: questa cartella contiene tutti i file di testo estratti generati durante l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="694f7-169">Extracted_text_files: This folder contains all of the extracted text files that were generated at processing.</span></span>
