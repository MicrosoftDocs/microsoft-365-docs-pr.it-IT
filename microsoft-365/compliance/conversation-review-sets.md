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
description: Informazioni su come usare la funzionalità di ricostruzione delle conversazioni in Advanced eDiscovery per ricostruire, rivedere ed esportare conversazioni in thread.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: bf5c39f567240b58546dbeb353e3e461e9b69e48
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358344"
---
# <a name="review-conversations-in-advanced-ediscovery"></a><span data-ttu-id="64f18-103">Esaminare le conversazioni in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="64f18-103">Review conversations in Advanced eDiscovery</span></span> 

<span data-ttu-id="64f18-104">La messaggistica istantanea è un modo pratico per porre domande, condividere idee o comunicare rapidamente tra grandi gruppi di destinatari.</span><span class="sxs-lookup"><span data-stu-id="64f18-104">Instant messaging is a convenient way to ask questions, share ideas, or quickly communicate across large audiences.</span></span> <span data-ttu-id="64f18-105">Poiché le piattaforme di messaggistica istantanea, come Microsoft Teams, diventano fondamentali per la collaborazione aziendale, le organizzazioni devono valutare il modo in cui il flusso di lavoro di eDiscovery affronta queste nuove forme di comunicazione e collaborazione.</span><span class="sxs-lookup"><span data-stu-id="64f18-105">As instant messaging platforms, like Microsoft Teams, become core to enterprise collaboration, organizations must evaluate how their eDiscovery workflow addresses these new forms of communication and collaboration.</span></span> 

<span data-ttu-id="64f18-106">La funzionalità di ricostruzione delle conversazioni in Advanced eDiscovery è progettata per facilitare l'identificazione del contenuto contestuale e la produzione di visualizzazioni di conversazione distinte.</span><span class="sxs-lookup"><span data-stu-id="64f18-106">The Conversation Reconstruction feature in Advanced eDiscovery is designed to help you identify contextual content and produce distinct conversation views.</span></span> <span data-ttu-id="64f18-107">Questa funzionalità consente di esaminare in modo efficiente e rapido conversazioni complete di messaggistica istantanea (denominate anche conversazioni in *thread)* generate in piattaforme come Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="64f18-107">This capability allows you to efficiently and rapidly review complete instant message conversations (also called *threaded conversations*) that are generated in platforms like Microsoft Teams.</span></span>

<span data-ttu-id="64f18-108">Con la ricostruzione delle conversazioni, puoi usare le funzionalità integrate per ricostruire, rivedere ed esportare conversazioni in thread.</span><span class="sxs-lookup"><span data-stu-id="64f18-108">With Conversation Reconstruction, you can use built-in capabilities to reconstruct, review, and export threaded conversations.</span></span> <span data-ttu-id="64f18-109">Utilizzare advanced eDiscovery Conversation Reconstruction per:</span><span class="sxs-lookup"><span data-stu-id="64f18-109">Use Advanced eDiscovery Conversation Reconstruction to:</span></span>

- <span data-ttu-id="64f18-110">Conservare metadati univoci a livello di messaggio in tutti i messaggi all'interno di una conversazione.</span><span class="sxs-lookup"><span data-stu-id="64f18-110">Preserve unique message-level metadata across all messages within a conversation.</span></span>

- <span data-ttu-id="64f18-111">Raccogliere i messaggi contestuali relativi ai risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="64f18-111">Collect contextual messages around your search results.</span></span>

- <span data-ttu-id="64f18-112">Rivedere, annotare e redigere conversazioni in thread.</span><span class="sxs-lookup"><span data-stu-id="64f18-112">Review, annotate, and redact threaded conversations.</span></span>

- <span data-ttu-id="64f18-113">Esportare singoli messaggi o conversazioni in thread</span><span class="sxs-lookup"><span data-stu-id="64f18-113">Export individual messages or threaded conversations</span></span>

