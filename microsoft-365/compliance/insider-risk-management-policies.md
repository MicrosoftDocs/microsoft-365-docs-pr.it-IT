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
ms.openlocfilehash: 9f8424beb7e4a078d14bce755fc399ecd41764d9
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126635"
---
# <a name="insider-risk-management-policies"></a>Criteri di gestione dei rischi Insider

I criteri di gestione dei rischi Insider determinano quali utenti sono nell'ambito e quali tipi di indicatori di rischio sono configurati per gli avvisi. È possibile creare rapidamente un criterio che si applica a tutti gli utenti dell'organizzazione o definire singoli utenti o gruppi per la gestione in un criterio. I criteri supportano le priorità dei contenuti per concentrare le condizioni dei criteri su più o specifici microsoft Teams, siti di SharePoint, tipi di riservatezza dei dati ed etichette dati. Utilizzando i modelli, è possibile selezionare indicatori di rischio specifici e personalizzare le soglie degli eventi per gli indicatori dei criteri, personalizzando in modo efficace i punteggi dei rischi e il livello e la frequenza degli avvisi. Inoltre, i punteggi di rischio e i rilevamenti di anomalie consentono di identificare le attività degli utenti di maggiore rilevanza o più insolite. Le finestre dei criteri consentono di definire l'intervallo di tempo in cui applicare il criterio alle attività di avviso e vengono usate per determinare la durata del criterio una volta attivato.

## <a name="policy-dashboard"></a>Dashboard dei criteri

Il **dashboard dei** criteri consente di visualizzare rapidamente i criteri nell'organizzazione e lo stato corrente degli avvisi associati a ogni criterio.

