---
title: Informazioni di riferimento sulle caratteristiche di conformità comunicazione
description: Riferimento alla funzionalità per la conformità delle comunicazioni in Microsoft 365. Informazioni dettagliate e specifiche per ogni componente di funzionalità.
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
ms.openlocfilehash: 017946c08bb1c44f31bbcb87b3ce46571ab8b480
ms.sourcegitcommit: a5ed189fa789975f8c3ed39db1d52f2ef7d671aa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2020
ms.locfileid: "45101607"
---
# <a name="communication-compliance-feature-reference"></a>Informazioni di riferimento sulle caratteristiche di conformità comunicazione

## <a name="policies"></a>Criteri

>[!Important]
>L'utilizzo di PowerShell per la creazione e la gestione di criteri di conformità della comunicazione non è supportato. Per creare e gestire questi criteri, è necessario utilizzare i controlli di gestione dei criteri nella [soluzione Microsoft 365 Communication Compliance](https://compliance.microsoft.com/supervisoryreview).

È possibile creare criteri di conformità della comunicazione per le organizzazioni Microsoft 365 nel centro conformità di Microsoft 365. I criteri di conformità della comunicazione definiscono le comunicazioni e gli utenti soggetti a revisione nell'organizzazione, definiscono le condizioni personalizzate che devono soddisfare le comunicazioni e specificano chi deve eseguire le revisioni. Gli utenti inclusi nel gruppo di ruoli **amministratore revisione di supervisione** possono impostare i criteri e tutti coloro a cui è assegnato questo ruolo possono accedere alla pagina **conformità comunicazione** nel centro conformità di Microsoft 365. Se necessario, è possibile esportare la cronologia delle modifiche apportate a un criterio a un file con estensione CSV che include anche lo stato degli avvisi in sospeso, degli elementi escalation e degli elementi risolti. I criteri non possono essere rinominati e possono essere eliminati quando non sono più necessari.

>[!NOTE]
>I criteri di supervisione creati nel centro sicurezza & Compliance per le sottoscrizioni di Office 365 non possono eseguire la migrazione a Microsoft 365. Se si esegue la migrazione da un abbonamento a Office 365 a un abbonamento a Microsoft 365, sarà necessario creare nuovi criteri di conformità per la comunicazione per sostituire il criterio di supervisione esistente.

## <a name="policy-templates"></a>Modelli dei criteri

I modelli di criteri sono impostazioni predefinite che è possibile utilizzare per creare rapidamente criteri per risolvere scenari di conformità comuni. Ognuno di questi modelli presenta differenze nelle condizioni e nell'ambito e tutti i modelli utilizzano gli stessi tipi di segnali di analisi. È possibile scegliere tra i modelli di criteri seguenti:

|**Area**|**Modello di criteri**|**Dettagli**|
|:-----|:-----|:-----|
| **Lingua offensiva e anti-molestia** | Monitorare le comunicazioni per la lingua offensiva | -Locations: Exchange Online, Microsoft teams, Yammer, Skype for business <br> -Direction: in ingresso, in uscita, interno <br> -Percentuale di verifica: 100% <br> -Conditions: classificatore di lingua offensivo |
| **Informazioni sensibili** | Monitorare le comunicazioni per informazioni riservate | -Locations: Exchange Online, Microsoft teams, Yammer, Skype for business <br> -Direction: in ingresso, in uscita, interno <br> -Percentuale di verifica: 10% <br> -Conditions: informazioni riservate, modelli di contenuto esterno alla casella e tipi, opzione dizionario personalizzato, allegati superiori a 1 MB |
| **Conformità alle normative** | Monitorare le comunicazioni per informazioni relative alla conformità alle normative finanziarie | -Locations: Exchange Online, Microsoft teams, Yammer, Skype for business <br> -Direction: in ingresso, in uscita <br> -Percentuale di verifica: 10% <br> -Conditions: opzione dizionario personalizzato, allegati di dimensioni superiori a 1 MB |

## <a name="supervised-users"></a>Utenti controllati

Prima di iniziare a utilizzare la conformità alla comunicazione, è necessario determinare chi ha bisogno delle proprie comunicazioni. Nei criteri, gli indirizzi di posta elettronica degli utenti identificano gli utenti o i gruppi di persone da sorvegliare. Alcuni esempi di questi gruppi sono i gruppi di Microsoft 365, le liste di distribuzione basate su Exchange, le community di Yammer e i canali Microsoft teams. È inoltre possibile escludere utenti o gruppi specifici dall'analisi con un gruppo di esclusione specifico o un elenco di gruppi.

>[!IMPORTANT]
>Gli utenti interessati dai criteri di conformità della comunicazione devono avere una licenza di conformità Microsoft 365 E5, una licenza di Office 365 Enterprise E3 con il componente aggiuntivo per la conformità avanzato oppure essere inclusi in un abbonamento a Office 365 Enterprise E5. Se non si dispone di un piano Enterprise E5 esistente e si vuole provare la conformità alla comunicazione, è possibile [iscriversi per una versione di valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).

