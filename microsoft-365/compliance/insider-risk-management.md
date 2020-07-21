---
title: Gestione dei rischi Insider
description: Informazioni su come ridurre al minimo i rischi nell'organizzazione con la gestione dei rischi insider in Microsoft 365.
keywords: Microsoft 365, rischio Insider, gestione dei rischi, conformità
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
ms.openlocfilehash: d7e06eb025513caa2d4ad61f7b9d8b2a9e0d2cba
ms.sourcegitcommit: a08103bc120bdec7cfeaf67c1be4e221241e69ad
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2020
ms.locfileid: "45199576"
---
# <a name="insider-risk-management-in-microsoft-365"></a>Gestione dei rischi insider in Microsoft 365

Insider Risk Management è una soluzione di conformità in Microsoft 365 che consente di ridurre al minimo i rischi interni, consentendo di rilevare, indagare e agire su attività dannose e involontarie nell'organizzazione. I criteri di rischio Insider consentono di definire i tipi di rischi per identificare e rilevare all'interno dell'organizzazione, ad esempio agendo su casi e casi di escalation a Microsoft Advanced eDiscovery, se necessario. Gli analisti di rischio nell'organizzazione possono rapidamente prendere le azioni appropriate per assicurarsi che gli utenti siano conformi agli standard di conformità dell'organizzazione.

Guardare il video seguente per informazioni su come la gestione dei rischi Insider può aiutare l'organizzazione a prevenire, rilevare e contenere i rischi durante la definizione di priorità per i valori dell'organizzazione, la lingua e l'esperienza utente:
<br>
<br>
>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4j9CN]

## <a name="modern-risk-pain-points"></a>Punti di dolore ai rischi moderni

La gestione e la riduzione dei rischi all'interno dell'organizzazione iniziano con la comprensione dei tipi di rischi riscontrati nei luoghi di lavoro moderni. Alcuni rischi sono basati su eventi esterni e fattori che non rientrano nel controllo diretto. Altri rischi sono basati su eventi interni e attività degli utenti che possono essere minimizzati ed evitati. Alcuni esempi sono i rischi derivanti da comportamenti illegali, inadeguati, non autorizzati o non etici e da azioni da parte di utenti dell'organizzazione. Tali comportamenti includono una vasta gamma di rischi interni provenienti dagli utenti:

- Perdite di dati sensibili e fuoriuscita di dati
- Violazioni della riservatezza
- Furto di proprietà intellettuale (IP)
- Frodi
- Insider Trading
- Violazioni della conformità alle normative

Gli utenti dei luoghi di lavoro moderni hanno accesso alla creazione, alla gestione e alla condivisione dei dati in un ampio spettro di piattaforme e servizi. Nella maggior parte dei casi, le organizzazioni dispongono di risorse e strumenti limitati per identificare e mitigare i rischi a livello di organizzazione e soddisfare anche gli standard sulla privacy degli utenti.

Insider Risk Management utilizza l'intera gamma di indicatori di servizio e di terze parti che consentono di identificare rapidamente, valutare e agire sull'attività di rischio. Utilizzando i registri di Microsoft 365 e Microsoft Graph, Insider Risk Management consente di definire criteri specifici per identificare gli indicatori di rischio. Questi criteri consentono di identificare le attività rischiose e di agire per attenuare tali rischi.

La gestione dei rischi Insider è incentrata sui seguenti principi:

- **Trasparenza**: bilanciare la privacy degli utenti rispetto al rischio dell'organizzazione con l'architettura privacy-by-Design.
- **Configurabile**: criteri configurabili basati su gruppi industriali, geografici e aziendali.
- **Integrated**: workflow integrato tra le soluzioni di conformità di Microsoft 365.
- **Azione**: fornisce informazioni per abilitare le notifiche degli utenti, le indagini sui dati e le indagini degli utenti.

## <a name="workflow"></a>Flusso di lavoro

Il flusso di lavoro di gestione dei rischi insider consente di identificare, indagare ed intervenire per risolvere i rischi interni nell'organizzazione. Con i modelli di criteri focalizzati, la segnalazione di attività complete tra il servizio Microsoft 365 e gli strumenti di gestione dei casi e degli avvisi, è possibile utilizzare informazioni utili per identificare e agire rapidamente su comportamenti a rischio.

