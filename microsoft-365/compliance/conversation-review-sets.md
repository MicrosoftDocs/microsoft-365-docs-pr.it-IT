---
title: Esaminare le conversazioni in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Informazioni sulla funzionalità di ricostruzione delle conversazioni in Advanced eDiscovery (denominato threading delle conversazioni) per ricostruire, esaminare ed esportare conversazioni di chat nei gruppi di Microsoft Teams e Yammer.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 12887ba8dd74c3dab445dcc76e155e274a371539
ms.sourcegitcommit: 8f1721de52dbe3a12c11a0fa5ed0ef5972ca8196
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/17/2021
ms.locfileid: "50838305"
---
# <a name="conversation-threading-in-advanced-ediscovery"></a><span data-ttu-id="10d52-103">Threading delle conversazioni in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="10d52-103">Conversation threading in Advanced eDiscovery</span></span>

<span data-ttu-id="10d52-104">La messaggistica istantanea è un modo pratico per porre domande, condividere idee o comunicare rapidamente tra gruppi di destinatari di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="10d52-104">Instant messaging is a convenient way to ask questions, share ideas, or quickly communicate across large audiences.</span></span> <span data-ttu-id="10d52-105">Poiché le piattaforme di messaggistica istantanea, come i gruppi di Microsoft Teams e Yammer, diventano fondamentali per la collaborazione aziendale, le organizzazioni devono valutare il modo in cui il flusso di lavoro di eDiscovery affronta queste nuove forme di comunicazione e collaborazione.</span><span class="sxs-lookup"><span data-stu-id="10d52-105">As instant messaging platforms, like Microsoft Teams and Yammer groups, become core to enterprise collaboration, organizations must evaluate how their eDiscovery workflow addresses these new forms of communication and collaboration.</span></span>

<span data-ttu-id="10d52-106">La funzionalità di ricostruzione delle conversazioni in Advanced eDiscovery è progettata per consentire l'identificazione del contenuto contestuale e la produzione di visualizzazioni di conversazione distinte.</span><span class="sxs-lookup"><span data-stu-id="10d52-106">The Conversation Reconstruction feature in Advanced eDiscovery is designed to help you identify contextual content and produce distinct conversation views.</span></span> <span data-ttu-id="10d52-107">Questa funzionalità consente di esaminare in modo efficiente e rapido conversazioni complete di messaggistica istantanea (denominate anche conversazioni a *thread)* generate in piattaforme come Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="10d52-107">This capability allows you to efficiently and rapidly review complete instant message conversations (also called *threaded conversations*) that are generated in platforms like Microsoft Teams.</span></span>

<span data-ttu-id="10d52-108">Con la ricostruzione delle conversazioni, puoi usare le funzionalità integrate per ricostruire, rivedere ed esportare conversazioni a thread.</span><span class="sxs-lookup"><span data-stu-id="10d52-108">With Conversation Reconstruction, you can use built-in capabilities to reconstruct, review, and export threaded conversations.</span></span> <span data-ttu-id="10d52-109">Utilizzare la ricostruzione avanzata delle conversazioni di eDiscovery per:</span><span class="sxs-lookup"><span data-stu-id="10d52-109">Use Advanced eDiscovery Conversation Reconstruction to:</span></span>

- <span data-ttu-id="10d52-110">Conservare metadati univoci a livello di messaggio in tutti i messaggi all'interno di una conversazione.</span><span class="sxs-lookup"><span data-stu-id="10d52-110">Preserve unique message-level metadata across all messages within a conversation.</span></span>

- <span data-ttu-id="10d52-111">Raccogliere i messaggi contestuali relativi ai risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="10d52-111">Collect contextual messages around your search results.</span></span>

- <span data-ttu-id="10d52-112">Rivedere, annotare e redigere conversazioni in thread.</span><span class="sxs-lookup"><span data-stu-id="10d52-112">Review, annotate, and redact threaded conversations.</span></span>

- <span data-ttu-id="10d52-113">Esportare singoli messaggi o conversazioni in thread</span><span class="sxs-lookup"><span data-stu-id="10d52-113">Export individual messages or threaded conversations</span></span>

## <a name="terminology"></a><span data-ttu-id="10d52-114">Terminologia</span><span class="sxs-lookup"><span data-stu-id="10d52-114">Terminology</span></span>

<span data-ttu-id="10d52-115">Ecco alcune definizioni utili per iniziare a usare la ricostruzione delle conversazioni.</span><span class="sxs-lookup"><span data-stu-id="10d52-115">Here are few definitions to help you get start using Conversation Reconstruction.</span></span>

