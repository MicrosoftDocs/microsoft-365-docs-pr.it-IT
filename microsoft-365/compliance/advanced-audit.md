---
title: Audit avanzato in Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
- m365solution-audit
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Audit avanzato in Microsoft 365 fornisce nuove funzionalità di audit per aiutare l'organizzazione nelle indagini forensi e di conformità.
ms.openlocfilehash: 51ec75cc8d8ae554ea9cbef3a9ea2aa18171e70a
ms.sourcegitcommit: 9bf6a4f77f9af5fd988f6795bad3b240213a51fc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/10/2020
ms.locfileid: "48950995"
---
# <a name="advanced-audit-in-microsoft-365"></a>Audit avanzato in Microsoft 365

La [ funzionalità di controllo unificato ](search-the-audit-log-in-security-and-compliance.md) in Microsoft 365 offre alle organizzazioni visibilità in molti tipi di attività controllate relative a differenti servizi in Microsoft 365. Audit avanzato consente alle organizzazioni di svolgere indagini forensi e di conformità aumentando il periodo di conservazione dei log di controllo richiesti per condurre un'indagine, fornendo accesso a eventi cruciali che consentono di determinare la portata della violazione e velocizzando l'accesso all’API Office 365 Management Activity.

> [!NOTE]
> Audit avanzato è disponibile per le organizzazioni con un abbonamento a Office 365 E5 o Microsoft 365 Enterprise E5. Inoltre, è possibile assegnare agli utenti una licenza di Microsoft 365 E5 Compliance o E5 eDiscovery e il componente aggiuntivo di controllo, quando le licenze per utente sono obbligatorie per le funzionalità di Audit avanzato, come accade per la conservazione a lungo termine dei log di controllo e l'accesso a eventi cruciali per le indagini. Per altre informazioni sulle licenze, vedere [Guida alle licenze di Microsoft 365 per sicurezza e conformità](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#advanced-audit).

Questo articolo offre una panoramica delle funzionalità di Audit avanzato.

## <a name="long-term-retention-of-audit-logs"></a>Conservazione a lungo termine dei log di controllo

