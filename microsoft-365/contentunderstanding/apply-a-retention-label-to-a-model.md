---
title: Applicare un'etichetta di conservazione a un modello
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Questo articolo spiega come applicare un'etichetta di conservazione a un modello in SharePoint Syntex
ms.openlocfilehash: 48c0b983316cfe29019d09cb20546fa4b325b3b0
ms.sourcegitcommit: 78f48304f990e969a052fe6536b2e8d6856e1086
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2021
ms.locfileid: "50242772"
---
# <a name="apply-a-retention-label-to-a-model-in-sharepoint-syntex"></a><span data-ttu-id="d9fe1-103">Applicare un'etichetta di conservazione a un modello in SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="d9fe1-103">Apply a retention label to a model in SharePoint Syntex</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GydO]  

</br>


<span data-ttu-id="d9fe1-104">Applicare un'[etichetta di conservazione](https://docs.microsoft.com/microsoft-365/compliance/retention) a un modello in Microsoft SharePoint Syntex è molto semplice.</span><span class="sxs-lookup"><span data-stu-id="d9fe1-104">You can easily apply a [retention label](https://docs.microsoft.com/microsoft-365/compliance/retention) to a model in Microsoft SharePoint Syntex.</span></span> <span data-ttu-id="d9fe1-105">È possibile farlo sia per i modelli di analisi dei documenti, sia per i modelli di elaborazione dei moduli.</span><span class="sxs-lookup"><span data-stu-id="d9fe1-105">You can do this for both document understanding and form processing models.</span></span>

<span data-ttu-id="d9fe1-106">Le etichette di conservazione permettono di applicare impostazioni di conservazione ai documenti identificati dai modelli.</span><span class="sxs-lookup"><span data-stu-id="d9fe1-106">Retention labels let you apply retention settings to the documents that your models identify.</span></span>  <span data-ttu-id="d9fe1-107">Ad esempio, si può fare modo che il modello non solo identifichi i documenti di tipo *Contratto di assicurazione* caricati in una raccolta documenti, ma anche che applichi l'etichetta di conservazione *Business*, in modo che non sia possibile eliminare questi documenti dalla raccolta per il periodo di tempo specificato, ad esempio i cinque mesi successivi.</span><span class="sxs-lookup"><span data-stu-id="d9fe1-107">For example, you want your model to not only identify any *Insurance notice* documents that are uploaded to your document library, but to also apply a *Business* retention tag to them so that these documents cannot be deleted from the document library for the specified time period (the next five months, for example).</span></span>

<span data-ttu-id="d9fe1-108">Si può applicare al modello un'etichetta di conservazione preesistente, usando le impostazioni del modello nella home page del modello.</span><span class="sxs-lookup"><span data-stu-id="d9fe1-108">You can apply a pre-existing retention label to your model through your model settings on your model's home page.</span></span> 

> [!Important]
> <span data-ttu-id="d9fe1-109">Affinché siano disponibili etichette di conservazione da applicare ai modelli di analisi dei documenti, occorre [crearle e pubblicarle nel Centro conformità Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels).</span><span class="sxs-lookup"><span data-stu-id="d9fe1-109">For retention labels to be available to apply to your document understanding models, they need to be [created and published in the Microsoft 365 Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels).</span></span>

## <a name="to-add-a-retention-label-to-a-document-understanding-model"></a><span data-ttu-id="d9fe1-110">Per aggiungere un'etichetta di conservazione a un modello di analisi dei documenti</span><span class="sxs-lookup"><span data-stu-id="d9fe1-110">To add a retention label to a document understanding model</span></span>

