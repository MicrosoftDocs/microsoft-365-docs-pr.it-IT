---
title: Esaminare i requisiti di architettura e il framework tecnico per Microsoft Defender for Identity, diagramma dell'architettura, MDI
description: Il diagramma tecnico per Microsoft Defender for Identity in Microsoft 365 Defender ti aiuterà a comprendere l'identità in Microsoft 365 prima di creare il laboratorio di valutazione o l'ambiente pilota.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
ms.date: 07/09/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 8f0c736d07a2a66420416d30ae2dc45ae5fee37a
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458303"
---
# <a name="review-architecture-requirements-and-key-concepts-for-microsoft-defender-for-identity"></a>Esaminare i requisiti di architettura e i concetti chiave per Microsoft Defender for Identity


**Si applica a:**
- Microsoft 365 Defender

Questo articolo è [il passaggio 1 di 3 nel](eval-defender-identity-overview.md) processo di configurazione dell'ambiente di valutazione per Microsoft Defender for Identity. Per ulteriori informazioni su questo processo, vedere [l'articolo di panoramica](eval-defender-identity-overview.md).

Prima di abilitare Microsoft Defender per l'identità, assicurati di aver compreso l'architettura e di poter soddisfare i requisiti.

Microsoft Defender for Identity usa l'apprendimento automatico e l'analisi comportamentale per identificare gli attacchi nella rete locale insieme al rilevamento e alla prevenzione proattiva dei rischi di accesso degli utenti associati alle identità cloud. Per altre informazioni, vedi [Che cos'è Microsoft Defender per l'identità?](/defender-for-identity/what-is)

Defender for Identity protegge gli utenti di Active Directory locali e/o gli utenti sincronizzati con il Azure Active Directory (Azure AD). Per proteggere un ambiente costituito solo da utenti di Azure AD, vedere [Azure AD Identity Protection.](/azure/active-directory/identity-protection/overview-identity-protection)

## <a name="understand-the-architecture"></a>Informazioni sull'architettura

Il diagramma seguente illustra l'architettura di base per Defender for Identity. 

![Architettura per Microsoft Defender for Identity](../../media/defender/m365-defender-identity-architecture.png)

In questa illustrazione:
- I sensori installati nei controller di dominio ACTIVE analizzano i registri e il traffico di rete e li inviano a Microsoft Defender per l'identità per l'analisi e la creazione di report.
-  I sensori possono anche analizzare Active Directory Federation Services (AD FS) quando Azure AD è configurato per l'utilizzo dell'autenticazione federata (linea tratteggiata nella figura). 
- Microsoft Defender for Identity condivide i segnali Microsoft 365 Defender per il rilevamento esteso e la risposta (XDR).


I sensori Defender for Identity possono essere installati direttamente nei server seguenti:

- Controller di dominio: il sensore monitora direttamente il traffico dei controller di dominio, senza la necessità di un server dedicato o la configurazione del mirroring delle porte.
- ADFS: il sensore monitora direttamente il traffico di rete e gli eventi di autenticazione.

Per un'analisi più approfondita dell'architettura di Defender for Identity, inclusa l'integrazione con Cloud App Security, vedi [Architettura di Microsoft Defender per l'identità.](/defender-for-identity/architecture)


## <a name="understand-key-concepts"></a>Comprendere i concetti chiave

Nella tabella seguente sono stati identificati i concetti chiave importanti da comprendere durante la valutazione, la configurazione e la distribuzione di Microsoft Defender for Identity.


|Concetti  |Descrizione |Ulteriori informazioni  |
|---------|---------|---------|
| Attività monitorate | Defender for Identity monitora i segnali generati dall'interno dell'organizzazione per rilevare attività sospette o dannose e consente di determinare la validità di ogni potenziale minaccia in modo che sia possibile eseguire la triage e rispondere in modo efficace.  |  [Attività monitorate di Microsoft Defender for Identity](/defender-for-identity/monitored-activities)       |
| Avvisi di sicurezza    | Gli avvisi di sicurezza di Defender for Identity spiegano le attività sospette rilevate dai sensori nella rete insieme agli attori e ai computer coinvolti in ogni minaccia.   | [Avvisi di sicurezza per Microsoft Defender for Identity](/defender-for-identity/suspicious-activity-guide?tabs=external)    |
| Profili entità    | I profili entità offrono un'analisi approfondita completa di utenti, computer, dispositivi e risorse insieme alla cronologia di accesso.   | [Informazioni sui profili entità](/defender-for-identity/entity-profiles)  |
| Percorsi di movimento laterali    | Un componente chiave delle informazioni dettagliate sulla sicurezza MDI è l'identificazione dei percorsi di movimento laterali in cui un utente malintenzionato utilizza account non sensibili per accedere ad account sensibili o computer in tutta la rete.  | [Microsoft Defender for Identity Lateral Movement Paths (LPP)](/defender-for-identity/use-case-lateral-movement-path)  |
| Risoluzione dei nomi di rete    |  Network Name Resolution (NNR) è un componente della funzionalità MDI che acquisisce le attività in base al traffico di rete, agli eventi Windows, a ETW e così via e correla questi dati non elaborati ai computer rilevanti coinvolti in ogni attività.       | [Che cos'è La risoluzione dei nomi di rete?](/defender-for-identity/nnr-policy)      |
| Report    | I report di Defender for Identity consentono di pianificare o generare e scaricare immediatamente report che forniscono informazioni sullo stato di sistema ed entità.  È possibile creare report sull'integrità del sistema, gli avvisi di sicurezza e i potenziali percorsi di movimento laterali rilevati nell'ambiente.   | [Microsoft Defender for Identity Reports ](/defender-for-identity/reports)       |
| Gruppi di ruoli    | Defender for Identity offre gruppi basati sui ruoli e accesso delegato per proteggere i dati in base alle specifiche esigenze di sicurezza e conformità dell'organizzazione, tra cui Amministratori, Utenti e Visualizzatori.        |  [Ruoli dei gruppi Microsoft Defender per identità](/defender-for-identity/role-groups)       |
| Portale amministrativo    |  Oltre al Centro sicurezza Microsoft 365, il cab del portale defender per l'identità viene usato per monitorare e rispondere a attività sospette.      | [Utilizzo del portale di Microsoft Defender per l'identità](/defender-for-identity/workspace-portal)        |
| Microsoft Cloud App Security integrazione   | Microsoft Cloud App Security si integra con Microsoft Defender for Identity per fornire l'analisi comportamentale (UEBA) dell'entità utente in un ambiente ibrido, sia nell'app cloud che in locale   | Integrazione di Microsoft Defender for Identity  |
| | | |


## <a name="review-prerequisites"></a>Esaminare i prerequisiti

Defender for Identity richiede alcune operazioni preliminari per garantire che l'identità locale e i componenti di rete soddisfino i requisiti minimi. Usa questo articolo come elenco di controllo per assicurarti che l'ambiente sia pronto: [Microsoft Defender for Identity prerequisites](/defender-for-identity/prerequisites).


## <a name="next-steps"></a>Passaggi successivi

Passaggio 2 di 3: Abilitare [l'ambiente di valutazione Defender for Identity](eval-defender-identity-enable-eval.md)

Tornare alla panoramica per [valutare Microsoft Defender for Identity](eval-defender-identity-overview.md)

Tornare alla panoramica per [valutare e valutare Microsoft 365 Defender](eval-overview.md) 