---
title: Utilizzare PowerShell per eseguire una migrazione IMAP a Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: c28de4a5-1e8e-4491-9421-af066cde7cdd
description: Informazioni su come utilizzare PowerShell per eseguire una migrazione IMAP (Internet Mail Access Protocol) a Microsoft 365.
ms.openlocfilehash: fbfc0340e80ce70aa8a706d89a4d27729b91535b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924769"
---
# <a name="use-powershell-to-perform-an-imap-migration-to-microsoft-365"></a>Utilizzare PowerShell per eseguire una migrazione IMAP a Microsoft 365

*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*

Come parte del processo di distribuzione di Microsoft 365, è possibile scegliere di eseguire la migrazione del contenuto delle cassette postali degli utenti da un servizio di posta elettronica IMAP (Internet Mail Access Protocol) a Microsoft 365. In questo articolo vengono illustrate le attività per una migrazione IMAP della posta elettronica tramite PowerShell di Exchange Online. 
  
> [!NOTE]
> È anche possibile utilizzare l'interfaccia di amministrazione di Exchange per eseguire una migrazione IMAP. Vedere [Migrate your IMAP mailboxes](/Exchange/mailbox-migration/migrating-imap-mailboxes/migrating-imap-mailboxes). 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

Tempo stimato per il completamento di questa attività: tra i 2 e i 5 minuti per creare un batch di migrazione. Dopo l'avvio del batch di migrazione, la durata della migrazione varia in base al numero di cassette postali nel batch, alla dimensione di ogni cassetta postale e alla capacità di rete disponibile. Per informazioni su altri fattori che influiscono sul tempo necessario per eseguire la migrazione delle cassette postali a Microsoft 365, vedere [Migration Performance](/Exchange/mailbox-migration/office-365-migration-best-practices).
  
È necessario disporre delle autorizzazioni per poter eseguire queste procedure. Per verificare le autorizzazioni necessarie, vedere la voce "Migrazione" in una tabella nell'argomento [Autorizzazioni di destinatari](/exchange/recipients-permissions-exchange-2013-help).
  
Per utilizzare i cmdlet di PowerShell di Exchange Online, è necessario eseguire l'accesso e importare i cmdlet nella sessione di Windows PowerShell locale. Per le istruzioni, vedere [Connettersi a Exchange Online tramite Remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).
  
Per un elenco completo dei comandi di migrazione, vedere [Cmdlet di spostamento e migrazione](/powershell/exchange/).
  
Le seguenti limitazioni valgono per le migrazioni IMAP:
  
- È possibile eseguire la migrazione solo degli elementi nella cartella Posta in arrivo o in altre cartelle di posta di un utente. Non è possibile migrare i contatti, gli elementi del calendario e le attività.
    
- È possibile eseguire la migrazione di un massimo di 500.000 elementi dalla cassetta postale di un utente.
    
- La dimensione massima di un messaggio di posta elettronica di cui è possibile eseguire la migrazione è 35 MB.
    
## <a name="migration-steps"></a>Procedura della migrazione

### <a name="step-1-prepare-for-an-imap-migration"></a>Passaggio 1: predisporre una migrazione IMAP
<a name="BK_Step1"> </a>

- **Se si dispone di un dominio per l'organizzazione IMAP, aggiungerlo come dominio accettato dell'organizzazione di Microsoft 365.** Se si desidera utilizzare lo stesso dominio già proprietario per le cassette postali di Microsoft 365, è innanzitutto necessario aggiungerlo come dominio accettato a Microsoft 365. Dopo l'aggiunta, è possibile creare gli utenti in Microsoft 365. Per ulteriori informazioni, vedere[Verify your domain](../admin/setup/add-domain.md).
    
- **Aggiungere ogni utente a Microsoft 365 in modo che abbia una cassetta postale.** Per istruzioni, vedere[Aggiungere utenti a Microsoft 365 per le aziende.](../admin/add-users/add-users.md)
    
