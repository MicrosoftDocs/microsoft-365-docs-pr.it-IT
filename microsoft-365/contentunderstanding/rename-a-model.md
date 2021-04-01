---
title: Rinominare un modello in Microsoft SharePoint Syntex.
ms.author: chucked
author: chuckedmonson
manager: pamgreen
audience: admin
ms.reviewer: ssquires
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Informazioni su come e perché rinominare un modello in Microsoft SharePoint Syntex.
ms.openlocfilehash: d0d17f040199b2e6b60bfc98d325f18b6de0b7f2
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/30/2021
ms.locfileid: "51446003"
---
# <a name="rename-a-model-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="a9c52-103">Rinominare un modello in Microsoft SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="a9c52-103">Rename a model in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="a9c52-104">A un certo punto, è consigliabile rinominare un modello di analisi dei documenti.</span><span class="sxs-lookup"><span data-stu-id="a9c52-104">At some point, you might want to rename a document understanding model.</span></span> <span data-ttu-id="a9c52-105">Un esempio comune è quando si crea una bozza iniziale di un modello, si potrebbe non aver pensato a fondo al nome finale (ad esempio, si potrebbe aver impostato il nome "AlexWilburModel1").</span><span class="sxs-lookup"><span data-stu-id="a9c52-105">A common example is when you create an initial draft of a model, you might not have given a lot of thought as to the final name (for example, you might have named it “AlexWilburModel1”).</span></span> <span data-ttu-id="a9c52-106">Quando ci si avvicina alla finalizzazione del modello e lo si mette in uso, ci si rende conto che un nome più corretto potrebbe essere "Rinnovo contratti" e si vuole rinominarlo.</span><span class="sxs-lookup"><span data-stu-id="a9c52-106">As you come closer to finalizing the model and putting it to use, you realize that a more proper name would be “Contract Renewals,” and you want to rename it.</span></span>  

<span data-ttu-id="a9c52-107">Un altro esempio è quello in cui l'organizzazione prende la decisione di fare riferimento a un processo o a un tipo di documento con un nome diverso.</span><span class="sxs-lookup"><span data-stu-id="a9c52-107">Another example is when your organization makes a decision to refer to a process or document type by a different name.</span></span> <span data-ttu-id="a9c52-108">Ad esempio, quando si crea il modello e si è pronti per applicarlo, l'organizzazione potrebbe avere il compito di fare in modo che tutti i "Contratti" siano formalmente denominati "Accordi".</span><span class="sxs-lookup"><span data-stu-id="a9c52-108">For example, after you create your model and are ready to apply it, your organization might mandate that all “Contracts” will now formally be referred to as “Agreements.”</span></span> <span data-ttu-id="a9c52-109">Se necessario, è possibile scegliere di rinominare il modello da "Rinnovi contrattuali" in "Rinnovi degli Accordi".</span><span class="sxs-lookup"><span data-stu-id="a9c52-109">If needed, you can choose to rename your model from “Contract Renewals” to “Agreement Renewals.”</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a9c52-110">È possibile rinominare un modello di analisi dei documenti solo se non è stato applicato a una raccolta documenti.</span><span class="sxs-lookup"><span data-stu-id="a9c52-110">You can only rename a document understanding model if it has not been applied to a document library.</span></span> 

<span data-ttu-id="a9c52-111">La ridenominazione di un modello rinomina anche [tipo di contenuto](/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) associato al modello.</span><span class="sxs-lookup"><span data-stu-id="a9c52-111">Renaming a model also renames the [content type](/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) that is associated with the model.</span></span>

## <a name="rename-a-model"></a><span data-ttu-id="a9c52-112">Rinominare un modello</span><span class="sxs-lookup"><span data-stu-id="a9c52-112">Rename a model</span></span>

<span data-ttu-id="a9c52-113">Seguire questi passaggi per rinominare un modello di analisi dei documenti.</span><span class="sxs-lookup"><span data-stu-id="a9c52-113">Follow these steps to rename a document understanding model.</span></span>

