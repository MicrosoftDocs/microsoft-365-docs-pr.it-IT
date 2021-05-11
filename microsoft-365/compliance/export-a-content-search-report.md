---
title: Esportare un report di Ricerca contenuto
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
f1_keywords:
- ms.o365.cc.CustomizeExportReport
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 5c8c1db6-d8ac-4dbb-8a7a-f65d452169b9
description: Anziché esportare i risultati effettivi di una ricerca di contenuto nel Centro sicurezza & conformità in Office 365, è possibile esportare un report dei risultati della ricerca. Il report contiene un riepilogo dei risultati della ricerca e un documento con informazioni dettagliate su ogni elemento da esportare.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 094e67812b45ab1544d629ba6ddabcd86c70c633
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311574"
---
# <a name="export-a-content-search-report"></a><span data-ttu-id="cc775-104">Esportare il rapporto della Ricerca contenuto</span><span class="sxs-lookup"><span data-stu-id="cc775-104">Export a Content search report</span></span>

<span data-ttu-id="cc775-105">Anziché esportare il set completo di risultati della ricerca da una ricerca contenuto nel Centro conformità Microsoft 365 (o da una ricerca associata a un caso di eDiscovery di base), è possibile esportare gli stessi report generati quando si esportano i risultati della ricerca effettivi.</span><span class="sxs-lookup"><span data-stu-id="cc775-105">Instead of exporting the full set of search results from a Content search in the Microsoft 365 compliance Center (or from a search that's associated with a Core eDiscovery case), you can export the same reports that are generated when you export the actual search results.</span></span>
  
<span data-ttu-id="cc775-106">Quando si esporta un report, i file di report vengono scaricati in una cartella del computer locale con lo stesso nome di Ricerca contenuto, ma accodati con *_ReportsOnly*.</span><span class="sxs-lookup"><span data-stu-id="cc775-106">When you export a report, the report files are downloaded to a folder on your local computer that has the same name as the Content Search, but that's appended with *_ReportsOnly*.</span></span> <span data-ttu-id="cc775-107">Ad esempio, se la ricerca contenuto è denominata  *ContosoCase0815,* il report viene scaricato in una cartella denominata *ContosoCase0815_ReportsOnly*.</span><span class="sxs-lookup"><span data-stu-id="cc775-107">For example, if the Content Search is named  *ContosoCase0815*, then the report is downloaded to a folder named *ContosoCase0815_ReportsOnly*.</span></span> <span data-ttu-id="cc775-108">Per un elenco dei documenti inclusi nel report, vedere [What's included in the report](#whats-included-in-the-report).</span><span class="sxs-lookup"><span data-stu-id="cc775-108">For a list of documents that are included in the report, see [What's included in the report](#whats-included-in-the-report).</span></span>

## <a name="before-you-export-a-search-report"></a><span data-ttu-id="cc775-109">Prima di esportare un report di ricerca</span><span class="sxs-lookup"><span data-stu-id="cc775-109">Before you export a search report</span></span>

- <span data-ttu-id="cc775-110">Per esportare un report di ricerca, è necessario disporre del ruolo di gestione ricerca di conformità nel Centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="cc775-110">To export a search report, you have to be assigned the Compliance Search management role in Security & Compliance Center.</span></span> <span data-ttu-id="cc775-111">Questo ruolo viene assegnato per impostazione predefinita ai gruppi di ruoli Gestione eDiscovery e Gestione organizzazione incorporati.</span><span class="sxs-lookup"><span data-stu-id="cc775-111">This role is assigned by default to the built-in eDiscovery Manager and Organization Management role groups.</span></span> <span data-ttu-id="cc775-112">Per altre informazioni, vedere [Assegnare autorizzazioni di eDiscovery](assign-ediscovery-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="cc775-112">For more information, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

- <span data-ttu-id="cc775-113">Quando si esporta un report, i dati vengono temporaneamente archiviati in un percorso Archiviazione di Azure nel cloud Microsoft prima di essere scaricati nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="cc775-113">When you export a report, the data is temporarily stored in an Azure Storage location in the Microsoft cloud before it's downloaded to your local computer.</span></span> <span data-ttu-id="cc775-114">Assicurati che l'organizzazione possa connettersi all'endpoint in Azure, che è **\* .blob.core.windows.net** (il carattere jolly rappresenta un identificatore univoco per l'esportazione).</span><span class="sxs-lookup"><span data-stu-id="cc775-114">Be sure that your organization can connect to the endpoint in Azure, which is **\*.blob.core.windows.net** (the wildcard represents a unique identifier for your export).</span></span> <span data-ttu-id="cc775-115">I dati dei risultati della ricerca vengono eliminati dalla posizione Archiviazione di Azure due settimane dopo la creazione.</span><span class="sxs-lookup"><span data-stu-id="cc775-115">The search results data is deleted from the Azure Storage location two weeks after it's created.</span></span>

- <span data-ttu-id="cc775-116">Il computer utilizzato per esportare i risultati della ricerca deve soddisfare i seguenti requisiti di sistema:</span><span class="sxs-lookup"><span data-stu-id="cc775-116">The computer you use to export the search results has to meet the following system requirements:</span></span>

  - <span data-ttu-id="cc775-117">Versione più recente Windows (32 bit o 64 bit)</span><span class="sxs-lookup"><span data-stu-id="cc775-117">Latest version of Windows (32-bit or 64-bit)</span></span>

  - <span data-ttu-id="cc775-118">Microsoft .NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="cc775-118">Microsoft .NET Framework 4.7</span></span>

- <span data-ttu-id="cc775-119">Per eseguire lo strumento di esportazione di eDiscovery<sup>1,</sup>è necessario utilizzare uno dei browser supportati seguenti:</span><span class="sxs-lookup"><span data-stu-id="cc775-119">You have to use one of the following supported browsers to run the eDiscovery Export Tool<sup>1</sup>:</span></span>

  - <span data-ttu-id="cc775-120">Microsoft Edge <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="cc775-120">Microsoft Edge <sup>2</sup></span></span>

    <span data-ttu-id="cc775-121">OPPURE</span><span class="sxs-lookup"><span data-stu-id="cc775-121">OR</span></span>

  - <span data-ttu-id="cc775-122">Microsoft Internet Explorer 10 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="cc775-122">Microsoft Internet Explorer 10 and later versions</span></span>

  > [!NOTE]
  > <span data-ttu-id="cc775-123"><sup>1</sup> Microsoft non produce estensioni o componenti aggiuntivi di terze parti per ClickOnce applicazioni.</span><span class="sxs-lookup"><span data-stu-id="cc775-123"><sup>1</sup> Microsoft doesn't manufacture third-party extensions or add-ons for ClickOnce applications.</span></span> <span data-ttu-id="cc775-124">L'esportazione dei risultati della ricerca con un browser non supportato con estensioni o componenti aggiuntivi di terze parti non è supportata.</span><span class="sxs-lookup"><span data-stu-id="cc775-124">Exporting search results using an unsupported browser with third-party extensions or add-ons isn't supported.</span></span><br/>
  > <span data-ttu-id="cc775-125"><sup>2</sup> In seguito alle recenti modifiche apportate al Microsoft Edge, il ClickOnce non è più abilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="cc775-125"><sup>2</sup> As a result of recent changes to Microsoft Edge, ClickOnce support is no longer enabled by default.</span></span> <span data-ttu-id="cc775-126">Per istruzioni sull'abilitazione del ClickOnce in Edge, vedere [Use the eDiscovery Export Tool in Microsoft Edge](configure-edge-to-export-search-results.md).</span><span class="sxs-lookup"><span data-stu-id="cc775-126">For instructions on enabling ClickOnce support in Edge, see [Use the eDiscovery Export Tool in Microsoft Edge](configure-edge-to-export-search-results.md).</span></span>

- <span data-ttu-id="cc775-127">Se le dimensioni totali stimate dei risultati restituiti dalla ricerca superano i 2 TB, l'esportazione dei report ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="cc775-127">If the estimated total size of the results returned by search exceeds 2 TB, exporting the reports fails.</span></span> <span data-ttu-id="cc775-128">Per esportare correttamente i report, provare a restringere l'ambito ed eseguire di nuovo la ricerca in modo che la dimensione stimata dei risultati sia inferiore a 2 TB.</span><span class="sxs-lookup"><span data-stu-id="cc775-128">To successfully export the reports, try to narrow the scope and rerun the search so the estimated size of the results is less than 2 TB.</span></span>

- <span data-ttu-id="cc775-129">Se i risultati di una ricerca sono precedenti a 7 giorni e si invia un processo di report di esportazione, viene visualizzato un messaggio di errore in cui viene richiesto di eseguire di nuovo la ricerca per aggiornare i risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="cc775-129">If the results of a search are older than 7 days and you submit an export report job, an error message is displayed prompting you to rerun the search to update the search results.</span></span> <span data-ttu-id="cc775-130">In questo caso, annullare l'esportazione, eseguire di nuovo la ricerca e quindi avviare di nuovo l'esportazione.</span><span class="sxs-lookup"><span data-stu-id="cc775-130">If this happens, cancel the export, rerun the search, and then start the export again.</span></span>

- <span data-ttu-id="cc775-131">L'esportazione dei report di ricerca viene eseguita in base al numero massimo di esportazioni in esecuzione contemporaneamente e al numero massimo di esportazioni che un singolo utente può eseguire.</span><span class="sxs-lookup"><span data-stu-id="cc775-131">Exporting search reports counts against the maximum number of exports running at the same time and the maximum number of exports that a single user can run.</span></span> <span data-ttu-id="cc775-132">Per ulteriori informazioni sui limiti di esportazione, vedere [Export Content search results](export-search-results.md#export-limits).</span><span class="sxs-lookup"><span data-stu-id="cc775-132">For more information about export limits, see [Export Content search results](export-search-results.md#export-limits).</span></span>
  
## <a name="step-1-generate-the-report-for-export"></a><span data-ttu-id="cc775-133">Passaggio 1: Generare il report per l'esportazione</span><span class="sxs-lookup"><span data-stu-id="cc775-133">Step 1: Generate the report for export</span></span>

<span data-ttu-id="cc775-134">Il primo passaggio consiste nel preparare il report per il download nel computer in uso.</span><span class="sxs-lookup"><span data-stu-id="cc775-134">The first step is to prepare the report for downloading to your computer exporting.</span></span> <span data-ttu-id="cc775-135">Quando si esporta il report, i documenti del report vengono caricati in un'area Archiviazione di Azure nel cloud Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cc775-135">When you export the report, the report documents are uploaded to an Azure Storage area in the Microsoft cloud.</span></span>
  
1. <span data-ttu-id="cc775-136">Nel Centro Microsoft 365 conformità selezionare la ricerca contenuto da cui si desidera esportare il report.</span><span class="sxs-lookup"><span data-stu-id="cc775-136">In the Microsoft 365 compliance center, select the Content search that you want to export the report from.</span></span>
  
2. <span data-ttu-id="cc775-137">Scegliere **Esporta** report dal menu Azioni nella parte inferiore della pagina del riquadro a comparsa **di ricerca.**</span><span class="sxs-lookup"><span data-stu-id="cc775-137">On the **Actions** menu at the bottom of the search flyout page, click **Export report**.</span></span>

   ![Opzione Esporta report nel menu Azioni](../media/ActionMenuExportReport.png)

   <span data-ttu-id="cc775-139">Viene **visualizzata la** pagina a comparsa Esporta report.</span><span class="sxs-lookup"><span data-stu-id="cc775-139">The **Export report** flyout page is displayed.</span></span> <span data-ttu-id="cc775-140">Le opzioni del report di esportazione disponibili per esportare le informazioni sulla ricerca dipendono dal fatto che i risultati della ricerca si trovino nelle cassette postali o nei siti o in una combinazione di entrambi.</span><span class="sxs-lookup"><span data-stu-id="cc775-140">The export report options available to export information about the search depend on whether search results are located in mailboxes or sites or a combination of both.</span></span>
  
3. <span data-ttu-id="cc775-141">In **Opzioni di output** scegliere una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cc775-141">Under **Output options**, choose one of the following options:</span></span>
  
   ![Opzioni di esportazione dell'output](../media/ExportOutputOptions.png)

    - <span data-ttu-id="cc775-143">Tutti gli elementi, esclusi quelli con formato non riconosciuto, vengono crittografati o non sono stati **indicizzati per altri motivi.**</span><span class="sxs-lookup"><span data-stu-id="cc775-143">**All items, excluding ones that have unrecognized format, are encrypted, or weren't indexed for other reasons**.</span></span> <span data-ttu-id="cc775-144">Questa opzione esporta solo informazioni sugli elementi indicizzati.</span><span class="sxs-lookup"><span data-stu-id="cc775-144">This option only exports information about indexed items.</span></span>
  
    - <span data-ttu-id="cc775-145">Tutti gli elementi, inclusi quelli con formato non riconosciuto, vengono crittografati o non sono stati **indicizzati per altri motivi.**</span><span class="sxs-lookup"><span data-stu-id="cc775-145">**All items, including ones that have unrecognized format, are encrypted, or weren't indexed for other reasons**.</span></span> <span data-ttu-id="cc775-146">Questa opzione esporta informazioni sugli elementi indicizzati e non indicizzati.</span><span class="sxs-lookup"><span data-stu-id="cc775-146">This option exports information about indexed and unindexed items.</span></span>
  
    - <span data-ttu-id="cc775-147">**Solo gli elementi con un** formato non riconosciuto, crittografati o non indicizzati per altri motivi.</span><span class="sxs-lookup"><span data-stu-id="cc775-147">**Only items that have an unrecognized format, are encrypted, or weren't indexed for other reasons**.</span></span> <span data-ttu-id="cc775-148">Questa opzione esporta solo informazioni sugli elementi non indicizzati.</span><span class="sxs-lookup"><span data-stu-id="cc775-148">This option only exports information about unindexed items.</span></span>

4. <span data-ttu-id="cc775-149">Configurare **l'opzione Abilita deduplicazione per Exchange contenuto.**</span><span class="sxs-lookup"><span data-stu-id="cc775-149">Configure the **Enable de-duplication for Exchange content** option.</span></span>
  
   - <span data-ttu-id="cc775-150">Se si seleziona questa opzione, il conteggio dei messaggi duplicati (prima della deduplicazione e dopo la deduplicazione) viene incluso nel rapporto riepilogativo dell'esportazione.</span><span class="sxs-lookup"><span data-stu-id="cc775-150">If you select this option, the count of duplicate messages (before de-duplication and after de-duplication) is included in the export summary report.</span></span> <span data-ttu-id="cc775-151">Inoltre, solo una copia di un messaggio verrà inclusa nel file manifest.xml.</span><span class="sxs-lookup"><span data-stu-id="cc775-151">Also, only one copy of a message will be included in the manifest.xml file.</span></span> <span data-ttu-id="cc775-152">Tuttavia, il report dei risultati dell'esportazione conterrà una riga per ogni copia di un messaggio duplicato in modo da poter identificare le cassette postali che contengono una copia del messaggio duplicato.</span><span class="sxs-lookup"><span data-stu-id="cc775-152">But the export results report will contain a row for every copy of a duplicate message so that you can identify the mailboxes that contain a copy of the duplicate message.</span></span> <span data-ttu-id="cc775-153">Per ulteriori informazioni sui report esportati, vedere [What's included in the report](#whats-included-in-the-report).</span><span class="sxs-lookup"><span data-stu-id="cc775-153">For more information about the exported reports, see [What's included in the report](#whats-included-in-the-report).</span></span>

   - <span data-ttu-id="cc775-154">Se non si seleziona questa opzione, i rapporti di esportazione conterranno informazioni su tutti i messaggi restituiti dalla ricerca, inclusi i duplicati.</span><span class="sxs-lookup"><span data-stu-id="cc775-154">If you don't select this option, the export reports will contain information about all messages returned by the search, including duplicates.</span></span>

     <span data-ttu-id="cc775-155">Per ulteriori informazioni sulla deduplicazione e su come vengono identificati gli elementi duplicati, vedere [De-duplicazione nei risultati della ricerca eDiscovery.](de-duplication-in-ediscovery-search-results.md)</span><span class="sxs-lookup"><span data-stu-id="cc775-155">For more information about de-duplication and how duplicate items are identified, see [De-duplication in eDiscovery search results](de-duplication-in-ediscovery-search-results.md).</span></span>

5. <span data-ttu-id="cc775-156">Fare **clic su Genera report**.</span><span class="sxs-lookup"><span data-stu-id="cc775-156">Click **Generate report**.</span></span>

   <span data-ttu-id="cc775-157">I report di ricerca sono preparati per il download, il che significa che i documenti del report vengono caricati in un percorso Archiviazione di Azure nel cloud Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cc775-157">The search reports are prepared for downloading, which means the report documents are uploaded to an Azure Storage location in the Microsoft cloud.</span></span> <span data-ttu-id="cc775-158">Questa operazione può richiedere diversi minuti.</span><span class="sxs-lookup"><span data-stu-id="cc775-158">This may take several minutes.</span></span>

<span data-ttu-id="cc775-159">Per istruzioni su come scaricare i report di ricerca esportati, vedere la sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="cc775-159">See the next section for instructions to download the exported search reports.</span></span>
  
## <a name="step-2-download-the-report"></a><span data-ttu-id="cc775-160">Passaggio 2: scaricare il report</span><span class="sxs-lookup"><span data-stu-id="cc775-160">Step 2: Download the report</span></span>

<span data-ttu-id="cc775-161">Il passaggio successivo consiste nel scaricare il report dall'area Archiviazione di Azure nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="cc775-161">The next step is to download the report from the Azure Storage area to your local computer.</span></span>

1. <span data-ttu-id="cc775-162">Nella pagina **Ricerca contenuto** nel Centro Microsoft 365 conformità selezionare la **scheda** Esportazioni</span><span class="sxs-lookup"><span data-stu-id="cc775-162">On the **Content search** page in the Microsoft 365 compliance center, select the **Exports** tab</span></span>
  
   <span data-ttu-id="cc775-163">Potrebbe essere necessario fare clic **su Aggiorna** per aggiornare l'elenco dei processi di esportazione in modo che venga visualizzato il processo di esportazione creato.</span><span class="sxs-lookup"><span data-stu-id="cc775-163">You may have to click **Refresh** to update the list of export jobs so that it shows the export job you created.</span></span> <span data-ttu-id="cc775-164">I processi di report di esportazione hanno lo stesso nome della ricerca corrispondente **_ReportsOnly** aggiunto al nome di ricerca.</span><span class="sxs-lookup"><span data-stu-id="cc775-164">Export report jobs have the same name as the corresponding search with **_ReportsOnly** appended to the search name.</span></span>
  
2. <span data-ttu-id="cc775-165">Selezionare il processo di esportazione creato nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="cc775-165">Select the export job that you created in Step 1.</span></span>

3. <span data-ttu-id="cc775-166">Nella pagina **a comparsa Esporta report** in Chiave di **esportazione** fare clic su Copia **negli Appunti.**</span><span class="sxs-lookup"><span data-stu-id="cc775-166">On the **Export report** flyout page under **Export key**, click **Copy to clipboard**.</span></span> <span data-ttu-id="cc775-167">Questa chiave viene utilizzata nel passaggio 6 per scaricare i risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="cc775-167">You use this key in step 6 to download the search results.</span></span>
  
   > [!IMPORTANT]
   > <span data-ttu-id="cc775-168">Poiché chiunque può installare e avviare lo strumento di esportazione di eDiscovery e quindi utilizzare questa chiave per scaricare il report di ricerca, assicurarsi di adottare precauzioni per proteggere questa chiave proprio come si proteggono le password o altre informazioni correlate alla sicurezza.</span><span class="sxs-lookup"><span data-stu-id="cc775-168">Because anyone can install and start the eDiscovery Export tool, and then use this key to download the search report, be sure to take precautions to protect this key just like you would protect passwords or other security-related information.</span></span>

4. <span data-ttu-id="cc775-169">Nella parte superiore della pagina a comparsa fare clic su **Scarica risultati.**</span><span class="sxs-lookup"><span data-stu-id="cc775-169">At the top of the flyout page, click **Download results**.</span></span>

5. <span data-ttu-id="cc775-170">Se viene richiesto di installare lo strumento di **esportazione di eDiscovery,** fare clic su **Installa**.</span><span class="sxs-lookup"><span data-stu-id="cc775-170">If you're prompted to install the **eDiscovery Export Tool**, click **Install**.</span></span>

6. <span data-ttu-id="cc775-171">Nello strumento **di esportazione eDiscovery** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cc775-171">In the **eDiscovery Export Tool**, do the following:</span></span>

   ![Strumento di esportazione eDiscovery](../media/eDiscoveryExportTool.png)

   1. <span data-ttu-id="cc775-173">Incollare la chiave di esportazione copiata nel passaggio 3 nella casella appropriata.</span><span class="sxs-lookup"><span data-stu-id="cc775-173">Paste the export key that you copied in step 3 in the appropriate box.</span></span>
  
   2. <span data-ttu-id="cc775-174">Fare **clic su** Sfoglia per specificare il percorso in cui si desidera scaricare i file di report di ricerca.</span><span class="sxs-lookup"><span data-stu-id="cc775-174">Click **Browse** to specify the location where you want to download the search report files.</span></span>

7. <span data-ttu-id="cc775-175">Fare clic su **Avvia** per scaricare i risultati della ricerca nel computer.</span><span class="sxs-lookup"><span data-stu-id="cc775-175">Click **Start** to download the search results to your computer.</span></span>
  
    <span data-ttu-id="cc775-176">Lo **Strumento di esportazione eDiscovery** consente di visualizzare informazioni sullo stato delle informazioni relative al processo di esportazione, incluso il numero stimato (e le dimensioni) degli elementi rimanenti da scaricare.</span><span class="sxs-lookup"><span data-stu-id="cc775-176">The **eDiscovery Export Tool** displays status information about the export process, including an estimate of the number (and size) of the remaining items to be downloaded.</span></span> <span data-ttu-id="cc775-177">Al termine del processo di esportazione, è possibile accedere ai file nel percorso in cui sono stati scaricati.</span><span class="sxs-lookup"><span data-stu-id="cc775-177">When the export process is complete, you can access the files in the location where they were downloaded.</span></span>
  
## <a name="whats-included-in-the-report"></a><span data-ttu-id="cc775-178">Elementi inclusi nel report</span><span class="sxs-lookup"><span data-stu-id="cc775-178">What's included in the report</span></span>

<span data-ttu-id="cc775-179">Quando si genera ed esporta un report sui risultati di una ricerca contenuto, vengono scaricati i documenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="cc775-179">When you generate and export a report about the results of a Content search, the following documents are downloaded:</span></span>
  
- <span data-ttu-id="cc775-180">**Riepilogo esportazione:** Un Excel contenente un riepilogo dell'esportazione.</span><span class="sxs-lookup"><span data-stu-id="cc775-180">**Export summary:** An Excel document that contains a summary of the export.</span></span> <span data-ttu-id="cc775-181">Sono incluse informazioni quali il numero di origini contenuto in cui è stata ricercata, il numero di risultati della ricerca da ogni percorso di contenuto, il numero stimato di elementi, il numero effettivo di elementi da esportare e le dimensioni stimate ed effettive degli elementi che verranno esportati.</span><span class="sxs-lookup"><span data-stu-id="cc775-181">This includes information such as the number of content sources that were searched, the number of search results from each content location, the estimated number of items, the actual number of items that would be exported, and the estimated and actual size of items that would be exported.</span></span>

   <span data-ttu-id="cc775-182">Se si includono elementi non indicizzati durante l'esportazione del report, il numero di elementi non indicizzati viene incluso nel numero totale di risultati di ricerca stimati e nel numero totale di risultati di ricerca scaricati (se si desidera esportare i risultati della ricerca) elencati nel rapporto riepilogativo dell'esportazione.</span><span class="sxs-lookup"><span data-stu-id="cc775-182">If you include unindexed items when exporting the report, the number of unindexed items are included in the total number of estimated search results and in the total number of downloaded search results (if you were to export the search results) that are listed in the export summary report.</span></span> <span data-ttu-id="cc775-183">In altre parole, il numero totale di elementi che verrebbero scaricati è uguale al numero totale di risultati stimati e al numero totale di elementi non indicizzati.</span><span class="sxs-lookup"><span data-stu-id="cc775-183">In other words, the total number of items that would be downloaded is equal to the total number of estimated results and the total number of unindexed items.</span></span>
  
- <span data-ttu-id="cc775-184">**Manifesto:** File manifesto (in formato XML) contenente informazioni su ogni elemento incluso nei risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="cc775-184">**Manifest:** A manifest file (in XML format) that contains information about each item included in the search results.</span></span> <span data-ttu-id="cc775-185">Se è stata abilitata l'opzione di deduplicazione, i messaggi duplicati non vengono inclusi nel file manifesto.</span><span class="sxs-lookup"><span data-stu-id="cc775-185">If you enabled the de-duplication option, duplicate message are not included in the manifest file.</span></span>

- <span data-ttu-id="cc775-186">**Risultati:** Un Excel contenente una riga con informazioni su ogni elemento indicizzato che verrà esportato con i risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="cc775-186">**Results:** An Excel document that contains a row with information about each indexed item that would be exported with the search results.</span></span> <span data-ttu-id="cc775-187">Per la posta elettronica, il log dei risultati contiene informazioni su ogni messaggio, tra cui:</span><span class="sxs-lookup"><span data-stu-id="cc775-187">For email, the result log contains information about each message, including:</span></span> 

  - <span data-ttu-id="cc775-188">Il percorso del messaggio nella cassetta postale di origine (e se il messaggio è nella cassetta postale principale o di archiviazione).</span><span class="sxs-lookup"><span data-stu-id="cc775-188">The location of the message in the source mailbox (including whether the message is in the primary or archive mailbox).</span></span>

  - <span data-ttu-id="cc775-189">La data in cui è stato inviato o ricevuto il messaggio.</span><span class="sxs-lookup"><span data-stu-id="cc775-189">The date the message was sent or received.</span></span>

  - <span data-ttu-id="cc775-190">La riga dell'oggetto del messaggio.</span><span class="sxs-lookup"><span data-stu-id="cc775-190">The Subject line from the message.</span></span>

  - <span data-ttu-id="cc775-191">Il mittente e i destinatari del messaggio.</span><span class="sxs-lookup"><span data-stu-id="cc775-191">The sender and recipients of the message.</span></span>

  <span data-ttu-id="cc775-192">Per i documenti SharePoint e OneDrive for Business, il registro dei risultati contiene informazioni su ogni documento, tra cui:</span><span class="sxs-lookup"><span data-stu-id="cc775-192">For documents from SharePoint and OneDrive for Business sites, the results log contains information about each document, including:</span></span>

  - <span data-ttu-id="cc775-193">L'URL per il documento.</span><span class="sxs-lookup"><span data-stu-id="cc775-193">The URL for the document.</span></span>

  - <span data-ttu-id="cc775-194">L’URL per la raccolta di siti in cui si trova il documento.</span><span class="sxs-lookup"><span data-stu-id="cc775-194">The URL for the site collection where the document is located.</span></span>

  - <span data-ttu-id="cc775-195">La data dell'ultima modifica al documento.</span><span class="sxs-lookup"><span data-stu-id="cc775-195">The date that the document was last modified.</span></span>

  - <span data-ttu-id="cc775-196">Il nome del documento (che si trova nella colonna Oggetto nel log dei risultati).</span><span class="sxs-lookup"><span data-stu-id="cc775-196">The name of the document (which is located in the Subject column in the result log).</span></span>

  > [!NOTE]
  > <span data-ttu-id="cc775-197">Il numero di righe nel report **Risultati** deve essere uguale al numero totale di risultati della ricerca meno il numero totale di elementi elencati nel report **Elementi non indicizzati.**</span><span class="sxs-lookup"><span data-stu-id="cc775-197">The number of rows in the **Results** report should be equal to the total number of search results minus the total number of items listed in the **Unindexed Items** report.</span></span>
  
- <span data-ttu-id="cc775-198">**Trace.log**: Registro di traccia contenente informazioni dettagliate sulla registrazione del processo di esportazione e che consente di individuare i problemi durante l'esportazione.</span><span class="sxs-lookup"><span data-stu-id="cc775-198">**Trace.log**: A trace log that contains detailed logging information about the export process and can help uncover issues during export.</span></span> <span data-ttu-id="cc775-199">Se si apre un ticket con il supporto tecnico Microsoft per un problema relativo all'esportazione dei report di ricerca, potrebbe essere richiesto di fornire questo registro di traccia.</span><span class="sxs-lookup"><span data-stu-id="cc775-199">If you open a ticket with Microsoft Support about an issue related to exporting search reports, you may be asked to provide this trace log.</span></span>

- <span data-ttu-id="cc775-200">**Elementi non indicizzati:** Un Excel contenente informazioni su eventuali elementi non indicizzati inclusi nei risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="cc775-200">**Unindexed items:** An Excel document that contains information about any unindexed items included in the search results.</span></span> <span data-ttu-id="cc775-201">Se non si includono elementi non indicizzati quando si genera il report dei risultati della ricerca, il report verrà comunque scaricato, ma sarà vuoto.</span><span class="sxs-lookup"><span data-stu-id="cc775-201">If you don't include unindexed items when you generate the search results report, this report will still be downloaded, but will be empty.</span></span>
