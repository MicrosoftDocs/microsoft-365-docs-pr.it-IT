---
title: Applicazione di un'etichetta di conservazione a un modello di comprensione del documento
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 10/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: In questo articolo viene illustrato come applicare un'etichetta di conservazione a un modello di comprensione del documento
ms.openlocfilehash: 26ad64906c0e2a311d8b244e8e1596a8b975cc15
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294924"
---
# <a name="apply-a-retention-label-to-a-document-understanding-model"></a><span data-ttu-id="95581-103">Applicazione di un'etichetta di conservazione a un modello di comprensione del documento</span><span class="sxs-lookup"><span data-stu-id="95581-103">Apply a retention label to a document understanding model</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

<span data-ttu-id="95581-104">È possibile applicare facilmente un' [etichetta di conservazione](https://docs.microsoft.com/microsoft-365/compliance/retention) a un modello di comprensione del documento in Microsoft SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="95581-104">You can easily apply a [retention label](https://docs.microsoft.com/microsoft-365/compliance/retention) to a document understanding model in Microsoft SharePoint Syntex.</span></span>

<span data-ttu-id="95581-105">Le etichette di conservazione consentono di applicare le impostazioni di conservazione ai documenti identificati dai modelli.</span><span class="sxs-lookup"><span data-stu-id="95581-105">Retention labels let you apply retention settings to the documents that your document understanding models identify.</span></span>  <span data-ttu-id="95581-106">Ad esempio, si desidera che il modello non identifichi solo i documenti di *avviso di assicurazione* caricati nella raccolta documenti, ma applichi anche un tag di conservazione *aziendale* in modo che tali documenti non possano essere eliminati dalla raccolta documenti per il periodo di tempo specificato (ad esempio, i prossimi cinque mesi).</span><span class="sxs-lookup"><span data-stu-id="95581-106">For example, you want your model to not only identify any *Insurance notice* documents that are uploaded to your document library, but to also apply a *Business* retention tag to them so that these documents cannot be deleted from the document library for the specified time period (the next five months, for example).</span></span>

<span data-ttu-id="95581-107">È possibile applicare un'etichetta di conservazione preesistente al modello di comprensione dei documenti tramite le impostazioni del modello nella Home page del modello.</span><span class="sxs-lookup"><span data-stu-id="95581-107">You can apply a pre-existing retention label to your document understanding model through your model settings on your model's home page.</span></span> 

> [!Important]
> <span data-ttu-id="95581-108">Affinché le etichette di conservazione siano disponibili per essere applicate al modello di comprensione del contenuto, è necessario [crearle e pubblicarle nel centro conformità di Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels).</span><span class="sxs-lookup"><span data-stu-id="95581-108">For retention labels to be available to apply to your content understanding model, they need to be [created and published in the Microsoft 365 Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels).</span></span>

## <a name="to-add-a-retention-label-to-a-document-understanding-model"></a><span data-ttu-id="95581-109">Per aggiungere un'etichetta di conservazione a un modello di comprensione del documento</span><span class="sxs-lookup"><span data-stu-id="95581-109">To add a retention label to a document understanding model</span></span>

1. <span data-ttu-id="95581-110">Nella Home page del modello selezionare **Impostazioni modello**.</span><span class="sxs-lookup"><span data-stu-id="95581-110">From the model home page, select **Model settings**.</span></span></br>
2. <span data-ttu-id="95581-111">Nelle **impostazioni del modello**, nella sezione **sicurezza e conformità** , selezionare il menu **etichetta di conservazione** per visualizzare un elenco delle etichette di conservazione disponibili per il modello da applicare.</span><span class="sxs-lookup"><span data-stu-id="95581-111">In **Model settings**, in the **Security and compliance** section, select the **Retention label** menu to see a list of retention labels that are available for your to apply to the model.</span></span></br>
 <span data-ttu-id="95581-112">![Menu etichetta di conservazione](../media/content-understanding/retention-labels-menu.png)</span><span class="sxs-lookup"><span data-stu-id="95581-112">![Retention label menu](../media/content-understanding/retention-labels-menu.png)</span></span></br> 
3. <span data-ttu-id="95581-113">Selezionare l'etichetta di conservazione che si desidera applicare al modello e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="95581-113">Select the retention label you want to apply to the model, and then select **Save**.</span></span></br>

<span data-ttu-id="95581-114">Dopo aver applicato l'etichetta di conservazione al modello, è possibile applicarla a una delle seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="95581-114">After applying the retention label to your model, you are able to apply it to a:</span></span>
- <span data-ttu-id="95581-115">Nuova raccolta documenti</span><span class="sxs-lookup"><span data-stu-id="95581-115">New document library</span></span>
- <span data-ttu-id="95581-116">Raccolta documenti a cui è già applicato il modello</span><span class="sxs-lookup"><span data-stu-id="95581-116">Document library to which the model is already applied</span></span>
 
## <a name="apply-the-retention-label-to-a-document-library-to-which-the-model-is-already-applied"></a><span data-ttu-id="95581-117">Applicare l'etichetta di conservazione a una raccolta documenti a cui è già applicato il modello</span><span class="sxs-lookup"><span data-stu-id="95581-117">Apply the retention label to a document library to which the model is already applied</span></span>

