---
title: Contrassegnare i documenti in un insieme da rivedere
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: L'aggiunta di tag ai documenti in un set di revisioni consente di rimuovere il contenuto non necessario e di identificare il contenuto pertinente in Advanced eDiscovery caso.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6d6a933f24a034aced99a8eaa70c6ee951765ca0
ms.sourcegitcommit: cc9e3cac6af23f20d7cc5ac6fc6f6e01bc3cc5c5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2021
ms.locfileid: "52736273"
---
# <a name="tag-documents-in-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="a5633-103">Contrassegnare i documenti in un set di revisioni in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="a5633-103">Tag documents in a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="a5633-104">L'organizzazione del contenuto in un set di revisione è importante per completare vari flussi di lavoro nel processo di eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="a5633-104">Organizing content in a review set is important to complete various workflows in the eDiscovery process.</span></span> <span data-ttu-id="a5633-105">Tra questi vi sono anche:</span><span class="sxs-lookup"><span data-stu-id="a5633-105">This includes:</span></span>

- <span data-ttu-id="a5633-106">Eliminare contenuto non necessario</span><span class="sxs-lookup"><span data-stu-id="a5633-106">Culling unnecessary content</span></span>

- <span data-ttu-id="a5633-107">Identificazione del contenuto pertinente</span><span class="sxs-lookup"><span data-stu-id="a5633-107">Identifying relevant content</span></span>

- <span data-ttu-id="a5633-108">Identificazione del contenuto che deve essere esaminato da un esperto o da un avvocato</span><span class="sxs-lookup"><span data-stu-id="a5633-108">Identifying content that must be reviewed by an expert or attorney</span></span>

<span data-ttu-id="a5633-109">Quando esperti, avvocati o altri utenti esaminano il contenuto in un set di recensioni, le loro opinioni relative al contenuto possono essere acquisite utilizzando tag.</span><span class="sxs-lookup"><span data-stu-id="a5633-109">When experts, attorneys, or other users review content in a review set, their opinions related to the content can be captured by using tags.</span></span> <span data-ttu-id="a5633-110">Ad esempio, se lo scopo è eliminare il contenuto non necessario, un utente può contrassegnare i documenti con un tag, ad esempio "non reattivo".</span><span class="sxs-lookup"><span data-stu-id="a5633-110">For example, if the intent is to cull unnecessary content, a user can tag documents with a tag such as "non-responsive".</span></span> <span data-ttu-id="a5633-111">Dopo aver esaminato e taggato il contenuto, è possibile creare una ricerca nel set di recensioni per escludere qualsiasi contenuto contrassegnato come "non reattivo".</span><span class="sxs-lookup"><span data-stu-id="a5633-111">After content has been reviewed and tagged, a review set search can be created to exclude any content tagged as "non-responsive".</span></span> <span data-ttu-id="a5633-112">Questo processo elimina il contenuto non reattivo dai passaggi successivi del flusso di lavoro di eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="a5633-112">This process eliminates the non-responsive content from the next steps in the eDiscovery workflow.</span></span> <span data-ttu-id="a5633-113">Il riquadro di tagging in un set di revisione può essere personalizzato per ogni caso in modo che i tag supportino il flusso di lavoro di revisione previsto per il caso.</span><span class="sxs-lookup"><span data-stu-id="a5633-113">The tagging panel in a review set can be customized for every case so that the tags support the intended review workflow for the case.</span></span>

> [!NOTE]
> <span data-ttu-id="a5633-114">L'ambito dei tag è un Advanced eDiscovery caso.</span><span class="sxs-lookup"><span data-stu-id="a5633-114">The scope of tags is an Advanced eDiscovery case.</span></span> <span data-ttu-id="a5633-115">Ciò significa che un caso può avere un solo set di tag che i revisori possono usare per contrassegnare i documenti del set di revisione.</span><span class="sxs-lookup"><span data-stu-id="a5633-115">That means a case can only have one set of tags that reviewers can use to tag review set documents.</span></span> <span data-ttu-id="a5633-116">Non è possibile configurare un set diverso di tag da utilizzare in set di revisione diversi nello stesso caso.</span><span class="sxs-lookup"><span data-stu-id="a5633-116">You can't set up a different set of tags for use in different review sets in the same case.</span></span>

## <a name="tag-types"></a><span data-ttu-id="a5633-117">Tipi di tag</span><span class="sxs-lookup"><span data-stu-id="a5633-117">Tag types</span></span>

<span data-ttu-id="a5633-118">Advanced eDiscovery fornisce due tipi di tag:</span><span class="sxs-lookup"><span data-stu-id="a5633-118">Advanced eDiscovery provides two types of tags:</span></span>

