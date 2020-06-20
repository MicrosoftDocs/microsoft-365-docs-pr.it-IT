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
ms.openlocfilehash: 28f1264736f158fd686174813b9cefdd087c274c
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818085"
---
# <a name="clone-a-content-search"></a>Clonare una ricerca contenuto

Creazione di una ricerca contenuto nel centro conformità di Office 365 o Microsoft 365 che consente di eseguire ricerche in molte cassette postali o in siti di SharePoint e OneDrive for business può richiedere un po' di tempo. La specifica dei siti da cercare può anche essere soggetta a errori se si digita un URL in modo improprio. Per evitare questi problemi, è possibile utilizzare lo script di Windows PowerShell in questo articolo per clonare rapidamente una ricerca di contenuto esistente. Quando si clona una ricerca, viene creata una nuova ricerca, con un nome diverso, che contiene le stesse proprietà, ad esempio i percorsi di contenuto e la query di ricerca, come ricerca originale. È quindi possibile modificare la nuova ricerca modificando la query di parole chiave o l'intervallo di date ed eseguirlo.
  
Perché clonare le ricerche di contenuto?
  
- Per confrontare i risultati delle diverse query di ricerca con parole chiave eseguite negli stessi percorsi di contenuto.
    
- Per evitare di dover immettere di nuovo un numero elevato di posizioni di contenuto quando si crea una nuova ricerca.
    
- Per ridurre le dimensioni dei risultati della ricerca. Se ad esempio si dispone di una ricerca che restituisce troppi risultati da esportare, è possibile clonare la ricerca e quindi aggiungere una condizione di ricerca in base a un intervallo di date per ridurre il numero di risultati della ricerca.
  
## <a name="script-information"></a>Informazioni sullo script

- Per eseguire lo script descritto in questo argomento, è necessario essere membri del gruppo di ruoli eDiscovery Manager nel centro sicurezza & Compliance.
    
- Lo script include la gestione degli errori minima. Lo scopo principale dello script è di clonare velocemente una ricerca di contenuto.
    
- Lo script crea una nuova ricerca del contenuto, ma non la avvia.
    
- Questo script tiene conto del fatto che la ricerca di contenuto che si sta clonando è associata a un caso di eDiscovery. Se la ricerca è associata a un caso, la nuova ricerca verrà associata anche allo stesso caso. Se la ricerca esistente non è associata a un caso, la nuova ricerca verrà elencata nella pagina **Ricerca contenuto** nel centro conformità. 
    
- Lo script di esempio fornito in questo argomento non è supportato in alcun servizio o programma di supporto Microsoft standard. Lo script di esempio viene fornito come senza garanzie di alcun tipo. Inoltre Microsoft declina ogni responsabilità su garanzie implicite, senza alcuna limitazione, incluse le garanzie implicite di commerciabilità e/o adeguatezza per uno scopo specifico. L'intero rischio derivante dall'utilizzo o dalle prestazioni dello script di esempio e della documentazione resta all'interno dell'utente. In nessun caso Microsoft, i suoi autori o chiunque altro coinvolto nella creazione, produzione o consegna degli script è da ritenersi responsabile per qualsiasi danno eventuale (inclusi, senza limitazione alcuna, danni riguardanti profitti aziendali, interruzione di attività, perdita di informazioni aziendali o altra perdita pecuniaria) derivanti dall'utilizzo o dall'incapacità di utilizzo degli script di esempio e della documentazione, anche nel caso in cui Microsoft sia stata avvisata della possibilità di tali danni.
  
## <a name="step-1-run-the-script-to-clone-a-search"></a>Passaggio 1: eseguire lo script per clonare una ricerca

Nello script di questo passaggio viene creata una nuova ricerca di contenuto clonando un'altra esistente. Quando si esegue questo script, vengono richieste le informazioni seguenti:
  
- **Credenziali utente** : lo script utilizzerà le credenziali per connettersi al centro sicurezza & conformità per l'organizzazione con Windows PowerShell. Come indicato in precedenza, è necessario essere membri del gruppo di ruoli eDiscovery Manager nella & di sicurezza compCompliance Center per eseguire lo script. 
    
- **Il nome della ricerca esistente** , ovvero la ricerca di contenuto che si desidera clonare. 
    
- **Nome della nuova ricerca che verrà creata** : se si lascia vuoto questo valore, lo script creerà un nome per la nuova ricerca basata sul nome della ricerca che si sta clonando. 
    
Per clonare una ricerca:
  
1. Salvare il testo seguente in un file di script di Windows PowerShell utilizzando un suffisso FileName di. ps1. ad esempio, `CloneSearch.ps1` .
    
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

2. Aprire Windows PowerShell e passare alla cartella in cui è stato salvato lo script.
    
3. Eseguire lo script; Per esempio:
    
    ```powershell
    .\CloneSearch.ps1
    ```

4. Quando vengono richieste le credenziali, immettere l'indirizzo di posta elettronica e la password, quindi fare clic su **OK**.
    
5. Immettere le informazioni seguenti quando richiesto dallo script. Digitare ogni informazione e quindi premere **invio**.
    
    - Nome della ricerca esistente.
    
    - Nome della nuova ricerca.
    
    Lo script crea la nuova ricerca del contenuto, ma non la avvia. In questo modo è possibile modificare ed eseguire la ricerca nel passaggio successivo. Per visualizzare le proprietà della nuova ricerca, è possibile eseguire il cmdlet **Get-ComplianceSearch** o andare alla pagina **Ricerca contenuto** o **eDiscovery** nel centro conformità, a seconda che la nuova ricerca sia associata a un caso. 
  
## <a name="step-2-edit-and-run-the-cloned-search-in-the-compliance-center"></a>Passaggio 2: modificare ed eseguire la ricerca clonata nel centro conformità

Dopo aver eseguito lo script per clonare una ricerca di contenuto esistente, il passaggio successivo consiste nel passare al centro conformità per modificare ed eseguire la nuova ricerca. Come indicato in precedenza, è possibile modificare una ricerca modificando la query di ricerca con parole chiave e aggiungendo o rimuovendo le condizioni di ricerca. Per altre informazioni, vedere:
  
- [Ricerca contenuto in Office 365](content-search.md)
    
- [Query con parole chiave e condizioni di ricerca per la Ricerca contenuto](keyword-queries-and-search-conditions.md)
    
- [casi di eDiscovery](ediscovery-cases.md)