<span data-ttu-id="95581-118">Se il modello di conoscenza del documento è già stato applicato a una raccolta documenti, è possibile eseguire le operazioni seguenti per sincronizzare l'aggiornamento dell'etichetta di conservazione per applicarlo alla raccolta documenti:</span><span class="sxs-lookup"><span data-stu-id="95581-118">If your document understanding model has already been applied to a document library, you can do the following to sync your retention label update to apply it to the document library:</span></span></br>

1. <span data-ttu-id="95581-119">Nella sezione **raccolte con questo modello** della Home page del modello selezionare la raccolta documenti in cui si desidera applicare l'aggiornamento per l'etichetta di conservazione.</span><span class="sxs-lookup"><span data-stu-id="95581-119">On your model home page, in the **Libraries with this model** section, select the document library to which you want to apply the retention label update.</span></span> </br> 
2. <span data-ttu-id="95581-120">Selezionare **Sincronizza**.</span><span class="sxs-lookup"><span data-stu-id="95581-120">Select **Sync**.</span></span> </br>
 <span data-ttu-id="95581-121">![Modello di sincronizzazione](../media/content-understanding/sync-model.png)</span><span class="sxs-lookup"><span data-stu-id="95581-121">![Sync model](../media/content-understanding/sync-model.png)</span></span></br> 


<span data-ttu-id="95581-122">Dopo aver applicato l'aggiornamento e averla sincronizzata con il modello, è possibile verificare che sia stata applicata eseguendo le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="95581-122">After applying the update and syncing it to your model, you can confirm that it has been applied by doing the following:</span></span>

1. <span data-ttu-id="95581-123">Nel centro contenuto, nella sezione **raccolte con questo modello** , fare clic sulla raccolta a cui è stato applicato il modello aggiornato.</span><span class="sxs-lookup"><span data-stu-id="95581-123">In the content center, in the **Libraries with this model** section, click on the library to which your updated model was applied.</span></span> </br>
2. <span data-ttu-id="95581-124">Nella visualizzazione raccolta documenti selezionare l'icona informazioni per controllare le proprietà del modello.</span><span class="sxs-lookup"><span data-stu-id="95581-124">In your document library view, select the information icon to check the model properties.</span></span></br>  
3. <span data-ttu-id="95581-125">Nell'elenco **modelli attivi** selezionare il modello aggiornato.</span><span class="sxs-lookup"><span data-stu-id="95581-125">In the **Active models** list, select your updated model.</span></span></br>
4. <span data-ttu-id="95581-126">Nella sezione **etichetta di conservazione** verrà visualizzato il nome dell'etichetta di conservazione applicata.</span><span class="sxs-lookup"><span data-stu-id="95581-126">In the **Retention label** section you will see the name of the applied retention label.</span></span></br>


<span data-ttu-id="95581-127">Nella pagina visualizzazione del modello nella raccolta documenti verrà visualizzata una nuova colonna di **etichette di conservazione** .</span><span class="sxs-lookup"><span data-stu-id="95581-127">On your model's view page in your document library, a new **Retention label** column will display.</span></span>  <span data-ttu-id="95581-128">Poiché il modello classifica i file identificati come appartenenti al tipo di contenuto e li elenca nella visualizzazione libreria, nella colonna etichetta di conservazione verrà visualizzato anche il nome dell'etichetta di conservazione applicata tramite il modello.</span><span class="sxs-lookup"><span data-stu-id="95581-128">As your model classifies files it identifies as belonging to it's content type and lists them in the library view, the Retention label column will also display the name of the retention label that has been applied to it through the model.</span></span>


<span data-ttu-id="95581-129">Ad esempio, tutti i documenti di *avviso di assicurazione* che il modello identifica avrà anche l'etichetta di conservazione dell' *azienda* applicata, impedendo che vengano eliminati dalla raccolta documenti per cinque mesi.</span><span class="sxs-lookup"><span data-stu-id="95581-129">For example, all *Insurance notice* documents that your model identifies will also have the *Business* retention label applied to them, preventing them from being deleted from the document library for five months.</span></span> <span data-ttu-id="95581-130">Se si tenta di eliminare il file dalla raccolta documenti, verrà visualizzato un messaggio di errore che indica che non è consentito a causa dell'etichetta di conservazione applicata.</span><span class="sxs-lookup"><span data-stu-id="95581-130">If an attempt is made to delete the file from the document library, an error will display saying it is not allowed because of the applied retention label.</span></span>

## <a name="see-also"></a><span data-ttu-id="95581-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="95581-131">See Also</span></span>
[<span data-ttu-id="95581-132">Creare un classificatore</span><span class="sxs-lookup"><span data-stu-id="95581-132">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="95581-133">Creare un estrattore</span><span class="sxs-lookup"><span data-stu-id="95581-133">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="95581-134">Panoramica della comprensione del documento</span><span class="sxs-lookup"><span data-stu-id="95581-134">Document Understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="95581-135">Creare un modello di elaborazione dei moduli</span><span class="sxs-lookup"><span data-stu-id="95581-135">Create a form processing model</span></span>](create-a-form-processing-model.md)  
