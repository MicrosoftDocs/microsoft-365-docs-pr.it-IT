---
title: Caricare dati non Office 365 in un insieme da rivedere
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
description: Importare i dati non di Office 365 in un set di revisione in un caso di eDiscovery avanzato.
ms.openlocfilehash: ae5effafd8a208d3c03ce40e03c9da2b0ea6b8d1
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42072209"
---
# <a name="load-non-office-365-data-into-a-review-set"></a><span data-ttu-id="9a087-103">Caricare dati non Office 365 in un insieme da rivedere</span><span class="sxs-lookup"><span data-stu-id="9a087-103">Load non-Office 365 data into a review set</span></span>

<span data-ttu-id="9a087-104">Non tutti i documenti che devono essere analizzati in Advanced eDiscovery sono disponibili in Office 365.</span><span class="sxs-lookup"><span data-stu-id="9a087-104">Not all documents that you need to analyze in Advanced eDiscovery are located in Office 365.</span></span> <span data-ttu-id="9a087-105">Con la caratteristica di importazione di dati non di Office 365 in Advanced eDiscovery, è possibile caricare documenti che non sono presenti in Office 365 in un set di revisione.</span><span class="sxs-lookup"><span data-stu-id="9a087-105">With the non-Office 365 data import feature in Advanced eDiscovery, you can upload documents that aren't located in Office 365 to a review set.</span></span> <span data-ttu-id="9a087-106">In questo articolo viene illustrato come portare i documenti non Office 365 in Advanced eDiscovery per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="9a087-106">This article shows you how to bring your non-Office 365 documents into Advanced eDiscovery for analysis.</span></span>

>[!Note]
><span data-ttu-id="9a087-107">Advanced eDiscovery richiede un abbonamento a Microsoft 365 o Office 365 E5 per l'organizzazione o un abbonamento E3 con l'abbonamento al componente aggiuntivo per la conformità avanzato.</span><span class="sxs-lookup"><span data-stu-id="9a087-107">Advanced eDiscovery requires an Microsoft 365 or Office 365 E5 subscription for your organization or an E3 subscription with the Advanced Compliance add-on subscription.</span></span> <span data-ttu-id="9a087-108">Se non si dispone di tale piano e si desidera provare Advanced eDiscovery, è possibile iscriversi per una versione di valutazione di Office 365 Enterprise E5.</span><span class="sxs-lookup"><span data-stu-id="9a087-108">If you don't have that plan and want to try Advanced eDiscovery, you can sign up for a trial of Office 365 Enterprise E5.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="9a087-109">Informazioni preliminari</span><span class="sxs-lookup"><span data-stu-id="9a087-109">Before you begin</span></span>

<span data-ttu-id="9a087-110">Se si utilizza la funzionalità carica non Office 365 descritta in questo articolo, è necessario disporre di quanto segue:</span><span class="sxs-lookup"><span data-stu-id="9a087-110">Using the upload non-Office 365 feature described in this article requires that you have the following:</span></span>

- <span data-ttu-id="9a087-111">A tutti i depositari ai quali si desidera associare il contenuto non di Office 365 deve essere assegnata una licenza E5 o una licenza E3 con una licenza per il componente aggiuntivo per la conformità avanzata.</span><span class="sxs-lookup"><span data-stu-id="9a087-111">All custodians that you want to associate non-Office 365 content to must be assigned an E5 license, or an E3 license with an Advanced Compliance add-on license.</span></span>

- <span data-ttu-id="9a087-112">Un caso avanzato di eDiscovery esistente.</span><span class="sxs-lookup"><span data-stu-id="9a087-112">An existing Advanced eDiscovery case.</span></span>

- <span data-ttu-id="9a087-113">I depositari devono essere aggiunti al caso prima di poter caricare e associare ai dati non di Office 365.</span><span class="sxs-lookup"><span data-stu-id="9a087-113">Custodians must be added to the case before you can upload and associate the non-Office 365 data to them.</span></span>

- <span data-ttu-id="9a087-114">I dati non di Office 365 devono essere un tipo di file supportato da Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="9a087-114">Non-Office 365 data must be a file type that's supported by Advanced eDiscovery.</span></span> <span data-ttu-id="9a087-115">Per ulteriori informazioni, vedere [tipi di file supportati in Advanced eDiscovery](supported-filetypes-ediscovery20.md).</span><span class="sxs-lookup"><span data-stu-id="9a087-115">For more information, see [Supported file types in Advanced eDiscovery](supported-filetypes-ediscovery20.md).</span></span>

