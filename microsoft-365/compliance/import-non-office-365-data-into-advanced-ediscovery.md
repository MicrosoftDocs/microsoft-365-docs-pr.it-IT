---
title: Importare contenuto non Microsoft 365 per l'analisi avanzata di eDiscovery
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- OEC150
- MET150
ms.assetid: 0ee60763-a30b-495b-8543-971c3384a801
description: Come eseguire la procedura per importare il contenuto non archiviato in Microsoft 365 in un BLOB di Azure in modo che possa essere analizzato con AeD
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: be30daa35770247a9dd342b88093872083075547
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/21/2020
ms.locfileid: "48636953"
---
# <a name="import-non-microsoft-365-content-for-advanced-ediscovery-classic-analysis"></a><span data-ttu-id="fb1fd-103">Importare contenuto non Microsoft 365 per l'analisi di Advanced eDiscovery (Classic)</span><span class="sxs-lookup"><span data-stu-id="fb1fd-103">Import non-Microsoft 365 content for Advanced eDiscovery (classic) analysis</span></span>

<span data-ttu-id="fb1fd-104">Non tutti i documenti che potrebbe essere necessario analizzare con Advanced eDiscovery vivranno in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fb1fd-104">Not all documents that you may need to analyze with Advanced eDiscovery will live in Microsoft 365.</span></span> <span data-ttu-id="fb1fd-105">Con la caratteristica di importazione di contenuto non Microsoft 365 in Advanced eDiscovery è possibile caricare documenti che non risiedono in Microsoft 365 (ad eccezione dei file PST) in un caso collegato, BLOB di archiviazione di Azure e analizzarli con Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="fb1fd-105">With the Non-Microsoft 365 content import feature in Advanced eDiscovery you can upload documents that don't live in Microsoft 365 (except PST files) into a case linked, Azure storage blob and analyze them with Advanced eDiscovery.</span></span> <span data-ttu-id="fb1fd-106">In questa procedura viene illustrato come portare i documenti non Microsoft 365 in Advanced eDiscovery per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="fb1fd-106">This procedure shows you how to bring your non-Microsoft 365 documents into Advanced eDiscovery for analysis.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fb1fd-p102">Per usare Advanced eDiscovery è necessario avere Office 365 E3 con il componente aggiuntivo Advanced Compliance o un abbonamento E5 dell'organizzazione. Se non si ha questo piano e si desidera provare Advanced eDiscovery, è possibile [richiedere una valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="fb1fd-p102">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="fb1fd-109">È possibile acquistare un abbonamento aggiuntivo per l'archiviazione dei dati di eDiscovery per il contenuto non Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fb1fd-109">You can purchase an Advanced eDiscovery data storage add-on subscription for your non-Microsoft 365 content.</span></span> <span data-ttu-id="fb1fd-110">Questo è disponibile solo per il contenuto che deve essere analizzato con Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="fb1fd-110">This is exclusively available for content that is to be analyzed with Advanced eDiscovery.</span></span> <span data-ttu-id="fb1fd-111">Seguire la procedura in [acquistare o modificare un componente aggiuntivo per Microsoft 365 for business](https://docs.microsoft.com/microsoft-365/commerce/buy-or-edit-an-add-on) e acquistare il componente aggiuntivo di archiviazione avanzata di eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="fb1fd-111">Follow the steps in [Buy or edit an add-on for Microsoft 365 for business](https://docs.microsoft.com/microsoft-365/commerce/buy-or-edit-an-add-on) and purchase the Advanced eDiscovery storage add-on.</span></span> 
  
## <a name="requirements-to-upload-non-office-365-content"></a><span data-ttu-id="fb1fd-112">Requisiti per caricare il contenuto non Office 365</span><span class="sxs-lookup"><span data-stu-id="fb1fd-112">Requirements to upload non-Office 365 content</span></span>

<span data-ttu-id="fb1fd-113">Se si utilizza la funzionalità carica non Office 365 come descritto in questa procedura, è necessario disporre di:</span><span class="sxs-lookup"><span data-stu-id="fb1fd-113">Using the upload Non-Office 365 feature as described in this procedure requires that you have:</span></span>
  
- <span data-ttu-id="fb1fd-114">Un Office 365 E3 con un componente aggiuntivo di conformità avanzato o un abbonamento E5.</span><span class="sxs-lookup"><span data-stu-id="fb1fd-114">An Office 365 E3 with Advanced Compliance add-on or E5 subscription.</span></span>
    
- <span data-ttu-id="fb1fd-115">Tutti i depositari il cui contenuto non Office 365 verrà caricato devono avere E3 con licenze di componenti aggiuntivi o E5 con Advanced Compliance.</span><span class="sxs-lookup"><span data-stu-id="fb1fd-115">All custodians whose non-Office 365 content will be uploaded must have E3 with Advanced Compliance add-on or E5 licenses.</span></span>
    
- <span data-ttu-id="fb1fd-116">Un caso di eDiscovery esistente.</span><span class="sxs-lookup"><span data-stu-id="fb1fd-116">An existing eDiscovery case.</span></span>
    
