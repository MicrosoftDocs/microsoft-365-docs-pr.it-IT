---
title: Scaricare i processi di esportazione per un caso advanced eDiscovery
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
ROBOTS: NOINDEX, NOFOLLOW
ms.custom: seo-marvel-mar2020
description: Installare e usare Azure Storage Explorer per scaricare i documenti esportati da un set di recensioni in Advanced eDiscovery.
ms.openlocfilehash: 0a73d157b2661202507883dd6542cdf6c6b482f8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926622"
---
# <a name="download-export-jobs-in-an-advanced-ediscovery-case"></a><span data-ttu-id="10402-103">Scaricare i processi di esportazione in un caso advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="10402-103">Download export jobs in an Advanced eDiscovery case</span></span>

<span data-ttu-id="10402-104">Quando si esportano documenti da un set di revisione in un caso advanced eDiscovery, i documenti vengono caricati in una posizione di Archiviazione di Azure fornita da Microsoft o in una posizione di Archiviazione di Azure gestita dall'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="10402-104">When you export documents from a review set in an Advanced eDiscovery case, the documents are uploaded to a Microsoft-provided Azure Storage location or to an Azure Storage location managed by your organization.</span></span> <span data-ttu-id="10402-105">Il tipo di percorso di Archiviazione di Azure usato dipende dall'opzione selezionata al momento dell'esportazione dei documenti.</span><span class="sxs-lookup"><span data-stu-id="10402-105">The type of Azure Storage location used depends on which option was selected when the documents were exported.</span></span>

<span data-ttu-id="10402-106">In questo articolo vengono fornite istruzioni su come usare Esplora risorse di archiviazione di Microsoft Azure per connettersi a un percorso di archiviazione di Azure per esplorare e scaricare i documenti esportati.</span><span class="sxs-lookup"><span data-stu-id="10402-106">This article provides instructions for how to use the Microsoft Azure Storage Explorer to connect to an Azure Storage location to browse and download the exported documents.</span></span> <span data-ttu-id="10402-107">Per altre informazioni su Azure Storage Explorer, vedere [Guida introduttiva: Usare Azure Storage Explorer.](/azure/storage/blobs/storage-quickstart-blobs-storage-explorer)</span><span class="sxs-lookup"><span data-stu-id="10402-107">For more information about Azure Storage Explorer, see [Quickstart: Use Azure Storage Explorer](/azure/storage/blobs/storage-quickstart-blobs-storage-explorer).</span></span>

## <a name="step-1-install-the-azure-storage-explorer"></a><span data-ttu-id="10402-108">Passaggio 1: installare Azure Storage Explorer</span><span class="sxs-lookup"><span data-stu-id="10402-108">Step 1: Install the Azure Storage Explorer</span></span>

