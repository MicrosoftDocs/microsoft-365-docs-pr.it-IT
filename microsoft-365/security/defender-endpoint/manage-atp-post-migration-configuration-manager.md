---
title: Gestire Microsoft Defender per Endpoint con Configuration Manager
description: Informazioni su come gestire Microsoft Defender per Endpoint con Configuration Manager
keywords: post-migrazione, gestire, operazioni, manutenzione, utilizzo, Configuration Manager, windows defender advanced threat protection, atp, edr
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
ms.date: 09/22/2020
ms.reviewer: chventou
ms.openlocfilehash: 36599d830ac737b112df9f7c948e65829d6a7ce6
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51066837"
---
# <a name="manage-microsoft-defender-for-endpoint-with-configuration-manager"></a>Gestire Microsoft Defender per Endpoint con Configuration Manager

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender ATP](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


È consigliabile usare [Microsoft Endpoint Manager,](https://docs.microsoft.com/mem)che include [Microsoft Intune (Intune)](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) e Microsoft Endpoint Configuration Manager (Configuration [Manager)](https://docs.microsoft.com/mem/configmgr/core/understand/introduction) per gestire le funzionalità di protezione dalle minacce dell'organizzazione per i dispositivi (anche denominate endpoint). 
- [Altre informazioni su Endpoint Manager](https://docs.microsoft.com/mem/endpoint-manager-overview)
- [Co-gestire Microsoft Defender per Endpoint nei dispositivi Windows 10 con Configuration Manager e Intune](manage-atp-post-migration-intune.md)

## <a name="configure-microsoft-defender-for-endpoint-with-configuration-manager"></a>Configurare Microsoft Defender per Endpoint con Configuration Manager

|Attività  |Risorse per approfondire  |
|---------|---------|
|**Installare la console di Configuration Manager** se non è già presente<br/><br/>*Se non hai già la console Configuration Manger, usa queste risorse per ottenere i bit e installarla.* |[Ottenere il supporto di installazione](https://docs.microsoft.com/mem/configmgr/core/servers/deploy/install/get-install-media)<br/><br/>[Installare la console di Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/servers/deploy/install/install-consoles)  |
|**Usare Configuration Manager per eseguire l'onboardboard** dei dispositivi in Microsoft Defender for Endpoint <br/><br/> *Se hai dispositivi (o endpoint) non ancora onboarded in Microsoft Defender for Endpoint, puoi farlo con Configuration Manager.*   |[Onboard to Microsoft Defender for Endpoint with Configuration Manager](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection#about-onboarding-to-atp-with-configuration-manager)      |
|**Gestire i criteri antimalware e la sicurezza di Windows Firewall** per i computer client (endpoint)<br/><br/>*Configurare le funzionalità di protezione degli endpoint, tra cui Microsoft Defender for Endpoint, protezione da exploit, controllo delle applicazioni, antimalware, impostazioni del firewall e altro ancora.*  |[Configuration Manager: Endpoint Protection](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-protection)       |
|**Scegliere i metodi per l'aggiornamento degli aggiornamenti antimalware** nei dispositivi dell'organizzazione <br/><br/>*Con Endpoint Protection in Configuration Manager puoi scegliere tra diversi metodi per mantenere aggiornate le definizioni antimalware nei dispositivi dell'organizzazione.* |[Configurare gli aggiornamenti delle definizioni per Endpoint Protection](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-definition-updates) <br/><br/>[Usare Configuration Manager per distribuire gli aggiornamenti delle definizioni](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-definitions-configmgr) |
|**Abilitare Protezione di rete** per impedire ai dipendenti di usare app con contenuti dannosi su Internet <br/><br/>*Ti consigliamo di [usare prima la modalità](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/evaluate-network-protection) di controllo per la protezione di rete in un ambiente di testing per vedere quali app verrebbero bloccate prima dell'implementazione.* |[Attivare la protezione di rete con Configuration Manager](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/enable-network-protection#microsoft-endpoint-configuration-manager)  |
|**Configurare l'accesso controllato alle cartelle** per la protezione da ransomware <br/><br/>*L'accesso controllato alle cartelle viene anche definito protezione antiransomware.*   |[Endpoint protection: accesso controllato alle cartelle](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#controlled-folder-access) <br/><br/>[Abilitare l'accesso controllato alle cartelle in Gestione configurazione endpoint Microsoft](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/enable-controlled-folders#microsoft-endpoint-configuration-manager) |

## <a name="configure-your-microsoft-defender-security-center"></a>Configurare Microsoft Defender Security Center

Se non l'hai già fatto, configura **Microsoft Defender Security Center** ( ) per visualizzare gli avvisi, configurare le funzionalità di protezione dalle minacce e visualizzare informazioni dettagliate sulla sicurezza complessiva [https://securitycenter.windows.com](https://securitycenter.windows.com) dell'organizzazione. 

Puoi anche configurare se e quali funzionalità possono essere visualizzati dagli utenti finali in Microsoft Defender Security Center.

- [Panoramica di Microsoft Defender Security Center](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/use)

- [Endpoint protection: Microsoft Defender Security Center](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a>Passaggi successivi

- [Panoramica della gestione delle minacce e delle vulnerabilità](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [Visitare il dashboard delle operazioni di sicurezza di Microsoft Defender Security Center](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/security-operations-dashboard)

- [Gestire Microsoft Defender per Endpoint con Intune](manage-atp-post-migration-intune.md)
