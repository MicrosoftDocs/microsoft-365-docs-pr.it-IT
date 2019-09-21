---
title: Esportare i documenti da un insieme da rivedere
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
description: ''
ms.openlocfilehash: cf8b11fa82398ab8cfa3981064741d0dbf349f71
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37083638"
---
# <a name="export-documents-from-a-review-set"></a><span data-ttu-id="d52ca-102">Esportare i documenti da un insieme da rivedere</span><span class="sxs-lookup"><span data-stu-id="d52ca-102">Export documents from a review set</span></span>

<span data-ttu-id="d52ca-103">È possibile esportare il contenuto per la presentazione o la revisione esterna da un set di revisione tramite uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="d52ca-103">You can export content for presentation or external review from a review set by one of the following methods:</span></span>

- [<span data-ttu-id="d52ca-104">Scaricare documenti</span><span class="sxs-lookup"><span data-stu-id="d52ca-104">Download documents</span></span>](#download-documents-from-a-review-set)
 
- [<span data-ttu-id="d52ca-105">Esportare documenti</span><span class="sxs-lookup"><span data-stu-id="d52ca-105">Export documents</span></span>](#export-documents-from-a-review-set)

## <a name="download-documents-from-a-review-set"></a><span data-ttu-id="d52ca-106">Scaricare i documenti da un set di Revisione</span><span class="sxs-lookup"><span data-stu-id="d52ca-106">Download documents from a review set</span></span>

<span data-ttu-id="d52ca-107">Download offre un modo semplice per scaricare contenuto da un set di recensioni in formato nativo.</span><span class="sxs-lookup"><span data-stu-id="d52ca-107">Download offers a simple way to download content from a review set in Native format.</span></span> <span data-ttu-id="d52ca-108">Sfrutta le caratteristiche di trasferimento dei dati del browser in modo che una richiesta del browser venga visualizzata una volta che il download è pronto.</span><span class="sxs-lookup"><span data-stu-id="d52ca-108">It leverages the browser’s data transfer features so a browser prompt will appear once a download is ready.</span></span> <span data-ttu-id="d52ca-109">I file scaricati con questo metodo verranno zippati in un file contenitore e saranno file a livello di elemento.</span><span class="sxs-lookup"><span data-stu-id="d52ca-109">Files downloaded using this method will be zipped into a container file and will be item level files.</span></span> <span data-ttu-id="d52ca-110">Questo significa che se si seleziona un allegato, verrà visualizzato automaticamente il messaggio di posta elettronica con l'allegato incluso.</span><span class="sxs-lookup"><span data-stu-id="d52ca-110">This means that if you select an attachment, you will automatically receive the email with the attachment included.</span></span> <span data-ttu-id="d52ca-111">Analogamente, se si seleziona un foglio di calcolo di Excel incorporato in un documento di Word, verrà visualizzato il documento di Word con il foglio di calcolo di Excel incorporato.</span><span class="sxs-lookup"><span data-stu-id="d52ca-111">Similarly, if you select an excel spreadsheet that was embedded in a word document, you will receive the word document with the excel spreadsheet embedded.</span></span> <span data-ttu-id="d52ca-112">Gli elementi scaricati conserveranno la data dell'Ultima modifica che può essere visualizzata come proprietà di un file.</span><span class="sxs-lookup"><span data-stu-id="d52ca-112">Downloaded items will preserve the last modified date which can be viewed as a file property.</span></span>

<span data-ttu-id="d52ca-113">Per scaricare contenuto da un set di recensioni, iniziare selezionando i file che si desidera scaricare, quindi selezionare "Scarica" dal menu azioni.</span><span class="sxs-lookup"><span data-stu-id="d52ca-113">To download content from a review set, start by selecting the files you want to download then select “Download” under the Actions menu.</span></span>

![Schermata di una descrizione del computer generata automaticamente](media/eDiscoDownload.png)

## <a name="export-documents-from-a-review-set"></a><span data-ttu-id="d52ca-115">Esportare i documenti da un insieme da rivedere</span><span class="sxs-lookup"><span data-stu-id="d52ca-115">Export documents from a review set</span></span>

<span data-ttu-id="d52ca-116">Export consente agli utenti di personalizzare il contenuto incluso nel pacchetto di download.</span><span class="sxs-lookup"><span data-stu-id="d52ca-116">Export allows users to customize the content that is included in the download package.</span></span> <span data-ttu-id="d52ca-117">Fornisce una pagina di configurazione con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="d52ca-117">It provides a configuration page with the following settings:</span></span>

### <a name="metadata-file"></a><span data-ttu-id="d52ca-118">File di metadati</span><span class="sxs-lookup"><span data-stu-id="d52ca-118">Metadata file</span></span>

<span data-ttu-id="d52ca-119">Questo può essere considerato come il "Load file" che contiene i metadati associati ai file esportati.</span><span class="sxs-lookup"><span data-stu-id="d52ca-119">This can be considered your “load file” that contains metadata associated with the files you exported.</span></span> <span data-ttu-id="d52ca-120">Per un elenco dei campi disponibili nel file di metadati, vedere \[link\].</span><span class="sxs-lookup"><span data-stu-id="d52ca-120">For a list of fields available in the metadata file, see \[link\].</span></span> <span data-ttu-id="d52ca-121">Questo file può in genere essere ingerito da<sup>3 strumenti</sup> di terze parti a valle.</span><span class="sxs-lookup"><span data-stu-id="d52ca-121">This file can typically be ingested by 3<sup>rd</sup> party tools downstream.</span></span>

### <a name="tag-data"></a><span data-ttu-id="d52ca-122">Dati tag</span><span class="sxs-lookup"><span data-stu-id="d52ca-122">Tag data</span></span>

<span data-ttu-id="d52ca-123">Questo contenuto verrebbe aggiunto come campi nel file di metadati.</span><span class="sxs-lookup"><span data-stu-id="d52ca-123">This content would be added as fields in the metadata file.</span></span> <span data-ttu-id="d52ca-124">Contiene tutte le informazioni sui tag applicate nei set di revisione.</span><span class="sxs-lookup"><span data-stu-id="d52ca-124">It contains all of the tag information applied in review sets.</span></span>

### <a name="text-files"></a><span data-ttu-id="d52ca-125">File di testo</span><span class="sxs-lookup"><span data-stu-id="d52ca-125">Text files</span></span>

<span data-ttu-id="d52ca-126">È possibile generare file di testo per ogni file esportato da un set di revisione.</span><span class="sxs-lookup"><span data-stu-id="d52ca-126">Text files can be generated for each file exported from a review set.</span></span> <span data-ttu-id="d52ca-127">Spesso questi file sono necessari per i partner del servizio come parte dell'ingestione dei dati<sup>in 3 strumenti</sup> di terze parti a valle.</span><span class="sxs-lookup"><span data-stu-id="d52ca-127">Often times these files are required by service partners as part of ingesting data into 3<sup>rd</sup> party tools downstream.</span></span>

### <a name="redacted-files"></a><span data-ttu-id="d52ca-128">File redatti</span><span class="sxs-lookup"><span data-stu-id="d52ca-128">Redacted files</span></span>

<span data-ttu-id="d52ca-129">Se durante la revisione vengono generati file PDF ritirati, questi sono disponibili durante l'esportazione.</span><span class="sxs-lookup"><span data-stu-id="d52ca-129">If redacted PDFs are generated during review, these files are available during export.</span></span> <span data-ttu-id="d52ca-130">Gli utenti possono decidere se esportare solo i file nativi o sostituire i nativi che dispongono di redazioni con il masterizzato nei file PDF.</span><span class="sxs-lookup"><span data-stu-id="d52ca-130">Users can decide whether to export native files only or to replace natives that have redactions with the burned in PDFs.</span></span>

### <a name="export-location"></a><span data-ttu-id="d52ca-131">Percorso di esportazione</span><span class="sxs-lookup"><span data-stu-id="d52ca-131">Export Location</span></span>

<span data-ttu-id="d52ca-132">Il contenuto esportato viene recapitato a un BLOB di Azure fornito da Microsoft o è possibile utilizzare il BLOB di un cliente se i dettagli vengono forniti all'esportazione.</span><span class="sxs-lookup"><span data-stu-id="d52ca-132">Exported content is delivered to either a Microsoft provided Azure blob or a customer’s blob can be used if the details are provided at export.</span></span>

### <a name="export-structure"></a><span data-ttu-id="d52ca-133">Struttura di esportazione</span><span class="sxs-lookup"><span data-stu-id="d52ca-133">Export Structure</span></span>

<span data-ttu-id="d52ca-134">Quando il contenuto viene esportato da un set di revisione, il contenuto è organizzato nella struttura seguente.</span><span class="sxs-lookup"><span data-stu-id="d52ca-134">When content is exported from a review set, the content is organized in the following structure.</span></span>

  - <span data-ttu-id="d52ca-135">Cartella radice-ID download</span><span class="sxs-lookup"><span data-stu-id="d52ca-135">Root folder – Download ID</span></span>
    
      - <span data-ttu-id="d52ca-136">Esporta\_caricamento\_file. csv = file di metadati</span><span class="sxs-lookup"><span data-stu-id="d52ca-136">Export\_load\_file.csv = metadata file</span></span>
    
      - <span data-ttu-id="d52ca-137">Summary. txt = un file di riepilogo con statistiche di esportazione</span><span class="sxs-lookup"><span data-stu-id="d52ca-137">Summary.txt = a summary file with export statistics</span></span>
    
      - <span data-ttu-id="d52ca-138">Input\_o file\_nativi = contiene tutti i file nativi</span><span class="sxs-lookup"><span data-stu-id="d52ca-138">Input\_or native\_files = contains all native files</span></span>
    
      - <span data-ttu-id="d52ca-139">File\_Error = contiene eventuali file di errore inclusi nell'esportazione</span><span class="sxs-lookup"><span data-stu-id="d52ca-139">Error\_files = contains any error files included in the export</span></span>
        
          - <span data-ttu-id="d52ca-140">ExtractionError – un CSV che contiene i metadati disponibili di file che non sono stati estratti correttamente dai file padre</span><span class="sxs-lookup"><span data-stu-id="d52ca-140">ExtractionError – a csv that contains any available metadata of files that were not properly extracted from parent files</span></span>
        
          - <span data-ttu-id="d52ca-141">ProcessingError – contenuto con errori di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="d52ca-141">ProcessingError – content with processing errors.</span></span> <span data-ttu-id="d52ca-142">Questo contenuto è a livello di elemento significato se un allegato ha subito un errore di elaborazione, il messaggio di posta elettronica che contiene l'allegato verrà incluso in questa cartella.</span><span class="sxs-lookup"><span data-stu-id="d52ca-142">This content is item level meaning if an attachment experienced a processing error, the email that contains the attachment will be included in this folder.</span></span>
    
      - <span data-ttu-id="d52ca-143">File\_di\_testo estratti = contiene tutti i file di testo estratti generati durante l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="d52ca-143">Extracted\_text\_files = contains all of the extracted text files generated at processing.</span></span>