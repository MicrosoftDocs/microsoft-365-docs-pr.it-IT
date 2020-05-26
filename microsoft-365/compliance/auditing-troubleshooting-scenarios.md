---
title: Eseguire una ricerca nel registro di controllo per risolvere gli scenari comuni
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.custom:
- seo-marvel-apr2020
description: Informazioni su come utilizzare lo strumento di ricerca del registro di controllo di Office 365 per risolvere i problemi di supporto comuni per gli account di posta elettronica.
ms.openlocfilehash: e370a0220fcc42854d3cc570e175ab96845f7d4b
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/23/2020
ms.locfileid: "44351129"
---
# <a name="search-the-audit-log-to-investigate-common-support-issues"></a>Eseguire una ricerca nel registro di controllo per esaminare i problemi di supporto comuni

In questo articolo viene descritto come utilizzare lo strumento di ricerca del registro di controllo per individuare i problemi di supporto comuni. Ciò include l'utilizzo del log di controllo per:

- Individuare l'indirizzo IP del computer utilizzato per accedere a un account compromesso
- Determinare gli utenti che configurano l'inoltro della posta elettronica per una cassetta postale
- Determinare se un utente ha eliminato gli elementi di posta elettronica nella propria cassetta postale
- Determinare se un utente ha creato una regola di posta in arrivo
- Esaminare il motivo per cui è stato eseguito un account di accesso corretto da un utente esterno all'organizzazione

## <a name="using-the-audit-log-search-tool"></a>Utilizzo dello strumento di ricerca del registro di controllo

Tutti gli scenari di risoluzione dei problemi descritti in questo articolo si basano sull'utilizzo dello strumento di ricerca del registro di controllo nel centro sicurezza & Compliance. In questa sezione sono elencate le autorizzazioni necessarie per eseguire una ricerca nel registro di controllo e vengono descritti i passaggi per accedere alle ricerche del registro di controllo e eseguirle. In ogni sezione dello scenario viene illustrato come configurare una query di ricerca del registro di controllo e cosa cercare nelle informazioni dettagliate nei record di controllo corrispondenti ai criteri di ricerca.

### <a name="permissions-required-to-use-the-audit-log-search-tool"></a>Autorizzazioni necessarie per l'utilizzo dello strumento di ricerca del registro di controllo

Per eseguire una ricerca nel registro di controllo, è necessario essere assegnati al ruolo di controllo di sola visualizzazione o ai registri di controllo in Exchange Online. Per impostazione predefinita, questi ruoli sono assegnati ai gruppi di ruoli Gestione conformità e Gestione organizzazione nella pagina **Autorizzazioni** nell'Interfaccia di amministrazione di Exchange. Gli amministratori globali di Office 365 e Microsoft 365 vengono aggiunti automaticamente come membri del gruppo di ruoli Gestione organizzazione in Exchange Online. Per altre informazioni, vedere [Gestire i gruppi di ruoli in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkID=730688).

### <a name="running-audit-log-searches"></a>Esecuzione delle ricerche nei registri di controllo

In questa sezione vengono descritte le nozioni di base per la creazione e l'esecuzione di ricerche nei registri Utilizzare queste istruzioni come punto di partenza per ogni scenario di risoluzione dei problemi in questo articolo. Per istruzioni dettagliate, vedere [Search the audit log](search-the-audit-log-in-security-and-compliance.md#step-1-run-an-audit-log-search).