- **Ottenere il nome di dominio completo (FQDN) del server IMAP**. È necessario fornire il nome di dominio completo (FQDN), denominato anche nome completo del computer, del server IMAP dal quale si desidera migrare i dati delle cassette postali quando si crea un endpoint di migrazione IMAP. Utilizzare un client IMAP o il comando PING per verificare che sia possibile utilizzare il nome di dominio completo per comunicare con il server IMAP tramite Internet.
    
- **Configurare il firewall per consentire connessioni IMAP**. Potrebbe essere necessario aprire porte nel firewall dell'organizzazione che ospita il server IMAP, in modo che il traffico di rete proveniente dal datacenter Microsoft durante la migrazione sia in grado di accedere all'organizzazione che ospita il server IMAP. Per un elenco di indirizzi IP utilizzati dai datacenter Microsoft, vedere l'articolo relativo agli [URL e intervalli di indirizzi IP per Office 365](./urls-and-ip-address-ranges.md).
    
- **Assegnare all'account dell'amministratore le autorizzazioni necessarie per accedere alle cassette postali nell'organizzazione IMAP**. Se si utilizzano le credenziali di amministratore nel file CSV, l'account in uso deve disporre delle autorizzazioni necessarie per accedere alle cassette postali locali. Le autorizzazioni necessarie per accedere alle cassette postali dell'utente sono determinate da uno specifico server IMAP. 
    
- **Per utilizzare i cmdlet di PowerShell di Exchange Online**, è necessario eseguire l'accesso e importare i cmdlet nella sessione di Windows PowerShell locale. Per le istruzioni, vedere [Connettersi a Exchange Online tramite Remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).
    
    Per un elenco completo dei comandi di migrazione, vedere [Cmdlet di spostamento e migrazione](/powershell/exchange/).
    
- **Verificare che sia possibile connettersi al server IMAP**. Eseguire il seguente comando di PowerShell di Exchange Online per verificare le impostazioni di connessione al server IMAP.
    
  ```powershell
  Test-MigrationServerAvailability -IMAP -RemoteServer <FQDN of IMAP server> -Port <143 or 993> -Security <None, Ssl, or Tls>
  ```

    Per il valore del parametro **Port**, in genere si utilizza 143 per le connessioni non crittografate o Transport Layer Security (TLS) e 993 per le connessioni SSL.
    
### <a name="step-2-create-a-csv-file-for-an-imap-migration-batch"></a>Passaggio 2: creare un file CSV per un batch di migrazione IMAP
<a name="BK_Step2"> </a>

Identificare il gruppo di utenti per i quali si desidera effettuare la migrazione delle cassette postali in un batch di migrazione IMAP. Ogni riga nel file CSV contiene informazioni necessarie per connettersi a una cassetta postale nel sistema di messaggistica IMAP.
  
Di seguito sono riportati gli attributi necessari per ogni utente: 
  
- **EmailAddress** specifica l'ID utente per la cassetta postale di Microsoft 365 dell'utente.
    
- **UserName** specifica il nome di accesso per l'account da utilizzare per accedere alla cassetta postale sul server IMAP.
    
- **Password** specifica la password per l'account nella colonna **UserName**.
    
Di seguito viene illustrato un esempio di formato per il file CSV. In questo esempio viene eseguita la migrazione di tre cassette postali:
  
```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,terry.adams,1091990
annb@contoso.edu,ann.beebe,2111991
paulc@contoso.edu,paul.cannon,3281986
```

Per l'attributo **UserName**, oltre al nome utente, è possibile utilizzare le credenziali di un account al quale sono state assegnate le autorizzazioni necessarie per accedere alle cassette postali nel server IMAP. Di seguito, sono riportati alcuni dei formati specifici utilizzati per alcuni server IMAP:
  
 **Microsoft Exchange:**
  
