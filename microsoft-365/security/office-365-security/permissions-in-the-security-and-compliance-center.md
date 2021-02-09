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
ms.openlocfilehash: 316f5ea742684a18c6ab531843cc4fef85d74896
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150220"
---
# <a name="permissions-in-the-security--compliance-center"></a>Autorizzazioni nel Centro sicurezza e conformità

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender per Office 365 piano 1 e piano 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Il Centro sicurezza & conformità consente di concedere autorizzazioni agli utenti che eseguono attività di conformità come la gestione dei dispositivi, la prevenzione della perdita dei dati, eDiscovery, la conservazione e così via. Queste persone possono eseguire solo le attività a cui si concede esplicitamente l'accesso. Per accedere al Centro sicurezza & conformità, gli utenti devono essere amministratori globali o membri di uno o più gruppi di ruoli del Centro sicurezza & conformità.

Le autorizzazioni nel Centro sicurezza & conformità si basano sul modello delle autorizzazioni di controllo dell'accesso basato sui ruoli (RBAC). RBAC è lo stesso modello di autorizzazioni utilizzato da Exchange, quindi se si ha familiarità con Exchange, concedere le autorizzazioni nel Centro sicurezza & conformità sarà molto simile. È importante ricordare, tuttavia, che i gruppi di ruoli di Exchange e i gruppi di ruoli del Centro sicurezza & conformità non condividono l'appartenenza o le autorizzazioni. Anche se entrambi dispongono di un gruppo di ruoli Gestione organizzazione, non sono uguali. Le autorizzazioni che concedono e i membri dei gruppi di ruoli sono diverse. Di seguito è riportato un elenco & gruppi di ruoli del Centro sicurezza e conformità.

![Pagina Autorizzazioni nel Centro sicurezza & conformità](../../media/992c20ca-e82e-497c-9c8d-6fab212deb80.png)

## <a name="relationship-of-members-roles-and-role-groups"></a>Relazione tra membri, ruoli e gruppi di ruoli

Un **ruolo** concede le autorizzazioni per eseguire un set di attività; Ad esempio, il ruolo Gestione casi consente agli utenti di lavorare con i casi di eDiscovery.

Un **gruppo di ruoli** è un set di ruoli che consente agli utenti di eseguire il proprio lavoro nel Centro sicurezza & conformità. Ad esempio, il gruppo di ruoli Amministratore conformità include (tra gli altri ruoli) i ruoli per Gestione casi, Ricerca contenuto e Configurazione organizzazione (oltre ad altri) perché un utente che è un amministratore di conformità avrà bisogno delle autorizzazioni per eseguire il proprio lavoro.

Il Centro sicurezza & conformità include i gruppi di ruoli predefiniti per le attività e le funzioni più comuni a cui sarà necessario assegnare gli utenti. È consigliabile aggiungere semplicemente singoli utenti **come membri** ai gruppi di ruoli predefiniti.

![Diagramma che mostra la relazione tra gruppi di ruoli e ruoli e membri](../../media/2a16d200-968c-4755-98ec-f1862d58cb8b.png)

## <a name="permissions-needed-to-use-features-in-the-security--compliance-center"></a>Autorizzazioni necessarie per usare le funzionalità nel Centro sicurezza & conformità

Nella tabella seguente sono elencati i gruppi di ruoli predefiniti disponibili nel Centro sicurezza & conformità e i ruoli assegnati ai gruppi di ruoli per impostazione predefinita. Per concedere autorizzazioni a un utente per eseguire un'attività di conformità, aggiungerle al gruppo di ruoli Centro sicurezza & conformità appropriato.

La gestione delle autorizzazioni nel Centro sicurezza & conformità consente solo agli utenti di accedere alle funzionalità di conformità disponibili all'interno del Centro sicurezza & conformità stesso. Se si desidera concedere autorizzazioni ad altre funzionalità di conformità non presenti nel Centro sicurezza & conformità, ad esempio le regole del flusso di posta di Exchange (note anche come regole di trasporto), è necessario utilizzare l'interfaccia di amministrazione di Exchange.

Per informazioni su come concedere l'accesso al Centro sicurezza & conformità, vedere Concedere agli utenti l'accesso all'interfaccia di amministrazione conformità di [Microsoft 365.](grant-access-to-the-security-and-compliance-center.md)

> [!NOTE]
> Per visualizzare la **scheda Autorizzazioni** nel Centro sicurezza & conformità, è necessario essere un amministratore. In particolare, è necessario  essere assegnati al ruolo Gestione ruoli  e tale ruolo viene assegnato solo al gruppo di ruoli Gestione organizzazione nel Centro sicurezza & conformità per impostazione predefinita. Inoltre, il **ruolo Gestione ruoli** consente agli utenti di visualizzare, creare e modificare i gruppi di ruoli.

<br><br>

****

