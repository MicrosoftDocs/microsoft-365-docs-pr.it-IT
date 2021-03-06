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
description: È possibile creare un'esenzione associata a un caso di eDiscovery di base in Microsoft 365 per conservare il contenuto rilevante per un'indagine o un caso legale.
ms.openlocfilehash: 61bbe2e8d2713c2960105e2ec4eb4beffcd4306e
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311610"
---
# <a name="create-an-ediscovery-hold"></a>Creare un blocco di eDiscovery

È possibile utilizzare un caso di eDiscovery di base per creare blocchi per conservare il contenuto che potrebbe essere rilevante per il caso. È possibile impostare un blocco sulle cassette postali Exchange e sugli account OneDrive for Business delle persone su cui si sta indagando nel caso. È inoltre possibile mantenere le cassette postali e i siti associati a Microsoft Teams, Office 365 gruppi e Yammer gruppi. Quando si conservano le posizioni del contenuto, il contenuto viene conservato fino a quando non si rimuove il percorso del contenuto dall'esenzione o fino a quando non si elimina il blocco.

Dopo aver creato un blocco di eDiscovery, l'applicazione del blocco potrebbe richiedere fino a 24 ore.

Quando si crea un'esenzione, sono disponibili le opzioni seguenti per l'ambito del contenuto conservato nei percorsi di contenuto specificati:
  
- Creare un'esenzione infinita in cui tutto il contenuto nelle posizioni specificate viene messo in attesa. In alternativa, è possibile creare un'esenzione basata su query in cui viene messo in attesa solo il contenuto nelle posizioni specificate che corrisponde a una query di ricerca.

- Specificare un intervallo di date per mantenere solo il contenuto inviato, ricevuto o creato all'interno di tale intervallo di date. In alternativa, è possibile contenere tutto il contenuto in posizioni specificate indipendentemente dal momento in cui è stato inviato, ricevuto o creato.
  
## <a name="how-to-create-an-ediscovery-hold"></a>Come creare un blocco di eDiscovery

Per creare un blocco eDiscovery associato a un caso di eDiscovery di base:
  
1. Accedere a e accedere utilizzando le credenziali per l'account utente a cui sono state assegnate [https://compliance.microsoft.com](https://compliance.microsoft.com) le autorizzazioni di eDiscovery appropriate.

2. Nel riquadro di spostamento sinistro del Centro Microsoft 365 conformità fare clic su **Mostra** tutto e quindi su **eDiscovery > Core**.

3. Nella pagina **Core eDiscovery** fare clic sul nome del caso in cui si desidera creare il blocco.

4. Nella **home** page del caso fare clic sulla **scheda Esenzione.**
  
5. Nella pagina **Esenzione** fare clic su **Crea.**

6. Nella pagina **Name your hold** wizard assegnare un nome all'esenzione e aggiungere una descrizione facoltativa e quindi fare clic su **Avanti.** Il nome del blocco deve essere univoco nell'organizzazione.

7. Nella pagina **della procedura guidata Scegli** percorsi scegliere i percorsi di contenuto che si desidera mettere in attesa. È possibile piazzare un blocco per cassette postali, siti e cartelle pubbliche.

    ![Scegliere le posizioni dei contenuti da mettere in attesa](../media/eDiscoveryHoldLocations.png)
  
   1. **Cassette postali di Exchange**: impostare l'interruttore su **Attivato** e quindi fare clic su **Scegliere utenti, gruppi o team** per specificare le cassette postali da mettere in attesa. Utilizzare la casella di ricerca per trovare le cassette postali degli utenti e i gruppi di distribuzione da mettere in attesa (per mettere in attesa le cassette postali dei membri del gruppo). È inoltre possibile impostare un blocco sulla cassetta postale associata per un team Microsoft, un Office 365 e un Yammer gruppo. Per ulteriori informazioni sui dati dell'applicazione conservati quando una cassetta postale viene messa in attesa, vedere [Content stored in mailboxes for eDiscovery](what-is-stored-in-exo-mailbox.md).

   1. **Siti di SharePoint**: impostare l'interruttore su **Attivato** quindi fare clic su **Scegli siti** per specificare i siti di SharePoint e gli account di OneDrive da mettere in blocco. Digitare l'URL per ogni sito che si desidera mettere in blocco. È inoltre possibile aggiungere l'URL del sito SharePoint per un team Microsoft, un Office 365 gruppo o un Yammer gruppo.
  
   1. **Cartelle pubbliche di Exchange**: impostare l'interruttore su **attivato** per mettere in stato di blocco tutte le cartelle pubbliche nell'organizzazione di Exchange Online. Non è possibile scegliere cartelle pubbliche specifiche da mettere in blocco. Lasciare l'interruttore disattivato se non si vuole impostare un blocco sulle cartelle pubbliche.

   > [!NOTE]
   > È necessario aggiungere almeno un percorso di contenuto all'esenzione. In caso contrario, le statistiche di blocco di eDiscovery mostreranno che nessun elemento è in attesa.

