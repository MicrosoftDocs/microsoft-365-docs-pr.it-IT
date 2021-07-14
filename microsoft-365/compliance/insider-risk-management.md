---
title: Informazioni sulla gestione dei rischi Insider
description: Informazioni su come ridurre al minimo i rischi nell'organizzazione con la gestione dei rischi insider in Microsoft 365.
keywords: Microsoft 365, rischio insider, gestione dei rischi, conformità
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
ms.openlocfilehash: e033142567c0eb33987cae6d840abf5f6422365e
ms.sourcegitcommit: 997a21b83795789cda0a6b4a77f9985a3233d0c0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2021
ms.locfileid: "53430601"
---
# <a name="learn-about-insider-risk-management-in-microsoft-365"></a>Informazioni sulla gestione dei rischi insider in Microsoft 365

La gestione dei rischi insider è una soluzione di conformità in Microsoft 365 che consente di ridurre al minimo i rischi interni consentendo di rilevare, analizzare e agire su attività dannose e involontarie nell'organizzazione. I criteri di rischio Insider consentono di definire i tipi di rischi da identificare e rilevare nell'organizzazione, inclusa l'azione sui casi e l'escalation dei casi a Microsoft Advanced eDiscovery se necessario. Gli analisti dei rischi nell'organizzazione possono intraprendere rapidamente azioni appropriate per assicurarsi che gli utenti siano conformi agli standard di conformità dell'organizzazione.

Guarda i video seguenti per scoprire in che modo la gestione dei rischi insider può aiutare l'organizzazione a prevenire, rilevare e contenere rischi, assegnando al tempo stesso la priorità ai valori, alla cultura e all'esperienza utente dell'organizzazione:
<br>
<br>

**Soluzione di gestione dei rischi insider & sviluppo**:
>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4j9CN]
<br>

**Flusso di lavoro per la gestione dei rischi Insider**:
>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4OUXB]

## <a name="modern-risk-pain-points"></a>Punti di rischio moderni

Le attività di gestione e riduzione del rischio in un'organizzazione iniziano con la comprensione dei tipi di rischio riscontrati nei moderni ambienti di lavoro. Alcuni rischi sono guidati da eventi esterni e fattori esterni al controllo diretto. Altri rischi sono generati da eventi interni e attività utente che possono essere ridotte al minimo ed evitate. Alcuni esempi sono i rischi derivanti da comportamenti e azioni illegali, inappropriati, non autorizzati o non etici da parte degli utenti dell'organizzazione. Questi comportamenti includono un'ampia gamma di rischi interni da parte degli utenti:

- Divulgazione di dati sensibili e fuga di dati
- Violazioni della riservatezza
- Furto della proprietà intellettuale
- Frode
- Insider trading
- Violazioni della conformità alle normative

Gli utenti nell'ambiente di lavoro moderno hanno accesso alla creazione, alla gestione e alla condivisione dei dati in un'ampia gamma di piattaforme e servizi. Nella maggior parte dei casi, le organizzazioni dispongono di risorse e strumenti limitati per identificare e ridurre i rischi a livello di organizzazione, oltre a soddisfare gli standard di privacy degli utenti.

La gestione dei rischi insider usa l'intera gamma di indicatori di servizio e di terze parti per identificare, eseguire la valutazione e agire rapidamente sulle attività di rischio. Utilizzando i log di Microsoft 365 e Microsoft Graph, la gestione dei rischi insider consente di definire criteri specifici per identificare gli indicatori di rischio. Questi criteri consentono di identificare le attività rischiose e di agire per attenuare tali rischi.

La gestione dei rischi insider è centrata sui principi seguenti:

- **Trasparenza:** bilanciare la privacy degli utenti rispetto ai rischi dell'organizzazione con l'architettura basata sulla privacy per progettazione.
- **Configurabile**: criteri configurabili in base a gruppi industriali, geografici e aziendali.
- **Integrated**: flusso di lavoro integrato tra Microsoft 365 soluzioni di conformità.
- **Utilizzabile:** fornisce informazioni dettagliate per abilitare le notifiche dei revisori, le indagini sui dati e le indagini degli utenti.

## <a name="identifying-potential-risks-with-analytics-preview"></a>Identificazione dei rischi potenziali con l'analisi (anteprima)

