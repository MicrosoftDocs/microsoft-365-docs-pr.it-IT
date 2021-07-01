---
title: Attività rapide per iniziare a usare il Centro conformità Microsoft 365
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- m365-security-compliance
- m365initiative-compliance
localization_priority: Normal
description: Informazioni sulle attività che consentono di iniziare rapidamente a utilizzare la conformità in Microsoft 365.
ms.openlocfilehash: 61a057c3666faae51a012dd9db2d4c63ded0f77a
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2021
ms.locfileid: "53227260"
---
# <a name="quick-tasks-for-getting-started-with-microsoft-365-compliance"></a>Attività rapide per iniziare a usare il Centro conformità Microsoft 365

Se non si ha familiarità con Microsoft 365 e si chiede da dove iniziare, questo articolo fornisce indicazioni sulle nozioni di base e assegna priorità alle attività di conformità importanti. Questo articolo ti aiuterà a iniziare rapidamente a gestire e monitorare i dati, a proteggere le informazioni e a ridurre al minimo i rischi insider.

Questo articolo è utile anche se si sta cercando di capire come gestire al meglio i rischi, proteggere i dati e rimanere conformi alle normative e agli standard con una nuova forza lavoro remota. I dipendenti collaborano e si connettono tra loro in modi nuovi e ciò significa che i processi e i controlli di conformità esistenti potrebbero dover adattarsi. Identificare e gestire questi nuovi rischi di conformità all'interno dell'organizzazione è fondamentale per proteggere i dati e ridurre al minimo minacce e rischi.

Dopo aver completato queste attività di conformità di base, è consigliabile espandere la copertura di conformità nell'organizzazione implementando ulteriori soluzioni Microsoft 365 conformità.

## <a name="task-1-configure-compliance-permissions"></a>Attività 1: Configurare le autorizzazioni di conformità

È importante gestire chi nell'organizzazione ha accesso al Centro conformità Microsoft 365 per visualizzare il contenuto ed eseguire attività di gestione. Microsoft 365 fornisce ruoli amministrativi specifici per la conformità e per l'utilizzo degli strumenti inclusi nella Centro conformità Microsoft 365.

Per iniziare, assegnare autorizzazioni di conformità alle persone dell'organizzazione in modo che possano eseguire queste attività e impedire a persone non autorizzate di accedere ad aree esterne alle proprie responsabilità. Prima di iniziare a configurare e implementare soluzioni  di conformità incluse  in Microsoft 365, è necessario assicurarsi di aver assegnato le persone appropriate all'amministratore dei dati di conformità e ai ruoli di amministratore di conformità. Sarà inoltre necessario assegnare gli utenti al ruolo Azure Active Directory lettore globale per visualizzare i dati in Compliance Manager.

Per istruzioni dettagliate sulla configurazione delle autorizzazioni e sull'assegnazione delle persone ai ruoli di amministratore, vedere Autorizzazioni nel [Centro sicurezza & conformità.](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)

## <a name="task-2-know-your-state-of-compliance"></a>Attività 2: conoscere lo stato di conformità

È difficile sapere dove andare se non si sa dove si trova. Soddisfare le esigenze di conformità include la comprensione del livello di rischio corrente e degli aggiornamenti che potrebbero essere necessari in questi tempi in continua evoluzione. Sia che l'organizzazione non sia nuova ai requisiti di conformità o abbia una profonda esperienza con gli standard e le normative che regolano il settore, l'unica cosa migliore da fare per migliorare la conformità è capire dove si trova l'organizzazione.

[Microsoft Compliance Manager consente](compliance-manager.md) di comprendere la posizione di conformità dell'organizzazione ed evidenziare le aree che potrebbero richiedere miglioramenti. Compliance Manager usa un dashboard centralizzato per calcolare un punteggio basato sul rischio, misurando i progressi nel completamento di azioni che consentono di ridurre i rischi relativi alla protezione dei dati e agli standard normativi. È inoltre possibile utilizzare Compliance Manager come strumento per tenere traccia di tutte le valutazioni dei rischi. Fornisce funzionalità del flusso di lavoro che consentono di completare in modo efficiente la valutazione dei rischi tramite uno strumento comune.

