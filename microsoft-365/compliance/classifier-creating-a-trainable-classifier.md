---
title: Creare un classificatore addestrabile (anteprima)
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Utilizzare classificatori addestrabili quando uno dei classificatori di caselle pronti per l'uso non soddisfa le proprie esigenze. Un classificatore Microsoft 365 è uno strumento che è possibile addestrare per riconoscere vari tipi di contenuto fornendo esempi da esaminare. In questo argomento viene illustrato come creare un classificatore personalizzato.
ms.openlocfilehash: cb3cda9777d692a56263e92cd908eb09bfa99895
ms.sourcegitcommit: 8fda7852b2a5baa92b8a365865b014ea6d100bbc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/03/2019
ms.locfileid: "39813374"
---
# <a name="creating-a-trainable-classifier-preview"></a><span data-ttu-id="6cc06-105">Creazione di un classificatore addestrabile (anteprima)</span><span class="sxs-lookup"><span data-stu-id="6cc06-105">Creating a trainable classifier (preview)</span></span>

<span data-ttu-id="6cc06-106">Utilizzare i classificatori addestrabili quando uno dei classificatori fuori campo non soddisfa le proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="6cc06-106">Use trainable classifiers when one of the out of the box classifiers won't meet your needs.</span></span> <span data-ttu-id="6cc06-107">Un classificatore Microsoft 365 è uno strumento che è possibile addestrare per riconoscere vari tipi di contenuto fornendo esempi da esaminare.</span><span class="sxs-lookup"><span data-stu-id="6cc06-107">A Microsoft 365 classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="6cc06-108">Formazione il classificatore implica la prima assegnazione di campioni che sono selezionati in modo umano e corrispondono positivamente alla categoria.</span><span class="sxs-lookup"><span data-stu-id="6cc06-108">Training the classifier involves first giving it samples that are human picked and positively match the category.</span></span> <span data-ttu-id="6cc06-109">Successivamente, dopo averli elaborati, si verificano le stime conferendole una combinazione di esempi positivi e negativi.</span><span class="sxs-lookup"><span data-stu-id="6cc06-109">Then, after it has processed those, you test the predictions by giving it a mix of positive and negative samples.</span></span>

<span data-ttu-id="6cc06-110">Per ulteriori informazioni sui diversi tipi di classificatori, vedere [Guida introduttiva ai classificatori addestrabili (anteprima)](classifier-getting-started-with.md)</span><span class="sxs-lookup"><span data-stu-id="6cc06-110">To learn more about the different types of classifiers, see [Getting started with trainable classifiers (preview)](classifier-getting-started-with.md)</span></span>

<span data-ttu-id="6cc06-111">Questa sequenza temporale riflette una distribuzione di esempio.</span><span class="sxs-lookup"><span data-stu-id="6cc06-111">This timeline reflects a sample deployment.</span></span>

![addestrare-classificatore-sequenza temporale](media/trainable-classifier-deployment-timeline_border.png)

> [!TIP]
> <span data-ttu-id="6cc06-113">L'opzione opt-in è necessaria per la prima volta per i classificatori addestrabili.</span><span class="sxs-lookup"><span data-stu-id="6cc06-113">Opt-in is required the first time for trainable classifiers.</span></span> <span data-ttu-id="6cc06-114">Per completare una valutazione di base del contenuto delle organizzazioni, sono necessari dodici giorni per Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6cc06-114">It takes twelve days for Microsoft 365 to complete a baseline evaluation of your organizations content.</span></span>

## <a name="seed-content"></a><span data-ttu-id="6cc06-115">Contenuto del seeding</span><span class="sxs-lookup"><span data-stu-id="6cc06-115">Seed content</span></span>

<span data-ttu-id="6cc06-116">Quando si desidera che un classificatore addestrabile sia in grado di identificare in modo indipendente e accurato un elemento come in particolare la categoria di contenuto, è necessario innanzitutto presentarlo con numerosi esempi del tipo di contenuto nella categoria.</span><span class="sxs-lookup"><span data-stu-id="6cc06-116">When you want a trainable classifier to independently and accurately identify an item as being in particular category of content, you first have to present it with many samples of the type of content that are in the category.</span></span> <span data-ttu-id="6cc06-117">L'alimentazione dei campioni al classificatore addestrabile è nota come *seeding*.</span><span class="sxs-lookup"><span data-stu-id="6cc06-117">This feeding of samples to the trainable classifier is known as *seeding*.</span></span> <span data-ttu-id="6cc06-118">Il contenuto del seeding viene selezionato da un essere umano e viene giudicato per rappresentare la categoria di contenuto.</span><span class="sxs-lookup"><span data-stu-id="6cc06-118">Seed content is selected by a human and is judged to represent the category of content.</span></span>

