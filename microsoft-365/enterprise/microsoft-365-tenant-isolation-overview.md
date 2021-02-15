---
title: Isolamento del tenant in Microsoft 365
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
description: Questo articolo contiene un riepilogo di come Microsoft applica l'isolamento del tenant in servizi cloud come Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c9af522c71f3b089c8f2f198f861bcac8a0011a2
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384933"
---
# <a name="tenant-isolation-in-microsoft-365"></a>Isolamento del tenant in Microsoft 365

Uno dei principali vantaggi del cloud computing è il concetto di un'infrastruttura comune condivisa tra numerosi clienti contemporaneamente, che porta a un'ampia scalabilità. Questo concetto è *denominato multi-tenancy.* Microsoft lavora costantemente per garantire che le architetture multi-tenant dei servizi cloud supportino gli standard di sicurezza, riservatezza, privacy, integrità e disponibilità a livello aziendale.

In base agli investimenti e all'esperienza significativi raccolti da [Trustworthy Computing](https://www.microsoft.com/trust-center) e dal ciclo di vita dello sviluppo della [sicurezza,](https://www.microsoft.com/securityengineering/sdl/)i servizi cloud Microsoft sono stati progettati presupponendo che tutti i tenant siano potenzialmente ostile a tutti gli altri tenant e abbiamo implementato misure di sicurezza per impedire che le azioni di un tenant influiscano sulla sicurezza o sul servizio di un altro tenant o per accedere al contenuto di un altro tenant.

I due obiettivi principali della gestione dell'isolamento del tenant in un ambiente multi-tenant sono:

1.    Impedire la perdita di contenuti dei clienti o l'accesso non autorizzato ai contenuti dei clienti nei tenant; e
2.    Impedire che le azioni di un tenant influiscano negativamente sul servizio per un altro tenant

In Microsoft 365 sono state implementate più forme di protezione per impedire ai clienti di compromettere i servizi o le applicazioni di Microsoft 365 o di ottenere l'accesso non autorizzato alle informazioni di altri tenant o del sistema Microsoft 365 stesso, tra cui:

- L'isolamento logico dei contenuti dei clienti all'interno di ogni tenant per i servizi di Microsoft 365 viene ottenuto tramite l'autorizzazione di Azure Active Directory e il controllo dell'accesso basato sui ruoli.
- SharePoint Online fornisce meccanismi di isolamento dei dati a livello di archiviazione.
- Microsoft usa una rigorosa sicurezza fisica, screening in background e una strategia di crittografia a più livelli per proteggere la riservatezza e l'integrità dei contenuti dei clienti. Tutti i data center di Microsoft 365 dispongono di controlli di accesso biometrici, con la maggior parte delle stampe palmo necessarie per ottenere l'accesso fisico. Inoltre, tutti i dipendenti Microsoft con sede negli Stati Uniti devono completare correttamente un controllo del background standard come parte del processo di assunzione. Per ulteriori informazioni sui controlli utilizzati per l'accesso amministrativo in Microsoft 365, vedere Controlli di accesso amministrativo di [Microsoft 365.](microsoft-365-administrative-access-controls-overview.md)
- Microsoft 365 usa tecnologie lato servizio che crittografano i contenuti dei clienti in transito e in transito, tra cui BitLocker, crittografia per file, TLS (Transport Layer Security) e IPsec (Internet Protocol Security). Per informazioni dettagliate sulla crittografia in Microsoft 365, vedere Tecnologie di crittografia dei dati [in Microsoft 365.](../compliance/office-365-encryption-in-the-microsoft-cloud-overview.md)

Insieme, le protezioni sopra elencate forniscono affidabili controlli di isolamento logico che forniscono la protezione dalle minacce e la mitigazione equivalenti a quella fornita solo dall'isolamento fisico.

## <a name="related-links"></a>Collegamenti correlati

- [Isolamento e controllo di accesso in Azure Active Directory](microsoft-365-isolation-in-azure-active-directory.md)
- [Isolamento del tenant in Office Graph e Delve](microsoft-365-isolation-in-graph-and-delve.md)
- [Isolamento del tenant per la funzionalità di ricerca di Microsoft 365](microsoft-365-isolation-in-microsoft-365-search.md)
- [Isolamento del tenant in Office 365 Video](microsoft-365-isolation-in-microsoft-365-video.md)
- [Limiti della risorsa](microsoft-365-resource-limits.md)
- [Monitoraggio e verifica dei limiti del tenant](microsoft-365-monitoring-and-testing.md)
- [Isolamento e controllo di accesso in Microsoft 365](microsoft-365-isolation-in-microsoft-365.md)
