---
title: Training di un modello di codifica predittivo in Advanced eDiscovery
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
description: ''
ms.openlocfilehash: 84ec1ad42f2cec2487debe7160a3f24e09bdd830
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288192"
---
# <a name="train-a-predictive-coding-model-preview"></a><span data-ttu-id="51256-102">Eseguire il training di un modello di codifica predittivo (anteprima)</span><span class="sxs-lookup"><span data-stu-id="51256-102">Train a predictive coding model (preview)</span></span>

<span data-ttu-id="51256-103">Dopo aver creato un modello di codifica predittivo in Advanced eDiscovery, il passaggio successivo consiste nell'eseguire il primo round di training per formare il modello su ciò che è rilevante e non pertinente nel set di recensioni.</span><span class="sxs-lookup"><span data-stu-id="51256-103">After you create a predictive coding model in Advanced eDiscovery, the next step is to performing the first training round to train the model on what is relevant and non-relevant content in your review set.</span></span> <span data-ttu-id="51256-104">Dopo aver completato il primo ciclo di training, è possibile eseguire round di training successivi per migliorare la capacità del modello di prevedere contenuti pertinenti e non rilevanti.</span><span class="sxs-lookup"><span data-stu-id="51256-104">After you complete the first round of training, you can perform subsequent training rounds to improve the model's ability to predict relevant and non-relevant content.</span></span>

