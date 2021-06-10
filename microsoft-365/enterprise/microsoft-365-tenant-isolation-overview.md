---
title: Isolamento tenant in Microsoft 365
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
description: Questo articolo contiene un riepilogo di come Microsoft applica l'isolamento dei tenant in servizi cloud come Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7c5be65186b75f6056a64b776e4f0d25bcd55eb1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923077"
---
# <a name="tenant-isolation-in-microsoft-365"></a>Isolamento tenant in Microsoft 365

Uno dei principali vantaggi del cloud computing è il concetto di un'infrastruttura condivisa e comune tra numerosi clienti contemporaneamente, che porta a un'economia di scala. Questo concetto è denominato *multi-tenancy.* Microsoft lavora costantemente per garantire che le architetture multi-tenant dei nostri servizi cloud supportino gli standard di sicurezza, riservatezza, privacy, integrità e disponibilità a livello aziendale.

In base agli investimenti e all'esperienza significativi raccolti da [Trustworthy Computing](https://www.microsoft.com/trust-center) e dal Ciclo di vita dello sviluppo della [sicurezza,](https://www.microsoft.com/securityengineering/sdl/)i servizi cloud Microsoft sono stati progettati presupponendo che tutti i tenant siano potenzialmente ostile a tutti gli altri tenant e che siano state implementate misure di sicurezza per impedire che le azioni di un tenant influiscano sulla sicurezza o sul servizio di un altro tenant o sull'accesso al contenuto di un altro tenant.

I due obiettivi principali della gestione dell'isolamento del tenant in un ambiente multi-tenant sono:

1.    Impedire la perdita o l'accesso non autorizzato al contenuto dei clienti tra tenant; e
2.    Impedire alle azioni di un tenant di influire negativamente sul servizio per un altro tenant

In tutto il Microsoft 365 sono state implementate più forme di protezione per impedire ai clienti di compromettere i servizi o le applicazioni di Microsoft 365 o di ottenere l'accesso non autorizzato alle informazioni di altri tenant o del sistema Microsoft 365 stesso, tra cui:

- L'isolamento logico del contenuto dei clienti all'interno di ogni tenant per Microsoft 365 servizi viene ottenuto Azure Active Directory'autorizzazione e il controllo dell'accesso basato sui ruoli.
- SharePoint Online fornisce meccanismi di isolamento dei dati a livello di archiviazione.
- Microsoft usa una rigorosa sicurezza fisica, screening in background e una strategia di crittografia a più livelli per proteggere la riservatezza e l'integrità dei contenuti dei clienti. Tutti Microsoft 365 data center dispongono di controlli di accesso biometrici, con la maggior parte delle stampe palm per ottenere l'accesso fisico. Inoltre, tutti i dipendenti Microsoft con sede negli Stati Uniti devono completare correttamente un controllo in background standard nell'ambito del processo di assunzione. Per ulteriori informazioni sui controlli utilizzati per l'accesso amministrativo in Microsoft 365, vedere [Microsoft 365 Administrative Access Controls](/compliance/assurance/assurance-administrative-access-controls-overview).
- Microsoft 365 utilizza tecnologie sul lato servizio che crittografano i contenuti dei clienti in transito e in pausa, tra cui BitLocker, crittografia per file, TLS (Transport Layer Security) e IPsec (Internet Protocol Security). Per informazioni dettagliate sulla crittografia in Microsoft 365, vedere [Data Encryption Technologies in Microsoft 365](../compliance/office-365-encryption-in-the-microsoft-cloud-overview.md).

Insieme, le protezioni sopra elencate forniscono controlli di isolamento logico affidabili che forniscono la protezione dalle minacce e la mitigazione equivalenti a quella fornita solo dall'isolamento fisico.

## <a name="related-links"></a>Collegamenti correlati

- [Isolamento e controllo di accesso in Azure Active Directory](microsoft-365-isolation-in-azure-active-directory.md)
- [Isolamento del tenant in Office Graph e Delve](microsoft-365-isolation-in-graph-and-delve.md)
- [Isolamento del tenant per la funzionalità di ricerca di Microsoft 365](microsoft-365-isolation-in-microsoft-365-search.md)
- [Isolamento del tenant in Office 365 Video](microsoft-365-isolation-in-microsoft-365-video.md)
- [Limiti della risorsa](/compliance/assurance/assurance-resource-limits)
- [Monitoraggio e verifica dei limiti del tenant](/compliance/assurance/assurance-monitoring-and-testing)
- [Isolamento e controllo di accesso in Microsoft 365](microsoft-365-isolation-in-microsoft-365.md)