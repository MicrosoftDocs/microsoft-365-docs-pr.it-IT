---
title: Perché è necessario usare PowerShell per Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: ''
ms.assetid: b3209b1a-40c7-4ede-8e78-8a88bb2adc8a
description: 'Riepilogo: comprendere il motivo per cui è necessario utilizzare PowerShell per gestire Microsoft 365, in alcuni casi in modo più efficiente e in altri casi per necessità.'
ms.openlocfilehash: d56a2cc47a06be911f1fd38aea3a557c631d2db0
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754107"
---
# <a name="why-you-need-to-use-powershell-for-microsoft-365"></a>Perché è necessario usare PowerShell per Microsoft 365

*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*

Con l'interfaccia di amministrazione di Microsoft 365, è possibile gestire gli account utente e le licenze di Microsoft 365. È inoltre possibile gestire i servizi Microsoft 365, ad esempio Exchange Online, teams e SharePoint Online. Se invece si utilizza PowerShell per gestire questi servizi, è possibile utilizzare l'ambiente della riga di comando e del linguaggio di scripting per velocizzare, automatizzare e rendere disponibili le funzionalità aggiuntive.
  
In questo articolo viene illustrato come utilizzare PowerShell per gestire Microsoft 365 per:
  
- Rivelare informazioni aggiuntive che non sono visibili nell'interfaccia di amministrazione di Microsoft 365
    
- Configurare le funzionalità e le impostazioni possibili solo con PowerShell
    
- Operazioni in blocco
    
- Filtrare i dati
    
- Stampa o salvataggio dei dati
    
- Gestire tra i servizi
    
Tenere presente che PowerShell per Microsoft 365 è un insieme di moduli per Windows PowerShell, che è un ambiente della riga di comando per i servizi e le piattaforme basati su Windows. Questo ambiente crea una lingua della shell dei comandi che può essere estesa con moduli aggiuntivi. Consente di eseguire comandi o script semplici o complessi. Ad esempio, dopo aver installato i moduli di PowerShell per Microsoft 365 e aver eseguito la connessione alla sottoscrizione Microsoft 365, è possibile eseguire il comando seguente per elencare tutte le cassette postali degli utenti per Microsoft Exchange Online:
  
```powershell
Get-Mailbox
```

È anche possibile ottenere l'elenco delle cassette postali utilizzando l'interfaccia di amministrazione di Microsoft 365 ma contando gli elementi in tutti gli elenchi di tutti i siti per tutte le app Web non è facile.
  
PowerShell per Microsoft 365 è stato creato per semplificare la gestione di Microsoft 365 e non per la sostituzione dell'interfaccia di amministrazione di Microsoft 365. Gli amministratori devono essere in grado di utilizzare PowerShell per Microsoft 365 perché esistono alcune procedure di configurazione che possono essere eseguite solo tramite PowerShell per i comandi di Microsoft 365. Per questi casi, è necessario sapere come eseguire le operazioni seguenti:
  
- Installare i moduli di PowerShell per Microsoft 365 (solo una volta per ogni computer di amministratore).
    
- Connettersi alla sottoscrizione Microsoft 365 (una volta per ogni sessione di PowerShell).
    
- Raccogliere le informazioni necessarie per eseguire i comandi di PowerShell necessari per Microsoft 365.
    
- Eseguire PowerShell per i comandi di Microsoft 365.
    
Dopo aver imparato queste abilità di base, non è necessario elencare gli utenti delle cassette postali utilizzando il comando **Get-Mailbox** . Inoltre, non è necessario capire come creare un nuovo comando come indicato in precedenza per contare tutti gli elementi in tutti gli elenchi di tutti i siti per tutte le app Web. Microsoft e la community degli amministratori possono aiutarti a svolgere le attività in base alle esigenze.
  
## <a name="powershell-for-microsoft-365-can-reveal-information-that-you-cant-see-with-the-microsoft-365-admin-center"></a>PowerShell per Microsoft 365 è in grado di rivelare informazioni che non sono visibili con l'interfaccia di amministrazione di Microsoft 365

