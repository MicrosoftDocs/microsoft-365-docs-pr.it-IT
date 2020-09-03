---
title: Microsoft 365 monitoraggio e controllo dell'accesso ai controlli
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
description: 'Sintesi: un riepilogo dei diversi controlli di accesso al monitoraggio e di controllo disponibili in Microsoft 365.'
ms.openlocfilehash: ba79ba2263940e5677ada412f467a429e584b8ff
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332293"
---
# <a name="monitoring-and-auditing-access-controls-in-microsoft-365"></a>Monitoraggio e controllo dei controlli di accesso in Microsoft 365

Microsoft esegue il monitoraggio e il controllo estensivo di tutte le delega, i privilegi e le operazioni che si verificano in Microsoft 365. Microsoft 365 Access Control è un processo automatizzato basato sul principio del privilegio minimo e sull'integrazione dei controlli di accesso ai dati e degli audit:

- Tutti gli accessi consentiti possono essere rintracciati in un utente univoco. Gli amministratori sono responsabili della gestione del contenuto dei clienti.
- Le richieste di controllo di accesso, le approvazioni e i registri delle operazioni amministrative vengono acquisiti per l'analisi della sicurezza e degli eventi dannosi.
- I livelli di accesso vengono esaminati in tempo quasi reale in base all'appartenenza a un gruppo di sicurezza per garantire che solo gli utenti che dispongono di motivazioni aziendali autorizzate e soddisfino i requisiti di idoneità abbiano accesso ai sistemi.
- Microsoft 365, i suoi controlli di accesso e i servizi di supporto, tra cui Azure Active Directory e i datacenter fisici, vengono regolarmente controllati da terze parti indipendenti per la conformità con le norme [iso/iec 27001](https://www.microsoft.com/TrustCenter/Compliance/iso-iec-27001), [iso/IEC 27018](https://www.microsoft.com/TrustCenter/Compliance/iso-iec-27018), [SOC](https://www.microsoft.com/TrustCenter/Compliance/SOC), [FedRAMP](https://www.microsoft.com/TrustCenter/Compliance/FedRAMP)e altri [standard](https://www.microsoft.com/TrustCenter/Compliance?service=Office#Icons).
- Gli ingegneri di Microsoft 365 devono eseguire una formazione annuale sulla sicurezza, esaminare le procedure consigliate per l'accesso con privilegi elevati e riconoscere i criteri di sicurezza e privacy di Microsoft per mantenere i diritti per il servizio.

Gli avvisi automatici vengono attivati quando vengono rilevate attività sospette, ad esempio più account di accesso non riusciti entro un breve periodo. Il team di risposta alla sicurezza di Microsoft 365 utilizza l'apprendimento automatico e l'analisi dei dati di grandi dimensioni per esaminare e analizzare l'attività, cercare modelli di accesso irregolari e rispondere in modo proattivo a attività anomale e illecite. Microsoft impiega anche un team dedicato di tester di penetrazione e si impegna negli esercizi di team rosso e blu periodici per individuare i problemi di sicurezza e controllo di accesso nel servizio. I clienti possono verificare l'efficacia dei sistemi di controllo di accesso usando i rapporti di controllo e l'API di attività di gestione fornita da Microsoft 365.

Per ulteriori informazioni, vedere [Office 365 Management Activity API Reference](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference) and [Auditing and reporting in Microsoft 365](microsoft-365-auditing-and-reporting-overview.md).
