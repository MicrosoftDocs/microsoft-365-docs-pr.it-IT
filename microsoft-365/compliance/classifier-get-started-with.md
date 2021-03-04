---
title: Per iniziare con i classificatori sottoponibili a training
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
description: Un classificatore di Microsoft 365 è uno strumento che è possibile formare per riconoscere vari tipi di contenuto fornendogli esempi da esaminare. Questo articolo illustra come creare e formare un classificatore personalizzato e come riqualificarli per aumentare l'accuratezza.
ms.openlocfilehash: a73acd7665cd23f13329bb5db4e890b0f3b0d861
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423295"
---
# <a name="get-started-with-trainable-classifiers"></a><span data-ttu-id="2602a-104">Per iniziare con i classificatori sottoponibili a training</span><span class="sxs-lookup"><span data-stu-id="2602a-104">Get started with trainable classifiers</span></span>

<span data-ttu-id="2602a-105">Un classificatore formabile di Microsoft 365 è uno strumento che è possibile formare per riconoscere vari tipi di contenuto fornendogli esempi da esaminare.</span><span class="sxs-lookup"><span data-stu-id="2602a-105">A Microsoft 365 trainable classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="2602a-106">Una volta preparato, è possibile utilizzarlo per identificare l'elemento per l'applicazione delle etichette di riservatezza di Office, dei criteri di conformità delle comunicazioni e dei criteri delle etichette di conservazione.</span><span class="sxs-lookup"><span data-stu-id="2602a-106">Once trained, you can use it to identify item for application of Office sensitivity labels, Communications compliance policies, and retention label policies.</span></span>

<span data-ttu-id="2602a-107">La creazione di un classificatore sotto forma di un classificatore sotto forma di training personalizzato implica innanzitutto la creazione di campioni selezionati dall'utente e che corrispondano in modo positivo alla categoria.</span><span class="sxs-lookup"><span data-stu-id="2602a-107">Creating a custom trainable classifier first involves giving it samples that are human picked and positively match the category.</span></span> <span data-ttu-id="2602a-108">Quindi, dopo averli elaborati, puoi testare la capacità dei classificatori di prevedere fornendo una combinazione di campioni positivi e negativi.</span><span class="sxs-lookup"><span data-stu-id="2602a-108">Then, after it has processed those, you test the classifiers ability to predict by giving it a mix of positive and negative samples.</span></span> <span data-ttu-id="2602a-109">Questo articolo illustra come creare e formare un classificatore personalizzato e come migliorare le prestazioni dei classificatori e dei classificatori pre-addestrati personalizzati nel corso della loro durata tramite la riqualificazione.</span><span class="sxs-lookup"><span data-stu-id="2602a-109">This article shows you how to create and train a custom classifier and how to improve the performance of custom trainable classifiers and pre-trained classifiers over their lifetime through retraining.</span></span>

<span data-ttu-id="2602a-110">Per ulteriori informazioni sui diversi tipi di classificatori, vedere Informazioni sui classificatori disponibili [per il training.](classifier-learn-about.md)</span><span class="sxs-lookup"><span data-stu-id="2602a-110">To learn more about the different types of classifiers, see [Learn about trainable classifiers](classifier-learn-about.md).</span></span>

<span data-ttu-id="2602a-111">Guardare questo video per un breve riepilogo della creazione di un classificatore formabile.</span><span class="sxs-lookup"><span data-stu-id="2602a-111">Watch this video for a quick summary of creating a trainable classifier.</span></span> <span data-ttu-id="2602a-112">Dovrai comunque leggere questo articolo completo per ottenere i dettagli.</span><span class="sxs-lookup"><span data-stu-id="2602a-112">You'll still need to read this full article to get the details.</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWyGL7]


## <a name="prerequisites"></a><span data-ttu-id="2602a-113">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="2602a-113">Prerequisites</span></span>

### <a name="licensing-requirements"></a><span data-ttu-id="2602a-114">Requisiti per la licenza</span><span class="sxs-lookup"><span data-stu-id="2602a-114">Licensing requirements</span></span>

