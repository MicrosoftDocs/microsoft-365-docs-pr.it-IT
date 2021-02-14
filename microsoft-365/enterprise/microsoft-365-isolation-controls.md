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
description: Informazioni sul funzionamento dei controlli di isolamento in Microsoft 365, consentendo ai servizi di operare o rimanere autonomi in base alle esigenze.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bb0989f19002267ab92bf184a12a4076f753580e
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332377"
---
# <a name="microsoft-365-isolation-controls"></a>Controlli di isolamento di Microsoft 365 

Microsoft lavora continuamente per garantire che l'architettura multi-tenant di Microsoft 365 supporti gli standard di sicurezza, riservatezza, privacy, integrità, locale, internazionale e disponibilità a [livello aziendale.](https://www.microsoft.com/TrustCenter/Compliance?service=Office#Icons) La scalabilità e l'ambito dei servizi forniti da Microsoft rendono difficile e non economico gestire Microsoft 365 con un'interazione umana significativa. I servizi di Microsoft 365 vengono forniti tramite più data center distribuiti a livello globale, ognuno altamente automatizzato con poche operazioni che richiedono un tocco umano o qualsiasi accesso ai contenuti dei clienti. Il nostro personale supporta questi servizi e data center utilizzando strumenti automatizzati e accesso remoto altamente sicuro. 

Microsoft 365 è composto da più servizi che forniscono importanti funzionalità aziendali e contribuiscono all'intera esperienza di Microsoft 365. Ognuno di questi servizi è autonomo e progettato per l'integrazione tra loro.

Microsoft 365 è progettato con i principi seguenti:

 - **[Architettura orientata ai servizi:](https://docs.microsoft.com/previous-versions/aa480021(v=msdn.10))** progettazione e sviluppo di software sotto forma di servizi interoperabili che forniscono funzionalità aziendali ben definite.
 - **[Garanzia](https://www.microsoft.com/download/details.aspx?id=40872)** di sicurezza operativa : un framework che incorpora le conoscenze acquisite tramite varie funzionalità uniche di Microsoft, tra cui Microsoft [Security Development Lifecycle,](https://www.microsoft.com/sdl/default.aspx) [Microsoft Security Response Center](https://technet.microsoft.com/library/dn440717.aspx)e una conoscenza approfondita del panorama delle minacce alla sicurezza informatica.

I servizi di Microsoft 365 operano tra loro, ma sono progettati e implementati in modo che possano essere distribuiti e gestiti come servizi autonomi, indipendentemente l'uno dall'altro. Microsoft separa i compiti e le aree di responsabilità per Microsoft 365 per ridurre le opportunità di modifica non autorizzata o involontaria o uso improprio delle risorse dell'organizzazione. I team di Microsoft 365 hanno ruoli definiti come parte di un meccanismo completo di controllo degli accessi basato sui ruoli.

## <a name="customer-content-isolation"></a>Isolamento del contenuto del cliente

Tutto il contenuto dei clienti in un tenant è isolato dagli altri tenant e dai dati relativi alle operazioni e ai sistemi utilizzati nella gestione di Microsoft 365. In Microsoft 365 vengono implementate più forme di protezione per ridurre al minimo il rischio di compromissione di qualsiasi servizio o applicazione di Microsoft 365. Più forme di protezione impediscono anche l'accesso non autorizzato alle informazioni dei tenant o del sistema Microsoft 365 stesso.

Per informazioni su come Microsoft implementa l'isolamento logico dei dati del tenant in Microsoft 365, vedere [Isolamento del tenant in Microsoft 365.](microsoft-365-tenant-isolation-overview.md)
