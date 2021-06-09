---
title: Eseguire query sul contenuto di un set di recensioni
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
description: Informazioni su come creare ed eseguire una query in un set di recensioni per organizzare il contenuto per una revisione più efficiente in un Advanced eDiscovery caso.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 64dbeb8ad68f4188e5768a0a7e0e80ca6c22760b
ms.sourcegitcommit: cc9e3cac6af23f20d7cc5ac6fc6f6e01bc3cc5c5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2021
ms.locfileid: "52736421"
---
# <a name="query-and-filter-content-in-a-review-set"></a><span data-ttu-id="71456-103">Query e contenuto del filtro in un insieme da rivedere</span><span class="sxs-lookup"><span data-stu-id="71456-103">Query and filter content in a review set</span></span>

<span data-ttu-id="71456-104">Nella maggior parte dei casi, sarà utile approfondire il contenuto di un set di recensioni e organizzarlo per facilitare una revisione più efficiente.</span><span class="sxs-lookup"><span data-stu-id="71456-104">In most cases, it will be useful to dig deeper into the content in a review set and organize it to facilitate a more efficient review.</span></span> <span data-ttu-id="71456-105">L'utilizzo di filtri e query in un set di revisioni consente di concentrarsi su un sottoinsieme di documenti che soddisfano i criteri della revisione.</span><span class="sxs-lookup"><span data-stu-id="71456-105">Using filters and queries in a review set helps you focus on a subset of documents that meet the criteria of your review.</span></span>

## <a name="default-filters"></a><span data-ttu-id="71456-106">Filtri predefiniti</span><span class="sxs-lookup"><span data-stu-id="71456-106">Default filters</span></span>

<span data-ttu-id="71456-107">In un set di recensioni sono presenti cinque filtri predefiniti precaricati nel set di recensioni:</span><span class="sxs-lookup"><span data-stu-id="71456-107">In a review set, there are five default filters that are pre-loaded in the review set:</span></span>

- <span data-ttu-id="71456-108">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="71456-108">Keywords</span></span>
- <span data-ttu-id="71456-109">Data</span><span class="sxs-lookup"><span data-stu-id="71456-109">Date</span></span>
- <span data-ttu-id="71456-110">Mittente/Autore</span><span class="sxs-lookup"><span data-stu-id="71456-110">Sender/Author</span></span>
- <span data-ttu-id="71456-111">Oggetto/Titolo</span><span class="sxs-lookup"><span data-stu-id="71456-111">Subject/Title</span></span>
- <span data-ttu-id="71456-112">Tag</span><span class="sxs-lookup"><span data-stu-id="71456-112">Tags</span></span>

![Tipi di filtro predefiniti](../media/DefaultFilterTypes.png)

<span data-ttu-id="71456-114">Fare clic su ogni filtro per espanderlo e assegnare un valore.</span><span class="sxs-lookup"><span data-stu-id="71456-114">Click each filter to expand it and assign a value.</span></span> <span data-ttu-id="71456-115">Fare clic all'esterno del filtro per applicare automaticamente il filtro al set di revisioni.</span><span class="sxs-lookup"><span data-stu-id="71456-115">Click outside the filter to automatically apply the filter to the review set.</span></span> <span data-ttu-id="71456-116">Lo screenshot seguente mostra il filtro Data configurato per visualizzare i documenti in un intervallo di date.</span><span class="sxs-lookup"><span data-stu-id="71456-116">The following screenshot shows the Date filter configured to show documents within a date range.</span></span>

![Filtro predefinito espanso](../media/ExpandedFilter.png)

## <a name="add-or-remove-filters"></a><span data-ttu-id="71456-118">Aggiungere o rimuovere filtri</span><span class="sxs-lookup"><span data-stu-id="71456-118">Add or remove filters</span></span>

<span data-ttu-id="71456-119">Per aggiungere o rimuovere i filtri visualizzati per il set di recensioni, selezionare **Filtri** per aprire il riquadro dei filtri, visualizzato in una pagina a comparsa.</span><span class="sxs-lookup"><span data-stu-id="71456-119">To add or remove filters that are displayed for the review set, select **Filters** to open the filter panel, which is displayed on a flyout page.</span></span> 

