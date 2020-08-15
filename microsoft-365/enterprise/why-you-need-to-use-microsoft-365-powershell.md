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
ms.openlocfilehash: 7220356cd79b03674661ace386fd1d38a7e39587
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690974"
---
# <a name="why-you-need-to-use-powershell-for-microsoft-365"></a>Perché è necessario usare PowerShell per Microsoft 365

*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*

Con l'interfaccia di amministrazione di Microsoft 365, è possibile non solo gestire gli account utente e le licenze di Microsoft 365, ma è anche possibile gestire i servizi Microsoft 365 quali Exchange Online, teams e SharePoint Online. Tuttavia, è anche possibile gestire questi elementi con i comandi di PowerShell, sfruttando un ambiente di gestione della riga di comando e di scripting per velocità, automazione e funzionalità aggiuntive.
  
In questo articolo verranno illustrati i modi in cui è possibile utilizzare PowerShell per gestire Microsoft 365:
  
- Rivelare informazioni aggiuntive che non sono visibili con l'interfaccia di amministrazione di Microsoft 365
    
- Configurare le funzionalità e le impostazioni possibili solo con PowerShell
    
- Eseguire operazioni in blocco
    
- Filtro dei dati
    
- Stampa o salvataggio dei dati
    
- Gestire tra i servizi
    
Prima di iniziare, è necessario comprendere che PowerShell per Microsoft 365 è un insieme di moduli per Windows PowerShell, un ambiente della riga di comando per i servizi e le piattaforme basati su Windows. Questo ambiente crea una lingua della shell dei comandi che può essere estesa con moduli aggiuntivi e consente di eseguire comandi o script semplici o complessi. Ad esempio, dopo aver installato i moduli di PowerShell per Microsoft 365 e aver eseguito la connessione alla sottoscrizione Microsoft 365, è possibile eseguire questo comando per elencare tutte le cassette postali degli utenti per Microsoft Exchange Online:
  
```powershell
Get-Mailbox
```

La possibilità di ottenere l'elenco delle cassette postali può essere completata facilmente utilizzando l'interfaccia di amministrazione di Microsoft 365, ma il conteggio del numero di elementi in tutti gli elenchi di tutti i siti per tutte le app Web non può essere effettuato facilmente.
  
Tenere presente che PowerShell per Microsoft 365 è stato creato per aumentare e migliorare la capacità di gestire Microsoft 365, non per sostituire l'interfaccia di amministrazione di Microsoft 365. In qualità di amministratore, è necessario essere almeno a proprio agio nell'utilizzo di PowerShell per Microsoft 365 perché esistono alcune procedure di configurazione che è possibile eseguire solo con i comandi di PowerShell per Microsoft 365. In questi casi, verrà richiesto di conoscere le procedure per effettuare le seguenti operazioni:
  
- Installare i moduli di PowerShell per Microsoft 365 (eseguiti solo una volta per ogni computer di amministratore).
    
- Connettersi alla sottoscrizione Microsoft 365 (operazione eseguita una sola volta per ogni sessione di PowerShell).
    
- Raccogliere le informazioni necessarie per eseguire i comandi di PowerShell necessari per Microsoft 365.
    
- Eseguire correttamente i comandi di PowerShell per Microsoft 365.
    
Dopo aver appreso le competenze di base, non è necessario elencare gli utenti delle cassette postali con il comando **Get-Mailbox**, né saper creare un nuovo comando simile a quello precedente per contare tutti gli elementi in tutti gli elenchi di tutti i siti per tutte le app Web. Microsoft e la community di amministratori possono aiutarti in base alle esigenze.
  
## <a name="powershell-for-microsoft-365-can-reveal-additional-information-that-you-cannot-see-with-the-microsoft-365-admin-center"></a>PowerShell per Microsoft 365 è in grado di rivelare informazioni aggiuntive che non sono visibili con l'interfaccia di amministrazione di Microsoft 365

L'interfaccia di amministrazione di Microsoft 365 Visualizza molte informazioni utili, ma ciò non significa che Visualizza tutte le informazioni possibili che Microsoft 365 archivia su utenti, licenze, cassette postali e siti. Di seguito è riportato un esempio per **gli utenti e i gruppi** nell'interfaccia di amministrazione di Microsoft 365:
  