1. <span data-ttu-id="a9c52-114">Nel centro contenuti, selezionare **Modelli** per visualizzare l'elenco dei modelli.</span><span class="sxs-lookup"><span data-stu-id="a9c52-114">From the content center, select **Models** to see your models list.</span></span>

2. <span data-ttu-id="a9c52-115">Alla pagina **Modelli**, selezionare il modello che si desidera rinominare.</span><span class="sxs-lookup"><span data-stu-id="a9c52-115">On the **Models** page, select the model you want to rename.</span></span>

3. <span data-ttu-id="a9c52-116">Usando la barra multifunzione o il pulsante **Mostra azioni** (accanto al nome modello), selezionare **Rinomina**.</span><span class="sxs-lookup"><span data-stu-id="a9c52-116">By using either the ribbon or the **Show actions** button (next to the model name), select **Rename**.</span></span> </br>

    ![Screenshot della pagina Modelli che mostra un modello selezionato con le opzioni Rinomina evidenziate.](../media/content-understanding/select-model-rename-both.png) </br>

4. <span data-ttu-id="a9c52-118">Nel riquadro **Rinomina modello** :</span><span class="sxs-lookup"><span data-stu-id="a9c52-118">On the **Rename model** panel:</span></span>

   <span data-ttu-id="a9c52-119">a.</span><span class="sxs-lookup"><span data-stu-id="a9c52-119">a.</span></span> <span data-ttu-id="a9c52-120">In **Nuovo nome**, immettere il nuovo nome del modello che si desidera rinominare.</span><span class="sxs-lookup"><span data-stu-id="a9c52-120">Under **New name**, enter the new name of the model that you want to rename.</span></span></br>

    ![Screenshot che mostra il pannello Rinomina modello.](../media/content-understanding/rename-model-panel.png) </br>

   <span data-ttu-id="a9c52-122">b.</span><span class="sxs-lookup"><span data-stu-id="a9c52-122">b.</span></span> <span data-ttu-id="a9c52-123">(Facoltativo) In **Impostazioni avanzate**, selezionare se si desidera associare un [tipo di contenuto](/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) esistente.</span><span class="sxs-lookup"><span data-stu-id="a9c52-123">(Optional) Under **Advanced settings**, select whether you want to associate an existing [content type](/sharepoint/governance/content-type-and-workflow-planning#content-type-overview).</span></span> <span data-ttu-id="a9c52-124">Se si sceglie **Usa un tipo di contenuto esistente**, il modello verrà rinominato in modo da corrispondere al tipo di contenuto selezionato.</span><span class="sxs-lookup"><span data-stu-id="a9c52-124">If you choose **Use an existing content type**, the model will be renamed to match the selected content type.</span></span>

5. <span data-ttu-id="a9c52-125">Selezionare **Rinomina**.</span><span class="sxs-lookup"><span data-stu-id="a9c52-125">Select **Rename**.</span></span>

## <a name="see-also"></a><span data-ttu-id="a9c52-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a9c52-126">See Also</span></span>
[<span data-ttu-id="a9c52-127">Creare un classificatore</span><span class="sxs-lookup"><span data-stu-id="a9c52-127">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="a9c52-128">Creare un estrattore</span><span class="sxs-lookup"><span data-stu-id="a9c52-128">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="a9c52-129">Rinominare un estrattore</span><span class="sxs-lookup"><span data-stu-id="a9c52-129">Rename an extractor</span></span>](rename-an-extractor.md)

[<span data-ttu-id="a9c52-130">Panoramica sull'analisi dei documenti</span><span class="sxs-lookup"><span data-stu-id="a9c52-130">Document Understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="a9c52-131">Tipi di spiegazione</span><span class="sxs-lookup"><span data-stu-id="a9c52-131">Explanation types</span></span>](explanation-types-overview.md)

[<span data-ttu-id="a9c52-132">Applicare un modello</span><span class="sxs-lookup"><span data-stu-id="a9c52-132">Apply a model</span></span>](apply-a-model.md) 
