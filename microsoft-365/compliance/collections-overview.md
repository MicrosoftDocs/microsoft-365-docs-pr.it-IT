---
title: Panoramica delle raccolte in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
ms.reviewer: nickrob
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
description: Utilizzare le raccolte in Advanced eDiscovery per cercare e raccogliere contenuto relativo al caso o all'indagine.
ms.openlocfilehash: e3f383fab31ec39f22bd781fc84644e3eeee57bb
ms.sourcegitcommit: 8f1721de52dbe3a12c11a0fa5ed0ef5972ca8196
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/17/2021
ms.locfileid: "50838938"
---
# <a name="learn-about-collections-in-advanced-ediscovery"></a><span data-ttu-id="0fddd-103">Informazioni sulle raccolte in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="0fddd-103">Learn about collections in Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="0fddd-104">Stiamo implementazione di una nuova esperienza di raccolta in Advanced eDiscovery, descritta in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="0fddd-104">We're rolling out a new collections experience in Advanced eDiscovery, which is described in this article.</span></span> <span data-ttu-id="0fddd-105">Questa implementazione avrà un certo numero di settimane prima che sia disponibile per tutte le organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="0fddd-105">This rollout will take a number of weeks before it's available to all organizations.</span></span> <span data-ttu-id="0fddd-106">Se la nuova esperienza di raccolta non è disponibile nell'organizzazione, è comunque possibile raccogliere il contenuto del caso con lo strumento di ricerca [avanzata di eDiscovery.](create-search-to-collect-data.md)</span><span class="sxs-lookup"><span data-stu-id="0fddd-106">If the new collections experience isn't available in your organization, you can still collect case content with the [Advanced eDiscovery search tool](create-search-to-collect-data.md).</span></span>

<span data-ttu-id="0fddd-107">Quando le organizzazioni devono raccogliere le comunicazioni e i contenuti che possono essere rilevanti per un'indagine o un potenziale contenzioso, devono affrontare una sfida significativa nelle migliori circostanze.</span><span class="sxs-lookup"><span data-stu-id="0fddd-107">When organizations are faced with gathering the communications and content that may be relevant to an investigation or potential litigation, they face a significant challenge under the best of circumstances.</span></span> <span data-ttu-id="0fddd-108">Nell'ambiente di lavoro moderno di oggi, il volume, la varietà e la velocità dei contenuti consentono l'innovazione e il lavoro remoto, espandendo allo stesso tempo i requisiti e il processo di gestione delle raccolte per le indagini di eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="0fddd-108">In today’s modern workplace, the volume, variety, and velocity of content is enabling innovation and remote work, while also expanding the requirements and process for managing collections for eDiscovery investigations.</span></span>

<span data-ttu-id="0fddd-109">Il flusso di lavoro della raccolta pone significative sfide tecniche per l'estrazione di contenuto da posizioni e origini native.</span><span class="sxs-lookup"><span data-stu-id="0fddd-109">The collection workflow poses significant technical challenges around extracting content from native locations and sources.</span></span> <span data-ttu-id="0fddd-110">È anche un punto critico nella valutazione e nella strategia per scenari comuni di controversie o indagini.</span><span class="sxs-lookup"><span data-stu-id="0fddd-110">It's also a critical point in the assessment and strategy for common litigation or investigations scenarios.</span></span> <span data-ttu-id="0fddd-111">Quando le organizzazioni iniziano a valutare un'indagine, le prime domande sono chi è stato coinvolto?</span><span class="sxs-lookup"><span data-stu-id="0fddd-111">As organizations begin to assess an investigation, the first questions asked are who was involved?</span></span> <span data-ttu-id="0fddd-112">Dopo aver identificato chi è stato coinvolto, questi custodi possono essere messi in attesa rapidamente per conservare il contenuto pertinente.</span><span class="sxs-lookup"><span data-stu-id="0fddd-112">After identifying who was involved, these custodians can quickly be placed on hold to preserve relevant content.</span></span> <span data-ttu-id="0fddd-113">La domanda successiva è cosa è avvenuto?</span><span class="sxs-lookup"><span data-stu-id="0fddd-113">The next question is what took place?</span></span> <span data-ttu-id="0fddd-114">Per rispondere a questa seconda domanda fondamentale di qualsiasi indagine, i responsabili devono rivolgersi ai dati.</span><span class="sxs-lookup"><span data-stu-id="0fddd-114">To answer this second fundamental question of any investigation, managers must turn to the data.</span></span> <span data-ttu-id="0fddd-115">Per valutare rapidamente il contenuto più rilevante per la questione di ciò che è avvenuto, i manager iniziano a perfezionare l'obiettivo della domanda per garantire che i risultati della raccolta siano completi senza essere troppo ampi.</span><span class="sxs-lookup"><span data-stu-id="0fddd-115">To quickly assess the most relevant content to the question of what took place, managers start to refine the target of the question to ensure that the collection results are comprehensive without being too broad.</span></span>

