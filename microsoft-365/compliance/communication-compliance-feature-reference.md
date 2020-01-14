---
title: Informazioni di riferimento sulla funzionalità di conformità delle comunicazioni (anteprima)
description: Riferimento alla funzionalità per la conformità delle comunicazioni in Microsoft 365. Informazioni dettagliate e specifiche per ogni componente di funzionalità.
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
ms.openlocfilehash: 886ede889e1843c7f7e94b89aeffb89d59a0120a
ms.sourcegitcommit: 39bd4be7e8846770f060b5dd7d895fc8040b18f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/14/2020
ms.locfileid: "41111850"
---
# <a name="communication-compliance-feature-reference-preview"></a>Informazioni di riferimento sulla funzionalità di conformità delle comunicazioni (anteprima)

## <a name="policies"></a>Generali

È possibile creare criteri di conformità della comunicazione per le organizzazioni Microsoft 365 nel centro conformità di Microsoft 365. Se si dispone di un'organizzazione di Office 365, verranno [configurati i criteri di supervisione](configure-supervision-policies.md) nel centro sicurezza & conformità di Office 365. I criteri di conformità della comunicazione definiscono le comunicazioni e gli utenti soggetti a revisione nell'organizzazione, definiscono le condizioni personalizzate che devono soddisfare le comunicazioni e specificano chi deve eseguire le revisioni. Gli utenti inclusi nel gruppo di ruoli **amministratore revisione di supervisione** possono impostare i criteri e tutti coloro a cui è assegnato questo ruolo possono accedere alla pagina **conformità comunicazione** nel centro conformità di Microsoft 365. Se necessario, è possibile esportare la cronologia delle modifiche apportate a un criterio a un file con estensione CSV che include anche lo stato degli avvisi in sospeso, degli elementi escalation e degli elementi risolti. I criteri non possono essere rinominati e possono essere eliminati quando non sono più necessari.

>[!NOTE]
>I criteri di supervisione creati nel centro sicurezza e conformità di Office 365 per le sottoscrizioni di Office 365 non possono eseguire la migrazione a Microsoft 365. Se si esegue la migrazione da un abbonamento a Office 365 a un abbonamento a Microsoft 365, sarà necessario creare nuovi criteri di conformità per la comunicazione per sostituire il criterio di supervisione esistente.

## <a name="policy-templates"></a>Modelli dei criteri

I modelli di criteri sono impostazioni predefinite che è possibile utilizzare per creare rapidamente criteri per risolvere scenari di conformità comuni. Ognuno di questi modelli presenta differenze nelle condizioni e nell'ambito e tutti i modelli utilizzano gli stessi tipi di segnali di analisi. È possibile scegliere tra i modelli di criteri seguenti:

|**Area**|**Modello di criteri**|**Dettagli**|
|:-----|:-----|:-----|
| **Lingua offensiva e anti-molestia** | Monitorare le comunicazioni per la lingua offensiva | -Locations: Exchange, teams, Skype for business <br> -Direction: in ingresso, in uscita, interno <br> -Percentuale di verifica: 100% <br> -Conditions: classificatore di lingua offensivo |
| **Informazioni riservate** | Monitorare le comunicazioni per informazioni riservate | -Locations: Exchange, teams, Skype for business <br> -Direction: in ingresso, in uscita, interno <br> -Percentuale di verifica: 10% <br> -Conditions: informazioni riservate, modelli e tipi di contenuto esterno alla casella, opzione dizionario personalizzato, allegati di dimensioni superiori a 1 MB |
| **Conformità alle normative** | Monitorare le comunicazioni per informazioni relative alla conformità alle normative finanziarie | -Locations: Exchange, teams, Skype for business <br> -Direction: in ingresso, in uscita <br> -Percentuale di verifica: 10% <br> -Conditions: opzione dizionario personalizzato, allegati di dimensioni superiori a 1 MB |

## <a name="supervised-users"></a>Utenti controllati

