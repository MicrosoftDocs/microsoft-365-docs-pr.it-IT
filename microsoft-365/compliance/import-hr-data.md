---
title: Configurare un connettore per importare i dati sulle risorse umane
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: Gli amministratori possono configurare un connettore di dati per importare i dati dei dipendenti dal sistema HR (Human Resources) dell'organizzazione a Microsoft 365. In questo modo è possibile utilizzare i dati HR nei criteri di gestione dei rischi Insider utili per rilevare l'attività da parte di utenti specifici che possono rappresentare un rischio interno per la propria organizzazione.
ms.openlocfilehash: a8eaeda3bc883de55a2c588e39557b4517ae3cc5
ms.sourcegitcommit: 9f5b136b96b3af4db4cc6f5b1f35130ae60d6b12
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/15/2020
ms.locfileid: "47817166"
---
# <a name="set-up-a-connector-to-import-hr-data-preview"></a>Configurare un connettore per l'importazione dei dati HR (anteprima)

È possibile configurare un connettore di dati nel centro conformità di Microsoft 365 per importare i dati delle risorse umane (HR) relativi a eventi come le dimissioni dell'utente o una modifica del livello di lavoro di un utente. I dati HR possono quindi essere utilizzati dalla [soluzione di gestione dei rischi Insider](insider-risk-management.md) per generare indicatori di rischio che consentono di identificare eventuali attività dannose o il furto di dati da parte di utenti all'interno dell'organizzazione.

La configurazione di un connettore per i dati HR che i criteri di gestione dei rischi Insider possono utilizzare per generare indicatori di rischio consiste nella creazione di un file CSV che contiene i dati HR, la creazione di un'app in Azure Active Directory utilizzata per l'autenticazione, la creazione di un connettore di dati HR nel centro conformità di Microsoft 365 e l'esecuzione di uno script (su base pianificata) che consente di ingerire i dati HR nei file CSV nel cloud Microsoft in modo che sia disponibile per l'insider soluzione di gestione dei rischi.

## <a name="before-you-begin"></a>Prima di iniziare

- Determinare gli scenari e i dati HR da importare in Microsoft 365. In questo modo è possibile determinare il numero di file CSV e i connettori HR necessari per la creazione e la modalità di generazione e struttura dei file CSV. I dati HR che vengono importati sono determinati dai criteri di gestione dei rischi Insider che si desidera implementare. Per ulteriori informazioni, vedere passaggio 1.

- Determinare il modo in cui recuperare o esportare i dati dal sistema HR dell'organizzazione (e su base regolare) e aggiungerli ai file CSV creati nel passaggio 1. Lo script eseguito nel passaggio 4 caricherà i dati HR nei file CSV nel cloud Microsoft.

- L'organizzazione deve acconsentire a consentire al servizio di importazione di Office 365 di accedere ai dati nell'organizzazione. Per acconsentire a questa richiesta, accedere a [Questa pagina](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), accedere con le credenziali di un amministratore globale di Microsoft 365 e quindi accettare la richiesta. È necessario completare questo passaggio prima di poter creare correttamente il connettore HR nel passaggio 3.

- All'utente che crea il connettore HR nel passaggio 3 deve essere assegnato il ruolo di importazione/esportazione delle cassette postali in Exchange Online. Per impostazione predefinita, questo ruolo non è assegnato ad alcun gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo import export delle cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In alternativa, è possibile creare un nuovo gruppo di ruoli, assegnare il ruolo di esportazione delle cassette postali e quindi aggiungere gli utenti corretti come membri. Per ulteriori informazioni, vedere la sezione creare gruppi di [ruoli](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) o [modificare gruppi di ruoli](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) nell'articolo "gestire i gruppi di ruoli in Exchange Online".

- Lo script di esempio eseguito nel passaggio 4 caricherà i dati HR nel cloud Microsoft in modo che possa essere utilizzato dalla soluzione di gestione dei rischi Insider. Questo script di esempio non è supportato in alcun servizio o programma di supporto Microsoft standard. Lo script di esempio viene fornito come senza garanzie di alcun tipo. Microsoft esclude inoltre qualsiasi garanzia implicita, tra cui, senza limitazioni, tutte le garanzie implicite di commerciabilità o idoneità per uno scopo specifico. L'intero rischio derivante dall'utilizzo o dalle prestazioni dello script di esempio e della documentazione resta all'interno dell'utente. In nessun caso Microsoft, i suoi autori o chiunque altro coinvolto nella creazione, produzione o consegna degli script è da ritenersi responsabile per qualsiasi danno eventuale (inclusi, senza limitazione alcuna, danni riguardanti profitti aziendali, interruzione di attività, perdita di informazioni aziendali o altra perdita pecuniaria) derivanti dall'utilizzo o dall'incapacità di utilizzo degli script di esempio e della documentazione, anche nel caso in cui Microsoft sia stata avvisata della possibilità di tali danni.

## <a name="step-1-prepare-a-csv-file-with-your-hr-data"></a>Passaggio 1: preparare un file CSV con i dati HR