8. Al termine dell'aggiunta di posizioni all'esenzione, fare clic su **Avanti.**

9. Per creare un blocco basato su query utilizzando parole chiave o condizioni, eseguire la procedura seguente. Per mantenere tutto il contenuto nei percorsi di contenuto specificati, fare clic su **Avanti.**

    ![Creare un blocco basato su query con parole chiave e condizioni](../media/eDiscoveryHoldQuery.png)
  
    1. Nella casella in Parole **chiave** digitare una query per mantenere solo il contenuto corrispondente ai criteri della query. È possibile specificare parole chiave, proprietà dei messaggi di posta elettronica o proprietà del sito, ad esempio i nomi di file. È inoltre possibile utilizzare query più complesse che utilizzano un operatore booleano, ad **esempio AND**, **OR** o **NOT.**

    2. Fare **clic su Aggiungi** condizione per aggiungere una o più condizioni per restringere la query per l'esenzione. Ogni condizione aggiunge una clausola alla query di ricerca KQL creata ed eseguita quando si crea il blocco. Ad esempio, è possibile specificare un intervallo di date in modo che i messaggi di posta elettronica o i documenti del sito creati nell'intervallo di date siano mantenuti. Una condizione è collegata logicamente alla query con parole chiave (specificata nella casella **Parole** chiave) e ad altre condizioni dall'operatore **AND.** Ciò significa che gli elementi devono soddisfare sia la query con parole chiave che la condizione da mantenere.

    Per ulteriori informazioni sulla creazione di una query di ricerca e sull'utilizzo di condizioni, vedere Query con parole chiave e condizioni [di ricerca per eDiscovery.](keyword-queries-and-search-conditions.md)

10. Dopo aver configurato un blocco basato su query, fare clic su **Avanti.**

11. Rivedere le impostazioni e modificarle, se necessario, e quindi fare clic su **Invia.**

## <a name="query-based-holds-placed-on-sites"></a>Blocchi basati su query inseriti nei siti

Tenere presente quanto segue quando si posiziona un blocco eDiscovery basato su query sui documenti che si trovano in SharePoint siti:

- Un blocco basato su query inizialmente mantiene tutti i documenti di un sito per un breve periodo di tempo dopo l'eliminazione. Ciò significa che quando un documento viene eliminato, verrà spostato nella raccolta di archiviazione anche se non corrisponde ai criteri dell'archiviazione basata su query. Tuttavia, i documenti eliminati che non corrispondono a un'archiviazione basata su query verranno rimossi da un processo timer che elabora la raccolta di archiviazione. Il processo timer viene eseguito periodicamente e confronta tutti i documenti nella raccolta di archiviazione con i blocchi di eDiscovery basati su query (e altri tipi di esenzioni e criteri di conservazione). Il processo timer elimina i documenti che non corrispondono a un'esenzione basata su query e mantiene i documenti che lo fanno.

- Le esenzioni basate su query non devono essere utilizzate per eseguire l'archiviazione mirata, ad esempio per conservare i documenti in una cartella o un sito specifico o utilizzando altri criteri di conservazione basati sulla posizione. Questa operazione potrebbe avere risultati imprevisti. È consigliabile utilizzare criteri di conservazione non basati sulla posizione, ad esempio parole chiave, intervalli di date o altre proprietà del documento per conservare i documenti del sito.

