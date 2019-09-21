---
title: Creare un report su esenzioni nei casi di eDiscovery in Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/11/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid: MOE150
ms.assetid: cca08d26-6fbf-4b2c-b102-b226e4cd7381
description: Utilizzare lo script in questo articolo per generare un report contenente informazioni su tutte le esenzioni associate ai casi di eDiscovery nel centro conformità in Office 365 o Microsoft 365.
ms.openlocfilehash: 7118b62dcd42413309e33c45e80516c8822faeff
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37083120"
---
# <a name="create-a-report-on-holds-in-ediscovery-cases-in-office-365"></a><span data-ttu-id="7f51f-103">Creare un report su esenzioni nei casi di eDiscovery in Office 365</span><span class="sxs-lookup"><span data-stu-id="7f51f-103">Create a report on holds in eDiscovery cases in Office 365</span></span>
  
<span data-ttu-id="7f51f-104">Lo script in questo articolo consente agli amministratori di eDiscovery e ai responsabili di eDiscovery di generare un report contenente informazioni su tutte le esenzioni associate ai casi di eDiscovery nel centro conformità di Office 365 o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7f51f-104">The script in this article lets eDiscovery administrators and eDiscovery managers generate a report that contains information about all holds that are associated with eDiscovery cases in the the compliance center in Office 365 or Microsoft 365.</span></span> <span data-ttu-id="7f51f-105">Il report contiene informazioni quali il nome del caso in cui è associata una conservazione, i percorsi di contenuto che sono stati conservati e se il blocco è basato su query.</span><span class="sxs-lookup"><span data-stu-id="7f51f-105">The report contains information such as the name of the case a hold is associated with, the content locations that are placed on hold, and whether the hold is query-based.</span></span> <span data-ttu-id="7f51f-106">Se sono presenti casi che non dispongono di alcuna esenzione, lo script creerà un ulteriore rapporto con un elenco di casi senza esenzioni.</span><span class="sxs-lookup"><span data-stu-id="7f51f-106">If there are cases that don't have any holds, the script will create an additional report with a list of cases without holds.</span></span>

