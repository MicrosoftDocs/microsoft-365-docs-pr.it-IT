---
title: Utilizzo di uno script per aggiungere gli utenti a un'esenzione in un caso di eDiscovery di base nel centro sicurezza & Compliance
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
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: bad352ff-d5d2-45d8-ac2a-6cb832f10e73
ms.custom: seo-marvel-apr2020
description: Informazioni su come eseguire uno script per aggiungere cassette postali & siti di OneDrive for business a un nuovo blocco associato a un caso di eDiscovery nel centro sicurezza & Compliance.
ms.openlocfilehash: 55ad3c8c8a4a6b77df4c2d3409fee6e5b43cc5f6
ms.sourcegitcommit: 41eb898143286755cd36df9f7e769de641263d73
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2020
ms.locfileid: "45391486"
---
# <a name="use-a-script-to-add-users-to-a-hold-in-a-core-ediscovery-case"></a>Utilizzo di uno script per aggiungere gli utenti a un'esenzione in un caso di eDiscovery di base

Il Centro sicurezza & conformità fornisce i cmdlet di PowerShell che consentono di automatizzare le attività che richiedono tempo per la creazione e la gestione dei casi di eDiscovery. Attualmente, utilizzando lo strumento case di eDiscovery nel centro sicurezza & conformità per inserire un numero elevato di posizioni di contenuto del custode in attesa richiede tempo e preparazione. Ad esempio, prima di creare un'esenzione, è necessario raccogliere l'URL per ogni sito di OneDrive for business che si desidera inserire in attesa. Quindi, per ogni utente che si desidera inserire in attesa, è necessario aggiungere la propria cassetta postale e il proprio sito di OneDrive for business all'esenzione. Nelle versioni future del Centro sicurezza & conformità, questo sarà più facile da fare. Fino a quel momento, è possibile utilizzare lo script in questo articolo per automatizzare il processo.
  
Lo script richiede il nome del dominio del sito personale dell'organizzazione, ad esempio **Contoso** nell'URL https://contoso-my.sharepoint.com) , il nome di un caso di eDiscovery esistente, il nome del nuovo blocco associato al caso, un elenco di indirizzi di posta elettronica degli utenti che si desidera conservare e una query di ricerca da utilizzare se si desidera creare un blocco basato su query. Lo script ottiene quindi l'URL del sito di OneDrive for business per ogni utente nell'elenco, crea la nuova esenzione e quindi aggiunge la cassetta postale e il sito di OneDrive for business per ogni utente nell'elenco all'esenzione. Lo script genera anche file di registro che contengono informazioni sul nuovo blocco.
  
Di seguito vengono illustrati i passaggi per eseguire questa operazione:
  
