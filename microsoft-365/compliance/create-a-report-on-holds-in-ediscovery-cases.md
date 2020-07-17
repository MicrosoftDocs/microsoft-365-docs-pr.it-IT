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
# <a name="create-a-report-on-holds-in-ediscovery-cases"></a><span data-ttu-id="e4bb6-103">Creare un report sui casi di blocco in eDiscovery</span><span class="sxs-lookup"><span data-stu-id="e4bb6-103">Create a report on holds in eDiscovery cases</span></span>
  
<span data-ttu-id="e4bb6-104">Lo script in questo articolo consente agli amministratori di eDiscovery e ai responsabili di eDiscovery di generare un report contenente informazioni su tutte le esenzioni associate ai casi di eDiscovery nel centro conformità di Office 365 o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e4bb6-104">The script in this article lets eDiscovery administrators and eDiscovery managers generate a report that contains information about all holds that are associated with eDiscovery cases in the the compliance center in Office 365 or Microsoft 365.</span></span> <span data-ttu-id="e4bb6-105">Il report contiene informazioni quali il nome del caso in cui è associata una conservazione, i percorsi di contenuto che sono stati conservati e se il blocco è basato su query.</span><span class="sxs-lookup"><span data-stu-id="e4bb6-105">The report contains information such as the name of the case a hold is associated with, the content locations that are placed on hold, and whether the hold is query-based.</span></span> <span data-ttu-id="e4bb6-106">Se sono presenti casi che non dispongono di alcuna esenzione, lo script creerà un ulteriore rapporto con un elenco di casi senza esenzioni.</span><span class="sxs-lookup"><span data-stu-id="e4bb6-106">If there are cases that don't have any holds, the script will create an additional report with a list of cases without holds.</span></span>