1. <span data-ttu-id="d9fe1-111">Nella home page del modello selezionare **Impostazioni modello**.</span><span class="sxs-lookup"><span data-stu-id="d9fe1-111">From the model home page, select **Model settings**.</span></span></br>
2. <span data-ttu-id="d9fe1-112">In **Impostazioni modello** selezionare il menu **Etichetta di conservazione** nella sezione **Sicurezza e conformità** per visualizzare un elenco delle etichette di conservazione disponibili per il modello.</span><span class="sxs-lookup"><span data-stu-id="d9fe1-112">In **Model settings**, in the **Security and compliance** section, select the **Retention label** menu to see a list of retention labels that are available for your to apply to the model.</span></span></br>
 <span data-ttu-id="d9fe1-113">![Menu Etichetta di conservazione](../media/content-understanding/retention-labels-menu.png)</span><span class="sxs-lookup"><span data-stu-id="d9fe1-113">![Retention label menu](../media/content-understanding/retention-labels-menu.png)</span></span></br> 
3. <span data-ttu-id="d9fe1-114">Selezionare l'etichetta di conservazione da applicare al modello e scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="d9fe1-114">Select the retention label you want to apply to the model, and then select **Save**.</span></span></br>

<span data-ttu-id="d9fe1-115">Dopo aver applicato l'etichetta conservazione al modello, è possibile applicarla:</span><span class="sxs-lookup"><span data-stu-id="d9fe1-115">After applying the retention label to your model, you are able to apply it to a:</span></span>
- <span data-ttu-id="d9fe1-116">A una nuova raccolta documenti</span><span class="sxs-lookup"><span data-stu-id="d9fe1-116">New document library</span></span>
- <span data-ttu-id="d9fe1-117">A una raccolta documenti a cui è già applicato il modello</span><span class="sxs-lookup"><span data-stu-id="d9fe1-117">Document library to which the model is already applied</span></span>
 
## <a name="apply-the-retention-label-to-a-document-library-to-which-the-model-is-already-applied"></a><span data-ttu-id="d9fe1-118">Applicare l'etichetta conservazione a una raccolta documenti a cui è già applicato il modello</span><span class="sxs-lookup"><span data-stu-id="d9fe1-118">Apply the retention label to a document library to which the model is already applied</span></span>

<span data-ttu-id="d9fe1-119">Se il modello di analisi dei documenti è già stato applicato a una raccolta documenti, è possibile procedere come segue per sincronizzare l'aggiornamento dell'etichetta di conservazione e applicarlo alla raccolta documenti:</span><span class="sxs-lookup"><span data-stu-id="d9fe1-119">If your document understanding model has already been applied to a document library, you can do the following to sync your retention label update to apply it to the document library:</span></span></br>

1. <span data-ttu-id="d9fe1-120">Nella home page del modello selezionare la raccolta documenti alla quale si vuole applicare l'aggiornamento dell'etichetta di conservazione nella sezione **Raccolte con questo modello**.</span><span class="sxs-lookup"><span data-stu-id="d9fe1-120">On your model home page, in the **Libraries with this model** section, select the document library to which you want to apply the retention label update.</span></span> </br> 
2. <span data-ttu-id="d9fe1-121">Selezionare **Sincronizza**.</span><span class="sxs-lookup"><span data-stu-id="d9fe1-121">Select **Sync**.</span></span> </br>
 <span data-ttu-id="d9fe1-122">![Sincronizzazione del modello](../media/content-understanding/sync-model.png)</span><span class="sxs-lookup"><span data-stu-id="d9fe1-122">![Sync model](../media/content-understanding/sync-model.png)</span></span></br> 


<span data-ttu-id="d9fe1-123">Dopo aver applicato l'aggiornamento e averlo sincronizzato con il modello, è possibile verificare che sia stato applicato eseguendo le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d9fe1-123">After applying the update and syncing it to your model, you can confirm that it has been applied by doing the following:</span></span>

