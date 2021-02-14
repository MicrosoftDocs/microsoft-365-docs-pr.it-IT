---
title: Caricare dati non Di Microsoft 365 in un insieme da rivedere
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Informazioni su come importare dati non Di Microsoft 365 in un insieme da rivedere per l'analisi in un caso di Advanced eDiscovery.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ad70207bdc015107a5aba074e2df06a42c0618b3
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285862"
---
# <a name="load-non-microsoft-365-data-into-a-review-set"></a><span data-ttu-id="1ed94-103">Caricare dati non Di Microsoft 365 in un insieme da rivedere</span><span class="sxs-lookup"><span data-stu-id="1ed94-103">Load non-Microsoft 365 data into a review set</span></span>

<span data-ttu-id="1ed94-104">Non tutti i documenti che è necessario analizzare in Advanced eDiscovery si trovano in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1ed94-104">Not all documents that you need to analyze in Advanced eDiscovery are located in Microsoft 365.</span></span> <span data-ttu-id="1ed94-105">Con la funzionalità di importazione dei dati non Di Microsoft 365 in Advanced eDiscovery, è possibile caricare i documenti che non si trovano in Microsoft 365 in un insieme da rivedere.</span><span class="sxs-lookup"><span data-stu-id="1ed94-105">With the non-Microsoft 365 data import feature in Advanced eDiscovery, you can upload documents that aren't located in Microsoft 365 to a review set.</span></span> <span data-ttu-id="1ed94-106">Questo articolo illustra come portare i documenti non Microsoft 365 in Advanced eDiscovery per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="1ed94-106">This article shows you how to bring your non-Microsoft 365 documents into Advanced eDiscovery for analysis.</span></span>

## <a name="requirements-to-upload-non-office-365-content"></a><span data-ttu-id="1ed94-107">Requisiti per caricare contenuto non Office 365</span><span class="sxs-lookup"><span data-stu-id="1ed94-107">Requirements to upload non-Office 365 content</span></span>

<span data-ttu-id="1ed94-108">L'uso della funzionalità di caricamento non Microsoft 365 descritta in questo articolo richiede quanto segue:</span><span class="sxs-lookup"><span data-stu-id="1ed94-108">Using the upload non-Microsoft 365 feature described in this article requires that you have the following:</span></span>