## <a name="terminology"></a><span data-ttu-id="64f18-114">Terminologia</span><span class="sxs-lookup"><span data-stu-id="64f18-114">Terminology</span></span>

<span data-ttu-id="64f18-115">Ecco alcune definizioni utili per iniziare a usare la ricostruzione delle conversazioni.</span><span class="sxs-lookup"><span data-stu-id="64f18-115">Here are few definitions to help you get start using Conversation Reconstruction.</span></span>

- <span data-ttu-id="64f18-116">**Messaggi:** Rappresenta l'unità più piccola di una conversazione.</span><span class="sxs-lookup"><span data-stu-id="64f18-116">**Messages:** Represent the smallest unit of a conversation.</span></span> <span data-ttu-id="64f18-117">I messaggi possono variare in base alle dimensioni, alla struttura e ai metadati.</span><span class="sxs-lookup"><span data-stu-id="64f18-117">Messages may vary in size, structure, and metadata.</span></span> 

- <span data-ttu-id="64f18-118">**Conversazione:** Rappresenta un raggruppamento di uno o più messaggi.</span><span class="sxs-lookup"><span data-stu-id="64f18-118">**Conversation:** Represents a grouping of one or more messages.</span></span> <span data-ttu-id="64f18-119">Nelle diverse applicazioni, le conversazioni possono essere rappresentate in modi diversi.</span><span class="sxs-lookup"><span data-stu-id="64f18-119">Across different applications, conversations may be represented in different ways.</span></span> <span data-ttu-id="64f18-120">In alcune applicazioni esiste un'azione esplicita che deriva dalla risposta a un messaggio esistente.</span><span class="sxs-lookup"><span data-stu-id="64f18-120">In some applications, there is an explicit action that results from replying to an existing message.</span></span> <span data-ttu-id="64f18-121">Le conversazioni vengono formate in modo esplicito come risultato di questa azione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="64f18-121">Conversations are formed explicitly as a result of this user action.</span></span> <span data-ttu-id="64f18-122">Ad esempio, ecco uno screenshot di una conversazione di canale in Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="64f18-122">For example, here is a screenshot of a channel conversation in Microsoft Teams.</span></span>

   ![Conversazione del canale di Microsoft Teams](../media/threadedchat.png)

   <span data-ttu-id="64f18-124">In altre app (ad esempio i messaggi di chat 1xN in Teams), non esiste una catena di risposte formale e i messaggi vengono invece visualizzati come un "flat river di messaggi" all'interno di un singolo thread.</span><span class="sxs-lookup"><span data-stu-id="64f18-124">In other apps (such as 1xN chat messages in Teams), there is not a formal reply chain and instead messages appear as a "flat river of messages" within a single thread.</span></span> <span data-ttu-id="64f18-125">In questi tipi di app, le conversazioni vengono dedote da un gruppo di messaggi che si verificano entro un determinato periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="64f18-125">In these types apps, conversations are inferred from a group of messages that occur within a certain time.</span></span> <span data-ttu-id="64f18-126">Questo "raggruppamento soft" di messaggi (anziché una catena di risposte) rappresenta la conversazione "avanti e indietro" su un argomento specifico di interesse.</span><span class="sxs-lookup"><span data-stu-id="64f18-126">This "soft-grouping" of messages (as opposed to a reply chain) represent the "back and forth" conversation about a specific topic of interest.</span></span> 

## <a name="step-1-run-a-search"></a><span data-ttu-id="64f18-127">Passaggio 1: Eseguire una ricerca</span><span class="sxs-lookup"><span data-stu-id="64f18-127">Step 1: Run a search</span></span>

