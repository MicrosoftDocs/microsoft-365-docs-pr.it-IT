---
title: Creare blocchi di eDiscovery in un caso di eDiscovery di base
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: È possibile creare un'esenzione associata a un caso di eDiscovery di base per conservare il contenuto che potrebbe essere rilevante per un'indagine.
ms.openlocfilehash: 377a9e7a31864f177f0ccbdc4cf2789fdc1cf373
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423467"
---
# <a name="create-an-ediscovery-hold"></a>Creare un blocco di eDiscovery

È possibile utilizzare un caso di eDiscovery di base per creare esenzioni per conservare il contenuto che potrebbe essere rilevante per il caso. È possibile impostare un blocco sulle cassette postali di Exchange e sugli account OneDrive for Business delle persone su cui si sta esaminando il caso. È inoltre possibile impostare un blocco per le cassette postali e i siti associati a Microsoft Teams, Gruppi di Office 365 e Gruppi di Yammer. Quando si conservano i percorsi di contenuto, il contenuto viene conservato fino a quando non si rimuove il blocco dal percorso del contenuto o fino a quando non si elimina l'esenzione.

Dopo aver creato un blocco di eDiscovery, l'applicazione del blocco potrebbe richiedere fino a 24 ore. 

Quando si crea un'esenzione, sono disponibili le opzioni seguenti per impostare l'ambito del contenuto conservato nei percorsi di contenuto specificati:
  
- Si crea un'esenzione infinita in cui tutto il contenuto nelle posizioni specificate viene messo in attesa. In alternativa, è possibile creare un'archiviazione basata su query in cui viene sospeso solo il contenuto nelle posizioni specificate che corrisponde a una query di ricerca.

- È possibile specificare un intervallo di date per mantenere solo il contenuto inviato, ricevuto o creato entro tale intervallo di date. In alternativa, è possibile contenere tutto il contenuto in posizioni specifiche, indipendentemente da quando è stato inviato, ricevuto o creato.
  
## <a name="how-to-create-an-ediscovery-hold"></a>Come creare un blocco di eDiscovery

Per creare un blocco di eDiscovery associato a un caso di eDiscovery di base:
  
1. Accedere utilizzando le credenziali dell'account utente a cui sono state assegnate [https://compliance.microsoft.com](https://compliance.microsoft.com) le autorizzazioni di eDiscovery appropriate.

2. Nel riquadro di spostamento sinistro del Centro conformità Microsoft 365 fare clic su Mostra tutto e quindi su **eDiscovery > Core.**

3. Nella pagina **Core eDiscovery** selezionare il caso in cui si desidera creare il blocco e quindi fare clic **su Apri caso.**

4. Nella **home** page del caso fare clic sulla **scheda Esenzioni.**
  
5. Nella pagina **Esenzioni** fare clic su **Crea.**

6. Nella pagina **Name your hold** wizard assegnare un nome all'esenzione e aggiungere una descrizione facoltativa e quindi fare clic su **Next.** Il nome del blocco deve essere univoco nell'organizzazione.

7. Nella pagina **Percorsi contenuto** scegliere i percorsi di contenuto che si desidera mettere in attesa. È possibile mantenere le cassette postali, i siti e le cartelle pubbliche.

    ![Scegliere i percorsi dei contenuti da mettere in attesa](../media/a59e4265-9151-4dbf-913f-6a4ab8db06b4.png)
  
   1. **Posizioni delle** cassette postali: fare clic su Scegli **utenti, gruppi** o team, quindi fare di nuovo clic su Scegli **utenti, gruppi o team** per specificare le cassette postali da mettere in attesa. Utilizzare la casella di ricerca per trovare le cassette postali degli utenti e i gruppi di distribuzione (per mettere un blocco sulle cassette postali dei membri del gruppo) da mettere in attesa. È inoltre possibile impostare un blocco sulla cassetta postale associata per un microsoft team, un gruppo di Office 365 o un gruppo di Yammer. Selezionare l'utente, il gruppo, la casella di controllo del team, **fare clic su Scegli** e quindi su **Fine.**

   1. **Percorsi dei** siti: fare  **clic su Scegli siti** e quindi di nuovo su Scegli siti per specificare gli account di SharePoint e OneDrive da mettere in attesa. Digitare l'URL per ogni sito che si desidera conservare. È inoltre possibile aggiungere l'URL per il sito di SharePoint per un team microsoft, un gruppo di Office 365 o un gruppo di Yammer. Fare **clic su** Scegli e quindi su **Fine.**
  
   1. **Cartelle pubbliche di Exchange.** Spostare l'interruttore Attiva/Disattiva nella posizione Tutti per mettere in attesa tutte le cartelle pubbliche ![ ](../media/scc-toggle-on.png) nell'organizzazione di Exchange Online.  Non è possibile scegliere cartelle pubbliche specifiche da mettere in attesa. Lasciare l'interruttore Attiva/Disattiva impostato su **Nessuno** se non si desidera attivare un'esenzione per le cartelle pubbliche.

   > [!NOTE]
   > È necessario aggiungere almeno un percorso di contenuto all'esenzione. In caso contrario, i valori statici del blocco di eDiscovery mostreranno che nessun elemento è in attesa.