- **Nome criterio:** il nome assegnato al criterio nella procedura guidata per i criteri.
- **Avvisi attivi**: numero di avvisi attivi per ogni criterio.
- **Avvisi confermati:** numero totale di avvisi generati dai criteri negli ultimi 365 giorni.
- **Azioni eseguite sugli avvisi:** numero totale di avvisi confermati o ignorati negli ultimi 365 giorni.
- **Efficacia dei criteri**: percentuale determinata dagli avvisi confermati totali suddivisi per il numero totale di azioni eseguite sugli avvisi (ovvero la somma degli avvisi confermati o ignorati nell'ultimo anno).
- **Attivo**: stato del caso, *sì* o *no.*

![Dashboard dei criteri di gestione dei rischi Insider](../media/insider-risk-policy-dashboard.png)

## <a name="policy-templates"></a>Modelli dei criteri

I modelli di gestione dei rischi Insider sono condizioni dei criteri predefinite che definiscono i tipi di indicatori di rischio e il modello di punteggio dei rischi utilizzati dal criterio. A ogni criterio deve essere assegnato un modello nella procedura guidata di creazione dei criteri prima della creazione del criterio. La gestione dei rischi Insider supporta fino a cinque criteri per ogni modello di criterio. Quando si crea un nuovo criterio di rischio Insider con la procedura guidata dei criteri, è possibile scegliere tra uno dei modelli di criteri seguenti:

### <a name="data-theft-by-departing-users"></a>Furto di dati da parte degli utenti

Quando gli utenti lasciano l'organizzazione, esistono indicatori di rischio specifici in genere associati al furto di dati da parte degli utenti che lasciano l'organizzazione. Questo modello di criteri usa gli indicatori per il punteggio dei rischi e concentra il rilevamento e gli avvisi su questa area di rischio. Il furto di dati per gli utenti in partenza può includere il download di file da SharePoint Online, la stampa di file e la copia dei dati nei servizi di messaggistica e archiviazione cloud personali vicino alle date di scadenza e alle dimissioni dal lavoro. Questo modello inizia a segnare gli indicatori di rischio relativi a queste attività e il modo in cui sono correlati allo stato di impiego degli utenti.

>[!IMPORTANT]
>Quando si utilizza questo modello, è necessario configurare un connettore risorse umane di Microsoft 365 per importare periodicamente le informazioni sulla data di chiusura e di chiusura per gli utenti dell'organizzazione. Per istruzioni [dettagliate](import-hr-data.md) sulla configurazione del connettore risorse umane di Microsoft 365 per l'organizzazione, vedere l'articolo importare dati con il connettore risorse umane.

### <a name="general-data-leaks"></a>Perdite di dati generali

La protezione dei dati e la prevenzione delle perdite di dati sono una sfida costante per la maggior parte delle organizzazioni, in particolare con la rapida crescita di nuovi dati creati da utenti, dispositivi e servizi. Gli utenti sono autorizzati a creare, archiviare e condividere informazioni tra servizi e dispositivi che rendono la gestione delle perdite di dati sempre più complessa e difficile. Le perdite di dati possono includere la sovrascrittura accidentale di informazioni esterne all'organizzazione o il furto di dati con intento dannoso. In combinazione con un criterio di prevenzione della perdita dei dati (DLP) assegnato, questo modello inizia a segnare rilevamenti in tempo reale di download sospetti di dati di SharePoint Online, condivisione di file e cartelle, stampa di file e copia dei dati nei servizi di messaggistica e archiviazione cloud personali.

Quando si utilizza un **modello** di perdita di dati, è necessario assegnare un criterio DLP per attivare gli indicatori nel criterio di rischio Insider per gli avvisi di gravità elevata nell'organizzazione. Ogni volta che un avviso di gravità elevata viene generato da una regola dei criteri DLP viene aggiunto al log di controllo di Office 365, i criteri di rischio Insider creati con questo modello esaminano automaticamente l'avviso DLP di gravità elevata. Se l'avviso contiene un utente nell'ambito definito nei criteri di rischio Insider, l'avviso viene elaborato dal criterio di rischio Insider come nuovo avviso e assegnato una gravità del rischio Insider e un punteggio di rischio. Questo criterio consente di valutare questo avviso nel contesto di altre attività incluse nel caso.

#### <a name="data-leaks-policy-guidelines"></a>Linee guida per i criteri per la perdita di dati

Quando si creano o si modificano i criteri DLP da utilizzare con i criteri di gestione dei rischi Insider, prendere in considerazione le linee guida seguenti:

- Assegnare priorità agli eventi di esfiltrazione dei dati ed essere selettivi quando si assegnano le impostazioni dei rapporti operazioni non consentite su *Alta* durante la configurazione delle regole nei criteri DLP.  Ad esempio, l'invio di documenti sensibili  a un noto partecipante deve essere un evento di esfiltrazione con livello di avviso elevato. L'assegnazione di  un livello  elevato nelle impostazioni dei rapporti operazioni non consentite in altre regole dei criteri DLP può aumentare il rumore nel flusso di lavoro degli avvisi di gestione dei rischi Insider e rendere più difficile per gli investigatori e gli analisti dei dati valutare correttamente questi avvisi. Ad esempio, *l'assegnazione* di livelli di avviso elevati alle attività di negazione dell'accesso nei criteri DLP rende più difficile valutare il comportamento e le attività degli utenti veramente rischiosi.
- Assicurarsi di aver compreso e configurato correttamente gli utenti nell'ambito sia nei criteri di gestione dei rischi DLP che insider. Solo gli utenti definiti come nell'ambito dei  criteri di gestione dei rischi Insider che utilizzano il modello Perdite di dati avranno avvisi dei criteri DLP di gravità elevata elaborati. Inoltre, solo gli utenti definiti come nell'ambito in una regola per un avviso DLP di gravità elevata verranno esaminati dal criterio di gestione dei rischi Insider per essere considerati. È importante non configurare inconsapevolmente gli utenti nell'ambito dei criteri di rischio DLP e Insider in modo in conflitto.

     Ad esempio, se l'ambito delle regole dei criteri DLP è solo agli  utenti del team vendite e il criterio di rischio Insider creato dal modello Perdita di dati ha definito tutti gli utenti come nell'ambito, il criterio di rischio Insider eelaborare solo avvisi DLP di gravità elevata per gli utenti del team di vendita. Il criterio di rischio Insider non riceverà alcun avviso DLP ad alta priorità per gli utenti da elaborare che non sono definiti nelle regole DLP in questo esempio. Viceversa, se il criterio di  gestione dei rischi Insider creato dai modelli di perdita di dati ha come ambito solo gli utenti del team di vendita e il criterio DLP assegnato è assegnato a tutti gli utenti, il criterio di rischio Insider elaverà solo avvisi DLP di gravità elevata per i membri del team vendite. Il criterio di gestione dei rischi Insider ignorerà gli avvisi DLP di gravità elevata per tutti gli utenti non del team di vendita.

- Verificare che **l'impostazione della** regola dei rapporti operazioni non consentite nel criterio DLP utilizzato per questo modello di gestione dei rischi Insider sia configurata per gli *avvisi* di livello di gravità elevato. Il *livello di* gravità elevato è che gli eventi di attivazione e gli  avvisi di gestione dei rischi Insider non verranno generati dalle regole nei criteri DLP con il campo Dei rapporti operazioni non consentite impostato su *Basso* o *Medio.*

    ![Impostazione dell'avviso del criterio DLP](../media/insider-risk-DLP-policy-high-severity.png)

     >[!NOTE]
     >Quando si crea un nuovo criterio DLP utilizzando i modelli predefiniti, è necessario selezionare l'opzione Crea  o personalizza regole **DLP** avanzate per configurare l'impostazione dei rapporti operazioni non consentite per il livello di gravità elevato. 

A ogni criterio di gestione dei rischi Insider creato **dal** modello Perdita di dati può essere assegnato un solo criterio DLP. Prendere in considerazione la creazione di un criterio DLP dedicato che combina le diverse attività che si desidera rilevare e agire come trigger di eventi per i criteri di rischio Insider che utilizzano il modello perdite **di** dati.

Vedere [l'articolo creare, testare e](create-test-tune-dlp-policy.md) ottimizzare un criterio DLP per istruzioni dettagliate per configurare i criteri DLP per l'organizzazione.

### <a name="data-leaks-by-priority-users-preview"></a>Perdite di dati per utenti con priorità (anteprima)

La protezione dei dati e la prevenzione delle perdite di dati per gli utenti dell'organizzazione possono dipendere dalla posizione, dal livello di accesso alle informazioni riservate o dalla cronologia dei rischi. Le perdite di dati possono includere la sovrascrittura accidentale di informazioni altamente riservate all'esterno dell'organizzazione o il furto di dati con intento dannoso. In combinazione con un criterio di prevenzione della perdita dei dati (DLP) assegnato, questo modello inizia a segnare rilevamenti in tempo reale di attività sospette e aumenta la probabilità di avvisi di rischio Insider e avvisi con livelli di gravità più elevati. Gli utenti con priorità sono definiti in [gruppi di utenti con](insider-risk-management-settings.md#priority-user-groups-preview) priorità configurati nell'area delle impostazioni di gestione dei rischi Insider.

Come per il modello **General data leaks,** è necessario assegnare un criterio DLP per attivare gli indicatori nel criterio di rischio Insider per gli avvisi di gravità elevata nell'organizzazione. Segui le linee guida per i criteri per la perdita di dati sopra riportate quando crei un criterio usando questo modello. Inoltre, sarà necessario assegnare gruppi di utenti con priorità creati in Impostazioni di gestione dei rischi **Insider** Gruppi di utenti  >    >   priorità al criterio.

### <a name="data-leaks-by-disgruntled-users-preview"></a>Perdite di dati da parte di utenti scontenti (anteprima)

Quando gli utenti sperimentano fattori di stress per l'impiego, potrebbero non essere scontenti e ciò può aumentare le probabilità di attività a rischio insider. Questo modello inizia a segnare l'attività dell'utente quando viene identificato un indicatore associato a un dissenso. Ad esempio, le notifiche relative al miglioramento delle prestazioni, le revisioni delle prestazioni scarse o le modifiche allo stato del livello di processo. Le perdite di dati per gli utenti scontenti possono includere il download di file da SharePoint Online e la copia dei dati nei servizi di messaggistica e archiviazione del cloud personale vicino a eventi stressor di lavoro.

Quando si utilizza questo modello, è necessario configurare anche un connettore risorse umane di Microsoft 365 per importare periodicamente notifiche di miglioramento delle prestazioni, stato di revisione delle prestazioni scadente o informazioni sulle modifiche a livello di processo per gli utenti dell'organizzazione. Per istruzioni [dettagliate](import-hr-data.md) sulla configurazione del connettore risorse umane di Microsoft 365 per l'organizzazione, vedere l'articolo importare dati con il connettore risorse umane.

### <a name="general-security-policy-violations-preview"></a>Violazioni generali dei criteri di sicurezza (anteprima)

In molte organizzazioni, gli utenti hanno le autorizzazioni per installare software nei propri dispositivi o per modificare le impostazioni dei dispositivi per facilitare le attività. Inavvertitamente o con intento dannoso, gli utenti possono installare malware o disabilitare importanti funzionalità di sicurezza che consentono di proteggere le informazioni nel dispositivo o nelle risorse di rete. Questo modello di criteri usa gli avvisi di sicurezza di Microsoft Defender per Endpoint per iniziare a segnare queste attività e il rilevamento dello stato attivo e gli avvisi per questa area di rischio. Usa questo modello per fornire informazioni dettagliate sulle violazioni dei criteri di sicurezza in scenari in cui gli utenti potrebbero avere una cronologia delle violazioni dei criteri di sicurezza che potrebbero essere un indicatore di rischio Insider.

Dovrai configurare Microsoft Defender per Endpoint nell'organizzazione e abilitare Defender per Endpoint per l'integrazione della gestione dei rischi Insider in Defender Security Center per importare gli avvisi di violazione della sicurezza. Per altre informazioni sulla configurazione di Defender per Endpoint per l'integrazione della gestione dei rischi Insider, vedi [Configurare le funzionalità avanzate in Defender for Endpoint.](/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center)

### <a name="security-policy-violations-by-departing-users-preview"></a>Violazioni dei criteri di sicurezza da parte degli utenti (anteprima)

L'abbandono degli utenti, sia in termini positivi che negativi, può essere un rischio maggiore per le violazioni dei criteri di sicurezza. Per evitare violazioni di sicurezza accidentali o dannose per gli utenti in partenza, questo modello di criteri usa Defender for Endpoint alerts per fornire informazioni dettagliate sulle attività correlate alla sicurezza. Queste attività includono l'installazione di malware o altre applicazioni potenzialmente dannose e la disabilitazione delle funzionalità di sicurezza nei dispositivi. Gli indicatori dei criteri vengono attivati dopo che gli utenti hanno una data di disdetta o di chiusura importata dal connettore risorse umane di Microsoft 365 come evento di attivazione.

Quando si utilizza questo modello, è necessario configurare un connettore risorse umane di Microsoft 365 per importare periodicamente le informazioni sulla data di chiusura e di chiusura per gli utenti dell'organizzazione. Per istruzioni [dettagliate](import-hr-data.md) sulla configurazione del connettore risorse umane di Microsoft 365 per l'organizzazione, vedere l'articolo importare dati con il connettore risorse umane.

Dovrai configurare Microsoft Defender per Endpoint nell'organizzazione e abilitare Defender per Endpoint per l'integrazione della gestione dei rischi Insider in Defender Security Center per importare gli avvisi di violazione della sicurezza. Per altre informazioni sulla configurazione di Defender per Endpoint per l'integrazione della gestione dei rischi Insider, vedi [Configurare le funzionalità avanzate in Defender for Endpoint.](/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center)

### <a name="security-policy-violations-by-priority-users-preview"></a>Violazioni dei criteri di sicurezza da parte degli utenti con priorità (anteprima)

La protezione da violazioni della sicurezza per gli utenti dell'organizzazione può dipendere dalla posizione, dal livello di accesso alle informazioni riservate o dalla cronologia dei rischi. Poiché le violazioni di sicurezza in base alla priorità degli utenti possono avere un impatto non strutturato sulle aree critiche dell'organizzazione, questo modello di criteri inizia a segnare su questi indicatori e usa gli avvisi di Microsoft Defender for Endpoint per fornire informazioni approfondite sulle attività correlate alla sicurezza per questi utenti. Questi possono includere la priorità degli utenti nell'installazione di malware o altre applicazioni potenzialmente dannose e la disabilitazione delle funzionalità di sicurezza nei propri dispositivi. Gli utenti con priorità sono definiti in gruppi di utenti con priorità configurati nell'area delle impostazioni di gestione dei rischi Insider.

Dovrai configurare Microsoft Defender per Endpoint nell'organizzazione e abilitare Defender per Endpoint per l'integrazione della gestione dei rischi Insider in Defender Security Center per importare gli avvisi di violazione della sicurezza. Per altre informazioni sulla configurazione di Defender per Endpoint per l'integrazione della gestione dei rischi Insider, vedi [Configurare le funzionalità avanzate in Defender for Endpoint.](/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center) Inoltre, sarà necessario assegnare gruppi di utenti con priorità creati in Impostazioni di gestione dei rischi **Insider** Gruppi di utenti  >    >   priorità al criterio.

### <a name="security-policy-violations-by-disgruntled-users-preview"></a>Violazioni dei criteri di sicurezza da parte di utenti scontenti (anteprima)

Gli utenti che provano stress per l'impiego possono essere a rischio maggiore per violazioni accidentali o dannose dei criteri di sicurezza. Questi stress possono includere l'utente che viene inserito in un piano di miglioramento delle prestazioni, lo stato di valutazione delle prestazioni scarse o l'abbassamento di livello dalla posizione corrente. Questo modello di criteri avvia il punteggio dei rischi in base a questi indicatori e attività associati a questi eventi per questi utenti.

Quando si utilizza questo modello, è necessario configurare anche un connettore risorse umane di Microsoft 365 per importare periodicamente notifiche di miglioramento delle prestazioni, stato di revisione delle prestazioni scadente o informazioni sulle modifiche a livello di processo per gli utenti dell'organizzazione. Per istruzioni [dettagliate](import-hr-data.md) sulla configurazione del connettore risorse umane di Microsoft 365 per l'organizzazione, vedere l'articolo importare dati con il connettore risorse umane.

Dovrai anche configurare Microsoft Defender per Endpoint nell'organizzazione e abilitare Defender per Endpoint per l'integrazione della gestione dei rischi Insider in Defender Security Center per importare gli avvisi di violazione della sicurezza. Per altre informazioni sulla configurazione di Defender per Endpoint per l'integrazione della gestione dei rischi Insider, vedi [Configurare le funzionalità avanzate in Defender for Endpoint.](/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center)

### <a name="policy-template-prerequisites-and-triggering-events"></a>Prerequisiti dei modelli di criteri ed eventi di attivazione

A seconda del modello scelto per un criterio di gestione dei rischi Insider, gli eventi di attivazione e i prerequisiti dei criteri variano. L'attivazione degli eventi è un prerequisito che determina se un utente è attivo per un criterio di gestione dei rischi Insider. Se un utente viene aggiunto a un criterio di gestione dei rischi Insider ma non dispone di un evento di attivazione, l'attività dell'utente non viene valutata dal criterio, a meno che non venga aggiunto manualmente nel dashboard degli utenti. I prerequisiti dei criteri sono elementi necessari in modo che i criteri ricevano i segnali o le attività necessari per valutare i rischi.

Nella tabella seguente sono elencati gli eventi di attivazione e i prerequisiti per i criteri creati da ogni modello di criteri di gestione dei rischi Insider:

| **Modello di criteri** | **Attivazione di eventi per i criteri** | **Prerequisiti** |
| :------------------ | :--------------------------------- | :---------------- |
| Furto di dati da parte degli utenti | Indicatore della data di disdetta o di chiusura dal connettore risorse umane | Connettore risorse umane di Microsoft 365 configurato per indicatori di data di chiusura e di dimissioni |
| Perdite di dati generali | Attività dei criteri di perdita dei dati che crea un avviso di gravità elevata | Criteri DLP configurati per gli avvisi di gravità elevata |
| Perdite di dati per utenti con priorità | Attività dei criteri di perdita dei dati che crea un avviso di gravità elevata | Criteri DLP configurati per gli avvisi di gravità elevata <br><br> Gruppi di utenti con priorità configurati nelle impostazioni dei rischi Insider |
| Perdite di dati da parte di utenti scontenti | Indicatori di miglioramento delle prestazioni, prestazioni scarse o cambiamenti a livello di processo dal connettore risorse umane | Connettore risorse umane di Microsoft 365 configurato per gli indicatori di disgruenza |
| Violazioni generali dei criteri di sicurezza | Evasione difensiva dei controlli di sicurezza o del software indesiderato rilevato da Microsoft Defender per Endpoint | Sottoscrizione di Microsoft Defender for Endpoint attiva <br><br> Integrazione di Microsoft Defender for Endpoint con il Centro conformità Microsoft 365 configurato |
| Violazioni dei criteri di sicurezza da parte degli utenti | Indicatori di data di disdetta o di chiusura dal connettore risorse umane | Connettore risorse umane di Microsoft 365 configurato per indicatori di data di chiusura e di dimissioni <br><br> Sottoscrizione di Microsoft Defender for Endpoint attiva <br><br> Integrazione di Microsoft Defender for Endpoint con il Centro conformità Microsoft 365 configurato |
| Violazioni dei criteri di sicurezza per utenti con priorità | Evasione difensiva dei controlli di sicurezza o del software indesiderato rilevato da Microsoft Defender per Endpoint | Sottoscrizione di Microsoft Defender for Endpoint attiva <br><br> Integrazione di Microsoft Defender for Endpoint con il Centro conformità Microsoft 365 configurato <br><br> Gruppi di utenti con priorità configurati nelle impostazioni dei rischi Insider |
| Violazioni dei criteri di sicurezza da parte di un utente scontento | Indicatori di miglioramento delle prestazioni, prestazioni scarse o cambiamenti a livello di processo dal connettore risorse umane | Connettore risorse umane di Microsoft 365 configurato per gli indicatori di disgruenza <br><br> Sottoscrizione di Microsoft Defender for Endpoint attiva <br><br> Integrazione di Microsoft Defender for Endpoint con il Centro conformità Microsoft 365 configurato |

## <a name="prioritize-content-in-policies"></a>Assegnare priorità al contenuto nei criteri

I criteri di gestione dei rischi Insider supportano l'impostazione di una priorità più alta per il contenuto a seconda della posizione in cui è archiviato o della modalità di classificazione. Se si specifica il contenuto come priorità, aumenta il punteggio di rischio per qualsiasi attività associata, che a sua volta aumenta la probabilità di generare un avviso di gravità elevata. Tuttavia, alcune attività non genereranno un avviso a meno che il contenuto correlato non contenga tipi di informazioni sensibili predefiniti o personalizzati o non sia stato specificato come priorità nel criterio.

Ad esempio, l'organizzazione dispone di un sito di SharePoint dedicato per un progetto estremamente riservato. Le perdite di dati per le informazioni in questo sito di SharePoint potrebbero compromettere il progetto e avere un impatto significativo sul suo successo. Assegnando la priorità a questo sito di SharePoint in un criterio di perdita di dati, i punteggi di rischio per le attività idonee vengono automaticamente aumentati. Questa definizione di priorità aumenta la probabilità che queste attività generino un avviso di rischio Insider e aumentino il livello di gravità dell'avviso.

Quando si crea un criterio di gestione dei rischi Insider nella procedura guidata dei criteri, è possibile scegliere tra le seguenti priorità:

- **Siti di SharePoint:** a tutte le attività associate a tutti i tipi di file nei siti di SharePoint definiti viene assegnato un punteggio di rischio maggiore. 
- **Tipi di informazioni riservate**: a tutte le attività associate a contenuti che contengono tipi di [informazioni riservate](sensitive-information-type-entity-definitions.md) viene assegnato un punteggio di rischio maggiore.
- **Etichette di riservatezza:** a tutte le [](sensitivity-labels.md) attività associate al contenuto a cui sono applicate etichette di riservatezza specifiche viene assegnato un punteggio di rischio superiore.

## <a name="create-a-new-policy"></a>Creare un nuovo criterio

Per creare un nuovo criterio di gestione dei rischi Insider, si userà la procedura guidata dei criteri nella soluzione di gestione dei rischi **Insider** nel Centro conformità Microsoft 365.

Completare la procedura seguente per creare un nuovo criterio:

1. Nel Centro [conformità Microsoft 365](https://compliance.microsoft.com)passare a **Gestione dei rischi Insider** e selezionare la **scheda** Criteri.
2. Selezionare **Crea criterio** per aprire la procedura guidata per i criteri
3. Nella pagina **Nuovi criteri di rischio Insider,** completare i campi seguenti:
    - **Nome (obbligatorio):** immettere un nome descrittivo per il criterio.
    - **Descrizione (facoltativo):** immettere una descrizione per il criterio.
    - **Scegliere il modello di criteri (obbligatorio):** selezionare uno dei modelli di [criteri](insider-risk-management-policies.md#policy-templates) per definire i tipi di indicatori di rischio monitorati dal criterio.

    >[!IMPORTANT]
    >La maggior parte dei modelli di criteri dispone di prerequisiti che devono essere configurati per il criterio per generare avvisi pertinenti. Se non sono stati configurati i prerequisiti dei criteri applicabili, vedere Introduzione alla [gestione dei rischi Insider.](insider-risk-management-configure.md#step-3-configure-prerequisites-for-templates)

4. Selezionare **Avanti** per continuare.
5. Nella pagina **Utenti**  selezionare Aggiungi utente  o gruppo o Scegli gruppi di utenti con priorità per definire quali utenti o gruppi di utenti con priorità sono inclusi nel criterio, a seconda del modello di criteri selezionato. Selezionare la casella di controllo Tutti gli utenti e i gruppi **abilitati** alla posta elettronica, se applicabile (se non è stato selezionato un modello basato sull'utente con priorità). Selezionare **Avanti** per continuare.
6. Nella pagina **Specificare il contenuto di cui definire la priorità (facoltativo)** è possibile assegnare le origini per definire la priorità per un aumento dei punteggi di rischio. Tuttavia, alcune attività non genereranno un avviso a meno che il contenuto correlato non contenga tipi di informazioni sensibili predefiniti o personalizzati o non sia stato specificato come priorità in questa pagina:
    - **Siti di SharePoint:** selezionare **Aggiungi sito di SharePoint** e selezionare le organizzazioni di SharePoint di cui si desidera assegnare la priorità. Ad esempio, *"group1@contoso.sharepoint.com/sites/group1"*.
    - **Tipo di informazioni sensibili:** seleziona **Aggiungi tipo di informazioni sensibili** e seleziona i tipi di riservatezza di cui vuoi definire la priorità. Ad esempio, *"U.S. Bank Account Number"* e *"Credit Card Number"*.
    - **Etichette di riservatezza:** selezionare **Aggiungi etichetta di riservatezza** e selezionare le etichette di cui si desidera definire la priorità. Ad esempio, *"Riservato"* *e "Segreto".*
7. Selezionare **Avanti** per continuare.
8. Nella pagina **Seleziona indicatori di** criteri [](insider-risk-management-settings.md#indicators) verranno visualizzati gli indicatori definiti come disponibili nella pagina Indicatori delle impostazioni di rischio   >  **Insider.** Se è stato selezionato *un* modello di perdita di dati all'inizio della procedura guidata, è necessario selezionare un criterio DLP dall'elenco a discesa dei criteri **DLP** per abilitare gli indicatori di attivazione per il criterio. Selezionare gli indicatori che si desidera applicare al criterio. Se si preferisce non usare le impostazioni di soglia dei criteri predefiniti per questi indicatori, disabilitare le soglie predefinite consigliate da **Microsoft** e immettere i valori di soglia per ogni indicatore selezionato. Se è stato selezionato almeno  un indicatore di *Office* o dispositivo, selezionare gli indicatori del punteggio **di rischio in base** alle esigenze. I punteggi di rischio sono applicabili solo per gli indicatori selezionati.

    >[!IMPORTANT]
    >Se gli indicatori in questa pagina non possono essere selezionati, è necessario selezionare gli indicatori che si desidera abilitare per tutti i criteri nella pagina Indicatori dei criteri delle impostazioni di gestione dei rischi  >    >   Insider.

9. Selezionare **Avanti** per continuare.
10. Nella pagina **Intervallo di tempo dei** criteri, vedrai le condizioni della finestra di attivazione per il criterio nella pagina Impostazioni dei rischi **Insider** Intervallo di tempo [](insider-risk-management-settings.md#policy-timeframes)  >  **dei** criteri.
11. Selezionare **Avanti** per continuare.
12. Nella pagina **Revisione** esaminare le impostazioni scelte per il criterio. Selezionare **Modifica** per modificare uno qualsiasi dei valori dei criteri oppure selezionare **Invia** per creare e attivare il criterio.

## <a name="update-a-policy"></a>Aggiornare un criterio

Per aggiornare un criterio di gestione dei rischi Insider esistente, si userà la procedura guidata dei criteri nella soluzione di gestione dei rischi **Insider** nel Centro conformità Microsoft 365.

Completare la procedura seguente per gestire un criterio esistente:

1. Nel Centro [conformità Microsoft 365](https://compliance.microsoft.com)passare a **Gestione dei rischi Insider** e selezionare la **scheda** Criteri.
2. Nel dashboard dei criteri selezionare il criterio che si desidera gestire.
3. Nella pagina dei dettagli del criterio, selezionare **Modifica criterio**
4. Nella procedura guidata dei criteri non è possibile modificare i campi seguenti:
    - **Name**: Nome descrittivo del criterio
    - **Scegliere il modello di** criteri: il modello utilizzato per definire i tipi di indicatori di rischio monitorati dal criterio.
5. Immettere una nuova descrizione per il criterio nel **campo Descrizione.** 
6. Selezionare **Avanti** per continuare.
7. Nella pagina **Utenti**  selezionare Aggiungi utente  o gruppo o Scegli gruppi di utenti con priorità per definire quali utenti o gruppi di utenti con priorità sono inclusi nel criterio, a seconda del modello di criteri selezionato. Selezionare la casella di controllo Tutti gli utenti e i gruppi **abilitati** alla posta elettronica, se applicabile (se non è stato selezionato un modello basato sull'utente con priorità). Selezionare **Avanti** per continuare.
8. Nella pagina **Specificare il contenuto di cui definire la priorità (facoltativo)** è possibile assegnare le origini per definire la priorità per un aumento dei punteggi di rischio. Tuttavia, alcune attività non genereranno un avviso a meno che il contenuto correlato non contenga tipi di informazioni sensibili predefiniti o personalizzati o non sia stato specificato come priorità in questa pagina:
    - **Siti di SharePoint:** selezionare **Aggiungi sito di SharePoint** e selezionare le organizzazioni di SharePoint di cui si desidera assegnare la priorità. Ad esempio, *"group1@contoso.sharepoint.com/sites/group1"*.
    - **Tipo di informazioni sensibili:** seleziona **Aggiungi tipo di informazioni sensibili** e seleziona i tipi di riservatezza di cui vuoi definire la priorità. Ad esempio, *"U.S. Bank Account Number"* e *"Credit Card Number"*.
    - **Etichette di riservatezza:** selezionare **Aggiungi etichetta di riservatezza** e selezionare le etichette di cui si desidera definire la priorità. Ad esempio, *"Riservato"* *e "Segreto".*
9. Selezionare **Avanti** per continuare.
10. Nella pagina **Seleziona indicatori di** criteri [](insider-risk-management-settings.md#indicators) verranno visualizzati gli indicatori definiti come disponibili nella pagina Indicatori delle impostazioni di rischio   >  **Insider.** Se è stato selezionato *un* modello di perdita di dati all'inizio della procedura guidata, è necessario selezionare un criterio DLP dall'elenco a discesa dei criteri **DLP** per abilitare gli indicatori di attivazione per il criterio. Selezionare gli indicatori che si desidera applicare al criterio. Se si preferisce non usare le impostazioni di soglia dei criteri predefiniti per questi indicatori, disabilitare le soglie predefinite consigliate da **Microsoft** e immettere i valori di soglia per ogni indicatore selezionato. Se è stato selezionato almeno  un indicatore di *Office* o dispositivo, selezionare gli indicatori del punteggio **di rischio in base** alle esigenze. I punteggi di rischio sono applicabili solo per gli indicatori selezionati.

    >[!IMPORTANT]
    >Se gli indicatori in questa pagina non possono essere selezionati, è necessario selezionare gli indicatori che si desidera abilitare per tutti i criteri nella pagina Indicatori dei criteri delle impostazioni di gestione dei rischi  >    >   Insider.

11. Selezionare **Avanti** per continuare.
12. Nella pagina **Intervallo di tempo dei** criteri, vedrai le condizioni della finestra di attivazione per il criterio nella pagina Impostazioni dei rischi **Insider** Intervallo di tempo [](insider-risk-management-settings.md#policy-timeframes)  >  **dei** criteri.
13. Selezionare **Avanti** per continuare.
14. Nella pagina **Revisione** esaminare le impostazioni aggiornate per il criterio. Selezionare **Modifica** per modificare uno qualsiasi dei valori dei criteri oppure selezionare **Invia** per aggiornare e attivare il criterio.

## <a name="delete-a-policy"></a>Eliminare un criterio

>[!NOTE]
>L'eliminazione di un criterio non elimina gli avvisi attivi o archiviati generati dal criterio.

Per eliminare un criterio di gestione dei rischi Insider esistente, eseguire la procedura seguente:

1. Nel Centro [conformità Microsoft 365](https://compliance.microsoft.com)passare a **Gestione dei rischi Insider** e selezionare la **scheda** Criteri.
2. Nel dashboard dei criteri selezionare il criterio che si desidera eliminare.
3. Selezionare **Elimina sulla** barra degli strumenti del dashboard.
4. Nella finestra **di dialogo** Elimina selezionare **Sì** per eliminare il criterio oppure scegliere **Annulla** per chiudere la finestra di dialogo.
