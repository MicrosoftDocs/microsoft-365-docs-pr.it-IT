---
title: Pilotare Microsoft Defender for Identity, configurare benchmark di configurazione, standard, linee guida ed eseguire esercitazioni sul rilevamento e la correzione di varie minacce di identità come ricognizione, credenziali compromesse, movimento laterale, dominio dominante e avvisi di esfiltrazione, condurre indagini su utenti, computer, entità e percorsi di movimento laterale.
description: Pilota Microsoft Defender for Identity, imposta benchmark, esercitazioni sulla ricognizione, credenziali compromesse, movimento laterale, dominio dominante e avvisi di exfiltration, tra gli altri.
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
ms.openlocfilehash: 14c5b9252e980d1f693139393d26b9405cb1b812
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458055"
---
# <a name="pilot-microsoft-defender-for-identity"></a>Pilota di Microsoft Defender per l'identità


**Si applica a:**
- Microsoft 365 Defender

Questo articolo è [il passaggio 3 di 3 del](eval-defender-identity-overview.md) processo di configurazione dell'ambiente di valutazione per Microsoft Defender for Identity. Per ulteriori informazioni su questo processo, vedere [l'articolo di panoramica](eval-defender-identity-overview.md).

Usa la procedura seguente per configurare il progetto pilota per Microsoft Defender per l'identità. Si noti che i suggerimenti non includono la configurazione di un gruppo pilota. La procedura consigliata consiste nell'installare il sensore in tutti i server che eseguono Servizi di dominio Active Directory e Active Directory Federated Services (AD FS).

![Passaggi per l'aggiunta di Microsoft Defender per l'identità all'ambiente di valutazione di Defender](../../media/defender/m365-defender-identity-pilot-steps.png)

Nella tabella seguente vengono descritti i passaggi illustrati nell'illustrazione.

- [Passaggio 1: Configurare i suggerimenti di benchmark per l'ambiente di identità](#step-1-configure-benchmark-recommendations-for-your-identity-environment)
- [Passaggio 2: provare le funzionalità - Esercitazioni dettagliate per identificare e correggere diversi tipi di attacco ](#step-2-try-out-capabilities--walk-through-tutorials-for-identifying-and-remediating-different-attack-types)

## <a name="step-1-configure-benchmark-recommendations-for-your-identity-environment"></a>Passaggio 1. Configurare i suggerimenti di benchmark per l'ambiente di identità

Microsoft fornisce consigli di benchmark di sicurezza per i clienti che usano i servizi Cloud Microsoft. [Azure Security Benchmark](/security/benchmark/azure/overview) (ASB) fornisce procedure consigliate e suggerimenti prescrittivi per migliorare la sicurezza di carichi di lavoro, dati e servizi in Azure.

Questi consigli di benchmark includono [la linea di base della sicurezza di Azure per Microsoft Defender per l'identità.](/security/benchmark/azure/baselines/defender-for-identity-security-baseline) L'implementazione di questi suggerimenti può richiedere del tempo per la pianificazione e l'implementazione. Anche se questi incrementeranno notevolmente la sicurezza dell'ambiente di identità, non dovrebbero impedirti di continuare a valutare e implementare Microsoft Defender for Identity. Questi sono disponibili qui per la tua consapevolezza.

## <a name="step-2-try-out-capabilities--walk-through-tutorials-for-identifying-and-remediating-different-attack-types"></a>Passaggio 2. Funzionalità di prova: esercitazioni per identificare e correggere diversi tipi di attacco

La documentazione di Microsoft Defender for Identity include una serie di esercitazioni che illustrano il processo di identificazione e correzione di vari tipi di attacco.

Prova le esercitazioni su Defender per l'identità:
- [Avvisi di ricognizione](/defender-for-identity/reconnaissance-alerts)
- [Avvisi credenziali compromesse](/defender-for-identity/compromised-credentials-alerts)
- [Avvisi di movimento laterale](/defender-for-identity/lateral-movement-alerts)
- [Avvisi di dominio dominante](/defender-for-identity/domain-dominance-alerts)
- [Avvisi di esfiltrazione](/defender-for-identity/exfiltration-alerts)
- [Analizzare un utente](/defender-for-identity/investigate-a-user)
- [Analizzare un computer](/defender-for-identity/investigate-a-computer)
- [Analizzare i percorsi di movimento laterale](/defender-for-identity/investigate-lateral-movement-path)
- [Analizzare le entità](/defender-for-identity/investigate-entity)

## <a name="next-steps"></a>Passaggi successivi

[Valutare Microsoft Defender per Office 365](eval-defender-office-365-overview.md)

Torna alla panoramica di [Evaluate Microsoft Defender for Office 365](eval-defender-office-365-overview.md)

Tornare alla panoramica per [valutare e valutare Microsoft 365 Defender](eval-overview.md)