Se si sta eseguendo la migrazione della posta elettronica dall'implementazione IMAP per Microsoft Exchange, utilizzare il formato **Dominio/NomeUtente_Amministratore/NomeUtente_Utente** per l'attributo **UserName** nel file CSV. Si supponga di eseguire la migrazione della posta elettronica da Exchange per Terry Adams, Ann Beebe e Paul Cannon. Si dispone di un account di amministratore della posta, dove il nome utente è **mailadmin** e la password **è P \@ ssw0rd**. Il file CSV risulterà simile al seguente:
  
```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,contoso-students/mailadmin/terry.adams,P@ssw0rd
annb@contoso.edu,contoso-students/mailadmin/ann.beebe,P@ssw0rd
paulc@contoso.edu,contoso-students/mailadmin/paul.cannon,P@ssw0rd
```

 **Dovecot:**
  
Per i server IMAP che supportano SASL (Simple Authentication and Security Layer), come ad esempio il server IMAP Dovecot, utilizzare il formato **NomeUtente_Utente*NomeUtente_Amministratore**, dove l'asterisco ( * ) è un carattere separatore configurabile. Supponiamo che la migrazione della posta elettronica degli stessi utenti da un server IMAP Dovecot utilizzi le credenziali di amministratore **mailadmin** e **P \@ ssw0rd**. Il file CSV risulterà simile al seguente:
  
```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,terry.adams*mailadmin,P@ssw0rd
annb@contoso.edu,ann.beebe*mailadmin,P@ssw0rd
paulc@contoso.edu,paul.cannon*mailadmin,P@ssw0rd
```

 **Mirapoint:**
  
Se si esegue la migrazione della posta elettronica da Mirapoint Message Server, utilizzare il formato **\@ #user dominio#Admin_UserName#** per le credenziali di amministratore. Per eseguire la migrazione della posta elettronica da Mirapoint utilizzando le credenziali di amministratore **mailadmin** e **P \@ ssw0rd,** il file CSV sarà simile al seguente:
  
```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,#terry.adams@contoso-students.edu#mailadmin#,P@ssw0rd
annb@contoso.edu,#ann.beebe@contoso-students.edu#mailadmin#,P@ssw0rd
paulc@contoso.edu,#paul.cannon@contoso-students.edu#mailadmin#,P@ssw0rd
```

 **Courier IMAP:**
  
