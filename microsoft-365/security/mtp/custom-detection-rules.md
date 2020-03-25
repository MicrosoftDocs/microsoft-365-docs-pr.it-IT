---
title: Creare e gestire le regole di rilevamento personalizzate in Microsoft Threat Protection
description: Informazioni su come creare e gestire le regole per i rilevamenti personalizzati in base alle query di ricerca avanzate
keywords: caccia avanzata, caccia alle minacce, Cyber Threat Hunting, Microsoft Threat Protection, Microsoft 365, MTP, M365, Search, query, telemetria, rilevamenti personalizzati, regole, schema, kusto, Microsoft 365, Microsoft Threat Protection, RBAC, Permissions, Microsoft ATP difensore
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
ms.openlocfilehash: adb8c7dfa0050ef2eb0d59e1e55d07da7aaa3f39
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2020
ms.locfileid: "42931741"
---
# <a name="create-and-manage-custom-detections-rules"></a>Creare e gestire le regole per i rilevamenti personalizzati

**Si applica a:**
- Microsoft Threat Protection

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Le regole di rilevamento personalizzate create con le query di [ricerca avanzata](advanced-hunting-overview.md) consentono di monitorare in modo proattivo vari eventi e Stati del sistema, tra cui l'attività di violazione sospetta e gli endpoint non configurati correttamente. È possibile impostare gli avvisi e le azioni di risposta ogni volta che si verificano delle corrispondenze.

## <a name="required-permissions-for-managing-custom-detections"></a>Autorizzazioni necessarie per la gestione dei rilevamenti personalizzati

Per gestire i rilevamenti personalizzati, è necessario essere assegnati a uno di questi ruoli:

- **Amministratore della sicurezza** : l'amministratore della sicurezza o il ruolo di amministratore della sicurezza è un [ruolo di Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) per la gestione di varie impostazioni di sicurezza in Microsoft 365 Security Center e vari portali e servizi.

- **Operatore di sicurezza** : il ruolo Operatore di sicurezza è un [ruolo di Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) per la gestione degli avvisi e dispone dell'accesso globale in sola lettura sulle funzionalità relative alla sicurezza, incluse tutte le informazioni disponibili in Microsoft 365 Security Center. Questo ruolo è sufficiente per la gestione dei rilevamenti personalizzati solo se il controllo di accesso basato sui ruoli (RBAC) è disattivato in Microsoft Defender ATP. Se sono stati configurati RBAC, è necessaria anche l'autorizzazione **Gestisci impostazioni di sicurezza** per Microsoft Defender ATP.

Per gestire le autorizzazioni necessarie, un **amministratore globale** può eseguire le operazioni seguenti:

