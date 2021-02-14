---
title: Criteri di supervisione
description: Informazioni sull'uso dei criteri di supervisione in Microsoft 365 per acquisire le comunicazioni dei dipendenti per l'esame da parte di revisori designati.
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
ms.custom: seo-marvel-apr2020
titleSuffix: Microsoft 365 Compliance
ms.openlocfilehash: 27c4d4603396089cb58cfed192f09d0db70cac5a
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547586"
---
# <a name="supervision-policies"></a>Criteri di supervisione

>[!IMPORTANT]
>Dopo il rilascio della conformità delle comunicazioni in Conformità Microsoft 365 a febbraio 2020, la supervisione in Office 365 viene ritirata. I criteri di supervisione non saranno più disponibili per la creazione e i criteri verranno rimossi dopo un lungo periodo di accesso in sola lettura.
>
>Se si utilizza supervisione, tenere presente che:
>
>- A partire dal 15 giugno 2020, i tenant non potranno creare nuovi criteri di supervisione.
>- A partire dal 31 agosto 2020, i criteri esistenti interromperanno l'acquisizione dei nuovi messaggi.
>- A partire dal 26 ottobre 2020, i criteri esistenti verranno eliminati.
>
>We actively encourage customers who are currently exploring or using Supervision in Office 365 to use the new [communication compliance](communication-compliance.md) solution to address your communications monitoring or regulatory requirements with a much richer set of intelligent capabilities.

I criteri di supervisione in Microsoft 365 consentono di acquisire le comunicazioni dei dipendenti per l'esame da parte di revisori designati. È possibile definire criteri specifici che acquisiscono la posta elettronica interna ed esterna, Microsoft Teams o le comunicazioni di terze parti nell'organizzazione. I revisori possono quindi esaminare i messaggi per verificare che siano conformi agli standard di messaggi dell'organizzazione e risolverli con il tipo di classificazione.

Questi criteri possono anche aiutare a superare molte sfide di conformità moderne, tra cui:

- Monitoraggio di tipi crescenti di canali di comunicazione
- L'aumento del volume di dati dei messaggi
- L'applicazione & il rischio di sanzioni

In alcune organizzazioni può verificarsi una separazione dei compiti tra il supporto IT e il gruppo di gestione della conformità. Microsoft 365 supporta la separazione tra la configurazione delle funzionalità dei criteri di supervisione e la configurazione dei criteri per le comunicazioni acquisite. Ad esempio, il gruppo IT di un'organizzazione può essere responsabile della configurazione delle autorizzazioni di ruolo e dei gruppi per supportare i criteri di supervisione configurati e gestiti dal team di conformità dell'organizzazione.