- <span data-ttu-id="10d52-116">**Messaggi:** Rappresenta l'unità più piccola di una conversazione.</span><span class="sxs-lookup"><span data-stu-id="10d52-116">**Messages:** Represent the smallest unit of a conversation.</span></span> <span data-ttu-id="10d52-117">I messaggi possono variare in base alle dimensioni, alla struttura e ai metadati.</span><span class="sxs-lookup"><span data-stu-id="10d52-117">Messages may vary in size, structure, and metadata.</span></span> 

- <span data-ttu-id="10d52-118">**Conversazione:** Rappresenta un raggruppamento di uno o più messaggi.</span><span class="sxs-lookup"><span data-stu-id="10d52-118">**Conversation:** Represents a grouping of one or more messages.</span></span> <span data-ttu-id="10d52-119">In diverse applicazioni, le conversazioni possono essere rappresentate in modi diversi.</span><span class="sxs-lookup"><span data-stu-id="10d52-119">Across different applications, conversations may be represented in different ways.</span></span> <span data-ttu-id="10d52-120">In alcune applicazioni esiste un'azione esplicita che deriva dalla risposta a un messaggio esistente.</span><span class="sxs-lookup"><span data-stu-id="10d52-120">In some applications, there is an explicit action that results from replying to an existing message.</span></span> <span data-ttu-id="10d52-121">Le conversazioni vengono formate in modo esplicito a seguito di questa azione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="10d52-121">Conversations are formed explicitly as a result of this user action.</span></span> <span data-ttu-id="10d52-122">Ad esempio, ecco uno screenshot di una conversazione di canale in Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="10d52-122">For example, here is a screenshot of a channel conversation in Microsoft Teams.</span></span>

   ![Conversazione sul canale di Microsoft Teams](../media/threadedchat.png)

   <span data-ttu-id="10d52-124">In altre app (ad esempio i messaggi di chat 1xN in Teams), non esiste una catena di risposta formale e i messaggi vengono invece visualizzati come un "flat river di messaggi" all'interno di un singolo thread.</span><span class="sxs-lookup"><span data-stu-id="10d52-124">In other apps (such as 1xN chat messages in Teams), there is not a formal reply chain and instead messages appear as a "flat river of messages" within a single thread.</span></span> <span data-ttu-id="10d52-125">In questi tipi di app, le conversazioni vengono dedotto da un gruppo di messaggi che si verificano entro un determinato periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="10d52-125">In these types apps, conversations are inferred from a group of messages that occur within a certain time.</span></span> <span data-ttu-id="10d52-126">Questo "raggruppamento soft" dei messaggi (anziché una catena di risposte) rappresenta la conversazione "avanti e indietro" su un argomento specifico di interesse.</span><span class="sxs-lookup"><span data-stu-id="10d52-126">This "soft-grouping" of messages (as opposed to a reply chain) represent the "back and forth" conversation about a specific topic of interest.</span></span>

## <a name="step-1-create-a-draft-collection"></a><span data-ttu-id="10d52-127">Passaggio 1: Creare una raccolta di bozze</span><span class="sxs-lookup"><span data-stu-id="10d52-127">Step 1: Create a draft collection</span></span>

<span data-ttu-id="10d52-128">Dopo aver identificato i custodi e le posizioni dei contenuti rilevanti, è possibile creare una ricerca per trovare contenuto potenzialmente pertinente.</span><span class="sxs-lookup"><span data-stu-id="10d52-128">After you have identified relevant custodians and content locations, you can create a search to find potentially relevant content.</span></span> <span data-ttu-id="10d52-129">Nella scheda **Raccolte** del caso Advanced eDiscovery è possibile creare una raccolta facendo clic su **Nuova raccolta** e seguendo la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="10d52-129">On the **Collections** tab in the Advanced eDiscovery case, you can create a collection by clicking **New collection** and following the wizard.</span></span> <span data-ttu-id="10d52-130">Per informazioni su come creare una raccolta, creare una query di ricerca e visualizzare in anteprima i risultati della ricerca, vedere [Create a draft collection.](create-draft-collection.md)</span><span class="sxs-lookup"><span data-stu-id="10d52-130">For information about how you can create a collection, build a search query, and preview the search results, see [Create a draft collection](create-draft-collection.md).</span></span>

