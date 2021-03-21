---
title: Criteri di gestione dei rischi Insider
description: Informazioni sui criteri di gestione dei rischi insider in Microsoft 365
keywords: Microsoft 365, gestione dei rischi insider, gestione dei rischi, conformità
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
ms.openlocfilehash: 96d265a7b909b439f960c951b10c84f4bc7a63b0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916830"
---
# <a name="insider-risk-management-policies"></a>Criteri di gestione dei rischi Insider

I criteri di gestione dei rischi insider determinano quali utenti sono nell'ambito e quali tipi di indicatori di rischio sono configurati per gli avvisi. È possibile creare rapidamente un criterio che si applica a tutti gli utenti dell'organizzazione o definire singoli utenti o gruppi per la gestione in un criterio. I criteri supportano le priorità del contenuto per concentrare le condizioni dei criteri su più o specifici microsoft Teams, siti di SharePoint, tipi di riservatezza dei dati ed etichette dati. Utilizzando i modelli, è possibile selezionare indicatori di rischio specifici e personalizzare le soglie degli eventi per gli indicatori dei criteri, personalizzando in modo efficace i punteggi di rischio e il livello e la frequenza degli avvisi. Inoltre, i ripetitori del punteggio di rischio e i rilevamenti di anomalie consentono di identificare le attività degli utenti di maggiore importanza o più insolite. Le finestre dei criteri consentono di definire l'intervallo di tempo per l'applicazione del criterio alle attività di avviso e vengono utilizzate per determinare la durata del criterio una volta attivato.

## <a name="policy-dashboard"></a>Dashboard dei criteri

Il **dashboard dei** criteri consente di visualizzare rapidamente i criteri nell'organizzazione, l'integrità dei criteri, aggiungere manualmente gli utenti ai criteri e visualizzare lo stato degli avvisi associati a ogni criterio.

- **Nome criterio**: Nome assegnato al criterio nella procedura guidata dei criteri.
- **Status**: stato di integrità per ogni criterio. Visualizza il numero di avvisi e suggerimenti per i criteri oppure lo stato *Integro* per i criteri senza problemi.  È possibile fare clic sul criterio per visualizzare i dettagli sullo stato di integrità per eventuali avvisi o suggerimenti.
- **Avvisi attivi**: numero di avvisi attivi per ogni criterio.
- **Avvisi confermati:** numero totale di avvisi generati dai criteri negli ultimi 365 giorni.
- **Azioni eseguite sugli avvisi**: numero totale di avvisi confermati o ignorati negli ultimi 365 giorni.
- **Efficacia degli** avvisi dei criteri : percentuale determinata dagli avvisi confermati totali suddivisi per il totale delle azioni eseguite sugli avvisi (ovvero la somma degli avvisi confermati o ignorati nell'ultimo anno).

![Dashboard dei criteri di gestione dei rischi Insider](../media/insider-risk-policy-dashboard.png)

## <a name="policy-recommendations-from-analytics-preview"></a>Suggerimenti per i criteri dall'analisi (anteprima)

L'analisi dei rischi Insider consente di eseguire una valutazione dei potenziali rischi insider nell'organizzazione senza configurare criteri di rischio insider. Questa valutazione può aiutare l'organizzazione a identificare le potenziali aree con un rischio maggiore per gli utenti e a determinare il tipo e l'ambito dei criteri di gestione dei rischi insider che è possibile configurare.

Per altre informazioni sull'analisi dei rischi insider e sui suggerimenti per i criteri, vedi Impostazioni di gestione dei rischi [insider: Analisi (anteprima).](insider-risk-management-settings.md#analytics-preview)

## <a name="policy-templates"></a>Modelli dei criteri

I modelli di gestione dei rischi insider sono condizioni dei criteri predefinite che definiscono i tipi di indicatori di rischio e il modello di punteggio dei rischi utilizzati dal criterio. Ogni criterio deve disporre di un modello assegnato nella procedura guidata per la creazione dei criteri prima della creazione del criterio. La gestione dei rischi insider supporta fino a cinque criteri per ogni modello di criteri. Quando si crea un nuovo criterio di rischio insider con la procedura guidata dei criteri, è possibile scegliere uno dei modelli di criteri seguenti:

### <a name="data-theft-by-departing-users"></a>Furto di dati da parte di utenti in partenza

Quando gli utenti lasciano l'organizzazione, esistono indicatori di rischio specifici in genere associati al furto di dati da parte degli utenti in partenza. Questo modello di criteri usa indicatori di esfiltrazione per il punteggio di rischio e si concentra sul rilevamento e sugli avvisi in questa area di rischio. Il furto di dati per gli utenti in partenza può includere il download di file da SharePoint Online, la stampa di file e la copia dei dati nei servizi di messaggistica e archiviazione cloud personali in prossimità delle date di fine e di chiusura dell'impiego. Utilizzando il connettore risorse umane di Microsoft 365 o l'opzione per monitorare automaticamente l'eliminazione dell'account utente in Azure Active Directory per l'organizzazione, questo modello inizia a segnare gli indicatori di rischio relativi a queste attività e la correlazione con lo stato di impiego degli utenti.

>[!IMPORTANT]
>Quando si utilizza questo modello, è possibile configurare un connettore risorse umane di Microsoft 365 per importare periodicamente le informazioni sulla data di chiusura e di chiusura per gli utenti dell'organizzazione. Vedere [l'articolo Importare dati con il](import-hr-data.md) connettore HR per istruzioni dettagliate per configurare il connettore risorse umane di Microsoft 365 per l'organizzazione. Se si sceglie di non usare il connettore risorse umane, è necessario selezionare l'opzione Account utente eliminato da Azure AD durante la configurazione degli eventi trigger nella procedura guidata dei criteri.

### <a name="general-data-leaks"></a>Perdite di dati generali

La protezione dei dati e la prevenzione delle perdite di dati è una sfida costante per la maggior parte delle organizzazioni, in particolare con la rapida crescita di nuovi dati creati da utenti, dispositivi e servizi. Gli utenti sono autorizzati a creare, archiviare e condividere informazioni tra servizi e dispositivi che rendono sempre più complessa e difficile la gestione delle perdite di dati. Le perdite di dati possono includere la sovrascrittura accidentale di informazioni esterne all'organizzazione o il furto di dati con intenti dannosi. Con un criterio di prevenzione della perdita dei dati (DLP) assegnato o l'evento di attivazione predefinito, questo modello inizia a segnare rilevamenti in tempo reale di download sospetti di dati di SharePoint Online, condivisione di file e cartelle, stampa di file e copia dei dati nei servizi di messaggistica e archiviazione cloud personali.

Quando si utilizza un *modello perdite* di dati, è possibile assegnare un criterio DLP per attivare gli indicatori nel criterio di rischio insider per gli avvisi di gravità elevata nell'organizzazione. Ogni volta che un avviso di gravità elevata viene generato da una regola dei criteri DLP viene aggiunto al log di controllo di Office 365, i criteri di rischio insider creati con questo modello esaminano automaticamente l'avviso DLP di gravità elevata. Se l'avviso contiene un utente nell'ambito definito nel criterio di rischio Insider, l'avviso viene elaborato dai criteri di rischio insider come nuovo avviso e viene assegnato un livello di gravità del rischio insider e un punteggio di rischio. Questo criterio consente di valutare questo avviso nel contesto di altre attività incluse nel caso. Se non si sceglie un criterio DLP, è necessario selezionare l'evento di attivazione predefinito.

#### <a name="data-leaks-policy-guidelines"></a>Linee guida per i criteri per le perdite di dati

Quando si creano o si modificano i criteri DLP da utilizzare con i criteri di gestione dei rischi insider, prendere in considerazione le linee guida seguenti:

- Assegnare priorità agli eventi di esfiltrazione dei dati ed essere selettivi quando si assegnano le impostazioni dei rapporti operazioni non consentite su *Alta* durante la configurazione delle regole nei criteri DLP.  Ad esempio, l'invio tramite posta elettronica di documenti sensibili a un concorrente noto deve essere un *evento* di esfiltrazione a livello di avviso elevato. L'assegnazione di  un livello  elevato nelle impostazioni dei rapporti degli eventi imprevisti in altre regole dei criteri DLP può aumentare il rumore nel flusso di lavoro degli avvisi per la gestione dei rischi insider e rendere più difficile per gli investigatori e gli analisti dei dati valutare correttamente questi avvisi. Ad esempio, l'assegnazione di *livelli* di avviso elevati per accedere alle attività di negazione dell'accesso nei criteri DLP rende più difficile valutare il comportamento e le attività degli utenti realmente rischiose.
- Assicurarsi di aver compreso e configurato correttamente gli utenti nell'ambito sia nei criteri di gestione dei rischi DLP che insider. Solo gli utenti definiti come nell'ambito dei  criteri di gestione dei rischi insider che utilizzano il modello Perdite di dati avranno avvisi dei criteri DLP di gravità elevata elaborati. Inoltre, solo gli utenti definiti come nell'ambito di una regola per un avviso DLP di gravità elevata verranno esaminati dal criterio di gestione dei rischi insider da prendere in considerazione. È importante non configurare inconsapevolmente gli utenti nell'ambito sia nei criteri dlp che nei criteri di rischio insider in modo in conflitto.

     Ad esempio, se l'ambito delle regole dei criteri DLP è solo per  gli utenti del team di vendita e il criterio di rischio insider creato dal modello Perdite di dati ha definito tutti gli utenti come nell'ambito, il criterio di rischio Insider eelaborare solo avvisi DLP di gravità elevata per gli utenti del team di vendita. I criteri di rischio insider non riceveranno avvisi DLP ad alta priorità per gli utenti da elaborare che non sono definiti nelle regole DLP in questo esempio. Al contrario, se il criterio di  gestione dei rischi insider creato dai modelli di perdita di dati ha come ambito solo gli utenti del team di vendita e il criterio DLP assegnato è assegnato a tutti gli utenti, il criterio di rischio insider elaverà solo avvisi DLP di gravità elevata per i membri del team vendite. I criteri di gestione dei rischi insider ignoreranno gli avvisi DLP di gravità elevata per tutti gli utenti non del team di vendita.

- Verificare che **l'impostazione della regola** rapporti eventi imprevisti nel criterio DLP utilizzato per questo modello di gestione dei rischi insider sia configurata per gli *avvisi* a livello di gravità elevato. Il *livello di* gravità elevato è che gli eventi di attivazione e gli avvisi di gestione dei rischi insider non verranno generati dalle regole nei criteri DLP con il campo **Rapporti** operazioni non consentite impostato su *Basso* o *Medio.*

    ![Impostazione dell'avviso del criterio DLP](../media/insider-risk-DLP-policy-high-severity.png)

     >[!NOTE]
     >Quando si crea un nuovo criterio DLP utilizzando i modelli predefiniti, è necessario selezionare l'opzione Crea o personalizza regole **DLP** avanzate per configurare l'impostazione Rapporti operazioni non consentite per il livello di *gravità* Elevato. 

A ogni criterio di gestione dei rischi insider creato dal **modello Perdite** di dati può essere assegnato un solo criterio DLP. Prendere in considerazione la creazione di un criterio DLP dedicato che combina le diverse attività che si desidera rilevare e agire come trigger di eventi per i criteri di rischio insider che utilizzano il modello **Perdite di** dati.

Per istruzioni dettagliate sulla configurazione dei criteri DLP per l'organizzazione, vedere l'articolo [Creare, testare](create-test-tune-dlp-policy.md) e ottimizzare un criterio DLP.

### <a name="data-leaks-by-priority-users-preview"></a>Perdite di dati per utenti con priorità (anteprima)

La protezione dei dati e la prevenzione delle perdite di dati per gli utenti dell'organizzazione possono dipendere dalla posizione, dal livello di accesso alle informazioni riservate o dalla cronologia dei rischi. Le perdite di dati possono includere la sovrascrittura accidentale di informazioni estremamente riservate all'esterno dell'organizzazione o il furto di dati con intento dannoso. Con un criterio di prevenzione della perdita dei dati (DLP) assegnato, questo modello inizia a segnare rilevamenti in tempo reale di attività sospette e comporta una maggiore probabilità di avvisi e avvisi di rischio insider con livelli di gravità più elevati. Gli utenti con priorità sono definiti in [gruppi di utenti con priorità](insider-risk-management-settings.md#priority-user-groups-preview) configurate nell'area delle impostazioni di gestione dei rischi insider.

Come per il **modello General data leaks**, è necessario assegnare un criterio DLP per attivare gli indicatori nel criterio di rischio Insider per gli avvisi di gravità elevata nell'organizzazione. Segui le linee guida sui criteri perdite di dati sopra riportate quando crei un criterio usando questo modello. Inoltre, sarà necessario assegnare gruppi di utenti con priorità creati in Impostazioni di gestione dei rischi **Insider** Gruppi di utenti priorità  >    >   al criterio.

### <a name="data-leaks-by-disgruntled-users-preview"></a>Perdite di dati da parte di utenti scontenti (anteprima)

Quando gli utenti sperimentano fattori di stress per l'impiego, possono diventare scontenti, il che può aumentare le probabilità di attività a rischio insider. Questo modello inizia a segnare l'attività dell'utente quando viene identificato un indicatore associato a un discontento. Alcuni esempi includono notifiche di miglioramento delle prestazioni, valutazioni delle prestazioni scarse o modifiche allo stato a livello di processo. Le perdite di dati per gli utenti scontenti possono includere il download di file da SharePoint Online e la copia dei dati nei servizi di messaggistica e archiviazione cloud personali in prossimità di eventi di stress per l'impiego.

Quando si utilizza questo modello, è inoltre necessario configurare un connettore risorse umane di Microsoft 365 per importare periodicamente le notifiche di miglioramento delle prestazioni, lo stato di revisione delle prestazioni scarse o le informazioni sulle modifiche a livello di processo per gli utenti dell'organizzazione. Vedere [l'articolo Importare dati con il](import-hr-data.md) connettore HR per istruzioni dettagliate per configurare il connettore risorse umane di Microsoft 365 per l'organizzazione.

### <a name="general-security-policy-violations-preview"></a>Violazioni generali dei criteri di sicurezza (anteprima)

In molte organizzazioni, gli utenti sono autorizzati a installare software nei propri dispositivi o a modificare le impostazioni dei dispositivi per facilitare le attività. Inavvertitamente o con intento dannoso, gli utenti possono installare malware o disabilitare importanti funzionalità di sicurezza che consentono di proteggere le informazioni nel dispositivo o nelle risorse di rete. Questo modello di criteri usa gli avvisi di sicurezza di Microsoft Defender per Endpoint per iniziare a segnare queste attività, il rilevamento dello stato attivo e gli avvisi per questa area di rischio. Usa questo modello per fornire informazioni dettagliate sulle violazioni dei criteri di sicurezza in scenari in cui gli utenti potrebbero avere una cronologia delle violazioni dei criteri di sicurezza che potrebbero essere un indicatore di rischio insider.

Dovrai configurare Microsoft Defender for Endpoint nell'organizzazione e abilitare Defender for Endpoint per l'integrazione della gestione dei rischi insider nel Defender Security Center per importare gli avvisi di violazione della sicurezza. Per altre informazioni sulla configurazione di Defender per Endpoint per l'integrazione della gestione dei rischi insider, vedi [Configurare le funzionalità avanzate in Defender for Endpoint.](/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center)

### <a name="security-policy-violations-by-departing-users-preview"></a>Violazioni dei criteri di sicurezza da parte degli utenti in partenza (anteprima)

