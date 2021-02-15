---
title: Configurare un connettore per importare i dati di badging fisico
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
description: Gli amministratori possono configurare un connettore dati per importare i dati dal sistema di badging fisico dell'organizzazione in Microsoft 365. In questo modo è possibile utilizzare questi dati nei criteri di gestione dei rischi Insider per rilevare l'accesso agli edifici fisici da parte di utenti specifici che potrebbero indicare una possibile minaccia interna all'organizzazione.
ms.openlocfilehash: 7e745b42d0df79f5c39f9fa02cb1b63f164ec2a5
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620132"
---
# <a name="set-up-a-connector-to-import-physical-badging-data-preview"></a>Configurare un connettore per importare i dati fisici di badging (anteprima)

È possibile configurare un connettore di dati nel Centro conformità Microsoft 365 per importare i dati fisici di badging, ad esempio gli eventi di accesso fisico non elaborato dei dipendenti o eventuali allarmi di accesso fisico generati dal sistema di badging dell'organizzazione. Alcuni esempi di punti di accesso fisici sono l'ingresso a un edificio o l'ingresso nella sala server o nel data center. I dati di badging fisico possono essere usati dalla soluzione di gestione dei rischi [insider](insider-risk-management.md) di Microsoft 365 per proteggere l'organizzazione da attività dannose o furti di dati all'interno dell'organizzazione.

La configurazione di un connettore di badging fisico è costituita dalle attività seguenti:

- Creazione di un'app in Azure Active Directory (Azure AD) per accedere a un endpoint API che accetta un payload JSON contenente dati di badging fisici.

- Creazione del payload JSON con uno schema definito dal connettore dati di badging fisico.

- Creazione di un connettore dati di badging fisico nel Centro conformità Microsoft 365.

- Esecuzione di uno script per eseguire il push dei dati fisici non validi all'endpoint DELL.

- Facoltativamente, pianificando l'esecuzione automatica dello script per importare i dati di badging fisici.

## <a name="before-you-set-up-the-connector"></a>Prima di configurare il connettore

- All'utente che crea il connettore di badging fisico nel passaggio 3 deve essere assegnato il ruolo di importazione/esportazione delle cassette postali in Exchange Online. Per impostazione predefinita, questo ruolo non è assegnato ad alcun gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo di importazione/esportazione delle cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In or you can create a new role group, assign the Mailbox Import Export role, and then add the appropriate users as members. Per ulteriori informazioni, vedere le sezioni [Creazione](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) di gruppi di ruoli o Modifica gruppi [di](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) ruoli nell'articolo "Gestire i gruppi di ruoli in Exchange Online".

- Devi determinare come recuperare o esportare i dati dal sistema di badging fisico dell'organizzazione (su base giornaliera) e creare un file JSON descritto nel passaggio 2. Lo script eseguito nel passaggio 4 inserirà i dati nel file JSON nell'endpoint dell'API.

- Lo script di esempio eseguito nel passaggio 4 inserisce i dati fisici di badging dal file JSON all'API del connettore in modo che possano essere usati dalla soluzione di gestione dei rischi Insider. Questo script di esempio non è supportato in alcun servizio o programma di supporto standard Microsoft. Lo script di esempio è fornito così come è senza alcun tipo di garanzia. Microsoft esclude inoltre qualsiasi garanzia implicita, tra cui, senza limitazioni, tutte le garanzie implicite di commerciabilità o idoneità per uno scopo specifico. L'utente assume tutti i rischi associati all'uso o alle prestazioni dello script di esempio e della documentazione. In nessun caso Microsoft, i suoi autori o chiunque altro coinvolto nella creazione, produzione o consegna degli script è da ritenersi responsabile per qualsiasi danno eventuale (inclusi, senza limitazione alcuna, danni riguardanti profitti aziendali, interruzione di attività, perdita di informazioni aziendali o altra perdita pecuniaria) derivanti dall'utilizzo o dall'incapacità di utilizzo degli script di esempio e della documentazione, anche nel caso in cui Microsoft sia stata avvisata della possibilità di tali danni.

## <a name="step-1-create-an-app-in-azure-active-directory"></a>Passaggio 1: creare un'app in Azure Active Directory

