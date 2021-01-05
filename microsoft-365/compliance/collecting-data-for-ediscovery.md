---
title: Raccogliere i dati per un caso in Advanced eDiscovery
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
description: Informazioni su come identificare un set di documenti per la revisione in un'indagine tramite lo strumento di ricerca in Advanced eDiscovery.
ms.custom: seo-marvel-2020
ms.openlocfilehash: b69127f1a372a9b843b9c7dac1b2909dd80b2988
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751269"
---
# <a name="collect-data-for-a-case-in-advanced-ediscovery"></a><span data-ttu-id="28ad6-103">Raccogliere i dati per un caso in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="28ad6-103">Collect data for a case in Advanced eDiscovery</span></span>

<span data-ttu-id="28ad6-104">Dopo aver identificato i depositari e le origini dati di interesse per il caso, è necessario identificare il set di documenti in cui eseguire l'approfondimento.</span><span class="sxs-lookup"><span data-stu-id="28ad6-104">Once you've identified custodians and data sources that are of interest for your case, it's time to identify the set of documents to delve into.</span></span> <span data-ttu-id="28ad6-105">È possibile utilizzare lo strumento di ricerca in Advanced eDiscovery per identificare i documenti rilevanti provenienti da posizioni detentive e non detentive in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="28ad6-105">You can use the Search tool in Advanced eDiscovery to identify relevant documents from custodial and non-custodial locations in Microsoft 365.</span></span>

<span data-ttu-id="28ad6-106">Dopo aver eseguito una ricerca, è possibile visualizzare le statistiche sugli elementi recuperati, ad esempio le posizioni con la maggior parte degli elementi corrispondenti alla query di ricerca.</span><span class="sxs-lookup"><span data-stu-id="28ad6-106">After you run a search, you can view statistics on the retrieved items, such as the locations that had the most items that matched the search query.</span></span> <span data-ttu-id="28ad6-107">È inoltre possibile visualizzare in anteprima un sottoinsieme dei risultati.</span><span class="sxs-lookup"><span data-stu-id="28ad6-107">You can also preview a subset of the results.</span></span> <span data-ttu-id="28ad6-108">Dopo aver identificato il set di documenti che si desidera esaminare ulteriormente, è possibile aggiungere i risultati della ricerca a un set di revisione da raccogliere ed elaborare.</span><span class="sxs-lookup"><span data-stu-id="28ad6-108">When you've identified the set of documents you want to further examine, you can add the search results to a review set to collect and process.</span></span>

## <a name="create-a-search"></a><span data-ttu-id="28ad6-109">Creare una ricerca</span><span class="sxs-lookup"><span data-stu-id="28ad6-109">Create a search</span></span>

<span data-ttu-id="28ad6-110">Selezionando **nuova ricerca** nella scheda **ricerche** verrà avviata una procedura guidata che consentirà di creare una ricerca.</span><span class="sxs-lookup"><span data-stu-id="28ad6-110">Selecting **New search** on the **Searches** tab will start a wizard that guides you through creating a search.</span></span> <span data-ttu-id="28ad6-111">Per informazioni dettagliate su come creare una ricerca, vedere [creare una ricerca per raccogliere i dati](create-search-to-collect-data.md).</span><span class="sxs-lookup"><span data-stu-id="28ad6-111">For detailed information on how to create a search, see [Create a search to collect data](create-search-to-collect-data.md).</span></span>

<span data-ttu-id="28ad6-112">Dopo la creazione di una ricerca, viene visualizzata una pagina a comparsa con dettagli.</span><span class="sxs-lookup"><span data-stu-id="28ad6-112">After a search is created, a flyout page with details is displayed.</span></span> <span data-ttu-id="28ad6-113">I pulsanti **statistiche** e **Anteprima** non sono disponibili inizialmente perché la ricerca non è ancora stata completata.</span><span class="sxs-lookup"><span data-stu-id="28ad6-113">The **Statistics** and **Preview** buttons are initially unavailable because the search hasn't completed yet.</span></span> <span data-ttu-id="28ad6-114">È possibile tenere conto dello stato di avanzamento della ricerca nella scheda **ricerche** .</span><span class="sxs-lookup"><span data-stu-id="28ad6-114">You can keep track of the progress of the search on the **Searches** tab.</span></span>

## <a name="view-search-results-and-statistics"></a><span data-ttu-id="28ad6-115">Visualizzare i risultati della ricerca e le statistiche</span><span class="sxs-lookup"><span data-stu-id="28ad6-115">View search results and statistics</span></span>

