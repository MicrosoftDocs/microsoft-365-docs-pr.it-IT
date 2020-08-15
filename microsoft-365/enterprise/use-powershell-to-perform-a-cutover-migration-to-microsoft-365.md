---
title: Utilizzare PowerShell per eseguire una migrazione completa a Microsoft 365
ms.author: sirkkuw
author: sirkkuw
manager: laurawi
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
ms.assetid: b468cb4b-a35c-43d3-85bf-65446998af40
description: Informazioni su come utilizzare PowerShell per spostare il contenuto da un sistema di posta elettronica di origine in una sola volta eseguendo una migrazione di completa a Microsoft 365.
ms.openlocfilehash: bf97fef7e0e927dc901b0223978a3eef377def2c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690967"
---
# <a name="use-powershell-to-perform-a-cutover-migration-to-microsoft-365"></a>Utilizzare PowerShell per eseguire una migrazione completa a Microsoft 365

*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*

È possibile eseguire la migrazione del contenuto delle cassette postali degli utenti da un sistema di posta elettronica di origine a Microsoft 365 tutti insieme utilizzando una migrazione completa. In questo articolo vengono illustrate le attività per una migrazione completa della posta elettronica tramite PowerShell di Exchange Online. 
  
Esaminando l'argomento, [cosa è necessario sapere sulla migrazione della posta elettronica di completa a Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=536688), è possibile ottenere una panoramica del processo di migrazione. Una volta appresi i contenuti di questo articolo, utilizzarlo per iniziare la migrazione delle cassette postali da un sistema di posta elettronica a un altro.
  
> [!NOTE]
> Inoltre, è possibile utilizzare l'interfaccia di amministrazione di Exchange per eseguire una migrazione completa. Vedere [eseguire una migrazione completa della posta elettronica a Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=536689). 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

Tempo stimato per il completamento di questa attività: tra i 2 e i 5 minuti per creare un batch di migrazione. Dopo l'avvio del batch di migrazione, la durata della migrazione varia in base al numero di cassette postali nel batch, alla dimensione di ogni cassetta postale e alla capacità di rete disponibile. Per informazioni sugli altri fattori che influiscono sul tempo necessario per eseguire la migrazione delle cassette postali a Microsoft 365, vedere [Migration performance](https://go.microsoft.com/fwlink/p/?LinkId=275079).
  
È necessario disporre delle autorizzazioni per poter eseguire queste procedure. Per verificare le autorizzazioni necessarie, vedere la voce "Migrazione" in una tabella nell'argomento [Autorizzazioni di destinatari](https://go.microsoft.com/fwlink/p/?LinkId=534105).
  
Per utilizzare i cmdlet di PowerShell di Exchange Online, è necessario eseguire l'accesso e importare i cmdlet nella sessione di Windows PowerShell locale. Per le istruzioni, vedere [Connettersi a Exchange Online tramite Remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=534121).
  