Il primo passaggio consiste nel creare e registrare una nuova app in Azure Active Directory (Azure AD). L'app corrisponderà al connettore di badging fisico creato nel passaggio 3. La creazione di questa app consentirà ad Azure AD di autenticare la richiesta push per il payload JSON contenente dati di badging fisici. Durante la creazione di questa app Azure AD, assicurati di salvare le informazioni seguenti. Questi valori verranno utilizzati nei passaggi successivi.

- ID applicazione Azure AD (detto anche *ID app* o *ID client)*

- Segreto dell'applicazione Azure AD (detto *anche segreto client)*

- ID tenant (denominato anche *ID directory)*

Per istruzioni dettagliate sulla creazione di un'app in Azure AD, vedi [Registrare un'applicazione con la piattaforma di identità Microsoft.](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app)

## <a name="step-2-prepare-a-json-file-with-physical-badging-data"></a>Passaggio 2: Preparare un file JSON con dati di badging fisici

Il passaggio successivo consiste nel creare un file JSON contenente informazioni sui dati di accesso fisico dei dipendenti. Come spiegato nella sezione prima di iniziare, dovrai determinare come generare questo file JSON dal sistema di badging fisico dell'organizzazione.

Il file JSON deve essere conforme alla definizione dello schema richiesta dal connettore. Ecco le descrizioni delle proprietà dello schema necessarie per il file JSON:

| Proprietà | Descrizione | Tipo di dati |
|:-----------|:--------------|:------------|
|UserId|Un dipendente può avere più identità digitali tra i sistemi. L'input deve avere l'ID di Azure AD già risolto dal sistema di origine. |UPN o indirizzo di posta elettronica|
|AssetId|ID di riferimento dell'asset fisico o del punto di accesso fisico.| Stringa alfanumerica|
|AssetName|Nome descrittivo dell'asset fisico o del punto di accesso fisico.|Stringa alfanumerica|
|EventTime|Timestamp di accesso.|Data e ora, in formato UTC|
|AccessStatus|Valore di `Success` o `Failed`| Stringa|
|||

Ecco un esempio di file JSON conforme allo schema richiesto:

```json
[
    {
        "UserId":"sarad@contoso.com"
        "AssetId":"Mid-Sec-7",
        "AssetName":"Main Building 1st Floor Mid Section",
        "EventTime":"2019-07-04T01:57:49",
        "AccessStatus":"Failed",
    },
    {
        "UserId":"pilarp@contoso.com",        
        "AssetId":"Mid-Sec-7",
        "AssetName":"Main Building 1st Floor Mid Section",
        "EventTime":"2019-07-04T02:57:49",        
        "AccessStatus":"Success",
    }
]
```
Puoi anche scaricare la definizione dello schema seguente per il file JSON dalla procedura guidata quando crei il connettore di badging fisico nel passaggio 3.

```text
{
    "title" : "Physical Badging Signals",
    "description" : "Access signals from physical badging systems",
    "DataType" : {
        "description" : "Identify what is the data type for input signal",
        "type" : "string",
    },
    "type" : "object",
    "properties": {
        "UserId" : {
            "description" : "Unique identifier AAD Id resolved by the source system",
            "type" : "string",
        },
        "AssetId": {
            "description" : "Unique ID of the physical asset/access point",
            "type" : "string",
        },
        "AssetName": {
            "description" : "friendly name of the physical asset/access point",
            "type" : "string",
        },
        "EventTime" : {
            "description" : "timestamp of access",
            "type" : "string",
        },
        "AccessStatus" : {
            "description" : "what was the status of access attempt - Success/Failed",
            "type" : "string",
        },
    }
    "required" : ["UserId", "AssetId", "EventTime" "AccessStatus"]
}
```

## <a name="step-3-create-the-physical-badging-connector"></a>Passaggio 3: Creare il connettore di badging fisico

Il passaggio successivo consiste nel creare un connettore di badging fisico nel Centro conformità Microsoft 365. Dopo aver eseguito lo script nel passaggio 4, il file JSON creato nel passaggio 3 verrà elaborato e inserito nell'endpoint API configurato nel passaggio 1. In questo passaggio, assicurarsi di copiare il JobId generato quando si crea il connettore. Il JobId verrà utilizzato quando si esegue lo script.

