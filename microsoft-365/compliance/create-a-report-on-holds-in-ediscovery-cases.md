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
description: Informazioni su come generare un report contenente informazioni su tutti i blocchi associati ai casi di eDiscovery.
ms.openlocfilehash: 04282f6f2481d892fa16d685936efeec55feae77
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908410"
---
# <a name="create-a-report-on-holds-in-ediscovery-cases"></a><span data-ttu-id="f01e6-103">Creare un report sui casi di blocco in eDiscovery</span><span class="sxs-lookup"><span data-stu-id="f01e6-103">Create a report on holds in eDiscovery cases</span></span>

<span data-ttu-id="f01e6-104">Lo script in questo articolo consente agli amministratori di eDiscovery e ai responsabili di eDiscovery di generare un report contenente informazioni su tutti i blocchi associati ai casi di eDiscovery nel Centro conformità in Office 365 o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f01e6-104">The script in this article lets eDiscovery administrators and eDiscovery managers generate a report that contains information about all holds that are associated with eDiscovery cases in the the compliance center in Office 365 or Microsoft 365.</span></span> <span data-ttu-id="f01e6-105">Il report contiene informazioni quali il nome del caso a cui è associata un'esenzione, le posizioni del contenuto che vengono poste in attesa e se il blocco è basato su query.</span><span class="sxs-lookup"><span data-stu-id="f01e6-105">The report contains information such as the name of the case a hold is associated with, the content locations that are placed on hold, and whether the hold is query-based.</span></span> <span data-ttu-id="f01e6-106">Se in alcuni casi non sono presenti esenzioni, lo script creerà un report aggiuntivo con un elenco di casi senza esenzioni.</span><span class="sxs-lookup"><span data-stu-id="f01e6-106">If there are cases that don't have any holds, the script will create an additional report with a list of cases without holds.</span></span>