Per una rapida panoramica dei criteri di supervisione, vedi il video sui criteri di [supervisione](https://youtu.be/C3Y8WZ7o_dI) nel [canale Microsoft Mechanics.](https://www.youtube.com/user/OfficeGarageSeries)

## <a name="transitioning-from-supervision"></a>Transizione dalla supervisione

Le organizzazioni che usano i criteri di supervisione e pianificano la transizione ai criteri di conformità delle comunicazioni [in Microsoft 365](communication-compliance.md) devono comprendere questi punti importanti:

- La soluzione di supervisione in Microsoft 365 verrà completamente sostituita dalla soluzione di conformità delle comunicazioni in Microsoft 365. Per le organizzazioni che passano alla conformità delle comunicazioni dai criteri di  supervisione, è consigliabile creare nuovi criteri nella conformità delle comunicazioni che hanno le stesse condizioni dei criteri di supervisione esistenti per consentire nuovi miglioramenti di analisi e correzione. Quando si passa alla conformità delle comunicazioni in Microsoft 365, è consigliabile pianificare l'esportazione dei dati di report dalla supervisione se si dispone di requisiti dei criteri di conservazione di conformità interni.
- Nel frattempo, le organizzazioni possono utilizzare entrambe le soluzioni affiancate fino alla migrazione completa, ma i criteri utilizzati in ogni soluzione devono avere *nomi di criteri univoci.* I gruppi e i dizionari di parole chiave personalizzati possono essere condivisi tra le soluzioni durante il periodo di transizione.
- I messaggi salvati in supervisione nelle corrispondenze dei criteri di Microsoft 365 non possono essere spostati o condivisi nella conformità delle comunicazioni in Microsoft 365.

Per informazioni sul ritiro per la supervisione in Office 365, vedere la roadmap di [Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap) per informazioni dettagliate.

## <a name="scenarios-for-supervision-policies"></a>Scenari per i criteri di supervisione

I criteri di supervisione possono facilitare il monitoraggio delle comunicazioni nell'organizzazione in diverse aree:

- **Criteri aziendali**

    I dipendenti devono rispettare l'uso accettabile, gli standard etici e altri criteri aziendali in tutte le comunicazioni aziendali. I criteri di supervisione possono rilevare violazioni dei criteri e consentono di intraprendere azioni correttive per ridurre questi tipi di incidenti. Ad esempio, potresti monitorare potenziali violazioni delle risorse umane, ad esempio molestie o l'uso di linguaggio inappropriato o offensivo nelle comunicazioni dei dipendenti.

- **Gestione dei rischi**

    Le organizzazioni sono responsabili di tutte le comunicazioni distribuite nell'infrastruttura e nei sistemi di rete aziendali. L'uso dei criteri di supervisione per identificare e gestire la potenziale esposizione legale e i rischi può contribuire a ridurre al minimo i rischi prima che possano danneggiare le operazioni aziendali. Ad esempio, è possibile monitorare l'organizzazione per le comunicazioni non autorizzate per i progetti riservati, ad esempio acquisizioni imminenti, fusioni, divulgazioni di utili, riorganizzazioni o modifiche del team di leadership.

- **Conformità alle normative**

    La maggior parte delle organizzazioni deve rispettare alcuni tipi di standard di conformità alle normative nell'ambito delle normali procedure operative. Queste normative spesso richiedono alle organizzazioni di implementare un tipo di processo di supervisione o supervisione per la messaggistica appropriata per il proprio settore. La regola 3110 dell'autorità di regolamentazione del settore finanziario (FINRA) è un buon esempio di requisito per le organizzazioni di disporre di procedure di supervisione per monitorare le attività dei dipendenti e i tipi di aziende in cui si impegna. Un altro esempio potrebbe essere la necessità di monitorare broker-rivenditori nell'organizzazione per proteggersi da potenziali attività di riciclaggio, insider trading, collusione o corruzione. I criteri di supervisione possono aiutare l'organizzazione a soddisfare questi requisiti fornendo un processo per monitorare e segnalare le comunicazioni aziendali.

## <a name="components"></a>Componenti

### <a name="supervision-policy"></a>Criteri di supervisione

I criteri di supervisione vengono creati nel Centro conformità. Questi criteri definiscono quali comunicazioni e utenti sono soggetti a revisione nell'organizzazione, definiscono le condizioni personalizzate che le comunicazioni devono soddisfare e specificano chi deve eseguire le revisioni. Gli utenti inclusi nel gruppo di ruoli Revisione di supervisione possono configurare i criteri e chiunque abbia questo ruolo assegnato può accedere alla pagina Supervisione nel Centro conformità.

### <a name="supervised-users"></a>Utenti supervisionati

Prima di iniziare a usare la supervisione, è necessario determinare chi deve essere esaminato dalle comunicazioni. Nel criterio, gli indirizzi di posta elettronica degli utenti identificano gli utenti o i gruppi di persone da supervisionare. Alcuni esempi di questi gruppi sono i gruppi di Microsoft 365, le liste di distribuzione basate su Exchange e i canali di Microsoft Teams. È inoltre possibile escludere utenti o gruppi specifici dalla supervisione con un gruppo supervisionato o un elenco di gruppi.

>[!IMPORTANT]
>Gli utenti monitorati dai criteri di supervisione devono avere una licenza Di conformità di Microsoft 365 E5, una licenza di Office 365 Enterprise E3 con il componente aggiuntivo Conformità avanzata o essere inclusi in un abbonamento a Office 365 Enterprise E5 o essere inclusi in un abbonamento a Microsoft 365 E5. Se non si dispone di un piano Enterprise E5 esistente e si vuole provare la supervisione, è possibile iscriversi per una versione di valutazione di [Office 365 Enterprise E5.](https://go.microsoft.com/fwlink/p/?LinkID=698279)

### <a name="reviewers"></a>Revisori

Quando si crea un criterio di supervisione, è necessario determinare chi eseguirà le revisioni dei messaggi degli utenti supervisionati. Nel criterio, gli indirizzi di posta elettronica degli utenti identificano gli utenti o i gruppi di persone per esaminare le comunicazioni supervisionate. Tutti i revisori devono disporre di cassette postali ospitate su Exchange Online.

### <a name="groups-for-supervised-users-and-reviewers"></a>Gruppi per utenti e revisori supervisionati

Per semplificare la configurazione, creare gruppi per gli utenti che necessitano di una revisione delle comunicazioni e gruppi per gli utenti che esaminano tali comunicazioni. Se si usano gruppi, potrebbero essere necessari diversi gruppi. Ad esempio, se si desidera monitorare le comunicazioni tra due gruppi distinti di persone o se si desidera specificare un gruppo che non è supervisionato.

Quando si seleziona un gruppo di Microsoft 365 per gli utenti supervisionati, il criterio monitora il contenuto della cassetta postale condivisa e i canali di Microsoft Teams associati al gruppo. Quando si seleziona una lista di distribuzione, il criterio monitora le cassette postali dei singoli utenti.

### <a name="supported-communication-types"></a>Tipi di comunicazione supportati

Con i criteri di supervisione, è possibile scegliere di monitorare i messaggi in una o più delle piattaforme di comunicazione seguenti:

- **Posta elettronica di Exchange:** Le cassette postali ospitate su Exchange Online come parte dell'abbonamento a Microsoft 365 sono tutte idonee per la supervisione dei messaggi. I messaggi di posta elettronica e gli allegati corrispondenti alle condizioni dei criteri di supervisione sono immediatamente disponibili per il monitoraggio e nei report di supervisione. I tipi di allegati supportati per la supervisione sono gli stessi dei tipi di file supportati per le ispezioni del contenuto delle regole del flusso di posta [di Exchange.](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection)

- **Microsoft Teams:** È possibile supervisionare le comunicazioni in chat e gli allegati associati nei canali pubblici e privati di Microsoft Teams e nelle singole chat. Le chat di Teams che corrispondono alle condizioni dei criteri di supervisione vengono elaborate una volta ogni 24 ore e quindi sono disponibili per il monitoraggio e nei report di supervisione. Utilizzare le configurazioni di gestione dei gruppi seguenti per supervisionare le chat dei singoli utenti e le comunicazioni dei canali in Teams:

    - **Per la supervisione della chat di Teams:** Assegnare singoli utenti o assegnare un [gruppo di distribuzione](https://support.office.com/article/Distribution-groups-E8BA58A8-FAB2-4AAF-8AA1-2A304052D2DE) al criterio di supervisione. Questa configurazione è per le relazioni utente/chat 1-a-1 o 1-to-many.
    - **Per le comunicazioni del Canale di Teams:** Assegnare ai criteri di supervisione tutti i canali di Microsoft Team o i gruppi di Microsoft 365 che si desidera monitorare che contengono un utente specifico. Se si aggiunge lo stesso utente ad altri canali di Microsoft Teams o gruppi di Microsoft 365, assicurarsi di aggiungere questi nuovi canali e gruppi ai criteri di supervisione.

- **Skype for Business online:** Le comunicazioni in chat e gli allegati associati in Skype for Business online possono essere supervisionati. Le chat di Skype for Business online che corrispondono alle condizioni dei criteri di supervisione vengono elaborate una volta ogni 24 ore e quindi sono disponibili per il monitoraggio e nei report di supervisione. Le conversazioni di chat supervisionate derivano da [conversazioni precedenti salvate in Skype for Business online.](https://support.office.com/article/Find-a-previous-Skype-for-Business-conversation-18892eba-5f18-4281-8c87-fd48bd72e6a2)  Utilizzare la seguente configurazione di gestione dei gruppi per supervisionare le comunicazioni di chat degli utenti in Skype for Business online:

    - **Per la supervisione della chat di Skype for Business online:** Assegnare singoli utenti o assegnare un [gruppo di distribuzione](https://support.office.com/article/Distribution-groups-E8BA58A8-FAB2-4AAF-8AA1-2A304052D2DE) al criterio di supervisione. Questa configurazione è per le relazioni utente/chat 1-a-1 o 1-to-many.

- **Origini di terze parti:** È possibile supervisionare le comunicazioni da origini di terze parti (ad esempio da Facebook o DropBox) per i dati importati nelle cassette postali dell'organizzazione. [Informazioni su come importare dati di terze parti.](archiving-third-party-data.md)

Per impostazione predefinita, le comunicazioni acquisite in queste piattaforme vengono conservate per sette anni per ogni criterio, anche se gli utenti lasciano l'organizzazione e la loro cassetta postale viene eliminata.

### <a name="policy-settings"></a>Impostazioni dei criteri

#### <a name="direction"></a>Direction

Per impostazione predefinita, **la condizione Direction** è visualizzata e non può essere rimossa. Le impostazioni della direzione di comunicazione in un criterio vengono scelte singolarmente o insieme:

- **In ingresso:** è possibile scegliere In  **ingresso** per esaminare le comunicazioni inviate alle persone che si è scelto di **supervisionare** da persone non incluse nel criterio.
- **In** uscita: è **possibile** scegliere In  uscita se si desidera esaminare le comunicazioni inviate dalle persone che si è scelto di **supervisionare** a persone non incluse nel criterio.
- **Interno:** è possibile scegliere **Interno** per esaminare le comunicazioni inviate **tra** le persone identificate nel criterio.

#### <a name="sensitive-information-types"></a>Tipi di informazioni sensibili

È possibile includere i tipi di informazioni riservate come parte dei criteri di supervisione. I tipi di informazioni riservate sono tipi di dati predefiniti o personalizzati che consentono di identificare e proteggere i numeri di carta di credito, i numeri di conto corrente bancario, i numeri di passaporto e altro ancora. Come parte della prevenzione della perdita dei dati [(DLP),](data-loss-prevention-policies.md)la configurazione delle informazioni riservate può utilizzare modelli, prossimità dei caratteri, livelli di sicurezza e anche tipi di dati personalizzati per identificare e contrassegnare i contenuti che potrebbero essere sensibili. I tipi di informazioni riservate predefiniti sono:

- Finanze
- Salute e salute
- Privacy
- Tipo di informazioni personalizzato

Per ulteriori informazioni sui dettagli delle informazioni riservate e sui modelli inclusi nei tipi predefiniti, vedere Definizioni delle entità [dei tipi di informazioni riservate.](sensitive-information-type-entity-definitions.md)

#### <a name="custom-keyword-dictionaries"></a>Dizionari di parole chiave personalizzati

Configurare dizionari di parole chiave personalizzati (o lessiconi) per fornire una gestione semplice delle parole chiave specifiche dell'organizzazione o del settore. I dizionari di parole chiave supportano fino a 100 KB di termini (post compressione) nel dizionario e supportano qualsiasi lingua. Anche il limite del tenant è di 100 KB dopo la compressione. Se necessario, è possibile applicare più dizionari di parole chiave personalizzati a un singolo criterio o disporre di un singolo dizionario di parole chiave per criterio. Questi dizionari vengono assegnati in un criterio di supervisione e possono essere provenienti da un file (ad esempio un elenco csv o txt) o da un elenco che è possibile importare nel Centro [conformità.](create-a-keyword-dictionary.md)

#### <a name="offensive-language"></a>Linguaggio offensivo

Monitorare i messaggi di posta elettronica inviati o ricevuti nell'organizzazione per un linguaggio offensivo. Il modello usa una combinazione di machine learning, intelligenza artificiale e parole chiave per identificare il linguaggio nei messaggi di posta elettronica che potrebbero violare i criteri anti-molestie e bullismo. Il modello di linguaggio offensivo attualmente supporta le parole chiave inglesi e monitora il corpo dei messaggi di posta elettronica.

>[!NOTE]
>Creare un [criterio di prevenzione della](create-test-tune-dlp-policy.md) perdita di dati con un dizionario di parole [chiave](create-a-keyword-dictionary.md) personalizzato di termini bloccati se è necessario:
>
>- monitorare le comunicazioni di Microsoft Teams nell'organizzazione per un linguaggio offensivo
>- impedire o bloccare il linguaggio offensivo nelle comunicazioni nell'organizzazione

Il modello non fornisce un elenco esaustivo del linguaggio offensivo. Inoltre, gli standard linguistici e culturali cambiano continuamente e, alla luce di queste realtà, Microsoft si riserva il diritto di aggiornare il modello a sua discrezione. Anche se il modello può aiutare l'organizzazione a monitorare il linguaggio offensivo, il modello non è progettato per fornire l'unico mezzo per monitorare o affrontare tale linguaggio. L'organizzazione, non Microsoft, rimane responsabile di tutte le decisioni relative al monitoraggio e al blocco del linguaggio offensivo.

Il modello di linguaggio offensivo monitora la posta elettronica per le valutazioni associate ai seguenti tipi di lingua:

|**Tipo**|**Descrizione**|
|:-----|:-----|
| **Volgarità** | Espressioni che invade la maggior parte delle persone. |
| **Legatori** | Espressioni che esprimano un pregiudicato nei confronti di gruppi specifici (ad esempio, etnia, orientamento sessuale, disabilità). |
| **Scherni** | Espressioni che provocano provocazione, violenza, scherno o potrebbero causare ingiusto o violenza. |
| **Espressioni mascherate** | Espressioni per cui il significato o la pronuncia è uguale a un altro termine più offensivo. |

#### <a name="conditional-settings"></a>Impostazioni condizionali
<a name="ConditionalSettings"> </a>

Le condizioni selezionate per il criterio si applicano alle comunicazioni provenienti sia dalla posta elettronica che da origini di terze parti nell'organizzazione (ad esempio da Facebook o DropBox).

Nella tabella seguente vengono illustrate ulteriori informazioni su ogni condizione.
  
|**Condizione**|**Come usare questa condizione**|
|:-----|:-----|
| **Il messaggio viene ricevuto da uno di questi domini** <br><br> **Il messaggio non viene ricevuto da nessuno di questi domini** | Applicare il criterio per includere o escludere domini o indirizzi di posta elettronica specifici nei messaggi ricevuti. Immettere ogni dominio o indirizzo di posta elettronica e separare più domini o indirizzi di posta elettronica con una virgola. Ogni dominio o indirizzo di posta elettronica immesso viene applicato separatamente, solo un dominio o un indirizzo di posta elettronica deve essere applicato per applicare il criterio al messaggio. <br><br> Se si desidera monitorare tutta la posta elettronica da un dominio specifico, ma si desidera escludere i messaggi  che non necessitano di revisione (newsletter, annunci e così via), è necessario configurare la condizione che un messaggio non viene ricevuto da uno di questi domini condizione che esclude l'indirizzo di posta elettronica (ad esempio "newsletter@contoso.com"). |
| **Il messaggio viene inviato a uno di questi domini** <br><br> **Il messaggio non viene inviato ad alcuno di questi domini** | Applicare il criterio per includere o escludere domini o indirizzi di posta elettronica specifici nei messaggi inviati. Immettere ogni dominio o indirizzo di posta elettronica e separare più domini o indirizzi di posta elettronica con una virgola. Ogni dominio o indirizzo di posta elettronica viene applicato separatamente, solo un dominio o un indirizzo di posta elettronica deve essere applicato per applicare il criterio al messaggio. <br><br> Se si desidera monitorare tutta la posta elettronica inviata a un dominio specifico, ma si desidera escludere i messaggi inviati che non devono essere esaminati, è necessario configurare due condizioni: <br> - Un **messaggio viene inviato a una condizione di** questi domini che definisce il dominio ("contoso.com"), AND <br> - Un **messaggio non viene inviato ad alcuna** condizione di questi domini che esclude l'indirizzo di posta elettronica ("subscriptions@contoso.com"). |
| **Il messaggio è classificato con una di queste etichette** <br><br> **Il messaggio non è classificato con nessuna di queste etichette** | Per applicare il criterio quando alcune etichette di conservazione vengono incluse o escluse in un messaggio. Le etichette di conservazione devono essere configurate separatamente e le etichette configurate vengono scelte come parte di questa condizione. Ogni etichetta scelta viene applicata separatamente (solo una di queste etichette deve essere applicata per applicare il criterio al messaggio). Per ulteriori informazioni sulle etichette di conservazione, vedere [Informazioni sui criteri di conservazione e sulle etichette di conservazione.](retention.md)|
| **Il messaggio contiene una di queste parole** <br><br> **Il messaggio non contiene nessuna di queste parole** | Per applicare il criterio quando determinate parole o frasi vengono incluse o escluse in un messaggio, immettere ogni parola o frase e separarli con una virgola. Ogni parola immessa viene applicata separatamente (solo una parola deve essere applicata per applicare il criterio al messaggio). Per ulteriori informazioni sull'immissione di parole o frasi, vedere la sezione successiva che corrisponde a parole e frasi a messaggi di posta [elettronica o allegati.](supervision-policies.md#Matchwords)|
| **L'allegato contiene una di queste parole** <br><br> **L'allegato non contiene nessuna di queste parole** | Per applicare il criterio quando determinate parole o frasi vengono incluse o escluse in un allegato del messaggio ,ad esempio un documento di Word, immettere ogni parola o frase e separarli con una virgola. Ogni parola immessa viene applicata separatamente (solo una parola deve essere applicata per applicare il criterio all'allegato). Per ulteriori informazioni sull'immissione di parole o frasi, vedere la sezione successiva che corrisponde a parole e frasi a messaggi di posta [elettronica o allegati.](supervision-policies.md#Matchwords)|
| **L'allegato è uno di questi tipi di file** <br><br> **L'allegato non è uno di questi tipi di file** | Per supervisionare le comunicazioni che includono o escludono tipi specifici di allegati, immettere le estensioni di file,ad esempio .exe o .pdf. Se si desidera includere o escludere più estensioni di file, immetterli in righe separate. Solo un'estensione dell'allegato deve corrispondere per l'applicazione del criterio.|
| **La dimensione del messaggio è superiore a** <br><br> **La dimensione del messaggio non è superiore a** | Per esaminare i messaggi in base a una determinata dimensione, utilizzare queste condizioni per specificare la dimensione massima o minima che un messaggio può avere prima di essere sottoposto a revisione. Ad esempio, se  si specifica che la dimensione del messaggio è superiore a \> **1,0 MB,** tutti i messaggi di dimensioni superiori a 1,01 MB sono soggetti a revisione. È possibile scegliere byte, kilobyte, megabyte o gigabyte per questa condizione.|
| **L'allegato è più grande di** <br><br> **L'allegato non è più grande di** | Per esaminare i messaggi in base alle dimensioni degli allegati, specificare la dimensione massima o minima che un allegato può avere prima che il messaggio e i relativi allegati siano soggetti a revisione. Ad esempio, se  si specifica che l'allegato è superiore a \> **2,0 MB,** tutti i messaggi con allegati di 2,01 MB e oltre sono soggetti a revisione. È possibile scegliere byte, kilobyte, megabyte o gigabyte per questa condizione.|
   
##### <a name="matching-words-and-phrases-to-emails-or-attachments"></a>Corrispondenza di parole e frasi a messaggi di posta elettronica o allegati
<a name="Matchwords"></a> Ogni parola immessa e separata da una virgola viene applicata separatamente (solo una parola deve essere applicata per applicare la condizione del criterio al messaggio di posta elettronica o all'allegato). Ad esempio, usiamo la condizione, **Il** messaggio contiene una di queste parole, con le parole chiave "banker" e "insider trading" separate da una virgola (banker, insider trading). Il criterio si applica a tutti i messaggi che includono la parola "banker" o la frase "insider trading". Per applicare questa condizione dei criteri, è necessario che si verifichi solo una di queste parole o frasi. Le parole nel messaggio o nell'allegato devono corrispondere esattamente a quelle immesse.

Per analizzare i messaggi di posta elettronica [](create-test-tune-dlp-policy.md) e gli allegati [](create-a-keyword-dictionary.md) per le stesse parole chiave, creare un criterio di prevenzione della perdita dei dati con un dizionario di parole chiave personalizzato per i termini che si desidera monitorare. Questa configurazione dei criteri identifica le parole chiave definite che vengono visualizzate nel messaggio di posta elettronica **O** nell'allegato di posta elettronica. L'utilizzo delle impostazioni dei criteri condizionali standard *(* Il messaggio contiene una di queste parole e l'allegato contiene una di queste parole) per identificare i termini nei messaggi e negli allegati richiede che i termini siano presenti **sia** nel messaggio che nell'allegato. 
  
##### <a name="enter-multiple-conditions"></a>Immettere più condizioni

Se si immettono più condizioni, Microsoft 365 usa tutte le condizioni insieme per determinare quando applicare il criterio agli elementi di comunicazione. Quando si configurano più condizioni, è necessario che vengano soddisfatte tutte le condizioni per l'applicazione del criterio, a meno che non venga immessa un'eccezione. Ad esempio, è necessario un criterio che si applica se un messaggio contiene la parola "trade" ed è superiore a 2 MB. Tuttavia, se il messaggio contiene anche le parole "Approvato da Contoso finanziario", il criterio non deve essere applicato. Pertanto, in questo caso, le tre condizioni sono le seguenti:
  
- **Il messaggio contiene una di queste parole,** con la parola chiave "trade"

- **La dimensione dei messaggi è maggiore di**, con il valore 2 MB

- **Il messaggio non contiene nessuna di queste parole,** con le parole chiave "Approvato dal team finanziario di Contoso"

#### <a name="review-percentage"></a>Percentuale revisione

Se si desidera ridurre la quantità di contenuto da rivedere, è possibile specificare una percentuale di tutte le comunicazioni disciplinate da un criterio di supervisione. Viene selezionato un campione casuale di contenuto in tempo reale dalla percentuale totale di contenuto che soddisfa le condizioni dei criteri scelte. Se si desidera che i revisori rivedano tutti gli elementi, è possibile immettere **il 100%** in un criterio di supervisione.

## <a name="monitor--manage"></a>Monitorare & gestione

È facile monitorare i risultati dei criteri di supervisione e applicare un tag di risoluzione. È possibile visualizzare rapidamente:

- Stato degli elementi esaminati
- Utenti e gruppi sotto supervisione
- Utenti e gruppi designati come revisori

### <a name="supervision-policy-dashboard"></a>Dashboard dei criteri di supervisione

Utilizzare il dashboard dei criteri di supervisione per gestire i risultati dei criteri di supervisione e risolvere gli elementi in sospeso. Questo dashboard consente ai revisori di visualizzare gli elementi che devono essere esaminati, agire su un elemento ed esaminare i risultati degli elementi esaminati e risolti in precedenza per ogni criterio di supervisione. È possibile accedere al dashboard dei criteri di supervisione nel Centro conformità **in**  >  *Supervisione apertura dei criteri*  >  **personalizzati.**

#### <a name="dashboard-home"></a>Dashboard Home

La home page **del** dashboard include diverse sezioni che consentono di agire rapidamente sui criteri di supervisione. Qui è possibile:

- Esaminare rapidamente gli elementi evidenziati in sospeso e risolti per la settimana
- Visualizzare un elenco degli utenti supervisionati e dei gruppi supervisionati per il criterio selezionato
- Visualizzare un elenco dei revisori e rivedere i team per il criterio selezionato
- Vedere quali piattaforme di comunicazione hanno contenuti sotto supervisione per i criteri

#### <a name="review-tab"></a>Scheda Revisione

Nella **scheda Revisione** i revisori classificano e risolvono gli elementi identificati dal criterio selezionato. Qui è possibile:

- Filtra in base a elementi in sospeso, conformi, non conformi e discutibili.
- Contrassegnare un singolo elemento come conforme, non conforme o discutibile. Puoi anche registrare un commento con l'elemento per chiarire l'azione di tagging eseguita.
- Contrassegnare in blocco più elementi come conformi, non conformi o discutibili. Puoi anche registrare un commento con più elementi per chiarire l'azione di tagging eseguita.
- Consente di visualizzare la cronologia del tagging per un singolo elemento. Include chi ha risolto l'elemento, la data e l'ora dell'azione, il tag di risoluzione ed eventuali commenti inclusi.
- Riclassificare gli elementi esaminati in precedenza come conformi, non conformi o discutibili. Puoi anche registrare un commento con uno o più elementi per chiarire l'azione di riclassificazione eseguita.

#### <a name="resolved-items-tab"></a>Scheda Elementi risolti

La **scheda Elementi risolti** consente ai revisori di visualizzare tutti gli elementi risolti in precedenza per il criterio selezionato. Qui è possibile:

- Visualizzare e ordinare rapidamente l'oggetto, il mittente e la data degli elementi risolti
- Visualizzare la classificazione e la cronologia dei commenti di qualsiasi elemento selezionato

## <a name="reports"></a>Report

Usa i report di supervisione per visualizzare l'attività di revisione a livello di criterio e revisore. Per ogni criterio, è anche possibile visualizzare le statistiche in tempo reale sullo stato corrente dell'attività di revisione. È possibile utilizzare i report di supervisione per:
  
- Verificare che i criteri funzionino come previsto.
- Scopri quante comunicazioni devono essere esaminate.
- Scopri quante comunicazioni non sono conformi e quali stanno superando la revisione. Queste informazioni consentono di decidere se ottimizzare i criteri o modificare il numero di revisori.

### <a name="view-the-supervision-report"></a>Visualizzare il report Supervisione

1. Accedere al Centro [conformità con](https://compliance.microsoft.com) le credenziali per un account amministratore con le autorizzazioni per visualizzare i report di supervisione.
2. Passare a  Dashboard report \> **o** **Supervisione** per visualizzare il widget di report di supervisione per un riepilogo dell'attività corrente dei criteri di supervisione.
3. Selezionare **il** widget Supervisione per aprire la pagina del report dettagliata.

>[!NOTE]
>Se non si è in  grado di accedere alla pagina Report, verificare di essere membri del gruppo di ruoli Revisione di supervisione, come descritto in Rendere disponibile la [supervisione nell'organizzazione.](configure-supervision-policies.md) L'inclusione in questo gruppo di ruoli consente di creare e gestire i criteri di supervisione ed eseguire il report.
  
### <a name="how-to-use-the-report"></a>Come usare il report

Questo report elenca ogni criterio e il numero di comunicazioni in ogni fase del processo di revisione. Utilizzare il report per:
  
- Visualizzare i dati per tutti i criteri o per criteri specifici.
- Visualizzare i dati raggruppati per tipo di tag, revisore o tipo di messaggio.
- Esportare i dati in un file CSV in base alla data dell'attività, ai criteri e all'attività del revisore.
- Filtra i dati in base alla data dell'attività, al tipo di tag, al revisore e al tipo di messaggio.

Ecco una suddivisione dei valori visualizzati nella colonna **Tipo di** tag.
  
|**Tipo di tag**|**Cosa significa**|
|:-----|:-----|
| **Non revisionato** | Numero di messaggi di posta elettronica non ancora esaminati. Questi messaggi di posta elettronica sono in attesa di revisione nel dashboard di supervisione di Microsoft 365.
| **Conforme** | Il numero di messaggi di posta elettronica revisionati e contrassegnati come conformi. Questi messaggi necessitano ancora di risoluzione. |
| **Discutibile** | Il numero di messaggi di posta elettronica revisionati e contrassegnati come discutibili. Funge da flag per altri revisori per verificare se un messaggio di posta elettronica necessita di analisi per la conformità. Questi messaggi necessitano ancora di risoluzione. |
| **Non conforme (attivo)** | Il numero di messaggi di posta elettronica non conformi che i revisori stanno attualmente esaminando. |
| **Non conforme (risolto)** | Numero di messaggi di posta elettronica non conformi che i revisori hanno esaminato e risolto. |
| **Criteri di hit** | Il numero totale (giornaliero) di messaggi provenienti da origini dati di Exchange, Teams e di terze parti che soddisfano una o più condizioni definite in un criterio di supervisione |
| **In Purview** | Il numero totale (giornaliero) di messaggi provenienti da origini dati di Exchange, Teams e di terze parti analizzati da un criterio di supervisione |
| **Risolto** | Il numero totale di messaggi provenienti da origini dati di Exchange, Teams e di terze parti classificate come **risolte**|

>[!NOTE]
>È necessario eseguire il provisioning dei criteri di supervisione prima che vengano visualizzati nei report. Se i criteri vengono eliminati, i dati cronologici vengono comunque visualizzati. Tuttavia, vengono indicati come "criteri inesistenti" e la funzione **di** esportazione non è disponibile.

## <a name="audit"></a>Audit

In alcuni casi, è necessario fornire informazioni ai revisori normativi o di conformità per dimostrare la supervisione delle attività e delle comunicazioni dei dipendenti. Queste informazioni possono essere un riepilogo di tutte le attività di supervisione associate a un criterio definito o ogni volta che viene modificato un criterio di supervisione. I criteri di supervisione dispongono di audit trail predefiniti per una preparazione completa per i controlli interni o esterni. Le cronologie di controllo dettagliate di ogni azione monitorata dai criteri di supervisione forniscono una prova delle procedure di supervisione.

Visualizzare le attività di controllo nel log di controllo unificato o con il cmdlet di PowerShell [Search-UnifiedAuditLog.](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog)

Ad esempio, nell'esempio seguente vengono restituite le attività per tutte le attività di revisione di supervisione (criteri e regole) e vengono elencate informazioni dettagliate per ognuna:

```PowerShell
Search-UnifiedAuditLog -StartDate 3/1/2019 -EndDate ([System.DateTime]::Now) -RecordType DataGovernance -ResultSize 5000 | Where-Object {$_.Operations -like "*SupervisoryReview*"}  | fl CreationDate,Operations,UserIds,AuditData
```

In questo esempio vengono restituite le attività di aggiornamento per i criteri di conformità delle comunicazioni:

```PowerShell
Search-UnifiedAuditLog -StartDate $startDate -EndDate $endDate -Operations SupervisionPolicyCreated,SupervisionPolicyUpdated,SupervisionPolicyDeletedAuditData
```

Oltre alle informazioni fornite nei rapporti e nei registri di supervisione, è anche possibile utilizzare il cmdlet [Di PowerShell Get-SupervisoryReviewActivity](https://docs.microsoft.com/powershell/module/exchange/get-supervisoryreviewactivity) per restituire un elenco dettagliato completo di tutte le attività dei criteri di supervisione.

## <a name="ready-to-get-started"></a>Pronti per iniziare?

Per configurare i criteri di supervisione per l'organizzazione, vedere [Configurare i criteri di supervisione.](configure-supervision-policies.md)
