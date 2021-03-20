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
# <a name="create-a-report-on-holds-in-ediscovery-cases"></a>Creare un report sui casi di blocco in eDiscovery

Lo script in questo articolo consente agli amministratori di eDiscovery e ai responsabili di eDiscovery di generare un report contenente informazioni su tutti i blocchi associati ai casi di eDiscovery nel Centro conformità in Office 365 o Microsoft 365. Il report contiene informazioni quali il nome del caso a cui è associata un'esenzione, le posizioni del contenuto che vengono poste in attesa e se il blocco è basato su query. Se in alcuni casi non sono presenti esenzioni, lo script creerà un report aggiuntivo con un elenco di casi senza esenzioni.

Per una [descrizione](#more-information) dettagliata delle informazioni incluse nel report, vedere la sezione Ulteriori informazioni.

## <a name="admin-requirements-and-script-information"></a>Requisiti dell'amministratore e informazioni sullo script

- Per generare un report su tutti i casi di eDiscovery nell'organizzazione, è necessario essere un amministratore di eDiscovery nell'organizzazione. Se si è un responsabile di eDiscovery, il report includerà solo informazioni sui casi a cui è possibile accedere. Per ulteriori informazioni sulle autorizzazioni di eDiscovery, vedere [Assign eDiscovery permissions](assign-ediscovery-permissions.md).

- Lo script in questo articolo ha una gestione minima degli errori. Lo scopo principale è creare rapidamente report sulle esenzioni associate ai casi di eDiscovery nell'organizzazione.

- Gli script di esempio forniti in questo articolo non sono supportati da alcun programma o servizio standard di supporto Microsoft. Gli script di esempio sono forniti così come sono senza alcun tipo di garanzia. Inoltre Microsoft declina ogni responsabilità su garanzie implicite, senza alcuna limitazione, incluse le garanzie implicite di commerciabilità e/o adeguatezza per uno scopo specifico. Qualsiasi rischio eventuale pervenga, durante l'utilizzo degli script di esempio e della documentazione, si intende a carico dell'utente. In nessun caso Microsoft, i suoi autori o chiunque altro coinvolto nella creazione, produzione o consegna degli script è da ritenersi responsabile per qualsiasi danno eventuale (inclusi, senza limitazione alcuna, danni riguardanti profitti aziendali, interruzione di attività, perdita di informazioni aziendali o altra perdita pecuniaria) derivanti dall'utilizzo o dall'incapacità di utilizzo degli script di esempio e della documentazione, anche nel caso in cui Microsoft sia stata avvisata della possibilità di tali danni.

## <a name="step-1-connect-to-the-security--compliance-center-powershell"></a>Passaggio 1: connettersi a PowerShell & Centro sicurezza e conformità

Il primo passaggio consiste nel connettersi a PowerShell & Centro sicurezza e conformità per l'organizzazione. Per ottenere istruzioni dettagliate, vedere [Connettersi a PowerShell in Centro sicurezza e conformità](/powershell/exchange/connect-to-scc-powershell).

## <a name="step-2-run-the-script-to-report-on-holds-associated-with-ediscovery-cases"></a>Passaggio 2: eseguire lo script per segnalare i blocchi associati ai casi di eDiscovery

Dopo aver eseguito la connessione & PowerShell al Centro sicurezza e conformità, il passaggio successivo consiste nel creare ed eseguire lo script che raccoglie informazioni sui casi di eDiscovery nell'organizzazione.

1. Salvare il testo seguente in un file Windows PowerShell script utilizzando il suffisso del nome di file ps1. ad esempio, CaseHoldsReport.ps1.

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

2. Nella sessione Windows PowerShell aperta nel passaggio 1 passare alla cartella in cui è stato salvato lo script.

3. Eseguire lo script; Per esempio:

   ```powershell
   .\CaseHoldsReport.ps1
   ```

   Lo script richiederà una cartella di destinazione in cui salvare il report.

4. Digitare il nome del percorso completo della cartella in cui salvare il report e quindi premere **INVIO.**

   > [!TIP]
   > Per salvare il report nella stessa cartella in cui si trova lo script, digitare un punto (".") quando viene richiesto di specificare una cartella di destinazione. Per salvare il report in una sottocartella della cartella in cui si trova lo script, è sufficiente digitare il nome della sottocartella.

   Lo script inizia a raccogliere informazioni su tutti i casi di eDiscovery nell'organizzazione. Non accedere al file di report durante l'esecuzione dello script. Al termine dello script, viene visualizzato un messaggio di conferma nella Windows PowerShell sessione. Dopo aver visualizzato questo messaggio, è possibile accedere al report nella cartella specificata nel passaggio 4. Il nome del file per il report è `CaseHoldsReport<DateTimeStamp>.csv` .

   In aggiunta, lo script crea anche un report con un elenco di casi che non dispongono di esenzioni. Il nome del file per questo report è `CaseswithNoHolds<DateTimeStamp>.csv` .

   Ecco un esempio di esecuzione dello script CaseHoldsReport.ps1.

   ![Output dopo l'esecuzione dello script CaseHoldsReport.ps1](../media/7d312ed5-505e-4ec5-8f06-3571e3524a1a.png)

## <a name="more-information"></a>Ulteriori informazioni

Il report di conservazione dei casi creato quando si esegue lo script in questo articolo contiene le informazioni seguenti su ogni blocco. Come spiegato in precedenza, è necessario essere un amministratore di eDiscovery per restituire informazioni per tutte le esenzioni nell'organizzazione. Per ulteriori informazioni sui casi di conservazione, vedere [casi di eDiscovery](./get-started-core-ediscovery.md).

- Il nome del blocco e il nome del caso eDiscovery a cui è associato il blocco.

- Indica se il caso di eDiscovery è attivo o chiuso.

- Indica se il blocco è abilitato o disabilitato.

- I membri del caso di eDiscovery a cui è associato il blocco. I membri del caso possono visualizzare o gestire un caso, a seconda delle autorizzazioni di eDiscovery assegnate.

- Data e ora di creazione del caso.

- Se un caso è chiuso, l'utente che lo ha chiuso e l'ora e la data in cui è stato chiuso.

- Le cassette postali di Exchange e i percorsi dei siti di SharePoint in attesa.

- Se il blocco è basato su query, la sintassi della query.

- Ora e data in cui è stato creato il blocco e la persona che l'ha creata.

- Data e ora dell'ultima modifica del blocco e dell'utente che l'ha modificata.