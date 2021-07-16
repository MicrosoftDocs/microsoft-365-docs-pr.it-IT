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
ms.openlocfilehash: acbad7a1c5fa541ee83da668768cc42af7a5afda
ms.sourcegitcommit: 84e70051bb61b1171cebfbabe500b4904dfac04f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/16/2021
ms.locfileid: "53464010"
---
# <a name="whats-new-in-microsoft-365-compliance"></a>Novità sulla conformità Microsoft 365

Che si tratta dell'aggiunta di nuove soluzioni al [Centro conformità Microsoft 365,](microsoft-365-compliance-center.md)dell'aggiornamento delle funzionalità esistenti in base al feedback dell'utente o della distribuzione di documentazione aggiornata e aggiornata, Microsoft 365 consente di rimanere al top del panorama di conformità in continua evoluzione. Dai un'occhiata di seguito per vedere le novità della conformità Microsoft 365 oggi.

> [!NOTE]
> Alcune funzionalità di conformità vengono implementazioni a velocità diverse per i clienti. Se non vedi ancora una funzionalità, prova ad aggiungerti alla [versione mirata.](/office365/admin/manage/release-options-in-office-365)

> [!TIP]
> Ti interessa cosa succede in altre centri di amministrazione? Vedere questi articoli:
>
> - [Novità della interfaccia di amministrazione di Microsoft 365](/office365/admin/whats-new-in-preview)
> - [Novità nell'interfaccia SharePoint di amministrazione](/sharepoint/what-s-new-in-admin-center)
> - [Novità di Microsoft 365 Defender](../security/defender/whats-new.md)
>
> E visitare la roadmap [Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap) per informazioni sulle Microsoft 365 che sono state avviate, sono in fase di implementazione, sono in fase di sviluppo, sono state annullate o rilasciate in precedenza.

## <a name="june-2021"></a>Giugno 2021

### <a name="customer-key"></a>Customer Key

- [Crittografia del servizio con chiave cliente](customer-key-overview.md) (IPS a livello di tenant della chiave cliente ora crittografa la configurazione dell'etichetta di riservatezza per Microsoft Information Protection).

### <a name="data-connectors"></a>Connettori dati

- Abbiamo rilasciato 17 nuovi connettori dati in collaborazione con [17a-4 LLC](archiving-third-party-data.md#17a-4-data-connectors) e un nuovo connettore [in collaborazione con CellTrust.](archiving-third-party-data.md#celltrust-data-connectors) Abbiamo anche rilasciato altri connettori dati in collaborazione con [Veritas](archiving-third-party-data.md#veritas-data-connectors) e [TeleMessage.](archiving-third-party-data.md#telemessage-data-connectors) Ad oggi, questo rende disponibili 65 connettori di dati per importare e archiviare dati di terze parti Microsoft 365.

### <a name="ediscovery"></a>eDiscovery

- [Eseguire query e filtrare](review-set-search.md) il contenuto in un set di recensioni (nuove funzionalità di query e filtro in un nuovo formato UX per filtrare e cercare contenuto in un set di recensioni)
- [Contrassegnare](tagging-documents.md) i documenti in un set di revisioni in Advanced eDiscovery (nuove funzionalità di tag ed esperienza utente per semplificare e velocizzare l'aggiunta di tag ai documenti in un set di revisioni; include nuove funzionalità di applicazione di tag ai documenti tramite una query e l'utilizzo di filtri per trovare o escludere rapidamente gli elementi del set di revisioni in base alla modalità di applicazione di tag a un elemento)
- Configurare i limiti di conformità per le indagini [di eDiscovery](set-up-compliance-boundaries.md) (Microsoft ha rimosso il requisito di contattare il supporto tecnico microsoft per richiedere che un attributo di conformità sia sincronizzato con gli account OneDrive; ora viene utilizzato un filtro delle autorizzazioni di ricerca delle cassette postali per applicare i limiti di conformità per OneDrive)

### <a name="sensitivity-labels"></a>Etichette di riservatezza

- La procedura guidata dei criteri [](sensitivity-labels-office-apps.md#outlook-specific-options-for-default-label-and-mandatory-labeling) di etichetta di riservatezza ora supporta opzioni specifiche Outlook per l'etichetta predefinita e l'etichettatura obbligatoria come configurazione più semplice rispetto alle impostazioni avanzate di PowerShell (ancora supportate).
- Il supporto [per i contrassegni dinamici con variabili](sensitivity-labels-office-apps.md#dynamic-markings-with-variables ) è ora in distribuzione per Word, Excel e PowerPoint sul web
- Per [i criteri di etichettatura](apply-sensitivity-label-automatically.md) automatica per Exchange, se l'etichetta è configurata per la crittografia, tale crittografia non viene applicata. Inoltre, per Exchange criteri di etichettatura automatica, è ora possibile configurare le eccezioni e le nuove condizioni seguenti: oggetto, indirizzo del destinatario o indirizzo del mittente corrisponde a modelli; l'indirizzo del destinatario contiene parole; il dominio del mittente è, il destinatario è un membro di; sender is.
- Quando si utilizzano etichette di riservatezza con team, gruppi e siti, è possibile utilizzare Set-SPOTenant con il parametro BlockSendLabelMismatchEmail per evitare che il messaggio di posta elettronica generato automaticamente quando viene registrato l'evento di controllo **Rilevata** mancata corrispondenza di riservatezza dei documenti.  Per ulteriori informazioni, vedere [Auditing sensitivity label activities.](sensitivity-labels-teams-groups-sites.md#auditing-sensitivity-label-activities )
- [L'impostazione del contesto di](sensitivity-labels-teams-groups-sites.md#more-information-about-the-dependencies-for-the-authentication-context-option) autenticazione è ora completamente implementazione in anteprima per le etichette di riservatezza. Inoltre, questa configurazione è ora supportata da Microsoft Teams.
- I file etichettati e crittografati da un nome di principio del servizio (ad esempio Microsoft Cloud App Security) e quindi caricati in SharePoint e OneDrive possono ora essere aperti in Office per il web dopo aver abilitato le etichette di riservatezza per i file [Office in SharePoint e OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).
- [La creazione](sensitivity-labels-coauthoring.md) condivisa e il salvataggio automatico non sono più limitati ai tenant di test e ora sono supportati in produzione quando si utilizza la versione 2105: 18 giugno per Windows e versione 16.50+ per macOS. Tieni presente che questa funzionalità non è ancora supportata da iOS e Android e rimane in anteprima.

## <a name="may-2021"></a>Maggio 2021

### <a name="data-loss-prevention"></a>Prevenzione della perdita di dati

- Nuove indicazioni per la [pianificazione della strategia di prevenzione della perdita di](dlp-overview-plan-for-dlp.md) dati.

### <a name="retention-and-records-management"></a>Gestione della conservazione e dei record

- Se si rilascia un criterio di conservazione da un sito di SharePoint o da un account OneDrive, non è più necessario attendere il periodo di tolleranza di 30 giorni prima di poter eliminare il sito o l'account. Richiesta popolare dai clienti, questa modifica è ora completa per tutti i tenant.
- In **anteprima,** revisione dell'eliminazione in più fasi: un amministratore può [](disposition.md) ora aggiungere fino a cinque fasi consecutive di revisione dell'eliminazione per un'etichetta di conservazione e i revisori possono aggiungere altri utenti alla fase di revisione dell'eliminazione. È anche possibile personalizzare le notifiche e i promemoria tramite posta elettronica.

### <a name="sensitive-information-types"></a>Tipi di informazioni riservate

- Nuove informazioni aggiunte per facilitare la [modifica di un dizionario parole chiave.](sit-modify-keyword-dictionary.md)

### <a name="sensitivity-labels"></a>Etichette di riservatezza

- In anteprima, una nuova impostazione per **il** contesto di autenticazione è ora disponibile quando si configura un'etichetta di riservatezza per gruppi [e siti.](sensitivity-labels-teams-groups-sites.md) Questa opzione funziona in combinazione con i criteri di accesso condizionale di Azure AD per applicare condizioni più stringenti quando gli utenti accedono SharePoint siti a cui è applicata l'etichetta. Prima di configurare questa [impostazione,](sensitivity-labels-teams-groups-sites.md#more-information-about-the-dependencies-for-the-authentication-context-option) assicurati di leggere le dipendenze e le limitazioni.
- [I criteri di etichettatura](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange) automatica configurati solo per Exchange ora supportano  le etichette di riservatezza che applicano la crittografia con Consenti agli utenti di assegnare le autorizzazioni per le opzioni Non inoltrare o Encrypt-Only.
- [L'etichettatura](sensitivity-labels-office-apps.md#require-users-to-apply-a-label-to-their-email-and-documents) obbligatoria è ora disponibile in genere per tutte Office app, su tutte le piattaforme.

## <a name="april-2021"></a>Aprile 2021

### <a name="advanced-ediscovery"></a>Advanced eDiscovery

- [Limiti in Advanced eDiscovery](/microsoft-365/compliance/limits-ediscovery20#export-limits---final-export-out-of-review-set). Le organizzazioni possono ora esportare fino a 5 milioni di elementi o 500 MB, a seconda di quale sia il valore più piccolo, in una singola esportazione di elementi da un set di revisione.

### <a name="data-classification"></a>Classificazione dei dati

- [Attività di etichettatura disponibili in Esplora attività](/microsoft-365/compliance/data-classification-activity-explorer-available-events)

### <a name="data-connectors"></a>Connettori dati

- [Configurare un connettore per archiviare Cisco Jabber nei dati Oracle](/microsoft-365/compliance/archive-ciscojabberonoracle-data)
- [Configurare un connettore per archiviare Cisco Jabber nei dati PostgreSQL](/microsoft-365/compliance/archive-ciscojabberonpostgresql-data)

### <a name="data-loss-prevention"></a>Prevenzione della perdita di dati

- Nuovo argomento per [informazioni di riferimento sui suggerimenti per i criteri di prevenzione della perdita di dati](/microsoft-365/compliance/dlp-policy-tips-reference).
- Nuovo argomento per [Informazioni sulla prevenzione della perdita di dati](/microsoft-365/compliance/dlp-learn-about-dlp).
- Nuovo argomento per [Iniziare a usare il dashboard di](/microsoft-365/compliance/dlp-alerts-dashboard-get-started)avviso per la prevenzione della perdita di dati .

### <a name="retention-policies-and-retention-label-policies"></a>Criteri di conservazione e criteri di etichetta di conservazione

- La posizione Microsoft 365 Groups ora supporta l'applicazione delle impostazioni di conservazione solo alle cassette postali di Microsoft 365 o solo ai siti SharePoint connessi utilizzando il cmdlet [Set-RetentionCompliancePolicy di PowerShell](/powershell/module/exchange/set-retentioncompliancepolicy) con il parametro *Applications.*

### <a name="sensitivity-labels"></a>Etichette di riservatezza

Outlook e aggiornamenti:

- [Impostazioni diverse per l'etichetta predefinita e](sensitivity-labels-office-apps.md#outlook-specific-options-for-default-label-and-mandatory-labeling) l'etichettatura obbligatoria sono ora supportate per l'etichettatura predefinita. In precedenza, queste impostazioni erano supportate solo dal client di etichettatura unificato AIP.
- [Encrypt-Only](encryption-sensitivity-labels.md#let-users-assign-permissions) è ora supportato da macOS, iOS e Android.
- [L'etichettatura](sensitivity-labels-office-apps.md#require-users-to-apply-a-label-to-their-email-and-documents) obbligatoria è in distribuzione nelle piattaforme rimanenti.
- [I contrassegni dinamici con tutte le variabili](sensitivity-labels-office-apps.md#dynamic-markings-with-variables) sono supportati in tutti Outlook client.

## <a name="march-2021"></a>Marzo 2021

Ecco alcune delle modifiche apportate alle soluzioni Microsoft 365 conformità e al contenuto per il mese di marzo.

### <a name="advanced-ediscovery"></a>Advanced eDiscovery

- **Advanced eDiscovery raccolte ora** supporta il nuovo strumento [di raccolta e flusso di lavoro.](/microsoft-365/compliance/collections-overview) Altri nuovi argomenti includono [la creazione di una bozza di](/microsoft-365/compliance/create-draft-collection)raccolta, il commit di una bozza di raccolta in un insieme [di](/microsoft-365/compliance/commit-draft-collection)revisione e le statistiche e i report [di raccolta.](/microsoft-365/compliance/collection-statistics-reports)
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
- [Creare notifiche per attività di corrispondenza esatta dei dati](/microsoft-365/compliance/sit-edm-notifications-activities)
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

- [Informazioni su Endpoint DLP](/microsoft-365/compliance/endpoint-dlp-learn-about)
- [Inviare notifiche di posta elettronica e visualizzare i suggerimenti per i criteri di prevenzione della perdita dei dati](/microsoft-365/compliance/use-notifications-and-policy-tips)
- [Informazioni sullo scanner locale Microsoft 365 prevenzione della perdita di dati](/microsoft-365/compliance/dlp-on-premises-scanner-learn)
- [Introduzione allo scanner locale per la prevenzione della perdita di dati](/microsoft-365/compliance/dlp-on-premises-scanner-get-started)
- [Creare criteri di prevenzione della perdita dei dati per proteggere i documenti con FCI o altre proprietà](/microsoft-365/compliance/protect-documents-that-have-fci-or-other-properties)
- [Uso della prevenzione della perdita di dati degli endpoint](/microsoft-365/compliance/endpoint-dlp-using)
- [Introduzione alla prevenzione della perdita di dati degli endpoint](/microsoft-365/compliance/endpoint-dlp-getting-started)

### <a name="ediscovery"></a>eDiscovery

Il contenuto è stato aggiunto o aggiornato negli argomenti seguenti:

- [Decrittografia in Microsoft 365 eDiscovery](/microsoft-365/compliance/ediscovery-decryption)
- [Query con parole chiave e condizioni di ricerca](/microsoft-365/compliance/keyword-queries-and-search-conditions#limitations-for-searching-sensitive-data-types)
- [Ritiro del modulo Pertinenza in Advanced eDiscovery](/microsoft-365/compliance/relevance-module-retirement)
- [Utilizzare uno script per aggiungere utenti a un'esenzione in un caso di eDiscovery di base](/microsoft-365/compliance/use-a-script-to-add-users-to-a-hold-in-ediscovery)

### <a name="encryption"></a>Crittografia

Il contenuto è stato aggiunto o aggiornato negli argomenti seguenti:

#### <a name="azure-rights-management-service-rms"></a>Azure Rights Management Service (RMS)

- [Funzionalità di crittografia gestite dai clienti](/microsoft-365/compliance/office-365-customer-managed-encryption-features)
- [Exchange Online della posta elettronica con AD RMS](/microsoft-365/compliance/information-rights-management-in-exchange-online). Il supporto per questo servizio è deprecato. Non è più possibile utilizzare AD RMS in un ambiente Exchange ibrido. Eseguire invece la migrazione ad Azure RMS.

#### <a name="customer-key"></a>Customer Key

- [Customer Key per Microsoft 365 a livello di tenant](/microsoft-365/compliance/customer-key-tenant-level)
- [Panoramica di sicurezza e conformità](/microsoftteams/security-compliance-overview)

#### <a name="information-rights-management-irm"></a>Information Rights Management (IRM)

- [Applicare Information Rights Management (IRM) a un elenco o a una raccolta.](/microsoft-365/compliance/configure-irm-to-use-an-on-premises-ad-rms-server) Questi cloud nazionali non supportano questa impostazione:
  - Microsoft Cloud for US Government
  - Microsoft Cloud Germania
  - Azure e Microsoft 365 gestiti da 21Vianet in Cina)
- [Configurare IRM per l'utilizzo di un server AD RMS locale.](/microsoft-365/compliance/configure-irm-to-use-an-on-premises-ad-rms-server) Il supporto per questo servizio in un ambiente Exchange ibrido è deprecato.

### <a name="sensitive-information-types"></a>Tipi di informazioni riservate

Il contenuto è stato aggiunto o aggiornato negli argomenti seguenti:

- [Informazioni sui tipi di informazioni riservate](/microsoft-365/compliance/sensitive-information-type-learn-about)
- [Creare un tipo di informazione riservata personalizzata usando PowerShell](/microsoft-365/compliance/create-a-custom-sensitive-information-type-in-scc-powershell)
- [Creare tipi di informazioni riservate personalizzati con classificazione basata su Corrispondenza esatta dati](/microsoft-365/compliance/create-custom-sensitive-information-types-with-exact-data-match-based-classification)
- [Definizioni delle entità tipo di informazioni sensibili](/microsoft-365/compliance/sensitive-information-type-entity-definitions)

### <a name="sensitivity-labels"></a>Etichette di riservatezza

Il contenuto è stato aggiunto o aggiornato negli argomenti seguenti:

- **SharePoint condivisione esterna**. Per [le etichette contenitore,](sensitivity-labels-teams-groups-sites.md) l'opzione per la condivisione esterna SharePoint siti viene ora rilasciata come disponibile in genere. Inoltre, il interfaccia di amministrazione di Microsoft 365 e Planner ora supportano l'applicazione di queste etichette di riservatezza. 
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
