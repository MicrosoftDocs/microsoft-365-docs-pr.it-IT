---
title: Risoluzione dei problemi comuni di eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Informazioni sui passaggi di base per la risoluzione dei problemi che è possibile eseguire per risolvere i problemi comuni in Office 365 eDiscovery.
siblings_only: true
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a867ed2e55c73fe4bbd890273d78cf57f4bfbd2c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926546"
---
# <a name="investigate-troubleshoot-and-resolve-common-ediscovery-issues"></a><span data-ttu-id="1946e-103">Analizzare, risolvere e risolvere i problemi comuni di eDiscovery</span><span class="sxs-lookup"><span data-stu-id="1946e-103">Investigate, troubleshoot, and resolve common eDiscovery issues</span></span>

<span data-ttu-id="1946e-104">In questo argomento vengono illustrati i passaggi di base per la risoluzione dei problemi che è possibile eseguire per identificare e risolvere i problemi che possono verificarsi durante una ricerca eDiscovery o in un altro punto del processo di eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="1946e-104">This topic covers basic troubleshooting steps you can take to identify and resolve issues you may encounter during an eDiscovery search or elsewhere in the eDiscovery process.</span></span> <span data-ttu-id="1946e-105">La risoluzione di alcuni di questi scenari richiede assistenza da parte del supporto tecnico Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1946e-105">Resolving some of these scenarios requires help from Microsoft Support.</span></span> <span data-ttu-id="1946e-106">Le informazioni su quando contattare il supporto Tecnico Microsoft sono incluse nei passaggi di risoluzione.</span><span class="sxs-lookup"><span data-stu-id="1946e-106">Information on when to contact Microsoft Support is included in the resolution steps.</span></span>

## <a name="errorissue-ambiguous-location"></a><span data-ttu-id="1946e-107">Errore/problema: percorso ambiguo</span><span class="sxs-lookup"><span data-stu-id="1946e-107">Error/issue: Ambiguous location</span></span>

<span data-ttu-id="1946e-108">Se si tenta di aggiungere la posizione della cassetta postale dell'utente per la ricerca e sono presenti oggetti duplicati o in conflitto con lo stesso ID utente nella directory di Exchange Online Protection (EOP), viene visualizzato questo errore: `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous` .</span><span class="sxs-lookup"><span data-stu-id="1946e-108">If you try to add user's mailbox location to search and there are duplicate or conflicting objects with the same userID in the Exchange Online Protection (EOP) directory, you receive this error: `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous`.</span></span>

### <a name="resolution"></a><span data-ttu-id="1946e-109">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="1946e-109">Resolution</span></span>

<span data-ttu-id="1946e-110">Verificare la presenza di utenti duplicati o lista di distribuzione con lo stesso ID utente.</span><span class="sxs-lookup"><span data-stu-id="1946e-110">Check for duplicate users or distribution list with the same user ID.</span></span>