## <a name="step-2-commit-a-draft-collection-to-a-review-set"></a><span data-ttu-id="10d52-131">Passaggio 2: Eseguire il commit di una bozza di raccolta in un set di revisione</span><span class="sxs-lookup"><span data-stu-id="10d52-131">Step 2: Commit a draft collection to a review set</span></span>

<span data-ttu-id="10d52-132">Dopo aver esaminato e finalizzato la query di ricerca in una raccolta, è possibile aggiungere i risultati della ricerca a un set di revisione.</span><span class="sxs-lookup"><span data-stu-id="10d52-132">After you have reviewed and finalized the search query in a collection, you can add the search results to a review set.</span></span> <span data-ttu-id="10d52-133">Quando si aggiungono i risultati della ricerca in un set di revisione, i dati originali vengono copiati in un'area di Archiviazione di Azure per facilitare il processo di revisione e analisi.</span><span class="sxs-lookup"><span data-stu-id="10d52-133">When you add your search results into a review set, the original data is copied to an Azure Storage area to facilitate the review and analysis process.</span></span> <span data-ttu-id="10d52-134">Per ulteriori informazioni sull'aggiunta dei risultati di ricerca a un set di revisione, vedere [Commit di una raccolta di bozze in un set di revisione.](commit-draft-collection.md)</span><span class="sxs-lookup"><span data-stu-id="10d52-134">For more information about adding search results to a review set, see [Commit a draft collection to a review set](commit-draft-collection.md).</span></span>

<span data-ttu-id="10d52-135">Quando aggiungi elementi dalle conversazioni a un set di recensioni, puoi usare l'opzione conversazioni a thread per raccogliere messaggi contestuali dalle conversazioni che contengono elementi che corrispondono ai criteri di ricerca della raccolta.</span><span class="sxs-lookup"><span data-stu-id="10d52-135">When you add items from conversations to a review set, you can use the threaded conversations option to collect contextual messages from conversations that contain items that match the search criteria of the collection.</span></span> <span data-ttu-id="10d52-136">Dopo aver selezionato l'opzione conversazioni di thread, possono verificarsi le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="10d52-136">After you select the thread conversations option, the following things can happen:</span></span>

  ![Recupero conversazioni](../media/messagesandconversations.png)
  
1. <span data-ttu-id="10d52-138">Utilizzando una parola chiave e una query di intervallo di date, la ricerca ha restituito un risultato *nel messaggio 3.*</span><span class="sxs-lookup"><span data-stu-id="10d52-138">Using a keyword and date range query, the search returned a hit on *Message 3*.</span></span> <span data-ttu-id="10d52-139">Questo messaggio fa parte di una conversazione più ampia, illustrata da *CRC1.*</span><span class="sxs-lookup"><span data-stu-id="10d52-139">This message was part of a larger conversation, illustrated by *CRC1*.</span></span>
  
2. <span data-ttu-id="10d52-140">Quando si aggiungono i dati in un set di revisione e si abilitano le opzioni di recupero delle conversazioni, Advanced eDiscovery torna indietro e raccoglie altri elementi in *CRC1.*</span><span class="sxs-lookup"><span data-stu-id="10d52-140">When you add the data into a review set and enable the conversation retrieval options, Advanced eDiscovery will go back and collect other items in *CRC1*.</span></span>
  
3. <span data-ttu-id="10d52-141">Dopo aver aggiunto gli elementi al set di revisione, è possibile esaminare tutti i singoli messaggi di *CRC1.*</span><span class="sxs-lookup"><span data-stu-id="10d52-141">After the items have been added to the review set, you can review all the individual messages from *CRC1*.</span></span>

<span data-ttu-id="10d52-142">Per abilitato l'opzione conversazioni in thread, vedere [Commit di una bozza di raccolta in un set di revisione.](commit-draft-collection.md#commit-a-draft-collection-to-a-review-set)</span><span class="sxs-lookup"><span data-stu-id="10d52-142">To enabled the threaded conversations option, see [Commit a draft collection to a review set](commit-draft-collection.md#commit-a-draft-collection-to-a-review-set).</span></span>
  
## <a name="step-3-review-and-export-threaded-conversations"></a><span data-ttu-id="10d52-143">Passaggio 3: esaminare ed esportare conversazioni in thread</span><span class="sxs-lookup"><span data-stu-id="10d52-143">Step 3: Review and export threaded conversations</span></span>