L'interfaccia di amministrazione di Microsoft 365 Visualizza numerose informazioni utili. Tuttavia, non vengono visualizzate tutte le informazioni possibili che Microsoft 365 archivia sugli utenti, le licenze, le cassette postali e i siti. Di seguito è riportato un esempio per *gli utenti e i gruppi* nell'interfaccia di amministrazione di Microsoft 365:
  
![Esempio di visualizzazione di utenti e gruppi nell'interfaccia di amministrazione di Microsoft 365.](../media/o365-powershell-users-and-groups.png)
  
In questa visualizzazione vengono fornite le informazioni necessarie in molti casi. Tuttavia, in alcuni casi sono necessarie informazioni aggiuntive. Ad esempio, le licenze Microsoft 365 (e le funzionalità di Microsoft 365 disponibili per un utente) dipendono in parte dalla posizione geografica dell'utente. I criteri e le funzionalità che possono essere estesi a un utente che vive negli Stati Uniti potrebbero non essere uguali a quelli che è possibile estendere a un utente in India o in Belgio. Attenersi alla seguente procedura nell'interfaccia di amministrazione di Microsoft 365 per determinare la posizione geografica di un utente:
  
1. Fare doppio clic sul **Nome visualizzato** dell'utente.
    
2. Nel riquadro di visualizzazione proprietà utente, selezionare **Dettagli**.
    
3. Nella visualizzazione dettagli, fare clic su **ulteriori dettagli**.
    
4. Scorrere fino a individuare il **paese o l'area geografica**del titolo:
    
     ![Esempio di informazioni sull'area geografica per un utente nell'interfaccia di amministrazione di Microsoft 365.](../media/o365-powershell-usage-location.png)
  
5. Prendere nota del nome visualizzato e della posizione dell'utente su un pezzo di carta o copiarlo e incollarlo nel Blocco note.
    
È necessario ripetere questa procedura per ogni utente. Se si dispone di numerosi utenti, questo processo può essere noioso. Con PowerShell per Microsoft 365, è possibile visualizzare queste informazioni per tutti gli utenti utilizzando il comando seguente:
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```


>[!Note]
>PowerShell Core non supporta il modulo di Microsoft Azure Active Directory per il modulo di Windows PowerShell e i cmdlet che dispongono di *MSOL* nel proprio nome. È necessario eseguire questi cmdlet da Windows PowerShell.
>

Di seguito è riportato un esempio dei risultati:
  
```powershell
DisplayName                               UsageLocation
-----------                               -------------
Bonnie Kearney                            GB
Fabrice Canel                             BR
Brian Johnson (TAILSPIN)                  US
Anne Wallace                              US
Alex Darrow                               US
David Longmuir                            BR
```

L'interpretazione di questo comando di PowerShell è: recuperare tutti gli utenti nella sottoscrizione Microsoft 365 corrente (**Get-AzureADUser**), ma visualizzare solo il nome e la posizione di ogni utente (**Select DisplayName, UsageLocation**).
  
Poiché PowerShell per Microsoft 365 supporta una lingua della shell dei comandi, è possibile modificare ulteriormente le informazioni ottenute tramite il comando **Get-AzureADUser** . Ad esempio, potrebbe essere necessario ordinare gli utenti in base alla posizione, raggruppando tutti gli utenti brasiliani insieme, tutti gli utenti degli Stati Uniti e così via. Di seguito è riportato il comando:
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation | Sort UsageLocation, DisplayName
```

Di seguito è riportato un esempio dei risultati:
  
```powershell
DisplayName                                 UsageLocation
-----------                                 -------------
David Longmuir                              BR
Fabrice Canel                               BR
Bonnie Kearney                              GB
Alex Darrow                                 US
Anne Wallace                                US
Brian Johnson (TAILSPIN)                    US
```

L'interpretazione di questo comando di PowerShell è: recuperare tutti gli utenti nella sottoscrizione Microsoft 365 corrente, ma visualizzare solo il nome e la posizione di ogni utente e ordinarli in primo luogo in base alla posizione e quindi al nome (**Sort UsageLocation, DisplayName**).
  
È inoltre possibile utilizzare ulteriori filtri. Ad esempio, se si desidera visualizzare tali informazioni sugli utenti residenti in Brasile, utilizzare questo comando:
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq "BR"} | Select DisplayName, UsageLocation 
```

Di seguito è riportato un esempio dei risultati:
  
```powershell
DisplayName                                           UsageLocation
-----------                                           -------------
David Longmuir                                        BR
Fabrice Canel                                         BR
```

L'interpretazione di questo comando di PowerShell è: recuperare tutti gli utenti nella sottoscrizione Microsoft 365 corrente la cui posizione è il Brasile (**dove {$ \_ . UsageLocation-EQ "BR"}**), quindi vengono visualizzati il nome e la posizione di ogni utente.
  
 **Nota sui domini di grandi dimensioni**
  
Se si dispone di un dominio di grandi dimensioni con decine di migliaia di utenti, provare alcuni degli esempi illustrati in questo articolo potrebbe portare alla limitazione. In base a fattori quali la potenza di calcolo e la larghezza di banda di rete disponibile, è possibile che si stia tentando di fare troppo contemporaneamente. Per le organizzazioni di grandi dimensioni potrebbe essere necessario dividere alcune di queste operazioni di PowerShell in due comandi.

Ad esempio, il comando seguente restituisce tutti gli account utente e visualizza il nome e il percorso di ognuno di essi:
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```

