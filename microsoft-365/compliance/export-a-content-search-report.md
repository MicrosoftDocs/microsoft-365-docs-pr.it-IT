---
title: Esportare un report di Ricerca contenuto
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
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
description: Invece di esportare i risultati effettivi di una ricerca contenuto nel centro sicurezza & conformità in Office 365, è possibile esportare un rapporto sui risultati di ricerca. Il report contiene un riepilogo dei risultati della ricerca e un documento con informazioni dettagliate su ogni elemento che verrebbe esportato.
ms.openlocfilehash: 6730a1c406e02de26cbef964e445cfad31c948ec
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42074393"
---
# <a name="export-a-content-search-report"></a><span data-ttu-id="b228b-104">Esportare un report di Ricerca contenuto</span><span class="sxs-lookup"><span data-stu-id="b228b-104">Export a Content Search report</span></span>

<span data-ttu-id="b228b-105">Invece di esportare il set completo di risultati della ricerca da una ricerca di contenuto nel centro sicurezza & Compliance (e da una ricerca di contenuto associata a un caso di eDiscovery), è possibile esportare gli stessi rapporti generati quando si esportano i risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="b228b-105">Instead of exporting the full set of search results from a Content Search in the Security & Compliance Center (and from a Content Search that's associated with an eDiscovery case), you can export the same reports that are generated when you export search results.</span></span>
  
<span data-ttu-id="b228b-106">Quando si esporta un report, viene scaricato in una cartella con lo stesso nome della ricerca di contenuto, ma accodato con *_ReportsOnly*.</span><span class="sxs-lookup"><span data-stu-id="b228b-106">When you export a report, it's downloaded to a folder that has the same name as the Content Search, but that's appended with *_ReportsOnly*.</span></span> <span data-ttu-id="b228b-107">Ad esempio, se la ricerca di contenuto è denominata *ContosoCase0815*, il report viene scaricato in una cartella denominata *ContosoCase0815_ReportsOnly*.</span><span class="sxs-lookup"><span data-stu-id="b228b-107">For example, if the Content Search is named  *ContosoCase0815*, then the report is downloaded to a folder named *ContosoCase0815_ReportsOnly*.</span></span> <span data-ttu-id="b228b-108">Per un elenco dei documenti inclusi nel report, vedere [What ' s incluso nel report](#whats-included-in-the-report).</span><span class="sxs-lookup"><span data-stu-id="b228b-108">For a list of documents that are included in the report, see [What's included in the report](#whats-included-in-the-report).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="b228b-109">Informazioni preliminari</span><span class="sxs-lookup"><span data-stu-id="b228b-109">Before you begin</span></span>

- <span data-ttu-id="b228b-110">Per esportare un rapporto di ricerca contenuto, è necessario assegnare il ruolo di gestione della ricerca di conformità nel centro sicurezza & Compliance.</span><span class="sxs-lookup"><span data-stu-id="b228b-110">To export a Content Search report, you have to be assigned the Compliance Search management role in the Security & Compliance Center.</span></span> <span data-ttu-id="b228b-111">Questo ruolo viene assegnato ai gruppi di ruoli di gestione eDiscovery e dell'organizzazione incorporati.</span><span class="sxs-lookup"><span data-stu-id="b228b-111">This role is assigned to the built-in eDiscovery Manager and Organization Management role groups.</span></span> <span data-ttu-id="b228b-112">Non viene assegnato per impostazione predefinita al gruppo di ruoli Gestione organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b228b-112">It isn't assigned by default to the Organization Management role group.</span></span> <span data-ttu-id="b228b-113">Per altre informazioni, vedere [Assegnare autorizzazioni di eDiscovery](assign-ediscovery-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="b228b-113">For more information, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>
    
- <span data-ttu-id="b228b-114">Quando si esporta un report, i dati vengono temporaneamente archiviati in un'area di archiviazione di Azure univoca nel cloud Microsoft prima che vengano scaricati nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="b228b-114">When you export a report, the data is temporarily stored in a unique Azure Storage area in the Microsoft cloud before it's downloaded to your local computer.</span></span> <span data-ttu-id="b228b-115">Assicurarsi che l'organizzazione sia in grado di connettersi all'endpoint in Azure, che è \*\* \*. blob.Core.Windows.NET\*\* (il carattere jolly rappresenta un identificatore univoco per l'esportazione).</span><span class="sxs-lookup"><span data-stu-id="b228b-115">Be sure that your organization can connect to the endpoint in Azure, which is **\*.blob.core.windows.net** (the wildcard represents a unique identifier for your export).</span></span> <span data-ttu-id="b228b-116">I dati dei risultati della ricerca vengono eliminati dall'area di archiviazione di Azure due settimane dopo la sua creazione.</span><span class="sxs-lookup"><span data-stu-id="b228b-116">The search results data is deleted from the Azure Storage area two weeks after it's created.</span></span> 
    
- <span data-ttu-id="b228b-117">Il computer utilizzato per esportare i risultati della ricerca deve soddisfare i seguenti requisiti di sistema:</span><span class="sxs-lookup"><span data-stu-id="b228b-117">The computer you use to export the search results has to meet the following system requirements:</span></span>
    
  - <span data-ttu-id="b228b-118">versioni a 32 bit o 64 bit di Windows 7 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="b228b-118">32-bit or 64-bit versions of Windows 7 and later versions</span></span>
    
  - <span data-ttu-id="b228b-119">Microsoft .NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="b228b-119">Microsoft .NET Framework 4.7</span></span>
    
- <span data-ttu-id="b228b-120">Per eseguire lo strumento di esportazione di eDiscovery<sup>1</sup>, è necessario utilizzare uno dei seguenti browser supportati:</span><span class="sxs-lookup"><span data-stu-id="b228b-120">You have to use one of the following supported browsers to run the eDiscovery Export Tool<sup>1</sup>:</span></span>

  - <span data-ttu-id="b228b-121">Microsoft Edge <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="b228b-121">Microsoft Edge <sup>2</sup></span></span>

    <span data-ttu-id="b228b-122">OPPURE</span><span class="sxs-lookup"><span data-stu-id="b228b-122">OR</span></span>

  - <span data-ttu-id="b228b-123">Microsoft Internet Explorer 10 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="b228b-123">Microsoft Internet Explorer 10 and later versions</span></span>

  > [!NOTE]
  > <span data-ttu-id="b228b-124"><sup>1</sup> Microsoft non produce estensioni o componenti aggiuntivi di terze parti per le applicazioni ClickOnce.</span><span class="sxs-lookup"><span data-stu-id="b228b-124"><sup>1</sup> Microsoft doesn't manufacture third-party extensions or add-ons for ClickOnce applications.</span></span> <span data-ttu-id="b228b-125">L'esportazione dei risultati di ricerca utilizzando un browser non supportato con le estensioni di terze parti o i componenti aggiuntivi non è supportata.</span><span class="sxs-lookup"><span data-stu-id="b228b-125">Exporting search results using an unsupported browser with third-party extensions or add-ons isn't supported.</span></span><br/>
  > <span data-ttu-id="b228b-126"><sup>2</sup> come risultato delle recenti modifiche apportate a Microsoft Edge, il supporto ClickOnce non è più abilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="b228b-126"><sup>2</sup> As a result of recent changes to Microsoft Edge, ClickOnce support is no longer enabled by default.</span></span> <span data-ttu-id="b228b-127">Per istruzioni sull'abilitazione del supporto ClickOnce in Edge, vedere [utilizzare lo strumento di esportazione di eDiscovery di Office 365 in Microsoft Edge](configure-edge-to-export-search-results.md).</span><span class="sxs-lookup"><span data-stu-id="b228b-127">For instructions on enabling ClickOnce support in Edge, see [Use the Office 365 eDiscovery Export Tool in Microsoft Edge](configure-edge-to-export-search-results.md).</span></span>

- <span data-ttu-id="b228b-128">Se le dimensioni totali stimate dei risultati restituiti da una ricerca di contenuto superano 2 TB, l'esportazione del rapporto ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="b228b-128">If the estimated total size of the results returned by a Content Search exceeds 2 TB, exporting the report fails.</span></span> <span data-ttu-id="b228b-129">Per esportare correttamente il report, provare a restringere l'ambito e rieseguire la ricerca in modo che le dimensioni stimate dei risultati siano inferiori a 2 TB.</span><span class="sxs-lookup"><span data-stu-id="b228b-129">To successfully export the report, try to narrow the scope and rerun the search so the estimated size of the results is less than 2 TB.</span></span>

- <span data-ttu-id="b228b-130">L'esportazione dei rapporti di ricerca del contenuto conta sul numero massimo di esportazioni in esecuzione contemporaneamente e sul numero massimo di esportazioni che un singolo utente può eseguire.</span><span class="sxs-lookup"><span data-stu-id="b228b-130">Exporting Content Search reports counts against the maximum number of exports running at the same time and the maximum number of exports that a single user can run.</span></span> <span data-ttu-id="b228b-131">Per ulteriori informazioni sui limiti di esportazione, vedere [Export content search results](export-search-results.md#export-limits).</span><span class="sxs-lookup"><span data-stu-id="b228b-131">For more information about export limits, see [Export Content Search results](export-search-results.md#export-limits).</span></span>

## <a name="generate-and-download-a-content-search-report"></a><span data-ttu-id="b228b-132">Generare e scaricare un report di ricerca contenuto</span><span class="sxs-lookup"><span data-stu-id="b228b-132">Generate and download a Content Search report</span></span>

<span data-ttu-id="b228b-133">I passaggi per generare e scaricare un report di ricerca contenuto sono simili all'esportazione dei risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="b228b-133">The steps to generate and download a Content Search report are similar to actually exporting search results.</span></span>
  
## <a name="step-1-generate-the-report-for-export"></a><span data-ttu-id="b228b-134">Passaggio 1: generare il report per l'esportazione</span><span class="sxs-lookup"><span data-stu-id="b228b-134">Step 1: Generate the report for export</span></span>

<span data-ttu-id="b228b-135">Il primo passaggio consiste nel preparare il report per il download nel computer che esporta.</span><span class="sxs-lookup"><span data-stu-id="b228b-135">The first step is to prepare the report for downloading to your computer exporting.</span></span> <span data-ttu-id="b228b-136">Quando si esegue il report, i documenti del report vengono caricati in un'area di archiviazione di Azure nel cloud Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b228b-136">When you the report, the report documents are uploaded to an Azure Storage area in the Microsoft cloud.</span></span>
  
1. <span data-ttu-id="b228b-137">Passare a [https://protection.office.com](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="b228b-137">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="b228b-138">Accedere a Office 365 usando l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="b228b-138">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="b228b-139">Nel riquadro sinistro del Centro sicurezza & conformità fare clic su ricerca \*\*\*\* \> **contenuto**ricerca.</span><span class="sxs-lookup"><span data-stu-id="b228b-139">In the left pane of the Security & Compliance Center, click **Search** \> **Content search**.</span></span>
    
4. <span data-ttu-id="b228b-140">Nella pagina **Ricerca contenuto** selezionare una ricerca.</span><span class="sxs-lookup"><span data-stu-id="b228b-140">On the **Content search** page, select a search.</span></span> 
    
5. <span data-ttu-id="b228b-141">Nel riquadro dei dettagli, in **Esporta rapporto in un computer**, fare clic su **genera report**.</span><span class="sxs-lookup"><span data-stu-id="b228b-141">In the details pane, under **Export report to a computer**, click **Generate report**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b228b-142">Se i risultati di una ricerca hanno più di 7 giorni, viene chiesto di aggiornare i risultati di ricerca.</span><span class="sxs-lookup"><span data-stu-id="b228b-142">If the results for a search are older than 7 days, you are prompted to update the search results.</span></span> <span data-ttu-id="b228b-143">In tal caso, annullare l'esportazione, fare clic su **Aggiorna i risultati della ricerca** nel riquadro dei dettagli per la ricerca selezionata e quindi avviare di nuovo l'esportazione del rapporto dopo l'aggiornamento dei risultati.</span><span class="sxs-lookup"><span data-stu-id="b228b-143">If this happens, cancel the export, click **Update search results** in the details pane for the selected search, and then start the report export again after the results are updated.</span></span> 
  
6. <span data-ttu-id="b228b-144">Nella pagina **Esporta un report** , in **Includi questi elementi della ricerca**, scegliere una delle seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="b228b-144">On the **Export a report** page, under **Include these items from the search**, choose one of the following options:</span></span>
    
    - <span data-ttu-id="b228b-145">Esportare solo gli elementi indicizzati</span><span class="sxs-lookup"><span data-stu-id="b228b-145">Export only indexed items</span></span>
    
    - <span data-ttu-id="b228b-146">Esportare gli elementi indicizzati e non</span><span class="sxs-lookup"><span data-stu-id="b228b-146">Export indexed and unindexed items</span></span>
    
    - <span data-ttu-id="b228b-147">Esportare solo gli elementi non indicizzati</span><span class="sxs-lookup"><span data-stu-id="b228b-147">Export only unindexed items</span></span>
    
    <span data-ttu-id="b228b-148">Per ulteriori informazioni sugli elementi non indicizzati, vedere [elementi indicizzati parzialmente nella ricerca contenuto](partially-indexed-items-in-content-search.md).</span><span class="sxs-lookup"><span data-stu-id="b228b-148">For more information about unindexed items, see [Partially indexed items in Content Search](partially-indexed-items-in-content-search.md).</span></span>
    
7. <span data-ttu-id="b228b-149">Scegliere di includere le statistiche di ricerca per tutte le versioni dei documenti di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b228b-149">Choose to include search statistics for all versions of SharePoint documents.</span></span> <span data-ttu-id="b228b-150">Questa opzione viene visualizzata solo se le origini di contenuto della ricerca includono i siti di SharePoint o OneDrive for business.</span><span class="sxs-lookup"><span data-stu-id="b228b-150">This option appears only if the content sources of the search include SharePoint or OneDrive for Business sites.</span></span>
    
8. <span data-ttu-id="b228b-151">Fare clic su **genera report**.</span><span class="sxs-lookup"><span data-stu-id="b228b-151">Click **Generate report**.</span></span>
    
    <span data-ttu-id="b228b-152">Il report dei risultati della ricerca è pronto per il download, il che significa che i documenti del rapporto verranno caricati nell'area di archiviazione di Azure nel cloud Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b228b-152">The search results report is prepared for downloading, which means the report documents will be uploaded to the Azure Storage area in the Microsoft cloud.</span></span> <span data-ttu-id="b228b-153">Quando il report è pronto per il download, il collegamento del **rapporto di download** viene visualizzato in **Esporta rapporto in un computer** nel riquadro dei dettagli.</span><span class="sxs-lookup"><span data-stu-id="b228b-153">When the report is ready for download, the **Download report** link is displayed under **Export report to a computer** in the details pane.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="b228b-154">È inoltre possibile esportare un report per una ricerca di contenuto associata a un caso di eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="b228b-154">You can also export a report for a Content Search that's associated with an eDiscovery case.</span></span> <span data-ttu-id="b228b-155">A tale scopo, accedere a **eDiscovery** \> **eDiscovery**, selezionare un caso e fare clic su **modifica** ![icona](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)modifica.</span><span class="sxs-lookup"><span data-stu-id="b228b-155">To do this, go to **eDiscovery** \> **eDiscovery**, select a case, and click **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span> <span data-ttu-id="b228b-156">Nella pagina **ricerche** selezionare una ricerca e **quindi fare clic su** ![Esporta esportazione dei risultati della ricerca](../media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \> **l'icona Esporta un report**.</span><span class="sxs-lookup"><span data-stu-id="b228b-156">On the **Searches** page, select a search, and then click **Export** ![Export search results icon](../media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \> **Export a report**.</span></span> 
  
## <a name="step-2-download-the-report"></a><span data-ttu-id="b228b-157">Passaggio 2: scaricare il report</span><span class="sxs-lookup"><span data-stu-id="b228b-157">Step 2: Download the report</span></span>

<span data-ttu-id="b228b-158">Il passaggio successivo consiste nel scaricare il report dall'area di archiviazione di Azure nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="b228b-158">The next step is to download the report from the Azure Storage area to your local computer.</span></span>
  
1. <span data-ttu-id="b228b-159">Nel riquadro dei dettagli per la ricerca per la quale è stato generato il report, in **Esporta rapporto in un computer**, fare clic su **Scarica report**.</span><span class="sxs-lookup"><span data-stu-id="b228b-159">In the details pane for the search that you generated the report for, under **Export report to a computer**, click **Download report**.</span></span>
    
    <span data-ttu-id="b228b-160">Viene visualizzata la pagina **download report** che contiene le seguenti informazioni sul rapporto scaricato nel computer.</span><span class="sxs-lookup"><span data-stu-id="b228b-160">The **Download report** page is displayed and contains the following information about the report that's downloaded to your computer.</span></span> 
    
    - <span data-ttu-id="b228b-161">Il numero di elementi che verranno scaricati.</span><span class="sxs-lookup"><span data-stu-id="b228b-161">The number of items that will be downloaded.</span></span>
    
    - <span data-ttu-id="b228b-162">La dimensione totale stimata degli elementi che verranno scaricati.</span><span class="sxs-lookup"><span data-stu-id="b228b-162">The estimated total size of the items that will be downloaded.</span></span>
    
    - <span data-ttu-id="b228b-163">Se gli elementi esportati saranno indicizzati o non indicizzati.</span><span class="sxs-lookup"><span data-stu-id="b228b-163">Whether indexed or unindexed will be exported.</span></span> <span data-ttu-id="b228b-164">Gli elementi non indicizzati sono elementi che hanno un formato riconosciuto, sono crittografati o non sono stati indicizzati per altri motivi.</span><span class="sxs-lookup"><span data-stu-id="b228b-164">Unindexed items are items that have a recognized format, are encrypted, or weren't indexed for other reasons.</span></span>
    
    - <span data-ttu-id="b228b-165">Se verranno scaricate le versioni dei documenti di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b228b-165">Whether versions of SharePoint documents will be downloaded.</span></span>
    
    - <span data-ttu-id="b228b-166">Lo stato del processo di esportazione del report.</span><span class="sxs-lookup"><span data-stu-id="b228b-166">The status of the report export process.</span></span> <span data-ttu-id="b228b-167">È possibile iniziare a scaricare il report anche se la preparazione del report non è stata completata.</span><span class="sxs-lookup"><span data-stu-id="b228b-167">You can start downloading the report even if the preparation of the report isn't complete.</span></span>
    
2. <span data-ttu-id="b228b-168">In **Chiave di esportazione**, fare clic su **Copia negli Appunti**.</span><span class="sxs-lookup"><span data-stu-id="b228b-168">Under **Export key**, click **Copy to clipboard**.</span></span> <span data-ttu-id="b228b-169">È possibile utilizzare questa chiave nel passaggio 5 per scaricare il report.</span><span class="sxs-lookup"><span data-stu-id="b228b-169">You use this key in step 5 to download the report.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="b228b-170">Poiché tutti gli utenti possono installare e avviare lo strumento di esportazione di eDiscovery e quindi utilizzare questa chiave per scaricare il report di ricerca, assicurarsi di prendere precauzioni per proteggere questa chiave come se si proteggessero le password o altre informazioni relative alla sicurezza.</span><span class="sxs-lookup"><span data-stu-id="b228b-170">Because anyone can install and start the eDiscovery Export tool, and then use this key to download the search report, be sure to take precautions to protect this key just like you would protect passwords or other security-related information.</span></span> 
  
3. <span data-ttu-id="b228b-171">Fare clic su **download report**.</span><span class="sxs-lookup"><span data-stu-id="b228b-171">Click **Download report**.</span></span>
    
4. <span data-ttu-id="b228b-172">Se viene richiesto di installare lo **strumento di esportazione di MicrosoftOffice 365 eDiscovery**, fare clic su **Installa**.</span><span class="sxs-lookup"><span data-stu-id="b228b-172">If you're prompted to install the **MicrosoftOffice 365 eDiscovery Export Tool**, click **Install**.</span></span>
    
5. <span data-ttu-id="b228b-173">Nello **Strumento di esportazione eDiscovery**, incollare la chiave di esportazione copiata nel passaggio 2 nella casella appropriata.</span><span class="sxs-lookup"><span data-stu-id="b228b-173">In the **eDiscovery Export Tool**, paste the export key that you copied in step 2 in the appropriate box.</span></span>
    
6. <span data-ttu-id="b228b-174">Fare clic su **Sfoglia** per specificare il percorso in cui si desidera scaricare il report.</span><span class="sxs-lookup"><span data-stu-id="b228b-174">Click **Browse** to specify the location where you want to download the report.</span></span> 
    
7. <span data-ttu-id="b228b-175">Fare clic su **Avvia** per scaricare i risultati della ricerca nel computer.</span><span class="sxs-lookup"><span data-stu-id="b228b-175">Click **Start** to download the search results to your computer.</span></span> 
    
    <span data-ttu-id="b228b-176">Lo **Strumento di esportazione eDiscovery** consente di visualizzare informazioni sullo stato delle informazioni relative al processo di esportazione, incluso il numero stimato (e le dimensioni) degli elementi rimanenti da scaricare.</span><span class="sxs-lookup"><span data-stu-id="b228b-176">The **eDiscovery Export Tool** displays status information about the export process, including an estimate of the number (and size) of the remaining items to be downloaded.</span></span> <span data-ttu-id="b228b-177">Al termine del processo di esportazione, è possibile accedere ai file nel percorso in cui sono stati scaricati.</span><span class="sxs-lookup"><span data-stu-id="b228b-177">When the export process is complete, you can access the files in the location where they were downloaded.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="b228b-178">È possibile scaricare il report per una ricerca di contenuto associata a un caso di eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="b228b-178">You can download the report for a Content Search that's associated with an eDiscovery case.</span></span> <span data-ttu-id="b228b-179">A tale scopo, accedere a **eDiscovery** \> **eDiscovery**, selezionare un caso e fare clic su **modifica** ![icona](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)modifica.</span><span class="sxs-lookup"><span data-stu-id="b228b-179">To do this, go to **eDiscovery** \> **eDiscovery**, select a case, and click **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span> <span data-ttu-id="b228b-180">Nella pagina **esportazioni** selezionare l'esportazione di un report e quindi fare clic su **Scarica report** nel riquadro dei dettagli.</span><span class="sxs-lookup"><span data-stu-id="b228b-180">On the **Exports** page, select an report export, and then click **Download report** in the details pane.</span></span> 
  
## <a name="whats-included-in-the-report"></a><span data-ttu-id="b228b-181">Elementi inclusi nel report</span><span class="sxs-lookup"><span data-stu-id="b228b-181">What's included in the report</span></span>

<span data-ttu-id="b228b-182">Quando si genera ed esporta un report sui risultati di una ricerca di contenuto, vengono scaricati i documenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="b228b-182">When you generate and export a report about the results of a Content Search, the following documents are downloaded:</span></span>
  
- <span data-ttu-id="b228b-183">**Riepilogo esportazione:** Documento di Excel che contiene un riepilogo dell'esportazione.</span><span class="sxs-lookup"><span data-stu-id="b228b-183">**Export Summary:** An Excel document that contains a summary of the export.</span></span> <span data-ttu-id="b228b-184">Sono incluse informazioni quali il numero di origini di contenuto di cui è stata eseguita la ricerca, il numero di risultati di ricerca di ogni percorso del contenuto, il numero stimato di elementi, il numero effettivo di elementi che verrebbero esportati e le dimensioni stimate e effettive degli elementi. che verrebbe esportato.</span><span class="sxs-lookup"><span data-stu-id="b228b-184">This includes information such as the number of content sources that were searched, the number of search results from each content location, the estimated number of items, the actual number of items that would be exported, and the estimated and actual size of items that would be exported.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="b228b-185">Se si includono gli elementi non indicizzati durante l'esportazione del report, il numero di elementi non indicizzati viene incluso nel numero totale di risultati della ricerca stimati e nel numero totale di risultati della ricerca scaricati (se si desidera esportare i risultati della ricerca) elencati nel Esporta rapporto riepilogativo.</span><span class="sxs-lookup"><span data-stu-id="b228b-185">If you include unindexed items when exporting the report, the number of unindexed items are included in the total number of estimated search results and in the total number of downloaded search results (if you were to export the search results) that are listed in the Export Summary report.</span></span> <span data-ttu-id="b228b-186">In altre parole, il numero totale di elementi che verrebbero scaricati è uguale al numero totale di risultati stimati e al numero totale di elementi non indicizzati.</span><span class="sxs-lookup"><span data-stu-id="b228b-186">In other words, the total number of items that would be downloaded is equal to the total number of estimated results and the total number of unindexed items.</span></span> 
  
- <span data-ttu-id="b228b-187">**Manifesto:** File manifesto (in formato XML) che contiene informazioni su ogni elemento incluso nei risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="b228b-187">**Manifest:** A manifest file (in XML format) that contains information about each item included in the search results.</span></span> 
    
- <span data-ttu-id="b228b-188">**Risultati:** Documento di Excel che contiene una riga contenente informazioni su ogni elemento indicizzato che verrebbe esportato con i risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="b228b-188">**Results:** An Excel document that contains a row with information about each indexed item that would be exported with the search results.</span></span> <span data-ttu-id="b228b-189">Per la posta elettronica, il log dei risultati contiene informazioni su ogni messaggio, tra cui:</span><span class="sxs-lookup"><span data-stu-id="b228b-189">For email, the result log contains information about each message, including:</span></span> 
    
  - <span data-ttu-id="b228b-190">Il percorso del messaggio nella cassetta postale di origine (e se il messaggio è nella cassetta postale principale o di archiviazione).</span><span class="sxs-lookup"><span data-stu-id="b228b-190">The location of the message in the source mailbox (including whether the message is in the primary or archive mailbox).</span></span>
    
  - <span data-ttu-id="b228b-191">La data in cui è stato inviato o ricevuto il messaggio.</span><span class="sxs-lookup"><span data-stu-id="b228b-191">The date the message was sent or received.</span></span>
    
  - <span data-ttu-id="b228b-192">La riga dell'oggetto del messaggio.</span><span class="sxs-lookup"><span data-stu-id="b228b-192">The Subject line from the message.</span></span>
    
  - <span data-ttu-id="b228b-193">Il mittente e i destinatari del messaggio.</span><span class="sxs-lookup"><span data-stu-id="b228b-193">The sender and recipients of the message.</span></span>
    
    <span data-ttu-id="b228b-194">Per i documenti provenienti da siti di SharePoint e OneDrive for business, il registro dei risultati contiene informazioni su ogni documento, tra cui:</span><span class="sxs-lookup"><span data-stu-id="b228b-194">For documents from SharePoint and OneDrive for Business sites, the Results log contains information about each document, including:</span></span>
    
  - <span data-ttu-id="b228b-195">L'URL per il documento.</span><span class="sxs-lookup"><span data-stu-id="b228b-195">The URL for the document.</span></span>
    
  - <span data-ttu-id="b228b-196">L’URL per la raccolta di siti in cui si trova il documento.</span><span class="sxs-lookup"><span data-stu-id="b228b-196">The URL for the site collection where the document is located.</span></span>
    
  - <span data-ttu-id="b228b-197">La data dell'ultima modifica al documento.</span><span class="sxs-lookup"><span data-stu-id="b228b-197">The date that the document was last modified.</span></span>
    
  - <span data-ttu-id="b228b-198">Il nome del documento (che si trova nella colonna Oggetto nel log dei risultati).</span><span class="sxs-lookup"><span data-stu-id="b228b-198">The name of the document (which is located in the Subject column in the result log).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b228b-199">Il numero di righe del rapporto **risultati** deve essere uguale al numero totale di risultati della ricerca meno il numero totale di elementi elencati nel rapporto **elementi non indicizzati** .</span><span class="sxs-lookup"><span data-stu-id="b228b-199">The number of rows in the **Results** report should be equal to the total number of search results minus the total number of items listed in the **Unindexed Items** report.</span></span> 
  
- <span data-ttu-id="b228b-200">**Elementi non indicizzati:** Documento di Excel che contiene informazioni su eventuali elementi non indicizzati inclusi nei risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="b228b-200">**Unindexed Items:** An Excel document that contains information about any unindexed items included in the search results.</span></span> <span data-ttu-id="b228b-201">Se non si includono gli elementi non indicizzati durante la generazione del report dei risultati della ricerca, il report verrà comunque scaricato, ma sarà vuoto.</span><span class="sxs-lookup"><span data-stu-id="b228b-201">If you don't include unindexed items when you generate the search results report, this report will still be downloaded, but will be empty.</span></span>
