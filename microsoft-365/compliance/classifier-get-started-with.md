---
title: Introduzione ai classificatori sottoponibili a training (anteprima)
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
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Un classificatore Microsoft 365 è uno strumento che è possibile addestrare per riconoscere vari tipi di contenuto fornendo esempi da esaminare. In questo articolo viene illustrato come creare e formare un classificatore personalizzato e come riqualificarli per aumentare l'accuratezza.
ms.openlocfilehash: 9fe50f7faada77492fd93a86d0c3549cc8e1d361
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/14/2020
ms.locfileid: "49072965"
---
# <a name="get-started-with-trainable-classifiers-preview"></a><span data-ttu-id="6c237-104">Introduzione ai classificatori sottoponibili a training (anteprima)</span><span class="sxs-lookup"><span data-stu-id="6c237-104">Get started with trainable classifiers (preview)</span></span>

<span data-ttu-id="6c237-105">Un classificatore addestrabile di Microsoft 365 è uno strumento che è possibile addestrare per riconoscere vari tipi di contenuto fornendo esempi da esaminare.</span><span class="sxs-lookup"><span data-stu-id="6c237-105">A Microsoft 365 trainable classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="6c237-106">Una volta addestrato, è possibile utilizzarlo per identificare gli elementi per l'applicazione delle etichette di sensibilità di Office, i criteri di conformità delle comunicazioni e i criteri etichette di conservazione.</span><span class="sxs-lookup"><span data-stu-id="6c237-106">Once trained, you can use it to identify item for application of Office sensitivity labels, Communications compliance policies, and retention label policies.</span></span>

<span data-ttu-id="6c237-107">La creazione di un classificatore addestrabile personalizzato comporta innanzitutto l'assegnazione di campioni che sono scelti dall'uomo e corrispondono positivamente alla categoria.</span><span class="sxs-lookup"><span data-stu-id="6c237-107">Creating a custom trainable classifier first involves giving it samples that are human picked and positively match the category.</span></span> <span data-ttu-id="6c237-108">Successivamente, dopo averli elaborati, è possibile testare la capacità dei classificatori di predire assegnando un insieme di esempi positivi e negativi.</span><span class="sxs-lookup"><span data-stu-id="6c237-108">Then, after it has processed those, you test the classifiers ability to predict by giving it a mix of positive and negative samples.</span></span> <span data-ttu-id="6c237-109">In questo articolo viene illustrato come creare e formare un classificatore personalizzato e come migliorare le prestazioni di classificatori addestrabili personalizzati e classificatori preformati nel corso della loro durata tramite la riqualificazione.</span><span class="sxs-lookup"><span data-stu-id="6c237-109">This article shows you how to create and train a custom classifier and how to improve the performance of custom trainable classifiers and pre-trained classifiers over their lifetime through retraining.</span></span>

