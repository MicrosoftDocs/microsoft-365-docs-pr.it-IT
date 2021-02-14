---
title: Preparare un file CSV per un elenco ID di Ricerca contenuto
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 82c97bb4-2b64-4edc-804d-cedbda525d22
ms.custom:
- seo-marvel-apr2020
description: Utilizzare i file CSV di una ricerca di contenuto esistente per creare una ricerca nell'elenco id che restituisce messaggi di posta elettronica specifici.
ms.openlocfilehash: 7b63a78d34306cf3afcef49276e584bc816c107f
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817975"
---
# <a name="prepare-a-csv-file-for-an-id-list-content-search"></a><span data-ttu-id="06a27-103">Preparare un file CSV per un elenco ID di Ricerca contenuto</span><span class="sxs-lookup"><span data-stu-id="06a27-103">Prepare a CSV file for an ID list Content Search</span></span>

<span data-ttu-id="06a27-104">È possibile cercare specifici messaggi di posta elettronica della cassetta postale e altri elementi della cassetta postale utilizzando un elenco di ID di Exchange.</span><span class="sxs-lookup"><span data-stu-id="06a27-104">You can search for specific mailbox email messages and other mailbox items using a list of Exchange IDs.</span></span> <span data-ttu-id="06a27-105">Per creare una ricerca nell'elenco id (formalmente denominata ricerca mirata), è necessario inviare un file con valori delimitati da virgole (CSV) che identifica gli elementi specifici della cassetta postale da cercare.</span><span class="sxs-lookup"><span data-stu-id="06a27-105">To create an ID list search (formally called a targeted search), you submit a comma separated value (CSV) file that identifies the specific mailbox items to search for.</span></span> <span data-ttu-id="06a27-106">Per questo file CSV si utilizza il file **Results.csv** o il file **Items.csv** non indicizzato che vengono inclusi quando si esportano i risultati di Ricerca contenuto o si esporta un report ricerca contenuto da ricerca contenuto e ricerca contenuto esistente.</span><span class="sxs-lookup"><span data-stu-id="06a27-106">For this CSV file you use the **Results.csv** file or the **Unindexed Items.csv** file that are included when you export the Content Search results or export a Content Search report from and existing Content Search.</span></span> <span data-ttu-id="06a27-107">Modificare quindi uno di questi file per indicare gli elementi specifici da cercare, quindi creare una nuova ricerca nell'elenco di ID e inviare il file CSV.</span><span class="sxs-lookup"><span data-stu-id="06a27-107">Then you edit one of these files to indicate the specific items to search for, and then create a new ID list search and submit the CSV file.</span></span>

<span data-ttu-id="06a27-108">Ecco una rapida panoramica del processo di creazione di una ricerca nell'elenco di ID.</span><span class="sxs-lookup"><span data-stu-id="06a27-108">Here's a quick overview of the process for creating an ID list search.</span></span>

1. <span data-ttu-id="06a27-109">Creare ed eseguire una ricerca di contenuto nuova o guidata nel Centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="06a27-109">Create and run a new or guided Content Search in the Security & Compliance Center.</span></span>

2. <span data-ttu-id="06a27-110">Esportare i risultati della ricerca di contenuto o esportare il report di ricerca contenuto.</span><span class="sxs-lookup"><span data-stu-id="06a27-110">Export the content search results or export the content search report.</span></span> <span data-ttu-id="06a27-111">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="06a27-111">For more information, see:</span></span>

    - [<span data-ttu-id="06a27-112">Esportare i risultati della Ricerca contenuto</span><span class="sxs-lookup"><span data-stu-id="06a27-112">Export Content Search results</span></span>](export-search-results.md)

    - [<span data-ttu-id="06a27-113">Esportare il rapporto della Ricerca contenuto</span><span class="sxs-lookup"><span data-stu-id="06a27-113">Export a Content Search report</span></span>](export-a-content-search-report.md)

