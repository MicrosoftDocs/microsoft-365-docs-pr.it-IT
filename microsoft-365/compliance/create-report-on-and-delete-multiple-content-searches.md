---
title: Creare, analizzare ed eliminare più ricerche di contenuto
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/26/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
ms.assetid: 1d463dda-a3b5-4675-95d4-83db19c9c4a3
description: Informazioni su come automatizzare le attività di ricerca contenuto come la creazione di ricerche e l'esecuzione di report tramite gli script di PowerShell nel centro sicurezza & compliance in Office 365.
ms.openlocfilehash: 75caf75d576ac4a24779de15f5b05cb7fe8fa724
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37083070"
---
# <a name="create-report-on-and-delete-multiple-content-searches"></a><span data-ttu-id="a8a5f-103">Creare, analizzare ed eliminare più ricerche di contenuto</span><span class="sxs-lookup"><span data-stu-id="a8a5f-103">Create, report on, and delete multiple Content Searches</span></span>

 <span data-ttu-id="a8a5f-104">Creare rapidamente e segnalare le ricerche di individuazione è spesso un passaggio importante in eDiscovery e nelle indagini quando si cerca di conoscere i dati sottostanti e la ricchezza e la qualità delle ricerche.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-104">Quickly creating and reporting discovery searches is often an important step in eDiscovery and investigations when you're trying to learn about the underlying data, and the richness and quality of your searches.</span></span> <span data-ttu-id="a8a5f-105">Per eseguire questa operazione, la sicurezza & Compliance Center PowerShell offre un set di cmdlet per automatizzare le attività di ricerca del contenuto in termini di tempo.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-105">To help you do this, the Security & Compliance Center PowerShell offers a set of cmdlets to automate time-consuming Content Search tasks.</span></span> <span data-ttu-id="a8a5f-106">Questi script consentono di creare una serie di ricerche in modo semplice e rapido e quindi di eseguire i report dei risultati di ricerca stimati che consentono di determinare la quantità di dati in questione.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-106">These scripts provide a quick and easy way to create a number of searches, and then run reports of the estimated search results that can help you determine the quantity of data in question.</span></span> <span data-ttu-id="a8a5f-107">È inoltre possibile utilizzare gli script per creare diverse versioni delle ricerche per confrontare i risultati prodotti da ognuno di essi.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-107">You can also use the scripts to create different versions of searches to compare the results each one produces.</span></span> <span data-ttu-id="a8a5f-108">Questi script consentono di identificare e abbattere i dati in modo rapido ed efficiente.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-108">These scripts can help you to quickly and efficiently identify and cull your data.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="a8a5f-109">Informazioni preliminari</span><span class="sxs-lookup"><span data-stu-id="a8a5f-109">Before you begin</span></span>

- <span data-ttu-id="a8a5f-110">Per eseguire gli script descritti in questo argomento, è necessario essere membri del gruppo di ruoli eDiscovery Manager nel centro sicurezza & Compliance.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-110">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center to run the scripts that are described in this topic.</span></span> 
    
