---
title: Configurare un connettore per importare i dati delle risorse umane nel cloud del governo statunitense
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
ROBOTS: NOINDEX, NOFOLLOW
description: Gli amministratori nel cloud us government possono configurare un connettore dati per importare i dati dei dipendenti dal sistema delle risorse umane dell'organizzazione in Microsoft 365. In questo modo è possibile utilizzare i dati delle risorse umane nei criteri di gestione dei rischi insider per rilevare le attività di utenti specifici che potrebbero rappresentare una minaccia interna per l'organizzazione.
ms.openlocfilehash: 16d6d72d557744e30d41795d5f8c8a17db81c6a3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905928"
---
# <a name="set-up-a-connector-to-import-hr-data-in-us-government"></a>Configurare un connettore per importare i dati delle risorse umane in US Government

È possibile configurare un connettore dati nel Centro conformità Microsoft 365 per importare i dati delle risorse umane nell'organizzazione del governo statunitense. I dati relativi alle risorse umane includono la data in cui un dipendente ha inviato le proprie dimissioni e la data dell'ultimo giorno del dipendente. Questi dati sulle risorse umane possono quindi essere utilizzati dalle soluzioni di protezione delle informazioni Microsoft, ad esempio la soluzione di gestione dei rischi [insider,](insider-risk-management.md)per proteggere l'organizzazione da attività dannose o furti di dati all'interno dell'organizzazione. La configurazione di un connettore hr consiste nella creazione di un'app in Azure Active Directory usata per l'autenticazione da parte del connettore, nella creazione di un file di mapping CSV contenente i dati delle risorse umane, nella creazione di un connettore dati nel Centro conformità e quindi nell'esecuzione di uno script (su base pianificata) che inserisce i dati delle risorse umane nel file CSV nel cloud Microsoft. Il connettore dati viene quindi utilizzato dallo strumento di gestione dei rischi insider per accedere ai dati delle risorse umane importati nell'organizzazione di Microsoft 365 US Government.

## <a name="before-you-begin"></a>Prima di iniziare

- All'utente che crea il connettore HR nel passaggio 3 deve essere assegnato il ruolo Esportazione importazione cassette postali in Exchange Online. Per impostazione predefinita, questo ruolo non è assegnato ad alcun gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo Esportazione importazione cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In caso contrario, è possibile creare un nuovo gruppo di ruoli, assegnare il ruolo importazione/esportazione delle cassette postali e quindi aggiungere gli utenti appropriati come membri. Per ulteriori informazioni, vedere le sezioni [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) o Modify role [groups](/Exchange/permissions-exo/role-groups#modify-role-groups) nell'articolo "Manage role groups in Exchange Online".

- Dovrai determinare come recuperare o esportare i dati dal sistema hr dell'organizzazione (a intervalli regolari) e aggiungerli al file CSV descritto nel passaggio 2. Lo script eseguito nel passaggio 4 carica i dati delle risorse umane nel file CSV nel cloud Microsoft.

- Lo script di esempio eseguito nel passaggio 4 consente di caricare i dati delle risorse umane nel cloud Microsoft in modo che possano essere utilizzati da altri strumenti Microsoft, ad esempio la soluzione di gestione dei rischi insider. Questo script di esempio non è supportato in alcun servizio o programma di supporto standard Microsoft. Lo script di esempio è fornito così come è senza alcun tipo di garanzia. Microsoft esclude inoltre qualsiasi garanzia implicita, tra cui, senza limitazioni, tutte le garanzie implicite di commerciabilità o idoneità per uno scopo specifico. L'utente assume tutti i rischi associati all'uso o alle prestazioni dello script di esempio e della documentazione. In nessun caso Microsoft, i suoi autori o chiunque altro coinvolto nella creazione, produzione o consegna degli script è da ritenersi responsabile per qualsiasi danno eventuale (inclusi, senza limitazione alcuna, danni riguardanti profitti aziendali, interruzione di attività, perdita di informazioni aziendali o altra perdita pecuniaria) derivanti dall'utilizzo o dall'incapacità di utilizzo degli script di esempio e della documentazione, anche nel caso in cui Microsoft sia stata avvisata della possibilità di tali danni.

## <a name="step-1-create-an-app-in-azure-active-directory"></a>Passaggio 1: Creare un'app in Azure Active Directory

