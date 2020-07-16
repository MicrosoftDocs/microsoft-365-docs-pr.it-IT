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
ms.custom: seo-marvel-apr2020
description: Utilizzare la ricerca contenuto nel centro sicurezza & conformità per eseguire raccolte mirate, che garantiscono che gli elementi si trovino in una cassetta postale o in una cartella specifica del sito.
ms.openlocfilehash: fb7f900e8deaef6946d1ed8ea109d42207a882b3
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819106"
---
# <a name="use-content-search-for-targeted-collections"></a><span data-ttu-id="d89d1-103">Usare Ricerca contenuto per le raccolte di destinazione</span><span class="sxs-lookup"><span data-stu-id="d89d1-103">Use Content Search for targeted collections</span></span>

<span data-ttu-id="d89d1-104">La funzionalità di ricerca contenuto nel &amp; Centro sicurezza e conformità non fornisce un modo diretto nell'interfaccia utente per eseguire ricerche in cartelle specifiche nelle cassette postali di Exchange o nei siti di SharePoint e OneDrive for business.</span><span class="sxs-lookup"><span data-stu-id="d89d1-104">The Content Search feature in the Security &amp; Compliance Center doesn't provide a direct way in the UI to search specific folders in Exchange mailboxes or SharePoint and OneDrive for Business sites.</span></span> <span data-ttu-id="d89d1-105">Tuttavia, è possibile eseguire ricerche in cartelle specifiche (denominate *insieme mirato*) specificando la proprietà ID cartella per la proprietà posta elettronica o percorso (DocumentLink) per i siti nella sintassi della query di ricerca effettiva.</span><span class="sxs-lookup"><span data-stu-id="d89d1-105">However, it's possible to search specific folders (called a *targeted collection*) by specifying the folder ID property for email or path (DocumentLink) property for sites in the actual search query syntax.</span></span> <span data-ttu-id="d89d1-106">L'utilizzo di ricerca contenuto per l'esecuzione di una raccolta mirata è utile quando si è certi che gli elementi sensibili a un caso o a elementi privilegiati si trovino in una specifica cassetta postale o cartella del sito.</span><span class="sxs-lookup"><span data-stu-id="d89d1-106">Using Content Search to perform a targeted collection is useful when you're confident that items responsive to a case or privileged items are located in a specific mailbox or site folder.</span></span> <span data-ttu-id="d89d1-107">È possibile utilizzare lo script in questo articolo per ottenere l'ID della cartella per le cartelle delle cassette postali o il percorso (DocumentLink) per le cartelle in un sito di SharePoint e OneDrive for business.</span><span class="sxs-lookup"><span data-stu-id="d89d1-107">You can use the script in this article to obtain the folder ID for mailbox folders or the path (DocumentLink) for folders on a SharePoint and OneDrive for Business site.</span></span> <span data-ttu-id="d89d1-108">Successivamente, è possibile utilizzare l'ID o il percorso della cartella in una query di ricerca per restituire gli elementi che si trovano nella cartella.</span><span class="sxs-lookup"><span data-stu-id="d89d1-108">Then you can use the folder ID or path in a search query to return items located in the folder.</span></span>

> [!NOTE]
> <span data-ttu-id="d89d1-109">Per restituire il contenuto presente in una cartella di un sito di SharePoint o OneDrive for business, lo script in questo argomento utilizza la proprietà gestita DocumentLink anziché la proprietà Path.</span><span class="sxs-lookup"><span data-stu-id="d89d1-109">To return content located in a folder in a SharePoint or OneDrive for Business site, the script in this topic uses the DocumentLink managed property instead of the Path property.</span></span> <span data-ttu-id="d89d1-110">La proprietà DocumentLink è più robusta della proprietà Path perché restituirà tutto il contenuto di una cartella, mentre la proprietà Path non restituirà alcuni file multimediali.</span><span class="sxs-lookup"><span data-stu-id="d89d1-110">The DocumentLink property is more robust than the Path property because it will return all content in a folder, whereas the Path property won't return some media files.</span></span>

## <a name="before-you-use-content-search"></a><span data-ttu-id="d89d1-111">Prima di utilizzare la ricerca contenuto</span><span class="sxs-lookup"><span data-stu-id="d89d1-111">Before you use Content Search</span></span>

