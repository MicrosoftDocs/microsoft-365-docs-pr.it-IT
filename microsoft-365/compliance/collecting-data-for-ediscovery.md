---
title: Raccogliere i dati per un caso in Advanced eDiscovery
ms.author: esclee
author: markjjo
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
ms.assetid: ''
description: ''
ms.openlocfilehash: 4e0bc71071ecfe20a2141e72b1146e9688618faf
ms.sourcegitcommit: e386037c9cc335c86896dc153344850735afbccd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/27/2019
ms.locfileid: "39633605"
---
# <a name="collect-data-for-a-case-in-advanced-ediscovery"></a><span data-ttu-id="c360e-102">Raccogliere i dati per un caso in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="c360e-102">Collect data for a case in Advanced eDiscovery</span></span>

<span data-ttu-id="c360e-103">Dopo aver identificato i depositari e le origini dati di interesse per il caso, è necessario identificare il set di documenti in cui eseguire l'approfondimento.</span><span class="sxs-lookup"><span data-stu-id="c360e-103">Once you've identified custodians and data sources that are of interest for your case, it's time to identify the set of documents to delve into.</span></span> <span data-ttu-id="c360e-104">È possibile utilizzare lo strumento di ricerca in Advanced eDiscovery per identificarli da posizioni detentive e non detentive in Office 365.</span><span class="sxs-lookup"><span data-stu-id="c360e-104">You can use the Search tool in Advanced eDiscovery to identify these from custodial and non-custodial locations in Office 365.</span></span>

<span data-ttu-id="c360e-105">Dopo aver eseguito una ricerca, è possibile visualizzare le statistiche sugli elementi recuperati, ad esempio le posizioni con la maggior parte degli elementi corrispondenti alla query di ricerca.</span><span class="sxs-lookup"><span data-stu-id="c360e-105">After you run a search, you can view statistics on the retrieved items, such as the locations that had the most items that matched the search query.</span></span> <span data-ttu-id="c360e-106">È inoltre possibile visualizzare in anteprima un sottoinsieme dei risultati.</span><span class="sxs-lookup"><span data-stu-id="c360e-106">You can also preview a subset of the results.</span></span> <span data-ttu-id="c360e-107">Dopo aver identificato il set di documenti che si desidera esaminare ulteriormente, è possibile aggiungere i risultati della ricerca a un set di revisione da raccogliere ed elaborare.</span><span class="sxs-lookup"><span data-stu-id="c360e-107">When you've identified the set of documents you want to further examine, you can add the search results to a review set to collect and process.</span></span>

## <a name="create-a-search"></a><span data-ttu-id="c360e-108">Creare una ricerca</span><span class="sxs-lookup"><span data-stu-id="c360e-108">Create a search</span></span>

<span data-ttu-id="c360e-109">Selezionando **nuova ricerca** nella scheda **ricerche** verrà avviata una procedura guidata che consentirà di creare una ricerca.</span><span class="sxs-lookup"><span data-stu-id="c360e-109">Selecting **New search** on the **Searches** tab will start a wizard that guides you through creating a search.</span></span> <span data-ttu-id="c360e-110">Per informazioni dettagliate su come creare una ricerca, vedere [creare una ricerca per raccogliere i dati](create-search-to-collect-data.md).</span><span class="sxs-lookup"><span data-stu-id="c360e-110">For detailed information on how to create a search, see [Create a search to collect data](create-search-to-collect-data.md).</span></span>

<span data-ttu-id="c360e-111">Dopo la creazione di una ricerca, viene visualizzata una pagina a comparsa con dettagli.</span><span class="sxs-lookup"><span data-stu-id="c360e-111">After a search is created, a flyout page with details is displayed.</span></span> <span data-ttu-id="c360e-112">I pulsanti **statistiche** e **Anteprima** non sono disponibili inizialmente perché la ricerca non è ancora stata completata.</span><span class="sxs-lookup"><span data-stu-id="c360e-112">The **Statistics** and **Preview** buttons are initially unavailable because the search hasn't completed yet.</span></span> <span data-ttu-id="c360e-113">È possibile tenere conto dello stato di avanzamento della ricerca nella scheda **ricerche** .</span><span class="sxs-lookup"><span data-stu-id="c360e-113">You can keep track of the progress of the search on the **Searches** tab.</span></span>