|Gruppo di ruoli|Descrizione|Ruoli predefiniti assegnati|
|---|---|---|
|**Conformità delle comunicazioni**|Fornisce l'autorizzazione a tutti i ruoli di conformità delle comunicazioni: amministratore, analista, investigatore e visualizzatore.|Gestione dei casi <p> Communication Compliance Admin <p> Analisi di conformità delle comunicazioni <p> Gestione dei casi di conformità delle comunicazioni <p> Indagine sulla conformità delle comunicazioni <p> Visualizzatore conformità comunicazioni <p> Provider di feedback per la classificazione dei dati <p> View-Only caso|
|**Amministratori di conformità delle comunicazioni**|Amministratori della conformità delle comunicazioni che possono creare/modificare criteri e definire impostazioni globali.|Communication Compliance Admin <p> Gestione dei casi di conformità delle comunicazioni|
|**Analisti della conformità delle comunicazioni**|Gli analisti della conformità delle comunicazioni che possono analizzare le corrispondenze dei criteri, visualizzare i metadati dei messaggi ed eseguire azioni correttive.|Analisi di conformità delle comunicazioni <p> Gestione dei casi di conformità delle comunicazioni|
|**Investigatori della conformità delle comunicazioni**|Analisti della conformità delle comunicazioni che possono analizzare le corrispondenze dei criteri, visualizzare il contenuto dei messaggi ed eseguire azioni correttive.|Gestione dei casi <p> Analisi di conformità delle comunicazioni <p> Gestione dei casi di conformità delle comunicazioni <p> Analisi della conformità delle comunicazioni <p> Provider di feedback per la classificazione dei dati <p> View-Only caso|
|**Visualizzatori conformità comunicazioni**|Visualizzatore della conformità delle comunicazioni che può accedere ai report e ai widget disponibili.|Gestione dei casi di conformità delle comunicazioni <p> Visualizzatore conformità comunicazioni|
|**Amministratore conformità**<sup>1</sup>|I membri possono gestire le impostazioni per la gestione dei dispositivi, la prevenzione della perdita dei dati, i report e l'archiviazione.|Gestione dei casi <p> Amministratore di conformità <p> Ricerca di conformità <p> Provider di feedback per la classificazione dei dati <p> Revisore feedback classificazione dati <p> Gestione dei dispositivi <p> Gestione dell'eliminazione <p> Gestione conformità DLP <p> Hold <p> Gestione della conformità IB <p> Gestione avvisi <p> Configurazione organizzazione <p> RecordManagement <p> Gestione della conservazione <p> View-Only di controllo <p> View-Only caso <p> View-Only dispositivi <p> View-Only conformità DLP <p> View-Only conformità IB <p> View-Only gestire gli avvisi <p> Destinatari solo visualizzazione <p> View-Only record <p> View-Only conservazione|
|**Amministratore dei dati di conformità**|I membri possono gestire le impostazioni per la gestione dei dispositivi, la protezione dei dati, la prevenzione della perdita dei dati, i report e l'archiviazione.|Amministratore di conformità <p> Ricerca di conformità <p> Gestione dei dispositivi <p> Gestione conformità DLP <p> Gestione dell'eliminazione <p> Gestione della conformità IB <p> Gestione avvisi <p> Configurazione organizzazione <p> RecordManagement <p> Gestione della conservazione <p> Amministratore delle etichette di riservatezza <p> View-Only di controllo <p> View-Only dispositivi <p> View-Only conformità DLP <p> View-Only conformità IB <p> View-Only gestire gli avvisi <p> Destinatari solo visualizzazione <p> View-Only record <p> View-Only conservazione|
|**Amministratori di Compliance Manager**|Gestire la creazione e la modifica dei modelli.|Amministrazione di Compliance Manager <p> Valutazione di Compliance Manager <p> Contributo di Compliance Manager <p> Lettore di Compliance Manager|
|**Valutatori di Compliance Manager**|Creare valutazioni, implementare azioni di miglioramento e aggiornare lo stato dei test per le azioni di miglioramento.|Valutazione di Compliance Manager <p> Contributo di Compliance Manager <p> Lettore di Compliance Manager|
|**Collaboratori di Compliance Manager**|Creare valutazioni ed eseguire operazioni per implementare azioni di miglioramento.|Contributo di Compliance Manager <p> Lettore di Compliance Manager|
|**Lettori di Compliance Manager**|Visualizzare tutto il contenuto di Compliance Manager, ad eccezione delle funzioni di amministratore.|Lettore di Compliance Manager|
|**Visualizzatore contenuto di Esplora contenuto**|Visualizzare i file di contenuto in Esplora contenuto.|Visualizzatore contenuto classificazione dati|
|**Visualizzatore elenco esplora contenuto**|Visualizza tutti gli elementi in Esplora contenuto solo in formato elenco.|Visualizzatore elenco classificazione dati|
|**Gestore di eDiscovery**|I membri possono eseguire ricerche e inserire blocchi nelle cassette postali, nei siti di SharePoint Online e nelle posizioni di OneDrive for Business. I membri possono anche creare e gestire casi di eDiscovery, aggiungere e rimuovere membri a un caso, creare e modificare ricerche di contenuto associate a un caso e accedere ai dati dei casi in Advanced eDiscovery. <p> Un amministratore di eDiscovery è un membro del gruppo di ruoli Gestore di eDiscovery a cui sono state assegnate autorizzazioni aggiuntive. Oltre alle attività che un gestore di eDiscovery può eseguire, un amministratore di eDiscovery può:<ul><li>Visualizzare tutti i casi di eDiscovery nell'organizzazione.</li><li>Gestire qualsiasi caso di eDiscovery dopo che si è aggiunto come membro del caso.</li></ul> <p> La differenza principale tra un responsabile di eDiscovery e un amministratore di eDiscovery è che un amministratore di eDiscovery può accedere a tutti i casi elencati nella pagina casi di **eDiscovery** nel Centro sicurezza & conformità. Un responsabile di eDiscovery può accedere solo ai casi creati o ai casi di cui è membro. Per ulteriori informazioni su come impostare un utente come amministratore di eDiscovery, vedere Assegnare le autorizzazioni [di eDiscovery nel Centro sicurezza & conformità.](../../compliance/assign-ediscovery-permissions.md)|Gestione dei casi <p> Comunicazione <p> Ricerca di conformità <p> Responsabile <p> Esportazione <p> Hold <p> Anteprima <p> Revisione <p> Decrittografia RMS|
|**Lettore globale**|I membri hanno accesso in sola lettura a report, avvisi e possono visualizzare tutte le impostazioni e la configurazione.<p> La differenza principale tra lettore globale e lettore di sicurezza è che un lettore globale può accedere alla **configurazione e alle impostazioni.**|Ruolo con autorizzazioni di lettura per la sicurezza <p> Lettore etichette di riservatezza <p> Visualizzazione Garanzia del servizio <p> View-Only di controllo <p> View-Only dispositivi <p> View-Only conformità DLP <p> View-Only conformità IB <p> View-Only gestire gli avvisi <p> Destinatari solo visualizzazione <p> View-Only record <p> View-Only conservazione|
|**Gestione dei rischi Insider**|Utilizzare questo gruppo di ruoli per gestire la gestione dei rischi Insider per l'organizzazione in un singolo gruppo. Aggiungendo tutti gli account utente per amministratori, analisti e investigatori designati, è possibile configurare le autorizzazioni di gestione dei rischi Insider in un singolo gruppo. Questo gruppo di ruoli contiene tutti i ruoli di autorizzazione per la gestione dei rischi Insider. Questo è il modo più semplice per iniziare rapidamente a usare la gestione dei rischi Insider ed è adatto per le organizzazioni che non necessitano di autorizzazioni separate definite per gruppi di utenti separati.|Gestione dei casi <p> Amministratore gestione dei rischi Insider <p> Analisi della gestione dei rischi Insider <p> Analisi della gestione dei rischi Insider <p> View-Only caso|
|**Amministratori della gestione dei rischi Insider**|Utilizzare questo gruppo di ruoli per configurare inizialmente la gestione dei rischi Insider e successivamente per separare gli amministratori dei rischi Insider in un gruppo definito. Gli utenti di questo gruppo di ruoli possono creare, leggere, aggiornare ed eliminare i criteri di gestione dei rischi Insider, le impostazioni globali e le assegnazioni dei gruppi di ruoli.|Gestione dei casi <p> Amministratore gestione dei rischi Insider <p> View-Only caso|
|**Analisti gestione dei rischi Insider**|Utilizzare questo gruppo per assegnare autorizzazioni agli utenti che fungeranno da analisti dei casi di rischio Insider. Gli utenti di questo gruppo di ruoli possono accedere a tutti i modelli di avvisi, casi e avvisi per la gestione dei rischi Insider. Non possono accedere a Esplora contenuto con rischio Insider.|Gestione dei casi <p> Analisi della gestione dei rischi Insider <p> View-Only caso|
|**Revisori della gestione dei rischi Insider**|Revisori della gestione dei rischi insider in grado di visualizzare i log di controllo delle azioni eseguite da analisti, investigatori e amministratori.|Controllo della gestione dei rischi Insider|
|**Investigatori gestione dei rischi Insider**|Utilizzare questo gruppo per assegnare autorizzazioni agli utenti che agiranno come investigatori dei dati di rischio Insider. Gli utenti di questo gruppo di ruoli possono accedere a tutti gli avvisi di gestione dei rischi Insider, i casi, i modelli di avviso e Esplora contenuto per tutti i casi.|Gestione dei casi <p> Analisi della gestione dei rischi Insider <p> View-Only caso|
|**Collaboratori IRM**|Questo gruppo di ruoli è visibile, ma viene utilizzato solo dai servizi in background.|Contributo permanente per la gestione dei rischi Insider <p> Contributo temporaneo per la gestione dei rischi Insider|
|**Amministratore MailFlow**|I membri possono monitorare e visualizzare informazioni dettagliate e report sul flusso di posta nel Centro sicurezza & conformità. Gli amministratori globali possono aggiungere utenti ordinari a questo gruppo, ma, se l'utente non è un membro del gruppo Di amministrazione di Exchange, l'utente non avrà accesso alle attività correlate all'amministratore di Exchange.|Destinatari solo visualizzazione|
|**Gestione organizzazione**<sup>1</sup>|I membri possono controllare le autorizzazioni per l'accesso alle funzionalità nel Centro sicurezza & conformità e anche gestire le impostazioni per la gestione dei dispositivi, la prevenzione della perdita dei dati, i report e l'archiviazione. <p> Gli utenti che non sono amministratori globali devono essere amministratori di Exchange per visualizzare ed eseguire azioni sui dispositivi gestiti da Dispositivi mobili e sicurezza di base per Microsoft 365 (in precedenza noto come Gestione di dispositivi mobili o MDM). <p> Gli amministratori globali vengono aggiunti automaticamente come membri di questo gruppo di ruoli.|Registri di controllo <p> Gestione dei casi <p> Amministratore di conformità <p> Ricerca di conformità <p> Gestione dei dispositivi <p> Gestione conformità DLP <p> Hold <p> Gestione della conformità IB <p> Gestione avvisi <p> Configurazione organizzazione <p> Quarantena <p> RecordManagement <p> Gestione della conservazione <p> Gestione ruoli <p> Ricerca ed eliminazione <p> Amministratore della sicurezza <p> Ruolo con autorizzazioni di lettura per la sicurezza <p> Amministratore etichette di riservatezza <p> Lettore etichette di riservatezza <p> Visualizzazione Garanzia del servizio <p> Collaboratore tag <p> Tag Manager <p> Lettore tag <p> View-Only di controllo <p> View-Only dispositivi <p> View-Only conformità DLP <p> View-Only conformità IB <p> View-Only caso <p> View-Only gestire gli avvisi <p> Destinatari solo visualizzazione <p> View-Only record <p> View-Only conservazione|
|**Amministratore quarantena**|I membri possono accedere a tutte le azioni di quarantena. Per ulteriori informazioni, vedere Gestire i messaggi e i file in quarantena [come amministratore in EOP](manage-quarantined-messages-and-files.md)|Quarantena|
|**Gestione record**|I membri possono configurare tutti gli aspetti della gestione dei record, incluse le etichette di conservazione e le revisioni per l'eliminazione.|Gestione dell'eliminazione <p> RecordManagement <p> Gestione della conservazione|
|**Reviewer**|I membri possono accedere ai set di recensioni [nei casi di Advanced eDiscovery.](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20) I membri di questo gruppo di ruoli possono visualizzare e aprire l'elenco dei casi nella pagina **eDiscovery > Advanced** nel Centro conformità Microsoft 365 di cui sono membri. Dopo aver accesso a un caso di Advanced eDiscovery, l'utente può selezionare **Rivedere i set** per accedere ai dati del caso. Questo ruolo non consente all'utente di visualizzare in anteprima i risultati di una ricerca di raccolta associata al caso o di eseguire altre attività di ricerca o gestione dei casi. I membri di questo gruppo di ruoli possono accedere solo ai dati di un insieme da rivedere.|Revisione|
|**Amministratore della sicurezza**|I membri hanno accesso a diverse funzionalità di sicurezza di Identity Protection Center, Privileged Identity Management, Monitor Microsoft 365 Service Health e Security & Compliance Center. <p> Per impostazione predefinita, è possibile che questo gruppo di ruoli non abbia membri. Tuttavia, il ruolo Amministratore della sicurezza di Azure Active Directory viene assegnato a questo gruppo di ruoli. Di conseguenza, questo gruppo di ruoli eredita le funzionalità e l'appartenenza al ruolo Amministratore della sicurezza da Azure Active Directory. <p> Per gestire le autorizzazioni centralmente, aggiungere e rimuovere membri del gruppo nell'interfaccia di amministrazione di Azure Active Directory. Per ulteriori informazioni, vedere [Autorizzazioni del ruolo amministratore in Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) Se si modifica questo gruppo di ruoli nel Centro sicurezza & conformità (appartenenza o ruoli), tali modifiche si applicano solo al Centro sicurezza & conformità e non ad altri servizi. <p> Questo gruppo di ruoli include tutte le autorizzazioni di sola lettura del ruolo Lettore di sicurezza, oltre a una serie di autorizzazioni amministrative aggiuntive per gli stessi servizi: Azure Information Protection, Identity Protection Center, Privileged Identity Management, Monitor Microsoft 365 Service Health e Security & Compliance Center.|Registri di controllo <p> Gestione dei dispositivi <p> Gestione conformità DLP <p> Gestione della conformità IB <p> Gestione avvisi <p> Quarantena <p> Amministratore della sicurezza <p> Amministratore delle etichette di riservatezza <p> Collaboratore tag <p> Tag Manager <p> Lettore tag <p> View-Only di controllo <p> View-Only dispositivi <p> View-Only conformità DLP <p> View-Only conformità IB <p> View-Only gestire gli avvisi|
|**Operatore sicurezza**|I membri possono gestire gli avvisi di sicurezza e visualizzare anche i report e le impostazioni delle funzionalità di sicurezza.|Ricerca di conformità <p> Gestione avvisi <p> Ruolo con autorizzazioni di lettura per la sicurezza <p> Collaboratore tag <p> Lettore tag <p> View-Only di controllo <p> View-Only dispositivi <p> View-Only conformità DLP <p> View-Only conformità IB <p> View-Only gestire gli avvisi|
|**Lettore di sicurezza**|I membri hanno accesso in sola lettura a diverse funzionalità di sicurezza di Identity Protection Center, Privileged Identity Management, Monitor Microsoft 365 Service Health e Security & Compliance Center. <p> Per impostazione predefinita, questo gruppo di ruoli potrebbe non avere membri. Tuttavia, il ruolo Lettore di sicurezza di Azure Active Directory viene assegnato a questo gruppo di ruoli. Di conseguenza, questo gruppo di ruoli eredita le funzionalità e l'appartenenza al ruolo Lettore di sicurezza da Azure Active Directory. <p> Per gestire le autorizzazioni centralmente, aggiungere e rimuovere membri del gruppo nell'interfaccia di amministrazione di Azure Active Directory. Per ulteriori informazioni, vedere [Autorizzazioni del ruolo di amministratore in Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) Se si modifica questo gruppo di ruoli nel Centro sicurezza & conformità (appartenenza o ruoli), tali modifiche si applicano solo al Centro sicurezza & conformità e non ad altri servizi.|Ruolo con autorizzazioni di lettura per la sicurezza <p> Lettore etichette di riservatezza <p> Lettore tag <p> View-Only dispositivi <p> View-Only conformità DLP <p> View-Only conformità IB <p> View-Only gestire gli avvisi|
|**Service Assurance User**|I membri possono accedere alla sezione Garanzia del servizio nel Centro sicurezza & conformità. La garanzia del servizio fornisce report e documenti che descrivono le procedure di sicurezza di Microsoft per i dati dei clienti archiviati in Microsoft 365. Fornisce inoltre report di controllo di terze parti indipendenti su Microsoft 365. Per ulteriori informazioni, vedere [Garanzia del servizio nel Centro sicurezza & conformità.](https://docs.microsoft.com/microsoft-365/compliance/service-assurance)|Visualizzazione Garanzia del servizio|
|**Revisione di supervisione**|I membri possono creare e gestire i criteri che definiscono quali comunicazioni sono soggette a revisione in un'organizzazione. Per ulteriori informazioni, vedere [Configurare i criteri di conformità delle comunicazioni per l'organizzazione.](../../compliance/communication-compliance-configure.md)|Supervisory Review Administrator|
|

