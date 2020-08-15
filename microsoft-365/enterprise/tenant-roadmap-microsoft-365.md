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
ms.openlocfilehash: db7054d1f6afc7e4835507dc6415e0b240918c1f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691507"
---
# <a name="tenant-roadmap-for-microsoft-365"></a>Guida di orientamento tenant per Microsoft 365

Il tenant Microsoft 365 è l'insieme di servizi assegnati alla propria organizzazione. Questo tenant è in genere associato a uno o più nomi di dominio DNS e funge da contenitore centrale per sottoscrizioni diverse e licenze all'interno delle quali viene assegnato agli account utente. 

Quando si crea un tenant di Microsoft 365, è possibile assegnarlo a una specifica posizione geografica. È inoltre possibile disporre di un tenant con più posizioni geografiche e spostare il tenant da una posizione a un'altra.

Una configurazione del tenant ben pianificata e eseguita è fondamentale per prepararla per i servizi di base della rete e dell'identità.

## <a name="plan"></a>Piano

Nella fase di pianificazione dell'implementazione tenant:

- [Comprendere gli abbonamenti, le licenze e i tenant di Azure Active Directory (Azure AD)](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [Informazioni su come utilizzare i certificati SSL di terze parti](plan-for-third-party-ssl-certificates.md)
- [Guide all'installazione di Access nell'interfaccia di amministrazione di Microsoft 365](setup-guides-for-microsoft-365.md)
- [Comprendere i modi in cui un tenant Microsoft 365 è integrato con i servizi di Azure AD](integrated-apps-and-azure-ads.md)
- [Pianificare il supporto delle app client](microsoft-365-client-support-certificate-based-authentication.md)
- [Determinare la modalità di utilizzo dell'autenticazione moderna ibrida](hybrid-modern-auth-overview.md)
- [Pianificare gli aggiornamenti di Office 2007 e Office 2010](plan-upgrade-previous-versions-office.md)
- [Comprendere l'isolamento del tenant](microsoft-365-tenant-isolation-overview.md)
- [Ottenere i dettagli su Microsoft 365 Service Assurance](https://docs.microsoft.com/microsoft-365/compliance/service-assurance)

## <a name="deploy"></a>Distribuisci

Nella fase di distribuzione dell'implementazione tenant, [aggiungere i domini DNS](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) per la propria organizzazione.

## <a name="tenants-with-multiple-geographic-locations"></a>Tenant con più posizioni geografiche

Con Microsoft 365 Multi-Geo l'organizzazione può espandere la presenza di Microsoft 365 a più paesi/aree geografiche all'interno del tenant esistente.

[Introduzione](microsoft-365-multi-geo.md) a Understanding, Planning, Configuring e then Administering with Microsoft 365 multi-Geo.

## <a name="moving-a-tenants-geographic-locations"></a>Spostamento delle posizioni geografiche di un tenant

Microsoft continua ad aprire nuove aree geografiche di datacenter (GEOS) per i servizi di Microsoft 365. Questi nuovi datacenter GEOS aggiungono capacità e risorse di calcolo per supportare la crescita della domanda e dell'utilizzo dei clienti. Inoltre, il nuovo datacenter GEOS offre la residenza di dati in-Geo per i dati di base dei clienti.

Informazioni introduttive sulla comprensione e la richiesta di spostamento di dati geo con lo [spostamento di dati di base in un nuovo datacenter geografico Microsoft 365](moving-data-to-new-datacenter-geos.md).

## <a name="next-step"></a>Passaggio successivo

Avviare la pianificazione del tenant con [abbonamenti, licenze, account e tenant](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).

