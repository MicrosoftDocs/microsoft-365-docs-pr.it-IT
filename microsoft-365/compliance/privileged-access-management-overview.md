---
title: Informazioni sulla gestione degli accessi con privilegi
description: Questo articolo offre una panoramica sulla gestione degli accessi privilegiati in Microsoft 365, incluse le risposte alle domande frequenti ..
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

La gestione degli accessi privilegiati consente un controllo granulare degli accessi sulle attività di amministrazione con privilegi in Office 365. Consente di proteggere l'organizzazione da violazioni che utilizzano account di amministratore con privilegi esistenti con accesso permanente ai dati sensibili o l'accesso alle impostazioni di configurazione critiche. La gestione degli accessi privilegiati richiede agli utenti di richiedere l'accesso just-in-time per completare attività con privilegi elevati e con privilegi tramite un flusso di lavoro di approvazione con ambito elevato e con limiti di tempo. Questa configurazione offre agli utenti un accesso sufficiente per eseguire l'attività a portata di mano, senza rischiare l'esposizione di dati sensibili o impostazioni di configurazione critiche. L'abilitazione della gestione degli accessi privilegiati in Microsoft 365 consente all'organizzazione di operare senza privilegi permanenti e fornire un livello di difesa contro le vulnerabilità di accesso amministrativo permanente.