> [!NOTE]
> <sup>1</sup> Questo gruppo di ruoli non assegna ai membri le autorizzazioni necessarie per eseguire ricerche nel log di controllo o per utilizzare rapporti che potrebbero includere dati di Exchange, ad esempio i report DLP o Defender per Office 365. Per eseguire ricerche nel log di controllo o per visualizzare tutti i rapporti, è necessario assegnare a un utente le autorizzazioni in Exchange Online. Ciò avviene perché il cmdlet sottostante usato per la ricerca nel log di controllo è un cmdlet di Exchange Online. Gli amministratori globali possono eseguire ricerche nel log di controllo e visualizzare tutti i rapporti perché vengono aggiunti automaticamente come membri del gruppo di ruoli Gestione organizzazione in Exchange Online. Per ulteriori informazioni, vedere Eseguire una ricerca nel log di controllo nel [Centro sicurezza & conformità.](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)

## <a name="roles-in-the-security--compliance-center"></a>Ruoli nel Centro sicurezza & conformità

Nella tabella seguente sono elencati i ruoli disponibili e i gruppi di ruoli a cui sono assegnati per impostazione predefinita.

Si noti che i ruoli seguenti non vengono assegnati al gruppo di ruoli Gestione organizzazione per impostazione predefinita:

- Amministratore simulatore di attacco
- Autore payload simulatore di attacco
- Comunicazione
- Communication Compliance Admin
- Analisi di conformità delle comunicazioni
- Gestione dei casi di conformità delle comunicazioni
- Analisi della conformità delle comunicazioni
- Visualizzatore conformità comunicazioni
- Amministrazione di Compliance Manager
- Valutazione di Compliance Manager
- Contributo di Compliance Manager
- Lettore di Compliance Manager
- Responsabile
- Visualizzatore contenuto classificazione dati
- Provider di feedback per la classificazione dei dati
- Revisore feedback classificazione dati
- Visualizzatore elenco classificazione dati
- Gestione dell'eliminazione
- Esportazione
- Amministratore gestione dei rischi Insider
- Analisi della gestione dei rischi Insider
- Controllo della gestione dei rischi Insider
- Analisi della gestione dei rischi Insider
- Contributo permanente per la gestione dei rischi Insider
- Contributo temporaneo per la gestione dei rischi Insider
- Anteprima
- Revisione
- Decrittografia RMS
- Supervisory Review Administrator