Gli utenti in uscita, indipendentemente dal fatto che si lascino in termini positivi o negativi, potrebbero essere più rischiosi per le violazioni dei criteri di sicurezza. Per proteggere gli utenti in partenza da violazioni di sicurezza accidentali o dannose, questo modello di criteri usa Defender for Endpoint alerts per fornire informazioni dettagliate sulle attività correlate alla sicurezza. Queste attività includono l'installazione di malware o altre applicazioni potenzialmente dannose e la disabilitazione delle funzionalità di sicurezza nei dispositivi. Utilizzando il connettore risorse umane di [Microsoft 365](import-hr-data.md) o l'opzione per monitorare automaticamente l'eliminazione degli account utente in Azure Active Directory per l'organizzazione, questo modello inizia a segnare gli indicatori di rischio relativi a queste attività di sicurezza e la correlazione con lo stato di impiego degli utenti.

Dovrai configurare Microsoft Defender for Endpoint nell'organizzazione e abilitare Defender for Endpoint per l'integrazione della gestione dei rischi insider nel Defender Security Center per importare gli avvisi di violazione della sicurezza. Per altre informazioni sulla configurazione di Defender per Endpoint per l'integrazione della gestione dei rischi insider, vedi [Configurare le funzionalità avanzate in Defender for Endpoint.](/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center)

### <a name="security-policy-violations-by-priority-users-preview"></a>Violazioni dei criteri di sicurezza per utenti con priorità (anteprima)

La protezione da violazioni della sicurezza per gli utenti dell'organizzazione può dipendere dalla posizione, dal livello di accesso alle informazioni riservate o dalla cronologia dei rischi. Poiché le violazioni della sicurezza per priorità degli utenti possono avere un impatto significativo sulle aree critiche dell'organizzazione, questo modello di criteri inizia a segnare su questi indicatori e usa gli avvisi di Microsoft Defender for Endpoint per fornire informazioni dettagliate sulle attività correlate alla sicurezza per questi utenti. Queste attività possono includere l'installazione prioritaria di malware o altre applicazioni potenzialmente dannose e la disabilitazione delle funzionalità di sicurezza nei dispositivi. Gli utenti con priorità sono definiti in gruppi di utenti con priorità configurate nell'area delle impostazioni di gestione dei rischi insider.

Dovrai configurare Microsoft Defender for Endpoint nell'organizzazione e abilitare Defender for Endpoint per l'integrazione della gestione dei rischi insider nel Defender Security Center per importare gli avvisi di violazione della sicurezza. Per altre informazioni sulla configurazione di Defender per Endpoint per l'integrazione della gestione dei rischi insider, vedi [Configurare le funzionalità avanzate in Defender for Endpoint.](/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center) Inoltre, sarà necessario assegnare gruppi di utenti con priorità creati in Impostazioni di gestione dei rischi **Insider** Gruppi di utenti priorità  >    >   al criterio.

### <a name="security-policy-violations-by-disgruntled-users-preview"></a>Violazioni dei criteri di sicurezza da parte di utenti scontenti (anteprima)

Gli utenti che provano stress sul lavoro possono essere a rischio maggiore per violazioni accidentali o dannose dei criteri di sicurezza. Questi stress possono includere l'utente inserito in un piano di miglioramento delle prestazioni, lo stato di valutazione delle prestazioni scarso o l'abbassamento di livello dalla posizione corrente. Questo modello di criteri avvia il punteggio dei rischi in base a questi indicatori e attività associati a questi eventi per questi utenti.

Quando si utilizza questo modello, è inoltre necessario configurare un connettore risorse umane di Microsoft 365 per importare periodicamente le notifiche di miglioramento delle prestazioni, lo stato di revisione delle prestazioni scarse o le informazioni sulle modifiche a livello di processo per gli utenti dell'organizzazione. Vedere [l'articolo Importare dati con il](import-hr-data.md) connettore HR per istruzioni dettagliate per configurare il connettore risorse umane di Microsoft 365 per l'organizzazione.

Dovrai anche configurare Microsoft Defender for Endpoint nell'organizzazione e abilitare Defender for Endpoint per l'integrazione della gestione dei rischi insider nel Defender Security Center per importare gli avvisi di violazione della sicurezza. Per altre informazioni sulla configurazione di Defender per Endpoint per l'integrazione della gestione dei rischi insider, vedi [Configurare le funzionalità avanzate in Defender for Endpoint.](/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center)

### <a name="policy-template-prerequisites-and-triggering-events"></a>Prerequisiti dei modelli di criteri ed eventi di attivazione

A seconda del modello scelto per un criterio di gestione dei rischi insider, gli eventi di attivazione e i prerequisiti dei criteri variano. Gli eventi di attivazione sono prerequisiti che determinano se un utente è attivo per un criterio di gestione dei rischi insider. Se un utente viene aggiunto a un criterio di gestione dei rischi insider ma non dispone di un evento di attivazione, l'attività dell'utente non viene valutata dal criterio, a meno che non venga aggiunto manualmente nel dashboard utenti. I prerequisiti dei criteri sono elementi necessari in modo che il criterio riceva i segnali o le attività necessarie per valutare i rischi.

Nella tabella seguente sono elencati gli eventi di attivazione e i prerequisiti per i criteri creati da ogni modello di criteri di gestione dei rischi insider:

| **Modello di criteri** | **Attivazione di eventi per i criteri** | **Prerequisiti** |
| :------------------ | :--------------------------------- | :---------------- |
| Furto di dati da parte di utenti in partenza | Indicatore della data di disdetta o di chiusura dal connettore HR | (facoltativo) Connettore hr di Microsoft 365 configurato per gli indicatori di data di chiusura e di chiusura o l'integrazione di Azure Active Directory abilitata |
| Perdite di dati generali | Attività dei criteri di perdita dei dati che crea un avviso di gravità elevata | (facoltativo) Criteri DLP configurati per gli avvisi di gravità elevata o l'evento di attivazione dell'esfiltrazione dei dati incorporati |
| Perdite di dati per utenti con priorità | Attività dei criteri di perdita dei dati che crea un avviso di *gravità* elevata o trigger di eventi di exfiltration incorporati | (facoltativo) Criteri DLP configurati per gli avvisi di gravità elevata <br><br> Gruppi di utenti con priorità configurati nelle impostazioni dei rischi insider |
| Perdite di dati da parte di utenti scontenti | Miglioramento delle prestazioni, prestazioni scarse o indicatori di modifica a livello di processo dal connettore HR | Connettore hr di Microsoft 365 configurato per gli indicatori di disgruenza |
| Violazioni generali dei criteri di sicurezza | Evasione difensiva dei controlli di sicurezza o del software indesiderato rilevato da Microsoft Defender for Endpoint | Sottoscrizione attiva a Microsoft Defender per endpoint <br><br> Integrazione di Microsoft Defender for Endpoint con il Centro conformità Microsoft 365 configurato |
| Violazioni dei criteri di sicurezza da parte degli utenti in partenza | Indicatori di data di disdetta o di chiusura dal connettore HR o dall'eliminazione dell'account di Azure Active Directory | (facoltativo) Connettore risorse umane di Microsoft 365 configurato per gli indicatori di data di chiusura e di chiusura <br><br> Sottoscrizione attiva a Microsoft Defender per endpoint <br><br> Integrazione di Microsoft Defender for Endpoint con il Centro conformità Microsoft 365 configurato |
| Violazioni dei criteri di sicurezza per utenti con priorità | Evasione difensiva dei controlli di sicurezza o del software indesiderato rilevato da Microsoft Defender for Endpoint | Sottoscrizione attiva a Microsoft Defender per endpoint <br><br> Integrazione di Microsoft Defender for Endpoint con il Centro conformità Microsoft 365 configurato <br><br> Gruppi di utenti con priorità configurati nelle impostazioni dei rischi insider |
| Violazioni dei criteri di sicurezza da parte di un utente scontento | Miglioramento delle prestazioni, prestazioni scarse o indicatori di modifica a livello di processo dal connettore HR | Connettore hr di Microsoft 365 configurato per gli indicatori di disgruenza <br><br> Sottoscrizione attiva a Microsoft Defender per endpoint <br><br> Integrazione di Microsoft Defender for Endpoint con il Centro conformità Microsoft 365 configurato |

