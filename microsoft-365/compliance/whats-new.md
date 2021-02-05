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
description: Che si tratta dell'aggiunta di nuove soluzioni al Centro conformità, dell'aggiornamento delle funzionalità esistenti in base al feedback degli utenti o dell'implementazione di documentazione aggiornata e aggiornata, Microsoft 365 consente di rimanere sempre aggiornati nel panorama della conformità in continua evoluzione. Scopri cosa abbiamo fatto fino a questo mese.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 682f736456ebe822ee5a34de0175003fd7516920
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2021
ms.locfileid: "50113975"
---
# <a name="whats-new-in-microsoft-365-compliance"></a>Novità sulla conformità Microsoft 365

Che si tratta dell'aggiunta di nuove soluzioni al Centro conformità [Microsoft 365,](microsoft-365-compliance-center.md)dell'aggiornamento delle funzionalità esistenti in base al feedback degli utenti o dell'implementazione di documentazione aggiornata e aggiornata, Microsoft 365 consente di rimanere sempre aggiornati nel panorama della conformità. Di seguito sono riportate le novità della conformità di Microsoft 365.

> [!NOTE]
> Alcune funzionalità di conformità vengono implementazioni a velocità diverse per i clienti. Se non vedi ancora una funzionalità, prova ad aggiungerti alla [versione mirata.](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365)

