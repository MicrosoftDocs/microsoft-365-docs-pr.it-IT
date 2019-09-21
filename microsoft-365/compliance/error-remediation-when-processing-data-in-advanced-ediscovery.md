---
title: Correzione degli errori durante l'elaborazione dei dati
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
description: ''
ms.openlocfilehash: 02fa8870d6edb4e1a6616604ee0e98638b217237
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37083767"
---
# <a name="error-remediation-when-processing-data"></a><span data-ttu-id="b16a3-102">Correzione degli errori durante l'elaborazione dei dati</span><span class="sxs-lookup"><span data-stu-id="b16a3-102">Error remediation when processing data</span></span>

<span data-ttu-id="b16a3-103">La correzione degli errori consente agli amministratori di eDiscovery di correggere i problemi relativi ai dati che impediscono al eDiscovery avanzato di elaborare correttamente il contenuto.</span><span class="sxs-lookup"><span data-stu-id="b16a3-103">Error remediation allows eDiscovery administrators the ability to rectify data issues that prevent Advanced eDiscovery from properly processing the content.</span></span> <span data-ttu-id="b16a3-104">Ad esempio, i file protetti da password non possono essere elaborati dopo che i file sono stati bloccati o crittografati.</span><span class="sxs-lookup"><span data-stu-id="b16a3-104">For example, files that are password protected can't be processed since the files are locked or encrypted.</span></span> <span data-ttu-id="b16a3-105">Se si utilizza la correzione degli errori, gli amministratori di eDiscovery possono scaricare i file con tale errore, rimuovere la protezione tramite password e quindi caricare i file corretti.</span><span class="sxs-lookup"><span data-stu-id="b16a3-105">Using error remediation, eDiscovery administrators can download files with such errors, remove the password protection, and then upload the remediated files.</span></span>

<span data-ttu-id="b16a3-106">Utilizzare il flusso di lavoro seguente per correggere i file con errori nei casi avanzati di eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="b16a3-106">Use the following workflow to remediate files with errors in Advanced eDiscovery cases.</span></span>

## <a name="create-an-error-remediation-session-to-remediate-files-with-processing-errors"></a><span data-ttu-id="b16a3-107">Creare una sessione di correzione degli errori per rimediare i file con errore di elaborazione</span><span class="sxs-lookup"><span data-stu-id="b16a3-107">Create an error remediation session to remediate files with processing errors</span></span>

>[!NOTE]
><span data-ttu-id="b16a3-108">Se la procedura guidata per la correzione degli errori viene chiusa in qualsiasi momento durante la routine seguente, è possibile tornare alla sessione di correzione degli errori dalla scheda **elaborazione** selezionando **correzioni** dal menu a discesa **Visualizza** .</span><span class="sxs-lookup"><span data-stu-id="b16a3-108">If the the error remediation wizard is closed at any time during the following procedure, you can return to the error remediation session from the **Processing** tab by selecting **Remediations** in the **View** drop-down menu.</span></span>

1. <span data-ttu-id="b16a3-109">Nella scheda **elaborazione** del caso Advanced eDiscovery, selezionare **errori** dal menu a discesa **Visualizza** , quindi selezionare un set di revisione o l'intero caso nel menu a discesa **ambito** .</span><span class="sxs-lookup"><span data-stu-id="b16a3-109">On the **Processing** tab in the Advanced eDiscovery case, select **Errors** in the **View** drop-down menu and then select a review set or the entire case in the **Scope** drop-down menu.</span></span> <span data-ttu-id="b16a3-110">In questa sezione vengono visualizzati tutti gli errori provenienti dal caso o dall'errore di un set di revisione specifico.</span><span class="sxs-lookup"><span data-stu-id="b16a3-110">This section displays all errors from the case or error from a specific review set.</span></span>

   ![Correzione degli errori](media/8c2faf1a-834b-44fc-b418-6a18aed8b81a.png)