## <a name="ediscovery-hold-statistics"></a>Statistiche di blocco di eDiscovery

Dopo aver creato un blocco di eDiscovery, le informazioni sul nuovo blocco vengono visualizzate nella pagina a comparsa per il blocco selezionato. Queste informazioni includono il numero di cassette postali e siti in attesa e le statistiche sul contenuto che è stato messo in attesa, ad esempio il numero totale e le dimensioni degli elementi messi in attesa e l'ultima volta in cui sono state calcolate le statistiche di blocco. Queste statistiche di blocco consentono di identificare la quantità di contenuto correlato al caso in corso di conservazione.
  
![Statistiche di blocco](../media/eDiscoveryHoldStatistics.png)
  
Tenere presenti le seguenti informazioni sulle statistiche di blocco di eDiscovery:
  
- Il numero totale di elementi in attesa indica il numero di elementi di tutte le origini di contenuto che vengono messi in attesa. Se è stata creata un'esenzione basata su query, questa statistica indica il numero di elementi che corrispondono alla query.

- Il numero di elementi in attesa include anche gli elementi non indicizzati trovati nei percorsi del contenuto. Se si crea un'archiviazione basata su query, tutti gli elementi non indicizzati nelle posizioni del contenuto vengono messi in attesa. Sono inclusi gli elementi non indicizzati che non corrispondono ai criteri di ricerca di un'esenzione basata su query e gli elementi non indicizzati che potrebbero non rientrare in una condizione di intervallo di date. Ciò è diverso da quello che accade quando si esegue una ricerca, in cui gli elementi non indicizzati che non corrispondono alla query di ricerca o sono esclusi da una condizione di intervallo di date non vengono inclusi nei risultati della ricerca. Per ulteriori informazioni sugli elementi non indicizzati, vedere [Elementi parzialmente indicizzati.](partially-indexed-items-in-content-search.md)

- È possibile ottenere le statistiche di blocco più recenti facendo clic **su Aggiorna statistiche** per eseguire di nuovo una stima della ricerca che calcola il numero corrente di elementi in attesa.

- È normale che il numero di elementi in attesa aumenti nel tempo perché gli utenti la cui cassetta postale o sito è in attesa in genere inviano o ricevono nuovi messaggi di posta elettronica e creano nuovi documenti in SharePoint e OneDrive.

- Se una cassetta postale di Exchange, un sito di SharePoint o un account OneDrive viene spostato in un'area diversa in un ambiente multi-geografico, le statistiche per tale sito non verranno incluse nelle statistiche di blocco. Tuttavia, il contenuto in tali posizioni verrà comunque conservato. Inoltre, se una cassetta postale o un sito viene spostato in un'area diversa, l'indirizzo SMTP o l'URL visualizzato nel blocco non verrà aggiornato automaticamente. Sarà necessario modificare il blocco e aggiornare l'URL o l'indirizzo SMTP in modo che i percorsi del contenuto siano di nuovo inclusi nelle statistiche di blocco

## <a name="search-locations-on-ediscovery-hold"></a>Percorsi di ricerca nel blocco di eDiscovery

Quando si [cerca contenuto](search-for-content-in-core-ediscovery.md) in un caso di Core eDiscovery, è possibile configurare rapidamente la ricerca in modo che eseezioni solo nei percorsi di contenuto che sono stati inseriti in un blocco associato al caso.

Selezionare **l'opzione Posizioni in attesa** per cercare tutti i percorsi di contenuto che sono stati messi in attesa. Se il caso contiene più blocchi di eDiscovery, quando si seleziona questa opzione verranno cercati i percorsi dei contenuti di tutte le esenzioni. Inoltre, se una posizione del contenuto è stata inserita in un blocco basato su query, quando si esegue la ricerca verranno cercati solo gli elementi che corrispondono alla query di blocco. In altre parole, con i risultati della ricerca viene restituito solo il contenuto che corrisponde sia ai criteri di conservazione che ai criteri di ricerca. Ad esempio, se un utente è stato messo in attesa caso basato su query che mantiene gli elementi che sono stati inviati o creati prima di una data specifica, solo tali elementi verranno cercati. Questa operazione viene eseguita connettendo la query di blocco del caso e la query di ricerca tramite un **operatore AND.**

