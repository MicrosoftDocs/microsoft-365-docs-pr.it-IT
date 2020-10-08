---
title: Impostazioni di gestione dei rischi Insider
description: Informazioni sulle impostazioni di gestione dei rischi insider in Microsoft 365
keywords: Microsoft 365, gestione dei rischi Insider, gestione dei rischi, conformità
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
ms.openlocfilehash: c98c0081d95da19e79db03dc4b4fdb823a14e42c
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377271"
---
# <a name="get-started-with-insider-risk-management-settings"></a>Informazioni introduttive sulle impostazioni di gestione dei rischi Insider

Le impostazioni di gestione dei rischi Insider si applicano a tutti i criteri di gestione dei rischi Insider, indipendentemente dal modello scelto quando si crea un criterio. Le impostazioni vengono configurate utilizzando il controllo **impostazioni di rischio Insider** nella parte superiore di tutte le schede gestione rischi Insider. Queste impostazioni controllano i componenti dei criteri per le aree seguenti:

- Privacy
- Indicatori
- Sequenze temporali del criterio
- Rilevamenti intelligenti
- Avvisi di esportazione (anteprima)
- Gruppi di utenti prioritari (anteprima)
- Risorse fisiche prioritarie (anteprima)
- Flussi automatizzati di alimentazione (anteprima)
- Microsoft Teams (anteprima)

Prima di iniziare e creare criteri di gestione dei rischi Insider, è importante comprendere queste impostazioni e scegliere l'opzione livelli migliori per le esigenze di conformità per l'organizzazione.

## <a name="privacy"></a>Privacy

La protezione della privacy degli utenti che dispongono di corrispondenze di criteri è importante e può contribuire a promuovere l'oggettività nelle analisi dei dati e nelle recensioni degli analizzatori dei rischi Insider Per gli utenti con una corrispondenza dei criteri di rischio Insider, è possibile scegliere una delle seguenti impostazioni:

- **Mostrare le versioni di anonimi dei nomi utente**: i nominativi degli utenti sono anonimi per impedire agli amministratori, ai ricercatori dei dati e ai revisori di vedere chi è associato agli avvisi dei criteri. Ad esempio, un utente ' Grace Taylor ' verrebbe visualizzato con uno pseudonimo randomizzato come ' AnonIS8-988' in tutte le aree dell'esperienza di gestione dei rischi Insider. Se si sceglie questa impostazione, anonimizza tutti gli utenti con le corrispondenze di criteri correnti e precedenti e si applica a tutti i criteri. Le informazioni sui profili utente nell'avviso del rischio Insider e nei dettagli del caso non saranno disponibili quando si sceglie questa opzione. Tuttavia, i nomi utente vengono visualizzati quando si aggiungono nuovi utenti ai criteri esistenti o quando si assegnano gli utenti ai nuovi criteri. Se si sceglie di disattivare questa impostazione, i nomi utente verranno visualizzati per tutti gli utenti che hanno corrispondenze di criteri correnti o precedenti.
- Non vengono visualizzate le **versioni di anonimi dei nomi utente**: i nomi utente vengono visualizzati per tutte le corrispondenze di criteri correnti e precedenti per gli avvisi e i casi. Le informazioni sui profili utente, ovvero il nome, il titolo, l'alias e l'organizzazione o il reparto, vengono visualizzate per tutti gli avvisi e i casi di gestione dei rischi Insider.

![Impostazioni di privacy per la gestione dei rischi Insider](../media/insider-risk-settings-privacy.png)

## <a name="indicators"></a>Indicatori

I modelli di criteri per i rischi Insider definiscono il tipo di attività di rischio che si desidera rilevare ed esaminare. Ogni modello di criteri si basa su indicatori specifici che corrispondono a trigger specifici e attività a rischio. Tutti gli indicatori sono disattivati per impostazione predefinita ed è necessario selezionare uno o più indicatori di criteri prima di configurare un criterio di gestione dei rischi Insider.

Gli avvisi vengono attivati dai criteri quando gli utenti eseguono attività relative a indicatori di criteri che soddisfano una soglia obbligatoria. Gestione dei rischi Insider utilizza due tipi di indicatori:

- **Triggering Events**: eventi che determinano se un utente è attivo per un criterio di gestione dei rischi Insider. Se un utente viene aggiunto a un criterio di gestione dei rischi insider non ha un evento di attivazione, l'attività dell'utente non viene valutata dal criterio. Ad esempio, l'utente A viene aggiunto a un criterio creato dal modello *di criteri di furto dei dati da parte degli utenti* e il criterio e il connettore Microsoft 365 HR sono stati configurati correttamente. Fino a quando l'utente A ha una data di terminazione segnalata dal connettore HR, l'utente A attività non viene valutato da questo criterio di gestione dei rischi Insider per rischi. Un altro esempio di evento di attivazione è il caso in cui un utente abbia un avviso di criteri DLP di gravità *elevato* quando si utilizzano i criteri di *perdita dei dati* .
- **Indicatori di criteri**: indicatori inclusi nei criteri di gestione dei rischi Insider utilizzati per determinare un punteggio di rischio per un utente in ambito. Questi indicatori di criteri vengono attivati solo dopo che si è verificato un evento di attivazione per un utente. Alcuni esempi di indicatori di criteri si verificano quando un utente copia i dati in servizi di archiviazione cloud personali o dispositivi di archiviazione portatili oppure se un utente condivide file e cartelle interni con parti esterne non autorizzate.

Gli indicatori dei criteri sono segmentati nelle aree seguenti. È possibile scegliere gli indicatori per attivare e personalizzare i limiti degli eventi indicatori per ogni livello di indicatore quando si crea un criterio di rischio Insider:

- **Indicatori di Office**: includono indicatori dei criteri per i siti di SharePoint, i team e la messaggistica di posta elettronica.
- **Indicatori del dispositivo**: includono indicatori dei criteri per attività quali la condivisione di file sulla rete o con i dispositivi. Gli indicatori includono attività relative ai file di Microsoft Office. File CSV e. File PDF. Se si selezionano gli **indicatori di dispositivo**, l'attività viene elaborata solo per i dispositivi con Windows 10 Build 1809 o versione successiva. Per ulteriori informazioni sulla configurazione dei dispositivi per l'integrazione con rischio Insider, vedere [Guida introduttiva a Endpoint DLP](endpoint-dlp-getting-started.md).
- **Indicatore di violazione dei criteri di sicurezza**: sono inclusi gli indicatori di Microsoft Defender ATP relativi all'installazione di software non approvato o dannoso o al bypassare i controlli di sicurezza. Per ricevere avvisi in gestione dei rischi Insider, è necessario disporre di una licenza di Microsoft Defender ATP attiva e l'integrazione dei rischi Insider abilitata. Per ulteriori informazioni sulla configurazione di Microsoft Defender ATP per l'integrazione di gestione dei rischi Insider, vedere [configure advanced features in Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-features\#share-endpoint-alerts-with-microsoft-compliance-center).
- **Booster del Punteggio di rischio**: tra cui l'aumento del Punteggio di rischio per attività inusuali o precedenti violazioni dei criteri. Abilitazione del Punteggio di rischio i Booster aumentano i punteggi dei rischi e la probabilità di avvisi per questi tipi di attività. I booster del Punteggio di rischio possono essere selezionati solo se sono stati selezionati uno o più indicatori sopra riportati.

![Impostazioni degli indicatori di gestione dei rischi Insider](../media/insider-risk-settings-indicators.png)