<br><br>

****

|Ruolo|Descrizione|Assegnazioni predefinite del gruppo di ruoli|
|---|---|---|
|**Amministratore simulatore di attacco**|Usato per creare e gestire tutti gli aspetti delle campagne di simulazione degli attacchi.||
|**Autore payload simulatore di attacco**|Usato per creare e gestire i payload degli attacchi che possono essere distribuiti dall'amministratore del simulatore di attacco.||
|**Registri di controllo**|Attivare e configurare il controllo per l'organizzazione, visualizzare i report di controllo dell'organizzazione e quindi esportare tali report in un file.|Gestione organizzazione <p> Amministratore della sicurezza|
|**Gestione dei casi**|Creare, modificare, eliminare e controllare l'accesso ai casi di eDiscovery.|Conformità delle comunicazioni <p> Investigatori della conformità delle comunicazioni <p> Amministratore di conformità <p>Gestore di eDiscovery <p> Gestione dei rischi Insider <p> Amministratori della gestione dei rischi Insider <p> Analisti gestione dei rischi Insider <p> Investigatori gestione dei rischi Insider <p> Gestione organizzazione|
|**Comunicazione**|Gestire tutte le comunicazioni con i responsabile identificati in un caso di Advanced eDiscovery.  Creare notifiche di blocco, tenere promemoria e escalation alla gestione. Tenere traccia del riconoscimento da parte del responsabile delle notifiche di blocco e gestire l'accesso al portale dei responsabile usato da ogni responsabile in un caso per tenere traccia delle comunicazioni per i casi in cui sono stati identificati come responsabile.|Gestore di eDiscovery|
|**Communication Compliance Admin**|Usato per gestire i criteri nella funzionalità Conformità comunicazioni.|Conformità delle comunicazioni <p> Amministratori di conformità delle comunicazioni|
|**Analisi di conformità delle comunicazioni**|Usato per eseguire un'indagine, la correzione delle violazioni dei messaggi nella funzionalità Conformità comunicazioni. Può visualizzare solo i metadati del messaggio.|Conformità delle comunicazioni <p> Analisti della conformità delle comunicazioni <p> Investigatori della conformità delle comunicazioni|
|**Gestione dei casi di conformità delle comunicazioni**|Usato per accedere ai casi di conformità delle comunicazioni.|Conformità delle comunicazioni <p> Amministratori di conformità delle comunicazioni <p> Analisti della conformità delle comunicazioni <p> Investigatori della conformità delle comunicazioni <p> Visualizzatori conformità comunicazioni|
|**Analisi della conformità delle comunicazioni**|Usato per eseguire indagini, correzioni ed esaminare le violazioni dei messaggi nella funzionalità Conformità comunicazioni. Può visualizzare i metadati del messaggio e il messaggio.|Conformità delle comunicazioni <p> Investigatori della conformità delle comunicazioni|
|**Visualizzatore conformità comunicazioni**|Usato per accedere a report e widget nella funzionalità Conformità comunicazioni.|Conformità delle comunicazioni <p> Visualizzatori conformità comunicazioni|
|**Amministratore di conformità**|Visualizzare e modificare le impostazioni e i report per le funzionalità di conformità.|Amministratore di conformità <p> Amministratore dei dati di conformità <p> Gestione organizzazione|
|**Amministrazione di Compliance Manager**|Gestire la creazione e la modifica dei modelli.|Amministratori di Compliance Manager|
|**Valutazione di Compliance Manager**|Creare valutazioni, implementare azioni di miglioramento e aggiornare lo stato dei test per le azioni di miglioramento.|Amministratori di Compliance Manager <p> Valutatori di Compliance Manager|
|**Contributo di Compliance Manager**|Creare valutazioni ed eseguire operazioni per implementare azioni di miglioramento.|Amministratori di Compliance Manager <p> Valutatori di Compliance Manager <p> Collaboratori di Compliance Manager|
|**Compliance Manager - Lettore**|Visualizzare tutto il contenuto di Compliance Manager, ad eccezione delle funzioni di amministratore.|Amministratori di Compliance Manager <p> Valutatori di Compliance Manager <p> Collaboratori di Compliance Manager <p> Lettori di Compliance Manager|
|**Ricerca di conformità**|Eseguire ricerche tra le cassette postali e ottenere una stima dei risultati.|Amministratore di conformità <p> Amministratore dei dati di conformità <p>Gestore di eDiscovery <p> Gestione organizzazione <p> Operatore della sicurezza|
|**Responsabile**|Identificare e gestire i responsabile per i casi di Advanced eDiscovery e utilizzare le informazioni di Azure Active Directory e altre origini per trovare le origini dati associate ai responsabile. Associare in un caso altre origini dati, ad esempio cassette postali, siti di SharePoint e Teams.  Impostare un blocco legale sulle origini dati associate ai responsabile per conservare il contenuto nel contesto di un caso.|Gestore di eDiscovery|
|**Visualizzatore contenuto classificazione dati**|Visualizzare il rendering sul posto dei file in Esplora contenuto.|Visualizzatore contenuto di Esplora contenuto|
|**Provider di feedback per la classificazione dei dati**|Consente di fornire feedback ai classificatori in Esplora contenuto.|Conformità delle comunicazioni <p> Investigatori della conformità delle comunicazioni <p> Amministratore di conformità|
|**Revisore feedback classificazione dati**|Consente di esaminare il feedback dei classificatori in Esplora feedback.|Amministratore di conformità|
|**Visualizzatore elenco classificazione dati**|Visualizzare l'elenco dei file in Esplora contenuto.|Visualizzatore elenco esplora contenuto|
|**Gestione dei dispositivi**|Consente di visualizzare e modificare le impostazioni e i report per le funzionalità di gestione dei dispositivi.|Amministratore di conformità <p> Amministratore dei dati di conformità <p> Gestione organizzazione <p> Amministratore della sicurezza|
|**Gestione dell'eliminazione**|Controllare le autorizzazioni per l'accesso all'eliminazione manuale nel Centro sicurezza & conformità.|Amministratore di conformità <p> Amministratore dei dati di conformità <p> Gestione record|
|**Gestione conformità DLP**|Consente di visualizzare e modificare le impostazioni e i report per i criteri di prevenzione della perdita dei dati (DLP).|Amministratore di conformità <p> Amministratore dei dati di conformità <p> Gestione organizzazione <p> Amministratore della sicurezza|
|**Esportazione**|Esportare il contenuto della cassetta postale e del sito restituito dalle ricerche.|Gestore di eDiscovery|
|**Blocco**|Archiviazione del contenuto nelle cassette postali, nei siti e nelle cartelle pubbliche. Quando è in attesa, una copia del contenuto viene archiviata in una posizione sicura. I proprietari del contenuto potranno comunque modificare o eliminare il contenuto originale.|Amministratore di conformità <p>Gestore di eDiscovery <p> Gestione organizzazione|
|**Gestione della conformità IB**|Visualizzare, creare, rimuovere, modificare e testare i criteri di Information Barrier.|Amministratore di conformità <p> Amministratore dei dati di conformità <p> Gestione organizzazione <p> Amministratore della sicurezza|
|**Amministratore gestione dei rischi Insider**|Creare, modificare, eliminare e controllare l'accesso alla funzionalità di gestione dei rischi Insider.|Gestione dei rischi Insider <p> Amministratori della gestione dei rischi Insider|
|**Analisi della gestione dei rischi Insider**|Accedere a tutti i modelli di avvisi, casi e avvisi per la gestione dei rischi Insider.|Gestione dei rischi Insider <p> Analisti gestione dei rischi Insider|
|**Controllo della gestione dei rischi Insider**|Consentire la visualizzazione degli audit trail dei rischi Insider.|Revisori della gestione dei rischi Insider|
|**Analisi della gestione dei rischi Insider**|Accedere a tutti gli avvisi, i casi, i modelli di avviso e Esplora contenuto insider per tutti i casi.|Gestione dei rischi Insider <p> Investigatori gestione dei rischi Insider|
|**Contributo permanente per la gestione dei rischi Insider**|Questo gruppo di ruoli è visibile, ma viene utilizzato solo dai servizi in background.|Collaboratori IRM|
|**Contributo temporaneo per la gestione dei rischi Insider**|Questo gruppo di ruoli è visibile, ma viene utilizzato solo dai servizi in background.|Collaboratori IRM|
|**Gestione avvisi**|Consente di visualizzare e modificare le impostazioni e i report per gli avvisi.|Amministratore di conformità <p> Amministratore dei dati di conformità <p> Gestione organizzazione <p> Amministratore della sicurezza <p> Operatore della sicurezza|
|**Configurazione organizzazione**|Eseguire, visualizzare ed esportare i report di controllo e gestire i criteri di conformità per DLP, dispositivi e conservazione.|Amministratore di conformità <p> Amministratore dei dati di conformità <p> Gestione organizzazione|
|**Anteprima**|Visualizzare un elenco di elementi restituiti dalle ricerche di contenuto e aprire ogni elemento dall'elenco per visualizzarne il contenuto.|Gestore di eDiscovery|
|**Quarantena**|Consente di visualizzare e rilasciare la posta elettronica in quarantena.|Amministratore quarantena <p> Amministratore della sicurezza <p> Gestione organizzazione|
|**RecordManagement**|Consente di visualizzare e modificare la configurazione della caratteristica di gestione dei record.|Amministratore di conformità <p> Amministratore dei dati di conformità <p> Gestione organizzazione <p> Gestione record|
|**Gestione della conservazione**|Gestire i criteri di conservazione, le etichette di conservazione e i criteri delle etichette di conservazione.|Amministratore di conformità <p> Amministratore dei dati di conformità <p> Gestione organizzazione <p> Gestione record|
|**Verifica**|Questo ruolo consente agli utenti di accedere ai set di revisione nei casi di Advanced eDiscovery. Gli utenti a cui è assegnato questo ruolo possono visualizzare e aprire l'elenco dei casi nella pagina **eDiscovery > Advanced** nel Centro conformità Microsoft 365 di cui sono membri. Dopo aver accesso a un caso di Advanced eDiscovery, l'utente può selezionare **Rivedere i set** per accedere ai dati del caso. Questo ruolo non consente all'utente di visualizzare in anteprima i risultati di una ricerca di raccolta associata al caso o di eseguire altre attività di ricerca o gestione dei casi. Gli utenti con questo ruolo possono accedere solo ai dati in un insieme da rivedere.|Gestore di eDiscovery <p> Reviewer|
|**Decrittografia RMS**|Decrittografare il contenuto protetto da RMS durante l'esportazione dei risultati della ricerca.|Gestore di eDiscovery|
|**Gestione ruoli**|Gestire l'appartenenza ai gruppi di ruoli e creare o eliminare gruppi di ruoli personalizzati.|Gestione organizzazione|
|**Ricerca ed eliminazione**|Consente agli utenti di rimuovere in blocco i dati che corrispondono ai criteri di una ricerca di contenuto.|Gestione organizzazione|
|**Amministratore della sicurezza**|Visualizzare e modificare la configurazione e i report per le funzionalità di sicurezza.|Gestione organizzazione <p> Amministratore della sicurezza|
|**Lettore di sicurezza**|Visualizzare la configurazione e i report per le funzionalità di sicurezza.|Ruolo con autorizzazioni di lettura globali <p> Gestione organizzazione <p> Operatore della sicurezza <p> Ruolo con autorizzazioni di lettura per la sicurezza|
|**Amministratore delle etichette di riservatezza**|Consente di visualizzare, creare, modificare e rimuovere etichette di riservatezza.|Amministratore dei dati di conformità <p> Gestione organizzazione <p> Amministratore della sicurezza|
|**Lettore etichette di riservatezza**|Visualizzare la configurazione e l'utilizzo delle etichette di riservatezza.|Ruolo con autorizzazioni di lettura globali <p> Gestione organizzazione <p> Ruolo con autorizzazioni di lettura per la sicurezza|
|**Visualizzazione Garanzia del servizio**|Scaricare i documenti disponibili dalla sezione Garanzia del servizio. Il contenuto include il controllo indipendente, la documentazione di conformità e le indicazioni relative all'attendibilità per l'uso delle funzionalità di Microsoft 365 per gestire i rischi di sicurezza e conformità alle normative.|Ruolo con autorizzazioni di lettura globali <p> Gestione organizzazione <p> Service Assurance User|
|**Supervisory Review Administrator**|Gestire i criteri del processo di revisione, incluse le comunicazioni da rivedere e gli utenti che devono eseguire la revisione.|Revisione di supervisione|
|**Collaboratore tag**|Visualizzare e aggiornare l'appartenenza ai tag utente esistenti.|Gestione organizzazione <p> Amministratore della sicurezza <p> Operatore della sicurezza|
|**Tag Manager**|Visualizzare, aggiornare, creare ed eliminare tag utente.|Gestione organizzazione <p> Amministratore della sicurezza|
|**Lettore tag**|Accesso in sola lettura ai tag utente esistenti.|Ruolo con autorizzazioni di lettura per la sicurezza|
|**Registri di controllo di sola visualizzazione**|Visualizzare ed esportare i report di controllo. Poiché questi report potrebbero contenere informazioni riservate, è consigliabile assegnare questo ruolo solo agli utenti che hanno l'esigenza esplicita di visualizzare tali informazioni.|Amministratore di conformità <p> Amministratore dei dati di conformità <p> Ruolo con autorizzazioni di lettura globali <p> Gestione organizzazione <p> Amministratore della sicurezza <p> Operatore della sicurezza|
|**Maiuscole/minuscole di sola visualizzazione**||Conformità delle comunicazioni <p> Investigatori della conformità delle comunicazioni <p> Amministratore di conformità <p> Gestione dei rischi Insider <p> Amministratori della gestione dei rischi Insider <p> Analisti gestione dei rischi Insider <p> Insider RiskManagement Investigators <p> Gestione organizzazione|
|**Gestione dispositivi di sola visualizzazione**|Visualizzare la configurazione e i report per la funzionalità Gestione dispositivi.|Amministratore di conformità <p> Amministratore dei dati di conformità <p> Ruolo con autorizzazioni di lettura globali <p> Gestione organizzazione <p> Amministratore della sicurezza <p> Operatore della sicurezza <p> Ruolo con autorizzazioni di lettura per la sicurezza|
|**Gestione della conformità DLP di sola visualizzazione**|Visualizzare le impostazioni e i report per i criteri di prevenzione della perdita dei dati (DLP).|Amministratore di conformità <p> Amministratore dei dati di conformità <p> Ruolo con autorizzazioni di lettura globali <p> Gestione organizzazione <p> Amministratore della sicurezza <p> Operatore della sicurezza <p> Ruolo con autorizzazioni di lettura per la sicurezza|
|**Gestione della conformità IB di sola visualizzazione**|Visualizzare la configurazione e i report per la funzionalità Barriere informazioni.|Amministratore di conformità <p> Amministratore dei dati di conformità <p> Ruolo con autorizzazioni di lettura globali <p> Gestione organizzazione <p> Amministratore della sicurezza <p> Operatore della sicurezza <p> Ruolo con autorizzazioni di lettura per la sicurezza|
|**Gestisci avvisi in sola visualizzazione**|Visualizzare la configurazione e i report per la funzionalità Gestisci avvisi.|Amministratore di conformità <p> Amministratore dei dati di conformità <p> Ruolo con autorizzazioni di lettura globali <p> Gestione organizzazione <p> Amministratore della sicurezza <p> Operatore della sicurezza <p> Ruolo con autorizzazioni di lettura per la sicurezza|
|**Destinatari solo visualizzazione**|Consente di visualizzare informazioni su utenti e gruppi.|Amministratore di conformità <p> Amministratore dei dati di conformità <p> Ruolo con autorizzazioni di lettura globali <p> Amministratore MailFlow <p> Gestione organizzazione|
|**Gestione record di sola visualizzazione**|Visualizzare la configurazione della funzionalità di gestione dei record.|Amministratore di conformità <p> Amministratore dei dati di conformità <p> <p> Ruolo con autorizzazioni di lettura globali <p> Gestione organizzazione|
|**Gestione della conservazione in sola visualizzazione**|Visualizzare la configurazione dei criteri di conservazione, delle etichette di conservazione e dei criteri delle etichette di conservazione.|Amministratore di conformità <p> Amministratore dei dati di conformità <p> Amministratore globale <p> Gestione organizzazione|
|
