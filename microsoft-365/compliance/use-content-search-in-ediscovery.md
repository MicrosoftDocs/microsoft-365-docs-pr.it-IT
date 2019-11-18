---
title: Utilizzare la ricerca di contenuto nel flusso di lavoro di eDiscovery
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/30/2016
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 55f31488-288a-473a-9b9e-831a11e3711a
description: 'Utilizzare uno script di PowerShell per creare una ricerca eDiscovery sul posto in Exchange online in base a una ricerca creata nel centro sicurezza & conformità. '
ms.openlocfilehash: a16bf747da2d2eb8219ac4c13f4ff8c34d37b2c3
ms.sourcegitcommit: 1d376287f6c1bf5174873e89ed4bf7bb15bc13f6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/14/2019
ms.locfileid: "38686602"
---
# <a name="use-content-search-in-your-ediscovery-workflow"></a><span data-ttu-id="275cb-103">Usare Ricerca contenuto nel flusso di lavoro di eDiscovery</span><span class="sxs-lookup"><span data-stu-id="275cb-103">Use Content Search in your eDiscovery workflow</span></span>

<span data-ttu-id="275cb-104">La funzionalità di ricerca contenuto nel centro sicurezza & conformità consente di effettuare una ricerca in tutte le cassette postali dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="275cb-104">The Content Search feature in the Security & Compliance Center allows you to search all mailboxes in your organization.</span></span> <span data-ttu-id="275cb-105">A differenza di eDiscovery sul posto in Exchange Online (dove è possibile effettuare ricerche fino a 10.000 cassette postali), non esistono limiti per il numero di cassette postali di destinazione in una singola ricerca.</span><span class="sxs-lookup"><span data-stu-id="275cb-105">Unlike In-Place eDiscovery in Exchange Online (where you can search up to 10,000 mailboxes), there are no limits for the number of target mailboxes in a single search.</span></span> <span data-ttu-id="275cb-106">Per gli scenari che richiedono di eseguire ricerche a livello dell'intera organizzazione, è possibile utilizzare Ricerca contenuto per effettuare ricerche in tutte le cassette postali.</span><span class="sxs-lookup"><span data-stu-id="275cb-106">For scenarios that require you to perform organization-wide searches, you can use Content Search to search all mailboxes.</span></span> <span data-ttu-id="275cb-107">È quindi possibile utilizzare le funzionalità per i flussi di lavoro di eDiscovery sul posto per eseguire altre attività relative a eDiscovery, come la conservazione delle cassette postali e l'esportazione dei risultati di ricerca.</span><span class="sxs-lookup"><span data-stu-id="275cb-107">Then you can use the workflow features of In-Place eDiscovery to perform other eDiscovery-related tasks, such as placing mailboxes on hold and exporting search results.</span></span> <span data-ttu-id="275cb-108">Ad esempio, si supponga di dover effettuare una ricerca in tutte le cassette postali per identificare responsabili specifici di un caso legale.</span><span class="sxs-lookup"><span data-stu-id="275cb-108">For example, let's say you have to search all mailboxes to identify specific custodians that are responsive to a legal case.</span></span> <span data-ttu-id="275cb-109">È possibile utilizzare la ricerca contenuto nel centro sicurezza & conformità per cercare tutte le cassette postali dell'organizzazione per identificare quelle che rispondono al caso.</span><span class="sxs-lookup"><span data-stu-id="275cb-109">You can use Content Search in the Security & Compliance Center to search all mailboxes in your organization to identify those that are responsive to the case.</span></span> <span data-ttu-id="275cb-110">Successivamente, è possibile utilizzare l'elenco delle cassette postali del custode come cassette postali di origine per una ricerca eDiscovery sul posto in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="275cb-110">Then you can use that list of custodian mailboxes as the source mailboxes for an In-Place eDiscovery search in Exchange Online.</span></span> <span data-ttu-id="275cb-111">eDiscovery sul posto consente, inoltre, di abilitare una conservazione per tali cassette postali di origine, copiare i risultati della ricerca in una cassetta postale di individuazione ed esportare i risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="275cb-111">Using In-Place eDiscovery also allows you to put a hold on those source mailboxes, copy search results to a discovery mailbox, and export the search results.</span></span>
  
<span data-ttu-id="275cb-112">In questo argomento è incluso uno script che è possibile eseguire per creare una ricerca eDiscovery sul posto in Exchange Online utilizzando l'elenco delle cassette postali di origine e la query di ricerca di una ricerca creata nel centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="275cb-112">This topic includes a script that you can run to create an In-Place eDiscovery search in Exchange Online by using the list of source mailboxes and search query from a search created in the Security & Compliance Center.</span></span> <span data-ttu-id="275cb-113">Di seguito viene fornita una panoramica del processo:</span><span class="sxs-lookup"><span data-stu-id="275cb-113">Here's an overview of the process:</span></span>
  
