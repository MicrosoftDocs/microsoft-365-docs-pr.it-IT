---
title: Configurare le funzionalità per la riduzione della superficie di attacco
description: Utilizzare Microsoft Intune, Microsoft Endpoint Configuration Manager, i cmdlet di PowerShell e Criteri di gruppo per configurare la riduzione della superficie di attacco.
keywords: asr, riduzione della superficie di attacco, windows defender, microsoft defender, antivirus, av
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
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.date: 06/02/2021
ms.openlocfilehash: 948b5dc201526bf54aae0e857cfd40dcc9fe1e19
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2021
ms.locfileid: "52984449"
---
# <a name="configure-attack-surface-reduction-capabilities"></a>Configurare le funzionalità per la riduzione della superficie di attacco

**Si applica a:**

- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Defender for Endpoint include diverse funzionalità di riduzione della superficie di attacco. Per altre informazioni, vedi [Panoramica delle funzionalità di riduzione della superficie di attacco.](overview-attack-surface-reduction.md) Per configurare la riduzione della superficie di attacco nell'ambiente, attenersi alla seguente procedura:

1. [Abilitare l'isolamento basato su hardware per Microsoft Edge](/windows/security/threat-protection/microsoft-defender-application-guard/install-md-app-guard).

2. Abilita il controllo dell'applicazione.

   1. Esaminare i criteri di base in Windows. Vedere [Criteri di base di esempio.](/windows/security/threat-protection/windows-defender-application-control/example-wdac-base-policies)
   2. Vedi la [guida Windows Defender progettazione di Application Control](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-design-guide).
   3. Fare riferimento [a Deploying Windows Defender Application Control (WDAC)](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-deployment-guide).

3. [Abilitare l'accesso controllato alle cartelle](enable-controlled-folders.md).

4. [Attivare Protezione di rete](enable-network-protection.md).

5. [Abilita protezione da exploit](enable-exploit-protection.md).

6. [Configurare le regole di riduzione della superficie di attacco](enable-attack-surface-reduction.md).

7. Configurare il firewall di rete.

   1. Ottieni una panoramica di [Windows Defender Firewall con sicurezza avanzata.](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)
   2. Usa la [Windows Defender progettazione del firewall per](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-design-guide) decidere come progettare i criteri firewall.
   3. Utilizzare la [Windows Defender di distribuzione di Firewall per](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-deployment-guide) configurare il firewall dell'organizzazione con sicurezza avanzata.

> [!TIP]
> Nella maggior parte dei casi, quando si configurano le funzionalità di riduzione della superficie di attacco, è possibile scegliere tra diversi metodi:

> - Microsoft Endpoint Manager (che ora include Microsoft Intune e Microsoft Endpoint Configuration Manager)
> - Criteri di gruppo
> - Cmdlet di PowerShell
