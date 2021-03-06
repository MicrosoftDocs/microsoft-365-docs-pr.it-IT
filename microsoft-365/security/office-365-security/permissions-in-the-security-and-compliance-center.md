---
title: Autorizzazioni - Centro sicurezza & conformità
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.AdminRoleGroups
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
description: Gli amministratori possono ottenere informazioni sulle autorizzazioni disponibili nel Centro sicurezza & conformità in Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a2be234805977dd1efce10032e36113a460f3d96
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769882"
---
# <a name="permissions-in-the-security--compliance-center"></a>Autorizzazioni nel Centro sicurezza e conformità

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Il Centro sicurezza & conformità consente di concedere autorizzazioni agli utenti che eseguono attività di conformità come la gestione dei dispositivi, la prevenzione della perdita dei dati, eDiscovery, la conservazione e così via. Queste persone possono eseguire solo le attività a cui si concede esplicitamente l'accesso. Per accedere al Centro sicurezza & conformità, gli utenti devono essere amministratori globali o membri di uno o più gruppi di ruoli & Centro sicurezza e conformità.

Le autorizzazioni nel Centro sicurezza & conformità si basano sul modello di autorizzazioni RBAC (Role-Based Access Control). RBAC è lo stesso modello di autorizzazioni utilizzato da Exchange, quindi se si ha familiarità con Exchange, concedere le autorizzazioni nel Centro sicurezza & conformità sarà molto simile. È importante ricordare, tuttavia, che i gruppi di ruoli Exchange e i gruppi di ruoli & centro conformità non condividono l'appartenenza o le autorizzazioni. Anche se entrambi dispongono di un gruppo di ruoli Gestione organizzazione, non sono uguali. Le autorizzazioni concesse e i membri dei gruppi di ruoli sono diversi. Di seguito è riportato un elenco di gruppi di ruoli & centro sicurezza e conformità.

![Pagina Autorizzazioni nel Centro sicurezza & conformità](../../media/992c20ca-e82e-497c-9c8d-6fab212deb80.png)

## <a name="relationship-of-members-roles-and-role-groups"></a>Relazione tra membri, ruoli e gruppi di ruoli

Un **ruolo** concede le autorizzazioni per eseguire un set di attività. ad esempio, il ruolo Gestione casi consente agli utenti di utilizzare i casi di eDiscovery.

Un **gruppo di ruoli** è un set di ruoli che consente agli utenti di eseguire il proprio lavoro nel Centro sicurezza & conformità. Ad esempio, il gruppo di ruoli Amministratore conformità include (tra gli altri ruoli) i ruoli per Gestione casi, Ricerca contenuto e Configurazione organizzazione (oltre ad altri) perché un amministratore di conformità avrà bisogno delle autorizzazioni per eseguire il proprio lavoro.

Il Centro sicurezza & conformità include gruppi di ruoli predefiniti per le attività e le funzioni più comuni a cui sarà necessario assegnare gli utenti. È consigliabile aggiungere semplicemente singoli utenti **come membri** ai gruppi di ruoli predefiniti.

![Diagramma che mostra la relazione tra gruppi di ruoli e ruoli e membri](../../media/2a16d200-968c-4755-98ec-f1862d58cb8b.png)

## <a name="role-groups-in-the-security--compliance-center"></a>Gruppi di ruoli nel Centro sicurezza & conformità

Nella tabella seguente sono elencati i gruppi di ruoli predefiniti disponibili nel Centro sicurezza & conformità e i ruoli assegnati ai gruppi di ruoli per impostazione predefinita. Per concedere autorizzazioni a un utente per eseguire un'attività di conformità, aggiungerle al gruppo di ruoli Centro sicurezza & conformità appropriato.

La gestione delle autorizzazioni nel Centro sicurezza & conformità consente solo agli utenti di accedere alle funzionalità di conformità disponibili all'interno del Centro sicurezza & conformità stesso. Se si desidera concedere autorizzazioni ad altre funzionalità di conformità non presenti nel Centro sicurezza e conformità di &, ad esempio le regole del flusso di posta di Exchange (note anche come regole di trasporto), è necessario utilizzare l'interfaccia di amministrazione di Exchange.

Per informazioni su come concedere l'accesso al Centro sicurezza & conformità, vedere [Give users access to Microsoft 365 Compliance admin center](grant-access-to-the-security-and-compliance-center.md).

> [!NOTE]
> Per visualizzare la **scheda** Autorizzazioni nel Centro sicurezza & conformità, è necessario essere un amministratore. In particolare, è necessario  essere assegnati al ruolo Gestione ruoli  e tale ruolo viene assegnato solo al gruppo di ruoli Gestione organizzazione nel Centro sicurezza & conformità per impostazione predefinita. Inoltre, il **ruolo Gestione ruoli** consente agli utenti di visualizzare, creare e modificare i gruppi di ruoli.

<br>

****

