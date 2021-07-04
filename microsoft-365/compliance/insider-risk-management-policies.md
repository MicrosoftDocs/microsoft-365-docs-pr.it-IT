---
title: Criteri di gestione dei rischi Insider
description: Informazioni sui criteri di gestione dei rischi Insider in Microsoft 365
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
ms.openlocfilehash: f64fcf4908f119e261b07bbc4feaed2151e30187
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226432"
---
# <a name="insider-risk-management-policies"></a>Criteri di gestione dei rischi Insider

I criteri di gestione dei rischi Insider determinano quali utenti includere nell'ambito e quali tipi di indicatori di rischio siano configurati per gli avvisi. È possibile creare rapidamente un criterio applicabile a tutti gli utenti dell'organizzazione oppure definire singoli utenti o gruppi da gestire in un criterio. I criteri supportano le priorità dei contenuti, per focalizzare l'attenzione sulle condizioni dei criteri su uno o più team di Microsoft Teams, siti di SharePoint, tipi di riservatezza dei dati ed etichette dati. Usando i modelli è possibile selezionare specifici indicatori di rischio e personalizzare le soglie degli eventi per gli indicatori dei criteri, personalizzando efficacemente i punteggi di rischio, oltre che il livello e la frequenza degli avvisi. Inoltre, i booster del punteggio del rischio e i rilevamenti delle anomalie aiutano a identificare le attività utente di maggiore importanza o più insolite. Le finestre dei criteri consentono di definire l'intervallo di tempo in cui applicare il criterio alle attività di avviso e vengono usate per determinare la durata del criterio dopo l'attivazione.