<span data-ttu-id="7f51f-107">Per una descrizione dettagliata delle informazioni incluse nel report, vedere la sezione [ulteriori informazioni](#more-information) .</span><span class="sxs-lookup"><span data-stu-id="7f51f-107">See the [More information](#more-information) section for a detailed description of the information included in the report.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="7f51f-108">Informazioni preliminari</span><span class="sxs-lookup"><span data-stu-id="7f51f-108">Before you begin</span></span>

- <span data-ttu-id="7f51f-109">Per generare un report su tutti i casi di eDiscovery nell'organizzazione, è necessario essere un amministratore di eDiscovery nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7f51f-109">To generate a report on all eDiscovery cases in your organization, you have to be an eDiscovery Administrator in your organization.</span></span> <span data-ttu-id="7f51f-110">Se si è un Manager di eDiscovery, il report includerà solo informazioni sui casi in cui è possibile accedere.</span><span class="sxs-lookup"><span data-stu-id="7f51f-110">If you are an eDiscovery Manager, the report will only include information about the cases that you can access.</span></span> <span data-ttu-id="7f51f-111">Per ulteriori informazioni sulle autorizzazioni di eDiscovery, vedere [assign eDiscovery Permissions](assign-ediscovery-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="7f51f-111">For more information about eDiscovery permissions, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>
    
- <span data-ttu-id="7f51f-112">Lo script di questo articolo contiene una gestione degli errori minima.</span><span class="sxs-lookup"><span data-stu-id="7f51f-112">The script in this article has minimal error handling.</span></span> <span data-ttu-id="7f51f-113">Lo scopo principale consiste nel creare rapidamente report sulle esenzioni associate ai casi di eDiscovery nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7f51f-113">The primary purpose is to quickly create report about the holds that are associated with the eDiscovery cases in your organization.</span></span>
    
- <span data-ttu-id="7f51f-p104">Gli script di esempio forniti in questo articolo non sono supportati da alcun programma o servizio standard di supporto Microsoft. Gli script di esempio sono forniti così come sono senza alcun tipo di garanzia. Inoltre Microsoft declina ogni responsabilità su garanzie implicite, senza alcuna limitazione, incluse le garanzie implicite di commerciabilità e/o adeguatezza per uno scopo specifico. Qualsiasi rischio eventuale pervenga, durante l'utilizzo degli script di esempio e della documentazione, si intende a carico dell'utente. In nessun caso Microsoft, i suoi autori o chiunque altro coinvolto nella creazione, produzione o consegna degli script è da ritenersi responsabile per qualsiasi danno eventuale (inclusi, senza limitazione alcuna, danni riguardanti profitti aziendali, interruzione di attività, perdita di informazioni aziendali o altra perdita pecuniaria) derivanti dall'utilizzo o dall'incapacità di utilizzo degli script di esempio e della documentazione, anche nel caso in cui Microsoft sia stata avvisata della possibilità di tali danni.</span><span class="sxs-lookup"><span data-stu-id="7f51f-p104">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
    
## <a name="step-1-connect-to-the-security--compliance-center-powershell"></a><span data-ttu-id="7f51f-119">Passaggio 1: connettersi al centro sicurezza & Compliance PowerShell</span><span class="sxs-lookup"><span data-stu-id="7f51f-119">Step 1: Connect to the Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="7f51f-120">Il primo passaggio consiste nel connettersi al centro sicurezza & Compliance per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7f51f-120">The first step is to connect to the Security & Compliance Center for your organization.</span></span>
  
1. <span data-ttu-id="7f51f-121">Salvare il testo seguente in un file di script di Windows PowerShell utilizzando un suffisso FileName di. ps1. ad esempio, `ConnectSCC.ps1`.</span><span class="sxs-lookup"><span data-stu-id="7f51f-121">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `ConnectSCC.ps1`.</span></span> 
    
      ```
      # Get login credentials 
      $UserCredential = Get-Credential 
      $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection 
      Import-PSSession $Session -AllowClobber -DisableNameChecking 
      $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Security & Compliance Center)" 
    ```

2. <span data-ttu-id="7f51f-122">Nel computer locale, aprire Windows PowerShell e passare alla cartella in cui è stato salvato lo script.</span><span class="sxs-lookup"><span data-stu-id="7f51f-122">On your local computer, open Windows PowerShell and go to the folder where you saved the script.</span></span> 
    
3. <span data-ttu-id="7f51f-123">Eseguire lo script; Per esempio:</span><span class="sxs-lookup"><span data-stu-id="7f51f-123">Run the script; for example:</span></span>

    ```
    .\ConnectSCC.ps1
    ```
   
4. <span data-ttu-id="7f51f-124">Quando vengono richieste le credenziali, immettere l'indirizzo di posta elettronica e la password, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="7f51f-124">When prompted for your credentials, enter your email address and password, and then click **OK**.</span></span> 
  
## <a name="step-2-run-the-script-to-report-on-holds-associated-with-ediscovery-cases"></a><span data-ttu-id="7f51f-125">Passaggio 2: eseguire lo script per segnalare le esenzioni associate ai casi di eDiscovery</span><span class="sxs-lookup"><span data-stu-id="7f51f-125">Step 2: Run the script to report on holds associated with eDiscovery cases</span></span>

<span data-ttu-id="7f51f-126">Dopo aver effettuato la connessione a PowerShell per il Centro sicurezza & conformità, il passaggio successivo consiste nel creare ed eseguire lo script che raccoglie informazioni sui casi di eDiscovery nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7f51f-126">After you've connected to Security & Compliance Center PowerShell, the next step is to create and run the script that collects information about the eDiscovery cases in your organization.</span></span> 
  
1. <span data-ttu-id="7f51f-127">Salvare il testo seguente in un file di script di Windows PowerShell utilizzando un suffisso FileName di. ps1. ad esempio, CaseHoldsReport. ps1.</span><span class="sxs-lookup"><span data-stu-id="7f51f-127">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, CaseHoldsReport.ps1.</span></span> 
    
  ```
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

2. <span data-ttu-id="7f51f-128">Nella sessione di Windows PowerShell aperta al passaggio 1 passare alla cartella in cui è stato salvato lo script.</span><span class="sxs-lookup"><span data-stu-id="7f51f-128">In the Windows PowerShell session that opened in Step 1, go to the folder where you saved the script.</span></span> 
    
3. <span data-ttu-id="7f51f-129">Eseguire lo script; Per esempio:</span><span class="sxs-lookup"><span data-stu-id="7f51f-129">Run the script; for example:</span></span>

    ```
    .\CaseHoldsReport.ps1
    ```

    <span data-ttu-id="7f51f-130">Lo script richiederà la creazione di una cartella di destinazione in cui salvare il report.</span><span class="sxs-lookup"><span data-stu-id="7f51f-130">The script will prompt for a target folder to save the report to.</span></span> 
    
4. <span data-ttu-id="7f51f-131">Digitare il nome del percorso completo della cartella in cui salvare il report e quindi premere **invio**.</span><span class="sxs-lookup"><span data-stu-id="7f51f-131">Type the full path name of the folder to save the report to, and then press **Enter**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="7f51f-132">Per salvare il report nella stessa cartella in cui si trova lo script, digitare un punto (".") quando viene richiesto di specificare una cartella di destinazione.</span><span class="sxs-lookup"><span data-stu-id="7f51f-132">To save the report in the same folder that the script is located in, type a period (".") when prompted for a target folder.</span></span> <span data-ttu-id="7f51f-133">Per salvare il report in una sottocartella della cartella in cui si trova lo script, digitare il nome della sottocartella.</span><span class="sxs-lookup"><span data-stu-id="7f51f-133">To save the report in a subfolder in the folder where the script is located, just type the name of the subfolder.</span></span> 
  
    <span data-ttu-id="7f51f-134">Lo script inizia a raccogliere informazioni su tutti i casi di eDiscovery nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7f51f-134">The script starts to collect information about all the eDiscovery cases in your organization.</span></span> <span data-ttu-id="7f51f-135">Non accedere al file di report mentre lo script è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="7f51f-135">Don't access the report file while the script is running.</span></span> <span data-ttu-id="7f51f-136">Una volta completato lo script, nella sessione di Windows PowerShell viene visualizzato un messaggio di conferma.</span><span class="sxs-lookup"><span data-stu-id="7f51f-136">After the script is complete, a confirmation message is displayed in the Windows PowerShell session.</span></span> <span data-ttu-id="7f51f-137">Dopo aver visualizzato questo messaggio, è possibile accedere al report nella cartella specificata nel passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="7f51f-137">After this message is displayed, you can access the report in the folder that you specified in Step 4.</span></span> <span data-ttu-id="7f51f-138">Il nome del file del report è `CaseHoldsReport<DateTimeStamp>.csv`.</span><span class="sxs-lookup"><span data-stu-id="7f51f-138">The file name for the report is `CaseHoldsReport<DateTimeStamp>.csv`.</span></span>

    <span data-ttu-id="7f51f-139">Addtionally, lo script crea anche un rapporto con un elenco di casi che non dispongono di alcuna esenzione.</span><span class="sxs-lookup"><span data-stu-id="7f51f-139">Addtionally, the script also creates a report with a list of cases that don't have any holds.</span></span> <span data-ttu-id="7f51f-140">Il nome del file di questo report `CaseswithNoHolds<DateTimeStamp>.csv`è.</span><span class="sxs-lookup"><span data-stu-id="7f51f-140">The file name for this report is `CaseswithNoHolds<DateTimeStamp>.csv`.</span></span>
    
    <span data-ttu-id="7f51f-141">Di seguito è riportato un esempio di esecuzione dello script CaseHoldsReport. ps1.</span><span class="sxs-lookup"><span data-stu-id="7f51f-141">Here's an example of running the CaseHoldsReport.ps1 script.</span></span> 
    
    ![L'output dopo l'esecuzione dello script CaseHoldsReport. ps1](media/7d312ed5-505e-4ec5-8f06-3571e3524a1a.png)
  
## <a name="more-information"></a><span data-ttu-id="7f51f-143">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="7f51f-143">More information</span></span>

<span data-ttu-id="7f51f-144">Il caso contiene il rapporto creato quando si esegue lo script in questo articolo contiene le informazioni seguenti su ogni blocco.</span><span class="sxs-lookup"><span data-stu-id="7f51f-144">The case holds report that's created when you run the script in this article contains the following information about each hold.</span></span> <span data-ttu-id="7f51f-145">Come spiegato in precedenza, è necessario essere un amministratore di eDiscovery per restituire le informazioni relative a tutte le esenzioni nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7f51f-145">As previously explained, you have to be an eDiscovery Administrator to return information for all holds in your organization.</span></span> <span data-ttu-id="7f51f-146">Per ulteriori informazioni sulle esenzioni dei casi, vedere [eDiscovery Cases](ediscovery-cases.md).</span><span class="sxs-lookup"><span data-stu-id="7f51f-146">For more information about case holds, see [eDiscovery cases](ediscovery-cases.md).</span></span>
  
  - <span data-ttu-id="7f51f-147">Nome del blocco e nome del caso di eDiscovery a cui è associato il blocco.</span><span class="sxs-lookup"><span data-stu-id="7f51f-147">The name of the hold and the name of the eDiscovery case that the hold is associated with.</span></span>
    
  - <span data-ttu-id="7f51f-148">Se il caso eDiscovery è attivo o chiuso.</span><span class="sxs-lookup"><span data-stu-id="7f51f-148">Whether or not the eDiscovery case is active or closed.</span></span>
    
  - <span data-ttu-id="7f51f-149">Se il blocco è abilitato o disabilitato.</span><span class="sxs-lookup"><span data-stu-id="7f51f-149">Whether or not the hold is enabled or disabled.</span></span>
    
  - <span data-ttu-id="7f51f-150">I membri del caso di eDiscovery a cui è associato il blocco.</span><span class="sxs-lookup"><span data-stu-id="7f51f-150">The members of the eDiscovery case that the hold is associated with.</span></span> <span data-ttu-id="7f51f-151">I membri del caso possono visualizzare o gestire un caso, a seconda delle autorizzazioni di eDiscovery a cui sono stati assegnati.</span><span class="sxs-lookup"><span data-stu-id="7f51f-151">Case members can view or manage a case, depending on the eDiscovery permissions they've been assigned.</span></span>
    
  - <span data-ttu-id="7f51f-152">Data e ora in cui è stato creato il caso.</span><span class="sxs-lookup"><span data-stu-id="7f51f-152">The time and date the case was created.</span></span>
    
  - <span data-ttu-id="7f51f-153">Se un caso è chiuso, la persona che lo ha chiuso e l'ora e la data in cui è stata chiusa.</span><span class="sxs-lookup"><span data-stu-id="7f51f-153">If a case is closed, the person who closed it and the time and date it was closed.</span></span>
    
  - <span data-ttu-id="7f51f-154">Posizioni delle cassette postali di Exchange e dei siti di SharePoint che sono in attesa.</span><span class="sxs-lookup"><span data-stu-id="7f51f-154">The Exchange mailboxes and SharePoint sites locations that are on hold.</span></span>
    
  - <span data-ttu-id="7f51f-155">Se il blocco è basato su query, la sintassi della query.</span><span class="sxs-lookup"><span data-stu-id="7f51f-155">If the hold is query-based, the query syntax.</span></span>
    
  - <span data-ttu-id="7f51f-156">La data e l'ora in cui è stato creato il blocco e la persona che lo ha creato.</span><span class="sxs-lookup"><span data-stu-id="7f51f-156">The time and date the hold was created and the person who created it.</span></span>
    
  - <span data-ttu-id="7f51f-157">Data e ora dell'Ultima modifica dell'esenzione e della persona che lo ha modificato.</span><span class="sxs-lookup"><span data-stu-id="7f51f-157">The time and date the hold was last changed and the person who changed it.</span></span>