## <a name="reviewers"></a>Revisori

Quando si crea un criterio di conformità della comunicazione, è necessario determinare chi esamina i messaggi degli utenti controllati. Nei criteri, gli indirizzi di posta elettronica degli utenti identificano gli utenti o i gruppi di persone per esaminare le comunicazioni sorvegliate. Tutti i revisori devono disporre di cassette postali ospitate in Exchange Online e devono essere assegnati ai ruoli Gestione e **Revisione** dei **casi** . Quando i revisori vengono aggiunti a un criterio, ricevono automaticamente un messaggio di posta elettronica che informa gli utenti dell'assegnazione ai criteri e fornisce collegamenti alle informazioni sul processo di revisione.

## <a name="groups-for-supervised-users-and-reviewers"></a>Gruppi per gli utenti e i revisori controllati

Per semplificare l'installazione, creare gruppi per gli utenti che hanno bisogno di una revisione delle comunicazioni e di gruppi per gli utenti che esaminano tali comunicazioni. Se si utilizzano i gruppi, potrebbero essere necessari diversi. Ad esempio, se si desidera eseguire l'analisi delle comunicazioni tra due gruppi distinti di persone oppure se si desidera specificare un gruppo non supervisionato.

Quando si assegna un gruppo di distribuzione nel criterio, il criterio monitora tutti i messaggi di posta elettronica di ogni utente del gruppo di distribuzione. Quando si assegna un gruppo di Microsoft 365 nel criterio, il criterio monitora tutti i messaggi di posta elettronica inviati a quel gruppo, non i singoli messaggi di posta elettronica ricevuti da ogni membro del gruppo.

L'aggiunta di gruppi e liste di distribuzione ai criteri di conformità della comunicazione fa parte delle condizioni generali e del set di regole, quindi il numero massimo di gruppi e di liste di distribuzione supportate da un criterio varia a seconda del numero di condizioni aggiunte al criterio. Ogni criterio deve supportare circa 20 gruppi o liste di distribuzione, a seconda del numero di condizioni aggiuntive presenti nel criterio.

## <a name="supported-communication-types"></a>Tipi di comunicazione supportati

Con i criteri di conformità della comunicazione, è possibile scegliere di analizzare i messaggi in una o più delle seguenti piattaforme di comunicazione come gruppo o come origini autonome. Le comunicazioni acquisite su queste piattaforme vengono conservate per sette anni per ogni criterio per impostazione predefinita, anche se gli utenti lasciano l'organizzazione e le relative cassette postali vengono eliminate.