- <span data-ttu-id="a8a5f-111">Per raccogliere un elenco degli URL per i siti di OneDrive for business nell'organizzazione che è possibile aggiungere al file CSV nel passaggio 1, vedere [creare un elenco di tutti i percorsi di OneDrive nell'organizzazione](https://support.office.com/article/Create-a-list-of-all-OneDrive-locations-in-your-organization-8e200cb2-c768-49cb-88ec-53493e8ad80a).</span><span class="sxs-lookup"><span data-stu-id="a8a5f-111">To collect a list of the URLs for the OneDrive for Business sites in your organization that you can add to the CSV file in Step 1, see [Create a list of all OneDrive locations in your organization](https://support.office.com/article/Create-a-list-of-all-OneDrive-locations-in-your-organization-8e200cb2-c768-49cb-88ec-53493e8ad80a).</span></span> 
    
- <span data-ttu-id="a8a5f-112">Assicurarsi di salvare tutti i file creati in questo argomento nella stessa cartella.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-112">Be sure to save all the files that you create in this topic to the same folder.</span></span> <span data-ttu-id="a8a5f-113">Questo renderà più facile eseguire gli script.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-113">That will make it easier to run the scripts.</span></span>
    
- <span data-ttu-id="a8a5f-114">Gli script includono la gestione degli errori minima.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-114">The scripts include minimal error handling.</span></span> <span data-ttu-id="a8a5f-115">Lo scopo principale consiste nel creare rapidamente, riferire ed eliminare più ricerche di contenuto.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-115">Their primary purpose is to quickly create, report on, and delete multiple Content Searches.</span></span>
    
- <span data-ttu-id="a8a5f-p104">Gli script di esempio forniti in questo articolo non sono supportati da alcun programma o servizio standard di supporto Microsoft. Gli script di esempio sono forniti così come sono senza alcun tipo di garanzia. Inoltre Microsoft declina ogni responsabilità su garanzie implicite, senza alcuna limitazione, incluse le garanzie implicite di commerciabilità e/o adeguatezza per uno scopo specifico. Qualsiasi rischio eventuale pervenga, durante l'utilizzo degli script di esempio e della documentazione, si intende a carico dell'utente. In nessun caso Microsoft, i suoi autori o chiunque altro coinvolto nella creazione, produzione o consegna degli script è da ritenersi responsabile per qualsiasi danno eventuale (inclusi, senza limitazione alcuna, danni riguardanti profitti aziendali, interruzione di attività, perdita di informazioni aziendali o altra perdita pecuniaria) derivanti dall'utilizzo o dall'incapacità di utilizzo degli script di esempio e della documentazione, anche nel caso in cui Microsoft sia stata avvisata della possibilità di tali danni.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-p104">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
    
## <a name="step-1-create-a-csv-file-that-contains-information-about-the-searches-you-want-to-run"></a><span data-ttu-id="a8a5f-121">Passaggio 1: creare un file CSV che contiene informazioni sulle ricerche che si desidera eseguire</span><span class="sxs-lookup"><span data-stu-id="a8a5f-121">Step 1: Create a CSV file that contains information about the searches you want to run</span></span>

<span data-ttu-id="a8a5f-122">Il file con valori delimitati da virgole (CSV) creato in questo passaggio contiene una riga per ogni utente che desidera eseguire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-122">The comma separated value (CSV) file that you create in this step contains a row for each user that want to search.</span></span> <span data-ttu-id="a8a5f-123">È possibile eseguire una ricerca nella cassetta postale di Exchange Online dell'utente (che include la cassetta postale di archiviazione, se abilitata) e il sito di OneDrive for business.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-123">You can search the user's Exchange Online mailbox (which includes the archive mailbox, if it's enabled) and their OneDrive for Business site.</span></span> <span data-ttu-id="a8a5f-124">In alternativa, è possibile cercare solo la cassetta postale o il sito di OneDrive for business.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-124">Or you can search just the mailbox or the OneDrive for Business site.</span></span> <span data-ttu-id="a8a5f-125">È inoltre possibile cercare qualsiasi sito nell'organizzazione di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-125">You can also search any site in your SharePoint Online organization.</span></span> <span data-ttu-id="a8a5f-126">Lo script eseguito nel passaggio 3 creerà una ricerca distinta per ogni riga del file CSV.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-126">The script that you run in Step 3 will create a separate search for each row in the CSV file.</span></span> 
  
1. <span data-ttu-id="a8a5f-127">Copiare e incollare il testo seguente in un file txt tramite il blocco note.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-127">Copy and paste the following text into a .txt file using NotePad.</span></span> <span data-ttu-id="a8a5f-128">Salvare il file in una cartella nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-128">Save this file to a folder on your local computer.</span></span> <span data-ttu-id="a8a5f-129">Gli altri script vengono salvati anche in questa cartella.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-129">You'll save the other scripts to this folder as well.</span></span>
    
    ```
    ExchangeLocation,SharePointLocation,ContentMatchQuery,StartDate,EndDate
    sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2000,12/31/2005
    sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2006,12/31/2010
    sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2011,3/21/2016
    ,https://contoso.sharepoint.com/sites/contoso,,,3/21/2016
    ,https://contoso-my.sharepoint.com/personal/davidl_contoso_onmicrosoft_com,,1/1/2015,
    ,https://contoso-my.sharepoint.com/personal/janets_contoso_onmicrosoft_com,,1/1/2015,
    ```

    <span data-ttu-id="a8a5f-130">La prima riga, o riga di intestazione, del file elenca i parametri che verranno utilizzati dal cmdlet **New-ComplianceSearch** (nello script nel passaggio 3) per creare nuove ricerche di contenuto.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-130">The first row, or header row, of the file lists the parameters that will be used by **New-ComplianceSearch** cmdlet (in the script in Step 3) to create a new Content Searches.</span></span> <span data-ttu-id="a8a5f-131">Ogni nome di parametro è separato da una virgola.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-131">Each parameter name is separated by a comma.</span></span> <span data-ttu-id="a8a5f-132">Verificare che non vi siano spazi nella riga di intestazione.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-132">Make sure there aren't any spaces in the header row.</span></span> <span data-ttu-id="a8a5f-133">Ogni riga sotto la riga di intestazione rappresenta i valori dei parametri per ogni ricerca.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-133">Each row under the header row represents the parameter values for each search.</span></span> <span data-ttu-id="a8a5f-134">Assicurarsi di sostituire i dati segnaposto nel file CSV con i dati effettivi.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-134">Be sure to replace the placeholder data in the CSV file with your actual data.</span></span> 
    
