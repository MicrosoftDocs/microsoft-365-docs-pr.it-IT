---
title: Risoluzione dei problemi comuni relativi a eDiscovery
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
ms.openlocfilehash: e1fbda23b730956db42d8e7a92218fb9837868b8
ms.sourcegitcommit: cbe8724bd71d1c002395d98f1451c5f578c824f9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "49988140"
---
# <a name="investigate-troubleshoot-and-resolve-common-ediscovery-issues"></a><span data-ttu-id="bbc05-103">Esaminare, risolvere i problemi e risolvere i problemi comuni relativi a eDiscovery</span><span class="sxs-lookup"><span data-stu-id="bbc05-103">Investigate, troubleshoot, and resolve common eDiscovery issues</span></span>

<span data-ttu-id="bbc05-104">In questo argomento vengono illustrati i passaggi di base per la risoluzione dei problemi che è possibile eseguire per identificare e risolvere i problemi che possono verificarsi durante una ricerca di eDiscovery o altrove nel processo di eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="bbc05-104">This topic covers basic troubleshooting steps you can take to identify and resolve issues you may encounter during an eDiscovery search or elsewhere in the eDiscovery process.</span></span> <span data-ttu-id="bbc05-105">La risoluzione di alcuni di questi scenari richiede assistenza da parte del supporto tecnico Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bbc05-105">Resolving some of these scenarios requires help from Microsoft Support.</span></span> <span data-ttu-id="bbc05-106">Informazioni su quando contattare il supporto tecnico Microsoft è incluso nei passaggi di risoluzione.</span><span class="sxs-lookup"><span data-stu-id="bbc05-106">Information on when to contact Microsoft Support is included in the resolution steps.</span></span>

## <a name="errorissue-ambiguous-location"></a><span data-ttu-id="bbc05-107">Errore/problema: posizione ambigua</span><span class="sxs-lookup"><span data-stu-id="bbc05-107">Error/issue: Ambiguous location</span></span>

<span data-ttu-id="bbc05-108">Se si tenta di aggiungere la posizione della cassetta postale dell'utente alla ricerca e sono presenti oggetti duplicati o in conflitto con lo stesso userID nella directory di Exchange Online Protection (EOP), viene visualizzato questo errore: `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous` .</span><span class="sxs-lookup"><span data-stu-id="bbc05-108">If you try to add user's mailbox location to search and there are duplicate or conflicting objects with the same userID in the Exchange Online Protection (EOP) directory, you receive this error: `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous`.</span></span>

### <a name="resolution"></a><span data-ttu-id="bbc05-109">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="bbc05-109">Resolution</span></span>

<span data-ttu-id="bbc05-110">Controllare gli utenti duplicati o la lista di distribuzione con lo stesso ID utente.</span><span class="sxs-lookup"><span data-stu-id="bbc05-110">Check for duplicate users or distribution list with the same user ID.</span></span>

