---
title: Informazioni di riferimento sulla funzionalità di conformità delle comunicazioni
description: Informazioni di riferimento sulla funzionalità per la conformità delle comunicazioni in Microsoft 365. Informazioni dettagliate e specifiche per ognuno dei componenti delle funzionalità.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: dbfe1d4aaa821714bac68692d3be38ba8aad8e7f
ms.sourcegitcommit: 7ebed5810480d7c49f8ca03207b5ea84993d253f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "51488223"
---
# <a name="communication-compliance-feature-reference"></a>Informazioni di riferimento sulla funzionalità di conformità delle comunicazioni

## <a name="policies"></a>Criteri

>[!Important]
>L'uso di PowerShell per creare e gestire i criteri di conformità delle comunicazioni non è supportato. Per creare e gestire questi criteri, è necessario utilizzare i controlli di gestione dei criteri nella soluzione di conformità alle comunicazioni [di Microsoft 365.](https://compliance.microsoft.com/supervisoryreview)

I criteri di conformità delle comunicazioni vengono creati per le organizzazioni di Microsoft 365 nel Centro conformità Microsoft 365. I criteri di conformità delle comunicazioni definiscono quali comunicazioni e utenti sono soggetti a revisione nell'organizzazione, definiscono le condizioni personalizzate che le comunicazioni devono soddisfare e specificano chi deve eseguire le revisioni. Gli utenti assegnati al ruolo *Amministratore* conformità comunicazione possono configurare i  criteri e chiunque abbia questo ruolo assegnato può accedere alla pagina Conformità comunicazioni e alle impostazioni globali nel Centro conformità Microsoft 365. Se necessario, è possibile esportare la cronologia delle modifiche apportate a un criterio in un file CSV (valori delimitati da virgole) che include anche lo stato degli avvisi in sospeso, degli elementi inoltrati e degli elementi risolti. I criteri non possono essere rinominati e possono essere eliminati quando non sono più necessari.

>[!NOTE]
>I criteri di supervisione creati nel Centro sicurezza & conformità per le sottoscrizioni di Office 365 non possono eseguire la migrazione a Microsoft 365. Se si esegue la migrazione da un abbonamento a Office 365 a un abbonamento a Microsoft 365, è necessario creare nuovi criteri di conformità delle comunicazioni per sostituire i criteri di supervisione esistenti.

## <a name="policy-templates"></a>Modelli dei criteri

I modelli di criteri sono impostazioni predefinite che è possibile utilizzare per creare rapidamente criteri per affrontare scenari di conformità comuni. Ognuno di questi modelli presenta differenze nelle condizioni e nell'ambito e tutti i modelli usano gli stessi tipi di segnali di scansione. È possibile scegliere tra i modelli di criteri seguenti:

|**Area**|**Modello di criteri**|**Dettagli**|
|:-----|:-----|:-----|
| **Linguaggio offensivo e anti-molestie** | Monitorare le comunicazioni per il linguaggio offensivo | - Posizioni: Exchange Online, Microsoft Teams, Yammer, Skype for Business <br> - Direzione: In ingresso, In uscita, Interno <br> - Percentuale revisione: 100% <br> - Condizioni: classificatore del linguaggio offensivo |
| **Informazioni sensibili** | Monitorare le comunicazioni per le informazioni riservate | - Posizioni: Exchange Online, Microsoft Teams, Yammer, Skype for Business <br> - Direzione: In ingresso, In uscita, Interno <br> - Percentuale revisione: 10% <br> - Condizioni: informazioni riservate, modelli di contenuto predefiniti e tipi, opzione dizionario personalizzato, allegati di dimensioni superiori a 1 MB |
| **Conformità normativa** | Monitorare le comunicazioni per informazioni relative alla conformità alle normative finanziarie | - Posizioni: Exchange Online, Microsoft Teams, Yammer, Skype for Business <br> - Direzione: in ingresso, in uscita <br> - Percentuale revisione: 10% <br> - Condizioni: opzione dizionario personalizzato, allegati di dimensioni superiori a 1 MB |
| **Conflitto di interesse** | Monitorare le comunicazioni tra due gruppi o due utenti per evitare conflitti di interesse | - Posizioni: Exchange Online, Microsoft Teams, Yammer, Skype for Business <br> - Direzione: Interno <br> - Percentuale revisione: 100% <br> - Condizioni: Nessuna |

Le comunicazioni vengono analizzate ogni 24 ore dalla creazione dei criteri. Ad esempio, se si crea un criterio linguistico offensivo alle 11.00, il criterio raccoglierà i segnali di conformità delle comunicazioni ogni 24 ore ogni giorno alle 11.00. La modifica di un criterio non cambia questa volta. Per visualizzare la data e l'ora dell'ultima analisi di un criterio, passare alla *colonna Ultima* analisi criteri nella **pagina** Criteri. Dopo aver creato un nuovo criterio, potrebbero essere necessarie fino a 24 ore per visualizzare la prima data e ora di analisi dei criteri. La data e l'ora dell'ultima analisi verranno convertite nel fuso orario del sistema locale.

## <a name="permissions"></a>Autorizzazioni

>[!Important]
>Per impostazione predefinita, gli amministratori globali non hanno accesso alle funzionalità di conformità delle comunicazioni. I ruoli assegnati in questo passaggio sono necessari prima che le funzionalità di conformità della comunicazione siano accessibili.

Esistono cinque gruppi di ruoli utilizzati per configurare le autorizzazioni per gestire le funzionalità di conformità delle comunicazioni. Per rendere **disponibile** la conformità delle comunicazioni come opzione di menu nel Centro conformità Microsoft 365 e continuare con questi passaggi di configurazione, è necessario essere assegnati ai gruppi di ruoli Communication *Compliance* o *Communication Compliance Admin.* Per accedere e gestire le funzionalità di conformità delle comunicazioni dopo la configurazione iniziale, gli utenti devono essere membri di almeno un gruppo di ruoli di conformità delle comunicazioni.

A seconda di come si desidera gestire i criteri di comunicazione e gli avvisi, è necessario assegnare gli utenti a gruppi di ruoli specifici. È possibile assegnare utenti con responsabilità di conformità diverse a gruppi di ruoli specifici per gestire diverse aree di funzionalità di conformità delle comunicazioni. In caso contrario, è possibile decidere di assegnare tutti gli account utente per amministratori, analisti, investigatori e visualizzatori designati al gruppo di ruoli *Conformità* comunicazioni. Utilizzare uno o più gruppi di ruoli per soddisfare al meglio i requisiti di gestione della conformità.

Scegliere tra queste opzioni del gruppo di ruoli per la configurazione della conformità delle comunicazioni:

|**Gruppo di ruolo**|**Autorizzazioni del gruppo di ruoli**|
|:-----|:-----|
| **Conformità delle comunicazioni** | Utilizzare questo gruppo di ruoli per gestire la conformità delle comunicazioni per l'organizzazione in un singolo gruppo. Aggiungendo tutti gli account utente per amministratori, analisti, investigatori e visualizzatori designati, è possibile configurare le autorizzazioni di conformità delle comunicazioni in un singolo gruppo. Questo gruppo di ruoli contiene tutti i ruoli di autorizzazione di conformità delle comunicazioni. Questa configurazione è il modo più semplice per iniziare rapidamente a utilizzare la conformità delle comunicazioni ed è adatta per le organizzazioni che non necessitano di autorizzazioni separate definite per gruppi di utenti distinti. |
| **Communication Compliance Admin** | Utilizzare questo gruppo di ruoli per configurare inizialmente la conformità delle comunicazioni e successivamente per separare gli amministratori di conformità delle comunicazioni in un gruppo definito. Gli utenti assegnati a questo gruppo di ruoli possono creare, leggere, aggiornare ed eliminare criteri di conformità delle comunicazioni, impostazioni globali e assegnazioni di gruppi di ruoli. Gli utenti assegnati a questo gruppo di ruoli non possono visualizzare gli avvisi dei messaggi. |
| **Communication Compliance Analyst** | Utilizzare questo gruppo per assegnare autorizzazioni agli utenti che fungeranno da analisti della conformità delle comunicazioni. Gli utenti assegnati a questo gruppo di ruoli possono visualizzare i criteri in cui sono assegnati come revisori, visualizzare i metadati dei messaggi (non il contenuto del messaggio), inoltrare ad altri revisori o inviare notifiche agli utenti. Gli analisti non possono risolvere gli avvisi in sospeso. |
| **Communication Compliance Investigator** | Utilizzare questo gruppo per assegnare autorizzazioni agli utenti che agiranno come investigatori della conformità delle comunicazioni. Gli utenti assegnati a questo gruppo di ruoli possono visualizzare i metadati e il contenuto dei messaggi, inoltrare ad altri revisori, inoltrare a un caso advanced eDiscovery, inviare notifiche agli utenti e risolvere l'avviso. |
| **Visualizzatore conformità comunicazioni** | Utilizzare questo gruppo per assegnare autorizzazioni agli utenti che gestiranno i report di comunicazione. Gli utenti assegnati a questo gruppo di ruoli possono accedere a tutti i widget di report nella home page di conformità delle comunicazioni e possono visualizzare tutti i report di conformità delle comunicazioni. |

