---
title: Gestione degli accessi con privilegi in Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom: Ent_Solutions
ms.assetid: ''
description: Utilizzare questo argomento per ulteriori informazioni sulla gestione degli accessi con privilegi in Office 365
ms.openlocfilehash: 7547568d6ea2a13de5391d5a827df2921833838c
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37084434"
---
# <a name="privileged-access-management-in-office-365"></a>Gestione degli accessi con privilegi in Office 365

> [!IMPORTANT]
> In questo argomento vengono illustrate le linee guida per la distribuzione e la configurazione per le funzionalità disponibili solo in Office 365 E5 e SKU di conformità avanzate.

La gestione degli accessi con privilegi consente il controllo di accesso granulare sulle attività amministrative privilegiate in Office 365. Può aiutare a proteggere l'organizzazione da violazioni che utilizzano account amministratore privilegiati esistenti con accesso permanente ai dati sensibili o accesso alle impostazioni di configurazione critiche. La gestione degli accessi con privilegi richiede agli utenti di richiedere l'accesso just-in-time per completare le attività elevate e privilegiate tramite un flusso di lavoro di approvazione estremamente ambito e con limiti temporali. Questo consente agli utenti di accedere in modo sufficiente per eseguire l'attività a portata di mano, senza rischiare l'esposizione di dati sensibili o di impostazioni di configurazione critiche. L'abilitazione della gestione degli accessi con privilegi in Office 365 consente all'organizzazione di operare con privilegi zero e di fornire un livello di difesa contro le vulnerabilità di accesso amministrativo permanenti.

Per una breve panoramica sull'archivio protetto dei clienti integrato e sul flusso di lavoro per la gestione degli accessi con privilegi, vedere questa [cassetta del cliente e gestione degli accessi con privilegi in Office 365](https://go.microsoft.com/fwlink/?linkid=2066800).

## <a name="layers-of-protection"></a>Livelli di protezione

La gestione degli accessi con privilegi integra altre protezioni di funzionalità di accesso e di dati all'interno dell'architettura di sicurezza di Office 365. La gestione degli accessi con privilegi come parte di un approccio integrato e a livello di sicurezza fornisce un modello di sicurezza che massimizza la protezione delle informazioni riservate e le impostazioni di configurazione di Office 365. Come illustrato nel diagramma, la gestione degli accessi con privilegi si basa sulla protezione fornita con la crittografia nativa dei dati di Office 365 e sul modello di sicurezza per il controllo di accesso basato sui ruoli dei servizi di Office 365. Quando viene utilizzato con [Azure ad Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure), queste due funzionalità forniscono il controllo di accesso con accesso just-in-time a diversi ambiti.

![Protezione a più livelli in Office 365](media/pam-layered-protection.png)

La gestione degli accessi con privilegi in Office 365 è definita e portata a livello di **attività** , mentre Azure ad Privileged Identity Management applica la protezione a livello di **ruolo** con la possibilità di eseguire più attività. Azure AD Privileged Identity Management consente principalmente la gestione degli accessi per i ruoli di Active Directory e i gruppi di ruoli, mentre la gestione degli accessi con privilegi in Office 365 si applica solo a livello di attività.

- **Abilitazione della gestione degli accessi con privilegi in Office 365 mentre è già in uso Azure ad Privileged Identity Management:** L'aggiunta di gestione degli accessi con privilegi in Office 365 fornisce un altro livello granulare di funzionalità di protezione e controllo per l'accesso privilegiato ai dati di Office 365.

- **Abilitazione di Azure ad Privileged Identity Management già utilizzando la gestione degli accessi con privilegi in Office 365:**  L'aggiunta di Azure AD Privileged Identity Management alla gestione degli accessi con privilegi in Office 365 può estendere l'accesso privilegiato ai dati esterni a Office 365 che sono definiti principalmente dai ruoli o dall'identità dell'utente.  

## <a name="privileged-access-management-architecture-and-process-flow"></a>Architettura e flusso di processo di gestione degli accessi con privilegi

Ognuno dei seguenti flussi di processo descrive l'architettura dell'accesso con privilegi e la modalità di interazione con il substrato di Office 365, il controllo di Office 365 e l'Exchange Management Runspace.

### <a name="step-1-configure-a-privileged-access-policy"></a>Passaggio 1: configurare un criterio di accesso privilegiato

Quando si configura un criterio di accesso privilegiato con l'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com) o Exchange Management PowerShell, vengono definiti i criteri e i processi delle funzionalità di accesso privilegiato e gli attributi dei criteri nel supporto di Office 365. Le attività vengono registrate nel centro sicurezza e conformità di Office 365. Il criterio è ora abilitato e pronto per gestire le richieste in arrivo per le approvazioni.

