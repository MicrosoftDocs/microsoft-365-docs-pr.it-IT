---
title: Condizioni ed eccezioni dei criteri DLP (anteprima)
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
description: informazioni sulle condizioni e le eccezioni dei criteri DLP
ms.openlocfilehash: 2ce49b15bdb13035a37f6895b4b8865b55a62f78
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841472"
---
# <a name="dlp-policy-conditions-and-exceptions-preview"></a>Condizioni ed eccezioni dei criteri DLP (anteprima)

Le condizioni e le eccezioni nei criteri DLP identificano gli elementi sensibili a cui viene applicato il criterio. Le condizioni definiscono gli elementi da includere e le eccezioni definiscono gli elementi da escludere. Per ogni condizione è presente un'eccezione corrispondente che utilizza la stessa identica sintassi.

 La maggior parte delle condizioni e delle eccezioni ha una proprietà che supporta uno o più valori. Ad esempio, se il criterio DLP viene applicato ai messaggi di posta elettronica di Exchange, il **mittente** è la condizione richiede il mittente del messaggio. Alcune condizioni dispongono di due proprietà. Ad esempio, la condizione **Un'intestazione di messaggio include una di queste parole** richiede una proprietà per specificare il campo dell'intestazione del messaggio e un'altra proprietà per specificare il testo da cercare nel campo dell'intestazione. Alcune condizioni o eccezioni non dispongono di proprietà. Ad esempio, la condizione di **allegato è protetta da password** Cerca solo gli allegati nei messaggi protetti da password.

## <a name="conditions-and-exceptions-for-dlp-policies"></a>Condizioni ed eccezioni per i criteri DLP

Nelle tabelle riportate di seguito vengono descritte le condizioni e le eccezioni disponibili in DLP.

