---
title: Correzione degli errori dei singoli elementi
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
description: È possibile correggere un errore di elaborazione in un documento in un set di revisione in Advanced eDiscovery senza dover seguire il processo di correzione degli errori in blocco.
ms.openlocfilehash: 3c50f9dcd1448ee36edd0e82e5b2c2879c11d6b5
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42069677"
---
# <a name="single-item-error-remediation"></a><span data-ttu-id="ae5b7-103">Correzione degli errori dei singoli elementi</span><span class="sxs-lookup"><span data-stu-id="ae5b7-103">Single item error remediation</span></span>

<span data-ttu-id="ae5b7-104">La correzione degli errori garantisce agli utenti avanzati di eDiscovery la possibilità di correggere i problemi relativi ai dati che impediscono l'elaborazione corretta del contenuto da parte di Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="ae5b7-104">Error remediation gives Advanced eDiscovery users the ability to rectify data issues that prevent Advanced eDiscovery from properly processing the content.</span></span> <span data-ttu-id="ae5b7-105">Ad esempio, i file protetti da password non possono essere elaborati perché tali file sono bloccati o crittografati.</span><span class="sxs-lookup"><span data-stu-id="ae5b7-105">For example, files that are password protected can't be processed because those files are locked or encrypted.</span></span> <span data-ttu-id="ae5b7-106">In precedenza, è possibile correggere solo gli errori in blocco utilizzando [questo flusso di lavoro](error-remediation-when-processing-data-in-advanced-ediscovery.md).</span><span class="sxs-lookup"><span data-stu-id="ae5b7-106">Previously, you could only remediate errors in bulk by using [this workflow](error-remediation-when-processing-data-in-advanced-ediscovery.md).</span></span> <span data-ttu-id="ae5b7-107">Tuttavia, a volte, non ha senso correggere gli errori in più file quando non si è sicuri se uno qualsiasi di questi file risponde al caso in cui si sta indagando.</span><span class="sxs-lookup"><span data-stu-id="ae5b7-107">But sometimes, it doesn't make sense to remediate errors in multiple files when you’re unsure if any of those files are responsive to the case you’re investigating.</span></span> <span data-ttu-id="ae5b7-108">Potrebbe anche non essere opportuno correggere gli errori prima di aver avuto la possibilità di esaminare i metadati dei file (come il percorso del file o chi aveva accesso) per aiutarti a prendere decisioni in anticipo sulla reattività.</span><span class="sxs-lookup"><span data-stu-id="ae5b7-108">It also might not make sense to remediate errors before you’ve had a chance to review the file metadata (such as file location or who had access) to help you make up-front decisions about responsiveness.</span></span> <span data-ttu-id="ae5b7-109">Una nuova funzionalità denominata correzione degli errori di un *singolo elemento* fornisce ai responsabili di eDiscovery la possibilità di visualizzare i metadati dei file con un errore di elaborazione e, se necessario, correggere l'errore direttamente nel set di revisione.</span><span class="sxs-lookup"><span data-stu-id="ae5b7-109">A new feature called *single item error remediation* gives eDiscovery managers the ability to view the metadata of files with a processing error and if necessary remediate the error directly in the review set.</span></span> <span data-ttu-id="ae5b7-110">In questo articolo viene illustrato come identificare, ignorare e correggere i file con errori di elaborazione in un set di revisione.</span><span class="sxs-lookup"><span data-stu-id="ae5b7-110">The article discusses how to identify, ignore, and remediate files with processing errors in a review set.</span></span>

## <a name="identify-documents-with-errors"></a><span data-ttu-id="ae5b7-111">Identificare i documenti con errori</span><span class="sxs-lookup"><span data-stu-id="ae5b7-111">Identify documents with errors</span></span>

<span data-ttu-id="ae5b7-112">I documenti con errori di elaborazione in un set di revisione sono ora identificati (con un banner).</span><span class="sxs-lookup"><span data-stu-id="ae5b7-112">Documents with processing errors in a review set are now identified (with a banner).</span></span> <span data-ttu-id="ae5b7-113">È possibile correggere o ignorare l'errore.</span><span class="sxs-lookup"><span data-stu-id="ae5b7-113">You can remediate or ignore the error.</span></span> <span data-ttu-id="ae5b7-114">Nella schermata seguente viene mostrato il banner di errore di elaborazione per un documento di Word in un set di revisione che è protetto da password.</span><span class="sxs-lookup"><span data-stu-id="ae5b7-114">The following screenshot shows the processing error banner for a Word document in a review set that is password-protected.</span></span> <span data-ttu-id="ae5b7-115">Si noti inoltre che è possibile visualizzare i metadati dei file di documenti con errori di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="ae5b7-115">Also notice that you can view the file metadata of documents with processing errors.</span></span>

