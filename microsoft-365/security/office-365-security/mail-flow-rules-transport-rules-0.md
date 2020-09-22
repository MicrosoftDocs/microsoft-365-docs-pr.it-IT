---
title: Regole del flusso di posta in EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 9c2cf227-eff7-48ef-87fb-487186e47363
description: È possibile utilizzare le regole del flusso di posta (regole di trasporto) per identificare ed eseguire azioni sui messaggi che transitano nell'organizzazione.
ms.openlocfilehash: dba4771d575f0155e4ca1fc994d8467e496e5777
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201740"
---
# <a name="mail-flow-rules-transport-rules-in-standalone-eop"></a>Regole del flusso di posta (regole di trasporto) in Exchange Online Protection autonomo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Nelle organizzazioni autonome di Exchange Online Protection (EOP) prive di cassette postali di Exchange Online, è possibile utilizzare le regole del flusso di posta (note anche come regole di trasporto) per identificare ed eseguire azioni sui messaggi che transitano nell'organizzazione.

In questo argomento vengono illustrati i componenti delle regole del flusso di posta e il loro funzionamento.

Per i passaggi per creare, copiare e gestire le regole del flusso di posta, vedere [gestire le regole del flusso di posta in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules). Per ciascuna regola è possibile applicare, verificare o testare e inviare una notifica al mittente. Per ulteriori informazioni sulle opzioni di testing, vedere [test Mail Flow Rules](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/test-mail-flow-rules) and [policy Tips in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/data-loss-prevention/policy-tips).

