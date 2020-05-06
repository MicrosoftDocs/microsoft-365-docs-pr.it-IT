---
title: Caricare dati non Microsoft 365 in un set di Revisione
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
description: Informazioni su come importare i dati non Microsoft 365 in un set di revisione per l'analisi in un caso di eDiscovery avanzato.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ed4a26ea1dd68b9198cce67ce0f97580ed4b2a99
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034424"
---
# <a name="load-non-microsoft-365-data-into-a-review-set"></a><span data-ttu-id="4468f-103">Caricare dati non Microsoft 365 in un set di Revisione</span><span class="sxs-lookup"><span data-stu-id="4468f-103">Load non-Microsoft 365 data into a review set</span></span>

<span data-ttu-id="4468f-104">Non tutti i documenti che devono essere analizzati in Advanced eDiscovery si trovano in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4468f-104">Not all documents that you need to analyze in Advanced eDiscovery are located in Microsoft 365.</span></span> <span data-ttu-id="4468f-105">Con la caratteristica di importazione di dati non Microsoft 365 in Advanced eDiscovery, è possibile caricare i documenti che non sono presenti in Microsoft 365 in un set di revisione.</span><span class="sxs-lookup"><span data-stu-id="4468f-105">With the non-Microsoft 365 data import feature in Advanced eDiscovery, you can upload documents that aren't located in Microsoft 365 to a review set.</span></span> <span data-ttu-id="4468f-106">In questo articolo viene illustrato come portare i documenti non Microsoft 365 in Advanced eDiscovery per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="4468f-106">This article shows you how to bring your non-Microsoft 365 documents into Advanced eDiscovery for analysis.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="4468f-107">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="4468f-107">Before you begin</span></span>

<span data-ttu-id="4468f-108">Se si utilizza la funzionalità carica non Microsoft 365 descritta in questo articolo, è necessario disporre di quanto segue:</span><span class="sxs-lookup"><span data-stu-id="4468f-108">Using the upload non-Microsoft 365 feature described in this article requires that you have the following:</span></span>

