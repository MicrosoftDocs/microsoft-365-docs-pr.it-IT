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
ms.collection: M365-subscription-management
ms.custom: it-pro
description: La Guida di orientamento per la configurazione dei tenant per Microsoft 365.
ms.openlocfilehash: 7834e8b7f9ff8a1b33f2f2a7ccc4a499e4da7c69
ms.sourcegitcommit: 13ae76220b4ad688438a5d1031a6e1b5300ffa23
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/15/2020
ms.locfileid: "47775148"
---
# <a name="tenant-roadmap-for-microsoft-365"></a>Guida di orientamento tenant per Microsoft 365

Il tenant Microsoft 365 è l'insieme di servizi assegnati alla propria organizzazione. In genere, questo tenant è associato a uno o più nomi di dominio DNS e funge da contenitore centrale per sottoscrizioni diverse e licenze all'interno delle quali viene assegnato agli account utente.

Quando si crea un tenant di Microsoft 365, è possibile assegnarlo a una specifica posizione geografica. È inoltre possibile disporre di un tenant con più posizioni geografiche e spostare il tenant da una posizione a un'altra.

Per ottenere il tenant pronto per i servizi di base della rete e dell'identità, è importante pianificare attentamente ed eseguire la configurazione del tenant.

## <a name="plan"></a>Piano

Per pianificare l'implementazione del tenant:

- [Comprendere gli abbonamenti, le licenze e i tenant di Azure Active Directory (Azure AD)](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [Informazioni su come utilizzare i certificati SSL di terze parti](plan-for-third-party-ssl-certificates.md)
- [Guide all'installazione di Access nell'interfaccia di amministrazione di Microsoft 365](setup-guides-for-microsoft-365.md)
- [Comprendere i modi in cui un tenant Microsoft 365 è integrato con i servizi di Azure AD](integrated-apps-and-azure-ads.md)
- [Pianificare il supporto delle app client](microsoft-365-client-support-certificate-based-authentication.md)
- [Determinare la modalità di utilizzo dell'autenticazione moderna ibrida](hybrid-modern-auth-overview.md)
- [Pianificare gli aggiornamenti di Office 2007 e Office 2010](plan-upgrade-previous-versions-office.md)
- [Comprendere l'isolamento del tenant](microsoft-365-tenant-isolation-overview.md)
- [Ottenere i dettagli su Microsoft 365 Service Assurance](https://docs.microsoft.com/microsoft-365/compliance/service-assurance)

## <a name="deploy"></a>Distribuire

Per distribuire il tenant, [aggiungere i domini DNS](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) per la propria organizzazione.

## <a name="tenants-with-multiple-geographic-locations"></a>Tenant con più posizioni geografiche

Con Microsoft 365 Multi-Geo l'organizzazione può espandere la presenza di Microsoft 365 a più paesi/aree geografiche all'interno del tenant esistente.

Per informazioni su Microsoft 365 multi-Geo, inclusa la pianificazione, la configurazione e l'amministrazione, [iniziare da qui](microsoft-365-multi-geo.md).

## <a name="move-a-tenants-geographic-locations"></a>Spostare le posizioni geografiche di un tenant

Microsoft continua ad aprire nuove aree geografiche di datacenter (GEOS) per i servizi di Microsoft 365. Questi nuovi datacenter GEOS aggiungono capacità e risorse di calcolo per supportare la crescita della domanda e dell'utilizzo dei clienti. Inoltre, il nuovo datacenter GEOS offre la residenza di dati in-Geo per i dati di base dei clienti.

Per informazioni su Microsoft 365 datacenter Geo, incluso il modo in cui richiedere una mossa di geo data, [iniziare da qui](moving-data-to-new-datacenter-geos.md).

## <a name="next-step"></a>Passaggio successivo

Avviare la pianificazione del tenant con [abbonamenti, licenze, account e tenant](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).

