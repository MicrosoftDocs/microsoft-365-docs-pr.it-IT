---
title: Visualizzare i risultati dell'analisi in Office 365 Advanced eDiscovery
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 5974f3c2-89fe-4c5f-ac7b-57f214437f7e
description: 'Informazioni su come visualizzare i risultati del processo di analisi in Office 365 Advanced eDiscovery, incluse le definizioni delle opzioni di attività visualizzate.  '
ms.openlocfilehash: 092daa506316b5eb1ef1f5c466055b29e350dc18
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37084314"
---
# <a name="view-analyze-results-in-office-365-advanced-ediscovery"></a><span data-ttu-id="a6bce-103">Visualizzare i risultati dell'analisi in Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="a6bce-103">View Analyze results in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="a6bce-p101">Per usare Advanced eDiscovery è necessario avere Office 365 E3 con il componente aggiuntivo Advanced Compliance o un abbonamento E5 dell'organizzazione. Se non si ha questo piano e si desidera provare Advanced eDiscovery, è possibile [richiedere una valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="a6bce-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="a6bce-106">In Advanced eDiscovery, Progress and results for the Analyze Process può essere visualizzato in una vasta gamma di visualizzazioni come descritto di seguito.</span><span class="sxs-lookup"><span data-stu-id="a6bce-106">In Advanced eDiscovery, progress and results for the Analyze process can be viewed in a variety of displays as described below.</span></span>
  
## <a name="view-analyze-task-status"></a><span data-ttu-id="a6bce-107">Visualizzazione dello stato dell'attività Analyze</span><span class="sxs-lookup"><span data-stu-id="a6bce-107">View Analyze task status</span></span>

<span data-ttu-id="a6bce-108">In **prepara \> analisi \> stato \> attività risultati**, lo stato viene visualizzato durante e dopo l'analisi dell'esecuzione del processo.</span><span class="sxs-lookup"><span data-stu-id="a6bce-108">In **Prepare \> Analyze \> Results \> Task status**, the status is displayed during and after Analyze process execution.</span></span> 
  
![Analizzare lo stato delle attività](media/d0372978-ce08-4f4e-a1fc-aa918ae44364.png)
  
<span data-ttu-id="a6bce-110">Le attività visualizzate possono variare a seconda delle opzioni selezionate.</span><span class="sxs-lookup"><span data-stu-id="a6bce-110">The tasks displayed may vary depending on the options selected.</span></span> 
  
- <span data-ttu-id="a6bce-111">**ND/et: Setup**: prepara per l'esecuzione, ad esempio set di parametri Run e case.</span><span class="sxs-lookup"><span data-stu-id="a6bce-111">**ND/ET: setup**: Prepares for the run, for example, sets run and case parameters.</span></span>
    
- <span data-ttu-id="a6bce-112">**ND/et: calcolo ND**: processi di analisi quasi duplicati dei file.</span><span class="sxs-lookup"><span data-stu-id="a6bce-112">**ND/ET: ND calculation**: Processes Near-duplicate analysis of files.</span></span>
    
- <span data-ttu-id="a6bce-113">**ND/et: et calculation**: esegue l'analisi del thread di posta elettronica sull'intero set di messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="a6bce-113">**ND/ET: ET calculation**: Performs Email Thread analysis on the entire email set.</span></span>
    
- <span data-ttu-id="a6bce-114">**ND/et: pivot e similitudini**: esegue l'elaborazione di pivot e file di somiglianza.</span><span class="sxs-lookup"><span data-stu-id="a6bce-114">**ND/ET: pivots and similarities**: Performs pivot and file similarity processing.</span></span>
    
- <span data-ttu-id="a6bce-115">**ND/et: aggiornamento dei metadati**: finalizza i nuovi dati raccolti nei file del database.</span><span class="sxs-lookup"><span data-stu-id="a6bce-115">**ND/ET: metadata update**: Finalizes the new data collected on the files in the database.</span></span>
    
- <span data-ttu-id="a6bce-116">**Temi: calcolo**dei temi: esecuzione dell'analisi dei temi.</span><span class="sxs-lookup"><span data-stu-id="a6bce-116">**Themes: themes calculation**: Runs themes analysis.</span></span> <span data-ttu-id="a6bce-117">(Visualizzato solo se selezionato).</span><span class="sxs-lookup"><span data-stu-id="a6bce-117">(Displayed only if selected.)</span></span>
    