Questa operazione funziona perfettamente per i domini più piccoli. Tuttavia, in un'organizzazione di grandi dimensioni, potrebbe essere necessario suddividere l'operazione in due comandi: un comando per archiviare le informazioni sull'account utente in una variabile e un'altra per visualizzare le informazioni necessarie. Di seguito viene riportato un esempio:
  
```powershell
$x = Get-AzureADUser
$x | Select DisplayName, UsageLocation
```

L'interpretazione di questo set di comandi di PowerShell è la seguente:
1. Ottenere tutti gli utenti nella sottoscrizione Microsoft 365 corrente e archiviare le informazioni in una variabile denominata $x (**$x = Get-AzureADUser**).
1.  Visualizzare il contenuto della variabile *$x*, ma includere solo il nome e la posizione di ogni utente (**$x | Selezionare DisplayName, UsageLocation**).
  
## <a name="microsoft-365-has-features-that-you-can-only-configure-with-powershell-for-microsoft-365"></a>Microsoft 365 dispone di funzionalità che è possibile configurare solo con PowerShell per Microsoft 365

L'interfaccia di amministrazione di Microsoft 365 ha lo scopo di consentire l'accesso a attività amministrative comuni e utili per la maggior parte degli ambienti. In altre parole, l'interfaccia di amministrazione di Microsoft 365 è stata progettata in modo che l'amministratore tipico possa eseguire le attività di gestione più comuni. Tuttavia, esistono alcune attività che non possono essere eseguite nell'interfaccia di amministrazione.
  
Ad esempio, l'interfaccia di amministrazione di Skype for business online offre alcune opzioni per la creazione di inviti a riunioni personalizzate:
  
![Esempio di visualizzazione di inviti personalizzati a riunioni nell’interfaccia di amministrazione di Skype for Business online.](../media/o365-powershell-meeting-invitation.png)
  
Con queste impostazioni, è possibile aggiungere un tocco di personalizzazione e professionalità alle convocazioni di riunioni. Tuttavia, per le impostazioni di configurazione delle riunioni non è sufficiente creare inviti alle riunioni personalizzati. Ad esempio, per impostazione predefinita le riunioni consentono:
  
- A utenti anonimi di ottenere l'ingresso automatico a ogni riunione.
    
- Ai partecipanti di registrare una riunione.
    
