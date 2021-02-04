---
title: Usare uno script PowerShell per la ricerca nel log di audit
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom: seo-marvel-apr2020
description: Usare uno script PowerShell, che esegue il cmdlet Search-UnifiedAuditLog, per la ricerca nel log di audit. Questo script è ottimizzato per restituire un set di record di controllo di grandi dimensioni (fino a 50.000). Lo script esporta questi record in un file CSV che è possibile visualizzare o trasformare usando Power Query in Excel.
ms.openlocfilehash: a91a54a6c35f96b90df156eaf4bc9735c911fc11
ms.sourcegitcommit: 4f40f5be140a23bacff6fd7b85536de14fc7d499
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2021
ms.locfileid: "50084702"
---
# <a name="use-a-powershell-script-to-search-the-audit-log"></a><span data-ttu-id="bc621-105">Usare uno script PowerShell per la ricerca nel log di audit</span><span class="sxs-lookup"><span data-stu-id="bc621-105">Use a PowerShell script to search the audit log</span></span>

<span data-ttu-id="bc621-106">La sicurezza, la conformità e il controllo sono diventati una priorità assoluta per gli amministratori IT al giorno d’oggi.</span><span class="sxs-lookup"><span data-stu-id="bc621-106">Security, compliance, and auditing have become a top priority for IT administrators in today’s world.</span></span> <span data-ttu-id="bc621-107">Microsoft 365 offre diverse funzionalità incorporate per aiutare le organizzazioni a gestire la sicurezza, la conformità e il controllo.</span><span class="sxs-lookup"><span data-stu-id="bc621-107">Microsoft 365 has several built-in capabilities to help organizations manage security, compliance, and auditing.</span></span> <span data-ttu-id="bc621-108">In particolare, la registrazione di controllo unificata consente di esaminare gli incidenti di sicurezza e i problemi di conformità.</span><span class="sxs-lookup"><span data-stu-id="bc621-108">In particular, unified audit logging can help you investigate security incidents and compliance issues.</span></span> <span data-ttu-id="bc621-109">È possibile recuperare i log di audit usando i metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="bc621-109">You can retrieve audit logs by using the following methods:</span></span>

- [<span data-ttu-id="bc621-110">L’API Office 365 Management Activity</span><span class="sxs-lookup"><span data-stu-id="bc621-110">The Office 365 Management Activity API</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)

- <span data-ttu-id="bc621-111">Lo [strumento di ricerca nel log di audit](search-the-audit-log-in-security-and-compliance.md) nel Centro conformità Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="bc621-111">The [audit log search tool](search-the-audit-log-in-security-and-compliance.md) in the Microsoft 365 compliance center</span></span>

- <span data-ttu-id="bc621-112">Il cmdlet [Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog) in Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="bc621-112">The [Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog) cmdlet in Exchange Online PowerShell</span></span>

<span data-ttu-id="bc621-113">Se è necessario recuperare regolarmente i log di audit, è consigliabile prendere in considerazione una soluzione che usi l'API Office 365 Management Activity, in quanto può offrire alle organizzazioni di grandi dimensioni la scalabilità e le prestazioni per recuperare milioni di record di controllo in modo continuativo.</span><span class="sxs-lookup"><span data-stu-id="bc621-113">If you need to retrieve audit logs on a regular basis, you should consider a solution that uses the Office 365 Management Activity API because it that can provide large organizations with the scalability and performance to retrieve millions of audit records on an ongoing basis.</span></span> <span data-ttu-id="bc621-114">L'uso dello strumento di ricerca nel log di audit nel Centro conformità Microsoft 365 è un ottimo modo per trovare rapidamente i record di controllo per operazioni specifiche che si verificano in un intervallo di tempo più breve.</span><span class="sxs-lookup"><span data-stu-id="bc621-114">Using the audit log search tool in Microsoft 365 compliance center is a good way to quickly find audit records for specific operations that occur in shorter time range.</span></span> <span data-ttu-id="bc621-115">L'uso di intervalli di tempo più lunghi nello strumento di ricerca nel log di audit, in particolare per le organizzazioni di grandi dimensioni, potrebbe restituire una quantità di record troppo elevata per essere gestita o esportata facilmente.</span><span class="sxs-lookup"><span data-stu-id="bc621-115">Using longer time ranges in the audit log search tool, especially for large organizations, might return too many records to easily manage or export.</span></span>