<span data-ttu-id="64f18-128">Dopo aver identificato i responsabile e i percorsi dei contenuti pertinenti, è possibile creare una ricerca per trovare contenuto potenzialmente pertinente.</span><span class="sxs-lookup"><span data-stu-id="64f18-128">After you have identified relevant custodians and content locations, you can create a search to find potentially relevant content.</span></span> <span data-ttu-id="64f18-129">Nella scheda **Ricerche** nel caso di Advanced eDiscovery, è possibile creare una ricerca facendo clic su Nuova ricerca **e** seguendo la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="64f18-129">On the **Searches** tab in the Advanced eDiscovery case, you can create a search by clicking **New search** and following the wizard.</span></span> <span data-ttu-id="64f18-130">Per informazioni su come creare una ricerca, creare una query di ricerca e visualizzare i risultati della ricerca, vedere [Raccogliere dati per un caso.](create-search-to-collect-data.md)</span><span class="sxs-lookup"><span data-stu-id="64f18-130">For information about how you can create a search, build a search query, and view the search results, see [Collect data for a case](create-search-to-collect-data.md).</span></span>

## <a name="step-2-create-a-conversation-review-set"></a><span data-ttu-id="64f18-131">Passaggio 2: Creare un insieme di recensioni di conversazione</span><span class="sxs-lookup"><span data-stu-id="64f18-131">Step 2: Create a conversation review set</span></span>

<span data-ttu-id="64f18-132">In un insieme da rivedere, è possibile cercare, contrassegnare, annotare e redigere documenti, messaggi di posta elettronica e conversazioni in chat.</span><span class="sxs-lookup"><span data-stu-id="64f18-132">In a review set, you can search, tag, annotate, and redact documents, email messages, and chat conversations.</span></span> <span data-ttu-id="64f18-133">In Advanced eDiscovery, è possibile personalizzare la revisione delle conversazioni, in base a singoli messaggi o conversazioni in thread.</span><span class="sxs-lookup"><span data-stu-id="64f18-133">In Advanced eDiscovery, you can customize your review of conversations, based in individual messages or threaded conversations.</span></span> <span data-ttu-id="64f18-134">Questo è determinato dal tipo di insieme di revisione a cui si aggiungono i risultati della ricerca creata nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="64f18-134">This is determined by the type of review set that you add the results of the search created in Step 1 to.</span></span> <span data-ttu-id="64f18-135">Esistono due diversi tipi di insiemi di recensioni:</span><span class="sxs-lookup"><span data-stu-id="64f18-135">There are two different types of review sets:</span></span> 
  
  - <span data-ttu-id="64f18-136">**Set di revisioni standard:** I messaggi nelle conversazioni vengono elaborati e visualizzati come singoli elementi.</span><span class="sxs-lookup"><span data-stu-id="64f18-136">**Standard review sets:** Messages in conversations are processed and displayed as individual items.</span></span> 
  
  -  <span data-ttu-id="64f18-137">**Insiemi di revisioni di conversazione:** I messaggi nelle conversazioni vengono elaborati singolarmente, ma visualizzati in una visualizzazione per conversazione.</span><span class="sxs-lookup"><span data-stu-id="64f18-137">**Conversation review sets:** Messages in conversations are processed individually but displayed in a conversation view.</span></span> <span data-ttu-id="64f18-138">In un insieme di revisioni di conversazione, è possibile annotare, contrassegnare e redigere i messaggi in una visualizzazione conversazione in thread.</span><span class="sxs-lookup"><span data-stu-id="64f18-138">In a conversation review set, you can annotate, tag, and redact messages in a threaded conversation view.</span></span> 

<span data-ttu-id="64f18-139">Per ulteriori informazioni su come esaminare e gestire il contenuto in un insieme da rivedere, vedere [Gestire i set di recensioni.](managing-review-sets.md)</span><span class="sxs-lookup"><span data-stu-id="64f18-139">For more information about how to review and manage content in a review set, see [Manage review sets](managing-review-sets.md).</span></span> 

## <a name="step-3-enable-conversation-retrieval-options"></a><span data-ttu-id="64f18-140">Passaggio 3: abilitare le opzioni di recupero delle conversazioni</span><span class="sxs-lookup"><span data-stu-id="64f18-140">Step 3: Enable conversation retrieval options</span></span>

