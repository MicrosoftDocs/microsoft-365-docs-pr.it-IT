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
description: Informazioni su come selezionare ed esportare o scaricare contenuto da un set di revisione per presentazioni o recensioni esterne.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 29c2224a1ce0a92bca3b2057352f6f82fdc7afde
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034094"
---
# <a name="export-documents-from-a-review-set"></a><span data-ttu-id="34b30-103">Esportare i documenti da un insieme da rivedere</span><span class="sxs-lookup"><span data-stu-id="34b30-103">Export documents from a review set</span></span>

<span data-ttu-id="34b30-104">È possibile esportare il contenuto per la presentazione o la revisione esterna da un set di revisione tramite uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="34b30-104">You can export content for presentation or external review from a review set by one of the following methods:</span></span>

- [<span data-ttu-id="34b30-105">Scaricare documenti</span><span class="sxs-lookup"><span data-stu-id="34b30-105">Download documents</span></span>](#download-documents-from-a-review-set)
 
- [<span data-ttu-id="34b30-106">Esportare documenti</span><span class="sxs-lookup"><span data-stu-id="34b30-106">Export documents</span></span>](#export-documents-from-a-review-set)

## <a name="download-documents-from-a-review-set"></a><span data-ttu-id="34b30-107">Scaricare i documenti da un set di Revisione</span><span class="sxs-lookup"><span data-stu-id="34b30-107">Download documents from a review set</span></span>

<span data-ttu-id="34b30-108">Download offre un modo semplice per scaricare contenuto da un set di recensioni in formato nativo.</span><span class="sxs-lookup"><span data-stu-id="34b30-108">Download offers a simple way to download content from a review set in Native format.</span></span> <span data-ttu-id="34b30-109">Sfrutta le caratteristiche di trasferimento dei dati del browser in modo che una richiesta del browser venga visualizzata una volta che il download è pronto.</span><span class="sxs-lookup"><span data-stu-id="34b30-109">It leverages the browser's data transfer features so a browser prompt will appear once a download is ready.</span></span> <span data-ttu-id="34b30-110">I file scaricati con questo metodo verranno zippati in un file contenitore e saranno file a livello di elemento.</span><span class="sxs-lookup"><span data-stu-id="34b30-110">Files downloaded using this method will be zipped into a container file and will be item level files.</span></span> <span data-ttu-id="34b30-111">Questo significa che se si seleziona un allegato, verrà visualizzato automaticamente il messaggio di posta elettronica con l'allegato incluso.</span><span class="sxs-lookup"><span data-stu-id="34b30-111">This means that if you select an attachment, you will automatically receive the email with the attachment included.</span></span> <span data-ttu-id="34b30-112">Analogamente, se si seleziona un foglio di calcolo di Excel incorporato in un documento di Word, verrà visualizzato il documento di Word con il foglio di calcolo di Excel incorporato.</span><span class="sxs-lookup"><span data-stu-id="34b30-112">Similarly, if you select an excel spreadsheet that was embedded in a word document, you will receive the word document with the excel spreadsheet embedded.</span></span> <span data-ttu-id="34b30-113">Gli elementi scaricati conserveranno la data dell'Ultima modifica che può essere visualizzata come proprietà di un file.</span><span class="sxs-lookup"><span data-stu-id="34b30-113">Downloaded items will preserve the last modified date which can be viewed as a file property.</span></span>

<span data-ttu-id="34b30-114">Per scaricare contenuto da un set di recensioni, iniziare selezionando i file che si desidera scaricare, quindi selezionare "Scarica" dal menu azioni.</span><span class="sxs-lookup"><span data-stu-id="34b30-114">To download content from a review set, start by selecting the files you want to download then select "Download" under the Actions menu.</span></span>

![Schermata di una descrizione del computer generata automaticamente](../media/eDiscoDownload.png)

## <a name="export-documents-from-a-review-set"></a><span data-ttu-id="34b30-116">Esportare i documenti da un insieme da rivedere</span><span class="sxs-lookup"><span data-stu-id="34b30-116">Export documents from a review set</span></span>

<span data-ttu-id="34b30-117">Export consente agli utenti di personalizzare il contenuto incluso nel pacchetto di download.</span><span class="sxs-lookup"><span data-stu-id="34b30-117">Export allows users to customize the content that is included in the download package.</span></span> <span data-ttu-id="34b30-118">Fornisce una pagina di configurazione con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="34b30-118">It provides a configuration page with the following settings:</span></span>

### <a name="metadata-file"></a><span data-ttu-id="34b30-119">File di metadati</span><span class="sxs-lookup"><span data-stu-id="34b30-119">Metadata file</span></span>

<span data-ttu-id="34b30-120">Questo può essere considerato come il "Load file" che contiene i metadati associati ai file che vengono esportati.</span><span class="sxs-lookup"><span data-stu-id="34b30-120">This can be considered your "load file" that contains metadata associated with the files you export.</span></span> <span data-ttu-id="34b30-121">Per un elenco dei campi esportati disponibili nel file di metadati, vedere [Document Metadata Fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span><span class="sxs-lookup"><span data-stu-id="34b30-121">For a list of exported fields available in the metadata file, see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span></span> <span data-ttu-id="34b30-122">Questo file può in genere essere ingerito da strumenti di terze parti.</span><span class="sxs-lookup"><span data-stu-id="34b30-122">This file can typically be ingested by third-party tools.</span></span>

### <a name="tag-data"></a><span data-ttu-id="34b30-123">Dati tag</span><span class="sxs-lookup"><span data-stu-id="34b30-123">Tag data</span></span>

<span data-ttu-id="34b30-124">Questo contenuto verrebbe aggiunto come campi nel file di metadati.</span><span class="sxs-lookup"><span data-stu-id="34b30-124">This content would be added as fields in the metadata file.</span></span> <span data-ttu-id="34b30-125">Contiene tutte le informazioni sui tag applicate nei set di revisione.</span><span class="sxs-lookup"><span data-stu-id="34b30-125">It contains all of the tag information applied in review sets.</span></span>

### <a name="text-files"></a><span data-ttu-id="34b30-126">File di testo</span><span class="sxs-lookup"><span data-stu-id="34b30-126">Text files</span></span>

<span data-ttu-id="34b30-127">È possibile generare file di testo per ogni file esportato da un set di revisione.</span><span class="sxs-lookup"><span data-stu-id="34b30-127">Text files can be generated for each file exported from a review set.</span></span> <span data-ttu-id="34b30-128">Spesso questi file sono necessari per i partner del servizio come parte dell'ingestione dei dati in strumenti di terze parti.</span><span class="sxs-lookup"><span data-stu-id="34b30-128">Often times these files are required by service partners as part of ingesting data into third-party tools.</span></span>

### <a name="redacted-files"></a><span data-ttu-id="34b30-129">File redatti</span><span class="sxs-lookup"><span data-stu-id="34b30-129">Redacted files</span></span>

<span data-ttu-id="34b30-130">Se durante la revisione vengono generati file PDF redatti, tali file sono disponibili durante l'esportazione.</span><span class="sxs-lookup"><span data-stu-id="34b30-130">If redacted PDF files are generated during review, these files are available during export.</span></span> <span data-ttu-id="34b30-131">È possibile decidere se esportare solo i file nativi o sostituire i file nativi che richiedono la redazione con i file PDF che contengono le redazioni effettive.</span><span class="sxs-lookup"><span data-stu-id="34b30-131">You can decide whether to export native files only or to replace the native files that required redaction with the PDF files that contain the actual redactions.</span></span>

### <a name="export-location"></a><span data-ttu-id="34b30-132">Percorso di esportazione</span><span class="sxs-lookup"><span data-stu-id="34b30-132">Export location</span></span>

<span data-ttu-id="34b30-133">Il contenuto esportato viene recapitato a un BLOB di Azure fornito da Microsoft o è possibile utilizzare il BLOB di un cliente se i dettagli vengono forniti all'esportazione.</span><span class="sxs-lookup"><span data-stu-id="34b30-133">Exported content is delivered to either a Microsoft provided Azure blob or a customer's blob can be used if the details are provided at export.</span></span>

### <a name="export-structure"></a><span data-ttu-id="34b30-134">Struttura di esportazione</span><span class="sxs-lookup"><span data-stu-id="34b30-134">Export structure</span></span>

<span data-ttu-id="34b30-135">Quando il contenuto viene esportato da un set di revisione, il contenuto è organizzato nella struttura seguente.</span><span class="sxs-lookup"><span data-stu-id="34b30-135">When content is exported from a review set, the content is organized in the following structure.</span></span>

  - <span data-ttu-id="34b30-136">Cartella radice-ID download</span><span class="sxs-lookup"><span data-stu-id="34b30-136">Root folder – Download ID</span></span>
    
      - <span data-ttu-id="34b30-137">Esporta\_caricamento\_file. csv = file di metadati</span><span class="sxs-lookup"><span data-stu-id="34b30-137">Export\_load\_file.csv = metadata file</span></span>
    
      - <span data-ttu-id="34b30-138">Summary. txt = un file di riepilogo con statistiche di esportazione</span><span class="sxs-lookup"><span data-stu-id="34b30-138">Summary.txt = a summary file with export statistics</span></span>
    
      - <span data-ttu-id="34b30-139">Input\_o file\_nativi = contiene tutti i file nativi</span><span class="sxs-lookup"><span data-stu-id="34b30-139">Input\_or native\_files = contains all native files</span></span>
    
      - <span data-ttu-id="34b30-140">File\_Error = contiene eventuali file di errore inclusi nell'esportazione</span><span class="sxs-lookup"><span data-stu-id="34b30-140">Error\_files = contains any error files included in the export</span></span>
        
          - <span data-ttu-id="34b30-141">ExtractionError – un CSV che contiene i metadati disponibili di file che non sono stati estratti correttamente dai file padre</span><span class="sxs-lookup"><span data-stu-id="34b30-141">ExtractionError – a csv that contains any available metadata of files that were not properly extracted from parent files</span></span>
        
          - <span data-ttu-id="34b30-142">ProcessingError – contenuto con errori di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="34b30-142">ProcessingError – content with processing errors.</span></span> <span data-ttu-id="34b30-143">Questo contenuto è a livello di elemento significato se un allegato ha subito un errore di elaborazione, il messaggio di posta elettronica che contiene l'allegato verrà incluso in questa cartella.</span><span class="sxs-lookup"><span data-stu-id="34b30-143">This content is item level meaning if an attachment experienced a processing error, the email that contains the attachment will be included in this folder.</span></span>
    
      - <span data-ttu-id="34b30-144">File\_di\_testo estratti = contiene tutti i file di testo estratti generati durante l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="34b30-144">Extracted\_text\_files = contains all of the extracted text files generated at processing.</span></span>