- A tutti gli utenti dell'organizzazione di essere designati come relatori quando partecipano a riunione.
    
Queste impostazioni non sono disponibili nell'interfaccia di amministrazione di Skype for business online. È possibile controllarli da PowerShell per Microsoft 365. Di seguito viene riportato un comando che disabilita queste tre impostazioni:
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False -AllowConferenceRecording $False -DesignateAsPresenter "None"
```

> [!NOTE]
> Per eseguire questo comando, è necessario installare il [modulo di PowerShell di Skype for business online ](https://www.microsoft.com/download/details.aspx?id=39366).
  
L'interpretazione di questo comando di PowerShell è la seguente:
 
1. Nelle impostazioni per le nuove riunioni di Skype for business online (**Set-CsMeetingConfiguration**), disabilitare la possibilità di consentire agli utenti anonimi di ottenere l'accesso automatico alle riunioni (**-AdmitAnonymousUsersByDefault $false**).
2.  Disabilitare la possibilità per i partecipanti di registrare le riunioni (**-AllowConferenceRecording $false**).
3. Non designare tutti gli utenti dell'organizzazione come relatori (**-DesignateAsPresenter "None"**).
  
Per ripristinare le impostazioni predefinite (abilitare le opzioni), eseguire il comando seguente:
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $True -AllowConferenceRecording $True -DesignateAsPresenter "Company"
```

Esistono anche altri scenari analoghi, che è il motivo per cui gli amministratori dovrebbero sapere come eseguire PowerShell per i comandi di Microsoft 365.
  
## <a name="powershell-for-microsoft-365-is-great-for-bulk-operations"></a>PowerShell per Microsoft 365 è ideale per le operazioni in blocco

Le interfacce visive come l'interfaccia di amministrazione di Microsoft 365 sono estremamente utili quando si ha a che fare con un'unica operazione. Ad esempio, se è necessario disabilitare un account utente, è possibile utilizzare l'interfaccia di amministrazione per individuare e cancellare rapidamente una casella di controllo. Potrebbe essere più facile che eseguire un'operazione analoga in PowerShell.
  
Tuttavia, se è necessario modificare molte cose o alcuni elementi selezionati all'interno di un insieme di grandi dimensioni, è possibile che l'interfaccia di amministrazione di Microsoft 365 non sia lo strumento migliore. Ad esempio, si supponga di dover cambiare il prefisso su migliaia di numeri di telefono o di rimuovere l'utente specifico *Ken* resite da tutti i siti di SharePoint Online. Come è possibile eseguire questa operazione nell'interfaccia di amministrazione di Microsoft 365?
  
Per l'ultimo esempio, si supponga che siano disponibili diverse centinaia di siti di SharePoint Online e che non si conoscano quelli di cui è membro Ken Meyer. È necessario avviare l'interfaccia di amministrazione di Microsoft 365 e quindi eseguire questa procedura per ogni sito:
  
1. Selezionare l' **URL** del sito.
    
2. Nella casella **Proprietà raccolta siti** selezionare il collegamento **Indirizzo sito Web** per aprire il sito.
    
3. Nel sito selezionare **Condividi**.
    