3. <span data-ttu-id="06a27-114">Modificare il file **Results.csv** o il Items.csvnon **indicizzato e** identificare gli elementi specifici della cassetta postale che si desidera includere nella ricerca dell'elenco di ID.</span><span class="sxs-lookup"><span data-stu-id="06a27-114">Edit the **Results.csv** file or the **Unindexed Items.csv** and identify the specific mailbox items that you want to include in the ID list search.</span></span> <span data-ttu-id="06a27-115">Vedere le [istruzioni per](#prepare-the-csv-file-for-an-id-list-search) la preparazione di un file CSV per la ricerca di un elenco di ID.</span><span class="sxs-lookup"><span data-stu-id="06a27-115">See the [instructions](#prepare-the-csv-file-for-an-id-list-search) for preparing a CSV file for an ID list search.</span></span>

4. <span data-ttu-id="06a27-116">Creare una nuova ricerca nell'elenco di ID (vedere le [istruzioni](#create-an-id-list-search)) e inviare il file CSV preparato.</span><span class="sxs-lookup"><span data-stu-id="06a27-116">Create a new ID list search (see the [instructions](#create-an-id-list-search)) and submit the CSV file that you prepared.</span></span> <span data-ttu-id="06a27-117">La query di ricerca creata consente di cercare solo gli elementi selezionati nel file CSV.</span><span class="sxs-lookup"><span data-stu-id="06a27-117">The search query that's created will only search for the items selected in the CSV file.</span></span>

> [!NOTE]
> <span data-ttu-id="06a27-118">Le ricerche nell'elenco di ID sono supportate solo per gli elementi della cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="06a27-118">ID list searches are only supported for mailbox items.</span></span> <span data-ttu-id="06a27-119">Non è possibile cercare i documenti di SharePoint e OneDrive in una ricerca elenco ID.</span><span class="sxs-lookup"><span data-stu-id="06a27-119">You can't search for SharePoint and OneDrive documents in an ID list search.</span></span>

 <span data-ttu-id="06a27-120">**Perché creare una ricerca nell'elenco id?**</span><span class="sxs-lookup"><span data-stu-id="06a27-120">**Why create an ID list search?**</span></span> <span data-ttu-id="06a27-121">Se non è possibile determinare se un elemento risponde a una richiesta di eDiscovery in base ai metadati nei file **Results.csv** o **Items.csvnon** indicizzati, è possibile utilizzare una ricerca nell'elenco id per trovare, visualizzare in anteprima ed esportare tale elemento per determinare se è reattivo al caso in cui si sta esaminando.</span><span class="sxs-lookup"><span data-stu-id="06a27-121">If you're unable to determine if an item is responsive to an eDiscovery request based on the metadata in the **Results.csv** or **Unindexed Items.csv** files, you can use an ID list search to find, preview, and then export that item to determine if it's responsive to the case you're investigating.</span></span> <span data-ttu-id="06a27-122">Le ricerche nell'elenco id vengono in genere utilizzate per cercare e restituire un set specifico di elementi non indicizzati.</span><span class="sxs-lookup"><span data-stu-id="06a27-122">ID list searches are typically used to search for and return a specific set of unindexed items.</span></span>

## <a name="prepare-the-csv-file-for-an-id-list-search"></a><span data-ttu-id="06a27-123">Preparare il file CSV per la ricerca di un elenco di ID</span><span class="sxs-lookup"><span data-stu-id="06a27-123">Prepare the CSV file for an ID list search</span></span>

<span data-ttu-id="06a27-124">Dopo aver esportato i risultati della ricerca o il report per una ricerca di contenuto, è possibile eseguire la procedura seguente per preparare il file CSV per una ricerca nell'elenco di ID.</span><span class="sxs-lookup"><span data-stu-id="06a27-124">After you export the search results or report for a content search, you can perform the following steps to prepare the CSV file for an ID list search.</span></span> <span data-ttu-id="06a27-125">Questo file CSV identificherà ogni elemento nella ricerca dell'elenco di ID.</span><span class="sxs-lookup"><span data-stu-id="06a27-125">This CSV file will identify every item in the ID list search.</span></span>

