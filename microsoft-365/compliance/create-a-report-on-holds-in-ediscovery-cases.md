---
title: Creare un report sui casi di blocco in eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/11/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: cca08d26-6fbf-4b2c-b102-b226e4cd7381
ms.custom:
- seo-marvel-apr2020
description: Informazioni su come generare un report in cui siano contenute tutte le esenzioni associate ai casi di eDiscovery.
ms.openlocfilehash: b4387434d57373f9569b6472786e8ad40de85b21
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818035"
---
# <a name="create-a-report-on-holds-in-ediscovery-cases"></a>Creare un report sui casi di blocco in eDiscovery
  
Lo script in questo articolo consente agli amministratori di eDiscovery e ai responsabili di eDiscovery di generare un report contenente informazioni su tutte le esenzioni associate ai casi di eDiscovery nel centro conformità di Office 365 o Microsoft 365. Il report contiene informazioni quali il nome del caso in cui è associata una conservazione, i percorsi di contenuto che sono stati conservati e se il blocco è basato su query. Se sono presenti casi che non dispongono di alcuna esenzione, lo script creerà un ulteriore rapporto con un elenco di casi senza esenzioni.

Per una descrizione dettagliata delle informazioni incluse nel report, vedere la sezione [ulteriori informazioni](#more-information) .
  
## <a name="admin-requirements-and-script-information"></a>Requisiti di amministratore e informazioni sullo script

- Per generare un report su tutti i casi di eDiscovery nell'organizzazione, è necessario essere un amministratore di eDiscovery nell'organizzazione. Se si è un Manager di eDiscovery, il report includerà solo informazioni sui casi in cui è possibile accedere. Per ulteriori informazioni sulle autorizzazioni di eDiscovery, vedere [assign eDiscovery Permissions](assign-ediscovery-permissions.md).
    
- Lo script di questo articolo contiene una gestione degli errori minima. Lo scopo principale consiste nel creare rapidamente report sulle esenzioni associate ai casi di eDiscovery nell'organizzazione.
    
- The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.
    
## <a name="step-1-connect-to-the-security--compliance-center-powershell"></a>Passaggio 1: connettersi al centro sicurezza & Compliance PowerShell

Il primo passaggio consiste nel connettersi a PowerShell per il Centro sicurezza & Compliance per l'organizzazione. Per ottenere istruzioni dettagliate, vedere [Connettersi a PowerShell in Centro sicurezza e conformità](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).
  
Se l'account di Microsoft 365 usa l'autenticazione a più fattori o l'autenticazione federata, non è possibile usare le istruzioni riportate nell'argomento precedente per la connessione a PowerShell in Centro sicurezza e conformità. Per farlo, vedere le istruzioni nell’argomento [Connettersi a PowerShell in Centro sicurezza e conformità mediante l'autenticazione a più fattori](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell).
  
## <a name="step-2-run-the-script-to-report-on-holds-associated-with-ediscovery-cases"></a>Passaggio 2: eseguire lo script per segnalare le esenzioni associate ai casi di eDiscovery

Dopo aver effettuato la connessione a PowerShell per il Centro sicurezza & conformità, il passaggio successivo consiste nel creare ed eseguire lo script che raccoglie informazioni sui casi di eDiscovery nell'organizzazione. 
  
1. Salvare il testo seguente in un file di script di Windows PowerShell utilizzando un suffisso FileName di. ps1. ad esempio, CaseHoldsReport.ps1. 
    
  ```powershell
#script begin
" " 
write-host "***********************************************"
write-host "   Security & Compliance Center   " -foregroundColor yellow -backgroundcolor darkgreen
write-host "        eDiscovery cases - Holds report         " -foregroundColor yellow -backgroundcolor darkgreen 
write-host "***********************************************"
" " 
#prompt users to specify a path to store the output files
$time=get-date
$Path = Read-Host 'Enter a file path to save the report to a .csv file'
$outputpath=$Path+'\'+'CaseHoldsReport'+' '+$time.day+'-'+$time.month+'-'+$time.year+' '+$time.hour+'.'+$time.minute+'.csv'
$noholdsfilepath=$Path+'\'+'CaseswithNoHolds'+' '+$time.day+'-'+$time.month+'-'+$time.year+' '+$time.hour+'.'+$time.minute+'.csv'
#add case details to the csv file
function add-tocasereport{
Param([string]$casename,
[String]$casestatus,
[datetime]$casecreatedtime,
[string]$casemembers,
[datetime]$caseClosedDateTime,
[string]$caseclosedby,
[string]$holdname,
[String]$Holdenabled,
[string]$holdcreatedby,
[string]$holdlastmodifiedby,
[string]$ExchangeLocation,
[string]$sharePointlocation,
[string]$ContentMatchQuery,
[datetime]$holdcreatedtime,
[datetime]$holdchangedtime
)
$addRow = New-Object PSObject 
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case name" -Value $casename
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case status" -Value $casestatus
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case members" -Value $casemembers
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case created time" -Value $casecreatedtime
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case closed time" -Value $caseClosedDateTime
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case closed by" -Value $caseclosedby
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold name" -Value $holdname
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold enabled" -Value $Holdenabled
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold created by" -Value $holdcreatedby
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold last changed by" -Value $holdlastmodifiedby
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Exchange locations" -Value  $ExchangeLocation
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "SharePoint locations" -Value $sharePointlocation
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold query" -Value $ContentMatchQuery
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold created time (UTC)" -Value $holdcreatedtime
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold changed time (UTC)" -Value $holdchangedtime
$allholdreport = $addRow | Select-Object "Case name","Case status","Hold name","Hold enabled","Case members", "Case created time","Case closed time","Case closed by","Exchange locations","SharePoint locations","Hold query","Hold created by","Hold created time (UTC)","Hold last changed by","Hold changed time (UTC)"
$allholdreport | export-csv -path $outputPath -notypeinfo -append -Encoding ascii 
}
#get information on the cases and pass values to the case report function
" "
write-host "Gathering a list of cases and holds..."
" "
$edc =Get-ComplianceCase -ErrorAction SilentlyContinue
foreach($cc in $edc)
{
write-host "Working on case :" $cc.name
if($cc.status -eq 'Closed')
{
$cmembers = ((Get-ComplianceCaseMember -Case $cc.name).windowsLiveID)-join ';'
add-tocasereport -casename $cc.name -casestatus $cc.Status -caseclosedby $cc.closedby -caseClosedDateTime $cc.ClosedDateTime -casemembers $cmembers 
}
else{
$cmembers = ((Get-ComplianceCaseMember -Case $cc.name).windowsLiveID)-join ';'
$policies = Get-CaseHoldPolicy -Case $cc.Name | %{ Get-CaseHoldPolicy $_.Name -Case $_.CaseId -DistributionDetail}
if ($policies -ne $NULL)
{
foreach ($policy in $policies)
{
$rule=Get-CaseHoldRule -Policy $policy.name
add-tocasereport -casename $cc.name -casemembers $cmembers -casestatus $cc.Status -casecreatedtime $cc.CreatedDateTime -holdname $policy.name -holdenabled $policy.enabled -holdcreatedby $policy.CreatedBy -holdlastmodifiedby $policy.LastModifiedBy -ExchangeLocation (($policy.exchangelocation.name)-join ';') -SharePointLocation (($policy.sharePointlocation.name)-join ';') -ContentMatchQuery $rule.ContentMatchQuery -holdcreatedtime $policy.WhenCreatedUTC -holdchangedtime $policy.WhenChangedUTC
}
}
else{
write-host "No hold policies found in case:" $cc.name -foregroundColor 'Yellow'
" "
[string]$cc.name | out-file -filepath $noholdsfilepath -append 
}
}
}

" "
Write-host "Script complete! Report files saved to this folder: '$Path'"
" "
#script end
  ```

2. Nella sessione di Windows PowerShell aperta al passaggio 1 passare alla cartella in cui è stato salvato lo script. 
    
3. Eseguire lo script; Per esempio:

    ```powershell
    .\CaseHoldsReport.ps1
    ```

    Lo script richiederà la creazione di una cartella di destinazione in cui salvare il report. 
    
4. Digitare il nome del percorso completo della cartella in cui salvare il report e quindi premere **invio**.
    
    > [!TIP]
    > Per salvare il report nella stessa cartella in cui si trova lo script, digitare un punto (".") quando viene richiesto di specificare una cartella di destinazione. Per salvare il report in una sottocartella della cartella in cui si trova lo script, digitare il nome della sottocartella. 
  
    Lo script inizia a raccogliere informazioni su tutti i casi di eDiscovery nell'organizzazione. Non accedere al file di report mentre lo script è in esecuzione. Una volta completato lo script, nella sessione di Windows PowerShell viene visualizzato un messaggio di conferma. Dopo aver visualizzato questo messaggio, è possibile accedere al report nella cartella specificata nel passaggio 4. Il nome del file del report è `CaseHoldsReport<DateTimeStamp>.csv` .

    Addtionally, lo script crea anche un rapporto con un elenco di casi che non dispongono di alcuna esenzione. Il nome del file di questo report è `CaseswithNoHolds<DateTimeStamp>.csv` .
    
    Di seguito è riportato un esempio di esecuzione dello script CaseHoldsReport.ps1. 
    
    ![L'output dopo l'esecuzione dello script CaseHoldsReport.ps1](../media/7d312ed5-505e-4ec5-8f06-3571e3524a1a.png)
  
## <a name="more-information"></a>Ulteriori informazioni

Il caso contiene il rapporto creato quando si esegue lo script in questo articolo contiene le informazioni seguenti su ogni blocco. Come spiegato in precedenza, è necessario essere un amministratore di eDiscovery per restituire le informazioni relative a tutte le esenzioni nell'organizzazione. Per ulteriori informazioni sulle esenzioni dei casi, vedere [eDiscovery Cases](ediscovery-cases.md).
  
  - Nome del blocco e nome del caso di eDiscovery a cui è associato il blocco.
    
  - Se il caso eDiscovery è attivo o chiuso.
    
  - Se il blocco è abilitato o disabilitato.
    
  - I membri del caso di eDiscovery a cui è associato il blocco. I membri del caso possono visualizzare o gestire un caso, a seconda delle autorizzazioni di eDiscovery a cui sono stati assegnati.
    
  - Data e ora in cui è stato creato il caso.
    
  - Se un caso è chiuso, la persona che lo ha chiuso e l'ora e la data in cui è stata chiusa.
    
  - Posizioni delle cassette postali di Exchange e dei siti di SharePoint che sono in attesa.
    
  - Se il blocco è basato su query, la sintassi della query.
    
  - La data e l'ora in cui è stato creato il blocco e la persona che lo ha creato.
    
  - Data e ora dell'Ultima modifica dell'esenzione e della persona che lo ha modificato.