<span data-ttu-id="f01e6-107">Per una [descrizione](#more-information) dettagliata delle informazioni incluse nel report, vedere la sezione Ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="f01e6-107">See the [More information](#more-information) section for a detailed description of the information included in the report.</span></span>

## <a name="admin-requirements-and-script-information"></a><span data-ttu-id="f01e6-108">Requisiti dell'amministratore e informazioni sullo script</span><span class="sxs-lookup"><span data-stu-id="f01e6-108">Admin requirements and script information</span></span>

- <span data-ttu-id="f01e6-109">Per generare un report su tutti i casi di eDiscovery nell'organizzazione, è necessario essere un amministratore di eDiscovery nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f01e6-109">To generate a report on all eDiscovery cases in your organization, you have to be an eDiscovery Administrator in your organization.</span></span> <span data-ttu-id="f01e6-110">Se si è un responsabile di eDiscovery, il report includerà solo informazioni sui casi a cui è possibile accedere.</span><span class="sxs-lookup"><span data-stu-id="f01e6-110">If you are an eDiscovery Manager, the report will only include information about the cases that you can access.</span></span> <span data-ttu-id="f01e6-111">Per ulteriori informazioni sulle autorizzazioni di eDiscovery, vedere [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="f01e6-111">For more information about eDiscovery permissions, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

- <span data-ttu-id="f01e6-112">Lo script in questo articolo ha una gestione minima degli errori.</span><span class="sxs-lookup"><span data-stu-id="f01e6-112">The script in this article has minimal error handling.</span></span> <span data-ttu-id="f01e6-113">Lo scopo principale è creare rapidamente report sulle esenzioni associate ai casi di eDiscovery nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f01e6-113">The primary purpose is to quickly create report about the holds that are associated with the eDiscovery cases in your organization.</span></span>

- <span data-ttu-id="f01e6-p104">Gli script di esempio forniti in questo articolo non sono supportati da alcun programma o servizio standard di supporto Microsoft. Gli script di esempio sono forniti così come sono senza alcun tipo di garanzia. Inoltre Microsoft declina ogni responsabilità su garanzie implicite, senza alcuna limitazione, incluse le garanzie implicite di commerciabilità e/o adeguatezza per uno scopo specifico. Qualsiasi rischio eventuale pervenga, durante l'utilizzo degli script di esempio e della documentazione, si intende a carico dell'utente. In nessun caso Microsoft, i suoi autori o chiunque altro coinvolto nella creazione, produzione o consegna degli script è da ritenersi responsabile per qualsiasi danno eventuale (inclusi, senza limitazione alcuna, danni riguardanti profitti aziendali, interruzione di attività, perdita di informazioni aziendali o altra perdita pecuniaria) derivanti dall'utilizzo o dall'incapacità di utilizzo degli script di esempio e della documentazione, anche nel caso in cui Microsoft sia stata avvisata della possibilità di tali danni.</span><span class="sxs-lookup"><span data-stu-id="f01e6-p104">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>

## <a name="step-1-connect-to-the-security--compliance-center-powershell"></a><span data-ttu-id="f01e6-119">Passaggio 1: connettersi a PowerShell & Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="f01e6-119">Step 1: Connect to the Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="f01e6-120">Il primo passaggio consiste nel connettersi a PowerShell & Centro sicurezza e conformità per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f01e6-120">The first step is to connect to Security & Compliance Center PowerShell for your organization.</span></span> <span data-ttu-id="f01e6-121">Per ottenere istruzioni dettagliate, vedere [Connettersi a PowerShell in Centro sicurezza e conformità](/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="f01e6-121">For step-by-step instructions, see [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

## <a name="step-2-run-the-script-to-report-on-holds-associated-with-ediscovery-cases"></a><span data-ttu-id="f01e6-122">Passaggio 2: eseguire lo script per segnalare i blocchi associati ai casi di eDiscovery</span><span class="sxs-lookup"><span data-stu-id="f01e6-122">Step 2: Run the script to report on holds associated with eDiscovery cases</span></span>

<span data-ttu-id="f01e6-123">Dopo aver eseguito la connessione & PowerShell al Centro sicurezza e conformità, il passaggio successivo consiste nel creare ed eseguire lo script che raccoglie informazioni sui casi di eDiscovery nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f01e6-123">After you've connected to Security & Compliance Center PowerShell, the next step is to create and run the script that collects information about the eDiscovery cases in your organization.</span></span>

1. <span data-ttu-id="f01e6-124">Salvare il testo seguente in un file Windows PowerShell script utilizzando il suffisso del nome di file ps1. ad esempio, CaseHoldsReport.ps1.</span><span class="sxs-lookup"><span data-stu-id="f01e6-124">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, CaseHoldsReport.ps1.</span></span>

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

2. <span data-ttu-id="f01e6-125">Nella sessione Windows PowerShell aperta nel passaggio 1 passare alla cartella in cui è stato salvato lo script.</span><span class="sxs-lookup"><span data-stu-id="f01e6-125">In the Windows PowerShell session that opened in Step 1, go to the folder where you saved the script.</span></span>

3. <span data-ttu-id="f01e6-126">Eseguire lo script; Per esempio:</span><span class="sxs-lookup"><span data-stu-id="f01e6-126">Run the script; for example:</span></span>

   ```powershell
   .\CaseHoldsReport.ps1
   ```

   <span data-ttu-id="f01e6-127">Lo script richiederà una cartella di destinazione in cui salvare il report.</span><span class="sxs-lookup"><span data-stu-id="f01e6-127">The script will prompt for a target folder to save the report to.</span></span>

4. <span data-ttu-id="f01e6-128">Digitare il nome del percorso completo della cartella in cui salvare il report e quindi premere **INVIO.**</span><span class="sxs-lookup"><span data-stu-id="f01e6-128">Type the full path name of the folder to save the report to, and then press **Enter**.</span></span>

   > [!TIP]
   > <span data-ttu-id="f01e6-129">Per salvare il report nella stessa cartella in cui si trova lo script, digitare un punto (".") quando viene richiesto di specificare una cartella di destinazione.</span><span class="sxs-lookup"><span data-stu-id="f01e6-129">To save the report in the same folder that the script is located in, type a period (".") when prompted for a target folder.</span></span> <span data-ttu-id="f01e6-130">Per salvare il report in una sottocartella della cartella in cui si trova lo script, è sufficiente digitare il nome della sottocartella.</span><span class="sxs-lookup"><span data-stu-id="f01e6-130">To save the report in a subfolder in the folder where the script is located, just type the name of the subfolder.</span></span>

   <span data-ttu-id="f01e6-131">Lo script inizia a raccogliere informazioni su tutti i casi di eDiscovery nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f01e6-131">The script starts to collect information about all the eDiscovery cases in your organization.</span></span> <span data-ttu-id="f01e6-132">Non accedere al file di report durante l'esecuzione dello script.</span><span class="sxs-lookup"><span data-stu-id="f01e6-132">Don't access the report file while the script is running.</span></span> <span data-ttu-id="f01e6-133">Al termine dello script, viene visualizzato un messaggio di conferma nella Windows PowerShell sessione.</span><span class="sxs-lookup"><span data-stu-id="f01e6-133">After the script is complete, a confirmation message is displayed in the Windows PowerShell session.</span></span> <span data-ttu-id="f01e6-134">Dopo aver visualizzato questo messaggio, è possibile accedere al report nella cartella specificata nel passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="f01e6-134">After this message is displayed, you can access the report in the folder that you specified in Step 4.</span></span> <span data-ttu-id="f01e6-135">Il nome del file per il report è `CaseHoldsReport<DateTimeStamp>.csv` .</span><span class="sxs-lookup"><span data-stu-id="f01e6-135">The file name for the report is `CaseHoldsReport<DateTimeStamp>.csv`.</span></span>

   <span data-ttu-id="f01e6-136">In aggiunta, lo script crea anche un report con un elenco di casi che non dispongono di esenzioni.</span><span class="sxs-lookup"><span data-stu-id="f01e6-136">Addtionally, the script also creates a report with a list of cases that don't have any holds.</span></span> <span data-ttu-id="f01e6-137">Il nome del file per questo report è `CaseswithNoHolds<DateTimeStamp>.csv` .</span><span class="sxs-lookup"><span data-stu-id="f01e6-137">The file name for this report is `CaseswithNoHolds<DateTimeStamp>.csv`.</span></span>

   <span data-ttu-id="f01e6-138">Ecco un esempio di esecuzione dello script CaseHoldsReport.ps1.</span><span class="sxs-lookup"><span data-stu-id="f01e6-138">Here's an example of running the CaseHoldsReport.ps1 script.</span></span>

   ![Output dopo l'esecuzione dello script CaseHoldsReport.ps1](../media/7d312ed5-505e-4ec5-8f06-3571e3524a1a.png)

## <a name="more-information"></a><span data-ttu-id="f01e6-140">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="f01e6-140">More information</span></span>

<span data-ttu-id="f01e6-141">Il report di conservazione dei casi creato quando si esegue lo script in questo articolo contiene le informazioni seguenti su ogni blocco.</span><span class="sxs-lookup"><span data-stu-id="f01e6-141">The case holds report that's created when you run the script in this article contains the following information about each hold.</span></span> <span data-ttu-id="f01e6-142">Come spiegato in precedenza, è necessario essere un amministratore di eDiscovery per restituire informazioni per tutte le esenzioni nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f01e6-142">As previously explained, you have to be an eDiscovery Administrator to return information for all holds in your organization.</span></span> <span data-ttu-id="f01e6-143">Per ulteriori informazioni sui casi di conservazione, vedere [casi di eDiscovery](./get-started-core-ediscovery.md).</span><span class="sxs-lookup"><span data-stu-id="f01e6-143">For more information about case holds, see [eDiscovery cases](./get-started-core-ediscovery.md).</span></span>

- <span data-ttu-id="f01e6-144">Il nome del blocco e il nome del caso eDiscovery a cui è associato il blocco.</span><span class="sxs-lookup"><span data-stu-id="f01e6-144">The name of the hold and the name of the eDiscovery case that the hold is associated with.</span></span>

- <span data-ttu-id="f01e6-145">Indica se il caso di eDiscovery è attivo o chiuso.</span><span class="sxs-lookup"><span data-stu-id="f01e6-145">Whether or not the eDiscovery case is active or closed.</span></span>

- <span data-ttu-id="f01e6-146">Indica se il blocco è abilitato o disabilitato.</span><span class="sxs-lookup"><span data-stu-id="f01e6-146">Whether or not the hold is enabled or disabled.</span></span>

- <span data-ttu-id="f01e6-147">I membri del caso di eDiscovery a cui è associato il blocco.</span><span class="sxs-lookup"><span data-stu-id="f01e6-147">The members of the eDiscovery case that the hold is associated with.</span></span> <span data-ttu-id="f01e6-148">I membri del caso possono visualizzare o gestire un caso, a seconda delle autorizzazioni di eDiscovery assegnate.</span><span class="sxs-lookup"><span data-stu-id="f01e6-148">Case members can view or manage a case, depending on the eDiscovery permissions they've been assigned.</span></span>

- <span data-ttu-id="f01e6-149">Data e ora di creazione del caso.</span><span class="sxs-lookup"><span data-stu-id="f01e6-149">The time and date the case was created.</span></span>

- <span data-ttu-id="f01e6-150">Se un caso è chiuso, l'utente che lo ha chiuso e l'ora e la data in cui è stato chiuso.</span><span class="sxs-lookup"><span data-stu-id="f01e6-150">If a case is closed, the person who closed it and the time and date it was closed.</span></span>

- <span data-ttu-id="f01e6-151">Le cassette postali di Exchange e i percorsi dei siti di SharePoint in attesa.</span><span class="sxs-lookup"><span data-stu-id="f01e6-151">The Exchange mailboxes and SharePoint sites locations that are on hold.</span></span>

- <span data-ttu-id="f01e6-152">Se il blocco è basato su query, la sintassi della query.</span><span class="sxs-lookup"><span data-stu-id="f01e6-152">If the hold is query-based, the query syntax.</span></span>

- <span data-ttu-id="f01e6-153">Ora e data in cui è stato creato il blocco e la persona che l'ha creata.</span><span class="sxs-lookup"><span data-stu-id="f01e6-153">The time and date the hold was created and the person who created it.</span></span>

- <span data-ttu-id="f01e6-154">Data e ora dell'ultima modifica del blocco e dell'utente che l'ha modificata.</span><span class="sxs-lookup"><span data-stu-id="f01e6-154">The time and date the hold was last changed and the person who changed it.</span></span>