<span data-ttu-id="06a27-126">Si noti che è possibile utilizzare un file CSV da una ricerca che  includeva siti di SharePoint e account di OneDrive, ma è possibile selezionare solo gli elementi della cassetta postale per una ricerca nell'elenco id.</span><span class="sxs-lookup"><span data-stu-id="06a27-126">Note that you can use a CSV file from a search that included SharePoint sites and OneDrive accounts, but you can select  *only*  mailbox items for an ID list search.</span></span> <span data-ttu-id="06a27-127">Se si seleziona un documento in SharePoint o OneDrive, il file CSV avrà esito negativo durante la creazione di una ricerca nell'elenco di ID.</span><span class="sxs-lookup"><span data-stu-id="06a27-127">If you select a document in SharePoint or OneDrive, the CSV file will fail validation when you create an ID list search.</span></span>

1. <span data-ttu-id="06a27-128">Aprire il **Results.csv** **o il** file di Items.csvnon indicizzato in Excel.</span><span class="sxs-lookup"><span data-stu-id="06a27-128">Open the **Results.csv** or **Unindexed Items.csv** file in Excel.</span></span>

2. <span data-ttu-id="06a27-129">Nella colonna **Selezionato** digitare **Sì** nella cella corrispondente all'elemento che si desidera cercare.</span><span class="sxs-lookup"><span data-stu-id="06a27-129">In the **Selected** column, type **Yes** in the cell that corresponds to the item that you want to search for.</span></span> <span data-ttu-id="06a27-130">Ripetere questo passaggio per ogni elemento che si desidera cercare.</span><span class="sxs-lookup"><span data-stu-id="06a27-130">Repeat this step for every item that you want to search for.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="06a27-131">Quando si apre il file CSV in Excel, il formato dei dati per la colonna **ID** documento viene modificato in **Generale.**</span><span class="sxs-lookup"><span data-stu-id="06a27-131">When you open the CSV file in Excel, the data format for the **Document ID** column is changed to **General**.</span></span> <span data-ttu-id="06a27-132">In questo modo viene visualizzato l'ID documento di un elemento in notazione scientifica.</span><span class="sxs-lookup"><span data-stu-id="06a27-132">This results in displaying the document ID for an item in scientific notation.</span></span> <span data-ttu-id="06a27-133">Ad esempio, l'ID documento "481037338205" viene visualizzato come "4.81037E+11" È necessario eseguire i passaggi successivi per modificare il formato dei dati della colonna **ID** documento in **Numero** per ripristinare il formato corretto per l'ID documento.</span><span class="sxs-lookup"><span data-stu-id="06a27-133">For example, the document ID of "481037338205" is displayed as "4.81037E+11" You have to perform the next steps to change the data format of the **Document ID** column to **Number** to restore the correct format for the document ID.</span></span> <span data-ttu-id="06a27-134">In caso contrario, la ricerca nell'elenco di ID che usa il file CSV avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="06a27-134">If you don't do this, the ID list search that uses the CSV file will fail.</span></span>

3. <span data-ttu-id="06a27-135">Fare clic con il pulsante destro **del mouse sull'intera colonna ID** documento e scegliere Formato **celle.**</span><span class="sxs-lookup"><span data-stu-id="06a27-135">Right-click the entire **Document ID** column and select **Format Cells**.</span></span>

4. <span data-ttu-id="06a27-136">Nella casella **Categoria** fare clic su **Numero.**</span><span class="sxs-lookup"><span data-stu-id="06a27-136">In the **Category** box, click **Number**.</span></span>