- <span data-ttu-id="d89d1-112">Per eseguire lo script nel passaggio 1, è necessario essere membri del gruppo di ruoli eDiscovery Manager nel &amp; Centro sicurezza e conformità.</span><span class="sxs-lookup"><span data-stu-id="d89d1-112">You have to be a member of the eDiscovery Manager role group in the Security &amp; Compliance Center to run the script in Step 1.</span></span> <span data-ttu-id="d89d1-113">Per altre informazioni, vedere [Assegnare autorizzazioni di eDiscovery](assign-ediscovery-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="d89d1-113">For more information, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>
    
    <span data-ttu-id="d89d1-114">Inoltre, è necessario essere assegnati al ruolo destinatari di posta elettronica nell'organizzazione di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="d89d1-114">Additionally, you have to be assigned the Mail Recipients role in your Exchange Online organization.</span></span> <span data-ttu-id="d89d1-115">Questo è necessario per eseguire il cmdlet **Get-MailboxFolderStatistics** , incluso nello script nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="d89d1-115">This is required to run the **Get-MailboxFolderStatistics** cmdlet, which is included in the script in Step 1.</span></span> <span data-ttu-id="d89d1-116">Per impostazione predefinita, il ruolo destinatari di posta viene assegnato ai gruppi di ruoli Gestione organizzazione e gestione destinatari in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="d89d1-116">By default, the Mail Recipients role is assigned to the Organization Management and Recipient Management role groups in Exchange Online.</span></span> <span data-ttu-id="d89d1-117">Per ulteriori informazioni sull'assegnazione delle autorizzazioni in Exchange Online, vedere [Manage Role Group Members](https://go.microsoft.com/fwlink/p/?linkid=692102).</span><span class="sxs-lookup"><span data-stu-id="d89d1-117">For more information about assigning permissions in Exchange Online, see [Manage role group members](https://go.microsoft.com/fwlink/p/?linkid=692102).</span></span> <span data-ttu-id="d89d1-118">È inoltre possibile creare un gruppo di ruoli personalizzato, assegnare il ruolo destinatari di posta elettronica e quindi aggiungere i membri che devono eseguire lo script nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="d89d1-118">You could also create a custom role group, assign the Mail Recipients role to it, and then add the members who need to run the script in Step 1.</span></span> <span data-ttu-id="d89d1-119">Per ulteriori informazioni, vedere [Gestire gruppi di ruoli](https://go.microsoft.com/fwlink/p/?linkid=730688).</span><span class="sxs-lookup"><span data-stu-id="d89d1-119">For more information, see [Manage role groups](https://go.microsoft.com/fwlink/p/?linkid=730688).</span></span>
    
- <span data-ttu-id="d89d1-120">Ogni volta che si esegue lo script nel passaggio 1, viene creata una nuova sessione di PowerShell remota.</span><span class="sxs-lookup"><span data-stu-id="d89d1-120">Each time you run the script in Step 1, a new remote PowerShell session is created.</span></span> <span data-ttu-id="d89d1-121">In questo modo, è possibile utilizzare tutte le sessioni remote di PowerShell disponibili.</span><span class="sxs-lookup"><span data-stu-id="d89d1-121">So you could use up all the remote PowerShell sessions available to you.</span></span> <span data-ttu-id="d89d1-122">Per evitare che ciò accada, è possibile eseguire il comando riportato di seguito per disconnettere le sessioni di PowerShell remote attive.</span><span class="sxs-lookup"><span data-stu-id="d89d1-122">To prevent this from happening, you can run the following command to disconnect your active remote PowerShell sessions.</span></span>
    
  ```powershell
  Get-PSSession | Remove-PSSession
  ```

    <span data-ttu-id="d89d1-123">Per ulteriori informazioni, vedere [Connessione a Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span><span class="sxs-lookup"><span data-stu-id="d89d1-123">For more information, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>
    
- <span data-ttu-id="d89d1-124">Lo script include la gestione degli errori minima.</span><span class="sxs-lookup"><span data-stu-id="d89d1-124">The script includes minimal error handling.</span></span> <span data-ttu-id="d89d1-125">Lo scopo principale dello script è la visualizzazione rapida di un elenco di ID cartella delle cassette postali o percorsi del sito che è possibile utilizzare nella sintassi delle query di ricerca di una ricerca contenuto per l'esecuzione di una raccolta di destinazione.</span><span class="sxs-lookup"><span data-stu-id="d89d1-125">The primary purpose of the script is to quickly display a list of mailbox folder IDs or site paths that can be used in the search query syntax of a Content Search to perform a targeted collection.</span></span>
    
- <span data-ttu-id="d89d1-126">Lo script di esempio fornito in questo argomento non è supportato in alcun servizio o programma di supporto Microsoft standard.</span><span class="sxs-lookup"><span data-stu-id="d89d1-126">The sample script provided in this topic isn't supported under any Microsoft standard support program or service.</span></span> <span data-ttu-id="d89d1-127">Lo script di esempio viene fornito come senza garanzie di alcun tipo.</span><span class="sxs-lookup"><span data-stu-id="d89d1-127">The sample script is provided AS IS without warranty of any kind.</span></span> <span data-ttu-id="d89d1-128">Inoltre Microsoft declina ogni responsabilità su garanzie implicite, senza alcuna limitazione, incluse le garanzie implicite di commerciabilità e/o adeguatezza per uno scopo specifico.</span><span class="sxs-lookup"><span data-stu-id="d89d1-128">Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.</span></span> <span data-ttu-id="d89d1-129">L'intero rischio derivante dall'utilizzo o dalle prestazioni dello script di esempio e della documentazione resta all'interno dell'utente.</span><span class="sxs-lookup"><span data-stu-id="d89d1-129">The entire risk arising out of the use or performance of the sample script and documentation remains with you.</span></span> <span data-ttu-id="d89d1-130">In nessun caso Microsoft, i suoi autori o chiunque altro coinvolto nella creazione, produzione o consegna degli script è da ritenersi responsabile per qualsiasi danno eventuale (inclusi, senza limitazione alcuna, danni riguardanti profitti aziendali, interruzione di attività, perdita di informazioni aziendali o altra perdita pecuniaria) derivanti dall'utilizzo o dall'incapacità di utilizzo degli script di esempio e della documentazione, anche nel caso in cui Microsoft sia stata avvisata della possibilità di tali danni.</span><span class="sxs-lookup"><span data-stu-id="d89d1-130">In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
  
## <a name="step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site"></a><span data-ttu-id="d89d1-131">Passaggio 1: eseguire lo script per ottenere un elenco di cartelle per una cassetta postale o un sito</span><span class="sxs-lookup"><span data-stu-id="d89d1-131">Step 1: Run the script to get a list of folders for a mailbox or site</span></span>

<span data-ttu-id="d89d1-132">Lo script eseguito in questo primo passaggio restituirà un elenco di cartelle di cassette postali o di SharePoint e OneDrive for business e l'ID o il percorso corrispondente per ogni cartella.</span><span class="sxs-lookup"><span data-stu-id="d89d1-132">The script that you run in this first step will return a list of mailbox folders or SharePoint and OneDrive for Business folders, and the corresponding folder ID or path for each folder.</span></span> <span data-ttu-id="d89d1-133">Quando si esegue questo script, vengono richieste le informazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="d89d1-133">When you run this script, it will prompt you for the following information.</span></span>
  
- <span data-ttu-id="d89d1-134">**Indirizzo di posta elettronica o URL del sito** Digitare un indirizzo di posta elettronica del custode per restituire un elenco di cartelle di cassette postali di Exchange e ID cartella.</span><span class="sxs-lookup"><span data-stu-id="d89d1-134">**Email address or site URL** Type an email address of the custodian to return a list of Exchange mailbox folders and folder IDs.</span></span> <span data-ttu-id="d89d1-135">In alternativa, digitare l'URL di un sito di SharePoint o di un sito di OneDrive for business per restituire un elenco di percorsi per il sito specificato.</span><span class="sxs-lookup"><span data-stu-id="d89d1-135">Or type the URL for a SharePoint site or a OneDrive for Business site to return a list of paths for the specified site.</span></span> <span data-ttu-id="d89d1-136">Ecco alcuni esempi:</span><span class="sxs-lookup"><span data-stu-id="d89d1-136">Here are some examples:</span></span> 
    
  - <span data-ttu-id="d89d1-137">**Exchange** -stacig@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="d89d1-137">**Exchange** - stacig@contoso.onmicrosoft.com</span></span> 
    
  - <span data-ttu-id="d89d1-138">**SharePoint** - https://contoso.sharepoint.com/sites/marketing</span><span class="sxs-lookup"><span data-stu-id="d89d1-138">**SharePoint** - https://contoso.sharepoint.com/sites/marketing</span></span> 
    
  - <span data-ttu-id="d89d1-139">**OneDrive for business** - https://contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com</span><span class="sxs-lookup"><span data-stu-id="d89d1-139">**OneDrive for Business** - https://contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com</span></span> 
    
- <span data-ttu-id="d89d1-140">**Credenziali utente** : lo script utilizzerà le credenziali per la connessione a Exchange Online e il centro sicurezza & conformità con Remote PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d89d1-140">**Your user credentials** - The script will use your credentials to connect to Exchange Online and the Security & Compliance Center with remote PowerShell.</span></span> <span data-ttu-id="d89d1-141">Come spiegato in precedenza, è necessario assegnare le autorizzazioni appropriate per eseguire correttamente lo script.</span><span class="sxs-lookup"><span data-stu-id="d89d1-141">As previously explained, you have to assigned the appropriate permissions to successfully run this script.</span></span>
    
<span data-ttu-id="d89d1-142">Per visualizzare un elenco delle cartelle delle cassette postali o dei nomi del sito documentlink (percorso):</span><span class="sxs-lookup"><span data-stu-id="d89d1-142">To display a list of mailbox folders or site documentlink (path) names:</span></span>
  
1. <span data-ttu-id="d89d1-143">Salvare il testo seguente in un file di script di Windows PowerShell utilizzando un suffisso FileName di. ps1. ad esempio, `GetFolderSearchParameters.ps1` .</span><span class="sxs-lookup"><span data-stu-id="d89d1-143">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `GetFolderSearchParameters.ps1`.</span></span>
    
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

2. <span data-ttu-id="d89d1-144">Nel computer locale, aprire Windows PowerShell e passare alla cartella in cui è stato salvato lo script.</span><span class="sxs-lookup"><span data-stu-id="d89d1-144">On your local computer, open Windows PowerShell and go to the folder where you saved the script.</span></span>
    
3. <span data-ttu-id="d89d1-145">Eseguire lo script; Per esempio:</span><span class="sxs-lookup"><span data-stu-id="d89d1-145">Run the script; for example:</span></span>
    
      ```powershell
      .\GetFolderSearchParameters.ps1
      ```

4. <span data-ttu-id="d89d1-146">Immettere le informazioni richieste dallo script.</span><span class="sxs-lookup"><span data-stu-id="d89d1-146">Enter the information that the script prompts you for.</span></span>
    
    <span data-ttu-id="d89d1-147">Nello script viene visualizzato un elenco di cartelle di cassette postali o di cartelle del sito per l'utente specificato.</span><span class="sxs-lookup"><span data-stu-id="d89d1-147">The script displays a list of mailbox folders or site folders for the specified user.</span></span> <span data-ttu-id="d89d1-148">Lasciare aperta la finestra in modo che sia possibile copiare un ID cartella o un nome di documentlink e incollarlo in una query di ricerca nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="d89d1-148">Let this window open so that you can copy a folder ID or documentlink name and paste it in to a search query in Step 2.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="d89d1-149">Invece di visualizzare un elenco di cartelle sullo schermo del computer, è possibile reindirizzare l'output dello script in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="d89d1-149">Instead of displaying a list of folders on the computer screen, you can re-direct the output of the script to a text file.</span></span> <span data-ttu-id="d89d1-150">Questo file verrà salvato nella cartella in cui si trova lo script.</span><span class="sxs-lookup"><span data-stu-id="d89d1-150">This file will be saved to the folder where the script is located.</span></span> <span data-ttu-id="d89d1-151">Ad esempio, per reindirizzare l'output dello script in un file di testo, eseguire il comando riportato di seguito nel passaggio 3: `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` è possibile copiare un ID cartella o documentlink dal file da utilizzare in una query di ricerca.</span><span class="sxs-lookup"><span data-stu-id="d89d1-151">For example, to redirect the script output to a text file, run the following command in Step 3:  `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` Then you can copy a folder ID or documentlink from the file to use in a search query.</span></span>
  
### <a name="script-output-for-mailbox-folders"></a><span data-ttu-id="d89d1-152">Output dello script per le cartelle delle cassette postali</span><span class="sxs-lookup"><span data-stu-id="d89d1-152">Script output for mailbox folders</span></span>

<span data-ttu-id="d89d1-153">Se si ricevono gli ID della cartella delle cassette postali, lo script si connette a Exchange Online tramite Remote PowerShell, esegue il cmdlet **Get-MailboxFolderStatisics** e quindi Visualizza l'elenco delle cartelle dalla cassetta postale specificata.</span><span class="sxs-lookup"><span data-stu-id="d89d1-153">If you're getting mailbox folder IDs, the script connects to Exchange Online by using remote PowerShell, runs the **Get-MailboxFolderStatisics** cmdlet, and then displays the list of the folders from the specified mailbox.</span></span> <span data-ttu-id="d89d1-154">Per ogni cartella della cassetta postale, nello script viene visualizzato il nome della cartella nella colonna **percorsocartella** e l'ID della cartella nella colonna **FolderQuery** .</span><span class="sxs-lookup"><span data-stu-id="d89d1-154">For every folder in the mailbox, the script displays the name of the folder in the **FolderPath** column and the folder ID in the **FolderQuery** column.</span></span> <span data-ttu-id="d89d1-155">Inoltre, lo script aggiunge il prefisso di **FolderId** (che è il nome della proprietà della cassetta postale) all'ID della cartella.</span><span class="sxs-lookup"><span data-stu-id="d89d1-155">Additionally, the script adds the prefix of **folderId** (which is the name of the mailbox property) to the folder ID.</span></span> <span data-ttu-id="d89d1-156">Poiché la proprietà **FolderId** è una proprietà ricercabile, è possibile utilizzare `folderid:<folderid>` in una query di ricerca nel passaggio 2 per eseguire una ricerca in tale cartella.</span><span class="sxs-lookup"><span data-stu-id="d89d1-156">Because the **folderid** property is a searchable property, you'll use  `folderid:<folderid>` in a search query in Step 2 to search that folder.</span></span> <span data-ttu-id="d89d1-157">Lo script Visualizza un massimo di 100 cartelle di cassette postali.</span><span class="sxs-lookup"><span data-stu-id="d89d1-157">The script displays a maximum of 100 mailbox folders.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d89d1-158">Lo script in questo articolo include la logica di codifica che converte i valori ID della cartella di 64 caratteri restituiti da **Get-MailboxFolderStatistics** allo stesso formato 48-character indicizzato per la ricerca.</span><span class="sxs-lookup"><span data-stu-id="d89d1-158">The script in this article includes encoding logic that converts the 64-character folder Id values that are returned by **Get-MailboxFolderStatistics** to the same 48-character format that is indexed for search.</span></span> <span data-ttu-id="d89d1-159">Se si esegue il cmdlet **Get-MailboxFolderStatistics** in PowerShell per ottenere un ID cartella (invece di eseguire lo script in questo articolo), una query di ricerca che utilizza tale valore ID cartella avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="d89d1-159">If you just run the **Get-MailboxFolderStatistics** cmdlet in PowerShell to obtain a folder Id (instead of running the script in this article), a search query that uses that folder Id value will fail.</span></span> <span data-ttu-id="d89d1-160">È necessario eseguire lo script per ottenere gli ID di cartella formattati correttamente che possono essere utilizzati in una ricerca di contenuto.</span><span class="sxs-lookup"><span data-stu-id="d89d1-160">You have to run the script to get the correctly-formatted folder Ids that can be used in a Content Search.</span></span>
  
<span data-ttu-id="d89d1-161">Di seguito è riportato un esempio dell'output restituito dallo script per le cartelle delle cassette postali.</span><span class="sxs-lookup"><span data-stu-id="d89d1-161">Here's an example of the output returned by the script for mailbox folders.</span></span>
  
![Esempio dell'elenco di cartelle di cassette postali e ID cartella restituiti dallo script](../media/cd739207-eb84-4ebf-a03d-703f3d3a797d.png)
  
<span data-ttu-id="d89d1-163">Nell'esempio del passaggio 2 viene illustrata la query utilizzata per eseguire la ricerca nella sottocartella Ripuliture nella cartella elementi ripristinabili dell'utente.</span><span class="sxs-lookup"><span data-stu-id="d89d1-163">The example in Step 2 shows the query used to search the Purges subfolder in the user's Recoverable Items folder.</span></span>
  
### <a name="script-output-for-site-folders"></a><span data-ttu-id="d89d1-164">Output dello script per le cartelle del sito</span><span class="sxs-lookup"><span data-stu-id="d89d1-164">Script output for site folders</span></span>

<span data-ttu-id="d89d1-165">Se si riceve il percorso della proprietà **documentlink** da siti di SharePoint o OneDrive for business, lo script si connette al centro sicurezza & conformità tramite Remote PowerShell, crea una nuova ricerca di contenuto in cui vengono eseguite ricerche nel sito per le cartelle e quindi viene visualizzato un elenco delle cartelle che si trovano nel sito specificato.</span><span class="sxs-lookup"><span data-stu-id="d89d1-165">If you're getting the path of the **documentlink** property from SharePoint or OneDrive for Business sites, the script connects to the Security & Compliance Center using remote PowerShell, creates a new Content Search that searches the site for folders, and then displays a list of the folders located in the specified site.</span></span> <span data-ttu-id="d89d1-166">Lo script Visualizza il nome di ogni cartella e aggiunge il prefisso di **documentlink** all'URL della cartella.</span><span class="sxs-lookup"><span data-stu-id="d89d1-166">The script displays the name of each folder and adds the prefix of **documentlink** to the folder URL.</span></span> <span data-ttu-id="d89d1-167">Poiché la proprietà **documentlink** è una proprietà per la ricerca, è possibile utilizzare la `documentlink:<path>` coppia Property: value in una query di ricerca nel passaggio 2 per eseguire una ricerca nella cartella.</span><span class="sxs-lookup"><span data-stu-id="d89d1-167">Because the **documentlink** property is a searchable property, you'll use `documentlink:<path>` property:value pair in a search query in Step 2 to search that folder.</span></span> <span data-ttu-id="d89d1-168">Lo script Visualizza un massimo di 200 cartelle del sito.</span><span class="sxs-lookup"><span data-stu-id="d89d1-168">The script displays a maximum of 200 site folders.</span></span> <span data-ttu-id="d89d1-169">Se sono presenti più di 200 cartelle del sito, vengono visualizzate quelle più recenti.</span><span class="sxs-lookup"><span data-stu-id="d89d1-169">If there are more than 200 site folders, the newest ones are displayed.</span></span>
  
<span data-ttu-id="d89d1-170">Di seguito è riportato un esempio dell'output restituito dallo script per le cartelle del sito.</span><span class="sxs-lookup"><span data-stu-id="d89d1-170">Here's an example of the output returned by the script for site folders.</span></span>
  
![Esempio dell'elenco di nomi di documentlink per le cartelle del sito restituite dallo script](../media/519e8347-7365-4067-af78-96c465dc3d15.png)
  
## <a name="step-2-use-a-folder-id-or-documentlink-to-perform-a-targeted-collection"></a><span data-ttu-id="d89d1-172">Passaggio 2: utilizzare un ID cartella o documentlink per eseguire una raccolta di destinazione</span><span class="sxs-lookup"><span data-stu-id="d89d1-172">Step 2: Use a folder ID or documentlink to perform a targeted collection</span></span>

<span data-ttu-id="d89d1-173">Dopo aver eseguito lo script per raccogliere un elenco di ID cartella o documentlinks per un utente specifico, il passaggio successivo per accedere al centro sicurezza & compliance e creare una nuova ricerca contenuto per eseguire la ricerca in una cartella specifica.</span><span class="sxs-lookup"><span data-stu-id="d89d1-173">After you've run the script to collect a list of folder IDs or documentlinks for a specific user, the next step to go to the Security & Compliance Center and create a new Content Search to search a specific folder.</span></span> <span data-ttu-id="d89d1-174">Si utilizzerà la `folderid:<folderid>` `documentlink:<path>` coppia o proprietà: valore nella query di ricerca configurata nella casella parola chiave ricerca contenuto (o come valore per il parametro *ContentMatchQuery* se si utilizza il cmdlet **New-ComplianceSearch** ).</span><span class="sxs-lookup"><span data-stu-id="d89d1-174">You'll use the  `folderid:<folderid>` or  `documentlink:<path>` property:value pair in the search query that you configure in the Content Search keyword box (or as the value for the  *ContentMatchQuery*  parameter if you use the **New-ComplianceSearch** cmdlet).</span></span> <span data-ttu-id="d89d1-175">È possibile combinare la `folderid` `documentlink` Proprietà or con altri parametri di ricerca o condizioni di ricerca.</span><span class="sxs-lookup"><span data-stu-id="d89d1-175">You can combine the  `folderid` or  `documentlink` property with other search parameters or search conditions.</span></span> <span data-ttu-id="d89d1-176">Se nella query è inclusa solo la `folderid` `documentlink` Proprietà or, la ricerca restituirà tutti gli elementi presenti nella cartella specificata.</span><span class="sxs-lookup"><span data-stu-id="d89d1-176">If you only include the  `folderid` or  `documentlink` property in the query, the search will return all items located in the specified folder.</span></span> 
  
1. <span data-ttu-id="d89d1-177">Passare a [https://protection.office.com](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="d89d1-177">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="d89d1-178">Accedere utilizzando l'account e le credenziali utilizzati per eseguire lo script nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="d89d1-178">Sign in using the account and credentials that you used to run the script in Step 1.</span></span>
    
3. <span data-ttu-id="d89d1-179">Nel riquadro sinistro del Centro sicurezza & conformità fare clic su ricerca **Search** \> **contenuto**ricerca, quindi fare clic su **nuova** ![ icona Aggiungi ](../media/O365-MDM-CreatePolicy-AddIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="d89d1-179">In the left pane of the Security & Compliance Center, click **Search** \> **Content search**, and then click **New** ![Add icon](../media/O365-MDM-CreatePolicy-AddIcon.gif).</span></span>
    
4. <span data-ttu-id="d89d1-180">Nella pagina **Nuova ricerca**, digitare un nome relativo alla ricerca contenuto.</span><span class="sxs-lookup"><span data-stu-id="d89d1-180">On the **New search** page, type a name for the Content Search.</span></span> <span data-ttu-id="d89d1-181">Questo nome deve essere univoco nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d89d1-181">This name has to be unique in your organization.</span></span> 
    
5. <span data-ttu-id="d89d1-182">In **dove si desidera**eseguire la ricerca, eseguire una delle operazioni seguenti, a seconda che si cerchi una cartella della cassetta postale o una cartella del sito:</span><span class="sxs-lookup"><span data-stu-id="d89d1-182">Under **Where do you want us to look**, do one of the following, based on whether you're searching a mailbox folder or a site folder:</span></span>
    
    - <span data-ttu-id="d89d1-183">Fare clic su **Scegli cassette postali specifiche da cercare** e quindi aggiungere la stessa cassetta postale specificata al momento dell'esecuzione dello script nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="d89d1-183">Click **Choose specific mailboxes to search** and then add the same mailbox that you specified when you ran the script in Step 1.</span></span> 
    
      <span data-ttu-id="d89d1-184">Oppure</span><span class="sxs-lookup"><span data-stu-id="d89d1-184">Or</span></span>
    
    - <span data-ttu-id="d89d1-185">Fare clic su **Scegli siti specifici per cercare** e quindi aggiungere lo stesso URL del sito specificato durante l'esecuzione dello script nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="d89d1-185">Click **Choose specific sites to search** to search and then add the same site URL that you specified when you ran the script in Step 1.</span></span> 
    
6. <span data-ttu-id="d89d1-186">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d89d1-186">Click **Next**.</span></span>
    
7. <span data-ttu-id="d89d1-187">Nella casella parola chiave della pagina **che cosa si desidera cercare per** la pagina, incollare il `folderid:<folderid>` valore o `documentlink:<path>` restituito dallo script nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="d89d1-187">In the keyword box on the **What do you want us to look for** page, paste the  `folderid:<folderid>` or  `documentlink:<path>` value that was returned by the script in Step 1.</span></span> 
    
    <span data-ttu-id="d89d1-188">Ad esempio, la query nello screenshot seguente cercherà tutti gli elementi nella sottocartella Purges nella cartella elementi ripristinabili dell'utente (il valore della `folderid` proprietà per la sottocartella Purges viene visualizzato nello screenshot del passaggio 1):</span><span class="sxs-lookup"><span data-stu-id="d89d1-188">For example, the query in the following screenshot will search for any item in the Purges subfolder in the user's Recoverable Items folder (the value of the `folderid` property for the Purges subfolder is shown in the screenshot in Step 1):</span></span>
    
    ![Incollare il FolderId o documentlink nella casella parola chiave della query di ricerca](../media/84057516-b663-48a4-a78f-8032a8f8da80.png)
  
8. <span data-ttu-id="d89d1-190">Fare clic su **Cerca** per avviare la ricerca di raccolta di destinazione.</span><span class="sxs-lookup"><span data-stu-id="d89d1-190">Click **Search** to start the targeted collection search.</span></span> 
  
### <a name="examples-of-search-queries-for-targeted-collections"></a><span data-ttu-id="d89d1-191">Esempi di query di ricerca per gli insiemi di destinazione</span><span class="sxs-lookup"><span data-stu-id="d89d1-191">Examples of search queries for targeted collections</span></span>

<span data-ttu-id="d89d1-192">Di seguito sono riportati alcuni esempi di utilizzo delle `folderid` `documentlink` proprietà e in una query di ricerca per l'esecuzione di una raccolta di destinazione.</span><span class="sxs-lookup"><span data-stu-id="d89d1-192">Here are some examples of using the  `folderid` and  `documentlink` properties in a search query to perform a targeted collection.</span></span> <span data-ttu-id="d89d1-193">Si noti che i segnaposto vengono utilizzati per `folderid:<folderid>` e `documentlink:<path>` per risparmiare spazio.</span><span class="sxs-lookup"><span data-stu-id="d89d1-193">Note that placeholders are used for  `folderid:<folderid>` and  `documentlink:<path>` to save space.</span></span> 
  
- <span data-ttu-id="d89d1-194">In questo esempio vengono cercate tre cartelle di cassette postali diverse.</span><span class="sxs-lookup"><span data-stu-id="d89d1-194">This example searches three different mailbox folders.</span></span> <span data-ttu-id="d89d1-195">È possibile utilizzare una sintassi di query simile per cercare le cartelle nascoste nella cartella elementi ripristinabili di un utente.</span><span class="sxs-lookup"><span data-stu-id="d89d1-195">You could use similar query syntax to search the hidden folders in a user's Recoverable Items folder.</span></span>
    
  ```powershell
  folderid:<folderid> OR folderid:<folderid> OR folderid:<folderid>
  ```

- <span data-ttu-id="d89d1-196">In questo esempio viene eseguita la ricerca di elementi che contengono una frase esatta in una cartella della cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="d89d1-196">This example searches a mailbox folder for items that contain an exact phrase.</span></span>
    
  ```powershell
  folderid:<folderid> AND "Contoso financial results"
  ```

- <span data-ttu-id="d89d1-197">In questo esempio viene eseguita una ricerca in una cartella del sito e in tutte le sottocartelle per i documenti che contengono le lettere "NDA" nel titolo.</span><span class="sxs-lookup"><span data-stu-id="d89d1-197">This example searches a site folder (and any subfolders) for documents that contain the letters "NDA" in the title.</span></span>
    
  ```powershell
  documentlink:<path> AND filename:nda
  ```

- <span data-ttu-id="d89d1-198">In questo esempio viene eseguita una ricerca in una cartella del sito e in qualsiasi sottocartella per i documenti che sono stati modificati all'interno di un intervallo di date.</span><span class="sxs-lookup"><span data-stu-id="d89d1-198">This example searches a site folder (and any subfolder) for documents there were changed within a date range.</span></span>
    
  ```powershell
  documentlink:<path> AND (lastmodifiedtime>=01/01/2017 AND lastmodifiedtime<=01/21/2017)
  ```

## <a name="more-information"></a><span data-ttu-id="d89d1-199">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="d89d1-199">More information</span></span>

<span data-ttu-id="d89d1-200">Quando si utilizza lo script in questo articolo, è necessario tenere presente quanto segue per eseguire le raccolte mirate.</span><span class="sxs-lookup"><span data-stu-id="d89d1-200">Keep the following things in mind when using the script in this article to perform targeted collections.</span></span>
  
- <span data-ttu-id="d89d1-201">Lo script non rimuove alcuna cartella dai risultati.</span><span class="sxs-lookup"><span data-stu-id="d89d1-201">The script doesn't remove any folders from the results.</span></span> <span data-ttu-id="d89d1-202">Pertanto, alcune cartelle elencate nei risultati potrebbero non essere ricercabili (o restituire zero elementi) perché contengono contenuto generato dal sistema.</span><span class="sxs-lookup"><span data-stu-id="d89d1-202">So some folders listed in the results might be unsearchable (or return zero items) because they contain system-generated content.</span></span>
    
- <span data-ttu-id="d89d1-203">Questo script restituisce solo informazioni sulla cartella per la cassetta postale principale dell'utente.</span><span class="sxs-lookup"><span data-stu-id="d89d1-203">This script only returns folder information for the user's primary mailbox.</span></span> <span data-ttu-id="d89d1-204">Non restituisce informazioni sulle cartelle nella cassetta postale di archiviazione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="d89d1-204">It doesn't return information about folders in the user's archive mailbox.</span></span>
    
- <span data-ttu-id="d89d1-205">Quando si eseguono ricerche nelle cartelle delle cassette postali, verrà eseguita la ricerca solo nella cartella specificata (identificata dalla relativa `folderid` proprietà); le sottocartelle non verranno cercate.</span><span class="sxs-lookup"><span data-stu-id="d89d1-205">When searching mailbox folders, only the specified folder (identified by its  `folderid` property) will be searched; subfolders won't be searched.</span></span> <span data-ttu-id="d89d1-206">Per eseguire la ricerca in cartelle secondarie, è necessario utilizzare l'ID cartella per la sottocartella che si desidera ricercare.</span><span class="sxs-lookup"><span data-stu-id="d89d1-206">To search sub-folders, you need to use the  folder ID for the sub-folder that you want to search.</span></span> 
    
- <span data-ttu-id="d89d1-207">Quando si esegue la ricerca nelle cartelle del sito, la cartella (identificata dalla relativa `documentlink` proprietà) e tutte le sottocartelle verranno ricercate.</span><span class="sxs-lookup"><span data-stu-id="d89d1-207">When searching site folders, the folder (identified by its  `documentlink` property) and all sub-folders will be searched.</span></span> 
    
- <span data-ttu-id="d89d1-208">Quando si esportano i risultati di una ricerca in cui è stata specificata solo la `folderid` proprietà nella query di ricerca, è possibile scegliere la prima opzione di esportazione, "tutti gli elementi, esclusi quelli con formato non riconosciuto, sono crittografati o non sono stati indicizzati per altri motivi".</span><span class="sxs-lookup"><span data-stu-id="d89d1-208">When exporting the results of a search in which you only specified the `folderid` property in the search query, you can choose the first export option, "All items, excluding ones that have an unrecognized format, are encrypted, or weren't indexed for other reasons."</span></span> <span data-ttu-id="d89d1-209">Tutti gli elementi della cartella verranno sempre esportati indipendentemente dallo stato di indicizzazione, poiché l'ID della cartella è sempre indicizzato.</span><span class="sxs-lookup"><span data-stu-id="d89d1-209">All items in the folder will always be exported regardless of their indexing status because the folder ID is always indexed.</span></span>
