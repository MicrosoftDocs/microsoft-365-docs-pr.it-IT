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
ms.openlocfilehash: 3d3d0830ac677ea812a0d09793de8214245d6b2a
ms.sourcegitcommit: e5b1a900043e2e41650ea1cbf4227043729c6053
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2021
ms.locfileid: "52060991"
---
# <a name="investigate-troubleshoot-and-resolve-common-ediscovery-issues"></a>Analizzare, risolvere e risolvere i problemi comuni di eDiscovery

In questo argomento vengono illustrati i passaggi di base per la risoluzione dei problemi che è possibile eseguire per identificare e risolvere i problemi che possono verificarsi durante una ricerca eDiscovery o in un altro punto del processo di eDiscovery. La risoluzione di alcuni di questi scenari richiede assistenza da parte del supporto tecnico Microsoft. Le informazioni su quando contattare il supporto Tecnico Microsoft sono incluse nei passaggi di risoluzione.

## <a name="errorissue-ambiguous-location"></a>Errore/problema: percorso ambiguo

Se si tenta di aggiungere la posizione della cassetta postale dell'utente per la ricerca e sono presenti oggetti duplicati o in conflitto con lo stesso ID utente nella directory di Exchange Online Protection (EOP), viene visualizzato questo errore: `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous` .

### <a name="resolution"></a>Risoluzione

Verificare la presenza di utenti duplicati o lista di distribuzione con lo stesso ID utente.

1. Connessione a [PowerShell & Centro sicurezza e conformità](/powershell/exchange/connect-to-scc-powershell).

2. Eseguire il comando seguente per recuperare tutte le istanze del nome utente:

    ```powershell
    Get-Recipient <username>
    ```

   L'output per "useralias@contoso.com" è simile al seguente:

   > 
   > |Nome|RecipientType|
   > |---|---|
   > |Alias, Utente|MailUser|
   > |Alias, Utente|Utente|

3. Se vengono restituiti più utenti, individuare e correggere l'oggetto in conflitto.

## <a name="errorissue-search-fails-on-specific-locations"></a>Errore/problema: la ricerca ha esito negativo in posizioni specifiche

Una ricerca di contenuto o eDiscovery può produrre l'errore seguente: `This search completed with (#) errors.  Would you like to retry the search on the failed locations?`

![Schermata di errore della posizione specifica della ricerca non riesce](../media/edisc-tshoot-specific-location-search-fails.png)

### <a name="resolution"></a>Risoluzione

Se viene visualizzato questo errore, è consigliabile verificare i percorsi non riusciti nella ricerca e quindi eseguire di nuovo la ricerca solo nei percorsi non riusciti.

1. Connessione [a PowerShell & centro](/powershell/exchange/connect-to-scc-powershell) sicurezza e conformità, quindi eseguire il comando seguente:

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. Dall'output di PowerShell, visualizzare le posizioni non riuscite nel campo degli errori o dai dettagli sullo stato nell'errore dall'output della ricerca.

3. Ritentare la ricerca eDiscovery solo nei percorsi con errore.

4. Se si continua a ricevere questi errori, vedere [Riprovare](/Office365/SecurityCompliance/retry-failed-content-search) percorsi non riusciti per ulteriori procedure di risoluzione dei problemi.

## <a name="errorissue-file-not-found"></a>Errore/problema: file non trovato

Quando si esegue una ricerca eDiscovery che include posizioni di SharePoint Online e One Drive For Business, è possibile che venga visualizzato l'errore anche se il file si `File Not Found` trova nel sito. Questo errore verrà visualizzato negli avvisi di esportazione e errors.csv o ignorato items.csv. Ciò può verificarsi se non è possibile trovare il file nel sito o se l'indice non è aggiornato. Ecco il testo di un errore effettivo (con enfasi aggiunta).

> 28.06.2019 10:02:19_FailedToExportItem_Failed per scaricare il contenuto. Informazioni di diagnostica aggiuntive: Microsoft. Office. Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure: impossibile eseguire il download dal contenuto 6ea52149-91cd-4965-b5bb-82ca6a3ec9be di tipo Document. ID correlazione: 3bd84722-937b-4c23-b61b-08d6fba9ec32. ServerErrorCode: -2147024894 ---> Microsoft. SharePoint. Client.ServerException: ***file non trovato.*** presso Microsoft. SharePoint. Client.ClientRequest.ProcessResponseStream(Stream responseStream) presso Microsoft. SharePoint. Client.ClientRequest.ProcessResponse() --- fine dell'analisi dello stack delle eccezioni interne ---

### <a name="resolution"></a>Risoluzione

1. Controllare il percorso identificato nella ricerca per verificare che il percorso del file sia corretto e aggiunto nei percorsi di ricerca.

2. Utilizzare le procedure descritte in Richiedere manualmente la ricerca per indicizzazione e la reindicizzazione di un [sito,](/sharepoint/crawl-site-content) di una raccolta o di un elenco per reindicizzare il sito.

## <a name="errorissue-search-fails-because-recipient-is-not-found"></a>Errore/problema: la ricerca ha esito negativo perché il destinatario non è stato trovato

Una ricerca eDiscovery ha esito negativo con l'errore `recipient not found` . Questo errore può verificarsi se non è possibile trovare l'oggetto utente in Exchange Online Protection (EOP) perché l'oggetto non è stato sincronizzato.

### <a name="resolution"></a>Risoluzione

