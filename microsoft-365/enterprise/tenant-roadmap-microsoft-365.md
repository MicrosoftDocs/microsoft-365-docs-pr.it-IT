---
title: Guida di orientamento tenant per Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/10/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- m365initiative-coredeploy
ms.custom: it-pro
description: La Guida di orientamento per la configurazione dei tenant per Microsoft 365.
ms.openlocfilehash: db0f9552fce460ca6d25ee74ea2031bea388b8dc
ms.sourcegitcommit: 3b1bd8aa1430bc9565743a446bbc27b199f30f73
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2020
ms.locfileid: "48656008"
---
# <a name="tenant-roadmap-for-microsoft-365"></a>Guida di orientamento tenant per Microsoft 365

Il tenant Microsoft 365 è l'insieme di servizi assegnati alla propria organizzazione. In genere, questo tenant è associato a uno o più nomi di dominio DNS e funge da contenitore centrale per sottoscrizioni diverse e licenze all'interno delle quali viene assegnato agli account utente. Per ulteriori informazioni, vedere [abbonamenti, licenze, account e tenant per offerte cloud di Microsoft](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).

Quando si crea un tenant di Microsoft 365, è possibile assegnarlo a una specifica posizione geografica. È inoltre possibile disporre di un tenant con più posizioni geografiche e spostare il tenant da una posizione a un'altra.

Per ottenere il tenant pronto per l'identità, è importante pianificare attentamente ed eseguire la configurazione del tenant.


## <a name="set-up-your-microsoft-365-tenant"></a>Configurare il tenant di Microsoft 365

Dopo aver verificato che la rete sia stata ottimizzata per l'accesso a Microsoft 365 sia per gli addetti locali che per i dipendenti remoti, le attività importanti successive stanno pianificando e configurando il tenant di Microsoft 365 per i nomi di dominio DNS, i servizi comuni e l'infrastruttura di identità che supporta l'accesso sicuro degli utenti.

## <a name="plan"></a>Piano

Per pianificare l'implementazione del tenant:

- [Comprendere gli abbonamenti, le licenze e i tenant di Azure Active Directory (Azure AD)](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [Informazioni su come utilizzare i certificati SSL di terze parti](plan-for-third-party-ssl-certificates.md)
- [Comprendere i modi in cui un tenant Microsoft 365 è integrato con i servizi di Azure AD](integrated-apps-and-azure-ads.md)
- [Pianificare il supporto delle app client](microsoft-365-client-support-certificate-based-authentication.md)
- [Determinare la modalità di utilizzo dell'autenticazione moderna ibrida](hybrid-modern-auth-overview.md)
- [Pianificare gli aggiornamenti di Office 2007 e Office 2010](plan-upgrade-previous-versions-office.md)
- [Comprendere l'isolamento del tenant](microsoft-365-tenant-isolation-overview.md)
- [Ottenere i dettagli su Microsoft 365 Service Assurance](microsoft-365-administrative-access-controls-overview.md)

### <a name="deploy"></a>Distribuzione

Per distribuire il tenant: 

- Aggiungere i [domini DNS](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) per la propria organizzazione.
- Utilizzare le [guide all'installazione nell'interfaccia di amministrazione di Microsoft 365](setup-guides-for-microsoft-365.md).
- Creare l' [infrastruttura di identità](identity-roadmap-microsoft-365.md) e [proteggere gli accessi degli utenti](microsoft-365-secure-sign-in.md).

### <a name="move-a-tenants-geographic-locations"></a>Spostare le posizioni geografiche di un tenant

Microsoft continua ad aprire nuove aree geografiche di datacenter (GEOS) per i servizi di Microsoft 365. Questi nuovi datacenter GEOS aggiungono capacità e risorse di calcolo per supportare la crescita della domanda e dell'utilizzo dei clienti. Inoltre, il nuovo datacenter GEOS offre la residenza di dati in-Geo per i dati di base dei clienti.

Per ulteriori informazioni, vedere [Moving core data to New Microsoft 365 datacenter GEOS](moving-data-to-new-datacenter-geos.md).


## <a name="deploy-microsoft-365-multi-geo"></a>Distribuire Microsoft 365 multi-Geo

Con Microsoft 365 Multi-Geo l'organizzazione può espandere la presenza di Microsoft 365 a più paesi/aree geografiche all'interno del tenant esistente.

Per ulteriori informazioni, vedere [Microsoft 365 multi-Geo](microsoft-365-multi-geo.md).

## <a name="manage-multiple-microsoft-365-tenancies"></a>Gestire più Microsoft 365 locazione 

Anche se l'utilizzo di un singolo tenant per il Oganization è ideale, potrebbe essere una delle numerose organizzazioni con più locazione. Per motivi multipli di locazione è possibile includere fusioni e acquisizioni, si desidera l'isolamento amministrativo o si dispone di una decentralizzata.

Se si dispone di più di Microsoft 365 locazione, vedere questi articoli per ulteriori informazioni su:

- [Collaborazione tra tenant](microsoft-365-inter-tenant-collaboration.md)
- [Migrazione delle cassette postali tra tenant](cross-tenant-mailbox-migration.md)
- [Migrazioni da tenant a tenant](microsoft-365-tenant-to-tenant-migrations.md)


## <a name="next-step"></a>Passaggio successivo

Avviare la pianificazione del tenant con [abbonamenti, licenze, account e tenant](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).
