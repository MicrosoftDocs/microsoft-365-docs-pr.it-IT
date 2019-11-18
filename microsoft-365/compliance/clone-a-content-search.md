---
title: Clonare una ricerca contenuto
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
ms.assetid: 7b40eeaa-544c-4534-b89b-9f79998e374c
description: Utilizzare lo script di Windows PowerShell in questo articolo per clonare rapidamente una ricerca di contenuto esistente nel centro conformità di Office 365 o Microsoft 365. Quando si clona una ricerca, viene creata una nuova ricerca (con un nuovo nome) che contiene le stesse proprietà della ricerca originale. È quindi possibile modificare la nuova ricerca modificando la query di parole chiave o l'intervallo di date e quindi eseguirlo.
ms.openlocfilehash: 25aa5d6a1ba19f697a6ccf474e055faf6a19d6bd
ms.sourcegitcommit: 1d376287f6c1bf5174873e89ed4bf7bb15bc13f6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/14/2019
ms.locfileid: "38686549"
---
# <a name="clone-a-content-search"></a><span data-ttu-id="df11a-105">Clonare una ricerca contenuto</span><span class="sxs-lookup"><span data-stu-id="df11a-105">Clone a Content Search</span></span>

<span data-ttu-id="df11a-106">La creazione di una ricerca contenuto nel centro conformità di Office 365 o Microsoft 365 che consente di eseguire ricerche in molte cassette postali o in siti di SharePoint e OneDrive for business può richiedere un po' di tempo.</span><span class="sxs-lookup"><span data-stu-id="df11a-106">Creating a Content Search in the compliance center in Office 365 or Microsoft 365 that searches a lot of mailboxes or SharePoint and OneDrive for Business sites can take awhile.</span></span> <span data-ttu-id="df11a-107">La specifica dei siti da cercare può anche essere soggetta a errori se si digita un URL in modo improprio.</span><span class="sxs-lookup"><span data-stu-id="df11a-107">Specifying the sites to search can also be prone to errors if you mistype a URL.</span></span> <span data-ttu-id="df11a-108">Per evitare questi problemi, è possibile utilizzare lo script di Windows PowerShell in questo articolo per clonare rapidamente una ricerca di contenuto esistente.</span><span class="sxs-lookup"><span data-stu-id="df11a-108">To avoid these issues, you can use the Windows PowerShell script in this article to quickly clone an existing Content Search.</span></span> <span data-ttu-id="df11a-109">Quando si clona una ricerca, viene creata una nuova ricerca, con un nome diverso, che contiene le stesse proprietà, ad esempio i percorsi di contenuto e la query di ricerca, come la ricerca originale.</span><span class="sxs-lookup"><span data-stu-id="df11a-109">When a you clone a search, a new search (with a different name) is created that contains the same properties (such as the content locations and the search query) as the original search.</span></span> <span data-ttu-id="df11a-110">È quindi possibile modificare la nuova ricerca (modificando la query di parole chiave o l'intervallo di date) ed eseguirla.</span><span class="sxs-lookup"><span data-stu-id="df11a-110">Then you can edit the new search (by changing the keyword query or the date range) and run it.</span></span>
  
<span data-ttu-id="df11a-111">Perché clonare le ricerche di contenuto?</span><span class="sxs-lookup"><span data-stu-id="df11a-111">Why clone Content Searches?</span></span>
  
- <span data-ttu-id="df11a-112">Per confrontare i risultati delle diverse query di ricerca con parole chiave eseguite negli stessi percorsi di contenuto.</span><span class="sxs-lookup"><span data-stu-id="df11a-112">To compare the results of different keyword search queries run on the same content locations.</span></span>
    
- <span data-ttu-id="df11a-113">Per evitare di dover immettere nuovamente un numero elevato di posizioni di contenuto quando si crea una nuova ricerca.</span><span class="sxs-lookup"><span data-stu-id="df11a-113">To save you from having to re-enter a large number of content locations when you create a new search.</span></span>
    