2. <span data-ttu-id="a8a5f-135">Aprire il file. txt in Excel e quindi utilizzare le informazioni riportate nella tabella seguente per modificare il file con le informazioni per ogni ricerca.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-135">Open the .txt file in Excel, and then use the information in the following table to edit the file with information for each search.</span></span> 
    
    |<span data-ttu-id="a8a5f-136">**Parametro**</span><span class="sxs-lookup"><span data-stu-id="a8a5f-136">**Parameter**</span></span>|<span data-ttu-id="a8a5f-137">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="a8a5f-137">**Description**</span></span>|
    |:-----|:-----|
    | `ExchangeLocation` <br/> |<span data-ttu-id="a8a5f-138">L'indirizzo SMTP della cassetta postale dell'utente.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-138">The SMTP address of the user's mailbox.</span></span>  <br/> |
    | `SharePointLocation` <br/> |<span data-ttu-id="a8a5f-139">L'URL del sito di OneDrive for business dell'utente o l'URL di qualsiasi sito nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-139">The URL for the user's OneDrive for Business site or the URL for any site in your organization.</span></span> <span data-ttu-id="a8a5f-140">Per l'URL per i siti di OneDrive for business, utilizzare questo ` https://<your organization>-my.sharepoint.com/personal/<user alias>_<your organization>_onmicrosoft_com `formato:.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-140">For the URL for OneDrive for Business sites, use this format: ` https://<your organization>-my.sharepoint.com/personal/<user alias>_<your organization>_onmicrosoft_com `.</span></span> <span data-ttu-id="a8a5f-141">Ad esempio,  `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com`.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-141">For example,  `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com`.</span></span>  <br/> |
    | `ContentMatchQuery` <br/> |<span data-ttu-id="a8a5f-142">Query di ricerca per la ricerca.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-142">The search query for the search.</span></span> <span data-ttu-id="a8a5f-143">Per ulteriori informazioni sulla creazione di una query di ricerca, vedere [keyword queries and Search Conditions for content search](keyword-queries-and-search-conditions.md).</span><span class="sxs-lookup"><span data-stu-id="a8a5f-143">For more information about creating a search query, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>  <br/> |
    | `StartDate` <br/> |<span data-ttu-id="a8a5f-144">Per la posta elettronica, la data o dopo che un messaggio è stato ricevuto da un destinatario o inviato dal mittente.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-144">For email, the date on or after a message was received by a recipient or sent by the sender.</span></span> <span data-ttu-id="a8a5f-145">Per i documenti sui siti di SharePoint o OneDrive for business, la data in cui è stato modificato l'ultima volta un documento.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-145">For documents on SharePoint or OneDrive for Business sites, the date on or after a document was last modified.</span></span>  <br/> |
    | `EndDate` <br/> |<span data-ttu-id="a8a5f-146">Per la posta elettronica, la data su o prima che un messaggio è stato inviato da un utente.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-146">For email, the date on or before a message was sent by a sent by the user.</span></span> <span data-ttu-id="a8a5f-147">Per i documenti nei siti di SharePoint o OneDrive for business, la data di inizio o di fine di un documento è stata modificata.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-147">For documents on SharePoint or OneDrive for Business sites, the date on or before a document was last modified.</span></span>  <br/> |
   
3. <span data-ttu-id="a8a5f-148">Salvare il file di Excel come file CSV in una cartella del computer locale.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-148">Save the Excel file as a CSV file to a folder on your local computer.</span></span> <span data-ttu-id="a8a5f-149">Lo script creato nel passaggio 3 utilizzerà le informazioni contenute in questo file CSV per creare le ricerche.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-149">The script that you create in Step 3 will use the information in this CSV file to create the searches.</span></span> 
  
