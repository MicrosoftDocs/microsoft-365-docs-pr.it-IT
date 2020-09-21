---
title: Come riqualificare un classificatore in Esplora contenuto (anteprima)
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
description: Informazioni su come fornire commenti e suggerimenti a un classificatore addestrabile in Esplora contenuto.
ms.openlocfilehash: 0fbce595894cbbf2a017fc1bf657b14a5b812e29
ms.sourcegitcommit: fdb5f9d865037c0ae23aae34a5c0f06b625b2f69
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/18/2020
ms.locfileid: "48132326"
---
# <a name="how-to-retrain-a-classifier-in-content-explorer-preview"></a><span data-ttu-id="00c03-103">Come riqualificare un classificatore in Esplora contenuto (anteprima)</span><span class="sxs-lookup"><span data-stu-id="00c03-103">How to retrain a classifier in content explorer (preview)</span></span>

<span data-ttu-id="00c03-104">Un classificatore addestrabile di Microsoft 365 è uno strumento che è possibile addestrare per riconoscere vari tipi di contenuto fornendo esempi da esaminare.</span><span class="sxs-lookup"><span data-stu-id="00c03-104">A Microsoft 365 trainable classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="00c03-105">Una volta addestrato, è possibile utilizzarlo per identificare gli elementi per l'applicazione delle etichette di sensibilità di Office, i criteri di conformità delle comunicazioni e i criteri etichette di conservazione.</span><span class="sxs-lookup"><span data-stu-id="00c03-105">Once trained, you can use it to identify item for application of Office sensitivity labels, communications compliance policies, and retention label policies.</span></span>

<span data-ttu-id="00c03-106">In questo articolo viene illustrato come migliorare le prestazioni dei classificatori addestrabili personalizzati e di alcuni classificatori preformati fornendo loro commenti e suggerimenti aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="00c03-106">This article shows you how to improve the performance of custom trainable classifiers and some pre-trained classifiers by providing them additional feedback.</span></span>

<span data-ttu-id="00c03-107">Per ulteriori informazioni sui diversi tipi di classificatori, vedere [informazioni sui classificatori addestrabili (Preview)](classifier-learn-about.md).</span><span class="sxs-lookup"><span data-stu-id="00c03-107">To learn more about the different types of classifiers, see [Learn about trainable classifiers (preview)](classifier-learn-about.md).</span></span>

## <a name="permissions"></a><span data-ttu-id="00c03-108">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="00c03-108">Permissions</span></span>

<span data-ttu-id="00c03-109">Per accedere ai classificatori nel centro conformità di Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="00c03-109">To access classifiers in the Microsoft 365 Compliance center:</span></span>

- <span data-ttu-id="00c03-110">il ruolo di amministratore conformità o l'amministratore dei dati di conformità è necessario per formare un classificatore</span><span class="sxs-lookup"><span data-stu-id="00c03-110">the Compliance admin role or Compliance Data Administrator is required to train a classifier</span></span>

<span data-ttu-id="00c03-111">Sono necessari account con queste autorizzazioni per l'utilizzo dei classificatori in questi scenari:</span><span class="sxs-lookup"><span data-stu-id="00c03-111">You'll need accounts with these permissions to use classifiers in these scenarios:</span></span>

- <span data-ttu-id="00c03-112">Scenario dei criteri per l'etichetta di conservazione: ruoli Gestione record e gestione conservazione</span><span class="sxs-lookup"><span data-stu-id="00c03-112">Retention label policy scenario: Record Management and Retention Management roles</span></span> 

## <a name="overall-workflow"></a><span data-ttu-id="00c03-113">Flusso di lavoro globale</span><span class="sxs-lookup"><span data-stu-id="00c03-113">Overall workflow</span></span>

> [!IMPORTANT]
> <span data-ttu-id="00c03-114">È possibile fornire commenti e suggerimenti in Esplora contenuto per applicare automaticamente i criteri delle etichette di conservazione per scambiare gli elementi e utilizza il classificatore come condizione.</span><span class="sxs-lookup"><span data-stu-id="00c03-114">You provide feedback in content explorer for auto-apply retention label policies to Exchange items and uses the classifier as a condition.</span></span> <span data-ttu-id="00c03-115">**Se non si dispone di un criterio di conservazione che applica automaticamente un'etichetta di conservazione agli elementi di Exchange e utilizza un classificatore come condizione, interrompere l'applicazione.**</span><span class="sxs-lookup"><span data-stu-id="00c03-115">**If you don't have a retention policy that auto-applies a retention label to Exchange items and      uses a classifier as a condition, stop here.**</span></span>

