---
title: Usare uno script PowerShell per la ricerca nel log di audit
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom: seo-marvel-apr2020
description: Usare uno script di PowerShell che esegue il cmdlet Search-UnifiedAuditLog in Exchange Online per cercare il log di audit. Questo script è ottimizzato per restituire un set di record di controllo di grandi dimensioni (fino a 50.000). Lo script esporta questi record in un file CSV che è possibile visualizzare o trasformare usando Power Query in Excel.
ms.openlocfilehash: df5e675e5e36603a73078bd5ecf5e64bc7a76f95
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939566"
---
# <a name="use-a-powershell-script-to-search-the-audit-log"></a>Usare uno script PowerShell per la ricerca nel log di audit

La sicurezza, la conformità e il controllo sono diventati una priorità assoluta per gli amministratori IT al giorno d’oggi. Microsoft 365 offre diverse funzionalità incorporate per aiutare le organizzazioni a gestire la sicurezza, la conformità e il controllo. In particolare, la registrazione di controllo unificata consente di esaminare gli incidenti di sicurezza e i problemi di conformità. È possibile recuperare i log di audit usando i metodi seguenti:

- [L’API Office 365 Management Activity](/office/office-365-management-api/office-365-management-activity-api-reference)

- Lo [strumento di ricerca nel log di audit](search-the-audit-log-in-security-and-compliance.md) nel Centro conformità Microsoft 365

- Il cmdlet [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog) in Exchange Online PowerShell

Se è necessario recuperare regolarmente i log di audit, è consigliabile prendere in considerazione una soluzione che usi l'API Office 365 Management Activity, in quanto può offrire alle organizzazioni di grandi dimensioni la scalabilità e le prestazioni per recuperare milioni di record di controllo in modo continuativo. L'uso dello strumento di ricerca nel log di audit nel Centro conformità Microsoft 365 è un ottimo modo per trovare rapidamente i record di controllo per operazioni specifiche che si verificano in un intervallo di tempo più breve. L'uso di intervalli di tempo più lunghi nello strumento di ricerca nel log di audit, in particolare per le organizzazioni di grandi dimensioni, potrebbe restituire una quantità di record troppo elevata per essere gestita o esportata facilmente.

In situazioni in cui è necessario recuperare manualmente i dati di controllo per un'indagine o un incidente specifico, in particolare per intervalli di date più lunghi nelle organizzazioni di grandi dimensioni, l'uso del cmdlet **Search-UnifiedAuditLog** può essere l'opzione migliore. Questo articolo include uno script PowerShell che usa il cmdlet per recuperare fino a 50.000 record di controllo e quindi esportarli in un file CSV che può essere formattato con Power Query in Excel per assistere nella revisione. L'uso dello script in questo articolo consente anche di ridurre al minimo la possibilità che le ricerche nel log di audit di grandi dimensioni raggiungano il timeout nel servizio.

## <a name="before-you-run-the-script"></a>Prima di eseguire lo script

- La registrazione di controllo deve essere abilitata per l'organizzazione per poter usare correttamente lo script per restituire record di controllo. La registrazione di controllo è attivata per impostazione predefinita per le organizzazioni di Microsoft 365 e Office 365 Enterprise. Per verificare che la ricerca nel registro di controllo sia attivata per l’organizzazione, è possibile eseguire il comando seguente in Exchange Online PowerShell:

  ```powershell
  Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
  ```

  Il valore `True` per la proprietà **UnifiedAuditLogIngestionEnabled** indica che la ricerca nel log di audit è attivata.

- È necessario avere il ruolo Log di audit di sola lettura o Log di audit in Exchange Online per poter eseguire correttamente lo script. Per impostazione predefinita, questi ruoli sono assegnati ai gruppi di ruoli Gestione conformità e Gestione organizzazione nella pagina Autorizzazioni nell'Interfaccia di amministrazione di Exchange. Per altre informazioni, vedere la sezione "Requisiti per eseguire ricerche nel log di audit" in [Eseguire una ricerca nel log di audit nel Centro conformità](search-the-audit-log-in-security-and-compliance.md#requirements-to-search-the-audit-log).

- Il completamento dello script può richiedere molto tempo. Il tempo necessario per l'esecuzione dipende dall'intervallo di date e dalle dimensioni dell'intervallo per cui si configura lo script per il recupero dei record di controllo. Date più distanziate con intervalli più piccoli comportano una durata di esecuzione maggiore. Per altre informazioni sull'intervallo di date e sugli intervalli, vedere la tabella del passaggio 2.

- Lo script di esempio fornito in questo articolo non è supportato in alcun programma o servizio di supporto standard Microsoft. Viene fornito COSÌ COM'È senza garanzie di alcun tipo. Microsoft esclude inoltre qualsiasi garanzia implicita, tra cui, senza limitazioni, tutte le garanzie implicite di commerciabilità o idoneità per uno scopo specifico. L'utente si assume tutti i rischi associati all'uso o alle prestazioni dello script di esempio e della documentazione. In nessun caso Microsoft, i suoi autori o chiunque altro coinvolto nella creazione, nella produzione o nella distribuzione degli script potranno essere ritenuti responsabili per eventuali danni di qualsiasi tipo (tra cui, senza limitazioni, danni per perdita di informazioni aziendali o profitti, interruzione dell'attività o altre perdite economiche) derivanti dall'uso o dall'impossibilità a usare gli script di esempio o la documentazione, anche se Microsoft è stata avvisata della possibilità di tali danni.

