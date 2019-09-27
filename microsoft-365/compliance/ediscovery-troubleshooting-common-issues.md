---
title: Problemi di eDiscovery comuni di Troublshooting
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
description: Indagini, risoluzione dei problemi e risolvere problemi comuni in Office 365 eDiscovery.
siblings_only: true
ms.openlocfilehash: db355067aa4e3fc41541e6414b59c92aaac1b5b3
ms.sourcegitcommit: 75c8f89049081f08852699c8d51c3a07b12165da
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2019
ms.locfileid: "37207294"
---
# <a name="investigate-troubleshoot-and-resolve-common-ediscovery-issues"></a><span data-ttu-id="cd252-103">Esaminare, risolvere i problemi e risolverne i problemi comuni relativi a eDiscovery</span><span class="sxs-lookup"><span data-stu-id="cd252-103">Investigate, troubleshoot and resolve common eDiscovery issues</span></span>

<span data-ttu-id="cd252-104">In questo argomento vengono illustrati i passaggi di base per la risoluzione dei problemi che è possibile eseguire per identificare e risolvere i problemi che possono verificarsi durante una ricerca di eDiscovery o altrove nel processo di eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="cd252-104">This topic covers basic troubleshooting steps you can take to identify and resolve issues you may encounter during an eDiscovery search or elsewhere in the eDiscovery process.</span></span> <span data-ttu-id="cd252-105">La risoluzione di alcuni di questi scenari richiede assistenza da parte dei servizi di supporto tecnico (CSS).</span><span class="sxs-lookup"><span data-stu-id="cd252-105">Resolving some of these scenarios requires help from Customer Support Services (CSS).</span></span> <span data-ttu-id="cd252-106">Le informazioni su quando contattare CSS sono incluse nei passaggi di risoluzione.</span><span class="sxs-lookup"><span data-stu-id="cd252-106">Information on when to contact CSS is included in the resolution steps.</span></span>

## <a name="errorissue-ambiguous-location"></a><span data-ttu-id="cd252-107">Errore/percorso ambiguo del problema</span><span class="sxs-lookup"><span data-stu-id="cd252-107">Error/issue ambiguous location</span></span>

