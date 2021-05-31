---
title: Applicare un'etichetta di conservazione a un modello in SharePoint Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Informazioni su come applicare un'etichetta di conservazione a un modello in SharePoint Syntex.
ms.openlocfilehash: 799ab3fa0fcdc9af9d227428056d2cd7abeaf539
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706721"
---
# <a name="apply-a-sensitivity-label-to-a-model-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="29939-103">Applicare un'etichetta di conservazione a un modello in SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="29939-103">Apply a sensitivity label to a model in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="29939-104">Microsoft SharePoint Syntex consente di applicare facilmente un'[etichetta di riservatezza](../compliance/sensitivity-labels.md) a un modello di analisi dei documenti.</span><span class="sxs-lookup"><span data-stu-id="29939-104">You can easily apply a [sensitivity label](../compliance/sensitivity-labels.md) to document understanding models in Microsoft SharePoint Syntex.</span></span> <span data-ttu-id="29939-105">Questa caratteristica non è ancora disponibile per i modelli di elaborazione di moduli.</span><span class="sxs-lookup"><span data-stu-id="29939-105">This feature isn't available yet for form processing models.</span></span>

<span data-ttu-id="29939-106">Le etichette di riservatezza consentono di applicare criteri di crittografia, condivisione e accesso condizionale ai documenti identificati nei modelli.</span><span class="sxs-lookup"><span data-stu-id="29939-106">Sensitivity labels let you apply encryption, sharing, and conditional access policies to the documents that your models identify.</span></span> <span data-ttu-id="29939-107">Ad esempio, si vuole che il modello non solo identifichi i documenti finanziari che contengono numeri di conto corrente bancario o numeri di carta di credito caricati nella raccolta documenti, ma anche applicare un'*etichetta di riservatezza* Crittografia per limitare gli utenti autorizzati che possono accedere a tale contenuto e le relative modalità di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="29939-107">For example, you want your model to not only identify any financial documents that contain bank account numbers or credit card numbers that are uploaded to your document library, but also to apply an *Encryption* sensitivity label to them to restrict who can access that content and how it can be used.</span></span>

<span data-ttu-id="29939-108">Si può applicare al modello un'etichetta di sensibilità preesistente, usando le impostazioni del modello nella home page del modello.</span><span class="sxs-lookup"><span data-stu-id="29939-108">You can apply a pre-existing sensitivity label to your model through your model settings on your model's home page.</span></span> <span data-ttu-id="29939-109">L'etichetta deve essere già pubblicata per essere disponibile per la selezione dalle impostazioni del modello.</span><span class="sxs-lookup"><span data-stu-id="29939-109">The label must already be published to be available for selection from model settings.</span></span>

> [!Important]
> <span data-ttu-id="29939-110">Affinché siano disponibili etichette di sensibilità da applicare ai modelli di analisi dei documenti, occorre [crearle e pubblicarle nel Centro conformità Microsoft 365](../business-video/create-sensitivity-labels.md).</span><span class="sxs-lookup"><span data-stu-id="29939-110">For sensitivity labels to be available to apply to your document understanding models, they need to be [created and published in the Microsoft 365 Compliance Center](../business-video/create-sensitivity-labels.md).</span></span>

## <a name="add-a-sensitivity-label-to-a-document-understanding-model"></a><span data-ttu-id="29939-111">Aggiungere un'etichetta di sensibilità a un modello di analisi dei documenti</span><span class="sxs-lookup"><span data-stu-id="29939-111">Add a sensitivity label to a document understanding model</span></span>

