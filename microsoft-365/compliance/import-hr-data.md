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
description: Gli amministratori possono configurare un connettore dati per importare i dati dei dipendenti dal sistema delle risorse umane dell'organizzazione in Microsoft 365. In questo modo è possibile utilizzare i dati sulle risorse umane nei criteri di gestione dei rischi Insider per rilevare attività di utenti specifici che potrebbero rappresentare una minaccia interna per l'organizzazione.
ms.openlocfilehash: 756851b848822fa801493b2832368ccb2a1a0b51
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620242"
---
# <a name="set-up-a-connector-to-import-hr-data"></a>Configurare un connettore per importare i dati sulle risorse umane

È possibile configurare un connettore di dati nel Centro conformità Microsoft 365 per importare i dati delle risorse umane (HR) relativi a eventi quali lemissioni di un utente o una modifica del livello di lavoro di un utente. I dati delle risorse umane possono quindi essere utilizzati dalla soluzione di gestione dei rischi [Insider](insider-risk-management.md) per generare indicatori di rischio che consentono di identità di possibili attività dannose o furti di dati da parte di utenti all'interno dell'organizzazione.

La configurazione di un connettore per i dati sulle risorse umane che i criteri di gestione dei rischi Insider possono utilizzare per generare indicatori di rischio consiste nella creazione di un file CSV contenente i dati sulle risorse umane, nella creazione di un'app in Azure Active Directory usata per l'autenticazione, nella creazione di un connettore di dati sulle risorse umane nel Centro conformità Microsoft 365 e nell'esecuzione di uno script (su base pianificata) che inserisce i dati delle risorse umane nei file CSV nel cloud Microsoft in modo che sia disponibile per insider soluzione di gestione dei rischi.

## <a name="before-you-begin"></a>Prima di iniziare

- Determinare quali scenari hr e dati importare in Microsoft 365. In questo modo sarà possibile determinare il numero di file CSV e connettori hr da creare e come generare e strutturare i file CSV. I dati delle risorse umane che si importano sono determinati dai criteri di gestione dei rischi Insider che si desidera implementare. Per ulteriori informazioni, vedere il passaggio 1.

- Determinare come recuperare o esportare i dati dal sistema delle risorse umane dell'organizzazione (e su base regolare) e aggiungerli ai file CSV creati nel passaggio 1. Lo script eseguito nel passaggio 4 carica i dati delle risorse umane nei file CSV nel cloud Microsoft.

- All'utente che crea il connettore hr nel passaggio 3 deve essere assegnato il ruolo di importazione/esportazione delle cassette postali in Exchange Online. Per impostazione predefinita, questo ruolo non è assegnato ad alcun gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo di importazione/esportazione delle cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In or you can create a new role group, assign the Mailbox Import Export role, and then add the appropriate users as members. Per ulteriori informazioni, vedere le sezioni [Creazione](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) di gruppi di ruoli o Modifica gruppi [di](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) ruoli nell'articolo "Gestire i gruppi di ruoli in Exchange Online".

- Lo script di esempio eseguito nel passaggio 4 consente di caricare i dati delle risorse umane nel cloud Microsoft in modo che possano essere utilizzati dalla soluzione di gestione dei rischi Insider. Questo script di esempio non è supportato in alcun servizio o programma di supporto standard Microsoft. Lo script di esempio è fornito così come è senza alcun tipo di garanzia. Microsoft esclude inoltre qualsiasi garanzia implicita, tra cui, senza limitazioni, tutte le garanzie implicite di commerciabilità o idoneità per uno scopo specifico. L'utente assume tutti i rischi associati all'uso o alle prestazioni dello script di esempio e della documentazione. In nessun caso Microsoft, i suoi autori o chiunque altro coinvolto nella creazione, produzione o consegna degli script è da ritenersi responsabile per qualsiasi danno eventuale (inclusi, senza limitazione alcuna, danni riguardanti profitti aziendali, interruzione di attività, perdita di informazioni aziendali o altra perdita pecuniaria) derivanti dall'utilizzo o dall'incapacità di utilizzo degli script di esempio e della documentazione, anche nel caso in cui Microsoft sia stata avvisata della possibilità di tali danni.

## <a name="step-1-prepare-a-csv-file-with-your-hr-data"></a>Passaggio 1: Preparare un file CSV con i dati delle risorse umane

Il primo passaggio consiste nel creare un file CSV contenente i dati delle risorse umane che il connettore importerà in Microsoft 365. Questi dati verranno utilizzati dalla soluzione di rischio Insider per generare potenziali indicatori di rischio. I dati per gli scenari hr seguenti possono essere importati in Microsoft 365:

- Le remissioni dei dipendenti. Informazioni sugli utenti che hanno lasciato l'organizzazione.

- Modifiche a livello di processo. Informazioni sulle modifiche a livello di processo per gli utenti, ad esempio promozioni e abbassamenti di livello.