## <a name="step-1-connect-to-exchange-online-powershell"></a>Passaggio 1: Connettersi a Exchange Online PowerShell

La prima operazione da eseguire consiste nel connettersi a Exchange Online PowerShell. È possibile connettersi usando l'autenticazione moderna o l'autenticazione a più fattori (MFA). Per istruzioni dettagliate, vedere [Connettersi a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

## <a name="step-2-modify-and-run-the-script-to-retrieve-audit-records"></a>Passaggio 2: Modificare ed eseguire lo script per recuperare i record di controllo

Dopo aver eseguito la connessione a Exchange Online PowerShell, il passaggio successivo consiste nel creare, modificare ed eseguire lo script per recuperare i dati di controllo. Le prime sette righe dello script di ricerca nel log di audit contengono le variabili seguenti che è possibile modificare per configurare la ricerca. Per la descrizione di queste variabili, vedere la tabella nel passaggio 2.

1. Salvare il testo seguente in uno script di Windows PowerShell usando il suffisso del nome .ps1. Per esempio, SearchAuditLog.ps1.

   ```powershell
   #Modify the values for the following variables to configure the audit log search.
   $logFile = "d:\AuditLogSearch\AuditLogSearchLog.txt"
   $outputFile = "d:\AuditLogSearch\AuditLogRecords.csv"
   [DateTime]$start = [DateTime]::UtcNow.AddDays(-1)
   [DateTime]$end = [DateTime]::UtcNow
   $record = "AzureActiveDirectory"
   $resultSize = 5000
   $intervalMinutes = 60
   
   #Start script
   [DateTime]$currentStart = $start
   [DateTime]$currentEnd = $start
   
   Function Write-LogFile ([String]$Message)
   {
       $final = [DateTime]::Now.ToUniversalTime().ToString("s") + ":" + $Message
       $final | Out-File $logFile -Append
   }
   
   Write-LogFile "BEGIN: Retrieving audit records between $($start) and $($end), RecordType=$record, PageSize=$resultSize."
   Write-Host "Retrieving audit records for the date range between $($start) and $($end), RecordType=$record, ResultsSize=$resultSize"
   
   $totalCount = 0
   while ($true)
   {
       $currentEnd = $currentStart.AddMinutes($intervalMinutes)
       if ($currentEnd -gt $end)
       {
           $currentEnd = $end
       }
   
       if ($currentStart -eq $currentEnd)
       {
           break
       }
   
       $sessionID = [Guid]::NewGuid().ToString() + "_" +  "ExtractLogs" + (Get-Date).ToString("yyyyMMddHHmmssfff")
       Write-LogFile "INFO: Retrieving audit records for activities performed between $($currentStart) and $($currentEnd)"
       Write-Host "Retrieving audit records for activities performed between $($currentStart) and $($currentEnd)"
       $currentCount = 0
   
       $sw = [Diagnostics.StopWatch]::StartNew()
       do
       {
           $results = Search-UnifiedAuditLog -StartDate $currentStart -EndDate $currentEnd -RecordType $record -SessionId $sessionID -SessionCommand ReturnLargeSet -ResultSize $resultSize
   
           if (($results | Measure-Object).Count -ne 0)
           {
               $results | export-csv -Path $outputFile -Append -NoTypeInformation
   
               $currentTotal = $results[0].ResultCount
               $totalCount += $results.Count
               $currentCount += $results.Count
               Write-LogFile "INFO: Retrieved $($currentCount) audit records out of the total $($currentTotal)"
   
               if ($currentTotal -eq $results[$results.Count - 1].ResultIndex)
               {
                   $message = "INFO: Successfully retrieved $($currentTotal) audit records for the current time range. Moving on!"
                   Write-LogFile $message
                   Write-Host "Successfully retrieved $($currentTotal) audit records for the current time range. Moving on to the next interval." -foregroundColor Yellow
                   ""
                   break
               }
           }
       }
       while (($results | Measure-Object).Count -ne 0)
   
       $currentStart = $currentEnd
   }
   
   Write-LogFile "END: Retrieving audit records between $($start) and $($end), RecordType=$record, PageSize=$resultSize, total count: $totalCount."
   Write-Host "Script complete! Finished retrieving audit records for the date range between $($start) and $($end). Total count: $totalCount" -foregroundColor Green
   ```

2. Modificare le variabili elencate nella tabella seguente per configurare i criteri di ricerca. Lo script include valori di esempio per queste variabili, ma è consigliabile modificarli (se non diversamente specificato) in modo da soddisfare i requisiti specifici.

   <br>

   ****

   |Variabile|Valore esemplificativo|Descrizione|
   |---|---|---|
   |`$logFile`|"d:\temp\AuditSearchLog.txt"|Specifica il nome e il percorso del file di log che contiene informazioni sullo stato della ricerca nel log di audit eseguita dallo script. Lo script scrive i timestamp UTC nel file di log.|
   |`$outputFile`|"d:\temp\AuditRecords.csv"|Specifica il nome e il percorso del file CSV che contiene i record di controllo restituiti dallo script.|
   |`[DateTime]$start` e `[DateTime]$end`|[DateTime]::UtcNow.AddDays(-1) <br/>[DateTime]::UtcNow|Specifica l'intervallo di date per la ricerca nel log di audit. Lo script restituirà i record per le attività di controllo che si sono verificate all’interno dell'intervallo di date specificato. Ad esempio, per restituire le attività eseguite nel mese di gennaio 2021, è possibile usare una data di inizio `"2021-01-01"` e una data di fine `"2021-01-31"` (racchiudere i valori tra virgolette doppie). Il valore di esempio nello script restituisce i record per le attività eseguite nelle 24 ore precedenti. Se non si include un timestamp nel valore, viene utilizzato il timestamp predefinito 00:00 (mezzanotte) nella data specificata.|
   |`$record`|"AzureActiveDirectory"|Specifica il tipo di record delle attività di controllo (chiamate anche *operazioni*) da cercare. Questa proprietà indica il servizio o la caratteristica in cui è stata attivata un'attività. Per un elenco dei tipi di record che è possibile usare per questa variabile, vedere [Tipo di record del log di audit](/office/office-365-management-api/office-365-management-activity-api-schema#auditlogrecordtype). È possibile usare il nome del tipo di record o il valore di enumerazione. <br/><br/>**Suggerimento:** per restituire i record di controllo per tutti i tipi di record, usare il valore `$null` (senza virgolette).|
   |`$resultSize`|5000|Specifica il numero di risultati restituiti ogni volta che il cmdlet **Search-UnifiedAuditLog** viene chiamato dallo script (definito come *set di risultati*). 5000 è il valore massimo supportato dal cmdlet. Lasciare questo valore così come è.|
   |`$intervalMinutes`|60|Per superare il limite di 5000 record restituiti, questa variabile accetta l'intervallo di dati specificato e lo suddivide in intervalli di tempo inferiori. Ora ogni intervallo, e non l'intervallo di date intero, è soggetto al limite di output di 5000 record del comando. Il valore predefinito di 5000 record per intervallo di 60 minuti all’interno dell'intervallo di date deve essere sufficiente per la maggior parte delle organizzazioni. Tuttavia, se lo script restituisce un errore che indica `maximum results limitation reached`, ridurre l'intervallo di tempo, ad esempio a 30 o anche 15 minuti, ed eseguire di nuovo lo script.|
   ||||

   La maggior parte delle variabili elencate nella tabella precedente corrispondono ai parametri per il cmdlet **Search-UnifiedAuditLog**. Per ulteriori informazioni su questi parametri, vedere [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog).

3. Aprire Windows PowerShell sul computer locale e passare alla cartella in cui è stato salvato lo script modificato.

4. Eseguire lo script in Exchange Online PowerShell, ad esempio:

   ```powershell
   .\SearchAuditLog.ps1
   ```

Lo script visualizza i messaggi di stato mentre è in esecuzione. Al termine dell'esecuzione, lo script crea il file di log e il file CSV che contiene i record di controllo e li salva nelle cartelle definite dalle variabili `$logFile` e `$outputFile`.

> [!IMPORTANT]
> Esiste un limite di 50.000 per il numero massimo di record di controllo restituiti ogni volta che si esegue questo script. Se si esegue questo script e vengono restituiti 50.000 risultati, è probabile che i record di controllo per le attività che si sono verificate all’interno dell'intervallo di date non siano stati inclusi. In questo caso, è consigliabile dividere l'intervallo di date in durate più piccole e quindi eseguire di nuovo lo script per ogni intervallo di date. Ad esempio, se un intervallo di date di 90 giorni restituisce 50.000 risultati, è possibile eseguire di nuovo lo script in due volte, una per i primi 45 giorni nell'intervallo di date e la seconda per i 45 giorni seguenti.

## <a name="step-3-format-and-view-the-audit-records"></a>Passaggio 3: Formattare e visualizzare i record di controllo

Dopo aver eseguito lo script ed esportato i record di controllo in un file CSV, è possibile formattare il file CSV per semplificare la revisione e l'analisi dei record di controllo. Un modo per farlo è la funzionalità di trasformazione JSON di Power Query in Excel per suddividere ogni proprietà della colonna **AuditData** nell'oggetto JSON in colonne specifiche. Per istruzioni dettagliate, vedere “Passaggio 2: Formattare il log di audit esportato usando l’editor di Power Query” in [Esportare, configurare e visualizzare i record del log di audit](export-view-audit-log-records.md#step-2-format-the-exported-audit-log-using-the-power-query-editor).