1. <span data-ttu-id="bbc05-111">Connettersi a [PowerShell per Centro sicurezza & Compliance](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="bbc05-111">Connect to [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="bbc05-112">Eseguire il seguente comando per recuperare tutte le istanze del nome utente:</span><span class="sxs-lookup"><span data-stu-id="bbc05-112">Run the following command to retrieve all instances of the username:</span></span>

    ```powershell
    Get-Recipient <username>
    ```

   <span data-ttu-id="bbc05-113">L'output per ' useralias@contoso.com ' sarebbe simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="bbc05-113">The output for 'useralias@contoso.com' would be similar to the following:</span></span>

   > 
   > |<span data-ttu-id="bbc05-114">Nome</span><span class="sxs-lookup"><span data-stu-id="bbc05-114">Name</span></span>|<span data-ttu-id="bbc05-115">RecipientType</span><span class="sxs-lookup"><span data-stu-id="bbc05-115">RecipientType</span></span>|
   > |---|---|
   > |<span data-ttu-id="bbc05-116">Alias, utente</span><span class="sxs-lookup"><span data-stu-id="bbc05-116">Alias, User</span></span>|<span data-ttu-id="bbc05-117">MailUser</span><span class="sxs-lookup"><span data-stu-id="bbc05-117">MailUser</span></span>|
   > |<span data-ttu-id="bbc05-118">Alias, utente</span><span class="sxs-lookup"><span data-stu-id="bbc05-118">Alias, User</span></span>|<span data-ttu-id="bbc05-119">Utente</span><span class="sxs-lookup"><span data-stu-id="bbc05-119">User</span></span>|

3. <span data-ttu-id="bbc05-120">Se vengono restituiti più utenti, individuare e correggere l'oggetto in conflitto.</span><span class="sxs-lookup"><span data-stu-id="bbc05-120">If multiple users are returned, locate and fix the conflicting object.</span></span>

## <a name="errorissue-search-fails-on-specific-locations"></a><span data-ttu-id="bbc05-121">Errore/problema: la ricerca ha esito negativo su percorsi specifici</span><span class="sxs-lookup"><span data-stu-id="bbc05-121">Error/issue: Search fails on specific locations</span></span>

<span data-ttu-id="bbc05-122">Un eDiscovery o una ricerca di contenuto può generare l'errore seguente: `This search completed with (#) errors.  Would you like to retry the search on the failed locations?`</span><span class="sxs-lookup"><span data-stu-id="bbc05-122">An eDiscovery or content search may yield the following error: `This search completed with (#) errors.  Would you like to retry the search on the failed locations?`</span></span>

![Posizione specifica della ricerca non riuscita screenshot di errore](../media/edisc-tshoot-specific-location-search-fails.png)

### <a name="resolution"></a><span data-ttu-id="bbc05-124">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="bbc05-124">Resolution</span></span>

<span data-ttu-id="bbc05-125">Se viene visualizzato questo errore, è consigliabile verificare che le posizioni non riuscite nella ricerca rieseguano la ricerca solo nelle posizioni non riuscite.</span><span class="sxs-lookup"><span data-stu-id="bbc05-125">If you receive this error, we recommend that you verify the locations that failed in the search  then rerun the search only on the failed locations.</span></span>

1. <span data-ttu-id="bbc05-126">Connettersi a [PowerShell per Centro sicurezza & Compliance](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) e quindi eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="bbc05-126">Connect to [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) and then run the following command:</span></span>

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. <span data-ttu-id="bbc05-127">Nell'output di PowerShell, visualizzare le posizioni non riuscite nel campo errori o nei dettagli dello stato nell'errore dall'output di ricerca.</span><span class="sxs-lookup"><span data-stu-id="bbc05-127">From the PowerShell output, view the failed locations in the errors field or from the status details in the error from the search output.</span></span>

3. <span data-ttu-id="bbc05-128">Riprovare la ricerca di eDiscovery solo nelle posizioni non riuscite.</span><span class="sxs-lookup"><span data-stu-id="bbc05-128">Retry the eDiscovery search on the failed locations only.</span></span>

4. <span data-ttu-id="bbc05-129">Se si continua a ricevere questi errori, vedere [retry failed locations](https://docs.microsoft.com/Office365/SecurityCompliance/retry-failed-content-search) for more troubleshooting steps.</span><span class="sxs-lookup"><span data-stu-id="bbc05-129">If you continue to receive these errors, see [Retry failed locations](https://docs.microsoft.com/Office365/SecurityCompliance/retry-failed-content-search) for more troubleshooting steps.</span></span>

## <a name="errorissue-file-not-found"></a><span data-ttu-id="bbc05-130">Errore/problema: file non trovato</span><span class="sxs-lookup"><span data-stu-id="bbc05-130">Error/issue: File not found</span></span>

<span data-ttu-id="bbc05-131">Quando si esegue una ricerca di eDiscovery che include SharePoint Online e un'unità per le posizioni aziendali, è possibile che venga visualizzato un errore `File Not Found` anche se il file si trova nel sito.</span><span class="sxs-lookup"><span data-stu-id="bbc05-131">When running an eDiscovery search that includes SharePoint Online and One Drive For Business locations, you may receive the error `File Not Found` although the file is located on the site.</span></span> <span data-ttu-id="bbc05-132">Questo errore verrà visualizzato negli avvisi di esportazione e errors.csv o saltato items.csv.</span><span class="sxs-lookup"><span data-stu-id="bbc05-132">This error will be in the export warnings and errors.csv or skipped items.csv.</span></span> <span data-ttu-id="bbc05-133">Ciò può verificarsi se il file non è stato trovato nel sito o se l'indice non è aggiornato.</span><span class="sxs-lookup"><span data-stu-id="bbc05-133">This may occur if the file can't be found on the site or if the index is out of date.</span></span> <span data-ttu-id="bbc05-134">Di seguito è indicato il testo di un errore reale (con enfasi aggiunta).</span><span class="sxs-lookup"><span data-stu-id="bbc05-134">Here's the text of an actual error (with emphasis added).</span></span>

> <span data-ttu-id="bbc05-135">28.06.2019 10:02:19_FailedToExportItem_Failed scaricare il contenuto.</span><span class="sxs-lookup"><span data-stu-id="bbc05-135">28.06.2019 10:02:19_FailedToExportItem_Failed to download content.</span></span> <span data-ttu-id="bbc05-136">Ulteriori informazioni di diagnostica: Microsoft. Office. compliance. EDiscovery. ExportWorker. Exceptions. ContentDownloadTemporaryFailure: failed to download from content 6ea52149-91CD-4965-b5bb-82ca6a3ec9be of Type Document.</span><span class="sxs-lookup"><span data-stu-id="bbc05-136">Additional diagnostic info : Microsoft.Office.Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure: Failed to download from content 6ea52149-91cd-4965-b5bb-82ca6a3ec9be of type Document.</span></span> <span data-ttu-id="bbc05-137">ID di correlazione: 3bd84722-937b-4c23-b61b-08d6fba9ec32.</span><span class="sxs-lookup"><span data-stu-id="bbc05-137">Correlation Id: 3bd84722-937b-4c23-b61b-08d6fba9ec32.</span></span> <span data-ttu-id="bbc05-138">ServerErrorCode:-2147024894---> Microsoft. SharePoint. client. ServerException: ***file non trovato***.</span><span class="sxs-lookup"><span data-stu-id="bbc05-138">ServerErrorCode: -2147024894 ---> Microsoft.SharePoint.Client.ServerException: ***File Not Found***.</span></span> <span data-ttu-id="bbc05-139">in Microsoft. SharePoint. client. ClientRequest. ProcessResponseStream (Stream responseStream) in Microsoft. SharePoint. client. ClientRequest. ProcessResponse ()---fine dell'analisi dello stack dell'eccezione interna---</span><span class="sxs-lookup"><span data-stu-id="bbc05-139">at Microsoft.SharePoint.Client.ClientRequest.ProcessResponseStream(Stream responseStream) at Microsoft.SharePoint.Client.ClientRequest.ProcessResponse() --- End of inner exception stack trace ---</span></span>

### <a name="resolution"></a><span data-ttu-id="bbc05-140">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="bbc05-140">Resolution</span></span>

1. <span data-ttu-id="bbc05-141">Controllare la posizione identificata nella ricerca per verificare che il percorso del file sia corretto e che sia stato aggiunto nei percorsi di ricerca.</span><span class="sxs-lookup"><span data-stu-id="bbc05-141">Check location identified in the search to ensure the that the location of the file is correct and added in the search locations.</span></span>

2. <span data-ttu-id="bbc05-142">Utilizzare le procedure per eseguire la ricerca per indicizzazione [e reindicizzazione manuale di un sito, di una raccolta o di un elenco](https://docs.microsoft.com/sharepoint/crawl-site-content) per reindicizzare il sito.</span><span class="sxs-lookup"><span data-stu-id="bbc05-142">Use the procedures at [Manually request crawling and re-indexing of a site, a library, or a list](https://docs.microsoft.com/sharepoint/crawl-site-content) to reindex the site.</span></span>

## <a name="errorissue-search-fails-because-recipient-is-not-found"></a><span data-ttu-id="bbc05-143">Errore/problema: la ricerca ha esito negativo perché il destinatario non viene trovato</span><span class="sxs-lookup"><span data-stu-id="bbc05-143">Error/issue: Search fails because recipient is not found</span></span>

<span data-ttu-id="bbc05-144">Una ricerca di eDiscovery ha esito negativo con errore `recipient not found` .</span><span class="sxs-lookup"><span data-stu-id="bbc05-144">An eDiscovery search fails with error the `recipient not found`.</span></span> <span data-ttu-id="bbc05-145">Questo errore può verificarsi se l'oggetto utente non è disponibile in Exchange Online Protection (EOP) perché l'oggetto non è stato sincronizzato.</span><span class="sxs-lookup"><span data-stu-id="bbc05-145">This error may occur if the user object cannot be found in Exchange Online Protection (EOP) because the object has not synced.</span></span>

### <a name="resolution"></a><span data-ttu-id="bbc05-146">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="bbc05-146">Resolution</span></span>

1. <span data-ttu-id="bbc05-147">Connettersi a [PowerShell di Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="bbc05-147">Connect to [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="bbc05-148">Eseguire il seguente comando per verificare se l'utente è sincronizzato con Exchange Online Protection:</span><span class="sxs-lookup"><span data-stu-id="bbc05-148">Run the following command to check if the user is synced to Exchange Online Protection:</span></span>

   ```powershell
   Get-Recipient <userId> | FL
   ```

3. <span data-ttu-id="bbc05-149">Deve essere presente un oggetto utente di posta elettronica per la domanda dell'utente.</span><span class="sxs-lookup"><span data-stu-id="bbc05-149">There should be a mail user object for the user question.</span></span> <span data-ttu-id="bbc05-150">Se non viene restituito alcun valore, esaminare l'oggetto User.</span><span class="sxs-lookup"><span data-stu-id="bbc05-150">If nothing is returned, investigate the user object.</span></span> <span data-ttu-id="bbc05-151">Se l'oggetto non può essere sincronizzato, contattare il supporto tecnico Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bbc05-151">Contact Microsoft Support if the object can't be synced.</span></span>

## <a name="errorissue-exporting-search-results-is-slow"></a><span data-ttu-id="bbc05-152">Errore/problema: l'esportazione dei risultati di ricerca è lenta</span><span class="sxs-lookup"><span data-stu-id="bbc05-152">Error/issue: Exporting search results is slow</span></span>

<span data-ttu-id="bbc05-153">Quando si esportano i risultati della ricerca da eDiscovery o ricerca contenuto nel centro sicurezza e conformità, il download richiede più tempo del previsto.</span><span class="sxs-lookup"><span data-stu-id="bbc05-153">When exporting search results from eDiscovery or Content Search in the Security and Compliance center, the download takes longer than expected.</span></span>  <span data-ttu-id="bbc05-154">È possibile controllare la quantità di dati da scaricare ed eventualmente aumentare la velocità di esportazione.</span><span class="sxs-lookup"><span data-stu-id="bbc05-154">You can check to see the amount of data to be download and possibly increase the export speed.</span></span>

### <a name="resolution"></a><span data-ttu-id="bbc05-155">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="bbc05-155">Resolution</span></span>

1. <span data-ttu-id="bbc05-156">Connettersi a [PowerShell per Centro sicurezza & Compliance](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) e quindi eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="bbc05-156">Connect to [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) and then run the following command:</span></span>

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. <span data-ttu-id="bbc05-157">Individuare la quantità di dati da scaricare nei parametri SearchResults e SearchStatistics.</span><span class="sxs-lookup"><span data-stu-id="bbc05-157">Find the amount of data to be downloaded in the SearchResults and SearchStatistics parameters.</span></span>

3. <span data-ttu-id="bbc05-158">Eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="bbc05-158">Run the following command:</span></span>

   ```powershell
   Get-ComplianceSearchAction | FL
   ```

4. <span data-ttu-id="bbc05-159">Nel campo risultati individuare i dati che sono stati esportati e visualizzare gli eventuali errori riscontrati.</span><span class="sxs-lookup"><span data-stu-id="bbc05-159">In the results field, find the data that has been exported and view any errors encountered.</span></span>

5. <span data-ttu-id="bbc05-160">Controllare il file Trace. log che si trova nella directory in cui è stato esportato il contenuto per eventuali errori.</span><span class="sxs-lookup"><span data-stu-id="bbc05-160">Check the trace.log file located in the directory that you exported the content to for any errors.</span></span>

6. <span data-ttu-id="bbc05-161">Se si verificano ancora problemi, è consigliabile dividere le ricerche che restituiscono un set di risultati di grandi dimensioni in ricerche più piccole.</span><span class="sxs-lookup"><span data-stu-id="bbc05-161">If you still have issues, consider dividing searches that return a large set of results into smaller searches.</span></span> <span data-ttu-id="bbc05-162">Ad esempio, è possibile utilizzare intervalli di date nelle query di ricerca per restituire un insieme di risultati più piccolo che può essere scaricato più velocemente.</span><span class="sxs-lookup"><span data-stu-id="bbc05-162">For example, you can use date ranges in search queries to return a smaller set of results that can be downloaded faster.</span></span>

## <a name="errorissue-internal-server-error-500-occurred"></a><span data-ttu-id="bbc05-163">Errore/problema: "errore interno del server (500) si è verificato"</span><span class="sxs-lookup"><span data-stu-id="bbc05-163">Error/issue: "Internal server error (500) occurred"</span></span>

<span data-ttu-id="bbc05-164">Quando si esegue una ricerca eDiscovery, se la ricerca ha esito negativo con un errore simile a "Internal Server Error (500) si è verificato", potrebbe essere necessario eseguire nuovamente la ricerca solo su percorsi specifici per le cassette postali.</span><span class="sxs-lookup"><span data-stu-id="bbc05-164">When running an eDiscovery search, if the search continually fails with error similar to "Internal server error (500) occurred", you may need rerun the search only on specific mailbox locations.</span></span>

![Errore del server interno 500 screenshot](../media/edisc-tshoot-error-500.png)

### <a name="resolution"></a><span data-ttu-id="bbc05-166">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="bbc05-166">Resolution</span></span>

1. <span data-ttu-id="bbc05-167">Suddividere la ricerca in ricerche più piccole ed eseguire di nuovo la ricerca.</span><span class="sxs-lookup"><span data-stu-id="bbc05-167">Break the search into smaller searches and run the search again.</span></span>  <span data-ttu-id="bbc05-168">Provare a utilizzare un intervallo di date più piccolo o limitare il numero di posizioni in cui è stata eseguita la ricerca.</span><span class="sxs-lookup"><span data-stu-id="bbc05-168">Try using a smaller date range or limit the number of locations being searched.</span></span>

2. <span data-ttu-id="bbc05-169">Connettersi a [PowerShell per Centro sicurezza & Compliance](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) e quindi eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="bbc05-169">Connect to [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) and then run the following command:</span></span>

   ```powershell Set-CaseHoldPolicy <policyname> -RetryDistribution
   Get-ComplianceSearch <searchname> | FL
   ```

3. <span data-ttu-id="bbc05-170">Esaminare l'output per i risultati e gli errori.</span><span class="sxs-lookup"><span data-stu-id="bbc05-170">Examine the output for results and errors.</span></span>

4. <span data-ttu-id="bbc05-171">Esaminare il file Trace. log.</span><span class="sxs-lookup"><span data-stu-id="bbc05-171">Examine the trace.log file.</span></span> <span data-ttu-id="bbc05-172">Si trova nella stessa cartella in cui sono stati esportati i risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="bbc05-172">It's located  in the same folder that you exported the search results to.</span></span>

5. <span data-ttu-id="bbc05-173">Contattare il Servizio Supporto Tecnico Clienti Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bbc05-173">Contact Microsoft Support.</span></span>

## <a name="errorissue-holds-dont-sync"></a><span data-ttu-id="bbc05-174">Errore/problema: esenzioni non sincronizzate</span><span class="sxs-lookup"><span data-stu-id="bbc05-174">Error/issue: Holds don't sync</span></span>

<span data-ttu-id="bbc05-175">errore di distribuzione della sincronizzazione del criterio di eDiscovery in caso di blocco.</span><span class="sxs-lookup"><span data-stu-id="bbc05-175">eDiscovery Case Hold Policy Sync Distribution error.</span></span> <span data-ttu-id="bbc05-176">L'errore si legge:</span><span class="sxs-lookup"><span data-stu-id="bbc05-176">The error reads:</span></span>

> <span data-ttu-id="bbc05-177">"Risorse: richiede più tempo del previsto per la distribuzione del criterio.</span><span class="sxs-lookup"><span data-stu-id="bbc05-177">"Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="bbc05-178">Potrebbe essere necessario un ulteriore 2 ore per aggiornare lo stato di distribuzione finale, in modo da controllare tra un paio di ore.</span><span class="sxs-lookup"><span data-stu-id="bbc05-178">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours."</span></span>

### <a name="resolution"></a><span data-ttu-id="bbc05-179">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="bbc05-179">Resolution</span></span>

1. <span data-ttu-id="bbc05-180">Connettersi a [PowerShell per il Centro sicurezza & Compliance](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) e quindi eseguire il comando seguente per un blocco di caso di eDiscovery:</span><span class="sxs-lookup"><span data-stu-id="bbc05-180">Connect to [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) and then run the following command for an eDiscovery case hold:</span></span>

   ```powershell
   Get-CaseHoldPolicy <policyname> - DistributionDetail | FL
   ```

    <span data-ttu-id="bbc05-181">Per un criterio di conservazione, eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="bbc05-181">For a retention policy, run the following command:</span></span>

   ```powershell
   Get-RetentionCompliancePolicy <policyname> - DistributionDetail | FL
   ```

2. <span data-ttu-id="bbc05-182">Esaminare il valore del parametro DistributionDetail per gli errori analoghi a quelli riportati di seguito:</span><span class="sxs-lookup"><span data-stu-id="bbc05-182">Examine the value in the DistributionDetail parameter for errors like the following:</span></span>

   > <span data-ttu-id="bbc05-183">Errore: risorse: richiede più tempo del previsto per la distribuzione del criterio.</span><span class="sxs-lookup"><span data-stu-id="bbc05-183">Error: Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="bbc05-184">Potrebbe essere necessario un ulteriore 2 ore per aggiornare lo stato di distribuzione finale, in modo da controllare tra un paio di ore.</span><span class="sxs-lookup"><span data-stu-id="bbc05-184">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours."</span></span>

3. <span data-ttu-id="bbc05-185">Provare a eseguire il parametro RetryDistribution per il criterio in questione:</span><span class="sxs-lookup"><span data-stu-id="bbc05-185">Try running the RetryDistribution parameter on the policy in question:</span></span>

   <span data-ttu-id="bbc05-186">Per il caso di eDiscovery:</span><span class="sxs-lookup"><span data-stu-id="bbc05-186">For eDiscovery case holds:</span></span>

   ```powershell
   Set-CaseHoldPolicy <policyname> -RetryDistribution
   ```

   <span data-ttu-id="bbc05-187">Per i criteri di conservazione:</span><span class="sxs-lookup"><span data-stu-id="bbc05-187">For retention policies:</span></span>

   ```powershell
   Set-RetentionCompliancePolicy <policyname> -RetryDistribution
   ```

4. <span data-ttu-id="bbc05-188">Contattare il Servizio Supporto Tecnico Clienti Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bbc05-188">Contact Microsoft Support.</span></span>

## <a name="error-the-condition-specified-using-http-conditional-headers-is-not-met"></a><span data-ttu-id="bbc05-189">Errore: "la condizione specificata utilizzando le intestazioni condizionali HTTP non è soddisfatta"</span><span class="sxs-lookup"><span data-stu-id="bbc05-189">Error: "The condition specified using HTTP conditional header(s) is not met"</span></span>

<span data-ttu-id="bbc05-190">Quando si scaricano i risultati della ricerca utilizzando lo strumento di esportazione di eDiscovery, è possibile che venga visualizzato il seguente messaggio di errore: `System.Net.WebException: The remote server returned an error: (412) The condition specified using HTTP conditional header(s) is not met.` errore temporaneo, che in genere si verifica nel percorso di archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="bbc05-190">When downloading search results using the eDiscovery Export Tool, it's possible you might receive the following error: `System.Net.WebException: The remote server returned an error: (412) The condition specified using HTTP conditional header(s) is not met.` This is transient error, which typically occurs in the Azure Storage location.</span></span>

### <a name="resolution"></a><span data-ttu-id="bbc05-191">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="bbc05-191">Resolution</span></span>

<span data-ttu-id="bbc05-192">Per risolvere il problema, riprovare a [scaricare i risultati della ricerca](export-search-results.md#step-2-download-the-search-results), che riavvierà lo strumento di esportazione di eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="bbc05-192">To resolve this issue, retry [downloading the search results](export-search-results.md#step-2-download-the-search-results), which will restart the eDiscovery Export Tool.</span></span>

## <a name="errorissue-downloaded-export-shows-no-results"></a><span data-ttu-id="bbc05-193">Errore/problema: l'esportazione scaricata non Visualizza risultati</span><span class="sxs-lookup"><span data-stu-id="bbc05-193">Error/issue: Downloaded export shows no results</span></span>

<span data-ttu-id="bbc05-194">Dopo un'esportazione completata, il download completato tramite lo strumento Esporta Visualizza zero file nei risultati.</span><span class="sxs-lookup"><span data-stu-id="bbc05-194">After a successful export, the completed download via the export tool shows zero files in the results.</span></span>

### <a name="resolution"></a><span data-ttu-id="bbc05-195">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="bbc05-195">Resolution</span></span>

<span data-ttu-id="bbc05-196">Si tratta di un problema sul fronte client e per rimediare, provare a eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="bbc05-196">This is a client-side issue and in order to remediate it, please attempt the following steps:</span></span>

1. <span data-ttu-id="bbc05-197">Provare a utilizzare un altro client/computer per il download.</span><span class="sxs-lookup"><span data-stu-id="bbc05-197">Try using another client/machine to download.</span></span>

2. <span data-ttu-id="bbc05-198">Assicurarsi di scaricare in un'unità locale.</span><span class="sxs-lookup"><span data-stu-id="bbc05-198">Make sure to download to a local drive.</span></span>

3. <span data-ttu-id="bbc05-199">Assicurarsi che lo scanner antivirus non sia in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="bbc05-199">Make sure the virus scanner is not running.</span></span>

4. <span data-ttu-id="bbc05-200">Assicurarsi che nessun'altra esportazione venga scaricata nella stessa cartella o in qualsiasi cartella padre.</span><span class="sxs-lookup"><span data-stu-id="bbc05-200">Make sure that no other export is downloading to the same folder or any parent folder.</span></span>

5. <span data-ttu-id="bbc05-201">Se i passaggi precedenti non funzionano, disabilitare la compressione e la deduplicazione.</span><span class="sxs-lookup"><span data-stu-id="bbc05-201">If the previous steps did not work, disable zipping and de-duplication.</span></span>

6. <span data-ttu-id="bbc05-202">In questo caso, il problema è dovuto a un virus o a un problema del disco.</span><span class="sxs-lookup"><span data-stu-id="bbc05-202">If this works then the issue is due to a local virus scanner or a disk issue.</span></span>