5. <span data-ttu-id="06a27-137">Modificare il numero di posizioni decimali su **0** e quindi fare clic su **OK** per salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="06a27-137">Change the number of decimal places to **0**, and then click **OK** to save your changes.</span></span> <span data-ttu-id="06a27-138">Si noti che i valori nella colonna ID documento vengono modificati in numeri.</span><span class="sxs-lookup"><span data-stu-id="06a27-138">Notice that the values in the Document ID column are changed to numbers.</span></span>

    <span data-ttu-id="06a27-139">Ecco un esempio di file CSV pronto per l'invio per una ricerca di contenuto di un elenco di ID.</span><span class="sxs-lookup"><span data-stu-id="06a27-139">Here's an example of the a CSV file that's ready to be submitted for a ID list content search.</span></span>

    ![Esempio di file CSV per una ricerca di contenuto mirata](../media/8371b8cb-1638-496e-9be1-fe1565757d67.png)

6. <span data-ttu-id="06a27-141">Salvare il file CSV o usare **Salva con nome** per salvare il file con un nome file diverso.</span><span class="sxs-lookup"><span data-stu-id="06a27-141">Save the CSV file or use **Save As** to the save the file with different file name.</span></span> <span data-ttu-id="06a27-142">In entrambi i casi, assicurarsi di salvare il file in formato CSV.</span><span class="sxs-lookup"><span data-stu-id="06a27-142">In both cases, be sure to save the file with the CSV format.</span></span>

## <a name="create-an-id-list-search"></a><span data-ttu-id="06a27-143">Creare una ricerca elenco ID</span><span class="sxs-lookup"><span data-stu-id="06a27-143">Create an ID list search</span></span>

<span data-ttu-id="06a27-144">Il passaggio successivo consiste nel creare un nuovo elenco di ID ricerca contenuto e inviare il file CSV preparato nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="06a27-144">The next step is to create a new ID list Content Search and submit the CSV file that you prepared in the previous step.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="06a27-145">È consigliabile creare una ricerca nell'elenco id non più di 2 giorni dopo l'esportazione dei risultati o del report da una ricerca di contenuto.</span><span class="sxs-lookup"><span data-stu-id="06a27-145">You should create an ID list search no more than 2 days after exporting the results or report from a Content Search.</span></span> <span data-ttu-id="06a27-146">Se i risultati della ricerca o il report sono stati esportati più di 2 giorni fa, è necessario esportare di nuovo i risultati della ricerca o il report per generare file CSV aggiornati.</span><span class="sxs-lookup"><span data-stu-id="06a27-146">If the search results or report where exported more than 2 days ago, you should re-export the search results or report to generate updated CSV files.</span></span> <span data-ttu-id="06a27-147">Puoi quindi preparare uno dei file CSV aggiornati e usarlo per creare una ricerca nell'elenco di ID.</span><span class="sxs-lookup"><span data-stu-id="06a27-147">Then you can prepare one of the updated CSV files and use it to create an ID list search.</span></span>

1. <span data-ttu-id="06a27-148">Nel Centro sicurezza & conformità passare a **Ricerca** \> **contenuto.**</span><span class="sxs-lookup"><span data-stu-id="06a27-148">In the Security & Compliance Center, go to **Search** \> **Content search**.</span></span>