<span data-ttu-id="0fddd-116">Le raccolte in Advanced eDiscovery consentono ai responsabili di eDiscovery di individuare rapidamente il contenuto di posta elettronica, documenti e altro contenuto in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0fddd-116">Collections in Advanced eDiscovery help eDiscovery managers quickly scope a search for content across email, documents, and other content in Microsoft 365.</span></span> <span data-ttu-id="0fddd-117">Le raccolte forniscono ai responsabili una stima del contenuto che potrebbe essere rilevante per il caso.</span><span class="sxs-lookup"><span data-stu-id="0fddd-117">Collections provide managers with an estimate of the content that may be relevant to the case.</span></span> <span data-ttu-id="0fddd-118">In questo modo i responsabili possono prendere decisioni rapide e informate sulle dimensioni e l'ambito del contenuto rilevante per un caso.</span><span class="sxs-lookup"><span data-stu-id="0fddd-118">This allows managers to make quick, informed decisions about the size and scope of content relevant to a case.</span></span> <span data-ttu-id="0fddd-119">I responsabili di eDiscovery possono creare una raccolta per cercare origini dati di archiviazione (ad esempio cassette postali e siti di SharePoint) e utilizzando criteri di ricerca specifici (ad esempio parole chiave e intervalli di date) per definire rapidamente l'ambito della raccolta.</span><span class="sxs-lookup"><span data-stu-id="0fddd-119">eDiscovery managers can create a collection to search custodial data sources (such as mailboxes and SharePoint sites) and by using specific search criteria (such as keywords and date ranges) to quickly define the scope of their collection.</span></span>

<span data-ttu-id="0fddd-120">Dopo aver definito la raccolta, i responsabili di eDiscovery possono salvare la raccolta come bozza e ottenere stime, incluse le stime per il volume di dati, le posizioni del contenuto che contengono risultati e il numero di risultati per la condizione di query di ricerca.</span><span class="sxs-lookup"><span data-stu-id="0fddd-120">After the collection is defined, eDiscovery managers can save the collection as a draft and get estimates, including estimates for data volume, the content locations that contain results, and the number of hits for search query condition.</span></span> <span data-ttu-id="0fddd-121">Queste informazioni dettagliate consentono di determinare se la raccolta deve essere rivista per restringere o espandere l'ambito della raccolta prima di passare alla revisione e analizzare le fasi del flusso di lavoro di eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="0fddd-121">These insights can help to inform if the collection should be revised to narrow or expand the scope of the collection before moving on the review and analyze stages in the eDiscovery workflow.</span></span>

