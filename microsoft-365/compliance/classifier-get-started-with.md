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
description: Un Microsoft 365 classificatore è uno strumento che puoi formare per riconoscere diversi tipi di contenuto fornendogli esempi da esaminare. Questo articolo illustra come creare e formare un classificatore personalizzato e come riqualificarli per aumentare l'accuratezza.
ms.openlocfilehash: 3053e5154fb4e1ff39ce7db366ce4679bbb8911d
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286634"
---
# <a name="get-started-with-trainable-classifiers"></a><span data-ttu-id="84ea2-104">Per iniziare con i classificatori sottoponibili a training</span><span class="sxs-lookup"><span data-stu-id="84ea2-104">Get started with trainable classifiers</span></span>

<span data-ttu-id="84ea2-105">Un Microsoft 365 classificatore di cui è possibile eseguire il training è uno strumento che è possibile formare per riconoscere vari tipi di contenuto fornendogli esempi da esaminare.</span><span class="sxs-lookup"><span data-stu-id="84ea2-105">A Microsoft 365 trainable classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="84ea2-106">Una volta addestrato, è possibile utilizzarlo per identificare l'elemento per l'applicazione di Office di riservatezza, criteri di conformità delle comunicazioni e criteri di etichetta di conservazione.</span><span class="sxs-lookup"><span data-stu-id="84ea2-106">Once trained, you can use it to identify item for application of Office sensitivity labels, Communications compliance policies, and retention label policies.</span></span>

<span data-ttu-id="84ea2-107">La creazione di un classificatore sotto forma di training personalizzato comporta innanzitutto la creazione di campioni selezionati dall'utente e che corrispondono in modo positivo alla categoria.</span><span class="sxs-lookup"><span data-stu-id="84ea2-107">Creating a custom trainable classifier first involves giving it samples that are human picked and positively match the category.</span></span> <span data-ttu-id="84ea2-108">Quindi, dopo averli elaborati, puoi testare la capacità dei classificatori di prevedere fornendogli una combinazione di campioni positivi e negativi.</span><span class="sxs-lookup"><span data-stu-id="84ea2-108">Then, after it has processed those, you test the classifiers ability to predict by giving it a mix of positive and negative samples.</span></span> <span data-ttu-id="84ea2-109">Questo articolo illustra come creare e formare un classificatore personalizzato e come migliorare le prestazioni dei classificatori e dei classificatori pre-addestrabili personalizzati nel corso della loro durata tramite la riqualificazione.</span><span class="sxs-lookup"><span data-stu-id="84ea2-109">This article shows you how to create and train a custom classifier and how to improve the performance of custom trainable classifiers and pre-trained classifiers over their lifetime through retraining.</span></span>

<span data-ttu-id="84ea2-110">Per ulteriori informazioni sui diversi tipi di classificatori, vedere [Learn about trainable classifiers](classifier-learn-about.md).</span><span class="sxs-lookup"><span data-stu-id="84ea2-110">To learn more about the different types of classifiers, see [Learn about trainable classifiers](classifier-learn-about.md).</span></span>

<span data-ttu-id="84ea2-111">Guarda questo video per un breve riepilogo della creazione di un classificatore addestrabile.</span><span class="sxs-lookup"><span data-stu-id="84ea2-111">Watch this video for a quick summary of creating a trainable classifier.</span></span> <span data-ttu-id="84ea2-112">Dovrai comunque leggere questo articolo completo per ottenere i dettagli.</span><span class="sxs-lookup"><span data-stu-id="84ea2-112">You'll still need to read this full article to get the details.</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWyGL7]


## <a name="prerequisites"></a><span data-ttu-id="84ea2-113">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="84ea2-113">Prerequisites</span></span>

### <a name="licensing-requirements"></a><span data-ttu-id="84ea2-114">Requisiti di licenza</span><span class="sxs-lookup"><span data-stu-id="84ea2-114">Licensing requirements</span></span>

