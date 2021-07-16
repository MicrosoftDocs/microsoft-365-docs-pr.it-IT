---
title: Controlli di isolamento Microsoft 365
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
description: Scopri come funzionano i controlli di isolamento Microsoft 365, consentendo ai servizi di operare o rimanere autonomi in base alle esigenze.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 514b12e44d9e81a18b691ebf3196a3d21157e71b
ms.sourcegitcommit: 27addd4dac07926528b788215d2dcd0e46301eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/16/2021
ms.locfileid: "53464096"
---
# <a name="microsoft-365-isolation-controls"></a>Controlli di isolamento Microsoft 365 

Microsoft lavora continuamente per garantire che l'architettura multi-tenant di Microsoft 365 supporti gli standard di sicurezza, riservatezza, privacy, integrità, locale, internazionale e disponibilità a [livello aziendale.](https://www.microsoft.com/TrustCenter/Compliance?service=Office#Icons) La scalabilità e l'ambito dei servizi forniti da Microsoft rendono difficile e non economica la gestione delle Microsoft 365 con un'interazione umana significativa. Microsoft 365 sono forniti tramite più data center distribuiti a livello globale, ognuno altamente automatizzato con poche operazioni che richiedono un tocco umano o qualsiasi accesso al contenuto dei clienti. Il nostro staff supporta questi servizi e data center utilizzando strumenti automatizzati e un accesso remoto estremamente sicuro. 

Microsoft 365 è costituito da più servizi che forniscono importanti funzionalità aziendali e contribuiscono all'intera esperienza Microsoft 365 aziendale. Ognuno di questi servizi è autonomo e progettato per l'integrazione tra loro.

Microsoft 365 è progettato con i principi seguenti:

 - **[Architettura orientata ai servizi](/previous-versions/aa480021(v=msdn.10)):** progettazione e sviluppo di software sotto forma di servizi interoperabili che forniscono funzionalità aziendali ben definite.
 - **[Garanzia di](https://www.microsoft.com/download/details.aspx?id=40872)** sicurezza operativa : un framework che incorpora le conoscenze acquisite attraverso varie funzionalità uniche per Microsoft, tra cui Microsoft [Security Development Lifecycle,](https://www.microsoft.com/sdl/default.aspx) [Microsoft Security Response Center](https://technet.microsoft.com/library/dn440717.aspx)e una profonda consapevolezza del panorama delle minacce alla cybersecurity.

Microsoft 365 i servizi operano tra loro, ma sono progettati e implementati in modo che possano essere distribuiti e gestiti come servizi autonomi, indipendenti l'uno dall'altro. Microsoft separa i compiti e le aree di responsabilità Microsoft 365 ridurre le opportunità di modifica non autorizzata o involontaria o uso improprio delle risorse dell'organizzazione. Microsoft 365 team hanno definito ruoli come parte di un meccanismo completo di controllo degli accessi basato sui ruoli.

## <a name="customer-content-isolation"></a>Isolamento del contenuto del cliente

Tutto il contenuto dei clienti in un tenant è isolato da altri tenant e dai dati relativi alle operazioni e ai sistemi utilizzati nella gestione di Microsoft 365. In tutto il Microsoft 365 vengono implementate più forme di protezione per ridurre al minimo il rischio di compromissione di Microsoft 365 servizio o applicazione. Più forme di protezione impediscono inoltre l'accesso non autorizzato alle informazioni dei tenant o del Microsoft 365 stesso sistema.

Per informazioni su come Microsoft implementa l'isolamento logico dei dati del tenant Microsoft 365, vedere [Isolamento tenant in Microsoft 365](microsoft-365-tenant-isolation-overview.md).