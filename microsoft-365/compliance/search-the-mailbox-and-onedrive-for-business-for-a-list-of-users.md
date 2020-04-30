---
title: Usare Ricerca contenuto per cercare un elenco di utenti nella cassetta postale e nel sito di OneDrive for Business
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/3/2017
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
ms.assetid: 5f4f8206-2d6a-4cb2-bbc6-7a0698703cc0
description: Utilizzare la ricerca contenuto e lo script in questo articolo per eseguire ricerche nelle cassette postali e nei siti di OneDrive for business per un gruppo di utenti.
ms.openlocfilehash: 31dfa2057eff27ed1d2579cc541361858a11c7ce
ms.sourcegitcommit: 60c1932dcca249355ef7134df0ceb0e57757dc81
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/29/2020
ms.locfileid: "43943275"
---
# <a name="use-content-search-to-search-the-mailbox-and-onedrive-for-business-site-for-a-list-of-users"></a>Usare Ricerca contenuto per cercare un elenco di utenti nella cassetta postale e nel sito di OneDrive for Business

Il Centro sicurezza & conformità fornisce una serie di cmdlet di Windows PowerShell che consentono di automatizzare le attività relative a eDiscovery. Attualmente, la creazione di una ricerca di contenuto nel centro sicurezza & conformità per la ricerca di un numero elevato di posizioni di contenuto del custode richiede tempo e preparazione. Prima di creare una ricerca, è necessario raccogliere l'URL per ogni sito di OneDrive for business e quindi aggiungere ogni cassetta postale e sito di OneDrive for business alla ricerca. Nelle versioni future, questo sarà più facile da fare nel centro sicurezza & Compliance. Fino a quel momento, è possibile utilizzare lo script in questo articolo per automatizzare il processo. Questo script richiede l'utilizzo del nome del dominio del sito Web dell'organizzazione, ad esempio **Contoso** nell'URL https://contoso-my.sharepoint.com), un elenco di indirizzi di posta elettronica utente, il nome della nuova ricerca contenuto e la query di ricerca da utilizzare. Lo script ottiene l'URL di OneDrive for business per ogni utente nell'elenco e quindi crea e avvia una ricerca di contenuto che cerca nella cassetta postale e nel sito di OneDrive for business ogni utente nell'elenco, utilizzando la query di ricerca fornita. 
  
## <a name="before-you-begin"></a>Informazioni preliminari

- È necessario essere membri del gruppo di ruoli eDiscovery Manager nel centro sicurezza & compliance e un amministratore globale di SharePoint Online per eseguire lo script nel passaggio 3.
    
- Assicurarsi di salvare l'elenco di utenti creato nel passaggio 2 e lo script nel passaggio 3 alla stessa cartella. Questo renderà più facile eseguire lo script.
    
- Lo script include la gestione degli errori minima. Lo scopo principale è la ricerca rapida e semplice della cassetta postale e del sito di OneDrive for business di ogni utente.
    
