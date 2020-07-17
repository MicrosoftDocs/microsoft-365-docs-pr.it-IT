---
title: Eseguire il modulo di processo in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: dbc1e251-0596-443b-ac9b-f398ba955b73
description: Informazioni sulle linee guida per la preparazione dei file di dati per l'analisi con Advanced eDiscovery.
ms.openlocfilehash: 5130bea7da8922fd7e98d07696ffde3930d2ce41
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936199"
---
# <a name="run-the-process-module-in-advanced-ediscovery-classic"></a><span data-ttu-id="c4890-103">Eseguire il modulo di processo in Advanced eDiscovery (Classic)</span><span class="sxs-lookup"><span data-stu-id="c4890-103">Run the Process module in Advanced eDiscovery (classic)</span></span>

<span data-ttu-id="c4890-104">I file dei casi vengono caricati in Advanced eDiscovery durante la **preparazione** del \> **processo**.</span><span class="sxs-lookup"><span data-stu-id="c4890-104">Case files are loaded into the Advanced eDiscovery during **Prepare** \> **Process**.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="c4890-p101">Per usare Advanced eDiscovery è necessario avere Office 365 E3 con il componente aggiuntivo Advanced Compliance o un abbonamento E5 dell'organizzazione. Se non si ha questo piano e si desidera provare Advanced eDiscovery, è possibile [richiedere una valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="c4890-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
## <a name="guidelines-preparing-data-for-advanced-ediscovery"></a><span data-ttu-id="c4890-107">Linee guida: preparazione dei dati per Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="c4890-107">Guidelines: Preparing data for Advanced eDiscovery</span></span>

- <span data-ttu-id="c4890-108">**Qualità**: identificare chiaramente la popolazione dei file del caso pertinente per il caso.</span><span class="sxs-lookup"><span data-stu-id="c4890-108">**Quality**: Clearly identify the case file population pertinent to the case.</span></span>
    
- <span data-ttu-id="c4890-109">**Carichi**: caricare i file in un percorso accessibile a Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="c4890-109">**Loads**: Load the files into a location that is accessible to Advanced eDiscovery.</span></span>
    
- <span data-ttu-id="c4890-110">**ID file**: un identificatore di file univoco in Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="c4890-110">**File ID**: A unique file identifier in Advanced eDiscovery.</span></span> <span data-ttu-id="c4890-111">Se non è stato importato alcun identificatore di file, Advanced eDiscovery genera automaticamente l'ID.</span><span class="sxs-lookup"><span data-stu-id="c4890-111">If no file identifier is imported, Advanced eDiscovery automatically generates the ID.</span></span> <span data-ttu-id="c4890-112">Se si mappa l'ID in un carico di processo successivo e si mappa un percorso diverso da quello del caricamento del processo iniziale, Advanced eDiscovery sostituirà il percorso (invece di aggiungere una nuova voce di file).</span><span class="sxs-lookup"><span data-stu-id="c4890-112">If you map the ID in a subsequent Process load, and map a different path than in the initial Process load, Advanced eDiscovery will replace the path (rather than add a new file entry).</span></span> <span data-ttu-id="c4890-113">L'ID può essere utilizzato come riferimento nel processo di esportazione.</span><span class="sxs-lookup"><span data-stu-id="c4890-113">The ID can be used as a reference in the Export process.</span></span> <span data-ttu-id="c4890-114">Il valore dell'ID non deve essere "-1".</span><span class="sxs-lookup"><span data-stu-id="c4890-114">The ID value should not be "-1".</span></span>
    
- <span data-ttu-id="c4890-115">**MD5**: questa firma viene utilizzata per distinguere i file (due file non vengono considerati duplicati esatti, a meno che non dispongano dello stesso MD5).</span><span class="sxs-lookup"><span data-stu-id="c4890-115">**MD5**: This signature is used to differentiate between files (two files are not considered exact duplicates unless they have the same MD5).</span></span> <span data-ttu-id="c4890-116">Per impostazione predefinita, Advanced eDiscovery calcola l'MD5 dei file.</span><span class="sxs-lookup"><span data-stu-id="c4890-116">By default, Advanced eDiscovery calculates the MD5 of files.</span></span> <span data-ttu-id="c4890-117">Quando i file caricati sono file di testo, è consigliabile caricare e mappare il valore MD5 originale anziché calcolarlo in Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="c4890-117">When the loaded files are text files, it is recommended to load and map the original MD5 value instead of calculating it in Advanced eDiscovery.</span></span>
    
