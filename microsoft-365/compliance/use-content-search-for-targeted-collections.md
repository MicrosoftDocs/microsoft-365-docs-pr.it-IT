---
title: Usare Ricerca contenuto per le raccolte di destinazione
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
- M365-security-compliance
- SPO_Content
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: e3cbc79c-5e97-43d3-8371-9fbc398cd92e
description: Utilizzare la ricerca contenuto nel centro sicurezza & conformità per eseguire le raccolte mirate. Un insieme mirato indica che gli elementi che rispondono a un caso o a elementi privilegiati si trovano in una cassetta postale o in una cartella del sito specifica. Utilizzare lo script in questo articolo per ottenere l'ID o il percorso della cartella specifica della cassetta postale o delle cartelle del sito che si desidera ricercare.
ms.openlocfilehash: 4808dad8faed99ac15c4f9828ad1759e2f1179fc
ms.sourcegitcommit: 60c1932dcca249355ef7134df0ceb0e57757dc81
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/29/2020
ms.locfileid: "43942979"
---
# <a name="use-content-search-for-targeted-collections"></a>Usare Ricerca contenuto per le raccolte di destinazione

La funzionalità di ricerca contenuto nel centro &amp; sicurezza e conformità non fornisce un modo diretto nell'interfaccia utente per eseguire ricerche in cartelle specifiche nelle cassette postali di Exchange o nei siti di SharePoint e OneDrive for business. Tuttavia, è possibile eseguire ricerche in cartelle specifiche (denominate *insieme mirato*) specificando la proprietà ID cartella per la proprietà posta elettronica o percorso (DocumentLink) per i siti nella sintassi della query di ricerca effettiva. L'utilizzo di ricerca contenuto per l'esecuzione di una raccolta mirata è utile quando si è certi che gli elementi sensibili a un caso o a elementi privilegiati si trovino in una specifica cassetta postale o cartella del sito. È possibile utilizzare lo script in questo articolo per ottenere l'ID della cartella per le cartelle delle cassette postali o il percorso (DocumentLink) per le cartelle in un sito di SharePoint e OneDrive for business. Successivamente, è possibile utilizzare l'ID o il percorso della cartella in una query di ricerca per restituire gli elementi che si trovano nella cartella.

> [!NOTE]
> Per restituire il contenuto presente in una cartella di un sito di SharePoint o OneDrive for business, lo script in questo argomento utilizza la proprietà gestita DocumentLink anziché la proprietà Path. La proprietà DocumentLink è più robusta della proprietà Path perché restituirà tutto il contenuto di una cartella, mentre la proprietà Path non restituirà alcuni file multimediali.

## <a name="before-you-begin"></a>Informazioni preliminari