4. Nella finestra di dialogo **Condividi** , selezionare il collegamento che consente di visualizzare tutti gli utenti che dispongono delle autorizzazioni per il sito:
    
     ![Esempio di visualizzazione di membri del sito SharePoint Online nell'interfaccia di amministrazione di SharePoint Online.](../media/o365-powershell-view-permissions.png)
  
5. Nella finestra **di dialogo condiviso con** selezionare **Avanzate**.
    
6. Scorrere l'elenco degli utenti, trovare e selezionare Ken (supponendo che disponga delle autorizzazioni per il sito) e quindi selezionare **Rimuovi autorizzazioni utente**.
    
Questo richiederebbe *molto* tempo per diverse centinaia di siti.
  
L'alternativa consiste nell'eseguire il seguente comando in PowerShell per Microsoft 365 per rimuovere Ken remario da tutti i siti:
  
```powershell
Get-SPOSite | ForEach {Remove-SPOUser -Site $_.Url -LoginName "kenmyer@litwareinc.com"}
```

> [!NOTE]
> Questo comando richiede l'installazione del [modulo di PowerShell di SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps). 
  
L'interpretazione di questo comando di PowerShell è: recuperare tutti i siti di SharePoint nella sottoscrizione Microsoft 365 corrente (**Get-SPOSite**) e per ogni sito rimuovere Ken Meyer dall'elenco degli utenti che possono accedervi (**foreach {Remove-consorter-site $ \_ . URL-LoginName "kenmyer \@ litwareinc.com"}**).
  
Diciamo a Microsoft 365 di rimuovere Ken Meyer da ogni sito, compresi quelli a cui non ha accesso. In questo modo, i risultati visualizzeranno gli errori per i siti a cui non è consentito l'accesso. È possibile utilizzare una condizione aggiuntiva su questo comando per rimuovere Ken Meyer solo dai siti che lo dispongono nell'elenco di accesso. Tuttavia, gli errori restituiti non causano danni per i siti stessi. Questo comando potrebbe richiedere alcuni minuti per l'esecuzione in centinaia di siti anziché ore di utilizzo dell'interfaccia di amministrazione di Microsoft 365.
  
Di seguito è riportato un altro esempio di operazione in blocco. Utilizzare questo comando per aggiungere *Bonnie Kearney*, un nuovo amministratore di SharePoint, a tutti i siti dell'organizzazione:
  
```powershell
Get-SPOSite | ForEach {Add-SPOUser -Site $_.Url -LoginName "bkearney@litwareinc.com" -Group "Members"}
```

L'interpretazione di questo comando di PowerShell è: recuperare tutti i siti di SharePoint nella sottoscrizione Microsoft 365 corrente e per ogni sito consentire a Bonnie Kearney Access aggiungendo il nome di accesso al gruppo membri del sito (**foreach {Add-Consorter-site $ \_ . URL-LoginName "bkearney \@ litwareinc.com"-gruppo "membri"}**).
  
## <a name="powershell-for-microsoft-365-is-great-at-filtering-data"></a>PowerShell per Microsoft 365 è ottimo per filtrare i dati

L'interfaccia di amministrazione di Microsoft 365 offre diversi modi per filtrare i dati in modo da individuare facilmente un sottoinsieme di informazioni mirato. Ad esempio, Exchange facilita il filtro di qualsiasi proprietà relativa alla cassetta postale di un utente. Ad esempio, di seguito è riportato l'elenco delle cassette postali per tutti gli utenti che vivono nella città di Bloomington:
  
![Esempio di ricerca avanzata nell'interfaccia di amministrazione di Microsoft 365 per l'elenco delle cassette postali per tutti gli utenti che vivono nella città di Bloomington.](../media/o365-powershell-advanced-search.png)
  
L'interfaccia di amministrazione di Exchange consente di combinare i criteri di filtro. Ad esempio, è possibile trovare le cassette postali per tutte le persone che vivono in Bloomington e lavorano nel reparto Finanza.
  
Tuttavia, è possibile eseguire limitazioni nell'interfaccia di amministrazione di Exchange. Ad esempio, non è possibile trovare facilmente le cassette postali di persone che vivono in Bloomington *o* San Diego o le cassette postali per tutte le persone che non vivono in Bloomington.
  
Per ottenere un elenco delle cassette postali per tutte le persone che vivono in Bloomington o San Diego, è possibile utilizzare il seguente comando di PowerShell per Microsoft 365:
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and ($_.City -eq "San Diego" -or $_.City -eq "Bloomington")} | Select DisplayName, City
```

Di seguito è riportato un esempio dei risultati:
  
```powershell
DisplayName                              City
-----------                              ----
Alex Darrow                              San Diego
Bonnie Kearney                           San Diego
Julian Isla                              Bloomington
Rob Young                                Bloomington
```

L'interpretazione di questo comando di PowerShell è: recuperare tutti gli utenti nell'attuale sottoscrizione di Microsoft 365 che dispongono di una cassetta postale nella città di San Diego o Bloomington (**dove {$ \_ . RecipientTypeDetails-EQ "UserMailbox"-and ($ \_ . City-EQ "San Diego"-oppure $ \_ . City-EQ "Bloomington")}**), quindi visualizzare il nome e la città per ognuno (**selezionare DisplayName, City**).
  
Ed ecco il comando per elencare tutte le cassette postali per le persone che vivono ovunque tranne Bloomington:
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and $_.City -ne "Bloomington"} | Select DisplayName, City
```