- <span data-ttu-id="df11a-114">Per ridurre le dimensioni dei risultati della ricerca; Se ad esempio si dispone di una ricerca che restituisce troppi risultati da esportare, è possibile clonare la ricerca e quindi aggiungere una condizione di ricerca in base a un intervallo di date per ridurre il numero di risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="df11a-114">To decrease the size of the search results; for example, if you have a search that returns too many results to export, you can clone the search and then add a search condition based on a date range to reduce the number of search results.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="df11a-115">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="df11a-115">Before you begin</span></span>

- <span data-ttu-id="df11a-116">Per eseguire lo script descritto in questo argomento, è necessario essere membri del gruppo di ruoli eDiscovery Manager nel centro sicurezza & Compliance.</span><span class="sxs-lookup"><span data-stu-id="df11a-116">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center to run the script described in this topic.</span></span>
    
- <span data-ttu-id="df11a-117">Lo script include la gestione degli errori minima.</span><span class="sxs-lookup"><span data-stu-id="df11a-117">The script includes minimal error handling.</span></span> <span data-ttu-id="df11a-118">Lo scopo principale dello script è di clonare velocemente una ricerca di contenuto.</span><span class="sxs-lookup"><span data-stu-id="df11a-118">The primary purpose of the script is to quickly clone a content search.</span></span>
    
- <span data-ttu-id="df11a-119">Lo script crea una nuova ricerca del contenuto, ma non la avvia.</span><span class="sxs-lookup"><span data-stu-id="df11a-119">The script creates a new Content Search, but doesn't start it.</span></span>
    
- <span data-ttu-id="df11a-120">Questo script tiene conto del fatto che la ricerca di contenuto che si sta clonando è associata a un caso di eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="df11a-120">This script takes into account whether the Content Search that you're cloning is associated with an eDiscovery case.</span></span> <span data-ttu-id="df11a-121">Se la ricerca è associata a un caso, la nuova ricerca verrà associata anche allo stesso caso.</span><span class="sxs-lookup"><span data-stu-id="df11a-121">If the search is associated with a case, the new search will also be associated with the same case.</span></span> <span data-ttu-id="df11a-122">Se la ricerca esistente non è associata a un caso, la nuova ricerca verrà elencata nella pagina **Ricerca contenuto** nel centro conformità.</span><span class="sxs-lookup"><span data-stu-id="df11a-122">If the existing search isn't associated with a case, the new search will be listed on the **Content search** page in the compliance center.</span></span> 
    
- <span data-ttu-id="df11a-123">Lo script di esempio fornito in questo argomento non è supportato in alcun servizio o programma di supporto Microsoft standard.</span><span class="sxs-lookup"><span data-stu-id="df11a-123">The sample script provided in this topic isn't supported under any Microsoft standard support program or service.</span></span> <span data-ttu-id="df11a-124">Lo script di esempio viene fornito come senza garanzie di alcun tipo.</span><span class="sxs-lookup"><span data-stu-id="df11a-124">The sample script is provided AS IS without warranty of any kind.</span></span> <span data-ttu-id="df11a-125">Inoltre Microsoft declina ogni responsabilità su garanzie implicite, senza alcuna limitazione, incluse le garanzie implicite di commerciabilità e/o adeguatezza per uno scopo specifico.</span><span class="sxs-lookup"><span data-stu-id="df11a-125">Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.</span></span> <span data-ttu-id="df11a-126">L'intero rischio derivante dall'utilizzo o dalle prestazioni dello script di esempio e della documentazione resta all'interno dell'utente.</span><span class="sxs-lookup"><span data-stu-id="df11a-126">The entire risk arising out of the use or performance of the sample script and documentation remains with you.</span></span> <span data-ttu-id="df11a-127">In nessun caso Microsoft, i suoi autori o chiunque altro coinvolto nella creazione, produzione o consegna degli script è da ritenersi responsabile per qualsiasi danno eventuale (inclusi, senza limitazione alcuna, danni riguardanti profitti aziendali, interruzione di attività, perdita di informazioni aziendali o altra perdita pecuniaria) derivanti dall'utilizzo o dall'incapacità di utilizzo degli script di esempio e della documentazione, anche nel caso in cui Microsoft sia stata avvisata della possibilità di tali danni.</span><span class="sxs-lookup"><span data-stu-id="df11a-127">In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
  