1. Connessione a [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Eseguire il comando seguente per verificare se l'utente è sincronizzato con Exchange Online Protection:

   ```powershell
   Get-Recipient <userId> | FL
   ```

3. Deve essere presente un oggetto utente di posta per la domanda dell'utente. Se non viene restituito alcun valore, analizzare l'oggetto utente. Contattare il supporto tecnico Microsoft se l'oggetto non può essere sincronizzato.

## <a name="errorissue-exporting-search-results-is-slow"></a>Errore/problema: l'esportazione dei risultati della ricerca è lenta

Quando si esportano i risultati della ricerca da eDiscovery o Ricerca contenuto nel Centro sicurezza e conformità, il download richiede più tempo del previsto.  Puoi controllare la quantità di dati da scaricare ed eventualmente aumentare la velocità di esportazione.

### <a name="resolution"></a>Risoluzione

1. Connessione [a PowerShell & centro](/powershell/exchange/connect-to-scc-powershell) sicurezza e conformità, quindi eseguire il comando seguente:

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. Trova la quantità di dati da scaricare nei parametri SearchResults e SearchStatistics.

3. Eseguire il comando seguente:

   ```powershell
   Get-ComplianceSearchAction | FL
   ```

4. Nel campo dei risultati individuare i dati esportati e visualizzare gli eventuali errori riscontrati.

5. Verificare la presenza di eventuali errori nel file trace.log presente nella directory in cui è stato esportato il contenuto.

6. Se si verificano ancora problemi, è consigliabile suddividere le ricerche che restituiscono un set di risultati di grandi dimensioni in ricerche più piccole. È ad esempio possibile utilizzare intervalli di date nelle query di ricerca per restituire un set più piccolo di risultati che possono essere scaricati più velocemente.

## <a name="errorissue-internal-server-error-500-occurred"></a>Errore/problema: "Errore interno del server (500) si è verificato"

Quando si esegue una ricerca eDiscovery, se la ricerca continuamente non riesce con un errore simile a "Errore interno del server (500) si è verificato", potrebbe essere necessario eseguire di nuovo la ricerca solo in posizioni specifiche delle cassette postali.

![Screenshot dell'errore interno del server 500](../media/edisc-tshoot-error-500.png)

### <a name="resolution"></a>Risoluzione

1. Suddividere la ricerca in ricerche più piccole ed eseguire di nuovo la ricerca.  Provare a utilizzare un intervallo di date più piccolo o limitare il numero di posizioni in cui si sta ricercando.

2. Connessione [a PowerShell & centro](/powershell/exchange/connect-to-scc-powershell) sicurezza e conformità, quindi eseguire il comando seguente:

   ```powershell Set-CaseHoldPolicy <policyname> -RetryDistribution
   Get-ComplianceSearch <searchname> | FL
   ```

3. Esaminare l'output per ottenere risultati ed errori.

4. Esaminare il file trace.log. Si trova nella stessa cartella in cui sono stati esportati i risultati della ricerca.

5. Contattare il Servizio Supporto Tecnico Clienti Microsoft.

## <a name="errorissue-holds-dont-sync"></a>Errore/problema: i blocchi non vengono sincronizzati

Errore di distribuzione della sincronizzazione dei criteri di blocco del caso di eDiscovery. L'errore è:

> "Risorse: la distribuzione del criterio richiede più tempo del previsto. L'aggiornamento dello stato finale della distribuzione potrebbe richiedere altre 2 ore, quindi controllare di nuovo tra un paio d'ore."

### <a name="resolution"></a>Risoluzione

1. Connessione a [PowerShell &](/powershell/exchange/connect-to-scc-powershell) Centro sicurezza e conformità, quindi eseguire il comando seguente per un blocco caso di eDiscovery:

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

Quando si scaricano i risultati della ricerca utilizzando lo strumento di esportazione di eDiscovery, è possibile che venga visualizzato l'errore seguente: Si tratta di un errore temporaneo, che in genere si verifica nel percorso Archiviazione di Azure `System.Net.WebException: The remote server returned an error: (412) The condition specified using HTTP conditional header(s) is not met.` ricerca.

### <a name="resolution"></a>Risoluzione

Per risolvere questo problema, ritentare [il download dei risultati della](export-search-results.md#step-2-download-the-search-results)ricerca, che riavvierà lo strumento di esportazione di eDiscovery.

## <a name="errorissue-downloaded-export-shows-no-results"></a>Errore/problema: l'esportazione scaricata non mostra risultati

Dopo un'esportazione completata, il download completato tramite lo strumento di esportazione mostra zero file nei risultati.

### <a name="resolution"></a>Risoluzione

Si tratta di un problema sul lato client e per risolvere il problema, provare a eseguire la procedura seguente:

1. Prova a usare un altro client/computer per il download.

2. Rimuovere le ricerche precedenti non più necessarie utilizzando il cmdlet [Remove-ComplianceSearch][/powershell/module/exchange/remove-compliancesearch].

3. Assicurati di eseguire il download in un'unità locale.

4. Verificare che il programma antivirus non sia in esecuzione.

5. Assicurarsi che nessun'altra esportazione sia in download nella stessa cartella o in qualsiasi cartella padre.

6. Se i passaggi precedenti non sono stati esatti, disabilitare la compressione e la deduplicazione.

7. Se funziona, il problema è dovuto a un programma antivirus locale o a un problema del disco.