<span data-ttu-id="28ad6-116">Sono disponibili due componenti di una ricerca di contenuto: statistiche (stime) e anteprima.</span><span class="sxs-lookup"><span data-stu-id="28ad6-116">There are two components of a content search: Statistics (Estimates) and Preview.</span></span> <span data-ttu-id="28ad6-117">Dopo aver completato ognuno di questi componenti, lo stato visualizzato nelle colonne corrispondenti nella scheda **ricerche** cambia da **inviato** a **in corso** a **completato**.</span><span class="sxs-lookup"><span data-stu-id="28ad6-117">As each of these components complete, you'll see the status displayed in the corresponding columns on the **Searches** tab change from **Submitted** to **In progress** to **Completed**.</span></span>

<span data-ttu-id="28ad6-118">Una volta completata la stima della ricerca, selezionare la ricerca per visualizzare la pagina del riquadro a comparsa, in cui vengono visualizzate le statistiche di alto livello sui risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="28ad6-118">Once the search estimate is completed, select the search to display the flyout page, which will display some high-level statistics about the results of the search.</span></span> <span data-ttu-id="28ad6-119">A questo punto, il pulsante **statistiche** sarà attivo.</span><span class="sxs-lookup"><span data-stu-id="28ad6-119">At this point, the **Statistics** button will be active.</span></span> <span data-ttu-id="28ad6-120">È possibile selezionarla per visualizzare le statistiche di ricerca, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="28ad6-120">You can select it to see search statistics, such as:</span></span>

- <span data-ttu-id="28ad6-121">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="28ad6-121">Summary</span></span>
- <span data-ttu-id="28ad6-122">Posizioni principali</span><span class="sxs-lookup"><span data-stu-id="28ad6-122">Top locations</span></span>
- <span data-ttu-id="28ad6-123">Query</span><span class="sxs-lookup"><span data-stu-id="28ad6-123">Queries</span></span>

<span data-ttu-id="28ad6-124">Per ulteriori informazioni sulle statistiche di ricerca, vedere [Search Statistics](search-statistics-in-advanced-ediscovery.md).</span><span class="sxs-lookup"><span data-stu-id="28ad6-124">For more information about search statistics, see [Search statistics](search-statistics-in-advanced-ediscovery.md).</span></span>

<span data-ttu-id="28ad6-125">Dopo aver completato l'anteprima, il pulsante **Anteprima** sarà attivo.</span><span class="sxs-lookup"><span data-stu-id="28ad6-125">Once preview is completed, the **Preview** button will be active.</span></span> <span data-ttu-id="28ad6-126">Selezionarla per visualizzare in anteprima un sottoinsieme di campionamento dei risultati.</span><span class="sxs-lookup"><span data-stu-id="28ad6-126">Select it to preview a sampled subset of the results.</span></span>

## <a name="add-search-results-to-a-review-set"></a><span data-ttu-id="28ad6-127">Aggiungere i risultati della ricerca a un insieme da rivedere</span><span class="sxs-lookup"><span data-stu-id="28ad6-127">Add search results to a review set</span></span>

<span data-ttu-id="28ad6-128">Quando si è pronti per la raccolta e l'elaborazione di tutti i risultati di una ricerca, è possibile farlo aggiungendola a un set di revisione.</span><span class="sxs-lookup"><span data-stu-id="28ad6-128">When you're ready to collect and process the entire results of a search, you can do so by adding it to a review set.</span></span> <span data-ttu-id="28ad6-129">Per ulteriori informazioni, vedere [Add Data to a Review set](add-data-to-review-set.md).</span><span class="sxs-lookup"><span data-stu-id="28ad6-129">For details, see [Add data to a review set](add-data-to-review-set.md).</span></span>

## <a name="add-non-microsoft-365-data-to-a-review-set"></a><span data-ttu-id="28ad6-130">Aggiungere dati non Microsoft 365 a un set di Revisione</span><span class="sxs-lookup"><span data-stu-id="28ad6-130">Add non-Microsoft 365 data to a review set</span></span>

<span data-ttu-id="28ad6-131">Come parte del processo di raccolta per un caso, è anche possibile aggiungere dati non di Office 365 a un set di revisione ed esaminare e analizzare insieme ai dati di Office 365 raccolti tramite lo strumento di ricerca.</span><span class="sxs-lookup"><span data-stu-id="28ad6-131">As part of the collection process for a case, you can also add non-Office 365 data to a review set and review and analyze together with the Office 365 data that you collected by using the search tool.</span></span> <span data-ttu-id="28ad6-132">Quando si aggiungono non Office 365, è necessario associarlo a un determinato custode nel caso.</span><span class="sxs-lookup"><span data-stu-id="28ad6-132">When you add non-Office 365, you have to associate it with a specific custodian in the case.</span></span> <span data-ttu-id="28ad6-133">Per ulteriori informazioni, vedere [caricare i dati non Microsoft 365 in un set di revisione](load-non-Office-365-data-into-a-review-set.md).</span><span class="sxs-lookup"><span data-stu-id="28ad6-133">For more information, see [Load non-Microsoft 365 data into a review set](load-non-Office-365-data-into-a-review-set.md).</span></span>