8. Dopo aver aggiunto i percorsi di contenuto all'esenzione, fare clic su **Avanti.**

9. Per creare un'esenzione basata su query con condizioni, completare le operazioni seguenti. In caso contrario, per mantenere tutto il contenuto nei percorsi di contenuto specificati, fare clic su **Avanti.**

    ![Creare un blocco basato su query con condizioni](../media/d587b58e-d05c-4ac0-b0fe-09019e4f1063.png)
  
    1. Nella casella sotto Parole **chiave** digitare una query di ricerca in modo che solo il contenuto che soddisfa i criteri di ricerca sia mantenuto. È possibile specificare parole chiave, proprietà dei messaggi di posta elettronica o proprietà del documento, ad esempio i nomi di file. È inoltre possibile utilizzare query più complesse che utilizzano un operatore booleano, ad esempio **AND**, **OR** o **NOT.**

    1. Fare **clic su Aggiungi** condizioni per aggiungere una o più condizioni per restringere la query di ricerca per l'esenzione. Ogni condizione aggiunge una clausola alla query di ricerca KQL creata ed eseguita quando si crea l'esenzione. Ad esempio, è possibile specificare un intervallo di date in modo che i messaggi di posta elettronica o i documenti del sito creati entro l'intervallo di date siano messi in attesa. Una condizione è collegata logicamente alla query con parole chiave (specificata nella casella **Parole** chiave) dall'operatore **AND.** Ciò significa che gli elementi devono soddisfare sia la query con parole chiave che la condizione da mantenere.

    Per ulteriori informazioni sulla creazione di una query di ricerca e sull'utilizzo di condizioni, vedere Query con parole chiave [e condizioni di ricerca per Ricerca contenuto.](keyword-queries-and-search-conditions.md)

10. Dopo aver configurato un blocco basato su query, fare clic su **Avanti.**

11. Rivedere le impostazioni e modificarle, se necessario, e quindi fare clic **su Crea blocco.**

## <a name="query-based-holds-placed-on-site-documents"></a>Blocchi basati su query inseriti nei documenti del sito

Tenere presente quanto segue quando si posiziona un blocco eDiscovery basato su query sui documenti che si trovano nei siti di SharePoint:

- Un blocco basato su query mantiene inizialmente tutti i documenti di un sito per un breve periodo di tempo dopo l'eliminazione. Ciò significa che quando un documento viene eliminato, verrà spostato nella raccolta di archiviazione anche se non corrisponde ai criteri dell'archiviazione basata su query. Tuttavia, i documenti eliminati che non corrispondono a un'archiviazione basata su query verranno rimossi da un processo timer che elabora la raccolta di archiviazione. Il processo timer viene eseguito periodicamente e confronta tutti i documenti nella raccolta di archiviazione con i blocchi di eDiscovery basati su query (e altri tipi di esenzioni e criteri di conservazione). Il processo timer elimina i documenti che non corrispondono a un'esenzione basata su query e mantiene i documenti corrispondenti.

- Le esenzioni basate su query non devono essere utilizzate per eseguire l'archiviazione mirata, ad esempio per conservare i documenti in una cartella o in un sito specifico o utilizzando altri criteri di conservazione basati sulla posizione. Questa operazione potrebbe avere risultati imprevisti. È consigliabile utilizzare criteri di blocco non basati sulla posizione, ad esempio parole chiave, intervalli di date o altre proprietà del documento per conservare i documenti del sito.

