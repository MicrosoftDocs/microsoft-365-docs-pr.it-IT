---
title: Cercare nella cassetta postale & OneDrive for Business un elenco di utenti con Ricerca contenuto
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/3/2017
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
ms.assetid: 5f4f8206-2d6a-4cb2-bbc6-7a0698703cc0
description: Usare Ricerca contenuto e lo script in questo articolo per cercare un gruppo di utenti nelle cassette postali e nei siti di OneDrive for Business.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 51e668438c6016a0c5f2c914dc2b2e86cc56f49e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922468"
---
# <a name="use-content-search-to-search-the-mailbox-and-onedrive-for-business-site-for-a-list-of-users"></a><span data-ttu-id="e8dd5-103">Usare Ricerca contenuto per cercare un elenco di utenti nella cassetta postale e nel sito di OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="e8dd5-103">Use Content Search to search the mailbox and OneDrive for Business site for a list of users</span></span>

<span data-ttu-id="e8dd5-104">Il Centro sicurezza & conformità offre una serie di Windows PowerShell che consentono di automatizzare le attività correlate a eDiscovery che richiedono molto tempo.</span><span class="sxs-lookup"><span data-stu-id="e8dd5-104">The Security & Compliance Center provides a number of Windows PowerShell cmdlets that let you automate time-consuming eDiscovery-related tasks.</span></span> <span data-ttu-id="e8dd5-105">Attualmente, la creazione di una ricerca di contenuto nel Centro sicurezza & conformità per la ricerca in un numero elevato di posizioni di contenuto responsabile richiede tempo e preparazione.</span><span class="sxs-lookup"><span data-stu-id="e8dd5-105">Currently, creating a Content Search in the Security & Compliance Center to search a large number of custodian content locations takes time and preparation.</span></span> <span data-ttu-id="e8dd5-106">Prima di creare una ricerca, è necessario raccogliere l'URL per ogni sito di OneDrive for Business e quindi aggiungere ogni cassetta postale e il sito di OneDrive for Business alla ricerca.</span><span class="sxs-lookup"><span data-stu-id="e8dd5-106">Before you create a search, you have to collect the URL for each OneDrive for Business site and then add each mailbox and OneDrive for Business site to the search.</span></span> <span data-ttu-id="e8dd5-107">Nelle versioni future sarà più facile eseguire questa operazione nel Centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="e8dd5-107">In future releases, this will be easier to do in the Security & Compliance Center.</span></span> <span data-ttu-id="e8dd5-108">Fino ad allora, è possibile utilizzare lo script in questo articolo per automatizzare questo processo.</span><span class="sxs-lookup"><span data-stu-id="e8dd5-108">Until then, you can use the script in this article to automate this process.</span></span> <span data-ttu-id="e8dd5-109">Questo script richiede il nome del dominio MySite dell'organizzazione (ad esempio, **contoso** nell'URL), un elenco di indirizzi di posta elettronica utente, il nome della nuova ricerca contenuto e la query di ricerca da `https://contoso-my.sharepoint.com` utilizzare.</span><span class="sxs-lookup"><span data-stu-id="e8dd5-109">This script prompts you for the name of your organization's MySite domain (for example, **contoso** in the URL `https://contoso-my.sharepoint.com`), a list of user email addresses, the name of the new Content Search, and the search query to use.</span></span> <span data-ttu-id="e8dd5-110">Lo script ottiene l'URL di OneDrive for Business per ogni utente nell'elenco e quindi crea e avvia una ricerca contenuto che cerca ogni utente nell'elenco nella cassetta postale e nel sito di OneDrive for Business utilizzando la query di ricerca specificata.</span><span class="sxs-lookup"><span data-stu-id="e8dd5-110">The script gets the OneDrive for Business URL for each user in the list, and then it creates and starts a Content Search that searches the mailbox and OneDrive for Business site for each user in the list, using the search query that you provide.</span></span>
  
## <a name="permissions-and-script-information"></a><span data-ttu-id="e8dd5-111">Autorizzazioni e informazioni sullo script</span><span class="sxs-lookup"><span data-stu-id="e8dd5-111">Permissions and script information</span></span>

- <span data-ttu-id="e8dd5-112">Per eseguire lo script nel passaggio 3, è necessario essere membri del gruppo di ruoli Responsabile eDiscovery nel Centro sicurezza & conformità e un amministratore globale di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="e8dd5-112">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center and a SharePoint Online global administrator to run the script in Step 3.</span></span>

- <span data-ttu-id="e8dd5-113">Assicurarsi di salvare l'elenco degli utenti creati nel passaggio 2 e lo script nel passaggio 3 nella stessa cartella.</span><span class="sxs-lookup"><span data-stu-id="e8dd5-113">Be sure to save the list of users that you create in Step 2 and the script in Step 3 to the same folder.</span></span> <span data-ttu-id="e8dd5-114">In questo modo sarà più semplice eseguire lo script.</span><span class="sxs-lookup"><span data-stu-id="e8dd5-114">That will make it easier to run the script.</span></span>

- <span data-ttu-id="e8dd5-115">Lo script include una gestione minima degli errori.</span><span class="sxs-lookup"><span data-stu-id="e8dd5-115">The script includes minimal error handling.</span></span> <span data-ttu-id="e8dd5-116">Lo scopo principale è cercare rapidamente e facilmente la cassetta postale e il sito di OneDrive for Business di ogni utente.</span><span class="sxs-lookup"><span data-stu-id="e8dd5-116">Its primary purpose is to quickly and easily search the mailbox and OneDrive for Business site of each user.</span></span>

- <span data-ttu-id="e8dd5-p104">Gli script di esempio forniti in questo articolo non sono supportati da alcun programma o servizio standard di supporto Microsoft. Gli script di esempio sono forniti così come sono senza alcun tipo di garanzia. Inoltre Microsoft declina ogni responsabilità su garanzie implicite, senza alcuna limitazione, incluse le garanzie implicite di commerciabilità e/o adeguatezza per uno scopo specifico. Qualsiasi rischio eventuale pervenga, durante l'utilizzo degli script di esempio e della documentazione, si intende a carico dell'utente. In nessun caso Microsoft, i suoi autori o chiunque altro coinvolto nella creazione, produzione o consegna degli script è da ritenersi responsabile per qualsiasi danno eventuale (inclusi, senza limitazione alcuna, danni riguardanti profitti aziendali, interruzione di attività, perdita di informazioni aziendali o altra perdita pecuniaria) derivanti dall'utilizzo o dall'incapacità di utilizzo degli script di esempio e della documentazione, anche nel caso in cui Microsoft sia stata avvisata della possibilità di tali danni.</span><span class="sxs-lookup"><span data-stu-id="e8dd5-p104">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>

## <a name="step-1-install-the-sharepoint-online-management-shell"></a><span data-ttu-id="e8dd5-122">Passaggio 1: Installare SharePoint Online Management Shell</span><span class="sxs-lookup"><span data-stu-id="e8dd5-122">Step 1: Install the SharePoint Online Management Shell</span></span>

<span data-ttu-id="e8dd5-123">Il primo passaggio consiste nell'installare SharePoint Online Management Shell.</span><span class="sxs-lookup"><span data-stu-id="e8dd5-123">The first step is to install the SharePoint Online Management Shell.</span></span> <span data-ttu-id="e8dd5-124">Non è necessario utilizzare la shell in questa procedura, ma è necessario installarla perché contiene i prerequisiti richiesti dallo script eseguito nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="e8dd5-124">You don't have to use the shell in this procedure, but you have to install it because it contains pre-requisites required by the script that you run in Step 3.</span></span> <span data-ttu-id="e8dd5-125">Questi prerequisiti consentono allo script di comunicare con SharePoint Online per ottenere gli URL per i siti di OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="e8dd5-125">These prerequisites allow the script to communicate with SharePoint Online to get the URLs for the OneDrive for Business sites.</span></span>
  
<span data-ttu-id="e8dd5-126">Passare a [Configurare SharePoint Online Management Shell Windows PowerShell ambiente](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) ed eseguire i passaggi 1 e 2 per installare SharePoint Online Management Shell.</span><span class="sxs-lookup"><span data-stu-id="e8dd5-126">Go to [Set up the SharePoint Online Management Shell Windows PowerShell environment](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) and perform Step 1 and Step 2 to install the SharePoint Online Management Shell.</span></span>
  
## <a name="step-2-generate-a-list-of-users"></a><span data-ttu-id="e8dd5-127">Passaggio 2: Generare un elenco di utenti</span><span class="sxs-lookup"><span data-stu-id="e8dd5-127">Step 2: Generate a list of users</span></span>

<span data-ttu-id="e8dd5-128">Lo script nel passaggio 3 creerà una ricerca contenuto per cercare nelle cassette postali e negli account di OneDrive un elenco di utenti.</span><span class="sxs-lookup"><span data-stu-id="e8dd5-128">The script in Step 3 will create a Content Search to search the mailboxes and OneDrive accounts for a list of users.</span></span> <span data-ttu-id="e8dd5-129">È possibile digitare gli indirizzi di posta elettronica in un file di testo oppure eseguire un comando in Windows PowerShell per ottenere un elenco di indirizzi di posta elettronica e salvarli in un file ,che si trova nella stessa cartella in cui verrà salvato lo script nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="e8dd5-129">You can just type the email addresses in a text file, or you can run a command in Windows PowerShell to get a list of email addresses and save them to a file (located in same folder that you'll save the script to in Step 3).</span></span>
  
<span data-ttu-id="e8dd5-130">Ecco un comando [di PowerShell di Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell) che è possibile eseguire per ottenere un elenco di indirizzi di posta elettronica per tutti gli utenti dell'organizzazione e salvarlo in un file di testo denominato `Users.txt` .</span><span class="sxs-lookup"><span data-stu-id="e8dd5-130">Here's an [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) command that you can runt to get a list of email addresses for all users in your organization and save it to a text file named `Users.txt`.</span></span> 
  
```powershell
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > Users.txt
```

<span data-ttu-id="e8dd5-131">Dopo aver eseguito questo comando, assicurarsi di aprire il file e rimuovere l'intestazione contenente il nome della proprietà,  `PrimarySmtpAddress` .</span><span class="sxs-lookup"><span data-stu-id="e8dd5-131">After you run this command, be sure to open the file and remove the header that contains the property name,  `PrimarySmtpAddress`.</span></span> <span data-ttu-id="e8dd5-132">Il file di testo deve contenere solo un elenco di indirizzi di posta elettronica e altro.</span><span class="sxs-lookup"><span data-stu-id="e8dd5-132">The text file should just contain a list of email addresses, and nothing else.</span></span> <span data-ttu-id="e8dd5-133">Verificare che non siano presenti righe vuote prima o dopo l'elenco degli indirizzi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="e8dd5-133">Make sure there are no blank rows before or after the list of email addresses.</span></span>
  
## <a name="step-3-run-the-script-to-create-and-start-the-search"></a><span data-ttu-id="e8dd5-134">Passaggio 3: Eseguire lo script per creare e avviare la ricerca</span><span class="sxs-lookup"><span data-stu-id="e8dd5-134">Step 3: Run the script to create and start the search</span></span>

<span data-ttu-id="e8dd5-135">Quando si esegue lo script in questo passaggio, verranno richieste le informazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="e8dd5-135">When you run the script in this step, it will prompt you for the following information.</span></span> <span data-ttu-id="e8dd5-136">Assicurarsi di avere queste informazioni pronte prima di eseguire lo script.</span><span class="sxs-lookup"><span data-stu-id="e8dd5-136">Be sure to have this information ready before you run the script.</span></span>
  
- <span data-ttu-id="e8dd5-137">**Credenziali** utente: lo script utilizzerà le credenziali per accedere a SharePoint Online per ottenere gli URL di OneDrive for Business e connettersi al Centro sicurezza & e conformità con PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="e8dd5-137">**Your user credentials** - The script will use your credentials to access SharePoint Online to get the OneDrive for Business URLs and to connect to the Security & Compliance Center with remote PowerShell.</span></span> 
    
- <span data-ttu-id="e8dd5-138">**Nome del dominio mySite-** Il dominio MySite è il dominio che contiene tutti i siti di OneDrive for Business nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e8dd5-138">**Name of your MySite domain** - The MySite domain is the domain that contains all the OneDrive for Business sites in your organization.</span></span> <span data-ttu-id="e8dd5-139">Ad esempio, se l'URL del dominio MySite è , è necessario immettere quando lo script richiede il nome del **https://contoso-my.sharepoint.com**  `contoso` dominio MySite.</span><span class="sxs-lookup"><span data-stu-id="e8dd5-139">For example, if the URL for your MySite domain is **https://contoso-my.sharepoint.com**, then you would enter  `contoso` when the script prompts you for the name of your MySite domain.</span></span> 
    
- <span data-ttu-id="e8dd5-140">**Pathname del file di testo del passaggio 2** - Nome del percorso del file di testo creato nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="e8dd5-140">**Pathname of the text file from Step 2** - The pathname of the text file that you created in Step 2.</span></span> <span data-ttu-id="e8dd5-141">Se il file di testo e lo script si trovano nella stessa cartella, immettere il nome del file di testo.</span><span class="sxs-lookup"><span data-stu-id="e8dd5-141">If the text file and the script are located in the same folder, then enter the name of the text file.</span></span> <span data-ttu-id="e8dd5-142">In caso contrario, immettere il percorso completo per il file di testo.</span><span class="sxs-lookup"><span data-stu-id="e8dd5-142">Otherwise, enter the complete pathname for the text file.</span></span> 
    
- <span data-ttu-id="e8dd5-143">**Nome della ricerca contenuto** - Nome della ricerca contenuto che verrà creata dallo script.</span><span class="sxs-lookup"><span data-stu-id="e8dd5-143">**Name of the Content Search** - The name of the Content Search that will be created by the script.</span></span> 
    
- <span data-ttu-id="e8dd5-144">**Query di** ricerca - Viene creata ed eseguita la query di ricerca che verrà utilizzata con la ricerca contenuto.</span><span class="sxs-lookup"><span data-stu-id="e8dd5-144">**Search query** - The search query that will be used with the Content Search is created and run.</span></span> <span data-ttu-id="e8dd5-145">Per ulteriori informazioni sulle query di ricerca, vedere [Query con parole chiave e condizioni di ricerca per Ricerca contenuto.](keyword-queries-and-search-conditions.md)</span><span class="sxs-lookup"><span data-stu-id="e8dd5-145">For more information about search queries, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>


<span data-ttu-id="e8dd5-146">**Per eseguire lo script:**</span><span class="sxs-lookup"><span data-stu-id="e8dd5-146">**To run the script:**</span></span>
    
1. <span data-ttu-id="e8dd5-147">Salvare il testo seguente in un file Windows PowerShell script utilizzando il suffisso del nome di file ps1. ad `SearchEXOOD4B.ps1` esempio.</span><span class="sxs-lookup"><span data-stu-id="e8dd5-147">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `SearchEXOOD4B.ps1`.</span></span> <span data-ttu-id="e8dd5-148">Salvare il file nella stessa cartella in cui è stato salvato l'elenco di utenti nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="e8dd5-148">Save the file to the same folder where you saved the list of users in Step 2.</span></span>
    
  ```powershell
  # This PowerShell script will prompt you for the following information:
  #    * Your user credentials 
  #    * The name of your organization's MySite domain                                              
  #    * The pathname for the text file that contains a list of user email addresses
  #    * The name of the Content Search that will be created
  #    * The search query string
  # The script will then:
  #    * Find the OneDrive for Business site for each user in the text file
  #    * Create and start a Content Search using the above information
  # Get user credentials
  if (!$credentials)
  {
      $credentials = Get-Credential
  }
  # Get the user's MySite domain name.  We use this to create the admin URL and root URL for OneDrive for Business
  $mySiteDomain = Read-Host "What is your organization's MySite domain?  For example,  'contoso' for 'https://contoso-my.sharepoint.com'"
  $AdminUrl = "https://$mySiteDomain-admin.sharepoint.com"
  $mySiteUrlRoot = "https://$mySiteDomain-my.sharepoint.com"
  # Get other required information
  $inputfile = read-host "Enter the file name of the text file that contains the email addresses for the users you want to search"
  $searchName = Read-Host "Enter the name for the new search"
  $searchQuery = Read-Host "Enter the search query you want to use"
  $emailAddresses = Get-Content $inputfile | where {$_ -ne ""}  | foreach{ $_.Trim() }
  # Connect to Office 365
  if (!$s -or !$a)
  {
      $s = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://ps.compliance.protection.outlook.com/powershell-liveid" -Credential $credentials -Authentication Basic -AllowRedirection -SessionOption (New-PSSessionOption -SkipCACheck -SkipCNCheck -SkipRevocationCheck)
      $a = Import-PSSession $s -AllowClobber
      if (!$s)
      {
          Write-Error "Could not create PowerShell session."
          return;
      }
  }
  # Load the SharePoint assemblies from the SharePoint Online Management Shell
  # To install, go to https://go.microsoft.com/fwlink/p/?LinkId=255251
  if (!$SharePointClient -or !$SPRuntime -or !$SPUserProfile)
  {
      $SharePointClient = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client")
      $SPRuntime = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.Runtime")
      $SPUserProfile = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.UserProfiles")
      if (!$SharePointClient)
      {
          Write-Error "SharePoint Online Management Shell isn't installed, please install from: https://go.microsoft.com/fwlink/p/?LinkId=255251 and then run this script again"
          return;
      }
  }
  if (!$spCreds)
  {
      $spCreds = New-Object Microsoft.SharePoint.Client.SharePointOnlineCredentials($credentials.UserName, $credentials.Password)
  }
  # Add the path of the User Profile Service to the SPO admin URL, then create a new webservice proxy to access it
  $proxyaddr = "$AdminUrl/_vti_bin/UserProfileService.asmx?wsdl"
  $UserProfileService= New-WebServiceProxy -Uri $proxyaddr -UseDefaultCredential False
  $UserProfileService.Credentials = $credentials
  # Take care of auth cookies
  $strAuthCookie = $spCreds.GetAuthenticationCookie($AdminUrl)
  $uri = New-Object System.Uri($AdminUrl)
  $container = New-Object System.Net.CookieContainer
  $container.SetCookies($uri, $strAuthCookie)
  $UserProfileService.CookieContainer = $container
  Write-Host "Getting each user's OneDrive for Business URL"
  $urls = @()
  foreach($emailAddress in $emailAddresses)
  {
      try
      {
          $prop = $UserProfileService.GetUserProfileByName("i:0#.f|membership|$emailAddress") | Where-Object { $_.Name -eq "PersonalSpace" } 
          $url = $prop.values[0].value
          $furl = $mySiteUrlRoot + $url
          $urls += $furl
          Write-Host "-$emailAddress => $furl"
      }
      catch
      {
          Write-Warning "Could not locate OneDrive for $emailAddress"
      }
  }
  Write-Host "Creating and starting the search"
  $search = New-ComplianceSearch -Name $searchName -ExchangeLocation $emailAddresses -SharePointLocation $urls -ContentMatchQuery $searchQuery
  # Finally, start the search and then display the status
  if($search)
  {
      Start-ComplianceSearch $search.Name
      Get-ComplianceSearch $search.Name
  }
  
  ```

2. <span data-ttu-id="e8dd5-149">Aprire Windows PowerShell e passare alla cartella in cui è stato salvato lo script e l'elenco degli utenti del passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="e8dd5-149">Open Windows PowerShell and go to the folder where you saved the script and the list of users from Step 2.</span></span>
    
3. <span data-ttu-id="e8dd5-150">Avviare lo script. Per esempio:</span><span class="sxs-lookup"><span data-stu-id="e8dd5-150">Start the script; for example:</span></span>
    
    ```powershell
    .\SearchEXOOD4B.ps1
    ```

4. <span data-ttu-id="e8dd5-151">Quando vengono richieste le credenziali, immettere l'indirizzo di posta elettronica e la password, quindi fare clic su **OK.**</span><span class="sxs-lookup"><span data-stu-id="e8dd5-151">When prompted for your credentials, enter your email address and password, and then click **OK**.</span></span> 
    
5. <span data-ttu-id="e8dd5-152">Quando richiesto dallo script, immettere le informazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="e8dd5-152">Enter following information when prompted by the script.</span></span> <span data-ttu-id="e8dd5-153">Digitare ogni informazione e quindi premere **INVIO.**</span><span class="sxs-lookup"><span data-stu-id="e8dd5-153">Type each piece of information and then press **Enter**.</span></span>
    
    - <span data-ttu-id="e8dd5-154">Nome del dominio MySite.</span><span class="sxs-lookup"><span data-stu-id="e8dd5-154">The name of your MySite domain.</span></span> 
    
    - <span data-ttu-id="e8dd5-155">Nome del percorso del file di testo che contiene l'elenco di utenti.</span><span class="sxs-lookup"><span data-stu-id="e8dd5-155">The pathname of the text file that contains the list of users.</span></span>
    
    - <span data-ttu-id="e8dd5-156">Nome della ricerca contenuto.</span><span class="sxs-lookup"><span data-stu-id="e8dd5-156">A name for the Content Search.</span></span>
    
    - <span data-ttu-id="e8dd5-157">La query di ricerca (lasciare vuoto questo campo per restituire tutti gli elementi nei percorsi del contenuto).</span><span class="sxs-lookup"><span data-stu-id="e8dd5-157">The search query (leave this blank to return all items in the content locations).</span></span>
    
    <span data-ttu-id="e8dd5-158">Lo script ottiene gli URL per ogni sito di OneDrive for Business e quindi crea e avvia la ricerca.</span><span class="sxs-lookup"><span data-stu-id="e8dd5-158">The script gets the URLs for each OneDrive for Business site and then creates and starts the search.</span></span> <span data-ttu-id="e8dd5-159">È possibile eseguire il cmdlet **Get-ComplianceSearch** in PowerShell del Centro sicurezza & conformità per visualizzare  le statistiche e i risultati della ricerca oppure passare alla pagina Ricerca contenuto nel Centro sicurezza & conformità per visualizzare le informazioni sulla ricerca.</span><span class="sxs-lookup"><span data-stu-id="e8dd5-159">You can either run the **Get-ComplianceSearch** cmdlet in Security & Compliance Center PowerShell to display the search statistics and results, or you can go to the **Content search** page in the Security & Compliance Center to view information about the search.</span></span>