<span data-ttu-id="bc621-116">In situazioni in cui è necessario recuperare manualmente i dati di controllo per un'indagine o un incidente specifico, in particolare per intervalli di date più lunghi nelle organizzazioni di grandi dimensioni, l'uso del cmdlet **Search-UnifiedAuditLog** può essere l'opzione migliore.</span><span class="sxs-lookup"><span data-stu-id="bc621-116">When there are situations where you need to manually retrieve auditing data for a specific investigation or incident, particularly for longer date ranges in larger organizations, using the **Search-UnifiedAuditLog** cmdlet may be the best option.</span></span> <span data-ttu-id="bc621-117">Questo articolo include uno script PowerShell che usa il cmdlet per recuperare fino a 50.000 record di controllo e quindi esportarli in un file CSV che può essere formattato con Power Query in Excel per assistere nella revisione.</span><span class="sxs-lookup"><span data-stu-id="bc621-117">This article includes a PowerShell script that uses the cmdlet to retrieve up to 50,000 audit records and then export them to a CSV file that you can format using Power Query in Excel to help with your review.</span></span> <span data-ttu-id="bc621-118">L'uso dello script in questo articolo consente anche di ridurre al minimo la possibilità che le ricerche nel log di audit di grandi dimensioni raggiungano il timeout nel servizio.</span><span class="sxs-lookup"><span data-stu-id="bc621-118">Using the script in this article also minimizes the chance that large audit log searches will time out in the service.</span></span>

## <a name="before-you-run-the-script"></a><span data-ttu-id="bc621-119">Prima di eseguire lo script</span><span class="sxs-lookup"><span data-stu-id="bc621-119">Before you run the script</span></span>

- <span data-ttu-id="bc621-120">La registrazione di controllo deve essere abilitata per l'organizzazione per poter usare correttamente lo script per restituire record di controllo.</span><span class="sxs-lookup"><span data-stu-id="bc621-120">Audit logging has to be enabled for your organization to successfully use the script to return audit records.</span></span> <span data-ttu-id="bc621-121">La registrazione di controllo è attivata per impostazione predefinita per le organizzazioni di Microsoft 365 e Office 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="bc621-121">Audit logging is turned on by default for Microsoft 365 and Office 365 enterprise organizations.</span></span> <span data-ttu-id="bc621-122">Per verificare che la ricerca nel registro di controllo sia attivata per l’organizzazione, è possibile eseguire il comando seguente in Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="bc621-122">To verify that audit log search is turned on for your organization, you can run the following command in Exchange Online PowerShell:</span></span>

  ```powershell
  Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
  ```
  
  <span data-ttu-id="bc621-123">Il valore `True` per la proprietà **UnifiedAuditLogIngestionEnabled** indica che la ricerca nel log di audit è attivata.</span><span class="sxs-lookup"><span data-stu-id="bc621-123">The value of `True` for the **UnifiedAuditLogIngestionEnabled** property indicates that audit log search is turned on.</span></span>

- <span data-ttu-id="bc621-124">È necessario avere il ruolo Log di audit di sola lettura o Log di audit in Exchange Online per poter eseguire correttamente lo script.</span><span class="sxs-lookup"><span data-stu-id="bc621-124">You have to be assigned the View-Only Audit Logs or Audit Logs role in Exchange Online to run successfully the script.</span></span> <span data-ttu-id="bc621-125">Per impostazione predefinita, questi ruoli sono assegnati ai gruppi di ruoli Gestione conformità e Gestione organizzazione nella pagina Autorizzazioni nell'Interfaccia di amministrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="bc621-125">By default, these roles are assigned to the Compliance Management and Organization Management role groups on the Permissions page in the Exchange admin center.</span></span> <span data-ttu-id="bc621-126">Per altre informazioni, vedere la sezione "Requisiti per eseguire ricerche nel log di audit" in [Eseguire una ricerca nel log di audit nel Centro conformità](search-the-audit-log-in-security-and-compliance.md#requirements-to-search-the-audit-log).</span><span class="sxs-lookup"><span data-stu-id="bc621-126">For more information, see the "Requirements to search the audit log" section in [Search the audit log in the compliance center](search-the-audit-log-in-security-and-compliance.md#requirements-to-search-the-audit-log).</span></span>