## <a name="step-2-connect-to-security--compliance-center-powershell"></a><span data-ttu-id="a8a5f-150">Passaggio 2: connettersi a PowerShell per Centro sicurezza & Compliance</span><span class="sxs-lookup"><span data-stu-id="a8a5f-150">Step 2: Connect to Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="a8a5f-151">Il passaggio successivo consiste nel connettersi al centro di sicurezza & Compliance PowerShell per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-151">The next step is to connect to the Security & Compliance Center PowerShell for your organization.</span></span>
  
1. <span data-ttu-id="a8a5f-152">Salvare il testo seguente in un file di script di Windows PowerShell utilizzando un suffisso FileName di. ps1. ad esempio, `ConnectSCC.ps1`.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-152">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `ConnectSCC.ps1`.</span></span> <span data-ttu-id="a8a5f-153">Salvare il file nella stessa cartella in cui è stato salvato il file CSV nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-153">Save the file to the same folder that you saved the CSV file to in Step 1.</span></span>
    
    ```
    # Get login credentials 
    $UserCredential = Get-Credential 
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection 
    Import-PSSession $Session -AllowClobber -DisableNameChecking 
    $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Security & Compliance Center)" 
    ```

2. <span data-ttu-id="a8a5f-154">Nel computer locale, aprire Windows PowerShell, passare alla cartella in cui si trova lo script creato nel passaggio precedente, quindi eseguire lo script. Per esempio:</span><span class="sxs-lookup"><span data-stu-id="a8a5f-154">On your local computer, open Windows PowerShell, go to the folder where the script that you created in the previous step is located, and then run the script; for example:</span></span>
    
    ```
    .\ConnectSCC.ps1
    ```
  
## <a name="step-3-run-the-script-to-create-and-start-the-searches"></a><span data-ttu-id="a8a5f-155">Passaggio 3: eseguire lo script per creare e avviare le ricerche</span><span class="sxs-lookup"><span data-stu-id="a8a5f-155">Step 3: Run the script to create and start the searches</span></span>

<span data-ttu-id="a8a5f-156">Lo script in questo passaggio creerà una ricerca di contenuto distinta per ogni riga del file CSV creato nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-156">The script in this step will create a separate Content Search for each row in the CSV file that you created in Step 1.</span></span> <span data-ttu-id="a8a5f-157">Quando si esegue questo script, verranno richiesti due valori:</span><span class="sxs-lookup"><span data-stu-id="a8a5f-157">When you run this script, you'll be prompted for two values:</span></span>
  
- <span data-ttu-id="a8a5f-158">**ID gruppo di ricerca** -questo nome fornisce un modo semplice per organizzare le ricerche create dal file CSV.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-158">**Search Group ID** - This name provides an easy way to organize the searches that are created from the CSV file.</span></span> <span data-ttu-id="a8a5f-159">Tutte le ricerche create vengono denominate con l'ID del gruppo di ricerca e quindi viene aggiunto un numero al nome della ricerca.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-159">Each search that's created is named with the Search Group ID, and then a number is appended to the search name.</span></span> <span data-ttu-id="a8a5f-160">Ad esempio, se si immette **ContosoCase** per l'ID del gruppo di ricerca, le ricerche verranno denominate **ContosoCase_1**, **ContosoCase_2**, **ContosoCase_3**e così via.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-160">For example, if you enter **ContosoCase** for the Search Group ID, then the searches are named **ContosoCase_1**, **ContosoCase_2**, **ContosoCase_3**, and so on.</span></span> <span data-ttu-id="a8a5f-161">Si noti che il nome digitato è distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-161">Note that the name you type is case sensitive.</span></span> <span data-ttu-id="a8a5f-162">Quando si utilizza l'ID del gruppo di ricerca nel passaggio 4 e nel passaggio 5, è necessario utilizzare lo stesso caso in cui è stato creato.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-162">When you use the Search Group ID in Step 4 and Step 5, you have to use the same case as you did when you created it.</span></span> 
    