## <a name="step-1-run-the-script-to-clone-a-search"></a><span data-ttu-id="df11a-128">Passaggio 1: eseguire lo script per clonare una ricerca</span><span class="sxs-lookup"><span data-stu-id="df11a-128">Step 1: Run the script to clone a search</span></span>

<span data-ttu-id="df11a-129">Nello script di questo passaggio viene creata una nuova ricerca di contenuto clonando un'altra esistente.</span><span class="sxs-lookup"><span data-stu-id="df11a-129">The script in this step will create a new Content Search by cloning an existing one.</span></span> <span data-ttu-id="df11a-130">Quando si esegue questo script, vengono richieste le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="df11a-130">When you run this script, you'll be prompted for the following information:</span></span>
  
- <span data-ttu-id="df11a-131">**Credenziali utente** : lo script utilizzerà le credenziali per connettersi al centro sicurezza & Compliance per l'organizzazione di Office 365 con Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="df11a-131">**Your user credentials** - The script will use your credentials to connect to the Security & Compliance Center for your Office 365 organization with Windows PowerShell.</span></span> <span data-ttu-id="df11a-132">Come indicato in precedenza, è necessario essere membri del gruppo di ruoli eDiscovery Manager nella & di sicurezza compCompliance Center per eseguire lo script.</span><span class="sxs-lookup"><span data-stu-id="df11a-132">As previously stated, you have to be a member of the eDiscovery Manager role group in the Security & compCompliance Center to run the script.</span></span> 
    
- <span data-ttu-id="df11a-133">**Il nome della ricerca esistente** , ovvero la ricerca di contenuto che si desidera clonare.</span><span class="sxs-lookup"><span data-stu-id="df11a-133">**The name of the existing search** - This is the Content Search that you want to clone.</span></span> 
    
- <span data-ttu-id="df11a-134">**Nome della nuova ricerca che verrà creata** : se si lascia vuoto questo valore, lo script creerà un nome per la nuova ricerca basata sul nome della ricerca che si sta clonando.</span><span class="sxs-lookup"><span data-stu-id="df11a-134">**The name of the new search that will be created** - If you leave this value blank, the script will create a name for the new search that is based on the name of the search that you're cloning.</span></span> 
    
<span data-ttu-id="df11a-135">Per clonare una ricerca:</span><span class="sxs-lookup"><span data-stu-id="df11a-135">To clone a search:</span></span>
  
