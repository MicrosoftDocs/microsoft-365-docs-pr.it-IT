---
title: Informazioni di riferimento sulla prevenzione della perdita di dati
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: low
ms.collection:
- M365-security-compliance
- SPO_Content
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: materiale di riferimento per la prevenzione della perdita di dati
ms.openlocfilehash: 7e8494c0199d62951e7b5f01bb1b65e90e8584f2
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878161"
---
# <a name="data-loss-prevention-reference"></a>Informazioni di riferimento sulla prevenzione della perdita di dati
 
> [!IMPORTANT]
> Questo è l'argomento di riferimento non è più la risorsa principale per Microsoft 365 di prevenzione della perdita dei dati (DLP). Il set di contenuti DLP viene aggiornato e ristrutturato. Gli argomenti trattati in questo articolo verranno trattati in articoli nuovi e aggiornati. Per ulteriori informazioni sulla prevenzione della perdita dei dati, vedere [Informazioni sulla prevenzione della perdita dei dati.](dlp-learn-about-dlp.md)

<!-- this topic needs to be split into smaller, more coherent ones. It is confusing as it is. -->
<!-- move this note to a more appropriate place, no topic should start with a note -->
> [!NOTE]
> Le funzionalità di prevenzione della perdita dei dati sono state aggiunte di recente ai messaggi di chat e canali di Microsoft Teams per gli utenti con licenza di Office 365 Advanced Compliance, che è disponibile come opzione indipendente e incluso in Office 365 E5 e Microsoft 365 E5 Compliance. Per altre informazioni sui requisiti di licenza, vedere [Linee guida per le licenze dei servizi a livello di tenant di Microsoft 365](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance).



<!-- MOVED TO LEARN ABOUT To comply with business standards and industry regulations, organizations must protect sensitive information and prevent its inadvertent disclosure. Sensitive information can include financial data or personally identifiable information (PII) such as credit card numbers, social security numbers, or health records. With a data loss prevention (DLP) policy in the Office 365 Security &amp; Compliance Center, you can identify, monitor, and automatically protect sensitive information across Office 365.
  
With a DLP policy, you can:
  
- **Identify sensitive information across many locations, such as Exchange Online, SharePoint Online, OneDrive for Business, and Microsoft Teams.**
    
    For example, you can identify any document containing a credit card number that's stored in any OneDrive for Business site, or you can monitor just the OneDrive sites of specific people.
    
- **Prevent the accidental sharing of sensitive information**. 
    
    For example, you can identify any document or email containing a health record that's shared with people outside your organization, and then automatically block access to that document or block the email from being sent.
    
- **Monitor and protect sensitive information in the desktop versions of Excel, PowerPoint, and Word.**
    
    Just like in Exchange Online, SharePoint Online, and OneDrive for Business, these Office desktop programs include the same capabilities to identify sensitive information and apply DLP policies. DLP provides continuous monitoring when people share content in these Office programs.
    
- **Help users learn how to stay compliant without interrupting their workflow.**
    
    You can educate your users about DLP policies and help them remain compliant without blocking their work. For example, if a user tries to share a document containing sensitive information, a DLP policy can both send them an email notification and show them a policy tip in the context of the document library that allows them to override the policy if they have a business justification. The same policy tips also appear in Outlook on the web, Outlook, Excel, PowerPoint, and Word.
    
- **View DLP alerts and reports showing content that matches your organization’s DLP policies.**
    
    To view alerts and metadata related to your DLP policies you can use the [DLP Alerts Management Dashboard](dlp-configure-view-alerts-policies.md). You can also view policy match reports to assess how your organization is complying with a DLP policy. If a DLP policy allows users to override a policy tip and report a false positive, you can also view what users have reported

-->    
## <a name="create-and-manage-dlp-policies"></a>Creare e gestire i criteri DLP

È possibile creare e gestire i criteri di prevenzione della perdita dei dati nella pagina Prevenzione della perdita di dati nel Centro conformità e sicurezza di Microsoft 365.
  
![Pagina Prevenzione della perdita di dati nel Centro sicurezza e conformità di Office 365](../media/943fd01c-d7aa-43a9-846d-0561321a405e.png)
  
<!-- MOVED TO LEARN ABOUT ## What a DLP policy contains

A DLP policy contains a few basic things:
  
- Where to protect the content: **locations** such as Exchange Online, SharePoint Online, and OneDrive for Business sites, as well as Microsoft Teams chat and channel messages. 
    
- When and how to protect the content by enforcing **rules** comprised of: 
    
  - **Conditions** the content must match before the rule is enforced. For example, a rule might be configured to look only for content containing Social Security numbers that's been shared with people outside your organization. 
    
  - **Actions** that you want the rule to take automatically when content matching the conditions is found. For example, a rule might be configured to block access to a document and send both the user and compliance officer an email notification. -->
    
È possibile usare una regola per rispettare uno specifico requisito di protezione e quindi usare i criteri di prevenzione della perdita dei dati per raggruppare i requisiti comuni, ad esempio tutte le regole necessarie per la conformità a una specifica normativa.
  
È possibile che si disponga di un criterio DLP che consente di rilevare la presenza di informazioni soggette ai moduli di conformità Health Insurance Portability and Accountability Act (HIPAA). Questo criterio di prevenzione della perdita dei dati consente di proteggere i dati HIPAA (il cosa) in tutti i siti di SharePoint Online e in tutti quelli di OneDrive for Business (il dove) rilevando i documenti che contengono informazioni riservate condivise con utenti esterni all'organizzazione (le condizioni), bloccando quindi l'accesso a tali documenti e inviando una notifica (le azioni). Questi requisiti vengono archiviati come singole regole e raggruppati come criteri di prevenzione della perdita dei dati per semplificare la gestione e la creazione di report.
  
![Diagramma che mostra criterio di prevenzione della perita dei dati contenente posizioni e regole](../media/c006860c-2d00-42cb-aaa4-5b5638d139f7.png)
  
<!-- MOVED TO LEARN ABOUT ### Locations

DLP policies are applied to sensitive items across Microsoft 365 locations and can be further scoped as detailed in this table.


|Location | Include/exclude by|
|---------|---------|
|Exchange email| distribution groups|
|SharePoint sites |sites |
|OneDrive accounts |accounts |
|Teams chat and channel messages |accounts |
|Windows 10 devices |user or group |
|Microsoft Cloud App Security |instance |
 -->

Se si sceglie di includere gruppi di distribuzione specifici in Exchange, i criteri DLP verranno applicati solo ai membri di quel gruppo. Analogamente, escludendo un gruppo di distribuzione si escluderanno tutti i membri di quel gruppo di distribuzione dalla valutazione dei criteri. È possibile scegliere di applicare un criterio ai membri delle liste di distribuzione, dei gruppi di distribuzione dinamici e dei gruppi di sicurezza. Una politica DLP non può contenere più di 50 inclusioni ed esclusioni.

