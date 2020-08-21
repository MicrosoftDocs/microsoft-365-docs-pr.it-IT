---
title: Creare, analizzare ed eliminare più ricerche di contenuto
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- SPO_Content
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: 1d463dda-a3b5-4675-95d4-83db19c9c4a3
description: Informazioni su come automatizzare le attività di ricerca contenuto come la creazione di ricerche e l'esecuzione di report tramite gli script di PowerShell nel centro sicurezza & compliance in Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d748e12942fa2d634f27c04de37ccf5b3ec19297
ms.sourcegitcommit: 260bbb93bbda62db9e88c021ccccfa75ac39a32e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2020
ms.locfileid: "46845898"
---
# <a name="create-report-on-and-delete-multiple-content-searches"></a>Creare, analizzare ed eliminare più ricerche di contenuto

 Creare rapidamente e segnalare le ricerche di individuazione è spesso un passaggio importante in eDiscovery e nelle indagini quando si cerca di conoscere i dati sottostanti e la ricchezza e la qualità delle ricerche. Per eseguire questa operazione, la sicurezza & Compliance Center PowerShell offre un set di cmdlet per automatizzare le attività di ricerca del contenuto in termini di tempo. Questi script consentono di creare una serie di ricerche in modo semplice e rapido e quindi di eseguire i report dei risultati di ricerca stimati che consentono di determinare la quantità di dati in questione. È inoltre possibile utilizzare gli script per creare diverse versioni delle ricerche per confrontare i risultati prodotti da ognuno di essi. Questi script consentono di identificare e abbattere i dati in modo rapido ed efficiente.

## <a name="before-you-create-a-content-search"></a>Prima di creare una ricerca di contenuto

- Per eseguire gli script descritti in questo argomento, è necessario essere membri del gruppo di ruoli eDiscovery Manager nel centro sicurezza & Compliance.

