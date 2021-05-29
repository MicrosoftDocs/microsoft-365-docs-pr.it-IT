---
title: Novità sulla conformità Microsoft 365
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
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
description: Che si tratta dell'aggiunta di nuove soluzioni al Centro conformità, dell'aggiornamento delle funzionalità esistenti in base al feedback dell'utente o dell'implementazione di documentazione aggiornata e aggiornata, Microsoft 365 consente di rimanere al top del panorama di conformità in continua evoluzione. Scopri cosa abbiamo fatto fino a questo mese.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ae1df2ce6373e4a8f6b01c33e50bea5e6c16ca0a
ms.sourcegitcommit: 4bcac4cb4f9399ebbd7c8cff0abb4d6ecedb731e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/28/2021
ms.locfileid: "52698953"
---
# <a name="whats-new-in-microsoft-365-compliance"></a>Novità sulla conformità Microsoft 365

Che si tratta dell'aggiunta di nuove soluzioni al Centro conformità [di Microsoft 365,](microsoft-365-compliance-center.md)dell'aggiornamento delle funzionalità esistenti in base al feedback dell'utente o dell'implementazione di documentazione aggiornata e aggiornata, Microsoft 365 consente di rimanere al top del panorama di conformità in continua evoluzione. Dai un'occhiata di seguito per vedere le novità della conformità Microsoft 365 oggi.

> [!NOTE]
> Alcune funzionalità di conformità vengono implementazioni a velocità diverse per i clienti. Se non vedi ancora una funzionalità, prova ad aggiungerti alla [versione mirata.](/office365/admin/manage/release-options-in-office-365)

> [!TIP]
> Ti interessa cosa succede in altre centri di amministrazione? Vedere questi articoli:<br>[Novità nell'interfaccia Microsoft 365 di amministrazione](/office365/admin/whats-new-in-preview)<br>[Novità nell'interfaccia SharePoint di amministrazione](/sharepoint/what-s-new-in-admin-center)<br>[Novità di Microsoft 365 Defender](../security/defender/whats-new.md)<br><br>
E visitare la roadmap [Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap) per informazioni sulle Microsoft 365 che sono state avviate, sono in fase di implementazione, sono in fase di sviluppo, sono state annullate o rilasciate in precedenza.

## <a name="april-2021"></a>Aprile 2021

### <a name="advanced-ediscovery"></a>Advanced eDiscovery

- [Limiti in Advanced eDiscovery](/microsoft-365/compliance/limits-ediscovery20#export-limits---final-export-out-of-review-set). Le organizzazioni possono ora esportare fino a 5 milioni di elementi o 500 MB, a seconda di quale sia il valore più piccolo, in una singola esportazione di elementi da un set di revisione.

### <a name="data-classification"></a>Classificazione dei dati

- [Attività di etichettatura disponibili in Esplora attività](/microsoft-365/compliance/data-classification-activity-explorer-available-events)

### <a name="data-connectors"></a>Connettori dati

- [Configurare un connettore per archiviare Cisco Jabber sui dati Oracle]/microsoft-365/compliance/archive-ciscojanoracle-data)
- [Configurare un connettore per archiviare Cisco Jabber nei dati PostgreSQL](/microsoft-365/compliance/archive-ciscojabberonpostgresql-data)

### <a name="data-loss-prevention"></a>Prevenzione della perdita di dati

- Nuovo argomento per [informazioni di riferimento sui suggerimenti per i criteri di prevenzione della perdita di dati](/microsoft-365/compliance/dlp-policy-tips-reference).
- Nuovo argomento per [Informazioni sulla prevenzione della perdita di dati](/microsoft-365/compliance/dlp-learn-about-dlp).
- Nuovo argomento per [Iniziare a usare il dashboard di](/microsoft-365/compliance/dlp-alerts-dashboard-get-started)avviso per la prevenzione della perdita di dati .

### <a name="retention-policies-and-retention-label-policies"></a>Criteri di conservazione e criteri di etichetta di conservazione

- Il percorso Microsoft 365 Groups ora supporta l'applicazione delle impostazioni di conservazione solo alle cassette postali di Microsoft 365 o solo ai siti SharePoint connessi utilizzando il cmdlet [Set-RetentionCompliancePolicy di PowerShell](/powershell/module/exchange/set-retentioncompliancepolicy) con il parametro Applications.