<span data-ttu-id="64f18-141">Dopo aver esaminato e finalizzato la query di ricerca, è possibile aggiungere i risultati della ricerca a un insieme da rivedere.</span><span class="sxs-lookup"><span data-stu-id="64f18-141">After you have reviewed and finalized your search query, you can add the search results to a review set.</span></span> <span data-ttu-id="64f18-142">Quando si aggiungono i risultati della ricerca in un insieme da rivedere, i dati originali vengono copiati in un'area di archiviazione di Azure per facilitare il processo di revisione e analisi.</span><span class="sxs-lookup"><span data-stu-id="64f18-142">When you add your search results into a review set, the original data is copied to an Azure Storage area to facilitate the review and analysis process.</span></span> <span data-ttu-id="64f18-143">Per ulteriori informazioni sull'aggiunta di risultati di ricerca a un insieme da rivedere, vedere [Aggiungere risultati di ricerca a un insieme da rivedere.](add-data-to-review-set.md)</span><span class="sxs-lookup"><span data-stu-id="64f18-143">For more information about adding search results to a review set, see [Add search results to a review set](add-data-to-review-set.md).</span></span> 

<span data-ttu-id="64f18-144">Quando si aggiungono dati dalle conversazioni a un insieme da rivedere, è possibile utilizzare le opzioni di recupero delle conversazioni per espandere la ricerca e includere messaggi contestuali.</span><span class="sxs-lookup"><span data-stu-id="64f18-144">When you add data from conversations to a review set, you can use the conversation retrieval options to expand your search and include contextual messages.</span></span> <span data-ttu-id="64f18-145">Dopo aver impostato le opzioni di recupero delle conversazioni, possono verificarsi le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="64f18-145">After you set the conversation retrieval options, the following things can happen:</span></span>

  ![Recupero conversazioni](../media/messagesandconversations.png)
  
1. <span data-ttu-id="64f18-147">Utilizzando una query con parole chiave e intervalli di date, la ricerca ha restituito un risultato *nel messaggio 3.*</span><span class="sxs-lookup"><span data-stu-id="64f18-147">Using a keyword and date range query, the search returned a hit on *Message 3*.</span></span> <span data-ttu-id="64f18-148">Questo messaggio fa parte di una conversazione più ampia, illustrata da *CRC1.*</span><span class="sxs-lookup"><span data-stu-id="64f18-148">This message was part of a larger conversation, illustrated by *CRC1*.</span></span> 
  
2. <span data-ttu-id="64f18-149">Quando si aggiungono i dati in un insieme da rivedere e si abilitano le opzioni di recupero della conversazione, Advanced eDiscovery tornerà indietro e raccoglierà altri elementi in *CRC1.*</span><span class="sxs-lookup"><span data-stu-id="64f18-149">When you add the data into a review set and enable the conversation retrieval options, Advanced eDiscovery will go back and collect other items in *CRC1*.</span></span> 
  
3. <span data-ttu-id="64f18-150">Dopo aver aggiunto gli elementi all'insieme da rivedere, è possibile esaminare tutti i singoli messaggi provenienti da *CRC1.*</span><span class="sxs-lookup"><span data-stu-id="64f18-150">After the items have been added to the review set, you can review all the individual messages from *CRC1*.</span></span> 

<span data-ttu-id="64f18-151">Per abilitare il recupero delle conversazioni:</span><span class="sxs-lookup"><span data-stu-id="64f18-151">To enable conversation retrieval:</span></span>
  
1. <span data-ttu-id="64f18-152">Nella scheda **Ricerche** nel caso di Advanced eDiscovery, selezionare una ricerca e quindi fare clic su Aggiungi per rivedere **il set** nella pagina a comparsa.</span><span class="sxs-lookup"><span data-stu-id="64f18-152">On the **Searches** tab in the Advanced eDiscovery case, select a search, and then click **Add to review set** on the flyout page.</span></span>
  
