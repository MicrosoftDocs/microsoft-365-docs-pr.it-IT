---
title: Dashboard avanzato di eDiscovery per i set di Revisione
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
description: ''
ms.openlocfilehash: 127e2c9a04977bf6e902a1ce669fa9e4248e3ef2
ms.sourcegitcommit: 2913fd74ad5086c7cac6388447285be9aa5a8e44
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2020
ms.locfileid: "41662230"
---
# <a name="advanced-ediscovery-dashboard-for-review-sets-preview"></a><span data-ttu-id="d3d91-102">Dashboard avanzato di eDiscovery per i set di riesami (anteprima)</span><span class="sxs-lookup"><span data-stu-id="d3d91-102">Advanced eDiscovery dashboard for review sets (preview)</span></span>

<span data-ttu-id="d3d91-103">Per alcuni casi in Advanced eDiscovery, è possibile che si disponga di un volume elevato di documenti e messaggi di posta elettronica che devono essere esaminati.</span><span class="sxs-lookup"><span data-stu-id="d3d91-103">For some cases in Advanced eDiscovery, you may have a large volume of documents and email messages that need to be reviewed.</span></span> <span data-ttu-id="d3d91-104">Prima di avviare il processo di revisione, è consigliabile analizzare rapidamente il corpus per identificare le tendenze o le statistiche chiave che consentono di sviluppare la strategia di revisione.</span><span class="sxs-lookup"><span data-stu-id="d3d91-104">Before you start the review process, you may want to quickly analyze your corpus to identify trends or key statistics that will help you develop your review strategy.</span></span> <span data-ttu-id="d3d91-105">A tale scopo, è possibile utilizzare il dashboard Advanced eDiscovery per i set di revisione per analizzare rapidamente il corpo.</span><span class="sxs-lookup"><span data-stu-id="d3d91-105">To do this, you can use the Advanced eDiscovery dashboard for review sets to quickly analyze your corpus.</span></span>

## <a name="step-1-create-a-widget-on-the-review-set-dashboard"></a><span data-ttu-id="d3d91-106">Passaggio 1: creare un widget nel dashboard del set di recensioni</span><span class="sxs-lookup"><span data-stu-id="d3d91-106">Step 1: Create a widget on the review set dashboard</span></span>

1. <span data-ttu-id="d3d91-107">Nel centro sicurezza & conformità, accedere a **eDiscovery > Advanced eDiscovery** per visualizzare l'elenco dei casi nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d3d91-107">In the Security & Compliance Center, go to **eDiscovery > Advanced eDiscovery** to display the list of cases in your organization.</span></span>
  
2. <span data-ttu-id="d3d91-108">Selezionare un caso esistente.</span><span class="sxs-lookup"><span data-stu-id="d3d91-108">Select an existing case.</span></span>
  
3. <span data-ttu-id="d3d91-109">Fare clic sulla scheda **Revisione set** e quindi selezionare un set di revisione.</span><span class="sxs-lookup"><span data-stu-id="d3d91-109">Click the **Review Set** tab, and then select a review set.</span></span>
  
4. <span data-ttu-id="d3d91-110">Nell'elenco a discesa **singoli risultati** fare clic su **visualizzazione profilo di ricerca**.</span><span class="sxs-lookup"><span data-stu-id="d3d91-110">In the **Individual results** dropdown list, click **Search profile view**.</span></span> 

   ![DashbordPivot](media/dashboardpivot.png)

   <span data-ttu-id="d3d91-112">Viene visualizzata la pagina **visualizzazione profilo di ricerca** . la prima volta che si visualizza questa pagina, vengono visualizzati tre widget predefiniti.</span><span class="sxs-lookup"><span data-stu-id="d3d91-112">The **Search profile view** page is displayed; the first time you display this page, three default widgets are displayed.</span></span>

   ![Dashboard](media/dashboardonly.png)
  
5. <span data-ttu-id="d3d91-114">Fare clic sul **nuovo widget** e quindi selezionare uno degli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="d3d91-114">Click the **New  widget** and then select one of the following items:</span></span>

   ![Nuovo elenco a discesa widget](media/NewWidgetDropdownBox.png)

   - <span data-ttu-id="d3d91-116">**Scegliere dalla raccolta:** Visualizza una raccolta predefinita di widget.</span><span class="sxs-lookup"><span data-stu-id="d3d91-116">**Choose from library:** Displays a default library of widgets.</span></span> <span data-ttu-id="d3d91-117">Si fa clic su un widget e quindi si fa clic su **Aggiungi** per aggiungerlo ai widget nella pagina **visualizzazione profilo di ricerca** .</span><span class="sxs-lookup"><span data-stu-id="d3d91-117">You click a widget and then click **Add** to add it to the widgets on the **Search profile view** page.</span></span>
  
   - <span data-ttu-id="d3d91-118">**Creare widget personalizzato:** Visualizza una pagina a comparsa che è possibile utilizzare per configurare un widget personalizzato.</span><span class="sxs-lookup"><span data-stu-id="d3d91-118">**Create custom widget:** Displays a flyout page that you can use to set up a custom widget.</span></span> 