- <span data-ttu-id="a8a5f-163">**File CSV** : il nome del file CSV creato nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-163">**CSV file** - The name of the CSV file that you created in Step 1.</span></span> <span data-ttu-id="a8a5f-164">Assicurarsi di includere l'utilizzo del nome file completo, includere l'estensione del file CSV. ad esempio, `ContosoCase.csv`.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-164">Be sure to include the use the full filename, include the .csv file extension; for example,  `ContosoCase.csv`.</span></span>
    
<span data-ttu-id="a8a5f-165">Per eseguire lo script:</span><span class="sxs-lookup"><span data-stu-id="a8a5f-165">To run the script:</span></span>

1. <span data-ttu-id="a8a5f-166">Salvare il testo seguente in un file di script di Windows PowerShell utilizzando un suffisso FileName di. ps1. ad esempio, `CreateSearches.ps1`.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-166">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `CreateSearches.ps1`.</span></span> <span data-ttu-id="a8a5f-167">Salvare il file nella stessa cartella in cui sono stati salvati gli altri file.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-167">Save the file to the same folder where you saved the other files.</span></span>
    
  ```Powershell
  # Get the Search Group ID and the location of the CSV input file
  $searchGroup = Read-Host 'Search Group ID'
  $csvFile = Read-Host 'Source CSV file'
    
  # Do a quick check to make sure our group name will not collide with other searches
  $searchCounter = 1
  import-csv $csvFile |
    ForEach-Object{
    
    $searchName = $searchGroup +'_' + $searchCounter
    $search = Get-ComplianceSearch $searchName -EA SilentlyContinue
    if ($search)
    {
        Write-Error "The Search Group ID conflicts with existing searches.  Please choose a search group name and restart the script."
        return
    }
    $searchCounter++
  }
    
  $searchCounter = 1
  import-csv $csvFile |
    ForEach-Object{
    
    # Create the query
    $query = $_.ContentMatchQuery
    if(($_.StartDate -or $_.EndDate))
    {
          # Add the appropriate date restrictions.  NOTE: Using the Date condition property here because it works across Exchange, SharePoint, and OneDrive for Business.
          # For Exchange, the Date condition property maps to the Sent and Received dates; for SharePoint and OneDrive for Business, it maps to Created and Modified dates.
          if($query)
          {
              $query += " AND"
          }
          $query += " ("
          if($_.StartDate)
          {
              $query += "Date >= " + $_.StartDate
          }
          if($_.EndDate)
          {
              if($_.StartDate)
              {
                  $query += " AND "
              }
              $query += "Date <= " + $_.EndDate
          }
          $query += ")"
    }
      
      # -ExchangeLocation can't be set to an empty string, set to null if there's no location.
      $exchangeLocation = $null
      if ( $_.ExchangeLocation)
      {
           $exchangeLocation = $_.ExchangeLocation
      }
    
    # Create and run the search        
    $searchName = $searchGroup +'_' + $searchCounter
    Write-Host "Creating and running search: " $searchName -NoNewline
    $search = New-ComplianceSearch -Name $searchName -ExchangeLocation $exchangeLocation -SharePointLocation $_.SharePointLocation -ContentMatchQuery $query
    
    # Start and wait for each search to complete
    Start-ComplianceSearch $search.Name
    while ((Get-ComplianceSearch $search.Name).Status -ne "Completed")
    {
        Write-Host " ." -NoNewline
        Start-Sleep -s 3
    }
    Write-Host ""
    
    $searchCounter++
  }
  ```

2. <span data-ttu-id="a8a5f-168">In Windows PowerShell, passare alla cartella in cui è stato salvato lo script nel passaggio precedente, quindi eseguire lo script. Per esempio:</span><span class="sxs-lookup"><span data-stu-id="a8a5f-168">In Windows PowerShell, go to the folder where you saved the script in the previous step, and then run the script; for example:</span></span>
    
    ```Powershell
    .\CreateSearches.ps1
    ```

3. <span data-ttu-id="a8a5f-169">Al prompt **ID gruppo di ricerca** Digitare il nome di un gruppo di ricerca e quindi premere **invio**. ad esempio, `ContosoCase`.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-169">At the **Search Group ID** prompt, type a search group name, and then press **Enter**; for example,  `ContosoCase`.</span></span> <span data-ttu-id="a8a5f-170">Tenere presente che questo nome è distinzione tra maiuscole e minuscole, quindi sarà necessario digitarlo nello stesso modo nei passaggi successivi.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-170">Remember that this name is case sensitive, so you'll have to type it the same way in the subsequent steps.</span></span>
    