<span data-ttu-id="10d52-144">Dopo che il contenuto è stato elaborato e aggiunto al set di recensioni, puoi iniziare a esaminare i dati nel set di recensioni.</span><span class="sxs-lookup"><span data-stu-id="10d52-144">After the content has been processed and added to the review set, you can start reviewing the data in the review set.</span></span> <span data-ttu-id="10d52-145">Le funzionalità di revisione sono diverse a seconda che il contenuto sia stato aggiunto a un set di revisione standard o a un set di recensioni di conversazione.</span><span class="sxs-lookup"><span data-stu-id="10d52-145">The review capabilities are different depending on whether the content was added to a standard review set or a conversation review set.</span></span>

### <a name="reviewing-conversations-in-a-standard-review-set"></a><span data-ttu-id="10d52-146">Revisione delle conversazioni in un set di recensioni standard</span><span class="sxs-lookup"><span data-stu-id="10d52-146">Reviewing conversations in a standard review set</span></span>

<span data-ttu-id="10d52-147">In un set di revisione standard, i messaggi vengono elaborati e visualizzati come singoli elementi, in modo analogo a come vengono archiviati in una cartella delle cassette postali.</span><span class="sxs-lookup"><span data-stu-id="10d52-147">In a standard review set, messages are processed and displayed as individual items, similar to how they're stored in a mailbox folder.</span></span> <span data-ttu-id="10d52-148">In questo flusso di lavoro, ogni messaggio viene elaborato come elemento separato.</span><span class="sxs-lookup"><span data-stu-id="10d52-148">In this workflow, each message is processed as a separate item.</span></span> <span data-ttu-id="10d52-149">Di conseguenza, le opzioni di riepilogo ed esportazione a thread non sono disponibili in un set di revisione standard.</span><span class="sxs-lookup"><span data-stu-id="10d52-149">As a result, the threaded summary and export options aren't available in a standard review set.</span></span>

  ![Set di revisione standard](../media/standardrs.PNG)

### <a name="reviewing-conversations-in-a-conversation-review-set"></a><span data-ttu-id="10d52-151">Revisione delle conversazioni in un set di revisione delle conversazioni</span><span class="sxs-lookup"><span data-stu-id="10d52-151">Reviewing conversations in a conversation review set</span></span>

<span data-ttu-id="10d52-152">In un set di revisione delle conversazioni, i singoli messaggi vengono threadati e presentati come conversazioni.</span><span class="sxs-lookup"><span data-stu-id="10d52-152">In a conversation review set, individual messages are threaded together and presented as conversations.</span></span> <span data-ttu-id="10d52-153">In questo modo è possibile esaminare ed esportare conversazioni contestuali.</span><span class="sxs-lookup"><span data-stu-id="10d52-153">This lets you review and export contextual conversations.</span></span> 

  ![Insieme di revisione delle conversazioni](../media/ConversationRSOptions.PNG)

<span data-ttu-id="10d52-155">Le sezioni seguenti descrivono la revisione e l'esportazione di conversazioni in un set di revisione delle conversazioni.</span><span class="sxs-lookup"><span data-stu-id="10d52-155">The following sections describe reviewing and exporting conversations in a conversation review set.</span></span>

#### <a name="reviewing-conversations"></a><span data-ttu-id="10d52-156">Revisione delle conversazioni</span><span class="sxs-lookup"><span data-stu-id="10d52-156">Reviewing conversations</span></span>

<span data-ttu-id="10d52-157">In un set di revisione delle conversazioni, puoi usare le opzioni seguenti per facilitare il processo di revisione.</span><span class="sxs-lookup"><span data-stu-id="10d52-157">In a conversation review set, you can use the following options to facilitate the review process.</span></span>

- <span data-ttu-id="10d52-158">**Raggruppa per conversazione:** Raggruppa i messaggi all'interno della stessa conversazione per aiutare gli utenti a semplificare e accelerare il processo di revisione.</span><span class="sxs-lookup"><span data-stu-id="10d52-158">**Group by conversation:** Groups messages within the same conversation together to help users simplify and expedite their review process.</span></span>

- <span data-ttu-id="10d52-159">**Visualizzazione riepilogo:** Visualizza la conversazione a thread.</span><span class="sxs-lookup"><span data-stu-id="10d52-159">**Summary view:** Displays the threaded conversation.</span></span> <span data-ttu-id="10d52-160">In questa visualizzazione è possibile visualizzare l'intera conversazione e accedere ai metadati per ogni singolo messaggio.</span><span class="sxs-lookup"><span data-stu-id="10d52-160">In this view, you can see the entire conversation and also access the metadata for each individual message.</span></span>  
  
   - <span data-ttu-id="10d52-161">Visualizzare i metadati per i singoli messaggi</span><span class="sxs-lookup"><span data-stu-id="10d52-161">View metadata for individual messages</span></span>
   
   - <span data-ttu-id="10d52-162">Scaricare singoli messaggi</span><span class="sxs-lookup"><span data-stu-id="10d52-162">Download individual messages</span></span>

