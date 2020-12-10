---
title: Informazioni sulla gestione degli accessi con privilegi
description: In questo articolo viene fornita una panoramica della gestione degli accessi con privilegi in Microsoft 365, incluse le risposte alle domande frequenti.
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
ms.openlocfilehash: dc7c6807e8c89b4146784e5be7f57472777a4c84
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613330"
---
# <a name="learn-about-privileged-access-management"></a>Informazioni sulla gestione degli accessi con privilegi

La gestione degli accessi con privilegi consente il controllo di accesso granulare sulle attività amministrative privilegiate in Office 365. Può aiutare a proteggere l'organizzazione da violazioni che utilizzano account amministratore privilegiati esistenti con accesso permanente ai dati sensibili o accesso alle impostazioni di configurazione critiche. La gestione degli accessi con privilegi richiede agli utenti di richiedere l'accesso just-in-time per completare le attività elevate e privilegiate tramite un flusso di lavoro di approvazione estremamente ambito e con limiti temporali. Questa configurazione consente agli utenti di accedere in modo sufficiente per eseguire l'attività a portata di mano, senza rischiare l'esposizione di dati sensibili o di impostazioni di configurazione critiche. L'abilitazione della gestione degli accessi con privilegi in Microsoft 365 consente all'organizzazione di operare con privilegi zero e di fornire un livello di difesa contro le vulnerabilità di accesso amministrativo permanenti.

Per una breve panoramica sull'archivio protetto dei clienti integrato e sul flusso di lavoro per la gestione degli accessi con privilegi, vedere questo [archivio clienti e gestione accesso privilegiato](https://go.microsoft.com/fwlink/?linkid=2066800).

## <a name="layers-of-protection"></a>Livelli di protezione

La gestione degli accessi con privilegi integra altre protezioni di funzionalità di accesso e di dati all'interno dell'architettura di sicurezza di Microsoft 365. La gestione degli accessi con privilegi come parte di un approccio integrato e a livello di sicurezza fornisce un modello di sicurezza che massimizza la protezione delle informazioni riservate e le impostazioni di configurazione di Microsoft 365. Come illustrato nel diagramma, la gestione degli accessi con privilegi si basa sulla protezione fornita con la crittografia nativa dei dati di Microsoft 365 e sul modello di sicurezza per il controllo di accesso basato sui ruoli dei servizi di Microsoft 365. Quando viene utilizzato con [Azure ad Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure), queste due funzionalità forniscono il controllo di accesso con accesso just-in-time a diversi ambiti.

![Protezione a più livelli in Microsoft 365](../media/pam-layered-protection.png)

La gestione degli accessi con privilegi è definita e portata a livello di **attività** , mentre Azure ad Privileged Identity Management applica la protezione a livello di **ruolo** con la possibilità di eseguire più attività. Azure AD Privileged Identity Management consente principalmente la gestione degli accessi per i ruoli di Active Directory e i gruppi di ruoli, mentre la gestione degli accessi con privilegi in Microsoft 365 si applica solo a livello di attività.

- **Abilitazione della gestione degli accessi con privilegi durante la gestione di Azure ad Privileged Identity Management:** L'aggiunta di gestione accessi con privilegi fornisce un altro livello granulare di funzionalità di protezione e controllo per l'accesso privilegiato ai dati di Microsoft 365.

- **Abilitazione di Azure ad Privileged Identity Management già utilizzando la gestione degli accessi con privilegi in Office 365:**  L'aggiunta di Azure AD Privileged Identity Management alla gestione degli accessi con privilegi può estendere l'accesso privilegiato ai dati esterni a Microsoft 365 che sono definiti principalmente da ruoli utente o identità.  

## <a name="privileged-access-management-architecture-and-process-flow"></a>Architettura e flusso di processo di gestione degli accessi con privilegi

Ognuno dei seguenti flussi di processo descrive l'architettura dell'accesso con privilegi e la modalità di interazione con il substrato di Microsoft 365, il controllo e l'Exchange Management Runspace.

### <a name="step-1-configure-a-privileged-access-policy"></a>Passaggio 1: configurare un criterio di accesso privilegiato

Quando si configura un criterio di accesso privilegiato con l'interfaccia di [amministrazione di microsoft 365](https://admin.microsoft.com) o Exchange Management PowerShell, è possibile definire i criteri e i processi delle funzionalità di accesso privilegiato e gli attributi dei criteri nel supporto di stampa di Microsoft 365. Le attività vengono registrate nel centro sicurezza e &amp; conformità. Il criterio è ora abilitato e pronto per gestire le richieste in arrivo per le approvazioni.

![Passaggio 1: creazione di criteri](../media/pam-step1-policy-creation.jpg)

