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
description: Informazioni su come selezionare ed esportare contenuto da un set Advanced eDiscovery per presentazioni o recensioni esterne.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a174c147da6e424891508bad484f45f4a5d308b6
ms.sourcegitcommit: ea8de1b48adb6df92fb9351ea862184a9f16cbbb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/16/2021
ms.locfileid: "53461400"
---
# <a name="export-documents-from-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="1adc5-103">Esportare documenti da un set di revisioni in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="1adc5-103">Export documents from a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="1adc5-104">L'esportazione consente agli utenti di personalizzare il contenuto incluso nel pacchetto di download quando si esporta un documento da un set di revisioni in Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="1adc5-104">Export allows users to customize the content that is included in the download package when you export document from a review set in Advanced eDiscovery.</span></span>

<span data-ttu-id="1adc5-105">Per esportare documenti da un set di revisioni:</span><span class="sxs-lookup"><span data-stu-id="1adc5-105">To export documents from a review set:</span></span>

1. <span data-ttu-id="1adc5-106">Nel Centro conformità Microsoft 365, aprire il caso Advanced eDiscovery, selezionare la  scheda Set di revisioni e quindi selezionare il set di revisioni che si desidera esportare.</span><span class="sxs-lookup"><span data-stu-id="1adc5-106">In the Microsoft 365 compliance center, open the Advanced eDiscovery case, select the **Review sets** tab, and then select the review set that you want to export.</span></span>