## <a name="view-search-results-and-statistics"></a><span data-ttu-id="c360e-114">Visualizzare i risultati della ricerca e le statistiche</span><span class="sxs-lookup"><span data-stu-id="c360e-114">View search results and statistics</span></span>

<span data-ttu-id="c360e-115">Sono disponibili due componenti di una ricerca di contenuto: statistiche (stime) e anteprima.</span><span class="sxs-lookup"><span data-stu-id="c360e-115">There are two components of a content search: Statistics (Estimates) and Preview.</span></span> <span data-ttu-id="c360e-116">Dopo aver completato ognuno di questi componenti, lo stato visualizzato nelle colonne corrispondenti nella scheda **ricerche** cambia da **inviato** a **in corso** a **completato**.</span><span class="sxs-lookup"><span data-stu-id="c360e-116">As each of these components complete, you'll see the status displayed in the corresponding columns on the **Searches** tab change from **Submitted** to **In progress** to **Completed**.</span></span>

<span data-ttu-id="c360e-117">Una volta completata la stima della ricerca, selezionare la ricerca per visualizzare la pagina del riquadro a comparsa, in cui vengono visualizzate le statistiche di alto livello sui risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="c360e-117">Once the search estimate is completed, select the search to display the flyout page, which will display some high-level statistics about the results of the search.</span></span> <span data-ttu-id="c360e-118">A questo punto, il pulsante **statistiche** sarà attivo.</span><span class="sxs-lookup"><span data-stu-id="c360e-118">At this point, the **Statistics** button will be active.</span></span> <span data-ttu-id="c360e-119">È possibile selezionarla per visualizzare le statistiche di ricerca, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="c360e-119">You can select it to see search statistics, such as:</span></span>

- <span data-ttu-id="c360e-120">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="c360e-120">Summary</span></span>
- <span data-ttu-id="c360e-121">Posizioni principali</span><span class="sxs-lookup"><span data-stu-id="c360e-121">Top locations</span></span>
- <span data-ttu-id="c360e-122">Query</span><span class="sxs-lookup"><span data-stu-id="c360e-122">Queries</span></span>

<span data-ttu-id="c360e-123">Per ulteriori informazioni sulle statistiche di ricerca, vedere [Search Statistics](search-statistics.md).</span><span class="sxs-lookup"><span data-stu-id="c360e-123">For more information about search statistics, see [Search statistics](search-statistics.md).</span></span>

<span data-ttu-id="c360e-124">Dopo aver completato l'anteprima, il pulsante **Anteprima** sarà attivo.</span><span class="sxs-lookup"><span data-stu-id="c360e-124">Once preview is completed, the **Preview** button will be active.</span></span> <span data-ttu-id="c360e-125">Selezionarla per visualizzare in anteprima un sottoinsieme di campionamento dei risultati.</span><span class="sxs-lookup"><span data-stu-id="c360e-125">Select it to preview a sampled subset of the results.</span></span>

## <a name="adding-search-results-to-a-review-set"></a><span data-ttu-id="c360e-126">Aggiunta dei risultati di ricerca a un set di Revisione</span><span class="sxs-lookup"><span data-stu-id="c360e-126">Adding search results to a review set</span></span>

<span data-ttu-id="c360e-127">Quando si è pronti per la raccolta e l'elaborazione di tutti i risultati di una ricerca, è possibile farlo aggiungendola a un set di revisione.</span><span class="sxs-lookup"><span data-stu-id="c360e-127">When you're ready to collect and process the entire results of a search, you can do so by adding it to a review set.</span></span> <span data-ttu-id="c360e-128">Per ulteriori informazioni, vedere [Add Data to a Review set](add-data-to-review-set.md).</span><span class="sxs-lookup"><span data-stu-id="c360e-128">For details, see [Add data to a review set](add-data-to-review-set.md).</span></span>