Ecco alcuni altri aspetti da tenere presenti durante la ricerca di posizioni nel blocco di eDiscovery:

- Se una posizione di contenuto fa parte di più esenzioni nello stesso caso, le query di blocco vengono combinate dagli operatori **OR** quando si esegue una ricerca in tale percorso del contenuto utilizzando l'opzione tutto il contenuto del caso. Analogamente, se un percorso di contenuto fa parte di due blocchi diversi, in cui uno è basato su query e l'altro è un blocco infinito (in cui tutto il contenuto viene messo in attesa), tutto il contenuto viene ricercato a causa dell'archiviazione infinita.

- Se una ricerca è configurata in modo da cercare i percorsi di archiviazione e quindi si modifica un blocco di eDiscovery nel caso (aggiungendo o rimuovendo una posizione o modificando una query di blocco), la configurazione della ricerca viene aggiornata con tali modifiche. Tuttavia, è necessario eseguire di nuovo la ricerca dopo la modifica del blocco per aggiornare i risultati della ricerca.

- Se più blocchi di eDiscovery vengono inseriti in un'unica posizione in un caso di eDiscovery e si sceglie di cercare i percorsi di archiviazione, il numero massimo di parole chiave per la query di ricerca è 500. Ciò è dovuto al fatto che la ricerca combina tutte le esenzioni basate su query utilizzando l'operatore **OR.** Se sono presenti più di 500 parole chiave nelle query di blocco combinate e nella query di ricerca, la ricerca verrà eseguita su tutto il contenuto della cassetta postale, non solo sul contenuto corrispondente al caso basato su query.

- Se lo stato di un blocco di eDiscovery è Attivato **(In sospeso),** è comunque possibile eseguire ricerche nelle posizioni di blocco mentre il blocco è attivato.

## <a name="preserve-content-in-microsoft-teams"></a>Mantenere il contenuto in Microsoft Teams

Le conversazioni che fanno parte di Microsoft Teams vengono archiviate nella cassetta postale associata al team Microsoft. Allo stesso modo, i file che i membri del team condividono in un canale vengono archiviati nel sito di SharePoint del team. Pertanto, è necessario inserire la cassetta postale del team e il SharePoint sul blocco eDiscovery per conservare le conversazioni e i file in un canale.

In alternativa, le conversazioni che fanno parte dell'elenco Chat in Teams (denominate *chat 1:1* o chat di gruppo *1:N)* vengono archiviate nelle cassette postali degli utenti che partecipano alla chat. I file condivisi dagli utenti nelle conversazioni di chat vengono archiviati nell'account OneDrive dell'utente che condivide il file. Pertanto, è necessario aggiungere le singole cassette postali utente e OneDrive account a un blocco di eDiscovery per conservare le conversazioni e i file nell'elenco di chat. È buona idea mettere un blocco sulle cassette postali dei membri di un team Microsoft oltre a mettere in attesa la cassetta postale del team e il sito.

> [!NOTE]
> Se l'organizzazione ha una distribuzione ibrida di Exchange (o l'organizzazione sincronizza un'organizzazione Exchange locale con Office 365) e ha abilitato Microsoft Teams, gli utenti locali possono utilizzare l'applicazione chat di Teams e partecipare a chat 1:1 e chat di gruppo 1:N. Queste conversazioni vengono archiviate nell'archiviazione basata su cloud associata a un utente locale. Se un utente locale viene posto in un blocco di eDiscovery, il contenuto Teams chat nell'archiviazione basata su cloud verrà conservato. Per altre informazioni, vedere [Cercare i dati delle chat di Teams degli utenti locali](search-cloud-based-mailboxes-for-on-premises-users.md).

Per ulteriori informazioni sulla conservazione Teams contenuto, vedere [Place a Microsoft Teams user or team on legal hold.](/MicrosoftTeams/legal-hold)

### <a name="preserve-card-content"></a>Conservare il contenuto della scheda