## <a name="ediscovery-hold-statistics"></a>Statistiche del blocco di eDiscovery

Dopo aver creato un blocco di eDiscovery, le informazioni sul nuovo blocco vengono visualizzate nella pagina a comparsa per l'esenzione selezionata. Queste informazioni includono il numero di cassette postali e siti in attesa e le statistiche sul contenuto che è stato messo in attesa, ad esempio il numero totale e le dimensioni degli elementi messi in attesa e l'ultima volta in cui sono state calcolate le statistiche di blocco. Queste statistiche di conservazione consentono di identificare la quantità di contenuto correlato al caso in corso di conservazione.
  
![Statistiche di blocco](../media/575cfe0a-9210-4ae4-8df8-65665d66712e.png)
  
Tenere presente quanto segue sulle statistiche di blocco di eDiscovery:
  
- Il numero totale di elementi in attesa indica il numero di elementi di tutte le origini di contenuto che vengono messi in attesa. Se è stata creata un'esenzione basata su query, questa statistica indica il numero di elementi che corrispondono alla query.

- Il numero di elementi in attesa include anche gli elementi non indicizzati trovati nei percorsi del contenuto. Se si crea un'archiviazione basata su query, tutti gli elementi non indicizzati nei percorsi del contenuto vengono messi in attesa. Sono inclusi gli elementi non indicizzati che non corrispondono ai criteri di ricerca di un'esenzione basata su query e gli elementi non indicizzati che potrebbero non rientrare in una condizione di intervallo di date. Ciò è diverso da quello che accade quando si esegue una ricerca, in cui gli elementi non indicizzati che non corrispondono alla query di ricerca o sono esclusi da una condizione di intervallo di date non vengono inclusi nei risultati della ricerca. Per ulteriori informazioni sugli elementi non indicizzati, vedere [Elementi parzialmente indicizzati.](partially-indexed-items-in-content-search.md)

- È possibile ottenere le statistiche di blocco più recenti facendo clic su **Aggiorna** statistiche per eseguire di nuovo una stima della ricerca che calcola il numero corrente di elementi in attesa.

- È normale che il numero di elementi in attesa aumenti nel tempo perché gli utenti la cui cassetta postale o sito è in attesa in genere inviano o ricevono nuovi messaggi di posta elettronica e creano nuovi documenti in SharePoint e OneDrive.

- Se una cassetta postale di Exchange, un sito di SharePoint o un account di OneDrive viene spostato in un'area geografica diversa in un ambiente multi-geografico, le statistiche per tale sito non verranno incluse nelle statistiche di blocco. Tuttavia, il contenuto in tali posizioni verrà comunque conservato. Inoltre, se una cassetta postale o un sito viene spostato in un'area geografica diversa, l'indirizzo SMTP o l'URL visualizzato nel blocco non verrà aggiornato automaticamente. Sarà necessario modificare il blocco e aggiornare l'URL o l'indirizzo SMTP in modo che i percorsi dei contenuti siano di nuovo inclusi nelle statistiche di blocco

## <a name="search-locations-on-ediscovery-hold"></a>Percorsi di ricerca nel blocco di eDiscovery

Quando si [cerca contenuto](search-for-content-in-core-ediscovery.md) in un caso di Core eDiscovery, è possibile configurare rapidamente la ricerca in modo da eseguire la ricerca solo nei percorsi dei contenuti che sono stati inseriti in un blocco associato al caso.

![Posizioni in attesa](../media/d56398aa-0b20-4500-8e26-494eab92a99f.png)

Selezionare **l'opzione Percorsi in attesa** per cercare tutti i percorsi di contenuto che sono stati messi in attesa. Se il caso contiene più blocchi di eDiscovery, le posizioni dei contenuti di tutti i blocchi verranno cercate quando si seleziona questa opzione. Inoltre, se una posizione del contenuto è stata inserita in un blocco basato su query, durante l'esecuzione della ricerca verranno cercati solo gli elementi che corrispondono alla query di blocco. In altre parole, con i risultati della ricerca viene restituito solo il contenuto che corrisponde sia ai criteri di conservazione che ai criteri di ricerca. Ad esempio, se a un utente è stata impostata un'esenzione per caso basata su query che conserva gli elementi inviati o creati prima di una data specifica, verrà eseguita la ricerca solo di tali elementi. Questa operazione viene eseguita connettendo la query di blocco del caso e la query di ricerca tramite un **operatore AND.**