1. <span data-ttu-id="1946e-111">Connettersi [a PowerShell & Centro sicurezza e conformità](/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="1946e-111">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="1946e-112">Eseguire il comando seguente per recuperare tutte le istanze del nome utente:</span><span class="sxs-lookup"><span data-stu-id="1946e-112">Run the following command to retrieve all instances of the username:</span></span>

    ```powershell
    Get-Recipient <username>
    ```

   <span data-ttu-id="1946e-113">L'output per "useralias@contoso.com" è simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="1946e-113">The output for 'useralias@contoso.com' would be similar to the following:</span></span>

   > 
   > |<span data-ttu-id="1946e-114">Nome</span><span class="sxs-lookup"><span data-stu-id="1946e-114">Name</span></span>|<span data-ttu-id="1946e-115">RecipientType</span><span class="sxs-lookup"><span data-stu-id="1946e-115">RecipientType</span></span>|
   > |---|---|
   > |<span data-ttu-id="1946e-116">Alias, Utente</span><span class="sxs-lookup"><span data-stu-id="1946e-116">Alias, User</span></span>|<span data-ttu-id="1946e-117">MailUser</span><span class="sxs-lookup"><span data-stu-id="1946e-117">MailUser</span></span>|
   > |<span data-ttu-id="1946e-118">Alias, Utente</span><span class="sxs-lookup"><span data-stu-id="1946e-118">Alias, User</span></span>|<span data-ttu-id="1946e-119">Utente</span><span class="sxs-lookup"><span data-stu-id="1946e-119">User</span></span>|

3. <span data-ttu-id="1946e-120">Se vengono restituiti più utenti, individuare e correggere l'oggetto in conflitto.</span><span class="sxs-lookup"><span data-stu-id="1946e-120">If multiple users are returned, locate and fix the conflicting object.</span></span>

## <a name="errorissue-search-fails-on-specific-locations"></a><span data-ttu-id="1946e-121">Errore/problema: la ricerca ha esito negativo in posizioni specifiche</span><span class="sxs-lookup"><span data-stu-id="1946e-121">Error/issue: Search fails on specific locations</span></span>

<span data-ttu-id="1946e-122">Una ricerca di contenuto o eDiscovery può produrre l'errore seguente: `This search completed with (#) errors.  Would you like to retry the search on the failed locations?`</span><span class="sxs-lookup"><span data-stu-id="1946e-122">An eDiscovery or content search may yield the following error: `This search completed with (#) errors.  Would you like to retry the search on the failed locations?`</span></span>

![Schermata di errore della posizione specifica della ricerca non riesce](../media/edisc-tshoot-specific-location-search-fails.png)

### <a name="resolution"></a><span data-ttu-id="1946e-124">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="1946e-124">Resolution</span></span>

<span data-ttu-id="1946e-125">Se viene visualizzato questo errore, è consigliabile verificare i percorsi non riusciti nella ricerca e quindi eseguire di nuovo la ricerca solo nei percorsi non riusciti.</span><span class="sxs-lookup"><span data-stu-id="1946e-125">If you receive this error, we recommend that you verify the locations that failed in the search  then rerun the search only on the failed locations.</span></span>

1. <span data-ttu-id="1946e-126">Connettersi [a PowerShell & Centro](/powershell/exchange/connect-to-scc-powershell) sicurezza e conformità ed eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="1946e-126">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and then run the following command:</span></span>

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. <span data-ttu-id="1946e-127">Dall'output di PowerShell, visualizzare le posizioni non riuscite nel campo degli errori o dai dettagli sullo stato nell'errore dall'output della ricerca.</span><span class="sxs-lookup"><span data-stu-id="1946e-127">From the PowerShell output, view the failed locations in the errors field or from the status details in the error from the search output.</span></span>

3. <span data-ttu-id="1946e-128">Ritentare la ricerca eDiscovery solo nei percorsi con errore.</span><span class="sxs-lookup"><span data-stu-id="1946e-128">Retry the eDiscovery search on the failed locations only.</span></span>

4. <span data-ttu-id="1946e-129">Se si continua a ricevere questi errori, vedere [Riprovare](/Office365/SecurityCompliance/retry-failed-content-search) percorsi non riusciti per ulteriori procedure di risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="1946e-129">If you continue to receive these errors, see [Retry failed locations](/Office365/SecurityCompliance/retry-failed-content-search) for more troubleshooting steps.</span></span>

## <a name="errorissue-file-not-found"></a><span data-ttu-id="1946e-130">Errore/problema: file non trovato</span><span class="sxs-lookup"><span data-stu-id="1946e-130">Error/issue: File not found</span></span>

<span data-ttu-id="1946e-131">Quando si esegue una ricerca eDiscovery che include posizioni di SharePoint Online e One Drive For Business, è possibile che venga visualizzato l'errore anche se il file si `File Not Found` trova nel sito.</span><span class="sxs-lookup"><span data-stu-id="1946e-131">When running an eDiscovery search that includes SharePoint Online and One Drive For Business locations, you may receive the error `File Not Found` although the file is located on the site.</span></span> <span data-ttu-id="1946e-132">Questo errore verrà visualizzato negli avvisi di esportazione e errors.csv o ignorato items.csv.</span><span class="sxs-lookup"><span data-stu-id="1946e-132">This error will be in the export warnings and errors.csv or skipped items.csv.</span></span> <span data-ttu-id="1946e-133">Ciò può verificarsi se non è possibile trovare il file nel sito o se l'indice non è aggiornato.</span><span class="sxs-lookup"><span data-stu-id="1946e-133">This may occur if the file can't be found on the site or if the index is out of date.</span></span> <span data-ttu-id="1946e-134">Ecco il testo di un errore effettivo (con enfasi aggiunta).</span><span class="sxs-lookup"><span data-stu-id="1946e-134">Here's the text of an actual error (with emphasis added).</span></span>

> <span data-ttu-id="1946e-135">28.06.2019 10:02:19_FailedToExportItem_Failed per scaricare il contenuto.</span><span class="sxs-lookup"><span data-stu-id="1946e-135">28.06.2019 10:02:19_FailedToExportItem_Failed to download content.</span></span> <span data-ttu-id="1946e-136">Ulteriori informazioni di diagnostica: Microsoft.Office.Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure: Impossibile scaricare dal contenuto 6ea52149-91cd-4965-b5bb-82ca6a3ec9be di tipo Document.</span><span class="sxs-lookup"><span data-stu-id="1946e-136">Additional diagnostic info : Microsoft.Office.Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure: Failed to download from content 6ea52149-91cd-4965-b5bb-82ca6a3ec9be of type Document.</span></span> <span data-ttu-id="1946e-137">ID correlazione: 3bd84722-937b-4c23-b61b-08d6fba9ec32.</span><span class="sxs-lookup"><span data-stu-id="1946e-137">Correlation Id: 3bd84722-937b-4c23-b61b-08d6fba9ec32.</span></span> <span data-ttu-id="1946e-138">ServerErrorCode: -2147024894 ---> Microsoft.SharePoint.Client.ServerException: ***File non trovato.***</span><span class="sxs-lookup"><span data-stu-id="1946e-138">ServerErrorCode: -2147024894 ---> Microsoft.SharePoint.Client.ServerException: ***File Not Found***.</span></span> <span data-ttu-id="1946e-139">at Microsoft.SharePoint.Client.ClientRequest.ProcessResponseStream(Stream responseStream) at Microsoft.SharePoint.Client.ClientRequest.ProcessResponse() --- End of inner exception stack trace ---</span><span class="sxs-lookup"><span data-stu-id="1946e-139">at Microsoft.SharePoint.Client.ClientRequest.ProcessResponseStream(Stream responseStream) at Microsoft.SharePoint.Client.ClientRequest.ProcessResponse() --- End of inner exception stack trace ---</span></span>

### <a name="resolution"></a><span data-ttu-id="1946e-140">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="1946e-140">Resolution</span></span>

1. <span data-ttu-id="1946e-141">Controllare il percorso identificato nella ricerca per verificare che il percorso del file sia corretto e aggiunto nei percorsi di ricerca.</span><span class="sxs-lookup"><span data-stu-id="1946e-141">Check location identified in the search to ensure the that the location of the file is correct and added in the search locations.</span></span>

2. <span data-ttu-id="1946e-142">Utilizzare le procedure descritte in Richiedere manualmente la ricerca per indicizzazione e la reindicizzazione di un [sito,](/sharepoint/crawl-site-content) di una raccolta o di un elenco per reindicizzare il sito.</span><span class="sxs-lookup"><span data-stu-id="1946e-142">Use the procedures at [Manually request crawling and re-indexing of a site, a library, or a list](/sharepoint/crawl-site-content) to reindex the site.</span></span>

## <a name="errorissue-search-fails-because-recipient-is-not-found"></a><span data-ttu-id="1946e-143">Errore/problema: la ricerca ha esito negativo perché il destinatario non è stato trovato</span><span class="sxs-lookup"><span data-stu-id="1946e-143">Error/issue: Search fails because recipient is not found</span></span>

<span data-ttu-id="1946e-144">Una ricerca eDiscovery ha esito negativo con l'errore `recipient not found` .</span><span class="sxs-lookup"><span data-stu-id="1946e-144">An eDiscovery search fails with error the `recipient not found`.</span></span> <span data-ttu-id="1946e-145">Questo errore può verificarsi se non è possibile trovare l'oggetto utente in Exchange Online Protection (EOP) perché l'oggetto non è stato sincronizzato.</span><span class="sxs-lookup"><span data-stu-id="1946e-145">This error may occur if the user object cannot be found in Exchange Online Protection (EOP) because the object has not synced.</span></span>

### <a name="resolution"></a><span data-ttu-id="1946e-146">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="1946e-146">Resolution</span></span>

1. <span data-ttu-id="1946e-147">Connettersi [a PowerShell di Exchange Online.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="1946e-147">Connect to [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="1946e-148">Eseguire il comando seguente per verificare se l'utente è sincronizzato con Exchange Online Protection:</span><span class="sxs-lookup"><span data-stu-id="1946e-148">Run the following command to check if the user is synced to Exchange Online Protection:</span></span>

   ```powershell
   Get-Recipient <userId> | FL
   ```

3. <span data-ttu-id="1946e-149">Deve essere presente un oggetto utente di posta per la domanda dell'utente.</span><span class="sxs-lookup"><span data-stu-id="1946e-149">There should be a mail user object for the user question.</span></span> <span data-ttu-id="1946e-150">Se non viene restituito alcun valore, analizzare l'oggetto utente.</span><span class="sxs-lookup"><span data-stu-id="1946e-150">If nothing is returned, investigate the user object.</span></span> <span data-ttu-id="1946e-151">Contattare il supporto tecnico Microsoft se l'oggetto non può essere sincronizzato.</span><span class="sxs-lookup"><span data-stu-id="1946e-151">Contact Microsoft Support if the object can't be synced.</span></span>

## <a name="errorissue-exporting-search-results-is-slow"></a><span data-ttu-id="1946e-152">Errore/problema: l'esportazione dei risultati della ricerca è lenta</span><span class="sxs-lookup"><span data-stu-id="1946e-152">Error/issue: Exporting search results is slow</span></span>

<span data-ttu-id="1946e-153">Quando si esportano i risultati della ricerca da eDiscovery o Ricerca contenuto nel Centro sicurezza e conformità, il download richiede più tempo del previsto.</span><span class="sxs-lookup"><span data-stu-id="1946e-153">When exporting search results from eDiscovery or Content Search in the Security and Compliance center, the download takes longer than expected.</span></span>  <span data-ttu-id="1946e-154">Puoi controllare la quantità di dati da scaricare ed eventualmente aumentare la velocità di esportazione.</span><span class="sxs-lookup"><span data-stu-id="1946e-154">You can check to see the amount of data to be download and possibly increase the export speed.</span></span>

### <a name="resolution"></a><span data-ttu-id="1946e-155">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="1946e-155">Resolution</span></span>

1. <span data-ttu-id="1946e-156">Connettersi [a PowerShell & Centro](/powershell/exchange/connect-to-scc-powershell) sicurezza e conformità ed eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="1946e-156">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and then run the following command:</span></span>

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. <span data-ttu-id="1946e-157">Trova la quantità di dati da scaricare nei parametri SearchResults e SearchStatistics.</span><span class="sxs-lookup"><span data-stu-id="1946e-157">Find the amount of data to be downloaded in the SearchResults and SearchStatistics parameters.</span></span>

3. <span data-ttu-id="1946e-158">Eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="1946e-158">Run the following command:</span></span>

   ```powershell
   Get-ComplianceSearchAction | FL
   ```

4. <span data-ttu-id="1946e-159">Nel campo dei risultati individuare i dati esportati e visualizzare gli eventuali errori riscontrati.</span><span class="sxs-lookup"><span data-stu-id="1946e-159">In the results field, find the data that has been exported and view any errors encountered.</span></span>

5. <span data-ttu-id="1946e-160">Verificare la presenza di eventuali errori nel file trace.log presente nella directory in cui è stato esportato il contenuto.</span><span class="sxs-lookup"><span data-stu-id="1946e-160">Check the trace.log file located in the directory that you exported the content to for any errors.</span></span>

6. <span data-ttu-id="1946e-161">Se si verificano ancora problemi, è consigliabile suddividere le ricerche che restituiscono un set di risultati di grandi dimensioni in ricerche più piccole.</span><span class="sxs-lookup"><span data-stu-id="1946e-161">If you still have issues, consider dividing searches that return a large set of results into smaller searches.</span></span> <span data-ttu-id="1946e-162">È ad esempio possibile utilizzare intervalli di date nelle query di ricerca per restituire un set più piccolo di risultati che possono essere scaricati più velocemente.</span><span class="sxs-lookup"><span data-stu-id="1946e-162">For example, you can use date ranges in search queries to return a smaller set of results that can be downloaded faster.</span></span>

## <a name="errorissue-internal-server-error-500-occurred"></a><span data-ttu-id="1946e-163">Errore/problema: "Errore interno del server (500) si è verificato"</span><span class="sxs-lookup"><span data-stu-id="1946e-163">Error/issue: "Internal server error (500) occurred"</span></span>

<span data-ttu-id="1946e-164">Quando si esegue una ricerca eDiscovery, se la ricerca continuamente non riesce con un errore simile a "Errore interno del server (500) si è verificato", potrebbe essere necessario eseguire di nuovo la ricerca solo in posizioni specifiche delle cassette postali.</span><span class="sxs-lookup"><span data-stu-id="1946e-164">When running an eDiscovery search, if the search continually fails with error similar to "Internal server error (500) occurred", you may need rerun the search only on specific mailbox locations.</span></span>

![Screenshot dell'errore interno del server 500](../media/edisc-tshoot-error-500.png)

### <a name="resolution"></a><span data-ttu-id="1946e-166">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="1946e-166">Resolution</span></span>

1. <span data-ttu-id="1946e-167">Suddividere la ricerca in ricerche più piccole ed eseguire di nuovo la ricerca.</span><span class="sxs-lookup"><span data-stu-id="1946e-167">Break the search into smaller searches and run the search again.</span></span>  <span data-ttu-id="1946e-168">Provare a utilizzare un intervallo di date più piccolo o limitare il numero di posizioni in cui si sta ricercando.</span><span class="sxs-lookup"><span data-stu-id="1946e-168">Try using a smaller date range or limit the number of locations being searched.</span></span>

2. <span data-ttu-id="1946e-169">Connettersi [a PowerShell & Centro](/powershell/exchange/connect-to-scc-powershell) sicurezza e conformità ed eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="1946e-169">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and then run the following command:</span></span>

   ```powershell Set-CaseHoldPolicy <policyname> -RetryDistribution
   Get-ComplianceSearch <searchname> | FL
   ```

3. <span data-ttu-id="1946e-170">Esaminare l'output per ottenere risultati ed errori.</span><span class="sxs-lookup"><span data-stu-id="1946e-170">Examine the output for results and errors.</span></span>

4. <span data-ttu-id="1946e-171">Esaminare il file trace.log.</span><span class="sxs-lookup"><span data-stu-id="1946e-171">Examine the trace.log file.</span></span> <span data-ttu-id="1946e-172">Si trova nella stessa cartella in cui sono stati esportati i risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="1946e-172">It's located  in the same folder that you exported the search results to.</span></span>

5. <span data-ttu-id="1946e-173">Contattare il Servizio Supporto Tecnico Clienti Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1946e-173">Contact Microsoft Support.</span></span>

## <a name="errorissue-holds-dont-sync"></a><span data-ttu-id="1946e-174">Errore/problema: i blocchi non vengono sincronizzati</span><span class="sxs-lookup"><span data-stu-id="1946e-174">Error/issue: Holds don't sync</span></span>

<span data-ttu-id="1946e-175">Errore di distribuzione della sincronizzazione dei criteri di blocco del caso di eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="1946e-175">eDiscovery Case Hold Policy Sync Distribution error.</span></span> <span data-ttu-id="1946e-176">L'errore è:</span><span class="sxs-lookup"><span data-stu-id="1946e-176">The error reads:</span></span>

> <span data-ttu-id="1946e-177">"Risorse: la distribuzione del criterio richiede più tempo del previsto.</span><span class="sxs-lookup"><span data-stu-id="1946e-177">"Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="1946e-178">L'aggiornamento dello stato finale della distribuzione potrebbe richiedere altre 2 ore, quindi controllare di nuovo tra un paio d'ore."</span><span class="sxs-lookup"><span data-stu-id="1946e-178">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours."</span></span>

### <a name="resolution"></a><span data-ttu-id="1946e-179">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="1946e-179">Resolution</span></span>

1. <span data-ttu-id="1946e-180">Connettersi [a PowerShell & Centro](/powershell/exchange/connect-to-scc-powershell) sicurezza e conformità ed eseguire il comando seguente per un blocco caso di eDiscovery:</span><span class="sxs-lookup"><span data-stu-id="1946e-180">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and then run the following command for an eDiscovery case hold:</span></span>

   ```powershell
   Get-CaseHoldPolicy <policyname> - DistributionDetail | FL
   ```

    <span data-ttu-id="1946e-181">Per un criterio di conservazione, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="1946e-181">For a retention policy, run the following command:</span></span>

   ```powershell
   Get-RetentionCompliancePolicy <policyname> - DistributionDetail | FL
   ```

2. <span data-ttu-id="1946e-182">Esaminare il valore nel parametro DistributionDetail per verificare la presenza di errori simili ai seguenti:</span><span class="sxs-lookup"><span data-stu-id="1946e-182">Examine the value in the DistributionDetail parameter for errors like the following:</span></span>

   > <span data-ttu-id="1946e-183">Errore: risorse: la distribuzione del criterio richiede più tempo del previsto.</span><span class="sxs-lookup"><span data-stu-id="1946e-183">Error: Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="1946e-184">L'aggiornamento dello stato finale della distribuzione potrebbe richiedere altre 2 ore, quindi controllare di nuovo tra un paio d'ore."</span><span class="sxs-lookup"><span data-stu-id="1946e-184">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours."</span></span>

3. <span data-ttu-id="1946e-185">Provare a eseguire il parametro RetryDistribution sul criterio in questione:</span><span class="sxs-lookup"><span data-stu-id="1946e-185">Try running the RetryDistribution parameter on the policy in question:</span></span>

   <span data-ttu-id="1946e-186">Per i blocchi dei casi di eDiscovery:</span><span class="sxs-lookup"><span data-stu-id="1946e-186">For eDiscovery case holds:</span></span>

   ```powershell
   Set-CaseHoldPolicy <policyname> -RetryDistribution
   ```

   <span data-ttu-id="1946e-187">Per i criteri di conservazione:</span><span class="sxs-lookup"><span data-stu-id="1946e-187">For retention policies:</span></span>

   ```powershell
   Set-RetentionCompliancePolicy <policyname> -RetryDistribution
   ```

4. <span data-ttu-id="1946e-188">Contattare il Servizio Supporto Tecnico Clienti Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1946e-188">Contact Microsoft Support.</span></span>

## <a name="error-the-condition-specified-using-http-conditional-headers-is-not-met"></a><span data-ttu-id="1946e-189">Errore: "La condizione specificata tramite le intestazioni condizionali HTTP non è soddisfatta"</span><span class="sxs-lookup"><span data-stu-id="1946e-189">Error: "The condition specified using HTTP conditional header(s) is not met"</span></span>

<span data-ttu-id="1946e-190">Quando si scaricano i risultati della ricerca utilizzando lo strumento di esportazione di eDiscovery, è possibile che venga visualizzato l'errore seguente: Si tratta di un errore temporaneo, che in genere si verifica nel percorso di `System.Net.WebException: The remote server returned an error: (412) The condition specified using HTTP conditional header(s) is not met.` archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="1946e-190">When downloading search results using the eDiscovery Export Tool, it's possible you might receive the following error: `System.Net.WebException: The remote server returned an error: (412) The condition specified using HTTP conditional header(s) is not met.` This is transient error, which typically occurs in the Azure Storage location.</span></span>

### <a name="resolution"></a><span data-ttu-id="1946e-191">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="1946e-191">Resolution</span></span>

<span data-ttu-id="1946e-192">Per risolvere questo problema, ritentare [il download dei risultati della](export-search-results.md#step-2-download-the-search-results)ricerca, che riavvierà lo strumento di esportazione di eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="1946e-192">To resolve this issue, retry [downloading the search results](export-search-results.md#step-2-download-the-search-results), which will restart the eDiscovery Export Tool.</span></span>

## <a name="errorissue-downloaded-export-shows-no-results"></a><span data-ttu-id="1946e-193">Errore/problema: l'esportazione scaricata non mostra risultati</span><span class="sxs-lookup"><span data-stu-id="1946e-193">Error/issue: Downloaded export shows no results</span></span>

<span data-ttu-id="1946e-194">Dopo un'esportazione completata, il download completato tramite lo strumento di esportazione mostra zero file nei risultati.</span><span class="sxs-lookup"><span data-stu-id="1946e-194">After a successful export, the completed download via the export tool shows zero files in the results.</span></span>

### <a name="resolution"></a><span data-ttu-id="1946e-195">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="1946e-195">Resolution</span></span>

<span data-ttu-id="1946e-196">Si tratta di un problema sul lato client e per risolvere il problema, provare a eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="1946e-196">This is a client-side issue and in order to remediate it, please attempt the following steps:</span></span>

1. <span data-ttu-id="1946e-197">Prova a usare un altro client/computer per il download.</span><span class="sxs-lookup"><span data-stu-id="1946e-197">Try using another client/machine to download.</span></span>

2. <span data-ttu-id="1946e-198">Assicurati di eseguire il download in un'unità locale.</span><span class="sxs-lookup"><span data-stu-id="1946e-198">Make sure to download to a local drive.</span></span>

3. <span data-ttu-id="1946e-199">Verificare che il programma antivirus non sia in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="1946e-199">Make sure the virus scanner is not running.</span></span>

4. <span data-ttu-id="1946e-200">Assicurarsi che nessun'altra esportazione sia in download nella stessa cartella o in qualsiasi cartella padre.</span><span class="sxs-lookup"><span data-stu-id="1946e-200">Make sure that no other export is downloading to the same folder or any parent folder.</span></span>

5. <span data-ttu-id="1946e-201">Se i passaggi precedenti non sono stati esatti, disabilitare la compressione e la deduplicazione.</span><span class="sxs-lookup"><span data-stu-id="1946e-201">If the previous steps did not work, disable zipping and de-duplication.</span></span>

6. <span data-ttu-id="1946e-202">Se funziona, il problema è dovuto a un programma antivirus locale o a un problema del disco.</span><span class="sxs-lookup"><span data-stu-id="1946e-202">If this works then the issue is due to a local virus scanner or a disk issue.</span></span>