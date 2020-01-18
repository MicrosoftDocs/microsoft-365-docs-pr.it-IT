---
title: Richieste di Customer Lockbox di Office 365
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
search.appverid:
- BCS160
- MET150
- MOE150
description: Informazioni sulle richieste dell'archivio protetto dei clienti che consentono di controllare il modo in cui un tecnico del supporto Microsoft può accedere ai dati durante l'esecuzione di un problema.
ms.openlocfilehash: a9f7f6116d4667e294666afc71747a6fad1efb33
ms.sourcegitcommit: 48a45b0d2c60d4d79669174f462603a43f272875
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/18/2020
ms.locfileid: "41233767"
---
# <a name="customer-lockbox-in-office-365"></a>Archivio protetto dei clienti in Office 365

In questo articolo vengono fornite indicazioni per la distribuzione e la configurazione di una funzionalità attualmente disponibile solo per le organizzazioni che dispongono di un abbonamento a Microsoft 365 E5, Office 365 E5, protezione delle informazioni e conformità o Advanced Compliance Add-on. L'archivio protetto dei clienti supporta le richieste di accesso ai dati di Exchange Online, SharePoint Online e OneDrive for business. Per consigliare il supporto per altri servizi di Office 365, inviare una richiesta a [office 365 UserVoice](https://office365.uservoice.com/).

L'archivio protetto dei clienti garantisce che Microsoft non sia in grado di accedere al contenuto per eseguire un'operazione del servizio senza l'approvazione esplicita. L'archivio protetto dei clienti introduce il flusso di lavoro di approvazione per le richieste di accesso al contenuto.

In alcuni casi, gli ingegneri Microsoft aiutano la risoluzione dei problemi relativi ai clienti nel processo di supporto. In genere, i problemi vengono risolti tramite una vasta gamma di telemetria e strumenti di debug Microsoft per i propri servizi. Tuttavia, in alcuni casi è necessario che un tecnico Microsoft acceda al contenuto dei clienti per determinare la causa principale e risolvere il problema. L'archivio protetto dei clienti richiede all'ingegnere di richiedere l'accesso da parte del cliente come passaggio finale del flusso di lavoro di approvazione. In questo modo le organizzazioni sono autorizzate ad approvare o negare queste richieste e a fornire il controllo di accesso diretto al cliente.

### <a name="customer-lockbox-overview-video"></a>Video panoramica dell'archivio clienti