- <span data-ttu-id="fb1fd-117">Tutti i file per il caricamento raccolti in cartelle in cui è presente una cartella per ogni custode e il nome delle cartelle è in questo formato  *alias@domainname*  .</span><span class="sxs-lookup"><span data-stu-id="fb1fd-117">All the files for uploading gathered into folders where there is one folder per custodian and the folders' name is in this format  *alias@domainname*  .</span></span> <span data-ttu-id="fb1fd-118">I  *alias@domainname*  devono essere utenti di Office 365 alias e Domain.</span><span class="sxs-lookup"><span data-stu-id="fb1fd-118">The  *alias@domainname*  must be users Office 365 alias and domain.</span></span> <span data-ttu-id="fb1fd-119">È possibile raccogliere tutte le cartelle di  *alias@domainname*  in una cartella radice.</span><span class="sxs-lookup"><span data-stu-id="fb1fd-119">You can collect all the  *alias@domainname*  folders into a root folder.</span></span> <span data-ttu-id="fb1fd-120">La cartella radice può contenere solo le cartelle  *alias@domainname*  , non devono essere presenti file liberi nella cartella radice.</span><span class="sxs-lookup"><span data-stu-id="fb1fd-120">The root folder can only contain the  *alias@domainname*  folders, there must be no loose files in the root folder.</span></span>
    
- <span data-ttu-id="fb1fd-121">Un account che sia un amministratore di eDiscovery o eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="fb1fd-121">An account that is either an eDiscovery Manager or eDiscovery Administrator.</span></span>
    
