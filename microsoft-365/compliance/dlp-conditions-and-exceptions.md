---
title: Condizioni, eccezioni e azioni dei criteri DLP (anteprima)
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: informazioni sulle condizioni e le eccezioni dei criteri dlp
ms.openlocfilehash: 5c2c8e010047c2de05cc8422da1958e2fe5fc54c
ms.sourcegitcommit: d859ea36152c227699c1786ef08cda5805ecf7db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "49604216"
---
# <a name="dlp-policy-conditions-exceptions-and-actions-preview"></a>Condizioni, eccezioni e azioni dei criteri DLP (anteprima)

Le condizioni e le eccezioni nei criteri DLP identificano gli elementi sensibili a cui viene applicato il criterio. Le azioni definiscono ciò che accade come conseguenza di una condizione di eccezione che viene soddisfatta.

- Le condizioni definiscono gli elementi da includere
- Le eccezioni definiscono gli elementi da escludere.
- Le azioni definiscono cosa accade come conseguenza della condizione o dell'eccezione che viene soddisfatta
 
La maggior parte delle condizioni e delle eccezioni dispone di una proprietà che supporta uno o più valori. Ad esempio, se il criterio DLP viene applicato  ai messaggi di posta elettronica di Exchange, la condizione del mittente richiede il mittente del messaggio. Alcune condizioni dispongono di due proprietà. Ad esempio, la condizione **Un'intestazione di messaggio include una di queste parole** richiede una proprietà per specificare il campo dell'intestazione del messaggio e un'altra proprietà per specificare il testo da cercare nel campo dell'intestazione. Alcune condizioni o eccezioni non hanno proprietà. Ad esempio, la condizione **Allegato protetto da password** cerca semplicemente gli allegati nei messaggi protetti da password.

In genere, per le azioni sono necessarie proprietà aggiuntive. Ad esempio, quando la regola del criterio DLP reindirizza un messaggio, è necessario specificare dove viene reindirizzato il messaggio. 
<!-- Some actions have multiple properties that are available or required. For example, when the rule adds a header field to the message header, you need to specify both the name and value of the header. When the rule adds a disclaimer to messages, you need to specify the disclaimer text, but you can also specify where to insert the text, or what to do if the disclaimer can't be added to the message. Typically, you can configure multiple actions in a rule, but some actions are exclusive. For example, one rule can't reject and redirect the same message.-->

## <a name="conditions-and-exceptions-for-dlp-policies"></a>Condizioni ed eccezioni per i criteri DLP

Le tabelle nelle sezioni seguenti descrivono le condizioni e le eccezioni disponibili in DLP.