[Passaggio 1: Installare SharePoint Online Management Shell](#step-1-install-the-sharepoint-online-management-shell)
  
[Passaggio 2: generazione di un elenco di utenti](#step-2-generate-a-list-of-users)
  
[Passaggio 3: eseguire lo script per creare un blocco e aggiungere utenti](#step-3-run-the-script-to-create-a-hold-and-add-users)
  
## <a name="before-you-add-users-to-a-hold"></a>Prima di aggiungere gli utenti a un'esenzione

- Per eseguire lo script nel passaggio 3, è necessario essere membri del gruppo di ruoli eDiscovery Manager nel centro sicurezza & compliance e amministratore di SharePoint Online. Per ulteriori informazioni, vedere [assegnare le autorizzazioni di eDiscovery nel centro sicurezza & conformità di Office 365](assign-ediscovery-permissions.md).

- È possibile aggiungere un numero massimo di cassette postali di 1.000 e 100 siti a un blocco associato a un caso di eDiscovery nel centro sicurezza & conformità. Presupponendo che tutti gli utenti che si desidera inserire in attesa dispongano di un sito di OneDrive for business, è possibile aggiungere un massimo di 100 utenti a un'esenzione utilizzando lo script in questo articolo.

- Assicurarsi di salvare l'elenco di utenti creato nel passaggio 2 e lo script nel passaggio 3 alla stessa cartella. Questo renderà più facile eseguire lo script.

- Lo script aggiunge l'elenco di utenti a un nuovo blocco associato a un caso esistente. Verificare che il caso in cui si desidera associare l'esenzione venga creato prima di eseguire lo script.

- Ogni volta che si esegue lo script, vengono create nuove sessioni di PowerShell di sicurezza & conformità e di PowerShell di SharePoint Online. In questo modo, è possibile utilizzare tutte le sessioni di PowerShell disponibili. Per evitare che ciò accada, è possibile eseguire i seguenti comandi per disconnettere le sessioni di PowerShell attive.

  ```powershell
  Get-PSSession | Remove-PSSession
  ```

   ```powershell
   Disconnect-SPOService
   ```

- Lo script include la gestione degli errori minima. Il suo scopo principale è quello di posizionare rapidamente e facilmente la cassetta postale e il sito di OneDrive for business di ogni utente in attesa.

- Gli script di esempio forniti in questo articolo non sono supportati da alcun programma o servizio standard di supporto Microsoft. Gli script di esempio sono forniti così come sono senza alcun tipo di garanzia. Inoltre Microsoft declina ogni responsabilità su garanzie implicite, senza alcuna limitazione, incluse le garanzie implicite di commerciabilità e/o adeguatezza per uno scopo specifico. Qualsiasi rischio eventuale pervenga, durante l'utilizzo degli script di esempio e della documentazione, si intende a carico dell'utente. In nessun caso Microsoft, i suoi autori o chiunque altro coinvolto nella creazione, produzione o consegna degli script è da ritenersi responsabile per qualsiasi danno eventuale (inclusi, senza limitazione alcuna, danni riguardanti profitti aziendali, interruzione di attività, perdita di informazioni aziendali o altra perdita pecuniaria) derivanti dall'utilizzo o dall'incapacità di utilizzo degli script di esempio e della documentazione, anche nel caso in cui Microsoft sia stata avvisata della possibilità di tali danni.

## <a name="step-1-install-the-sharepoint-online-management-shell"></a>Passaggio 1: Installare SharePoint Online Management Shell

Il primo passaggio consiste nell'installare SharePoint Online Management Shell se non è già installato nel computer locale. Non è necessario utilizzare la shell in questa procedura, ma è necessario installarla perché contiene i prerequisiti richiesti dallo script eseguito nel passaggio 3. Questi prerequisiti consentono allo script di comunicare con SharePoint Online per ottenere gli URL per i siti di OneDrive for business.
  
Andare a [configurare l'ambiente di Windows PowerShell per SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkID=286318) ed eseguire il passaggio 1 e il passaggio 2 per installare SharePoint Online Management Shell nel computer locale. 

## <a name="step-2-generate-a-list-of-users"></a>Passaggio 2: generazione di un elenco di utenti

Lo script nel passaggio 3 creerà un'esenzione associata a un caso di eDiscovery e i siti di aggiunta di cassette postali e OneDrive for business di un elenco di utenti all'esenzione. È possibile digitare gli indirizzi di posta elettronica in un file di testo oppure eseguire un comando in Windows PowerShell per ottenere un elenco di indirizzi di posta elettronica e salvarli in un file (che si trova nella stessa cartella in cui verrà salvato lo script nel passaggio 3).
  
Di seguito è riportato un comando di PowerShell (eseguito utilizzando Remote PowerShell connesso all'organizzazione di Exchange Online) per ottenere un elenco di indirizzi di posta elettronica per tutti gli utenti dell'organizzazione e salvarlo in un file di testo denominato HoldUsers.txt.
  
```powershell
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > HoldUsers.txt
```

Dopo aver eseguito il comando, aprire il file di testo e rimuovere l'intestazione che contiene il nome della proprietà `PrimarySmtpAddress` . Quindi rimuovere tutti gli indirizzi di posta elettronica ad eccezione di quelli per gli utenti che si desidera aggiungere al blocco che verrà creato nel passaggio 3. Verificare che non vi siano righe vuote prima o dopo l'elenco di indirizzi di posta elettronica.
  
## <a name="step-3-run-the-script-to-create-a-hold-and-add-users"></a>Passaggio 3: eseguire lo script per creare un blocco e aggiungere utenti

Quando si esegue lo script in questo passaggio, vengono richieste le informazioni seguenti. Assicurarsi di avere queste informazioni pronte prima di eseguire lo script.
  
- **Credenziali utente:** Lo script utilizzerà le credenziali per connettersi al centro sicurezza & conformità con Remote PowerShell. Utilizzerà anche queste credenziali per accedere a SharePoint Online per ottenere gli URL di OneDrive for business per l'elenco di utenti.

- **Nome del dominio del sito personale:** Il dominio del sito personale è il dominio che contiene tutti i siti di OneDrive for business nell'organizzazione. Ad esempio, se l'URL del dominio del sito personale è **https://contoso-my.sharepoint.com** , è necessario immettere `contoso` quando lo script richiede il nome del dominio del sito personale.

- **Nome del caso:** Nome di un caso esistente. Lo script creerà un nuovo blocco associato a questo caso.

- **Nome dell'esenzione:** Il nome del blocco che lo script creerà e associerà al caso specificato.

- **Query di ricerca per un blocco basato su query:** È possibile creare un blocco basato su query in modo che venga memorizzato solo il contenuto che soddisfa i criteri di ricerca specificati. Per inserire tutto il contenuto in attesa, basta premere **invio** quando viene richiesto di eseguire una query di ricerca.

- **Attivazione o meno dell'esenzione:** È possibile fare in modo che lo script venga attivato nell'esenzione dopo la creazione oppure che lo script possa creare il blocco senza abilitarlo. Se non è stato attivato lo script, è possibile attivarlo in un secondo momento nel centro sicurezza & Compliance oppure eseguendo i comandi di PowerShell seguenti:

  ```powershell
  Set-CaseHoldPolicy -Identity <name of the hold> -Enabled $true
  ```

  ```powershell
  Set-CaseHoldRule -Identity <name of the hold> -Disabled $false
  ```

- **Nome del file di testo con l'elenco di utenti** : il nome del file di testo del passaggio 2 che contiene l'elenco di utenti da aggiungere all'esenzione. Se il file si trova nella stessa cartella dello script, digitare il nome del file, ad esempio HoldUsers.txt. Se il file di testo si trova in un'altra cartella, digitare il percorso completo del file.

Dopo aver raccolto le informazioni che verranno richieste dallo script, il passaggio finale consiste nell'eseguire lo script per creare il nuovo blocco e aggiungervi gli utenti.
  
1. Salvare il testo seguente in un file di script di Windows PowerShell utilizzando un suffisso del nome di file `.ps1` . Ad esempio, `AddUsersToHold.ps1`.

   ```powershell
   #script begin
   " " 
   write-host "***********************************************"
   write-host "   Security & Compliance Center   " -foregroundColor yellow -backgroundcolor darkgreen
   write-host "   eDiscovery cases - Add users to a hold   " -foregroundColor yellow -backgroundcolor darkgreen 
   write-host "***********************************************"
   " " 
   # Get user credentials &amp; Connect to Office 365 SCC, SPO
   $credentials = Get-Credential -Message "Specify your credentials to connect to the Security & Compliance Center and SharePoint Online"
   $s = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://ps.compliance.protection.outlook.com/powershell-liveid" -Credential $credentials -Authentication Basic -AllowRedirection -SessionOption (New-PSSessionOption -SkipCACheck -SkipCNCheck -SkipRevocationCheck)
   $a = Import-PSSession $s -AllowClobber
       if (!$s)
       {
           Write-Error "Couldn't create PowerShell session."
           return;
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
           Write-Error "The SharePoint Online Management Shell isn't installed. Please install it from: https://go.microsoft.com/fwlink/p/?LinkId=255251 and then re-run this script."
           return;
       }
   }
   if (!$spCreds)
   {
       $spCreds = New-Object Microsoft.SharePoint.Client.SharePointOnlineCredentials($credentials.UserName, $credentials.Password)
   }
   # Get the user's MySite domain name. We use this to create the admin URL and root URL for OneDrive for Business
   ""
   $mySiteDomain = Read-Host "Enter the name of your organization's MySite domain. For example, 'contoso' for 'https://contoso-my.sharepoint.com'"
   ""
   # Get other required information
   do{
   $casename = Read-Host "Enter the name of the case"
   $caseexists = (get-compliancecase -identity "$casename" -erroraction SilentlyContinue).isvalid
   if($caseexists -ne 'True')
   {""
   write-host "A case named '$casename' doesn't exist. Please specify the name of an existing case, or create a new case and then re-run the script." -foregroundColor Yellow
   ""}
   }While($caseexists -ne 'True')
   ""
   do{
   $holdName = Read-Host "Enter the name of the new hold"
   $holdexists=(get-caseholdpolicy -identity "$holdname" -case "$casename" -erroraction SilentlyContinue).isvalid
   if($holdexists -eq 'True')
   {""
   write-host "A hold named '$holdname' already exists. Please specify a new hold name." -foregroundColor Yellow
   ""}
   }While($holdexists -eq 'True')
   ""
   $holdQuery = Read-Host "Enter a search query to create a query-based hold, or press Enter to hold all content"
   ""
   $holdstatus = read-host "Do you want the hold enabled after it's created? (Yes/No)"
   do{
   ""
   $inputfile = read-host "Enter the name of the text file that contains the email addresses of the users to add to the hold"
   ""
   $fileexists = test-path -path $inputfile
   if($fileexists -ne 'True'){write-host "$inputfile doesn't exist. Please enter a valid file name." -foregroundcolor Yellow}
   }while($fileexists -ne 'True')
   #Import the list of addresses from the txt file.  Trim any excess spaces and make sure all addresses 
       #in the list are unique.
     [array]$emailAddresses = Get-Content $inputfile -ErrorAction SilentlyContinue | where {$_.trim() -ne ""}  | foreach{ $_.Trim() }
     [int]$dupl = $emailAddresses.count
     [array]$emailAddresses = $emailAddresses | select-object -unique
     $dupl -= $emailAddresses.count
   #Validate email addresses so the hold creation does not run in to an error.
   if($emailaddresses.count -gt 0){
   write-host ($emailAddresses).count "addresses were found in the text file. There were $dupl duplicate entries in the file." -foregroundColor Yellow
   ""
   Write-host "Validating the email addresses. Please wait..." -foregroundColor Yellow
   ""
   $finallist =@()
   foreach($emailAddress in $emailAddresses)
   {
   if((get-recipient $emailaddress -erroraction SilentlyContinue).isvalid -eq 'True')
   {$finallist += $emailaddress}
   else {"Unable to find the user $emailaddress"
   [array]$excludedlist += $emailaddress}
   }
   ""
   #find user's OneDrive Site URL using email address
   Write-Host "Getting the URL for each user's OneDrive for Business site." -foregroundColor Yellow 
   ""
   $AdminUrl = "https://$mySiteDomain-admin.sharepoint.com"
   $mySiteUrlRoot = "https://$mySiteDomain-my.sharepoint.com"
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
   $urls = @()
   foreach($emailAddress in $emailAddresses)
   {
        try{
          $prop = $UserProfileService.GetUserProfileByName("i:0#.f|membership|$emailAddress") | Where-Object { $_.Name -eq "PersonalSpace" }
          $url = $prop.values[0].value
        if($url -ne $null){
          $furl = $mySiteUrlRoot + $url
          $urls += $furl
          Write-Host "- $emailAddress => $furl"
        [array]$ODadded += $furl}
    else{    
          Write-Warning "Couldn't locate OneDrive for $emailAddress"
        [array]$ODExluded += $emailAddress
      }}
    catch { 
    Write-Warning "Could not locate OneDrive for $emailAddress"
    [array]$ODExluded += $emailAddress
    Continue }
   }
   if(($finallist.count -gt 0) -or ($urls.count -gt 0)){
   ""
   Write-Host "Creating the hold named $holdname. Please wait..." -foregroundColor Yellow
   if(($holdstatus -eq "Y") -or ($holdstatus -eq  "y") -or ($holdstatus -eq "yes") -or ($holdstatus -eq "YES")){
   New-CaseHoldPolicy -Name "$holdName" -Case "$casename" -ExchangeLocation $finallist -SharePointLocation $urls -Enabled $True | out-null
   New-CaseHoldRule -Name "$holdName" -Policy "$holdname" -ContentMatchQuery $holdQuery | out-null
   }
   else{
   New-CaseHoldPolicy -Name "$holdName" -Case "$casename" -ExchangeLocation $finallist -SharePointLocation $urls -Enabled $false | out-null
   New-CaseHoldRule -Name "$holdName" -Policy "$holdname" -ContentMatchQuery $holdQuery -disabled $true | out-null
   }
   ""
   }
   else {"No valid locations were identified. Therefore, the hold wasn't created."}
   #write log files (if needed)
   $newhold=Get-CaseHoldPolicy -Identity "$holdname" -Case "$casename" -erroraction SilentlyContinue
   $newholdrule=Get-CaseHoldRule -Identity "$holdName" -erroraction SilentlyContinue
   if(($ODAdded.count -gt 0) -or ($ODExluded.count -gt 0) -or ($finallist.count -gt 0) -or ($excludedlist.count -gt 0) -or ($newhold.isvalid -eq 'True') -or ($newholdrule.isvalid -eq 'True'))
   {
   Write-Host "Generating output files..." -foregroundColor Yellow
   if($ODAdded.count -gt 0){
   "OneDrive Locations" | add-content .\LocationsOnHold.txt
   "==================" | add-content .\LocationsOnHold.txt 
   $newhold.SharePointLocation.name | add-content .\LocationsOnHold.txt}
   if($ODExluded.count -gt 0){ 
   "Users without OneDrive locations" | add-content .\LocationsNotOnHold.txt
   "================================" | add-content .\LocationsNotOnHold.txt
   $ODExluded | add-content .\LocationsNotOnHold.txt}
   if($finallist.count -gt 0){
   " " | add-content .\LocationsOnHold.txt
   "Exchange Locations" | add-content .\LocationsOnHold.txt
   "==================" | add-content .\LocationsOnHold.txt 
   $newhold.ExchangeLocation.name | add-content .\LocationsOnHold.txt}
   if($excludedlist.count -gt 0){
   " "| add-content .\LocationsNotOnHold.txt
   "Mailboxes not added to the hold" | add-content .\LocationsNotOnHold.txt
   "===============================" | add-content .\LocationsNotOnHold.txt
   $excludedlist | add-content .\LocationsNotOnHold.txt}
   $FormatEnumerationLimit=-1
   if($newhold.isvalid -eq 'True'){$newhold|fl >.\GetCaseHoldPolicy.txt}
   if($newholdrule.isvalid -eq 'True'){$newholdrule|Fl >.\GetCaseHoldRule.txt}
   }
   }
   else {"The hold wasn't created because no valid entries were found in the text file."}
   ""
   Write-host "Script complete!" -foregroundColor Yellow
   ""
   #script end
   ```

2. Nel computer locale, aprire Windows PowerShell e passare alla cartella in cui è stato salvato lo script.

3. Eseguire lo script; Per esempio:

   ```powershell
   .\AddUsersToHold.ps1
   ```

4. Immettere le informazioni richieste dallo script.

   Lo script si connette a PowerShell per la sicurezza & Compliance Center e quindi crea la nuova conservazione nel caso di eDiscovery e aggiunge le cassette postali e OneDrive for business per gli utenti nell'elenco. Per visualizzare il nuovo blocco, è possibile accedere al caso nella pagina **eDiscovery** del centro sicurezza & Compliance. 

Al termine dell'esecuzione dello script, vengono creati i file di registro riportati di seguito e vengono salvati nella cartella in cui si trova lo script.
  
- **LocationsOnHold.txt:** Contiene un elenco delle cassette postali e dei siti di OneDrive for business che lo script ha eseguito correttamente.

- **LocationsNotOnHold.txt:** Contiene un elenco delle cassette postali e dei siti di OneDrive for business che lo script non ha posto in attesa. Se un utente dispone di una cassetta postale, ma non di un sito di OneDrive for business, l'utente verrebbe incluso nell'elenco dei siti di OneDrive for business che non sono stati inseriti in attesa.

- **GetCaseHoldPolicy.txt:** Contiene l'output del cmdlet **Get-CaseHoldPolicy** per il nuovo blocco, che lo script ha eseguito dopo la creazione del nuovo blocco. Le informazioni restituite da questo cmdlet includono un elenco di utenti le cui cassette postali e i siti di OneDrive for business sono stati messi in attesa e se il blocco è abilitato o disabilitato. 

- **GetCaseHoldRule.txt:** Contiene l'output del cmdlet **Get-CaseHoldRule** per il nuovo blocco, che lo script ha eseguito dopo la creazione del nuovo blocco. Le informazioni restituite da questo cmdlet includono la query di ricerca se è stato utilizzato lo script per creare un blocco basato su query.