### <a name="for-organizations-using-the-original-permissions-and-role-groups"></a>Per le organizzazioni che utilizzano le autorizzazioni originali e i gruppi di ruoli

La nuova struttura del gruppo di ruoli sostituisce la struttura iniziale del gruppo di ruoli per la conformità alle comunicazioni. Per le organizzazioni che già usano la conformità delle comunicazioni, è necessario avere il ruolo di amministratore della revisione della supervisione per iniziare a usare la conformità delle comunicazioni nel Centro conformità Microsoft 365. Inoltre, è stato necessario creare un nuovo gruppo di ruoli per i revisori con i ruoli Supervisory Review Administrator, Case Management, Compliance Administrator e Review per analizzare e correggere i messaggi con le corrispondenze dei criteri. In sostanza, tutti gli amministratori e i revisori si trovavano in un singolo gruppo di ruoli e tutti avevano le stesse autorizzazioni di accesso e gestione. Con gli aggiornamenti più recenti per la conformità delle comunicazioni, è consigliabile pianificare la migrazione dalla struttura del gruppo di ruoli precedente alla nuova struttura del gruppo di ruoli. Il supporto per la struttura del gruppo di ruoli precedente verrà gradualmente sfasato.

Per facilitare la pianificazione della migrazione, considerare l'esempio seguente. Attualmente nell'organizzazione sono presenti tre tipi di utenti, amministratori IT, valutazione e revisori. Questi tre tipi di utenti sono nella struttura del gruppo di ruoli precedente e sono tutti membri di un singolo gruppo di ruoli a cui sono assegnati i ruoli seguenti:

- Supervisory Review Administrator
- Gestione dei casi
- Amministratore conformità
- Revisione

Per aggiornare i ruoli per questi utenti per la nuova struttura del gruppo di ruoli e per separare le autorizzazioni di accesso e gestione per gli utenti, è possibile prendere in considerazione tre nuovi gruppi e le assegnazioni dei nuovi gruppi di ruolo associate:

- **Amministratori IT**: assegnato al nuovo gruppo di ruoli *Communication Compliance Admin.*
- **Triage**: assegnato al gruppo di ruoli *Communication Compliance Analyst.*
- **Revisori**: assegnato al nuovo gruppo di ruoli *Investigatore conformità* comunicazioni.

## <a name="supervised-users"></a>Utenti con supervisione

Prima di iniziare a usare la conformità delle comunicazioni, è necessario determinare chi deve essere esaminato dalle comunicazioni. Nel criterio, gli indirizzi di posta elettronica degli utenti identificano gli utenti o i gruppi di persone da supervisionare. Alcuni esempi di questi gruppi sono i gruppi di Microsoft 365, le liste di distribuzione basate su Exchange, le community di Yammer e i canali di Microsoft Teams. È inoltre possibile escludere utenti o gruppi specifici dall'analisi con un gruppo di esclusione specifico o un elenco di gruppi. Per ulteriori informazioni sui tipi di gruppi supportati nei criteri di conformità delle comunicazioni, vedere [Introduzione alla conformità delle comunicazioni.](communication-compliance-configure.md#step-3-optional-set-up-groups-for-communication-compliance)