Il primo passaggio consiste nel creare un file CSV contenente i dati HR che il connettore verrà importato in Microsoft 365. Questi dati verranno utilizzati dalla soluzione di rischio Insider per generare indicatori di rischio potenziali. I dati per gli scenari HR seguenti possono essere importati in Microsoft 365:

- Dimissioni dei dipendenti. Informazioni sugli utenti che hanno lasciato l'organizzazione.

- Modifiche a livello di processo. Informazioni sulle modifiche apportate a livello di processo per gli utenti, ad esempio promozioni e demozioni.

- Revisioni delle prestazioni. Informazioni sulle prestazioni degli utenti.

- Piani di miglioramento delle prestazioni. Informazioni sui piani di miglioramento delle prestazioni per gli utenti.

Il tipo di dati HR da importare dipende dal criterio di gestione dei rischi Insider e dal modello di criteri corrispondente che si desidera implementare. Nella tabella seguente vengono illustrati i tipi di dati HR necessari per ogni modello di criteri:

| **Modello di criteri**| **Tipo di dati HR**|
|:-----------------------------------------------|:---------------------------------------------------------------------|
| Furto dei dati da parte degli utenti                   | Dimissioni dei dipendenti                                                 |
| Perdite di dati generali                              | Non supportato                                                        |
| Perdite di dati da parte di utenti prioritari                    | Non supportato                                                        |
| Perdite di dati da parte di utenti scontenti                 | Modifiche a livello di processo, revisioni delle prestazioni, piani di miglioramento delle prestazioni |
| Violazioni dei criteri di sicurezza generali              | Non supportato                                                        |
| Violazioni dei criteri di sicurezza da parte degli utenti   | Dimissioni dei dipendenti                                                 |
| Violazioni dei criteri di sicurezza per gli utenti con priorità    | Non supportato                                                        |
| Violazioni dei criteri di sicurezza da parte di utenti scontenti | Modifiche a livello di processo, revisioni delle prestazioni, piani di miglioramento delle prestazioni |
| Lingua offensiva nel messaggio di posta elettronica                     | Non supportato                                                        |

