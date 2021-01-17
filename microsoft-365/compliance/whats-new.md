---
title: Novità sulla conformità Microsoft 365
f1.keywords:
- NOCSH
ms.author: brendonb
author: brendonb
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: L'aggiunta di nuove nuove soluzioni al centro conformità, l'aggiornamento delle funzionalità esistenti in base ai commenti o la documentazione aggiornata e rinnovata, Microsoft 365 consente di rimanere al di sopra del panorama di conformità in continua evoluzione. Scoprire cosa è stato fino a questo mese.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 8723171820bb1c089d34b81f5adb6663ecc9b8af
ms.sourcegitcommit: 27cb4591e08f62ba0a08d6dcf224bf2039034fe5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2021
ms.locfileid: "49883715"
---
# <a name="whats-new-in-microsoft-365-compliance"></a>Novità sulla conformità Microsoft 365

L'aggiunta di nuove soluzioni al [centro conformità di Microsoft 365](microsoft-365-compliance-center.md), l'aggiornamento delle funzionalità esistenti in base ai commenti e la documentazione aggiornata, Microsoft 365 consente di rimanere al di sopra del panorama di conformità sempre mutevole. Per informazioni sulle novità della conformità di Microsoft 365, vedere oggi stesso. 

> [!NOTE]
> Alcune funzionalità di conformità vengono distribuite a velocità diverse rispetto ai clienti. Se non si vede ancora una funzionalità, provare ad aggiungersi alla [versione mirata](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365).