1. <span data-ttu-id="df11a-136">Salvare il testo seguente in un file di script di Windows PowerShell utilizzando un suffisso FileName di. ps1. ad esempio, `CloneSearch.ps1`.</span><span class="sxs-lookup"><span data-stu-id="df11a-136">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `CloneSearch.ps1`.</span></span>
    
  ```powershell
  # This PowerShell script clones an existing Content Search in the Office 365 security and compliance center.
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

2. <span data-ttu-id="df11a-137">Aprire Windows PowerShell e passare alla cartella in cui è stato salvato lo script.</span><span class="sxs-lookup"><span data-stu-id="df11a-137">Open Windows PowerShell and go to the folder where you saved the script.</span></span>
    
3. <span data-ttu-id="df11a-138">Eseguire lo script; Per esempio:</span><span class="sxs-lookup"><span data-stu-id="df11a-138">Run the script; for example:</span></span>
    
    ```powershell
    .\CloneSearch.ps1
    ```

4. <span data-ttu-id="df11a-139">Quando vengono richieste le credenziali, immettere l'indirizzo di posta elettronica e la password, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="df11a-139">When prompted for your credentials, enter your email address and password, and then click **OK**.</span></span>
    
5. <span data-ttu-id="df11a-140">Immettere le informazioni seguenti quando richiesto dallo script.</span><span class="sxs-lookup"><span data-stu-id="df11a-140">Enter following information when prompted by the script.</span></span> <span data-ttu-id="df11a-141">Digitare ogni informazione e quindi premere **invio**.</span><span class="sxs-lookup"><span data-stu-id="df11a-141">Type each piece of information and then press **Enter**.</span></span>
    
    - <span data-ttu-id="df11a-142">Nome della ricerca esistente.</span><span class="sxs-lookup"><span data-stu-id="df11a-142">The name of the existing search.</span></span>
    
    - <span data-ttu-id="df11a-143">Nome della nuova ricerca.</span><span class="sxs-lookup"><span data-stu-id="df11a-143">The name of the new search.</span></span>
    
    <span data-ttu-id="df11a-144">Lo script crea la nuova ricerca del contenuto, ma non la avvia.</span><span class="sxs-lookup"><span data-stu-id="df11a-144">The script creates the new Content Search, but doesn't start it.</span></span> <span data-ttu-id="df11a-145">In questo modo è possibile modificare ed eseguire la ricerca nel passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="df11a-145">This gives you a chance to edit and run the search in the next step.</span></span> <span data-ttu-id="df11a-146">Per visualizzare le proprietà della nuova ricerca, è possibile eseguire il cmdlet **Get-ComplianceSearch** o andare alla pagina **Ricerca contenuto** o **eDiscovery** nel centro conformità, a seconda che la nuova ricerca sia o meno associata a un caso.</span><span class="sxs-lookup"><span data-stu-id="df11a-146">You can view the properties of the new search by running the **Get-ComplianceSearch** cmdlet or by going to the **Content search** or **eDiscovery** page in the compliance center, depending on whether or not the new search is associated with a case.</span></span> 
  
## <a name="step-2-edit-and-run-the-cloned-search-in-the-compliance-center"></a><span data-ttu-id="df11a-147">Passaggio 2: modificare ed eseguire la ricerca clonata nel centro conformità</span><span class="sxs-lookup"><span data-stu-id="df11a-147">Step 2: Edit and run the cloned search in the compliance center</span></span>

<span data-ttu-id="df11a-148">Dopo aver eseguito lo script per clonare una ricerca di contenuto esistente, il passaggio successivo consiste nel passare al centro conformità per modificare ed eseguire la nuova ricerca.</span><span class="sxs-lookup"><span data-stu-id="df11a-148">After the you've run the script to clone an existing Content Search, the next step is to go to the compliance center to edit and run the new search.</span></span> <span data-ttu-id="df11a-149">Come indicato in precedenza, è possibile modificare una ricerca modificando la query di ricerca con parole chiave e aggiungendo o rimuovendo le condizioni di ricerca.</span><span class="sxs-lookup"><span data-stu-id="df11a-149">As previously stated, you can edit a search by changing the keyword search query and adding or removing search conditions.</span></span> <span data-ttu-id="df11a-150">Per ulteriori informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="df11a-150">For more information, see:</span></span>
  
- [<span data-ttu-id="df11a-151">Ricerca contenuto in Office 365</span><span class="sxs-lookup"><span data-stu-id="df11a-151">Content Search in Office 365</span></span>](content-search.md)
    
- [<span data-ttu-id="df11a-152">Query con parole chiave e condizioni di ricerca per la Ricerca contenuto</span><span class="sxs-lookup"><span data-stu-id="df11a-152">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
    
- [<span data-ttu-id="df11a-153">casi di eDiscovery</span><span class="sxs-lookup"><span data-stu-id="df11a-153">eDiscovery cases</span></span>](ediscovery-cases.md)
