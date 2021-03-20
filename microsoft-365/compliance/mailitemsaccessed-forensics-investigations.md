---
title: Usare Audit avanzato per le indagini sugli account compromessi
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Usare l'azione di controllo delle cassette postali MailItemsAccessed per eseguire indagini forensi sugli account utente compromessi.
ms.openlocfilehash: e9dda101b330f6632e66c226156df3497ac38453
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50903482"
---
# <a name="use-advanced-audit-to-investigate-compromised-accounts"></a>Usare Audit avanzato per le indagini sugli account compromessi

La compromissione di un account utente, detta anche *takeover*, è un tipo di attacco in cui un utente malintenzionato acquisisce la proprietà di un account e agisce come se fosse il vero proprietario. A volte questi tipi di attacchi causano più danni di quanto previsto dall'utente malintenzionato. Quando si analizzano gli account di posta elettronica compromessi, è necessario presumere che i dati di posta elettronica compromessi siano di più rispetto a quanto indicato tracciando la presenza effettiva dell'autore dell'attacco. A seconda del tipo di dati contenuti nei messaggi di posta elettronica, è necessario presumere che siano state compromesse informazioni riservate o esporsi a sanzioni, a meno che non sia possibile dimostrare che non sono state esposte informazioni sensibili. Ad esempio, le organizzazioni che devono essere conformi all'HIPAA sono soggette a sanzioni elevate se vengono esposte le informazioni sanitarie dei pazienti (PHI). In questi casi, è improbabile che i pirati informatici siano interessati ai dati PHI, ma le organizzazioni devono comunque segnalare una violazione dei dati, a meno che non possano dimostrare il contrario.

Per semplificare le indagini sugli account di posta elettronica compromessi, ora controlliamo l'accesso ai dati di posta elettronica in base ai protocolli di posta elettronica e ai client con l'azione di controllo delle cassette postali *MailItemsAccessed*. Questa nuova azione sottoposta a controllo aiuterà gli investigatori a comprendere meglio le violazioni dei dati di posta elettronica e a restringere l'ambito a specifici messaggi che potrebbero essere stati compromessi. L'uso di questa nuova azione di controllo è la difesa forense, per poter attestare che un determinato elemento di dati di posta non è stato compromesso. Se un utente malintenzionato ha ottenuto l'accesso a un determinato messaggio di posta elettronica, Exchange Online controlla l'evento anche se non c'è alcuna indicazione che l'elemento di posta elettronica sia stato effettivamente letto.

## <a name="the-mailitemsaccessed-mailbox-auditing-action"></a>Azione di controllo delle cassette postali MailItemsAccessed