- [Mittenti](#senders)
- [Destinatari](#recipients)
- [Oggetto o corpo del messaggio](#message-subject-or-body)
- [Allegati](#attachments)
- [Intestazioni del messaggio](#message-headers)
- [Proprietà dei messaggi](#message-properties)

## <a name="senders"></a>Mittenti


|**condizione o eccezione in DLP**  |**parametri di condizione/eccezione in Microsoft 365 PowerShell** |**tipo di proprietà**  |**description**|
|---------|---------|---------|---------|
|Sender è |condizione: *from* <br/> eccezione: *ExceptIfFrom*      |Addresses |     Messaggi inviati dalle cassette postali, gli utenti di posta elettronica, i contatti di posta elettronica o i gruppi Microsoft 365 nell'organizzazione.|
|L'indirizzo IP del mittente è     |condizione: *SenderIpRanges*<br/> eccezione: *ExceptIfSenderIPRanges*         |  IPAddressRanges       | Messaggi in cui l'indirizzo IP del mittente corrisponde all'indirizzo IP specificato o ricade nell'intervallo di indirizzi IP specificato.       |
|L'indirizzo del mittente contiene le parole   | condizione: *FromAddressContainsWords* <br/> eccezione: *ExceptIfFromAddressContainsWords consente*        |   Parole      |   Messaggi che contengono le parole specificate nell'indirizzo e-mail del mittente.|
| Indirizzo mittente corrisponde a modelli    | condizione: *FromAddressMatchesPatterns* <br/> eccezione: *ExceptFromAddressMatchesPatterns*       |      Modelli   |  Messaggi in cui l'indirizzo e-mail del mittente contiene modelli di testo che corrispondono alle espressioni regolari specificate.  |
|Il dominio del mittente è  |  condizione: *SenderDomainIs* <br/> eccezione: *ExceptIfSenderDomainIs*       |DomainName         |     Messaggi in cui il dominio dell'indirizzo di posta elettronica del mittente corrisponde al valore specificato. Se è necessario trovare i domini mittente che *contengono* il dominio specificato (ad esempio, qualsiasi sottodominio di un dominio), utilizzare la condizione *FromAddressMatchesPatterns* ( **sender address Matches** ) e specificare il dominio utilizzando la sintassi:' \. Domain \. com $'.    |

## <a name="recipients"></a>Destinatari

|**condizione o eccezione in DLP**| **parametri di condizione/eccezione in Microsoft 365 PowerShell** |    **tipo di proprietà** | **description**|
|---------|---------|---------|---------|
|Il destinatario è|  condizione: *SentTo* <br/> eccezione: *ExceptIfSentTo* | Addresses | Messaggi in cui uno dei destinatari è la cassetta postale, l'utente di posta o il contatto di posta specificato nell'organizzazione. I destinatari possono essere nei campi **To** , **Cc** o **Bcc** del messaggio.  |
|Il dominio del destinatario è|   condizione: *RecipientDomainIs* <br/> eccezione: *ExceptIfRecipientDomainIs* |   DomainName |    Messaggi in cui il dominio dell'indirizzo di posta elettronica del mittente corrisponde al valore specificato.|
|L'indirizzo del destinatario contiene le parole|  condizione: *RecipientAddressContainsWords* <br/> eccezione: *ExceptIfRecipientAddressContainsWords*|    Parole|  Messaggi che contengono le parole specificate nell'indirizzo e-mail del destinatario. <br/>**Nota** : questa condizione non considera i messaggi che vengono inviati all'indirizzo proxy del destinatario. Esegue la corrispondenza solo dei messaggi che vengono inviati all'indirizzo e-mail principale del destinatario.|
|Indirizzi del destinatario corrisponde a modelli| condizione: *RecipientAddressMatchesPatterns* <br/> eccezione: *ExceptIfRecipientAddressMatchesPatterns*|   Modelli    |Messaggi in cui l'indirizzo e-mail del destinatario contiene modelli di testo che corrispondono alle espressioni regolari specificate. <br/> **Nota** : questa condizione non considera i messaggi che vengono inviati all'indirizzo proxy del destinatario. Esegue la corrispondenza solo dei messaggi che vengono inviati all'indirizzo e-mail principale del destinatario.|
|Inviato a membro di| condizione: *SentToMemberOf* <br/> eccezione: *ExceptIfSentToMemberOf*|  Addresses|  Messaggi che contengono destinatari che sono membri del gruppo di distribuzione specificato, del gruppo di sicurezza abilitato alla posta elettronica o del gruppo Microsoft 365. Il gruppo può essere nei campi **To** , **Cc** o **Bcc** del messaggio.|

## <a name="message-subject-or-body"></a>Oggetto o corpo del messaggio

|**condizione o eccezione in DLP** | **parametri di condizione/eccezione in Microsoft 365 PowerShell** |**tipo di proprietà**| **description**|
|---------|---------|---------|---------|
|Subject contiene parole o frasi| condizione: *SubjectContainsWords* <br/> eccezione: *ExceptIf SubjectContainsWords*| Parole   |Messaggi che contengono le parole specificate nel campo Subject.|
|Modelli di corrispondenza degli argomenti|condizione: *SubjectMatchesPatterns* <br/> eccezione: *ExceptIf SubjectMatchesPatterns*|Modelli   |Messaggi in cui il campo Subject contiene modelli di testo che corrispondono alle espressioni regolari specificate.|
|Contenuto contiene|  condizione: *ContentContainsSensitiveInformation* <br/> eccezione *ExceptIfContentContainsSensitiveInformation*| SensitiveInformationTypes|  Messaggi o documenti che contengono informazioni riservate come definito dai criteri di prevenzione della perdita di dati (DLP).|


## <a name="attachments"></a>Allegati

|**condizione o eccezione in DLP**| **parametri di condizione/eccezione in Microsoft 365 PowerShell**| **tipo di proprietà**   |**description**|
|---------|---------|---------|---------|
|L'allegato è protetto da password|condizione: *DocumentIsPasswordProtected* <br/> eccezione: *ExceptIfDocumentIsPasswordProtected*|nessuno| Messaggi in cui un allegato è protetto da password (e pertanto non può essere analizzato). Il rilevamento delle password funziona solo per documenti Office e file ZIP.|
|L'estensione di file dell'allegato è|condizione: *ContentExtensionMatchesWords* <br/> eccezione: *ExceptIfContentExtensionMatchesWords*|  Parole   |Messaggi in cui l'estensione di un file allegato corrisponde a una delle parole specificate.|
|Non è stato possibile analizzare il contenuto di un allegato di posta elettronica|condizione: *DocumentIsUnsupported* <br/>eccezione: *ExceptIf DocumentIsUnsupported*|   n/d|    Messaggi in cui un allegato non è riconosciuto a livello nativo da Exchange Online.|
|Il contenuto di un allegato di posta elettronica non ha completato l'analisi|   condizione: *ProcessingLimitExceeded* <br/> eccezione: *ExceptIfProcessingLimitExceeded*|    n/d |Messaggi in cui il motore delle regole non ha completato l'analisi degli allegati. È possibile utilizzare questa condizione per creare regole che interagiscono per identificare ed elaborare i messaggi in cui non è stato possibile analizzare completamente il contenuto.|
|Nome documento contiene parole|condizione: *DocumentNameMatchesWords* <br/> eccezione: *ExceptIfDocumentNameMatchesWords* |Parole  |Messaggi in cui il nome del file di un allegato corrisponde a una delle parole specificate.|
|Nome documento corrisponde a modelli|condizione: *DocumentNameMatchesPatterns* <br/> eccezione: *ExceptIfDocumentNameMatchesPatterns*|    Modelli    |Messaggi in cui il nome di file di un allegato contiene modelli di testo che corrispondono alle espressioni regolari specificate.|
|La proprietà del documento è|condizione: *ContentPropertyContainsWords* <br/> eccezione: *ExceptIfContentPropertyContainsWords* |Parole| Messaggi o documenti in cui l'estensione del file di un allegato corrisponde a una delle parole specificate.|
|La dimensione del documento è uguale o maggiore di| condizione: *DocumentSizeOver* <br/> eccezione: *ExceptIfDocumentSizeOver*|    Dimensioni    |Messaggi in cui un allegato ha una dimensione uguale o superiore al valore specificato.|

## <a name="message-headers"></a>Intestazioni del messaggio

|**condizione o eccezione in DLP**| **parametri di condizione/eccezione in Microsoft 365 PowerShell**| **tipo di proprietà**|  **description**|
|---------|---------|---------|---------|
|L'intestazione contiene parole o frasi|condizione: *HeaderContainsWords* <br/> eccezione: *ExceptIfHeaderContainsWords*|  Tabella hash  |Messaggi che contengono il campo di intestazione specificato e il valore di tale campo di intestazione contiene le parole specificate.|
|Modelli di corrispondenza di intestazione|   condizione: *HeaderMatchesPatterns* <br/> eccezione: *ExceptIfHeaderMatchesPatterns*|    Tabella hash  |Messaggi che contengono il campo di intestazione specificato e il valore di tale campo di intestazione contiene le espressioni regolari specificate.|

## <a name="message-properties"></a>Proprietà del messaggio

|**condizione o eccezione in DLP**| **parametri di condizione/eccezione in Microsoft 365 PowerShell**| **tipo di proprietà**   |**description**|
|---------|---------|---------|---------|
|Dimensione del messaggio sopra|condizione: *MessageSizeOver* <br/> eccezione: *ExceptIfMessageSizeOver*| Dimensioni    |Messaggi in cui la dimensione totale (messaggio più allegato) è uguale o superiore al valore specificato. <br/>**Nota** : i limiti di dimensione dei messaggi per le cassette postali vengono valutati prima delle regole del flusso di posta. Un messaggio troppo grande per una cassetta postale verrà rifiutato prima che una regola con questa condizione possa essere applicata al messaggio.  |