<span data-ttu-id="10402-109">Il primo passaggio consiste nel scaricare e installare Azure Storage Explorer.</span><span class="sxs-lookup"><span data-stu-id="10402-109">The first step is to download and install the Azure Storage Explorer.</span></span> <span data-ttu-id="10402-110">Per istruzioni, vedere [Strumento Azure Storage Explorer.](https://go.microsoft.com/fwlink/p/?LinkId=544842)</span><span class="sxs-lookup"><span data-stu-id="10402-110">For instructions, see [Azure Storage Explorer tool](https://go.microsoft.com/fwlink/p/?LinkId=544842).</span></span> <span data-ttu-id="10402-111">Questo strumento consente di connettersi e scaricare i documenti esportati nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="10402-111">You use this tool to connect to and download the exported documents in Step 3.</span></span>

## <a name="step-2-obtain-the-sas-url-from-the-export-job"></a><span data-ttu-id="10402-112">Passaggio 2: Ottenere l'URL della firma di accesso condiviso dal processo di esportazione</span><span class="sxs-lookup"><span data-stu-id="10402-112">Step 2: Obtain the SAS URL from the export job</span></span>

<span data-ttu-id="10402-113">Il passaggio successivo consiste nell'ottenere l'URL della firma di accesso condiviso (SAS) generato al momento della creazione del processo di esportazione per esportare i documenti [da un set di revisioni.](export-documents-from-review-set.md)</span><span class="sxs-lookup"><span data-stu-id="10402-113">The next step is to obtain the shared access signature (SAS) URL that's generated when you created the export job to [export documents from a review set](export-documents-from-review-set.md).</span></span> <span data-ttu-id="10402-114">È possibile copiare l'URL della firma di accesso condiviso per i documenti caricati in un percorso di archiviazione di Azure fornito da Microsoft o in un percorso di archiviazione di Azure gestito dall'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="10402-114">You can copy the SAS URL for documents that are uploaded to a Microsoft-provided Azure Storage location or an Azure Storage location managed by your organization.</span></span> <span data-ttu-id="10402-115">In entrambi i casi, si usa l'URL della firma di accesso condiviso per connettersi al percorso di Archiviazione di Azure nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="10402-115">In either case, you use the SAS URL to connect to the Azure Storage location in Step 3.</span></span>

1. <span data-ttu-id="10402-116">Nella pagina **Advanced eDiscovery** passare al caso e quindi fare clic sulla **scheda** Esportazioni.</span><span class="sxs-lookup"><span data-stu-id="10402-116">On the **Advanced eDiscovery** page, go to the case, and then click the **Exports** tab.</span></span>

2. <span data-ttu-id="10402-117">Nella scheda **Esportazioni** fare clic sul processo di esportazione che si desidera scaricare.</span><span class="sxs-lookup"><span data-stu-id="10402-117">On the **Exports** tab, click the export job that you want to download.</span></span>

3. <span data-ttu-id="10402-118">Nella pagina a comparsa, in **Posizioni,** copiare l'URL della firma di accesso condiviso visualizzato.</span><span class="sxs-lookup"><span data-stu-id="10402-118">On the flyout page, under **Locations**, copy the SAS URL that's displayed.</span></span> <span data-ttu-id="10402-119">Se necessario, è possibile salvarlo in un file in modo da poterlo accedere al passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="10402-119">If necessary, you can save it to a file so you can access it in Step 3.</span></span>
 
   ![Copiare l'URL della firma di accesso condiviso visualizzato in Percorsi](../media/eDiscoExportJob.png)

## <a name="step-3-connect-to-the-azure-storage-location"></a><span data-ttu-id="10402-121">Passaggio 3: connettersi al percorso di archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="10402-121">Step 3: Connect to the Azure Storage location</span></span>

<span data-ttu-id="10402-122">Il passaggio finale consiste nell'usare Azure Storage Explorer e l'URL della firma di accesso condiviso per connettersi al percorso di Archiviazione di Azure e scaricare i documenti esportati in un computer locale.</span><span class="sxs-lookup"><span data-stu-id="10402-122">The final step is to use the Azure Storage Explorer and the SAS URL to connect to the Azure Storage location and download the documents that you exported to a local computer.</span></span>

1. <span data-ttu-id="10402-123">Aprire Azure Storage Explorer installato nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="10402-123">Open the Azure Storage Explorer that you installed in Step 1.</span></span>

2. <span data-ttu-id="10402-124">Fai clic **sull'icona Aggiungi account.**</span><span class="sxs-lookup"><span data-stu-id="10402-124">Click the **Add account** icon.</span></span> <span data-ttu-id="10402-125">In alternativa, è possibile fare clic con il pulsante destro **del mouse su Account di archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="10402-125">Alternatively, you can right-click **Storage Accounts**.</span></span>

   ![Fare clic sull'icona Aggiungi account](../media/AzureStorageConnect.png)

3. <span data-ttu-id="10402-127">Nella pagina **Connetti a Archiviazione di Azure** fare clic su Usa URI firma di accesso condiviso **e** quindi su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="10402-127">On the **Connect to Azure Storage** page, click **Use a shared access signature (SAS) URI** and then click **Next**.</span></span>

    ![Fare clic su Usa URI firma di accesso condiviso e quindi su Avanti](../media/AzureStorageConnect2.png)

4. <span data-ttu-id="10402-129">Nella pagina **Allega con URI SAS** fare clic nella casella URI e quindi incollare l'URL della firma di accesso condiviso ottenuto nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="10402-129">On the **Attach with SAS URI** page, click in the URI box, and then paste the SAS URL that you obtained in Step 2.</span></span> 

    ![Incollare l'URL della firma di accesso condiviso nella casella URI](../media/AzureStorageConnect3.png)

    <span data-ttu-id="10402-131">Si noti che una parte dell'URL della firma di accesso condiviso viene visualizzata nella **casella Nome** visualizzato.</span><span class="sxs-lookup"><span data-stu-id="10402-131">Notice that a portion of the SAS URL is displayed in the **Display name** box.</span></span> <span data-ttu-id="10402-132">Verrà utilizzato come nome visualizzato del contenitore creato  nell'account di archiviazione dopo la connessione al percorso di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="10402-132">This will be used as the display name of the container that's created under the **Storage accounts** after you connect to the storage location.</span></span> <span data-ttu-id="10402-133">Questo nome è costituito dall'ID del caso advanced eDiscovery e da un identificatore univoco.</span><span class="sxs-lookup"><span data-stu-id="10402-133">This name consists of the ID of the Advanced eDiscovery case is from and a unique identifier.</span></span> <span data-ttu-id="10402-134">È possibile mantenere il nome visualizzato predefinito o modificarlo.</span><span class="sxs-lookup"><span data-stu-id="10402-134">You can keep the default display name or change it.</span></span> <span data-ttu-id="10402-135">Se viene modificato, il nome visualizzato deve essere univoco.</span><span class="sxs-lookup"><span data-stu-id="10402-135">If you change it, the display name must be unique.</span></span>

5. <span data-ttu-id="10402-136">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="10402-136">Click **Next**.</span></span>

    <span data-ttu-id="10402-137">Viene **visualizzata la** pagina Riepilogo connessione.</span><span class="sxs-lookup"><span data-stu-id="10402-137">The **Connection summary** page is displayed.</span></span>

    ![Fare clic su Connetti nella pagina Riepilogo connessione per connettersi al percorso di archiviazione di Azure](../media/AzureStorageConnect4.png)

6. <span data-ttu-id="10402-139">Nella pagina **Riepilogo connessione** esaminare le informazioni sulla connessione e quindi fare clic su **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="10402-139">On the **Connection summary** page, review the connection information, and then click **Connect**.</span></span>

    <span data-ttu-id="10402-140">Viene aperto il nodo **Contenitori BLOB** (in **Account**  >  **di archiviazione (contenitori** \> allegati).</span><span class="sxs-lookup"><span data-stu-id="10402-140">The **Blob containers** node (under **Storage Accounts** > **(Attached Containers)** \> is opened.</span></span>

    ![Esportare processi nel nodo contenitori BLOB](../media/AzureStorageConnect5.png)

    <span data-ttu-id="10402-142">Contiene un contenitore denominato con il nome visualizzato del passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="10402-142">It contains a container named with the display name from step 4.</span></span> <span data-ttu-id="10402-143">Questo contenitore contiene una cartella per ogni processo di esportazione creato.</span><span class="sxs-lookup"><span data-stu-id="10402-143">This container contains a folder for each export job that you've created.</span></span> <span data-ttu-id="10402-144">Queste cartelle sono denominate con un ID corrispondente all'ID del processo di esportazione.</span><span class="sxs-lookup"><span data-stu-id="10402-144">These folders are named with an ID that corresponds to the ID of the export job.</span></span> <span data-ttu-id="10402-145">Questi ID di esportazione (e il nome dell'esportazione) sono disponibili in  Informazioni di supporto nella pagina a comparsa per ogni processo di preparazione dei dati per l'esportazione elencato nella **scheda** Processi. </span><span class="sxs-lookup"><span data-stu-id="10402-145">You can find these export IDs (and the name of the export) under **Support information** on the flyout page for each **Preparing data for export** job listed on the **Jobs** tab.</span></span>

7. <span data-ttu-id="10402-146">Fare doppio clic sulla cartella del processo di esportazione per aprirla.</span><span class="sxs-lookup"><span data-stu-id="10402-146">Double-click the export job folder to open it.</span></span>

   <span data-ttu-id="10402-147">Viene visualizzato un elenco di cartelle e rapporti di esportazione.</span><span class="sxs-lookup"><span data-stu-id="10402-147">A list of folders and export reports is displayed.</span></span>
   
    ![La cartella di esportazione contiene i file esportati e i report di esportazione](../media/AzureStorageConnect6.png)

   <span data-ttu-id="10402-149">La cartella del processo di esportazione contiene gli elementi seguenti.</span><span class="sxs-lookup"><span data-stu-id="10402-149">The export job folder contains the following items.</span></span> <span data-ttu-id="10402-150">Gli elementi effettivi nella cartella di esportazione sono determinati dalle opzioni di esportazione configurate al momento della creazione del processo di esportazione.</span><span class="sxs-lookup"><span data-stu-id="10402-150">The actual items in the export folder are determined by the export options configured when the export job was created.</span></span> <span data-ttu-id="10402-151">Per ulteriori informazioni, vedere [Export documents from a review set.](export-documents-from-review-set.md)</span><span class="sxs-lookup"><span data-stu-id="10402-151">For more information, see [Export documents from a review set](export-documents-from-review-set.md).</span></span>

    - <span data-ttu-id="10402-152">Export_load_file.csv: questo file CSV è un report di esportazione dettagli contenente informazioni su ogni documento esportato.</span><span class="sxs-lookup"><span data-stu-id="10402-152">Export_load_file.csv: This CSV file is a detail export report that contains information about each exported document.</span></span> <span data-ttu-id="10402-153">Il file è costituito da una colonna per ogni proprietà di metadati di un documento.</span><span class="sxs-lookup"><span data-stu-id="10402-153">The file consists of a column for each metadata property for a document.</span></span> <span data-ttu-id="10402-154">Per un elenco e una descrizione dei metadati inclusi in questo report, vedere la colonna **Nome** campo esportato nella tabella in Campi metadati documento [in Advanced eDiscovery.](document-metadata-fields-in-advanced-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="10402-154">For a list and description of the metadata that's included in this report, see the **Exported field name** column in the table in [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-advanced-ediscovery.md).</span></span>
    
    - <span data-ttu-id="10402-155">Summary.txt: un file di testo contenente un riepilogo dell'esportazione, incluse le statistiche di esportazione.</span><span class="sxs-lookup"><span data-stu-id="10402-155">Summary.txt: A text file that contains a summary of the export including export statistics.</span></span>
    
    - <span data-ttu-id="10402-156">Extracted_text_files: questa cartella contiene una versione di file di testo di ogni documento esportato.</span><span class="sxs-lookup"><span data-stu-id="10402-156">Extracted_text_files: This folder contains a text file version of each exported document.</span></span>
     
    - <span data-ttu-id="10402-157">NativeFiles: questa cartella contiene una versione file nativa di ogni documento esportato.</span><span class="sxs-lookup"><span data-stu-id="10402-157">NativeFiles: This folder contains a native file version of each exported document.</span></span>
    
    - <span data-ttu-id="10402-158">Error_files: questa cartella include gli elementi seguenti quando il processo di esportazione contiene file di errore:</span><span class="sxs-lookup"><span data-stu-id="10402-158">Error_files: This folder includes the following items when the export job contains any error files:</span></span> 
        
      - <span data-ttu-id="10402-159">ExtractionError.csv: questo file CSV contiene i metadati disponibili per i file che non sono stati estratti correttamente dall'elemento padre.</span><span class="sxs-lookup"><span data-stu-id="10402-159">ExtractionError.csv: This CSV file contains the available metadata for files that weren't properly extracted from their parent item.</span></span>
        
      - <span data-ttu-id="10402-160">ProcessingError: questa cartella contiene documenti con errori di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="10402-160">ProcessingError: This folder contains documents with processing errors.</span></span> <span data-ttu-id="10402-161">Questo contenuto si trova a livello di elemento, il che significa che se un allegato ha avuto un errore di elaborazione, anche il documento contenente l'allegato verrà incluso in questa cartella.</span><span class="sxs-lookup"><span data-stu-id="10402-161">This content is at an item level, which means if an attachment had a processing error, the document that contains the attachment will also be included in this folder.</span></span>
 
8. <span data-ttu-id="10402-162">Per esportare tutto il contenuto nell'esportazione, selezionare la cartella di esportazione e quindi fare clic su **Scarica.**</span><span class="sxs-lookup"><span data-stu-id="10402-162">To export all contents in the export, select the export folder, and then click **Download**.</span></span>

9. <span data-ttu-id="10402-163">Specificare il percorso in cui si desidera scaricare i file esportati e quindi fare clic su Seleziona cartella.</span><span class="sxs-lookup"><span data-stu-id="10402-163">Specify the location where you want to download the exported files, and then click Select folder.</span></span>

    <span data-ttu-id="10402-164">Azure Storage Explorer avvia il processo di esportazione.</span><span class="sxs-lookup"><span data-stu-id="10402-164">The Azure Storage Explorer starts the export process.</span></span> <span data-ttu-id="10402-165">Lo stato del download degli elementi esportati viene visualizzato nel **riquadro** Attività.</span><span class="sxs-lookup"><span data-stu-id="10402-165">The status of the downloading the exported items is displayed in the **Activities** pane.</span></span> <span data-ttu-id="10402-166">Al termine del download viene visualizzato un messaggio.</span><span class="sxs-lookup"><span data-stu-id="10402-166">A message is displayed when the download is finished.</span></span>

    ![Al termine del download viene visualizzato un messaggio](../media/AzureStorageConnect8.png)

> [!NOTE]
> <span data-ttu-id="10402-168">Anziché scaricare l'intero processo di esportazione, è possibile selezionare elementi specifici da scaricare.</span><span class="sxs-lookup"><span data-stu-id="10402-168">Instead of downloading the entire export job, you can select specific items to download.</span></span> <span data-ttu-id="10402-169">Anziché scaricare elementi, è possibile fare doppio clic su un elemento per visualizzarlo.</span><span class="sxs-lookup"><span data-stu-id="10402-169">And instead of downloading items, you can double-click an item to view it.</span></span>