Guardare il video[ ](https://www.youtube.com/watch?v=kudK5ajZTUo)sulla configurazione dei criteri di gestione dei rischi Insider per una panoramica del modo in cui i criteri creati con modelli di criteri predefiniti consentono di intervenire rapidamente sui potenziali rischi.

## <a name="policy-dashboard"></a>Dashboard dei criteri

Il **Dashboard dei criteri** consente di visualizzare rapidamente i criteri nell'organizzazione e il relativo stato dei, di aggiungere manualmente utenti ai criteri e di visualizzare lo stato corrente degli avvisi associati a ciascun criterio.

- **Nome criterio**: nome assegnato al criterio nella procedura guidata.
- **Stato**: stato di integrità di ogni criterio. Mostra il numero di avvisi e suggerimenti per i criteri oppure lo stato *Integro* per i criteri senza problemi.  È possibile fare clic sul criterio per visualizzare i dettagli sullo stato di integrità per eventuali avvisi o suggerimenti.
- **Avvisi attivi**: numero di avvisi attivi per ogni criterio.
- **Avvisi confermati**: numero totale di avvisi generati dal criterio risultati in casi negli ultimi 365 giorni.
- **Interventi in seguito ad avvisi**: numero totale di avvisi confermati o ignorati negli ultimi 365 giorni.
- **Efficacia degli avvisi dei criteri**: percentuale determinata dal totale degli avvisi confermati diviso per le azioni totali eseguite sugli avvisi, ovvero la somma degli avvisi confermati o ignorati nell'ultimo anno.

![Dashboard dei criteri di gestione dei rischi Insider](../media/insider-risk-policy-dashboard.png)

## <a name="policy-recommendations-from-analytics-preview"></a>Suggerimenti per i criteri dall'analisi (anteprima)

L'analisi del rischio Insider consente di condurre una valutazione dei potenziali rischi insider nell'organizzazione senza configurare criteri di rischio Insider. Questa valutazione può aiutare l'organizzazione a identificare le potenziali aree con rischio utente più elevato e a determinare il tipo e l'ambito dei criteri di gestione dei rischi Insider che può essere opportuno configurare.

Per altre informazioni sull'analisi del rischio Insider, vedere [Impostazioni di gestione dei rischi Insider: Analisi (anteprima)](insider-risk-management-settings.md#analytics-preview).

## <a name="policy-templates"></a>Modelli di criteri

I modelli di gestione dei rischi Insider sono condizioni predefinite dei criteri che definiscono i tipi di indicatori di rischio e il modello di assegnazione del punteggio di rischio usati da un criterio. Per poter creare i criteri, è necessario che a ogni criterio sia assegnato un modello nella procedura guidata. La gestione dei rischi Insider supporta fino a cinque criteri per ogni modello di criterio. Quando si crea un nuovo criterio di rischio Insider con la creazione guidata criteri, si può scegliere uno dei modelli seguenti:

### <a name="data-theft-by-departing-users"></a>Furto di dati da parte di utenti che lasciano l'organizzazione

Esistono specifici indicatori di rischio in genere associati al furto di dati da parte degli utenti che lasciano l'organizzazione. Questo modello di criteri usa indicatori di esfiltrazione per il l'assegnazione del punteggio di rischio ed è incentrato sul rilevamento e sugli avvisi in quest'area di rischio. Il furto di dati da parte di utenti che lasciano l'organizzazione può includere il download di file da SharePoint Online, la stampa di file e la copia di dati in servizi personali di messaggistica e archiviazione cloud all'approssimarsi delle date di dimissioni e di termine del rapporto di lavoro. Usando il connettore HR di Microsoft 365 o l'opzione per monitorare automaticamente l'eliminazione degli account utente in Azure Active Directory per l'organizzazione, questo modello inizia a valutare gli indicatori di rischio relativi a queste attività e la relativa correlazione con lo stato di impiego degli utenti.

> [!IMPORTANT]
> Quando si usa questo modello, è possibile configurare un connettore HR di Microsoft 365 in modo da importare periodicamente i dettagli sulle date di fine rapporto o dimissioni per gli utenti dell'organizzazion. Vedere l'articolo [Importare dati con il connettore HR](import-hr-data.md) per istruzioni dettagliate su come configurare il connettore HR di Microsoft 365 per l'organizzazione. Se si sceglie di non usare il connettore HR, quando si configurano gli eventi di attivazione nella creazione guidata criteri è necessario selezionare l'opzione L'account utente è stato eliminato da Azure AD.

### <a name="general-data-leaks"></a>Fughe di dati generali

Proteggere i dati e impedirne la violazione è una sfida costante per la maggior parte delle organizzazioni, in particolare con il rapido aumento dei nuovi dati creati da utenti, dispositivi e servizi. Gli utenti possono creare, archiviare e condividere informazioni tra servizi e dispositivi, rendendo la gestione delle fughe di dati sempre più complessa. Le violazioni dei dati spaziano dalla condivisione accidentale di informazioni all'esterno dell'organizzazione al furto di dati con intento doloso. Dopo l'assegnazione di un criterio di prevenzione della perdita dei dati (DLP) o dell'evento di attivazione predefinito, questo modello inizia a valutare i rilevamenti in tempo reale di attività sospette di download di dati di SharePoint Online, condivisione di file e cartelle, stampa di file e copia di dati in servizi personali di messaggistica cloud e archiviazione.

Quando si usa un modello *Fughe di dati*, è possibile assegnare un criterio DLP in modo da attivare nel criterio di rischio Insider indicatori per gli avvisi con livello di gravità alto nell'organizzazione. Ogni volta che un avviso con livello di gravità alto generato da una regola di criterio DLP viene aggiunto al log di controllo di Office 365, i criteri di rischio Insider creati con questo modello esaminano automaticamente l'avviso. Se l'avviso contiene un utente nell'ambito definito nel criterio di rischio Insider, viene elaborato dal criterio di rischio Insider come nuovo avviso e gli vengono assegnati un livello di gravità e un punteggio di rischio Insider. Questo criterio consente di valutare l'avviso nel contesto con altre attività incluse nel caso. Se non si sceglie un criterio di prevenzione della perdita dei dati, è necessario selezionare l'evento di attivazione predefinito.

#### <a name="data-leaks-policy-guidelines"></a>Linee guida per i criteri sulle fughe di dati

Quando si creano o si modificano criteri DLP da usare con i criteri di gestione dei rischi Insider, considerare le linee guida seguenti:

- Assegnare la priorità agli eventi di esfiltrazione di dati ed essere selettivi quando si configurano le impostazioni dei **Report degli incidenti** su *Alto* durante la configurazione delle regole nei criteri di prevenzione della perdita dei dati. Ad esempio, l'invio di documenti riservati a un concorrente noto dovrebbe essere un evento di esfiltrazione con livello di avviso *Alto*. Assegnare senza una reale necessità il livello *Alto* nelle impostazioni dei **Report degli incidenti** in altre regole di criteri DLP può aumentare il numero di messaggi nel flusso di lavoro degli avvisi per la gestione dei rischi Insider, rendendone più difficile la valutazione corretta da parte di investigatori e analisti dei dati. Ad esempio, assegnare il livello di avviso *Alto* alle attività di tipo accesso negato nei criteri DLP rende più difficile individuare i comportamenti e le attività degli utenti effettivamente a rischio.
- Assicurarsi di comprendere e configurare correttamente gli utenti compresi nell'ambito sia nei criteri DLP, sia nei criteri di gestione dei rischi Insider. Gli avvisi dei criteri DLP con livello di gravità alto verranno elaborati solo per gli utenti definiti come compresi nell'ambito per i criteri di gestione dei rischi Insider usando il modello **Fughe di dati**. Inoltre, solo gli utenti definiti come compresi nell'ambito in una regola per un avviso DLP con livello di gravità alto verranno esaminati dal criterio di gestione dei rischi Insider. È importante non configurare inconsapevolmente utenti in ambito nei criteri DLP e nei criteri di rischio Insider in un modo che generi conflitti.

     Ad esempio, se l'ambito delle regole del criterio DLP è limitato agli utenti del team di vendita e allo stesso tempo l'ambito del criterio di rischio Insider creato dal modello **Fughe di dati** include tutti gli utenti, di fatto il criterio di rischio Insider elaborerà solo gli avvisi DLP di gravità elevata per gli utenti del team di vendita. Il criterio di rischio Insider non riceverà avvisi DLP con priorità alta da elaborare per gli utenti non definiti nelle regole DLP in questo esempio. Viceversa, se l'ambito del criterio di rischio Insider creato dal modello **Fughe di dati** è limitato agli utenti del team di vendita, mentre il criterio DLP assegnato include tutti gli utenti, il criterio di rischio Insider elaborerà solo gli avvisi DLP di gravità elevata per i membri del team di vendita. Il criterio di rischio Insider ignorerà gli avvisi DLP di gravità elevata per tutti gli utenti non del team di vendita.

- Assicurarsi che l'impostazione della regola **Report degli incidenti** nel criterio DLP usato per questo modello di gestione dei rischi Insider sia configurata per gli avvisi con livello di gravità *Alto*. Il livello di gravità *Alto* è l'evento di attivazione e gli avvisi di gestione dei rischi Insider non verranno generati dalle regole nei criteri DLP con il campo **Report degli incidenti** impostato su *Basso* o *Medio*.

    ![Impostazione avviso criterio DLP](../media/insider-risk-DLP-policy-high-severity.png)

     > [!NOTE]
     > Quando si crea un nuovo criterio DLP usando i modelli predefiniti, è necessario selezionare l'opzione **Creare o personalizzare le regole avanzate di prevenzione della perdita dei dati** per configurare l'impostazione **Report degli incidenti** per il livello di gravità *Alto*.

A ogni criterio di gestione dei rischi Insider creato dal modello **Fughe di dati** può essere assegnato un solo criterio DLP. È consigliabile creare un criterio DLP dedicato che combini le diverse attività da rilevare e che dovranno fungere da eventi di attivazione per i criteri di rischio insider che usano il modello **Fughe di dati**.

Vedere l'articolo [Creare, testare e ottimizzare un criterio DLP](create-test-tune-dlp-policy.md) per istruzioni dettagliate su come configurare i criteri DLP per l'organizzazione.

### <a name="data-leaks-by-priority-users-preview"></a>Perdita di dati per utenti con priorità (anteprima)

La protezione dei dati e la prevenzione della perdita di dati per gli utenti dell'organizzazione possono dipendere da fattori come la posizione, il livello di accesso alle informazioni riservate o la cronologia dei rischi. Le violazioni dei dati spaziano dalla condivisione accidentale di informazioni altamente sensibili all'esterno dell'organizzazione al furto di dati con intento doloso. Con un criterio di prevenzione della perdita dei dati (DLP) assegnato, questo modello avvia l'assegnazione di un punteggio ai rilevamenti in tempo reale di attività sospette e aumenta la probabilità di ricevere avvisi di rischio Insider e avvisi con livelli di gravità più elevati. Gli utenti con priorità sono definiti nei [gruppi di utenti con priorità](insider-risk-management-settings.md#priority-user-groups-preview) configurati nell'area delle impostazioni di gestione dei rischi Insider.

Come con il modello **Fughe di dati generali**, è necessario assegnare un criterio DLP per attivare nel criterio di rischio Insider indicatori per avvisi con livello di gravità alto nell'organizzazione. Quando si crea un criterio con questo modello, seguire le linee guida per i criteri sulle fughe di dati. Sarà anche necessario assegnare al criterio i gruppi di utenti con priorità creati in **Gestione dei rischi Insider** > **Impostazioni** > **Gruppi di utenti con priorità**.

### <a name="data-leaks-by-disgruntled-users-preview"></a>Perdite di dati da parte di utenti scontenti (anteprima)

Quando gli utenti sperimentano eventi di stress legati all'impiego, possono diventare scontenti, il che può aumentare la possibilità di attività di rischio Insider. Questo modello avvia l'assegnazione di un punteggio alle attività utente quando viene identificato un indicatore associato a malcontento. Ad esempio notifiche per il miglioramento delle prestazioni, valutazioni delle prestazioni insoddisfacenti o modifiche del livello di lavoro. Le violazioni dei dati da parte di utenti scontenti possono includere il download di file da SharePoint Online, la stampa di file e la copia di dati in servizi personali di messaggistica e archiviazione cloud all'approssimarsi delle date di dimissioni e di termine del rapporto di lavoro.

Quando si usa questo modello, è necessario configurare anche un connettore HR di Microsoft 365 per importare periodicamente notifiche per il miglioramento delle prestazioni, valutazioni delle prestazioni insoddisfacenti o modifiche del livello di lavoro relative agli utenti dell'organizzazione. Vedere l'articolo [Importare dati con il connettore HR](import-hr-data.md) per istruzioni dettagliate su come configurare il connettore HR di Microsoft 365 per l'organizzazione.

### <a name="general-security-policy-violations-preview"></a>Violazioni dei criteri di sicurezza generali (anteprima)

In molte organizzazioni gli utenti sono autorizzati a installare software nei propri dispositivi o a modificarne le impostazioni. Accidentalmente o con intento doloso, gli utenti possono installare malware o disabilitare funzionalità di sicurezza importanti che proteggono le informazioni nel dispositivo o nelle risorse di rete. Questo modello di criteri usa gli avvisi di sicurezza di Microsoft Defender per endpoint per iniziare ad assegnare un punteggio a queste attività e concentrare il rilevamento e gli avvisi su questa area di rischio. Usare questo modello per fornire informazioni dettagliate sulle violazioni dei criteri di sicurezza negli scenari in cui gli utenti potrebbero avere una storia di violazioni, che potenzialmente indica un rischio Insider.

Per importare gli avvisi di violazione della sicurezza è necessario configurare Microsoft Defender for endpoint nell'organizzazione e abilitarlo per l'integrazione della gestione dei rischi Insider in Defender Security Center. Per altre informazioni sulla configurazione di Defender per Endpoint per l'integrazione della gestione dei rischi Insider, vedere [Configurare le funzionalità avanzate in Defender per endpoint](/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center).

### <a name="security-policy-violations-by-departing-users-preview"></a>Violazioni dei criteri di sicurezza da parte di utenti che lasciano l'organizzazione (anteprima)

Gli utenti che lasciano l'organizzazione, in termini sia positivi che negativi, possono essere associati a rischi più elevati di violazioni dei criteri di sicurezza. Per proteggersi da violazioni della sicurezza involontarie o dolose da parte degli utenti che lasciano l'organizzazione, questo modello di criteri usa Defender per endpoint per fornire informazioni dettagliate sulle attività correlate alla sicurezza. Queste attività includono l'installazione di malware o altre applicazioni potenzialmente dannose e la disabilitazione delle funzionalità di sicurezza nei dispositivi. Usando il [connettore HR di Microsoft 365](import-hr-data.md) o l'opzione per monitorare automaticamente l'eliminazione degli account utente in Azure Active Directory per l'organizzazione, questo modello inizia a valutare gli indicatori di rischio relativi a queste attività di sicurezza e la relativa correlazione con lo stato di impiego degli utenti.

Per importare gli avvisi di violazione della sicurezza è necessario configurare Microsoft Defender for endpoint nell'organizzazione e abilitarlo per l'integrazione della gestione dei rischi Insider in Defender Security Center. Per altre informazioni sulla configurazione di Defender per Endpoint per l'integrazione della gestione dei rischi Insider, vedere [Configurare le funzionalità avanzate in Defender per endpoint](/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center).

### <a name="security-policy-violations-by-priority-users-preview"></a>Violazioni dei criteri di sicurezza per utenti con priorità (anteprima)

La protezione dalle violazioni della sicurezza per gli utenti dell'organizzazione può dipendere da fattori come la posizione, il livello di accesso alle informazioni riservate o la cronologia dei rischi. Poiché le violazioni della sicurezza da parte degli utenti con priorità possono avere un notevole impatto sulle aree critiche dell'organizzazione, questo modello di criteri avvia l'assegnazione di punteggi a questi indicatori e usa gli avvisi di Microsoft Defender per endpoint per fornire informazioni sulle attività correlate alla sicurezza per questi utenti. Queste attività possono includere l'installazione di malware o altre applicazioni potenzialmente dannose e la disabilitazione delle funzionalità di sicurezza nei dispositivi. Gli utenti con priorità sono definiti nei gruppi di utenti con priorità configurati nell'area delle impostazioni di gestione dei rischi Insider.

Per importare gli avvisi di violazione della sicurezza è necessario configurare Microsoft Defender for endpoint nell'organizzazione e abilitarlo per l'integrazione della gestione dei rischi Insider in Defender Security Center. Per altre informazioni sulla configurazione di Defender per Endpoint per l'integrazione della gestione dei rischi Insider, vedere [Configurare le funzionalità avanzate in Defender per endpoint](/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center). Sarà anche necessario assegnare al criterio i gruppi di utenti con priorità creati in **Gestione dei rischi Insider** > **Impostazioni** > **Gruppi di utenti con priorità**.

### <a name="security-policy-violations-by-disgruntled-users-preview"></a>Violazioni dei criteri di sicurezza da parte di utenti scontenti (anteprima)

Gli utenti che sperimentano un evento che produce stress legato al lavoro possono essere a rischio più elevato di violazioni dei criteri di sicurezza, accidentali o dolose. Questi eventi stressanti possono includere un abbassamento di livello rispetto alla mansione attuale, una valutazione che indica prestazioni insoddisfacenti o l'inserimento in un piano di miglioramento delle prestazioni. Questo modello di criteri avvia l'assegnazione di un punteggio di rischio in base a questi indicatori e alle attività associate a questi eventi per questi utenti.

Quando si usa questo modello, è necessario configurare anche un connettore HR di Microsoft 365 per importare periodicamente notifiche per il miglioramento delle prestazioni, valutazioni delle prestazioni insoddisfacenti o modifiche del livello di lavoro relative agli utenti dell'organizzazione. Vedere l'articolo [Importare dati con il connettore HR](import-hr-data.md) per istruzioni dettagliate su come configurare il connettore HR di Microsoft 365 per l'organizzazione.

Per importare gli avvisi di violazione della sicurezza è necessario inoltre configurare Microsoft Defender for endpoint nell'organizzazione e abilitarlo per l'integrazione della gestione dei rischi Insider in Defender Security Center. Per altre informazioni sulla configurazione di Defender per Endpoint per l'integrazione della gestione dei rischi Insider, vedere [Configurare le funzionalità avanzate in Defender per endpoint](/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center).

### <a name="policy-template-prerequisites-and-triggering-events"></a>Prerequisiti ed eventi di attivazione dei modelli di criteri

Gli eventi di attivazione e i prerequisiti dei criteri di gestione dei rischi Insider variano in base al modello di criteri scelto. Gli eventi di attivazione sono prerequisiti che determinano se un utente è attivo per un criterio di gestione dei rischi Insider. Se un utente viene aggiunto a un criterio di rischio Insider, ma non ha un evento di attivazione, l'attività utente non viene valutata dal criterio a meno che l'utente non venga aggiunto manualmente nel dashboard Utenti. I prerequisiti dei criteri sono gli elementi necessari perché i criteri ricevano i segnali o le attività necessarie per valutare il rischio.

La tabella seguente elenca gli eventi di attivazione e i prerequisiti per i criteri creati da ogni modello di criteri di gestione dei rischi Insider:

| **Modello di criteri** | **Eventi di attivazione per i criteri** | **Prerequisiti** |
| :------------------ | :--------------------------------- | :---------------- |
| Furto di dati da parte di utenti che lasciano l'organizzazione | Indicatore data di dimissioni o di fine rapporto dal connettore HR | (Facoltativo) Connettore HR di Microsoft 365 configurato per gli indicatori della data di dimissioni o di fine rapporto o integrazione con Azure Active Directory abilitata |
| Fughe di dati generali | Attività di un criterio sulla fuga di dati che crea un avviso di gravità elevata | (Facoltativo) Criterio DLP configurato per avvisi di gravità elevata o evento di attivazione esfiltrazione dati predefinito |
| Perdita di dati per utenti con priorità | Attività di un criterio sulla fuga di dati che crea un avviso *Livello di gravità alto* o trigger di evento di esfiltrazione predefiniti | (Facoltativo) Criterio DLP configurato per gli avvisi di gravità elevata <br><br> Gruppi di utenti con priorità configurati nelle impostazioni dei rischi Insider |
| Perdite di dati da parte di utenti scontenti | Indicatori di miglioramento delle prestazioni, prestazioni insoddisfacenti o variazione del livello di lavoro dal connettore HR | Connettore HR di Microsoft 365 configurato per gli indicatori di malcontento |
| Violazioni dei criteri di sicurezza generali | Evasione difensiva dei controlli di sicurezza o software indesiderato rilevato da Microsoft Defender for endpoint | Abbonamento attivo a Microsoft Defender per endpoint <br><br> Integrazione di Microsoft Defender per endpoint con il Centro conformità Microsoft 365 configurata |
| Violazioni dei criteri di sicurezza da parte di utenti che lasciano l'organizzazione | Indicatore della data di dimissioni o di fine rapporto dal connettore HR oppure eliminazione dell'account Azure Active Directory. | (Facoltativo) Connettore HR di Microsoft 365 configurato per gli indicatori della data di dimissioni o di fine rapporto <br><br> Abbonamento attivo a Microsoft Defender per endpoint <br><br> Integrazione di Microsoft Defender per endpoint con il Centro conformità Microsoft 365 configurata |
| Violazioni dei criteri di sicurezza per utenti con priorità | Evasione difensiva dei controlli di sicurezza o software indesiderato rilevato da Microsoft Defender for endpoint | Abbonamento attivo a Microsoft Defender per endpoint <br><br> Integrazione di Microsoft Defender per endpoint con il Centro conformità Microsoft 365 configurata <br><br> Gruppi di utenti con priorità configurati nelle impostazioni dei rischi Insider |
| Violazioni dei criteri di sicurezza da parte di utenti scontenti | Indicatori di miglioramento delle prestazioni, prestazioni insoddisfacenti o variazione del livello di lavoro dal connettore HR | Connettore HR di Microsoft 365 configurato per gli indicatori di malcontento <br><br> Abbonamento attivo a Microsoft Defender per endpoint <br><br> Integrazione di Microsoft Defender per endpoint con il Centro conformità Microsoft 365 configurata |

## <a name="prioritize-content-in-policies"></a>Assegnare priorità al contenuto nei criteri

I criteri di gestione dei rischi Insider supportano l'impostazione di una priorità più alta per il contenuto in base alla classificazione o alla posizione in cui è archiviato. La definizione del contenuto come priorità aumenta il punteggio di rischio per le attività associate, il che, a sua volta, aumenta la possibilità di generare un avviso di gravità elevato. Alcune attività, tuttavia, non generano un avviso, a meno che il contenuto correlato non contenga tipi di informazioni sensibili incorporati o personalizzati oppure non sia stato specificato come priorità nel criterio.

Si supponga, ad esempio, che l'organizzazione abbia un sito di SharePoint dedicato per un progetto estremamente riservato. Una fuga di dati in questo sito di SharePoint potrebbe compromettere il progetto e avere un impatto significativo sul suo successo. Assegnando la priorità a questo sito di SharePoint in un criterio sulle fughe di dati, i punteggi di rischio per le attività pertinenti vengono aumentati automaticamente. Questa definizione di priorità aumenta la probabilità che queste attività generino un avviso di rischio Insider e aumenta il livello di gravità dell'avviso.

Quando si crea un criterio di rischio Insider nella creazione guidata criteri, è possibile scegliere una delle priorità seguenti:

- **Siti di SharePoint**: a qualunque attività associata a tutti i tipi di file nei siti di SharePoint definiti viene assegnato un punteggio di rischio più alto. 
- **Tipi di informazioni sensibili**: a qualunque attività associata a un contenuto che include [tipi di informazioni sensibili](sensitive-information-type-entity-definitions.md) verrà assegnato un punteggio di rischio più alto.
- **Etichette di riservatezza**: a qualunque attività associata a un contenuto a cui sono applicate specifiche [etichette di riservatezza](sensitivity-labels.md) verrà assegnato un punteggio di rischio più alto.

## <a name="sequence-detection-preview"></a>Rilevamento sequenza (anteprima)

Le attività rischiose potrebbero non presentarsi come eventi isolati. Questi rischi fanno spesso parte di una sequenza di eventi più ampia. Una sequenza è un gruppo di due o più attività utente eseguite una dopo l'altra, che potrebbe suggerire un rischio elevato. L'identificazione di queste attività correlate è una parte importante della valutazione del rischio complessivo. Quando si abilita il rilevamento delle sequenze per i criteri relativi al furto o alla fuga di dati, informazioni dettagliate sulle attività in sequenza vengono visualizzate nella scheda **Attività utente** all'interno di un caso di gestione dei rischi Insider. I modelli di criteri seguenti supportano il rilevamento delle sequenze:

- Furto di dati da parte di utenti che lasciano l'organizzazione
- Fughe di dati generali
- Perdita di dati per utenti con priorità
- Perdite di dati da parte di utenti scontenti

Questi criteri di gestione dei rischi Insider possono usare indicatori specifici e l'ordine in cui si verificano per rilevare ogni passaggio in una sequenza di rischio. I nomi file vengono usati quando si esegue il mapping delle attività in una sequenza. Questi rischi sono organizzati in quattro categorie di attività principali:

- **Raccolta**: i segnali di questa categoria sono incentrati sulle attività di download da parte degli utenti nell'ambito del criterio. Un'attività di esempio in questa categoria è il download di file dai siti di SharePoint.
- **Esfiltrazione**: i segnali di questa categoria sono incentrati sulle attività di estrazione o condivisione in origini interne ed esterne da parte degli utenti nell'ambito del criterio. Un'attività di esempio in questa categoria è l'invio di messaggi di posta elettronica con allegati dall'organizzazione a destinatari esterni.
- **Offuscamento**: i segnali di questa categoria sono incentrati sul mascheramento delle attività rischiose da parte degli utenti nell'ambito del criterio. Un'attività di esempio in questa categoria è la ridenominazione dei file in un dispositivo.
- **Pulizia**: i segnali di questa categoria sono incentrati sulle attività di eliminazione da parte degli utenti nell'ambito del criterio. Un'attività di esempio in questa categoria è l'eliminazione dei file in un dispositivo.

> [!NOTE]
> Il rilevamento delle sequenze usa gli indicatori abilitati nelle impostazioni globali per la gestione dei rischi Insider e gli indicatori selezionati in un criterio. Se non sono selezionati gli indicatori appropriati, il rilevamento delle sequenze non funziona.

È possibile personalizzare singole impostazioni di soglia per ogni tipo di rilevamento sequenza configurato nei criteri. Queste impostazioni di soglia modificano gli avvisi in base al volume di file associati alla sequenza.

Per altre informazioni sulla gestione del rilevamento delle sequenze nella visualizzazione **Attività utente**, vedere [Casi di gestione dei rischi Insider: Attività utente](insider-risk-management-cases.md#user-activity).

## <a name="cumulative-exfiltration-detection-preview"></a>Rilevamento esfiltrazione cumulativa (anteprima)

Gli indicatori di rischio Insider aiutano a identificare i livelli insoliti di attività di rischio, quando valutate quotidianamente per gli utenti nell'ambito dei criteri di rischio Insider. Il rilevamento dell'esfiltrazione cumulativa usa modelli di apprendimento automatico per identificare i casi in cui le attività di esfiltrazione degli utenti superano le medie dell'organizzazione, quando misurate nel tempo e su più tipi di attività di esfiltrazione. Investigatori e analisti impegnati nella gestione dei rischi Insider possono usare queste informazioni per identificare le attività di esfiltrazione che solitamente non generano avvisi, ma sono superiori a quelle tipiche dell'organizzazione. Alcuni esempi possono essere i casi in cui utenti che stanno per lasciare l'organizzazione esfiltrano lentamente dati giorno dopo giorno oppure i casi in cui gli utenti condividono ripetutamente dati tra più canali in misura superiore rispetto al normale.

Il rilevamento dell'esfiltrazione cumulativa è abilitato per impostazione predefinita quando si usano i modelli di criteri seguenti:

- Furto di dati da parte di utenti che lasciano l'organizzazione
- Fughe di dati generali
- Perdita di dati per utenti con priorità
- Perdite di dati da parte di utenti scontenti

> [!NOTE]
> Il rilevamento dell'esfiltrazione cumulativa usa gli indicatori di esfiltrazione abilitati nelle impostazioni globali per la gestione dei rischi Insider e gli indicatori di esfiltrazione selezionati in un criterio. Di conseguenza, il rilevamento dell'esfiltrazione cumulativa viene valutato solo per gli indicatori di esfiltrazione necessari selezionati.

Quando si abilita il rilevamento dell'esfiltrazione cumulativa per i criteri relativi al furto o alla fuga di dati, informazioni dettagliate sulle attività di esfiltrazione cumulative vengono visualizzate nella scheda **Attività utente** all'interno di un caso di gestione dei rischi Insider.

Per altre informazioni sulla gestione delle attività degli utenti, vedere [Casi di gestione dei rischi Insider: Attività utente](insider-risk-management-cases.md#user-activity).

## <a name="policy-health-preview"></a>Integrità dei criteri (anteprima)

Lo stato di integrità dei criteri fornisce informazioni dettagliate sui potenziali problemi relativi ai criteri di gestione dei rischi Insider. La colonna Stato nella scheda Criteri può indicare problemi relativi ai criteri che potrebbero impedire la segnalazione di attività utente o il motivo per cui il numero di avvisi per le attività è insolito. Lo stato di integrità dei criteri può anche confermare che il criterio è integro e non richiede attenzione o modifiche alla configurazione.

Se ci sono problemi con un criterio, lo stato di integrità mostra avvisi di notifica e suggerimenti per intervenire e risolverli. Queste notifiche possono essere utili per risolvere i problemi seguenti:

- Criteri con configurazione incompleta. Questi problemi possono includere utenti o gruppi mancanti nel criterio o altri passaggi di configurazione del criterio incompleti.
- Criteri con problemi di configurazione degli indicatori. Gli indicatori sono una parte importante di ogni criterio. Se gli indicatori non sono configurati o se gli indicatori selezionati sono troppo pochi, il criterio potrebbe non valutare le attività rischiose come previsto.
- I trigger di criteri non funzionano o i relativi requisiti non sono configurati correttamente. La funzionalità dei criteri può dipendere da altri servizi o requisiti di configurazione per rilevare in modo efficace gli eventi di attivazione e attivare l'assegnazione del punteggio di rischio agli utenti. Queste dipendenze possono includere problemi con la configurazione del connettore, la condivisione degli avvisi di Microsoft Defender per endpoint o le impostazioni di configurazione dei criteri DLP.
- I limiti di volume sono vicini o superiori ai limiti. I criteri di gestione dei rischi Insider usano numerosi servizi ed endpoint di Microsoft 365 per aggregare i segnali delle attività di rischio. A seconda del numero di utenti nei criteri, i limiti di volume possono ritardare l'identificazione e la segnalazione delle attività di rischio. Per altre informazioni su questi limiti, vedere la sezione Limiti dei modelli di criteri di questo articolo.

Per vedere rapidamente lo stato di integrità di un criterio, passare alla scheda Criteri e alla colonna Stato. Qui saranno visualizzati i possibili stati di integrità seguenti per ogni criterio:

- Integro: non sono stati identificati problemi.
- Suggerimenti: sono presenti alcuni problemi che potrebbero impedire che il criterio funzioni come previsto.
- Avvisi: sono presenti problemi che impediscono al criterio di identificare le attività rischiose.

Per altre informazioni sui suggerimenti o sugli avvisi, selezionare un criterio nella scheda **Criteri** per aprire la scheda dei dettagli del criterio. Nella sezione Notifiche della scheda dettagli verranno visualizzate altre informazioni su suggerimenti e avvisi, con indicazioni su come risolvere questi problemi.

![Integrità dei criteri di gestione dei rischi Insider](../media/insider-risk-policy-health.png)

Usare la tabella seguente per altre informazioni su suggerimenti, notifiche di avviso e azioni da intraprendere per risolvere i potenziali problemi.

|**Messaggi di notifica**|**Modelli di criteri**|**Cause/Provare questa azione per correggere**|
|:------------------------|:-------------------|:---------------------------|
| Il criterio non sta assegnando i punteggi di rischio all'attività | Tutti i modelli di criteri | Rivedere l'ambito del criterio e la configurazione dell'evento di attivazione perché il criterio possa assegnare punteggi di rischio all'attività <br><br> 1. Rivedere gli utenti selezionati per il criterio. Se sono selezionati pochi utenti, può essere utile selezionarne altri. <br> 2. Se si usa un connettore HR, verificare che invii i dati corretti. <br> 3. Se si usa un criterio DLP come evento di attivazione, verificare che sia configurato per essere usato in questo criterio. <br> 4. Per i criteri di violazione della sicurezza, esaminare lo stato di valutazione degli avvisi di Microsoft Defender per endpoint selezionato nelle impostazioni dei rischi Insider in Rilevamenti intelligenti. Verificare che il filtro degli avvisi non sia troppo ristretto. |
| I criteri non hanno generato avvisi | Tutti i modelli di criteri | Rivedere la configurazione del criterio in modo da analizzare l'assegnazione dei punteggi dell'attività a cui si è interessati. <br><br> 1. Verificare di aver selezionato gli indicatori per cui si vuole calcolare il punteggio. Più sono gli indicatori selezionati, più sono le attività a cui sono assegnati punteggi di rischio. <br> 2. Rivedere la personalizzazione della soglia per il criterio. Se le soglie selezionate non sono allineate alla tolleranza al rischio dell'organizzazione, modificare le selezioni in modo che vengano creati avvisi in base alle soglie preferite. <br> 3. Rivedere gli utenti e i gruppi selezionati per il criterio. Verificare di aver selezionato tutti gli utenti e i gruppi applicabili. <br> 4. Per i criteri di violazione della sicurezza, verificare di aver selezionato lo stato di valutazione degli avvisi per cui si vuole calcolare il punteggio per gli avvisi di Microsoft Defender per endpoint nelle impostazioni, in Rilevamenti intelligenti.|
| Nessun utente o gruppo incluso in questo criterio | Tutti i modelli di criteri | Al criterio non sono assegnati utenti o gruppi. <br><br> Modificare il criterio e selezionare utenti o gruppi. |
| Nessun indicatore selezionato per questi criteri | Tutti i modelli di criteri | Non sono stati selezionati indicatori per il criterio <br><br> Modificare il criterio e selezionare gli indicatori appropriati. |
| Nessun gruppo di utenti con priorità incluso nel criterio | - Perdita di dati per utenti con priorità <br> - Violazioni dei criteri di sicurezza per utenti con priorità | Al criterio non sono assegnati gruppi di utenti con priorità. <br><br> Configurare gruppi di utenti con priorità in Gestione dei rischi Insider e assegnarli al criterio. |
| Nessun evento di attivazione selezionato per questo criterio | Tutti i modelli di criteri | Per il criterio non è selezionato un evento di attivazione <br><br> Alle attività utente non verranno assegnati punteggi di rischio finché non si modifica il criterio e non si seleziona un evento di attivazione. |
| Il connettore HR non è configurato o non sta funzionando come previsto | - Furto di dati da parte di utente che lascia l'organizzazione <br> - Violazioni dei criteri di sicurezza da parte di utenti che lasciano l'organizzazione. <br> - Perdite di dati da parte di utenti scontenti <br> - Violazioni dei criteri di sicurezza da parte di utenti scontenti | C'è un problema con il connettore HR. <br><br> 1. Se si usa un connettore HR, verificare che invii i dati corretti <br><br> OPPURE <br><br> 2. Selezionare l'evento di attivazione eliminato dell'account Azure AD. |
| Non è stato eseguito l'onboarding dei dispositivi | - Furto di dati da parte di utenti che lasciano l'organizzazione <br> - Fughe di dati generali <br> - Perdite di dati da parte di utenti scontenti <br> - Perdita di dati per utenti con priorità | Gli indicatori di dispositivo sono selezionati, ma non è stato eseguito l'onboarding di dispositivi in Microsoft 365 <br><br> Verificare che sia stato eseguito l'onboarding dei dispositivi e che soddisfino i requisiti. |
| Il connettore HR non ha caricato dati di recente | - Furto di dati da parte di utente che lascia l'organizzazione <br> - Violazioni dei criteri di sicurezza da parte di utenti che lasciano l'organizzazione. <br> - Perdite di dati da parte di utenti scontenti <br> - Violazioni dei criteri di sicurezza da parte di utenti scontenti | Il connettore HR non ha importato dati per più di 7 giorni. <br><br> Verificare che il connettore HR sia configurato correttamente e stia inviando dati. |
| Non è possibile verificare lo stato del connettore HR al momento. Ricontrolla in seguito. | - Furto di dati da parte di utente che lascia l'organizzazione <br> - Violazioni dei criteri di sicurezza da parte di utenti che lasciano l'organizzazione. <br> - Perdite di dati da parte di utenti scontenti <br> - Violazioni dei criteri di sicurezza da parte di utenti scontenti | La soluzione di gestione dei rischi Insider non è in grado di controllare lo stato del connettore HR. <br><br> Verificare che il connettore HR sia configurato correttamente e stia inviando dati oppure tornare e controllare lo stato del criterio.  |
| I criteri di prevenzione della perdita dei dati non sono selezionati come evento di attivazione | - Fughe di dati generali <br> - Perdita di dati per utenti con priorità | Non è stato selezionato un criterio DLP come evento di attivazione oppure il criterio selezionato è stato eliminato. <br><br> Modificare il criterio e selezionare un criterio DLP attivo o "L'utente esegue un'attività di esfiltrazione" come evento di attivazione nella configurazione criterio. |
| I criteri di prevenzione della perdita dei dati utilizzati in questo criterio sono disattivati | - Fughe di dati generali <br> - Perdita di dati per utenti con priorità | I criteri di prevenzione della perdita dei dati utilizzati in questo criterio sono disattivati. <br><br> 1. Attivare i criteri DLP assegnati a questo criterio. <br><br> OPPURE <br><br> 2. Modificare questo criterio e selezionare un nuovo criterio DLP o "L'utente esegue un'attività di esfiltrazione" come evento di attivazione nella configurazione criterio. |
| Il criterio di prevenzione della perdita di dati non soddisfa i requisiti | - Fughe di dati generali <br> - Perdita di dati per utenti con priorità | I criteri DLP usati come eventi di attivazione devono essere configurati in modo da generare avvisi di gravità elevata. <br><br>  1. Modificare il criterio DLP per assegnare agli avvisi applicabili il *Livello di gravità alto*. <br><br> OPPURE <br><br> 2. Modificare questo criterio e selezionare *L'utente esegue un'attività di esfiltrazione* come evento di attivazione. |
| La tua organizzazione non dispone di un abbonamento a Microsoft Defender per endpoint | - Violazioni dei criteri di sicurezza generali <br> - Violazioni dei criteri di sicurezza da parte di utenti che lasciano l'organizzazione <br> - Violazioni dei criteri di sicurezza da parte di utenti scontenti <br> - Violazioni dei criteri di sicurezza per utenti con priorità | Non è stato rilevato un abbonamento attivo a Microsoft Defender per endpoint per l'organizzazione. <br><br> Finché non viene aggiunto un abbonamento a Microsoft Defender per endpoint, questi criteri non assegnano punteggi di rischio alle attività utente. |
| Gli avvisi di Microsoft Defender per endpoint non sono condivisi con il centro conformità | - Violazioni dei criteri di sicurezza generali <br> - Violazioni dei criteri di sicurezza da parte di utenti che lasciano l'organizzazione <br> - Violazioni dei criteri di sicurezza da parte di utenti scontenti <br> - Violazioni dei criteri di sicurezza per utenti con priorità | Gli avvisi di Microsoft Defender per endpoint non sono condivisi con il centro conformità. <br><br> Configurare la condivisione degli avvisi di Microsoft Defender per endpoint. |
| Stai per raggiungere il limite massimo di utenti sottoposti all'assegnazione di un punteggio per questo criterio. | Tutti i modelli di criteri | Ogni modello di criteri ha un numero massimo di utenti nell'ambito. Vedere i dettagli nella sezione sui limiti dei modelli. <br><br> Rivedere gli utenti nella scheda Utenti e rimuovere quelli ai quali non è più necessario assegnare un punteggio. |

## <a name="policy-template-limits"></a>Limiti dei modelli di criteri

I modelli di criteri di gestione dei rischi Insider usano dei limiti per gestire il volume e il tasso di elaborazione delle attività di rischio degli utenti compresi nell'ambito e il modo in cui questo processo viene integrato con i servizi Microsoft 365 di supporto. Ogni modello di criteri include un numero massimo di utenti ai quali è possibile assegnare attivamente punteggi di rischio e che il criterio può supportare ed elaborare in modo efficace segnalando le attività a rischio. Gli utenti nell'ambito sono utenti con eventi di attivazione per il criterio.

Il limite per ogni criterio viene calcolato in base al numero totale di utenti univoci che ricevono punteggi di rischio per ogni tipo di modello di criterio. Se il numero di utenti per un tipo di modello di criteri è prossimo o superiore il limite, le prestazioni dei criteri saranno ridotte. Per visualizzare il numero corrente di utenti per un criterio, passare alla scheda Criteri e alla colonna Utenti compresi nell'ambito. Possono essere presenti fino a cinque criteri per ogni modello di criteri. Questi limiti massimi si applicano agli utenti in tutti i criteri che usano un determinato modello di criteri.

Usare la tabella seguente per determinare il numero massimo di utenti nell'ambito supportati per ogni modello di criteri:

|**Modello di criteri**|**Numero massimo attuale di utenti nell'ambito**|
|:------------------|:--------------------------------|
| Fughe di dati generali | 15.000 |
| Perdite di dati da parte di utenti scontenti | 7.500 |
| Perdita di dati per utenti con priorità | 1.000 |
| Furto di dati da parte di utenti che lasciano l'organizzazione | 20.000 |
| Violazioni dei criteri di sicurezza generali | 1.000 |
| Violazioni dei criteri di sicurezza per utenti con priorità | 1.000 |
| Violazioni dei criteri di sicurezza da parte di utenti che lasciano l'organizzazione | 15.000 |
| Violazioni dei criteri di sicurezza da parte di utenti scontenti | 7.500 |

## <a name="create-a-new-policy"></a>Creare un nuovo criterio

Per creare un nuovo criterio di gestione dei rischi Insider, usare la creazione guidata criteri nella soluzione **Gestione dei rischi Insider** nel Centro conformità Microsoft 365.

Completare i passaggi seguenti per creare un nuovo criterio:

1. Nel [Centro conformità Microsoft 365](https://compliance.microsoft.com) passare a **Gestione dei rischi Insider** e selezionare la scheda **Criteri**.
2. Selezionare **Crea criterio** per aprire la creazione guidata criteri.
3. Nella pagina **Modello criteri** scegliere una categoria di criteri e quindi selezionare il modello per il nuovo criterio. Questi modelli sono costituiti da condizioni e da indicatori che definiscono le attività a rischio da rilevare e analizzare. Esaminare i prerequisiti del modello, gli eventi di attivazione e le attività rilevate per verificare che sia adatto alle proprie esigenze.

    > [!IMPORTANT]
    > Alcuni modelli di criteri hanno prerequisiti che devono essere configurati perché il criterio possa generare avvisi rilevanti. Se non sono stati configurati i prerequisiti dei criteri applicabili, vedere il **Passaggio 4** descritto in precedenza.

4. Selezionare **Avanti** per continuare.
5. Nella pagina **Nome e descrizione** completare i campi seguenti:
    - **Nome (obbligatorio)**: immettere un nome descrittivo per il criterio. Non sarà possibile modificarlo dopo aver creato il criterio.
    - **Descrizione (facoltativa)**: immettere una descrizione per il criterio.

6. Selezionare **Avanti** per continuare.
7. Nella pagina **Utenti e gruppi** selezionare **Includere tutti gli utenti e i gruppi** o **Includere utenti e gruppi specifici** per definire quali utenti o gruppi includere nel criterio. In alternativa, se è stato scelto un modello basato sugli utenti con priorità, selezionare **Aggiungi o modifica gruppi di utenti prioritari**. Selezionando **Includere tutti gli utenti e i gruppi** verranno cercati eventi di attivazione per tutti gli utenti e i gruppi dell'organizzazione per avviare l'assegnazione di punteggi di rischio per il criterio. Selezionando **Includere utenti e gruppi specifici** è possibile definire quali utenti e gruppi assegnare al criterio.
8. Selezionare **Avanti** per continuare.
9. Nella pagina **Contenuto a cui assegnare priorità** è possibile assegnare (se necessario) le origini prioritarie, aumentando così la possibilità di generare un avviso di gravità elevata per queste origini. Selezionare una delle opzioni seguenti:

    - **Sì, voglio impostare i siti di SharePoint, le etichette di riservatezza e/o i tipi di informazioni sensibili come contenuti prioritari**. Se si seleziona questa opzione, verranno abilitate pagine dei dettagli nella procedura guidata per configurare questi canali.
    - **Non voglio specificare il contenuto prioritario in questo momento (è possibile farlo dopo aver creato il criterio)**. Se si seleziona questa opzione, le pagine dei dettagli sui canali della procedura guidata verranno ignorate.

10. Selezionare **Avanti** per continuare.

11. Se nel passaggio precedente è stata selezionata l'opzione **Sì, voglio impostare i siti di SharePoint, le etichette di riservatezza e/o i tipi di informazioni sensibili come contenuti prioritari**, verranno visualizzate le pagine dei dettagli per *Siti di SharePoint*, *Tipi di informazioni sensibili* ed *Etichette di riservatezza*. Usare queste pagine di dettagli per definire i siti di SharePoint, i tipi di informazioni sensibili e le etichette di riservatezza a cui assegnare priorità nel criterio.

    - **Siti di SharePoint**: selezionare **Aggiungi sito di SharePoint** e selezionare i siti di SharePoint a cui si ha accesso e a cui si vuole dare priorità. Ad esempio, *"group1@contoso.sharepoint.com/sites/group1"*.
    - **Tipo di informazioni sensibili**: selezionare **Aggiungi tipo di informazioni sensibili** e selezionare i tipi a cui si vuole dare priorità. Ad esempio, *"Numero di conto corrente bancario (Stati Uniti)"* e *"Numero carta di credito"*.
    - **Etichette di riservatezza**: selezionare **Aggiungi etichetta di riservatezza** e selezionare le etichette a cui si vuole dare priorità. Ad esempio, *"Riservato"* e *"Segreto"*.

12. Selezionare **Avanti** per continuare.
13. Nella pagina **Indicatori ed evento di attivazione** verranno visualizzati gli [indicatori](insider-risk-management-settings.md#indicators) definiti come disponibili nelle **** impostazioni dei rischi Insider > **Indicatori**. Se all'inizio della procedura guidata è stato selezionato un modello *Fughe di dati*, è necessario selezionare un criterio di prevenzione della perdita dei dati nell'elenco a discesa **Criteri DLP** per abilitare gli indicatori di attivazione per il criterio oppure selezionare l'evento di attivazione predefinito.

    > [!IMPORTANT]
    > Se non è possibile selezionare gli indicatori in questa pagina, è necessario selezionare gli indicatori che si vogliono abilitare per tutti i criteri. È possibile usare il pulsante **Abilita indicatori** nella procedura guidata o selezionare gli indicatori nella pagina **Gestione dei rischi Insider** > **Impostazioni** > **Indicatori di criteri**.

    Selezionare gli indicatori da applicare al criterio. Se si preferisce non usare le impostazioni di soglia dei criteri predefinite per questi indicatori, disabilitare **Utilizzare le soglie predefinite consigliate da Microsoft** e immettere i valori di soglia per ogni indicatore selezionato.

    - Se è stato selezionato almeno un indicatore *Ufficio* o *Dispositivo*, selezionare i **Booster del punteggio di rischio** come appropriato. I booster del punteggio di rischio sono applicabili solo a indicatori selezionati.
    - Se è stato selezionato un modello di criteri *Furto di dati* o *Fughe di dati*, selezionare uno o più metodi di **Rilevamento sequenza** e un metodo di **Rilevamento esfiltrazione cumulativa** da applicare al criterio.

14. Selezionare **Avanti** per continuare.
15. Nella pagina **Soglie indicatore** selezionare l'opzione per usare le soglie predefinite o per specificare soglie personalizzate per singoli indicatori. Per ogni indicatore, scegliere il livello appropriato per generare il livello desiderato di avvisi attività.
16. Selezionare **Avanti** per continuare.
17. Nella pagina di verifica **** rivedere le impostazioni scelte per i criteri ed eventuali suggerimenti o avvisi relativi alle selezioni. Selezionare **Modifica** per cambiare qualsiasi valore del criterio oppure selezionare **Invia** per creare e attivare il criterio.

## <a name="update-a-policy"></a>Aggiornare un criterio

Per aggiornare un criterio di gestione dei rischi Insider, usare la creazione guidata criteri nella soluzione **Gestione dei rischi Insider** nel Centro conformità Microsoft 365.

Per gestire un criterio esistente, completare la procedura seguente:

1. Nel [Centro conformità Microsoft 365](https://compliance.microsoft.com) passare a **Gestione dei rischi Insider** e selezionare la scheda **Criteri**.
2. Nel dashboard dei criteri selezionare il criterio da gestire.
3. Nella pagina dei dettagli del criterio selezionare **Modifica criterio**
4. Nella creazione guidata criteri non è possibile modificare quanto segue:
    - **Modello criteri**: modello usato per definire i tipi di indicatori di rischio monitorati dal criterio.
    - **Nome**: nome descrittivo del criterio
5. Nella pagina **Nome e descrizione** aggiornare la descrizione del criterio nel campo **Descrizione**.
6. Selezionare **Avanti** per continuare.
7. Nella pagina **Utenti e gruppi** selezionare **Includere tutti gli utenti e i gruppi** o **Includere utenti e gruppi specifici** per definire quali utenti o gruppi includere nel criterio. In alternativa, se è stato scelto un modello basato sugli utenti con priorità, selezionare **Aggiungi o modifica gruppi di utenti prioritari**. Selezionando **Includere tutti gli utenti e i gruppi** verranno cercati eventi di attivazione per tutti gli utenti e i gruppi dell'organizzazione per avviare l'assegnazione di punteggi di rischio per il criterio. Selezionando **Includere utenti e gruppi specifici** è possibile definire quali utenti e gruppi assegnare al criterio.
8. Selezionare **Avanti** per continuare.
9. Nella pagina **Contenuto a cui assegnare priorità** è possibile assegnare (se necessario) le origini prioritarie, aumentando così la possibilità di generare un avviso di gravità elevata per queste origini. Selezionare una delle opzioni seguenti:

    - **Sì, voglio impostare i siti di SharePoint, le etichette di riservatezza e/o i tipi di informazioni sensibili come contenuti prioritari**. Se si seleziona questa opzione, verranno abilitate pagine dei dettagli nella procedura guidata per configurare questi canali.
    - **Non voglio specificare il contenuto prioritario in questo momento (è possibile farlo dopo aver creato il criterio)**. Se si seleziona questa opzione, le pagine dei dettagli sui canali della procedura guidata verranno ignorate.

10. Selezionare **Avanti** per continuare.

11. Se nel passaggio precedente è stata selezionata l'opzione **Sì, voglio impostare i siti di SharePoint, le etichette di riservatezza e/o i tipi di informazioni sensibili come contenuti prioritari**, verranno visualizzate le pagine dei dettagli per *Siti di SharePoint*, *Tipi di informazioni sensibili* ed *Etichette di riservatezza*. Usare queste pagine di dettagli per definire i siti di SharePoint, i tipi di informazioni sensibili e le etichette di riservatezza a cui assegnare priorità nel criterio.

    - **Siti di SharePoint**: selezionare **Aggiungi sito di SharePoint** e selezionare i siti di SharePoint a cui si ha accesso e a cui si vuole dare priorità. Ad esempio, *"group1@contoso.sharepoint.com/sites/group1"*.
    - **Tipo di informazioni sensibili**: selezionare **Aggiungi tipo di informazioni sensibili** e selezionare i tipi a cui si vuole dare priorità. Ad esempio, *"Numero di conto corrente bancario (Stati Uniti)"* e *"Numero carta di credito"*.
    - **Etichette di riservatezza**: selezionare **Aggiungi etichetta di riservatezza** e selezionare le etichette a cui si vuole dare priorità. Ad esempio, *"Riservato"* e *"Segreto"*.

12. Selezionare **Avanti** per continuare.
13. Nella pagina **Indicatori ed evento di attivazione** verranno visualizzati gli [indicatori](insider-risk-management-settings.md#indicators) definiti come disponibili nelle **** impostazioni dei rischi Insider > **Indicatori**. Se all'inizio della procedura guidata è stato selezionato un modello *Fughe di dati*, è necessario selezionare un criterio di prevenzione della perdita dei dati nell'elenco a discesa **Criteri DLP** per abilitare gli indicatori di attivazione per il criterio oppure selezionare l'evento di attivazione predefinito.

    > [!IMPORTANT]
    > Se non è possibile selezionare gli indicatori in questa pagina, è necessario selezionare gli indicatori che si vogliono abilitare per tutti i criteri. È possibile usare il pulsante **Abilita indicatori** nella procedura guidata o selezionare gli indicatori nella pagina **Gestione dei rischi Insider** > **Impostazioni** > **Indicatori di criteri**.

    Selezionare gli indicatori da applicare al criterio. Se si preferisce non usare le impostazioni di soglia dei criteri predefinite per questi indicatori, disabilitare **Utilizzare le soglie predefinite consigliate da Microsoft** e immettere i valori di soglia per ogni indicatore selezionato.

    - Se è stato selezionato almeno un indicatore *Ufficio* o *Dispositivo*, selezionare i **Booster del punteggio di rischio** come appropriato. I booster del punteggio di rischio sono applicabili solo a indicatori selezionati.
    - Se è stato selezionato un modello di criteri *Furto di dati* o *Fughe di dati*, selezionare uno o più metodi di **Rilevamento sequenza** e un metodo di **Rilevamento esfiltrazione cumulativa** da applicare al criterio.

14. Selezionare **Avanti** per continuare.
15. Nella pagina **Soglie indicatore** selezionare l'opzione per usare le soglie predefinite o per specificare soglie personalizzate per singoli indicatori. Per ogni indicatore, scegliere il livello appropriato per generare il livello desiderato di avvisi attività.
16. Selezionare **Avanti** per continuare.
17. Nella pagina di verifica **** rivedere le impostazioni scelte per i criteri ed eventuali suggerimenti o avvisi relativi alle selezioni. Selezionare **Modifica** per cambiare qualsiasi valore del criterio oppure selezionare **Invia** per creare e attivare il criterio.

## <a name="copy-a-policy"></a>Copiare un criterio

Può essere necessario creare un nuovo criterio simile a uno esistente, che richiede solo poche modifiche alla configurazione. Anziché creare un nuovo criterio da zero, è possibile copiare un criterio esistente e quindi modificare le aree che devono essere aggiornate nel nuovo criterio.

Per copiare un criterio esistente, completare la procedura seguente:

1. Nel Centro conformità Microsoft 365 passare a Gestione dei rischi Insider e selezionare la scheda Criteri.
2. Nel dashboard dei criteri selezionare il criterio da copiare.
3. Nella pagina dei dettagli del criterio selezionare Copia.
4. Nella creazione guidata criteri assegnare un nome al nuovo criterio e aggiornare la configurazione del criterio in base alle esigenze.

## <a name="immediately-start-scoring-user-activity"></a>Avviare immediatamente l'assegnazione del punteggio alle attività utente

In alcuni scenari può essere necessario iniziare ad assegnare subito punteggi di rischio agli utenti con criteri di rischio Insider al di fuori del flusso di lavoro degli eventi di attivazione per la gestione dei rischi Insider. Usare **Avvia l'assegnazione del punteggio alle attività per gli utenti** nella scheda **Criteri** per aggiungere manualmente uno o più utenti a uno o più criteri di rischio Insider per un periodo di tempo specifico, in modo da iniziare immediatamente ad assegnare punteggi di rischio alle loro attività e ignorare il requisito che un utente abbia un indicatore di attivazione, ad esempio una corrispondenza con un criterio DLP. È anche possibile aggiungere un motivo per l'aggiunta dell'utente al criterio, che verrà visualizzato nella sequenza temporale delle sue attività. Gli utenti aggiunti manualmente ai criteri vengono visualizzati nel dashboard **Utenti** e, se un'attività soddisfa le soglie di avviso per i criteri, verranno creati avvisi.

Ecco alcuni scenari in cui può essere utile iniziare immediatamente ad assegnare un punteggio alle attività utente:

- Sono stati identificati utenti con problemi di rischio e si vuole iniziare subito ad assegnare punteggi di rischio alle loro attività per uno o più criteri
- Si è verificato un incidente che può richiedere l'assegnazione immediata di punteggi di rischio alle attività degli utenti interessati per uno o più criteri
- Il connettore HR non è stato ancora configurato, ma si vuole iniziare ad assegnare punteggi di rischio alle attività degli utenti per gli eventi HR caricando un file CSV per gli utenti

> [!NOTE]
> Possono essere necessario diverse ore prima che i nuovi utenti aggiunti manualmente compaiano nel dashboard **Utenti**. La visualizzazione delle attività dei 90 giorni precedenti per questi utenti può richiedere fino a 24 ore. Per visualizzare le attività degli utenti aggiunti manualmente, passare alla scheda **Utenti**, selezionare l'utente nel dashboard **Utenti** e aprire la scheda **Attività utente** nel riquadro dei dettagli.

Per avviare manualmente l'assegnazione del punteggio alle attività degli utenti in uno o più criteri di gestione dei rischi Insider, procedere come segue:

1. Nel [Centro conformità Microsoft 365](https://compliance.microsoft.com) passare a **Gestione dei rischi Insider** e selezionare la scheda **Criteri**.
2. Nel dashboard dei criteri selezionare il criterio o i criteri a cui si vogliono aggiungere utenti.
3. Selezionare **Avvia l'assegnazione del punteggio alle attività per gli utenti**.
4. Nel campo **Motivo** aggiungere un motivo per l'aggiunta degli utenti nel riquadro **Aggiungi utenti a più criteri**.
5. Nel campo **Deve durare per (scegliere tra 5 e 30 giorni)** definire il numero di giorni in cui assegnare un punteggio alle attività degli utenti per i criteri a cui sono stati aggiunti
6. Per cercare utenti in Active Directory, usare il campo **Cerca utenti da aggiungere ai criteri**. Digitare il nome dell'utente da aggiungere ai criteri. Selezionare il nome utente e ripetere la procedura per assegnare altri utenti ai criteri. L'elenco degli utenti selezionati compare nella sezione Utenti del riquadro Aggiungi utenti a più criteri.
7. Per importare un elenco di utenti da aggiungere ai criteri, selezionare **Importa** per importare un file CSV (valori delimitati da virgole). Il file deve essere nel formato seguente ed è necessario elencare i nomi di accesso UPN nel file:

    ```csv
    user principal name
    user1@domain.com
    user2@domain.com
    ```

8. Selezionare Aggiungi utenti ai criteri per accettare le modifiche e aggiungere utenti ai criteri oppure scegliere Annulla per annullare le modifiche e chiudere la finestra di dialogo.

## <a name="stop-scoring-users-in-a-policy"></a>Interrompere il calcolo del punteggio per gli utenti in un criterio

Per interrompere il calcolo del punteggio degli utenti in un criterio, vedere l'articolo [Dashboard utenti della gestione dei rischi Insider: Rimuovere utenti dall'assegnazione all'ambito dei criteri](insider-risk-management-users.md#remove-users-from-in-scope-assignment-to-policies).

## <a name="delete-a-policy"></a>Eliminare un criterio

> [!NOTE]
> L'eliminazione di un criterio non comporta l'eliminazione degli avvisi attivi o archiviati generati dal criterio.

Per eliminare un criterio di gestione dei rischi Insider esistente, completare i passaggi seguenti:

1. Nel [Centro conformità Microsoft 365](https://compliance.microsoft.com) passare a **Gestione dei rischi Insider** e selezionare la scheda **Criteri**.
2. Nel dashboard dei criteri selezionare il criterio da eliminare.
3. Selezionare **Elimina** sulla barra degli strumenti del dashboard.
4. Nella finestra di dialogo **Elimina** selezionare **Sì** per eliminare il criterio oppure **Annulla** per chiudere la finestra di dialogo.