2. <span data-ttu-id="b16a3-112">Selezionare gli errori che si desidera correggere facendo clic sul pulsante di opzione accanto al tipo di errore o al tipo di file.</span><span class="sxs-lookup"><span data-stu-id="b16a3-112">Select the errors you want to remediate by clicking the radio button next to either the error type or file type.</span></span>  <span data-ttu-id="b16a3-113">Nell'esempio seguente, viene rimediato un file protetto da password.</span><span class="sxs-lookup"><span data-stu-id="b16a3-113">In the following example, we're remediating a password protected file.</span></span>

3. <span data-ttu-id="b16a3-114">Fare clic su **nuova correzione degli errori**.</span><span class="sxs-lookup"><span data-stu-id="b16a3-114">Click **New error remediation**.</span></span>

    <span data-ttu-id="b16a3-115">Il flusso di lavoro di correzione dei problemi inizia con una fase di preparazione in cui i file con errori vengono copiati in una posizione di archiviazione di Azure fornita da Microsoft in modo da poterli scaricare nel computer locale per correggere i problemi.</span><span class="sxs-lookup"><span data-stu-id="b16a3-115">The error remediation workflow starts with a preparation stage where the files with errors are copied to a Microsoft-provided Azure Storage location so that you can download them to your local computer to remediate.</span></span>

    ![Preparazione della correzione degli errori](media/390572ec-7012-47c4-a6b6-4cbb5649e8a8.png)

4. <span data-ttu-id="b16a3-117">Al termine della preparazione, fare clic su **Avanti: scaricare i file** per continuare con il download.</span><span class="sxs-lookup"><span data-stu-id="b16a3-117">After the preparation is complete, click **Next: Download files** to proceed with download.</span></span>

    ![Scaricare file](media/6ac04b09-8e13-414a-9e24-7c75ba586363.png)

5. <span data-ttu-id="b16a3-119">Per scaricare i file, specificare il **percorso di destinazione per il download**.</span><span class="sxs-lookup"><span data-stu-id="b16a3-119">To download files, specify the **Destination path for download**.</span></span> <span data-ttu-id="b16a3-120">Si tratta di un percorso della cartella padre nel computer locale in cui verrà scaricato il file.</span><span class="sxs-lookup"><span data-stu-id="b16a3-120">This is a path to the parent folder on your local computer where the file will be downloaded.</span></span>  <span data-ttu-id="b16a3-121">Il percorso predefinito,%USERPROFILE%\Downloads\errors, punta alla cartella Downloads dell'utente connesso.</span><span class="sxs-lookup"><span data-stu-id="b16a3-121">The default path, %USERPROFILE%\Downloads\errors, points to the logged-in user's downloads folder.</span></span> <span data-ttu-id="b16a3-122">Se lo si desidera, è possibile modificare questo percorso.</span><span class="sxs-lookup"><span data-stu-id="b16a3-122">You can change this path if desired.</span></span> <span data-ttu-id="b16a3-123">In caso contrario, si consiglia di utilizzare un percorso di file locale per ottenere prestazioni ottimali.</span><span class="sxs-lookup"><span data-stu-id="b16a3-123">If you do change it, we recommend that you use a local file path for the best performance.</span></span> <span data-ttu-id="b16a3-124">Non utilizzare un percorso di rete remoto.</span><span class="sxs-lookup"><span data-stu-id="b16a3-124">Don't use a remote network path.</span></span> <span data-ttu-id="b16a3-125">Ad esempio, è possibile utilizzare il percorso **C:\Remediation**.</span><span class="sxs-lookup"><span data-stu-id="b16a3-125">For example, you could use the path **C:\Remediation**.</span></span> 

   <span data-ttu-id="b16a3-126">Il percorso della cartella padre viene aggiunto automaticamente al comando AzCopy (come valore del parametro **/dest** ).</span><span class="sxs-lookup"><span data-stu-id="b16a3-126">The path to the parent folder is automatically added to AzCopy command (as the value of the **/Dest** parameter).</span></span>

