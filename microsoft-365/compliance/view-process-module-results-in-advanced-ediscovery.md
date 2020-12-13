---
title: Visualizza i risultati del modulo di processo in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
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
ms.assetid: c6f016cb-409f-4ae9-911c-1395cf0c86ea
description: Informazioni su come trovare i risultati di un modulo di processo eseguito in Advanced eDiscovery, incluso lo stato delle attività e il riepilogo dei processi.
ms.openlocfilehash: 73699d77e305055f6c2dc444fff00fb714b458cd
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663265"
---
# <a name="view-process-module-results-in-advanced-ediscovery-classic"></a><span data-ttu-id="acfbc-103">Visualizza i risultati del modulo di processo in Advanced eDiscovery (Classic)</span><span class="sxs-lookup"><span data-stu-id="acfbc-103">View Process module results in Advanced eDiscovery (classic)</span></span>

<span data-ttu-id="acfbc-104">Dopo l'avvio del processo di **preparazione** \>  , è possibile visualizzare lo stato e i risultati.</span><span class="sxs-lookup"><span data-stu-id="acfbc-104">After **Prepare** \> **Process** is initiated, you can view progress and results.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="acfbc-p101">Per usare Advanced eDiscovery è necessario avere Office 365 E3 con il componente aggiuntivo Advanced Compliance o un abbonamento E5 dell'organizzazione. Se non si ha questo piano e si desidera provare Advanced eDiscovery, è possibile [richiedere una valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="acfbc-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
## <a name="process-task-status"></a><span data-ttu-id="acfbc-107">Stato attività processo</span><span class="sxs-lookup"><span data-stu-id="acfbc-107">Process task status</span></span>

<span data-ttu-id="acfbc-108">Nei risultati del processo di **preparazione** \>  \> la pagina mostra lo stato corrente (se il processo è in esecuzione) oppure lo stato dell'ultimo processo di elaborazione, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="acfbc-108">In **Prepare** \> **Process** \> **Results**, the page shows the current status (if Process is currently running) or the last Process status task status as shown in the following example.</span></span>
  
![Stato delle attività del modulo processo](../media/9430f9e7-a4dd-47c7-ac2e-2c6a60fc948b.png)
  
<span data-ttu-id="acfbc-110">Le attività visualizzate possono variare a seconda delle opzioni di elaborazione selezionate.</span><span class="sxs-lookup"><span data-stu-id="acfbc-110">The displayed tasks may vary depending on the Process options selected.</span></span> 
  
- <span data-ttu-id="acfbc-111">**Inventario**: Advanced eDiscovery scorre tutti i file selezionati per il processo ed esegue la raccolta di dati di base.</span><span class="sxs-lookup"><span data-stu-id="acfbc-111">**Inventory**: Advanced eDiscovery iterates through all files selected for Process and performs basic data collection.</span></span>
    
- <span data-ttu-id="acfbc-112">**Calcolo delle firme**: consente di calcolare le firme digitali MD5.</span><span class="sxs-lookup"><span data-stu-id="acfbc-112">**Calculate signatures**: Calculates the MD5 digital signatures.</span></span>
    
- <span data-ttu-id="acfbc-113">**Estrazione dei composti**: estrae i file interni o contenuti in modo ricorsivo da file compositi (ad esempio, PST, zip, msg).</span><span class="sxs-lookup"><span data-stu-id="acfbc-113">**Compounds extraction**: Extracts inner or contained files recursively from compound files (for example, PST, ZIP, MSG).</span></span> <span data-ttu-id="acfbc-114">I file estratti sono archiviati nella cartella case del caso.</span><span class="sxs-lookup"><span data-stu-id="acfbc-114">Extracted files are stored in the case folder of the case.</span></span>
    
- <span data-ttu-id="acfbc-115">**Database di sincronizzazione**: processo di database interno.</span><span class="sxs-lookup"><span data-stu-id="acfbc-115">**Synchronizing database**: Internal database process.</span></span>
    
- <span data-ttu-id="acfbc-116">**Copia file**: copia i file di processo.</span><span class="sxs-lookup"><span data-stu-id="acfbc-116">**File copy**: Copies Process files.</span></span> <span data-ttu-id="acfbc-117">Questa attività viene sempre visualizzata, anche quando è selezionata l'opzione file di copia avanzata.</span><span class="sxs-lookup"><span data-stu-id="acfbc-117">This task is always displayed, even when the advanced Copy files option is selected.</span></span>
    
- <span data-ttu-id="acfbc-118">**Estrazione del testo**: quando sono presenti file nativi, Advanced eDiscovery estrae testo da questi file tramite DTSearch.</span><span class="sxs-lookup"><span data-stu-id="acfbc-118">**Text extraction**: When there are native files, Advanced eDiscovery extracts text from these files using DTSearch.</span></span> <span data-ttu-id="acfbc-119">Il testo estratto di questi file è memorizzato come file di testo nella cartella case.</span><span class="sxs-lookup"><span data-stu-id="acfbc-119">The extracted text of these files is stored as text files in the case folder.</span></span>
    
- <span data-ttu-id="acfbc-120">**Aggiornamento dei metadati**: elabora i metadati caricati.</span><span class="sxs-lookup"><span data-stu-id="acfbc-120">**Updating metadata**: Processes the loaded metadata.</span></span> 
    
- <span data-ttu-id="acfbc-121">**Finalizzazione**: elaborazione interna che consente di finalizzare i dati dei file di caso caricati (ad esempio, identificare i file di errore e di successo).</span><span class="sxs-lookup"><span data-stu-id="acfbc-121">**Finalizing**: Internal processing that finalizes data of loaded case files (for example, identify error and success files).</span></span> 
    
<span data-ttu-id="acfbc-122">Stato attività: visualizzato dopo il completamento dell'attività.</span><span class="sxs-lookup"><span data-stu-id="acfbc-122">Task status: Displayed after task completion.</span></span> <span data-ttu-id="acfbc-123">Mentre le attività sono in esecuzione, viene visualizzata la durata di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="acfbc-123">While tasks are running, run duration is displayed.</span></span>
  
> [!NOTE]
> <span data-ttu-id="acfbc-124">Le attività completate possono includere anche i totali per i file che hanno completato l'elaborazione o i file con errori.</span><span class="sxs-lookup"><span data-stu-id="acfbc-124">Completed tasks may also include totals for files that completed processing or files with errors.</span></span> 
  
> [!TIP]
> <span data-ttu-id="acfbc-125">"Annulla" fornisce un'opzione di rollback per interrompere l'esecuzione del processo e quindi eseguire il rollback al popolamento precedente dei dati o ai dati elaborati salvati.</span><span class="sxs-lookup"><span data-stu-id="acfbc-125">"Cancel" provides a rollback option to stop Process execution and then roll back to the previous data population or saved processed data.</span></span> <span data-ttu-id="acfbc-126">Rollback Annulla tutti i dati elaborati.</span><span class="sxs-lookup"><span data-stu-id="acfbc-126">Rollback clears all processed data.</span></span> <span data-ttu-id="acfbc-127">Se non si desidera che i dati elaborati vengano persi (ad esempio, si prevede di ricaricare i file), selezionare l'opzione "Annulla" in questa finestra per scegliere di non eseguire il rollback.</span><span class="sxs-lookup"><span data-stu-id="acfbc-127">If you do not want the processed data to be lost (for example, you plan to reload these files), select the "Cancel" option in this window to choose not to roll back.</span></span> 
  
## <a name="process-summary"></a><span data-ttu-id="acfbc-128">Riepilogo del processo</span><span class="sxs-lookup"><span data-stu-id="acfbc-128">Process summary</span></span>

<span data-ttu-id="acfbc-129">In preparare \> \> \> il riepilogo del processo dei risultati del processo, viene visualizzata una scomposizione dei risultati di file caricati in base ai risultati dell'elaborazione e dell'errore del file.</span><span class="sxs-lookup"><span data-stu-id="acfbc-129">In Prepare \> Process \> Results \> Process summary, a breakdown of loaded file results is displayed according to successful file processing and error results.</span></span>
  
<span data-ttu-id="acfbc-130">I riquadri presentano una visualizzazione grafica delle statistiche dei file importati, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="acfbc-130">The panes present a graphical display of imported file statistics, as follows:</span></span>
  
- <span data-ttu-id="acfbc-131">**Riepilogo processi accumulare** d: tutti i file nel caso.</span><span class="sxs-lookup"><span data-stu-id="acfbc-131">**Process summary accumulate** d: All files in the case.</span></span>
    
- <span data-ttu-id="acfbc-132">**Riepilogo del processo ultimo**: file caricati dall'ultima sessione o dall'azione.</span><span class="sxs-lookup"><span data-stu-id="acfbc-132">**Process summary last**: Files loaded from the last session or action.</span></span> 
    
- <span data-ttu-id="acfbc-133">**Famiglie ultimo**: informazioni sulla famiglia nel caso (se presente).</span><span class="sxs-lookup"><span data-stu-id="acfbc-133">**Families last**: Family information in the case (if any).</span></span>
    
- <span data-ttu-id="acfbc-134">Se sono stati aggiunti file di **seeding** , il numero di file di seeding è elencato per ogni problema definito per i file.</span><span class="sxs-lookup"><span data-stu-id="acfbc-134">If **Seed** files were added, the number of seed files is listed per issue that was defined for the files.</span></span> 
    
    <span data-ttu-id="acfbc-135">Se la marcatura dei file di **inizializzazione** non è riuscita, nota anche.</span><span class="sxs-lookup"><span data-stu-id="acfbc-135">If the marking of **Seed** files failed, that is also noted.</span></span> 
    
- <span data-ttu-id="acfbc-136">Se sono stati aggiunti file **con tag preselezionati** , il numero di file contrassegnati è elencato per ogni problema definito per i file.</span><span class="sxs-lookup"><span data-stu-id="acfbc-136">If **Pre-tagged** files were added, the number of pre-tagged files is listed per issue that was defined for the files.</span></span> 
    
    <span data-ttu-id="acfbc-137">Se la marcatura dei file **precontrassegnati** ha avuto esito negativo, viene anche rilevato.</span><span class="sxs-lookup"><span data-stu-id="acfbc-137">If the marking of **Pre-tagged** files failed, that is also noted.</span></span> 
    
![Riepilogo modulo processo](../media/2086a691-9e3d-4117-beb2-a5c3a9a4cc94.png)
  
## <a name="process-summary-accumulated-and-last-charts"></a><span data-ttu-id="acfbc-139">Riepilogo del processo accumulato e ultimo grafico</span><span class="sxs-lookup"><span data-stu-id="acfbc-139">Process summary accumulated and last charts</span></span>

<span data-ttu-id="acfbc-140">La barra sinistra include i file di origine + estratti: tutti i file trovati.</span><span class="sxs-lookup"><span data-stu-id="acfbc-140">The left bar includes Source + extracted files: which is all files found.</span></span> 
  
<span data-ttu-id="acfbc-141">La barra destra, elaborata, include:</span><span class="sxs-lookup"><span data-stu-id="acfbc-141">The right bar, Processed, includes:</span></span>
  
- <span data-ttu-id="acfbc-142">File con errori di caricamento</span><span class="sxs-lookup"><span data-stu-id="acfbc-142">Files with load errors</span></span>
    
- <span data-ttu-id="acfbc-143">File caricati correttamente, che possono includere:</span><span class="sxs-lookup"><span data-stu-id="acfbc-143">Successfully loaded files, which may include:</span></span> 
    
  - <span data-ttu-id="acfbc-144">**Existing**: file caricati prima e ora caricati di nuovo (inclusi i duplicati).</span><span class="sxs-lookup"><span data-stu-id="acfbc-144">**Existing**: Files that were loaded before and are now loaded again (including duplicates).</span></span>
    
  - <span data-ttu-id="acfbc-145">**Testo**: file univoci con testo.</span><span class="sxs-lookup"><span data-stu-id="acfbc-145">**Text**: Unique files with text.</span></span>
    
  - <span data-ttu-id="acfbc-146">**Non testuale**: file di testo vuoti, file di testo nativo vuoti, file non di testo nativi.</span><span class="sxs-lookup"><span data-stu-id="acfbc-146">**Non-text**: Empty text files, empty native text files, native non-text files.</span></span> 
    
  - <span data-ttu-id="acfbc-147">**Duplicate** s: file duplicati con testo.</span><span class="sxs-lookup"><span data-stu-id="acfbc-147">**Duplicate** s: Duplicate files with text.</span></span>
    
## <a name="last-process-errors"></a><span data-ttu-id="acfbc-148">Ultimi errori del processo</span><span class="sxs-lookup"><span data-stu-id="acfbc-148">Last process errors</span></span>

<span data-ttu-id="acfbc-149">Nei \> risultati del processo di preparazione \> \> , vengono visualizzati i dettagli relativi agli errori dell'ultima sessione o all'azione eseguita.</span><span class="sxs-lookup"><span data-stu-id="acfbc-149">In Prepare \> Process \> Results \> Last process errors, details of the errors in the last session or action performed are displayed.</span></span>
  
![Errori modulo processo](../media/4771d0f4-4217-445a-9ba4-8b6541c5ad09.png)
  
## <a name="see-also"></a><span data-ttu-id="acfbc-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="acfbc-151">See also</span></span>

[<span data-ttu-id="acfbc-152">Advanced eDiscovery (classico)</span><span class="sxs-lookup"><span data-stu-id="acfbc-152">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="acfbc-153">Esecuzione del modulo di elaborazione e caricamento dei dati</span><span class="sxs-lookup"><span data-stu-id="acfbc-153">Running the Process module and loading data</span></span>](run-the-process-module-and-load-data-in-advanced-ediscovery.md)

