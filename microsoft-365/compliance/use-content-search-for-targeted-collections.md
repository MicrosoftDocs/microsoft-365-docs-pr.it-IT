---
title: Usare Ricerca contenuto per le raccolte di destinazione
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
- SPO_Content
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: e3cbc79c-5e97-43d3-8371-9fbc398cd92e
ms.custom: seo-marvel-apr2020
description: Utilizzare la ricerca contenuto nel centro conformità di Microsoft 365 per eseguire raccolte di destinazione, in modo da garantire che gli elementi siano situati in una cassetta postale o in una cartella specifica del sito.
ms.openlocfilehash: 0908b8262942e7a1c4d80bc511d4b8cbcc6dc646
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376593"
---
# <a name="use-content-search-for-targeted-collections"></a>Usare Ricerca contenuto per le raccolte di destinazione

La funzionalità di ricerca contenuto nel centro conformità di Microsoft 365 non fornisce un modo diretto nell'interfaccia utente per la ricerca di cartelle specifiche nelle cassette postali di Exchange o nei siti di SharePoint e OneDrive for business. Tuttavia, è possibile eseguire ricerche in cartelle specifiche (denominate *insieme mirato*) specificando la proprietà ID cartella per la proprietà posta elettronica o percorso (DocumentLink) per i siti nella sintassi della query di ricerca effettiva. L'utilizzo di ricerca contenuto per l'esecuzione di una raccolta mirata è utile quando si è certi che gli elementi sensibili a un caso o a elementi privilegiati si trovino in una specifica cassetta postale o cartella del sito. È possibile utilizzare lo script in questo articolo per ottenere l'ID della cartella per le cartelle delle cassette postali o il percorso (DocumentLink) per le cartelle in un sito di SharePoint e OneDrive for business. Successivamente, è possibile utilizzare l'ID o il percorso della cartella in una query di ricerca per restituire gli elementi che si trovano nella cartella.

> [!NOTE]
> Per restituire il contenuto presente in una cartella di un sito di SharePoint o OneDrive for business, lo script in questo argomento utilizza la proprietà gestita DocumentLink anziché la proprietà Path. La proprietà DocumentLink è più robusta della proprietà Path perché restituirà tutto il contenuto di una cartella, mentre la proprietà Path non restituirà alcuni file multimediali.

## <a name="before-you-run-a-targeted-collection"></a>Prima di eseguire una raccolta di destinazione