6. <span data-ttu-id="b16a3-127">Copiare il comando predefinito facendo clic su **copia negli Appunti**.</span><span class="sxs-lookup"><span data-stu-id="b16a3-127">Copy the predefined command by clicking **Copy to clipboard**.</span></span> <span data-ttu-id="b16a3-128">Aprire un prompt dei comandi di Windows, incollare il comando AzCopy e quindi premere **invio**.</span><span class="sxs-lookup"><span data-stu-id="b16a3-128">Open a Windows Command Prompt, paste the AzCopy command, and then press **Enter**.</span></span>  

    ![Preparare la correzione per gli errori](media/f364ab4d-31c5-4375-b69f-650f694a2f69.png)    

    > [!NOTE]
    > <span data-ttu-id="b16a3-130">È necessario utilizzare AzCopy v 8.1 per utilizzare correttamente il comando disponibile nella pagina **Scarica file** .</span><span class="sxs-lookup"><span data-stu-id="b16a3-130">You must use AzCopy v8.1 to successfully use the command that's provided on the **Download files** page.</span></span> <span data-ttu-id="b16a3-131">È inoltre necessario utilizzare AzCopy v 8.1 per caricare i file nel passaggio 10.</span><span class="sxs-lookup"><span data-stu-id="b16a3-131">You also must use AzCopy v8.1 to upload the files in step 10.</span></span> <span data-ttu-id="b16a3-132">Per installare questa versione di AzCopy, vedere [Transfer Data with the AzCopy v 8.1 in Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span><span class="sxs-lookup"><span data-stu-id="b16a3-132">To install this version of AzCopy, see [Transfer data with the AzCopy v8.1 on Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span></span> <span data-ttu-id="b16a3-133">Se il comando AzCopy fornito ha esito negativo, vedere [risolvere i problemi relativi a AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).</span><span class="sxs-lookup"><span data-stu-id="b16a3-133">If the supplied AzCopy command fails, please see [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).</span></span>

    <span data-ttu-id="b16a3-134">I file selezionati vengono scaricati nel percorso specificato nel passaggio 5.</span><span class="sxs-lookup"><span data-stu-id="b16a3-134">The files that you selected are downloaded to the location that you specified in step 5.</span></span> <span data-ttu-id="b16a3-135">Nella cartella padre (ad esempio, **C:\Remediation**), viene creata automaticamente la struttura di sottocartelle seguente:</span><span class="sxs-lookup"><span data-stu-id="b16a3-135">In the parent folder (for example, **C:\Remediation**), the following subfolder structure is automatically created:</span></span>

    `<Parent folder>\Subfolder 1\Subfolder 2\<file>`

    - <span data-ttu-id="b16a3-136">La *sottocartella 1* è denominata con l'ID del caso o del set di revisione, a seconda dell'ambito selezionato nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="b16a3-136">*Subfolder 1* is named with the ID for the case or the review set, depending on the scope that you selected in step 1.</span></span>

    - <span data-ttu-id="b16a3-137">La *sottocartella 2* è denominata con l'ID file del file scaricato</span><span class="sxs-lookup"><span data-stu-id="b16a3-137">*Subfolder 2* is named with the file ID of the downloaded file</span></span>

    - <span data-ttu-id="b16a3-138">Il file scaricato si trova nella *sottocartella 2* e viene denominato anche con l'ID file.</span><span class="sxs-lookup"><span data-stu-id="b16a3-138">The downloaded file is located in *Subfolder 2* and is also named with the file ID.</span></span>

    <span data-ttu-id="b16a3-139">Di seguito è riportato un esempio del percorso della cartella e del nome del file di errore creato quando gli elementi vengono scaricati nella cartella padre di **C:\Remediation** :</span><span class="sxs-lookup"><span data-stu-id="b16a3-139">Here's an example of the folder path and error file name that's created when items are downloaded to the **C:\Remediation** parent folder:</span></span>

    `C:\Remediation\232f8b7e-089c-4781-88c6-210da0615d32\d1459499146268a096ea20202cd029857d64087706e6d6ca2a224970ae3b8938\d1459499146268a096ea20202cd029857d64087706e6d6ca2a224970ae3b8938.docx`

    <span data-ttu-id="b16a3-140">Se si scaricano più file, ognuno di essi viene scaricato in una sottocartella denominata con l'ID del file.</span><span class="sxs-lookup"><span data-stu-id="b16a3-140">If multiple files are downloaded, each one is downloaded to a subfolder that's named with the file ID.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="b16a3-141">Quando si caricano i file nel passaggio 9 e nel passaggio 10, i file corretti devono avere lo stesso nome di file e trovarsi nella stessa struttura di sottocartelle.</span><span class="sxs-lookup"><span data-stu-id="b16a3-141">When you upload files in step 9 and step 10, the remediated files must have that same filename and be located in the same subfolder structure.</span></span> <span data-ttu-id="b16a3-142">La sottocartella e i nomi di file vengono utilizzati per associare il file di correzione al file di errore originale.</span><span class="sxs-lookup"><span data-stu-id="b16a3-142">The subfolder and file names are used to associated the remediated file with the original error file.</span></span> <span data-ttu-id="b16a3-143">Se la struttura di cartelle o i nomi di file vengono modificati, verrà visualizzato il seguente `Cannot apply Error Remediation to the current Workingset`messaggio di errore:.</span><span class="sxs-lookup"><span data-stu-id="b16a3-143">If the folder structure or file names are changed, you'll receive the following error: `Cannot apply Error Remediation to the current Workingset`.</span></span> <span data-ttu-id="b16a3-144">Per evitare problemi, è consigliabile mantenere i file corretti nella stessa cartella padre e sottocartella.</span><span class="sxs-lookup"><span data-stu-id="b16a3-144">To prevent any issues, we recommend that keep the remediated files in the same parent folder and subfolder structure.</span></span>

