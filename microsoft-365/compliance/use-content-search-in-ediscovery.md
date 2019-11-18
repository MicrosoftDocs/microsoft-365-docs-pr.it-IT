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
# <a name="use-content-search-in-your-ediscovery-workflow"></a>Usare Ricerca contenuto nel flusso di lavoro di eDiscovery

La funzionalità di ricerca contenuto nel centro sicurezza & conformità consente di effettuare una ricerca in tutte le cassette postali dell'organizzazione. A differenza di eDiscovery sul posto in Exchange Online (dove è possibile effettuare ricerche fino a 10.000 cassette postali), non esistono limiti per il numero di cassette postali di destinazione in una singola ricerca. Per gli scenari che richiedono di eseguire ricerche a livello dell'intera organizzazione, è possibile utilizzare Ricerca contenuto per effettuare ricerche in tutte le cassette postali. È quindi possibile utilizzare le funzionalità per i flussi di lavoro di eDiscovery sul posto per eseguire altre attività relative a eDiscovery, come la conservazione delle cassette postali e l'esportazione dei risultati di ricerca. Ad esempio, si supponga di dover effettuare una ricerca in tutte le cassette postali per identificare responsabili specifici di un caso legale. È possibile utilizzare la ricerca contenuto nel centro sicurezza & conformità per cercare tutte le cassette postali dell'organizzazione per identificare quelle che rispondono al caso. Successivamente, è possibile utilizzare l'elenco delle cassette postali del custode come cassette postali di origine per una ricerca eDiscovery sul posto in Exchange Online. eDiscovery sul posto consente, inoltre, di abilitare una conservazione per tali cassette postali di origine, copiare i risultati della ricerca in una cassetta postale di individuazione ed esportare i risultati della ricerca.
  
In questo argomento è incluso uno script che è possibile eseguire per creare una ricerca eDiscovery sul posto in Exchange Online utilizzando l'elenco delle cassette postali di origine e la query di ricerca di una ricerca creata nel centro sicurezza & conformità. Di seguito viene fornita una panoramica del processo:
  
