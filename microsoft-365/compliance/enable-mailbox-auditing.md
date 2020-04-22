---
title: Gestire il controllo delle cassette postali
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: aaca8987-5b62-458b-9882-c28476a66918
description: La registrazione di controllo delle cassette postali è attivata per impostazione predefinita (denominato anche controllo delle cassette postali predefinito o controllo delle cassette postali per impostazione predefinita). Ciò significa che alcune azioni eseguite da proprietari, delegati e amministratori delle cassette postali vengono automaticamente registrate in un registro di controllo delle cassette postali, in cui è possibile cercare le attività eseguite sulla cassetta postale.
ms.openlocfilehash: 458e5c9797874f35e99c09edbc3ef45753132cba
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631731"
---
# <a name="manage-mailbox-auditing"></a>Gestire il controllo delle cassette postali

A partire da gennaio 2019, Microsoft sta attivando la registrazione di controllo delle cassette postali per impostazione predefinita per tutte le organizzazioni. Ciò significa che alcune azioni eseguite dai proprietari, dai delegati e dagli amministratori delle cassette postali vengono registrate automaticamente e che i record di controllo della cassetta postale corrispondente saranno disponibili quando si effettua la ricerca nel registro di controllo della cassetta postale. Prima che il controllo delle cassette postali fosse attivato per impostazione predefinita, è necessario abilitarlo manualmente per ogni cassetta postale dell'utente nell'organizzazione.

Di seguito sono illustrati alcuni vantaggi del controllo delle cassette postali per impostazione predefinita:

- Il controllo viene abilitato automaticamente quando si crea una nuova cassetta postale. Non è necessario abilitarlo manualmente per i nuovi utenti.

- Non è necessario gestire le azioni delle cassette postali di cui è stato eseguito il controllo. Per impostazione predefinita, per ogni tipo di accesso (amministratore, delegato e proprietario) viene controllata una serie di azioni delle cassette postali predefinite.