### <a name="sensitivity-labels"></a>Etichette di riservatezza

Outlook e aggiornamenti:
- In precedenza supportato solo dal client di etichettatura unificato AIP, l'etichettatura incorporata ora supporta impostazioni diverse per l'etichetta predefinita e [l'etichettatura obbligatoria](sensitivity-labels-office-apps.md#outlook-specific-options-for-default-label-and-mandatory-labeling)
- Encrypt-Only è ora supportato da macOS, iOS e Android
- Gestire le etichette di riservatezza nell'argomento delle app di [Office](/microsoft-365/compliance/sensitivity-labels-office-apps) aggiornato [](/microsoft-365/compliance/sensitivity-labels-office-apps#outlook-specific-options-for-default-label-and-mandatory-labeling) con le nuove voci nella tabella delle funzionalità di [Outlook](/microsoft-365/compliance/sensitivity-labels-office-apps#sensitivity-label-capabilities-in-outlook) per Impostazioni diverse per l'etichetta predefinita e l'etichettatura obbligatoria per la nuova versione della funzionalità di Outlook per l'etichettatura incorporata per supportare un'etichetta predefinita diversa ed esenzione dall'etichettatura obbligatoria. Inoltre, l'opzione Encrypt-Only è ora supportata da macOS/iOS/Android e tutti i contrassegni dinamici con variabili sono ora supportati in tutti Outlook client. L'etichettatura obbligatoria è ora disponibile per le piattaforme rimanenti.

## <a name="march-2021"></a>Marzo 2021

Ecco alcune delle modifiche apportate alle soluzioni Microsoft 365 conformità e al contenuto per il mese di marzo.

### <a name="advanced-ediscovery"></a>Advanced eDiscovery

- **Advanced eDiscovery raccolte ora** supporta il nuovo strumento [di raccolta e flusso di lavoro.](/microsoft-365/compliance/collections-overview) Altri nuovi argomenti includono [la creazione di una bozza di](https://docs.microsoft.com/microsoft-365/compliance/create-draft-collection)raccolta, il commit di una bozza di raccolta in un insieme [di](/microsoft-365/compliance/commit-draft-collection)revisione e le statistiche e i report [di raccolta.](/microsoft-365/compliance/collection-statistics-reports)
- **Esportare documenti** in un set di revisione in [un](/microsoft-365/compliance/download-export-jobs) Archiviazione di Azure account.
- **Modulo di codifica predittiva per Advanced eDiscovery**. Prima di tutto, esaminare la nuova funzionalità di [codifica predittiva](/microsoft-365/compliance/predictive-coding-overview) che sostituisce il modulo Pertinenza ritirato.

### <a name="data-classification"></a>Classificazione dei dati

- **Esplora classificazione dati**. [Introduzione a](/microsoft-365/compliance/data-classification-activity-explorer) Esplora classificazione dati.

### <a name="data-connectors"></a>Connettori dati

- **Chiavi private**. Il supporto per le chiavi private è stato aggiunto ai dati [del messaggio Bloomberg,](/microsoft-365/compliance/archive-bloomberg-message-data#set-up-a-connector-using-public-keys) ai dati [di ICE Chat](/microsoft-365/compliance/archive-icechat-data#set-up-a-connector-using-public-keys) e ai connettori di dati di Instant [Bloomberg.](/microsoft-365/compliance/archive-instant-bloomberg-data#set-up-a-connector-using-public-keys)

### <a name="data-loss-prevention"></a>Prevenzione della perdita dei dati

- **Microsoft Teams supporto .** Supporto per la prevenzione della perdita di dati esteso [a Microsoft Teams](/microsoft-365/compliance/dlp-teams-default-policy).
- **Estensione conformità Microsoft**. Introduzione all'estensione [Conformità Microsoft](/microsoft-365/compliance/dlp-chrome-get-started).

### <a name="encryption"></a>Crittografia

- **Codice Cliente per Microsoft 365**. [Panoramica del codice "Customer Key"](/microsoft-365/compliance/customer-key-tenant-level) Microsoft 365 a livello di tenant (anteprima pubblica).
- **Crittografia a chiave doppia**. Ulteriori informazioni [sull'abilitazione del supporto per](/microsoft-365/compliance/double-key-encryption) i documenti con etichetta e protetti in SharePoint e OneDrive for Business.

### <a name="insider-risk-management"></a>Gestione dei rischi Insider

I seguenti aggiornamenti delle funzionalità di gestione dei rischi insider sono stati rilasciati per l'anteprima pubblica a marzo:

- Nuova funzionalità di analisi per l'identificazione dei rischi prima di creare criteri di rischio insider
- Supporto e gestione del rilevamento delle nuove sequenze di attività di rischio
- Nuovo supporto per il rilevamento delle esfiltrazioni cumulative
- Nuovi report sull'integrità dei criteri in-app e supporto dei suggerimenti
- Nuova funzionalità del registro di controllo e creazione di report
- Miglioramenti apportati alla procedura guidata per la creazione dei criteri
- Aggiornamenti di Esplora contenuto
- Nuovo processo/supporto per la gestione degli utenti (aggiungere/rimuovere utenti dai criteri)
- Nuovo supporto per l'integrazione AAD (supporto dei criteri utente in partenza)
- Supporto del dominio aggiornato nei criteri (REGEX)
- Miglioramenti e miglioramenti dei modelli di criteri

Gli argomenti seguenti sono stati aggiornati o aggiunti per supportare queste nuove funzionalità:

- [Informazioni sulla gestione dei rischi Insider](/microsoft-365/compliance/insider-risk-management)
- [Piano per la gestione dei rischi Insider](/microsoft-365/compliance/insider-risk-management-plan)
- [Introduzione alle impostazioni di gestione dei rischi insider](/microsoft-365/compliance/insider-risk-management-settings)
- [Introduzione alla gestione dei rischi Insider](/microsoft-365/compliance/insider-risk-management-configure)
- [Creare e gestire i criteri dei rischi Insider](/microsoft-365/compliance/insider-risk-management-policies)
- [Esaminare gli avvisi relativi ai rischi Insider](/microsoft-365/compliance/insider-risk-management-alerts)
- [Intervenire riguardo ai casi di rischio Insider](/microsoft-365/compliance/insider-risk-management-cases)
- [Rivedere le attività con il log di audit del rischio Insider](/microsoft-365/compliance/insider-risk-management-audit-log)
- [Esaminare i dati con l'explorer del contenuto di gestione dei rischi Insider](/microsoft-365/compliance/insider-risk-management-content-explorer)
- [Gestire il flusso di lavoro con il dashboard utenti](/microsoft-365/compliance/insider-risk-management-users)

### <a name="records-management"></a>Gestione dei record

- **Miglioramenti al piano di file**. Un aggiornamento al [piano di file](file-plan-manager.md) rimuove o migliora le restrizioni di lunghezza precedenti per l'importazione.
- **Eliminare le etichette di conservazione per i record**. Una versione di anteprima supporta la possibilità di eliminare [etichette di conservazione](create-apply-retention-labels.md#deleting-retention-labels) che contrassegnano gli elementi come record.

### <a name="sensitive-information-types"></a>Tipi di informazioni sensibili

Il contenuto è stato aggiunto o aggiornato negli argomenti seguenti:

- [Introduzione al tipo di informazioni riservate personalizzato](/microsoft-365/compliance/create-a-custom-sensitive-information-type)
- [Informazioni sui tipi di informazioni riservate](/microsoft-365/compliance/sensitive-information-type-learn-about)
- [Creare tipi di informazioni sensibili personalizzati con classificazione esatta basata su Exact Data Match](/microsoft-365/compliance/create-custom-sensitive-information-types-with-exact-data-match-based-classification)
- [Creare notifiche per le attività di corrispondenza esatta dei dati](/microsoft-365/compliance/sit-edm-notifications-activities)
- [Definizioni di entità del tipo di informazioni riservate](/microsoft-365/compliance/sensitive-information-type-entity-definitions)
- [Creare un tipo di informazioni riservate personalizzato tramite PowerShell](/microsoft-365/compliance/create-a-custom-sensitive-information-type-in-scc-powershell)
- [Creare un dizionario di parole chiave](/microsoft-365/compliance/create-a-keyword-dictionary)

### <a name="sensitivity-labels"></a>Etichette di riservatezza

- **Supporto DoD**. Supporto per i tenant del governo statunitense con ambienti DoD.
- **Encrypt-Only for Outlook**. Le opzioni di crittografia Outlook ora includono Encrypt-Only quando si seleziona Consenti agli [utenti di assegnare le autorizzazioni](encryption-sensitivity-labels.md#let-users-assign-permissions).
- **Applicazione di etichette predefinite in Office app**. Indicazioni [aggiornate](sensitivity-labels-office-apps.md#office-built-in-labeling-client-and-the-azure-information-protection-client) su come applicare etichette predefinite nelle app Office quando è installato il client di etichettatura unificata di Azure Information Protection.

## <a name="february-2021"></a>Febbraio 2021

Ecco alcune delle modifiche apportate alle soluzioni Microsoft 365 e al contenuto per il mese di febbraio.

### <a name="auditing"></a>Controllo

- **Gestire i criteri di conservazione dei log di controllo**. Ulteriori informazioni sul nuovo [dashboard Dei criteri di conservazione di controllo.](/microsoft-365/compliance/audit-log-retention-policies#manage-audit-log-retention-policies-1)
- **Cercare nel log di controllo**. [Utilizzare lo script di PowerShell per eseguire ricerche nel log di controllo.](/microsoft-365/compliance/audit-log-search-script)

### <a name="data-classification-content-explorer"></a>Esplora contenuto classificazione dati

Il contenuto è stato aggiunto o aggiornato negli argomenti seguenti:

- [Introduzione a Esplora contenuto](/microsoft-365/compliance/data-classification-content-explorer)
- [Note sulla versione della classificazione dei dati](/microsoft-365/compliance/data-classification-pub-preview-relnotes)

### <a name="data-loss-prevention"></a>Prevenzione della perdita dei dati

Il contenuto è stato aggiunto o aggiornato negli argomenti seguenti:

- [Informazioni su Endpoint DLP](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-learn-about)
- [Inviare notifiche di posta elettronica e visualizzare i suggerimenti per i criteri di prevenzione della perdita dei dati](https://docs.microsoft.com/microsoft-365/compliance/use-notifications-and-policy-tips)
- [Informazioni sullo scanner locale Microsoft 365 prevenzione della perdita di dati](https://docs.microsoft.com/microsoft-365/compliance/dlp-on-premises-scanner-learn)
- [Introduzione allo scanner locale per la prevenzione della perdita di dati](https://docs.microsoft.com/microsoft-365/compliance/dlp-on-premises-scanner-get-started)
- [Creare criteri di prevenzione della perdita dei dati per proteggere i documenti con FCI o altre proprietà](https://docs.microsoft.com/microsoft-365/compliance/protect-documents-that-have-fci-or-other-properties)
- [Uso di Prevenzione della perdita di dati degli endpoint](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-using)
- [Introduzione alla prevenzione della perdita di dati degli endpoint](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-getting-started)

### <a name="ediscovery"></a>eDiscovery

Il contenuto è stato aggiunto o aggiornato negli argomenti seguenti:

- [Decrittografia in Microsoft 365 eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/ediscovery-decryption)
- [Query con parole chiave e condizioni di ricerca](https://docs.microsoft.com/microsoft-365/compliance/keyword-queries-and-search-conditions#limitations-for-searching-sensitive-data-types)
- [Ritiro del modulo Pertinenza in Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/relevance-module-retirement)
- [Utilizzare uno script per aggiungere utenti a un'esenzione in un caso di eDiscovery di base](https://docs.microsoft.com/microsoft-365/compliance/use-a-script-to-add-users-to-a-hold-in-ediscovery)

### <a name="encryption"></a>Crittografia

Il contenuto è stato aggiunto o aggiornato negli argomenti seguenti:

#### <a name="azure-rights-management-service-rms"></a>Azure Rights Management Service (RMS)

- [Funzionalità di crittografia gestite dai clienti](https://docs.microsoft.com/microsoft-365/compliance/office-365-customer-managed-encryption-features)
- [Exchange Online della posta elettronica con AD RMS](https://docs.microsoft.com/microsoft-365/compliance/information-rights-management-in-exchange-online). Il supporto per questo servizio è deprecato. Non è più possibile utilizzare AD RMS in un ambiente Exchange ibrido. Eseguire invece la migrazione ad Azure RMS.

#### <a name="customer-key"></a>Customer Key

- [Customer Key per Microsoft 365 a livello di tenant](https://docs.microsoft.com/microsoft-365/compliance/customer-key-tenant-level)
- [Panoramica di sicurezza e conformità](https://docs.microsoft.com/microsoftteams/security-compliance-overview)

#### <a name="information-rights-management-irm"></a>Information Rights Management (IRM)

- [Applicare Information Rights Management (IRM) a un elenco o a una raccolta.](https://docs.microsoft.com/microsoft-365/compliance/configure-irm-to-use-an-on-premises-ad-rms-server) Questi cloud nazionali non supportano questa impostazione:
    - Microsoft Cloud for US Government
    - Microsoft Cloud Germania
    - Azure e Microsoft 365 gestiti da 21Vianet in Cina)
- [Configurare IRM per l'utilizzo di un server AD RMS locale.](https://docs.microsoft.com/microsoft-365/compliance/configure-irm-to-use-an-on-premises-ad-rms-server) Il supporto per questo servizio in un ambiente Exchange ibrido è deprecato.

### <a name="sensitive-information-types"></a>Tipi di informazioni riservate

Il contenuto è stato aggiunto o aggiornato negli argomenti seguenti:

- [Informazioni sui tipi di informazioni riservate](https://docs.microsoft.com/microsoft-365/compliance/sensitive-information-type-learn-about)
- [Creare un tipo di informazione riservata personalizzata usando PowerShell](https://docs.microsoft.com/microsoft-365/compliance/create-a-custom-sensitive-information-type-in-scc-powershell)
- [Creare tipi di informazioni riservate personalizzati con classificazione basata su Corrispondenza esatta dati](https://docs.microsoft.com/microsoft-365/compliance/create-custom-sensitive-information-types-with-exact-data-match-based-classification)
- [Definizioni delle entità tipo di informazioni sensibili](https://docs.microsoft.com/microsoft-365/compliance/sensitive-information-type-entity-definitions)


### <a name="sensitivity-labels"></a>Etichette di riservatezza

Il contenuto è stato aggiunto o aggiornato negli argomenti seguenti:

- **SharePoint condivisione esterna**. Per [le etichette contenitore,](sensitivity-labels-teams-groups-sites.md) l'opzione per la condivisione esterna SharePoint siti viene ora rilasciata come disponibile in genere. Inoltre, l'interfaccia Microsoft 365 e Planner ora supportano l'applicazione di queste etichette di riservatezza. 
- **Creazione condivisa e salvataggio automatico**. Il supporto [per la creazione condivisa e il salvataggio](sensitivity-labels-coauthoring.md) automatico per i file crittografati viene rilasciato come anteprima per i test nei tenant non di produzione.

## <a name="january-2021"></a>Gennaio 2021

### <a name="support-for-card-content-in-teams"></a>Supporto per il contenuto delle schede in Teams

Le soluzioni di Microsoft 365 seguenti supportano ora il rilevamento del contenuto della scheda [generato](/microsoftteams/platform/task-modules-and-cards/what-are-cards) tramite le app nei Teams messaggi:

- **Core e Advanced eDiscovery**. Il contenuto della scheda può [ora essere messo](create-ediscovery-holds.md#preserve-card-content) [in](/microsoftteams/ediscovery-investigation#search-for-card-content) attesa o incluso nelle ricerche (si applica anche alla ricerca di contenuto).
- **Controlla**. L'attività della scheda [viene ora registrata nel log di controllo.](/microsoftteams/audit-log-events#teams-activities)
- **Criteri di conservazione**. Può ora usare i criteri di conservazione per [conservare ed eliminare il contenuto della scheda.](retention-policies-teams.md#whats-included-for-retention-and-deletion)

### <a name="information-governance-and-records-management"></a>Governance delle informazioni e gestione dei record

[Nuova valutazione per](retention-regulatory-requirements.md#new-zealand-public-records-act) l'utilizzo della governance delle informazioni e della gestione dei record per soddisfare gli obblighi di conformità per il New Zealand Public Records Act.

### <a name="sensitivity-labels"></a>Etichette di riservatezza

- Le etichette di riservatezza sono ora supportate per i tenant del governo statunitense (GCC e GCC-H).
- Nuovo [supporto per l'etichettatura](sensitivity-labels-office-apps.md) automatica per macOS.

## <a name="december-2020"></a>Dicembre 2020

### <a name="spotlight-new-content-for-insider-risk-solutions"></a>Contenuti in evidenza: nuovi contenuti per soluzioni di rischio insider

Il team Microsoft 365 contenuto di conformità è al lavoro per creare documenti di "soluzione di contenuto" per promuovere il modo in cui le funzionalità di conformità possono essere utilizzate insieme per soddisfare gli obiettivi di conformità.

Il primo è il contenuto che riunisce le nostre soluzioni di rischio insider: conformità delle comunicazioni, gestione dei rischi insider, barriere alle informazioni e gestione degli accessi privilegiati. Ecco un'occhiata a ciò che troverai:

- [Nuova pagina di destinazione per le soluzioni di rischio insider.](insider-risk-solution-overview.md) Include informazioni dettagliate sui rischi che le soluzioni possono contribuire a ridurre, i requisiti di licenza, la sequenza di distribuzione, le illustrazioni dell'architettura, le risorse di formazione e altro ancora.
- Nuovi articoli di panoramica per ogni soluzione di rischio insider. Linee guida e collegamenti ad articoli utili per informazioni su, pianificare, distribuire e gestire ogni soluzione:
  - [Conformità delle comunicazioni](communication-compliance-solution-overview.md)
  - [Gestione dei rischi Insider](insider-risk-management-solution-overview.md)
  - [Barriere informative](information-barriers-solution-overview.md)
  - [Gestione accessi con privilegi](privileged-access-management-solution-overview.md)
  
Presto saranno disponibili altri documenti sulle soluzioni di contenuto.

### <a name="advanced-ediscovery"></a>Advanced eDiscovery

Flusso di lavoro e funzionalità migliorate per [l'aggiunta](add-custodians-to-case.md) di custodi e origini dati [non](non-custodial-data-sources.md) Advanced eDiscovery caso.

### <a name="data-connectors"></a>Connettori dati

[Quattro nuovi connettori Veritas](archiving-third-party-data.md#third-party-data-connectors)rilasciati: Redtail Speak, Salesforce Chatter, ServiceNow e Yieldbroker.

### <a name="encryption"></a>Crittografia

Introduzione [al codice "Customer Key" Microsoft 365 a livello di tenant.](customer-key-tenant-level.md) Usando le chiavi fornite, è possibile creare un criterio di crittografia dei dati e assegnarlo al tenant. Protezione esecuzione programmi crittografa i dati nel tenant per questi carichi di lavoro:

- Teams chat (chat 1:1, chat di gruppo, chat di riunione e conversazioni di canale)
- Teams messaggi multimediali (immagini, frammenti di codice, video, immagini wiki)
- Teams registrazioni di chiamate e riunioni archiviate in Teams archiviazione
- Teams chat
- Teams suggerimenti di chat di Cortana
- Teams di stato
- Informazioni sull'utente e sul segnale Exchange Online

### <a name="records-management"></a>Gestione dei record

Il [gruppo di ruoli amministratore](get-started-with-records-management.md#permissions-required-for-records-management) Gestione record concede ora le autorizzazioni per tutte le funzionalità di gestione dei record, inclusa la revisione dell'eliminazione.

### <a name="sensitivity-labels"></a>Etichette di riservatezza

- [Etichetta automaticamente i dati in Azure Purview (anteprima)](/azure/purview/create-sensitivity-label). È ora possibile creare e applicare automaticamente etichette di riservatezza agli asset in Azure Purview, ad esempio i file nell'archiviazione BLOB di Azure e le colonne di database in SQL Server.
- [Richiedere agli utenti di applicare un'etichetta agli elementi](sensitivity-labels-office-apps.md#require-users-to-apply-a-label-to-their-email-and-documents). Nota anche come "etichettatura obbligatoria", questa nuova opzione richiede agli utenti di scegliere e applicare un'etichetta di riservatezza negli scenari specifici.