- <span data-ttu-id="bc621-127">Il completamento dello script può richiedere molto tempo.</span><span class="sxs-lookup"><span data-stu-id="bc621-127">It may take a long time for the script to complete.</span></span> <span data-ttu-id="bc621-128">Il tempo necessario per l'esecuzione dipende dall'intervallo di date e dalle dimensioni dell'intervallo per cui si configura lo script per il recupero dei record di controllo.</span><span class="sxs-lookup"><span data-stu-id="bc621-128">How long it takes to run depends on the date range and the size of the interval that you configure the script to retrieve audit records for.</span></span> <span data-ttu-id="bc621-129">Date più distanziate con intervalli più piccoli comportano una durata di esecuzione maggiore.</span><span class="sxs-lookup"><span data-stu-id="bc621-129">Larger date ranges and smaller intervals will result in a long running time.</span></span> <span data-ttu-id="bc621-130">Per altre informazioni sull'intervallo di date e sugli intervalli, vedere la tabella del passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="bc621-130">See the table in Step 2 for more information about the date range and intervals.</span></span>

- <span data-ttu-id="bc621-131">Lo script di esempio fornito in questo articolo non è supportato da alcun programma o servizio standard di supporto Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bc621-131">The sample script provided in this article isn't supported under any Microsoft standard support program or service.</span></span> <span data-ttu-id="bc621-132">Lo script di esempio è fornito così come è senza alcun tipo di garanzia.</span><span class="sxs-lookup"><span data-stu-id="bc621-132">The sample script is provided AS IS without warranty of any kind.</span></span> <span data-ttu-id="bc621-133">Microsoft esclude inoltre qualsiasi garanzia implicita, tra cui, senza limitazioni, tutte le garanzie implicite di commerciabilità o idoneità per uno scopo specifico.</span><span class="sxs-lookup"><span data-stu-id="bc621-133">Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.</span></span> <span data-ttu-id="bc621-134">L'utente assume tutti i rischi associati all'uso o alle prestazioni dello script di esempio e della documentazione.</span><span class="sxs-lookup"><span data-stu-id="bc621-134">The entire risk arising out of the use or performance of the sample script and documentation remains with you.</span></span> <span data-ttu-id="bc621-135">In nessun caso Microsoft, i suoi autori o chiunque altro coinvolto nella creazione, produzione o consegna dello script è da ritenersi responsabile per qualsiasi danno eventuale (inclusi, senza limitazione alcuna, danni riguardanti profitti aziendali, interruzione di attività, perdita di informazioni aziendali o altra perdita pecuniaria) derivanti dall'utilizzo o dall'incapacità di utilizzo dello script di esempio e della documentazione, anche nel caso in cui Microsoft sia stata avvisata della possibilità di tali danni.</span><span class="sxs-lookup"><span data-stu-id="bc621-135">In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the script be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample script or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>

## <a name="step-1-connect-to-exchange-online-powershell"></a><span data-ttu-id="bc621-136">Passaggio 1: Connettersi a Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="bc621-136">Step 1: Connect to Exchange Online PowerShell</span></span>

<span data-ttu-id="bc621-137">La prima operazione da eseguire consiste nel connettersi a Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bc621-137">The first step is to connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="bc621-138">È possibile connettersi usando l'autenticazione moderna o l'autenticazione a più fattori (MFA).</span><span class="sxs-lookup"><span data-stu-id="bc621-138">You can connect using modern authentication or with multi-factor authentication (MFA).</span></span> <span data-ttu-id="bc621-139">Per istruzioni dettagliate, vedere [Connettersi a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="bc621-139">For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

## <a name="step-2-modify-and-run-the-script-to-retrieve-audit-records"></a><span data-ttu-id="bc621-140">Passaggio 2: Modificare ed eseguire lo script per recuperare i record di controllo</span><span class="sxs-lookup"><span data-stu-id="bc621-140">Step 2: Modify and run the script to retrieve audit records</span></span>

