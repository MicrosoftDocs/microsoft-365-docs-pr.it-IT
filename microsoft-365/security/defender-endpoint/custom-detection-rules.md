---
title: Creare regole di rilevamento personalizzate in Microsoft Defender ATP
ms.reviewer: ''
description: Informazioni su come creare regole di rilevamento personalizzate basate su query di ricerca avanzate
keywords: rilevamenti personalizzati, creare, gestire, avvisi, modificare, eseguire su richiesta, frequenza, intervallo, regole di rilevamento, ricerca avanzata, ricerca, query, azioni di risposta, mdatp, microsoft defender atp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 09/20/2020
ms.technology: mde
ms.openlocfilehash: 15dec5396a5ba95fe3ec7af5f9a72bbf15e07140
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500492"
---
# <a name="create-custom-detection-rules"></a>Creare regole di rilevamento personalizzate

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Le regole di rilevamento personalizzate create da query [di](advanced-hunting-overview.md) ricerca avanzate consentono di monitorare in modo proattivo diversi eventi e stati di sistema, tra cui attività sospette di violazione e dispositivi non configurati correttamente. Puoi impostarli per l'esecuzione a intervalli regolari, generando avvisi ed eseguire azioni di risposta ogni volta che ci sono corrispondenze.

Leggere questo articolo per informazioni su come creare nuove regole di rilevamento personalizzate. In [altri, vedere Visualizzazione e gestione delle regole esistenti.](custom-detections-manage.md)

> [!NOTE]
> Per creare o gestire rilevamenti personalizzati, [il ruolo](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group) deve disporre dell'autorizzazione gestisci **impostazioni di** sicurezza.

## <a name="1-prepare-the-query"></a>1. Preparare la query.

In Microsoft Defender Security Center passare a **Ricerca avanzata** e selezionare una query esistente o creare una nuova query. Quando si utilizza una nuova query, eseguire la query per identificare gli errori e comprendere i possibili risultati.

>[!IMPORTANT]
>Per impedire al servizio di restituire troppi avvisi, ogni regola può generare solo 100 avvisi ogni volta che viene eseguito. Prima di creare una regola, modificare la query per evitare avvisi per le normali attività quotidiane.

### <a name="required-columns-in-the-query-results"></a>Colonne obbligatorie nei risultati della query

Per utilizzare una query per una regola di rilevamento personalizzata, la query deve restituire le colonne seguenti:

- `Timestamp`
- `DeviceId`
- `ReportId`

Le query semplici, ad esempio quelle che non utilizzano l'operatore or per personalizzare o aggregare i risultati, in genere `project` `summarize` restituiscono queste colonne comuni.

Esistono diversi modi per garantire che query più complesse restituiranno queste colonne. Ad esempio, se preferisci aggregare e contare per , puoi comunque restituirli e riceverli `DeviceId` dall'evento più recente che coinvolge ogni `Timestamp` `ReportId` dispositivo.

La query di esempio seguente conta il numero di dispositivi univoci ( ) con rilevamenti antivirus e lo usa per trovare solo i dispositivi con più `DeviceId` di cinque rilevamenti. Per restituire l'ultimo `Timestamp` e il corrispondente , viene utilizzato `ReportId` `summarize` l'operatore con la funzione `arg_max` .

```kusto
DeviceEvents
| where Timestamp > ago(7d)
| where ActionType == "AntivirusDetection"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| where count_ > 5
```

> [!TIP]
> Per migliorare le prestazioni delle query, impostare un filtro temporale che corrisponda alla frequenza di esecuzione prevista per la regola. Poiché l'esecuzione meno frequente è ogni 24 ore, il filtro per il giorno precedente copre tutti i nuovi dati.

## <a name="2-create-a-new-rule-and-provide-alert-details"></a>2. Creare una nuova regola e fornire i dettagli dell'avviso.

Con la query nell'editor di query, selezionare Crea regola **di rilevamento** e specificare i dettagli dell'avviso seguenti:

- **Nome rilevamento**- Nome della regola di rilevamento
- **Frequenza:** intervallo per l'esecuzione della query e l'esecuzione di azioni. [Vedi ulteriori indicazioni di seguito](#rule-frequency)
- **Titolo dell'avviso**: titolo visualizzato con gli avvisi attivati dalla regola
- **Gravità:** potenziale rischio del componente o dell'attività identificato dalla regola. [Informazioni sulla gravità degli avvisi](alerts-queue.md#severity)
- **Categoria:** tipo di componente o attività di minaccia, se presente. [Informazioni sulle categorie di avvisi](alerts-queue.md#understanding-alert-categories)
- **MITRE ATT&CK,** ovvero una o più tecniche di attacco identificate dalla regola, come documentato nel framework MITRE ATT&CK. Questa sezione non è disponibile con determinate categorie di avviso, ad esempio malware, ransomware, attività sospette e software indesiderato
- **Descrizione:** ulteriori informazioni sul componente o sull'attività identificate dalla regola 
- **Azioni consigliate:** azioni aggiuntive che i risponditori potrebbero intraprendere in risposta a un avviso

Per ulteriori informazioni sulla modalità di visualizzazione dei dettagli dell'avviso, [vedere informazioni sulla coda degli avvisi.](alerts-queue.md)

### <a name="rule-frequency"></a>Frequenza delle regole

Quando viene salvata, viene eseguita immediatamente una nuova regola di rilevamento personalizzata e viene verificata la presenza di corrispondenze degli ultimi 30 giorni di dati. La regola viene quindi rieseguiti a intervalli fissi e durate di lookback in base alla frequenza scelta:

- **Ogni 24 ore:** viene eseguito ogni 24 ore, controllando i dati degli ultimi 30 giorni
- **Ogni 12 ore:** viene eseguito ogni 12 ore, controllando i dati delle ultime 24 ore
- **Ogni 3 ore:** viene eseguito ogni 3 ore, controllando i dati delle ultime 6 ore
- **Ogni ora:** viene eseguito ogni ora, controllando i dati delle ultime 2 ore

Quando si modifica una regola, questa verrà eseguita con le modifiche applicate nella successiva fase di esecuzione pianificata in base alla frequenza impostata.


> [!TIP]
> Associare i filtri tempo nella query alla durata del lookback. I risultati al di fuori della durata del lookback vengono ignorati.

Selezionare la frequenza che corrisponde alla frequenza con cui si desidera monitorare i rilevamenti e considerare la capacità dell'organizzazione di rispondere agli avvisi.

## <a name="3-choose-the-impacted-entities"></a>3. Scegliere le entità influenzate.

Identificare le colonne nei risultati della query in cui si prevede di trovare l'entità principale interessata o interessata. Ad esempio, una query potrebbe restituire sia gli ID dispositivo che gli ID utente. L'identificazione di quale di queste colonne rappresenta l'entità principale influenzata consente al servizio di aggregare avvisi rilevanti, correlare eventi imprevisti e azioni di risposta di destinazione.

È possibile selezionare una sola colonna per ogni tipo di entità. Le colonne non restituite dalla query non possono essere selezionate.

## <a name="4-specify-actions"></a>4. Specificare le azioni.

La regola di rilevamento personalizzata può eseguire automaticamente azioni su file o dispositivi restituiti dalla query.

### <a name="actions-on-devices"></a>Azioni nei dispositivi

Queste azioni vengono applicate ai dispositivi nella `DeviceId` colonna dei risultati della query:

- **Isola dispositivo:** applica l'isolamento di rete completo, impedendo al dispositivo di connettersi a qualsiasi applicazione o servizio, ad eccezione del servizio Defender for Endpoint. [Altre informazioni sull'isolamento dei dispositivi](respond-machine-alerts.md#isolate-devices-from-the-network)
- **Raccogli pacchetto di analisi:** raccoglie le informazioni sul dispositivo in un file ZIP. [Altre informazioni sul pacchetto di analisi](respond-machine-alerts.md#collect-investigation-package-from-devices)
- **Esegui analisi antivirus:** esegue un'analisi completa di Microsoft Defender Antivirus nel dispositivo
- **Avvia indagine:** avvia [un'indagine](automated-investigations.md) automatizzata nel dispositivo
- **Limita l'esecuzione** dell'app: imposta le restrizioni sul dispositivo per consentire l'esecuzione solo dei file firmati con un certificato rilasciato da Microsoft. [Altre informazioni sulla limitazione dell'esecuzione delle app](respond-machine-alerts.md#restrict-app-execution)

### <a name="actions-on-files"></a>Azioni sui file

Queste azioni vengono applicate ai file nella colonna o nei `SHA1` `InitiatingProcessSHA1` risultati della query:

- **Consenti/Blocca:** aggiunge automaticamente il file [all'elenco](manage-indicators.md) di indicatori personalizzati in modo che sia sempre consentita l'esecuzione o il blocco dell'esecuzione. Puoi impostare l'ambito di questa azione in modo che sia eseguita solo nei gruppi di dispositivi selezionati. Questo ambito è indipendente dall'ambito della regola.
- **File in** quarantena: elimina il file dalla posizione corrente e ne inserisce una copia in quarantena

### <a name="actions-on-users"></a>Azioni sugli utenti

- **Contrassegna l'utente come** compromesso: imposta il livello di rischio dell'utente su "alto" in Azure Active Directory, attivando i criteri [di protezione delle identità corrispondenti.](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection#risk-levels)

## <a name="5-set-the-rule-scope"></a>5. Impostare l'ambito della regola.

Impostare l'ambito per specificare quali dispositivi sono coperti dalla regola:

- Tutti i dispositivi
- Gruppi di dispositivi specifici

Verranno interrogati solo i dati dei dispositivi nell'ambito. Inoltre, le azioni verranno eseguite solo su tali dispositivi.

## <a name="6-review-and-turn-on-the-rule"></a>6. Esaminare e attivare la regola.

Dopo aver esaminato la regola, selezionare **Crea** per salvarla. La regola di rilevamento personalizzata viene eseguita immediatamente. Viene eseguito di nuovo in base alla frequenza configurata per verificare la presenza di corrispondenze, generare avvisi ed eseguire azioni di risposta.

È possibile [visualizzare e gestire regole di rilevamento personalizzate,](custom-detections-manage.md)controllare le esecuzioni precedenti ed esaminare gli avvisi che hanno attivato. È inoltre possibile eseguire una regola su richiesta e modificarla.

## <a name="related-topics"></a>Argomenti correlati

- [Visualizzare e gestire regole di rilevamento personalizzate](custom-detections-manage.md)
- [Panoramica dei rilevamenti personalizzati](overview-custom-detections.md)
- [Panoramica della rilevazione avanzata](advanced-hunting-overview.md)
- [Scoprire il linguaggio delle query in Ricerca avanzata](advanced-hunting-query-language.md)
- [Visualizzare e organizzare gli avvisi](alerts-queue.md)