- Gli script di esempio forniti in questo argomento non sono supportati in alcun servizio o programma di supporto Microsoft standard. Gli script di esempio sono forniti così come sono senza alcun tipo di garanzia. Microsoft nega inoltre tutte le garanzie di[https://go.microsoft.com/fwlink/p/?LinkId=517283](https://go.microsoft.com/fwlink/p/?LinkId=517283)mplied, incluse, a titolo esemplificativo, le garanzie implicite di commerciabilità o di idoneità per uno scopo specifico. Qualsiasi rischio eventuale pervenga, durante l'utilizzo degli script di esempio e della documentazione, si intende a carico dell'utente. In nessun caso Microsoft, i suoi autori o chiunque altro coinvolto nella creazione, produzione o consegna degli script è da ritenersi responsabile per qualsiasi danno eventuale (inclusi, senza limitazione alcuna, danni riguardanti profitti aziendali, interruzione di attività, perdita di informazioni aziendali o altra perdita pecuniaria) derivanti dall'utilizzo o dall'incapacità di utilizzo degli script di esempio e della documentazione, anche nel caso in cui Microsoft sia stata avvisata della possibilità di tali danni.
    
## <a name="step-1-install-the-sharepoint-online-management-shell"></a>Passaggio 1: Installare SharePoint Online Management Shell

Il primo passaggio consiste nell'installare SharePoint Online Management Shell. Non è necessario utilizzare la shell in questa procedura, ma è necessario installarla perché contiene i prerequisiti richiesti dallo script eseguito nel passaggio 3. Questi prerequisiti consentono allo script di comunicare con SharePoint Online per ottenere gli URL per i siti di OneDrive for business.
  
Andare a [configurare l'ambiente di Windows PowerShell per SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkID=286318) ed eseguire il passaggio 1 e il passaggio 2 per installare SharePoint Online Management Shell.
  
## <a name="step-2-generate-a-list-of-users"></a>Passaggio 2: generazione di un elenco di utenti

Lo script nel passaggio 3 creerà una ricerca di contenuto per cercare le cassette postali e gli account di OneDrive per un elenco di utenti. È possibile digitare gli indirizzi di posta elettronica in un file di testo oppure eseguire un comando in Windows PowerShell per ottenere un elenco di indirizzi di posta elettronica e salvarli in un file (che si trova nella stessa cartella in cui verrà salvato lo script nel passaggio 3).
  
Di seguito è riportato un comando di [PowerShell di Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=517283) che può essere utilizzato per ottenere un elenco di indirizzi di posta elettronica per tutti gli utenti dell'organizzazione e salvarlo in un file di testo denominato `Users.txt`. 
  
```powershell
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > Users.txt
```

Dopo aver eseguito il comando, accertarsi di aprire il file e rimuovere l'intestazione che contiene il nome della proprietà `PrimarySmtpAddress`. Il file di testo deve contenere solo un elenco di indirizzi di posta elettronica e nient'altro. Verificare che non vi siano righe vuote prima o dopo l'elenco di indirizzi di posta elettronica.
  
## <a name="step-3-run-the-script-to-create-and-start-the-search"></a>Passaggio 3: eseguire lo script per creare e avviare la ricerca

Quando si esegue lo script in questo passaggio, vengono richieste le informazioni seguenti. Assicurarsi di avere queste informazioni pronte prima di eseguire lo script.
  
- **Credenziali utente** : lo script utilizzerà le credenziali per accedere a SharePoint Online per ottenere gli URL di OneDrive for business e connettersi al centro sicurezza & conformità con Remote PowerShell. 
    
- **Nome del dominio del sito Web** : il dominio del sito Web è il dominio che contiene tutti i siti di OneDrive for business nell'organizzazione. Ad esempio, se l'URL del dominio del sito Web è **https://contoso-my.sharepoint.com**, è necessario immetterlo `contoso` quando lo script richiede il nome del dominio di siti personali. 
    
- **Percorso del file di testo del passaggio 2** : il percorso del file di testo creato nel passaggio 2. Se il file di testo e lo script si trovano nella stessa cartella, immettere il nome del file di testo. In caso contrario, immettere il percorso completo per il file di testo. 
    
- **Nome della ricerca di contenuto** -il nome della ricerca di contenuto che verrà creata dallo script. 
    
- **Query di ricerca** -la query di ricerca che verrà utilizzata con la ricerca di contenuto viene creata ed eseguita. Per ulteriori informazioni sulle query di ricerca, vedere [keyword query and Search Conditions for content search](keyword-queries-and-search-conditions.md).


**Per eseguire lo script:**
    
1. Salvare il testo seguente in un file di script di Windows PowerShell utilizzando un suffisso FileName di. ps1. ad esempio, `SearchEXOOD4B.ps1`. Salvare il file nella stessa cartella in cui è stato salvato l'elenco di utenti nel passaggio 2.
    
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

2. Aprire Windows PowerShell e passare alla cartella in cui è stato salvato lo script e l'elenco di utenti del passaggio 2.
    
3. Avviare lo script; Per esempio:
    
    ```powershell
    .\SearchEXOOD4B.ps1
    ```

4. Quando vengono richieste le credenziali, immettere l'indirizzo di posta elettronica e la password, quindi fare clic su **OK**. 
    
5. Immettere le informazioni seguenti quando richiesto dallo script. Digitare ogni informazione e quindi premere **invio**.
    
    - Nome del dominio di siti personali. 
    
    - Il percorso del file di testo che contiene l'elenco di utenti.
    
    - Un nome per la ricerca di contenuto.
    
    - La query di ricerca (lasciare vuoto questo elemento per restituire tutti gli elementi nei percorsi di contenuto).
    
    Lo script consente di recuperare gli URL per ogni sito di OneDrive for business e quindi di creare e avviare la ricerca. È possibile eseguire il cmdlet **Get-ComplianceSearch** in PowerShell per la sicurezza & Compliance Center per visualizzare le statistiche di ricerca e i risultati oppure andare alla pagina **Ricerca contenuto** nel centro sicurezza & conformità per visualizzare le informazioni sulla ricerca. 