Audit avanzato conserva tutti i record di controllo di Exchange, SharePoint e Azure Active Directory per un anno. Ciò viene eseguito da un criterio di conservazione del log di controllo predefinito che conserva i record di controllo che contengono il valore di **Exchange** , **SharePoint** o **AzureActiveDirectory** per la proprietà del **carico di lavoro** (che indica il servizio in cui si è verificata l'attività) per un anno. Conservare i record di controllo per periodi più lunghi può aiutare nelle indagini forensi o di conformità in corso. Per ulteriori informazioni, vedere la sezione "Criterio di conservazione del log di controllo predefinito" in [ Gestire i criteri di conservazione del log di controllo](audit-log-retention-policies.md#default-audit-log-retention-policy).

In fase di rilascio, ci sarà anche la possibilità di conservare i log di audit per 10 anni. Il periodo di conservazione di 10 anni dei log di controllo consente di supportare le indagini lunghe e rispondere a obblighi normativi, legali e interni.

> [!NOTE]
> La conservazione dei log di controllo per 10 anni richiederà una licenza aggiuntiva dei componenti aggiuntivi. Tale licenza sarà disponibile all'inizio del 2021. Per ulteriori informazioni, vedere la sezione [Domande frequenti sull'Audit avanzato](#faqs-for-advanced-audit).

### <a name="audit-log-retention-policies"></a>Criteri di conservazione dei log di controllo

Tutti i record di controllo generati in altri servizi che non sono coperti dal criterio di conservazione del log di controllo predefinito, descritto nella sezione precedente, vengono conservati per 90 giorni. È tuttavia possibile creare criteri di conservazione del log di controllo personalizzati per conservare altri log di controllo per periodi di tempo più lunghi di 10 anni. È possibile creare un criterio per conservare i record di controllo in base a uno o più dei seguenti criteri:

- Il servizio Microsoft 365 in cui si sono verificate le attività controllate.

- Le specifiche attività controllate.

- L'utente che esegue un'attività controllata.

È anche possibile specificare per quanto tempo mantenere i record di controllo che corrispondono ai criteri e un livello di priorità, in modo che i criteri specifici abbiano priorità su altri criteri. Si noti inoltre che i criteri di conservazione dei log di controllo personalizzati hanno la precedenza sui criteri di conservazione del controllo predefiniti, in caso sia necessario mantenere i record di controllo di Exchange, SharePoint o Azure Active Directory per meno di un anno (o per 10 anni) per alcuni o tutti gli utenti dell'organizzazione. Per altre informazioni, vedere [Gestire i criteri di conservazione dei log di controllo](audit-log-retention-policies.md).

## <a name="access-to-crucial-events-for-investigations"></a>Accesso agli eventi cruciali per le indagini

Audit avanzato consente alle organizzazioni di svolgere indagini forensi e di conformità fornendo l'accesso a eventi cruciali, ad esempio quando è stato effettuato l'accesso agli elementi di posta o quando è stata inviata o inoltrato una risposta, e quando e cosa ha cercato un utente in Exchange Online e SharePoint Online. Tali eventi cruciali consentono di indagare su possibili violazioni e determinare la portata della compromissione. Audit avanzato fornisce i seguenti eventi cruciali:

- [MailItemsAccessed](#mailitemsaccessed)

- [Send](#send)

- [SearchQueryInitiatedExchange](#searchqueryinitiatedexchange)

- [SearchQueryInitiatedSharePoint](#searchqueryinitiatedsharepoint)

### <a name="mailitemsaccessed"></a>MailItemsAccessed

L'evento MailItemsAccessed è un'azione di controllo della cassetta postale e viene attivato quando si accede ai dati di posta da protocolli e client di posta. L'azione MailItemsAccessed consente agli investigatori di identificare le violazioni dei dati e determinare l'ambito dei messaggi che potrebbero essere stati compromessi. Se un utente malintenzionato ha ottenuto l'accesso ai messaggi di posta elettronica, l'azione MailItemsAccessed verrà attivata anche se non vi è alcun segnale esplicito che i messaggi siano stati effettivamente letti (in altre parole, il tipo di accesso come un associazione o sincronizzazione viene registrato nel record di controllo).

L'azione MailItemsAccessed per le cassette postali sostituisce MessageBind nella registrazione di controllo delle cassette postali in Exchange Online, e offre i miglioramenti seguenti:

- MessageBind era configurabile solo per il tipo di accesso utente AuditAdmin; non si applicava alle azioni delegate o proprietarie. MailItemsAccessed si applica a tutti i tipi di accesso.

- MessageBind copriva solo l'accesso da parte di un client di posta. Non si applicava alle attività di sincronizzazione. Gli eventi MailItemsAccessed vengono attivati da entrambi i tipi di accesso, associazione e sincronizzazione.

- Le azioni MessageBind attivavano la creazione di più record di controllo al momento dell'accesso alla stessa e-mail, con conseguente "rumore" di controllo. Al contrario, gli eventi MailItemsAccessed vengono aggregati in un minor numero di record di controllo.

Per informazioni sui record di controllo per le attività di MailItemsAccessed, vedere [Usare Audit avanzato per individuare gli account compromessi](mailitemsaccessed-forensics-investigations.md).

Per cercare i record di controllo MailItemsAccessed, è possibile cercare l'attività **Elementi delle cassette postali accessibili** nell'elenco a discesa **Attività su cassette postali di Exchange** nello [strumento Ricerca log di audit](search-the-audit-log-in-security-and-compliance.md) nel Centro conformità Microsoft 365.

![Ricerca di azioni MailItemsAccessed nello strumento Ricerca log di audit](../media/AdvAudit_MailItemsAccessed.png)

È anche possibile eseguire i comandi [Search-UnifiedAuditLog -Operations MailItemsAccessed](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog) o [Search-MailboxAuditLog -Operations MailItemsAccessed](https://docs.microsoft.com/powershell/module/exchange/search-mailboxauditlog) in PowerShell per Exchange Online.

### <a name="send"></a>Send

Anche l'evento send è un'azione di controllo delle cassette postali, ed è avviato quando l'utente esegue una di queste azioni:

- Inviare un messaggio di posta elettronica

- Rispondere a un messaggio di posta elettronica

- Inoltrare un messaggio di posta elettronica

Gli investigatori possono utilizzare l'evento Invia per identificare i messaggi di posta elettronica inviati da un account compromesso. Il record di controllo per un evento di invio contiene informazioni sul messaggio, ad esempio quando il messaggio è stato inviato, l'ID InternetMessage, la riga dell'oggetto e se il messaggio conteneva allegati. Queste informazioni di controllo possono aiutare gli investigatori a identificare le informazioni sui messaggi di posta elettronica inviati da un account compromesso o inviati da un utente malintenzionato. Inoltre, gli investigatori possono utilizzare uno strumento eDiscovery di Microsoft 365 per cercare il messaggio (utilizzando la riga dell'oggetto o l'ID del messaggio) per identificare i destinatari a cui è stato inviato il messaggio e il contenuto effettivo di tale messaggio.

Per cercare i record di controllo dell'evento Send, cercare l'attività **Messaggi inviati** nell'elenco a discesa **Attività su cassette postali di Exchange** nello [Strumento di ricerca dei log di controllo](search-the-audit-log-in-security-and-compliance.md) del Centro conformità Microsoft 365.

![Cercare le azioni di invio dei messaggi nello strumento di ricerca nel log di controllo](../media/AdvAudit_SentMessage.png)

È anche possibile eseguire i comandi [Search-UnifiedAuditLog -Operations Send](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog) o [Search-MailboxAuditLog -Operations Send](https://docs.microsoft.com/powershell/module/exchange/search-mailboxauditlog) in PowerShell per Exchange Online.

### <a name="searchqueryinitiatedexchange"></a>SearchQueryInitiatedExchange

L'evento SearchQueryInitiatedExchange viene attivato quando una persona utilizza la barra di ricerca in Outlook sul Web per cercare elementi in una cassetta postale. Gli investigatori possono utilizzare l'evento SearchQueryInitiatedExchange per determinare se un utente malintenzionato che potrebbe aver compromesso un account ha cercato o tentato di accedere a informazioni riservate nella cassetta postale. Il record di controllo per un evento SearchQueryInitiatedExchange contiene informazioni come il testo effettivo della query di ricerca. Osservando le query di ricerca che un utente malintenzionato potrebbe aver eseguito, un investigatore può comprendere meglio l'intento dietro i dati di posta elettronica ricercati.

Per cercare i record di controllo dell'evento SearchQueryInitiatedExchange, cercare l'attività **Ricerche email eseguite** nell'elenco a discesa **Attività di ricerca** nello [Strumento di ricerca dei log di controllo](search-the-audit-log-in-security-and-compliance.md) del Centro conformità.

![Cercare le azioni di ricerca dei messaggi di posta elettronica nello strumento di ricerca dei log di controllo](../media/AdvAudit_SearchExchange.png)

È anche possibile eseguire [Search-UnifiedAuditLog -Operations SearchQueryInitiatedExchange](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog) in PowerShell per Exchange Online.

> [!NOTE]
> Bisogna eseguire questo comando in PowerShell per Exchange Online, in modo che gli eventi SearchQueryInitiatedExchange (eseguiti dallo specifico utente E5) siano inclusi nei risultati della ricerca dei log di controllo: `Set-Mailbox <user identity> -AuditOwner @{Add="SearchQueryInitiated"}`.

### <a name="searchqueryinitiatedsharepoint"></a>SearchQueryInitiatedSharePoint

In modo simile alla ricerca di elementi della cassetta postale, l'evento SearchQueryInitiatedSharePoint viene attivato quando una persona cerca elementi nel sito principale di SharePoint per l'organizzazione. Gli investigatori possono utilizzare l'evento SearchQueryInitiatedSharePoint per determinare se un utente malintenzionato ha tentato di trovare, ed eventualmente accedere, ad informazioni riservate in SharePoint. Il record di controllo per un evento SearchQueryInitiatedSharePoint contiene anche il testo della query di ricerca. Osservando le query di ricerca che un utente malintenzionato potrebbe aver eseguito, un investigatore può comprendere meglio l'intento e l'ambito dei dati del file ricercati.

Per cercare i record di controllo dell'evento SearchQueryInitiatedSharePoint, cercare l'attività **Ricerche di SharePoint eseguite** nell'elenco a discesa **Attività di ricerca** nello [Strumento di ricerca dei log di controllo](search-the-audit-log-in-security-and-compliance.md) del Centro conformità.

![Cercare le azioni di ricerca eseguite in SharePoint nello strumento di ricerca dei log di controllo](../media/AdvAudit_SearchSharePoint.png)

È anche possibile eseguire [Search-UnifiedAuditLog -Operations SearchQueryInitiatedSharePoint](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog) in PowerShell per Exchange Online.

> [!NOTE]
> Bisogna eseguire questo comando in PowerShell per Exchange Online, in modo che gli eventi SearchQueryInitiatedSharePoint (eseguiti dallo specifico utente E5) siano inclusi nei risultati della ricerca dei log di controllo: `Set-Mailbox <user identity> -AuditOwner @{Add="SearchQueryInitiated"}`.

## <a name="high-bandwidth-access-to-the-office-365-management-activity-api"></a>Accesso a larghezza di banda elevata all'API Office 365 Management Activity

Le organizzazioni che accedono ai log di controllo tramite l'API Office 365 Management Activity erano vincolate da limitazioni a livello di editore. Ciò significa che per un editore che estrae dati per conto di più clienti, il limite era condiviso da tutti i clienti.

Con il rilascio di Audit avanzato, si passa da un limite a livello di editore a un limite a livello di tenant. Il risultato è che ogni organizzazione otterrà una quota di larghezza di banda completamente allocata per accedere ai dati di controllo. La larghezza di banda non è un limite predefinito statico, ma è modellata in base a una combinazione di fattori, tra cui il numero di postazioni nell'organizzazione e il fatto che le organizzazioni E5 otterranno una larghezza di banda maggiore rispetto alle organizzazioni non E5.

A tutte le organizzazioni viene inizialmente assegnata una baseline di 2.000 richieste al minuto. Questo limite verrà incrementato in modo dinamico in base al numero di postazioni di un'organizzazione e all'abbonamento di licenza. Le organizzazioni E5 otterranno circa il doppio della larghezza di banda delle organizzazioni non E5. Sarà anche previsto un tetto per la larghezza di banda massima per proteggere l'integrità del servizio.

Per altre informazioni, vedere la sezione dedicata alla limitazione dell'API nell'argomento di [riferimento all'API Office 365 Management Activity](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#api-throttling).

## <a name="faqs-for-advanced-audit"></a>Domande frequenti su Audit avanzato

**Ogni utente deve avere una licenza E5 per usufruire di Audit avanzato?**

Per usufruire delle funzionalità di Audit avanzato a livello utente, a un utente deve essere assegnato una licenza E5. Sono presenti alcune funzionalità che verificano la disponibilità della licenza appropriata per fornire la funzionalità all'utente. Ad esempio, se si sta provando a conservare i record di controllo di un utente a cui non è stata assegnata una licenza E5 per più di 90 giorni, il sistema restituirà un messaggio di errore.

**Se l'organizzazione ha un abbonamento a E5, in che modo è possibile ottenere l'accesso ai record di controllo per gli eventi più importanti?**

Per i clienti idonei e gli utenti a cui è assegnata la licenza appropriata, non ci sono azioni da intraprendere per accedere agli eventi di controllo cruciali.

**Quando sarà disponibile il componente aggiuntivo per la conservazione dei log di controllo per 10 anni?**

Il nuovo componente per la conservazione dei log di controllo per 10 anni sarà disponibile per i clienti con abbonamento E5 all'inizio del 2021.

**Che cosa succede ai log di controllo della mia organizzazione se creo un criterio di conservazione dei log di controllo per 10 anni quando la funzionalità viene rilasciata al pubblico, ma prima che la licenza necessaria per il componente aggiuntivo sia resa disponibile all'inizio del 2021?**

Qualsiasi dato dei log di controllo coperto da un criterio di conservazione per 10 anni creato dopo che il componente sarà reso disponibile sarà conservato per 10 anni. Se la licenza per il componente aggiuntivo di conservazione del log di controllo per 10 anni sarà disponibile all'inizio del 2021, l'utente dovrà acquistare le licenze del componente aggiuntivo per gli utenti i cui dati di controllo vengono conservati ai sensi di un criterio di conservazione da 10 anni già esistente. Inoltre, quando la licenza per il componente aggiuntivo sarà disponibile all'inizio del 2021, verrà applicata la licenza appropriata quando saranno creati i nuovi criteri di conservazione dei log di controllo per 10 anni.

**I nuovi eventi di Audit avanzato sono disponibili nell'API Office 365 Management Activity?**

Sì. Finché verranno generati record di controllo per gli utenti in possesso della licenza appropriata, sarà possibile accedere a tali record tramite l'API Office 365 Management Activity.

**Una larghezza di banda superiore comporta una latenza o un contratto di servizio migliore?**

Al momento, una larghezza di banda superiore garantisce una pipeline migliore, soprattutto per le organizzazioni con un volume elevato di segnali di controllo e modelli di consumo significativi. Una larghezza di banda superiore può migliorare la latenza. Ma non esiste un contratto di servizio associato a una larghezza di banda superiore. Le latenze standard sono documentate e non subiscono modifiche con il rilascio di Audit avanzato.
