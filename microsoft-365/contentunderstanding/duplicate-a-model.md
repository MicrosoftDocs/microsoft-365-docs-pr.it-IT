---
title: Duplicare un modello in Microsoft SharePoint Syntex
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
description: Informazioni su come e perché duplicare un modello in Microsoft SharePoint Syntex.
ms.openlocfilehash: 501c33b5309ca4af264a361c80fb0409c08c92e3
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/30/2021
ms.locfileid: "51446037"
---
# <a name="duplicate-a-model-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="41939-103">Duplicare un modello in Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="41939-103">Duplicate a model in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="41939-104">Duplicare un modello di analisi dei documenti consente di risparmiare tempo e risorse se si necessita di creare un nuovo modello e di sapere che un modello esistente è molto simile a ciò di cui si ha bisogno.</span><span class="sxs-lookup"><span data-stu-id="41939-104">Duplicating a document understanding model can save you time and effort if you need to create a new model, and know that an existing model is very similar to what you need.</span></span>

<span data-ttu-id="41939-105">Ad esempio, un modello esistente denominato "Contratti" classifica gli stessi file di cui si necessita per lavorare.</span><span class="sxs-lookup"><span data-stu-id="41939-105">For example, an existing model named “Contracts” classifies the same files you need to work with.</span></span> <span data-ttu-id="41939-106">Il nuovo modello estrarrà alcuni dati esistenti, ma dovrà essere aggiornato per estrarre alcuni dati aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="41939-106">Your new model will extract some of the existing data, but will need to be updated to extract some additional data.</span></span> <span data-ttu-id="41939-107">Invece di creare ed eseguire il training di un nuovo modello da zero, sarà possibile usare la funzionalità di duplicazione modello per creare una copia del modello Contratti, che copierà anche tutti gli elementi del training associati, quali estrattori di file ed entità.</span><span class="sxs-lookup"><span data-stu-id="41939-107">Instead of creating and training a new model from scratch, you can use the duplicate model feature to make a copy of the Contracts model, which will also copy all associated training items, such as example files and entity extractors.</span></span>

<span data-ttu-id="41939-108">Quando si duplica il modello, dopo averlo rinominato (ad esempio, "Rinnovi contrattuali"), sarà possibile apportare aggiornamenti allo stesso.</span><span class="sxs-lookup"><span data-stu-id="41939-108">When you duplicate the model, after you rename it (for example, to “Contract Renewals”), you can then make updates to it.</span></span> <span data-ttu-id="41939-109">Ad esempio, è possibile scegliere di rimuovere alcuni dei campi estratti esistenti di cui non si necessita, quindi eseguire il training del modello per estrarne uno nuovo (ad esempio, "Data di rinnovo").</span><span class="sxs-lookup"><span data-stu-id="41939-109">For example, you can choose to remove some of the existing extracted fields that you don’t need, and then train the model to extract a new one (for example, “Renewal date”).</span></span>

## <a name="duplicate-a-model"></a><span data-ttu-id="41939-110">Duplicare un modello</span><span class="sxs-lookup"><span data-stu-id="41939-110">Duplicate a model</span></span>

<span data-ttu-id="41939-111">Seguire questi passaggi per duplicare un modello di analisi dei documenti.</span><span class="sxs-lookup"><span data-stu-id="41939-111">Follow these steps to duplicate a document understanding model.</span></span>

1. <span data-ttu-id="41939-112">Nel centro contenuti, selezionare **Modelli** per visualizzare l'elenco dei modelli.</span><span class="sxs-lookup"><span data-stu-id="41939-112">From the content center, select **Models** to see your models list.</span></span>

2. <span data-ttu-id="41939-113">Alla pagina **Modelli**, selezionare il modello che si desidera duplicare.</span><span class="sxs-lookup"><span data-stu-id="41939-113">On the **Models** page, select the model you want to duplicate.</span></span>

3. <span data-ttu-id="41939-114">Usando la barra multifunzione o il pulsante **Mostra azioni** (accanto al nome modello), selezionare **Duplica**.</span><span class="sxs-lookup"><span data-stu-id="41939-114">By using either the ribbon or the **Show actions** button (next to the model name), select **Duplicate**.</span></span></br>

    ![Screenshot della pagina Modelli che mostra un modello selezionato con le opzioni Duplica evidenziate.](../media/content-understanding/select-model-duplicate-both.png) </br>

4. <span data-ttu-id="41939-116">Nel pannello **Duplica modello**:</span><span class="sxs-lookup"><span data-stu-id="41939-116">On the **Duplicate model** panel:</span></span>

   <span data-ttu-id="41939-117">a.</span><span class="sxs-lookup"><span data-stu-id="41939-117">a.</span></span> <span data-ttu-id="41939-118">In **Nome**, immettere il nuovo nome del modello che si desidera duplicare.</span><span class="sxs-lookup"><span data-stu-id="41939-118">Under **Name**, enter the new name of the model that you want to duplicate.</span></span></br>

    ![Screenshot che mostra il pannello Duplica modello.](../media/content-understanding/duplicate-model-panel.png) </br>

   <span data-ttu-id="41939-120">b.</span><span class="sxs-lookup"><span data-stu-id="41939-120">b.</span></span> <span data-ttu-id="41939-121">In **Descrizione**, aggiungere una descrizione del nuovo modello.</span><span class="sxs-lookup"><span data-stu-id="41939-121">Under **Description**, add a description of your new model.</span></span>

   <span data-ttu-id="41939-122">c.</span><span class="sxs-lookup"><span data-stu-id="41939-122">c.</span></span> <span data-ttu-id="41939-123">(Facoltativo) In **Impostazioni avanzate**, selezionare se si desidera associare un [tipo di contenuto](/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) esistente.</span><span class="sxs-lookup"><span data-stu-id="41939-123">(Optional) Under **Advanced settings**, select whether you want to associate an existing [content type](/sharepoint/governance/content-type-and-workflow-planning#content-type-overview).</span></span>

5. <span data-ttu-id="41939-124">Selezionare **Duplica**.</span><span class="sxs-lookup"><span data-stu-id="41939-124">Select **Duplicate**.</span></span>

## <a name="see-also"></a><span data-ttu-id="41939-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="41939-125">See Also</span></span>
[<span data-ttu-id="41939-126">Creare un classificatore</span><span class="sxs-lookup"><span data-stu-id="41939-126">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="41939-127">Rinominare un modello</span><span class="sxs-lookup"><span data-stu-id="41939-127">Rename a model</span></span>](rename-a-model.md)

[<span data-ttu-id="41939-128">Creare un estrattore</span><span class="sxs-lookup"><span data-stu-id="41939-128">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="41939-129">Panoramica sull'analisi dei documenti</span><span class="sxs-lookup"><span data-stu-id="41939-129">Document Understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="41939-130">Tipi di spiegazione</span><span class="sxs-lookup"><span data-stu-id="41939-130">Explanation types</span></span>](explanation-types-overview.md)

[<span data-ttu-id="41939-131">Applicare un modello</span><span class="sxs-lookup"><span data-stu-id="41939-131">Apply a model</span></span>](apply-a-model.md) 

[<span data-ttu-id="41939-132">Modalità di accessibilità di SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="41939-132">SharePoint Syntex Accessibility Mode</span></span>](accessibility-mode.md)