![Esempio di visualizzazione di utenti e gruppi nell'interfaccia di amministrazione di Microsoft 365.](../media/o365-powershell-users-and-groups.png)
  
Per diversi scopi, verranno visualizzate le informazioni necessarie. Tuttavia, in alcuni casi sono necessarie informazioni aggiuntive. Ad esempio, le licenze Microsoft 365 (e le funzionalità di Microsoft 365 disponibili per un utente) dipendono in parte dalla posizione geografica dell'utente. I criteri e le funzionalità che è possibile estendere a un utente che vive negli Stati Uniti potrebbero non essere gli stessi per un utente che risiede in India o Belgio. È possibile utilizzare l'interfaccia di amministrazione di Microsoft 365 per determinare la posizione geografica di un utente con questa procedura:
  
1. Fare doppio clic sul **Nome visualizzato** dell'utente.
    
2. Nelle proprietà del riquadro di visualizzazione dell'utente, fare clic su **Dettagli**.
    
3. Nella visualizzazione dettagli, fare clic su **ulteriori dettagli**.
    
4. Scorrere verso il basso fino a quando non viene visualizzata l'intestazione **Paese o regione**:
    
     ![Esempio di informazioni sull'area geografica per un utente nell'interfaccia di amministrazione di Microsoft 365.](../media/o365-powershell-usage-location.png)
  
5. Prendere nota del nome visualizzato e della posizione dell'utente su un pezzo di carta o copiarlo e incollarlo nel Blocco note. 
    
È necessario ripetere questa procedura per ogni utente. Per molti utenti, potrebbe trattarsi di un'attività noiosa. Con PowerShell per Microsoft 365, è possibile visualizzare queste informazioni per tutti gli utenti con il seguente comando:
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```


>[!Note]
>PowerShell Core non supporta il modulo di Microsoft Azure Active Directory per Windows PowerShell e i cmdlet con **MSOL** all'interno del nome. Per continuare a usare i cmdlet, è necessario eseguirli in Windows PowerShell.
>

Ecco un esempio di visualizzazione:
  
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

> [!TIP]
>  L'interpretazione di questo comando di PowerShell è: recuperare tutti gli utenti nella sottoscrizione Microsoft 365 corrente ( **Get-AzureADUser** ), ma visualizzare solo il nome e la posizione di ogni utente ( **Select DisplayName, UsageLocation** ).
  
Poiché PowerShell per Microsoft 365 supporta una lingua di shell dei comandi, è possibile modificare ulteriormente le informazioni ottenute dal comando **Get-AzureADUser** . Ad esempio, se si desidera ordinare gli utenti in base alla propria posizione, raggruppare tutti gli utenti brasiliani insieme, tutti gli utenti degli Stati Uniti e così via. Di seguito è riportato il comando:
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation | Sort UsageLocation, DisplayName
```

Ecco un esempio di visualizzazione:
  
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

> [!TIP]
>  L'interpretazione di questo comando di PowerShell è: recuperare tutti gli utenti nella sottoscrizione Microsoft 365 corrente, ma visualizzare solo il nome e la posizione di ogni utente e ordinarli in primo luogo in base alla posizione e quindi ai rispettivi nomi ( **Sort UsageLocation, DisplayName** ).
  
È inoltre possibile utilizzare altre opzioni di filtro. Ad esempio, se si desidera visualizzare tali informazioni sugli utenti residenti in Brasile, utilizzare questo comando:
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq "BR"} | Select DisplayName, UsageLocation 
```

Ecco un esempio di visualizzazione:
  
```powershell
DisplayName                                           UsageLocation
-----------                                           -------------
David Longmuir                                        BR
Fabrice Canel                                         BR
```

> [!TIP]
>  L'interpretazione di questo comando di PowerShell è: recuperare tutti gli utenti nella sottoscrizione Microsoft 365 corrente la cui posizione è il Brasile ( **dove {$ \_ . UsageLocation-EQ "BR"}** ), quindi visualizzare il nome e la posizione di ogni utente.
  
 **Nota rapida riguardo i domini più grandi**
  
Se si dispone di un dominio di grandi dimensioni, con decine di migliaia di utenti, alcuni degli esempi mostrati in questo articolo potrebbero causare una "limitazione". Ciò significa che, in base a dati come la potenza di elaborazione e lunghezza di banda disponibile, si sta cercando di effettuare troppe operazioni contemporaneamente. Per questo motivo, le organizzazioni di grandi dimensioni potrebbero voler dividere alcuni di questi comandi PowerShell per Microsoft 365 in due comandi. Ad esempio, questo comando restituisce tutti gli account utente e mostra il nome e la posizione di ciascun utente:
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```

