---
title: Criteri di supervisione
description: Informazioni sui criteri di supervisione in Office 365
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
titleSuffix: Office 365 Compliance
ms.openlocfilehash: dafc745d985c93e4665db469442b0b6dc2eda070
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42081073"
---
# <a name="supervision-policies-in-office-365"></a>Criteri di supervisione in Office 365

I criteri di supervisione in Office 365 consentono di acquisire le comunicazioni dei dipendenti per l'esame da revisori designati. È possibile definire criteri specifici che consentono di acquisire messaggi di posta elettronica interni ed esterni, Microsoft teams o comunicazioni di terze parti nell'organizzazione. I revisori possono quindi esaminare i messaggi per assicurarsi che siano conformi agli standard dei messaggi dell'organizzazione e risolverli con il tipo di classificazione.

Questi criteri possono anche aiutare a superare molte sfide di conformità moderne, tra cui:

- Monitoraggio dei tipi di canali di comunicazione crescenti
- Volume crescente di dati dei messaggi
- Applicazione di regolamentazione & il rischio di multe

In alcune organizzazioni può verificarsi una separazione dei compiti tra il supporto IT e il gruppo di gestione della conformità. Office 365 supporta la separazione tra la configurazione delle funzionalità del criterio di supervisione e la configurazione dei criteri per le comunicazioni acquisite. Ad esempio, il gruppo IT di un'organizzazione potrebbe essere responsabile dell'impostazione delle autorizzazioni e dei gruppi di ruoli per supportare i criteri di supervisione configurati e gestiti dal team di conformità dell'organizzazione.