In alcuni casi, è possibile che si desideri limitare gli indicatori dei criteri di rischio Insider applicati ai criteri di insider Risk nell'organizzazione. È possibile disattivare gli indicatori dei criteri per aree specifiche disattivando tutti i criteri di rischio Insider. Non è possibile modificare gli eventi di attivazione per i modelli di criteri di rischio Insider.

Per definire gli indicatori dei criteri di rischio Insider abilitati in tutti i criteri di rischio Insider, passare a indicatori **delle impostazioni dei rischi Insider**  >  **Indicators** e selezionare uno o più indicatori di criteri. Gli indicatori selezionati nella pagina Impostazioni indicatori non possono essere configurati singolarmente quando si crea o si modifica un criterio di rischio Insider nella procedura guidata dei criteri.

>[!NOTE]
>Potrebbe essere necessario diverse ore prima che i nuovi utenti aggiunti manualmente vengano visualizzati nel **dashboard degli utenti**. Le attività per i 90 giorni precedenti per questi utenti possono richiedere fino a 24 ore per la visualizzazione. Per visualizzare le attività per gli utenti aggiunti manualmente, selezionare l'utente nel **Dashboard utenti** e aprire la scheda **attività utente** nel riquadro dei dettagli.

### <a name="indicator-level-settings-preview"></a>Impostazioni livello indicatore (anteprima)

Quando si crea un criterio nella procedura guidata per i criteri, è possibile configurare in che modo il numero giornaliero di eventi di rischio deve influire sul punteggio di rischio per gli avvisi di rischio Insider. Queste impostazioni degli indicatori consentono di controllare il modo in cui il numero di occorrenze di eventi di rischio nell'organizzazione deve influire sul punteggio di rischio e, di conseguenza, sulla gravità degli avvisi associata, per questi eventi. Se si preferisce, è anche possibile scegliere di mantenere i livelli di soglia di evento predefiniti consigliati da Microsoft per tutti gli indicatori abilitati.

Ad esempio, si decide di abilitare gli indicatori di SharePoint nelle impostazioni dei criteri di rischio Insider e di impostare soglie personalizzate per gli eventi di SharePoint quando si configurano gli indicatori per un nuovo criterio di *perdita dei dati* Insider rischio. Durante la creazione guidata criteri di rischio Insider, vengono configurati tre diversi livelli di eventi giornalieri per ogni indicatore di SharePoint in modo da influenzare il Punteggio di rischio per gli avvisi associati a tali eventi.

![Impostazioni degli indicatori personalizzati per la gestione dei rischi Insider](../media/insider-risk-custom-indicators.png)

Per il primo livello di evento giornaliero, impostare la soglia a *10 o più eventi al giorno* per un impatto minore sul punteggio di rischio per gli eventi, *20 o più eventi al giorno* per un impatto medio sul punteggio di rischio per gli eventi e *30 o più eventi al giorno* un impatto maggiore sul punteggio di rischio per gli eventi. Queste impostazioni indicano in modo efficace:

- Se sono presenti 1-9 eventi di SharePoint che si verificano dopo l'evento triggering, i punteggi del rischio hanno un impatto minimo e tendono a non generare un avviso.
- Se sono presenti 10-19 eventi di SharePoint che si verificano dopo un evento di attivazione, il Punteggio di rischio è intrinsecamente inferiore e i livelli di gravità degli avvisi tendono a essere a un livello basso.
- Se sono presenti 20-29 eventi di SharePoint che si verificano dopo un triggering, il Punteggio di rischio è intrinsecamente più elevato e i livelli di gravità degli avvisi tendono a essere a un livello medio.
- Se sono presenti 30 o più eventi di SharePoint che si verificano dopo un triggering, il Punteggio di rischio è intrinsecamente più elevato e i livelli di gravità degli avvisi tendono a essere a un livello elevato.

## <a name="policy-timeframes"></a>Intervalli di tempo per i criteri

Gli intervalli di tempo dei criteri consentono di definire i periodi di revisione precedenti e futuri che vengono attivati dopo le corrispondenze dei criteri in base a eventi e attività per i modelli di criteri di gestione del rischio Insider. A seconda del modello di criteri scelto, sono disponibili i seguenti tempi di criteri:

- **Finestra di attivazione**: disponibile per tutti i modelli di criteri, la *finestra di attivazione* è il numero definito di giorni in cui la finestra viene attivata **dopo** un evento di trigger. La finestra viene attivata da 1 a 30 giorni dopo che si è verificato un evento di attivazione per qualsiasi utente assegnato al criterio. Ad esempio, è stato configurato un criterio di gestione dei rischi Insider e impostare la *finestra di attivazione* su 30 giorni. Sono passati diversi mesi da quando è stato configurato il criterio e si verifica un evento di attivazione per uno degli utenti inclusi nel criterio. L'evento triggering attiva la *finestra di attivazione* e il criterio è attivo per l'utente per 30 giorni dopo l'evento triggering.
- **Rilevamento attività precedenti**: disponibile per tutti i modelli di criteri, il *rilevamento delle attività precedenti* è il numero definito di giorni in cui la finestra viene attivata **prima** di un evento di attivazione. La finestra viene attivata da 0 a 180 giorni prima che si verifichi un evento di attivazione per qualsiasi utente assegnato al criterio. Ad esempio, è stato configurato un criterio di gestione dei rischi Insider e il *rilevamento delle attività precedenti* è stato impostato su 90 giorni. Sono passati diversi mesi da quando è stato configurato il criterio e si verifica un evento di attivazione per uno degli utenti inclusi nel criterio. L'evento triggering attiva il *rilevamento delle attività precedenti* e il criterio raccoglie le attività storiche per quell'utente per 90 giorni prima dell'evento triggering.

![Impostazioni di calendario per la gestione dei rischi Insider](../media/insider-risk-settings-timeframes.png)

## <a name="intelligent-detections"></a>Rilevamenti intelligenti

Le impostazioni di rilevamento intelligente consentono di affinare la modalità di elaborazione dei rilevamenti delle attività rischiose per gli avvisi. In alcuni casi, potrebbe essere necessario definire i tipi di file da ignorare o si desidera applicare un livello di rilevamento per i file che consentono di definire una barra minima per gli avvisi. Quando si utilizzano criteri di linguaggio offensivi, potrebbe essere necessario aumentare o diminuire la sensibilità di rilevamento per controllare la quantità di corrispondenze di criteri segnalate. Utilizzare queste impostazioni per controllare il volume generale degli avvisi, le esclusioni dei tipi di file, i limiti relativi al volume del file e la sensibilità all'individuazione del linguaggio offensivo.

![Impostazioni per i rilevamenti intelligenti di gestione dei rischi](../media/insider-risk-settings-detections.png)

### <a name="anomaly-detections"></a>Rilevamenti di anomalia

I rilevamenti anomali includono le impostazioni per le esclusioni dei tipi di file e i limiti del volume file.

- **Esclusioni**dei tipi di file: per escludere tipi di file specifici da tutti i criteri di gestione dei rischi Insider, immettere le estensioni del tipo di file separate da virgole. Ad esempio, per escludere determinati tipi di file musicali dalle corrispondenze di criteri, è possibile immettere *AAC, MP3, WAV, WMA* nel campo **esclusioni tipo di file** . I file con queste estensioni verrebbero ignorati da tutti i criteri di gestione dei rischi Insider.
- **Limite di riduzione del volume del file**: per definire un livello di file minimo prima che vengano segnalati avvisi attività nei criteri di rischio Insider, immettere il numero di file. Ad esempio, è necessario immettere '10 ' se non si desidera generare avvisi di rischio Insider quando un utente Scarica 10 file o meno, anche se i criteri considerano questa attività un'anomalia.