Analogamente, il contenuto della scheda generato dalle app nei canali di Teams, nelle chat 1:1 e nelle chat di gruppo 1:N viene archiviato nelle cassette postali e viene conservato quando una cassetta postale viene conservata in un blocco di eDiscovery. Una *scheda* è un contenitore di interfaccia utente per piccole parti di contenuto. Le schede possono avere più proprietà e allegati e possono includere pulsanti che attivano le azioni della scheda. Per ulteriori informazioni, vedere [Cards](/microsoftteams/platform/task-modules-and-cards/what-are-cards). Come nel caso di altri contenuti di Teams, il luogo di archiviazione del contenuto delle schede dipende da dove è stata usata la scheda. Il contenuto delle schede usate in un canale di Teams viene archiviato nella cassetta postale di gruppo di Teams. Il contenuto delle schede per chat tra due persone e 1xN viene archiviato nelle cassette postali dei partecipanti alla chat.

### <a name="preserve-meeting-and-call-information"></a>Conservare le informazioni sulle riunioni e sulle chiamate

Le informazioni di riepilogo per le riunioni e le chiamate in un canale Teams vengono archiviate anche nelle cassette postali degli utenti che hanno composto la riunione o la chiamata. Questo contenuto viene conservato anche quando viene effettuato un blocco di eDiscovery sulle cassette postali degli utenti.

### <a name="preserve-content-in-private-channels"></a>Conservare il contenuto nei canali privati

A partire da febbraio 2020, è stata attivata anche la possibilità di conservare il contenuto nei canali privati. Poiché le chat di canale privato vengono archiviate nelle cassette postali dei partecipanti alla chat, l'archiviazione di una cassetta postale utente in eDiscovery consente di conservare le chat dei canali privati. Inoltre, se una cassetta postale utente è stata inserita in un blocco di eDiscovery prima di febbraio 2020, il blocco verrà applicato automaticamente ai messaggi del canale privato archiviati in tale cassetta postale. È inoltre supportata la conservazione dei file condivisi nei canali privati.

### <a name="preserve-wiki-content"></a>Conservare il contenuto wiki

Ogni canale del team o del team contiene anche un Wiki per la raccolta di note e la collaborazione. Il contenuto Wiki viene salvato automaticamente in un file con formato MHT. Il file è archiviato nella raccolta documenti di dati Wiki di Teams nel sito di SharePoint del team. È possibile conservare il contenuto wiki aggiungendo il sito SharePoint team a un blocco eDiscovery.

> [!NOTE]
> La possibilità di conservare il contenuto Wiki per un canale del team o del team (quando si mette in attesa il sito di SharePoint del team) è stata rilasciata il 22 giugno 2017. Se un sito del team è in attesa, il contenuto wiki verrà conservato a partire da tale data. Tuttavia, se un sito del team è in attesa e il contenuto wiki è stato eliminato prima del 22 giugno 2017, il contenuto wiki non è stato conservato.

### <a name="office-365-groups"></a>Gruppi di Office 365

Teams è basato su Office 365 gruppi. Pertanto, l'inserimento Office 365 gruppi nell'archiviazione di eDiscovery è simile all'archiviazione Teams contenuto.

Tenere presente quanto segue quando si inserisce sia Teams che Office 365 gruppi in un blocco di eDiscovery:

- Come spiegato in precedenza, per mettere in attesa il contenuto che si trova nei gruppi Teams e Office 365, è necessario specificare la cassetta postale e il sito SharePoint associato a un gruppo o a un team.

- Eseguire il cmdlet **Get-UnifiedGroup** in [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) per visualizzare le proprietà per Teams e Office 365 gruppi. Questo è un buon modo per ottenere l'URL del sito associato a un team o a un Office 365 gruppo. Ad esempio, il comando seguente consente di visualizzare le proprietà selezionate per un gruppo di Office 365 denominato Senior Leadership Team:

    ```text
    Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl

    DisplayName            : Senior Leadership Team
    Alias                  : seniorleadershipteam
    PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
    SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
    ```

    > [!NOTE]
    > Per eseguire il cmdlet **Get-UnifiedGroup**, è necessario avere il ruolo Destinatari di sola lettura in Exchange Online o essere membri di un gruppo di ruoli assegnato al ruolo Destinatari di sola lettura. 
  
