---
title: Rinominare un estrattore in Microsoft SharePoint Syntex
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
description: Informazioni su come rinominare un estrattore in Microsoft SharePoint Syntex.
ms.openlocfilehash: 4c0db1d0523e30706a2e6ec31286e5e91adb61a6
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445995"
---
# <a name="rename-an-extractor-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="15f95-103">Rinominare un estrattore in Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="15f95-103">Rename an extractor in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="15f95-104">A un certo punto, potrebbe essere necessario rinominare un estrattore per poter fare riferimento a un campo dati estratto da un nome diverso.</span><span class="sxs-lookup"><span data-stu-id="15f95-104">At some point, you might need to rename an extractor if you want to refer to an extracted data field by a different name.</span></span> <span data-ttu-id="15f95-105">Ad esempio, l'organizzazione decide di apportare modifiche ai documenti contrattuali e chiama i "clienti" "acquirenti" nei documenti.</span><span class="sxs-lookup"><span data-stu-id="15f95-105">For example, your organization decides to make changes to their contract documents, and refers to “customers” as “clients” in their documents.</span></span> <span data-ttu-id="15f95-106">Nell'ambito dell'estrazione di un campo "Cliente" nel modello, sarà possibile rinominarlo "Acquirente".</span><span class="sxs-lookup"><span data-stu-id="15f95-106">If you were extracting a “Customer” field in your model, you can choose to rename it to “Client.”</span></span>

<span data-ttu-id="15f95-107">Quando viene sincronizzato il modello aggiornato nella libreria documenti di SharePoint, verrà visualizzata una nuova colonna "Acquirente" nella vista libreria documenti.</span><span class="sxs-lookup"><span data-stu-id="15f95-107">When you sync your updated model to your SharePoint document library, you will see a new “Client” column in your document library view.</span></span> <span data-ttu-id="15f95-108">La vista conserverà la colonna "Cliente" per le attività precedenti, ma aggiornerà la nuova colonna "Acquirente" per tutti i nuovi documenti elaborati dal modello.</span><span class="sxs-lookup"><span data-stu-id="15f95-108">Your view will retain the “Customer” column for past activity, but will update the new “Client” column for all new documents that are processed by your model.</span></span> 

> [!IMPORTANT]
>  <span data-ttu-id="15f95-109">Assicurarsi di sincronizzare il modello aggiornato nelle librerie documenti in cui è stato applicato in precedenza per fare in modo che venga visualizzato il nuovo nome colonna.</span><span class="sxs-lookup"><span data-stu-id="15f95-109">Make sure to sync your updated model to the document libraries where you had previously applied it for the new column name to display.</span></span> 

## <a name="rename-an-extractor"></a><span data-ttu-id="15f95-110">Rinominare un estrattore</span><span class="sxs-lookup"><span data-stu-id="15f95-110">Rename an extractor</span></span>

<span data-ttu-id="15f95-111">Seguire questi passaggi per rinominare un estrattore di entità.</span><span class="sxs-lookup"><span data-stu-id="15f95-111">Follow these steps to rename an entity extractor.</span></span>

1. <span data-ttu-id="15f95-112">Nel centro contenuti, selezionare **Modelli** per visualizzare l'elenco dei modelli.</span><span class="sxs-lookup"><span data-stu-id="15f95-112">From the content center, select **Models** to see your models list.</span></span>

2. <span data-ttu-id="15f95-113">Alla pagina **Modelli**, nella colonna **Nome**, selezionare il modello per cui si desidera rinominare un estrattore.</span><span class="sxs-lookup"><span data-stu-id="15f95-113">On the **Models** page, in the **Name** column, select the model for which you want to rename an extractor.</span></span>

3. <span data-ttu-id="15f95-114">In **Estrattori di entità**, selezionare il nome dell'estrattore che si desidera rinominare, quindi **Rinomina**.</span><span class="sxs-lookup"><span data-stu-id="15f95-114">Under **Entity extractors**, select the name of the extractor you want to rename, and then select **Rename**.</span></span></br>

    ![Screenshot della sezione Estrattori entità che mostra un estrattore selezionato con l'opzione Rinomina evidenziata.](../media/content-understanding/entity-extractor-rename.png) </br>

4. <span data-ttu-id="15f95-116">Nel pannello **Rinominare estrattore di entità**:</span><span class="sxs-lookup"><span data-stu-id="15f95-116">On the **Rename entity extractor** panel:</span></span>

   <span data-ttu-id="15f95-117">a.</span><span class="sxs-lookup"><span data-stu-id="15f95-117">a.</span></span> <span data-ttu-id="15f95-118">In **Nuovo nome**, immettere il nuovo nome dell'estrattore.</span><span class="sxs-lookup"><span data-stu-id="15f95-118">Under **New name**, enter the new name of the extractor.</span></span></br>

    ![Screenshot che mostra un pannello di un Estrattore di entità.](../media/content-understanding/rename-entity-extractor-panel.png) </br>

   <span data-ttu-id="15f95-120">b.</span><span class="sxs-lookup"><span data-stu-id="15f95-120">b.</span></span> <span data-ttu-id="15f95-121">(Facoltativo) In **Impostazioni avanzate**, selezionare se si desidera associare una colonna sito esistente.</span><span class="sxs-lookup"><span data-stu-id="15f95-121">(Optional) Under **Advanced settings**, select whether you want to associate an existing site column.</span></span>

5. <span data-ttu-id="15f95-122">Selezionare **Rinomina**.</span><span class="sxs-lookup"><span data-stu-id="15f95-122">Select **Rename**.</span></span>

## <a name="see-also"></a><span data-ttu-id="15f95-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="15f95-123">See Also</span></span>
[<span data-ttu-id="15f95-124">Creare un estrattore</span><span class="sxs-lookup"><span data-stu-id="15f95-124">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="15f95-125">Creare un classificatore</span><span class="sxs-lookup"><span data-stu-id="15f95-125">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="15f95-126">Rinominare un modello</span><span class="sxs-lookup"><span data-stu-id="15f95-126">Rename a model</span></span>](rename-a-model.md)

[<span data-ttu-id="15f95-127">Tipi di spiegazione</span><span class="sxs-lookup"><span data-stu-id="15f95-127">Explanation types</span></span>](explanation-types-overview.md)

[<span data-ttu-id="15f95-128">Sfruttare la tassonomia dell'archivio termini durante la creazione di un estrattore</span><span class="sxs-lookup"><span data-stu-id="15f95-128">Leverage term store taxonomy when creating an extractor</span></span>](leverage-term-store-taxonomy.md)

[<span data-ttu-id="15f95-129">Panoramica sull'analisi dei documenti</span><span class="sxs-lookup"><span data-stu-id="15f95-129">Document Understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="15f95-130">Applicare un modello</span><span class="sxs-lookup"><span data-stu-id="15f95-130">Apply a model</span></span>](apply-a-model.md) 