### <a name="offensive-language-detections"></a>Rilevamenti di lingua offensiva

>[!IMPORTANT]
>A partire dal 16 ottobre 2020, non sarà più possibile creare criteri utilizzando questo modello. Tutti i criteri attivi che utilizzano questo modello funzioneranno fino a quando non verranno rimossi definitivamente nel gennaio 2021. Il classificatore incorporato del linguaggio offensivo che supporta questo modello è obsoleto perché produce un numero elevato di falsi positivi. Per risolvere i problemi di rischio per la lingua offensiva, è consigliabile utilizzare i criteri di [conformità alla comunicazione](communication-compliance.md) Microsoft 365. Per ulteriori informazioni sui classificatori incorporati, vedere [Guida introduttiva ai classificatori addestrabili](classifier-get-started-with.md).

Per modificare la sensibilità del classificatore dei linguaggi offensivi per i criteri che utilizzano la *lingua offensiva nel modello di posta elettronica* , scegliere una delle seguenti impostazioni:

- **Low**: il livello di sensibilità più basso con l'intervallo più ampio per il rilevamento del linguaggio offensivo e del sentimento. La probabilità di falsi positivi per la corrispondenza di lingua offensiva è elevata.
- **Medium**: livello di sensibilità medio-livello con un intervallo bilanciato per il rilevamento del linguaggio offensivo e del sentimento. La probabilità di falsi positivi per la corrispondenza dei linguaggi offensivi è media.
- **High**: il livello di sensibilità più alto con un intervallo ristretto per il rilevamento del linguaggio offensivo e del sentimento. La probabilità di falsi positivi per la corrispondenza di lingua offensiva è bassa.

### <a name="alert-volume"></a>Volume avvisi

Le attività degli utenti rilevate dai criteri di rischio Insider sono assegnate a un punteggio di rischio specifico, che a sua data determina la gravità degli avvisi (basso, medio, alto). Per impostazione predefinita, viene generato un determinato numero di avvisi di bassa, media e elevata gravità, ma è possibile aumentare o diminuire il volume in base alle proprie esigenze. Per modificare il volume degli avvisi per tutti i criteri di gestione dei rischi Insider, scegliere una delle seguenti impostazioni:

- **Meno avvisi**: verranno visualizzati tutti gli avvisi di gravità elevata, meno avvisi di gravità media e nessun livello di gravità basso. Questo livello di impostazione significa che potrebbe essere possibile perdere alcuni veri positivi.
- **Volume predefinito**: verranno visualizzati tutti gli avvisi di gravità elevata e una quantità bilanciata di avvisi di gravità medio-bassa.
- **Altri avvisi**: vedrai tutti gli avvisi di gravità media e alta e la maggior parte degli avvisi di gravità bassa. Questo livello di impostazione può comportare un numero maggiore di falsi positivi.

### <a name="microsoft-defender-advanced-threat-protection-preview"></a>Protezione avanzata dalle minacce di Microsoft Defender (anteprima)

[Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) (ATP) è una piattaforma di sicurezza per endpoint Enterprise progettata per aiutare le reti aziendali a impedire, rilevare, analizzare e rispondere alle minacce avanzate. Per una migliore visibilità della violazione della sicurezza nell'organizzazione, è possibile importare e filtrare gli avvisi ATP di Microsoft Defender per le attività utilizzate nei criteri creati da modelli di criteri di violazione della sicurezza di gestione dei rischi Insider Management.

A seconda dei tipi di segnali che sono interessati, è possibile scegliere di importare avvisi per la gestione dei rischi insider in base allo stato di valutazione dell'avviso ATP Microsoft Defender. È possibile definire uno o più dei seguenti stati di valutazione degli avvisi nelle impostazioni globali da importare:

- Unknown
- Nuova
- In corso
- Risolti

Gli avvisi di Microsoft Defender ATP vengono importati ogni giorno. A seconda dello stato di valutazione scelto, è possibile che vengano visualizzate più attività utente per lo stesso avviso delle modifiche allo stato del triage in Microsoft Defender ATP.

Ad esempio, se si seleziona *nuovo*, *in corso*e *risolto* per questa impostazione, quando viene generato un avviso ATP di Microsoft Defender e lo stato è *nuovo*, viene importata un'attività di avviso iniziale per l'utente in Risk Insider. Quando lo stato del Triage ATP Microsoft Defender cambia *in corso*, viene importata una seconda attività per questo avviso per l'utente in rischio Insider. Quando viene impostato lo stato di valutazione ATP Microsoft Defender finale di *risolto* , viene importata una terza attività per questo avviso per l'utente in Risk Insider. Questa funzionalità consente agli inquirenti di seguire la progressione degli avvisi di Microsoft Defender ATP e di scegliere il livello di visibilità richiesto dall'indagine.

>[!IMPORTANT]
>Per importare gli avvisi relativi alla violazione di sicurezza, è necessario che Microsoft Defender ATP sia configurato nell'organizzazione e abilitare Microsoft Defender ATP per l'integrazione di gestione dei rischi Insider nel centro sicurezza protezione. Per ulteriori informazioni sulla configurazione di Microsoft Defender ATP per l'integrazione di gestione dei rischi Insider, vedere [configure advanced features in Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-features\#share-endpoint-alerts-with-microsoft-compliance-center).

### <a name="domains-preview"></a>Domini (anteprima)

Le impostazioni del dominio consentono di definire i livelli di rischio per le comunicazioni verso domini specifici. Tali comunicazioni includono file di condivisione, messaggi di posta elettronica o download di contenuto. Specificando i domini in queste impostazioni, è possibile aumentare o diminuire il rischio segnando per attività che si svolge con questi domini. Ad esempio, per specificare contoso.com e sales.wingtiptoys.com come domini consentiti, immettere ' contoso.com sales.wingtiptoys.com ' nel campo **domini consentiti** .

Per ognuna delle impostazioni di dominio seguenti, è possibile immettere fino a 500 domini:

- **Domini non consentiti:** Se si specificano domini non consentiti, le attività che si verificano con questi domini avranno un punteggio di rischio *maggiore* .
- **Domini consentiti:** Se si specificano domini consentiti nelle impostazioni, le attività che si verificano con questi domini avranno un punteggio di rischio *inferiore* e verranno trattate in modo analogo a come viene trattata l'attività organizzativa interna. Ad esempio, le attività di posta elettronica a questi domini vengono analizzate in modo analogo a come viene analizzata l'attività di posta elettronica interna.
- **Domini di terze parti:** I domini di terze parti sono domini utilizzati a fini commerciali all'interno dell'organizzazione e i contenuti sensibili possono essere archiviati in queste posizioni. Specificando un dominio di terze parti, è possibile ricevere avvisi per qualsiasi attività rischiosa su questi domini.

## <a name="export-alerts-preview"></a>Avvisi di esportazione (anteprima)