Ecco alcuni altri aspetti da tenere presenti quando si effettuano ricerche in posizioni con archiviazione eDiscovery:

- Se un percorso di contenuto fa parte di più blocchi all'interno dello stesso caso, le query di blocco vengono combinate dagli operatori **OR** quando si esegue una ricerca in tale percorso del contenuto utilizzando l'opzione di contenuto per tutti i casi. Analogamente, se un percorso di contenuto fa parte di due blocchi diversi, in cui uno è basato su query e l'altro è un blocco infinito (in cui tutto il contenuto viene messo in attesa), tutto il contenuto viene ricercato a causa dell'esenzione infinita.

- Se una ricerca è configurata per cercare i percorsi di archiviazione e quindi si modifica un blocco di eDiscovery nel caso (aggiungendo o rimuovendo una posizione o modificando una query di blocco), la configurazione di ricerca viene aggiornata con tali modifiche. Tuttavia, è necessario eseguire di nuovo la ricerca dopo aver modificato il blocco per aggiornare i risultati della ricerca.

- Se più blocchi di eDiscovery vengono inseriti in una singola posizione in un caso di eDiscovery e si sceglie di eseguire ricerche nei percorsi di archiviazione, il numero massimo di parole chiave per la query di ricerca è 500. Questo perché la ricerca combina tutti i blocchi basati su query utilizzando l'operatore **OR.** Se sono presenti più di 500 parole chiave nelle query di blocco combinate e nella query di ricerca, la ricerca viene eseguita su tutto il contenuto della cassetta postale, non solo sul contenuto che corrisponde al caso basato su query.

- Se lo stato di un blocco di eDiscovery è **Attivato,** è comunque possibile cercare le posizioni in attesa mentre il blocco è attivato.

## <a name="preserve-content-in-microsoft-teams"></a>Mantenere il contenuto in Microsoft Teams

Le conversazioni che fanno parte di un canale di Microsoft Teams vengono archiviate nella cassetta postale associata a Microsoft Team. Allo stesso modo, i file che i membri del team condividono in un canale vengono archiviati nel sito di SharePoint del team. Pertanto, è necessario inserire la cassetta postale del team e il sito di SharePoint in un blocco eDiscovery per conservare conversazioni e file in un canale.

In alternativa, le conversazioni che fanno parte dell'elenco chat in Teams (denominate *chat 1:1* o chat di gruppo *1:N)* vengono archiviate nelle cassette postali degli utenti che partecipano alla chat. I file che gli utenti condividono nelle conversazioni in chat vengono archiviati nell'account OneDrive dell'utente che condivide il file. Pertanto, è necessario aggiungere le cassette postali dei singoli utenti e gli account di OneDrive a un blocco di eDiscovery per mantenere conversazioni e file nell'elenco chat. È buona idea impostare un blocco sulle cassette postali dei membri di un team Microsoft oltre a mettere in attesa la cassetta postale del team e il sito.

> [!IMPORTANT]
> In un'organizzazione basata su cloud, gli utenti che partecipano a conversazioni che fanno parte dell'elenco chat in Teams devono disporre di una cassetta postale di Exchange Online per conservare le conversazioni in chat quando la cassetta postale viene conservata in un blocco eDiscovery. Questo perché le conversazioni che fanno parte dell'elenco chat vengono archiviate nelle cassette postali basate sul cloud dei partecipanti alla chat. Se un partecipante alla chat non dispone di una cassetta postale di Exchange Online, non sarà possibile conservare tali conversazioni. Ad esempio, in una distribuzione ibrida di Exchange, gli utenti con una cassetta postale locale potrebbero essere in grado di partecipare a conversazioni che fanno parte dell'elenco chat in Teams. In questo caso, tuttavia, il contenuto di queste conversazioni non può essere conservato perché questi utenti non dispongono di cassette postali basate sul cloud che possono essere conservate.