![Pannello filtro](../media/FilterPanel.png)

<span data-ttu-id="71456-121">I filtri disponibili sono organizzati in quattro sezioni:</span><span class="sxs-lookup"><span data-stu-id="71456-121">The available filters are organized in four sections:</span></span>

- <span data-ttu-id="71456-122">**Ricerca:** filtri che forniscono funzionalità di ricerca diverse.</span><span class="sxs-lookup"><span data-stu-id="71456-122">**Search**: Filters that provide different search capabilities.</span></span>

- <span data-ttu-id="71456-123">**Analisi &** codifica predittiva : Filtri per le proprietà generate e aggiunte ai documenti quando si esegue il processo analitico di document **& tramite posta** elettronica o si utilizzano modelli di codifica predittivi.</span><span class="sxs-lookup"><span data-stu-id="71456-123">**Analytics & predictive coding**: Filters for properties generated and added to documents when you run the **Document & email analytic** job or use predictive coding models.</span></span>

- <span data-ttu-id="71456-124">**ID: filtri** per tutte le proprietà ID dei documenti.</span><span class="sxs-lookup"><span data-stu-id="71456-124">**IDs**: Filters for all ID properties of documents.</span></span>

- <span data-ttu-id="71456-125">**Proprietà elemento**: Filtri per le proprietà del documento.</span><span class="sxs-lookup"><span data-stu-id="71456-125">**Item properties**: Filters for document properties.</span></span> 

<span data-ttu-id="71456-126">Espandi ogni sezione e seleziona o deseleziona i filtri per aggiungerli o rimuoverli nel set di filtri.</span><span class="sxs-lookup"><span data-stu-id="71456-126">Expand each section and select or deselect filters to add or remove them in the filter set.</span></span> <span data-ttu-id="71456-127">Quando si aggiunge un filtro, questo viene visualizzato nel set di filtri.</span><span class="sxs-lookup"><span data-stu-id="71456-127">When you add a filter, it's displayed in the filter set.</span></span> 

![Elenco delle sezioni e delle proprietà del filtro nel riquadro dei filtri](../media/FilterPanel2.png)

> [!NOTE]
> <span data-ttu-id="71456-129">Quando espandi una sezione nel riquadro dei filtri, noterai che sono selezionati i tipi di filtro predefiniti.</span><span class="sxs-lookup"><span data-stu-id="71456-129">When you expand a section in the filter panel, you'll notice that the default filter types are selected.</span></span> <span data-ttu-id="71456-130">Puoi mantenerle selezionate o deselezionarle e rimosse dal set di filtri.</span><span class="sxs-lookup"><span data-stu-id="71456-130">You can keep these selected or deselect them and removed them from the filter set.</span></span> 

## <a name="filter-types"></a><span data-ttu-id="71456-131">Tipi di filtro</span><span class="sxs-lookup"><span data-stu-id="71456-131">Filter types</span></span>

<span data-ttu-id="71456-132">Ogni campo ricercabile in un set di recensioni dispone di un filtro corrispondente che è possibile utilizzare per filtrare gli elementi in base a un campo specifico.</span><span class="sxs-lookup"><span data-stu-id="71456-132">Every searchable field in a review set has a corresponding filter that you can use for filter items based on a specific field.</span></span>

<span data-ttu-id="71456-133">Esistono più tipi di filtri:</span><span class="sxs-lookup"><span data-stu-id="71456-133">There are multiple types of filters:</span></span>

- <span data-ttu-id="71456-134">**Testo libero**: viene applicato un filtro a testo libero ai campi di testo, ad esempio "Subject".</span><span class="sxs-lookup"><span data-stu-id="71456-134">**Freetext**: A freetext filter is applied to text fields such as "Subject".</span></span> <span data-ttu-id="71456-135">È possibile elencare più termini di ricerca separandoli con una virgola.</span><span class="sxs-lookup"><span data-stu-id="71456-135">You can list multiple search terms by separating them with a comma.</span></span>

