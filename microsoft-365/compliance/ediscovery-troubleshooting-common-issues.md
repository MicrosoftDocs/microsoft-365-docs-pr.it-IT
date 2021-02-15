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
description: Informazioni sui passaggi di base per la risoluzione dei problemi che è possibile eseguire per risolvere i problemi comuni in eDiscovery di Office 365.
siblings_only: true
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e1fbda23b730956db42d8e7a92218fb9837868b8
ms.sourcegitcommit: cbe8724bd71d1c002395d98f1451c5f578c824f9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "49988140"
---
# <a name="investigate-troubleshoot-and-resolve-common-ediscovery-issues"></a>Analizzare, risolvere e risolvere i problemi comuni di eDiscovery

In questo argomento vengono illustrati i passaggi di base per la risoluzione dei problemi che è possibile eseguire per identificare e risolvere i problemi che possono verificarsi durante una ricerca eDiscovery o altrove nel processo di eDiscovery. Per risolvere alcuni di questi scenari, è necessaria l'assistenza del supporto tecnico Microsoft. Le informazioni su quando contattare il supporto tecnico Microsoft sono incluse nei passaggi di risoluzione.

## <a name="errorissue-ambiguous-location"></a>Errore/problema: posizione ambigua

Se si tenta di aggiungere il percorso della cassetta postale dell'utente per la ricerca e sono presenti oggetti duplicati o in conflitto con lo stesso ID utente nella directory di Exchange Online Protection (EOP), viene visualizzato questo errore: `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous` .

### <a name="resolution"></a>Risoluzione

Verificare la presenza di utenti duplicati o liste di distribuzione con lo stesso ID utente.

1. Connettersi [a PowerShell & Centro sicurezza e conformità.](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)

2. Eseguire il comando seguente per recuperare tutte le istanze del nome utente:

    ```powershell
    Get-Recipient <username>
    ```

   L'output per "useralias@contoso.com" sarà simile al seguente:

   > 
   > |Nome|RecipientType|
   > |---|---|
   > |Alias, User|MailUser|
   > |Alias, User|Utente|

3. Se vengono restituiti più utenti, individuare e correggere l'oggetto in conflitto.

## <a name="errorissue-search-fails-on-specific-locations"></a>Errore/problema: la ricerca non riesce in percorsi specifici

Una ricerca di contenuto o eDiscovery può produrre l'errore seguente: `This search completed with (#) errors.  Would you like to retry the search on the failed locations?`

![Schermata di errore della posizione specifica della ricerca non riuscita](../media/edisc-tshoot-specific-location-search-fails.png)

### <a name="resolution"></a>Risoluzione

Se viene visualizzato questo errore, è consigliabile verificare i percorsi non riusciti nella ricerca e quindi eseguire di nuovo la ricerca solo nei percorsi con errori.

1. Connettersi [a PowerShell & Centro](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) sicurezza e conformità ed eseguire il comando seguente:

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. Dall'output di PowerShell, visualizzare i percorsi con errori nel campo degli errori o dai dettagli sullo stato nell'errore dall'output della ricerca.

3. Ritentare la ricerca eDiscovery solo nei percorsi non riusciti.

