---
title: Applicare il filtro punteggio di previsione agli elementi in un set di recensioni
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
ms.reviewer: jefwan
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: Utilizzare un filtro del punteggio di previsione per visualizzare gli elementi che un modello di codifica predittivo prevede come pertinente o non pertinente.
ms.openlocfilehash: 0ca2770d5ccbcc3ea5f3dec8394f69d1f5117da5
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822528"
---
# <a name="apply-a-prediction-score-filter-to-a-review-set-preview"></a><span data-ttu-id="b70d4-103">Applicare un filtro punteggio di previsione a un set di recensioni (anteprima)</span><span class="sxs-lookup"><span data-stu-id="b70d4-103">Apply a prediction score filter to a review set (preview)</span></span>

<span data-ttu-id="b70d4-104">Dopo aver creato un modello di codifica predittivo in Advanced eDiscovery e averlo addestrato al punto in cui è stabile, è possibile applicare il filtro del punteggio di previsione per visualizzare gli elementi del set di revisione che il modello ha determinato siano pertinenti (o non pertinenti).</span><span class="sxs-lookup"><span data-stu-id="b70d4-104">After you create a predictive coding model in Advanced eDiscovery and train it to the point where it's stable, you can apply the prediction score filter to display review set items that the model has determined are relevant (or not relevant).</span></span> <span data-ttu-id="b70d4-105">Quando si crea un modello, viene creato anche un filtro del punteggio di previsione corrispondente.</span><span class="sxs-lookup"><span data-stu-id="b70d4-105">When you create a model, a corresponding prediction score filter is also created.</span></span> <span data-ttu-id="b70d4-106">È possibile utilizzare questo filtro per visualizzare gli elementi assegnati a un punteggio di previsione all'interno di un intervallo specificato.</span><span class="sxs-lookup"><span data-stu-id="b70d4-106">You can use this filter to display items assigned a prediction score within a specified range.</span></span> <span data-ttu-id="b70d4-107">In generale, i punteggi di stima compresi tra **0** e **0,5** vengono assegnati agli elementi previsti dal modello non sono rilevanti.</span><span class="sxs-lookup"><span data-stu-id="b70d4-107">In general, prediction scores between **0** and **.5** are assigned to items that model has predicted are not relevant.</span></span> <span data-ttu-id="b70d4-108">Gli elementi assegnati ai punteggi di previsione **compresi tra 0,5** e **1,0** sono elementi pertinenti previsti dal modello.</span><span class="sxs-lookup"><span data-stu-id="b70d4-108">Items assigned prediction scores between **.5** and **1.0** are items the model has predicted are relevant.</span></span>

<span data-ttu-id="b70d4-109">Ecco due modi per usare il filtro del punteggio di previsione:</span><span class="sxs-lookup"><span data-stu-id="b70d4-109">Here are two ways you can use the prediction score filter:</span></span>

- <span data-ttu-id="b70d4-110">Definire la priorità della revisione degli elementi in un set di revisione previsto dal modello sono rilevanti.</span><span class="sxs-lookup"><span data-stu-id="b70d4-110">Prioritize the review of items in a review set that the model has predicted are relevant.</span></span>

- <span data-ttu-id="b70d4-111">Gli elementi del set di revisione previsti dal modello non sono rilevanti.</span><span class="sxs-lookup"><span data-stu-id="b70d4-111">Cull items from the review set that the model has predicted are not relevant.</span></span> <span data-ttu-id="b70d4-112">In alternativa, è possibile utilizzare il filtro del punteggio di previsione per de-definire la priorità per la revisione degli elementi non rilevanti.</span><span class="sxs-lookup"><span data-stu-id="b70d4-112">Alternative, you can use the prediction score filter to de-prioritize the review of non-relevant items.</span></span>

## <a name="before-you-apply-a-prediction-score-filter"></a><span data-ttu-id="b70d4-113">Prima di applicare un filtro punteggio di previsione</span><span class="sxs-lookup"><span data-stu-id="b70d4-113">Before you apply a prediction score filter</span></span>

- <span data-ttu-id="b70d4-114">Creare un modello di codifica predittiva in modo che sia creato un filtro punteggio di previsione corrispondente.</span><span class="sxs-lookup"><span data-stu-id="b70d4-114">Create a predictive coding model so that a corresponding prediction score filter is created.</span></span>

- <span data-ttu-id="b70d4-115">È possibile applicare un filtro punteggio di previsione dopo uno qualsiasi dei round di training.</span><span class="sxs-lookup"><span data-stu-id="b70d4-115">You can apply a prediction score filter after any of the training rounds.</span></span> <span data-ttu-id="b70d4-116">Tuttavia, potresti voler attendere dopo aver eseguito diversi round o finché il modello non è stabile prima di usare il filtro del punteggio di previsione.</span><span class="sxs-lookup"><span data-stu-id="b70d4-116">But you may want to wait after performing several rounds or until the model is stable before using the prediction score filter.</span></span>

## <a name="apply-a-prediction-score-filter"></a><span data-ttu-id="b70d4-117">Applicare un filtro del punteggio di previsione</span><span class="sxs-lookup"><span data-stu-id="b70d4-117">Apply a prediction score filter</span></span>