- <span data-ttu-id="10d52-163">**Visualizzazione testo:** Fornisce il testo estratto per l'intera conversazione.</span><span class="sxs-lookup"><span data-stu-id="10d52-163">**Text view:** Provides the extracted text for the entire conversation.</span></span>

- <span data-ttu-id="10d52-164">**Annotate view:** Consente di aggiungere un markup a una visualizzazione a thread della conversazione.</span><span class="sxs-lookup"><span data-stu-id="10d52-164">**Annotate view:** Lets you markup a threaded view of the conversation.</span></span> <span data-ttu-id="10d52-165">Tutti i messaggi della conversazione condividono lo stesso documento annotato.</span><span class="sxs-lookup"><span data-stu-id="10d52-165">All messages in the conversation share the same annotated document.</span></span>

- <span data-ttu-id="10d52-166">**Tagging:** Quando visualizzi le conversazioni in un set di recensioni, puoi visualizzare e applicare i tag facendo clic sul **pannello Tagging** nel pannello Codifica.</span><span class="sxs-lookup"><span data-stu-id="10d52-166">**Tagging:** When viewing conversations in a review set, you can view and apply tags by clicking **Tagging panel** in the Coding panel.</span></span>

- <span data-ttu-id="10d52-167">**Eseguire di nuovo la conversione della conversazione:** Quando i messaggi vengono aggiunti a un set di revisione delle conversazioni, viene eseguito automaticamente un processo di conversione per creare il riepilogo a thread e annotare le visualizzazioni.</span><span class="sxs-lookup"><span data-stu-id="10d52-167">**Rerun conversation conversion:** When messages are added to a conversation review set, a conversion job is automatically run to create the threaded summary and annotate views.</span></span> <span data-ttu-id="10d52-168">Se il processo di ricostruzione della conversazione ha esito negativo, è possibile rieseguire il processo facendo clic su Azione **> Creare PDF** di conversazione nel set di revisioni.</span><span class="sxs-lookup"><span data-stu-id="10d52-168">If the Conversation Reconstruction job fails, you can rerun this job by clicking **Action > Create conversation PDFs** in the review set.</span></span>

#### <a name="exporting-conversations"></a><span data-ttu-id="10d52-169">Esportazione di conversazioni</span><span class="sxs-lookup"><span data-stu-id="10d52-169">Exporting conversations</span></span>

<span data-ttu-id="10d52-170">In un set di revisione delle conversazioni, puoi impostare le opzioni seguenti per esportare le conversazioni:</span><span class="sxs-lookup"><span data-stu-id="10d52-170">In a conversation review set, you can set the following options to export conversations:</span></span>

![Opzioni di esportazione per le conversazioni](../media/export.png)

<span data-ttu-id="10d52-172">a.</span><span class="sxs-lookup"><span data-stu-id="10d52-172">a.</span></span> <span data-ttu-id="10d52-173">Opzioni metadati</span><span class="sxs-lookup"><span data-stu-id="10d52-173">Metadata options</span></span>

   - <span data-ttu-id="10d52-174">**Carica file:** I metadati sono inclusi per ogni singolo messaggio, messaggio di posta elettronica e documento.</span><span class="sxs-lookup"><span data-stu-id="10d52-174">**Load file:** Metadata is included for each individual message, email, and document.</span></span> <span data-ttu-id="10d52-175">In una conversazione è presente una riga per ogni messaggio.</span><span class="sxs-lookup"><span data-stu-id="10d52-175">There is one row for each message in a conversation.</span></span> 

   - <span data-ttu-id="10d52-176">**Tag:** I tag del processo di revisione sono inclusi nel file di metadati.</span><span class="sxs-lookup"><span data-stu-id="10d52-176">**Tags:** Tags from your review process are included in the metadata file.</span></span> <span data-ttu-id="10d52-177">I messaggi di una conversazione condividono gli stessi tag.</span><span class="sxs-lookup"><span data-stu-id="10d52-177">Messages in a conversation share the same tags.</span></span> 