- <span data-ttu-id="a5633-119">**Tag a scelta** singola : limita i revisori alla selezione di un singolo tag all'interno di un gruppo.</span><span class="sxs-lookup"><span data-stu-id="a5633-119">**Single choice tags**: Restricts reviewers to selecting a single tag within a group.</span></span> <span data-ttu-id="a5633-120">Questi tipi di tag possono essere utili per garantire che i revisori non selezionano tag in conflitto, ad esempio "reattivi" e "non reattivi".</span><span class="sxs-lookup"><span data-stu-id="a5633-120">These types of tags can be useful to ensure that reviewers don't select conflicting tags such as "responsive" and "non-responsive".</span></span> <span data-ttu-id="a5633-121">I tag a scelta singola vengono visualizzati come pulsanti di opzione.</span><span class="sxs-lookup"><span data-stu-id="a5633-121">Single choice tags appear as radio buttons.</span></span>

- <span data-ttu-id="a5633-122">**Tag a scelta multipla**: consente alle recensioni di selezionare più tag all'interno di un gruppo.</span><span class="sxs-lookup"><span data-stu-id="a5633-122">**Multiple choice tags**: Allow reviews to select multiple tags within a group.</span></span> <span data-ttu-id="a5633-123">Questi tipi di tag vengono visualizzati come caselle di controllo.</span><span class="sxs-lookup"><span data-stu-id="a5633-123">These types of tags appear as checkboxes.</span></span>

## <a name="tag-structure"></a><span data-ttu-id="a5633-124">Struttura tag</span><span class="sxs-lookup"><span data-stu-id="a5633-124">Tag structure</span></span>

<span data-ttu-id="a5633-125">Oltre ai tipi di tag, la struttura dell'organizzazione dei tag nel pannello tag può essere usata per rendere più intuitivo l'applicazione di tag ai documenti.</span><span class="sxs-lookup"><span data-stu-id="a5633-125">In addition to the tag types, the structure of how tags are organized in the tag panel can be used to make tagging documents more intuitive.</span></span> <span data-ttu-id="a5633-126">I tag sono raggruppati per sezioni.</span><span class="sxs-lookup"><span data-stu-id="a5633-126">Tags are grouped by sections.</span></span> <span data-ttu-id="a5633-127">La ricerca dei set di recensioni supporta la possibilità di eseguire ricerche per tag e per sezione tag.</span><span class="sxs-lookup"><span data-stu-id="a5633-127">Review set search supports the ability to search by tag and by tag section.</span></span> <span data-ttu-id="a5633-128">Ciò significa che puoi creare una ricerca di set di recensioni per recuperare i documenti contrassegnati con qualsiasi tag in una sezione.</span><span class="sxs-lookup"><span data-stu-id="a5633-128">This means you can create a review set search to retrieve documents tagged with any tag in a section.</span></span>

![Sezioni di tag nel pannello tag](../media/TagTypes.png)

<span data-ttu-id="a5633-130">Puoi organizzare ulteriormente i tag annidandoli all'interno di una sezione.</span><span class="sxs-lookup"><span data-stu-id="a5633-130">You can further organize tags by nesting them within a section.</span></span> <span data-ttu-id="a5633-131">Ad esempio, se lo scopo è identificare e contrassegnare il contenuto con privilegi, è possibile utilizzare la annidamento per chiarire che un revisore può contrassegnare un documento come "privilegiato" e selezionare il tipo di privilegio controllando il tag annidato appropriato.</span><span class="sxs-lookup"><span data-stu-id="a5633-131">For example, if the intent is to identify and tag privileged content, nesting can be used to make it clear that a reviewer can tag a document as "Privileged" and select the type of privilege by checking the appropriate nested tag.</span></span>