Per un elenco completo dei comandi di migrazione, vedere [Cmdlet di spostamento e migrazione](https://go.microsoft.com/fwlink/p/?LinkId=534750).
  
## <a name="migration-steps"></a>Procedura della migrazione

### <a name="step-1-prepare-for-a-cutover-migration"></a>Passaggio 1: predisporre una migrazione completa
<a name="BK_Step1"> </a>

- **Aggiungere l'organizzazione di Exchange locale come dominio accettato dell'organizzazione Microsoft 365.** Il servizio di migrazione utilizza l'indirizzo SMTP delle cassette postali locali per creare l'ID utente e l'indirizzo di posta elettronica dei Microsoft Online Services per le nuove cassette postali di Microsoft 365. La migrazione avrà esito negativo se il dominio di Exchange non è un dominio accettato o il dominio principale dell'organizzazione Microsoft 365. Per ulteriori informazioni, vedere [verificare il dominio](https://go.microsoft.com/fwlink/p/?LinkId=534110).
    
- **Configurare Outlook via Internet nel server Exchange locale** Nel servizio di migrazione della posta elettronica viene utilizzato RPC su HTTP, anche denominato Outlook via Internet, per connettersi al server Exchange locale. Per informazioni sull'installazione di Outlook via Internet per Exchange 2010, Exchange 2007 ed Exchange 2003, vedere gli argomenti seguenti:
    
  - [Exchange 2010: Abilita Outlook via Internet](https://go.microsoft.com/fwlink/?LinkID=187249)
    
  - [Exchange 2007: Come abilitare Outlook Anywhere](https://go.microsoft.com/fwlink/?LinkID=167210)
    
  - [Exchange 2003: Scenari di distribuzione per RPC su HTTP](https://go.microsoft.com/fwlink/?LinkID=73657)
    
  - [Configurazione di Outlook via Internet con Exchange 2003](https://go.microsoft.com/fwlink/?LinkID=167209)
    
    > [!IMPORTANT]
    > È necessario configurare Outlook via Internet con un certificato considerato attendibile da un'autorità di certificazione (CA, Certificate Authority). Non può essere configurato con un certificato autofirmato. Per ulteriori informazioni, vedere [Come configurare SSL per Outlook via Internet](https://go.microsoft.com/fwlink/?LinkID=80875). 
  
- **Verificare che sia possibile connettersi all'organizzazione di Exchange tramite Outlook via Internet** Provare uno di questi metodi per testare le impostazioni di connessione:
    
  - Utilizzare Microsoft Outlook all'esterno della rete aziendale per connettersi alla cassetta postale di Exchange locale.
    
  - Utilizzare Microsoft [Exchange Remote Connectivity Analyzer](https://www.testexchangeconnectivity.com/) per testare le impostazioni della connessione. Utilizzare Outlook via Internet (RPC su HTTP) o i test di individuazione automatica di Outlook.
    
  - In PowerShell di Exchange Online, eseguire i comandi seguenti.
    
  ```
  $Credentials = Get-Credential
  ```

  ```
  Test-MigrationServerAvailability -ExchangeOutlookAnywhere -Autodiscover -EmailAddress <email address for on-premises administrator> -Credentials $credentials
  ```

- **Assegnare a un account utente locale le autorizzazioni necessarie per accedere alle cassette postali nella propria organizzazione di Exchange.** L'account utente locale utilizzato per la connessione all'organizzazione di Exchange locale (denominato anche amministratore della migrazione) deve disporre delle autorizzazioni necessarie per accedere alle cassette postali locali di cui si desidera eseguire la migrazione a Microsoft 365. Questo account utente viene utilizzato per creare un endpoint di migrazione per la propria organizzazione locale.
    
    Nel seguente elenco vengono mostrati i privilegi amministrativi necessari per migrare le cassette postali tramite una migrazione completa. Esistono tre opzioni possibili.
    
  - L'amministratore di migrazione deve essere un membro del gruppo **Domain Admins** in Active Directory nell'organizzazione locale.
    
    Oppure
    
  - All'amministratore di migrazione è assegnata l'autorizzazione **FullAccess** per ogni cassetta postale locale.
    
    Oppure
    
  - All'amministratore di migrazione deve essere assegnata l'autorizzazione **Receive As** nel database di cassette postali locali in cui si trovano le cassette postali dell'utente.
    
- **Disabilitare la messaggistica unificata.** Se le cassette postali locali di cui si sta eseguendo la migrazione sono abilitate per la messaggistica unificata, è necessario disabilitare la messaggistica stessa prima di eseguire la migrazione. È possibile quindi riabilitare la messaggistica unificata al termine della migrazione.
    
- **Gruppi di sicurezza e delegati** Il servizio di migrazione della posta elettronica non è in grado di rilevare se i gruppi di Active Directory locali sono gruppi di sicurezza o meno, pertanto non è possibile eseguire il provisioning di gruppi migrati come gruppi di sicurezza in Microsoft 365. Se si desidera disporre di gruppi di sicurezza nel tenant Microsoft 365, è necessario innanzitutto eseguire il provisioning di un gruppo di sicurezza abilitato alla posta elettronica vuoto nel tenant di Microsoft 365 prima di avviare la migrazione di completa. Inoltre, questo metodo di migrazione consente di spostare solo le cassette postali, gli utenti di posta, i contatti di posta e gruppi abilitati alla posta. Se qualsiasi altro oggetto di Active Directory, ad esempio un utente che non esegue la migrazione a Microsoft 365, viene assegnato come Manager o delegato a un oggetto di cui è in corso la migrazione, è necessario rimuoverlo dall'oggetto prima di eseguire la migrazione.
    
### <a name="step-2-create-a-migration-endpoint"></a>Passaggio 2: creare un endpoint di migrazione
<a name="BK_Step2"> </a>

Per eseguire correttamente la migrazione della posta elettronica, Microsoft 365 deve connettersi e comunicare con il sistema di posta elettronica di origine. A tale scopo, Microsoft 365 utilizza un endpoint di migrazione. Per creare un endpoint di migrazione di Outlook via Internet per una migrazione completa, è necessario innanzitutto [connettersi a Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=534121). 
  
Per un elenco completo dei comandi di migrazione, vedere [Cmdlet di spostamento e migrazione](https://go.microsoft.com/fwlink/p/?LinkId=534750).
  
In PowerShell di Exchange Online, eseguire i comandi seguenti:
  
```
$Credentials = Get-Credential
```

Nell'esempio viene utilizzato il cmdlet [Test-MigrationServerAvailability](https://go.microsoft.com/fwlink/p/?LinkId=534752) per ottenere e verificare le impostazioni di connessione al server di Exchange locale. In seguito, tali impostazioni vengono utilizzate per creare l'endpoint di migrazione denominato "CutoverEndpoint".
  
```
$TSMA = Test-MigrationServerAvailability -ExchangeOutlookAnywhere -Autodiscover -EmailAddress administrator@contoso.com -Credentials $credentials
```

```
New-MigrationEndpoint -ExchangeOutlookAnywhere -Name CutoverEndpoint -ConnectionSettings $TSMA.ConnectionSettings
```

> [!NOTE]
> Il cmdlet **New-MigrationEndpoint** può essere utilizzato per specificare un database per il servizio da utilizzare tramite l'opzione **-TargetDatabase**. In caso contrario, un database viene assegnato in modo casuale dal sito di Active Directory Federation Services (ADFS) 2.0 in cui si trova la cassetta postale di gestione.
  
#### <a name="verify-it-worked"></a>Verificare che il passaggio di migrazione sia avvenuto correttamente

In PowerShell di Exchange Online, eseguire il comando riportato di seguito per visualizzare le informazioni sull'endpoint di migrazione "CutoverEndpoint":
  
```
Get-MigrationEndpoint CutoverEndpoint | Format-List EndpointType,ExchangeServer,UseAutoDiscover,Max*

```

### <a name="step-3-create-the-cutover-migration-batch"></a>Passaggio 3: creare il batch di migrazione completa
<a name="BK_Step3"> </a>

È possibile utilizzare il cmdlet **New-MigrationBatch** in PowerShell di Exchange Online per creare un batch di migrazione per una migrazione completa. È possibile creare un batch di migrazione e avviarlo automaticamente includendo il parametro _AutoStart_. In alternativa, è possibile creare il batch di migrazione, per poi avviarlo utilizzando il cmdlet **Start-MigrationBatch**. In questo esempio viene creato un batch di migrazione denominato "CutoverBatch" e viene utilizzato l'endpoint di migrazione creato nel passaggio precedente.
  
```
New-MigrationBatch -Name CutoverBatch -SourceEndpoint CutoverEndpoint -AutoStart
```

In questo esempio viene inoltre creato un batch di migrazione denominato "CutoverBatch" e viene utilizzato l'endpoint di migrazione creato nel passaggio precedente. Poiché il parametro  _AutoStart_ non è incluso, il batch di migrazione deve essere avviato manualmente nel dashboard di migrazione oppure utilizzando il cmdlet **Start-MigrationBatch**. Come illustrato in precedenza, può esistere solo un batch di migrazione completa alla volta.
  
```
New-MigrationBatch -Name CutoverBatch -SourceEndpoint CutoverEndpoint
```

#### <a name="verify-it-worked"></a>Verificare che il passaggio di migrazione sia avvenuto correttamente

Per verificare che sia stato creato correttamente un batch di migrazione per una migrazione completa, eseguire il seguente comando in PowerShell di Exchange Online per visualizzare informazioni sul nuovo batch di migrazione:
  
```
Get-MigrationBatch | Format-List
```

### <a name="step-4-start-the-cutover-migration-batch"></a>Passaggio 4: avviare il batch di migrazione completa
<a name="BK_Step4"> </a>

Per avviare il batch di migrazione in PowerShell di Exchange Online, eseguire il comando riportato di seguito. In tal modo verrà creato un batch di migrazione denominato "CutoverBatch".
  
```
Start-MigrationBatch -Identity CutoverBatch
```

#### <a name="verify-it-worked"></a>Verificare che il passaggio di migrazione sia avvenuto correttamente

Se un batch di migrazione è avviato correttamente, il relativo stato sul dashboard di migrazione viene indicato come Sincronizzazione in corso. Per verificare che sia stato avviato correttamente un batch di migrazione tramite PowerShell di Exchange Online, eseguire il comando riportato di seguito:
  
```
Get-MigrationBatch -Identity CutoverBatch |  Format-List Status
```

### <a name="step-5-route-your-email-to-microsoft-365"></a>Passaggio 5: instradare la posta elettronica a Microsoft 365
<a name="BK_Step5"> </a>

I sistemi di posta elettronica utilizzano un record DNS denominato record MX per individuare dove recapitare i messaggi di posta elettronica. Durante il processo di migrazione della posta elettronica, il record MX fa riferimento al sistema di posta elettronica di origine. Una volta completata la migrazione della posta elettronica a Microsoft 365, è possibile puntare il record MX su Microsoft 365. Ciò consente di verificare che la posta elettronica venga recapitata alle cassette postali di Microsoft 365. Spostando il record MX, è inoltre possibile disattivare il sistema di posta elettronica precedente al momento più opportuno. 
  
Per molti provider DNS, sono disponibili istruzioni specifiche per [modificare il record MX](https://go.microsoft.com/fwlink/p/?LinkId=279163). Se il provider DNS non è incluso oppure si desidera farsi un'idea delle direzioni generali, vengono fornite anche [istruzioni generali sul record MX](https://go.microsoft.com/fwlink/?LinkId=397449).
  
È possibile che i sistemi di posta elettronica dei propri clienti e partner impieghino fino a 72 ore per riconoscere il record MX modificato. Attendere almeno 72 ore prima di procedere con l'attività successiva: [Passaggio 6: eliminare il batch di migrazione completa](use-powershell-to-perform-a-cutover-migration-to-microsoft-365.md#Bk_step6). 
  
### <a name="step-6-delete-the-cutover-migration-batch"></a>Passaggio 6: eliminare il batch di migrazione completa
<a name="Bk_step6"> </a>

Dopo aver modificato il record MX e aver verificato che tutti i messaggi di posta elettronica vengano instradati alle cassette postali di Microsoft 365, informare gli utenti che la posta viene inviata a Microsoft 365. Dopo questa operazione, è possibile eliminare il batch di migrazione completa. Verificare le seguenti condizioni prima di eliminare il batch di migrazione.
  
- Tutti gli utenti utilizzano le cassette postali di Microsoft 365. Dopo l'eliminazione del batch, la posta inviata alle cassette postali sul server Exchange locale non viene copiata nelle cassette postali di Microsoft 365 corrispondenti.
    
- Le cassette postali di Microsoft 365 sono state sincronizzate almeno una volta dopo che la posta è cominciata a essere inviata direttamente. Per eseguire questa operazione, verificare che il valore dell'ultima casella di tempo sincronizzato per il batch di migrazione sia più recente rispetto al momento in cui la posta elettronica ha iniziato a essere instradata direttamente alle cassette postali di Microsoft 365.
    
Per eliminare il batch di migrazione "CutoverBatch" in PowerShell di Exchange Online, eseguire il comando riportato di seguito:
  
```
Remove-MigrationBatch -Identity CutoverBatch
```

### <a name="section-7-assign-user-licenses"></a>Sezione 7: assegnare licenze utente
<a name="BK_Step7"> </a>

 **Attivare gli account utente di Microsoft 365 per gli account migrati assegnando le licenze.** Se non si assegna una licenza, la cassetta postale viene disabilitata al termine del periodo di prova (30 giorni). Per assegnare una licenza nell'interfaccia di amministrazione di Microsoft 365, vedere [assegnare o](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)annullare l'assegnazione delle licenze.
  
### <a name="step-8-complete-post-migration-tasks"></a>Passaggio 8: completare le attività successive alla migrazione
<a name="BK_Step8"> </a>

- **Creare un record DNS di individuazione automatica affinché gli utenti possano accedere facilmente alle proprie cassette postali.** Dopo la migrazione di tutte le cassette postali locali a Microsoft 365, è possibile configurare un record DNS di individuazione automatica per l'organizzazione di Microsoft 365 per consentire agli utenti di connettersi facilmente alle nuove cassette postali di Microsoft 365 con Outlook e i client mobili. Questo nuovo record DNS di individuazione automatica deve utilizzare lo stesso spazio dei nomi che si sta utilizzando per l'organizzazione Microsoft 365. Ad esempio, se lo spazio dei nomi basato su cloud è cloud.contoso.com, il record DNS di individuazione automatica che deve essere creato è autodiscover.cloud.contoso.com.
    
    Se si mantiene il server Exchange, è inoltre necessario verificare che il record CNAME DNS di individuazione automatica debba puntare a Microsoft 365 in DNS interno ed esterno dopo la migrazione in modo che il client di Outlook si connetta alla cassetta postale corretta.
    
    > [!NOTE]
    >  In Exchange 2007, Exchange 2010 e Exchange 2013 è inoltre necessario impostare  `Set-ClientAccessServer AutodiscoverInternalConnectionURI` su `Null`. 
  
    Microsoft 365 utilizza un record CNAME per implementare il servizio di individuazione automatica per Outlook e i client mobili. Il record CNAME di individuazione automatica deve includere le seguenti informazioni:
    
  - **Alias:** individuazione automatica
    
  - **Destinazione:** autodiscover.outlook.com
    
    Per ulteriori informazioni, vedere [aggiungere record DNS per connettere il dominio](https://go.microsoft.com/fwlink/p/?LinkId=535028).
    
- **Rimuovere i server di Exchange locali.** Dopo aver verificato che tutta la posta elettronica viene instradata direttamente alle cassette postali di Microsoft 365 e che non è più necessario mantenere l'organizzazione di posta elettronica locale o non pianificare l'implementazione di una soluzione Single Sign-on (SSO), è possibile disinstallare Exchange dai server e rimuovere l'organizzazione di Exchange locale.
    
    Per ulteriori informazioni, vedere gli argomenti seguenti:
    
  - [Modifica o eliminazione di Exchange 2010](https://go.microsoft.com/fwlink/?LinkId=217936)
    
  - [Come rimuovere un'organizzazione di Exchange 2007](https://go.microsoft.com/fwlink/?LinkID=100485)
    
  - [Disinstallazione di Exchange Server 2003](https://go.microsoft.com/fwlink/?LinkID=56561)
    