Informazioni sugli avvisi di gestione dei rischi Insider sono esportabili in servizi di gestione eventi e informazioni di sicurezza tramite lo [schema API di attività di gestione di Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#security-and-compliance-alerts-schema). È possibile utilizzare le API di attività di gestione di Office 365 per esportare le informazioni di avviso in altre applicazioni che possono essere utilizzate dall'organizzazione per gestire o aggregare informazioni sui rischi Insider.

Per utilizzare le API per esaminare le informazioni sugli avvisi dei rischi Insider:

1. Abilitare il supporto API di gestione delle attività di Office 365 nell'esportazione delle impostazioni di **gestione rischi Insider**  >  **Settings**  >  **Export**. Per impostazione predefinita, questa impostazione è disabilitata per l'organizzazione Microsoft 365.
2. Filtrare le attività di controllo comuni di Office 365 da *SecurityComplianceAlerts*.
3. Filtrare *SecurityComplianceAlerts* dalla categoria *InsiderRiskManagement* .

![Impostazioni di avviso di esportazione di gestione dei rischi Insider](../media/insider-risk-settings-export.png)

Le informazioni sugli avvisi contengono informazioni provenienti dallo schema di avviso per la sicurezza e la conformità e lo schema comune API di attività di gestione di Office 365.

I campi e i valori seguenti vengono esportati per gli avvisi di gestione dei rischi Insider per lo schema di avviso conformità & di sicurezza:

| **Parametro Alert** | **Descrizione** |
|:------------------|:----------------|
| AlertType | Il tipo di avviso è *Custom*.  |
| AlertId | Il GUID dell'avviso. Gli avvisi di gestione rischi Insider sono modificabili. Quando viene modificato lo stato di avviso, viene generato un nuovo log con lo stesso AlertID. Questo AlertID può essere utilizzato per correlare gli aggiornamenti per un avviso. |
| Categoria | La categoria dell'avviso è *InsiderRiskManagement*. Questa categoria può essere utilizzata per distinguere gli avvisi da altri avvisi di sicurezza & conformità. |
| Commenti | Commenti predefiniti per l'avviso. I valori sono un *nuovo avviso* (registrato quando viene creato un avviso) e l'avviso è stato *aggiornato* (registrato quando è presente un aggiornamento a un avviso). Utilizzare AlertID per correlare gli aggiornamenti per un avviso. |
| Dati | I dati per l'avviso includono l'ID utente univoco, il nome dell'entità utente e la data e l'ora (UTC) quando l'utente è stato attivato in un criterio. |
| Nome | Nome del criterio per i criteri di gestione dei rischi Insider che hanno generato l'avviso. |
| PolicyId | Il GUID del criterio di gestione dei rischi Insider che ha attivato l'avviso. |
| Gravità | La gravità dell'avviso. I valori sono *alto*, *medio*o *basso*. |
| Origine | L'origine dell'avviso. Il valore è *Office 365 Security & Compliance*. |
| Stato | Lo stato dell'avviso. I valori *sono attivi* (è*necessario riesaminare* i rischi Insider), *indagare* (*confermato* nel rischio Insider), *risolto* (*risolto* in rischio Insider), *respinto* (*respinto* dal rischio Insider). |
| Version | La versione dello schema di avviso per la sicurezza e la conformità. |

I campi e i valori seguenti vengono esportati per gli avvisi di gestione dei rischi Insider per lo [schema comune API di gestione attività di Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema).

- UserId
- Id
- RecordType
- CreationTime
- Operazione
- OrganizationId
- UserType
- UserKey

## <a name="priority-user-groups-preview"></a>Gruppi di utenti prioritari (anteprima)

Gli utenti dell'organizzazione possono avere livelli di rischio diversi a seconda della posizione, del livello di accesso alle informazioni riservate o della cronologia dei rischi. La definizione di priorità per l'esame e il punteggio delle attività di tali utenti può essere di aiuto per individuare potenziali rischi che potrebbero avere conseguenze più elevate per l'organizzazione. I gruppi di utenti prioritari per la gestione dei rischi Insider consentono di definire gli utenti dell'organizzazione che richiedono un controllo più attento e un punteggio più sensibile ai rischi. Insieme alle violazioni dei *criteri di sicurezza per gli utenti con priorità* e le *perdite di dati da* parte dei modelli di criteri per gli utenti prioritari, gli utenti aggiunti a un gruppo di utenti prioritari hanno aumentato la probabilità di avvisi e avvisi con livelli di gravità superiori.

![Impostazioni di priorità del gruppo di utenti prioritari di gestione dei rischi](../media/insider-risk-settings-priority-users.png)

Ad esempio, è necessario proteggersi dalle perdite di dati per un progetto estremamente riservato, in cui gli utenti possono accedere alle informazioni riservate. Si sceglie di creare un gruppo di utenti prioritario di un utente di *Project riservato* *per gli utenti* dell'organizzazione che lavorano su questo progetto. Se si utilizza la creazione guidata criteri e le *perdite di dati per il modello di criteri degli utenti prioritari* , è possibile creare un nuovo criterio e assegnare il gruppo di utenti prioritari per gli utenti di *progetto riservato* al criterio. Le attività esaminate dal criterio per i membri del gruppo di utenti prioritari di *Project riservata agli* utente sono più sensibili ai rischi e alle attività da parte di questi utenti avranno maggiori probabilità di generare un avviso e di avere avvisi con livelli di gravità superiori.

### <a name="create-a-priority-user-group"></a>Creare un gruppo di utenti prioritari

Per creare un nuovo gruppo di utenti prioritari, verranno utilizzati i controlli di impostazione nella soluzione di **gestione dei rischi Insider** nel centro conformità di Microsoft 365. Per creare un gruppo di utenti prioritari, è necessario essere membri del gruppo di ruoli amministratore *Insider Risk Management* o *Insider Management* .

Completare la procedura seguente per creare un gruppo di utenti prioritari:

1. Nel [centro conformità di Microsoft 365](https://compliance.microsoft.com), accedere a **gestione dei rischi Insider** e selezionare **impostazioni di rischio Insider**.
2. Selezionare la scheda **gruppi di utenti prioritari**
3. Nella scheda **gruppi di utenti prioritari** selezionare **Crea gruppo utenti prioritari** per avviare la creazione guidata gruppo.
4. Nella pagina **Definisci gruppo** , completare i seguenti campi:
    - **Nome (obbligatorio)**: immettere un nome descrittivo per il gruppo di utenti prioritari. Non è possibile modificare il nome del gruppo di utenti prioritari dopo aver completato la procedura guidata.
    - **Description (facoltativo)**: immettere una descrizione per il gruppo di utenti prioritari.
5. Fare clic su **Avanti** per continuare.
6. Nella pagina **Scegli membri** selezionare Seleziona **membri** da cercare e selezionare gli account utente abilitati alla posta elettronica inclusi nel gruppo oppure selezionare la casella di controllo **Seleziona tutto** per aggiungere tutti gli utenti dell'organizzazione al gruppo. Fare clic su **Aggiungi** per continuare o su **Annulla** per chiudere senza aggiungere utenti al gruppo.
7. Fare clic su **Avanti** per continuare.
8. Nella pagina **Revisione** rivedere le impostazioni selezionate per il gruppo di utenti prioritari. Selezionare **modifica** per modificare qualsiasi valore del gruppo o selezionare **Invia** per creare e attivare il gruppo di utenti prioritari.
9. Nella pagina conferma, fare clic su **fine** per uscire dalla procedura guidata.

### <a name="update-a-priority-user-group"></a>Aggiornare un gruppo di utenti prioritari

Per aggiornare un gruppo di utenti prioritari esistente, è possibile utilizzare l'impostazione dei controlli nella soluzione di **gestione dei rischi Insider** nel centro conformità di Microsoft 365. Per aggiornare un gruppo di utenti prioritari, è necessario essere membri del gruppo di ruoli amministratore *Insider Risk Management* o *Insider Management* .

Completare la procedura seguente per modificare un gruppo di utenti prioritari:

1. Nel [centro conformità di Microsoft 365](https://compliance.microsoft.com), accedere a **gestione dei rischi Insider** e selezionare **impostazioni di rischio Insider**.
2. Selezionare la scheda **gruppi di utenti prioritari**
3. Selezionare il gruppo di utenti prioritari che si desidera modificare e selezionare **modifica gruppo**.
4. Nella pagina **Definisci gruppo** , aggiornare il campo Descrizione, se necessario. Non è possibile aggiornare il nome del gruppo di utenti prioritari. Fare clic su **Avanti** per continuare.
5. Nella pagina **Scegli membri** aggiungere nuovi membri al gruppo utilizzando il controllo **Scegli membri** . Per rimuovere un utente dal gruppo, selezionare là X ' accanto all'utente che si desidera rimuovere. Fare clic su **Avanti** per continuare.
6. Nella pagina **Revisione** , esaminare le impostazioni di aggiornamento selezionate per il gruppo di utenti prioritari. Selezionare **modifica** per modificare qualsiasi valore del gruppo o selezionare **Invia** per aggiornare il gruppo di utenti prioritari.
7. Nella pagina conferma, fare clic su **fine** per uscire dalla procedura guidata.

### <a name="delete-a-priority-user-group"></a>Eliminare un gruppo di utenti prioritari

Per eliminare un gruppo di utenti prioritari esistente, è possibile utilizzare l'impostazione dei controlli nella soluzione di **gestione dei rischi Insider** nel centro conformità di Microsoft 365. Per eliminare un gruppo di utenti prioritari, è necessario essere membri del gruppo di ruoli amministratore *Insider Risk Management* o *Insider Management* .

>[!IMPORTANT]
>L'eliminazione di un gruppo di utenti prioritari lo rimuove da qualsiasi criterio attivo a cui è assegnato. Se si elimina un gruppo di utenti prioritari assegnato a un criterio attivo, il criterio non conterrà alcun utente nell'ambito e sarà effettivamente inattivo e non creerà avvisi.

Completare la procedura seguente per eliminare un gruppo di utenti prioritari:

1. Nel [centro conformità di Microsoft 365](https://compliance.microsoft.com), accedere a **gestione dei rischi Insider** e selezionare **impostazioni di rischio Insider**.
2. Selezionare la scheda **gruppi di utenti prioritari**
3. Selezionare il gruppo di utenti prioritari che si desidera modificare e selezionare **Elimina** dal menu del dashboard.
4. Nella finestra di dialogo **Elimina** fare clic su **Sì** per eliminare il gruppo di utenti prioritari o su **Annulla** per tornare al dashboard.

## <a name="priority-physical-assets-preview"></a>Risorse fisiche prioritarie (anteprima)

L'identificazione dell'accesso alle risorse fisiche prioritarie e la correlazione dell'attività di accesso agli eventi degli utenti è un componente importante dell'infrastruttura di conformità. Tali risorse fisiche rappresentano le posizioni prioritarie nell'organizzazione, ad esempio edifici aziendali, Data Center o sale server. Le attività di rischio Insider possono essere associate a utenti che lavorano in ore inusuali, tentando di accedere a queste aree non autorizzate sensibili o sicure e le richieste di accesso a aree di alto livello senza necessità legittime.

Con le risorse fisiche prioritarie abilitate e il [connettore di dati fisico di badging](import-physical-badging-data.md) configurato, la gestione dei rischi Insider integra i segnali provenienti dai sistemi di controllo fisico e di accesso con altre attività a rischio utente. Esaminando i modelli di comportamento tra i sistemi di accesso fisico e la correlazione di tali attività con altri eventi di rischio Insider, la gestione dei rischi Insider può aiutare gli inquirenti e gli analisti a prendere decisioni di risposta più informate sugli avvisi. L'accesso alle risorse fisiche prioritarie è segnato e identificato in modo diverso dall'accesso a risorse non prioritarie.

Ad esempio, l'organizzazione dispone di un sistema di badging per gli utenti che monitorano e approvano l'accesso fisico alle normali aree di lavoro e di progetto sensibili. Si dispone di più utenti che lavorano su un progetto sensibile e questi utenti torneranno ad altre aree dell'organizzazione al termine del progetto. Dopo il completamento del progetto sensibile, è necessario assicurarsi che il lavoro del progetto rimanga riservato e che l'accesso alle aree del progetto sia strettamente controllato.

È possibile scegliere di abilitare il connettore dati fisico di badging in Microsoft 365 per importare le informazioni di accesso dal sistema di badging fisico e specificare le risorse fisiche prioritarie nella gestione dei rischi Insider. Importando informazioni dal sistema badging e correlando le informazioni di accesso fisico ad altre attività a rischio identificate in gestione dei rischi Insider, si noterà che uno degli utenti del progetto sta accedendo agli uffici progetti dopo l'orario di lavoro normale ed esporta anche grandi quantità di dati in un servizio di archiviazione cloud personale dall'area di lavoro normale. Questa attività di accesso fisico associata all'attività online può indicare possibili furti di dati e ricercatori di conformità e gli analisti possono intraprendere azioni appropriate come indicato dalle circostanze per questo utente.

### <a name="configure-priority-physical-assets"></a>Configurare le risorse fisiche prioritarie

Per configurare le risorse fisiche prioritarie, è necessario configurare il connettore fisico di badging e utilizzare l'impostazione dei controlli nella soluzione di **gestione dei rischi Insider** nel centro conformità di Microsoft 365. Per configurare le risorse fisiche prioritarie, è necessario essere membri del gruppo di ruoli amministratore *Insider Risk Management* o *Insider Management*.

Completare la procedura seguente per configurare le risorse fisiche prioritarie:

1. Seguire i passaggi di configurazione per la gestione dei rischi Insider nell'articolo [Guida introduttiva ai rischi Insider Management](insider-risk-management-configure.md) . Nel passaggio 3, verificare di aver configurato il connettore fisico di badging.

    >[!IMPORTANT]
    >Per i criteri di gestione dei rischi Insider per l'utilizzo e la correlazione dei dati del segnale relativi agli utenti che partono e terminano con i dati degli eventi dalle piattaforme di controllo e accesso fisico, è necessario configurare anche il connettore Microsoft 365 HR. Se si Abilita il connettore fisico di badging senza abilitare il connettore Microsoft 365 HR, i criteri di gestione dei rischi Insider elaborerà solo gli eventi per le attività di accesso fisico per gli utenti dell'organizzazione.

2. Nel [centro conformità Microsoft 365](https://compliance.microsoft.com), accedere a **gestione dei rischi Insider** e selezionare risorse fisiche prioritarie priorità **delle impostazioni di rischio Insider**  >  **Priority physical assets**.
3. Nella pagina **risorse fisiche prioritarie** è possibile aggiungere manualmente gli ID di risorsa fisica che si desidera monitorare per gli eventi patrimoniali importati dal connettore badging fisico o importare un. File CSV di tutti gli ID risorse fisiche importati dal connettore badging fisico: a) per aggiungere manualmente gli ID risorse fisiche, scegliere **Aggiungi risorse fisiche prioritarie**, immettere un ID risorsa fisica e quindi fare clic su **Aggiungi**. Immettere ulteriori ID asset fisici e quindi selezionare **Aggiungi risorse fisiche prioritarie** per salvare tutti gli asset immessi.
    b) per aggiungere un elenco di ID asset fisici da a. File CSV, scegliere **Importa risorse fisiche prioritarie**. Nella finestra di dialogo Esplora file selezionare il. File CSV che si desidera importare, quindi selezionare **Apri**. Gli ID delle risorse fisiche del. I file CSV vengono aggiunti all'elenco.
4. Passare alla scheda **indicatori dei criteri** in impostazioni.
5. Nella pagina **indicatori di criteri** , passare alla sezione **indicatori di accesso fisico** e selezionare la casella di controllo per l' **accesso fisico dopo la terminazione o l'accesso non riuscito a Asset riservati**.
6. Selezionare **Salva** per configurare ed uscire.

### <a name="delete-a-priority-physical-asset"></a>Eliminare una risorsa fisica prioritaria

Per eliminare una risorsa fisica prioritaria esistente, è possibile utilizzare l'impostazione dei controlli nella soluzione di gestione dei rischi Insider nel centro conformità di Microsoft 365. Per eliminare una risorsa fisica prioritaria, è necessario essere membri del gruppo di ruoli amministratore Insider Risk Management o insider Management.

>[!IMPORTANT]
>L'eliminazione di una risorsa fisica prioritaria la rimuove dall'esame da qualsiasi criterio attivo a cui era stato precedentemente incluso. Gli avvisi generati da attività associate alla risorsa fisica prioritaria non vengono eliminati.

Completare la procedura seguente per eliminare una risorsa fisica prioritaria:

1. Nel [centro conformità Microsoft 365](https://compliance.microsoft.com), accedere a **gestione dei rischi Insider** e selezionare risorse fisiche prioritarie priorità **delle impostazioni di rischio Insider**  >  **Priority physical assets**.
2. Nella pagina **risorse fisiche prioritarie** selezionare il bene che si desidera eliminare.
3. Scegliere **Elimina** dal menu azione per eliminare il bene.

## <a name="power-automate-flows-preview"></a>Flussi automatizzati di alimentazione (anteprima)

[Microsoft Power automatizzate](https://docs.microsoft.com/power-automate/getting-started) è un servizio di flusso di lavoro che automatizza le azioni tra le applicazioni e i servizi. Utilizzando flussi provenienti da modelli o creati manualmente, è possibile automatizzare le attività comuni associate a queste applicazioni e servizi. Quando si abilitano i flussi automatici di alimentazione per la gestione dei rischi Insider, è possibile automatizzare le attività importanti per i casi e gli utenti. È possibile configurare i flussi automatici di alimentazione per recuperare informazioni sugli utenti, gli avvisi e i casi e condividere queste informazioni con le parti interessate e altre applicazioni, nonché automatizzare le azioni in gestione dei rischi Insider, ad esempio la pubblicazione di note di caso. I flussi automatici di alimentazione sono applicabili per i casi e per qualsiasi utente nell'ambito di un criterio.

I clienti con abbonamenti Microsoft 365 che includono la gestione dei rischi insider non necessitano di ulteriori licenze di automatizzazione dell'alimentazione per utilizzare i modelli di automatizzazione di Power Management dei rischi consigliati. Questi modelli possono essere personalizzati per supportare l'organizzazione e coprire gli scenari di gestione dei rischi Insider core. Se si sceglie di utilizzare le funzionalità di automatizzazione di Power Premium in questi modelli, creare un modello personalizzato utilizzando il connettore di conformità di Microsoft 365 o utilizzare i modelli Power Automate per altre aree di conformità in Microsoft 365, potrebbe essere necessario disporre di licenze aggiuntive per automatizzare la potenza.

I seguenti modelli di automatizzazione dei poteri vengono forniti ai clienti per supportare l'automazione dei processi per gli utenti e i casi di gestione del rischio Insider:

- **Informare gli utenti quando vengono aggiunti a un criterio di rischio Insider**: questo modello è per le organizzazioni che dispongono di criteri interni, privacy o requisiti normativi che gli utenti devono ricevere una notifica quando sono soggetti a criteri di gestione dei rischi Insider. Quando questo flusso è configurato e selezionato per un utente nella pagina utenti, gli utenti e i loro manager ricevono un messaggio di posta elettronica quando l'utente viene aggiunto a un criterio di gestione dei rischi Insider. Questo modello supporta anche l'aggiornamento di un elenco di SharePoint ospitato in un sito di SharePoint per consentire di tenere presenti i dettagli dei messaggi di notifica come data/ora e il destinatario del messaggio. Se si è scelto di anonimizzare gli utenti in **impostazioni di privacy**, i flussi creati da questo modello non funzioneranno come previsto in modo che la privacy degli utenti venga mantenuta. I flussi automatici di alimentazione con questo modello sono disponibili nel **dashboard degli utenti**.
- **Richiedere informazioni da HR o business su un utente in un caso di rischio Insider**: quando si agisce su un caso, gli analisti e gli investigatori del rischio Insider possono dover consultare HR o altre parti interessate per comprendere il contesto delle attività del caso. Quando questo flusso è configurato e selezionato per un caso, gli analisti e gli investigatori inviano un messaggio di posta elettronica alle parti interessate HR e business configurate per questo flusso. Ogni destinatario viene inviato un messaggio con opzioni di risposta preconfigurate o personalizzabili. Quando i destinatari selezionano un'opzione di risposta, la risposta viene registrata come nota del caso e include informazioni su destinatario e data/ora. Se si è scelto di anonimizzare gli utenti in **impostazioni di privacy**, i flussi creati da questo modello non funzioneranno come previsto in modo che la privacy degli utenti venga mantenuta. I flussi automatici di alimentazione con questo modello sono disponibili nel **dashboard dei casi**.
- **Gestione notifiche quando un utente dispone di un avviso di rischio Insider**: alcune organizzazioni potrebbero dover avere una notifica di gestione immediata quando un utente dispone di un avviso di gestione dei rischi Insider. Quando questo flusso è configurato e selezionato, il responsabile dell'utente del caso viene inviato un messaggio di posta elettronica con le seguenti informazioni su tutti gli avvisi di caso: 
    - Criterio applicabile per l'avviso
    - Data/ora dell'avviso
    - Livello di gravità dell'avviso

    Il flusso aggiorna automaticamente le note del caso in cui il messaggio è stato inviato e che il flusso è stato attivato. Se si è scelto di anonimizzare gli utenti in **impostazioni di privacy**, i flussi creati da questo modello non funzioneranno come previsto in modo che la privacy degli utenti venga mantenuta. I flussi automatici di alimentazione con questo modello sono disponibili nel **dashboard dei casi**.

- **Aggiungere un promemoria del calendario per il follow-up di un caso di rischio Insider**: questo modello consente agli investigatori e agli analisti del rischio di aggiungere promemoria del calendario per i casi al calendario di Office 365 Outlook. Questo flusso Elimina la necessità per gli utenti di uscire o di disattivare il flusso di lavoro di gestione dei rischi Insider quando si elaborano i casi e gli avvisi di Triaging. Quando questo flusso è configurato e selezionato, viene aggiunto un promemoria al calendario di Outlook di Office 365 per l'utente che esegue il flusso. I flussi automatici di alimentazione con questo modello sono disponibili nel **dashboard dei casi**.

### <a name="create-a-power-automate-flow-from-insider-risk-management-template"></a>Creare un flusso automatico di alimentazione automatizzato dal modello di gestione dei rischi Insider

Per creare un flusso di automatizzazione di potenza da un modello consigliato di gestione dei rischi Insider, è possibile utilizzare i controlli delle impostazioni nella soluzione di **gestione dei rischi Insider** nel centro conformità Microsoft 365 o l'opzione **Gestisci flussi automatici di alimentazione** dal controllo **automatizzare** quando si lavora direttamente nei dashboard dei **casi** o **degli utenti**.

Per creare un flusso di automazione dell'alimentazione nell'area delle impostazioni, è necessario essere membri del gruppo di ruoli amministratore di gestione dei rischi *Insider* Management o *Insider Management* . Per creare un flusso automatico di alimentazione automatizzato con l'opzione **Gestisci flussi automatici di alimentazione** , è necessario essere membri di almeno un gruppo di ruoli di gestione dei rischi Insider.

Completare la procedura seguente per creare un flusso di automatizzazione Power da un modello consigliato di gestione dei rischi Insider:

1. Nel [centro conformità di Microsoft 365](https://compliance.microsoft.com/), accedere a **gestione dei rischi Insider** e selezionare **Impostazioni rischi Insider**  >  **Powers automatizzare i flussi**. È inoltre possibile accedere alle pagine dashboard dei **casi** o **degli utenti** scegliendo **automatizza**  >  **Gestione flussi automatici di alimentazione**.
2. Sulla pagina **flussi automatici di alimentazione** selezionare un modello consigliato dai **modelli di gestione dei rischi insider come** sezione della pagina.
3. Il flusso elenca le connessioni incorporate necessarie per il flusso e noterà se lo stato della connessione è disponibile. Se necessario, aggiornare tutte le connessioni che non vengono visualizzate come disponibili. Selezionare **continua**.
4. Per impostazione predefinita, i flussi consigliati sono preconfigurati con i campi dati del servizio di gestione dei rischi Insider consigliati e Microsoft 365 necessari per completare l'attività assegnata per il flusso. Se necessario, personalizzare i componenti del flusso utilizzando il controllo **Mostra opzioni avanzate** e configurando le proprietà disponibili per il componente di flusso.
5. Se necessario, aggiungere eventuali passaggi aggiuntivi al flusso selezionando il pulsante **nuovo passaggio** . Nella maggior parte dei casi, non dovrebbe essere necessario per i modelli predefiniti consigliati.
6. Selezionare **Save Draft** per salvare il flusso per ulteriori configurazioni oppure selezionare **Salva** per completare la configurazione del flusso.
7. Selezionare **Chiudi** per tornare alla pagina del **flusso Power automatizzate** . Il nuovo modello verrà elencato come flusso nelle schede **My Flows** ed è automaticamente disponibile dal controllo DropDown **automatizzato** quando si utilizzano i casi di gestione dei rischi Insider per l'utente che crea il flusso.

>[!IMPORTANT]
>Se altri utenti dell'organizzazione devono accedere al flusso, è necessario che il flusso sia condiviso.

### <a name="create-a-custom-power-automate-flow-for-insider-risk-management"></a>Creare un flusso di automatizzazione del potere personalizzato per la gestione dei rischi Insider

Alcuni processi e flussi di lavoro per l'organizzazione possono essere esterni ai modelli di flusso di gestione dei rischi Insider consigliati e potrebbe essere necessario creare flussi automatici di alimentazione automatizzati personalizzati per le aree di gestione dei rischi Insider. I flussi automatici di alimentazione sono flessibili e supportano una personalizzazione estesa, ma sono necessari alcuni passaggi per l'integrazione con le funzionalità di gestione dei rischi Insider.

Completare la procedura seguente per creare un modello personalizzato Power automatizzate per la gestione dei rischi Insider:

1. **Controllare la licenza per il flusso Power Automate**: per creare flussi di automatizzazione di alimentazione personalizzati che utilizzano trigger di gestione dei rischi Insider, è necessaria una licenza di automatizzazione del potere. I modelli di flusso di gestione dei rischi Insider consigliati non richiedono licenze aggiuntive e sono inclusi come parte della licenza di gestione dei rischi Insider.
2. **Creare un flusso automatizzato**: creare un flusso che esegua una o più attività dopo la sua attivazione da parte di un evento di gestione dei rischi Insider. Per informazioni dettagliate su come creare un flusso automatizzato, vedere [Create a Flow in Power](https://docs.microsoft.com/power-automate/get-started-logic-flow)automatizzate.
3. **Selezionare il connettore di conformità microsoft 365**: cercare e selezionare il connettore di conformità di Microsoft 365. Questo connettore attiva i trigger e le azioni di gestione dei rischi Insider. Per ulteriori informazioni sui connettori, vedere l'articolo relativo alla [Panoramica dei riferimenti del connettore](https://docs.microsoft.com/connectors/connector-reference/) .
4. **Scegliere trigger di gestione dei rischi Insider per il flusso: la**gestione dei rischi Insider dispone di due trigger disponibili per flussi automatizzati di alimentazione automatici:
    - **Per un caso di gestione dei rischi Insider selezionati**: i flussi con questo trigger possono essere selezionati dalla pagina del dashboard dei casi di gestione dei rischi Insider.
    - **Per un utente selezionato di gestione dei rischi Insider**: i flussi con questo trigger possono essere selezionati dalla pagina dashboard utenti di gestione dei rischi Insider Management.
5. Scegliere azioni di gestione dei rischi Insider per il flusso: è possibile scegliere tra diverse azioni per la gestione dei rischi Insider da includere nel flusso personalizzato:
    - Ottenere avvisi di gestione dei rischi Insider
    - Ottenere il caso di gestione dei rischi Insider
    - Ottenere un utente di gestione dei rischi Insider
    - Ottenere avvisi di gestione dei rischi Insider per un caso
    - Aggiungere una nota caso di gestione del rischio Insider

### <a name="share-a-power-automate-flow"></a>Condividere un flusso automatico di alimentazione automatizzato

Per impostazione predefinita, i flussi automatici di potenza creati da un utente sono disponibili solo per l'utente. Per gli altri utenti di gestione dei rischi Insider di avere accesso e utilizzare un flusso, il flusso deve essere condiviso dal creatore del flusso. Per condividere un flusso, è possibile utilizzare i controlli delle impostazioni nella **soluzione di gestione dei rischi Insider** nel centro conformità di Microsoft 365 o nell'opzione **Gestisci flussi automatici di alimentazione** dal controllo automatizzare quando si lavora direttamente nelle pagine del dashboard dei **casi** o **degli utenti** . Dopo aver condiviso un flusso, tutti gli utenti con cui è stato condiviso possono accedere al flusso nell'elenco a discesa **automatizza** controllo nel **caso** e nei **dashboard utente**.

Per condividere un flusso di automazione dell'alimentazione nell'area delle impostazioni, è necessario essere membri del gruppo di ruoli amministratore di gestione dei rischi *Insider* Management o *Insider Management* . Per condividere un flusso automatico di alimentazione automatizzato con l'opzione **Gestisci flussi automatici di alimentazione** , è necessario essere membri di almeno un gruppo di ruoli di gestione dei rischi Insider.

Completare la procedura seguente per condividere un flusso Power automatizzate:

1. Nel [centro conformità di Microsoft 365](htttps://compliance.microsoft.com), accedere a **gestione dei rischi Insider** e selezionare **Impostazioni rischi Insider**  >  **Powers automatizzare i flussi**. È inoltre possibile accedere alle pagine dashboard dei **casi** o **degli utenti** scegliendo **automatizza**  >  **Gestione flussi automatici di alimentazione**.
2. Sulla pagina **flussi automatici di alimentazione** selezionare la scheda **flussi personali** o **flussi di Team** .
3. Selezionare il flusso da condividere e quindi scegliere **Condividi** dal menu Opzioni flusso.
4. Nella pagina condivisione flusso, immettere il nome dell'utente o del gruppo che si desidera aggiungere come proprietario per il flusso.
5. Nella finestra di dialogo **connessione utilizzata** , selezionare **OK** per confermare che l'utente o il gruppo aggiunto avrà accesso completo al flusso.

### <a name="edit-a-power-automate-flow"></a>Modificare un flusso Power automatizzate

Per modificare un flusso, è possibile utilizzare i controlli delle impostazioni nella soluzione di **gestione dei rischi Insider** nel centro conformità di Microsoft 365 o nell'opzione **Gestisci flussi automatici di alimentazione** dal controllo **automatizzare** quando si lavora direttamente nei dashboard dei **casi** o **degli utenti**.

Per modificare un flusso automatico di alimentazione nell'area delle impostazioni, è necessario essere membri del gruppo di ruoli amministratore di gestione dei rischi *Insider* Management o *Insider Management* . Per modificare un flusso automatico di alimentazione con l'opzione **Gestisci flussi automatici di alimentazione** , è necessario essere membri di almeno un gruppo di ruoli di gestione dei rischi Insider.

Completare la procedura seguente per modificare un flusso Power automatizzate:

1. Nel [centro conformità di Microsoft 365](htttps://compliance.microsoft.com), accedere a **gestione dei rischi Insider** e selezionare **Impostazioni rischi Insider**  >  **Powers automatizzare i flussi**. È inoltre possibile accedere alle pagine dashboard dei **casi** o **degli utenti** scegliendo **automatizza**  >  **Gestione flussi automatici di alimentazione**.
2. Sulla pagina **flussi automatici di alimentazione** selezionare un flusso da modificare e scegliere **modifica** dal menu controllo flusso.
3. Selezionare le impostazioni dei **puntini**  >  **Settings** di sospensione per modificare un'impostazione del componente di flusso o l'eliminazione con **puntini**  >  **Delete** per eliminare un componente di flusso
4. Selezionare **Salva** e quindi **Chiudi** per completare la modifica del flusso.

### <a name="delete-a-power-automate-flow"></a>Eliminare un flusso Power automatizzate

Per eliminare un flusso, è possibile utilizzare i controlli delle impostazioni nella soluzione di **gestione dei rischi Insider** nel centro conformità di Microsoft 365 o nell'opzione **Gestisci flussi automatici di alimentazione** dal controllo **automatizzare** quando si lavora direttamente nei dashboard dei **casi** o **degli utenti**. Quando un flusso viene eliminato, viene rimosso come opzione per tutti gli utenti.

Per eliminare un flusso di automatizzazione di alimentazione nell'area impostazioni, è necessario essere membri del gruppo di ruoli amministratore di gestione dei rischi *Insider* Management o *Insider Management* . Per eliminare un flusso automatico di alimentazione automatizzato con l'opzione **Gestisci flussi automatici di alimentazione** , è necessario essere membri di almeno un gruppo di ruoli di gestione dei rischi Insider.

Completare la procedura seguente per eliminare un flusso Power automatizzate:

1. Nel [centro conformità di Microsoft 365](htttps://compliance.microsoft.com), accedere a **gestione dei rischi Insider** e selezionare **Impostazioni rischi Insider**  >  **Powers automatizzare i flussi**. È inoltre possibile accedere alle pagine dashboard dei **casi** o **degli utenti** scegliendo **automatizza**  >  **Gestione flussi automatici di alimentazione**.
2. Sulla pagina **flussi automatici di alimentazione** selezionare un flusso da eliminare e scegliere **Elimina** dal menu controllo flusso.
3. Nella finestra di dialogo di conferma dell'eliminazione, selezionare **Elimina** per rimuovere il flusso o selezionare **Annulla** per uscire dall'azione di eliminazione.

## <a name="microsoft-teams-preview"></a>Microsoft Teams (anteprima)

Gli analisti e gli investigatori di conformità possono facilmente utilizzare Microsoft teams per la collaborazione sui casi di gestione dei rischi Insider. Possono coordinare e comunicare con le altre parti interessate in Microsoft teams per:

- Coordinamento e revisione delle attività di risposta per i casi nei canali di team privati
- Condivisione e archiviazione sicura dei file e delle evidenze relative a singoli casi
- Monitorare e verificare le attività di risposta degli analisti e degli investigatori

Dopo che Microsoft teams è abilitato per la gestione dei rischi Insider, viene creato un team di Microsoft teams dedicato ogni volta che viene confermato un avviso e viene creato un caso. Per impostazione predefinita, il team include automaticamente tutti i membri della *gestione dei rischi*Insider, gli *analisti di gestione dei rischi*Insider e i gruppi di ruolo *investigatori di gestione dei rischi Insider* (fino a 100 utenti iniziali). È possibile aggiungere ulteriori collaboratori dell'organizzazione al team dopo la sua creazione e, se necessario. Per i casi esistenti creati prima dell'abilitazione di Microsoft teams, gli analisti e gli investigatori possono scegliere di creare un nuovo team di Microsoft teams quando si lavora in un caso, se necessario.  Dopo aver risolto il caso associato in gestione dei rischi Insider, il team viene archiviato automaticamente (spostato in nascosto e in sola lettura).

Per ulteriori informazioni sull'utilizzo di team e canali in Microsoft teams, vedere [Overview of Teams and channels in Microsoft teams](https://docs.microsoft.com/MicrosoftTeams/teams-channels-overview).

L'abilitazione del supporto di Microsoft teams per i casi è semplice e veloce da configurare. Per abilitare Microsoft teams per la gestione dei rischi Insider, eseguire i passaggi seguenti:

1. Nel [centro conformità di Microsoft 365](htttps://compliance.microsoft.com), passare a impostazioni di rischio Insider Management Risk **Manager**Insider  >  **Insider risk settings**.
2. Selezionare la scheda **Microsoft teams** .
3. Abilitare l'integrazione di Microsoft teams per la gestione dei rischi Insider.
4. Selezionare **Salva** per configurare ed uscire.

### <a name="create-a-microsoft-teams-team-for-existing-cases"></a>Creare un team di Microsoft teams per i casi esistenti

Se si Abilita il supporto di Microsoft teams per la gestione dei rischi Insider dopo che sono presenti casi, è necessario creare manualmente un team per ogni caso in base alle esigenze. Dopo aver abilitato il supporto di Microsoft teams nelle impostazioni di gestione dei rischi Insider, nuovi casi creeranno automaticamente un nuovo team di Microsoft teams.

Gli utenti devono disporre dell'autorizzazione per creare i gruppi di Microsoft 365 nell'organizzazione per creare un team di Microsoft Teams da un caso. Per ulteriori informazioni sulla gestione delle autorizzazioni per i gruppi di Microsoft 365, vedere [gestire gli utenti autorizzati a creare gruppi di microsoft 365](https://docs.microsoft.com/microsoft-365/solutions/manage-creation-of-groups).

Per creare un team per un caso, è possibile utilizzare il controllo Crea Microsoft Team quando si lavora direttamente in un caso esistente. Completare la procedura seguente per creare un nuovo team:

1. Nel [centro conformità di Microsoft 365](htttps://compliance.microsoft.com), passare a casi di **gestione dei rischi Insider**  >  **Cases** e selezionare un caso esistente.
2. Scegliere **Crea Microsoft Team**dal menu azione caso.
3. Nel campo **nome Team** , immettere un nome per il nuovo team di Microsoft teams.
4. Selezionare **Crea Microsoft Team** e quindi **Chiudi**.

A seconda del numero di utenti assegnati ai gruppi di ruoli di gestione dei rischi Insider, potrebbero essere necessari 15 minuti affinché tutti gli investigatori e gli analisti siano aggiunti al team di Microsoft teams per un caso.
