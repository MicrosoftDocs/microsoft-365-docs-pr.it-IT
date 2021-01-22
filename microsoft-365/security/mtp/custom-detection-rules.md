---
title: Creare e gestire regole di rilevamento personalizzate in Microsoft 365 Defender
description: Informazioni su come creare e gestire regole di rilevamento personalizzate basate su query di ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca delle minacce informatiche, protezione dalle minacce Microsoft, Microsoft 365, mtp, m365, ricerca, query, telemetria, rilevamenti personalizzati, regole, schema, kusto, Microsoft 365, Microsoft Threat Protection, RBAC, autorizzazioni, Microsoft Defender ATP
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 8c7e47e66f9e5543cc122c5b5154207cae836d2a
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932923"
---
# <a name="create-and-manage-custom-detections-rules"></a>Creare e gestire regole di rilevamento personalizzate

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

Le regole di rilevamento personalizzate sono regole che è possibile progettare e modificare utilizzando [query di ricerca](advanced-hunting-overview.md) avanzata. Queste regole consentono di monitorare in modo proattivo diversi eventi e stati di sistema, tra cui attività di violazione sospetta e endpoint non configurati correttamente. Puoi impostarli per l'esecuzione a intervalli regolari, generando avvisi ed eseguire azioni di risposta ogni volta che sono presenti corrispondenze.

## <a name="required-permissions-for-managing-custom-detections"></a>Autorizzazioni necessarie per la gestione dei rilevamenti personalizzati

Per gestire i rilevamenti personalizzati, è necessario disporre di uno di questi ruoli:

- **Amministratore della** sicurezza: gli utenti con questo [ruolo di Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) possono gestire le impostazioni di sicurezza nel Centro sicurezza Microsoft 365 e in altri portali e servizi.

- **Operatore della** sicurezza: gli utenti con questo ruolo di [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) possono gestire gli avvisi e avere accesso globale in sola lettura alle funzionalità correlate alla sicurezza, incluse tutte le informazioni nel Centro sicurezza Microsoft 365. Questo ruolo è sufficiente per gestire i rilevamenti personalizzati solo se il controllo dell'accesso basato sui ruoli (RBAC) è disattivato in Microsoft Defender per endpoint. Se il controllo di accesso basato sui ruoli è configurato, è necessaria anche l'autorizzazione per gestire le impostazioni **di** sicurezza per Defender per Endpoint.

Per gestire le autorizzazioni necessarie, un **amministratore globale** può:

- Assegnare **il ruolo di amministratore della** sicurezza o **operatore** di sicurezza nell'interfaccia di amministrazione di [Microsoft 365](https://admin.microsoft.com/) in Amministratore **sicurezza**  >  **ruoli.**
- Controllare le impostazioni RBAC per Microsoft Defender for Endpoint in [Microsoft Defender Security Center](https://securitycenter.windows.com/) in **Ruoli**  >  **autorizzazioni**  >  **impostazioni.** Selezionare il ruolo corrispondente per assegnare **l'autorizzazione per la gestione delle impostazioni di** sicurezza.

> [!NOTE]
> Per gestire i rilevamenti personalizzati,  gli **operatori** della sicurezza dovranno disporre dell'autorizzazione per gestire le impostazioni di sicurezza in Microsoft Defender per Endpoint se RBAC è attivato.

## <a name="create-a-custom-detection-rule"></a>Creare una regola di rilevamento personalizzata
### <a name="1-prepare-the-query"></a>1. Preparare la query.

Nel Centro sicurezza Microsoft 365 passare a **Ricerca avanzata** e selezionare una query esistente o creare una nuova query. Quando si utilizza una nuova query, eseguire la query per identificare gli errori e comprendere i possibili risultati.

>[!IMPORTANT]
>Per impedire al servizio di restituire troppi avvisi, ogni regola può generare solo 100 avvisi ogni volta che viene eseguito. Prima di creare una regola, modificare la query per evitare avvisi per le normali attività quotidiane.


#### <a name="required-columns-in-the-query-results"></a>Colonne obbligatorie nei risultati della query
Per creare una regola di rilevamento personalizzata, la query deve restituire le colonne seguenti:

- `Timestamp`: usato per impostare il timestamp per gli avvisi generati
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
>Il supporto per entità aggiuntive verrà aggiunto man quando vengono aggiunte nuove tabelle allo [schema di ricerca avanzata.](advanced-hunting-schema-tables.md)

Query semplici, ad esempio quelle che non utilizzano l'operatore or per personalizzare o aggregare i risultati, in genere restituiscono `project` `summarize` queste colonne comuni.

Esistono diversi modi per garantire che query più complesse restituiranno queste colonne. Ad esempio, se si preferisce aggregare e contare per entità in una colonna come , è comunque possibile restituire e ottenere dall'evento più recente che coinvolge `DeviceId` `Timestamp` ogni elemento `ReportId` `DeviceId` univoco.

La query di esempio seguente conta il numero di dispositivi univoci ( ) con rilevamenti antivirus e usa questo conteggio per trovare solo i dispositivi con più di `DeviceId` cinque rilevamenti. Per restituire l'ultima `Timestamp` e la `ReportId` corrispondente, viene utilizzato `summarize` l'operatore con la `arg_max` funzione.

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

Con la query nell'editor di query, selezionare Crea regola **di** rilevamento e specificare i dettagli dell'avviso seguenti:

- **Nome rilevamento**- Nome della regola di rilevamento
- **Frequenza:** intervallo per l'esecuzione della query e l'esecuzione di un'azione. [Vedi altre indicazioni di seguito](#rule-frequency)
- **Titolo dell'avviso**: titolo visualizzato con gli avvisi attivati dalla regola
- **Gravità :** potenziale rischio del componente o dell'attività identificata dalla regola
- **Categoria:** componente della minaccia o attività identificata dalla regola
- **MiTRE ATT&CK:** una o più tecniche di attacco identificate dalla regola come documentato nel [framework MITRE ATT&CK.](https://attack.mitre.org/) Questa sezione è nascosta per alcune categorie di avviso, tra cui malware, ransomware, attività sospette e software indesiderato
- **Descrizione:** ulteriori informazioni sul componente o sull'attività identificata dalla regola 
- **Azioni consigliate:** azioni aggiuntive che i risponditori potrebbero intraprendere in risposta a un avviso

#### <a name="rule-frequency"></a>Frequenza delle regole
Quando si salva o si modifica una nuova regola, viene eseguita e viene verificata la presenza di corrispondenze degli ultimi 30 giorni di dati. La regola viene quindi rieseguiti a intervalli fissi, applicando una durata di lookback in base alla frequenza scelta:

- **Ogni 24 ore:** viene eseguito ogni 24 ore, controllando i dati degli ultimi 30 giorni
- **Ogni 12 ore:** viene eseguito ogni 12 ore, controllando i dati delle ultime 24 ore
- **Ogni 3 ore:** viene eseguito ogni 3 ore, controllando i dati delle ultime 6 ore
- **Ogni ora:** viene eseguita ogni ora, controllando i dati delle ultime 2 ore

>[!TIP]
> Associare i filtri tempo nella query alla durata di lookback. I risultati al di fuori della durata di lookback vengono ignorati.  

Selezionare la frequenza che corrisponde alla frequenza con cui si desidera monitorare i rilevamenti. Considerare la capacità dell'organizzazione di rispondere agli avvisi.

### <a name="3-choose-the-impacted-entities"></a>3. Scegliere le entità influenzate.
Identificare le colonne nei risultati della query in cui si prevede di trovare l'entità principale interessata o interessata. Ad esempio, una query potrebbe restituire gli indirizzi del mittente ( `SenderFromAddress` o ) e del `SenderMailFromAddress` destinatario ( `RecipientEmailAddress` ). L'identificazione di quale di queste colonne rappresenta l'entità impacted principale consente al servizio di aggregare avvisi pertinenti, correlare gli eventi imprevisti e le azioni di risposta di destinazione.

È possibile selezionare una sola colonna per ogni tipo di entità (cassetta postale, utente o dispositivo). Le colonne non restituite dalla query non possono essere selezionate.

### <a name="4-specify-actions"></a>4. Specificare le azioni.
La regola di rilevamento personalizzata può eseguire automaticamente azioni su dispositivi, file o utenti restituiti dalla query.

#### <a name="actions-on-devices"></a>Azioni nei dispositivi
Queste azioni vengono applicate ai dispositivi nella `DeviceId` colonna dei risultati della query:
- **Isola dispositivo:** usa Microsoft Defender per Endpoint per applicare l'isolamento di rete completo, impedendo al dispositivo di connettersi a qualsiasi applicazione o servizio. [Altre informazioni sull'isolamento del computer di Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-devices-from-the-network)
- **Raccogliere il pacchetto di** analisi: raccoglie le informazioni sul dispositivo in un file ZIP. [Altre informazioni sul pacchetto di analisi di Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices)
- **Eseguire l'analisi antivirus:** esegue un'Windows Defender antivirus completa nel dispositivo
- **Avvia un'indagine:** avvia [un'indagine](mtp-autoir.md) automatizzata nel dispositivo
- **Limita l'esecuzione dell'app:** imposta restrizioni per il dispositivo per consentire l'esecuzione solo dei file firmati con un certificato emesso da Microsoft. [Altre informazioni sulle restrizioni per le app con Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#restrict-app-execution)

#### <a name="actions-on-files"></a>Azioni sui file
Se questa opzione è selezionata, è possibile scegliere di applicare l'azione Del **file** in quarantena ai file nella colonna , , o dei `SHA1` risultati della `InitiatingProcessSHA1` `SHA256` `InitiatingProcessSHA256` query. Questa azione elimina il file dalla posizione corrente e ne mette una copia in quarantena.