- <span data-ttu-id="fb1fd-122">[Strumenti di archiviazione di Microsoft Azure](https://aka.ms/downloadazcopy) installati in un computer che ha accesso alla struttura di cartelle di contenuto non di Office 365.</span><span class="sxs-lookup"><span data-stu-id="fb1fd-122">[Microsoft Azure Storage Tools](https://aka.ms/downloadazcopy) installed on a computer that has access to the non-Office 365 content folder structure.</span></span> 
    
## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a><span data-ttu-id="fb1fd-123">Caricare il contenuto non Office 365 in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="fb1fd-123">Upload non-Office 365 content into Advanced eDiscovery</span></span>


1. <span data-ttu-id="fb1fd-124">In qualità di Manager di eDiscovery o amministratore di eDiscovery, aprire **eDiscovery**e aprire il caso in cui verranno caricati i dati non di Office 365.</span><span class="sxs-lookup"><span data-stu-id="fb1fd-124">As an eDiscovery Manager or eDiscovery Administrator, open **eDiscovery**, and open the case that the non-Office 365 data will be uploaded to.</span></span> <span data-ttu-id="fb1fd-125">Se è necessario creare un caso, vedere [gestire i casi di eDiscovery nel centro sicurezza e &amp; conformità](ediscovery-cases.md).</span><span class="sxs-lookup"><span data-stu-id="fb1fd-125">If you need to create a case, see [Manage eDiscovery cases in the Security &amp; Compliance Center](ediscovery-cases.md).</span></span>
    
2. <span data-ttu-id="fb1fd-126">Fare clic su **passa a eDiscovery avanzato**.</span><span class="sxs-lookup"><span data-stu-id="fb1fd-126">Click **Switch to Advanced eDiscovery**.</span></span>

3. <span data-ttu-id="fb1fd-127">Selezionare i **set di revisione** dal menu.</span><span class="sxs-lookup"><span data-stu-id="fb1fd-127">Select **Review Sets** from the menu.</span></span>

4. <span data-ttu-id="fb1fd-128">Selezionare un set di revisione esistente oppure scegliere **Aggiungi Revisione**.</span><span class="sxs-lookup"><span data-stu-id="fb1fd-128">Select an existing Review Set or choose **Add Review Set**.</span></span>

5. <span data-ttu-id="fb1fd-129">Selezionare **Manage Review set**.</span><span class="sxs-lookup"><span data-stu-id="fb1fd-129">Select **Manage review set**.</span></span>

6. <span data-ttu-id="fb1fd-130">Nella scheda dati non Office 365, selezionare **Visualizza caricamento**.</span><span class="sxs-lookup"><span data-stu-id="fb1fd-130">In the Non-Office 365 data card, select **View Uploads**.</span></span>

7. <span data-ttu-id="fb1fd-131">Scegliere **Carica file** per avviare la procedura guidata per il caricamento dei file.</span><span class="sxs-lookup"><span data-stu-id="fb1fd-131">Choose **Upload files** to start the file upload wizard.</span></span>

8. <span data-ttu-id="fb1fd-132">La prima scheda è **1. Prepara passaggio**.</span><span class="sxs-lookup"><span data-stu-id="fb1fd-132">The first tab is **1. Prepare step**.</span></span> <span data-ttu-id="fb1fd-133">Selezionare **Avanti: carica file**.</span><span class="sxs-lookup"><span data-stu-id="fb1fd-133">Select **Next: Upload files**.</span></span>

9. <span data-ttu-id="fb1fd-134">Sul **2. Scheda carica file** verrà richiesto di scaricare AzCopy.exe se non è già stato fatto e quindi di specificare il percorso del file.</span><span class="sxs-lookup"><span data-stu-id="fb1fd-134">On the **2. Upload files** tab you will be prompted to download AzCopy.exe if you have not done so already, and then to provide the path to the file location.</span></span> <span data-ttu-id="fb1fd-135">Ad esempio, `C:\Upload`  vi darà il comando per l'esecuzione di AzCopy.exe.</span><span class="sxs-lookup"><span data-stu-id="fb1fd-135">For example, `C:\Upload`  will give you the command to execute AzCopy.exe.</span></span> <span data-ttu-id="fb1fd-136">Usando `C:\Upload` , si vedrà:</span><span class="sxs-lookup"><span data-stu-id="fb1fd-136">Using `C:\Upload`, you will see:</span></span>

   `"%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy\AzCopy.exe" /Source:"c:\upload" /Dest:"https://spnam03salinkexternal003.blob.core.windows.net/16d13440-a6a4-4bc5-a82b-10ac9cfe9d7c-1601401811-externalstore?sv=2017-07-29&sr=c&si=ExternalStore63%7C0&sig=9Dq5v20TwkxByYDHhIEx%2FHSLlmlqUjY0njkJyTO0zGA%3D" /s`
  
10. <span data-ttu-id="fb1fd-137">Aprire una finestra del prompt dei comandi ed eseguire il comando AzCopy.exe per importare i dati in Azure.</span><span class="sxs-lookup"><span data-stu-id="fb1fd-137">Open a command prompt window and execute the AzCopy.exe command to import the data into Azure.</span></span> <span data-ttu-id="fb1fd-138">Dopo aver caricato tutti i dati, selezionare **Avanti: elabora file**.</span><span class="sxs-lookup"><span data-stu-id="fb1fd-138">Once it has loaded all of the data, select **Next: Process files**.</span></span>

11. <span data-ttu-id="fb1fd-139">La scheda successiva è **3. Elabora i file** in cui verranno visualizzati i depositari che dispongono di dati associati e mostrerà anche lo stato di avanzamento dei dati da importare.</span><span class="sxs-lookup"><span data-stu-id="fb1fd-139">The next tab is **3. Process files** where you will see the custodians that have data associated with them and will also show you the progress of the data being imported.</span></span>
        
    <span data-ttu-id="fb1fd-140">Per ulteriori informazioni sulla sintassi di Azcopy, vedere [Transfer Data with the Azcopy in Windows](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy).</span><span class="sxs-lookup"><span data-stu-id="fb1fd-140">For more information on Azcopy syntax, see [Transfer data with the AzCopy on Windows](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy).</span></span> 
    
    <span data-ttu-id="fb1fd-141">Per ulteriori informazioni sull'elaborazione avanzata di eDiscovery, vedere [Run the process Module and load data in Advanced eDiscovery (Classic)](run-the-process-module-and-load-data-in-advanced-ediscovery.md).</span><span class="sxs-lookup"><span data-stu-id="fb1fd-141">For more details on Advanced eDiscovery Processing, see [Run the Process module and load data in Advanced eDiscovery (classic)](run-the-process-module-and-load-data-in-advanced-ediscovery.md).</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="fb1fd-142">Deve essere presente una cartella radice per utente e il nome della cartella deve trovarsi nel formato <b>alias@domainname</b>  .</span><span class="sxs-lookup"><span data-stu-id="fb1fd-142">There must be one root folder per user and the folder name must be in the <b>alias@domainname</b>  format.</span></span> 
   
    > [!IMPORTANT]
    > <span data-ttu-id="fb1fd-143">Dopo che il contenitore è stato elaborato correttamente in Advanced eDiscovery, non sarà più possibile aggiungere nuovo contenuto allo spazio di archiviazione SAS in Azure.</span><span class="sxs-lookup"><span data-stu-id="fb1fd-143">Once the container is successfully processed in Advanced eDiscovery, you will no longer be able to add new content to the SAS storage in Azure.</span></span> <span data-ttu-id="fb1fd-144">Se si raccolgono contenuto aggiuntivo e si desidera aggiungerlo al caso per l'analisi avanzata di eDiscovery, è necessario creare un nuovo contenitore di **dati non Office 365** e ripetere questa procedura.</span><span class="sxs-lookup"><span data-stu-id="fb1fd-144">If you collect additional content and you want to add it to the case for Advanced eDiscovery analysis, you must create a new **Non-Office 365 data** container and repeat this procedure.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="fb1fd-145">Se il contenitore non  *elabora correttamente a causa di problemi di denominazione delle cartelle*  e quindi si corregge i problemi, sarà comunque necessario creare un nuovo contenitore e riconnetterlo e caricarlo nuovamente utilizzando le procedure illustrate in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="fb1fd-145">If the container  *does not process successfully due to folder naming issues*  and you then fix the issues, you will still have to create a new container and the reconnect and upload again using the procedures in this article.</span></span>