## <a name="prioritize-content-in-policies"></a>Assegnare priorità al contenuto nei criteri

I criteri di gestione dei rischi Insider supportano la specifica di una priorità più alta per il contenuto a seconda della posizione in cui è archiviato o della modalità di classificazione. Se si specifica il contenuto come priorità, aumenta il punteggio di rischio per qualsiasi attività associata, che a sua volta aumenta la probabilità di generare un avviso di gravità elevata. Tuttavia, alcune attività non genereranno un avviso a meno che il contenuto correlato non contenga tipi di informazioni sensibili predefiniti o personalizzati o non sia stato specificato come priorità nel criterio.

Ad esempio, l'organizzazione dispone di un sito di SharePoint dedicato per un progetto estremamente riservato. Le perdite di dati per le informazioni in questo sito di SharePoint potrebbero compromettere il progetto e avere un impatto significativo sul suo successo. Assegnando la priorità a questo sito di SharePoint in un criterio perdite di dati, i punteggi di rischio per le attività idonee vengono aumentati automaticamente. Questa definizione di priorità aumenta la probabilità che queste attività generino un avviso di rischio insider e aumentino il livello di gravità per l'avviso.

Quando si crea un criterio di gestione dei rischi insider nella procedura guidata dei criteri, è possibile scegliere tra le seguenti priorità:

- **Siti di SharePoint:** a qualsiasi attività associata a tutti i tipi di file nei siti di SharePoint definiti viene assegnato un punteggio di rischio più elevato. 
- **Tipi di informazioni riservate**: a tutte le attività associate al contenuto contenente tipi di [informazioni riservate](sensitive-information-type-entity-definitions.md) viene assegnato un punteggio di rischio più elevato.
- **Etichette di riservatezza**: a tutte le attività associate a contenuto a cui sono applicate etichette di [riservatezza](sensitivity-labels.md) specifiche viene assegnato un punteggio di rischio più alto.

## <a name="sequence-detection-preview"></a>Rilevamento della sequenza (anteprima)

Le attività rischiose potrebbero non verificarsi come eventi isolati. Questi rischi fanno spesso parte di una sequenza più ampia di eventi. Una sequenza è un gruppo di due o più attività utente eseguite una dopo l'altra che potrebbero suggerire un rischio elevato. L'identificazione di queste attività correlate è una parte importante della valutazione dei rischi globali. Quando il rilevamento della sequenza è abilitato per i criteri di furti di dati o perdite di dati, le informazioni dettagliate delle attività relative alle informazioni sulla sequenza vengono visualizzate nella scheda **Attività** utente all'interno di un caso di gestione dei rischi insider. I modelli di criteri seguenti supportano il rilevamento delle sequenze:

- Furto di dati da parte di utenti in partenza
- Perdite di dati generali
- Perdite di dati per utenti con priorità
- Perdite di dati da parte di utenti scontenti

Questi criteri di gestione dei rischi insider possono utilizzare indicatori specifici e l'ordine in cui si verificano per rilevare ogni passaggio in una sequenza di rischi. I nomi dei file vengono utilizzati per il mapping delle attività in una sequenza. Questi rischi sono organizzati in quattro categorie principali di attività:

- **Raccolta:** questi segnali di categoria sono incentrati sulle attività di download da parte degli utenti dei criteri nell'ambito. Un esempio di attività in questa categoria è il download di file dai siti di SharePoint.
- **Esfiltrazione:** queste categorie segnalano l'attenzione sulla condivisione o sulle attività di estrazione verso origini interne ed esterne da parte degli utenti dei criteri nell'ambito. Un esempio di attività in questa categoria è l'invio di messaggi di posta elettronica con allegati dall'organizzazione a destinatari esterni.
- **Offuscamento**: questi segnali di categoria si concentrano sul mascheramento delle attività rischiose da parte degli utenti dei criteri nell'ambito. Un esempio di attività in questa categoria è la ridenominazione dei file in un dispositivo.
- **Pulizia: questi segnali** di categoria sono incentrati sulle attività di eliminazione da parte degli utenti dei criteri nell'ambito. Un esempio di attività in questa categoria è l'eliminazione di file da un dispositivo.

>[!NOTE]
>Il rilevamento della sequenza usa gli indicatori abilitati nelle impostazioni globali per la gestione dei rischi insider e gli indicatori selezionati in un criterio. Se gli indicatori appropriati non sono selezionati, il rilevamento della sequenza non funzionerà.

È possibile personalizzare le singole impostazioni di soglia per ogni tipo di rilevamento di sequenza quando viene configurato nel criterio. Queste impostazioni di soglia regolano gli avvisi in base al volume di file associati alla sequenza.