La nuova azione MailItemsAccessed fa parte della nuova funzionalità [Audit avanzato](advanced-audit.md). È parte del [controllo delle cassette postali di Exchange](/office365/securitycompliance/enable-mailbox-auditing#mailbox-auditing-actions) ed è abilitata per impostazione predefinita per gli utenti a cui è assegnata una licenza di Office 365 o Microsoft 365 E5 o per le organizzazioni con un abbonamento al componente aggiuntivo Microsoft 365 E5 Compliance.

L'azione di controllo delle cassette postali MailItemsAccessed copre tutti i protocolli di posta elettronica: POP, IMAP, MAPI, EWS, Exchange ActiveSync e REST. Copre anche entrambi i tipi di accesso alla posta elettronica: *sync* e *bind*.

### <a name="auditing-sync-access"></a>Controllo dell'accesso per sincronizzazione

Le operazioni Sync vengono registrate solo quando si accede a una cassetta postale da una versione desktop del client Outlook per Windows o Mac. Durante l'operazione Sync, in genere questi client scaricano un set di elementi di posta di grandi dimensioni dal cloud a un computer locale. Il volume di controllo per le operazioni Sync è enorme. Per questo motivo, invece di generare un record di controllo per ogni elemento di posta elettronica sincronizzato, viene generato solo un evento di controllo per la cartella di posta contenente gli elementi che sono stati sincronizzati. Questo presuppone che *tutti* gli elementi di posta nella cartella sincronizzata siano stati compromessi. Il tipo di accesso viene registrato nel campo OperationProperties del record di controllo. 

Vedere il passaggio 2 nella sezione [Usare i record di controllo MailItemsAccessed per le indagini forensi](#use-mailitemsaccessed-audit-records-for-forensic-investigations) per un esempio di visualizzazione del tipo di accesso Sync in un record di controllo.

### <a name="auditing-bind-access"></a>Controllo dell'accesso per binding

Un'operazione Bind è un singolo accesso a un messaggio di posta elettronica. Per l'accesso per binding, l'InternetMessageId dei singoli messaggi verrà registrato nel record di controllo. L'azione di controllo MailItemsAccessed registra le operazioni Bind e le aggrega in un singolo record di controllo. Tutte le operazioni Bind che si verificano in un intervallo di due minuti vengono aggregate in un singolo record di controllo nel campo delle cartelle all'interno della proprietà AuditData. Ogni messaggio a cui è stato eseguito l'accesso è identificato dal relativo InternetMessageId. Il numero di operazioni di binding aggregate nel record viene visualizzato nel campo OperationCount della proprietà AuditData.

Vedere il passaggio 4 nella sezione [Usare i record di controllo MailItemsAccessed per le indagini forensi](#use-mailitemsaccessed-audit-records-for-forensic-investigations) per un esempio di visualizzazione del tipo di accesso Bind in un record di controllo.

### <a name="throttling-of-mailitemsaccessed-audit-records"></a>Limitazione dei record di controllo MailItemsAccessed

Se in meno di 24 ore vengono generati più di 1.000 record di controllo MailItemsAccessed, Exchange Online smetterà di generare i record di controllo per l'attività MailItemsAccessed. Quando una cassetta postale viene limitata, l'attività MailItemsAccessed non viene registrata per le 24 ore successive. Se questo avviene, è possibile che durante questo periodo la cassetta postale sia stata compromessa. La registrazione dell'attività MailItemsAccessed verrà ripresa dopo un periodo di 24 ore.  

Ecco alcuni aspetti da tenere presenti sulla limitazione:

- Meno dell'1% di tutte le cassette postali in Exchange Online è sottoposto a limitazione

- Quando una cassetta postale è limitata, solo i record di controllo per l'attività MailItemsAccessed non vengono controllati. Le altre azioni di controllo delle cassette postali non sono interessate.

- Le cassette postali vengono limitate solo per le operazioni Bind. I record di controllo delle operazioni Sync non vengono limitati.

- Se una cassetta postale viene limitata, si può presupporre che ci siano attività MailItemsAccessed che non sono state registrate nei log di controllo.

Vedere il passaggio 1 nella sezione [Usare i record di controllo MailItemsAccessed per le indagini forensi](#use-mailitemsaccessed-audit-records-for-forensic-investigations) per un esempio di visualizzazione della proprietà IsThrottled in un record di controllo.

## <a name="use-mailitemsaccessed-audit-records-for-forensic-investigations"></a>Usare i record di controllo MailItemsAccessed per le indagini forensi

Il controllo delle cassette postali genera record di controllo per l'accesso ai messaggi di posta elettronica, per offrire la certezza che i messaggi di posta elettronica non siano stati compromessi. Per questo motivo, nei casi in cui non siamo certi che sia stato eseguito l'accesso a determinati dati, presupponiamo che sia avvenuto, registrando tutte le attività di accesso alla posta.

In genere i record di controllo MailItemsAccessed vengono usati a scopi forensi dopo la risoluzione di una violazione dei dati e l'espulsione dell'autore dell'attacco. Per avviare l'indagine, è necessario identificare il set di cassette postali che sono state compromesse e determinare il periodo di tempo in cui l'utente malintenzionato ha avuto accesso alle cassette postali dell'organizzazione. Quindi, è possibile usare i cmdlet **UnifiedAuditLog** o **Search-MailboxAuditLog** in [PowerShell di Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell) per cercare i record di controllo che corrispondono alla violazione dei dati. 

È possibile eseguire uno dei comandi seguenti per cercare i record di controllo MailItemsAccessed:

**Log di controllo unificato**

```powershell
Search-UnifiedAuditLog -StartDate 01/06/2020 -EndDate 01/20/2020 -UserIds <user1,user2> -Operations MailItemsAccessed -ResultSize 1000
```

**Log di controllo cassetta postale**

```powershell
Search-MailboxAuditLog -Identity <user> -StartDate 01/06/2020 -EndDate 01/20/2020 -Operations MailItemsAccessed -ResultSize 1000 -ShowDetails
```

> [!TIP]
> Una delle principali differenze tra i due cmdlet è che è possibile usare **Search-UnifiedAuditLog** per cercare i record di controllo per le attività eseguite da uno o più utenti. Il motivo è che *UserId* è un parametro multivalore. Il cmdlet **Search-MailboxAuditLog** cerca nel log di controllo della cassetta postale un singolo utente.

Di seguito sono illustrati i passaggi per usare i record di controllo MailItemsAccessed per analizzare un attacco con compromissione di un account utente. Ogni passaggio mostra la sintassi dei comandi per i cmdlet **Search-UnifiedAuditLog** o **Search-MailboxAuditLog**.

1. Controllare se la cassetta postale è stata limitata. In tal caso, alcuni record di controllo delle cassette postali non sono stati registrati. Se alcuni record di controllo hanno il valore "IsThrottled" uguale a "True", bisogna presupporre che, per le 24 ore successive alla generazione del record, l'accesso alla cassetta postale non è stato controllato e che tutti i dati di posta sono stati compromessi.

   Per cercare i record MailItemsAccessed in cui la cassetta postale era limitata, eseguire il comando seguente:

   **Log di controllo unificato**
 
   ```powershell
   Search-UnifiedAuditLog -StartDate 01/06/2020 -EndDate 01/20/2020 -UserIds <user1,user2> -Operations MailItemsAccessed -ResultSize 1000 | Where {$_.AuditData -like '*"IsThrottled","Value":"True"*'} | FL
   ```

   **Log di controllo cassetta postale**

   ```powershell
   Search-MailboxAuditLog -StartDate 01/06/2020 -EndDate 01/20/2020 -Identity <user> -Operations MailItemsAccessed -ResultSize 10000 -ShowDetails | Where {$_.OperationProperties -like "*IsThrottled:True*"} | FL
   ```

2. Controllare le attività di sincronizzazione. Se un utente malintenzionato usa un client di posta elettronica per scaricare i messaggi in una cassetta postale, può disconnettere il computer da Internet e accedere ai messaggi in locale senza interagire con il server. Questo significa che il controllo delle cassette postali non è in grado di controllare queste attività.

   Per cercare i record MailItemsAccessed in cui l'accesso agli elementi di posta è avvenuto tramite un'operazione Sync, eseguire il comando seguente:

   **Log di controllo unificato**

   ```powershell
   Search-UnifiedAuditLog -StartDate 01/06/2020 -EndDate 02/20/2020 -UserIds <user1,user2> -Operations MailItemsAccessed -ResultSize 1000 | Where {$_.AuditData -like '*"MailAccessType","Value":"Sync"*'} | FL
   ```

   **Log di controllo cassetta postale**

   ```powershell
   Search-MailboxAuditLog -StartDate 01/06/2020 -EndDate 01/20/2020 -Identity <user> -Operations MailItemsAccessed -ResultSize 10000 -ShowDetails | Where {$_.OperationProperties -like "*MailAccessType:Sync*"} | FL
   ```

3. Controllare le attività di sincronizzazione per determinare se qualcuna di esse è avvenuta nel contesto di quella usata dall'autore dell'attacco per accedere alla cassetta postale. Il contesto è identificato e differenziato dall'indirizzo IP del computer client usato per accedere alla cassetta postale e dal protocollo di posta. Per altre informazioni, vedere la sezione [Identificazione dei contesti di accesso di record di controllo diversi](#identifying-the-access-contexts-of-different-audit-records).

   Usare le proprietà elencate di seguito per le indagini. Queste proprietà si trovano nella proprietà AuditData o OperationProperties. Se una delle sincronizzazioni si verifica nello stesso contesto dell'attività dell'utente malintenzionato, presupporre che quest'ultimo abbia sincronizzato tutti gli elementi di posta elettronica con il suo client, il che significa che l'intera cassetta postale è stata probabilmente compromessa.

   |Proprietà         | Descrizione |
   |:---------------- | :----------|
   |ClientInfoString | Descrive il protocollo, client (include la versione)|
   |ClientIPAddress  | Indirizzo IP del computer client.|
   |SessionId        | L'ID sessione consente di distinguere le azioni dell'autore dell'attacco dalle normali attività dell'utente nello stesso account (nel caso di un account compromesso)|
   |UserId           | UPN dell'utente che legge il messaggio.|
   |||

4. Controllare le attività di binding. Dopo avere eseguito i passaggi 2 e 3, si può essere certi che tutti gli altri accessi ai messaggi di posta elettronica dell'autore dell'attacco saranno acquisiti nei record di controllo MailItemsAccessed che hanno una proprietà MailAccessType con il valore "Bind".

   Per cercare i record MailItemsAccessed in cui l'accesso agli elementi di posta è avvenuto tramite un'operazione Bind, eseguire il comando seguente.

   **Log di controllo unificato**

   ```powershell
   Search-UnifiedAuditLog -StartDate 01/06/2020 -EndDate 01/20/2020 -UserIds <user1,user2> -Operations MailItemsAccessed -ResultSize 1000 | Where {$_.AuditData -like '*"MailAccessType","Value":"Bind"*'} | FL
   ```
 
   **Log di controllo cassetta postale**
   
   ```powershell
   Search-MailboxAuditLog -StartDate 01/06/2020 -EndDate 01/20/2020 -Identity <user> -Operations MailItemsAccessed -ResultSize 10000 -ShowDetails | Where {$_.OperationProperties -like "*MailAccessType:Bind*"} | FL
   ```

   I messaggi di posta elettronica a cui è stato eseguito l'accesso sono identificati dal relativo valore InternetMessageId. Si può anche controllare se siano presenti record di controllo con lo stesso contesto di quelli di altre attività dell'utente malintenzionato. Per altre informazioni, vedere la sezione [Identificazione dei contesti di accesso di record di controllo diversi](#identifying-the-access-contexts-of-different-audit-records).
 
   È possibile usare i dati di controllo per le operazioni di binding in due modi diversi:

     - Accedere o raccogliere tutti i messaggi di posta elettronica a cui ha eseguito l'accesso l'utente malintenzionato usando l'InternetMessageId per trovarli, poi verificare se uno di questi messaggi contiene informazioni riservate.

     - Usare l'InternetMessageId per cercare i record di controllo relativi a un set di messaggi di posta elettronica potenzialmente sensibili. Questa opzione è utile se si è preoccupati solo per un numero limitato di messaggi.

## <a name="filtering-of-duplicate-audit-records"></a>Filtro dei record di controllo duplicati

I record di controllo duplicati per le stesse operazioni di binding che si verificano entro un'ora l'una dall'altra vengono esclusi per rimuovere i dati non significativi. Anche le operazioni di sincronizzazione sono filtrate a intervalli di un'ora. Un'eccezione a questo processo di deduplicazione si verifica se, per lo stesso InternetMessageId, le proprietà descritte nella tabella seguente sono diverse. Se una di queste proprietà è diversa in un'operazione duplicata, viene generato un nuovo record di controllo. Questo processo è descritto in modo più dettagliato nella sezione successiva.

| Proprietà| Descrizione|
|:--------|:---------|
|ClientIPAddress | Indirizzo IP del computer client.|
|ClientInfoString| Protocollo client, client usato per accedere alla cassetta postale.| 
|ParentFolder    | Percorso completo della cartella dell'elemento di posta a cui è stato eseguito l'accesso. |
|Logon_type      | Tipo di accesso dell'utente che ha eseguito l'azione. I tipi di accesso e il valore di enumerazione corrispondente sono Owner (0), Admin (1) o Delegate (2).|
|MailAccessType  | Indica se l'accesso è un'operazione Bind o Sync.|
|MailboxUPN      | UPN della cassetta postale in cui si trova il messaggio letto.|
|User            | UPN dell'utente che legge il messaggio.|
|SessionId       | L'ID sessione consente di distinguere le azioni dell'autore dell'attacco dalle normali attività dell'utente nella stessa cassetta postale, in caso di compromissione dell'account. Per altre informazioni sulle sessioni, vedere [Contextualizing attacker activity within sessions in Exchange Online](https://techcommunity.microsoft.com/t5/exchange-team-blog/contextualizing-attacker-activity-within-sessions-in-exchange/ba-p/608801) (Contestualizzare le attività di un utente malintenzionato all'interno delle sessioni in Exchange Online).|
||||

## <a name="identifying-the-access-contexts-of-different-audit-records"></a>Identificazione dei contesti di accesso di record di controllo diversi

È comune che l'autore di un attacco possa accedere a una cassetta postale nello stesso momento in cui vi accede il proprietario della cassetta postale. Per distinguere l'accesso del malintenzionato da quello del proprietario della cassetta postale, esistono delle proprietà del record di controllo che definiscono il contesto dell'accesso. Come descritto in precedenza, quando i valori di queste proprietà sono diversi, anche se l'attività si verifica entro l'intervallo di aggregazione, vengono generati record di controllo distinti. Nell'esempio seguente ci sono tre diversi record di controllo. Ognuno di essi è differenziato dalle proprietà SessionId e ClientIPAddress. Sono anche identificati i messaggi a cui è stato eseguito l'accesso.

|Record di controllo 1  |Record di controllo 2  |Record di controllo 3|
|---------|---------|---------|
|ClientIPAddress **1**<br/>SessionId **2**|ClientIPAddress **2**<br/>SessionId **2**|ClientIPAddress **1**<br/>SessionId **3**|
|InternetMessageId **A**<br/>InternetMessageId **D**<br/>InternetMessageId **E**<br/>InternetMessageId **F**<br/>|InternetMessageId **A**<br/>InternetMessageId **C**|InternetMessageId **B** |
||||

Se una o più delle proprietà elencate nella tabella della [sezione precedente](#filtering-of-duplicate-audit-records) è diversa, viene generato un record di controllo separato per tenere traccia del nuovo contesto. Gli accessi verranno ordinati nei record di controllo separati in base al contesto in cui si è verificata l'attività.

Ad esempio, nei record di controllo visualizzati nello screenshot seguente, anche se accediamo alla posta elettronica da EWSEditor e OWA contemporaneamente, l'attività di accesso viene raccolta in record di controllo diversi in base al contesto in cui si è verificato l'accesso. In questo caso, il contesto è definito da valori diversi per la proprietà ClientInfoString.

![Record di controllo diversi in base al contesto](../media/MailItemsAccessed4.png)

Questa è la sintassi del comando visualizzato nello screenshot precedente:

```powershell
Search-MailboxAuditLog -Identity admin -ShowDetails -Operations MailItemsAccessed -ResultSize 2000 | Select LastAccessed,Operation,AuditOperationsCountInAggregatedRecord,ClientInfoString
```