4. <span data-ttu-id="a8a5f-171">Al prompt dei **file CSV di origine** Digitare il nome del file CSV, inclusa l'estensione del file CSV. ad esempio, `ContosoCase.csv`.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-171">At the **Source CSV file** prompt, type the name of the CSV file, including the .csv file extension; for example,  `ContosoCase.csv`.</span></span>
    
5. <span data-ttu-id="a8a5f-172">Premere **invio** per continuare a eseguire lo script.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-172">Press **Enter** to continue running the script.</span></span> 
    
    <span data-ttu-id="a8a5f-173">Nello script viene visualizzato lo stato di avanzamento della creazione e dell'esecuzione delle ricerche.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-173">The script displays the progress of creating and running the searches.</span></span> <span data-ttu-id="a8a5f-174">Al termine dell'esecuzione dello script, viene restituito il prompt.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-174">When the script is complete, it returns to the prompt.</span></span> 
    
    ![Output di esempio dall’esecuzione dello script per creare ricerche di conformità multiple](media/37d59b0d-5f89-4dbc-9e2d-0e88e2ed7b4c.png)
  
## <a name="step-4-run-the-script-to-report-the-search-estimates"></a><span data-ttu-id="a8a5f-176">Passaggio 4: eseguire lo script per segnalare le stime di ricerca</span><span class="sxs-lookup"><span data-stu-id="a8a5f-176">Step 4: Run the script to report the search estimates</span></span>

<span data-ttu-id="a8a5f-177">Dopo aver creato le ricerche, il passaggio successivo consiste nell'eseguire uno script che consente di visualizzare un report semplice del numero di hit di ricerca per ogni ricerca creata al passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-177">After you create the searches, the next step is to run a script that displays a simple report of the number of search hits for each search that was created in Step 3.</span></span> <span data-ttu-id="a8a5f-178">Il report include anche le dimensioni dei risultati per ogni ricerca e il numero totale di hit e dimensioni totali di tutte le ricerche.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-178">The report also includes the size of results for each search, and the total number of hits and total size of all searches.</span></span> <span data-ttu-id="a8a5f-179">Quando si esegue lo script dei report, viene richiesto l'ID del gruppo di ricerca e un nome di file CSV Se si desidera salvare il report in un file CSV.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-179">When you run the reporting script, you'll be prompted for the Search Group ID, and a CSV filename if you want to save the report to a CSV file.</span></span>
  
1. <span data-ttu-id="a8a5f-180">Salvare il testo seguente in un file di script di Windows PowerShell utilizzando un suffisso FileName di. ps1. ad esempio, `SearchReport.ps1`.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-180">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `SearchReport.ps1`.</span></span> <span data-ttu-id="a8a5f-181">Salvare il file nella stessa cartella in cui sono stati salvati gli altri file.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-181">Save the file to the same folder where you saved the other files.</span></span>
    
  ```Powershell
  $searchGroup = Read-Host 'Search Group ID'
  $outputFile = Read-Host 'Enter a file name or file path to save the report to a .csv file. Leave blank to only display the report'
  $searches = Get-ComplianceSearch | ?{$_.Name -clike $searchGroup + "_*"}
  $allSearchStats = @()
  foreach ($partialObj in $searches)
  {
      $search = Get-ComplianceSearch $partialObj.Name
      $sizeMB = [System.Math]::Round($search.Size / 1MB, 2)
      $searchStatus = $search.Status
      if($search.Errors)
      {
          $searchStatus = "Failed"
      }elseif($search.NumFailedSources -gt 0)
      {
          $searchStatus = "Failed Sources"
      }
      $searchStats = New-Object PSObject
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name Name -Value $search.Name
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name ContentMatchQuery -Value $search.ContentMatchQuery
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name Status -Value $searchStatus
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name Items -Value $search.Items
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name "Size" -Value $search.Size
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name "Size(MB)" -Value $sizeMB
      $allSearchStats += $searchStats
  }
  # Calculate the totals
  $allItems = ($allSearchStats | Measure-Object Items -Sum).Sum
  # Convert the total size to MB and round to the nearst 100th
  $allSize = ($allSearchStats | Measure-Object 'Size' -Sum).Sum
  $allSizeMB = [System.Math]::Round($allSize  / 1MB, 2)
  # Get the total successful searches and total of all searches
  $allSuccessCount = ($allSearchStats |?{$_.Status -eq "Completed"}).Count
  $allCount = $allSearchStats.Count
  $allStatus = [string]$allSuccessCount + " of " + [string]$allCount
  # Totals Row
  $totalSearchStats = New-Object PSObject
  Add-Member -InputObject $totalSearchStats -MemberType NoteProperty -Name Name -Value "Total"
  Add-Member -InputObject $totalSearchStats -MemberType NoteProperty -Name Status -Value $allStatus
  Add-Member -InputObject $totalSearchStats -MemberType NoteProperty -Name Items -Value $allItems
  Add-Member -InputObject $totalSearchStats -MemberType NoteProperty -Name "Size(MB)" -Value $allSizeMB
  $allSearchStats += $totalSearchStats
  # Just get the columns we're interested in showing
  $allSearchStatsPrime = $allSearchStats | Select-Object Name, Status, Items, "Size(MB)", ContentMatchQuery
  # Print the results to the screen
  $allSearchStatsPrime |ft -AutoSize -Wrap
  # Save the results to a CSV file
  if ($outputFile)
  {
      $allSearchStatsPrime | Export-Csv -Path $outputFile -NoTypeInformation
  }
  ```

