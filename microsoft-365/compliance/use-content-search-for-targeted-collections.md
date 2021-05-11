---
title: Usare Ricerca contenuto per raccolte di destinazione
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
description: Utilizzare Ricerca contenuto nel Centro Microsoft 365 conformità per eseguire una raccolta di destinazione, che cerca gli elementi in una cassetta postale o in una cartella del sito specifica.
ms.openlocfilehash: cf0364d39a78e1bbbc062d85ce750d190fbbda5a
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311909"
---
# <a name="use-content-search-for-targeted-collections"></a>Usare Ricerca contenuto per raccolte di destinazione

Lo strumento ricerca contenuto nel Centro conformità Microsoft 365 non fornisce un modo diretto nell'interfaccia utente per cercare cartelle specifiche nelle cassette postali di Exchange o SharePoint e OneDrive for Business siti. È tuttavia possibile eseguire ricerche in cartelle specifiche (denominate raccolte di *destinazione)* specificando la proprietà ID cartella per la posta elettronica o il percorso (DocumentLink) per i siti nella sintassi della query di ricerca effettiva. L'utilizzo di Ricerca contenuto per eseguire una raccolta di destinazione è utile quando si è certi che gli elementi che rieseguono un caso o elementi con privilegi si trovino in una cassetta postale o in una cartella del sito specifica. È possibile utilizzare lo script in questo articolo per ottenere l'ID cartella per le cartelle delle cassette postali o il percorso (DocumentLink) per le cartelle in un SharePoint e OneDrive for Business sito. È quindi possibile utilizzare l'ID o il percorso della cartella in una query di ricerca per restituire gli elementi che si trovano nella cartella.

> [!NOTE]
> Per restituire il contenuto che si trova in una cartella in un sito SharePoint o OneDrive for Business, lo script in questo argomento utilizza la proprietà gestita DocumentLink anziché la proprietà Path. La proprietà DocumentLink è più affidabile della proprietà Path perché restituirà tutto il contenuto di una cartella, mentre la proprietà Path non restituirà alcuni file multimediali.

## <a name="before-you-run-a-targeted-collection"></a>Prima di eseguire una raccolta di destinazione

- Per eseguire lo script nel passaggio 1, è necessario essere membri del gruppo di ruoli Responsabile eDiscovery nel Centro sicurezza & conformità. Per altre informazioni, vedere [Assegnare autorizzazioni di eDiscovery](assign-ediscovery-permissions.md).

- È inoltre necessario essere assegnati al ruolo Destinatari di posta nell'Exchange Online organizzazione. Questa operazione è necessaria per eseguire il cmdlet **Get-MailboxFolderStatistics,** incluso nello script. Per impostazione predefinita, il ruolo Destinatari di posta viene assegnato ai gruppi di ruoli Gestione organizzazione e Gestione destinatari in Exchange Online. Per ulteriori informazioni sull'assegnazione delle autorizzazioni in Exchange Online, vedere [Manage role group members](/exchange/manage-role-group-members-exchange-2013-help). È inoltre possibile creare un gruppo di ruoli personalizzato, assegnare il ruolo Destinatari di posta e quindi aggiungere i membri che devono eseguire lo script nel passaggio 1. Per ulteriori informazioni, vedere [Gestire gruppi di ruoli](/Exchange/permissions-exo/role-groups).

- Lo script in questo articolo supporta l'autenticazione moderna. È possibile utilizzare lo script così come è se si è un'Microsoft 365 o un'Microsoft 365 GCC organizzazione. Se si è un'organizzazione di Office 365 Germany, un'organizzazione di Microsoft 365 GCC High o un'organizzazione DoD di Microsoft 365, sarà necessario modificare lo script per eseguirlo correttamente. In particolare, è necessario modificare la riga e utilizzare il `Connect-ExchangeOnline` *parametro ExchangeEnvironmentName* (e il valore appropriato per il tipo di organizzazione) per connettersi a Exchange Online PowerShell.  È inoltre necessario modificare la riga e utilizzare i parametri `Connect-IPPSSession` *ConnectionUri* e *AzureADAuthorizationEndpointUri* (e i valori appropriati per il tipo di organizzazione) per connettersi a PowerShell del Centro sicurezza & conformità. Per ulteriori informazioni, vedere gli esempi in [Connessione a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-without-using-mfa) e Connessione sicurezza & [Centro conformità PowerShell.](/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa)