<span data-ttu-id="10d52-178">b.</span><span class="sxs-lookup"><span data-stu-id="10d52-178">b.</span></span> <span data-ttu-id="10d52-179">Opzioni di conversazione</span><span class="sxs-lookup"><span data-stu-id="10d52-179">Conversation options</span></span>
  
   - <span data-ttu-id="10d52-180">**File di conversazione:** Quando si esportano file di conversazione, la visualizzazione con annotazioni viene convertita in un file PDF e scaricata nella cartella di esportazione.</span><span class="sxs-lookup"><span data-stu-id="10d52-180">**Conversation files:** When you export conversation files, the annotated view is converted to a PDF file and downloaded to the export folder.</span></span> <span data-ttu-id="10d52-181">I messaggi in un file di conversazione puntano alla versione PDF dello stesso file di conversazione.</span><span class="sxs-lookup"><span data-stu-id="10d52-181">Messages in one conversation file point to the PDF version of the same conversation file.</span></span>  
  
   - <span data-ttu-id="10d52-182">**Singoli messaggi di chat:** Quando si esportano singoli messaggi, ogni messaggio univoco nella conversazione viene esportato come elemento autonomo.</span><span class="sxs-lookup"><span data-stu-id="10d52-182">**Individual chat messages:** When you export individual messages, each unique message in the conversation is exported as a standalone item.</span></span> <span data-ttu-id="10d52-183">Il file viene esportato nello stesso formato in cui è stato salvato nella cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="10d52-183">The file is exported in the same format that it was saved as in the mailbox.</span></span> <span data-ttu-id="10d52-184">Per una conversazione specifica, si ricevono più file msg.</span><span class="sxs-lookup"><span data-stu-id="10d52-184">For a specific conversation, you receive multiple .msg files.</span></span>

     >[!NOTE]
     > <span data-ttu-id="10d52-185">Se sono state applicate annotazioni al file di conversazione, queste annotazioni non verranno trasferite ai singoli messaggi.</span><span class="sxs-lookup"><span data-stu-id="10d52-185">If you applied annotations to the conversation file, these annotations won't be transferred to the individual messages.</span></span>

<span data-ttu-id="10d52-186">c.</span><span class="sxs-lookup"><span data-stu-id="10d52-186">c.</span></span> <span data-ttu-id="10d52-187">Altre opzioni</span><span class="sxs-lookup"><span data-stu-id="10d52-187">Other options</span></span>

   - <span data-ttu-id="10d52-188">**Generare file di testo per tutto il contenuto esportato:** Genera un file di testo per ogni conversazione esportata dal set di recensioni.</span><span class="sxs-lookup"><span data-stu-id="10d52-188">**Generate text files for all exported content:** Generates a text file for each conversation exported from the review set.</span></span>

   - <span data-ttu-id="10d52-189">**Sostituisci il contenuto esportato con PDF redatti:** Se i file di conversazione redatti vengono generati durante il processo di revisione, questi file sono disponibili durante l'esportazione.</span><span class="sxs-lookup"><span data-stu-id="10d52-189">**Replace exported content with redacted PDFs:** If redacted conversation files are generated during the review process, then these files are available during export.</span></span> <span data-ttu-id="10d52-190">Puoi decidere se esportare solo i file nativi (non selezionando questa opzione) o sostituire i file nativi con le versioni rievocate dei file nativi (selezionando questa opzione), che vengono esportati come file PDF.</span><span class="sxs-lookup"><span data-stu-id="10d52-190">You can decided whether to export only the native files (by not selecting this option) or to replace the native files with the redacted versions of the native files (by selecting this option), which are exported as PDF files.</span></span>

## <a name="more-information"></a><span data-ttu-id="10d52-191">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="10d52-191">More information</span></span>

<span data-ttu-id="10d52-192">Per ulteriori informazioni su come esaminare i dati dei casi in Advanced eDiscovery, vedere gli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="10d52-192">To learn more about how to review case data in Advanced eDiscovery, see the following articles:</span></span>

- [<span data-ttu-id="10d52-193">Visualizzare i dati del caso</span><span class="sxs-lookup"><span data-stu-id="10d52-193">View case data</span></span>](view-documents-in-review-set.md)

- [<span data-ttu-id="10d52-194">Analizzare i dati del caso</span><span class="sxs-lookup"><span data-stu-id="10d52-194">Analyze case data</span></span>](analyzing-data-in-review-set.md)

- [<span data-ttu-id="10d52-195">Esportare i dati del caso</span><span class="sxs-lookup"><span data-stu-id="10d52-195">Export case data</span></span>](exporting-data-ediscover20.md)
