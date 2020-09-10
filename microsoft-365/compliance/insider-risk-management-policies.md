---
title: Criteri di gestione dei rischi Insider
description: Informazioni sui criteri di gestione dei rischi insider in Microsoft 365
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
ms.collection: m365-security-compliance
ms.openlocfilehash: fa38b81ff02729f1bd874c1ac286712b0a6bbb7a
ms.sourcegitcommit: 74ef7179887eedc696c975a82c865b2d4b3808fd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/09/2020
ms.locfileid: "47416810"
---
# <a name="insider-risk-management-policies"></a>Criteri di gestione dei rischi Insider

I criteri di gestione dei rischi Insider determinano quali utenti sono nell'ambito e quali tipi di indicatori di rischio sono configurati per gli avvisi. È possibile creare rapidamente un criterio che si applica a tutti gli utenti dell'organizzazione o definire singoli utenti o gruppi per la gestione in un criterio. I criteri supportano le priorità del contenuto per concentrare le condizioni dei criteri su più o specifici team Microsoft, siti di SharePoint, tipi di sensibilità dei dati e etichette dati. Utilizzando i modelli, è possibile selezionare indicatori di rischio specifici e personalizzare le soglie degli eventi per gli indicatori di criteri, personalizzando in modo efficace i punteggi dei rischi e il livello e la frequenza degli avvisi. Inoltre, i booster del Punteggio di rischio e i rilevamenti delle anomalie consentono di identificare le attività degli utenti più importanti o più inusuali. Criteri le finestre consentono di definire la tempistica per applicare il criterio alle attività di avviso e vengono utilizzate per determinare la durata del criterio, una volta attivato.

## <a name="policy-dashboard"></a>Dashboard di criteri

Il **dashboard dei criteri** consente di visualizzare rapidamente i criteri dell'organizzazione e lo stato corrente degli avvisi associati a ogni criterio.