2. <span data-ttu-id="64f18-153">Selezionare un insieme di recensioni esistente o crearne uno.</span><span class="sxs-lookup"><span data-stu-id="64f18-153">Select an existing review set or create a review set.</span></span> <span data-ttu-id="64f18-154">È possibile configurare le opzioni di recupero quando si aggiungono risultati di ricerca a un insieme standard o a una revisione di conversazione.</span><span class="sxs-lookup"><span data-stu-id="64f18-154">You can configure retrieval options when adding search results to a standard or a conversation review set.</span></span>
  
3. <span data-ttu-id="64f18-155">In **Opzioni raccolta** configurare le opzioni di recupero delle conversazioni per le origini  di contenuto che si desidera espandere nella ricerca e quindi fare clic su Aggiungi per avviare il processo.</span><span class="sxs-lookup"><span data-stu-id="64f18-155">Under **Collection options**, configure the conversation retrieval options for the content sources that you want to expand in your search, and then click **Add** to start the process.</span></span>  
  
4. <span data-ttu-id="64f18-156">Al termine **del processo di impostazione Aggiungi** a revisione nella **scheda** Processi, è possibile iniziare a esaminare le conversazioni.</span><span class="sxs-lookup"><span data-stu-id="64f18-156">After the **Add to review set** job on the **Jobs** tab has finished, you can start reviewing the conversations.</span></span>

## <a name="step-4-review-and-export-conversations-in-a-review-set"></a><span data-ttu-id="64f18-157">Passaggio 4: Rivedere ed esportare conversazioni in un insieme da rivedere</span><span class="sxs-lookup"><span data-stu-id="64f18-157">Step 4: Review and export conversations in a review set</span></span>

<span data-ttu-id="64f18-158">Dopo che il contenuto è stato elaborato e aggiunto al set di recensioni, puoi iniziare a esaminare i dati nel set di recensioni.</span><span class="sxs-lookup"><span data-stu-id="64f18-158">After the content has been processed and added to the review set, you can start reviewing the data in the review set.</span></span> <span data-ttu-id="64f18-159">Le funzionalità di revisione sono diverse a seconda che il contenuto sia stato aggiunto a un insieme di recensioni standard o a un insieme di recensioni di conversazione.</span><span class="sxs-lookup"><span data-stu-id="64f18-159">The review capabilities are different depending on whether the content was added to a standard review set or a conversation review set.</span></span> 

### <a name="reviewing-conversations-in-a-standard-review-set"></a><span data-ttu-id="64f18-160">Revisione delle conversazioni in un insieme di recensioni standard</span><span class="sxs-lookup"><span data-stu-id="64f18-160">Reviewing conversations in a standard review set</span></span>

<span data-ttu-id="64f18-161">In un insieme di revisione standard, i messaggi vengono elaborati e visualizzati come singoli elementi, in modo analogo al modo in cui vengono archiviati in una cartella delle cassette postali.</span><span class="sxs-lookup"><span data-stu-id="64f18-161">In a standard review set, messages are processed and displayed as individual items, similar to how they're stored in a mailbox folder.</span></span> <span data-ttu-id="64f18-162">In questo flusso di lavoro, ogni messaggio viene elaborato come elemento separato.</span><span class="sxs-lookup"><span data-stu-id="64f18-162">In this workflow, each message is processed as a separate item.</span></span> <span data-ttu-id="64f18-163">Di conseguenza, le opzioni di riepilogo ed esportazione in thread non sono disponibili in un insieme di revisione standard.</span><span class="sxs-lookup"><span data-stu-id="64f18-163">As a result, the threaded summary and export options aren't available in a standard review set.</span></span> 

  ![Insieme da rivedere standard](../media/standardrs.PNG)

