---
title: Creare, analizzare ed eliminare più ricerche di contenuto
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
- SPO160
- MOE150
- MET150
ms.assetid: 1d463dda-a3b5-4675-95d4-83db19c9c4a3
description: Informazioni su come automatizzare le attività di Ricerca contenuto, ad esempio la creazione di ricerche e l'esecuzione di report tramite script di PowerShell nel Centro sicurezza & conformità in Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c467b8ebc5ad3171347b23cad47f563b3634ee29
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546862"
---
# <a name="create-report-on-and-delete-multiple-content-searches"></a><span data-ttu-id="89c66-103">Creare, analizzare ed eliminare più ricerche di contenuto</span><span class="sxs-lookup"><span data-stu-id="89c66-103">Create, report on, and delete multiple Content Searches</span></span>

 <span data-ttu-id="89c66-104">La creazione rapida di ricerche di individuazione e la creazione di report è spesso un passaggio importante in eDiscovery e nelle indagini quando si prova a conoscere i dati sottostanti e la qualità e la qualità delle ricerche.</span><span class="sxs-lookup"><span data-stu-id="89c66-104">Quickly creating and reporting discovery searches is often an important step in eDiscovery and investigations when you're trying to learn about the underlying data, and the richness and quality of your searches.</span></span> <span data-ttu-id="89c66-105">A tale scopo, PowerShell per Centro sicurezza & conformità offre una serie di cmdlet per automatizzare le attività di Ricerca contenuto che richiedono molto tempo.</span><span class="sxs-lookup"><span data-stu-id="89c66-105">To help you do this, the Security & Compliance Center PowerShell offers a set of cmdlets to automate time-consuming Content Search tasks.</span></span> <span data-ttu-id="89c66-106">Questi script forniscono un modo semplice e rapido per creare una serie di ricerche e quindi eseguire report dei risultati di ricerca stimati che consentono di determinare la quantità di dati in questione.</span><span class="sxs-lookup"><span data-stu-id="89c66-106">These scripts provide a quick and easy way to create a number of searches, and then run reports of the estimated search results that can help you determine the quantity of data in question.</span></span> <span data-ttu-id="89c66-107">È inoltre possibile utilizzare gli script per creare versioni diverse delle ricerche per confrontare i risultati prodotti da ognuno di essi.</span><span class="sxs-lookup"><span data-stu-id="89c66-107">You can also use the scripts to create different versions of searches to compare the results each one produces.</span></span> <span data-ttu-id="89c66-108">Questi script consentono di identificare e rimuovere i dati in modo rapido ed efficiente.</span><span class="sxs-lookup"><span data-stu-id="89c66-108">These scripts can help you to quickly and efficiently identify and cull your data.</span></span>

## <a name="before-you-create-a-content-search"></a><span data-ttu-id="89c66-109">Prima di creare una ricerca di contenuto</span><span class="sxs-lookup"><span data-stu-id="89c66-109">Before you create a Content Search</span></span>

- <span data-ttu-id="89c66-110">Per eseguire gli script descritti in questo argomento, è necessario essere membri del gruppo di ruoli Gestore di eDiscovery nel Centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="89c66-110">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center to run the scripts that are described in this topic.</span></span>