1. Vai a [https://compliance.microsoft.com](https://compliance.microsoft.com/) e quindi fai clic su **Connettori dati** nel riquadro di spostamento sinistro.

2. Nella pagina **Connettori dati** in **Badging fisico** fare clic su **Visualizza.**

3. Nella pagina **Badging fisico** fare clic su **Aggiungi connettore.**

4. Nella pagina **Credenziali di autenticazione** eseguire le operazioni seguenti e quindi fare clic su **Avanti:**
  
   1. Digitare o incollare l'ID applicazione Azure AD per l'app Azure creata nel passaggio 1.
  
   2. Scarica lo schema di esempio per il riferimento per creare il file JSON.
  
   3. Digitare un nome univoco per il connettore di badging fisico.

5. Nella pagina **Revisione** rivedere le impostazioni e quindi fare clic su **Fine** per creare il connettore.

6. Viene visualizzata una pagina di stato che conferma la creazione del connettore. Questa pagina contiene anche l'ID processo. È possibile copiare l'ID processo da questa pagina o dalla pagina a comparsa del connettore. Questo ID processo è necessario quando si esegue lo script.

   La pagina di stato contiene anche un collegamento allo script. Fai riferimento a questo script per informazioni su come pubblicare il file JSON nell'endpoint dell'API.

7. Fare clic su **Fine**.

   Il nuovo connettore viene visualizzato nell'elenco nella **scheda Connettori.**

8. Fare clic sul connettore di badging fisico appena creato per visualizzare la pagina del riquadro a comparsa, che contiene le proprietà e altre informazioni sul connettore.

## <a name="step-4-run-the-script-to-post-your-json-file-containing-physical-badging-data"></a>Passaggio 4: Eseguire lo script per pubblicare il file JSON contenente dati di badging fisici

Il passaggio successivo nella configurazione di un connettore di badging fisico consiste nell'eseguire uno script che inserirà i dati di badging fisici nel file JSON (creato nel passaggio 2) all'endpoint API creato nel passaggio 1. Forniamo uno script di esempio per il riferimento e puoi scegliere di usarlo o creare uno script personalizzato per pubblicare il file JSON nell'endpoint dell'API.

Dopo aver eseguito lo script, il file JSON contenente i dati di badging fisici viene inserito nell'organizzazione di Microsoft 365, dove è possibile accedervi dalla soluzione di gestione dei rischi Insider. È consigliabile pubblicare i dati fisici ogni giorno. A tale scopo, automatizza il processo di generazione del file JSON ogni giorno dal sistema di badging fisico e quindi pianifica lo script per il push dei dati.

> [!NOTE]
> Il numero massimo di record nel file JSON che possono essere elaborati dall'API è 50.000 record.

1. Passare a [questo sito GitHub per](https://github.com/microsoft/m365-hrconnector-sample-scripts/blob/master/upload_termination_records.ps1) accedere allo script di esempio.

2. Fare clic **sul pulsante** Non elaborato per visualizzare lo script in visualizzazione Testo

3. Copiare tutte le righe dello script di esempio e quindi salvarle in un file di testo.

4. Modificare lo script di esempio per l'organizzazione, se necessario.

5. Salvare il file di testo come Windows PowerShell file script utilizzando il suffisso del nome file ps1. ad esempio, PhysicalBadging.ps1.

6. Aprire un prompt dei comandi nel computer locale e passare alla directory in cui è stato salvato lo script.

7. Eseguire il comando seguente per eseguire il push dei dati fisici di badging nel file JSON nel cloud Microsoft. Per esempio:

   ```powershell
   .\PhysicalBadging.ps1 -tenantId "<Tenant Id>" -appId "<Azure AD App Id>" -appSecret "<Azure AD App Secret>" -jobId "Job Id" -jsonFilePath "<records file path>"
   ```

   Nella tabella seguente vengono descritti i parametri da utilizzare con questo script e i relativi valori obbligatori. Le informazioni ottenute nei passaggi precedenti vengono utilizzate nei valori per questi parametri.

   | Parametro | Descrizione |
   |:-------------|:--------------|
   |tenantId | Questo è l'ID dell'organizzazione di Microsoft 365 ottenuta nel passaggio 1. È anche possibile ottenere il tenantId per l'organizzazione nel pannello **Panoramica** nell'interfaccia di amministrazione di Azure AD. Viene usato per identificare l'organizzazione. |
   |appId | Questo è l'ID dell'applicazione Azure AD per l'app creata in Azure AD nel passaggio 1. Viene usato da Azure AD per l'autenticazione quando lo script tenta di accedere all'organizzazione di Microsoft 365.                    |
   |appSecret | Questo è il segreto dell'applicazione Azure AD per l'app creata in Azure AD nel passaggio 1. Viene utilizzato anche per l'autenticazione.                                                        |
   |jobId | Questo è l'ID processo per il connettore di badging fisico creato nel passaggio 3. Viene usato per associare i dati fisici di badging inviati al cloud Microsoft al connettore di badging fisico.              |
   |JsonFilePath | Questo è il percorso del file nel computer locale (quello che stai usando per eseguire lo script) per il file JSON creato nel passaggio 2. Questo file deve seguire lo schema di esempio descritto nel passaggio 3.|
   |||

   Ecco un esempio della sintassi per lo script del connettore di badging fisico utilizzando i valori effettivi per ogni parametro:

   ```powershell
   .\PhysicalBadging.ps1 -tenantId d5723623-11cf-4e2e-b5a5-01d1506273g9 -appId 29ee526e-f9a7-4e98-a682-67f41bfd643e -appSecret MNubVGbcQDkGCnn -jobId b8be4a7d-e338-43eb-a69e-c513cd458eba -csvFilePath 'C:\Users\contosoadmin\Desktop\Data\physical_badging_data.json'
   ```

   Se il caricamento ha esito positivo, lo script visualizza il **messaggio Caricamento** completato.

   Se si dispone di più file JSON, è necessario eseguire lo script per ogni file.

> [!NOTE]
> Puoi anche scegliere di eseguire il push dei dati fisici di badging nell'endpoint dell'API con metodi diversi dall'esecuzione dello script precedente. Ad esempio, ecco un esempio per usare Postman per eseguire il push dei dati nell'endpoint dell'API.

## <a name="step-5-monitor-the-physical-badging-connector"></a>Passaggio 5: Monitorare il connettore di badging fisico

Dopo aver creato il connettore di badging fisico e aver push dei dati fisici, è possibile visualizzare il connettore e caricare lo stato nel Centro conformità Microsoft 365. Se si pianifica l'esecuzione automatica dello script a intervalli regolari, è inoltre possibile visualizzare lo stato corrente dopo l'ultima esecuzione dello script.

1. Andare a [https://compliance.microsoft.com](https://compliance.microsoft.com/) e fare clic su **Connettori dati** nel riquadro di spostamento sinistro.

2. Fare clic **sulla scheda Connettori** e quindi selezionare il connettore di badging fisico per visualizzare la pagina a comparsa. Questa pagina contiene le proprietà e le informazioni sul connettore.

   ![Pagina di stato del riquadro a comparsa per il connettore di badging fisico](..\media\PhysicalBadgingStatusFlyout.png)

3. In **Ultima importazione** fare clic sul collegamento Scarica **registro** per aprire (o salvare) il registro di stato per il connettore. Questo log contiene informazioni su ogni esecuzione dello script e sul caricamento dei dati dal file CSV nel cloud Microsoft.

   ![Il file di registro del connettore di badging fisico visualizza il numero di righe dal file JSON che sono state caricate](..\media\PhysicalBadgingConnectorLogFile.png)

   Il **campo RecordsSaved** indica il numero di righe nel file CSV caricato. Ad esempio, se il file CSV contiene quattro righe, il valore dei campi **RecordsSaved** è 4, se lo script ha caricato correttamente tutte le righe nel file CSV.

Se lo script non è stato eseguito nel passaggio 4, viene visualizzato un collegamento per scaricare lo script in **Ultima importazione.** È possibile scaricare lo script e quindi seguire i passaggi del passaggio 4 per eseguirlo.

## <a name="optional-step-6-schedule-the-script-to-run-automatically"></a>(Facoltativo) Passaggio 6: Pianificare l'esecuzione automatica dello script

Per assicurarsi che i dati di badging fisici più recenti dell'organizzazione siano disponibili per strumenti come la soluzione di gestione dei rischi Insider, è consigliabile pianificare l'esecuzione automatica dello script su base ricorrente, ad esempio una volta al giorno. Ciò richiede anche di aggiornare i dati fisici di badging al file JSON in base a una pianificazione simile (se non la stessa) in modo che contenga le informazioni più recenti sui dipendenti che lasciano l'organizzazione. L'obiettivo è quello di caricare i dati di badging fisici più correnti in modo che il connettore di badging fisico possa renderli disponibili per la soluzione di gestione dei rischi Insider.

Puoi usare l'app Utilità di pianificazione in Windows per eseguire automaticamente lo script ogni giorno.

1. Nel computer locale fare clic sul pulsante **Start** di Windows e quindi digitare **Utilità di pianificazione.**

2. Fare clic **sull'app Utilità** di pianificazione per aprirla.

3. Nella sezione **Azioni** fare clic su **Crea attività.**

4. Nella scheda **Generale** digitare un nome descrittivo per l'attività pianificata. ad esempio, **script del connettore di badging fisico.** È inoltre possibile aggiungere una descrizione facoltativa.

5. In **Opzioni di sicurezza** eseguire le operazioni seguenti:

   1. Determinare se eseguire lo script solo quando si è connessi al computer o se eseguirlo quando si è connessi o meno.

   2. Assicurati che la **casella di controllo Esegui con i privilegi più** elevati sia selezionata.

6. Selezionare la **scheda Trigger,** fare clic su **Nuovo** e quindi eseguire le operazioni seguenti:

   1. In **Impostazioni** selezionare l'opzione **Giornaliera** e quindi scegliere la data e l'ora in cui eseguire lo script per la prima volta. Lo script verrà eseguito ogni giorno alla stessa ora specificata.

   2. In **Impostazioni avanzate** verificare che la casella di controllo **Abilitato** sia selezionata.

   3. Fare clic su **OK**.

7. Selezionare la **scheda Azioni,** fare clic **su Nuovo** e quindi eseguire le operazioni seguenti:

   ![Impostazioni delle azioni per creare una nuova attività pianificata per lo script del connettore di badging fisico](..\media\SchedulePhysicalBadgingScript1.png)

   1. **Nell'elenco a** discesa Azione verificare che sia selezionata l'opzione **Avvia** un programma.

   2. Nella casella **Programma/script** fare clic su Sfoglia e passare al percorso seguente e selezionarlo in modo che il percorso sia visualizzato nella casella: C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe.

   3. Nella casella **Aggiungi argomenti (facoltativo)** incollare lo stesso comando script eseguito nel passaggio 4. Ad esempio, .\PhysicalBadging.ps1-tenantId "d5723623-11cf-4e2e-b5a5-01d1506273g9" -appId "c12823b7-b55a-4989-faba-02de41bb97c3" -appSecret "MNubVGbcQDkGCnn" -jobId "e081f4f4-3831-48d6-7bb3-fcfab1581458" -jsonFilePath "C:\Users\contosoadmin\Desktop\Data\physical_badging_data.csv"

   4. Nella casella **Inizia in (facoltativo)** incollare il percorso della cartella dello script eseguito nel passaggio 4. Ad esempio, C:\Utenti\contosoadmin\Desktop\Scripts.

   5. Fare **clic su OK** per salvare le impostazioni per la nuova azione.

8. Nella finestra **Crea attività** fare clic su **OK** per salvare l'attività pianificata. Potrebbe essere richiesto di immettere le credenziali dell'account utente.

   La nuova attività viene visualizzata nella libreria dell'Utilità di pianificazione.

   ![La nuova attività viene visualizzata nella libreria dell'Utilità di pianificazione](..\media\SchedulePhysicalBadgingScript2.png)

Viene visualizzata l'ora dell'ultima esecuzione dello script e la successiva esecuzione pianificata. È possibile fare doppio clic sull'attività per modificarla.

È inoltre possibile verificare l'ultima esecuzione dello script nella pagina a comparsa del connettore di badging fisico corrispondente nel Centro conformità.