1. <span data-ttu-id="29939-112">Nella home page del modello selezionare **Impostazioni modello**.</span><span class="sxs-lookup"><span data-stu-id="29939-112">From the model home page, select **Model settings**.</span></span>

   ![Screenshot della pagina Modelli con l'opzione Impostazioni modello evidenziata.](../media/content-understanding/sensitivity-model-settings.png)

2. <span data-ttu-id="29939-114">Nel riquadro **Impostazioni modello** nella sezione **Conformità**, selezionare il menu **Etichetta di sensibilità** per visualizzare un elenco delle etichette di sensibilità disponibili per il modello.</span><span class="sxs-lookup"><span data-stu-id="29939-114">On **Model settings** pane, in the **Compliance** section, select the **Sensitivity label** menu to see a list of sensitivity labels that are available for you to apply to the model.</span></span>

   ![Screenshot del riquadro Impostazioni modello con il menu dell'etichetta di sensibilità.](../media/content-understanding/sensitivity-model-settings-pane.png) 

3. <span data-ttu-id="29939-116">Selezionare l'etichetta di sensibilità da applicare al modello e scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="29939-116">Select the sensitivity label you want to apply to the model, and then select **Save**.</span></span>

<span data-ttu-id="29939-117">Dopo aver applicato l'etichetta di sensibilità al modello, è possibile applicarla a:</span><span class="sxs-lookup"><span data-stu-id="29939-117">After you apply the sensitivity label to your model, you can apply it to a:</span></span>

- <span data-ttu-id="29939-118">A una nuova raccolta documenti</span><span class="sxs-lookup"><span data-stu-id="29939-118">New document library</span></span>
- <span data-ttu-id="29939-119">A una raccolta documenti a cui è già applicato il modello</span><span class="sxs-lookup"><span data-stu-id="29939-119">Document library to which the model is already applied</span></span>
 
### <a name="apply-the-sensitivity-label-to-a-document-library-to-which-the-model-is-already-applied"></a><span data-ttu-id="29939-120">Applicare l'etichetta di sensibilità a una raccolta documenti a cui è già applicato il modello</span><span class="sxs-lookup"><span data-stu-id="29939-120">Apply the sensitivity label to a document library to which the model is already applied</span></span>

<span data-ttu-id="29939-121">Se il modello di analisi dei documenti è già stato applicato a una raccolta documenti, è possibile procedere come segue per sincronizzare l'aggiornamento dell'etichetta di sensibilità e applicarlo alla raccolta documenti:</span><span class="sxs-lookup"><span data-stu-id="29939-121">If your document understanding model has already been applied to a document library, you can do the following to sync your sensitivity label update to apply it to the document library:</span></span>

1. <span data-ttu-id="29939-122">Nella home page del modello selezionare la raccolta documenti alla quale si vuole applicare l'aggiornamento dell'etichetta di sensibilità nella sezione **Raccolte con questo modello**.</span><span class="sxs-lookup"><span data-stu-id="29939-122">On the model home page, in the **Libraries with this model** section, select the document library to which you want to apply the sensitivity label update.</span></span>

2. <span data-ttu-id="29939-123">Selezionare **Sincronizza**.</span><span class="sxs-lookup"><span data-stu-id="29939-123">Select **Sync**.</span></span>

   ![Screenshot che mostra le raccolte con la sezione di questo modello con l'opzione Sincronizza evidenziata.](../media/content-understanding/sensitivity-libraries-sync.png)

<span data-ttu-id="29939-125">Dopo aver applicato l'aggiornamento e averlo sincronizzato con il modello, è possibile verificare che sia stato applicato eseguendo le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="29939-125">After you apply the update and sync it to your model, you can confirm that it has been applied by doing the following steps:</span></span>

1. <span data-ttu-id="29939-126">Nella sezione **Raccolte con questo modello** del centro contenuti selezionare la raccolta a cui è stato applicato il modello aggiornato.</span><span class="sxs-lookup"><span data-stu-id="29939-126">In the content center, in the **Libraries with this model** section, select the library to which your updated model was applied.</span></span> 

2. <span data-ttu-id="29939-127">Nella visualizzazione Raccolta documenti selezionare l'icona informazioni per controllare le proprietà del modello.</span><span class="sxs-lookup"><span data-stu-id="29939-127">In your document library view, select the information icon to check the model properties.</span></span>

3. <span data-ttu-id="29939-128">Selezionare il modello aggiornato nell'elenco **Modelli attivi**.</span><span class="sxs-lookup"><span data-stu-id="29939-128">In the **Active models** list, select your updated model.</span></span>

4. <span data-ttu-id="29939-129">Nella sezione **Etichetta di riservatezza**, verrà visualizzato il nome dell'etichetta di riservatezza applicata.</span><span class="sxs-lookup"><span data-stu-id="29939-129">In the **Sensitivity label** section, you'll see the name of the applied sensitivity label.</span></span>

<span data-ttu-id="29939-130">Nella pagina di visualizzazione del modello della raccolta documenti comparirà una nuova colonna **Etichetta di riservatezza**.</span><span class="sxs-lookup"><span data-stu-id="29939-130">On your model's view page in your document library, a new **Sensitivity label** column will display.</span></span> <span data-ttu-id="29939-131">Man mano che il modello classifica i file che identifica come appartenenti al proprio tipo di contenuto e li elenca nella visualizzazione della raccolta, nella colonna **Etichetta di riservatezza** compare anche il nome dell'etichetta di conservazione applicata mediante il modello.</span><span class="sxs-lookup"><span data-stu-id="29939-131">As your model classifies files it identifies as belonging to its content type and lists them in the library view, the **Sensitivity label** column will also display the name of the sensitivity label that has been applied to it through the model.</span></span>

<span data-ttu-id="29939-132">Ad esempio, a tutti i documenti finanziari identificati dal modello verrà applicata anche l'etichetta di riservatezza *Crittografia*, per impedire l'accesso da parte di utenti non autorizzati.</span><span class="sxs-lookup"><span data-stu-id="29939-132">For example, all financial documents that your model identifies also will have the *Encryption* sensitivity label applied to them, preventing them from being accessed by unauthorized people.</span></span> <span data-ttu-id="29939-133">Se una persona non autorizzata tenta di accedere al file dalla raccolta documenti, verrà visualizzato un messaggio di errore che segnala che non è consentito a causa dell'etichetta di sensibilità applicata.</span><span class="sxs-lookup"><span data-stu-id="29939-133">If an attempt is made to access the file from the document library by an unauthorized person, an error will display saying it isn't allowed because of the applied sensitivity label.</span></span>

<!---
## Add a sensitivity label to a form processing model

> [!Important]
> For sensitivity labels to be available to apply to your form processing model, they need to be [created and published in the Microsoft 365 Compliance Center](../business-video/create-sensitivity-labels.md).

You can either apply a sensitivity label to a form processing model when you are creating a model, or apply it to an existing model.

### Add a sensitivity label when you create a form processing model

1. When you [create a new form processing model](create-a-form-processing-model.md), select **Advanced settings**.

2. In **Advanced settings**, in the **Sensitivity label** section, select the menu and then select the sensitivity label you want to apply to the model.

3.  After you've completed your remaining model settings, select **Create** to build your model.

### Add a sensitivity label to an existing form processing model

You can add a sensitivity label to an existing form processing model in different ways:

- Through the **Automate** menu in the document library
- Through the **Active model** settings in the document library 

#### Add a sensitivity label to an existing form processing model through the Automate menu

You can add a sensitivity label to an existing form processing model that you own through the **Automate** menu in the document library in which the model is applied.

1. In your document library to which the form processing model is applied, select the **Automate** menu, select **AI Builder**, and then select **View form processing model details**.

2. On the **Model details** pane, in the **Sensitivity label** section, select the sensitivity label you want to apply. Then select **Save**.

#### Add a sensitivity label to an existing form processing model in the active model settings

You can add a sensitivity label to an existing form processing model that you own through the **Active model** settings in the document library in which the model is applied.

1. In the SharePoint document library in which the model is applied, select the **View active models** icon, and then select **View active models**.

2. In **Active models**, select the form processing model to which you want to apply the sensitivity label.

3. On the **Model details** pane, in the **Sensitivity label** section, select the sensitivity label you want to apply. Then select **Save**.

   > [!NOTE]
   > You must be the model owner for the **Model settings** pane to be editable. 
--->

## <a name="see-also"></a><span data-ttu-id="29939-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="29939-134">See also</span></span>

[<span data-ttu-id="29939-135">Applicare un'etichetta di conservazione</span><span class="sxs-lookup"><span data-stu-id="29939-135">Apply a retention label</span></span>](apply-a-retention-label-to-a-model.md)

[<span data-ttu-id="29939-136">Creare un classificatore</span><span class="sxs-lookup"><span data-stu-id="29939-136">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="29939-137">Creare un estrattore</span><span class="sxs-lookup"><span data-stu-id="29939-137">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="29939-138">Panoramica sull'analisi dei documenti</span><span class="sxs-lookup"><span data-stu-id="29939-138">Document Understanding overview</span></span>](document-understanding-overview.md)