<span data-ttu-id="2602a-115">I classificatori sono una funzionalità di conformità di Microsoft 365 E5 o E5.</span><span class="sxs-lookup"><span data-stu-id="2602a-115">Classifiers are a Microsoft 365 E5, or E5 Compliance feature.</span></span> <span data-ttu-id="2602a-116">È necessario disporre di uno di questi abbonamenti per utilizzarli.</span><span class="sxs-lookup"><span data-stu-id="2602a-116">You must have one of these subscriptions to make use of them.</span></span>

### <a name="permissions"></a><span data-ttu-id="2602a-117">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="2602a-117">Permissions</span></span>

<span data-ttu-id="2602a-118">Per accedere ai classificatori nell'interfaccia utente:</span><span class="sxs-lookup"><span data-stu-id="2602a-118">To access classifiers in the UI:</span></span> 

- <span data-ttu-id="2602a-119">L'amministratore globale deve acconsentire esplicitamente al tenant per creare classificatori personalizzati.</span><span class="sxs-lookup"><span data-stu-id="2602a-119">the Global admin needs to opt in for the tenant to create custom classifiers.</span></span>
- <span data-ttu-id="2602a-120">Il ruolo amministratore di conformità è necessario per formare un classificatore.</span><span class="sxs-lookup"><span data-stu-id="2602a-120">Compliance Administrator role is required to train a classifier.</span></span>

<span data-ttu-id="2602a-121">Saranno necessari account con queste autorizzazioni per usare i classificatori in questi scenari:</span><span class="sxs-lookup"><span data-stu-id="2602a-121">You'll need accounts with these permissions to use classifiers in these scenarios:</span></span>

- <span data-ttu-id="2602a-122">Scenario dei criteri di etichetta di conservazione: ruoli Gestione record e Gestione conservazione</span><span class="sxs-lookup"><span data-stu-id="2602a-122">Retention label policy scenario: Record Management and Retention Management roles</span></span> 
- <span data-ttu-id="2602a-123">Scenario dei criteri per le etichette di riservatezza: Amministratore della sicurezza, Amministratore conformità, Amministratore dati di conformità</span><span class="sxs-lookup"><span data-stu-id="2602a-123">Sensitivity label policy scenario: Security Administrator, Compliance Administrator, Compliance Data Administrator</span></span>
- <span data-ttu-id="2602a-124">Scenario dei criteri di conformità delle comunicazioni: Insider Risk Management Admin, Supervisory Review Administrator</span><span class="sxs-lookup"><span data-stu-id="2602a-124">Communication compliance policy scenario: Insider Risk Management Admin, Supervisory Review Administrator</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="2602a-125">Per impostazione predefinita, solo l'utente che crea un classificatore personalizzato può formare ed esaminare le previsioni effettuate da tale classificatore.</span><span class="sxs-lookup"><span data-stu-id="2602a-125">By default, only the user who creates a custom classifier can train and review predictions made by that classifier.</span></span>

## <a name="prepare-for-a-custom-trainable-classifier"></a><span data-ttu-id="2602a-126">Preparare un classificatore di cui è possibile utilizzare il training personalizzato</span><span class="sxs-lookup"><span data-stu-id="2602a-126">Prepare for a custom trainable classifier</span></span> 

<span data-ttu-id="2602a-127">È utile comprendere cosa implica la creazione di un classificatore di cui è possibile eseguire il training personalizzato prima di procedere.</span><span class="sxs-lookup"><span data-stu-id="2602a-127">It's helpful to understand what's involved in creating a custom trainable classifier before you dive in.</span></span> 

### <a name="timeline"></a><span data-ttu-id="2602a-128">Sequenza temporale</span><span class="sxs-lookup"><span data-stu-id="2602a-128">Timeline</span></span>

<span data-ttu-id="2602a-129">Questa sequenza temporale riflette una distribuzione di esempio di classificatori sotto forma di sottosezioni.</span><span class="sxs-lookup"><span data-stu-id="2602a-129">This timeline reflects a sample deployment of trainable classifiers.</span></span>

![trainable-classifier-timeline](../media/trainable-classifier-deployment-timeline_border.png)