Per istruzioni dettagliate per iniziare a usare Compliance Manager, vedere [Introduzione a Compliance Manager.](compliance-manager-setup.md)

> [!IMPORTANT]
> La sicurezza e la conformità sono strettamente integrate per la maggior parte delle organizzazioni. È importante che l'organizzazione indirizzi le aree di sicurezza di base, protezione dalle minacce e gestione delle identità e degli accessi per fornire un approccio di difesa approfondito sia alla sicurezza che alla conformità.
>
> Controllare il [Microsoft 365 secure score](../security/defender/microsoft-secure-score.md) nel centro sicurezza Microsoft 365 e completare le attività descritte negli articoli seguenti:
>
> - [Roadmap per la sicurezza - Priorità principali per i primi 30 giorni, 90 giorni e oltre](../security/office-365-security/security-roadmap.md)
> - [Le 12 attività principali per i team di sicurezza per supportare il lavoro da casa](../security/top-security-tasks-for-remote-work.md)

## <a name="task-3-enable-auditing-for-your-organization"></a>Attività 3: Abilitare il controllo per l'organizzazione

Dopo aver determinato lo stato corrente dell'organizzazione e chi può gestire le funzioni di conformità, il passaggio successivo consiste nel verificare di disporre dei dati per eseguire indagini di conformità e generare report per le attività di rete e utente nell'organizzazione. L'abilitazione del controllo è anche un prerequisito importante per le soluzioni di conformità trattate più avanti in questo articolo.

Insights forniti dal log di controllo sono uno strumento utile per soddisfare i requisiti di conformità alle soluzioni che consentono di gestire e monitorare le aree di conformità che necessitano di miglioramenti. La registrazione di controllo deve essere abilitata prima che le attività siano registrate e che sia possibile eseguire ricerche nel log di controllo. Se abilitata, le attività degli utenti e degli amministratori dell'organizzazione vengono registrate nel log di controllo e conservate per 90 giorni e fino a un anno a seconda della licenza assegnata agli utenti.

Per istruzioni dettagliate su come attivare o disattivare il controllo, vedere Attivare o [disattivare la ricerca nel log di controllo.](turn-audit-log-search-on-or-off.md)

## <a name="task-4-create-policies-to-alert-you-about-potential-compliance-issues"></a>Attività 4: creare criteri per avvisare l'utente in caso di potenziali problemi di conformità

Microsoft fornisce diversi criteri di avviso incorporati che consentono di identificare l'abuso delle autorizzazioni di amministratore, l'attività di malware, potenziali minacce esterne e interne e i rischi di governance delle informazioni. Questi criteri sono attivati per impostazione predefinita, ma potrebbe essere necessario configurare avvisi personalizzati per gestire i requisiti di conformità specifici per l'organizzazione.

Usa i criteri di avviso e gli strumenti del dashboard degli avvisi per creare criteri di avviso personalizzati e visualizzare gli avvisi generati quando gli utenti eseguono attività che soddisfano le condizioni dei criteri. Alcuni esempi potrebbero essere l'uso di criteri di avviso per tenere traccia delle attività degli utenti e degli amministratori che influiscono sui requisiti di conformità, sulle autorizzazioni e sugli incidenti di perdita dei dati nell'organizzazione.

Per istruzioni dettagliate sulla creazione di criteri di avviso personalizzati, vedere Criteri di avviso nel Centro [sicurezza e conformità.](alert-policies.md)

## <a name="task-5-classify-and-protect-sensitive-data"></a>Attività 5: classificare e proteggere i dati sensibili