[Passaggio 1: creare una ricerca di contenuto per effettuare una ricerca in tutte le cassette postali dell'organizzazione](#step-1-create-a-content-search-to-search-all-mailboxes-in-your-organization)

[Passaggio 2: connettersi al centro conformità \& di sicurezza e a Exchange online in una singola sessione di PowerShell remota](#step-2-connect-to-the-security--compliance-center-and-exchange-online-in-a-single-remote-powershell-session)
  
[Passaggio 3: eseguire lo script per creare una ricerca eDiscovery sul posto dalla ricerca di contenuto](#step-3-run-the-script-to-create-an-in-place-ediscovery-search-from-the-content-search)

[Step 4: Start the In-Place eDiscovery search](#step-4-start-the-in-place-ediscovery-search)

## <a name="step-1-create-a-content-search-to-search-all-mailboxes-in-your-organization"></a>Passaggio 1: creare una ricerca di contenuto per effettuare una ricerca in tutte le cassette postali dell'organizzazione

Il primo passaggio consiste nell'utilizzare il Centro sicurezza & Compliance (o la sicurezza & Compliance Center PowerShell) per creare una ricerca di contenuto che cerca tutte le cassette postali dell'organizzazione. Non esiste alcun limite al numero di cassette postali per una singola ricerca di contenuto. Specificare una query con parole chiave appropriate (o una query per tipi di informazioni riservate) in modo che la ricerca restituisca solo le cassette postali di origine rilevanti per l'analisi. Se necessario, è possibile perfezionare la query di ricerca per circoscrivere l'ambito dei risultati di ricerca e il numero di cassette postali di origine restituite.
  
> [!NOTE]
> Se la ricerca di contenuto di origine non restituisce risultati, non viene creata una ricerca eDiscovery sul posto quando si esegue lo script indicato al passaggio 3. Potrebbe essere necessario rivedere la query di ricerca ed eseguire di nuovo la ricerca di contenuto per ottenere dei risultati. 
  
### <a name="use-the-security--compliance-center-to-search-all-mailboxes"></a>Utilizzare il Centro sicurezza e conformità per effettuare ricerche in tutte le cassette postali

1. [Accedere al centro sicurezza & conformità](go-to-the-securitycompliance-center.md). 
    
2.  > Fare **clic**su ricerca**contenuto**ricerca, quindi fare clic su nuova](media/O365-MDM-CreatePolicy-AddIcon.gif)icona di **ricerca** ![Aggiungi.
    
3. Nella pagina **Nuova ricerca**, digitare un nome per la ricerca di contenuto. 
    
4. In **Dove si vuole effettuare la ricerca?**, fare clic su **Cerca in tutte le cassette postali**, quindi su **Avanti**.
    
5. Nella casella sotto **Dove si vuole effettuare la ricerca?**, digitare una query di ricerca. È possibile specificare parole chiave, proprietà dei messaggi come le date di invio o ricezione o proprietà dei documenti come il nome file o la data dell'ultima modifica apportata. È possibile utilizzare una query più complessa che utilizza un operatore booleano, ad esempio e, o, non o vicino, oppure è anche possibile cercare informazioni riservate (ad esempio i numeri di previdenza sociale) nei messaggi. Per ulteriori informazioni sulla creazione di query di ricerca, vedere [Keyword queries for Content Search](keyword-queries-and-search-conditions.md).
    
6. Fare clic su **Ricerca** per salvare le impostazioni di ricerca e avviare la ricerca. 
    
    Dopo un po' di tempo, viene visualizzata una stima dei risultati della ricerca nel riquadro dettagli. La stima include la dimensione totale e il numero di elementi per i risultati della ricerca. Una volta completata la ricerca, è possibile visualizzare in anteprima i risultati della ricerca. Se necessario **, fare clic su**![Aggiorna](media/O365-MDM-Policy-RefreshIcon.gif) l'icona Aggiorna per aggiornare le informazioni nel riquadro dei dettagli. 
    
7.  Se necessario, perfezionare la query di ricerca per limitare l'ambito dei risultati della ricerca, quindi riavviare la ricerca. 
    
### <a name="use-security--compliance-center-powershell-to-search-all-mailboxes"></a>Utilizzare la sicurezza & Compliance Center PowerShell per effettuare ricerche in tutte le cassette postali

È inoltre possibile utilizzare il cmdlet **New-ComplianceSearch** per effettuare ricerche in tutte le cassette postali dell'organizzazione. Il primo passaggio consiste nel [connettersi a PowerShell per Centro sicurezza & Compliance](https://go.microsoft.com/fwlink/p/?LinkID=627084).
  
Di seguito è riportato un esempio di utilizzo di PowerShell per eseguire una ricerca in tutte le cassette postali dell'organizzazione. La query di ricerca restituisce tutti i messaggi inviati tra il 1° gennaio 2015 e il 30 giugno 2015 e contenenti la frase "relazione finanziaria" nella riga dell'oggetto. Il primo comando crea la ricerca e il secondo la esegue. 
  
```powershell
New-ComplianceSearch -Name "Search All-Financial Report" -ExchangeLocation all -ContentMatchQuery 'sent>=01/01/2015 AND sent<=06/30/2015 AND subject:"financial report"'
```

```powershell
Start-ComplianceSearch -Identity "Search All-Financial Report"
```

Per ulteriori informazioni, vedere [New-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517935).
  
### <a name="verify-the-number-of-source-mailboxes-in-the-content-search"></a>Verificare il numero di cassette postali di origine nella ricerca di contenuto

Una ricerca di contenuto restituisce un massimo di 1.000 cassette postali di origine che contengono i risultati della ricerca. Se sono presenti più di 1.000 cassette postali che contengono contenuto che corrisponde alla query di ricerca, solo le cassette postali di 1.000 con la maggior parte dei risultati della ricerca vengono incluse nella ricerca di contenuto creata nel passaggio precedente. Pertanto, se più di 1.000 cassette postali contengono risultati della ricerca, alcune di queste cassette postali non verranno incluse nell'elenco delle cassette postali di origine copiate nella nuova ricerca eDiscovery sul posto creata nel passaggio 3. 
  
Per facilitare la creazione di una ricerca di contenuto con non più di 1.000 cassette postali di origine, seguire questa procedura per eseguire uno script che Visualizza il numero di cassette postali di origine (che contengono i risultati della ricerca) restituite dalla ricerca di contenuto creata nel passaggio 1. 
  
1. Salvare il testo seguente in un file di script di PowerShell utilizzando un suffisso FileName di. ps1. Ad esempio, è possibile salvarlo in un file denominato `SourceMailboxes.ps1`.
    
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

2. In PowerShell Centro sicurezza & conformità, passare alla cartella in cui si trova lo script creato nel passaggio precedente, quindi eseguire lo script. Per esempio:
    
    ```powershell
    .\SourceMailboxes.ps1
    ```

3. Quando viene richiesto dallo script, digitare il nome della ricerca di contenuto creata nel passaggio 1.
    
    Lo script consente di visualizzare il numero di cassette postali di origine che contengono i risultati della ricerca.
    
Se sono presenti più di 1.000 cassette postali di origine, provare a creare due (o più) ricerche di contenuto. Ad esempio, effettuare una ricerca di contenuto per una metà delle cassette postali dell'organizzazione ed effettuare un'altra ricerca di contenuto per l'altra metà. È inoltre possibile modificare i criteri di ricerca per ridurre il numero di cassette postali che contengono i risultati della ricerca. Ad esempio, è possibile includere un intervallo di date o affinare la query di parole chiave.
  
## <a name="step-2-connect-to-the-security--compliance-center-and-exchange-online-in-a-single-remote-powershell-session"></a>Passaggio 2: connettersi al centro conformità \& di sicurezza e a Exchange online in una singola sessione di PowerShell remota

Il passaggio successivo consiste nel connettere Windows PowerShell al centro sicurezza & compliance e all'organizzazione di Exchange Online. Questa operazione è necessaria perché lo script eseguito nel passaggio 3 richiede l'accesso ai cmdlet di ricerca contenuto nel centro sicurezza & compliance e nei cmdlet eDiscovery sul posto in Exchange Online.
  
1. Salvare il testo seguente in un file di script di Windows PowerShell con il suffisso del nome .ps1. Ad esempio, è possibile salvarlo in un file denominato `ConnectEXO-CC.ps1`.
    
    ```powershell
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -AllowClobber -DisableNameChecking
    $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Exchange Online + Compliance Center)"
    ```

2. Nel computer locale, aprire Windows PowerShell, passare alla cartella in cui si trova lo script creato nel passaggio precedente, quindi eseguire lo script. Per esempio:
    
    ```powershell
    .\ConnectEXO-CC.ps1
    ```

Come si può verificare se l'operazione ha avuto esito positivo? Dopo aver eseguito lo script, i cmdlet del Centro sicurezza & compliance e di Exchange Online vengono importati nella sessione di PowerShell locale. Se non vengono visualizzati errori, la connessione è stata eseguita correttamente. Un test rapido consiste nell'eseguire un cmdlet del Centro sicurezza & Compliance, ad esempio **Install-UnifiedCompliancePrerequisite** , e un cmdlet di Exchange Online, come **Get-Mailbox**. 
  
## <a name="step-3-run-the-script-to-create-an-in-place-ediscovery-search-from-the-content-search"></a>Passaggio 3: eseguire lo script per creare una ricerca eDiscovery sul posto dalla ricerca di contenuto

Dopo aver creato la sessione Dual PowerShell nel passaggio 2, il passaggio successivo consiste nell'eseguire uno script che convertirà una ricerca di contenuto esistente in una ricerca eDiscovery sul posto. In particolare, lo script:
  
- Richiede il nome della ricerca di contenuto da convertire.
    
- Verifica che la ricerca di contenuto abbia completato l'esecuzione. Se la ricerca di contenuto non restituisce risultati, non viene creata una ricerca eDiscovery sul posto.
    
- Salva un elenco di cassette postali di origine dalla ricerca di contenuto che contengono i risultati della ricerca per una variabile.
    
- Crea una nuova ricerca eDiscovery sul posto, con le proprietà riportate di seguito. La nuova ricerca non è stata avviata. È possibile avviarla nel passaggio 4.
    
  - **Nome** -il nome della nuova ricerca utilizza questo formato: \<nome della ricerca\>di contenuto _MBSearch1. Se si esegue di nuovo lo script e si utilizza la stessa ricerca del contenuto di origine, la \<ricerca sarà denominata nome\>della ricerca di contenuto _MBSearch2.
    
  - **Cassette postali di origine** : tutte le cassette postali dalla ricerca contenuto che contengono i risultati della ricerca. 
    
  - **Query di ricerca** -la nuova ricerca utilizza la query di ricerca dalla ricerca contenuto. Se la ricerca di contenuto include tutti i contenuti (la query di ricerca è vuota), la nuova ricerca potrà usufruire di una query di ricerca vuota e includerà tutti i contenuti trovati nelle cassette postali di origine. 
    
  - **Ricerca solo preventivo** : la nuova ricerca è contrassegnata come ricerca di sola stima. I risultati della ricerca non verranno copiati in una cassetta postale di individuazione dopo l'avvio. 
    
1. Salvare il testo seguente in un file di script di Windows PowerShell con il suffisso del nome ps1. Ad esempio, è possibile salvarlo in un file denominato `CreateMBSearchFromComplianceSearch.ps1`.
    
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

2. Nella sessione di Windows PowerShell creata al passaggio 2 passare alla cartella in cui si trova lo script creato nel passaggio precedente, quindi eseguire lo script. Per esempio:
    
    ```powershell
    .\CreateMBSearchFromComplianceSearch.ps1
    ```

3. Quando viene richiesto dallo script, digitare il nome della ricerca di contenuto che si desidera includere in una ricerca eDiscovery sul posto, ad esempio la ricerca creata al passaggio 1, e quindi premere **invio**.
    
    Se lo script ha esito positivo, viene creata una nuova ricerca eDiscovery sul posto con lo stato **NotStarted**. Eseguire il comando  `Get-MailboxSearch <Name of Content Search>_MBSearch1 | FL` per visualizzare le proprietà della nuova ricerca. 
  
## <a name="step-4-start-the-in-place-ediscovery-search"></a>Passaggio 4: avviare la ricerca eDiscovery sul posto

Lo script eseguito nel passaggio 3 crea una nuova ricerca eDiscovery sul posto, ma non la avvia. Il passaggio successivo consiste nell'avviare la ricerca, affinché sia possibile ottenere una stima dei risultati della ricerca.
  
1. In the Exchange admin center (EAC), go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.
    
2. Nella visualizzazione elenco, selezionare la ricerca eDiscovery sul posto creata nel passaggio 3.
    
3. ![](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif) \> Fare **clic su icona ricerca di** ricerca **stimare i risultati** della ricerca per avviare la ricerca e restituire una stima delle dimensioni totali e del numero di elementi restituiti dalla ricerca. 
    
    Le stime vengono visualizzate nel riquadro dei dettagli. ![Fare **clic su Aggiorna l'** icona](media/O365-MDM-Policy-RefreshIcon.gif) Aggiorna per aggiornare le informazioni visualizzate nel riquadro dei dettagli. 
    
4. Per visualizzare in anteprima i risultati dopo il completamento della ricerca, fare clic su **Anteprima risultati della ricerca** nel riquadro dei dettagli.
  
## <a name="next-steps-after-creating-and-running-the-in-place-ediscovery-search"></a>Passaggi successivi alla creazione e all'esecuzione della ricerca eDiscovery sul posto

Dopo aver avviato la ricerca eDiscovery sul posto creata dallo script nel passaggio 3, è possibile utilizzare il normale flusso di lavoro della ricerca eDiscovery sul posto per eseguire varie operazioni relative alla ricerca eDiscovery sui risultati della ricerca.
  
### <a name="create-an-in-place-hold"></a>Creare un blocco sul posto

1. In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.
    
2. Nella visualizzazione elenco, selezionare la ricerca eDiscovery sul posto creata nel passaggio 3, quindi fare clic su **modifica** ![icona](media/O365-MDM-CreatePolicy-EditIcon.gif)modifica.
    
3. Nella pagina **Blocco sul posto**, selezionare la casella di controllo **Blocca il contenuto delle cassette postali selezionate che corrisponde alla query di ricerca** e scegliere una delle seguenti opzioni: 
    
  - **Attesa illimitata** : selezionare questa opzione per inserire gli elementi restituiti dalla ricerca in un blocco indefinito. Gli elementi conservati verranno mantenuti fino a quando la cassetta postale non sarà stata rimossa dalla ricerca o non sarà stata eliminata la ricerca. 
    
  - **Specificare il numero di giorni in cui contenere gli elementi relativi alla data di ricezione** : scegliere questa opzione per conservare gli elementi per un periodo specifico. La durata viene calcolata a partire dalla data di ricezione o creazione dell'elemento della cassetta postale. 
    
4. Fare clic su **Salva** per creare il blocco sul posto e riavviare la ricerca. 
    
[Inizio pagina](use-content-search-in-ediscovery.md#top)
  
### <a name="copy-the-search-results"></a>Copiare i risultati della ricerca

1. In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.
    
2. Nella visualizzazione elenco, selezionare la ricerca eDiscovery sul posto creata nel passaggio 3.
    
3. Fare clic su icona](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif) **ricerca di** ricerca e quindi su **Copia risultati della ricerca** dall'elenco a discesa. ![ 
    
4. In **Copia risultati della ricerca**, scegliere una delle seguenti opzioni:
    
    - **Includi elementi non ricercabili** : selezionare questa casella di controllo per includere gli elementi della cassetta postale che non è stato possibile cercare (ad esempio, messaggi con allegati di tipi di file che non possono essere indicizzati dalla ricerca di Exchange). 
    
    - **Attiva la deduplicazione** : selezionare questa casella di controllo per escludere i messaggi duplicati. Nella cassetta postale di individuazione verrà copiata una sola istanza del messaggio. 
    
    - **Abilita registrazione completa** : selezionare questa casella di controllo per includere un registro completo nei risultati della ricerca. 
    
    - **Invio della posta elettronica quando la copia è stata completata** : selezionare questa casella di controllo per ricevere una notifica tramite posta elettronica al termine della ricerca. 
    
    - **Copiare i risultati in questa cassetta postale di individuazione** -fare clic su **Sfoglia** per selezionare la cassetta postale di individuazione in cui si desidera copiare i risultati della ricerca. 
    
5. Fare clic su **Copia** per avviare il processo per copiare i risultati della ricerca nella cassetta postale di individuazione specificata. 
    
6. ![Fare **clic su Aggiorna l'** icona](media/O365-MDM-Policy-RefreshIcon.gif) Aggiorna per aggiornare le informazioni sullo stato della copia visualizzate nel riquadro dei dettagli. 
    
7. Al termine della copia, fare clic su **Apri** per aprire la cassetta postale di individuazione e visualizzare i risultati della ricerca. 
  
### <a name="export-the-search-results"></a>Esportare i risultati della ricerca

1. In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.
    
2. Nella visualizzazione elenco, selezionare la ricerca eDiscovery sul posto creata nel passaggio 3, quindi fare clic su **Esporta in un file PST**.
    
3. Nella finestra **Strumento eDiscovery per esportazione PST** effettuare le seguenti operazioni: 
    
    - Fare clic su **Sfoglia** per specificare la posizione in cui si desidera scaricare il file PST. 
    
    - Selezionare la casella di controllo **Abilita deduplicazione** per escludere i messaggi duplicati. Il file PST conterrà una sola istanza di un messaggio. 
    
    - Selezionare la casella di controllo **Includi elementi senza funzioni di ricerca** per includere elementi non ricercabili, ad esempio messaggi con allegati di tipi di file non indicizzabili da parte di Ricerca di Exchange. Gli elementi non ricercabili vengono esportati in un file PST separato. 
    
4. Fare clic su **Start** per esportare i risultati della ricerca in un file PST. 
    
    Viene visualizzata una finestra contenente informazioni relative allo stato del processo di esportazione.