- Revisioni delle prestazioni. Informazioni sulle prestazioni degli utenti.

- Piani di miglioramento delle prestazioni. Informazioni sui piani di miglioramento delle prestazioni per gli utenti.

Il tipo di dati sulle risorse umane da importare dipende dal criterio di gestione dei rischi Insider e dal modello di criteri corrispondente che si desidera implementare. Nella tabella seguente viene illustrato il tipo di dati HR necessario per ogni modello di criterio:

|  Modello di criteri |  Tipo di dati HR |
|:-----------------------------------------------|:---------------------------------------------------------------------|
| Furto di dati da parte degli utenti                   | Demissioni dei dipendenti                                                 |
| Perdite di dati generali                              | Non applicabile                                                        |
| Perdite di dati per utenti con priorità                    | Non applicabile                                                        |
| Perdite di dati da parte di utenti scontenti                 | Modifiche a livello di processo, revisioni delle prestazioni, piani di miglioramento delle prestazioni |
| Violazioni generali dei criteri di sicurezza              | Non applicabile                                                        |
| Violazioni dei criteri di sicurezza da parte degli utenti   | Demissioni dei dipendenti                                                 |
| Violazioni dei criteri di sicurezza da parte degli utenti con priorità    | Non applicabile                                                        |
| Violazioni dei criteri di sicurezza da parte di utenti scontenti | Modifiche a livello di processo, revisioni delle prestazioni, piani di miglioramento delle prestazioni |
| Linguaggio offensivo nella posta elettronica                     | Non applicabile                                                        |