2. <span data-ttu-id="a8a5f-182">In Windows PowerShell, passare alla cartella in cui è stato salvato lo script nel passaggio precedente, quindi eseguire lo script. Per esempio:</span><span class="sxs-lookup"><span data-stu-id="a8a5f-182">In Windows PowerShell, go to the folder where you saved the script in the previous step, and then run the script; for example:</span></span>
    
    ```Powershell
    .\SearchReport.ps1
    ```

3. <span data-ttu-id="a8a5f-183">Al prompt **ID gruppo di ricerca** Digitare il nome di un gruppo di ricerca e quindi premere **invio**. ad esempio `ContosoCase`.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-183">At the **Search Group ID** prompt, type a search group name, and then press **Enter**; for example  `ContosoCase`.</span></span> <span data-ttu-id="a8a5f-184">Tenere presente che questo nome è distinzione tra maiuscole e minuscole, quindi sarà necessario digitarlo nello stesso modo in cui è stato eseguito lo script nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-184">Remember that this name is case sensitive, so you'll have to type it the same way you did when you ran the script in Step 3.</span></span>
    
4. <span data-ttu-id="a8a5f-185">Nel **percorso del file per salvare il report in un file CSV (lasciare vuoto solo per visualizzare il report)** , digitare il nome di un file del percorso completo (inclusa l'estensione CSV) se si desidera salvare il report in un file CSV.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-185">At the **File path to save the report to a CSV file (leave blank to just display the report)** prompt, type a file name of complete filename path (including the .csv file extension) if you want to save the report to a CSV file.</span></span> <span data-ttu-id="a8a5f-186">nome del file CSV, inclusa l'estensione del file CSV.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-186">name of the CSV file, including the .csv file extension.</span></span> <span data-ttu-id="a8a5f-187">Ad esempio, è possibile digitare `ContosoCaseReport.csv` per salvarlo nella directory corrente oppure è possibile digitare `C:\Users\admin\OneDrive for Business\ContosoCase\ContosoCaseReport.csv` per salvarlo in un'altra cartella.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-187">For example, you could type  `ContosoCaseReport.csv` to save it to the current directory or you could type  `C:\Users\admin\OneDrive for Business\ContosoCase\ContosoCaseReport.csv` to save it to a different folder.</span></span> <span data-ttu-id="a8a5f-188">È inoltre possibile lasciare il messaggio vuoto per visualizzare il report, ma non salvarlo in un file.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-188">You can also leave the prompt blank to display the report but not save it to a file.</span></span> 
    
5. <span data-ttu-id="a8a5f-189">Premere **INVIO**.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-189">Press **Enter**.</span></span>
    
    <span data-ttu-id="a8a5f-190">Nello script viene visualizzato lo stato di avanzamento della creazione e dell'esecuzione delle ricerche.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-190">The script displays the progress of creating and running the searches.</span></span> <span data-ttu-id="a8a5f-191">Al termine dello script, viene visualizzato il report.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-191">When the script is complete, the report is displayed.</span></span> 
    
    ![Eseguire il report di ricerca per visualizzare le stime per il gruppo di ricerca](media/3b5f2595-71d5-4a14-9214-fad156c981f8.png)
  
> [!NOTE]
> <span data-ttu-id="a8a5f-193">Se la stessa cassetta postale o sito è specificato come percorso di contenuto in più di una ricerca in un gruppo di ricerca, la stima complessiva dei risultati nel rapporto (sia per il numero di elementi che per la dimensione totale) potrebbe includere i risultati per gli stessi elementi.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-193">If the same mailbox or site is specified as a content location in more than one search in a search group, the total results estimate in the report (for both the number of items and the total size) might include results for the same items.</span></span> <span data-ttu-id="a8a5f-194">Ciò è dovuto al fatto che lo stesso messaggio di posta elettronica o documento verrà conteggiato più di una volta se corrisponde alla query per ricerche diverse nel gruppo di ricerca.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-194">That's because the same email message or document will be counted more than once if it matches the query for different searches in the search group.</span></span> 
  
## <a name="step-5-run-the-script-to-delete-the-searches"></a><span data-ttu-id="a8a5f-195">Passaggio 5: eseguire lo script per eliminare le ricerche</span><span class="sxs-lookup"><span data-stu-id="a8a5f-195">Step 5: Run the script to delete the searches</span></span>

<span data-ttu-id="a8a5f-196">Poiché potrebbe essere la creazione di un sacco di ricerche, questo ultimo script rende semplice eliminare rapidamente le ricerche create nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-196">Because you might be creating a lot of searches, this last script just makes it easy to quickly delete the searches you created in Step 3.</span></span> <span data-ttu-id="a8a5f-197">Come gli altri script, questo richiede anche l'ID del gruppo di ricerca.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-197">Like the other scripts, this one also prompts you for the Search Group ID.</span></span> <span data-ttu-id="a8a5f-198">Tutte le ricerche con l'ID del gruppo di ricerca nel nome della ricerca verranno eliminate quando si esegue questo script.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-198">All searches with the Search Group ID in the search name will be deleted when you run this script.</span></span> 
  
1. <span data-ttu-id="a8a5f-199">Salvare il testo seguente in un file di script di Windows PowerShell utilizzando un suffisso FileName di. ps1. ad esempio, `DeleteSearches.ps1`.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-199">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `DeleteSearches.ps1`.</span></span> <span data-ttu-id="a8a5f-200">Salvare il file nella stessa cartella in cui sono stati salvati gli altri file.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-200">Save the file to the same folder where you saved the other files.</span></span>
    
  ```Powershell
  # Delete all searches in a search group
  $searchGroup = Read-Host 'Search Group ID'
  Get-ComplianceSearch |
      ForEach-Object{
      # If the name matches the search group name pattern (case sensitive), delete the search
      if ($_.Name -cmatch $searchGroup + "_\d+")
      {
          Write-Host "Deleting search: " $_.Name
          Remove-ComplianceSearch $_.Name -Confirm:$false
      }
  }
  ```

2. <span data-ttu-id="a8a5f-201">In Windows PowerShell, passare alla cartella in cui è stato salvato lo script nel passaggio precedente, quindi eseguire lo script. Per esempio:</span><span class="sxs-lookup"><span data-stu-id="a8a5f-201">In Windows PowerShell, go to the folder where you saved the script in the previous step, and then run the script; for example:</span></span>
    
    ```Powershell
    .\DeleteSearches.ps1
    ```

3. <span data-ttu-id="a8a5f-202">Al prompt **ID gruppo di ricerca** Digitare il nome di un gruppo di ricerca per le ricerche che si desidera eliminare e quindi premere **invio**. ad esempio, `ContosoCase`.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-202">At the **Search Group ID** prompt, type a search group name for the searches that you want to delete, and then press **Enter**; for example,  `ContosoCase`.</span></span> <span data-ttu-id="a8a5f-203">Tenere presente che questo nome è distinzione tra maiuscole e minuscole, quindi sarà necessario digitarlo nello stesso modo in cui è stato eseguito lo script nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-203">Remember that this name is case sensitive, so you'll have to type it the same way you did when you ran the script in Step 3.</span></span>
    
    <span data-ttu-id="a8a5f-204">Nello script viene visualizzato il nome di ogni ricerca che viene eliminata.</span><span class="sxs-lookup"><span data-stu-id="a8a5f-204">The script displays the name of each search that's deleted.</span></span>
    
    ![Eseguire lo script per eliminare le ricerche nel gruppo di ricerca](media/9d97b9d6-a539-4d9b-a4e4-e99989144ec7.png)
