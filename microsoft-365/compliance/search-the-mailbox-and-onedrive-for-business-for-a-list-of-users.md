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
# <a name="use-content-search-to-search-the-mailbox-and-onedrive-for-business-site-for-a-list-of-users"></a>Usare Ricerca contenuto per cercare un elenco di utenti nella cassetta postale e nel sito di OneDrive for Business

Il Centro sicurezza & conformità offre una serie di Windows PowerShell che consentono di automatizzare le attività correlate a eDiscovery che richiedono molto tempo. Attualmente, la creazione di una ricerca di contenuto nel Centro sicurezza & conformità per la ricerca in un numero elevato di posizioni di contenuto responsabile richiede tempo e preparazione. Prima di creare una ricerca, è necessario raccogliere l'URL per ogni sito di OneDrive for Business e quindi aggiungere ogni cassetta postale e il sito di OneDrive for Business alla ricerca. Nelle versioni future sarà più facile eseguire questa operazione nel Centro sicurezza & conformità. Fino ad allora, è possibile utilizzare lo script in questo articolo per automatizzare questo processo. Questo script richiede il nome del dominio MySite dell'organizzazione (ad esempio, **contoso** nell'URL), un elenco di indirizzi di posta elettronica utente, il nome della nuova ricerca contenuto e la query di ricerca da `https://contoso-my.sharepoint.com` utilizzare. Lo script ottiene l'URL di OneDrive for Business per ogni utente nell'elenco e quindi crea e avvia una ricerca contenuto che cerca ogni utente nell'elenco nella cassetta postale e nel sito di OneDrive for Business utilizzando la query di ricerca specificata.
  
## <a name="permissions-and-script-information"></a>Autorizzazioni e informazioni sullo script

- Per eseguire lo script nel passaggio 3, è necessario essere membri del gruppo di ruoli Responsabile eDiscovery nel Centro sicurezza & conformità e un amministratore globale di SharePoint Online.

- Assicurarsi di salvare l'elenco degli utenti creati nel passaggio 2 e lo script nel passaggio 3 nella stessa cartella. In questo modo sarà più semplice eseguire lo script.

- Lo script include una gestione minima degli errori. Lo scopo principale è cercare rapidamente e facilmente la cassetta postale e il sito di OneDrive for Business di ogni utente.

- Gli script di esempio forniti in questo articolo non sono supportati da alcun programma o servizio standard di supporto Microsoft. Gli script di esempio sono forniti così come sono senza alcun tipo di garanzia. Inoltre Microsoft declina ogni responsabilità su garanzie implicite, senza alcuna limitazione, incluse le garanzie implicite di commerciabilità e/o adeguatezza per uno scopo specifico. Qualsiasi rischio eventuale pervenga, durante l'utilizzo degli script di esempio e della documentazione, si intende a carico dell'utente. In nessun caso Microsoft, i suoi autori o chiunque altro coinvolto nella creazione, produzione o consegna degli script è da ritenersi responsabile per qualsiasi danno eventuale (inclusi, senza limitazione alcuna, danni riguardanti profitti aziendali, interruzione di attività, perdita di informazioni aziendali o altra perdita pecuniaria) derivanti dall'utilizzo o dall'incapacità di utilizzo degli script di esempio e della documentazione, anche nel caso in cui Microsoft sia stata avvisata della possibilità di tali danni.

## <a name="step-1-install-the-sharepoint-online-management-shell"></a>Passaggio 1: Installare SharePoint Online Management Shell

Il primo passaggio consiste nell'installare SharePoint Online Management Shell. Non è necessario utilizzare la shell in questa procedura, ma è necessario installarla perché contiene i prerequisiti richiesti dallo script eseguito nel passaggio 3. Questi prerequisiti consentono allo script di comunicare con SharePoint Online per ottenere gli URL per i siti di OneDrive for Business.
  
Passare a [Configurare SharePoint Online Management Shell Windows PowerShell ambiente](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) ed eseguire i passaggi 1 e 2 per installare SharePoint Online Management Shell.
  
## <a name="step-2-generate-a-list-of-users"></a>Passaggio 2: Generare un elenco di utenti

Lo script nel passaggio 3 creerà una ricerca contenuto per cercare nelle cassette postali e negli account di OneDrive un elenco di utenti. È possibile digitare gli indirizzi di posta elettronica in un file di testo oppure eseguire un comando in Windows PowerShell per ottenere un elenco di indirizzi di posta elettronica e salvarli in un file ,che si trova nella stessa cartella in cui verrà salvato lo script nel passaggio 3.
  
Ecco un comando [di PowerShell di Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell) che è possibile eseguire per ottenere un elenco di indirizzi di posta elettronica per tutti gli utenti dell'organizzazione e salvarlo in un file di testo denominato `Users.txt` . 
  
```powershell
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > Users.txt
```

Dopo aver eseguito questo comando, assicurarsi di aprire il file e rimuovere l'intestazione contenente il nome della proprietà,  `PrimarySmtpAddress` . Il file di testo deve contenere solo un elenco di indirizzi di posta elettronica e altro. Verificare che non siano presenti righe vuote prima o dopo l'elenco degli indirizzi di posta elettronica.
  
## <a name="step-3-run-the-script-to-create-and-start-the-search"></a>Passaggio 3: Eseguire lo script per creare e avviare la ricerca

Quando si esegue lo script in questo passaggio, verranno richieste le informazioni seguenti. Assicurarsi di avere queste informazioni pronte prima di eseguire lo script.
  
- **Credenziali** utente: lo script utilizzerà le credenziali per accedere a SharePoint Online per ottenere gli URL di OneDrive for Business e connettersi al Centro sicurezza & e conformità con PowerShell remoto. 
    
- **Nome del dominio mySite-** Il dominio MySite è il dominio che contiene tutti i siti di OneDrive for Business nell'organizzazione. Ad esempio, se l'URL del dominio MySite è , è necessario immettere quando lo script richiede il nome del **https://contoso-my.sharepoint.com**  `contoso` dominio MySite. 
    
- **Pathname del file di testo del passaggio 2** - Nome del percorso del file di testo creato nel passaggio 2. Se il file di testo e lo script si trovano nella stessa cartella, immettere il nome del file di testo. In caso contrario, immettere il percorso completo per il file di testo. 
    
- **Nome della ricerca contenuto** - Nome della ricerca contenuto che verrà creata dallo script. 
    
- **Query di** ricerca - Viene creata ed eseguita la query di ricerca che verrà utilizzata con la ricerca contenuto. Per ulteriori informazioni sulle query di ricerca, vedere [Query con parole chiave e condizioni di ricerca per Ricerca contenuto.](keyword-queries-and-search-conditions.md)


**Per eseguire lo script:**
    
1. Salvare il testo seguente in un file Windows PowerShell script utilizzando il suffisso del nome di file ps1. ad `SearchEXOOD4B.ps1` esempio. Salvare il file nella stessa cartella in cui è stato salvato l'elenco di utenti nel passaggio 2.
    
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

2. Aprire Windows PowerShell e passare alla cartella in cui è stato salvato lo script e l'elenco degli utenti del passaggio 2.
    
3. Avviare lo script. Per esempio:
    
    ```powershell
    .\SearchEXOOD4B.ps1
    ```

4. Quando vengono richieste le credenziali, immettere l'indirizzo di posta elettronica e la password, quindi fare clic su **OK.** 
    
5. Quando richiesto dallo script, immettere le informazioni seguenti. Digitare ogni informazione e quindi premere **INVIO.**
    
    - Nome del dominio MySite. 
    
    - Nome del percorso del file di testo che contiene l'elenco di utenti.
    
    - Nome della ricerca contenuto.
    
    - La query di ricerca (lasciare vuoto questo campo per restituire tutti gli elementi nei percorsi del contenuto).
    
    Lo script ottiene gli URL per ogni sito di OneDrive for Business e quindi crea e avvia la ricerca. È possibile eseguire il cmdlet **Get-ComplianceSearch** in PowerShell del Centro sicurezza & conformità per visualizzare  le statistiche e i risultati della ricerca oppure passare alla pagina Ricerca contenuto nel Centro sicurezza & conformità per visualizzare le informazioni sulla ricerca.