Per i report di riepilogo e dettagli sui messaggi che corrispondono alle regole del flusso di posta, vedere [Use Mail Protection reports to view data about malware, spam, and Rule detections](https://docs.microsoft.com/exchange/monitoring/use-mail-protection-reports).

Per implementare determinati criteri di messaggistica usando le regole del flusso di posta, vedere gli argomenti seguenti:

- [Utilizzare le regole del flusso di posta per esaminare gli allegati di messaggi in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments)

- [Configurare la crittografia in Office 365 Enterprise](../../compliance/set-up-encryption.md)

- [Disclaimer, firme, piè di pagina o intestazioni di messaggi a livello di organizzazione in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/disclaimers-signatures-footers-or-headers)

- [Usare le regole del flusso di posta per impostare il livello di probabilità di posta indesiderata (SCL) nei messaggi](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)

- [Creare elenchi di mittenti bloccati in EOP](create-block-sender-lists-in-office-365.md)

- [Riduzione dei pericoli di malware tramite blocco dei file allegati in Exchange Online Protection](reducing-malware-threats-through-file-attachment-blocking-in-exchange-online-pro.md)

- [Definire le regole per crittografare o decrittografare i messaggi di posta elettronica in Office 365](https://docs.microsoft.com/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email)

Nel video seguente viene fornita una dimostrazione dell'impostazione delle regole del flusso di posta in EOP autonomo.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/7cdcd2cb-9382-4065-98e1-81257b32a189?autoplay=false]

## <a name="mail-flow-rule-components"></a>Componenti delle regole del flusso di posta

Una regola del flusso di posta è composta da condizioni, eccezioni, azioni e proprietà:

- **Condizioni**: identificare i messaggi a cui si desidera applicare le azioni. Alcune condizioni esaminano i campi d'intestazione dei messaggi (ad esempio, i campi A, Da, o Cc). Altre condizioni esaminano le proprietà del messaggio (ad esempio, l'oggetto, il corpo, gli allegati, la dimensione o la classificazione). Per la maggior parte delle condizioni l'utente deve specificare un operatore di confronto (ad esempio, uguale a, diverso da o contiene) e un valore da utilizzare per la corrispondenza. Se non sono presenti condizioni o eccezioni, la regola viene applicata a tutti i messaggi.

Per ulteriori informazioni sulle condizioni delle regole del flusso di posta in EOP autonomo, vedere [Mail Flow Rule conditions and Exceptions (Predicates) in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).

- **Eccezioni**: facoltativamente, identificare i messaggi a cui le azioni non devono essere applicate. Nelle eccezioni sono presenti gli stessi identificatori dei messaggi disponibili nelle condizioni. Le eccezioni sostituiscono le condizioni e impediscono l'esecuzione delle azioni della regola su un messaggio, anche nel caso in cui il messaggio soddisfi tutte le condizioni configurate.

- **Azioni**: specificare le operazioni da eseguire per i messaggi che soddisfano le condizioni della regola e non corrispondono ad alcuna eccezione. Sono disponibili molte azioni, ad esempio il rifiuto, l'eliminazione o il reindirizzamento dei messaggi, l'aggiunta di altri destinatari, l'aggiunta di prefissi all'oggetto del messaggio o l'inserimento di dichiarazioni di non responsabilità nel corpo del messaggio.

Per ulteriori informazioni sulle azioni delle regole del flusso di posta disponibili in EOP autonomo, vedere [Mail Flow Rule Actions in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).

- **Proprietà**: specificare altre impostazioni delle regole che non sono condizioni, eccezioni o azioni. Ad esempio, quando è necessario applicare la regola oppure se applicare o verificare la regola, il periodo in cui la regola è attiva.

  Per ulteriori informazioni, vedere la sezione in questo argomento [Proprietà delle regole del flusso di posta](#mail-flow-rule-properties).

### <a name="multiple-conditions-exceptions-and-actions"></a>Più condizioni, eccezioni e azioni

Nella tabella seguente è illustrato come in una regola vengono gestite più condizioni, valori della condizione, eccezioni e azioni.

****

|Componente|Logica|Commenti|
|---|---|---|
|Più condizioni|E|Un messaggio deve corrispondere a tutte le condizioni della regola. Se occorre una condizione di corrispondenza o un'altra, è possibile utilizzare regole distinte per ogni condizione. Ad esempio, per aggiungere la stessa dichiarazione di non responsabilità nei messaggi con allegati e nei messaggi con testo specifico, è possibile creare una regola per ogni condizione. Nell'interfaccia di amministrazione di Exchange, è possibile copiare facilmente una regola.|
|Una condizione con più valori|OPPURE|Le stesse condizioni consentono di specificare più valori. Il messaggio deve corrispondere a uno qualsiasi (non tutti) dei valori specificati. Ad esempio, se in un messaggio di posta elettronica l'oggetto è Informazioni sul prezzo delle azioni e la condizione **L'oggetto include una o più parole seguenti** è configurata per la corrispondenza alle parole Contoso o azioni, la condizione è soddisfatta perché l'oggetto contiene almeno uno dei valori specificati.  |
|Più eccezioni|OPPURE|Se un messaggio corrisponde a una qualsiasi delle eccezioni, le azioni non vengono applicate al messaggio. Quest'ultimo non deve necessariamente corrispondere a tutte le eccezioni.|
|Più azioni|E|I messaggi che corrispondono alle condizioni di una regola prendono tutte le azioni che sono specificate dalla regola. Ad esempio, se vengono selezionate le azioni **Anteponi all'oggetto del messaggio** e **Aggiungi destinatari alla casella Ccn**, verranno applicate entrambe al messaggio.<br/><br/> Tenere presente che alcune azioni come **Elimina il messaggio senza inviare alcuna notifica** impediscono l'applicazione a un messaggio delle regole successive. Altre azioni quali **Inoltra il messaggio** non consentono azioni aggiuntive.<br/><br/> È inoltre possibile impostare un'azione su una regola in modo che quando quella regola viene applicata, le regole successive non vengono applicate al messaggio.|
|

### <a name="mail-flow-rule-properties"></a>Proprietà regola flusso di posta

Nella tabella seguente vengono descritte le proprietà della regola che sono disponibili nelle regole di flusso della posta.

****

|Nome proprietà nell'interfaccia di amministrazione di Exchange|Nome del parametro in PowerShell|Descrizione|
|---|---|---|
|**Priorità**|_Priority_|Indica in che ordine le regole vengono applicate ai messaggi. La priorità predefinita si basa sul momento di creazione della regola; le regole meno recenti hanno una priorità superiore rispetto a quelle più nuove, mentre le regole con priorità superiore vengono elaborate prima delle regole con priorità inferiore. <br/><br/> La priorità della regola vengono modificate nell'interfaccia di amministrazione di Exchange spostando la regola verso l'alto o verso il basso nell'elenco delle regole. In PowerShell, impostare il numero di priorità (0 è la priorità più alta). <br/><br/> Ad esempio, in caso di una regola per rifiutare i messaggi che includono un numero di carta di credito e un'altra che richiede l'approvazione, è possibile far applicare per prima la regola per il rifiuto e interrompere l'applicazione delle altre regole.  |
|**Modalità**|_Mode_|È possibile specificare se la regola deve elaborare i messaggi immediatamente oppure se le regole devono essere testate senza coinvolgere il recapito del messaggio (con o senza suggerimenti sui criteri DLP). <br/><br/> I suggerimenti per i criteri presentano una breve nota in Outlook o Outlook sul Web che fornisce informazioni sulle possibili violazioni dei criteri alla persona che sta creando il messaggio. Per ulteriori informazioni, vedere **Suggerimenti per i criteri**. <br/><br/> Per ulteriori informazioni sulle modalità, vedere **Testare una regola del flusso di posta elettronica**.|
|**Attiva la regola in data** <br/><br/> **Disattiva la regola in data**|_ActivationDate_ <br/> _ExpiryDate_| Specifica l'intervallo di date in cui la data è attiva.|
|Casella di controllo **On** selezionata o deselezionata|Nuove regole: parametro _Enabled_ nel cmdlet **New-TransportRule**. <br/><br/> Regole esistenti: Utilizzare il cmdlet **Enable-TransportRule** o **Disable-TransportRule**. <br/><br/> Il valore viene visualizzato nella proprietà **State** della regola.|È possibile creare una regola disabilitata e abilitarla successivamente, quando l'utente è pronto per sottoporla a test. In alternativa, è possibile disabilitare una regola senza eliminarla per preservare le impostazioni.|
|**Rimanda il messaggio se l'elaborazione della regola non può essere completata**|_RuleErrorAction_|È possibile specificare in che modo bisogna gestire il messaggio, se l'elaborazione della regola non può essere completata. Per impostazione predefinita, la regola sarà ignorata, ma è possibile scegliere di inviare di nuovo il messaggio per l'elaborazione.|
|**Trova l'indirizzo del mittente nella parte seguente del messaggio**|_SenderAddressLocation_|Se la regola usa condizioni o eccezioni che esaminano l'indirizzo e-mail del mittente, è possibile cercare il valore nell'intestazione del messaggio, nella busta del messaggio o in entrambi i punti.|
|**Arrestare l'elaborazione di più regole**|_SenderAddressLocation_|Si tratta di un'azione per la regola, ma ha l'aspetto di una proprietà nell'interfaccia di amministrazione di Exchange. È possibile scegliere di interrompere l'applicazione di ulteriori regole a un messaggio dopo che una regola elabora un messaggio.|
|**Commenti**|_Comments_|È possibile immettere commenti descrittivi sulla regola.|
|

## <a name="how-mail-flow-rules-are-applied-to-messages"></a>Modalità di applicazione delle regole del flusso di posta ai messaggi

Tutti i messaggi che transitano nell'organizzazione vengono valutati rispetto alle regole di trasporto abilitate per l'organizzazione. Le regole vengono elaborate nell'ordine elencato nella **Mail flow** \> pagina **regole** del flusso di posta in EAC o in base al valore del parametro _Priority_ corrispondente in PowerShell.

Ogni regola offre inoltre l'opzione di arrestare l'elaborazione di più regole in caso di corrispondenza della regola. Questa impostazione è importante per i messaggi che corrispondono alle condizioni di più regole del flusso di posta. Quale regola si desidera applicare al messaggio? Tutte? Solo una?

### <a name="differences-in-processing-based-on-message-type"></a>Differenze di elaborazione in base al tipo di messaggio

Esistono diversi tipi di messaggi che passano attraverso un'organizzazione. Nella seguente tabella sono riportati i tipi di messaggio che possono essere elaborati dalle regole del flusso di posta.

****

|Tipo di messaggio|È possibile applicare una regola?|
|---|---|
|**Messaggi regolari**: messaggi che contengono un solo corpo RTF (Rich Text Format), HTML o testo normale o un set di corpi dei messaggi costituito da più parti o alternativa.|Sì|
|**Crittografia messaggi di office 365**: messaggi crittografati tramite crittografia dei messaggi di Office 365 in Office 365. Per ulteriori informazioni, vedere [Crittografia in Office 365](https://docs.microsoft.com/microsoft-365/compliance/encryption).|Le regole possono sempre accedere alle intestazioni delle buste ed elaborare i messaggi in base alle condizioni che esaminano quelle intestazioni. <br/><br/> Affinché una regola possa esaminare o modificare i contenuti di un messaggio crittografato, è necessario verificare che la crittografia di trasporto sia abilitata (Obbligatoria o Facoltativa; l'impostazione predefinita è Facoltativa). Per ulteriori informazioni, vedere [definire le regole per crittografare o decrittografare i messaggi di posta elettronica in Office 365](https://docs.microsoft.com/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email).|
|**Messaggi crittografati (S/MIME)**|Le regole possono accedere solo alle intestazioni delle buste ed elaborare i messaggi in base alle condizioni che esaminano quelle intestazioni. <br/><br/> Le regole con le condizioni che richiedono l'analisi del contenuto del messaggio oppure le azioni che modificano i contenuti del messaggio non possono essere elaborate.|
|**Messaggi protetti da RMS**: messaggi in cui è stato applicato un criterio Active Directory Rights Management Services (ad RMS) o Azure Rights Management (RMS).|Le regole possono sempre accedere alle intestazioni delle buste ed elaborare i messaggi in base alle condizioni che esaminano quelle intestazioni. <br/><br/> Affinché una regola possa esaminare o modificare i contenuti di un messaggio protetto da RMS, è necessario verificare che la crittografia di trasporto sia abilitata (Obbligatoria o Facoltativa; l'impostazione predefinita è Facoltativa).|
|**Messaggi con firma pulita**: messaggi firmati ma non crittografati.|Sì|
|**Messaggi di messaggistica unificata**: messaggi creati o elaborati dal servizio di messaggistica unificata, ad esempio segreteria telefonica, fax, notifiche di chiamata senza risposta e messaggi creati o inoltrati tramite Microsoft Outlook Voice Access.|Sì|
|**Messaggi anonimi**: messaggi inviati da mittenti anonimi.|Sì|
|**Rapporti di lettura**: rapporti generati in risposta alle richieste di conferma di lettura da parte dei mittenti. I report di lettura dispongono di una classe messaggio `IPM.Note*.MdnRead` o `IPM.Note*.MdnNotRead` .|Sì|
|

## <a name="what-else-should-i-know"></a>Informazioni aggiuntive

- La **versione** o il valore della proprietà **RuleVersion** per una regola non è importante in Exchange Online Protection.

- Dopo aver creato o modificato una regola del flusso di posta, possono essere necessari fino a 30 minuti affinché la regola nuova o aggiornata venga applicata ai messaggi.

## <a name="for-more-information"></a>Ulteriori informazioni

[Utilizzare le regole del flusso di posta per esaminare gli allegati di messaggi in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments)

[Crittografia della posta elettronica in Office 365](../../compliance/email-encryption.md)

[Limiti delle regole di Journal, trasporto e posta in arrivo](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#journal-transport-and-inbox-rule-limits)