- Ogni volta che si esegue lo script, viene creata una nuova sessione remota di PowerShell. Ciò significa che è possibile utilizzare tutte le sessioni remote di PowerShell disponibili. Per evitare che ciò accada, eseguire il comando seguente per disconnettere le sessioni remote di PowerShell attive.

  ```powershell
  Get-PSSession | Remove-PSSession
  ```

    Per ulteriori informazioni, vedere [Connessione a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

- Lo script include una gestione minima degli errori. Lo scopo principale dello script è visualizzare rapidamente un elenco di ID cartella delle cassette postali o percorsi di sito che possono essere utilizzati nella sintassi delle query di ricerca di una ricerca contenuto per eseguire una raccolta di destinazione.

- Lo script di esempio fornito in questo argomento non è supportato in alcun servizio o programma di supporto standard Microsoft. Lo script di esempio è fornito così come è senza alcun tipo di garanzia. Microsoft esclude inoltre qualsiasi garanzia implicita, tra cui, senza limitazioni, tutte le garanzie implicite di commerciabilità o idoneità per uno scopo specifico. L'utente assume tutti i rischi associati all'uso o alle prestazioni dello script di esempio e della documentazione. In nessun caso Microsoft, i suoi autori o chiunque altro coinvolto nella creazione, produzione o consegna degli script è da ritenersi responsabile per qualsiasi danno eventuale (inclusi, senza limitazione alcuna, danni riguardanti profitti aziendali, interruzione di attività, perdita di informazioni aziendali o altra perdita pecuniaria) derivanti dall'utilizzo o dall'incapacità di utilizzo degli script di esempio e della documentazione, anche nel caso in cui Microsoft sia stata avvisata della possibilità di tali danni.

## <a name="step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site"></a>Passaggio 1: eseguire lo script per ottenere un elenco di cartelle per una cassetta postale o un sito

Lo script eseguito in questo primo passaggio restituirà un elenco di cartelle delle cassette postali o SharePoint e OneDrive for Business e l'ID o il percorso della cartella corrispondente per ogni cartella. Quando si esegue questo script, verranno richieste le informazioni seguenti.

- **Indirizzo di posta elettronica o URL** sito: digitare un indirizzo di posta elettronica del responsabile per restituire un elenco Exchange cartelle e ID cartella della cassetta postale. Oppure digitare l'URL di un SharePoint o di un OneDrive for Business per restituire un elenco di percorsi per il sito specificato. Ecco alcuni esempi:

  - **Exchange**: stacig@contoso.onmicrosoft.com <spam> <spam>

  - **SharePoint**: https <span>:// contoso.sharepoint.com/sites/marketing</span>

  - **OneDrive for Business**: https <span>://</span>contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com

- **Credenziali utente:** lo script utilizzerà le credenziali per connettersi a Exchange Online PowerShell o a PowerShell & Compliance Center usando l'autenticazione moderna. Come spiegato in precedenza, è necessario disporre delle autorizzazioni appropriate per eseguire correttamente questo script.

Per visualizzare un elenco delle cartelle delle cassette postali o dei nomi site documentlink (percorso):

1. Salvare il testo seguente in un file Windows PowerShell script utilizzando un suffisso di nome file .ps1; ad `GetFolderSearchParameters.ps1` esempio.

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

4. Immettere le informazioni richieste per lo script.

    Lo script visualizza un elenco delle cartelle delle cassette postali o delle cartelle del sito per l'utente specificato. Lasciare aperta questa finestra in modo che sia possibile copiare un ID cartella o un nome documentlink e incollarlo in una query di ricerca nel passaggio 2.

    > [!TIP]
    > Invece di visualizzare un elenco di cartelle sullo schermo del computer, puoi ri-indirizzare l'output dello script in un file di testo. Questo file verrà salvato nella cartella in cui si trova lo script. Ad esempio, per reindirizzare l'output dello script a un file di testo, eseguire il comando seguente nel passaggio 3: Quindi è possibile copiare un ID cartella o un documentlink dal file da utilizzare in una  `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` query di ricerca.

### <a name="script-output-for-mailbox-folders"></a>Output dello script per le cartelle delle cassette postali

Se si ottengono gli ID delle cartelle delle cassette postali, lo script si connette Exchange Online PowerShell, esegue il cmdlet **Get-MailboxFolderStatisics** e quindi visualizza l'elenco delle cartelle dalla cassetta postale specificata. Per ogni cartella nella cassetta postale, lo script visualizza il nome della cartella nella colonna **FolderPath** e l'ID della cartella nella **colonna FolderQuery.** Inoltre, lo script aggiunge il prefisso **di folderId** (che è il nome della proprietà della cassetta postale) all'ID cartella. Poiché la **proprietà folderid** è una proprietà ricercabile, verrà utilizzata in una query di ricerca nel  `folderid:<folderid>` passaggio 2 per cercare tale cartella. Lo script visualizza un massimo di 100 cartelle delle cassette postali.

> [!IMPORTANT]
> Lo script in questo articolo include la logica di codifica che converte i valori id cartella a 64 caratteri restituiti da **Get-MailboxFolderStatistics** nello stesso formato di 48 caratteri indicizzato per la ricerca. Se si esegue semplicemente il cmdlet **Get-MailboxFolderStatistics** in PowerShell per ottenere un ID cartella (anziché eseguire lo script in questo articolo), una query di ricerca che utilizza tale valore id cartella avrà esito negativo. È necessario eseguire lo script per ottenere gli ID di cartella formattati correttamente che possono essere utilizzati in una ricerca contenuto.

Ecco un esempio dell'output restituito dallo script per le cartelle delle cassette postali.

![Esempio dell'elenco delle cartelle delle cassette postali e degli ID delle cartelle restituiti dallo script](../media/cd739207-eb84-4ebf-a03d-703f3d3a797d.png)

Nell'esempio del passaggio 2 viene illustrata la query utilizzata per cercare la sottocartella Ripuliture nella cartella Elementi ripristinabili dell'utente.

### <a name="script-output-for-site-folders"></a>Output dello script per le cartelle del sito

Se si riceve il percorso della proprietà **documentlink** da siti di SharePoint o OneDrive for Business, lo script si connette a PowerShell sicurezza & conformità, crea una nuova ricerca contenuto che cerca le cartelle nel sito e quindi visualizza un elenco delle cartelle che si trovano nel sito specificato. Lo script visualizza il nome di ogni cartella e aggiunge il prefisso **di documentlink** all'URL della cartella. Poiché la **proprietà documentlink** è una proprietà ricercabile, si utilizzerà la coppia property:value in una query di ricerca nel passaggio 2 per cercare `documentlink:<path>` tale cartella. Lo script visualizza un massimo di 200 cartelle del sito. Se sono presenti più di 200 cartelle del sito, vengono visualizzate quelle più recenti.

Ecco un esempio dell'output restituito dallo script per le cartelle del sito.

![Esempio di elenco di nomi documentlink per le cartelle del sito restituite dallo script](../media/519e8347-7365-4067-af78-96c465dc3d15.png)

## <a name="step-2-use-a-folder-id-or-documentlink-to-perform-a-targeted-collection"></a>Passaggio 2: Usare un ID cartella o un documentlink per eseguire una raccolta di destinazione

Dopo aver eseguito lo script per raccogliere un elenco di ID cartella o collegamenti a documenti per un utente specifico, il passaggio successivo per passare al Centro conformità di Microsoft 365 e creare una nuova ricerca contenuto per eseguire ricerche in una cartella specifica. Verrà utilizzata la coppia o property:value nella query di ricerca configurata nella casella parola chiave Ricerca contenuto (o come valore del parametro ContentMatchQuery se si utilizza il `folderid:<folderid>` `documentlink:<path>` cmdlet **New-ComplianceSearch).**  È possibile combinare la  `folderid` proprietà o con altri parametri di ricerca o condizioni di  `documentlink` ricerca. Se si include solo la proprietà o nella query, la ricerca restituirà tutti gli  `folderid` elementi che si trovano nella cartella  `documentlink` specificata.

1. Passare a e accedere utilizzando l'account e le credenziali utilizzati per <https://compliance.microsoft.com> eseguire lo script nel passaggio 1.

2. Nel riquadro sinistro del Centro conformità fare clic su **Mostra** tutto  >  **ricerca contenuto** e quindi su Nuova **ricerca.**

3. Nella casella **Parole** chiave incollare il `folderid:<folderid>` valore o  `documentlink:<path>` restituito dallo script nel passaggio 1.

    Ad esempio, la query nello screenshot seguente cerca qualsiasi elemento nella sottocartella Ripuliture nella cartella Elementi ripristinabili dell'utente (il valore della proprietà per la sottocartella Ripuliture è mostrato nello screenshot nel `folderid` passaggio 1):

    ![Incollare il folderid o documentlink nella casella delle parole chiave della query di ricerca](../media/FolderIDSearchQuery.png)

4. In **Percorsi** selezionare **Percorsi specifici e** quindi fare clic su **Modifica.**

5. Eseguire una delle operazioni seguenti, a seconda che si cerchi una cartella della cassetta postale o una cartella del sito:

    - Accanto a **Exchange** posta elettronica fare clic su Scegli **utenti,** gruppi o team e quindi aggiungere la stessa cassetta postale specificata durante l'esecuzione dello script nel passaggio 1.

      Oppure

    - Accanto a **SharePoint** siti fare clic **su** Scegli siti e quindi aggiungere lo stesso URL di sito specificato durante l'esecuzione dello script nel passaggio 1.

6. Dopo aver salvato il percorso di contenuto in cui eseguire la ricerca, fare clic su Salva & **esecuzione,** digitare un nome per la ricerca contenuto e quindi fare clic **su** Salva per avviare la ricerca di raccolta di destinazione.

### <a name="examples-of-search-queries-for-targeted-collections"></a>Esempi di query di ricerca per raccolte di destinazione

Ecco alcuni esempi di utilizzo delle proprietà  `folderid` e in una query di ricerca per eseguire una raccolta di  `documentlink` destinazione. I segnaposto vengono utilizzati  `folderid:<folderid>` per e per risparmiare  `documentlink:<path>` spazio.

- In questo esempio viene eseguita una ricerca in tre diverse cartelle delle cassette postali. È possibile utilizzare una sintassi di query simile per cercare le cartelle nascoste nella cartella Elementi ripristinabili di un utente.

  ```powershell
  folderid:<folderid> OR folderid:<folderid> OR folderid:<folderid>
  ```

- In questo esempio viene eseguita una ricerca di elementi che contengono una frase esatta in una cartella delle cassette postali.

  ```powershell
  folderid:<folderid> AND "Contoso financial results"
  ```

- In questo esempio viene eseguita una ricerca in una cartella del sito (ed eventuali sottocartelle) di documenti contenenti le lettere "NDA" nel titolo.

  ```powershell
  documentlink:<path> AND filename:nda
  ```

- In questo esempio viene eseguita una ricerca in una cartella del sito (e in qualsiasi sottocartella) dei documenti che sono stati modificati in un intervallo di date.

  ```powershell
  documentlink:<path> AND (lastmodifiedtime>=01/01/2017 AND lastmodifiedtime<=01/21/2017)
  ```

## <a name="more-information"></a>Ulteriori informazioni

Quando si usa lo script in questo articolo per eseguire raccolte di destinazione, tenere presente quanto segue.

- Lo script non rimuove alcuna cartella dai risultati. Alcune cartelle elencate nei risultati potrebbero pertanto non essere ricercabili (o restituire zero elementi) perché contengono contenuto generato dal sistema o perché contengono solo sottocartelle e non elementi delle cassette postali.

- Questo script restituisce solo le informazioni sulla cartella per la cassetta postale principale dell'utente. Non restituisce informazioni sulle cartelle nella cassetta postale di archiviazione dell'utente. Per restituire informazioni sulle cartelle nella cassetta postale di archiviazione dell'utente, è possibile modificare lo script. A tale scopo, modificare la riga `$folderStatistics = Get-MailboxFolderStatistics $emailAddress` in e quindi salvare ed eseguire lo script `$folderStatistics = Get-MailboxFolderStatistics $emailAddress -Archive` modificato. Questa modifica restituirà gli ID cartella per cartelle e sottocartelle nella cassetta postale di archiviazione dell'utente. Per eseguire ricerche nell'intera cassetta postale di archiviazione, è possibile connettere tutte le coppie id cartella proprietà:valore a `OR` un operatore in una query di ricerca.

- Durante la ricerca nelle cartelle delle cassette postali, verrà eseguita la ricerca solo nella cartella specificata (identificata dalla relativa proprietà). Le sottocartelle non `folderid` verranno cercate. Per cercare le sottocartelle, è necessario utilizzare l'ID cartella per la sottocartella in cui si desidera eseguire la ricerca.

- Durante la ricerca nelle cartelle del sito, verrà eseguita la ricerca nella cartella (identificata dalla relativa proprietà) e in tutte le `documentlink` sottocartelle.

- Quando si esportano i risultati di una ricerca in cui è stata specificata solo la proprietà nella query di ricerca, è possibile scegliere la prima opzione di esportazione, "Tutti gli elementi, esclusi quelli con formato non riconosciuto, sono crittografati o non sono stati indicizzati per altri `folderid` motivi". Tutti gli elementi nella cartella verranno sempre esportati indipendentemente dal relativo stato di indicizzazione perché l'ID cartella è sempre indicizzato.
