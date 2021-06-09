---
title: Informazioni sulla gestione degli accessi con privilegi
description: In questo articolo viene fornita una panoramica sulla gestione degli accessi con privilegi in Microsoft 365, incluse le risposte alle domande frequenti (DOMANDE FREQUENTI).
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: overview
f1.keywords:
- NOCSH
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.openlocfilehash: 059e1653d7db9140dbc80fd69fe36e95a744b079
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126605"
---
# <a name="learn-about-privileged-access-management"></a>Informazioni sulla gestione degli accessi con privilegi

La gestione degli accessi privilegiati consente il controllo granulare degli accessi sulle attività di amministrazione privilegiate in Office 365. Può aiutare a proteggere l'organizzazione da violazioni tramite account amministratore privilegiati esistenti con accesso permanente a dati sensibili o a impostazioni di configurazione critiche. Con la gestione degli accessi privilegiati gli utenti devono richiedere l'accesso JIT per completare le attività elevate e con privilegi attraverso un flusso di lavoro di approvazione altamente mirato e limitato nel tempo. Questa configurazione offre agli utenti un accesso sufficiente per eseguire l'attività da svolgere, senza rischiare l'esposizione di dati sensibili o impostazioni di configurazione critiche. L'abilitazione della gestione degli accessi con privilegi in Microsoft 365 consente all'organizzazione di operare senza privilegi permanenti e fornire un livello di difesa contro le vulnerabilità di accesso amministrativo in piedi.