Questa operazione funziona perfettamente per i domini più piccoli. Nelle organizzazioni di grandi dimensioni, tuttavia, potrebbe essere necessario dividerlo in due comandi: un comando per archiviare le informazioni sugli account utente in una variabile, l'altro per visualizzare le informazioni necessarie. Ecco un esempio:
  
```powershell
$x = Get-AzureADUser
$x | Select DisplayName, UsageLocation
```

L'interpretazione di questo set di comandi di PowerShell è la seguente:
- Ottenere tutti gli utenti nella sottoscrizione Microsoft 365 corrente e archiviare le informazioni in una variabile denominata $x ( **$x = Get-AzureADUser** ).
- Visualizzare il contenuto della variabile $x, ma includere solo il nome e la posizione di ciascun utente ( **$x | Select DisplayName, UsageLocation** ).
  
## <a name="microsoft-365-has-features-that-you-can-only-configure-with-powershell-for-microsoft-365"></a>Microsoft 365 dispone di funzionalità che è possibile configurare solo con PowerShell per Microsoft 365

L'interfaccia di amministrazione di Microsoft 365 ha lo scopo di consentire l'accesso alle attività amministrative più comuni o significative che si applicano alla maggior parte delle persone. In altre parole, l'interfaccia di amministrazione di Microsoft 365 è stata progettata in modo che l'amministratore comune potesse utilizzare lo strumento per eseguire le attività di gestione più comuni. In base a questa definizione, significa che sono presenti alcune attività che non possono essere completate tramite l'interfaccia di amministrazione di Microsoft 365.
  
Ad esempio, l'interfaccia di amministrazione di Skype for Business online offre alcune opzioni per la creazione di convocazioni di riunioni personalizzate:
  
![Esempio di visualizzazione di inviti personalizzati a riunioni nell’interfaccia di amministrazione di Skype for Business online.](../media/o365-powershell-meeting-invitation.png)
  
Con queste impostazioni, è possibile aggiungere un tocco di personalizzazione e professionalità alle convocazioni di riunioni. Tuttavia, esistono più impostazioni di configurazione di una riunione rispetto alla semplice creazione di convocazioni personalizzate. Ad esempio, per impostazione predefinita le riunioni consentono:
  
- A utenti anonimi di ottenere l'ingresso automatico a ogni riunione.
    
- Ai partecipanti di registrare una riunione.
    
- A tutti gli utenti dell'organizzazione di essere designati come relatori quando partecipano a riunione.
    
Queste impostazioni non sono disponibili dall'interfaccia di amministrazione di Skype for Business online. Tuttavia, è possibile controllarli da PowerShell per Microsoft 365. Ecco un comando che consente di disabilitare queste tre impostazioni:
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False -AllowConferenceRecording $False -DesignateAsPresenter "None"
```

> [!NOTE]
> Questo comando richiede l'installazione del [modulo di PowerShell per Skype for Business Online ](https://www.microsoft.com/download/details.aspx?id=39366). 
  
> [!TIP]
>  L'interpretazione di questo comando PowerShell è la seguente: per le impostazioni per le nuove riunioni di Skype for business online ( **Set-CsMeetingConfiguration** ), disabilitare l'accesso degli utenti anonimi alle riunioni (- **AdmitAnonymousUsersByDefault $false** ), disabilitare la possibilità per i partecipanti di registrare le riunioni ( **-AllowConferenceRecording $false** ) e non designare tutti gli utenti dell'organizzazione come relatori ( **-DesignateAsPresenter "None"** ).
  
Se si cambia idea e si desidera ripristinare le impostazioni predefinite (tutte abilitate), sarà sufficiente eseguire questo comando:
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $True -AllowConferenceRecording $True -DesignateAsPresenter "Company"
```

Questo è solo un esempio. Ve ne sono altri, ed è il motivo per cui, in quanto amministratore, è necessario avere dimestichezza con i comandi di PowerShell per Microsoft 365.
  