### <a name="reviewing-conversations-in-a-conversation-review-set"></a><span data-ttu-id="64f18-165">Revisione delle conversazioni in un insieme di revisioni di conversazione</span><span class="sxs-lookup"><span data-stu-id="64f18-165">Reviewing conversations in a conversation review set</span></span>

<span data-ttu-id="64f18-166">In un insieme di revisioni di conversazione, i singoli messaggi vengono uniti e presentati come conversazioni.</span><span class="sxs-lookup"><span data-stu-id="64f18-166">In a conversation review set, individual messages are threaded together and presented as conversations.</span></span> <span data-ttu-id="64f18-167">In questo modo è possibile esaminare ed esportare conversazioni contestuali.</span><span class="sxs-lookup"><span data-stu-id="64f18-167">This lets you review and export contextual conversations.</span></span> 

  ![Insieme per la revisione delle conversazioni](../media/ConversationRSOptions.PNG)

<span data-ttu-id="64f18-169">Le sezioni seguenti descrivono la revisione e l'esportazione delle conversazioni in un insieme di revisioni di conversazione.</span><span class="sxs-lookup"><span data-stu-id="64f18-169">The following sections describe reviewing and exporting conversations in a conversation review set.</span></span>

#### <a name="reviewing-conversations"></a><span data-ttu-id="64f18-170">Revisione delle conversazioni</span><span class="sxs-lookup"><span data-stu-id="64f18-170">Reviewing conversations</span></span>

<span data-ttu-id="64f18-171">In un insieme di revisioni di conversazione, è possibile utilizzare le opzioni seguenti per facilitare il processo di revisione.</span><span class="sxs-lookup"><span data-stu-id="64f18-171">In a conversation review set, you can use the following options to facilitate the review process.</span></span>

- <span data-ttu-id="64f18-172">**Raggruppamento per conversazione:** Raggruppa i messaggi all'interno della stessa conversazione per aiutare gli utenti a semplificare e accelerare il processo di revisione.</span><span class="sxs-lookup"><span data-stu-id="64f18-172">**Group by conversation:** Groups messages within the same conversation together to help users simplify and expedite their review process.</span></span> 

- <span data-ttu-id="64f18-173">**Visualizzazione riepilogo:** Visualizza la conversazione in thread.</span><span class="sxs-lookup"><span data-stu-id="64f18-173">**Summary view:** Displays the threaded conversation.</span></span> <span data-ttu-id="64f18-174">In questa visualizzazione è possibile visualizzare l'intera conversazione e accedere ai metadati per ogni singolo messaggio.</span><span class="sxs-lookup"><span data-stu-id="64f18-174">In this view, you can see the entire conversation and also access the metadata for each individual message.</span></span>  
  
   - <span data-ttu-id="64f18-175">Visualizzare i metadati per i singoli messaggi</span><span class="sxs-lookup"><span data-stu-id="64f18-175">View metadata for individual messages</span></span>
   
   - <span data-ttu-id="64f18-176">Scaricare singoli messaggi</span><span class="sxs-lookup"><span data-stu-id="64f18-176">Download individual messages</span></span>

- <span data-ttu-id="64f18-177">**Visualizzazione testo:** Fornisce il testo estratto per l'intera conversazione.</span><span class="sxs-lookup"><span data-stu-id="64f18-177">**Text view:** Provides the extracted text for the entire conversation.</span></span> 

- <span data-ttu-id="64f18-178">**Annotate view:** Consente di aggiungere commenti a una visualizzazione in thread della conversazione.</span><span class="sxs-lookup"><span data-stu-id="64f18-178">**Annotate view:** Lets you markup a threaded view of the conversation.</span></span> <span data-ttu-id="64f18-179">Tutti i messaggi della conversazione condividono lo stesso documento annotato.</span><span class="sxs-lookup"><span data-stu-id="64f18-179">All messages in the conversation share the same annotated document.</span></span>