4. Se si continuano a ricevere questi errori, vedere [Riprovare](https://docs.microsoft.com/Office365/SecurityCompliance/retry-failed-content-search) percorsi non riusciti per ulteriori procedure di risoluzione dei problemi.

## <a name="errorissue-file-not-found"></a>Errore/problema: File non trovato

Quando si esegue una ricerca eDiscovery che include le posizioni di SharePoint Online e One Drive for Business, è possibile che venga visualizzato l'errore anche se il file si `File Not Found` trova nel sito. Questo errore verrà visualizzato negli avvisi di esportazione e errors.csv o ignorato items.csv. Ciò può verificarsi se non è possibile trovare il file nel sito o se l'indice non è aggiornato. Ecco il testo di un errore effettivo (con enfasi aggiunta).

> 28.06.2019 10:02:19_FailedToExportItem_Failed per scaricare il contenuto. Info di diagnostica aggiuntive: Microsoft.Office.Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure: Failed to download from content 6ea52149-91cd-4965-b5bb-82ca6a3ec9be of type Document. ID correlazione: 3bd84722-937b-4c23-b61b-08d6fba9ec32. ServerErrorCode: -2147024894 ---> Microsoft.SharePoint.Client.ServerException: ***File non trovato.*** at Microsoft.SharePoint.Client.ClientRequest.ProcessResponseStream(Stream responseStream) at Microsoft.SharePoint.Client.ClientRequest.ProcessResponse() --- End of inner exception stack trace ---

### <a name="resolution"></a>Risoluzione

1. Controllare il percorso identificato nella ricerca per verificare che il percorso del file sia corretto e aggiunto nei percorsi di ricerca.

2. Utilizzare le procedure descritte in Richiedere manualmente la ricerca per indicizzazione e la reindicizzazione di un [sito,](https://docs.microsoft.com/sharepoint/crawl-site-content) una raccolta o un elenco per reindicizzare il sito.

## <a name="errorissue-search-fails-because-recipient-is-not-found"></a>Errore/problema: la ricerca non riesce perché il destinatario non è stato trovato

Una ricerca eDiscovery ha esito negativo con l'errore `recipient not found` . Questo errore può verificarsi se non è possibile trovare l'oggetto utente in Exchange Online Protection (EOP) perché l'oggetto non è stato sincronizzato.

### <a name="resolution"></a>Risoluzione

1. Connettersi [a PowerShell di Exchange Online.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)

2. Eseguire il comando seguente per verificare se l'utente è sincronizzato con Exchange Online Protection:

   ```powershell
   Get-Recipient <userId> | FL
   ```

3. Deve essere presente un oggetto utente di posta per la domanda dell'utente. Se non viene restituito alcun valore, analizzare l'oggetto utente. Se l'oggetto non può essere sincronizzato, contattare il supporto tecnico Microsoft.

## <a name="errorissue-exporting-search-results-is-slow"></a>Errore/problema: l'esportazione dei risultati della ricerca è lenta

Quando si esportano i risultati della ricerca da eDiscovery o Ricerca contenuto nel Centro sicurezza e conformità, il download richiede più tempo del previsto.  È possibile controllare la quantità di dati da scaricare ed eventualmente aumentare la velocità di esportazione.

### <a name="resolution"></a>Risoluzione

1. Connettersi [a PowerShell & Centro](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) sicurezza e conformità ed eseguire il comando seguente:

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. Trovare la quantità di dati da scaricare nei parametri SearchResults e SearchStatistics.

3. Eseguire il comando riportato di seguito:

   ```powershell
   Get-ComplianceSearchAction | FL
   ```

4. Nel campo dei risultati individuare i dati esportati e visualizzare gli eventuali errori riscontrati.

5. Controllare se sono presenti errori nel file trace.log che si trova nella directory in cui è stato esportato il contenuto.

6. Se si verificano ancora problemi, è consigliabile suddividere le ricerche che restituiscono un set di risultati di grandi dimensioni in ricerche più piccole. È ad esempio possibile utilizzare intervalli di date nelle query di ricerca per restituire un set di risultati più piccolo che può essere scaricato più velocemente.

## <a name="errorissue-internal-server-error-500-occurred"></a>Errore/problema: "Errore interno del server (500) si è verificato"

Quando si esegue una ricerca eDiscovery, se la ricerca non riesce continuamente con un errore simile a "Errore interno del server (500)", potrebbe essere necessario eseguire di nuovo la ricerca solo in posizioni specifiche della cassetta postale.

![Screenshot dell'errore interno del server 500](../media/edisc-tshoot-error-500.png)

### <a name="resolution"></a>Risoluzione

1. Suddividere la ricerca in ricerche più piccole ed eseguire di nuovo la ricerca.  Provare a usare un intervallo di date più piccolo o limitare il numero di posizioni in cui eseguire la ricerca.

2. Connettersi [a PowerShell & Centro](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) sicurezza e conformità ed eseguire il comando seguente:

   ```powershell Set-CaseHoldPolicy <policyname> -RetryDistribution
   Get-ComplianceSearch <searchname> | FL
   ```

3. Esaminare l'output per ottenere risultati ed errori.

4. Esaminare il file trace.log. Si trova nella stessa cartella in cui sono stati esportati i risultati della ricerca.

5. Contattare il Servizio Supporto Tecnico Clienti Microsoft.

## <a name="errorissue-holds-dont-sync"></a>Errore/problema: i blocchi non vengono sincronizzati

Errore di distribuzione della sincronizzazione dei criteri di blocco del caso di eDiscovery. L'errore è il seguente:

> "Risorse: la distribuzione del criterio richiede più tempo del previsto. L'aggiornamento dello stato finale della distribuzione potrebbe richiedere altre 2 ore, quindi riestrarlo tra un paio d'ore."

### <a name="resolution"></a>Risoluzione

1. Connettersi [a PowerShell & Centro](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) sicurezza e conformità ed eseguire il comando seguente per un blocco caso di eDiscovery:

   ```powershell
   Get-CaseHoldPolicy <policyname> - DistributionDetail | FL
   ```

    Per un criterio di conservazione, eseguire il comando seguente:

   ```powershell
   Get-RetentionCompliancePolicy <policyname> - DistributionDetail | FL
   ```

2. Esaminare il valore nel parametro DistributionDetail per verificare la presenza di errori simili ai seguenti:

   > Errore: risorse: la distribuzione del criterio richiede più tempo del previsto. L'aggiornamento dello stato finale della distribuzione potrebbe richiedere altre 2 ore, quindi controllare di nuovo tra un paio d'ore."

3. Provare a eseguire il parametro RetryDistribution sul criterio in questione:

   Per i blocchi dei casi di eDiscovery:

   ```powershell
   Set-CaseHoldPolicy <policyname> -RetryDistribution
   ```

   Per i criteri di conservazione:

   ```powershell
   Set-RetentionCompliancePolicy <policyname> -RetryDistribution
   ```

4. Contattare il Servizio Supporto Tecnico Clienti Microsoft.

## <a name="error-the-condition-specified-using-http-conditional-headers-is-not-met"></a>Errore: "La condizione specificata tramite le intestazioni condizionali HTTP non è soddisfatta"

When downloading search results using the eDiscovery Export Tool, it's possible you might receive the following error: `System.Net.WebException: The remote server returned an error: (412) The condition specified using HTTP conditional header(s) is not met.` This is transient error, which typically occurs in the Azure Storage location.

### <a name="resolution"></a>Risoluzione

Per risolvere questo problema, riprovare a [scaricare i risultati della](export-search-results.md#step-2-download-the-search-results)ricerca, che riavvierà lo strumento di esportazione di eDiscovery.

## <a name="errorissue-downloaded-export-shows-no-results"></a>Errore/problema: l'esportazione scaricata non mostra risultati

Dopo un'esportazione completata, il download completato tramite lo strumento di esportazione mostra zero file nei risultati.

### <a name="resolution"></a>Risoluzione

This is a client-side issue and in order to remediate it, please attempt the following steps:

1. Prova a usare un altro client/computer per il download.

2. Assicurati di eseguire il download in un'unità locale.

3. Verificare che il programma antivirus non sia in esecuzione.

4. Assicurarsi che nessun'altra esportazione sia in download nella stessa cartella o in qualsiasi cartella padre.

5. Se i passaggi precedenti non sono stati esatti, disabilitare la compressione e la deduplicazione.

6. If this works then the issue is due to a local virus scanner or a disk issue.