- Quando si esegue la ricerca nella cassetta postale di un utente, non verrà ricercato alcun team o gruppo di Office 365 di cui l'utente è membro. Analogamente, quando si posiziona un team o un gruppo di Office 365 sul blocco di eDiscovery, solo la cassetta postale del gruppo e il sito del gruppo vengono messi in attesa. Le cassette postali e i OneDrive for Business dei membri del gruppo non vengono messi in attesa a meno che non vengano esplicitamente aggiunti al blocco di eDiscovery. Pertanto, se è necessario mettere in attesa un team o un gruppo di Office 365 per un motivo legale, è consigliabile aggiungere le cassette postali e gli account OneDrive dei membri del team o del gruppo sullo stesso blocco.

- Per ottenere un elenco dei membri di un team o di un  gruppo di Office 365, è possibile visualizzare le proprietà nella pagina Gruppi nell'interfaccia Microsoft 365 di amministrazione. In alternativa, è possibile eseguire il comando seguente in PowerShell di Exchange Online:

    ```powershell
    Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress
    ```

    > [!NOTE]
    > Per eseguire il cmdlet **Get-UnifiedGroupLinks**, è necessario avere il ruolo Destinatari di sola lettura in Exchange Online o essere membri di un gruppo di ruoli assegnato al ruolo Destinatari di sola lettura.

## <a name="preserve-content-in-onedrive-accounts"></a>Mantenere il contenuto in OneDrive account

Per raccogliere un elenco degli URL per i siti di OneDrive for Business nell'organizzazione in modo da poterli aggiungere a un'esenzione o a una ricerca associata a un caso di eDiscovery, vedere [Create a list of all OneDrive locations in your organization](/onedrive/list-onedrive-urls). Lo script in questo articolo crea un file di testo contenente un elenco di tutti OneDrive siti dell'organizzazione. Per eseguire questo script, è necessario installare e usare SharePoint Online Management Shell. Assicurarsi di aggiungere l'URL del dominio MySite dell'organizzazione a ogni sito OneDrive che si desidera includere nella ricerca. Si tratta del dominio che contiene tutti i siti di OneDrive, ad esempio, `https://contoso-my.sharepoint.com`. Di seguito viene riportato un esempio di sito OneDrive di un utente: `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft.com`.

> [!IMPORTANT]
> L'URL dell'account OneDrive utente include il nome dell'entità utente (UPN, User Principal Name), ad esempio `https://alpinehouse-my.sharepoint.com/personal/sarad_alpinehouse_onmicrosoft_com` . Nel raro caso in cui l'UPN di una persona viene modificato, anche l'URL OneDrive cambia per incorporare il nuovo UPN. Se l'account OneDrive di un utente fa parte di un blocco di eDiscovery, vecchio e il relativo UPN viene modificato, è necessario aggiornare il blocco e sarà necessario aggiornare il blocco e aggiungere il nuovo URL di OneDrive dell'utente e rimuovere quello precedente. Per altre informazioni, vedere [Come le modifiche UPN influiscono sull'URL di OneDrive](/onedrive/upn-changes).

## <a name="removing-content-locations-from-an-ediscovery-hold"></a>Rimozione di percorsi di contenuto da un blocco di eDiscovery

Dopo che una cassetta postale, SharePoint o un OneDrive viene rimosso da un blocco di eDiscovery, viene applicata una conservazione *di* ritardo. Ciò significa che la rimozione effettiva del blocco viene ritardata di 30 giorni per evitare che i dati vengano eliminati definitivamente (eliminati) da un percorso di contenuto. In questo modo gli amministratori possono cercare o recuperare contenuto che verrà eliminato dopo la rimozione di un blocco di eDiscovery. I dettagli del funzionamento del blocco di ritardo per le cassette postali e i siti sono diversi.