- <span data-ttu-id="71456-136">**Date**: viene utilizzato un filtro data per i campi data, ad esempio "Data ultima modifica".</span><span class="sxs-lookup"><span data-stu-id="71456-136">**Date**: A date filter is used for date fields such as "Last modified date".</span></span>

- <span data-ttu-id="71456-137">**Opzioni di** ricerca : un filtro delle opzioni di ricerca fornisce un elenco di valori possibili (ogni valore viene visualizzato con una casella di controllo che è possibile selezionare) per campi specifici nella revisione.</span><span class="sxs-lookup"><span data-stu-id="71456-137">**Search options**: A search options filter provides a list of possible values (each value is displayed with a checkbox that you can select) for particular fields in the review.</span></span> <span data-ttu-id="71456-138">Questo filtro viene utilizzato per i campi, ad esempio "Sender", in cui è presente un numero limitato di valori possibili nel set di revisione.</span><span class="sxs-lookup"><span data-stu-id="71456-138">This filter is used for fields, such as "Sender", where there is a finite number of possible values in the review set.</span></span>

- <span data-ttu-id="71456-139">**Parola** chiave: una condizione di parola chiave è un'istanza specifica della condizione a testo libero che è possibile utilizzare per cercare termini.</span><span class="sxs-lookup"><span data-stu-id="71456-139">**Keyword**: A keyword condition is a specific instance of freetext condition that you can use to search for terms.</span></span> <span data-ttu-id="71456-140">È inoltre possibile utilizzare un linguaggio di query simile a KQL in questo tipo di filtro.</span><span class="sxs-lookup"><span data-stu-id="71456-140">You can also use KQL-like query language in this type of filter.</span></span> <span data-ttu-id="71456-141">Per ulteriori informazioni, vedere le sezioni Linguaggio query e Generatore di query avanzato in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="71456-141">For more information, see the Query language and Advanced query builder sections in this topic.</span></span>

## <a name="include-and-exclude-filter-relationships"></a><span data-ttu-id="71456-142">Includere ed escludere relazioni filtro</span><span class="sxs-lookup"><span data-stu-id="71456-142">Include and exclude filter relationships</span></span>

<span data-ttu-id="71456-143">È possibile modificare la relazione di inclusione ed esclusione per un determinato filtro.</span><span class="sxs-lookup"><span data-stu-id="71456-143">You have the option to change the include and exclude relationship for a particular filter.</span></span> <span data-ttu-id="71456-144">Ad esempio, nel filtro Tag puoi escludere gli elementi contrassegnati  con un tag specifico selezionando Uguale a nessuno nel filtro a discesa.</span><span class="sxs-lookup"><span data-stu-id="71456-144">For example, in the Tag filter, you can exclude items that are tagged with a particular tag by selecting **Equals none of** in the dropdown filter.</span></span> 

![Escludi filtro tag](../media/TagFilterExclude.png)

## <a name="save-filters-as-queries"></a><span data-ttu-id="71456-146">Salvare i filtri come query</span><span class="sxs-lookup"><span data-stu-id="71456-146">Save filters as queries</span></span>

<span data-ttu-id="71456-147">Dopo aver soddisfatto i filtri, è possibile salvare la combinazione di filtri come query di filtro.</span><span class="sxs-lookup"><span data-stu-id="71456-147">After you are satisfied with your filters, you can save the filter combination as a filter query.</span></span> <span data-ttu-id="71456-148">In questo modo è possibile applicare il filtro nelle sessioni di revisione future.</span><span class="sxs-lookup"><span data-stu-id="71456-148">This lets you apply the filter in the future review sessions.</span></span>