<span data-ttu-id="51256-105">Per esaminare il flusso di lavoro di codifica predittiva, vedere Informazioni sulla codifica [predittiva in Advanced eDiscovery](predictive-coding-overview.md#the-predictive-coding-workflow)</span><span class="sxs-lookup"><span data-stu-id="51256-105">To review the predictive coding workflow, see [Learn about predictive coding in Advanced eDiscovery](predictive-coding-overview.md#the-predictive-coding-workflow)</span></span>

## <a name="before-you-train-a-model"></a><span data-ttu-id="51256-106">Prima di eseguire il training di un modello</span><span class="sxs-lookup"><span data-stu-id="51256-106">Before you train a model</span></span>

- <span data-ttu-id="51256-107">Durante un ciclo di formazione, etichettare gli elementi come **Rilevanti** o **Non** rilevanti in base alla pertinenza del contenuto del documento.</span><span class="sxs-lookup"><span data-stu-id="51256-107">During a training round, label items as **Relevant** or **Not relevant** based on the relevancy of the content in the document.</span></span> <span data-ttu-id="51256-108">Non basare la decisione sui valori nei campi dei metadati.</span><span class="sxs-lookup"><span data-stu-id="51256-108">Don't base your decision on the values in the metadata fields.</span></span> <span data-ttu-id="51256-109">Ad esempio, per i messaggi di posta elettronica Teams conversazioni, non basare la decisione di etichettatura sui partecipanti del messaggio.</span><span class="sxs-lookup"><span data-stu-id="51256-109">For example, for email messages or Teams conversations, don't base your labeling decision on the message participants.</span></span>

## <a name="train-a-model-for-the-first-time"></a><span data-ttu-id="51256-110">Training di un modello per la prima volta</span><span class="sxs-lookup"><span data-stu-id="51256-110">Train a model for the first time</span></span>

1. <span data-ttu-id="51256-111">Nella finestra Centro conformità Microsoft 365 aprire un Advanced eDiscovery e quindi selezionare la **scheda Set di** revisioni.</span><span class="sxs-lookup"><span data-stu-id="51256-111">In the Microsoft 365 compliance center, open an Advanced eDiscovery case and then select the **Review sets** tab.</span></span>

2. <span data-ttu-id="51256-112">Apri un set di recensioni e quindi fai clic su **Analisi**  >  **Gestisci codifica predittiva (anteprima)**.</span><span class="sxs-lookup"><span data-stu-id="51256-112">Open a review set and then click **Analytics** > **Manage predictive coding (preview)**.</span></span>

3. <span data-ttu-id="51256-113">Nella pagina **Modelli di codifica predittiva (anteprima)** selezionare il modello di cui si desidera eseguire il training.</span><span class="sxs-lookup"><span data-stu-id="51256-113">On the **Predictive coding models (preview)** page, select the model that you want to train.</span></span>

4. <span data-ttu-id="51256-114">Nella scheda **Panoramica,** in **Round 1,** fare clic **su Avvia il round di formazione successivo.**</span><span class="sxs-lookup"><span data-stu-id="51256-114">On the **Overview** tab, under **Round 1**, click **Start next training round**.</span></span>

   <span data-ttu-id="51256-115">Viene **visualizzata** la scheda Formazione che contiene 50 elementi da etichettare.</span><span class="sxs-lookup"><span data-stu-id="51256-115">The **Training** tab is displayed and contains 50 items for you to label.</span></span>

5. <span data-ttu-id="51256-116">Esaminare ogni documento e quindi selezionare il **pulsante Rilevante** o **Non** rilevante nella parte inferiore del riquadro di lettura per etichettarlo.</span><span class="sxs-lookup"><span data-stu-id="51256-116">Review each document and then select the **Relevant** or **Not relevant** button at the bottom of the reading pane to label it.</span></span>

   ![Etichettare ogni documento come rilevante o non pertinente](..\media\TrainModel1.png)

6. <span data-ttu-id="51256-118">Dopo aver etichettato tutti i 50 elementi, fare clic su **Fine.**</span><span class="sxs-lookup"><span data-stu-id="51256-118">After you've labeled all 50 items, click **Finish**.</span></span>

    <span data-ttu-id="51256-119">Il sistema avrà un paio di minuti per "imparare" dall'etichettatura e aggiornare il modello.</span><span class="sxs-lookup"><span data-stu-id="51256-119">It will take a couple minutes for the system to "learn" from your labeling and update the model.</span></span> <span data-ttu-id="51256-120">Al termine di questo processo, viene visualizzato lo stato **Pronto** per il modello nella pagina Modelli di codifica predittiva **(anteprima).**</span><span class="sxs-lookup"><span data-stu-id="51256-120">When this process is complete, a status of **Ready** is displayed for the model on the **Predictive coding models (preview)** page.</span></span>

## <a name="perform-additional-training-rounds"></a><span data-ttu-id="51256-121">Eseguire ulteriori round di formazione</span><span class="sxs-lookup"><span data-stu-id="51256-121">Perform additional training rounds</span></span>

<span data-ttu-id="51256-122">Dopo aver eseguito il primo ciclo di formazione, è possibile eseguire round di formazione successivi seguendo i passaggi della sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="51256-122">After you perform the first round of training, you can perform subsequent training rounds by following the steps in the previous section.</span></span> <span data-ttu-id="51256-123">L'unica differenza è che il numero del round di training verrà aggiornato nella scheda **Panoramica del** modello. Ad esempio, dopo aver eseguito il primo round di formazione, è possibile fare clic su Avvia il round di **formazione** successivo per iniziare il secondo ciclo di formazione.</span><span class="sxs-lookup"><span data-stu-id="51256-123">The only difference is the number of the training round will be updated on the model **Overview** tab. For example, after performing the first training round, you can click **Start next training round** to start the second round of training.</span></span> <span data-ttu-id="51256-124">E così via.</span><span class="sxs-lookup"><span data-stu-id="51256-124">And so on.</span></span>

<span data-ttu-id="51256-125">Ogni round di training (sia quelli in corso che quelli completati) viene visualizzato nella **scheda Training** per il modello.</span><span class="sxs-lookup"><span data-stu-id="51256-125">Each round of training (both those in progress and those that are complete) is displayed on the **Training** tab for the model.</span></span> <span data-ttu-id="51256-126">Quando si seleziona un round di formazione, viene visualizzata una pagina a comparsa con informazioni e metriche per il round.</span><span class="sxs-lookup"><span data-stu-id="51256-126">When you select a training round, a flyout page with information and metrics for the round is displayed.</span></span>

## <a name="what-happens-after-you-perform-a-training-round"></a><span data-ttu-id="51256-127">Cosa succede dopo aver eseguito un round di formazione</span><span class="sxs-lookup"><span data-stu-id="51256-127">What happens after you perform a training round</span></span>

<span data-ttu-id="51256-128">Dopo aver eseguito il primo ciclo di formazione, viene avviato un processo che esegue le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="51256-128">After you perform the first training round, a job is started that does the following things:</span></span>

- <span data-ttu-id="51256-129">In base al modo in cui hai etichettato i 40 elementi nel set di training, il modello apprende dall'etichettatura e si aggiorna per diventare più accurato.</span><span class="sxs-lookup"><span data-stu-id="51256-129">Based on how you labeled the 40 items in the training set, the model learns from your labeling and updates itself to become more accurate.</span></span>

- <span data-ttu-id="51256-130">Il modello elabora quindi ogni elemento nell'intero set di revisione e assegna un punteggio di previsione compreso tra **0** (non rilevante) e **1** (pertinente).</span><span class="sxs-lookup"><span data-stu-id="51256-130">The model then processes each item in the entire review set and assigns a prediction score between **0** (not relevant) and **1** (relevant).</span></span>

- <span data-ttu-id="51256-131">Il modello assegna un punteggio di previsione ai 10 elementi del set di controlli etichettati durante il round di training.</span><span class="sxs-lookup"><span data-stu-id="51256-131">The model assigns a prediction score to the 10 items in the control set that you labeled during the training round.</span></span> <span data-ttu-id="51256-132">Il modello confronta il punteggio di stima di questi 10 elementi con l'etichetta effettiva assegnata all'elemento durante la fase di training.</span><span class="sxs-lookup"><span data-stu-id="51256-132">The model compares the prediction score of these 10 items with the actual label that you assigned to the item during the training round.</span></span> <span data-ttu-id="51256-133">In base a questo confronto, il modello identifica la classificazione seguente (denominata matrice confusione *set* di controlli ) per valutare le prestazioni di previsione del modello:</span><span class="sxs-lookup"><span data-stu-id="51256-133">Based on this comparison, the model identifies the following classification (called the *Control set confusion matrix*) to assess the model's prediction performance:</span></span>

  <br>

  ****

  |<span data-ttu-id="51256-134">Etichetta</span><span class="sxs-lookup"><span data-stu-id="51256-134">Label</span></span>|<span data-ttu-id="51256-135">Il modello prevede che l'elemento sia rilevante</span><span class="sxs-lookup"><span data-stu-id="51256-135">Model predicts item is relevant</span></span>|<span data-ttu-id="51256-136">Il modello prevede che l'elemento non sia rilevante</span><span class="sxs-lookup"><span data-stu-id="51256-136">Model predicts item is not relevant</span></span>|
  |---|---|---|
  |<span data-ttu-id="51256-137">**Elemento etichette revisore pertinente**</span><span class="sxs-lookup"><span data-stu-id="51256-137">**Reviewer labels item as relevant**</span></span>|<span data-ttu-id="51256-138">True positive</span><span class="sxs-lookup"><span data-stu-id="51256-138">True positive</span></span>|<span data-ttu-id="51256-139">Falso positivo</span><span class="sxs-lookup"><span data-stu-id="51256-139">False positive</span></span>|
  |<span data-ttu-id="51256-140">**Elemento etichette revisore non pertinente**</span><span class="sxs-lookup"><span data-stu-id="51256-140">**Reviewer labels item as not relevant**</span></span>|<span data-ttu-id="51256-141">Falso negativo</span><span class="sxs-lookup"><span data-stu-id="51256-141">False negative</span></span>|<span data-ttu-id="51256-142">True negative</span><span class="sxs-lookup"><span data-stu-id="51256-142">True negative</span></span>|
  |

  <span data-ttu-id="51256-143">In base a questi confronti, il modello deriva i valori per le metriche del punteggio F, della precisione e del richiamo e del margine di errore per ognuno di essi.</span><span class="sxs-lookup"><span data-stu-id="51256-143">Based on these comparisons, the model derives values for the F-score, precision, and recall metrics and the margin of error for each one.</span></span> <span data-ttu-id="51256-144">I punteggi per queste metriche delle prestazioni del modello vengono visualizzati in una pagina a comparsa per il round di training.</span><span class="sxs-lookup"><span data-stu-id="51256-144">Scores for these model performance metrics are displayed on a flyout page for the training round.</span></span> <span data-ttu-id="51256-145">Per una descrizione di queste metriche, vedere [Informazioni di riferimento sulla codifica predittiva.](predictive-coding-reference.md)</span><span class="sxs-lookup"><span data-stu-id="51256-145">For a description of these metrics, see [Predictive coding reference](predictive-coding-reference.md).</span></span>

- <span data-ttu-id="51256-146">Infine, il modello determina i 50 elementi successivi che verranno utilizzati per il turno di training successivo.</span><span class="sxs-lookup"><span data-stu-id="51256-146">Finally, the model determines the next 50 items that will be used for the next training round.</span></span> <span data-ttu-id="51256-147">Questa volta, il modello potrebbe selezionare 20 elementi dal set di controlli e 30 nuovi elementi dal set di revisione e designarli come set di training per il turno successivo.</span><span class="sxs-lookup"><span data-stu-id="51256-147">This time, the model might select 20 items from the control set and 30 new items from the review set and designate them as the training set for the next round.</span></span> <span data-ttu-id="51256-148">Il campionamento per il turno di training successivo non viene campionato in modo uniforme.</span><span class="sxs-lookup"><span data-stu-id="51256-148">The sampling for the next training round is not uniformly sampled.</span></span> <span data-ttu-id="51256-149">Il modello ottimizza la selezione di campionamento degli elementi dal set di recensioni per selezionare gli elementi in cui la previsione è ambigua, il che significa che il punteggio di stima è compreso nell'intervallo 0,5.</span><span class="sxs-lookup"><span data-stu-id="51256-149">The model will optimize the sampling selection of items from the review set to select items where the prediction is ambiguous, which means the prediction score is in the 0.5 range.</span></span> <span data-ttu-id="51256-150">Questo processo è noto come *selezione parziale.*</span><span class="sxs-lookup"><span data-stu-id="51256-150">This process is known as *biased selection*.</span></span>

### <a name="what-happens-after-you-perform-subsequent-training-rounds"></a><span data-ttu-id="51256-151">Cosa succede dopo aver eseguito round di formazione successivi</span><span class="sxs-lookup"><span data-stu-id="51256-151">What happens after you perform subsequent training rounds</span></span>

<span data-ttu-id="51256-152">Dopo aver eseguito round di training successivi (dopo il primo round di training), il modello esegue le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="51256-152">After you perform subsequent training rounds (after the first training round), the model does the following things:</span></span>

- <span data-ttu-id="51256-153">Il modello viene aggiornato in base alle etichette applicate al set di training in tale round di training.</span><span class="sxs-lookup"><span data-stu-id="51256-153">The model is updated based on the labels that you applied to the training set in that round of training.</span></span>

- <span data-ttu-id="51256-154">Il sistema valuta il punteggio di previsione del modello per gli elementi nel set di controlli e controlla se il punteggio è allineato al modo in cui hai etichettato gli elementi nel set di controlli.</span><span class="sxs-lookup"><span data-stu-id="51256-154">The system evaluates the model's prediction score on the items in the control set and check whether the score aligns with how you labeled items in the control set.</span></span> <span data-ttu-id="51256-155">La valutazione viene eseguita su tutti gli elementi etichettati del set di controlli per tutti i round di training.</span><span class="sxs-lookup"><span data-stu-id="51256-155">The evaluation is performed on all labeled items from control set for all training rounds.</span></span> <span data-ttu-id="51256-156">I risultati di questa valutazione sono incorporati nel dashboard nella **scheda Panoramica** del modello.</span><span class="sxs-lookup"><span data-stu-id="51256-156">The results of this evaluation are incorporated in the dashboard on the **Overview** tab for the model.</span></span>

- <span data-ttu-id="51256-157">Il modello aggiornato rielabora ogni elemento nel set di revisione e assegna a ogni elemento un punteggio di previsione aggiornato.</span><span class="sxs-lookup"><span data-stu-id="51256-157">The updated model reprocesses every item in the review set and assign each item an updated prediction score.</span></span>

## <a name="next-steps"></a><span data-ttu-id="51256-158">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="51256-158">Next steps</span></span>

<span data-ttu-id="51256-159">Dopo aver eseguito il primo round di training, è possibile eseguire più round di training o applicare il filtro del punteggio di previsione del modello al set di revisione per visualizzare gli elementi previsti dal modello come rilevanti o non pertinenti.</span><span class="sxs-lookup"><span data-stu-id="51256-159">After you perform the first training round, you can perform more training rounds or apply the model's prediction score filter to the review set to view the items the model has predicted as relevant or not relevant.</span></span> <span data-ttu-id="51256-160">Per ulteriori informazioni, vedere [Apply a prediction score filter to a review set](predictive-coding-apply-prediction-filter.md).</span><span class="sxs-lookup"><span data-stu-id="51256-160">For more information, see [Apply a prediction score filter to a review set](predictive-coding-apply-prediction-filter.md).</span></span>