- <span data-ttu-id="a6bce-118">**Stato attività**: questa riga viene visualizzata dopo il completamento dell'attività.</span><span class="sxs-lookup"><span data-stu-id="a6bce-118">**Task status**: This line is displayed after task completion.</span></span> <span data-ttu-id="a6bce-119">Mentre le attività sono in esecuzione, viene visualizzata la durata di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a6bce-119">While tasks are running, run duration is displayed.</span></span>
    
> [!NOTE]
> <span data-ttu-id="a6bce-120">I risultati dell'analisi di quasi duplicati e di thread di posta elettronica (ND ed ED) si applicano al numero di documenti da elaborare.</span><span class="sxs-lookup"><span data-stu-id="a6bce-120">The Analyze results of Near-duplicates and Email Threads (ND and ED) applies to the number of documents to be processed.</span></span> <span data-ttu-id="a6bce-121">Non include file duplicati esatti.</span><span class="sxs-lookup"><span data-stu-id="a6bce-121">It does not include Exact duplicate files.</span></span> 
  
## <a name="view-near-duplicates-and-email-threads-status"></a><span data-ttu-id="a6bce-122">Visualizzazione near-Duplicates and mail Threads status</span><span class="sxs-lookup"><span data-stu-id="a6bce-122">View Near-duplicates and Email Threads status</span></span>

<span data-ttu-id="a6bce-123">I risultati della popolazione di **destinazione** visualizzano il numero di documenti, messaggi di posta elettronica, allegati ed errori nella popolazione di destinazione.</span><span class="sxs-lookup"><span data-stu-id="a6bce-123">The **Target** population results display the number of documents, emails, attachments, and errors in the target population.</span></span> 
  
<span data-ttu-id="a6bce-124">Nei risultati dei **documenti** vengono visualizzati il numero di pivot, i duplicati univoci e i file duplicati esatti.</span><span class="sxs-lookup"><span data-stu-id="a6bce-124">The **Documents** results display the number of pivots, unique near-duplicates, and exact duplicate files.</span></span> 
  
<span data-ttu-id="a6bce-125">I **risultati dei messaggi di** posta elettronica visualizzano il numero di copie inclusive, inclusive, uniche e inclusive e il resto del messaggio.</span><span class="sxs-lookup"><span data-stu-id="a6bce-125">The **Emails** results display the number of inclusive, inclusive minus, unique inclusive copies, and the rest of the email messages.</span></span> <span data-ttu-id="a6bce-126">I diversi tipi di risultati del messaggio di posta elettronica sono:</span><span class="sxs-lookup"><span data-stu-id="a6bce-126">The different types of email results are:</span></span> 
  
- <span data-ttu-id="a6bce-127">**Inclusive**: un messaggio di posta elettronica incluso è il nodo di terminazione in un thread di posta elettronica e contiene tutta la cronologia precedente di quel thread.</span><span class="sxs-lookup"><span data-stu-id="a6bce-127">**Inclusive**: An inclusive email is the terminating node in an email thread and contains all the previous history of that thread.</span></span> <span data-ttu-id="a6bce-128">Di conseguenza, il revisore può concentrarsi in modo sicuro sul messaggio di posta elettronica incluso, senza la necessità di leggere i messaggi precedenti nel thread.</span><span class="sxs-lookup"><span data-stu-id="a6bce-128">As a result, the reviewer can safely focus on the inclusive email, without the need to read the previous messages in the thread.</span></span> 
    
- <span data-ttu-id="a6bce-129">**Inclusione meno**: un messaggio di posta elettronica incluso è definito come incluso meno se sono presenti uno o più allegati diversi associati ai padri dei messaggi inclusivi.</span><span class="sxs-lookup"><span data-stu-id="a6bce-129">**Inclusive minus**: An inclusive email is designated as inclusive minus if there are one or more different attachments associated with the parents of the inclusive message.</span></span> <span data-ttu-id="a6bce-130">In questo contesto, il termine padre viene utilizzato per i messaggi che si trovano verso l'alto sul thread di posta elettronica o le conversazioni incluse in tale messaggio di posta elettronica incluso specifico.</span><span class="sxs-lookup"><span data-stu-id="a6bce-130">In this context, the term Parent is used for messages located upwards on the email thread or conversations included in that specific inclusive email.</span></span> <span data-ttu-id="a6bce-131">Un revisore può utilizzare l'indicazione meno inclusiva come un segnale che, sebbene potrebbe non essere necessario esaminare il contenuto dei genitori inclusi nella posta elettronica, potrebbe essere utile esaminare gli allegati associati ai padri del percorso inclusivo.</span><span class="sxs-lookup"><span data-stu-id="a6bce-131">A reviewer can use the inclusive minus indication as a signal that although it might not be necessary to review the content of the inclusive email parents, it may be useful to review the attachments associated with the inclusive path parents.</span></span> 
    
