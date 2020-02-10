---
title: Audit avanzato in Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Il controllo avanzato in Microsoft 365 fornisce nuove funzionalità di audit per aiutare l'organizzazione nelle indagini forensi e di conformità.
ms.openlocfilehash: 49d2e2bbf7d1c19bb4c282920008a0ca9a34188d
ms.sourcegitcommit: 570ad1c7c334476ecec00dc355dfe52e8c2bb87b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/08/2020
ms.locfileid: "41862401"
---
# <a name="advanced-audit-in-microsoft-365"></a>Audit avanzato in Microsoft 365

La [funzionalità di audit unificato](search-the-audit-log-in-security-and-compliance.md) in Microsoft 365 consente alle organizzazioni di avere visibilità su molti tipi di attività controllate in molti servizi diversi in Microsoft 365. Con il rilascio di Audit avanzato in Microsoft 365 sono state aggiunte nuove funzionalità di audit per aiutare l'organizzazione nelle indagini forensi e di conformità.

> [!NOTE]
> Audit avanzato è disponibile per le organizzazioni con un abbonamento a Office 365 o Microsoft 365 Enterprise E5. Inoltre, è possibile assegnare agli utenti un abbonamento al componente aggiuntivo Microsoft 365 E5 Compliance nei casi in cui è necessaria una licenze per utente per le funzionalità Audit avanzato, come per la conservazione a lungo termine dei log di controllo e gli eventi di audit di alto valore.

Questo articolo offre una panoramica delle funzionalità di Audit avanzato.

## <a name="long-term-retention-of-audit-logs"></a>Conservazione a lungo termine dei log di controllo

Audit avanzato conserva tutti i record di controllo di Exchange, SharePoint e Azure Active Directory per un anno. Questa operazione viene eseguita da un criterio di conservazione predefinito dei log di controllo che conserva per un anno tutti i record di controllo che contengono il valore **Exchange**, **SharePoint** o **AzureActiveDirectory** per la proprietà **Workload**, che indica il servizio in cui si è verificata l'attività. Questo può essere utile nell'ambito delle indagini forensi o di conformità in corso. Per altre informazioni, vedere la sezione "Criterio di conservazione dei log di controllo predefinito" in [Gestire i criteri di conservazione dei log di controllo](audit-log-retention-policies.md#default-audit-log-retention-policy).

## <a name="audit-log-retention-policies"></a>Criteri di conservazione dei log di controllo

Tutti i record di controllo generati in altri servizi non coperti dai criteri di conservazione dei log di controllo predefiniti descritti nella sezione precedente vengono conservati per 90 giorni. Ora, però, è possibile creare criteri di conservazione dei log di controllo personalizzati per conservare altri record di controllo per un massimo di un anno. Si può creare un criterio per conservare i record di controllo in base a uno o più dei seguenti criteri:

- Il servizio Microsoft 365 in cui si sono verificate le attività controllate

- Attività controllate specifiche

- Utente che esegue un'attività controllata

È anche possibile specificare per quanto tempo conservare i record di controllo che soddisfano i criteri e un livello di priorità, affinché determinati criteri abbiano priorità su altri. Si noti inoltre che i criteri di conservazione dei log di controllo personalizzati hanno la precedenza sui criteri di conservazione predefiniti in caso sia necessario conservare i record di controllo di Exchange, SharePoint o Azure Active Directory per meno di un anno per alcuni o tutti gli utenti dell'organizzazione. Per altre informazioni, vedere [Gestire i criteri di conservazione dei log di controllo](audit-log-retention-policies.md).

## <a name="high-value-audit-events"></a>Eventi di controllo di alta qualità

Gli eventi di controllo a livello di sicurezza e conformità di alta qualità sono quelli che consentono di indagare su possibili violazioni o eseguire altre indagini di tipo forense. Il primo evento di questo tipo che rilasciamo è l'evento di audit di cassette postali *MailItemsAccessed*. Questo evento viene generato quando viene eseguito l'accesso ai dati di posta elettronica da protocolli di posta elettronica e da client. L'evento MailItemsAccessed può aiutare gli investigatori a identificare violazioni dei dati e a determinare l'ambito dei messaggi che potrebbero essere stati compromessi. Se un utente malintenzionato ha ottenuto l'accesso ai messaggi di posta elettronica, viene generato l'evento MailItemsAccessed anche in assenza di segnale esplicito che indichi l'avvenuta lettura; in altri termini, nel record di controllo viene registrato il tipo di accesso, ad esempio tramite associazione o sincronizzazione.

La nuova azione MailItemsAccessed per le cassette postali sostituisce MessageBind nella registrazione di controllo delle cassette postali in Exchange Online e offre i miglioramenti seguenti:

- MessageBind era configurabile solo per il tipo di accesso utente AuditAdmin; non si applicava alle azioni delegate o proprietarie. MailItemsAccessed si applica a tutti i tipi di accesso.

- MessageBind copriva solo l'accesso da parte di un client di posta elettronica. Non si applicava alle attività di sincronizzazione. Gli eventi di MailItemsAccessed vengono generati dai tipi di accesso di associazione e sincronizzazione.

- Le azioni MessageBind attivavano la creazione di più record di controllo al momento dell'accesso allo stesso messaggio di posta elettronica, con conseguente "rumore" di auditing. Gli eventi MailItemsAccessed, invece, sono aggregati in un numero minore di record di controllo.

Per altre informazioni sulla registrazione di controllo delle cassette postali, vedere [Gestire il controllo delle cassette postali](enable-mailbox-auditing.md).

## <a name="high-bandwidth-access-to-the-office-365-management-activity-api"></a>Accesso a larghezza di banda elevata all'API Office 365 Management Activity

Le organizzazioni che accedono ai log di controllo con l'API Office 365 Management Activity erano vincolate da limitazioni a livello di publisher. Questo significa che per un publisher che estrae dati per conto di più clienti, il limite era condiviso da tutti i clienti.

Con il rilascio di Audit avanzato, si passa da un limite a livello di publisher a un limite a livello di tenant. Il risultato è che ogni organizzazione otterrà una quota di larghezza di banda completamente allocata per accedere ai dati di controllo. La larghezza di banda non è un limite predefinito statico, ma è modellata in base a una combinazione di fattori, tra cui il numero di postazioni nell'organizzazione e il fatto che le organizzazioni E5 otterranno una larghezza di banda maggiore rispetto alle organizzazioni non E5.

A tutte le organizzazioni viene inizialmente assegnata una baseline di 2.000 richieste al minuto. Questo limite verrà incrementato in modo dinamico in base al numero di postazioni di un'organizzazione e all'abbonamento di licenza. Le organizzazioni E5 otterranno approssimativamente il doppio della larghezza di banda delle organizzazioni non E5. Sarà anche previsto un tetto per la larghezza di banda massima per proteggere l'integrità del servizio.

Per altre informazioni, vedere la sezione dedicata alla limitazione dell'API nell'argomento di [riferimento all'API Office 365 Management Activity](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#api-throttling).