Di seguito è riportato un esempio dei risultati:
  
```powershell
DisplayName                               City
-----------                               ----
MOD Administrator                         Redmond
Alex Darrow                               San Diego
Allie Bellew                              Bellevue
Anne Wallace                              Louisville
Aziz Hassouneh                            Cairo
Belinda Newman                            Charlotte
Bonnie Kearney                            San Diego
David Longmuir                            Waukesha
Denis Dehenne                             Birmingham
Garret Vargas                             Seattle
Garth Fort                                Tulsa
Janet Schorr                              Bellevue
```

L'interpretazione di questo comando di PowerShell è: recuperare tutti gli utenti nell'attuale sottoscrizione di Microsoft 365 che dispongono di una cassetta postale che non si trova nella città di Bloomington (**dove {$ \_ . RecipientTypeDetails-EQ "UserMailbox"-e $ \_ . City-ne "Bloomington"}**), quindi visualizzare il nome e la città per ognuno di essi.
  
### <a name="use-wildcards"></a>Utilizzo di caratteri jolly

È inoltre possibile utilizzare i caratteri jolly nei filtri di PowerShell per far corrispondere parte di un nome. Ad esempio, si supponga di essere alla ricerca di un account utente. Tutto quello che è possibile ricordare è che il cognome dell'utente era *Anderson* o forse *Henderson* o *Jorgenson*.
  
È possibile rintracciare l'utente nell'interfaccia di amministrazione di Microsoft 365 utilizzando lo strumento di ricerca ed effettuando tre ricerche diverse:
  
- Una per  *Anderson* 
    
- Una per  *Henderson* 
    
- Una per  *Jorgenson* 
    
Poiché tutti e tre questi nomi terminano con "son", è possibile indicare a PowerShell di visualizzare tutti gli utenti il cui nome termina con "son". Di seguito è riportato il comando:
  
```powershell
Get-User -Filter '{LastName -like "*son"}'
```

L'interpretazione di questo comando di PowerShell è: recuperare tutti gli utenti nella sottoscrizione Microsoft 365 corrente, ma utilizzare un filtro che elenca solo gli utenti i cui cognomi terminano con "son" (**-Filter ' {LastName-like " \* son"}'**). Lo \* stand per qualsiasi set di caratteri, ovvero lettere nel cognome dell'utente.
  
## <a name="powershell-for-microsoft-365-makes-it-easy-to-print-or-save-data"></a>PowerShell per Microsoft 365 rende più semplice la stampa o il salvataggio dei dati

L'interfaccia di amministrazione di Microsoft 365 consente di visualizzare gli elenchi di dati. Di seguito è riportato un esempio dell'interfaccia di amministrazione di Skype for business online in cui viene visualizzato un elenco di utenti abilitati per Skype for business online:
  
![Esempio di interfaccia di amministrazione di Skype for Business online che mostra un elenco di utenti abilitati a Skype for Business online.](../media/o365-powershell-lync-users.png)
  
Per salvare tali informazioni in un file, è necessario incollarlo in un foglio di lavoro di documento o di Microsoft Excel. In entrambi i casi potrebbe essere necessaria una formattazione aggiuntiva. Inoltre, l'interfaccia di amministrazione di Microsoft 365 non consente di stampare direttamente l'elenco visualizzato.
  