Per svolgere il proprio lavoro, i membri dell'organizzazione collaborano con altri utenti, sia interni che esterni all'organizzazione stessa. Questo significa che i contenuti non sono più protetti da un firewall, ma possono spostarsi tra dispositivi, applicazioni e servizi. E quando si spostano, è preferibile che lo facciano in modo sicuro e protetto, nel rispetto dei criteri aziendali e di conformità dell'organizzazione.

[Le etichette di riservatezza](sensitivity-labels.md) consentono di classificare e proteggere i dati dell'organizzazione, assicurando al contempo che la produttività degli utenti e la loro capacità di collaborare non siano ostacolate. Usare le etichette di riservatezza per applicare restrizioni di utilizzo e crittografia, applicare contrassegni visivi e proteggere le informazioni su piattaforme e dispositivi, in locale e nel cloud.

Per istruzioni dettagliate sulla configurazione e l'utilizzo delle etichette di riservatezza, vedere [Introduzione alle etichette di riservatezza.](get-started-with-sensitivity-labels.md) Per informazioni sulle licenze delle etichette di riservatezza, vedere [Microsoft 365 sulla licenza per la sicurezza & conformità](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection).

## <a name="task-6-configure-a-retention-policy"></a>Attività 6: Configurare un criterio di conservazione

I [criteri di conservazione](retention.md) consentono di decidere in modo proattivo se conservare il contenuto, eliminare il contenuto o entrambi, conservare ed eliminare il contenuto alla fine di un periodo di conservazione specificato. Queste azioni potrebbero essere necessarie per conformarsi alle normative del settore e ai criteri interni, oltre a ridurre i rischi in caso di controversia legale o violazione della sicurezza.

Quando il contenuto è soggetto a criteri di conservazione, gli utenti possono continuare a modificarlo e a lavorare con il contenuto come se nulla fosse cambiato. Il contenuto viene conservato sul posto, nella posizione originale. Tuttavia, se un utente modifica o elimina contenuto soggetto ai criteri di conservazione, una copia del contenuto originale viene salvata in un percorso sicuro in cui viene conservato mentre sono in vigore i criteri di conservazione per tale contenuto.

È possibile mettere rapidamente in atto un criterio di conservazione per più posizioni nell'ambiente di Microsoft 365, ad esempio posta elettronica Exchange, siti SharePoint, account OneDrive e gruppi Microsoft 365. Non esistono limiti al numero di cassette postali o siti che questo criterio può includere automaticamente. Tuttavia, se è necessario ottenere una maggiore selettività, è possibile farlo configurando un criterio di conservazione per posizioni specifiche e includendo o escludendo siti o utenti.

Per istruzioni dettagliate sulla configurazione di un criterio di conservazione, vedere [Create and configure retention policies](create-retention-policies.md). Se si configura per la prima volta la conservazione in Microsoft 365, vedere [Informazioni sui criteri e sulle etichette di conservazione](get-started-with-retention.md).

## <a name="task-7-configure-sensitive-information-and-offensive-language-policies"></a>Attività 7: Configurare informazioni riservate e criteri linguistici offensivi

Proteggere le informazioni riservate e rilevare e agire in caso di molestie sul luogo di lavoro è una parte importante della conformità ai criteri e agli standard interni. [La conformità delle](communication-compliance-feature-reference.md) comunicazioni in Microsoft 365 consente di ridurre al minimo questi rischi consentendo di rilevare, acquisire ed eseguire rapidamente azioni di correzione per la posta elettronica e le comunicazioni Microsoft Teams comunicazioni. Includono comunicazioni inappropriate contenenti volgarità, minacce e molestie e comunicazioni che condividono informazioni riservate all'interno e all'esterno dell'organizzazione.

Un linguaggio offensivo predefinito e un modello di criteri *anti-molestie* consente di analizzare le comunicazioni interne ed esterne per trovare le corrispondenze dei criteri in modo che possano essere esaminate dai revisori designati. I revisori possono analizzare la posta elettronica analizzata, Microsoft Teams, Yammer o comunicazioni di terze parti nell'organizzazione e intraprendere azioni di correzione appropriate per assicurarsi che siano conformi agli standard dell'organizzazione.

