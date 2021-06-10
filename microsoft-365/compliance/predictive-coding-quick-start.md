---
title: Codifica predittiva in Advanced eDiscovery - Guida introduttiva
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
description: Informazioni su come iniziare a usare il modulo di codifica predittiva in Advanced eDiscovery. In questo articolo viene descritto il processo end-to-end relativo all'utilizzo della codifica predittiva per identificare il contenuto in un set di recensioni più rilevante per l'indagine.
ms.openlocfilehash: 16fb92af5048ae6cd953e522b2e5e5d8f5a7256f
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822560"
---
# <a name="quick-start-predictive-coding-in-advanced-ediscovery-preview"></a><span data-ttu-id="80451-104">Guida introduttiva: codifica predittiva in Advanced eDiscovery (anteprima)</span><span class="sxs-lookup"><span data-stu-id="80451-104">Quick start: Predictive coding in Advanced eDiscovery (preview)</span></span>

<span data-ttu-id="80451-105">In questo articolo viene presentata una guida introduttiva all'uso della codifica predittiva in Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="80451-105">This article presents a quick start for using predictive coding in Advanced eDiscovery.</span></span> <span data-ttu-id="80451-106">Il modulo di codifica predittivo in Advanced eDiscovery utilizza le funzionalità intelligenti di machine learning in Advanced eDiscovery per ridurre la quantità di contenuto da esaminare.</span><span class="sxs-lookup"><span data-stu-id="80451-106">The predictive coding module in Advanced eDiscovery uses the intelligent, machine learning capabilities in Advanced eDiscovery to help you reduce the amount of content to review.</span></span> <span data-ttu-id="80451-107">La codifica predittiva consente di ridurre e ridurre grandi volumi di contenuto del caso a un set pertinente di elementi di cui è possibile definire la priorità per la revisione.</span><span class="sxs-lookup"><span data-stu-id="80451-107">Predictive coding helps you reduce and cull large volumes of case content to a relevant set of items that you can prioritize for review.</span></span> <span data-ttu-id="80451-108">Questa operazione viene eseguita creando e formando i propri modelli di codifica predittivi che consentono di definire la priorità della revisione degli elementi più rilevanti in un set di recensioni.</span><span class="sxs-lookup"><span data-stu-id="80451-108">This is accomplished by creating and training your own predictive coding models that help you prioritize the review of the most relevant items in a review set.</span></span>

<span data-ttu-id="80451-109">Ecco una breve panoramica del processo di codifica predittiva:</span><span class="sxs-lookup"><span data-stu-id="80451-109">Here's an a quick overview of the predictive coding process:</span></span>

![Processo di avvio rapido per la codifica di previsione](..\media\PredictiveCodingQuickStartProcess.png)

<span data-ttu-id="80451-111">Per iniziare, crea un modello e etichetta fino a 50 elementi come pertinenti o non rilevanti.</span><span class="sxs-lookup"><span data-stu-id="80451-111">To get started, you create a model, label as few as 50 items as relevant or not relevant.</span></span> <span data-ttu-id="80451-112">Il sistema usa quindi questo training per applicare i punteggi di previsione a ogni elemento del set di recensioni.</span><span class="sxs-lookup"><span data-stu-id="80451-112">The system then uses this training to apply prediction scores to every item in the review set.</span></span> <span data-ttu-id="80451-113">In questo modo puoi filtrare gli elementi in base al punteggio di previsione, che ti consente di esaminare prima gli elementi più pertinenti (o non rilevanti).</span><span class="sxs-lookup"><span data-stu-id="80451-113">This lets you filter items based on the prediction score, which  allows you to review the most relevant (or non-relevant) items first.</span></span> <span data-ttu-id="80451-114">Se si desidera eseguire il training di modelli con livelli di attribuzione e frequenza di richiamo più elevati, è possibile continuare a etichettare gli elementi nei round di training successivi fino a quando il modello non si stabilizza.</span><span class="sxs-lookup"><span data-stu-id="80451-114">If you want to train models with higher accuracies and recall rates, you can continue labeling items in subsequent training rounds until the model stabilizes.</span></span> <span data-ttu-id="80451-115">Una volta stabilizzato il modello, è possibile applicare il filtro di stima finale per definire la priorità degli elementi da esaminare.</span><span class="sxs-lookup"><span data-stu-id="80451-115">Once the model is stabilized, you can apply the final prediction filter to prioritize items to review.</span></span>

