---
title: Applicare un'etichetta di conservazione a un modello di analisi dei documenti
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
description: Questo articolo spiega come applicare un'etichetta di conservazione a un modello di analisi dei documenti
ms.openlocfilehash: 6dcd81b580b7bf0801641bbd019e1b99ecfe7338
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/25/2021
ms.locfileid: "49976556"
---
# <a name="apply-a-retention-label-to-a-document-understanding-model"></a><span data-ttu-id="01308-103">Applicare un'etichetta di conservazione a un modello di analisi dei documenti</span><span class="sxs-lookup"><span data-stu-id="01308-103">Apply a retention label to a document understanding model</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GydO]  

</br>


<span data-ttu-id="01308-104">Microsoft SharePoint Syntex consente di applicare facilmente un'[etichetta di conservazione](https://docs.microsoft.com/microsoft-365/compliance/retention) a un modello di analisi dei documenti.</span><span class="sxs-lookup"><span data-stu-id="01308-104">You can easily apply a [retention label](https://docs.microsoft.com/microsoft-365/compliance/retention) to a document understanding model in Microsoft SharePoint Syntex.</span></span>

<span data-ttu-id="01308-105">Le etichette di conservazione permettono di applicare impostazioni di conservazione ai documenti identificati dal modello di analisi dei documenti.</span><span class="sxs-lookup"><span data-stu-id="01308-105">Retention labels let you apply retention settings to the documents that your document understanding models identify.</span></span>  <span data-ttu-id="01308-106">Ad esempio, si può fare modo che il modello non solo identifichi i documenti di tipo *Contratto di assicurazione* caricati in una raccolta documenti, ma anche che applichi l'etichetta di conservazione *Business*, in modo che non sia possibile eliminare questi documenti dalla raccolta per il periodo di tempo specificato, ad esempio i cinque mesi successivi.</span><span class="sxs-lookup"><span data-stu-id="01308-106">For example, you want your model to not only identify any *Insurance notice* documents that are uploaded to your document library, but to also apply a *Business* retention tag to them so that these documents cannot be deleted from the document library for the specified time period (the next five months, for example).</span></span>

<span data-ttu-id="01308-107">Si può applicare al modello di analisi dei documenti un'etichetta di conservazione preesistente, usando le impostazioni del modello nella home page del modello.</span><span class="sxs-lookup"><span data-stu-id="01308-107">You can apply a pre-existing retention label to your document understanding model through your model settings on your model's home page.</span></span> 

> [!Important]
> <span data-ttu-id="01308-108">Affinché siano disponibili etichette di conservazione da applicare al modello di comprensione dei contenuti, occorre [crearle e pubblicarle nel Centro conformità Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels).</span><span class="sxs-lookup"><span data-stu-id="01308-108">For retention labels to be available to apply to your content understanding model, they need to be [created and published in the Microsoft 365 Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels).</span></span>

## <a name="to-add-a-retention-label-to-a-document-understanding-model"></a><span data-ttu-id="01308-109">Per aggiungere un'etichetta di conservazione a un modello di analisi dei documenti</span><span class="sxs-lookup"><span data-stu-id="01308-109">To add a retention label to a document understanding model</span></span>

1. <span data-ttu-id="01308-110">Nella home page del modello selezionare **Impostazioni modello**.</span><span class="sxs-lookup"><span data-stu-id="01308-110">From the model home page, select **Model settings**.</span></span></br>
2. <span data-ttu-id="01308-111">In **Impostazioni modello** selezionare il menu **Etichetta di conservazione** nella sezione **Sicurezza e conformità** per visualizzare un elenco delle etichette di conservazione disponibili per il modello.</span><span class="sxs-lookup"><span data-stu-id="01308-111">In **Model settings**, in the **Security and compliance** section, select the **Retention label** menu to see a list of retention labels that are available for your to apply to the model.</span></span></br>
 <span data-ttu-id="01308-112">![Menu Etichetta di conservazione](../media/content-understanding/retention-labels-menu.png)</span><span class="sxs-lookup"><span data-stu-id="01308-112">![Retention label menu](../media/content-understanding/retention-labels-menu.png)</span></span></br> 
3. <span data-ttu-id="01308-113">Selezionare l'etichetta di conservazione da applicare al modello e scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="01308-113">Select the retention label you want to apply to the model, and then select **Save**.</span></span></br>

<span data-ttu-id="01308-114">Dopo aver applicato l'etichetta conservazione al modello, è possibile applicarla:</span><span class="sxs-lookup"><span data-stu-id="01308-114">After applying the retention label to your model, you are able to apply it to a:</span></span>
- <span data-ttu-id="01308-115">A una nuova raccolta documenti</span><span class="sxs-lookup"><span data-stu-id="01308-115">New document library</span></span>
- <span data-ttu-id="01308-116">A una raccolta documenti a cui è già applicato il modello</span><span class="sxs-lookup"><span data-stu-id="01308-116">Document library to which the model is already applied</span></span>
 
## <a name="apply-the-retention-label-to-a-document-library-to-which-the-model-is-already-applied"></a><span data-ttu-id="01308-117">Applicare l'etichetta conservazione a una raccolta documenti a cui è già applicato il modello</span><span class="sxs-lookup"><span data-stu-id="01308-117">Apply the retention label to a document library to which the model is already applied</span></span>