Il modello di  criteri informazioni riservate predefinito consente di creare rapidamente un criterio per analizzare la posta elettronica e le comunicazioni Microsoft Teams contenenti parole chiave o tipi di informazioni riservate definiti per assicurarsi che i dati importanti non siano condivisi con persone che non dovrebbero avere accesso. Queste attività potrebbero includere comunicazioni non autorizzate su progetti riservati o regole specifiche del settore per insider trading o altre attività di collusione.

Per istruzioni dettagliate sulla pianificazione e la configurazione della conformità delle comunicazioni, vedere [Plan for communication compliance](communication-compliance-plan.md) e Get started with communication [compliance.](communication-compliance-configure.md) Per informazioni sulle licenze di conformità delle comunicazioni, vedere [Microsoft 365 sulle licenze per la sicurezza & conformità](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#communication-compliance).

## <a name="task-8-see-whats-happening-with-your-sensitive-items"></a>Attività 8: vedere cosa succede agli elementi sensibili

Le etichette di riservatezza, i tipi di informazioni riservate, le etichette e i criteri di conservazione e i classificatori addestrabili possono essere utilizzati per classificare ed etichettare gli elementi sensibili in Exchange, SharePoint e OneDrive come illustrato nelle attività precedenti. L'ultimo passaggio del percorso di attività rapido consiste nel vedere quali elementi sono stati etichettati e quali azioni stanno facendo gli utenti su tali elementi sensibili. [Esplora contenuto ed](data-classification-content-explorer.md) [Esplora attività](data-classification-activity-explorer.md) offrono questa visibilità.

### <a name="content-explorer"></a>Esplora contenuto
 Esplora contenuto consente di visualizzare, nel formato nativo, tutti gli elementi classificati come tipo di informazioni riservate o appartenenti a una determinata classificazione da un classificatore trainabile, nonché tutti gli elementi a cui è applicata la riservatezza o l'etichetta di conservazione.

Per istruzioni dettagliate sull'uso di Esplora contenuto, vedere [Know your data - data classification overview](data-classification-overview.md)e Get started with content [explorer.](data-classification-content-explorer.md)

### <a name="activity-explorer"></a>Esplora attività
Esplora attività consente di monitorare le attività eseguite con gli elementi riservati classificati ed etichettati tra:
- SharePoint
- Exchange
- OneDrive

Sono disponibili per l'uso oltre 30 filtri diversi, alcuni dei quali sono:

- intervallo di date
- tipo di attività
- posizione
- utente
- etichetta di riservatezza
- etichetta di conservazione
- percorso file
- Criteri DLP

Per istruzioni dettagliate sull'uso di Esplora attività, vedi [Introduzione a Esplora attività.](data-classification-activity-explorer.md)

## <a name="next-steps"></a>Passaggi successivi

Dopo aver configurato le nozioni di base per la gestione della conformità per l'organizzazione, prendere in considerazione le soluzioni di conformità seguenti in Microsoft 365 per proteggere le informazioni riservate e rilevare e agire su ulteriori rischi insider.

### <a name="configure-retention-labels"></a>Configurare etichette di conservazione

Anche se i criteri di conservazione si applicano a livello di contenitore a posizioni quali siti di SharePoint e cassette postali di [Exchange,](retention.md#retention-labels) le etichette di conservazione consentono una destinazione più specifica per i criteri di conservazione ed eliminazione. Ad esempio, a livello di documento o messaggio di posta elettronica che gli utenti finali possono applicare manualmente oltre all'applicazione automatica da parte degli amministratori. È inoltre possibile applicare un'etichetta di conservazione a una raccolta documenti, una cartella o un set di documenti in SharePoint, in modo che tutti i documenti archiviati in tale posizione ereditino l'etichetta di conservazione predefinita.

Inoltre, le etichette di conservazione [supportano la gestione dei record](records-management.md) per contrassegnare il contenuto come record. In questo caso, l'etichetta pone ulteriori restrizioni sul contenuto che potrebbe essere necessario per aiutare l'organizzazione a rispettare i requisiti normativi.

Per istruzioni dettagliate su come creare e pubblicare etichette di conservazione, vedere le indicazioni seguenti:
- [Creare etichette di conservazione e applicarle nelle app](create-apply-retention-labels.md)
- [Applicare automaticamente un'etichetta di conservazione al contenuto](apply-retention-labels-automatically.md)

Per iniziare a utilizzare la gestione dei record, vedere [Introduzione alla gestione dei record.](get-started-with-records-management.md)

### <a name="identify-and-define-sensitive-information-types"></a>Identificare e definire i tipi di informazioni riservate

Definire i tipi di informazioni riservate in base al modello contenuto nelle informazioni nei dati dell'organizzazione. Utilizzare [i tipi di informazioni riservate](./sensitive-information-type-entity-definitions.md) incorporati per identificare e proteggere i numeri di carta di credito, i numeri di conto corrente bancario, i numeri di passaporto e altro ancora. Oppure creare tipi [di informazioni di riservatezza personalizzati](create-a-custom-sensitive-information-type.md) specifici per l'organizzazione.

Per istruzioni dettagliate sulla definizione di tipi di informazioni riservate personalizzati, vedere [Create a custom sensitive information type in the Security & Compliance Center.](./create-a-custom-sensitive-information-type.md)

### <a name="prevent-data-loss"></a>Prevenire la perdita di dati

[I criteri di prevenzione della](dlp-learn-about-dlp.md) perdita dei dati consentono di identificare, monitorare e proteggere automaticamente le informazioni riservate nell'Microsoft 365 organizzazione. Utilizzare i criteri DLP per identificare gli elementi sensibili tra servizi Microsoft, impedire la condivisione accidentale di elementi sensibili e aiutare gli utenti a rimanere conformi senza interrompere il flusso di lavoro.

Per istruzioni dettagliate sulla configurazione dei criteri DLP, [creare, testare e ottimizzare un criterio DLP.](create-test-tune-dlp-policy.md) Per informazioni sulle licenze per la gestione della perdita di dati, vedere [Microsoft 365 sulle licenze per la sicurezza & conformità.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#office-365-data-loss-prevention-for-exchange-online-sharepoint-online-and-onedrive-for-business)

### <a name="detect-and-act-on-insider-risks"></a>Rilevare e agire sui rischi insider

I dipendenti hanno sempre più accesso alla creazione, alla gestione e alla condivisione dei dati in un'ampia gamma di piattaforme e servizi. Nella maggior parte dei casi, le organizzazioni dispongono di risorse e strumenti limitati per identificare e ridurre i rischi a livello di organizzazione, oltre a soddisfare i requisiti di conformità e gli standard di privacy dei dipendenti. Questi rischi possono includere il furto di dati allontanando i dipendenti e le perdite di dati di informazioni esterne all'organizzazione per oversharing accidentale o intento dannoso.

[La gestione dei](insider-risk-management-policies.md) rischi insider in Microsoft 365 utilizza l'intera gamma di indicatori di servizio e di terze parti per aiutarti a identificare, eseguire la valutazione e agire rapidamente sulle attività degli utenti rischiose. Utilizzando i log di Microsoft 365 e Microsoft Graph, la gestione dei rischi insider consente di definire criteri specifici per identificare gli indicatori di rischio e di intervenire per mitigare questi rischi.

Per istruzioni dettagliate sulla pianificazione e la configurazione dei criteri di gestione dei rischi insider, vedere [Plan for insider risk management](insider-risk-management-plan.md) e Get started with insider risk [management.](insider-risk-management-configure.md) Per informazioni sulle licenze per la gestione dei rischi insider, vedere [Microsoft 365 sulle licenze per la sicurezza & conformità](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#insider-risk-management).