2. <span data-ttu-id="1adc5-107">Nel set di revisioni fare clic **su Azione**  >  **Esporta.**</span><span class="sxs-lookup"><span data-stu-id="1adc5-107">In the review set, click **Action** > **Export**.</span></span>

   <span data-ttu-id="1adc5-108">Lo strumento di esportazione visualizza la pagina a comparsa con le impostazioni per configurare l'esportazione.</span><span class="sxs-lookup"><span data-stu-id="1adc5-108">The Export tool displays the flyout page with the settings to configure the export.</span></span> <span data-ttu-id="1adc5-109">Alcune opzioni sono selezionate per impostazione predefinita, ma è possibile modificarle.</span><span class="sxs-lookup"><span data-stu-id="1adc5-109">Some options are selected by default, but you can change these.</span></span> <span data-ttu-id="1adc5-110">Per le descrizioni delle opzioni di esportazione che è possibile configurare, vedere la sezione seguente.</span><span class="sxs-lookup"><span data-stu-id="1adc5-110">See the following section for descriptions of the export options that you can configure.</span></span>

   ![Opzioni di configurazione per l'esportazione di elementi da un set di revisione](../media/bcfc72c7-4a01-4697-9e16-2965b7f04fdb.png)

3. <span data-ttu-id="1adc5-112">Dopo aver configurato l'esportazione, fare clic **su Esporta** per avviare il processo di esportazione.</span><span class="sxs-lookup"><span data-stu-id="1adc5-112">After you configure the export, click **Export** to start the export process.</span></span> <span data-ttu-id="1adc5-113">A seconda dell'opzione selezionata nella sezione **Opzioni** di output, è possibile accedere ai file di esportazione tramite download diretto o nell'account Archiviazione di Azure dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1adc5-113">Depending on the option that you selected in **Output options** section, you can access the export files by direct download or in your organization's Azure Storage account.</span></span>

> [!NOTE]
> <span data-ttu-id="1adc5-114">I processi di esportazione vengono conservati per tutta la durata del caso.</span><span class="sxs-lookup"><span data-stu-id="1adc5-114">Export jobs are retained for the life of the case.</span></span> <span data-ttu-id="1adc5-115">Tuttavia, è necessario scaricare il contenuto da un processo di esportazione entro 30 giorni dal completamento del processo di esportazione.</span><span class="sxs-lookup"><span data-stu-id="1adc5-115">However, you must download the content from an export job within 30 days after the export job is complete.</span></span>

## <a name="export-options"></a><span data-ttu-id="1adc5-116">Opzioni di esportazione</span><span class="sxs-lookup"><span data-stu-id="1adc5-116">Export options</span></span>

<span data-ttu-id="1adc5-117">Utilizzare le opzioni seguenti per configurare l'esportazione.</span><span class="sxs-lookup"><span data-stu-id="1adc5-117">Use the following options to configure the export.</span></span> <span data-ttu-id="1adc5-118">Non tutte le opzioni sono consentite per alcune opzioni di output, in particolare l'esportazione di file di testo e PDF redatti non sono consentite durante l'esportazione nel formato PST.</span><span class="sxs-lookup"><span data-stu-id="1adc5-118">Not all options are allowed for some output options, most notably, export of text files and redacted PDFs are not allowed when exporting to the PST format.</span></span>

- <span data-ttu-id="1adc5-119">**Nome esportazione**: Nome del processo di esportazione.</span><span class="sxs-lookup"><span data-stu-id="1adc5-119">**Export name**: Name of the export job.</span></span> <span data-ttu-id="1adc5-120">Verrà usato per assegnare un nome ai file ZIP che verranno scaricati.</span><span class="sxs-lookup"><span data-stu-id="1adc5-120">This will be used to name the ZIP files that will be downloaded.</span></span>

- <span data-ttu-id="1adc5-121">**Descrizione**: campo a testo libero che consente di aggiungere una descrizione.</span><span class="sxs-lookup"><span data-stu-id="1adc5-121">**Description**: Free-text field for you to add a description.</span></span>

- <span data-ttu-id="1adc5-122">**Esportare questi documenti**</span><span class="sxs-lookup"><span data-stu-id="1adc5-122">**Export these documents**</span></span>

  - <span data-ttu-id="1adc5-123">Solo documenti selezionati: questa opzione esporta solo i documenti attualmente selezionati.</span><span class="sxs-lookup"><span data-stu-id="1adc5-123">Selected documents only: This option exports only the documents that are currently selected.</span></span> <span data-ttu-id="1adc5-124">Questa opzione è disponibile solo quando gli elementi sono selezionati in un set di revisioni.</span><span class="sxs-lookup"><span data-stu-id="1adc5-124">This option is only available when items are selected in a review set.</span></span>
  
  - <span data-ttu-id="1adc5-125">Tutti i documenti filtrati: questa opzione consente di esportare i documenti in un filtro attivo.</span><span class="sxs-lookup"><span data-stu-id="1adc5-125">All filtered documents: This option exports the documents in an active filter.</span></span> <span data-ttu-id="1adc5-126">Questa opzione è disponibile solo quando viene applicato un filtro al set di revisioni.</span><span class="sxs-lookup"><span data-stu-id="1adc5-126">This option is only available when a filter is applied to the review set.</span></span>
  
  - <span data-ttu-id="1adc5-127">Tutti i documenti nel set di revisioni: questa opzione consente di esportare tutti i documenti nel set di revisioni.</span><span class="sxs-lookup"><span data-stu-id="1adc5-127">All documents in the review set: This option exports all documents in the review set.</span></span>

- <span data-ttu-id="1adc5-128">**Opzioni di** output: il contenuto esportato è disponibile per il download direttamente tramite un Web browser o può essere inviato a un Archiviazione di Azure account.</span><span class="sxs-lookup"><span data-stu-id="1adc5-128">**Output options**: Exported content is either available for download directly through a web browser or can be sent to an Azure Storage account.</span></span> <span data-ttu-id="1adc5-129">Le prime due opzioni consentono il download diretto.</span><span class="sxs-lookup"><span data-stu-id="1adc5-129">The first two options enable direct download.</span></span>
  
  - <span data-ttu-id="1adc5-130">Solo report: vengono creati solo il file di riepilogo e di caricamento.</span><span class="sxs-lookup"><span data-stu-id="1adc5-130">Reports only: Only the summary and load file are created.</span></span>
  
  - <span data-ttu-id="1adc5-131">File e file PST (la posta elettronica viene aggiunta ai file PST quando possibile): i file vengono esportati in un formato simile alla struttura di directory originale visualizzata dagli utenti nelle applicazioni native.</span><span class="sxs-lookup"><span data-stu-id="1adc5-131">Loose files and PSTs (email is added to PSTs when possible): Files are exported in a format that resembles the original directory structure seen by users in their native applications.</span></span>  <span data-ttu-id="1adc5-132">Per ulteriori informazioni, vedere la [sezione Loose files and PST export structure.](#loose-files-and-pst-export-structure)</span><span class="sxs-lookup"><span data-stu-id="1adc5-132">For more information, see the [Loose files and PST export structure](#loose-files-and-pst-export-structure) section.</span></span>
  
  - <span data-ttu-id="1adc5-133">Struttura di directory compressa: i file vengono esportati e inclusi nel download.</span><span class="sxs-lookup"><span data-stu-id="1adc5-133">Condensed directory structure: Files are exported and included in the download.</span></span>
  
  - <span data-ttu-id="1adc5-134">Struttura di directory compressa esportata nell'account Archiviazione di Azure: i file vengono esportati nell'account Archiviazione di Azure dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1adc5-134">Condensed directory structure exported to your Azure Storage account: Files are exported to your organization's Azure Storage account.</span></span> <span data-ttu-id="1adc5-135">Per questa opzione, devi fornire l'URL del contenitore nel tuo account Archiviazione di Azure in cui esportare i file.</span><span class="sxs-lookup"><span data-stu-id="1adc5-135">For this option, you have to provide the URL for the container in your Azure Storage account to export the files to.</span></span> <span data-ttu-id="1adc5-136">Devi anche fornire il token di firma di accesso condiviso (SAS) per il tuo account Archiviazione di Azure account.</span><span class="sxs-lookup"><span data-stu-id="1adc5-136">You also have to provide the shared access signature (SAS) token for your Azure Storage account.</span></span> <span data-ttu-id="1adc5-137">Per ulteriori informazioni, vedere [Export documents in a review set to an Archiviazione di Azure account](download-export-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="1adc5-137">For more information, see [Export documents in a review set to an Azure Storage account](download-export-jobs.md).</span></span>

- <span data-ttu-id="1adc5-138">**Includi**</span><span class="sxs-lookup"><span data-stu-id="1adc5-138">**Include**</span></span>
  
  - <span data-ttu-id="1adc5-139">Tag: se selezionata, le informazioni di tagging vengono incluse nel file di caricamento.</span><span class="sxs-lookup"><span data-stu-id="1adc5-139">Tags: When selected, tagging information is included in the load file.</span></span>
  
  - <span data-ttu-id="1adc5-140">File di testo: questa opzione include le versioni di testo estratte dei file nativi nell'esportazione.</span><span class="sxs-lookup"><span data-stu-id="1adc5-140">Text files: This option includes the extracted text versions of native files in the export.</span></span>
  
  - <span data-ttu-id="1adc5-141">Sostituire i nativi con PDF convertiti: se i file PDF redatti vengono generati durante la revisione, questi file sono disponibili per l'esportazione.</span><span class="sxs-lookup"><span data-stu-id="1adc5-141">Replace redacted natives with converted PDFs: If redacted PDF files are generated during review, these files are available for export.</span></span> <span data-ttu-id="1adc5-142">È possibile scegliere di esportare solo i file nativi che sono stati redatti (non selezionando questa opzione) oppure è possibile selezionare questa opzione per esportare i file PDF che contengono le azioni effettive.</span><span class="sxs-lookup"><span data-stu-id="1adc5-142">You can choose to export only the native files that were redacted (by not selecting this option) or you can select this option to export the PDF files that contain the actual redactions.</span></span>

<span data-ttu-id="1adc5-143">Nelle sezioni seguenti viene descritta la struttura delle cartelle per i file con estensione loose e le opzioni della struttura di directory compressa.</span><span class="sxs-lookup"><span data-stu-id="1adc5-143">The following sections describe the folder structure for loose files and condensed directory structure options.</span></span> <span data-ttu-id="1adc5-144">Le esportazioni vengono partizionate in file ZIP con una dimensione massima di contenuto non compresso di 75 GB.</span><span class="sxs-lookup"><span data-stu-id="1adc5-144">Exports are partitioned into ZIP files with a maximum size of uncompressed content of 75 GB.</span></span> <span data-ttu-id="1adc5-145">Se le dimensioni dell'esportazione sono inferiori a 75 GB, l'esportazione sarà costituita da un file di riepilogo e da un singolo file ZIP.</span><span class="sxs-lookup"><span data-stu-id="1adc5-145">If the export size is less than 75 GB, the export will consist of a summary file and a single ZIP file.</span></span> <span data-ttu-id="1adc5-146">Per le esportazioni di dimensioni superiori a 75 GB di dati non compressi, verranno creati più file ZIP.</span><span class="sxs-lookup"><span data-stu-id="1adc5-146">For exports larger than 75 GB of uncompressed data, multiple ZIP files will be created.</span></span> <span data-ttu-id="1adc5-147">Una volta scaricati, i file ZIP possono essere decompressi in un'unica posizione per ricreare l'esportazione completa.</span><span class="sxs-lookup"><span data-stu-id="1adc5-147">Once downloaded, the ZIP files can be uncompressed into a single location to recreate the full export.</span></span>

### <a name="loose-files-and-pst-export-structure"></a><span data-ttu-id="1adc5-148">File con estensione loose e struttura di esportazione PST</span><span class="sxs-lookup"><span data-stu-id="1adc5-148">Loose files and PST export structure</span></span>

<span data-ttu-id="1adc5-149">Se si seleziona questa opzione di esportazione, il contenuto esportato viene organizzato nella struttura seguente:</span><span class="sxs-lookup"><span data-stu-id="1adc5-149">If you select this export option, the exported content is organized in the following structure:</span></span>

- <span data-ttu-id="1adc5-150">Summary.csv: include un riepilogo del contenuto esportato dal set di recensioni</span><span class="sxs-lookup"><span data-stu-id="1adc5-150">Summary.csv: Includes a summary of the content exported from the review set</span></span>

- <span data-ttu-id="1adc5-151">Cartella radice: questa cartella denominata [Nome esportazione] x di z.zip e verrà ripetuta per ogni partizione del file ZIP.</span><span class="sxs-lookup"><span data-stu-id="1adc5-151">Root folder: This folder in named [Export Name] x of z.zip and will be repeated for each ZIP file partition.</span></span>
  
  - <span data-ttu-id="1adc5-152">Export_load_file_x di z.csv: il file di metadati.</span><span class="sxs-lookup"><span data-stu-id="1adc5-152">Export_load_file_x of z.csv: The metadata file.</span></span>
  
  - <span data-ttu-id="1adc5-153">Avvisi ed errori x di z.csv: questo file include informazioni sugli errori rilevati durante il tentativo di esportazione dal set di revisione.</span><span class="sxs-lookup"><span data-stu-id="1adc5-153">Warnings and errors x of z.csv: This file includes information about errors encountered when trying to export from the review set.</span></span>
  
  - <span data-ttu-id="1adc5-154">Exchange: questa cartella contiene tutto il contenuto Exchange archiviati nei file PST.</span><span class="sxs-lookup"><span data-stu-id="1adc5-154">Exchange: This folder contains all content from Exchange stored in PST files.</span></span> <span data-ttu-id="1adc5-155">I file PDF redatti non possono essere inclusi con questa opzione.</span><span class="sxs-lookup"><span data-stu-id="1adc5-155">Redacted PDF files cannot be included with this option.</span></span> <span data-ttu-id="1adc5-156">Se nel set di revisioni è selezionato un allegato, il messaggio di posta elettronica padre verrà esportato con l'allegato allegato.</span><span class="sxs-lookup"><span data-stu-id="1adc5-156">If an attachment is selected in the review set, the parent email will be exported with the attachment attached.</span></span>
  
  - <span data-ttu-id="1adc5-157">SharePoint: questa cartella contiene tutto il contenuto nativo di SharePoint in un formato di file nativo.</span><span class="sxs-lookup"><span data-stu-id="1adc5-157">SharePoint: This folder contains all native content from SharePoint in a native file format.</span></span> <span data-ttu-id="1adc5-158">I file PDF redatti non possono essere inclusi con questa opzione.</span><span class="sxs-lookup"><span data-stu-id="1adc5-158">Redacted PDF files cannot be included with this option.</span></span>

### <a name="condensed-directory-structure"></a><span data-ttu-id="1adc5-159">Struttura di directory compressa</span><span class="sxs-lookup"><span data-stu-id="1adc5-159">Condensed directory structure</span></span>

- <span data-ttu-id="1adc5-160">Summary.csv: include un riepilogo del contenuto esportato dal set di recensioni</span><span class="sxs-lookup"><span data-stu-id="1adc5-160">Summary.csv: Includes a summary of the content exported from the review set</span></span>

- <span data-ttu-id="1adc5-161">Cartella radice: questa cartella denominata [Nome esportazione] x di z.zip e verrà ripetuta per ogni partizione del file ZIP.</span><span class="sxs-lookup"><span data-stu-id="1adc5-161">Root folder: This folder in named [Export Name] x of z.zip and will be repeated for each ZIP file partition.</span></span>
  
  - <span data-ttu-id="1adc5-162">Export_load_file_x di z.csv: il file di metadati e include anche il percorso di ogni file archiviato nel file ZIP.</span><span class="sxs-lookup"><span data-stu-id="1adc5-162">Export_load_file_x of z.csv: The metadata file and also includes the location of each file that is stored in the ZIP file.</span></span>
  
  - <span data-ttu-id="1adc5-163">Avvisi ed errori x di z.csv: questo file include informazioni sugli errori rilevati durante il tentativo di esportazione dal set di revisione.</span><span class="sxs-lookup"><span data-stu-id="1adc5-163">Warnings and errors x of z.csv: This file includes information about errors encountered when trying to export from the review set.</span></span>

  - <span data-ttu-id="1adc5-164">NativeFiles: questa cartella contiene tutti i file nativi esportati.</span><span class="sxs-lookup"><span data-stu-id="1adc5-164">NativeFiles: This folder contains all the native files that were exported.</span></span> <span data-ttu-id="1adc5-165">I file nativi vengono sostituiti con PDF redatti se è stata selezionata l'opzione Sostituisci i nativi con i *PDF convertiti.*</span><span class="sxs-lookup"><span data-stu-id="1adc5-165">Natives files are replaced with redacted PDFs if you selected the *Replace redacted natives with converted PDFs* option.</span></span>
  
  - <span data-ttu-id="1adc5-166">Error_files: questa cartella contiene file con errore di estrazione o di altro tipo.</span><span class="sxs-lookup"><span data-stu-id="1adc5-166">Error_files: This folder contains files that had either extraction or other processing error.</span></span> <span data-ttu-id="1adc5-167">I file verranno inseriti in cartelle separate, ExtractionError o ProcessingError.</span><span class="sxs-lookup"><span data-stu-id="1adc5-167">The files will be placed into separate folders, either ExtractionError or ProcessingError.</span></span> <span data-ttu-id="1adc5-168">Questi file sono elencati nel file di caricamento.</span><span class="sxs-lookup"><span data-stu-id="1adc5-168">These files are listed in the load file.</span></span>

  - <span data-ttu-id="1adc5-169">Extracted_text_files: questa cartella contiene tutti i file di testo estratti generati durante l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="1adc5-169">Extracted_text_files: This folder contains all of the extracted text files that were generated at processing.</span></span>

### <a name="condensed-directory-structure-exported-to-your-azure-storage-account"></a><span data-ttu-id="1adc5-170">Struttura di directory compressa esportata nell'Archiviazione di Azure account</span><span class="sxs-lookup"><span data-stu-id="1adc5-170">Condensed directory structure exported to your Azure Storage Account</span></span>

<span data-ttu-id="1adc5-171">Questa opzione utilizza la stessa struttura generale della struttura di *directory* condensata, tuttavia il contenuto non viene compresso e i dati vengono salvati nel Archiviazione di Azure account.</span><span class="sxs-lookup"><span data-stu-id="1adc5-171">This option uses the same general structure as the *Condensed directory structure*, however the contents is not zipped and the data is saved to your Azure Storage account.</span></span> <span data-ttu-id="1adc5-172">Questa opzione viene in genere utilizzata quando si utilizza un provider di eDiscovery di terze parti.</span><span class="sxs-lookup"><span data-stu-id="1adc5-172">This option is generally used when working with a third-party eDiscovery provider.</span></span> <span data-ttu-id="1adc5-173">Per informazioni dettagliate su come utilizzare questa opzione, vedere [Export documents in a review set to an Archiviazione di Azure account](download-export-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="1adc5-173">For details about how to use this option, see [Export documents in a review set to an Azure Storage account](download-export-jobs.md).</span></span>