2. <span data-ttu-id="06a27-149">Nella pagina **Ricerca** fare clic sulla freccia accanto all'icona Aggiungi nuova ricerca e quindi fare clic ![ su Cerca per ELENCO ](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif)  **ID.**</span><span class="sxs-lookup"><span data-stu-id="06a27-149">On the **Search** page, click the arrow next to ![Add icon](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **New search**, and then click **Search by ID List**.</span></span>

    ![Fare clic su Cerca per ID nell'elenco a discesa Nuova ricerca](../media/e65f9942-09b2-4127-865e-e64029a590df.png)

3. <span data-ttu-id="06a27-151">Nel riquadro **a comparsa** Elenco di ricerca per ID assegnare un  nome alla ricerca e facoltativamente descriverla, quindi fare clic su Sfoglia e selezionare il file CSV preparato nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="06a27-151">On the **Search by ID List** flyout, name the search (and optionally describe it) and then click **Browse** and select the CSV file that you prepared in the previous step.</span></span>

    <span data-ttu-id="06a27-152">Microsoft 365 tenta di convalidare il file CSV.</span><span class="sxs-lookup"><span data-stu-id="06a27-152">Microsoft 365 attempts to validate the CSV file.</span></span> <span data-ttu-id="06a27-153">Se la convalida non riesce, viene visualizzato un messaggio di errore che consente di risolvere gli errori di convalida.</span><span class="sxs-lookup"><span data-stu-id="06a27-153">If the validation is unsuccessful, an error message is displayed that might help you troubleshoot the validation errors.</span></span> <span data-ttu-id="06a27-154">Il file CSV deve essere convalidato correttamente per creare una ricerca nell'elenco di ID.</span><span class="sxs-lookup"><span data-stu-id="06a27-154">The CSV file has to be successfully validated to create an ID list search.</span></span>

4. <span data-ttu-id="06a27-155">Dopo aver convalidato correttamente il file CSV, fare clic **su Cerca** per creare la ricerca nell'elenco di ID.</span><span class="sxs-lookup"><span data-stu-id="06a27-155">After the CSV file is successfully validated, click **Search** to create the ID list search.</span></span>

    <span data-ttu-id="06a27-156">Ecco un esempio dei risultati della ricerca stimati e della query generata per una ricerca nell'elenco di ID.</span><span class="sxs-lookup"><span data-stu-id="06a27-156">Here's an example of the estimated search results and the query that's generated for an ID list search.</span></span>

    ![Query di ricerca per una ricerca di contenuto mirata nel riquadro dei dettagli](../media/dbd9e570-c04b-4056-a8a7-37e9916ec683.png)

    <span data-ttu-id="06a27-158">Si noti che il numero di elementi stimati visualizzati nelle statistiche per la ricerca id deve corrispondere al numero di elementi selezionati nel file CSV.</span><span class="sxs-lookup"><span data-stu-id="06a27-158">Note that the number of estimated items displayed in statistics for the ID search should match the number of items that you selected in the CSV file.</span></span>

5. <span data-ttu-id="06a27-159">Visualizzare in anteprima o esportare gli elementi restituiti dalla ricerca nell'elenco id.</span><span class="sxs-lookup"><span data-stu-id="06a27-159">Preview or export the items returned by the ID list search.</span></span>

> [!NOTE]
> <span data-ttu-id="06a27-160">Se si sposta una cassetta postale dopo aver creato una ricerca nell'elenco di ID, la query per la ricerca non restituirà gli elementi specificati.</span><span class="sxs-lookup"><span data-stu-id="06a27-160">If you move a mailbox after creating an ID list search, the query for the search won't return the specified items.</span></span> <span data-ttu-id="06a27-161">Questo perché la proprietà **DocumentId** per gli elementi della cassetta postale viene modificata quando una cassetta postale viene spostata.</span><span class="sxs-lookup"><span data-stu-id="06a27-161">That's because the **DocumentId** property for mailbox items are changed when a mailbox is moved.</span></span> <span data-ttu-id="06a27-162">Nella rara istanza in cui una cassetta postale viene spostata dopo aver creato una ricerca nell'elenco di ID, è necessario creare una nuova ricerca di contenuto (o aggiornare i risultati della ricerca di contenuto esistente) e quindi esportare i risultati della ricerca o il report per generare file CSV aggiornati che possono essere utilizzati per creare una nuova ricerca nell'elenco di ID.</span><span class="sxs-lookup"><span data-stu-id="06a27-162">In the rare instance when a mailbox is moved after you create an ID list search, you should create a new content search (or update the search results for the existing content search) and then export the search results or report to generate updated CSV files that can be used to create a new ID list search.</span></span>
