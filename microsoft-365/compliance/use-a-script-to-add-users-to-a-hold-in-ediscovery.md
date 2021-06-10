---
title: Utilizzare uno script per aggiungere utenti a un'esenzione in un caso di eDiscovery di base
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
- SPO_Content
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: bad352ff-d5d2-45d8-ac2a-6cb832f10e73
ms.custom: seo-marvel-apr2020
description: Informazioni su come eseguire uno script per aggiungere cassette postali & OneDrive for Business siti a un nuovo blocco associato a un caso di eDiscovery nel Centro Microsoft 365 conformità.
ms.openlocfilehash: d6e6ff1ca053fd8c729054490e78ef42dc64e829
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909916"
---
# <a name="use-a-script-to-add-users-to-a-hold-in-a-core-ediscovery-case"></a>Utilizzare uno script per aggiungere utenti a un'esenzione in un caso di eDiscovery di base

Security & Compliance Center PowerShell fornisce cmdlet che consentono di automatizzare le attività che richiedono molto tempo relative alla creazione e alla gestione dei casi di eDiscovery. Attualmente, l'utilizzo del caso Core eDiscovery nel Centro sicurezza & conformità per mettere in attesa un numero elevato di posizioni di contenuto depositario richiede tempo e preparazione. Ad esempio, prima di creare un'esenzione, è necessario raccogliere l'URL per ogni sito OneDrive for Business che si desidera mettere in attesa. Quindi, per ogni utente che si desidera mettere in attesa, è necessario aggiungere la propria cassetta postale e il OneDrive for Business sito all'esenzione. È possibile utilizzare lo script in questo articolo per automatizzare questo processo.
  
Lo script richiede il nome del dominio del sito personale dell'organizzazione( ad esempio, nell'URL , il nome di un caso eDiscovery esistente, il nome del nuovo blocco associato al caso, un elenco di indirizzi di posta elettronica degli utenti che si desidera mettere in attesa e una query di ricerca da utilizzare se si desidera creare un blocco basato su `contoso` https://contoso-my.sharepoint.com) query. Lo script ottiene quindi l'URL per il sito di OneDrive for Business per ogni utente nell'elenco, crea il nuovo blocco e quindi aggiunge la cassetta postale e il sito OneDrive for Business per ogni utente nell'elenco all'esenzione. Lo script genera inoltre file di registro contenenti informazioni sulla nuova esenzione.
  
Ecco i passaggi per eseguire questa operazione:
  