Il primo passaggio consiste nel creare e registrare una nuova app in Azure Active Directory (Azure AD). L'app corrisponderà al connettore HR creato nel passaggio 3. La creazione di questa app consentirà ad Azure AD di autenticare il connettore HR quando viene eseguito e tenterà di accedere all'organizzazione. Questa app verrà usata anche per autenticare lo script eseguito nel passaggio 4 per caricare i dati delle risorse umane nel cloud Microsoft. Durante la creazione di questa app Azure AD, assicurati di salvare le informazioni seguenti. Questi valori verranno utilizzati nei passaggi successivi.

- ID applicazione Azure AD (denominato anche *ID app* o *ID client)*

- Segreto dell'applicazione Azure AD (denominato *anche segreto client)*

- ID tenant (denominato anche *ID directory)*

Per istruzioni dettagliate sulla creazione di un'app in Azure AD, vedi [Registrare un'applicazione con la piattaforma di identità Microsoft.](/azure/active-directory/develop/quickstart-register-app)

## <a name="step-2-prepare-a-csv-file-with-your-hr-data"></a>Passaggio 2: Preparare un file CSV con i dati delle risorse umane

Il passaggio successivo consiste nel creare un file CSV contenente informazioni sui dipendenti che hanno lasciato l'organizzazione. Come spiegato nella sezione Prima di iniziare, è necessario determinare come generare questo file CSV dal sistema hr dell'organizzazione. L'esempio seguente mostra un file CSV completato (aperto in Note Pad) contenente i tre parametri obbligatori (colonne). È molto più semplice modificare il file CSV in Microsoft Excel.

```text
EmailAddress,TerminationDate,LastWorkingDate
sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,2019-04-29T15:18:02.4675041+05:30
pilarp@contoso.com,2019-04-24T09:15:49Z,2019-04-29T15:18:02.7117540
```