- Quando Microsoft rilascia una nuova azione della cassetta postale (in particolare le azioni che consentono di proteggere l'organizzazione e la guida con indagini forensi), l'azione viene aggiunta automaticamente all'elenco delle azioni delle cassette postali controllate per impostazione predefinita. Questo significa che non è necessario monitorare aggiungere nuove azioni alle cassette postali.

- Si dispone di un criterio di controllo delle cassette postali coerente all'interno dell'organizzazione (perché si controllano le stesse azioni per tutte le cassette postali).

> [!NOTE]
>* La cosa importante da ricordare sul rilascio del controllo delle cassette postali per impostazione predefinita è: non è necessario eseguire alcuna operazione per la gestione del controllo delle cassette postali. Tuttavia, per ulteriori informazioni, personalizzare il controllo delle cassette postali dalle impostazioni predefinite o disattivarlo completamente, questo argomento può essere di aiuto. <br><br>* Per impostazione predefinita, solo gli eventi di controllo delle cassette postali per gli utenti E5 sono disponibili nelle ricerche del registro di controllo nel centro sicurezza & conformità o tramite l'API di attività di gestione di Office 365. Per ulteriori informazioni, vedere la sezione [altre informazioni](#more-information) in questo argomento.

## <a name="verify-mailbox-auditing-on-by-default-is-turned-on"></a>Verificare che il controllo delle cassette postali per impostazione predefinita sia attivato

Per verificare che il controllo delle cassette postali per impostazione predefinita sia attivato per l'organizzazione, eseguire il comando seguente in [PowerShell di Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell):

```PowerShell
Get-OrganizationConfig | Format-List AuditDisabled
```

Il valore **false** indica che il controllo delle cassette postali è abilitato per impostazione predefinita per l'organizzazione. Questo valore dell'organizzazione per impostazione predefinita sostituisce l'impostazione di controllo delle cassette postali su specifiche cassette. Ad esempio, se il controllo della cassetta postale è disabilitato per una cassetta postale (la proprietà *AuditEnabled consente* è **impostata su false** sulla cassetta postale), le azioni della cassetta postale predefinite continueranno a essere controllate per la cassetta postale, perché il controllo delle cassette postali per impostazione predefinita è abilitato per l'organizzazione.

Per mantenere la funzionalità di controllo delle cassette postali disabilitata per cassette postali specifiche, è possibile configurare il bypass di controllo della cassetta postale per il proprietario della cassetta postale e per gli altri utenti a cui è stato delegato l'accesso Per ulteriori informazioni, vedere la sezione [ignorare la registrazione di controllo delle cassette postali](#bypass-mailbox-audit-logging) in questo argomento.

> [!NOTE]
> Quando l'esecuzione del controllo delle cassette postali è attivata per impostazione predefinita per l'organizzazione, la proprietà *AuditEnabled consente* per le cassette postali in questione non verrà modificata da **false** a **true**. In altre parole, il controllo delle cassette postali per impostazione predefinita ignora la proprietà *AuditEnabled consente* per le cassette postali.

## <a name="supported-mailbox-types"></a>Tipi di cassette postali supportate

Nella tabella seguente vengono illustrati i tipi di cassette postali attualmente supportati dal controllo delle cassette postali per impostazione predefinita:

|**Tipo di cassetta postale**|**Supportato**|**Non supportato**|
|:---------|:---------:|:---------:|
|Cassette postali utente|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|Cassette postali condivise|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|Cassette postali del gruppo Microsoft 365|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|Cassette postali per la risorsa||![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Cassette postali delle cartelle pubbliche||![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|

## <a name="logon-types-and-mailbox-actions"></a>Tipi di accesso e azioni delle cassette postali

I tipi di accesso classificano l'utente che ha eseguito le azioni sottoposte a controllo sulla cassetta postale. Nell'elenco seguente vengono descritti i tipi di accesso utilizzati per la registrazione di controllo delle cassette postali:

- **Proprietario**: il proprietario della cassetta postale (l'account associato alla cassetta postale).

- **Delegato**:

  - A un utente a cui è stata assegnata l'autorizzazione Senda, SendOnBehalf o FullAccess a un'altra cassetta postale.

  - Un amministratore a cui è stata assegnata l'autorizzazione FullAccess per la cassetta postale di un utente.

- **Amministratore**:

  - La cassetta postale viene cercata con uno dei seguenti strumenti di Microsoft eDiscovery:

    - Ricerca contenuto nel centro conformità.

    - eDiscovery o Advanced eDiscovery nel centro conformità.

    - EDiscovery sul posto in Exchange Online.

  - È possibile accedere alla cassetta postale utilizzando l'editor MAPI di Microsoft Exchange Server.

### <a name="mailbox-actions-for-user-mailboxes-and-shared-mailboxes"></a>Azioni delle cassette postali per gli utenti e le cassette postali condivise

Nella tabella seguente vengono descritte le azioni della cassetta postale disponibili nella registrazione di controllo delle cassette postali per gli utenti e le cassette postali condivise.

- Un segno di spunta ( ![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)) indica che l'azione della cassetta postale può essere registrata per il tipo di accesso (non tutte le azioni sono disponibili per tutti i tipi di accesso).

- Un asterisco ( <sup>\*</sup> ) dopo che il segno di spunta indica che l'azione della cassetta postale è registrata per impostazione predefinita per il tipo di accesso.

- Tenere presente che un amministratore con autorizzazione di accesso completo a una cassetta postale è considerato un delegato.

|**Azione della cassetta postale**|**Descrizione**|**Admin**|**Delegato**|**Proprietario**|
|:---------|:---------|:---------:|:---------:|:---------:|
|**AddFolderPermissions**|**Nota**: Sebbene questo valore venga accettato come azione della cassetta postale, è già incluso nell'azione **UpdateFolderPermissions** e non è controllato separatamente. In altre parole, non utilizzare questo valore.||||
|**ApplyRecord**|Un elemento è etichettato come record.|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**Copia**|Messaggio copiato in un'altra cartella.|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||
|**Creare**|Un elemento è stato creato nella cartella calendario, contatti, note o attività nella cassetta postale (ad esempio, viene creata una nuova convocazione di riunione). La creazione, l'invio o la ricezione di un messaggio non viene controllata, così come la creazione di una cartella della cassetta postale.|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**Predefinita**||![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**FolderBind**|Accesso effettuato a una cartella della cassetta postale. Tale azione viene registrata anche quando l'amministratore o un delegato apre la cassetta postale.<br/><br/> **Nota**: i record di controllo per le operazioni di associazione delle cartelle eseguite dai delegati vengono consolidati Viene generato un record di controllo per l'accesso a una singola cartella entro 24 ore.|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|**HardDelete**|Messaggio eliminato dalla cartella Elementi ripristinabili.|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**MailItemsAccessed**|I dati di posta elettronica sono accessibili tramite protocolli e client di posta elettronica. Questo valore è disponibile solo per gli utenti della sottoscrizione del componente aggiuntivo di conformità E5 o E5. Per informazioni dettagliate, vedere [accesso a eventi cruciali per le indagini](advanced-audit.md#access-to-crucial-events-for-investigations).|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**MailboxLogin**|L'utente ha eseguito l'accesso alla propria cassetta postale. |||![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**MessageBind**|Un messaggio è stato visualizzato nel riquadro di anteprima o è stato aperto da un amministratore. **Nota**: Sebbene questo valore venga accettato come azione della cassetta postale, queste azioni non vengono più registrate.|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||
|**ModifyFolderPermissions**|**Nota**: Sebbene questo valore venga accettato come azione della cassetta postale, è già incluso nell'azione **UpdateFolderPermissions** e non è controllato separatamente. In altre parole, non utilizzare questo valore.||||
|**Move**|Messaggio spostato in un'altra cartella.|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**MoveToDeletedItems**|Messaggio eliminato e spostato nella cartella Posta eliminata.|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**RecordDelete**|Un elemento etichettato come record è stato eliminato temporaneamente (spostato nella cartella elementi ripristinabili). Gli elementi contrassegnati come record non possono essere eliminati definitivamente (eliminati dalla cartella elementi ripristinabili).|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**RemoveFolderPermissions**|**Nota**: Sebbene questo valore venga accettato come azione della cassetta postale, è già incluso nell'azione **UpdateFolderPermissions** e non è controllato separatamente. In altre parole, non utilizzare questo valore.||||
|**SendAs**|Messaggio inviato utilizzando l'autorizzazione SendAs. Ciò significa che un altro utente ha inviato il messaggio come se provenisse dal proprietario della cassetta postale.|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>||
|**SendOnBehalf**|Messaggio inviato utilizzando l'autorizzazione SendOnBehalf. Ciò significa che un altro utente ha inviato il messaggio per conto del proprietario della cassetta postale. Il messaggio indica al destinatario la persona per conto della quale è stato inviato il messaggio e l’utente che ha effettivamente inviato il messaggio.|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>||
|**SoftDelete**|Messaggio eliminato in modo definitivo dalla cartella Posta eliminata. Gli elementi eliminati temporaneamente vengono spostati nella cartella Elementi ripristinabili.|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**Aggiorna**|Modifiche apportate a un messaggio o alle relative proprietà.|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**UpdateCalendarDelegation**|Una delega del calendario è stata assegnata a una cassetta postale. La delega del calendario assegna a un altro utente nella stessa organizzazione le autorizzazioni per la gestione del calendario del proprietario della cassetta postale.|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>||![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**UpdateComplianceTag**|Viene applicata un'etichetta di conservazione diversa a un elemento di posta elettronica, a cui è assegnata solo un'etichetta di conservazione.|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**UpdateFolderPermissions**|Un'autorizzazione per una cartella è stata cambiata. Le autorizzazioni per le cartelle determinano quali utenti dell'organizzazione possono accedere alle cartelle di una cassetta postale e ai messaggi che contengono.|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**UpdateInboxRules**|È stata aggiunta, rimossa o modificata una regola di posta in arrivo. Le regole di posta in arrivo vengono utilizzate per elaborare i messaggi nella posta in arrivo dell'utente in base alle condizioni specificate e intraprendere azioni quando vengono soddisfatte le condizioni di una regola, ad esempio lo spostamento di un messaggio in una cartella specificata o l'eliminazione di un messaggio.|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|

> [!IMPORTANT]
> Se nella propria organizzazione sono state abilitate le azioni delle cassette postali da controllare per qualsiasi tipo di accesso *prima* che il controllo delle cassette postali per impostazione predefinita fosse abilitato, le impostazioni personalizzate vengono mantenute nella cassetta postale e non vengono sovrascritte dalle azioni predefinite della cassetta postale come descritto in questa sezione. Per ripristinare i valori predefiniti delle azioni delle cassette postali di controllo (operazione che è possibile eseguire in qualsiasi momento), vedere la sezione [ripristinare le azioni delle cassette postali predefinite](#restore-the-default-mailbox-actions) più avanti in questo argomento.

### <a name="mailbox-actions-for-microsoft-365-group-mailboxes"></a>Azioni delle cassette postali per Microsoft 365

Il controllo delle cassette postali per impostazione predefinita porta la registrazione di controllo delle cassette postali alle cassette postali del gruppo Microsoft 365, ma non è possibile personalizzare le operazioni registrate (non è possibile aggiungere o rimuovere le azioni delle cassette postali registrate per qualsiasi tipo di accesso).

Nella tabella seguente vengono descritte le azioni delle cassette postali registrate per impostazione predefinita nelle cassette postali del gruppo Microsoft 365 per ogni tipo di accesso.

Tenere presente che un amministratore con autorizzazione di accesso completo a una cassetta postale di un gruppo di Microsoft 365 è considerato un delegato.

|**Azione della cassetta postale**|**Descrizione**|**Admin**|**Delegato**|**Proprietario**|
|:---------|:---------|:---------:|:---------:|:---------:|
|**Creare**|Creazione di un elemento del calendario. La creazione, l'invio o la ricezione di un messaggio non viene controllata,|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>||
|**HardDelete**|Messaggio eliminato dalla cartella Elementi ripristinabili.|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**MoveToDeletedItems**|Messaggio eliminato e spostato nella cartella Posta eliminata.|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**SendAs**|Un messaggio è stato inviato con l'autorizzazione SendAs,|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>||
|**SendOnBehalf**|Un messaggio è stato inviato con l'autorizzazione SendOnBehalf, |![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>||
|**SoftDelete**|Messaggio eliminato in modo definitivo dalla cartella Posta eliminata. Gli elementi eliminati temporaneamente vengono spostati nella cartella Elementi ripristinabili.|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**Aggiorna**|Modifiche apportate a un messaggio o alle relative proprietà.|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|

### <a name="verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type"></a>Verificare che le azioni delle cassette postali predefinite vengano registrate per ogni tipo di accesso

Per impostazione predefinita, il controllo delle cassette postali aggiunge una nuova proprietà *DefaultAuditSet* a tutte le cassette postali. Il valore di questa proprietà indica se le azioni delle cassette postali predefinite (gestite da Microsoft) vengono controllate sulla cassetta postale.

Per visualizzare il valore delle cassette postali degli utenti o delle \<cassette\> postali condivise, sostituire MailboxIdentity con il nome, l'alias, l'indirizzo di posta elettronica o il nome dell'entità utente (nomeutente) della cassetta postale ed eseguire il comando seguente in PowerShell di Exchange Online:

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Format-List DefaultAuditSet
```

Per visualizzare il valore delle cassette postali di gruppo di \<Microsoft\> 365, sostituire MailboxIdentity con il nome, l'alias o l'indirizzo di posta elettronica della cassetta postale condivisa ed eseguire il comando seguente in PowerShell di Exchange Online:

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> -GroupMailbox | Format-List DefaultAuditSet
```

Il valore `Admin, Delegate, Owner` indica:

- Le azioni predefinite delle cassette postali per tutti e tre i tipi di accesso vengono controllate. Questo è l'unico valore visualizzato nelle cassette postali del gruppo Microsoft 365.

- Un amministratore *non ha* modificato le azioni delle cassette postali controllate per qualsiasi tipo di accesso in una cassetta postale utente o in una cassetta postale condivisa. Nota Questo è lo stato predefinito dopo che il controllo delle cassette postali per impostazione predefinita viene inizialmente attivato all'interno dell'organizzazione.

Se un amministratore ha mai modificato le azioni della cassetta postale controllate per un tipo di accesso (utilizzando i parametri *AuditAdmin*, *AuditDelegate*o *AuditOwner* sul cmdlet **Set-Mailbox** ), il valore della proprietà sarà diverso.

Ad esempio, il valore `Owner` della proprietà *DefaultAuditSet* in una cassetta postale utente o in una cassetta postale condivisa indica quanto segue:

- Le azioni delle cassette postali predefinite per il proprietario della cassetta postale vengono controllate.

- Le azioni delle cassette postali controllate `Delegate` per `Admin` i tipi di accesso e sono state modificate dalle azioni predefinite.

Un valore vuoto per la proprietà *DefaultAuditSet* indica che le azioni delle cassette postali per tutti e tre i tipi di accesso sono state modificate nella cassetta postale dell'utente o in una cassetta postale condivisa.

Per ulteriori informazioni, vedere la sezione [modificare o ripristinare le azioni delle cassette postali registrate per impostazione predefinita](#change-or-restore-mailbox-actions-logged-by-default) in questo argomento

### <a name="display-the-mailbox-actions-that-are-being-logged-on-mailboxes"></a>Visualizzare le azioni delle cassette postali registrate nelle cassette postali

Per visualizzare le azioni delle cassette postali attualmente in fase di accesso alle cassette postali degli \<utenti\> o alle cassette postali condivise, sostituire MailboxIdentity con il nome, l'alias, l'indirizzo di posta elettronica o il nome dell'entità utente (nomeutente) della cassetta postale ed eseguire uno o più dei comandi seguenti in PowerShell di Exchange Online.

> [!NOTE]
> Anche se è possibile aggiungere `-GroupMailbox` l'opzione ai comandi **Get-Mailbox** seguenti per le cassette postali del gruppo Microsoft 365, non credere ai valori restituiti. Le azioni delle cassette postali predefinite e statiche di cui è stato eseguito il controllo per le cassette postali del gruppo Microsoft 365 sono descritte nella sezione [azioni della cassetta postale per](#mailbox-actions-for-microsoft-365-group-mailboxes) le cassette postali di Microsoft 365 di questo argomento.

#### <a name="owner-actions"></a>Azioni del proprietario

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditOwner
```

#### <a name="delegate-actions"></a>Azioni delegate

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditDelegate
```

#### <a name="admin-actions"></a>Azioni amministrative

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditAdmin
```

## <a name="change-or-restore-mailbox-actions-logged-by-default"></a>Modificare o ripristinare le azioni delle cassette postali registrate per impostazione predefinita

Come spiegato in precedenza, uno dei principali vantaggi dell'utilizzo del controllo delle cassette postali per impostazione predefinita è: non è necessario gestire le azioni delle cassette postali controllate. Microsoft fa questo per te e noi aggiungeremo automaticamente nuove azioni delle cassette postali da controllare per impostazione predefinita quando vengono rilasciate.

Tuttavia, è possibile che l'organizzazione debba controllare un diverso insieme di azioni delle cassette postali per le cassette postali degli utenti e le cassette postali condivise. Nelle procedure illustrate in questa sezione viene illustrato come modificare le azioni delle cassette postali controllate per ogni tipo di accesso e come ripristinare le azioni predefinite gestite da Microsoft.

> [!IMPORTANT]
> Se si utilizzano le procedure seguenti per personalizzare le azioni delle cassette postali registrate nelle cassette postali degli utenti o nelle cassette postali condivise, tutte le nuove azioni della cassetta postale predefinite rilasciate da Microsoft non verranno controllate automaticamente su tali cassette postali. È necessario aggiungere manualmente tutte le nuove azioni della cassetta postale all'elenco personalizzato di azioni.

### <a name="change-the-mailbox-actions-to-audit"></a>Modificare le azioni delle cassette postali da controllare

È possibile utilizzare i parametri *AuditAdmin*, *AuditDelegate*o *AuditOwner* sul cmdlet **Set-Mailbox** per modificare le azioni delle cassette postali controllate per le cassette postali degli utenti e le cassette postali condivise (le azioni controllate per le cassette postali del gruppo Microsoft 365 non possono essere personalizzate).

È possibile utilizzare due metodi diversi per specificare le azioni delle cassette postali:

- *Replace* (overwrite) the existing mailbox actions usando la `action1,action2,...actionN`sintassi seguente:.

- *Aggiungere o rimuovere* azioni delle cassette postali senza influire su altri valori esistenti utilizzando `@{Add="action1","action2",..."actionN"}` la `@{Remove="action1","action2",..."actionN"}`sintassi seguente: oppure.

In questo esempio vengono modificate le azioni delle cassette postali di amministrazione per la cassetta postale denominata "Gabriela Laureano" sovrascrivendo le azioni predefinite con SoftDelete e HardDelete.

```PowerShell
Set-Mailbox -Identity "Gabriela Laureano" -AuditAdmin HardDelete,SoftDelete
```

In questo esempio viene aggiunta l'azione MailboxLogin Owner alla cassetta postale laura@contoso.onmicrosoft.com.

```PowerShell
Set-Mailbox -Identity laura@contoso.onmicrosoft.com -AuditOwner @{Add="MailboxLogin"}
```

In questo esempio viene rimossa l'azione delegata MoveToDeletedItems per la cassetta postale del team di discussione.

```PowerShell
Set-Mailbox -Identity "Team Discussion" -AuditDelegate @{Remove="MoveToDeletedItems"}
```

Indipendentemente dal metodo utilizzato, la personalizzazione delle azioni delle cassette postali controllate nelle cassette postali degli utenti o nelle cassette postali condivise ha i risultati seguenti:

- Per il tipo di accesso personalizzato, le azioni delle cassette postali controllate non sono più gestite da Microsoft.

- Il tipo di accesso personalizzato non viene più visualizzato nel valore della proprietà *DefaultAuditSet* per la cassetta postale come [descritto in precedenza](#verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type).

### <a name="restore-the-default-mailbox-actions"></a>Ripristinare le azioni predefinite delle cassette postali

Se sono state personalizzate le azioni delle cassette postali controllate in una cassetta postale utente o in una cassetta postale condivisa, è possibile ripristinare le azioni predefinite della cassetta postale per uno o per tutti i tipi di accesso utilizzando la sintassi seguente:

```PowerShell
Set-Mailbox -Identity <MailboxIdentity> -DefaultAuditSet <Admin | Delegate | Owner>
```

È possibile specificare più valori di *DefaultAuditSet* separati da virgole

**Nota**: le procedure seguenti non si applicano alle cassette postali del gruppo Microsoft 365 (sono limitate alle azioni predefinite come descritto di [seguito](#mailbox-actions-for-microsoft-365-group-mailboxes)).

In questo esempio vengono ripristinate le azioni predefinite della cassetta postale di controllo per tutti i tipi di accesso nella cassetta postale mark@contoso.onmicrosoft.com.

```PowerShell
Set-Mailbox -Identity mark@contoso.onmicrosoft.com -DefaultAuditSet Admin,Delegate,Owner
```

In questo esempio vengono ripristinate le azioni di cassette postali di controllo predefinite per il tipo di accesso all'amministratore nella cassetta postale chris@contoso.onmicrosoft.com, ma vengono lasciate le azioni di cassetta postale controllate personalizzate per i tipi di accesso delegato e proprietario.

```PowerShell
Set-Mailbox -Identity chris@contoso.onmicrosoft.com -DefaultAuditSet Admin
```

Ripristino delle azioni delle cassette postali di controllo predefinite per un tipo di accesso sono riportati i risultati seguenti:

- L'elenco corrente delle azioni delle cassette postali viene sostituito con le azioni predefinite delle cassette postali per il tipo di accesso.

- Tutte le nuove azioni della cassetta postale rilasciate da Microsoft vengono aggiunte automaticamente all'elenco delle azioni controllate per il tipo di accesso.

- Il valore della proprietà *DefaultAuditSet* per la cassetta postale viene aggiornato per includere il tipo di accesso ripristinato.

## <a name="turn-off-mailbox-auditing-on-by-default-for-your-organization"></a>Disattivare il controllo delle cassette postali per impostazione predefinita per l'organizzazione

Per impostazione predefinita, è possibile disattivare il controllo delle cassette postali per l'intera organizzazione eseguendo il comando seguente in PowerShell di Exchange Online:

```PowerShell
Set-OrganizationConfig -AuditDisabled $true
```

La disattivazione del controllo delle cassette postali per impostazione predefinita ha i risultati seguenti:

- Il controllo delle cassette postali è disabilitato per l'organizzazione.

- Dal momento in cui il controllo delle cassette postali è stato disabilitato per impostazione predefinita, non vengono controllate le azioni delle cassette postali, anche se il controllo è abilitato su una cassetta postale (la proprietà *AuditEnabled consente* nella cassetta postale è **vera**).

- Il controllo delle cassette postali non è abilitato per le nuove cassette postali e l'impostazione della proprietà *AuditEnabled consente* in una cassetta postale nuova o esistente su **true** verrà ignorata.

- Tutte le impostazioni di esclusione di controllo delle cassette postali (configurate utilizzando il cmdlet **Set-MailboxAuditBypassAssociation** ) vengono ignorate.

- I record di controllo delle cassette postali esistenti vengono mantenuti fino alla scadenza del periodo di validità del registro di controllo.

### <a name="turn-on-mailbox-auditing-on-by-default"></a>Attivazione del controllo delle cassette postali per impostazione predefinita

Per abilitare di nuovo il controllo della cassetta postale per l'organizzazione, eseguire il comando seguente in PowerShell di Exchange Online:

```PowerShell
Set-OrganizationConfig -AuditDisabled $false
```

## <a name="bypass-mailbox-audit-logging"></a>Ignorare la registrazione di controllo delle cassette postali

Attualmente, non è possibile disabilitare il controllo della cassetta postale per cassette postali specifiche quando l'esecuzione del controllo delle cassette postali è attivata per impostazione predefinita nell'organizzazione. Ad esempio, se si imposta la proprietà della cassetta postale *AuditEnabled consente* su **false** , verrà ignorata.

Tuttavia, è comunque possibile utilizzare il cmdlet **Set-MailboxAuditBypassAssociation** in Exchange Online PowerShell per impedire la registrazione di *tutte* le azioni delle cassette postali da parte degli utenti specificati, indipendentemente dal luogo in cui si verificano le azioni. Ad esempio:

- Le azioni del proprietario della cassetta postale eseguite dagli utenti ignorati non vengono registrate.

- Le azioni delegate eseguite dagli utenti ignorati nelle cassette postali di altri utenti (incluse le cassette postali condivise) non vengono registrate.

- Le azioni amministrative eseguite dagli utenti ignorati non vengono registrate.

Per ignorare la registrazione di controllo delle cassette postali per \<un\> utente specifico, sostituire MailboxIdentity con il nome, l'indirizzo di posta elettronica, l'alias o il nome dell'entità utente (nomeutente) dell'utente ed eseguire il comando seguente:

```PowerShell
Set-MailboxAuditBypassAssociation -Identity <MailboxIdentity> -AuditByPassEnabled $true
```

Per verificare che il controllo sia bypassato per l'utente specificato, eseguire il comando riportato di seguito:

```PowerShell
Get-MailboxAuditBypassAssociation -Identity <MailboxIdentity> | Format-List AuditByPassEnabled
```

Il valore **true** indica che la registrazione di controllo delle cassette postali viene ignorata per l'utente.

## <a name="more-information"></a>Ulteriori informazioni

- Anche se la registrazione di controllo delle cassette postali è attivata per impostazione predefinita per tutte le organizzazioni, solo gli utenti con licenze E5 restituiranno gli eventi del registro di controllo delle cassette postali nelle [ricerche del registro di controllo nel centro sicurezza & conformità](search-the-audit-log-in-security-and-compliance.md) o tramite l' [API di gestione di Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference) **per impostazione predefinita**

  Per recuperare le voci del registro di controllo delle cassette postali per gli utenti senza licenze E5, è possibile:

  - Abilitare manualmente il controllo delle cassette postali su singole cassette di posta `Set-Mailbox -Identity <MailboxIdentity> -AuditEnabled $true`(eseguire il comando). Dopo aver eseguito questa operazione, è possibile utilizzare le ricerche del registro di controllo nel centro sicurezza & Compliance o tramite l'API di attività di gestione di Office 365.
  
    > [!NOTE]
    > Se il controllo delle cassette postali è già abilitato per la cassetta postale, ma le ricerche non restituiscono alcun risultato, modificare _AuditEnabled_ il valore del `$false` parametro AuditEnabled consente e quindi `$true`tornare a.
  
  - Utilizzare i cmdlet seguenti in PowerShell di Exchange Online:

    - [Search-MailboxAuditLog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-mailboxauditlog) per eseguire una ricerca nel registro di controllo della cassetta postale per utenti specifici.

    - [New-MailboxAuditLogSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/new-mailboxauditlogsearch) per eseguire una ricerca nel log di controllo delle cassette postali per utenti specifici e per inviare i risultati tramite posta elettronica ai destinatari specificati.

  - Utilizzare l'interfaccia di amministrazione di Exchange (EAC) in Exchange Online per eseguire le operazioni seguenti:

    - [Esportare i log di controllo delle cassette postali](https://docs.microsoft.com/Exchange/security-and-compliance/exchange-auditing-reports/export-mailbox-audit-logs)

    - [Eseguire un rapporto di accesso non proprietario della cassetta postale](https://docs.microsoft.com/Exchange/security-and-compliance/exchange-auditing-reports/non-owner-mailbox-access-report)

- Per impostazione predefinita, i record del registro di controllo della cassetta postale vengono conservati per 90 giorni prima di essere eliminati. È possibile modificare il limite di validità dei record del registro di controllo utilizzando il parametro *AuditLogAgeLimit* sul cmdlet **Set-Mailbox** in Exchange Online PowerShell. Tuttavia, l'aumento di questo valore non consente di cercare eventi che hanno più di 90 giorni nel log di controllo.

  Se si aumenta il limite di validità, è necessario utilizzare il cmdlet [Search-MailboxAuditLog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-mailboxauditlog) in Exchange Online PowerShell per eseguire una ricerca nel registro di controllo della cassetta postale dell'utente per i record precedenti a 90 giorni.

- Se la proprietà *AuditLogAgeLimit* di una cassetta postale è stata modificata prima del controllo delle cassette postali attivata per impostazione predefinita per l'organizzazione, il periodo di validità del registro di controllo esistente della cassetta postale non è stato modificato. In altre parole, il controllo delle cassette postali per impostazione predefinita non influisce sul limite di validità corrente dei record di controllo delle cassette postali.

- Per modificare il valore di *AuditLogAgeLimit* in una cassetta postale di un gruppo di Microsoft 365, `-GroupMailbox` è necessario includere l'opzione nel comando **Set-Mailbox** .

- I record del registro di controllo delle cassette postali sono archiviati in una sottocartella (denominata *Audit*) nella cartella elementi ripristinabili nella cassetta postale di ogni utente. Tenere presenti le considerazioni seguenti sui record di controllo delle cassette postali e sulla cartella elementi ripristinabili:

  - I record di controllo delle cassette postali sono confrontati con la quota di archiviazione della cartella elementi ripristinabili, che è 30 GB per impostazione predefinita (la quota di avviso è 20). La quota di archiviazione viene automaticamente aumentata a 100 GB (con una quota di avviso di 90 GB) quando:

    - Un blocco viene inserito in una cassetta postale.

    - La cassetta postale viene assegnata a un criterio di conservazione nel centro conformità.

  - I record di controllo della cassetta postale contano anche rispetto al limite della cartella [per la cartella elementi ripristinabili](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#mailbox-folder-limits). È possibile archiviare un massimo di 3 milioni elementi (record di controllo) nella sottocartella controlli.

    > [!NOTE]
    > È improbabile che il controllo delle cassette postali per impostazione predefinita influenzi la quota di archiviazione o il limite della cartella per la cartella elementi ripristinabili.

    - È possibile eseguire il comando seguente in PowerShell di Exchange Online per visualizzare le dimensioni e il numero di elementi nella sottocartella revisioni nella cartella elementi ripristinabili:

      ```PowerShell
      Get-MailboxFolderStatistics -Identity <MailboxIdentity> -FolderScope RecoverableItems | Where-Object {$_.Name -eq 'Audits'} | Format-List FolderPath,FolderSize,ItemsInFolder
      ```

    - Non è possibile accedere direttamente a un record del registro di controllo nella cartella elementi ripristinabili. al contrario, si utilizza il cmdlet **Search-MailboxAuditLog** o si cerca il log di controllo per individuare e visualizzare i record di controllo delle cassette postali.

- Se una cassetta postale viene conservata o assegnata a un criterio di conservazione nel centro conformità, i record del registro di controllo continuano a essere conservati per la durata definita dalla proprietà *AuditLogAgeLimit* della cassetta postale (90 giorni per impostazione predefinita). Per conservare i record del registro di controllo più a lungo per le cassette postali in blocco, è necessario aumentare il valore *AuditLogAgeLimit* della cassetta postale.

- In un ambiente multi-geografico il controllo delle cassette postali in aree geografiche diverse non è supportato. Ad esempio, se a un utente sono assegnate le autorizzazioni per accedere a una cassetta postale condivisa in un'area geografica diversa, le azioni sulla cassetta postale eseguite da tale utente non vengono registrate nel log di controllo della cassetta postale condivisa.