![Banner visualizzato per il documento con errore di elaborazione](../media/SIERimage1.png)

<span data-ttu-id="ae5b7-117">È inoltre possibile cercare i documenti che presentano errori di elaborazione utilizzando la condizione di **elaborazione dello stato** durante [l'esecuzione di query sui documenti in un set di revisione](review-set-search.md).</span><span class="sxs-lookup"><span data-stu-id="ae5b7-117">You can also search for documents that have processing errors by using the **Processing status** condition when [querying the documents in a review set](review-set-search.md).</span></span>

![Utilizzare la condizione di elaborazione dello stato per cercare i documenti di errore](../media/SIERimage2.png)

### <a name="ignore-errors"></a><span data-ttu-id="ae5b7-119">Ignorare gli errori</span><span class="sxs-lookup"><span data-stu-id="ae5b7-119">Ignore errors</span></span>

<span data-ttu-id="ae5b7-120">È possibile ignorare un errore di elaborazione facendo clic su **Ignora** nel banner di errore di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="ae5b7-120">You can ignore a processing error by clicking **Ignore** in the processing error banner.</span></span> <span data-ttu-id="ae5b7-121">Quando si ignora un errore, il documento viene rimosso dal flusso di lavoro per la [correzione degli errori di massa](error-remediation-when-processing-data-in-advanced-ediscovery.md).</span><span class="sxs-lookup"><span data-stu-id="ae5b7-121">When you ignore an error, the document is removed from the [bulk error remediation workflow](error-remediation-when-processing-data-in-advanced-ediscovery.md).</span></span> <span data-ttu-id="ae5b7-122">Dopo aver ignorato un errore, il banner del documento cambia colore e indica che l'errore di elaborazione è stato ignorato.</span><span class="sxs-lookup"><span data-stu-id="ae5b7-122">After an error is ignored, the document banner changes color and indicates that the processing error was ignored.</span></span> <span data-ttu-id="ae5b7-123">In qualsiasi momento, è possibile annullare la decisione di ignorare l'errore facendo clic su **Ripristina**.</span><span class="sxs-lookup"><span data-stu-id="ae5b7-123">At any time, you can revert the decision to ignore the error by clicking **Revert**.</span></span>

![Fare clic su Ignora per ignorare l'errore di elaborazione](../media/SIERimage3.png)

<span data-ttu-id="ae5b7-125">È inoltre possibile cercare tutti i documenti in cui si è verificato un errore di elaborazione ignorato utilizzando la condizione relativa agli *errori di elaborazione ignorati* durante l'esecuzione di query sui documenti in un set di revisione.</span><span class="sxs-lookup"><span data-stu-id="ae5b7-125">You can also search for all documents that had a processing error that was ignored by using the *Ignored processing errors* condition when querying documents in a review set.</span></span>

![Utilizzare la condizione relativa agli errori di elaborazione ignorati per cercare i documenti di errore ignorati](../media/SIERimage4.png)

## <a name="remediate-a-document-with-errors"></a><span data-ttu-id="ae5b7-127">Correggere gli errori di un documento</span><span class="sxs-lookup"><span data-stu-id="ae5b7-127">Remediate a document with errors</span></span>

<span data-ttu-id="ae5b7-128">A volte potrebbe essere necessario correggere un errore di elaborazione nei documenti (tramite la rimozione di una password, la decrittografia di un file crittografato o il ripristino di un documento danneggiato) e quindi aggiungere il documento correttivo al set di revisione.</span><span class="sxs-lookup"><span data-stu-id="ae5b7-128">Sometimes you may be required to remediate a processing error in documents (by removing a password, decrypting an encrypted file, or recovering a corrupted document) and then add the remediated document to the review set.</span></span> <span data-ttu-id="ae5b7-129">In questo modo è possibile esaminare ed esportare il documento di errore insieme agli altri documenti nel set di revisione.</span><span class="sxs-lookup"><span data-stu-id="ae5b7-129">This allows you to review and export the error document together with the other documents in the review set.</span></span> 

<span data-ttu-id="ae5b7-130">Per correggere un singolo documento, attenersi alla procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="ae5b7-130">To remediate a single document, follow these steps:</span></span>

1. <span data-ttu-id="ae5b7-131"> > Fare **clic su download downloa\d\*\*\**originale** per scaricare una copia del file in un computer locale.</span><span class="sxs-lookup"><span data-stu-id="ae5b7-131">Click **Download** > **Download original** to download a copy of the file to a local computer.</span></span>

   ![Scaricare il documento con l'errore di elaborazione](../media/SIERimage5.png)

2. <span data-ttu-id="ae5b7-133">Correggere l'errore nel file offline.</span><span class="sxs-lookup"><span data-stu-id="ae5b7-133">Remediate the error in the file offline.</span></span> <span data-ttu-id="ae5b7-134">Per i file crittografati, che richiedono un software di decrittografia, per rimuovere la protezione dalle password, fornire la password e salvare il file oppure utilizzare un programma di cracking delle password.</span><span class="sxs-lookup"><span data-stu-id="ae5b7-134">For encrypted files, that would require decryption software, to remove password protection, either provide the password and save the file or use a password cracker.</span></span> <span data-ttu-id="ae5b7-135">Dopo aver rimediato il file, passare al passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="ae5b7-135">After you remediate the file, go to the next step.</span></span>

3. <span data-ttu-id="ae5b7-136">Nel set di Revisione selezionare il file con l'errore di elaborazione da correggere e quindi fare clic su **correzione**.</span><span class="sxs-lookup"><span data-stu-id="ae5b7-136">In the review set, select the file with the processing error that you remediated, and then  click **Remediation**.</span></span>

   ![Fare clic su correzione nel banner del documento con errore di elaborazione](../media/SIERimage6.png)


4. <span data-ttu-id="ae5b7-138">Fare clic su **Sfoglia**, passare al percorso del file di correzione nel computer locale e quindi selezionare il file.</span><span class="sxs-lookup"><span data-stu-id="ae5b7-138">Click **Browse**, go to the location of the remediated file on your local computer, and then select the file.</span></span>

   ![Fare clic su Sfoglia e selezionare il file corretti nel computer locale](../media/SIERimage7.png)

    <span data-ttu-id="ae5b7-140">Dopo aver selezionato il file di correzione, viene caricato automaticamente nel set di revisione.</span><span class="sxs-lookup"><span data-stu-id="ae5b7-140">After selecting the remediated file, it is automatically uploaded to the review set.</span></span> <span data-ttu-id="ae5b7-141">È possibile monitorare lo stato di elaborazione del file.</span><span class="sxs-lookup"><span data-stu-id="ae5b7-141">You can track the processing status of the file.</span></span>

    ![Lo stato del processo di correzione viene visualizzato](../media/SIERimage8.png)

   <span data-ttu-id="ae5b7-143">Al termine dell'elaborazione, è possibile visualizzare il documento correttivo.</span><span class="sxs-lookup"><span data-stu-id="ae5b7-143">After processing is completed, you can view the remediated document.</span></span>

    ![È possibile visualizzare il file di correzione nel formato nativo nel set di Revisione](../media/SIERimage9.png)

<span data-ttu-id="ae5b7-145">Per ulteriori informazioni sugli elementi che si verificano quando un documento viene correttivo, vedere [cosa succede quando i file vengono corretti](error-remediation.md#what-happens-when-files-are-remediated).</span><span class="sxs-lookup"><span data-stu-id="ae5b7-145">For more information about what happens when a document is remediated, see [What happens when files are remediated](error-remediation.md#what-happens-when-files-are-remediated).</span></span>

## <a name="search-for-remediated-documents"></a><span data-ttu-id="ae5b7-146">Ricerca di documenti corretti</span><span class="sxs-lookup"><span data-stu-id="ae5b7-146">Search for remediated documents</span></span>

<span data-ttu-id="ae5b7-147">È possibile cercare tutti i documenti in un set di revisione che sono stati corretti utilizzando la condizione **Keywords** e specificando la proprietà seguente: coppia valore: **IsFromErrorRemediation: true**.</span><span class="sxs-lookup"><span data-stu-id="ae5b7-147">You can search for all documents in a review set that were remediated by using the **Keywords** condition and specifying the following property:value pair: **IsFromErrorRemediation:true**.</span></span> <span data-ttu-id="ae5b7-148">Questa proprietà è disponibile anche nel file di caricamento dell'esportazione quando si esportano i documenti da un set di revisione.</span><span class="sxs-lookup"><span data-stu-id="ae5b7-148">This property is also available in the export load file when you export documents from a review set.</span></span>
