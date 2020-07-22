---
title: Impostazioni di gestione dei rischi Insider
description: Informazioni sulle impostazioni di gestione dei rischi insider in Microsoft 365
keywords: Microsoft 365, gestione dei rischi Insider, gestione dei rischi, conformità
localization_priority: Normal
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: a31ee6de305cf9226a8b605f75bb71406f78fd70
ms.sourcegitcommit: fe20f5ed07f38786c63df0f73659ca472e69e478
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2020
ms.locfileid: "45201422"
---
# <a name="get-started-with-insider-risk-management-settings"></a>Informazioni introduttive sulle impostazioni di gestione dei rischi Insider

Le impostazioni di gestione dei rischi Insider si applicano a tutti i criteri di gestione dei rischi Insider, indipendentemente dal modello scelto quando si crea un criterio. Le impostazioni vengono configurate utilizzando il controllo **impostazioni di rischio Insider** nella parte superiore di tutte le schede gestione rischi Insider. Queste impostazioni controllano i componenti dei criteri per le aree seguenti:

- Privacy
- Indicatori
- Sequenze temporali del criterio
- Rilevamenti intelligenti
- Avvisi di esportazione
- Gruppi di utenti prioritari

Prima di iniziare e creare criteri di gestione dei rischi Insider, è importante comprendere queste impostazioni e scegliere l'opzione livelli migliori per le esigenze di conformità per l'organizzazione.

## <a name="privacy"></a>Privacy

La protezione della privacy degli utenti che dispongono di corrispondenze di criteri è importante e può contribuire a promuovere l'oggettività nelle analisi dei dati e nelle recensioni degli analizzatori dei rischi Insider Per gli utenti con una corrispondenza dei criteri di rischio Insider, è possibile scegliere una delle seguenti impostazioni:

- **Mostrare le versioni di anonimi dei**nomi utente: i denominati degli utenti sono anonimi per impedire agli amministratori, ai ricercatori di dati e ai revisori di vedere gli utenti associati agli avvisi dei criteri. Ad esempio, un utente ' Grace Taylor ' verrebbe visualizzato con uno pseudonimo randomizzato come ' AnonIS8-988' in tutte le aree dell'esperienza di gestione dei rischi Insider. Se si sceglie questa impostazione, anonimizza tutti gli utenti con le corrispondenze di criteri correnti e precedenti e si applica a tutti i criteri. Le informazioni sui profili utente nell'avviso del rischio Insider e nei dettagli del caso non saranno disponibili quando si sceglie questa opzione. Tuttavia, i nomi utente vengono visualizzati quando si aggiungono nuovi utenti ai criteri esistenti o quando si assegnano gli utenti ai nuovi criteri. Se si sceglie di disattivare questa impostazione, i nomi utente verranno visualizzati per tutti gli utenti che hanno corrispondenze di criteri correnti o precedenti.
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
- New
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

1. Abilitare il supporto API di gestione delle attività di Office 365 nelle impostazioni di gestione dei rischi Insider. Per impostazione predefinita, questa impostazione è disabilitata per l'organizzazione Microsoft 365.
2. Filtrare le attività di controllo comuni di Office 365 da *SecurityComplianceAlerts*.
3. Filtrare *SecurityComplianceAlerts* dalla categoria *InsiderRiskManagement* .

![Impostazioni di avviso di esportazione di gestione dei rischi Insider](../media/insider-risk-settings-export.png)

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