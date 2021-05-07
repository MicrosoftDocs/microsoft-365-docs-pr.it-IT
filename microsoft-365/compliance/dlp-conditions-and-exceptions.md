---
title: Condizioni, eccezioni e azioni dei criteri DLP
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: None
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
recommendations: false
description: informazioni sulle condizioni ed eccezioni dei criteri dlp
ms.openlocfilehash: 54c66f36e6a4b59147461ad154a4012f62bda77f
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114392"
---
# <a name="dlp-policy-conditions-exceptions-and-actions"></a>Condizioni, eccezioni e azioni dei criteri DLP

Le condizioni e le eccezioni nei criteri DLP identificano gli elementi sensibili a cui viene applicato il criterio. Le azioni definiscono cosa accade in seguito a una condizione di eccezione soddisfatta.

- Le condizioni definiscono cosa includere
- Le eccezioni definiscono cosa escludere.
- Le azioni definiscono cosa accade in seguito alla condizione o all'eccezione soddisfatta
 
La maggior parte delle condizioni e delle eccezioni dispone di una proprietà che supporta uno o più valori. Ad esempio, se il criterio DLP viene applicato Exchange  messaggi di posta elettronica, il mittente è condizione richiede il mittente del messaggio. Alcune condizioni dispongono di due proprietà. Ad esempio, la condizione **Un'intestazione di messaggio include una di queste parole** richiede una proprietà per specificare il campo dell'intestazione del messaggio e un'altra proprietà per specificare il testo da cercare nel campo dell'intestazione. Alcune condizioni o eccezioni non hanno proprietà. Ad esempio, la condizione **Attachment is password protected** cerca semplicemente gli allegati nei messaggi protetti da password.

In genere, per le azioni sono necessarie proprietà aggiuntive. Ad esempio, quando la regola dei criteri DLP reindirizza un messaggio, è necessario specificare dove viene reindirizzato il messaggio. 
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


|**condizione o eccezione in DLP**  |**parametri di condizione/eccezione in Microsoft 365 PowerShell** |**tipo di proprietà**  |**description**|
|---------|---------|---------|---------|
|Il mittente è |condition: *From* <br/> exception: *ExceptIfFrom*      |Addresses |     Messaggi inviati dalle cassette postali, dagli utenti di posta, dai contatti di posta o dai Microsoft 365 specifici dell'organizzazione.|
|L'indirizzo IP del mittente è     |condizione: *SenderIPRanges*<br/> exception: *ExceptIfSenderIPRanges*         |  IPAddressRanges       | Messaggi in cui l'indirizzo IP del mittente corrisponde all'indirizzo IP specificato o ricade nell'intervallo di indirizzi IP specificato.       |
|L'indirizzo del mittente contiene parole   | condition: *FromAddressContainsWords* <br/> exception: *ExceptIfFromAddressContainsWords*        |   Parole      |   Messaggi che contengono le parole specificate nell'indirizzo e-mail del mittente.|
| L'indirizzo del mittente corrisponde ai modelli    | condition: *FromAddressMatchesPatterns* <br/> eccezione: *ExceptFromAddressMatchesPatterns*       |      Modelli   |  Messaggi in cui l'indirizzo e-mail del mittente contiene modelli di testo che corrispondono alle espressioni regolari specificate.  |
|Il dominio del mittente è  |  condizione: *SenderDomainIs* <br/> exception: *ExceptIfSenderDomainIs*       |DomainName         |     Messaggi in cui il dominio dell'indirizzo di posta elettronica del mittente corrisponde al valore specificato. Se è necessario trovare  i domini del mittente che contengono il dominio specificato(ad esempio, qualsiasi sottodominio di un dominio), utilizzare la condizione L'indirizzo del mittente corrisponde **a**(*FromAddressMatchesPatterns*) e specificare il dominio utilizzando la sintassi: ' \. dominio \. com$'.    |
|Ambito mittente    | condition: *FromScope* <br/> exception: *ExceptIfFromScope*    | UserScopeFrom    |    Messaggi inviati da mittenti interni o esterni.    |
|Le proprietà specificate del mittente includono una o più delle seguenti parole|condizione: *SenderADAttributeContainsWords* <br/> exception: *ExceptIfSenderADAttributeContainsWords*|Prima proprietà: `ADAttribute` <p> Seconda proprietà: `Words`|Messaggi in cui l'attributo specificato Active Directory del mittente contiene una delle parole specificate.|
|Le proprietà specificate del mittente corrispondono a questi modelli di testo|condizione: *SenderADAttributeMatchesPatterns* <br/> exception: *ExceptIfSenderADAttributeMatchesPatterns*|Prima proprietà: `ADAttribute` <p> Seconda proprietà: `Patterns`|Messaggi in cui l'attributo specificato Active Directory del mittente contiene modelli di testo che corrispondono alle espressioni regolari specificate.|