6. <span data-ttu-id="d3d91-119">Per creare un widget personalizzato, fare quanto segue nella pagina Aggiungi riquadro a comparsa **del widget** :</span><span class="sxs-lookup"><span data-stu-id="d3d91-119">To create a custom widget, do the following on the **Add widget** flyout page:</span></span>

   ![Creare widget](media/addwidget.png)

    <span data-ttu-id="d3d91-121">a.</span><span class="sxs-lookup"><span data-stu-id="d3d91-121">a.</span></span> <span data-ttu-id="d3d91-122">Digitare un nome per il widget, visualizzato nella barra del titolo del widget.</span><span class="sxs-lookup"><span data-stu-id="d3d91-122">Type a name for the widget, which is displayed in the widget title bar.</span></span> <span data-ttu-id="d3d91-123">È necessario denominare un widget, ma è utile identificare i dati del widget.</span><span class="sxs-lookup"><span data-stu-id="d3d91-123">Naming a widget is required, but it's helpful to identify the widget data.</span></span>

    <span data-ttu-id="d3d91-124">b.</span><span class="sxs-lookup"><span data-stu-id="d3d91-124">b.</span></span> <span data-ttu-id="d3d91-125">Selezionare una proprietà nell'elenco a discesa **Scegli pivot** che verrà utilizzato per i dati del widget.</span><span class="sxs-lookup"><span data-stu-id="d3d91-125">Select a property in the **Choose pivot** dropdown list that will be used for the widget data.</span></span> <span data-ttu-id="d3d91-126">Gli elementi di questo elenco sono le proprietà ricercabili per gli elementi del set di revisione.</span><span class="sxs-lookup"><span data-stu-id="d3d91-126">The items in this list are the searchable properties for the items in the review set.</span></span> <span data-ttu-id="d3d91-127">Per una descrizione di queste proprietà, vedere [Document Metadata Fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span><span class="sxs-lookup"><span data-stu-id="d3d91-127">For a description of these properties, see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span></span> <span data-ttu-id="d3d91-128">Le opzioni di pivot per il widget sono elencate nella colonna **nome campo ricercabile** in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="d3d91-128">The pivot options for the widget are listed in the **Searchable field name** column in this topic.</span></span>

    <span data-ttu-id="d3d91-129">c.</span><span class="sxs-lookup"><span data-stu-id="d3d91-129">c.</span></span> <span data-ttu-id="d3d91-130">Selezionare un tipo di grafico per visualizzare i dati dalla proprietà pivot selezionata.</span><span class="sxs-lookup"><span data-stu-id="d3d91-130">Select a chart type to display the data from the selected pivot property.</span></span>

  6. <span data-ttu-id="d3d91-131">Fare clic su **Aggiungi** per creare il widget personalizzato e visualizzarlo nella pagina **visualizzazione profilo di ricerca** .</span><span class="sxs-lookup"><span data-stu-id="d3d91-131">Click **Add** to create the custom widget and display it on the **Search profile view** page.</span></span>

## <a name="step-2-create-a-review-set-search-query"></a><span data-ttu-id="d3d91-132">Passaggio 2: creare una query di ricerca set di Revisione</span><span class="sxs-lookup"><span data-stu-id="d3d91-132">Step 2: Create a review set search query</span></span>

1. <span data-ttu-id="d3d91-133">Fare clic su **...** nella barra del titolo del widget, quindi fare clic su **applica condizione**.</span><span class="sxs-lookup"><span data-stu-id="d3d91-133">Click **...** in the widget title bar, and then click **Apply condition**.</span></span>

   ![Dashboard](media/searchprofilehome.png)

2. <span data-ttu-id="d3d91-135">Nella pagina del riquadro a comparsa, fare clic su un elemento nel tasto widget o nel grafico widget per creare un filtro.</span><span class="sxs-lookup"><span data-stu-id="d3d91-135">On the flyout page, click an element on the widget key or widget chart to create a filter.</span></span>

   ![CreateFilter](media/applyconditionfilter.png)

3. <span data-ttu-id="d3d91-137">Ripetere i passaggi 1-2 per altri widget.</span><span class="sxs-lookup"><span data-stu-id="d3d91-137">Repeat steps 1-2 for other widgets multiple widgets.</span></span> 

4. <span data-ttu-id="d3d91-138">Al termine, fare clic su **Salva con nome** per salvare le condizioni come una nuova query di ricerca per il set di revisione.</span><span class="sxs-lookup"><span data-stu-id="d3d91-138">When you're done, click **Save as query** to save your conditions as a new search query for the review set.</span></span>

   ![Query](media/savequery.png)

5. <span data-ttu-id="d3d91-140">Chiudere la **visualizzazione del profilo di ricerca** per tornare alla visualizzazione dei risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="d3d91-140">Close the **Search profile view** to return to the search results view.</span></span>

   <span data-ttu-id="d3d91-141">Se sono stati creati filtri visivi, la query risultante viene applicata ai risultati della ricerca visualizzati e la query di ricerca salvata nel passaggio 4 viene visualizzata sotto **query salvate**.</span><span class="sxs-lookup"><span data-stu-id="d3d91-141">If you have created any visual filters, the resulting query is applied to the search results that are displayed, and the search query that you saved in step 4 is displayed under **Saved queries**.</span></span> <span data-ttu-id="d3d91-142">Per ulteriori informazioni sulle query dei set di revisione, vedere [query the data in a Review set](review-set-search.md).</span><span class="sxs-lookup"><span data-stu-id="d3d91-142">For more information about review set queries, see [Query the data in a review set](review-set-search.md).</span></span>
