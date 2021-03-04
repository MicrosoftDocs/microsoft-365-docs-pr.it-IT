---
title: Come ripetere il training di un classificatore in Esplora contenuto
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Informazioni su come fornire feedback a un classificatore di cui è possibile eseguire il training in Esplora contenuto.
ms.openlocfilehash: fabfe8e4df377c25012b358960d7f7ff7ff994bc
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423263"
---
# <a name="how-to-retrain-a-classifier-in-content-explorer"></a><span data-ttu-id="6fe4e-103">Come ripetere il training di un classificatore in Esplora contenuto</span><span class="sxs-lookup"><span data-stu-id="6fe4e-103">How to retrain a classifier in content explorer</span></span>

<span data-ttu-id="6fe4e-104">Un classificatore formabile di Microsoft 365 è uno strumento che è possibile formare per riconoscere vari tipi di contenuto fornendogli esempi da esaminare.</span><span class="sxs-lookup"><span data-stu-id="6fe4e-104">A Microsoft 365 trainable classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="6fe4e-105">Una volta preparato, è possibile utilizzarlo per identificare l'elemento per l'applicazione delle etichette di riservatezza di Office, dei criteri di conformità delle comunicazioni e dei criteri delle etichette di conservazione.</span><span class="sxs-lookup"><span data-stu-id="6fe4e-105">Once trained, you can use it to identify item for application of Office sensitivity labels, communications compliance policies, and retention label policies.</span></span>

<span data-ttu-id="6fe4e-106">Questo articolo illustra come migliorare le prestazioni dei classificatori addestrabili personalizzati e di alcuni classificatori pre-preparati fornendo loro un feedback aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="6fe4e-106">This article shows you how to improve the performance of custom trainable classifiers and some pre-trained classifiers by providing them additional feedback.</span></span>

<span data-ttu-id="6fe4e-107">Per ulteriori informazioni sui diversi tipi di classificatori, vedere Informazioni sui classificatori disponibili [per il training.](classifier-learn-about.md)</span><span class="sxs-lookup"><span data-stu-id="6fe4e-107">To learn more about the different types of classifiers, see [Learn about trainable classifiers](classifier-learn-about.md).</span></span>

<span data-ttu-id="6fe4e-108">Guardare questo video per un breve riepilogo del processo di ottimizzazione e riqualificazione.</span><span class="sxs-lookup"><span data-stu-id="6fe4e-108">Watch this video for a quick summary of the tuning and retraining process.</span></span> <span data-ttu-id="6fe4e-109">Dovrai comunque leggere questo articolo completo per ottenere i dettagli.</span><span class="sxs-lookup"><span data-stu-id="6fe4e-109">You'll still need to read this full article to get the details.</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWyGMs]


## <a name="permissions"></a><span data-ttu-id="6fe4e-110">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="6fe4e-110">Permissions</span></span>

<span data-ttu-id="6fe4e-111">Per accedere ai classificatori nel Centro conformità Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="6fe4e-111">To access classifiers in the Microsoft 365 Compliance center:</span></span>

- <span data-ttu-id="6fe4e-112">Il ruolo di amministratore della conformità o l'amministratore dei dati di conformità è necessario per formare un classificatore</span><span class="sxs-lookup"><span data-stu-id="6fe4e-112">the Compliance admin role or Compliance Data Administrator is required to train a classifier</span></span>

<span data-ttu-id="6fe4e-113">Per usare i classificatori in questi scenari, sono necessari account con queste autorizzazioni:</span><span class="sxs-lookup"><span data-stu-id="6fe4e-113">You'll need accounts with these permissions to use classifiers in these scenarios:</span></span>

- <span data-ttu-id="6fe4e-114">Scenario dei criteri di etichetta di conservazione: ruoli Gestione record e Gestione conservazione</span><span class="sxs-lookup"><span data-stu-id="6fe4e-114">Retention label policy scenario: Record Management and Retention Management roles</span></span> 

## <a name="overall-workflow"></a><span data-ttu-id="6fe4e-115">Flusso di lavoro complessivo</span><span class="sxs-lookup"><span data-stu-id="6fe4e-115">Overall workflow</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6fe4e-116">Il feedback viene fornito in Esplora contenuto per l'applicazione automatica dei criteri delle etichette di conservazione agli elementi di Exchange e il classificatore viene utilizzato come condizione.</span><span class="sxs-lookup"><span data-stu-id="6fe4e-116">You provide feedback in content explorer for auto-apply retention label policies to Exchange items and uses the classifier as a condition.</span></span> <span data-ttu-id="6fe4e-117">**Se non si dispone di un criterio di conservazione che applica automaticamente un'etichetta di conservazione agli elementi di Exchange e usa un classificatore come condizione, fermarsi qui.**</span><span class="sxs-lookup"><span data-stu-id="6fe4e-117">**If you don't have a retention policy that auto-applies a retention label to Exchange items and      uses a classifier as a condition, stop here.**</span></span>

