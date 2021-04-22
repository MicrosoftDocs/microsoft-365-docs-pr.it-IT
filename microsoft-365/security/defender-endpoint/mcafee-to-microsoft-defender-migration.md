---
title: Eseguire la migrazione da McAfee a Microsoft Defender for Endpoint
description: Passa da McAfee a Microsoft Defender for Endpoint. Leggere questo articolo per una panoramica.
keywords: migrazione, Microsoft Defender for Endpoint, edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
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
- m365solution-mcafeemigrate
- m365solution-overview
ms.topic: article
ms.custom: migrationguides
ms.date: 03/03/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 3d26e2c134f5f9794f7acd41e49c27bd9f331153
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932644"
---
# <a name="migrate-from-mcafee-to-microsoft-defender-for-endpoint"></a>Eseguire la migrazione da McAfee a Microsoft Defender for Endpoint

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Se si prevede di passare da McAfee Endpoint Security (McAfee) a [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) (Microsoft Defender for Endpoint), si è nel posto giusto. Usa questo articolo come guida.


:::image type="content" source="images/mcafee-mde-migration.png" alt-text="Panoramica della migrazione da McAfee a Defender for Endpoint":::

Quando fai il passaggio da McAfee a Defender for Endpoint, inizi con la soluzione McAfee in modalità attiva, configura Defender per Endpoint in modalità passiva, onboard su Defender per Endpoint e quindi imposta Defender per Endpoint sulla modalità attiva e rimuovi McAfee.

## <a name="the-migration-process"></a>Processo di migrazione

Quando si passa da McAfee a Microsoft Defender for Endpoint, si segue un processo che può essere suddiviso in tre fasi: Preparazione, installazione e onboard. 

![Fasi di migrazione - preparare l'onboard](images/phase-diagrams/migration-phases.png)

|Fase |Descrizione |
|--|--|
|[Preparare la migrazione](mcafee-to-microsoft-defender-prepare.md) |Durante la [**fase di**](mcafee-to-microsoft-defender-prepare.md) preparazione, aggiornerà i dispositivi dell'organizzazione, ottieni Microsoft Defender for Endpoint, pianicherà i ruoli e le autorizzazioni e concedi l'accesso a Microsoft Defender Security Center. Puoi anche configurare il proxy del dispositivo e le impostazioni Internet per abilitare la comunicazione tra i dispositivi dell'organizzazione e Microsoft Defender for Endpoint. |
|[Configurare Microsoft Defender per Endpoint](mcafee-to-microsoft-defender-setup.md) |Durante [](mcafee-to-microsoft-defender-setup.md) la fase di installazione, abiliti Microsoft Defender Antivirus e assicurati che sia in modalità passiva e configura le impostazioni & esclusioni per Microsoft Defender Antivirus, Microsoft Defender for Endpoint e McAfee. Puoi anche creare gruppi di dispositivi, raccolte e unità organizzative. Infine, è possibile configurare i criteri antimalware e le impostazioni di protezione in tempo reale.|
|[Onboard to Microsoft Defender for Endpoint](mcafee-to-microsoft-defender-onboard.md) |Durante la [**fase di onboarding,**](mcafee-to-microsoft-defender-onboard.md) puoi eseguire l'onboarding dei dispositivi a Microsoft Defender per Endpoint e verificare che tali dispositivi comunichino con Microsoft Defender for Endpoint. Infine, disinstalla McAfee e assicurati che la protezione tramite Microsoft Defender Antivirus & Microsoft Defender for Endpoint sia in modalità attiva. |

## <a name="whats-included-in-microsoft-defender-for-endpoint"></a>Cosa è incluso in Microsoft Defender for Endpoint?

In questa guida alla [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) migrazione ci concentriamo sulla protezione di nuova generazione e sulle funzionalità di rilevamento e risposta degli [endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) come punto di partenza per il passaggio a Microsoft Defender for Endpoint. Tuttavia, Microsoft Defender per Endpoint include molto di più di protezione antivirus ed endpoint. Microsoft Defender per endpoint è una piattaforma unificata per la protezione preventiva, il rilevamento post-violazione, l'indagine automatizzata e la risposta. Nella tabella seguente sono riepilogate le funzionalità e le funzionalità di Microsoft Defender per Endpoint. 

| Funzionalità/funzionalità | Descrizione |
|---|---|
| [Gestione di minacce e vulnerabilità.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) | Le & di gestione delle vulnerabilità consentono di identificare, valutare e correggere i punti deboli degli endpoint (ad esempio i dispositivi). |
| [Riduzione della superficie di attacco](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-attack-surface-reduction) | Le regole di riduzione della superficie di attacco consentono di proteggere i dispositivi e le applicazioni dell'organizzazione da attacchi e minacce informatiche. |
| [Protezione di nuova generazione](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10) | La protezione di nuova generazione include Microsoft Defender Antivirus per bloccare minacce e malware. |
| [Rilevamento e risposta di endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) | Le funzionalità di rilevamento e risposta degli endpoint rilevano, analizzano e rispondono ai tentativi di intrusione e alle violazioni attive.  |
| [Rilevazione avanzata](advanced-hunting-overview.md) | Le funzionalità di ricerca avanzate consentono al team delle operazioni di sicurezza di individuare indicatori ed entità di minacce note o potenziali. |
| [Blocco e contenimento comportamentale](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) | Le funzionalità di blocco e contenimento comportamentali consentono di identificare e arrestare le minacce, in base ai comportamenti e agli alberi di processo, anche quando la minaccia ha iniziato l'esecuzione. |
| [Indagine e correzione automatizzate](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/automated-investigations) | Le funzionalità di analisi e risposta automatizzate esaminano gli avvisi e esere azioni di correzione immediate per risolvere le violazioni. |
| [Servizio di ricerca delle minacce](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-threat-experts) (Microsoft Threat Experts) | I servizi di ricerca delle minacce offrono ai team delle operazioni di sicurezza il monitoraggio e l'analisi a livello di esperti e assicurano che le minacce critiche non siano perse. |

**Vuoi saperne di più? Vedi [Microsoft Defender per Endpoint.](https://docs.microsoft.com/windows/security/threat-protection)**

## <a name="next-step"></a>Passaggio successivo

- Passare a [Prepararsi per la migrazione](mcafee-to-microsoft-defender-prepare.md).