<span data-ttu-id="00c03-116">Quando si utilizzano i classificatori, è possibile aumentare la precisione delle classificazioni che stanno facendo.</span><span class="sxs-lookup"><span data-stu-id="00c03-116">As you use your classifiers, you may want to increase the precision of the classifications that they're making.</span></span> <span data-ttu-id="00c03-117">A tale scopo, valutare la qualità delle classificazioni eseguite per gli elementi identificati come una corrispondenza o non una corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="00c03-117">You do this by evaluating the quality of the classifications made  for items it has identified as being a match or not a match.</span></span> <span data-ttu-id="00c03-118">Dopo aver eseguito 30 valutazioni per un classificatore, è necessario che i commenti e suggerimenti vengano riaddestrati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="00c03-118">After you make 30 evaluations for a classifier it takes that feedback and automatically retrains itself.</span></span>

<span data-ttu-id="00c03-119">Per ulteriori informazioni sul flusso di lavoro globale di riqualificazione di un classificatore, vedere [Process Flow for retraining a Classificator](classifier-learn-about.md#retraining-classifiers).</span><span class="sxs-lookup"><span data-stu-id="00c03-119">To understand more about the overall workflow of retraining a classifier, see [Process flow for retraining a classifier](classifier-learn-about.md#retraining-classifiers).</span></span>

> [!NOTE]
> <span data-ttu-id="00c03-120">Un classificatore deve essere già pubblicato e in uso prima che possa essere riaddestrato.</span><span class="sxs-lookup"><span data-stu-id="00c03-120">A classifier must already be published and in use before it can be retrained.</span></span>

## <a name="how-to-retrain-a-classifier-in-content-explorer-preview"></a><span data-ttu-id="00c03-121">Come riqualificare un classificatore in Esplora contenuto (anteprima)</span><span class="sxs-lookup"><span data-stu-id="00c03-121">How to retrain a classifier in content explorer (preview)</span></span>

1. <span data-ttu-id="00c03-122">Accedere al centro conformità Microsoft 365 con l'accesso al ruolo amministratore di sicurezza o di amministratore della protezione e aprire **Microsoft 365 Compliance Center**  >  **Data classificazione**  >  **Content Explorer**.</span><span class="sxs-lookup"><span data-stu-id="00c03-122">Sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** > **Data classification** > **Content explorer**.</span></span> 
2. <span data-ttu-id="00c03-123">Nell'elenco **filtro su etichette, tipi di informazioni o categorie** , espandere **classificatori addestrabili**.</span><span class="sxs-lookup"><span data-stu-id="00c03-123">Under the **Filter on labels, info types, or categories** list, expand **Trainable classifiers**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="00c03-124">È possibile richiedere fino a otto giorni affinché gli elementi aggregati vengano visualizzati nell'intestazione dei classificatori addestrabili.</span><span class="sxs-lookup"><span data-stu-id="00c03-124">It can take up to eight days for aggregated items to appear under the trainable classifiers heading.</span></span>

3. <span data-ttu-id="00c03-125">Scegliere il classificatore addestrabile utilizzato nei criteri di etichetta di conservazione applicati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="00c03-125">Choose the trainable classifier you used in you auto-apply retention label policy.</span></span> <span data-ttu-id="00c03-126">Questo è il classificatore addestrabile che fornirà commenti e suggerimenti.</span><span class="sxs-lookup"><span data-stu-id="00c03-126">This is the trainable classifier you will give feedback on.</span></span>

> [!NOTE]
> <span data-ttu-id="00c03-127">Se un elemento contiene una voce nella colonna **etichetta di conservazione** , significa che l'elemento è stato classificato come a `match` .</span><span class="sxs-lookup"><span data-stu-id="00c03-127">If an item has an entry in the **Retention label** column, it means that the item was classified as a `match`.</span></span>  <span data-ttu-id="00c03-128">Se un elemento non dispone di una voce nella colonna **etichetta di conservazione** , significa che è stata classificata come a `close match` .</span><span class="sxs-lookup"><span data-stu-id="00c03-128">If an item doesn't have an entry in the **Retention label** column, it means it was classified as a `close match`.</span></span> <span data-ttu-id="00c03-129">È possibile migliorare maggiormente la precisione del classificatore fornendo commenti e suggerimenti sugli `close match` elementi.</span><span class="sxs-lookup"><span data-stu-id="00c03-129">You can improve the classifier precision the most by providing feedback on `close match` items.</span></span> 

4. <span data-ttu-id="00c03-130">Scegliere un elemento e aprirlo.</span><span class="sxs-lookup"><span data-stu-id="00c03-130">Choose an item and open it.</span></span>
 
 > [!TIP]
> <span data-ttu-id="00c03-131">È possibile fornire commenti e suggerimenti su più elementi contemporaneamente, scegliendo tutti e quindi scegliendo **migliora classificazione** nella barra dei comandi.</span><span class="sxs-lookup"><span data-stu-id="00c03-131">You can provide feedback on multiple items simultaneously by choosing them all and then choosing **Improve classification** in the command bar.</span></span>

5. <span data-ttu-id="00c03-132">Scegliere **Fornisci commenti e suggerimenti**.</span><span class="sxs-lookup"><span data-stu-id="00c03-132">Choose **Provide feedback**.</span></span>
6. <span data-ttu-id="00c03-133">Nel riquadro dei **commenti e suggerimenti dettagliati** , se l'elemento è un valore true positive, scegliere **match**.</span><span class="sxs-lookup"><span data-stu-id="00c03-133">In the **Detailed feedback** pane, if the item is a true positive, choose, **Match**.</span></span>  <span data-ttu-id="00c03-134">Se l'elemento è un falso positivo, ovvero non è stato incluso in modo errato nella categoria, scegliere **non una corrispondenza**.</span><span class="sxs-lookup"><span data-stu-id="00c03-134">If the item is a false positive, that is it was incorrectly included in the category, choose **Not a match**.</span></span>
7. <span data-ttu-id="00c03-135">Se è presente un altro classificatore più appropriato per l'elemento, è possibile sceglierlo nell'elenco **Suggerisci altri classificatori addestrabili** .</span><span class="sxs-lookup"><span data-stu-id="00c03-135">If there is another classifier that would be more appropriate for the item, you can choose it from the **Suggest other trainable classifiers** list.</span></span> <span data-ttu-id="00c03-136">Questo attiverà l'altro classificatore per valutare l'elemento.</span><span class="sxs-lookup"><span data-stu-id="00c03-136">This will trigger the other classifier to evaluate the item.</span></span>
8. <span data-ttu-id="00c03-137">Scegliere **Invia commenti e suggerimenti** per inviare la valutazione `match` delle `not a match` classificazioni e suggerire altri classificatori addestrabili.</span><span class="sxs-lookup"><span data-stu-id="00c03-137">Choose **Send feedback** to send your evaluation of the `match`, `not a match` classifications and suggest other trainable classifiers.</span></span> <span data-ttu-id="00c03-138">Quando sono state fornite 30 istanze di commenti e suggerimenti a un classificatore, la riqualificazione viene automaticamente.</span><span class="sxs-lookup"><span data-stu-id="00c03-138">When you've provided 30 instances of feedback to a classifier, it will automatically  retrain.</span></span> <span data-ttu-id="00c03-139">La riqualificazione può richiedere da 1 a 4 ore.</span><span class="sxs-lookup"><span data-stu-id="00c03-139">Retraining can take from one to four hours.</span></span> <span data-ttu-id="00c03-140">I classificatori possono essere riaddestrati solo due volte al giorno.</span><span class="sxs-lookup"><span data-stu-id="00c03-140">Classifiers can only be retrained twice per day.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="00c03-141">Queste informazioni passano al classificatore del tenant, **ma non tornano a Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="00c03-141">This information goes to the classifier in your tenant, **it does not go back to Microsoft**.</span></span>

9. <span data-ttu-id="00c03-142">Aprire **classificatori addestrabili (anteprima)**.</span><span class="sxs-lookup"><span data-stu-id="00c03-142">Open **Trainable classifiers (preview)**.</span></span>
10. <span data-ttu-id="00c03-143">Il classificatore che è stato utilizzato nei criteri di conformità delle comunicazioni verrà visualizzato nell'intestazione **riqualificazione** .</span><span class="sxs-lookup"><span data-stu-id="00c03-143">The classifier that was used in your Communications compliance policy will appear under the **Re-training** heading.</span></span>

![classificatore nello stato di riqualificazione](../media/classifier-retraining.png)

11. <span data-ttu-id="00c03-145">Una volta completata la riqualificazione, scegliere il classificatore per aprire la panoramica sulla riqualificazione.</span><span class="sxs-lookup"><span data-stu-id="00c03-145">Once retraining completes, choose the classifier to open the retraining overview.</span></span>

![Panoramica dei risultati di riqualificazione del classificatore](../media/classifier-retraining-overview.png)

12. <span data-ttu-id="00c03-147">Esaminare l'azione consigliata e i confronti di stima delle versioni riqualificate e attualmente pubblicate del classificatore.</span><span class="sxs-lookup"><span data-stu-id="00c03-147">Review the recommended action, and the prediction comparisons of the retrained and currently published versions of the classifier.</span></span>
13. <span data-ttu-id="00c03-148">Se si è soddisfatti dei risultati della riqualificazione, scegliere **ripubblicare**.</span><span class="sxs-lookup"><span data-stu-id="00c03-148">If you satisfied with the results of the retraining, choose **Re-publish**.</span></span>
14. <span data-ttu-id="00c03-149">Se non si è soddisfatti dei risultati della riqualificazione, è possibile scegliere di fornire ulteriori commenti e suggerimenti al classificatore nell'interfaccia di conformità delle comunicazioni e avviare un altro ciclo di riqualificazione o non eseguire alcuna operazione nel qual caso la versione attualmente pubblicata del classificatore continuerà a essere utilizzata.</span><span class="sxs-lookup"><span data-stu-id="00c03-149">If you are not satisfied with the results of the retraining, you can choose to provide additional feedback to the classifier in the Communications compliance interface and start another retraining cycle or do nothing in which case the currently published version of the classifier will continue to be used.</span></span> 

## <a name="details-on-republishing-recommendations"></a><span data-ttu-id="00c03-150">Informazioni dettagliate sulla ripubblicazione dei suggerimenti</span><span class="sxs-lookup"><span data-stu-id="00c03-150">Details on republishing recommendations</span></span>

<span data-ttu-id="00c03-151">Ecco alcune informazioni su come formulare la raccomandazione di ripubblicare un classificatore riaddestrato o suggerire ulteriori ricorsi.</span><span class="sxs-lookup"><span data-stu-id="00c03-151">Here is a little information on how we formulate the recommendation to re-publish a retrained classifier or suggest further retraining.</span></span> <span data-ttu-id="00c03-152">Ciò richiede una conoscenza più approfondita del funzionamento dei classificatori addestrabili.</span><span class="sxs-lookup"><span data-stu-id="00c03-152">This requires a little deeper understanding of how trainable classifiers work.</span></span>

<span data-ttu-id="00c03-153">Dopo una riqualificazione, vengono valutate le prestazioni del classificatore sia sugli elementi con feedback, sia su tutti gli elementi originariamente utilizzati per formare il classificatore.</span><span class="sxs-lookup"><span data-stu-id="00c03-153">After a retrain, we evaluate the classifier's performance on both the items with feedback as well as any items originally used to train the classifier.</span></span> 

- <span data-ttu-id="00c03-154">Per i modelli incorporati, gli elementi utilizzati per la formazione del classificatore sono gli elementi utilizzati da Microsoft per creare il modello.</span><span class="sxs-lookup"><span data-stu-id="00c03-154">For built-in models, items used to train the classifier are the items used by Microsoft to build the model.</span></span>
- <span data-ttu-id="00c03-155">Per i modelli personalizzati, gli elementi utilizzati nell'allenamento originale il classificatore è compreso tra i siti aggiunti per il test e la revisione.</span><span class="sxs-lookup"><span data-stu-id="00c03-155">For custom models, items used in the original training the classifier are from the sites you had added for test and review.</span></span>

<span data-ttu-id="00c03-156">Vengono confrontati i numeri di prestazioni su entrambi i set di elementi per il classificatore riaddestrato e pubblicato per fornire una raccomandazione sull'eventuale ripubblicazione del miglioramento.</span><span class="sxs-lookup"><span data-stu-id="00c03-156">We compare the performance numbers on both sets of items for the retrained and published classifier to provide a recommendation on whether there was improvement to republish.</span></span> 

## <a name="see-also"></a><span data-ttu-id="00c03-157">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="00c03-157">See also</span></span>

- [<span data-ttu-id="00c03-158">Informazioni sui classificatori addestrabili (anteprima)</span><span class="sxs-lookup"><span data-stu-id="00c03-158">Learn about trainable classifiers (preview)</span></span>](classifier-learn-about.md)
- [<span data-ttu-id="00c03-159">Estensioni dei nomi di file sottoposti a ricerca per indicizzazione e tipi di file analizzati predefiniti in SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="00c03-159">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)
