---
title: Visualizzare i risultati dell'analisi in Advanced eDiscovery
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
ms.assetid: 5974f3c2-89fe-4c5f-ac7b-57f214437f7e
description: Informazioni sul percorso in cui visualizzare i risultati del processo di analisi in Advanced eDiscovery, incluse le definizioni delle opzioni di attività visualizzate.
ms.openlocfilehash: 24a4b0685ec5dc82aff0b1f0de81080a62e49776
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936949"
---
# <a name="view-analyze-results-in-advanced-ediscovery-classic"></a><span data-ttu-id="79caa-103">Visualizzazione analisi dei risultati in Advanced eDiscovery (Classic)</span><span class="sxs-lookup"><span data-stu-id="79caa-103">View Analyze results in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="79caa-104">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization.</span><span class="sxs-lookup"><span data-stu-id="79caa-104">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization.</span></span> <span data-ttu-id="79caa-105">If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="79caa-105">If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="79caa-106">In Advanced eDiscovery, Progress and results for the Analyze Process può essere visualizzato in una vasta gamma di visualizzazioni come descritto di seguito.</span><span class="sxs-lookup"><span data-stu-id="79caa-106">In Advanced eDiscovery, progress and results for the Analyze process can be viewed in a variety of displays as described below.</span></span>
  
## <a name="view-analyze-task-status"></a><span data-ttu-id="79caa-107">Visualizzazione dello stato dell'attività Analyze</span><span class="sxs-lookup"><span data-stu-id="79caa-107">View Analyze task status</span></span>

<span data-ttu-id="79caa-108">In **prepara \> analisi \> \> stato attività risultati**, lo stato viene visualizzato durante e dopo l'analisi dell'esecuzione del processo.</span><span class="sxs-lookup"><span data-stu-id="79caa-108">In **Prepare \> Analyze \> Results \> Task status**, the status is displayed during and after Analyze process execution.</span></span> 
  
![Analizzare lo stato delle attività](../media/d0372978-ce08-4f4e-a1fc-aa918ae44364.png)
  
<span data-ttu-id="79caa-110">Le attività visualizzate possono variare a seconda delle opzioni selezionate.</span><span class="sxs-lookup"><span data-stu-id="79caa-110">The tasks displayed may vary depending on the options selected.</span></span> 
  
- <span data-ttu-id="79caa-111">**ND/et: Setup**: prepara per l'esecuzione, ad esempio set di parametri Run e case.</span><span class="sxs-lookup"><span data-stu-id="79caa-111">**ND/ET: setup**: Prepares for the run, for example, sets run and case parameters.</span></span>
    
- <span data-ttu-id="79caa-112">**ND/et: calcolo ND**: processi di analisi quasi duplicati dei file.</span><span class="sxs-lookup"><span data-stu-id="79caa-112">**ND/ET: ND calculation**: Processes Near-duplicate analysis of files.</span></span>
    
- <span data-ttu-id="79caa-113">**ND/et: et calculation**: esegue l'analisi del thread di posta elettronica sull'intero set di messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="79caa-113">**ND/ET: ET calculation**: Performs Email Thread analysis on the entire email set.</span></span>
    
- <span data-ttu-id="79caa-114">**ND/et: pivot e similitudini**: esegue l'elaborazione di pivot e file di somiglianza.</span><span class="sxs-lookup"><span data-stu-id="79caa-114">**ND/ET: pivots and similarities**: Performs pivot and file similarity processing.</span></span>
    
- <span data-ttu-id="79caa-115">**ND/et: aggiornamento dei metadati**: finalizza i nuovi dati raccolti nei file del database.</span><span class="sxs-lookup"><span data-stu-id="79caa-115">**ND/ET: metadata update**: Finalizes the new data collected on the files in the database.</span></span>
    
- <span data-ttu-id="79caa-116">**Temi: calcolo**dei temi: esecuzione dell'analisi dei temi.</span><span class="sxs-lookup"><span data-stu-id="79caa-116">**Themes: themes calculation**: Runs themes analysis.</span></span> <span data-ttu-id="79caa-117">(Visualizzato solo se selezionato).</span><span class="sxs-lookup"><span data-stu-id="79caa-117">(Displayed only if selected.)</span></span>
    
