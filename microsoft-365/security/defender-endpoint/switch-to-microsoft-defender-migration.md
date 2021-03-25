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
ms.date: 02/11/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.technology: mde
ms.openlocfilehash: 6e5b79e447579631e4aa2eaf02352dc3fa6a8daa
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51066090"
---
# <a name="make-the-switch-from-a-non-microsoft-endpoint-solution-to-microsoft-defender-for-endpoint"></a>Passare da una soluzione endpoint non Microsoft a Microsoft Defender for Endpoint

Se si prevede di passare da una soluzione di protezione degli endpoint non Microsoft a [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) (Defender for Endpoint), si è nel posto giusto. Usa questo articolo come guida.

:::image type="content" source="images/nonms-mde-migration.png" alt-text="Panoramica della migrazione a Defender for Endpoint":::

Quando si passa a Defender per Endpoint, si inizia con la soluzione non Microsoft in modalità attiva, si configura Defender per Endpoint in modalità passiva, si esegue l'onboard su Defender per Endpoint e quindi si imposta Defender per Endpoint sulla modalità attiva e si rimuove la soluzione non Microsoft.

> [!TIP]
> - Se attualmente si usa McAfee Endpoint Security (McAfee), vedere [Migrate from McAfee to Microsoft Defender for Endpoint](mcafee-to-microsoft-defender-migration.md).
> - Se attualmente si usa Symantec Endpoint Protection (Symantec), vedere [Migrate from Symantec to Microsoft Defender for Endpoint](symantec-to-microsoft-defender-atp-migration.md).

## <a name="the-migration-process"></a>Processo di migrazione

Quando si passa a Microsoft Defender for Endpoint, si segue un processo che può essere suddiviso in tre fasi, come descritto nella tabella seguente:

![Fasi di migrazione : preparazione, installazione, onboard](images/phase-diagrams/migration-phases.png)

|Fase |Descrizione |
|--|--|
|[Preparare la migrazione](switch-to-microsoft-defender-prepare.md) |Durante [la fase **di** preparazione,](switch-to-microsoft-defender-prepare.md)aggiornerà i dispositivi dell'organizzazione, si ottiene Microsoft Defender for Endpoint, si pianificano ruoli e autorizzazioni e si concede l'accesso a Microsoft Defender Security Center. Puoi anche configurare il proxy del dispositivo e le impostazioni Internet per abilitare la comunicazione tra i dispositivi dell'organizzazione e Microsoft Defender for Endpoint. |
|[Configurare Microsoft Defender per Endpoint](switch-to-microsoft-defender-setup.md) |Durante la fase di [installazione,  ](switch-to-microsoft-defender-setup.md)abiliti Microsoft Defender Antivirus e assicurati che sia in modalità passiva e configura le impostazioni & esclusioni per Microsoft Defender Antivirus, Microsoft Defender for Endpoint e la soluzione di protezione degli endpoint esistente. Puoi anche creare gruppi di dispositivi, raccolte e unità organizzative. Infine, è possibile configurare i criteri antimalware e le impostazioni di protezione in tempo reale.|
|[Onboard to Microsoft Defender for Endpoint](switch-to-microsoft-defender-onboard.md) |Durante [la fase di **onboarding,**](switch-to-microsoft-defender-onboard.md)puoi eseguire l'onboarding dei dispositivi a Microsoft Defender for Endpoint e verificare che tali dispositivi comunichino con Microsoft Defender for Endpoint. Infine, disinstalla la soluzione di endpoint protection esistente e assicurati che la protezione tramite Microsoft Defender Antivirus & Microsoft Defender for Endpoint sia in modalità attiva. |

## <a name="whats-included-in-microsoft-defender-for-endpoint"></a>Cosa è incluso in Microsoft Defender for Endpoint?

In questa guida alla [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) migrazione ci concentriamo sulla protezione di nuova generazione e sulle funzionalità di rilevamento e risposta degli [endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) come punto di partenza per il passaggio a Microsoft Defender for Endpoint. Tuttavia, Microsoft Defender per Endpoint include molto di più di protezione antivirus ed endpoint. Microsoft Defender per endpoint è una piattaforma unificata per la protezione preventiva, il rilevamento post-violazione, l'indagine automatizzata e la risposta. Nella tabella seguente sono riepilogate le funzionalità e le funzionalità di Microsoft Defender per Endpoint. 

| Funzionalità/funzionalità | Descrizione |
|---|---|
| [Gestione delle & delle minacce](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) | Le & di gestione delle vulnerabilità consentono di identificare, valutare e correggere i punti deboli degli endpoint (ad esempio i dispositivi). |
| [Riduzione della superficie d'attacco](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-attack-surface-reduction) | Le regole di riduzione della superficie di attacco consentono di proteggere i dispositivi e le applicazioni dell'organizzazione da attacchi e minacce informatiche. |
| [Protezione di nuova generazione](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10) | La protezione di nuova generazione include Microsoft Defender Antivirus per bloccare minacce e malware. |
| [Rilevamento endpoint e risposta](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) | Le funzionalità di rilevamento e risposta degli endpoint rilevano, analizzano e rispondono ai tentativi di intrusione e alle violazioni attive.  |
| [Ricerca avanzata](advanced-hunting-overview.md) | Le funzionalità di ricerca avanzate consentono al team delle operazioni di sicurezza di individuare indicatori ed entità di minacce note o potenziali. |
| [Blocco comportamentale e contenimento](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) | Le funzionalità di blocco e contenimento comportamentali consentono di identificare e arrestare le minacce, in base ai comportamenti e agli alberi di processo, anche quando la minaccia ha iniziato l'esecuzione. |
| [Indagine e correzione automatizzate](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/automated-investigations) | Le funzionalità di analisi e risposta automatizzate esaminano gli avvisi e esere azioni di correzione immediate per risolvere le violazioni. |
| [Servizio di ricerca delle minacce](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-threat-experts) (Microsoft Threat Experts) | I servizi di ricerca delle minacce offrono ai team delle operazioni di sicurezza il monitoraggio e l'analisi a livello di esperti e assicurano che le minacce critiche non siano perse. |

**Vuoi saperne di più? Vedi [Microsoft Defender per Endpoint.](https://docs.microsoft.com/windows/security/threat-protection)**

## <a name="next-step"></a>Passaggio successivo

- Passare a [Prepararsi per la migrazione](switch-to-microsoft-defender-prepare.md).