<span data-ttu-id="bc621-141">Dopo aver eseguito la connessione a Exchange Online PowerShell, il passaggio successivo consiste nel creare, modificare ed eseguire lo script per recuperare i dati di controllo.</span><span class="sxs-lookup"><span data-stu-id="bc621-141">After you've connected to Exchange Online PowerShell, the next step is to create, modify, and run the script to retrieve the auditing data.</span></span> <span data-ttu-id="bc621-142">Le prime sette righe dello script di ricerca nel log di audit contengono le variabili seguenti che è possibile modificare per configurare la ricerca.</span><span class="sxs-lookup"><span data-stu-id="bc621-142">The first seven lines in the audit log search script contain the following variables that you can modify to configure your search.</span></span> <span data-ttu-id="bc621-143">Per la descrizione di queste variabili, vedere la tabella nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="bc621-143">See the table in step 2 for a description of these variables.</span></span>

1. <span data-ttu-id="bc621-144">Salvare il testo seguente in uno script di Windows PowerShell con il suffisso del nome .ps1.</span><span class="sxs-lookup"><span data-stu-id="bc621-144">Save the following text to a Windows PowerShell script by using a filename suffix of .ps1.</span></span> <span data-ttu-id="bc621-145">Ad esempio: SearchAuditLog.ps1.</span><span class="sxs-lookup"><span data-stu-id="bc621-145">For example, SearchAuditLog.ps1.</span></span>

```powershell
#Modify the values for the following variables to configure the audit log search.
$logFile = "d:\AuditLogSearch\AuditLogSearchLog.txt"
$outputFile = "d:\AuditLogSearch\AuditLogRecords.csv"
[DateTime]$start = [DateTime]::UtcNow.AddDays(-1)
[DateTime]$end = [DateTime]::UtcNow
$record = "AzureActiveDirectory"
$resultSize = 5000
$intervalMinutes = 60

#Start script
[DateTime]$currentStart = $start
[DateTime]$currentEnd = $start

Function Write-LogFile ([String]$Message)
{
    $final = [DateTime]::Now.ToString("s") + ":" + $Message
    $final | Out-File $logFile -Append
}

Write-LogFile "BEGIN: Retrieving audit records between $($start) and $($end), RecordType=$record, PageSize=$resultSize."
Write-Host "Retrieving audit records for the date range between $($start) and $($end), RecordType=$record, ResultsSize=$resultSize"

$totalCount = 0
while ($true)
{
    $currentEnd = $currentStart.AddMinutes($intervalMinutes)
    if ($currentEnd -gt $end)
    {
        $currentEnd = $end
    }

    if ($currentStart -eq $currentEnd)
    {
        break
    }

    $sessionID = [DateTime]::Now.ToString("s")
    Write-LogFile "INFO: Retrieving audit records for activities performed between $($currentStart) and $($currentEnd)"
    Write-Host "Retrieving audit records for activities performed between $($currentStart) and $($currentEnd)"
    $currentCount = 0

    $sw = [Diagnostics.StopWatch]::StartNew()
    do
    {
        $results = Search-UnifiedAuditLog -StartDate $currentStart -EndDate $currentEnd -RecordType $record -SessionId $sessionID -SessionCommand ReturnLargeSet -ResultSize $resultSize

        if (($results | Measure-Object).Count -ne 0)
        {
            $results | export-csv -Path $outputFile -Append -NoTypeInformation

            $currentTotal = $results[0].ResultCount
            $totalCount += $results.Count
            $currentCount += $results.Count
            Write-LogFile "INFO: Retrieved $($currentCount) audit records out of the total $($currentTotal)"

            if ($currentTotal -eq $results[$results.Count - 1].ResultIndex)
            {
                $message = "INFO: Successfully retrieved $($currentTotal) audit records for the current time range. Moving on!"
                Write-LogFile $message
                Write-Host "Successfully retrieved $($currentTotal) audit records for the current time range. Moving on to the next interval." -foregroundColor Yellow
                ""
                break
            } 
        }
    }
    while (($results | Measure-Object).Count -ne 0)

    $currentStart = $currentEnd
}

Write-LogFile "END: Retrieving audit records between $($start) and $($end), RecordType=$record, PageSize=$resultSize, total count: $totalCount."
Write-Host "Script complete! Finished retrieving audit records for the date range between $($start) and $($end). Total count: $totalCount" -foregroundColor Green

```