![Passaggio 1: creazione di criteri](media/pam-step1-policy-creation.jpg)

### <a name="step-2-access-request"></a>Passaggio 2: richiesta di accesso

Nell'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com) o con Exchange Management PowerShell, gli utenti possono richiedere l'accesso a attività con privilegi elevati o di privilegio. La funzionalità accesso privilegiato Invia la richiesta al substrato Office 365 per l'elaborazione in base ai criteri di accesso ai privilegi configurati e registra l'attività nei registri del Centro sicurezza e conformità di Office 365.

![Passaggio 2: richiesta di accesso](media/pam-step2-access-request.jpg)

### <a name="step-3-access-approval"></a>Passaggio 3: accesso all'approvazione

Viene generata una richiesta di approvazione e la notifica della richiesta in sospeso viene inviata tramite posta elettronica ai responsabili approvazione. Se approvato, la richiesta di accesso privilegiato viene elaborata come approvazione e l'attività è pronta per essere completata. Se negato, l'attività viene bloccata e non viene concesso alcun accesso al richiedente. Il richiedente riceve una notifica dell'approvazione o della negazione della richiesta tramite il messaggio di posta elettronica.

![Passaggio 3: accesso all'approvazione](media/pam-step3-access-approval.jpg)

### <a name="step-4-access-processing"></a>Passaggio 4: accedere all'elaborazione

Per una richiesta approvata, l'attività viene elaborata da Exchange Management Runspace. L'approvazione viene controllata rispetto al criterio di accesso privilegiato ed elaborata dal supporto di stampa di Office 365. Tutte le attività per l'attività vengono registrate nel centro sicurezza e conformità di Office 365.

![Passaggio 4: accedere all'elaborazione](media/pam-step4-access-processing.jpg)

## <a name="frequently-asked-questions"></a>Domande frequenti

### <a name="what-skus-can-use-privileged-access-in-office-365"></a>Quali SKU possono utilizzare l'accesso con privilegi in Office 365?
La gestione degli accessi con privilegi è disponibile per i clienti con Office 365 E5 e SKU di conformità avanzate.

### <a name="when-will-privileged-access-support-office-365-workloads-beyond-exchange"></a>Quando verrà supportato l'accesso con privilegi Office 365 carichi di lavoro al di fuori di Exchange?
La gestione degli accessi con privilegi sarà disponibile in altri carichi di lavoro di Office 365. Per ulteriori informazioni, vedere la Guida di [orientamento a Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap) .

### <a name="my-organization-needs-more-than-30-privileged-access-policies-will-this-limit-be-increased"></a>L'organizzazione ha bisogno di più di 30 criteri di accesso privilegiato, questo limite verrà aumentato?
Sì, l'innalzamento del limite corrente di 30 criteri di accesso privilegiato per l'organizzazione di Office 365 è nella roadmap delle caratteristiche.

### <a name="do-i-need-to-be-a-global-admin-to-manage-privileged-access-in-office-365"></a>È necessario essere un amministratore globale per gestire l'accesso con privilegi in Office 365?
No, è necessario il ruolo di gestione dei ruoli di Exchange assegnato agli account che gestiscono l'accesso con privilegi in Office 365. Se non si desidera configurare il ruolo di gestione ruolo come autorizzazione Account autonomo, il ruolo amministratore globale include questo ruolo per impostazione predefinita e può gestire l'accesso con privilegi. Gli utenti inclusi nel gruppo dei responsabili approvazione non devono essere un amministratore globale o il ruolo di gestione dei ruoli è stato assegnato per esaminare e approvare le richieste.

### <a name="how-is-privileged-access-management-in-office-365-related-to-customer-lockbox"></a>In che modo la gestione degli accessi con privilegi in Office 365 è relativa all'archivio protetto dei clienti?
L' [archivio protetto dei clienti](https://docs.microsoft.com/office365/admin/manage/customer-lockbox-requests) consente un livello di controllo di accesso per le organizzazioni quando Microsoft accede ai dati. La gestione degli accessi con privilegi in Office 365 consente il controllo di accesso granulare all'interno di un'organizzazione per tutte le attività di Office 365.

## <a name="ready-to-get-started"></a>Pronti per iniziare?

Avviare [la configurazione dell'organizzazione per la gestione degli accessi con privilegi](privileged-access-management-configuration.md).

## <a name="learn-more"></a>Ulteriori informazioni

[Guida interattiva: monitorare e controllare le attività dell'amministratore con la gestione degli accessi con privilegi](https://content.cloudguides.com/en-us/guides/Privileged%20Access%20Management)