Per una rapida panoramica del flusso di lavoro integrato Customer Lockbox e della gestione degli accessi privilegiati, vedi questo video sulla gestione degli accessi con privilegi e [Customer Lockbox.](https://go.microsoft.com/fwlink/?linkid=2066800)

## <a name="layers-of-protection"></a>Livelli di protezione

La gestione degli accessi privilegiati integra altre protezioni per i dati e le funzionalità di accesso all'interno dell'architettura di sicurezza di Microsoft 365. L'inclusione della gestione degli accessi privilegiati nell'ambito di un approccio integrato e su più livelli alla sicurezza offre un modello di sicurezza che ottimizza la protezione delle informazioni riservate e delle impostazioni di configurazione di Microsoft 365. Come illustrato nel diagramma, la gestione degli accessi privilegiati si basa sulla protezione fornita con la crittografia nativa dei dati di Microsoft 365 e sul modello di sicurezza del controllo degli accessi basato sui ruoli dei servizi di Microsoft 365. Se usate con [Azure AD Privileged Identity Management,](/azure/active-directory/active-directory-privileged-identity-management-configure)queste due funzionalità forniscono il controllo dell'accesso con accesso just-in-time in ambiti diversi.

![Protezione su più livelli in Microsoft 365](../media/pam-layered-protection.png)

La gestione degli accessi privilegiati  viene definita e con ambito a livello  di attività, mentre Azure AD Privileged Identity Management applica la protezione a livello di ruolo con la possibilità di eseguire più attività. Azure AD Privileged Identity Management consente principalmente la gestione degli accessi per i ruoli e i gruppi di ruoli di ACTIVE, mentre la gestione degli accessi privilegiati in Microsoft 365 si applica solo a livello di attività.

- **Abilitazione della gestione degli accessi con privilegi quando si usa già Azure AD Privileged Identity Management:** L'aggiunta della gestione degli accessi privilegiati offre un altro livello granulare di funzionalità di protezione e controllo per l'accesso con privilegi ai dati di Microsoft 365.

- **Abilitazione di Azure AD Privileged Identity Management mentre si usa già la gestione degli accessi con privilegi in Office 365:**  L'aggiunta di Azure AD Privileged Identity Management alla gestione degli accessi privilegiati può estendere l'accesso con privilegi ai dati esterni a Microsoft 365 definiti principalmente da ruoli utente o identità.  

## <a name="privileged-access-management-architecture-and-process-flow"></a>Architettura di gestione degli accessi privilegiati e flusso di processo

Ognuno dei flussi di processo seguenti delinea l'architettura dell'accesso privilegiato e il modo in cui interagisce con il substrato di Microsoft 365, il controllo e il runspace di gestione di Exchange.

### <a name="step-1-configure-a-privileged-access-policy"></a>Passaggio 1: Configurare un criterio di accesso con privilegi

Quando si configura un criterio di accesso con privilegi con l'interfaccia di amministrazione di [Microsoft 365](https://admin.microsoft.com) o Exchange Management PowerShell, si definiscono i criteri e i processi delle funzionalità di accesso con privilegi e gli attributi dei criteri nel substrato di Microsoft 365. Le attività vengono registrate nel Centro &amp; sicurezza e conformità. Il criterio è ora abilitato e pronto per gestire le richieste in arrivo per le approvazioni.

![Passaggio 1: creazione dei criteri](../media/pam-step1-policy-creation.jpg)

### <a name="step-2-access-request"></a>Passaggio 2: richiesta di accesso

Nell'interfaccia di amministrazione di [Microsoft 365](https://admin.microsoft.com) o con Exchange Management PowerShell, gli utenti possono richiedere l'accesso alle attività con privilegi o con privilegi elevati. La funzionalità di accesso con privilegi invia la richiesta al substrato di Microsoft 365 per l'elaborazione in base ai criteri di accesso con privilegi configurati e registra l'attività nei log del Centro &amp; sicurezza e conformità.

![Passaggio 2: richiesta di accesso](../media/pam-step2-access-request.jpg)

### <a name="step-3-access-approval"></a>Passaggio 3: approvazione dell'accesso

Viene generata una richiesta di approvazione e la notifica della richiesta in sospeso viene inviata tramite posta elettronica ai responsabili approvazione. Se approvata, la richiesta di accesso con privilegi viene elaborata come approvazione e l'attività è pronta per essere completata. Se negata, l'attività viene bloccata e non viene concesso alcun accesso al richiedente. Il richiedente viene informato dell'approvazione o del rifiuto della richiesta tramite un messaggio di posta elettronica.

![Passaggio 3: approvazione dell'accesso](../media/pam-step3-access-approval.jpg)

### <a name="step-4-access-processing"></a>Passaggio 4: elaborazione dell'accesso

Per una richiesta approvata, l'attività viene elaborata dal runspace Di gestione di Exchange. L'approvazione viene controllata rispetto ai criteri di accesso con privilegi ed elaborata dal substrato di Microsoft 365. Tutte le attività per l'attività vengono registrate nel Centro &amp; sicurezza e conformità.

![Passaggio 4: elaborazione dell'accesso](../media/pam-step4-access-processing.jpg)

## <a name="frequently-asked-questions"></a>Domande frequenti

### <a name="what-skus-can-use-privileged-access-in-office-365"></a>Quali SKU possono usare l'accesso con privilegi in Office 365?

La gestione degli accessi privilegiati è disponibile per i clienti per un'ampia selezione di abbonamenti e componenti aggiuntivi di Microsoft 365 e Office 365. Per [informazioni dettagliate, vedere Introduzione alla gestione degli accessi](privileged-access-management-configuration.md) con privilegi.

### <a name="when-will-privileged-access-support-office-365-workloads-beyond-exchange"></a>Quando l'accesso con privilegi supporterà i carichi di lavoro di Office 365 oltre Exchange?

La gestione degli accessi privilegiati sarà presto disponibile in altri carichi di lavoro di Office 365. Visitare la [roadmap di Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap) per ulteriori dettagli.

### <a name="my-organization-needs-more-than-30-privileged-access-policies-will-this-limit-be-increased"></a>L'organizzazione ha bisogno di più di 30 criteri di accesso con privilegi, questo limite verrà aumentato?

Sì, l'aumento del limite corrente di 30 criteri di accesso con privilegi per ogni organizzazione è nella roadmap delle funzionalità.

### <a name="do-i-need-to-be-a-global-admin-to-manage-privileged-access-in-office-365"></a>È necessario essere un amministratore globale per gestire l'accesso con privilegi in Office 365?

No, è necessario il ruolo Gestione ruoli di Exchange assegnato agli account che gestiscono l'accesso con privilegi in Office 365. Se non si desidera configurare il ruolo Gestione ruoli come autorizzazione account autonomo, il ruolo Amministratore globale include questo ruolo per impostazione predefinita e può gestire l'accesso con privilegi. Gli utenti inclusi in un gruppo di responsabili approvazione non devono essere un amministratore globale o avere il ruolo Gestione ruoli assegnato per esaminare e approvare le richieste con PowerShell.

### <a name="how-is-privileged-access-management-related-to-customer-lockbox"></a>In che modo la gestione degli accessi con privilegi è correlata a Customer Lockbox?

[Customer Lockbox consente](/office365/admin/manage/customer-lockbox-requests) un livello di controllo di accesso per le organizzazioni quando Microsoft accede ai dati. La gestione degli accessi privilegiati consente un controllo granulare degli accessi all'interno di un'organizzazione per tutte le attività con privilegi di Microsoft 365.

## <a name="ready-to-get-started"></a>Pronti per iniziare?

Iniziare [a configurare l'organizzazione per la gestione degli accessi con privilegi.](privileged-access-management-configuration.md)

## <a name="learn-more"></a>Ulteriori informazioni

[Guida interattiva: Monitorare e controllare le attività dell'amministratore con la gestione degli accessi con privilegi](https://content.cloudguides.com/guides/Privileged%20Access%20Management)
