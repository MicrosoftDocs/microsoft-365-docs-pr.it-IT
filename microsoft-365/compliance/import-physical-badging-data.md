---
title: Configurare un connettore per l'importazione dei dati fisici di badging
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
description: Gli amministratori possono configurare un connettore di dati per importare i dati dal sistema fisico di badging dell'organizzazione a Microsoft 365. In questo modo è possibile utilizzare questi dati nei criteri di gestione dei rischi Insider utili per rilevare l'accesso ai propri edifici fisici da parte di utenti specifici che potrebbero indicare una possibili minacce interne all'organizzazione.
ms.openlocfilehash: 6d52879031c8801191b1a419f38a1167c1bb0688
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48204507"
---
# <a name="set-up-a-connector-to-import-physical-badging-data-preview"></a>Configurare un connettore per l'importazione dei dati fisici di badging (anteprima)

È possibile configurare un connettore di dati nel centro conformità di Microsoft 365 per importare dati fisici di badging, ad esempio gli eventi di accesso fisico RAW del dipendente o gli allarmi di accesso fisico generati dal sistema di badging dell'organizzazione. Esempi di punti di accesso fisici sono una voce di un edificio o una voce di sala server o di un Data Center. I dati fisici di badging possono essere utilizzati dalla soluzione Microsoft 365 [Insider Risk Management](insider-risk-management.md) per contribuire alla protezione dell'organizzazione da attività dannose o furti di dati all'interno dell'organizzazione.

L'impostazione di un connettore fisico di badging è costituita dalle attività seguenti:

- Creazione di un'app in Azure Active Directory (Azure AD) per accedere a un endpoint API che accetta un payload JSON contenente dati di badging fisici.

- Creazione del payload JSON con uno schema definito dal connettore dati fisico di badging.

- Creazione di un connettore dati fisico di badging nel centro conformità di Microsoft 365.

- Esecuzione di uno script per inviare i dati fisici di badging all'endpoint dell'API.

- Facoltativamente, la pianificazione dello script per l'esecuzione automatica per l'importazione dei dati di badging fisica corrente.

## <a name="before-you-set-up-the-connector"></a>Prima di configurare il connettore

- L'organizzazione deve acconsentire a consentire al servizio di importazione di Office 365 di accedere ai dati nell'organizzazione. Per acconsentire a questa richiesta, accedere a [Questa pagina](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), accedere con le credenziali di un amministratore globale di Microsoft 365 e quindi accettare la richiesta. È necessario completare questo passaggio prima che sia possibile creare correttamente il connettore fisico di badging nel passaggio 3.

- All'utente che crea il connettore fisico di badging nel passaggio 3 deve essere assegnato il ruolo di importazione/esportazione delle cassette postali in Exchange Online. Per impostazione predefinita, questo ruolo non è assegnato ad alcun gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo import export delle cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In alternativa, è possibile creare un nuovo gruppo di ruoli, assegnare il ruolo di esportazione delle cassette postali e quindi aggiungere gli utenti corretti come membri. Per ulteriori informazioni, vedere la sezione creare gruppi di [ruoli](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) o [modificare gruppi di ruoli](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) nell'articolo "gestire i gruppi di ruoli in Exchange Online".

- È necessario determinare come recuperare o esportare i dati dal sistema di badging fisico dell'organizzazione (su base giornaliera) e creare un file JSON descritto nel passaggio 2. Lo script eseguito nel passaggio 4 invierà i dati nel file JSON all'endpoint dell'API.