### <a name="recipients"></a>Destinatari

|**condizione o eccezione in DLP**| **parametri di condizione/eccezione in Microsoft 365 PowerShell** |    **tipo di proprietà** | **description**|
|---------|---------|---------|---------|
|Il destinatario è|  condizione: *SentTo* <br/> exception: *ExceptIfSentTo* | Addresses | Messaggi in cui uno dei destinatari è la cassetta postale, l'utente di posta o il contatto di posta specificato nell'organizzazione. I destinatari possono essere nei campi **To**, **Cc** o **Bcc** del messaggio.  |
|Il dominio del destinatario è|   condizione: *RecipientDomainIs* <br/> exception: *ExceptIfRecipientDomainIs* |   DomainName |    Messaggi in cui il dominio dell'indirizzo di posta elettronica del destinatario corrisponde al valore specificato.|
|L'indirizzo del destinatario contiene parole|  condition: *AnyOfRecipientAddressContainsWords* <br/> exception: *ExceptIfAnyOfRecipientAddressContainsWords*|  Parole|  Messaggi che contengono le parole specificate nell'indirizzo e-mail del destinatario. <br/>**Nota**: questa condizione non considera i messaggi che vengono inviati all'indirizzo proxy del destinatario. Esegue la corrispondenza solo dei messaggi che vengono inviati all'indirizzo e-mail principale del destinatario.|
|L'indirizzo del destinatario corrisponde ai modelli| condizione: *AnyOfRecipientAddressMatchesPatterns* <br/> eccezione: *ExceptIfAnyOfRecipientAddressMatchesPatterns*| Modelli    |Messaggi in cui l'indirizzo e-mail del destinatario contiene modelli di testo che corrispondono alle espressioni regolari specificate. <br/> **Nota**: questa condizione non considera i messaggi che vengono inviati all'indirizzo proxy del destinatario. Esegue la corrispondenza solo dei messaggi che vengono inviati all'indirizzo e-mail principale del destinatario.|
|Inviato a membro di| condition: *SentToMemberOf* <br/> exception: *ExceptIfSentToMemberOf*|  Addresses|  Messaggi contenenti destinatari membri del gruppo di distribuzione, del gruppo di sicurezza abilitato alla posta elettronica o Microsoft 365 gruppo. Il gruppo può essere nei campi **To**, **Cc** o **Bcc** del messaggio.|

### <a name="message-subject-or-body"></a>Oggetto o corpo del messaggio

|**condizione o eccezione in DLP** | **parametri di condizione/eccezione in Microsoft 365 PowerShell** |**tipo di proprietà**| **description**|
|---------|---------|---------|---------|
|L'oggetto contiene parole o frasi| condition: *SubjectContainsWords* <br/> exception: *ExceptIf SubjectContainsWords*| Parole   |Messaggi che contengono le parole specificate nel campo Subject.|
|L'oggetto corrisponde ai modelli|condition: *SubjectMatchesPatterns* <br/> exception: *ExceptIf SubjectMatchesPatterns*|Modelli   |Messaggi in cui il campo Subject contiene modelli di testo che corrispondono alle espressioni regolari specificate.|
|Il contenuto contiene|  condition: *ContentContainsSensitiveInformation* <br/> exception *ExceptIfContentContainsSensitiveInformation*| SensitiveInformationTypes|  Messaggi o documenti che contengono informazioni riservate come definito dai criteri di prevenzione della perdita dei dati (DLP).|
| Oggetto o corpo corrisponde al modello    | condition: *SubjectOrBodyMatchesPatterns* <br/> exception: *ExceptIfSubjectOrBodyMatchesPatterns*    | Modelli    | Messaggi in cui il campo oggetto o il corpo del messaggio contiene modelli di testo che corrispondono alle espressioni regolari specificate.    |
| L'oggetto o il corpo contiene parole    | condition: *SubjectOrBodyContainsWords* <br/> exception: *ExceptIfSubjectOrBodyContainsWords*    | Parole    | Messaggi con le parole specificate nel campo oggetto o nel corpo del messaggio    |


### <a name="attachments"></a>Allegati

