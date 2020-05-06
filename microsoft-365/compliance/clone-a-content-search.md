---
title: Clonare una ricerca contenuto
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 4/26/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 7b40eeaa-544c-4534-b89b-9f79998e374c
ms.custom:
- seo-marvel-apr2020
description: Utilizzare lo script di Windows PowerShell in questo articolo per clonare rapidamente una ricerca di contenuto esistente nel centro conformità di Office 365 o Microsoft 365.
ms.openlocfilehash: 013a3cd04b665e1da800638a2335adb034878a4a
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035648"
---
# <a name="clone-a-content-search"></a><span data-ttu-id="504cc-103">Clonare una ricerca contenuto</span><span class="sxs-lookup"><span data-stu-id="504cc-103">Clone a Content Search</span></span>

<span data-ttu-id="504cc-104">Creazione di una ricerca contenuto nel centro conformità di Office 365 o Microsoft 365 che consente di eseguire ricerche in molte cassette postali o in siti di SharePoint e OneDrive for business può richiedere un po' di tempo.</span><span class="sxs-lookup"><span data-stu-id="504cc-104">Creating a Content Search in the compliance center in Office 365 or Microsoft 365 that searches many mailboxes or SharePoint and OneDrive for Business sites can take a while.</span></span> <span data-ttu-id="504cc-105">La specifica dei siti da cercare può anche essere soggetta a errori se si digita un URL in modo improprio.</span><span class="sxs-lookup"><span data-stu-id="504cc-105">Specifying the sites to search can also be prone to errors if you mistype a URL.</span></span> <span data-ttu-id="504cc-106">Per evitare questi problemi, è possibile utilizzare lo script di Windows PowerShell in questo articolo per clonare rapidamente una ricerca di contenuto esistente.</span><span class="sxs-lookup"><span data-stu-id="504cc-106">To avoid these issues, you can use the Windows PowerShell script in this article to quickly clone an existing Content Search.</span></span> <span data-ttu-id="504cc-107">Quando si clona una ricerca, viene creata una nuova ricerca, con un nome diverso, che contiene le stesse proprietà, ad esempio i percorsi di contenuto e la query di ricerca, come ricerca originale.</span><span class="sxs-lookup"><span data-stu-id="504cc-107">When you clone a search, a new search (with a different name) is created that contains the same properties (such as the content locations and the search query) as the original search.</span></span> <span data-ttu-id="504cc-108">È quindi possibile modificare la nuova ricerca modificando la query di parole chiave o l'intervallo di date ed eseguirlo.</span><span class="sxs-lookup"><span data-stu-id="504cc-108">Then you can edit the new search by changing the keyword query or the date range, and run it.</span></span>
  
<span data-ttu-id="504cc-109">Perché clonare le ricerche di contenuto?</span><span class="sxs-lookup"><span data-stu-id="504cc-109">Why clone Content Searches?</span></span>
  
- <span data-ttu-id="504cc-110">Per confrontare i risultati delle diverse query di ricerca con parole chiave eseguite negli stessi percorsi di contenuto.</span><span class="sxs-lookup"><span data-stu-id="504cc-110">To compare the results of different keyword search queries run on the same content locations.</span></span>
    
- <span data-ttu-id="504cc-111">Per evitare di dover immettere di nuovo un numero elevato di posizioni di contenuto quando si crea una nuova ricerca.</span><span class="sxs-lookup"><span data-stu-id="504cc-111">To save you from having to reenter a large number of content locations when you create a new search.</span></span>
    
- <span data-ttu-id="504cc-112">Per ridurre le dimensioni dei risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="504cc-112">To decrease the size of the search results.</span></span> <span data-ttu-id="504cc-113">Se ad esempio si dispone di una ricerca che restituisce troppi risultati da esportare, è possibile clonare la ricerca e quindi aggiungere una condizione di ricerca in base a un intervallo di date per ridurre il numero di risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="504cc-113">For example, if you have a search that returns too many results to export, you can clone the search and then add a search condition based on a date range to reduce the number of search results.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="504cc-114">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="504cc-114">Before you begin</span></span>

- <span data-ttu-id="504cc-115">Per eseguire lo script descritto in questo argomento, è necessario essere membri del gruppo di ruoli eDiscovery Manager nel centro sicurezza & Compliance.</span><span class="sxs-lookup"><span data-stu-id="504cc-115">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center to run the script described in this topic.</span></span>
    