1. Accedere a [https://protection.office.com/unifiedauditlog](https://protection.office.com/unifiedauditlog) e accedere con l'account aziendale o dell'Istituto di istruzione.
    
    Viene visualizzata la pagina **Ricerca log di controllo**. 
    
    ![Configurare i criteri e quindi selezionare Cerca per eseguire la ricerca](../media/8639d09c-2843-44e4-8b4b-9f45974ff7f1.png)
  
4. È possibile configurare i criteri di ricerca seguenti. Ogni scenario di risoluzione dei problemi in questo articolo consiglia specifiche linee guida per la configurazione di questi campi.
    
    a. **Attività:** Selezionare l'elenco a discesa per visualizzare le attività di cui è possibile eseguire la ricerca. Dopo aver eseguito la ricerca, vengono visualizzati solo i record di controllo per le attività selezionate. Selezionando **Mostra risultati per tutte le attività** vengono visualizzati i risultati di tutte le attività che soddisfano gli altri criteri di ricerca. È inoltre necessario lasciare vuoto questo campo in alcuni degli scenari di risoluzione dei problemi.
    
    b. Data di **inizio** e **Data di fine:** Selezionare un intervallo di data e ora per visualizzare gli eventi che si sono verificati entro quel periodo. Gli ultimi sette giorni sono selezionati per impostazione predefinita. La data e l'ora sono specificate in formato UTC (Coordinated Universal Time). L'intervallo massimo che è possibile specificare è 90 giorni.

    c. **Utenti:** Fare clic in questa casella e quindi selezionare uno o più utenti per visualizzare i risultati della ricerca. I record di controllo per l'attività selezionata eseguita dagli utenti selezionati in questa casella vengono visualizzati nell'elenco dei risultati. Lasciare la casella vuota per restituire le voci per tutti gli utenti (e gli account del servizio) nell'organizzazione.
    
    d. **File, cartella o sito:** Digitare il nome di un file o di una cartella per la ricerca di attività correlate al file della cartella che contiene la parola chiave specificata. È anche possibile specificare un URL di un file o una cartella. Se si utilizza un URL, assicurarsi che il tipo di percorso URL completo o se si digita solo una parte dell'URL non includa caratteri o spazi speciali. Lasciare questa casella vuota per restituire le voci per tutti i file e le cartelle nell'organizzazione. Questo campo viene lasciato vuoto in tutti gli scenari di risoluzione dei problemi descritti in questo articolo.
    
5. Selezionare **Cerca** per eseguire la ricerca utilizzando i criteri di ricerca. 
    
    I risultati della ricerca vengono caricati e dopo alcuni istanti vengono visualizzati sotto **risultati** nella pagina di **ricerca del registro di controllo** . In ognuna delle sezioni di questo articolo vengono fornite indicazioni sugli aspetti da cercare nel contesto dello scenario di risoluzione dei problemi specifico.

    Per ulteriori informazioni sulla visualizzazione, il filtro o l'esportazione dei risultati di ricerca del registro di controllo, vedere:

    - [Visualizzare i risultati della ricerca](search-the-audit-log-in-security-and-compliance.md#step-2-view-the-search-results)
    - [Filtrare i risultati della ricerca](search-the-audit-log-in-security-and-compliance.md#step-3-filter-the-search-results)
    - [Esportare i risultati della ricerca](search-the-audit-log-in-security-and-compliance.md#step-4-export-the-search-results-to-a-file)

## <a name="find-the-ip-address-of-the-computer-used-to-access-a-compromised-account"></a>Individuare l'indirizzo IP del computer utilizzato per accedere a un account compromesso

L'indirizzo IP corrispondente a un'attività eseguita da qualsiasi utente è incluso nella maggior parte dei record di controllo. Le informazioni sul client utilizzato sono incluse anche nel record di controllo.

Ecco come configurare una query di ricerca del registro di controllo per questo scenario:

**Attività:** Se pertinente per il caso, selezionare un'attività specifica da cercare. Per la risoluzione dei problemi relativi agli account compromessi, è consigliabile selezionare l' **utente connesso all'attività della cassetta postale** in **attività Cassetta postale di Exchange**. In questo modo vengono restituiti i record di controllo che mostrano l'indirizzo IP utilizzato per l'accesso alla cassetta postale. In caso contrario, lasciare vuoto questo campo per restituire i record di controllo per tutte le attività. 

> [!TIP]
> Se si lascia questo campo vuoto, verranno restituite le attività di **UserLoggedIn** , che è un'attività di Azure Active Directory che indica che un utente ha eseguito l'accesso a un account. Utilizzare il filtro nei risultati della ricerca per visualizzare i record di controllo di **UserLoggedIn** .

Data di **inizio** e **Data di fine:** Selezionare un intervallo di date applicabile all'inchiesta.

**Utenti:** Se si sta esaminando un account compromesso, selezionare l'utente il cui account è stato compromesso. Restituisce i record di controllo per le attività eseguite dall'account utente.

**File, cartella o sito:** Lasciare vuoto questo campo.

Dopo aver eseguito la ricerca, l'indirizzo IP di ogni attività viene visualizzato nella colonna **indirizzo IP** nei risultati della ricerca. Selezionare il record nei risultati della ricerca per visualizzare informazioni più dettagliate sulla pagina a comparsa.

## <a name="determine-who-set-up-email-forwarding-for-a-mailbox"></a>Determinare gli utenti che configurano l'inoltro della posta elettronica per una cassetta postale

Quando l'inoltro della posta elettronica è configurato per una cassetta postale, i messaggi di posta elettronica inviati alla cassetta postale vengono inoltrati a un'altra cassetta postale. I messaggi possono essere inoltrati agli utenti all'interno o all'esterno dell'organizzazione. Quando l'inoltro della posta elettronica è configurato in una cassetta postale, il cmdlet Exchange Online sottostante utilizzato è **Set-Mailbox**.

Ecco come configurare una query di ricerca del registro di controllo per questo scenario:

**Attività:** Lasciare vuoto questo campo in modo che la ricerca restituisca i record di controllo per tutte le attività. Questa operazione è necessaria per restituire tutti i record di controllo relativi al cmdlet **Set-Mailbox** .

Data di **inizio** e **Data di fine:** Selezionare un intervallo di date applicabile all'inchiesta.

**Utenti:** A meno che non si stia indagando su un problema di inoltro della posta elettronica per un utente specifico, lasciare vuoto questo campo. Questo consente di identificare se l'inoltro della posta elettronica è stato configurato per qualsiasi utente.

**File, cartella o sito:** Lasciare vuoto questo campo.

Dopo aver eseguito la ricerca, selezionare **Filtra i risultati** nella pagina dei risultati di ricerca. Nella casella in intestazione colonna **attività** digitare **Set-Mailbox** in modo che vengano visualizzati solo i record di controllo correlati al cmdlet **Set-Mailbox** .

![Filtraggio dei risultati di una ricerca nel registro di controllo](../media/emailforwarding1.png)

A questo punto, è necessario esaminare i dettagli di ogni record di controllo per determinare se l'attività è correlata all'inoltro della posta elettronica. Selezionare il record di controllo per visualizzare la pagina dei **Dettagli** dell'icona a comparsa e quindi selezionare **altre informazioni**. Nella schermata e nelle descrizioni seguenti vengono evidenziate le informazioni che indicano che l'inoltro della posta elettronica è stato impostato sulla cassetta postale.

![Informazioni dettagliate dal record di controllo](../media/emailforwarding2.png)

a. Nel campo **ObjectID** viene visualizzato l'alias della cassetta postale in cui è stato impostato l'inoltro della posta elettronica. Questa cassetta postale viene visualizzata anche nella colonna **elemento** nella pagina dei risultati di ricerca.

b. Nel campo **parametri** , il valore *ForwardingSmtpAddress* indica che l'inoltro della posta elettronica è stato impostato sulla cassetta postale. In questo esempio, la posta viene inoltrata all'indirizzo di posta elettronica mike@contoso.com, che si trova all'esterno dell'organizzazione di alpinehouse.onmicrosoft.com.

c. Il valore *true* per il parametro *DeliverToMailboxAndForward* indica che una copia del messaggio viene recapitata a Sarad@alpinehouse.onmicrosoft.com *ed* è inoltrata all'indirizzo di posta elettronica specificato dal parametro *ForwardingSmtpAddress* , che in questo esempio è Mike@contoso.com. Se il valore del parametro *DeliverToMailboxAndForward* è impostato su *false*, la posta elettronica viene inoltrata solo all'indirizzo specificato dal parametro *ForwardingSmtpAddress* . Non viene recapitato alla cassetta postale specificata nel campo **ObjectID** .

d. Il campo **userid** indica l'utente che ha impostato l'inoltro della posta elettronica sulla cassetta postale specificata nel campo **ObjectID** . Questo utente viene inoltre visualizzato nella colonna **utente** della pagina dei risultati di ricerca. In questo caso, sembra che il proprietario della cassetta postale abbia impostato l'inoltro della posta elettronica sulla sua cassetta postale.

Se si determina che l'inoltro della posta elettronica non deve essere impostato sulla cassetta postale, è possibile rimuoverlo eseguendo il comando seguente in PowerShell di Exchange Online:

```powershell
Set-Mailbox <mailbox alias> -ForwardingSmtpAddress $null 
```

Per ulteriori informazioni sui parametri relativi all'inoltro della posta elettronica, vedere l'articolo [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/set-mailbox) .

## <a name="determine-if-a-user-deleted-email-items"></a>Determinare se un utente ha eliminato gli elementi di posta elettronica

A partire da gennaio 2019, Microsoft sta attivando la registrazione di controllo delle cassette postali per impostazione predefinita per tutte le organizzazioni di Office 365 e Microsoft. Ciò significa che alcune azioni eseguite dai proprietari delle cassette postali vengono registrate automaticamente e i record di controllo della cassetta postale corrispondenti sono disponibili quando si effettua la ricerca nel registro di controllo della cassetta postale. Prima che il controllo delle cassette postali fosse attivato per impostazione predefinita, è necessario abilitarlo manualmente per ogni cassetta postale dell'utente nell'organizzazione. 

Le azioni delle cassette postali registrate per impostazione predefinita includono le azioni della cassetta postale SoftDelete e HardDelete eseguite dai proprietari delle cassette postali. Questo significa che è possibile utilizzare la procedura seguente per eseguire una ricerca nel registro di controllo per gli eventi relativi agli elementi di posta elettronica eliminati. Per ulteriori informazioni sul controllo delle cassette postali per impostazione predefinita, vedere [gestire il controllo delle cassette postali](enable-mailbox-auditing.md).

Ecco come configurare una query di ricerca del registro di controllo per questo scenario:

**Attività:** In **attività Cassetta postale di Exchange**selezionare una o entrambe le attività seguenti:

- **Messaggi eliminati dalla cartella Posta eliminata:** Questa attività corrisponde all'azione di controllo delle cassette postali di **SoftDelete** . Questa attività viene inoltre registrata quando un utente Elimina definitivamente un elemento selezionandolo e premendo **MAIUSC + CANC**. Dopo l'eliminazione definitiva di un elemento, l'utente può ripristinarlo fino alla scadenza del periodo di conservazione degli elementi eliminati.

- **Messaggi eliminati dalla cassetta postale:** Questa attività corrisponde all'azione di controllo delle cassette postali di **HardDelete** . Questa operazione viene registrata quando un utente elimina un elemento dalla cartella elementi ripristinabili. Gli amministratori possono utilizzare lo strumento di ricerca contenuto nel centro sicurezza e conformità per cercare e recuperare gli elementi eliminati fino a quando il periodo di conservazione degli elementi eliminati non scade o più a lungo se la cassetta postale dell'utente è in attesa.

Data di **inizio** e **Data di fine:** Selezionare un intervallo di date applicabile all'inchiesta.

**Utenti:** Se si seleziona un utente in questo campo, lo strumento di ricerca del registro di controllo restituirà i record di controllo per gli elementi di posta elettronica eliminati (SoftDeleted o HardDeleted) dall'utente specificato. In alcuni casi, l'utente che elimina un messaggio di posta elettronica potrebbe non essere il proprietario della cassetta postale.

**File, cartella o sito:** Lasciare vuoto questo campo.

Dopo aver eseguito la ricerca, è possibile filtrare i risultati della ricerca per visualizzare i record di controllo per gli elementi eliminati temporaneamente o per gli elementi eliminati in modo rigido. Selezionare il record di controllo per visualizzare la pagina dei **Dettagli** dell'icona a comparsa e quindi selezionare **altre informazioni**. Ulteriori informazioni sull'elemento eliminato, ad esempio la riga dell'oggetto e la posizione dell'elemento quando è stata eliminata, vengono visualizzate nel campo **AffectedItems** . Nelle schermate seguenti viene mostrato un esempio del campo **AffectedItems** da un elemento eliminato temporaneamente e da un elemento eliminato definitivamente.

**Esempio di campo AffectedItems per l'elemento eliminato temporaneamente**

![Record di controllo per elementi eliminati temporaneamente](../media/softdeleteditem.png)

**Esempio di campo AffectedItems per gli elementi eliminati in modo rigido**

![Record di controllo per l'elemento di posta elettronica eliminato definitivamente](../media/harddeleteditem.png)

### <a name="recover-deleted-email-items"></a>Recuperare gli elementi di posta elettronica eliminati

Gli utenti possono recuperare gli elementi eliminati temporaneamente se il periodo di conservazione degli elementi eliminati non è scaduto. In Exchange Online, il periodo di conservazione degli elementi eliminati predefinito è di 14 giorni, ma gli amministratori possono aumentare questa impostazione fino a un massimo di 30 giorni. Indirizzare gli utenti a [recuperare elementi o messaggi di posta elettronica eliminati in Outlook sul Web](https://support.office.com/article/Recover-deleted-items-or-email-in-Outlook-Web-App-C3D8FC15-EEEF-4F1C-81DF-E27964B7EDD4) per istruzioni sul ripristino degli elementi eliminati.

Come spiegato in precedenza, gli amministratori potrebbero essere in grado di recuperare gli elementi eliminati definitivamente se il periodo di conservazione degli elementi eliminati non è scaduto o se la cassetta postale è in attesa, in questo caso gli elementi vengono mantenuti fino alla scadenza della durata del blocco. Quando si esegue una ricerca di contenuto, gli elementi eliminati temporaneamente e eliminati nella cartella elementi ripristinabili vengono restituiti nei risultati della ricerca se corrispondono alla query di ricerca. Per ulteriori informazioni sull'esecuzione di ricerche di contenuto, vedere [Content search in Office 365](content-search.md).

> [!TIP]
> Per cercare gli elementi di posta elettronica eliminati, cercare tutto o parte della riga dell'oggetto visualizzata nel campo **AffectedItems** del record di controllo.

## <a name="determine-if-a-user-created-an-inbox-rule"></a>Determinare se un utente ha creato una regola di posta in arrivo

Quando gli utenti creano una regola di posta in arrivo per la cassetta postale di Exchange Online, il record di controllo corrispondente viene salvato nel log di controllo. Per ulteriori informazioni sulle regole di posta in arrivo, vedere:

- [Utilizzare le regole di posta in arrivo in Outlook sul Web](https://support.office.com/article/use-inbox-rules-in-outlook-on-the-web-8400435c-f14e-4272-9004-1548bb1848f2)
- [Gestione dei messaggi di posta elettronica in Outlook tramite le regole](https://support.office.com/article/Manage-email-messages-by-using-rules-C24F5DEA-9465-4DF4-AD17-A50704D66C59)

Ecco come configurare una query di ricerca del registro di controllo per questo scenario:

**Attività:** In **attività Cassetta postale di Exchange**, selezionare **New-InboxRule creare/modificare/abilitare/disabilitare la regola di posta in arrivo**.

Data di **inizio** e **Data di fine:** Selezionare un intervallo di date applicabile all'inchiesta.

**Utenti:** A meno che non si stia studiando un utente specifico, lasciare vuoto questo campo. In questo modo è possibile identificare le nuove regole di posta in arrivo configurate da qualsiasi utente.

**File, cartella o sito:** Lasciare vuoto questo campo.

Dopo aver eseguito la ricerca, i record di controllo per questa attività vengono visualizzati nei risultati della ricerca. Selezionare un record di controllo per visualizzare la pagina dei **Dettagli** del riquadro a comparsa e quindi selezionare **altre informazioni**. Le informazioni sulle impostazioni delle regole di posta in arrivo vengono visualizzate nel campo **parametri** . Nella schermata e nelle descrizioni seguenti vengono evidenziate le informazioni sulle regole di posta in arrivo.

![Record di controllo per la nuova regola di posta in arrivo](../media/NewInboxRuleRecord.png)

a. Nel campo **ObjectID** viene visualizzato il nome completo della regola di posta in arrivo. Questo nome include l'alias della cassetta postale dell'utente (ad esempio, Sarad) e il nome della regola di posta in arrivo (ad esempio, "move messages from admin").

b. Nel campo **parametri** viene visualizzata la condizione della regola di posta in arrivo. In questo esempio, la condizione è specificata dal parametro *from* . Il valore definito per il parametro *from* indica che la regola di posta in arrivo agisce sul messaggio di posta elettronica inviato da admin@alpinehouse.onmicrosoft.com. Per un elenco completo dei parametri che possono essere utilizzati per definire le condizioni delle regole di posta in arrivo, vedere l'articolo [New-InboxRule](https://docs.microsoft.com/powershell/module/exchange/new-inboxrule) .

c. Il parametro *MoveToFolder* consente di specificare l'azione per la regola di posta in arrivo. In questo esempio, i messaggi ricevuti da admin@alpinehouse.onmicrosoft.com vengono spostati nella cartella denominata *AdminSearch*. Per un elenco completo dei parametri che possono essere utilizzati per definire l'azione di una regola di posta in arrivo, vedere anche l'articolo [New-InboxRule](https://docs.microsoft.com/powershell/module/exchange/new-inboxrule) .

d. Il campo **userid** indica l'utente che ha creato la regola di posta in arrivo specificata nel campo **ObjectID** . Questo utente viene inoltre visualizzato nella colonna **utente** della pagina dei risultati di ricerca.

## <a name="investigate-why-there-was-a-successful-login-by-a-user-outside-your-organization"></a>Esaminare il motivo per cui è stato eseguito un account di accesso corretto da un utente esterno all'organizzazione

Quando si esaminano i record di controllo nel log di controllo, è possibile che vengano visualizzati record che indicano che un utente esterno è stato autenticato da Azure Active Directory e che ha eseguito correttamente l'accesso all'organizzazione. Ad esempio, un amministratore in contoso.onmicrosoft.com può visualizzare un record di controllo che indica che un utente di un'organizzazione diversa (ad esempio fabrikam.onmicrosoft.com) ha eseguito correttamente l'accesso a contoso.onmicrosoft.com. Analogamente, è possibile che vengano visualizzati i record di controllo che indicano che gli utenti con un account Microsoft (MSA), ad esempio Outlook.com o Live.com, hanno effettuato correttamente l'accesso all'organizzazione. In questi casi, l'attività controllata è l' **utente**che ha effettuato l'accesso. 

Si tratta di un comportamento legato alla progettazione del prodotto. Azure Active Directory (Azure AD), il servizio directory, consente di fare qualcosa chiamato *autenticazione pass-through* quando un utente esterno tenta di accedere a un sito di SharePoint o a una posizione di OneDrive nell'organizzazione. Quando l'utente esterno tenta di eseguire questa operazione, viene richiesto di immettere le proprie credenziali. Azure Active Directory utilizza le credenziali per autenticare l'utente, in modo che solo Azure AD verifichi che l'utente sia quello che dicono di essere. L'indicazione dell'account di accesso con esito positivo nel record di controllo è il risultato di Azure AD Authenticating the user. L'account di accesso con esito positivo non significa che l'utente sia stato in grado di accedere alle risorse o di eseguire altre azioni nell'organizzazione. Indica solo che l'utente è stato autenticato da Azure AD. Per consentire a un utente pass-through di accedere alle risorse di SharePoint o OneDrive, un utente dell'organizzazione deve condividere in modo esplicito una risorsa con l'utente esterno inviando un collegamento di condivisione di un invito o di condivisione anonima. 

> [!NOTE]
> Azure AD consente l'autenticazione pass-through solo per *le applicazioni di terze parti*, ad esempio SharePoint Online e OneDrive for business. Non è consentito per altre applicazioni di terze parti.

Di seguito è riportato un esempio e le descrizioni delle proprietà rilevanti in un record di controllo per un utente che ha **eseguito l'accesso** a un evento che è il risultato dell'autenticazione pass-through. Selezionare il record di controllo per visualizzare la pagina dei **Dettagli** dell'icona a comparsa e quindi selezionare **altre informazioni**.

![Esempio di record di controllo per l'autenticazione pass-thru completata](../media/PassThroughAuth1.png)

   a. Questo campo indica che l'utente che ha tentato di accedere a una risorsa nell'organizzazione non è stato trovato nell'Azure AD dell'organizzazione.

   b. In questo campo viene visualizzato l'UPN dell'utente esterno che ha tentato di accedere a una risorsa nell'organizzazione. Questo ID utente viene identificato anche nelle proprietà **User** e **userid** del record di controllo.

   c. La proprietà **ApplicationID** identifica l'applicazione che ha attivato la richiesta di accesso. Il valore di 00000003-0000-0FF1-CE00-000000000000 visualizzato nella proprietà ApplicationId in questo record di controllo indica SharePoint Online. OneDrive for business ha anch ' esso lo stesso ApplicationId.

   d. Ciò indica che l'autenticazione pass-through ha avuto esito positivo. In altre parole, l'utente è stato autenticato correttamente da Azure AD. 

   e. Il valore **RecordType** di **15** indica che l'attività controllata (UserLoggedIn) è un evento di accesso del servizio token di sicurezza (STS) in Azure ad.

Per ulteriori informazioni sulle altre proprietà visualizzate in un record di controllo di UserLoggedIn, vedere le informazioni sullo schema relative AD Azure AD in [Office 365 Management Activity API schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#azure-active-directory-base-schema).

Di seguito sono riportati due esempi di scenari che comportano l'accesso di un **utente con** esito positivo all'attività di controllo a causa dell'autenticazione pass-through: 

  - Un utente con un account Microsoft (ad esempio SaraD@outlook.com) ha tentato di accedere a un documento in un account OneDrive for business in fourthcoffee.onmicrosoft.com e non è presente un account utente Guest corrispondente per SaraD@outlook.com in fourthcoffee.onmicrosoft.com.

  - Un utente con un account aziendale o dell'Istituto di istruzione in un'organizzazione (ad esempio pilarp@fabrikam.onmicrosoft.com) ha tentato di accedere a un sito di SharePoint in contoso.onmicrosoft.com e non è presente un account utente Guest corrispondente per pilarp@fabrikam.com in contoso.onmicrosoft.com.


### <a name="tips-for-investigating-successful-logins-resulting-from-pass-through-authentication"></a>Suggerimenti per l'analisi degli account di accesso riusciti risultanti dall'autenticazione pass-through

- Eseguire una ricerca nel registro di controllo per le attività eseguite dall'utente esterno identificato nell'utente che ha eseguito l' **accesso** al record di controllo. Digitare l'UPN per l'utente esterno nella casella **utenti** e utilizzare un intervallo di date se pertinente allo scenario. Ad esempio, è possibile creare una ricerca utilizzando i seguenti criteri di ricerca:

   ![Ricerca di tutte le attività eseguite dall'utente esterno](../media/PassThroughAuth2.png)

    Oltre all'utente che ha **effettuato l'accesso** , è possibile che vengano restituiti altri record di controllo, ad esempio per indicare a un utente dell'organizzazione risorse condivise con l'utente esterno e se l'utente esterno ha eseguito l'accesso, la modifica o il download di un documento condiviso con essi.

- Cercare le attività di condivisione di SharePoint che indichino che un file è stato condiviso con l'utente esterno identificato da un utente che ha **eseguito l'accesso al** record di controllo. Per altre informazioni, vedere [Usare il controllo della condivisione nel log di controllo](use-sharing-auditing.md).

- Esportare i risultati della ricerca del registro di controllo che contengono record rilevanti per l'analisi in modo che sia possibile utilizzare Excel per cercare altre attività correlate all'utente esterno. Per ulteriori informazioni, vedere [esportare, configurare e visualizzare i record del registro di controllo](export-view-audit-log-records.md).
