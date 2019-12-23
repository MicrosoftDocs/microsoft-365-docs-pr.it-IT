---
title: Come impedire falsi positivi in Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Informazioni su come impedire falsi positivi ed evitare che i messaggi effettivi vengano contrassegnati come posta indesiderata in Office 365, Exchange Online e Exchange Online Protection (EOP).
ms.openlocfilehash: 483bad168aa421e3fba4b0cc51e0b2e286f5701d
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2019
ms.locfileid: "40809322"
---
# <a name="how-to-prevent-good-email-messages-from-being-marked-as-spam-in-office-365"></a>Come impedire che i messaggi di posta elettronica effettivi vengano contrassegnati come indesiderati in Office 365

 **I messaggi effettivi vengono contrassegnata come posta indesiderata in Office 365? Ecco cosa fare.**

Se un messaggio di posta elettronica in arrivo è stato contrassegnato come posta indesiderata (ossia come _falso positivo_) in Office 365, Exchange Online o Exchange Online Protection (EOP), è opportuno segnalare il messaggio a Microsoft usando il [componente aggiuntivo Segnala messaggio](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2). È inoltre possibile inviare il messaggio usando [Esplora richieste](admin-submission.md).

## <a name="determine-why-the-message-was-marked-as-spam"></a>Determinare il motivo per cui il messaggio è stato contrassegnato come posta indesiderata