Prima di iniziare a utilizzare la conformità alla comunicazione, è necessario determinare chi ha bisogno delle proprie comunicazioni. Nei criteri, gli indirizzi di posta elettronica degli utenti identificano gli utenti o i gruppi di persone da sorvegliare. Alcuni esempi di questi gruppi sono i gruppi di Office 365, le liste di distribuzione basate su Exchange e i canali Microsoft teams. È inoltre possibile escludere utenti o gruppi specifici dall'analisi con un gruppo di esclusione specifico o un elenco di gruppi.

>[!IMPORTANT]
>Gli utenti interessati dai criteri di conformità della comunicazione devono avere una licenza di conformità Microsoft 365 E5, una licenza di Office 365 Enterprise E3 con il componente aggiuntivo per la conformità avanzato oppure essere inclusi in un abbonamento a Office 365 Enterprise E5. Se non si dispone di un piano Enterprise E5 esistente e si vuole provare la conformità alla comunicazione, è possibile [iscriversi per una versione di valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).

## <a name="reviewers"></a>Revisori

Quando si crea un criterio di conformità della comunicazione, è necessario determinare chi esamina i messaggi degli utenti controllati. Nei criteri, gli indirizzi di posta elettronica degli utenti identificano gli utenti o i gruppi di persone per esaminare le comunicazioni sorvegliate. Tutti i revisori devono disporre di cassette postali ospitate in Exchange Online e devono essere assegnati ai ruoli Gestione e **Revisione** dei **casi** .

## <a name="groups-for-supervised-users-and-reviewers"></a>Gruppi per gli utenti e i revisori controllati

Per semplificare l'installazione, creare gruppi per gli utenti che hanno bisogno di una revisione delle comunicazioni e di gruppi per gli utenti che esaminano tali comunicazioni. Se si utilizzano i gruppi, potrebbero essere necessari diversi. Ad esempio, se si desidera eseguire l'analisi delle comunicazioni tra due gruppi distinti di persone oppure se si desidera specificare un gruppo non supervisionato.

Quando si seleziona un gruppo di Office 365 per gli utenti controllati, il criterio analizza il contenuto della cassetta postale di Office 365 condivisa e dei canali Microsoft teams associati al gruppo. Quando si seleziona una lista di distribuzione, il criterio analizza le singole cassette postali degli utenti.

## <a name="supported-communication-types"></a>Tipi di comunicazione supportati

Con i criteri di conformità della comunicazione, è possibile scegliere di analizzare i messaggi in una o più delle seguenti piattaforme di comunicazione come gruppo o come origini autonome. Le comunicazioni acquisite su queste piattaforme vengono conservate per sette anni per ogni criterio per impostazione predefinita, anche se gli utenti lasciano l'organizzazione e le relative cassette postali vengono eliminate.