Per una breve panoramica del flusso di lavoro integrato Customer Lockbox e della gestione degli accessi privilegiati, vedi questo video sulla gestione degli accessi con privilegi e [Customer Lockbox.](https://go.microsoft.com/fwlink/?linkid=2066800)

## <a name="layers-of-protection"></a>Livelli di protezione

La gestione degli accessi privilegiati integra altre protezioni dei dati e delle funzionalità di accesso all'Microsoft 365 di sicurezza. L'inclusione della gestione degli accessi privilegiati nell'ambito di un approccio integrato e a più livelli alla sicurezza offre un modello di sicurezza che ottimizza la protezione delle informazioni riservate e delle Microsoft 365 di configurazione. Come illustrato nel diagramma, la gestione degli accessi privilegiati si basa sulla protezione fornita con la crittografia nativa dei dati di Microsoft 365 e sul modello di sicurezza del controllo di accesso basato sui ruoli dei servizi Microsoft 365. Se usate con [Azure AD Privileged Identity Management](/azure/active-directory/active-directory-privileged-identity-management-configure), queste due funzionalità forniscono il controllo di accesso con accesso just-in-time in ambiti diversi.

![Protezione a più livelli in Microsoft 365](../media/pam-layered-protection.png)

La gestione degli accessi con privilegi  è definita e con ambito a livello  di attività, mentre Azure AD Privileged Identity Management applica la protezione a livello di ruolo con la possibilità di eseguire più attività. Azure AD Privileged Identity Management consente principalmente di gestire gli accessi per i ruoli e i gruppi di ruoli di Active Directory, mentre la gestione degli accessi privilegiati in Microsoft 365 si applica solo a livello di attività.

- **Abilitazione della gestione degli accessi con privilegi mentre si usa già Azure AD Privileged Identity Management:** L'aggiunta della gestione degli accessi privilegiati offre un altro livello granulare di funzionalità di protezione e controllo per l'accesso con privilegi Microsoft 365 dati.

- **Abilitazione di Azure AD Privileged Identity Management la gestione** degli accessi con privilegi già in Office 365:  L'aggiunta di Privileged Identity Management Azure AD alla gestione degli accessi privilegiati può estendere l'accesso con privilegi ai dati esterni Microsoft 365 definiti principalmente da ruoli utente o identità.  

## <a name="privileged-access-management-architecture-and-process-flow"></a>Architettura di gestione degli accessi con privilegi e flusso di processo

Ognuno dei flussi di processo seguenti delinea l'architettura dell'accesso privilegiato e il modo in cui interagisce con il substrato di Microsoft 365, il controllo e lo spazio di esecuzione Exchange Management.

### <a name="step-1-configure-a-privileged-access-policy"></a>Passaggio 1: configurare un criterio di accesso privilegiato

Quando si configura un criterio di accesso con privilegi con l'interfaccia di amministrazione di [Microsoft 365](https://admin.microsoft.com) o PowerShell di gestione di Exchange, si definiscono i criteri e i processi delle funzionalità di accesso con privilegi e gli attributi dei criteri nel substrato di Microsoft 365. Le attività vengono registrate nel Centro &amp; sicurezza e conformità. Il criterio è ora abilitato ed pronto per gestire le richieste di approvazione in arrivo.

![Passaggio 1: creazione dei criteri](../media/pam-step1-policy-creation.jpg)

### <a name="step-2-access-request"></a>Passaggio 2: richiesta di accesso

[Nell'Microsoft 365 di amministrazione](https://admin.microsoft.com) o con PowerShell Exchange Management, gli utenti possono richiedere l'accesso ad attività con privilegi elevati o con privilegi. La funzionalità di accesso con privilegi invia la richiesta al Microsoft 365 per l'elaborazione in base al criterio di accesso dei privilegi configurato e registra l'attività nei registri del Centro &amp; sicurezza e conformità.

![Passaggio 2: richiesta di accesso](../media/pam-step2-access-request.jpg)

### <a name="step-3-access-approval"></a>Passaggio 3: approvazione dell'accesso

Viene generata una richiesta di approvazione e viene inviata la notifica di richiesta in sospeso tramite posta elettronica ai responsabili approvazione. Se approvata, la richiesta di accesso privilegiato viene elaborata come un'approvazione e l'attività sarà pronta per essere completata. Se negata, l'attività viene bloccata e non viene concesso alcun accesso al richiedente. Il richiedente riceve notifica dell'approvazione o rifiuto della richiesta tramite posta elettronica.

![Passaggio 3: approvazione dell'accesso](../media/pam-step3-access-approval.jpg)

### <a name="step-4-access-processing"></a>Passaggio 4: elaborazione dell'accesso

Per una richiesta approvata, l'attività viene elaborata dallo spazio di esecuzione di Exchange Management. L'approvazione viene verificata rispetto al criterio di accesso privilegiato e viene elaborata dal substrato di Microsoft 365. Tutte le attività per l'attività vengono registrate nel Centro &amp; sicurezza e conformità.

![Passaggio 4: elaborazione dell'accesso](../media/pam-step4-access-processing.jpg)

## <a name="frequently-asked-questions"></a>Domande frequenti

### <a name="what-skus-can-use-privileged-access-in-office-365"></a>Quali SKU possono usare l'accesso con privilegi in Office 365?

La gestione degli accessi privilegiati è disponibile per i clienti per un'ampia selezione di Microsoft 365 e Office 365 e componenti aggiuntivi. Per [informazioni dettagliate, vedere Introduzione alla gestione degli accessi](privileged-access-management-configuration.md) con privilegi.

### <a name="when-will-privileged-access-support-office-365-workloads-beyond-exchange"></a>Quando l'accesso con privilegi supporterà Office 365 carichi di lavoro oltre Exchange?

La gestione degli accessi privilegiati sarà presto disponibile in altri Office 365 di lavoro. Per ulteriori [dettagli, Microsoft 365 guida](https://www.microsoft.com/microsoft-365/roadmap) di orientamento.

### <a name="my-organization-needs-more-than-30-privileged-access-policies-will-this-limit-be-increased"></a>L'organizzazione ha bisogno di più di 30 criteri di accesso con privilegi, questo limite verrà aumentato?

Sì, l'aumento del limite corrente di 30 criteri di accesso con privilegi per ogni organizzazione è nella roadmap delle funzionalità.

### <a name="do-i-need-to-be-a-global-admin-to-manage-privileged-access-in-office-365"></a>Devo essere un amministratore globale per gestire l'accesso con privilegi in Office 365?

No, è necessario assegnare Exchange ruolo Gestione ruoli agli account che gestiscono l'accesso con privilegi in Office 365. Se non si desidera configurare il ruolo Gestione ruoli come autorizzazione account autonomo, il ruolo Amministratore globale include questo ruolo per impostazione predefinita e può gestire l'accesso con privilegi. Gli utenti inclusi in un gruppo di responsabili approvazione non devono essere un amministratore globale o disporre del ruolo Gestione ruoli assegnato per esaminare e approvare le richieste con PowerShell.

### <a name="how-is-privileged-access-management-related-to-customer-lockbox"></a>In che modo la gestione degli accessi con privilegi è correlata a Customer Lockbox?

[Customer Lockbox](/office365/admin/manage/customer-lockbox-requests) consente un livello di controllo di accesso per le organizzazioni quando Microsoft accede ai dati. La gestione degli accessi privilegiati consente un controllo granulare dell'accesso all'interno di un'organizzazione per Microsoft 365 attività privilegiate.

## <a name="ready-to-get-started"></a>Pronti per iniziare?

Iniziare [a configurare l'organizzazione per la gestione degli accessi con privilegi.](privileged-access-management-configuration.md)

## <a name="learn-more"></a>Altre informazioni

[Guida interattiva: Monitorare e controllare le attività di amministratore con la gestione degli accessi con privilegi](https://content.cloudguides.com/guides/Privileged%20Access%20Management)