## <a name="powershell-for-microsoft-365-is-great-at-carrying-out-bulk-operations"></a>PowerShell per Microsoft 365 è molto utile per eseguire operazioni in blocco

Storicamente, le interfacce visive come l'interfaccia di amministrazione di Microsoft 365 sono più importanti quando si ha un'unica operazione da eseguire. Ad esempio, se è necessario disabilitare un account utente, è possibile utilizzare l'interfaccia di amministrazione di Microsoft 365 per individuare e cancellare rapidamente una casella di controllo. Questo può essere più semplice rispetto all'esecuzione di un'operazione analoga in PowerShell.
  
Tuttavia, se è necessario modificare molte cose o alcuni elementi selezionati all'interno di un insieme di grandi dimensioni, è possibile che l'interfaccia di amministrazione di Microsoft 365 non sia il miglior utilizzo del proprio tempo. Ad esempio, se è stato necessario cambiare il prefisso su migliaia di numeri di telefono o se è necessario rimuovere un utente specifico, Ken remario, da tutti i siti di SharePoint Online, come è possibile eseguire tale operazione nell'interfaccia di amministrazione di Microsoft 365?
  
Per quanto riguarda l'ultimo esempio, sono presenti diverse centinaia di siti di SharePoint Online e non si sa nemmeno di quali di questi siti è membro Ken Meyer. Questo significa che sarà necessario iniziare dall'interfaccia di amministrazione di Microsoft 365 e quindi eseguire questa procedura per ogni sito:
  
1. Fare clic sull' **URL** del sito.
    
2. Nella casella **proprietà della raccolta del sito**, fare clic sul link **Indirizzo sito Web** per aprire il sito.
    
3. Nel sito, fare clic su **Condividi**.
    
