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
ms.custom: seo-marvel-apr2020
description: La registrazione di controllo delle cassette postali è attivata per impostazione predefinita in Microsoft 365 (detto anche controllo delle cassette postali predefinito o controllo delle cassette postali attivato per impostazione predefinita). Ciò significa che determinate azioni eseguite da proprietari, delegati e amministratori delle cassette postali vengono registrate automaticamente in un registro di controllo delle cassette postali, in cui è possibile cercare le attività eseguite sulla cassetta postale.
ms.openlocfilehash: 859bd0dc633ece887fe11d57068fab4eb1395cdd
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311173"
---
# <a name="manage-mailbox-auditing"></a>Gestire il controllo delle cassette postali

A partire da gennaio 2019, Microsoft attiva la registrazione di controllo delle cassette postali per impostazione predefinita per tutte le organizzazioni. Ciò significa che determinate azioni eseguite dai proprietari delle cassette postali, dai delegati e dagli amministratori vengono registrate automaticamente e i record di controllo delle cassette postali corrispondenti saranno disponibili quando le si cerca nel registro di controllo delle cassette postali. Prima che il controllo delle cassette postali fosse attivato per impostazione predefinita, era necessario abilitarlo manualmente per ogni cassetta postale utente dell'organizzazione.

Ecco alcuni vantaggi del controllo delle cassette postali per impostazione predefinita:

- Il controllo viene abilitato automaticamente quando si crea una nuova cassetta postale. Non è necessario abilitarlo manualmente per i nuovi utenti.

- Non è necessario gestire le azioni delle cassette postali che vengono verificate. Un set predefinito di azioni della cassetta postale viene controllati per impostazione predefinita per ogni tipo di accesso (Amministratore, Delegato e Proprietario).