<span data-ttu-id="80451-116">Per una panoramica dettagliata della codifica predittiva, vedere Informazioni sulla codifica [predittiva in Advanced eDiscovery](predictive-coding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="80451-116">For a detailed overview of predictive coding, see [Learn about predictive coding in Advanced eDiscovery](predictive-coding-overview.md).</span></span>

## <a name="step-1-create-a-new-predictive-coding-model"></a><span data-ttu-id="80451-117">Passaggio 1: Creare un nuovo modello di codifica predittiva</span><span class="sxs-lookup"><span data-stu-id="80451-117">Step 1: Create a new predictive coding model</span></span>

<span data-ttu-id="80451-118">Il primo passaggio consiste nel creare un nuovo modello di codifica predittiva nel set di revisioni</span><span class="sxs-lookup"><span data-stu-id="80451-118">The first step is to create a new predictive coding model in the review set</span></span>

1. <span data-ttu-id="80451-119">Nel Centro Microsoft 365 conformità aprire un caso Advanced eDiscovery e quindi selezionare la **scheda Revisione set.**</span><span class="sxs-lookup"><span data-stu-id="80451-119">In the Microsoft 365 compliance center, open an Advanced eDiscovery case and then select the **Review sets** tab.</span></span>

2. <span data-ttu-id="80451-120">Apri un set di recensioni e quindi fai clic su **Analisi**  >  **Gestisci codifica predittiva (anteprima)**.</span><span class="sxs-lookup"><span data-stu-id="80451-120">Open a review set and then click **Analytics** > **Manage predictive coding (preview)**.</span></span>

   ![Fai clic sul menu a discesa Analizza nel set di recensioni per passare alla pagina Codifica predittiva](..\media\ManagePredictiveCoding.png)

3. <span data-ttu-id="80451-122">Nella pagina **Modelli di codifica predittiva (anteprima)** fare clic su **Nuovo modello.**</span><span class="sxs-lookup"><span data-stu-id="80451-122">On the **Predictive coding models (preview)** page, click **New model**.</span></span>

4. <span data-ttu-id="80451-123">Nella pagina a comparsa digitare un nome per il modello e una descrizione facoltativa.</span><span class="sxs-lookup"><span data-stu-id="80451-123">On the flyout page, type a name for the model and an optional description.</span></span>

5. <span data-ttu-id="80451-124">Fare **clic su** Salva per creare il modello.</span><span class="sxs-lookup"><span data-stu-id="80451-124">Click **Save** to create the model.</span></span>

   <span data-ttu-id="80451-125">Il sistema predisporrà il modello in un paio di minuti.</span><span class="sxs-lookup"><span data-stu-id="80451-125">It will take a couple minutes for the system to prepare your model.</span></span> <span data-ttu-id="80451-126">Una volta pronto, è possibile eseguire il primo ciclo di formazione.</span><span class="sxs-lookup"><span data-stu-id="80451-126">After it's ready, you can perform the first round of training.</span></span>

<span data-ttu-id="80451-127">Per istruzioni più dettagliate, vedere [Create a predictive coding model](predictive-coding-create-model.md).</span><span class="sxs-lookup"><span data-stu-id="80451-127">For more detailed instructions, see [Create a predictive coding model](predictive-coding-create-model.md).</span></span>

## <a name="step-2-perform-the-first-training-round"></a><span data-ttu-id="80451-128">Passaggio 2: Eseguire il primo round di formazione</span><span class="sxs-lookup"><span data-stu-id="80451-128">Step 2: Perform the first training round</span></span>

<span data-ttu-id="80451-129">Dopo aver creato il modello, il passaggio successivo consiste nel completare il primo ciclo di training etichettando gli elementi come rilevanti o non rilevanti.</span><span class="sxs-lookup"><span data-stu-id="80451-129">After you create the model, the next step is to complete the first training round by labeling items as relevant or not relevant.</span></span>

1. <span data-ttu-id="80451-130">Apri il set di revisione e quindi fai **clic** su Analisi  >  **Gestisci codifica predittiva (anteprima).**</span><span class="sxs-lookup"><span data-stu-id="80451-130">Open the review set and then click **Analytics** > **Manage predictive coding (preview)**.</span></span>

2. <span data-ttu-id="80451-131">Nella pagina **Modelli di codifica predittiva (anteprima)** selezionare il modello di cui si desidera eseguire il training.</span><span class="sxs-lookup"><span data-stu-id="80451-131">On the **Predictive coding models (preview)** page, select the model that you want to train.</span></span>

3. <span data-ttu-id="80451-132">Nella scheda **Panoramica,** in **Round 1,** fare clic **su Avvia il round di formazione successivo.**</span><span class="sxs-lookup"><span data-stu-id="80451-132">On the **Overview** tab, under **Round 1**, click **Start next training round**.</span></span>

   <span data-ttu-id="80451-133">Viene **visualizzata** la scheda Formazione che contiene 50 elementi da etichettare.</span><span class="sxs-lookup"><span data-stu-id="80451-133">The **Training** tab is displayed and contains 50 items for you to label.</span></span>

4. <span data-ttu-id="80451-134">Esaminare ogni documento e quindi selezionare il **pulsante Rilevante** o **Non** rilevante nella parte inferiore del riquadro di lettura per etichettarlo.</span><span class="sxs-lookup"><span data-stu-id="80451-134">Review each document and then select the **Relevant** or **Not relevant** button at the bottom of the reading pane to label it.</span></span>

   ![Etichettare ogni documento come rilevante o non pertinente](..\media\TrainModel1.png)

5. <span data-ttu-id="80451-136">Dopo aver etichettato tutti i 50 elementi, fare clic su **Fine.**</span><span class="sxs-lookup"><span data-stu-id="80451-136">After you've labeled all 50 items, click **Finish**.</span></span>

    <span data-ttu-id="80451-137">Il sistema avrà un paio di minuti per "imparare" dall'etichettatura e aggiornare il modello.</span><span class="sxs-lookup"><span data-stu-id="80451-137">It will take a couple minutes for the system to "learn" from your labeling and update the model.</span></span> <span data-ttu-id="80451-138">Al termine di questo processo, viene visualizzato lo stato **Pronto** per il modello nella pagina Modelli di codifica predittiva **(anteprima).**</span><span class="sxs-lookup"><span data-stu-id="80451-138">When this process is complete, a status of **Ready** is displayed for the model on the **Predictive coding models (preview)** page.</span></span>

<span data-ttu-id="80451-139">Per istruzioni più dettagliate, vedere [Training a predictive coding model](predictive-coding-train-model.md).</span><span class="sxs-lookup"><span data-stu-id="80451-139">For more detailed instructions, see [Train a predictive coding model](predictive-coding-train-model.md).</span></span>

## <a name="step-3-apply-the-prediction-score-filter-to-items-in-review-set"></a><span data-ttu-id="80451-140">Passaggio 3: Applicare il filtro del punteggio di previsione agli elementi nel set di revisione</span><span class="sxs-lookup"><span data-stu-id="80451-140">Step 3: Apply the prediction score filter to items in review set</span></span>

<span data-ttu-id="80451-141">Dopo aver eseguito al momento del lease un round di training, è possibile applicare il filtro del punteggio di previsione agli elementi nel set di revisione.</span><span class="sxs-lookup"><span data-stu-id="80451-141">After you perform at lease one training round, you can apply the prediction score filter to items in review set.</span></span> <span data-ttu-id="80451-142">In questo modo è possibile esaminare gli elementi previsti dal modello come rilevanti o non pertinenti.</span><span class="sxs-lookup"><span data-stu-id="80451-142">This lets you review the items the model has predicted as relevant or not relevant.</span></span>   

1. <span data-ttu-id="80451-143">Apri il set di recensioni.</span><span class="sxs-lookup"><span data-stu-id="80451-143">Open the review set.</span></span>

   ![Fare clic su Filtri per visualizzare la pagina a comparsa Filtri](..\media\PredictionScoreFilter0.png)

   <span data-ttu-id="80451-145">I filtri predefiniti precaricati vengono visualizzati nella parte superiore della pagina del set di recensioni.</span><span class="sxs-lookup"><span data-stu-id="80451-145">The pre-loaded default filters are displayed at the top of the review set page.</span></span> <span data-ttu-id="80451-146">È possibile lasciare questa impostazione su **Any**.</span><span class="sxs-lookup"><span data-stu-id="80451-146">You can leave these set to **Any**.</span></span>

2. <span data-ttu-id="80451-147">Fare **clic su** Filtri per visualizzare la pagina **a** comparsa Filtri.</span><span class="sxs-lookup"><span data-stu-id="80451-147">Click **Filters** to display the **Filters** flyout page.</span></span>

3. <span data-ttu-id="80451-148">Espandi la **sezione Analisi & codifica predittiva** per visualizzare un set di filtri.</span><span class="sxs-lookup"><span data-stu-id="80451-148">Expand the **Analytics & predictive coding** section to display a set of filters.</span></span>

      ![Filtro punteggio di previsione nella sezione Analisi & codifica predittiva](..\media\PredictionScoreFilter1.png)

   <span data-ttu-id="80451-150">La convenzione di denominazione per i filtri del punteggio di previsione è **Punteggio di previsione (nome modello).**</span><span class="sxs-lookup"><span data-stu-id="80451-150">The naming convention for prediction score filters is **Prediction score (model name)**.</span></span> <span data-ttu-id="80451-151">Ad esempio, il nome del filtro del punteggio di previsione per un modello denominato **Modello A** è Punteggio di **previsione (modello A).**</span><span class="sxs-lookup"><span data-stu-id="80451-151">For example, the prediction score filter name for a model named **Model A** is **Prediction score (Model A)**.</span></span>

4. <span data-ttu-id="80451-152">Selezionare il filtro del punteggio di previsione che si desidera utilizzare e quindi fare clic su **Fine.**</span><span class="sxs-lookup"><span data-stu-id="80451-152">Select the prediction score filter that you want to use and then click **Done**.</span></span>

5. <span data-ttu-id="80451-153">Nella pagina del set di recensioni, fare clic sull'elenco a discesa per il filtro del punteggio di previsione e digitare i valori minimo e massimo per l'intervallo di punteggio di previsione.</span><span class="sxs-lookup"><span data-stu-id="80451-153">On the review set page, click the dropdown for the prediction score filter and type minimum and maximum values for the prediction score range.</span></span> <span data-ttu-id="80451-154">Ad esempio, lo screenshot seguente mostra un intervallo di punteggio di previsione compreso tra **0,5** e **1,0.**</span><span class="sxs-lookup"><span data-stu-id="80451-154">For example, the following screenshot shows a prediction score range between **.5** and **1.0**.</span></span>

   ![Valori minimi e massimi per il filtro del punteggio di previsione](..\media\PredictionScoreFilter2.png)

6. <span data-ttu-id="80451-156">Fare clic all'esterno del filtro per applicare automaticamente il filtro al set di revisioni.</span><span class="sxs-lookup"><span data-stu-id="80451-156">Click outside the filter to automatically apply the filter to the review set.</span></span>

  <span data-ttu-id="80451-157">Nella pagina del set di revisioni viene visualizzato un elenco di documenti con un punteggio di previsione compreso nell'intervallo specificato.</span><span class="sxs-lookup"><span data-stu-id="80451-157">A list of documents with a prediction score within the range you specified is displayed on the review set page.</span></span>

<span data-ttu-id="80451-158">Per istruzioni più dettagliate, vedere [Apply a prediction filter to a review set](predictive-coding-apply-prediction-filter.md).</span><span class="sxs-lookup"><span data-stu-id="80451-158">For more detailed instructions, see [Apply a prediction filter to a review set](predictive-coding-apply-prediction-filter.md).</span></span>

## <a name="step-4-perform-more-training-rounds"></a><span data-ttu-id="80451-159">Passaggio 4: Eseguire più round di formazione</span><span class="sxs-lookup"><span data-stu-id="80451-159">Step 4: Perform more training rounds</span></span>

<span data-ttu-id="80451-160">Più che probabile, dovrai eseguire più round di formazione per formare il modulo per prevedere meglio gli elementi pertinenti e non rilevanti nel set di recensioni.</span><span class="sxs-lookup"><span data-stu-id="80451-160">More than likely, you'll have to perform more training rounds to train the module to better predict relevant and non-relevant items in the review set.</span></span> <span data-ttu-id="80451-161">In generale, il modello verrà addestrato abbastanza volte fino a quando non si stabilizzerà abbastanza per soddisfare i requisiti.</span><span class="sxs-lookup"><span data-stu-id="80451-161">In general, you'll train the model enough times until it stabilizes enough to meet your requirements.</span></span>

<span data-ttu-id="80451-162">Per ulteriori informazioni, vedere [Eseguire round di formazione aggiuntivi](predictive-coding-train-model.md#perform-additional-training-rounds)</span><span class="sxs-lookup"><span data-stu-id="80451-162">For more information, see [Perform additional training rounds](predictive-coding-train-model.md#perform-additional-training-rounds)</span></span>

## <a name="step-5-apply-the-final-prediction-score-filter-to-prioritize-review"></a><span data-ttu-id="80451-163">Passaggio 5: Applicare il filtro del punteggio di previsione finale per definire le priorità della revisione</span><span class="sxs-lookup"><span data-stu-id="80451-163">Step 5: Apply the final prediction score filter to prioritize review</span></span>

<span data-ttu-id="80451-164">Ripetere le istruzioni nel passaggio 3 per applicare il punteggio di previsione finale al set di revisione per definire la priorità della revisione degli elementi rilevanti e non rilevanti dopo aver completato tutti i round di training e aver stabilizzato il modello.</span><span class="sxs-lookup"><span data-stu-id="80451-164">Repeat the instructions in Step 3 to apply the final prediction score to the review set to prioritize the review of relevant and non-relevant items after you complete all the training rounds and stabilize the model.</span></span>