- Per eseguire lo script nel passaggio 1, è necessario essere membri del gruppo di ruoli eDiscovery Manager nel centro sicurezza & Compliance. Per altre informazioni, vedere [Assegnare autorizzazioni di eDiscovery](assign-ediscovery-permissions.md).

    Inoltre, è necessario essere assegnati al ruolo destinatari di posta elettronica nell'organizzazione di Exchange Online. Questo è necessario per eseguire il cmdlet **Get-MailboxFolderStatistics** , incluso nello script. Per impostazione predefinita, il ruolo destinatari di posta viene assegnato ai gruppi di ruoli Gestione organizzazione e gestione destinatari in Exchange Online. Per ulteriori informazioni sull'assegnazione delle autorizzazioni in Exchange Online, vedere [Manage Role Group Members](https://go.microsoft.com/fwlink/p/?linkid=692102). È inoltre possibile creare un gruppo di ruoli personalizzato, assegnare il ruolo destinatari di posta elettronica e quindi aggiungere i membri che devono eseguire lo script nel passaggio 1. Per ulteriori informazioni, vedere [Gestire gruppi di ruoli](https://go.microsoft.com/fwlink/p/?linkid=730688).

- Lo script in questo articolo supporta l'autenticazione moderna. È possibile utilizzare lo script così com'è se si è un'organizzazione Microsoft 365 o Microsoft 365 GCC. Se si è un'organizzazione di Office 365 Germany, un'organizzazione di Microsoft 365 GCC High o un'organizzazione di Microsoft 365 DoD, sarà necessario modificare lo script per eseguirlo correttamente. In particolare, è necessario modificare la riga `Connect-ExchangeOnline` e utilizzare il parametro *ExchangeEnvironmentName* (e il valore appropriato per il tipo di organizzazione) per connettersi a PowerShell di Exchange Online.  Inoltre, è necessario modificare la riga `Connect-IPPSSession` e utilizzare i parametri *ConnectionURI* e *AzureADAuthorizationEndpointUri* (e i valori corretti per il tipo di organizzazione) per connettersi a PowerShell per il Centro sicurezza & Compliance. Per ulteriori informazioni, vedere gli esempi in [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?#connect-to-exchange-online-powershell-without-using-mfa) e [connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa).

- Ogni volta che si esegue lo script, viene creata una nuova sessione di PowerShell remota. Questo significa che è possibile utilizzare tutte le sessioni remote di PowerShell disponibili. Per evitare che ciò accada, eseguire il comando riportato di seguito per disconnettere le sessioni di PowerShell remote attive.

  ```powershell
  Get-PSSession | Remove-PSSession
  ```

    Per ulteriori informazioni, vedere [Connessione a Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).

- Lo script include la gestione degli errori minima. Lo scopo principale dello script è la visualizzazione rapida di un elenco di ID cartella delle cassette postali o percorsi del sito che è possibile utilizzare nella sintassi delle query di ricerca di una ricerca contenuto per l'esecuzione di una raccolta di destinazione.

- Lo script di esempio fornito in questo argomento non è supportato in alcun servizio o programma di supporto Microsoft standard. Lo script di esempio viene fornito come senza garanzie di alcun tipo. Microsoft esclude inoltre qualsiasi garanzia implicita, tra cui, senza limitazioni, tutte le garanzie implicite di commerciabilità o idoneità per uno scopo specifico. L'intero rischio derivante dall'utilizzo o dalle prestazioni dello script di esempio e della documentazione resta all'interno dell'utente. In nessun caso Microsoft, i suoi autori o chiunque altro coinvolto nella creazione, produzione o consegna degli script è da ritenersi responsabile per qualsiasi danno eventuale (inclusi, senza limitazione alcuna, danni riguardanti profitti aziendali, interruzione di attività, perdita di informazioni aziendali o altra perdita pecuniaria) derivanti dall'utilizzo o dall'incapacità di utilizzo degli script di esempio e della documentazione, anche nel caso in cui Microsoft sia stata avvisata della possibilità di tali danni.
  
## <a name="step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site"></a>Passaggio 1: eseguire lo script per ottenere un elenco di cartelle per una cassetta postale o un sito

Lo script eseguito in questo primo passaggio restituirà un elenco di cartelle di cassette postali o di SharePoint e OneDrive for business e l'ID o il percorso corrispondente per ogni cartella. Quando si esegue questo script, vengono richieste le informazioni seguenti.
  
- **Indirizzo di posta elettronica o URL del sito**: digitare un indirizzo di posta elettronica del custode per restituire un elenco di cartelle di cassette postali di Exchange e ID cartella. In alternativa, digitare l'URL di un sito di SharePoint o di un sito di OneDrive for business per restituire un elenco di percorsi per il sito specificato. Ecco alcuni esempi:

  - **Exchange**: stacig@contoso. onmicrosoft <spam> <spam> . com

  - **SharePoint**: https <span>://</span>contoso.SharePoint.com/sites/marketing 

  - **OneDrive for business**: https <span>://</span>contoso-My.SharePoint.com/Personal/stacig_contoso_onmicrosoft_com 

- **Credenziali utente**: lo script utilizzerà le credenziali per connettersi a PowerShell di Exchange Online o al centro di sicurezza & conformità con l'autenticazione moderna. Come spiegato in precedenza, è necessario assegnare le autorizzazioni appropriate per eseguire correttamente lo script.

Per visualizzare un elenco delle cartelle delle cassette postali o dei nomi del sito documentlink (percorso):
  
1. Salvare il testo seguente in un file di script di Windows PowerShell utilizzando un suffisso FileName di. ps1. ad esempio, `GetFolderSearchParameters.ps1` .

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
   if ($addressOrSite.IndexOf("@") -ige 0)
   {
      # List the folder Ids for the target mailbox
      $emailAddress = $addressOrSite
      # Connect to Exchange Online PowerShell
      if (!$ExoSession)
      {
          Import-Module ExchangeOnlineManagement
          Connect-ExchangeOnline
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
      # Connect to Security & Compliance Center PowerShell
      if (!$SccSession)
      {
          Import-Module ExchangeOnlineManagement
          Connect-IPPSSession
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
    > Invece di visualizzare un elenco di cartelle sullo schermo del computer, è possibile reindirizzare l'output dello script in un file di testo. Questo file verrà salvato nella cartella in cui si trova lo script. Ad esempio, per reindirizzare l'output dello script in un file di testo, eseguire il comando riportato di seguito nel passaggio 3:  `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` è possibile copiare un ID cartella o documentlink dal file da utilizzare in una query di ricerca.
  
### <a name="script-output-for-mailbox-folders"></a>Output dello script per le cartelle delle cassette postali

Se si ricevono gli ID della cartella delle cassette postali, lo script si connette a PowerShell di Exchange Online, esegue il cmdlet **Get-MailboxFolderStatisics** e quindi Visualizza l'elenco delle cartelle dalla cassetta postale specificata. Per ogni cartella della cassetta postale, nello script viene visualizzato il nome della cartella nella colonna **percorsocartella** e l'ID della cartella nella colonna **FolderQuery** . Inoltre, lo script aggiunge il prefisso di **FolderId** (che è il nome della proprietà della cassetta postale) all'ID della cartella. Poiché la proprietà **FolderId** è una proprietà ricercabile, è possibile utilizzare  `folderid:<folderid>` in una query di ricerca nel passaggio 2 per eseguire una ricerca in tale cartella. Lo script Visualizza un massimo di 100 cartelle di cassette postali.

> [!IMPORTANT]
> Lo script in questo articolo include la logica di codifica che converte i valori ID della cartella di 64 caratteri restituiti da **Get-MailboxFolderStatistics** allo stesso formato 48-character indicizzato per la ricerca. Se si esegue il cmdlet **Get-MailboxFolderStatistics** in PowerShell per ottenere un ID cartella (invece di eseguire lo script in questo articolo), una query di ricerca che utilizza tale valore ID cartella avrà esito negativo. È necessario eseguire lo script per ottenere gli ID di cartella formattati correttamente che possono essere utilizzati in una ricerca di contenuto.
  
Di seguito è riportato un esempio dell'output restituito dallo script per le cartelle delle cassette postali.
  
![Esempio dell'elenco di cartelle di cassette postali e ID cartella restituiti dallo script](../media/cd739207-eb84-4ebf-a03d-703f3d3a797d.png)
  
Nell'esempio del passaggio 2 viene illustrata la query utilizzata per eseguire la ricerca nella sottocartella Ripuliture nella cartella elementi ripristinabili dell'utente.
  
### <a name="script-output-for-site-folders"></a>Output dello script per le cartelle del sito

Se si sta ottenendo il percorso della proprietà **documentlink** da siti di SharePoint o OneDrive for business, lo script si connette a PowerShell per la sicurezza & Compliance, crea una nuova ricerca di contenuto che cerca il sito per le cartelle e quindi Visualizza un elenco delle cartelle che si trovano nel sito specificato. Lo script Visualizza il nome di ogni cartella e aggiunge il prefisso di **documentlink** all'URL della cartella. Poiché la proprietà **documentlink** è una proprietà per la ricerca, è possibile utilizzare la `documentlink:<path>` coppia Property: value in una query di ricerca nel passaggio 2 per eseguire una ricerca nella cartella. Lo script Visualizza un massimo di 200 cartelle del sito. Se sono presenti più di 200 cartelle del sito, vengono visualizzate quelle più recenti.
  
Di seguito è riportato un esempio dell'output restituito dallo script per le cartelle del sito.
  
![Esempio dell'elenco di nomi di documentlink per le cartelle del sito restituite dallo script](../media/519e8347-7365-4067-af78-96c465dc3d15.png)
  
## <a name="step-2-use-a-folder-id-or-documentlink-to-perform-a-targeted-collection"></a>Passaggio 2: utilizzare un ID cartella o documentlink per eseguire una raccolta di destinazione

Dopo aver eseguito lo script per raccogliere un elenco di ID cartella o collegamenti di documento per un utente specifico, il passaggio successivo per passare al centro conformità di Microsoft 365 e creare una nuova ricerca contenuto per eseguire la ricerca in una cartella specifica. Si utilizzerà la  `folderid:<folderid>`  `documentlink:<path>` coppia o proprietà: valore nella query di ricerca configurata nella casella parola chiave ricerca contenuto (o come valore per il parametro  *ContentMatchQuery*  se si utilizza il cmdlet **New-ComplianceSearch** ). È possibile combinare la  `folderid`  `documentlink` Proprietà or con altri parametri di ricerca o condizioni di ricerca. Se nella query è inclusa solo la  `folderid`  `documentlink` Proprietà or, la ricerca restituirà tutti gli elementi presenti nella cartella specificata.
  
1. Passare a [https://compliance.microsoft.com](https://compliance.microsoft.com) e accedere utilizzando l'account e le credenziali utilizzati per eseguire lo script nel passaggio 1.

2. Nel riquadro sinistro del centro conformità fare clic su **Mostra tutte le**  >  **ricerche di contenuto** e quindi fare clic su **nuova ricerca**.

3. Nella casella **parole chiave** incollare il `folderid:<folderid>` valore o  `documentlink:<path>` restituito dallo script nel passaggio 1.

    Ad esempio, la query nello screenshot seguente cercherà tutti gli elementi nella sottocartella Purges nella cartella elementi ripristinabili dell'utente (il valore della `folderid` proprietà per la sottocartella Purges viene visualizzato nello screenshot del passaggio 1):

    ![Incollare il FolderId o documentlink nella casella parola chiave della query di ricerca](../media/FolderIDSearchQuery.png)

4. In **percorsi** selezionare **percorsi specifici** e quindi fare clic su **modifica**.

5. Eseguire una delle operazioni seguenti, a seconda che si cerchi una cartella della cassetta postale o una cartella del sito:

    - Accanto a **posta elettronica di Exchange**, fare clic su **Scegli utenti, gruppi o team** e quindi aggiungere la stessa cassetta postale specificata al momento dell'esecuzione dello script nel passaggio 1.

      Oppure

    - Accanto a **siti di SharePoint** fare clic su **Scegli siti** e quindi aggiungere lo stesso URL del sito specificato durante l'esecuzione dello script nel passaggio 1.

6. Dopo aver salvato il percorso del contenuto per la ricerca, fare clic su **salva & Esegui**, digitare un nome per la ricerca di contenuto e quindi fare clic su **Salva** per avviare la ricerca di raccolta di destinazione. 
  
### <a name="examples-of-search-queries-for-targeted-collections"></a>Esempi di query di ricerca per gli insiemi di destinazione

Di seguito sono riportati alcuni esempi di utilizzo delle  `folderid`  `documentlink` proprietà e in una query di ricerca per l'esecuzione di una raccolta di destinazione. I segnaposto vengono utilizzati per il  `folderid:<folderid>`  `documentlink:<path>` salvataggio e lo spazio. 
  
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
  
- Lo script non rimuove alcuna cartella dai risultati. Pertanto, alcune cartelle elencate nei risultati potrebbero non essere ricercabili (o restituire zero elementi) perché contengono contenuto generato dal sistema o perché contengono solo sottocartelle e non elementi della cassetta postale.

- Questo script restituisce solo informazioni sulla cartella per la cassetta postale principale dell'utente. Non restituisce informazioni sulle cartelle nella cassetta postale di archiviazione dell'utente. Per restituire informazioni sulle cartelle nella cassetta postale di archiviazione dell'utente, è possibile modificare lo script. A tale scopo, modificare la riga `$folderStatistics = Get-MailboxFolderStatistics $emailAddress` e `$folderStatistics = Get-MailboxFolderStatistics $emailAddress -Archive` quindi salvare ed eseguire lo script modificato. Questa modifica restituirà gli ID della cartella per le cartelle e le sottocartelle nella cassetta postale di archiviazione dell'utente. Per eseguire una ricerca nell'intera cassetta postale di archiviazione, è possibile connettere tutte le coppie proprietà ID cartella: valore con un `OR` operatore in una query di ricerca.

- Quando si eseguono ricerche nelle cartelle delle cassette postali, verrà eseguita la ricerca solo nella cartella specificata (identificata dalla relativa `folderid` proprietà); le sottocartelle non verranno cercate. Per eseguire la ricerca nelle sottocartelle, è necessario utilizzare l'ID della cartella per la sottocartella che si desidera ricercare.

- Quando si esegue la ricerca nelle cartelle del sito, la cartella (identificata dalla relativa `documentlink` proprietà) e tutte le sottocartelle verranno cercate. 

- Quando si esportano i risultati di una ricerca in cui è stata specificata solo la `folderid` proprietà nella query di ricerca, è possibile scegliere la prima opzione di esportazione, "tutti gli elementi, esclusi quelli con formato non riconosciuto, sono crittografati o non sono stati indicizzati per altri motivi". Tutti gli elementi della cartella verranno sempre esportati indipendentemente dallo stato di indicizzazione, poiché l'ID della cartella è sempre indicizzato.