> [!TIP]
> <span data-ttu-id="6cc06-119">È necessario avere almeno 50 campioni positivi e ben 500.</span><span class="sxs-lookup"><span data-stu-id="6cc06-119">You need to have at least 50 positive samples and as many as 500.</span></span> <span data-ttu-id="6cc06-120">Il classificatore addestrativo elaborerà fino a 500 campioni creati più recenti (per data e timestamp creati dal file).</span><span class="sxs-lookup"><span data-stu-id="6cc06-120">The trainable classifier will process up to the 500 most recent created samples (by file created date/time stamp).</span></span> <span data-ttu-id="6cc06-121">Più esempi vengono forniti, maggiore è la precisione delle stime che verranno apportate dal classificatore.</span><span class="sxs-lookup"><span data-stu-id="6cc06-121">The more samples you provide, the more accurate the predictions the classifier will make.</span></span>

## <a name="testing-content"></a><span data-ttu-id="6cc06-122">Test del contenuto</span><span class="sxs-lookup"><span data-stu-id="6cc06-122">Testing content</span></span>

<span data-ttu-id="6cc06-123">Dopo che il classificatore addestratore ha elaborato campioni positivi sufficienti per creare un modello di stima, è necessario verificare le stime che consente di verificare se il classificatore può distinguere correttamente tra gli elementi che corrispondono alla categoria e gli elementi che non lo fanno.</span><span class="sxs-lookup"><span data-stu-id="6cc06-123">Once the trainable classifier has processed enough positive samples to build a prediction model, you need to test the predictions it makes to see if the classifier can correctly distinguish between items that match the category and items that don't.</span></span> <span data-ttu-id="6cc06-124">A tale scopo, è necessario nutrirlo con un altro, che si spera più grande, insieme di contenuto umano raccolto che è costituito da campioni che devono rientrare nella categoria e campioni che non lo faranno.</span><span class="sxs-lookup"><span data-stu-id="6cc06-124">You do this by feeding it another, hopefully larger, set of human picked content that consists of samples that should fall into the category and samples that won't.</span></span> <span data-ttu-id="6cc06-125">Dopo averli elaborati, si procede manualmente ai risultati e si verifica se ogni previsione è corretta, non corretta o non si è certi.</span><span class="sxs-lookup"><span data-stu-id="6cc06-125">Once it processes those, you manually go through the results and verify whether each prediction is correct, incorrect, or you aren't sure.</span></span> <span data-ttu-id="6cc06-126">Il classificatore addestrabile utilizza questi commenti e suggerimenti per migliorare il modello di stima.</span><span class="sxs-lookup"><span data-stu-id="6cc06-126">The trainable classifier uses this feedback to improve its prediction model.</span></span>

> [!TIP]
> <span data-ttu-id="6cc06-127">Per ottenere risultati ottimali, avere 10.000 elementi nel set di campioni di test con una distribuzione uniforme di corrispondenze positive e negative.</span><span class="sxs-lookup"><span data-stu-id="6cc06-127">For best results, have 10,000 items in your test sample set with an even distribution of positive and negative matches.</span></span>

## <a name="how-to-create-a-trainable-classifier"></a><span data-ttu-id="6cc06-128">Come creare un classificatore addestrabile</span><span class="sxs-lookup"><span data-stu-id="6cc06-128">How to create a trainable classifier</span></span>