- <span data-ttu-id="9a087-116">Tutti i file caricati in un set di revisione devono trovarsi in cartelle, in cui ogni cartella è associata a un determinato custode.</span><span class="sxs-lookup"><span data-stu-id="9a087-116">All files that are uploaded to a review set must be located in folders, where each folder is associated with a specific custodian.</span></span> <span data-ttu-id="9a087-117">I nomi di queste cartelle devono utilizzare il formato di denominazione seguente: *alias@domainname*.</span><span class="sxs-lookup"><span data-stu-id="9a087-117">The names for these folders must use the following naming format: *alias@domainname*.</span></span> <span data-ttu-id="9a087-118">Il alias@domainname deve essere l'alias e il dominio dell'utente di Office 365.</span><span class="sxs-lookup"><span data-stu-id="9a087-118">The alias@domainname must be the user's Office 365 alias and domain.</span></span> <span data-ttu-id="9a087-119">È possibile raccogliere tutte le cartelle di alias@domainname in una cartella radice.</span><span class="sxs-lookup"><span data-stu-id="9a087-119">You can collect all the alias@domainname folders in a root folder.</span></span> <span data-ttu-id="9a087-120">La cartella radice può contenere solo le cartelle alias@domainname.</span><span class="sxs-lookup"><span data-stu-id="9a087-120">The root folder can only contain the alias@domainname folders.</span></span> <span data-ttu-id="9a087-121">I file allentati nella cartella radice non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="9a087-121">Loose files in the root folder aren't supported.</span></span>

   <span data-ttu-id="9a087-122">La struttura di cartelle per i dati non di Office 365 che si desidera caricare sarebbe simile all'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="9a087-122">The folder structure for the non-Office 365 data that you want to upload would be similar to the following example:</span></span>

   - <span data-ttu-id="9a087-123">c:\nonO365\abraham.mcmahon@contoso.com</span><span class="sxs-lookup"><span data-stu-id="9a087-123">c:\nonO365\abraham.mcmahon@contoso.com</span></span>
   - <span data-ttu-id="9a087-124">c:\nonO365\jewell.gordon@contoso.com</span><span class="sxs-lookup"><span data-stu-id="9a087-124">c:\nonO365\jewell.gordon@contoso.com</span></span>
   - <span data-ttu-id="9a087-125">c:\nonO365\staci.gonzalez@contoso.com</span><span class="sxs-lookup"><span data-stu-id="9a087-125">c:\nonO365\staci.gonzalez@contoso.com</span></span>

   <span data-ttu-id="9a087-126">Dove abraham.mcmahon@contoso.com, jewell.gordon@contoso.com e staci.gonzalez@contoso.com sono gli indirizzi SMTP dei depositari nel caso.</span><span class="sxs-lookup"><span data-stu-id="9a087-126">Where abraham.mcmahon@contoso.com, jewell.gordon@contoso.com, and staci.gonzalez@contoso.com are the SMTP addresses of custodians in the case.</span></span>

   ![Struttura di cartelle di caricamento dei dati non Office 365](../media/3f2dde84-294e-48ea-b44b-7437bd25284c.png)

- <span data-ttu-id="9a087-128">Un account assegnato al gruppo di ruoli eDiscovery Manager (e aggiunto come amministratore di eDiscovery).</span><span class="sxs-lookup"><span data-stu-id="9a087-128">An account that is assigned to the eDiscovery Manager role group (and added as eDiscovery Administrator).</span></span>