- **Nome criterio**: il nome assegnato al criterio nella procedura guidata per i criteri.
- **Avvisi attivi**: il numero di avvisi attivi per ogni criterio.
- **Avvisi confermati**: il numero totale di avvisi restituiti nei casi dal criterio negli ultimi 365 giorni.
- **Azioni intraprese sugli avvisi**: il numero totale di avvisi che sono stati confermati o scartati negli ultimi 365 giorni.
- **Efficacia dei criteri**: la percentuale determinata dal totale degli avvisi confermati diviso per le azioni totali eseguite sugli avvisi (ovvero la somma degli avvisi che sono stati confermati o scartati nell'ultimo anno).
- **Attivo**: lo stato del caso, ovvero *Sì* o *No*.

![Dashboard dei criteri di gestione del rischio Insider](../media/insider-risk-policy-dashboard.png)

## <a name="policy-templates"></a>Modelli dei criteri

I modelli di gestione dei rischi Insider sono condizioni predefinite che definiscono i tipi di indicatori di rischio e il modello di Punteggio di rischio utilizzato dal criterio. Ogni criterio deve disporre di un modello assegnato nella procedura guidata per la creazione dei criteri prima di creare il criterio. Gestione dei rischi Insider supporta un massimo di cinque criteri per ogni modello di criteri. Quando si crea un nuovo criterio di rischio Insider con la procedura guidata per i criteri, è possibile scegliere uno dei modelli di criteri seguenti:

### <a name="data-theft-by-departing-users"></a>Furto dei dati da parte degli utenti

Quando gli utenti lasciano l'organizzazione, esistono indicatori di rischio specifici tipicamente associati al furto dei dati da parte degli utenti. Questo modello di criteri utilizza indicatori per il Punteggio dei rischi e concentra il rilevamento e gli avvisi in questa area di rischio. Il furto dei dati per gli utenti in partenza può includere il download di file da SharePoint Online, la stampa di file e la copia dei dati in servizi di archiviazione e messaggistica cloud personali vicino alle date di dimissioni e di fine del lavoro. Questo modello inizia a segnare gli indicatori di rischio relativi a queste attività e a correlare con lo stato di utilizzo dell'utente.

>[!IMPORTANT]
>Quando si utilizza questo modello, è necessario configurare un connettore Microsoft 365 HR per importare periodicamente le informazioni relative alle dimissioni e alla terminazione per gli utenti dell'organizzazione. Vedere l'articolo [Import Data with the HR Connector](import-hr-data.md) per informazioni dettagliate su come configurare il connettore Microsoft 365 HR per la propria organizzazione.

### <a name="general-data-leaks"></a>Perdite di dati generali

La protezione dei dati e la prevenzione della perdita di dati è una sfida costante per la maggior parte delle organizzazioni, in particolare con la rapida espansione dei nuovi dati creati da utenti, dispositivi e servizi. Gli utenti sono autorizzati a creare, archiviare e condividere informazioni tra i servizi e i dispositivi che rendono la gestione delle perdite di dati sempre più complesse e difficili. Le perdite di dati possono includere la sovracondivisione accidentale di informazioni all'esterno dell'organizzazione o il furto di dati con intenti dolosi. In combinazione con un criterio di prevenzione della perdita di dati (DLP) assegnato, questo modello inizia a segnare i rilevamenti in tempo reale dei download di dati di SharePoint online sospetti, la condivisione di file e cartelle, la stampa di file e la copia dei dati in servizi di archiviazione e messaggistica cloud personali.

Quando si utilizza un modello di **perdita di dati** , è necessario assegnare un criterio DLP per attivare gli indicatori nei criteri di rischio Insider per gli avvisi di gravità elevata nell'organizzazione. Ogni volta che viene generato un avviso di severità elevato da una regola di criteri DLP viene aggiunto al registro di controllo di Office 365, i criteri di rischio Insider creati con questo modello esaminano automaticamente l'avviso di gravità elevata. Se l'avviso contiene un utente in ambito definito nel criterio di rischio Insider, l'avviso viene elaborato dal criterio di rischio insider come nuovo avviso e assegnato un livello di rischio Insider e un punteggio di rischio. Questo criterio consente di valutare questo avviso in contesto ad altre attività incluse nel caso.

#### <a name="data-leaks-policy-guidelines"></a>Linee guida per i criteri di perdita dei dati

Quando si creano o si modificano i criteri DLP per l'utilizzo con i criteri di gestione dei rischi Insider, tenere presente quanto segue

- Assegnare la *priorità agli eventi di exfiltration* dei dati ed essere selettivi quando si configurano **le regole** nei criteri DLP. Ad esempio, la posta elettronica dei documenti sensibili a un concorrente conosciuto dovrebbe essere un evento exfiltration a livello di avviso *elevato* . L'assegnazione eccessiva del livello *elevato* nelle impostazioni dei **rapporti sugli incidenti** in altre regole di criteri DLP può aumentare il rumore nel flusso di lavoro di avviso di gestione dei rischi Insider e rendere più difficile per i ricercatori e gli analisti di dati valutare adeguatamente questi avvisi. Ad esempio, se si assegnano livelli di avviso *elevati* per accedere alle attività Denial nei criteri DLP, è più difficile valutare le attività e il comportamento degli utenti davvero rischiosi.
- Assicurarsi di aver compreso e configurato correttamente gli utenti in ambito sia nei criteri di gestione del rischio DLP che Insider. Solo gli utenti definiti come ambito per i criteri di gestione dei rischi Insider che utilizzano il modello di **perdita di dati** avranno gli avvisi del criterio DLP a gravità elevata elaborati. Inoltre, solo gli utenti definiti come nell'ambito di una regola per un avviso DLP di gravità elevato verranno esaminati dal criterio di gestione dei rischi Insider per considerazione. È importante che non si configuri inconsapevolmente gli utenti in ambito sia nei criteri di rischio DLP che insider in modo conflittuale.

     Ad esempio, se le regole dei criteri DLP sono limitate a solo gli utenti del team di vendita e il criterio di rischio Insider creato dal modello per le **perdite di dati** ha definito tutti gli utenti come nell'ambito, il criterio di rischio Insider elaborerà solo avvisi DLP ad alta gravità per gli utenti del team di vendita. Il criterio di rischio insider non riceverà avvisi DLP ad alta priorità per gli utenti di elaborare che non sono definiti nelle regole DLP in questo esempio. Al contrario, se il criterio di gestione dei rischi Insider creato da modelli di **perdita di dati** ha come ambito solo gli utenti del team di vendita e il criterio DLP assegnato ha come ambito tutti gli utenti, il criterio di rischio Insider elaborerà solo avvisi DLP di gravità elevata per i membri del team di vendita. Il criterio di gestione dei rischi Insider ignorerà gli avvisi DLP ad alta gravità per tutti gli utenti non del team di vendita.

- Verificare che l'impostazione della regola per i **rapporti imprevisti** nel criterio DLP utilizzato per il modello di gestione dei rischi Insider sia configurata per avvisi a livello di gravità *elevato* . Il livello di gravità *elevato* è gli eventi di attivazione e gli avvisi di gestione dei rischi insider non vengono generati dalle regole nei criteri DLP con il campo **rapporto eventi** non consentiti in *basso* o *medio*.

    ![Impostazione dell'avviso del criterio DLP](../media/insider-risk-DLP-policy-high-severity.png)

     >[!NOTE]
     >Quando si crea un nuovo criterio DLP utilizzando i modelli incorporati, è necessario selezionare l'opzione **Crea o Personalizza Advanced DLP Rules** per configurare l'impostazione dei **rapporti sugli incidenti** per il livello di gravità *elevato* .

Ogni criterio di gestione dei rischi Insider creato dal modello per le **perdite di dati** può essere assegnato solo a un criterio DLP. Valutare la possibilità di creare un criterio DLP dedicato che combini le diverse attività che si desidera rilevare e fungere da eventi di attivazione per i criteri di rischio Insider che utilizzano il modello di **perdita di dati** .

Per informazioni dettagliate su come configurare i criteri DLP per la propria organizzazione, vedere l'argomento [creare, testare e ottimizzare un criterio DLP](create-test-tune-dlp-policy.md) .

### <a name="data-leaks-by-priority-users-preview"></a>Perdite di dati da parte di utenti prioritari (anteprima)

La protezione dei dati e la prevenzione della perdita di dati per gli utenti dell'organizzazione possono dipendere dalla posizione, dal livello di accesso alle informazioni riservate o dalla cronologia dei rischi. Le perdite di dati possono includere la sovracondivisione accidentale di informazioni estremamente riservate all'esterno dell'organizzazione o il furto di dati con intenti dolosi. In combinazione con un criterio di prevenzione della perdita di dati (DLP, Data Loss Prevention) assegnato, questo modello inizia a segnare i rilevamenti in tempo reale dell'attività sospetta e comporta una maggiore probabilità di avvisi e avvisi con livelli di gravità superiori. Gli utenti prioritari sono definiti in [gruppi di utenti prioritari](insider-risk-management-settings.md#priority-user-groups-preview) configurati nell'area impostazioni di gestione dei rischi Insider.

Come per il **modello di perdita di dati generale**, è necessario assegnare un criterio DLP per attivare gli indicatori nei criteri di rischio Insider per gli avvisi di gravità elevata nell'organizzazione. Seguire le linee guida relative ai criteri per le perdite di dati precedenti quando si crea un criterio utilizzando questo modello. È inoltre necessario assegnare ai criteri i gruppi di utenti prioritari creati **Insider risk management**in  >  **Settings**  >  **gruppi di priorità** delle impostazioni di gestione dei rischi Insider.

### <a name="data-leaks-by-disgruntled-users-preview"></a>Perdite di dati da parte di utenti scontenti (anteprima)

Quando gli utenti avvertono fattori di stress occupazionali, potrebbero essere scontenti, il che potrebbe aumentare le probabilità di attività di rischio Insider. Questo modello inizia a segnare l'attività dell'utente quando viene identificato un indicatore associato a malumore. Esempi sono le notifiche di miglioramento delle prestazioni, le revisioni delle prestazioni scadenti o le modifiche allo stato del livello di lavoro. Le perdite di dati per gli utenti scontenti possono includere il download di file da SharePoint Online e la copia dei dati in servizi di archiviazione e messaggistica cloud personali in prossimità di eventi di stress occupazionali.

Quando si utilizza questo modello, è inoltre necessario configurare un connettore Microsoft 365 HR per importare periodicamente le notifiche di miglioramento delle prestazioni, lo stato di revisione delle prestazioni scadente o le informazioni sulle modifiche a livello di processo per gli utenti dell'organizzazione. Vedere l'articolo [Import Data with the HR Connector](import-hr-data.md) per informazioni dettagliate su come configurare il connettore Microsoft 365 HR per la propria organizzazione.

### <a name="general-security-policy-violations-preview"></a>Violazioni generali dei criteri di sicurezza (anteprima)

In molte organizzazioni, gli utenti dispongono delle autorizzazioni per installare il software nei propri dispositivi o per modificare le impostazioni del dispositivo per agevolare le attività. Involontariamente o con intenti dolosi, gli utenti possono installare malware o disabilitare importanti funzionalità di sicurezza che consentono di proteggere le informazioni sul dispositivo o sulle risorse di rete. Questo modello di criteri utilizza gli avvisi di sicurezza di Microsoft Defender Advanced Threat Protection (ATP) per iniziare a segnare queste attività e a concentrare il rilevamento e gli avvisi su questa area di rischio. Utilizzare questo modello per fornire informazioni sulle violazioni dei criteri di sicurezza negli scenari in cui gli utenti potrebbero avere una cronologia delle violazioni dei criteri di sicurezza che possono essere un indicatore del rischio Insider.

Per importare gli avvisi relativi alla violazione di sicurezza, è necessario che Microsoft Defender ATP sia configurato nell'organizzazione e abilitare Microsoft Defender ATP per l'integrazione di gestione dei rischi Insider nel centro sicurezza protezione. Per ulteriori informazioni sulla configurazione di Microsoft Defender ATP per l'integrazione di gestione dei rischi Insider, vedere [configure advanced features in Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center).

### <a name="security-policy-violations-by-departing-users-preview"></a>Violazioni dei criteri di sicurezza partendo dagli utenti (anteprima)

La partenza degli utenti, indipendentemente dal fatto che si verifichino condizioni positive o negative, potrebbe essere un rischio maggiore per le violazioni dei criteri di sicurezza. Per garantire la protezione da violazioni accidentali o dannose per la sicurezza per gli utenti in partenza, questo modello di criteri utilizza gli avvisi di Microsoft Defender ATP per fornire informazioni dettagliate sulle attività relative alla sicurezza. Tali attività includono l'installazione di malware o altre applicazioni potenzialmente nocive e la disabilitazione delle funzionalità di sicurezza sui propri dispositivi. Gli indicatori dei criteri vengono attivati dopo che gli utenti hanno una data di dimissioni o di terminazione importata dal connettore Microsoft 365 HR come evento di attivazione.

Quando si utilizza questo modello, è necessario configurare un connettore Microsoft 365 HR per importare periodicamente le informazioni relative alle dimissioni e alla terminazione per gli utenti dell'organizzazione. Vedere l'articolo [Import Data with the HR Connector](import-hr-data.md) per informazioni dettagliate su come configurare il connettore Microsoft 365 HR per la propria organizzazione.

Per importare gli avvisi relativi alla violazione di sicurezza, è necessario che Microsoft Defender ATP sia configurato nell'organizzazione e abilitare Microsoft Defender ATP per l'integrazione di gestione dei rischi Insider nel centro sicurezza protezione. Per ulteriori informazioni sulla configurazione di Microsoft Defender ATP per l'integrazione di gestione dei rischi Insider, vedere [configure advanced features in Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center).

### <a name="security-policy-violations-by-priority-users-preview"></a>Violazioni dei criteri di sicurezza per gli utenti con priorità (anteprima)

La protezione da violazioni di sicurezza per gli utenti dell'organizzazione può dipendere dalla posizione, dal livello di accesso alle informazioni riservate o dalla cronologia dei rischi. Poiché le violazioni della sicurezza per gli utenti con priorità potrebbero avere un impatto ingrandito sulle aree critiche dell'organizzazione, questo modello di criteri inizia a segnare questi indicatori e utilizza gli avvisi di Microsoft Defender ATP per fornire informazioni dettagliate sulle attività relative alla sicurezza per questi utenti. Questi possono includere gli utenti prioritari che installano malware o altre applicazioni potenzialmente nocive e disabilitano le funzionalità di sicurezza sui propri dispositivi. Gli utenti prioritari sono definiti in gruppi di utenti prioritari configurati nell'area impostazioni di gestione dei rischi Insider.

Per importare gli avvisi relativi alla violazione di sicurezza, è necessario che Microsoft Defender ATP sia configurato nell'organizzazione e abilitare Microsoft Defender ATP per l'integrazione di gestione dei rischi Insider nel centro sicurezza protezione. Per ulteriori informazioni sulla configurazione di Microsoft Defender ATP per l'integrazione di gestione dei rischi Insider, vedere [configure advanced features in Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center). È inoltre necessario assegnare ai criteri i gruppi di utenti prioritari creati **Insider risk management**in  >  **Settings**  >  **gruppi di priorità** delle impostazioni di gestione dei rischi Insider.

### <a name="security-policy-violations-by-disgruntled-users-preview"></a>Violazioni dei criteri di sicurezza da parte di utenti scontenti (anteprima)

Gli utenti che avvertono fattori di stress occupazionali possono avere un rischio maggiore per violazioni dei criteri di sicurezza involontarie o dannose. Tali fattori di stress possono includere l'utente che si trova in un piano di miglioramento delle prestazioni, lo stato di revisione delle prestazioni scarso o che viene abbassato di livello rispetto alla posizione corrente. Questo modello di criteri inizia a segnare i rischi in base a questi indicatori e attività associati a questi eventi per questi utenti.

Quando si utilizza questo modello, è inoltre necessario configurare un connettore Microsoft 365 HR per importare periodicamente le notifiche di miglioramento delle prestazioni, lo stato di revisione delle prestazioni scadente o le informazioni sulle modifiche a livello di processo per gli utenti dell'organizzazione. Vedere l'articolo [Import Data with the HR Connector](import-hr-data.md) per informazioni dettagliate su come configurare il connettore Microsoft 365 HR per la propria organizzazione.

È inoltre necessario che Microsoft Defender ATP sia configurato nell'organizzazione e abilitare Microsoft Defender ATP per l'integrazione di gestione dei rischi Insider nel centro sicurezza protezione per importare gli avvisi relativi alla violazione della sicurezza. Per ulteriori informazioni sulla configurazione di Microsoft Defender ATP per l'integrazione di gestione dei rischi Insider, vedere [configure advanced features in Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center).

### <a name="offensive-language-in-email"></a>Lingua offensiva nel messaggio di posta elettronica

Il rilevamento e l'esecuzione di operazioni per impedire comportamenti offensivi e abusivi sono una componente fondamentale della prevenzione dei rischi. I classificatori incorporati in Microsoft 365 Scan hanno inviato messaggi di posta elettronica dalle cassette postali di Exchange Online nell'organizzazione per diversi tipi di problemi di conformità. Questi classificatori utilizzano una combinazione di intelligenza artificiale e parole chiave per identificare la lingua nella posta elettronica che potrebbe violare i criteri di anti-molestia. Utilizzare questo modello per creare rapidamente un criterio che utilizza questi classificatori per rilevare automaticamente il contenuto del messaggio di posta elettronica che può essere considerato abusivo o offensivo. Insider Risk Management utilizza classificatori che analizzano i messaggi di posta elettronica inviati per i termini e i sentimenti di lingua inglese per il linguaggio offensivo.

### <a name="policy-template-prerequisites-and-triggering-events"></a>Prerequisiti e eventi di attivazione dei modelli di criteri

A seconda del modello scelto per un criterio di gestione dei rischi Insider, gli eventi di attivazione e i prerequisiti di criteri variano. Gli eventi di attivazione sono prerequisiti che determinano se un utente è attivo per un criterio di gestione dei rischi Insider. Se un utente viene aggiunto a un criterio di gestione dei rischi Insider ma non ha un evento di attivazione, l'attività dell'utente non viene valutata dal criterio, a meno che non venga aggiunta manualmente nel dashboard degli utenti. I prerequisiti per i criteri sono elementi obbligatori in modo che il criterio riceva i segnali o le attività necessarie per valutare i rischi.

Nella tabella seguente sono elencati gli eventi di attivazione e i prerequisiti per i criteri creati da ogni modello di criteri di gestione dei rischi Insider:

| **Modello di criteri** | **Attivazione di eventi per i criteri** | **Prerequisiti** |
| :------------------ | :--------------------------------- | :---------------- |
| Furto dei dati da parte degli utenti | Indicatore data dimissioni o terminazione dal connettore HR | Connettore Microsoft 365 HR configurato per gli indicatori di data di terminazione e dimissioni |
| Perdite di dati generali | Attività del criterio di perdita dei dati che crea un avviso di gravità elevato | Criteri DLP configurati per avvisi di gravità elevata |
| Perdite di dati da parte di utenti prioritari | Attività del criterio di perdita dei dati che crea un avviso di gravità elevato | Criteri DLP configurati per avvisi di gravità elevata <br><br> Gruppi di utenti prioritari configurati nelle impostazioni dei rischi Insider |
| Perdite di dati da parte di utenti scontenti | Miglioramenti delle prestazioni, prestazioni insufficienti o indicatori di modifica a livello di processo dal connettore HR | Connettore Microsoft 365 HR configurato per gli indicatori di malumore |
| Violazioni dei criteri di sicurezza generali | Evasione difensiva dei controlli di sicurezza o del software indesiderato rilevato da Microsoft Defender ATP | Sottoscrizione di Microsoft Defender ATP attiva <br><br> Integrazione di Microsoft Defender ATP con centro conformità Microsoft 365 configurato |
| Violazioni dei criteri di sicurezza da parte degli utenti | Indicatori di data di dimissioni o di terminazione dal connettore HR | Connettore Microsoft 365 HR configurato per gli indicatori di data di terminazione e dimissioni <br><br> Sottoscrizione di Microsoft Defender ATP attiva <br><br> Integrazione di Microsoft Defender ATP con centro conformità Microsoft 365 configurato |
| Violazioni dei criteri di sicurezza per gli utenti con priorità | Evasione difensiva dei controlli di sicurezza o del software indesiderato rilevato da Microsoft Defender ATP | Sottoscrizione di Microsoft Defender ATP attiva <br><br> Integrazione di Microsoft Defender ATP con centro conformità Microsoft 365 configurato <br><br> Gruppi di utenti prioritari configurati nelle impostazioni dei rischi Insider |
| Violazioni dei criteri di sicurezza da parte di utenti scontenti | Miglioramenti delle prestazioni, prestazioni insufficienti o indicatori di modifica a livello di processo dal connettore HR | Connettore Microsoft 365 HR configurato per gli indicatori di malumore <br><br> Sottoscrizione di Microsoft Defender ATP attiva <br><br> Integrazione di Microsoft Defender ATP con centro conformità Microsoft 365 configurato |
| Lingua offensiva nel messaggio di posta elettronica | Linguaggio blasfemo, minacce o molestie nei messaggi di posta elettronica | Abbonamento a Exchange Online attivo |

## <a name="prioritize-content-in-policies"></a>Definire la priorità del contenuto nei criteri

I criteri di gestione dei rischi Insider supportano la specifica di una priorità più alta per il contenuto a seconda della modalità di archiviazione o di classificazione. La specifica del contenuto come priorità aumenta il Punteggio di rischio per qualsiasi attività associata, che a sua volta aumenta la possibilità di generare un avviso di gravità elevato. Tuttavia, alcune attività non genereranno alcun avviso, a meno che il contenuto correlato non contenga tipi di informazioni riservate incorporate o personalizzati o sia stato specificato come priorità nel criterio.

Ad esempio, l'organizzazione dispone di un sito di SharePoint dedicato per un progetto estremamente riservato. Le perdite di dati per le informazioni contenute in questo sito di SharePoint potrebbero compromettere il progetto e incidere in modo significativo sul relativo esito positivo. Assegnando la priorità a questo sito di SharePoint in un criterio di perdita dei dati, i punteggi dei rischi per le attività di qualificazione sono aumentati automaticamente. In questo modo si aumenta la probabilità che queste attività generino un avviso di rischio Insider e aumentano il livello di gravità per l'avviso.

Quando si crea un criterio di gestione dei rischi Insider nella procedura guidata dei criteri, è possibile scegliere tra le seguenti priorità:

- **Siti di SharePoint**: a qualsiasi attività associata a tutti i tipi di file in siti di SharePoint definiti viene assegnato un punteggio di rischio maggiore. 
- **Tipi di informazioni riservate**: a qualsiasi attività associata a contenuto che contiene [tipi di informazioni riservate](sensitive-information-type-entity-definitions.md) viene assegnato un punteggio di rischio maggiore.
- **Etichette di riservatezza**: a qualsiasi attività associata a contenuto con [etichette di riservatezza](sensitivity-labels.md) specifiche viene assegnato un punteggio di rischio maggiore.

## <a name="create-a-new-policy"></a>Creare un nuovo criterio

Per creare un nuovo criterio di gestione dei rischi Insider, è possibile utilizzare la creazione guidata criteri in soluzione di **gestione dei rischi Insider** nel centro conformità Microsoft 365.

Completare la procedura seguente per creare un nuovo criterio:

1. Nel [centro conformità di Microsoft 365](https://compliance.microsoft.com)accedere a **gestione dei rischi Insider** e selezionare la scheda **criteri** .
2. Selezionare **create Policy** per aprire la procedura guidata per i criteri
3. Nella pagina **nuovo criterio di rischio Insider** completare i seguenti campi:
    - **Nome (obbligatorio)**: immettere un nome descrittivo per il criterio.
    - **Description (facoltativo)**: immettere una descrizione per il criterio.
    - **Scegliere il modello di criteri (obbligatorio)**: selezionare uno dei [modelli di criteri](insider-risk-management-policies.md#policy-templates) per definire i tipi di indicatori di rischio sono monitorati dal criterio.

    >[!IMPORTANT]
    >La maggior parte dei modelli di criteri ha prerequisiti che devono essere configurati per il criterio per generare avvisi rilevanti. Se non sono stati configurati i prerequisiti per i criteri applicabili, vedere [Introduzione alla gestione dei rischi Insider](insider-risk-management-configure.md#step-3-configure-prerequisites-for-templates).

4. Fare clic su **Avanti** per continuare.
5. Nella pagina **utenti** selezionare **Aggiungi utente o gruppo** oppure **scegliere gruppi** di utenti prioritari per definire quali utenti o gruppi di priorità sono inclusi nel criterio, a seconda del modello di criteri selezionato. Selezionare **tutti gli utenti e i gruppi abilitati alla posta elettronica** , se applicabile (se non è stato selezionato un modello di priorità basato sull'utente). Fare clic su **Avanti** per continuare.
6. Nella pagina **specificare il contenuto di cui definire la priorità (facoltativa)** , è possibile assegnare le origini alla priorità per i punteggi di rischio aumentati. Tuttavia, alcune attività non genereranno alcun avviso, a meno che il contenuto correlato contenga tipi di informazioni riservate incorporate o personalizzati o sia stato specificato come priorità in questa pagina:
    - **Siti di SharePoint**: selezionare **Aggiungi sito di SharePoint** e selezionare le organizzazioni di SharePoint a cui si desidera assegnare la priorità. Ad esempio, *"group1@contoso.sharepoint.com/sites/group1"*.
    - **Tipo di informazioni riservate**: selezionare **Aggiungi tipo di informazioni riservate** e selezionare i tipi di sensibilità che si desidera impostare come priorità. Ad esempio, *"numero di conto corrente bancario statunitense"* e *"numero di carta di credito"*.
    - **Etichette di riservatezza**: selezionare **Aggiungi etichetta di riservatezza** e selezionare le etichette che si desidera impostare come priorità. Ad esempio, *"confidenziale"* e *"segreto"*.
7. Fare clic su **Avanti** per continuare.
8. Nella pagina **Selezione indicatori di criteri** verranno visualizzati gli [indicatori](insider-risk-management-settings.md#indicators) definiti come disponibili nella pagina indicatori **impostazioni di rischio Insider**  >  **Indicators** . Se all'inizio della procedura guidata è stato selezionato un modello per le *perdite di dati* , è necessario selezionare un criterio DLP dall'elenco a discesa dei **criteri DLP** per abilitare gli indicatori di attivazione per il criterio. Selezionare gli indicatori che si desidera applicare al criterio. Se si preferisce non utilizzare le impostazioni predefinite della soglia dei criteri per questi indicatori, disabilitare le **soglie di utilizzo predefinite consigliate da Microsoft** e immettere i valori di soglia per ogni indicatore selezionato. Se è stato selezionato almeno un indicatore di *Office* o *dispositivo* , selezionare i **Booster del Punteggio di rischio** in base alle esigenze. I booster del Punteggio di rischio sono applicabili solo per gli indicatori selezionati.

    >[!IMPORTANT]
    >Se non è possibile selezionare gli indicatori in questa pagina, è necessario scegliere gli indicatori che si desidera abilitare per tutti i criteri nella pagina indicatori dei criteri di **gestione dei rischi Insider Management**  >  **Settings**  >  **Policy indicators** .

9. Fare clic su **Avanti** per continuare.
10. Nella pagina **scadenze** dei criteri verranno visualizzate le condizioni per la [finestra di attivazione](insider-risk-management-settings.md#policy-timeframes) per il criterio che si trova nella pagina scadenze dei criteri di **rischio Insider**  >  **Policy timeframes** .
11. Fare clic su **Avanti** per continuare.
12. Nella pagina **Revisione** rivedere le impostazioni selezionate per il criterio. Selezionare **modifica** per modificare i valori dei criteri o selezionare **Invia** per creare e attivare il criterio.

## <a name="update-a-policy"></a>Aggiornare un criterio

Per aggiornare un criterio di gestione dei rischi Insider esistente, è possibile utilizzare la procedura guidata criteri nella soluzione di **gestione dei rischi Insider** nel centro conformità Microsoft 365.

Completare la procedura seguente per gestire un criterio esistente:

1. Nel [centro conformità di Microsoft 365](https://compliance.microsoft.com)accedere a **gestione dei rischi Insider** e selezionare la scheda **criteri** .
2. Nel dashboard dei criteri selezionare il criterio che si desidera gestire.
3. Nella pagina dei dettagli del criterio, selezionare **modifica criterio**
4. Nella creazione guidata criteri non è possibile modificare i campi seguenti:
    - **Nome**: nome descrittivo per il criterio
    - **Scegliere il modello di criteri**: il modello utilizzato per definire i tipi di indicatori di rischio monitorati dal criterio.
5. Immettere una nuova descrizione per il criterio nel campo **Descrizione** . 
6. Fare clic su **Avanti** per continuare.
7. Nella pagina **utenti** selezionare **Aggiungi utente o gruppo** oppure **scegliere gruppi** di utenti prioritari per definire quali utenti o gruppi di priorità sono inclusi nel criterio, a seconda del modello di criteri selezionato. Selezionare **tutti gli utenti e i gruppi abilitati alla posta elettronica** , se applicabile (se non è stato selezionato un modello di priorità basato sull'utente). Fare clic su **Avanti** per continuare.
8. Nella pagina **specificare il contenuto di cui definire la priorità (facoltativa)** , è possibile assegnare le origini alla priorità per i punteggi di rischio aumentati. Tuttavia, alcune attività non genereranno alcun avviso, a meno che il contenuto correlato contenga tipi di informazioni riservate incorporate o personalizzati o sia stato specificato come priorità in questa pagina:
    - **Siti di SharePoint**: selezionare **Aggiungi sito di SharePoint** e selezionare le organizzazioni di SharePoint a cui si desidera assegnare la priorità. Ad esempio, *"group1@contoso.sharepoint.com/sites/group1"*.
    - **Tipo di informazioni riservate**: selezionare **Aggiungi tipo di informazioni riservate** e selezionare i tipi di sensibilità che si desidera impostare come priorità. Ad esempio, *"numero di conto corrente bancario statunitense"* e *"numero di carta di credito"*.
    - **Etichette di riservatezza**: selezionare **Aggiungi etichetta di riservatezza** e selezionare le etichette che si desidera impostare come priorità. Ad esempio, *"confidenziale"* e *"segreto"*.
9. Fare clic su **Avanti** per continuare.
10. Nella pagina **Selezione indicatori di criteri** verranno visualizzati gli [indicatori](insider-risk-management-settings.md#indicators) definiti come disponibili nella pagina indicatori **impostazioni di rischio Insider**  >  **Indicators** . Se all'inizio della procedura guidata è stato selezionato un modello per le *perdite di dati* , è necessario selezionare un criterio DLP dall'elenco a discesa dei **criteri DLP** per abilitare gli indicatori di attivazione per il criterio. Selezionare gli indicatori che si desidera applicare al criterio. Se si preferisce non utilizzare le impostazioni predefinite della soglia dei criteri per questi indicatori, disabilitare le **soglie di utilizzo predefinite consigliate da Microsoft** e immettere i valori di soglia per ogni indicatore selezionato. Se è stato selezionato almeno un indicatore di *Office* o *dispositivo* , selezionare i **Booster del Punteggio di rischio** in base alle esigenze. I booster del Punteggio di rischio sono applicabili solo per gli indicatori selezionati.

    >[!IMPORTANT]
    >Se non è possibile selezionare gli indicatori in questa pagina, è necessario scegliere gli indicatori che si desidera abilitare per tutti i criteri nella pagina indicatori dei criteri di **gestione dei rischi Insider Management**  >  **Settings**  >  **Policy indicators** .

11. Fare clic su **Avanti** per continuare.
12. Nella pagina **scadenze** dei criteri verranno visualizzate le condizioni per la [finestra di attivazione](insider-risk-management-settings.md#policy-timeframes) per il criterio che si trova nella pagina scadenze dei criteri di **rischio Insider**  >  **Policy timeframes** .
13. Fare clic su **Avanti** per continuare.
14. Nella pagina **Revisione** esaminare le impostazioni aggiornate per il criterio. Selezionare **modifica** per modificare i valori dei criteri o selezionare **Invia** per aggiornare e attivare il criterio.

## <a name="delete-a-policy"></a>Eliminare un criterio

>[!NOTE]
>L'eliminazione di un criterio non comporta l'eliminazione di avvisi attivi o archiviati generati dal criterio.

Per eliminare un criterio di gestione dei rischi Insider esistente, completare i passaggi seguenti:

1. Nel [centro conformità di Microsoft 365](https://compliance.microsoft.com)accedere a **gestione dei rischi Insider** e selezionare la scheda **criteri** .
2. Nel dashboard dei criteri selezionare il criterio che si desidera eliminare.
3. Selezionare **Delete** sulla barra degli strumenti del dashboard.
4. Nella finestra di dialogo **Elimina** selezionare **Sì** per eliminare il criterio oppure fare clic su **Annulla** per chiudere la finestra di dialogo.