L'identificazione e la risoluzione delle attività a rischio interno e i problemi di conformità con la gestione dei rischi insider in Microsoft 365 utilizzano il flusso di lavoro seguente:

![Workflow di gestione dei rischi Insider](../media/insider-risk-workflow.png)

### <a name="policies"></a>Criteri

I [criteri di gestione dei rischi Insider](insider-risk-management-policies.md) vengono creati utilizzando modelli predefiniti e condizioni di criteri che definiscono gli eventi di attivazione e gli indicatori di rischio esaminati nell'organizzazione. Queste condizioni includono la modalità di utilizzo degli indicatori di rischio per gli avvisi, quali sono gli utenti inclusi nel criterio, quali sono le priorità dei servizi e il periodo di tempo di monitoraggio.

È possibile scegliere tra i seguenti [modelli di criteri per iniziare rapidamente con Insider Risk Management:

- [Furto dei dati da parte degli utenti](insider-risk-management-policies.md#data-theft-by-departing-users)
- [Perdite di dati generali](insider-risk-management-policies.md#general-data-leaks)
- [Perdite di dati da parte di utenti prioritari (anteprima)](insider-risk-management-policies.md#data-leaks-by-priority-users-preview)
- [Perdite di dati da parte di utenti scontenti (anteprima)](insider-risk-management-policies.md#data-leaks-by-disgruntled-users-preview)
- [Violazioni generali dei criteri di sicurezza (anteprima)](insider-risk-management-policies.md#general-security-policy-violations-preview)
- [Violazioni dei criteri di sicurezza partendo dagli utenti (anteprima)](insider-risk-management-policies.md#security-policy-violations-by-departing-users-preview)
- [Violazioni dei criteri di sicurezza per gli utenti con priorità (anteprima)](insider-risk-management-policies.md#security-policy-violations-by-priority-users-preview)
- [Violazioni dei criteri di sicurezza da parte di utenti scontenti (anteprima)](insider-risk-management-policies.md#security-policy-violations-by-disgruntled-users-preview)
- [Lingua offensiva nel messaggio di posta elettronica](insider-risk-management-policies.md#offensive-language-in-email)

![Dashboard dei criteri di gestione del rischio Insider](../media/insider-risk-policy-dashboard.png)

### <a name="alerts"></a>Avvisi

Gli avvisi vengono generati automaticamente da indicatori di rischio che soddisfano le condizioni dei criteri e vengono visualizzati nel [Dashboard avvisi](insider-risk-management-alerts.md). Questo dashboard consente di visualizzare rapidamente tutti gli avvisi che richiedono la revisione, gli avvisi aperti nel tempo e le statistiche di avviso per la propria organizzazione. Tutti gli avvisi dei criteri vengono visualizzati con le seguenti informazioni per identificare rapidamente lo stato degli avvisi esistenti e i nuovi avvisi che richiedono un'azione:

- Stato
- Gravità
- Tempo rilevato
- Caso
- Stato del caso

![Dashboard di avviso gestione dei rischi Insider](../media/insider-risk-alerts-dashboard.png)

### <a name="triage"></a>Triage

Le nuove attività utente che richiedono l'analisi generano automaticamente gli avvisi a cui è stato assegnato lo stato di *revisione dei fabbisogni* . I revisori possono identificare e valutare rapidamente gli avvisi e analizzarli, valutarli e verificarli.

Gli avvisi vengono risolti aprendo un nuovo caso, assegnando l'avviso a un caso esistente o ignorando l'avviso. Utilizzando i filtri di avviso, è facile identificare rapidamente gli avvisi in base allo stato, alla gravità o al tempo rilevato. Nell'ambito del processo di valutazione, i revisori possono visualizzare i dettagli degli avvisi per le attività identificate dal criterio, visualizzare le attività degli utenti associate alla corrispondenza dei criteri, vedere la gravità dell'avviso e verificare le informazioni sui profili utente.

![Valutazione della gestione dei rischi Insider](../media/insider-risk-triage.png)

### <a name="investigate"></a>Investigare

I [casi](insider-risk-management-cases.md) vengono creati per gli avvisi che richiedono una revisione e un'analisi più approfondita dei dettagli e delle circostanze dell'attività attorno alla corrispondenza dei criteri. Il **Dashboard del caso** fornisce una visualizzazione all-up di tutti i casi attivi, dei casi aperti nel tempo e delle statistiche del caso per l'organizzazione. I revisori possono filtrare rapidamente i casi in base allo stato, la data in cui è stato aperto il caso e la data in cui è stato aggiornato l'ultimo caso.

Se si seleziona un caso nel dashboard del caso, verrà aperta la causa per l'analisi e la revisione. Questo passaggio è il fulcro del flusso di lavoro di gestione dei rischi Insider. Questa area è la posizione in cui le attività di rischio, le condizioni dei criteri, gli avvisi e i dettagli degli utenti vengono sintetizzati in una visualizzazione integrata per i revisori. Gli strumenti principali di indagine in questo campo sono:

- **Attività utente**: l'attività dell'utente viene visualizzata automaticamente in un grafico interattivo che traccia le attività nel tempo e a livello di rischio per le attività di rischio correnti o precedenti. I revisori possono rapidamente filtrare e visualizzare l'intera cronologia dei rischi per l'utente e analizzare attività specifiche per ulteriori dettagli.
- **Content Explorer**: tutti i file di dati e i messaggi di posta elettronica associati alle attività di avviso vengono acquisiti e visualizzati automaticamente nell'Esplora contenuto. I revisori possono filtrare e visualizzare i file e i messaggi in base all'origine dati, al tipo di file, ai tag, alla conversazione e a molti altri attributi.
- **Note di caso**: i revisori possono fornire note per un caso nella sezione case Notes. Questo elenco consolida tutte le note in una visualizzazione centrale e include reviewer e informazioni presentate dalla data.

![Indagini sulla gestione dei rischi Insider](../media/insider-risk-investigate.png)

### <a name="action"></a>Azione

Dopo aver esaminato i casi, i revisori possono agire rapidamente per risolvere il caso o collaborare con altre parti interessate a rischio nell'organizzazione. Se gli utenti violano accidentalmente o inavvertitamente condizioni dei criteri, è possibile inviare all'utente un semplice avviso di sollecito dai modelli di avviso che è possibile personalizzare per l'organizzazione. Questi avvisi possono essere utili come promemoria semplici o possono indirizzare l'utente all'aggiornamento o alle linee guida per evitare future comportamenti a rischio. Per ulteriori informazioni, vedere [modelli di avviso per la gestione dei rischi Insider](insider-risk-management-notices.md).

Nelle situazioni più gravi, potrebbe essere necessario condividere le informazioni sui casi di gestione dei rischi Insider con altri revisori o servizi nell'organizzazione. La gestione dei rischi Insider è strettamente integrata con altre soluzioni Microsoft 365 Compliance che consentono di risolvere i rischi end-to-end.

- **Advanced eDiscovery**: l'escalation di un caso di indagine consente di trasferire i dati e la gestione del caso in eDiscovery avanzata in Microsoft 365. Advanced eDiscovery offre un flusso di lavoro end-to-end per conservare, raccogliere, rivedere, analizzare ed esportare contenuti rispondenti alle indagini interne ed esterne dell'organizzazione. Consente ai team legali di gestire l'intero flusso di lavoro di notifica della conservazione legale. Per ulteriori informazioni sui casi di eDiscovery avanzati, vedere [Overview of Advanced eDiscovery in Microsoft 365](overview-ediscovery-20.md).
- **ServiceNow (Preview)**: ServiceNow è una popolare piattaforma di cloud computing che aiuta le organizzazioni a gestire i flussi di lavoro digitali per le operazioni aziendali. Insider Risk Management supporta la condivisione di avvisi in caso di problemi con il servizio ServiceNow e consente di creare incidenti e di modificare le richieste relative ai singoli casi di rischio Insider. Per ulteriori informazioni sulla condivisione dei dati di avviso con ServiceNow, vedere [share a case with ServiceNow](insider-risk-management-cases.md#share-a-case).
- **Integrazione di office 365 Management Apis (Preview)**: gestione dei rischi Insider supporta l'esportazione di informazioni sugli avvisi per i servizi di gestione eventi e informazioni di sicurezza mediante le API di gestione di Office 365. Accesso alle informazioni sugli avvisi nella piattaforma i processi di rischio dell'organizzazione consentono una maggiore flessibilità nell'agire sulle attività a rischio. Per ulteriori informazioni su come esportare gli avvisi con le API di gestione di Office 365, vedere [Export Alerts](insider-risk-management-settings.md#export-alerts-preview).

## <a name="scenarios"></a>Scenari

La gestione dei rischi Insider può aiutare a rilevare, indagare ed intervenire per attenuare i rischi interni nell'organizzazione in diversi scenari comuni:

### <a name="data-theft-by-departing-users"></a>Furto dei dati da parte degli utenti

Quando gli utenti lasciano un'organizzazione, volontariamente o come risultato di una terminazione, spesso vi sono preoccupazioni legittime che la società, i clienti e i dati degli utenti sono a rischio. Gli utenti possono accettare innocentemente che i dati del progetto non siano proprietari o che possano essere tentati di prendere i dati dell'azienda per ottenere un guadagno personale e violare la politica aziendale e gli standard giuridici. I criteri di gestione dei rischi Insider che utilizzano il modello [di criteri per il furto dei dati in base agli utenti](insider-risk-management-policies.md#policy-templates) vengono rilevati automaticamente attività tipicamente associate a questo tipo di furto. Con questo criterio, gli utenti riceveranno automaticamente gli avvisi per le attività sospette associate al furto dei dati, in modo da poter intraprendere azioni investigative appropriate. Per questo modello di criteri è necessaria la configurazione di un [connettore Microsoft 365 HR](import-hr-data.md) per l'organizzazione.

### <a name="intentional-or-unintentional-leak-of-sensitive-or-confidential-information"></a>Perdita intenzionale o involontaria di informazioni sensibili o riservate

Nella maggior parte dei casi, gli utenti fanno del loro meglio per gestire in modo appropriato informazioni riservate o sensibili. Tuttavia, occasionalmente, gli utenti possono commettere errori e le informazioni vengono condivise accidentalmente all'esterno dell'organizzazione o in violazione dei criteri di protezione delle informazioni. In altri casi, gli utenti possono intenzionalmente infiltrazioni o condividere informazioni riservate e confidenziali con intenti dolosi e potenziali guadagni personali. I criteri di gestione dei rischi Insider creati utilizzando i modelli di criteri per le perdite di dati seguenti consentono di rilevare automaticamente le attività tipicamente associate alla condivisione di informazioni riservate

- [Perdite di dati generali](insider-risk-management-policies.md#general-data-leaks)
- [Perdite di dati da parte di utenti prioritari (anteprima)](insider-risk-management-policies.md#data-leaks-by-priority-users-preview)
- [Perdite di dati da parte di utenti scontenti (anteprima)](insider-risk-management-policies.md#data-leaks-by-disgruntled-users-preview)

### <a name="offensive-behavior-that-violates-corporate-policies"></a>Comportamenti offensivi che violano i criteri aziendali

Le comunicazioni da utente a utente spesso sono un'origine di violazioni involontarie o dannose dei criteri aziendali. Tali violazioni possono includere il linguaggio offensivo, le minacce e le molestie tra gli utenti. Questo tipo di attività contribuisce a un ambiente di lavoro ostile e può provocare azioni legali nei confronti di entrambi gli utenti e l'organizzazione più grande. Insider Risk Management utilizza nuovi classificatori Microsoft 365 incorporati e la [lingua offensiva nel](insider-risk-management-policies.md#offensive-language-in-email) modello di criteri di posta elettronica per ridurre al minimo tali rischi. Questo modello di criteri consente di configurare e abilitare rapidamente un criterio per rilevare automaticamente e avvisare l'utente di questo tipo di comportamento nell'organizzazione.

## <a name="intentional-or-unintentional-security-policy-violations-preview"></a>Violazioni dei criteri di sicurezza intenzionale o involontaria (anteprima)

Gli utenti in genere dispongono di un elevato livello di controllo per la gestione dei dispositivi nel luogo di lavoro moderno. Ciò può includere le autorizzazioni per l'installazione o la disinstallazione di applicazioni necessarie per l'esecuzione delle loro mansioni o la possibilità di disabilitare temporaneamente le funzionalità di sicurezza dei dispositivi. Se questa attività è involontaria, accidentale o dannosa, questa condotta può rappresentare un rischio per la propria organizzazione ed è importante identificare e agire per minimizzare. Per semplificare l'identità di queste attività di sicurezza, i modelli di violazione dei criteri di sicurezza di gestione del rischio Insider seguenti sono punteggi degli indicatori di rischio per la sicurezza e utilizzano gli avvisi di Microsoft Defender Advanced Threat Protection (ATP) per fornire informazioni utili per le attività relative alla sicurezza:

- [Violazioni generali dei criteri di sicurezza (anteprima)](insider-risk-management-policies.md#general-security-policy-violations-preview)
- [Violazioni dei criteri di sicurezza partendo dagli utenti (anteprima)](insider-risk-management-policies.md#security-policy-violations-by-departing-users-preview)
- [Violazioni dei criteri di sicurezza per gli utenti con priorità (anteprima)](insider-risk-management-policies.md#security-policy-violations-by-priority-users-preview)
- [Violazioni dei criteri di sicurezza da parte di utenti scontenti (anteprima)](insider-risk-management-policies.md#security-policy-violations-by-disgruntled-users-preview)

## <a name="policies-for-users-based-on-position-access-level-or-risk-history-preview"></a>Criteri per gli utenti in base alla posizione, al livello di accesso o alla cronologia dei rischi (anteprima)

Gli utenti dell'organizzazione possono avere livelli di rischio diversi a seconda della posizione, del livello di accesso alle informazioni riservate o della cronologia dei rischi. Questo può includere i membri del team direttivo dell'organizzazione, gli amministratori IT che dispongono di numerosi privilegi di accesso ai dati e di rete o gli utenti con una cronologia passata di attività a rischio. In questi casi, l'ispezione più ravvicinata e il Punteggio dei rischi più aggressivi sono importanti per aiutare gli avvisi di superficie per l'analisi e l'azione rapida. Per identificare le attività rischiose per questi tipi di utenti, è possibile creare gruppi di utenti prioritari e creare criteri dai modelli di criteri seguenti:

- [Violazioni dei criteri di sicurezza per gli utenti con priorità (anteprima)](insider-risk-management-policies.md#security-policy-violations-by-priority-users-preview)
- [Perdite di dati da parte di utenti prioritari (anteprima)](insider-risk-management-policies.md#data-leaks-by-priority-users-preview)

## <a name="actions-and-behaviors-by-disgruntled-users-preview"></a>Azioni e comportamenti da parte di utenti scontenti (anteprima)

Stress occupazionali gli eventi possono influire sul comportamento degli utenti in diversi modi correlati ai rischi Insider. Tali fattori di stress possono essere una valutazione delle prestazioni scadente, una retrocessione della posizione o l'utente che si trova in un piano di valutazione delle prestazioni. Anche se la maggior parte degli utenti non risponde a questi eventi in modo dannoso, la sollecitazione di queste azioni può comportare la possibilità di eseguire azioni che normalmente non possono prendere in considerazione durante la normale situazione. Per agevolare l'identità di questi tipi di attività a rischio, i seguenti modelli di criteri di gestione dei rischi Insider utilizzano il connettore Microsoft 365 HR e iniziano a segnare indicatori di rischio relativi a comportamenti che possono verificarsi in prossimità di eventi di stress occupazionale:

- [Perdite di dati da parte di utenti scontenti (anteprima)](insider-risk-management-policies.md#data-leaks-by-disgruntled-users-preview)
- [Violazioni dei criteri di sicurezza da parte di utenti scontenti (anteprima)](insider-risk-management-policies.md#security-policy-violations-by-disgruntled-users-preview)

## <a name="ready-to-get-started"></a>Pronti per iniziare?

- Per informazioni su come prepararsi per abilitare i criteri di gestione dei rischi Insider nell'organizzazione, vedere [Plan for Insider Risk Management](insider-risk-management-plan.md) .
- Per configurare le impostazioni globali per i criteri di rischio Insider, vedere [Introduzione alle impostazioni di gestione dei rischi Insider](insider-risk-management-settings.md) .
- Vedere [Introduzione alla gestione dei rischi Insider](insider-risk-management-configure.md) per configurare i prerequisiti, creare criteri e iniziare a ricevere avvisi.