<span data-ttu-id="0fddd-122">Quando il responsabile è soddisfatto dell'ambito della raccolta e della quantità stimata di  contenuto che potrebbe rispondere, il responsabile può aggiungere o confermare il contenuto in un set di recensioni.</span><span class="sxs-lookup"><span data-stu-id="0fddd-122">When the manager is satisfied with the scope of the collection and the estimated amount of content that's likely to be responsive, the manager can add or *commit* the content to a review set.</span></span> <span data-ttu-id="0fddd-123">Quando si esegue il commit di una raccolta in un set di revisioni, tale responsabile ha anche le opzioni per includere conversazioni in chat, allegati cloud e versioni di documenti.</span><span class="sxs-lookup"><span data-stu-id="0fddd-123">When committing a collection to a review set, that manager also has the options to include chat conversations, cloud attachments, and document versions.</span></span> <span data-ttu-id="0fddd-124">Il contenuto della raccolta passa anche attraverso un altro livello di elaborazione durante l'inserimento nel set di revisione.</span><span class="sxs-lookup"><span data-stu-id="0fddd-124">The content in the collection also goes through another level of processing during ingestion into the review set.</span></span> <span data-ttu-id="0fddd-125">e la raccolta verrà aggiornata con il riepilogo finale della raccolta.</span><span class="sxs-lookup"><span data-stu-id="0fddd-125">and the collection will be updated with the final collection summary.</span></span> <span data-ttu-id="0fddd-126">Dopo l'aggiunta del contenuto al set di revisione, i responsabili di eDiscovery possono continuare a eseguire query, raggruppare e perfezionare il contenuto per facilitare la minimizzazione e la revisione.</span><span class="sxs-lookup"><span data-stu-id="0fddd-126">After content is added to the review set, eDiscovery managers can continue to query, group, and refine the content in to help with minimization and review.</span></span> <span data-ttu-id="0fddd-127">Inoltre, la raccolta viene aggiornata con informazioni e statistiche sul contenuto di cui è stato eseguito il commit nel set di revisioni.</span><span class="sxs-lookup"><span data-stu-id="0fddd-127">Additionally, the collection is updated with information and statistics about the content committed to the review set.</span></span> <span data-ttu-id="0fddd-128">In questo modo viene fornito un riferimento cronologico sul contenuto dell'insieme.</span><span class="sxs-lookup"><span data-stu-id="0fddd-128">This provides a historical reference about the content in the collection.</span></span>

<span data-ttu-id="0fddd-129">Con il rilascio delle raccolte in  advanced eDiscovery, la scheda Ricerche è stata rinominata **Raccolte** in un caso advanced eDiscovery nel Centro conformità Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0fddd-129">With the release of collections in an Advanced eDiscovery, the **Searches** tab has been renamed to **Collections** in an Advanced eDiscovery case in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="0fddd-130">I passaggi per definire l'ambito e le dimensioni della raccolta seguono lo stesso processo della ricerca per definire posizioni e condizioni.</span><span class="sxs-lookup"><span data-stu-id="0fddd-130">The steps to define the scope and size of the collection follow the same process as search to define locations and conditions.</span></span> <span data-ttu-id="0fddd-131">Salva come bozza e ottieni stime di anteprima consente di convalidare rapidamente l'ambito di destinazione delle raccolte prima di eseguire una ricerca e una raccolta complete nel set di revisione.</span><span class="sxs-lookup"><span data-stu-id="0fddd-131">Save as draft and get preview estimates enables quick validation of targeted scope of collections prior to committing a full search and collection into the review set.</span></span> <span data-ttu-id="0fddd-132">In questo modo è possibile migliorare la gestione dei processi e le iterazioni mirate per iniziare a ridurre al minimo il contenuto durante il processo di ricerca e raccolta.</span><span class="sxs-lookup"><span data-stu-id="0fddd-132">This enables improved job management, and targeted iterations for starting to minimize content during the search and collection process.</span></span>

## <a name="collections-workflow"></a><span data-ttu-id="0fddd-133">Flusso di lavoro raccolte</span><span class="sxs-lookup"><span data-stu-id="0fddd-133">Collections workflow</span></span>

<span data-ttu-id="0fddd-134">Per iniziare a usare le raccolte in Advanced eDiscovery, ecco un flusso di lavoro di base e le descrizioni di ogni passaggio del processo.</span><span class="sxs-lookup"><span data-stu-id="0fddd-134">To get started using collections in Advanced eDiscovery, here's a basic workflow and descriptions of each step in the process.</span></span>

![Flusso di lavoro delle raccolte in Advanced eDiscovery](../media/CollectionsWorkflow.png)