>[!IMPORTANT]
>Gli utenti coperti dai criteri di conformità delle comunicazioni devono disporre di una licenza di conformità di Microsoft 365 E5, di una licenza di Office 365 Enterprise E3 con il componente aggiuntivo Conformità avanzata o di essere inclusi in un abbonamento a Office 365 Enterprise E5. Se non si dispone di un piano Enterprise E5 esistente e si desidera provare la conformità delle comunicazioni, è possibile iscriversi a una versione di valutazione di [Office 365 Enterprise E5.](https://go.microsoft.com/fwlink/p/?LinkID=698279)

## <a name="reviewers"></a>Revisori

Quando si crea un criterio di conformità delle comunicazioni, è necessario determinare chi rivede i messaggi degli utenti supervisionati. Nel criterio, gli indirizzi di posta elettronica degli utenti identificano gli utenti o i gruppi di persone per esaminare le comunicazioni supervisionate. Tutti i revisori devono disporre di cassette postali ospitate in Exchange Online e devono essere assegnate ai ruoli *Analisi* di conformità delle comunicazioni o *Analisi di conformità delle* comunicazioni. Ai revisori (analisti o investigatori) deve essere assegnato anche il ruolo *Gestione* dei casi di conformità della comunicazione. Quando i revisori vengono aggiunti a un criterio, ricevono automaticamente un messaggio di posta elettronica che li informa dell'assegnazione al criterio e fornisce collegamenti a informazioni sul processo di revisione.

## <a name="groups-for-supervised-users-and-reviewers"></a>Gruppi per utenti e revisori supervisionati

Per semplificare la configurazione, creare gruppi per gli utenti che necessitano di un controllo delle comunicazioni e gruppi per gli utenti che rivedeno tali comunicazioni. Se si usano gruppi, potrebbero essere necessari diversi. Ad esempio, se si desidera analizzare le comunicazioni tra due gruppi distinti di persone o se si desidera specificare un gruppo che non è supervisionato.

Quando si assegna un gruppo di distribuzione nel criterio, il criterio monitora tutti i messaggi di posta elettronica di ogni utente nel gruppo di distribuzione. Quando si assegna un gruppo di Microsoft 365 nel criterio, il criterio monitora tutti i messaggi di posta elettronica inviati a tale gruppo, non i singoli messaggi di posta elettronica ricevuti da ogni membro del gruppo.

L'aggiunta di gruppi e liste di distribuzione ai criteri di conformità delle comunicazioni fa parte delle condizioni e delle regole generali impostate, pertanto il numero massimo di gruppi e liste di distribuzione supportate da un criterio varia a seconda del numero di condizioni aggiunte al criterio. Ogni criterio deve supportare circa 20 gruppi o liste di distribuzione, a seconda del numero di condizioni aggiuntive presenti nel criterio.

## <a name="supported-communication-types"></a>Tipi di comunicazione supportati

Con i criteri di conformità delle comunicazioni, è possibile scegliere di analizzare i messaggi in una o più delle piattaforme di comunicazione seguenti come gruppo o come origini autonome. Per impostazione predefinita, le comunicazioni acquisite su queste piattaforme vengono mantenute per sette anni per ogni criterio, anche se gli utenti lasciano l'organizzazione e le loro cassette postali vengono eliminate.

- **Microsoft Teams:** è possibile analizzare le comunicazioni chat sia nei canali pubblici che privati di Microsoft Teams e nelle singole chat. Quando gli utenti vengono assegnati a un criterio di conformità delle comunicazioni con la copertura di Microsoft Teams selezionata, le comunicazioni di chat per gli utenti vengono monitorate automaticamente in tutti i Microsoft Teams in cui gli utenti sono membri. La copertura di Microsoft Teams viene inclusa automaticamente per i modelli di criteri predefiniti ed è selezionata per impostazione predefinita nel modello di criteri personalizzato. L'elaborazione delle chat di Teams che corrispondono alle condizioni dei criteri di conformità della comunicazione può richiedere fino a 48 ore. Utilizzare le configurazioni di gestione dei gruppi seguenti per supervisionare le singole chat utente e le comunicazioni dei canali in Teams:

    - **Per le comunicazioni chat di Teams:** Assegnare singoli utenti o assegnare un [gruppo di distribuzione](https://support.office.com/article/Distribution-groups-E8BA58A8-FAB2-4AAF-8AA1-2A304052D2DE) ai criteri di conformità delle comunicazioni. Questa impostazione è per le relazioni utente/chat uno-a-uno o uno-a-molti.
    - **Per le comunicazioni di Teams Channel:** Assegnare ai criteri di conformità delle comunicazioni ogni canale di Microsoft Teams o gruppo di Microsoft 365 che si desidera analizzare contenente un utente specifico. Se si aggiunge lo stesso utente ad altri canali di Microsoft Teams o gruppi di Microsoft 365, assicurarsi di aggiungere questi nuovi canali e gruppi ai criteri di conformità delle comunicazioni. Se un membro del canale è un utente con supervisione all'interno di un criterio e la direzione *in* ingresso è configurata in un criterio, tutti i messaggi inviati all'interno del canale sono soggetti alla revisione e alle possibili corrispondenze dei criteri (anche per gli utenti nel canale che non sono supervisionati esplicitamente). Ad esempio, l'utente A è il proprietario o un membro di un canale. L'utente B e l'utente C sono membri dello stesso canale e utilizzano un linguaggio corrispondente ai criteri di lingua offensivi che controllano solo l'utente A. L'utente B e l'utente C creano corrispondenze dei criteri per le conversazioni all'interno del canale anche se non sono direttamente controllati nei criteri di linguaggio offensivo. Le conversazioni di Teams tra l'utente B e l'utente C che si trova all'esterno del canale che include l'utente A non sono soggette ai criteri di linguaggio offensivi che includono l'utente A. Per escludere i membri del canale dalla supervisione quando altri membri del canale vengono supervisionati in modo esplicito, disattivare l'impostazione Direzione di comunicazione *in* ingresso nei criteri di conformità delle comunicazioni applicabili.
    - **Per le comunicazioni chat** di Teams con ambienti di posta elettronica ibridi: la conformità delle comunicazioni può monitorare i messaggi di chat per gli utenti delle organizzazioni con una distribuzione di Exchange locale o un provider di posta elettronica esterno che ha abilitato Microsoft Teams. È necessario creare un gruppo di distribuzione per gli utenti con cassette postali locali o esterne da monitorare. Quando si crea un criterio di conformità delle  comunicazioni, si assegna questo gruppo di distribuzione come selezione Di utenti e gruppi supervisionati nella procedura guidata dei criteri.

- **Posta elettronica di Exchange:** le cassette postali ospitate in Exchange Online nell'ambito dell'abbonamento a Microsoft 365 o Office 365 sono tutte idonee per l'analisi dei messaggi. L'elaborazione dei messaggi di posta elettronica e degli allegati di Exchange che corrispondono alle condizioni dei criteri di conformità delle comunicazioni può richiedere fino a 24 ore. I tipi di allegati supportati per la conformità delle comunicazioni sono gli stessi dei tipi di file supportati per le ispezioni del contenuto delle regole del flusso di posta [di Exchange.](/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection)

- **Yammer:** è possibile analizzare i messaggi privati e le conversazioni pubbliche e gli allegati associati nelle community di Yammer. Quando un utente viene aggiunto ai criteri di conformità delle comunicazioni che includono Yammer come canale definito, le comunicazioni tra tutte le community yammer di cui l'utente è membro sono incluse nel processo di analisi. L'elaborazione delle chat e degli allegati di Yammer che corrispondono alle condizioni dei criteri di conformità delle comunicazioni può richiedere fino a 24 ore. Yammer deve essere in [modalità nativa per i](/yammer/configure-your-yammer-network/overview-native-mode) criteri di conformità delle comunicazioni per monitorare le comunicazioni e gli allegati di Yammer. In modalità nativa, tutti gli utenti di Yammer sono in Azure Active Directory (AAD), tutti i gruppi sono gruppi di Office 365 e tutti i file sono archiviati in SharePoint Online.

- **Skype for Business online:** è possibile supervisionare le comunicazioni chat e gli allegati associati in Skype for Business online. L'elaborazione delle chat di Skype for Business online che corrispondono alle condizioni dei criteri di conformità delle comunicazioni può richiedere fino a 24 ore. Le conversazioni di chat supervisionate derivano da [conversazioni precedenti salvate in Skype for Business online.](https://support.office.com/article/Find-a-previous-Skype-for-Business-conversation-18892eba-5f18-4281-8c87-fd48bd72e6a2)  Utilizzare la configurazione di gestione dei gruppi seguente per supervisionare le comunicazioni di chat degli utenti in Skype for Business online:

    - **Per le comunicazioni chat di Skype for Business Online:** assegnare singoli utenti o assegnare un [gruppo di distribuzione](https://support.office.com/article/Distribution-groups-E8BA58A8-FAB2-4AAF-8AA1-2A304052D2DE) ai criteri di conformità delle comunicazioni. Questa impostazione è per le relazioni utente/chat uno-a-uno o uno-a-molti.

- **Origini di terze** parti: è possibile analizzare le comunicazioni per i dati importati nelle cassette postali dell'organizzazione di Microsoft 365 da origini di terze parti come [Instant Bloomberg,](archive-instant-bloomberg-data.md) [Slack,](archive-slack-data.md) [Zoom,](archive-zoommeetings-data.md)SMS e molti altri. Per un elenco completo dei connettori supportati nella conformità delle comunicazioni, vedere [Archive third-party data](archiving-third-party-data.md).

    È necessario configurare un connettore di terze parti per l'organizzazione di Microsoft 365 prima di poter assegnare il connettore a un criterio di conformità delle comunicazioni. Nella **sezione Origini di terze parti** della procedura guidata dei criteri di conformità delle comunicazioni vengono visualizzati solo i connettori di terze parti attualmente configurati.

## <a name="policy-settings"></a>Impostazioni dei criteri

### <a name="users"></a>Utenti

È possibile selezionare Tutti **gli** utenti o definire utenti specifici in un criterio di conformità delle comunicazioni. Selezionando **Tutti gli utenti,** il criterio viene applicato a tutti gli utenti e a tutti i gruppi in cui è incluso qualsiasi utente come membro. La definizione di utenti specifici applica il criterio agli utenti definiti e a tutti i gruppi in cui gli utenti definiti sono inclusi come membri.

### <a name="direction"></a>Direction

Per impostazione predefinita, **la condizione Direction** è visualizzata e non può essere rimossa. Le impostazioni della direzione di comunicazione in un criterio vengono scelte singolarmente o insieme:

- **In ingresso:** è possibile scegliere **In ingresso** per esaminare le comunicazioni **inviate** alle persone che si è scelto di supervisionare.
- **In** uscita: è possibile scegliere **In** uscita se si desidera esaminare le comunicazioni inviate **dalle** persone che si è scelto di supervisionare.
- **Interno**: è possibile scegliere **Interno** per esaminare le comunicazioni inviate **tra** le persone identificate nel criterio.

### <a name="sensitive-information-types"></a>Tipi di informazioni sensibili

È possibile includere i tipi di informazioni riservate nell'ambito dei criteri di conformità delle comunicazioni. I tipi di informazioni riservate sono tipi di dati predefiniti o personalizzati che consentono di identificare e proteggere i numeri di carta di credito, i numeri di conto corrente bancario, i numeri di passaporto e altro ancora. Come parte della prevenzione della perdita dei dati [(DLP),](data-loss-prevention-policies.md)la configurazione delle informazioni riservate può utilizzare modelli, prossimità dei caratteri, livelli di probabilità e anche tipi di dati personalizzati per identificare e contrassegnare il contenuto che potrebbe essere sensibile. I tipi di informazioni riservate predefiniti sono:

- Finanze
- Medical and health
- Privacy
- Tipo di informazioni personalizzato

Per ulteriori informazioni sui dettagli delle informazioni riservate e sui modelli inclusi nei tipi predefiniti, vedere [Definizioni di](sensitive-information-type-entity-definitions.md)entità del tipo di informazioni riservate .

### <a name="custom-keyword-dictionaries"></a>Dizionari parole chiave personalizzati

Configurare dizionari di parole chiave personalizzati (o lessiconi) per fornire una gestione semplice delle parole chiave specifiche dell'organizzazione o del settore. I dizionari parole chiave supportano fino a 100 KB di termini (post-compressione) nel dizionario e supportano qualsiasi lingua. Il limite del tenant è anche di 100 KB dopo la compressione. Se necessario, è possibile applicare più dizionari parole chiave personalizzati a un singolo criterio o disporre di un singolo dizionario di parole chiave per criterio. Questi dizionari vengono assegnati in un criterio di conformità della comunicazione e possono essere provenienti da un file (ad esempio un elenco csv o txt) o da un elenco che è possibile importare nel Centro [conformità.](create-a-keyword-dictionary.md) Utilizzare dizionari personalizzati quando è necessario supportare termini o lingue specifici dell'organizzazione e dei criteri.

### <a name="classifiers"></a>Classificatori

I classificatori predefiniti e globali analizzano i messaggi inviati o ricevuti in tutti i canali di comunicazione dell'organizzazione per i diversi tipi di problemi di conformità. I classificatori usano una combinazione di intelligenza artificiale e parole chiave per identificare il linguaggio nei messaggi che potrebbero violare i criteri anti-molestie. I classificatori incorporati attualmente supportano l'identificazione delle parole chiave dei messaggi in diverse lingue:

- Cinese (semplificato)
- Inglese
- Francese
- Tedesco
- Italiano
- Giapponese
- Portoghese
- Spagnolo

I classificatori predefiniti per la conformità delle comunicazioni e globali analizzano le comunicazioni alla ricerca di termini, immagini e valutazioni per i seguenti tipi di linguaggio e contenuto:

- **Minaccia:** analizza le minacce per commettere violenza o danni fisici a una persona o a una proprietà.
- **Molestie mirate:** analizza il comportamento offensivo rivolto alle persone in merito a etnie, colori, religiosi, origini nazionali.
- **Volgarità:** esegue la ricerca di espressioni volgari che mette in imbarazzo la maggior parte delle persone.
- **Immagini per adulti:** esegue la ricerca di immagini di natura sessuale esplicita.
- **Immagini racy:** esegue la ricerca di immagini di natura sessuale indicativa, ma che contengono contenuto meno esplicito rispetto alle immagini ritenute adulte.
- **Immagini gory**: Esegue la ricerca di immagini che ritraggono la violenza e la gore.

I *classificatori* di immagini Per adulti, *Racy* e *Gory* analizzano i file nei formati .jpeg, .png, .gif e .bmp. Le dimensioni dei file di immagine devono essere inferiori a 4 megabyte (MB) e le dimensioni delle immagini devono essere maggiori di 50x50 pixel e superiori a 50 kilobyte (KB) per l'immagine per essere idonea per la valutazione. L'identificazione dell'immagine è supportata per i messaggi di posta elettronica di Exchange Online e i canali e le chat di Microsoft Teams.

I classificatori predefiniti disponibili per il training e i classificatori globali non forniscono un elenco esaustivo di termini o immagini in queste aree. Inoltre, gli standard linguistici e culturali cambiano continuamente e, alla luce di queste realtà, Microsoft si riserva il diritto di aggiornare i classificatori a sua discrezione. Anche se i classificatori possono aiutare l'organizzazione a monitorare queste aree, i classificatori non sono destinati a fornire l'unico mezzo per monitorare o affrontare tale linguaggio o immagini dell'organizzazione. L'organizzazione, non Microsoft, rimane responsabile di tutte le decisioni relative al monitoraggio, all'analisi e al blocco della lingua e delle immagini in queste aree, inclusa la conformità con la privacy locale e altre leggi applicabili. Microsoft incoraggia la consulenza con i consulenti legali prima della distribuzione e dell'uso.

>[!NOTE]
>I criteri che usano classificatori ispezionano e valutano i messaggi con un numero di parole uguale o superiore a sei. I messaggi contenenti meno di sei parole non vengono valutati nei criteri tramite classificatori. Per identificare ed eseguire azioni su messaggi più brevi contenenti contenuto inappropriato, è consigliabile includere un dizionario di parole chiave personalizzato per il monitoraggio dei criteri di conformità delle comunicazioni per questo tipo di contenuto.

Per informazioni sui classificatori addestrabili in Microsoft 365, vedere [Introduzione ai classificatori addestrabili.](classifier-get-started-with.md)

### <a name="optical-character-recognition-ocr-preview"></a>Riconoscimento ottico dei caratteri (OCR) (anteprima)

Configurare criteri di conformità delle comunicazioni incorporati o personalizzati per analizzare e identificare il testo stampato o scritto a mano da immagini che potrebbero non essere appropriati nell'organizzazione. Servizi cognitivi di Azure integrati e il supporto per l'analisi ottica per identificare il testo nelle immagini consentono ad analisti e investigatori di rilevare e agire su casi in cui una condotta inappropriata potrebbe non essere rilevata nelle comunicazioni principalmente non testuali.

È possibile abilitare il riconoscimento ottico dei caratteri (OCR) nei nuovi criteri da modelli, criteri personalizzati o aggiornare i criteri esistenti per espandere il supporto per l'elaborazione di immagini e allegati incorporati. Se abilitata in un criterio creato da un modello di criteri, l'analisi automatica è supportata per le immagini incorporate o allegate nei messaggi di posta elettronica e nei messaggi di chat di Microsoft Teams. Per i criteri personalizzati, una o più impostazioni condizionali associate a parole chiave, classificatori incorporati o tipi di informazioni riservate devono essere configurate nel criterio per abilitare la selezione dell'analisi OCR.

Le immagini da 50 KB a 4 MB nei formati di immagine seguenti vengono analizzate ed elaborate:

- .jpg/.jpeg (gruppo di esperti fotografici congiunti)
- .png (grafica di rete portatile)
- .bmp (bitmap)
- .tiff (formato file immagine tag)
- .pdf (formato documento portatile)

>[!NOTE]
>L'analisi e l'estrazione di immagini PDF incorporate e allegate è attualmente supportata solo per i messaggi di posta elettronica.

Quando si esaminano gli avvisi in sospeso per i criteri con OCR abilitato, le immagini identificate e corrispondenti alle condizioni dei criteri vengono visualizzate come elementi figlio per gli avvisi associati. È possibile visualizzare l'immagine originale per valutare il testo identificato nel contesto del messaggio originale. La disponibilità delle immagini rilevate con avvisi può richiedere fino a 48 ore.

### <a name="conditional-settings"></a>Impostazioni condizionali
<a name="ConditionalSettings"> </a>

Le condizioni selezionate per il criterio si applicano alle comunicazioni provenienti sia dalla posta elettronica che da origini di terze parti nell'organizzazione (ad esempio da Instant Bloomberg).

Nella tabella seguente vengono illustrate ulteriori informazioni su ogni condizione.
  
|**Condizione**|**Come usare questa condizione**|
|:-----|:-----|
| **Il contenuto corrisponde a uno di questi classificatori** | Applica al criterio quando tutti i classificatori vengono inclusi o esclusi in un messaggio. Alcuni classificatori sono predefiniti nel tenant e i classificatori personalizzati devono essere configurati separatamente prima che siano disponibili per questa condizione. Solo un classificatore può essere definito come condizione in un criterio. Per ulteriori informazioni sulla configurazione dei classificatori, vedere [Learn about trainable classifiers (preview)](classifier-learn-about.md). |
| **Il contenuto contiene uno di questi tipi di informazioni riservate** | Applica al criterio quando qualsiasi tipo di informazione sensibile viene incluso o escluso in un messaggio. Alcuni classificatori sono predefiniti nel tenant e i classificatori personalizzati possono essere configurati separatamente o come parte del processo di assegnazione delle condizioni. Ogni tipo di informazioni riservate scelto viene applicato separatamente e solo uno di questi tipi di informazioni riservate deve essere applicato per applicare il criterio al messaggio. Per ulteriori informazioni sui tipi di informazioni riservate personalizzati, vedere [Informazioni sui tipi di informazioni riservate.](sensitive-information-type-learn-about.md) |
| **Il messaggio viene ricevuto da uno di questi domini**  <br><br> **Il messaggio non viene ricevuto da uno di questi domini** | Applicare il criterio per includere o escludere domini o indirizzi di posta elettronica specifici nei messaggi ricevuti. Immettere ogni dominio o indirizzo di posta elettronica e separare più domini o indirizzi di posta elettronica con una virgola. Ogni dominio o indirizzo di posta elettronica immesso viene applicato separatamente, solo un dominio o un indirizzo di posta elettronica deve applicare il criterio al messaggio. <br><br> Se si desidera analizzare tutti i messaggi di posta elettronica di un dominio specifico, ma escludere i messaggi che  non necessitano di revisione (newsletter, annunci e così via), è necessario configurare una condizione Messaggio non ricevuto da uno di questi domini che esclude l'indirizzo di posta elettronica (ad esempio "newsletter@contoso.com"). |
| **Il messaggio viene inviato a uno di questi domini**  <br><br> **Il messaggio non viene inviato ad alcuno di questi domini** | Applicare il criterio per includere o escludere domini o indirizzi di posta elettronica specifici nei messaggi inviati. Immettere ogni dominio o indirizzo di posta elettronica e separare più domini o indirizzi di posta elettronica con una virgola. Ogni dominio o indirizzo di posta elettronica viene applicato separatamente, solo un dominio o un indirizzo di posta elettronica deve applicare il criterio al messaggio. <br><br> Se si desidera analizzare tutti i messaggi di posta elettronica inviati a un dominio specifico, ma si desidera escludere i messaggi inviati che non necessitano di revisione, è necessario configurare due condizioni: <br> - Un **messaggio viene inviato a uno di questi** domini condizione che definisce il dominio ("contoso.com"), AND <br> - Un **messaggio non viene inviato ad alcuna condizione** di questi domini che esclude l'indirizzo di posta elettronica ("subscriptions@contoso.com"). |
| **Il messaggio viene classificato con una di queste etichette**  <br><br> **Il messaggio non è classificato con nessuna di queste etichette** | Per applicare il criterio quando determinate etichette di conservazione vengono incluse o escluse in un messaggio. Le etichette di conservazione devono essere configurate separatamente e le etichette configurate vengono scelte come parte di questa condizione. Ogni etichetta scelta viene applicata separatamente (solo una di queste etichette deve essere applicata al criterio da applicare al messaggio). Per ulteriori informazioni sulle etichette di conservazione, vedere [Informazioni sui criteri di conservazione e sulle etichette di conservazione.](retention.md)|
| **Il messaggio contiene una di queste parole**  <br><br> **Il messaggio non contiene nessuna di queste parole** | Per applicare il criterio quando determinate parole o frasi vengono incluse o escluse in un messaggio, immettere ogni parola separata da una virgola. Per frasi di due o più parole, utilizzare le virgolette attorno alla frase. Ogni parola o frase immessa viene applicata separatamente (per applicare il criterio al messaggio è necessario applicare una sola parola). Per ulteriori informazioni sull'immissione di parole o frasi, vedere la sezione successiva Corrispondenza di parole e frasi a messaggi di posta [elettronica o allegati.](communication-compliance-feature-reference.md#Matchwords)|
| **L'allegato contiene una di queste parole**  <br><br> **L'allegato non contiene nessuna di queste parole** | Per applicare il criterio quando determinate parole o frasi vengono incluse o escluse in un allegato di un messaggio,ad esempio un documento di Word, immettere ogni parola separata da una virgola. Per frasi di due o più parole, utilizzare le virgolette attorno alla frase. Ogni parola o frase immessa viene applicata separatamente (per applicare il criterio all'allegato deve essere applicata una sola parola). Per ulteriori informazioni sull'immissione di parole o frasi, vedere la sezione successiva Corrispondenza di parole e frasi a messaggi di posta [elettronica o allegati.](communication-compliance-feature-reference.md#Matchwords)|
| **L'allegato è uno di questi tipi di file**  <br><br> **L'allegato non è uno di questi tipi di file** | Per supervisionare le comunicazioni che includono o escludono tipi specifici di allegati, immettere le estensioni di file ,ad esempio .exe o .pdf. Se si desidera includere o escludere più estensioni di file, immetterli in righe separate. Per applicare il criterio, è necessario che una sola estensione dell'allegato corrisponda.|
| **La dimensione del messaggio è superiore a**  <br><br> **La dimensione del messaggio non è superiore a** | Per esaminare i messaggi in base a una determinata dimensione, utilizzare queste condizioni per specificare le dimensioni massime o minime che un messaggio può avere prima di essere sottoposto a revisione. Se ad esempio  si specifica una dimensione del messaggio superiore a \> **1,0 MB,** tutti i messaggi di dimensioni superiori a 1,01 MB sono soggetti a revisione. È possibile scegliere byte, kilobyte, megabyte o gigabyte per questa condizione.|
| **L'allegato è più grande di**  <br><br> **L'allegato non è più grande di** | Per esaminare i messaggi in base alle dimensioni degli allegati, specificare la dimensione massima o minima che un allegato può avere prima che il messaggio e i relativi allegati siano soggetti a revisione. Ad esempio, se si specifica **Che** l'allegato è superiore a \> **2,0 MB,** tutti i messaggi con allegati di 2,01 MB e oltre sono soggetti a revisione. È possibile scegliere byte, kilobyte, megabyte o gigabyte per questa condizione.|
   
#### <a name="matching-words-and-phrases-to-emails-or-attachments"></a>Corrispondenza di parole e frasi a messaggi di posta elettronica o allegati
<a name="Matchwords"> </a>

Ogni parola immessa e separata con una virgola viene applicata separatamente (per applicare la condizione del criterio al messaggio di posta elettronica o all'allegato deve essere applicata una sola parola). Ad esempio, usiamo la condizione **Message** contiene una di queste parole, con le parole chiave "banker", "confidential" e "insider trading" separate da una virgola (banker, confidential,"insider trading"). Il criterio si applica a tutti i messaggi che includono la parola "banker", "confidential" o la frase "insider trading". Per applicare questa condizione dei criteri, è necessario che si verifichi solo una di queste parole o frasi. Le parole nel messaggio o nell'allegato devono corrispondere esattamente a quelle immesse.

>[!IMPORTANT]
>Quando si importa un file di dizionario personalizzato, ogni parola o frase deve essere separata con un ritorno a capo e su una riga separata. <br> Ad esempio: <br><br>
>*banker* <br>
>*confidential* <br>
>*insider trading*

Per analizzare sia i messaggi di posta [](create-test-tune-dlp-policy.md) elettronica che gli [](create-a-keyword-dictionary.md) allegati per le stesse parole chiave, creare un criterio di prevenzione della perdita di dati con un dizionario di parole chiave personalizzato per i termini che si desidera analizzare nei messaggi. Questa configurazione dei criteri identifica le parole chiave definite che vengono visualizzate nel messaggio di posta elettronica **o nell'allegato** di posta elettronica. L'utilizzo delle impostazioni dei criteri condizionali standard (*Message* contiene una qualsiasi di queste parole e *Attachment* contiene una qualsiasi di queste parole) per identificare i termini nei messaggi e negli allegati richiede che i termini siano presenti **sia** nel messaggio che nell'allegato.
  
#### <a name="enter-multiple-conditions"></a>Immettere più condizioni

Se si immettono più condizioni, Microsoft 365 usa tutte le condizioni insieme per determinare quando applicare i criteri di conformità delle comunicazioni agli elementi di comunicazione. Quando si impostano più condizioni, è necessario che vengano soddisfatte tutte le condizioni per l'applicazione del criterio, a meno che non venga immessa un'eccezione. Ad esempio, è necessario un criterio che si applica se un messaggio contiene la parola "commercio" ed è superiore a 2 MB. Tuttavia, se il messaggio contiene anche le parole "Approvato da Contoso financial", il criterio non deve essere applicato. In questo esempio le tre condizioni vengono definite come segue:
  
- **Il messaggio contiene una di queste parole**, con la parola chiave "trade"
- **La dimensione del messaggio è maggiore di**, con il valore 2 MB
- **Il messaggio non contiene nessuna di queste parole,** con le parole chiave "Approvato dal team finanziario di Contoso"

### <a name="review-percentage"></a>Percentuale revisione

Se si desidera ridurre la quantità di contenuto da esaminare, è possibile specificare una percentuale di tutte le comunicazioni disciplinate da un criterio di conformità delle comunicazioni. Un campione casuale di contenuto in tempo reale viene selezionato dalla percentuale totale di contenuto che soddisfa le condizioni dei criteri scelti. Se si desidera che i revisori rivedeno tutti gli elementi, è possibile configurare **il 100%** in un criterio di conformità delle comunicazioni.

## <a name="privacy"></a>Privacy

Proteggere la privacy degli utenti che hanno corrispondenze ai criteri è importante e può contribuire a promuovere l'obiettività nell'analisi e nell'analisi dei dati per gli avvisi di conformità alle comunicazioni. Questa impostazione si applica solo ai nomi utente visualizzati nella soluzione di conformità delle comunicazioni. Non influisce sulla modalità di visualizzazione dei nomi in altre soluzioni di conformità o nell'interfaccia di amministrazione.

Per gli utenti con una corrispondenza di conformità alle comunicazioni, è possibile scegliere una delle impostazioni seguenti in **Impostazioni di conformità della comunicazione:**

- **Show anonymized versions of usernames**: I nomi utente sono anonimi per impedire agli utenti nel gruppo di ruoli *Communication Compliance Analyst* di vedere chi è associato agli avvisi dei criteri. Gli utenti nel *gruppo di ruoli* Communication Compliance Investigator visualizzano sempre i nomi utente, non le versioni anonime. Ad esempio, un utente "Grace Taylor" verrebbe visualizzato con uno pseudonimo casuale, ad esempio "AnonIS8-988" in tutte le aree dell'esperienza di conformità delle comunicazioni. Quando si sceglie questa impostazione, vengono resi anonimi tutti gli utenti con corrispondenze con i criteri correnti e precedenti e si applica a tutti i criteri. Le informazioni del profilo utente nei dettagli dell'avviso di conformità delle comunicazioni non saranno disponibili quando si sceglie questa opzione. Tuttavia, i nomi utente vengono visualizzati quando si aggiungono nuovi utenti ai criteri esistenti o quando si assegnano utenti a nuovi criteri. Se si sceglie di disattivare questa impostazione, i nomi utente vengono visualizzati per tutti gli utenti con corrispondenze di criteri correnti o precedenti.
- **Non mostrare versioni anonime dei** nomi utente: i nomi utente vengono visualizzati per tutte le corrispondenze dei criteri correnti e precedenti per gli avvisi di conformità alle comunicazioni. Le informazioni del profilo utente (nome, titolo, alias e organizzazione o reparto) vengono visualizzate per l'utente per tutti gli avvisi di conformità alle comunicazioni.

## <a name="notice-templates"></a>Modelli di avviso

È possibile creare modelli di avviso se si desidera inviare agli utenti un avviso di promemoria tramite posta elettronica per le corrispondenze dei criteri nell'ambito del processo di risoluzione dei problemi. Le notifiche possono essere inviate solo all'indirizzo di posta elettronica dell'utente associato alla corrispondenza dei criteri che ha generato l'avviso specifico per la correzione. Quando si seleziona un modello di avviso da applicare a una violazione dei criteri come parte del flusso di lavoro di correzione, è possibile scegliere di accettare i valori dei campi definiti nel modello o sovrascrivere i campi in base alle esigenze.

I modelli di avviso sono modelli di messaggio di posta elettronica personalizzati in cui è possibile definire i campi dei messaggi seguenti nell'area **Impostazioni di conformità della** comunicazione:

|**Campo**|**Obbligatorio**| **Dettagli** |
|:-----|:-----|:-----|
|**Nome del modello** | Sì | Il nome descrittivo del modello di avviso che verrà selezionato nel flusso di lavoro di notifica durante la correzione supporta i caratteri di testo. |
| **Indirizzo del mittente** | Sì | L'indirizzo di uno o più utenti o gruppi che inviano il messaggio all'utente con una corrispondenza di criteri, selezionata da Active Directory per la sottoscrizione. |
| **Indirizzi CC e Ccn** | No | Utenti o gruppi facoltativi da notificare della corrispondenza dei criteri, selezionati in Active Directory per l'abbonamento. |
| **Oggetto** | Sì | Le informazioni visualizzate nella riga dell'oggetto del messaggio supportano i caratteri di testo. |
| **Corpo del messaggio** | Sì | Le informazioni visualizzate nel corpo del messaggio supportano valori di testo o HTML. |

### <a name="html-for-notices"></a>HTML per gli avvisi

Se si desidera creare più di un semplice messaggio di posta elettronica basato su testo per le notifiche, è possibile creare un messaggio più dettagliato utilizzando HTML nel campo corpo del messaggio di un modello di avviso. Nell'esempio seguente viene fornito il formato del corpo del messaggio per un modello di notifica di posta elettronica basato su HTML di base:

```HTML
<!DOCTYPE html>
<html>
    <body>
        <h2>Action Required: Contoso Employee Code of Conduct Policy Training</h2>
        <p>A recent message you've sent has generated a policy alert for the Contoso Employee <a href='https://www.contoso.com'>Code of Conduct Policy</a>.</p>
        <p>You are required to attend the Contoso Employee Code of Conduct <a href='https://www.contoso.com'>training</a> within the next 14 days. Please contact <a href='mailto:hr@contoso.com'>Human Resources</a> with any questions about this training request.</p>
        <p>Thank you,</p>
        <p><em>Human Resources</em></p>
    </body>
</html>
```

>[!NOTE]
>L'implementazione dell'attributo href HTML nei modelli di notifica di conformità delle comunicazioni attualmente supporta solo le virgolette singole anziché le virgolette doppie per i riferimenti URL.

## <a name="filters"></a>Filtri

I filtri di conformità delle comunicazioni consentono di filtrare e ordinare i messaggi di avviso per azioni di analisi e correzione più rapide. Il filtro è disponibile nelle **schede In** sospeso **e Risolto** per ogni criterio. Per salvare un filtro o un set di filtri come query di filtro salvata, è necessario configurare uno o più valori come selezioni di filtro. Nella tabella seguente sono riportati i dettagli del filtro:

|**Filter**|**Dettagli**|
|:-----|:-----|
| **Data** | Data in cui il messaggio è stato inviato o ricevuto da un utente dell'organizzazione. Per filtrare un singolo giorno, selezionare un intervallo di date che inizia con il giorno per cui si desidera ottenere i risultati e terminare con il giorno successivo. Se ad esempio si desidera filtrare i risultati per il 20/09/2020, è necessario scegliere un intervallo di date di filtro 20/09/2020-21/9/2020.|
| **Classe File** | Classe del messaggio in base al tipo di messaggio, *messaggio* o *allegato.* |
| **Ha allegato** | Presenza dell'allegato nel messaggio. |
| **Classe Item** | Origine del messaggio in base al tipo di messaggio, alla posta elettronica, alla chat di Microsoft Team, a Bloomberg e così via. Per ulteriori informazioni sui tipi di elemento comuni e sulle classi messaggio, vedere [Tipi di elemento e classi messaggio](/office/vba/outlook/concepts/forms/item-types-and-message-classes). |
| **Domini destinatari** | Dominio a cui è stato inviato il messaggio. Questo dominio è in genere il dominio di sottoscrizione di Microsoft 365 per impostazione predefinita. |
| **Destinatario** | Utente a cui è stato inviato il messaggio. |
| **Mittente** | Persona che ha inviato il messaggio. |
| **Dominio del mittente** | Dominio che ha inviato il messaggio. |
| **Dimensioni** | Dimensioni del messaggio in KB. |
| **Oggetto/Titolo** | Oggetto del messaggio o titolo della chat. |
| **Tag** | Tag assegnati a un messaggio, *questionable,* *compliant* o *non conforme.* |
| **Riassegnata a** | Nome utente della persona inclusa nell'ambito di un'azione di escalation del messaggio. |
| **Classificatori** | Nome dei classificatori predefiniti e personalizzati applicabili al messaggio. Alcuni esempi includono *linguaggio offensivo,* *molestie* mirate, *volgarità,* *minacce* e altro ancora.

## <a name="alert-policies"></a>Criteri di avviso

Dopo aver configurato un criterio, viene creato automaticamente un criterio di avviso corrispondente e vengono generati avvisi per i messaggi che soddisfano le condizioni definite nel criterio. Per impostazione predefinita, a tutti i criteri corrispondenti ai trigger di avviso viene assegnato un livello di gravità medio nel criterio di avviso associato. Gli avvisi vengono generati per un criterio di conformità delle comunicazioni una volta raggiunto il livello di soglia del trigger di aggregazione nel criterio di avviso associato.

Per i criteri di conformità delle comunicazioni, i seguenti valori dei criteri di avviso sono configurati per impostazione predefinita:

|**Trigger dei criteri di avviso**|**Valore predefinito**|
|:-----|:-----|
| Aggregazione | Aggregazione semplice |
| Soglia | 4 attività |
| Finestra | 60 minuti |

>[!Note]
>Le impostazioni di attivazione della soglia dei criteri di avviso per le attività supportano un valore minimo pari o superiore a 3 per i criteri di conformità delle comunicazioni.

È possibile modificare le impostazioni predefinite per i trigger su numero di attività, periodo  per le attività e per utenti specifici nei criteri di avviso nella pagina Criteri di avviso nel Centro sicurezza & conformità.

### <a name="change-the-severity-level-for-an-alert-policy"></a>Modificare il livello di gravità per un criterio di avviso

Se si desidera modificare il livello di gravità assegnato in un criterio di avviso per uno specifico criterio di conformità delle comunicazioni, completare la procedura seguente:

1. Accedere usando [https://compliance.microsoft.com](https://compliance.microsoft.com) le credenziali per un account amministratore nell'organizzazione di Microsoft 365.

2. Nel Centro conformità Microsoft 365 passare a **Criteri**.

3. Selezionare **Avviso di Office 365** nella  pagina Criteri per aprire la pagina Criteri avvisi nel Centro sicurezza & e conformità di Office **365.** 

4. Seleziona la casella di controllo per i criteri di conformità delle comunicazioni che vuoi aggiornare, quindi seleziona **Modifica criterio.**

5. Nella scheda **Descrizione** selezionare l'elenco a discesa **Gravità** per configurare il livello di avviso del criterio.

6. Selezionare **Salva** per applicare il nuovo livello di gravità al criterio.

7. Selezionare **Chiudi per** uscire dalla pagina dei dettagli dei criteri di avviso.

## <a name="power-automate-flows"></a>Power Automate flows

[Microsoft Power Automate è](/power-automate/getting-started) un servizio di flusso di lavoro che automatizza le azioni tra applicazioni e servizi. Utilizzando i flussi dei modelli o creati manualmente, è possibile automatizzare le attività comuni associate a tali applicazioni e servizi. Quando si abilita Power Automate flows per la conformità delle comunicazioni, è possibile automatizzare attività importanti per avvisi e utenti. È possibile configurare i flussi di Power Automate per inviare notifiche ai responsabili quando gli utenti hanno avvisi di conformità alle comunicazioni e altre applicazioni.

I clienti con abbonamenti a Microsoft 365 che includono la conformità alle comunicazioni non necessitano di licenze di Power Automate aggiuntive per usare il modello power automate di conformità alle comunicazioni predefinito consigliato. Il modello predefinito può essere personalizzato per supportare l'organizzazione e coprire gli scenari di conformità delle comunicazioni di base. Se si sceglie di usare le funzionalità di Power Automate premium in questi modelli, creare un modello personalizzato utilizzando il connettore di conformità di Microsoft 365 o utilizzare i modelli power automate per altre aree di conformità in Microsoft 365, potrebbero essere necessarie licenze di Power Automate aggiuntive.

>[!IMPORTANT]
>Si ricevono richieste di convalida delle licenze aggiuntive durante il test dei flussi di Power Automate? L'organizzazione potrebbe non aver ancora ricevuto gli aggiornamenti del servizio per questa funzionalità di anteprima. Gli aggiornamenti vengono distribuiti e tutte le organizzazioni con abbonamenti a Microsoft 365 che includono la conformità alle comunicazioni devono disporre del supporto delle licenze per i flussi creati dai modelli power automate consigliati entro il 30 ottobre 2020.

![Conformità delle comunicazioni Power Automate](../media/communication-compliance-power-automate.png)

Il modello Power Automate seguente viene fornito ai clienti per supportare l'automazione dei processi per gli avvisi di conformità alle comunicazioni:

- **Notifica al responsabile quando un utente ha un avviso** di conformità della comunicazione: alcune organizzazioni potrebbero dover avere una notifica di gestione immediata quando un utente ha un avviso di conformità della comunicazione. Quando questo flusso viene configurato e selezionato, al responsabile del caso all'utente viene inviato un messaggio di posta elettronica con le informazioni seguenti su tutti gli avvisi:
    - Criteri applicabili per l'avviso
    - Data/ora dell'avviso
    - Livello di gravità dell'avviso

### <a name="create-a-power-automate-flow"></a>Creare un flusso power automate

Per creare un flusso di Power Automate da un  modello predefinito consigliato, userai l'opzione Gestisci flussi automatici di alimentazione del controllo **Automatizza** quando lavori direttamente in un avviso. Per creare un flusso di Power Automate con **Manage Power Automate flows,** è necessario essere membri di almeno un gruppo di ruoli di conformità delle comunicazioni.

Completare la procedura seguente per creare un flusso power automate da un modello predefinito:

1. Nel Centro conformità Microsoft 365 passare a **Criteri** di conformità delle comunicazioni e selezionare il criterio  >   con l'avviso che si desidera esaminare.
2. Dal criterio, selezionare la scheda **In** sospeso e selezionare un avviso in sospeso.
3. Seleziona **Power Automate dal** menu dell'azione di avviso.
4. Nella pagina **Power Automate** selezionare un  modello predefinito nella sezione Modelli di conformità per le comunicazioni che potrebbero piacerti nella pagina.
5. Il flusso elenca le connessioni incorporate necessarie per il flusso e viene visualizzato se gli stati della connessione sono disponibili. Se necessario, aggiornare tutte le connessioni che non vengono visualizzate come disponibili. Selezionare **Continua.**
6. Per impostazione predefinita, i flussi consigliati sono preconfigurato con la conformità alle comunicazioni consigliata e i campi dati dei servizi di Microsoft 365 necessari per completare l'attività assegnata per il flusso. Se necessario, personalizzare i componenti del flusso utilizzando il **controllo Mostra** opzioni avanzate e configurando le proprietà disponibili per il componente di flusso.
7. Se necessario, aggiungere ulteriori passaggi al flusso selezionando il **pulsante Nuovo** passaggio. Nella maggior parte dei casi, questa modifica non deve essere necessaria per i modelli predefiniti consigliati.
8. Selezionare **Salva bozza** per salvare il flusso per ulteriori configurazioni in un secondo momento oppure selezionare **Salva** per completare la configurazione per il flusso.
9. Selezionare **Chiudi** per tornare alla pagina del flusso Power Automate. Il nuovo modello verrà elencato  come flusso nella scheda Flussi personali ed è automaticamente disponibile dal controllo Power Automate per l'utente che ha creato il flusso quando utilizza gli avvisi di conformità delle comunicazioni.

### <a name="share-a-power-automate-flow"></a>Condividere un flusso power automate

Per impostazione predefinita, i flussi di Power Automate creati da un utente sono disponibili solo per tale utente. Per consentire ad altri utenti di conformità delle comunicazioni di accedere e usare un flusso, il flusso deve essere condiviso dall'autore del flusso. Per condividere un flusso, userai il controllo **Power Automate** quando lavori direttamente in un avviso.

Per condividere un flusso power automate, è necessario essere membri di almeno un gruppo di ruoli di conformità delle comunicazioni.
Completare la procedura seguente per condividere un flusso power automate:

1. Nel Centro conformità Microsoft 365 passare a **Criteri** di conformità delle comunicazioni e selezionare il criterio  >   con l'avviso che si desidera esaminare.
2. Dal criterio, selezionare la scheda **In** sospeso e selezionare un avviso in sospeso.
3. Seleziona **Power Automate dal** menu dell'azione di avviso.
4. Nella pagina **Flussi automatici di alimentazione** selezionare la scheda Flussi **del** team o **Flussi del** team.
5. Seleziona il flusso da condividere, quindi scegli **Condividi** dal menu delle opzioni del flusso.
6. Nella pagina di condivisione del flusso immettere il nome dell'utente o del gruppo che si desidera aggiungere come proprietario del flusso.
7. Nella finestra **di dialogo Connessione** utilizzata selezionare **OK** per confermare che l'utente o il gruppo aggiunto avrà accesso completo al flusso.

### <a name="edit-a-power-automate-flow"></a>Modificare un flusso di Power Automate

Se devi modificare un flusso, userai il controllo **Power Automate** quando lavori direttamente in un avviso. Per modificare un flusso di Power Automate, è necessario essere membri di almeno un gruppo di ruoli di conformità delle comunicazioni.

Completare la procedura seguente per modificare un flusso di Power Automate:

1. Nel Centro conformità Microsoft 365 passare a **Criteri** di conformità delle comunicazioni e selezionare il criterio  >   con l'avviso che si desidera esaminare.
2. Dal criterio, selezionare la scheda **In** sospeso e selezionare un avviso in sospeso.
3. Seleziona **Power Automate dal** menu dell'azione di avviso.
4. Nella pagina **Flussi di Power Automate** selezionare il flusso da modificare. Seleziona **Modifica** dal menu controllo di flusso.
5. Selezionare i **puntini di sospensione** Impostazioni per modificare l'impostazione di un componente di flusso o i puntini di  >   **sospensione**  >  **Elimina** per eliminare un componente di flusso.
6. Selezionare **Salva** e quindi **Chiudi per** completare la modifica del flusso.

### <a name="delete-a-power-automate-flow"></a>Eliminare un flusso power automate

Se devi eliminare un flusso, userai il controllo **Power Automate** quando lavori direttamente in un avviso. Per eliminare un flusso di Power Automate, è necessario essere membri di almeno un gruppo di ruoli di conformità delle comunicazioni.

Completare la procedura seguente per eliminare un flusso di Power Automate:

1. Nel Centro conformità Microsoft 365 passare a **Criteri** di conformità delle comunicazioni e selezionare il criterio  >   con l'avviso che si desidera esaminare.
2. Dal criterio, selezionare la scheda **In** sospeso e selezionare un avviso in sospeso.
3. Seleziona **Power Automate dal** menu dell'azione di avviso.
4. Nella pagina **Flussi automatici di alimentazione** selezionare il flusso da eliminare. Seleziona **Elimina** dal menu controllo di flusso.
5. Nella finestra di dialogo di conferma dell'eliminazione, selezionare **Elimina** per rimuovere il flusso oppure **scegliere Annulla** per uscire dall'azione di eliminazione.

## <a name="reports"></a>Report

Il nuovo dashboard **Report** è la posizione centrale per la visualizzazione di tutti i report di conformità delle comunicazioni. I widget di report offrono una rapida visualizzazione delle informazioni dettagliate più comunemente necessarie per una valutazione complessiva dello stato delle attività di conformità delle comunicazioni. Le informazioni contenute nei widget di report non sono esportabili. I report dettagliati forniscono informazioni approfondite relative a specifiche aree di conformità delle comunicazioni e offrono la possibilità di filtrare, raggruppare, ordinare ed esportare informazioni durante la revisione.

![Dashboard dei report di conformità delle comunicazioni](../media/communication-compliance-reports-dashboard.png)

Il **dashboard Report** contiene i seguenti widget di report e collegamenti dettagliati ai report:

- **Widget Corrispondenze criteri** recenti: visualizza il numero di corrispondenze in base al criterio attivo nel tempo.
- **Elementi risolti dal** widget criteri: visualizza il numero di avvisi di corrispondenza dei criteri risolti dal criterio nel tempo.
- **Utenti con la maggior parte dei** widget di corrispondenza dei criteri: visualizza gli utenti (o nomi utente anonimi) e il numero di corrispondenze dei criteri per un determinato periodo.
- **Widget Criteri con la maggior** parte delle corrispondenze: visualizza i criteri e il numero di corrispondenze per un determinato periodo, classificati dal più alto al più basso per le corrispondenze.
- Escalation per widget **criteri:** visualizza il numero di escalation per criterio in un determinato periodo di tempo.
- **Report dettagliato sulle impostazioni** dei criteri e sullo stato: fornisce un'analisi dettagliata della configurazione e delle impostazioni dei criteri, nonché dello stato generale di ogni criterio (corrispondenze e azioni) nei messaggi. Include informazioni sui criteri e come i criteri sono associati a utenti e gruppi, posizioni, percentuali di revisione, revisori, stato e data dell'ultima modifica del criterio. Utilizzare *l'opzione* Esporta per creare un file CSV contenente i dettagli del report.
- **Elementi e azioni per report dettagliato** dei criteri: esaminare ed esportare gli elementi corrispondenti e le azioni di correzione per ogni criterio. Include le informazioni sui criteri e la modalità con cui i criteri sono associati a:

    - Elementi corrispondenti
    - Elementi inoltrati
    - Elementi risolti
    - Contrassegnato come conforme
    - Contrassegnato come non conforme
    - Contrassegnato come discutibile
    - Elementi in sospeso
    - Notifica dell'utente
    - Caso creato
    
    Utilizzare *l'opzione* Esporta per creare un file CSV contenente i dettagli del report.
- **Report dettagliato su elementi** e azioni per posizione: esaminare ed esportare gli elementi corrispondenti e le azioni di correzione per ogni posizione di Microsoft 365. Include informazioni sul modo in cui le piattaforme del carico di lavoro sono associate a:

    - Elementi corrispondenti
    - Elementi inoltrati
    - Elementi risolti
    - Contrassegnato come conforme
    - Contrassegnato come non conforme
    - Contrassegnato come discutibile
    - Elementi in sospeso
    - Notifica dell'utente
    - Caso creato

    Utilizzare *l'opzione* Esporta per creare un file CSV contenente i dettagli del report.
- **Report dettagliato attività** per utente: esaminare ed esportare gli elementi corrispondenti e le azioni di correzione per utente. Include informazioni sul modo in cui gli utenti sono associati a:

    - Elementi corrispondenti
    - Elementi inoltrati
    - Elementi risolti
    - Contrassegnato come conforme
    - Contrassegnato come non conforme
    - Contrassegnato come discutibile
    - Elementi in sospeso
    - Notifica dell'utente
    - Caso creato

    Utilizzare *l'opzione* Esporta per creare un file CSV contenente i dettagli del report.

## <a name="audit"></a>Audit

In alcuni casi, è necessario fornire informazioni ai revisori normativi o di conformità per dimostrare la supervisione delle attività e delle comunicazioni degli utenti. Queste informazioni possono essere un riepilogo di tutte le attività associate a un criterio organizzativo definito o ogni volta che viene modificato un criterio di conformità della comunicazione. I criteri di conformità delle comunicazioni dispongono di audit trail predefiniti per una completa preparazione per i controlli interni o esterni. Le cronologie di controllo dettagliate di ogni azione di creazione, modifica ed eliminazione vengono acquisite dai criteri di comunicazione per fornire una prova delle procedure di supervisione.

>[!Important]
>Il controllo deve essere abilitato per l'organizzazione prima di registrare gli eventi di conformità delle comunicazioni. Per abilitare il controllo, vedere [Enable the audit log](communication-compliance-configure.md#step-2-required-enable-the-audit-log).

Per visualizzare le attività di aggiornamento dei criteri di conformità delle comunicazioni, selezionare il **controllo** Esporta aggiornamenti dei criteri nella pagina principale per qualsiasi criterio. Per esportare le attività  di aggiornamento, è necessario disporre dei ruoli *Amministratore* globale o Amministratore conformità comunicazioni. Questa azione genera un file di controllo in formato CSV contenente le informazioni seguenti:

|**Campo**|**Dettagli**|
|:-----|:-----|
| **CreationDate** | Data in cui l'attività di aggiornamento è stata eseguita in un criterio. |
| **UserIds** | Utente che ha eseguito l'attività di aggiornamento in un criterio. |
| **Operazioni** | Operazioni di aggiornamento eseguite sul criterio. |
| **AuditData** | Questo campo è l'origine dati principale per tutte le attività di aggiornamento dei criteri. Tutte le attività di aggiornamento vengono registrate e separate da delimitatori di virgole. |

Per visualizzare le attività di revisione  della conformità delle comunicazioni per un criterio, selezionare il controllo Esporta attività di revisione nella pagina **Panoramica** per un criterio specifico. Per esportare le attività di *revisione,* è necessario disporre dei ruoli *Amministratore* globale o Amministratore conformità comunicazioni. Questa azione genera un file di controllo in formato CSV contenente le informazioni seguenti:

|**Campo**|**Dettagli**|
|:-----|:-----|
| **CreationDate** | Data in cui l'attività di revisione è stata eseguita in un criterio. |
| **UserIds** | Utente che ha eseguito l'attività di revisione in un criterio. |
| **Operazioni** | Le operazioni di revisione eseguite sul criterio. |
| **AuditData** | Questo campo è l'origine dati principale per tutte le attività di revisione dei criteri. Tutte le attività di revisione vengono registrate e separate da delimitatori di virgole. |

È inoltre possibile visualizzare le attività di controllo nel log di controllo unificato o con il cmdlet [Di PowerShell Search-UnifiedAuditLog.](/powershell/module/exchange/search-unifiedauditlog) Per ulteriori informazioni sui criteri di conservazione dei log di controllo, vedere [Manage audit log retention policies](audit-log-retention-policies.md).

Ad esempio, nell'esempio seguente vengono restituite le attività per tutte le attività di revisione (criteri e regole):

```PowerShell
Search-UnifiedAuditLog -StartDate $startDate -EndDate $endDate -RecordType AeD -Operations SupervisoryReviewTag
```

In questo esempio vengono restituite le attività di aggiornamento per i criteri di conformità delle comunicazioni:

```PowerShell
Search-UnifiedAuditLog -StartDate $startDate -EndDate $endDate -RecordType Discovery -Operations SupervisionPolicyCreated,SupervisionPolicyUpdated,SupervisionPolicyDeleted
```

In questo esempio vengono restituite le attività che corrispondono ai criteri di conformità delle comunicazioni correnti:

```PowerShell
Search-UnifiedAuditLog -StartDate $startDate -EndDate $endDate -Operations SupervisionRuleMatch 
```

Le corrispondenze dei criteri di conformità delle comunicazioni vengono archiviate in una cassetta postale di supervisione per ogni criterio. In alcuni casi, potrebbe essere necessario controllare le dimensioni della cassetta postale di supervisione per un criterio per assicurarsi che non si sta avvicinando al limite corrente di 50 GB. Se viene raggiunto il limite della cassetta postale, le corrispondenze dei criteri non vengono acquisite e sarà necessario creare un nuovo criterio (con le stesse impostazioni) per continuare a acquisire corrispondenze per le stesse attività.

Per verificare le dimensioni di una cassetta postale di supervisione per un criterio, completare le operazioni seguenti:

1. Utilizzare il cmdlet [Connect-ExchangeOnline](/powershell/module/exchange/connect-exchangeonline) nel modulo PowerShell V2 di Exchange Online per connettersi a PowerShell di Exchange Online utilizzando l'autenticazione moderna.
2. Eseguire quanto segue in PowerShell:

    ```PowerShell
    ForEach ($p in Get-SupervisoryReviewPolicyV2 | Sort-Object Name) 
    {
       "<Name of your communication compliance policy>: " + $p.Name
       Get-MailboxStatistics $p.ReviewMailbox | ft ItemCount,TotalItemSize
    }
    ```

## <a name="transitioning-from-supervision-in-office-365"></a>Transizione dalla supervisione in Office 365

Le organizzazioni che usano i criteri di supervisione in Office 365 devono pianificare immediatamente la transizione ai criteri di conformità delle comunicazioni in Microsoft 365 e devono comprendere questi punti importanti:

- La soluzione di supervisione in Office 365 è stata completamente sostituita dalla soluzione di conformità delle comunicazioni in Microsoft 365. È consigliabile creare nuovi criteri nella conformità delle comunicazioni che hanno le stesse impostazioni dei criteri di supervisione esistenti per usare i nuovi miglioramenti di analisi e correzione.
- I messaggi salvati in supervisione nelle corrispondenze dei criteri di Office 365 non possono essere spostati o condivisi nella conformità delle comunicazioni in Microsoft 365.
- Per le organizzazioni con entrambe le soluzioni utilizzate affiancate durante il processo di transizione, i criteri utilizzati in ogni soluzione devono avere nomi di criteri univoci. I gruppi e i dizionari parole chiave personalizzati possono essere condivisi tra le soluzioni durante un periodo di transizione.

Per informazioni sul ritiro per la supervisione in Office 365, vedere la roadmap di [Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap) per informazioni dettagliate.

## <a name="ready-to-get-started"></a>Pronti per iniziare?

Per configurare la conformità delle comunicazioni per l'organizzazione di Microsoft 365, vedere [Configure communication compliance for your Microsoft 365 organization](communication-compliance-configure.md).