- <span data-ttu-id="c4890-118">**Tipo di file e nome**:</span><span class="sxs-lookup"><span data-stu-id="c4890-118">**File type and name**:</span></span>
    
  - <span data-ttu-id="c4890-119">Advanced eDiscovery è in grado di elaborare file di vari formati ed estrarre i file nativi caricati in un formato standard, ad esempio \* . TXT, HTML o. XML.</span><span class="sxs-lookup"><span data-stu-id="c4890-119">Advanced eDiscovery can process files of various formats and extract loaded native files into a standard format, such as \*.TXT, HTML, or .XML.</span></span> <span data-ttu-id="c4890-120">L'elaborazione dei file di testo è più veloce rispetto ai file nativi.</span><span class="sxs-lookup"><span data-stu-id="c4890-120">Processing of text files is faster than native files.</span></span> <span data-ttu-id="c4890-121">I file di testo estratti vengono archiviati nella cartella case.</span><span class="sxs-lookup"><span data-stu-id="c4890-121">Extracted text files are stored in the case folder.</span></span>
    
  - <span data-ttu-id="c4890-122">Non caricare file che non possono essere estratti, ad esempio file di sistema o immagini grafiche.</span><span class="sxs-lookup"><span data-stu-id="c4890-122">Do not load files that cannot be extracted, such as system files or graphic images.</span></span> <span data-ttu-id="c4890-123">Questi file potrebbero ritardare l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="c4890-123">These files may delay processing.</span></span>
    
  - <span data-ttu-id="c4890-124">Verificare che i nomi dei file siano denominati in modo significativo e i percorsi siano corretti.</span><span class="sxs-lookup"><span data-stu-id="c4890-124">Verify that file names are significantly named and paths are correct.</span></span>
    
- <span data-ttu-id="c4890-125">**Percorso file**: Advanced eDiscovery è in grado di caricare file con lunghezze di percorso fino a 400 caratteri.</span><span class="sxs-lookup"><span data-stu-id="c4890-125">**File path**: Advanced eDiscovery can load files with path lengths up to 400 characters.</span></span>
    
- <span data-ttu-id="c4890-126">**Estrazione**del testo: quando si estrae del testo da file nativi, oltre al testo normale, vengono estratti anche i seguenti elementi: testo nascosto (Excel e. doc), colonne nascoste (Excel), rilevamento delle modifiche (file con estensione doc), note degli altoparlanti (con estensione ppt), oggetti incorporati (ad esempio, oggetti di Excel in a. ppt).</span><span class="sxs-lookup"><span data-stu-id="c4890-126">**Text extraction**: When extracting text from native files, in addition to normal text, the following are also extracted: hidden text (Excel and .doc), hidden columns (Excel), track changes (.doc), speaker notes (.ppt), embedded objects (for example, Excel objects in a .ppt).</span></span> <span data-ttu-id="c4890-127">Questi possono essere visualizzati nell'editor di testo.</span><span class="sxs-lookup"><span data-stu-id="c4890-127">These can be viewed in the Text editor.</span></span>
    
- <span data-ttu-id="c4890-128">**Ignora testo**: questa funzionalità facoltativa è definita dopo l'esecuzione del processo e prima dell'analisi.</span><span class="sxs-lookup"><span data-stu-id="c4890-128">**Ignore Text**: This optional feature is defined after Process is run and before Analyze.</span></span> <span data-ttu-id="c4890-129">Ignorare il testo deve essere utilizzato con cautela perché il relativo utilizzo può ridurre le prestazioni dell'analisi dei file.</span><span class="sxs-lookup"><span data-stu-id="c4890-129">Ignore text should be used with caution because its use may reduce the performance of file analysis.</span></span>
    
- <span data-ttu-id="c4890-130">**Testo multilingue**: Advanced eDiscovery attualmente non gestisce i nomi multilingue per i tag, il custode e i problemi.</span><span class="sxs-lookup"><span data-stu-id="c4890-130">**Multilingual text**: Advanced eDiscovery does not currently handle multilingual names for tags, custodian, and issues.</span></span>
    