<span data-ttu-id="71456-149">Per salvare un filtro, selezionare **Salva la query e** assegnare un nome.</span><span class="sxs-lookup"><span data-stu-id="71456-149">To save a filter, select **Save the query** and name it.</span></span> <span data-ttu-id="71456-150">È possibile eseguire query di filtro salvate  in precedenza selezionando l'elenco a discesa Query di filtro salvate e selezionando una query di filtro da applicare per esaminare i documenti impostati.</span><span class="sxs-lookup"><span data-stu-id="71456-150">You or other reviewers can run previously saved filter queries by selecting the **Saved filter queries** dropdown and selecting a filter query to apply to review set documents.</span></span> 

![Salvare una query di filtro](../media/SaveFilterQuery.png)

<span data-ttu-id="71456-152">Per eliminare una query di filtro, aprire il riquadro dei filtri e selezionare l'icona cestino accanto alla query.</span><span class="sxs-lookup"><span data-stu-id="71456-152">To delete a filter query, open the filter panel and select the trashcan icon next to the query.</span></span>

![Eliminare una query di filtro](../media/DeleteFilterQuery.png)

## <a name="query-language"></a><span data-ttu-id="71456-154">Linguaggio di query</span><span class="sxs-lookup"><span data-stu-id="71456-154">Query language</span></span>

<span data-ttu-id="71456-155">Oltre a utilizzare i filtri, è anche possibile utilizzare un linguaggio di query simile a KQL nel filtro Parole chiave per creare la query di ricerca del set di recensioni.</span><span class="sxs-lookup"><span data-stu-id="71456-155">In addition to using filters, you can also use a KQL-like query language in the Keywords filter to build your review set search query.</span></span> <span data-ttu-id="71456-156">Il linguaggio di query per le query di set di revisione supporta gli operatori Boolean standard, ad **esempio AND**, **OR**, **NOT** e **NEAR.**</span><span class="sxs-lookup"><span data-stu-id="71456-156">The query language for review set queries supports standard Boolean operators, such as **AND**, **OR**, **NOT**, and **NEAR**.</span></span> <span data-ttu-id="71456-157">Supporta inoltre un carattere jolly a carattere singolo (?) e un carattere jolly a più caratteri (\*).</span><span class="sxs-lookup"><span data-stu-id="71456-157">It also supports a single-character wildcard (?) and a multi-character wildcard (\*).</span></span>

## <a name="advanced-query-builder"></a><span data-ttu-id="71456-158">Generatore di query avanzato</span><span class="sxs-lookup"><span data-stu-id="71456-158">Advanced query builder</span></span>

<span data-ttu-id="71456-159">È inoltre possibile creare query più avanzate per cercare documenti in un set di revisioni.</span><span class="sxs-lookup"><span data-stu-id="71456-159">You can also build more advanced queries to search for documents in a review set.</span></span>

1. <span data-ttu-id="71456-160">Apri il pannello dei filtri, seleziona **Filtri** ed espandi la **sezione** Ricerca.</span><span class="sxs-lookup"><span data-stu-id="71456-160">Open the filter panel, select **Filters**, and expand the **Search** section.</span></span>

  ![Aggiungere un filtro KQL](../media/AddKQLFilter.png)

2. <span data-ttu-id="71456-162">Selezionare il **filtro KQL** e fare clic **su Apri generatore di query.**</span><span class="sxs-lookup"><span data-stu-id="71456-162">Select the **KQL** filter and click **Open query builder**.</span></span>

   <span data-ttu-id="71456-163">In questo pannello è possibile creare query KQL complesse utilizzando il generatore di query.</span><span class="sxs-lookup"><span data-stu-id="71456-163">In this panel, you can create complex KQL queries by using the query builder.</span></span> <span data-ttu-id="71456-164">È possibile aggiungere condizioni o gruppi di condizioni che sono costituito da più condizioni connesse logicamente da **relazioni AND** **o OR.**</span><span class="sxs-lookup"><span data-stu-id="71456-164">You can add conditions or add condition groups that are made up of multiple conditions that are logically connected by **AND** or **OR** relationships.</span></span>

   ![Utilizzare il generatore di query per configurare query di filtro complesse](../media/ComplexQuery.png)