Per ulteriori informazioni sulla conservazione del contenuto di Teams, vedere Inserire un utente o un team di [Microsoft Teams in conservazione a tempo in sospeso.](https://docs.microsoft.com/MicrosoftTeams/legal-hold)

### <a name="preserve-card-content"></a>Conservare il contenuto della scheda

Analogamente, il contenuto delle schede generato dalle app nei canali di Teams, nelle chat 1:1 e nelle chat di gruppo 1:N viene archiviato nelle cassette postali e viene conservato quando una cassetta postale viene conservata in un blocco eDiscovery. Una *scheda* è un contenitore di interfaccia utente per piccole parti di contenuto. Le schede possono avere più proprietà e allegati e possono includere pulsanti che attivano le azioni delle carte. Per ulteriori informazioni, vedere [Schede.](https://docs.microsoft.com/microsoftteams/platform/task-modules-and-cards/what-are-cards) Come nel caso di altri contenuti di Teams, il luogo di archiviazione del contenuto delle schede dipende da dove è stata usata la scheda. Il contenuto delle schede usate in un canale di Teams viene archiviato nella cassetta postale di gruppo di Teams. Il contenuto delle schede per chat tra due persone e 1xN viene archiviato nelle cassette postali dei partecipanti alla chat.

### <a name="preserve-meeting-and-call-information"></a>Conservare le informazioni sulle riunioni e sulle chiamate

Le informazioni di riepilogo per le riunioni e le chiamate in un canale di Teams vengono archiviate anche nelle cassette postali degli utenti che hanno chiamato o hanno chiamato la riunione. Questo contenuto viene conservato anche quando viene effettuato un blocco di eDiscovery sulle cassette postali degli utenti.

### <a name="preserve-content-in-private-channels"></a>Conservare il contenuto nei canali privati

A partire da febbraio 2020, è stata attivata anche la possibilità di conservare il contenuto nei canali privati. Poiché le chat di canale privato vengono archiviate nelle cassette postali dei partecipanti alla chat, l'archiviazione di una cassetta postale utente in eDiscovery conserverà le chat dei canali privati. Inoltre, se una cassetta postale utente è stata conservata in eDiscovery prima di febbraio 2020, il blocco verrà applicato automaticamente ai messaggi del canale privato archiviati in tale cassetta postale. È supportata anche la conservazione dei file condivisi nei canali privati.

### <a name="preserve-wiki-content"></a>Conservare il contenuto del wiki

Ogni canale del team o del team contiene anche un wiki per la raccolta di note e la collaborazione. Il contenuto Wiki viene salvato automaticamente in un file con formato MHT. Il file è archiviato nella raccolta documenti di dati Wiki di Teams nel sito di SharePoint del team. È possibile conservare il contenuto wiki aggiungendo il sito di SharePoint del team a un blocco eDiscovery.

> [!NOTE]
> La possibilità di conservare il contenuto wiki per un canale del team o del team (quando si conserva il sito di SharePoint del team) è stata rilasciata il 22 giugno 2017. Se un sito del team è in attesa, il contenuto del wiki verrà conservato a partire da tale data. Tuttavia, se un sito del team è in attesa e il contenuto wiki è stato eliminato prima del 22 giugno 2017, il contenuto wiki non è stato conservato.

### <a name="office-365-groups"></a>Gruppi di Office 365

Teams è basato sui gruppi di Office 365. Pertanto, l'archiviazione dei gruppi di Office 365 su eDiscovery è simile all'archiviazione dei contenuti di Teams.

Tenere presente quanto segue quando si inserisce sia Teams che Gruppi di Office 365 in un blocco di eDiscovery:

- Come spiegato in precedenza, per mettere in attesa il contenuto presente in Teams e gruppi di Office 365, è necessario specificare la cassetta postale e il sito di SharePoint associati a un gruppo o a un team.

- Eseguire il cmdlet **Get-UnifiedGroup** in [PowerShell di Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) per visualizzare le proprietà di Teams e gruppi di Office 365. Questo è un buon modo per ottenere l'URL del sito associato a un team o a un gruppo di Office 365. Ad esempio, il comando seguente consente di visualizzare le proprietà selezionate per un gruppo di Office 365 denominato Senior Leadership Team:

    ```text
    Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl

    DisplayName            : Senior Leadership Team
    Alias                  : seniorleadershipteam
    PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
    SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
    ```

    > [!NOTE]
    > Per eseguire il cmdlet **Get-UnifiedGroup**, è necessario avere il ruolo Destinatari di sola lettura in Exchange Online o essere membri di un gruppo di ruoli assegnato al ruolo Destinatari di sola lettura. 
  
- Quando si esegue la ricerca nella cassetta postale di un utente, non verrà cercata alcuna ricerca in qualsiasi team o gruppo di Office 365 di cui l'utente è membro. Analogamente, quando si applica un blocco a un team o a un gruppo di Office 365 per eDiscovery, solo la cassetta postale del gruppo e il sito del gruppo vengono messi in attesa. Le cassette postali e i siti di OneDrive for Business dei membri del gruppo non vengono messi in attesa a meno che non vengano aggiunti esplicitamente al blocco di eDiscovery. Pertanto, se è necessario mettere in attesa un team o un gruppo di Office 365 per un motivo legale, è consigliabile aggiungere le cassette postali e gli account di OneDrive dei membri del team o del gruppo sullo stesso blocco.

- Per ottenere un elenco dei membri di un team o di un gruppo  di Office 365, è possibile visualizzare le proprietà nella pagina Gruppi nell'interfaccia di amministrazione di Microsoft 365. In alternativa, è possibile eseguire il comando seguente in PowerShell di Exchange Online:

    ```powershell
    Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress
    ```

    > [!NOTE]
    > Per eseguire il cmdlet **Get-UnifiedGroupLinks**, è necessario avere il ruolo Destinatari di sola lettura in Exchange Online o essere membri di un gruppo di ruoli assegnato al ruolo Destinatari di sola lettura.

## <a name="preserve-content-in-onedrive-accounts"></a>Mantenere il contenuto negli account di OneDrive

Per raccogliere un elenco degli URL per i siti di OneDrive for Business nell'organizzazione in modo da poterli aggiungere a un'esenzione o a una ricerca associata a un caso di eDiscovery, vedere Creare un elenco di tutti i percorsi di [OneDrive nell'organizzazione.](https://docs.microsoft.com/onedrive/list-onedrive-urls) Lo script in questo articolo crea un file di testo che contiene un elenco di tutti i siti di OneDrive nell'organizzazione. Per eseguire questo script, è necessario installare e usare SharePoint Online Management Shell. Assicurarsi di aggiungere l'URL del dominio MySite dell'organizzazione a ogni sito OneDrive che si desidera includere nella ricerca. Si tratta del dominio che contiene tutti i siti di OneDrive, ad esempio, `https://contoso-my.sharepoint.com`. Di seguito viene riportato un esempio di sito OneDrive di un utente: `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft.com`.

> [!IMPORTANT]
> L'URL dell'account OneDrive di un utente include il nome dell'entità utente (UPN), ad esempio `https://alpinehouse-my.sharepoint.com/personal/sarad_alpinehouse_onmicrosoft_com` . Nel raro caso in cui l'UPN di una persona viene modificato, anche l'URL di OneDrive cambierà per incorporare il nuovo UPN. Se l'account OneDrive di un utente fa parte di un blocco di eDiscovery, il vecchio e il relativo UPN vengono modificati, è necessario aggiornare il blocco e sarà necessario aggiornare il blocco e aggiungere il nuovo URL di OneDrive dell'utente e rimuovere quello precedente. Per altre informazioni, vedere [Come le modifiche UPN influiscono sull'URL di OneDrive](https://docs.microsoft.com/onedrive/upn-changes).

## <a name="removing-content-locations-from-an-ediscovery-hold"></a>Rimozione di percorsi di contenuto da un blocco di eDiscovery

Dopo la rimozione di una cassetta postale, di un sito di SharePoint o di un account di OneDrive da un blocco di eDiscovery, viene applicato un blocco *di* ritardo. Ciò significa che la rimozione effettiva del blocco viene ritardata di 30 giorni per impedire che i dati vengano eliminati definitivamente (eliminati) da un percorso di contenuto. In questo modo gli amministratori hanno la possibilità di cercare o recuperare il contenuto che verrà eliminato dopo la rimozione di un blocco di eDiscovery. I dettagli del funzionamento del blocco di ritardo per le cassette postali e i siti sono diversi.

- **Cassette postali:** Un blocco di ritardo viene posizionato su una cassetta postale la volta successiva che l'Assistente cartelle gestite elabora la cassetta postale e rileva che un blocco di eDiscovery è stato rimosso. In particolare, un blocco di ritardo viene applicato a una cassetta postale quando l'Assistente cartelle gestite imposta una delle seguenti proprietà della cassetta postale su **True:**

   - **DelayHoldApplied:** Questa proprietà si applica al contenuto correlato alla posta elettronica (generato da utenti che utilizzano Outlook e Outlook sul Web) archiviato nella cassetta postale di un utente.

   - **DelayReleaseHoldApplied:** Questa proprietà si applica ai contenuti basati sul cloud (generati da app non Outlook come Microsoft Teams, Microsoft Forms e Microsoft Yammer) archiviati nella cassetta postale di un utente. I dati cloud generati da un'app Microsoft vengono in genere archiviati in una cartella nascosta nella cassetta postale di un utente.

   Quando viene impostato un blocco di ritardo sulla cassetta postale (quando una delle proprietà precedenti è impostata su **True),** la cassetta postale viene ancora considerata in attesa per una durata illimitata del blocco, come se la cassetta postale fosse in conservazione per controversia legale. Dopo 30 giorni, il blocco di ritardo scade e Microsoft 365 tenterà automaticamente di rimuovere il blocco di ritardo (impostando la proprietà DelayHoldApplied o DelayReleaseHoldApplied su **False)** in modo che il blocco venga rimosso. Dopo che una di queste proprietà è impostata su **False,** gli elementi corrispondenti contrassegnati per la rimozione vengono eliminati alla successiva elaborazione della cassetta postale da parte dell'Assistente cartelle gestite.

   Per altre informazioni, vedere [Gestione della permanenza nelle cassette postali ](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold).

- **Siti di SharePoint e OneDrive:** Qualsiasi contenuto di SharePoint o OneDrive conservato nella raccolta di archiviazione non viene eliminato durante il periodo di attesa di 30 giorni dopo la rimozione di un sito da un blocco di eDiscovery. Questo è simile a quello che accade quando un sito viene rilasciato da un criterio di conservazione. Inoltre, non è possibile eliminare manualmente questo contenuto nella raccolta di archiviazione durante il periodo di attesa di 30 giorni. 

   Per ulteriori informazioni, vedere [Rilascio di un criterio per la conservazione.](retention.md#releasing-a-policy-for-retention)

Un blocco di ritardo viene applicato anche alle posizioni di contenuto in attesa quando si chiude un caso di eDiscovery di base perché i blocchi vengono disattivati quando un caso viene chiuso. Per ulteriori informazioni sulla chiusura di un caso, vedere [Chiudere, riaprire ed eliminare un caso di Core eDiscovery.](close-reopen-delete-core-ediscovery-cases.md)

## <a name="ediscovery-hold-limits"></a>Limiti relativi al blocco di eDiscovery

Nella tabella seguente sono elencati i limiti per i casi di eDiscovery e i blocchi dei casi.

  | Descrizione del limite | Limite |
  |:-----|:-----|
  |Numero massimo di casi per un'organizzazione.  <br/> |Nessun limite  <br/> |
  |Numero massimo di blocchi di eDiscovery per un'organizzazione.  <br/> |10.000  <br/> |
  |Numero massimo di cassette postali in un singolo blocco di eDiscovery. Questo limite include il totale combinato delle cassette postali degli utenti e le cassette postali associate a Gruppi di Microsoft 365, Microsoft Teams e Gruppi di Yammer.  <br/> |1.000  <br/> |
  |Numero massimo di siti in un singolo blocco di eDiscovery. Questo limite include il totale combinato dei siti di OneDrive for Business, dei siti di SharePoint e dei siti associati a Gruppi di Microsoft 365, Microsoft Teams e Gruppi di Yammer.  <br/> |100  <br/> |
  |Numero massimo di casi visualizzati nella home page di eDiscovery e numero massimo di elementi visualizzati nelle schede Esenzioni, Ricerche ed Esporta all'interno di un caso. <sup>1</sup> |1.000|
  |||

   > [!NOTE]
   > <sup>1</sup> Per visualizzare un elenco di più di 1.000 casi, blocchi, ricerche o esportazioni, è possibile utilizzare il cmdlet di PowerShell Per la sicurezza di Office 365 & Conformità:
   >
   > - [Get-ComplianceCase](https://docs.microsoft.com/powershell/module/exchange/get-compliancecase)
   > - [Get-CaseHoldPolicy](https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy)
   > - [Get-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch)
   > - [Get-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction)
