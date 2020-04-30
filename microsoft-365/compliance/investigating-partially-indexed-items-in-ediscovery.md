---
title: Analisi degli elementi parzialmente indicizzati in eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/26/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 4e8ff113-6361-41e2-915a-6338a7e2a1ed
description: Gli elementi parzialmente indicizzati (denominati anche elementi non indicizzati) sono elementi e documenti delle cassette postali di Exchange nei siti di SharePoint e OneDrive che per qualche motivo non sono stati completamente indicizzati per la ricerca di contenuto. In questo articolo, è possibile capire perché gli elementi non possono essere indicizzati per la ricerca e vengono restituiti come elementi parzialmente indicizzati, identificare gli errori di ricerca per gli elementi parzialmente indicizzati e utilizzare uno script di PowerShell per determinare l'esposizione dell'organizzazione agli elementi di posta elettronica parzialmente indicizzati.
ms.openlocfilehash: 0053ec5b03f5d32af1a39be94474c05f74ec3234
ms.sourcegitcommit: 60c1932dcca249355ef7134df0ceb0e57757dc81
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/29/2020
ms.locfileid: "43942129"
---
# <a name="investigating-partially-indexed-items-in-ediscovery"></a><span data-ttu-id="bbdca-104">Analisi degli elementi parzialmente indicizzati in eDiscovery</span><span class="sxs-lookup"><span data-stu-id="bbdca-104">Investigating partially indexed items in eDiscovery</span></span>

