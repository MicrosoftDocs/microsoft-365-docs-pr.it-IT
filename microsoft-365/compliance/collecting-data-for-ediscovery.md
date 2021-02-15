---
title: Raccogliere dati per un caso in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
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
description: Informazioni su come identificare un set di documenti da rivedere in un'indagine utilizzando lo strumento di ricerca in Advanced eDiscovery.
ms.custom: seo-marvel-2020
ms.openlocfilehash: b69127f1a372a9b843b9c7dac1b2909dd80b2988
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751269"
---
# <a name="collect-data-for-a-case-in-advanced-ediscovery"></a><span data-ttu-id="fd22c-103">Raccogliere dati per un caso in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="fd22c-103">Collect data for a case in Advanced eDiscovery</span></span>

<span data-ttu-id="fd22c-104">Dopo aver identificato i responsabile e le origini dati di interesse per il caso, è il momento di identificare il set di documenti da approfondire.</span><span class="sxs-lookup"><span data-stu-id="fd22c-104">Once you've identified custodians and data sources that are of interest for your case, it's time to identify the set of documents to delve into.</span></span> <span data-ttu-id="fd22c-105">È possibile utilizzare lo strumento di ricerca in Advanced eDiscovery per identificare i documenti rilevanti da posizioni di depositario e non responsabile in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fd22c-105">You can use the Search tool in Advanced eDiscovery to identify relevant documents from custodial and non-custodial locations in Microsoft 365.</span></span>

<span data-ttu-id="fd22c-106">Dopo aver eseguito una ricerca, è possibile visualizzare le statistiche relative agli elementi recuperati, ad esempio le posizioni con il maggior numero di elementi corrispondenti alla query di ricerca.</span><span class="sxs-lookup"><span data-stu-id="fd22c-106">After you run a search, you can view statistics on the retrieved items, such as the locations that had the most items that matched the search query.</span></span> <span data-ttu-id="fd22c-107">È inoltre possibile visualizzare in anteprima un sottoinsieme dei risultati.</span><span class="sxs-lookup"><span data-stu-id="fd22c-107">You can also preview a subset of the results.</span></span> <span data-ttu-id="fd22c-108">Dopo aver identificato il set di documenti che si desidera esaminare ulteriormente, è possibile aggiungere i risultati della ricerca a un insieme da raccogliere ed elaborare.</span><span class="sxs-lookup"><span data-stu-id="fd22c-108">When you've identified the set of documents you want to further examine, you can add the search results to a review set to collect and process.</span></span>

## <a name="create-a-search"></a><span data-ttu-id="fd22c-109">Creare una ricerca</span><span class="sxs-lookup"><span data-stu-id="fd22c-109">Create a search</span></span>

<span data-ttu-id="fd22c-110">Se **si seleziona Nuova** ricerca nella scheda **Ricerche,** verrà avviata una procedura guidata che guida l'utente nella creazione di una ricerca.</span><span class="sxs-lookup"><span data-stu-id="fd22c-110">Selecting **New search** on the **Searches** tab will start a wizard that guides you through creating a search.</span></span> <span data-ttu-id="fd22c-111">Per informazioni dettagliate su come creare una ricerca, vedere [Creare una ricerca per raccogliere dati.](create-search-to-collect-data.md)</span><span class="sxs-lookup"><span data-stu-id="fd22c-111">For detailed information on how to create a search, see [Create a search to collect data](create-search-to-collect-data.md).</span></span>

<span data-ttu-id="fd22c-112">Dopo la creazione di una ricerca, viene visualizzata una pagina a comparsa con i dettagli.</span><span class="sxs-lookup"><span data-stu-id="fd22c-112">After a search is created, a flyout page with details is displayed.</span></span> <span data-ttu-id="fd22c-113">I **pulsanti Statistiche** e **Anteprima** non sono inizialmente disponibili perché la ricerca non è ancora stata completata.</span><span class="sxs-lookup"><span data-stu-id="fd22c-113">The **Statistics** and **Preview** buttons are initially unavailable because the search hasn't completed yet.</span></span> <span data-ttu-id="fd22c-114">È possibile tenere traccia dell'avanzamento della ricerca nella **scheda** Ricerche.</span><span class="sxs-lookup"><span data-stu-id="fd22c-114">You can keep track of the progress of the search on the **Searches** tab.</span></span>

## <a name="view-search-results-and-statistics"></a><span data-ttu-id="fd22c-115">Visualizzare i risultati e le statistiche della ricerca</span><span class="sxs-lookup"><span data-stu-id="fd22c-115">View search results and statistics</span></span>