<span data-ttu-id="84ea2-115">I classificatori sono una Microsoft 365 E5 o E5 Compliance.</span><span class="sxs-lookup"><span data-stu-id="84ea2-115">Classifiers are a Microsoft 365 E5, or E5 Compliance feature.</span></span> <span data-ttu-id="84ea2-116">Per utilizzarle, è necessario disporre di una di queste sottoscrizioni.</span><span class="sxs-lookup"><span data-stu-id="84ea2-116">You must have one of these subscriptions to make use of them.</span></span>

### <a name="permissions"></a><span data-ttu-id="84ea2-117">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="84ea2-117">Permissions</span></span>

<span data-ttu-id="84ea2-118">Per accedere ai classificatori nell'interfaccia utente:</span><span class="sxs-lookup"><span data-stu-id="84ea2-118">To access classifiers in the UI:</span></span> 

- <span data-ttu-id="84ea2-119">l'amministratore globale deve acconsentire esplicitamente al tenant per creare classificatori personalizzati.</span><span class="sxs-lookup"><span data-stu-id="84ea2-119">the Global admin needs to opt in for the tenant to create custom classifiers.</span></span>
- <span data-ttu-id="84ea2-120">Il ruolo amministratore della conformità è necessario per formare un classificatore.</span><span class="sxs-lookup"><span data-stu-id="84ea2-120">Compliance Administrator role is required to train a classifier.</span></span>

<span data-ttu-id="84ea2-121">Per usare i classificatori in questi scenari, sono necessari account con queste autorizzazioni:</span><span class="sxs-lookup"><span data-stu-id="84ea2-121">You'll need accounts with these permissions to use classifiers in these scenarios:</span></span>

- <span data-ttu-id="84ea2-122">Scenario dei criteri di etichetta di conservazione: ruoli Gestione record e Gestione conservazione</span><span class="sxs-lookup"><span data-stu-id="84ea2-122">Retention label policy scenario: Record Management and Retention Management roles</span></span> 
- <span data-ttu-id="84ea2-123">Scenario dei criteri delle etichette di riservatezza: Amministratore della sicurezza, Amministratore conformità, Amministratore dati di conformità</span><span class="sxs-lookup"><span data-stu-id="84ea2-123">Sensitivity label policy scenario: Security Administrator, Compliance Administrator, Compliance Data Administrator</span></span>
- <span data-ttu-id="84ea2-124">Scenario dei criteri di conformità della comunicazione: Insider Risk Management Admin, Supervisory Review Administrator</span><span class="sxs-lookup"><span data-stu-id="84ea2-124">Communication compliance policy scenario: Insider Risk Management Admin, Supervisory Review Administrator</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="84ea2-125">Per impostazione predefinita, solo l'utente che crea un classificatore personalizzato può eseguire il training e rivedere le previsioni effettuate da tale classificatore.</span><span class="sxs-lookup"><span data-stu-id="84ea2-125">By default, only the user who creates a custom classifier can train and review predictions made by that classifier.</span></span>

## <a name="prepare-for-a-custom-trainable-classifier"></a><span data-ttu-id="84ea2-126">Preparare un classificatore addestrabile personalizzato</span><span class="sxs-lookup"><span data-stu-id="84ea2-126">Prepare for a custom trainable classifier</span></span> 

<span data-ttu-id="84ea2-127">È utile comprendere cosa comporta la creazione di un classificatore addestrabile personalizzato prima di tuffarsi.</span><span class="sxs-lookup"><span data-stu-id="84ea2-127">It's helpful to understand what's involved in creating a custom trainable classifier before you dive in.</span></span> 

### <a name="timeline"></a><span data-ttu-id="84ea2-128">Sequenza temporale</span><span class="sxs-lookup"><span data-stu-id="84ea2-128">Timeline</span></span>

<span data-ttu-id="84ea2-129">Questa sequenza temporale riflette una distribuzione di esempio di classificatori sotto forma di training.</span><span class="sxs-lookup"><span data-stu-id="84ea2-129">This timeline reflects a sample deployment of trainable classifiers.</span></span>

![trainable-classifier-timeline](../media/trainable-classifier-deployment-timeline_border.png)

