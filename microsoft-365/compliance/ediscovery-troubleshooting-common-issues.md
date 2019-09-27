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
# <a name="investigate-troubleshoot-and-resolve-common-ediscovery-issues"></a>Esaminare, risolvere i problemi e risolverne i problemi comuni relativi a eDiscovery

In questo argomento vengono illustrati i passaggi di base per la risoluzione dei problemi che è possibile eseguire per identificare e risolvere i problemi che possono verificarsi durante una ricerca di eDiscovery o altrove nel processo di eDiscovery. La risoluzione di alcuni di questi scenari richiede assistenza da parte dei servizi di supporto tecnico (CSS). Le informazioni su quando contattare CSS sono incluse nei passaggi di risoluzione.

## <a name="errorissue-ambiguous-location"></a>Errore/percorso ambiguo del problema

Verrà visualizzato questo errore "la ricerca di conformità contiene il percorso `(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous"` non valido seguente se si è tentato di aggiungere la posizione della cassetta postale dell'utente alla ricerca e sono presenti oggetti duplicati o in conflitto con lo stesso ID utente in Exchange Online Protection (EOP) Directory.

### <a name="resolution"></a>Soluzione

Controllare gli utenti duplicati o la lista di distribuzione con lo stesso ID utente.

1. Connettersi a [PowerShell di Exchange Online](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).
2. Recuperare tutte le istanze del nome utente, digitare quanto segue:

```powershell
Get-Recipient <username>
```

L'output per ' useralias@contoso.com ' potrebbe essere

> 
> |Name  |RecipientType  |
> |---------|---------|
> |Alias, utente     |MailUser         |
> |Alias, utente     |Utente         |

3. Se vengono restituiti più utenti, individuare e correggere l'oggetto in conflitto.

## <a name="errorissue-search-fails-on-specific-locations"></a>Errore/problema la ricerca ha esito negativo in posizioni specifiche

Un eDiscovery o una ricerca di contenuto può generare l'errore seguente:
>Questa ricerca è stata completata con gli errori (#).  Si desidera riprovare la ricerca nelle posizioni non riuscite?

![posizione specifica di ricerca non riuscita screenshot di errore]( media/edisc-tshoot-specific-location-search-fails.png)

### <a name="resolution"></a>Soluzione

Se viene visualizzato questo errore, è consigliabile verificare che i percorsi non riusciti nella ricerca rieseguano di nuovo la ricerca solo nelle posizioni non riuscite.

1. Connettersi a [PowerShell di Exchange Online Protection](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps).
1. Tipo

```powershell
Get-Compliancesearch searchname|fl 
```

3. Nell'output di PowerShell, visualizzare le posizioni non riuscite nel campo errori o nei dettagli dello stato nell'errore dall'output di ricerca.
1. Riprovare la ricerca di eDiscovery solo nelle posizioni non riuscite.
1. Se si continua a ricevere questi errori, vedere [tentativi non riusciti](https://docs.microsoft.com/en-us/Office365/SecurityCompliance/retry-failed-content-search) per ulteriori passaggi per la risoluzione dei problemi.

## <a name="errorissue-file-not-found"></a>Errore/problema impossibile trovare il file

Quando si esegue una ricerca di eDiscovery che include SharePoint Online e un'unità per le posizioni aziendali, è possibile `File Not Found` che venga visualizzato un errore anche se il file si trova nel sito. Questo errore si verificherà con gli avvisi di esportazione e gli errori. csv o gli elementi ignorati. csv ciò può verificarsi se il file non può essere posizionato nel sito o se l'indice non è aggiornato. Di seguito è indicato il testo di un errore reale, con enfasi aggiunta.
  
> 28.06.2019 10:02:19_FailedToExportItem_Failed per scaricare il contenuto. Ulteriori informazioni di diagnostica: Microsoft. Office. compliance. EDiscovery. ExportWorker. Exceptions. ContentDownloadTemporaryFailure: failed to download from content 6ea52149-91CD-4965-b5bb-82ca6a3ec9be of Type Document. ID di correlazione: 3bd84722-937b-4c23-b61b-08d6fba9ec32. ServerErrorCode:-2147024894---> Microsoft. SharePoint. client. ServerException: ***file non trovato***. in Microsoft. SharePoint. client. ClientRequest. ProcessResponseStream (Stream responseStream) in Microsoft. SharePoint. client. ClientRequest. ProcessResponse ()---fine dell'analisi dello stack dell'eccezione interna---

### <a name="resolution"></a>Soluzione

1. Controllare la posizione identificata nella ricerca per verificare che il percorso del file sia corretto e che sia stato aggiunto nei percorsi di ricerca.
2. Utilizzare le procedure per eseguire la ricerca per indicizzazione [e reindicizzazione manuale di un sito, una raccolta o un elenco](https://docs.microsoft.com/en-us/sharepoint/crawl-site-content) per reindicizzare il sito.

## <a name="errorissue-search-fails-recipient-not-found"></a>Errore/problema ricerca non riuscito destinatario non trovato

la ricerca eDiscovery ha esito negativo con errore `recipient not found`. Questo errore può verificarsi se l'oggetto utente non è disponibile in Exchange Online Protection (EOP) perché l'oggetto non è stato sincronizzato.

### <a name="resolution"></a>Soluzione

1. Connettersi a [PowerShell di Exchange Online Protection](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps).
1. Controllare se l'oggetto utente è sincronizzato con il tipo di protezione Exchange Online:

```powershell
Get-Recipient userId|fl
```

3. Deve essere presente un oggetto MailUser per la domanda dell'utente. Se non viene restituito alcun valore, esaminare l'oggetto User. Se l'oggetto non può essere sincronizzato, contattare CSS.

## <a name="errorissue-exporting-search-results-is-slow"></a>Errore/problema l'esportazione dei risultati di ricerca è lenta

Quando si esportano i risultati della ricerca da eDiscovery o ricerca contenuto nel centro sicurezza e conformità, il download richiede più tempo del previsto.  È possibile controllare la quantità di dati da scaricare ed eventualmente aumentare la velocità di esportazione.

### <a name="resolution"></a>Soluzione

1.  Provare a utilizzare i passaggi identificati nell'articolo [aumentare la velocità di download](https://docs.microsoft.com/en-us/office365/securitycompliance/increase-download-speeds-when-exporting-ediscovery-results).
2.  Se si dispone ancora di problemi, connettersi a [PowerShell di Exchange Online Protection](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps) e digitare quanto segue:

```powershell
Get-ComplianceSearch searchname\fl
```

4. Individuare la quantità di dati da scaricare nei parametri SearchResults e SearchStatistics.
5. Tipo

```powershell
Get-ComplianceSearchAction |fl
```

6. Nel campo risultati individuare i dati che sono stati esportati e visualizzare gli eventuali errori riscontrati.
7. Controllare il file Trace. log che si trova nella directory in cui è stato esportato il contenuto per eventuali errori.

## <a name="errorissue-internal-server-error-500-occurred"></a>Errore/problema "errore interno del server (500) si è verificato"

Quando si esegue una ricerca eDiscovery, se la ricerca ha esito negativo con un errore simile a "Internal Server Error (500) si è verificato", potrebbe essere necessario eseguire di nuovo la ricerca solo su percorsi specifici per le cassette postali.

![errore del server interno 500 screenshot](media/edisc-tshoot-error-500.png)

### <a name="resolution"></a>Soluzione

1. Suddividere la ricerca in ricerche più piccole ed eseguire di nuovo la ricerca.  Provare a utilizzare un intervallo di date più piccolo o limitare il numero di posizioni in cui è stata eseguita la ricerca.
2. Connettersi a [PowerShell di Exchange Online Protection](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps) e digitare quanto segue:

```powershell
Get-ComplianceSearch searchname |fl
```

3. Esaminare l'output per i risultati e gli errori.
3. Esaminare il file Trace. log. Sarà presente nella stessa cartella in cui è stata inviata l'esportazione.
4. Contattare il supporto CSS.

## <a name="errorissue-holds-dont-sync"></a>Errore/problema contiene non sincronizzare

errore di distribuzione della sincronizzazione del criterio di eDiscovery in caso di blocco. L'errore si legge:

> "Risorse: richiede più tempo del previsto per la distribuzione del criterio. Per aggiornare lo stato di distribuzione finale, potrebbe essere necessario attendere altre due ore, quindi riprovare tra un paio di ore ".

### <a name="resolution"></a>Soluzione

1.  Connettersi a [PowerShell di Exchange Online Protection](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps) e digitare quanto segue:

```powershell
Get-RetentionCompliancePolicy  policyname - Distributiondetail|fl
```

2. Esaminare il valore del parametro Distributiondetail per gli errori analoghi a quelli riportati di seguito:

> Se si verifica un errore, è possibile creare un'escalation a PG per forzare la risincronizzazione manuale del criterio.

3. Contatti CSS.

## <a name="see-also"></a>Vedere anche
- [Suggerimenti per evitare errori di posizione del contenuto](https://docs.microsoft.com/en-us/microsoft-365/compliance/retry-failed-content-search%23tips-to-avoid-content-location-errors)