Per ulteriori informazioni sui modelli di criteri per la gestione dei rischi Insider, vedere [Criteri di gestione dei rischi Insider.](insider-risk-management-policies.md#policy-templates)

Per ogni scenario di risorse umane, è necessario fornire i dati sulle risorse umane corrispondenti in uno o più file CSV. Il numero di file CSV da usare per l'implementazione della gestione dei rischi Insider è illustrato più avanti in questa sezione.

Dopo aver creato il file CSV con i dati sulle risorse umane necessari, archiviarlo nel computer locale in cui si esegue lo script nel passaggio 4. È inoltre consigliabile implementare una strategia di aggiornamento per assicurarsi che il file CSV contenga sempre le informazioni più aggiornate in modo che, indipendentemente dall'esecuzione dello script, i dati sulle risorse umane più aggiornati verranno caricati nel cloud Microsoft e accessibili per la soluzione di gestione dei rischi Insider.

> [!IMPORTANT]
> I nomi di colonna descritti nelle sezioni seguenti non sono parametri obbligatori, ma solo esempi. È possibile utilizzare qualsiasi nome di colonna nei file CSV. Tuttavia, i nomi di colonna utilizzati in un *file* CSV devono essere mappati al tipo di dati quando si crea il connettore risorse umane nel passaggio 3. Tieni inoltre presente che i file CSV di esempio nelle sezioni seguenti sono visualizzati nella visualizzazione NotePad. È molto più semplice visualizzare e modificare i file CSV in Microsoft Excel.

Nelle sezioni seguenti vengono descritti i dati CSV necessari per ogni scenario hr.

### <a name="csv-file-for-employee-resignation-data"></a>File CSV per i dati di dimissioni dei dipendenti

Ecco un esempio di file CSV per i dati di dimissioni dei dipendenti.

```text
EmailAddress,ResignationDate,LastWorkingDate
sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,2019-04-29T15:18:02.4675041+05:30
pilarp@contoso.com,2019-04-24T09:15:49Z,2019-04-29T15:18:02.7117540
```

Nella tabella seguente viene descritta ogni colonna del file CSV per i dati di rinuncia dei dipendenti.

|  Colonna   |   Descrizione |
|:------------|:----------------|
|**EmailAddress**| Specifica l'indirizzo di posta elettronica (UPN) dell'utente terminato.|
| **ResignationDate** | Specifica la data in cui l'impiego dell'utente è stato ufficialmente terminato nell'organizzazione. Ad esempio, questa potrebbe essere la data in cui l'utente ha dato l'avviso sull'uscita dall'organizzazione. Questa data può essere diversa dalla data dell'ultimo giorno di lavoro della persona. Utilizzare il formato di data seguente: , ovvero il formato di data e ora `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` [ISO 8601.](https://www.iso.org/iso-8601-date-and-time-format.html)|
| **LastWorkingDate** | Specifica l'ultimo giorno di lavoro per l'utente terminato. Utilizzare il formato di data seguente: , ovvero il formato di data e ora `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` [ISO 8601.](https://www.iso.org/iso-8601-date-and-time-format.html)|
|||

### <a name="csv-file-for-job-level-changes-data"></a>File CSV per i dati delle modifiche a livello di processo

Ecco un esempio di file CSV per i dati delle modifiche a livello di processo.

```text
EmailAddress,EffectiveDate,OldLevel,NewLevel
sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,Level 61 – Sr. Manager,Level 60- Manager
pillar@contoso.com,2019-04-23T15:18:02.4675041+05:30,Level 62 – Director,Level 60- Sr. Manager
```

Nella tabella seguente viene descritta ogni colonna del file CSV per i dati relativi alle modifiche a livello di processo.

|  Colonna | Descrizione |
|:--------- |:------------- |
| **EmailAddress**  | Specifica l'indirizzo di posta elettronica dell'utente (UPN).|
| **EffectiveDate** | Specifica la data in cui il livello di lavoro dell'utente è stato modificato ufficialmente. Utilizzare il formato di data seguente: , ovvero il formato di data e ora `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` [ISO 8601.](https://www.iso.org/iso-8601-date-and-time-format.html)|
| **Osservazioni**| Specifica le osservazioni fornite dall'analizzatore sulla modifica del livello del processo. È possibile immettere un limite di 200 caratteri. Questo parametro è facoltativo. Non è necessario includerlo nel file CSV.|
| **OldLevel**| Specifica il livello di lavoro dell'utente prima della modifica. Si tratta di un parametro di testo libero e può contenere tassonomia gerarchica per l'organizzazione. Questo parametro è facoltativo. Non è necessario includerlo nel file CSV.|
| **NewLevel**| Specifica il livello di lavoro dell'utente dopo la modifica. Si tratta di un parametro di testo libero e può contenere tassonomia gerarchica per l'organizzazione. Questo parametro è facoltativo. Non è necessario includerlo nel file CSV.|
|||

### <a name="csv-file-for-performance-review-data"></a>File CSV per i dati di revisione delle prestazioni

Ecco un esempio di file CSV per i dati sulle prestazioni.

```text
EmailAddress,EffectiveDate,Remarks,Rating
sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,Met expectations but bad attitude,2-Below expectation
pillar@contoso.com,2019-04-23T15:18:02.4675041+05:30, Multiple conflicts with the team
```

Nella tabella seguente viene descritta ogni colonna del file CSV per i dati di revisione delle prestazioni.

|  Colonna | Descrizione |
|:----------|:--------------|
| **EmailAddress**  | Specifica l'indirizzo di posta elettronica dell'utente (UPN).|
| **EffectiveDate** | Specifica la data in cui l'utente è stato ufficialmente informato del risultato della revisione delle prestazioni. Può essere la data di fine del ciclo di revisione delle prestazioni. Utilizzare il formato di data seguente: , ovvero il formato di data e ora `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` [ISO 8601.](https://www.iso.org/iso-8601-date-and-time-format.html)|
| **Osservazioni**| Specifica eventuali osservazioni fornite dall'analizzatore all'utente per la verifica delle prestazioni. Si tratta di un parametro di testo con un limite di 200 caratteri. Questo parametro è facoltativo. Non è necessario includerlo nel file CSV.|
| **Valutazione**| Specifica la valutazione fornita per la verifica delle prestazioni. Si tratta di un parametro di testo che può contenere qualsiasi testo in formato libero utilizzato dall'organizzazione per riconoscere la valutazione. Ad esempio, "3 Soddisfatte le aspettative" o "2 al di sotto della media". Si tratta di un parametro di testo con un limite di 25 caratteri. Questo parametro è facoltativo. Non è necessario includerlo nel file CSV.|
|||

### <a name="csv-file-for-performance-improvement-plan-data"></a>File CSV per i dati del piano di miglioramento delle prestazioni

Ecco un esempio di file CSV per i dati relativi ai dati del piano di miglioramento delle prestazioni.

```text
EmailAddress,EffectiveDate,ImprovementRemarks,PerformanceRating
sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,Met expectation but bad attitude,2-Below expectation
pillar@contoso.com,2019-04-23T15:18:02.4675041+05:30, Multiple conflicts with the team
```

Nella tabella seguente viene descritta ogni colonna del file CSV per i dati di revisione delle prestazioni.

|  Colonna |  Descrizione |
|:----------|:---------------|
| **EmailAddress**  | Specifica l'indirizzo di posta elettronica dell'utente (UPN).|
| **EffectiveDate** | Specifica la data in cui l'utente è stato ufficialmente informato del piano di miglioramento delle prestazioni. È necessario utilizzare il seguente formato di data: , ovvero il formato di data e ora `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` [ISO 8601.](https://www.iso.org/iso-8601-date-and-time-format.html)|
| **Osservazioni**| Specifica eventuali osservazioni fornite dall'analizzatore sul piano di miglioramento delle prestazioni. Si tratta di un parametro di testo con un limite di 200 caratteri. Questo è un parametro facoltativo. Non è necessario includerlo nel file CSV. |
| **Valutazione**| Specifica qualsiasi classificazione o altra informazione correlata alla revisione delle prestazioni. piano di miglioramento delle prestazioni. Si tratta di un parametro di testo che può contenere qualsiasi testo in formato libero utilizzato dall'organizzazione per riconoscere la valutazione. Ad esempio, "3 Soddisfatte le aspettative" o "2 al di sotto della media". Si tratta di un parametro di testo con un limite di 25 caratteri. Questo è un parametro facoltativo. Non è necessario includerlo nel file CSV.|
|||

### <a name="determining-how-many-csv-files-to-use-for-hr-data"></a>Determinazione del numero di file CSV da utilizzare per i dati delle risorse umane

Nel passaggio 3 è possibile scegliere di creare connettori separati per ogni tipo di dati HR oppure di creare un singolo connettore per tutti i tipi di dati. È possibile usare file CSV separati contenenti dati per uno scenario hr (come gli esempi dei file CSV descritti nelle sezioni precedenti). In alternativa, è possibile utilizzare un singolo file CSV contenente dati per due o più scenari di risorse umane. Ecco alcune linee guida per determinare il numero di file CSV da usare per i dati sulle risorse umane.

- Se il criterio di gestione dei rischi Insider che si desidera implementare richiede più tipi di dati HR, è consigliabile utilizzare un singolo file CSV contenente tutti i tipi di dati necessari.

- Il metodo per generare o raccogliere i dati delle risorse umane può determinare il numero di file CSV. Ad esempio, se i diversi tipi di dati delle risorse umane utilizzati per configurare un connettore hr si trovano in un unico sistema hr dell'organizzazione, è possibile esportare i dati in un singolo file CSV. Tuttavia, se i dati vengono distribuiti in sistemi HR diversi, potrebbe essere più semplice esportare i dati in file CSV diversi. Ad esempio, i dati sulle remissioni dei dipendenti possono trovarsi in un sistema di risorse umane diverso da quello a livello di lavoro o di revisione delle prestazioni. In questo caso, potrebbe essere più semplice avere file CSV separati invece di dover combinare manualmente i dati in un singolo file CSV. Pertanto, la modalità di recupero o esportazione dei dati dai sistemi HR può determinare il numero di file CSV necessari.

- Come regola generale, il numero di connettori HR che sarà necessario creare dipende dai tipi di dati in un file CSV. Ad esempio, se un file CSV contiene tutti i tipi di dati necessari per supportare l'implementazione della gestione dei rischi Insider, è necessario un solo connettore hr. Tuttavia, se si dispone di due file CSV separati che contengono ognuno un singolo tipo di dati, sarà necessario creare due connettori HR. Un'eccezione è che se si aggiunge una colonna **HRScenario** a un file CSV (vedere la sezione successiva), è possibile configurare un singolo connettore hr in grado di elaborare file CSV diversi.

### <a name="configuring-a-single-csv-file-for-multiple-hr-data-types"></a>Configurazione di un singolo file CSV per più tipi di dati HR

È possibile aggiungere più tipi di dati HR a un singolo file CSV. Ciò è utile se la soluzione di gestione dei rischi Insider che si sta implementando richiede più tipi di dati hr o se i tipi di dati si trovano in un unico sistema hr dell'organizzazione. La presenza di un numero inferiore di file CSV consente sempre di avere meno connettori hr da creare e gestire.

Ecco i requisiti per la configurazione di un file CSV con più tipi di dati:

- È necessario aggiungere le colonne obbligatorie (e facoltative se vengono utilizzate) per ogni tipo di dati e il nome di colonna corrispondente nella riga di intestazione. Se un tipo di dati non corrisponde a una colonna, è possibile lasciare vuoto il valore.

- Per utilizzare un file CSV con più tipi di dati delle risorse umane, il connettore HR deve sapere quali righe del file CSV contengono il tipo di dati delle risorse umane. Questa operazione viene eseguita aggiungendo un'ulteriore **colonna HRScenario** al file CSV. I valori in questa colonna identificano il tipo di dati delle risorse umane in ogni riga. Ad esempio, i valori che corrispondono ai quattro scenari relativi alle risorse umane possono essere Dimissioni, Modifica a livello di processo, Revisione delle prestazioni e \` Piano di miglioramento delle \` \` \` \` \` \` \` prestazioni.

- Se si dispone di più file CSV che contengono una colonna HRScenario**, assicurarsi che ogni file utilizzi lo stesso nome di colonna e gli stessi valori che identificano gli scenari hr specifici.

L'esempio seguente mostra un file CSV contenente la **colonna HRScenario.** I valori nella colonna HRScenario identificano il tipo di dati nella riga corrispondente.

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
> È possibile utilizzare qualsiasi nome per la colonna che identifichi il tipo di dati HR perché il nome della colonna nel file CSV verrà mappato come colonna che identifica il tipo di dati HR quando si configura il connettore nel passaggio 3. I valori utilizzati per la colonna del tipo di dati verranno mappati anche quando si configura il connettore.

### <a name="adding-the-hrscenario-column-to-a-csv-file-that-contains-a-single-data-type"></a>Aggiunta della colonna HRScenario a un file CSV contenente un singolo tipo di dati

In base ai sistemi HR dell'organizzazione e alla modalità di esportazione dei dati sulle risorse umane in file CSV, potrebbe essere necessario creare più file CSV contenenti un singolo tipo di dati hr. In questo caso, è comunque possibile creare un singolo connettore hr per importare dati da file CSV diversi. A tale scopo, è sufficiente aggiungere una colonna HRScenario al file CSV e specificare il tipo di dati HR. È quindi possibile eseguire lo script per ogni file CSV, ma utilizzare lo stesso ID processo per il connettore. Vedere [il passaggio 4.](#step-4-run-the-sample-script-to-upload-your-hr-data)

## <a name="step-2-create-an-app-in-azure-active-directory"></a>Passaggio 2: creare un'app in Azure Active Directory

Il passaggio successivo consiste nel creare e registrare una nuova app in Azure Active Directory (Azure AD). L'app corrisponderà al connettore hr creato nel passaggio 3. La creazione di questa app consentirà ad Azure AD di autenticare il connettore hr quando viene eseguito e tenterà di accedere all'organizzazione. Questa app verrà usata anche per autenticare lo script eseguito nel passaggio 4 per caricare i dati delle risorse umane nel cloud Microsoft. Durante la creazione di questa app Azure AD, assicurati di salvare le informazioni seguenti. Questi valori verranno utilizzati nei passaggi 3 e 4.

- ID applicazione Azure AD (detto anche *ID app* o *ID client)*

- Segreto dell'applicazione Azure AD (detto *anche segreto client)*

- ID tenant (denominato anche *ID directory)*

Per istruzioni dettagliate sulla creazione di un'app in Azure AD, vedi [Registrare un'applicazione con la piattaforma di identità Microsoft.](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app)

## <a name="step-3-create-the-hr-connector"></a>Passaggio 3: Creare il connettore risorse umane

Il passaggio successivo consiste nel creare un connettore hr nel Centro conformità Microsoft 365. Dopo aver eseguito lo script nel passaggio 4, il connettore hr creato ingestirà i dati delle risorse umane dal file CSV all'organizzazione di Microsoft 365. Prima di creare un connettore, assicurarsi di disporre di un elenco degli scenari hr e dei nomi delle colonne CSV corrispondenti per ognuno di essi. È necessario mappare i dati necessari per ogni scenario ai nomi di colonna effettivi nel file CSV durante la configurazione del connettore. In alternativa, è possibile caricare un file CSV di esempio durante la configurazione del connettore e la procedura guidata consente di mappare il nome delle colonne ai tipi di dati necessari.

Dopo aver completato questo passaggio, assicurarsi di copiare l'ID processo generato quando si crea il connettore. L'ID processo verrà utilizzato quando si esegue lo script.

1. Vai a [https://compliance.microsoft.com](https://compliance.microsoft.com/) e quindi fai clic su **Connettori dati** nel riquadro di spostamento sinistro.

2. Nella pagina **Connettori dati in** **RISORSE UMANE** fare clic su **Visualizza.**

3. Nella pagina **Hr Custom** fare clic su **Add connector.**

4. Nella pagina **Imposta la connessione** eseguire le operazioni seguenti e quindi fare clic su **Avanti:**

   1. Digitare o incollare l'ID applicazione Azure AD per l'app Azure creata nel passaggio 2.

   1. Digitare un nome per il connettore risorse umane.

5. Nella pagina Scenari hr selezionare uno o più scenari hr per cui si desidera importare i dati e quindi fare clic su **Avanti.**

6. Nella pagina del metodo di mapping dei file selezionare una delle opzioni seguenti e quindi fare clic su **Avanti.**

   - **Caricare un file di esempio.** Se si seleziona questa opzione, fare clic su **Carica file di** esempio per caricare il file CSV preparato nel passaggio 1. Questa opzione consente di selezionare rapidamente i nomi delle colonne nel file CSV da un elenco a discesa per mapparli ai tipi di dati per gli scenari hr selezionati in precedenza.

   OPPURE

   - **Specificare manualmente i dettagli del mapping.** Se si seleziona questa opzione, è necessario digitare il nome delle colonne nel file CSV per mapparle ai tipi di dati per gli scenari hr selezionati in precedenza.

7. Nella pagina Dettagli mapping file eseguire una delle operazioni seguenti, a seconda che sia stato caricato un file CSV di esempio e se si sta configurando il connettore per un singolo scenario hr o per più scenari. Se è stato caricato un file di esempio, non è necessario digitare i nomi delle colonne. Puoi sceglierli da un elenco a discesa.

    - Se nel passaggio precedente è stato selezionato un singolo scenario hr, digitare i nomi delle intestazioni di colonna (denominati anche *parametri)* dal file CSV creato nel passaggio 1 in ognuna delle caselle appropriate. I nomi di colonna digitati non supportano la distinzione tra maiuscole e minuscole, ma assicurarsi di includere spazi se i nomi di colonna nel file CSV includono spazi. Come spiegato in precedenza, i nomi digitati in queste caselle devono corrispondere ai nomi dei parametri nel file CSV. Ad esempio, lo screenshot seguente mostra i nomi dei parametri del file CSV di esempio per lo scenario hr di dimissioni dei dipendenti mostrato nel passaggio 1.

    - Se hai selezionato più tipi di dati nel passaggio precedente, devi immettere il nome della colonna dell'identificatore che identificherà il tipo di dati HR nel file CSV. Dopo aver immesso il nome della colonna dell'identificatore, digitare il valore che identifica questo tipo di dati HR e digitare i nomi delle intestazioni di colonna per i tipi di dati selezionati dai file CSV creati nel passaggio 1 in ognuna delle caselle appropriate per ogni tipo di dati selezionato. Come spiegato in precedenza, i nomi digitati in queste caselle devono corrispondere ai nomi di colonna nel file CSV.

8. Nella pagina **Revisione** rivedere le impostazioni e quindi fare clic su **Fine** per creare il connettore.

   Viene visualizzata una pagina di stato che conferma la creazione del connettore. Questa pagina contiene due aspetti importanti necessari per completare il passaggio successivo per eseguire lo script di esempio per caricare i dati delle risorse umane.

   ![Pagina Di revisione con ID processo e collegamento a github per script di esempio](../media/HRConnector_Confirmation.png)

   1. **ID processo.** Questo ID processo sarà necessario per eseguire lo script nel passaggio successivo. È possibile copiarlo da questa pagina o dalla pagina del riquadro a comparsa del connettore.

   1. **Collegamento a uno script di esempio.** Fare clic **sul** collegamento qui per passare al sito GitHub per accedere allo script di esempio (il collegamento apre una nuova finestra). Tenere aperta questa finestra in modo da poter copiare lo script nel passaggio 4. In alternativa, è possibile aggiungere un segnalibro alla destinazione o copiare l'URL in modo che sia possibile accedervi nuovamente quando si esegue lo script. Questo collegamento è disponibile anche nella pagina del riquadro a comparsa del connettore.

9. Fare clic su **Fine**.

   Il nuovo connettore viene visualizzato nell'elenco nella **scheda Connettori.**

10. Fare clic sul connettore risorse umane appena creato per visualizzare la pagina del riquadro a comparsa, che contiene le proprietà e altre informazioni sul connettore.

   ![Pagina a comparsa per il nuovo connettore risorse umane](../media/HRConnectorWizard7.png)

Se non lo hai già fatto, puoi copiare i valori per **l'ID app di Azure** e l'ID processo **del connettore.** Saranno necessari per eseguire lo script nel passaggio successivo. Puoi anche scaricare lo script dalla pagina a comparsa (o scaricarlo usando il collegamento nel passaggio successivo).

È anche possibile fare clic **su Modifica** per modificare l'ID app di Azure o i nomi delle intestazioni di colonna definiti nella pagina **Mapping file.**

## <a name="step-4-run-the-sample-script-to-upload-your-hr-data"></a>Passaggio 4: Eseguire lo script di esempio per caricare i dati delle risorse umane

L'ultimo passaggio nella configurazione di un connettore hr consiste nell'eseguire uno script di esempio che consente di caricare i dati delle risorse umane nel file CSV (creato nel passaggio 1) nel cloud Microsoft. In particolare, lo script carica i dati nel connettore hr. Dopo aver eseguito lo script, il connettore hr creato nel passaggio 3 importa i dati sulle risorse umane nell'organizzazione di Microsoft 365, dove è possibile accedervi da altri strumenti di conformità, ad esempio la soluzione di gestione dei rischi Insider. Dopo aver eseguito lo script, prendere in considerazione la pianificazione di un'attività per eseguirla automaticamente su base giornaliera, in modo che i dati di licenziamento dei dipendenti più aggiornati vengono caricati nel cloud Microsoft. Vedere [Pianificare l'esecuzione automatica dello script.](#optional-step-6-schedule-the-script-to-run-automatically)

1. Passare alla finestra lasciata aperta dal passaggio precedente per accedere al sito GitHub con lo script di esempio. In alternativa, aprire il sito con segnalibri o utilizzare l'URL copiato.

2. Fare clic **sul pulsante** Non elaborato per visualizzare lo script nella visualizzazione testo.

3. Copiare tutte le righe dello script di esempio e quindi salvarle in un file di testo.

4. Modificare lo script di esempio per l'organizzazione, se necessario.

5. Salvare il file di testo come Windows PowerShell file script utilizzando il suffisso del nome file `.ps1` ; ad esempio, `HRConnector.ps1` .

6. Aprire un prompt dei comandi nel computer locale e passare alla directory in cui è stato salvato lo script.

7. Eseguire il comando seguente per caricare i dati delle risorse umane nel file CSV nel cloud Microsoft; Per esempio:

    ```powershell
    .\HRConnector.ps1 -tenantId <tenantId> -appId <appId>  -appSecret <appSecret>  -jobId <jobId>  -csvFilePath '<csvFilePath>'
    ```

   Nella tabella seguente vengono descritti i parametri da utilizzare con questo script e i relativi valori obbligatori. Le informazioni ottenute nei passaggi precedenti vengono utilizzate nei valori per questi parametri.

   | Parametro | Descrizione |
   |:-----|:-----|:-----|
   |`tenantId`|Questo è l'ID dell'organizzazione di Microsoft 365 ottenuta nel passaggio 2. È anche possibile ottenere l'ID tenant per l'organizzazione nel pannello **Panoramica** nell'interfaccia di amministrazione di Azure AD. Viene usato per identificare l'organizzazione.|
   |`appId` |Questo è l'ID dell'applicazione Azure AD per l'app creata in Azure AD nel passaggio 2. Viene usato da Azure AD per l'autenticazione quando lo script tenta di accedere all'organizzazione di Microsoft 365. | 
   |`appSecret`|Questo è il segreto dell'applicazione Azure AD per l'app creata in Azure AD nel passaggio 2. Utilizzato anche per l'autenticazione.|
   |`jobId`|Questo è l'ID processo per il connettore HR creato nel passaggio 3. Viene usato per associare i dati delle risorse umane caricati nel cloud Microsoft al connettore hr.|
   |`csvFilePath`|Questo è il percorso del file CSV (archiviato nello stesso sistema dello script) creato nel passaggio 1. Cercare di evitare spazi nel percorso del file. in caso contrario, utilizzare virgolette singole.|
   |||

   Ecco un esempio della sintassi per lo script del connettore HR utilizzando i valori effettivi per ogni parametro:

   ```powershell
    .\HRConnector.ps1 -tenantId d5723623-11cf-4e2e-b5a5-01d1506273g9 -appId 29ee526e-f9a7-4e98-a682-67f41bfd643e -appSecret MNubVGbcQDkGCnn -jobId b8be4a7d-e338-43eb-a69e-c513cd458eba -csvFilePath 'C:\Users\contosoadmin\Desktop\Data\employee_termination_data.csv'
    ```

   Se il caricamento ha esito positivo, lo script visualizza il **messaggio Caricamento** completato.

   > [!NOTE]
   > In caso di problemi durante l'esecuzione del comando precedente a causa dei criteri di esecuzione, vedere [Informazioni](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies) sui criteri di esecuzione e [Set-ExecutionPolicy](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy) per indicazioni sull'impostazione dei criteri di esecuzione.

## <a name="step-5-monitor-the-hr-connector"></a>Passaggio 5: Monitorare il connettore hr

Dopo aver creato il connettore HR ed eseguito lo script per caricare i dati delle risorse umane, è possibile visualizzare il connettore e caricare lo stato nel Centro conformità Microsoft 365. Se si pianifica l'esecuzione automatica dello script a intervalli regolari, è inoltre possibile visualizzare lo stato corrente dopo l'ultima esecuzione dello script.

1. Andare a [https://compliance.microsoft.com](https://compliance.microsoft.com) e fare clic su **Connettori dati** nel riquadro di spostamento sinistro.

2. Fare clic **sulla scheda Connettori** e quindi selezionare il connettore HR per visualizzare la pagina del riquadro a comparsa. Questa pagina contiene le proprietà e le informazioni sul connettore.

   ![Pagina a comparsa del connettore HR con proprietà e stato](../media/HRConnectorFlyout1.png)

3. In **Stato** fare clic sul **collegamento Scarica registro** per aprire (o salvare) il registro di stato per il connettore. Questo log contiene informazioni su ogni esecuzione dello script e sul caricamento dei dati dal file CSV nel cloud Microsoft. 

   ![Il file di registro del connettore hr visualizza le righe dei numeri dal file CSV che sono state caricate](../media/HRConnectorLogFile.png)

   Il `RecordsSaved` campo indica il numero di righe nel file CSV caricato. Ad esempio, se il file CSV contiene quattro righe, il valore dei campi è 4, se lo script ha caricato correttamente tutte le righe `RecordsSaved` nel file CSV.

Se lo script non è stato eseguito nel passaggio 4, viene visualizzato un collegamento per scaricare lo script in **Ultima importazione.** È possibile scaricare lo script e quindi seguire i passaggi per eseguire lo script.

## <a name="optional-step-6-schedule-the-script-to-run-automatically"></a>(Facoltativo) Passaggio 6: Pianificare l'esecuzione automatica dello script

Per assicurarsi che i dati sulle risorse umane più recenti dell'organizzazione siano disponibili per strumenti come la soluzione di gestione dei rischi Insider, è consigliabile pianificare l'esecuzione automatica dello script su base ricorrente, ad esempio una volta al giorno. È inoltre necessario aggiornare i dati sulle risorse umane nel file CSV in base a una pianificazione simile(se non la stessa) in modo che contenga le informazioni più recenti sui dipendenti che lasciano l'organizzazione. L'obiettivo è quello di caricare i dati delle risorse umane più correnti in modo che il connettore HR possa renderli disponibili per la soluzione di gestione dei rischi Insider.

Puoi usare l'app Utilità di pianificazione in Windows per eseguire automaticamente lo script ogni giorno.

1. Nel computer locale fare clic sul pulsante **Start** di Windows e quindi digitare **Utilità di pianificazione.**

2. Fare clic **sull'app Utilità** di pianificazione per aprirla.

3. Nella sezione **Azioni** fare clic su **Crea attività.**

4. Nella scheda **Generale** digitare un nome descrittivo per l'attività pianificata. ad esempio, **HR Connector Script.** È inoltre possibile aggiungere una descrizione facoltativa.

5. In **Opzioni di sicurezza** eseguire le operazioni seguenti:

   1. Determinare se eseguire lo script solo quando si è connessi al computer o se eseguirlo quando si è connessi o meno.

   1. Assicurati che la **casella di controllo Esegui con i privilegi più** elevati sia selezionata.

6. Selezionare la **scheda Trigger,** fare clic su **Nuovo** e quindi eseguire le operazioni seguenti:

   1. In **Impostazioni** selezionare l'opzione **Giornaliera** e quindi scegliere la data e l'ora in cui eseguire lo script per la prima volta. Lo script verrà eseguito ogni giorno alla stessa ora specificata.

   1. In **Impostazioni avanzate** verificare che la casella di controllo **Abilitato** sia selezionata.

   1. Fare clic su **OK**.

7. Selezionare la **scheda Azioni,** fare clic **su Nuovo** e quindi eseguire le operazioni seguenti:

   ![Impostazioni delle azioni per creare una nuova attività pianificata per lo script del connettore risorse umane](../media/HRConnectorScheduleTask1.png)

   1. **Nell'elenco a** discesa Azione verificare che sia selezionata l'opzione **Avvia** un programma.

   1. Nella casella **Programma/script** fare clic su **Sfoglia** e passare al percorso seguente e selezionarlo in modo che il percorso sia visualizzato nella casella: `C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe` .

   1. Nella casella **Aggiungi argomenti (facoltativo)** incollare lo stesso comando script eseguito nel passaggio 4. Per esempio `.\HRConnector.ps1 -tenantId "d5723623-11cf-4e2e-b5a5-01d1506273g9" -appId "c12823b7-b55a-4989-faba-02de41bb97c3" -appSecret "MNubVGbcQDkGCnn"  -jobId "e081f4f4-3831-48d6-7bb3-fcfab1581458" -csvFilePath "C:\Users\contosoadmin\Desktop\Data\employee_termination_data.csv"`

   1. Nella casella **Inizia in (facoltativo)** incollare il percorso della cartella dello script eseguito nel passaggio 4. Ad esempio, `C:\Users\contosoadmin\Desktop\Scripts`.

   1. Fare **clic su OK** per salvare le impostazioni per la nuova azione.

8. Nella finestra **Crea attività** fare clic su **OK** per salvare l'attività pianificata. Potrebbe essere richiesto di immettere le credenziali dell'account utente.

   La nuova attività viene visualizzata nella libreria dell'Utilità di pianificazione.

   ![La nuova attività viene visualizzata nella libreria dell'Utilità di pianificazione](../media/HRConnectorTaskSchedulerLibrary.png)

   Viene visualizzata l'ora dell'ultima esecuzione dello script e la successiva esecuzione pianificata. È possibile fare doppio clic sull'attività per modificarla.

   È inoltre possibile verificare l'ultima esecuzione dello script nella pagina a comparsa del connettore hr corrispondente nel Centro conformità.

## <a name="existing-hr-connectors"></a>Connettori HR esistenti

Il 20 luglio 2020 sono stati rilasciati ulteriori scenari supportati dai connettori HR. Questi sono gli scenari relativi alle risorse umane descritti in precedenza in questo articolo. Qualsiasi connettore HR creato prima di questa data supporta solo lo scenario di dimissioni dei dipendenti. Se è stato creato un connettore hr prima del 20 luglio 2020, è stata eseguita la migrazione in modo che continui a eseguire la migrazione dei dati delle risorse umane nel cloud Microsoft. Non è necessario eseguire alcun'operazione per mantenere questa funzionalità. È possibile continuare a utilizzare il connettore senza interruzioni.

Se si desidera implementare ulteriori scenari di risorse umane, creare un nuovo connettore hr e configurarlo per gli altri scenari hr rilasciati. Dovrai anche creare uno o più nuovi file CSV contenenti i dati per supportare gli scenari hr aggiuntivi. Dopo aver creato un nuovo connettore hr, eseguire lo script utilizzando l'ID processo del nuovo connettore e i file CSV con i dati per gli scenari hr aggiuntivi.