- **Cassette postali:** Un blocco di ritardo viene posizionato su una cassetta postale la volta successiva che l'Assistente cartelle gestite elabora la cassetta postale e rileva che un blocco di eDiscovery è stato rimosso. In particolare, un blocco di ritardo viene applicato a una cassetta postale quando l'Assistente cartelle gestite imposta una delle seguenti proprietà della cassetta postale su **True:**

   - **DelayHoldApplied:** Questa proprietà si applica al contenuto correlato alla posta elettronica (generato da utenti che utilizzano Outlook e Outlook sul Web) archiviato nella cassetta postale di un utente.

   - **DelayReleaseHoldApplied:** Questa proprietà si applica al contenuto basato sul cloud (generato da app non Outlook come Microsoft Teams, Microsoft Forms e Microsoft Yammer) archiviato nella cassetta postale di un utente. I dati cloud generati da un'app Microsoft vengono in genere archiviati in una cartella nascosta nella cassetta postale di un utente.

   Quando viene effettuato un blocco di ritardo sulla cassetta postale (quando una delle proprietà precedenti è impostata su **True),** la cassetta postale viene ancora considerata in attesa per una durata di conservazione illimitata, come se la cassetta postale fosse in attesa per controversia legale. Dopo 30 giorni, il blocco di ritardo scade e Microsoft 365 tenterà automaticamente di rimuovere il blocco di ritardo (impostando la proprietà DelayHoldApplied o DelayReleaseHoldApplied su **False)** in modo che il blocco venga rimosso. Dopo aver impostato una di queste proprietà su **False,** gli elementi corrispondenti contrassegnati per la rimozione vengono eliminati alla successiva elaborazione della cassetta postale da parte dell'Assistente cartelle gestite.

   Per altre informazioni, vedere [Gestione della permanenza nelle cassette postali ](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold).

- **SharePoint e OneDrive siti:** Qualsiasi SharePoint o OneDrive contenuto conservato nella raccolta di archiviazione non viene eliminato durante il periodo di attesa di 30 giorni dopo la rimozione di un sito da un blocco di eDiscovery. Questo è simile a quello che accade quando un sito viene rilasciato da un criterio di conservazione. Inoltre, non è possibile eliminare manualmente questo contenuto nella raccolta di archiviazione durante il periodo di attesa di ritardo di 30 giorni. 

   Per ulteriori informazioni, vedere [Rilascio di un criterio per la conservazione.](retention.md#releasing-a-policy-for-retention)

Un blocco di ritardo viene applicato anche alle posizioni di contenuto in attesa quando si chiude un caso di eDiscovery di base perché le esenzioni vengono disattivate quando un caso viene chiuso. Per ulteriori informazioni sulla chiusura di un caso, vedere [Close, reopen, and delete a Core eDiscovery case.](close-reopen-delete-core-ediscovery-cases.md)

## <a name="ediscovery-hold-limits"></a>Limiti di blocco di eDiscovery

Nella tabella seguente sono elencati i limiti per i casi di eDiscovery e i blocchi dei casi.

  | Descrizione del limite | Limite |
  |:-----|:-----|
  |Numero massimo di casi per un'organizzazione.  <br/> |Nessun limite  <br/> |
  |Numero massimo di blocchi di eDiscovery per un'organizzazione.  <br/> |10.000  <br/> |
  |Numero massimo di cassette postali in un singolo blocco eDiscovery. Questo limite include il totale combinato delle cassette postali degli utenti e le cassette postali associate Microsoft 365 gruppi, Microsoft Teams e Yammer gruppi.  <br/> |1.000  <br/> |
  |Numero massimo di siti in un singolo blocco eDiscovery. Questo limite include il totale combinato di OneDrive for Business, siti SharePoint e siti associati a Microsoft 365 Groups, Microsoft Teams e Yammer Groups.  <br/> |100  <br/> |
  |Numero massimo di casi visualizzati nella home page di eDiscovery e numero massimo di elementi visualizzati nelle schede Esenzioni, Ricerche ed Esportazione all'interno di un caso. <sup>1</sup> |1.000|
  |||

   > [!NOTE]
   > <sup>1</sup> Per visualizzare un elenco di più di 1.000 casi, blocchi, ricerche o esportazioni, è possibile utilizzare il cmdlet di PowerShell Office 365 Security & Compliance corrispondente:
   >
   > - [Get-ComplianceCase](/powershell/module/exchange/get-compliancecase)
   > - [Get-CaseHoldPolicy](/powershell/module/exchange/get-caseholdpolicy)
   > - [Get-ComplianceSearch](/powershell/module/exchange/get-compliancesearch)
   > - [Get-ComplianceSearchAction](/powershell/module/exchange/get-compliancesearchaction)
