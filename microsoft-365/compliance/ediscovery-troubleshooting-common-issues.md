---
title: Risoluzione dei problemi comuni relativi a eDiscovery
f1.keywords:
- NOCSH
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
description: Esaminare, risolvere i problemi e risolvere i problemi comuni in eDiscovery.
siblings_only: true
ms.openlocfilehash: 5bcbe498cb650268dc8ff6f2b41a6201e75a8192
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631771"
---
# <a name="investigate-troubleshoot-and-resolve-common-ediscovery-issues"></a>Esaminare, risolvere i problemi e risolvere i problemi comuni relativi a eDiscovery

In questo argomento vengono illustrati i passaggi di base per la risoluzione dei problemi che è possibile eseguire per identificare e risolvere i problemi che possono verificarsi durante una ricerca di eDiscovery o altrove nel processo di eDiscovery. La risoluzione di alcuni di questi scenari richiede assistenza da parte del supporto tecnico Microsoft. Informazioni su quando contattare il supporto tecnico Microsoft è incluso nei passaggi di risoluzione.

## <a name="errorissue-ambiguous-location"></a>Errore/problema: posizione ambigua

Se si tenta di aggiungere la posizione della cassetta postale dell'utente alla ricerca e sono presenti oggetti duplicati o in conflitto con lo stesso userID nella directory di Exchange Online Protection (EOP), viene `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous`visualizzato questo errore:. 

### <a name="resolution"></a>Soluzione

Controllare gli utenti duplicati o la lista di distribuzione con lo stesso ID utente.

1. Connettersi a [PowerShell per Centro sicurezza & Compliance](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).

2. Eseguire il seguente comando per recuperare tutte le istanze del nome utente:

    ```powershell
    Get-Recipient <username>
    ```

   L'output per ' useralias@contoso.com ' sarebbe simile al seguente:

   > 
   > |Nome  |RecipientType  |
   > |---------|---------|
   > |Alias, utente     |MailUser         |
   > |Alias, utente     |Utente         |

3. Se vengono restituiti più utenti, individuare e correggere l'oggetto in conflitto.

## <a name="errorissue-search-fails-on-specific-locations"></a>Errore/problema: la ricerca ha esito negativo su percorsi specifici