7. <span data-ttu-id="b16a3-145">Dopo aver scaricato i file, è possibile risolverli con uno strumento appropriato.</span><span class="sxs-lookup"><span data-stu-id="b16a3-145">After downloading the files, you can remediate them with an appropriate tool.</span></span> <span data-ttu-id="b16a3-146">Per i file protetti da password, esistono diversi strumenti di cracking delle password che è possibile utilizzare.</span><span class="sxs-lookup"><span data-stu-id="b16a3-146">For password-protected files, there are several password cracking tools you can use.</span></span> <span data-ttu-id="b16a3-147">Se si conoscono le password per i file, è possibile aprirle e rimuovere la protezione tramite password.</span><span class="sxs-lookup"><span data-stu-id="b16a3-147">If you know the passwords for the files, you can open them and remove the password protection.</span></span>

8. <span data-ttu-id="b16a3-148">Tornare a Advanced eDiscovery e la procedura guidata per la correzione degli errori, quindi fare clic su **Avanti: carica file**.</span><span class="sxs-lookup"><span data-stu-id="b16a3-148">Return to Advanced eDiscovery and the error remediation wizard and then click **Next: Upload files**.</span></span>  <span data-ttu-id="b16a3-149">Si passa alla pagina successiva in cui è ora possibile caricare i file.</span><span class="sxs-lookup"><span data-stu-id="b16a3-149">This moves to the next page where you can now upload the files.</span></span>

    ![Caricare file](media/af3d8617-1bab-4ecd-8de0-22e53acba240.png)

9. <span data-ttu-id="b16a3-151">Specificare la cartella padre in cui si trovano i file corretti nella casella di testo **percorso alla posizione dei file** .</span><span class="sxs-lookup"><span data-stu-id="b16a3-151">Specify the parent folder where the remediated files are located in the **Path to location of files** text box.</span></span> <span data-ttu-id="b16a3-152">Anche in questo caso, la cartella padre deve avere la stessa struttura di sottocartelle creata quando sono stati scaricati i file.</span><span class="sxs-lookup"><span data-stu-id="b16a3-152">Again, the parent folder must have the same subfolder structure that was created when you downloaded the files.</span></span>

    <span data-ttu-id="b16a3-153">Il percorso della cartella padre viene aggiunto automaticamente al comando AzCopy (come valore del parametro **/source** ).</span><span class="sxs-lookup"><span data-stu-id="b16a3-153">The path to the parent folder is automatically added to AzCopy command (as the value of the **/Source** parameter).</span></span>