<span data-ttu-id="6c237-110">Per ulteriori informazioni sui diversi tipi di classificatori, vedere [informazioni sui classificatori addestrabili (Preview)](classifier-learn-about.md).</span><span class="sxs-lookup"><span data-stu-id="6c237-110">To learn more about the different types of classifiers, see [Learn about trainable classifiers (preview)](classifier-learn-about.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6c237-111">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="6c237-111">Prerequisites</span></span>

### <a name="licensing-requirements"></a><span data-ttu-id="6c237-112">Requisiti per la licenza</span><span class="sxs-lookup"><span data-stu-id="6c237-112">Licensing requirements</span></span>

<span data-ttu-id="6c237-113">I classificatori sono una funzionalità di conformità di Microsoft 365 E5 o E5.</span><span class="sxs-lookup"><span data-stu-id="6c237-113">Classifiers are a Microsoft 365 E5, or E5 Compliance feature.</span></span> <span data-ttu-id="6c237-114">È necessario disporre di uno di questi abbonamenti per utilizzarli.</span><span class="sxs-lookup"><span data-stu-id="6c237-114">You must have one of these subscriptions to make use of them.</span></span>

### <a name="permissions"></a><span data-ttu-id="6c237-115">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="6c237-115">Permissions</span></span>

<span data-ttu-id="6c237-116">Per accedere ai classificatori nell'interfaccia utente:</span><span class="sxs-lookup"><span data-stu-id="6c237-116">To access classifiers in the UI:</span></span> 

- <span data-ttu-id="6c237-117">l'amministratore globale deve optare per il tenant per creare classificatori personalizzati.</span><span class="sxs-lookup"><span data-stu-id="6c237-117">the Global admin needs to opt in for the tenant to create custom classifiers.</span></span>
- <span data-ttu-id="6c237-118">L'amministratore della conformità o il ruolo di analisi dei dati è necessario per formare un classificatore.</span><span class="sxs-lookup"><span data-stu-id="6c237-118">Compliance Administrator or Data Investigation role is required to train a classifier.</span></span>

<span data-ttu-id="6c237-119">Sono necessari account con queste autorizzazioni per l'utilizzo dei classificatori in questi scenari:</span><span class="sxs-lookup"><span data-stu-id="6c237-119">You'll need accounts with these permissions to use classifiers in these scenarios:</span></span>

- <span data-ttu-id="6c237-120">Scenario dei criteri per l'etichetta di conservazione: ruoli Gestione record e gestione conservazione</span><span class="sxs-lookup"><span data-stu-id="6c237-120">Retention label policy scenario: Record Management and Retention Management roles</span></span> 
- <span data-ttu-id="6c237-121">Scenario di criteri per le etichette di riservatezza: amministratore della sicurezza, amministratore conformità, amministratore dei dati di conformità</span><span class="sxs-lookup"><span data-stu-id="6c237-121">Sensitivity label policy scenario: Security Administrator, Compliance Administrator, Compliance Data Administrator</span></span>
- <span data-ttu-id="6c237-122">Scenario di criteri di conformità della comunicazione: amministratore di gestione dei rischi Insider, Responsabile Revisione di supervisione</span><span class="sxs-lookup"><span data-stu-id="6c237-122">Communication compliance policy scenario: Insider Risk Management Admin, Supervisory Review Administrator</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="6c237-123">Per impostazione predefinita, solo l'utente che crea un classificatore personalizzato può formare ed esaminare le stime eseguite dal classificatore.</span><span class="sxs-lookup"><span data-stu-id="6c237-123">By default, only the user who creates a custom classifier can train and review predictions made by that classifier.</span></span>

## <a name="prepare-for-a-custom-trainable-classifier"></a><span data-ttu-id="6c237-124">Prepararsi per un classificatore addestrabile personalizzato</span><span class="sxs-lookup"><span data-stu-id="6c237-124">Prepare for a custom trainable classifier</span></span> 

<span data-ttu-id="6c237-125">È utile comprendere cosa è coinvolto nella creazione di un classificatore addestrabile personalizzato prima dell'immersione.</span><span class="sxs-lookup"><span data-stu-id="6c237-125">It's helpful to understand what's involved in creating a custom trainable classifier before you dive in.</span></span> 

### <a name="timeline"></a><span data-ttu-id="6c237-126">Sequenza temporale</span><span class="sxs-lookup"><span data-stu-id="6c237-126">Timeline</span></span>

<span data-ttu-id="6c237-127">Questa sequenza temporale riflette una distribuzione di esempio dei classificatori addestrabili.</span><span class="sxs-lookup"><span data-stu-id="6c237-127">This timeline reflects a sample deployment of trainable classifiers.</span></span>

![addestrare-classificatore-sequenza temporale](../media/trainable-classifier-deployment-timeline_border.png)

> [!TIP]
> <span data-ttu-id="6c237-129">L'opzione opt-in è necessaria per la prima volta per i classificatori addestrabili.</span><span class="sxs-lookup"><span data-stu-id="6c237-129">Opt-in is required the first time for trainable classifiers.</span></span> <span data-ttu-id="6c237-130">Per completare una valutazione di base del contenuto delle organizzazioni, sono necessari dodici giorni per Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6c237-130">It takes twelve days for Microsoft 365 to complete a baseline evaluation of your organizations content.</span></span> <span data-ttu-id="6c237-131">Contattare l'amministratore globale per iniziare a utilizzare il processo di opt-in.</span><span class="sxs-lookup"><span data-stu-id="6c237-131">Contact your global administrator to kick off the opt-in process.</span></span>

### <a name="overall-workflow"></a><span data-ttu-id="6c237-132">Flusso di lavoro globale</span><span class="sxs-lookup"><span data-stu-id="6c237-132">Overall workflow</span></span>

<span data-ttu-id="6c237-133">Per ulteriori informazioni sul flusso di lavoro globale della creazione di classificatori addestrabili personalizzati, vedere [flow Process per la creazione di classificatori addestrabili per i clienti](classifier-learn-about.md#process-flow-for-creating-custom-classifiers).</span><span class="sxs-lookup"><span data-stu-id="6c237-133">To understand more about the overall workflow of creating custom trainable classifiers, see [Process flow for creating customer trainable classifiers](classifier-learn-about.md#process-flow-for-creating-custom-classifiers).</span></span>

### <a name="seed-content"></a><span data-ttu-id="6c237-134">Contenuto del seeding</span><span class="sxs-lookup"><span data-stu-id="6c237-134">Seed content</span></span>

<span data-ttu-id="6c237-135">Quando si desidera che un classificatore addestrabile sia in grado di identificare in modo indipendente e accurato un elemento come in particolare la categoria di contenuto, è necessario innanzitutto presentarlo con numerosi esempi del tipo di contenuto nella categoria.</span><span class="sxs-lookup"><span data-stu-id="6c237-135">When you want a trainable classifier to independently and accurately identify an item as being in particular category of content, you first have to present it with many samples of the type of content that are in the category.</span></span> <span data-ttu-id="6c237-136">L'alimentazione dei campioni al classificatore addestrabile è nota come *seeding*.</span><span class="sxs-lookup"><span data-stu-id="6c237-136">This feeding of samples to the trainable classifier is known as *seeding*.</span></span> <span data-ttu-id="6c237-137">Il contenuto del seeding viene selezionato da un essere umano e viene giudicato per rappresentare la categoria di contenuto.</span><span class="sxs-lookup"><span data-stu-id="6c237-137">Seed content is selected by a human and is judged to represent the category of content.</span></span>

> [!TIP]
> <span data-ttu-id="6c237-138">È necessario avere almeno 50 campioni positivi e ben 500.</span><span class="sxs-lookup"><span data-stu-id="6c237-138">You need to have at least 50 positive samples and as many as 500.</span></span> <span data-ttu-id="6c237-139">Il classificatore addestrativo elaborerà fino a 500 campioni creati più recenti (per data e timestamp creati dal file).</span><span class="sxs-lookup"><span data-stu-id="6c237-139">The trainable classifier will process up to the 500 most recent created samples (by file created date/time stamp).</span></span> <span data-ttu-id="6c237-140">Più esempi vengono forniti, maggiore è la precisione delle stime che verranno apportate dal classificatore.</span><span class="sxs-lookup"><span data-stu-id="6c237-140">The more samples you provide, the more accurate the predictions the classifier will make.</span></span>

### <a name="testing-content"></a><span data-ttu-id="6c237-141">Test del contenuto</span><span class="sxs-lookup"><span data-stu-id="6c237-141">Testing content</span></span>

<span data-ttu-id="6c237-142">Dopo che il classificatore addestratore ha elaborato campioni positivi sufficienti per creare un modello di stima, è necessario verificare le stime che consente di verificare se il classificatore può distinguere correttamente tra gli elementi che corrispondono alla categoria e gli elementi che non lo fanno.</span><span class="sxs-lookup"><span data-stu-id="6c237-142">Once the trainable classifier has processed enough positive samples to build a prediction model, you need to test the predictions it makes to see if the classifier can correctly distinguish between items that match the category and items that don't.</span></span> <span data-ttu-id="6c237-143">A tale scopo, selezionare un altro gruppo di contenuto umano raccolto, che è costituito da esempi che devono rientrare nella categoria e gli esempi che non sono necessari.</span><span class="sxs-lookup"><span data-stu-id="6c237-143">You do this by selecting another, hopefully larger, set of human picked content that consists of samples that should fall into the category and samples that won't.</span></span> <span data-ttu-id="6c237-144">È consigliabile eseguire il test con dati diversi rispetto ai dati di inizializzazione iniziali forniti per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="6c237-144">You should test with different data than the initial seed data you first provided.</span></span> <span data-ttu-id="6c237-145">Dopo averli elaborati, si procede manualmente ai risultati e si verifica se ogni previsione è corretta, non corretta o non si è certi.</span><span class="sxs-lookup"><span data-stu-id="6c237-145">Once it processes those, you manually go through the results and verify whether each prediction is correct, incorrect, or you aren't sure.</span></span> <span data-ttu-id="6c237-146">Il classificatore addestrabile utilizza questi commenti e suggerimenti per migliorare il modello di stima.</span><span class="sxs-lookup"><span data-stu-id="6c237-146">The trainable classifier uses this feedback to improve its prediction model.</span></span>

> [!TIP]
> <span data-ttu-id="6c237-147">Per ottenere risultati ottimali, è necessario che almeno 200 elementi del campione di test siano distribuiti con una distribuzione uniforme di corrispondenze positive e negative.</span><span class="sxs-lookup"><span data-stu-id="6c237-147">For best results, have at least 200 items in your test sample set with an even distribution of positive and negative matches.</span></span>

## <a name="how-to-create-a-trainable-classifier"></a><span data-ttu-id="6c237-148">Come creare un classificatore addestrabile</span><span class="sxs-lookup"><span data-stu-id="6c237-148">How to create a trainable classifier</span></span>

1. <span data-ttu-id="6c237-149">Raccogliere tra gli elementi di contenuto di 50-500 Seed.</span><span class="sxs-lookup"><span data-stu-id="6c237-149">Collect between 50-500 seed content items.</span></span> <span data-ttu-id="6c237-150">Questi devono essere solo campioni che rappresentano fortemente il tipo di contenuto che si desidera che il classificatore addestrabile identifichi positivamente come nella Categoria classificazione.</span><span class="sxs-lookup"><span data-stu-id="6c237-150">These must be only samples that strongly represent the type of content you want the trainable classifier to positively identify as being in the classification category.</span></span> <span data-ttu-id="6c237-151">Per i tipi di file supportati, vedere le estensioni di file sottoposte [a ricerca per indicizzazione e i tipi di file analizzati in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) .</span><span class="sxs-lookup"><span data-stu-id="6c237-151">See, [Default crawled file name extensions and parsed file types in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) for the supported file types.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="6c237-152">Gli elementi di esempio Seed e test non devono essere crittografati e devono essere in inglese.</span><span class="sxs-lookup"><span data-stu-id="6c237-152">The seed and test sample items must not be encrypted and they must be in English.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="6c237-153">Verificare che gli elementi del set di Seed siano esempi **forti** della categoria.</span><span class="sxs-lookup"><span data-stu-id="6c237-153">Make sure the items in your seed set are **strong** examples of the category.</span></span> <span data-ttu-id="6c237-154">Il classificatore addestrabile crea inizialmente il modello in base alle operazioni con cui viene eseguito il seeding.</span><span class="sxs-lookup"><span data-stu-id="6c237-154">The trainable classifier initially builds its model based on what you seed it with.</span></span> <span data-ttu-id="6c237-155">Il classificatore presuppone che tutti gli esempi di sementi siano forti positivi e che non sia possibile sapere se un campione è una corrispondenza debole o negativa per la categoria.</span><span class="sxs-lookup"><span data-stu-id="6c237-155">The classifier assumes all seed samples are strong positives and has no way of knowing if a sample is a weak or negative match to the category.</span></span>

2. <span data-ttu-id="6c237-156">Inserire il contenuto di inizializzazione in una cartella di SharePoint Online dedicata a contenere *solo il contenuto del seeding*.</span><span class="sxs-lookup"><span data-stu-id="6c237-156">Place the seed content in a SharePoint Online folder that is dedicated to holding *the seed content only*.</span></span> <span data-ttu-id="6c237-157">Prendere nota dell'URL del sito, della raccolta e della cartella.</span><span class="sxs-lookup"><span data-stu-id="6c237-157">Make note of the site, library, and folder URL.</span></span>

   > [!TIP]
   > <span data-ttu-id="6c237-158">Se si crea un nuovo sito e una nuova cartella per i dati di seeding, è possibile eseguire l'indicizzazione di almeno un'ora affinché tale percorso venga indicizzato prima di creare il classificatore addestrabile che utilizzerà tali dati.</span><span class="sxs-lookup"><span data-stu-id="6c237-158">If you create a new site and folder for your seed data, allow at least an hour for that location to be indexed before creating the trainable classifier that will use that seed data.</span></span>

3. <span data-ttu-id="6c237-159">Accedere a Microsoft 365 Compliance Center with Compliance admin or Security admin Role Access e aprire **Microsoft 365 Compliance Center** o **Microsoft 365 Security Center**  >  **Data Classification**.</span><span class="sxs-lookup"><span data-stu-id="6c237-159">Sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** or **Microsoft 365 security center** > **Data classification**.</span></span>

4. <span data-ttu-id="6c237-160">Scegliere la scheda **classificatori addestrabili** .</span><span class="sxs-lookup"><span data-stu-id="6c237-160">Choose the **Trainable classifiers** tab.</span></span>

5. <span data-ttu-id="6c237-161">Scegliere **Crea classificatore addestrabile**.</span><span class="sxs-lookup"><span data-stu-id="6c237-161">Choose **Create trainable classifier**.</span></span>

6. <span data-ttu-id="6c237-162">Inserire i valori adatti per i `Name` `Description` campi e della categoria di elementi che si desidera vengano identificati dal classificatore addestrabile.</span><span class="sxs-lookup"><span data-stu-id="6c237-162">Fill in appropriate values for the `Name` and `Description` fields of the category of items you want this trainable classifier to identify.</span></span>

7. <span data-ttu-id="6c237-163">Scegliere il sito di SharePoint Online, la raccolta e l'URL della cartella per il sito di contenuto Seed del passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="6c237-163">Pick the SharePoint Online site, library, and folder URL for the seed content site from step 2.</span></span> <span data-ttu-id="6c237-164">Scegliere `Add` .</span><span class="sxs-lookup"><span data-stu-id="6c237-164">Choose `Add`.</span></span>

8. <span data-ttu-id="6c237-165">Rivedere le impostazioni e scegliere `Create trainable classifier` .</span><span class="sxs-lookup"><span data-stu-id="6c237-165">Review the settings and choose `Create trainable classifier`.</span></span>

9. <span data-ttu-id="6c237-166">Entro 24 ore, il classificatore addestrativo elaborerà i dati di seeding e realizzerà un modello di stima.</span><span class="sxs-lookup"><span data-stu-id="6c237-166">Within 24 hours the trainable classifier will process the seed data and build a prediction model.</span></span> <span data-ttu-id="6c237-167">Lo stato del classificatore è `In progress` durante l'elaborazione dei dati di seeding.</span><span class="sxs-lookup"><span data-stu-id="6c237-167">The classifier status is `In progress` while it processes the seed data.</span></span> <span data-ttu-id="6c237-168">Quando il classificatore ha terminato di elaborare i dati di seeding, lo stato cambia in `Need test items` .</span><span class="sxs-lookup"><span data-stu-id="6c237-168">When the classifier is finished processing the seed data, the status changes to `Need test items`.</span></span>

10. <span data-ttu-id="6c237-169">È ora possibile visualizzare la pagina dei dettagli scegliendo il classificatore.</span><span class="sxs-lookup"><span data-stu-id="6c237-169">You can now view the details page by choosing the classifier.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="6c237-170">![classificatore addestrabile pronto per il testing](../media/classifier-trainable-ready-to-test-detail.png)</span><span class="sxs-lookup"><span data-stu-id="6c237-170">![trainable classifier ready for testing](../media/classifier-trainable-ready-to-test-detail.png)</span></span>

11. <span data-ttu-id="6c237-171">Raccogliere almeno 200 elementi di contenuto di prova (10.000 max) per ottenere risultati ottimali.</span><span class="sxs-lookup"><span data-stu-id="6c237-171">Collect at least 200 test content items (10,000 max) for best results.</span></span> <span data-ttu-id="6c237-172">Queste devono essere una combinazione di elementi che sono forti positivi, negativi forti e alcuni che sono un po' meno evidenti nella loro natura.</span><span class="sxs-lookup"><span data-stu-id="6c237-172">These should be a mix of items that are strong positives, strong negatives and some that are a little less obvious in their nature.</span></span> <span data-ttu-id="6c237-173">Per i tipi di file supportati, vedere le estensioni di file sottoposte [a ricerca per indicizzazione e i tipi di file analizzati in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) .</span><span class="sxs-lookup"><span data-stu-id="6c237-173">See, [Default crawled file name extensions and parsed file types in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) for the supported file types.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="6c237-174">Gli elementi di esempio non devono essere crittografati e devono essere in inglese.</span><span class="sxs-lookup"><span data-stu-id="6c237-174">The sample items must not be encrypted and they must be in English.</span></span>

12. <span data-ttu-id="6c237-175">Inserire il contenuto del test in una cartella di SharePoint Online dedicata alla conservazione *del solo contenuto del test*.</span><span class="sxs-lookup"><span data-stu-id="6c237-175">Place the test content in a SharePoint Online folder that is dedicated to holding *the test content only*.</span></span> <span data-ttu-id="6c237-176">Prendere nota del sito, della raccolta e dell'URL della cartella di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="6c237-176">Make note of the SharePoint Online site, library, and folder URL.</span></span>

    > [!TIP]
    > <span data-ttu-id="6c237-177">Se si crea un nuovo sito e una nuova cartella per i dati di test, è possibile che la posizione venga indicizzata per almeno un'ora prima di creare il classificatore addestrabile che utilizzerà tali dati.</span><span class="sxs-lookup"><span data-stu-id="6c237-177">If you create a new site and folder for your test data, allow at least an hour for that location to be indexed before creating the trainable classifier that will use that seed data.</span></span>

13. <span data-ttu-id="6c237-178">Scegliere `Add items to test` .</span><span class="sxs-lookup"><span data-stu-id="6c237-178">Choose `Add items to test`.</span></span>

14. <span data-ttu-id="6c237-179">Scegliere il sito di SharePoint Online, la raccolta e l'URL della cartella per il sito di contenuto di test dal passaggio 12.</span><span class="sxs-lookup"><span data-stu-id="6c237-179">Pick the SharePoint Online site, library, and folder URL for the test content site from step 12.</span></span> <span data-ttu-id="6c237-180">Scegliere `Add` .</span><span class="sxs-lookup"><span data-stu-id="6c237-180">Choose `Add`.</span></span>

15. <span data-ttu-id="6c237-181">Completare la procedura guidata scegliendo `Done` .</span><span class="sxs-lookup"><span data-stu-id="6c237-181">Finish the wizard by choosing `Done`.</span></span> <span data-ttu-id="6c237-182">Il classificatore addestrabile richiederà fino a un'ora per l'elaborazione dei file di test.</span><span class="sxs-lookup"><span data-stu-id="6c237-182">Your trainable classifier will take up to an hour to process the test files.</span></span>

16. <span data-ttu-id="6c237-183">Quando si esegue l'elaborazione dei file di test da parte del classificatore addestrabile, lo stato nella pagina dei dettagli cambia `Ready to review` .</span><span class="sxs-lookup"><span data-stu-id="6c237-183">When the trainable classifier is done processing your test files, the status on the details page will change to `Ready to review`.</span></span> <span data-ttu-id="6c237-184">Se è necessario aumentare le dimensioni del campione di test, scegliere `Add items to test` e consentire al classificatore addestrabile di elaborare gli elementi aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="6c237-184">If you need to increase the test sample size, choose `Add items to test` and allow the trainable classifier to process the additional items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="6c237-185">![pronto per la revisione dello screenshot](../media/classifier-trainable-ready-to-review-detail.png)</span><span class="sxs-lookup"><span data-stu-id="6c237-185">![ready to review screenshot](../media/classifier-trainable-ready-to-review-detail.png)</span></span>

17. <span data-ttu-id="6c237-186">Scegliere la `Tested items to review` scheda per esaminare gli elementi.</span><span class="sxs-lookup"><span data-stu-id="6c237-186">Choose `Tested items to review` tab to review items.</span></span>

18. <span data-ttu-id="6c237-187">Microsoft 365 presenterà 30 elementi alla volta.</span><span class="sxs-lookup"><span data-stu-id="6c237-187">Microsoft 365 will present 30 items at a time.</span></span> <span data-ttu-id="6c237-188">Verificarli e nella `We predict this item is "Relevant". Do you agree?` casella scegliere uno `Yes` o più `No` o `Not sure, skip to next item` .</span><span class="sxs-lookup"><span data-stu-id="6c237-188">Review them and in the `We predict this item is "Relevant". Do you agree?` box choose either `Yes` or `No` or `Not sure, skip to next item`.</span></span> <span data-ttu-id="6c237-189">L'accuratezza del modello viene aggiornata automaticamente dopo ogni 30 elementi.</span><span class="sxs-lookup"><span data-stu-id="6c237-189">Model accuracy is automatically updated after every 30 items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="6c237-190">![casella di controllo elementi](../media/classifier-trainable-review-detail.png)</span><span class="sxs-lookup"><span data-stu-id="6c237-190">![review items box](../media/classifier-trainable-review-detail.png)</span></span>

19. <span data-ttu-id="6c237-191">Esaminare *almeno 200 elementi* .</span><span class="sxs-lookup"><span data-stu-id="6c237-191">Review *at least* 200 items.</span></span> <span data-ttu-id="6c237-192">Dopo che il Punteggio di accuratezza si è stabilizzato, l'opzione **pubblicazione** diventerà disponibile e lo stato del classificatore diventerà `Ready to use` .</span><span class="sxs-lookup"><span data-stu-id="6c237-192">Once the accuracy score has stabilized, the **publish** option will become available and the classifier status will say `Ready to use`.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="6c237-193">![Punteggio di precisione e pronto per la pubblicazione](../media/classifier-trainable-review-ready-to-publish.png)</span><span class="sxs-lookup"><span data-stu-id="6c237-193">![accuracy score and ready to publish](../media/classifier-trainable-review-ready-to-publish.png)</span></span>

20. <span data-ttu-id="6c237-194">Pubblicare il classificatore.</span><span class="sxs-lookup"><span data-stu-id="6c237-194">Publish the classifier.</span></span>

21. <span data-ttu-id="6c237-195">Dopo aver pubblicato il classificatore sarà disponibile come condizione in [Office auto-Labeling con etichette di riservatezza](apply-sensitivity-label-automatically.md), [applicare automaticamente i criteri delle etichette di conservazione in base a una condizione](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) e in [conformità alla comunicazione](communication-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="6c237-195">Once published your classifier will be available as a condition in [Office auto-labeling with sensitivity labels](apply-sensitivity-label-automatically.md), [auto-apply retention label policy based on a condition](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) and in [Communication compliance](communication-compliance.md).</span></span>
