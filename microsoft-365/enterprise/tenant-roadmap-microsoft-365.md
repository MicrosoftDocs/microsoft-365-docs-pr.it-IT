---
title: Roadmap tenant per Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- m365initiative-coredeploy
ms.custom: it-pro
description: La roadmap per configurare i tenant per Microsoft 365.
ms.openlocfilehash: 4b94540293b86bd922ce4b29f970e52eb1245a01
ms.sourcegitcommit: 84e70051bb61b1171cebfbabe500b4904dfac04f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/16/2021
ms.locfileid: "53464034"
---
# <a name="tenant-roadmap-for-microsoft-365"></a>Roadmap tenant per Microsoft 365

Il Microsoft 365 tenant è il set di servizi assegnati all'organizzazione. In genere, questo tenant è associato a uno o più nomi di dominio DNS pubblici e funge da contenitore centrale e isolato per sottoscrizioni diverse e le licenze in essi assegnate agli account utente. Per ulteriori informazioni, vedere [Sottoscrizioni, licenze, account](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)e tenant per le offerte cloud di Microsoft.

Quando si crea un tenant Microsoft 365, lo si assegna a una posizione geografica specifica. È inoltre possibile avere un tenant con più posizioni geografiche e spostare il tenant da una posizione a un'altra.

Per preparare il tenant per utenti, gruppi, licenze e app cloud, è fondamentale pianificare ed eseguire con attenzione la configurazione del tenant.

## <a name="set-up-your-microsoft-365-tenant"></a>Configurare il tenant Microsoft 365 tenant

Dopo aver garantito che la rete sia ottimizzata per l'accesso a Microsoft 365 sia per i lavoratori locali che per i lavoratori remoti, le attività più importanti sono la pianificazione e la configurazione del tenant di Microsoft 365 per i nomi di dominio DNS, i servizi comuni e per l'infrastruttura di identità che supporta l'accesso utente sicuro.

### <a name="plan"></a>Pianificare

Per pianificare l'implementazione del tenant:

- [Informazioni su sottoscrizioni, licenze e tenant Azure Active Directory (Azure AD)](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [Informazioni su come usare certificati SSL di terze parti](plan-for-third-party-ssl-certificates.md)
- [Comprendere i modi in cui un tenant Microsoft 365 è integrato con i servizi di Azure AD](integrated-apps-and-azure-ads.md)
- [Pianificare il supporto delle app client](microsoft-365-client-support-certificate-based-authentication.md)
- [Determinare come usare l'autenticazione moderna ibrida](hybrid-modern-auth-overview.md)
- [Pianificare gli Office 2007 e Office 2010](plan-upgrade-previous-versions-office.md)
- [Comprendere l'isolamento del tenant](/compliance/assurance/microsoft-365-isolation-controls)

### <a name="deploy"></a>Distribuzione

Per distribuire il tenant: 

- Aggiungere i [domini DNS](../admin/setup/add-domain.md) per l'organizzazione.
- Utilizzare le [guide all'installazione nella interfaccia di amministrazione di Microsoft 365](setup-guides-for-microsoft-365.md).
- Creare [l'infrastruttura di identità](identity-roadmap-microsoft-365.md) e proteggere gli account di accesso degli [utenti.](microsoft-365-secure-sign-in.md)

### <a name="move-a-tenants-geographic-locations"></a>Spostare le posizioni geografiche di un tenant

Microsoft continua ad aprire nuove posizioni geografiche del datacenter (geo) per Microsoft 365 servizi. Questi nuovi geo datacenter aggiungono capacità e risorse di calcolo per supportare la domanda dei clienti e la crescita dell'utilizzo. Inoltre, i nuovi dati geografici del datacenter offrono la residenza dei dati in-geo per i dati principali dei clienti.

Per ulteriori informazioni, vedere [Moving core data to new Microsoft 365 datacenter geos](moving-data-to-new-datacenter-geos.md).


## <a name="deploy-microsoft-365-multi-geo"></a>Distribuire Microsoft 365 Multi-Geo

Con Microsoft 365 Multi-Geo l'organizzazione può espandere la presenza di Microsoft 365 a più paesi/aree geografiche all'interno del tenant esistente.

Per ulteriori informazioni, vedere [Microsoft 365 Multi-Geo](microsoft-365-multi-geo.md).

## <a name="manage-multiple-microsoft-365-tenants"></a>Gestire più Microsoft 365 tenant 

Anche se avere un singolo tenant per la tua oganizzazione è ideale, potresti essere una delle molte organizzazioni che hanno più tenant. I motivi possono includere fusioni e acquisizioni, si desidera l'isolamento amministrativo o si dispone di un'IT decentralizzata.

Se si dispone di Microsoft 365 tenant, vedere questi articoli per ulteriori informazioni su:

- [Collaborazione tra tenant](microsoft-365-inter-tenant-collaboration.md)
- [Migrazione delle cassette postali tra tenant](cross-tenant-mailbox-migration.md)
- [Migrazioni da tenant a tenant](microsoft-365-tenant-to-tenant-migrations.md)

## <a name="next-step"></a>Passaggio successivo

Iniziare la pianificazione del tenant [con Sottoscrizioni, licenze, account e tenant.](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)