<span data-ttu-id="6fe4e-118">Quando si utilizzano i classificatori, è possibile aumentare la precisione delle classificazioni che stanno effettuando.</span><span class="sxs-lookup"><span data-stu-id="6fe4e-118">As you use your classifiers, you may want to increase the precision of the classifications that they're making.</span></span> <span data-ttu-id="6fe4e-119">A tale scopo, valutare la qualità delle classificazioni effettuate per gli elementi identificati come corrispondenti o meno.</span><span class="sxs-lookup"><span data-stu-id="6fe4e-119">You do this by evaluating the quality of the classifications made  for items it has identified as being a match or not a match.</span></span> <span data-ttu-id="6fe4e-120">Dopo aver fatto 30 valutazioni per un classificatore, richiede quel feedback e si rie classifica automaticamente.</span><span class="sxs-lookup"><span data-stu-id="6fe4e-120">After you make 30 evaluations for a classifier it takes that feedback and automatically retrains itself.</span></span>

<span data-ttu-id="6fe4e-121">Per ulteriori informazioni sul flusso di lavoro generale di riqualificazione di un classificatore, vedere Flusso di processo per la [riqualificazione di un classificatore.](classifier-learn-about.md#retraining-classifiers)</span><span class="sxs-lookup"><span data-stu-id="6fe4e-121">To understand more about the overall workflow of retraining a classifier, see [Process flow for retraining a classifier](classifier-learn-about.md#retraining-classifiers).</span></span>

> [!NOTE]
> <span data-ttu-id="6fe4e-122">Un classificatore deve essere già pubblicato e in uso prima di poter essere riesegnato.</span><span class="sxs-lookup"><span data-stu-id="6fe4e-122">A classifier must already be published and in use before it can be retrained.</span></span>

## <a name="how-to-retrain-a-classifier-in-content-explorer"></a><span data-ttu-id="6fe4e-123">Come ripetere il training di un classificatore in Esplora contenuto</span><span class="sxs-lookup"><span data-stu-id="6fe4e-123">How to retrain a classifier in content explorer</span></span>

1. <span data-ttu-id="6fe4e-124">Accedere al Centro conformità Microsoft 365 con l'accesso al ruolo di amministratore della conformità o amministratore della sicurezza e aprire Esplora contenuto per la classificazione dei dati del Centro conformità **Microsoft 365.**  >    >  </span><span class="sxs-lookup"><span data-stu-id="6fe4e-124">Sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** > **Data classification** > **Content explorer**.</span></span> 
2. <span data-ttu-id="6fe4e-125">**Nell'elenco Filtro in base a etichette, tipi di** informazioni o categorie espandere Classificatori sotto forma di **sottosezioni.**</span><span class="sxs-lookup"><span data-stu-id="6fe4e-125">Under the **Filter on labels, info types, or categories** list, expand **Trainable classifiers**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6fe4e-126">La visualizzazione degli elementi aggregati sotto l'intestazione classificatori sotto il training può richiedere fino a otto giorni.</span><span class="sxs-lookup"><span data-stu-id="6fe4e-126">It can take up to eight days for aggregated items to appear under the trainable classifiers heading.</span></span>

3. <span data-ttu-id="6fe4e-127">Scegliere il classificatore formabile usato nei criteri di etichetta di conservazione applicati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="6fe4e-127">Choose the trainable classifier you used in you auto-apply retention label policy.</span></span> <span data-ttu-id="6fe4e-128">Questo è il classificatore su cui è possibile formare il feedback.</span><span class="sxs-lookup"><span data-stu-id="6fe4e-128">This is the trainable classifier you will give feedback on.</span></span>

> [!NOTE]
> <span data-ttu-id="6fe4e-129">Se un elemento contiene una voce nella colonna **Dell'etichetta** di conservazione, significa che l'elemento è stato classificato come `match` .</span><span class="sxs-lookup"><span data-stu-id="6fe4e-129">If an item has an entry in the **Retention label** column, it means that the item was classified as a `match`.</span></span>  <span data-ttu-id="6fe4e-130">Se un elemento non dispone di una voce nella colonna **Dell'etichetta** di conservazione, significa che è stato classificato come `close match` .</span><span class="sxs-lookup"><span data-stu-id="6fe4e-130">If an item doesn't have an entry in the **Retention label** column, it means it was classified as a `close match`.</span></span> <span data-ttu-id="6fe4e-131">Puoi migliorare maggiormente la precisione del classificatore fornendo feedback sugli `close match` elementi.</span><span class="sxs-lookup"><span data-stu-id="6fe4e-131">You can improve the classifier precision the most by providing feedback on `close match` items.</span></span> 

4. <span data-ttu-id="6fe4e-132">Scegliere un elemento e aprirlo.</span><span class="sxs-lookup"><span data-stu-id="6fe4e-132">Choose an item and open it.</span></span>
 
 > [!TIP]
> <span data-ttu-id="6fe4e-133">Puoi fornire feedback su più elementi contemporaneamente scegliendoli tutti e quindi scegliendo **Migliora classificazione** nella barra dei comandi.</span><span class="sxs-lookup"><span data-stu-id="6fe4e-133">You can provide feedback on multiple items simultaneously by choosing them all and then choosing **Improve classification** in the command bar.</span></span>

5. <span data-ttu-id="6fe4e-134">Scegliere **Fornisci feedback.**</span><span class="sxs-lookup"><span data-stu-id="6fe4e-134">Choose **Provide feedback**.</span></span>
6. <span data-ttu-id="6fe4e-135">Nel riquadro **Commenti e suggerimenti dettagliati,** se l'elemento è un vero positivo, scegliere **Corrispondenza.**</span><span class="sxs-lookup"><span data-stu-id="6fe4e-135">In the **Detailed feedback** pane, if the item is a true positive, choose, **Match**.</span></span>  <span data-ttu-id="6fe4e-136">Se l'elemento è un falso positivo, che è stato incluso in modo errato nella categoria, scegliere **Non corrisponde a.**</span><span class="sxs-lookup"><span data-stu-id="6fe4e-136">If the item is a false positive, that is it was incorrectly included in the category, choose **Not a match**.</span></span>
7. <span data-ttu-id="6fe4e-137">Se è presente un altro classificatore più appropriato per l'elemento, è possibile sceglierlo nell'elenco **Suggerisci** altri classificatori formabili.</span><span class="sxs-lookup"><span data-stu-id="6fe4e-137">If there is another classifier that would be more appropriate for the item, you can choose it from the **Suggest other trainable classifiers** list.</span></span> <span data-ttu-id="6fe4e-138">In questo modo verrà attivato l'altro classificatore per valutare l'elemento.</span><span class="sxs-lookup"><span data-stu-id="6fe4e-138">This will trigger the other classifier to evaluate the item.</span></span>
8. <span data-ttu-id="6fe4e-139">Scegliere **Invia feedback** per inviare la valutazione dei classificatori, le classificazioni e suggerire altri `match` `not a match` classificatori formabili.</span><span class="sxs-lookup"><span data-stu-id="6fe4e-139">Choose **Send feedback** to send your evaluation of the `match`, `not a match` classifications and suggest other trainable classifiers.</span></span> <span data-ttu-id="6fe4e-140">Quando hai fornito 30 istanze di feedback a un classificatore, verrà automaticamente riesercita la formazione.</span><span class="sxs-lookup"><span data-stu-id="6fe4e-140">When you've provided 30 instances of feedback to a classifier, it will automatically  retrain.</span></span> <span data-ttu-id="6fe4e-141">La riqualificazione può richiedere da una a quattro ore.</span><span class="sxs-lookup"><span data-stu-id="6fe4e-141">Retraining can take from one to four hours.</span></span> <span data-ttu-id="6fe4e-142">I classificatori possono essere addestrati solo due volte al giorno.</span><span class="sxs-lookup"><span data-stu-id="6fe4e-142">Classifiers can only be retrained twice per day.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6fe4e-143">Queste informazioni passano al classificatore nel tenant, **non tornano a Microsoft.**</span><span class="sxs-lookup"><span data-stu-id="6fe4e-143">This information goes to the classifier in your tenant, **it does not go back to Microsoft**.</span></span>

9. <span data-ttu-id="6fe4e-144">Apri **classificatori di cui è possibile utilizzare il training.**</span><span class="sxs-lookup"><span data-stu-id="6fe4e-144">Open **Trainable classifiers**.</span></span>
10. <span data-ttu-id="6fe4e-145">Il classificatore usato nei criteri di conformità delle comunicazioni verrà visualizzato sotto **l'intestazione Ri-formazione.**</span><span class="sxs-lookup"><span data-stu-id="6fe4e-145">The classifier that was used in your Communications compliance policy will appear under the **Re-training** heading.</span></span>

![classificatore nello stato di riqualificazione](../media/classifier-retraining.png)

11. <span data-ttu-id="6fe4e-147">Al termine della riqualificazione, scegli il classificatore per aprire la panoramica della riqualificazione.</span><span class="sxs-lookup"><span data-stu-id="6fe4e-147">Once retraining completes, choose the classifier to open the retraining overview.</span></span>

![Panoramica dei risultati di riqualificazione dei classificatori](../media/classifier-retraining-overview.png)

12. <span data-ttu-id="6fe4e-149">Esaminare l'azione consigliata e i confronti di previsione delle versioni riesecite e attualmente pubblicate del classificatore.</span><span class="sxs-lookup"><span data-stu-id="6fe4e-149">Review the recommended action, and the prediction comparisons of the retrained and currently published versions of the classifier.</span></span>
13. <span data-ttu-id="6fe4e-150">Se si è soddisfatti dei risultati della riqualificazione, scegliere **Riposizioni.**</span><span class="sxs-lookup"><span data-stu-id="6fe4e-150">If you satisfied with the results of the retraining, choose **Re-publish**.</span></span>
14. <span data-ttu-id="6fe4e-151">Se non si è soddisfatti dei risultati della riqualificazione, è possibile scegliere di fornire ulteriore feedback al classificatore nell'interfaccia di conformità delle comunicazioni e avviare un altro ciclo di riqualificazione o non eseguire alcuna operazione nel qual caso la versione attualmente pubblicata del classificatore continuerà a essere utilizzata.</span><span class="sxs-lookup"><span data-stu-id="6fe4e-151">If you are not satisfied with the results of the retraining, you can choose to provide additional feedback to the classifier in the Communications compliance interface and start another retraining cycle or do nothing in which case the currently published version of the classifier will continue to be used.</span></span> 

## <a name="details-on-republishing-recommendations"></a><span data-ttu-id="6fe4e-152">Dettagli sulla ripubblicazione dei suggerimenti</span><span class="sxs-lookup"><span data-stu-id="6fe4e-152">Details on republishing recommendations</span></span>

<span data-ttu-id="6fe4e-153">Ecco un po' di informazioni su come formulare il suggerimento di pubblicare di nuovo un classificatore riqualificato o suggerire un'ulteriore riqualificazione.</span><span class="sxs-lookup"><span data-stu-id="6fe4e-153">Here is a little information on how we formulate the recommendation to re-publish a retrained classifier or suggest further retraining.</span></span> <span data-ttu-id="6fe4e-154">Ciò richiede una conoscenza più approfondita del funzionamento dei classificatori formabili.</span><span class="sxs-lookup"><span data-stu-id="6fe4e-154">This requires a little deeper understanding of how trainable classifiers work.</span></span>

<span data-ttu-id="6fe4e-155">Dopo un nuovo training, valutiamo le prestazioni del classificatore su entrambi gli elementi con feedback, nonché su tutti gli elementi originariamente usati per formare il classificatore.</span><span class="sxs-lookup"><span data-stu-id="6fe4e-155">After a retrain, we evaluate the classifier's performance on both the items with feedback as well as any items originally used to train the classifier.</span></span> 

- <span data-ttu-id="6fe4e-156">Per i modelli predefiniti, gli elementi usati per eseguire il training del classificatore sono gli elementi usati da Microsoft per creare il modello.</span><span class="sxs-lookup"><span data-stu-id="6fe4e-156">For built-in models, items used to train the classifier are the items used by Microsoft to build the model.</span></span>
- <span data-ttu-id="6fe4e-157">Per i modelli personalizzati, gli elementi usati nella formazione originale del classificatore sono provenienti dai siti aggiunti per il test e la revisione.</span><span class="sxs-lookup"><span data-stu-id="6fe4e-157">For custom models, items used in the original training the classifier are from the sites you had added for test and review.</span></span>

<span data-ttu-id="6fe4e-158">Confrontiamo i numeri delle prestazioni su entrambi i set di elementi per il classificatore rie addestrato e pubblicato per fornire una raccomandazione sulla possibile ripubblicazione di un miglioramento.</span><span class="sxs-lookup"><span data-stu-id="6fe4e-158">We compare the performance numbers on both sets of items for the retrained and published classifier to provide a recommendation on whether there was improvement to republish.</span></span> 

## <a name="see-also"></a><span data-ttu-id="6fe4e-159">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6fe4e-159">See also</span></span>

- [<span data-ttu-id="6fe4e-160">Informazioni sui classificatori sottoponibili a training</span><span class="sxs-lookup"><span data-stu-id="6fe4e-160">Learn about trainable classifiers</span></span>](classifier-learn-about.md)
- [<span data-ttu-id="6fe4e-161">Estensioni dei nomi di file sottoposti a ricerca per indicizzazione e tipi di file analizzati predefiniti in SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="6fe4e-161">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)