È possibile risolvere molti problemi relativi ai falsi positivi visualizzando l'intestazione del messaggio di posta elettronica, per determinare il motivo per cui il messaggio è stato contrassegnato come posta indesiderata. Per visualizzare l'intestazione del messaggio, [visualizzare le intestazioni dei messaggi Internet in Outlook](https://support.office.com/article/cd039382-dc6e-4264-ac74-c048563d212c).

In particolare, è necessario cercare un campo di intestazione denominato **X-Forefront-Antispam-Report**. I valori principali da cercare sono:

- **SFV:SPM**: il messaggio è stato contrassegnato come posta indesiderata dal filtro protezione da posta indesiderata (anche noto come _filtro contenuto_). Per ulteriori informazioni, vedere [Protezione dalla posta indesiderata in Office 365](anti-spam-protection.md).

- **SFV:BLK**: il messaggio è stato contrassegnato come posta indesiderata perché l'indirizzo di posta elettronica del mittente è incluso nell'elenco Mittenti bloccati del **destinatario**. Per ulteriori informazioni, vedere [Filtrare la posta indesiderata in Outlook sul web](https://support.office.com/article/db786e79-54e2-40cc-904f-d89d57b7f41d) e [Informazioni generali sul filtro per la posta indesiderata](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089).

- **SFV:SKS**: il messaggio è stato contrassegnato come posta indesiderata **prima** di essere esaminato dal filtro protezione da posta indesiderata. Ad esempio, una regola del flusso di posta (nota anche come regola di trasporto) imposta il livello di probabilità di posta indesiderata (SCL) del messaggio su un valore elevato (9), che indica quindi un messaggio indesiderato. Per ulteriori informazioni, vedere [Livelli di probabilità di posta indesiderata](spam-confidence-levels.md).

  Eseguire una traccia messaggio per verificare se una regola del flusso di posta è responsabile del valore SCL elevato. Per ulteriori informazioni, vedere [Traccia messaggio nel Centro sicurezza e conformità](message-trace-scc.md).

- **SFV: SKB**: il messaggio è stato contrassegnato come posta indesiderata perché corrisponde a una voce di blocco in un criterio di filtro della posta indesiderata (ad esempio mittenti bloccati o domini di mittenti bloccati). Per ulteriori informazioni, vedere [Configurare i criteri di filtro della posta indesiderata](configure-your-spam-filter-policies.md).

- **SFV:BULK**: il messaggio è stato identificato come posta elettronica in blocco anziché come posta indesiderata dal filtro protezione da posta indesiderata. Ciò si verifica quando il livello di reclamo in blocco (BCL) è **maggiore** della soglia di blocco definita nelle impostazioni dei criteri di protezione da posta indesiderata (più basso è il valore BCL, maggiore è la probabilità che si tratti di un messaggio di posta indesiderata). È possibile visualizzare il valore BCL nel campo di intestazione **X-Microsoft-Antispam**.

  La posta elettronica in blocco (nota anche come _posta grigia_) è un messaggio indesiderato, ma non dannoso, di marketing o pubblicitario, che è stato richiesto volontariamente o involontariamente dall'utente. Gli utenti hanno aspettative differenti sul modo in cui deve essere gestita la posta elettronica in blocco. Per questo motivo, è possibile creare regole o criteri differenti per consentire o bloccare la posta elettronica in blocco di conseguenza. Per ulteriori informazioni, vedere i seguenti argomenti:

  - [Differenza tra posta elettronica indesiderata e posta elettronica inviata in blocco](what-s-the-difference-between-junk-email-and-bulk-email.md)

  - [Valori dei livelli di reclamo in blocco (BCL)](bulk-complaint-level-values.md)

- **CAT:SPOOF** o **CAT:PHISH**: indica che il messaggio potrebbe essere falsificato, ovvero che l'origine del messaggio non può essere convalidata e potrebbe essere sospetta.

  Se il messaggio è stato inviato da un mittente falsificato, il mittente legittimo corrispondente dovrà verificare i record di SPF e DKIM del dominio di posta elettronica nel proprio DNS pubblico. Per ulteriori informazioni, controllare il campo di intestazione **Authentication-Results**. Anche se può essere difficile fare in modo che tutti i mittenti usino metodi adeguati di autenticazione della posta elettronica, l'esclusione di questi controlli può essere molto pericolosa ed è la causa principale di messaggi di spoofing e phishing.

> [!NOTE]
> • Per ulteriori informazioni sugli altri valori e sulle intestazioni dei messaggi di posta indesiderata, vedere [Intestazioni dei messaggi per la protezione da posta indesiderata](anti-spam-message-headers.md). <br/><br/>• L'utilizzo degli altri campi di intestazione che non sono descritti in modo specifico è riservato al team di protezione da posta indesiderata di Microsoft per scopi di diagnostica. <br/><br/>• Il campo di intestazione **X-CustomSpam** nell'intestazione del messaggio indica che è stato contrassegnato come posta indesiderata dal filtro avanzato di posta indesiderata (ASF). È in corso lo spostamento della funzionalità ASF in altre parti dello stack di filtro, per questo è consigliabile **disattivare** le impostazioni di ASF attualmente disponibili nei criteri di protezione dalla posta indesiderata. Per ulteriori informazioni, vedere le [Opzioni avanzate per il filtro della posta indesiderata](advanced-spam-filtering-asf-options.md).

## <a name="solutions-for-too-much-spam"></a>Soluzioni per posta indesiderata in eccesso

Per rendere più efficace il filtro della posta indesiderata, è necessario che un amministratore configuri alcune impostazioni nell'organizzazione. Se non si è un amministratore, è possibile passare alla sezione utenti.

### <a name="for-admins"></a>Per gli amministratori

- **Puntare il record MX del dominio di posta elettronica a Office 365**: per ottenere protezione da Office 365, il record MX per tutti i domini di posta elettronica in Office 365 deve puntare a Office 365 e solo a Office 365 (ovvero, la posta elettronica per i destinatari in quei domini deve sempre essere recapitata a Office 365 prima di tutto). Se il record MX punta a un'altra posizione (ad esempio, una soluzione o un dispositivo di terze parti per la posta indesiderata), Office 365 non può fornire il filtro posta indesiderata per gli utenti. In questo scenario, è consigliabile creare una regola di flusso di posta elettronica che permette di ignorare il filtro posta indesiderata per tutti i messaggi (impostare il valore SCL di tutti i messaggi in arrivo a -1). Se si decide di puntare il record MX prima di tutto a Office 365 in un secondo momento, assicurarsi di rimuovere tale regola.

- **Attivare il componente aggiuntivo Segnala messaggio per gli utenti**: è altamente consigliabile abilitare il componente aggiuntivo Segnala messaggio per gli utenti. Per istruzioni, vedere [Abilitare il componente aggiuntivo Segnala messaggio](enable-the-report-message-add-in.md).

- **Usare Esplora richieste**: gli amministratori ora possono inviare messaggi di posta elettronica per l'analisi di Microsoft. Gli amministratori possono anche essere in grado di visualizzare il feedback degli utenti. Per modificare le impostazioni di filtro posta indesiderata, è possibile usare i criteri nelle segnalazioni dei falsi positivi. Per ulteriori informazioni, vedere [Come inviare posta indesiderata, phishing, URL e file sospetti a Microsoft per l'analisi di Office 365](admin-submission.md).

- **Verificare che gli utenti rispettino i limiti consentiti**, come descritto in [Limiti di ricezione e invio](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#receiving-and-sending-limits) nella descrizione del servizio Exchange Online.

- **Verificare i livelli BCL nei criteri di protezione dalla posta indesiderata**, come descritto nella sezione precedente di questo argomento.

### <a name="for-users"></a>Per gli utenti

- **Aggiungere il mittente all'elenco Mittenti attendibili** in [Outlook](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089) o [ Outlook sul web](https://support.office.com/article/db786e79-54e2-40cc-904f-d89d57b7f41d).

  Office 365 userà l'elenco Mittenti attendibili e l’elenco Destinatari attendibili, ma non l’elenco dei Domini attendibili. Questo avviene indipendentemente dal fatto che il dominio venga aggiunto all'elenco (in Outlook, in Outlook sul web o in Outlook e poi sincronizzato con la sincronizzazione della directory).

- **Disabilitare il filtro SmartScreen in Outlook**: nei client desktop meno recenti di Outlook, non abilitare il filtro SmartScreen per le **Opzioni posta elettronica indesiderata**. Gli aggiornamenti per il filtro SmartScreen sono terminati a novembre 2016. Se si abilita la protezione **bassa** o **alta** della posta elettronica indesiderata in Outlook, si userà il filtro SmartScreen e si potranno ricevere falsi positivi. Il filtro SmartScreen non è disponibile nei moderni client desktop di Outlook. Per ulteriori informazioni, vedere [Eliminazione del supporto per SmartScreen in Outlook ed Exchange](https://techcommunity.microsoft.com/t5/Exchange-Team-Blog/Deprecating-support-for-SmartScreen-in-Outlook-and-Exchange/ba-p/605332).

## <a name="troubleshooting-a-message-is-delivered-to-the-junk-email-folder-after-passing-anti-spam-filtering"></a>Risoluzione dei problemi: i messaggi vengono recapitati nella cartella Posta indesiderata dopo aver superato il filtro posta indesiderata

Se l’utente ha selezionato l'opzione **Solo elenchi indirizzi attendibili** nelle opzioni di posta elettronica indesiderata di Outlook, tutti i messaggi provenienti da persone che non sono presenti nell'elenco Mittenti attendibili o Destinatari attendibili dell'utente verranno recapitati nella cartella **Posta indesiderata**, indipendentemente dal fatto che il messaggio abbia superato il filtro posta indesiderata dell'organizzazione o che una regola del flusso di posta abbia contrassegnato il messaggio come attendibile (valore SCL a -1).

Il destinatario vedrà in Outlook sul web un suggerimento di sicurezza di colore giallo, che indicherà un messaggio nella cartella **Posta indesiderata** poiché il mittente non è incluso nell'elenco dei mittenti attendibili del destinatario.

L'intestazione del messaggio includerà il valore del campo di intestazione `SFV:SKN` **X-Forefront-Antispam-Report** (il messaggio non è stato contrassegnato come posta indesiderata prima di procedere con il filtro posta indesiderata oppure `SFV:NSPM`il filtro posta indesiderata ha definito il messaggio come attendibile), ma il messaggio viene comunque recapitato nella cartella **posta indesiderata dell’utente**.

L'intestazione del messaggio non indica che il messaggio è stato recapitato come posta indesiderata poiché l’utente ha usato l’impostazione **Solo elenchi indirizzi attendibili**. Tuttavia, è possibile usare il cmdlet **Get-MailboxJunkEmailConfiguration** in PowerShell di Exchange Online per verificare se un utente consente solo ai messaggi provenienti da mittenti attendibili di essere recapitati nella Posta in arrivo.

Sostituire \<MailboxIdentity\> con il nome, l'alias o l'indirizzo di posta elettronica della cassetta postale ed eseguire il comando seguente in [PowerShell di Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell):

```PowerShell
Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List TrustedListsOnly,ContactsTrusted,TrustedSendersAndDomains
```

- Se il valore della proprietà *TrustedListsOnly* è `True`: i messaggi non inviati da mittenti o destinatari attendibili (ossia le persone che non sono presenti negli elenchi Mittenti attendibili e Destinatari attendibili dell'utente) verranno reindirizzati alla cartella **Posta indesiderata**.

- Se il valore della proprietà *ContactsTrusted* è `True`: i contatti dell'utente vengono identificati anche come mittenti attendibili. Se il valore della proprietà *TrustedListsOnly* è anche `True`, i messaggi provenienti da persone che non sono presenti nell'elenco Mittenti attendibili, nell’elenco Destinatari attendibili o nei contatti saranno recapitati nella cartella **Posta indesiderata**.

- Il valore della proprietà *TrustedSendersAndDomains* contiene l'elenco Mittenti attendibili dell'utente.

Per modificare queste opzioni nella cassetta postale, sostituire \<MailboxIdentity\> con il nome, l’alias o l’indirizzo di posta elettronica della cassetta postale ed eseguire il comando seguente:

```PowerShell
Set-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" -TrustedListsOnly $false -ContactsTrusted $false
```

Per informazioni dettagliate su sintassi, parametri e autorizzazioni necessarie, vedere gli argomenti [Get-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-mailboxjunkemailconfiguration) e [Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-mailboxjunkemailconfiguration).

## <a name="directory-synchronization-for-standalone-eop-customers"></a>Sincronizzazione della directory per clienti singoli di Exchange Online Protection

Se si usa solamente Exchange Online Protection per proteggere l’organizzazione Exchange locale, è consigliabile sincronizzare le impostazioni utente con il servizio usando la sincronizzazione della directory.
 In questo modo, si ha la certezza che gli elenchi dei Mittenti attendibili vengano rispettati da Exchange Online Protection. Per ulteriori informazioni, vedere [Utilizzare la sincronizzazione della directory per gestire gli utenti di posta](manage-mail-users-in-eop.md#use-directory-synchronization-to-manage-mail-users).