1. <span data-ttu-id="6cc06-129">Raccogliere tra gli elementi di contenuto di 50-500 Seed.</span><span class="sxs-lookup"><span data-stu-id="6cc06-129">Collect between 50-500 seed content items.</span></span> <span data-ttu-id="6cc06-130">Questi devono essere solo campioni che rappresentano fortemente il tipo di contenuto che si desidera che il classificatore addestrabile identifichi positivamente come nella Categoria classificazione.</span><span class="sxs-lookup"><span data-stu-id="6cc06-130">These must be only samples that strongly represent the type of content you want the trainable classifier to positively identify as being in the classification category.</span></span> <span data-ttu-id="6cc06-131">Per i tipi di file supportati, vedere le estensioni di file sottoposte [a ricerca per indicizzazione e i tipi di file analizzati in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) .</span><span class="sxs-lookup"><span data-stu-id="6cc06-131">See, [Default crawled file name extensions and parsed file types in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) for the supported file types.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6cc06-132">Gli elementi di esempio Seed e test non devono essere crittografati e devono essere in inglese.</span><span class="sxs-lookup"><span data-stu-id="6cc06-132">The seed and test sample items must not be encrypted and they must be in English.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6cc06-133">Verificare che gli elementi del set di Seed siano esempi **forti** della categoria.</span><span class="sxs-lookup"><span data-stu-id="6cc06-133">Make sure the items in your seed set are **strong** examples of the category.</span></span> <span data-ttu-id="6cc06-134">Il classificatore addestrabile crea inizialmente il modello in base alle operazioni con cui viene eseguito il seeding.</span><span class="sxs-lookup"><span data-stu-id="6cc06-134">The trainable classifier initially builds its model based on what you seed it with.</span></span> <span data-ttu-id="6cc06-135">Il classificatore presuppone che tutti gli esempi di sementi siano forti positivi e che non sia possibile sapere se un campione è una corrispondenza debole o negativa per la categoria.</span><span class="sxs-lookup"><span data-stu-id="6cc06-135">The classifier assumes all seed samples are strong positives and has no way of knowing if a sample is a weak or negative match to the category.</span></span>

2. <span data-ttu-id="6cc06-136">Inserire il contenuto di inizializzazione in una cartella di SharePoint Online dedicata a contenere *solo il contenuto del seeding*.</span><span class="sxs-lookup"><span data-stu-id="6cc06-136">Place the seed content in a SharePoint Online folder that is dedicated to holding *the seed content only*.</span></span> <span data-ttu-id="6cc06-137">Prendere nota dell'URL del sito, della raccolta e della cartella.</span><span class="sxs-lookup"><span data-stu-id="6cc06-137">Make note of the site, library, and folder URL.</span></span>

> [!TIP]
> <span data-ttu-id="6cc06-138">Se si crea un nuovo sito e una nuova cartella per i dati di seeding, è possibile eseguire l'indicizzazione di almeno un'ora affinché tale percorso venga indicizzato prima di creare il classificatore addestrabile che utilizzerà tali dati.</span><span class="sxs-lookup"><span data-stu-id="6cc06-138">If you create a new site and folder for your seed data, allow at least an hour for that location to be indexed before creating the trainable classifier that will use that seed data.</span></span>

3. <span data-ttu-id="6cc06-139">Accedere a Microsoft 365 Compliance Center with Compliance admin or Security admin Role Access e Open **Microsoft 365 Compliance Center** or **Microsoft 365 Security Center** > **Data Classification**</span><span class="sxs-lookup"><span data-stu-id="6cc06-139">Sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** or **Microsoft 365 security center** > **Data classification**</span></span>

4. <span data-ttu-id="6cc06-140">Scegliere la scheda **classificatori addestrabili** .</span><span class="sxs-lookup"><span data-stu-id="6cc06-140">Choose the **Trainable classifiers** tab.</span></span>

5. <span data-ttu-id="6cc06-141">Scegliere **Crea classificatore addestrabile**.</span><span class="sxs-lookup"><span data-stu-id="6cc06-141">Choose **Create trainable classifier**.</span></span>

6. <span data-ttu-id="6cc06-142">Inserire i valori adeguati per `Name`i campi `Description` e la categoria di elementi che si desidera vengano identificati dal classificatore addestrabile.</span><span class="sxs-lookup"><span data-stu-id="6cc06-142">Fill in appropriate values for the `Name`, and `Description` fields of the category of items you want this trainable classifier to identify.</span></span>

7. <span data-ttu-id="6cc06-143">Immettere il sito, la raccolta e l'URL della cartella di SharePoint Online esatti per il sito di contenuto Seed del passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="6cc06-143">Enter the exact SharePoint Online site, library, and folder URL for the seed content site from step 2.</span></span> <span data-ttu-id="6cc06-144">Scegliere `Add`.</span><span class="sxs-lookup"><span data-stu-id="6cc06-144">Choose `Add`.</span></span>

8. <span data-ttu-id="6cc06-145">Rivedere le impostazioni e scegliere `Create trainable classifier`.</span><span class="sxs-lookup"><span data-stu-id="6cc06-145">Review the settings and choose `Create trainable classifier`.</span></span>