10. <span data-ttu-id="b16a3-154">Copiare il comando predefinito facendo clic su **copia negli Appunti**.</span><span class="sxs-lookup"><span data-stu-id="b16a3-154">Copy the predefined command by clicking **Copy to clipboard**.</span></span> <span data-ttu-id="b16a3-155">Aprire un prompt dei comandi di Windows, incollare il comando AzCopy e quindi premere **invio**.</span><span class="sxs-lookup"><span data-stu-id="b16a3-155">Open a Windows Command Prompt, paste the AzCopy command, and then press **Enter**.</span></span> <span data-ttu-id="b16a3-156">caricare i file.</span><span class="sxs-lookup"><span data-stu-id="b16a3-156">upload the files.</span></span>

    ![ff2ff691-629F-4065-9b37-5333f937daf6. png](media/ff2ff691-629f-4065-9b37-5333f937daf6.png)

11. <span data-ttu-id="b16a3-158">Dopo aver eseguito il comando AzCopy, fare clic su **Avanti: elabora file**.</span><span class="sxs-lookup"><span data-stu-id="b16a3-158">After you run the AzCopy command, click **Next: Process files**.</span></span>

    <span data-ttu-id="b16a3-159">Al termine dell'elaborazione, è possibile passare a revisione set e visualizzare i file corretti.</span><span class="sxs-lookup"><span data-stu-id="b16a3-159">When processing is complete, you can go to review set and view the remediated files.</span></span> 

## <a name="what-happens-when-files-are-remediated"></a><span data-ttu-id="b16a3-160">Cosa accade quando i file vengono corretti</span><span class="sxs-lookup"><span data-stu-id="b16a3-160">What happens when files are remediated</span></span>

<span data-ttu-id="b16a3-161">Quando i file corretti vengono caricati, vengono conservati i metadati originali, ad eccezione dei campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="b16a3-161">When remediated files are uploaded, the original metadata is preserved except for the following fields:</span></span> 

- <span data-ttu-id="b16a3-162">ExtractedTextSize</span><span class="sxs-lookup"><span data-stu-id="b16a3-162">ExtractedTextSize</span></span>
- <span data-ttu-id="b16a3-163">HasText</span><span class="sxs-lookup"><span data-stu-id="b16a3-163">HasText</span></span>
- <span data-ttu-id="b16a3-164">IsErrorRemediate</span><span class="sxs-lookup"><span data-stu-id="b16a3-164">IsErrorRemediate</span></span>
- <span data-ttu-id="b16a3-165">LoadId</span><span class="sxs-lookup"><span data-stu-id="b16a3-165">LoadId</span></span>
- <span data-ttu-id="b16a3-166">ProcessingErrorMessage</span><span class="sxs-lookup"><span data-stu-id="b16a3-166">ProcessingErrorMessage</span></span>
- <span data-ttu-id="b16a3-167">ProcessingStatus</span><span class="sxs-lookup"><span data-stu-id="b16a3-167">ProcessingStatus</span></span>
- <span data-ttu-id="b16a3-168">Testo</span><span class="sxs-lookup"><span data-stu-id="b16a3-168">Text</span></span>
- <span data-ttu-id="b16a3-169">WordCount</span><span class="sxs-lookup"><span data-stu-id="b16a3-169">WordCount</span></span>
- <span data-ttu-id="b16a3-170">WorkingsetId</span><span class="sxs-lookup"><span data-stu-id="b16a3-170">WorkingsetId</span></span>

<span data-ttu-id="b16a3-171">Per una definizione di tutti i campi dei metadati in Advanced eDiscovery, vedere [Document Metadata Fields](document-metadata-fields.md).</span><span class="sxs-lookup"><span data-stu-id="b16a3-171">For a definition of all metadata fields in Advanced eDiscovery, see [Document metadata fields](document-metadata-fields.md).</span></span>