- **Microsoft teams**: è possibile analizzare le comunicazioni di chat sia nei canali di Microsoft Team pubblici che in quelli privati e nelle chat individuali. Quando gli utenti vengono assegnati a un criterio di conformità della comunicazione con la copertura Microsoft teams selezionata, le comunicazioni chat per gli utenti vengono monitorate automaticamente in tutti i team di Microsoft in cui gli utenti sono membri. La copertura Microsoft teams viene automaticamente inclusa per i modelli di criteri predefiniti ed è selezionata per impostazione predefinita nel modello di criteri personalizzato. Chat teams la corrispondenza delle condizioni dei criteri di conformità della comunicazione può richiedere fino a 24 ore. Utilizzare le seguenti configurazioni di gestione dei gruppi per controllare le chat utente e le comunicazioni dei canali nei team:

    - **Per le comunicazioni di chat dei team:** Assegnare singoli utenti o assegnare un [gruppo di distribuzione](https://support.office.com/article/Distribution-groups-E8BA58A8-FAB2-4AAF-8AA1-2A304052D2DE) ai criteri di conformità della comunicazione. Questa impostazione è per le relazioni tra utenti/chat uno-a-uno o uno-a-molti.
    - **Per le comunicazioni di canale dei team:** Assegnare a ogni canale Microsoft teams o al gruppo Microsoft 365 che si desidera analizzare che contenga un utente specifico per i criteri di conformità della comunicazione. Se si aggiunge lo stesso utente ad altri canali Microsoft teams o gruppi Microsoft 365, accertarsi di aggiungere questi nuovi canali e gruppi ai criteri di conformità della comunicazione.
    - **Per le comunicazioni chat di team con ambienti di posta elettronica ibridi**: la conformità alla comunicazione può monitorare i messaggi di chat per gli utenti per le organizzazioni che dispongono di una distribuzione locale di Exchange o di un provider di posta elettronica esterno che ha abilitato Microsoft teams. È necessario creare un gruppo di distribuzione per gli utenti che dispongono di cassette postali locali o esterne da monitorare. Quando si crea un criterio di conformità della comunicazione, questo gruppo di distribuzione viene assegnato come selezione di **utenti e gruppi sorvegliati** nella procedura guidata per i criteri.

    >[!IMPORTANT]
    >È necessario presentare una richiesta con il supporto tecnico Microsoft per consentire all'organizzazione di utilizzare l'interfaccia utente grafica nel centro sicurezza & conformità per cercare i dati di chat dei team per gli utenti locali. Per ulteriori informazioni, vedere [ricerca di cassette postali basate sul cloud per gli utenti locali](search-cloud-based-mailboxes-for-on-premises-users.md).

Per cercare dati di chat di Teams nelle cassette postali basate sul cloud degli utenti locali, è necessario presentare al Supporto tecnico Microsoft la richiesta di abilitare l'organizzazione all'uso dell'interfaccia utente grafica nel Centro sicurezza e conformità.

- **Posta elettronica di Exchange**: le cassette postali ospitate in Exchange Online come parte dell'abbonamento a Microsoft 365 o Office 365 sono tutte idonee per l'analisi dei messaggi. Messaggi di posta elettronica di Exchange e allegati che corrispondono alle condizioni dei criteri di conformità della comunicazione possono richiedere fino a 24 ore. I tipi di allegati supportati per la conformità alla comunicazione sono gli stessi dei [tipi di file supportati per le ispezioni del contenuto delle regole del flusso di posta di Exchange](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection).

- **Yammer**: è possibile analizzare i messaggi privati e le conversazioni pubbliche e gli allegati associati nelle community di Yammer. Quando un utente viene aggiunto al criterio di conformità della comunicazione che include Yammer come canale definito, le comunicazioni tra tutte le community di Yammer di cui l'utente è membro sono incluse nel processo di analisi. Chat e allegati di Yammer che soddisfano le condizioni dei criteri di conformità della comunicazione possono richiedere fino a 24 ore per essere elaborate. Yammer deve essere in [modalità nativa](https://docs.microsoft.com/yammer/configure-your-yammer-network/overview-native-mode) per i criteri di conformità della comunicazione per monitorare le comunicazioni e gli allegati di Yammer. In modalità nativa, tutti gli utenti di Yammer sono in Azure Active Directory (AAD), tutti i gruppi sono gruppi di Office 365 e tutti i file vengono archiviati in SharePoint Online.

- **Skype for business online**: è possibile controllare le comunicazioni di chat e gli allegati associati in Skype for business online. Chat di Skype for business online che soddisfano le condizioni dei criteri di conformità della comunicazione possono richiedere fino a 24 ore per essere elaborate. Le conversazioni di chat sorvegliate vengono provenienti da [precedenti conversazioni salvate in Skype for business online](https://support.office.com/article/Find-a-previous-Skype-for-Business-conversation-18892eba-5f18-4281-8c87-fd48bd72e6a2).  Utilizzare la configurazione di gestione dei gruppi seguente per supervisionare le comunicazioni della chat utente in Skype for business online:

    - **Per le comunicazioni di chat di Skype for business online**: assegnare singoli utenti o assegnare un [gruppo di distribuzione](https://support.office.com/article/Distribution-groups-E8BA58A8-FAB2-4AAF-8AA1-2A304052D2DE) ai criteri di conformità della comunicazione. Questa impostazione è per le relazioni tra utenti/chat uno-a-uno o uno-a-molti.

- **Origini**di terze parti: è possibile eseguire l'analisi delle comunicazioni da origini di terze parti per i dati importati nelle cassette postali nell'organizzazione Microsoft 365. I connettori supportano le risorse di terze parti seguenti:

    - [Bloomberg istantaneo](archive-instant-bloomberg-data.md)
    - [Messaggio Bloomberg](archive-bloomberg-message-data.md)
    - [Chat di ghiaccio](archive-icechat-data.md)

Prima di poter assegnare il connettore a un criterio di conformità della comunicazione, è necessario configurare un connettore di terze parti per l'organizzazione Microsoft 365. La sezione **origini di terze parti** della procedura guidata per la conformità dei criteri di comunicazione Visualizza solo i connettori di terze parti attualmente configurati.

## <a name="transitioning-from-supervision-in-office-365"></a>Transizione dalla vigilanza in Office 365

Le organizzazioni che utilizzano i criteri di supervisione in Office 365 e la pianificazione della transizione ai criteri di conformità della comunicazione in Microsoft 365 devono comprendere questi importanti punti:

- Entrambe le soluzioni possono essere utilizzate affiancate all'interno dell'organizzazione, ma i criteri utilizzati in ogni soluzione devono avere nomi di criteri univoci. I gruppi e i dizionari di parole chiave personalizzati possono essere condivisi tra le soluzioni durante un periodo di transizione.
- I messaggi salvati in supervisione nelle corrispondenze di criteri di Office 365 non possono essere spostati o condivisi nella conformità della comunicazione in Microsoft 365.
- La soluzione di supervisione in Office 365 sarà completamente sostituita dalla soluzione di conformità della comunicazione in Microsoft 365. È consigliabile creare nuovi criteri di conformità alla comunicazione con le stesse impostazioni dei criteri di supervisione esistenti per l'utilizzo dei nuovi miglioramenti di analisi e correzione. Quando si esegue la transizione alla conformità alla comunicazione in Microsoft 365, è consigliabile pianificare l'esportazione dei dati di Reporting dalla supervisione in Office 365 se sono presenti requisiti per i criteri di conservazione della conformità interni.

Per informazioni sulla pensione per la vigilanza in Office 365, vedere la Guida di [orientamento di Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap) per informazioni dettagliate.

## <a name="policy-settings"></a>Impostazioni dei criteri

### <a name="users"></a>Utenti

È possibile selezionare **tutti gli utenti** o definire utenti specifici in un criterio di conformità della comunicazione. Se si seleziona **tutti gli utenti** , il criterio viene applicato a tutti gli utenti e a tutti i gruppi a cui è incluso un utente come membro. La definizione di utenti specifici applica il criterio agli utenti definiti e a tutti i gruppi a cui gli utenti definiti sono inclusi come membri.

### <a name="direction"></a>Direction

Per impostazione predefinita, la **direzione è** la condizione viene visualizzata e non può essere rimossa. Le impostazioni relative alla direzione di comunicazione in un criterio vengono scelte singolarmente o contemporaneamente:

- In **ingresso**: è possibile scegliere in **ingresso** per esaminare le comunicazioni inviate **alle** persone scelte per la supervisione.
- In **uscita**: è possibile scegliere in **uscita** se si desidera esaminare le comunicazioni inviate **dalle** persone scelte per la supervisione.
- **Internal**: è possibile scegliere **Internal** per esaminare le comunicazioni inviate **tra** le persone identificate nel criterio.

### <a name="sensitive-information-types"></a>Tipi di informazioni sensibili

È possibile includere i tipi di informazioni riservate nell'ambito del criterio di conformità della comunicazione. I tipi di informazioni riservate sono tipi di dati predefiniti o personalizzati che consentono di identificare e proteggere i numeri di carta di credito, i numeri di conto corrente bancario, i numeri di passaporto e altro ancora. Come parte di [prevenzione della perdita di dati (DLP)](data-loss-prevention-policies.md), la configurazione delle informazioni riservate può utilizzare modelli, prossimità dei caratteri, livelli di sicurezza e persino tipi di dati personalizzati per identificare e contrassegnare il contenuto che potrebbe essere sensibile. I tipi di informazioni riservate predefinite sono:

- Finanze
- Medicale e sanitarie
- Privacy
- Tipo di informazioni personalizzato

Per ulteriori informazioni sui dettagli riservati e sui modelli inclusi nei tipi predefiniti, vedere definizioni di [entità per il tipo di informazioni riservate](sensitive-information-type-entity-definitions.md).

### <a name="custom-keyword-dictionaries"></a>Dizionari per parole chiave personalizzate

Configure custom keyword Dictionary (o lessici) per fornire una gestione semplice delle parole chiave specifiche per l'organizzazione o l'industria. I dizionari per parole chiave supportano fino a 100.000 termini per dizionario e supportano qualsiasi lingua. Se necessario, è possibile applicare più dizionari di parole chiave personalizzati a un singolo criterio oppure disporre di un solo dizionario di parole chiave per ogni criterio. Questi dizionari sono assegnati a un criterio di conformità della comunicazione e possono essere provenienti da un file, ad esempio un elenco con estensione CSV o txt, oppure da un elenco che è possibile [importare nel centro conformità](create-a-keyword-dictionary.md). Utilizzare i dizionari personalizzati quando è necessario supportare termini o lingue specifiche per l'organizzazione e i criteri.

### <a name="classifiers"></a>Classificatori

I classificatori incorporati analizzano i messaggi inviati o ricevuti su tutti i canali di comunicazione nell'organizzazione per diversi tipi di problemi di conformità. I classificatori utilizzano una combinazione di intelligenza artificiale e parole chiave per identificare la lingua nei messaggi suscettibili di violare i criteri di anti-molestia. I classificatori incorporati supportano attualmente solo le parole chiave in inglese nei messaggi.

Conformità della comunicazione i classificatori incorporati analizzano le comunicazioni per i termini e i sentimenti per i seguenti tipi di lingua:

- **Pericolo**: consente di analizzare le minacce per commettere violenze o danni fisici a una persona o a una proprietà.
- **Molestie**: analisi per comportamenti offensivi che mirano alle persone in relazione a razza, colore, religione, origine nazionale.
- **Parolacce**: esegue la ricerca di espressioni profane che imbarazzano la maggior parte delle persone.

I classificatori incorporati non forniscono un elenco esaustivo di termini in queste aree. Inoltre, gli standard linguistici e culturali cambiano continuamente e, alla luce di queste realtà, Microsoft si riserva il diritto di aggiornare i classificatori a propria discrezione. Mentre i classificatori possono assistere l'organizzazione nel monitoraggio di queste aree, i classificatori non sono destinati a fornire il solo mezzo di monitoraggio o di indirizzamento di tale lingua da parte dell'organizzazione. La propria organizzazione, non Microsoft, resta responsabile di tutte le decisioni relative all'analisi e al blocco della lingua in queste aree.

Per informazioni sui classificatori in Microsoft 365, vedere [classificatori](classifier-getting-started-with.md).

### <a name="conditional-settings"></a>Impostazioni condizionali
<a name="ConditionalSettings"> </a>

Le condizioni che scegli per il criterio si applicano alle comunicazioni sia dalla posta elettronica sia dalle fonti di terze parti nell'organizzazione (come da Instant Bloomberg o DropBox).

Nella tabella seguente vengono illustrate altre informazioni su ogni condizione.
  
|**Condizione**|**Come utilizzare questa condizione**|
|:-----|:-----|
| **Il contenuto corrisponde a uno di questi classificatori** | Applicare il criterio quando i classificatori sono inclusi o esclusi in un messaggio. Alcuni classificatori sono già definiti nel tenant e i classificatori personalizzati devono essere configurati separatamente prima di essere disponibili per questa condizione. Un solo classificatore può essere definito come una condizione in un criterio. Per ulteriori informazioni sulla configurazione dei classificatori, vedere [classificatori](classifier-getting-started-with.md). |
| **Content contiene uno qualsiasi di questi tipi di informazioni riservate** | Applicare al criterio quando i tipi di informazioni riservate sono inclusi o esclusi in un messaggio. Alcuni classificatori sono già definiti nel tenant e i classificatori personalizzati possono essere configurati separatamente o come parte del processo di assegnazione delle condizioni. Ogni tipo di informazioni riservate scelto viene applicato separatamente e solo uno di questi tipi di informazioni riservate deve richiedere il criterio da applicare al messaggio. Per ulteriori informazioni sui tipi di informazioni riservate personalizzate, vedere Custom definitive [Information types](custom-sensitive-info-types.md). |
| **Il messaggio viene ricevuto da uno di questi domini**  <br><br> **Il messaggio non viene ricevuto da nessuno di questi domini** | Applicare il criterio per includere o escludere domini o indirizzi di posta elettronica specifici nei messaggi ricevuti. Immettere ogni dominio o indirizzo di posta elettronica e separare più domini o indirizzi di posta elettronica con una virgola. Ogni dominio o indirizzo di posta elettronica immesso viene applicato separatamente, solo un dominio o un indirizzo di posta elettronica devono essere applicati per il criterio da applicare al messaggio. <br><br> Se si desidera eseguire l'analisi di tutti i messaggi di posta elettronica da un dominio specifico, ma si desidera escludere il messaggio che non è necessario esaminare (newsletter, annunci e così via), è necessario configurare un **messaggi non ricevuti da una delle seguenti condizioni dei domini** che escludono l'indirizzo di posta elettronica (ad esempio "newsletter@contoso.com"). |
| **Il messaggio viene inviato a uno di questi domini**  <br><br> **Il messaggio non viene inviato a uno di questi domini** | Applicare il criterio per includere o escludere domini o indirizzi di posta elettronica specifici nei messaggi inviati. Immettere ogni dominio o indirizzo di posta elettronica e separare più domini o indirizzi di posta elettronica con una virgola. Ogni dominio o indirizzo di posta elettronica viene applicato separatamente, per applicare il criterio al messaggio è necessario un solo dominio o un indirizzo di posta elettronica. <br><br> Se si desidera eseguire l'analisi di tutti i messaggi di posta elettronica inviati a un dominio specifico, ma si desidera escludere il messaggio inviato che non è necessario rivedere, è necessario configurare due condizioni: <br> -Un **messaggio viene inviato a una qualsiasi di queste condizioni dei domini** che definisce il dominio ("contoso.com") e <br> -Un **messaggio non viene inviato a una di queste condizioni di dominio** che escluda l'indirizzo di posta elettronica ("subscriptions@contoso.com"). |
| **Il messaggio è classificato con una qualsiasi di queste etichette**  <br><br> **Il messaggio non è classificato con nessuna di queste etichette** | Per applicare il criterio quando determinate etichette di conservazione sono incluse o escluse in un messaggio. Le etichette di conservazione devono essere configurate separatamente e le etichette configurate vengono scelte come parte di questa condizione. Ogni etichetta scelta viene applicata separatamente (è necessario applicare solo una di queste etichette per il criterio da applicare al messaggio). Per ulteriori informazioni sulla configurazione delle etichette di conservazione, vedere [Overview of retention labels](labels.md).|
| **Il messaggio contiene una o più delle seguenti parole**  <br><br> **Il messaggio contiene nessuna di queste parole** | Per applicare il criterio quando determinate parole o frasi sono incluse o escluse in un messaggio, immettere ogni parola separata con una virgola. Per le frasi di due o più parole, utilizzare le virgolette attorno alla frase. Ogni parola o frase immessa viene applicata separatamente (è necessario applicare solo una parola per il criterio da applicare al messaggio). Per ulteriori informazioni sull'immissione di parole o frasi, vedere la sezione successiva che [corrisponde a parole e frasi a messaggi di posta elettronica o allegati](communication-compliance-feature-reference.md#Matchwords).|
| **L'allegato contiene una o più delle seguenti parole**  <br><br> **L'allegato contiene nessuna di queste parole** | Per applicare il criterio quando determinate parole o frasi sono incluse o escluse in un allegato del messaggio, ad esempio un documento di Word, immettere ogni parola separata con una virgola. Per le frasi di due o più parole, utilizzare le virgolette attorno alla frase. Ogni parola o frase immessa viene applicata separatamente (è necessario applicare solo una parola per il criterio da applicare all'allegato). Per ulteriori informazioni sull'immissione di parole o frasi, vedere la sezione successiva che [corrisponde a parole e frasi a messaggi di posta elettronica o allegati](communication-compliance-feature-reference.md#Matchwords).|
| **Attachment è uno qualsiasi di questi tipi di file**  <br><br> **Attachment è nessuno di questi tipi di file** | Per controllare le comunicazioni che includono o escludono tipi specifici di allegati, immettere le estensioni di file, ad esempio. exe o. pdf. Se si desidera includere o escludere più estensioni di file, immetterle su righe separate. Per applicare il criterio, è necessario che sia presente una sola estensione per gli allegati.|
| **La dimensione del messaggio è superiore a**  <br><br> **La dimensione del messaggio non è maggiore di** | Per esaminare i messaggi in base a una determinata dimensione, utilizzare queste condizioni per specificare le dimensioni massime o minime che un messaggio può avere prima che sia soggetto a revisione. Ad esempio, se si specifica che **la dimensione del messaggio è maggiore di** \> **1,0 MB**, tutti i messaggi che sono 1,01 MB e superiori sono soggetti a revisione. Per questa condizione è possibile scegliere byte, kilobyte, megabyte o gigabyte.|
| **L'allegato è più grande di**  <br><br> **L'allegato non è più grande di** | Per esaminare i messaggi in base alle dimensioni degli allegati, specificare le dimensioni massime o minime che un allegato può avere prima che il messaggio e i suoi allegati siano soggetti a revisione. Ad esempio, se si specifica **Attachment è maggiore di** \> **2,0 MB**, tutti i messaggi con allegati 2,01 MB e oltre sono soggetti a revisione. Per questa condizione è possibile scegliere byte, kilobyte, megabyte o gigabyte.|
   
#### <a name="matching-words-and-phrases-to-emails-or-attachments"></a>Corrispondenza di parole e frasi a messaggi di posta elettronica o allegati
<a name="Matchwords"> </a>

Ogni parola immessa e separata con una virgola viene applicata separatamente (è necessario applicare solo una parola per la condizione di criteri da applicare al messaggio di posta elettronica o all'allegato). Ad esempio, usiamo la condizione, il **messaggio contiene una di queste parole**, con le parole chiave "Banker", "confidenziale" e "insider trading" separati da una virgola (banchiere, confidenziale, "insider trading"). Il criterio si applica a tutti i messaggi che includono la parola "banchiere", "confidenziale" o la frase "insider trading". Per applicare questa condizione di criteri, è necessario che si verifichi solo una di queste parole o frasi. Le parole del messaggio o dell'allegato devono corrispondere esattamente a quelle immesse.

>[!IMPORTANT]
>Quando si importa un file di dizionario personalizzato, ogni parola o frase deve essere separata con un ritorno a capo e su una riga distinta. <br> Ad esempio: <br><br>
>*banchiere* <br>
>*riservate* <br>
>*Insider Trading*

Per analizzare i messaggi di posta elettronica e gli allegati per le stesse parole chiave, creare un [criterio di prevenzione della perdita di dati](create-test-tune-dlp-policy.md) con un dizionario di parole [chiave personalizzato](create-a-keyword-dictionary.md) per i termini che si desidera analizzare nei messaggi. Questa configurazione dei criteri identifica le parole chiave definite che vengono visualizzate nel messaggio di posta elettronica **o** nell'allegato di posta elettronica. Utilizzando le impostazioni standard dei criteri condizionali (il*messaggio contiene una di queste parole* e l' *allegato contiene una di queste parole*) per identificare i termini nei messaggi e negli allegati è necessario che i termini siano presenti **sia** nel messaggio che nell'allegato.
  
#### <a name="enter-multiple-conditions"></a>Immettere più condizioni

Se si immettono più condizioni, Microsoft 365 utilizza tutte le condizioni insieme per determinare quando applicare il criterio di conformità della comunicazione agli elementi di comunicazione. Quando si configurano più condizioni, è necessario che vengano soddisfatte tutte le condizioni per applicare il criterio, a meno che non si immetta un'eccezione. Ad esempio, è necessario un criterio che si applica se un messaggio contiene la parola "Trade" ed è maggiore di 2 MB. Tuttavia, se il messaggio contiene anche le parole "approvate da Contoso Financial", il criterio non deve essere applicato. In questo esempio, le tre condizioni verrebbero definite nel modo seguente:
  
- Il **messaggio contiene una di queste parole**, con le parole chiave "Trade"
- La **dimensione del messaggio è maggiore di**, con il valore 2 MB
- Il **messaggio contiene nessuna di queste parole**, con le parole chiave "approvate dal team finanziario contoso"

### <a name="review-percentage"></a>Percentuale di Revisione

Se si desidera ridurre la quantità di contenuto da rivedere, è possibile specificare una percentuale di tutte le comunicazioni regolate da un criterio di conformità della comunicazione. Viene selezionato un campione casuale di contenuto in tempo reale rispetto alla percentuale totale di contenuto che corrisponde alle condizioni dei criteri scelte. Se si desidera che i revisori rivedano tutti gli elementi, è possibile configurare il **100%** in un criterio di conformità della comunicazione.

## <a name="notices"></a>Avvisi

È possibile creare modelli di avviso se si desidera inviare agli utenti una notifica di promemoria tramite posta elettronica per le corrispondenze di criteri nell'ambito del processo di risoluzione dei problemi. Gli avvisi possono essere inviati solo all'indirizzo di posta elettronica dipendente associato alla corrispondenza dei criteri che ha generato l'avviso specifico per la correzione. Quando si seleziona un modello di avviso da applicare a una violazione dei criteri nell'ambito del flusso di lavoro di correzione, è possibile scegliere di accettare i valori del campo definiti nel modello o sovrascrivere i campi in base alle esigenze.

I modelli di avviso sono modelli di posta elettronica personalizzati in cui è possibile definire i campi del messaggio seguenti:

|**Campo**|**Obbligatorio**| **Dettagli** |
|:-----|:-----|:-----|
|**Nome del modello** | Sì | Nome descrittivo per il modello di avviso che è possibile selezionare nel flusso di lavoro Notify durante la correzione, supporta i caratteri di testo. |
| **Indirizzo del mittente** | Sì | L'indirizzo di uno o più utenti o gruppi che invia il messaggio al dipendente con una corrispondenza di criteri, selezionata da Active Directory per l'abbonamento. |
| **Indirizzi CC e Ccn** | No | Gli utenti o i gruppi facoltativi da notificare la corrispondenza dei criteri, selezionati da Active Directory per l'abbonamento. |
| **Oggetto** | Sì | Le informazioni visualizzate nella riga dell'oggetto del messaggio supportano caratteri di testo. |
| **Corpo del messaggio** | Sì | Informazioni visualizzate nel corpo del messaggio, supporta i valori di testo o HTML. |

### <a name="html-for-notices"></a>HTML per gli avvisi

Se si desidera creare più di un semplice messaggio di posta elettronica basato su testo per le notifiche, è possibile creare un messaggio più dettagliato utilizzando HTML nel campo corpo del messaggio di un modello di avviso. Nell'esempio seguente viene fornito il formato del corpo del messaggio per un modello di notifica di posta elettronica basato su HTML:

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
>L'implementazione dell'attributo HTML href nei modelli di notifica di conformità di comunicazione supporta attualmente solo virgolette singole anziché virgolette doppie per i riferimenti URL.

## <a name="filters"></a>Filtri

I filtri di conformità di comunicazione consentono di filtrare e ordinare i messaggi di avviso per eseguire più rapidamente le operazioni di analisi e correzione. Il filtro è disponibile nelle schede **in sospeso** e **risolte** per ogni criterio. Per salvare un filtro o un set di filtri come query del filtro salvato, è necessario configurare uno o più valori come selezioni dei filtri. Nella tabella seguente vengono illustrati i dettagli del filtro:

|**Filter**|**Dettagli**|
|:-----|:-----|
| **Data** | La data in cui il messaggio è stato inviato o ricevuto da un utente dell'organizzazione. |
| **Classe file** | La classe del messaggio in base al tipo di messaggio, ovvero *messaggio* o *allegato*. |
| **Ha allegato** | La presenza degli allegati nel messaggio. |
| **Classe Item** | L'origine del messaggio in base al tipo di messaggio, alla posta elettronica, a Microsoft Team Chat, Bloonmberg e così via. Per ulteriori informazioni sui tipi di elementi comuni e sulle classi dei messaggi, vedere [tipi di elementi e classi di messaggi](https://docs.microsoft.com/office/vba/outlook/concepts/forms/item-types-and-message-classes). |
| **Domini destinatario** | Il dominio in cui è stato inviato il messaggio. Questo dominio è in genere il dominio di sottoscrizione Microsoft 365 per impostazione predefinita. |
| **Destinatario** | L'utente a cui è stato inviato il messaggio. |
| **Mittente** | La persona che ha inviato il messaggio. |
| **Dominio mittente** | Il dominio che ha inviato il messaggio. |
| **Dimensioni** | Le dimensioni del messaggio in KB. |
| **Subject/title** | L'oggetto del messaggio o il titolo della chat. |
| **Categorie** | Tag assegnati a un messaggio, che può essere *discutibile*, *conforme*o *non conforme*. |
| **Escalation a** | Il nome utente della persona inclusa come parte di un'azione di escalation dei messaggi. |
| **Classificatori** | Nome dei classificatori incorporati e personalizzati che si applicano al messaggio. Alcuni esempi includono il *linguaggio offensivo*, la *molestia mirata*, la *profanità*, la *minaccia*e altro ancora.

## <a name="alert-policies"></a>Criteri di avviso

Dopo aver configurato un criterio, viene creato automaticamente un criterio di avviso corrispondente e vengono generati avvisi per i messaggi che soddisfano le condizioni definite nel criterio. Per impostazione predefinita, tutti i criteri corrispondenti ai trigger di avviso sono assegnati a un livello di gravità medio nel criterio di avviso associato. Gli avvisi vengono generati per un criterio di conformità della comunicazione dopo che il livello di soglia dei trigger di aggregazione viene soddisfatto nel criterio di avviso associato.

Per i criteri di conformità della comunicazione, i valori dei criteri di avviso seguenti sono configurati per impostazione predefinita:

|**Trigger di criteri di avviso**|**Valore predefinito**|
|:-----|:-----|
| Aggregazione | Aggregazione semplice |
| Soglia | 4 attività |
| Finestra | 60 minuti |

>[!Note]
>Le impostazioni dei trigger di soglia dei criteri di avviso per le attività supportano un valore minimo di 3 o superiore per i criteri di conformità della comunicazione.

È possibile modificare le impostazioni predefinite per i trigger per il numero di attività, il periodo per le attività e per gli utenti specifici nei criteri di avviso nella pagina **criteri di avviso** nel centro sicurezza & conformità.

### <a name="change-the-severity-level-for-an-alert-policy"></a>Modificare il livello di gravità per un criterio di avviso

Se si desidera modificare il livello di gravità assegnato in un criterio di avviso per uno specifico criterio di conformità della comunicazione, eseguire la procedura seguente:

1. Accedere [https://compliance.microsoft.com](https://compliance.microsoft.com) con le credenziali per un account di amministratore nell'organizzazione Microsoft 365.

2. Nel centro conformità di Microsoft 365, passare a **criteri**.

3. Selezionare **office 365 Alert** nella pagina **criteri** per aprire la pagina **criteri avvisi** nel **Centro sicurezza & conformità di Office 365**.

4. Selezionare la casella di controllo per il criterio di conformità di comunicazione che si desidera aggiornare, quindi selezionare **modifica criterio**.

5. Nella scheda **Descrizione** selezionare l'elenco a discesa **Severity** per configurare il livello di avviso del criterio.

6. Selezionare **Salva** per applicare il nuovo livello di gravità al criterio.

7. Selezionare **Chiudi** per uscire dalla pagina dei dettagli del criterio di avviso.

## <a name="audit"></a>Audit

In alcuni casi, è necessario fornire informazioni ai revisori dei conti normativi o di conformità per dimostrare la supervisione delle attività e delle comunicazioni degli impiegati. Tali informazioni possono essere un riepilogo di tutte le attività associate a un criterio organizzativo definito o in qualsiasi momento in cui si modifica un criterio di conformità della comunicazione. I criteri di conformità della comunicazione hanno percorsi di controllo incorporati per una preparazione completa per i controlli interni o esterni. Le cronologie di controllo dettagliate di ogni azione di creazione, modifica ed eliminazione vengono acquisite dai criteri di comunicazione per fornire la prova delle procedure di supervisione.

>[!Important]
>È necessario che il controllo sia abilitato per l'organizzazione prima che vengano registrati gli eventi di conformità della comunicazione. Per abilitare il controllo, vedere [Enable the audit log](communication-compliance-configure.md#step-2-required-enable-the-audit-log).

Per visualizzare le attività relative ai criteri di conformità della comunicazione, selezionare il controllo **Esporta attività di revisione** nella pagina principale per tutti i criteri. Questa azione genera un file di controllo nel formato. csv che contiene le informazioni seguenti:

|**Campo**|**Dettagli**|
|:-----|:-----|
| **CreationDate** | Data in cui l'attività è stata eseguita in un criterio. |
| **UserIds** | L'utente che ha eseguito l'attività in un criterio. |
| **Operazioni** | Le operazioni eseguite sul criterio. |
| **AuditData** | Questo campo è l'origine dati principale per tutte le attività dei criteri. Tutte le attività vengono registrate e separate da delimitatori di virgole. |

È inoltre possibile visualizzare le attività di controllo nel log di controllo unificato o con il cmdlet di PowerShell [Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog) .

Ad esempio, nell'esempio seguente vengono restituite le attività per tutte le attività di revisione di supervisione (criteri e regole):

```PowerShell
Search-UnifiedAuditLog -StartDate $startDate -EndDate $endDate -RecordType AeD -Operations SupervisoryReviewTag
```

In questo esempio vengono restituite le attività di aggiornamento per i criteri di conformità della comunicazione:

```PowerShell
Search-UnifiedAuditLog -StartDate $startDate -EndDate $endDate -RecordType Discovery -Operations SupervisionPolicyCreated,SupervisionPolicyUpdated,SupervisionPolicyDeleted
```

## <a name="ready-to-get-started"></a>Pronti per iniziare?

Per configurare la conformità di comunicazione per l'organizzazione Microsoft 365, vedere [Configure Communication Compliance for your microsoft 365 Organization](communication-compliance-configure.md).
