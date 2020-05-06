---
title: Scaricare i processi di esportazione per un caso
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
ms.assetid: ''
ms.custom: seo-marvel-mar2020
description: Installare e utilizzare Esplora archivi di Azure per scaricare i documenti esportati da un set di revisione in Advanced eDiscovery.
ms.openlocfilehash: 617ef0b27d5cab4098c505eaefb935ba8ae4ae2a
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035678"
---
# <a name="download-export-jobs"></a><span data-ttu-id="952e7-103">Scaricare processi di esportazione</span><span class="sxs-lookup"><span data-stu-id="952e7-103">Download export jobs</span></span>

<span data-ttu-id="952e7-104">Quando si esportano i documenti da un set di revisione in un caso avanzato di eDiscovery, i documenti vengono caricati in una posizione di archiviazione di Azure fornita da Microsoft o in un percorso di archiviazione di Azure gestito dall'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="952e7-104">When you export documents from a review set in an Advanced eDiscovery case, the documents are uploaded to a Microsoft-provided Azure Storage location or to an Azure Storage location managed by your organization.</span></span> <span data-ttu-id="952e7-105">Il tipo di percorso di archiviazione di Azure utilizzato dipende dall'opzione selezionata quando i documenti sono stati esportati.</span><span class="sxs-lookup"><span data-stu-id="952e7-105">The type of Azure Storage location used depends on which option was selected when the documents were exported.</span></span> 

<span data-ttu-id="952e7-106">In questo articolo vengono fornite le istruzioni per l'utilizzo di Microsoft Azure Storage Explorer per la connessione a un percorso di archiviazione di Azure per cercare e scaricare i documenti esportati.</span><span class="sxs-lookup"><span data-stu-id="952e7-106">This article provides instructions for how to use the Microsoft Azure Storage Explorer to connect to an Azure Storage location to browse and download the exported documents.</span></span> <span data-ttu-id="952e7-107">Per ulteriori informazioni su Esplora archivi di Azure, vedere [Guida introduttiva: utilizzare Esplora risorse di Azure](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-storage-explorer).</span><span class="sxs-lookup"><span data-stu-id="952e7-107">For more information about Azure Storage Explorer, see [Quickstart: Use Azure Storage Explorer](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-storage-explorer).</span></span>

## <a name="step-1-install-the-azure-storage-explorer"></a><span data-ttu-id="952e7-108">Passaggio 1: installare l'archivio di archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="952e7-108">Step 1: Install the Azure Storage Explorer</span></span>

