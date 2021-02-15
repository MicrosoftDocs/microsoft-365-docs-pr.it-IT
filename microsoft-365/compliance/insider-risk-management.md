---
title: Informazioni sulla gestione dei rischi Insider
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
ms.collection:
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
ms.openlocfilehash: ceb35fa9e89a5393500cecb82e52f44852e47b6f
ms.sourcegitcommit: c0cfb9b354db56fdd329aec2a89a9b2cf160c4b0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2021
ms.locfileid: "50094667"
---
# <a name="learn-about-insider-risk-management-in-microsoft-365"></a>Informazioni sulla gestione dei rischi Insider in Microsoft 365

La gestione dei rischi Insider è una soluzione di conformità in Microsoft 365 che consente di ridurre al minimo i rischi interni consentendo di rilevare, analizzare e agire su attività dannose e accidentali nell'organizzazione. I criteri di rischio Insider consentono di definire i tipi di rischi da identificare e rilevare nell'organizzazione, inclusa l'azione sui casi e l'escalation dei casi a Microsoft Advanced eDiscovery, se necessario. Gli analisti dei rischi nell'organizzazione possono intraprendere rapidamente le azioni appropriate per assicurarsi che gli utenti siano conformi agli standard di conformità dell'organizzazione.

Guardare il video seguente per scoprire in che modo la gestione dei rischi Insider può aiutare l'organizzazione a prevenire, rilevare e contenere i rischi, classificando al contempo i valori, la cultura e l'esperienza utente dell'organizzazione:
<br>
<br>
>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4j9CN]

## <a name="modern-risk-pain-points"></a>Punti di rischio moderni

La gestione e la riduzione dei rischi nell'organizzazione iniziano con la comprensione dei tipi di rischi rilevati nell'ambiente di lavoro moderno. Alcuni rischi sono guidati da eventi esterni e fattori che non sono direttamente sotto controllo. Altri rischi sono guidati da eventi interni e attività degli utenti che possono essere ridotte al minimo ed evitate. Alcuni esempi sono i rischi derivanti da comportamenti e azioni illegali, inappropriati, non autorizzati o non etici da parte degli utenti dell'organizzazione. Questi comportamenti includono un'ampia gamma di rischi interni da parte degli utenti:

- Perdite di dati sensibili e fuga di dati
- Violazioni di riservatezza
- Furto di proprietà intellettuale (IP)
- Frode
- Insider trading
- Violazioni della conformità alle normative

Gli utenti nell'area di lavoro moderna hanno accesso per creare, gestire e condividere dati in un'ampia gamma di piattaforme e servizi. Nella maggior parte dei casi, le organizzazioni dispongono di risorse e strumenti limitati per identificare e mitigare i rischi a livello di organizzazione, pur nel rispetto degli standard di privacy degli utenti.

La gestione dei rischi Insider usa l'intera gamma di indicatori di servizio e di terze parti per aiutarti a identificare, valutarne e agire rapidamente sull'attività di rischio. Utilizzando i log di Microsoft 365 e Microsoft Graph, la gestione dei rischi Insider consente di definire criteri specifici per identificare gli indicatori di rischio. Questi criteri consentono di identificare le attività rischiose e di agire per attenuare tali rischi.

La gestione dei rischi Insider è centrata sui principi seguenti:

- **Trasparenza:** bilanciare la privacy degli utenti rispetto ai rischi dell'organizzazione con l'architettura basata sulla privacy in base alla progettazione.
- **Configurabile:** criteri configurabili in base ai gruppi di settore, geografico e aziendale.
- **Integrato:** flusso di lavoro integrato nelle soluzioni di conformità di Microsoft 365.
- **Utilizzabile:** fornisce informazioni dettagliate per abilitare le notifiche utente, le indagini sui dati e le indagini degli utenti.

## <a name="workflow"></a>Flusso di lavoro

Il flusso di lavoro di gestione dei rischi Insider consente di identificare, analizzare e intraprendere azioni per affrontare i rischi interni all'organizzazione. Con i modelli di criteri incentrati, la segnalazione completa dell'attività nel servizio Microsoft 365 e gli strumenti di gestione di avvisi e casi, è possibile usare informazioni utili per identificare rapidamente e agire su comportamenti rischiosi.