Fortunatamente, è possibile utilizzare PowerShell per non solo visualizzare l'elenco ma per salvarlo in un file che può essere importato facilmente in Excel. Di seguito è riportato un comando di esempio per salvare i dati degli utenti di Skype for business online in un file con valori delimitati da virgole (CSV), che può essere importato facilmente come tabella in un foglio di lavoro di Excel:
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Export-Csv -Path "C:\Logs\SfBUsers.csv" -NoTypeInformation
```

Di seguito è riportato un esempio dei risultati:
  
![Esempio di una tabella importata in un foglio di lavoro di Excel per i dati degli utenti di Skype for business online salvati in un file con valori delimitati da virgole.](../media/o365-powershell-data-in-excel.png)
  
L'interpretazione di questo comando di PowerShell è: ottenere tutti gli utenti di Skype for business online nella sottoscrizione Microsoft 365 corrente (**Get-CsOnlineUser**); ottenere solo il nome utente, l'UPN e la posizione (**selezionare DisplayName, userPrincipalName, UsageLocation**); e quindi salvare le informazioni in un file CSV denominato C: \\ logs \\SfBUsers.csv (**Export-CSV-path "c: \\ logs \\SfBUsers.csv"-NoTypeInformation**).
  
È inoltre possibile utilizzare le opzioni per salvare questo elenco come un file XML o una pagina HTML. Infatti, con ulteriori comandi di PowerShell, è possibile salvarlo direttamente come file di Excel, con qualsiasi formattazione personalizzata desiderata.
  
È anche possibile inviare l'output di un comando di PowerShell che consente di visualizzare un elenco direttamente alla stampante predefinita in Windows. Di seguito è riportato un comando di esempio:
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Out-Printer
```

Di seguito, è riportato l'aspetto del documento stampato:
  