- <span data-ttu-id="c4890-131">**Metadati**: determinare se sono presenti metadati che si desidera salvare nel database dei casi per riferimento futuro, ad esempio l'intervallo di date, le dimensioni dei file, il tipo di file, il custode e l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="c4890-131">**Metadata**: Determine if there is metadata that you want to save in the case database for future reference, such as date range, file size, file type, custodian, and subject.</span></span> <span data-ttu-id="c4890-132">I metadati possono essere caricati dopo che i file sono già stati caricati senza rieseguire l'inventario o l'aggiunta di un sovraccarico di rielaborazione.</span><span class="sxs-lookup"><span data-stu-id="c4890-132">Metadata can be loaded after files were already loaded without rerunning the inventory or adding reprocessing overhead.</span></span> 
    
  - <span data-ttu-id="c4890-133">Se i file sono stati caricati originariamente in base al percorso, mappare la colonna percorso quando si importano successivamente i metadati.</span><span class="sxs-lookup"><span data-stu-id="c4890-133">If the files were originally loaded by path, map the path column when later importing metadata.</span></span> <span data-ttu-id="c4890-134">È possibile fare riferimento al file in base all'ID e mappare un percorso diverso.</span><span class="sxs-lookup"><span data-stu-id="c4890-134">It is possible to refer to the file by ID and to map a different path.</span></span> <span data-ttu-id="c4890-135">Questo è uno scenario utile quando si modificano i percorsi dei file.</span><span class="sxs-lookup"><span data-stu-id="c4890-135">This is a useful scenario when the file paths change.</span></span>
    
  - <span data-ttu-id="c4890-136">Se i file sono stati originariamente caricati da ID file, mappare la colonna ID durante il caricamento dei metadati.</span><span class="sxs-lookup"><span data-stu-id="c4890-136">If the files were originally loaded by File ID, map the ID column when loading metadata.</span></span> <span data-ttu-id="c4890-137">Se si fa riferimento al file in base al percorso (anziché all'ID), i file verranno caricati di nuovo con un ID diverso.</span><span class="sxs-lookup"><span data-stu-id="c4890-137">Referring to the file by path (instead of ID) will cause files to be re-loaded with a different ID.</span></span> <span data-ttu-id="c4890-138">Advanced eDiscovery consente di creare copie dei file anziché i metadati di caricamento dei file esistenti.</span><span class="sxs-lookup"><span data-stu-id="c4890-138">Advanced eDiscovery creates copies of the files rather that loading metadata of the existing files.</span></span>
    
- <span data-ttu-id="c4890-139">**Famiglie**: non è possibile caricare una famiglia senza il padre (capo della famiglia).</span><span class="sxs-lookup"><span data-stu-id="c4890-139">**Families**: It is not possible to load a family without its parent (head of family).</span></span> 
    
- <span data-ttu-id="c4890-140">**Dimensioni file**: non è previsto alcun limite per la dimensione dei file caricati in Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="c4890-140">**File size**: There is no limitation on the size of files loaded to Advanced eDiscovery.</span></span> <span data-ttu-id="c4890-141">Per l'analisi (Analyze, pertinenza e così via), il limite è 5.242.880 caratteri del testo estratto.</span><span class="sxs-lookup"><span data-stu-id="c4890-141">For analysis (Analyze, Relevance, etc.), the limit is 5,242,880 characters of extracted text.</span></span> <span data-ttu-id="c4890-142">I file di grandi dimensioni vengono ignorati (ad esempio, in caso di pertinenza, i file non partecipano al processo di formazione per pertinenza e non ricevono un punteggio di pertinenza dopo il calcolo del batch).</span><span class="sxs-lookup"><span data-stu-id="c4890-142">Larger files are ignored (for example, in Relevance, files do not participate in the Relevance training process and do not receive a Relevance score after batch calculation).</span></span>
    
- <span data-ttu-id="c4890-143">**Quantità file**: non è previsto alcun limite consigliato per il numero di file che possono essere gestiti in un singolo caso.</span><span class="sxs-lookup"><span data-stu-id="c4890-143">**File quantity**: There is no recommended limit on the number of files that can be handled in a single case.</span></span> <span data-ttu-id="c4890-144">Le prestazioni dipendono dalle risorse del sistema.</span><span class="sxs-lookup"><span data-stu-id="c4890-144">Performance depends on the resources of your system.</span></span> 
    
## <a name="filtering-files"></a><span data-ttu-id="c4890-145">Filtro dei file</span><span class="sxs-lookup"><span data-stu-id="c4890-145">Filtering files</span></span>

<span data-ttu-id="c4890-146">Un'etichetta definita dall'utente può essere associata a un insieme di file per escluderli dal processo o da altre attività.</span><span class="sxs-lookup"><span data-stu-id="c4890-146">A user-defined label can be associated with a set of files to exclude them from Process or other tasks.</span></span> <span data-ttu-id="c4890-147">Ogni sessione di processo è associata a un ID batch.</span><span class="sxs-lookup"><span data-stu-id="c4890-147">Each Process session is associated with a batch ID.</span></span> <span data-ttu-id="c4890-148">Anche se l'ID batch non è visibile per l'esperto in pertinenza, è possibile eseguire questa operazione utilizzando un'utilità di ricerca, aggiungendo un filtro per il batch corrente e contrassegnando tutti i file corretti con un'etichetta definita dall'utente.</span><span class="sxs-lookup"><span data-stu-id="c4890-148">Although the batch ID is not visible to the expert in Relevance, this can be done using a search utility, by adding a filter for the current batch and tagging all appropriate files with a user-defined label.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="c4890-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c4890-149">See also</span></span>

[<span data-ttu-id="c4890-150">Advanced eDiscovery (classico)</span><span class="sxs-lookup"><span data-stu-id="c4890-150">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="c4890-151">Esecuzione del modulo di elaborazione e caricamento dei dati</span><span class="sxs-lookup"><span data-stu-id="c4890-151">Running the Process module and loading data</span></span>](run-the-process-module-and-load-data-in-advanced-ediscovery.md)
  
[<span data-ttu-id="c4890-152">Visualizzazione dei risultati del modulo di elaborazione</span><span class="sxs-lookup"><span data-stu-id="c4890-152">Viewing Process module results</span></span>](view-process-module-results-in-advanced-ediscovery.md)