<span data-ttu-id="952e7-109">Il primo passaggio consiste nel scaricare e installare Esplora archivi di Azure.</span><span class="sxs-lookup"><span data-stu-id="952e7-109">The first step is to download and install the Azure Storage Explorer.</span></span> <span data-ttu-id="952e7-110">Per istruzioni, vedere [Azure Storage Explorer tool](https://go.microsoft.com/fwlink/p/?LinkId=544842).</span><span class="sxs-lookup"><span data-stu-id="952e7-110">For instructions, see [Azure Storage Explorer tool](https://go.microsoft.com/fwlink/p/?LinkId=544842).</span></span> <span data-ttu-id="952e7-111">È possibile utilizzare questo strumento per connettersi e scaricare i documenti esportati nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="952e7-111">You use this tool to connect to and download the exported documents in Step 3.</span></span>

## <a name="step-2-obtain-the-sas-url-from-the-export-job"></a><span data-ttu-id="952e7-112">Passaggio 2: ottenere l'URL SAS dal processo di esportazione</span><span class="sxs-lookup"><span data-stu-id="952e7-112">Step 2: Obtain the SAS URL from the export job</span></span>

<span data-ttu-id="952e7-113">Il passaggio successivo consiste nell'ottenere l'URL della firma di accesso condiviso (SAS) che viene generato quando è stato creato il processo di esportazione per [esportare i documenti da un set di revisione](export-documents-from-review-set.md).</span><span class="sxs-lookup"><span data-stu-id="952e7-113">The next step is to obtain the shared access signature (SAS) URL that's generated when you created the export job to [export documents from a review set](export-documents-from-review-set.md).</span></span> <span data-ttu-id="952e7-114">È possibile copiare l'URL SAS per i documenti caricati in una posizione di archiviazione di Azure fornita da Microsoft o un percorso di archiviazione di Azure gestito dall'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="952e7-114">You can copy the SAS URL for documents that are uploaded to a Microsoft-provided Azure Storage location or an Azure Storage location managed by your organization.</span></span> <span data-ttu-id="952e7-115">In entrambi i casi, è possibile utilizzare l'URL SAS per connettersi al percorso di archiviazione di Azure nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="952e7-115">In either case, you use the SAS URL to connect to the Azure Storage location in Step 3.</span></span>

1. <span data-ttu-id="952e7-116">Nella pagina **Advanced eDiscovery** passare al caso, quindi fare clic sulla scheda **esportazioni** .</span><span class="sxs-lookup"><span data-stu-id="952e7-116">On the **Advanced eDiscovery** page, go to the case, and then click the **Exports** tab.</span></span>

2. <span data-ttu-id="952e7-117">Nella scheda **esportazioni** fare clic sul processo di esportazione che si desidera scaricare.</span><span class="sxs-lookup"><span data-stu-id="952e7-117">On the **Exports** tab, click the export job that you want to download.</span></span>

3. <span data-ttu-id="952e7-118">Nella pagina riquadro a comparsa, in **percorsi**, copiare l'URL SAS visualizzato.</span><span class="sxs-lookup"><span data-stu-id="952e7-118">On the flyout page, under **Locations**, copy the SAS URL that's displayed.</span></span> <span data-ttu-id="952e7-119">Se necessario, è possibile salvarlo in un file in modo che sia possibile accedervi nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="952e7-119">If necessary, you can save it to a file so you can access it in Step 3.</span></span>
 
   ![Copiare l'URL SAS visualizzato in percorsi](../media/eDiscoExportJob.png)

## <a name="step-3-connect-to-the-azure-storage-location"></a><span data-ttu-id="952e7-121">Passaggio 3: connettersi al percorso di archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="952e7-121">Step 3: Connect to the Azure Storage location</span></span>

<span data-ttu-id="952e7-122">Il passaggio finale consiste nell'utilizzare l'esploratore di archiviazione di Azure e l'URL SAS per connettersi al percorso di archiviazione di Azure e scaricare i documenti esportati in un computer locale.</span><span class="sxs-lookup"><span data-stu-id="952e7-122">The final step is to use the Azure Storage Explorer and the SAS URL to connect to the Azure Storage location and download the documents that you exported to a local computer.</span></span>

1.  <span data-ttu-id="952e7-123">Aprire l'esploratore di archiviazione di Azure installato nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="952e7-123">Open the Azure Storage Explorer that you installed in Step 1.</span></span>

2. <span data-ttu-id="952e7-124">Fare clic sull'icona **Aggiungi account** .</span><span class="sxs-lookup"><span data-stu-id="952e7-124">Click the **Add account** icon.</span></span> <span data-ttu-id="952e7-125">In alternativa, è possibile fare clic con il pulsante destro del mouse su **account di archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="952e7-125">Alternatively, you can right-click **Storage Accounts**.</span></span>

   ![Fare clic sull'icona Aggiungi account](../media/AzureStorageConnect.png)

3.  <span data-ttu-id="952e7-127">Nella pagina **connessione ad Azure Storage** fare clic su **utilizza un URI di firma di accesso condiviso** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="952e7-127">On the **Connect to Azure Storage** page, click **Use a shared access signature (SAS) URI** and then click **Next**.</span></span>

    ![Fare clic su Usa un URI per la firma di accesso condiviso e quindi fare clic su Avanti.](../media/AzureStorageConnect2.png)

4.  <span data-ttu-id="952e7-129">Nella pagina **Allega con URI SAS** fare clic nella casella URI e quindi incollare l'URL SAS ottenuto nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="952e7-129">On the **Attach with SAS URI** page, click in the URI box, and then paste the SAS URL that you obtained in Step 2.</span></span> 

    ![Incollare l'URL SAS nella casella URI](../media/AzureStorageConnect3.png)

    <span data-ttu-id="952e7-131">Si noti che una parte dell'URL SAS viene visualizzata nella casella **nome visualizzato** .</span><span class="sxs-lookup"><span data-stu-id="952e7-131">Notice that a portion of the SAS URL is displayed in the **Display name** box.</span></span> <span data-ttu-id="952e7-132">Verrà utilizzato come nome visualizzato del contenitore creato negli **account di archiviazione** dopo la connessione al percorso di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="952e7-132">This will be used as the display name of the container that's created under the **Storage accounts** after you connect to the storage location.</span></span> <span data-ttu-id="952e7-133">Questo nome è costituito dall'ID del caso Advanced eDiscovery e da un identificatore univoco.</span><span class="sxs-lookup"><span data-stu-id="952e7-133">This name consists of the ID of the Advanced eDiscovery case is from and a unique identifier.</span></span> <span data-ttu-id="952e7-134">È possibile mantenere il nome visualizzato predefinito o modificarlo.</span><span class="sxs-lookup"><span data-stu-id="952e7-134">You can keep the default display name or change it.</span></span> <span data-ttu-id="952e7-135">Se viene modificato, il nome visualizzato deve essere univoco.</span><span class="sxs-lookup"><span data-stu-id="952e7-135">If you change it, the display name must be unique.</span></span>

5.  <span data-ttu-id="952e7-136">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="952e7-136">Click **Next**.</span></span>

    <span data-ttu-id="952e7-137">Viene visualizzata la pagina **Riepilogo connessione** .</span><span class="sxs-lookup"><span data-stu-id="952e7-137">The **Connection summary** page is displayed.</span></span>
   
    ![Fare clic su Connetti nella pagina Riepilogo connessione per connettersi al percorso di archiviazione di Azure](../media/AzureStorageConnect4.png)

6. <span data-ttu-id="952e7-139">Nella pagina **Riepilogo connessione** esaminare le informazioni sulla connessione e quindi fare clic su **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="952e7-139">On the **Connection summary** page, review the connection information, and then click **Connect**.</span></span> 

    <span data-ttu-id="952e7-140">Viene aperto il nodo **contenitori BLOB** (in **account** > di archiviazione **(contenitori associati)** \> .</span><span class="sxs-lookup"><span data-stu-id="952e7-140">The **Blob containers** node (under **Storage Accounts** > **(Attached Containers)** \> is opened.</span></span> 

    ![Esportare processi nel nodo contenitori BLOB](../media/AzureStorageConnect5.png)

    <span data-ttu-id="952e7-142">Contiene un contenitore denominato con il nome visualizzato del passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="952e7-142">It contains a container named with the display name from step 4.</span></span> <span data-ttu-id="952e7-143">Questo contenitore contiene una cartella per ogni processo di esportazione creato.</span><span class="sxs-lookup"><span data-stu-id="952e7-143">This container contains a folder for each export job that you've created.</span></span> <span data-ttu-id="952e7-144">Queste cartelle sono denominate con un ID che corrisponde all'ID del processo di esportazione.</span><span class="sxs-lookup"><span data-stu-id="952e7-144">These folders are named with an ID that corresponds to the ID of the export job.</span></span> <span data-ttu-id="952e7-145">È possibile trovare questi ID di esportazione (e il nome dell'esportazione) in **informazioni di supporto** nella pagina a comparsa per ogni processo di **preparazione dei dati per l'esportazione** elencato nella scheda **processi** .</span><span class="sxs-lookup"><span data-stu-id="952e7-145">You can find these export IDs (and the name of the export) under **Support information** on the flyout page for each **Preparing data for export** job listed on the **Jobs** tab.</span></span>

7. <span data-ttu-id="952e7-146">Fare doppio clic sulla cartella Export Job per aprirla.</span><span class="sxs-lookup"><span data-stu-id="952e7-146">Double-click the export job folder to open it.</span></span>

   <span data-ttu-id="952e7-147">Viene visualizzato un elenco di cartelle e di report di esportazione.</span><span class="sxs-lookup"><span data-stu-id="952e7-147">A list of folders and export reports is displayed.</span></span>
   
    ![La cartella Export contiene i file esportati e i report di esportazione](../media/AzureStorageConnect6.png)

   <span data-ttu-id="952e7-149">La cartella dei processi di esportazione contiene gli elementi seguenti.</span><span class="sxs-lookup"><span data-stu-id="952e7-149">The export job folder contains the following items.</span></span> <span data-ttu-id="952e7-150">Gli elementi effettivi nella cartella Export sono determinati dalle opzioni di esportazione configurate al momento della creazione del processo di esportazione.</span><span class="sxs-lookup"><span data-stu-id="952e7-150">The actual items in the export folder are determined by the export options configured when the export job was created.</span></span> <span data-ttu-id="952e7-151">Per ulteriori informazioni, vedere [esportare documenti da un set di revisione](export-documents-from-review-set.md).</span><span class="sxs-lookup"><span data-stu-id="952e7-151">For more information, see [Export documents from a review set](export-documents-from-review-set.md).</span></span>

    - <span data-ttu-id="952e7-152">Export_load_file. csv: questo file CSV è un report di esportazione dettagliata che contiene informazioni su ogni documento esportato.</span><span class="sxs-lookup"><span data-stu-id="952e7-152">Export_load_file.csv: This CSV file is a detail export report that contains information about each exported document.</span></span> <span data-ttu-id="952e7-153">Il file è costituito da una colonna per ogni proprietà dei metadati di un documento.</span><span class="sxs-lookup"><span data-stu-id="952e7-153">The file consists of a column for each metadata property for a document.</span></span> <span data-ttu-id="952e7-154">Per un elenco e una descrizione dei metadati inclusi in questo report, vedere la colonna **nome campo esportato** nella tabella nei [campi dei metadati del documento in Advanced eDiscovery](document-metadata-fields.md).</span><span class="sxs-lookup"><span data-stu-id="952e7-154">For a list and description of the metadata that's included in this report, see the **Exported field name** column in the table in [Document metadata fields in Advanced eDiscovery](document-metadata-fields.md).</span></span>
    
    - <span data-ttu-id="952e7-155">Summary. txt: un file di testo contenente un riepilogo dell'esportazione, tra cui le statistiche di esportazione.</span><span class="sxs-lookup"><span data-stu-id="952e7-155">Summary.txt: A text file that contains a summary of the export including export statistics.</span></span>
    
    - <span data-ttu-id="952e7-156">Extracted_text_files: questa cartella contiene una versione del file di testo di ogni documento esportato.</span><span class="sxs-lookup"><span data-stu-id="952e7-156">Extracted_text_files: This folder contains a text file version of each exported document.</span></span>
     
    - <span data-ttu-id="952e7-157">NativeFiles: questa cartella contiene una versione di file nativa di ogni documento esportato.</span><span class="sxs-lookup"><span data-stu-id="952e7-157">NativeFiles: This folder contains a native file version of each exported document.</span></span>
    
    - <span data-ttu-id="952e7-158">Error_files: questa cartella include gli elementi seguenti quando il processo di esportazione contiene eventuali file di errore:</span><span class="sxs-lookup"><span data-stu-id="952e7-158">Error_files: This folder includes the following items when the export job contains any error files:</span></span> 
        
      - <span data-ttu-id="952e7-159">ExtractionError. csv: questo file CSV contiene i metadati disponibili per i file che non sono stati estratti correttamente dall'elemento padre.</span><span class="sxs-lookup"><span data-stu-id="952e7-159">ExtractionError.csv: This CSV file contains the available metadata for files that weren't properly extracted from their parent item.</span></span>
        
      - <span data-ttu-id="952e7-160">ProcessingError: questa cartella contiene documenti con errori di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="952e7-160">ProcessingError: This folder contains documents with processing errors.</span></span> <span data-ttu-id="952e7-161">Questo contenuto è a livello di elemento, il che significa che se un allegato ha un errore di elaborazione, il documento che contiene l'allegato verrà incluso anche in questa cartella.</span><span class="sxs-lookup"><span data-stu-id="952e7-161">This content is at an item level, which means if an attachment had a processing error, the document that contains the attachment will also be included in this folder.</span></span>
 
8. <span data-ttu-id="952e7-162">Per esportare tutto il contenuto nell'esportazione, selezionare la cartella Export, quindi fare clic su **download**.</span><span class="sxs-lookup"><span data-stu-id="952e7-162">To export all contents in the export, select the export folder, and then click **Download**.</span></span>

9. <span data-ttu-id="952e7-163">Specificare il percorso in cui si desidera scaricare i file esportati e quindi fare clic su Seleziona cartella.</span><span class="sxs-lookup"><span data-stu-id="952e7-163">Specify the location where you want to download the exported files, and then click Select folder.</span></span>

    <span data-ttu-id="952e7-164">Esplora archivi di Azure consente di avviare il processo di esportazione.</span><span class="sxs-lookup"><span data-stu-id="952e7-164">The Azure Storage Explorer starts the export process.</span></span> <span data-ttu-id="952e7-165">Lo stato del download degli elementi esportati viene visualizzato nel riquadro **attività** .</span><span class="sxs-lookup"><span data-stu-id="952e7-165">The status of the downloading the exported items is displayed in the **Activities** pane.</span></span> <span data-ttu-id="952e7-166">Quando il download è stato completato, viene visualizzato un messaggio.</span><span class="sxs-lookup"><span data-stu-id="952e7-166">A message is displayed when the download is finished.</span></span>

    ![Quando il download è stato completato, viene visualizzato un messaggio](../media/AzureStorageConnect8.png)

> [!NOTE]
> <span data-ttu-id="952e7-168">Invece di scaricare l'intero processo di esportazione, è possibile selezionare elementi specifici da scaricare.</span><span class="sxs-lookup"><span data-stu-id="952e7-168">Instead of downloading the entire export job, you can select specific items to download.</span></span> <span data-ttu-id="952e7-169">Invece di scaricare gli elementi, è possibile fare doppio clic su un elemento per visualizzarlo.</span><span class="sxs-lookup"><span data-stu-id="952e7-169">And instead of downloading items, you can double-click an item to view it.</span></span>