2. <span data-ttu-id="bc621-146">Modificare le variabili elencate nella tabella seguente per configurare i criteri di ricerca.</span><span class="sxs-lookup"><span data-stu-id="bc621-146">Modify the variables listed in the following table to configure the search criteria.</span></span> <span data-ttu-id="bc621-147">Lo script include valori di esempio per queste variabili, ma è consigliabile modificarli (se non diversamente specificato) in modo da soddisfare i requisiti specifici.</span><span class="sxs-lookup"><span data-stu-id="bc621-147">The script includes sample values for these variables, but you should change them (unless stated otherwise) to meet your specific requirements.</span></span>

   |<span data-ttu-id="bc621-148">Variabile</span><span class="sxs-lookup"><span data-stu-id="bc621-148">Variable</span></span>|<span data-ttu-id="bc621-149">Valore esemplificativo</span><span class="sxs-lookup"><span data-stu-id="bc621-149">Sample value</span></span>|<span data-ttu-id="bc621-150">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bc621-150">Description</span></span>|
   |---|---|---|
   |`$logFile`|<span data-ttu-id="bc621-151">"d:\temp\AuditSearchLog.txt"</span><span class="sxs-lookup"><span data-stu-id="bc621-151">"d:\temp\AuditSearchLog.txt"</span></span>|<span data-ttu-id="bc621-152">Specifica il nome e il percorso del file di log che contiene informazioni sullo stato della ricerca nel log di audit eseguita dallo script.</span><span class="sxs-lookup"><span data-stu-id="bc621-152">Specifies the name and location for the log file that contains information about the progress of the audit log search performed by the script.</span></span>|
   |`$outputFile`|<span data-ttu-id="bc621-153">"d:\temp\AuditRecords.csv"</span><span class="sxs-lookup"><span data-stu-id="bc621-153">"d:\temp\AuditRecords.csv"</span></span>|<span data-ttu-id="bc621-154">Specifica il nome e il percorso del file CSV che contiene i record di controllo restituiti dallo script.</span><span class="sxs-lookup"><span data-stu-id="bc621-154">Specifies the name and location of the CSV file that contains the audit records returned by the script.</span></span>|
   |<span data-ttu-id="bc621-155">`[DateTime]$start` e `[DateTime]$end`</span><span class="sxs-lookup"><span data-stu-id="bc621-155">`[DateTime]$start` and `[DateTime]$end`</span></span>|[DateTime]::UtcNow.AddDays(-1) <br/>[DateTime]::UtcNow|<span data-ttu-id="bc621-158">Specifica l'intervallo di date per la ricerca nel log di audit.</span><span class="sxs-lookup"><span data-stu-id="bc621-158">Specifies the date range for the audit log search.</span></span> <span data-ttu-id="bc621-159">Lo script restituirà i record per le attività di controllo che si sono verificate all’interno dell'intervallo di date specificato.</span><span class="sxs-lookup"><span data-stu-id="bc621-159">The script will return records for audit activities that occurred within the specified date range.</span></span> <span data-ttu-id="bc621-160">Ad esempio, per restituire le attività eseguite nel mese di gennaio 2021, è possibile usare una data di inizio `"2021-01-01"` e una data di fine `"2021-01-31"` (racchiudere i valori tra virgolette doppie). Il valore di esempio nello script restituisce i record per le attività eseguite nelle 24 ore precedenti.</span><span class="sxs-lookup"><span data-stu-id="bc621-160">For example, to return activities performed in January 2021, you can use a start date of `"2021-01-01"` and an end date of `"2021-01-31"` (be sure to surround the values in double-quotation marks) The sample value in the script returns records for activities performed in the previous 24 hours.</span></span> <span data-ttu-id="bc621-161">Se non si include un timestamp nel valore, viene utilizzato il timestamp predefinito 00:00 (mezzanotte) nella data specificata.</span><span class="sxs-lookup"><span data-stu-id="bc621-161">If you don't include a timestamp in the value, the default timestamp is 12:00 AM (midnight) on the specified date.</span></span>|
   |`$record`|<span data-ttu-id="bc621-162">"AzureActiveDirectory"</span><span class="sxs-lookup"><span data-stu-id="bc621-162">"AzureActiveDirectory"</span></span>|<span data-ttu-id="bc621-163">Specifica il tipo di record delle attività di controllo (chiamate anche *operazioni*) da cercare.</span><span class="sxs-lookup"><span data-stu-id="bc621-163">Specifies the record type of the audit activities (also called *operations*) to search for.</span></span> <span data-ttu-id="bc621-164">Questa proprietà indica il servizio o la caratteristica in cui è stata attivata un'attività.</span><span class="sxs-lookup"><span data-stu-id="bc621-164">This property indicates the service or feature that an activity was triggered in.</span></span> <span data-ttu-id="bc621-165">Per un elenco dei tipi di record che è possibile usare per questa variabile, vedere [Tipo di record del log di audit](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#auditlogrecordtype).</span><span class="sxs-lookup"><span data-stu-id="bc621-165">For a list of record types that you can use for this variable, see [Audit log record type](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#auditlogrecordtype).</span></span> <span data-ttu-id="bc621-166">È possibile usare il nome del tipo di record o il valore di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="bc621-166">You can use the record type name or ENUM value.</span></span> <br/><br/><span data-ttu-id="bc621-167">**Suggerimento:** per restituire i record di controllo per tutti i tipi di record, usare il valore `$null` (senza virgolette).</span><span class="sxs-lookup"><span data-stu-id="bc621-167">**Tip:** To return audit records for all record types, use the value `$null` (without double-quotations marks).</span></span>|
   |`$resultSize`|<span data-ttu-id="bc621-168">5000</span><span class="sxs-lookup"><span data-stu-id="bc621-168">5000</span></span>|<span data-ttu-id="bc621-169">Specifica il numero di risultati restituiti ogni volta che il cmdlet **Search-UnifiedAuditLog** viene chiamato dallo script (definito come *set di risultati*).</span><span class="sxs-lookup"><span data-stu-id="bc621-169">Specifies the number of results returned each time the **Search-UnifiedAuditLog** cmdlet is called by the script (called a *result set*).</span></span> <span data-ttu-id="bc621-170">5000 è il valore massimo supportato dal cmdlet.</span><span class="sxs-lookup"><span data-stu-id="bc621-170">The value of 5,000 is the maximum value supported by the cmdlet.</span></span> <span data-ttu-id="bc621-171">Lasciare questo valore così come è.</span><span class="sxs-lookup"><span data-stu-id="bc621-171">Leave this value as-is.</span></span>|
   |`$intervalMinutes`|<span data-ttu-id="bc621-172">60</span><span class="sxs-lookup"><span data-stu-id="bc621-172">60</span></span>|<span data-ttu-id="bc621-173">Per superare il limite di 5000 record restituiti, questa variabile accetta l'intervallo di dati specificato e lo suddivide in intervalli di tempo inferiori.</span><span class="sxs-lookup"><span data-stu-id="bc621-173">To help overcome the limit of 5000 records returned, this variable takes the data range you specified and slices it up into smaller time intervals.</span></span> <span data-ttu-id="bc621-174">Ora ogni intervallo, e non l'intero intervallo di date, è soggetto al limite del comando di un output di 5000 record.</span><span class="sxs-lookup"><span data-stu-id="bc621-174">Now each interval, not the entire date range, is subject to the 5000 record output limit of the command.</span></span> <span data-ttu-id="bc621-175">Il valore predefinito di 5000 record per intervallo di 60 minuti all’interno dell'intervallo di date dovrebbe essere sufficiente per la maggior parte delle organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="bc621-175">The default value of 5000 records per 60 minute interval within the date range should be sufficient for most organizations.</span></span> <span data-ttu-id="bc621-176">Tuttavia, se lo script restituisce un errore che indica `maximum results limitation reached`, ridurre l'intervallo di tempo (ad esempio a 30 o anche 15 minuti) ed eseguire di nuovo lo script.</span><span class="sxs-lookup"><span data-stu-id="bc621-176">But, if the script returns an error that says, `maximum results limitation reached`, decrease the time interval (for example, to 30 minutes or even 15 minutes) and rerun the script.</span></span>|
   ||||

   <span data-ttu-id="bc621-177">La maggior parte delle variabili elencate nella tabella precedente corrispondono ai parametri per il cmdlet **Search-UnifiedAuditLog**.</span><span class="sxs-lookup"><span data-stu-id="bc621-177">Most of the variables listed in the previous table correspond to parameters for the **Search-UnifiedAuditLog** cmdlet.</span></span> <span data-ttu-id="bc621-178">Per ulteriori informazioni su questi parametri, vedere [Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog).</span><span class="sxs-lookup"><span data-stu-id="bc621-178">For more information about these parameters, see [Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog).</span></span>

