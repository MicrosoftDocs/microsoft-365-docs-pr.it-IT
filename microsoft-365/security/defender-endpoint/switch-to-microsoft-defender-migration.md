---
title: Passare da una soluzione endpoint non Microsoft a Microsoft Defender for Endpoint
description: Passare a Microsoft Defender for Endpoint. Leggere questo articolo per una panoramica.
keywords: migrazione, windows defender advanced endpoint protection, per Endpoint, edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-migratetomdatp
- m365solution-overview
ms.topic: conceptual
ms.custom: migrationguides
ms.date: 05/14/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.technology: mde
ms.openlocfilehash: 013205a1b5b9db204f626a6fe6ab76ad07378558
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538004"
---
# <a name="make-the-switch-from-a-non-microsoft-endpoint-solution-to-microsoft-defender-for-endpoint"></a>Passare da una soluzione endpoint non Microsoft a Microsoft Defender for Endpoint

Se si prevede di passare da una soluzione di protezione degli endpoint non Microsoft a [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) (Defender for Endpoint), si è nel posto giusto. Usa questo articolo come guida.

:::image type="content" source="images/nonms-mde-migration.png" alt-text="Panoramica della migrazione a Defender for Endpoint":::

Quando si passa a Defender per Endpoint, si inizia con la soluzione non Microsoft in modalità attiva, si configura Defender per Endpoint in modalità passiva, si esegue l'onboard su Defender per Endpoint e quindi si imposta Defender per Endpoint sulla modalità attiva e si rimuove la soluzione non Microsoft.

> [!TIP]
> - Se attualmente si usa McAfee Endpoint Security (McAfee), vedere [Migrate from McAfee to Defender for Endpoint.](mcafee-to-microsoft-defender-migration.md)
> - Se attualmente stai usando Symantec Endpoint Protection (Symantec), vedi Eseguire la migrazione da [Symantec](symantec-to-microsoft-defender-endpoint-migration.md)a Defender per Endpoint.

## <a name="the-migration-process"></a>Processo di migrazione

Quando si passa a Defender per Endpoint, si segue un processo che può essere suddiviso in tre fasi, come descritto nella tabella seguente:

![Fasi di migrazione : preparazione, installazione, onboard](images/phase-diagrams/migration-phases.png)

|Fase |Descrizione |
|--|--|
|[Preparare la migrazione](switch-to-microsoft-defender-prepare.md) |Durante [la fase **di** preparazione,](switch-to-microsoft-defender-prepare.md)aggiorneremo i dispositivi dell'organizzazione, ottieni Defender per Endpoint, pianichei i ruoli e le autorizzazioni e concedi l'accesso al Microsoft Defender Security Center. Puoi anche configurare il proxy del dispositivo e le impostazioni Internet per abilitare la comunicazione tra i dispositivi dell'organizzazione e Defender for Endpoint. |
|[Configurare Defender per Endpoint](switch-to-microsoft-defender-setup.md) |Durante [la fase **di** installazione,](switch-to-microsoft-defender-setup.md)abiliti Antivirus Microsoft Defender e lo imposta in modalità passiva. Puoi anche configurare le impostazioni & esclusioni per Antivirus Microsoft Defender e la soluzione di endpoint protection esistente. Quindi, crei i gruppi di dispositivi, le raccolte e le unità organizzative. Infine, è possibile configurare i criteri antimalware e le impostazioni di protezione in tempo reale.|
|[Onboard to Defender for Endpoint](switch-to-microsoft-defender-onboard.md) |Durante [la fase di **onboarding,**](switch-to-microsoft-defender-onboard.md)puoi eseguire l'onboarding dei dispositivi a Defender for Endpoint, verificare che Antivirus Microsoft Defender sia in esecuzione in modalità passiva e verificare che gli endpoint comunichino con Defender per Endpoint. Quindi, disinstalla la soluzione di endpoint protection esistente e assicurati che Defender for Endpoint funzioni correttamente. |

## <a name="whats-included-in-microsoft-defender-for-endpoint"></a>Cosa è incluso in Microsoft Defender for Endpoint?

In questa guida alla migrazione ci concentriamo [sulle](microsoft-defender-antivirus-in-windows-10.md) funzionalità di protezione e rilevamento degli [endpoint](overview-endpoint-detection-response.md) e di risposta di nuova generazione come punto di partenza per il passaggio a Defender for Endpoint. Tuttavia, Defender for Endpoint include molto più di protezione antivirus ed endpoint. Defender for Endpoint è una piattaforma unificata per la protezione preventiva, il rilevamento post-violazione, l'indagine automatizzata e la risposta. La tabella seguente riepiloga le funzionalità e le funzionalità in Defender for Endpoint. 

| Funzionalità/funzionalità | Descrizione |
|---|---|
| [Gestione di minacce e vulnerabilità.](next-gen-threat-and-vuln-mgt.md) | Le & gestione delle vulnerabilità consentono di identificare, valutare e correggere i punti deboli degli endpoint (ad esempio i dispositivi). |
| [Riduzione della superficie di attacco](overview-attack-surface-reduction.md) | Le regole di riduzione della superficie di attacco consentono di proteggere i dispositivi e le applicazioni dell'organizzazione da attacchi e minacce informatiche. |
| [Protezione di nuova generazione](microsoft-defender-antivirus-in-windows-10.md) | La protezione di nuova generazione include Antivirus Microsoft Defender per bloccare minacce e malware. |
| [Rilevamento e risposta di endpoint](overview-endpoint-detection-response.md) | Le funzionalità di rilevamento e risposta degli endpoint rilevano, analizzano e rispondono ai tentativi di intrusione e alle violazioni attive.  |
| [Rilevazione avanzata](advanced-hunting-overview.md) | Le funzionalità di ricerca avanzate consentono al team delle operazioni di sicurezza di individuare indicatori ed entità di minacce note o potenziali. |
| [Blocco e contenimento comportamentale](behavioral-blocking-containment.md) | Le funzionalità di blocco e contenimento comportamentali consentono di identificare e arrestare le minacce, in base ai comportamenti e agli alberi di processo, anche quando la minaccia ha iniziato l'esecuzione. |
| [Analisi e correzione automatizzate](automated-investigations.md) | Le funzionalità di analisi e risposta automatizzate esaminano gli avvisi e esere azioni di correzione immediate per risolvere le violazioni. |
| [Servizio di ricerca delle minacce](microsoft-threat-experts.md) (Microsoft Threat Experts) | I servizi di ricerca delle minacce offrono ai team delle operazioni di sicurezza il monitoraggio e l'analisi a livello di esperti e assicurano che le minacce critiche non siano perse. |

**Vuoi saperne di più? Vedi [Defender per Endpoint.](microsoft-defender-endpoint.md)**

## <a name="next-step"></a>Passaggio successivo

- Passare a [Prepararsi per la migrazione](switch-to-microsoft-defender-prepare.md).
