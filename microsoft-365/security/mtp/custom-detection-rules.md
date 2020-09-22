---
title: Creare e gestire le regole di rilevamento personalizzate in Microsoft Threat Protection
description: Informazioni su come creare e gestire le regole per i rilevamenti personalizzati in base alle query di ricerca avanzate
keywords: caccia avanzata, caccia alle minacce, Cyber-caccia alle minacce, Microsoft Threat Protection, Microsoft 365, MTP, M365, ricerca, query, telemetria, rilevamenti personalizzati, regole, schema, kusto, Microsoft 365, Microsoft Threat Protection, RBAC, autorizzazioni, Microsoft Defender ATP
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: e3388bd0d3a7ac6afff0109eb80945d3ddc362fd
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198898"
---
# <a name="create-and-manage-custom-detections-rules"></a>Creare e gestire le regole per i rilevamenti personalizzati

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft Threat Protection

Le regole di rilevamento personalizzate sono regole che è possibile progettare e modificare utilizzando query di [caccia avanzate](advanced-hunting-overview.md) . Queste regole consentono di monitorare in modo proattivo vari eventi e Stati del sistema, tra cui l'attività di violazione sospetta e gli endpoint non configurati correttamente. È possibile impostare gli avvisi e le azioni di risposta ogni volta che si verificano delle corrispondenze.

## <a name="required-permissions-for-managing-custom-detections"></a>Autorizzazioni necessarie per la gestione dei rilevamenti personalizzati

Per gestire i rilevamenti personalizzati, è necessario essere assegnati a uno di questi ruoli:

- **Amministratore della sicurezza**: gli utenti che dispongono di questo [ruolo di Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) possono gestire le impostazioni di sicurezza in Microsoft 365 Security Center e in altri portali e servizi.

- **Operatore di sicurezza**: gli utenti che dispongono di questo [ruolo di Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) possono gestire gli avvisi e dispongono dell'accesso globale in sola lettura alle funzionalità relative alla sicurezza, incluse tutte le informazioni disponibili in Microsoft 365 Security Center. Questo ruolo è sufficiente per la gestione dei rilevamenti personalizzati solo se il controllo di accesso basato sui ruoli (RBAC) è disattivato in Microsoft Defender ATP. Se sono stati configurati RBAC, è necessaria anche l'autorizzazione **Gestisci impostazioni di sicurezza** per Microsoft Defender ATP.

Per gestire le autorizzazioni necessarie, un **amministratore globale** può:

- Assegnare l' **amministratore della sicurezza** o il ruolo di **operatore di sicurezza** nell'interfaccia di amministrazione di [Microsoft 365](https://admin.microsoft.com/) in **roles**  >  **Security admin**.
- Controllare le impostazioni di RBAC per Microsoft Defender ATP in [Microsoft Defender Security Center](https://securitycenter.windows.com/) in **Settings**  >  **Permissions**  >  **roles**. Selezionare il ruolo corrispondente per assegnare l'autorizzazione **Gestisci impostazioni di sicurezza** .

> [!NOTE]
> Per gestire i rilevamenti personalizzati, **gli operatori di sicurezza** avranno bisogno dell'autorizzazione **Gestisci impostazioni di sicurezza** in Microsoft Defender ATP se RBAC è attivato.

## <a name="create-a-custom-detection-rule"></a>Creare una regola di rilevamento personalizzata
### <a name="1-prepare-the-query"></a>1. preparare la query.

In Microsoft 365 Security Center, andare a **ricerca avanzata** e selezionare una query esistente o creare una nuova query. Quando si utilizza una nuova query, eseguire la query per identificare gli errori e comprendere i possibili risultati.

>[!IMPORTANT]
>Per evitare che il servizio restituisca troppi avvisi, ogni regola è limitata alla generazione di soli 100 avvisi ogni volta che viene eseguita. Prima di creare una regola, modificare la query per evitare di ricevere avvisi per attività quotidiane normali.


#### <a name="required-columns-in-the-query-results"></a>Colonne obbligatorie nei risultati della query
Per creare una regola di rilevamento personalizzata, è necessario che la query restituisca le colonne seguenti:

- `Timestamp`-utilizzato per impostare il timestamp per gli avvisi generati
- `ReportId`-consente di abilitare le ricerche per i record originali
- Una delle colonne seguenti che identificano i dispositivi, gli utenti o le cassette postali specifici:
    - `DeviceId`
    - `DeviceName`
    - `RemoteDeviceName`
    - `RecipientEmailAddress`
    - `SenderFromAddress` (mittente busta o indirizzo del percorso restituito)
    - `SenderMailFromAddress` (indirizzo mittente visualizzato dal client di posta elettronica)
    - `RecipientObjectId`
    - `AccountObjectId`
    - `AccountSid`
    - `AccountUpn`
    - `InitiatingProcessAccountSid`
    - `InitiatingProcessAccountUpn`
    - `InitiatingProcessAccountObjectId`

>[!NOTE]
>Il supporto per altre entità verrà aggiunto quando vengono aggiunte nuove tabelle allo [schema di caccia avanzato](advanced-hunting-schema-tables.md).

Query semplici, ad esempio quelle che non utilizzano l' `project` `summarize` operatore OR per personalizzare o aggregare i risultati, generalmente restituiscono queste colonne comuni.

Sono disponibili vari modi per garantire che le query più complesse restituiscano queste colonne. Ad esempio, se si preferisce aggregare e contare per entità in una colonna come `DeviceId` , è comunque possibile restituire `Timestamp` e `ReportId` ottenere dall'evento più recente che coinvolgono ogni Unique `DeviceId` .

La query di esempio seguente conta il numero di dispositivi univoci ( `DeviceId` ) con rilevamenti antivirus e utilizza questo conteggio per trovare solo i dispositivi con più di cinque rilevamenti. Per restituire l'ultima `Timestamp` e la corrispondente `ReportId` , viene utilizzato l' `summarize` operatore con la `arg_max` funzione.

```kusto
DeviceEvents
| where Timestamp > ago(1d)
| where ActionType == "AntivirusDetection"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| where count_ > 5
```

> [!TIP]
> Per migliorare le prestazioni delle query, impostare un filtro temporale che corrisponda alla frequenza di esecuzione desiderata per la regola. Poiché l'esecuzione meno frequente è _ogni 24 ore_, il filtro per il giorno precedente riguarderà tutti i nuovi dati.

### <a name="2-create-new-rule-and-provide-alert-details"></a>2. creare una nuova regola e fornire informazioni dettagliate sugli avvisi.

Con la query nell'editor di query, selezionare **Crea regola di rilevamento** e specificare gli avvisi seguenti:

- **Nome del rilevamento**-nome della regola di rilevamento
- **Frequenza**: intervallo per l'esecuzione della query e l'azione. [Per ulteriori informazioni, vedere](#rule-frequency)
- **Titolo avviso**-titolo visualizzato con gli avvisi attivati dalla regola
- **Severity**-potenziale rischio del componente o dell'attività identificata dalla regola
- **Categoria**-componente di minaccia o attività identificata dalla regola
- **Mitre att&tecniche CK**: una o più tecniche di attacco identificate dalla regola come documentate nel [Framework di Mitre att&CK](https://attack.mitre.org/). Questa sezione è nascosta per alcune categorie di avviso, tra cui malware, ransomware, attività sospette e software indesiderato
- **Descrizione**: altre informazioni sul componente o l'attività identificata dalla regola 
- **Azioni consigliate**: azioni aggiuntive che i risponditori potrebbero prendere in risposta a un avviso

#### <a name="rule-frequency"></a>Frequenza delle regole
Quando si salva o si modifica una nuova regola, viene eseguito e vengono verificate le corrispondenze degli ultimi 30 giorni di dati. La regola viene quindi eseguita di nuovo a intervalli fissi, applicando una durata lookback in base alla frequenza scelta:

- **Ogni 24 ore**: viene eseguito ogni 24 ore, controllando i dati degli ultimi 30 giorni.
- **Ogni 12 ore**: viene eseguito ogni 12 ore, controllando i dati delle ultime 24 ore.
- **Ogni 3 ore**: viene eseguito ogni 3 ore, controllando i dati delle ultime 6 ore.
- **Ogni ora**: viene eseguito ogni ora, controllando i dati delle ultime 2 ore.

>[!TIP]
> Corrispondono ai filtri temporali della query con la durata di lookback. I risultati al di fuori della durata di lookback vengono ignorati.  

Selezionare la frequenza corrispondente alla misura in cui si desidera monitorare i rilevamenti. Si consideri la capacità dell'organizzazione di rispondere agli avvisi.

### <a name="3-choose-the-impacted-entities"></a>3. scegliere le entità interessate.
Identificare le colonne nei risultati della query in cui si prevede di trovare l'entità interessata o con l'impatto principale. Ad esempio, una query potrebbe restituire `SenderFromAddress` gli indirizzi mittente (o `SenderMailFromAddress` ) e destinatario ( `RecipientEmailAddress` ). Identificare quali di queste colonne rappresentano la principale entità interessata aiuta gli avvisi rilevanti di aggregazione del servizio, la correlazione degli incidenti e le azioni di risposta di destinazione.

È possibile selezionare una sola colonna per ogni tipo di entità (cassetta postale, utente o dispositivo). Le colonne non restituite dalla query non possono essere selezionate.

### <a name="4-specify-actions"></a>4. specificare le azioni.
La regola di rilevamento personalizzata può eseguire automaticamente azioni su dispositivi, file o utenti restituiti dalla query.

#### <a name="actions-on-devices"></a>Azioni sui dispositivi
Queste azioni vengono applicate ai dispositivi nella `DeviceId` colonna dei risultati della query:
- **Isolate Device**-utilizza Microsoft Defender ATP per applicare l'isolamento completo della rete, impedendo al dispositivo di connettersi a qualsiasi applicazione o servizio. [Altre informazioni sull'isolamento del computer ATP Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-devices-from-the-network)
- **Raccolta del pacchetto di analisi**: raccoglie le informazioni sui dispositivi in un file zip. [Per ulteriori informazioni, vedere il pacchetto di analisi ATP Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices)
- **Run Antivirus Scan**: esegue un'analisi completa di Windows Defender antivirus sul dispositivo
- **Avviare un'analisi**: consente di avviare un' [analisi automatizzata](mtp-autoir.md) sul dispositivo
- **Limitazione dell'esecuzione delle app**: consente di impostare restrizioni sul dispositivo per consentire l'esecuzione di solo i file firmati con un certificato rilasciato da Microsoft. [Per ulteriori informazioni sulle restrizioni delle app con Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#restrict-app-execution)

#### <a name="actions-on-files"></a>Azioni sui file
Se si seleziona questa opzione, è possibile scegliere di applicare l'azione **file di quarantena** sui file nella `SHA1` colonna,, `InitiatingProcessSHA1` `SHA256` o `InitiatingProcessSHA256` dei risultati della query. Questa azione consente di eliminare il file dal percorso corrente e di collocarne una copia in quarantena.

#### <a name="actions-on-users"></a>Azioni sugli utenti
Se si seleziona questa opzione, l' **utente Contrassegno come azione compromessa** viene utilizzato per gli utenti nella `AccountObjectId` `InitiatingProcessAccountObjectId` colonna, o `RecipientObjectId` dei risultati della query. Questa azione imposta il livello di rischio degli utenti su "High" in Azure Active Directory, attivando i [criteri di protezione dell'identità](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection)corrispondenti.

> [!NOTE]
> L'azione Consenti o blocca per le regole di rilevamento personalizzate non è attualmente supportata su Microsoft Threat Protection.

### <a name="5-set-the-rule-scope"></a>5. impostare l'ambito della regola.
Impostare l'ambito per specificare quali dispositivi sono coperti dalla regola. L'ambito influenza le regole che controllano i dispositivi e non influisce sulle regole che controllano solo le cassette postali e gli account utente o le identità.

Quando si imposta l'ambito, è possibile selezionare:

- Tutti i dispositivi
- Gruppi di dispositivi specifici

Verrà eseguita una query solo sui dati dei dispositivi nell'ambito. Inoltre, le azioni verranno eseguite solo su tali dispositivi.

### <a name="6-review-and-turn-on-the-rule"></a>6. rivedere e accendere la regola.
Dopo aver esaminato la regola, fare clic su **Crea** per salvarla. Viene eseguita immediatamente la regola di rilevamento personalizzata. Viene eseguito di nuovo in base alla frequenza configurata per verificare la corrispondenza, generare avvisi e prendere le azioni di risposta.

## <a name="manage-existing-custom-detection-rules"></a>Gestire le regole di rilevamento personalizzate esistenti
È possibile visualizzare l'elenco delle regole di rilevamento personalizzate esistenti, verificare le relative esecuzioni precedenti ed esaminare gli avvisi che sono stati attivati. È inoltre possibile eseguire una regola su richiesta e modificarla.

### <a name="view-existing-rules"></a>Visualizzazione delle regole esistenti

Per visualizzare tutte le regole di rilevamento personalizzate esistenti, **passare a ricerca**di  >  **rilevamenti personalizzati**. Nella pagina sono elencate tutte le regole con le seguenti informazioni di esecuzione:

- **Ultima esecuzione**: quando è stata eseguita l'ultima esecuzione di una regola per verificare la corrispondenza di query e generare avvisi
- **Stato ultima esecuzione**-se una regola ha avuto esito positivo
- **Esecuzione successiva**: la successiva esecuzione pianificata
- **Stato**: se una regola è stata attivata o disattivata

### <a name="view-rule-details-modify-rule-and-run-rule"></a>Visualizzare i dettagli delle regole, modificare la regola e eseguire la regola

Per visualizzare informazioni complete su una regola di rilevamento personalizzata, andare alla **ricerca**di  >  **rilevamenti personalizzati** e quindi selezionare il nome della regola. È quindi possibile visualizzare le informazioni generali sulla regola, incluse le informazioni relative allo stato e all'ambito di esecuzione. La pagina fornisce anche l'elenco degli avvisi e delle azioni attivati.

![Pagina dei dettagli delle regole di rilevamento personalizzate](../../media/custom-detection-details.png)<br>
*Dettagli sulle regole di rilevamento personalizzate*

È inoltre possibile eseguire le azioni seguenti sulla regola da questa pagina:

- **Esegui**-eseguire immediatamente la regola. Questo reimposta anche l'intervallo per la successiva esecuzione.
- **Modifica**: consente di modificare la regola senza modificare la query
- **Modify query**-modificare la query in Advanced Hunting
- **Attiva**  /  **Disattiva**: attiva la regola o Interrompi l'esecuzione
- **Elimina (Delete**)-disattiva la regola e rimuovila

### <a name="view-and-manage-triggered-alerts"></a>Visualizzare e gestire gli avvisi attivati

Nella schermata Dettagli regola (**caccia**ai  >  **rilevamenti personalizzati**  >  **[nome regola]**), andare a **avvisi attivati**, in cui sono elencati gli avvisi generati dalle corrispondenze alla regola. Selezionare un avviso per visualizzare informazioni dettagliate su di esso e intraprendere le azioni seguenti:

- Gestire l'avviso impostando lo stato e la classificazione (avviso vero o falso)
- Collegare l'avviso a un evento imprevisto
- Eseguire la query che ha attivato l'avviso per la ricerca avanzata

### <a name="review-actions"></a>Esaminare le azioni
Nella schermata Dettagli regola (**caccia**ai  >  **rilevamenti personalizzati**  >  **[nome regola]**), andare a **azioni attivate**, in cui sono elencate le azioni eseguite in base alle corrispondenze alla regola.

>[!TIP]
>Per visualizzare rapidamente le informazioni e intervenire su un elemento di una tabella, utilizzare la colonna di selezione [&#10003;] a sinistra della tabella.

## <a name="related-topic"></a>Argomento correlato
- [Panoramica dei rilevamenti personalizzati](custom-detections-overview.md)
- [Panoramica della ricerca avanzata](advanced-hunting-overview.md)
- [Scoprire il linguaggio delle query in Ricerca avanzata](advanced-hunting-query-language.md)
