---
title: Creare e gestire regole di rilevamento personalizzate in Microsoft 365 Defender
description: Informazioni su come creare e gestire regole di rilevamento personalizzate basate su query di ricerca avanzate
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, protezione dalle minacce Microsoft, Microsoft 365, mtp, m365, ricerca, query, telemetria, rilevamenti personalizzati, regole, schema, kusto, Microsoft 365, Microsoft Threat Protection, RBAC, autorizzazioni, Microsoft Defender ATP
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 12a35a9f80da6b401495fcae7c245436b35b991c
ms.sourcegitcommit: ef98b8a18d275e5b5961e63d2b0743d046321737
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/26/2021
ms.locfileid: "51382890"
---
# <a name="create-and-manage-custom-detections-rules"></a>Creare e gestire regole di rilevamento personalizzate

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

Le regole di rilevamento personalizzate sono regole che è possibile progettare e modificare utilizzando [query di ricerca](advanced-hunting-overview.md) avanzate. Queste regole consentono di monitorare in modo proattivo vari eventi e stati di sistema, tra cui attività di violazione sospetta e endpoint non configurati correttamente. Puoi impostarli per l'esecuzione a intervalli regolari, generando avvisi ed eseguire azioni di risposta ogni volta che ci sono corrispondenze.

## <a name="required-permissions-for-managing-custom-detections"></a>Autorizzazioni necessarie per la gestione dei rilevamenti personalizzati

Per gestire i rilevamenti personalizzati, è necessario disporre di uno di questi ruoli:

- **Amministratore della** sicurezza: gli utenti con questo [ruolo di Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) possono gestire le impostazioni di sicurezza nel Centro sicurezza Microsoft 365 e in altri portali e servizi.

- **Operatore di** sicurezza: gli utenti con questo ruolo [di Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) possono gestire gli avvisi e avere accesso globale in sola lettura alle funzionalità correlate alla sicurezza, incluse tutte le informazioni nel Centro sicurezza Microsoft 365. Questo ruolo è sufficiente per gestire i rilevamenti personalizzati solo se il controllo di accesso basato sui ruoli (RBAC) è disattivato in Microsoft Defender per Endpoint. Se è stato configurato RBAC, è necessario disporre anche dell'autorizzazione di gestione delle impostazioni **di** sicurezza per Defender per Endpoint.

Per gestire le autorizzazioni necessarie, un **amministratore globale** può:

- Assegnare **il ruolo di amministratore della** sicurezza o **operatore** di sicurezza nell'interfaccia di amministrazione di [Microsoft 365](https://admin.microsoft.com/) in **Ruoli**  >  **Amministratore sicurezza**.
- Controllare le impostazioni RBAC per Microsoft Defender for Endpoint in [Microsoft Defender Security Center](https://securitycenter.windows.com/) in **Impostazioni**  >  **Autorizzazioni**  >  **Ruoli**. Selezionare il ruolo corrispondente per assegnare **l'autorizzazione gestisci impostazioni di** sicurezza.

> [!NOTE]
> Per gestire i rilevamenti **personalizzati,** gli operatori della sicurezza dovranno disporre dell'autorizzazione di gestione delle impostazioni di sicurezza in Microsoft Defender per Endpoint se RBAC è attivato. 

## <a name="create-a-custom-detection-rule"></a>Creare una regola di rilevamento personalizzata
### <a name="1-prepare-the-query"></a>1. Preparare la query.

Nel Centro sicurezza Microsoft 365 passare a Ricerca **avanzata** e selezionare una query esistente o creare una nuova query. Quando si utilizza una nuova query, eseguire la query per identificare gli errori e comprendere i possibili risultati.

>[!IMPORTANT]
>Per impedire al servizio di restituire troppi avvisi, ogni regola può generare solo 100 avvisi ogni volta che viene eseguito. Prima di creare una regola, modificare la query per evitare avvisi per le normali attività quotidiane.


#### <a name="required-columns-in-the-query-results"></a>Colonne obbligatorie nei risultati della query
Per creare una regola di rilevamento personalizzata, la query deve restituire le colonne seguenti:

- `Timestamp`: utilizzato per impostare il timestamp per gli avvisi generati
- `ReportId`: abilita le ricerche per i record originali
- Una delle colonne seguenti che identificano dispositivi, utenti o cassette postali specifici:
    - `DeviceId`
    - `DeviceName`
    - `RemoteDeviceName`
    - `RecipientEmailAddress`
    - `SenderFromAddress` (mittente della busta o indirizzo Return-Path destinatario)
    - `SenderMailFromAddress` (indirizzo del mittente visualizzato dal client di posta elettronica)
    - `RecipientObjectId`
    - `AccountObjectId`
    - `AccountSid`
    - `AccountUpn`
    - `InitiatingProcessAccountSid`
    - `InitiatingProcessAccountUpn`
    - `InitiatingProcessAccountObjectId`

>[!NOTE]
>Il supporto per altre entità verrà aggiunto quando vengono aggiunte nuove tabelle allo [schema di ricerca avanzata.](advanced-hunting-schema-tables.md)

Le query semplici, ad esempio quelle che non utilizzano l'operatore or per personalizzare o aggregare i risultati, in genere `project` `summarize` restituiscono queste colonne comuni.

Esistono diversi modi per garantire che query più complesse restituiranno queste colonne. Ad esempio, se si preferisce aggregare e contare per entità in una colonna come , è comunque possibile restituire e ottenere dall'evento più recente che coinvolge `DeviceId` `Timestamp` ogni `ReportId` univoco `DeviceId` .

La query di esempio seguente conta il numero di dispositivi univoci ( ) con rilevamenti antivirus e usa questo conteggio per trovare solo i dispositivi con più `DeviceId` di cinque rilevamenti. Per restituire l'ultimo `Timestamp` e il corrispondente , viene utilizzato `ReportId` `summarize` l'operatore con la funzione `arg_max` .

```kusto
DeviceEvents
| where Timestamp > ago(1d)
| where ActionType == "AntivirusDetection"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| where count_ > 5
```

> [!TIP]
> Per migliorare le prestazioni delle query, impostare un filtro temporale che corrisponda alla frequenza di esecuzione prevista per la regola. Poiché l'esecuzione meno frequente _è ogni 24 ore,_ il filtro per il giorno precedente copre tutti i nuovi dati.

### <a name="2-create-new-rule-and-provide-alert-details"></a>2. Creare una nuova regola e fornire i dettagli dell'avviso.

Con la query nell'editor di query, selezionare Crea regola **di rilevamento** e specificare i dettagli dell'avviso seguenti:

- **Nome rilevamento**- Nome della regola di rilevamento
- **Frequenza:** intervallo per l'esecuzione della query e l'esecuzione di azioni. [Vedi ulteriori indicazioni di seguito](#rule-frequency)
- **Titolo dell'avviso**: titolo visualizzato con gli avvisi attivati dalla regola
- **Gravità:** potenziale rischio del componente o dell'attività identificata dalla regola
- **Categoria:** componente di minaccia o attività identificata dalla regola
- **MITRE ATT&tecniche CK,** ovvero una o più tecniche di attacco identificate dalla regola, come documentato nel [framework MITRE ATT&CK.](https://attack.mitre.org/) Questa sezione è nascosta per determinate categorie di avvisi, tra cui malware, ransomware, attività sospette e software indesiderato
- **Descrizione:** ulteriori informazioni sul componente o sull'attività identificate dalla regola 
- **Azioni consigliate:** azioni aggiuntive che i risponditori potrebbero intraprendere in risposta a un avviso

#### <a name="rule-frequency"></a>Frequenza delle regole
Quando si salva una nuova regola, viene eseguita e viene verificata la presenza di corrispondenze degli ultimi 30 giorni di dati. La regola viene quindi eseguita di nuovo a intervalli fissi, applicando una durata di lookback in base alla frequenza scelta:

- **Ogni 24 ore:** viene eseguito ogni 24 ore, controllando i dati degli ultimi 30 giorni
- **Ogni 12 ore:** viene eseguito ogni 12 ore, controllando i dati delle ultime 24 ore
- **Ogni 3 ore:** viene eseguito ogni 3 ore, controllando i dati delle ultime 6 ore
- **Ogni ora:** viene eseguito ogni ora, controllando i dati delle ultime 2 ore

Quando si modifica una regola, questa verrà eseguita con le modifiche applicate nella successiva fase di esecuzione pianificata in base alla frequenza impostata.



>[!TIP]
> Associare i filtri tempo nella query alla durata del lookback. I risultati al di fuori della durata del lookback vengono ignorati.  

Selezionare la frequenza corrispondente alla frequenza con cui si desidera monitorare i rilevamenti. Considerare la capacità dell'organizzazione di rispondere agli avvisi.

### <a name="3-choose-the-impacted-entities"></a>3. Scegliere le entità influenzate.
Identificare le colonne nei risultati della query in cui si prevede di trovare l'entità principale interessata o interessata. Ad esempio, una query potrebbe restituire gli indirizzi del mittente ( `SenderFromAddress` o ) e del `SenderMailFromAddress` destinatario ( `RecipientEmailAddress` ). L'identificazione di quale di queste colonne rappresenta l'entità principale influenzata consente al servizio di aggregare avvisi rilevanti, correlare eventi imprevisti e azioni di risposta di destinazione.

È possibile selezionare una sola colonna per ogni tipo di entità (cassetta postale, utente o dispositivo). Le colonne non restituite dalla query non possono essere selezionate.

### <a name="4-specify-actions"></a>4. Specificare le azioni.
La regola di rilevamento personalizzata può eseguire automaticamente azioni su dispositivi, file o utenti restituiti dalla query.

#### <a name="actions-on-devices"></a>Azioni nei dispositivi
Queste azioni vengono applicate ai dispositivi nella `DeviceId` colonna dei risultati della query:
- **Isola dispositivo:** usa Microsoft Defender for Endpoint per applicare l'isolamento di rete completo, impedendo al dispositivo di connettersi a qualsiasi applicazione o servizio. [Altre informazioni sull'isolamento del computer di Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-devices-from-the-network)
- **Raccogli pacchetto di analisi:** raccoglie le informazioni sul dispositivo in un file ZIP. [Altre informazioni sul pacchetto di analisi di Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices)
- **Esegui analisi antivirus:** esegue un'Windows Defender antivirus completa nel dispositivo
- **Avvia un'indagine:** avvia [un'indagine](m365d-autoir.md) automatizzata sul dispositivo
- **Limita l'esecuzione dell'app:** imposta le restrizioni sul dispositivo per consentire l'esecuzione solo dei file firmati con un certificato rilasciato da Microsoft. [Altre informazioni sulle restrizioni per le app con Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/respond-machine-alerts#restrict-app-execution)

#### <a name="actions-on-files"></a>Azioni sui file
Se selezionata, è possibile scegliere di applicare l'azione Quarantena **file** ai file nella `SHA1` colonna , , o dei risultati della `InitiatingProcessSHA1` `SHA256` `InitiatingProcessSHA256` query. Questa azione elimina il file dal percorso corrente e ne mette una copia in quarantena.

#### <a name="actions-on-users"></a>Azioni sugli utenti
Se selezionata, **l'azione** Contrassegna l'utente come compromessa viene eseguita sugli utenti nella `AccountObjectId` colonna , o dei risultati della `InitiatingProcessAccountObjectId` `RecipientObjectId` query. Questa azione imposta il livello di rischio degli utenti su "alto" in Azure Active Directory, attivando i criteri [di protezione delle identità corrispondenti.](/azure/active-directory/identity-protection/overview-identity-protection)

> [!NOTE]
> L'azione consenti o blocca per le regole di rilevamento personalizzate non è attualmente supportata in Microsoft 365 Defender.

### <a name="5-set-the-rule-scope"></a>5. Impostare l'ambito della regola.
Impostare l'ambito per specificare quali dispositivi sono coperti dalla regola. L'ambito influenza le regole che controllano i dispositivi e non influisce sulle regole che controllano solo le cassette postali, gli account utente o le identità.

Quando si imposta l'ambito, è possibile selezionare:

- Tutti i dispositivi
- Gruppi di dispositivi specifici

Verranno interrogati solo i dati dei dispositivi nell'ambito. Inoltre, le azioni verranno eseguite solo su tali dispositivi.

### <a name="6-review-and-turn-on-the-rule"></a>6. Esaminare e attivare la regola.
Dopo aver esaminato la regola, selezionare **Crea** per salvarla. La regola di rilevamento personalizzata viene eseguita immediatamente. Viene eseguito di nuovo in base alla frequenza configurata per verificare la presenza di corrispondenze, generare avvisi ed eseguire azioni di risposta.


>[!Important] 
>I rilevamenti personalizzati devono essere regolarmente esaminati per l'efficienza e l'efficacia. Per assicurarsi di creare rilevamenti che attivano avvisi veri, prendere tempo per esaminare i rilevamenti personalizzati esistenti seguendo la procedura descritta in [Gestire le regole di rilevamento personalizzate esistenti.](#manage-existing-custom-detection-rules) <br>  
È possibile mantenere il controllo sull'ampia o specificità dei rilevamenti personalizzati, in modo che eventuali falsi avvisi generati da rilevamenti personalizzati potrebbero indicare la necessità di modificare determinati parametri delle regole.


## <a name="manage-existing-custom-detection-rules"></a>Gestire le regole di rilevamento personalizzate esistenti
È possibile visualizzare l'elenco delle regole di rilevamento personalizzate esistenti, controllare le esecuzioni precedenti ed esaminare gli avvisi che hanno attivato. È inoltre possibile eseguire una regola su richiesta e modificarla.

### <a name="view-existing-rules"></a>Visualizzare le regole esistenti

Per visualizzare tutte le regole di rilevamento personalizzate esistenti, passare **a Ricerca**  >  **rilevamenti personalizzati.** Nella pagina sono elencate tutte le regole con le seguenti informazioni di esecuzione:

- **Ultima esecuzione:** data dell'ultima esecuzione di una regola per verificare la presenza di corrispondenze di query e generare avvisi
- **Stato dell'ultima esecuzione:** indica se una regola è stata eseguita correttamente
- **Esecuzione successiva:** l'esecuzione pianificata successiva
- **Stato:** indica se una regola è stata attivata o disattivata

### <a name="view-rule-details-modify-rule-and-run-rule"></a>Visualizzare i dettagli della regola, modificare la regola ed eseguire la regola

Per visualizzare informazioni complete su una regola di rilevamento personalizzata, passare a **Ricerca** di rilevamenti  >  **personalizzati** e quindi selezionare il nome della regola. È quindi possibile visualizzare informazioni generali sulla regola, incluse le informazioni relative allo stato di esecuzione e all'ambito. Nella pagina è inoltre disponibile l'elenco degli avvisi e delle azioni attivati.

![Pagina dettagli regola di rilevamento personalizzata](../../media/custom-detection-details.png)<br>
*Dettagli delle regole di rilevamento personalizzate*

È inoltre possibile eseguire le azioni seguenti nella regola da questa pagina:

- **Esegui:** eseguire immediatamente la regola. In questo modo viene reimpostato anche l'intervallo per l'esecuzione successiva.
- **Modifica:** modificare la regola senza modificare la query
- **Modifica query**: modifica la query in ricerca avanzata
- **Attivare**  /  **Disattiva:** abilita la regola o arresta l'esecuzione
- **Delete:** disattivare la regola e rimuoverla

### <a name="view-and-manage-triggered-alerts"></a>Visualizzare e gestire gli avvisi attivati

Nella schermata dei dettagli della regola (**Ricerca** di rilevamenti personalizzati  >    >  **[nome regola]**) passare a **Avvisi** attivati , in cui sono elencati gli avvisi generati dalle corrispondenze alla regola. Selezionare un avviso per visualizzare informazioni dettagliate ed eseguire le azioni seguenti:

- Gestire l'avviso impostandone lo stato e la classificazione (avviso vero o falso)
- Collegare l'avviso a un evento imprevisto
- Eseguire la query che ha attivato l'avviso per la ricerca avanzata

### <a name="review-actions"></a>Rivedere le azioni
Nella schermata dei dettagli della regola (**Ricerca** di rilevamenti personalizzati  >    >  **[nome regola]**) passare a **Azioni** attivate , in cui sono elencate le azioni eseguite in base alle corrispondenze alla regola.

>[!TIP]
>Per visualizzare rapidamente le informazioni ed eseguire azioni su un elemento di una tabella, utilizzare la colonna di selezione [&#10003;] a sinistra della tabella.

## <a name="see-also"></a>Vedere anche
- [Panoramica dei rilevamenti personalizzati](custom-detections-overview.md)
- [Panoramica della ricerca avanzata](advanced-hunting-overview.md)
- [Scoprire il linguaggio delle query in Ricerca avanzata](advanced-hunting-query-language.md)
- [Eseguire la migrazione di query di ricerca avanzate da Microsoft Defender per Endpoint](advanced-hunting-migrate-from-mde.md)
