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
description: L'aggiunta di tag ai documenti in un insieme da rivedere consente di rimuovere il contenuto non necessario e di identificare il contenuto pertinente in un caso di Advanced eDiscovery.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 83e7a3c9c097968c4d773e6e2092bb3c50154cc3
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285282"
---
# <a name="tag-documents-in-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="e3422-103">Contrassegnare i documenti in una recensione impostata in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="e3422-103">Tag documents in a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="e3422-104">L'organizzazione del contenuto in un insieme da rivedere è importante per completare vari flussi di lavoro nel processo di eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="e3422-104">Organizing content in a review set is important to complete various workflows in the eDiscovery process.</span></span> <span data-ttu-id="e3422-105">Ciò include:</span><span class="sxs-lookup"><span data-stu-id="e3422-105">This includes:</span></span>

- <span data-ttu-id="e3422-106">Eliminare contenuti non necessari</span><span class="sxs-lookup"><span data-stu-id="e3422-106">Culling unnecessary content</span></span>

- <span data-ttu-id="e3422-107">Identificazione del contenuto pertinente</span><span class="sxs-lookup"><span data-stu-id="e3422-107">Identifying relevant content</span></span>
 
- <span data-ttu-id="e3422-108">Identificazione dei contenuti che devono essere esaminati da un esperto o da un avvocato</span><span class="sxs-lookup"><span data-stu-id="e3422-108">Identifying content that must be reviewed by an expert or an attorney</span></span>

<span data-ttu-id="e3422-109">Quando esperti, avvocati o altri utenti esaminano il contenuto in un insieme di recensioni, le loro opinioni relative al contenuto possono essere acquisite tramite tag.</span><span class="sxs-lookup"><span data-stu-id="e3422-109">When experts, attorneys, or other users review content in a review set, their opinions related to the content can be captured by using tags.</span></span> <span data-ttu-id="e3422-110">Ad esempio, se lo scopo è eliminare il contenuto non necessario, un utente può contrassegnare i documenti con un tag, ad esempio "non reattivo".</span><span class="sxs-lookup"><span data-stu-id="e3422-110">For example, if the intent is to cull unnecessary content, a user can tag documents with a tag such as "non-responsive".</span></span> <span data-ttu-id="e3422-111">Dopo che il contenuto è stato esaminato e contrassegnato, è possibile creare una ricerca di insieme da rivedere per escludere qualsiasi contenuto contrassegnato come "non reattivo", eliminando questo contenuto dai passaggi successivi del flusso di lavoro di eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="e3422-111">After content has been reviewed and tagged, a review set search can be created to exclude any content tagged as "non-responsive", which eliminates this content from the next steps in the eDiscovery workflow.</span></span> <span data-ttu-id="e3422-112">Il pannello di tag può essere personalizzato per ogni caso in modo che i tag possano supportare il flusso di lavoro di revisione previsto.</span><span class="sxs-lookup"><span data-stu-id="e3422-112">The tag panel can be customized for every case so that the tags can support the intended review workflow.</span></span>

## <a name="tag-types"></a><span data-ttu-id="e3422-113">Tipi di tag</span><span class="sxs-lookup"><span data-stu-id="e3422-113">Tag types</span></span>

<span data-ttu-id="e3422-114">Advanced eDiscovery offre due tipi di tag:</span><span class="sxs-lookup"><span data-stu-id="e3422-114">Advanced eDiscovery provides two types of tags:</span></span>

- <span data-ttu-id="e3422-115">**Tag a scelta singola:** limita gli utenti a selezionare un singolo tag all'interno di un gruppo.</span><span class="sxs-lookup"><span data-stu-id="e3422-115">**Single choice tags** - Restricts users to select a single tag within a group.</span></span> <span data-ttu-id="e3422-116">Ciò può essere utile per garantire che gli utenti non selezionano tag in conflitto, ad esempio "reattivi" e "non reattivi".</span><span class="sxs-lookup"><span data-stu-id="e3422-116">This can be useful to ensure users don't select conflicting tags such as "responsive" and "non-responsive".</span></span> <span data-ttu-id="e3422-117">Questi elementi verranno visualizzati come pulsanti di opzione.</span><span class="sxs-lookup"><span data-stu-id="e3422-117">These will appear as radio buttons.</span></span>

- <span data-ttu-id="e3422-118">**Tag a scelta multipla:** consente agli utenti di selezionare più tag all'interno di un gruppo.</span><span class="sxs-lookup"><span data-stu-id="e3422-118">**Multiple choice tags** - Allow users to select multiple tags within a group.</span></span> <span data-ttu-id="e3422-119">Questi elementi verranno visualizzati come caselle di controllo.</span><span class="sxs-lookup"><span data-stu-id="e3422-119">These will appear as checkboxes.</span></span>

