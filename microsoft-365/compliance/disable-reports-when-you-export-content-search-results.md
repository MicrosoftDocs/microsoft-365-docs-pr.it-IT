---
title: Disabilitare i rapporti quando si esportano i risultati di Ricerca contenuto
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/30/2016
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MOE150
ms.assetid: c9b0ff0c-282b-4a44-b43f-cfc5b96557f9
description: Modificare il registro di sistema di Windows nel computer locale per disabilitare i report quando si esportano i risultati di una ricerca di contenuto dal centro sicurezza & conformità in Office 365. La disattivazione di questi rapporti consente di velocizzare il tempo di download e di risparmiare spazio su disco.
ms.openlocfilehash: f6abcf8afe70bc6ce04f0f9343e28879f7fed885
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37082933"
---
# <a name="disable-reports-when-you-export-content-search-results"></a><span data-ttu-id="eeee4-104">Disabilitare i rapporti quando si esportano i risultati di Ricerca contenuto</span><span class="sxs-lookup"><span data-stu-id="eeee4-104">Disable reports when you export Content Search results</span></span>

<span data-ttu-id="eeee4-105">Quando si utilizza lo strumento di esportazione di eDiscovery di Office 365 per esportare i risultati di una ricerca di contenuto nel centro sicurezza & conformità, lo strumento crea e Esporta automaticamente due rapporti che contengono informazioni aggiuntive sul contenuto esportato.</span><span class="sxs-lookup"><span data-stu-id="eeee4-105">When you use the Office 365 eDiscovery Export tool to export the results of a Content Search in the Security & Compliance Center, the tool automatically creates and exports two reports that contain additional information about the exported content.</span></span> <span data-ttu-id="eeee4-106">Questi rapporti sono il file results. csv e il file manifest. XML (vedere la sezione [domande frequenti su disabilitazione dei rapporti di esportazione](#frequently-asked-questions-about-disabling-export-reports) in questo argomento per una descrizione dettagliata di questi report).</span><span class="sxs-lookup"><span data-stu-id="eeee4-106">These reports are the Results.csv file and the Manifest.xml file (see the [Frequently asked questions about disabling export reports](#frequently-asked-questions-about-disabling-export-reports) section in this topic for detailed descriptions of these reports).</span></span> <span data-ttu-id="eeee4-107">Poiché questi file possono essere di dimensioni molto grandi, è possibile velocizzare il tempo di download e salvare lo spazio su disco impedendo l'esportazione di tali file.</span><span class="sxs-lookup"><span data-stu-id="eeee4-107">Because these files can be very large, you can speed up the download time and save disk space by preventing these files from being exported.</span></span> <span data-ttu-id="eeee4-108">A tale scopo, è possibile modificare il registro di sistema di Windows nel computer utilizzato per esportare i risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="eeee4-108">You can do this by changing the Windows Registry on the computer that you use to export the search results.</span></span> <span data-ttu-id="eeee4-109">Se si desidera includere i rapporti in un secondo momento, è possibile modificare l'impostazione del registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="eeee4-109">If you want to include the reports at a later time, you can edit the registry setting.</span></span> 
  
## <a name="create-registry-settings-to-disable-the-export-reports"></a><span data-ttu-id="eeee4-110">Creare le impostazioni del registro di sistema per disabilitare i report di esportazione</span><span class="sxs-lookup"><span data-stu-id="eeee4-110">Create registry settings to disable the export reports</span></span>

<span data-ttu-id="eeee4-111">Eseguire la procedura seguente nel computer che verrà utilizzato per esportare i risultati di una ricerca di contenuto.</span><span class="sxs-lookup"><span data-stu-id="eeee4-111">Perform the following procedure on the computer that you'll use to export the results a content search.</span></span>
  
1. <span data-ttu-id="eeee4-112">Chiudere lo strumento di esportazione di Office 365 eDiscovery se è aperto.</span><span class="sxs-lookup"><span data-stu-id="eeee4-112">Close the Office 365 eDiscovery Export tool if it's open.</span></span>
    
2. <span data-ttu-id="eeee4-113">Eseguire una o entrambe le operazioni seguenti, a seconda del rapporto di esportazione che si desidera disabilitare.</span><span class="sxs-lookup"><span data-stu-id="eeee4-113">Perform one or both of the following steps, depending on which export report you want to disable.</span></span>
    
    - <span data-ttu-id="eeee4-114">**Results. csv**</span><span class="sxs-lookup"><span data-stu-id="eeee4-114">**Results.csv**</span></span>
    
      <span data-ttu-id="eeee4-115">Salvare il testo seguente in un file del registro di sistema di Windows utilizzando un suffisso FileName di. reg. ad esempio, DisableResultsCsv. reg.</span><span class="sxs-lookup"><span data-stu-id="eeee4-115">Save the following text to a Windows registry file by using a filename suffix of .reg; for example, DisableResultsCsv.reg.</span></span>
    
      ```
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d False 
      ```

    - <span data-ttu-id="eeee4-116">**Manifest. XML**</span><span class="sxs-lookup"><span data-stu-id="eeee4-116">**Manifest.xml**</span></span>
    
      <span data-ttu-id="eeee4-117">Salvare il testo seguente in un file del registro di sistema di Windows utilizzando un suffisso FileName di. reg. ad esempio, DisableManifestXml. reg.</span><span class="sxs-lookup"><span data-stu-id="eeee4-117">Save the following text to a Windows registry file by using a filename suffix of .reg; for example, DisableManifestXml.reg.</span></span>
    
      ```
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d False 
      ```

3. <span data-ttu-id="eeee4-118">In Esplora risorse fare clic o fare doppio clic sul file con estensione reg creato nei passaggi precedenti.</span><span class="sxs-lookup"><span data-stu-id="eeee4-118">In Windows Explorer, click or double-click the .reg file that you created in the previous steps.</span></span>
    
4. <span data-ttu-id="eeee4-119">Nella finestra controllo di accesso utente fare clic su **Sì** per consentire all'editor del registro di sistema di apportare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="eeee4-119">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
5. <span data-ttu-id="eeee4-120">Quando viene richiesto di continuare, fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="eeee4-120">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="eeee4-121">L'editor del registro di sistema Visualizza un messaggio in cui viene indicato che l'impostazione è stata aggiunta correttamente al registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="eeee4-121">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
  
## <a name="edit-registry-settings-to-re-enable-the-export-reports"></a><span data-ttu-id="eeee4-122">Modificare le impostazioni del registro di sistema per riattivare i report di esportazione</span><span class="sxs-lookup"><span data-stu-id="eeee4-122">Edit registry settings to re-enable the export reports</span></span>

<span data-ttu-id="eeee4-123">Se i rapporti results. csv e manifest. XML sono stati disabilitati creando i file con estensione reg nella procedura precedente, è possibile modificare tali file per riabilitare un report in modo che venga esportato con i risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="eeee4-123">If you disabled the Results.csv and Manifest.xml reports by creating the .reg files in the previous procedure, you can edit those files to re-enable a report so that it's exported with the search results.</span></span> <span data-ttu-id="eeee4-124">Eseguire di nuovo la procedura seguente nel computer che verrà utilizzato per esportare i risultati di una ricerca di contenuto.</span><span class="sxs-lookup"><span data-stu-id="eeee4-124">Again, perform the following procedure on the computer that you'll use to export the results a content search.</span></span>
  
1. <span data-ttu-id="eeee4-125">Chiudere lo strumento di esportazione di Office 365 eDiscovery se è aperto.</span><span class="sxs-lookup"><span data-stu-id="eeee4-125">Close the Office 365 eDiscovery Export tool if it's open.</span></span>
    
2. <span data-ttu-id="eeee4-126">Modificare uno o entrambi i file. reg Edit creati nella procedura precedente.</span><span class="sxs-lookup"><span data-stu-id="eeee4-126">Edit one or both of the .reg edit files that you created in the previous procedure.</span></span>
    
    - <span data-ttu-id="eeee4-127">**Results. csv**</span><span class="sxs-lookup"><span data-stu-id="eeee4-127">**Results.csv**</span></span>
    
        <span data-ttu-id="eeee4-128">Aprire il file DisableResultsCsv. reg in blocco note, modificare il `False` valore `True`in e quindi salvare il file.</span><span class="sxs-lookup"><span data-stu-id="eeee4-128">Open the DisableResultsCsv.reg file in Notepad, change the value  `False` to  `True`, and then save the file.</span></span> <span data-ttu-id="eeee4-129">Ad esempio, dopo aver modificato il file, questo aspetto è simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="eeee4-129">For example, after you edit the file, it looks like this:</span></span>
    
        ```
        Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d True
        ```

    - <span data-ttu-id="eeee4-130">**Manifest. XML**</span><span class="sxs-lookup"><span data-stu-id="eeee4-130">**Manifest.xml**</span></span>
    
        <span data-ttu-id="eeee4-131">Aprire il file DisableManifestXml. reg in blocco note, modificare il `False` valore `True`in e quindi salvare il file.</span><span class="sxs-lookup"><span data-stu-id="eeee4-131">Open the DisableManifestXml.reg file in Notepad, change the value  `False` to  `True`, and then save the file.</span></span> <span data-ttu-id="eeee4-132">Ad esempio, dopo aver modificato il file, questo aspetto è simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="eeee4-132">For example, after you edit the file, it looks like this:</span></span>
    
      ```
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d True
      ```

3. <span data-ttu-id="eeee4-133">In Esplora risorse fare clic o fare doppio clic su un file con estensione reg modificato nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="eeee4-133">In Windows Explorer, click or double-click a .reg file that you edited in the previous step.</span></span>
    
4. <span data-ttu-id="eeee4-134">Nella finestra controllo di accesso utente fare clic su **Sì** per consentire all'editor del registro di sistema di apportare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="eeee4-134">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
5. <span data-ttu-id="eeee4-135">Quando viene richiesto di continuare, fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="eeee4-135">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="eeee4-136">L'editor del registro di sistema Visualizza un messaggio in cui viene indicato che l'impostazione è stata aggiunta correttamente al registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="eeee4-136">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
  
## <a name="frequently-asked-questions-about-disabling-export-reports"></a><span data-ttu-id="eeee4-137">Domande frequenti sulla disabilitazione dei rapporti di esportazione</span><span class="sxs-lookup"><span data-stu-id="eeee4-137">Frequently asked questions about disabling export reports</span></span>
<span data-ttu-id="eeee4-138"><a name="faqs"> </a></span><span class="sxs-lookup"><span data-stu-id="eeee4-138"></span></span>

 <span data-ttu-id="eeee4-139">**Quali sono i report results. csv e manifest. XML?**</span><span class="sxs-lookup"><span data-stu-id="eeee4-139">**What are the Results.csv and Manifest.xml reports?**</span></span>
  
<span data-ttu-id="eeee4-140">I file results. csv e manifest. XML contengono informazioni aggiuntive sul contenuto che è stato esportato.</span><span class="sxs-lookup"><span data-stu-id="eeee4-140">The Results.csv and Manifest.xml files contain additional information about the content that was exported.</span></span>
  
- <span data-ttu-id="eeee4-141">**Results. csv** un documento di Excel che contiene informazioni su ogni elemento che viene scaricato come risultato della ricerca.</span><span class="sxs-lookup"><span data-stu-id="eeee4-141">**Results.csv** An Excel document that contains information about each item that is download as a search result.</span></span> <span data-ttu-id="eeee4-142">Per la posta elettronica, il log dei risultati contiene informazioni su ogni messaggio, tra cui:</span><span class="sxs-lookup"><span data-stu-id="eeee4-142">For email, the result log contains information about each message, including:</span></span> 
    
  - <span data-ttu-id="eeee4-143">Il percorso del messaggio nella cassetta postale di origine (e se il messaggio è nella cassetta postale principale o di archiviazione).</span><span class="sxs-lookup"><span data-stu-id="eeee4-143">The location of the message in the source mailbox (including whether the message is in the primary or archive mailbox).</span></span>
    
  - <span data-ttu-id="eeee4-144">La data in cui è stato inviato o ricevuto il messaggio.</span><span class="sxs-lookup"><span data-stu-id="eeee4-144">The date the message was sent or received.</span></span>
    
  - <span data-ttu-id="eeee4-145">La riga dell'oggetto del messaggio.</span><span class="sxs-lookup"><span data-stu-id="eeee4-145">The Subject line from the message.</span></span>
    
  - <span data-ttu-id="eeee4-146">Il mittente e i destinatari del messaggio.</span><span class="sxs-lookup"><span data-stu-id="eeee4-146">The sender and recipients of the message.</span></span>
    
  - <span data-ttu-id="eeee4-147">Se il messaggio è un messaggio duplicato se è stata abilitata la deduplicazione quando si esportano i risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="eeee4-147">Whether the message is a duplicate message if you enabled de-duplication when exporting the search results.</span></span> <span data-ttu-id="eeee4-148">I messaggi duplicati avranno un valore nella colonna **padre ItemId** che identifica il messaggio come duplicato.</span><span class="sxs-lookup"><span data-stu-id="eeee4-148">Duplicate messages will have a value in the **Parent ItemId** column that identifies the message as a duplicate.</span></span> <span data-ttu-id="eeee4-149">Il valore nella colonna **ItemId padre** è uguale al valore nella colonna **DocumentID elemento** del messaggio che è stato esportato.</span><span class="sxs-lookup"><span data-stu-id="eeee4-149">The value in the **Parent ItemId** column is the same as the value in the **Item DocumentId** column of the message that was exported.</span></span> 
    
    <span data-ttu-id="eeee4-150">Per i documenti dei siti di SharePoint e OneDrive for business, il log dei risultati contiene informazioni su ogni documento, tra cui:</span><span class="sxs-lookup"><span data-stu-id="eeee4-150">For documents from SharePoint and OneDrive for Business sites, the result log contains information about each document, including:</span></span>
    
  - <span data-ttu-id="eeee4-151">L'URL per il documento.</span><span class="sxs-lookup"><span data-stu-id="eeee4-151">The URL for the document.</span></span>
    
  - <span data-ttu-id="eeee4-152">L’URL per la raccolta di siti in cui si trova il documento.</span><span class="sxs-lookup"><span data-stu-id="eeee4-152">The URL for the site collection where the document is located.</span></span>
    
  - <span data-ttu-id="eeee4-153">La data dell'ultima modifica al documento.</span><span class="sxs-lookup"><span data-stu-id="eeee4-153">The date that the document was last modified.</span></span>
    
  - <span data-ttu-id="eeee4-154">Il nome del documento (che si trova nella colonna Oggetto nel log dei risultati).</span><span class="sxs-lookup"><span data-stu-id="eeee4-154">The name of the document (which is located in the Subject column in the result log).</span></span>
    
- <span data-ttu-id="eeee4-155">**Manifest. XML** un file manifesto (in formato XML) che contiene informazioni su ogni elemento incluso nei risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="eeee4-155">**Manifest.xml** A manifest file (in XML format) that contains information about each item included in the search results.</span></span> <span data-ttu-id="eeee4-156">Le informazioni contenute in questo report sono uguali a quelle del report results. csv, ma sono nel formato specificato dal modello di riferimento per l'individuazione elettronica (EDRM).</span><span class="sxs-lookup"><span data-stu-id="eeee4-156">The information in this report is the same as the Results.csv report, but it's in the format specified by the Electronic Discovery Reference Model (EDRM).</span></span> <span data-ttu-id="eeee4-157">Per ulteriori informazioni su EDRM, accedere a [https://www.edrm.net](https://www.edrm.net).</span><span class="sxs-lookup"><span data-stu-id="eeee4-157">For more information about EDRM, go to [https://www.edrm.net](https://www.edrm.net).</span></span>
    
 <span data-ttu-id="eeee4-158">**Quando è necessario disabilitare l'esportazione di questi rapporti?**</span><span class="sxs-lookup"><span data-stu-id="eeee4-158">**When should I disable exporting these reports?**</span></span>
  
<span data-ttu-id="eeee4-159">Dipende dalle esigenze specifiche.</span><span class="sxs-lookup"><span data-stu-id="eeee4-159">It depends on your specific needs.</span></span> <span data-ttu-id="eeee4-160">Molte organizzazioni non richiedono ulteriori informazioni sui risultati di ricerca e non hanno bisogno di questi rapporti.</span><span class="sxs-lookup"><span data-stu-id="eeee4-160">Many organizations don't require additional information about search results, and don't need these reports.</span></span>
  
 <span data-ttu-id="eeee4-161">**Per quale computer è necessario eseguire questa operazione?**</span><span class="sxs-lookup"><span data-stu-id="eeee4-161">**What computer do I have to do this on?**</span></span>
  
 <span data-ttu-id="eeee4-162">È necessario modificare l'impostazione del registro di sistema in un computer locale in cui viene eseguito lo strumento di esportazione di eDiscovery di Office 365.</span><span class="sxs-lookup"><span data-stu-id="eeee4-162">You have to change the registry setting on any local computer that you run the Office 365 eDiscovery Export tool on.</span></span> 
  
 <span data-ttu-id="eeee4-163">**Dopo aver modificato questa impostazione, è necessario riavviare il computer?**</span><span class="sxs-lookup"><span data-stu-id="eeee4-163">**After I change this setting, do I have to restart the computer?**</span></span>
  
<span data-ttu-id="eeee4-164">No, non è necessario riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="eeee4-164">No, you don't have to restart the computer.</span></span> <span data-ttu-id="eeee4-165">Tuttavia, se è in esecuzione lo strumento di esportazione di Office 365 eDiscovery, è necessario chiuderlo e riavviarlo dopo aver modificato l'impostazione del registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="eeee4-165">But if the Office 365 eDiscovery Export tool is running, you have to close it and then restart it after you change the registry setting.</span></span>
  
 <span data-ttu-id="eeee4-166">**Una chiave del registro di sistema esistente viene modificata o viene creata una nuova chiave?**</span><span class="sxs-lookup"><span data-stu-id="eeee4-166">**Does an existing registry key get edited or does a new key get created?**</span></span>
  
<span data-ttu-id="eeee4-167">La prima volta che si esegue il file con estensione reg creato nella procedura descritta in questo argomento viene creata una nuova chiave del registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="eeee4-167">A new registry key is created the first time you run the .reg file that you created in the procedure in this topic.</span></span> <span data-ttu-id="eeee4-168">L'impostazione viene quindi modificata ogni volta che viene modificato e rieseguito il file. reg Edit.</span><span class="sxs-lookup"><span data-stu-id="eeee4-168">Then the setting is edited each time you change and re-run the .reg edit file.</span></span>
