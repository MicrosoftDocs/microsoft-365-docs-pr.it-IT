---
title: Risoluzione dei problemi comuni relativi a eDiscovery
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Esaminare, risolvere i problemi e risolvere i problemi comuni in Office 365 eDiscovery.
siblings_only: true
ms.openlocfilehash: 0d411976ecf6adba9df1f75eb8a45409647b3e1a
ms.sourcegitcommit: c7f7ff463141f7d7f0970b64e5a04341db7e4fa8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/02/2019
ms.locfileid: "37378638"
---
# <a name="investigate-troubleshoot-and-resolve-common-ediscovery-issues"></a><span data-ttu-id="12fb2-103">Esaminare, risolvere i problemi e risolvere i problemi comuni relativi a eDiscovery</span><span class="sxs-lookup"><span data-stu-id="12fb2-103">Investigate, troubleshoot, and resolve common eDiscovery issues</span></span>

<span data-ttu-id="12fb2-104">In questo argomento vengono illustrati i passaggi di base per la risoluzione dei problemi che è possibile eseguire per identificare e risolvere i problemi che possono verificarsi durante una ricerca di eDiscovery o altrove nel processo di eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="12fb2-104">This topic covers basic troubleshooting steps you can take to identify and resolve issues you may encounter during an eDiscovery search or elsewhere in the eDiscovery process.</span></span> <span data-ttu-id="12fb2-105">La risoluzione di alcuni di questi scenari richiede assistenza da parte del supporto tecnico Microsoft.</span><span class="sxs-lookup"><span data-stu-id="12fb2-105">Resolving some of these scenarios requires help from Microsoft Support.</span></span> <span data-ttu-id="12fb2-106">Informazioni su quando contattare il supporto tecnico Microsoft è incluso nei passaggi di risoluzione.</span><span class="sxs-lookup"><span data-stu-id="12fb2-106">Information on when to contact Microsoft Support is included in the resolution steps.</span></span>

## <a name="errorissue-ambiguous-location"></a><span data-ttu-id="12fb2-107">Errore/problema: posizione ambigua</span><span class="sxs-lookup"><span data-stu-id="12fb2-107">Error/issue: Ambiguous location</span></span>

<span data-ttu-id="12fb2-108">Se si tenta di aggiungere la posizione della cassetta postale dell'utente alla ricerca e sono presenti oggetti duplicati o in conflitto con lo stesso userID nella directory di Exchange Online Protection (EOP), verrà visualizzato `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous`questo errore:.</span><span class="sxs-lookup"><span data-stu-id="12fb2-108">If you try to add user's mailbox location to search and there are duplicate or conflicting objects with the same userID in the Exchange Online Protection (EOP) directory, you will receive this error: `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous`.</span></span> 

### <a name="resolution"></a><span data-ttu-id="12fb2-109">Soluzione</span><span class="sxs-lookup"><span data-stu-id="12fb2-109">Resolution</span></span>

<span data-ttu-id="12fb2-110">Controllare gli utenti duplicati o la lista di distribuzione con lo stesso ID utente.</span><span class="sxs-lookup"><span data-stu-id="12fb2-110">Check for duplicate users or distribution list with the same user ID.</span></span>