- **Microsoft teams**: è possibile analizzare le comunicazioni chat e gli allegati associati in entrambi i canali di Microsoft teams pubblici e privati e nelle chat individuali. Chat teams la corrispondenza delle condizioni dei criteri di conformità della comunicazione viene elaborata una volta ogni 24 ore e quindi è disponibile nei report di conformità della comunicazione. Utilizzare le seguenti configurazioni di gestione dei gruppi per controllare le chat utente e le comunicazioni dei canali nei team:

    - **Per le comunicazioni di chat dei team:** Assegnare singoli utenti o assegnare un [gruppo di distribuzione](https://support.office.com/article/Distribution-groups-E8BA58A8-FAB2-4AAF-8AA1-2A304052D2DE) ai criteri di conformità della comunicazione. Questo è per le relazioni utente/chat uno-a-uno o uno-a-molti.
    - **Per le comunicazioni di canale dei team:** Assegnare a tutti i gruppi di Microsoft Team Channel o Office 365 che si desidera analizzare che contengano un utente specifico per i criteri di conformità della comunicazione. Se si aggiunge lo stesso utente ad altri canali Microsoft teams o gruppi di Office 365, accertarsi di aggiungere questi nuovi canali e gruppi ai criteri di conformità della comunicazione.

- **Posta elettronica di Exchange**: le cassette postali ospitate in Exchange Online come parte dell'abbonamento a Microsoft 365 o Office 365 sono tutte idonee per l'analisi dei messaggi. Messaggi di posta elettronica e allegati corrispondenti alle condizioni dei criteri di conformità della comunicazione sono immediatamente disponibili nei report di conformità comunicazione. I tipi di allegati supportati per la conformità alla comunicazione sono gli stessi dei [tipi di file supportati per le ispezioni del contenuto delle regole del flusso di posta di Exchange](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection).

- **Skype for business online**: è possibile controllare le comunicazioni di chat e gli allegati associati in Skype for business online. Chat di Skype for business online che soddisfano le condizioni dei criteri di conformità della comunicazione vengono elaborate una volta ogni 24 ore e quindi sono disponibili nei rapporti di conformità della comunicazione. Le conversazioni di chat sorvegliate vengono provenienti da [precedenti conversazioni salvate in Skype for business online](https://support.office.com/article/Find-a-previous-Skype-for-Business-conversation-18892eba-5f18-4281-8c87-fd48bd72e6a2).  Utilizzare la configurazione di gestione dei gruppi seguente per supervisionare le comunicazioni della chat utente in Skype for business online:

    - **Per le comunicazioni di chat di Skype for business online**: assegnare singoli utenti o assegnare un [gruppo di distribuzione](https://support.office.com/article/Distribution-groups-E8BA58A8-FAB2-4AAF-8AA1-2A304052D2DE) ai criteri di conformità della comunicazione. Questo è per le relazioni utente/chat uno-a-uno o uno-a-molti.

- **Origini**di terze parti: è possibile eseguire l'analisi delle comunicazioni da origini di terze parti per i dati importati nelle cassette postali nell'organizzazione Microsoft 365. I connettori supportano le risorse di terze parti seguenti:

    - [Bloomberg istantaneo](archive-instant-bloomberg-data.md)
    - [Facebook](archive-facebook-data-with-sample-connector.md)
    - [LinkedIn](archive-linkedin-data.md)
    - SAP SuccessFactors
    - [Twitter](archive-twitter-data-with-sample-connector.md)
    - [Connettore dati personalizzato](archiving-third-party-data.md)

Prima di poter assegnare il connettore a un criterio di conformità della comunicazione, è necessario configurare un connettore di terze parti per l'organizzazione Microsoft 365. La sezione origini di terze **parti** della procedura guidata per la conformità dei criteri di comunicazione Visualizza solo i connettori di terze parti attualmente configurati.

## <a name="policy-settings"></a>Impostazioni dei criteri

### <a name="users"></a>Utenti

È possibile selezionare **tutti gli utenti** o definire utenti specifici in un criterio di conformità della comunicazione. Se si seleziona **tutti gli utenti** , il criterio viene applicato a tutti gli utenti e a tutti i gruppi a cui è incluso un utente come membro. La definizione di utenti specifici applica il criterio agli utenti definiti e a tutti i gruppi a cui gli utenti definiti sono inclusi come membri.

### <a name="direction"></a>Direction

Per impostazione predefinita, la **direzione è** la condizione viene visualizzata e non può essere rimossa. Le impostazioni relative alla direzione di comunicazione in un criterio vengono scelte singolarmente o contemporaneamente:

- In **ingresso**: è possibile scegliere in **ingresso** per esaminare le comunicazioni inviate **alle** persone scelte per la supervisione.
- In **uscita**: è possibile scegliere in **uscita** se si desidera esaminare le comunicazioni inviate **dalle** persone scelte per la supervisione.
- **Internal**: è possibile scegliere **Internal** per esaminare le comunicazioni inviate **tra** le persone identificate nel criterio.

### <a name="sensitive-information-types"></a>Tipi di informazioni sensibili

È possibile includere i tipi di informazioni riservate nell'ambito del criterio di conformità della comunicazione. I tipi di informazioni riservate sono tipi di dati predefiniti o personalizzati che consentono di identificare e proteggere i numeri di carta di credito, i numeri di conto corrente bancario, i numeri di passaporto e altro ancora. Nell'ambito del servizio di [prevenzione della perdita di dati (DLP)](data-loss-prevention-policies.md)di Office 365, la configurazione delle informazioni riservate può utilizzare modelli, prossimità dei caratteri, livelli di sicurezza e persino tipi di dati personalizzati per identificare e contrassegnare il contenuto che potrebbe essere sensibile. I tipi di informazioni riservate predefinite sono:

- Finanze
- Medicale e sanitarie
- Privacy
- Tipo di informazioni personalizzato

Per ulteriori informazioni sui dettagli riservati e sui modelli inclusi nei tipi predefiniti, vedere [quali tipi di informazioni riservate devono essere cercate](what-the-sensitive-information-types-look-for.md).

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

Le condizioni che scegli per il criterio si applicano alle comunicazioni sia dalla posta elettronica sia dalle fonti di terze parti nell'organizzazione (come da Facebook o DropBox).

Nella tabella seguente vengono illustrate altre informazioni su ogni condizione.
  
|**Condizione**|**Come utilizzare questa condizione**|
|:-----|:-----|
| **Il contenuto corrisponde a uno di questi classificatori** | Applicare il criterio quando i classificatori sono inclusi o esclusi in un messaggio. Alcuni classificatori sono già definiti nel tenant e i classificatori personalizzati devono essere configurati separatamente prima di essere disponibili per questa condizione. Un solo classificatore può essere definito come una condizione in un criterio. Per ulteriori informazioni sulla configurazione dei classificatori, vedere [classificatori](classifier-getting-started-with.md). |
| **Content contiene uno qualsiasi di questi tipi di informazioni riservate** | Applicare al criterio quando i tipi di informazioni riservate sono inclusi o esclusi in un messaggio. Alcuni classificatori sono già definiti nel tenant e i classificatori personalizzati possono essere configurati separatamente o come parte del processo di assegnazione delle condizioni. Ogni tipo di informazioni riservate scelto viene applicato separatamente e solo uno di questi tipi di informazioni riservate deve richiedere il criterio da applicare al messaggio. Per ulteriori informazioni sui tipi di informazioni riservate personalizzate, vedere Custom definitive [Information types](custom-sensitive-info-types.md). |
| **Il messaggio viene ricevuto da uno di questi domini**  <br><br> **Il messaggio non viene ricevuto da nessuno di questi domini** | Applicare il criterio per includere o escludere domini o indirizzi di posta elettronica specifici nei messaggi ricevuti. Immettere ogni dominio o indirizzo di posta elettronica e separare più domini o indirizzi di posta elettronica con una virgola. Ogni dominio o indirizzo di posta elettronica immesso viene applicato separatamente, solo un dominio o un indirizzo di posta elettronica devono essere applicati per il criterio da applicare al messaggio. <br><br> Se si desidera eseguire l'analisi di tutti i messaggi di posta elettronica da un dominio specifico, ma si desidera escludere il messaggio che non è necessario esaminare (newsletter, annunci e così via), è necessario configurare un **messaggi non ricevuti da una delle seguenti condizioni dei domini** che escludono l'indirizzo di posta elettronica (ad esempio "newsletter@contoso.com"). |
| **Il messaggio viene inviato a uno di questi domini**  <br><br> **Il messaggio non viene inviato a uno di questi domini** | Applicare il criterio per includere o escludere domini o indirizzi di posta elettronica specifici nei messaggi inviati. Immettere ogni dominio o indirizzo di posta elettronica e separare più domini o indirizzi di posta elettronica con una virgola. Ogni dominio o indirizzo di posta elettronica viene applicato separatamente, per applicare il criterio al messaggio è necessario un solo dominio o un indirizzo di posta elettronica. <br><br> Se si desidera eseguire l'analisi di tutti i messaggi di posta elettronica inviati a un dominio specifico, ma si desidera escludere il messaggio inviato che non è necessario rivedere, è necessario configurare due condizioni: <br> -Un **messaggio viene inviato a una qualsiasi di queste condizioni dei domini** che definisce il dominio ("contoso.com") e <br> -Un **messaggio non viene inviato a una di queste condizioni di dominio** che escluda l'indirizzo di posta elettronica ("subscriptions@contoso.com"). |
| **Il messaggio è classificato con una qualsiasi di queste etichette**  <br><br> **Il messaggio non è classificato con nessuna di queste etichette** | Per applicare il criterio quando determinate etichette di conservazione sono incluse o escluse in un messaggio. Le etichette di conservazione devono essere configurate separatamente e le etichette configurate vengono scelte come parte di questa condizione. Ogni etichetta scelta viene applicata separatamente (è necessario applicare solo una di queste etichette per il criterio da applicare al messaggio). Per ulteriori informazioni sulla configurazione delle etichette di conservazione, vedere [Overview of retention labels](labels.md).|
| **Il messaggio contiene una o più delle seguenti parole**  <br><br> **Il messaggio contiene nessuna di queste parole** | Per applicare il criterio quando determinate parole o frasi sono incluse o escluse in un messaggio, immettere ogni parola o frase e separare con una virgola. Ogni parola immessa viene applicata separatamente (è necessario applicare solo una parola per il criterio da applicare al messaggio). Per ulteriori informazioni sull'immissione di parole o frasi, vedere la sezione successiva che [corrisponde a parole e frasi a messaggi di posta elettronica o allegati](communication-compliance-feature-reference.md#Matchwords).|
| **L'allegato contiene una o più delle seguenti parole**  <br><br> **L'allegato contiene nessuna di queste parole** | Per applicare il criterio quando determinate parole o frasi sono incluse o escluse in un allegato del messaggio (ad esempio un documento di Word), immettere ogni parola o frase e separare con una virgola. Ogni parola immessa viene applicata separatamente (è necessario applicare solo una parola per il criterio da applicare all'allegato). Per ulteriori informazioni sull'immissione di parole o frasi, vedere la sezione successiva che [corrisponde a parole e frasi a messaggi di posta elettronica o allegati](communication-compliance-feature-reference.md#Matchwords).|
| **Attachment è uno qualsiasi di questi tipi di file**  <br><br> **Attachment è nessuno di questi tipi di file** | Per controllare le comunicazioni che includono o escludono tipi specifici di allegati, immettere le estensioni di file, ad esempio. exe o. pdf. Se si desidera includere o escludere più estensioni di file, immetterle su righe separate. Per applicare il criterio, è necessario che sia presente una sola estensione per gli allegati.|
| **La dimensione del messaggio è superiore a**  <br><br> **La dimensione del messaggio non è maggiore di** | Per esaminare i messaggi in base a una determinata dimensione, utilizzare queste condizioni per specificare le dimensioni massime o minime che un messaggio può avere prima che sia soggetto a revisione. Ad esempio, se si specifica che **la dimensione del messaggio è maggiore di** \> **1,0 MB**, tutti i messaggi che sono 1,01 MB e superiori sono soggetti a revisione. Per questa condizione è possibile scegliere byte, kilobyte, megabyte o gigabyte.|
| **L'allegato è più grande di**  <br><br> **L'allegato non è più grande di** | Per esaminare i messaggi in base alle dimensioni degli allegati, specificare le dimensioni massime o minime che un allegato può avere prima che il messaggio e i suoi allegati siano soggetti a revisione. Ad esempio, se si specifica **Attachment è maggiore di** \> **2,0 MB**, tutti i messaggi con allegati 2,01 MB e oltre sono soggetti a revisione. Per questa condizione è possibile scegliere byte, kilobyte, megabyte o gigabyte.|
   
#### <a name="matching-words-and-phrases-to-emails-or-attachments"></a>Corrispondenza di parole e frasi a messaggi di posta elettronica o allegati
<a name="Matchwords"> </a>

Ogni parola immessa e separata con una virgola viene applicata separatamente (è necessario applicare solo una parola per la condizione di criteri da applicare al messaggio di posta elettronica o all'allegato). Ad esempio, usiamo la condizione, il **messaggio contiene una di queste parole**, con le parole chiave "Banker" e "insider trading" separati da una virgola (banchiere, insider trading). Il criterio si applica a tutti i messaggi che includono la parola "Banker" o la frase "insider trading". Per applicare questa condizione di criteri, è necessario che si verifichi solo una di queste parole o frasi. Le parole del messaggio o dell'allegato devono corrispondere esattamente a quelle immesse.

Per analizzare i messaggi di posta elettronica e gli allegati per le stesse parole chiave, creare un [criterio di prevenzione della perdita di dati](create-test-tune-dlp-policy.md) con un dizionario di parole [chiave personalizzato](create-a-keyword-dictionary.md) per i termini che si desidera analizzare nei messaggi. Questa configurazione dei criteri identifica le parole chiave definite che vengono visualizzate nel messaggio di posta elettronica **o** nell'allegato di posta elettronica. Utilizzando le impostazioni standard dei criteri condizionali (il*messaggio contiene una di queste parole* e l' *allegato contiene una di queste parole*) per identificare i termini nei messaggi e negli allegati è necessario che i termini siano presenti **sia** nel messaggio che nell'allegato.
  
#### <a name="enter-multiple-conditions"></a>Immettere più condizioni

Se si immettono più condizioni, Microsoft 365 utilizza tutte le condizioni insieme per determinare quando applicare il criterio di supervisione agli elementi di comunicazione. Quando si configurano più condizioni, è necessario che vengano soddisfatte tutte le condizioni per applicare il criterio, a meno che non si immetta un'eccezione. Ad esempio, è necessario un criterio che si applica se un messaggio contiene la parola "Trade" ed è maggiore di 2 MB. Tuttavia, se il messaggio contiene anche le parole "approvate da Contoso Financial", il criterio non deve essere applicato. In questo esempio, le tre condizioni verrebbero definite nel modo seguente:
  
- Il **messaggio contiene una di queste parole**, con le parole chiave "Trade"
- La **dimensione del messaggio è maggiore di**, con il valore 2 MB
- Il **messaggio contiene nessuna di queste parole**, con le parole chiave "approvate dal team finanziario contoso"

### <a name="review-percentage"></a>Percentuale di Revisione

Se si desidera ridurre la quantità di contenuto da rivedere, è possibile specificare una percentuale di tutte le comunicazioni regolate da un criterio di supervisione. Viene selezionato un campione casuale di contenuto in tempo reale rispetto alla percentuale totale di contenuto che corrisponde alle condizioni dei criteri scelte. Se si desidera che i revisori rivedano tutti gli elementi, è possibile configurare il **100%** in un criterio di conformità della comunicazione.

## <a name="notices"></a>Avvisi

È possibile creare modelli di avviso se si desidera inviare agli utenti una notifica di promemoria tramite posta elettronica per le corrispondenze di criteri nell'ambito del processo di risoluzione dei problemi. Gli avvisi possono essere inviati solo all'indirizzo di posta elettronica dipendente associato alla corrispondenza dei criteri che ha generato l'avviso specifico per la correzione. Quando si seleziona un modello di avviso da applicare a una violazione dei criteri nell'ambito del flusso di lavoro di correzione, è possibile scegliere di accettare i valori del campo definiti nel modello o sovrascrivere i campi in base alle esigenze.

I modelli di avviso sono modelli di posta elettronica personalizzati in cui è possibile definire i campi del messaggio seguenti:

|**Campo**|**Obbligatorio**| **Dettagli** |
|:-----|:-----|:-----|
|**Nome del modello** | Sì | Nome descrittivo per il modello di avviso che è possibile selezionare nel flusso di lavoro Notify durante la correzione, supporta i caratteri di testo. |
| **Indirizzo mittente** | Sì | L'indirizzo di uno o più utenti o gruppi che invia il messaggio al dipendente con una corrispondenza di criteri, selezionata da Active Directory per l'abbonamento. |
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
| **Classe Item** | L'origine del messaggio in base al tipo di messaggio, alla posta elettronica, a Microsoft Team Chat, Bloonmberg e così via. |
| **Domini destinatario** | Il dominio in cui è stato inviato il messaggio. Si tratta in genere del dominio di sottoscrizione Microsoft 365 per impostazione predefinita. |
| **Destinatario** | L'utente a cui è stato inviato il messaggio. |
| **Mittente** | La persona che ha inviato il messaggio. |
| **Dominio del mittente** | Il dominio che ha inviato il messaggio. |
| **Dimensioni** | Le dimensioni del messaggio in KB. |
| **Subject/title** | L'oggetto del messaggio o il titolo della chat. |
| **Tag** | Tag assegnati a un messaggio, che può essere *discutibile*, *conforme*o *non conforme*. |
| **Escalation a** | Il nome utente della persona inclusa come parte di un'azione di escalation dei messaggi. |

## <a name="alert-policies"></a>Criteri di avviso

Dopo aver configurato un criterio, viene creato automaticamente un criterio di avviso corrispondente e vengono generati avvisi per i messaggi che soddisfano le condizioni definite nel criterio. Per impostazione predefinita, tutti i criteri corrispondenti ai trigger di avviso sono assegnati a un livello di gravità medio nel criterio di avviso associato. Gli avvisi vengono generati per un criterio di conformità della comunicazione dopo che il livello di soglia dei trigger di aggregazione viene soddisfatto nel criterio di avviso di Office 365 associato.

Per i criteri di conformità della comunicazione, i valori dei criteri di avviso seguenti sono configurati per impostazione predefinita:

|**Trigger di criteri di avviso**|**Valore predefinito**|
|:-----|:-----|
| Aggregazione | Aggregazione semplice |
| Soglia | 4 attività |
| Finestra | 60 minuti |

>[!Note]
>Le impostazioni dei trigger di soglia dei criteri di avviso per le attività supportano un valore minimo di 3 o superiore per i criteri di conformità della comunicazione.

È possibile modificare le impostazioni predefinite per i trigger per il numero di attività, il periodo per le attività e per gli utenti specifici nei criteri di avviso nella pagina **criteri di avviso** nel centro sicurezza & conformità di Office 365.

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

In alcuni casi, è necessario fornire informazioni ai revisori dei conti normativi o di conformità per dimostrare la supervisione delle attività e delle comunicazioni degli impiegati. Può trattarsi di un riepilogo di tutte le attività associate a un criterio organizzativo definito o in qualsiasi momento in cui cambia il criterio di conformità della comunicazione. I criteri di conformità della comunicazione hanno percorsi di controllo incorporati per una preparazione completa per i controlli interni o esterni. Le cronologie di controllo dettagliate di ogni azione di creazione, modifica ed eliminazione vengono acquisite dai criteri di comunicazione per fornire la prova delle procedure di supervisione.

>[!Important]
>È necessario che il controllo sia abilitato per l'organizzazione prima che vengano registrati gli eventi di conformità della comunicazione. Per abilitare il controllo, vedere [Enable Auditing for your Communication Compliance Policies](communication-compliance-configure.md#step-6-enable-auditing-for-your-communication-compliance-policies-optional).

Per visualizzare le attività relative ai criteri di conformità della comunicazione, selezionare il controllo **Esporta attività di revisione** nella pagina principale per tutti i criteri. In questo modo viene generato un file di controllo nel formato CSV che contiene le informazioni seguenti:

|**Campo**|**Dettagli**|
|:-----|:-----|
| **CreationDate** | Quando l'attività è stata eseguita in un criterio. |
| **UserIds** | L'utente che ha eseguito l'attività in un criterio. |
| **Operations** | Le operazioni eseguite sul criterio. |
| **AuditData** | Si tratta del campo principale di origine dati per tutte le attività dei criteri. Tutte le attività vengono registrate e separate da delimitatori di virgole. |

È inoltre possibile visualizzare le attività di controllo nel log di controllo unificato o con il cmdlet di PowerShell [Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-unifiedauditlog) .

Ad esempio, nell'esempio seguente vengono restituite le attività per tutte le attività di revisione di supervisione (criteri e regole) ed elenchi di informazioni dettagliate per ogni:

```PowerShell
Search-UnifiedAuditLog -StartDate 3/1/2019 -EndDate ([System.DateTime]::Now) -RecordType DataGovernance -ResultSize 5000 | Where-Object {$_.Operations -like "*SupervisoryReview*"}  | fl CreationDate,Operations,UserIds,AuditData
```

In questo esempio vengono restituite le attività di aggiornamento per i criteri di conformità della comunicazione:

```PowerShell
Search-UnifiedAuditLog -StartDate $startDate -EndDate $endDate -Operations SupervisionPolicyCreated,SupervisionPolicyUpdated,SupervisionPolicyDeletedAuditData
```

## <a name="ready-to-get-started"></a>Pronti per iniziare?

Per configurare la conformità di comunicazione per l'organizzazione Microsoft 365, vedere [Configure Communication Compliance for your microsoft 365 Organization (Preview)](communication-compliance-configure.md).