- [Mittenti](#senders)
- [Destinatari](#recipients)
- [Oggetto o corpo del messaggio](#message-subject-or-body)
- [Allegati](#attachments)
- [Intestazioni del messaggio](#message-headers)
- [Proprietà dei messaggi](#message-properties)

### <a name="senders"></a>Mittenti


|**condizione o eccezione in DLP**  |**Parametri di condizione/eccezione in Microsoft 365 PowerShell** |**tipo di proprietà**  |**description**|
|---------|---------|---------|---------|
|Il mittente è |condition: *From* <br/> eccezione: *ExceptIfFrom*      |Addresses |     Messaggi inviati dalle cassette postali, dagli utenti di posta elettronica, dai contatti di posta o dai gruppi di Microsoft 365 specificati nell'organizzazione.|
|L'indirizzo IP del mittente è     |condizione: *SenderIPRanges*<br/> eccezione: *ExceptIfSenderIPRanges*         |  IPAddressRanges       | Messaggi in cui l'indirizzo IP del mittente corrisponde all'indirizzo IP specificato o ricade nell'intervallo di indirizzi IP specificato.       |
|L'indirizzo del mittente contiene parole   | condizione: *FromAddressContainsWords* <br/> eccezione: *ExceptIfFromAddressContainsWords*        |   Parole      |   Messaggi che contengono le parole specificate nell'indirizzo e-mail del mittente.|
| L'indirizzo del mittente corrisponde ai modelli    | condizione: *FromAddressMatchesPatterns* <br/> eccezione: *ExceptFromAddressMatchesPatterns*       |      Modelli   |  Messaggi in cui l'indirizzo e-mail del mittente contiene modelli di testo che corrispondono alle espressioni regolari specificate.  |
|Il dominio del mittente è  |  condizione: *SenderDomainIs* <br/> eccezione: *ExceptIfSenderDomainIs*       |DomainName         |     Messaggi in cui il dominio dell'indirizzo di posta elettronica del mittente corrisponde al valore specificato. Se è necessario trovare  i domini del mittente che contengono il dominio specificato (ad esempio, qualsiasi sottodominio di un dominio), utilizzare la condizione L'indirizzo del mittente corrisponde **a**(*FromAddressMatchesPatterns*) e specificare il dominio utilizzando la sintassi: ' \. dominio \. com$'.    |
|Ambito mittente    | condition: *FromScope* <br/> eccezione: *ExceptIfFromScope*    | UserScopeFrom    |    Messaggi inviati da mittenti interni o esterni.    |

### <a name="recipients"></a>Destinatari

|**condizione o eccezione in DLP**| **Parametri di condizione/eccezione in Microsoft 365 PowerShell** |    **tipo di proprietà** | **description**|
|---------|---------|---------|---------|
|Il destinatario è|  condizione: *SentTo* <br/> eccezione: *ExceptIfSentTo* | Addresses | Messaggi in cui uno dei destinatari è la cassetta postale, l'utente di posta o il contatto di posta specificato nell'organizzazione. I destinatari possono essere nei campi **To**, **Cc** o **Bcc** del messaggio.  |
|Il dominio del destinatario è|   condizione: *RecipientDomainIs* <br/> eccezione: *ExceptIfRecipientDomainIs* |   DomainName |    Messaggi in cui il dominio dell'indirizzo di posta elettronica del mittente corrisponde al valore specificato.|
|L'indirizzo del destinatario contiene parole|  condizione: *RecipientAddressContainsWords* <br/> eccezione: *ExceptIfRecipientAddressContainsWords*|    Parole|  Messaggi che contengono le parole specificate nell'indirizzo e-mail del destinatario. <br/>**Nota**: questa condizione non considera i messaggi che vengono inviati all'indirizzo proxy del destinatario. Esegue la corrispondenza solo dei messaggi che vengono inviati all'indirizzo e-mail principale del destinatario.|
|L'indirizzo del destinatario corrisponde ai modelli| condizione: *RecipientAddressMatchesPatterns* <br/> eccezione: *ExceptIfRecipientAddressMatchesPatterns*|   Modelli    |Messaggi in cui l'indirizzo e-mail del destinatario contiene modelli di testo che corrispondono alle espressioni regolari specificate. <br/> **Nota**: questa condizione non considera i messaggi che vengono inviati all'indirizzo proxy del destinatario. Esegue la corrispondenza solo dei messaggi che vengono inviati all'indirizzo e-mail principale del destinatario.|
|Inviato al membro di| condizione: *SentToMemberOf* <br/> eccezione: *ExceptIfSentToMemberOf*|  Addresses|  Messaggi contenenti destinatari membri del gruppo di distribuzione, del gruppo di sicurezza abilitato alla posta elettronica o del gruppo di Microsoft 365 specificato. Il gruppo può essere nei campi **To**, **Cc** o **Bcc** del messaggio.|

### <a name="message-subject-or-body"></a>Oggetto o corpo del messaggio

|**condizione o eccezione in DLP** | **Parametri di condizione/eccezione in Microsoft 365 PowerShell** |**tipo di proprietà**| **description**|
|---------|---------|---------|---------|
|L'oggetto contiene parole o frasi| condition: *SubjectContainsWords* <br/> eccezione: *ExceptIf SubjectContainsWords*| Parole   |Messaggi che contengono le parole specificate nel campo Subject.|
|L'oggetto corrisponde ai modelli|condition: *SubjectMatchesPatterns* <br/> eccezione: *ExceptIf SubjectMatchesPatterns*|Modelli   |Messaggi in cui il campo Oggetto contiene modelli di testo che corrispondono alle espressioni regolari specificate.|
|Il contenuto contiene|  condizione: *ContentContainsSensitiveInformation* <br/> exception *ExceptIfContentContainsSensitiveInformation*| SensitiveInformationTypes|  Messaggi o documenti che contengono informazioni riservate come definito dai criteri di prevenzione della perdita di dati (DLP).|
| L'oggetto o il corpo corrisponde al modello    | condizione: *SubjectOrBodyMatchesPatterns* <br/> eccezione: *ExceptIfSubjectOrBodyMatchesPatterns*    | Modelli    | Messaggi in cui il campo oggetto o il corpo del messaggio contiene modelli di testo che corrispondono alle espressioni regolari specificate.    |
| L'oggetto o il corpo contiene parole    | condizione: *SubjectOrBodyContainsWords* <br/> eccezione: *ExceptIfSubjectOrBodyContainsWords*    | Parole    | Messaggi con le parole specificate nel campo oggetto o nel corpo del messaggio    |


### <a name="attachments"></a>Allegati

|**condizione o eccezione in DLP**| **Parametri di condizione/eccezione in Microsoft 365 PowerShell**| **tipo di proprietà**   |**description**|
|---------|---------|---------|---------|
|L'allegato è protetto da password|condizione: *DocumentIsPasswordProtected* <br/> eccezione: *ExceptIfDocumentIsPasswordProtected*|nessuno| Messaggi in cui un allegato è protetto da password (e pertanto non può essere analizzato). Il rilevamento delle password funziona solo per i documenti di Office, i file ZIP e i file con estensione 7z.|
|L'estensione del file dell'allegato è|condizione: *ContentExtensionMatchesWords* <br/> eccezione: *ExceptIfContentExtensionMatchesWords*|  Parole   |Messaggi in cui l'estensione di un file allegato corrisponde a una delle parole specificate.|
|Non è stato possibile analizzare il contenuto di un allegato di posta elettronica|condizione: *DocumentIsUnsupported* <br/>eccezione: *ExceptIf DocumentIsUnsupported*|   n/d|    Messaggi in cui un allegato non è riconosciuto a livello nativo da Exchange Online.|
|Il contenuto di qualsiasi allegato di posta elettronica non ha completato l'analisi|   condizione: *ProcessingLimitExceeded* <br/> eccezione: *ExceptIfProcessingLimitExceeded*|    n/d |Messaggi in cui il motore delle regole non ha completato l'analisi degli allegati. È possibile utilizzare questa condizione per creare regole che interagiscono per identificare ed elaborare i messaggi in cui non è stato possibile analizzare completamente il contenuto.|
|Il nome del documento contiene parole|condizione: *DocumentNameMatchesWords* <br/> eccezione: *ExceptIfDocumentNameMatchesWords* |Parole  |Messaggi in cui il nome file di un allegato corrisponde a una delle parole specificate.|
|Il nome del documento corrisponde ai modelli|condizione: *DocumentNameMatchesPatterns* <br/> eccezione: *ExceptIfDocumentNameMatchesPatterns*|    Modelli    |Messaggi in cui il nome di file di un allegato contiene modelli di testo che corrispondono alle espressioni regolari specificate.|
|La proprietà del documento è|condizione: *ContentPropertyContainsWords* <br/> eccezione: *ExceptIfContentPropertyContainsWords* |Parole| Messaggi o documenti in cui l'estensione del file di un allegato corrisponde a una delle parole specificate.|
|La dimensione del documento è uguale o maggiore di| condizione: *DocumentSizeOver* <br/> eccezione: *ExceptIfDocumentSizeOver*|    Dimensioni    |Messaggi in cui un allegato ha una dimensione uguale o superiore al valore specificato.|

### <a name="message-headers"></a>Intestazioni messaggio

|**condizione o eccezione in DLP**| **Parametri di condizione/eccezione in Microsoft 365 PowerShell**| **tipo di proprietà**|  **description**|
|---------|---------|---------|---------|
|L'intestazione contiene parole o frasi|condizione: *HeaderContainsWords* <br/> eccezione: *ExceptIfHeaderContainsWords*|  Tabella Hash  |Messaggi che contengono il campo di intestazione specificato e il valore di tale campo di intestazione contiene le parole specificate.|
|L'intestazione corrisponde ai modelli|   condizione: *HeaderMatchesPatterns* <br/> eccezione: *ExceptIfHeaderMatchesPatterns*|    Tabella Hash  |Messaggi che contengono il campo di intestazione specificato e il valore di tale campo di intestazione contiene le espressioni regolari specificate.|

### <a name="message-properties"></a>Proprietà del messaggio

|**condizione o eccezione in DLP**| **Parametri di condizione/eccezione in Microsoft 365 PowerShell**| **tipo di proprietà**   |**description**|
|---------|---------|---------|---------|
|Dimensione dei messaggi oltre|condizione: *MessageSizeOver* <br/> eccezione: *ExceptIfMessageSizeOver*| Dimensioni    |Messaggi in cui la dimensione totale (messaggio più allegato) è uguale o superiore al valore specificato. <br/>**Nota**: i limiti di dimensione dei messaggi per le cassette postali vengono valutati prima delle regole del flusso di posta. Un messaggio troppo grande per una cassetta postale verrà rifiutato prima che una regola con questa condizione possa essere applicata al messaggio.  |
| Con importanza    | condition: *WithImportance* <br/> eccezione: *ExceptIfWithImportance*    | Priorità    | Messaggi contrassegnati con il livello di priorità specificato.    |
| Il set di caratteri del contenuto contiene parole    | condizione: *ContentCharacterSetContainsWords* <br/> *ExceptIfContentCharacterSetContainsWords*    | CharacterSets    | Messaggi che contengono i nomi dei set di caratteri specificati.    |
| Ha la sostituzione del mittente    | condition: *HasSenderOverride* <br/> eccezione: *ExceptIfHasSenderOverride*    | n/d    | Messaggi in cui il mittente ha scelto di ignorare un criterio di prevenzione della perdita di dati (DLP). Per ulteriori informazioni sui criteri DLP, vedere [Prevenzione della perdita dei dati.](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)   |
| Corrispondenze del tipo di messaggio    | condizione: *MessageTypeMatches* <br/> eccezione: *ExceptIfMessageTypeMatches*    | MessageType    | Messaggi del tipo specificato.    |

## <a name="actions-for-dlp-policies"></a>Azioni per i criteri DLP

Questa tabella descrive le azioni disponibili in DLP.


|**azione in DLP**|**parametri di azione in Microsoft 365 PowerShell**|**tipo di proprietà**|**description**|
|---------|---------|---------|---------|
|Imposta intestazione|SetHeader|First property: *Header Name* </br> Seconda proprietà: *Header Value*|Il parametro SetHeader consente di specificare un'azione per la regola DLP che aggiunge o modifica un campo di intestazione e un valore nell'intestazione del messaggio. Questo parametro utilizza la sintassi "HeaderName:HeaderValue". È possibile specificare più coppie nome/valore di intestazione separate da virgole|
|Rimuovi intestazione| RemoveHeader| Proprietà principale: *MessageHeaderField*</br> Proprietà secondaria: *String*|  Il parametro RemoveHeader consente di specificare un'azione per la regola DLP che rimuove un campo di intestazione dall'intestazione del messaggio. Questo parametro utilizza la sintassi "HeaderName" o "HeaderName:HeaderValue". È possibile specificare più nomi di intestazione o coppie nome/valore di intestazione separate da virgole|
|Reindirizzare il messaggio a utenti specifici|*RedirectMessageTo*|Addresses| Reindirizza il messaggio ai destinatari specificati. Il messaggio non viene recapitato ai destinatari originali e non viene inviata nessuna notifica né a questi né al mittente.|
|Inoltrare il messaggio per l'approvazione al responsabile del mittente| Moderato|Prima proprietà: *ModerateMessageByManager*</br> Proprietà seconda: *Boolean*|Il parametro Moderate consente di specificare un'azione per la regola DLP che invia il messaggio di posta elettronica a un moderatore. Questo parametro utilizza la sintassi: @{ModerateMessageByManager = <$true \| $false>;|
|Inoltrare il messaggio per l'approvazione a responsabili approvazione specifici| Moderato|Prima proprietà: *ModerateMessageByUser*</br>Proprietà secondaria: *Addresses*|Il parametro Moderate consente di specificare un'azione per la regola DLP che invia il messaggio di posta elettronica a un moderatore. Questo parametro utilizza la sintassi: @{ ModerateMessageByUser = @("emailaddress1","emailaddress2",..."emailaddressN")}|
|Aggiungere un destinatario|AddRecipients|First property: *Field*</br>Proprietà secondaria: *Addresses*| Aggiunge uno o più destinatari al campo A/Cc/Ccn del messaggio. Questo parametro utilizza la sintassi: @{<AddToRecipients \| CopyTo \| BlindCopyTo> = "emailaddress"}|
|Aggiungere il responsabile del mittente come destinatario|AddRecipients | Prima proprietà: *AddedManagerAction*</br>Proprietà secondo: *Campo* | Aggiunge il responsabile del mittente al messaggio come tipo di destinatario specificato ( To, Cc, Bcc ) o reindirizza il messaggio al gestore del mittente senza indicare il mittente o il destinatario. Questa operazione funziona solo se l'attributo Manager del mittente è definito in Active Directory. Questo parametro utilizza la sintassi: @{AddManagerAsRecipientType = "<To \| Cc \| Bcc>"}|    
Oggetto anteposto    |PrependSubject    |Stringa    |Consente di aggiungere il testo specificato all'inizio del campo Subject del messaggio. Valutare l'uso di uno spazio o dei due punti (:) come ultimo carattere del testo specificato per distinguerlo dal testo dell'oggetto originale.</br>Per impedire l'aggiunta della stessa stringa ai messaggi che contengono già il testo nell'oggetto (ad esempio, risposte), aggiungere l'eccezione "L'oggetto contiene parole" (ExceptIfSubjectContainsWords) alla regola.    |
Applicare la dichiarazione di non responsabilità HTML    |ApplyHtmlDisclaimer    |Proprietà first: *Text*</br>Second property: *Location*</br>Terza proprietà: *azione di fallback*    |Applica la dichiarazione di non responsabilità HTML specificata al percorso richiesto del messaggio.</br>Questo parametro utilizza la sintassi: @{ Text = " " ; Location = <Append \| Prepend>; FallbackAction = <Wrap \| Ignore \| Reject> }