9. <span data-ttu-id="6cc06-146">Entro 24 ore, il classificatore addestrativo elaborerà i dati di seeding e realizzerà un modello di stima.</span><span class="sxs-lookup"><span data-stu-id="6cc06-146">Within 24 hours the trainable classifier will process the seed data and build a prediction model.</span></span> <span data-ttu-id="6cc06-147">Lo stato del classificatore `In progress` è durante l'elaborazione dei dati di seeding.</span><span class="sxs-lookup"><span data-stu-id="6cc06-147">The classifier status is `In progress` while it processes the seed data.</span></span> <span data-ttu-id="6cc06-148">Quando il classificatore ha terminato di elaborare i dati di seeding, lo `Need test items`stato cambia in.</span><span class="sxs-lookup"><span data-stu-id="6cc06-148">When the classifier is finished processing the seed data, the status changes to `Need test items`.</span></span>

10. <span data-ttu-id="6cc06-149">È ora possibile visualizzare la pagina dei dettagli scegliendo il classificatore.</span><span class="sxs-lookup"><span data-stu-id="6cc06-149">You can now view the details page by choosing the classifier.</span></span>


![classificatore addestrabile pronto per il testing](media/classifier-trainable-ready-to-test-detail.png)

11. <span data-ttu-id="6cc06-151">Raccogliere almeno 200 elementi di contenuto di test.</span><span class="sxs-lookup"><span data-stu-id="6cc06-151">Collect at least 200 test content items.</span></span> <span data-ttu-id="6cc06-152">Microsoft consiglia 10.000 per ottenere risultati ottimali.</span><span class="sxs-lookup"><span data-stu-id="6cc06-152">Microsoft recommends 10,000 for best results.</span></span> <span data-ttu-id="6cc06-153">Queste devono essere una combinazione di elementi che sono forti positivi, negativi forti e alcuni che sono un po' meno evidenti nella loro natura.</span><span class="sxs-lookup"><span data-stu-id="6cc06-153">These should be a mix of items that are strong positives, strong negatives and some that are a little less obvious in their nature.</span></span> <span data-ttu-id="6cc06-154">Per i tipi di file supportati, vedere le estensioni di file sottoposte [a ricerca per indicizzazione e i tipi di file analizzati in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) .</span><span class="sxs-lookup"><span data-stu-id="6cc06-154">See, [Default crawled file name extensions and parsed file types in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) for the supported file types.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6cc06-155">Gli elementi di esempio non devono essere crittografati e devono essere in inglese.</span><span class="sxs-lookup"><span data-stu-id="6cc06-155">The sample items must not be encrypted and they must be in English.</span></span>

12. <span data-ttu-id="6cc06-156">Inserire il contenuto del test in una cartella di SharePoint Online dedicata alla conservazione *del solo contenuto del test*.</span><span class="sxs-lookup"><span data-stu-id="6cc06-156">Place the test content in a SharePoint Online folder that is dedicated to holding *the test content only*.</span></span> <span data-ttu-id="6cc06-157">Prendere nota del sito, della raccolta e dell'URL della cartella di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="6cc06-157">Make note of the SharePoint Online site, library, and folder URL.</span></span>

> [!TIP]
> <span data-ttu-id="6cc06-158">Se si crea un nuovo sito e una nuova cartella per i dati di test, è possibile che la posizione venga indicizzata per almeno un'ora prima di creare il classificatore addestrabile che utilizzerà tali dati.</span><span class="sxs-lookup"><span data-stu-id="6cc06-158">If you create a new site and folder for your test data, allow at least an hour for that location to be indexed before creating the trainable classifier that will use that seed data.</span></span>

13. <span data-ttu-id="6cc06-159">Scegliere `Add items to test`.</span><span class="sxs-lookup"><span data-stu-id="6cc06-159">Choose `Add items to test`.</span></span>

14. <span data-ttu-id="6cc06-160">Immettere il sito, la raccolta e l'URL della cartella di SharePoint Online esatti per il sito di contenuto di test del passaggio 12.</span><span class="sxs-lookup"><span data-stu-id="6cc06-160">Enter the exact SharePoint Online site, library, and folder URL for the test content site from step 12.</span></span> <span data-ttu-id="6cc06-161">Scegliere `Add`.</span><span class="sxs-lookup"><span data-stu-id="6cc06-161">Choose `Add`.</span></span>

15. <span data-ttu-id="6cc06-162">Completare la procedura guidata scegliendo `Done`.</span><span class="sxs-lookup"><span data-stu-id="6cc06-162">Finish the wizard by choosing `Done`.</span></span> <span data-ttu-id="6cc06-163">Il classificatore addestrabile richiederà fino a un'ora per l'elaborazione dei file di test.</span><span class="sxs-lookup"><span data-stu-id="6cc06-163">Your trainable classifier will take up to an hour to process the test files.</span></span>