L'identificazione e la risoluzione delle attività di rischio interne e dei problemi di conformità con la gestione dei rischi Insider in Microsoft 365 usa il flusso di lavoro seguente:

![Flusso di lavoro per la gestione dei rischi Insider](../media/insider-risk-workflow.png)

### <a name="policies"></a>Criteri

[I criteri di gestione dei](insider-risk-management-policies.md) rischi Insider vengono creati utilizzando modelli predefiniti e condizioni dei criteri che definiscono gli eventi di attivazione e gli indicatori di rischio esaminati nell'organizzazione. Queste condizioni includono il modo in cui gli indicatori di rischio vengono utilizzati per gli avvisi, quali utenti sono inclusi nel criterio, quali servizi sono classificati in ordine di priorità e il periodo di tempo di monitoraggio.

È possibile selezionare uno dei modelli di criteri seguenti per iniziare rapidamente a usare la gestione dei rischi Insider:

- [Furto di dati da parte degli utenti](insider-risk-management-policies.md#data-theft-by-departing-users)
- [Perdite di dati generali](insider-risk-management-policies.md#general-data-leaks)
- [Perdite di dati per utenti con priorità (anteprima)](insider-risk-management-policies.md#data-leaks-by-priority-users-preview)
- [Perdite di dati da parte di utenti scontenti (anteprima)](insider-risk-management-policies.md#data-leaks-by-disgruntled-users-preview)
- [Violazioni generali dei criteri di sicurezza (anteprima)](insider-risk-management-policies.md#general-security-policy-violations-preview)
- [Violazioni dei criteri di sicurezza da parte degli utenti (anteprima)](insider-risk-management-policies.md#security-policy-violations-by-departing-users-preview)
- [Violazioni dei criteri di sicurezza da parte degli utenti con priorità (anteprima)](insider-risk-management-policies.md#security-policy-violations-by-priority-users-preview)
- [Violazioni dei criteri di sicurezza da parte di utenti scontenti (anteprima)](insider-risk-management-policies.md#security-policy-violations-by-disgruntled-users-preview)

![Dashboard dei criteri di gestione dei rischi Insider](../media/insider-risk-policy-dashboard.png)

### <a name="alerts"></a>Avvisi

Gli avvisi vengono generati automaticamente dagli indicatori di rischio che soddisfano le condizioni dei criteri e vengono visualizzati nel [dashboard degli avvisi.](insider-risk-management-alerts.md) Questo dashboard consente di visualizzare rapidamente tutti gli avvisi che devono essere esaminati, aperti nel tempo e le statistiche degli avvisi per l'organizzazione. Tutti gli avvisi dei criteri vengono visualizzati con le informazioni seguenti per identificare rapidamente lo stato degli avvisi esistenti e dei nuovi avvisi che devono essere utilizzati:

- Stato
- Gravità
- Ora rilevata
- Caso
- Stato del caso

![Dashboard di avviso per la gestione dei rischi Insider](../media/insider-risk-alerts-dashboard.png)

### <a name="triage"></a>Triage

Le nuove attività utente che devono essere esaminate generano automaticamente avvisi a cui è assegnato lo *stato Revisione* delle esigenze. I revisori possono identificare e rivedere, valutare e valutare rapidamente questi avvisi.

Gli avvisi vengono risolti aprendo un nuovo caso, assegnando l'avviso a un caso esistente o ignorando l'avviso. Usando i filtri degli avvisi, è facile identificare rapidamente gli avvisi in base allo stato, alla gravità o al tempo rilevato. Come parte del processo di valutazione, i revisori possono visualizzare i dettagli degli avvisi per le attività identificate dal criterio, visualizzare le attività degli utenti associate alla corrispondenza dei criteri, vedere la gravità dell'avviso ed esaminare le informazioni del profilo utente.

![Valutazione della gestione dei rischi Insider](../media/insider-risk-triage.png)

### <a name="investigate"></a>Investigare

[I](insider-risk-management-cases.md) casi vengono creati per gli avvisi che richiedono una revisione e un'analisi più approfondite dei dettagli dell'attività e delle circostanze relative alla corrispondenza dei criteri. Il **dashboard dei casi** offre una visualizzazione all-up di tutti i casi attivi, i casi aperti nel tempo e le statistiche dei casi per l'organizzazione. I revisori possono filtrare rapidamente i casi in base allo stato, alla data di apertura del caso e alla data dell'ultimo aggiornamento del caso.

La selezione di un caso nel dashboard del caso apre il caso per l'indagine e la revisione. Questo passaggio è alla base del flusso di lavoro di gestione dei rischi Insider. In quest'area le attività di rischio, le condizioni dei criteri, i dettagli degli avvisi e i dettagli utente vengono sintetizzati in una visualizzazione integrata per i revisori. Gli strumenti di indagine principali in quest'area sono:

- **Attività utente:** l'attività dell'utente viene visualizzata automaticamente in un grafico interattivo che traccia le attività nel tempo e in base al livello di rischio per le attività di rischio correnti o passate. I revisori possono filtrare e visualizzare rapidamente l'intera cronologia dei rischi per l'utente ed esaminare attività specifiche per ulteriori dettagli.
- **Esplora contenuto:** tutti i file di dati e i messaggi di posta elettronica associati alle attività di avviso vengono acquisiti e visualizzati automaticamente in Esplora contenuto. I revisori possono filtrare e visualizzare file e messaggi in base all'origine dati, al tipo di file, ai tag, alla conversazione e a molti altri attributi.
- **Note sul caso:** i revisori possono fornire note per un caso nella sezione Note caso. Questo elenco consolida tutte le note in una visualizzazione centrale e include le informazioni sul revisore e sulla data di invio.

![Analisi della gestione dei rischi Insider](../media/insider-risk-investigate.png)

### <a name="action"></a>Azione

Dopo l'analisi dei casi, i revisori possono agire rapidamente per risolvere il caso o collaborare con altre parti interessate al rischio nell'organizzazione. Se gli utenti violano accidentalmente o inavvertitamente le condizioni dei criteri, è possibile inviare all'utente un semplice promemoria dai modelli di avviso che è possibile personalizzare per l'organizzazione. Queste comunicazioni possono fungere da semplici promemoria o indirizzare l'utente a corsi di aggiornamento o indicazioni per evitare comportamenti rischiosi futuri. Per ulteriori informazioni, vedere Modelli di avviso [per la gestione dei rischi Insider.](insider-risk-management-notices.md)

Nelle situazioni più gravi, potrebbe essere necessario condividere le informazioni sul caso di gestione dei rischi insider con altri revisori o servizi dell'organizzazione. La gestione dei rischi Insider è strettamente integrata con altre soluzioni di conformità di Microsoft 365 per facilitare la risoluzione dei rischi end-to-end.

- **Advanced eDiscovery:** l'escalation di un caso di indagine consente di trasferire i dati e la gestione del caso ad Advanced eDiscovery in Microsoft 365. Advanced eDiscovery fornisce un flusso di lavoro end-to-end per conservare, raccogliere, esaminare, analizzare ed esportare contenuti reattivi alle indagini interne ed esterne dell'organizzazione. Consente ai team legali di gestire l'intero flusso di lavoro di notifica della conservazione a tempo in sospeso. Per ulteriori informazioni sui casi di Advanced eDiscovery, vedere [Panoramica di Advanced eDiscovery in Microsoft 365.](overview-ediscovery-20.md)
- **ServiceNow (anteprima):** ServiceNow è una popolare piattaforma di cloud computing che consente alle organizzazioni di gestire i flussi di lavoro digitali per le operazioni aziendali. La gestione dei rischi Insider supporta la condivisione degli avvisi per i casi con il servizio ServiceNow e consente di creare eventi imprevisti e richieste di modifica relative a singoli casi di rischio Insider. Per ulteriori informazioni sulla condivisione delle informazioni sugli avvisi con ServiceNow, vedere [Condividere un caso con ServiceNow.](insider-risk-management-cases.md#share-the-case)
- Integrazione delle API di gestione di **Office 365 (anteprima):** la gestione dei rischi Insider supporta l'esportazione delle informazioni di avviso nei servizi siem (Security Information and Event Management) tramite le API di gestione di Office 365. L'accesso alle informazioni sugli avvisi nella piattaforma più adatto ai processi di rischio dell'organizzazione offre una maggiore flessibilità nell'agire sulle attività di rischio. Per ulteriori informazioni sull'esportazione di informazioni sugli avvisi con le API di gestione di Office 365, vedere [Esportare avvisi.](insider-risk-management-settings.md#export-alerts-preview)

>[!NOTE]
>Grazie per il feedback e il supporto durante l'anteprima del connettore ServiceNow. We've decided to end the preview of ServiceNow connector and discontinue support in insider risk management on November 30, 2020. Stiamo valutando attivamente metodi alternativi per fornire ai clienti l'integrazione di ServiceNow nella gestione dei rischi Insider.

## <a name="scenarios"></a>Scenari

La gestione dei rischi Insider consente di rilevare, analizzare e intervenire per ridurre i rischi interni all'organizzazione in diversi scenari comuni:

### <a name="data-theft-by-departing-users"></a>Furto di dati da parte degli utenti

Quando gli utenti lasciano un'organizzazione, volontariamente o come risultato della risoluzione, spesso ci sono dubbi legittimi sul rischio che i dati aziendali, dei clienti e degli utenti siano a rischio. Gli utenti possono presupporre che i dati del progetto non siano proprietari o che siano tentati di prendere i dati aziendali per ottenere vantaggi personali e violare i criteri aziendali e gli standard legali. I criteri di gestione [](insider-risk-management-policies.md#policy-templates) dei rischi Insider che usano il modello di criteri Furto dati allontanando gli utenti rilevano automaticamente le attività in genere associate a questo tipo di furto. Con questo criterio, riceverai automaticamente avvisi per le attività sospette associate al furto di dati allontanando gli utenti in modo da poter eseguire le azioni di indagine appropriate. Per questo modello di criteri è necessaria la configurazione di un connettore risorse umane di [Microsoft 365](import-hr-data.md) per l'organizzazione.

### <a name="intentional-or-unintentional-leak-of-sensitive-or-confidential-information"></a>Perdita intenzionale o involontaria di informazioni sensibili o riservate

Nella maggior parte dei casi, gli utenti provano a gestire correttamente le informazioni sensibili o riservate. Tuttavia, a volte gli utenti possono commettere errori e le informazioni vengono condivise accidentalmente all'esterno dell'organizzazione o in violazione dei criteri di protezione delle informazioni. In altre circostanze, gli utenti possono intenzionalmente divulgazione o condivisione di informazioni sensibili e riservate con intento dannoso e per potenziali guadagni personali. I criteri di gestione dei rischi Insider creati con i seguenti modelli di criteri per la perdita di dati rilevano automaticamente le attività in genere associate alla condivisione di informazioni riservate o riservate:

- [Perdite di dati generali](insider-risk-management-policies.md#general-data-leaks)
- [Perdite di dati per utenti con priorità (anteprima)](insider-risk-management-policies.md#data-leaks-by-priority-users-preview)
- [Perdite di dati da parte di utenti scontenti (anteprima)](insider-risk-management-policies.md#data-leaks-by-disgruntled-users-preview)

## <a name="intentional-or-unintentional-security-policy-violations-preview"></a>Violazioni intenzionali o involontarie dei criteri di sicurezza (anteprima)

Gli utenti hanno in genere un elevato livello di controllo quando gestiscono i propri dispositivi nell'ambiente di lavoro moderno. Ciò può includere le autorizzazioni per installare o disinstallare le applicazioni necessarie per le prestazioni dei loro compiti o la possibilità di disabilitare temporaneamente le funzionalità di sicurezza del dispositivo. Indipendentemente dal fatto che questa attività sia accidentale, accidentale o dannosa, questa condotta può rappresentare un rischio per l'organizzazione ed è importante identificare e agire per ridurre al minimo. Per consentire l'identità di queste attività di sicurezza rischiose, i seguenti modelli di violazione dei criteri di sicurezza per la gestione dei rischi Insider punteggia gli indicatori di rischio di sicurezza e usa Microsoft Defender per gli avvisi endpoint per fornire informazioni dettagliate per le attività correlate alla sicurezza:

- [Violazioni generali dei criteri di sicurezza (anteprima)](insider-risk-management-policies.md#general-security-policy-violations-preview)
- [Violazioni dei criteri di sicurezza da parte degli utenti (anteprima)](insider-risk-management-policies.md#security-policy-violations-by-departing-users-preview)
- [Violazioni dei criteri di sicurezza da parte degli utenti con priorità (anteprima)](insider-risk-management-policies.md#security-policy-violations-by-priority-users-preview)
- [Violazioni dei criteri di sicurezza da parte di utenti scontenti (anteprima)](insider-risk-management-policies.md#security-policy-violations-by-disgruntled-users-preview)

## <a name="policies-for-users-based-on-position-access-level-or-risk-history-preview"></a>Criteri per gli utenti in base alla posizione, al livello di accesso o alla cronologia dei rischi (anteprima)

Gli utenti dell'organizzazione possono avere livelli di rischio diversi a seconda della posizione, del livello di accesso alle informazioni riservate o della cronologia dei rischi. Ciò può includere i membri del team dirigenziale dell'organizzazione, gli amministratori IT che dispongono di numerosi privilegi di accesso alla rete e dati oppure utenti con una cronologia passata di attività rischiose. In questi casi, un'ispezione più approfondita e un punteggio di rischio più aggressivo sono importanti per consentire la visualizzazione di avvisi per l'indagine e azioni rapide. Per identificare le attività rischiose per questi tipi di utenti, è possibile creare gruppi di utenti con priorità e creare criteri dai modelli di criteri seguenti:

- [Violazioni dei criteri di sicurezza da parte degli utenti con priorità (anteprima)](insider-risk-management-policies.md#security-policy-violations-by-priority-users-preview)
- [Perdite di dati per utenti con priorità (anteprima)](insider-risk-management-policies.md#data-leaks-by-priority-users-preview)

## <a name="actions-and-behaviors-by-disgruntled-users-preview"></a>Azioni e comportamenti da parte di utenti scontenti (anteprima)

Gli eventi di stress per l'impiego possono influire sul comportamento degli utenti in diversi modi correlati ai rischi insider. Questi stress possono essere una revisione delle prestazioni scadente, un abbassamento di livello della posizione o il posizionamento dell'utente in un piano di revisione delle prestazioni. Anche se la maggior parte degli utenti non risponde in modo dannoso a questi eventi, lo stress di queste azioni può causare ad alcuni utenti di intraprendere azioni che in genere non considerano in circostanze normali. Per facilitare l'identità di questi tipi di attività rischiose, i seguenti modelli di criteri di gestione dei rischi Insider usano il connettore hr di Microsoft 365 e iniziano a segnare gli indicatori di rischio relativi a comportamenti che possono verificarsi in prossimità di eventi stressor di lavoro:

- [Perdite di dati da parte di utenti scontenti (anteprima)](insider-risk-management-policies.md#data-leaks-by-disgruntled-users-preview)
- [Violazioni dei criteri di sicurezza da parte di utenti scontenti (anteprima)](insider-risk-management-policies.md#security-policy-violations-by-disgruntled-users-preview)

## <a name="ready-to-get-started"></a>Pronti per iniziare?

- Vedere [Pianificare la gestione dei rischi Insider](insider-risk-management-plan.md) per informazioni su come prepararsi per abilitare i criteri di gestione dei rischi Insider nell'organizzazione.
- Vedere [Introduzione alle impostazioni di gestione dei rischi Insider](insider-risk-management-settings.md) per configurare le impostazioni globali per i criteri di rischio Insider.
- Vedere [Introduzione alla gestione dei rischi Insider per](insider-risk-management-configure.md) configurare i prerequisiti, creare criteri e iniziare a ricevere avvisi.
