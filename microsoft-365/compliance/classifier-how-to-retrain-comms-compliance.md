---
title: Come ripetere il training di un classificatore in Conformità alle comunicazioni
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
description: Informazioni su come fornire feedback a un classificatore addestrabile in Conformità comunicazioni.
ms.openlocfilehash: 75fff8220b052618c70a6490b8c3569c11ecc861
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918147"
---
# <a name="how-to-retrain-a-classifier-in-communications-compliance"></a><span data-ttu-id="b189f-103">Come ripetere il training di un classificatore in Conformità alle comunicazioni</span><span class="sxs-lookup"><span data-stu-id="b189f-103">How to retrain a classifier in communications compliance</span></span>

<span data-ttu-id="b189f-104">Un classificatore di Microsoft 365 addestrabile è uno strumento che è possibile addestrare a riconoscere vari tipi di contenuto fornendogli esempi da esaminare.</span><span class="sxs-lookup"><span data-stu-id="b189f-104">A Microsoft 365 trainable classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="b189f-105">Una volta addestrato, è possibile utilizzarlo per identificare l'elemento per l'applicazione delle etichette di riservatezza di Office, dei criteri di conformità delle comunicazioni e dei criteri delle etichette di conservazione.</span><span class="sxs-lookup"><span data-stu-id="b189f-105">Once trained, you can use it to identify item for application of Office sensitivity labels, communications compliance policies, and retention label policies.</span></span>

<span data-ttu-id="b189f-106">Questo articolo illustra come migliorare le prestazioni dei classificatori addestrabili personalizzati e di alcuni classificatori pre-addestrati fornendo loro un feedback aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="b189f-106">This article shows you how to improve the performance of custom trainable classifiers and some pre-trained classifiers by providing them additional feedback.</span></span>

<span data-ttu-id="b189f-107">Per ulteriori informazioni sui diversi tipi di classificatori, vedere [Learn about trainable classifiers](classifier-learn-about.md).</span><span class="sxs-lookup"><span data-stu-id="b189f-107">To learn more about the different types of classifiers, see [Learn about trainable classifiers](classifier-learn-about.md).</span></span>

## <a name="permissions"></a><span data-ttu-id="b189f-108">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="b189f-108">Permissions</span></span>

<span data-ttu-id="b189f-109">Per accedere ai classificatori nel Centro conformità Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="b189f-109">To access classifiers in the Microsoft 365 Compliance center:</span></span>

- <span data-ttu-id="b189f-110">il ruolo di amministratore della conformità o l'amministratore dei dati di conformità è necessario per formare un classificatore</span><span class="sxs-lookup"><span data-stu-id="b189f-110">the Compliance admin role or Compliance Data Administrator is required to train a classifier</span></span>

<span data-ttu-id="b189f-111">Per usare i classificatori in questi scenari, sono necessari account con queste autorizzazioni:</span><span class="sxs-lookup"><span data-stu-id="b189f-111">You'll need accounts with these permissions to use classifiers in these scenarios:</span></span>

- <span data-ttu-id="b189f-112">Scenario dei criteri di conformità della comunicazione: Insider Risk Management Admin, Supervisory Review Administrator</span><span class="sxs-lookup"><span data-stu-id="b189f-112">Communication compliance policy scenario: Insider Risk Management Admin, Supervisory Review Administrator</span></span> 

## <a name="overall-workflow"></a><span data-ttu-id="b189f-113">Flusso di lavoro complessivo</span><span class="sxs-lookup"><span data-stu-id="b189f-113">Overall workflow</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b189f-114">Fornisci feedback nella soluzione di conformità che usa il classificatore come condizione.</span><span class="sxs-lookup"><span data-stu-id="b189f-114">You provide feedback in the compliance solution that is using the classifier as a condition.</span></span> <span data-ttu-id="b189f-115">**Se non si dispone di un criterio di conformità delle comunicazioni che usa un classificatore come condizione, arrestarsi qui.**</span><span class="sxs-lookup"><span data-stu-id="b189f-115">**If you don't have a communications compliance policy that uses a classifier as a condition, stop here.**</span></span>

<span data-ttu-id="b189f-116">Quando usi i classificatori, potresti voler aumentare la precisione delle classificazioni che stanno effettuando.</span><span class="sxs-lookup"><span data-stu-id="b189f-116">As you use your classifiers, you may want to increase the precision of the classifications that they're making.</span></span> <span data-ttu-id="b189f-117">A tale scopo, valutare la qualità delle classificazioni effettuate per gli elementi identificati come corrispondenti o meno.</span><span class="sxs-lookup"><span data-stu-id="b189f-117">You do this by evaluating the quality of the classifications made  for items it has identified as being a match or not a match.</span></span> <span data-ttu-id="b189f-118">Dopo aver fatto 30 valutazioni per un classificatore, è necessario ricevere tale feedback e riqualificare automaticamente se stesso.</span><span class="sxs-lookup"><span data-stu-id="b189f-118">After you make 30 evaluations for a classifier it takes that feedback and automatically retrains itself.</span></span>