1. <span data-ttu-id="0fddd-136">**Creare ed eseguire una bozza di raccolta**.</span><span class="sxs-lookup"><span data-stu-id="0fddd-136">**Create and run a draft collection**.</span></span> <span data-ttu-id="0fddd-137">Il primo passaggio consiste nel creare una bozza di raccolta e definire le origini dati di custodia e non di custodia in cui eseguire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="0fddd-137">The first step is to create a draft collection and define the custodial and non-custodial data sources to search.</span></span> <span data-ttu-id="0fddd-138">È inoltre possibile eseguire ricerche in altre origini dati che non sono state aggiunte al caso.</span><span class="sxs-lookup"><span data-stu-id="0fddd-138">You can also search other data sources that haven't been added to the case.</span></span> <span data-ttu-id="0fddd-139">Dopo aver aggiunto le origini dati, configurare la query di ricerca per cercare nelle origini dati il contenuto rilevante per il caso.</span><span class="sxs-lookup"><span data-stu-id="0fddd-139">After you add the data sources, you configure the search query to search the data sources for content relevant to the case.</span></span> <span data-ttu-id="0fddd-140">È possibile utilizzare parole chiave, proprietà e condizioni per creare query di ricerca che restituiscono contenuto probabilmente più rilevante per il caso.</span><span class="sxs-lookup"><span data-stu-id="0fddd-140">You can keywords, properties, and conditions to build search queries that return content that's likely most relevant to the case.</span></span> <span data-ttu-id="0fddd-141">Per ulteriori informazioni, vedere [Create a draft collection.](create-draft-collection.md)</span><span class="sxs-lookup"><span data-stu-id="0fddd-141">For more information, see [Create a draft collection](create-draft-collection.md).</span></span>

