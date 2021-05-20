---
title: Visualizzare in anteprima i risultati di una ricerca eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MED150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Visualizzare in anteprima un campione dei risultati restituiti da una Ricerca contenuto o da una ricerca Core eDiscovery nel Centro conformità Microsoft 365.
ms.openlocfilehash: a89c8c9ed2500b4e2a859c75be3da177203d1406
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538600"
---
# <a name="preview-ediscovery-search-results"></a><span data-ttu-id="e43a7-103">Visualizzare in anteprima i risultati di una ricerca di eDiscovery</span><span class="sxs-lookup"><span data-stu-id="e43a7-103">Preview eDiscovery search results</span></span>

<span data-ttu-id="e43a7-104">Dopo aver eseguito una Ricerca contenuto o una ricerca associata a un caso di Core eDiscovery, è possibile visualizzare in anteprima un campione dei risultati restituiti dalla ricerca.</span><span class="sxs-lookup"><span data-stu-id="e43a7-104">After you run a Content search or a search associated with a Core eDiscovery case, you can preview a sample of the results returned by the search.</span></span> <span data-ttu-id="e43a7-105">La visualizzazione in anteprima degli elementi restituiti dalla query di ricerca consente di determinare se la ricerca restituisce i risultati previsti o se è necessario modificare la query ed eseguire di nuovo la ricerca.</span><span class="sxs-lookup"><span data-stu-id="e43a7-105">Previewing items returned by the search query can help you determine if the search is returning the results you hope for or if you need to change the search query and rerun the search.</span></span>

<span data-ttu-id="e43a7-106">Per visualizzare in anteprima un campione dei risultati restituiti da una ricerca:</span><span class="sxs-lookup"><span data-stu-id="e43a7-106">To preview a sample of results returned by a search:</span></span>

1. <span data-ttu-id="e43a7-107">Nel Centro conformità Microsoft 365, passare alla pagina Ricerca contenuto o a un caso di Core eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="e43a7-107">In the Microsoft 365 compliance center, go to the Content search page or a Core eDiscovery case.</span></span>

2. <span data-ttu-id="e43a7-108">Selezionare la ricerca per visualizzare la pagina a comparsa.</span><span class="sxs-lookup"><span data-stu-id="e43a7-108">Select search to display the flyout page.</span></span>

3. <span data-ttu-id="e43a7-109">Nella parte inferiore della pagina, fare clic su **Verifica campione**.</span><span class="sxs-lookup"><span data-stu-id="e43a7-109">On the bottom of the flyout page, click **Review sample**.</span></span>

   ![Fare clic su Esamina esempio nella pagina a comparsa per visualizzare in anteprima i risultati](../media/PreviewSearchResults1.png)

   <span data-ttu-id="e43a7-111">Viene visualizzata una pagina contenente un esempio dei risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="e43a7-111">A page is displayed containing a sample of the search results.</span></span>

4. <span data-ttu-id="e43a7-112">Selezionare un elemento per visualizzarne il contenuto nel Riquadro di lettura.</span><span class="sxs-lookup"><span data-stu-id="e43a7-112">Select an item to view its contents in the reading pane.</span></span>

   ![Visualizzare in anteprima gli elementi nel Riquadro di lettura](../media/PreviewSearchResults2.png)

   <span data-ttu-id="e43a7-114">Nello screenshot precedente, le parole chiave della query di ricerca sono evidenziate quando si visualizza l'anteprima degli elementi.</span><span class="sxs-lookup"><span data-stu-id="e43a7-114">In the previous screenshot, notice that keywords from the search query are highlighted when you preview items.</span></span>

## <a name="how-the-search-result-samples-are-selected"></a><span data-ttu-id="e43a7-115">Come vengono selezionati gli esempi dei risultati della ricerca</span><span class="sxs-lookup"><span data-stu-id="e43a7-115">How the search result samples are selected</span></span>

<span data-ttu-id="e43a7-116">Per l'anteprima sono disponibili al massimo 1.000 elementi selezionati casualmente.</span><span class="sxs-lookup"><span data-stu-id="e43a7-116">A maximum of 1,000 randomly selected items are available to preview.</span></span> <span data-ttu-id="e43a7-117">Oltre a essere selezionati in modo casuale, gli elementi disponibili per l'anteprima devono anche soddisfare i criteri seguenti:</span><span class="sxs-lookup"><span data-stu-id="e43a7-117">In addition to being randomly selected, items available for preview must also meet the following criteria:</span></span>