[Passaggio 1: Installare SharePoint Online Management Shell](#step-1-install-the-sharepoint-online-management-shell)
  
[Passaggio 2: Generare un elenco di utenti](#step-2-generate-a-list-of-users)
  
[Passaggio 3: Eseguire lo script per creare un'esenzione e aggiungere utenti](#step-3-run-the-script-to-create-a-hold-and-add-users)
  
## <a name="before-you-add-users-to-a-hold"></a>Prima di aggiungere utenti a un'esenzione

- Per eseguire lo script nel passaggio 3, è necessario essere membri del gruppo di ruoli Responsabile eDiscovery nel Centro sicurezza & conformità e un amministratore di SharePoint Online. Per ulteriori informazioni, vedere [Assign eDiscovery permissions in the Office 365 Security & Compliance Center](assign-ediscovery-permissions.md).

- È possibile aggiungere un massimo di 1.000 cassette postali e 100 siti a un blocco associato a un caso di eDiscovery nel Centro sicurezza & conformità. Presupponendo che ogni utente che si desidera mettere in attesa abbia un sito di OneDrive for Business, è possibile aggiungere un massimo di 100 utenti a un'esenzione utilizzando lo script in questo articolo.

- Assicurarsi di salvare l'elenco degli utenti creati nel passaggio 2 e lo script nel passaggio 3 nella stessa cartella. In questo modo sarà più semplice eseguire lo script.

- Lo script aggiunge l'elenco di utenti a una nuova esenzione associata a un caso esistente. Assicurarsi che il caso a cui si desidera associare l'esenzione venga creato prima di eseguire lo script.

- Lo script in questo articolo supporta l'autenticazione moderna quando ci si connette a PowerShell & Centro sicurezza e conformità e SharePoint Online Management Shell. È possibile utilizzare lo script così come è se si è un'Microsoft 365 o un'Microsoft 365 GCC organizzazione. Se si è un'organizzazione di Office 365 Germany, un'organizzazione di Microsoft 365 GCC High o un'organizzazione DoD di Microsoft 365, sarà necessario modificare lo script per eseguirlo correttamente. In particolare, è necessario modificare la riga e utilizzare i parametri `Connect-IPPSSession` *ConnectionUri* e *AzureADAuthorizationEndpointUri* (e i valori appropriati per il tipo di organizzazione) per connettersi a PowerShell del Centro sicurezza & conformità. Per ulteriori informazioni, vedere gli esempi in [Connessione a PowerShell & Centro sicurezza](/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa)e conformità.

- Lo script si disconnette automaticamente da PowerShell & Centro sicurezza e conformità e SharePoint Online Management Shell.

- Lo script include una gestione minima degli errori. Il suo scopo principale è quello di mettere in attesa la cassetta postale e OneDrive for Business sito di ogni utente.

- Gli script di esempio forniti in questo articolo non sono supportati da alcun programma o servizio standard di supporto Microsoft. Gli script di esempio sono forniti così come sono senza alcun tipo di garanzia. Inoltre Microsoft declina ogni responsabilità su garanzie implicite, senza alcuna limitazione, incluse le garanzie implicite di commerciabilità e/o adeguatezza per uno scopo specifico. Qualsiasi rischio eventuale pervenga, durante l'utilizzo degli script di esempio e della documentazione, si intende a carico dell'utente. In nessun caso Microsoft, i suoi autori o chiunque altro coinvolto nella creazione, produzione o consegna degli script è da ritenersi responsabile per qualsiasi danno eventuale (inclusi, senza limitazione alcuna, danni riguardanti profitti aziendali, interruzione di attività, perdita di informazioni aziendali o altra perdita pecuniaria) derivanti dall'utilizzo o dall'incapacità di utilizzo degli script di esempio e della documentazione, anche nel caso in cui Microsoft sia stata avvisata della possibilità di tali danni.

## <a name="step-1-install-the-sharepoint-online-management-shell"></a>Passaggio 1: Installare SharePoint Online Management Shell

Il primo passaggio consiste nell'installare SharePoint Online Management Shell se non è già installato nel computer locale. Non è necessario utilizzare la shell in questa procedura, ma è necessario installarla perché contiene i prerequisiti richiesti dallo script eseguito nel passaggio 3. Questi prerequisiti consentono allo script di comunicare con SharePoint Online per ottenere gli URL per i OneDrive for Business siti.
  
Passare a [Configurare l'ambiente SharePoint Online Management Shell Windows PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) ed eseguire i passaggi 1 e 2 per installare SharePoint Online Management Shell nel computer locale.

## <a name="step-2-generate-a-list-of-users"></a>Passaggio 2: Generare un elenco di utenti

Lo script nel passaggio 3 creerà un blocco associato a un caso di eDiscovery e aggiungerà le cassette postali e i siti OneDrive for Business di un elenco di utenti al blocco. È possibile digitare gli indirizzi di posta elettronica in un file di testo oppure eseguire un comando in Windows PowerShell per ottenere un elenco di indirizzi di posta elettronica e salvarli in un file (che si trova nella stessa cartella in cui verrà salvato lo script nel passaggio 3).
  
Ecco un comando di PowerShell (eseguito tramite PowerShell remoto connesso all'organizzazione di Exchange Online) per ottenere un elenco di indirizzi di posta elettronica per tutti gli utenti dell'organizzazione e salvarlo in un file di testo denominato HoldUsers.txt.
  
```powershell
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > HoldUsers.txt
```

Dopo aver eseguito questo comando, aprire il file di testo e rimuovere l'intestazione contenente il nome della proprietà,  `PrimarySmtpAddress` . Rimuovere quindi tutti gli indirizzi di posta elettronica ad eccezione di quelli per gli utenti che si desidera aggiungere all'esenzione che si creerà nel passaggio 3. Verificare che non siano presenti righe vuote prima o dopo l'elenco degli indirizzi di posta elettronica.
  
## <a name="step-3-run-the-script-to-create-a-hold-and-add-users"></a>Passaggio 3: Eseguire lo script per creare un'esenzione e aggiungere utenti

Quando si esegue lo script in questo passaggio, verranno richieste le informazioni seguenti. Assicurarsi di avere queste informazioni pronte prima di eseguire lo script.
  
- **Credenziali utente:** Lo script userà le credenziali per connettersi al Centro sicurezza & conformità con PowerShell. Userà anche queste credenziali per accedere SharePoint Online per ottenere gli URL OneDrive for Business per l'elenco di utenti.

- **Nome del dominio SharePoint dominio:** Lo script richiede di immettere questo nome in modo che possa connettersi all'SharePoint di amministrazione. Viene inoltre utilizzato il nome di dominio per gli URL OneDrive nell'organizzazione. Ad esempio, se l'URL dell'interfaccia di amministrazione è e l'URL per OneDrive è , immettere quando lo script richiede il nome `https://contoso-admin.sharepoint.com` `https://contoso-my.sharepoint.com` di `contoso` dominio.

- **Nome del caso:** Nome di un caso esistente. Lo script creerà una nuova esenzione associata a questo caso.

- **Nome del blocco:** Nome del blocco che verrà creato e associato al caso specificato.

- **Query di ricerca per un blocco basato su query:** È possibile creare un'esenzione basata su query in modo che solo il contenuto che soddisfa i criteri di ricerca specificati sia messo in attesa. Per mettere tutto il contenuto in attesa, è sufficiente premere **INVIO** quando viene richiesta una query di ricerca.

- **Attivare o meno l'esenzione:** È possibile fare in modo che lo script accerti l'esenzione dopo la creazione oppure che lo script crei l'esenzione senza abilitarla. Se lo script non attiva l'esenzione, è possibile attivarlo in un secondo momento nel Centro sicurezza & conformità o eseguendo i comandi di PowerShell seguenti:

  ```powershell
  Set-CaseHoldPolicy -Identity <name of the hold> -Enabled $true
  ```

  ```powershell
  Set-CaseHoldRule -Identity <name of the hold> -Disabled $false
  ```

- **Nome del file di testo con l'elenco** di utenti - Nome del file di testo del passaggio 2 contenente l'elenco di utenti da aggiungere all'esenzione. Se il file si trova nella stessa cartella dello script, è sufficiente digitare il nome del file, ad esempio HoldUsers.txt. Se il file di testo si trova in un'altra cartella, digitare il percorso completo del file.

Dopo aver raccolto le informazioni richieste nello script, il passaggio finale consiste nell'eseguire lo script per creare il nuovo blocco e aggiungervi utenti.
  
1. Salvare il testo seguente in un Windows PowerShell di script utilizzando il suffisso del nome file `.ps1` . Ad esempio, `AddUsersToHold.ps1`.

```powershell
#script begin
" "
write-host "***********************************************"
write-host "   Security & Compliance Center PowerShell  " -foregroundColor yellow -backgroundcolor darkgreen
write-host "   Core eDiscovery cases - Add users to a hold   " -foregroundColor yellow -backgroundcolor darkgreen 
write-host "***********************************************"
" "
# Connect to SCC PowerShell using modern authentication
if (!$SccSession)
{
  Import-Module ExchangeOnlineManagement
  Connect-IPPSSession
}

# Get the organization's domain name. We use this to create the SharePoint admin URL and root URL for OneDrive for Business.
""
$mySiteDomain = Read-Host "Enter the domain name for your SharePoint organization. We use this name to connect to SharePoint admin center and for the OneDrive URLs in your organization. For example, 'contoso' in 'https://contoso-admin.sharepoint.com' and 'https://contoso-my.sharepoint.com'"
""

# Connect to PnP Online using modern authentication
Import-Module PnP.PowerShell
Connect-PnPOnline -Url https://$mySiteDomain-admin.sharepoint.com -UseWebLogin

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
#Find user's OneDrive account URL using email address
Write-Host "Getting the URL for each user's OneDrive for Business site." -foregroundColor Yellow 
""
$AdminUrl = "https://$mySiteDomain-admin.sharepoint.com"
$mySiteUrlRoot = "https://$mySiteDomain-my.sharepoint.com"
$urls = @()
foreach($emailAddress in $emailAddresses)
{
try
{
$url=Get-PnPUserProfileProperty -Account $emailAddress | Select PersonalUrl
$urls += $url.PersonalUrl
       Write-Host "- $emailAddress => $url"
       [array]$ODadded += $url.PersonalUrl
       }catch { 
 Write-Warning "Could not locate OneDrive for $emailAddress"
 [array]$ODExluded += $emailAddress
 Continue }
}
$urls | FL
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
#Disconnect from SCC PowerShell and PnPOnline

Write-host "Disconnecting from SCC PowerShell and PnP Online" -foregroundColor Yellow
Get-PSSession | Remove-PSSession
Disconnect-PnPOnline

Write-host "Script complete!" -foregroundColor Yellow
""
#script end
```

2. Nel computer locale, aprire Windows PowerShell e passare alla cartella in cui è stato salvato lo script.

3. Eseguire lo script; Per esempio:

   ```powershell
   .\AddUsersToHold.ps1
   ```

4. Immettere le informazioni richieste per lo script.

   Lo script si connette & PowerShell del Centro sicurezza e conformità e quindi crea il nuovo blocco nel caso eDiscovery e aggiunge le cassette postali e OneDrive for Business per gli utenti nell'elenco. È possibile passare al caso nella pagina **eDiscovery** nel Centro sicurezza & conformità per visualizzare il nuovo blocco.

Al termine dell'esecuzione, lo script crea i file di registro seguenti e li salva nella cartella in cui si trova lo script.
  
- **LocationsOnHold.txt:** Contiene un elenco di cassette postali e OneDrive for Business siti che lo script ha messo in attesa correttamente.

- **LocationsNotOnHold.txt:** Contiene un elenco di cassette postali e OneDrive for Business siti che lo script non ha posto in attesa. Se un utente dispone di una cassetta postale, ma non di un sito OneDrive for Business, l'utente verrà incluso nell'elenco dei siti OneDrive for Business che non sono stati messi in attesa.

- **GetCaseHoldPolicy.txt:** Contiene l'output del cmdlet **Get-CaseHoldPolicy** per il nuovo blocco, eseguito dopo la creazione del nuovo blocco. Le informazioni restituite da questo cmdlet includono un elenco di utenti le cui cassette postali e siti di OneDrive for Business sono stati messi in attesa e se il blocco è abilitato o disabilitato. 

- **GetCaseHoldRule.txt:** Contiene l'output del cmdlet **Get-CaseHoldRule** per il nuovo blocco, eseguito dopo la creazione del nuovo blocco. Le informazioni restituite da questo cmdlet includono la query di ricerca se è stato utilizzato lo script per creare un'esenzione basata su query.