1. <span data-ttu-id="12fb2-111">Connettersi a [PowerShell di Office 365 Security & Compliance Center](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="12fb2-111">Connect to [Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="12fb2-112">Recuperare tutte le istanze del nome utente, digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="12fb2-112">Retrieve all instances of the username, type:</span></span>

    ```powershell
    Get-Recipient <username>
    ```

<span data-ttu-id="12fb2-113">L'output per ' useralias@contoso.com ' sarebbe simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="12fb2-113">The output for 'useralias@contoso.com' would be similar to the following:</span></span>

> 
> |<span data-ttu-id="12fb2-114">Name</span><span class="sxs-lookup"><span data-stu-id="12fb2-114">Name</span></span>  |<span data-ttu-id="12fb2-115">RecipientType</span><span class="sxs-lookup"><span data-stu-id="12fb2-115">RecipientType</span></span>  |
> |---------|---------|
> |<span data-ttu-id="12fb2-116">Alias, utente</span><span class="sxs-lookup"><span data-stu-id="12fb2-116">Alias, User</span></span>     |<span data-ttu-id="12fb2-117">MailUser</span><span class="sxs-lookup"><span data-stu-id="12fb2-117">MailUser</span></span>         |
> |<span data-ttu-id="12fb2-118">Alias, utente</span><span class="sxs-lookup"><span data-stu-id="12fb2-118">Alias, User</span></span>     |<span data-ttu-id="12fb2-119">Utente</span><span class="sxs-lookup"><span data-stu-id="12fb2-119">User</span></span>         |

3. <span data-ttu-id="12fb2-120">Se vengono restituiti più utenti, individuare e correggere l'oggetto in conflitto.</span><span class="sxs-lookup"><span data-stu-id="12fb2-120">If multiple users are returned, locate and fix the conflicting object.</span></span>

## <a name="errorissue-search-fails-on-specific-locations"></a><span data-ttu-id="12fb2-121">Errore/problema: la ricerca ha esito negativo su percorsi specifici</span><span class="sxs-lookup"><span data-stu-id="12fb2-121">Error/issue: Search fails on specific locations</span></span>

<span data-ttu-id="12fb2-122">Un eDiscovery o una ricerca di contenuto può generare l'errore seguente:</span><span class="sxs-lookup"><span data-stu-id="12fb2-122">An eDiscovery or content search may yield the following error:</span></span>
><span data-ttu-id="12fb2-123">Questa ricerca è stata completata con gli errori (#).</span><span class="sxs-lookup"><span data-stu-id="12fb2-123">This search completed with (#) errors.</span></span>  <span data-ttu-id="12fb2-124">Si desidera riprovare la ricerca nelle posizioni non riuscite?</span><span class="sxs-lookup"><span data-stu-id="12fb2-124">Would you like to retry the search on the failed locations?</span></span>

![Posizione specifica di ricerca non riuscita screenshot di errore]( media/edisc-tshoot-specific-location-search-fails.png)

### <a name="resolution"></a><span data-ttu-id="12fb2-126">Soluzione</span><span class="sxs-lookup"><span data-stu-id="12fb2-126">Resolution</span></span>

<span data-ttu-id="12fb2-127">Se viene visualizzato questo errore, è consigliabile verificare che le posizioni non riuscite nella ricerca rieseguano la ricerca solo nelle posizioni non riuscite.</span><span class="sxs-lookup"><span data-stu-id="12fb2-127">If you receive this error, we recommend that you verify the locations that failed in the search  then rerun the search only on the failed locations.</span></span>

1. <span data-ttu-id="12fb2-128">Connettersi a [Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) e quindi immettere il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="12fb2-128">Connect to [Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) and then enter the following command:</span></span>

    ```powershell
    Get-ComplianceSearch <searchname> | FL 
    ```

2. <span data-ttu-id="12fb2-129">Nell'output di PowerShell, visualizzare le posizioni non riuscite nel campo errori o nei dettagli dello stato nell'errore dall'output di ricerca.</span><span class="sxs-lookup"><span data-stu-id="12fb2-129">From the PowerShell output, view the failed locations in the errors field or from the status details in the error from the search output.</span></span>

3. <span data-ttu-id="12fb2-130">Riprovare la ricerca di eDiscovery solo nelle posizioni non riuscite.</span><span class="sxs-lookup"><span data-stu-id="12fb2-130">Retry the eDiscovery search on the failed locations only.</span></span>

4. <span data-ttu-id="12fb2-131">Se si continua a ricevere questi errori, vedere [retry failed locations](https://docs.microsoft.com/en-us/Office365/SecurityCompliance/retry-failed-content-search) for more troubleshooting steps.</span><span class="sxs-lookup"><span data-stu-id="12fb2-131">If you continue to receive these errors, see [Retry failed locations](https://docs.microsoft.com/en-us/Office365/SecurityCompliance/retry-failed-content-search) for more troubleshooting steps.</span></span>

## <a name="errorissue-file-not-found"></a><span data-ttu-id="12fb2-132">Errore/problema: file non trovato</span><span class="sxs-lookup"><span data-stu-id="12fb2-132">Error/issue: File not found</span></span>

<span data-ttu-id="12fb2-133">Quando si esegue una ricerca di eDiscovery che include SharePoint Online e un'unità per le posizioni aziendali, è possibile `File Not Found` che venga visualizzato un errore anche se il file si trova nel sito.</span><span class="sxs-lookup"><span data-stu-id="12fb2-133">When running an eDiscovery search that includes SharePoint Online and One Drive For Business locations, you may receive the error `File Not Found` although the file is located on the site.</span></span> <span data-ttu-id="12fb2-134">Questo errore risulterà negli avvisi di esportazione e negli errori. csv o negli elementi. csv ignorati.</span><span class="sxs-lookup"><span data-stu-id="12fb2-134">This error will be in the export warnings and errors.csv or skipped items.csv.</span></span> <span data-ttu-id="12fb2-135">Ciò può verificarsi se il file non può essere posizionato nel sito o se l'indice non è aggiornato.</span><span class="sxs-lookup"><span data-stu-id="12fb2-135">This may occur if the file cannot be located on the site or the index is out of date.</span></span> <span data-ttu-id="12fb2-136">Di seguito è indicato il testo di un errore reale, con enfasi aggiunta.</span><span class="sxs-lookup"><span data-stu-id="12fb2-136">Here's the text of an actual error, with emphasis added.</span></span>
  
> <span data-ttu-id="12fb2-137">28.06.2019 10:02:19_FailedToExportItem_Failed per scaricare il contenuto.</span><span class="sxs-lookup"><span data-stu-id="12fb2-137">28.06.2019 10:02:19_FailedToExportItem_Failed to download content.</span></span> <span data-ttu-id="12fb2-138">Ulteriori informazioni di diagnostica: Microsoft. Office. compliance. EDiscovery. ExportWorker. Exceptions. ContentDownloadTemporaryFailure: failed to download from content 6ea52149-91CD-4965-b5bb-82ca6a3ec9be of Type Document.</span><span class="sxs-lookup"><span data-stu-id="12fb2-138">Additional diagnostic info : Microsoft.Office.Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure: Failed to download from content 6ea52149-91cd-4965-b5bb-82ca6a3ec9be of type Document.</span></span> <span data-ttu-id="12fb2-139">ID di correlazione: 3bd84722-937b-4c23-b61b-08d6fba9ec32.</span><span class="sxs-lookup"><span data-stu-id="12fb2-139">Correlation Id: 3bd84722-937b-4c23-b61b-08d6fba9ec32.</span></span> <span data-ttu-id="12fb2-140">ServerErrorCode:-2147024894---> Microsoft. SharePoint. client. ServerException: ***file non trovato***.</span><span class="sxs-lookup"><span data-stu-id="12fb2-140">ServerErrorCode: -2147024894 ---> Microsoft.SharePoint.Client.ServerException: ***File Not Found***.</span></span> <span data-ttu-id="12fb2-141">in Microsoft. SharePoint. client. ClientRequest. ProcessResponseStream (Stream responseStream) in Microsoft. SharePoint. client. ClientRequest. ProcessResponse ()---fine dell'analisi dello stack dell'eccezione interna---</span><span class="sxs-lookup"><span data-stu-id="12fb2-141">at Microsoft.SharePoint.Client.ClientRequest.ProcessResponseStream(Stream responseStream) at Microsoft.SharePoint.Client.ClientRequest.ProcessResponse() --- End of inner exception stack trace ---</span></span>

### <a name="resolution"></a><span data-ttu-id="12fb2-142">Soluzione</span><span class="sxs-lookup"><span data-stu-id="12fb2-142">Resolution</span></span>

1. <span data-ttu-id="12fb2-143">Controllare la posizione identificata nella ricerca per verificare che il percorso del file sia corretto e che sia stato aggiunto nei percorsi di ricerca.</span><span class="sxs-lookup"><span data-stu-id="12fb2-143">Check location identified in the search to ensure the that the location of the file is correct and added in the search locations.</span></span>

2. <span data-ttu-id="12fb2-144">Utilizzare le procedure per eseguire la ricerca per indicizzazione [e reindicizzazione manuale di un sito, una raccolta o un elenco](https://docs.microsoft.com/en-us/sharepoint/crawl-site-content) per reindicizzare il sito.</span><span class="sxs-lookup"><span data-stu-id="12fb2-144">Use the procedures at [Manually request crawling and re-indexing of a site, a library or a list](https://docs.microsoft.com/en-us/sharepoint/crawl-site-content) to re-index the site.</span></span>

## <a name="errorissue-search-fails-because-recipient-is-not-found"></a><span data-ttu-id="12fb2-145">Errore/problema: la ricerca ha esito negativo perché il destinatario non viene trovato</span><span class="sxs-lookup"><span data-stu-id="12fb2-145">Error/issue: Search fails because recipient is not found</span></span>

<span data-ttu-id="12fb2-146">Una ricerca di eDiscovery ha esito `recipient not found`negativo con errore.</span><span class="sxs-lookup"><span data-stu-id="12fb2-146">An eDiscovery search fails with error the `recipient not found`.</span></span> <span data-ttu-id="12fb2-147">Questo errore può verificarsi se l'oggetto utente non è disponibile in Exchange Online Protection (EOP) perché l'oggetto non è stato sincronizzato.</span><span class="sxs-lookup"><span data-stu-id="12fb2-147">This error may occur if the user object cannot be found in Exchange Online Protection (EOP) because the object has not synced.</span></span>

### <a name="resolution"></a><span data-ttu-id="12fb2-148">Soluzione</span><span class="sxs-lookup"><span data-stu-id="12fb2-148">Resolution</span></span>

1. <span data-ttu-id="12fb2-149">Connettersi a [PowerShell di Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="12fb2-149">Connect to [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="12fb2-150">Controllare se l'oggetto utente è sincronizzato con il tipo di protezione Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="12fb2-150">Check to see if the user object is synced to Exchange Online Protection type:</span></span>

    ```powershell
    Get-Recipient <userId> | FL
    ```

3. <span data-ttu-id="12fb2-151">Deve essere presente un oggetto utente di posta elettronica per la domanda dell'utente.</span><span class="sxs-lookup"><span data-stu-id="12fb2-151">There should be a mail user object for the user question.</span></span> <span data-ttu-id="12fb2-152">Se non viene restituito alcun valore, esaminare l'oggetto User.</span><span class="sxs-lookup"><span data-stu-id="12fb2-152">If nothing is returned, investigate the user object.</span></span> <span data-ttu-id="12fb2-153">Se l'oggetto non può essere sincronizzato, contattare il supporto tecnico Microsoft.</span><span class="sxs-lookup"><span data-stu-id="12fb2-153">Contact Microsoft Support if the object can't be synced.</span></span>

## <a name="errorissue-exporting-search-results-is-slow"></a><span data-ttu-id="12fb2-154">Errore/problema: l'esportazione dei risultati di ricerca è lenta</span><span class="sxs-lookup"><span data-stu-id="12fb2-154">Error/issue: Exporting search results is slow</span></span>

<span data-ttu-id="12fb2-155">Quando si esportano i risultati della ricerca da eDiscovery o ricerca contenuto nel centro sicurezza e conformità, il download richiede più tempo del previsto.</span><span class="sxs-lookup"><span data-stu-id="12fb2-155">When exporting search results from eDiscovery or Content Search in the Security and Compliance center, the download takes longer than expected.</span></span>  <span data-ttu-id="12fb2-156">È possibile controllare la quantità di dati da scaricare ed eventualmente aumentare la velocità di esportazione.</span><span class="sxs-lookup"><span data-stu-id="12fb2-156">You can check to see the amount of data to be download and possibly increase the export speed.</span></span>

### <a name="resolution"></a><span data-ttu-id="12fb2-157">Soluzione</span><span class="sxs-lookup"><span data-stu-id="12fb2-157">Resolution</span></span>

1.  <span data-ttu-id="12fb2-158">Provare a utilizzare i passaggi identificati nell'articolo [aumentare la velocità di download](https://docs.microsoft.com/en-us/office365/securitycompliance/increase-download-speeds-when-exporting-ediscovery-results).</span><span class="sxs-lookup"><span data-stu-id="12fb2-158">Try using the steps identified in the article [Increase Download Speeds](https://docs.microsoft.com/en-us/office365/securitycompliance/increase-download-speeds-when-exporting-ediscovery-results).</span></span>

2.  <span data-ttu-id="12fb2-159">In caso di problemi, connettersi a [Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) e quindi immettere il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="12fb2-159">If you still have issues, connect to [Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) and then enter the following command:</span></span>

    ```powershell
    Get-ComplianceSearch <searchname> | FL
    ```

4. <span data-ttu-id="12fb2-160">Individuare la quantità di dati da scaricare nei parametri SearchResults e SearchStatistics.</span><span class="sxs-lookup"><span data-stu-id="12fb2-160">Find the amount of data to be downloaded in the SearchResults and SearchStatistics parameters.</span></span>

5. <span data-ttu-id="12fb2-161">Immettere il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="12fb2-161">Enter the following command:</span></span>

   ```powershell
   Get-ComplianceSearchAction | FL
   ```

6. <span data-ttu-id="12fb2-162">Nel campo risultati individuare i dati che sono stati esportati e visualizzare gli eventuali errori riscontrati.</span><span class="sxs-lookup"><span data-stu-id="12fb2-162">In the results field, find the data that has been exported and view any errors encountered.</span></span>

7. <span data-ttu-id="12fb2-163">Controllare il file Trace. log che si trova nella directory in cui è stato esportato il contenuto per eventuali errori.</span><span class="sxs-lookup"><span data-stu-id="12fb2-163">Check the trace.log file located in the directory that you exported the content to for any errors.</span></span>

## <a name="errorissue-internal-server-error-500-occurred"></a><span data-ttu-id="12fb2-164">Errore/problema: "errore interno del server (500) si è verificato"</span><span class="sxs-lookup"><span data-stu-id="12fb2-164">Error/issue: "Internal server error (500) occurred"</span></span>

<span data-ttu-id="12fb2-165">Quando si esegue una ricerca eDiscovery, se la ricerca ha esito negativo con un errore simile a "Internal Server Error (500) si è verificato", potrebbe essere necessario eseguire nuovamente la ricerca solo su percorsi specifici per le cassette postali.</span><span class="sxs-lookup"><span data-stu-id="12fb2-165">When running an eDiscovery search, if the search continually fails with error similar to "Internal server error (500) occurred", you may need rerun the search only on specific mailbox locations.</span></span>

![Errore del server interno 500 screenshot](media/edisc-tshoot-error-500.png)

### <a name="resolution"></a><span data-ttu-id="12fb2-167">Soluzione</span><span class="sxs-lookup"><span data-stu-id="12fb2-167">Resolution</span></span>

1. <span data-ttu-id="12fb2-168">Suddividere la ricerca in ricerche più piccole ed eseguire di nuovo la ricerca.</span><span class="sxs-lookup"><span data-stu-id="12fb2-168">Break the search into smaller searches and run the search again.</span></span>  <span data-ttu-id="12fb2-169">Provare a utilizzare un intervallo di date più piccolo o limitare il numero di posizioni in cui è stata eseguita la ricerca.</span><span class="sxs-lookup"><span data-stu-id="12fb2-169">Try using a smaller date range or limit the number of locations being searched.</span></span>

2. <span data-ttu-id="12fb2-170">Connettersi a [Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) e quindi immettere il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="12fb2-170">Connect to [Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) and then enter the following command:</span></span>

    ```powershell
    Get-ComplianceSearch <searchname> | FL
    ```

3. <span data-ttu-id="12fb2-171">Esaminare l'output per i risultati e gli errori.</span><span class="sxs-lookup"><span data-stu-id="12fb2-171">Examine the output for results and errors.</span></span>

4. <span data-ttu-id="12fb2-172">Esaminare il file Trace. log.</span><span class="sxs-lookup"><span data-stu-id="12fb2-172">Examine the trace.log file.</span></span> <span data-ttu-id="12fb2-173">Sarà presente nella stessa cartella in cui è stata inviata l'esportazione.</span><span class="sxs-lookup"><span data-stu-id="12fb2-173">It will be in the same folder that you sent the export to.</span></span>

5. <span data-ttu-id="12fb2-174">Contattare il Servizio Supporto Tecnico Clienti Microsoft.</span><span class="sxs-lookup"><span data-stu-id="12fb2-174">Contact Microsoft Support.</span></span>

## <a name="errorissue-holds-dont-sync"></a><span data-ttu-id="12fb2-175">Errore/problema: esenzioni non sincronizzate</span><span class="sxs-lookup"><span data-stu-id="12fb2-175">Error/issue: Holds don't sync</span></span>

<span data-ttu-id="12fb2-176">errore di distribuzione della sincronizzazione del criterio di eDiscovery in caso di blocco.</span><span class="sxs-lookup"><span data-stu-id="12fb2-176">eDiscovery Case Hold Policy Sync Distribution error.</span></span> <span data-ttu-id="12fb2-177">L'errore si legge:</span><span class="sxs-lookup"><span data-stu-id="12fb2-177">The error reads:</span></span>

> <span data-ttu-id="12fb2-178">"Risorse: richiede più tempo del previsto per la distribuzione del criterio.</span><span class="sxs-lookup"><span data-stu-id="12fb2-178">"Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="12fb2-179">Per aggiornare lo stato di distribuzione finale, potrebbe essere necessario attendere altre due ore, quindi riprovare tra un paio di ore ".</span><span class="sxs-lookup"><span data-stu-id="12fb2-179">It might take an additional two hours to update the final deployment status, so check back in a couple hours.”</span></span>

### <a name="resolution"></a><span data-ttu-id="12fb2-180">Soluzione</span><span class="sxs-lookup"><span data-stu-id="12fb2-180">Resolution</span></span>

1.  <span data-ttu-id="12fb2-181">Connettersi a [Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) e quindi immettere il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="12fb2-181">Connect to [Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) and then enter the following command:</span></span>

    ```powershell
    Get-RetentionCompliancePolicy  <policyname> - DistributionDetail | FL
    ```

2. <span data-ttu-id="12fb2-182">Esaminare il valore del parametro DistributionDetail per gli errori analoghi a quelli riportati di seguito:</span><span class="sxs-lookup"><span data-stu-id="12fb2-182">Examine the value in the DistributionDetail parameter for errors like the following:</span></span>

   > <span data-ttu-id="12fb2-183">Se si verifica un errore, è possibile creare un'escalation a PG per forzare la risincronizzazione manuale del criterio.</span><span class="sxs-lookup"><span data-stu-id="12fb2-183">If error exists, create escalation to PG to force a manual re-sync on the Policy.</span></span>

3. <span data-ttu-id="12fb2-184">Contattare il Servizio Supporto Tecnico Clienti Microsoft.</span><span class="sxs-lookup"><span data-stu-id="12fb2-184">Contact Microsoft Support.</span></span>

## <a name="see-also"></a><span data-ttu-id="12fb2-185">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="12fb2-185">See Also</span></span>

- [<span data-ttu-id="12fb2-186">Suggerimenti per evitare errori di posizione del contenuto</span><span class="sxs-lookup"><span data-stu-id="12fb2-186">Tips to avoid content location errors</span></span>](retry-failed-content-search.md#tips-to-avoid-content-location-errors)