- <span data-ttu-id="e43a7-118">È possibile visualizzare in anteprima un massimo di 100 elementi da un singolo percorso di contenuto (una cassetta postale o un sito).</span><span class="sxs-lookup"><span data-stu-id="e43a7-118">A maximum of 100 items from a single content location (a mailbox or a site) can be previewed.</span></span> <span data-ttu-id="e43a7-119">Ciò significa che è possibile che meno di 1.000 elementi siano disponibili per l'anteprima.</span><span class="sxs-lookup"><span data-stu-id="e43a7-119">This means that it's possible that less than 1,000 items might be available for preview.</span></span> <span data-ttu-id="e43a7-120">Ad esempio, se si cerca in quattro cassette postali e la ricerca restituisce 1.500 elementi stimati, solo 400 saranno disponibili per l'anteprima, perché è possibile visualizzare in anteprima solo 100 elementi per ogni cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="e43a7-120">For example, if you search four mailboxes and the search returns 1,500 estimated items, only 400 will be available for preview because only 100 items from each mailbox can be previewed.</span></span>

- <span data-ttu-id="e43a7-121">Per gli elementi della cassetta postale, l'anteprima è disponibile solo per i messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="e43a7-121">For mailbox items, only email messages are available to preview.</span></span> <span data-ttu-id="e43a7-122">Non è possibile visualizzare in anteprima elementi come attività, elementi del calendario e contatti.</span><span class="sxs-lookup"><span data-stu-id="e43a7-122">Items like tasks, calendar items, and contacts can't be previewed.</span></span>

- <span data-ttu-id="e43a7-123">Per gli elementi del sito, l'anteprima è disponibile solo per i documenti.</span><span class="sxs-lookup"><span data-stu-id="e43a7-123">For site items, only documents are available to preview.</span></span> <span data-ttu-id="e43a7-124">Non è possibile visualizzare in anteprima elementi come cartelle, elenchi o allegati di elenchi.</span><span class="sxs-lookup"><span data-stu-id="e43a7-124">Items like folders, lists, or list attachments can't be previewed.</span></span>

## <a name="file-types-supported-when-previewing-search-results"></a><span data-ttu-id="e43a7-125">Tipi di file supportati quando si visualizza l'anteprima dei risultati della ricerca</span><span class="sxs-lookup"><span data-stu-id="e43a7-125">File types supported when previewing search results</span></span>

<span data-ttu-id="e43a7-126">È possibile visualizzare l'anteprima dei tipi di file supportati nel riquadro di anteprima.</span><span class="sxs-lookup"><span data-stu-id="e43a7-126">You can preview supported file types in the preview pane.</span></span> <span data-ttu-id="e43a7-127">Se un tipo di file non è supportato, è necessario scaricarne una copia nel computer locale facendo clic su **Scarica elemento originale**.</span><span class="sxs-lookup"><span data-stu-id="e43a7-127">If a file type isn't supported, you have to download a copy of the file to your local computer (by clicking **Download original item**).</span></span> <span data-ttu-id="e43a7-128">Nelle pagine Web ASPX l'URL della pagina è incluso, anche se l'utente potrebbe non avere le autorizzazioni per accedere alla pagina.</span><span class="sxs-lookup"><span data-stu-id="e43a7-128">For .aspx Web pages, the URL for the page is included though you may not have permissions to access the page.</span></span> <span data-ttu-id="e43a7-129">Gli elementi non indicizzati non sono disponibili per la visualizzazione in anteprima.</span><span class="sxs-lookup"><span data-stu-id="e43a7-129">Unindexed items aren't available for previewing.</span></span>

<span data-ttu-id="e43a7-130">I tipi di file seguenti sono supportati e possono essere visualizzati in anteprima nel riquadro risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="e43a7-130">The following file types are supported and can be previewed in the search results pane.</span></span>
  
- <span data-ttu-id="e43a7-131">.txt, .html, .mhtml</span><span class="sxs-lookup"><span data-stu-id="e43a7-131">.txt, .html, .mhtml</span></span>

- <span data-ttu-id="e43a7-132">.eml</span><span class="sxs-lookup"><span data-stu-id="e43a7-132">.eml</span></span>

- <span data-ttu-id="e43a7-133">.doc, .docx, .docm</span><span class="sxs-lookup"><span data-stu-id="e43a7-133">.doc, .docx, .docm</span></span>

- <span data-ttu-id="e43a7-134">.pptm, .pptx</span><span class="sxs-lookup"><span data-stu-id="e43a7-134">.pptm, .pptx</span></span>

- <span data-ttu-id="e43a7-135">.pdf</span><span class="sxs-lookup"><span data-stu-id="e43a7-135">.pdf</span></span>

<span data-ttu-id="e43a7-136">Sono supportati anche i seguenti tipi di contenitori di file.</span><span class="sxs-lookup"><span data-stu-id="e43a7-136">Also, the following file container types are supported.</span></span> <span data-ttu-id="e43a7-137">È possibile visualizzare l'elenco di file nel contenitore nel riquadro di anteprima.</span><span class="sxs-lookup"><span data-stu-id="e43a7-137">You can view the list of files in the container in the preview pane.</span></span>
  
- <span data-ttu-id="e43a7-138">.zip</span><span class="sxs-lookup"><span data-stu-id="e43a7-138">.zip</span></span>

- <span data-ttu-id="e43a7-139">.gzip</span><span class="sxs-lookup"><span data-stu-id="e43a7-139">.gzip</span></span>