- <span data-ttu-id="9a087-129">Lo strumento AzCopy v 8.1 è installato in un computer che ha accesso alla struttura di cartelle di contenuto non di Office 365.</span><span class="sxs-lookup"><span data-stu-id="9a087-129">The AzCopy v8.1 tool installed on a computer that has access to the non-Office 365 content folder structure.</span></span> <span data-ttu-id="9a087-130">Per installare AzCopy, vedere [Transfer Data with the AzCopy v 8.1 in Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span><span class="sxs-lookup"><span data-stu-id="9a087-130">To install AzCopy, see [Transfer data with the AzCopy v8.1 on Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span></span> <span data-ttu-id="9a087-131">Assicurarsi di installare AzCopy nel percorso predefinito, che è **% ProgramFiles (x86)% \ Microsoft SDKs\Azure\AzCopy**.</span><span class="sxs-lookup"><span data-stu-id="9a087-131">Be sure to install AzCopy in the default location, which is **%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy**.</span></span> <span data-ttu-id="9a087-132">È necessario utilizzare AzCopy v 8.1.</span><span class="sxs-lookup"><span data-stu-id="9a087-132">You must use AzCopy v8.1.</span></span> <span data-ttu-id="9a087-133">Le altre versioni di AzCopy potrebbero non funzionare quando si caricano dati non di Office 365 in Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="9a087-133">Other versions of AzCopy may not work when loading non-Office 365 data in Advanced eDiscovery.</span></span>


## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a><span data-ttu-id="9a087-134">Caricare il contenuto non Office 365 in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="9a087-134">Upload non-Office 365 content into Advanced eDiscovery</span></span>

1. <span data-ttu-id="9a087-135">Come eDiscovery Manager o amministratore di eDiscovery, aprire Advanced eDiscovery, quindi il caso in cui i dati non di Office 365 verranno caricati.</span><span class="sxs-lookup"><span data-stu-id="9a087-135">As an eDiscovery Manager or eDiscovery Administrator, open Advanced eDiscovery, then the case that the non-Office 365 data will be uploaded to.</span></span>  

2. <span data-ttu-id="9a087-136">Fare clic su **Revisione set**e quindi selezionare il set di revisione in cui caricare i dati non di Office 365.</span><span class="sxs-lookup"><span data-stu-id="9a087-136">Click **Review sets**, and then select the review set to upload the non-Office 365 data to.</span></span>  <span data-ttu-id="9a087-137">Se non si dispone di un set di recensioni, è possibile crearne uno.</span><span class="sxs-lookup"><span data-stu-id="9a087-137">If you don't have a review set, you can create one.</span></span> 
 
3. <span data-ttu-id="9a087-138">Nel set di verifica fare clic su **Gestisci Revisione set**e quindi su **Visualizza caricamenti** nel riquadro **dati non di Office 365** .</span><span class="sxs-lookup"><span data-stu-id="9a087-138">In the review set, click **Manage review set**, and then click **View uploads** on the **Non-Office 365 data** tile.</span></span>

4. <span data-ttu-id="9a087-139">Fare clic su **Carica file** per avviare l'importazione guidata dati non di Office 365.</span><span class="sxs-lookup"><span data-stu-id="9a087-139">Click **Upload files** to start the Non-Office 365 data import wizard.</span></span>

   ![Caricare file](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

   <span data-ttu-id="9a087-141">Il primo passaggio della procedura guidata consente di preparare una posizione di archiviazione di Azure protetta fornita da Microsoft per il caricamento dei file.</span><span class="sxs-lookup"><span data-stu-id="9a087-141">The first step in the wizard prepares a secure Microsoft-provided Azure Storage location to upload the files to.</span></span>  <span data-ttu-id="9a087-142">Al termine della preparazione, il pulsante **Avanti: carica file** diventa attivo.</span><span class="sxs-lookup"><span data-stu-id="9a087-142">When the preparation is completed, the **Next: Upload files** button becomes active.</span></span>

   ![Importazione non Office 365: preparazione](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
5. <span data-ttu-id="9a087-144">Fare clic su **Avanti: carica file**.</span><span class="sxs-lookup"><span data-stu-id="9a087-144">Click **Next: Upload files**.</span></span>

6. <span data-ttu-id="9a087-145">Nella pagina **Carica file** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9a087-145">On the **Upload files** page, do the following:</span></span>

   ![Importazione non Office 365: caricamento di file](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

   <span data-ttu-id="9a087-147">a.</span><span class="sxs-lookup"><span data-stu-id="9a087-147">a.</span></span> <span data-ttu-id="9a087-148">Nella casella **percorso della posizione dei file** verificare o digitare il percorso della cartella principale in cui sono stati archiviati i dati non di Office 365 che si desidera caricare.</span><span class="sxs-lookup"><span data-stu-id="9a087-148">In the **Path to location of files** box, verify or type the location of the root folder where you've stored the non-Office 365 data you want to upload.</span></span> <span data-ttu-id="9a087-149">Ad esempio, per il percorso dei file di esempio visualizzati nella **sezione prima di iniziare**, è necessario digitare **%USERPROFILE\Downloads\nonO365**.</span><span class="sxs-lookup"><span data-stu-id="9a087-149">For example, for the location of the example files shown in the **Before you begin section**, you would type **%USERPROFILE\Downloads\nonO365**.</span></span> <span data-ttu-id="9a087-150">Se si specifica la posizione corretta, il comando AzCopy visualizzato nella casella sotto il percorso viene aggiornato correttamente.</span><span class="sxs-lookup"><span data-stu-id="9a087-150">Providing the correct location ensures the AzCopy command displayed in box under the path is properly updated.</span></span>

   <span data-ttu-id="9a087-151">b.</span><span class="sxs-lookup"><span data-stu-id="9a087-151">b.</span></span> <span data-ttu-id="9a087-152">Fare clic su **copia negli Appunti** per copiare il comando visualizzato nella casella.</span><span class="sxs-lookup"><span data-stu-id="9a087-152">Click **Copy to clipboard** to copy the command that is displayed in the box.</span></span>

7. <span data-ttu-id="9a087-153">Avviare un prompt dei comandi di Windows, incollare il comando copiato nel passaggio precedente e quindi premere **invio** per avviare il comando AzCopy.</span><span class="sxs-lookup"><span data-stu-id="9a087-153">Start a Windows command prompt, paste the command that you copied in the previous step, and then press **Enter** to start the AzCopy command.</span></span>  <span data-ttu-id="9a087-154">Dopo aver avviato il comando, i file non di Office 365 verranno caricati nel percorso di archiviazione di Azure preparato nel passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="9a087-154">After you start the command, the non-Office 365 files will be uploaded to the Azure Storage location that was prepared in step 4.</span></span>

   ![Importazione non Office 365: AzCopy](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

   > [!NOTE]
   > <span data-ttu-id="9a087-156">Come indicato in precedenza, è necessario utilizzare AzCopy v 8.1 per utilizzare correttamente il comando fornito nella pagina **Carica file** .</span><span class="sxs-lookup"><span data-stu-id="9a087-156">As previously stated, you must use AzCopy v8.1 to successfully use the command that's provided on the **Upload files** page.</span></span> <span data-ttu-id="9a087-157">Se il comando AzCopy fornito ha esito negativo, vedere [risolvere i problemi relativi a AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).</span><span class="sxs-lookup"><span data-stu-id="9a087-157">If the supplied AzCopy command fails, please see [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).</span></span>

8. <span data-ttu-id="9a087-158">Tornare al centro sicurezza & conformità e fare clic su **Avanti: elabora file** nella procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="9a087-158">Go back to the Security & Compliance Center, and click **Next: Process files** in the wizard.</span></span>  <span data-ttu-id="9a087-159">In questo modo viene avviata l'elaborazione, l'estrazione del testo e l'indicizzazione dei file non di Office 365 caricati nel percorso di archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="9a087-159">This initiates processing, text extraction, and indexing of the non-Office 365 files that were uploaded to the Azure Storage location.</span></span>  

9. <span data-ttu-id="9a087-160">Controllare lo stato di avanzamento dell'elaborazione dei file non di Office 365 nella pagina dei **file di processo** o nella scheda **processi** visualizzando un processo denominato **aggiunta di dati non di Office 365 a un set di revisione**.</span><span class="sxs-lookup"><span data-stu-id="9a087-160">Track the progress of processing the non-Office 365 files on the **Process files** page or on the **Jobs** tab by viewing a job named **Adding non-Office 365 data to a review set**.</span></span>  <span data-ttu-id="9a087-161">Al termine del processo, i nuovi file saranno disponibili nel set di revisione.</span><span class="sxs-lookup"><span data-stu-id="9a087-161">After the job is finished, the new files will be available in the review set.</span></span>

   ![Importazione non Office 365: elaborare i file](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

10. <span data-ttu-id="9a087-163">Al termine dell'elaborazione, è possibile chiudere la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="9a087-163">After the processing is finished, you can close the wizard.</span></span>