<span data-ttu-id="e4bb6-107">Per una descrizione dettagliata delle informazioni incluse nel report, vedere la sezione [ulteriori informazioni](#more-information) .</span><span class="sxs-lookup"><span data-stu-id="e4bb6-107">See the [More information](#more-information) section for a detailed description of the information included in the report.</span></span>
  
## <a name="admin-requirements-and-script-information"></a><span data-ttu-id="e4bb6-108">Requisiti di amministratore e informazioni sullo script</span><span class="sxs-lookup"><span data-stu-id="e4bb6-108">Admin requirements and script information</span></span>

- <span data-ttu-id="e4bb6-109">Per generare un report su tutti i casi di eDiscovery nell'organizzazione, è necessario essere un amministratore di eDiscovery nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e4bb6-109">To generate a report on all eDiscovery cases in your organization, you have to be an eDiscovery Administrator in your organization.</span></span> <span data-ttu-id="e4bb6-110">Se si è un Manager di eDiscovery, il report includerà solo informazioni sui casi in cui è possibile accedere.</span><span class="sxs-lookup"><span data-stu-id="e4bb6-110">If you are an eDiscovery Manager, the report will only include information about the cases that you can access.</span></span> <span data-ttu-id="e4bb6-111">Per ulteriori informazioni sulle autorizzazioni di eDiscovery, vedere [assign eDiscovery Permissions](assign-ediscovery-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="e4bb6-111">For more information about eDiscovery permissions, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>
    
- <span data-ttu-id="e4bb6-112">Lo script di questo articolo contiene una gestione degli errori minima.</span><span class="sxs-lookup"><span data-stu-id="e4bb6-112">The script in this article has minimal error handling.</span></span> <span data-ttu-id="e4bb6-113">Lo scopo principale consiste nel creare rapidamente report sulle esenzioni associate ai casi di eDiscovery nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e4bb6-113">The primary purpose is to quickly create report about the holds that are associated with the eDiscovery cases in your organization.</span></span>
    
- <span data-ttu-id="e4bb6-p104">Gli script di esempio forniti in questo articolo non sono supportati da alcun programma o servizio standard di supporto Microsoft. Gli script di esempio sono forniti così come sono senza alcun tipo di garanzia. Inoltre Microsoft declina ogni responsabilità su garanzie implicite, senza alcuna limitazione, incluse le garanzie implicite di commerciabilità e/o adeguatezza per uno scopo specifico. Qualsiasi rischio eventuale pervenga, durante l'utilizzo degli script di esempio e della documentazione, si intende a carico dell'utente. In nessun caso Microsoft, i suoi autori o chiunque altro coinvolto nella creazione, produzione o consegna degli script è da ritenersi responsabile per qualsiasi danno eventuale (inclusi, senza limitazione alcuna, danni riguardanti profitti aziendali, interruzione di attività, perdita di informazioni aziendali o altra perdita pecuniaria) derivanti dall'utilizzo o dall'incapacità di utilizzo degli script di esempio e della documentazione, anche nel caso in cui Microsoft sia stata avvisata della possibilità di tali danni.</span><span class="sxs-lookup"><span data-stu-id="e4bb6-p104">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
    
## <a name="step-1-connect-to-the-security--compliance-center-powershell"></a><span data-ttu-id="e4bb6-119">Passaggio 1: connettersi al centro sicurezza & Compliance PowerShell</span><span class="sxs-lookup"><span data-stu-id="e4bb6-119">Step 1: Connect to the Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="e4bb6-120">Il primo passaggio consiste nel connettersi a PowerShell per il Centro sicurezza & Compliance per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e4bb6-120">The first step is to connect to Security & Compliance Center PowerShell for your organization.</span></span> <span data-ttu-id="e4bb6-121">Per ottenere istruzioni dettagliate, vedere [Connettersi a PowerShell in Centro sicurezza e conformità](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="e4bb6-121">For step-by-step instructions, see [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>
  
<span data-ttu-id="e4bb6-122">Se l'account di Microsoft 365 usa l'autenticazione a più fattori o l'autenticazione federata, non è possibile usare le istruzioni riportate nell'argomento precedente per la connessione a PowerShell in Centro sicurezza e conformità.</span><span class="sxs-lookup"><span data-stu-id="e4bb6-122">If your Microsoft 365 account uses multi-factor authentication (MFA) or federated authentication, you can't use the instructions in the previous topic on connecting to Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="e4bb6-123">Per farlo, vedere le istruzioni nell’argomento [Connettersi a PowerShell in Centro sicurezza e conformità mediante l'autenticazione a più fattori](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="e4bb6-123">Instead, see the instructions in the topic [Connect to Security & Compliance Center PowerShell using multi-factor authentication](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell).</span></span>
  
## <a name="step-2-run-the-script-to-report-on-holds-associated-with-ediscovery-cases"></a><span data-ttu-id="e4bb6-124">Passaggio 2: eseguire lo script per segnalare le esenzioni associate ai casi di eDiscovery</span><span class="sxs-lookup"><span data-stu-id="e4bb6-124">Step 2: Run the script to report on holds associated with eDiscovery cases</span></span>

<span data-ttu-id="e4bb6-125">Dopo aver effettuato la connessione a PowerShell per il Centro sicurezza & conformità, il passaggio successivo consiste nel creare ed eseguire lo script che raccoglie informazioni sui casi di eDiscovery nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e4bb6-125">After you've connected to Security & Compliance Center PowerShell, the next step is to create and run the script that collects information about the eDiscovery cases in your organization.</span></span> 
  
1. <span data-ttu-id="e4bb6-126">Salvare il testo seguente in un file di script di Windows PowerShell utilizzando un suffisso FileName di. ps1. ad esempio, CaseHoldsReport.ps1.</span><span class="sxs-lookup"><span data-stu-id="e4bb6-126">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, CaseHoldsReport.ps1.</span></span> 
    
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

2. <span data-ttu-id="e4bb6-127">Nella sessione di Windows PowerShell aperta al passaggio 1 passare alla cartella in cui è stato salvato lo script.</span><span class="sxs-lookup"><span data-stu-id="e4bb6-127">In the Windows PowerShell session that opened in Step 1, go to the folder where you saved the script.</span></span> 
    
3. <span data-ttu-id="e4bb6-128">Eseguire lo script; Per esempio:</span><span class="sxs-lookup"><span data-stu-id="e4bb6-128">Run the script; for example:</span></span>

    ```powershell
    .\CaseHoldsReport.ps1
    ```

    <span data-ttu-id="e4bb6-129">Lo script richiederà la creazione di una cartella di destinazione in cui salvare il report.</span><span class="sxs-lookup"><span data-stu-id="e4bb6-129">The script will prompt for a target folder to save the report to.</span></span> 
    
4. <span data-ttu-id="e4bb6-130">Digitare il nome del percorso completo della cartella in cui salvare il report e quindi premere **invio**.</span><span class="sxs-lookup"><span data-stu-id="e4bb6-130">Type the full path name of the folder to save the report to, and then press **Enter**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="e4bb6-131">Per salvare il report nella stessa cartella in cui si trova lo script, digitare un punto (".") quando viene richiesto di specificare una cartella di destinazione.</span><span class="sxs-lookup"><span data-stu-id="e4bb6-131">To save the report in the same folder that the script is located in, type a period (".") when prompted for a target folder.</span></span> <span data-ttu-id="e4bb6-132">Per salvare il report in una sottocartella della cartella in cui si trova lo script, digitare il nome della sottocartella.</span><span class="sxs-lookup"><span data-stu-id="e4bb6-132">To save the report in a subfolder in the folder where the script is located, just type the name of the subfolder.</span></span> 
  
    <span data-ttu-id="e4bb6-133">Lo script inizia a raccogliere informazioni su tutti i casi di eDiscovery nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e4bb6-133">The script starts to collect information about all the eDiscovery cases in your organization.</span></span> <span data-ttu-id="e4bb6-134">Non accedere al file di report mentre lo script è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="e4bb6-134">Don't access the report file while the script is running.</span></span> <span data-ttu-id="e4bb6-135">Una volta completato lo script, nella sessione di Windows PowerShell viene visualizzato un messaggio di conferma.</span><span class="sxs-lookup"><span data-stu-id="e4bb6-135">After the script is complete, a confirmation message is displayed in the Windows PowerShell session.</span></span> <span data-ttu-id="e4bb6-136">Dopo aver visualizzato questo messaggio, è possibile accedere al report nella cartella specificata nel passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="e4bb6-136">After this message is displayed, you can access the report in the folder that you specified in Step 4.</span></span> <span data-ttu-id="e4bb6-137">Il nome del file del report è `CaseHoldsReport<DateTimeStamp>.csv` .</span><span class="sxs-lookup"><span data-stu-id="e4bb6-137">The file name for the report is `CaseHoldsReport<DateTimeStamp>.csv`.</span></span>

    <span data-ttu-id="e4bb6-138">Addtionally, lo script crea anche un rapporto con un elenco di casi che non dispongono di alcuna esenzione.</span><span class="sxs-lookup"><span data-stu-id="e4bb6-138">Addtionally, the script also creates a report with a list of cases that don't have any holds.</span></span> <span data-ttu-id="e4bb6-139">Il nome del file di questo report è `CaseswithNoHolds<DateTimeStamp>.csv` .</span><span class="sxs-lookup"><span data-stu-id="e4bb6-139">The file name for this report is `CaseswithNoHolds<DateTimeStamp>.csv`.</span></span>
    
    <span data-ttu-id="e4bb6-140">Di seguito è riportato un esempio di esecuzione dello script CaseHoldsReport.ps1.</span><span class="sxs-lookup"><span data-stu-id="e4bb6-140">Here's an example of running the CaseHoldsReport.ps1 script.</span></span> 
    
    ![L'output dopo l'esecuzione dello script CaseHoldsReport.ps1](../media/7d312ed5-505e-4ec5-8f06-3571e3524a1a.png)
  
## <a name="more-information"></a><span data-ttu-id="e4bb6-142">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="e4bb6-142">More information</span></span>

<span data-ttu-id="e4bb6-143">Il caso contiene il rapporto creato quando si esegue lo script in questo articolo contiene le informazioni seguenti su ogni blocco.</span><span class="sxs-lookup"><span data-stu-id="e4bb6-143">The case holds report that's created when you run the script in this article contains the following information about each hold.</span></span> <span data-ttu-id="e4bb6-144">Come spiegato in precedenza, è necessario essere un amministratore di eDiscovery per restituire le informazioni relative a tutte le esenzioni nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e4bb6-144">As previously explained, you have to be an eDiscovery Administrator to return information for all holds in your organization.</span></span> <span data-ttu-id="e4bb6-145">Per ulteriori informazioni sulle esenzioni dei casi, vedere [eDiscovery Cases](ediscovery-cases.md).</span><span class="sxs-lookup"><span data-stu-id="e4bb6-145">For more information about case holds, see [eDiscovery cases](ediscovery-cases.md).</span></span>
  
  - <span data-ttu-id="e4bb6-146">Nome del blocco e nome del caso di eDiscovery a cui è associato il blocco.</span><span class="sxs-lookup"><span data-stu-id="e4bb6-146">The name of the hold and the name of the eDiscovery case that the hold is associated with.</span></span>
    
  - <span data-ttu-id="e4bb6-147">Se il caso eDiscovery è attivo o chiuso.</span><span class="sxs-lookup"><span data-stu-id="e4bb6-147">Whether or not the eDiscovery case is active or closed.</span></span>
    
  - <span data-ttu-id="e4bb6-148">Se il blocco è abilitato o disabilitato.</span><span class="sxs-lookup"><span data-stu-id="e4bb6-148">Whether or not the hold is enabled or disabled.</span></span>
    
  - <span data-ttu-id="e4bb6-149">I membri del caso di eDiscovery a cui è associato il blocco.</span><span class="sxs-lookup"><span data-stu-id="e4bb6-149">The members of the eDiscovery case that the hold is associated with.</span></span> <span data-ttu-id="e4bb6-150">I membri del caso possono visualizzare o gestire un caso, a seconda delle autorizzazioni di eDiscovery a cui sono stati assegnati.</span><span class="sxs-lookup"><span data-stu-id="e4bb6-150">Case members can view or manage a case, depending on the eDiscovery permissions they've been assigned.</span></span>
    
  - <span data-ttu-id="e4bb6-151">Data e ora in cui è stato creato il caso.</span><span class="sxs-lookup"><span data-stu-id="e4bb6-151">The time and date the case was created.</span></span>
    
  - <span data-ttu-id="e4bb6-152">Se un caso è chiuso, la persona che lo ha chiuso e l'ora e la data in cui è stata chiusa.</span><span class="sxs-lookup"><span data-stu-id="e4bb6-152">If a case is closed, the person who closed it and the time and date it was closed.</span></span>
    
  - <span data-ttu-id="e4bb6-153">Posizioni delle cassette postali di Exchange e dei siti di SharePoint che sono in attesa.</span><span class="sxs-lookup"><span data-stu-id="e4bb6-153">The Exchange mailboxes and SharePoint sites locations that are on hold.</span></span>
    
  - <span data-ttu-id="e4bb6-154">Se il blocco è basato su query, la sintassi della query.</span><span class="sxs-lookup"><span data-stu-id="e4bb6-154">If the hold is query-based, the query syntax.</span></span>
    
  - <span data-ttu-id="e4bb6-155">La data e l'ora in cui è stato creato il blocco e la persona che lo ha creato.</span><span class="sxs-lookup"><span data-stu-id="e4bb6-155">The time and date the hold was created and the person who created it.</span></span>
    
  - <span data-ttu-id="e4bb6-156">Data e ora dell'Ultima modifica dell'esenzione e della persona che lo ha modificato.</span><span class="sxs-lookup"><span data-stu-id="e4bb6-156">The time and date the hold was last changed and the person who changed it.</span></span>