- <span data-ttu-id="89c66-111">Per raccogliere un elenco degli URL per i siti di OneDrive for Business nell'organizzazione che è possibile aggiungere al file CSV nel passaggio 1, vedere Creare un elenco di tutti i percorsi di [OneDrive nell'organizzazione.](https://docs.microsoft.com/onedrive/list-onedrive-urls)</span><span class="sxs-lookup"><span data-stu-id="89c66-111">To collect a list of the URLs for the OneDrive for Business sites in your organization that you can add to the CSV file in Step 1, see [Create a list of all OneDrive locations in your organization](https://docs.microsoft.com/onedrive/list-onedrive-urls).</span></span>

- <span data-ttu-id="89c66-112">Assicurarsi di salvare tutti i file creati in questo argomento nella stessa cartella.</span><span class="sxs-lookup"><span data-stu-id="89c66-112">Be sure to save all the files that you create in this topic to the same folder.</span></span> <span data-ttu-id="89c66-113">In questo modo sarà più semplice eseguire gli script.</span><span class="sxs-lookup"><span data-stu-id="89c66-113">That will make it easier to run the scripts.</span></span>

- <span data-ttu-id="89c66-114">Gli script includono una gestione degli errori minima.</span><span class="sxs-lookup"><span data-stu-id="89c66-114">The scripts include minimal error handling.</span></span> <span data-ttu-id="89c66-115">Il loro scopo principale è creare rapidamente, creare report ed eliminare più ricerche di contenuto.</span><span class="sxs-lookup"><span data-stu-id="89c66-115">Their primary purpose is to quickly create, report on, and delete multiple Content Searches.</span></span>

- <span data-ttu-id="89c66-p104">Gli script di esempio forniti in questo articolo non sono supportati da alcun programma o servizio standard di supporto Microsoft. Gli script di esempio sono forniti così come sono senza alcun tipo di garanzia. Inoltre Microsoft declina ogni responsabilità su garanzie implicite, senza alcuna limitazione, incluse le garanzie implicite di commerciabilità e/o adeguatezza per uno scopo specifico. Qualsiasi rischio eventuale pervenga, durante l'utilizzo degli script di esempio e della documentazione, si intende a carico dell'utente. In nessun caso Microsoft, i suoi autori o chiunque altro coinvolto nella creazione, produzione o consegna degli script è da ritenersi responsabile per qualsiasi danno eventuale (inclusi, senza limitazione alcuna, danni riguardanti profitti aziendali, interruzione di attività, perdita di informazioni aziendali o altra perdita pecuniaria) derivanti dall'utilizzo o dall'incapacità di utilizzo degli script di esempio e della documentazione, anche nel caso in cui Microsoft sia stata avvisata della possibilità di tali danni.</span><span class="sxs-lookup"><span data-stu-id="89c66-p104">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>

## <a name="step-1-create-a-csv-file-that-contains-information-about-the-searches-you-want-to-run"></a><span data-ttu-id="89c66-121">Passaggio 1: Creare un file CSV contenente informazioni sulle ricerche che si desidera eseguire</span><span class="sxs-lookup"><span data-stu-id="89c66-121">Step 1: Create a CSV file that contains information about the searches you want to run</span></span>

<span data-ttu-id="89c66-122">Il file con valori delimitati da virgole (CSV) creato in questo passaggio contiene una riga per ogni utente che desidera eseguire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="89c66-122">The comma separated value (CSV) file that you create in this step contains a row for each user that want to search.</span></span> <span data-ttu-id="89c66-123">È possibile eseguire ricerche nella cassetta postale di Exchange Online dell'utente (che include la cassetta postale di archiviazione, se abilitata) e nel sito di OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="89c66-123">You can search the user's Exchange Online mailbox (which includes the archive mailbox, if it's enabled) and their OneDrive for Business site.</span></span> <span data-ttu-id="89c66-124">Oppure è possibile eseguire una ricerca solo nella cassetta postale o nel sito di OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="89c66-124">Or you can search just the mailbox or the OneDrive for Business site.</span></span> <span data-ttu-id="89c66-125">È inoltre possibile eseguire ricerche in qualsiasi sito dell'organizzazione di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="89c66-125">You can also search any site in your SharePoint Online organization.</span></span> <span data-ttu-id="89c66-126">Lo script eseguito nel passaggio 3 creerà una ricerca separata per ogni riga nel file CSV.</span><span class="sxs-lookup"><span data-stu-id="89c66-126">The script that you run in Step 3 will create a separate search for each row in the CSV file.</span></span>

1. <span data-ttu-id="89c66-127">Copia e incolla il testo seguente in un file txt usando NotePad.</span><span class="sxs-lookup"><span data-stu-id="89c66-127">Copy and paste the following text into a .txt file using NotePad.</span></span> <span data-ttu-id="89c66-128">Salvare il file in una cartella nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="89c66-128">Save this file to a folder on your local computer.</span></span> <span data-ttu-id="89c66-129">Anche gli altri script verranno salvate in questa cartella.</span><span class="sxs-lookup"><span data-stu-id="89c66-129">You'll save the other scripts to this folder as well.</span></span>

   ```text
   ExchangeLocation,SharePointLocation,ContentMatchQuery,StartDate,EndDate
   sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2000,12/31/2005
   sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2006,12/31/2010
   sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2011,3/21/2016
   ,https://contoso.sharepoint.com/sites/contoso,,,3/21/2016
   ,https://contoso-my.sharepoint.com/personal/davidl_contoso_onmicrosoft_com,,1/1/2015,
   ,https://contoso-my.sharepoint.com/personal/janets_contoso_onmicrosoft_com,,1/1/2015,
   ```

   <span data-ttu-id="89c66-130">Nella prima riga, o riga di intestazione, del file sono elencati i parametri che verranno utilizzati dal cmdlet **New-ComplianceSearch** (nello script nel passaggio 3) per creare una nuova ricerca di contenuto.</span><span class="sxs-lookup"><span data-stu-id="89c66-130">The first row, or header row, of the file lists the parameters that will be used by **New-ComplianceSearch** cmdlet (in the script in Step 3) to create a new Content Searches.</span></span> <span data-ttu-id="89c66-131">Ogni nome di parametro è separato da una virgola.</span><span class="sxs-lookup"><span data-stu-id="89c66-131">Each parameter name is separated by a comma.</span></span> <span data-ttu-id="89c66-132">Assicurati che non siano presenti spazi nella riga di intestazione.</span><span class="sxs-lookup"><span data-stu-id="89c66-132">Make sure there aren't any spaces in the header row.</span></span> <span data-ttu-id="89c66-133">Ogni riga sotto la riga di intestazione rappresenta i valori dei parametri per ogni ricerca.</span><span class="sxs-lookup"><span data-stu-id="89c66-133">Each row under the header row represents the parameter values for each search.</span></span> <span data-ttu-id="89c66-134">Assicurarsi di sostituire i dati segnaposto nel file CSV con i dati effettivi.</span><span class="sxs-lookup"><span data-stu-id="89c66-134">Be sure to replace the placeholder data in the CSV file with your actual data.</span></span>

2. <span data-ttu-id="89c66-135">Aprire il file txt in Excel e quindi utilizzare le informazioni nella tabella seguente per modificare il file con le informazioni per ogni ricerca.</span><span class="sxs-lookup"><span data-stu-id="89c66-135">Open the .txt file in Excel, and then use the information in the following table to edit the file with information for each search.</span></span>

   ****

   |<span data-ttu-id="89c66-136">Parametro</span><span class="sxs-lookup"><span data-stu-id="89c66-136">Parameter</span></span>|<span data-ttu-id="89c66-137">Descrizione</span><span class="sxs-lookup"><span data-stu-id="89c66-137">Description</span></span>|
   |---|---|
   |`ExchangeLocation`|<span data-ttu-id="89c66-138">Indirizzo SMTP della cassetta postale dell'utente.</span><span class="sxs-lookup"><span data-stu-id="89c66-138">The SMTP address of the user's mailbox.</span></span>|
   |`SharePointLocation`|<span data-ttu-id="89c66-139">L'URL del sito di OneDrive for Business dell'utente o l'URL di qualsiasi sito dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="89c66-139">The URL for the user's OneDrive for Business site or the URL for any site in your organization.</span></span> <span data-ttu-id="89c66-140">Per l'URL dei siti di OneDrive for Business, utilizzare questo formato: ` https://<your organization>-my.sharepoint.com/personal/<user alias>_<your organization>_onmicrosoft_com ` .</span><span class="sxs-lookup"><span data-stu-id="89c66-140">For the URL for OneDrive for Business sites, use this format: ` https://<your organization>-my.sharepoint.com/personal/<user alias>_<your organization>_onmicrosoft_com `.</span></span> <span data-ttu-id="89c66-141">Ad esempio,  `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com`.</span><span class="sxs-lookup"><span data-stu-id="89c66-141">For example,  `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com`.</span></span>|
   |`ContentMatchQuery`|<span data-ttu-id="89c66-142">Query di ricerca per la ricerca.</span><span class="sxs-lookup"><span data-stu-id="89c66-142">The search query for the search.</span></span> <span data-ttu-id="89c66-143">Per ulteriori informazioni sulla creazione di una query di ricerca, vedere Query con parole [chiave e condizioni di ricerca per Ricerca contenuto.](keyword-queries-and-search-conditions.md)</span><span class="sxs-lookup"><span data-stu-id="89c66-143">For more information about creating a search query, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>|
   |`StartDate`|<span data-ttu-id="89c66-144">Per la posta elettronica, la data in cui un messaggio è stato ricevuto da un destinatario o inviato dal mittente.</span><span class="sxs-lookup"><span data-stu-id="89c66-144">For email, the date on or after a message was received by a recipient or sent by the sender.</span></span> <span data-ttu-id="89c66-145">Per i documenti nei siti di SharePoint o OneDrive for Business, la data in cui un documento è stato modificato per l'ultima volta o dopo l'ultima modifica.</span><span class="sxs-lookup"><span data-stu-id="89c66-145">For documents on SharePoint or OneDrive for Business sites, the date on or after a document was last modified.</span></span>|
   |`EndDate`|<span data-ttu-id="89c66-146">Per la posta elettronica, la data in cui un messaggio è stato inviato dall'utente o prima di quello precedente.</span><span class="sxs-lookup"><span data-stu-id="89c66-146">For email, the date on or before a message was sent by a sent by the user.</span></span> <span data-ttu-id="89c66-147">Per i documenti nei siti di SharePoint o OneDrive for Business, la data dell'ultima modifica di un documento o prima di quella precedente.</span><span class="sxs-lookup"><span data-stu-id="89c66-147">For documents on SharePoint or OneDrive for Business sites, the date on or before a document was last modified.</span></span>|
   |

3. <span data-ttu-id="89c66-148">Salvare il file di Excel come file CSV in una cartella nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="89c66-148">Save the Excel file as a CSV file to a folder on your local computer.</span></span> <span data-ttu-id="89c66-149">Lo script creato nel passaggio 3 utilizzerà le informazioni in questo file CSV per creare le ricerche.</span><span class="sxs-lookup"><span data-stu-id="89c66-149">The script that you create in Step 3 will use the information in this CSV file to create the searches.</span></span>

## <a name="step-2-connect-to-security--compliance-center-powershell"></a><span data-ttu-id="89c66-150">Passaggio 2: Connettersi a PowerShell in Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="89c66-150">Step 2: Connect to Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="89c66-151">Il passaggio successivo consiste nel connettersi a PowerShell in Centro sicurezza e conformità per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="89c66-151">The next step is to connect to Security & Compliance Center PowerShell for your organization.</span></span> <span data-ttu-id="89c66-152">Per ottenere istruzioni dettagliate, vedere [Connettersi a PowerShell in Centro sicurezza e conformità](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="89c66-152">For step-by-step instructions, see [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

## <a name="step-3-run-the-script-to-create-and-start-the-searches"></a><span data-ttu-id="89c66-153">Passaggio 3: Eseguire lo script per creare e avviare le ricerche</span><span class="sxs-lookup"><span data-stu-id="89c66-153">Step 3: Run the script to create and start the searches</span></span>

<span data-ttu-id="89c66-154">Lo script di questo passaggio creerà una ricerca contenuto separata per ogni riga del file CSV creato nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="89c66-154">The script in this step will create a separate Content Search for each row in the CSV file that you created in Step 1.</span></span> <span data-ttu-id="89c66-155">Quando si esegue questo script, verrà richiesto di immettere due valori:</span><span class="sxs-lookup"><span data-stu-id="89c66-155">When you run this script, you'll be prompted for two values:</span></span>

- <span data-ttu-id="89c66-156">**ID gruppo di** ricerca: questo nome consente di organizzare in modo semplice le ricerche create dal file CSV.</span><span class="sxs-lookup"><span data-stu-id="89c66-156">**Search Group ID** - This name provides an easy way to organize the searches that are created from the CSV file.</span></span> <span data-ttu-id="89c66-157">Ogni ricerca creata viene denominata con l'ID del gruppo di ricerca e quindi viene aggiunto un numero al nome della ricerca.</span><span class="sxs-lookup"><span data-stu-id="89c66-157">Each search that's created is named with the Search Group ID, and then a number is appended to the search name.</span></span> <span data-ttu-id="89c66-158">Ad esempio, se si immette **ContosoCase** come ID gruppo di ricerca, le ricerche vengono denominate **ContosoCase_1,** **ContosoCase_2,** **ContosoCase_3** e così via.</span><span class="sxs-lookup"><span data-stu-id="89c66-158">For example, if you enter **ContosoCase** for the Search Group ID, then the searches are named **ContosoCase_1**, **ContosoCase_2**, **ContosoCase_3**, and so on.</span></span> <span data-ttu-id="89c66-159">Si noti che per il nome digitato viene distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="89c66-159">Note that the name you type is case sensitive.</span></span> <span data-ttu-id="89c66-160">Quando si utilizza l'ID gruppo di ricerca nei passaggi 4 e 5, è necessario utilizzare lo stesso caso utilizzato al momento della creazione.</span><span class="sxs-lookup"><span data-stu-id="89c66-160">When you use the Search Group ID in Step 4 and Step 5, you have to use the same case as you did when you created it.</span></span>

- <span data-ttu-id="89c66-161">**File CSV** - Nome del file CSV creato nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="89c66-161">**CSV file** - The name of the CSV file that you created in Step 1.</span></span> <span data-ttu-id="89c66-162">Assicurarsi di includere il nome di file completo, includere l'estensione del file CSV. ad esempio  `ContosoCase.csv` .</span><span class="sxs-lookup"><span data-stu-id="89c66-162">Be sure to include the use the full filename, include the .csv file extension; for example,  `ContosoCase.csv`.</span></span>

<span data-ttu-id="89c66-163">Per eseguire lo script:</span><span class="sxs-lookup"><span data-stu-id="89c66-163">To run the script:</span></span>

1. <span data-ttu-id="89c66-164">Salvare il testo seguente in un file Windows PowerShell script utilizzando il suffisso del nome file ps1. ad esempio `CreateSearches.ps1` .</span><span class="sxs-lookup"><span data-stu-id="89c66-164">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `CreateSearches.ps1`.</span></span> <span data-ttu-id="89c66-165">Salvare il file nella stessa cartella in cui sono stati salvati gli altri file.</span><span class="sxs-lookup"><span data-stu-id="89c66-165">Save the file to the same folder where you saved the other files.</span></span>

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

2. <span data-ttu-id="89c66-166">In Windows PowerShell, passare alla cartella in cui è stato salvato lo script nel passaggio precedente ed eseguire lo script; Per esempio:</span><span class="sxs-lookup"><span data-stu-id="89c66-166">In Windows PowerShell, go to the folder where you saved the script in the previous step, and then run the script; for example:</span></span>

   ```Powershell
   .\CreateSearches.ps1
   ```

3. <span data-ttu-id="89c66-167">Al prompt **ID gruppo** di ricerca digitare il nome di un gruppo di ricerca e quindi premere **INVIO.** ad esempio  `ContosoCase` .</span><span class="sxs-lookup"><span data-stu-id="89c66-167">At the **Search Group ID** prompt, type a search group name, and then press **Enter**; for example,  `ContosoCase`.</span></span> <span data-ttu-id="89c66-168">Ricorda che questo nome fa distinzione tra maiuscole e minuscole, quindi dovrai digitarlo allo stesso modo nei passaggi successivi.</span><span class="sxs-lookup"><span data-stu-id="89c66-168">Remember that this name is case sensitive, so you'll have to type it the same way in the subsequent steps.</span></span>

4. <span data-ttu-id="89c66-169">Al prompt **dei file CSV di** origine digitare il nome del file CSV, inclusa l'estensione del file CSV. ad esempio  `ContosoCase.csv` .</span><span class="sxs-lookup"><span data-stu-id="89c66-169">At the **Source CSV file** prompt, type the name of the CSV file, including the .csv file extension; for example,  `ContosoCase.csv`.</span></span>

5. <span data-ttu-id="89c66-170">Premere **INVIO** per continuare a eseguire lo script.</span><span class="sxs-lookup"><span data-stu-id="89c66-170">Press **Enter** to continue running the script.</span></span>

   <span data-ttu-id="89c66-171">Lo script visualizza lo stato di avanzamento della creazione e dell'esecuzione delle ricerche.</span><span class="sxs-lookup"><span data-stu-id="89c66-171">The script displays the progress of creating and running the searches.</span></span> <span data-ttu-id="89c66-172">Una volta completato, lo script torna al prompt.</span><span class="sxs-lookup"><span data-stu-id="89c66-172">When the script is complete, it returns to the prompt.</span></span>

   ![Output di esempio dall’esecuzione dello script per creare ricerche di conformità multiple](../media/37d59b0d-5f89-4dbc-9e2d-0e88e2ed7b4c.png)

## <a name="step-4-run-the-script-to-report-the-search-estimates"></a><span data-ttu-id="89c66-174">Passaggio 4: Eseguire lo script per segnalare le stime della ricerca</span><span class="sxs-lookup"><span data-stu-id="89c66-174">Step 4: Run the script to report the search estimates</span></span>

<span data-ttu-id="89c66-175">Dopo aver creato le ricerche, il passaggio successivo consiste nell'eseguire uno script che visualizza un semplice report del numero di risultati della ricerca per ogni ricerca creata nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="89c66-175">After you create the searches, the next step is to run a script that displays a simple report of the number of search hits for each search that was created in Step 3.</span></span> <span data-ttu-id="89c66-176">Il report include anche le dimensioni dei risultati per ogni ricerca e il numero totale di riscontri e le dimensioni totali di tutte le ricerche.</span><span class="sxs-lookup"><span data-stu-id="89c66-176">The report also includes the size of results for each search, and the total number of hits and total size of all searches.</span></span> <span data-ttu-id="89c66-177">Quando si esegue lo script di creazione dei report, verranno chieti l'ID del gruppo di ricerca e un nome file CSV se si desidera salvare il report in un file CSV.</span><span class="sxs-lookup"><span data-stu-id="89c66-177">When you run the reporting script, you'll be prompted for the Search Group ID, and a CSV filename if you want to save the report to a CSV file.</span></span>

1. <span data-ttu-id="89c66-178">Salvare il testo seguente in un file Windows PowerShell script utilizzando il suffisso del nome file ps1. ad esempio `SearchReport.ps1` .</span><span class="sxs-lookup"><span data-stu-id="89c66-178">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `SearchReport.ps1`.</span></span> <span data-ttu-id="89c66-179">Salvare il file nella stessa cartella in cui sono stati salvati gli altri file.</span><span class="sxs-lookup"><span data-stu-id="89c66-179">Save the file to the same folder where you saved the other files.</span></span>

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

2. <span data-ttu-id="89c66-180">In Windows PowerShell, passare alla cartella in cui è stato salvato lo script nel passaggio precedente ed eseguire lo script; Per esempio:</span><span class="sxs-lookup"><span data-stu-id="89c66-180">In Windows PowerShell, go to the folder where you saved the script in the previous step, and then run the script; for example:</span></span>

   ```Powershell
   .\SearchReport.ps1
   ```

3. <span data-ttu-id="89c66-181">Al prompt **ID gruppo** di ricerca digitare il nome di un gruppo di ricerca e quindi premere **INVIO.** ad esempio  `ContosoCase` .</span><span class="sxs-lookup"><span data-stu-id="89c66-181">At the **Search Group ID** prompt, type a search group name, and then press **Enter**; for example  `ContosoCase`.</span></span> <span data-ttu-id="89c66-182">Ricorda che questo nome fa distinzione tra maiuscole e minuscole, quindi dovrai digitarlo nello stesso modo in cui hai eseguito lo script nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="89c66-182">Remember that this name is case sensitive, so you'll have to type it the same way you did when you ran the script in Step 3.</span></span>

4. <span data-ttu-id="89c66-183">At the **File path to save the report to a CSV file (leave blank to just display the report) prompt,** type a file name of complete filename path (including the .csv file extension) if you want to save the report to a CSV file.</span><span class="sxs-lookup"><span data-stu-id="89c66-183">At the **File path to save the report to a CSV file (leave blank to just display the report)** prompt, type a file name of complete filename path (including the .csv file extension) if you want to save the report to a CSV file.</span></span> <span data-ttu-id="89c66-184">nome del file CSV, inclusa l'estensione del file CSV.</span><span class="sxs-lookup"><span data-stu-id="89c66-184">name of the CSV file, including the .csv file extension.</span></span> <span data-ttu-id="89c66-185">Ad esempio, è possibile digitare per salvarlo nella directory corrente oppure digitare per  `ContosoCaseReport.csv`  `C:\Users\admin\OneDrive for Business\ContosoCase\ContosoCaseReport.csv` salvarlo in un'altra cartella.</span><span class="sxs-lookup"><span data-stu-id="89c66-185">For example, you could type  `ContosoCaseReport.csv` to save it to the current directory or you could type  `C:\Users\admin\OneDrive for Business\ContosoCase\ContosoCaseReport.csv` to save it to a different folder.</span></span> <span data-ttu-id="89c66-186">È inoltre possibile lasciare vuoto il prompt per visualizzare il report ma non salvarlo in un file.</span><span class="sxs-lookup"><span data-stu-id="89c66-186">You can also leave the prompt blank to display the report but not save it to a file.</span></span>

5. <span data-ttu-id="89c66-187">Premere **INVIO**.</span><span class="sxs-lookup"><span data-stu-id="89c66-187">Press **Enter**.</span></span>

   <span data-ttu-id="89c66-188">Lo script visualizza lo stato di avanzamento della creazione e dell'esecuzione delle ricerche.</span><span class="sxs-lookup"><span data-stu-id="89c66-188">The script displays the progress of creating and running the searches.</span></span> <span data-ttu-id="89c66-189">Al termine dello script, viene visualizzato il report.</span><span class="sxs-lookup"><span data-stu-id="89c66-189">When the script is complete, the report is displayed.</span></span>

   ![Eseguire il report di ricerca per visualizzare le stime per il gruppo di ricerca](../media/3b5f2595-71d5-4a14-9214-fad156c981f8.png)

> [!NOTE]
> <span data-ttu-id="89c66-191">Se la stessa cassetta postale o sito viene specificata come posizione del contenuto in più ricerche in un gruppo di ricerca, la stima totale dei risultati nel rapporto (sia per il numero di elementi che per le dimensioni totali) potrebbe includere i risultati per gli stessi elementi.</span><span class="sxs-lookup"><span data-stu-id="89c66-191">If the same mailbox or site is specified as a content location in more than one search in a search group, the total results estimate in the report (for both the number of items and the total size) might include results for the same items.</span></span> <span data-ttu-id="89c66-192">Questo perché lo stesso messaggio o documento di posta elettronica verrà conteggiato più volte se corrisponde alla query per ricerche diverse nel gruppo di ricerca.</span><span class="sxs-lookup"><span data-stu-id="89c66-192">That's because the same email message or document will be counted more than once if it matches the query for different searches in the search group.</span></span>

## <a name="step-5-run-the-script-to-delete-the-searches"></a><span data-ttu-id="89c66-193">Passaggio 5: Eseguire lo script per eliminare le ricerche</span><span class="sxs-lookup"><span data-stu-id="89c66-193">Step 5: Run the script to delete the searches</span></span>

<span data-ttu-id="89c66-194">Poiché è possibile che si creino molte ricerche, questo ultimo script semplifica semplicemente l'eliminazione rapida delle ricerche create nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="89c66-194">Because you might be creating a lot of searches, this last script just makes it easy to quickly delete the searches you created in Step 3.</span></span> <span data-ttu-id="89c66-195">Come gli altri script, anche questo richiede l'ID del gruppo di ricerca.</span><span class="sxs-lookup"><span data-stu-id="89c66-195">Like the other scripts, this one also prompts you for the Search Group ID.</span></span> <span data-ttu-id="89c66-196">Tutte le ricerche con l'ID del gruppo di ricerca nel nome della ricerca verranno eliminate quando si esegue questo script.</span><span class="sxs-lookup"><span data-stu-id="89c66-196">All searches with the Search Group ID in the search name will be deleted when you run this script.</span></span>

1. <span data-ttu-id="89c66-197">Salvare il testo seguente in un file Windows PowerShell script utilizzando il suffisso del nome file ps1. ad esempio `DeleteSearches.ps1` .</span><span class="sxs-lookup"><span data-stu-id="89c66-197">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `DeleteSearches.ps1`.</span></span> <span data-ttu-id="89c66-198">Salvare il file nella stessa cartella in cui sono stati salvati gli altri file.</span><span class="sxs-lookup"><span data-stu-id="89c66-198">Save the file to the same folder where you saved the other files.</span></span>

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

2. <span data-ttu-id="89c66-199">In Windows PowerShell, passare alla cartella in cui è stato salvato lo script nel passaggio precedente ed eseguire lo script; Per esempio:</span><span class="sxs-lookup"><span data-stu-id="89c66-199">In Windows PowerShell, go to the folder where you saved the script in the previous step, and then run the script; for example:</span></span>

   ```Powershell
   .\DeleteSearches.ps1
   ```

3. <span data-ttu-id="89c66-200">Al prompt **ID gruppo** di ricerca digitare il nome di un gruppo di ricerca per le ricerche che si desidera eliminare e quindi premere **INVIO.** ad esempio  `ContosoCase` .</span><span class="sxs-lookup"><span data-stu-id="89c66-200">At the **Search Group ID** prompt, type a search group name for the searches that you want to delete, and then press **Enter**; for example,  `ContosoCase`.</span></span> <span data-ttu-id="89c66-201">Ricorda che questo nome fa distinzione tra maiuscole e minuscole, quindi dovrai digitarlo nello stesso modo in cui hai eseguito lo script nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="89c66-201">Remember that this name is case sensitive, so you'll have to type it the same way you did when you ran the script in Step 3.</span></span>

   <span data-ttu-id="89c66-202">Lo script visualizza il nome di ogni ricerca eliminata.</span><span class="sxs-lookup"><span data-stu-id="89c66-202">The script displays the name of each search that's deleted.</span></span>

   ![Eseguire lo script per eliminare le ricerche nel gruppo di ricerca](../media/9d97b9d6-a539-4d9b-a4e4-e99989144ec7.png)