- Lo script di esempio eseguito nel passaggio 4 inserisce i dati fisici di badging dal file JSON all'API del connettore in modo che possa essere utilizzato dalla soluzione di gestione dei rischi Insider. Questo script di esempio non è supportato in alcun servizio o programma di supporto Microsoft standard. Lo script di esempio viene fornito come senza garanzie di alcun tipo. Microsoft esclude inoltre qualsiasi garanzia implicita, tra cui, senza limitazioni, tutte le garanzie implicite di commerciabilità o idoneità per uno scopo specifico. L'intero rischio derivante dall'utilizzo o dalle prestazioni dello script di esempio e della documentazione resta all'interno dell'utente. In nessun caso Microsoft, i suoi autori o chiunque altro coinvolto nella creazione, produzione o consegna degli script è da ritenersi responsabile per qualsiasi danno eventuale (inclusi, senza limitazione alcuna, danni riguardanti profitti aziendali, interruzione di attività, perdita di informazioni aziendali o altra perdita pecuniaria) derivanti dall'utilizzo o dall'incapacità di utilizzo degli script di esempio e della documentazione, anche nel caso in cui Microsoft sia stata avvisata della possibilità di tali danni.

## <a name="step-1-create-an-app-in-azure-active-directory"></a>Passaggio 1: creare un'app in Azure Active Directory

Il primo passaggio consiste nel creare e registrare una nuova app in Azure Active Directory (Azure AD). L'app corrisponderà al connettore badging fisico creato nel passaggio 3. La creazione di questa app consentirà ad Azure ad di autenticare la richiesta push per il payload JSON contenente dati di badging fisici. Durante la creazione di questa applicazione Azure AD, assicurarsi di salvare le informazioni seguenti. Questi valori verranno utilizzati nei passaggi successivi.

- ID applicazione Azure AD (denominato anche ID *app* o *ID client*)

- Segreto dell'applicazione Azure AD (denominato anche *segreto client*)

- ID tenant (denominato anche *ID directory*)

Per istruzioni dettagliate per la creazione di un'app in Azure AD, vedere registrazione di [un'applicazione con la piattaforma Microsoft Identity](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).

## <a name="step-2-prepare-a-json-file-with-physical-badging-data"></a>Passaggio 2: preparare un file JSON con dati badging fisici

Il passaggio successivo consiste nel creare un file JSON contenente informazioni sui dati di accesso fisico dei dipendenti. Come illustrato nella sezione prima di iniziare, è necessario determinare come generare questo file JSON dal sistema di badging fisico dell'organizzazione.

Il file JSON deve essere conforme alla definizione dello schema richiesta dal connettore. Di seguito sono riportate le descrizioni delle proprietà dello schema necessarie per il file JSON:

|**Proprietà**|**Descrizione**|**Data type**|
|:-----------|:--------------|:------------|
|UserId|Un dipendente può disporre di più identità digitali nei sistemi. Per l'input è necessario che l'ID di Azure AD sia già stato risolto dal sistema di origine. |UPN o indirizzo di posta elettronica|
|AssetId|ID di riferimento del cespite fisico o del punto di accesso fisico.| Stringa alfanumerica|
|AssetName|Nome descrittivo del cespite fisico o del punto di accesso fisico.|Stringa alfanumerica|
|EventTime|Indicatore di data e ora di accesso.|Data e ora, in formato UTC|
|AccessStatus|Valore di `Success` o `Failed`| Stringa|
|||

Di seguito è riportato un esempio di file JSON conforme allo schema obbligatorio:

```text
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
È inoltre possibile scaricare la seguente definizione di schema per il file JSON dalla procedura guidata quando si crea il connettore fisico di badging nel passaggio 3.

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

## <a name="step-3-create-the-physical-badging-connector"></a>Passaggio 3: creare il connettore badging fisico

Il passaggio successivo consiste nel creare un connettore fisico di badging nel centro conformità di Microsoft 365. Dopo aver eseguito lo script nel passaggio 4, il file JSON creato nel passaggio 3 verrà elaborato e spinto all'endpoint API configurato nel passaggio 1. In questo passaggio, assicurarsi di copiare il JobId generato quando si crea il connettore. Quando si esegue lo script, si utilizzerà il JobId.

1. Andare a [https://compliance.microsoft.com](https://compliance.microsoft.com/) e quindi fare clic su **connettori dati** nel NAV sinistro.

2. Nella pagina **connettori dati** in **badging fisica**fare clic su **Visualizza**.

3. Nella pagina **badging fisica** fare clic su **Aggiungi connettore**.

4. Nella pagina **credenziali di autenticazione** eseguire le operazioni seguenti e quindi fare clic su **Avanti**:
  
   1. Digitare o incollare l'ID dell'applicazione Azure AD per l'app Azure creata al passaggio 1.
  
   2. Scaricare lo schema di esempio per il riferimento per creare il file JSON.
  
   3. Digitare un nome univoco per il connettore fisico di badging.

5. Nella pagina **Revisione** rivedere le impostazioni e quindi fare clic su **fine** per creare il connettore.

6. Viene visualizzata una pagina di stato che conferma che il connettore è stato creato. Questa pagina contiene anche l'ID del processo. È possibile copiare l'ID processo da questa pagina o dalla pagina a comparsa del connettore. Quando si esegue lo script, è necessario l'ID del processo.

   La pagina stato contiene anche un collegamento allo script. Fare riferimento a questo script per comprendere come inviare il file JSON all'endpoint dell'API.

7. Fare clic su **Fine**.

   Il nuovo connettore viene visualizzato nell'elenco della scheda **connettori** .

8. Fare clic sul connettore badging fisico appena creato per visualizzare la pagina del riquadro a comparsa, che contiene le proprietà e altre informazioni sul connettore.

## <a name="step-4-run-the-script-to-post-your-json-file-containing-physical-badging-data"></a>Passaggio 4: eseguire lo script per inserire il file JSON contenente dati badging fisici

Il passaggio successivo nella configurazione di un connettore badging fisico consiste nell'eseguire uno script che spingerà i dati fisici di badging nel file JSON (creato nel passaggio 2) all'endpoint API creato nel passaggio 1. Viene fornito uno script di esempio per il riferimento e è possibile scegliere di utilizzarlo o creare uno script personalizzato per inviare il file JSON all'endpoint dell'API.

Dopo aver eseguito lo script, il file JSON contenente i dati fisici di badging viene inserito nell'organizzazione Microsoft 365, dove può accedere tramite la soluzione di gestione dei rischi Insider. Si consiglia di inviare giornalmente i dati di badging fisica. A tale scopo, è possibile automatizzare il processo per generare il file JSON ogni giorno dal sistema fisico di badging e quindi programmare lo script per inviare i dati.

> [!NOTE]
> Il numero massimo di record nel file JSON che possono essere elaborati dall'API è 50.000 record.

1. Passare a [questo sito GitHub](https://github.com/microsoft/m365-hrconnector-sample-scripts/blob/master/upload_termination_records.ps1) per accedere allo script di esempio.

2. Fare clic sul pulsante **RAW** per visualizzare lo script nella visualizzazione testo

3. Copiare tutte le righe nello script di esempio e quindi salvarle in un file di testo.

4. Modificare lo script di esempio per l'organizzazione, se necessario.

5. Salvare il file di testo come file di script di Windows PowerShell utilizzando un suffisso FileName di. ps1. ad esempio, PhysicalBadging.ps1.

6. Aprire un prompt dei comandi nel computer locale e passare alla directory in cui è stato salvato lo script.

7. Eseguire il seguente comando per inserire i dati fisici di badging nel file JSON nel cloud Microsoft. Per esempio:

   ```powershell
   .\PhysicalBadging.ps1 -tenantId "<Tenant Id>" -appId "<Azure AD App Id>" -appSecret "<Azure AD App Secret>" -jobId "Job Id" -jsonFilePath "<records file path>"
   ```

   Nella tabella seguente vengono descritti i parametri da utilizzare con questo script e i valori necessari. Le informazioni ottenute nei passaggi precedenti vengono utilizzate nei valori di questi parametri.

   | **Parametro**|**Descrizione**|
   |:-------------|:--------------|
   |tenantId | Questo è l'ID dell'organizzazione Microsoft 365 ottenuta al passaggio 1. È anche possibile ottenere l'tenantId per l'organizzazione nel pannello **Panoramica** nell'interfaccia di amministrazione di Azure ad. Viene utilizzato per identificare l'organizzazione. |
   |appId | Questo è l'ID dell'applicazione Azure AD per l'app creata in Azure AD nel passaggio 1. Questo metodo viene utilizzato da Azure AD per l'autenticazione quando lo script tenta di accedere all'organizzazione Microsoft 365.                    |
   |appSecret | Questo è il segreto dell'applicazione Azure AD per l'app creata in Azure AD nel passaggio 1. Questa operazione viene utilizzata anche per l'autenticazione.                                                        |
   |jobId | Questo è l'ID processo per il connettore badging fisico creato nel passaggio 3. Viene utilizzato per associare i dati fisici di badging che vengono inseriti nel cloud Microsoft con il connettore badging fisico.              |
   |JsonFilePath | Si tratta del percorso del file nel computer locale (quello utilizzato per eseguire lo script) per il file JSON creato nel passaggio 2. Questo file deve seguire lo schema di esempio descritto nel passaggio 3.|
   |||

   Di seguito è riportato un esempio della sintassi per lo script fisico del connettore di badging con i valori effettivi di ogni parametro:

   ```powershell
   .\PhysicalBadging.ps1 -tenantId d5723623-11cf-4e2e-b5a5-01d1506273g9 -appId 29ee526e-f9a7-4e98-a682-67f41bfd643e -appSecret MNubVGbcQDkGCnn -jobId b8be4a7d-e338-43eb-a69e-c513cd458eba -csvFilePath 'C:\Users\contosoadmin\Desktop\Data\physical_badging_data.json'
   ```

   Se il caricamento ha esito positivo, lo script Visualizza il messaggio di **caricamento con esito positivo** .

   Se si dispone di più file JSON, è necessario eseguire lo script per ogni file.

> [!NOTE]
> È inoltre possibile scegliere di inviare i dati fisici di badging all'endpoint dell'API tramite metodi diversi dall'esecuzione dello script precedente. Ad esempio, di seguito è riportato un esempio che consente di utilizzare il postino per inviare i dati all'endpoint dell'API.

## <a name="step-5-monitor-the-physical-badging-connector"></a>Passaggio 5: monitorare il connettore fisico di badging

Dopo aver creato il connettore fisico di badging e aver premuto i dati di badging fisici, è possibile visualizzare lo stato del connettore e del caricamento nel centro conformità di Microsoft 365. Se si pianifica lo script in modo che venga eseguito automaticamente periodicamente, è possibile visualizzare lo stato corrente anche dopo l'ultima esecuzione dello script.

1. Andare a [https://compliance.microsoft.com](https://compliance.microsoft.com/) e fare clic su **connettori dati** nel NAV sinistro.

2. Fare clic sulla scheda **connettori** e quindi selezionare il connettore badging fisico per visualizzare la pagina del riquadro a comparsa, che contiene le proprietà e le informazioni sul connettore.

   ![Pagina del riquadro a comparsa di stato per il connettore badging fisico](..\media\PhysicalBadgingStatusFlyout.png)

3. In **Ultima importazione**fare clic sul collegamento **download log** per aprire o salvare il registro di stato del connettore. Questo log contiene informazioni su ogni volta che lo script viene eseguito e carica i dati dal file CSV al cloud Microsoft.

   ![Il file di registro del connettore di badging fisico Visualizza le righe di numero da file JSON che sono stati caricati](..\media\PhysicalBadgingConnectorLogFile.png)

   Il campo **RecordsSaved** indica il numero di righe nel file CSV che è stato caricato. Ad esempio, se il file CSV contiene quattro righe, il valore dei campi **RecordsSaved** è 4, se lo script ha correttamente caricato tutte le righe del file CSV.

Se non è stato eseguito lo script nel passaggio 4, viene visualizzato un collegamento per scaricare lo script nell' **Ultima importazione**. È possibile scaricare lo script e quindi seguire i passaggi descritti nel passaggio 4 per eseguirlo.

## <a name="optional-step-6-schedule-the-script-to-run-automatically"></a>Optional Passaggio 6: pianificare l'esecuzione automatica dello script

Per assicurarsi che i dati di badging fisici più recenti dell'organizzazione siano disponibili per gli strumenti come la soluzione di gestione dei rischi Insider, è consigliabile pianificare lo script in modo che venga eseguito automaticamente su base ricorrente, ad esempio una volta al giorno. Questo richiede anche l'aggiornamento dei dati fisici di badging nel file JSON su una pianificazione analoga (se non uguale), in modo che contenga le informazioni più aggiornate sui dipendenti che lasciano l'organizzazione. L'obiettivo è quello di caricare i dati di badging fisici più recenti in modo che il connettore badging fisico possa renderlo disponibile per la soluzione di gestione dei rischi Insider.

È possibile utilizzare l'app utilità di pianificazione in Windows per eseguire automaticamente lo script ogni giorno.

1. Nel computer locale, fare clic sul pulsante **Start** di Windows e quindi digitare **utilità di pianificazione**.

2. Fare clic sull'app **utilità di pianificazione** per aprirla.

3. Nella sezione **azioni** fare clic su **Crea attività**.

4. Nella scheda **generale** Digitare un nome descrittivo per l'attività pianificata. ad esempio, **script del connettore badging fisico**. È inoltre possibile aggiungere una descrizione facoltativa.

5. In **Opzioni di sicurezza**eseguire le operazioni seguenti:

   1. Determinare se eseguire lo script solo quando si è connessi al computer o quando si è connessi o meno.

   2. Verificare che sia selezionata la casella **di controllo Esegui con i privilegi più alti** .

6. Selezionare la scheda **trigger** , fare clic su **nuovo**e quindi eseguire le operazioni seguenti:

   1. In **Impostazioni**, selezionare l'opzione **giornaliero** e quindi scegliere una data e un'ora per l'esecuzione dello script per la prima volta. Lo script viene applicato ogni giorno allo stesso tempo specificato.

   2. In **Impostazioni avanzate**verificare che sia selezionata la casella di controllo **abilitata** .

   3. Fare clic su **OK**.

7. Selezionare la scheda **azioni** , fare clic su **nuovo**e quindi eseguire le operazioni seguenti:

   ![Impostazioni azione per creare una nuova attività pianificata per lo script del connettore badging fisico](..\media\SchedulePhysicalBadgingScript1.png)

   1. Nell'elenco a discesa **azione** , verificare che sia selezionata l'opzione **avvia un programma** .

   2. Nella casella **programma/script** fare clic su **Sfoglia**e passare al percorso seguente e selezionarlo in modo che il percorso venga visualizzato nella casella: C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe.

   3. Nella casella **Add arguments (optional)** incollare lo stesso comando script eseguito nel passaggio 4. Ad esempio, .\PhysicalBadging.ps1-tenantId "d5723623-11CF-4E2E-b5a5-01d1506273g9"-appId "c12823b7-B55A-4989-FABA-02de41bb97c3"-appSecret "MNubVGbcQDkGCnn"-jobId "e081f4f4-3831-48D6-7bb3-fcfab1581458"-jsonFilePath "C:\Users\contosoadmin\Desktop\Data\physical_badging_data.csv"

   4. Nella casella **inizia in (facoltativo)** incollare il percorso della cartella dello script eseguito nel passaggio 4. Ad esempio, C:\Users\contosoadmin\Desktop\Scripts.

   5. Fare clic su **OK** per salvare le impostazioni per la nuova azione.

8. Nella finestra **Crea attività** fare clic su **OK** per salvare l'attività pianificata. Potrebbe essere richiesto di immettere le credenziali dell'account utente.

   La nuova attività viene visualizzata nella libreria dell'utilità di pianificazione.

   ![La nuova attività viene visualizzata nella raccolta di utilità di pianificazione](..\media\SchedulePhysicalBadgingScript2.png)

L'ultima volta che lo script è stato eseguito e la volta successiva che viene pianificata l'esecuzione viene visualizzata. È possibile fare doppio clic sull'attività per modificarla.

È inoltre possibile verificare l'ultima volta che lo script è stato eseguito nella pagina a comparsa del connettore badging fisico corrispondente nel centro conformità.