Per altre informazioni sulla gestione del rilevamento di sequenza nella **visualizzazione Attività** utente, vedi Casi di gestione dei rischi [Insider: Attività utente.](insider-risk-management-cases.md#user-activity)

## <a name="cumulative-exfiltration-detection-preview"></a>Rilevamento dell'esfiltrazione cumulativa (anteprima)

Gli indicatori di rischio Insider consentono di identificare livelli insoliti di attività di rischio valutate ogni giorno per gli utenti che sono nell'ambito dei criteri di rischio insider. Il rilevamento cumulativo dell'esfiltrazione usa modelli di machine learning per identificare quando le attività di esfiltrazione degli utenti superano le medie dell'organizzazione se misurate nel tempo e su più tipi di attività di esfiltrazione. Gli analisti e gli investigatori della gestione dei rischi insider possono usare informazioni dettagliate cumulative sul rilevamento delle esfiltrazioni per identificare le attività di esfiltrazione che in genere non generano avvisi, ma sono superiori a quelle tipiche dell'organizzazione. Alcuni esempi potrebbero essere l'esfiltrazione lenta dei dati da parte degli utenti per un intervallo di giorni o quando gli utenti condividono ripetutamente i dati su più canali più del solito per la condivisione dei dati per l'organizzazione.

Il rilevamento dell'esfiltrazione cumulativa è abilitato per impostazione predefinita quando si utilizzano i modelli di criteri seguenti:

- Furto di dati da parte di utenti in partenza
- Perdite di dati generali
- Perdite di dati per utenti con priorità
- Perdite di dati da parte di utenti scontenti

>[!NOTE]
>Il rilevamento cumulativo dell'esfiltrazione utilizza indicatori di esfiltrazione abilitati nelle impostazioni globali per la gestione dei rischi insider e gli indicatori di esfiltrazione selezionati in un criterio. Di conseguenza, il rilevamento cumulativo dell'esfiltrazione viene valutato solo per gli indicatori di esfiltrazione necessari selezionati.

Quando il rilevamento dell'esfiltrazione cumulativa è abilitato per i criteri di furto  o perdita di dati, le informazioni dettagliate delle attività di esfiltrazione cumulativa vengono visualizzate nella scheda Attività utente in un caso di gestione dei rischi insider.

Per altre informazioni sulla gestione delle attività degli utenti, vedi Casi di gestione dei rischi [Insider: Attività utente.](insider-risk-management-cases.md#user-activity)

## <a name="policy-health-preview"></a>Integrità dei criteri (anteprima)

Lo stato di integrità dei criteri fornisce informazioni dettagliate sui potenziali problemi relativi ai criteri di gestione dei rischi insider. La colonna Stato della scheda Criteri può avvisare l'utente dei problemi relativi ai criteri che potrebbero impedire la segnalazione delle attività degli utenti o il motivo per cui il numero di avvisi attività è insolito. Lo stato di integrità dei criteri può anche confermare che il criterio è integro e non richiede attenzione o modifiche alla configurazione.

In caso di problemi con un criterio, lo stato di integrità dei criteri visualizza avvisi di notifica e suggerimenti per aiutarti a intervenire per risolvere i problemi relativi ai criteri. Queste notifiche consentono di risolvere i problemi seguenti:

- Criteri con configurazione incompleta. Questi problemi possono includere utenti o gruppi mancanti nel criterio o altri passaggi di configurazione dei criteri incompleti.
- Criteri con problemi di configurazione degli indicatori. Gli indicatori sono una parte importante di ogni criterio. Se gli indicatori non sono configurati o se sono selezionati un numero troppo basso di indicatori, il criterio potrebbe non valutare le attività rischiose come previsto.
- I trigger dei criteri non funzionano o i requisiti di attivazione dei criteri non sono configurati correttamente. La funzionalità dei criteri può dipendere da altri servizi o requisiti di configurazione per rilevare in modo efficace l'attivazione di eventi per attivare l'assegnazione del punteggio di rischio agli utenti nel criterio. Queste dipendenze possono includere problemi con la configurazione del connettore, la condivisione degli avvisi di Microsoft Defender per endpoint o le impostazioni di configurazione dei criteri di prevenzione della perdita di dati.
- I limiti del volume sono prossimi o oltre i limiti. I criteri di gestione dei rischi insider usano numerosi servizi ed endpoint di Microsoft 365 per aggregare i segnali di attività di rischio. A seconda del numero di utenti nei criteri, i limiti di volume possono ritardare l'identificazione e la segnalazione delle attività di rischio. Per altre informazioni su questi limiti, vedere la sezione Limiti dei modelli di criteri di questo articolo.

Per visualizzare rapidamente lo stato di integrità di un criterio, passare alla scheda Criterio e alla colonna Stato. Di seguito sono riportate le opzioni seguenti relative allo stato di integrità dei criteri per ogni criterio:

- Integro: non sono stati identificati problemi con il criterio.
- Suggerimenti: esistono alcuni problemi con il criterio che potrebbero impedire il funzionamento del criterio come previsto.
- Avvisi: esistono problemi con i criteri che impediranno l'identificazione delle attività rischiose.

Per ulteriori dettagli su eventuali suggerimenti o avvisi, selezionare un criterio nella scheda **Criterio** per aprire la scheda dei dettagli del criterio. Ulteriori informazioni sui suggerimenti e gli avvisi, incluse le indicazioni su come risolvere questi problemi, verranno visualizzate nella sezione Notifiche della scheda dettagli.

![Integrità dei criteri di gestione dei rischi insider](../media/insider-risk-policy-health.png)

Usa la tabella seguente per altre informazioni sui consigli e sulle notifiche di avviso e sulle azioni da intraprendere per risolvere potenziali problemi.

|**Messaggi di notifica**|**Modelli dei criteri**|**Cause/ Provare questa azione per risolvere il problema**|
|:------------------------|:-------------------|:---------------------------|
| I criteri non assegnano i punteggi di rischio all'attività | Tutti i modelli di criteri | È possibile esaminare l'ambito dei criteri e attivare la configurazione degli eventi in modo che il criterio possa assegnare i punteggi di rischio all'attività <br><br> 1. Esaminare gli utenti selezionati per il criterio. Se sono stati selezionati pochi utenti, è possibile selezionare altri utenti. <br> 2. Se si utilizza un connettore HR, verificare che il connettore HR invii i dati corretti. <br> 3. Se si utilizza un criterio DLP come evento di attivazione, controllare la configurazione del criterio DLP per verificare che sia configurato per l'utilizzo in questo criterio. <br> 4. Per i criteri di violazione della sicurezza, esaminare lo stato di valutazione degli avvisi di Microsoft Defender per endpoint selezionato in Impostazioni rischio Insider > rilevamenti intelligenti. Verificare che il filtro degli avvisi non sia troppo stretto. |
| I criteri non hanno generato avvisi | Tutti i modelli di criteri | È possibile esaminare la configurazione dei criteri in modo da analizzare il punteggio dell'attività di cui si è a cuore. <br><br> 1. Verificare di aver selezionato gli indicatori che si desidera segnare. Maggiore è il numero di indicatori selezionati, maggiore è il numero di attività a cui vengono assegnati i punteggi di rischio. <br> 2. Rivedere la personalizzazione della soglia per i criteri. Se le soglie selezionate non sono allineate alla tolleranza di rischio dell'organizzazione, modificare le selezioni in modo che gli avvisi siano creati in base alle soglie preferite. <br> 3. Esaminare gli utenti e i gruppi selezionati per il criterio. Verificare di aver selezionato tutti gli utenti e i gruppi applicabili. <br> 4. Per i criteri di violazione della sicurezza, verificare di aver selezionato lo stato di valutazione degli avvisi che si desidera segnare per gli avvisi di Microsoft Defender for Endpoint in Rilevamenti intelligenti nelle impostazioni.|
| Nessun utente o gruppo è incluso in questo criterio | Tutti i modelli di criteri | Gli utenti o i gruppi non sono assegnati al criterio. <br><br> Modificare i criteri e selezionare gli utenti o i gruppi per il criterio. |
| Non sono stati selezionati indicatori per questo criterio | Tutti i modelli di criteri | Gli indicatori non sono stati selezionati per il criterio <br><br> Modificare i criteri e selezionare gli indicatori dei criteri appropriati per il criterio. |
| Nessun gruppo di utenti con priorità è incluso in questo criterio | - Perdite di dati per utenti con priorità <br> - Violazioni dei criteri di sicurezza da parte degli utenti con priorità | I gruppi di utenti con priorità non vengono assegnati al criterio. <br><br> Configurare i gruppi di utenti con priorità nelle impostazioni di gestione dei rischi Insider e assegnare gruppi di utenti con priorità al criterio. |
| Non è stato selezionato alcun evento di attivazione per questo criterio | Tutti i modelli di criteri | Un evento di attivazione non è configurato per il criterio <br><br> I punteggi di rischio non verranno assegnati alle attività degli utenti finché non si modifica il criterio e si seleziona un evento di attivazione. |
| Il connettore HR non è configurato o funziona come previsto | - Furto di dati da parte dell'utente in partenza <br> - Violazioni dei criteri di sicurezza da parte dell'utente in partenza <br> - Perdite di dati da parte di utenti scontenti <br> - Violazioni dei criteri di sicurezza da parte di utenti scontenti | Si è verificato un problema con il connettore HR. <br><br> 1. Se si utilizza un connettore HR, verificare che il connettore HR invii dati corretti <br><br> OPPURE <br><br> 2. Selezionare l'evento di attivazione dell'eliminazione dell'account Azure AD. |
| Nessun dispositivo è stato onboarded | - Furto di dati da parte di utenti in partenza <br> - Perdite di dati generali <br> - Perdite di dati da parte di utenti scontenti <br> - Perdite di dati per utenti con priorità | Gli indicatori di dispositivo sono selezionati, ma non sono presenti dispositivi onboarded in Microsoft 365 <br><br> Verificare se i dispositivi sono onboarded e soddisfano i requisiti. |
| Il connettore HR non ha caricato dati di recente | - Furto di dati da parte dell'utente in partenza <br> - Violazioni dei criteri di sicurezza da parte dell'utente in partenza <br> - Perdite di dati da parte di utenti scontenti <br> - Violazioni dei criteri di sicurezza da parte di utenti scontenti | Il connettore HR non ha importato dati da più di 7 giorni. <br><br> Verificare che il connettore HR sia configurato correttamente e inviare i dati. |
| Non è possibile controllare lo stato del connettore HR in questo momento, controllare di nuovo in seguito | - Furto di dati da parte dell'utente in partenza <br> - Violazioni dei criteri di sicurezza da parte dell'utente in partenza <br> - Perdite di dati da parte di utenti scontenti <br> - Violazioni dei criteri di sicurezza da parte di utenti scontenti | La soluzione di gestione dei rischi insider non è in grado di controllare lo stato del connettore HR. <br><br> Verificare che il connettore HR sia configurato correttamente e inviare dati oppure tornare e controllare lo stato del criterio.  |
| Il criterio DLP non è selezionato come evento di attivazione | - Perdite di dati generali <br> - Perdite di dati per utenti con priorità | Un criterio DLP non è stato selezionato come evento di attivazione o il criterio DLP selezionato è stato eliminato. <br><br> Modificare il criterio e selezionare un criterio DLP attivo oppure "L'utente esegue un'attività di esfiltrazione" come evento di attivazione nella configurazione dei criteri. |
| Il criterio DLP utilizzato in questo criterio è disattivato | - Perdite di dati generali <br> - Perdite di dati per utenti con priorità | Il criterio DLP utilizzato in questo criterio è disattivato. <br><br> 1. Attivare il criterio DLP assegnato a questo criterio. <br><br> OPPURE <br><br> 2. Modificare questo criterio e selezionare un nuovo criterio DLP o "L'utente esegue un'attività di esfiltrazione" come evento di attivazione nella configurazione dei criteri. |
| I criteri DLP non soddisfano i requisiti | - Perdite di dati generali <br> - Perdite di dati per utenti con priorità | I criteri DLP utilizzati come eventi di attivazione devono essere configurati per generare avvisi di gravità elevata. <br><br>  1. Modificare il criterio DLP per assegnare gli avvisi applicabili *come Gravità elevata*. <br><br> OPPURE <br><br> 2. Modificare questo criterio e selezionare *Utente esegue un'attività di esfiltrazione* come evento di attivazione. |
| L'organizzazione non dispone di una sottoscrizione a Microsoft Defender for Endpoint | - Violazioni generali dei criteri di sicurezza <br> - Violazioni dei criteri di sicurezza da parte degli utenti in partenza <br> - Violazioni dei criteri di sicurezza da parte di utenti scontenti <br> - Violazioni dei criteri di sicurezza da parte degli utenti con priorità | Non è stata rilevata una sottoscrizione attiva a Microsoft Defender for Endpoint per l'organizzazione. <br><br> Finché non viene aggiunta una sottoscrizione a Microsoft Defender for Endpoint, questi criteri non assegnano punteggi di rischio all'attività degli utenti. |
| Gli avvisi di Microsoft Defenders for Endpoint non vengono condivisi con il Centro conformità | - Violazioni generali dei criteri di sicurezza <br> - Violazioni dei criteri di sicurezza da parte degli utenti in partenza <br> - Violazioni dei criteri di sicurezza da parte di utenti scontenti <br> - Violazioni dei criteri di sicurezza da parte degli utenti con priorità | Gli avvisi di Microsoft Defender for Endpoint non vengono condivisi con il Centro conformità. <br><br> Configurare la condivisione degli avvisi di Microsoft Defender for Endpoint. |
| Si sta avvicinando il limite massimo di utenti con punteggio attivo per questo modello di criteri. | Tutti i modelli di criteri | Ogni modello di criteri ha un numero massimo di utenti nell'ambito. Vedi i dettagli della sezione limite del modello. <br><br> Esaminare gli utenti nella scheda Utenti e rimuovere tutti gli utenti che non devono più essere segnati. |

## <a name="policy-template-limits"></a>Limiti dei modelli di criteri

I modelli di criteri di gestione dei rischi Insider usano i limiti per gestire il volume e la velocità di elaborazione per le attività di rischio degli utenti nell'ambito e come questo processo è integrato con il supporto dei servizi di Microsoft 365. Ogni modello di criteri dispone di un numero massimo di utenti a cui è possibile assegnare attivamente i punteggi di rischio per il criterio che può supportare ed elaborare e segnalare in modo efficace le attività di rischio. Gli utenti nell'ambito sono utenti con eventi di attivazione per il criterio.

Il limite per ogni criterio viene calcolato in base al numero totale di utenti univoci che ricevono punteggi di rischio per ogni tipo di modello di criteri. Se il numero di utenti per un tipo di modello di criteri è prossimo o supera il limite di utenti, le prestazioni dei criteri verranno ridotte. Per visualizzare il numero corrente di utenti per un criterio, passare alla scheda Criteri e alla colonna Utenti nell'ambito. Potrebbero essere presenti fino a cinque criteri per qualsiasi modello di criteri. Questi limiti massimi si applicano agli utenti in tutti i criteri che usano un determinato modello di criteri.

Utilizzare la tabella seguente per determinare il numero massimo di utenti nell'ambito supportati per ogni modello di criteri:

|**Modello di criteri**|**Massimo utente corrente nell'ambito**|
|:------------------|:--------------------------------|
| Perdita di dati generale | 15,000 |
| Perdita di dati da parte di utenti scontenti | 7,500 |
| Perdita di dati per utenti con priorità | 1.000 |
| Furto di dati da parte di utenti in partenza | 20,000 |
| Violazioni generali dei criteri di sicurezza | 1.000 |
| Violazione dei criteri di sicurezza per utenti con priorità | 1.000 |
| Violazioni dei criteri di sicurezza da parte degli utenti in partenza | 15,000 |
| Violazioni dei criteri di sicurezza da parte di utenti scontenti | 7,500 |

## <a name="create-a-new-policy"></a>Creare un nuovo criterio

Per creare un nuovo criterio di gestione dei rischi insider, userai la procedura guidata per la gestione dei rischi **insider** nel Centro conformità Microsoft 365.

Completare la procedura seguente per creare un nuovo criterio:

1. Nel Centro [conformità Microsoft 365](https://compliance.microsoft.com)passare a **Gestione dei** rischi Insider e selezionare la **scheda** Criteri.
2. Selezionare **Crea criterio** per aprire la procedura guidata dei criteri.
3. Nella pagina **Modello di** criterio scegliere una categoria di criteri e quindi selezionare il modello per il nuovo criterio. Questi modelli sono costituito da condizioni e indicatori che definiscono le attività di rischio che si desidera rilevare e analizzare. Esaminare i prerequisiti del modello, l'attivazione di eventi e le attività rilevate per verificare che questo modello di criteri sia adatto alle proprie esigenze.

    >[!IMPORTANT]
    >Alcuni modelli di criteri dispongono di prerequisiti che devono essere configurati per il criterio per generare avvisi pertinenti. Se non sono stati configurati i prerequisiti dei criteri applicabili, vedere **passaggio 4** precedente.

4. Selezionare **Avanti** per continuare.
5. Nella pagina **Nome e descrizione** compilare i campi seguenti:
    - **Nome (obbligatorio):** immettere un nome descrittivo per il criterio. Questo nome non può essere modificato dopo la creazione del criterio.
    - **Descrizione (facoltativo):** immettere una descrizione per il criterio.

6. Selezionare **Avanti** per continuare.
7. Nella pagina **Utenti** e  gruppi selezionare Includi  tutti gli utenti e i gruppi oppure Includi utenti e gruppi specifici per definire quali utenti o gruppi sono inclusi nel criterio o se è stato scelto un modello basato su utenti prioritario. selezionare **Aggiungi o modifica gruppi di utenti con priorità**. Se **si seleziona Includi tutti gli utenti** e i gruppi, verranno cercati eventi di attivazione per tutti gli utenti e i gruppi dell'organizzazione per iniziare ad assegnare i punteggi di rischio per il criterio. Selezionando **Includi utenti e gruppi** specifici è possibile definire gli utenti e i gruppi da assegnare al criterio.
8. Selezionare **Avanti** per continuare.
9. Nella pagina **Contenuto per la** definizione delle priorità, è possibile assegnare (se necessario) le origini a cui assegnare la priorità, in modo da aumentare le probabilità di generare un avviso di gravità elevata per tali origini. Selezionare una delle opzioni seguenti:

    - **Si desidera specificare i siti di SharePoint, le etichette di riservatezza e/o i tipi di informazioni riservate come contenuto prioritario.** Selezionando questa opzione, verranno abilitate le pagine di dettaglio della procedura guidata per configurare questi canali.
    - **Non voglio specificare il contenuto** prioritario in questo momento (sarà possibile farlo dopo la creazione del criterio). Se si seleziona questa opzione, le pagine dei dettagli del canale verranno ignorate nella procedura guidata.

10. Selezionare **Avanti** per continuare.

11. Se è stato selezionato Si desidera specificare i siti di SharePoint, le etichette di riservatezza e/o i tipi di informazioni riservate come contenuto prioritario nel passaggio precedente, verranno visualizzate le pagine dei dettagli per i siti di **SharePoint,** i tipi di informazioni riservate e le etichette di  *riservatezza.* Usare queste pagine di dettaglio per definire SharePoint, i tipi di informazioni riservate e le etichette di riservatezza per definire la priorità nel criterio.

    - **Siti di SharePoint**: selezionare **Aggiungi sito di SharePoint** e selezionare i siti di SharePoint a cui si ha accesso e si desidera definire le priorità. Ad esempio, *"group1@contoso.sharepoint.com/sites/group1"*.
    - **Tipo di informazioni riservate:** seleziona **Aggiungi tipo di informazioni** riservate e seleziona i tipi di riservatezza di cui vuoi definire la priorità. Ad esempio, *"U.S. Bank Account Number"* e *"Credit Card Number"*.
    - **Etichette di riservatezza**: selezionare **Aggiungi etichetta di riservatezza** e selezionare le etichette di cui si desidera definire la priorità. Ad esempio, *"Confidential"* e *"Secret"*.

12. Selezionare **Avanti** per continuare.
13. Nella pagina **Indicatori ed** eventi di attivazione [](insider-risk-management-settings.md#indicators) vedrai gli indicatori definiti come disponibili nella pagina Indicatori delle impostazioni di rischio   >  **Insider.** Se è stato selezionato un modello Perdite di dati all'inizio della procedura guidata, è necessario selezionare un criterio DLP nell'elenco *a* discesa dei criteri **DLP** per abilitare gli indicatori di attivazione per il criterio o selezionare l'evento di attivazione predefinito.

    >[!IMPORTANT]
    >Se gli indicatori in questa pagina non possono essere selezionati, è necessario selezionare gli indicatori che si desidera abilitare per tutti i criteri. Puoi usare il **pulsante Attiva indicatori nella** procedura guidata o selezionare gli indicatori nella pagina **Impostazioni** di gestione dei rischi Insider  >    >  **Indicatori di** criteri.

    Selezionare gli indicatori che si desidera applicare al criterio. Se si preferisce non usare le impostazioni di soglia dei criteri predefiniti per questi indicatori, disabilitare l'opzione Usa soglie predefinite consigliate da **Microsoft** e immettere i valori di soglia per ogni indicatore selezionato.

    - Se è stato selezionato almeno un indicatore di *Office* o *dispositivo,* selezionare i ripetitori del **punteggio di rischio in** base alle esigenze. I ripetitori del punteggio di rischio sono applicabili solo per gli indicatori selezionati.
    - Se è stato  selezionato un  modello di criteri Furto di  dati o Perdite di dati, selezionare uno o più metodi di rilevamento della sequenza e un metodo di rilevamento **dell'esfiltrazione** cumulativa da applicare al criterio.

14. Selezionare **Avanti** per continuare.
15. Nella pagina **Soglie indicatore** selezionare l'opzione per l'utilizzo delle soglie degli indicatori predefinite o per specificare soglie personalizzate per singoli indicatori. Per ogni indicatore, scegliere il livello appropriato per generare il livello desiderato di avvisi di attività.
16. Selezionare **Avanti** per continuare.
17. Nella pagina **Revisione** esaminare le impostazioni scelte per il criterio e gli eventuali suggerimenti o avvisi per le selezioni. Selezionare **Modifica** per modificare i valori dei criteri oppure selezionare **Invia** per creare e attivare il criterio.

## <a name="update-a-policy"></a>Aggiornare un criterio

Per aggiornare un criterio di gestione dei rischi insider esistente, si userà la procedura guidata dei criteri nella soluzione di gestione dei rischi **Insider** nel Centro conformità Microsoft 365.

Completare la procedura seguente per gestire un criterio esistente:

1. Nel Centro [conformità Microsoft 365](https://compliance.microsoft.com)passare a **Gestione dei** rischi Insider e selezionare la **scheda** Criteri.
2. Nel dashboard dei criteri selezionare il criterio che si desidera gestire.
3. Nella pagina dei dettagli del criterio seleziona **Modifica criterio**
4. Nella procedura guidata dei criteri non è possibile modificare quanto segue:
    - **Modello di criteri:** modello utilizzato per definire i tipi di indicatori di rischio monitorati dal criterio.
    - **Name**: Nome descrittivo del criterio
5. Nella pagina **Nome e descrizione** aggiornare la descrizione del criterio nel **campo** Descrizione.
6. Selezionare **Avanti** per continuare.
7. Nella pagina **Utenti** e  gruppi selezionare Includi  tutti gli utenti e i gruppi oppure Includi utenti e gruppi specifici per definire quali utenti o gruppi sono inclusi nel criterio o se è stato scelto un modello basato su utenti prioritario. selezionare **Aggiungi o modifica gruppi di utenti con priorità**. Se **si seleziona Includi tutti gli utenti** e i gruppi, verranno cercati eventi di attivazione per tutti gli utenti e i gruppi dell'organizzazione per iniziare ad assegnare i punteggi di rischio per il criterio. Selezionando **Includi utenti e gruppi** specifici è possibile definire gli utenti e i gruppi da assegnare al criterio.
8. Selezionare **Avanti** per continuare.
9. Nella pagina **Contenuto per la** definizione delle priorità, è possibile assegnare (se necessario) le origini a cui assegnare la priorità, in modo da aumentare le probabilità di generare un avviso di gravità elevata per tali origini. Selezionare una delle opzioni seguenti:

    - **Si desidera specificare i siti di SharePoint, le etichette di riservatezza e/o i tipi di informazioni riservate come contenuto prioritario.** Selezionando questa opzione, verranno abilitate le pagine di dettaglio della procedura guidata per configurare questi canali.
    - **Non voglio specificare il contenuto** prioritario in questo momento (sarà possibile farlo dopo la creazione del criterio). Se si seleziona questa opzione, le pagine dei dettagli del canale verranno ignorate nella procedura guidata.

10. Selezionare **Avanti** per continuare.

11. Se è stato selezionato Si desidera specificare i siti di SharePoint, le etichette di riservatezza e/o i tipi di informazioni riservate come contenuto prioritario nel passaggio precedente, verranno visualizzate le pagine dei dettagli per i siti di **SharePoint,** i tipi di informazioni riservate e le etichette di  *riservatezza.* Usare queste pagine di dettaglio per definire SharePoint, i tipi di informazioni riservate e le etichette di riservatezza per definire la priorità nel criterio.

    - **Siti di SharePoint**: selezionare **Aggiungi sito di SharePoint** e selezionare i siti di SharePoint a cui si ha accesso e si desidera definire le priorità. Ad esempio, *"group1@contoso.sharepoint.com/sites/group1"*.
    - **Tipo di informazioni riservate:** seleziona **Aggiungi tipo di informazioni** riservate e seleziona i tipi di riservatezza di cui vuoi definire la priorità. Ad esempio, *"U.S. Bank Account Number"* e *"Credit Card Number"*.
    - **Etichette di riservatezza**: selezionare **Aggiungi etichetta di riservatezza** e selezionare le etichette di cui si desidera definire la priorità. Ad esempio, *"Confidential"* e *"Secret"*.

12. Selezionare **Avanti** per continuare.
13. Nella pagina **Indicatori ed** eventi di attivazione [](insider-risk-management-settings.md#indicators) vedrai gli indicatori definiti come disponibili nella pagina Indicatori delle impostazioni di rischio   >  **Insider.** Se è stato selezionato un modello Perdite di dati all'inizio della procedura guidata, è necessario selezionare un criterio DLP nell'elenco *a* discesa dei criteri **DLP** per abilitare gli indicatori di attivazione per il criterio o selezionare l'evento di attivazione predefinito.

    >[!IMPORTANT]
    >Se gli indicatori in questa pagina non possono essere selezionati, è necessario selezionare gli indicatori che si desidera abilitare per tutti i criteri. Puoi usare il **pulsante Attiva indicatori nella** procedura guidata o selezionare gli indicatori nella pagina **Impostazioni** di gestione dei rischi Insider  >    >  **Indicatori di** criteri.

    Selezionare gli indicatori che si desidera applicare al criterio. Se si preferisce non usare le impostazioni di soglia dei criteri predefiniti per questi indicatori, disabilitare l'opzione Usa soglie predefinite consigliate da **Microsoft** e immettere i valori di soglia per ogni indicatore selezionato.

    - Se è stato selezionato almeno un indicatore di *Office* o *dispositivo,* selezionare i ripetitori del **punteggio di rischio in** base alle esigenze. I ripetitori del punteggio di rischio sono applicabili solo per gli indicatori selezionati.
    - Se è stato  selezionato un  modello di criteri Furto di  dati o Perdite di dati, selezionare uno o più metodi di rilevamento della sequenza e un metodo di rilevamento **dell'esfiltrazione** cumulativa da applicare al criterio.

14. Selezionare **Avanti** per continuare.
15. Nella pagina **Soglie indicatore** selezionare l'opzione per l'utilizzo delle soglie degli indicatori predefinite o per specificare soglie personalizzate per singoli indicatori. Per ogni indicatore, scegliere il livello appropriato per generare il livello desiderato di avvisi di attività.
16. Selezionare **Avanti** per continuare.
17. Nella pagina **Revisione** esaminare le impostazioni scelte per il criterio e gli eventuali suggerimenti o avvisi per le selezioni. Selezionare **Modifica** per modificare i valori dei criteri oppure selezionare **Invia** per creare e attivare il criterio.

## <a name="copy-a-policy"></a>Copiare un criterio

Potrebbe essere necessario creare un nuovo criterio simile a un criterio esistente, ma che richiede solo alcune modifiche alla configurazione. Anziché creare un nuovo criterio da zero, è possibile copiare un criterio esistente e quindi modificare le aree che devono essere aggiornate nel nuovo criterio.

Completare la procedura seguente per copiare un criterio esistente:

1. Nel Centro conformità Microsoft 365 passare a Gestione dei rischi Insider e selezionare la scheda Criteri.
2. Nel dashboard dei criteri selezionare il criterio che si desidera copiare.
3. Nella pagina dei dettagli del criterio selezionare Copia.
4. Nella procedura guidata dei criteri assegnare un nome al nuovo criterio e aggiornare la configurazione dei criteri in base alle esigenze.

## <a name="immediately-start-scoring-user-activity"></a>Iniziare immediatamente a segnare l'attività utente

In alcuni scenari potrebbe essere necessario avviare immediatamente l'assegnazione dei punteggi di rischio agli utenti con criteri di rischio insider al di fuori del flusso di lavoro degli eventi di attivazione della gestione dei rischi insider. Utilizzare  Inizia attività di punteggio  per gli utenti nella scheda Criteri per aggiungere manualmente uno o più criteri di rischio insider per un periodo di tempo specifico, per iniziare immediatamente ad assegnare i punteggi di rischio alla propria attività e per ignorare il requisito per un utente di avere un indicatore di attivazione (ad esempio, una corrispondenza dei criteri DLP). Puoi anche aggiungere un motivo per aggiungere l'utente al criterio, che verrà visualizzato nella sequenza temporale delle attività degli utenti. Gli utenti aggiunti manualmente ai criteri vengono visualizzati nel **dashboard** Utenti e gli avvisi vengono creati se l'attività soddisfa le soglie di avviso dei criteri.

Alcuni scenari in cui potresti voler iniziare immediatamente a segnare le attività degli utenti:

- Quando gli utenti vengono identificati con problemi di rischio e si desidera iniziare immediatamente ad assegnare i punteggi di rischio alla propria attività per uno o più criteri
- Quando si verifica un evento imprevisto che potrebbe richiedere l'avvio immediato dell'assegnazione dei punteggi di rischio all'attività degli utenti coinvolti per uno o più criteri
- Se il connettore HR non è ancora stato configurato, ma si desidera iniziare ad assegnare punteggi di rischio alle attività degli utenti per gli eventi HR caricando un file CSV per gli utenti

>[!NOTE]
>La visualizzazione dei nuovi utenti aggiunti manualmente nel **dashboard** Utenti potrebbe richiedere diverse ore. La visualizzazione delle attività per i 90 giorni precedenti per questi utenti può richiedere fino a 24 ore. Per visualizzare le attività per gli utenti aggiunti manualmente, passare alla scheda **Utenti** e selezionare l'utente nel **dashboard** Utenti e aprire la scheda **Attività** utente nel riquadro dei dettagli.

Per avviare manualmente l'attività di punteggio per gli utenti in uno o più criteri di gestione dei rischi insider, completare i passaggi seguenti:

1. Nel Centro [conformità Microsoft 365](https://compliance.microsoft.com)passare a **Gestione dei** rischi Insider e selezionare la **scheda** Criteri.
2. Nel dashboard dei criteri selezionare i criteri a cui si desidera aggiungere utenti.
3. Selezionare **Avvia attività di punteggio per gli utenti**.
4. Nel campo **Motivo del** riquadro Aggiungi utenti a **più** criteri aggiungere un motivo per l'aggiunta degli utenti.
5. Nel campo **This should last for (choose between 5 and 30 days)** definire il numero di giorni in cui segnare l'attività dell'utente per il criterio a cui viene aggiunto
6. Per cercare utenti in Active Directory, utilizzare il **campo Cerca utente da aggiungere ai** criteri. Digitare il nome dell'utente che si desidera aggiungere ai criteri. Selezionare il nome utente e ripetere l'operazione per assegnare altri utenti ai criteri. L'elenco degli utenti selezionati viene visualizzato nella sezione utenti del riquadro Aggiungi utenti a più criteri.
7. Per importare un elenco di utenti  da aggiungere ai criteri, selezionare Importa per importare un file CSV (valori delimitati da virgole). Il file deve essere nel formato seguente ed è necessario elencare i nomi delle entità utente nel file:

    ```csv
    user principal name
    user1@domain.com
    user2@domain.com
    ```

8. Selezionare Aggiungi utenti ai criteri per accettare le modifiche e aggiungere utenti ai criteri oppure selezionare Annulla per ignorare le modifiche e chiudere la finestra di dialogo.

## <a name="stop-scoring-users-in-a-policy"></a>Interrompere il punteggio degli utenti in un criterio

Per interrompere il punteggio degli utenti in un criterio, vedere l'articolo [Insider risk management users: Remove users from in-scope assignment to policies.](insider-risk-management-users.md#remove-users-from-in-scope-assignment-to-policies)

## <a name="delete-a-policy"></a>Eliminare un criterio

>[!NOTE]
>L'eliminazione di un criterio non elimina gli avvisi attivi o archiviati generati dal criterio.

Per eliminare un criterio di gestione dei rischi insider esistente, eseguire la procedura seguente:

1. Nel Centro [conformità Microsoft 365](https://compliance.microsoft.com)passare a **Gestione dei** rischi Insider e selezionare la **scheda** Criteri.
2. Nel dashboard dei criteri selezionare il criterio che si desidera eliminare.
3. Selezionare **Elimina sulla** barra degli strumenti del dashboard.
4. Nella finestra **di dialogo** Elimina selezionare **Sì** per eliminare il criterio oppure scegliere **Annulla** per chiudere la finestra di dialogo.