Per una breve panoramica dei criteri di supervisione, vedere il [video sui criteri di supervisione](https://youtu.be/C3Y8WZ7o_dI) sul [canale Microsoft Mechanics](https://www.youtube.com/user/OfficeGarageSeries).

Per ulteriori informazioni sui miglioramenti e la disponibilità delle funzionalità di supervisione imminenti, vedere la Guida di [orientamento di Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap).

Si desidera provare la nuova esperienza di conformità della comunicazione in Microsoft 365? Consultare le funzionalità nuove e migliorate disponibili in [Compliance Communication in Microsoft 365](communication-compliance.md).

## <a name="transitioning-from-supervision-in-office-365"></a>Transizione dalla vigilanza in Office 365

Le organizzazioni che utilizzano i criteri di supervisione in Office 365 e la pianificazione della transizione ai [criteri di conformità della comunicazione in Microsoft 365](communication-compliance.md) devono comprendere questi importanti punti:

- La soluzione di supervisione in Office 365 sarà completamente sostituita dalla soluzione di conformità della comunicazione in Microsoft 365. Per le organizzazioni che si conformano alla conformità alla comunicazione dai criteri di supervisione, si consiglia di creare nuovi criteri di conformità alla comunicazione con le stesse *condizioni* dei criteri di supervisione esistenti per consentire nuovi miglioramenti di analisi e correzione. Quando si esegue la transizione alla conformità alla comunicazione in Microsoft 365, è consigliabile pianificare l'esportazione dei dati di Reporting dalla supervisione in Office 365 se sono presenti requisiti per i criteri di conservazione della conformità interni.
- Nel frattempo, le organizzazioni possono utilizzare entrambe le soluzioni affiancate fino alla migrazione completa, ma i criteri utilizzati in ogni soluzione devono avere *nomi di criteri univoci*. I gruppi e i dizionari di parole chiave personalizzati possono essere condivisi tra le soluzioni durante il periodo di transizione.
- I messaggi salvati in supervisione nelle corrispondenze di criteri di Office 365 non possono essere spostati o condivisi nella conformità della comunicazione in Microsoft 365.


Per informazioni sulla pensione per la vigilanza in Office 365, vedere la Guida di [orientamento di Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap) per informazioni dettagliate.

## <a name="scenarios-for-supervision-policies"></a>Scenari per i criteri di supervisione

I criteri di supervisione possono assistere il monitoraggio delle comunicazioni nell'organizzazione in diverse aree:

- **Criteri aziendali**

    I dipendenti devono essere conformi all'uso accettabile, agli standard etici e ad altri criteri aziendali in tutte le comunicazioni relative alle aziende. I criteri di supervisione sono in grado di rilevare violazioni dei criteri e di eseguire azioni correttive che consentono di attenuare questi tipi di incidenti. Ad esempio, è possibile monitorare la propria organizzazione per individuare potenziali violazioni delle risorse umane, quali molestie o utilizzo di linguaggio inappropriato o offensivo nelle comunicazioni dei dipendenti.

- **Gestione dei rischi**

    Le organizzazioni sono responsabili di tutte le comunicazioni distribuite nell'infrastruttura e nei sistemi di rete aziendale. L'utilizzo dei criteri di supervisione per identificare e gestire potenziali esposizione e rischi legali può contribuire a ridurre al minimo i rischi prima che possano danneggiare le operazioni aziendali. Ad esempio, è possibile monitorare la propria organizzazione per le comunicazioni non autorizzate per progetti riservati, ad esempio acquisizioni imminenti, fusioni, divulgazioni di guadagni, riorganizzazioni o modifiche del team di leadership.

- **Conformità alle normative**

    La maggior parte delle organizzazioni deve soddisfare alcuni tipi di standard di conformità normativi nell'ambito delle normali procedure operative. Queste normative richiedono spesso che le organizzazioni implementino un qualche tipo di processo di supervisione o sorveglianza per la messaggistica appropriata per il proprio settore. La regola FINRA (Financial Industry Regulatory Authority) 3110 è un buon esempio di un requisito per le organizzazioni di disporre di procedure di supervisione per monitorare le attività dei suoi dipendenti e i tipi di imprese in cui si impegna. Un altro esempio potrebbe essere la necessità di monitorare broker-dealer nell'organizzazione per salvaguardarsi da possibili operazioni di riciclaggio, insider trading, collusioni o tangenti. I criteri di supervisione consentono all'organizzazione di soddisfare questi requisiti fornendo una procedura per monitorare e segnalare le comunicazioni aziendali.

## <a name="components"></a>Componenti

### <a name="supervision-policy"></a>Criteri di supervisione

È possibile creare criteri di supervisione nel centro conformità. Questi criteri definiscono le comunicazioni e gli utenti soggetti a revisione nell'organizzazione, definiscono le condizioni personalizzate che devono soddisfare le comunicazioni e specifica chi deve eseguire le revisioni. Gli utenti inclusi nel gruppo di ruoli revisione di supervisione possono impostare i criteri e tutti coloro a cui è assegnato questo ruolo possono accedere alla pagina di supervisione nel centro conformità.

### <a name="supervised-users"></a>Utenti controllati

Prima di iniziare a usare la supervisione, è necessario determinare chi ha bisogno delle proprie comunicazioni. Nei criteri, gli indirizzi di posta elettronica degli utenti identificano gli utenti o i gruppi di persone da sorvegliare. Alcuni esempi di questi gruppi sono i gruppi di Office 365, le liste di distribuzione basate su Exchange e i canali Microsoft teams. È inoltre possibile escludere utenti o gruppi specifici dalla supervisione con un gruppo controllato o un elenco di gruppi.

>[!IMPORTANT]
>Gli utenti monitorati dai criteri di supervisione devono avere una licenza di conformità Microsoft 365 E5, una licenza di Office 365 Enterprise E3 con il componente aggiuntivo per la conformità avanzato o essere inclusi in un abbonamento a Office 365 Enterprise E5. Se non si dispone di un piano Enterprise E5 esistente e si vuole provare a eseguire la supervisione, è possibile [iscriversi per una versione di valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).

### <a name="reviewers"></a>Revisori

Quando si crea un criterio di supervisione, è necessario determinare chi eseguirà le revisioni dei messaggi degli utenti controllati. Nei criteri, gli indirizzi di posta elettronica degli utenti identificano gli utenti o i gruppi di persone per esaminare le comunicazioni sorvegliate. Tutti i revisori devono disporre di cassette postali ospitate in Exchange Online.

### <a name="groups-for-supervised-users-and-reviewers"></a>Gruppi per gli utenti e i revisori controllati

Per semplificare l'installazione, creare gruppi per gli utenti che hanno bisogno di una revisione delle comunicazioni e di gruppi per gli utenti che esaminano tali comunicazioni. Se si utilizzano i gruppi, potrebbero essere necessari diversi. Ad esempio, se si desidera monitorare le comunicazioni tra due gruppi distinti di persone o se si desidera specificare un gruppo che non è supervisionato.

Quando si seleziona un gruppo di Office 365 per gli utenti controllati, il criterio monitora il contenuto della cassetta postale di Office 365 condivisa e dei canali Microsoft teams associati al gruppo. Quando si seleziona una lista di distribuzione, il criterio monitora le singole cassette postali degli utenti.

### <a name="supported-communication-types"></a>Tipi di comunicazione supportati

Con i criteri di supervisione, è possibile scegliere di monitorare i messaggi in una o più delle piattaforme di comunicazione seguenti:

- **Posta elettronica di Exchange:** Le cassette postali ospitate in Exchange Online come parte dell'abbonamento a Office 365 sono tutte idonee per la supervisione dei messaggi. I messaggi di posta elettronica e gli allegati che corrispondono alle condizioni dei criteri di supervisione sono immediatamente disponibili per il monitoraggio e i report I tipi di allegati supportati per la supervisione sono gli stessi dei [tipi di file supportati per le ispezioni del contenuto delle regole del flusso di posta di Exchange](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection).

- **Microsoft teams:** È possibile controllare le comunicazioni chat e gli allegati associati sia nei canali di Microsoft Public che in quelli privati e nelle chat individuali. Chat teams le condizioni dei criteri di supervisione vengono elaborate una volta ogni 24 ore e quindi sono disponibili per il monitoraggio e per i report di supervisione. Utilizzare le seguenti configurazioni di gestione dei gruppi per controllare le chat utente e le comunicazioni dei canali nei team:

    - **Per la supervisione di teams chat:** Assegnare singoli utenti o assegnare un [gruppo di distribuzione](https://support.office.com/article/Distribution-groups-E8BA58A8-FAB2-4AAF-8AA1-2A304052D2DE) ai criteri di supervisione. Questo è per le relazioni utente/chat da 1 a 1 o 1-a-molti.
    - **Per le comunicazioni di canale dei team:** Assegnare a tutti i gruppi di Microsoft Team Channel o Office 365 che si desidera monitorare che contengano un utente specifico per i criteri di supervisione. Se si aggiunge lo stesso utente ad altri canali Microsoft teams o gruppi di Office 365, accertarsi di aggiungere questi nuovi canali e gruppi ai criteri di supervisione.

- **Skype for business online:** È possibile controllare le comunicazioni chat e gli allegati associati in Skype for business online. Le chat di Skype for business online che corrispondono alle condizioni dei criteri di supervisione vengono elaborate una volta ogni 24 ore e quindi sono disponibili per il monitoraggio e nei report di supervisione. Le conversazioni di chat sorvegliate vengono provenienti da [precedenti conversazioni salvate in Skype for business online](https://support.office.com/article/Find-a-previous-Skype-for-Business-conversation-18892eba-5f18-4281-8c87-fd48bd72e6a2).  Utilizzare la configurazione di gestione dei gruppi seguente per supervisionare le comunicazioni della chat utente in Skype for business online:

    - **Per la supervisione della chat in Skype for business online:** Assegnare singoli utenti o assegnare un [gruppo di distribuzione](https://support.office.com/article/Distribution-groups-E8BA58A8-FAB2-4AAF-8AA1-2A304052D2DE) ai criteri di supervisione. Questo è per le relazioni utente/chat da 1 a 1 o 1-a-molti.

- **Origini di terze parti:** È possibile controllare le comunicazioni provenienti da origini di terze parti (come da Facebook o DropBox) per i dati importati nelle cassette postali di Office 365 nell'organizzazione. [Informazioni su come importare i dati di terze parti in Office 365](archiving-third-party-data.md).

Le comunicazioni acquisite su queste piattaforme vengono conservate per sette anni per ogni criterio per impostazione predefinita, anche se gli utenti lasciano l'organizzazione e la loro cassetta postale viene eliminata.

### <a name="policy-settings"></a>Impostazioni dei criteri

#### <a name="direction"></a>Direction

Per impostazione predefinita, la **direzione è** la condizione viene visualizzata e non può essere rimossa. Le impostazioni relative alla direzione di comunicazione in un criterio vengono scelte singolarmente o contemporaneamente:

- In **ingresso**: è possibile scegliere in **ingresso** per esaminare le comunicazioni inviate **alle** persone scelte per la supervisione **da** parte di utenti non inclusi nel criterio.
- In **uscita**: è possibile scegliere in **uscita** se si desidera esaminare le comunicazioni inviate **dalle** persone che si è scelto di controllare **per** gli utenti non inclusi nel criterio.
- **Internal**: è possibile scegliere **Internal** per esaminare le comunicazioni inviate **tra** le persone identificate nel criterio.

#### <a name="sensitive-information-types"></a>Tipi di informazioni riservate

È possibile includere i tipi di informazioni riservate nell'ambito del criterio di supervisione. I tipi di informazioni riservate sono tipi di dati predefiniti o personalizzati che consentono di identificare e proteggere i numeri di carta di credito, i numeri di conto corrente bancario, i numeri di passaporto e altro ancora. Come parte del servizio di [prevenzione della perdita di dati (DLP)](data-loss-prevention-policies.md)di Office 365, la configurazione delle informazioni riservate può utilizzare modelli, prossimità dei caratteri, livelli di sicurezza e persino tipi di dati personalizzati per identificare e contrassegnare il contenuto che potrebbe essere sensibile. I tipi di informazioni riservate predefinite sono:

- Finanze
- Medicale e sanitarie
- Privacy
- Tipo di informazioni personalizzato

Per ulteriori informazioni sui dettagli riservati e sui modelli inclusi nei tipi predefiniti, vedere [quali tipi di informazioni riservate devono essere cercate](what-the-sensitive-information-types-look-for.md).

#### <a name="custom-keyword-dictionaries"></a>Dizionari per parole chiave personalizzate

Configure custom keyword Dictionary (o lessici) per fornire una gestione semplice delle parole chiave specifiche per l'organizzazione o l'industria. I dizionari per parole chiave supportano fino a 100.000 termini per dizionario. Se necessario, è possibile applicare più dizionari di parole chiave personalizzati a un singolo criterio oppure disporre di un solo dizionario di parole chiave per ogni criterio. Questi dizionari sono assegnati a un criterio di supervisione e possono essere provenienti da un file, ad esempio un elenco con estensione CSV o txt, oppure da un elenco che può essere [importato nel centro conformità](create-a-keyword-dictionary.md).

#### <a name="offensive-language"></a>Lingua offensiva

Monitorare i messaggi di posta elettronica inviati o ricevuti nell'organizzazione per la lingua offensiva. Il modello utilizza una combinazione di apprendimento automatico, intelligenza artificiale e parole chiave per identificare la lingua nei messaggi di posta elettronica suscettibili di violare i criteri di anti-molestia e bullismo. Il modello di lingua offensiva attualmente supporta le parole chiave in inglese e monitora il corpo dei messaggi di posta elettronica.

>[!NOTE]
>Creare un [criterio di prevenzione della perdita dei dati](create-test-tune-dlp-policy.md) con un [dizionario di parole chiave personalizzato](create-a-keyword-dictionary.md) dei termini bloccati se è necessario eseguire le operazioni seguenti:
>
>- monitorare le comunicazioni di Microsoft teams nell'organizzazione per la lingua offensiva
>- Impedisci o blocca la lingua offensiva nelle comunicazioni nell'organizzazione

Tenere presente che il modello non fornisce un elenco esaustivo di lingua offensiva. Inoltre, gli standard linguistici e culturali cambiano continuamente e, alla luce di queste realtà, Microsoft si riserva il diritto di aggiornare il modello a sua discrezione. Anche se il modello può aiutare l'organizzazione a monitorare il linguaggio offensivo, il modello non è destinato a fornire il solo mezzo di monitoraggio o di indirizzamento di tale lingua da parte dell'organizzazione. La propria organizzazione, non Microsoft, resta responsabile di tutte le decisioni relative al monitoraggio e al blocco del linguaggio offensivo.

Il modello di lingua offensivo monitora la posta elettronica per i sentimenti associati ai tipi di lingua seguenti:

|**Tipo**|**Descrizione**|
|:-----|:-----|
| **Bestemmie** | Espressioni che imbarazzano la maggior parte delle persone. |
| **Legature** | Espressioni che esprimono pregiudizio nei confronti di gruppi specifici (ad esempio, razza, etnia, orientamento sessuale, disabilità). |
| **Insulti** | Espressioni che provocano, condannano, ridicolizzano, o che potrebbero causare rabbia o violenza. |
| **Espressioni mascherate** | Espressioni per le quali il significato o la pronuncia è identica a quella di un altro termine più offensivo. |

#### <a name="conditional-settings"></a>Impostazioni condizionali
<a name="ConditionalSettings"> </a>

Le condizioni che scegli per il criterio si applicano alle comunicazioni sia dalla posta elettronica sia dalle fonti di terze parti nell'organizzazione (come da Facebook o DropBox).

Nella tabella seguente vengono illustrate altre informazioni su ogni condizione.
  
|**Condizione**|**Come utilizzare questa condizione**|
|:-----|:-----|
| **Il messaggio viene ricevuto da uno di questi domini** <br><br> **Il messaggio non viene ricevuto da nessuno di questi domini** | Applicare il criterio per includere o escludere domini o indirizzi di posta elettronica specifici nei messaggi ricevuti. Immettere ogni dominio o indirizzo di posta elettronica e separare più domini o indirizzi di posta elettronica con una virgola. Ogni dominio o indirizzo di posta elettronica immesso viene applicato separatamente, solo un dominio o un indirizzo di posta elettronica devono essere applicati per il criterio da applicare al messaggio. <br><br> Se si desidera monitorare tutti i messaggi di posta elettronica provenienti da un dominio specifico ma si desidera escludere il messaggio che non è necessario esaminare (newsletter, annunci e così via), è necessario configurare la condizione che **non sia stato ricevuto da nessuno di questi domini** la condizione che escluda l'indirizzo di posta elettronica (ad esempio "newsletter@contoso.com"). |
| **Il messaggio viene inviato a uno di questi domini** <br><br> **Il messaggio non viene inviato a uno di questi domini** | Applicare il criterio per includere o escludere domini o indirizzi di posta elettronica specifici nei messaggi inviati. Immettere ogni dominio o indirizzo di posta elettronica e separare più domini o indirizzi di posta elettronica con una virgola. Ogni dominio o indirizzo di posta elettronica viene applicato separatamente, per applicare il criterio al messaggio è necessario un solo dominio o un indirizzo di posta elettronica. <br><br> Se si desidera monitorare tutti i messaggi di posta elettronica inviati a un dominio specifico, ma si desidera escludere quelli inviati che non richiedono la revisione, è necessario configurare due condizioni: <br> -Un **messaggio viene inviato a una qualsiasi di queste condizioni dei domini** che definisce il dominio ("contoso.com") e <br> -Un **messaggio non viene inviato a una di queste condizioni di dominio** che escluda l'indirizzo di posta elettronica ("subscriptions@contoso.com"). |
| **Il messaggio è classificato con una qualsiasi di queste etichette** <br><br> **Il messaggio non è classificato con nessuna di queste etichette** | Per applicare il criterio quando determinate etichette di conservazione sono incluse o escluse in un messaggio. Le etichette di conservazione devono essere configurate separatamente e le etichette configurate vengono scelte come parte di questa condizione. Ogni etichetta scelta viene applicata separatamente (è necessario applicare solo una di queste etichette per il criterio da applicare al messaggio). Per ulteriori informazioni sulla configurazione delle etichette di conservazione, vedere [Overview of retention labels](labels.md).|
| **Il messaggio contiene una o più delle seguenti parole** <br><br> **Il messaggio contiene nessuna di queste parole** | Per applicare il criterio quando determinate parole o frasi sono incluse o escluse in un messaggio, immettere ogni parola o frase e separare con una virgola. Ogni parola immessa viene applicata separatamente (è necessario applicare solo una parola per il criterio da applicare al messaggio). Per ulteriori informazioni sull'immissione di parole o frasi, vedere la sezione successiva che [corrisponde a parole e frasi a messaggi di posta elettronica o allegati](supervision-policies.md#Matchwords).|
| **L'allegato contiene una o più delle seguenti parole** <br><br> **L'allegato contiene nessuna di queste parole** | Per applicare il criterio quando determinate parole o frasi sono incluse o escluse in un allegato del messaggio (ad esempio un documento di Word), immettere ogni parola o frase e separare con una virgola. Ogni parola immessa viene applicata separatamente (è necessario applicare solo una parola per il criterio da applicare all'allegato). Per ulteriori informazioni sull'immissione di parole o frasi, vedere la sezione successiva che [corrisponde a parole e frasi a messaggi di posta elettronica o allegati](supervision-policies.md#Matchwords).|
| **Attachment è uno qualsiasi di questi tipi di file** <br><br> **Attachment è nessuno di questi tipi di file** | Per controllare le comunicazioni che includono o escludono tipi specifici di allegati, immettere le estensioni di file, ad esempio. exe o. pdf. Se si desidera includere o escludere più estensioni di file, immetterle su righe separate. Per applicare il criterio, è necessario che sia presente una sola estensione per gli allegati.|
| **La dimensione del messaggio è superiore a** <br><br> **La dimensione del messaggio non è maggiore di** | Per esaminare i messaggi in base a una determinata dimensione, utilizzare queste condizioni per specificare le dimensioni massime o minime che un messaggio può avere prima che sia soggetto a revisione. Ad esempio, se si specifica che **la dimensione del messaggio è maggiore di** \> **1,0 MB**, tutti i messaggi che sono 1,01 MB e superiori sono soggetti a revisione. Per questa condizione è possibile scegliere byte, kilobyte, megabyte o gigabyte.|
| **L'allegato è più grande di** <br><br> **L'allegato non è più grande di** | Per esaminare i messaggi in base alle dimensioni degli allegati, specificare le dimensioni massime o minime che un allegato può avere prima che il messaggio e i suoi allegati siano soggetti a revisione. Ad esempio, se si specifica **Attachment è maggiore di** \> **2,0 MB**, tutti i messaggi con allegati 2,01 MB e oltre sono soggetti a revisione. Per questa condizione è possibile scegliere byte, kilobyte, megabyte o gigabyte.|
   
##### <a name="matching-words-and-phrases-to-emails-or-attachments"></a>Corrispondenza di parole e frasi a messaggi di posta elettronica o allegati
<a name="Matchwords"></a> Ogni parola immessa e separata con una virgola viene applicata separatamente (è necessario applicare solo una parola per la condizione di criteri da applicare al messaggio di posta elettronica o all'allegato). Ad esempio, usiamo la condizione, il **messaggio contiene una di queste parole**, con le parole chiave "Banker" e "insider trading" separati da una virgola (banchiere, insider trading). Il criterio si applica a tutti i messaggi che includono la parola "Banker" o la frase "insider trading". Per applicare questa condizione di criteri, è necessario che si verifichi solo una di queste parole o frasi. Le parole del messaggio o dell'allegato devono corrispondere esattamente a quelle immesse.

Per analizzare i messaggi di posta elettronica e gli allegati per le stesse parole chiave, creare un [criterio di prevenzione della perdita di dati](create-test-tune-dlp-policy.md) con un dizionario di parole [chiave personalizzato](create-a-keyword-dictionary.md) per i termini che si desidera monitorare. Questa configurazione dei criteri identifica le parole chiave definite che vengono visualizzate nel messaggio di posta elettronica **o** nell'allegato di posta elettronica. L'utilizzo delle impostazioni standard dei criteri condizionali (*messaggio contiene una di queste parole* e un *allegato contiene una di queste parole*) per identificare i termini nei messaggi e negli allegati richiede che i termini siano presenti **sia** nel messaggio che nell'allegato.
  
##### <a name="enter-multiple-conditions"></a>Immettere più condizioni

Se si immettono più condizioni, Office 365 utilizza tutte le condizioni insieme per determinare quando applicare il criterio agli elementi di comunicazione. Quando si configurano più condizioni, è necessario che vengano soddisfatte tutte le condizioni per applicare il criterio, a meno che non si immetta un'eccezione. Ad esempio, è necessario un criterio che si applica se un messaggio contiene la parola "Trade" ed è maggiore di 2 MB. Tuttavia, se il messaggio contiene anche le parole "approvate da Contoso Financial", il criterio non dovrebbe essere applicato. Pertanto, in questo caso, le tre condizioni sarebbero le seguenti:
  
- Il **messaggio contiene una di queste parole**, con le parole chiave "Trade"

- La **dimensione del messaggio è maggiore di**, con il valore 2 MB

- Il **messaggio contiene nessuna di queste parole**, con le parole chiave "approvate dal team finanziario contoso"

#### <a name="review-percentage"></a>Percentuale di Revisione

Se si desidera ridurre la quantità di contenuto da rivedere, è possibile specificare una percentuale di tutte le comunicazioni regolate da un criterio di supervisione. Viene selezionato un campione casuale di contenuto in tempo reale rispetto alla percentuale totale di contenuto che corrisponde alle condizioni dei criteri scelte. Se si desidera che i revisori rivedano tutti gli elementi, è possibile immettere **100%** in un criterio di supervisione.

## <a name="monitor--manage"></a>Monitorare & gestire

È facile monitorare i risultati dei criteri di supervisione e applicare un tag di risoluzione. È possibile visualizzare rapidamente:

- Lo stato degli elementi recensiti
- Utenti e gruppi sotto sorveglianza
- Utenti e gruppi designati come revisori

### <a name="supervision-policy-dashboard"></a>Dashboard criteri di supervisione

Utilizzare il dashboard dei criteri di supervisione per gestire i risultati dei criteri di supervisione e risolvere gli elementi in sospeso. Questo dashboard consente ai revisori di visualizzare gli elementi che devono essere esaminati, agire su un elemento ed esaminare i risultati degli elementi precedentemente esaminati e risolti per ogni criterio di supervisione. È possibile accedere al dashboard dei criteri di supervisione nel centro conformità **al momento** > dell' > **apertura**del*criterio personalizzato*.

#### <a name="dashboard-home"></a>Home dashboard

Nella **Home** page del dashboard sono disponibili diverse sezioni che consentono di agire rapidamente sui criteri di supervisione. Qui è possibile:

- Esaminare rapidamente le evidenziazioni in sospeso e risolte per la settimana
- Visualizzare un elenco degli utenti controllati e dei gruppi controllati per il criterio selezionato
- Visualizzare un elenco di revisori e team di revisione per il criterio selezionato
- Vedere quali piattaforme di comunicazione dispongono di contenuto sotto controllo per il criterio

#### <a name="review-tab"></a>Scheda Revisione

La scheda **Revisione** è la posizione in cui i revisori classificano e risolvono gli elementi identificati dal criterio selezionato. Qui è possibile:

- Filtrare in base agli elementi in sospeso, conformi, non conformi e discutibili.
- Contrassegnare un singolo elemento come conforme, non conforme o discutibile. È inoltre possibile registrare un commento con l'elemento per chiarire l'azione di tagging eseguita.
- I tag di massa più elementi sono conformi, non conformi o discutibili. È inoltre possibile registrare un commento con più elementi per chiarire l'azione di tagging eseguita.
- Visualizzare la cronologia del tagging per un singolo elemento. Include gli utenti che hanno risolto l'elemento, la data e l'ora dell'azione, il tag di risoluzione e tutti i commenti inclusi.
- Riclassificare gli elementi precedentemente recensiti come conformi, non conformi o discutibili. È inoltre possibile registrare un commento con elementi singoli o multipli per chiarire l'azione di riclassificazione eseguita.

#### <a name="resolved-items-tab"></a>Scheda elementi risolti

La scheda **elementi risolti** è la posizione in cui i revisori possono visualizzare tutti gli elementi precedentemente risolti per il criterio selezionato. Qui è possibile:

- Visualizzare e ordinare rapidamente l'oggetto, il mittente e la data degli elementi risolti
- Visualizzare la classificazione e la cronologia dei commenti di qualsiasi elemento selezionato

## <a name="reports"></a>Report

Utilizzare i rapporti di supervisione per visualizzare l'attività di revisione a livello di criteri e revisori. Per ogni criterio, è anche possibile visualizzare le statistiche in tempo reale sullo stato corrente dell'attività di revisione. È possibile utilizzare i report di supervisione per:
  
- Verificare che i criteri funzionino come previsto.
- Informazioni su quante comunicazioni devono essere riesaminate.
- Informazioni su quante comunicazioni non sono conformi e quali passano la revisione. Queste informazioni consentono di decidere se ottimizzare i criteri o modificare il numero di revisori.

### <a name="view-the-supervision-report"></a>Visualizzare il report di supervisione

1. Accedere al [centro conformità](https://compliance.microsoft.com) con le credenziali per un account di amministratore con le autorizzazioni per visualizzare i report di supervisione.
2. Accedere al **Dashboard** dei **report** \> o alla **supervisione** per visualizzare il widget report di supervisione per un riepilogo delle attività correnti sui criteri di supervisione.
3. Selezionare il widget di **supervisione** per aprire la pagina del rapporto dettagliato.

>[!NOTE]
>Se non si è in grado di accedere alla pagina **report** , verificare di essere membri del gruppo di ruolo revisione di supervisione, come descritto in [rendere la supervisione disponibile nell'organizzazione](configure-supervision-policies.md). L'inclusione in questo gruppo di ruoli consente di creare e gestire i criteri di supervisione ed eseguire il report.
  
### <a name="how-to-use-the-report"></a>Come utilizzare il report

Questo rapporto elenca ogni criterio e il numero di comunicazioni in ogni fase del processo di revisione. Utilizzare il report per:
  
- Visualizzare i dati per tutti i criteri o specifici.
- Visualizzare i dati raggruppati per tipo di tag, revisore o tipo di messaggio.
- Esportare i dati in un file CSV in base alla data di attività, ai criteri e all'attività reviewer.
- Filtrare i dati in base a data attività, tipo di tag, revisore e tipo di messaggio.

Di seguito viene indicata una scomposizione dei valori visualizzati nella colonna **tipo di tag** .
  
|**Tipo di tag**|**Cosa significa**|
|:-----|:-----|
| **Non Recensito** | Il numero di messaggi di posta elettronica non ancora recensiti. Questi messaggi di posta elettronica attendono la revisione nel dashboard di supervisione di Office 365.
| **Conformi** | Il numero di messaggi di posta elettronica esaminati e contrassegnati come conformi. Questi messaggi richiedono ancora una soluzione. |
| **Ambigui** | Il numero di messaggi di posta elettronica esaminati e contrassegnati come discutibili. Funge da contrassegno per gli altri revisori per controllare se un messaggio di posta elettronica deve essere esaminato per la conformità. Questi messaggi richiedono ancora una soluzione. |
| **Non conforme (attivo)** | Il numero di messaggi di posta elettronica non conformi che i revisori stanno attualmente esaminando. |
| **Non conforme (risolto)** | Il numero di messaggi di posta elettronica non conformi che i revisori hanno esaminato e risolto. |
| **Hit Policy** | Numero totale (giornaliero) dei messaggi provenienti da origini dati di Exchange, teams e di terze parti che corrispondono a una o più condizioni definite in un criterio di supervisione |
| **Competenza** | Numero totale (giornaliero) dei messaggi provenienti da origini dati di Exchange, teams e di terze parti analizzati da un criterio di supervisione |
| **Risolto** | Il numero totale di messaggi provenienti da origini dati di Exchange, teams e di terze parti classificate come **risolte**|

>[!NOTE]
>I criteri di supervisione devono essere sottoposto a provisioning prima che vengano visualizzati nei report. Se i criteri vengono eliminati, i dati cronologici vengono ancora visualizzati. Tuttavia, sono indicati come "criteri non esistenti" e la funzione di **esportazione** non è disponibile.

## <a name="audit"></a>Audit

In alcuni casi, è necessario fornire informazioni ai revisori dei conti normativi o di conformità per dimostrare la supervisione delle attività e delle comunicazioni degli impiegati. Può trattarsi di un riepilogo di tutte le attività di supervisione associate a un criterio definito o in qualsiasi momento in cui vengono modificati i criteri di supervisione. I criteri di supervisione sono basati su percorsi di controllo integrati per una completa preparazione per i controlli interni o esterni. La cronologia di controllo dettagliata di tutte le azioni monitorate dai criteri di supervisione fornisce la prova delle procedure di supervisione.

Le attività dei criteri di supervisione seguenti sono controllate e rese disponibili nei registri di controllo di Office 365:

|**Attività**|**Comandi associati**|
|:-----|:-----|
| **Creare un criterio** | [New-SupervisoryReviewPolicyV2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-supervisoryreviewpolicyv2) <br> [New-SupervisoryReviewRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-supervisoryreviewrule) |
| **Modificare un criterio** | [Set-SupervisoryReviewPolicyV2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-supervisoryreviewpolicyv2) <br> [Set-SupervisoryReviewRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-supervisoryreviewrule) |
| **Eliminare un criterio** | [Remove-SupervisoryReviewPolicyV2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/remove-supervisoryreviewpolicyv2) |

Visualizzare le attività di controllo nel log di controllo unificato o con il cmdlet [Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-unifiedauditlog) PowerShell.

Ad esempio, nell'esempio seguente vengono restituite le attività per tutte le attività di revisione di supervisione (criteri e regole) ed elenchi di informazioni dettagliate per ogni:

```PowerShell
Search-UnifiedAuditLog -StartDate 3/1/2019 -EndDate ([System.DateTime]::Now) -RecordType DataGovernance -ResultSize 5000 | Where-Object {$_.Operations -like "*SupervisoryReview*"}  | fl CreationDate,Operations,UserIds,AuditData
```

In questo esempio vengono restituite le attività di aggiornamento per i criteri di conformità della comunicazione:

```PowerShell
Search-UnifiedAuditLog -StartDate $startDate -EndDate $endDate -Operations SupervisionPolicyCreated,SupervisionPolicyUpdated,SupervisionPolicyDeletedAuditData
```

Oltre alle informazioni fornite nei report e nei registri di supervisione, è anche possibile utilizzare il cmdlet [Get-SupervisoryReviewActivity](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewactivity?view=exchange-ps) di PowerShell per restituire un elenco dettagliato completo di tutte le attività dei criteri di supervisione.

## <a name="ready-to-get-started"></a>Pronti per iniziare?

Per configurare i criteri di supervisione per l'organizzazione, vedere [configurare i criteri di supervisione](configure-supervision-policies.md).