- <span data-ttu-id="504cc-116">Lo script include la gestione degli errori minima.</span><span class="sxs-lookup"><span data-stu-id="504cc-116">The script includes minimal error handling.</span></span> <span data-ttu-id="504cc-117">Lo scopo principale dello script è di clonare velocemente una ricerca di contenuto.</span><span class="sxs-lookup"><span data-stu-id="504cc-117">The primary purpose of the script is to quickly clone a content search.</span></span>
    
- <span data-ttu-id="504cc-118">Lo script crea una nuova ricerca del contenuto, ma non la avvia.</span><span class="sxs-lookup"><span data-stu-id="504cc-118">The script creates a new Content Search, but doesn't start it.</span></span>
    
- <span data-ttu-id="504cc-119">Questo script tiene conto del fatto che la ricerca di contenuto che si sta clonando è associata a un caso di eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="504cc-119">This script takes into account whether the Content Search that you're cloning is associated with an eDiscovery case.</span></span> <span data-ttu-id="504cc-120">Se la ricerca è associata a un caso, la nuova ricerca verrà associata anche allo stesso caso.</span><span class="sxs-lookup"><span data-stu-id="504cc-120">If the search is associated with a case, the new search will also be associated with the same case.</span></span> <span data-ttu-id="504cc-121">Se la ricerca esistente non è associata a un caso, la nuova ricerca verrà elencata nella pagina **Ricerca contenuto** nel centro conformità.</span><span class="sxs-lookup"><span data-stu-id="504cc-121">If the existing search isn't associated with a case, the new search will be listed on the **Content search** page in the compliance center.</span></span> 
    
- <span data-ttu-id="504cc-122">Lo script di esempio fornito in questo argomento non è supportato in alcun servizio o programma di supporto Microsoft standard.</span><span class="sxs-lookup"><span data-stu-id="504cc-122">The sample script provided in this topic isn't supported under any Microsoft standard support program or service.</span></span> <span data-ttu-id="504cc-123">Lo script di esempio viene fornito come senza garanzie di alcun tipo.</span><span class="sxs-lookup"><span data-stu-id="504cc-123">The sample script is provided AS IS without warranty of any kind.</span></span> <span data-ttu-id="504cc-124">Inoltre Microsoft declina ogni responsabilità su garanzie implicite, senza alcuna limitazione, incluse le garanzie implicite di commerciabilità e/o adeguatezza per uno scopo specifico.</span><span class="sxs-lookup"><span data-stu-id="504cc-124">Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.</span></span> <span data-ttu-id="504cc-125">L'intero rischio derivante dall'utilizzo o dalle prestazioni dello script di esempio e della documentazione resta all'interno dell'utente.</span><span class="sxs-lookup"><span data-stu-id="504cc-125">The entire risk arising out of the use or performance of the sample script and documentation remains with you.</span></span> <span data-ttu-id="504cc-126">In nessun caso Microsoft, i suoi autori o chiunque altro coinvolto nella creazione, produzione o consegna degli script è da ritenersi responsabile per qualsiasi danno eventuale (inclusi, senza limitazione alcuna, danni riguardanti profitti aziendali, interruzione di attività, perdita di informazioni aziendali o altra perdita pecuniaria) derivanti dall'utilizzo o dall'incapacità di utilizzo degli script di esempio e della documentazione, anche nel caso in cui Microsoft sia stata avvisata della possibilità di tali danni.</span><span class="sxs-lookup"><span data-stu-id="504cc-126">In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
  
## <a name="step-1-run-the-script-to-clone-a-search"></a><span data-ttu-id="504cc-127">Passaggio 1: eseguire lo script per clonare una ricerca</span><span class="sxs-lookup"><span data-stu-id="504cc-127">Step 1: Run the script to clone a search</span></span>

<span data-ttu-id="504cc-128">Nello script di questo passaggio viene creata una nuova ricerca di contenuto clonando un'altra esistente.</span><span class="sxs-lookup"><span data-stu-id="504cc-128">The script in this step will create a new Content Search by cloning an existing one.</span></span> <span data-ttu-id="504cc-129">Quando si esegue questo script, vengono richieste le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="504cc-129">When you run this script, you'll be prompted for the following information:</span></span>
  
