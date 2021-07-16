---
title: Passare da Protezione endpoint non Microsoft a Microsoft Defender for Endpoint
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
- m365solution-mcafeemigrate
- m365solution-symantecmigrate
ms.topic: conceptual
ms.custom: migrationguides
ms.date: 06/14/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.technology: mde
ms.openlocfilehash: cff0810a4469d3c2d9ff2fe0fe5100b7a37408ae
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454746"
---
# <a name="make-the-switch-from-non-microsoft-endpoint-protection-to-microsoft-defender-for-endpoint"></a>Passare da Protezione endpoint non Microsoft a Microsoft Defender for Endpoint

Se stai pensando di passare da una soluzione di protezione degli endpoint non Microsoft a [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) (Defender for Endpoint), sei nel posto giusto. Usa questo articolo come guida.

:::image type="content" source="images/nonms-mde-migration.png" alt-text="Panoramica della migrazione a Defender for Endpoint":::

Quando si passa a Defender for Endpoint, si inizia con la soluzione non Microsoft che opera in modalità attiva. Quindi, configura Defender per Endpoint in modalità passiva e onboard i dispositivi a Defender per Endpoint. Successivamente, imposta Defender per Endpoint sulla modalità attiva. Infine, rimuovere la soluzione non Microsoft.

## <a name="the-migration-process"></a>Processo di migrazione

Il processo di migrazione a Defender for Endpoint può essere suddiviso in tre fasi, come descritto nella tabella seguente:

![Fasi di migrazione : preparazione, installazione, onboard](images/phase-diagrams/migration-phases.png)

|Fase |Descrizione |
|--|--|
|[Preparare la migrazione](switch-to-microsoft-defender-prepare.md) |Durante [la fase **di** preparazione](switch-to-microsoft-defender-prepare.md): <p>1. Aggiornare i dispositivi dell'organizzazione. <p>2. Ottenere Defender per Endpoint. <p>3. Pianificare i ruoli e le autorizzazioni e concedere l'accesso al Microsoft 365 Defender portale. <p>4. Configurare il proxy del dispositivo e le impostazioni Internet per abilitare la comunicazione tra i dispositivi dell'organizzazione e Defender for Endpoint. |
|[Configurare Defender per Endpoint](switch-to-microsoft-defender-setup.md) |Durante [la fase **di** installazione](switch-to-microsoft-defender-setup.md): <p>1. Abilitare/reinstallare Antivirus Microsoft Defender. <p>2. Configurare Defender per Endpoint. <p>3. Aggiungere Defender for Endpoint all'elenco di esclusione per la soluzione esistente. <p>4. Aggiungere la soluzione esistente all'elenco di esclusione per Antivirus Microsoft Defender. <p>5. Configurare i gruppi di dispositivi, le raccolte e le unità organizzative. <p>6. Configurare i criteri antimalware e le impostazioni di protezione in tempo reale.|
|[Onboard to Defender for Endpoint](switch-to-microsoft-defender-onboard.md) |Durante [la fase di **onboard:**](switch-to-microsoft-defender-onboard.md) <p>1. Onboard dei dispositivi a Defender for Endpoint. <p>2. Eseguire un test di rilevamento. <p>3. Verificare che Antivirus Microsoft Defender in esecuzione in modalità passiva. <p>4. Ottenere gli aggiornamenti per Antivirus Microsoft Defender. <p>5. Disinstallare la soluzione di endpoint protection esistente. <p>6. Verificare che Defender for Endpoint funzioni correttamente. |

## <a name="whats-included-in-microsoft-defender-for-endpoint"></a>Cosa è incluso in Microsoft Defender for Endpoint?

In questa guida alla migrazione ci concentriamo [sulle](microsoft-defender-antivirus-in-windows-10.md) funzionalità di protezione e rilevamento degli [endpoint](overview-endpoint-detection-response.md) e di risposta di nuova generazione come punto di partenza per il passaggio a Defender for Endpoint. Tuttavia, Defender for Endpoint include molto più di protezione antivirus ed endpoint. Defender for Endpoint è una piattaforma unificata per la protezione preventiva, il rilevamento post-violazione, l'indagine automatizzata e la risposta. La tabella seguente riepiloga le funzionalità e le funzionalità in Defender for Endpoint. 

| Funzionalità/funzionalità | Descrizione |
|---|---|
| [Gestione di minacce e vulnerabilità](next-gen-threat-and-vuln-mgt.md) | Le & gestione delle vulnerabilità consentono di identificare, valutare e correggere i punti deboli degli endpoint (ad esempio i dispositivi). |
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
