---
title: Novità nel centro conformità di Microsoft 365
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
description: Analogamente alle funzionalità del centro conformità di Microsoft 365, il contenuto della guida è sempre in evoluzione. Stiamo creando continuamente nuovi articoli, aggiornando quelli esistenti ed eseguendo modifiche in base ai commenti e suggerimenti. Scopri cosa c'è di nuovo e aggiornato in questo mese.
ms.openlocfilehash: 4a07327f9ea830483aa3abbaa1b6bd52ca825230
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632161"
---
# <a name="recent-updates-to-microsoft-365-compliance-content"></a>Aggiornamenti recenti a Microsoft 365 content Compliance

Analogamente alle funzionalità del centro conformità di Microsoft 365, il contenuto della guida è sempre in evoluzione. Stiamo creando continuamente nuovi articoli, aggiornando quelli esistenti ed eseguendo modifiche in base ai commenti e suggerimenti. Per vedere cosa c'è di nuovo e aggiornato questo mese, consulta la pagina seguente.

> [!TIP]
> Per rimanere al di sopra degli aggiornamenti delle funzionalità più recenti nel centro conformità Microsoft 365, vedere [What ' s New in the microsoft 365 Compliance Center](whats-new.md).

## <a name="february-2020"></a>Febbraio 2020

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