> [!VIDEO https://www.microsoft.com/videoplayer/embed/8fecf10b-1f03-4849-8b67-76d3d2a43f26?autoplay=false]

## <a name="customer-lockbox-workflow"></a>Flusso di lavoro archivio clienti

I passaggi seguenti delineano il flusso di lavoro tipico quando un tecnico Microsoft avvia una richiesta di archivio protetto dei clienti:

1. Un utente di un'organizzazione avverte un problema con la cassetta postale di Office 365.

2. Dopo che l'utente ha risolto il problema, ma non è in grado di correggerlo, apre una richiesta di supporto con il supporto tecnico Microsoft.

3. Un responsabile del supporto tecnico Microsoft esamina la richiesta di servizio e determina la necessità di accedere al tenant dell'organizzazione per risolvere il problema in Exchange Online.

4. L'ingegnere del supporto tecnico Microsoft accede allo strumento di richiesta di archivio protetto del cliente e effettua una richiesta di accesso ai dati che include il nome del tenant dell'organizzazione, il numero di richiesta di servizio e il tempo stimato per cui il tecnico deve accedere ai dati.

5. Dopo che un responsabile del supporto tecnico Microsoft ha approvato la richiesta, il servizio di gestione dei clienti ha inviato all'organizzazione una notifica di posta elettronica relativa alla richiesta di accesso in sospeso da Microsoft.

    ![Esempio di notifica di posta elettronica dell'archivio clienti](media/CustomerLockbox1.png)

   Tutti gli utenti a cui è stato assegnato il ruolo di amministratore del [responsabile dell'approvazione dei clienti](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) nell'interfaccia di amministrazione di Microsoft 365 possono approvare le richieste di

6. Il responsabile approvazione accede all'interfaccia di amministrazione di Microsoft 365 e approva la richiesta. Questo passaggio consente di attivare la creazione di un record di controllo tramite la ricerca nel registro di controllo di Office 365. Per ulteriori informazioni, vedere [richieste di controllo dell'archivio protetto dei clienti](#auditing-customer-lockbox-requests).

   Se il cliente rifiuta la richiesta o non approva la richiesta entro 12 ore, la richiesta scade e non viene concesso alcun accesso a Microsoft Engineer.

   > [!IMPORTANT]
   > Microsoft non include collegamenti nelle notifiche di posta elettronica dell'archivio clienti che richiedono l'accesso a Office 365.

7. Dopo che il responsabile approvazione dell'organizzazione approva la richiesta, il tecnico Microsoft riceve il messaggio di approvazione, accede al tenant in Exchange Online e risolve il problema del cliente. Gli ingegneri Microsoft hanno la durata richiesta per risolvere il problema dopo il quale l'accesso è stato revocato automaticamente.

> [!NOTE]
> Tutte le azioni eseguite da un tecnico Microsoft vengono registrate nel registro di controllo di Office 365. È possibile eseguire la ricerca e la revisione dei record di controllo.

## <a name="turn-customer-lockbox-requests-on-or-off"></a>Attivazione o disattivazione delle richieste dell'archivio clienti

È possibile abilitare i controlli archivio clienti all'interno dell'interfaccia di amministrazione di Microsoft 365. Quando si attiva l'archivio protetto dei clienti, Microsoft deve ottenere l'approvazione dell'organizzazione prima di accedere a qualsiasi contenuto del tenant.

1. L'utilizzo di [https://admin.microsoft.com](https://admin.microsoft.com) un account aziendale o dell'Istituto di istruzione con l'amministratore globale o il ruolo **responsabile approvazione accesso client** , accedere e accedere.

2. Scegliere **impostazioni > privacy & sicurezza**.

    ![Modificare le impostazioni del servizio di archivio clienti nell'interfaccia di amministrazione](media/CustomerLockbox2.png)

3. Nel riquadro **archivio protetto del cliente** , scegliere **modifica**, quindi sposta l' **interruttore su attivato o** **disattivato** per attivare o disattivare la funzionalità.

    ![Require approval for Customer Lockbox](media/CustomerLockbox4.png)

## <a name="approve-or-deny-a-customer-lockbox-request"></a>Approvare o rifiutare una richiesta di archivio protetto dei clienti

1. L'utilizzo di [https://admin.microsoft.com](https://admin.microsoft.com) un account aziendale o dell'Istituto di istruzione con l'amministratore globale o il ruolo **responsabile approvazione accesso client** , accedere e accedere.

2. Scegliere **supporto > richieste di archivio clienti**.

    ![Fare clic su supporto, quindi su richieste archivio clienti](media/CustomerLockbox5.png)

    Viene visualizzato un elenco delle richieste dell'archivio protetto dei clienti.

    ![Elenco delle richieste dell'archivio protetto dei clienti](media/CustomerLockbox6.png)

3. Selezionare la richiesta di un archivio protetto dei clienti e quindi scegliere **approva** o **rifiuta**.

    ![Approvare o negare le richieste dell'archivio clienti](media/CustomerLockbox7.png)

    Viene visualizzato un messaggio di conferma relativo all'approvazione della richiesta dell'archivio protetto dei clienti.

    ![Approvare o negare le richieste dell'archivio clienti](media/CustomerLockbox8.png)

## <a name="auditing-customer-lockbox-requests"></a>Richieste di controllo dell'archivio protetto dei clienti

I record di controllo che corrispondono alle richieste dell'archivio protetto dei clienti vengono registrati nel log di controllo di Office 365. È possibile accedere a questi registri utilizzando lo [strumento di ricerca del registro di controllo](search-the-audit-log-in-security-and-compliance.md) nel centro sicurezza & conformità di Office 365. Le azioni relative a una richiesta di accettazione o negazione di una cassetta postale del cliente e le azioni eseguite da ingegneri Microsoft (quando le richieste di accesso sono approvate) sono registrate anche nel log di controllo di Office 365. È possibile eseguire la ricerca e la revisione dei record di controllo.

### <a name="search-the-audit-log-for-activity-related-to-customer-lockbox-requests"></a>Eseguire una ricerca nel registro di controllo per attività correlate alle richieste dell'archivio protetto dei clienti

Prima di poter utilizzare il registro di controllo per tenere presenti le richieste per l'archivio protetto dei clienti, è necessario eseguire alcuni passaggi per impostare la registrazione di controllo. Per ulteriori informazioni, vedere [Search the audit log in the Office 365 Security & Compliance Center](https://docs.microsoft.com/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#before-you-begin). Dopo aver completato l'installazione, attenersi alla procedura seguente per creare una query di ricerca del registro di controllo per restituire i record di controllo relativi all'archivio protetto dei clienti:

1. Passare a [https://protection.office.com](https://protection.office.com).
  
2. Accedere a Office 365 usando l'account aziendale o dell'istituto di istruzione.

3. Nel riquadro sinistro del Centro sicurezza & conformità scegliere **Search &** > **Search log di controllo di ricerca**.

    Viene visualizzata la pagina di **ricerca del registro di controllo** .

    ![Pagina di ricerca del registro di controllo](media/auditlogsearch1.png)
  
4. Configurare i criteri di ricerca seguenti: 

    a. **Attività** -lasciare vuoto questo campo in modo che la ricerca restituisca i record di controllo per tutte le attività. Questa operazione è necessaria per restituire eventuali record di controllo relativi alle richieste dell'archivio protetto dei clienti e alle attività corrispondenti eseguite dagli ingegneri Microsoft.

    b. Data di **inizio** e **Data di fine** : selezionare un intervallo di data e ora per visualizzare gli eventi che si sono verificati entro quel periodo.

    c. **Utenti** : lasciare vuoto questo campo.

    d. **File, cartella o sito** : lasciare vuoto questo campo.

5. Fare clic su **Cerca** per eseguire la ricerca usando i criteri di ricerca.

    I risultati della ricerca vengono caricati e, dopo alcuni istanti, vengono visualizzati in **risultati** nella pagina **Ricerca log di controllo** .

6. Fare clic su **Filtra risultati** nella pagina dei risultati di ricerca ed eseguire una delle operazioni seguenti:

   - Per visualizzare i record di controllo relativi a un responsabile approvazione nell'organizzazione che approva o nega una richiesta di archivio protetto dei clienti: nella casella sotto la colonna **attività** digitare **set-AccessToCustomerDataRequest**.

   - Per visualizzare i record di controllo relativi a un tecnico Microsoft che esegue azioni in risposta a una richiesta di un archivio clienti approvato: nella casella sotto la colonna **utente** digitare **operatore Microsoft**. Nella colonna **attività** viene visualizzata l'azione eseguita dal tecnico.

      ![Filtro su "operatore Microsoft" per visualizzare i record di controllo](media/CustomerLockbox10.png)

7. Nell'elenco dei risultati, fare clic su un record di controllo per visualizzarlo.

### <a name="audit-record-for-a-customer-lockbox-access-request"></a>Record di controllo per una richiesta di accesso protetto dall'archivio clienti

Quando una persona all'interno dell'organizzazione approva o nega una richiesta di accesso protetto dei clienti, nel log di controllo di Office 365 viene registrato un record di controllo. Questo record contiene le informazioni seguenti.

| Proprietà del record di controllo| Descrizione|
|:---------- |:----------|
| Data       | La data e l'ora in cui è stata approvata o negata la richiesta di archivio clienti.
| Indirizzo IP | L'indirizzo IP del computer utilizzato dal responsabile approvazione per approvare o rifiutare una richiesta. |
| Utente       | L'account di servizio\[BOXServiceAccount@\]customerforest. prod.Outlook.com.            |
| Attività   | Set-AccessToCustomerDataRequest; si tratta dell'attività di controllo che viene registrata quando si approva o si nega una richiesta di archivio protetto dei clienti.                                |
| Elemento       | Il GUID della richiesta di archivio protetto dei clienti                             |

Nella schermata seguente viene mostrato un esempio di un record del registro di controllo che corrisponde a una richiesta di archivio clienti approvata. Se è stata negata una richiesta di archivio clienti, il valore del parametro **ApprovalDecision** sarebbe **Deny**.

![Record di controllo per una richiesta di un archivio clienti approvato](media/CustomerLockbox9.png)

> [!TIP]
> Per visualizzare informazioni più dettagliate in un record di controllo, fare clic su **altre informazioni**.

### <a name="audit-record-for-an-action-performed-by-a-microsoft-engineer"></a>Record di controllo per un'azione eseguita da un tecnico Microsoft

Le azioni eseguite da un tecnico Microsoft dopo che la richiesta di una cassetta del cliente è stata approvata (e che potrebbe causare l'accesso al contenuto del cliente) sono registrate nel registro di controllo. Questi record contengono le informazioni seguenti.

| Proprietà del record di controllo| Descrizione|
|:---------- |:----------|
| Data       | Data e ora in cui è stata eseguita l'azione. Si noti che l'ora in cui è stata eseguita l'azione sarà entro 4 ore dal momento in cui la richiesta di archivio protetto dei clienti è stata approvata.              |
| Indirizzo IP | L'indirizzo IP del computer utilizzato da Microsoft Engineer. |
| Utente       | Operatore Microsoft; Questo valore indica che questo record è correlato a una richiesta di archivio protetto dei clienti.                                  |
| Attività   | Nome dell'attività eseguita dal tecnico Microsoft.|
| Elemento       | \<vuota\>                                             |

## <a name="frequently-asked-questions"></a>Domande frequenti

#### <a name="which-office-365-services-does-customer-lockbox-apply-to"></a>A quali servizi di Office 365 viene applicato l'archivio protetto dei clienti?

L'archivio protetto dei clienti è attualmente supportato in Exchange Online, SharePoint Online e OneDrive for business.

#### <a name="is-customer-lockbox-available-to-all-office-365-customers"></a>L'archivio protetto dei clienti è disponibile per tutti i clienti di Office 365?

L'archivio protetto dei clienti è incluso con gli abbonamenti Microsoft 365 o Office 365 E5 e può essere aggiunto ad altri piani con una sottoscrizione di un componente aggiuntivo per la protezione delle informazioni e la conformità o per un abbonamento a Advanced Compliance. Per ulteriori informazioni, vedere [piani e prezzi](https://products.office.com/business/office-365-enterprise-e5-business-software) .

#### <a name="what-is-customer-content"></a>Che cos'è il contenuto del cliente?

Il contenuto del cliente è costituito dai dati creati dagli utenti di servizi e applicazioni di Office 365. Di seguito sono riportati alcuni esempi di contenuto dei clienti:

- Allegati del corpo o della posta elettronica

- Contenuto del sito di SharePoint

- Informazioni nel corpo di un file di SharePoint

- Corpo del file di presentazione di Skype for business

- Messaggi istantanei (messaggistica istantanea) o conversazioni vocali

- Dati di archiviazione strutturati o BLOB generati dall'utente (ad esempio, contenitori SQL)

- Informazioni sulla sicurezza di proprietà del cliente, ad esempio certificati, chiavi di crittografia e password

- Inferenze e tutte le inferenze successive, se il contenuto del cliente resta

Per ulteriori informazioni sul contenuto dei clienti in Office 365, vedere il [Centro protezione di office 365](https://products.office.com/business/office-365-trust-center-privacy/).

#### <a name="who-is-notified-when-there-is-a-request-to-access-my-content"></a>Chi riceve una notifica quando è presente una richiesta di accesso al contenuto?

Gli amministratori globali e tutti gli utenti a cui è stato assegnato il ruolo di amministratore del responsabile dell'approvazione del cliente. Questi sono anche gli stessi utenti che possono approvare le richieste dell'archivio protetto dei clienti.

#### <a name="who-can-approve-or-reject-these-requests-in-my-organization"></a>Chi può approvare o rifiutare queste richieste nell'organizzazione?

Amministratori globali e chiunque sia assegnato il ruolo di amministratore del responsabile dell'approvazione del cliente può approvare le richieste di accesso protetto dei clienti I clienti controllano queste assegnazioni di ruolo nelle rispettive organizzazioni.

#### <a name="how-do-i-opt-in-to-customer-lockbox"></a>Come si opta per l'archivio protetto dei clienti?

Un amministratore globale può abilitare e configurare l'archivio protetto dei clienti nell'interfaccia di amministrazione di Microsoft 365 o Microsoft 365.

#### <a name="if-i-approve-a-customer-lockbox-request-what-can-the-engineer-do-and-how-will-i-know-what-the-microsoft-engineer-did"></a>Se si approva la richiesta di un archivio protetto dei clienti, cosa può fare il tecnico e come è possibile sapere cosa ha fatto il tecnico Microsoft?

Dopo aver approvato una richiesta di accesso protetto per i clienti, Microsoft Engineer ha concesso questi privilegi necessari per accedere al contenuto dei clienti utilizzando i cmdlet preapprovati. Le azioni intraprese dagli ingegneri Microsoft in risposta alle richieste dell'archivio protetto dei clienti sono registrate e accessibili nel log di controllo nel centro sicurezza & conformità di Office 365.

#### <a name="how-do-i-know-that-microsoft-follows-the-approval-process"></a>Come si fa a sapere se Microsoft segue il processo di approvazione?

È possibile fare riferimento incrociato alle notifiche di approvazione della posta elettronica inviate agli amministratori e ai responsabili approvazione dell'organizzazione con la cronologia delle richieste dell'archivio protetto dei clienti nell'interfaccia di amministrazione di Microsoft 365.

L'archivio protetto dei clienti è incluso nel [report di controllo SOC 1 SSAE 16](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=91592749-e86a-43ac-801e-121382614681&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC%20%2F%20SSAE%2016%20Reports)più recente. Per ulteriori informazioni, è possibile trovare i report più recenti in [Microsoft Service Trust Portal](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=91592749-e86a-43ac-801e-121382614681&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC%20%2F%20SSAE%2016%20Reports).

#### <a name="can-microsoft-modify-the-list-of-approvers-for-my-tenant-if-not-how-is-it-prevented"></a>Microsoft può modificare l'elenco dei responsabili approvazione per il tenant? In caso contrario, come è precluso?

Solo un amministratore globale dell'organizzazione può specificare gli utenti autorizzati ad approvare le richieste dell'archivio protetto dei clienti. Questo significa che solo i membri del gruppo di amministratori globale in Azure Active Directory possono specificare gli utenti autorizzati ad approvare la richiesta. L'appartenenza al gruppo di amministratori globali in Azure Active Directory è gestita solo dall'organizzazione.

#### <a name="what-if-i-need-more-information-about-a-content-access-request-to-approve-it"></a>Che cosa fare se sono necessarie ulteriori informazioni su una richiesta di accesso al contenuto per approvarla?

Ogni richiesta dell'archivio protetto del cliente contiene un numero di richiesta di servizio di Office 365. È possibile contattare il supporto tecnico Microsoft e fare riferimento a questo numero di servizio per ottenere ulteriori informazioni sulla richiesta.

#### <a name="when-a-customer-lockbox-request-is-approved-how-long-are-the-permissions-valid"></a>Quando viene approvata una richiesta di archivio protetto dei clienti, per quanto tempo sono valide le autorizzazioni?

Attualmente, il periodo massimo per le autorizzazioni di accesso concesse a Microsoft Engineer è di 4 ore. Il tecnico Microsoft può anche richiedere un periodo di tempo più breve.

#### <a name="how-can-i-get-a-history-of-all-customer-lockbox-requests"></a>Come è possibile ottenere una cronologia di tutte le richieste dell'archivio protetto dei clienti?

Tutte le richieste dell'archivio protetto dei clienti vengono visualizzate nell'interfaccia di amministrazione di Microsoft 365.

#### <a name="how-do-i-correlate-the-content-access-requests-with-the-related-audit-logs"></a>In che modo è possibile correlare le richieste di accesso al contenuto con i registri di controllo correlati?

Il feed attività del centro conformità contiene le attività di registrazione dell'archivio protetto dei clienti. I clienti possono fare riferimento incrociato alle attività del registro dell'archivio protetto dei clienti dal feed attività rispetto alla richiesta di posta elettronica ricevuta.

#### <a name="what-happens-when-a-customer-doesnt-respond-to-a-customer-lockbox-request"></a>Cosa succede quando un cliente non risponde a una richiesta di archivio protetto dei clienti?

Le richieste dell'archivio protetto dei clienti hanno una durata predefinita di 12 ore. Se non si risponde a una richiesta entro 12 ore, la richiesta scade.

#### <a name="what-does-microsoft-do-when-a-customer-rejects-a-customer-lockbox-request"></a>Cosa fa Microsoft quando un cliente rifiuta una richiesta di un archivio protetto dei clienti?

Se un cliente rifiuta una richiesta di archivio clienti, non viene eseguito alcun accesso al contenuto del cliente. Se un utente dell'organizzazione continua a sperimentare un problema di servizio che richiede a Microsoft di accedere al contenuto del cliente per risolvere il problema, il problema del servizio potrebbe persistere e Microsoft ne informerà l'utente.

#### <a name="does-customer-lockbox-protect-against-data-requests-from-law-enforcement-agencies-or-other-third-parties"></a>L'archivio protetto dei clienti protegge dalle richieste di dati provenienti da agenzie di applicazione della legge o altre terze parti?

No. Microsoft richiede sul serio le richieste di terze parti per i dati dei clienti. Come provider di servizi cloud, Microsoft sostiene sempre la privacy dei dati del cliente. Nel caso in cui venga visualizzato un mandato di comparizione, Microsoft cerca sempre di reindirizzare la terza parte al cliente per ottenere le informazioni. (Leggere il Blog di Brad Smith: [proteggere i dati dei clienti dallo spionaggio governativo](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/)). Pubblicheremo periodicamente [informazioni dettagliate](https://www.microsoft.com/corporate-responsibility/lerr) sulle richieste di applicazione della legge ricevute da Microsoft.

Per ulteriori informazioni, vedere il [Centro protezione Microsoft](https://www.microsoft.com/trustcenter/default.aspx) relativo alle richieste di dati di terze parti e la sezione "divulgazione di dati dei clienti" nei [termini dei servizi online](https://www.microsoft.com/Licensing/product-licensing/products.aspx) .

#### <a name="how-does-microsoft-ensure-that-a-member-of-its-staff-doesnt-have-standing-access-to-customer-content-in-office-365-applications"></a>In che modo Microsoft garantisce che un membro del proprio personale non sia in grado di accedere al contenuto dei clienti nelle applicazioni di Office 365?

Microsoft implementa misure preventive estese mediante sistemi di controllo di accesso e misure investigative per identificare e risolvere i tentativi di eludere questi sistemi di controllo di accesso. Office 365 opera con i principi del privilegio minimo e dell'accesso just-in-time. Pertanto, nessun personale Microsoft dispone dell'autorizzazione necessaria per accedere ai contenuti dei clienti in maniera continuativa. Se l'autorizzazione viene concessa, è per una durata limitata. 

Office 365 utilizza un sistema di controllo di accesso denominato *archivio protetto* per elaborare le richieste per le autorizzazioni che conferiscono la possibilità di eseguire funzioni operative e amministrative all'interno del servizio. Un operatore deve richiedere l'accesso al contenuto del cliente tramite archivio protetto, che richiede quindi a una seconda persona di intervenire sulla richiesta (ad esempio, approvarlo) prima che venga concesso l'accesso. La seconda persona non può essere il richiedente e deve essere designata per approvare l'accesso al contenuto del cliente. Solo se la richiesta è approvata, l'operatore acquisisce l'accesso temporaneo al contenuto del cliente. Dopo la scadenza del periodo di elevazione, l'archivio protetto revoca l'accesso.

Per ulteriori informazioni sulle procedure generali sulla sicurezza di Microsoft, fare riferimento alle [condizioni dei servizi online](https://www.microsoft.com/licensing/product-licensing/products) .

#### <a name="under-what-circumstances-do-microsoft-engineers-need-access-to-my-content"></a>In quali circostanze gli ingegneri Microsoft devono accedere ai contenuti?

Lo scenario più comune in cui gli ingegneri Microsoft hanno necessità di accedere al contenuto dei clienti è quando il cliente effettua una richiesta di supporto che richiede l'accesso per la risoluzione dei problemi. Un principio fondamentale di Office 365 è che il servizio opera senza l'accesso di Microsoft al contenuto del cliente. Quasi tutte le operazioni di servizio eseguite da Microsoft sono completamente automatizzate e la partecipazione umana è estremamente controllata e sottratta al contenuto dei clienti. L'obiettivo di Office 365 è l'accesso ai contenuti dei clienti per supportare il servizio non è necessario finché il cliente non approva una richiesta specifica di Microsoft Access.

#### <a name="i-already-thought-my-data-was-secure-with-the-microsoft-cloud-so-why-do-i-need-customer-lockbox"></a>Già pensavo che i miei dati fossero protetti con il cloud Microsoft, quindi perché ho bisogno di un archivio protetto dei clienti?

L'archivio protetto dei clienti fornisce un ulteriore livello di controllo offrendo ai clienti la possibilità di concedere autorizzazioni di accesso esplicito per le operazioni del servizio. Se si dimostra che le procedure sono disponibili per l'autorizzazione di accesso ai dati esplicita, l'archivio clienti consente ai clienti di soddisfare determinati obblighi di conformità, come HIPAA e FEDRAMP.