Se si sceglie di includere o escludere specifici siti di SharePoint, i criteri di prevenzione della perdita dei dati possono contenere non più di 100 inclusioni ed esclusioni di questo tipo. Anche se questi limiti esistono, è importante sapere che possono essere superati applicando criteri a livello di organizzazione o validi per intere posizioni.

Se si sceglie di includere o escludere account o gruppi specifici di OneDrive, un criterio di prevenzione della perdita di dati potrà contenere non oltre 100 account utente o 50 gruppi di inclusione o esclusione.

> [!NOTE]
> OneDrive l'ambito dei criteri aziendali con account utente o gruppi è in anteprima pubblica. 
  
### <a name="rules"></a>Regole

> [!NOTE]
> Il comportamento predefinito dei criteri di prevenzione della perdita dei dati, quando non è configurato alcun avviso, non prevede alcun avviso o trigger. Questo comportamento si applica solo ai tipi di informazioni predefiniti. Per i tipi di informazioni personalizzati, il sistema visualizza una avviso anche se nei criteri non è definita alcuna azione.

Le regole costituiscono gli elementi che consentono di applicare i requisiti aziendali al contenuto dell'organizzazione. Un criterio include una o più regole e ciascuna di queste è composta da condizioni e azioni. Per ogni regola, le azioni vengono eseguite automaticamente, non appena vengono soddisfatte le condizioni. Le regole vengono eseguite in modo sequenziale, iniziando con quella più prioritaria in ogni criterio.
  
Una regola contiene anche opzioni per informare gli utenti (con suggerimenti per i criteri e notifiche tramite posta elettronica) e gli amministratori (con report sugli eventi tramite posta elettronica) che per il contenuto è stata individuata una corrispondenza alla regola.
  
Ecco i componenti di una regola, spiegati di seguito.
  