Un eDiscovery o una ricerca di contenuto può generare l'errore seguente:
>Questa ricerca è stata completata con gli errori (#).  Si desidera riprovare la ricerca nelle posizioni non riuscite?

![Posizione specifica della ricerca non riuscita screenshot di errore](../media/edisc-tshoot-specific-location-search-fails.png)

### <a name="resolution"></a>Soluzione

Se viene visualizzato questo errore, è consigliabile verificare che le posizioni non riuscite nella ricerca rieseguano la ricerca solo nelle posizioni non riuscite.

1. Connettersi a [PowerShell per Centro sicurezza & Compliance](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) e quindi eseguire il comando riportato di seguito:

    ```powershell
    Get-ComplianceSearch <searchname> | FL 
    ```

2. Nell'output di PowerShell, visualizzare le posizioni non riuscite nel campo errori o nei dettagli dello stato nell'errore dall'output di ricerca.

3. Riprovare la ricerca di eDiscovery solo nelle posizioni non riuscite.

4. Se si continua a ricevere questi errori, vedere [retry failed locations](https://docs.microsoft.com/Office365/SecurityCompliance/retry-failed-content-search) for more troubleshooting steps.

## <a name="errorissue-file-not-found"></a>Errore/problema: file non trovato

Quando si esegue una ricerca di eDiscovery che include SharePoint Online e un'unità per le posizioni aziendali, è possibile `File Not Found` che venga visualizzato un errore anche se il file si trova nel sito. Questo errore risulterà negli avvisi di esportazione e negli errori. csv o negli elementi. csv ignorati. Ciò può verificarsi se il file non è stato trovato nel sito o se l'indice non è aggiornato. Di seguito è indicato il testo di un errore reale (con enfasi aggiunta).
  
> 28.06.2019 10:02:19_FailedToExportItem_Failed scaricare il contenuto. Ulteriori informazioni di diagnostica: Microsoft. Office. compliance. EDiscovery. ExportWorker. Exceptions. ContentDownloadTemporaryFailure: failed to download from content 6ea52149-91CD-4965-b5bb-82ca6a3ec9be of Type Document. ID di correlazione: 3bd84722-937b-4c23-b61b-08d6fba9ec32. ServerErrorCode:-2147024894---> Microsoft. SharePoint. client. ServerException: ***file non trovato***. in Microsoft. SharePoint. client. ClientRequest. ProcessResponseStream (Stream responseStream) in Microsoft. SharePoint. client. ClientRequest. ProcessResponse ()---fine dell'analisi dello stack dell'eccezione interna---

### <a name="resolution"></a>Soluzione

1. Controllare la posizione identificata nella ricerca per verificare che il percorso del file sia corretto e che sia stato aggiunto nei percorsi di ricerca.

2. Utilizzare le procedure per eseguire la ricerca per indicizzazione [e reindicizzazione manuale di un sito, di una raccolta o di un elenco](https://docs.microsoft.com/sharepoint/crawl-site-content) per reindicizzare il sito.

## <a name="errorissue-search-fails-because-recipient-is-not-found"></a>Errore/problema: la ricerca ha esito negativo perché il destinatario non viene trovato

Una ricerca di eDiscovery ha esito `recipient not found`negativo con errore. Questo errore può verificarsi se l'oggetto utente non è disponibile in Exchange Online Protection (EOP) perché l'oggetto non è stato sincronizzato.

### <a name="resolution"></a>Soluzione

1. Connettersi a [PowerShell di Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).

2. Eseguire il seguente comando per verificare se l'utente è sincronizzato con Exchange Online Protection:

    ```powershell
    Get-Recipient <userId> | FL
    ```

3. Deve essere presente un oggetto utente di posta elettronica per la domanda dell'utente. Se non viene restituito alcun valore, esaminare l'oggetto User. Se l'oggetto non può essere sincronizzato, contattare il supporto tecnico Microsoft.

## <a name="errorissue-exporting-search-results-is-slow"></a>Errore/problema: l'esportazione dei risultati di ricerca è lenta

Quando si esportano i risultati della ricerca da eDiscovery o ricerca contenuto nel centro sicurezza e conformità, il download richiede più tempo del previsto.  È possibile controllare la quantità di dati da scaricare ed eventualmente aumentare la velocità di esportazione.

### <a name="resolution"></a>Soluzione

1.    Provare a utilizzare i passaggi identificati nell'articolo [aumentare la velocità di download](https://docs.microsoft.com/office365/securitycompliance/increase-download-speeds-when-exporting-ediscovery-results).

2.    In caso di problemi, connettersi al [centro di sicurezza & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) e quindi eseguire il comando seguente:

    ```powershell
    Get-ComplianceSearch <searchname> | FL
    ```

4. Individuare la quantità di dati da scaricare nei parametri SearchResults e SearchStatistics.

5. Eseguire il comando riportato di seguito:

   ```powershell
   Get-ComplianceSearchAction | FL
   ```

6. Nel campo risultati individuare i dati che sono stati esportati e visualizzare gli eventuali errori riscontrati.

7. Controllare il file Trace. log che si trova nella directory in cui è stato esportato il contenuto per eventuali errori.

## <a name="errorissue-internal-server-error-500-occurred"></a>Errore/problema: "errore interno del server (500) si è verificato"

Quando si esegue una ricerca eDiscovery, se la ricerca ha esito negativo con un errore simile a "Internal Server Error (500) si è verificato", potrebbe essere necessario eseguire nuovamente la ricerca solo su percorsi specifici per le cassette postali.

![Errore del server interno 500 screenshot](../media/edisc-tshoot-error-500.png)

### <a name="resolution"></a>Soluzione

1. Suddividere la ricerca in ricerche più piccole ed eseguire di nuovo la ricerca.  Provare a utilizzare un intervallo di date più piccolo o limitare il numero di posizioni in cui è stata eseguita la ricerca.

2. Connettersi a [PowerShell per Centro sicurezza & Compliance](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) e quindi eseguire il comando riportato di seguito:

    ```powershell Set-CaseHoldPolicy <policyname> -RetryDistribution
    Get-ComplianceSearch <searchname> | FL
    ```

3. Esaminare l'output per i risultati e gli errori.

4. Esaminare il file Trace. log. Si trova nella stessa cartella in cui sono stati esportati i risultati della ricerca.

5. Contattare il Servizio Supporto Tecnico Clienti Microsoft.

## <a name="errorissue-holds-dont-sync"></a>Errore/problema: esenzioni non sincronizzate

errore di distribuzione della sincronizzazione del criterio di eDiscovery in caso di blocco. L'errore si legge:

> "Risorse: richiede più tempo del previsto per la distribuzione del criterio. Potrebbe essere necessario un ulteriore 2 ore per aggiornare lo stato di distribuzione finale, in modo da controllare tra un paio di ore.

### <a name="resolution"></a>Soluzione

1.    Connettersi a [PowerShell per il Centro sicurezza & Compliance](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) e quindi eseguire il comando seguente per un blocco di caso di eDiscovery:

    ```powershell
    Get-CaseHoldPolicy <policyname> - DistributionDetail | FL
    ```

    Per un criterio di conservazione, eseguire il comando riportato di seguito:

    ```powershell
    Get-RetentionCompliancePolicy <policyname> - DistributionDetail | FL
    ```

2. Esaminare il valore del parametro DistributionDetail per gli errori analoghi a quelli riportati di seguito:
 
   > Errore: risorse: richiede più tempo del previsto per la distribuzione del criterio. Potrebbe essere necessario un ulteriore 2 ore per aggiornare lo stato di distribuzione finale, in modo da controllare tra un paio di ore. 
   
3. Provare a eseguire il parametro RetryDistribution per il criterio in questione:
   
    
    Per il caso di eDiscovery:

    ```powershell
    Set-CaseHoldPolicy <policyname> -RetryDistribution
    ```

    Per i criteri di conservazione:

    ```powershell
    Set-RetentionCompliancePolicy <policyname> -RetryDistribution
    ``` 

4. Contattare il Servizio Supporto Tecnico Clienti Microsoft.

## <a name="see-also"></a>Vedere anche

- [Suggerimenti per evitare errori di posizione del contenuto](retry-failed-content-search.md#tips-to-avoid-content-location-errors)