3. <span data-ttu-id="bc621-179">Aprire Windows PowerShell sul computer locale e passare alla cartella in cui è stato salvato lo script modificato.</span><span class="sxs-lookup"><span data-stu-id="bc621-179">On your local computer, open Windows PowerShell and go to the folder where you saved the modified script.</span></span>

4. <span data-ttu-id="bc621-180">Eseguire lo script in Exchange Online PowerShell, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="bc621-180">Run the script in Exchange Online PowerShell; for example:</span></span>

   ```powershell
   .\SearchAuditLog.ps1
   ```

<span data-ttu-id="bc621-181">Lo script visualizza i messaggi di stato mentre è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="bc621-181">The script displays progress messages while it's running.</span></span> <span data-ttu-id="bc621-182">Al termine dell'esecuzione, lo script crea il file di log e il file CSV che contiene i record di controllo e li salva nelle cartelle definite dalle variabili `$logFile` e `$outputFile`.</span><span class="sxs-lookup"><span data-stu-id="bc621-182">After the script is finished running, it creates the log file and the CSV file that contains the audit records and saves them to the folders defined by the `$logFile` and `$outputFile` variables.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bc621-183">Esiste un limite di 50.000 per il numero massimo di record di controllo restituiti ogni volta che si esegue questo script.</span><span class="sxs-lookup"><span data-stu-id="bc621-183">There is a 50,000 limit for the maximum number of audit records returned each time you run this script.</span></span> <span data-ttu-id="bc621-184">Se si esegue questo script e vengono restituiti 50.000 risultati, è probabile che i record di controllo per le attività che si sono verificate all’interno dell'intervallo di date non siano stati inclusi.</span><span class="sxs-lookup"><span data-stu-id="bc621-184">If you run this script and it returns 50,000 results, then it's likely that audit records for activities that occurred within the date range weren't included.</span></span> <span data-ttu-id="bc621-185">In questo caso, è consigliabile dividere l'intervallo di date in durate più piccole e quindi eseguire di nuovo lo script per ogni intervallo di date.</span><span class="sxs-lookup"><span data-stu-id="bc621-185">If this happens, we recommend that you divide the date range into smaller durations and then rerun the script for each date range.</span></span> <span data-ttu-id="bc621-186">Ad esempio, se un intervallo di date di 90 giorni restituisce 50.000 risultati, è possibile eseguire di nuovo lo script in due volte, una per i primi 45 giorni nell'intervallo di date e la seconda per i 45 giorni seguenti.</span><span class="sxs-lookup"><span data-stu-id="bc621-186">For example, if a date range of 90 days returns 50,000 results then you can rerun the script twice, once for the first 45 days in the date range and then again for the next 45 days.</span></span>