## <a name="tag-structure"></a><span data-ttu-id="e3422-120">Struttura tag</span><span class="sxs-lookup"><span data-stu-id="e3422-120">Tag structure</span></span>

<span data-ttu-id="e3422-121">Oltre ai tipi di tag, è possibile usare la struttura di organizzazione dei tag nel pannello tag per rendere più intuitivo il tagging dei documenti.</span><span class="sxs-lookup"><span data-stu-id="e3422-121">In addition to the tag types, the structure of how tags are organized in the tag panel can be used to make tagging documents more intuitive.</span></span> <span data-ttu-id="e3422-122">I tag sono raggruppati per sezioni.</span><span class="sxs-lookup"><span data-stu-id="e3422-122">Tags are grouped by sections.</span></span> <span data-ttu-id="e3422-123">La ricerca di set di recensioni supporta la possibilità di eseguire ricerche in base al tag e alla sezione tag.</span><span class="sxs-lookup"><span data-stu-id="e3422-123">Review set search supports the ability to search by tag and by tag section.</span></span> <span data-ttu-id="e3422-124">Ciò significa che è possibile creare una ricerca di insieme da rivedere per recuperare i documenti contrassegnati con qualsiasi tag in una sezione.</span><span class="sxs-lookup"><span data-stu-id="e3422-124">This means you can create a review set search to retrieve documents tagged with any tag in a section.</span></span>

![Sezioni tag nel pannello tag](../media/Tagtypes.png)

<span data-ttu-id="e3422-126">I tag possono essere ulteriormente organizzati annidandoli all'interno di una sezione.</span><span class="sxs-lookup"><span data-stu-id="e3422-126">Tags can be further organized by nesting them within a section.</span></span> <span data-ttu-id="e3422-127">Ad esempio, se lo scopo è identificare e contrassegnare il contenuto con privilegi, la annidamento può essere usata per chiarire che un utente può contrassegnare un documento come "Privilegiato" e selezionare il tipo di privilegio controllando il tag annidato appropriato.</span><span class="sxs-lookup"><span data-stu-id="e3422-127">For example, if the intent is to identify and tag privileged content, nesting can be used to make it clear that a user can tag a document as "Privileged" and select the type of privilege by checking the appropriate nested tag.</span></span>