<span data-ttu-id="01308-118">Se il modello di analisi dei documenti è già stato applicato a una raccolta documenti, è possibile procedere come segue per sincronizzare l'aggiornamento dell'etichetta di conservazione e applicarlo alla raccolta documenti:</span><span class="sxs-lookup"><span data-stu-id="01308-118">If your document understanding model has already been applied to a document library, you can do the following to sync your retention label update to apply it to the document library:</span></span></br>

1. <span data-ttu-id="01308-119">Nella home page del modello selezionare la raccolta documenti alla quale si vuole applicare l'aggiornamento dell'etichetta di conservazione nella sezione **Raccolte con questo modello**.</span><span class="sxs-lookup"><span data-stu-id="01308-119">On your model home page, in the **Libraries with this model** section, select the document library to which you want to apply the retention label update.</span></span> </br> 
2. <span data-ttu-id="01308-120">Selezionare **Sincronizza**.</span><span class="sxs-lookup"><span data-stu-id="01308-120">Select **Sync**.</span></span> </br>
 <span data-ttu-id="01308-121">![Sincronizzazione del modello](../media/content-understanding/sync-model.png)</span><span class="sxs-lookup"><span data-stu-id="01308-121">![Sync model](../media/content-understanding/sync-model.png)</span></span></br> 


<span data-ttu-id="01308-122">Dopo aver applicato l'aggiornamento e averlo sincronizzato con il modello, è possibile verificare che sia stato applicato eseguendo le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="01308-122">After applying the update and syncing it to your model, you can confirm that it has been applied by doing the following:</span></span>

1. <span data-ttu-id="01308-123">Nella sezione **Raccolte con questo modello** del centro contenuti fare clic sulla raccolta a cui è stato applicato il modello aggiornato.</span><span class="sxs-lookup"><span data-stu-id="01308-123">In the content center, in the **Libraries with this model** section, click on the library to which your updated model was applied.</span></span> </br>
2. <span data-ttu-id="01308-124">Nella visualizzazione Raccolta documenti selezionare l'icona informazioni per controllare le proprietà del modello.</span><span class="sxs-lookup"><span data-stu-id="01308-124">In your document library view, select the information icon to check the model properties.</span></span></br>  
3. <span data-ttu-id="01308-125">Selezionare il modello aggiornato nell'elenco **Modelli attivi**.</span><span class="sxs-lookup"><span data-stu-id="01308-125">In the **Active models** list, select your updated model.</span></span></br>
4. <span data-ttu-id="01308-126">Nella sezione **Etichetta di conservazione** sarà visualizzato il nome dell'etichetta di conservazione applicata.</span><span class="sxs-lookup"><span data-stu-id="01308-126">In the **Retention label** section you will see the name of the applied retention label.</span></span></br>


<span data-ttu-id="01308-127">Nella pagina di visualizzazione del modello della raccolta documenti comparirà una nuova colonna **Etichetta di conservazione**.</span><span class="sxs-lookup"><span data-stu-id="01308-127">On your model's view page in your document library, a new **Retention label** column will display.</span></span>  <span data-ttu-id="01308-128">Man mano che il modello classifica i file che identifica come appartenenti al proprio tipo di contenuto e li elenca nella visualizzazione della raccolta, nella colonna Etichetta di conservazione compare anche il nome dell'etichetta di conservazione applicata mediante il modello.</span><span class="sxs-lookup"><span data-stu-id="01308-128">As your model classifies files it identifies as belonging to it's content type and lists them in the library view, the Retention label column will also display the name of the retention label that has been applied to it through the model.</span></span>


<span data-ttu-id="01308-129">Ad esempio, a tutti i documenti *Contratto di assicurazione* identificati dal modello verrà anche applicata l'etichetta di conservazione *Business*, che ne impedisce l'eliminazione dalla raccolta documenti per cinque mesi.</span><span class="sxs-lookup"><span data-stu-id="01308-129">For example, all *Insurance notice* documents that your model identifies will also have the *Business* retention label applied to them, preventing them from being deleted from the document library for five months.</span></span> <span data-ttu-id="01308-130">Se qualcuno tenta di eliminare il file dalla raccolta documenti, verrà visualizzato un messaggio di errore che segnala che non è consentito a causa dell'etichetta di conservazione applicata.</span><span class="sxs-lookup"><span data-stu-id="01308-130">If an attempt is made to delete the file from the document library, an error will display saying it is not allowed because of the applied retention label.</span></span>

## <a name="see-also"></a><span data-ttu-id="01308-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="01308-131">See Also</span></span>
[<span data-ttu-id="01308-132">Creare un classificatore</span><span class="sxs-lookup"><span data-stu-id="01308-132">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="01308-133">Creare un estrattore</span><span class="sxs-lookup"><span data-stu-id="01308-133">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="01308-134">Panoramica sull'analisi dei documenti</span><span class="sxs-lookup"><span data-stu-id="01308-134">Document Understanding overview</span></span>](document-understanding-overview.md)


