---
title: Disabilitare i rapporti quando si esportano i risultati di Ricerca contenuto
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/30/2016
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c9b0ff0c-282b-4a44-b43f-cfc5b96557f9
ms.custom:
- seo-marvel-apr2020
description: Modificare il Windows Registro di sistema nel computer locale per disabilitare i report quando si esportano i risultati di una ricerca di contenuto dal Centro sicurezza & conformità.
ms.openlocfilehash: 0eaf9c9d1f70e03481b00d38d2e487709329c4cd
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817855"
---
# <a name="disable-reports-when-you-export-content-search-results"></a><span data-ttu-id="09fc2-103">Disabilitare i rapporti quando si esportano i risultati di Ricerca contenuto</span><span class="sxs-lookup"><span data-stu-id="09fc2-103">Disable reports when you export Content Search results</span></span>

<span data-ttu-id="09fc2-104">Quando si utilizza lo strumento di esportazione di eDiscovery per esportare i risultati di una ricerca di contenuto nel Centro sicurezza & conformità, lo strumento crea ed esporta automaticamente due report contenenti informazioni aggiuntive sul contenuto esportato.</span><span class="sxs-lookup"><span data-stu-id="09fc2-104">When you use the eDiscovery Export tool to export the results of a Content Search in the Security & Compliance Center, the tool automatically creates and exports two reports that contain additional information about the exported content.</span></span> <span data-ttu-id="09fc2-105">Questi report sono il file Results.csv e il file [](#frequently-asked-questions-about-disabling-export-reports) Manifest.xml (vedere la sezione Domande frequenti sulla disabilitazione dei report di esportazione in questo argomento per descrizioni dettagliate di questi report).</span><span class="sxs-lookup"><span data-stu-id="09fc2-105">These reports are the Results.csv file and the Manifest.xml file (see the [Frequently asked questions about disabling export reports](#frequently-asked-questions-about-disabling-export-reports) section in this topic for detailed descriptions of these reports).</span></span> <span data-ttu-id="09fc2-106">Poiché questi file possono essere molto grandi, è possibile velocizzare i tempi di download e risparmiare spazio su disco impedendo l'esportazione di tali file.</span><span class="sxs-lookup"><span data-stu-id="09fc2-106">Because these files can be very large, you can speed up the download time and save disk space by preventing these files from being exported.</span></span> <span data-ttu-id="09fc2-107">A tale scopo, è possibile modificare Windows del Registro di sistema nel computer utilizzato per esportare i risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="09fc2-107">You can do this by changing the Windows Registry on the computer that you use to export the search results.</span></span> <span data-ttu-id="09fc2-108">Se si desidera includere i report in un secondo momento, è possibile modificare l'impostazione del Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="09fc2-108">If you want to include the reports at a later time, you can edit the registry setting.</span></span> 
  
## <a name="create-registry-settings-to-disable-the-export-reports"></a><span data-ttu-id="09fc2-109">Creare impostazioni del Registro di sistema per disabilitare i report di esportazione</span><span class="sxs-lookup"><span data-stu-id="09fc2-109">Create registry settings to disable the export reports</span></span>

<span data-ttu-id="09fc2-110">Eseguire la procedura seguente nel computer che verrà utilizzato per esportare i risultati di una ricerca di contenuto.</span><span class="sxs-lookup"><span data-stu-id="09fc2-110">Perform the following procedure on the computer that you'll use to export the results a content search.</span></span>
  
1. <span data-ttu-id="09fc2-111">Chiudere lo strumento di esportazione di eDiscovery, se aperto.</span><span class="sxs-lookup"><span data-stu-id="09fc2-111">Close the eDiscovery Export tool if it's open.</span></span>
    
2. <span data-ttu-id="09fc2-112">Eseguire uno o entrambi i passaggi seguenti, a seconda del report di esportazione che si desidera disabilitare.</span><span class="sxs-lookup"><span data-stu-id="09fc2-112">Perform one or both of the following steps, depending on which export report you want to disable.</span></span>
    
    - <span data-ttu-id="09fc2-113">**Results.csv**</span><span class="sxs-lookup"><span data-stu-id="09fc2-113">**Results.csv**</span></span>
    
      <span data-ttu-id="09fc2-114">Salvare il testo seguente in un Windows del Registro di sistema utilizzando il suffisso del nome file reg; ad esempio DisableResultsCsv.reg.</span><span class="sxs-lookup"><span data-stu-id="09fc2-114">Save the following text to a Windows registry file by using a filename suffix of .reg; for example, DisableResultsCsv.reg.</span></span>
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d False 
      ```

    - <span data-ttu-id="09fc2-115">**Manifest.xml**</span><span class="sxs-lookup"><span data-stu-id="09fc2-115">**Manifest.xml**</span></span>
    
      <span data-ttu-id="09fc2-116">Salvare il testo seguente in un Windows del Registro di sistema utilizzando il suffisso del nome file reg; ad esempio DisableManifestXml.reg.</span><span class="sxs-lookup"><span data-stu-id="09fc2-116">Save the following text to a Windows registry file by using a filename suffix of .reg; for example, DisableManifestXml.reg.</span></span>
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d False 
      ```

3. <span data-ttu-id="09fc2-117">In Windows Explorer fare clic o fare doppio clic sul file reg creato nei passaggi precedenti.</span><span class="sxs-lookup"><span data-stu-id="09fc2-117">In Windows Explorer, click or double-click the .reg file that you created in the previous steps.</span></span>
    
4. <span data-ttu-id="09fc2-118">Nella finestra Controllo di accesso utente fare clic su **Sì** per consentire all'editor del Registro di sistema di apportare la modifica.</span><span class="sxs-lookup"><span data-stu-id="09fc2-118">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
5. <span data-ttu-id="09fc2-119">Quando viene richiesto di continuare, fare clic su **Sì.**</span><span class="sxs-lookup"><span data-stu-id="09fc2-119">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="09fc2-120">Nell'editor del Registro di sistema viene visualizzato un messaggio che indica che l'impostazione è stata aggiunta correttamente al Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="09fc2-120">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
  
## <a name="edit-registry-settings-to-re-enable-the-export-reports"></a><span data-ttu-id="09fc2-121">Modificare le impostazioni del Registro di sistema per abilitare di nuovo i report di esportazione</span><span class="sxs-lookup"><span data-stu-id="09fc2-121">Edit registry settings to re-enable the export reports</span></span>

<span data-ttu-id="09fc2-122">Se i report Results.csv e Manifest.xml sono stati disabilitati creando i file reg nella procedura precedente, è possibile modificare tali file per abilitare nuovamente un report in modo che sia esportato con i risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="09fc2-122">If you disabled the Results.csv and Manifest.xml reports by creating the .reg files in the previous procedure, you can edit those files to re-enable a report so that it's exported with the search results.</span></span> <span data-ttu-id="09fc2-123">Eseguire di nuovo la procedura seguente nel computer che verrà utilizzato per esportare i risultati di una ricerca di contenuto.</span><span class="sxs-lookup"><span data-stu-id="09fc2-123">Again, perform the following procedure on the computer that you'll use to export the results a content search.</span></span>
  
1. <span data-ttu-id="09fc2-124">Chiudere lo strumento di esportazione di eDiscovery, se aperto.</span><span class="sxs-lookup"><span data-stu-id="09fc2-124">Close the eDiscovery Export tool if it's open.</span></span>
    
2. <span data-ttu-id="09fc2-125">Modificare uno o entrambi i file reg creati nella procedura precedente.</span><span class="sxs-lookup"><span data-stu-id="09fc2-125">Edit one or both of the .reg edit files that you created in the previous procedure.</span></span>
    
    - <span data-ttu-id="09fc2-126">**Results.csv**</span><span class="sxs-lookup"><span data-stu-id="09fc2-126">**Results.csv**</span></span>
    
        <span data-ttu-id="09fc2-127">Aprire il file DisableResultsCsv.reg in Blocco note, modificare il valore `False` in e quindi salvare il `True` file.</span><span class="sxs-lookup"><span data-stu-id="09fc2-127">Open the DisableResultsCsv.reg file in Notepad, change the value  `False` to  `True`, and then save the file.</span></span> <span data-ttu-id="09fc2-128">Ad esempio, dopo aver modificato il file, il file sarà simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="09fc2-128">For example, after you edit the file, it looks like this:</span></span>
    
        ```text
        Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d True
        ```

    - <span data-ttu-id="09fc2-129">**Manifest.xml**</span><span class="sxs-lookup"><span data-stu-id="09fc2-129">**Manifest.xml**</span></span>
    
        <span data-ttu-id="09fc2-130">Aprire il file DisableManifestXml.reg in Blocco note, modificare il valore `False` in e quindi salvare il `True` file.</span><span class="sxs-lookup"><span data-stu-id="09fc2-130">Open the DisableManifestXml.reg file in Notepad, change the value  `False` to  `True`, and then save the file.</span></span> <span data-ttu-id="09fc2-131">Ad esempio, dopo aver modificato il file, il file sarà simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="09fc2-131">For example, after you edit the file, it looks like this:</span></span>
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d True
      ```

3. <span data-ttu-id="09fc2-132">In Windows Explorer fare clic o fare doppio clic su un file reg modificato nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="09fc2-132">In Windows Explorer, click or double-click a .reg file that you edited in the previous step.</span></span>
    
4. <span data-ttu-id="09fc2-133">Nella finestra Controllo di accesso utente fare clic su **Sì** per consentire all'editor del Registro di sistema di apportare la modifica.</span><span class="sxs-lookup"><span data-stu-id="09fc2-133">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
5. <span data-ttu-id="09fc2-134">Quando viene richiesto di continuare, fare clic su **Sì.**</span><span class="sxs-lookup"><span data-stu-id="09fc2-134">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="09fc2-135">Nell'editor del Registro di sistema viene visualizzato un messaggio che indica che l'impostazione è stata aggiunta correttamente al Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="09fc2-135">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
  
## <a name="frequently-asked-questions-about-disabling-export-reports"></a><span data-ttu-id="09fc2-136">Domande frequenti sulla disabilitazione dei report di esportazione</span><span class="sxs-lookup"><span data-stu-id="09fc2-136">Frequently asked questions about disabling export reports</span></span>

 <span data-ttu-id="09fc2-137">**Quali sono i Results.csv e Manifest.xml report?**</span><span class="sxs-lookup"><span data-stu-id="09fc2-137">**What are the Results.csv and Manifest.xml reports?**</span></span>
  
<span data-ttu-id="09fc2-138">I Results.csv e Manifest.xml contengono informazioni aggiuntive sul contenuto esportato.</span><span class="sxs-lookup"><span data-stu-id="09fc2-138">The Results.csv and Manifest.xml files contain additional information about the content that was exported.</span></span>
  
- <span data-ttu-id="09fc2-139">**Results.csv** Un Excel contenente informazioni su ogni elemento scaricato come risultato della ricerca.</span><span class="sxs-lookup"><span data-stu-id="09fc2-139">**Results.csv** An Excel document that contains information about each item that is download as a search result.</span></span> <span data-ttu-id="09fc2-140">Per la posta elettronica, il log dei risultati contiene informazioni su ogni messaggio, tra cui:</span><span class="sxs-lookup"><span data-stu-id="09fc2-140">For email, the result log contains information about each message, including:</span></span> 
    
  - <span data-ttu-id="09fc2-141">Il percorso del messaggio nella cassetta postale di origine (e se il messaggio è nella cassetta postale principale o di archiviazione).</span><span class="sxs-lookup"><span data-stu-id="09fc2-141">The location of the message in the source mailbox (including whether the message is in the primary or archive mailbox).</span></span>
    
  - <span data-ttu-id="09fc2-142">La data in cui è stato inviato o ricevuto il messaggio.</span><span class="sxs-lookup"><span data-stu-id="09fc2-142">The date the message was sent or received.</span></span>
    
  - <span data-ttu-id="09fc2-143">La riga dell'oggetto del messaggio.</span><span class="sxs-lookup"><span data-stu-id="09fc2-143">The Subject line from the message.</span></span>
    
  - <span data-ttu-id="09fc2-144">Il mittente e i destinatari del messaggio.</span><span class="sxs-lookup"><span data-stu-id="09fc2-144">The sender and recipients of the message.</span></span>
    
  - <span data-ttu-id="09fc2-145">Indica se il messaggio è duplicato se è stata abilitata la deduplicazione durante l'esportazione dei risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="09fc2-145">Whether the message is a duplicate message if you enabled de-duplication when exporting the search results.</span></span> <span data-ttu-id="09fc2-146">I messaggi duplicati avranno un valore nella **colonna ItemId** padre che identifica il messaggio come duplicato.</span><span class="sxs-lookup"><span data-stu-id="09fc2-146">Duplicate messages will have a value in the **Parent ItemId** column that identifies the message as a duplicate.</span></span> <span data-ttu-id="09fc2-147">Il valore nella **colonna Parent ItemId** corrisponde al valore nella colonna **Item DocumentId** del messaggio esportato.</span><span class="sxs-lookup"><span data-stu-id="09fc2-147">The value in the **Parent ItemId** column is the same as the value in the **Item DocumentId** column of the message that was exported.</span></span> 
    
    <span data-ttu-id="09fc2-148">Per i documenti SharePoint e OneDrive for Business, il registro dei risultati contiene informazioni su ogni documento, tra cui:</span><span class="sxs-lookup"><span data-stu-id="09fc2-148">For documents from SharePoint and OneDrive for Business sites, the result log contains information about each document, including:</span></span>
    
  - <span data-ttu-id="09fc2-149">L'URL per il documento.</span><span class="sxs-lookup"><span data-stu-id="09fc2-149">The URL for the document.</span></span>
    
  - <span data-ttu-id="09fc2-150">L’URL per la raccolta di siti in cui si trova il documento.</span><span class="sxs-lookup"><span data-stu-id="09fc2-150">The URL for the site collection where the document is located.</span></span>
    
  - <span data-ttu-id="09fc2-151">La data dell'ultima modifica al documento.</span><span class="sxs-lookup"><span data-stu-id="09fc2-151">The date that the document was last modified.</span></span>
    
  - <span data-ttu-id="09fc2-152">Il nome del documento (che si trova nella colonna Oggetto nel log dei risultati).</span><span class="sxs-lookup"><span data-stu-id="09fc2-152">The name of the document (which is located in the Subject column in the result log).</span></span>
    
- <span data-ttu-id="09fc2-153">**Manifest.xml** File manifesto (in formato XML) contenente informazioni su ogni elemento incluso nei risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="09fc2-153">**Manifest.xml** A manifest file (in XML format) that contains information about each item included in the search results.</span></span> <span data-ttu-id="09fc2-154">Le informazioni contenute in questo report sono le stesse del report Results.csv, ma sono nel formato specificato dal modello EDRM (Electronic Discovery Reference Model).</span><span class="sxs-lookup"><span data-stu-id="09fc2-154">The information in this report is the same as the Results.csv report, but it's in the format specified by the Electronic Discovery Reference Model (EDRM).</span></span> <span data-ttu-id="09fc2-155">Per ulteriori informazioni su EDRM, vedere [https://www.edrm.net](https://www.edrm.net) .</span><span class="sxs-lookup"><span data-stu-id="09fc2-155">For more information about EDRM, go to [https://www.edrm.net](https://www.edrm.net).</span></span>
    
 <span data-ttu-id="09fc2-156">**Quando è consigliabile disabilitare l'esportazione di questi report?**</span><span class="sxs-lookup"><span data-stu-id="09fc2-156">**When should I disable exporting these reports?**</span></span>
  
<span data-ttu-id="09fc2-157">Dipende dalle esigenze specifiche.</span><span class="sxs-lookup"><span data-stu-id="09fc2-157">It depends on your specific needs.</span></span> <span data-ttu-id="09fc2-158">Molte organizzazioni non richiedono ulteriori informazioni sui risultati della ricerca e non necessitano di questi report.</span><span class="sxs-lookup"><span data-stu-id="09fc2-158">Many organizations don't require additional information about search results, and don't need these reports.</span></span>
  
 <span data-ttu-id="09fc2-159">**In quale computer è necessario eseguire questa operazione?**</span><span class="sxs-lookup"><span data-stu-id="09fc2-159">**What computer do I have to do this on?**</span></span>
  
 <span data-ttu-id="09fc2-160">È necessario modificare l'impostazione del Registro di sistema in qualsiasi computer locale in cui si esegue lo strumento di esportazione di eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="09fc2-160">You have to change the registry setting on any local computer that you run the eDiscovery Export tool on.</span></span> 
  
 <span data-ttu-id="09fc2-161">**Dopo aver modificato questa impostazione, è necessario riavviare il computer?**</span><span class="sxs-lookup"><span data-stu-id="09fc2-161">**After I change this setting, do I have to restart the computer?**</span></span>
  
<span data-ttu-id="09fc2-162">No, non è necessario riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="09fc2-162">No, you don't have to restart the computer.</span></span> <span data-ttu-id="09fc2-163">Tuttavia, se lo strumento di esportazione di eDiscovery è in esecuzione, è necessario chiuderlo e riavviarlo dopo aver modificato l'impostazione del Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="09fc2-163">But if the eDiscovery Export tool is running, you have to close it and then restart it after you change the registry setting.</span></span>
  
 <span data-ttu-id="09fc2-164">**Una chiave del Registro di sistema esistente viene modificata o viene creata una nuova chiave?**</span><span class="sxs-lookup"><span data-stu-id="09fc2-164">**Does an existing registry key get edited or does a new key get created?**</span></span>
  
<span data-ttu-id="09fc2-165">Una nuova chiave del Registro di sistema viene creata alla prima esecuzione del file reg creato nella procedura descritta in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="09fc2-165">A new registry key is created the first time you run the .reg file that you created in the procedure in this topic.</span></span> <span data-ttu-id="09fc2-166">L'impostazione viene quindi modificata ogni volta che si modifica ed esegue di nuovo il file reg edit.</span><span class="sxs-lookup"><span data-stu-id="09fc2-166">Then the setting is edited each time you change and re-run the .reg edit file.</span></span>