![Sezioni dell'editor regole di prevenzione della perdita dei dati](../media/1859d504-b9c2-45ed-961b-a0092251acc2.png)
  
#### <a name="conditions"></a>Condizioni

Le condizioni sono importanti perché determinano i tipi di informazioni desiderati e il momento in cui eseguire un'azione. Ad esempio, si può scegliere di ignorare i contenuti che includono numeri di passaporto, nel caso in cui il contenuto contenga oltre 10 di questi numeri e sia condiviso con utenti esterni all'organizzazione.
  
Le condizioni si focalizzano sul **contenuto**, come i tipi di informazioni riservate desiderati, e sul **contesto**, come l'utente con cui viene condiviso il documento. È possibile usare le condizioni per assegnare azioni diverse a livelli di rischio diversi. Ad esempio, i contenuti riservati condivisi all'interno dell'organizzazione potrebbero essere caratterizzati da un livello di rischio inferiore rispetto ai contenuti riservati condivisi con utenti esterni all'organizzazione. 
  
![Elenco che mostra le condizioni disponibili per i criteri di prevenzione della perdita dei dati](../media/0fa43f90-d007-4506-ae93-43e8424fe103.png)
  
Le condizioni disponibili a questo punto consentono di determinare se:
  
- Il contenuto include un tipo di informazioni riservate.
    
- Il contenuto include un'etichetta. Per altre informazioni, vedere la sezione seguente: [Uso di un'etichetta di conservazione come condizione nei criteri di prevenzione della perdita dei dati](#using-a-retention-label-as-a-condition-in-a-dlp-policy).
    
- Il contenuto viene condiviso con utenti esterni o interni all'organizzazione.

  > [!NOTE]
  > Gli utenti che hanno account non guest nel tenant di Active Directory o di Azure Active Directory di un'organizzazione host sono considerati come utenti interni all'organizzazione.
    
#### <a name="types-of-sensitive-information"></a>Tipi di informazioni riservate

I criteri di prevenzione della perdita dei dati aiutano a proteggere le informazioni riservate definite come **tipo di informazioni riservate**. Microsoft 365 include le definizioni pronte per l'uso di molti tipi comuni di informazioni riservate in diverse aree geografiche, ad esempio numeri di carta di credito, di conto corrente bancario, di carta di identità e di passaporto. 
  
![Elenco dei tipi di informazioni riservate disponibili](../media/3eaa9911-bc94-44be-902f-363dbf3b07fe.png)
  
Quando un criterio di prevenzione della perdita dei dati cerca un tipo di informazione riservata (ad esempio un numero di carta di credito), non effettua soltanto la ricerca di un codice a 16 cifre. Ogni tipo di informazioni riservate viene definito e rilevato utilizzando una combinazione dei seguenti elementi:
  
- Parole chiave.
    
- Funzioni interne per convalidare i chesksum o la composizione.
    
- Valutazione di espressioni regolari per trovare corrispondenze di schemi.
    
- Altre analisi del contenuto.
    
In questo modo, il rilevamento di prevenzione della perdita dei dati raggiunge un livello superiore di accuratezza riducendo il numero di falsi positivi che possono interrompere il lavoro degli utenti.
  
#### <a name="actions"></a>Azioni

Quando un contenuto corrisponde a una condizione di una regola, è possibile applicare le azioni per proteggere automaticamente il contenuto.
  
![Elenco delle azioni disponibili dei criteri di prevenzione della perdita dei dati](../media/8aef17fc-1e99-4ac7-adfc-0f2c9c1a0697.png)
  
Con le azioni ora disponibili è possibile:
  
- **Limitare l'accesso al contenuto** In base alle proprie esigenze, è possibile limitare l'accesso al contenuto in tre modi:

  1. Limitare l'accesso al contenuto per tutti.
  2. Limitare l'accesso al contenuto per le persone esterne all'organizzazione.
  3. Limitare l'accesso a "chiunque abbia il collegamento".

  Per i contenuti dei siti, ciò significa che le autorizzazioni per il documento sono limitate per tutti tranne che per l'amministratore della raccolta siti principale, il proprietario del documento e la persona che lo ha modificato per ultima. Queste persone possono rimuovere le informazioni riservate dal documento o eseguire altri azioni correttive. Quando il documento è conforme, vengono automaticamente ripristinate le autorizzazioni originali. Se l'accesso è bloccato, il documento viene visualizzato con una speciale icona di suggerimento per i criteri nella raccolta del sito. 
    
  ![Suggerimento per i criteri che segnala che l’accesso al documento è bloccato](../media/b6cefed3-d212-43d7-8534-4b92b26ebd50.png)
  
  Per il contenuto dei messaggi di posta elettronica, questa azione blocca l'invio del messaggio. In base alla configurazione della regola di prevenzione della perdita dei dati, il mittente vedrà un rapporto di mancato recapito oppure, se la regola usa una notifica, un suggerimento per i criteri e/o una notifica tramite posta elettronica.
    
  ![Avviso che i destinatari non autorizzati devono essere rimossi dal messaggio](../media/302f9994-912d-41e7-861f-8a4539b3c285.png)
  
#### <a name="user-notifications-and-user-overrides"></a>Notifiche utente e criteri ignorati dall’utente

Grazie alle notifiche e ai criteri ignorati è possibile informare gli utenti sui criteri di prevenzione della perdita dei dati e aiutarli a rimanere conformi senza compromettere la loro produttività. Se ad esempio un utente prova a condividere un documento contenente informazioni riservate, è possibile inviargli una notifica tramite posta elettronica e mostrargli un suggerimento per i criteri nel contesto della raccolta documenti, che gli consente di ignorare i criteri se giustificato da motivi aziendali.
  
![Sezione Notifiche utente e Criteri ignorati dagli utenti dell'editor regole di prevenzione della perdita dei dati](../media/37b560d4-6e4e-489e-9134-d4b9daf60296.png)
  
Il messaggio di posta elettronica può informare l'utente che ha inviato, condiviso o modificato per ultimo il contenuto e, per il contenuto dei siti, l'amministratore della raccolta siti principale e il proprietario del documento. Inoltre, è possibile aggiungere o rimuovere a piacimento persone a cui inviare la notifica tramite posta elettronica.
  
Oltre a inviare una notifica tramite posta elettronica, una notifica utente mostra un suggerimento per i criteri:
  
- In Outlook e Outlook sul web.
    
- Per documenti in un sito di SharePoint Online o OneDrive for Business.
    
- In Excel, PowerPoint e Word, se il documento è archiviato in un sito incluso nei criteri di prevenzione della perdita dei dati.
    
Nella notifica di posta elettronica e nel suggerimento per i criteri viene spiegata la causa del conflitto tra il contenuto e un criterio di prevenzione della perdita dei dati. Si può anche scegliere di fare in modo che la notifica tramite posta elettronica e il suggerimento per i criteri consentano di ignorare la regola segnalando un falso positivo o fornendo una giustificazione aziendale. In questo modo è possibile informare gli utenti sui criteri di prevenzione della perdita dei dati e applicarli senza comprometterne la produttività. Anche le informazioni sui criteri ignorati e sui falsi positivi vengono registrate per la creazione di report (vedere di seguito per informazioni sui report) e vengono incluse nei report degli eventi (sezione successiva) in modo che il responsabile della conformità possa esaminarle regolarmente.
  
Ecco l'aspetto di un suggerimento per i criteri in un account di OneDrive for Business.
  
![Suggerimento per i criteri per un documento in un account di OneDrive](../media/f9834d35-94f0-4511-8555-0fe69855ce6d.png)

 Per ulteriori informazioni sulle notifiche all'utente e i suggerimenti per i criteri nei criteri DLP, vedere [Utilizzare notifiche e suggerimenti per i criteri](use-notifications-and-policy-tips.md).

#### <a name="alerts-and-incident-reports"></a>Avvisi e report degli incidenti

Quando viene trovata una corrispondenza con una regola, è possibile inviare un avviso tramite posta elettronica al responsabile della conformità (o a chiunque si desideri) con i relativi dettagli. Questo avviso tramite posta elettronica includerà un collegamento del [Dashboard di gestione degli avvisi DLP](dlp-configure-view-alerts-policies.md), tramite cui il responsabile della conformità potrà visualizzare i dettagli dell'avviso e degli eventi. Il dashboard contiene dettagli dell'evento che ha attivato l'avviso, insieme alle informazioni sul criterio di prevenzione della perdita di dati e sui contenuti riservati rilevati.

Inoltre, è possibile inviare un report degli incidenti con i dettagli dell'evento. Il report include informazioni sull'elemento con cui è stata trovata una corrispondenza, sull'effettivo contenuto che ha soddisfatto la regola, oltre al nome dell'ultima persona che ha modificato il contenuto. Per i messaggi di posta elettronica, il report include anche il messaggio originale che corrisponde ai criteri di prevenzione della perdita dei dati, sotto forma di allegato.

> [!div class="mx-imgBorder"]
> ![Pagina per la configurazione di rapporti operazioni non consentite](../media/Alerts-and-incident-report.png)

La prevenzione della perdita dei dati esegue la scansione della posta elettronica in modo diverso dagli elementi in SharePoint Online o OneDrive for Business. In SharePoint Online e OneDrive for Business, la prevenzione della perdita dei dati analizza gli elementi esistenti e quelli nuovi e genera un avviso e un report degli incidenti ogni volta in cui viene trovata una corrispondenza. In Exchange Online, la prevenzione della perdita dei dati esegue la scansione di nuovi messaggi di posta elettronica e genera un report in caso di corrispondenza dei criteri. La prevenzione della perdita dei dati ***non*** esegue la scansione o la corrispondenza di elementi di posta elettronica esistenti in precedenza archiviati in una cassetta postale o in un archivio.
  
## <a name="grouping-and-logical-operators"></a>Raggruppamento e operatori logici

Spesso i criteri di prevenzione della perdita dei dati includono un requisito semplice, ad esempio identificare tutti i contenuti che contengono un numero di codice fiscale. In altri casi, tuttavia, i criteri di prevenzione della perdita dei dati potrebbero dover identificare dati definiti in modo meno preciso.
  
Ad esempio, per identificare il contenuto soggetto all'Health Insurance Act (HIPAA), è necessario cercare:
  
- Contenuto che include tipi specifici di informazioni riservate, ad esempio un numero di previdenza sociale statunitense o un numero DEA (Drug Enforcement Agency).
    
    E
    
- Contenuto più difficile da identificare, ad esempio comunicazioni sul trattamento di un paziente o descrizioni dei servizi medicali forniti. L'identificazione di questo contenuto richiede la corrispondenza delle parole chiave rispetto a elenchi di parole chiave di dimensioni molto grandi, ad esempio l'elenco International Classification of Diseases (ICD-9-CM o ICD-10-CM).
    
È possibile identificare facilmente questi dati definiti in modo meno preciso usando il raggruppamento e gli operatori logici (E, O). Quando si creano criteri di prevenzione della perdita dei dati, è possibile:
  
- Raggruppare tipi di informazioni riservate.
    
- Scegliere l'operatore logico tra i tipi di informazioni riservate all'interno di un gruppo e tra i gruppi.
    
### <a name="choosing-the-operator-within-a-group"></a>Scelta dell'operatore all'interno di un gruppo

All'interno di un gruppo è possibile scegliere se è necessario che sia soddisfatta una o tutte le condizioni del gruppo perché il contenuto corrisponda alla regola.
  
![Gruppi con gli operatori all'interno dei gruppi](../media/6a12f1e8-112d-48ee-9a73-82b3dd0542e7.png)
  
### <a name="adding-a-group"></a>Aggiunta di un gruppo

È possibile aggiungere rapidamente un gruppo con proprie condizioni e un operatore all'interno.
  
![Pulsante Aggiungi gruppo](../media/5f72f292-d1f3-4f11-a911-a9f71e10abf6.png)
  
### <a name="choosing-the-operator-between-groups"></a>Scelta dell'operatore tra i gruppi

Tra i gruppi è possibile scegliere se è necessario che siano soddisfatte le condizioni di un solo gruppo o di tutti perché il contenuto corrisponda alla regola.
  
Ad esempio, il criterio predefinito **Stati Uniti - HIPAA** ha una regola che usa un operatore **E** tra i gruppi per identificare il contenuto che include: 
  
- dal gruppo **Identificatori di informazioni personali** (almeno un numero di previdenza sociale **O** un numero DEA) 
    
    **E**
    
- dal gruppo **Terminologia medica** (almeno una parola chiave ICD-9-CM **O** ICD-10-CM) 
    
![Gruppi con l'operatore tra i gruppi](../media/354aa77f-569c-4847-9dfe-605ee2bb28d1.png)
  
## <a name="the-priority-by-which-rules-are-processed"></a>Priorità in base alla quale vengono elaborate le regole

Quando si creano regole in un criterio, a ogni regola viene assegnata una priorità nell'ordine di creazione, ovvero la regola creata per prima avrà la priorità più alta, la regola creata per seconda avrà la seconda priorità e così via.

> [!div class="mx-imgBorder"]
> ![Regole in ordine di priorità](../media/dlp-rules-in-priority-order.png)
  
Dopo aver configurato più criteri di prevenzione della perdita dei dati, è possibile cambiare la priorità di uno o più criteri. Per farlo, selezionare un criterio, scegliere **Modifica criterio** e usare l'elenco **priorità** per specificare la priorità.

> [!div class="mx-imgBorder"]
> ![Impostare la priorità per un criterio](../media/dlp-set-policy-priority.png)

Quando il contenuto viene valutato a fronte delle regole, queste vengono elaborate in ordine di priorità. Se il contenuto corrisponde a più regole, le regole vengono elaborate in ordine di priorità e viene applicata l'azione più restrittiva. Ad esempio, se il contenuto corrisponde a tutte le regole seguenti, viene applicata la regola 3 perché è quella più restrittiva con la priorità più alta:
  
- Regola 1: solo notifica agli utenti
    
- Regola 2: notifica agli utenti, limita l'accesso e consente che gli utenti ignorino i criteri
    
- Regola 3: notifica agli utenti, limita l'accesso e non consente che gli utenti ignorino i criteri
    
- Regola 4: solo notifica agli utenti
    
- Regola 5: limita l'accesso
    
- Regola 6: notifica agli utenti, limita l'accesso e non consente che gli utenti ignorino i criteri
    
In questo esempio, le corrispondenze per tutte le regole vengono registrate nei log di controllo e visualizzate nei report di prevenzione della perdita dei dati, anche se viene applicata solo la regola più restrittiva.
  
Per informazioni sui suggerimenti per i criteri, tenere presente che:
  
- Viene visualizzato solo il suggerimento per i criteri della regola più restrittiva con la priorità più alta. Ad esempio, verrà visualizzato un suggerimento per i criteri di una regola che blocca l'accesso al contenuto rispetto a un suggerimento per i criteri di una regola che invia semplicemente una notifica. In questo modo, gli utenti evitano di dover leggere troppi suggerimenti per i criteri.
    
- 	Se i suggerimenti per i criteri nella regola più restrittiva permettono agli utenti di eseguire l'override della regola, l'override di questa regola comporta anche l'override di qualsiasi altra regola corrispondente al contenuto. 
    
## <a name="tuning-rules-to-make-them-easier-or-harder-to-match"></a>Ottimizzazione delle regole affinché siano più facili o difficili da soddisfare

Dopo la creazione e l'attivazione di specifici criteri di prevenzione della perdita dei dati, a volte si verificano questi problemi:
  
- Il contenuto che **non è** costituito da informazioni riservate e che soddisfa la regola è eccessivo. In altri termini, si verificano troppi falsi positivi. 
    
- Troppo poco contenuto che **è** costituito da informazioni riservate corrisponde alle regole. In altre parole, le azioni di protezione non vengono applicate alle informazioni riservate. 
    
Per risolvere questi problemi, è possibile ottimizzare le regole modificando il numero di istanze e l'accuratezza della corrispondenza per fare in modo che le regole siano più difficili o più facili da soddisfare. Ogni tipo di informazioni riservate usato in una regola include un numero di istanze e un'accuratezza di corrispondenza.
  
### <a name="instance-count"></a>Numero di istanze

Il numero di istanze indica semplicemente quante occorrenze di un determinato tipo di informazioni riservate devono essere presenti perché il contenuto soddisfi la regola. Ad esempio, il contenuto corrisponde alla regola riportata sotto se vengono identificati tra 1 e 9 numeri di passaporto univoci del Regno Unito o degli Stati Uniti.

> [!NOTE]
> Il conteggio delle istanze include solo le corrispondenze **univoche** per i tipi di informazioni riservate e parole chiave. Ad esempio, se un messaggio di posta elettronica contiene 10 occorrenze dello stesso numero di carta di credito, le 10 occorrenze vengono conteggiate come una singola istanza di un numero di carta di credito.
  
Per usare il numero di istanze per ottimizzare le regole, le indicazioni sono semplici:
  
- Per fare in modo che la regola sia più facile da soddisfare, ridurre il valore **min** e/o aumentare il valore **max**. È anche possibile impostare **max** su **qualsiasi** eliminando il valore numerico. 
    
- Per fare in modo che la regola sia più difficile da soddisfare, aumentare il valore **min**. 
    
In genere le azioni meno restrittive, come l'invio di notifiche all'utente, vengono usate in una regola con un numero di istanze inferiore, ad esempio 1-9. Le azioni più restrittive, come la limitazione dell'accesso al contenuto, senza consentire agli utenti di ignorare i criteri, vengono invece usate in una regola con un numero di istanze maggiore, ad esempio 10-qualsiasi.
  
![Numero di istanze nell'editor di regole](../media/e7ea3c12-72c5-4bb3-9590-c924c665e84d.png)
  
### <a name="match-accuracy"></a>Accuratezza della corrispondenza

Come illustrato in precedenza, ogni tipo di informazione riservata viene definito e rilevato usando una combinazione di tipi di prove. In genere, un tipo di informazioni riservate è definito da più combinazioni, dette criteri. Uno schema che richiede meno prove ha un'accuratezza della corrispondenza (o livello di probabilità) inferiore, che è invece maggiore per uno schema che richiede più prove. Per altre informazioni sugli schemi e sui livelli di probabilità usati da ogni tipo di informazioni sensibili, vedere [Definizioni delle entità tipo di informazioni sensibili](sensitive-information-type-entity-definitions.md).
  
Ad esempio, il tipo di informazioni riservate denominato Numero carta di credito è definito da due schemi:
  
- Uno schema con il 65% di probabilità che richiede:
    
  - Un numero nel formato di un numero di carta di credito.
    
  - Un numero che supera il checksum.
    
- Uno schema con l'85% di probabilità che richiede:
    
  - Un numero nel formato di un numero di carta di credito.
    
  - Un numero che supera il checksum.
    
  - Una parola chiave o una data di scadenza nel formato appropriato.
    
Questi livelli di probabilità (o accuratezza della corrispondenza) possono essere usati nelle regole. In genere le azioni meno restrittive, come l'invio di notifiche all'utente, vengono usate in una regola con un'accuratezza della corrispondenza inferiore. Le azioni più restrittive, come la limitazione dell'accesso al contenuto, senza consentire agli utenti di ignorare i criteri, vengono invece usate in una regola con un'accuratezza della corrispondenza maggiore.
  
È importante tenere presente che, quando nel contenuto viene rilevato un tipo specifico di informazioni riservate, come un numero di carta di credito, viene restituito solo un livello di probabilità:
  
- Se tutte le corrispondenze sono riferite a un singolo schema, viene restituito il relativo livello di probabilità.
    
- Se sono presenti corrispondenze per più schemi (ad esempio se esistono corrispondenze con due livelli di probabilità diversi), viene restituito un livello di probabilità superiore rispetto ai singoli schemi. Questa è la parte più complessa. Ad esempio, nel caso di una carta di credito, se sono soddisfatti gli schemi del 65% e dell'85%, il livello di probabilità restituito per quel tipo di informazioni riservate è superiore al 90% perché la presenza di più prove comporta una maggiore probabilità.
    
Quindi, se per le carte di credito si vogliono creare due regole che si escludono a vicenda, una per l'accuratezza della corrispondenza del 65% e una per l'accuratezza della corrispondenza dell'85%, gli intervalli di accuratezza della corrispondenza risultano come segue. La prima regola rileva solo le corrispondenze dello schema del 65%. La seconda regola rileva le corrispondenze con **almeno una** corrispondenza dell'85% e **potrebbe avere** altre corrispondenze con livello di probabilità inferiore. 
  
![Due regole con intervalli diversi per l'accuratezza della corrispondenza](../media/21bdfe36-7a91-4347-8098-11809a92f9a4.png)
  
Per questi motivi, le indicazioni per la creazione di regole con diverse accuratezze di corrispondenza sono:
  
- Il livello di probabilità inferiore usa generalmente lo stesso valore per **min** e **max**, anziché un intervallo. 
    
- Il livello di probabilità superiore è costituito in genere da un intervallo che inizia appena al di sopra del livello di probabilità inferiore e arriva a 100.
    
- Tutti i livelli di probabilità intermedi iniziano generalmente appena al di sopra del livello di probabilità inferiore e arrivano appena sotto il livello di probabilità superiore.
    
## <a name="using-a-retention-label-as-a-condition-in-a-dlp-policy"></a>Uso di un'etichetta di conservazione come condizione nei criteri di prevenzione della perdita dei dati

Quando si usa un'[etichetta di conservazione](retention.md#retention-labels) creata e pubblicata in precedenza come condizione nei criteri di prevenzione della perdita dei dati (DLP), è necessario tenere presente che:

- È necessario aver precedentemente creato e pubblicato l'etichetta di conservazione prima di usarla come condizione nei criteri DLP.
- La sincronizzazione delle etichette di conservazione pubblicate può richiedere da uno a sette giorni. Per altre informazioni, vedere [Quando le etichette di conservazione diventano disponibili per l'applicazione](create-apply-retention-labels.md#when-retention-labels-become-available-to-apply) per le etichette di conservazione pubblicate in un criterio di conservazione e [Tempo necessario per l'applicazione delle etichette di conservazione](apply-retention-labels-automatically.md#how-long-it-takes-for-retention-labels-to-take-effect) per le etichette di conservazione pubblicate automaticamente.
- L'uso di un'etichetta di conservazione in un criterio **è supportato solo per gli elementi di SharePoint e OneDrive***.

  ![Etichette come condizione](../media/5b1752b4-a129-4a88-b010-8dcf8a38bb09.png)

  È consigliabile usare un'etichetta di conservazione nei criteri DLP se sono presenti elementi in corso di conservazione ed eliminazione e si desidera applicare anche altri controlli, ad esempio:

  - È stata pubblicata un'etichetta di conservazione denominata **Anno di imposta 2018**, che una volta applicata ai documenti fiscali del 2018 archiviati in SharePoint, li conserva per 10 anni e poi li elimina. Inoltre, se si desidera che gli elementi non vengano condivisi all'esterno dell'organizzazione, è possibile usare i criteri DLP.

  > [!IMPORTANT]
  > Se si specifica un'etichetta di conservazione come condizione in un criterio di prevenzione della perdita dei dati (DLP) e si includono anche Exchange e/o Teams come posizione, si visualizzerà un messaggio di errore simile al seguente: **"La protezione dei contenuti etichettati nelle e-mail e nei messaggi di Teams non è supportata. Rimuovere l'etichetta seguente o disabilitare Exchange e Teams come posizione."** Questo perché il trasporto di Exchange non valuta i metadati dell'etichetta durante l'invio e il recapito dei messaggi. 

### <a name="using-a-sensitivity-label-as-a-condition-in-a-dlp-policy"></a>Uso di un'etichetta di riservatezza come condizione nei criteri di prevenzione della perdita dei dati

[Ulteriori informazioni](./dlp-sensitivity-label-as-condition.md) sull'uso dell'etichetta riservatezza come condizione nei criteri DLP.
  
### <a name="how-this-feature-relates-to-other-features"></a>Correlazione tra questa funzionalità e le altre

Al contenuto che include informazioni riservate possono essere applicate diverse funzionalità:
  
- Sia un'[etichetta di conservazione che un criterio di conservazione](retention.md) possono applicare azioni di **conservazione** a questo contenuto. 
    
- I criteri di prevenzione della perdita dei dati possono applicare azioni di **protezione** al contenuto. Inoltre, prima di applicare queste azioni, i criteri di prevenzione della perdita dei dati possono richiedere che siano soddisfatte altre condizioni oltre alla presenza di una specifica etichetta nel contenuto. 
    
![Diagramma delle funzionalità che possono applicarsi alle informazioni riservate](../media/dd410f97-a3a3-455c-a1e9-7ed8ae6893d6.png)
  
I criteri di prevenzione della perdita dei dati hanno capacità di rilevamento più complete rispetto a un'etichetta o ai criteri di conservazione applicati alle informazioni riservate. I criteri di prevenzione della perdita dei dati possono applicare azioni di protezione al contenuto con informazioni riservate. Se le informazioni riservate vengono rimosse, queste azioni di protezione vengono annullate alla successiva analisi del contenuto. Se invece viene applicato un criterio di conservazione o un'etichetta a un contenuto con informazioni riservate, si tratta di un'azione unica che non può essere annullata, anche se le informazioni riservate vengono rimosse.
  
Usando questa etichetta come condizione nei criteri di prevenzione della perdita dei dati è possibile applicare azioni di conservazione e di protezione al contenuto con l'etichetta specificata. Un contenuto con un'etichetta viene gestito esattamente come un contenuto con informazioni riservate: un'etichetta e un tipo di informazioni riservate rappresentano proprietà usate per classificare il contenuto, quindi è possibile applicare azioni al contenuto specificato.
  
![Diagramma dei criteri di prevenzione della perdita dei dati che usano un'etichetta come condizione](../media/4538fd8f-fb74-4743-bc22-a5de33adfebb.png)
  
## <a name="simple-settings-vs-advanced-settings"></a>Impostazioni semplici e avanzate

Quando si creano criteri di prevenzione della perdita dei dati, si può scegliere tra impostazioni semplici o avanzate:
  
- Le **Impostazioni semplici** consentono di creare facilmente il tipo più comune di criteri di prevenzione della perdita dei dati senza bisogno di usare l'editor per creare o modificare regole. 
    
- Le **Impostazioni avanzate** usano l'editor di regole per offrire il controllo completo su tutte le impostazioni dei criteri di prevenzione della perdita dei dati. 
    
In realtà, le impostazioni semplici e avanzate funzionano esattamente allo stesso modo, ovvero applicando regole costituite da condizioni e azioni, solo che con le impostazioni semplici l'editor di regole non viene visualizzato. Si tratta di un modo rapido per creare criteri di prevenzione della perdita dei dati.
  
### <a name="simple-settings"></a>Impostazioni semplici

Lo scenario di gran lunga più comune consiste nel creare criteri di prevenzione della perdita dei dati che consentano di proteggere il contenuto che include informazioni riservate dalla condivisione con utenti esterni all'organizzazione e intraprendere azioni correttive automatiche, ad esempio limitare l'accesso al contenuto, inviare notifiche agli utenti finali o agli amministratori e controllare l'evento per un'indagine successiva. I criteri di prevenzione della perdita dei dati vengono usati per evitare la divulgazione accidentale di informazioni riservate.
  
Per raggiungere facilmente questo scopo, quando si creano criteri di prevenzione della perdita dei dati è possibile scegliere **Usa le impostazioni semplici**. Queste impostazioni offrono tutto il necessario per implementare i criteri di prevenzione della perdita dei dati più comuni senza dover accedere all'editor di regole.
  
![Opzioni dei criteri di prevenzione della perdita dei dati per le impostazioni semplici e avanzate](../media/33c93824-ead5-43b6-9c3e-fd1630c92a7d.png)
  
### <a name="advanced-settings"></a>Impostazioni avanzate

Se è necessario creare criteri di prevenzione della perdita dei dati più personalizzati, scegliere **Usa le impostazioni avanzate**.
  
Le impostazioni avanzate presentano l'editor di regole, che offre il controllo completo su tutte le possibili opzioni, tra cui numero delle istanze e accuratezza della corrispondenza (livello di probabilità) per ogni regola.
  
Per passare rapidamente a una sezione, fare clic su un elemento nella barra di spostamento superiore dell'editor di regole per passare alla sezione seguente.
  
![Barra di spostamento superiore dell'editor di regole di prevenzione della perdita dei dati](../media/c527b97f-ca53-4c79-ad19-1a63be8a8ecc.png)
  
## <a name="dlp-policy-templates"></a>Modelli dei criteri di prevenzione della perdita dei dati

Il primo passaggio per la creazione dei criteri di prevenzione della perdita dei dati consiste nello scegliere le informazioni da proteggere. Iniziando con un modello di prevenzione della perdita dei dati, si evita lo sforzo di costruire un nuovo gruppo di regole da zero e di capire quali tipi di informazioni dovrebbero essere incluse per impostazione predefinita. È possibile aggiungere o modificare questi requisiti per ottimizzare la regola e rispondere ai requisiti specifici dell'organizzazione.
  
Un modello di criterio di prevenzione della perdita dei dati preconfigurato consente di rilevare tipi specifici di informazioni riservate, ad esempio i dati HIPAA, PCI-DSS, quelli della norma Gramm-Leach-Biley Act o specifiche informazioni personali locali. Per semplificare la ricerca e la protezione dei tipi comuni di informazioni riservate, i modelli di criteri inclusi in Microsoft 365 includono già i tipi più comuni necessari per iniziare.
  
![Elenco dei modelli di criteri di prevenzione della perdita dei dati con lo stato attivo sul modello degli Stati Uniti Patriot Act](../media/791b2403-430b-4987-8643-cc20abbd8148.png)
  
L'organizzazione può anche avere requisiti specifici personalizzati, nel qual caso è possibile creare criteri di prevenzione della perdita dei dati da zero scegliendo l'opzione **Criteri personalizzati**. I criteri personalizzati sono vuoti e non contengono regole predefinite. 
  
<!-- ## Roll out DLP policies gradually with test mode

rehomed to Plan for DLP

When you create your DLP policies, you should consider rolling them out gradually to assess their impact and test their effectiveness before fully enforcing them. For example, you don't want a new DLP policy to unintentionally block access to thousands of documents that people require access to in order to get their work done.
  
If you're creating DLP policies with a large potential impact, we recommend following this sequence:
  
1. **Start in test mode without Policy Tips** and then use the DLP reports and any incident reports to assess the impact. You can use DLP reports to view the number, location, type, and severity of policy matches. Based on the results, you can fine tune the rules as needed. In test mode, DLP policies will not impact the productivity of people working in your organization. 
    
2. **Move to Test mode with notifications and Policy Tips** so that you can begin to teach users about your compliance policies and prepare them for the rules that are going to be applied. At this stage, you can also ask users to report false positives so that you can further refine the rules. 
    
3. **Start full enforcement on the policies** so that the actions in the rules are applied and the content's protected. Continue to monitor the DLP reports and any incident reports or notifications to make sure that the results are what you intend. 

    ![Options for using test mode and turning on policy](../media/49fafaac-c6cb-41de-99c4-c43c3e380c3a.png)

    You can turn off a DLP policy at any time, which affects all rules in the policy. However, each rule can also be turned off individually by toggling its status in the rule editor.

    ![Options for turning off a rule in a policy](../media/f7b258ff-1b8b-4127-b580-83c6492f2bef.png)

    You can also change the priority of multiple rules in a policy. To do that, open a policy for editing. In a row for a rule, choose the ellipses (**...**), and then choose an option, such as **Move down** or **Bring to last**.

    > [!div class="mx-imgBorder"]
    > ![Set rule priority](../media/dlp-set-rule-priority.png)-->
  
## <a name="dlp-reports"></a>Report di prevenzione della perdita dei dati

Dopo aver creato e attivato i criteri di prevenzione della perdita dei dati, è consigliabile verificare che funzionino come previsto e consentano di mantenere la conformità. Con i report dei criteri di prevenzione della perdita dei dati, è possibile visualizzare il numero di corrispondenze con i criteri e con le regole nel corso del tempo, oltre al numero dei falsi positivi e delle regole ignorate. Per ogni report è possibile filtrare le corrispondenze per posizione, intervallo di tempo e anche restringere la ricerca a uno specifico criterio, regola o azione.
  
Con i report dei criteri di prevenzione della perdita dei dati, si ottengono informazioni aziendali ed è possibile:
  
- Concentrare l'attenzione su intervalli di tempo specifici e comprendere i motivi di eventuali impennate e tendenze.
    
- Individuare le procedure aziendali che violano i criteri di conformità dell'organizzazione.
    
- Comprendere l'eventuale impatto aziendale dei criteri DLP.
    
Inoltre, è possibile utilizzare i report DLP per ottimizzare i criteri DLP, quando vengono eseguiti.
  
![Dashboard Report nel Centro sicurezza e conformità](../media/6d741252-a0ce-4429-95ba-6c857ecc9a7e.png)
  
## <a name="how-dlp-policies-work"></a>Funzionamento dei criteri DLP

DLP permette di rilevare le informazioni riservate tramite un'analisi approfondita dei contenuti (non solo una semplice analisi del testo). Questa analisi approfondita utilizza corrispondenze delle parole chiave, del dizionario, la valutazione di espressioni regolari, funzioni interne e di altri metodi al fine di rilevare i contenuti corrispondenti ai criteri DLP. Viene considerata riservata potenzialmente solo una piccola percentuale dei dati. Un criterio DLP consente di identificare, monitorare e proteggere automaticamente solo tali dati, senza influire in alcun modo sul lavoro degli utenti con il resto del contenuto.
  
### <a name="policies-are-synced"></a>I criteri sono sincronizzati

Dopo aver creato un criterio di prevenzione della perdita dei dati nel Centro sicurezza e conformità, tale criterio viene salvato in un apposito archivio centrale e successivamente viene sincronizzato con le diverse origini di contenuti, tra cui:
  
- Exchange Online e da qui con Outlook sul Web e Outlook.
    
- Siti di OneDrive for Business.
    
- Siti di SharePoint Online.
    
- Applicazioni desktop di Office (Excel, PowerPoint e Word).

- Messaggi di chat e canali di Microsoft Teams.
    
In seguito alla sincronizzazione del criterio con il percorso corretto, viene avviata la valutazione del contenuto e l'applicazione delle azioni.
<!-- what is the time delay for first deployment of a policy and what is the sync schedule? -->
  
### <a name="policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites"></a>Valutazione dei criteri nei siti OneDrive for Business e SharePoint Online

In tutti i siti SharePoint Online e in tutti quelli di OneDrive for Business, i documenti vengono modificati costantemente: vengono creati, modificati, condivisi e così via. Questo implica che in qualsiasi momento possono entrare in conflitto o diventare conformi a un criterio di prevenzione della perdita dei dati. Ad esempio, una persona può caricare un documento che non contiene informazioni riservate nel proprio sito del team, ma in seguito un'altra persona può modificarlo e aggiungervi informazioni riservate.
  
Per questo motivo, i criteri DLP consentono di verificare la corrispondenza dei documenti ai criteri in background frequentemente. Tale operazione può essere considerata come una valutazione asincrona del criterio.<!-- what is the frequency? looks like it is tied to the search crawl schedule -->
  
#### <a name="how-it-works"></a>Funzionamento
 
Mentre vengono aggiunti o modificati documenti nei siti, il motore di ricerca esamina il contenuto in modo che possa essere cercato in seguito. Nel frattempo, il contenuto viene anche analizzato per rilevare informazioni riservate e verificare se vengono condivise. Tutte le informazioni riservate trovate vengono archiviate in sicurezza nell'indice di ricerca, a cui può accedere solo il team di conformità, e non utenti ordinari. Ogni criterio di prevenzione della perdita dei dati attivato viene eseguito in background (in modo asincrono), controllando frequentemente la ricerca di eventuali contenuti che corrispondono a un criterio e applicando le azioni per proteggerli da divulgazioni involontarie.
  
![Diagramma che illustra come i criteri di prevenzione della perdita dei dati valutano il contenuto in modo asincrono](../media/bdf73099-039a-4909-ae89-ac12c41992ba.png)
  
<!-- conflict with a DLP policy is bad wording --> Infine, i documenti possono essere in conflitto con un criterio DLP ma possono anche diventare conformi a tale criterio. Ad esempio, se una persona aggiunge numeri di carta di credito a un documento, è possibile che un criterio DLP blocchi l'accesso a tale documento automaticamente. Tuttavia, se in un secondo momento l'utente elimina le informazioni riservate, l'azione (in questo caso, di blocco) viene automaticamente annullata durante la successiva valutazione del documento rispetto al criterio.
  
I criteri di prevenzione della perdita dei dati valutano tutti i contenuti che possono essere indicizzati. Per altre informazioni sui tipi di file sottoposti per impostazione predefinita a ricerca per indicizzazione, vedere [Estensioni dei nomi di file sottoposti a ricerca per indicizzazione e tipi di file analizzati predefiniti in SharePoint Server](/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types).

> [!NOTE]
> Per evitare che i documenti vengano condivisi prima che i criteri DLP possano analizzarli, la condivisione di nuovi file in SharePoint può essere bloccata fino a quando il relativo contenuto non è stato indicizzato. Per informazioni dettagliate, vedere [Contrassegnare i nuovi file come riservati per impostazione predefinita](/sharepoint/sensitive-by-default). 
  
### <a name="policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web"></a>Valutazione dei criteri in Exchange Online, Outlook e Outlook sul web

Quando si creano criteri di prevenzione della perdita dei dati che includono Exchange Online come posizione, i criteri vengono sincronizzati dal Centro sicurezza e conformità di Office 365 con Exchange Online e quindi da Exchange Online con Outlook sul web e Outlook.
  
Quando un messaggio viene composto in Outlook, l'utente può visualizzare suggerimenti per i criteri man mano che il contenuto creato viene valutato rispetto ai criteri di prevenzione della perdita dei dati. Dopo l'invio, il messaggio viene valutato rispetto ai criteri di prevenzione della perdita dei dati nell'ambito delle normali operazioni del flusso di posta, oltre che rispetto alle regole del flusso di posta di Exchange (dette anche regole di trasporto) e ai criteri di prevenzione della perdita dei dati creati nell'interfaccia di amministrazione di Exchange. I criteri di prevenzione della perdita dei dati analizzano sia il messaggio che gli allegati.
  
### <a name="policy-evaluation-in-the-office-desktop-programs"></a>Valutazione dei criteri nei programmi desktop di Office

<!-- same capability to identify sensitive information line conflates sensitive information types and such -->
Excel, PowerPoint e Word dispongono della stessa funzionalità di SharePoint Online e OneDrive for Business che consente di identificare le informazioni riservate e applicare i criteri di prevenzione della perdita dei dati. Questi programmi di Office sincronizzano i propri criteri di prevenzione della perdita dei dati direttamente dall'archivio dei criteri centrale e quindi valutano continuamente i contenuti rispetto ai criteri di prevenzione della perdita dei dati quando gli utenti lavorano con documenti aperti da un sito incluso in un criterio.
  
La valutazione dei criteri di prevenzione della perdita dei dati in Office è progettata per non influire sulle prestazioni dei programmi o sulla produttività degli utenti. Se questi ultimi sono impegnati su un documento di grandi dimensioni oppure il computer di un utente è occupato, potrebbe essere necessario attendere qualche secondo prima che venga visualizzato un suggerimento per i criteri.

### <a name="policy-evaluation-in-microsoft-teams"></a>Valutazione dei criteri in Microsoft Teams
 <!--what do you mean that it's synched to user accounts?  I thought DLP policies were applied to locations not users like sensitivity labels are  -->

Quando si creano criteri di prevenzione della perdita dei dati che includono Microsoft teams come posizione, i criteri vengono sincronizzati dal Centro sicurezza e conformità di Office 365 con gli account utente e i messaggi di chat e canali di Microsoft Teams. A seconda di come vengono configurati i criteri di prevenzione della perdita dei dati, quando qualcuno tenta di condividere informazioni riservate in un messaggio di chat o canale di Microsoft Teams, è possibile bloccare o revocare il messaggio. Inoltre, i documenti che contengono informazioni riservate condivisi con utenti guest (utenti esterni), non potranno essere aperti da tali utenti. Per ulteriori informazioni, vedere [Prevenzione della perdita dei dati e Microsoft Teams](dlp-microsoft-teams.md).
 
## <a name="permissions"></a>Autorizzazioni

Per impostazione predefinita, gli amministratori globali, gli amministratori della sicurezza e gli amministratori di conformità avranno accesso per creare e applicare un criterio DLP. Gli altri membri del team di conformità che creeranno i criteri DLP necessitano delle autorizzazioni per il Centro &amp; sicurezza e conformità. Per impostazione predefinita, l'amministratore tenant avrà accesso a questa posizione e potrà concedere ai responsabili della conformità e ad altre persone l'accesso al Centro sicurezza e conformità, senza concedere loro tutte le autorizzazioni di un &amp; amministratore tenant. A tale scopo, è consigliabile:
  
1. Creare un gruppo in Microsoft 365 e aggiungervi i responsabili della conformità.
    
2. Creare un gruppo di ruoli nella pagina **Autorizzazioni** del Centro sicurezza e conformità. 

3. Durante la creazione del gruppo di ruoli, usare la sezione **Scegli ruoli** per aggiungere il ruolo seguente al gruppo di ruoli: **Gestione conformità DLP**.
    
4. Usare la sezione **Scegli membri** per aggiungere il gruppo di Microsoft 365 creato in precedenza al gruppo di ruoli.

È anche possibile creare un gruppo di ruoli con privilegi di sola visualizzazione per i report e i criteri DLP concedendo il ruolo di **solo visualizzazione per la gestione della conformità DLP**.

Per altre informazioni, vedere [Concedere agli utenti l'accesso al Centro conformità di Office 365](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).
  
Queste autorizzazioni sono necessarie solo per la creazione e l'applicazione di un criterio DLP. L'applicazione di un criterio non richiede l'accesso ai contenuti.
  
## <a name="find-the-dlp-cmdlets"></a>Trovare i cmdlet di prevenzione della perdita dei dati

Per usare la maggior parte dei cmdlet per il Centro sicurezza e conformità, è necessario:
  
1. [Connettersi al Centro sicurezza &amp; conformità di Office 365 usando la sessione remota di PowerShell](/powershell/exchange/connect-to-scc-powershell).
    
2. Usare uno di questi [cmdlet policy-and-compliance-dlp](/powershell/module/exchange/export-dlppolicycollection).
    
I report dei criteri di prevenzione della perdita dei dati devono tuttavia estrarre i dati da Microsoft 365, incluso Exchange Online. Per questo motivo, **i cmdlet per questi report sono disponibili in PowerShell per Exchange Online e non in PowerShell per Centro sicurezza e conformità**. Per usare i cmdlet per i report dei criteri di prevenzione della perdita dei dati, è quindi necessario:
  
1. [Connettersi a Exchange Online usando una sessione remota di PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).
    
2. Usare uno di questi cmdlet per i report dei criteri di prevenzione della perdita dei dati:
    
    - [Get-DlpDetectionsReport](/powershell/module/exchange/Get-DlpDetectionsReport)

    - [Get-DlpDetailReport](/powershell/module/exchange/Get-DlpDetailReport)
    
## <a name="more-information"></a>Ulteriori informazioni

- [Creare un criterio di prevenzione della perdita dei dati da un modello](create-a-dlp-policy-from-a-template.md)
    
- [Inviare notifiche e visualizzare i suggerimenti per i criteri di prevenzione della perdita dei dati](use-notifications-and-policy-tips.md)
    
- [Creare criteri di prevenzione della perdita dei dati per proteggere i documenti con FCI o altre proprietà](protect-documents-that-have-fci-or-other-properties.md)
    
- [Elementi inclusi nei modelli dei criteri di prevenzione della perdita dei dati](what-the-dlp-policy-templates-include.md)
    
- [Definizioni delle entità tipo di informazioni sensibili](sensitive-information-type-entity-definitions.md)
    
- [Cosa individuano le funzioni di prevenzione della perdita dei dati](what-the-dlp-functions-look-for.md)
    
- [Creare una tipologia personalizzata di informazioni riservate](create-a-custom-sensitive-information-type.md)