4. Nella finestra di dialogo **Condividi** fare clic sul link che mostra tutti gli utenti che dispongono delle autorizzazioni per il sito:
    
     ![Esempio di visualizzazione di membri del sito SharePoint Online nell'interfaccia di amministrazione di SharePoint Online.](../media/o365-powershell-view-permissions.png)
  
5. Nella finestra di dialogo **Condiviso con** fare clic su **Avanzate**.
    
6. Scorrere l'elenco degli utenti, trovare e selezionare Ken Myer (presumendo che disponga delle autorizzazioni per il sito), quindi fare clic su **Rimuovi autorizzazioni utente**.
    
La procedura può richiedere molto tempo per diverse centinaia di siti.
  
L'alternativa consiste nell'usare PowerShell per Microsoft 365 e il seguente comando per rimuovere Ken remario da tutti i siti:
  
```powershell
Get-SPOSite | ForEach {Remove-SPOUser -Site $_.Url -LoginName "kenmyer@litwareinc.com"}
```

> [!NOTE]
> Questo comando richiede l'installazione del [modulo di PowerShell di SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps). 
  
> [!TIP]
>  L'interpretazione di questo comando di PowerShell è: recuperare tutti i siti di SharePoint nella sottoscrizione Microsoft 365 corrente ( **Get-SPOSite** ) e per ogni sito, rimuovere Ken Meyer dall'elenco degli utenti che possono accedervi ( **foreach {Remove-consorter-site $ \_ . URL-LoginName "kenmyer@litwareinc.com"}** ).
  
Poiché si dice a Microsoft 365 di rimuovere Ken Meyer da ogni sito, compresi quelli in cui non ha accesso, la visualizzazione di questo comando mostrerà gli errori per i siti in cui attualmente non ha accesso. È possibile utilizzare una condizione aggiuntiva su questo comando, per rimuovere Ken Meyer solo dai siti in cui compare nell'elenco degli accessi, ma gli errori elencati non danneggiano i siti. Questo comando potrebbe richiedere alcuni minuti per l'esecuzione in centinaia di siti anziché ore di utilizzo dell'interfaccia di amministrazione di Microsoft 365.
  
Ecco un altro esempio di operazione di massa. Utilizzare questo comando per aggiungere Bonnie Kearney, un nuovo amministratore di SharePoint, a tutti i siti dell'organizzazione:
  
```powershell
Get-SPOSite | ForEach {Add-SPOUser -Site $_.Url -LoginName "bkearney@litwareinc.com" -Group "Members"}
```

> [!TIP]
>  L'interpretazione di questo comando di PowerShell è: recuperare tutti i siti di SharePoint nella sottoscrizione corrente di Microsoft 365 e per ogni sito, consentire a Bonnie Kearney di accedere aggiungendo il nome di accesso al gruppo membri del sito ( **foreach {Add-Consorter-site $ \_ . URL-LoginName "bkearney@litwareinc.com"-gruppo "membri"}** ).
  
## <a name="powershell-for-microsoft-365-is-great-at-filtering-data"></a>PowerShell per Microsoft 365 è ottimo per filtrare i dati

L'interfaccia di amministrazione di Microsoft 365 offre diversi modi per filtrare i dati in modo da individuare rapidamente e facilmente un sottoinsieme di informazioni mirato. Ad esempio, Exchange facilita il filtro di qualsiasi proprietà relativa alla cassetta postale di un utente. Ad esempio, questo è un elenco delle cassette postali degli utenti che vivono nella città di Bloomington:
  
![Esempio di ricerca avanzata nell'interfaccia di amministrazione di Microsoft 365 per l'elenco delle cassette postali per tutti gli utenti che vivono nella città di Bloomington.](../media/o365-powershell-advanced-search.png)
  
L'interfaccia di amministrazione di Exchange consente di combinare i criteri di filtro. Ad esempio, è possibile trovare le cassette postali di tutti i residenti di Bloomington e di coloro che lavorano nel reparto finanziario. 
  
Tuttavia, esistono limitazioni per le operazioni che è possibile eseguire nell'interfaccia di amministrazione di Exchange. Ad esempio, si potrebbe desiderare di individuare le cassette postali di persone che vivono a Bloomington o San Diego oppure le cassette postali di tutte le persone non residenti a Bloomington. 
  
Con PowerShell per Microsoft 365, è possibile ottenere un elenco delle cassette postali per tutte le persone che vivono nelle città di Bloomington o San Diego con questo comando:
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and ($_.City -eq "San Diego" -or $_.City -eq "Bloomington")} | Select DisplayName, City
```

Ecco un esempio di visualizzazione:
  
```powershell
DisplayName                              City
-----------                              ----
Alex Darrow                              San Diego
Bonnie Kearney                           San Diego
Julian Isla                              Bloomington
Rob Young                                Bloomington
```

> [!TIP]
>  L'interpretazione di questo comando di PowerShell è: recuperare tutti gli utenti nell'attuale sottoscrizione di Microsoft 365 che dispongono di una cassetta postale nelle città di San Diego o Bloomington ( **dove {$ \_ . RecipientTypeDetails-EQ "UserMailbox"-and ($ \_ . City-EQ "San Diego"-oppure $ \_ . City-EQ "Bloomington")}** ), quindi visualizzare il nome e la città per ognuno ( **selezionare DisplayName, City** ).
  
Il comando di seguito consente di elencare tutte le cassette postali delle persone che vivono in qualsiasi altro posto a eccezione di Bloomington:
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and $_.City -ne "Bloomington"} | Select DisplayName, City
```

Ecco un esempio di visualizzazione:
  
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

> [!TIP]
>  L'interpretazione di questo comando di PowerShell è: recuperare tutti gli utenti nell'attuale sottoscrizione di Microsoft 365 che dispongono di una cassetta postale che non si trova nella città di Bloomington ( **dove {$ \_ . RecipientTypeDetails-EQ "UserMailbox"-e $ \_ . City-ne "Bloomington"}** ), quindi visualizzare il nome e la città per ognuno di essi.
  
È inoltre possibile utilizzare i caratteri jolly nei filtri di PowerShell per far corrispondere parte di un nome. Ad esempio, si supponga di effettuare la ricerca di un account utente e di ricordare solo che il cognome potrebbe corrispondere ad Anderson o forse a Henderson oppure Jorgenson.
  
È possibile rintracciare l'utente nell'interfaccia di amministrazione di Microsoft 365 utilizzando lo strumento di ricerca ed effettuando tre ricerche diverse:
  
- Una per  *Anderson* 
    
- Una per  *Henderson* 
    
- Una per  *Jorgenson* 
    
Poiché tutti e tre questi nomi terminano con "son", è possibile indicare a PowerShell di visualizzare tutti gli utenti il cui nome termina con "son". Ecco il comando:
  
