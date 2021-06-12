---
title: Gestire Microsoft Defender per Endpoint con Configuration Manager
description: Informazioni su come gestire Microsoft Defender per Endpoint con Configuration Manager
keywords: post-migrazione, gestire, operazioni, manutenzione, utilizzo, Configuration Manager, Microsoft Defender for Endpoint, edr
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
- m365solution-scenario
ms.topic: article
ms.date: 06/11/2021
ms.reviewer: chventou
ms.openlocfilehash: 5fde3bfad69a5851dd94b76afb262f8be12d0360
ms.sourcegitcommit: 3e197d1ff7d8100faeaf1f5a33f1ad4ed2f72e99
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/11/2021
ms.locfileid: "52908258"
---
# <a name="manage-microsoft-defender-for-endpoint-with-configuration-manager"></a>Gestire Microsoft Defender per Endpoint con Configuration Manager

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


È consigliabile usare [Microsoft Endpoint Manager](/mem), che include [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) (Intune) e [Microsoft Endpoint Configuration Manager](/mem/configmgr/core/understand/introduction) (Configuration Manager) per gestire le funzionalità di protezione dalle minacce dell'organizzazione per i dispositivi (denominati anche endpoint). 
- [Ulteriori informazioni su Endpoint Manager](/mem/endpoint-manager-overview)
- [Co-gestire Microsoft Defender for Endpoint nei dispositivi Windows 10 con Configuration Manager e Intune](manage-atp-post-migration-intune.md)

## <a name="configure-microsoft-defender-for-endpoint-with-configuration-manager"></a>Configurare Microsoft Defender per Endpoint con Configuration Manager

|Attività  |Risorse per approfondire  |
|---------|---------|
|**Installare la console di Configuration Manager** se non è già presente<br/><br/>*Se non hai già la console Configuration Manger, usa queste risorse per ottenere i bit e installarla.* |[Ottenere il supporto di installazione](/mem/configmgr/core/servers/deploy/install/get-install-media)<br/><br/>[Installare la console di Configuration Manager](/mem/configmgr/core/servers/deploy/install/install-consoles)  |
|**Usare Configuration Manager per eseguire l'onboardboard** dei dispositivi in Microsoft Defender for Endpoint <br/><br/> *Se hai dispositivi (o endpoint) non ancora onboarded in Microsoft Defender for Endpoint, puoi farlo con Configuration Manager.*   |[Onboard to Microsoft Defender for Endpoint with Configuration Manager](/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection#about-onboarding-to-atp-with-configuration-manager)      |
|**Gestire i criteri antimalware e Windows firewall per** i computer client (endpoint)<br/><br/>*Configurare le funzionalità di protezione degli endpoint, tra cui Microsoft Defender for Endpoint, protezione da exploit, controllo delle applicazioni, antimalware, impostazioni del firewall e altro ancora.*  |[Configuration Manager: Endpoint Protection](/mem/configmgr/protect/deploy-use/endpoint-protection)       |
|**Scegliere i metodi per l'aggiornamento degli aggiornamenti antimalware** nei dispositivi dell'organizzazione <br/><br/>*Con Endpoint Protection in Configuration Manager, puoi scegliere tra diversi metodi per mantenere aggiornate le definizioni antimalware nei dispositivi dell'organizzazione.* |[Configurare gli aggiornamenti delle definizioni per Endpoint Protection](/mem/configmgr/protect/deploy-use/endpoint-definition-updates) <br/><br/>[Usare Configuration Manager per distribuire gli aggiornamenti delle definizioni](/mem/configmgr/protect/deploy-use/endpoint-definitions-configmgr) |
|**Abilitare Protezione di rete** per impedire ai dipendenti di usare app con contenuti dannosi su Internet <br/><br/>*Ti consigliamo di [usare prima la modalità](/microsoft-365/security/defender-endpoint/evaluate-network-protection) di controllo per la protezione di rete in un ambiente di testing per vedere quali app verrebbero bloccate prima dell'implementazione.* |[Attivare la protezione di rete con Configuration Manager](/microsoft-365/security/defender-endpoint/enable-network-protection#microsoft-endpoint-configuration-manager)  |
|**Configurare l'accesso controllato alle cartelle** per la protezione da ransomware <br/><br/>*L'accesso controllato alle cartelle viene anche definito protezione antiransomware.*   |[Endpoint protection: accesso controllato alle cartelle](/mem/intune/protect/endpoint-protection-windows-10#controlled-folder-access) <br/><br/>[Abilitare l'accesso controllato alle cartelle in Gestione configurazione endpoint Microsoft](/microsoft-365/security/defender-endpoint/enable-controlled-folders#microsoft-endpoint-configuration-manager) |

## <a name="configure-your-microsoft-defender-security-center"></a>Configurare il Microsoft Defender Security Center

Se non l'hai già fatto, configura il portale di Microsoft 365 Defender per visualizzare gli avvisi, configurare le funzionalità di protezione dalle minacce e visualizzare informazioni dettagliate sulla sicurezza complessiva dell'organizzazione. Vedere [Microsoft Defender Security Center](microsoft-defender-security-center.md). Puoi anche configurare se e quali funzionalità possono essere visualizzati dagli utenti finali nel portale Microsoft 365 Defender.

- [Panoramica della Microsoft Defender Security Center](/microsoft-365/security/defender-endpoint/use)

- [Endpoint protection: Microsoft Defender Security Center](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a>Passaggi successivi

- [Ottenere una panoramica di gestione di minacce e vulnerabilità](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [Visitare il dashboard Microsoft Defender Security Center delle operazioni di sicurezza](/microsoft-365/security/defender-endpoint/security-operations-dashboard)

- [Gestire Microsoft Defender per Endpoint con Intune](manage-atp-post-migration-intune.md)