Alcuni sistemi di posta elettronica di origine, ad esempio Courier IMAP, non supportano l'utilizzo delle credenziali di amministratore delle cassette postali per eseguire la migrazione delle cassette postali a Microsoft 365. Al contrario, è possibile configurare il sistema di posta elettronica di origine affinché utilizzi le cartelle condivise virtuali. Con le cartelle condivise virtuali, è possibile utilizzare le credenziali di amministratore delle cassette postali per accedere alle cassette postali dell'utente nel sistema di posta elettronica di origine. Per ulteriori informazioni su come configurare le cartelle condivise virtuali per Courier IMAP, vedere [Cartelle condivise](https://go.microsoft.com/fwlink/p/?LinkId=398870).
  
Per eseguire la migrazione delle cassette postali dopo avere configurato le cartelle condivise virtuali nel sistema di posta elettronica di origine, è necessario includere l'attributo **UserRoot** facoltativo nel file di migrazione. Questo attributo consente di specificare il percorso della cassetta postale di ogni utente nella struttura di cartelle condivise virtuali nel sistema di posta elettronica di origine. Ad esempio, il percorso per la cassetta postale di Terry è /utenti/terry.adams.
  
Di seguito è riportato un esempio di file CSV contenente l'attributo **UserRoot**:
  
```powershell
EmailAddress,UserName,Password,UserRoot
terrya@contoso.edu,mailadmin,P@ssw0rd,/users/terry.adams
annb@contoso.edu,mailadmin,P@ssw0rd,/users/ann.beebe
paulc@contoso.edu,mailadmin,P@ssw0rd,/users/paul.cannon
```

### <a name="step-3-create-an-imap-migration-endpoint"></a>Passaggio 3: creare un endpoint di migrazione IMAP
<a name="BK_Step3"> </a>

Per eseguire correttamente la migrazione della posta elettronica, Microsoft 365 deve connettersi e comunicare con il sistema di posta elettronica di origine. A tale scopo, Microsoft 365 usa un endpoint di migrazione. L'endpoint di migrazione definisce inoltre il numero di cassette postali da migrare contemporaneamente e il numero di cassette postali da sincronizzare contemporaneamente durante la sincronizzazione incrementale, che si verifica ogni 24 ore. Per creare un endpoint di migrazione per la migrazione IMAP, è necessario innanzitutto [connettersi a Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell). 
  
Per un elenco completo dei comandi di migrazione, vedere [Cmdlet di spostamento e migrazione](/powershell/exchange/).
  
Per creare l'endpoint di migrazione IMAP denominato "IMAPEndpoint" in PowerShell di Exchange Online, eseguire il comando seguente:
  
```powershell
New-MigrationEndpoint -IMAP -Name IMAPEndpoint -RemoteServer imap.contoso.com -Port 993 -Security Ssl

```

È inoltre possibile aggiungere i parametri per specificare le migrazioni contemporanee, le migrazioni incrementali contemporanee e le porte da utilizzare. Il seguente comando di PowerShell di Exchange Online consente di creare un endpoint di migrazione IMAP denominato "IMAPEndpoint" che supporta 50 migrazioni contemporanee e fino a 25 sincronizzazioni incrementali contemporanee. Inoltre, consente di configurare l'endpoint per l'utilizzo della porta 143 per la crittografia TLS.
  
```powershell
New-MigrationEndpoint -IMAP -Name IMAPEndpoint -RemoteServer imap.contoso.com -Port 143 -Security Tls -MaxConcurrentMigrations
50 -MaxConcurrentIncrementalSyncs 25
```

Per ulteriori informazioni sul cmdlet **New-MigrationEndpoint**, vedere [New-MigrationEndpoint](/powershell/module/exchange/new-migrationendpoint).
  
#### <a name="verify-it-worked"></a>Verificare che il passaggio di migrazione sia avvenuto correttamente

Eseguire il seguente comando in PowerShell di Exchange Online per visualizzare informazioni su "IMAPEndpoint":
  
```powershell
Get-MigrationEndpoint IMAPEndpoint | Format-List EndpointType,RemoteServer,Port,Security,Max*
```

### <a name="step-4-create-and-start-an-imap-migration-batch"></a>Passaggio 4: creare e avviare un batch di migrazione IMAP
<a name="BK_Step4"> </a>

È possibile utilizzare il cmdlet [New-MigrationBatch](/powershell/module/exchange/new-migrationbatch) per creare un batch di migrazione per una migrazione IMAP. È possibile creare un batch di migrazione e avviarlo automaticamente includendo il parametro _AutoStart_. In alternativa, è possibile creare il batch di migrazione e avviarlo in un secondo momento utilizzando il cmdlet [Start-MigrationBatch](/powershell/module/exchange/start-migrationbatch).
  
Il seguente comando di PowerShell di Exchange Online avvierà automaticamente il batch di migrazione denominato "IMAPBatch1" utilizzando un endpoint IMAP denominato "IMAPEndpoint":
  
```powershell
New-MigrationBatch -Name IMAPBatch1 -SourceEndpoint IMAPEndpoint -CSVData ([System.IO.File]::ReadAllBytes("C:\Users\Administrator\Desktop\IMAPmigration_1.csv")) -AutoStart
```

#### <a name="verify-it-worked"></a>Verificare che il passaggio di migrazione sia avvenuto correttamente

Eseguire il cmdlet [Get-MigrationBatch](/powershell/module/exchange/get-migrationbatch) per visualizzare informazioni su "IMAPBatch1":
  
```powershell
Get-MigrationBatch -Identity IMAPBatch1 | Format-List
```

È inoltre possibile verificare che il batch sia stato avviato eseguendo il comando riportato di seguito:
  
```powershell
Get-MigrationBatch -Identity IMAPBatch1 | Format-List Status
```

### <a name="step-5-route-your-email-to-microsoft-365"></a>Passaggio 5: Instradare la posta elettronica a Microsoft 365
<a name="BK_Step5"> </a>

I sistemi di posta elettronica utilizzano un record DNS denominato record MX per individuare dove recapitare i messaggi di posta elettronica. Durante il processo di migrazione della posta elettronica, il record MX fa riferimento al sistema di posta elettronica di origine. Ora che la migrazione della posta elettronica a Microsoft 365 è stata completata, è il momento di puntare il record MX a Microsoft 365. In questo modo si garantisce che la posta elettronica sia recapitata alle cassette postali di Microsoft 365. Spostando il record MX, è inoltre possibile disattivare il sistema di posta elettronica precedente al momento più opportuno. 
  
Per molti provider DNS, sono disponibili istruzioni specifiche per modificare il record MX. Se il provider DNS non è incluso oppure si desidera farsi un'idea delle direzioni generali, vengono fornite anche [istruzioni generali sul record MX](https://go.microsoft.com/fwlink/?LinkId=397449).
  
È possibile che i sistemi di posta elettronica dei propri clienti e partner impieghino fino a 72 ore per riconoscere il record MX modificato. Attendere almeno 72 ore prima di procedere con l'attività successiva: Passaggio 6: eliminare il batch di migrazione IMAP. 
  
### <a name="step-6-delete-imap-migration-batch"></a>Passaggio 6: eliminare il batch di migrazione IMAP
<a name="BK_Step6"> </a>

Dopo aver modificato il record MX e aver verificato che tutti i messaggi di posta elettronica vengano instradati alle cassette postali di Microsoft 365, informare gli utenti che la posta verrà inviata a Microsoft 365. Dopo questa operazione, è possibile eliminare il batch di migrazione IMAP. Verificare le seguenti condizioni prima di eliminare il batch di migrazione.
  
- Tutti gli utenti utilizzano le cassette postali di Microsoft 365. Dopo l'eliminazione del batch, la posta inviata alle cassette postali nel Exchange Server locale non viene copiata nelle cassette postali di Microsoft 365 corrispondenti.
    
- Le cassette postali di Microsoft 365 sono state sincronizzate almeno una volta dopo l'invio diretto della posta. A tale scopo, assicurarsi che il valore nella casella Data ultima sincronizzazione per il batch di migrazione sia più recente rispetto all'avvio del routing della posta direttamente alle cassette postali di Microsoft 365.
    
Per eliminare il batch di migrazione "IMAPBatch1" da PowerShell di Exchange Online, eseguire il comando riportato di seguito:
  
```powershell
Remove-MigrationBatch -Identity IMAPBatch1
```

Per ulteriori informazioni sul cmdlet **Remove-MigrationBatch**, vedere [Remove-MigrationBatch](/powershell/module/exchange/remove-migrationbatch).
  
#### <a name="verify-it-worked"></a>Verificare che il passaggio di migrazione sia avvenuto correttamente

Eseguire il seguente comando in PowerShell di Exchange Online per visualizzare informazioni su "IMAPBatch1":
  
```powershell
Get-MigrationBatch IMAPBatch1"
```

Il comando restituirà il batch di migrazione con uno stato di **Rimozione in corso** o restituirà un errore che informa che non è possibile trovare il batch di migrazione, confermandone l'eliminazione.
  
Per ulteriori informazioni sul cmdlet **Get-MigrationBatch**, vedere [Get-MigrationBatch](/powershell/module/exchange/get-migrationbatch).
  
## <a name="see-also"></a>Vedere anche

[Risoluzione dei problemi della migrazione IMAP](/exchange/troubleshoot/move-or-migrate-mailboxes/troubleshoot-issues-with-imap-mailbox-migration)