![Esempio di un documento stampato che è stato l'output di un comando di PowerShell inviato direttamente alla stampante predefinita in Windows.](../media/o365-powershell-printed-data.png)
  
L'interpretazione di questo comando di PowerShell è: ottenere tutti gli utenti di Skype for business online nella sottoscrizione Microsoft 365 corrente; ottenere solo il nome utente, l'UPN e la posizione. e quindi invia queste informazioni alla stampante predefinita di Windows (**fuori stampante**).
  
Il documento stampato ha la stessa formattazione semplice della visualizzazione nella finestra di comando di PowerShell. Per ottenere una copia cartacea, è sufficiente aggiungere **| Out-Printer** alla fine del comando.
  
## <a name="powershell-for-microsoft-365-lets-you-manage-across-server-products"></a>PowerShell per Microsoft 365 consente di gestire diversi prodotti server

I componenti che compongono Microsoft 365 sono stati concepiti per funzionare insieme. Si supponga, ad esempio, di aggiungere un nuovo utente a Microsoft 365 e di specificare tali informazioni come reparto e numero di telefono dell'utente. Tali informazioni saranno quindi disponibili se si accede alle informazioni dell'utente in uno dei servizi Microsoft 365: Skype for business online, Exchange o SharePoint.
  
Si tratta di informazioni generali che interessano la famiglia di prodotti. Le informazioni specifiche del prodotto, ad esempio le informazioni relative alla cassetta postale di Exchange di un utente, non sono in genere disponibili in tutta la famiglia. Ad esempio, le informazioni sull'abilitazione o meno della cassetta postale di un utente sono disponibili solo nell'interfaccia di amministrazione di Exchange.
  
Si supponga di voler creare un report che mostra le seguenti informazioni per tutti gli utenti:
  
- Nome visualizzato dell'utente
    
- Se l'utente ha una licenza per Microsoft 365
    
- L'abilitazione della cassetta postale di Exchange dell'utente.
    
- L'abilitazione per Skype for Business online dell'utente
    
Non è possibile produrre facilmente un rapporto di questo tipo nell'interfaccia di amministrazione di Microsoft 365. In alternativa, è necessario creare un documento distinto per archiviare le informazioni, ad esempio un foglio di lavoro di Excel. Ottenere quindi tutti i nomi utente e le informazioni di licenza dall'interfaccia di amministrazione di Microsoft 365, ottenere informazioni sulla cassetta postale dall'interfaccia di amministrazione di Exchange, ottenere informazioni su Skype for business online dall'interfaccia di amministrazione di Skype for business online e quindi combinare tali informazioni.
  
L'alternativa consiste nell'usare uno script di PowerShell per compilare il report.
  
Lo script di esempio seguente è più complesso rispetto ai comandi visualizzati finora in questo articolo. Tuttavia, dimostra la possibilità di utilizzare PowerShell per creare visualizzazioni di informazioni difficilmente ottenibili in altro modo. Ecco lo script per compilare e visualizzare l'elenco di cui hai bisogno:
  
```powershell
$x = Get-AzureADUser

foreach ($i in $x)
    {
      $y = Get-Mailbox -Identity $i.UserPrincipalName
      $i | Add-Member -MemberType NoteProperty -Name IsMailboxEnabled -Value $y.IsMailboxEnabled

      $y = Get-CsOnlineUser -Identity $i.UserPrincipalName
      $i | Add-Member -MemberType NoteProperty -Name EnabledForSfB -Value $y.Enabled
    }

$x | Select DisplayName, IsLicensed, IsMailboxEnabled, EnabledforSfB
```

Di seguito è riportato un esempio dei risultati:
  
```powershell
DisplayName             IsLicensed   IsMailboxEnabled   EnabledForSfB
-----------             ----------   ----------------   --------------
Bonnie Kearney          True         True               True
Fabrice Canel           True         True               True
Brian Johnson           False        True               False
Anne Wallace            True         True               True
Alex Darrow             True         True               True
David Longmuir          True         True               True
Katy Jordan             False        True               False
Molly Dempsey           False        True               False
```

L'interpretazione di questo script di PowerShell è la seguente:  

1. Ottenere tutti gli utenti nella sottoscrizione Microsoft 365 corrente e archiviare le informazioni in una variabile denominata *$x* (**$x = Get-AzureADUser**).
1. Avviare un ciclo che viene eseguito su tutti gli utenti nella variabile $x (**foreach ($i in $x)**).  
1. Definire una variabile denominata *$y* e archiviarvi le informazioni sulla cassetta postale dell'utente (**$y = Get-Mailbox-Identity $i. userPrincipalName**).
1. Aggiungere una nuova proprietà alle informazioni utente denominate *IsMailBoxEnabled*. Impostarla sul valore della proprietà IsMailBoxEnabled della cassetta postale dell'utente (**$i | Add-Member-MemberType NoteProperty-Name IsMailBoxEnabled-value $y. IsMailBoxEnabled**).
1. Definire una variabile denominata *$y*e archiviare le informazioni di Skype for business online dell'utente (**$y = Get-CsOnlineUser-Identity $i. userPrincipalName**).
1. Aggiungere una nuova proprietà alle informazioni utente denominate *EnabledForSfB*. Impostarla sul valore della proprietà Enabled delle informazioni di Skype for business online dell'utente (**$i | Add-Member-MemberType NoteProperty-Name EnabledForSfB-value $y. Enabled**).
1. Visualizzare l'elenco degli utenti, ma includere solo il nome, se sono concessi in licenza, e le due nuove proprietà che indicano se la propria cassetta postale è abilitata e se sono abilitati per Skype for business online (**$x | Selezionare DisplayName, con licenza, IsMailboxEnabled, EnabledforSfB**).
  
## <a name="see-also"></a>Vedere anche

[Guida introduttiva a PowerShell per Microsoft 365](getting-started-with-microsoft-365-powershell.md)
  
[Gestire gli account utente, le licenze e i gruppi di Microsoft 365 con PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Usare Windows PowerShell per creare report in Microsoft 365](use-windows-powershell-to-create-reports-in-microsoft-365.md)