1. <span data-ttu-id="d9fe1-124">Nella sezione **Raccolte con questo modello** del centro contenuti fare clic sulla raccolta a cui è stato applicato il modello aggiornato.</span><span class="sxs-lookup"><span data-stu-id="d9fe1-124">In the content center, in the **Libraries with this model** section, click on the library to which your updated model was applied.</span></span> </br>
2. <span data-ttu-id="d9fe1-125">Nella visualizzazione Raccolta documenti selezionare l'icona informazioni per controllare le proprietà del modello.</span><span class="sxs-lookup"><span data-stu-id="d9fe1-125">In your document library view, select the information icon to check the model properties.</span></span></br>  
3. <span data-ttu-id="d9fe1-126">Selezionare il modello aggiornato nell'elenco **Modelli attivi**.</span><span class="sxs-lookup"><span data-stu-id="d9fe1-126">In the **Active models** list, select your updated model.</span></span></br>
4. <span data-ttu-id="d9fe1-127">Nella sezione **Etichetta di conservazione** sarà visualizzato il nome dell'etichetta di conservazione applicata.</span><span class="sxs-lookup"><span data-stu-id="d9fe1-127">In the **Retention label** section you will see the name of the applied retention label.</span></span></br>


<span data-ttu-id="d9fe1-128">Nella pagina di visualizzazione del modello della raccolta documenti comparirà una nuova colonna **Etichetta di conservazione**.</span><span class="sxs-lookup"><span data-stu-id="d9fe1-128">On your model's view page in your document library, a new **Retention label** column will display.</span></span>  <span data-ttu-id="d9fe1-129">Man mano che il modello classifica i file che identifica come appartenenti al proprio tipo di contenuto e li elenca nella visualizzazione della raccolta, nella colonna Etichetta di conservazione compare anche il nome dell'etichetta di conservazione applicata mediante il modello.</span><span class="sxs-lookup"><span data-stu-id="d9fe1-129">As your model classifies files it identifies as belonging to it's content type and lists them in the library view, the Retention label column will also display the name of the retention label that has been applied to it through the model.</span></span>


<span data-ttu-id="d9fe1-130">Ad esempio, a tutti i documenti *Contratto di assicurazione* identificati dal modello verrà anche applicata l'etichetta di conservazione *Business*, che ne impedisce l'eliminazione dalla raccolta documenti per cinque mesi.</span><span class="sxs-lookup"><span data-stu-id="d9fe1-130">For example, all *Insurance notice* documents that your model identifies will also have the *Business* retention label applied to them, preventing them from being deleted from the document library for five months.</span></span> <span data-ttu-id="d9fe1-131">Se qualcuno tenta di eliminare il file dalla raccolta documenti, verrà visualizzato un messaggio di errore che segnala che non è consentito a causa dell'etichetta di conservazione applicata.</span><span class="sxs-lookup"><span data-stu-id="d9fe1-131">If an attempt is made to delete the file from the document library, an error will display saying it is not allowed because of the applied retention label.</span></span>

## <a name="to-add-a-retention-label-to-a-form-processing-model"></a><span data-ttu-id="d9fe1-132">Per aggiungere un'etichetta di conservazione a un modello di elaborazione moduli</span><span class="sxs-lookup"><span data-stu-id="d9fe1-132">To add a retention label to a form processing model</span></span>

> [!Important]
> <span data-ttu-id="d9fe1-133">Affinché siano disponibili etichette di conservazione da applicare al modello di elaborazione moduli, occorre [crearle e pubblicarle nel Centro conformità Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels).</span><span class="sxs-lookup"><span data-stu-id="d9fe1-133">For retention labels to be available to apply to your form processing model, they need to be [created and published in the Microsoft 365 Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels).</span></span>

<span data-ttu-id="d9fe1-134">È possibile applicare un'etichetta di conservazione a un modello di elaborazione moduli quando si crea il modello oppure applicarla a un modello esistente.</span><span class="sxs-lookup"><span data-stu-id="d9fe1-134">You can either apply a retention label to a form processing model when you are creating a model, or apply it to an existing model.</span></span>

### <a name="to-add-a-retention-label-when-you-create-a-form-processing-model"></a><span data-ttu-id="d9fe1-135">Per aggiungere un'etichetta di conservazione al momento della creazione di un modello di elaborazione moduli</span><span class="sxs-lookup"><span data-stu-id="d9fe1-135">To add a retention label when you create a form processing model</span></span>