- <span data-ttu-id="a6bce-132">**Copia inclusiva**: un messaggio di posta elettronica incluso è designato come copia inclusiva se si tratta della copia di un altro messaggi contrassegnato come inclusivo o inclusivo meno.</span><span class="sxs-lookup"><span data-stu-id="a6bce-132">**Inclusive copy**: An inclusive email is designated as inclusive copy if it's the copy of another message marked as inclusive or inclusive minus.</span></span> <span data-ttu-id="a6bce-133">In altre parole, questo messaggio ha lo stesso oggetto e corpo di un altro messaggio inclusivo e, come tale, risiede nello stesso nodo.</span><span class="sxs-lookup"><span data-stu-id="a6bce-133">In other words, this message has the same subject and body as another inclusive message and, as such, co-resides in the same node.</span></span> <span data-ttu-id="a6bce-134">Poiché i messaggi di copia inclusivi contengono lo stesso contenuto, è possibile che in genere vengano ignorati nel processo di revisione.</span><span class="sxs-lookup"><span data-stu-id="a6bce-134">Because inclusive copy messages contain the same content, they can usually be skipped in the review process.</span></span> 
    
- <span data-ttu-id="a6bce-135">**The Rest**: indica la posta elettronica che non contiene contenuti univoci e pertanto non rientra in nessuna delle tre categorie precedenti.</span><span class="sxs-lookup"><span data-stu-id="a6bce-135">**The rest**: This indicates email that doesn't contain any unique content, and therefore doesn't fall into any of the previous three categories.</span></span> <span data-ttu-id="a6bce-136">Questi messaggi di posta elettronica non devono essere esaminati.</span><span class="sxs-lookup"><span data-stu-id="a6bce-136">These email messages don't need to be reviewed.</span></span> <span data-ttu-id="a6bce-137">Se un messaggio contiene un allegato che non è incluso in una posta elettronica inclusa in un secondo momento, potrebbe essere necessario esaminare l'allegato.</span><span class="sxs-lookup"><span data-stu-id="a6bce-137">If a message contains an attachment that isn't on a later inclusive email, then the attachment might need to be reviewed.</span></span> <span data-ttu-id="a6bce-138">Ciò è indicato dall'esistenza di un messaggio di posta elettronica meno incluso all'interno del thread.</span><span class="sxs-lookup"><span data-stu-id="a6bce-138">This is indicated by the existence of an inclusive minus email within the thread.</span></span>
    
<span data-ttu-id="a6bce-139">I risultati degli **allegati** visualizzano il numero di allegati, in base al tipo di elementi unici e duplicati.</span><span class="sxs-lookup"><span data-stu-id="a6bce-139">The **Attachments** results display the number of attachments, according to such type as unique and duplicates.</span></span> 
  
![Risultati quasi duplicati e thread di posta elettronica](media/54491303-0ee3-4739-b42e-d1ee486842fd.png)
  
## <a name="see-also"></a><span data-ttu-id="a6bce-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a6bce-141">See also</span></span>

[<span data-ttu-id="a6bce-142">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="a6bce-142">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="a6bce-143">Informazioni sulla somiglianza del documento</span><span class="sxs-lookup"><span data-stu-id="a6bce-143">Understanding document similarity</span></span>](understand-document-similarity-in-advanced-ediscovery.md)
  
[<span data-ttu-id="a6bce-144">Impostazione delle opzioni di analisi</span><span class="sxs-lookup"><span data-stu-id="a6bce-144">Setting Analyze options</span></span>](set-analyze-options-in-advanced-ediscovery.md)
  
[<span data-ttu-id="a6bce-145">Impostazione Ignora testo</span><span class="sxs-lookup"><span data-stu-id="a6bce-145">Setting ignore text</span></span>](set-ignore-text-in-advanced-ediscovery.md)
  
[<span data-ttu-id="a6bce-146">Impostazione analisi impostazioni avanzate</span><span class="sxs-lookup"><span data-stu-id="a6bce-146">Setting Analyze advanced settings</span></span>](view-analyze-results-in-advanced-ediscovery.md)