- <span data-ttu-id="504cc-130">**Credenziali utente** : lo script utilizzerà le credenziali per connettersi al centro sicurezza & conformità per l'organizzazione con Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="504cc-130">**Your user credentials** - The script will use your credentials to connect to the Security & Compliance Center for your organization with Windows PowerShell.</span></span> <span data-ttu-id="504cc-131">Come indicato in precedenza, è necessario essere membri del gruppo di ruoli eDiscovery Manager nella & di sicurezza compCompliance Center per eseguire lo script.</span><span class="sxs-lookup"><span data-stu-id="504cc-131">As previously stated, you have to be a member of the eDiscovery Manager role group in the Security & compCompliance Center to run the script.</span></span> 
    
- <span data-ttu-id="504cc-132">**Il nome della ricerca esistente** , ovvero la ricerca di contenuto che si desidera clonare.</span><span class="sxs-lookup"><span data-stu-id="504cc-132">**The name of the existing search** - This is the Content Search that you want to clone.</span></span> 
    
- <span data-ttu-id="504cc-133">**Nome della nuova ricerca che verrà creata** : se si lascia vuoto questo valore, lo script creerà un nome per la nuova ricerca basata sul nome della ricerca che si sta clonando.</span><span class="sxs-lookup"><span data-stu-id="504cc-133">**The name of the new search that will be created** - If you leave this value blank, the script will create a name for the new search that is based on the name of the search that you're cloning.</span></span> 
    
<span data-ttu-id="504cc-134">Per clonare una ricerca:</span><span class="sxs-lookup"><span data-stu-id="504cc-134">To clone a search:</span></span>
  
1. <span data-ttu-id="504cc-135">Salvare il testo seguente in un file di script di Windows PowerShell utilizzando un suffisso FileName di. ps1. ad esempio, `CloneSearch.ps1`.</span><span class="sxs-lookup"><span data-stu-id="504cc-135">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `CloneSearch.ps1`.</span></span>
    
  ```powershell
  # This PowerShell script clones an existing content search in the Security &amp; Compliance Center.
  # Get login credentials from the user
  if(!$UserCredential)
  {
      $UserCredential = Get-Credential
      $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
      if (!$Session)
      {
          Write-Error "Couldn't create a remote PowerShell session."
          return
      }
      Import-PSSession $Session -AllowClobber -DisableNameChecking
      $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Security & Compliance Center)"
  }
  # Ask for the name of the search you want to clone
  $searchName = Read-Host 'Enter the name of the search that you want to clone'
  # Ask for the name of the new search
  $newSearchName = Read-Host 'Enter a name for the new search [leave blank to automatically generate a name]'
  $originalSearch = Get-ComplianceSearch $searchName -EA SilentlyContinue
  # Make sure we have a valid search before continuing
  if(!$originalSearch)
  {
      Write-Error "Couldn't find search: $searchName"
      return
  }
  $searchNameCounter = 1
  # Find a suitable name for the new search
  while(!$newSearchName)
  {
      $newSearchName = $originalSearch.Name + "_" + $searchNameCounter
      $tempSearch = Get-ComplianceSearch $newSearchName -EA SilentlyContinue
      if ($tempSearch)
      {
          $newSearchName = $null
          $searchNameCounter++
      }
  }
  $caseName
  # Determine if the search is part of a case; if so get the case name
  if ($originalSearch.CaseId)
  {
      $searchCase = Get-ComplianceCase $originalSearch.CaseId
      $caseName = $searchCase.Name
  }
  # Need to cast this value as a Boolean the old fashion way
  $allowNotFoundExchangeLocationsEnabled = $false
  if ($originalSearch.AllowNotFoundExchangeLocationsEnabled)
  {
      $allowNotFoundExchangeLocationsEnabled = $true
  }
  $newSearch = New-ComplianceSearch -Name $newSearchName -AllowNotFoundExchangeLocationsEnabled $allowNotFoundExchangeLocationsEnabled -Case $caseName -ContentMatchQuery $originalSearch.ContentMatchQuery -Description $originalSearch.Description -ExchangeLocation $originalSearch.ExchangeLocation -ExchangeLocationExclusion $originalSearch.ExchangeLocationExclusion -Language $originalSearch.Language -SharePointLocation $originalSearch.SharePointLocation -SharePointLocationExclusion $originalSearch.SharePointLocationExclusion -PublicFolderLocation $originalSearch.PublicFolderLocation
  if ($newSearch)
  {
      Write-Host $newSearch.Name "was successfully created" -ForegroundColor Yellow
  }
  ```