- <span data-ttu-id="4468f-109">A tutti i depositari ai quali si desidera associare il contenuto non Microsoft 365 deve essere assegnata la licenza appropriata.</span><span class="sxs-lookup"><span data-stu-id="4468f-109">All custodians that you want to associate non-Microsoft 365 content to must be assigned the appropriate license.</span></span> <span data-ttu-id="4468f-110">Per ulteriori informazioni, vedere [Introduzione a Advanced eDiscovery](get-started-with-advanced-ediscovery.md#step-1-verify-and-assign-appropriate-licenses).</span><span class="sxs-lookup"><span data-stu-id="4468f-110">For more information, see [Get started with Advanced eDiscovery](get-started-with-advanced-ediscovery.md#step-1-verify-and-assign-appropriate-licenses).</span></span>

- <span data-ttu-id="4468f-111">Un caso avanzato di eDiscovery esistente.</span><span class="sxs-lookup"><span data-stu-id="4468f-111">An existing Advanced eDiscovery case.</span></span>

- <span data-ttu-id="4468f-112">I depositari devono essere aggiunti al caso prima di poter caricare e associare ai dati non Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4468f-112">Custodians must be added to the case before you can upload and associate the non-Microsoft 365 data to them.</span></span>

- <span data-ttu-id="4468f-113">I dati non Microsoft 365 devono essere un tipo di file supportato da Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="4468f-113">Non-Microsoft 365 data must be a file type that's supported by Advanced eDiscovery.</span></span> <span data-ttu-id="4468f-114">Per ulteriori informazioni, vedere [tipi di file supportati in Advanced eDiscovery](supported-filetypes-ediscovery20.md).</span><span class="sxs-lookup"><span data-stu-id="4468f-114">For more information, see [Supported file types in Advanced eDiscovery](supported-filetypes-ediscovery20.md).</span></span>

- <span data-ttu-id="4468f-115">Tutti i file caricati in un set di revisione devono trovarsi in cartelle, in cui ogni cartella è associata a un determinato custode.</span><span class="sxs-lookup"><span data-stu-id="4468f-115">All files that are uploaded to a review set must be located in folders, where each folder is associated with a specific custodian.</span></span> <span data-ttu-id="4468f-116">I nomi di queste cartelle devono utilizzare il formato di denominazione seguente: *alias@domainname*.</span><span class="sxs-lookup"><span data-stu-id="4468f-116">The names for these folders must use the following naming format: *alias@domainname*.</span></span> <span data-ttu-id="4468f-117">Il alias@domainname deve essere l'alias e il dominio Microsoft 365 dell'utente.</span><span class="sxs-lookup"><span data-stu-id="4468f-117">The alias@domainname must be the user's Microsoft 365 alias and domain.</span></span> <span data-ttu-id="4468f-118">È possibile raccogliere tutte le cartelle di alias@domainname in una cartella radice.</span><span class="sxs-lookup"><span data-stu-id="4468f-118">You can collect all the alias@domainname folders in a root folder.</span></span> <span data-ttu-id="4468f-119">La cartella radice può contenere solo le cartelle alias@domainname.</span><span class="sxs-lookup"><span data-stu-id="4468f-119">The root folder can only contain the alias@domainname folders.</span></span> <span data-ttu-id="4468f-120">I file allentati nella cartella radice non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="4468f-120">Loose files in the root folder aren't supported.</span></span>

   <span data-ttu-id="4468f-121">La struttura di cartelle per i dati non Microsoft 365 che si desidera caricare sarebbe simile all'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="4468f-121">The folder structure for the non-Microsoft 365 data that you want to upload would be similar to the following example:</span></span>

   - <span data-ttu-id="4468f-122">c:\nonO365\abraham.mcmahon@contoso.com</span><span class="sxs-lookup"><span data-stu-id="4468f-122">c:\nonO365\abraham.mcmahon@contoso.com</span></span>
   - <span data-ttu-id="4468f-123">c:\nonO365\jewell.gordon@contoso.com</span><span class="sxs-lookup"><span data-stu-id="4468f-123">c:\nonO365\jewell.gordon@contoso.com</span></span>
   - <span data-ttu-id="4468f-124">c:\nonO365\staci.gonzalez@contoso.com</span><span class="sxs-lookup"><span data-stu-id="4468f-124">c:\nonO365\staci.gonzalez@contoso.com</span></span>

   <span data-ttu-id="4468f-125">Dove abraham.mcmahon@contoso.com, jewell.gordon@contoso.com e staci.gonzalez@contoso.com sono gli indirizzi SMTP dei depositari nel caso.</span><span class="sxs-lookup"><span data-stu-id="4468f-125">Where abraham.mcmahon@contoso.com, jewell.gordon@contoso.com, and staci.gonzalez@contoso.com are the SMTP addresses of custodians in the case.</span></span>

   ![Struttura di cartelle di caricamento dei dati non Microsoft 365](../media/3f2dde84-294e-48ea-b44b-7437bd25284c.png)

- <span data-ttu-id="4468f-127">Un account assegnato al gruppo di ruoli eDiscovery Manager (e aggiunto come amministratore di eDiscovery).</span><span class="sxs-lookup"><span data-stu-id="4468f-127">An account that is assigned to the eDiscovery Manager role group (and added as eDiscovery Administrator).</span></span>

- <span data-ttu-id="4468f-128">Lo strumento AzCopy v 8.1 è installato in un computer che ha accesso alla struttura di cartelle di contenuto non Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4468f-128">The AzCopy v8.1 tool installed on a computer that has access to the non-Microsoft 365 content folder structure.</span></span> <span data-ttu-id="4468f-129">Per installare AzCopy, vedere [Transfer Data with the AzCopy v 8.1 in Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span><span class="sxs-lookup"><span data-stu-id="4468f-129">To install AzCopy, see [Transfer data with the AzCopy v8.1 on Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span></span> <span data-ttu-id="4468f-130">Assicurarsi di installare AzCopy nel percorso predefinito, che è **% ProgramFiles (x86)% \ Microsoft SDKs\Azure\AzCopy**.</span><span class="sxs-lookup"><span data-stu-id="4468f-130">Be sure to install AzCopy in the default location, which is **%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy**.</span></span> <span data-ttu-id="4468f-131">È necessario utilizzare AzCopy v 8.1.</span><span class="sxs-lookup"><span data-stu-id="4468f-131">You must use AzCopy v8.1.</span></span> <span data-ttu-id="4468f-132">Le altre versioni di AzCopy potrebbero non funzionare quando si caricano dati non Microsoft 365 in Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="4468f-132">Other versions of AzCopy may not work when loading non-Microsoft 365 data in Advanced eDiscovery.</span></span>


## <a name="upload-non-microsoft-365-content-into-advanced-ediscovery"></a><span data-ttu-id="4468f-133">Caricare contenuto non Microsoft 365 in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="4468f-133">Upload non-Microsoft 365 content into Advanced eDiscovery</span></span>

1. <span data-ttu-id="4468f-134">In qualità di Manager di eDiscovery o amministratore di eDiscovery, aprire Advanced eDiscovery e passare al caso in cui verranno caricati i dati non Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4468f-134">As an eDiscovery Manager or eDiscovery Administrator, open Advanced eDiscovery, and go to the case that the non-Microsoft 365 data will be uploaded to.</span></span>  

2. <span data-ttu-id="4468f-135">Fare clic su **Revisione set**e quindi selezionare il set di revisione in cui caricare i dati non Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4468f-135">Click **Review sets**, and then select the review set to upload the non-Microsoft 365 data to.</span></span>  <span data-ttu-id="4468f-136">Se non si dispone di un set di recensioni, è possibile crearne uno.</span><span class="sxs-lookup"><span data-stu-id="4468f-136">If you don't have a review set, you can create one.</span></span> 
 
3. <span data-ttu-id="4468f-137">Nel set di verifica fare clic su **Gestisci Revisione set**e quindi su **Visualizza caricamenti** nel riquadro **dati non Microsoft 365** .</span><span class="sxs-lookup"><span data-stu-id="4468f-137">In the review set, click **Manage review set**, and then click **View uploads** on the **Non-Microsoft 365 data** tile.</span></span>

4. <span data-ttu-id="4468f-138">Fare clic su **Carica file** per avviare l'importazione guidata dati.</span><span class="sxs-lookup"><span data-stu-id="4468f-138">Click **Upload files** to start the data import wizard.</span></span>

   ![Caricare file](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

   <span data-ttu-id="4468f-140">Il primo passaggio della procedura guidata consente di preparare una posizione di archiviazione di Azure protetta fornita da Microsoft per il caricamento dei file.</span><span class="sxs-lookup"><span data-stu-id="4468f-140">The first step in the wizard prepares a secure Microsoft-provided Azure Storage location to upload the files to.</span></span>  <span data-ttu-id="4468f-141">Al termine della preparazione, il pulsante **Avanti: carica file** diventa attivo.</span><span class="sxs-lookup"><span data-stu-id="4468f-141">When the preparation is completed, the **Next: Upload files** button becomes active.</span></span>

   ![Importazione non Microsoft 365: preparazione](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
5. <span data-ttu-id="4468f-143">Fare clic su **Avanti: carica file**.</span><span class="sxs-lookup"><span data-stu-id="4468f-143">Click **Next: Upload files**.</span></span>

6. <span data-ttu-id="4468f-144">Nella pagina **Carica file** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4468f-144">On the **Upload files** page, do the following:</span></span>

   ![Importazione non Microsoft 365: caricamento di file](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

   <span data-ttu-id="4468f-146">a.</span><span class="sxs-lookup"><span data-stu-id="4468f-146">a.</span></span> <span data-ttu-id="4468f-147">Nella casella **percorso della posizione dei file** verificare o digitare il percorso della cartella principale in cui sono stati archiviati i dati non Microsoft 365 che si desidera caricare.</span><span class="sxs-lookup"><span data-stu-id="4468f-147">In the **Path to location of files** box, verify or type the location of the root folder where you've stored the non-Microsoft 365 data you want to upload.</span></span> <span data-ttu-id="4468f-148">Ad esempio, per il percorso dei file di esempio visualizzati nella **sezione prima di iniziare**, è necessario digitare **%USERPROFILE\Downloads\nonO365**.</span><span class="sxs-lookup"><span data-stu-id="4468f-148">For example, for the location of the example files shown in the **Before you begin section**, you would type **%USERPROFILE\Downloads\nonO365**.</span></span> <span data-ttu-id="4468f-149">Se si specifica la posizione corretta, il comando AzCopy visualizzato nella casella sotto il percorso viene aggiornato correttamente.</span><span class="sxs-lookup"><span data-stu-id="4468f-149">Providing the correct location ensures the AzCopy command displayed in box under the path is properly updated.</span></span>

   <span data-ttu-id="4468f-150">b.</span><span class="sxs-lookup"><span data-stu-id="4468f-150">b.</span></span> <span data-ttu-id="4468f-151">Fare clic su **copia negli Appunti** per copiare il comando visualizzato nella casella.</span><span class="sxs-lookup"><span data-stu-id="4468f-151">Click **Copy to clipboard** to copy the command that is displayed in the box.</span></span>

7. <span data-ttu-id="4468f-152">Avviare un prompt dei comandi di Windows, incollare il comando copiato nel passaggio precedente e quindi premere **invio** per avviare il comando AzCopy.</span><span class="sxs-lookup"><span data-stu-id="4468f-152">Start a Windows command prompt, paste the command that you copied in the previous step, and then press **Enter** to start the AzCopy command.</span></span>  <span data-ttu-id="4468f-153">Dopo aver avviato il comando, i file non Microsoft 365 verranno caricati nel percorso di archiviazione di Azure preparato nel passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="4468f-153">After you start the command, the non-Microsoft 365 files will be uploaded to the Azure Storage location that was prepared in step 4.</span></span>

   ![Importazione non Microsoft 365: AzCopy](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

   > [!NOTE]
   > <span data-ttu-id="4468f-155">Come indicato in precedenza, è necessario utilizzare AzCopy v 8.1 per utilizzare correttamente il comando fornito nella pagina **Carica file** .</span><span class="sxs-lookup"><span data-stu-id="4468f-155">As previously stated, you must use AzCopy v8.1 to successfully use the command that's provided on the **Upload files** page.</span></span> <span data-ttu-id="4468f-156">Se il comando AzCopy fornito ha esito negativo, vedere [risolvere i problemi relativi a AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).</span><span class="sxs-lookup"><span data-stu-id="4468f-156">If the supplied AzCopy command fails, please see [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).</span></span>

8. <span data-ttu-id="4468f-157">Tornare al centro sicurezza & conformità e fare clic su **Avanti: elabora file** nella procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="4468f-157">Go back to the Security & Compliance Center, and click **Next: Process files** in the wizard.</span></span>  <span data-ttu-id="4468f-158">In questo modo viene avviata l'elaborazione, l'estrazione del testo e l'indicizzazione dei file non Microsoft 365 caricati nel percorso di archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="4468f-158">This initiates processing, text extraction, and indexing of the non-Microsoft 365 files that were uploaded to the Azure Storage location.</span></span>  

9. <span data-ttu-id="4468f-159">Controllare lo stato di avanzamento dell'elaborazione dei file nella pagina dei **file di processo** o nella scheda **processi** visualizzando un processo denominato **aggiunta di dati non Microsoft 365 a un set di revisione**.</span><span class="sxs-lookup"><span data-stu-id="4468f-159">Track the progress of processing the files on the **Process files** page or on the **Jobs** tab by viewing a job named **Adding non-Microsoft 365 data to a review set**.</span></span>  <span data-ttu-id="4468f-160">Al termine del processo, i nuovi file saranno disponibili nel set di revisione.</span><span class="sxs-lookup"><span data-stu-id="4468f-160">After the job is finished, the new files will be available in the review set.</span></span>

   ![Importazione non Microsoft 365: elaborare i file](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

10. <span data-ttu-id="4468f-162">Al termine dell'elaborazione, è possibile chiudere la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="4468f-162">After the processing is finished, you can close the wizard.</span></span>
