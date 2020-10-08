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
description: Questo articolo contiene un riepilogo del modo in cui Microsoft impone l'isolamento dei tenant nei servizi cloud come Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c9af522c71f3b089c8f2f198f861bcac8a0011a2
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384933"
---
# <a name="tenant-isolation-in-microsoft-365"></a>Isolamento tenant in Microsoft 365

Uno dei vantaggi principali del cloud computing è il concetto di un'infrastruttura comune condivisa tra i numerosi clienti contemporaneamente, che porta a economie di scala. Questo concetto è denominato *multi-tenant*. Microsoft funziona continuamente per garantire che le architetture multi-tenant dei servizi cloud supportino la sicurezza a livello aziendale, la riservatezza, la privacy, l'integrità e gli standard di disponibilità.

In base ai significativi investimenti e all'esperienza ottenuti dall' [elaborazione affidabile](https://www.microsoft.com/trust-center) e dal ciclo di vita [dello sviluppo della sicurezza](https://www.microsoft.com/securityengineering/sdl/), i servizi cloud Microsoft sono stati concepiti con l'ipotesi che tutti i tenant siano potenzialmente ostili a tutti gli altri tenant e che siano state implementate misure di sicurezza per impedire che le azioni di un tenant influiscano sulla sicurezza o sul servizio di un altro tenant o sull'accesso al

I due obiettivi principali per mantenere l'isolamento del tenant in un ambiente multi-tenant sono:

1.    Impedire la fuoriuscita o l'accesso non autorizzato al contenuto dei clienti tra i tenant; e
2.    Impedire alle azioni di un tenant di influenzare negativamente il servizio per un altro tenant

Sono state implementate più forme di protezione in Microsoft 365 per impedire ai clienti di compromettere i servizi o le applicazioni di Microsoft 365 o di ottenere un accesso non autorizzato alle informazioni di altri tenant o del sistema Microsoft 365 stesso, tra cui:

- L'isolamento logico del contenuto dei clienti all'interno di ogni tenant per i servizi Microsoft 365 viene ottenuto tramite l'autorizzazione di Azure Active Directory e il controllo di accesso basato sui ruoli.
- SharePoint Online fornisce meccanismi di isolamento dei dati a livello di archiviazione.
- Microsoft utilizza la sicurezza fisica rigorosa, lo screening di sfondo e una strategia di crittografia a più livelli per proteggere la riservatezza e l'integrità del contenuto dei clienti. Tutti i datacenter Microsoft 365 dispongono di controlli di accesso biometrici, con la maggior parte delle stampe Palm che richiedono l'accesso fisico. Inoltre, tutti i dipendenti Microsoft basati su Stati Uniti sono necessari per completare correttamente un controllo di sfondo standard come parte del processo di assunzione. Per ulteriori informazioni sui controlli utilizzati per l'accesso amministrativo in Microsoft 365, vedere [controlli di accesso amministrativo di microsoft 365](microsoft-365-administrative-access-controls-overview.md).
- Microsoft 365 utilizza tecnologie sul fianco del servizio che crittografano il contenuto dei clienti a riposo e in transito, tra cui BitLocker, crittografia per file, TLS (Transport Layer Security) e IPsec (Internet Protocol Security). Per informazioni specifiche sulla crittografia in Microsoft 365, vedere [Data Encryption Technologies in microsoft 365](../compliance/office-365-encryption-in-the-microsoft-cloud-overview.md).

Insieme, le protezioni elencate di seguito offrono robusti controlli di isolamento logico che forniscono protezione dalle minacce e una mitigazione equivalente a quella fornita solo dall'isolamento fisico.

## <a name="related-links"></a>Collegamenti correlati

- [Isolamento e controllo di accesso in Azure Active Directory](microsoft-365-isolation-in-azure-active-directory.md)
- [Isolamento del tenant in Office Graph e Delve](microsoft-365-isolation-in-graph-and-delve.md)
- [Isolamento del tenant per la funzionalità di ricerca di Microsoft 365](microsoft-365-isolation-in-microsoft-365-search.md)
- [Isolamento del tenant in Office 365 Video](microsoft-365-isolation-in-microsoft-365-video.md)
- [Limiti della risorsa](microsoft-365-resource-limits.md)
- [Monitoraggio e verifica dei limiti del tenant](microsoft-365-monitoring-and-testing.md)
- [Isolamento e controllo di accesso in Microsoft 365](microsoft-365-isolation-in-microsoft-365.md)