![Tag annidati all'interno di una sezione tag](../media/Nestingtags.png)

## <a name="applying-tags"></a><span data-ttu-id="e3422-129">Applicazione di tag</span><span class="sxs-lookup"><span data-stu-id="e3422-129">Applying tags</span></span>

<span data-ttu-id="e3422-130">Esistono diversi modi per applicare un tag al contenuto.</span><span class="sxs-lookup"><span data-stu-id="e3422-130">There are several ways to apply a tag to content.</span></span>

### <a name="tagging-a-single-document"></a><span data-ttu-id="e3422-131">Applicazione di tag a un singolo documento</span><span class="sxs-lookup"><span data-stu-id="e3422-131">Tagging a single document</span></span>

<span data-ttu-id="e3422-132">Quando si visualizza un documento in un insieme di revisioni, è possibile visualizzare i tag che possono essere utilizzati da una revisione facendo clic sul **pannello Tagging.**</span><span class="sxs-lookup"><span data-stu-id="e3422-132">When viewing a document in a review set, you can display the tags that a review can use by clicking **Tagging panel**.</span></span>

![Fare clic sul pannello Tag per visualizzare il pannello tag](../media/Singledoctag.png)

<span data-ttu-id="e3422-134">In questo modo sarà possibile applicare tag al documento visualizzato nel visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="e3422-134">This will enable you to apply tags to the document displayed in the viewer.</span></span>

### <a name="bulk-tagging"></a><span data-ttu-id="e3422-135">Aggiunta di tag in blocco</span><span class="sxs-lookup"><span data-stu-id="e3422-135">Bulk tagging</span></span>

<span data-ttu-id="e3422-136">Il tagging in blocco può essere eseguito selezionando più file nella griglia dei risultati e quindi usando i tag nel pannello Tagging in modo simile al **tagging** di singoli documenti.</span><span class="sxs-lookup"><span data-stu-id="e3422-136">Bulk tagging can be done by selecting multiple files in the results grid and then using the tags in the **Tagging panel** similar to tagging single documents.</span></span> <span data-ttu-id="e3422-137">L'annullamento del tagging in blocco può essere eseguito selezionando i tag due volte. Il primo clic applica il tag e la seconda selezione garantisce che il tag sia cancellato per tutti i file selezionati.</span><span class="sxs-lookup"><span data-stu-id="e3422-137">Bulk un-tagging can be done by selecting tags twice; the first click will apply the tag, and the second selection will ensure that tag is cleared for all selected files.</span></span>

![Screenshot della descrizione di un telefono cellulare generata automaticamente](../media/Bulktag.png)

> [!NOTE]
> <span data-ttu-id="e3422-139">Quando si esegue il tagging in blocco, il pannello di tagging visualizza un conteggio dei file contrassegnati per ogni tag nel pannello.</span><span class="sxs-lookup"><span data-stu-id="e3422-139">When bulk tagging, the tagging panel will display a count of files that are tagged for each tag in the panel.</span></span>

### <a name="tagging-in-other-review-panels"></a><span data-ttu-id="e3422-140">Aggiunta di tag in altri pannelli delle recensioni</span><span class="sxs-lookup"><span data-stu-id="e3422-140">Tagging in other review panels</span></span>

<span data-ttu-id="e3422-141">Durante la revisione dei documenti, è possibile utilizzare gli altri pannelli delle revisioni per esaminare altre caratteristiche dei documenti nella griglia dei risultati.</span><span class="sxs-lookup"><span data-stu-id="e3422-141">When reviewing documents, you can use the other review panels to review other characteristics of documents in the results grid.</span></span> <span data-ttu-id="e3422-142">Ciò include la revisione di altri documenti correlati, thread di posta elettronica, quasi duplicati e duplicati hash.</span><span class="sxs-lookup"><span data-stu-id="e3422-142">This includes reviewing other related documents, email threads, near duplicates, and hash duplicates.</span></span> <span data-ttu-id="e3422-143">Ad esempio, quando si rivendono documenti  correlati (utilizzando il riquadro revisione della famiglia di documenti), è possibile ridurre significativamente i tempi di revisione contrassegnando in blocco i documenti correlati.</span><span class="sxs-lookup"><span data-stu-id="e3422-143">For example, when you're reviewing related documents (by using the **Document family** review panel), you can significantly reduce review time by bulk tagging related documents.</span></span> <span data-ttu-id="e3422-144">Ad esempio, se un messaggio di posta elettronica contiene diversi allegati e si desidera garantire che l'intera famiglia sia contrassegnata in modo coerente.</span><span class="sxs-lookup"><span data-stu-id="e3422-144">For example, if an email message has several attachments and you want to ensure that the entire family is tagged consistently.</span></span>

<span data-ttu-id="e3422-145">Ad esempio, ecco come visualizzare il pannello **Tagging** quando si usa il pannello **Revisione famiglia** di documenti:</span><span class="sxs-lookup"><span data-stu-id="e3422-145">For example, here's how to display the **Tagging panel** when using the **Document family** review panel:</span></span>

1. <span data-ttu-id="e3422-146">Con il riquadro delle revisioni aperto per un documento selezionato(ad  esempio, visualizzando l'elenco dei contenuti correlati nel riquadro revisione della famiglia di documenti, fare clic su Tag **documenti** nel riquadro di revisione della famiglia di documenti.</span><span class="sxs-lookup"><span data-stu-id="e3422-146">With the review panel open for a selected document (for example, displaying the list of related content in the **Document family** review panel, click **Tag documents** under the document family review panel.</span></span>

   <span data-ttu-id="e3422-147">Il riquadro di tagging viene visualizzato come finestra popup.</span><span class="sxs-lookup"><span data-stu-id="e3422-147">The tagging panel is displayed as a pop-up window.</span></span>

2. <span data-ttu-id="e3422-148">Scegliere uno o più tag per applicare il documento selezionato.</span><span class="sxs-lookup"><span data-stu-id="e3422-148">Choose one or more tags to apply the selected document.</span></span> 

3. <span data-ttu-id="e3422-149">Per contrassegnare tutti i documenti, selezionare tutti i documenti nel riquadro Famiglia di documenti, fare clic su Tag documenti e quindi scegliere i tag da applicare all'intera famiglia di documenti. </span><span class="sxs-lookup"><span data-stu-id="e3422-149">To tag all documents, select all documents in the **Document family** panel, click **Tag documents**, and then choose the tags to apply to the entire family of documents.</span></span>

![Screenshot di un post di social media Descrizione generata automaticamente](../media/Relatedtag.png)