```powershell
Get-User -Filter '{LastName -like "*son"}'
```

> [!TIP]
>  L'interpretazione di questo comando di PowerShell è: recuperare tutti gli utenti nella sottoscrizione Microsoft 365 corrente, ma utilizzare un filtro che elenca solo gli utenti i cui cognomi terminano con "son" ( **-Filter ' {LastName-like " \* son"}'** ). Gli \* stand per qualsiasi set di caratteri, ovvero lettere nel caso del cognome dell'utente.
  
## <a name="powershell-for-microsoft-365-makes-it-easy-to-print-or-save-data"></a>PowerShell per Microsoft 365 rende più semplice la stampa o il salvataggio dei dati

L'interfaccia di amministrazione di Microsoft 365 consente di visualizzare gli elenchi di dati. Ecco un esempio dell'interfaccia di amministrazione di Skype for Business online che mostra un elenco di utenti che sono stati abilitati per Skype for Business online:
  
![Esempio di interfaccia di amministrazione di Skype for Business online che mostra un elenco di utenti abilitati a Skype for Business online.](../media/o365-powershell-lync-users.png)
  
Per salvare queste informazioni in un file, è necessario copiarle e incollarle in un documento o in Excel. In entrambi i casi, la copia potrebbe richiedere ulteriore formattazione. Inoltre, l'interfaccia di amministrazione di Microsoft 365 non consente di stampare direttamente l'elenco visualizzato.
  
Fortunatamente, è possibile utilizzare PowerShell per non solo visualizzare l'elenco, ma salvarlo in un file che può essere importato facilmente in Excel. Ecco un comando di esempio per salvare i dati utente di Skype for Business online in un file con valori delimitati da virgole (CSV), che può essere facilmente importato come tabella in un foglio di lavoro di Excel:
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Export-Csv -Path "C:\Logs\SfBUsers.csv" -NoTypeInformation
```

Ecco un esempio di visualizzazione:
  
![Esempio di tabella importata in un foglio Excel di dati di utenti di Skype for Business online, salvati in un file con valori delimitati da virgole (CSV).](../media/o365-powershell-data-in-excel.png)
  
> [!TIP]
>  L'interpretazione di questo comando di PowerShell è: ottenere tutti gli utenti di Skype for business online nella sottoscrizione Microsoft 365 corrente ( **Get-CsOnlineUser** ), ottenere solo il nome utente, l'UPN e la posizione ( **selezionare DisplayName, userPrincipalName, UsageLocation** ) e quindi salvare tali informazioni nel file CSV denominato c: \\ logs \\SfBUsers.csv ( **Export-CSV-path "c: \\ logs \\SfBUsers.csv"-NoTypeInformation** ).
  
È anche possibile utilizzare le opzioni per salvare questo elenco come file XML o pagina HTML. Infatti, con altri comandi di PowerShell, è possibile salvarlo direttamente come file di Excel, con qualsiasi formattazione personalizzata che si desidera. 
  
È anche possibile inviare l'output di un comando di PowerShell che consente di visualizzare un elenco direttamente alla stampante predefinita in Windows. Ecco un esempio di comando:
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Out-Printer
```

Di seguito, è riportato l'aspetto del documento stampato:
  