1. <span data-ttu-id="d9fe1-136">Quando si [crea un nuovo modello di elaborazione moduli](https://docs.microsoft.com/microsoft-365/contentunderstanding/create-a-form-processing-model), selezionare <b>Impostazioni avanzate.</b></span><span class="sxs-lookup"><span data-stu-id="d9fe1-136">When you are [creating a new form processing model](https://docs.microsoft.com/microsoft-365/contentunderstanding/create-a-form-processing-model), select <b>Advanced settings.</b></span></span>
2. <span data-ttu-id="d9fe1-137">Nella sezione <b>Etichetta di conservazione</b> delle <b>Impostazioni avanzate</b> selezionare il menu e quindi l'etichetta di conservazione da applicare al modello.</b></span><span class="sxs-lookup"><span data-stu-id="d9fe1-137">In <b>Advanced settings</b>, in the <b>Retention label</b> section, select the menu and then select the retention label you want to apply to the model.</b></span></span>

 
     ![Aggiungere un'etichetta a un nuovo modello di elaborazione moduli](../media/content-understanding/retention-label-forms.png)</br>

3.  <span data-ttu-id="d9fe1-139">Dopo aver completato le impostazioni rimanenti del modello, selezionare <b>Crea</b> per creare il modello.</span><span class="sxs-lookup"><span data-stu-id="d9fe1-139">After you've completed your remaining model settings, select <b>Create</b> to build your model.</span></span>

### <a name="to-add-a-retention-label-to-an-existing-form-processing-model"></a><span data-ttu-id="d9fe1-140">Per aggiungere un'etichetta di conservazione a un modello di elaborazione moduli esistente</span><span class="sxs-lookup"><span data-stu-id="d9fe1-140">To add a retention label to an existing form processing model</span></span>

<span data-ttu-id="d9fe1-141">Si può aggiungere un'etichetta di conservazione a un modello di elaborazione moduli esistente in vari modi:</span><span class="sxs-lookup"><span data-stu-id="d9fe1-141">You can add a retention label to an existing form processing model in different ways:</span></span>
- <span data-ttu-id="d9fe1-142">Tramite il menu Automatizza nella raccolta documenti</span><span class="sxs-lookup"><span data-stu-id="d9fe1-142">Through the Automate menu in the document library</span></span>
- <span data-ttu-id="d9fe1-143">Tramite le impostazioni dei modelli attivi nella raccolta documenti</span><span class="sxs-lookup"><span data-stu-id="d9fe1-143">Through the Active model settings in the document library</span></span> 


#### <a name="to-add-a-retention-label-to-an-existing-form-processing-model-through-the-automate-menu"></a><span data-ttu-id="d9fe1-144">Per aggiungere un'etichetta di conservazione a un modello di elaborazione moduli esistente tramite il menu Automatizza</span><span class="sxs-lookup"><span data-stu-id="d9fe1-144">To add a retention label to an existing form processing model through the Automate menu</span></span>

<span data-ttu-id="d9fe1-145">È possibile aggiungere un'etichetta di conservazione a un modello di elaborazione moduli esistente di cui si è proprietari tramite il menu Automatizza della raccolta documenti in cui è applicato il modello.</span><span class="sxs-lookup"><span data-stu-id="d9fe1-145">You can add a retention label to an existing form processing model that you own through the Automate menu in the document library in which the model is applied.</span></span>


1. <span data-ttu-id="d9fe1-146">Nella raccolta documenti a cui è applicato il modello di elaborazione moduli selezionare il menu <b>Automatizza</b>, selezionare <b>AI Builder</b>, quindi <b>Visualizza dettagli modello di elaborazione dei moduli</b>.</span><span class="sxs-lookup"><span data-stu-id="d9fe1-146">In your document library to which the form processing model is applied, select the <b>Automate</b> menu, select <b>AI Builder</b>, then select <b>View form processing model details</b>.</span></span>

   ![Menu Automatizza](../media/content-understanding/automate-menu.png)</br>

2. <span data-ttu-id="d9fe1-148">Nella sezione <b>Etichetta di conservazione</b> dei dettagli del modello selezionare l'etichetta di conservazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="d9fe1-148">In the model details, in the <b>Retention Label</b> section, select the retention label you want to apply.</span></span>  <span data-ttu-id="d9fe1-149">Quindi selezionare <b>Salva</b>.</span><span class="sxs-lookup"><span data-stu-id="d9fe1-149">Then select <b>Save</b>.</span></span>

     ![Aggiungere un'etichetta a un modello di elaborazione moduli esistente](../media/content-understanding/retention-label-model-details.png)</br> 

#### <a name="to-add-a-retention-label-to-an-existing-form-processing-model-in-the-active-model-settings"></a><span data-ttu-id="d9fe1-151">Per aggiungere un'etichetta di conservazione a un modello di elaborazione moduli esistente nelle impostazioni dei modelli attivi</span><span class="sxs-lookup"><span data-stu-id="d9fe1-151">To add a retention label to an existing form processing model in the active model settings</span></span>

<span data-ttu-id="d9fe1-152">È possibile aggiungere un'etichetta di conservazione a un modello di elaborazione moduli esistente di cui si è proprietari tramite le impostazioni dei modelli attivi della raccolta documenti in cui è applicato il modello.</span><span class="sxs-lookup"><span data-stu-id="d9fe1-152">You can add a retention label to an existing form processing model that you own through the Active model settings in the document library in which the model is applied.</span></span>

1. <span data-ttu-id="d9fe1-153">Nella raccolta documenti di SharePoint in cui è applicato il modello selezionare l'icona <b>Visualizza modelli attivi</b> e quindi selezionare <b>Visualizza modelli attivi</b>.</b></span><span class="sxs-lookup"><span data-stu-id="d9fe1-153">In the SharePoint document library in which the model is applied, select the <b>View active models</b> icon, and then select <b>View active models</b>.</b></span></span>

   ![Visualizza i modelli attivi](../media/content-understanding/info-du.png)</br> 

2. <span data-ttu-id="d9fe1-155">In <b>Modelli attivi</b> selezionare il modello di elaborazione moduli a cui si vuole applicare l'etichetta di conservazione.</span><span class="sxs-lookup"><span data-stu-id="d9fe1-155">In <b>Active models</b>, select the form processing model to which you want to apply the retention label.</span></span>

     ![Dettagli del modello](../media/content-understanding/retention-label-model-details.png)</br> 


3. <span data-ttu-id="d9fe1-157">Nella sezione <b>Etichetta di conservazione</b> dei dettagli del modello selezionare l'etichetta di conservazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="d9fe1-157">In the model details, in the <b>Retention Label</b> section, select the retention label you want to apply.</span></span>  <span data-ttu-id="d9fe1-158">Quindi selezionare <b>Salva</b>.</span><span class="sxs-lookup"><span data-stu-id="d9fe1-158">Then select <b>Save</b>.</span></span>

> [!NOTE]
> <span data-ttu-id="d9fe1-159">È necessario essere il proprietario del modello per poter apportare modifiche nel riquadro delle impostazioni modello.</span><span class="sxs-lookup"><span data-stu-id="d9fe1-159">You must be the model owner for the model settings pane to be editable.</span></span> 


## <a name="see-also"></a><span data-ttu-id="d9fe1-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d9fe1-160">See Also</span></span>
[<span data-ttu-id="d9fe1-161">Creare un classificatore</span><span class="sxs-lookup"><span data-stu-id="d9fe1-161">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="d9fe1-162">Creare un estrattore</span><span class="sxs-lookup"><span data-stu-id="d9fe1-162">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="d9fe1-163">Panoramica sull'analisi dei documenti</span><span class="sxs-lookup"><span data-stu-id="d9fe1-163">Document Understanding overview</span></span>](document-understanding-overview.md)