- Per eseguire lo script nel passaggio 1, è necessario essere membri del gruppo di &amp; ruoli eDiscovery Manager nel centro sicurezza e conformità. Per altre informazioni, vedere [Assegnare autorizzazioni di eDiscovery](assign-ediscovery-permissions.md).
    
    Inoltre, è necessario essere assegnati al ruolo destinatari di posta elettronica nell'organizzazione di Exchange Online. Questo è necessario per eseguire il cmdlet **Get-MailboxFolderStatistics** , incluso nello script nel passaggio 1. Per impostazione predefinita, il ruolo destinatari di posta viene assegnato ai gruppi di ruoli Gestione organizzazione e gestione destinatari in Exchange Online. Per ulteriori informazioni sull'assegnazione delle autorizzazioni in Exchange Online, vedere [Manage Role Group Members](https://go.microsoft.com/fwlink/p/?linkid=692102). È inoltre possibile creare un gruppo di ruoli personalizzato, assegnare il ruolo destinatari di posta elettronica e quindi aggiungere i membri che devono eseguire lo script nel passaggio 1. Per ulteriori informazioni, vedere [Gestire gruppi di ruoli](https://go.microsoft.com/fwlink/p/?linkid=730688).
    
- Ogni volta che si esegue lo script nel passaggio 1, viene creata una nuova sessione di PowerShell remota. In questo modo, è possibile utilizzare tutte le sessioni remote di PowerShell disponibili. Per evitare che ciò accada, è possibile eseguire il comando riportato di seguito per disconnettere le sessioni di PowerShell remote attive.
    
  ```powershell
  Get-PSSession | Remove-PSSession
  ```

    Per ulteriori informazioni, vedere [Connessione a Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).
    
- Lo script include la gestione degli errori minima. Lo scopo principale dello script è la visualizzazione rapida di un elenco di ID cartella delle cassette postali o percorsi del sito che è possibile utilizzare nella sintassi delle query di ricerca di una ricerca contenuto per l'esecuzione di una raccolta di destinazione.
    
- Lo script di esempio fornito in questo argomento non è supportato in alcun servizio o programma di supporto Microsoft standard. Lo script di esempio viene fornito come senza garanzie di alcun tipo. Inoltre Microsoft declina ogni responsabilità su garanzie implicite, senza alcuna limitazione, incluse le garanzie implicite di commerciabilità e/o adeguatezza per uno scopo specifico. L'intero rischio derivante dall'utilizzo o dalle prestazioni dello script di esempio e della documentazione resta all'interno dell'utente. In nessun caso Microsoft, i suoi autori o chiunque altro coinvolto nella creazione, produzione o consegna degli script è da ritenersi responsabile per qualsiasi danno eventuale (inclusi, senza limitazione alcuna, danni riguardanti profitti aziendali, interruzione di attività, perdita di informazioni aziendali o altra perdita pecuniaria) derivanti dall'utilizzo o dall'incapacità di utilizzo degli script di esempio e della documentazione, anche nel caso in cui Microsoft sia stata avvisata della possibilità di tali danni.
  
## <a name="step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site"></a>Passaggio 1: eseguire lo script per ottenere un elenco di cartelle per una cassetta postale o un sito

Lo script eseguito in questo primo passaggio restituirà un elenco di cartelle di cassette postali o di SharePoint e OneDrive for business e l'ID o il percorso corrispondente per ogni cartella. Quando si esegue questo script, vengono richieste le informazioni seguenti.
  
- **Indirizzo di posta elettronica o URL del sito** Digitare un indirizzo di posta elettronica del custode per restituire un elenco di cartelle di cassette postali di Exchange e ID cartella. In alternativa, digitare l'URL di un sito di SharePoint o di un sito di OneDrive for business per restituire un elenco di percorsi per il sito specificato. Ecco alcuni esempi: 
    
  - **Exchange** -stacig@contoso.onmicrosoft.com 
    
  - **SharePoint** - https://contoso.sharepoint.com/sites/marketing 
    
  - **OneDrive for business** - https://contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com 
    
- **Credenziali utente** : lo script utilizzerà le credenziali per la connessione a Exchange Online e il centro sicurezza & conformità con Remote PowerShell. Come spiegato in precedenza, è necessario assegnare le autorizzazioni appropriate per eseguire correttamente lo script.
    
Per visualizzare un elenco delle cartelle delle cassette postali o dei nomi del sito documentlink (percorso):
  
1. Salvare il testo seguente in un file di script di Windows PowerShell utilizzando un suffisso FileName di. ps1. ad esempio, `GetFolderSearchParameters.ps1`.
    
  ```powershell
  #########################################################################################################
  # This PowerShell script will prompt you for:                                #
  #    * Admin credentials for a user who can run the Get-MailboxFolderStatistics cmdlet in Exchange    #
  #      Online and who is an eDiscovery Manager in the Security & Compliance Center.            #
  # The script will then:                                            #
  #    * If an email address is supplied: list the folders for the target mailbox.            #
  #    * If a SharePoint or OneDrive for Business site is supplied: list the documentlinks (folder paths) #
  #    * for the site.                                                                                    #
  #    * In both cases, the script supplies the correct search properties (folderid: or documentlink:)    #
  #      appended to the folder ID or documentlink to use in a Content Search.                #
  # Notes:                                                #
  #    * For SharePoint and OneDrive for Business, the paths are searched recursively; this means the     #
  #      the current folder and all sub-folders are searched.                        #
  #    * For Exchange, only the specified folder will be searched; this means sub-folders in the folder    #
  #      will not be searched.  To search sub-folders, you need to use the specify the folder ID for    #
  #      each sub-folder that you want to search.                                #
  #    * For Exchange, only folders in the user's primary mailbox will be returned by the script.        #
  #########################################################################################################
  # Collect the target email address or SharePoint Url
  $addressOrSite = Read-Host "Enter an email address or a URL for a SharePoint or OneDrive for Business site"
  # Authenticate with Exchange Online and the Security & Compliance Center (Exchange Online Protection - EOP)
  if (!$credentials)
  {
      $credentials = Get-Credential
  }
  if ($addressOrSite.IndexOf("@") -ige 0)
  {
      # List the folder Ids for the target mailbox
      $emailAddress = $addressOrSite
      # Authenticate with Exchange Online
      if (!$ExoSession)
      {
          $ExoSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid/ -Credential $credentials -Authentication Basic -AllowRedirection
          Import-PSSession $ExoSession -AllowClobber -DisableNameChecking
      }
      $folderQueries = @()
      $folderStatistics = Get-MailboxFolderStatistics $emailAddress
      foreach ($folderStatistic in $folderStatistics)
      {
          $folderId = $folderStatistic.FolderId;
          $folderPath = $folderStatistic.FolderPath;
          $encoding= [System.Text.Encoding]::GetEncoding("us-ascii")
          $nibbler= $encoding.GetBytes("0123456789ABCDEF");
          $folderIdBytes = [Convert]::FromBase64String($folderId);
          $indexIdBytes = New-Object byte[] 48;
          $indexIdIdx=0;
          $folderIdBytes | select -skip 23 -First 24 | %{$indexIdBytes[$indexIdIdx++]=$nibbler[$_ -shr 4];$indexIdBytes[$indexIdIdx++]=$nibbler[$_ -band 0xF]}
          $folderQuery = "folderid:$($encoding.GetString($indexIdBytes))";
          $folderStat = New-Object PSObject
          Add-Member -InputObject $folderStat -MemberType NoteProperty -Name FolderPath -Value $folderPath
          Add-Member -InputObject $folderStat -MemberType NoteProperty -Name FolderQuery -Value $folderQuery
          $folderQueries += $folderStat
      }
      Write-Host "-----Exchange Folders-----"
      $folderQueries |ft
  }
  elseif ($addressOrSite.IndexOf("http") -ige 0)
  {
      $searchName = "SPFoldersSearch"
      $searchActionName = "SPFoldersSearch_Preview"
      # List the folders for the SharePoint or OneDrive for Business Site
      $siteUrl = $addressOrSite
      # Authenticate with the Security & Compliance Center
      if (!$SccSession)
      {
          $SccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $credentials -Authentication Basic -AllowRedirection
          Import-PSSession $SccSession -AllowClobber -DisableNameChecking
      }
      # Clean-up, if the script was aborted, the search we created might not have been deleted.  Try to do so now.
      Remove-ComplianceSearch $searchName -Confirm:$false -ErrorAction 'SilentlyContinue'
      # Create a Content Search against the SharePoint Site or OneDrive for Business site and only search for folders; wait for the search to complete
      $complianceSearch = New-ComplianceSearch -Name $searchName -ContentMatchQuery "contenttype:folder" -SharePointLocation $siteUrl
      Start-ComplianceSearch $searchName
      do{
          Write-host "Waiting for search to complete..."
          Start-Sleep -s 5
          $complianceSearch = Get-ComplianceSearch $searchName
      }while ($complianceSearch.Status -ne 'Completed')
      if ($complianceSearch.Items -gt 0)
      {
          # Create a Compliance Search Action and wait for it to complete. The folders will be listed in the .Results parameter
          $complianceSearchAction = New-ComplianceSearchAction -SearchName $searchName -Preview
          do
          {
              Write-host "Waiting for search action to complete..."
              Start-Sleep -s 5
              $complianceSearchAction = Get-ComplianceSearchAction $searchActionName
          }while ($complianceSearchAction.Status -ne 'Completed')
          # Get the results and print out the folders
          $results = $complianceSearchAction.Results
          $matches = Select-String "Data Link:.+[,}]" -Input $results -AllMatches
          foreach ($match in $matches.Matches)
          {
              $rawUrl = $match.Value
              $rawUrl = $rawUrl -replace "Data Link: " -replace "," -replace "}"
              Write-Host "DocumentLink:""$rawUrl"""
          }
      }
      else
      {
          Write-Host "No folders were found for $siteUrl"
      }
      Remove-ComplianceSearch $searchName -Confirm:$false -ErrorAction 'SilentlyContinue'
  }
  else
  {
      Write-Error "Couldn't recognize $addressOrSite as an email address or a site URL"
  }
  ```

2. Nel computer locale, aprire Windows PowerShell e passare alla cartella in cui è stato salvato lo script.
    
3. Eseguire lo script; Per esempio:
    
      ```powershell
      .\GetFolderSearchParameters.ps1
      ```

4. Immettere le informazioni richieste dallo script.
    
    Nello script viene visualizzato un elenco di cartelle di cassette postali o di cartelle del sito per l'utente specificato. Lasciare aperta la finestra in modo che sia possibile copiare un ID cartella o un nome di documentlink e incollarlo in una query di ricerca nel passaggio 2.
    
    > [!TIP]
    > Invece di visualizzare un elenco di cartelle sullo schermo del computer, è possibile reindirizzare l'output dello script in un file di testo. Questo file verrà salvato nella cartella in cui si trova lo script. Ad esempio, per reindirizzare l'output dello script in un file di testo, eseguire il comando riportato `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` di seguito nel passaggio 3: è possibile copiare un ID cartella o documentlink dal file da utilizzare in una query di ricerca.
  
### <a name="script-output-for-mailbox-folders"></a>Output dello script per le cartelle delle cassette postali

Se si ricevono gli ID della cartella delle cassette postali, lo script si connette a Exchange Online tramite Remote PowerShell, esegue il cmdlet **Get-MailboxFolderStatisics** e quindi Visualizza l'elenco delle cartelle dalla cassetta postale specificata. Per ogni cartella della cassetta postale, nello script viene visualizzato il nome della cartella nella colonna **percorsocartella** e l'ID della cartella nella colonna **FolderQuery** . Inoltre, lo script aggiunge il prefisso di **FolderId** (che è il nome della proprietà della cassetta postale) all'ID della cartella. Poiché la proprietà **FolderId** è una proprietà ricercabile, è possibile utilizzare `folderid:<folderid>` in una query di ricerca nel passaggio 2 per eseguire una ricerca in tale cartella. Lo script Visualizza un massimo di 100 cartelle di cassette postali.

> [!IMPORTANT]
> Lo script in questo articolo include la logica di codifica che converte i valori ID della cartella di 64 caratteri restituiti da **Get-MailboxFolderStatistics** allo stesso formato 48-character indicizzato per la ricerca. Se si esegue il cmdlet **Get-MailboxFolderStatistics** in PowerShell per ottenere un ID cartella (invece di eseguire lo script in questo articolo), una query di ricerca che utilizza tale valore ID cartella avrà esito negativo. È necessario eseguire lo script per ottenere gli ID di cartella formattati correttamente che possono essere utilizzati in una ricerca di contenuto.
  
Di seguito è riportato un esempio dell'output restituito dallo script per le cartelle delle cassette postali.
  
![Esempio dell'elenco di cartelle di cassette postali e ID cartella restituiti dallo script](../media/cd739207-eb84-4ebf-a03d-703f3d3a797d.png)
  
Nell'esempio del passaggio 2 viene illustrata la query utilizzata per eseguire la ricerca nella sottocartella Ripuliture nella cartella elementi ripristinabili dell'utente.
  
### <a name="script-output-for-site-folders"></a>Output dello script per le cartelle del sito

Se si riceve il percorso della proprietà **documentlink** da siti di SharePoint o OneDrive for business, lo script si connette al centro sicurezza & conformità tramite Remote PowerShell, crea una nuova ricerca di contenuto in cui vengono eseguite ricerche nel sito per le cartelle e quindi viene visualizzato un elenco delle cartelle che si trovano nel sito specificato. Lo script Visualizza il nome di ogni cartella e aggiunge il prefisso di **documentlink** all'URL della cartella. Poiché la proprietà **documentlink** è una proprietà per la ricerca, è possibile `documentlink:<path>` utilizzare la coppia Property: value in una query di ricerca nel passaggio 2 per eseguire una ricerca nella cartella. Lo script Visualizza un massimo di 200 cartelle del sito. Se sono presenti più di 200 cartelle del sito, vengono visualizzate quelle più recenti.
  
Di seguito è riportato un esempio dell'output restituito dallo script per le cartelle del sito.
  
![Esempio dell'elenco di nomi di documentlink per le cartelle del sito restituite dallo script](../media/519e8347-7365-4067-af78-96c465dc3d15.png)
  
## <a name="step-2-use-a-folder-id-or-documentlink-to-perform-a-targeted-collection"></a>Passaggio 2: utilizzare un ID cartella o documentlink per eseguire una raccolta di destinazione

Dopo aver eseguito lo script per raccogliere un elenco di ID cartella o documentlinks per un utente specifico, il passaggio successivo per accedere al centro sicurezza & compliance e creare una nuova ricerca contenuto per eseguire la ricerca in una cartella specifica. Si utilizzerà la `folderid:<folderid>` coppia `documentlink:<path>` o proprietà: valore nella query di ricerca configurata nella casella parola chiave ricerca contenuto (o come valore per il parametro *ContentMatchQuery* se si utilizza il cmdlet **New-ComplianceSearch** ). È possibile combinare la `folderid` proprietà `documentlink` or con altri parametri di ricerca o condizioni di ricerca. Se nella query è inclusa `folderid` solo `documentlink` la proprietà or, la ricerca restituirà tutti gli elementi presenti nella cartella specificata. 
  
1. Passare a [https://protection.office.com](https://protection.office.com).
    
2. Accedere utilizzando l'account e le credenziali utilizzati per eseguire lo script nel passaggio 1.
    
3. Nel riquadro sinistro del Centro sicurezza & **conformità fare clic** \> su ricerca **contenuto**ricerca, quindi fare clic su **nuova** ![icona](../media/O365-MDM-CreatePolicy-AddIcon.gif)Aggiungi.
    
4. Nella pagina **Nuova ricerca**, digitare un nome relativo alla ricerca contenuto. Questo nome deve essere univoco nell'organizzazione. 
    
5. In **dove si desidera**eseguire la ricerca, eseguire una delle operazioni seguenti, a seconda che si cerchi una cartella della cassetta postale o una cartella del sito:
    
    - Fare clic su **Scegli cassette postali specifiche da cercare** e quindi aggiungere la stessa cassetta postale specificata al momento dell'esecuzione dello script nel passaggio 1. 
    
      Oppure
    
    - Fare clic su **Scegli siti specifici per cercare** e quindi aggiungere lo stesso URL del sito specificato durante l'esecuzione dello script nel passaggio 1. 
    
6. Fare clic su **Avanti**.
    
7. Nella casella parola chiave della pagina **che cosa si desidera cercare per** la pagina, incollare il `folderid:<folderid>` valore o `documentlink:<path>` restituito dallo script nel passaggio 1. 
    
    Ad esempio, la query nello screenshot seguente cercherà tutti gli elementi nella sottocartella Purges nella cartella elementi ripristinabili dell'utente (il valore della `folderid` proprietà per la sottocartella Purges viene visualizzato nello screenshot del passaggio 1):
    
    ![Incollare il FolderId o documentlink nella casella parola chiave della query di ricerca](../media/84057516-b663-48a4-a78f-8032a8f8da80.png)
  
8. Fare clic su **Cerca** per avviare la ricerca di raccolta di destinazione. 
  
### <a name="examples-of-search-queries-for-targeted-collections"></a>Esempi di query di ricerca per gli insiemi di destinazione

Di seguito sono riportati alcuni esempi di `folderid` utilizzo `documentlink` delle proprietà e in una query di ricerca per l'esecuzione di una raccolta di destinazione. Si noti che i segnaposto vengono `folderid:<folderid>` utilizzati `documentlink:<path>` per e per risparmiare spazio. 
  
- In questo esempio vengono cercate tre cartelle di cassette postali diverse. È possibile utilizzare una sintassi di query simile per cercare le cartelle nascoste nella cartella elementi ripristinabili di un utente.
    
  ```powershell
  folderid:<folderid> OR folderid:<folderid> OR folderid:<folderid>
  ```

- In questo esempio viene eseguita la ricerca di elementi che contengono una frase esatta in una cartella della cassetta postale.
    
  ```powershell
  folderid:<folderid> AND "Contoso financial results"
  ```

- In questo esempio viene eseguita una ricerca in una cartella del sito e in tutte le sottocartelle per i documenti che contengono le lettere "NDA" nel titolo.
    
  ```powershell
  documentlink:<path> AND filename:nda
  ```

- In questo esempio viene eseguita una ricerca in una cartella del sito e in qualsiasi sottocartella per i documenti che sono stati modificati all'interno di un intervallo di date.
    
  ```powershell
  documentlink:<path> AND (lastmodifiedtime>=01/01/2017 AND lastmodifiedtime<=01/21/2017)
  ```

## <a name="more-information"></a>Ulteriori informazioni

Quando si utilizza lo script in questo articolo, è necessario tenere presente quanto segue per eseguire le raccolte mirate.
  
- Lo script non rimuove alcuna cartella dai risultati. Pertanto, alcune cartelle elencate nei risultati potrebbero non essere ricercabili (o restituire zero elementi) perché contengono contenuto generato dal sistema.
    
- Questo script restituisce solo informazioni sulla cartella per la cassetta postale principale dell'utente. Non restituisce informazioni sulle cartelle nella cassetta postale di archiviazione dell'utente.
    
- Quando si eseguono ricerche nelle cartelle delle cassette postali, verrà eseguita `folderid` la ricerca solo nella cartella specificata (identificata dalla relativa proprietà). le sottocartelle non verranno cercate. Per eseguire la ricerca in cartelle secondarie, è necessario utilizzare l'ID cartella per la sottocartella che si desidera ricercare. 
    
- Quando si esegue la ricerca nelle cartelle del sito, la `documentlink` cartella (identificata dalla relativa proprietà) e tutte le sottocartelle verranno ricercate. 
    
- Quando si esportano i risultati di una ricerca in cui è `folderid` stata specificata solo la proprietà nella query di ricerca, è possibile scegliere la prima opzione di esportazione, "tutti gli elementi, esclusi quelli con formato non riconosciuto, sono crittografati o non sono stati indicizzati per altri motivi". Tutti gli elementi della cartella verranno sempre esportati indipendentemente dallo stato di indicizzazione, poiché l'ID della cartella è sempre indicizzato.