### <a name="step-2-access-request"></a>Passaggio 2: richiesta di accesso

Nell'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com) o con Exchange Management PowerShell, gli utenti possono richiedere l'accesso a attività con privilegi elevati o di privilegio. La funzionalità accesso privilegiato Invia la richiesta al substrato Microsoft 365 per l'elaborazione in base ai criteri di accesso ai privilegi configurati e registra l'attività nei registri del Centro sicurezza e &amp; conformità.

![Passaggio 2: richiesta di accesso](../media/pam-step2-access-request.jpg)

### <a name="step-3-access-approval"></a>Passaggio 3: accesso all'approvazione

Viene generata una richiesta di approvazione e la notifica della richiesta in sospeso viene inviata tramite posta elettronica ai responsabili approvazione. Se approvato, la richiesta di accesso privilegiato viene elaborata come approvazione e l'attività è pronta per essere completata. Se negato, l'attività viene bloccata e non viene concesso alcun accesso al richiedente. Il richiedente riceve una notifica dell'approvazione o della negazione della richiesta tramite il messaggio di posta elettronica.

![Passaggio 3: accesso all'approvazione](../media/pam-step3-access-approval.jpg)

### <a name="step-4-access-processing"></a>Passaggio 4: accedere all'elaborazione

Per una richiesta approvata, l'attività viene elaborata da Exchange Management Runspace. L'approvazione viene controllata rispetto al criterio di accesso privilegiato ed elaborata dal supporto tecnico Microsoft 365. Tutte le attività per l'attività vengono registrate nel centro sicurezza e &amp; conformità.

![Passaggio 4: accedere all'elaborazione](../media/pam-step4-access-processing.jpg)

## <a name="frequently-asked-questions"></a>Domande frequenti

### <a name="what-skus-can-use-privileged-access-in-office-365"></a>Quali SKU possono utilizzare l'accesso con privilegi in Office 365?

La gestione degli accessi con privilegi è disponibile per i clienti per una vasta gamma di abbonamenti e componenti aggiuntivi di Microsoft 365 e Office 365. Per informazioni dettagliate, vedere [Introduzione alla gestione degli accessi con privilegi](privileged-access-management-configuration.md) .

### <a name="when-will-privileged-access-support-office-365-workloads-beyond-exchange"></a>Quando verrà supportato l'accesso con privilegi Office 365 carichi di lavoro al di fuori di Exchange?

La gestione degli accessi con privilegi sarà disponibile in altri carichi di lavoro di Office 365. Per ulteriori informazioni, vedere la Guida di [orientamento a Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap) .

### <a name="my-organization-needs-more-than-30-privileged-access-policies-will-this-limit-be-increased"></a>L'organizzazione ha bisogno di più di 30 criteri di accesso privilegiato, questo limite verrà aumentato?

Sì, l'innalzamento del limite corrente di 30 criteri di accesso privilegiato per organizzazione è nella roadmap delle caratteristiche.

### <a name="do-i-need-to-be-a-global-admin-to-manage-privileged-access-in-office-365"></a>È necessario essere un amministratore globale per gestire l'accesso con privilegi in Office 365?

No, è necessario il ruolo di gestione dei ruoli di Exchange assegnato agli account che gestiscono l'accesso con privilegi in Office 365. Se non si desidera configurare il ruolo di gestione ruolo come autorizzazione Account autonomo, il ruolo amministratore globale include questo ruolo per impostazione predefinita e può gestire l'accesso con privilegi. Gli utenti inclusi nel gruppo dei responsabili approvazione non devono essere un amministratore globale o hanno il ruolo di gestione dei ruoli assegnato per esaminare e approvare le richieste con PowerShell.

### <a name="how-is-privileged-access-management-related-to-customer-lockbox"></a>Come è la gestione degli accessi con privilegi correlati all'archivio protetto dei clienti?

L' [archivio protetto dei clienti](https://docs.microsoft.com/office365/admin/manage/customer-lockbox-requests) consente un livello di controllo di accesso per le organizzazioni quando Microsoft accede ai dati. La gestione degli accessi con privilegi consente il controllo di accesso granulare all'interno di un'organizzazione per tutte le attività con privilegi 365 Microsoft

## <a name="ready-to-get-started"></a>Pronti per iniziare?

Avviare [la configurazione dell'organizzazione per la gestione degli accessi con privilegi](privileged-access-management-configuration.md).

## <a name="learn-more"></a>Ulteriori informazioni

[Guida interattiva: monitorare e controllare le attività dell'amministratore con la gestione degli accessi con privilegi](https://content.cloudguides.com/guides/Privileged%20Access%20Management)