|**condizione o eccezione in DLP**| **parametri di condizione/eccezione in Microsoft 365 PowerShell**| **tipo di proprietà**   |**description**|
|---------|---------|---------|---------|
|L'allegato è protetto da password|condizione: *DocumentIsPasswordProtected* <br/> exception: *ExceptIfDocumentIsPasswordProtected*|nessuno| Messaggi in cui un allegato è protetto da password (e pertanto non può essere analizzato). Il rilevamento delle password funziona solo Office documenti, .zip e file con estensione 7z.|
|L'estensione del file dell'allegato è|condition: *ContentExtensionMatchesWords* <br/> exception: *ExceptIfContentExtensionMatchesWords*|  Parole   |Messaggi in cui l'estensione di un file allegato corrisponde a una delle parole specificate.|
|Non è stato possibile analizzare il contenuto di qualsiasi allegato di posta elettronica|condizione: *DocumentIsUnsupported* <br/>exception: *ExceptIf DocumentIsUnsupported*|   n/d|    Messaggi in cui un allegato non è riconosciuto a livello nativo da Exchange Online.|
|Il contenuto di qualsiasi allegato di posta elettronica non ha completato l'analisi|   condizione: *ProcessingLimitExceeded* <br/> exception: *ExceptIfProcessingLimitExceeded*|    n/d |Messaggi in cui il motore delle regole non ha completato l'analisi degli allegati. È possibile utilizzare questa condizione per creare regole che interagiscono per identificare ed elaborare i messaggi in cui non è stato possibile analizzare completamente il contenuto.|
|Il nome del documento contiene parole|condition: *DocumentNameMatchesWords* <br/> exception: *ExceptIfDocumentNameMatchesWords* |Parole  |Messaggi in cui il nome file di un allegato corrisponde a una delle parole specificate.|
|Il nome del documento corrisponde ai modelli|condizione: *DocumentNameMatchesPatterns* <br/> exception: *ExceptIfDocumentNameMatchesPatterns*|    Modelli    |Messaggi in cui il nome di file di un allegato contiene modelli di testo che corrispondono alle espressioni regolari specificate.|
|La proprietà del documento è|condition: *ContentPropertyContainsWords* <br/> exception: *ExceptIfContentPropertyContainsWords* |Parole| Messaggi o documenti in cui l'estensione di file di un allegato corrisponde a una delle parole specificate.|
|La dimensione del documento è uguale o maggiore di| condizione: *DocumentSizeOver* <br/> exception: *ExceptIfDocumentSizeOver*|    Dimensioni    |Messaggi in cui un allegato ha una dimensione uguale o superiore al valore specificato.|
|Il contenuto di qualsiasi allegato include una di queste parole| condition: *DocumentContainsWords* <br/> exception: *ExceptIfDocumentContainsWords* |`Words`|Messaggi in cui un allegato contiene le parole specificate.|
|Qualsiasi contenuto di allegati corrisponde a questi modelli di testo|condition: *DocumentMatchesPatterns* <br/> eccezione: *ExceptIfDocumentMatchesPatterns* |`Patterns`|Messaggi in cui un allegato contiene modelli di testo che corrispondono alle espressioni regolari specificate. |

### <a name="message-headers"></a>Intestazioni dei messaggi

|**condizione o eccezione in DLP**| **parametri di condizione/eccezione in Microsoft 365 PowerShell**| **tipo di proprietà**|  **description**|
|---------|---------|---------|---------|
|L'intestazione contiene parole o frasi|condition: *HeaderContainsWords* <br/> exception: *ExceptIfHeaderContainsWords*|  Hash Table  |Messaggi che contengono il campo di intestazione specificato e il valore di tale campo di intestazione contiene le parole specificate.|
|L'intestazione corrisponde ai modelli|   condition: *HeaderMatchesPatterns* <br/> eccezione: *ExceptIfHeaderMatchesPatterns*|    Hash Table  |Messaggi che contengono il campo di intestazione specificato e il valore di tale campo di intestazione contiene le espressioni regolari specificate.|

### <a name="message-properties"></a>Proprietà del messaggio

|**condizione o eccezione in DLP**| **parametri di condizione/eccezione in Microsoft 365 PowerShell**| **tipo di proprietà**   |**description**|
|---------|---------|---------|---------|
| Con importanza    | condition: *WithImportance* <br/> exception: *ExceptIfWithImportance*    | Priorità    | Messaggi contrassegnati con il livello di priorità specificato.    |
| Il set di caratteri del contenuto contiene parole    | condition: *ContentCharacterSetContainsWords* <br/> *ExceptIfContentCharacterSetContainsWords*    | CharacterSets    | Messaggi che contengono i nomi dei set di caratteri specificati.    |
| Ha override del mittente    | condition: *HasSenderOverride* <br/> exception: *ExceptIfHasSenderOverride*    | n/d    | Messaggi in cui il mittente ha scelto di ignorare un criterio di prevenzione della perdita di dati (DLP). Per ulteriori informazioni sui criteri DLP, vedere [Informazioni sulla prevenzione della perdita dei dati](./dlp-learn-about-dlp.md) |
| Corrispondenze del tipo di messaggio    | condition: *MessageTypeMatches* <br/> exception: *ExceptIfMessageTypeMatches*    | MessageType    | Messaggi del tipo specificato.    |
|La dimensione del messaggio è maggiore o uguale a| condition: *MessageSizeOver* <br/> exception: *ExceptIfMessageSizeOver* |`Size`|Messaggi in cui la dimensione totale (messaggio più allegato) è uguale o superiore al valore specificato. **Nota**: i limiti di dimensione dei messaggi per le cassette postali vengono valutati prima delle regole del flusso di posta. Un messaggio troppo grande per una cassetta postale verrà rifiutato prima che una regola con questa condizione possa essere applicata al messaggio.|