> [!TIP]
> Interessato a cosa succede in altri centri di amministrazione? Consultare questi articoli:<br>[Novità dell'interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/office365/admin/whats-new-in-preview)<br>[Novità dell'interfaccia di amministrazione di SharePoint](https://docs.microsoft.com/sharepoint/what-s-new-in-admin-center)<br>[Novità di Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/whats-new)<br><br>
Per informazioni sulle funzionalità di Microsoft 365 che sono state avviate, sono in sviluppo, sono state annullate o sono state rilasciate in precedenza. [365](https://www.microsoft.com/en-us/microsoft-365/roadmap)

## <a name="november--december-2020"></a>Novembre & dicembre 2020
Solo un promemoria che spesso rilasciano nuove funzionalità aggiornate in uno stato di anteprima per sapere come vengono utilizzate in modo da poterli affinare e migliorare prima di rilasciarli alla disponibilità generale. Il feedback è critico durante l'anteprima (e oltre), quindi assicurati di farci sapere cosa pensi aprendo la scheda di feedback in basso a destra del centro conformità.

![feedback](../media/Feedback_card_MCC.JPG)

### <a name="spotlight-endpoint-data-loss-prevention-dlp-released"></a>Spotlight: rilasciata la prevenzione della perdita dei dati di endpoint (DLP)

[Endpoint DLP](endpoint-dlp-learn-about.md) estende le funzionalità di monitoraggio e protezione delle attività di DLP alle informazioni riservate nei dispositivi Windows 10. Dopo aver eseguito l' [onboarding](dlp-configure-endpoints.md) dei dispositivi nel centro conformità di Microsoft 365, è possibile configurare i criteri DLP per proteggere le informazioni riservate su tali dispositivi.

### <a name="advanced-ediscovery"></a>Advanced eDiscovery

Per semplificare la gestione del contenuto crittografato nel flusso di lavoro di eDiscovery, gli strumenti di Microsoft 365 eDiscovery ora incorporano la [decrittografia dei file crittografati](ediscovery-decryption.md) allegati ai messaggi di posta elettronica e inviati in Exchange. Inoltre, i documenti crittografati archiviati in SharePoint e OneDrive vengono decrittografati in Advanced eDiscovery.

### <a name="compliance-manager"></a>Compliance Manager

- [Supporto per abbonamenti governativi Microsoft 365](compliance-manager.md). Compliance Manager è ora disponibile per i clienti moderati e alti di US Government community (GCC).
- [Analizzatore di configurazione della conformità di Microsoft per Compliance Manager](compliance-manager-mcca.md). Nuovo strumento basato su PowerShell che consente di iniziare a utilizzare Compliance Manager analizzando le configurazioni correnti dell'organizzazione e convalidando le procedure consigliate di Microsoft 365.
- [Nuovi modelli](compliance-manager-templates-list.md). Sono stati aggiunti 56 nuovi modelli, portando i modelli Total Compliance Manager a oltre 230.

### <a name="data-connectors"></a>Connettori dati

[Cinque nuovi connettori di Globanet in anteprima](archiving-third-party-data.md#third-party-data-connectors). I nuovi connettori includono Reuters Dealing, Reuters FX, CellTrust, XIP, Generic MS SQL database Data.

### <a name="retention-labels-disposition-review"></a>Etichette di conservazione (revisione della disposizione)

Per visualizzare gli elementi durante una revisione della disposizione, gli utenti devono essere membri dei gruppi di ruoli Visualizzatore contenuto [Esplora contenuto e elenco Esplora contenuto](disposition.md#permissions-for-disposition). Sebbene sia necessario esaminare gli elementi, questi gruppi di ruoli non sono necessari per completare la revisione della disposizione.

### <a name="sensitivity-labels"></a>Etichette di riservatezza

- [(Anteprima) impostazioni di condivisione esterna per i siti di SharePoint](sensitivity-labels-teams-groups-sites.md#how-to-configure-groups-and-site-settings). Quando si crea un'etichetta che verrà utilizzata per i gruppi e i siti, viene visualizzata un'opzione per controllare la condivisione esterna per i siti di SharePoint a cui è applicata l'etichetta. È possibile specificare che la condivisione è consentita per tutti gli utenti, i clienti nuovi e quelli esistenti, solo gli ospiti esistenti o solo quelli dell'organizzazione. Quando viene applicata l'etichetta, le impostazioni dell'etichetta sostituiscono tutte le impostazioni [di condivisione esterna configurate nell'interfaccia di amministrazione di SharePoint](https://docs.microsoft.com/sharepoint/change-external-sharing-site).
- [Rimuovere l'etichetta e la crittografia da un documento etichettato](sensitivity-labels-sharepoint-onedrive-files.md#remove-encryption-for-a-labeled-document). Per rimuovere sia un'etichetta che la crittografia applicata da un documento etichettato in SharePoint, gli amministratori globali e gli amministratori di SharePoint possono eseguire il nuovo `Unlock-SPOSensitivityLabelEncryptedFile` cmdlet. Questo cmdlet viene eseguito anche se l'amministratore non dispone di autorizzazioni di accesso per il sito o il file oppure se il servizio Azure Rights Management non è disponibile.

## <a name="october-2020"></a>Ottobre 2020

### <a name="advanced-ediscovery"></a>Advanced eDiscovery

[Supporto per la lingua CJK](ediscovery-cjk-support.md). Advanced eDiscovery ora supporta le lingue del set di caratteri a doppio byte, conosciute collettivamente come lingue CJK (include cinese semplificato, cinese tradizionale, giapponese e coreano). Questi possono essere utilizzati in diversi scenari di set di revisione avanzati.

### <a name="sensitivity-labels"></a>Etichette di riservatezza

- [Ambito delle etichette](sensitivity-labels.md#label-scopes). Quando si crea un'etichetta di riservatezza, viene visualizzata una nuova opzione per definire l'ambito dell'etichetta. Questa opzione consente di configurare le etichette solo per file e messaggi di posta elettronica, contenitori (come i siti di SharePoint e i team) o entrambi.
- [Contrassegno contenuto dinamico](sensitivity-labels-office-apps.md#dynamic-markings-with-variables). Quando si configura la marcatura del contenuto per un'etichetta di riservatezza, è ora possibile utilizzare le variabili dinamiche come `${Item.Label}` e `${Item.Location}` nella stringa di testo per l'intestazione, il piè di pagina o la filigrana.

## <a name="september-2020"></a>Settembre 2020

### <a name="spotlight-compliance-manager"></a>Spotlight: Compliance Manager

Annunciato in Ignite quest'anno, il Punteggio di conformità è stato rebranded As [Compliance Manager](compliance-manager.md). Questa versione completa la transizione dalla Home page precedente di Compliance Manager nel Service Trust Portal e introduce una soluzione di gestione della conformità end-to-end nel centro conformità di Microsoft 365.

Guarda il video seguente per informazioni su come Compliance Manager può aiutare a semplificare la gestione della conformità dell'organizzazione.
<br>
<br>
>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4FGYZ]

### <a name="advanced-audit"></a>Audit avanzato

- La nuova conservazione di 10 anni dei registri di controllo consente di supportare indagini lunghe e di rispondere a obblighi normativi, legali e interni.
- [Tre nuovi nuovi eventi cruciali](advanced-audit.md#access-to-crucial-events-for-investigations). I nuovi eventi riportati di seguito possono essere utili per individuare possibili violazioni e determinare l'ambito di compromesso: Send, SearchQueryInitiatedExchange e SearchQueryInitiatedSharePoint.

### <a name="communication-compliance"></a>Conformità delle comunicazioni

- [Gruppi di ruoli aggiornati](communication-compliance-configure.md#step-1-required-enable-permissions-for-communication-compliance). I gruppi di ruoli Compliance Communication ora corrispondono alla struttura del gruppo di ruoli disponibile per la soluzione di gestione dei rischi Insider.
- [Dashboard report](communication-compliance-feature-reference.md#reports-preview). La posizione centrale per la visualizzazione di tutti i report di conformità della comunicazione. I widget dei report offrono una rapida visualizzazione delle informazioni più comuni necessarie per una valutazione complessiva dello stato delle attività di conformità alla comunicazione.
- [Flussi automatici di alimentazione automatizzati](communication-compliance-feature-reference.md#power-automate-flows). Impostare i flussi per automatizzare le attività per gli avvisi e gli utenti, informare i responsabili quando gli utenti attivano gli avvisi e altro ancora.
- [Azione di correzione ' migliorare la classificazione '](communication-compliance-investigate-remediate.md#step-3-decide-on-a-remediation-action). Gli avvisi contenenti elementi che soddisfano i classificatori addestrati potrebbero trarre vantaggio da commenti e suggerimenti utili per ridurre al minimo i falsi positivi nell'organizzazione. L'opzione **migliora classificazione** consente di fornire commenti e suggerimenti se gli elementi rilevati corrispondono al classificatore configurato nei criteri di conformità della comunicazione correlati. È anche possibile suggerire ad altri classificatori di associarsi all'elemento per migliorare l'accuratezza della corrispondenza per gli avvisi futuri.

### <a name="data-connectors"></a>Connettori dati

- [Nuovi connettori di dati di terze parti](archiving-third-party-data.md#third-party-data-connectors). 25 nuovi connettori di dati, tra cui 14 connettori di Globanet e 8 da TeleMessage.
- [Connettore badging fisico](import-physical-badging-data.md). Importare dati fisici di badging, ad esempio gli eventi di accesso fisico non elaborati del dipendente o gli allarmi di accesso fisico generati dal sistema badging dell'organizzazione. Tra gli esempi sono inclusi le voci di edifici, sale server o Data Center. I dati fisici di badging possono essere utilizzati dalla soluzione di gestione dei rischi Insider per proteggere l'organizzazione da attività dannose o furti di dati all'interno dell'organizzazione.

### <a name="insider-risk-management"></a>Gestione dei rischi Insider

- [Integrazione di Microsoft teams](insider-risk-management-settings.md#microsoft-teams-preview). Quando l'integrazione di teams è attivata nelle impostazioni di rischio Insider, è possibile coordinare e collaborare con altre parti interessate in teams in attività come la condivisione e l'archiviazione sicure dei dati relativi a singoli casi, la verifica e la revisione delle attività di risposta da analisti e ricercatori e altro ancora.
- [Flussi automatici di alimentazione automatizzati](insider-risk-management-settings.md#power-automate-flows-preview). Impostare i flussi per automatizzare le attività importanti per i casi e gli utenti, ad esempio il recupero di informazioni sull'utente, l'avviso e i casi da condividere con le parti interessate e altre app, automatizzando azioni come la pubblicazione di note di caso e altro ancora.
- [Esplora attività](insider-risk-management-alerts.md#activity-explorer-preview). Disponibile quando si esaminano gli avvisi, attività Esplora risorse fornisce ai ricercatori e agli analisti uno strumento analitico completo per eseguire il drill-down in ogni avviso. Esaminare rapidamente una cronologia delle attività a rischio individuate e identificare e filtrare tutte le attività di rischio associate agli avvisi.

### <a name="retention-policies-and-retention-labels"></a>Criteri di conservazione ed etichette di conservazione.

- [Supporto per Yammer](retention-policies-yammer.md). È ora possibile utilizzare i criteri di conservazione per conservare ed eliminare i messaggi della community e i messaggi privati di Yammer.
- [Applicare etichette alle registrazioni di riunioni di teams](apply-retention-labels-automatically.md#microsoft-teams-meeting-recordings). Quando si crea un criterio di etichettatura automatica, utilizzare l'editor di query con parole chiave per identificare le registrazioni delle riunioni dei team archiviate negli account di OneDrive degli utenti o in SharePoint.

### <a name="records-management"></a>Gestione dei record

[Supporto per i record normativi](declare-records.md#how-to-display-the-option-to-mark-content-as-a-regulatory-record). La classificazione di un'etichetta come record normativo aumenta le restrizioni applicate al contenuto a cui è applicata l'etichetta e limita le azioni di gestione disponibili per l'etichetta stessa. Ad esempio, dopo che è stato applicato al contenuto, nessuno, neanche un amministratore globale, può rimuovere l'etichetta. Per [ulteriori](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked) informazioni, vedere quali azioni sono consentite e bloccate per i record normativi.

### <a name="sensitivity-labels"></a>Etichette di riservatezza

[Supporto per i clienti del governo degli Stati Uniti](https://docs.microsoft.com/enterprise-mobility-security/solutions/ems-aip-premium-govt-service-description). Le etichette di riservatezza sono ora supportate per i clienti GCC, GCC High e DoD, solo per il client e lo scanner di Azure Information Protection Unified labeling.

### <a name="trainable-classifiers"></a>Classificatori sottoponibili a training

Nuove funzionalità di riqualificazione e feedback consentono di migliorare l'accuratezza e ridurre al minimo le corrispondenze false positive per tutti i classificatori personalizzati e alcuni classificatori prequalificati. Questo flusso consente di fornire commenti e suggerimenti su come gli elementi corrispondono a determinati classificatori, suggerire ad altri classificatori di associare gli elementi e riqualificare i classificatori per affinare e migliorare l'accuratezza delle corrispondenze.

Questa nuova funzionalità è inclusa nelle caratteristiche seguenti:

> [!NOTE]
> Per tutte le funzionalità, se si forniscono almeno 30 risposte di feedback, verrà creata una versione riqualificata del classificatore che è possibile esaminare. Se si verifica un miglioramento, è possibile ripubblicare il classificatore.

- [Classificatori addestrabili](classifier-learn-about.md#retraining-classifiers). Per migliorare l'accuratezza dei classificatori pubblicati, è possibile fornire commenti e suggerimenti sull'eventuale corrispondenza tra gli elementi rilevati e il classificatore.
- [Conformità alla comunicazione](classifier-how-to-retrain-comms-compliance.md). La nuova azione **miglioramento classificazione** consente di fornire commenti e suggerimenti se un elemento di un avviso di conformità della comunicazione corrisponde al classificatore configurato nel criterio di conformità della comunicazione.
- [Esplora contenuto](classifier-how-to-retrain-content-explorer.md). Se si configura un criterio di etichettatura automatica di conservazione per applicare automaticamente le etichette ai messaggi di posta elettronica che corrispondono ai classificatori addestrabili, è possibile utilizzare Esplora contenuto per esaminare gli elementi contrassegnati e fornire commenti e suggerimenti se gli elementi corrispondono al classificatore.

## <a name="august-2020"></a>Agosto 2020

### <a name="spotlight-insider-risk-and-communication-compliance-updates"></a>Spotlight: aggiornamenti per la conformità alle comunicazioni e ai rischi Insider

Numerose funzionalità nuove e migliorate hanno colpito l'anteprima pubblica di questo mese:

**Gestione dei rischi Insider**

- Consultare i sei nuovi [modelli di criteri](insider-risk-management-policies.md#policy-templates):
    - Perdite di dati da parte di utenti prioritari
    - Perdite di dati da parte di utenti scontenti
    - Violazioni dei criteri di sicurezza generali
    - Violazioni dei criteri di sicurezza da parte degli utenti
    - Violazioni dei criteri di sicurezza per gli utenti con priorità
    - Violazioni dei criteri di sicurezza da parte di utenti scontenti

- L'integrazione con [Microsoft Defender per endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) consente di importare e filtrare Microsoft Defender per gli avvisi endpoint per le attività rilevate dai criteri creati dai nuovi modelli di criteri di violazione della sicurezza. È inoltre disponibile un'impostazione relativa ai [rischi Insider](insider-risk-management-settings.md#microsoft-defender-for-endpoint-preview) in cui è possibile scegliere di importare avvisi di sicurezza per la gestione dei rischi insider in base allo stato di valutazione degli avvisi di Microsoft Defender per endpoint.

    > [!NOTE]
    > Per usufruire di Microsoft Defender per l'integrazione di endpoint (inclusi i nuovi modelli di violazione dei criteri di sicurezza), è necessario che Microsoft Defender per endpoint sia configurato nell'organizzazione. È inoltre necessario abilitare Microsoft Defender per endpoint per l'integrazione di gestione dei rischi Insider [configurando funzionalità avanzate in Microsoft Defender for endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center).
 
- Personalizzare le soglie degli indicatori quando si [Crea un criterio](insider-risk-management-policies.md#create-a-new-policy).
- Impostare i [gruppi](insider-risk-management-settings.md#priority-user-groups-preview) di utenti prioritari per definire gli utenti dell'organizzazione la cui attività richiede un controllo più approfondito in base a fattori quali la posizione, il livello di accesso alle informazioni riservate o la cronologia dei rischi.
- Utilizzare le API di attività di gestione di Office 365 per [esportare i dettagli dell'avviso sui rischi Insider](insider-risk-management-settings.md#export-alerts-preview) ad altre applicazioni che possono essere utilizzate dall'organizzazione per gestire o aggregare dati di rischio
- [Le nuove impostazioni di dominio](insider-risk-management-settings.md#domains-preview) consentono di definire e controllare i livelli di rischio per attività in domini specifici.

**Conformità delle comunicazioni**

- Quando si [esaminano i messaggi in un avviso](communication-compliance-investigate-remediate.md#step-3-decide-on-a-remediation-action), è ora possibile rimuovere i messaggi inadeguati nei canali Microsoft teams, 1:1 e Group Chat. I messaggi e il contenuto rimossi vengono sostituiti con un suggerimento per i criteri che spiega che è stato rimosso a causa di contenuti sensibili.
- Nuovi [ruoli di comunicazione](communication-compliance-configure.md#step-1-required-enable-permissions-for-communication-compliance) (saranno inclusi anche nei nuovi gruppi di ruoli di conformità di comunicazione che rilasciano a settembre).
- Nuova esperienza delle impostazioni di conformità di comunicazione che include le impostazioni per la [privacy](communication-compliance-feature-reference.md#privacy) e i [modelli di avviso](communication-compliance-feature-reference.md#notice-templates).
- Nuovi [classificatori](communication-compliance-feature-reference.md#classifiers) che consentono di rilevare immagini adulte, audace e cruente.
- La nuova notifica ' pattern detected ' che viene visualizzata quando si [esaminano i messaggi in un avviso](communication-compliance-investigate-remediate.md#step-2-examine-the-message-details) consente di conoscere le istanze ricorrenti dello stesso comportamento da parte di un utente.

### <a name="sensitivity-labels"></a>Etichette di riservatezza

- Per i tenant degli enti pubblici degli Stati Uniti (GCC, GCC-HC e DoD), le etichette di riservatezza sono attualmente supportate solo per lo scanner e il client di etichettatura unificata di Azure Information Protection. Per altre informazioni, vedere [Descrizione del servizio Azure Information Protection Premium per gli enti pubblici](https://docs.microsoft.com/enterprise-mobility-security/solutions/ems-aip-premium-govt-service-description).
- Per creare e configurare tutte le impostazioni visualizzate nell'interfaccia di amministrazione dell'etichettatura, è ora possibile [utilizzare PowerShell per la sicurezza & Compliance Center](create-sensitivity-labels.md#use-powershell-for-sensitivity-labels-and-their-policies) . Questo significa che, oltre a utilizzare PowerShell per le impostazioni che non sono disponibili nell'interfaccia di amministrazione dell'etichettatura, è ora possibile creare completamente script per la creazione e la manutenzione delle etichette di riservatezza e dei criteri di etichetta di riservatezza.

### <a name="records-management-content-overhaul"></a>Gestione dei record: Revisione del contenuto

Nuovi documenti che coprono i passaggi di distribuzione, contrassegnando il contenuto come record e le versioni dei record:

- [Introduzione alla gestione dei record](get-started-with-records-management.md)
- [Usare le etichette di conservazione per dichiarare i record](declare-records.md)
- [Usare il controllo delle versioni per aggiornare i record archiviati in SharePoint o OneDrive](record-versioning.md)

### <a name="retention-labels--policies"></a>Criteri delle etichette di conservazione &

L'attività amministrativa relativa alla conservazione è ora registrata e disponibile per la revisione nel log di controllo. Per la lista completa, vedere [Attività inerenti i criteri e le etichette di conservazione](search-the-audit-log-in-security-and-compliance.md#retention-policy-and-retention-label-activities).

### <a name="advanced-ediscovery"></a>Advanced eDiscovery

- Quando si [aggiunge una raccolta a un set di revisione](add-data-to-review-set.md#define-options-to-scope-your-collection-for-review), è ora possibile includere gli allegati moderni (denominati anche "allegati cloud") e le versioni di documenti di SharePoint.
- Nuova [esperienza di esportazione del download diretto](export-documents-from-review-set.md), eliminando la necessità di utilizzare Esplora archivi di Azure per scaricare il contenuto del caso.


## <a name="july-2020"></a>Luglio 2020

### <a name="spotlight-on-help-docs"></a>Spotlight sui documenti della Guida

Per facilitare la comprensione delle soluzioni di conformità che consentono di proteggere e gestire i dati sensibili dell'organizzazione, sono state create due nuove pagine di destinazione con una panoramica del modo in cui le soluzioni interagiscono per raggiungere tali obiettivi, inclusi i collegamenti ai documenti correlati, in modo da poterli immergere ulteriormente.

[Microsoft Information Protection in Microsoft 365.](information-protection.md)<br>
[Governance delle informazioni Microsoft in Microsoft 365](manage-Information-governance.md)

### <a name="advanced-ediscovery-add-non-custodial-data-sources-to-your-cases"></a>Advanced eDiscovery: aggiungere origini dati non detentive ai casi

Aggiungere dati a un caso senza che sia necessario associarlo a un custode (noto come [origini dati non detentive](non-custodial-data-sources.md)). Se è necessario inserire un blocco di dati non detentivi, è possibile farlo utilizzando la nuova funzionalità di indicizzazione avanzata.

### <a name="data-connectors-hr-connector-enhancements"></a>Connettori dati: miglioramenti del connettore HR

(In anteprima) Una nuova versione del [connettore HR](import-hr-data.md) consente di importare i dati relativi alle modifiche a livello di processo, alle revisioni delle prestazioni e ai piani di miglioramento delle prestazioni. Questi dati possono quindi essere utilizzati in diverse [politiche di rischio Insider](insider-risk-management-policies.md) per rilevare attività correlate.

### <a name="retention-labels-new-support-for-email"></a>Etichette di conservazione: nuovo supporto per la posta elettronica

È ora possibile creare un' [etichetta di conservazione](retention.md#retention-labels) per iniziare a mantenere la posta elettronica in base al momento in cui i messaggi sono stati etichettati. Questo non si applica agli elementi del calendario, che verranno mantenuti in base alla data di invio dell'elemento.

### <a name="sensitivity-labels-new-feature-and-an-improvement"></a>Etichette di riservatezza: nuova funzionalità e miglioramento

- (In anteprima) Quando si configurano le impostazioni di crittografia per un'etichetta, cercare la nuova opzione per usare la [crittografia a chiave doppia](encryption-sensitivity-labels.md#double-key-encryption) per proteggere ulteriormente i file etichettati e i messaggi di posta elettronica.
- Quando si creano o si eliminano etichette di riservatezza o si creano, modificano o eliminano i criteri di etichetta, le modifiche vengono sincronizzate entro 1 ora per tutti gli utenti, le app e i servizi.

## <a name="june-2020"></a>Giugno 2020

### <a name="spotlight-new-data-connectors-hit-preview"></a>Spotlight: i nuovi connettori di dati hanno colpito l'anteprima

Basandosi sulla promessa che consente di importare i dati da origini di terze parti in Microsoft 365, è lieta di annunciare la versione di anteprima di altri due connettori di dati:

- [Messaggio Bloomberg](archive-bloomberg-message-data.md). Importare e archiviare i dati della posta elettronica dei servizi finanziari dallo strumento di collaborazione del messaggio Bloomberg. Dopo che i dati sono stati archiviati nelle cassette postali, è possibile accedere ai dati e utilizzarli in funzionalità di conformità, ad esempio conservazione per controversia legale, ricerca contenuto, archiviazione sul posto, controllo, conformità alla comunicazione e criteri di ritenzione.
- [Chat su ghiaccio](archive-icechat-data.md). Importare e archiviare i dati di chat dei servizi finanziari dallo strumento di collaborazione di ICE chat. Dopo che i dati sono stati archiviati nelle cassette postali, è possibile accedere ai dati e utilizzarli in funzionalità di conformità, ad esempio conservazione per controversia legale, eDiscovery, archiviazione, controllo, conformità alla comunicazione e criteri per il mantenimento.

### <a name="compliance-score--compliance-manager-the-hits-keep-coming"></a>Punteggio di conformità & Compliance Manager: i risultati continuano a venire

Gli aggiornamenti di giugno includono una nuova visualizzazione drill-down di valutazione nel [Punteggio di conformità](compliance-score.md). Monitorare lo stato di avanzamento del controllo, aggiungere, eliminare valutazioni direttamente dal punteggio di conformità e altro ancora.

Vuoi rimanere al di sopra degli aggiornamenti per la conformità score e Compliance Manager? Contrassegnare le [Note di rilascio del Punteggio di conformità](compliance-score-release-notes.md) e controllare spesso.

## <a name="may-2020"></a>Maggio 2020

### <a name="spotlight-data-classification-is-officially-released"></a>Spotlight: la classificazione dei dati è stata rilasciata ufficialmente

Classificazione dei dati, aka '[know your data](data-classification-overview.md)', features (Analytics, Content Explorer e Esplora attività) sono state graduate dalla fase di anteprima e sono disponibili per tutte le organizzazioni. Potenti approfondimenti e strumenti consentono di individuare e valutare la modalità di utilizzo di informazioni e etichette sensibili (conservazione e sensibilità) nei contenuti all'interno dell'organizzazione. Esaminare il contenuto che contiene informazioni riservate o se sono state applicate etichette, esplorare l'attività delle etichette tra le posizioni di Microsoft 365, creare tipi di informazioni riservate personalizzate e altro ancora.

Fare un video tour...

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vx8x]

### <a name="trainable-classifiers-a-fix-and-a-feature"></a>Classificatori addestrabili: una correzione e una funzionalità

Potrebbe portare maggiori miglioramenti ai classificatori addestrabili:

- Una correzione basata sui commenti e suggerimenti: quando si esegue il seeding e si addestra un classificatore personalizzato, non è più necessario immettere manualmente gli URL del sito di SharePoint e i percorsi delle cartelle. È ora possibile scegliere da un elenco di siti e cartelle prepopolare.
- Nuova caratteristica: quando si crea un'etichetta di riservatezza e si configurano le impostazioni di etichettatura automatica per le app di Office, è ora possibile applicare automaticamente (o consigliare agli utenti di applicare) l'etichetta al contenuto che corrisponde ai classificatori addestrabili. [Altre informazioni](apply-sensitivity-label-automatically.md#configuring-trainable-classifiers-for-a-label)

### <a name="communication-compliance-yammer-support-is-here"></a>Conformità alla comunicazione: il supporto di Yammer è qui

I messaggi privati e le conversazioni della community pubblica in Yammer sono supportati nei criteri di conformità della comunicazione. Yammer è un canale facoltativo e deve essere in [modalità nativa](https://docs.microsoft.com/yammer/configure-your-yammer-network/overview-native-mode) per supportare l'analisi dei messaggi e degli allegati.

### <a name="data-loss-prevention-new-sharing-restriction"></a>Prevenzione della perdita di dati: nuova restrizione di condivisione

Quando si configura un criterio DLP per proteggere il contenuto in SharePoint o OneDrive, è ora possibile configurare l'azione "limitare l'accesso al contenuto" per bloccare le persone a cui è stato concesso l'accesso al contenuto tramite l'opzione "[chiunque abbia il collegamento](https://support.microsoft.com/office/share-files-outside-your-organization-with-anyone-links-53e91027-fb8e-4a6e-a3e4-5df4be32e38a)".

### <a name="insider-risk-management-tailor-your-alert-volume"></a>Gestione dei rischi Insider: adattare il volume degli avvisi

Le attività degli utenti rilevate dai criteri di rischio Insider sono assegnate a un punteggio di rischio specifico, che a sua data determina la gravità degli avvisi (basso, medio, alto). Per impostazione predefinita, Microsoft 365 genera una determinata quantità di avvisi di gravità bassa, media e alta, ma con la nuova [impostazione volume di avviso](insider-risk-management-settings.md#alert-volume)è possibile aumentare o diminuire il volume in base alle proprie esigenze.

### <a name="pst-import-new-region-supported"></a>Importazione PST: supporto per nuove aree geografiche

Il caricamento di rete è ora disponibile in Emirati Arabi Uniti.

### <a name="sensitivity-labels-new-privacy-option"></a>Etichette di riservatezza: nuova opzione privacy

Quando si configurano le [impostazioni del sito e del gruppo](sensitivity-labels-teams-groups-sites.md#how-to-configure-groups-and-site-settings) per un'etichetta, è ora possibile impostare l'opzione privacy su **None-Consenti agli utenti di scegliere gli utenti autorizzati a accedere al sito**. Questa opzione è utile quando si desidera proteggere il contenuto del contenitore utilizzando un'etichetta di riservatezza, ma è comunque possibile che gli utenti configurino l'impostazione di privacy.

## <a name="april-2020"></a>Aprile 2020

### <a name="records-management-overhauland-a-new-addition"></a>Gestione dei record: Revision... e una nuova aggiunta

April include un paio di aggiornamenti chiave per la soluzione di gestione dei record:

- La sezione ' Records Management ' è ora completamente disponibile nel centro conformità. Utilizzare le interfacce utente e le funzionalità aggiornate per il piano di file, le etichette di conservazione e i criteri di etichetta, gli eventi e la disposizione.
- A proposito di disposizione, è stato anche implementato il [certificato di disponibilità](disposition.md#disposition-of-records) dei record in SharePoint e OneDrive. È ora possibile visualizzare un elenco di elementi in quelle posizioni che sono state eliminate automaticamente o dopo una revisione della disposizione.

### <a name="sensitivity-labels-preview-auto-labeling-policies"></a>Etichette di riservatezza: anteprima di criteri di etichettatura automatica

Con i criteri di etichettatura automatica, è ora possibile applicare automaticamente le etichette di riservatezza ai documenti di SharePoint e OneDrive che sono già stati salvati (aka ' data at rest) e messaggi di posta elettronica che sono già stati inviati o ricevuti (aka ' e-mail in transito '). Poiché questa etichettatura viene applicata dai servizi anziché dalle app, non è necessario preoccuparsi di cosa hanno gli utenti delle app e di quale versione.

Questa funzionalità consente di estendere l'etichettatura sul retro del client già inclusa nelle impostazioni di "etichettatura automatica per le app di Office" quando si crea un'etichetta di riservatezza. Per velocizzare le differenze e i vantaggi delle opzioni di etichettatura automatica, vedere l' [articolo aggiornato](apply-sensitivity-label-automatically.md).

## <a name="march-2020"></a>Marzo 2020

### <a name="introducing-advanced-audit"></a>Introduzione al controllo avanzato

[Advanced audit in Microsoft 365](advanced-audit.md) introduce nuove funzionalità di controllo che consentono all'organizzazione di svolgere indagini forensi e di conformità. Gli Highlight includono la conservazione a lungo termine dei log di controllo, i criteri di conservazione del registro di controllo personalizzato, la nuova azione di controllo delle cassette postali di *MailItemsAccessed* e l'introduzione di un nuovo limite di limitazione a livello di tenant, che fornisce all'organizzazione una quota di larghezza di banda completamente allocata per accedere ai dati di controllo.

### <a name="compliance-score--compliance-manager-preview-the-latest-enhancements"></a>Score Compliance & Compliance Manager: anteprima dei miglioramenti più recenti

Gli aggiornamenti principali per questa versione di anteprima includono:

- Processo semplificato per la creazione e la modifica dei modelli
- Avviso per il controllo delle versioni e per i modelli e le azioni
- Sincronizzazione di azioni comuni tra gruppi
- Supporto per le lingue ora esteso a cinese (semplificato), cinese (tradizionale), francese, tedesco, italiano, giapponese, coreano, portoghese (Brasile), russo e spagnolo

Per ulteriori informazioni, vedere [Compliance Score](compliance-score.md) and [Compliance Manager](compliance-manager-overview.md)

### <a name="sensitivity-labels-support-for-labeling-office-files-in-sharepoint-and-onedrive-preview"></a>Etichette di riservatezza: supporto per l'etichettatura dei file di Office in SharePoint e OneDrive (anteprima)

L'abilitazione dell'anteprima consente agli utenti di applicare etichette di riservatezza in Office sul Web. Saranno in grado di visualizzare il pulsante **sensitivity** sulla barra multifunzione e il nome dell'etichetta applicata sulla barra di stato. Inoltre, se utilizzano le app desktop per etichettare e quindi salvare i file in SharePoint o OneDrive, Microsoft 365 sarà ora in grado di elaborare il contenuto di questi file se l'etichetta dispone di impostazioni di crittografia applicate. La CoAuthoring, la eDiscovery, la prevenzione della perdita di dati, la ricerca e altre funzionalità di collaborazione saranno supportate anche in queste circostanze.

[Informazioni su come abilitare l'anteprima](sensitivity-labels-sharepoint-onedrive-files.md)

## <a name="february-2020"></a>Febbraio 2020

### <a name="insider-risk-management-is-officially-released"></a>Gestione dei rischi Insider rilasciata ufficialmente

Rullo di tamburi, per favore...<br>La gestione dei rischi Insider è ora disponibile per le organizzazioni con gli abbonamenti seguenti:

- [Microsoft 365 E5](https://go.microsoft.com/fwlink/?linkid=2120431) (a pagamento o a prova)
- Sottoscrizione Microsoft 365 Enterprise E3 con il [componente aggiuntivo Microsoft E5 Compliance](https://go.microsoft.com/fwlink/?linkid=2120432)

Heads up che sono stati apportati alcuni miglioramenti dopo la versione di anteprima, inclusi i [nuovi gruppi di ruoli](insider-risk-management-configure.md#step-1-enable-permissions-for-insider-risk-management) e [le impostazioni a livello di soluzione](insider-risk-management-configure.md#step-4-configure-insider-risk-settings).

Come sempre, si prega di lasciare commenti e suggerimenti quando si utilizza la soluzione in modo da poter continuare a migliorare.

### <a name="records-management"></a>Gestione dei record

Questa nuova soluzione apporta tutte le funzionalità di gestione dei record in un unico ombrello. Tra i punti salienti sono inclusi l'introduzione del controllo delle versioni dei record per SharePoint e OneDrive e la prova dello smaltimento dei record.

![Pagina Gestione record in Microsoft 365 Compliance Center](../media/mcc-records-management-page.png)

[Ulteriori informazioni sulla gestione dei record](records-management.md)

### <a name="solution-spotlight-data-connectors-for-facebook-and-twitter"></a>Spotlight della soluzione: connettori di dati per Facebook e Twitter

Connettori di dati [rilasciati il mese scorso](#just-launched) e stiamo cercando il vostro aiuto per testare i connettori seguenti.

- [Pagine business di Facebook](archive-facebook-data-with-sample-connector.md). Importa e archivia i dati dalle pagine di business di Facebook a Microsoft 365. Vantaggi per le soluzioni di conformità, ad esempio la gestione dei record e eDiscovery.
- [Twitter](archive-twitter-data-with-sample-connector.md). Importa e archivia i dati da Twitter a Microsoft 365. Vantaggi per le soluzioni di conformità, ad esempio la gestione dei record e eDiscovery.

Man mano che si configurano e convalidano questi connettori, si prega di lasciare commenti e suggerimenti su cosa è successo, cosa non è stato e cosa è possibile fare per migliorare l'esperienza.

## <a name="january-2020"></a>Gennaio 2020

L'attesa è terminata. Siamo lieti di annunciare che Microsoft 365 Compliance Center è disponibile per tutti i clienti con i piani di Microsoft 365, Office 365, Enterprise Mobility + Security (EMS) e Windows 10 Enterprise. Tutti i dati o i criteri che sono stati gestiti nel centro sicurezza & conformità sono disponibili nel centro conformità, quindi non è necessario saltare avanti e indietro.

Segnalibro e Head Over Now to [https://compliance.microsoft.com](https://compliance.microsoft.com) to tour Your One-Stop-Shop per la gestione della conformità in tutto il tuo org... oppure [leggere questo articolo](microsoft-365-compliance-center.md) per approfondire un po' di più.

![Home page del centro conformità Microsoft 365](../media/mcc-home-ga.png)

Questo mese sono state rilasciate anche soluzioni nuove e aggiornate. Ecco una breve panoramica dei punti salienti.

### <a name="now-in-preview"></a>Ora in anteprima

**Gestione dei rischi Insider (Preview)**

Siamo lieti di annunciare che la nostra soluzione di gestione dei rischi Insider è ora in anteprima pubblica. In poche parole, la gestione dei rischi Insider aiuta l'organizzazione a identificare intelligentemente e ad intervenire sui rischi di informazioni privilegiate fornendo:

- Controlli anonimi per garantire la privacy degli utenti.
- Modelli di criteri intelligenti con indicatori nativi e di terze parti che identificano le minacce privilegiate, ad esempio le perdite di dati.
- Flussi di lavoro di analisi end-to-end integrati che interessano, team HR e Legal.

Ci piacerebbe sapere cosa ne pensi. Quando si utilizza la soluzione, è possibile lasciarci commenti e suggerimenti per essere certi di soddisfare le proprie esigenze quando ci dirigiamo verso la disponibilità generale.

[Ulteriori informazioni sulla gestione dei rischi Insider](insider-risk-management.md)

### <a name="just-launched"></a>Appena avviato

**Conformità delle comunicazioni**

La graduazione dalla fase di anteprima alla disponibilità completa, la conformità alla comunicazione è un componente chiave del nuovo set di soluzioni di rischio Insider. Questa soluzione robusta consente di ridurre al minimo i rischi di comunicazione utilizzando flussi di lavoro per il rilevamento, l'analisi e l'adozione di azioni correttive per i messaggi che non soddisfano gli standard dell'organizzazione.

I commenti dei clienti durante l'anteprima sono stati fantastici. Sono stati apportati numerosi miglioramenti, tra cui un'esperienza di prima esecuzione per iniziare, miglioramenti alle azioni di ricerca e correzione e altro ancora.

[Ulteriori informazioni sulla conformità alla comunicazione](communication-compliance.md)

![Pagina conformità comunicazione nel centro conformità Microsoft 365 che mostra la prima scheda dell'esperienza di benvenuto](../media/mcc-communication-compliance-page-with-fre.png)

**Connettori dati**

Precedentemente, lo spazio di condivisione con altre caratteristiche ' Import ' nel centro sicurezza & conformità di Office 365, i connettori di dati ora hanno la propria abitazione nel centro conformità di Microsoft 365. Utilizzare la nuova pagina ' data connectors ' per importare e archiviare i dati dai file delle risorse umane (HR) dell'organizzazione e da varie piattaforme di terze parti (come Facebook, LinkedIn, Twitter e Instant Bloomberg) alle cassette postali dell'organizzazione Microsoft 365. Una volta importati, i dati possono essere gestiti in diverse soluzioni di conformità, tra cui eDiscovery, gestione dei rischi Insider, conformità alla comunicazione, controllo, criteri di conservazione e altro ancora.

[Altre informazioni sui connettori di dati](archiving-third-party-data.md)

![Pagina connettori dati nel centro conformità di Microsoft 365](../media/mcc-data-connectors-page.png)

### <a name="noteworthy-updates"></a>Aggiornamenti rilevanti

**Nuovi modelli di valutazione per il Punteggio di conformità (anteprima)**

Lavorando sempre duramente per ottenere un vantaggio rispetto al panorama di conformità sempre in evoluzione, il team di conformità Score ha inviato una nuova serie di modelli per valutare la conformità dell'organizzazione rispetto alle normative recenti e ottenere indicazioni su come implementare controlli più efficaci. Verranno visualizzati nuovi modelli per:

- ISO/IEC 27701:2019
- California Consumer Privacy Act (CCPA)
- Brasile-legge generale sulla protezione dei dati (lei Geral de proteção de dados-LGPD)
- SOC 1 tipo 2 e SOC 2 di tipo 2

[Altre informazioni sui modelli di Punteggio di conformità](compliance-score.md#templates)