16. <span data-ttu-id="6cc06-164">Quando si esegue l'elaborazione dei file di test da `Ready to review`parte del classificatore addestrabile, lo stato nella pagina dei dettagli cambia.</span><span class="sxs-lookup"><span data-stu-id="6cc06-164">When the trainable classifier is done processing your test files, the status on the details page will change to `Ready to review`.</span></span> <span data-ttu-id="6cc06-165">Se è necessario aumentare le dimensioni del campione di test, `Add items to test` scegliere e consentire al classificatore addestrabile di elaborare gli elementi aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="6cc06-165">If you need to increase the test sample size, choose `Add items to test` and allow the trainable classifier to process the additional items.</span></span>

![pronto per la revisione dello screenshot](media/classifier-trainable-ready-to-review-detail.png)

17. <span data-ttu-id="6cc06-167">Scegliere `Tested items to review` la scheda per esaminare gli elementi.</span><span class="sxs-lookup"><span data-stu-id="6cc06-167">Choose `Tested items to review` tab to review items.</span></span>

18. <span data-ttu-id="6cc06-168">Microsoft 365 presenterà 30 elementi alla volta.</span><span class="sxs-lookup"><span data-stu-id="6cc06-168">Microsoft 365 will present 30 items at a time.</span></span> <span data-ttu-id="6cc06-169">Verificarli e nella casella `We predict this item is "Relevant". Do you agree?` scegliere uno `Yes` o `No` più o `Not sure, skip to next item`.</span><span class="sxs-lookup"><span data-stu-id="6cc06-169">Review them and in the `We predict this item is "Relevant". Do you agree?` box choose either `Yes` or `No` or `Not sure, skip to next item`.</span></span> <span data-ttu-id="6cc06-170">L'accuratezza del modello viene aggiornata automaticamente dopo ogni 30 elementi.</span><span class="sxs-lookup"><span data-stu-id="6cc06-170">Model accuracy is automatically updated after every 30 items.</span></span>

![casella di controllo elementi](media/classifier-trainable-review-detail.png)

19. <span data-ttu-id="6cc06-172">Esaminare *almeno 200 elementi* .</span><span class="sxs-lookup"><span data-stu-id="6cc06-172">Review *at least* 200 items.</span></span>

<!-- insert Analyze steps here-->

20. <span data-ttu-id="6cc06-173">Continuare a esaminare fino a quando l'accuratezza raggiunge almeno il 70 `Publish the classifier` % e `Ready to use`lo stato è.</span><span class="sxs-lookup"><span data-stu-id="6cc06-173">Continue to review until the accuracy reaches at least 70% and the `Publish the classifier` status is `Ready to use`.</span></span>

![accuratezza e pronto per la pubblicazione](media/classifier-trainable-review-ready-to-publish.png)

21. <span data-ttu-id="6cc06-175">Pubblicare il classificatore.</span><span class="sxs-lookup"><span data-stu-id="6cc06-175">Publish the classifier.</span></span>

22. <span data-ttu-id="6cc06-176">Una volta pubblicato, il classificatore sarà disponibile come condizione nel criterio di etichetta di conservazione per l' [applicazione automatica in base a una condizione](labels.md#applying-a-retention-label-automatically-based-on-conditions) e in [conformità alla comunicazione](communication-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="6cc06-176">Once published your classifier will be available as a condition in the [auto-apply retention label policy based on a condition](labels.md#applying-a-retention-label-automatically-based-on-conditions) and in [Communication compliance](communication-compliance.md).</span></span>

> [!CAUTION]
> <span data-ttu-id="6cc06-177">Dopo la pubblicazione di un classificatore, non è possibile eseguire ulteriori corsi di formazione, quindi accertarsi di aver testato e Recensito il maggior numero possibile di elementi per garantire la massima accuratezza possibile.</span><span class="sxs-lookup"><span data-stu-id="6cc06-177">Once a classifier is published, it can't go through any additional training, so be very sure that you have tested and reviewed as many items as possible to ensure that the accuracy is as high as possible.</span></span>

## <a name="see-also"></a><span data-ttu-id="6cc06-178">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6cc06-178">See also</span></span>

- [<span data-ttu-id="6cc06-179">Introduzione ai classificatori sottoponibili a training (anteprima)</span><span class="sxs-lookup"><span data-stu-id="6cc06-179">Getting started with trainable classifiers (preview)</span></span>](classifier-getting-started-with.md)
- [<span data-ttu-id="6cc06-180">Estensioni dei nomi di file sottoposti a ricerca per indicizzazione e tipi di file analizzati predefiniti in SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="6cc06-180">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)