|Gruppo di ruoli|Descrizione|Ruoli predefiniti assegnati|
|---|---|---|
|**Conformità delle comunicazioni**|Fornisce l'autorizzazione a tutti i ruoli di conformità della comunicazione: amministratore, analista, investigatore e visualizzatore.|Gestione dei casi <p> Amministratore per la conformità delle comunicazioni <p> Analisi per la conformità delle comunicazioni <p> Gestione dei casi di conformità delle comunicazioni <p> Indagine per la conformità delle comunicazioni <p> Visualizzatore della conformità delle comunicazioni <p> Provider di feedback per la classificazione dei dati <p> View-Only case|
|**Amministratori di conformità delle comunicazioni**|Amministratori della conformità delle comunicazioni che possono creare/modificare criteri e definire impostazioni globali.|Amministratore per la conformità delle comunicazioni <p> Gestione dei casi di conformità delle comunicazioni|
|**Analisti della conformità delle comunicazioni**|Analisti della conformità delle comunicazioni in grado di analizzare le corrispondenze dei criteri, visualizzare i metadati dei messaggi ed eseguire azioni correttive.|Analisi per la conformità delle comunicazioni <p> Gestione dei casi di conformità delle comunicazioni|
|**Investigatori per la conformità delle comunicazioni**|Analisti della conformità delle comunicazioni che possono analizzare le corrispondenze dei criteri, visualizzare il contenuto dei messaggi ed eseguire azioni correttive.|Gestione dei casi <p> Analisi per la conformità delle comunicazioni <p> Gestione dei casi di conformità delle comunicazioni <p> Indagine per la conformità delle comunicazioni <p> Provider di feedback per la classificazione dei dati <p> View-Only case|
|**Visualizzatori di conformità delle comunicazioni**|Visualizzatore della conformità alle comunicazioni che può accedere ai report e ai widget disponibili.|Gestione dei casi di conformità delle comunicazioni <p> Visualizzatore della conformità delle comunicazioni|
|**Compliance Administrator**<sup>1</sup>|I membri possono gestire le impostazioni per la gestione dei dispositivi, la prevenzione della perdita dei dati, i report e l'archiviazione.|Gestione dei casi <p> Amministratore di conformità <p> Ricerca di conformità <p> Provider di feedback per la classificazione dei dati <p> Revisore feedback classificazione dati <p> Gestione dei dispositivi <p> Gestione dell'eliminazione <p> Gestione della conformità DLP <p> Hold <p> Gestione della conformità IB <p> Gestione avvisi <p> Configurazione organizzazione <p> RecordManagement <p> Gestione della conservazione <p> Log di audit di sola visualizzazione <p> View-Only case <p> View-Only gestione dei dispositivi <p> View-Only conformità DLP <p> View-Only gestione della conformità IB <p> View-Only gestire gli avvisi <p> Destinatari solo visualizzazione <p> View-Only Gestione record <p> View-Only gestione della conservazione|
|**Amministratore dei dati di conformità**|I membri possono gestire le impostazioni per la gestione dei dispositivi, la protezione dei dati, la prevenzione della perdita dei dati, i report e l'archiviazione.|Amministratore di conformità <p> Ricerca di conformità <p> Gestione dei dispositivi <p> Gestione della conformità DLP <p> Gestione dell'eliminazione <p> Gestione della conformità IB <p> Gestione avvisi <p> Configurazione organizzazione <p> RecordManagement <p> Gestione della conservazione <p> Amministratore etichette di riservatezza <p> Log di audit di sola visualizzazione <p> View-Only gestione dei dispositivi <p> View-Only conformità DLP <p> View-Only gestione della conformità IB <p> View-Only gestire gli avvisi <p> Destinatari solo visualizzazione <p> View-Only Gestione record <p> View-Only gestione della conservazione|
|**Amministratore di Compliance Manager**|Gestire la creazione e la modifica dei modelli.|Amministrazione di Compliance Manager <p> Valutazione di Compliance Manager <p> Contributo di Compliance Manager <p> Lettore di Compliance Manager|
|**Esperto di Compliance Manager**|Creare valutazioni, implementare azioni di miglioramento e aggiornare lo stato dei test per le azioni di miglioramento.|Valutazione di Compliance Manager <p> Contributo di Compliance Manager <p> Lettore di Compliance Manager|
|**Collaboratore di Compliance Manager**|Creare valutazioni ed eseguire operazioni per implementare azioni di miglioramento.|Contributo di Compliance Manager <p> Lettore di Compliance Manager|
|**Lettore di Compliance Manager**|Visualizzare tutto il contenuto di Compliance Manager ad eccezione delle funzioni di amministratore.|Lettore di Compliance Manager|
|**Visualizzatore contenuto di Esplora contenuto**|Visualizzare i file di contenuto in Esplora contenuto.|Visualizzatore contenuto classificazione dati|
|**Visualizzatore elenco Esplora contenuto**|Visualizzare tutti gli elementi in Esplora contenuto solo in formato elenco.|Visualizzatore elenco classificazione dati|
|**Gestore di eDiscovery**|I membri possono eseguire ricerche e inserire blocchi nelle cassette postali, SharePoint siti online e OneDrive for Business posizioni. I membri possono inoltre creare e gestire casi di eDiscovery, aggiungere e rimuovere membri a un caso, creare e modificare ricerche contenuto associate a un caso e accedere ai dati del caso in Advanced eDiscovery. <p> Un amministratore di eDiscovery è un membro del gruppo di ruoli Manager eDiscovery a cui sono state assegnate autorizzazioni aggiuntive. Oltre alle attività che un responsabile di eDiscovery può eseguire, un amministratore di eDiscovery può:<ul><li>Visualizzare tutti i casi di eDiscovery nell'organizzazione.</li><li>Gestire ogni caso di eDiscovery dopo essersi aggiunto come membro di tale caso.</li></ul> <p> La differenza principale tra un responsabile di eDiscovery e un amministratore di eDiscovery è che un amministratore di eDiscovery può accedere a tutti i casi elencati nella pagina casi **di eDiscovery** nel Centro sicurezza & conformità. Un manager di eDiscovery può accedere solo ai casi creati o ai casi di cui è membro. Per ulteriori informazioni su come impostare un utente come amministratore di eDiscovery, vedere [Assign eDiscovery permissions in the Security & Compliance Center.](../../compliance/assign-ediscovery-permissions.md)|Gestione dei casi <p> Comunicazione <p> Ricerca di conformità <p> Custode <p> Esporta <p> Hold <p> Anteprima <p> Revisione <p> Decrittografia RMS|
|**Lettore globale**|I membri hanno accesso in sola lettura a report, avvisi e possono visualizzare tutte le impostazioni e la configurazione.<p> La differenza principale tra lettore globale e lettore di sicurezza è che un lettore globale può accedere alla **configurazione e alle impostazioni**.|Ruolo con autorizzazioni di lettura per la sicurezza <p> Lettore etichette di riservatezza <p> Visualizzazione Garanzia del servizio <p> Log di audit di sola visualizzazione <p> View-Only gestione dei dispositivi <p> View-Only conformità DLP <p> View-Only gestione della conformità IB <p> View-Only gestire gli avvisi <p> Destinatari solo visualizzazione <p> View-Only Gestione record <p> View-Only gestione della conservazione|
|**Insider Risk Management**|Usare questo gruppo di ruoli per la gestione dei rischi Insider per la propria organizzazione in un unico gruppo. Aggiungendo tutti gli account utente per amministratori, analisti e investigatori designati, è possibile configurare autorizzazioni per la gestione dei rischi Insider in unico gruppo. Questo gruppo di ruoli contiene tutti i ruoli di autorizzazione per la gestione dei rischi Insider. Si tratta del modo più semplice per iniziare rapidamente la gestione dei rischi Insider ed è adatto per le organizzazioni che non necessitano di autorizzazioni separate definite per gruppi separati di utenti.|Gestione dei casi <p> Insider Risk Management Admin <p> Analisi della gestione dei rischi Insider <p> Indagine insider sulla gestione dei rischi <p> View-Only case|
|**Insider Risk Management Admins**|Utilizzare questo gruppo di ruoli per configurare inizialmente la gestione dei rischi insider e successivamente per separare gli amministratori dei rischi insider in un gruppo definito. Gli utenti di questo gruppo di ruoli possono creare, leggere, aggiornare ed eliminare criteri di gestione dei rischi Insider, impostazioni globali e assegnazioni del gruppo di ruoli.|Gestione dei casi <p> Insider Risk Management Admin <p> View-Only case|
|**Analisti gestione dei rischi Insider**|Usare questo gruppo per assegnare le autorizzazioni agli utenti che fungeranno da analisti di casi di rischio Insider. Gli utenti di questo gruppo di ruoli possono accedere a tutti gli avvisi, casi e modelli di notifiche per la gestione dei rischi Insider. Non possono accedere a Esplora contenuto del rischio Insider.|Gestione dei casi <p> Analisi della gestione dei rischi Insider <p> View-Only case|
|**Revisori della gestione dei rischi insider**|Utilizzare questo gruppo per assegnare autorizzazioni agli utenti che controllano le attività di gestione dei rischi insider. Gli utenti di questo gruppo di ruoli possono accedere al log di controllo dei rischi insider.|Insider Risk Management Audit|
|**Investigatori gestione dei rischi Insider**|Usare questo gruppo per assegnare le autorizzazioni agli utenti che fungeranno da investigatori dei dati relativi al rischio Insider. Gli utenti di questo gruppo di ruoli possono accedere a tutti gli avvisi, casi, modelli di notifiche e Esplora contenuto per tutti i casi.|Gestione dei casi <p> Indagine insider sulla gestione dei rischi <p> View-Only case|
|**Collaboratori IRM**|Questo gruppo di ruoli è visibile, ma viene utilizzato solo dai servizi in background.|Insider Risk Management Contributo permanente <p> Insider Risk Management Contributo temporaneo|
|**Amministratore MailFlow**|I membri possono monitorare e visualizzare informazioni dettagliate e report sul flusso di posta nel Centro sicurezza & conformità. Gli amministratori globali possono aggiungere utenti ordinari a questo gruppo, ma, se l'utente non è un membro del gruppo di amministratori di Exchange, l'utente non avrà accesso Exchange attività correlate all'amministratore.|Destinatari solo visualizzazione|
|**Gestione organizzazione**<sup>1</sup>|I membri possono controllare le autorizzazioni per l'accesso alle funzionalità nel Centro sicurezza & conformità e anche gestire le impostazioni per la gestione dei dispositivi, la prevenzione della perdita dei dati, i report e la conservazione. <p> Gli utenti che non sono amministratori globali devono essere amministratori Exchange per visualizzare ed eseguire azioni sui dispositivi gestiti da Dispositivi mobili e sicurezza di base per Microsoft 365 (in precedenza noto come Gestione di dispositivi mobili o MDM). <p> Gli amministratori globali vengono aggiunti automaticamente come membri di questo gruppo di ruoli.|Log di audit <p> Gestione dei casi <p> Amministratore di conformità <p> Ricerca di conformità <p> Gestione dei dispositivi <p> Gestione della conformità DLP <p> Hold <p> Gestione della conformità IB <p> Gestione avvisi <p> Configurazione organizzazione <p> Quarantena <p> RecordManagement <p> Gestione della conservazione <p> Gestione ruoli <p> Ricerca ed eliminazione <p> Amministratore della sicurezza <p> Ruolo con autorizzazioni di lettura per la sicurezza <p> Amministratore etichette di riservatezza <p> Lettore etichette di riservatezza <p> Visualizzazione Garanzia del servizio <p> Collaboratore tag <p> Tag Manager <p> Lettore tag <p> Log di audit di sola visualizzazione <p> View-Only gestione dei dispositivi <p> View-Only conformità DLP <p> View-Only gestione della conformità IB <p> View-Only case <p> View-Only gestire gli avvisi <p> Destinatari solo visualizzazione <p> View-Only Gestione record <p> View-Only gestione della conservazione|
|**Amministratore quarantena**|I membri possono accedere a tutte le azioni di quarantena. Per ulteriori informazioni, vedere [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md)|Quarantena|
|**Gestione record**|I membri possono configurare tutti gli aspetti della gestione dei record, incluse le etichette di conservazione e le revisioni dell'eliminazione.|Gestione dell'eliminazione <p> RecordManagement <p> Gestione della conservazione|
|**Reviewer**|I membri possono accedere ai set [di Advanced eDiscovery](../../compliance/overview-ediscovery-20.md) casi. I membri di questo gruppo di ruoli possono visualizzare e aprire l'elenco dei casi nella pagina **eDiscovery > Advanced** nel Centro conformità Microsoft 365 di cui sono membri. Dopo che l'utente accede a Advanced eDiscovery caso, può selezionare **Rivedi set per** accedere ai dati del caso. Questo ruolo non consente all'utente di visualizzare in anteprima i risultati di una ricerca di raccolta associata al caso o di eseguire altre attività di ricerca o gestione dei casi. I membri di questo gruppo di ruoli possono accedere solo ai dati di un set di revisione.|Revisione|
|**Amministratore della sicurezza**|I membri hanno accesso a una serie di funzionalità di sicurezza di Identity Protection Center, Privileged Identity Management, Monitor Microsoft 365 Service Health e Security & Compliance Center. <p> Per impostazione predefinita, questo gruppo di ruoli potrebbe non avere membri. Tuttavia, il ruolo amministratore della sicurezza Azure Active Directory assegnato a questo gruppo di ruoli. Di conseguenza, questo gruppo di ruoli eredita le funzionalità e l'appartenenza al ruolo Amministratore sicurezza da Azure Active Directory. <p> Per gestire le autorizzazioni centralmente, aggiungere e rimuovere i membri del gruppo nell'interfaccia Azure Active Directory di amministrazione. Per ulteriori informazioni, vedere [Autorizzazioni del ruolo amministratore in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles). Se si modifica questo gruppo di ruoli nel Centro sicurezza & conformità (appartenenza o ruoli), tali modifiche si applicano solo al Centro sicurezza & conformità e non ad altri servizi. <p> Questo gruppo di ruoli include tutte le autorizzazioni di sola lettura del ruolo Lettore sicurezza, oltre a una serie di autorizzazioni amministrative aggiuntive per gli stessi servizi: Azure Information Protection, Identity Protection Center, Privileged Identity Management, Monitor Microsoft 365 Service Health e Security & Compliance Center.|Log di audit <p> Gestione dei dispositivi <p> Gestione della conformità DLP <p> Gestione della conformità IB <p> Gestione avvisi <p> Quarantena <p> Amministratore della sicurezza <p> Amministratore etichette di riservatezza <p> Collaboratore tag <p> Tag Manager <p> Lettore tag <p> Log di audit di sola visualizzazione <p> View-Only gestione dei dispositivi <p> View-Only conformità DLP <p> View-Only gestione della conformità IB <p> View-Only gestire gli avvisi|
|**Operatore sicurezza**|I membri possono gestire gli avvisi di sicurezza e visualizzare report e impostazioni delle funzionalità di sicurezza.|Ricerca di conformità <p> Gestione avvisi <p> Ruolo con autorizzazioni di lettura per la sicurezza <p> Collaboratore tag <p> Lettore tag <p> Log di audit di sola visualizzazione <p> View-Only gestione dei dispositivi <p> View-Only conformità DLP <p> View-Only gestione della conformità IB <p> View-Only gestire gli avvisi|
|**Lettore sicurezza**|I membri hanno accesso in sola lettura a diverse funzionalità di sicurezza di Identity Protection Center, Privileged Identity Management, Monitor Microsoft 365 Service Health e Security & Compliance Center. <p> Per impostazione predefinita, questo gruppo di ruoli potrebbe non avere membri. Tuttavia, il ruolo Lettore di sicurezza Azure Active Directory viene assegnato a questo gruppo di ruoli. Di conseguenza, questo gruppo di ruoli eredita le funzionalità e l'appartenenza al ruolo Lettore di sicurezza da Azure Active Directory. <p> Per gestire le autorizzazioni centralmente, aggiungere e rimuovere i membri del gruppo nell'interfaccia Azure Active Directory di amministrazione. Per ulteriori informazioni, vedere [Autorizzazioni del ruolo amministratore in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles). Se si modifica questo gruppo di ruoli nel Centro sicurezza & conformità (appartenenza o ruoli), tali modifiche si applicano solo al Centro sicurezza & conformità e non ad altri servizi.|Ruolo con autorizzazioni di lettura per la sicurezza <p> Lettore etichette di riservatezza <p> Lettore tag <p> View-Only gestione dei dispositivi <p> View-Only conformità DLP <p> View-Only gestione della conformità IB <p> View-Only gestire gli avvisi|
|**Utente service assurance**|I membri possono accedere alla sezione Garanzia del servizio nel Centro sicurezza & conformità. Il servizio di garanzia fornisce report e documenti che descrivono le procedure di sicurezza di Microsoft per i dati dei clienti archiviati in Microsoft 365. Fornisce inoltre report di controllo indipendenti di terze parti Microsoft 365. Per ulteriori informazioni, vedere [Service assurance in the Security & Compliance Center.](../../compliance/service-assurance.md)|Visualizzazione Garanzia del servizio|
|**Revisione di supervisione**|I membri possono creare e gestire i criteri che definiscono quali comunicazioni sono soggette a revisione in un'organizzazione. Per ulteriori informazioni, vedere [Configure communication compliance policies for your organization](../../compliance/communication-compliance-configure.md).|Supervisory Review Administrator|
|