- Quando Microsoft rilascia una nuova azione della cassetta postale, l'azione potrebbe essere aggiunta automaticamente all'elenco delle azioni delle cassette postali sottoposte a controllo per impostazione predefinita (a causa dell'utente che ha la licenza appropriata). Ciò significa che non è necessario monitorare l'aggiunta di nuove azioni sulle cassette postali.

- Si dispone di un criterio di controllo delle cassette postali coerente nell'organizzazione (perché si stanno controllando le stesse azioni per tutte le cassette postali).

> [!NOTE]
>* L'importante da ricordare sul rilascio del controllo delle cassette postali per impostazione predefinita è: non è necessario eseguire operazioni per gestire il controllo delle cassette postali. Tuttavia, per ulteriori informazioni, personalizzare il controllo delle cassette postali dalle impostazioni predefinite o disattivarlo del tutto, questo argomento può essere utile.
>- Per impostazione predefinita, solo gli eventi di controllo delle cassette postali per gli utenti di E5 sono disponibili nelle ricerche nei registri di controllo nel Centro sicurezza & Conformità o tramite l'API Office 365 Management Activity. Per ulteriori informazioni, vedere la [sezione Ulteriori](#more-information) informazioni in questo argomento.

## <a name="verify-mailbox-auditing-on-by-default-is-turned-on"></a>Verifica che il controllo della cassetta postale sia attivato per impostazione predefinita

Per verificare che il controllo delle cassette postali sia attivato per impostazione predefinita per l'organizzazione, eseguire il comando seguente in [Exchange Online PowerShell:](/powershell/exchange/connect-to-exchange-online-powershell)

```PowerShell
Get-OrganizationConfig | Format-List AuditDisabled
```

Il valore **False indica** che il controllo delle cassette postali attivato per impostazione predefinita è abilitato per l'organizzazione. Questo valore dell'organizzazione per impostazione predefinita sostituisce l'impostazione di controllo delle cassette postali in cassette postali specifiche. Ad esempio, se il controllo delle cassette postali è disabilitato per una cassetta postale (la proprietà *AuditEnabled* è **False** nella cassetta postale), le azioni predefinite della cassetta postale verranno comunque verificate per la cassetta postale, perché il controllo delle cassette postali è abilitato per impostazione predefinita per l'organizzazione.

Per mantenere disabilitato il controllo delle cassette postali per cassette postali specifiche, configurare il bypass di controllo delle cassette postali per il proprietario della cassetta postale e per altri utenti a cui è stato delegato l'accesso alla cassetta postale. Per ulteriori informazioni, vedere la sezione Ignorare la registrazione [di controllo delle cassette](#bypass-mailbox-audit-logging) postali in questo argomento.

> [!NOTE]
> Quando il controllo delle cassette postali è attivato per impostazione predefinita per l'organizzazione, la proprietà *AuditEnabled* per le cassette postali interessate non verrà modificata da **False** a **True.** In altre parole, il controllo delle cassette postali attivato per impostazione predefinita ignora la *proprietà AuditEnabled* nelle cassette postali.

## <a name="supported-mailbox-types"></a>Tipi di cassette postali supportati

La tabella seguente mostra i tipi di cassette postali attualmente supportati dal controllo delle cassette postali per impostazione predefinita:

|**Tipo di cassetta postale**|**Supportato**|**Non supportato**|
|:---------|:---------:|:---------:|
|Cassette postali degli utenti|![Segno di spunta](../media/checkmark.png)||
|Cassette postali condivise|![Segno di spunta](../media/checkmark.png)||
|Microsoft 365 Cassette postali di gruppo|![Segno di spunta](../media/checkmark.png)||
|Cassette postali per le risorse||![Segno di spunta](../media/checkmark.png)|
|Cassette postali delle cartelle pubbliche||![Segno di spunta](../media/checkmark.png)|

## <a name="logon-types-and-mailbox-actions"></a>Tipi di accesso e azioni delle cassette postali

I tipi di accesso classificano l'utente che ha fatto le azioni di controllo sulla cassetta postale. Nell'elenco seguente vengono descritti i tipi di accesso utilizzati nella registrazione di controllo delle cassette postali:

- **Proprietario:** il proprietario della cassetta postale (l'account associato alla cassetta postale).

- **Delegato**:

  - Utente a cui è stata assegnata l'autorizzazione SendAs, SendOnBehalf o FullAccess a un'altra cassetta postale.

  - Un amministratore a cui è stata assegnata l'autorizzazione FullAccess per la cassetta postale di un utente.

- **Amministratore**:

  - La cassetta postale viene cercata con uno dei seguenti strumenti di Microsoft eDiscovery:

    - Ricerca contenuto nel Centro conformità.

    - eDiscovery o Advanced eDiscovery nel Centro conformità.

    - In-Place eDiscovery in Exchange Online.

  - È possibile accedere alla cassetta postale utilizzando l Microsoft Exchange Server EDITOR MAPI.

### <a name="mailbox-actions-for-user-mailboxes-and-shared-mailboxes"></a>Azioni delle cassette postali per le cassette postali degli utenti e le cassette postali condivise

Nella tabella seguente vengono descritte le azioni delle cassette postali disponibili nella registrazione di controllo delle cassette postali per le cassette postali utente e le cassette postali condivise.

- Un segno di spunta ( ![Segno di spunta](../media/checkmark.png)) indica che l'azione della cassetta postale può essere registrata per il tipo di accesso (non tutte le azioni sono disponibili per tutti i tipi di accesso).

- Un asterisco ( ) dopo il segno di spunta indica che l'azione della cassetta postale viene registrata <sup>\*</sup> per impostazione predefinita per il tipo di accesso.

- Tenere presente che un amministratore con autorizzazione accesso completo a una cassetta postale è considerato un delegato.

|**Azione cassetta postale**|**Descrizione**|**Admin**|**Delegato**|**Proprietario**|
|:---------|:---------|:---------:|:---------:|:---------:|
|**AddFolderPermissions**|**Nota:** anche se questo valore viene accettato come azione della cassetta postale, è già incluso nell'azione **UpdateFolderPermissions** e non viene controllati separatamente. In altre parole, non usare questo valore.||||
|**ApplyRecord**|Un elemento viene etichettato come record.|![Segno di spunta](../media/checkmark.png)<sup>\*</sup>|![Segno di spunta](../media/checkmark.png)<sup>\*</sup>|![Segno di spunta](../media/checkmark.png)<sup>\*</sup>|
|**Copia**|Messaggio copiato in un'altra cartella.|![Segno di spunta](../media/checkmark.png)|||
|**Creare**|Un elemento è stato creato nella cartella Calendario, Contatti, Note o Attività nella cassetta postale (ad esempio, viene creata una nuova convocazione di riunione). La creazione, l'invio o la ricezione di un messaggio non viene controllata, così come la creazione di una cartella della cassetta postale.|![Segno di spunta](../media/checkmark.png)<sup>\*</sup>|![Segno di spunta](../media/checkmark.png)<sup>\*</sup>|![Segno di spunta](../media/checkmark.png)|
|**Predefinita**||![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|
|**FolderBind**|Accesso effettuato a una cartella della cassetta postale. Tale azione viene registrata anche quando l'amministratore o un delegato apre la cassetta postale.<br/><br/> **Nota:** i record di controllo per le azioni di associazione delle cartelle eseguite dai delegati vengono consolidati. Viene generato un record di controllo per l'accesso alle singole cartelle entro un periodo di 24 ore.|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)||
|**HardDelete**|Messaggio eliminato dalla cartella Elementi ripristinabili.|![Segno di spunta](../media/checkmark.png)<sup>\*</sup>|![Segno di spunta](../media/checkmark.png)<sup>\*</sup>|![Segno di spunta](../media/checkmark.png)<sup>\*</sup>|
|**MailItemsAccessed**|I client e i protocolli di posta elettronica a cui si accede ai dati di posta sono accessibili. Questo valore è disponibile solo per gli utenti della sottoscrizione di componenti aggiuntivi E5 o E5 Compliance. Per ulteriori informazioni, vedere [Set up Advanced Audit. ](set-up-advanced-audit.md)|![Segno di spunta](../media/checkmark.png)<sup>\*</sup>|![Segno di spunta](../media/checkmark.png)<sup>\*</sup>|![Segno di spunta](../media/checkmark.png)<sup>\*</sup>|
|**MailboxLogin**|L'utente ha eseguito l'accesso alla propria cassetta postale. |||![Segno di spunta](../media/checkmark.png)|
|**MessageBind**|Un messaggio è stato visualizzato nel riquadro di anteprima o aperto da un amministratore. **Nota:** sebbene questo valore sia accettato come azione della cassetta postale, queste azioni non vengono più registrate.|![Segno di spunta](../media/checkmark.png)|||
|**ModifyFolderPermissions**|**Nota:** anche se questo valore viene accettato come azione della cassetta postale, è già incluso nell'azione **UpdateFolderPermissions** e non viene controllati separatamente. In altre parole, non usare questo valore.||||
|**Move**|Messaggio spostato in un'altra cartella.|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|
|**MoveToDeletedItems**|Messaggio eliminato e spostato nella cartella Posta eliminata.|![Segno di spunta](../media/checkmark.png)<sup>\*</sup>|![Segno di spunta](../media/checkmark.png)<sup>\*</sup>|![Segno di spunta](../media/checkmark.png)<sup>\*</sup>|
|**RecordDelete**|Un elemento etichettato come record è stato eliminato in modo reversibile (spostato nella cartella Elementi ripristinabili). Gli elementi etichettati come record non possono essere eliminati definitivamente (eliminati dalla cartella Elementi ripristinabili).|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|
|**RemoveFolderPermissions**|**Nota:** anche se questo valore viene accettato come azione della cassetta postale, è già incluso nell'azione **UpdateFolderPermissions** e non viene controllati separatamente. In altre parole, non usare questo valore.||||
|**Send**|L'utente invia un messaggio di posta elettronica, risponde a un messaggio di posta elettronica o inoltra un messaggio di posta elettronica. Questo valore è disponibile solo per gli utenti della sottoscrizione di componenti aggiuntivi E5 o E5 Compliance. Per ulteriori informazioni, vedere [Set up Advanced Audit for users](set-up-advanced-audit.md).|![Segno di spunta](../media/checkmark.png)<sup>\*</sup>|![Segno di spunta](../media/checkmark.png)<sup>\*</sup>|![Segno di spunta](../media/checkmark.png)<sup>\*</sup>|
|**SendAs**|Messaggio inviato utilizzando l'autorizzazione SendAs. Ciò significa che un altro utente ha inviato il messaggio come se provenisse dal proprietario della cassetta postale.|![Segno di spunta](../media/checkmark.png)<sup>\*</sup>|![Segno di spunta](../media/checkmark.png)<sup>\*</sup>||
|**SendOnBehalf**|Messaggio inviato utilizzando l'autorizzazione SendOnBehalf. Ciò significa che un altro utente ha inviato il messaggio per conto del proprietario della cassetta postale. Il messaggio indica al destinatario la persona per conto della quale è stato inviato il messaggio e l’utente che ha effettivamente inviato il messaggio.|![Segno di spunta](../media/checkmark.png)<sup>\*</sup>|![Segno di spunta](../media/checkmark.png)<sup>\*</sup>||
|**SoftDelete**|Messaggio eliminato in modo definitivo dalla cartella Posta eliminata. Gli elementi eliminati temporaneamente vengono spostati nella cartella Elementi ripristinabili.|![Segno di spunta](../media/checkmark.png)<sup>\*</sup>|![Segno di spunta](../media/checkmark.png)<sup>\*</sup>|![Segno di spunta](../media/checkmark.png)<sup>\*</sup>|
|**Aggiorna**|Modifiche apportate a un messaggio o alle relative proprietà.|![Segno di spunta](../media/checkmark.png)<sup>\*</sup>|![Segno di spunta](../media/checkmark.png)<sup>\*</sup>|![Segno di spunta](../media/checkmark.png)<sup>\*</sup>|
|**UpdateCalendarDelegation**|A una cassetta postale è stata assegnata una delega del calendario. La delega del calendario assegna a un altro utente nella stessa organizzazione le autorizzazioni per la gestione del calendario del proprietario della cassetta postale.|![Segno di spunta](../media/checkmark.png)<sup>\*</sup>||![Segno di spunta](../media/checkmark.png)<sup>\*</sup>|
|**UpdateComplianceTag**|Un'etichetta di conservazione diversa viene applicata a un elemento di posta (a un elemento può essere assegnata una sola etichetta di conservazione).|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|
|**UpdateFolderPermissions**|Un'autorizzazione per una cartella è stata cambiata. Le autorizzazioni per le cartelle determinano quali utenti dell'organizzazione possono accedere alle cartelle di una cassetta postale e ai messaggi che contengono.|![Segno di spunta](../media/checkmark.png)<sup>\*</sup>|![Segno di spunta](../media/checkmark.png)<sup>\*</sup>|![Segno di spunta](../media/checkmark.png)<sup>\*</sup>|
|**UpdateInboxRules**|Una regola di Posta in arrivo è stata aggiunta, rimossa o modificata. Le regole di Posta in arrivo vengono utilizzate per elaborare i messaggi nella cartella Posta in arrivo dell'utente in base alle condizioni specificate ed eseguire azioni quando vengono soddisfatte le condizioni di una regola, ad esempio spostando un messaggio in una cartella specificata o eliminando un messaggio.|![Segno di spunta](../media/checkmark.png)<sup>\*</sup>|![Segno di spunta](../media/checkmark.png)<sup>\*</sup>|![Segno di spunta](../media/checkmark.png)<sup>\*</sup>|

> [!IMPORTANT]
> Se le azioni della cassetta postale sono  state personalizzate per controllare qualsiasi tipo di accesso prima che il controllo delle cassette postali per impostazione predefinita fosse abilitato nell'organizzazione, le impostazioni personalizzate vengono mantenute nella cassetta postale e non vengono sovrascritte dalle azioni predefinite della cassetta postale come descritto in questa sezione. Per ripristinare i valori predefiniti delle azioni delle cassette postali di controllo (operazione che è possibile eseguire in qualsiasi momento), vedere la sezione [Ripristinare](#restore-the-default-mailbox-actions) le azioni predefinite della cassetta postale più avanti in questo argomento.

### <a name="mailbox-actions-for-microsoft-365-group-mailboxes"></a>Azioni delle cassette postali per Microsoft 365 di gruppo

Il controllo delle cassette postali su per impostazione predefinita porta la registrazione di controllo delle cassette postali Microsoft 365 cassette postali di gruppo, ma non è possibile personalizzare ciò che viene registrato (non è possibile aggiungere o rimuovere le azioni delle cassette postali registrate per qualsiasi tipo di accesso).

Nella tabella seguente vengono descritte le azioni delle cassette postali registrate per impostazione predefinita Microsoft 365 cassette postali di gruppo per ogni tipo di accesso.

Tenere presente che un amministratore con autorizzazione di accesso completo a Microsoft 365 cassetta postale del gruppo è considerato un delegato.

|**Azione cassetta postale**|**Descrizione**|**Admin**|**Delegato**|**Proprietario**|
|:---------|:---------|:---------:|:---------:|:---------:|
|**Creare**|Creazione di un elemento del calendario. La creazione, l'invio o la ricezione di un messaggio non viene controllata,|![Segno di spunta](../media/checkmark.png)<sup>\*</sup>|![Segno di spunta](../media/checkmark.png)<sup>\*</sup>||
|**HardDelete**|Messaggio eliminato dalla cartella Elementi ripristinabili.|![Segno di spunta](../media/checkmark.png)<sup>\*</sup>|![Segno di spunta](../media/checkmark.png)<sup>\*</sup>|![Segno di spunta](../media/checkmark.png)<sup>\*</sup>|
|**MoveToDeletedItems**|Messaggio eliminato e spostato nella cartella Posta eliminata.|![Segno di spunta](../media/checkmark.png)<sup>\*</sup>|![Segno di spunta](../media/checkmark.png)<sup>\*</sup>|![Segno di spunta](../media/checkmark.png)<sup>\*</sup>|
|**SendAs**|Un messaggio è stato inviato con l'autorizzazione SendAs,|![Segno di spunta](../media/checkmark.png)<sup>\*</sup>|![Segno di spunta](../media/checkmark.png)<sup>\*</sup>||
|**SendOnBehalf**|Un messaggio è stato inviato con l'autorizzazione SendOnBehalf, |![Segno di spunta](../media/checkmark.png)<sup>\*</sup>|![Segno di spunta](../media/checkmark.png)<sup>\*</sup>||
|**SoftDelete**|Messaggio eliminato in modo definitivo dalla cartella Posta eliminata. Gli elementi eliminati temporaneamente vengono spostati nella cartella Elementi ripristinabili.|![Segno di spunta](../media/checkmark.png)<sup>\*</sup>|![Segno di spunta](../media/checkmark.png)<sup>\*</sup>|![Segno di spunta](../media/checkmark.png)<sup>\*</sup>|
|**Aggiorna**|Modifiche apportate a un messaggio o alle relative proprietà.|![Segno di spunta](../media/checkmark.png)<sup>\*</sup>|![Segno di spunta](../media/checkmark.png)<sup>\*</sup>|![Segno di spunta](../media/checkmark.png)<sup>\*</sup>|

### <a name="verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type"></a>Verificare che le azioni predefinite della cassetta postale vengano registrate per ogni tipo di accesso

Per impostazione predefinita, il controllo delle cassette postali aggiunge una *nuova proprietà DefaultAuditSet* a tutte le cassette postali. Il valore di questa proprietà indica se le azioni predefinite della cassetta postale (gestite da Microsoft) vengono verificate nella cassetta postale.

Per visualizzare il valore nelle cassette postali utente o nelle cassette postali condivise, sostituire con il nome, l'alias, l'indirizzo di posta elettronica o il nome dell'entità utente (nome utente) della cassetta postale ed eseguire il comando seguente \<MailboxIdentity\> in Exchange Online PowerShell:

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Format-List DefaultAuditSet
```

Per visualizzare il valore nelle cassette postali Microsoft 365 gruppo, sostituire con il nome, l'alias o l'indirizzo di posta elettronica della cassetta postale condivisa ed eseguire il comando \<MailboxIdentity\> seguente in Exchange Online PowerShell:

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> -GroupMailbox | Format-List DefaultAuditSet
```

Il valore `Admin, Delegate, Owner` indica:

- Le azioni predefinite delle cassette postali per tutti e tre i tipi di accesso vengono verificate. Questo è l'unico valore visualizzato nelle cassette postali Microsoft 365 gruppo.

- Un amministratore *non ha modificato* le azioni delle cassette postali verificate per alcun tipo di accesso su una cassetta postale utente o una cassetta postale condivisa. Si noti che questo è lo stato predefinito dopo che il controllo delle cassette postali è attivato per impostazione predefinita inizialmente nell'organizzazione.

Se un amministratore ha modificato le azioni della cassetta postale che vengono verificate per un tipo di accesso (utilizzando i parametri *AuditAdmin,* *AuditDelegate* o *AuditOwner* nel cmdlet **Set-Mailbox),** il valore della proprietà sarà diverso.

Ad esempio, il valore `Owner` della *proprietà DefaultAuditSet* su una cassetta postale utente o una cassetta postale condivisa indica:

- Le azioni predefinite della cassetta postale per il proprietario della cassetta postale vengono controllati.

- Le azioni delle cassette postali verificate per i tipi di accesso e sono `Delegate` state modificate rispetto alle azioni `Admin` predefinite.

Un valore vuoto per la *proprietà DefaultAuditSet* indica che le azioni della cassetta postale per tutti e tre i tipi di accesso sono state modificate nella cassetta postale dell'utente o in una cassetta postale condivisa.

Per ulteriori informazioni, vedere la sezione Modificare o ripristinare le azioni [della cassetta postale](#change-or-restore-mailbox-actions-logged-by-default) registrate per impostazione predefinita in questo argomento

### <a name="display-the-mailbox-actions-that-are-being-logged-on-mailboxes"></a>Visualizzare le azioni delle cassette postali che vengono registrate nelle cassette postali

Per visualizzare le azioni delle cassette postali attualmente registrate nelle cassette postali degli utenti o nelle cassette postali condivise, sostituire con il nome, l'alias, l'indirizzo di posta elettronica o il nome dell'entità utente (nome utente) della cassetta postale ed eseguire uno o più dei comandi seguenti \<MailboxIdentity\> in Exchange Online PowerShell.

> [!NOTE]
> Anche se è possibile aggiungere l'opzione ai seguenti comandi Get-Mailbox per Microsoft 365 cassette postali di gruppo, non credere ai `-GroupMailbox` valori restituiti.  Le azioni predefinite e statiche delle cassette postali che vengono verificate per le cassette postali di Microsoft 365 Group sono descritte nella sezione Azioni delle cassette postali per le cassette postali di Microsoft 365 [Gruppo](#mailbox-actions-for-microsoft-365-group-mailboxes) più indietro in questo argomento.

#### <a name="owner-actions"></a>Azioni del proprietario

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditOwner
```

#### <a name="delegate-actions"></a>Azioni delegate

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditDelegate
```

#### <a name="admin-actions"></a>Azioni di amministrazione

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditAdmin
```

## <a name="change-or-restore-mailbox-actions-logged-by-default"></a>Modificare o ripristinare le azioni delle cassette postali registrate per impostazione predefinita

Come spiegato in precedenza, uno dei vantaggi principali dell'utilizzo del controllo delle cassette postali per impostazione predefinita è che non è necessario gestire le azioni delle cassette postali che vengono verificate. Microsoft esegue questa operazione automaticamente e verranno automaticamente aggiunti nuove azioni delle cassette postali da controllare per impostazione predefinita non appena vengono rilasciate.

Tuttavia, l'organizzazione potrebbe essere necessaria per controllare un set diverso di azioni delle cassette postali per le cassette postali degli utenti e le cassette postali condivise. Le procedure descritte in questa sezione illustrano come modificare le azioni delle cassette postali che vengono controllati per ogni tipo di accesso e come ripristinare le azioni predefinite gestite da Microsoft.

> [!IMPORTANT]
> Se si utilizzano le procedure seguenti per personalizzare le azioni delle cassette postali registrate nelle cassette postali degli utenti o nelle cassette postali condivise, le nuove azioni predefinite rilasciate da Microsoft non verranno automaticamente verificate in tali cassette postali. Sarà necessario aggiungere manualmente eventuali nuove azioni della cassetta postale all'elenco personalizzato di azioni.

### <a name="change-the-mailbox-actions-to-audit"></a>Modificare le azioni delle cassette postali da controllare

È possibile utilizzare i parametri *AuditAdmin,* *AuditDelegate* o *AuditOwner* nel cmdlet **Set-Mailbox** per modificare le azioni delle cassette postali che vengono controllati per le cassette postali degli utenti e le cassette postali condivise (le azioni di controllo per le cassette postali di un gruppo di Microsoft 365 non possono essere personalizzate).

È possibile utilizzare due metodi diversi per specificare le azioni della cassetta postale:

- *Sostituire* (sovrascrivere) le azioni esistenti della cassetta postale utilizzando la sintassi seguente: `action1,action2,...actionN` .

- *Aggiungere o rimuovere azioni* della cassetta postale senza influire sugli altri valori esistenti utilizzando la `@{Add="action1","action2",..."actionN"}` sintassi seguente: o `@{Remove="action1","action2",..."actionN"}` .

In questo esempio vengono cambiate le azioni della cassetta postale di amministrazione per la cassetta postale denominata "Gabriela Laureano" sovrascrivendo le azioni predefinite con SoftDelete e HardDelete.

```PowerShell
Set-Mailbox -Identity "Gabriela Laureano" -AuditAdmin HardDelete,SoftDelete
```

In questo esempio viene aggiunta l'azione proprietario MailboxLogin alla cassetta postale laura@contoso.onmicrosoft.com.

```PowerShell
Set-Mailbox -Identity laura@contoso.onmicrosoft.com -AuditOwner @{Add="MailboxLogin"}
```

In questo esempio viene rimossa l'azione delegata MoveToDeletedItems per la cassetta postale Discussione team.

```PowerShell
Set-Mailbox -Identity "Team Discussion" -AuditDelegate @{Remove="MoveToDeletedItems"}
```

Indipendentemente dal metodo utilizzato, la personalizzazione delle azioni delle cassette postali verificate sulle cassette postali degli utenti o sulle cassette postali condivise ha i risultati seguenti:

- Per il tipo di accesso personalizzato, le azioni delle cassette postali verificate non vengono più gestite da Microsoft.

- Il tipo di accesso personalizzato non viene più visualizzato nel valore della proprietà *DefaultAuditSet* per la cassetta postale come [descritto in precedenza.](#verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type)

### <a name="restore-the-default-mailbox-actions"></a>Ripristinare le azioni predefinite delle cassette postali

Se sono state personalizzate le azioni della cassetta postale che vengono verificate su una cassetta postale utente o una cassetta postale condivisa, è possibile ripristinare le azioni predefinite della cassetta postale per uno o tutti i tipi di accesso utilizzando questa sintassi:

```PowerShell
Set-Mailbox -Identity <MailboxIdentity> -DefaultAuditSet <Admin | Delegate | Owner>
```

È possibile specificare più *valori DefaultAuditSet* separati da virgole

**Nota:** le procedure seguenti non si applicano Microsoft 365 cassette postali di gruppo (sono limitate alle azioni predefinite come descritto [qui).](#mailbox-actions-for-microsoft-365-group-mailboxes)

In questo esempio vengono ripristinate le azioni predefinite delle cassette postali di controllo per tutti i tipi di accesso nella cassetta postale mark@contoso.onmicrosoft.com.

```PowerShell
Set-Mailbox -Identity mark@contoso.onmicrosoft.com -DefaultAuditSet Admin,Delegate,Owner
```

In questo esempio vengono ripristinate le azioni predefinite delle cassette postali di controllo per il tipo di accesso Amministratore nel chris@contoso.onmicrosoft.com, ma le azioni personalizzate delle cassette postali di controllo per i tipi di accesso Delegato e Proprietario vengono comunque eseguite.

```PowerShell
Set-Mailbox -Identity chris@contoso.onmicrosoft.com -DefaultAuditSet Admin
```

Il ripristino delle azioni predefinite delle cassette postali di controllo per un tipo di accesso ha i seguenti risultati:

- L'elenco corrente delle azioni delle cassette postali viene sostituito con le azioni predefinite della cassetta postale per il tipo di accesso.

- Tutte le nuove azioni delle cassette postali rilasciate da Microsoft vengono aggiunte automaticamente all'elenco delle azioni verificate per il tipo di accesso.

- Il *valore della proprietà DefaultAuditSet* per la cassetta postale viene aggiornato in modo da includere il tipo di accesso ripristinato.

## <a name="turn-off-mailbox-auditing-on-by-default-for-your-organization"></a>Disattivare il controllo delle cassette postali per impostazione predefinita per l'organizzazione

È possibile disattivare il controllo delle cassette postali per impostazione predefinita per l'intera organizzazione eseguendo il comando seguente in Exchange Online PowerShell:

```PowerShell
Set-OrganizationConfig -AuditDisabled $true
```

La disattivazione del controllo delle cassette postali per impostazione predefinita ha i seguenti risultati:

- Il controllo delle cassette postali è disabilitato per l'organizzazione.

- Dal momento in cui è stato disabilitato il controllo delle cassette postali per impostazione predefinita, non viene verificata alcuna azione della cassetta postale, anche se il controllo è abilitato su una cassetta postale (la proprietà *AuditEnabled* nella cassetta postale è **True**).

- Il controllo delle cassette postali non è abilitato per le nuove cassette postali e l'impostazione della proprietà *AuditEnabled* su **True** per una cassetta postale nuova o esistente verrà ignorata.

- Tutte le impostazioni di associazione di bypass di controllo delle cassette postali (configurate utilizzando il cmdlet **Set-MailboxAuditBypassAssociation)** vengono ignorate.

- I record di controllo delle cassette postali esistenti vengono conservati fino alla scadenza del limite di validità del registro di controllo per il record.

### <a name="turn-on-mailbox-auditing-on-by-default"></a>Attivare il controllo delle cassette postali per impostazione predefinita

Per riattivare il controllo delle cassette postali per l'organizzazione, eseguire il comando seguente in Exchange Online PowerShell:

```PowerShell
Set-OrganizationConfig -AuditDisabled $false
```

## <a name="bypass-mailbox-audit-logging"></a>Escludi la registrazione di controllo della cassetta postale

Attualmente, non puoi disabilitare il controllo per cassette postali specifiche quando il controllo delle cassette postali è attivato per impostazione predefinita nella tua organizzazione. Ad esempio, l'impostazione della proprietà della cassetta postale *AuditEnabled* su **False** viene ignorata.

Tuttavia, è comunque possibile utilizzare il cmdlet **Set-MailboxAuditBypassAssociation** in  Exchange Online PowerShell per impedire la registrazione di qualsiasi azione della cassetta postale da parte degli utenti specificati, indipendentemente dal punto in cui si verificano le azioni. Ad esempio:

- Le azioni del proprietario della cassetta postale eseguite dagli utenti ignorati non vengono registrate.

- Le azioni delegate eseguite dagli utenti ignorati sulle cassette postali di altri utenti (incluse le cassette postali condivise) non vengono registrate.

- Le azioni di amministrazione eseguite dagli utenti ignorati non vengono registrate.

Per ignorare la registrazione di controllo delle cassette postali per un utente specifico, sostituire con il nome, l'indirizzo di posta elettronica, l'alias o il nome dell'entità utente (nome utente) dell'utente ed \<MailboxIdentity\> eseguire il comando seguente:

```PowerShell
Set-MailboxAuditBypassAssociation -Identity <MailboxIdentity> -AuditByPassEnabled $true
```

Per verificare che il controllo sia escluso da un’utente specifico, esegui il seguente comando:

```PowerShell
Get-MailboxAuditBypassAssociation -Identity <MailboxIdentity> | Format-List AuditByPassEnabled
```

Il valore **True** indica che la registrazione di controllo delle cassette postali viene ignorata per l'utente.

## <a name="more-information"></a>Ulteriori informazioni

- Anche se l'accesso di controllo delle cassette postali per impostazione predefinita è abilitato per tutte le organizzazioni, solo gli utenti con licenze E5 restituiranno gli eventi del registro di controllo delle cassette postali nelle ricerche nei registri di controllo nel Centro sicurezza [&](search-the-audit-log-in-security-and-compliance.md) conformità o tramite l'API attività di gestione di [Office 365](/office/office-365-management-api/office-365-management-activity-api-reference) per impostazione **predefinita.**

  Per recuperare le voci del registro di controllo delle cassette postali per gli utenti senza licenze E5, è possibile:

  - Abilitare manualmente il controllo delle cassette postali sulle singole cassette postali (eseguire il comando , `Set-Mailbox -Identity <MailboxIdentity> -AuditEnabled $true` ). Dopo questa operazione, è possibile usare le ricerche nei log di controllo nel Centro sicurezza & conformità o tramite l'API Office 365 Attività di gestione.
  
    > [!NOTE]
    > Se il controllo delle cassette postali sembra già abilitato nella cassetta postale, ma le ricerche non restituiscono risultati, modificare il valore del parametro _AuditEnabled_ in e quindi `$false` tornare a `$true` .
  
  - Utilizzare i cmdlet seguenti in Exchange Online PowerShell:

    - [Search-MailboxAuditLog](/powershell/module/exchange/search-mailboxauditlog) per cercare utenti specifici nel registro di controllo delle cassette postali.

    - [New-MailboxAuditLogSearch](/powershell/module/exchange/new-mailboxauditlogsearch) per cercare utenti specifici nel registro di controllo delle cassette postali e per inviare i risultati tramite posta elettronica a destinatari specifici.

  - Utilizzare l Exchange ac (EAC) in Exchange Online per eseguire le operazioni seguenti:

    - [Esportare i log di controllo delle cassette postali](/Exchange/security-and-compliance/exchange-auditing-reports/export-mailbox-audit-logs)

    - [Eseguire un rapporto di accesso non proprietario della cassetta postale](/Exchange/security-and-compliance/exchange-auditing-reports/non-owner-mailbox-access-report)

- Per impostazione predefinita, i record del registro di controllo delle cassette postali vengono conservati per 90 giorni prima di essere eliminati. È possibile modificare il limite di validità per i record del registro di controllo utilizzando il *parametro AuditLogAgeLimit* nel cmdlet **Set-Mailbox** in Exchange Online PowerShell. Tuttavia, l'aumento di questo valore non consente di cercare eventi precedenti a 90 giorni nel registro di controllo.

  Se si aumenta il limite di validità, è necessario utilizzare il cmdlet [Search-MailboxAuditLog](/powershell/module/exchange/search-mailboxauditlog) in Exchange Online PowerShell per cercare nel registro di controllo delle cassette postali dell'utente i record precedenti a 90 giorni.

- Se è stata modificata la proprietà *AuditLogAgeLimit* per una cassetta postale prima che il controllo delle cassette postali sia attivato per impostazione predefinita per l'organizzazione, il limite di validità del registro di controllo esistente della cassetta postale non viene modificato. In altre parole, il controllo delle cassette postali per impostazione predefinita non influisce sul limite di validità corrente per i record di controllo delle cassette postali.

- Per modificare il *valore AuditLogAgeLimit* in una cassetta postale di Microsoft 365 gruppo, è necessario includere l'opzione `-GroupMailbox` nel comando **Set-Mailbox.**

- I record del registro di controllo delle cassette postali vengono archiviati in una sottocartella (denominata *Controlli*) nella cartella Elementi ripristinabili nella cassetta postale di ogni utente. Tenere presente quanto segue sui record di controllo delle cassette postali e sulla cartella Elementi ripristinabili:

  - I record di controllo delle cassette postali vengono conteggiati in base alla quota di archiviazione della cartella Elementi ripristinabili, che è di 30 GB per impostazione predefinita (la quota di avviso è 20 GB). La quota di archiviazione viene automaticamente aumentata a 100 GB (con una quota di avviso di 90 GB) quando:

    - Un blocco viene effettuato su una cassetta postale.

    - La cassetta postale viene assegnata a un criterio di conservazione nel Centro conformità.

  - I record di controllo delle cassette postali vengono inoltre conteggiati rispetto al limite di [cartelle per la cartella Elementi ripristinabili.](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#mailbox-folder-limits) È possibile archiviare un massimo di 3 milioni di elementi (record di controllo) nella sottocartella Controlli.

    > [!NOTE]
    > È improbabile che il controllo delle cassette postali su per impostazione predefinita inciderà sulla quota di archiviazione o sul limite di cartelle per la cartella Elementi ripristinabili.

    - È possibile eseguire il comando seguente in Exchange Online PowerShell per visualizzare le dimensioni e il numero di elementi nella sottocartella Controlli nella cartella Elementi ripristinabili:

      ```PowerShell
      Get-MailboxFolderStatistics -Identity <MailboxIdentity> -FolderScope RecoverableItems | Where-Object {$_.Name -eq 'Audits'} | Format-List FolderPath,FolderSize,ItemsInFolder
      ```

    - Non è possibile accedere direttamente a un record del registro di controllo nella cartella Elementi ripristinabili. al contrario, si utilizza il cmdlet **Search-MailboxAuditLog** o si cerca nel registro di controllo per trovare e visualizzare i record di controllo delle cassette postali.

- Se una cassetta postale viene messa in attesa o assegnata a un criterio di conservazione nel Centro conformità, i record del registro di controllo vengono ancora conservati per la durata definita dalla proprietà *AuditLogAgeLimit* della cassetta postale (90 giorni per impostazione predefinita). Per conservare più a lungo i record del registro di controllo per le cassette postali in attesa, è necessario aumentare il valore *AuditLogAgeLimit* della cassetta postale.

- In un ambiente multi-geografico il controllo delle cassette postali in aree geografiche diverse non è supportato. Ad esempio, se a un utente sono assegnate le autorizzazioni per accedere a una cassetta postale condivisa in un'area geografica diversa, le azioni sulla cassetta postale eseguite da tale utente non vengono registrate nel log di controllo della cassetta postale condivisa.