> [!TIP]
> Sei interessato a cosa succede in altre centri di amministrazione? Consultare questi articoli:<br>[Novità nell'interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/office365/admin/whats-new-in-preview)<br>[Novità nell'interfaccia di amministrazione di SharePoint](https://docs.microsoft.com/sharepoint/what-s-new-in-admin-center)<br>[Novità di Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/whats-new)<br><br>
Visitare la roadmap di [Microsoft 365](https://www.microsoft.com/en-us/microsoft-365/roadmap) per informazioni sulle funzionalità di Microsoft 365 avviate, in fase di distribuzione, in fase di sviluppo, annullate o rilasciate in precedenza.

## <a name="december-2020"></a>Dicembre 2020

### <a name="spotlight-new-content-for-insider-risk-solutions"></a>Contenuti in evidenza: nuovi contenuti per soluzioni di rischio Insider

Il team dei contenuti di conformità di Microsoft 365 è al lavoro per creare documenti sulla "soluzione di contenuto" per promuovere l'uso comune delle funzionalità di conformità per soddisfare gli obiettivi di conformità.

Il primo è il contenuto che riunisce le soluzioni di rischio Insider: conformità delle comunicazioni, gestione dei rischi Insider, barriere in fatto di informazioni e gestione degli accessi privilegiati. Ecco un'anteprima di ciò che troverai:

- [Nuova pagina di destinazione per soluzioni di rischio Insider.](insider-risk-solution-overview.md) Include informazioni dettagliate sui rischi che le soluzioni possono contribuire a ridurre, i requisiti di licenza, la sequenza di distribuzione, le illustrazioni dell'architettura, le risorse di formazione e altro ancora.
- Nuovi articoli di panoramica per ogni soluzione di rischio Insider. Linee guida e collegamenti ad articoli utili per informazioni su, pianificare, distribuire e gestire ogni soluzione:
  - [Conformità delle comunicazioni](communication-compliance-solution-overview.md)
  - [Gestione dei rischi Insider](insider-risk-management-solution-overview.md)
  - [Barriere informative](information-barriers-solution-overview.md)
  - [Gestione accessi con privilegi](privileged-access-management-solution-overview.md)
  
Altri documenti sulle soluzioni di contenuto saranno disponibili a breve.

### <a name="advanced-ediscovery"></a>Advanced eDiscovery

Flusso di lavoro e funzionalità migliorate [per l'aggiunta](add-custodians-to-case.md) di responsabile e [origini dati non](non-custodial-data-sources.md) di tipo responsabile a un caso di Advanced eDiscovery.

### <a name="data-connectors"></a>Connettori dati

[Quattro nuovi connettori Globanet](archiving-third-party-data.md#third-party-data-connectors)rilasciati: Redtail Speak, Salesforce Chatter, ServiceNow e Yieldbroker.

### <a name="encryption"></a>Crittografia

Introduzione [a Customer Key per Microsoft 365 a livello di tenant.](customer-key-tenant-level.md) Utilizzando le chiavi fornite, è possibile creare un criterio di crittografia dei dati e assegnarlo al tenant. Protezione esecuzione programmi crittografa i dati nel tenant per questi carichi di lavoro:

- Messaggi di chat di Teams (chat 1:1, chat di gruppo, chat di riunioni e conversazioni del canale)
- Messaggi multimediali di Teams (immagini, frammenti di codice, video, immagini wiki)
- Registrazioni delle chiamate e delle riunioni di Teams archiviate nello spazio di archiviazione di Teams
- Notifiche di chat di Teams
- Suggerimenti per le chat di Teams da Cortana
- Messaggi di stato di Teams
- Informazioni su utenti e segnali per Exchange Online

### <a name="records-management"></a>Gestione dei record

Il [gruppo di ruoli amministratore](get-started-with-records-management.md#permissions-required-for-records-management) Gestione record concede ora le autorizzazioni per tutte le funzionalità di gestione dei record, inclusa la revisione dell'eliminazione.

### <a name="sensitivity-labels"></a>Etichette di riservatezza

- [Etichettare automaticamente i dati in Azure Purview (anteprima).](https://docs.microsoft.com/azure/purview/create-sensitivity-label) È ora possibile creare e applicare automaticamente etichette di riservatezza agli asset in Azure Purview, ad esempio i file nell'archiviazione BLOB di Azure e le colonne di database in SQL Server.
- [Richiedere agli utenti di applicare un'etichetta agli elementi.](sensitivity-labels-office-apps.md#require-users-to-apply-a-label-to-their-email-and-documents) Nota anche come "etichettatura obbligatoria", questa nuova opzione richiede agli utenti di scegliere e applicare un'etichetta di riservatezza negli scenari specifici.

## <a name="november-2020"></a>Novembre 2020
È sufficiente ricordare che spesso rilasciamo funzionalità nuove e aggiornate in uno stato di anteprima per scoprire come vengono usate in modo da poterle affinare e migliorare prima di rilasciare alla disponibilità generale. Il feedback dell'utente è fondamentale durante l'anteprima (e oltre), quindi assicurati di inviarci le tue opinioni aprendo la scheda Feedback in basso a destra nel Centro conformità.

![feedback](../media/Feedback_card_MCC.JPG)

### <a name="spotlight-endpoint-data-loss-prevention-dlp-released"></a>Spotlight: Endpoint data loss prevention (DLP) released

[Endpoint DLP](endpoint-dlp-learn-about.md) estende le funzionalità di monitoraggio e protezione delle attività di DLP alle informazioni sensibili nei dispositivi Windows 10. Dopo [l'onboarded](dlp-configure-endpoints.md) dei dispositivi nel Centro conformità Microsoft 365, è possibile configurare i criteri DLP per proteggere le informazioni riservate in tali dispositivi.

### <a name="advanced-ediscovery"></a>Advanced eDiscovery

Per semplificare la gestione del contenuto crittografato nel flusso di lavoro di [](ediscovery-decryption.md) eDiscovery, gli strumenti di eDiscovery di Microsoft 365 ora incorporano la decrittografia dei file crittografati allegati ai messaggi di posta elettronica e inviati in Exchange. Inoltre, i documenti crittografati archiviati in SharePoint e OneDrive vengono decrittografati in Advanced eDiscovery.

### <a name="compliance-manager"></a>Compliance Manager

- [Supporto per gli abbonamenti a Microsoft 365 Government.](compliance-manager.md) Compliance Manager è ora disponibile per i clienti della US Government Community (GCC) Moderate e High.
- [Analizzatore configurazione di conformità Microsoft per Compliance Manager.](compliance-manager-mcca.md) Nuovo strumento basato su PowerShell che consente di iniziare a usare Compliance Manager eseguendo l'analisi delle configurazioni correnti dell'organizzazione e convalidandole in base alle procedure consigliate di Microsoft 365.
- [Nuovi modelli.](compliance-manager-templates-list.md) Sono stati aggiunti 56 nuovi modelli, portando il totale dei modelli di Compliance Manager a oltre 230.

### <a name="data-connectors"></a>Connettori dati

[Cinque nuovi connettori Globanet in anteprima.](archiving-third-party-data.md#third-party-data-connectors) I nuovi connettori includono Reuters Dealing, Reuters FX, CellTrust, XIP, GENERIC MS SQL Database.

### <a name="retention-labels-disposition-review"></a>Etichette di conservazione (revisione per l'eliminazione)

Per visualizzare gli elementi durante una revisione dell'eliminazione, gli utenti devono ora essere membri dei gruppi di ruoli Visualizzatore contenuto di Esplora contenuto e Visualizzatore elenco [Esplora contenuto.](disposition.md#permissions-for-disposition) Anche se necessari per esaminare gli elementi, questi gruppi di ruoli non sono necessari per completare la revisione dell'eliminazione.

### <a name="sensitivity-labels"></a>Etichette di riservatezza

- [(Anteprima) Impostazioni di condivisione esterna per i siti di SharePoint.](sensitivity-labels-teams-groups-sites.md#how-to-configure-groups-and-site-settings) Quando si crea un'etichetta che verrà utilizzata per gruppi e siti, verrà visualizzata un'opzione per controllare la condivisione esterna per i siti di SharePoint a cui è applicata l'etichetta. È possibile specificare che la condivisione è consentita per chiunque, per gli utenti guest nuovi ed esistenti, solo per gli utenti guest esistenti o solo per gli utenti dell'organizzazione. Quando l'etichetta viene applicata, le impostazioni dell'etichetta sostituiranno tutte le impostazioni di condivisione esterna [configurate nell'interfaccia di amministrazione di SharePoint.](https://docs.microsoft.com/sharepoint/change-external-sharing-site)
- [Rimuovere l'etichetta e la crittografia da un documento etichettato.](sensitivity-labels-sharepoint-onedrive-files.md#remove-encryption-for-a-labeled-document) Per rimuovere sia un'etichetta che la crittografia applicata da un documento con etichetta in SharePoint, gli amministratori globali e gli amministratori di SharePoint possono eseguire il nuovo `Unlock-SPOSensitivityLabelEncryptedFile` cmdlet. Questo cmdlet viene eseguito anche se l'amministratore non dispone delle autorizzazioni di accesso al sito o al file o se il servizio Azure Rights Management non è disponibile.

## <a name="october-2020"></a>Ottobre 2020

### <a name="advanced-ediscovery"></a>Advanced eDiscovery

[Supporto del linguaggio CJK.](ediscovery-cjk-support.md) Advanced eDiscovery ora supporta le lingue dei set di caratteri a byte doppio, note collettivamente come lingue CJK (include il cinese semplificato, il cinese tradizionale, il giapponese e il coreano). Questi possono essere usati in diversi scenari avanzati di set di recensioni.

### <a name="sensitivity-labels"></a>Etichette di riservatezza

- [Ambito dell'etichetta.](sensitivity-labels.md#label-scopes) Quando si crea un'etichetta di riservatezza, viene visualizzata una nuova opzione per definire l'ambito dell'etichetta. Questa opzione consente di configurare le etichette solo per file e messaggi di posta elettronica, contenitori (ad esempio siti di SharePoint e Teams) o entrambi.
- [Contrassegno del contenuto dinamico.](sensitivity-labels-office-apps.md#dynamic-markings-with-variables) Quando si configura il contrassegno del contenuto per un'etichetta di riservatezza, è ora possibile utilizzare le variabili dinamiche, ad esempio e nella stringa di testo per l'intestazione, il piè di pagina `${Item.Label}` `${Item.Location}` o la filigrana.

## <a name="september-2020"></a>Settembre 2020

### <a name="spotlight-compliance-manager"></a>Spotlight: Compliance Manager

Annunciato a Ignite quest'anno, il punteggio di conformità viene ridenominato [Compliance Manager.](compliance-manager.md) Questa versione completa la transizione dalla home page precedente di Compliance Manager nel Service Trust Portal e introduce una soluzione di gestione della conformità end-to-end nel Centro conformità Microsoft 365.

Guardare il video seguente per informazioni su come Compliance Manager può semplificare il modo in cui l'organizzazione gestisce la conformità.
<br>
<br>
>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4FGYZ]

### <a name="advanced-audit"></a>Audit avanzato

- La nuova conservazione di 10 anni dei log di controllo consente di supportare indagini di lunga durata e di rispondere agli obblighi normativi, legali e interni.
- [Tre nuovi eventi cruciali.](advanced-audit.md#access-to-crucial-events-for-investigations) I nuovi eventi seguenti consentono di analizzare possibili violazioni e determinare l'ambito di compromissione: Send, SearchQueryInitiatedExchange e SearchQueryInitiatedSharePoint.

### <a name="communication-compliance"></a>Conformità delle comunicazioni

- [Gruppi di ruoli aggiornati.](communication-compliance-configure.md#step-1-required-enable-permissions-for-communication-compliance) I gruppi di ruoli di conformità delle comunicazioni ora corrispondono alla struttura del gruppo di ruoli disponibile per la soluzione di gestione dei rischi Insider.
- [Dashboard dei report.](communication-compliance-feature-reference.md#reports-preview) Posizione centrale per la visualizzazione di tutti i report di conformità delle comunicazioni. I widget di report offrono una rapida visualizzazione delle informazioni dettagliate più comunemente necessarie per una valutazione generale dello stato delle attività di conformità delle comunicazioni.
- [Flussi di Power Automate](communication-compliance-feature-reference.md#power-automate-flows). Configurare i flussi per automatizzare le attività per avvisi e utenti, informare i responsabili quando gli utenti attivano gli avvisi e altro ancora.
- [Azione di correzione "Migliora classificazione".](communication-compliance-investigate-remediate.md#step-3-decide-on-a-remediation-action) Gli avvisi contenenti elementi che corrispondono a classificatori che possono essere classificati possono trarre vantaggio dal feedback per ridurre al minimo i falsi positivi nell'organizzazione. **L'opzione Migliora classificazione** consente di fornire feedback se gli elementi rilevati corrispondono al classificatore configurato nei criteri di conformità delle comunicazioni correlati. Puoi anche suggerire altri classificatori da associare all'elemento per migliorare l'accuratezza della corrispondenza per gli avvisi futuri.

### <a name="data-connectors"></a>Connettori dati

- [Nuovi connettori dati di terze parti.](archiving-third-party-data.md#third-party-data-connectors) 25 nuovi connettori dati, inclusi 14 connettori da Globanet e 8 da Telemessage.
- [Connettore di badging fisico.](import-physical-badging-data.md) Importare dati di badging fisici, ad esempio gli eventi di accesso fisico non elaborati dei dipendenti o eventuali allarmi di accesso fisico generati dal sistema di badging dell'organizzazione. Ad esempio, le voci relative a edifici, sale server o data center. I dati di badging fisici possono essere utilizzati dalla soluzione di gestione dei rischi Insider per proteggere l'organizzazione da attività dannose o furti di dati all'interno dell'organizzazione.

### <a name="insider-risk-management"></a>Gestione dei rischi Insider

- [Integrazione di Microsoft Teams.](insider-risk-management-settings.md#microsoft-teams-preview) Quando l'integrazione di Teams è attivata nelle impostazioni dei rischi Insider, è possibile coordinare e collaborare con altri stakeholder in Teams su attività come la condivisione e l'archiviazione sicura dei dati relativi a singoli casi, il monitoraggio e la revisione delle attività di risposta di analisti e investigatori e altro ancora.
- [Flussi di Power Automate](insider-risk-management-settings.md#power-automate-flows-preview). Configurare i flussi per automatizzare attività importanti per casi e utenti, ad esempio il recupero di informazioni su utenti, avvisi e casi da condividere con le parti interessate e altre app, l'automazione di azioni come l'inserimento di note sul caso e altro ancora.
- [Esplora attività.](insider-risk-management-alerts.md#activity-explorer-preview) Disponibile quando si esaminano gli avvisi, Esplora attività offre a investigatori e analisti uno strumento analitico completo per eseguire il drill-down in ogni avviso. Esaminare rapidamente una sequenza temporale delle attività rischiose rilevate e identificare e filtrare tutte le attività di rischio associate agli avvisi.

### <a name="retention-policies-and-retention-labels"></a>Criteri di conservazione ed etichette di conservazione.

- [Supporto per Yammer.](retention-policies-yammer.md) È ora possibile utilizzare i criteri di conservazione per conservare ed eliminare i messaggi della community di Yammer e i messaggi privati.
- [Applicare etichette alle registrazioni delle riunioni di Teams.](apply-retention-labels-automatically.md#microsoft-teams-meeting-recordings) Quando si crea un criterio di applicazione automatica di etichette, usare l'editor di query con parole chiave per identificare le registrazioni delle riunioni di Teams archiviate negli account di OneDrive degli utenti o in SharePoint.

### <a name="records-management"></a>Gestione dei record

[Supporto per i record normativi.](declare-records.md#how-to-display-the-option-to-mark-content-as-a-regulatory-record) La classificazione di un'etichetta come record normativo aumenta le restrizioni applicate al contenuto a cui l'etichetta viene applicata e limita le azioni di gestione disponibili per l'etichetta stessa. Ad esempio, dopo l'applicazione al contenuto, nessuno, nemmeno un amministratore globale, può rimuovere l'etichetta. [Ulteriori informazioni](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked) sulle azioni consentite e bloccate per i record normativi.

### <a name="sensitivity-labels"></a>Etichette di riservatezza

[Supporto per i clienti del governo statunitense.](https://docs.microsoft.com/enterprise-mobility-security/solutions/ems-aip-premium-govt-service-description) Le etichette di riservatezza sono ora supportate per i clienti GCC, GCC High e DoD, solo per il client e lo scanner di etichettatura unificati di Azure Information Protection.

### <a name="trainable-classifiers"></a>Classificatori sottoponibili a training

Le nuove funzionalità di riqualificazione e feedback consentono di migliorare l'accuratezza e ridurre al minimo le corrispondenze di falsi positivi per tutti i classificatori personalizzati e alcuni classificatori già preparati. Questo flusso consente di fornire feedback sulla corrispondenza di determinati classificatori tra gli elementi, suggerire altri classificatori da associare agli elementi e riqualificare i classificatori per perfezionare e migliorare l'accuratezza della corrispondenza.

Questa nuova funzionalità è inclusa nelle funzionalità seguenti:

> [!NOTE]
> Per tutte le funzionalità, se fornisci almeno 30 risposte di feedback, creeremo una versione aggiornata del classificatore che puoi esaminare. In caso di miglioramento, è possibile ripubblicare il classificatore.

- [Classificatori di cui è possibile utilizzare il training.](classifier-learn-about.md#retraining-classifiers) Per migliorare l'accuratezza dei classificatori pubblicati, è possibile fornire un feedback sul fatto che gli elementi rilevati corrispondano al classificatore.
- [Conformità delle comunicazioni](classifier-how-to-retrain-comms-compliance.md). La nuova **azione di** correzione della classificazione Migliora consente di fornire feedback se un elemento di un avviso di conformità alle comunicazioni corrisponde al classificatore configurato nei criteri di conformità delle comunicazioni.
- [Esplora contenuto.](classifier-how-to-retrain-content-explorer.md) Se si configura un criterio di etichettatura automatica di conservazione per applicare automaticamente le etichette ai messaggi di posta elettronica che corrispondono a classificatori di cui è possibile eseguire il training, è possibile utilizzare Esplora contenuto per esaminare gli elementi etichettati e fornire feedback se gli elementi corrispondono al classificatore.

## <a name="august-2020"></a>Agosto 2020

### <a name="spotlight-insider-risk-and-communication-compliance-updates"></a>Informazioni in evidenza: aggiornamenti per la conformità dei rischi Insider e delle comunicazioni

Diverse funzionalità nuove e migliorate hanno raggiunto l'anteprima pubblica questo mese:

**Gestione dei rischi Insider**

- Vedere i sei nuovi modelli [di criteri:](insider-risk-management-policies.md#policy-templates)
    - Perdite di dati per utenti con priorità
    - Perdite di dati da parte di utenti scontenti
    - Violazioni generali dei criteri di sicurezza
    - Violazioni dei criteri di sicurezza da parte degli utenti
    - Violazioni dei criteri di sicurezza da parte degli utenti con priorità
    - Violazioni dei criteri di sicurezza da parte di utenti scontenti

- [L'integrazione con Microsoft Defender per Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) consente di importare e filtrare gli avvisi di Microsoft Defender per gli endpoint per le attività rilevate dai criteri creati dai nuovi modelli di criteri di violazione della sicurezza. Esiste anche un'impostazione di rischio [Insider](insider-risk-management-settings.md#microsoft-defender-for-endpoint-preview) correlata in cui è possibile scegliere di importare gli avvisi di sicurezza per la gestione dei rischi Insider in base allo stato di valutazione degli avvisi di Microsoft Defender for Endpoint.

    > [!NOTE]
    > Per sfruttare l'integrazione di Microsoft Defender for Endpoint (inclusi i nuovi modelli di violazione dei criteri di sicurezza), è necessario che Microsoft Defender for Endpoint sia configurato nell'organizzazione. Dovrai anche abilitare Microsoft Defender for Endpoint per l'integrazione della gestione dei rischi Insider configurando le funzionalità avanzate [in Microsoft Defender for Endpoint.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center)
 
- Personalizzare le soglie degli [indicatori durante la creazione di un criterio.](insider-risk-management-policies.md#create-a-new-policy)
- Impostare gruppi [di utenti](insider-risk-management-settings.md#priority-user-groups-preview) con priorità per definire gli utenti dell'organizzazione la cui attività richiede un'analisi più stretta in base a fattori quali la posizione, il livello di accesso alle informazioni riservate o la cronologia dei rischi.
- Usare le API office 365 Management Activity per esportare i dettagli degli avvisi per i rischi [Insider](insider-risk-management-settings.md#export-alerts-preview) in altre applicazioni che l'organizzazione potrebbe usare per gestire o aggregare i dati sui rischi Insider.
- Le [nuove impostazioni di dominio](insider-risk-management-settings.md#domains-preview) consentono di definire e controllare i livelli di rischio per l'attività in domini specifici.

**Conformità delle comunicazioni**

- Quando [si esaminano i messaggi in un](communication-compliance-investigate-remediate.md#step-3-decide-on-a-remediation-action)avviso, è ora possibile rimuovere i messaggi inappropriati nei canali di Microsoft Teams, 1:1 e nelle chat di gruppo. I messaggi e il contenuto rimossi vengono sostituiti con un suggerimento per i criteri che spiega che è stato rimosso a causa di contenuto sensibile.
- Nuovi [ruoli di comunicazione](communication-compliance-configure.md#step-1-required-enable-permissions-for-communication-compliance) (questi saranno inclusi anche nei nuovi gruppi di ruoli di conformità delle comunicazioni rilasciati a settembre).
- Nuova esperienza delle impostazioni di conformità delle comunicazioni che include le impostazioni [per la privacy e](communication-compliance-feature-reference.md#privacy) i modelli di [avviso.](communication-compliance-feature-reference.md#notice-templates)
- Nuovi [classificatori per](communication-compliance-feature-reference.md#classifiers) rilevare immagini adulte, racy e gory.
- La nuova notifica "Pattern detected" che viene visualizzata quando si esaminano i messaggi [in](communication-compliance-investigate-remediate.md#step-2-examine-the-message-details) un avviso consente di sapere se un utente riempe istanze dello stesso comportamento.

### <a name="sensitivity-labels"></a>Etichette di riservatezza

- Per i tenant degli enti pubblici degli Stati Uniti (GCC, GCC-HC e DoD), le etichette di riservatezza sono attualmente supportate solo per lo scanner e il client di etichettatura unificata di Azure Information Protection. Per altre informazioni, vedere [Descrizione del servizio Azure Information Protection Premium per gli enti pubblici](https://docs.microsoft.com/enterprise-mobility-security/solutions/ems-aip-premium-govt-service-description).
- È ora possibile [utilizzare PowerShell &](create-sensitivity-labels.md#use-powershell-for-sensitivity-labels-and-their-policies) Centro sicurezza e conformità per creare e configurare tutte le impostazioni presenti nell'interfaccia di amministrazione per l'etichettatura. Ciò significa che, oltre a usare PowerShell per le impostazioni che non sono disponibili nelle centri di amministrazione per l'etichettatura, è ora possibile creare e manutenzione di etichette di riservatezza e criteri di etichetta di riservatezza completamente script.

### <a name="records-management-content-overhaul"></a>Gestione dei record: revisione del contenuto

Nuovi documenti relativi ai passaggi di distribuzione, contrassegno del contenuto come record e controllo delle versioni dei record:

- [Introduzione alla gestione dei record](get-started-with-records-management.md)
- [Usare le etichette di conservazione per dichiarare i record](declare-records.md)
- [Usare il controllo delle versioni per aggiornare i record archiviati in SharePoint o OneDrive](record-versioning.md)

### <a name="retention-labels--policies"></a>Etichette di conservazione & criteri

L'attività di amministrazione correlata alla conservazione è ora registrata e disponibile per la revisione nel log di controllo. Per la lista completa, vedere [Attività inerenti i criteri e le etichette di conservazione](search-the-audit-log-in-security-and-compliance.md#retention-policy-and-retention-label-activities).

### <a name="advanced-ediscovery"></a>Advanced eDiscovery

- Quando [si aggiunge una raccolta a un insieme da](add-data-to-review-set.md#define-options-to-scope-your-collection-for-review)rivedere, è ora possibile includere allegati moderni (denominati anche "allegati cloud") e versioni di documenti di SharePoint.
- Nuova [esperienza di esportazione con download diretto,](export-documents-from-review-set.md)eliminando la necessità di usare Azure Storage Explorer per scaricare il contenuto del caso.

## <a name="july-2020"></a>Luglio 2020

### <a name="spotlight-on-help-docs"></a>Informazioni in evidenza sulla documentazione della Guida

Per comprendere quali soluzioni di conformità vengono utilizzate per proteggere e gestire i dati sensibili dell'organizzazione, sono state create due nuove pagine di destinazione con una panoramica del modo in cui le soluzioni funzionano insieme per raggiungere tali obiettivi, inclusi i collegamenti a documenti correlati in modo da poter approfondire ulteriormente l'argomento.

[Microsoft Information Protection in Microsoft 365.](information-protection.md)<br>
[Governance delle informazioni Microsoft in Microsoft 365](manage-Information-governance.md)

### <a name="advanced-ediscovery-add-non-custodial-data-sources-to-your-cases"></a>Advanced eDiscovery: Aggiungere origini dati non di tipo responsabile ai casi

Aggiungere dati a un caso senza doverlo associare a un responsabile (noto come origini dati non di [tipo depositario).](non-custodial-data-sources.md) Inoltre, se è necessario mettere in attesa questi dati non-depositl, sarà possibile farlo usando la nuova funzionalità di indicizzazione avanzata.

### <a name="data-connectors-hr-connector-enhancements"></a>Connettori dati: miglioramenti dei connettori hr

(In anteprima) Una nuova versione del connettore [risorse](import-hr-data.md) umane consente di importare i dati relativi alle modifiche a livello di processo, alle revisioni delle prestazioni e ai piani di miglioramento delle prestazioni. Questi dati possono quindi essere utilizzati in diversi criteri [di rischio Insider per](insider-risk-management-policies.md) rilevare le attività correlate.

### <a name="retention-labels-new-support-for-email"></a>Etichette di conservazione: nuovo supporto per la posta elettronica

È ora possibile creare [un'etichetta di conservazione](retention.md#retention-labels) per iniziare a conservare la posta elettronica in base all'etichetta dei messaggi. Ciò non si applica agli elementi del calendario, che verranno mantenuti in base all'invio dell'elemento.

### <a name="sensitivity-labels-new-feature-and-an-improvement"></a>Etichette di riservatezza: nuova funzionalità e miglioramento

- (In anteprima) Quando si configurano le impostazioni di crittografia per [](encryption-sensitivity-labels.md#double-key-encryption) un'etichetta, cercare la nuova opzione per utilizzare la crittografia a chiave doppia per proteggere ulteriormente i file e i messaggi di posta elettronica etichettati.
- Quando si creano o si eliminano etichette di riservatezza o si creano, modificano o eliminano i criteri delle etichette, le modifiche vengono sincronizzate entro 1 ora con tutti gli utenti, le app e i servizi.