![Tag annidati all'interno di una sezione tag](../media/NestingTags.png)

## <a name="create-tags"></a><span data-ttu-id="a5633-133">Creare tag</span><span class="sxs-lookup"><span data-stu-id="a5633-133">Create tags</span></span>

<span data-ttu-id="a5633-134">Prima di applicare tag ai documenti nel set di revisioni, è necessario creare una struttura di tag.</span><span class="sxs-lookup"><span data-stu-id="a5633-134">Before applying tags to documents in the review set, you need to create a tag structure.</span></span>

1. <span data-ttu-id="a5633-135">Aprire un set di revisioni e passare alla barra dei comandi e selezionare **Tag per query.**</span><span class="sxs-lookup"><span data-stu-id="a5633-135">Open a review set and navigate to the command bar and select **Tag by query**.</span></span>

2. <span data-ttu-id="a5633-136">Nel pannello di tagging seleziona **Gestisci opzioni tag**</span><span class="sxs-lookup"><span data-stu-id="a5633-136">In the tagging panel, select **Manage tag options**</span></span>

3. <span data-ttu-id="a5633-137">Seleziona **Aggiungi sezione tag.**</span><span class="sxs-lookup"><span data-stu-id="a5633-137">Select **Add tag section**.</span></span>

4. <span data-ttu-id="a5633-138">Digitare il titolo di un gruppo di tag e una descrizione facoltativa e quindi fare clic su **Salva.**</span><span class="sxs-lookup"><span data-stu-id="a5633-138">Type a tag group title and an optional description, and then click **Save**.</span></span>

5. <span data-ttu-id="a5633-139">Seleziona il menu a discesa con tre puntini accanto al titolo del gruppo di tag e fai clic **sulla casella di** controllo Aggiungi o sul pulsante di opzione **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="a5633-139">Select the triple dot dropdown menu next to the tag group title and click **Add check box** or **Add option button**.</span></span>

6. <span data-ttu-id="a5633-140">Digitare un nome e una descrizione per la casella di controllo o il pulsante di opzione.</span><span class="sxs-lookup"><span data-stu-id="a5633-140">Type a name and description for the checkbox or option button.</span></span>

7. <span data-ttu-id="a5633-141">Ripeti questo processo per creare nuove sezioni di tag, opzioni di tag e caselle di controllo.</span><span class="sxs-lookup"><span data-stu-id="a5633-141">Repeat this process to create new tag sections, tag options, and checkboxes.</span></span>

   ![Configurare la struttura dei tag](../media/ManageTagOptions3.png)

## <a name="applying-tags"></a><span data-ttu-id="a5633-143">Applicazione di tag</span><span class="sxs-lookup"><span data-stu-id="a5633-143">Applying tags</span></span>

<span data-ttu-id="a5633-144">Con la struttura dei tag impostata, i revisori possono applicare tag ai documenti di un set di revisioni.</span><span class="sxs-lookup"><span data-stu-id="a5633-144">With the tag structure in place, reviewers can apply tags to documents in a review set.</span></span> <span data-ttu-id="a5633-145">Esistono due modi diversi per applicare i tag:</span><span class="sxs-lookup"><span data-stu-id="a5633-145">There are two different ways to apply tags:</span></span>

- <span data-ttu-id="a5633-146">Tag file</span><span class="sxs-lookup"><span data-stu-id="a5633-146">Tag files</span></span>

- <span data-ttu-id="a5633-147">Tag per query</span><span class="sxs-lookup"><span data-stu-id="a5633-147">Tag by query</span></span>

### <a name="tag-files"></a><span data-ttu-id="a5633-148">Tag file</span><span class="sxs-lookup"><span data-stu-id="a5633-148">Tag files</span></span>

<span data-ttu-id="a5633-149">Indipendentemente dal fatto che si selezioni un singolo elemento o più elementi in un set di revisioni, è possibile applicare tag alla selezione facendo clic su **Tag file** nella barra dei comandi.</span><span class="sxs-lookup"><span data-stu-id="a5633-149">Whether you select a single item or several items in a review set, you can apply tags to their selection by clicking **Tag files** in the command bar.</span></span> <span data-ttu-id="a5633-150">Nel pannello di tagging puoi selezionare un tag e applicarlo automaticamente ai documenti selezionati.</span><span class="sxs-lookup"><span data-stu-id="a5633-150">In the tagging panel, you can select a tag and it is automatically applied to the selected documents.</span></span>

![Contrassegnare i file selezionati](../media/TagFile2.png)

> [!NOTE]
> <span data-ttu-id="a5633-152">I tag verranno applicati solo agli elementi selezionati nell'elenco di elementi.</span><span class="sxs-lookup"><span data-stu-id="a5633-152">Tags will be applied only to selected items in the list of items.</span></span>

### <a name="tag-by-query"></a><span data-ttu-id="a5633-153">Tag per query</span><span class="sxs-lookup"><span data-stu-id="a5633-153">Tag by query</span></span>

<span data-ttu-id="a5633-154">L'applicazione di tag tramite query consente di applicare tag a tutti gli elementi visualizzati da una query di filtro attualmente applicata nel set di revisioni.</span><span class="sxs-lookup"><span data-stu-id="a5633-154">Tagging by query lets you apply tags to all items displayed by a filter query that's currently applied in the review set.</span></span>

1. <span data-ttu-id="a5633-155">Deselezionare tutti gli elementi nel set di revisione e passare alla barra dei comandi e selezionare **Contrassegna per query**.</span><span class="sxs-lookup"><span data-stu-id="a5633-155">Unselect all items in the review set and go to the command bar and select **Tag by query**.</span></span>

2. <span data-ttu-id="a5633-156">Nel riquadro di tagging seleziona il tag che vuoi applicare.</span><span class="sxs-lookup"><span data-stu-id="a5633-156">In the tagging panel, select the tag that you want to apply.</span></span>

3. <span data-ttu-id="a5633-157">**Nell'elenco a discesa Selezione tag** sono disponibili tre opzioni che determinano a quali elementi applicare il tag.</span><span class="sxs-lookup"><span data-stu-id="a5633-157">Under the **Tag selection** dropdown, there are three options that dictate which items to apply the tag to.</span></span>

   - <span data-ttu-id="a5633-158">**Elementi che corrispondono a query applicata**: applica tag a elementi specifici che soddisfano le condizioni della query di filtro.</span><span class="sxs-lookup"><span data-stu-id="a5633-158">**Items that match applied query**: Applies tags to specific items that match the filter query conditions.</span></span>

   - <span data-ttu-id="a5633-159">**Includi elementi famiglia associati**: applica tag a elementi specifici che soddisfano le condizioni della query di filtro e gli elementi della famiglia associati.</span><span class="sxs-lookup"><span data-stu-id="a5633-159">**Include associated family items**: Applies tags to specific items that match the filter query conditions and their associated family items.</span></span> <span data-ttu-id="a5633-160">*Gli elementi della* famiglia sono elementi che condividono lo stesso valore di metadati FamilyId.</span><span class="sxs-lookup"><span data-stu-id="a5633-160">*Family items* are items that share the same FamilyId metadata value.</span></span>  

   - <span data-ttu-id="a5633-161">**Includi elementi di conversazione associati**: applica tag agli elementi che soddisfano le condizioni di query del filtro e agli elementi di conversazione associati.</span><span class="sxs-lookup"><span data-stu-id="a5633-161">**Include associated conversation items**: Applies tags to items that match the filter query conditions and their associated conversation items.</span></span> <span data-ttu-id="a5633-162">*Gli elementi di* conversazione sono elementi che condividono gli stessi valori dei metadati ConversationId.</span><span class="sxs-lookup"><span data-stu-id="a5633-162">*Conversation items* are items that share the same ConversationId metadata values.</span></span>

   ![Selezione tag](../media/TagByQuery2.png)

4. <span data-ttu-id="a5633-164">Fare **clic su Avvia processo di tagging** per attivare il processo di tagging.</span><span class="sxs-lookup"><span data-stu-id="a5633-164">Click **Start tagging job** to trigger the tagging job.</span></span>

## <a name="tag-filter"></a><span data-ttu-id="a5633-165">Filtro tag</span><span class="sxs-lookup"><span data-stu-id="a5633-165">Tag filter</span></span>

<span data-ttu-id="a5633-166">Utilizzare il filtro tag nel set di revisione per trovare o escludere rapidamente elementi dai risultati della query in base alla modalità di applicazione di tag a un elemento.</span><span class="sxs-lookup"><span data-stu-id="a5633-166">Use the tag filter in review set to quickly find or exclude items from the query results based on how an item is tagged.</span></span> 

1. <span data-ttu-id="a5633-167">Seleziona **Filtri** per espandere il pannello dei filtri.</span><span class="sxs-lookup"><span data-stu-id="a5633-167">Select **Filters** to expand the filter panel.</span></span>

2. <span data-ttu-id="a5633-168">Selezionare ed espandere **Proprietà elemento**.</span><span class="sxs-lookup"><span data-stu-id="a5633-168">Select and expand **Item properties**.</span></span>

3. <span data-ttu-id="a5633-169">Scorrere verso il basso per trovare il filtro denominato **Tag,** selezionare la casella di controllo e quindi fare clic su **Fine.**</span><span class="sxs-lookup"><span data-stu-id="a5633-169">Scroll down to find the filter named **Tag**, select the checkbox, and then click **Done**.</span></span>

4. <span data-ttu-id="a5633-170">Per includere o escludere elementi con un tag specifico da una query, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a5633-170">To include or exclude items with a specific tag from a query, do one of the following:</span></span>

   - <span data-ttu-id="a5633-171">**Includi elementi:** seleziona il valore del tag e seleziona Uguale a **uno qualsiasi** nel menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="a5633-171">**Include items**: Select the tag value and select **Equal any of** in the dropdown menu.</span></span>

      <span data-ttu-id="a5633-172">Oppure</span><span class="sxs-lookup"><span data-stu-id="a5633-172">Or</span></span>

   - <span data-ttu-id="a5633-173">**Escludi** elementi : seleziona il valore del tag e seleziona Uguale **a nessuno nel** menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="a5633-173">**Exclude items**: Select the tag value and select **Equals none of** in dropdown menu.</span></span>

     ![Elementi di esclusione filtro tag](../media/TagFilterExclude.png)

> [!NOTE]
> <span data-ttu-id="a5633-175">Assicurati di aggiornare la pagina per assicurarti che il filtro tag visualizzi le modifiche più recenti alla struttura dei tag.</span><span class="sxs-lookup"><span data-stu-id="a5633-175">Be sure to refresh the page to ensure that the tag filter displays the latest changes to the tag structure.</span></span>