<span data-ttu-id="fd22c-116">Esistono due componenti di una ricerca di contenuto: Statistiche (stime) e Anteprima.</span><span class="sxs-lookup"><span data-stu-id="fd22c-116">There are two components of a content search: Statistics (Estimates) and Preview.</span></span> <span data-ttu-id="fd22c-117">Al termine di ognuno di questi componenti, lo stato visualizzato  nelle colonne  corrispondenti nella scheda Ricerche cambia da Inviato **a In corso** e **Completato.**</span><span class="sxs-lookup"><span data-stu-id="fd22c-117">As each of these components complete, you'll see the status displayed in the corresponding columns on the **Searches** tab change from **Submitted** to **In progress** to **Completed**.</span></span>

<span data-ttu-id="fd22c-118">Una volta completata la stima della ricerca, selezionare la ricerca per visualizzare la pagina del riquadro a comparsa, in cui verranno visualizzate alcune statistiche di alto livello sui risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="fd22c-118">Once the search estimate is completed, select the search to display the flyout page, which will display some high-level statistics about the results of the search.</span></span> <span data-ttu-id="fd22c-119">A questo punto, il **pulsante** Statistiche sarà attivo.</span><span class="sxs-lookup"><span data-stu-id="fd22c-119">At this point, the **Statistics** button will be active.</span></span> <span data-ttu-id="fd22c-120">È possibile selezionarlo per visualizzare le statistiche di ricerca, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="fd22c-120">You can select it to see search statistics, such as:</span></span>

- <span data-ttu-id="fd22c-121">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="fd22c-121">Summary</span></span>
- <span data-ttu-id="fd22c-122">Posizioni principali</span><span class="sxs-lookup"><span data-stu-id="fd22c-122">Top locations</span></span>
- <span data-ttu-id="fd22c-123">Query</span><span class="sxs-lookup"><span data-stu-id="fd22c-123">Queries</span></span>

<span data-ttu-id="fd22c-124">Per ulteriori informazioni sulle statistiche di ricerca, vedere [Statistiche della ricerca.](search-statistics-in-advanced-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="fd22c-124">For more information about search statistics, see [Search statistics](search-statistics-in-advanced-ediscovery.md).</span></span>

<span data-ttu-id="fd22c-125">Al termine dell'anteprima, il **pulsante** Anteprima sarà attivo.</span><span class="sxs-lookup"><span data-stu-id="fd22c-125">Once preview is completed, the **Preview** button will be active.</span></span> <span data-ttu-id="fd22c-126">Selezionarlo per visualizzare un'anteprima di un sottoinsieme campionato dei risultati.</span><span class="sxs-lookup"><span data-stu-id="fd22c-126">Select it to preview a sampled subset of the results.</span></span>

## <a name="add-search-results-to-a-review-set"></a><span data-ttu-id="fd22c-127">Aggiungere i risultati della ricerca a un insieme da rivedere</span><span class="sxs-lookup"><span data-stu-id="fd22c-127">Add search results to a review set</span></span>

<span data-ttu-id="fd22c-128">Quando si è pronti per raccogliere ed elaborare tutti i risultati di una ricerca, è possibile aggiungerli a un insieme da rivedere.</span><span class="sxs-lookup"><span data-stu-id="fd22c-128">When you're ready to collect and process the entire results of a search, you can do so by adding it to a review set.</span></span> <span data-ttu-id="fd22c-129">Per informazioni dettagliate, vedere [Aggiungere dati a un insieme da rivedere.](add-data-to-review-set.md)</span><span class="sxs-lookup"><span data-stu-id="fd22c-129">For details, see [Add data to a review set](add-data-to-review-set.md).</span></span>

## <a name="add-non-microsoft-365-data-to-a-review-set"></a><span data-ttu-id="fd22c-130">Aggiungere dati non Di Microsoft 365 a un insieme da rivedere</span><span class="sxs-lookup"><span data-stu-id="fd22c-130">Add non-Microsoft 365 data to a review set</span></span>

<span data-ttu-id="fd22c-131">Come parte del processo di raccolta di un caso, è anche possibile aggiungere dati non di Office 365 a un insieme da rivedere e analizzare insieme ai dati di Office 365 raccolti tramite lo strumento di ricerca.</span><span class="sxs-lookup"><span data-stu-id="fd22c-131">As part of the collection process for a case, you can also add non-Office 365 data to a review set and review and analyze together with the Office 365 data that you collected by using the search tool.</span></span> <span data-ttu-id="fd22c-132">Quando si aggiunge non Office 365, è necessario associarlo a un responsabile specifico nel caso.</span><span class="sxs-lookup"><span data-stu-id="fd22c-132">When you add non-Office 365, you have to associate it with a specific custodian in the case.</span></span> <span data-ttu-id="fd22c-133">Per ulteriori informazioni, vedere [Caricare dati non Di Microsoft 365 in un insieme da rivedere.](load-non-Office-365-data-into-a-review-set.md)</span><span class="sxs-lookup"><span data-stu-id="fd22c-133">For more information, see [Load non-Microsoft 365 data into a review set](load-non-Office-365-data-into-a-review-set.md).</span></span>