L'analisi del rischio Insider consente di condurre una valutazione dei potenziali rischi insider nell'organizzazione senza configurare criteri di rischio Insider. Questa valutazione può aiutare l'organizzazione a identificare le potenziali aree con rischio utente più elevato e a determinare il tipo e l'ambito dei criteri di gestione dei rischi Insider che può essere opportuno configurare. Questa valutazione può anche aiutare a determinare le esigenze di ulteriori licenze o l'ottimizzazione futura dei criteri di rischio insider esistenti.

Per altre informazioni sull'analisi dei rischi insider, vedi Impostazioni di gestione dei rischi [insider: Analisi.](insider-risk-management-settings.md#analytics-preview)

## <a name="workflow"></a>Flusso di lavoro

Il flusso di lavoro per la gestione dei rischi insider consente di identificare, analizzare e intervenire per affrontare i rischi interni nell'organizzazione. Con i modelli di criteri mirati, la segnalazione completa delle attività nel servizio Microsoft 365 e gli strumenti di gestione di avvisi e casi, puoi usare informazioni dettagliate utili per identificare e agire rapidamente su comportamenti rischiosi.

L'identificazione e risoluzione delle attività di rischio interno e dei problemi di conformità con la gestione dei rischi Insider in Microsoft 365 si basa sul seguente flusso di lavoro:

![Flusso di lavoro della gestione dei rischi Insider](../media/insider-risk-workflow.png)

### <a name="policies"></a>Criteri

[I criteri di gestione dei](insider-risk-management-policies.md) rischi Insider vengono creati utilizzando modelli predefiniti e condizioni dei criteri che definiscono quali eventi di attivazione e indicatori di rischio vengono esaminati nell'organizzazione. Queste condizioni includono la modalità di utilizzo degli indicatori di rischio per gli avvisi, gli utenti inclusi nel criterio, la priorità dei servizi e il periodo di tempo di monitoraggio.

È possibile selezionare uno dei modelli di criteri seguenti per iniziare rapidamente a usare la gestione dei rischi insider:

- [Furto di dati da parte di utenti che lasciano l'organizzazione](insider-risk-management-policies.md#data-theft-by-departing-users)
- [Fughe di dati generali](insider-risk-management-policies.md#general-data-leaks)
- [Perdita di dati per utenti con priorità (anteprima)](insider-risk-management-policies.md#data-leaks-by-priority-users-preview)
- [Perdite di dati da parte di utenti scontenti (anteprima)](insider-risk-management-policies.md#data-leaks-by-disgruntled-users-preview)
- [Violazioni dei criteri di sicurezza generali (anteprima)](insider-risk-management-policies.md#general-security-policy-violations-preview)
- [Violazioni dei criteri di sicurezza da parte di utenti che lasciano l'organizzazione (anteprima)](insider-risk-management-policies.md#security-policy-violations-by-departing-users-preview)
- [Violazioni dei criteri di sicurezza per utenti con priorità (anteprima)](insider-risk-management-policies.md#security-policy-violations-by-priority-users-preview)
- [Violazioni dei criteri di sicurezza da parte di utenti scontenti (anteprima)](insider-risk-management-policies.md#security-policy-violations-by-disgruntled-users-preview)

![Dashboard dei criteri di gestione dei rischi Insider](../media/insider-risk-policy-dashboard.png)

### <a name="alerts"></a>Avvisi

Gli avvisi vengono generati automaticamente dagli indicatori di rischio che soddisfano le condizioni dei criteri e vengono visualizzati nel [dashboard Avvisi.](insider-risk-management-activities.md#alert-dashboard) Tale dashboard offre una vista rapida di tutti gli avvisi che necessitano di revisione, della loro creazione nel tempo e statistiche sugli avvisi dell'organizzazione. Tutti gli avvisi dei criteri vengono visualizzati con le informazioni seguenti per identificare rapidamente lo stato degli avvisi esistenti e dei nuovi avvisi che necessitano di azioni:

- Stato
- Gravità
- Tempo rilevato
- Caso
- Stato del caso

![Dashboard di avviso per la gestione dei rischi Insider](../media/insider-risk-alerts-dashboard.png)

### <a name="triage"></a>Triage

Le nuove attività utente che necessitano di analisi generano automaticamente avvisi a cui è assegnato lo *stato Revisione* esigenze. I revisori possono identificare e rivedere, valutare e valutare rapidamente questi avvisi.

Gli avvisi vengono risolti aprendo un nuovo caso, assegnando l'avviso a un caso già esistente oppure ignorandolo. Usando i filtri di avviso, è facile identificare rapidamente gli avvisi in base allo stato, alla gravità o al tempo rilevato. Nell'ambito del processo di valutazione, i revisori possono visualizzare i dettagli dell'avviso per le attività identificate dal criterio, visualizzare le attività utente associate alla corrispondenza dei criteri, vedere la gravità dell'avviso ed esaminare le informazioni del profilo utente.

![Valutazione della gestione dei rischi insider](../media/insider-risk-triage.png)

### <a name="investigate"></a>Esame

Analizzare rapidamente tutte le attività per un utente selezionato con [Report attività utente (anteprima).](insider-risk-management-activities.md#user-activity-reports-preview) Questi report consentono ai ricercatori dell'organizzazione di esaminare le attività per utenti specifici per un periodo di tempo definito senza doverli assegnare temporaneamente o esplicitamente a un criterio di gestione dei rischi insider. Dopo aver esaminato le attività per un utente, gli investigatori possono ignorare le singole attività come benigne, condividere o inviare tramite posta elettronica un collegamento al report con altri investigatori oppure scegliere di assegnare l'utente temporaneamente o esplicitamente a un criterio di gestione dei rischi insider.

[I](insider-risk-management-cases.md) casi vengono creati per gli avvisi che richiedono una revisione e un'analisi più approfondite dei dettagli dell'attività e delle circostanze relative alla corrispondenza dei criteri. La **dashboard dei casi** offre una visione d'insieme di tutti i casi attivi, dei casi aperti nel tempo e delle relative statistiche dell'organizzazione. I revisori possono filtrare rapidamente i casi in base allo stato, alla data di apertura del caso e alla data dell'ultimo aggiornamento del caso.

Selezionando un caso in tale dashboard, si aprirà il caso per l'indagine e la revisione. Questo passaggio è il cuore del flusso di lavoro per la gestione dei rischi insider. In quest'area le attività di rischio, le condizioni dei criteri, i dettagli degli avvisi e i dettagli degli utenti vengono sintetizzati in una visualizzazione integrata per i revisori. Gli strumenti di indagine principali in quest'area sono:

- **Attività utente**: l'attività dell'utente viene visualizzata automaticamente in un grafico interattivo che traccia le attività nel tempo e in base al livello di rischio per le attività di rischio correnti o passate. I revisori possono filtrare e visualizzare rapidamente l'intera cronologia dei rischi per l'utente ed esaminare attività specifiche per ulteriori dettagli.
- **Esplora contenuto:** tutti i file di dati e i messaggi di posta elettronica associati alle attività di avviso vengono acquisiti e visualizzati automaticamente in Esplora contenuto. I revisori possono filtrare e visualizzare file e messaggi in base all'origine dati, al tipo di file, ai tag, alla conversazione e a molti altri attributi.
- **Note caso:** i revisori possono fornire note per un caso nella sezione Note caso. Questo elenco consolida tutte le note in una visualizzazione centrale e include le informazioni relative al revisore e alla data di invio.

![Indagine sulla gestione dei rischi insider](../media/insider-risk-investigate.png)

Inoltre, il nuovo log di controllo [(anteprima)](insider-risk-management-audit-log.md) consente di rimanere informati sulle azioni intraprese sulle funzionalità di gestione dei rischi insider. Questa risorsa consente una revisione indipendente delle azioni intraprese dagli utenti assegnati a uno o più gruppi di ruoli di gestione dei rischi insider.

### <a name="action"></a>Azione

Dopo l'analisi dei casi, i revisori possono agire rapidamente per risolvere il caso o collaborare con altre parti interessate al rischio nell'organizzazione. Se gli utenti violano accidentalmente o inavvertitamente le condizioni dei criteri, è possibile inviare all'utente un semplice promemoria dai modelli di avviso che è possibile personalizzare per l'organizzazione. Questi avvisi possono essere utilizzati come semplici promemoria o possono indirizzare l'utente a corsi di aggiornamento o indicazioni per evitare comportamenti futuri rischiosi. Per ulteriori informazioni, consultare la sezione [Modelli di notifica per la gestione dei rischi Insider](insider-risk-management-notices.md).

Nelle situazioni più gravi potrebbe essere necessario condividere le informazioni sul caso di gestione dei rischi insider con altri revisori o servizi dell'organizzazione. La gestione dei rischi insider è strettamente integrata con altre Microsoft 365 di conformità per facilitare la risoluzione dei rischi end-to-end.

- **Advanced eDiscovery**: l'escalation di un caso di indagine consente di trasferire i dati e la gestione del caso Advanced eDiscovery in Microsoft 365. La soluzione Advanced eDiscovery offre un flusso di lavoro end-to-end per conservare, raccogliere, rivedere, analizzare ed esportare contenuti rilevanti per le indagini interne ed esterne dell'organizzazione. Consente ai team legali di gestire l'intero flusso di lavoro per le notifiche di blocco a fini giudiziari. Per maggiori informazioni sui casi di Advanced eDiscovery, consultare la [Panoramica di Advanced eDiscovery in Microsoft 365](overview-ediscovery-20.md).
- integrazione delle API di gestione di **Office 365 (anteprima):** la gestione dei rischi Insider supporta l'esportazione delle informazioni sugli avvisi nei servizi siem (Security Information and Event Management) tramite le API di Office 365 Management. L'accesso alle informazioni sugli avvisi nella piattaforma più adatto ai processi di rischio dell'organizzazione offre maggiore flessibilità nell'agire sulle attività a rischio. Per altre informazioni sull'esportazione delle informazioni sugli avvisi con Office 365 Management API, vedi [Esportare avvisi.](insider-risk-management-settings.md#export-alerts-preview)

> [!NOTE]
> Grazie per il feedback e il supporto durante l'anteprima del connettore ServiceNow. Abbiamo deciso di terminare l'anteprima del connettore ServiceNow e interrompere il supporto nella gestione dei rischi insider il 30 novembre 2020. Stiamo valutando attivamente metodi alternativi per fornire ai clienti l'integrazione di ServiceNow nella gestione dei rischi insider.

## <a name="scenarios"></a>Scenari

La gestione dei rischi insider consente di rilevare, analizzare e intervenire per ridurre i rischi interni nell'organizzazione in diversi scenari comuni:

### <a name="data-theft-by-departing-users"></a>Furto di dati da parte di utenti che lasciano l'organizzazione

Quando gli utenti lasciano un'organizzazione, volontariamente o come risultato della risoluzione, spesso vi sono dubbi legittimi che i dati aziendali, dei clienti e degli utenti siano a rischio. Gli utenti possono presupporre che i dati del progetto non siano proprietari oppure potrebbero essere tentati di prendere i dati aziendali per ottenere profitti personali e violare i criteri aziendali e gli standard legali. I criteri di gestione [](insider-risk-management-policies.md#policy-templates) dei rischi insider che utilizzano il modello di criteri Furto di dati usurpando gli utenti rilevano automaticamente le attività in genere associate a questo tipo di furto. Con questo criterio, riceverai automaticamente avvisi per le attività sospette associate al furto di dati allontanando gli utenti in modo da poter intraprendere azioni investigative appropriate. Per questo modello di Microsoft 365 è necessaria la configurazione di un [connettore per](import-hr-data.md) le risorse umane per l'organizzazione.

### <a name="intentional-or-unintentional-leak-of-sensitive-or-confidential-information"></a>Perdita intenzionale o involontaria di informazioni riservate o riservate

Nella maggior parte dei casi, gli utenti cercano di gestire correttamente le informazioni riservate o riservate. Tuttavia, a volte gli utenti possono commettere errori e le informazioni vengono condivise accidentalmente all'esterno dell'organizzazione o in violazione dei criteri di protezione delle informazioni. In altre circostanze, gli utenti possono intenzionalmente perdere o condividere informazioni riservate e riservate con intenti dannosi e per potenziali guadagni personali. I criteri di gestione dei rischi insider creati utilizzando i modelli di criteri perdite di dati rilevano automaticamente le attività in genere associate alla condivisione di informazioni riservate o riservate:

- [Fughe di dati generali](insider-risk-management-policies.md#general-data-leaks)
- [Perdita di dati per utenti con priorità (anteprima)](insider-risk-management-policies.md#data-leaks-by-priority-users-preview)
- [Perdite di dati da parte di utenti scontenti (anteprima)](insider-risk-management-policies.md#data-leaks-by-disgruntled-users-preview)

## <a name="intentional-or-unintentional-security-policy-violations-preview"></a>Violazioni intenzionali o involontarie dei criteri di sicurezza (anteprima)

Gli utenti hanno in genere un ampio livello di controllo quando gestiscono i propri dispositivi nell'ambiente di lavoro moderno. Questo controllo può includere le autorizzazioni per installare o disinstallare le applicazioni necessarie per le prestazioni dei propri compiti o la possibilità di disabilitare temporaneamente le funzionalità di sicurezza del dispositivo. Se questa attività è accidentale, accidentale o dannosa, questo comportamento può rappresentare un rischio per l'organizzazione ed è importante identificare e agire per ridurre al minimo. Per consentire l'identità di queste attività di sicurezza rischiose, i modelli di violazione dei criteri di sicurezza della gestione dei rischi insider seguenti segnano gli indicatori di rischio per la sicurezza e utilizzano Gli avvisi di Microsoft Defender for Endpoint per fornire informazioni dettagliate per le attività correlate alla sicurezza:

- [Violazioni dei criteri di sicurezza generali (anteprima)](insider-risk-management-policies.md#general-security-policy-violations-preview)
- [Violazioni dei criteri di sicurezza da parte di utenti che lasciano l'organizzazione (anteprima)](insider-risk-management-policies.md#security-policy-violations-by-departing-users-preview)
- [Violazioni dei criteri di sicurezza per utenti con priorità (anteprima)](insider-risk-management-policies.md#security-policy-violations-by-priority-users-preview)
- [Violazioni dei criteri di sicurezza da parte di utenti scontenti (anteprima)](insider-risk-management-policies.md#security-policy-violations-by-disgruntled-users-preview)

## <a name="policies-for-users-based-on-position-access-level-or-risk-history-preview"></a>Criteri per gli utenti in base alla posizione, al livello di accesso o alla cronologia dei rischi (anteprima)

Gli utenti dell'organizzazione possono avere livelli di rischio diversi a seconda della posizione, del livello di accesso alle informazioni riservate o della cronologia dei rischi. Questa struttura può includere membri del team dirigenziale dell'organizzazione, amministratori IT con privilegi di accesso alla rete e dati estesi o utenti con una cronologia passata di attività rischiose. In questi casi, un'ispezione più approfondita e un punteggio di rischio più aggressivo sono importanti per consentire la visualizzazione di avvisi per indagini e azioni rapide. Per identificare le attività rischiose per questi tipi di utenti, è possibile creare gruppi di utenti con priorità e creare criteri dai modelli di criteri seguenti:

- [Violazioni dei criteri di sicurezza per utenti con priorità (anteprima)](insider-risk-management-policies.md#security-policy-violations-by-priority-users-preview)
- [Perdita di dati per utenti con priorità (anteprima)](insider-risk-management-policies.md#data-leaks-by-priority-users-preview)

## <a name="actions-and-behaviors-by-disgruntled-users-preview"></a>Azioni e comportamenti da parte di utenti scontenti (anteprima)

Gli eventi di stress per l'impiego possono influire sul comportamento degli utenti in diversi modi correlati ai rischi insider. Questi stress possono essere una revisione delle prestazioni scarsa, un abbassamento di livello della posizione o il posizionamento dell'utente in un piano di revisione delle prestazioni. Sebbene la maggior parte degli utenti non risponda in modo dannoso a questi eventi, lo stress di queste azioni può comportare l'esecuzione di azioni che in genere potrebbero non prendere in considerazione in circostanze normali. Per facilitare l'identità di questi tipi di attività rischiose, i modelli di criteri di gestione dei rischi insider seguenti utilizzano il connettore risorse umane di Microsoft 365 e iniziano a segnare indicatori di rischio relativi a comportamenti che possono verificarsi in prossimità di eventi di stress da lavoro:

- [Perdite di dati da parte di utenti scontenti (anteprima)](insider-risk-management-policies.md#data-leaks-by-disgruntled-users-preview)
- [Violazioni dei criteri di sicurezza da parte di utenti scontenti (anteprima)](insider-risk-management-policies.md#security-policy-violations-by-disgruntled-users-preview)

## <a name="ready-to-get-started"></a>Pronti per iniziare?

- Per [informazioni su come preparare l'abilitazione](insider-risk-management-plan.md) dei criteri di gestione dei rischi insider nell'organizzazione, vedere Plan for insider risk management.
- Vedi [Introduzione alle impostazioni di gestione dei rischi insider](insider-risk-management-settings.md) per configurare le impostazioni globali per i criteri di rischio insider.
- Vedi [Introduzione alla gestione dei rischi insider](insider-risk-management-configure.md) per configurare i prerequisiti, creare criteri e iniziare a ricevere avvisi.