> [!NOTE]
> <sup>1</sup> Questo gruppo di ruoli non assegna ai membri le autorizzazioni necessarie per eseguire ricerche nel log di controllo o per utilizzare report che potrebbero includere dati di Exchange, ad esempio DLP o Defender per i report Office 365. Per eseguire ricerche nel log di controllo o per visualizzare tutti i report, a un utente devono essere assegnate le autorizzazioni in Exchange Online. Ciò avviene perché il cmdlet sottostante usato per la ricerca nel log di controllo è un cmdlet di Exchange Online. Gli amministratori globali possono eseguire ricerche nel log di controllo e visualizzare tutti i report perché vengono aggiunti automaticamente come membri del gruppo di ruoli Gestione organizzazione in Exchange Online. Per ulteriori informazioni, vedere [Search the audit log in the Security & Compliance Center.](../../compliance/search-the-audit-log-in-security-and-compliance.md)

## <a name="roles-in-the-security--compliance-center"></a>Ruoli nel Centro sicurezza & conformità

Nella tabella seguente sono elencati i ruoli disponibili e i gruppi di ruoli a cui sono assegnati per impostazione predefinita.

Si noti che i ruoli seguenti non vengono assegnati al gruppo di ruoli Gestione organizzazione per impostazione predefinita:

- Amministratore simulatore di attacco
- Autore payload simulatore di attacco
- Comunicazione
- Amministratore per la conformità delle comunicazioni
- Analisi per la conformità delle comunicazioni
- Gestione dei casi di conformità delle comunicazioni
- Indagine per la conformità delle comunicazioni
- Visualizzatore della conformità delle comunicazioni
- Amministrazione di Compliance Manager
- Valutazione di Compliance Manager
- Contributo di Compliance Manager
- Lettore di Compliance Manager
- Custode
- Visualizzatore contenuto classificazione dati
- Provider di feedback per la classificazione dei dati
- Revisore feedback classificazione dati
- Visualizzatore elenco classificazione dati
- Gestione dell'eliminazione
- Esporta
- Insider Risk Management Admin
- Analisi della gestione dei rischi Insider
- Insider Risk Management Audit
- Indagine insider sulla gestione dei rischi
- Insider Risk Management Contributo permanente
- Insider Risk Management Contributo temporaneo
- Anteprima
- Revisione
- Decrittografia RMS
- Supervisory Review Administrator

<br>

****

|Ruolo|Descrizione|Assegnazioni predefinite del gruppo di ruoli|
|---|---|---|
|**Amministratore simulatore di attacco**|Usato per creare e gestire tutti gli aspetti delle campagne di simulazione degli attacchi.||
|**Autore payload simulatore di attacco**|Usato per creare e gestire payload di attacco che possono essere distribuiti dall'amministratore del simulatore di attacco.||
|**Log di audit**|Attivare e configurare il controllo per l'organizzazione, visualizzare i report di controllo dell'organizzazione e quindi esportare tali report in un file.|Gestione dell'organizzazione <p> Amministratore della sicurezza|
|**Gestione dei casi**|Creare, modificare, eliminare e controllare l'accesso ai casi di eDiscovery.|Conformità delle comunicazioni <p> Investigatori per la conformità delle comunicazioni <p> Amministratore di conformità <p>Gestione di eDiscovery <p> Gestione dei rischi Insider <p> Insider Risk Management Admins <p> Insider Risk Management Analysts <p> Insider Risk Management Investigators <p> Gestione dell'organizzazione|
|**Comunicazione**|Gestire tutte le comunicazioni con i custodi identificati in un Advanced eDiscovery caso.  Crea notifiche di blocco, promemoria di blocco e escalation alla gestione. Tenere traccia del riconoscimento del responsabile delle notifiche di blocco e gestire l'accesso al portale del responsabile utilizzato da ogni responsabile in un caso per tenere traccia delle comunicazioni per i casi in cui sono state identificate come depositario.|Gestione di eDiscovery|
|**Amministratore per la conformità delle comunicazioni**|Usato per gestire i criteri nella funzionalità Conformità comunicazioni.|Conformità delle comunicazioni <p> Amministratori di conformità delle comunicazioni|
|**Analisi per la conformità delle comunicazioni**|Usato per eseguire indagini, correzione delle violazioni dei messaggi nella funzionalità Conformità comunicazione. Può visualizzare solo i metadati del messaggio.|Conformità delle comunicazioni <p> Analisti della conformità delle comunicazioni <p> Investigatori per la conformità delle comunicazioni|
|**Gestione dei casi di conformità delle comunicazioni**|Usato per accedere ai casi di conformità delle comunicazioni.|Conformità delle comunicazioni <p> Amministratori di conformità delle comunicazioni <p> Analisti della conformità delle comunicazioni <p> Investigatori per la conformità delle comunicazioni <p> Visualizzatori di conformità delle comunicazioni|
|**Indagine per la conformità delle comunicazioni**|Usato per eseguire indagini, correzioni ed esaminare le violazioni dei messaggi nella funzionalità Conformità comunicazione. Può visualizzare i metadati del messaggio e il messaggio.|Conformità delle comunicazioni <p> Investigatori per la conformità delle comunicazioni|
|**Visualizzatore della conformità delle comunicazioni**|Usato per accedere a report e widget nella funzionalità Conformità comunicazioni.|Conformità delle comunicazioni <p> Visualizzatori di conformità delle comunicazioni|
|**Amministratore conformità**|Visualizzare e modificare le impostazioni e i report per le funzionalità di conformità.|Amministratore di conformità <p> Amministratore dei dati di conformità <p> Gestione dell'organizzazione|
|**Amministrazione di Compliance Manager**|Gestire la creazione e la modifica dei modelli.|Amministratore di Compliance Manager|
|**Valutazione di Compliance Manager**|Creare valutazioni, implementare azioni di miglioramento e aggiornare lo stato dei test per le azioni di miglioramento.|Amministratore di Compliance Manager <p> Esperto di Compliance Manager|
|**Contributo di Compliance Manager**|Creare valutazioni ed eseguire operazioni per implementare azioni di miglioramento.|Amministratore di Compliance Manager <p> Esperto di Compliance Manager <p> Collaboratore di Compliance Manager|
|**Compliance Manager - Lettore**|Visualizzare tutto il contenuto di Compliance Manager ad eccezione delle funzioni di amministratore.|Amministratore di Compliance Manager <p> Esperto di Compliance Manager <p> Collaboratore di Compliance Manager <p> Lettore di Compliance Manager|
|**Ricerca di conformità**|Eseguire ricerche tra le cassette postali e ottenere una stima dei risultati.|Amministratore di conformità <p> Amministratore dei dati di conformità <p>Gestione di eDiscovery <p> Gestione dell'organizzazione <p> Operatore della sicurezza|
|**Custode**|Identificare e gestire i custodi per Advanced eDiscovery casi e usare le informazioni di Azure Active Directory e altre origini per trovare le origini dati associate ai depositati. Associare altre origini dati, ad esempio cassette postali, SharePoint siti e Teams ai custodi in un caso.  Conservare legalmente le origini dati associate ai custodi per conservare il contenuto nel contesto di un caso.|Gestione di eDiscovery|
|**Visualizzatore contenuto classificazione dati**|Visualizzare il rendering sul posto dei file in Esplora contenuto.|Visualizzatore contenuto di Esplora contenuto|
|**Provider di feedback per la classificazione dei dati**|Consente di fornire feedback ai classificatori in Esplora contenuto.|Conformità delle comunicazioni <p> Investigatori per la conformità delle comunicazioni <p> Amministratore di conformità|
|**Revisore feedback classificazione dati**|Consente di esaminare il feedback dei classificatori in Esplora feedback.|Amministratore di conformità|
|**Visualizzatore elenco classificazione dati**|Visualizzare l'elenco dei file in Esplora contenuto.|Visualizzatore elenco Esplora contenuto|
|**Gestione dispositivi**|Visualizzare e modificare le impostazioni e i report per le funzionalità di gestione dei dispositivi.|Amministratore di conformità <p> Amministratore dei dati di conformità <p> Gestione dell'organizzazione <p> Amministratore della sicurezza|
|**Gestione dell'eliminazione**|Controllare le autorizzazioni per l'accesso all'eliminazione manuale nel Centro sicurezza & conformità.|Amministratore di conformità <p> Amministratore dei dati di conformità <p> Gestione record|
|**Gestione della conformità DLP**|Visualizzare e modificare le impostazioni e i report per i criteri di prevenzione della perdita dei dati (DLP).|Amministratore di conformità <p> Amministratore dei dati di conformità <p> Gestione dell'organizzazione <p> Amministratore della sicurezza|
|**Esportare**|Esportare il contenuto della cassetta postale e del sito restituito dalle ricerche.|Gestione di eDiscovery|
|**Blocco**|Mettere in attesa il contenuto nelle cassette postali, nei siti e nelle cartelle pubbliche. Quando è in attesa, una copia del contenuto viene archiviata in una posizione sicura. I proprietari del contenuto potranno comunque modificare o eliminare il contenuto originale.|Amministratore di conformità <p>Gestione di eDiscovery <p> Gestione dell'organizzazione|
|**Gestione della conformità IB**|Visualizzare, creare, rimuovere, modificare e testare i criteri information barrier.|Amministratore di conformità <p> Amministratore dei dati di conformità <p> Gestione dell'organizzazione <p> Amministratore della sicurezza|
|**Insider Risk Management Admin**|Crea, modifica, elimina e controlla l'accesso alla funzionalità Insider Risk Management.|Gestione dei rischi Insider <p> Insider Risk Management Admins|
|**Analisi della gestione dei rischi Insider**|Accedere a tutti i modelli di avvisi, casi e avvisi per la gestione dei rischi insider.|Gestione dei rischi Insider <p> Insider Risk Management Analysts|
|**Insider Risk Management Audit**|Consentire la visualizzazione degli audit trail dei rischi Insider.|Revisori della gestione dei rischi insider|
|**Indagine insider sulla gestione dei rischi**|Accedere a tutti gli avvisi, i casi, i modelli di avvisi e Esplora contenuto per tutti i casi.|Gestione dei rischi Insider <p> Insider Risk Management Investigators|
|**Insider Risk Management Contributo permanente**|Questo gruppo di ruoli è visibile, ma viene utilizzato solo dai servizi in background.|Collaboratori IRM|
|**Insider Risk Management Contributo temporaneo**|Questo gruppo di ruoli è visibile, ma viene utilizzato solo dai servizi in background.|Collaboratori IRM|
|**Gestire gli avvisi**|Consente di visualizzare e modificare le impostazioni e i report per gli avvisi.|Amministratore di conformità <p> Amministratore dei dati di conformità <p> Gestione dell'organizzazione <p> Amministratore della sicurezza <p> Operatore della sicurezza|
|**Configurazione organizzazione**|Eseguire, visualizzare ed esportare report di controllo e gestire i criteri di conformità per DLP, dispositivi e conservazione.|Amministratore di conformità <p> Amministratore dei dati di conformità <p> Gestione dell'organizzazione|
|**Anteprima**|Visualizzare un elenco di elementi restituiti dalle ricerche di contenuto e aprire ogni elemento dall'elenco per visualizzarne il contenuto.|Gestione di eDiscovery|
|**Quarantena**|Consente la visualizzazione e il rilascio della posta elettronica in quarantena.|Amministratore quarantena <p> Amministratore della sicurezza <p> Gestione dell'organizzazione|
|**RecordManagement**|Visualizzare e modificare la configurazione della funzionalità di gestione dei record.|Amministratore di conformità <p> Amministratore dei dati di conformità <p> Gestione dell'organizzazione <p> Gestione record|
|**Gestione della conservazione**|Gestire i criteri di conservazione, le etichette di conservazione e i criteri delle etichette di conservazione.|Amministratore di conformità <p> Amministratore dei dati di conformità <p> Gestione dell'organizzazione <p> Gestione record|
|**Verifica**|Questo ruolo consente agli utenti di accedere ai set di revisione Advanced eDiscovery casi. Gli utenti assegnati a questo ruolo possono visualizzare e aprire l'elenco dei casi nella pagina **eDiscovery > Advanced** nel Centro conformità Microsoft 365 di cui sono membri. Dopo che l'utente accede a Advanced eDiscovery caso, può selezionare **Rivedi set per** accedere ai dati del caso. Questo ruolo non consente all'utente di visualizzare in anteprima i risultati di una ricerca di raccolta associata al caso o di eseguire altre attività di ricerca o gestione dei casi. Gli utenti con questo ruolo possono accedere solo ai dati in un set di revisione.|Gestione di eDiscovery <p> Reviewer|
|**Decrittografia RMS**|Decrittografare il contenuto protetto con RMS durante l'esportazione dei risultati della ricerca.|Gestione di eDiscovery|
|**Gestione ruoli**|Gestire l'appartenenza ai gruppi di ruoli e creare o eliminare gruppi di ruoli personalizzati.|Gestione dell'organizzazione|
|**Ricerca ed eliminazione**|Consente agli utenti di rimuovere in blocco i dati che corrispondono ai criteri di una ricerca di contenuto.|Gestione dell'organizzazione|
|**Amministratore della sicurezza**|Visualizzare e modificare la configurazione e i report per le funzionalità di sicurezza.|Gestione dell'organizzazione <p> Amministratore della sicurezza|
|**Lettore sicurezza**|Visualizzare la configurazione e i report per le funzionalità di sicurezza.|Lettore globale <p> Gestione dell'organizzazione <p> Operatore della sicurezza <p> Ruolo con autorizzazioni di lettura per la sicurezza|
|**Amministratore etichette di riservatezza**|Consente di visualizzare, creare, modificare e rimuovere etichette di riservatezza.|Amministratore dei dati di conformità <p> Gestione dell'organizzazione <p> Amministratore della sicurezza|
|**Lettore etichette di riservatezza**|Visualizzare la configurazione e l'utilizzo delle etichette di riservatezza.|Lettore globale <p> Gestione dell'organizzazione <p> Ruolo con autorizzazioni di lettura per la sicurezza|
|**Visualizzazione Garanzia del servizio**|Scaricare i documenti disponibili dalla sezione Service Assurance. Il contenuto include il controllo indipendente, la documentazione di conformità e le indicazioni relative all'attendibilità per l'utilizzo delle funzionalità Microsoft 365 per gestire la conformità normativa e i rischi per la sicurezza.|Lettore globale <p> Gestione dell'organizzazione <p> Utente service assurance|
|**Supervisory Review Administrator**|Gestire i criteri di revisione, incluse le comunicazioni da rivedere e gli utenti che devono eseguire la revisione.|Revisione di supervisione|
|**Collaboratore tag**|Visualizzare e aggiornare l'appartenenza ai tag utente esistenti.|Gestione dell'organizzazione <p> Amministratore della sicurezza <p> Operatore della sicurezza|
|**Tag Manager**|Visualizzare, aggiornare, creare ed eliminare tag utente.|Gestione dell'organizzazione <p> Amministratore della sicurezza|
|**Lettore tag**|Accesso in sola lettura ai tag utente esistenti.|Ruolo con autorizzazioni di lettura per la sicurezza|
|**Log di audit di sola visualizzazione**|Visualizzare ed esportare report di controllo. Poiché questi report potrebbero contenere informazioni riservate, è consigliabile assegnare questo ruolo solo agli utenti con la necessità esplicita di visualizzare queste informazioni.|Amministratore di conformità <p> Amministratore dei dati di conformità <p> Lettore globale <p> Gestione dell'organizzazione <p> Amministratore della sicurezza <p> Operatore della sicurezza|
|**Caso di sola visualizzazione**||Conformità delle comunicazioni <p> Investigatori per la conformità delle comunicazioni <p> Amministratore di conformità <p> Gestione dei rischi Insider <p> Insider Risk Management Admins <p> Insider Risk Management Analysts <p> Insider RiskManagement Investigators <p> Gestione dell'organizzazione|
|**Gestione dispositivi di sola visualizzazione**|Visualizza la configurazione e i report per la funzionalità Gestione dispositivi.|Amministratore di conformità <p> Amministratore dei dati di conformità <p> Lettore globale <p> Gestione dell'organizzazione <p> Amministratore della sicurezza <p> Operatore della sicurezza <p> Ruolo con autorizzazioni di lettura per la sicurezza|
|**Gestione conformità DLP di sola visualizzazione**|Visualizzare le impostazioni e i report per i criteri di prevenzione della perdita dei dati (DLP).|Amministratore di conformità <p> Amministratore dei dati di conformità <p> Lettore globale <p> Gestione dell'organizzazione <p> Amministratore della sicurezza <p> Operatore della sicurezza <p> Ruolo con autorizzazioni di lettura per la sicurezza|
|**Gestione conformità IB di sola visualizzazione**|Visualizzare la configurazione e i report per la funzionalità Barriere informazioni.|Amministratore di conformità <p> Amministratore dei dati di conformità <p> Lettore globale <p> Gestione dell'organizzazione <p> Amministratore della sicurezza <p> Operatore della sicurezza <p> Ruolo con autorizzazioni di lettura per la sicurezza|
|**Gestire gli avvisi in sola visualizzazione**|Visualizzare la configurazione e i report per la funzionalità Gestisci avvisi.|Amministratore di conformità <p> Amministratore dei dati di conformità <p> Lettore globale <p> Gestione dell'organizzazione <p> Amministratore della sicurezza <p> Operatore della sicurezza <p> Ruolo con autorizzazioni di lettura per la sicurezza|
|**Destinatari solo visualizzazione**|Visualizzare informazioni su utenti e gruppi.|Amministratore di conformità <p> Amministratore dei dati di conformità <p> Lettore globale <p> Amministratore MailFlow <p> Gestione dell'organizzazione|
|**Gestione record di sola visualizzazione**|Visualizzare la configurazione della funzionalità di gestione dei record.|Amministratore di conformità <p> Amministratore dei dati di conformità <p> <p> Lettore globale <p> Gestione dell'organizzazione|
|**Gestione conservazione di sola visualizzazione**|Visualizzare la configurazione dei criteri di conservazione, delle etichette di conservazione e dei criteri delle etichette di conservazione.|Amministratore di conformità <p> Amministratore dei dati di conformità <p> Amministratore globale <p> Gestione dell'organizzazione|
|
