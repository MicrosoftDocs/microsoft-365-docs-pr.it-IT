---
title: Controlli di isolamento di Microsoft 365
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: Informazioni su come funzionano i controlli di isolamento all'interno di Microsoft 365, consentendo ai servizi di interoperare o rimanere autonomi in base alle esigenze.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bb0989f19002267ab92bf184a12a4076f753580e
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332377"
---
# <a name="microsoft-365-isolation-controls"></a>Controlli di isolamento di Microsoft 365 

Microsoft continua a funzionare per garantire che l'architettura multi-tenant di Microsoft 365 supporti la sicurezza a livello aziendale, la riservatezza, la privacy, l'integrità, [gli standard](https://www.microsoft.com/TrustCenter/Compliance?service=Office#Icons)locali, internazionali e di disponibilità. La scalabilità e l'ambito dei servizi forniti da Microsoft rendono difficile e non economico gestire Microsoft 365 con una significativa interazione umana. I servizi Microsoft 365 sono forniti tramite più data center distribuiti a livello globale, ognuno estremamente automatizzato con poche operazioni che richiedono un contatto umano o qualsiasi accesso al contenuto del cliente. Il personale supporta questi servizi e Data Center utilizzando strumenti automatici e l'accesso remoto estremamente sicuro. 

Microsoft 365 è costituito da più servizi che forniscono importanti funzionalità aziendali e contribuiscono all'intera esperienza di Microsoft 365. Ognuno di questi servizi è autonomo e ha lo scopo di integrarsi tra loro.

Microsoft 365 è stato creato con i principi seguenti:

 - ** [Architettura orientata ai servizi](https://docs.microsoft.com/previous-versions/aa480021(v=msdn.10)):** la progettazione e lo sviluppo di software in forma di servizi interoperabili che forniscono funzionalità aziendali ben definite.
 - **[Garanzia di sicurezza operativa](https://www.microsoft.com/download/details.aspx?id=40872):** Framework che include le conoscenze acquisite tramite diverse funzionalità esclusive di Microsoft, tra cui il ciclo di vita [dello sviluppo della sicurezza](https://www.microsoft.com/sdl/default.aspx)di Microsoft, il [Centro sicurezza e risposta](https://technet.microsoft.com/library/dn440717.aspx)di Microsoft e la profonda consapevolezza del panorama delle minacce di Cybersecurity.

I servizi Microsoft 365 interagiscono tra loro, ma sono stati disegnati e implementati in modo che possano essere distribuiti e gestiti come servizi autonomi, indipendenti l'uno dall'altro. Microsoft segrega i compiti e le aree di responsabilità di Microsoft 365 per ridurre le opportunità di modifiche non autorizzate o involontarie o di uso improprio dei cespiti dell'organizzazione. I team di Microsoft 365 dispongono di ruoli definiti come parte di un meccanismo completo di controllo dell'accesso basato sui ruoli.

## <a name="customer-content-isolation"></a>Isolamento del contenuto del cliente

Tutto il contenuto del cliente in un tenant è isolato da altri tenant e dai dati relativi a operazioni e sistemi utilizzati per la gestione di Microsoft 365. Più forme di protezione vengono implementate in Microsoft 365 per ridurre al minimo il rischio di compromesso di qualsiasi applicazione o servizio Microsoft 365. Anche più forme di protezione impediscono l'accesso non autorizzato alle informazioni dei tenant o del sistema Microsoft 365 stesso.

Per informazioni su come Microsoft implementi l'isolamento logico dei dati del tenant all'interno di Microsoft 365, vedere [tenant isolation in microsoft 365](microsoft-365-tenant-isolation-overview.md).