1. <span data-ttu-id="b70d4-118">Nel Centro Microsoft 365 conformità aprire il caso Advanced eDiscovery, selezionare la scheda **Set di** revisioni e quindi aprire il set di recensioni.</span><span class="sxs-lookup"><span data-stu-id="b70d4-118">In the Microsoft 365 compliance center, open the Advanced eDiscovery case, select the **Review sets** tab, and then open the review set.</span></span>

   ![Fare clic su Filtri per visualizzare la pagina a comparsa Filtri](..\media\PredictionScoreFilter0.png)   

   <span data-ttu-id="b70d4-120">I filtri predefiniti precaricati vengono visualizzati nella parte superiore della pagina del set di recensioni.</span><span class="sxs-lookup"><span data-stu-id="b70d4-120">The pre-loaded default filters are displayed at the top of the review set page.</span></span> <span data-ttu-id="b70d4-121">È possibile lasciare questa impostazione su **Any**.</span><span class="sxs-lookup"><span data-stu-id="b70d4-121">You can leave these set to **Any**.</span></span>

2. <span data-ttu-id="b70d4-122">Fare **clic su** Filtri per visualizzare la pagina **a** comparsa Filtri.</span><span class="sxs-lookup"><span data-stu-id="b70d4-122">Click **Filters** to display the **Filters** flyout page.</span></span>

3. <span data-ttu-id="b70d4-123">Espandi la **sezione Analisi & codifica predittiva** per visualizzare un set di filtri.</span><span class="sxs-lookup"><span data-stu-id="b70d4-123">Expand the **Analytics & predictive coding** section to display a set of filters.</span></span>

      ![Filtro punteggio di previsione nella sezione Analisi & codifica predittiva](..\media\PredictionScoreFilter1.png)

   <span data-ttu-id="b70d4-125">La convenzione di denominazione per i filtri del punteggio di previsione è **Punteggio di previsione (nome modello).**</span><span class="sxs-lookup"><span data-stu-id="b70d4-125">The naming convention for prediction score filters is **Prediction score (model name)**.</span></span> <span data-ttu-id="b70d4-126">Ad esempio, il nome del filtro del punteggio di previsione per un modello denominato **Modello A** è Punteggio di **previsione (modello A).**</span><span class="sxs-lookup"><span data-stu-id="b70d4-126">For example, the prediction score filter name for a model named **Model A** is **Prediction score (Model A)**.</span></span>

4. <span data-ttu-id="b70d4-127">Selezionare il filtro del punteggio di previsione che si desidera utilizzare e quindi fare clic su **Fine.**</span><span class="sxs-lookup"><span data-stu-id="b70d4-127">Select the prediction score filter that you want to use and then click **Done**.</span></span>

5. <span data-ttu-id="b70d4-128">Nella pagina del set di recensioni, fare clic sull'elenco a discesa per il filtro del punteggio di previsione e digitare i valori minimo e massimo per l'intervallo di punteggio di previsione.</span><span class="sxs-lookup"><span data-stu-id="b70d4-128">On the review set page, click the dropdown for the prediction score filter and type minimum and maximum values for the prediction score range.</span></span> <span data-ttu-id="b70d4-129">Ad esempio, lo screenshot seguente mostra un intervallo di punteggio di previsione compreso tra **0,5** e **1,0.**</span><span class="sxs-lookup"><span data-stu-id="b70d4-129">For example, the following screenshot shows a prediction score range between **.5** and **1.0**.</span></span>

   ![Valori minimi e massimi per il filtro del punteggio di previsione](..\media\PredictionScoreFilter2.png)

6. <span data-ttu-id="b70d4-131">Fare clic all'esterno del filtro per applicare automaticamente il filtro al set di revisioni.</span><span class="sxs-lookup"><span data-stu-id="b70d4-131">Click outside the filter to automatically apply the filter to the review set.</span></span>

  <span data-ttu-id="b70d4-132">Nella pagina del set di revisioni viene visualizzato un elenco di documenti con un punteggio di previsione compreso nell'intervallo specificato.</span><span class="sxs-lookup"><span data-stu-id="b70d4-132">A list of documents with a prediction score within the range you specified is displayed on the review set page.</span></span> 

  > [!TIP]
  > <span data-ttu-id="b70d4-133">Per visualizzare il punteggio di previsione effettivo assegnato a un documento, è possibile fare clic sulla **scheda Metadati** nel riquadro di lettura.</span><span class="sxs-lookup"><span data-stu-id="b70d4-133">To view the actual prediction score assign to a document, you can click the **Metadata** tab in the reading pane.</span></span> <span data-ttu-id="b70d4-134">I punteggi di stima per tutti i modelli nel set di revisione vengono visualizzati nella proprietà dei metadati **RelevanceScores.**</span><span class="sxs-lookup"><span data-stu-id="b70d4-134">The prediction scores for all models in the review set are displayed in the **RelevanceScores** metadata property.</span></span>

## <a name="more-information"></a><span data-ttu-id="b70d4-135">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="b70d4-135">More information</span></span>

- <span data-ttu-id="b70d4-136">Per ulteriori informazioni sull'utilizzo dei filtri, vedere [Query and filter content in a review set](review-set-search.md).</span><span class="sxs-lookup"><span data-stu-id="b70d4-136">For more information about using filters, see [Query and filter content in a review set](review-set-search.md).</span></span>