2. <span data-ttu-id="504cc-136">Aprire Windows PowerShell e passare alla cartella in cui è stato salvato lo script.</span><span class="sxs-lookup"><span data-stu-id="504cc-136">Open Windows PowerShell and go to the folder where you saved the script.</span></span>
    
3. <span data-ttu-id="504cc-137">Eseguire lo script; Per esempio:</span><span class="sxs-lookup"><span data-stu-id="504cc-137">Run the script; for example:</span></span>
    
    ```powershell
    .\CloneSearch.ps1
    ```

4. <span data-ttu-id="504cc-138">Quando vengono richieste le credenziali, immettere l'indirizzo di posta elettronica e la password, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="504cc-138">When prompted for your credentials, enter your email address and password, and then click **OK**.</span></span>
    
5. <span data-ttu-id="504cc-139">Immettere le informazioni seguenti quando richiesto dallo script.</span><span class="sxs-lookup"><span data-stu-id="504cc-139">Enter following information when prompted by the script.</span></span> <span data-ttu-id="504cc-140">Digitare ogni informazione e quindi premere **invio**.</span><span class="sxs-lookup"><span data-stu-id="504cc-140">Type each piece of information and then press **Enter**.</span></span>
    
    - <span data-ttu-id="504cc-141">Nome della ricerca esistente.</span><span class="sxs-lookup"><span data-stu-id="504cc-141">The name of the existing search.</span></span>
    
    - <span data-ttu-id="504cc-142">Nome della nuova ricerca.</span><span class="sxs-lookup"><span data-stu-id="504cc-142">The name of the new search.</span></span>
    
    <span data-ttu-id="504cc-143">Lo script crea la nuova ricerca del contenuto, ma non la avvia.</span><span class="sxs-lookup"><span data-stu-id="504cc-143">The script creates the new Content Search, but doesn't start it.</span></span> <span data-ttu-id="504cc-144">In questo modo è possibile modificare ed eseguire la ricerca nel passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="504cc-144">This gives you a chance to edit and run the search in the next step.</span></span> <span data-ttu-id="504cc-145">Per visualizzare le proprietà della nuova ricerca, è possibile eseguire il cmdlet **Get-ComplianceSearch** o andare alla pagina **Ricerca contenuto** o **eDiscovery** nel centro conformità, a seconda che la nuova ricerca sia associata a un caso.</span><span class="sxs-lookup"><span data-stu-id="504cc-145">You can view the properties of the new search by running the **Get-ComplianceSearch** cmdlet or by going to the **Content search** or **eDiscovery** page in the compliance center, depending on whether the new search is associated with a case.</span></span> 
  
## <a name="step-2-edit-and-run-the-cloned-search-in-the-compliance-center"></a><span data-ttu-id="504cc-146">Passaggio 2: modificare ed eseguire la ricerca clonata nel centro conformità</span><span class="sxs-lookup"><span data-stu-id="504cc-146">Step 2: Edit and run the cloned search in the compliance center</span></span>

<span data-ttu-id="504cc-147">Dopo aver eseguito lo script per clonare una ricerca di contenuto esistente, il passaggio successivo consiste nel passare al centro conformità per modificare ed eseguire la nuova ricerca.</span><span class="sxs-lookup"><span data-stu-id="504cc-147">After you run the script to clone an existing Content Search, the next step is to go to the compliance center to edit and run the new search.</span></span> <span data-ttu-id="504cc-148">Come indicato in precedenza, è possibile modificare una ricerca modificando la query di ricerca con parole chiave e aggiungendo o rimuovendo le condizioni di ricerca.</span><span class="sxs-lookup"><span data-stu-id="504cc-148">As previously stated, you can edit a search by changing the keyword search query and adding or removing search conditions.</span></span> <span data-ttu-id="504cc-149">Per ulteriori informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="504cc-149">For more information, see:</span></span>
  
- [<span data-ttu-id="504cc-150">Ricerca contenuto in Office 365</span><span class="sxs-lookup"><span data-stu-id="504cc-150">Content Search in Office 365</span></span>](content-search.md)
    
- [<span data-ttu-id="504cc-151">Query con parole chiave e condizioni di ricerca per la Ricerca contenuto</span><span class="sxs-lookup"><span data-stu-id="504cc-151">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
    
- [<span data-ttu-id="504cc-152">casi di eDiscovery</span><span class="sxs-lookup"><span data-stu-id="504cc-152">eDiscovery cases</span></span>](ediscovery-cases.md)
