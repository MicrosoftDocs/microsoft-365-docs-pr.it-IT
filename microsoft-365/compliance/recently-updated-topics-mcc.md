---
title: Aggiornamenti recenti nel centro conformità
f1.keywords:
- NOCSH
ms.author: brendonb
author: brendonb
manager: laurawi
ms.date: 03/22/2020
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- m365-security-compliance
description: Analogamente alle funzionalità del centro conformità di Microsoft 365, il contenuto della guida è sempre in evoluzione. Scopri cosa c'è di nuovo e aggiornato in questo mese.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 3bba8d0bbd68c6d28d72bcf32abdc798d7125250
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818966"
---
# <a name="recent-updates-to-microsoft-365-compliance-content"></a>Aggiornamenti recenti a Microsoft 365 content Compliance

Analogamente alle funzionalità del centro conformità di Microsoft 365, il contenuto della guida è sempre in evoluzione. Stiamo creando continuamente nuovi articoli, aggiornando quelli esistenti ed eseguendo modifiche in base ai commenti e suggerimenti. Per vedere cosa c'è di nuovo e aggiornato questo mese, consulta la pagina seguente.

> [!TIP]
> Per rimanere al di sopra degli aggiornamenti delle funzionalità più recenti nel centro conformità Microsoft 365, vedere [What ' s New in the microsoft 365 Compliance Center](whats-new.md).

## <a name="march-2020"></a>Marzo 2020

### <a name="auditing"></a>Controllo

[Utilizzare il controllo avanzato per esaminare gli account compromessi](mailitemsaccessed-forensics-investigations.md) (nuovi)<br>Nuove linee guida sull'utilizzo della nuova azione di controllo delle cassette postali di *MailItemsAccessed* per le indagini forensi.

[Eseguire una ricerca nel registro di controllo](search-the-audit-log-in-security-and-compliance.md) (aggiornato)<br>Le modifiche includono:
- [Nuova sezione](search-the-audit-log-in-security-and-compliance.md#the-appsharepoint-user-in-audit-records) con informazioni dettagliate sull'utente ' app@sharepoint ' elencato nei record di controllo.
- [Nuove descrizioni](search-the-audit-log-in-security-and-compliance.md#quarantine-activities) delle attività di quarantena.
- Nella sezione [attività amministrazione utente](search-the-audit-log-in-security-and-compliance.md#user-administration-activities) , è stato chiarito che l'evento cambia password utente viene attivato quando un utente modifica la propria password (tramite la reimpostazione della password in modalità self-service) e viene attivato l'evento "Reimposta password utente" quando un amministratore reimposta la password di un utente.

### <a name="auto-expanding-archive"></a>Archivio in espansione automatica

[Panoramica dell'archiviazione illimitata](unlimited-archiving.md#outlook-requirements-for-accessing-items-in-an-auto-expanded-archive) (aggiornata)<br>Sono stati aggiunti chiarimenti che non è possibile eliminare una cartella nell'archivio principale o un archivio ausiliario dopo che l'archiviazione in espansione automatica è abilitata su una cassetta postale.

### <a name="compliance-scorecompliance-manager"></a>Punteggio di conformità/gestione conformità

Tutti gli argomenti [Compliance Score](compliance-score.md) and [Compliance Manager](compliance-manager-overview.md) riflettono gli aggiornamenti di questi prodotti rilasciati all'inizio di aprile (entrambi sono ancora in anteprima pubblica). Gli aggiornamenti principali includono:
- Processo semplificato per la creazione e la modifica dei modelli
- Avviso per il controllo delle versioni e per i modelli e le azioni
- Sincronizzazione di azioni comuni tra gruppi
- Supporto per le lingue ora esteso a cinese (semplificato), cinese (tradizionale), francese, tedesco, italiano, giapponese, coreano, portoghese (Brasile), russo e spagnolo

### <a name="communication-compliance"></a>Conformità delle comunicazioni

[Case Study-Contoso configura rapidamente un criterio di lingua offensivo per Microsoft teams, Exchange e Yammer Communications](communication-compliance-case-study.md) (New)<br>Un case study dettagliato per l'istruzione e le organizzazioni di piccole imprese per aiutarli a configurare rapidamente un criterio di lingua offensiva. Le richieste aumentate dai clienti come organizzazioni dilagano in su per le risposte di COVID19.

[Introduzione alla conformità alla comunicazione](communication-compliance-configure.md) (aggiornata)<br>Requisiti di licenza e autorizzazioni aggiornati.

### <a name="customer-key"></a>Customer Key

Eseguire [il rollforward o la rotazione di una chiave del cliente o di una chiave di disponibilità](customer-key-availability-key-roll.md) (aggiornata)<br>Aggiornamenti organizzativi che consentono di chiarire quali tasti è possibile e non possono essere inseriti.

Informazioni [sulla chiave di disponibilità per il codice "Customer Key](customer-key-availability-key-understand.md) " (aggiornato)<br>Sono stati aggiunti chiarimenti su Exchange Online Architecture for Customer Key.

### <a name="data-loss-prevention"></a>Prevenzione della perdita di dati

[Panoramica della prevenzione della perdita di dati](data-loss-prevention-policies.md) (aggiornata)<br>È stato aggiornato il tempo necessario per rendere effettive le etichette di conservazione e i criteri di comportamento predefiniti senza avvisi configurati.

### <a name="ediscovery"></a>eDiscovery

[Introduzione a Advanced eDiscovery](get-started-with-advanced-ediscovery.md) (New)<br>Vengono fornite informazioni sui requisiti di licenza e autorizzazioni, sulla procedura per configurare le impostazioni globali e sulla creazione di un nuovo caso e su una procedura dettagliata del flusso di lavoro di eDiscovery avanzato.

[Pensionamento degli strumenti legacy di eDiscovery](legacy-ediscovery-retirement.md) (aggiornato)<br>Le date di pensionamento sono state spostate di tre mesi a causa della situazione di salute pubblica. Articolo aggiornato cita le nuove date di pensionamento.

### <a name="insider-risk-management"></a>Gestione dei rischi Insider

Informazioni [introduttive sulla gestione dei rischi Insider](insider-risk-management-configure.md) (aggiornato)<br>Requisiti di licenza e autorizzazioni aggiornati.

[Definire i criteri di barriera delle informazioni](information-barriers-policies.md) (aggiornato)<br>Velocità e tempi di elaborazione chiarificati necessari per l'applicazione. Sono stati aggiunti dettagli sul modo in cui non devono essere presenti Criteri rubrica. Sono inoltre disponibili vari aggiornamenti del codice di PowerShell, incluso il nuovo codice per il filtro.

[Barriere informative](information-barriers.md) (aggiornate)<br>Sono stati corretti alcuni collegamenti interrotti e sono stati aggiornati collegamenti e titoli PDF. Per i commenti e suggerimenti dei clienti, è stato chiarito che le barriere informative supportano solo le restrizioni. Le restrizioni unidirezionali (come il marketing possono comunicare con i commercianti diurni, ma i trader diurni non possono comunicare con il marketing) non sono supportate.

[Risoluzione dei problemi relativi alle informazioni sugli ostacoli](information-barriers-troubleshooting.md) (aggiornato)<br>È stata aggiunta una nuova sezione scenario di risoluzione dei problemi. È stato aggiunto un collegamento ai passaggi per la riapplicazione delle barriere informative.

### <a name="office-365-message-encryption"></a>Crittografia dei messaggi di Office 365

[Gestire la crittografia dei messaggi di Office 365](manage-office-365-message-encryption.md) (aggiornata)<br>Aggiornato per riflettere che la funzione wrapper Force è una funzionalità OME standard, non avanzata. Riscrisse gli esempi di PowerShell per escludere tutti i riferimenti alla revoca e alla scadenza delle funzionalità di OME avanzate.

[Domande frequenti sulla crittografia dei messaggi](ome-faq.md) (aggiornato)<br>È stato chiarito che solo Outlook per il Web è in grado di applicare la crittografia ad-hoc. Analogamente, per tutti i client Outlook, i messaggi e gli allegati PDF non protetti ereditano la protezione OME del criterio di prevenzione della perdita di dati (DLP) o della regola del flusso di posta in Exchange Online.

### <a name="privileged-access-management"></a>Gestione accessi con privilegi

[Introduzione alla gestione degli accessi con privilegi](privileged-access-management-configuration.md) (aggiornato)<br>Requisiti di licenza e autorizzazioni aggiornati.

### <a name="pst-import"></a>Importazione PST

[Domande frequenti sull'importazione di file PST](faqimporting-pst-files-to-office-365.md) (aggiornato)<br>Aggiunte domande frequenti su come il processo di importazione PST gestisce gli elementi di posta elettronica duplicati.

### <a name="sensitivity-labels"></a>Etichette di riservatezza

Informazioni [sulle etichette di riservatezza](sensitivity-labels.md) (aggiornate)<br>Sono stati aggiunti dettagli negativi sulla gestione delle etichette nel portale di Azure, incluso un collegamento alla [notifica ufficiale](https://techcommunity.microsoft.com/t5/azure-information-protection/announcing-timelines-for-sunsetting-label-management-in-the/ba-p/1226179).

[Introduzione alle etichette di riservatezza](get-started-with-sensitivity-labels.md) (aggiornate)<br>Sono state aggiunte informazioni sul nuovo ruolo lettore di etichette di riservatezza, che è supportato inizialmente solo per i cmdlet di PowerShell per l'etichettatura.

[Creare e configurare le etichette di riservatezza e i relativi criteri](create-sensitivity-labels.md#removing-and-deleting-labels) (aggiornato)<br>Aggiunta nuova sezione vengono illustrate le conseguenze della rimozione e dell'eliminazione delle etichette.

[Utilizzare le etichette di riservatezza per proteggere il contenuto in Microsoft teams, gruppi microsoft 365 e siti di SharePoint (anteprima pubblica)](sensitivity-labels-teams-groups-sites.md) (aggiornato)<br>Le modifiche includono:

- Sono state rimosse le istruzioni di Azure AD e sono invece collegate alle [informazioni autorevoli di Azure ad](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels).
- Sono state aggiornate le [impostazioni per la configurazione del sito e del gruppo quando si crea o si modifica la sezione etichette di riservatezza](sensitivity-labels-teams-groups-sites.md#how-to-configure-site-and-group-settings-when-you-create-or-edit-sensitivity-labels) con informazioni sulla **privacy dell'impostazione dei siti di Team connessi al gruppo di Office 365** , che include la nuova opzione **nessuno** .
- È stata aggiunta una nota in cui viene descritto come solo le etichette con le impostazioni del sito e del gruppo saranno disponibili per la selezione quando gli utenti creano team, gruppi e siti. Questa funzionalità viene gradualmente implementata per le organizzazioni.

[Limitare l'accesso al contenuto utilizzando le etichette di riservatezza per applicare la crittografia](encryption-sensitivity-labels.md) (aggiornata)<br>[Nuova sezione](encryption-sensitivity-labels.md#example-configurations-for-the-encryption-settings) con impostazioni di crittografia di esempio per alcune delle configurazioni più comunemente utilizzate per la protezione di documenti e messaggi di posta elettronica.

[Applicazione automatica di un'etichetta di riservatezza al contenuto](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps) (aggiornato)<br>Spiegazione delle differenze comportamentali tra l'etichettatura incorporata e il client di etichettatura unificata di Azure Information Protection.

[Abilitare le etichette di riservatezza per i file di Office in SharePoint e OneDrive](sensitivity-labels-sharepoint-onedrive-files.md) (aggiornato)<br>Le modifiche includono:

- È stato chiarito che l'abilitazione di questa anteprima Visualizza il pulsante **sensitivity** sulla barra multifunzione per le etichette in Office per il Web, oltre a supportare i documenti etichettati e crittografati.
- Sono state aggiornate le istruzioni per Office 365 multi-Geo.
- L'elenco delle limitazioni contiene una nuova voce che include gli elementi che si verificano quando un computer è in modalità offline o per il sonno e se viene eliminata un'etichetta.

[Utilizzare le etichette di riservatezza nelle app di Office](sensitivity-labels-office-apps.md) (aggiornate)<br>Le modifiche includono:

- Informazioni sulle licenze spostate per [iniziare a utilizzare le etichette di riservatezza](get-started-with-sensitivity-labels.md).
- [Nuova sezione](sensitivity-labels-office-apps.md#labeling-client-for-desktop-apps) in cui viene illustrato come utilizzare le etichette incorporate nelle app desktop di Office, è necessario utilizzare un'edizione di sottoscrizione di Office anziché edizioni autonome.
- Le tabelle delle app supportate includono l'app di Office per iOS e Android e la configurazione che consente agli utenti di assegnare le autorizzazioni per Word, Excel e PowerPoint è stato aggiornato: ora viene visualizzato il canale mensile per Windows e Mac.  
- [Nuova sezione](sensitivity-labels-office-apps.md#office-built-in-labeling-client-and-other-labeling-solutions) che spiega come è possibile utilizzare l'impostazione di criteri di gruppo per disabilitare l'etichettatura incorporata se si utilizzano altre soluzioni di etichettatura che si desidera continuare a utilizzare per i computer Windows. 
- È stata aggiornata la sezione [Opzioni e etichette di sensibilità di Information Rights Management (IRM)](sensitivity-labels-office-apps.md#information-rights-management-irm-options-and-sensitivity-labels) con l'indicazione di utilizzare le etichette che applicano la crittografia anziché le opzioni IRM, con una spiegazione delle possibili conseguenze quando le due soluzioni di protezione sono miste.

### <a name="trainable-classifiers"></a>Classificatori addestrabili

[Guida introduttiva ai classificatori addestrabili (anteprima)](classifier-getting-started-with.md) (aggiornato)<br>Sono state aggiunte informazioni sul modo in cui il modello di lingua offensiva è obsoleto. Inoltre, è stata aggiunta una tabella che elenca i primi 25 linguaggi di codice utilizzati nel classificatore incorporato del codice sorgente.

## <a name="february-2020"></a>Febbraio 2020

> [!NOTE]
> Gli articoli elencati nei mesi precedenti possono essere stati aggiornati, spostati o eliminati. Di conseguenza, alcuni dei dettagli riportati di seguito potrebbero essere obsoleti e i collegamenti potrebbero essere interrotti.

### <a name="auditing"></a>Controllo

[Controllo avanzato in Microsoft 365](advanced-audit.md) (nuovo)<br>Disponibile per le organizzazioni con una sottoscrizione di Office 365 E5 o Microsoft 365 Enterprise E5, Advanced audit estende le funzionalità di controllo esistenti introducendo funzionalità quali periodi di conservazione lunghi per i registri di controllo, nuovi criteri di conservazione dei log di controllo e una nuova azione di controllo delle cassette postali che consente di tenere traccia della lettura della posta.

[Gestire i criteri di conservazione dei log di controllo](audit-log-retention-policies.md) (New)<br>Informazioni dettagliate sulla gestione dei criteri di conservazione dei log di controllo, la nuova funzionalità di controllo avanzata che consente di salvare i record di controllo da diversi servizi per un massimo di un anno.

[Gestire il controllo delle cassette postali](enable-mailbox-auditing.md#logon-types-and-mailbox-actions) (aggiornato)<br>Sono state aggiunte informazioni sulla nuova azione della cassetta postale di MailItemsAccessed, introdotta con Advanced audit.

[Eseguire una ricerca nel registro di controllo](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) (aggiornato)<br>Sono state aggiunte nuove descrizioni per le attività relative alle etichette di riservatezza e altre informazioni sulle [attività di collaborazione dei moduli](search-the-audit-log-in-security-and-compliance.md#forms-activities-performed-by-co-authors-and-anonymous-responders)di controllo.

### <a name="compliance-offerings"></a>Offerte per la conformità

[Framework di sicurezza delle informazioni ENISA](offering-enisa.md) (nuovo)<br>Nuovo argomento che supporta la rete europea e Information Security Agency (ENISA) Information Assurance Framework (IAF).

[Controlli organizzazione del servizio (SOC)](offering-SOC.md) (aggiornato)<br>Sono stati aggiunti nuovi riferimenti di controllo.

[Autorità australiana di regolamentazione prudenziale (apra)](offering-APRA-Australia.md) (aggiornata)<br>Contenuto allineato per i nuovi standard normativi.

### <a name="customer-key"></a>Customer Key

[Crittografia del servizio con la chiave Customer](customer-key-overview.md) (nuova)<br>Nuovo articolo che introduce la chiave del cliente, i concetti correlati come BitLocker e la crittografia del servizio e il modo in cui interagiscono.

[Gestione chiave cliente](customer-key-manage.md) (nuovo)<br>Istruzioni successive all'installazione per la gestione del codice "Customer Key", inclusi i passaggi per la gestione delle autorizzazioni di DEPs e Key Vault esistenti, i tempi stimati per il completamento delle operazioni, la verifica del funzionamento della crittografia e la modalità di uscita dal servizio.

Eseguire [il rollforward o la rotazione di una chiave del cliente o di una chiave di disponibilità](customer-key-availability-key-roll.md) (nuova)<br>Descrive come eseguire il rollback delle chiavi gestite dal cliente per la chiave del cliente.

Informazioni [sulla chiave di disponibilità per il codice "Customer Key](customer-key-availability-key-understand.md) " (nuovo)<br>Copertura dettagliata del codice di disponibilità: quando e come viene utilizzato per il ripristino dalla perdita di chiave, in cui esiste nella gerarchia di chiavi del cliente e altro ancora.

[Configurare la chiave del cliente per Microsoft 365](customer-key-set-up.md) (aggiornato)<br>Precedentemente intitolato "Controlling your data in Microsoft 365 using Customer Key", questo articolo si concentra esclusivamente su come configurare Customer Key per Office 365, incluse le istruzioni aggiornate.

### <a name="data-classification"></a>Classificazione dei dati

[Note sulla versione di anteprima pubblica di classificazione dei dati (anteprima)](data-classification-pub-preview-relnotes.md) (nuovo)<br>Note sulla versione per l'anteprima pubblica introduzione di nuove funzionalità in cui viene avviata l'analisi del contenuto sensibile e contrassegnato prima di creare qualsiasi criterio. In questo modo è possibile esaminare come le etichette di conservazione e di riservatezza esistenti incidono sull'organizzazione per valutare le esigenze dei criteri di protezione e di governance.

### <a name="gdpr"></a>GDPR

[Richieste del soggetto dei dati di Office 365 per GDPR e CCPA](gdpr-dsr-Office365.md) (aggiornato)<br>Rimossi i riferimenti a Microsoft StaffHub a causa [del pensionamento dell'app](https://docs.microsoft.com/microsoftteams/expand-teams-across-your-org/shifts/microsoft-staffhub-to-be-retired).

Sono stati aggiunti i riferimenti di Compliance Manager e i collegamenti aggiornati per il Punteggio di conformità negli articoli seguenti.<br>
[Riepilogo generale sulla protezione dei dati](gdpr.md) (l'articolo include anche nuove domande frequenti dal centro sicurezza).<br>
[Piano d'azione GDPR di Microsoft 365: massime priorità per i primi 30 giorni, 90 giorni e oltre](gdpr-action-plan.md)<br>
[Supportare il programma GDPR con elenchi di controllo di preparazione della conformità](gdpr-arc.md)<br>
[Elenco di controllo per l'applicazione del GDPR all'uso di Azure](gdpr-arc-Azure.md)<br>
[Elenco di controllo di preparazione della conformità di Dynamics 365 all'RGPD](gdpr-arc-Dynamics365.md)<br>
[Elenco di controllo per l'applicazione del GDPR all'uso di Microsoft Office 365](gdpr-arc-Office365.md)<br>

### <a name="insider-risk-management"></a>Gestione dei rischi Insider

Sono stati aggiornati gli articoli seguenti per supportare la versione ufficiale di insider Risk Management.<br>
[Informazioni sulla gestione dei rischi insider in Microsoft 365](insider-risk-management.md)<br>
[Introduzione alla gestione dei rischi Insider](insider-risk-management-configure.md)<br>
[Creare e gestire i criteri dei rischi Insider](insider-risk-management-policies.md)<br>
[Esaminare gli avvisi relativi ai rischi Insider](insider-risk-management-alerts.md)<br>
[Intervenire riguardo ai casi di rischio Insider](insider-risk-management-cases.md)<br>
[Esaminare i dati con l'explorer del contenuto di gestione dei rischi Insider](insider-risk-management-content-explorer.md)<br>
[Aggiungere utenti a criteri dei rischi Insider](insider-risk-management-users.md)<br>
[Creare avvisi di rischio Insider](insider-risk-management-notices.md)<br>

### <a name="records-management"></a>Gestione dei record

[Panoramica delle etichette di conservazione](labels.md) (aggiornate)<br>La sezione per l'applicazione di un'etichetta di conservazione in base alle condizioni ora include l'opzione per l'utilizzo dei classificatori addestrabili.

### <a name="sensitivity-labels"></a>Etichette di riservatezza

Iniziare [a utilizzare le etichette di riservatezza](get-started-with-sensitivity-labels.md) (nuove)<br>Include indicazioni per i clienti di Azure Information Protection, panoramica generale del processo e passaggi per la distribuzione di etichette di riservatezza, le autorizzazioni per la creazione e la gestione delle etichette, un elenco di scenari comuni che supportano le etichette e un elenco di documentazione disponibile per gli utenti finali.

Informazioni [sulle etichette di riservatezza](sensitivity-labels.md) (aggiornate)<br>Rinominati da "Panoramica delle etichette di riservatezza" e sono state spostate le informazioni dalla sezione "Introduzione" al nuovo articolo [Introduzione alle etichette di riservatezza](get-started-with-sensitivity-labels.md).

[Creare e configurare le etichette di riservatezza e i relativi criteri](create-sensitivity-labels.md) (aggiornato)<br>Informazioni sui dettagli delle autorizzazioni spostate nel nuovo articolo, iniziare [con le etichette di riservatezza](get-started-with-sensitivity-labels.md).

[Limitare l'accesso al contenuto utilizzando le etichette di riservatezza per applicare la crittografia](encryption-sensitivity-labels.md) (aggiornata)<br>Nuove opzioni di "None" e "Remove" sostituisce l'interruttore di crittografia e "Aggiungi tutti gli utenti autenticati" viene aggiunto come nuova autorizzazione per assegnare ora. La sezione per consentire agli utenti di assegnare l'autorizzazione viene aggiornata ora che è possibile richiedere agli utenti di selezionare le autorizzazioni personalizzate in Word, PowerPoint ed Excel in anteprima per Windows e Mac. Nuova sezione per le configurazioni di esempio su come configurare le impostazioni di crittografia per il supporto di casi di utilizzo specifici. Nuova sezione che elenca le considerazioni per crittografare il contenuto.

[Applicazione automatica di un'etichetta di riservatezza al contenuto](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps) (aggiornato)<br>La sezione per la configurazione dell'etichetta automatica per le app di Office include ora la nuova opzione per l'utilizzo dei classificatori addestrabili.

[Utilizzare le etichette di riservatezza per proteggere il contenuto in Microsoft teams, gruppi microsoft 365 e siti di SharePoint (anteprima pubblica)](sensitivity-labels-teams-groups-sites.md) (aggiornato)<br>Revisioni in tutto per una migliore esperienza di lettura e chiarimenti tecnici. Inoltre, per i commenti e suggerimenti dei clienti, sono stati aggiunti collegamenti all' [articolo di Azure ad](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels) per abilitare l'anteprima e applicare etichette di riservatezza ai gruppi di Microsoft 365 nel portale di Azure. Infine, è stata aggiunta una nuova sezione per il controllo delle attività relative alle etichette di riservatezza.

[Abilitare le etichette di riservatezza per i file di Office in SharePoint e OneDrive (Public Preview)](sensitivity-labels-sharepoint-onedrive-files.md) (aggiornato)<br>Tra i vari aggiornamenti sono disponibili chiarimenti per i commenti e suggerimenti del cliente per il funzionamento di questa funzionalità, sottolineando che le nuove funzionalità sono valide solo per i file nuovi e modificati e per una nuova limitazione che è possibile visualizzare solo durante una fase di testing se si eliminano le etichette.

[Utilizzare le etichette di riservatezza nelle app di Office](sensitivity-labels-office-apps.md) (aggiornate)<br>Sono state aggiornate le tabelle delle funzionalità per consentire agli utenti di assegnare autorizzazioni e applicare un'etichetta al contenuto automaticamente. Inoltre, in base al feedback dei clienti, è stata aggiunta un'eccezione per gli allegati di posta elettronica che ereditano un'etichetta.

### <a name="service-descriptions"></a>Descrizioni dei servizi

[Linee guida per la gestione delle licenze Microsoft 365 per la sicurezza & conformità](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance) (aggiornato)<br>Retitled from "Microsoft 365 tenant-Level Licensing Services guidance" per riflettere meglio il contenuto.