#### <a name="actions-on-users"></a>Azioni sugli utenti
Se selezionata, **l'azione** Contrassegna utente come compromessa viene eseguita sugli utenti nella `AccountObjectId` colonna , o nella colonna dei risultati della `InitiatingProcessAccountObjectId` `RecipientObjectId` query. Questa azione imposta il livello di rischio degli utenti su "alto" in Azure Active Directory, attivando i criteri [di protezione delle identità corrispondenti.](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection)

> [!NOTE]
> L'azione consenti o blocca per le regole di rilevamento personalizzate non è attualmente supportata in Microsoft 365 Defender.

### <a name="5-set-the-rule-scope"></a>5. Impostare l'ambito della regola.
Impostare l'ambito per specificare quali dispositivi sono coperti dalla regola. L'ambito influenza le regole che controllano i dispositivi e non influisce sulle regole che controllano solo le cassette postali e gli account utente o le identità.

Quando si imposta l'ambito, è possibile selezionare:

- Tutti i dispositivi
- Gruppi di dispositivi specifici

Verranno interrogati solo i dati dei dispositivi nell'ambito. Inoltre, le azioni verranno eseguite solo su tali dispositivi.

### <a name="6-review-and-turn-on-the-rule"></a>6. Rivedere e attivare la regola.
Dopo aver esaminato la regola, selezionare **Crea** per salvarla. La regola di rilevamento personalizzata viene eseguita immediatamente. Viene eseguito nuovamente in base alla frequenza configurata per verificare la presenza di corrispondenze, generare avvisi ed eseguire azioni di risposta.

## <a name="manage-existing-custom-detection-rules"></a>Gestire le regole di rilevamento personalizzate esistenti
Puoi visualizzare l'elenco delle regole di rilevamento personalizzate esistenti, controllarne le esecuzioni precedenti ed esaminare gli avvisi che hanno attivato. È inoltre possibile eseguire una regola su richiesta e modificarla.

### <a name="view-existing-rules"></a>Visualizzare le regole esistenti

Per visualizzare tutte le regole di rilevamento personalizzate esistenti, passare **a Ricerca**  >  **rilevamenti personalizzati.** Nella pagina sono elencate tutte le regole con le informazioni di esecuzione seguenti:

- **Ultima esecuzione:** data dell'ultima esecuzione di una regola per verificare la presenza di corrispondenze alle query e generare avvisi
- **Stato dell'ultima esecuzione:** indica se una regola è stata eseguita correttamente
- **Esecuzione successiva:** l'esecuzione pianificata successiva
- **Stato**: indica se una regola è stata attivata o disattivata

### <a name="view-rule-details-modify-rule-and-run-rule"></a>Visualizzare i dettagli della regola, modificare la regola ed eseguire la regola

Per visualizzare informazioni complete su una regola di rilevamento personalizzata, passare a **Ricerca** rilevamenti personalizzati e quindi  >   selezionare il nome della regola. È quindi possibile visualizzare informazioni generali sulla regola, incluse le informazioni relative allo stato di esecuzione e all'ambito. La pagina fornisce anche l'elenco di avvisi e azioni attivati.

![Pagina dei dettagli della regola di rilevamento personalizzata](../../media/custom-detection-details.png)<br>
*Dettagli delle regole di rilevamento personalizzate*

È inoltre possibile eseguire le azioni seguenti nella regola da questa pagina:

- **Esegui:** esegui la regola immediatamente. In questo modo viene reimpostato anche l'intervallo per l'esecuzione successiva.
- **Modifica:** modificare la regola senza modificare la query
- **Modifica query**: modificare la query nella ricerca avanzata
- **Attivare**  /  **Disattivare:** abilitare o arrestare l'esecuzione della regola
- **Elimina:** disattivare la regola e rimuoverla

### <a name="view-and-manage-triggered-alerts"></a>Visualizzare e gestire gli avvisi attivati

Nella schermata dei dettagli della regola (**Ricerca** rilevamenti personalizzati [nome della regola] ) passare a Avvisi attivati, in cui sono elencati gli avvisi generati dalle  >    >  corrispondenze alla regola.  Selezionare un avviso per visualizzare informazioni dettagliate ed eseguire le azioni seguenti:

- Gestire l'avviso impostandone lo stato e la classificazione (avviso vero o falso)
- Collegare l'avviso a un evento imprevisto
- Eseguire la query che ha attivato l'avviso per la ricerca avanzata

### <a name="review-actions"></a>Rivedere le azioni
Nella schermata dei dettagli della regola (**Ricerca** rilevamenti personalizzati [nome della regola] ) passare ad Azioni attivate, in cui sono elencate le azioni eseguite in base alle  >    >  corrispondenze alla regola. 

>[!TIP]
>Per visualizzare rapidamente le informazioni ed eseguire un'azione su un elemento di una tabella, utilizzare la colonna di selezione [&#10003;] a sinistra della tabella.

## <a name="related-topic"></a>Argomento correlato
- [Panoramica dei rilevamenti personalizzati](custom-detections-overview.md)
- [Panoramica della ricerca avanzata](advanced-hunting-overview.md)
- [Scoprire il linguaggio delle query in Ricerca avanzata](advanced-hunting-query-language.md)