2. <span data-ttu-id="0fddd-142">**Esaminare stime e statistiche**.</span><span class="sxs-lookup"><span data-stu-id="0fddd-142">**Review estimates and statistics**.</span></span> <span data-ttu-id="0fddd-143">Dopo aver creato ed eseguito una raccolta di bozze, il passaggio successivo consiste nel visualizzare le statistiche della raccolta per verificare se viene trovato contenuto pertinente e i percorsi di contenuto con il maggior numero di risultati.</span><span class="sxs-lookup"><span data-stu-id="0fddd-143">After you create a draft collection and run it, the next step is to view collection statistics to help you verify whether relevant content is being found and the content locations with the most hits.</span></span> <span data-ttu-id="0fddd-144">È inoltre possibile visualizzare in anteprima un campione dei risultati della ricerca per determinare ulteriormente se il contenuto rientra nell'ambito dell'indagine.</span><span class="sxs-lookup"><span data-stu-id="0fddd-144">You can also preview a sample of the search results to further help you determine if the content is within scope of your investigation.</span></span> <span data-ttu-id="0fddd-145">Per ulteriori informazioni, vedere [Statistics and reports for draft collections.](collection-statistics-reports.md#statistics-and-reports-for-draft-collections)</span><span class="sxs-lookup"><span data-stu-id="0fddd-145">For more information, see [Statistics and reports for draft collections](collection-statistics-reports.md#statistics-and-reports-for-draft-collections).</span></span>

3. <span data-ttu-id="0fddd-146">**Rivedere ed eseguire di nuovo una bozza di raccolta**.</span><span class="sxs-lookup"><span data-stu-id="0fddd-146">**Revise and rerun a draft collection**.</span></span> <span data-ttu-id="0fddd-147">In base alle stime e alle statistiche restituite dall'insieme, è possibile modificare la raccolta bozza modificando le origini dati in cui viene eseguita la ricerca e la query di ricerca per espandere o restringere la raccolta.</span><span class="sxs-lookup"><span data-stu-id="0fddd-147">Based on the estimates and statistics returned by the collection, you can edit the draft collection by changing the data sources that are searched and the search query to expand or narrow the collection.</span></span> <span data-ttu-id="0fddd-148">Puoi aggiornare ed eseguire di nuovo la raccolta bozze finché non sei sicuro che la raccolta contenga il contenuto più rilevante per il tuo caso.</span><span class="sxs-lookup"><span data-stu-id="0fddd-148">You can update and rerun the draft collection until you're confident that collection contains the content that's most relevant to your case.</span></span>

4. <span data-ttu-id="0fddd-149">**Eseguire il commit di una bozza di raccolta in un insieme di revisione.**</span><span class="sxs-lookup"><span data-stu-id="0fddd-149">**Commit a draft collection to a review set**.</span></span> <span data-ttu-id="0fddd-150">Quando si è soddisfatti che la raccolta restituisca il contenuto del tipo rilevante per il caso, è possibile eseguire il commit della raccolta nel set di revisione.</span><span class="sxs-lookup"><span data-stu-id="0fddd-150">When you're satisfied that the collection returns the type content that is relevant to the case, you can commit the collection to the review set.</span></span> <span data-ttu-id="0fddd-151">Quando si esegue il commit di una raccolta, è possibile aggiungere thread di conversazione, allegati cloud e versioni di documenti al set di revisione, tutti elementi che potrebbero essere rilevanti per il caso.</span><span class="sxs-lookup"><span data-stu-id="0fddd-151">When you commit a collection, you have the option to add conversation threads, cloud attachments, and document versions to the review set, all of which might be relevant to the case.</span></span> <span data-ttu-id="0fddd-152">Quando si esegue il commit di una raccolta, si verificano le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0fddd-152">The following things happen when you commit a collection:</span></span>

   - <span data-ttu-id="0fddd-153">Gli elementi figlio ( ad esempio allegati di posta elettronica, firme di posta elettronica e immagini) vengono estratti da un elemento padre (ad esempio un messaggio di posta elettronica, un messaggio di chat o un documento), indicizzati (in un processo denominato *indicizzazione* completa) e aggiunti al set di revisioni come file separati.</span><span class="sxs-lookup"><span data-stu-id="0fddd-153">Child items (such as email attachments, email signatures, and images) are extracted from a parent item (such as an email message, chat message, or document), indexed (in a process called *deep indexing*), and added to the review set as separate files.</span></span>

   - <span data-ttu-id="0fddd-154">L'indicizzazione approfondita viene eseguita sugli elementi raccolti da origini dati aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="0fddd-154">Deep indexing is performed on items collected from additional data sources.</span></span> <span data-ttu-id="0fddd-155">Questi tipi di origini dati sono percorsi di contenuto diversi da quelli di custodia e non di custodia aggiunti in precedenza al caso.</span><span class="sxs-lookup"><span data-stu-id="0fddd-155">These types of data sources are content locations other than the custodial and non-custodial data sources previously added to the case.</span></span>

   <span data-ttu-id="0fddd-156">Per ulteriori informazioni, vedere [Commit a draft collection to a review set](commit-draft-collection.md).</span><span class="sxs-lookup"><span data-stu-id="0fddd-156">For more information, see [Commit a draft collection to a review set](commit-draft-collection.md).</span></span>

5. <span data-ttu-id="0fddd-157">**Esaminare il riepilogo e le statistiche della raccolta.**</span><span class="sxs-lookup"><span data-stu-id="0fddd-157">**Review collection summary and statistics**.</span></span> <span data-ttu-id="0fddd-158">Dopo aver eseguito il commit di una raccolta in un set di revisione, vengono mantenute le informazioni sulla raccolta, ad esempio le statistiche sugli elementi estratti, l'indicizzazione completa, la query di ricerca utilizzata per la raccolta e i percorsi di contenuto da cui sono stati raccolti gli elementi.</span><span class="sxs-lookup"><span data-stu-id="0fddd-158">After you commit a collection to a review set, information about the collection is retained, such as statistics about extracted items, deep indexing, the search query used for the collection, and the content locations that items were collected from.</span></span> <span data-ttu-id="0fddd-159">Inoltre, le raccolte di cui è stato eseguito il commit non possono essere modificate o rieseguite.</span><span class="sxs-lookup"><span data-stu-id="0fddd-159">Also, committed collections can't be edited or rerun.</span></span> <span data-ttu-id="0fddd-160">È possibile copiarli o eliminarli.</span><span class="sxs-lookup"><span data-stu-id="0fddd-160">You can only copy or delete them.</span></span> <span data-ttu-id="0fddd-161">La conservazione delle raccolte fornisce un record cronologico degli elementi raccolti che sono stati aggiunti a un set di revisione.</span><span class="sxs-lookup"><span data-stu-id="0fddd-161">Preserving collections provides a historical record of the collected items that were added to a review set.</span></span> <span data-ttu-id="0fddd-162">Per ulteriori informazioni, vedere [Statistics and reports for committed collections.](collection-statistics-reports.md#statistics-and-reports-for-committed-collections)</span><span class="sxs-lookup"><span data-stu-id="0fddd-162">For more information, see [Statistics and reports for committed collections](collection-statistics-reports.md#statistics-and-reports-for-committed-collections).</span></span>