<span data-ttu-id="bbdca-105">Una ricerca di contenuto eseguita dal centro sicurezza & conformità include automaticamente gli elementi parzialmente indicizzati nei risultati della ricerca stimati durante l'esecuzione di una ricerca.</span><span class="sxs-lookup"><span data-stu-id="bbdca-105">A Content Search that you run from the Security & Compliance Center automatically includes partially indexed items in the estimated search results when you run a search.</span></span> <span data-ttu-id="bbdca-106">Gli elementi parzialmente indicizzati sono gli elementi della cassetta postale di Exchange e i documenti sui siti di SharePoint e OneDrive for business che per qualche motivo non sono stati completamente indicizzati per la ricerca.</span><span class="sxs-lookup"><span data-stu-id="bbdca-106">Partially indexed items are Exchange mailbox items and documents on SharePoint and OneDrive for Business sites that for some reason weren't completely indexed for search.</span></span> <span data-ttu-id="bbdca-107">La maggior parte dei messaggi di posta elettronica e i documenti del sito vengono indicizzati correttamente perché rientrano nei [limiti di indicizzazione dei messaggi di posta elettronica](limits-for-content-search.md#indexing-limits-for-email-messages)</span><span class="sxs-lookup"><span data-stu-id="bbdca-107">Most email messages and site documents are successfully indexed because they fall within the [Indexing limits for email messages](limits-for-content-search.md#indexing-limits-for-email-messages).</span></span> <span data-ttu-id="bbdca-108">Tuttavia, alcuni elementi possono superare questi limiti di indicizzazione e verranno parzialmente indicizzati.</span><span class="sxs-lookup"><span data-stu-id="bbdca-108">However, some items may exceed these indexing limits, and will be partially indexed.</span></span> <span data-ttu-id="bbdca-109">Di seguito sono riportati altri motivi per i quali gli elementi non possono essere indicizzati per la ricerca e vengono restituiti come elementi parzialmente indicizzati durante l'esecuzione di una ricerca di contenuto:</span><span class="sxs-lookup"><span data-stu-id="bbdca-109">Here are other reasons why items can't be indexed for search and are returned as partially indexed items when you run a Content Search:</span></span>
  
- <span data-ttu-id="bbdca-110">I messaggi di posta elettronica dispongono di un file allegato di un tipo di file che non può essere indicizzato. nella maggior parte dei casi, il tipo di file non è [riconosciuto o non è supportato per l'indicizzazione](partially-indexed-items-in-content-search.md#file-types-not-indexed-for-search)</span><span class="sxs-lookup"><span data-stu-id="bbdca-110">Email messages have an attached file of a file type that can't be indexed; in most cases, the file type is [unrecognized or unsupported for indexing](partially-indexed-items-in-content-search.md#file-types-not-indexed-for-search)</span></span>
    
- <span data-ttu-id="bbdca-111">I messaggi di posta elettronica dispongono di un file allegato privo di un gestore valido, ad esempio file di immagine. Questa è la causa più comune degli elementi di posta elettronica parzialmente indicizzati</span><span class="sxs-lookup"><span data-stu-id="bbdca-111">Email messages have an attached file without a valid handler, such as image files; this is the most common cause of partially indexed email items</span></span>
    
- <span data-ttu-id="bbdca-112">Troppi file allegati a un messaggio di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="bbdca-112">Too many files attached to an email message</span></span>
    
- <span data-ttu-id="bbdca-113">Un file allegato a un messaggio di posta elettronica è troppo grande</span><span class="sxs-lookup"><span data-stu-id="bbdca-113">A file attached to an email message is too large</span></span>
    
- <span data-ttu-id="bbdca-114">Il tipo di file è supportato per l'indicizzazione, ma si è verificato un errore di indicizzazione per un file specifico.</span><span class="sxs-lookup"><span data-stu-id="bbdca-114">The file type is supported for indexing but an indexing error occurred for a specific file</span></span>
    
<span data-ttu-id="bbdca-115">Anche se varia, la maggior parte delle organizzazioni clienti ha meno dell'1% del contenuto in base al volume e meno del 12% del contenuto in base alle dimensioni parzialmente indicizzate.</span><span class="sxs-lookup"><span data-stu-id="bbdca-115">Although it varies, most organizations customers have less than 1% of content by volume and less than 12% of content by size that is partially indexed.</span></span> <span data-ttu-id="bbdca-116">Il motivo della differenza tra il volume e la dimensione è che i file più grandi hanno una probabilità maggiore di contenere contenuto che non può essere completamente indicizzato.</span><span class="sxs-lookup"><span data-stu-id="bbdca-116">The reason for the difference between the volume versus size is that larger files have a higher probability of containing content that can't be completely indexed.</span></span>
  
## <a name="why-does-the-partially-indexed-item-count-change-for-a-search"></a><span data-ttu-id="bbdca-117">Perché il conteggio degli elementi parzialmente indicizzato cambia per una ricerca?</span><span class="sxs-lookup"><span data-stu-id="bbdca-117">Why does the partially indexed item count change for a search?</span></span>

<span data-ttu-id="bbdca-118">Dopo aver eseguito una ricerca contenuto nel centro sicurezza & conformità, il numero totale e le dimensioni degli elementi parzialmente indicizzati nei percorsi ricercati sono elencati nelle statistiche dei risultati di ricerca visualizzati nelle statistiche dettagliate per la ricerca.</span><span class="sxs-lookup"><span data-stu-id="bbdca-118">After you run a Content Search in the Security & Compliance Center, the total number and size of partially indexed items in the locations that were searched are listed in the search result statistics that are displayed in the detailed statistics for the search.</span></span> <span data-ttu-id="bbdca-119">Nota Queste sono denominate *voci non indicizzate* nelle statistiche di ricerca.</span><span class="sxs-lookup"><span data-stu-id="bbdca-119">Note these are called  *unindexed items*  in the search statistics.</span></span> <span data-ttu-id="bbdca-120">Di seguito sono riportati alcuni aspetti che influiscono sul numero di elementi parzialmente indicizzati restituiti nei risultati della ricerca:</span><span class="sxs-lookup"><span data-stu-id="bbdca-120">Here are a few things that will affect the number of partially indexed items that are returned in the search results:</span></span> 
  
- <span data-ttu-id="bbdca-121">Se un elemento è parzialmente indicizzato e corrisponde alla query di ricerca, è incluso sia nel conteggio (sia nelle dimensioni) degli elementi dei risultati di ricerca e degli elementi parzialmente indicizzati.</span><span class="sxs-lookup"><span data-stu-id="bbdca-121">If an item is partially indexed and matches the search query, it's included in both the count (and size) of search result items and partially indexed items.</span></span> <span data-ttu-id="bbdca-122">Tuttavia, quando vengono esportati i risultati della stessa ricerca, l'elemento viene incluso solo con un set di risultati di ricerca. non è incluso come elemento parzialmente indicizzato.</span><span class="sxs-lookup"><span data-stu-id="bbdca-122">However, when the results of that same search are exported, the item is included only with set of search results; it's not included as a partially indexed item.</span></span>
    
- <span data-ttu-id="bbdca-123">Se si specifica un intervallo di date per una query di ricerca, inclusa nella query di parole chiave o tramite una condizione, qualsiasi elemento parzialmente indicizzato che non corrisponde all'intervallo di date non è incluso nel numero di elementi parzialmente indicizzati.</span><span class="sxs-lookup"><span data-stu-id="bbdca-123">If you specify a date range for a search query (by including it in the keyword query or by using a condition), any partially indexed item that doesn't match the date range isn't included in the count of partially indexed items.</span></span> <span data-ttu-id="bbdca-124">Solo gli elementi parzialmente indicizzati che rientrano nell'intervallo di date sono inclusi nel numero di elementi parzialmente indicizzati.</span><span class="sxs-lookup"><span data-stu-id="bbdca-124">Only the partially indexed items that fall within date range are included in the count of partially indexed items.</span></span>
    
 <span data-ttu-id="bbdca-125">**Nota:** Gli elementi parzialmente indicizzati che si trovano in siti di SharePoint e OneDrive *non sono* inclusi nella stima degli elementi parzialmente indicizzati visualizzati nelle statistiche dettagliate per la ricerca.</span><span class="sxs-lookup"><span data-stu-id="bbdca-125">**Note:** Partially indexed items located in SharePoint and OneDrive sites  *are not*  included in the estimate of partially indexed items that's displayed in the detailed statistics for the search.</span></span> <span data-ttu-id="bbdca-126">Tuttavia, gli elementi parzialmente indicizzati possono essere esportati quando si esportano i risultati di una ricerca di contenuto.</span><span class="sxs-lookup"><span data-stu-id="bbdca-126">However, partially indexed items can be exported when you export the results of a Content Search.</span></span> <span data-ttu-id="bbdca-127">Ad esempio, se si cercano solo i siti in una ricerca di contenuto, gli elementi parzialmente indicizzati per il numero stimato saranno pari a zero.</span><span class="sxs-lookup"><span data-stu-id="bbdca-127">For example, if you only search sites in a Content Search, the estimated number partially indexed items will be zero.</span></span> 
  
## <a name="calculating-the-ratio-of-partially-indexed-items-in-your-organization"></a><span data-ttu-id="bbdca-128">Calcolo del rapporto tra gli elementi parzialmente indicizzati nell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="bbdca-128">Calculating the ratio of partially indexed items in your organization</span></span>

<span data-ttu-id="bbdca-129">Per comprendere l'esposizione dell'organizzazione a elementi parzialmente indicizzati, è possibile eseguire una ricerca per tutto il contenuto in tutte le cassette postali (utilizzando una query parola chiave vuota).</span><span class="sxs-lookup"><span data-stu-id="bbdca-129">To understand your organization's exposure to partially indexed items, you can run a search for all content in all mailboxes (by using a blank keyword query).</span></span> <span data-ttu-id="bbdca-130">Nell'esempio seguente, sono presenti 56.208 (4.830 MB) elementi completamente indicizzati e 470 (316 MB) di elementi parzialmente indicizzati.</span><span class="sxs-lookup"><span data-stu-id="bbdca-130">In the following example below, there are 56,208 (4,830 MB) fully indexed items and 470 (316 MB) partially indexed items.</span></span>
  
![Esempio di statistiche di ricerca che mostrano elementi parzialmente indicizzati](../media/0f6a5cf7-4c98-44a0-a0dd-5aed67124641.png)
  
<span data-ttu-id="bbdca-132">Per determinare la percentuale di elementi parzialmente indicizzati, è possibile utilizzare i calcoli riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="bbdca-132">You can determine the percentage of partially indexed items by using the following calculations.</span></span>
  
 <span data-ttu-id="bbdca-133">**Per calcolare il rapporto tra gli elementi parzialmente indicizzati nell'organizzazione:**</span><span class="sxs-lookup"><span data-stu-id="bbdca-133">**To calculate the ratio of partially indexed items in your organization:**</span></span>

`(Total number of partially indexed items/Total number of items) x 100`


`(470/56,208) x 100 = 0.84%`
 
<span data-ttu-id="bbdca-134">Utilizzando i risultati della ricerca dell'esempio precedente, il 84% di tutti gli elementi delle cassette postali è parzialmente indicizzato.</span><span class="sxs-lookup"><span data-stu-id="bbdca-134">By using the search results from the previous example, .84% of all mailboxes items are partially indexed.</span></span>
  
 <span data-ttu-id="bbdca-135">**Per calcolare la percentuale delle dimensioni degli elementi parzialmente indicizzati nell'organizzazione:**</span><span class="sxs-lookup"><span data-stu-id="bbdca-135">**To calculate the percentage of the size of partially indexed items in your organization:**</span></span>

`(Size of all partially indexed items/Size of all items) x 100`

`(316 MB/4830 MB) x 100 = 6.54%`

<span data-ttu-id="bbdca-136">Nell'esempio precedente, il 6,54% delle dimensioni totali degli elementi delle cassette postali è compreso tra gli elementi parzialmente indicizzati.</span><span class="sxs-lookup"><span data-stu-id="bbdca-136">So in the previous example, 6.54% of the total size of mailbox items are from partially indexed items.</span></span> <span data-ttu-id="bbdca-137">Come indicato in precedenza, la maggior parte delle organizzazioni clienti ha meno dell'1% del contenuto in base al volume e meno del 12% del contenuto in base alle dimensioni parzialmente indicizzate.</span><span class="sxs-lookup"><span data-stu-id="bbdca-137">As previously stated, most organizations customers have less than 1% of content by volume and less than 12% of content by size that is partially indexed.</span></span>

## <a name="working-with-partially-indexed-items"></a><span data-ttu-id="bbdca-138">Utilizzo di elementi parzialmente indicizzati</span><span class="sxs-lookup"><span data-stu-id="bbdca-138">Working with partially indexed items</span></span>

<span data-ttu-id="bbdca-139">Nei casi in cui è necessario esaminare parzialmente gli elementi per convalidare che non contengono informazioni rilevanti, è possibile [esportare un rapporto di ricerca contenuto](export-a-content-search-report.md) che contiene informazioni sugli elementi parzialmente indicizzati.</span><span class="sxs-lookup"><span data-stu-id="bbdca-139">In cases when you need to examine partially items to validate that they don't contain relevant information, you can [export a content search report](export-a-content-search-report.md) that contains information about partially indexed items.</span></span> <span data-ttu-id="bbdca-140">Quando si esporta un rapporto di ricerca contenuto, assicurarsi di scegliere una delle opzioni di esportazione che includa gli elementi parzialmente indicizzati.</span><span class="sxs-lookup"><span data-stu-id="bbdca-140">When you export a content search report, be sure to choose one of the export options that includes partially indexed items.</span></span> 
  
![Scegliere la seconda o la terza opzione per esportare gli elementi parzialmente indicizzati](../media/624a62b4-78f7-4329-ab5d-e62e3b369885.png)
  
<span data-ttu-id="bbdca-142">Quando si esportano i risultati della ricerca del contenuto o un rapporto di ricerca contenuto utilizzando una di queste opzioni, l'esportazione include un report denominato unindexed Items. csv.</span><span class="sxs-lookup"><span data-stu-id="bbdca-142">When you export content search results or a content search report using one of these options, the export includes a report named Unindexed Items.csv.</span></span> <span data-ttu-id="bbdca-143">Questo rapporto include la maggior parte delle stesse informazioni del file ResultsLog. csv. Tuttavia, il file unindexed Items. csv include anche due campi correlati agli elementi parzialmente indicizzati: **tag di errore** e proprietà di **errore**.</span><span class="sxs-lookup"><span data-stu-id="bbdca-143">This report includes most of the same information as the ResultsLog.csv file; however, the Unindexed Items.csv file also includes two fields related to partially indexed items: **Error Tags** and **Error Properties**.</span></span> <span data-ttu-id="bbdca-144">Questi campi contengono informazioni sull'errore di indicizzazione per ogni elemento parzialmente indicizzato.</span><span class="sxs-lookup"><span data-stu-id="bbdca-144">These fields contain information about the indexing error for each partially indexed item.</span></span> <span data-ttu-id="bbdca-145">L'utilizzo delle informazioni contenute in questi due campi consente di determinare se l'errore di indicizzazione per un determinato impatto dell'indagine.</span><span class="sxs-lookup"><span data-stu-id="bbdca-145">Using the information in these two fields can help you determine whether or not the indexing error for a particular impacts your investigation.</span></span> <span data-ttu-id="bbdca-146">In caso affermativo, è possibile eseguire una ricerca di contenuto mirato e recuperare ed esportare messaggi di posta elettronica specifici e documenti di SharePoint o OneDrive in modo da poterli esaminare per determinare se sono rilevanti per la propria indagine.</span><span class="sxs-lookup"><span data-stu-id="bbdca-146">If it does, you can perform a targeted content search and retrieve and export specific email messages and SharePoint or OneDrive documents so that you can examine them to determine if they're relevant to your investigation.</span></span> <span data-ttu-id="bbdca-147">Per istruzioni dettagliate, vedere [preparare un file CSV per una ricerca di contenuto mirata in Office 365](csv-file-for-an-id-list-content-search.md).</span><span class="sxs-lookup"><span data-stu-id="bbdca-147">For step-by-step instructions, see [Prepare a CSV file for a targeted Content Search in Office 365](csv-file-for-an-id-list-content-search.md).</span></span>
  
 <span data-ttu-id="bbdca-148">**Nota:** Il file unindexed Items. csv contiene anche campi denominati **tipo di errore** e **messaggio di errore**.</span><span class="sxs-lookup"><span data-stu-id="bbdca-148">**Note:** The Unindexed Items.csv file also contains fields named **Error Type** and **Error Message**.</span></span> <span data-ttu-id="bbdca-149">Si tratta di campi legacy che contengono informazioni simili alle informazioni nei campi dei **tag di errore** e delle **proprietà di errore** , ma con informazioni meno dettagliate.</span><span class="sxs-lookup"><span data-stu-id="bbdca-149">These are legacy fields that contain information that is similar to the information in the **Error Tags** and **Error Properties** fields, but with less detailed information.</span></span> <span data-ttu-id="bbdca-150">È possibile ignorare tali campi legacy.</span><span class="sxs-lookup"><span data-stu-id="bbdca-150">You can safely ignore these legacy fields.</span></span> 
  
## <a name="errors-related-to-partially-indexed-items"></a><span data-ttu-id="bbdca-151">Errori relativi agli elementi parzialmente indicizzati</span><span class="sxs-lookup"><span data-stu-id="bbdca-151">Errors related to partially indexed items</span></span>

<span data-ttu-id="bbdca-152">I tag di errore sono costituiti da due parti di informazioni, l'errore e il tipo di file.</span><span class="sxs-lookup"><span data-stu-id="bbdca-152">Error tags are made up of two pieces of information, the error and the file type.</span></span> <span data-ttu-id="bbdca-153">Ad esempio, in questa coppia errore/filetype:</span><span class="sxs-lookup"><span data-stu-id="bbdca-153">For example, in this error/filetype pair:</span></span>

```text
 parseroutputsize_xls
```

   
 <span data-ttu-id="bbdca-154">`parseroutputsize`è l'errore ed `xls` è il tipo di file del file su cui si è verificato l'errore.</span><span class="sxs-lookup"><span data-stu-id="bbdca-154">`parseroutputsize` is the error and  `xls` is the file type of the file the error occurred on.</span></span> <span data-ttu-id="bbdca-155">Nei casi in cui il tipo di file non è stato riconosciuto o il tipo di file non è stato applicato all'errore, `noformat` verrà visualizzato il valore al posto del tipo di file.</span><span class="sxs-lookup"><span data-stu-id="bbdca-155">In cases were the file type wasn't recognized or the file type was doesn't apply to the error, you will see the value  `noformat` in place of the file type.</span></span> 
  
<span data-ttu-id="bbdca-156">Di seguito è riportato un elenco di errori di indicizzazione e una descrizione della possibile causa dell'errore.</span><span class="sxs-lookup"><span data-stu-id="bbdca-156">The following is a list of indexing errors and a description of the possible cause of the error.</span></span>
  
|<span data-ttu-id="bbdca-157">**Tag di errore**</span><span class="sxs-lookup"><span data-stu-id="bbdca-157">**Error tag**</span></span>|<span data-ttu-id="bbdca-158">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="bbdca-158">**Description**</span></span>|
|:-----|:-----|
| `attachmentcount` <br/> |<span data-ttu-id="bbdca-159">Un messaggio di posta elettronica aveva troppi allegati e alcuni di questi allegati non sono stati elaborati.</span><span class="sxs-lookup"><span data-stu-id="bbdca-159">An email message had too many attachments, and some of these attachments weren't processed.</span></span>  <br/> |
| `attachmentdepth` <br/> |<span data-ttu-id="bbdca-160">La funzione di recupero contenuto e l'analizzatore del documento hanno rilevato troppi livelli di allegati annidati all'interno di altri allegati.</span><span class="sxs-lookup"><span data-stu-id="bbdca-160">The content retriever and document parser found too many levels of attachments nested inside other attachments.</span></span> <span data-ttu-id="bbdca-161">Alcuni di questi allegati non sono stati elaborati.</span><span class="sxs-lookup"><span data-stu-id="bbdca-161">Some of these attachments were not processed.</span></span>  <br/> |
| `attachmentrms` <br/> |<span data-ttu-id="bbdca-162">Un allegato non è stato in grado di decodificare perché è protetto da RMS.</span><span class="sxs-lookup"><span data-stu-id="bbdca-162">An attachment failed decoding because it was RMS-protected.</span></span>  <br/> |
| `attachmentsize` <br/> |<span data-ttu-id="bbdca-163">Un file allegato a un messaggio di posta elettronica è troppo grande e non è stato possibile elaborarlo.</span><span class="sxs-lookup"><span data-stu-id="bbdca-163">A file attached to an email message was too large and couldn't be processed.</span></span>  <br/> |
| `indexingtruncated` <br/> |<span data-ttu-id="bbdca-164">Quando si scrive il messaggio di posta elettronica elaborato nell'indice, una delle proprietà indicizzabili è troppo grande ed è stata troncata.</span><span class="sxs-lookup"><span data-stu-id="bbdca-164">When writing the processed email message to the index, one of the indexable properties was too large and was truncated.</span></span> <span data-ttu-id="bbdca-165">Le proprietà troncate sono elencate nel campo proprietà errore.</span><span class="sxs-lookup"><span data-stu-id="bbdca-165">The truncated properties are listed in Error Properties field.</span></span>  <br/> |
| `invalidunicode` <br/> |<span data-ttu-id="bbdca-166">Un messaggio di posta elettronica contiene testo che non può essere elaborato come Unicode valido.</span><span class="sxs-lookup"><span data-stu-id="bbdca-166">An email message contained text that couldn't be processed as valid Unicode.</span></span> <span data-ttu-id="bbdca-167">L'indicizzazione per questo elemento potrebbe essere incompleta.</span><span class="sxs-lookup"><span data-stu-id="bbdca-167">Indexing for this item may be incomplete.</span></span>  <br/> |
| `parserencrypted` <br/> |<span data-ttu-id="bbdca-168">Il contenuto dell'allegato o del messaggio di posta elettronica è crittografato e Microsoft 365 non è in grado di decodificare il contenuto.</span><span class="sxs-lookup"><span data-stu-id="bbdca-168">The content of attachment or email message is encrypted, and Microsoft 365 couldn't decode the content.</span></span>  <br/> |
| `parsererror` <br/> |<span data-ttu-id="bbdca-169">Si è verificato un errore sconosciuto durante l'analisi.</span><span class="sxs-lookup"><span data-stu-id="bbdca-169">An unknown error occurred during parsing.</span></span> <span data-ttu-id="bbdca-170">Questo in genere deriva da un errore del software o da un arresto del servizio.</span><span class="sxs-lookup"><span data-stu-id="bbdca-170">This typically results from a software bug or a service crash.</span></span>  <br/> |
| `parserinputsize` <br/> |<span data-ttu-id="bbdca-171">Un allegato è troppo grande per la gestione del parser e l'analisi di tale allegato non è stata eseguita o non è stata completata.</span><span class="sxs-lookup"><span data-stu-id="bbdca-171">An attachment was too large for the parser to handle, and the parsing of that attachment didn't happen or wasn't completed.</span></span>  <br/> |
| `parsermalformed` <br/> |<span data-ttu-id="bbdca-172">Un allegato non è stato corretto e non è stato possibile gestirlo dal parser.</span><span class="sxs-lookup"><span data-stu-id="bbdca-172">An attachment was malformed and couldn't be handled by the parser.</span></span> <span data-ttu-id="bbdca-173">Questo risultato può essere costituito da vecchi formati di file, file creati da software incompatibili o virus che fingono di essere diversi da quelli richiesti.</span><span class="sxs-lookup"><span data-stu-id="bbdca-173">This result from can old file formats, files created by incompatible software, or viruses pretending to be something other than claimed.</span></span>  <br/> |
| `parseroutputsize` <br/> |<span data-ttu-id="bbdca-174">L'output dell'analisi di un allegato è troppo grande e deve essere troncato.</span><span class="sxs-lookup"><span data-stu-id="bbdca-174">The output from the parsing of an attachment was too large and had to be truncated.</span></span>  <br/> |
| `parserunknowntype` <br/> |<span data-ttu-id="bbdca-175">Un allegato ha un tipo di file che Microsoft 365 non è in grado di rilevare.</span><span class="sxs-lookup"><span data-stu-id="bbdca-175">An attachment had a file type that Microsoft 365 couldn't detect.</span></span>  <br/> |
| `parserunsupportedtype` <br/> |<span data-ttu-id="bbdca-176">Un allegato aveva un tipo di file rilevato da Office 365could, ma l'analisi del tipo di file non è supportata.</span><span class="sxs-lookup"><span data-stu-id="bbdca-176">An attachment had a file type that Office 365could detect, but parsing that file type isn't supported.</span></span>  <br/> |
| `propertytoobig` <br/> |<span data-ttu-id="bbdca-177">Il valore di una proprietà di posta elettronica nell'archivio di Exchange era troppo grande per essere recuperato e il messaggio non è stato elaborato.</span><span class="sxs-lookup"><span data-stu-id="bbdca-177">The value of an email property in Exchange Store was too large to be retrieved and the message couldn't be processed.</span></span> <span data-ttu-id="bbdca-178">Questo accade in genere solo alla proprietà Body di un messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="bbdca-178">This typically only happens to the body property of an email message.</span></span>  <br/> |
| `retrieverrms` <br/> |<span data-ttu-id="bbdca-179">La funzione di recupero contenuto non è riuscita a decodificare un messaggio protetto da RMS.</span><span class="sxs-lookup"><span data-stu-id="bbdca-179">The content retriever failed to decode an RMS-protected message.</span></span>  <br/> |
| `wordbreakertruncated` <br/> |<span data-ttu-id="bbdca-180">Nel documento sono state identificate troppe parole durante l'indicizzazione.</span><span class="sxs-lookup"><span data-stu-id="bbdca-180">Too many words were identified in the document during indexing.</span></span> <span data-ttu-id="bbdca-181">L'elaborazione della proprietà si è interrotta al raggiungimento del limite e la proprietà è troncata.</span><span class="sxs-lookup"><span data-stu-id="bbdca-181">Processing of the property stopped when reaching the limit, and the property is truncated.</span></span>  <br/> |
   
<span data-ttu-id="bbdca-182">Nei campi di errore vengono descritti i campi che sono stati modificati dall'errore di elaborazione elencato nel campo tag error.</span><span class="sxs-lookup"><span data-stu-id="bbdca-182">Error fields describe which fields are affected by the processing error listed in the Error Tags field.</span></span> <span data-ttu-id="bbdca-183">Se si esegue la ricerca di una proprietà `subject` `participants`, ad esempio, gli errori nel corpo del messaggio non influiscono sui risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="bbdca-183">If you're searching a property such as  `subject` or  `participants`, errors in the body of the message won't impact the results of your search.</span></span> <span data-ttu-id="bbdca-184">Questo può essere utile quando si determinano esattamente gli elementi parzialmente indicizzati che potrebbe essere necessario approfondire.</span><span class="sxs-lookup"><span data-stu-id="bbdca-184">This can be useful when determining exactly which partially indexed items you might need to further investigate.</span></span>
  
## <a name="using-a-powershell-script-to-determine-your-organizations-exposure-to-partially-indexed-email-items"></a><span data-ttu-id="bbdca-185">Utilizzo di uno script di PowerShell per determinare l'esposizione dell'organizzazione a elementi di posta elettronica parzialmente indicizzati</span><span class="sxs-lookup"><span data-stu-id="bbdca-185">Using a PowerShell script to determine your organization's exposure to partially indexed email items</span></span>

<span data-ttu-id="bbdca-186">Nei passaggi seguenti viene illustrato come eseguire uno script di PowerShell che consente di cercare tutti gli elementi in tutte le cassette postali di Exchange e quindi di generare un report sul rapporto tra l'organizzazione e gli elementi di posta elettronica parzialmente indicizzati (conta e per dimensione) e visualizza il numero di elementi (e il relativo tipo di file) per ogni errore di indicizzazione che si verifica.</span><span class="sxs-lookup"><span data-stu-id="bbdca-186">The following steps show you how to run a PowerShell script that searches for all items in all Exchange mailboxes, and then generates a report about your organization's ratio of partially indexed email items (by count and by size) and displays the number of items (and their file type) for each indexing error that occurs.</span></span> <span data-ttu-id="bbdca-187">Utilizzare le descrizioni dei tag di errore nella sezione precedente per identificare l'errore di indicizzazione.</span><span class="sxs-lookup"><span data-stu-id="bbdca-187">Use the error tag descriptions in the previous section to identify the indexing error.</span></span>
  
1. <span data-ttu-id="bbdca-188">Salvare il testo seguente in un file di script di Windows PowerShell utilizzando un suffisso FileName di. ps1. ad esempio, `PartiallyIndexedItems.ps1`.</span><span class="sxs-lookup"><span data-stu-id="bbdca-188">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `PartiallyIndexedItems.ps1`.</span></span>

```powershell
  write-host "**************************************************"
  write-host "     Security & Compliance Center      " -foregroundColor yellow -backgroundcolor darkgreen
  write-host "   eDiscovery Partially Indexed Item Statistics   " -foregroundColor yellow -backgroundcolor darkgreen
  write-host "**************************************************"
  " " 
  # Create a search with Error Tags Refinders enabled
  Remove-ComplianceSearch "RefinerTest" -Confirm:$false -ErrorAction 'SilentlyContinue'
  New-ComplianceSearch -Name "RefinerTest" -ContentMatchQuery "size>0" -RefinerNames ErrorTags -ExchangeLocation ALL
  Start-ComplianceSearch "RefinerTest"
  # Loop while search is in progress
  do{
      Write-host "Waiting for search to complete..."
      Start-Sleep -s 5
      $complianceSearch = Get-ComplianceSearch "RefinerTest"
  }while ($complianceSearch.Status -ne 'Completed')
  $refiners = $complianceSearch.Refiners | ConvertFrom-Json
  $errorTagProperties = $refiners.Entries | Get-Member -MemberType NoteProperty
  $partiallyIndexedRatio = $complianceSearch.UnindexedItems / $complianceSearch.Items
  $partiallyIndexedSizeRatio = $complianceSearch.UnindexedSize / $complianceSearch.Size
  " "
  "===== Partially indexed items ====="
  "         Total          Ratio"
  "Count    {0:N0}{1:P2}" -f $complianceSearch.Items.ToString("N0").PadRight(15, " "), $partiallyIndexedRatio
  "Size(GB) {0:N2}{1:P2}" -f ($complianceSearch.Size / 1GB).ToString("N2").PadRight(15, " "), $partiallyIndexedSizeRatio
  " "
  Write-Host ===== Reasons for partially indexed items =====
  foreach($errorTagProperty in $errorTagProperties)
  {
      $name = $refiners.Entries.($errorTagProperty.Name).Name
      $count = $refiners.Entries.($errorTagProperty.Name).TotalCount
      $frag = $name.Split("{_}")
      $errorTag = $frag[0]
      $fileType = $frag[1]
      if ($errorTag -ne $lastErrorTag)
      {
          $errorTag
      }
      "    " + $fileType + " => " + $count
      $lastErrorTag = $errorTag
  }
  
```

2. <span data-ttu-id="bbdca-189">[Connettersi a PowerShell in Centro sicurezza e conformità](https://go.microsoft.com/fwlink/p/?linkid=627084).</span><span class="sxs-lookup"><span data-stu-id="bbdca-189">[Connect to Security & Compliance Center PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627084).</span></span>
    
3. <span data-ttu-id="bbdca-190">In PowerShell Centro sicurezza & conformità, passare alla cartella in cui è stato salvato lo script nel passaggio 1, quindi eseguire lo script. Per esempio:</span><span class="sxs-lookup"><span data-stu-id="bbdca-190">In Security & Compliance Center PowerShell, go to the folder where you saved the script in step 1, and then run the script; for example:</span></span>

    ```powershell
    .\PartiallyIndexedItems.ps1
    ```

<span data-ttu-id="bbdca-191">Di seguito è riportato un esempio per l'output restituito dallo script.</span><span class="sxs-lookup"><span data-stu-id="bbdca-191">Here's an example fo the output returned by the script.</span></span>
  
![Esempio di output da script che genera un report sull'esposizione dell'organizzazione a elementi di posta elettronica parzialmente indicizzati](../media/aeab5943-c15d-431a-bdb2-82f135abc2f3.png)
  
<span data-ttu-id="bbdca-193">Tenere presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="bbdca-193">Note the following:</span></span>
  
1. <span data-ttu-id="bbdca-194">Il numero totale e le dimensioni degli elementi di posta elettronica e il rapporto tra l'organizzazione e gli elementi di posta elettronica parzialmente indicizzati (conteggio e per dimensione)</span><span class="sxs-lookup"><span data-stu-id="bbdca-194">The total number and size of email items, and your organization's ratio of partially indexed email items (by count and by size)</span></span>
    
2. <span data-ttu-id="bbdca-195">Tag di errore dell'elenco e tipi di file corrispondenti per i quali si è verificato l'errore.</span><span class="sxs-lookup"><span data-stu-id="bbdca-195">A list error tags and the corresponding file types for which the error occurred.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="bbdca-196">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bbdca-196">See also</span></span>

<span data-ttu-id="bbdca-197">[Partially indexed items in Content Search in Office 365](partially-indexed-items-in-content-search.md) (Elementi parzialmente indicizzati in Ricerca contenuto in Office 365)</span><span class="sxs-lookup"><span data-stu-id="bbdca-197">[Partially indexed items in Content Search in Office 365](partially-indexed-items-in-content-search.md)</span></span>