- <span data-ttu-id="64f18-180">**Tagging:** Quando si visualizzano le conversazioni in un insieme da rivedere, è possibile visualizzare e applicare i tag facendo clic sul **pannello Tagging** nel pannello Codifica.</span><span class="sxs-lookup"><span data-stu-id="64f18-180">**Tagging:** When viewing conversations in a review set, you can view and apply tags by clicking **Tagging panel** in the Coding panel.</span></span>

- <span data-ttu-id="64f18-181">**Eseguire di nuovo la conversione della conversazione:** Quando i messaggi vengono aggiunti a un insieme di revisione delle conversazioni, viene eseguito automaticamente un processo di conversione per creare il riepilogo in thread e annotare le visualizzazioni.</span><span class="sxs-lookup"><span data-stu-id="64f18-181">**Rerun conversation conversion:** When messages are added to a conversation review set, a conversion job is automatically run to create the threaded summary and annotate views.</span></span> <span data-ttu-id="64f18-182">Se il processo di ricostruzione della conversazione ha esito negativo, è possibile rieseguire il processo facendo clic su **Azione > Crea PDF** conversazione nel set da rivedere.</span><span class="sxs-lookup"><span data-stu-id="64f18-182">If the Conversation Reconstruction job fails, you can rerun this job by clicking **Action > Create conversation PDFs** in the review set.</span></span>

#### <a name="exporting-conversations"></a><span data-ttu-id="64f18-183">Esportazione di conversazioni</span><span class="sxs-lookup"><span data-stu-id="64f18-183">Exporting conversations</span></span>

<span data-ttu-id="64f18-184">In un insieme di revisione delle conversazioni, è possibile impostare le opzioni seguenti per esportare le conversazioni:</span><span class="sxs-lookup"><span data-stu-id="64f18-184">In a conversation review set, you can set the following options to export conversations:</span></span>

![Opzioni di esportazione per le conversazioni](../media/export.png)

<span data-ttu-id="64f18-186">a.</span><span class="sxs-lookup"><span data-stu-id="64f18-186">a.</span></span> <span data-ttu-id="64f18-187">Opzioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="64f18-187">Metadata options</span></span>

   - <span data-ttu-id="64f18-188">**Carica file:** I metadati sono inclusi per ogni singolo messaggio, messaggio di posta elettronica e documento.</span><span class="sxs-lookup"><span data-stu-id="64f18-188">**Load file:** Metadata is included for each individual message, email, and document.</span></span> <span data-ttu-id="64f18-189">In una conversazione è presente una riga per ogni messaggio.</span><span class="sxs-lookup"><span data-stu-id="64f18-189">There is one row for each message in a conversation.</span></span> 

   - <span data-ttu-id="64f18-190">**Tag:** I tag del processo di revisione sono inclusi nel file di metadati.</span><span class="sxs-lookup"><span data-stu-id="64f18-190">**Tags:** Tags from your review process are included in the metadata file.</span></span> <span data-ttu-id="64f18-191">I messaggi di una conversazione condividono gli stessi tag.</span><span class="sxs-lookup"><span data-stu-id="64f18-191">Messages in a conversation share the same tags.</span></span> 