- Per raccogliere un elenco degli URL per i siti di OneDrive for business nell'organizzazione che è possibile aggiungere al file CSV nel passaggio 1, vedere [creare un elenco di tutti i percorsi di OneDrive nell'organizzazione](https://docs.microsoft.com/onedrive/list-onedrive-urls).

- Assicurarsi di salvare tutti i file creati in questo argomento nella stessa cartella. Questo renderà più facile eseguire gli script.

- Gli script includono la gestione degli errori minima. Lo scopo principale consiste nel creare rapidamente, riferire ed eliminare più ricerche di contenuto.

- Gli script di esempio forniti in questo articolo non sono supportati da alcun programma o servizio standard di supporto Microsoft. Gli script di esempio sono forniti così come sono senza alcun tipo di garanzia. Inoltre Microsoft declina ogni responsabilità su garanzie implicite, senza alcuna limitazione, incluse le garanzie implicite di commerciabilità e/o adeguatezza per uno scopo specifico. Qualsiasi rischio eventuale pervenga, durante l'utilizzo degli script di esempio e della documentazione, si intende a carico dell'utente. In nessun caso Microsoft, i suoi autori o chiunque altro coinvolto nella creazione, produzione o consegna degli script è da ritenersi responsabile per qualsiasi danno eventuale (inclusi, senza limitazione alcuna, danni riguardanti profitti aziendali, interruzione di attività, perdita di informazioni aziendali o altra perdita pecuniaria) derivanti dall'utilizzo o dall'incapacità di utilizzo degli script di esempio e della documentazione, anche nel caso in cui Microsoft sia stata avvisata della possibilità di tali danni.

## <a name="step-1-create-a-csv-file-that-contains-information-about-the-searches-you-want-to-run"></a>Passaggio 1: creare un file CSV che contiene informazioni sulle ricerche che si desidera eseguire

Il file con valori delimitati da virgole (CSV) creato in questo passaggio contiene una riga per ogni utente che desidera eseguire la ricerca. È possibile eseguire una ricerca nella cassetta postale di Exchange Online dell'utente (che include la cassetta postale di archiviazione, se abilitata) e il sito di OneDrive for business. In alternativa, è possibile cercare solo la cassetta postale o il sito di OneDrive for business. È inoltre possibile cercare qualsiasi sito nell'organizzazione di SharePoint Online. Lo script eseguito nel passaggio 3 creerà una ricerca distinta per ogni riga del file CSV.

1. Copiare e incollare il testo seguente in un file txt tramite il blocco note. Salvare il file in una cartella nel computer locale. Gli altri script vengono salvati anche in questa cartella.

   ```text
   ExchangeLocation,SharePointLocation,ContentMatchQuery,StartDate,EndDate
   sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2000,12/31/2005
   sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2006,12/31/2010
   sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2011,3/21/2016
   ,https://contoso.sharepoint.com/sites/contoso,,,3/21/2016
   ,https://contoso-my.sharepoint.com/personal/davidl_contoso_onmicrosoft_com,,1/1/2015,
   ,https://contoso-my.sharepoint.com/personal/janets_contoso_onmicrosoft_com,,1/1/2015,
   ```

   La prima riga, o riga di intestazione, del file elenca i parametri che verranno utilizzati dal cmdlet **New-ComplianceSearch** (nello script nel passaggio 3) per creare nuove ricerche di contenuto. Ogni nome di parametro è separato da una virgola. Verificare che non vi siano spazi nella riga di intestazione. Ogni riga sotto la riga di intestazione rappresenta i valori dei parametri per ogni ricerca. Assicurarsi di sostituire i dati segnaposto nel file CSV con i dati effettivi.

2. Aprire il file. txt in Excel e quindi utilizzare le informazioni riportate nella tabella seguente per modificare il file con le informazioni per ogni ricerca.

   ****

   |Parametro|Descrizione|
   |---|---|
   |`ExchangeLocation`|L'indirizzo SMTP della cassetta postale dell'utente.|
   |`SharePointLocation`|L'URL del sito di OneDrive for business dell'utente o l'URL di qualsiasi sito nell'organizzazione. Per l'URL per i siti di OneDrive for business, utilizzare questo formato: ` https://<your organization>-my.sharepoint.com/personal/<user alias>_<your organization>_onmicrosoft_com ` . Ad esempio,  `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com`.|
   |`ContentMatchQuery`|Query di ricerca per la ricerca. Per ulteriori informazioni sulla creazione di una query di ricerca, vedere [keyword queries and Search Conditions for content search](keyword-queries-and-search-conditions.md).|
   |`StartDate`|Per la posta elettronica, la data o dopo che un messaggio è stato ricevuto da un destinatario o inviato dal mittente. Per i documenti sui siti di SharePoint o OneDrive for business, la data in cui è stato modificato l'ultima volta un documento.|
   |`EndDate`|Per la posta elettronica, la data su o prima che un messaggio è stato inviato da un utente. Per i documenti nei siti di SharePoint o OneDrive for business, la data di inizio o di fine di un documento è stata modificata.|
   |

3. Salvare il file di Excel come file CSV in una cartella del computer locale. Lo script creato nel passaggio 3 utilizzerà le informazioni contenute in questo file CSV per creare le ricerche.

## <a name="step-2-connect-to-security--compliance-center-powershell"></a>Passaggio 2: Connettersi a PowerShell in Centro sicurezza e conformità

Il passaggio successivo consiste nel connettersi a PowerShell in Centro sicurezza e conformità per l'organizzazione. Per ottenere istruzioni dettagliate, vedere [Connettersi a PowerShell in Centro sicurezza e conformità](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).

## <a name="step-3-run-the-script-to-create-and-start-the-searches"></a>Passaggio 3: eseguire lo script per creare e avviare le ricerche

Lo script in questo passaggio creerà una ricerca di contenuto distinta per ogni riga del file CSV creato nel passaggio 1. Quando si esegue questo script, verranno richiesti due valori:

- **ID gruppo di ricerca** -questo nome fornisce un modo semplice per organizzare le ricerche create dal file CSV. Tutte le ricerche create vengono denominate con l'ID del gruppo di ricerca e quindi viene aggiunto un numero al nome della ricerca. Ad esempio, se si immette **ContosoCase** per l'ID del gruppo di ricerca, le ricerche vengono denominate **ContosoCase_1**, **ContosoCase_2**, **ContosoCase_3**e così via. Si noti che il nome digitato è distinzione tra maiuscole e minuscole. Quando si utilizza l'ID del gruppo di ricerca nel passaggio 4 e nel passaggio 5, è necessario utilizzare lo stesso caso in cui è stato creato.

- **File CSV** : il nome del file CSV creato nel passaggio 1. Assicurarsi di includere l'utilizzo del nome file completo, includere l'estensione del file CSV. ad esempio,  `ContosoCase.csv` .

Per eseguire lo script:

1. Salvare il testo seguente in un file di script di Windows PowerShell utilizzando un suffisso FileName di. ps1. ad esempio, `CreateSearches.ps1` . Salvare il file nella stessa cartella in cui sono stati salvati gli altri file.

   ```Powershell
   # Get the Search Group ID and the location of the CSV input file
   $searchGroup = Read-Host 'Search Group ID'
   $csvFile = Read-Host 'Source CSV file'

   # Do a quick check to make sure our group name will not collide with other searches
   $searchCounter = 1
   import-csv $csvFile |
     ForEach-Object{

     $searchName = $searchGroup +'_' + $searchCounter
     $search = Get-ComplianceSearch $searchName -EA SilentlyContinue
     if ($search)
     {
        Write-Error "The Search Group ID conflicts with existing searches.  Please choose a search group name and restart the script."
        return
     }
     $searchCounter++
   }

   $searchCounter = 1
   import-csv $csvFile |
     ForEach-Object{

     # Create the query
     $query = $_.ContentMatchQuery
     if(($_.StartDate -or $_.EndDate))
     {
          # Add the appropriate date restrictions.  NOTE: Using the Date condition property here because it works across Exchange, SharePoint, and OneDrive for Business.
          # For Exchange, the Date condition property maps to the Sent and Received dates; for SharePoint and OneDrive for Business, it maps to Created and Modified dates.
          if($query)
          {
              $query += " AND"
          }
          $query += " ("
          if($_.StartDate)
          {
              $query += "Date >= " + $_.StartDate
          }
          if($_.EndDate)
          {
              if($_.StartDate)
              {
                  $query += " AND "
              }
              $query += "Date <= " + $_.EndDate
          }
          $query += ")"
     }

     # -ExchangeLocation can't be set to an empty string, set to null if there's no location.
     $exchangeLocation = $null
     if ( $_.ExchangeLocation)
     {
           $exchangeLocation = $_.ExchangeLocation
     }

     # Create and run the search
     $searchName = $searchGroup +'_' + $searchCounter
     Write-Host "Creating and running search: " $searchName -NoNewline
     $search = New-ComplianceSearch -Name $searchName -ExchangeLocation $exchangeLocation -SharePointLocation $_.SharePointLocation -ContentMatchQuery $query

     # Start and wait for each search to complete
     Start-ComplianceSearch $search.Name
     while ((Get-ComplianceSearch $search.Name).Status -ne "Completed")
     {
        Write-Host " ." -NoNewline
        Start-Sleep -s 3
     }
     Write-Host ""

     $searchCounter++
   }
   ```

2. In Windows PowerShell, passare alla cartella in cui è stato salvato lo script nel passaggio precedente, quindi eseguire lo script. Per esempio:

   ```Powershell
   .\CreateSearches.ps1
   ```

3. Al prompt **ID gruppo di ricerca** Digitare il nome di un gruppo di ricerca e quindi premere **invio**. ad esempio,  `ContosoCase` . Tenere presente che questo nome è distinzione tra maiuscole e minuscole, quindi sarà necessario digitarlo nello stesso modo nei passaggi successivi.

4. Al prompt dei **file CSV di origine** Digitare il nome del file CSV, inclusa l'estensione del file CSV. ad esempio,  `ContosoCase.csv` .

5. Premere **invio** per continuare a eseguire lo script.

   Nello script viene visualizzato lo stato di avanzamento della creazione e dell'esecuzione delle ricerche. Al termine dell'esecuzione dello script, viene restituito il prompt.

   ![Output di esempio dall’esecuzione dello script per creare ricerche di conformità multiple](../media/37d59b0d-5f89-4dbc-9e2d-0e88e2ed7b4c.png)

## <a name="step-4-run-the-script-to-report-the-search-estimates"></a>Passaggio 4: eseguire lo script per segnalare le stime di ricerca

Dopo aver creato le ricerche, il passaggio successivo consiste nell'eseguire uno script che consente di visualizzare un report semplice del numero di hit di ricerca per ogni ricerca creata al passaggio 3. Il report include anche le dimensioni dei risultati per ogni ricerca e il numero totale di hit e dimensioni totali di tutte le ricerche. Quando si esegue lo script dei report, viene richiesto l'ID del gruppo di ricerca e un nome di file CSV Se si desidera salvare il report in un file CSV.

1. Salvare il testo seguente in un file di script di Windows PowerShell utilizzando un suffisso FileName di. ps1. ad esempio, `SearchReport.ps1` . Salvare il file nella stessa cartella in cui sono stati salvati gli altri file.

   ```Powershell
   $searchGroup = Read-Host 'Search Group ID'
   $outputFile = Read-Host 'Enter a file name or file path to save the report to a .csv file. Leave blank to only display the report'
   $searches = Get-ComplianceSearch | ?{$_.Name -clike $searchGroup + "_*"}
   $allSearchStats = @()
   foreach ($partialObj in $searches)
   {
      $search = Get-ComplianceSearch $partialObj.Name
      $sizeMB = [System.Math]::Round($search.Size / 1MB, 2)
      $searchStatus = $search.Status
      if($search.Errors)
      {
          $searchStatus = "Failed"
      }elseif($search.NumFailedSources -gt 0)
      {
          $searchStatus = "Failed Sources"
      }
      $searchStats = New-Object PSObject
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name Name -Value $search.Name
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name ContentMatchQuery -Value $search.ContentMatchQuery
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name Status -Value $searchStatus
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name Items -Value $search.Items
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name "Size" -Value $search.Size
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name "Size(MB)" -Value $sizeMB
      $allSearchStats += $searchStats
   }
   # Calculate the totals
   $allItems = ($allSearchStats | Measure-Object Items -Sum).Sum
   # Convert the total size to MB and round to the nearst 100th
   $allSize = ($allSearchStats | Measure-Object 'Size' -Sum).Sum
   $allSizeMB = [System.Math]::Round($allSize  / 1MB, 2)
   # Get the total successful searches and total of all searches
   $allSuccessCount = ($allSearchStats |?{$_.Status -eq "Completed"}).Count
   $allCount = $allSearchStats.Count
   $allStatus = [string]$allSuccessCount + " of " + [string]$allCount
   # Totals Row
   $totalSearchStats = New-Object PSObject
   Add-Member -InputObject $totalSearchStats -MemberType NoteProperty -Name Name -Value "Total"
   Add-Member -InputObject $totalSearchStats -MemberType NoteProperty -Name Status -Value $allStatus
   Add-Member -InputObject $totalSearchStats -MemberType NoteProperty -Name Items -Value $allItems
   Add-Member -InputObject $totalSearchStats -MemberType NoteProperty -Name "Size(MB)" -Value $allSizeMB
   $allSearchStats += $totalSearchStats
   # Just get the columns we're interested in showing
   $allSearchStatsPrime = $allSearchStats | Select-Object Name, Status, Items, "Size(MB)", ContentMatchQuery
   # Print the results to the screen
   $allSearchStatsPrime |ft -AutoSize -Wrap
   # Save the results to a CSV file
   if ($outputFile)
   {
      $allSearchStatsPrime | Export-Csv -Path $outputFile -NoTypeInformation
   }
   ```

2. In Windows PowerShell, passare alla cartella in cui è stato salvato lo script nel passaggio precedente, quindi eseguire lo script. Per esempio:

   ```Powershell
   .\SearchReport.ps1
   ```

3. Al prompt **ID gruppo di ricerca** Digitare il nome di un gruppo di ricerca e quindi premere **invio**. ad esempio  `ContosoCase` . Tenere presente che questo nome è distinzione tra maiuscole e minuscole, quindi sarà necessario digitarlo nello stesso modo in cui è stato eseguito lo script nel passaggio 3.

4. Nel **percorso del file per salvare il report in un file CSV (lasciare vuoto solo per visualizzare il report)** , digitare il nome di un file del percorso completo (inclusa l'estensione CSV) se si desidera salvare il report in un file CSV. nome del file CSV, inclusa l'estensione del file CSV. Ad esempio, è possibile digitare per  `ContosoCaseReport.csv` salvarlo nella directory corrente oppure è possibile digitare  `C:\Users\admin\OneDrive for Business\ContosoCase\ContosoCaseReport.csv` per salvarlo in un'altra cartella. È inoltre possibile lasciare il messaggio vuoto per visualizzare il report, ma non salvarlo in un file.

5. Premere **INVIO**.

   Nello script viene visualizzato lo stato di avanzamento della creazione e dell'esecuzione delle ricerche. Al termine dello script, viene visualizzato il report.

   ![Eseguire il report di ricerca per visualizzare le stime per il gruppo di ricerca](../media/3b5f2595-71d5-4a14-9214-fad156c981f8.png)

> [!NOTE]
> Se la stessa cassetta postale o sito è specificato come percorso di contenuto in più di una ricerca in un gruppo di ricerca, la stima complessiva dei risultati nel rapporto (sia per il numero di elementi che per la dimensione totale) potrebbe includere i risultati per gli stessi elementi. Ciò è dovuto al fatto che lo stesso messaggio di posta elettronica o documento verrà conteggiato più di una volta se corrisponde alla query per ricerche diverse nel gruppo di ricerca.

## <a name="step-5-run-the-script-to-delete-the-searches"></a>Passaggio 5: eseguire lo script per eliminare le ricerche

Poiché potrebbe essere la creazione di un sacco di ricerche, questo ultimo script rende semplice eliminare rapidamente le ricerche create nel passaggio 3. Come gli altri script, questo richiede anche l'ID del gruppo di ricerca. Tutte le ricerche con l'ID del gruppo di ricerca nel nome della ricerca verranno eliminate quando si esegue questo script.

1. Salvare il testo seguente in un file di script di Windows PowerShell utilizzando un suffisso FileName di. ps1. ad esempio, `DeleteSearches.ps1` . Salvare il file nella stessa cartella in cui sono stati salvati gli altri file.

   ```Powershell
   # Delete all searches in a search group
   $searchGroup = Read-Host 'Search Group ID'
   Get-ComplianceSearch |
      ForEach-Object{
      # If the name matches the search group name pattern (case sensitive), delete the search
      if ($_.Name -cmatch $searchGroup + "_\d+")
      {
          Write-Host "Deleting search: " $_.Name
          Remove-ComplianceSearch $_.Name -Confirm:$false
      }
   }
   ```

2. In Windows PowerShell, passare alla cartella in cui è stato salvato lo script nel passaggio precedente, quindi eseguire lo script. Per esempio:

   ```Powershell
   .\DeleteSearches.ps1
   ```

3. Al prompt **ID gruppo di ricerca** Digitare il nome di un gruppo di ricerca per le ricerche che si desidera eliminare e quindi premere **invio**. ad esempio,  `ContosoCase` . Tenere presente che questo nome è distinzione tra maiuscole e minuscole, quindi sarà necessario digitarlo nello stesso modo in cui è stato eseguito lo script nel passaggio 3.

   Nello script viene visualizzato il nome di ogni ricerca che viene eliminata.

   ![Eseguire lo script per eliminare le ricerche nel gruppo di ricerca](../media/9d97b9d6-a539-4d9b-a4e4-e99989144ec7.png)