> [!TIP]
> <span data-ttu-id="84ea2-131">Il consenso esplicito è necessario la prima volta per classificatori addestrabili.</span><span class="sxs-lookup"><span data-stu-id="84ea2-131">Opt-in is required the first time for trainable classifiers.</span></span> <span data-ttu-id="84ea2-132">Per completare una valutazione di Microsoft 365 di base del contenuto dell'organizzazione, sono necessari 12 giorni.</span><span class="sxs-lookup"><span data-stu-id="84ea2-132">It takes twelve days for Microsoft 365 to complete a baseline evaluation of your organizations content.</span></span> <span data-ttu-id="84ea2-133">Contattare l'amministratore globale per avviare il processo di consenso esplicito.</span><span class="sxs-lookup"><span data-stu-id="84ea2-133">Contact your global administrator to kick off the opt-in process.</span></span>

### <a name="overall-workflow"></a><span data-ttu-id="84ea2-134">Flusso di lavoro complessivo</span><span class="sxs-lookup"><span data-stu-id="84ea2-134">Overall workflow</span></span>

<span data-ttu-id="84ea2-135">Per ulteriori informazioni sul flusso di lavoro complessivo per la creazione di classificatori addestrabili personalizzati, vedere [Process flow for creating customer trainable classifiers](classifier-learn-about.md#process-flow-for-creating-custom-classifiers).</span><span class="sxs-lookup"><span data-stu-id="84ea2-135">To understand more about the overall workflow of creating custom trainable classifiers, see [Process flow for creating customer trainable classifiers](classifier-learn-about.md#process-flow-for-creating-custom-classifiers).</span></span>

### <a name="seed-content"></a><span data-ttu-id="84ea2-136">Contenuto seed</span><span class="sxs-lookup"><span data-stu-id="84ea2-136">Seed content</span></span>

<span data-ttu-id="84ea2-137">Quando si desidera che un classificatore sotto forma di training identifichini in modo indipendente e accurato un elemento in una determinata categoria di contenuto, è innanzitutto necessario presentarlo con molti esempi del tipo di contenuto presente nella categoria.</span><span class="sxs-lookup"><span data-stu-id="84ea2-137">When you want a trainable classifier to independently and accurately identify an item as being in particular category of content, you first have to present it with many samples of the type of content that are in the category.</span></span> <span data-ttu-id="84ea2-138">Questa alimentazione di campioni al classificatore trainabile è nota come *seeding.*</span><span class="sxs-lookup"><span data-stu-id="84ea2-138">This feeding of samples to the trainable classifier is known as *seeding*.</span></span> <span data-ttu-id="84ea2-139">Il contenuto di seed viene selezionato da un essere umano e viene scelto per rappresentare la categoria di contenuto.</span><span class="sxs-lookup"><span data-stu-id="84ea2-139">Seed content is selected by a human and is judged to represent the category of content.</span></span>

> [!TIP]
> <span data-ttu-id="84ea2-140">Devi avere almeno 50 campioni positivi e fino a 500.</span><span class="sxs-lookup"><span data-stu-id="84ea2-140">You need to have at least 50 positive samples and as many as 500.</span></span> <span data-ttu-id="84ea2-141">Il classificatore addestrabile eelaborare fino ai 500 esempi creati più di recente (per data e ora di creazione del file).</span><span class="sxs-lookup"><span data-stu-id="84ea2-141">The trainable classifier will process up to the 500 most recent created samples (by file created date/time stamp).</span></span> <span data-ttu-id="84ea2-142">Più esempi fornisci, più accurate saranno le previsioni che il classificatore farà.</span><span class="sxs-lookup"><span data-stu-id="84ea2-142">The more samples you provide, the more accurate the predictions the classifier will make.</span></span>

### <a name="testing-content"></a><span data-ttu-id="84ea2-143">Test del contenuto</span><span class="sxs-lookup"><span data-stu-id="84ea2-143">Testing content</span></span>

<span data-ttu-id="84ea2-144">Dopo che il classificatore sotto forma di training ha elaborato campioni positivi sufficienti per creare un modello di previsione, è necessario testare le previsioni che effettua per verificare se il classificatore è in grado di distinguere correttamente tra gli elementi che corrispondono alla categoria e gli elementi che non lo soddisfano.</span><span class="sxs-lookup"><span data-stu-id="84ea2-144">Once the trainable classifier has processed enough positive samples to build a prediction model, you need to test the predictions it makes to see if the classifier can correctly distinguish between items that match the category and items that don't.</span></span> <span data-ttu-id="84ea2-145">A tale scopo, selezionare un altro insieme, si spera più grande, di contenuto raccolto dall'utente costituito da campioni che dovrebbero rientrare nella categoria e campioni che non lo saranno.</span><span class="sxs-lookup"><span data-stu-id="84ea2-145">You do this by selecting another, hopefully larger, set of human picked content that consists of samples that should fall into the category and samples that won't.</span></span> <span data-ttu-id="84ea2-146">È consigliabile eseguire il test con dati diversi rispetto ai dati di inizializzazione iniziali forniti per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="84ea2-146">You should test with different data than the initial seed data you first provided.</span></span> <span data-ttu-id="84ea2-147">Dopo averli processati, puoi passare manualmente attraverso i risultati e verificare se ogni previsione è corretta, errata o non sei sicuro.</span><span class="sxs-lookup"><span data-stu-id="84ea2-147">Once it processes those, you manually go through the results and verify whether each prediction is correct, incorrect, or you aren't sure.</span></span> <span data-ttu-id="84ea2-148">Il classificatore addestrabile usa questo feedback per migliorare il modello di previsione.</span><span class="sxs-lookup"><span data-stu-id="84ea2-148">The trainable classifier uses this feedback to improve its prediction model.</span></span>

> [!TIP]
> <span data-ttu-id="84ea2-149">Per ottenere risultati ottimali, nel set di campioni di test sono presenti almeno 200 elementi con una distribuzione uniforme di corrispondenze positive e negative.</span><span class="sxs-lookup"><span data-stu-id="84ea2-149">For best results, have at least 200 items in your test sample set with an even distribution of positive and negative matches.</span></span>

## <a name="how-to-create-a-trainable-classifier"></a><span data-ttu-id="84ea2-150">Come creare un classificatore trainabile</span><span class="sxs-lookup"><span data-stu-id="84ea2-150">How to create a trainable classifier</span></span>

1. <span data-ttu-id="84ea2-151">Raccogliere tra 50 e 500 elementi di contenuto di seed.</span><span class="sxs-lookup"><span data-stu-id="84ea2-151">Collect between 50-500 seed content items.</span></span> <span data-ttu-id="84ea2-152">Questi devono essere solo esempi che rappresentano in modo forte il tipo di contenuto che il classificatore sotto forma di training deve identificare in modo positivo nella categoria di classificazione.</span><span class="sxs-lookup"><span data-stu-id="84ea2-152">These must be only samples that strongly represent the type of content you want the trainable classifier to positively identify as being in the classification category.</span></span> <span data-ttu-id="84ea2-153">Per i tipi di file supportati, vedere Default [crawled file name extensions and parsed file types in SharePoint Server.](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)</span><span class="sxs-lookup"><span data-stu-id="84ea2-153">See, [Default crawled file name extensions and parsed file types in SharePoint Server](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) for the supported file types.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="84ea2-154">Gli elementi di esempio di seed e test non devono essere crittografati e devono essere in inglese.</span><span class="sxs-lookup"><span data-stu-id="84ea2-154">The seed and test sample items must not be encrypted and they must be in English.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="84ea2-155">Assicurati che gli elementi nel set di seed siano **esempi** specifici della categoria.</span><span class="sxs-lookup"><span data-stu-id="84ea2-155">Make sure the items in your seed set are **strong** examples of the category.</span></span> <span data-ttu-id="84ea2-156">Il classificatore di cui è possibile eseguire il training inizialmente crea il modello in base al valore di inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="84ea2-156">The trainable classifier initially builds its model based on what you seed it with.</span></span> <span data-ttu-id="84ea2-157">Il classificatore presuppone che tutti i campioni di seme siano positivi forti e non abbia modo di sapere se un campione è una corrispondenza debole o negativa alla categoria.</span><span class="sxs-lookup"><span data-stu-id="84ea2-157">The classifier assumes all seed samples are strong positives and has no way of knowing if a sample is a weak or negative match to the category.</span></span>

2. <span data-ttu-id="84ea2-158">Inserire il contenuto del seed in una SharePoint online dedicata solo al *contenuto del seed.*</span><span class="sxs-lookup"><span data-stu-id="84ea2-158">Place the seed content in a SharePoint Online folder that is dedicated to holding *the seed content only*.</span></span> <span data-ttu-id="84ea2-159">Prendere nota dell'URL del sito, della raccolta e della cartella.</span><span class="sxs-lookup"><span data-stu-id="84ea2-159">Make note of the site, library, and folder URL.</span></span>

   > [!TIP]
   > <span data-ttu-id="84ea2-160">Se si crea un nuovo sito e una nuova cartella per i dati di seed, consentire l'indicizzazione di almeno un'ora per tale posizione prima di creare il classificatore trainabile che utilizzerà i dati di seed.</span><span class="sxs-lookup"><span data-stu-id="84ea2-160">If you create a new site and folder for your seed data, allow at least an hour for that location to be indexed before creating the trainable classifier that will use that seed data.</span></span>

3. <span data-ttu-id="84ea2-161">Accedi a Centro conformità Microsoft 365 con l'accesso al ruolo amministratore della conformità o amministratore della sicurezza e **apri** Centro conformità Microsoft 365 o **Microsoft 365 del** centro sicurezza  >  **Classificazione dati**.</span><span class="sxs-lookup"><span data-stu-id="84ea2-161">Sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** or **Microsoft 365 security center** > **Data classification**.</span></span>

4. <span data-ttu-id="84ea2-162">Scegliere la **scheda Classificatori trainabili.**</span><span class="sxs-lookup"><span data-stu-id="84ea2-162">Choose the **Trainable classifiers** tab.</span></span>

5. <span data-ttu-id="84ea2-163">Scegliere **Crea classificatore trainabile.**</span><span class="sxs-lookup"><span data-stu-id="84ea2-163">Choose **Create trainable classifier**.</span></span>

6. <span data-ttu-id="84ea2-164">Compilare i valori appropriati per i campi e della categoria di elementi che si desidera identificare da `Name` `Description` questo classificatore sotto forma di training.</span><span class="sxs-lookup"><span data-stu-id="84ea2-164">Fill in appropriate values for the `Name` and `Description` fields of the category of items you want this trainable classifier to identify.</span></span>

7. <span data-ttu-id="84ea2-165">Selezionare il SharePoint, la raccolta e l'URL della cartella di SharePoint online per il sito di contenuto seed dal passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="84ea2-165">Pick the SharePoint Online site, library, and folder URL for the seed content site from step 2.</span></span> <span data-ttu-id="84ea2-166">Scegliere `Add` .</span><span class="sxs-lookup"><span data-stu-id="84ea2-166">Choose `Add`.</span></span>

8. <span data-ttu-id="84ea2-167">Rivedere le impostazioni e scegliere `Create trainable classifier` .</span><span class="sxs-lookup"><span data-stu-id="84ea2-167">Review the settings and choose `Create trainable classifier`.</span></span>

9. <span data-ttu-id="84ea2-168">Entro 24 ore il classificatore addestrabile eelaborare i dati di seed e creare un modello di previsione.</span><span class="sxs-lookup"><span data-stu-id="84ea2-168">Within 24 hours the trainable classifier will process the seed data and build a prediction model.</span></span> <span data-ttu-id="84ea2-169">Lo stato del classificatore `In progress` è durante l'elaborazione dei dati di seed.</span><span class="sxs-lookup"><span data-stu-id="84ea2-169">The classifier status is `In progress` while it processes the seed data.</span></span> <span data-ttu-id="84ea2-170">Quando il classificatore ha terminato l'elaborazione dei dati di seed, lo stato viene modificato in `Need test items` .</span><span class="sxs-lookup"><span data-stu-id="84ea2-170">When the classifier is finished processing the seed data, the status changes to `Need test items`.</span></span>

10. <span data-ttu-id="84ea2-171">È ora possibile visualizzare la pagina dei dettagli scegliendo il classificatore.</span><span class="sxs-lookup"><span data-stu-id="84ea2-171">You can now view the details page by choosing the classifier.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="84ea2-172">![Classificatore addestrabile pronto per il test](../media/classifier-trainable-ready-to-test-detail.png)</span><span class="sxs-lookup"><span data-stu-id="84ea2-172">![trainable classifier ready for testing](../media/classifier-trainable-ready-to-test-detail.png)</span></span>

11. <span data-ttu-id="84ea2-173">Raccogliere almeno 200 elementi di contenuto di test (10.000 max) per ottenere risultati ottimali.</span><span class="sxs-lookup"><span data-stu-id="84ea2-173">Collect at least 200 test content items (10,000 max) for best results.</span></span> <span data-ttu-id="84ea2-174">Questi dovrebbero essere una combinazione di elementi che sono positivi forti, negativi forti e alcuni che sono un po ' meno evidenti nella loro natura.</span><span class="sxs-lookup"><span data-stu-id="84ea2-174">These should be a mix of items that are strong positives, strong negatives and some that are a little less obvious in their nature.</span></span> <span data-ttu-id="84ea2-175">Per i tipi di file supportati, vedere Default [crawled file name extensions and parsed file types in SharePoint Server.](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)</span><span class="sxs-lookup"><span data-stu-id="84ea2-175">See, [Default crawled file name extensions and parsed file types in SharePoint Server](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) for the supported file types.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="84ea2-176">Gli elementi di esempio non devono essere crittografati e devono essere in inglese.</span><span class="sxs-lookup"><span data-stu-id="84ea2-176">The sample items must not be encrypted and they must be in English.</span></span>

12. <span data-ttu-id="84ea2-177">Inserire il contenuto di test in una SharePoint online dedicata solo al contenuto *di test.*</span><span class="sxs-lookup"><span data-stu-id="84ea2-177">Place the test content in a SharePoint Online folder that is dedicated to holding *the test content only*.</span></span> <span data-ttu-id="84ea2-178">Prendere nota dell'URL SharePoint sito, raccolta e cartella di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="84ea2-178">Make note of the SharePoint Online site, library, and folder URL.</span></span>

    > [!TIP]
    > <span data-ttu-id="84ea2-179">Se si creano un nuovo sito e una nuova cartella per i dati di test, è necessario indicizzare almeno un'ora per tale posizione prima di creare il classificatore di cui è possibile eseguire il training che utilizzerà i dati di seed.</span><span class="sxs-lookup"><span data-stu-id="84ea2-179">If you create a new site and folder for your test data, allow at least an hour for that location to be indexed before creating the trainable classifier that will use that seed data.</span></span>

13. <span data-ttu-id="84ea2-180">Scegliere `Add items to test` .</span><span class="sxs-lookup"><span data-stu-id="84ea2-180">Choose `Add items to test`.</span></span>

14. <span data-ttu-id="84ea2-181">Selezionare l SharePoint, la raccolta e l'URL della cartella per il sito di contenuto di test dal passaggio 12.</span><span class="sxs-lookup"><span data-stu-id="84ea2-181">Pick the SharePoint Online site, library, and folder URL for the test content site from step 12.</span></span> <span data-ttu-id="84ea2-182">Scegliere `Add` .</span><span class="sxs-lookup"><span data-stu-id="84ea2-182">Choose `Add`.</span></span>

15. <span data-ttu-id="84ea2-183">Completare la procedura guidata scegliendo `Done` .</span><span class="sxs-lookup"><span data-stu-id="84ea2-183">Finish the wizard by choosing `Done`.</span></span> <span data-ttu-id="84ea2-184">Il classificatore di cui è possibile eseguire il training può richiedere fino a un'ora per elaborare i file di test.</span><span class="sxs-lookup"><span data-stu-id="84ea2-184">Your trainable classifier will take up to an hour to process the test files.</span></span>

16. <span data-ttu-id="84ea2-185">Quando il classificatore addestrabile ha finito di elaborare i file di test, lo stato nella pagina dei dettagli cambierà in `Ready to review` .</span><span class="sxs-lookup"><span data-stu-id="84ea2-185">When the trainable classifier is done processing your test files, the status on the details page will change to `Ready to review`.</span></span> <span data-ttu-id="84ea2-186">Se devi aumentare le dimensioni del campione di test, scegli e consenti al `Add items to test` classificatore addestrabile di elaborare gli elementi aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="84ea2-186">If you need to increase the test sample size, choose `Add items to test` and allow the trainable classifier to process the additional items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="84ea2-187">![screenshot pronto per la revisione](../media/classifier-trainable-ready-to-review-detail.png)</span><span class="sxs-lookup"><span data-stu-id="84ea2-187">![ready to review screenshot](../media/classifier-trainable-ready-to-review-detail.png)</span></span>

17. <span data-ttu-id="84ea2-188">Scegliere `Tested items to review` la scheda per esaminare gli elementi.</span><span class="sxs-lookup"><span data-stu-id="84ea2-188">Choose `Tested items to review` tab to review items.</span></span>

18. <span data-ttu-id="84ea2-189">Microsoft 365 presenta 30 elementi alla volta.</span><span class="sxs-lookup"><span data-stu-id="84ea2-189">Microsoft 365 will present 30 items at a time.</span></span> <span data-ttu-id="84ea2-190">Esaminarli e nella `We predict this item is "Relevant". Do you agree?` casella scegliere uno o `Yes` `No` `Not sure, skip to next item` .</span><span class="sxs-lookup"><span data-stu-id="84ea2-190">Review them and in the `We predict this item is "Relevant". Do you agree?` box choose either `Yes` or `No` or `Not sure, skip to next item`.</span></span> <span data-ttu-id="84ea2-191">L'accuratezza del modello viene aggiornata automaticamente dopo ogni 30 elementi.</span><span class="sxs-lookup"><span data-stu-id="84ea2-191">Model accuracy is automatically updated after every 30 items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="84ea2-192">![casella rivedi elementi](../media/classifier-trainable-review-detail.png)</span><span class="sxs-lookup"><span data-stu-id="84ea2-192">![review items box](../media/classifier-trainable-review-detail.png)</span></span>

19. <span data-ttu-id="84ea2-193">Esaminare *almeno* 200 elementi.</span><span class="sxs-lookup"><span data-stu-id="84ea2-193">Review *at least* 200 items.</span></span> <span data-ttu-id="84ea2-194">Una volta stabilizzato il punteggio di accuratezza, **l'opzione di** pubblicazione diventerà disponibile e lo stato del classificatore dirà `Ready to use` .</span><span class="sxs-lookup"><span data-stu-id="84ea2-194">Once the accuracy score has stabilized, the **publish** option will become available and the classifier status will say `Ready to use`.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="84ea2-195">![punteggio di accuratezza e pronto per la pubblicazione](../media/classifier-trainable-review-ready-to-publish.png)</span><span class="sxs-lookup"><span data-stu-id="84ea2-195">![accuracy score and ready to publish](../media/classifier-trainable-review-ready-to-publish.png)</span></span>

20. <span data-ttu-id="84ea2-196">Pubblicare il classificatore.</span><span class="sxs-lookup"><span data-stu-id="84ea2-196">Publish the classifier.</span></span>

21. <span data-ttu-id="84ea2-197">Dopo la pubblicazione, il classificatore sarà disponibile come condizione in Office [auto-etichettatura](apply-sensitivity-label-automatically.md)con etichette di [riservatezza,](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) applicare automaticamente i criteri delle etichette di conservazione in base a una condizione e in [Conformità alle comunicazioni.](communication-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="84ea2-197">Once published your classifier will be available as a condition in [Office auto-labeling with sensitivity labels](apply-sensitivity-label-automatically.md), [auto-apply retention label policy based on a condition](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) and in [Communication compliance](communication-compliance.md).</span></span>