- <span data-ttu-id="1ed94-109">A tutti i responsabile a cui si desidera associare contenuti non Di Microsoft 365 deve essere assegnata la licenza appropriata.</span><span class="sxs-lookup"><span data-stu-id="1ed94-109">All custodians that you want to associate non-Microsoft 365 content to must be assigned the appropriate license.</span></span> <span data-ttu-id="1ed94-110">Per ulteriori informazioni, vedere [Introduzione ad Advanced eDiscovery.](get-started-with-advanced-ediscovery.md#step-1-verify-and-assign-appropriate-licenses)</span><span class="sxs-lookup"><span data-stu-id="1ed94-110">For more information, see [Get started with Advanced eDiscovery](get-started-with-advanced-ediscovery.md#step-1-verify-and-assign-appropriate-licenses).</span></span>

- <span data-ttu-id="1ed94-111">Un caso di Advanced eDiscovery esistente.</span><span class="sxs-lookup"><span data-stu-id="1ed94-111">An existing Advanced eDiscovery case.</span></span>

- <span data-ttu-id="1ed94-112">I responsabile devono essere aggiunti al caso prima di poter caricare e associare i dati non Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1ed94-112">Custodians must be added to the case before you can upload and associate the non-Microsoft 365 data to them.</span></span>

- <span data-ttu-id="1ed94-113">I dati non Di Microsoft 365 devono essere un tipo di file supportato da Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="1ed94-113">Non-Microsoft 365 data must be a file type that's supported by Advanced eDiscovery.</span></span> <span data-ttu-id="1ed94-114">Per ulteriori informazioni, vedere [Tipi di file supportati in Advanced eDiscovery.](supported-filetypes-ediscovery20.md)</span><span class="sxs-lookup"><span data-stu-id="1ed94-114">For more information, see [Supported file types in Advanced eDiscovery](supported-filetypes-ediscovery20.md).</span></span>

- <span data-ttu-id="1ed94-115">Tutti i file caricati in un insieme da rivedere devono trovarsi in cartelle, in cui ogni cartella è associata a un responsabile specifico.</span><span class="sxs-lookup"><span data-stu-id="1ed94-115">All files that are uploaded to a review set must be located in folders, where each folder is associated with a specific custodian.</span></span> <span data-ttu-id="1ed94-116">I nomi di queste cartelle devono utilizzare il formato di denominazione seguente: *alias@domainname*.</span><span class="sxs-lookup"><span data-stu-id="1ed94-116">The names for these folders must use the following naming format: *alias@domainname*.</span></span> <span data-ttu-id="1ed94-117">Il alias@domainname deve essere l'alias e il dominio di Microsoft 365 dell'utente.</span><span class="sxs-lookup"><span data-stu-id="1ed94-117">The alias@domainname must be the user's Microsoft 365 alias and domain.</span></span> <span data-ttu-id="1ed94-118">È possibile raccogliere tutte le alias@domainname cartelle in una cartella radice.</span><span class="sxs-lookup"><span data-stu-id="1ed94-118">You can collect all the alias@domainname folders in a root folder.</span></span> <span data-ttu-id="1ed94-119">La cartella radice può contenere solo le alias@domainname esistenti.</span><span class="sxs-lookup"><span data-stu-id="1ed94-119">The root folder can only contain the alias@domainname folders.</span></span> <span data-ttu-id="1ed94-120">I file con estensione loose nella cartella radice non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="1ed94-120">Loose files in the root folder aren't supported.</span></span>

   <span data-ttu-id="1ed94-121">La struttura di cartelle per i dati non Di Microsoft 365 che si desidera caricare è simile all'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="1ed94-121">The folder structure for the non-Microsoft 365 data that you want to upload would be similar to the following example:</span></span>

   - <span data-ttu-id="1ed94-122">c:\nonO365\abraham.mcmahon@contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ed94-122">c:\nonO365\abraham.mcmahon@contoso.com</span></span>
   - <span data-ttu-id="1ed94-123">c:\nonO365\jewell.gordon@contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ed94-123">c:\nonO365\jewell.gordon@contoso.com</span></span>
   - <span data-ttu-id="1ed94-124">c:\nonO365\staci.gonzalez@contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ed94-124">c:\nonO365\staci.gonzalez@contoso.com</span></span>

   <span data-ttu-id="1ed94-125">Dove abraham.mcmahon@contoso.com, jewell.gordon@contoso.com e staci.gonzalez@contoso.com sono gli indirizzi SMTP dei responsabile nel caso.</span><span class="sxs-lookup"><span data-stu-id="1ed94-125">Where abraham.mcmahon@contoso.com, jewell.gordon@contoso.com, and staci.gonzalez@contoso.com are the SMTP addresses of custodians in the case.</span></span>

   ![Struttura della cartella di caricamento dei dati non di Microsoft 365](../media/3f2dde84-294e-48ea-b44b-7437bd25284c.png)

- <span data-ttu-id="1ed94-127">Un account assegnato al gruppo di ruoli Gestore di eDiscovery (e aggiunto come amministratore di eDiscovery).</span><span class="sxs-lookup"><span data-stu-id="1ed94-127">An account that is assigned to the eDiscovery Manager role group (and added as eDiscovery Administrator).</span></span>

- <span data-ttu-id="1ed94-128">Lo strumento AzCopy v8.1 è installato in un computer che ha accesso alla struttura di cartelle di contenuto non Di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1ed94-128">The AzCopy v8.1 tool installed on a computer that has access to the non-Microsoft 365 content folder structure.</span></span> <span data-ttu-id="1ed94-129">Per installare AzCopy, vedere [Trasferire dati con AzCopy v8.1 in Windows.](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy)</span><span class="sxs-lookup"><span data-stu-id="1ed94-129">To install AzCopy, see [Transfer data with the AzCopy v8.1 on Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span></span> <span data-ttu-id="1ed94-130">Assicurarsi di installare AzCopy nel percorso predefinito, ovvero **%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.**</span><span class="sxs-lookup"><span data-stu-id="1ed94-130">Be sure to install AzCopy in the default location, which is **%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy**.</span></span> <span data-ttu-id="1ed94-131">È necessario utilizzare AzCopy v8.1.</span><span class="sxs-lookup"><span data-stu-id="1ed94-131">You must use AzCopy v8.1.</span></span> <span data-ttu-id="1ed94-132">Altre versioni di AzCopy potrebbero non funzionare durante il caricamento di dati non Microsoft 365 in Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="1ed94-132">Other versions of AzCopy may not work when loading non-Microsoft 365 data in Advanced eDiscovery.</span></span>


## <a name="upload-non-microsoft-365-content-into-advanced-ediscovery"></a><span data-ttu-id="1ed94-133">Caricare contenuti non Microsoft 365 in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="1ed94-133">Upload non-Microsoft 365 content into Advanced eDiscovery</span></span>

1. <span data-ttu-id="1ed94-134">In quanto responsabile di eDiscovery o amministratore di eDiscovery, aprire Advanced eDiscovery e passare al caso in cui verranno caricati i dati non Di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1ed94-134">As an eDiscovery Manager or eDiscovery Administrator, open Advanced eDiscovery, and go to the case that the non-Microsoft 365 data will be uploaded to.</span></span>  

2. <span data-ttu-id="1ed94-135">Fare **clic su Review sets** e quindi selezionare il set di recensioni in cui caricare i dati non Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1ed94-135">Click **Review sets**, and then select the review set to upload the non-Microsoft 365 data to.</span></span>  <span data-ttu-id="1ed94-136">Se non hai un set di recensioni, puoi crearne uno.</span><span class="sxs-lookup"><span data-stu-id="1ed94-136">If you don't have a review set, you can create one.</span></span> 
 
3. <span data-ttu-id="1ed94-137">Nel set di recensioni, fare clic  su Gestisci **set** di recensioni e quindi su Visualizza caricamenti nel riquadro **dati non Microsoft 365.**</span><span class="sxs-lookup"><span data-stu-id="1ed94-137">In the review set, click **Manage review set**, and then click **View uploads** on the **Non-Microsoft 365 data** tile.</span></span>

4. <span data-ttu-id="1ed94-138">Fare **clic su Carica file** per avviare l'importazione guidata dei dati.</span><span class="sxs-lookup"><span data-stu-id="1ed94-138">Click **Upload files** to start the data import wizard.</span></span>

   ![Caricare file](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

   <span data-ttu-id="1ed94-140">Il primo passaggio della procedura guidata prepara un percorso sicuro di Archiviazione di Azure fornito da Microsoft in cui caricare i file.</span><span class="sxs-lookup"><span data-stu-id="1ed94-140">The first step in the wizard prepares a secure Microsoft-provided Azure Storage location to upload the files to.</span></span>  <span data-ttu-id="1ed94-141">Al termine della preparazione, il **pulsante Avanti: Carica** file diventa attivo.</span><span class="sxs-lookup"><span data-stu-id="1ed94-141">When the preparation is completed, the **Next: Upload files** button becomes active.</span></span>

   ![Importazione non Microsoft 365: preparare](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
5. <span data-ttu-id="1ed94-143">Fare **clic su Avanti: Carica file.**</span><span class="sxs-lookup"><span data-stu-id="1ed94-143">Click **Next: Upload files**.</span></span>

6. <span data-ttu-id="1ed94-144">Nella pagina **Carica file** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1ed94-144">On the **Upload files** page, do the following:</span></span>

   ![Importazione non Microsoft 365: caricare file](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

   <span data-ttu-id="1ed94-146">a.</span><span class="sxs-lookup"><span data-stu-id="1ed94-146">a.</span></span> <span data-ttu-id="1ed94-147">Nella casella **Percorso dei** file verificare o digitare il percorso della cartella radice in cui sono archiviati i dati non Di Microsoft 365 che si desidera caricare.</span><span class="sxs-lookup"><span data-stu-id="1ed94-147">In the **Path to location of files** box, verify or type the location of the root folder where you've stored the non-Microsoft 365 data you want to upload.</span></span> <span data-ttu-id="1ed94-148">Ad esempio, per il percorso dei file di esempio mostrati nella sezione Prima di **iniziare,** digitare **%USERPROFILE\Downloads\nonO365.**</span><span class="sxs-lookup"><span data-stu-id="1ed94-148">For example, for the location of the example files shown in the **Before you begin section**, you would type **%USERPROFILE\Downloads\nonO365**.</span></span> <span data-ttu-id="1ed94-149">Se si specifica il percorso corretto, il comando AzCopy visualizzato nella casella sotto il percorso verrà aggiornato correttamente.</span><span class="sxs-lookup"><span data-stu-id="1ed94-149">Providing the correct location ensures the AzCopy command displayed in box under the path is properly updated.</span></span>

   <span data-ttu-id="1ed94-150">b.</span><span class="sxs-lookup"><span data-stu-id="1ed94-150">b.</span></span> <span data-ttu-id="1ed94-151">Fare **clic su** Copia negli Appunti per copiare il comando visualizzato nella casella.</span><span class="sxs-lookup"><span data-stu-id="1ed94-151">Click **Copy to clipboard** to copy the command that is displayed in the box.</span></span>

7. <span data-ttu-id="1ed94-152">Avviare un prompt dei comandi di Windows, incollare il comando copiato nel passaggio precedente e quindi premere **INVIO** per avviare il comando AzCopy.</span><span class="sxs-lookup"><span data-stu-id="1ed94-152">Start a Windows command prompt, paste the command that you copied in the previous step, and then press **Enter** to start the AzCopy command.</span></span>  <span data-ttu-id="1ed94-153">Dopo aver avviato il comando, i file non Microsoft 365 verranno caricati nel percorso di archiviazione di Azure preparato nel passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="1ed94-153">After you start the command, the non-Microsoft 365 files will be uploaded to the Azure Storage location that was prepared in step 4.</span></span>

   ![Importazione non Microsoft 365: AzCopy](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

   > [!NOTE]
   > <span data-ttu-id="1ed94-155">Come indicato in precedenza, è necessario utilizzare AzCopy v8.1 per utilizzare correttamente il comando fornito nella pagina **Carica file.**</span><span class="sxs-lookup"><span data-stu-id="1ed94-155">As previously stated, you must use AzCopy v8.1 to successfully use the command that's provided on the **Upload files** page.</span></span> <span data-ttu-id="1ed94-156">Se il comando AzCopy fornito non riesce, vedere [Risoluzione dei problemi di AzCopy in Advanced eDiscovery.](troubleshooting-azcopy.md)</span><span class="sxs-lookup"><span data-stu-id="1ed94-156">If the supplied AzCopy command fails, please see [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).</span></span>

8. <span data-ttu-id="1ed94-157">Tornare al Centro sicurezza & conformità e fare clic su **Avanti: Elaborare i file** nella procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="1ed94-157">Go back to the Security & Compliance Center, and click **Next: Process files** in the wizard.</span></span>  <span data-ttu-id="1ed94-158">In questo modo viene avviata l'elaborazione, l'estrazione del testo e l'indicizzazione dei file non Microsoft 365 caricati nel percorso di archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="1ed94-158">This initiates processing, text extraction, and indexing of the non-Microsoft 365 files that were uploaded to the Azure Storage location.</span></span>  

9. <span data-ttu-id="1ed94-159">Tenere traccia dello stato di  avanzamento dell'elaborazione  dei file nella pagina Elabora file o nella scheda Processi visualizzando un processo denominato Aggiunta di dati **non Di Microsoft 365 a** un insieme da rivedere.</span><span class="sxs-lookup"><span data-stu-id="1ed94-159">Track the progress of processing the files on the **Process files** page or on the **Jobs** tab by viewing a job named **Adding non-Microsoft 365 data to a review set**.</span></span>  <span data-ttu-id="1ed94-160">Al termine del processo, i nuovi file saranno disponibili nell'insieme da rivedere.</span><span class="sxs-lookup"><span data-stu-id="1ed94-160">After the job is finished, the new files will be available in the review set.</span></span>

   ![Importazione non Microsoft 365: elaborare i file](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

10. <span data-ttu-id="1ed94-162">Al termine dell'elaborazione, è possibile chiudere la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="1ed94-162">After the processing is finished, you can close the wizard.</span></span>