<span data-ttu-id="cd252-108">Verrà visualizzato questo errore "la ricerca di conformità contiene il percorso `(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous"` non valido seguente se si è tentato di aggiungere la posizione della cassetta postale dell'utente alla ricerca e sono presenti oggetti duplicati o in conflitto con lo stesso ID utente in Exchange Online Protection (EOP) Directory.</span><span class="sxs-lookup"><span data-stu-id="cd252-108">You'll receive this error "The compliance search contains the following invalid location `(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous"` if you tried to add user’s mailbox location to search and there are duplicate or conflicting objects with the same user id in the Exchange Online Protection (EOP) directory.</span></span>

### <a name="resolution"></a><span data-ttu-id="cd252-109">Soluzione</span><span class="sxs-lookup"><span data-stu-id="cd252-109">Resolution</span></span>

<span data-ttu-id="cd252-110">Controllare gli utenti duplicati o la lista di distribuzione con lo stesso ID utente.</span><span class="sxs-lookup"><span data-stu-id="cd252-110">Check for duplicate users or distribution list with the same user ID.</span></span>

1. <span data-ttu-id="cd252-111">Connettersi a [PowerShell di Exchange Online](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="cd252-111">Connect to [Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>
2. <span data-ttu-id="cd252-112">Recuperare tutte le istanze del nome utente, digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="cd252-112">Retrieve all instances of the username, type:</span></span>

```powershell
Get-Recipient <username>
```

<span data-ttu-id="cd252-113">L'output per ' useralias@contoso.com ' potrebbe essere</span><span class="sxs-lookup"><span data-stu-id="cd252-113">The output for 'useralias@contoso.com' might be</span></span>

> 
> |<span data-ttu-id="cd252-114">Name</span><span class="sxs-lookup"><span data-stu-id="cd252-114">Name</span></span>  |<span data-ttu-id="cd252-115">RecipientType</span><span class="sxs-lookup"><span data-stu-id="cd252-115">RecipientType</span></span>  |
> |---------|---------|
> |<span data-ttu-id="cd252-116">Alias, utente</span><span class="sxs-lookup"><span data-stu-id="cd252-116">Alias, User</span></span>     |<span data-ttu-id="cd252-117">MailUser</span><span class="sxs-lookup"><span data-stu-id="cd252-117">MailUser</span></span>         |
> |<span data-ttu-id="cd252-118">Alias, utente</span><span class="sxs-lookup"><span data-stu-id="cd252-118">Alias, User</span></span>     |<span data-ttu-id="cd252-119">Utente</span><span class="sxs-lookup"><span data-stu-id="cd252-119">User</span></span>         |

3. <span data-ttu-id="cd252-120">Se vengono restituiti più utenti, individuare e correggere l'oggetto in conflitto.</span><span class="sxs-lookup"><span data-stu-id="cd252-120">If multiple users are returned, locate and fix the conflicting object.</span></span>

## <a name="errorissue-search-fails-on-specific-locations"></a><span data-ttu-id="cd252-121">Errore/problema la ricerca ha esito negativo in posizioni specifiche</span><span class="sxs-lookup"><span data-stu-id="cd252-121">Error/issue search fails on specific locations</span></span>

<span data-ttu-id="cd252-122">Un eDiscovery o una ricerca di contenuto può generare l'errore seguente:</span><span class="sxs-lookup"><span data-stu-id="cd252-122">An eDiscovery or content search may yield the following error:</span></span>
><span data-ttu-id="cd252-123">Questa ricerca è stata completata con gli errori (#).</span><span class="sxs-lookup"><span data-stu-id="cd252-123">This search completed with (#) errors.</span></span>  <span data-ttu-id="cd252-124">Si desidera riprovare la ricerca nelle posizioni non riuscite?</span><span class="sxs-lookup"><span data-stu-id="cd252-124">Would you like to retry the search on the failed locations?</span></span>

![posizione specifica di ricerca non riuscita screenshot di errore]( media/edisc-tshoot-specific-location-search-fails.png)

### <a name="resolution"></a><span data-ttu-id="cd252-126">Soluzione</span><span class="sxs-lookup"><span data-stu-id="cd252-126">Resolution</span></span>

<span data-ttu-id="cd252-127">Se viene visualizzato questo errore, è consigliabile verificare che i percorsi non riusciti nella ricerca rieseguano di nuovo la ricerca solo nelle posizioni non riuscite.</span><span class="sxs-lookup"><span data-stu-id="cd252-127">If you receive this error, we recommend that you verify the locations that failed in the search  then re-run the search only on the failed locations.</span></span>

1. <span data-ttu-id="cd252-128">Connettersi a [PowerShell di Exchange Online Protection](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="cd252-128">Connect to [Exchange Online Protection Powershell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps).</span></span>
1. <span data-ttu-id="cd252-129">Tipo</span><span class="sxs-lookup"><span data-stu-id="cd252-129">Type:</span></span>

```powershell
Get-Compliancesearch searchname|fl 
```

3. <span data-ttu-id="cd252-130">Nell'output di PowerShell, visualizzare le posizioni non riuscite nel campo errori o nei dettagli dello stato nell'errore dall'output di ricerca.</span><span class="sxs-lookup"><span data-stu-id="cd252-130">From the PowerShell output, view the failed locations in the errors field or from the status details in the error from the search output.</span></span>
1. <span data-ttu-id="cd252-131">Riprovare la ricerca di eDiscovery solo nelle posizioni non riuscite.</span><span class="sxs-lookup"><span data-stu-id="cd252-131">Retry the eDiscovery search on the failed locations only.</span></span>
1. <span data-ttu-id="cd252-132">Se si continua a ricevere questi errori, vedere [tentativi non riusciti](https://docs.microsoft.com/en-us/Office365/SecurityCompliance/retry-failed-content-search) per ulteriori passaggi per la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="cd252-132">If you continue to receive these error, see [Retry failed locations](https://docs.microsoft.com/en-us/Office365/SecurityCompliance/retry-failed-content-search) for additional troubleshooting steps.</span></span>

## <a name="errorissue-file-not-found"></a><span data-ttu-id="cd252-133">Errore/problema impossibile trovare il file</span><span class="sxs-lookup"><span data-stu-id="cd252-133">Error/issue file not found</span></span>

<span data-ttu-id="cd252-134">Quando si esegue una ricerca di eDiscovery che include SharePoint Online e un'unità per le posizioni aziendali, è possibile `File Not Found` che venga visualizzato un errore anche se il file si trova nel sito.</span><span class="sxs-lookup"><span data-stu-id="cd252-134">When running an eDiscovery search that includes SharePoint Online and One Drive For Business locations, you may receive the error `File Not Found` although the file is located on the site.</span></span> <span data-ttu-id="cd252-135">Questo errore si verificherà con gli avvisi di esportazione e gli errori. csv o gli elementi ignorati. csv ciò può verificarsi se il file non può essere posizionato nel sito o se l'indice non è aggiornato.</span><span class="sxs-lookup"><span data-stu-id="cd252-135">This error will be in the export warnings and errors.csv or skipped items.csv  This may occur if the file cannot be located on the site or the index is out of date.</span></span> <span data-ttu-id="cd252-136">Di seguito è indicato il testo di un errore reale, con enfasi aggiunta.</span><span class="sxs-lookup"><span data-stu-id="cd252-136">Here's the text of an actual error, with emphasis added.</span></span>
  
> <span data-ttu-id="cd252-137">28.06.2019 10:02:19_FailedToExportItem_Failed per scaricare il contenuto.</span><span class="sxs-lookup"><span data-stu-id="cd252-137">28.06.2019 10:02:19_FailedToExportItem_Failed to download content.</span></span> <span data-ttu-id="cd252-138">Ulteriori informazioni di diagnostica: Microsoft. Office. compliance. EDiscovery. ExportWorker. Exceptions. ContentDownloadTemporaryFailure: failed to download from content 6ea52149-91CD-4965-b5bb-82ca6a3ec9be of Type Document.</span><span class="sxs-lookup"><span data-stu-id="cd252-138">Additional diagnostic info : Microsoft.Office.Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure: Failed to download from content 6ea52149-91cd-4965-b5bb-82ca6a3ec9be of type Document.</span></span> <span data-ttu-id="cd252-139">ID di correlazione: 3bd84722-937b-4c23-b61b-08d6fba9ec32.</span><span class="sxs-lookup"><span data-stu-id="cd252-139">Correlation Id: 3bd84722-937b-4c23-b61b-08d6fba9ec32.</span></span> <span data-ttu-id="cd252-140">ServerErrorCode:-2147024894---> Microsoft. SharePoint. client. ServerException: ***file non trovato***.</span><span class="sxs-lookup"><span data-stu-id="cd252-140">ServerErrorCode: -2147024894 ---> Microsoft.SharePoint.Client.ServerException: ***File Not Found***.</span></span> <span data-ttu-id="cd252-141">in Microsoft. SharePoint. client. ClientRequest. ProcessResponseStream (Stream responseStream) in Microsoft. SharePoint. client. ClientRequest. ProcessResponse ()---fine dell'analisi dello stack dell'eccezione interna---</span><span class="sxs-lookup"><span data-stu-id="cd252-141">at Microsoft.SharePoint.Client.ClientRequest.ProcessResponseStream(Stream responseStream) at Microsoft.SharePoint.Client.ClientRequest.ProcessResponse() --- End of inner exception stack trace ---</span></span>

### <a name="resolution"></a><span data-ttu-id="cd252-142">Soluzione</span><span class="sxs-lookup"><span data-stu-id="cd252-142">Resolution</span></span>

1. <span data-ttu-id="cd252-143">Controllare la posizione identificata nella ricerca per verificare che il percorso del file sia corretto e che sia stato aggiunto nei percorsi di ricerca.</span><span class="sxs-lookup"><span data-stu-id="cd252-143">Check location identified in the search to ensure the that the location of the file is correct and added in the search locations.</span></span>
2. <span data-ttu-id="cd252-144">Utilizzare le procedure per eseguire la ricerca per indicizzazione [e reindicizzazione manuale di un sito, una raccolta o un elenco](https://docs.microsoft.com/en-us/sharepoint/crawl-site-content) per reindicizzare il sito.</span><span class="sxs-lookup"><span data-stu-id="cd252-144">Use the procedures at [Manually request crawling and re-indexing of a site, a library or a list](https://docs.microsoft.com/en-us/sharepoint/crawl-site-content) to re-index the site.</span></span>

## <a name="errorissue-search-fails-recipient-not-found"></a><span data-ttu-id="cd252-145">Errore/problema ricerca non riuscito destinatario non trovato</span><span class="sxs-lookup"><span data-stu-id="cd252-145">Error/issue search fails recipient not found</span></span>

<span data-ttu-id="cd252-146">la ricerca eDiscovery ha esito negativo con errore `recipient not found`.</span><span class="sxs-lookup"><span data-stu-id="cd252-146">eDiscovery search fails with error `recipient not found`.</span></span> <span data-ttu-id="cd252-147">Questo errore può verificarsi se l'oggetto utente non è disponibile in Exchange Online Protection (EOP) perché l'oggetto non è stato sincronizzato.</span><span class="sxs-lookup"><span data-stu-id="cd252-147">This error may occur if the user object cannot be found in Exchange Online Protection (EOP) because the object has not synced.</span></span>

### <a name="resolution"></a><span data-ttu-id="cd252-148">Soluzione</span><span class="sxs-lookup"><span data-stu-id="cd252-148">Resolution</span></span>

1. <span data-ttu-id="cd252-149">Connettersi a [PowerShell di Exchange Online Protection](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="cd252-149">Connect to [Exchange Online Protection PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps).</span></span>
1. <span data-ttu-id="cd252-150">Controllare se l'oggetto utente è sincronizzato con il tipo di protezione Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="cd252-150">Check to see if the user object is synced to Exchange Online Protection type:</span></span>

```powershell
Get-Recipient userId|fl
```

3. <span data-ttu-id="cd252-151">Deve essere presente un oggetto MailUser per la domanda dell'utente.</span><span class="sxs-lookup"><span data-stu-id="cd252-151">There should be a mailuser object for the user question.</span></span> <span data-ttu-id="cd252-152">Se non viene restituito alcun valore, esaminare l'oggetto User.</span><span class="sxs-lookup"><span data-stu-id="cd252-152">If nothing is returned, investigate the user object.</span></span> <span data-ttu-id="cd252-153">Se l'oggetto non può essere sincronizzato, contattare CSS.</span><span class="sxs-lookup"><span data-stu-id="cd252-153">Contact CSS if the object can't be synced.</span></span>

## <a name="errorissue-exporting-search-results-is-slow"></a><span data-ttu-id="cd252-154">Errore/problema l'esportazione dei risultati di ricerca è lenta</span><span class="sxs-lookup"><span data-stu-id="cd252-154">Error/issue exporting search results is slow</span></span>

<span data-ttu-id="cd252-155">Quando si esportano i risultati della ricerca da eDiscovery o ricerca contenuto nel centro sicurezza e conformità, il download richiede più tempo del previsto.</span><span class="sxs-lookup"><span data-stu-id="cd252-155">When exporting search results from eDiscovery or Content Search in the Security and Compliance center, the download takes longer than expected.</span></span>  <span data-ttu-id="cd252-156">È possibile controllare la quantità di dati da scaricare ed eventualmente aumentare la velocità di esportazione.</span><span class="sxs-lookup"><span data-stu-id="cd252-156">You can check to see the amount of data to be download and possibly increase the export speed.</span></span>

### <a name="resolution"></a><span data-ttu-id="cd252-157">Soluzione</span><span class="sxs-lookup"><span data-stu-id="cd252-157">Resolution</span></span>

1.  <span data-ttu-id="cd252-158">Provare a utilizzare i passaggi identificati nell'articolo [aumentare la velocità di download](https://docs.microsoft.com/en-us/office365/securitycompliance/increase-download-speeds-when-exporting-ediscovery-results).</span><span class="sxs-lookup"><span data-stu-id="cd252-158">Try using the steps identified in the article [Increase Download Speeds](https://docs.microsoft.com/en-us/office365/securitycompliance/increase-download-speeds-when-exporting-ediscovery-results).</span></span>
2.  <span data-ttu-id="cd252-159">Se si dispone ancora di problemi, connettersi a [PowerShell di Exchange Online Protection](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps) e digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="cd252-159">If you still have issues, connect to [Exchange Online Protection PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps) and type:</span></span>

```powershell
Get-ComplianceSearch searchname\fl
```

4. <span data-ttu-id="cd252-160">Individuare la quantità di dati da scaricare nei parametri SearchResults e SearchStatistics.</span><span class="sxs-lookup"><span data-stu-id="cd252-160">Find the amount of data to be downloaded in the SearchResults and SearchStatistics parameters.</span></span>
5. <span data-ttu-id="cd252-161">Tipo</span><span class="sxs-lookup"><span data-stu-id="cd252-161">Type:</span></span>

```powershell
Get-ComplianceSearchAction |fl
```

6. <span data-ttu-id="cd252-162">Nel campo risultati individuare i dati che sono stati esportati e visualizzare gli eventuali errori riscontrati.</span><span class="sxs-lookup"><span data-stu-id="cd252-162">In the results field find the data that has been exported and view any errors encountered.</span></span>
7. <span data-ttu-id="cd252-163">Controllare il file Trace. log che si trova nella directory in cui è stato esportato il contenuto per eventuali errori.</span><span class="sxs-lookup"><span data-stu-id="cd252-163">Check the trace.log file located in the directory that you exported the content to for any errors.</span></span>

## <a name="errorissue-internal-server-error-500-occurred"></a><span data-ttu-id="cd252-164">Errore/problema "errore interno del server (500) si è verificato"</span><span class="sxs-lookup"><span data-stu-id="cd252-164">Error/issue "Internal server error (500) occurred"</span></span>

<span data-ttu-id="cd252-165">Quando si esegue una ricerca eDiscovery, se la ricerca ha esito negativo con un errore simile a "Internal Server Error (500) si è verificato", potrebbe essere necessario eseguire di nuovo la ricerca solo su percorsi specifici per le cassette postali.</span><span class="sxs-lookup"><span data-stu-id="cd252-165">When running an eDiscovery search, if the search continually fails with error similar to "Internal server error (500) occurred", you may need re-run the search only on specific mailbox locations.</span></span>

![errore del server interno 500 screenshot](media/edisc-tshoot-error-500.png)

### <a name="resolution"></a><span data-ttu-id="cd252-167">Soluzione</span><span class="sxs-lookup"><span data-stu-id="cd252-167">Resolution</span></span>

1. <span data-ttu-id="cd252-168">Suddividere la ricerca in ricerche più piccole ed eseguire di nuovo la ricerca.</span><span class="sxs-lookup"><span data-stu-id="cd252-168">Break the search into smaller searches and run the search again.</span></span>  <span data-ttu-id="cd252-169">Provare a utilizzare un intervallo di date più piccolo o limitare il numero di posizioni in cui è stata eseguita la ricerca.</span><span class="sxs-lookup"><span data-stu-id="cd252-169">Try using a smaller date range or limit the number of locations being searched.</span></span>
2. <span data-ttu-id="cd252-170">Connettersi a [PowerShell di Exchange Online Protection](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps) e digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="cd252-170">Connect to [Exchange Online Protection PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps) and type:</span></span>

```powershell
Get-ComplianceSearch searchname |fl
```

3. <span data-ttu-id="cd252-171">Esaminare l'output per i risultati e gli errori.</span><span class="sxs-lookup"><span data-stu-id="cd252-171">Examine the output for results and errors.</span></span>
3. <span data-ttu-id="cd252-172">Esaminare il file Trace. log.</span><span class="sxs-lookup"><span data-stu-id="cd252-172">Examine the trace.log file.</span></span> <span data-ttu-id="cd252-173">Sarà presente nella stessa cartella in cui è stata inviata l'esportazione.</span><span class="sxs-lookup"><span data-stu-id="cd252-173">It will be in the same folder that you sent the export to.</span></span>
4. <span data-ttu-id="cd252-174">Contattare il supporto CSS.</span><span class="sxs-lookup"><span data-stu-id="cd252-174">Contact Support CSS.</span></span>

## <a name="errorissue-holds-dont-sync"></a><span data-ttu-id="cd252-175">Errore/problema contiene non sincronizzare</span><span class="sxs-lookup"><span data-stu-id="cd252-175">Error/issue holds don't sync</span></span>

<span data-ttu-id="cd252-176">errore di distribuzione della sincronizzazione del criterio di eDiscovery in caso di blocco.</span><span class="sxs-lookup"><span data-stu-id="cd252-176">eDiscovery Case Hold Policy Sync Distribution error.</span></span> <span data-ttu-id="cd252-177">L'errore si legge:</span><span class="sxs-lookup"><span data-stu-id="cd252-177">The error reads:</span></span>

> <span data-ttu-id="cd252-178">"Risorse: richiede più tempo del previsto per la distribuzione del criterio.</span><span class="sxs-lookup"><span data-stu-id="cd252-178">"Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="cd252-179">Per aggiornare lo stato di distribuzione finale, potrebbe essere necessario attendere altre due ore, quindi riprovare tra un paio di ore ".</span><span class="sxs-lookup"><span data-stu-id="cd252-179">It might take an additional two hours to update the final deployment status, so check back in a couple hours.”</span></span>

### <a name="resolution"></a><span data-ttu-id="cd252-180">Soluzione</span><span class="sxs-lookup"><span data-stu-id="cd252-180">Resolution</span></span>

1.  <span data-ttu-id="cd252-181">Connettersi a [PowerShell di Exchange Online Protection](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps) e digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="cd252-181">Connect to [Exchange Online Protection PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps) and type:</span></span>

```powershell
Get-RetentionCompliancePolicy  policyname - Distributiondetail|fl
```

2. <span data-ttu-id="cd252-182">Esaminare il valore del parametro Distributiondetail per gli errori analoghi a quelli riportati di seguito:</span><span class="sxs-lookup"><span data-stu-id="cd252-182">Examine the value in the Distributiondetail parameter for errors like the following:</span></span>

> <span data-ttu-id="cd252-183">Se si verifica un errore, è possibile creare un'escalation a PG per forzare la risincronizzazione manuale del criterio.</span><span class="sxs-lookup"><span data-stu-id="cd252-183">If error exists, create escalation to PG to force a manual re-sync on the Policy.</span></span>

3. <span data-ttu-id="cd252-184">Contatti CSS.</span><span class="sxs-lookup"><span data-stu-id="cd252-184">Contact CSS.</span></span>

## <a name="see-also"></a><span data-ttu-id="cd252-185">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cd252-185">See Also</span></span>
- [<span data-ttu-id="cd252-186">Suggerimenti per evitare errori di posizione del contenuto</span><span class="sxs-lookup"><span data-stu-id="cd252-186">Tips to avoid content location errors</span></span>](https://docs.microsoft.com/en-us/microsoft-365/compliance/retry-failed-content-search%23tips-to-avoid-content-location-errors)