## <a name="actions-for-dlp-policies"></a>Azioni per i criteri DLP

In questa tabella vengono descritte le azioni disponibili in DLP.


|**azione in DLP**|**parametri azione in Microsoft 365 PowerShell**|**tipo di proprietà**|**description**|
|---------|---------|---------|---------|
|Imposta intestazione|SetHeader|First property: *Header Name* </br> Seconda proprietà: *Header Value*|Il parametro SetHeader consente di specificare un'azione per la regola DLP che aggiunge o modifica un campo di intestazione e un valore nell'intestazione del messaggio. Questo parametro utilizza la sintassi "HeaderName:HeaderValue". È possibile specificare più coppie nome/valore di intestazione separate da virgole|
|Rimuovi intestazione| RemoveHeader| Proprietà principale: *MessageHeaderField*</br> Proprietà secondaria: *String*|  Il parametro RemoveHeader consente di specificare un'azione per la regola DLP che rimuove un campo di intestazione dall'intestazione del messaggio. Questo parametro utilizza la sintassi "HeaderName" o "HeaderName:HeaderValue". È possibile specificare più nomi di intestazione o coppie nome/valore di intestazione separate da virgole|
|Reindirizzare il messaggio a utenti specifici|*RedirectMessageTo*|Addresses| Reindirizza il messaggio ai destinatari specificati. Il messaggio non viene recapitato ai destinatari originali e non viene inviata nessuna notifica né a questi né al mittente.|
|Inoltrare il messaggio per l'approvazione al responsabile del mittente| Moderato|Prima proprietà: *ModerateMessageByManager*</br> Seconda proprietà: *Boolean*|Il parametro Moderate consente di specificare un'azione per la regola DLP che invia il messaggio di posta elettronica a un moderatore. Questo parametro utilizza la sintassi: @{ModerateMessageByManager = <$true \| $false>;|
|Inoltrare il messaggio per l'approvazione a responsabili approvazione specifici| Moderato|Prima proprietà: *ModerateMessageByUser*</br>Proprietà secondaria: *Addresses*|Il parametro Moderate consente di specificare un'azione per la regola DLP che invia il messaggio di posta elettronica a un moderatore. Questo parametro utilizza la sintassi: @{ ModerateMessageByUser = @("emailaddress1","emailaddress2",..."emailaddressN")}|
|Aggiungi destinatario|AddRecipients|First, proprietà: *Field*</br>Proprietà secondaria: *Addresses*| Aggiunge uno o più destinatari al campo A/Cc/Ccn del messaggio. Questo parametro utilizza la sintassi: @{<AddToRecipients \| CopyTo \| BlindCopyTo> = "emailaddress"}|
|Aggiungere il manager del mittente come destinatario|AddRecipients | Prima proprietà: *AddedManagerAction*</br>Seconda proprietà: *Field* | Aggiunge il responsabile del mittente al messaggio come tipo di destinatario specificato ( To, Cc, Bcc ) o reindirizza il messaggio al gestore del mittente senza indicare il mittente o il destinatario. Questa operazione funziona solo se l'attributo Manager del mittente è definito in Active Directory. Questo parametro utilizza la sintassi: @{AddManagerAsRecipientType = "<To \| Cc \| Bcc>"}|    
Oggetto anteposto    |PrependSubject    |Stringa    |Consente di aggiungere il testo specificato all'inizio del campo Subject del messaggio. Valutare l'uso di uno spazio o dei due punti (:) come ultimo carattere del testo specificato per distinguerlo dal testo dell'oggetto originale.  </br>Per impedire l'aggiunta della stessa stringa ai messaggi che contengono già il testo nell'oggetto (ad esempio risposte), aggiungere l'eccezione "L'oggetto contiene parole" (ExceptIfSubjectContainsWords) alla regola.    
|Applicare la dichiarazione di non responsabilità HTML    |ApplyHtmlDisclaimer    |First, proprietà: *Text*</br>Seconda proprietà: *Location*</br>Terza proprietà: *azione di fallback*    |Applica la dichiarazione di non responsabilità HTML specificata al percorso richiesto del messaggio.</br>Questo parametro utilizza la sintassi: @{ Text = " " ; Location = <Append \| Prepend>; FallbackAction = <Wrap \| Ignore \| Reject> }
|Rimuovere Office 365 Message Encryption e la protezione dei diritti    | RemoveRMSTemplate | n/d| Rimuove Office 365 di crittografia applicata a un messaggio di posta elettronica|
