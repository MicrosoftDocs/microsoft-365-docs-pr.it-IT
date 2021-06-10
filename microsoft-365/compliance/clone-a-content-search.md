---
title: Clonare una ricerca contenuto
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 4/26/2017
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 7b40eeaa-544c-4534-b89b-9f79998e374c
ms.custom:
- seo-marvel-apr2020
description: Usare lo script di PowerShell in questo articolo per clonare rapidamente una ricerca contenuto esistente nel Centro conformità in Office 365 o Microsoft 365.
ms.openlocfilehash: c64cec2415819dc53f30c303c241e3902f34017d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918062"
---
# <a name="clone-a-content-search"></a>Clonare una ricerca contenuto

La creazione di una ricerca contenuto nel Centro conformità in Office 365 o Microsoft 365 che esegue ricerche in molte cassette postali o SharePoint e OneDrive for Business siti può richiedere del tempo. La specifica dei siti in cui eseguire la ricerca può inoltre essere erta se si specifica un URL in modo erre. Per evitare questi problemi, è possibile utilizzare lo script Windows PowerShell in questo articolo per clonare rapidamente una ricerca di contenuto esistente. Quando si clona una ricerca, viene creata una nuova ricerca (con un nome diverso) che contiene le stesse proprietà (ad esempio i percorsi del contenuto e la query di ricerca) della ricerca originale. È quindi possibile modificare la nuova ricerca modificando la query con parole chiave o l'intervallo di date ed eseguirla.
  
Perché clonare le ricerche contenuto?
  
- Per confrontare i risultati di query di ricerca con parole chiave diverse eseguite nelle stesse posizioni del contenuto.
    
- Per non dover reim annotarti in un numero elevato di percorsi di contenuto quando crei una nuova ricerca.
    
- Per ridurre le dimensioni dei risultati della ricerca. Ad esempio, se si dispone di una ricerca che restituisce troppi risultati da esportare, è possibile clonare la ricerca e quindi aggiungere una condizione di ricerca basata su un intervallo di date per ridurre il numero di risultati della ricerca.
  
## <a name="script-information"></a>Informazioni script

- Per eseguire lo script descritto in questo argomento, è necessario essere membri del gruppo di ruoli Responsabile eDiscovery nel Centro sicurezza & conformità.
    
- Lo script include una gestione minima degli errori. Lo scopo principale dello script è clonare rapidamente una ricerca di contenuto.
    
- Lo script crea una nuova ricerca contenuto, ma non la avvia.
    
- Questo script tiene conto se la ricerca contenuto che si sta clonando è associata a un caso di eDiscovery. Se la ricerca è associata a un caso, anche la nuova ricerca verrà associata allo stesso caso. Se la ricerca esistente non è associata a un caso, la nuova ricerca verrà elencata nella pagina **Ricerca** contenuto nel Centro conformità. 
    
- Lo script di esempio fornito in questo argomento non è supportato in alcun servizio o programma di supporto standard Microsoft. Lo script di esempio è fornito così come è senza alcun tipo di garanzia. Microsoft esclude inoltre qualsiasi garanzia implicita, tra cui, senza limitazioni, tutte le garanzie implicite di commerciabilità o idoneità per uno scopo specifico. L'utente assume tutti i rischi associati all'uso o alle prestazioni dello script di esempio e della documentazione. In nessun caso Microsoft, i suoi autori o chiunque altro coinvolto nella creazione, produzione o consegna degli script è da ritenersi responsabile per qualsiasi danno eventuale (inclusi, senza limitazione alcuna, danni riguardanti profitti aziendali, interruzione di attività, perdita di informazioni aziendali o altra perdita pecuniaria) derivanti dall'utilizzo o dall'incapacità di utilizzo degli script di esempio e della documentazione, anche nel caso in cui Microsoft sia stata avvisata della possibilità di tali danni.
  
## <a name="step-1-run-the-script-to-clone-a-search"></a>Passaggio 1: eseguire lo script per clonare una ricerca

Lo script in questo passaggio creerà una nuova ricerca contenuto clonando una esistente. Quando si esegue questo script, verranno richieste le informazioni seguenti:
  
- **Credenziali utente:** lo script utilizzerà le credenziali per connettersi al Centro sicurezza & conformità per l'organizzazione con Windows PowerShell. Come indicato in precedenza, per eseguire lo script è necessario essere membri del gruppo di ruoli Responsabile eDiscovery nel Centro sicurezza & conformità. 
    
- **Nome della ricerca esistente:** si tratta della ricerca contenuto che si desidera clonare. 
    
- **Nome della** nuova ricerca che verrà creata: se si lascia vuoto questo valore, lo script creerà un nome per la nuova ricerca in base al nome della ricerca che si sta clonando. 
    
Per clonare una ricerca:
  
1. Salvare il testo seguente in un file Windows PowerShell script utilizzando un suffisso di nome file .ps1; ad `CloneSearch.ps1` esempio.
    
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

4. Quando vengono richieste le credenziali, immettere l'indirizzo di posta elettronica e la password, quindi fare clic su **OK.**
    
5. Quando richiesto dallo script, immettere le informazioni seguenti. Digitare ogni informazione e quindi premere **INVIO.**
    
    - Nome della ricerca esistente.
    
    - Nome della nuova ricerca.
    
    Lo script crea la nuova ricerca contenuto, ma non la avvia. In questo modo è possibile modificare ed eseguire la ricerca nel passaggio successivo. È possibile visualizzare le proprietà della nuova ricerca eseguendo il cmdlet  **Get-ComplianceSearch** o andando alla pagina Ricerca contenuto o **eDiscovery** nel Centro conformità, a seconda che la nuova ricerca sia associata a un caso. 
  
## <a name="step-2-edit-and-run-the-cloned-search-in-the-compliance-center"></a>Passaggio 2: Modificare ed eseguire la ricerca clonata nel Centro conformità

Dopo aver eseguito lo script per clonare una ricerca contenuto esistente, il passaggio successivo consiste nel passare al Centro conformità per modificare ed eseguire la nuova ricerca. Come indicato in precedenza, è possibile modificare una ricerca modificando la query di ricerca con parole chiave e aggiungendo o rimuovendo le condizioni di ricerca. Per altre informazioni, vedere:
  
- [Ricerca contenuto in Office 365](content-search.md)
    
- [Query con parole chiave e condizioni di ricerca per la Ricerca contenuto](keyword-queries-and-search-conditions.md)
    
- [Casi di eDiscovery](./get-started-core-ediscovery.md)