- <span data-ttu-id="79caa-118">**Stato attività**: questa riga viene visualizzata dopo il completamento dell'attività.</span><span class="sxs-lookup"><span data-stu-id="79caa-118">**Task status**: This line is displayed after task completion.</span></span> <span data-ttu-id="79caa-119">Mentre le attività sono in esecuzione, viene visualizzata la durata di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="79caa-119">While tasks are running, run duration is displayed.</span></span>
    
> [!NOTE]
> <span data-ttu-id="79caa-120">I risultati dell'analisi di quasi duplicati e di thread di posta elettronica (ND ed ED) si applicano al numero di documenti da elaborare.</span><span class="sxs-lookup"><span data-stu-id="79caa-120">The Analyze results of Near-duplicates and Email Threads (ND and ED) applies to the number of documents to be processed.</span></span> <span data-ttu-id="79caa-121">Non include file duplicati esatti.</span><span class="sxs-lookup"><span data-stu-id="79caa-121">It does not include Exact duplicate files.</span></span> 
  
## <a name="view-near-duplicates-and-email-threads-status"></a><span data-ttu-id="79caa-122">Visualizzazione near-Duplicates and mail Threads status</span><span class="sxs-lookup"><span data-stu-id="79caa-122">View Near-duplicates and Email Threads status</span></span>

<span data-ttu-id="79caa-123">I risultati della popolazione di **destinazione** visualizzano il numero di documenti, messaggi di posta elettronica, allegati ed errori nella popolazione di destinazione.</span><span class="sxs-lookup"><span data-stu-id="79caa-123">The **Target** population results display the number of documents, emails, attachments, and errors in the target population.</span></span> 
  
<span data-ttu-id="79caa-124">Nei risultati dei **documenti** vengono visualizzati il numero di pivot, i duplicati univoci e i file duplicati esatti.</span><span class="sxs-lookup"><span data-stu-id="79caa-124">The **Documents** results display the number of pivots, unique near-duplicates, and exact duplicate files.</span></span> 
  
<span data-ttu-id="79caa-125">I **risultati dei messaggi di** posta elettronica visualizzano il numero di copie inclusive, inclusive, uniche e inclusive e il resto del messaggio.</span><span class="sxs-lookup"><span data-stu-id="79caa-125">The **Emails** results display the number of inclusive, inclusive minus, unique inclusive copies, and the rest of the email messages.</span></span> <span data-ttu-id="79caa-126">I diversi tipi di risultati del messaggio di posta elettronica sono:</span><span class="sxs-lookup"><span data-stu-id="79caa-126">The different types of email results are:</span></span> 
  
- <span data-ttu-id="79caa-127">**Inclusive**: un messaggio di posta elettronica incluso è il nodo di terminazione in un thread di posta elettronica e contiene tutta la cronologia precedente di quel thread.</span><span class="sxs-lookup"><span data-stu-id="79caa-127">**Inclusive**: An inclusive email is the terminating node in an email thread and contains all the previous history of that thread.</span></span> <span data-ttu-id="79caa-128">Di conseguenza, il revisore può concentrarsi in modo sicuro sul messaggio di posta elettronica incluso, senza la necessità di leggere i messaggi precedenti nel thread.</span><span class="sxs-lookup"><span data-stu-id="79caa-128">As a result, the reviewer can safely focus on the inclusive email, without the need to read the previous messages in the thread.</span></span> 
    
- <span data-ttu-id="79caa-129">**Inclusione meno**: un messaggio di posta elettronica incluso è definito come incluso meno se sono presenti uno o più allegati diversi associati ai padri dei messaggi inclusivi.</span><span class="sxs-lookup"><span data-stu-id="79caa-129">**Inclusive minus**: An inclusive email is designated as inclusive minus if there are one or more different attachments associated with the parents of the inclusive message.</span></span> <span data-ttu-id="79caa-130">In questo contesto, il termine padre viene utilizzato per i messaggi che si trovano verso l'alto sul thread di posta elettronica o le conversazioni incluse in tale messaggio di posta elettronica incluso specifico.</span><span class="sxs-lookup"><span data-stu-id="79caa-130">In this context, the term Parent is used for messages located upwards on the email thread or conversations included in that specific inclusive email.</span></span> <span data-ttu-id="79caa-131">Un revisore può utilizzare l'indicazione meno inclusiva come un segnale che, sebbene potrebbe non essere necessario esaminare il contenuto dei genitori inclusi nella posta elettronica, potrebbe essere utile esaminare gli allegati associati ai padri del percorso inclusivo.</span><span class="sxs-lookup"><span data-stu-id="79caa-131">A reviewer can use the inclusive minus indication as a signal that although it might not be necessary to review the content of the inclusive email parents, it may be useful to review the attachments associated with the inclusive path parents.</span></span> 
    