Per ulteriori informazioni sui modelli di criteri per la gestione dei rischi Insider, vedere [Insider Risk Management Policies](insider-risk-management-policies.md#policy-templates).

Per ogni scenario HR, è necessario fornire i dati HR corrispondenti in uno o più file CSV. Il numero di file CSV da utilizzare per l'implementazione della gestione dei rischi Insider è descritto più avanti in questa sezione.

Dopo aver creato il file CSV con i dati HR necessari, archiviarlo nel computer locale in cui viene eseguito lo script nel passaggio 4. È inoltre consigliabile implementare una strategia di aggiornamento per verificare che il file CSV contenga sempre le informazioni più aggiornate in modo che qualsiasi operazione esegua lo script, i dati HR più recenti vengano caricati nel cloud Microsoft e siano accessibili alla soluzione di gestione dei rischi Insider.

> [!IMPORTANT]
> I nomi delle colonne descritti nelle sezioni seguenti non sono parametri obbligatori, ma solo esempi. È possibile utilizzare qualsiasi nome di colonna nei file CSV. Tuttavia, i nomi di colonna utilizzati in un file CSV *devono* essere mappati al tipo di dati quando si crea il connettore HR nel passaggio 3. Si noti inoltre che i file CSV di esempio nelle sezioni seguenti sono visualizzati nella visualizzazione blocco note. È molto più semplice visualizzare e modificare i file CSV in Microsoft Excel.

Nelle sezioni seguenti vengono descritti i dati CSV necessari per ogni scenario HR.

### <a name="csv-file-for-employee-resignation-data"></a>File CSV per i dati di dimissioni dei dipendenti

Di seguito è riportato un esempio di file CSV per i dati sulle dimissioni dei dipendenti.

```text
EmailAddress,ResignationDate,LastWorkingDate
sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,2019-04-29T15:18:02.4675041+05:30
pilarp@contoso.com,2019-04-24T09:15:49Z,2019-04-29T15:18:02.7117540
```

Nella tabella seguente vengono descritte tutte le colonne del file CSV per i dati sulle dimissioni dei dipendenti.

| **Colonna**  |  **Descrizione**|
|:------------|:----------------|
|**EmailAddress**| Specifica l'indirizzo di posta elettronica (UPN) dell'utente con terminazione.|
| **ResignationDate** | Specifica la data in cui l'occupazione dell'utente è stata ufficialmente terminata nell'organizzazione. Ad esempio, questa potrebbe essere la data in cui l'utente ha dato la propria comunicazione sull'uscita dall'organizzazione. Questa data può essere diversa dalla data dell'ultimo giorno di lavoro dell'utente. Utilizzare il formato di data seguente: `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` , ovvero il [formato di data e ora ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html).|
| **LastWorkingDate** | Specifica l'ultimo giorno di lavoro per l'utente terminato. Utilizzare il formato di data seguente: `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` , ovvero il [formato di data e ora ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html).|
|||

### <a name="csv-file-for-job-level-changes-data"></a>File CSV per i dati delle modifiche a livello di processo

Di seguito è riportato un esempio di file CSV per i dati relativi alle modifiche a livello di processo.

```text
EmailAddress,EffectiveDate,OldLevel,NewLevel
sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,Level 61 – Sr. Manager,Level 60- Manager
pillar@contoso.com,2019-04-23T15:18:02.4675041+05:30,Level 62 – Director,Level 60- Sr. Manager
```

Nella tabella seguente vengono descritte tutte le colonne del file CSV per i dati relativi alle modifiche a livello di processo.

| **Colonna**|**Descrizione**|
|:--------- |:------------- |
| **EmailAddress**  | Specifica l'indirizzo di posta elettronica (UPN) dell'utente.|
| **EffectiveDate** | Specifica la data in cui il livello di lavoro dell'utente è stato cambiato ufficialmente. Utilizzare il formato di data seguente: `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` , ovvero il [formato di data e ora ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html).|
| **Osservazioni**| Specifica le osservazioni fornite dall'analizzatore per la modifica del livello di processo. È possibile immettere un limite di 200 caratteri. Questo parametro è facoltativo. Non è necessario includerlo nel file CSV.|
| **OldLevel**| Specifica il livello di lavoro dell'utente prima che sia stato modificato. Si tratta di un parametro di testo libero che può contenere la tassonomia gerarchica per l'organizzazione. Questo parametro è facoltativo. Non è necessario includerlo nel file CSV.|
| **NewLevel**| Specifica il livello di lavoro dell'utente dopo che è stato modificato. Si tratta di un parametro di testo libero che può contenere la tassonomia gerarchica per l'organizzazione. Questo parametro è facoltativo. Non è necessario includerlo nel file CSV.|
|||

### <a name="csv-file-for-performance-review-data"></a>File CSV per i dati di revisione delle prestazioni

Di seguito è riportato un esempio di file CSV per i dati sulle prestazioni.

```text
EmailAddress,EffectiveDate,Remarks,Rating
sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,Met expectations but bad attitude,2-Below expectation
pillar@contoso.com,2019-04-23T15:18:02.4675041+05:30, Multiple conflicts with the team
```

Nella tabella seguente vengono descritte tutte le colonne del file CSV per i dati di revisione delle prestazioni.

| **Colonna**|**Descrizione**|
|:----------|:--------------|
| **EmailAddress**  | Specifica l'indirizzo di posta elettronica (UPN) dell'utente.|
| **EffectiveDate** | Specifica la data in cui l'utente è stato informato ufficialmente del risultato della revisione delle prestazioni. Questa può essere la data in cui è stato terminato il ciclo di revisione delle prestazioni. Utilizzare il formato di data seguente: `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` , ovvero il [formato di data e ora ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html).|
| **Osservazioni**| Specifica gli eventuali commenti forniti dall'analizzatore all'utente per la revisione delle prestazioni. Si tratta di un parametro di testo con un limite di 200 caratteri. Questo parametro è facoltativo. Non è necessario includerlo nel file CSV.|
| **Valutazione**| Specifica la classificazione fornita per la revisione delle prestazioni. Si tratta di un parametro di testo che può contenere qualsiasi testo in formato libero utilizzato dall'organizzazione per riconoscere la valutazione. Ad esempio, "3 attese soddisfatte" o "2 al di sotto della media". Si tratta di un parametro di testo con un limite di 25 caratteri. Questo parametro è facoltativo. Non è necessario includerlo nel file CSV.|
|||

### <a name="csv-file-for-performance-improvement-plan-data"></a>File CSV per i dati del piano per il miglioramento delle prestazioni

Di seguito è riportato un esempio di file CSV per i dati relativi ai dati del piano per il miglioramento delle prestazioni.

```text
EmailAddress,EffectiveDate,ImprovementRemarks,PerformanceRating
sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,Met expectation but bad attitude,2-Below expectation
pillar@contoso.com,2019-04-23T15:18:02.4675041+05:30, Multiple conflicts with the team
```

Nella tabella seguente vengono descritte tutte le colonne del file CSV per i dati di revisione delle prestazioni.

| **Colonna**| **Descrizione**|
|:----------|:---------------|
| **EmailAddress**  | Specifica l'indirizzo di posta elettronica (UPN) dell'utente.|
| **EffectiveDate** | Specifica la data in cui l'utente è stato informato ufficialmente del piano per il miglioramento delle prestazioni. È necessario utilizzare il formato di data seguente: `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` , ovvero il [formato di data e ora ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html).|
| **Osservazioni**| Specifica eventuali osservazioni fornite dal valutatore in merito al piano di miglioramento delle prestazioni. Si tratta di un parametro di testo con un limite di 200 caratteri. Si tratta di un parametro facoltativo. Non è necessario includerlo nel file CSV. |
| **Valutazione**| Specifica qualsiasi classificazione o altre informazioni relative alla verifica delle prestazioni. piano per il miglioramento delle prestazioni. Si tratta di un parametro di testo che può contenere il testo di un modulo libero utilizzato dall'organizzazione per riconoscere la valutazione. Ad esempio, "3 attese soddisfatte" o "2 al di sotto della media". Si tratta di un parametro di testo con un limite di 25 caratteri. Si tratta di un parametro facoltativo. Non è necessario includerlo nel file CSV.|
|||

### <a name="determining-how-many-csv-files-to-use-for-hr-data"></a>Determinare il numero di file CSV da utilizzare per i dati HR

Nel passaggio 3, è possibile scegliere di creare connettori separati per ogni tipo di dati HR oppure è possibile scegliere di creare un singolo connettore per tutti i tipi di dati. È possibile utilizzare file CSV separati che contengono dati per uno scenario HR (come gli esempi dei file CSV descritti nelle sezioni precedenti). In alternativa, è possibile utilizzare un singolo file CSV contenente i dati per due o più scenari HR. Di seguito sono riportate alcune linee guida che consentono di determinare il numero di file CSV da utilizzare per i dati HR.

- Se i criteri di gestione dei rischi Insider che si desidera implementare richiedono più tipi di dati HR, prendere in considerazione l'utilizzo di un singolo file CSV che contenga tutti i tipi di dati necessari.

- Il metodo per la generazione o la raccolta dei dati HR può determinare il numero di file CSV. Ad esempio, se i diversi tipi di dati HR utilizzati per configurare un connettore HR sono situati in un singolo sistema HR nell'organizzazione, è possibile esportare i dati in un singolo file CSV. Tuttavia, se i dati vengono distribuiti su sistemi HR diversi, potrebbe essere più facile esportare i dati in file CSV diversi. Ad esempio, i dati di dimissioni dei dipendenti possono trovarsi in un sistema HR diverso rispetto ai dati di valutazione del livello di lavoro o delle prestazioni. In questo caso, potrebbe essere più facile avere file CSV separati anziché dover combinare manualmente i dati in un singolo file CSV. In questo modo, la modalità di recupero o esportazione dei dati dai sistemi HR può determinare il numero di file CSV necessari.

- Come regola generale, il numero di connettori HR che è necessario creare è determinato dai tipi di dati in un file CSV. Ad esempio, se un file CSV contiene tutti i tipi di dati necessari per supportare l'implementazione di gestione dei rischi Insider, è necessario un solo connettore HR. Tuttavia, se si dispone di due file CSV separati che contengono un singolo tipo di dati, è necessario creare due connettori HR. Un'eccezione a questo è che se si aggiunge una colonna di **HRScenario** a un file CSV (vedere la sezione successiva), è possibile configurare un singolo connettore HR in grado di elaborare diversi file CSV.

### <a name="configuring-a-single-csv-file-for-multiple-hr-data-types"></a>Configurazione di un singolo file CSV per più tipi di dati HR

È possibile aggiungere più tipi di dati HR a un singolo file CSV. Ciò è utile se la soluzione di gestione dei rischi Insider che si sta implementando richiede più tipi di dati HR o se i tipi di dati si trovano in un singolo sistema HR nell'organizzazione. L'utilizzo di meno file CSV consente sempre di disporre di un numero di connettori HR inferiore per la creazione e la gestione.

Di seguito sono elencati i requisiti per la configurazione di un file CSV con più tipi di dati:

- Per ogni tipo di dati e il nome della colonna corrispondente nella riga di intestazione, è necessario aggiungere le colonne necessarie (e facoltative se vengono utilizzate). Se un tipo di dati non corrisponde a una colonna, è possibile lasciare il valore vuoto.

- Per utilizzare un file CSV con più tipi di dati HR, il connettore HR deve sapere quali righe del file CSV contengono i dati di tipo HR. Questa operazione viene eseguita aggiungendo una colonna **HRScenario** aggiuntiva al file CSV. I valori di questa colonna identificano il tipo di dati HR in ogni riga. Ad esempio, i valori che corrispondono ai quattro scenari HR potrebbero essere le \` dimissioni \` , la modifica del livello di \` lavoro, la \` \` revisione delle prestazioni \` e il piano di \` miglioramento delle prestazioni \` .

- Se si dispone di più file CSV che contengono una colonna HRScenario * *, assicurarsi che ogni file utilizzi lo stesso nome di colonna e gli stessi valori che identificano gli scenari HR specifici.

Nell'esempio seguente viene illustrato un file CSV che contiene la colonna **HRScenario** . I valori nella colonna HRScenario identificano il tipo di dati nella riga corrispondente.

```text
HRScenario,EmailAddress,ResignationDate,LastWorkingDate,EffectiveDate,Remarks,Rating,OldLevel,NewLevel
Resignation,sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,2019-04-29T15:18:02.4675041+05:30,,,,
Resignation,pilarp@contoso.com,2019-04-24T09:15:49Z,2019-04-29T15:18:02.7117540,,,,
Job level change,sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,,,,,Level 61 Sr. Manager, Level 60 Manager
Job level change,pillarp@contoso.com,2019-04-23T15:18:02.4675041+05:30,,,,,Level 62 Director,Level 60 Sr Manager
Performance review,sarad@contoso.com,,,2019-04-23T15:18:02.4675041+05:30,Met expectation but bad attitude,2 Below expectations,,
Performance review,pillarp@contoso.com,,,2019-04-23T15:18:02.4675041+05:30, Multiple conflicts with the team,,
Performance improvement plan,sarad@contoso.com,,,2019-04-23T15:18:02.4675041+05:30,Met expectations but bad attitude,2 Below expectations,,
Performance improvement plan,pillarp@contoso.com,,,2019-04-23T15:18:02.4675041+05:30,Multiple conflicts with the team,,
```

> [!NOTE]
> È possibile utilizzare qualsiasi nome per la colonna che identifica il tipo di dati HR perché si eseguirà il mapping del nome della colonna nel file CSV come colonna che identifica il tipo di dati HR quando si configura il connettore nel passaggio 3. Quando si configura il connettore, verranno mappati anche i valori utilizzati per la colonna tipo di dati.

### <a name="adding-the-hrscenario-column-to-a-csv-file-that-contains-a-single-data-type"></a>Aggiunta della colonna HRScenario a un file CSV che contiene un singolo tipo di dati

In base ai sistemi HR dell'organizzazione e alla modalità di esportazione dei dati HR in un file CSV, potrebbe essere necessario creare più file CSV che contengono un singolo tipo di dati HR. In questo caso, è comunque possibile creare un singolo connettore HR per importare i dati da diversi file CSV. A tale scopo, è sufficiente aggiungere una colonna HRScenario al file CSV e specificare il tipo di dati HR. È quindi possibile eseguire lo script per ogni file CSV, ma utilizzare lo stesso ID processo per il connettore. Vedere il [passaggio 4](#step-4-run-the-sample-script-to-upload-your-hr-data).

## <a name="step-2-create-an-app-in-azure-active-directory"></a>Passaggio 2: creare un'app in Azure Active Directory

Il passaggio successivo consiste nel creare e registrare una nuova app in Azure Active Directory (Azure AD). L'app corrisponderà al connettore HR creato nel passaggio 3. La creazione di questa app consentirà ad Azure AD di autenticare il connettore HR quando viene eseguito e tenta di accedere all'organizzazione. Questa app verrà utilizzata anche per autenticare lo script eseguito nel passaggio 4 per caricare i dati HR nel cloud Microsoft. Durante la creazione di questa applicazione Azure AD, assicurarsi di salvare le informazioni seguenti. Questi valori verranno utilizzati nel passaggio 3 e nel passaggio 4.

- ID applicazione Azure AD (denominato anche ID *app* o *ID client*)

- Segreto dell'applicazione Azure AD (denominato anche *segreto client*)

- ID tenant (denominato anche *ID directory*)

Per istruzioni dettagliate per la creazione di un'app in Azure AD, vedere registrazione di [un'applicazione con la piattaforma Microsoft Identity](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).

## <a name="step-3-create-the-hr-connector"></a>Passaggio 3: creare il connettore HR

Il passaggio successivo consiste nel creare un connettore HR nel centro conformità di Microsoft 365. Dopo aver eseguito lo script nel passaggio 4, il connettore HR creato inventerà i dati HR dal file CSV all'organizzazione Microsoft 365. Prima di creare un connettore, verificare di disporre di un elenco degli scenari HR e dei nomi di colonna CSV corrispondenti per ognuno di essi. È necessario eseguire il mapping dei dati necessari per ogni scenario ai nomi di colonna effettivi nel file CSV durante la configurazione del connettore. In alternativa, è possibile caricare un file CSV di esempio durante la configurazione del connettore e la procedura guidata consentirà di mappare il nome delle colonne ai tipi di dati necessari.

Dopo aver completato questo passaggio, assicurarsi di copiare l'ID processo generato quando si crea il connettore. Quando si esegue lo script, si utilizzerà l'ID del processo.

1. Andare a [https://compliance.microsoft.com](https://compliance.microsoft.com/) e quindi fare clic su **connettori dati** nel NAV sinistro.

2. Nella pagina **connettori dati (anteprima)** in **HR**, fare clic su **Visualizza**.

3. Nella pagina **personale HR** , fare clic su **Aggiungi connettore**.

4. Nella pagina **installazione della connessione** eseguire le operazioni seguenti e quindi fare clic su **Avanti**:

   a. Digitare o incollare l'ID dell'applicazione Azure AD per l'app di Azure creata al passaggio 2.

   b. Digitare un nome per il connettore HR.

5. Nella pagina scenari HR selezionare uno o più scenari HR di cui si desidera importare i dati e quindi fare clic su **Avanti**.

6. Nella pagina Metodo di mapping dei file selezionare una delle opzioni seguenti e quindi fare clic su **Avanti**.

   - **Caricare un file di esempio**. Se si seleziona questa opzione, fare clic su **Carica file di esempio** per caricare il file CSV preparato nel passaggio 1. Questa opzione consente di selezionare rapidamente i nomi di colonna nel file CSV da un elenco a discesa per mapparli ai tipi di dati per gli scenari HR precedentemente selezionati.

   OPPURE

   - **Fornire manualmente i dettagli di mapping**. Se si seleziona questa opzione, è necessario digitare il nome delle colonne del file CSV per mapparle ai tipi di dati per gli scenari HR precedentemente selezionati.

7. Nella pagina Dettagli mapping dei file eseguire una delle operazioni seguenti, a seconda che sia stato caricato un file CSV di esempio e che si stia configurando il connettore per un singolo scenario HR o per più scenari. Se è stato caricato un file di esempio, non è necessario digitare i nomi delle colonne. È possibile selezionarli da un elenco a discesa.

    - Se nel passaggio precedente è stato selezionato un singolo scenario HR, digitare i nomi delle intestazioni di colonna (denominati anche *parametri*) dal file CSV creato nel passaggio 1 in ognuna delle caselle appropriate. I nomi di colonna digitati non sono con distinzione tra maiuscole e minuscole, ma assicurarsi di includere spazi se i nomi delle colonne nel file CSV includono spazi. Come spiegato in precedenza, i nomi digitati in queste caselle devono corrispondere ai nomi dei parametri nel file CSV. Nella schermata seguente, ad esempio, vengono visualizzati i nomi dei parametri del file CSV di esempio per lo scenario di dimissioni HR del dipendente illustrato nel passaggio 1.

    - Se nel passaggio precedente sono stati selezionati più tipi di dati, è necessario immettere il nome della colonna identificatore che identificherà il tipo di dati HR nel file CSV. Dopo aver immesso il nome della colonna identificatore, digitare il valore che identifica questo tipo di dati HR e digitare i nomi delle intestazioni di colonna per i tipi di dati selezionati dal file CSV creato nel passaggio 1 in ognuna delle caselle appropriate per ogni tipo di dati selezionato. Come spiegato in precedenza, i nomi digitati in queste caselle devono corrispondere ai nomi delle colonne del file CSV.

8. Nella pagina **Revisione** rivedere le impostazioni e quindi fare clic su **fine** per creare il connettore.

   Viene visualizzata una pagina di stato che conferma che il connettore è stato creato. Questa pagina contiene due elementi importanti che è necessario completare il passaggio successivo per eseguire lo script di esempio per caricare i dati HR.

   ![Pagina Revisione con ID processo e collegamento a GitHub per lo script di esempio](../media/HRConnector_Confirmation.png)

   a. **ID processo.** Questo ID processo è necessario per eseguire lo script nel passaggio successivo. È possibile copiarlo da questa pagina o dalla pagina del riquadro a comparsa del connettore.

   b. **Collegamento a uno script di esempio.** Fare clic sul collegamento **qui** per passare al sito GitHub per accedere allo script di esempio (il collegamento apre una nuova finestra). Tenere aperta la finestra in modo che sia possibile copiare lo script nel passaggio 4. In alternativa, è possibile aggiungere un segnalibro alla destinazione o copiare l'URL in modo che sia possibile accedervi di nuovo quando si esegue lo script. Questo collegamento è disponibile anche nella pagina del riquadro a comparsa del connettore.

9. Fare clic su **Fine**.

   Il nuovo connettore viene visualizzato nell'elenco della scheda **connettori** .

10. Fare clic sul connettore HR appena creato per visualizzare la pagina del riquadro a comparsa, che contiene le proprietà e altre informazioni sul connettore.

   ![Pagina a comparsa per il nuovo connettore HR](../media/HRConnectorWizard7.png)

Se non è stato ancora fatto, è possibile copiare i valori per l'ID dell' **app di Azure** e il **processo di connettore**. Sarà necessario eseguire lo script nel passaggio successivo. È inoltre possibile scaricare lo script dalla pagina del riquadro a comparsa o scaricarlo utilizzando il collegamento nel passaggio successivo.

È inoltre possibile fare clic su **modifica** per modificare l'ID dell'app di Azure o i nomi delle intestazioni di colonna definiti nella pagina **mapping dei file** .

## <a name="step-4-run-the-sample-script-to-upload-your-hr-data"></a>Passaggio 4: eseguire lo script di esempio per caricare i dati HR

L'ultimo passaggio per la configurazione di un connettore HR è l'esecuzione di uno script di esempio che caricherà i dati HR nel file CSV (creato nel passaggio 1) nel cloud Microsoft. Nello specifico, lo script carica i dati nel connettore HR. Dopo aver eseguito lo script, il connettore HR creato nel passaggio 3 importa i dati HR nell'organizzazione Microsoft 365, in cui è possibile accedervi da altri strumenti di conformità, ad esempio la soluzione di gestione dei rischi Insider. Dopo aver eseguito lo script, prendere in considerazione la pianificazione di un'attività per l'esecuzione automatica su base giornaliera in modo che i dati di terminazione dei dipendenti più recenti vengano caricati nel cloud Microsoft. Vedere [pianificare lo script in modo che venga eseguito automaticamente](#optional-step-6-schedule-the-script-to-run-automatically).

1. Passare alla finestra che è stata lasciata aperta dal passaggio precedente per accedere al sito GitHub con lo script di esempio. In alternativa, aprire il sito con segnalibro o utilizzare l'URL copiato.

2. Fare clic sul pulsante **RAW** per visualizzare lo script nella visualizzazione testo.

3. Copiare tutte le righe nello script di esempio e quindi salvarle in un file di testo.

4. Modificare lo script di esempio per l'organizzazione, se necessario.

5. Salvare il file di testo come file di script di Windows PowerShell utilizzando un suffisso del nome di file `.ps1` , ad esempio, `HRConnector.ps1` .

6. Aprire un prompt dei comandi nel computer locale e passare alla directory in cui è stato salvato lo script.

7. Eseguire il seguente comando per caricare i dati HR nel file CSV nel cloud Microsoft. Per esempio:

    ```powershell
    .\HRConnector.ps1 -tenantId <tenantId> -appId <appId>  -appSecret <appSecret>  -jobId <jobId>  -csvFilePath '<csvFilePath>'
    ```

   Nella tabella seguente vengono descritti i parametri da utilizzare con questo script e i valori necessari. Le informazioni ottenute nei passaggi precedenti vengono utilizzate nei valori di questi parametri.

   |**Parametro**|**Descrizione**
   |:-----|:-----|:-----|
   |`tenantId`|Questo è l'ID dell'organizzazione Microsoft 365 ottenuta al passaggio 2. È anche possibile ottenere l'ID tenant per l'organizzazione nel pannello **Panoramica** nell'interfaccia di amministrazione di Azure ad. Viene utilizzato per identificare l'organizzazione.|
   |`appId` |Questo è l'ID dell'applicazione Azure AD per l'app creata in Azure AD nel passaggio 2. Questo metodo viene utilizzato da Azure AD per l'autenticazione quando lo script tenta di accedere all'organizzazione Microsoft 365. | 
   |`appSecret`|Questo è il segreto dell'applicazione Azure AD per l'app creata in Azure AD nel passaggio 2. Questo utilizzato anche per l'autenticazione.|
   |`jobId`|Questo è l'ID processo per il connettore HR creato nel passaggio 3. Viene utilizzato per associare i dati HR caricati nel cloud Microsoft con il connettore HR.|
   |`csvFilePath`|Si tratta del percorso del file CSV, memorizzato nello stesso sistema dello script, creato nel passaggio 1. Provare ad evitare gli spazi nel percorso del file; in caso contrario, utilizzare virgolette singole.|
   |||

   Di seguito è riportato un esempio della sintassi per lo script del connettore HR utilizzando i valori effettivi per ogni parametro:

   ```powershell
    .\HRConnector.ps1 -tenantId d5723623-11cf-4e2e-b5a5-01d1506273g9 -appId 29ee526e-f9a7-4e98-a682-67f41bfd643e -appSecret MNubVGbcQDkGCnn -jobId b8be4a7d-e338-43eb-a69e-c513cd458eba -csvFilePath 'C:\Users\contosoadmin\Desktop\Data\employee_termination_data.csv'
    ```

   Se il caricamento ha esito positivo, lo script Visualizza il messaggio di **caricamento con esito positivo** .

   > [!NOTE]
   > In caso di problemi durante l'esecuzione del comando precedente a causa dei criteri di esecuzione, vedere [informazioni sui criteri di esecuzione](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies) e [Set-ExecutionPolicy](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy) per indicazioni sull'impostazione dei criteri di esecuzione.

## <a name="step-5-monitor-the-hr-connector"></a>Passaggio 5: monitorare il connettore HR

Dopo aver creato il connettore HR ed eseguito lo script per caricare i dati HR, è possibile visualizzare lo stato del connettore e del caricamento nel centro conformità di Microsoft 365. Se si pianifica lo script in modo che venga eseguito automaticamente periodicamente, è possibile visualizzare lo stato corrente anche dopo l'ultima esecuzione dello script.

1. Andare a [https://compliance.microsoft.com](https://compliance.microsoft.com) e fare clic su **connettori dati** nel NAV sinistro.

2. Fare clic sulla scheda **connettori** e quindi selezionare il connettore HR per visualizzare la pagina del riquadro a comparsa, che contiene le proprietà e le informazioni sul connettore.

   ![Pagina del riquadro a comparsa del connettore HR con proprietà e stato](../media/HRConnectorFlyout1.png)

3. In **stato di avanzamento**fare clic sul collegamento **accedi al registro** per aprire o salvare il registro di stato del connettore. Questo log contiene informazioni su ogni volta che lo script viene eseguito e carica i dati dal file CSV al cloud Microsoft. 

   ![Il file di registro del connettore HR Visualizza le righe di numero da file CSV caricati](../media/HRConnectorLogFile.png)

   Il `RecordsSaved` campo indica il numero di righe nel file CSV che è stato caricato. Ad esempio, se il file CSV contiene quattro righe, il valore dei `RecordsSaved` campi è 4, se lo script ha correttamente caricato tutte le righe nel file CSV.

Se non è stato eseguito lo script nel passaggio 4, viene visualizzato un collegamento per scaricare lo script nell' **Ultima importazione**. È possibile scaricare lo script e quindi seguire la procedura per eseguire lo script.

## <a name="optional-step-6-schedule-the-script-to-run-automatically"></a>Optional Passaggio 6: pianificare l'esecuzione automatica dello script

Per assicurarsi che i dati HR più recenti dell'organizzazione siano disponibili per gli strumenti come la soluzione di gestione dei rischi Insider, si consiglia di pianificare lo script in modo che venga eseguito automaticamente su base ricorrente, ad esempio una volta al giorno. Questo richiede anche l'aggiornamento dei dati HR nel file CSV su una pianificazione analoga (se non uguale), in modo che contenga le informazioni più aggiornate sui dipendenti che lasciano l'organizzazione. L'obiettivo è quello di caricare i dati HR più aggiornati in modo che il connettore HR possa renderlo disponibile per la soluzione di gestione dei rischi Insider.

È possibile utilizzare l'app utilità di pianificazione in Windows per eseguire automaticamente lo script ogni giorno.

1. Nel computer locale, fare clic sul pulsante **Start** di Windows e quindi digitare **utilità di pianificazione**.

2. Fare clic sull'app **utilità di pianificazione** per aprirla.

3. Nella sezione **azioni** fare clic su **Crea attività**.

4. Nella scheda **generale** Digitare un nome descrittivo per l'attività pianificata. ad esempio, **lo script del connettore HR**. È inoltre possibile aggiungere una descrizione facoltativa.

5. In **Opzioni di sicurezza**eseguire le operazioni seguenti:

   a. Determinare se eseguire lo script solo quando si è connessi al computer o quando si è connessi o meno.

   b. Verificare che sia selezionata la casella **di controllo Esegui con i privilegi più alti** .

6. Selezionare la scheda **trigger** , fare clic su **nuovo**e quindi eseguire le operazioni seguenti:

   a. In **Impostazioni**, selezionare l'opzione **giornaliero** e quindi scegliere una data e un'ora per l'esecuzione dello script per la prima volta. Lo script viene applicato ogni giorno allo stesso tempo specificato.

   b. In **Impostazioni avanzate**verificare che sia selezionata la casella di controllo **abilitata** .

   c. Fare clic su **OK**.

7. Selezionare la scheda **azioni** , fare clic su **nuovo**e quindi eseguire le operazioni seguenti:

   ![Impostazioni azione per creare una nuova attività pianificata per lo script del connettore HR](../media/HRConnectorScheduleTask1.png)

   a. Nell'elenco a discesa **azione** , verificare che sia selezionata l'opzione **avvia un programma** .

   b. Nella casella **programma/script** fare clic su **Sfoglia**e passare al percorso seguente e selezionarlo in modo che il percorso venga visualizzato nella casella: `C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe` .

   c. Nella casella **Add arguments (optional)** incollare lo stesso comando script eseguito nel passaggio 4. Per esempio `.\HRConnector.ps1 -tenantId "d5723623-11cf-4e2e-b5a5-01d1506273g9" -appId "c12823b7-b55a-4989-faba-02de41bb97c3" -appSecret "MNubVGbcQDkGCnn"  -jobId "e081f4f4-3831-48d6-7bb3-fcfab1581458" -csvFilePath "C:\Users\contosoadmin\Desktop\Data\employee_termination_data.csv"`

   d. Nella casella **inizia in (facoltativo)** incollare il percorso della cartella dello script eseguito nel passaggio 4. Ad esempio, `C:\Users\contosoadmin\Desktop\Scripts`.

   e. Fare clic su **OK** per salvare le impostazioni per la nuova azione.

8. Nella finestra **Crea attività** fare clic su **OK** per salvare l'attività pianificata. Potrebbe essere richiesto di immettere le credenziali dell'account utente.

   La nuova attività viene visualizzata nella libreria dell'utilità di pianificazione.

   ![La nuova attività viene visualizzata nella raccolta di utilità di pianificazione](../media/HRConnectorTaskSchedulerLibrary.png)

   L'ultima volta che lo script è stato eseguito e la volta successiva che viene pianificata l'esecuzione viene visualizzata. È possibile fare doppio clic sull'attività per modificarla.

   È inoltre possibile verificare l'ultima volta che lo script è stato eseguito nella pagina a comparsa del connettore HR corrispondente nel centro conformità.

## <a name="existing-hr-connectors"></a>Connettori HR esistenti

Il 20 luglio 2020, sono stati rilasciati ulteriori scenari che sono supportati dai connettori HR. Si tratta degli scenari HR descritti in precedenza in questo articolo. Qualsiasi connettore HR creato prima di questa data supporta solo lo scenario di dimissioni dei dipendenti. Se è stato creato un connettore HR prima del 20 luglio 2020, è stata eseguita la migrazione in modo che continui a eseguire la migrazione dei dati HR nel cloud Microsoft. Non è necessario eseguire alcuna operazione per mantenere questa funzionalità. È possibile continuare a utilizzare il connettore senza interruzioni.

Se si desidera implementare ulteriori scenari HR, creare un nuovo connettore HR e configurarlo per gli scenari HR aggiuntivi che sono stati rilasciati. È inoltre necessario creare uno o più nuovi file CSV che contengono i dati per supportare gli scenari HR aggiuntivi. Dopo aver creato un nuovo connettore HR, eseguire lo script utilizzando l'ID processo del nuovo connettore e dei file CSV con i dati per gli scenari HR aggiuntivi.