> [!TIP]
> <span data-ttu-id="2602a-131">Il consenso esplicito è necessario per la prima volta per i classificatori di cui è possibile eseguire il training.</span><span class="sxs-lookup"><span data-stu-id="2602a-131">Opt-in is required the first time for trainable classifiers.</span></span> <span data-ttu-id="2602a-132">Sono necessari 12 giorni prima che Microsoft 365 completi una valutazione di base dei contenuti delle organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="2602a-132">It takes twelve days for Microsoft 365 to complete a baseline evaluation of your organizations content.</span></span> <span data-ttu-id="2602a-133">Contatta l'amministratore globale per avviare il processo di consenso esplicito.</span><span class="sxs-lookup"><span data-stu-id="2602a-133">Contact your global administrator to kick off the opt-in process.</span></span>

### <a name="overall-workflow"></a><span data-ttu-id="2602a-134">Flusso di lavoro complessivo</span><span class="sxs-lookup"><span data-stu-id="2602a-134">Overall workflow</span></span>

<span data-ttu-id="2602a-135">Per ulteriori informazioni sul flusso di lavoro complessivo della creazione di classificatori trainabili personalizzati, vedere Flusso di processo per la creazione di classificatori che possono [essere addestrati dal cliente.](classifier-learn-about.md#process-flow-for-creating-custom-classifiers)</span><span class="sxs-lookup"><span data-stu-id="2602a-135">To understand more about the overall workflow of creating custom trainable classifiers, see [Process flow for creating customer trainable classifiers](classifier-learn-about.md#process-flow-for-creating-custom-classifiers).</span></span>

### <a name="seed-content"></a><span data-ttu-id="2602a-136">Contenuto seed</span><span class="sxs-lookup"><span data-stu-id="2602a-136">Seed content</span></span>

<span data-ttu-id="2602a-137">Quando si desidera che un classificatore sotto forma di training identifitta in modo indipendente e accurato un elemento come in una determinata categoria di contenuto, è innanzitutto necessario presentarlo con molti esempi del tipo di contenuto presente nella categoria.</span><span class="sxs-lookup"><span data-stu-id="2602a-137">When you want a trainable classifier to independently and accurately identify an item as being in particular category of content, you first have to present it with many samples of the type of content that are in the category.</span></span> <span data-ttu-id="2602a-138">Questa distribuzione di campioni al classificatore di cui è possibile eseguire il training è nota come *seeding.*</span><span class="sxs-lookup"><span data-stu-id="2602a-138">This feeding of samples to the trainable classifier is known as *seeding*.</span></span> <span data-ttu-id="2602a-139">Il contenuto di seed viene selezionato da un essere umano e viene scelto per rappresentare la categoria di contenuto.</span><span class="sxs-lookup"><span data-stu-id="2602a-139">Seed content is selected by a human and is judged to represent the category of content.</span></span>

> [!TIP]
> <span data-ttu-id="2602a-140">Devi avere almeno 50 campioni positivi e fino a 500.</span><span class="sxs-lookup"><span data-stu-id="2602a-140">You need to have at least 50 positive samples and as many as 500.</span></span> <span data-ttu-id="2602a-141">Il classificatore di cui è possibile eseguire il training eelaborare fino ai 500 esempi creati più recenti (in base al timestamp/data di creazione del file).</span><span class="sxs-lookup"><span data-stu-id="2602a-141">The trainable classifier will process up to the 500 most recent created samples (by file created date/time stamp).</span></span> <span data-ttu-id="2602a-142">Più esempi fornisci, più accurate saranno le previsioni che il classificatore farà.</span><span class="sxs-lookup"><span data-stu-id="2602a-142">The more samples you provide, the more accurate the predictions the classifier will make.</span></span>

### <a name="testing-content"></a><span data-ttu-id="2602a-143">Test del contenuto</span><span class="sxs-lookup"><span data-stu-id="2602a-143">Testing content</span></span>

<span data-ttu-id="2602a-144">Dopo che il classificatore sotto forma di training ha elaborato un numero sufficiente di campioni positivi per creare un modello di previsione, devi testare le previsioni che effettua per verificare se il classificatore è in grado di distinguere correttamente tra gli elementi che corrispondono alla categoria e gli elementi che non lo fanno.</span><span class="sxs-lookup"><span data-stu-id="2602a-144">Once the trainable classifier has processed enough positive samples to build a prediction model, you need to test the predictions it makes to see if the classifier can correctly distinguish between items that match the category and items that don't.</span></span> <span data-ttu-id="2602a-145">A tale scopo, seleziona un altro set, probabilmente più grande, di contenuti selezionati dall'utente, costituiti da campioni che dovrebbero rientrare nella categoria e dai campioni che non lo saranno.</span><span class="sxs-lookup"><span data-stu-id="2602a-145">You do this by selecting another, hopefully larger, set of human picked content that consists of samples that should fall into the category and samples that won't.</span></span> <span data-ttu-id="2602a-146">È consigliabile eseguire il test con dati diversi rispetto ai dati di inizializzazione iniziali forniti per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="2602a-146">You should test with different data than the initial seed data you first provided.</span></span> <span data-ttu-id="2602a-147">Dopo averli elaborati, puoi passare manualmente attraverso i risultati e verificare se ogni previsione è corretta, errata o non sei sicuro.</span><span class="sxs-lookup"><span data-stu-id="2602a-147">Once it processes those, you manually go through the results and verify whether each prediction is correct, incorrect, or you aren't sure.</span></span> <span data-ttu-id="2602a-148">Il classificatore di cui è possibile eseguire il training usa questo feedback per migliorare il modello di previsione.</span><span class="sxs-lookup"><span data-stu-id="2602a-148">The trainable classifier uses this feedback to improve its prediction model.</span></span>

> [!TIP]
> <span data-ttu-id="2602a-149">Per ottenere risultati ottimali, impostare almeno 200 elementi nell'esempio di test con una distribuzione uniforme di corrispondenze positive e negative.</span><span class="sxs-lookup"><span data-stu-id="2602a-149">For best results, have at least 200 items in your test sample set with an even distribution of positive and negative matches.</span></span>

## <a name="how-to-create-a-trainable-classifier"></a><span data-ttu-id="2602a-150">Come creare un classificatore di cui è possibile eseguire il training</span><span class="sxs-lookup"><span data-stu-id="2602a-150">How to create a trainable classifier</span></span>

1. <span data-ttu-id="2602a-151">Raccogliere tra 50 e 500 elementi di contenuto di seed.</span><span class="sxs-lookup"><span data-stu-id="2602a-151">Collect between 50-500 seed content items.</span></span> <span data-ttu-id="2602a-152">Questi devono essere solo esempi che rappresentano in modo forte il tipo di contenuto che il classificatore sotto forma di training deve identificare in modo positivo nella categoria di classificazione.</span><span class="sxs-lookup"><span data-stu-id="2602a-152">These must be only samples that strongly represent the type of content you want the trainable classifier to positively identify as being in the classification category.</span></span> <span data-ttu-id="2602a-153">Per i tipi di file supportati, vedere [ Default crawled file name extensions and parsed file types in SharePoint](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) Server .</span><span class="sxs-lookup"><span data-stu-id="2602a-153">See, [Default crawled file name extensions and parsed file types in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) for the supported file types.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="2602a-154">Gli elementi di esempio di seed e test non devono essere crittografati e devono essere in inglese.</span><span class="sxs-lookup"><span data-stu-id="2602a-154">The seed and test sample items must not be encrypted and they must be in English.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="2602a-155">Assicurati che gli elementi nel set di seed siano **esempi** forti della categoria.</span><span class="sxs-lookup"><span data-stu-id="2602a-155">Make sure the items in your seed set are **strong** examples of the category.</span></span> <span data-ttu-id="2602a-156">Il classificatore di cui è possibile eseguire il training inizialmente crea il modello in base all'elemento con cui è stato creato il seeder.</span><span class="sxs-lookup"><span data-stu-id="2602a-156">The trainable classifier initially builds its model based on what you seed it with.</span></span> <span data-ttu-id="2602a-157">Il classificatore presuppone che tutti i campioni di seed siano positivi forti e non abbia modo di sapere se un campione è una corrispondenza debole o negativa alla categoria.</span><span class="sxs-lookup"><span data-stu-id="2602a-157">The classifier assumes all seed samples are strong positives and has no way of knowing if a sample is a weak or negative match to the category.</span></span>

2. <span data-ttu-id="2602a-158">Inserire il contenuto del seed in una cartella di SharePoint Online dedicata solo al *contenuto del seed.*</span><span class="sxs-lookup"><span data-stu-id="2602a-158">Place the seed content in a SharePoint Online folder that is dedicated to holding *the seed content only*.</span></span> <span data-ttu-id="2602a-159">Prendere nota dell'URL del sito, della raccolta e della cartella.</span><span class="sxs-lookup"><span data-stu-id="2602a-159">Make note of the site, library, and folder URL.</span></span>

   > [!TIP]
   > <span data-ttu-id="2602a-160">Se si crea un nuovo sito e una nuova cartella per i dati di seed, è necessario indicizzare almeno un'ora per tale posizione prima di creare il classificatore di cui è possibile eseguire il training che utilizzerà i dati di seed.</span><span class="sxs-lookup"><span data-stu-id="2602a-160">If you create a new site and folder for your seed data, allow at least an hour for that location to be indexed before creating the trainable classifier that will use that seed data.</span></span>

3. <span data-ttu-id="2602a-161">Accedere al Centro conformità Microsoft 365 con l'accesso al ruolo di amministratore della conformità o amministratore della sicurezza e aprire il Centro conformità **Microsoft 365** o la classificazione dei dati del Centro **sicurezza Microsoft 365.**  >  </span><span class="sxs-lookup"><span data-stu-id="2602a-161">Sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** or **Microsoft 365 security center** > **Data classification**.</span></span>

4. <span data-ttu-id="2602a-162">Scegliere la **scheda Classificatori trainabili.**</span><span class="sxs-lookup"><span data-stu-id="2602a-162">Choose the **Trainable classifiers** tab.</span></span>

5. <span data-ttu-id="2602a-163">Choose **Create trainable classifier**.</span><span class="sxs-lookup"><span data-stu-id="2602a-163">Choose **Create trainable classifier**.</span></span>

6. <span data-ttu-id="2602a-164">Compilare i valori appropriati per i campi e la categoria di elementi che si desidera identificare da `Name` `Description` questo classificatore sotto forma di training.</span><span class="sxs-lookup"><span data-stu-id="2602a-164">Fill in appropriate values for the `Name` and `Description` fields of the category of items you want this trainable classifier to identify.</span></span>

7. <span data-ttu-id="2602a-165">Selezionare l'URL del sito, della raccolta e della cartella di SharePoint Online per il sito di contenuto seme del passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="2602a-165">Pick the SharePoint Online site, library, and folder URL for the seed content site from step 2.</span></span> <span data-ttu-id="2602a-166">Scegliere `Add` .</span><span class="sxs-lookup"><span data-stu-id="2602a-166">Choose `Add`.</span></span>

8. <span data-ttu-id="2602a-167">Rivedere le impostazioni e scegliere `Create trainable classifier` .</span><span class="sxs-lookup"><span data-stu-id="2602a-167">Review the settings and choose `Create trainable classifier`.</span></span>

9. <span data-ttu-id="2602a-168">Entro 24 ore il classificatore che può eseguire il training eelaborare i dati di seed e creare un modello di previsione.</span><span class="sxs-lookup"><span data-stu-id="2602a-168">Within 24 hours the trainable classifier will process the seed data and build a prediction model.</span></span> <span data-ttu-id="2602a-169">Lo stato del classificatore è `In progress` durante l'elaborazione dei dati di seed.</span><span class="sxs-lookup"><span data-stu-id="2602a-169">The classifier status is `In progress` while it processes the seed data.</span></span> <span data-ttu-id="2602a-170">Al termine dell'elaborazione dei dati del seeder da parte del classificatore, lo stato viene modificato in `Need test items` .</span><span class="sxs-lookup"><span data-stu-id="2602a-170">When the classifier is finished processing the seed data, the status changes to `Need test items`.</span></span>

10. <span data-ttu-id="2602a-171">È ora possibile visualizzare la pagina dei dettagli scegliendo il classificatore.</span><span class="sxs-lookup"><span data-stu-id="2602a-171">You can now view the details page by choosing the classifier.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2602a-172">![Classificatore di cui è possibile eseguire il training pronto per il test](../media/classifier-trainable-ready-to-test-detail.png)</span><span class="sxs-lookup"><span data-stu-id="2602a-172">![trainable classifier ready for testing](../media/classifier-trainable-ready-to-test-detail.png)</span></span>

11. <span data-ttu-id="2602a-173">Raccogliere almeno 200 elementi di contenuto di test (10.000 max) per ottenere risultati ottimali.</span><span class="sxs-lookup"><span data-stu-id="2602a-173">Collect at least 200 test content items (10,000 max) for best results.</span></span> <span data-ttu-id="2602a-174">Questi devono essere una combinazione di elementi che sono positivi forti, negativi forti e alcuni che sono un po' meno ovvi nella loro natura.</span><span class="sxs-lookup"><span data-stu-id="2602a-174">These should be a mix of items that are strong positives, strong negatives and some that are a little less obvious in their nature.</span></span> <span data-ttu-id="2602a-175">Per i tipi di file supportati, vedere [ Default crawled file name extensions and parsed file types in SharePoint](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) Server .</span><span class="sxs-lookup"><span data-stu-id="2602a-175">See, [Default crawled file name extensions and parsed file types in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) for the supported file types.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="2602a-176">Gli elementi di esempio non devono essere crittografati e devono essere in inglese.</span><span class="sxs-lookup"><span data-stu-id="2602a-176">The sample items must not be encrypted and they must be in English.</span></span>

12. <span data-ttu-id="2602a-177">Inserire il contenuto di test in una cartella di SharePoint Online dedicata solo al contenuto *di test.*</span><span class="sxs-lookup"><span data-stu-id="2602a-177">Place the test content in a SharePoint Online folder that is dedicated to holding *the test content only*.</span></span> <span data-ttu-id="2602a-178">Prendere nota dell'URL del sito, della raccolta e della cartella di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="2602a-178">Make note of the SharePoint Online site, library, and folder URL.</span></span>

    > [!TIP]
    > <span data-ttu-id="2602a-179">Se si crea un nuovo sito e una nuova cartella per i dati di test, è necessario indicizzare almeno un'ora per tale posizione prima di creare il classificatore di cui è possibile eseguire il training che utilizzerà i dati di seed.</span><span class="sxs-lookup"><span data-stu-id="2602a-179">If you create a new site and folder for your test data, allow at least an hour for that location to be indexed before creating the trainable classifier that will use that seed data.</span></span>

13. <span data-ttu-id="2602a-180">Scegliere `Add items to test` .</span><span class="sxs-lookup"><span data-stu-id="2602a-180">Choose `Add items to test`.</span></span>

14. <span data-ttu-id="2602a-181">Selezionare l'URL del sito, della raccolta e della cartella di SharePoint Online per il sito di contenuto di prova dal passaggio 12.</span><span class="sxs-lookup"><span data-stu-id="2602a-181">Pick the SharePoint Online site, library, and folder URL for the test content site from step 12.</span></span> <span data-ttu-id="2602a-182">Scegliere `Add` .</span><span class="sxs-lookup"><span data-stu-id="2602a-182">Choose `Add`.</span></span>

15. <span data-ttu-id="2602a-183">Completare la procedura guidata scegliendo `Done` .</span><span class="sxs-lookup"><span data-stu-id="2602a-183">Finish the wizard by choosing `Done`.</span></span> <span data-ttu-id="2602a-184">Il classificatore che può eseguire il training può richiedere fino a un'ora per elaborare i file di test.</span><span class="sxs-lookup"><span data-stu-id="2602a-184">Your trainable classifier will take up to an hour to process the test files.</span></span>

16. <span data-ttu-id="2602a-185">Al termine dell'elaborazione dei file di test da parte del classificatore di cui è stato eseguito il training, lo stato nella pagina dei dettagli verrà modificato in `Ready to review` .</span><span class="sxs-lookup"><span data-stu-id="2602a-185">When the trainable classifier is done processing your test files, the status on the details page will change to `Ready to review`.</span></span> <span data-ttu-id="2602a-186">Se è necessario aumentare le dimensioni del campione di test, scegliere e consentire al `Add items to test` classificatore trainabile di elaborare gli elementi aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="2602a-186">If you need to increase the test sample size, choose `Add items to test` and allow the trainable classifier to process the additional items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2602a-187">![screenshot pronto per la revisione](../media/classifier-trainable-ready-to-review-detail.png)</span><span class="sxs-lookup"><span data-stu-id="2602a-187">![ready to review screenshot](../media/classifier-trainable-ready-to-review-detail.png)</span></span>

17. <span data-ttu-id="2602a-188">Scegliere `Tested items to review` la scheda per esaminare gli elementi.</span><span class="sxs-lookup"><span data-stu-id="2602a-188">Choose `Tested items to review` tab to review items.</span></span>

18. <span data-ttu-id="2602a-189">Microsoft 365 presenterà 30 elementi alla volta.</span><span class="sxs-lookup"><span data-stu-id="2602a-189">Microsoft 365 will present 30 items at a time.</span></span> <span data-ttu-id="2602a-190">Esaminarli e nella `We predict this item is "Relevant". Do you agree?` casella scegliere uno o `Yes` `No` . `Not sure, skip to next item`</span><span class="sxs-lookup"><span data-stu-id="2602a-190">Review them and in the `We predict this item is "Relevant". Do you agree?` box choose either `Yes` or `No` or `Not sure, skip to next item`.</span></span> <span data-ttu-id="2602a-191">L'accuratezza del modello viene aggiornata automaticamente ogni 30 elementi.</span><span class="sxs-lookup"><span data-stu-id="2602a-191">Model accuracy is automatically updated after every 30 items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2602a-192">![casella degli elementi da rivedere](../media/classifier-trainable-review-detail.png)</span><span class="sxs-lookup"><span data-stu-id="2602a-192">![review items box](../media/classifier-trainable-review-detail.png)</span></span>

19. <span data-ttu-id="2602a-193">Esaminare *almeno* 200 elementi.</span><span class="sxs-lookup"><span data-stu-id="2602a-193">Review *at least* 200 items.</span></span> <span data-ttu-id="2602a-194">Una volta che il punteggio di accuratezza si è stabilizzato, l'opzione **di** pubblicazione diventerà disponibile e lo stato del classificatore dirà `Ready to use` .</span><span class="sxs-lookup"><span data-stu-id="2602a-194">Once the accuracy score has stabilized, the **publish** option will become available and the classifier status will say `Ready to use`.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2602a-195">![punteggio di accuratezza e pronto per la pubblicazione](../media/classifier-trainable-review-ready-to-publish.png)</span><span class="sxs-lookup"><span data-stu-id="2602a-195">![accuracy score and ready to publish](../media/classifier-trainable-review-ready-to-publish.png)</span></span>

20. <span data-ttu-id="2602a-196">Pubblicare il classificatore.</span><span class="sxs-lookup"><span data-stu-id="2602a-196">Publish the classifier.</span></span>

21. <span data-ttu-id="2602a-197">Dopo la pubblicazione, il classificatore sarà disponibile come condizione nell'etichettatura automatica di [Office](apply-sensitivity-label-automatically.md)con etichette di riservatezza, applicare automaticamente i criteri delle etichette di conservazione in base [a](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) una condizione e in [Conformità alle comunicazioni.](communication-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="2602a-197">Once published your classifier will be available as a condition in [Office auto-labeling with sensitivity labels](apply-sensitivity-label-automatically.md), [auto-apply retention label policy based on a condition](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) and in [Communication compliance](communication-compliance.md).</span></span>