- <span data-ttu-id="79caa-132">**Copia inclusiva**: un messaggio di posta elettronica incluso è designato come copia inclusiva se si tratta della copia di un altro messaggi contrassegnato come inclusivo o inclusivo meno.</span><span class="sxs-lookup"><span data-stu-id="79caa-132">**Inclusive copy**: An inclusive email is designated as inclusive copy if it's the copy of another message marked as inclusive or inclusive minus.</span></span> <span data-ttu-id="79caa-133">In altre parole, questo messaggio ha lo stesso oggetto e corpo di un altro messaggio inclusivo e, come tale, risiede nello stesso nodo.</span><span class="sxs-lookup"><span data-stu-id="79caa-133">In other words, this message has the same subject and body as another inclusive message and, as such, co-resides in the same node.</span></span> <span data-ttu-id="79caa-134">Poiché i messaggi di copia inclusivi contengono lo stesso contenuto, è possibile che in genere vengano ignorati nel processo di revisione.</span><span class="sxs-lookup"><span data-stu-id="79caa-134">Because inclusive copy messages contain the same content, they can usually be skipped in the review process.</span></span> 
    
- <span data-ttu-id="79caa-135">**The Rest**: indica la posta elettronica che non contiene contenuti univoci e pertanto non rientra in nessuna delle tre categorie precedenti.</span><span class="sxs-lookup"><span data-stu-id="79caa-135">**The rest**: This indicates email that doesn't contain any unique content, and therefore doesn't fall into any of the previous three categories.</span></span> <span data-ttu-id="79caa-136">Questi messaggi di posta elettronica non devono essere esaminati.</span><span class="sxs-lookup"><span data-stu-id="79caa-136">These email messages don't need to be reviewed.</span></span> <span data-ttu-id="79caa-137">Se un messaggio contiene un allegato che non è incluso in una posta elettronica inclusa in un secondo momento, potrebbe essere necessario esaminare l'allegato.</span><span class="sxs-lookup"><span data-stu-id="79caa-137">If a message contains an attachment that isn't on a later inclusive email, then the attachment might need to be reviewed.</span></span> <span data-ttu-id="79caa-138">Ciò è indicato dall'esistenza di un messaggio di posta elettronica meno incluso all'interno del thread.</span><span class="sxs-lookup"><span data-stu-id="79caa-138">This is indicated by the existence of an inclusive minus email within the thread.</span></span>
    
<span data-ttu-id="79caa-139">I risultati degli **allegati** visualizzano il numero di allegati, in base al tipo di elementi unici e duplicati.</span><span class="sxs-lookup"><span data-stu-id="79caa-139">The **Attachments** results display the number of attachments, according to such type as unique and duplicates.</span></span> 
  
![Risultati quasi duplicati e thread di posta elettronica](../media/54491303-0ee3-4739-b42e-d1ee486842fd.png)
  
## <a name="see-also"></a><span data-ttu-id="79caa-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="79caa-141">See also</span></span>

[<span data-ttu-id="79caa-142">Advanced eDiscovery (classico)</span><span class="sxs-lookup"><span data-stu-id="79caa-142">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="79caa-143">Informazioni sulla somiglianza del documento</span><span class="sxs-lookup"><span data-stu-id="79caa-143">Understanding document similarity</span></span>](understand-document-similarity-in-advanced-ediscovery.md)
  
[<span data-ttu-id="79caa-144">Impostazione delle opzioni di analisi</span><span class="sxs-lookup"><span data-stu-id="79caa-144">Setting Analyze options</span></span>](set-analyze-options-in-advanced-ediscovery.md)
  
[<span data-ttu-id="79caa-145">Impostazione Ignora testo</span><span class="sxs-lookup"><span data-stu-id="79caa-145">Setting ignore text</span></span>](set-ignore-text-in-advanced-ediscovery.md)
  
[<span data-ttu-id="79caa-146">Impostazione analisi impostazioni avanzate</span><span class="sxs-lookup"><span data-stu-id="79caa-146">Setting Analyze advanced settings</span></span>](view-analyze-results-in-advanced-ediscovery.md)