- Assegnare l' **amministratore della sicurezza** o il ruolo di **operatore di sicurezza** nell'interfaccia di amministrazione di [Microsoft 365](https://admin.microsoft.com/) in **roles** > **Security admin**.
- Controllare le impostazioni di RBAC per Microsoft Defender ATP in [Microsoft Defender Security Center](https://securitycenter.windows.com/) in **Settings** > **Permissions** > **roles**. Selezionare il ruolo corrispondente per assegnare l'autorizzazione **Gestisci impostazioni di sicurezza** .

> [!NOTE]
> Per gestire i rilevamenti personalizzati, **gli operatori di sicurezza** avranno bisogno dell'autorizzazione **Gestisci impostazioni di sicurezza** in Microsoft Defender ATP se RBAC è attivato.

## <a name="create-a-custom-detection-rule"></a>Creare una regola di rilevamento personalizzata
### <a name="1-prepare-the-query"></a>1. preparare la query.

In Microsoft 365 Security Center, andare a **ricerca avanzata** e selezionare una query esistente o creare una nuova query. Quando si utilizza una nuova query, eseguire la query per identificare gli errori e comprendere i possibili risultati.

#### <a name="required-columns-in-the-query-results"></a>Colonne obbligatorie nei risultati della query
Per creare una regola di rilevamento personalizzata, è necessario che la query restituisca le colonne seguenti:

- `Timestamp`
- Una delle colonne del dispositivo, dell'utente o della cassetta postale seguenti:
    - `DeviceId`
    - `DeviceName`
    - `RemoteDeviceName`
    - `RecipientEmailAddress`
    - `SenderFromAddress`(mittente busta o indirizzo del percorso restituito)
    - `SenderMailFromAddress`(indirizzo mittente visualizzato dal client di posta elettronica)
    - `RecipientObjectId`
    - `AccountSid`
    - `InitiatingProcessAccountSid`
    - `InitiatingProcessAccountUpn`
    - `InitiatingProcessAccountObjectId`
>[!NOTE]
>Il supporto per altre entità verrà aggiunto quando vengono aggiunte nuove tabelle allo [schema di caccia avanzato](advanced-hunting-schema-tables.md).

Query semplici, ad esempio quelle che non utilizzano l' `project` operatore `summarize` or per personalizzare o aggregare i risultati, generalmente restituiscono queste colonne comuni.

Sono disponibili vari modi per garantire che le query più complesse restituiscano queste colonne. Ad esempio, se si preferisce aggregare e contare per entità in una colonna come `DeviceId`, è comunque possibile restituire `Timestamp` ottenendolo dall'evento più recente che coinvolge ogni Unique. `DeviceId`

La query di esempio seguente conta il numero di computer univoci (`DeviceId`) con rilevamenti antivirus e utilizza questo conteggio per trovare solo i computer con più di cinque rilevamenti. Per restituire la versione `Timestamp`più recente, viene `summarize` utilizzato l'operatore `arg_max` con la funzione.

```kusto
DeviceEvents
| where Timestamp > ago(7d)
| where ActionType == "AntivirusDetection"
| summarize Timestamp = max(Timestamp), count() by DeviceId
| where count_ > 5
```
### <a name="2-create-new-rule-and-provide-alert-details"></a>2. creare una nuova regola e fornire informazioni dettagliate sugli avvisi.

Con la query nell'editor di query, selezionare **Crea regola di rilevamento** e specificare gli avvisi seguenti:

- **Nome del rilevamento** -nome della regola di rilevamento
- **Frequenza** : intervallo per l'esecuzione della query e l'azione. [Per ulteriori informazioni, vedere](#rule-frequency)
- **Titolo avviso** -titolo visualizzato con gli avvisi attivati dalla regola
- **Severity** -potenziale rischio del componente o dell'attività identificata dalla regola
- **Categoria** -componente di minaccia o attività identificata dalla regola
- **Mitre att&le tecniche CK** -una o più tecniche di attacco identificate dalla regola come documentate nel [&CK Framework di Mitra](https://attack.mitre.org/)
- **Descrizione** : altre informazioni sul componente o l'attività identificata dalla regola 
- **Azioni consigliate** : azioni aggiuntive che i risponditori potrebbero prendere in risposta a un avviso

#### <a name="rule-frequency"></a>Frequenza delle regole
Quando viene salvata, viene eseguita immediatamente una regola di rilevamento personalizzata nuova o modificata e vengono verificate le corrispondenze degli ultimi 30 giorni di dati. La regola viene quindi eseguita di nuovo a intervalli fissi e le durate di lookback in base alla frequenza scelta:

- **Ogni 24 ore** : viene eseguito ogni 24 ore, controllando i dati degli ultimi 30 giorni.
- **Ogni 12 ore** : viene eseguito ogni 12 ore, controllando i dati delle ultime 24 ore.
- **Ogni 3 ore** : viene eseguito ogni 3 ore, controllando i dati delle ultime 6 ore.
- **Ogni ora** : viene eseguito ogni ora, controllando i dati delle ultime 2 ore.

Selezionare la frequenza corrispondente alla misura in cui si desidera monitorare i rilevamenti e valutare la capacità dell'organizzazione di rispondere agli avvisi.

### <a name="3-choose-the-impacted-entities"></a>3. scegliere le entità interessate.
Identificare le colonne nei risultati della query in cui si prevede di trovare l'entità interessata o con l'impatto principale. Ad esempio, una query potrebbe restituire gli indirizzi`SenderFromAddress` mittente `SenderMailFromAddress`(o) e`RecipientEmailAddress`destinatario (). Identificare quali di queste colonne rappresentano la principale entità interessata aiuta gli avvisi rilevanti di aggregazione del servizio, la correlazione degli incidenti e le azioni di risposta di destinazione.

È possibile selezionare una sola colonna per ogni tipo di entità (cassetta postale, utente o dispositivo). Le colonne non restituite dalla query non possono essere selezionate.

### <a name="3-specify-actions-on-files-or-machines"></a>3. specificare le azioni su file o computer.
La regola di rilevamento personalizzata può eseguire automaticamente azioni su file o computer restituiti dalla query.

#### <a name="actions-on-machines"></a>Azioni sui computer
Queste azioni vengono applicate ai computer nella `DeviceId` colonna dei risultati della query:
- **Isolate Machine** : utilizza Microsoft Defender ATP per applicare l'isolamento completo della rete, impedendo al computer di connettersi a qualsiasi applicazione o servizio. [Altre informazioni sull'isolamento del computer ATP Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-machines-from-the-network)
- **Raccolta del pacchetto di analisi** : raccoglie le informazioni sul computer in un file zip. [Per ulteriori informazioni, vedere il pacchetto di analisi ATP Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-machines)
- **Run Antivirus Scan** : esegue un'analisi completa di Windows Defender antivirus sul computer
- **Avviare un'indagine** : avvia un' [indagine automatizzata](mtp-autoir.md) sul computer

#### <a name="actions-on-files"></a>Azioni sui file
Se si seleziona questa opzione, l'azione **file di quarantena** viene eseguita `SHA1`sui `InitiatingProcessSHA1`file `SHA256`nella colonna `InitiatingProcessSHA256` ,, o dei risultati della query. Questa azione consente di eliminare il file dal percorso corrente e di collocarne una copia in quarantena.

> [!NOTE]
> L'azione Consenti o blocca per le regole di rilevamento personalizzate non è attualmente supportata su Microsoft Threat Protection.

### <a name="4-set-the-rule-scope"></a>4. impostare l'ambito della regola.
Impostare l'ambito per specificare quali dispositivi sono coperti dalla regola. L'ambito influenza le regole che controllano i dispositivi e non influisce sulle regole che controllano solo le cassette postali e gli account utente o le identità.

Quando si imposta l'ambito, è possibile selezionare:

- Tutti i dispositivi
- Gruppi di dispositivi specifici

Verrà eseguita una query solo sui dati dei dispositivi nell'ambito. Inoltre, le azioni verranno eseguite solo su tali dispositivi.

### <a name="5-review-and-turn-on-the-rule"></a>5. rivedere e accendere la regola.
Dopo aver esaminato la regola, fare clic su **Crea** per salvarla. Viene eseguita immediatamente la regola di rilevamento personalizzata. Viene eseguito di nuovo in base alla frequenza configurata per verificare la corrispondenza, generare avvisi e prendere le azioni di risposta.

## <a name="manage-existing-custom-detection-rules"></a>Gestire le regole di rilevamento personalizzate esistenti
È possibile visualizzare l'elenco delle regole di rilevamento personalizzate esistenti, verificare le relative esecuzioni precedenti ed esaminare gli avvisi che sono stati attivati. È inoltre possibile eseguire una regola su richiesta e modificarla.

### <a name="view-existing-rules"></a>Visualizzazione delle regole esistenti

Per visualizzare tutte le regole di rilevamento personalizzate esistenti, **passare a ricerca** > di**rilevamenti personalizzati**. Nella pagina sono elencate tutte le regole con le seguenti informazioni di esecuzione:

- **Ultima esecuzione** : quando è stata eseguita l'ultima esecuzione di una regola per verificare la corrispondenza di query e generare avvisi
- **Stato ultima esecuzione** -se una regola ha avuto esito positivo
- **Esecuzione successiva** : la successiva esecuzione pianificata
- **Stato** : se una regola è stata attivata o disattivata

### <a name="view-rule-details-modify-rule-and-run-rule"></a>Visualizzare i dettagli delle regole, modificare la regola e eseguire la regola

Per visualizzare informazioni complete su una regola di rilevamento personalizzata, selezionare il nome della regola nell'elenco delle regole in **caccia** > ai**rilevamenti personalizzati**. In questo articolo viene aperta una pagina sulla regola di rilevamento personalizzata con informazioni generali sulla regola, inclusi i dettagli dell'avviso, lo stato di esecuzione e l'ambito. Fornisce inoltre l'elenco degli avvisi attivati e delle azioni attivate.

![Pagina dei dettagli delle regole di rilevamento personalizzate](../../media/custom-detection-details.png)<br>
*Dettagli sulle regole di rilevamento personalizzate*

È inoltre possibile eseguire le azioni seguenti sulla regola da questa pagina:

- **Esegui** -eseguire immediatamente la regola. Questo reimposta anche l'intervallo per la successiva esecuzione.
- **Modifica** : consente di modificare la regola senza modificare la query
- **Modify query** -modificare la query in Advanced Hunting
- **Attiva**disattivazione-Abilita la regola o Interrompi l'esecuzione**Turn off**  / 
- **Elimina (Delete** )-disattiva la regola e rimuovila

### <a name="view-and-manage-triggered-alerts"></a>Visualizzare e gestire gli avvisi attivati

Nella schermata Dettagli regola (**caccia** > **ai rilevamenti** > personalizzati **[nome regola]**), andare a **avvisi attivati** per visualizzare l'elenco degli avvisi generati dalle corrispondenze alla regola. Selezionare un avviso per visualizzare informazioni dettagliate sull'avviso e intraprendere le azioni seguenti per l'avviso:

- Gestire l'avviso impostando lo stato e la classificazione (avviso vero o falso)
- Collegare l'avviso a un evento imprevisto
- Eseguire la query che ha attivato l'avviso per la ricerca avanzata

### <a name="review-actions"></a>Esaminare le azioni
Nella schermata Dettagli regola (**caccia** > **ai rilevamenti** > personalizzati **[nome regola]**), andare a **azioni attivate** per visualizzare l'elenco delle azioni intraprese in base alle corrispondenze alla regola.

>[!TIP]
>Per visualizzare rapidamente le informazioni e intervenire su un elemento di una tabella, utilizzare la colonna di selezione [&#10003;] a sinistra della tabella.

## <a name="related-topic"></a>Argomento correlato
- [Panoramica dei rilevamenti personalizzati](custom-detections-overview.md)
- [Panoramica della ricerca avanzata](advanced-hunting-overview.md)
- [Scoprire il linguaggio delle query in Ricerca avanzata](advanced-hunting-query-language.md)