## <a name="step-3-format-and-view-the-audit-records"></a><span data-ttu-id="bc621-187">Passaggio 3: Formattare e visualizzare i record di controllo</span><span class="sxs-lookup"><span data-stu-id="bc621-187">Step 3: Format and view the audit records</span></span>

<span data-ttu-id="bc621-188">Dopo aver eseguito lo script ed esportato i record di controllo in un file CSV, è possibile formattare il file CSV per semplificare la revisione e l'analisi dei record di controllo.</span><span class="sxs-lookup"><span data-stu-id="bc621-188">After you've run the script and exported the audit records to a CSV file, you may want to format the CSV to make easier to review and analyze the audit records.</span></span> <span data-ttu-id="bc621-189">Un modo per farlo è la funzionalità di trasformazione JSON di Power Query in Excel per suddividere ogni proprietà della colonna **AuditData** nell'oggetto JSON in colonne specifiche.</span><span class="sxs-lookup"><span data-stu-id="bc621-189">One way to do this is to the Power Query JSON transform feature in Excel to split each property in the JSON object in the **AuditData** column into its own column.</span></span> <span data-ttu-id="bc621-190">Per istruzioni dettagliate, vedere “Passaggio 2: Formattare il log di audit esportato usando l’editor di Power Query” in [Esportare, configurare e visualizzare i record del log di audit](export-view-audit-log-records.md#step-2-format-the-exported-audit-log-using-the-power-query-editor).</span><span class="sxs-lookup"><span data-stu-id="bc621-190">For step-by-step instructions, see "Step 2: Format the exported audit log using the Power Query Editor" in [Export, configure, and view audit log records](export-view-audit-log-records.md#step-2-format-the-exported-audit-log-using-the-power-query-editor).</span></span>