[<span data-ttu-id="275cb-114">Passaggio 1: creare una ricerca di contenuto per effettuare una ricerca in tutte le cassette postali dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="275cb-114">Step 1: Create a Content Search to search all mailboxes in your organization</span></span>](#step-1-create-a-content-search-to-search-all-mailboxes-in-your-organization)

[<span data-ttu-id="275cb-115">Passaggio 2: connettersi al centro conformità \& di sicurezza e a Exchange online in una singola sessione di PowerShell remota</span><span class="sxs-lookup"><span data-stu-id="275cb-115">Step 2: Connect to the Security \& Compliance Center and Exchange Online in a single remote PowerShell session</span></span>](#step-2-connect-to-the-security--compliance-center-and-exchange-online-in-a-single-remote-powershell-session)
  
[<span data-ttu-id="275cb-116">Passaggio 3: eseguire lo script per creare una ricerca eDiscovery sul posto dalla ricerca di contenuto</span><span class="sxs-lookup"><span data-stu-id="275cb-116">Step 3: Run the script to create an In-Place eDiscovery search from the Content Search</span></span>](#step-3-run-the-script-to-create-an-in-place-ediscovery-search-from-the-content-search)

[<span data-ttu-id="275cb-117">Step 4: Start the In-Place eDiscovery search</span><span class="sxs-lookup"><span data-stu-id="275cb-117">Step 4: Start the In-Place eDiscovery search</span></span>](#step-4-start-the-in-place-ediscovery-search)

## <a name="step-1-create-a-content-search-to-search-all-mailboxes-in-your-organization"></a><span data-ttu-id="275cb-118">Passaggio 1: creare una ricerca di contenuto per effettuare una ricerca in tutte le cassette postali dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="275cb-118">Step 1: Create a Content Search to search all mailboxes in your organization</span></span>

<span data-ttu-id="275cb-119">Il primo passaggio consiste nell'utilizzare il Centro sicurezza & Compliance (o la sicurezza & Compliance Center PowerShell) per creare una ricerca di contenuto che cerca tutte le cassette postali dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="275cb-119">The first step is to use the Security & Compliance Center (or Security & Compliance Center PowerShell) to create a Content Search that searches all mailboxes in your organization.</span></span> <span data-ttu-id="275cb-120">Non esiste alcun limite al numero di cassette postali per una singola ricerca di contenuto.</span><span class="sxs-lookup"><span data-stu-id="275cb-120">There's no limit for the number of mailboxes for a single Content Search.</span></span> <span data-ttu-id="275cb-121">Specificare una query con parole chiave appropriate (o una query per tipi di informazioni riservate) in modo che la ricerca restituisca solo le cassette postali di origine rilevanti per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="275cb-121">Specify an appropriate keyword query (or a query for sensitive information types) so that the search returns only those source mailboxes that are relevant to your investigation.</span></span> <span data-ttu-id="275cb-122">Se necessario, è possibile perfezionare la query di ricerca per circoscrivere l'ambito dei risultati di ricerca e il numero di cassette postali di origine restituite.</span><span class="sxs-lookup"><span data-stu-id="275cb-122">If necessary, refine the search query to narrow the scope of search results and source mailboxes that are returned.</span></span>
  
> [!NOTE]
> <span data-ttu-id="275cb-p104">Se la ricerca di contenuto di origine non restituisce risultati, non viene creata una ricerca eDiscovery sul posto quando si esegue lo script indicato al passaggio 3. Potrebbe essere necessario rivedere la query di ricerca ed eseguire di nuovo la ricerca di contenuto per ottenere dei risultati.</span><span class="sxs-lookup"><span data-stu-id="275cb-p104">If the source Content Search doesn't return any results, an In-Place eDiscovery won't be created when you run the script in Step 3. You may have to revise the search query then rerun the Content Search to return search results.</span></span> 
  
### <a name="use-the-security--compliance-center-to-search-all-mailboxes"></a><span data-ttu-id="275cb-125">Utilizzare il Centro sicurezza e conformità per effettuare ricerche in tutte le cassette postali</span><span class="sxs-lookup"><span data-stu-id="275cb-125">Use the Security & Compliance Center to search all mailboxes</span></span>

1. <span data-ttu-id="275cb-126">[Accedere al centro sicurezza & conformità](go-to-the-securitycompliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="275cb-126">[Go to the Security & Compliance Center](go-to-the-securitycompliance-center.md).</span></span> 
    
2. <span data-ttu-id="275cb-127"> > Fare **clic**su ricerca**contenuto**ricerca, quindi fare clic su nuova](media/O365-MDM-CreatePolicy-AddIcon.gif)icona di **ricerca** ![Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="275cb-127">Click **Search** > **Content search**, and then click **New search** ![Add icon](media/O365-MDM-CreatePolicy-AddIcon.gif).</span></span>
    
3. <span data-ttu-id="275cb-128">Nella pagina **Nuova ricerca**, digitare un nome per la ricerca di contenuto.</span><span class="sxs-lookup"><span data-stu-id="275cb-128">On the **New search** page, type a name for the Content Search.</span></span> 
    
4. <span data-ttu-id="275cb-129">In **Dove si vuole effettuare la ricerca?**, fare clic su **Cerca in tutte le cassette postali**, quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="275cb-129">Under **Where do you want us to look?**, click **Search all mailboxes**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="275cb-130">Nella casella sotto **Dove si vuole effettuare la ricerca?**, digitare una query di ricerca.</span><span class="sxs-lookup"><span data-stu-id="275cb-130">In the box under **What do you want us to look for?**, type a search query in the box.</span></span> <span data-ttu-id="275cb-131">È possibile specificare parole chiave, proprietà dei messaggi come le date di invio o ricezione o proprietà dei documenti come il nome file o la data dell'ultima modifica apportata.</span><span class="sxs-lookup"><span data-stu-id="275cb-131">You can specify keywords, message properties such as sent and received dates, or document properties such as file names or the date that a document was last changed.</span></span> <span data-ttu-id="275cb-132">È possibile utilizzare una query più complessa che utilizza un operatore booleano, ad esempio e, o, non o vicino, oppure è anche possibile cercare informazioni riservate (ad esempio i numeri di previdenza sociale) nei messaggi.</span><span class="sxs-lookup"><span data-stu-id="275cb-132">You can use a more complex queries that use a Boolean operator, such as AND, OR, NOT or NEAR, or you can also search for sensitive information (such as social security numbers) in messages.</span></span> <span data-ttu-id="275cb-133">Per ulteriori informazioni sulla creazione di query di ricerca, vedere [Keyword queries for Content Search](keyword-queries-and-search-conditions.md).</span><span class="sxs-lookup"><span data-stu-id="275cb-133">For more information about creating search queries, see [Keyword queries for Content Search](keyword-queries-and-search-conditions.md).</span></span>
    
6. <span data-ttu-id="275cb-134">Fare clic su **Ricerca** per salvare le impostazioni di ricerca e avviare la ricerca.</span><span class="sxs-lookup"><span data-stu-id="275cb-134">Click **Search** to save the search settings and start the search.</span></span> 
    
    <span data-ttu-id="275cb-135">Dopo un po' di tempo, viene visualizzata una stima dei risultati della ricerca nel riquadro dettagli.</span><span class="sxs-lookup"><span data-stu-id="275cb-135">After a while, an estimate of the search results displayed in the details pane.</span></span> <span data-ttu-id="275cb-136">La stima include la dimensione totale e il numero di elementi per i risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="275cb-136">The estimate includes the total size and number of items for the search results.</span></span> <span data-ttu-id="275cb-137">Una volta completata la ricerca, è possibile visualizzare in anteprima i risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="275cb-137">After the search is completed, you can preview the search results.</span></span> <span data-ttu-id="275cb-138">Se necessario **, fare clic su**![Aggiorna](media/O365-MDM-Policy-RefreshIcon.gif) l'icona Aggiorna per aggiornare le informazioni nel riquadro dei dettagli.</span><span class="sxs-lookup"><span data-stu-id="275cb-138">If necessary, click **Refresh**![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the information in the details pane.</span></span> 
    
7.  <span data-ttu-id="275cb-139">Se necessario, perfezionare la query di ricerca per limitare l'ambito dei risultati della ricerca, quindi riavviare la ricerca.</span><span class="sxs-lookup"><span data-stu-id="275cb-139">If necessary, refine the search query to narrow the scope of search results and then restart the search.</span></span> 
    
### <a name="use-security--compliance-center-powershell-to-search-all-mailboxes"></a><span data-ttu-id="275cb-140">Utilizzare la sicurezza & Compliance Center PowerShell per effettuare ricerche in tutte le cassette postali</span><span class="sxs-lookup"><span data-stu-id="275cb-140">Use Security & Compliance Center PowerShell to search all mailboxes</span></span>

<span data-ttu-id="275cb-141">È inoltre possibile utilizzare il cmdlet **New-ComplianceSearch** per effettuare ricerche in tutte le cassette postali dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="275cb-141">You can also use the **New-ComplianceSearch** cmdlet to search all mailboxes in your organization.</span></span> <span data-ttu-id="275cb-142">Il primo passaggio consiste nel [connettersi a PowerShell per Centro sicurezza & Compliance](https://go.microsoft.com/fwlink/p/?LinkID=627084).</span><span class="sxs-lookup"><span data-stu-id="275cb-142">The first step is to [Connect to Security & Compliance Center PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=627084).</span></span>
  
<span data-ttu-id="275cb-143">Di seguito è riportato un esempio di utilizzo di PowerShell per eseguire una ricerca in tutte le cassette postali dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="275cb-143">Here's an example of using PowerShell to search all mailboxes in your organization.</span></span> <span data-ttu-id="275cb-144">La query di ricerca restituisce tutti i messaggi inviati tra il 1° gennaio 2015 e il 30 giugno 2015 e contenenti la frase "relazione finanziaria" nella riga dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="275cb-144">The search query returns all messages sent between January 1, 2015 and June 30, 2015 and that contain the phrase "financial report" in the subject line.</span></span> <span data-ttu-id="275cb-145">Il primo comando crea la ricerca e il secondo la esegue.</span><span class="sxs-lookup"><span data-stu-id="275cb-145">The first command creates the search, and the second command runs the search.</span></span> 
  
```powershell
New-ComplianceSearch -Name "Search All-Financial Report" -ExchangeLocation all -ContentMatchQuery 'sent>=01/01/2015 AND sent<=06/30/2015 AND subject:"financial report"'
```

```powershell
Start-ComplianceSearch -Identity "Search All-Financial Report"
```

<span data-ttu-id="275cb-146">Per ulteriori informazioni, vedere [New-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517935).</span><span class="sxs-lookup"><span data-stu-id="275cb-146">For more information, see [New-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517935).</span></span>
  
### <a name="verify-the-number-of-source-mailboxes-in-the-content-search"></a><span data-ttu-id="275cb-147">Verificare il numero di cassette postali di origine nella ricerca di contenuto</span><span class="sxs-lookup"><span data-stu-id="275cb-147">Verify the number of source mailboxes in the Content Search</span></span>

<span data-ttu-id="275cb-148">Una ricerca di contenuto restituisce un massimo di 1.000 cassette postali di origine che contengono i risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="275cb-148">A Content Search returns a maximum of 1,000 source mailboxes that contain search results.</span></span> <span data-ttu-id="275cb-149">Se sono presenti più di 1.000 cassette postali che contengono contenuto che corrisponde alla query di ricerca, solo le cassette postali di 1.000 con la maggior parte dei risultati della ricerca vengono incluse nella ricerca di contenuto creata nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="275cb-149">If there are more than 1,000 mailboxes that contain content that matches the search query, only the top 1,000 mailboxes with the most search results are included in the Content Search that you created in the previous step.</span></span> <span data-ttu-id="275cb-150">Pertanto, se più di 1.000 cassette postali contengono risultati della ricerca, alcune di queste cassette postali non verranno incluse nell'elenco delle cassette postali di origine copiate nella nuova ricerca eDiscovery sul posto creata nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="275cb-150">So if more than 1,000 mailboxes contain search results, some of those mailboxes won't be included in the list of source mailboxes copied to the new In-Place eDiscovery search created in Step 3.</span></span> 
  
<span data-ttu-id="275cb-151">Per facilitare la creazione di una ricerca di contenuto con non più di 1.000 cassette postali di origine, seguire questa procedura per eseguire uno script che Visualizza il numero di cassette postali di origine (che contengono i risultati della ricerca) restituite dalla ricerca di contenuto creata nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="275cb-151">To help you create a Content Search with no more than 1,000 source mailboxes, follow these steps to run a script that displays the number of source mailboxes (that contain search results) returned by the Content Search you created in Step 1.</span></span> 
  
1. <span data-ttu-id="275cb-152">Salvare il testo seguente in un file di script di PowerShell utilizzando un suffisso FileName di. ps1.</span><span class="sxs-lookup"><span data-stu-id="275cb-152">Save the following text to a PowerShell script file by using a filename suffix of .ps1.</span></span> <span data-ttu-id="275cb-153">Ad esempio, è possibile salvarlo in un file denominato `SourceMailboxes.ps1`.</span><span class="sxs-lookup"><span data-stu-id="275cb-153">For example, you could save it to a file named `SourceMailboxes.ps1`.</span></span>
    
  ```powershell
  [CmdletBinding()]
  Param(
      [Parameter(Mandatory=$True,Position=1)]
      [string]$SearchName
  )
  $search = Get-ComplianceSearch $SearchName
  if ($search.Status -ne "Completed")
  {
                  "Please wait until the search finishes.";
                  break;
  }
  $results = $search.SuccessResults;
  if (($search.Items -le 0) -or ([string]::IsNullOrWhiteSpace($results)))
  {
                  "The Content Search " + $SearchName + " didn't return any useful results.";
                  break;
  }
  $mailboxes = @();
  $lines = $results -split '[\r\n]+';
  foreach ($line in $lines)
  {
      if ($line -match 'Location: (\S+),.+Item count: (\d+)' -and $matches[2] -gt 0)
      {
          $mailboxes += $matches[1];
      }
  }
  "Number of mailboxes that have search hits: " + $mailboxes.Count
  ```

2. <span data-ttu-id="275cb-154">In PowerShell Centro sicurezza & conformità, passare alla cartella in cui si trova lo script creato nel passaggio precedente, quindi eseguire lo script. Per esempio:</span><span class="sxs-lookup"><span data-stu-id="275cb-154">In Security & Compliance Center PowerShell, go to the folder where the script you created in the previous step is located, and then run the script; for example:</span></span>
    
    ```powershell
    .\SourceMailboxes.ps1
    ```

3. <span data-ttu-id="275cb-155">Quando viene richiesto dallo script, digitare il nome della ricerca di contenuto creata nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="275cb-155">When prompted by the script, type the name of the Content Search that you created in Step 1.</span></span>
    
    <span data-ttu-id="275cb-156">Lo script consente di visualizzare il numero di cassette postali di origine che contengono i risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="275cb-156">The script displays the number of source mailboxes that contain search results.</span></span>
    
<span data-ttu-id="275cb-157">Se sono presenti più di 1.000 cassette postali di origine, provare a creare due (o più) ricerche di contenuto.</span><span class="sxs-lookup"><span data-stu-id="275cb-157">If there are more than 1,000 source mailboxes, try creating two (or more) Content Searches.</span></span> <span data-ttu-id="275cb-158">Ad esempio, effettuare una ricerca di contenuto per una metà delle cassette postali dell'organizzazione ed effettuare un'altra ricerca di contenuto per l'altra metà.</span><span class="sxs-lookup"><span data-stu-id="275cb-158">For example, search half of your organization's mailboxes in one Content Search and the other half in another Content Search.</span></span> <span data-ttu-id="275cb-159">È inoltre possibile modificare i criteri di ricerca per ridurre il numero di cassette postali che contengono i risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="275cb-159">You could also change the search criteria to reduce the number of mailboxes that contain search results.</span></span> <span data-ttu-id="275cb-160">Ad esempio, è possibile includere un intervallo di date o affinare la query di parole chiave.</span><span class="sxs-lookup"><span data-stu-id="275cb-160">For example, you could include a date range or refine the keyword query.</span></span>
  
## <a name="step-2-connect-to-the-security--compliance-center-and-exchange-online-in-a-single-remote-powershell-session"></a><span data-ttu-id="275cb-161">Passaggio 2: connettersi al centro conformità \& di sicurezza e a Exchange online in una singola sessione di PowerShell remota</span><span class="sxs-lookup"><span data-stu-id="275cb-161">Step 2: Connect to the Security \& Compliance Center and Exchange Online in a single remote PowerShell session</span></span>

<span data-ttu-id="275cb-162">Il passaggio successivo consiste nel connettere Windows PowerShell al centro sicurezza & compliance e all'organizzazione di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="275cb-162">The next step is to connect Windows PowerShell to both the Security & Compliance Center and to your Exchange Online organization.</span></span> <span data-ttu-id="275cb-163">Questa operazione è necessaria perché lo script eseguito nel passaggio 3 richiede l'accesso ai cmdlet di ricerca contenuto nel centro sicurezza & compliance e nei cmdlet eDiscovery sul posto in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="275cb-163">This is necessary because the script that you run in Step 3 requires access to the Content Search cmdlets in the Security & Compliance Center and the In-Place eDiscovery cmdlets in Exchange Online.</span></span>
  
1. <span data-ttu-id="275cb-164">Salvare il testo seguente in un file di script di Windows PowerShell con il suffisso del nome .ps1.</span><span class="sxs-lookup"><span data-stu-id="275cb-164">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1.</span></span> <span data-ttu-id="275cb-165">Ad esempio, è possibile salvarlo in un file denominato `ConnectEXO-CC.ps1`.</span><span class="sxs-lookup"><span data-stu-id="275cb-165">For example, you could save it to a file named `ConnectEXO-CC.ps1`.</span></span>
    
    ```powershell
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -AllowClobber -DisableNameChecking
    $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Exchange Online + Compliance Center)"
    ```

2. <span data-ttu-id="275cb-166">Nel computer locale, aprire Windows PowerShell, passare alla cartella in cui si trova lo script creato nel passaggio precedente, quindi eseguire lo script. Per esempio:</span><span class="sxs-lookup"><span data-stu-id="275cb-166">On your local computer, open Windows PowerShell, go to the folder where the script that you created in the previous step is located, and then run the script; for example:</span></span>
    
    ```powershell
    .\ConnectEXO-CC.ps1
    ```

<span data-ttu-id="275cb-167">Come si può verificare se l'operazione ha avuto esito positivo?</span><span class="sxs-lookup"><span data-stu-id="275cb-167">How do you know if this worked?</span></span> <span data-ttu-id="275cb-168">Dopo aver eseguito lo script, i cmdlet del Centro sicurezza & compliance e di Exchange Online vengono importati nella sessione di PowerShell locale.</span><span class="sxs-lookup"><span data-stu-id="275cb-168">After you run the script, cmdlets from the Security & Compliance Center and Exchange Online are imported into your local PowerShell session.</span></span> <span data-ttu-id="275cb-169">Se non vengono visualizzati errori, la connessione è stata eseguita correttamente.</span><span class="sxs-lookup"><span data-stu-id="275cb-169">If you don't receive any errors, you connected successfully.</span></span> <span data-ttu-id="275cb-170">Un test rapido consiste nell'eseguire un cmdlet del Centro sicurezza & Compliance, ad esempio **Install-UnifiedCompliancePrerequisite** , e un cmdlet di Exchange Online, come **Get-Mailbox**.</span><span class="sxs-lookup"><span data-stu-id="275cb-170">A quick test is to run a Security & Compliance Center cmdlet—for example, **Install-UnifiedCompliancePrerequisite** —and an Exchange Online cmdlet, such as **Get-Mailbox**.</span></span> 
  
## <a name="step-3-run-the-script-to-create-an-in-place-ediscovery-search-from-the-content-search"></a><span data-ttu-id="275cb-171">Passaggio 3: eseguire lo script per creare una ricerca eDiscovery sul posto dalla ricerca di contenuto</span><span class="sxs-lookup"><span data-stu-id="275cb-171">Step 3: Run the script to create an In-Place eDiscovery search from the Content Search</span></span>

<span data-ttu-id="275cb-172">Dopo aver creato la sessione Dual PowerShell nel passaggio 2, il passaggio successivo consiste nell'eseguire uno script che convertirà una ricerca di contenuto esistente in una ricerca eDiscovery sul posto.</span><span class="sxs-lookup"><span data-stu-id="275cb-172">After you create the dual PowerShell session in Step 2, the next step is to run a script that will convert an existing Content Search to an In-Place eDiscovery search.</span></span> <span data-ttu-id="275cb-173">In particolare, lo script:</span><span class="sxs-lookup"><span data-stu-id="275cb-173">Here's what the script does:</span></span>
  
- <span data-ttu-id="275cb-174">Richiede il nome della ricerca di contenuto da convertire.</span><span class="sxs-lookup"><span data-stu-id="275cb-174">Prompts you for the name of the Content Search to convert.</span></span>
    
- <span data-ttu-id="275cb-p116">Verifica che la ricerca di contenuto abbia completato l'esecuzione. Se la ricerca di contenuto non restituisce risultati, non viene creata una ricerca eDiscovery sul posto.</span><span class="sxs-lookup"><span data-stu-id="275cb-p116">Verifies that the Content Search has completed running. If the Content Search doesn't return any results, and In-Place eDiscovery won't be created.</span></span>
    
- <span data-ttu-id="275cb-177">Salva un elenco di cassette postali di origine dalla ricerca di contenuto che contengono i risultati della ricerca per una variabile.</span><span class="sxs-lookup"><span data-stu-id="275cb-177">Saves a list of the source mailboxes from the Content Search that contain search results to a variable.</span></span>
    
- <span data-ttu-id="275cb-p117">Crea una nuova ricerca eDiscovery sul posto, con le proprietà riportate di seguito. La nuova ricerca non è stata avviata. È possibile avviarla nel passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="275cb-p117">Creates a new In-Place eDiscovery search, with the following properties. Note that the new search isn't started. You'll start it in step 4.</span></span>
    
  - <span data-ttu-id="275cb-181">**Nome** -il nome della nuova ricerca utilizza questo formato: \<nome della ricerca\>di contenuto _MBSearch1.</span><span class="sxs-lookup"><span data-stu-id="275cb-181">**Name** - The name of the new search uses this format: \<Name of Content Search\>_MBSearch1.</span></span> <span data-ttu-id="275cb-182">Se si esegue di nuovo lo script e si utilizza la stessa ricerca del contenuto di origine, la \<ricerca sarà denominata nome\>della ricerca di contenuto _MBSearch2.</span><span class="sxs-lookup"><span data-stu-id="275cb-182">If you run the script again and use the same source Content Search, the search will be named \<Name of Content Search\>_MBSearch2.</span></span>
    
  - <span data-ttu-id="275cb-183">**Cassette postali di origine** : tutte le cassette postali dalla ricerca contenuto che contengono i risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="275cb-183">**Source mailboxes** - All mailboxes from the Content Search that contain search results.</span></span> 
    
  - <span data-ttu-id="275cb-184">**Query di ricerca** -la nuova ricerca utilizza la query di ricerca dalla ricerca contenuto.</span><span class="sxs-lookup"><span data-stu-id="275cb-184">**Search query** - The new search uses the search query from the Content Search.</span></span> <span data-ttu-id="275cb-185">Se la ricerca di contenuto include tutti i contenuti (la query di ricerca è vuota), la nuova ricerca potrà usufruire di una query di ricerca vuota e includerà tutti i contenuti trovati nelle cassette postali di origine.</span><span class="sxs-lookup"><span data-stu-id="275cb-185">If the Content Search includes all content (where the search query is blank) the new search will also have a blank search query and will include all content found in the source mailboxes.</span></span> 
    
  - <span data-ttu-id="275cb-186">**Ricerca solo preventivo** : la nuova ricerca è contrassegnata come ricerca di sola stima.</span><span class="sxs-lookup"><span data-stu-id="275cb-186">**Estimate only search** - The new search is marked as an estimate-only search.</span></span> <span data-ttu-id="275cb-187">I risultati della ricerca non verranno copiati in una cassetta postale di individuazione dopo l'avvio.</span><span class="sxs-lookup"><span data-stu-id="275cb-187">It won't copy search results to a discovery mailbox after you start it.</span></span> 
    
1. <span data-ttu-id="275cb-188">Salvare il testo seguente in un file di script di Windows PowerShell con il suffisso del nome ps1.</span><span class="sxs-lookup"><span data-stu-id="275cb-188">Save the following text to a Windows PowerShell script file by using a filename suffix of ps1.</span></span> <span data-ttu-id="275cb-189">Ad esempio, è possibile salvarlo in un file denominato `CreateMBSearchFromComplianceSearch.ps1`.</span><span class="sxs-lookup"><span data-stu-id="275cb-189">For example, you could save it to a file named `CreateMBSearchFromComplianceSearch.ps1`.</span></span>
    
  ```powershell
  [CmdletBinding()]
  Param(
      [Parameter(Mandatory=$True,Position=1)]
      [string]$SearchName,
      [switch]$original,
      [switch]$restoreOriginal
  )
  $search = Get-ComplianceSearch $SearchName
  if ($search.Status -ne "Completed")
  {
    "Please wait until the search finishes";
    break;
  }
  $results = $search.SuccessResults;
  if (($search.Items -le 0) -or ([string]::IsNullOrWhiteSpace($results)))
  {
    "The Content Search " + $SearchName + " didn't return any useful results";
    "A mailbox search object wasn't created";
    break;
  }
  $mailboxes = @();
  $lines = $results -split '[\r\n]+';
  foreach ($line in $lines)
  {
      if ($line -match 'Location: (\S+),.+Item count: (\d+)' -and $matches[2] -gt 0)
      {
          $mailboxes += $matches[1];
      }
  }
  $msPrefix = $SearchName + "_MBSearch";
  $I = 1;
  $mbSearches = Get-MailboxSearch;
  while ($true)
  {
      $found = $false;
      $mbsName = "$msPrefix$I";
      foreach ($mbs in $mbSearches)
      {
          if ($mbs.Name -eq $mbsName)
          {
              $found = $true;
              break;
          }
      }
      if (!$found)
      {
          break;
      }
      $I++;
  }
  $query = $search.KeywordQuery;
  if ([string]::IsNullOrWhiteSpace($query))
  {
      $query = $search.ContentMatchQuery;
  }
  if ([string]::IsNullOrWhiteSpace($query))
  {
    New-MailboxSearch "$msPrefix$i" -SourceMailboxes $mailboxes -EstimateOnly;
  }
  else
  {
    New-MailboxSearch "$msPrefix$i" -SourceMailboxes $mailboxes -SearchQuery $query -EstimateOnly;
  }
  ```

2. <span data-ttu-id="275cb-190">Nella sessione di Windows PowerShell creata al passaggio 2 passare alla cartella in cui si trova lo script creato nel passaggio precedente, quindi eseguire lo script. Per esempio:</span><span class="sxs-lookup"><span data-stu-id="275cb-190">In the Windows PowerShell session that you created in Step 2, go to the folder where the script that you created in the previous step is located, and then run the script; for example:</span></span>
    
    ```powershell
    .\CreateMBSearchFromComplianceSearch.ps1
    ```

3. <span data-ttu-id="275cb-191">Quando viene richiesto dallo script, digitare il nome della ricerca di contenuto che si desidera includere in una ricerca eDiscovery sul posto, ad esempio la ricerca creata al passaggio 1, e quindi premere **invio**.</span><span class="sxs-lookup"><span data-stu-id="275cb-191">When prompted by the script, type the name of the Content Search that you want to covert to an In-Place eDiscovery search (for example, the search that you created in Step 1), and then press **Enter**.</span></span>
    
    <span data-ttu-id="275cb-p122">Se lo script ha esito positivo, viene creata una nuova ricerca eDiscovery sul posto con lo stato **NotStarted**. Eseguire il comando  `Get-MailboxSearch <Name of Content Search>_MBSearch1 | FL` per visualizzare le proprietà della nuova ricerca.</span><span class="sxs-lookup"><span data-stu-id="275cb-p122">If the script is successful, a new In-Place eDiscovery search is created with a status of **NotStarted**. Run the command  `Get-MailboxSearch <Name of Content Search>_MBSearch1 | FL` to display the properties of the new search.</span></span> 
  
## <a name="step-4-start-the-in-place-ediscovery-search"></a><span data-ttu-id="275cb-194">Passaggio 4: avviare la ricerca eDiscovery sul posto</span><span class="sxs-lookup"><span data-stu-id="275cb-194">Step 4: Start the In-Place eDiscovery search</span></span>

<span data-ttu-id="275cb-p123">Lo script eseguito nel passaggio 3 crea una nuova ricerca eDiscovery sul posto, ma non la avvia. Il passaggio successivo consiste nell'avviare la ricerca, affinché sia possibile ottenere una stima dei risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="275cb-p123">The script that you run in Step 3 creates a new In-Place eDiscovery search, but doesn't start it. The next step is to start the search so you can get an estimate of the search results.</span></span>
  
1. <span data-ttu-id="275cb-197">In the Exchange admin center (EAC), go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span><span class="sxs-lookup"><span data-stu-id="275cb-197">In the Exchange admin center (EAC), go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
2. <span data-ttu-id="275cb-198">Nella visualizzazione elenco, selezionare la ricerca eDiscovery sul posto creata nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="275cb-198">In the list view, select the In-Place eDiscovery search that you created in Step 3.</span></span>
    
3. <span data-ttu-id="275cb-199">![](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif) \> Fare **clic su icona ricerca di** ricerca **stimare i risultati** della ricerca per avviare la ricerca e restituire una stima delle dimensioni totali e del numero di elementi restituiti dalla ricerca.</span><span class="sxs-lookup"><span data-stu-id="275cb-199">Click **Search** ![Search icon](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif) \> **Estimate search results** to start the search and return an estimate of the total size and number of items returned by the search.</span></span> 
    
    <span data-ttu-id="275cb-200">Le stime vengono visualizzate nel riquadro dei dettagli.</span><span class="sxs-lookup"><span data-stu-id="275cb-200">The estimates are displayed in the details pane.</span></span> <span data-ttu-id="275cb-201">![Fare **clic su Aggiorna l'** icona](media/O365-MDM-Policy-RefreshIcon.gif) Aggiorna per aggiornare le informazioni visualizzate nel riquadro dei dettagli.</span><span class="sxs-lookup"><span data-stu-id="275cb-201">Click **Refresh** ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the information displayed in the details pane.</span></span> 
    
4. <span data-ttu-id="275cb-202">Per visualizzare in anteprima i risultati dopo il completamento della ricerca, fare clic su **Anteprima risultati della ricerca** nel riquadro dei dettagli.</span><span class="sxs-lookup"><span data-stu-id="275cb-202">To preview the results after the search is completed, click **Preview search results** in the details pane.</span></span>
  
## <a name="next-steps-after-creating-and-running-the-in-place-ediscovery-search"></a><span data-ttu-id="275cb-203">Passaggi successivi alla creazione e all'esecuzione della ricerca eDiscovery sul posto</span><span class="sxs-lookup"><span data-stu-id="275cb-203">Next steps after creating and running the In-Place eDiscovery search</span></span>

<span data-ttu-id="275cb-204">Dopo aver avviato la ricerca eDiscovery sul posto creata dallo script nel passaggio 3, è possibile utilizzare il normale flusso di lavoro della ricerca eDiscovery sul posto per eseguire varie operazioni relative alla ricerca eDiscovery sui risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="275cb-204">After you create and start the In-Place eDiscovery search that was created by the script in Step 3, you can use the normal In-Place eDiscovery workflow to perform different eDiscovery actions on the search results.</span></span>
  
### <a name="create-an-in-place-hold"></a><span data-ttu-id="275cb-205">Creare un blocco sul posto</span><span class="sxs-lookup"><span data-stu-id="275cb-205">Create an In-Place Hold</span></span>

1. <span data-ttu-id="275cb-206">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span><span class="sxs-lookup"><span data-stu-id="275cb-206">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
2. <span data-ttu-id="275cb-207">Nella visualizzazione elenco, selezionare la ricerca eDiscovery sul posto creata nel passaggio 3, quindi fare clic su **modifica** ![icona](media/O365-MDM-CreatePolicy-EditIcon.gif)modifica.</span><span class="sxs-lookup"><span data-stu-id="275cb-207">In the list view, select the In-Place eDiscovery search that you created in Step 3, and then click **Edit** ![Edit icon](media/O365-MDM-CreatePolicy-EditIcon.gif).</span></span>
    
3. <span data-ttu-id="275cb-208">Nella pagina **Blocco sul posto**, selezionare la casella di controllo **Blocca il contenuto delle cassette postali selezionate che corrisponde alla query di ricerca** e scegliere una delle seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="275cb-208">On the **In-Place Hold** page, select the **Place content matching the search query in selected mailboxes on hold** check box and then select one of the following options:</span></span> 
    
  - <span data-ttu-id="275cb-209">**Attesa illimitata** : selezionare questa opzione per inserire gli elementi restituiti dalla ricerca in un blocco indefinito.</span><span class="sxs-lookup"><span data-stu-id="275cb-209">**Hold indefinitely** - Choose this option to place items returned by the search on an indefinite hold.</span></span> <span data-ttu-id="275cb-210">Gli elementi conservati verranno mantenuti fino a quando la cassetta postale non sarà stata rimossa dalla ricerca o non sarà stata eliminata la ricerca.</span><span class="sxs-lookup"><span data-stu-id="275cb-210">Items on hold will be preserved until you remove the mailbox from the search or remove the search.</span></span> 
    
  - <span data-ttu-id="275cb-211">**Specificare il numero di giorni in cui contenere gli elementi relativi alla data di ricezione** : scegliere questa opzione per conservare gli elementi per un periodo specifico.</span><span class="sxs-lookup"><span data-stu-id="275cb-211">**Specify number of days to hold items relative to their received date** - Choose this option to hold items for a specific period.</span></span> <span data-ttu-id="275cb-212">La durata viene calcolata a partire dalla data di ricezione o creazione dell'elemento della cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="275cb-212">The duration is calculated from the date a mailbox item is received or created.</span></span> 
    
4. <span data-ttu-id="275cb-213">Fare clic su **Salva** per creare il blocco sul posto e riavviare la ricerca.</span><span class="sxs-lookup"><span data-stu-id="275cb-213">Click **Save** to create the In-Place Hold and restart the search.</span></span> 
    
[<span data-ttu-id="275cb-214">Inizio pagina</span><span class="sxs-lookup"><span data-stu-id="275cb-214">Return to top</span></span>](use-content-search-in-ediscovery.md#top)
  
### <a name="copy-the-search-results"></a><span data-ttu-id="275cb-215">Copiare i risultati della ricerca</span><span class="sxs-lookup"><span data-stu-id="275cb-215">Copy the search results</span></span>

1. <span data-ttu-id="275cb-216">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span><span class="sxs-lookup"><span data-stu-id="275cb-216">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
2. <span data-ttu-id="275cb-217">Nella visualizzazione elenco, selezionare la ricerca eDiscovery sul posto creata nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="275cb-217">In the list view, select the In-Place eDiscovery search that you created in Step 3.</span></span>
    
3. <span data-ttu-id="275cb-218">Fare clic su icona](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif) **ricerca di** ricerca e quindi su **Copia risultati della ricerca** dall'elenco a discesa. ![</span><span class="sxs-lookup"><span data-stu-id="275cb-218">Click **Search** ![Search icon](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif), and then click **Copy search results** from the drop-down list.</span></span> 
    
4. <span data-ttu-id="275cb-219">In **Copia risultati della ricerca**, scegliere una delle seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="275cb-219">In **Copy Search Results**, select from the following options:</span></span>
    
    - <span data-ttu-id="275cb-220">**Includi elementi non ricercabili** : selezionare questa casella di controllo per includere gli elementi della cassetta postale che non è stato possibile cercare (ad esempio, messaggi con allegati di tipi di file che non possono essere indicizzati dalla ricerca di Exchange).</span><span class="sxs-lookup"><span data-stu-id="275cb-220">**Include unsearchable items** - Select this check box to include mailbox items that couldn't be searched (for example, messages with attachments of file types that couldn't be indexed by Exchange Search).</span></span> 
    
    - <span data-ttu-id="275cb-221">**Attiva la deduplicazione** : selezionare questa casella di controllo per escludere i messaggi duplicati.</span><span class="sxs-lookup"><span data-stu-id="275cb-221">**Enable de-duplication** - Select this check box to exclude duplicate messages.</span></span> <span data-ttu-id="275cb-222">Nella cassetta postale di individuazione verrà copiata una sola istanza del messaggio.</span><span class="sxs-lookup"><span data-stu-id="275cb-222">Only a single instance of a message will be copied to the discovery mailbox.</span></span> 
    
    - <span data-ttu-id="275cb-223">**Abilita registrazione completa** : selezionare questa casella di controllo per includere un registro completo nei risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="275cb-223">**Enable full logging** - Select this check box to include a full log in search results.</span></span> 
    
    - <span data-ttu-id="275cb-224">**Invio della posta elettronica quando la copia è stata completata** : selezionare questa casella di controllo per ricevere una notifica tramite posta elettronica al termine della ricerca.</span><span class="sxs-lookup"><span data-stu-id="275cb-224">**Send me mail when the copy is completed** - Select this check box to get an email notification when the search is completed.</span></span> 
    
    - <span data-ttu-id="275cb-225">**Copiare i risultati in questa cassetta postale di individuazione** -fare clic su **Sfoglia** per selezionare la cassetta postale di individuazione in cui si desidera copiare i risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="275cb-225">**Copy results to this discovery mailbox** - Click **Browse** to select the discovery mailbox where you want the search results copied to.</span></span> 
    
5. <span data-ttu-id="275cb-226">Fare clic su **Copia** per avviare il processo per copiare i risultati della ricerca nella cassetta postale di individuazione specificata.</span><span class="sxs-lookup"><span data-stu-id="275cb-226">Click **Copy** to start the process to copy the search results to the specified discovery mailbox.</span></span> 
    
6. <span data-ttu-id="275cb-227">![Fare **clic su Aggiorna l'** icona](media/O365-MDM-Policy-RefreshIcon.gif) Aggiorna per aggiornare le informazioni sullo stato della copia visualizzate nel riquadro dei dettagli.</span><span class="sxs-lookup"><span data-stu-id="275cb-227">Click **Refresh** ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the information about the copying status that is displayed in the details pane.</span></span> 
    
7. <span data-ttu-id="275cb-228">Al termine della copia, fare clic su **Apri** per aprire la cassetta postale di individuazione e visualizzare i risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="275cb-228">When copying is complete, click **Open** to open the discovery mailbox to view the search results.</span></span> 
  
### <a name="export-the-search-results"></a><span data-ttu-id="275cb-229">Esportare i risultati della ricerca</span><span class="sxs-lookup"><span data-stu-id="275cb-229">Export the search results</span></span>

1. <span data-ttu-id="275cb-230">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span><span class="sxs-lookup"><span data-stu-id="275cb-230">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
2. <span data-ttu-id="275cb-231">Nella visualizzazione elenco, selezionare la ricerca eDiscovery sul posto creata nel passaggio 3, quindi fare clic su **Esporta in un file PST**.</span><span class="sxs-lookup"><span data-stu-id="275cb-231">In the list view, select the In-Place eDiscovery search that you created in Step 3, and then click **Export to a PST file**.</span></span>
    
3. <span data-ttu-id="275cb-232">Nella finestra **Strumento eDiscovery per esportazione PST** effettuare le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="275cb-232">In the **eDiscovery PST Export Tool** window, do the following:</span></span> 
    
    - <span data-ttu-id="275cb-233">Fare clic su **Sfoglia** per specificare la posizione in cui si desidera scaricare il file PST.</span><span class="sxs-lookup"><span data-stu-id="275cb-233">Click **Browse** to specify the location where you want to download the PST file.</span></span> 
    
    - <span data-ttu-id="275cb-p128">Selezionare la casella di controllo **Abilita deduplicazione** per escludere i messaggi duplicati. Il file PST conterrà una sola istanza di un messaggio.</span><span class="sxs-lookup"><span data-stu-id="275cb-p128">Click the **Enable deduplication** checkbox to exclude duplicate messages. Only a single instance of a message will be included in the PST file.</span></span> 
    
    - <span data-ttu-id="275cb-p129">Selezionare la casella di controllo **Includi elementi senza funzioni di ricerca** per includere elementi non ricercabili, ad esempio messaggi con allegati di tipi di file non indicizzabili da parte di Ricerca di Exchange. Gli elementi non ricercabili vengono esportati in un file PST separato.</span><span class="sxs-lookup"><span data-stu-id="275cb-p129">Click the **Include unsearchable items** checkbox to include mailbox items that couldn't be searched (for example, messages with attachments of file types that couldn't be indexed by Exchange Search). Unsearchable items are exported to a separate PST file.</span></span> 
    
4. <span data-ttu-id="275cb-238">Fare clic su **Start** per esportare i risultati della ricerca in un file PST.</span><span class="sxs-lookup"><span data-stu-id="275cb-238">Click **Start** to export the search results to a PST file.</span></span> 
    
    <span data-ttu-id="275cb-239">Viene visualizzata una finestra contenente informazioni relative allo stato del processo di esportazione.</span><span class="sxs-lookup"><span data-stu-id="275cb-239">A window is displayed that contains status information about the export process.</span></span>