<span data-ttu-id="b189f-119">Per ulteriori informazioni sul flusso di lavoro complessivo di riqualificazione di un classificatore, vedere [Process flow for retraining a classifier.](classifier-learn-about.md#retraining-classifiers)</span><span class="sxs-lookup"><span data-stu-id="b189f-119">To understand more about the overall workflow of retraining a classifier, see [Process flow for retraining a classifier](classifier-learn-about.md#retraining-classifiers).</span></span>

> [!NOTE]
> <span data-ttu-id="b189f-120">Un classificatore deve essere già pubblicato e in uso prima di poter essere nuovamente addestrato.</span><span class="sxs-lookup"><span data-stu-id="b189f-120">A classifier must already be published and in use before it can be retrained.</span></span>

## <a name="how-to-retrain-a-classifier-in-communication-compliance-policies"></a><span data-ttu-id="b189f-121">Come riqualificare un classificatore nei criteri di conformità delle comunicazioni</span><span class="sxs-lookup"><span data-stu-id="b189f-121">How to retrain a classifier in communication compliance policies</span></span>

1. <span data-ttu-id="b189f-122">Aprire i criteri di conformità di comunicazione che utilizzano un classificatore come condizione e scegliere uno degli elementi identificati **nell'elenco In** sospeso.</span><span class="sxs-lookup"><span data-stu-id="b189f-122">Open the Communication compliance policy that uses a classifier as a condition and choose one of the identified items from the **Pending** list.</span></span>
2. <span data-ttu-id="b189f-123">Scegliere i puntini di sospensione e **Migliorare la classificazione.**</span><span class="sxs-lookup"><span data-stu-id="b189f-123">Choose the ellipsis and **Improve classification**.</span></span>
3. <span data-ttu-id="b189f-124">Nel riquadro **Feedback dettagliato,** se l'elemento è un vero positivo, scegliere **Corrispondenza**.</span><span class="sxs-lookup"><span data-stu-id="b189f-124">In the **Detailed feedback** pane, if the item is a true positive, choose, **Match**.</span></span>  <span data-ttu-id="b189f-125">Se l'elemento è un falso positivo, che è stato incluso in modo errato nella categoria, scegliere **Non corrisponde.**</span><span class="sxs-lookup"><span data-stu-id="b189f-125">If the item is a false positive, that is it was incorrectly included in the category, choose **Not a match**.</span></span>
4. <span data-ttu-id="b189f-126">Se esiste un altro classificatore più appropriato per l'elemento, è possibile sceglierlo nell'elenco **Suggerisci** altri classificatori trainabili.</span><span class="sxs-lookup"><span data-stu-id="b189f-126">If there is another classifier that would be more appropriate for the item, you can choose it from the **Suggest other trainable classifiers** list.</span></span> <span data-ttu-id="b189f-127">Questo attiverà l'altro classificatore per valutare l'elemento.</span><span class="sxs-lookup"><span data-stu-id="b189f-127">This will trigger the other classifier to evaluate the item.</span></span>

> [!TIP]
> <span data-ttu-id="b189f-128">È possibile fornire commenti e suggerimenti su più elementi contemporaneamente scegliendoli tutti e quindi scegliendo Fornire **commenti e suggerimenti dettagliati** nella barra dei comandi.</span><span class="sxs-lookup"><span data-stu-id="b189f-128">You can provide feedback on multiple items simultaneously by choosing them all and then choosing **Provide detailed feedback** in the command bar.</span></span>

5. <span data-ttu-id="b189f-129">Scegliere **Invia feedback** per inviare la valutazione di , `match` `not a match` classificazioni e suggerire altri classificatori addestrabili.</span><span class="sxs-lookup"><span data-stu-id="b189f-129">Choose **Send feedback** to send your evaluation of the `match`, `not a match` classifications and suggest other trainable classifiers.</span></span> <span data-ttu-id="b189f-130">Quando hai fornito 30 istanze di feedback a un classificatore, verrà automaticamente riqualificato.</span><span class="sxs-lookup"><span data-stu-id="b189f-130">When you've provided 30 instances of feedback to a classifier, it will automatically  retrain.</span></span> <span data-ttu-id="b189f-131">La riqualificazione può richiedere da 1 a 4 ore.</span><span class="sxs-lookup"><span data-stu-id="b189f-131">Retraining can take from 1-4 hours.</span></span> <span data-ttu-id="b189f-132">I classificatori possono essere addestrati solo due volte al giorno.</span><span class="sxs-lookup"><span data-stu-id="b189f-132">Classifiers can only be retrained twice per day.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b189f-133">Queste informazioni passano al classificatore nel tenant, **non tornano a Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="b189f-133">This information goes to the classifier in your tenant, **it does not go back to Microsoft**.</span></span>

6.  <span data-ttu-id="b189f-134">Aprire la **pagina Classificazione dati** nel Centro conformità Microsoft **365.**</span><span class="sxs-lookup"><span data-stu-id="b189f-134">Open the **Data classification** page in the **Microsoft 365 compliance center**.</span></span>
7. <span data-ttu-id="b189f-135">Aprire **Classificatori trainabili**.</span><span class="sxs-lookup"><span data-stu-id="b189f-135">Open **Trainable classifiers**.</span></span>
8. <span data-ttu-id="b189f-136">Il classificatore utilizzato nei criteri di conformità comunicazioni verrà visualizzato sotto **l'intestazione Ri-formazione.**</span><span class="sxs-lookup"><span data-stu-id="b189f-136">The classifier that was used in your Communications compliance policy will appear under the **Re-training** heading.</span></span>

![classificatore nello stato di riqualificazione](../media/classifier-retraining.png)

9. <span data-ttu-id="b189f-138">Al termine della riqualificazione, scegli il classificatore per aprire la panoramica della riqualificazione.</span><span class="sxs-lookup"><span data-stu-id="b189f-138">Once retraining completes, choose the classifier to open the retraining overview.</span></span>

![Panoramica dei risultati di riqualificazione classificatore](../media/classifier-retraining-overview.png)

10. <span data-ttu-id="b189f-140">Esaminare l'azione consigliata e i confronti di previsione delle versioni di cui è stato eseguito il training e attualmente pubblicate del classificatore.</span><span class="sxs-lookup"><span data-stu-id="b189f-140">Review the recommended action, and the prediction comparisons of the retrained and currently published versions of the classifier.</span></span>
11. <span data-ttu-id="b189f-141">Se si è soddisfatti dei risultati della riqualificazione, scegliere **Ri publish**.</span><span class="sxs-lookup"><span data-stu-id="b189f-141">If you satisfied with the results of the retraining, choose **Re-publish**.</span></span>
12. <span data-ttu-id="b189f-142">Se non si è soddisfatti dei risultati della riqualificazione, è possibile scegliere di fornire ulteriore feedback al classificatore nell'interfaccia di conformità delle comunicazioni e avviare un altro ciclo di riqualificazione o non eseguire alcuna operazione nel qual caso la versione attualmente pubblicata del classificatore continuerà a essere utilizzata.</span><span class="sxs-lookup"><span data-stu-id="b189f-142">If you are not satisfied with the results of the retraining, you can choose to provide additional feedback to the classifier in the Communications compliance interface and start another retraining cycle or do nothing in which case the currently published version of the classifier will continue to be used.</span></span> 

## <a name="details-on-republishing-recommendations"></a><span data-ttu-id="b189f-143">Dettagli sulla ripubblicazione dei suggerimenti</span><span class="sxs-lookup"><span data-stu-id="b189f-143">Details on republishing recommendations</span></span>

<span data-ttu-id="b189f-144">Ecco un po' di informazioni su come formulare il suggerimento per pubblicare di nuovo un classificatore riqualificato o suggerire un'ulteriore riqualificazione.</span><span class="sxs-lookup"><span data-stu-id="b189f-144">Here is a little information on how we formulate the recommendation to re-publish a retrained classifier or suggest further retraining.</span></span> <span data-ttu-id="b189f-145">Ciò richiede una conoscenza più approfondita del funzionamento dei classificatori addestrabili.</span><span class="sxs-lookup"><span data-stu-id="b189f-145">This requires a little deeper understanding of how trainable classifiers work.</span></span>

<span data-ttu-id="b189f-146">Dopo una riqualificazione, valutiamo le prestazioni del classificatore sia sugli elementi con feedback che su tutti gli elementi originariamente usati per formare il classificatore.</span><span class="sxs-lookup"><span data-stu-id="b189f-146">After a retrain, we evaluate the classifier's performance on both the items with feedback as well as any items originally used to train the classifier.</span></span> 

- <span data-ttu-id="b189f-147">Per i modelli predefiniti, gli elementi usati per eseguire il training del classificatore sono gli elementi usati da Microsoft per creare il modello.</span><span class="sxs-lookup"><span data-stu-id="b189f-147">For built-in models, items used to train the classifier are the items used by Microsoft to build the model.</span></span>
- <span data-ttu-id="b189f-148">Per i modelli personalizzati, gli elementi utilizzati nel training originale del classificatore derivano dai siti aggiunti per il test e la revisione.</span><span class="sxs-lookup"><span data-stu-id="b189f-148">For custom models, items used in the original training the classifier are from the sites you had added for test and review.</span></span>

<span data-ttu-id="b189f-149">Confrontiamo i numeri delle prestazioni su entrambi i set di elementi per il classificatore rie addestrato e pubblicato per fornire un suggerimento sull'eventuale miglioramento della ripubblicazione.</span><span class="sxs-lookup"><span data-stu-id="b189f-149">We compare the performance numbers on both sets of items for the retrained and published classifier to provide a recommendation on whether there was improvement to republish.</span></span> 

## <a name="see-also"></a><span data-ttu-id="b189f-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b189f-150">See also</span></span>

- [<span data-ttu-id="b189f-151">Informazioni sui classificatori sottoponibili a training</span><span class="sxs-lookup"><span data-stu-id="b189f-151">Learn about trainable classifiers</span></span>](classifier-learn-about.md)
- [<span data-ttu-id="b189f-152">Estensioni dei nomi di file sottoposti a ricerca per indicizzazione e tipi di file analizzati predefiniti in SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="b189f-152">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)