<span data-ttu-id="64f18-192">b.</span><span class="sxs-lookup"><span data-stu-id="64f18-192">b.</span></span> <span data-ttu-id="64f18-193">Opzioni di conversazione</span><span class="sxs-lookup"><span data-stu-id="64f18-193">Conversation options</span></span>
  
   - <span data-ttu-id="64f18-194">**File di conversazione:** Quando si esportano i file di conversazione, la visualizzazione con annotazioni viene convertita in un file PDF e scaricata nella cartella di esportazione.</span><span class="sxs-lookup"><span data-stu-id="64f18-194">**Conversation files:** When you export conversation files, the annotated view is converted to a PDF file and downloaded to the export folder.</span></span> <span data-ttu-id="64f18-195">I messaggi in un file di conversazione puntano alla versione PDF dello stesso file di conversazione.</span><span class="sxs-lookup"><span data-stu-id="64f18-195">Messages in one conversation file point to the PDF version of the same conversation file.</span></span>  
  
   - <span data-ttu-id="64f18-196">**Singoli messaggi di chat:** Quando si esportano singoli messaggi, ogni messaggio univoco nella conversazione viene esportato come elemento autonomo.</span><span class="sxs-lookup"><span data-stu-id="64f18-196">**Individual chat messages:** When you export individual messages, each unique message in the conversation is exported as a standalone item.</span></span> <span data-ttu-id="64f18-197">Il file viene esportato nello stesso formato in cui è stato salvato nella cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="64f18-197">The file is exported in the same format that it was saved as in the mailbox.</span></span> <span data-ttu-id="64f18-198">Per una conversazione specifica, si ricevono più file con estensione msg.</span><span class="sxs-lookup"><span data-stu-id="64f18-198">For a specific conversation, you receive multiple .msg files.</span></span> 

     >[!NOTE]
     > <span data-ttu-id="64f18-199">Se sono state applicate annotazioni al file di conversazione, queste annotazioni non verranno trasferite ai singoli messaggi.</span><span class="sxs-lookup"><span data-stu-id="64f18-199">If you applied annotations to the conversation file, these annotations won't be transferred to the individual messages.</span></span> 

<span data-ttu-id="64f18-200">c.</span><span class="sxs-lookup"><span data-stu-id="64f18-200">c.</span></span> <span data-ttu-id="64f18-201">Altre opzioni</span><span class="sxs-lookup"><span data-stu-id="64f18-201">Other options</span></span>

   - <span data-ttu-id="64f18-202">**Generare file di testo per tutto il contenuto esportato:** Genera un file di testo per ogni conversazione esportata dal set di recensioni.</span><span class="sxs-lookup"><span data-stu-id="64f18-202">**Generate text files for all exported content:** Generates a text file for each conversation exported from the review set.</span></span> 

   - <span data-ttu-id="64f18-203">**Sostituisci il contenuto esportato con PDF redatti:** Se i file di conversazione redatti vengono generati durante il processo di revisione, questi file sono disponibili durante l'esportazione.</span><span class="sxs-lookup"><span data-stu-id="64f18-203">**Replace exported content with redacted PDFs:** If redacted conversation files are generated during the review process, then these files are available during export.</span></span> <span data-ttu-id="64f18-204">È possibile decidere se esportare solo i file nativi (non selezionando questa opzione) o sostituire i file nativi con le versioni dei file nativi (selezionando questa opzione), che vengono esportati come file PDF.</span><span class="sxs-lookup"><span data-stu-id="64f18-204">You can decided whether to export only the native files (by not selecting this option) or to replace the native files with the redacted versions of the native files (by selecting this option), which are exported as PDF files.</span></span>

## <a name="more-information"></a><span data-ttu-id="64f18-205">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="64f18-205">More information</span></span>

<span data-ttu-id="64f18-206">Per ulteriori informazioni su come esaminare i dati dei casi in Advanced eDiscovery, vedere i seguenti articoli:</span><span class="sxs-lookup"><span data-stu-id="64f18-206">To learn more about how to review case data in Advanced eDiscovery, see the following articles:</span></span>

- [<span data-ttu-id="64f18-207">Visualizzare i dati del caso</span><span class="sxs-lookup"><span data-stu-id="64f18-207">View case data</span></span>](view-documents-in-review-set.md)

- [<span data-ttu-id="64f18-208">Analizzare i dati del caso</span><span class="sxs-lookup"><span data-stu-id="64f18-208">Analyze case data</span></span>](analyzing-data-in-review-set.md)

- [<span data-ttu-id="64f18-209">Esportare i dati del caso</span><span class="sxs-lookup"><span data-stu-id="64f18-209">Export case data</span></span>](exporting-data-ediscover20.md)