![Esempio di un documento stampato che è stato l'output di un comando di PowerShell elencato direttamente alla stampante predefinita in Windows.](../media/o365-powershell-printed-data.png)
  
> [!TIP]
>  L'interpretazione di questo comando di PowerShell è: ottenere tutti gli utenti di Skype for business online nella sottoscrizione Microsoft 365 corrente, ottenere solo il nome utente, l'UPN e la posizione, quindi inviare tali informazioni alla stampante predefinita di Windows ( **fuori stampante** ).
  
Il documento stampato ha la stessa formattazione semplice della visualizzazione all'interno della finestra di comando di PowerShell, ma dopo aver creato un comando di PowerShell per elencare gli elementi necessari, è sufficiente aggiungere **| Out-Printer** alla fine del comando per ottenere una copia cartacea da utilizzare.
  
## <a name="powershell-for-microsoft-365-lets-you-manage-across-server-products"></a>PowerShell per Microsoft 365 consente di gestire diversi prodotti server

I diversi componenti che compongono Microsoft 365 sono stati concepiti per funzionare insieme. Si supponga, ad esempio, di aggiungere un nuovo utente a Microsoft 365 e, in tal caso, di specificare tali informazioni come reparto e numero di telefono dell'utente. Tali informazioni saranno quindi disponibili se si accede alle informazioni dell'utente utilizzando uno qualsiasi dei servizi Microsoft 365: Skype for business online, Exchange o SharePoint Online.
  
Si tratta di informazioni generali che interessano la famiglia di prodotti. Le informazioni specifiche di un prodotto, ad esempio quelle relative alla cassetta postale di Exchange di un utente, non sono generalmente disponibili tra le famiglie di prodotti. Ad esempio, se si desidera sapere se la cassetta postale di un utente è abilitata o meno, tale informazione è disponibile solo nell'interfaccia di amministrazione di Exchange. 
  
Si supponga di voler creare un report che mostra le seguenti informazioni per tutti gli utenti:
  
- Nome visualizzato dell'utente
    
- Se l'utente ha una licenza per Microsoft 365
    
- L'abilitazione della cassetta postale di Exchange dell'utente.
    
- L'abilitazione per Skype for Business online dell'utente
    
Al momento non è possibile utilizzare l'interfaccia di amministrazione di Microsoft 365 per produrre facilmente un rapporto di questo tipo. Al contrario, è necessario creare un documento separato per archiviare le informazioni, ad esempio un foglio di lavoro di Excel, e ottenere tutti i nomi utente e le informazioni di licenza dall'interfaccia di amministrazione di Microsoft 365, ottenere le informazioni della cassetta postale dall'interfaccia di amministrazione di Exchange, ottenere informazioni su Skype for business online dal centro di amministrazione di Skype for business online, quindi raccogliere e combinare tali informazioni.
  
L'alternativa consiste nell'usare uno script di PowerShell per compilare il report.
  
Il seguente script di esempio è più complesso dei comandi che finora sono stati illustrati in questo articolo. Tuttavia, dimostra la potenzialità dell'utilizzo di PowerShell per creare visualizzazioni di informazioni che sono molto difficili da fare altrimenti. Ecco lo script in grado di compilare e visualizzare l'elenco necessario:
  
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

Ecco un esempio di visualizzazione:
  
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

- Ottenere tutti gli utenti nella sottoscrizione Microsoft 365 corrente e archiviare le informazioni in una variabile denominata $x ( **$x = Get-AzureADUser** ).
- Avviare un ciclo che viene eseguito su tutti gli utenti nella variabile denominata $x ( **foreach ($i in $x)** ).  
- Definire una variabile denominata $y e archiviarvi all'interno le informazioni sulla cassetta postale dell'utente ( **$y = Get-Mailbox -Identity $i.UserPrincipalName** ).
- Aggiungere una nuova proprietà alle informazioni sull'utente denominata IsMailBoxEnabled e impostarla sul valore della proprietà IsMailBoxEnabled della cassetta postale dell'utente ( **$i | Add-Member -MemberType NoteProperty -Name IsMailboxEnabled -Value $y.IsMailboxEnabled** ).
- Definire una variabile denominata $y e archiviarvi all'interno le informazioni su Skype for Business Online relative all'utente ( **$y = Get-CsOnlineUser -Identity $i.UserPrincipalName** ).
- Aggiungere una nuova proprietà alle informazioni sull'utente denominata EnabledForSfB e impostarla sul valore della proprietà EnabledForSfB della cassetta postale dell'utente di Skype for Business Online ( **$i | Add-Member -MemberType NoteProperty -Name EnabledForSfB -Value $y.Enabled** ).
- Visualizzare l'elenco di utenti, ma includere solo il nome, se dispongono di una licenza e le due nuove proprietà che indicano se la loro cassetta postale è abilitata e se loro sono abilitati per Skype for Business Online ( **$x | Select DisplayName, IsLicensed, IsMailboxEnabled, EnabledforSfB** ).
  
## <a name="see-also"></a>Vedere anche

[Guida introduttiva a PowerShell per Microsoft 365](getting-started-with-microsoft-365-powershell.md)
  
[Gestire gli account utente, le licenze e i gruppi di Microsoft 365 con PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Usare Windows PowerShell per creare report in Microsoft 365](use-windows-powershell-to-create-reports-in-microsoft-365.md)