Nella prima riga, o riga di intestazione, del file CSV sono elencati i nomi di colonna necessari. Il nome utilizzato in ogni intestazione di colonna è a te (quelli nell'esempio precedente sono suggerimenti). Tuttavia, è necessario specificare gli stessi nomi di colonna utilizzati nel *file* CSV quando si crea il connettore HR nel passaggio 3. Non includere spazi nei nomi delle colonne.

Nella tabella seguente viene descritta ogni colonna del file CSV:

| Nome colonna | Descrizione |
|:-----|:-----|
| **EmailAddress** <br/> |Specifica l'indirizzo di posta elettronica del dipendente terminato.|
| **TerminationDate** <br/> |Specifica la data in cui l'impiego della persona è stato ufficialmente terminato nell'organizzazione. Ad esempio, questa potrebbe essere la data in cui il dipendente ha dato l'avviso sull'uscita dall'organizzazione. Questa data può essere diversa dalla data dell'ultimo giorno di lavoro della persona. Utilizzare il formato di data seguente: , che è il formato di data e ora `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` [ISO 8601.](https://www.iso.org/iso-8601-date-and-time-format.html)|
|**LastWorkingDate**|Specifica l'ultimo giorno di lavoro per il dipendente terminato. Utilizzare il formato di data seguente: , che è il formato di data e ora `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` [ISO 8601.](https://www.iso.org/iso-8601-date-and-time-format.html)|
|||

Dopo aver creato il file CSV con i dati delle risorse umane necessari, archiviarlo nello stesso sistema dello script eseguito nel passaggio 4. Assicurarsi di implementare una strategia di aggiornamento in modo che il file CSV contenga sempre le informazioni più aggiornate. In questo modo si garantisce che, qualunque sia l'esecuzione dello script, i dati più attuali sulla risoluzione dei dipendenti siano caricati nel cloud Microsoft.

## <a name="step-3-create-the-hr-connector"></a>Passaggio 3: Creare il connettore risorse umane

Il passaggio successivo consiste nel creare un connettore hr nel Centro conformità Microsoft 365. Dopo aver eseguito lo script nel passaggio 4, il connettore HR creato ingestirà i dati delle risorse umane dal file CSV all'organizzazione di Microsoft 365. In questo passaggio, assicurarsi di copiare l'ID processo generato quando si crea il connettore. L'ID processo verrà utilizzato quando si esegue lo script.

1. Vai a [https://compliance.microsoft.com](https://compliance.microsoft.com) e quindi fai clic su **Connettori dati** nel riquadro di spostamento sinistro.

2. Nella pagina **Connettori dati** in **Risorse umane** fare clic su **Visualizza.**

3. Nella pagina **Risorse** umane fare clic **su Aggiungi connettore**.

4. Nella pagina **Credenziali di autenticazione** eseguire le operazioni seguenti e quindi fare clic su **Avanti:**

   1. Digitare o incollare l'ID applicazione Azure AD per l'app Azure creata nel passaggio 1.

   1. Digitare un nome per il connettore HR.

5. Nella pagina **Mapping file** digitare i nomi delle tre intestazioni di colonna (denominate anche *parametri)* dal file CSV creato nel passaggio 2 in ognuna delle caselle appropriate. Per i nomi non viene fatto distinzione tra maiuscole e minuscole. Come spiegato in precedenza, i nomi digitati in queste caselle devono corrispondere ai nomi dei parametri nel file CSV. Ad esempio, lo screenshot seguente mostra i nomi dei parametri dell'esempio nel file CSV di esempio mostrato nel passaggio 2.

   ![I nomi delle intestazioni di colonna corrispondono a quelli nel file CSV](../media/HRConnectorWizard3.png)

6. Nella pagina **Revisione** rivedere le impostazioni e quindi fare clic su **Fine** per creare il connettore.

   Viene visualizzata una pagina di stato che conferma la creazione del connettore. Questa pagina contiene due aspetti importanti che è necessario completare nel passaggio successivo per eseguire lo script di esempio per caricare i dati delle risorse umane.

   ![Pagina Di revisione con ID processo e collegamento a github per script di esempio](../media/HRConnector_Confirmation.png)

   1. **ID processo.** Questo ID processo sarà necessario per eseguire lo script nel passaggio successivo. È possibile copiarlo da questa pagina o dalla pagina del riquadro a comparsa del connettore.
   
   1. **Collegamento allo script di esempio.** Fai clic **sul** collegamento qui per accedere al sito GitHub per accedere allo script di esempio (il collegamento apre una nuova finestra). Tenere aperta questa finestra in modo che sia possibile copiare lo script nel passaggio 4. In alternativa, è possibile aggiungere un segnalibro alla destinazione o copiare l'URL in modo da poterlo accedere di nuovo nel passaggio 4. Questo collegamento è disponibile anche nella pagina del riquadro a comparsa del connettore.

7. Fare clic su **Fatto**.

   Il nuovo connettore viene visualizzato nell'elenco nella **scheda Connettori.** 

8. Fare clic sul connettore HR appena creato per visualizzare la pagina a comparsa, che contiene proprietà e altre informazioni sul connettore.

   ![Pagina riquadro a comparsa per il nuovo connettore risorse umane](../media/HRConnectorWizard7.png)

   Se non l'hai già fatto, puoi copiare i valori per **l'ID app di Azure** e l'ID processo **del connettore.** Saranno necessari per eseguire lo script nel passaggio successivo. Puoi anche scaricare lo script dalla pagina a comparsa (o scaricarlo usando il collegamento nel passaggio successivo).

   È anche possibile fare **clic su** Modifica per modificare l'ID app di Azure o i nomi delle intestazioni di colonna definiti nella pagina **Mapping file.**

## <a name="step-4-run-the-sample-script-to-upload-your-hr-data"></a>Passaggio 4: Eseguire lo script di esempio per caricare i dati delle risorse umane

L'ultimo passaggio per configurare un connettore HR consiste nell'eseguire uno script di esempio che carichi i dati delle risorse umane nel file CSV (creato nel passaggio 2) nel cloud Microsoft. In particolare, lo script carica i dati nel connettore HR. Dopo aver eseguito lo script, il connettore HR creato nel passaggio 3 importa i dati delle risorse umane nell'organizzazione di Microsoft 365 a cui possono accedere altri strumenti di conformità, ad esempio la soluzione di gestione dei rischi Insider. Dopo aver eseguito lo script, è consigliabile pianificare un'attività per eseguirla automaticamente ogni giorno in modo che i dati più aggiornati sulla risoluzione dei dipendenti vengono caricati nel cloud Microsoft. Vedere [Pianificare l'esecuzione automatica dello script.](#optional-step-6-schedule-the-script-to-run-automatically)

1. Vai alla finestra lasciata aperta dal passaggio precedente per accedere al sito GitHub con lo script di esempio. In alternativa, aprire il sito con segnalibri o utilizzare l'URL copiato.

2. Fare clic **sul pulsante** Non elaborato per visualizzare lo script in visualizzazione testo.

3. Copiare tutte le righe dello script di esempio e quindi salvarle in un file di testo.

4. Modificare lo script di esempio per l'organizzazione, se necessario.

5. Salvare il file di testo come Windows PowerShell di script utilizzando il suffisso del nome del file `.ps1` ; ad esempio, `HRConnector.ps1` .

6. Aprire un prompt dei comandi nel computer locale e passare alla directory in cui è stato salvato lo script.

7. Eseguire il comando seguente per caricare i dati delle risorse umane nel file CSV nel cloud Microsoft. Per esempio:

    ```powershell
    .\HRConnector.ps1 -tenantId <tenantId> -appId <appId>  -appSecret <appSecret>  -jobId <jobId>  -csvFilePath '<csvFilePath>'
    ```

   Nella tabella seguente vengono descritti i parametri da utilizzare con questo script e i relativi valori obbligatori. Le informazioni ottenute nei passaggi precedenti vengono utilizzate nei valori per questi parametri.

   | Parametro | Descrizione |
   |:-----|:-----|:-----|
   |`tenantId`|ID per l'organizzazione di Microsoft 365 ottenuta nel passaggio 1. È anche possibile ottenere l'ID tenant per l'organizzazione nel pannello **Panoramica** nell'interfaccia di amministrazione di Azure AD. Viene utilizzato per identificare l'organizzazione.|
   |`appId` |ID dell'applicazione Azure AD per l'app creata in Azure AD nel passaggio 1. Viene usato da Azure AD per l'autenticazione quando lo script tenta di accedere all'organizzazione di Microsoft 365. |
   |`appSecret`|Segreto dell'applicazione Azure AD per l'app creata in Azure AD nel passaggio 1. Utilizzato anche per l'autenticazione.|
   |`jobId`|ID processo per il connettore HR creato nel passaggio 3. Viene usato per associare i dati delle risorse umane caricati nel cloud Microsoft al connettore HR.|
   |`csvFilePath`|Percorso del file CSV (archiviato nello stesso sistema dello script) creato nel passaggio 2. Cercare di evitare spazi nel percorso del file. in caso contrario, utilizzare virgolette singole.|
   |||
   
   Ecco un esempio di sintassi per lo script del connettore HR usando i valori effettivi per ogni parametro:

   ```powershell
    .\HRConnector.ps1 -tenantId d5723623-11cf-4e2e-b5a5-01d1506273g9 -appId 29ee526e-f9a7-4e98-a682-67f41bfd643e -appSecret MNubVGbcQDkGCnn -jobId b8be4a7d-e338-43eb-a69e-c513cd458eba -csvFilePath 'C:\Users\contosoadmin\Desktop\Data\employee_termination_data.csv'
    ```

   Se il caricamento ha esito positivo, lo script visualizza il **messaggio Caricamento** completato.

   > [!NOTE]
   > In caso di problemi durante l'esecuzione del comando precedente a causa dei criteri di esecuzione, vedere [Informazioni](/powershell/module/microsoft.powershell.core/about/about_execution_policies) sui criteri di esecuzione e [Set-ExecutionPolicy](/powershell/module/microsoft.powershell.security/set-executionpolicy) per indicazioni sull'impostazione dei criteri di esecuzione.

## <a name="step-5-monitor-the-hr-connector"></a>Passaggio 5: Monitorare il connettore HR

Dopo aver creato il connettore HR ed eseguito lo script per caricare i dati delle risorse umane, è possibile visualizzare il connettore e lo stato di caricamento nel Centro conformità Microsoft 365. Se si pianifica l'esecuzione automatica dello script a intervalli regolari, è anche possibile visualizzare lo stato corrente dopo l'ultima esecuzione dello script.

1. Vai a [https://compliance.microsoft.com](https://compliance.microsoft.com) e fai clic su **Connettori dati** nel riquadro di spostamento sinistro.

2. Fare clic **sulla scheda Connettori** e quindi selezionare il connettore HR per visualizzare la pagina a comparsa. Questa pagina contiene le proprietà e le informazioni sul connettore.

   ![Pagina a comparsa del connettore HR con proprietà e stato](../media/HRConnectorFlyout1.png)

3. In **Stato** fare clic sul **collegamento Scarica registro** per aprire (o salvare) il registro di stato per il connettore. Questo registro contiene informazioni su ogni esecuzione dello script e sul caricamento dei dati dal file CSV nel cloud Microsoft. 

   ![Il file di registro del connettore HR visualizza le righe dei numeri dal file CSV che sono state caricate](../media/HRConnectorLogFile.png)

   Il `RecordsSaved` campo indica il numero di righe nel file CSV caricato. Ad esempio, se il file CSV contiene quattro righe, il valore dei campi è 4, se lo script ha caricato correttamente tutte le righe `RecordsSaved` nel file CSV.

Se lo script non è stato eseguito nel passaggio 4, viene visualizzato un collegamento per scaricare lo script in **Ultima importazione.** È possibile scaricare lo script e quindi seguire i passaggi del passaggio 4 per eseguirlo.

## <a name="optional-step-6-schedule-the-script-to-run-automatically"></a>(Facoltativo) Passaggio 6: Pianificare l'esecuzione automatica dello script

Per assicurarsi che i dati sulle risorse umane più recenti dell'organizzazione siano disponibili per strumenti come la soluzione di gestione dei rischi insider, è consigliabile pianificare l'esecuzione automatica dello script su base ricorrente, ad esempio una volta al giorno. È inoltre necessario aggiornare i dati delle risorse umane nel file CSV in base a una pianificazione simile (se non la stessa) in modo che contenga le informazioni più recenti sui dipendenti che lasciano l'organizzazione. L'obiettivo è caricare i dati delle risorse umane più correnti in modo che il connettore HR possa renderli disponibili per la soluzione di gestione dei rischi insider.

Puoi usare l'app Utilità di pianificazione in Windows per eseguire automaticamente lo script ogni giorno.

1. Nel computer locale fare clic sul pulsante **Start** di Windows e quindi digitare **Utilità di pianificazione.**

2. Fai clic **sull'app Utilità** di pianificazione per aprirla.

3. Nella sezione **Azioni** fare clic su **Crea attività.**

4. Nella scheda **Generale** digitare un nome descrittivo per l'attività pianificata. ad esempio, **HR Connector Script**. È inoltre possibile aggiungere una descrizione facoltativa.

5. In **Opzioni di sicurezza** eseguire le operazioni seguenti:

   1. Determinare se eseguire lo script solo quando si è connessi al computer o eseguirlo quando si è connessi o meno.
   
   1. Assicurati che la **casella di controllo Esegui con** i privilegi più elevati sia selezionata.

6. Selezionare la **scheda Trigger,** fare clic **su Nuovo** e quindi eseguire le operazioni seguenti:

   1. In **Impostazioni** selezionare l'opzione **Giornaliero** e quindi scegliere una data e un'ora per eseguire lo script per la prima volta. Lo script verrà eseguito ogni giorno alla stessa ora specificata.
   
   1. In **Impostazioni avanzate** assicurati che la casella di controllo **Abilitato** sia selezionata.
   
   1. Fare clic su **OK**.

7. Selezionare la **scheda Azioni,** fare clic **su Nuovo** e quindi eseguire le operazioni seguenti:

   ![Impostazioni delle azioni per creare una nuova attività pianificata per lo script del connettore risorse umane](../media/HRConnectorScheduleTask1.png)

   1. **Nell'elenco a** discesa Azione assicurati che l'opzione **Avvia un** programma sia selezionata.

   1. Nella casella **Programma/script** fare clic **su** Sfoglia e passare al percorso seguente e selezionarlo in modo che il percorso sia visualizzato nella casella: `C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe` .

   1. Nella casella **Aggiungi argomenti (facoltativo)** incollare lo stesso comando di script eseguito nel passaggio 4. Per esempio `.\HRConnector.ps1 -tenantId "d5723623-11cf-4e2e-b5a5-01d1506273g9" -appId "c12823b7-b55a-4989-faba-02de41bb97c3" -appSecret "MNubVGbcQDkGCnn"  -jobId "e081f4f4-3831-48d6-7bb3-fcfab1581458" -csvFilePath "C:\Users\contosoadmin\Desktop\Data\employee_termination_data.csv"`

   1. Nella casella **Inizia in (facoltativo)** incollare il percorso della cartella dello script eseguito nel passaggio 4. Ad esempio, `C:\Users\contosoadmin\Desktop\Scripts`.

   1. Fare **clic su OK** per salvare le impostazioni per la nuova azione.

8. Nella finestra **Crea attività** fare clic su **OK** per salvare l'attività pianificata. Potrebbe essere richiesto di immettere le credenziali dell'account utente.

   La nuova attività viene visualizzata nella libreria dell'Utilità di pianificazione.

   ![La nuova attività viene visualizzata nella libreria dell'Utilità di pianificazione](../media/HRConnectorTaskSchedulerLibrary.png)

   Viene visualizzata l'ultima esecuzione dello script e la successiva esecuzione pianificata. È possibile fare doppio clic sull'attività per modificarla.

   È inoltre possibile verificare l'ultima esecuzione dello script nella pagina a comparsa del connettore HR corrispondente nel Centro conformità.