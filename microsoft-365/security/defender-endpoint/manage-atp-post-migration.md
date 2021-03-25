---
title: Gestire Microsoft Defender for Endpoint dopo la migrazione
description: Dopo aver effettuato il passaggio a Microsoft Defender for Endpoint, il passaggio successivo consiste nel gestire le funzionalità di protezione dalle minacce
keywords: post-migrazione, gestire, operazioni, manutenzione, utilizzo, windows defender advanced threat protection, atp, edr
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
ms.topic: conceptual
ms.date: 01/26/2021
ms.reviewer: chventou
ms.openlocfilehash: 54302f38f0fd63560ecd1c5545efa4621c6b9bbd
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185862"
---
# <a name="manage-microsoft-defender-for-endpoint-post-migration"></a>Gestire Microsoft Defender for Endpoint, dopo la migrazione

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Dopo aver spostato la soluzione antivirus e di protezione degli endpoint precedente in Microsoft Defender for Endpoint, il passaggio successivo consiste nel gestire le funzionalità e le funzionalità. Ti consigliamo di [usare Microsoft Endpoint Manager,](https://docs.microsoft.com/mem/endpoint-manager-overview)che include [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) e Microsoft Endpoint [Configuration Manager,](https://docs.microsoft.com/mem/configmgr/core/understand/introduction)per gestire i dispositivi e le impostazioni di sicurezza dell'organizzazione. Tuttavia, è possibile utilizzare altri strumenti/metodi, ad esempio Oggetti Criteri di [gruppo in Servizi di dominio Azure Active Directory.](https://docs.microsoft.com/azure/active-directory-domain-services/manage-group-policy) 

Nella tabella seguente sono elencati vari strumenti/metodi che è possibile utilizzare, con collegamenti per ulteriori informazioni. 
<br/><br/>

|Tool/Metodo  |Descrizione  |
|---------|---------|
|**[Informazioni dettagliate sul dashboard di gestione delle](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-dashboard-insights)** minacce e delle vulnerabilità in Microsoft Defender Security Center ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ) |Il dashboard & di gestione delle vulnerabilità fornisce informazioni utili che il team delle operazioni di sicurezza può utilizzare per ridurre l'esposizione e migliorare la sicurezza dell'organizzazione. <br/><br/>Vedi [Gestione & delle vulnerabilità](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) e Panoramica di Microsoft Defender Security [Center.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/use)  |
|**[Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)**  (scelta consigliata)    |Microsoft Intune (Intune), un componente di [Microsoft Endpoint Manager,](https://docs.microsoft.com/mem/endpoint-manager-overview)si concentra sulla gestione dei dispositivi mobili (MDM) e sulla gestione delle applicazioni mobili (MAM). Con Intune puoi controllare la modalità di utilizzo dei dispositivi dell'organizzazione, inclusi telefoni cellulari, tablet e portatili. È inoltre possibile configurare criteri specifici per controllare le applicazioni. <br/><br/>Vedi [Gestire Microsoft Defender per Endpoint con Intune.](manage-atp-post-migration-intune.md)         |
|**[Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/understand/introduction)**     |Microsoft Endpoint Manager (Configuration Manager), in precedenza noto come System Center Configuration Manager, è un componente di [Microsoft Endpoint Manager.](https://docs.microsoft.com/mem/endpoint-manager-overview) Configuration Manager è uno strumento potente per gestire utenti, dispositivi e software.<br/><br/>Vedi [Gestire Microsoft Defender per Endpoint con Configuration Manager.](manage-atp-post-migration-configuration-manager.md)        |
|**[Oggetti Criteri di gruppo in Servizi di dominio Azure Active Directory](https://docs.microsoft.com/azure/active-directory-domain-services/manage-group-policy)** |[Servizi di dominio Azure Active Directory](https://docs.microsoft.com/azure/active-directory-domain-services/overview) include oggetti Criteri di gruppo incorporati per utenti e dispositivi. È possibile personalizzare gli oggetti Criteri di gruppo incorporati in base alle esigenze dell'ambiente, nonché creare oggetti Criteri di gruppo e unità organizzative personalizzati. <br/><br/>Vedi [Gestire Microsoft Defender per Endpoint con oggetti Criteri di gruppo.](manage-atp-post-migration-group-policy-objects.md) |
|**[PowerShell, WMI e MPCmdRun.exe](manage-atp-post-migration-other-tools.md)** |*Ti consigliamo di usare Microsoft Endpoint Manager (che include Intune e Configuration Manager) per gestire le funzionalità di protezione dalle minacce nei dispositivi dell'organizzazione. Tuttavia, è possibile configurare alcune impostazioni, ad esempio le impostazioni di Microsoft Defender Antivirus su singoli dispositivi (endpoint) con PowerShell, WMI o lo strumento MPCmdRun.exe.*<br/><br/>Puoi usare PowerShell per gestire Microsoft Defender Antivirus, la protezione da exploit e le regole di riduzione della superficie di attacco. Vedi [Configurare Microsoft Defender per Endpoint con PowerShell.](manage-atp-post-migration-other-tools.md#configure-microsoft-defender-for-endpoint-with-powershell)<br/><br/>È possibile utilizzare Strumentazione gestione Windows (WMI) per gestire Microsoft Defender Antivirus ed esclusioni. Vedi [Configurare Microsoft Defender per Endpoint con WMI.](manage-atp-post-migration-other-tools.md#configure-microsoft-defender-for-endpoint-with-windows-management-instrumentation-wmi)<br/><br/>Puoi usare Microsoft Malware Protection Command-Line Utility (MPCmdRun.exe) per gestire Microsoft Defender Antivirus e le esclusioni, nonché convalidare le connessioni tra la rete e il cloud. Vedi [Configurare Microsoft Defender per Endpoint con MPCmdRun.exe](manage-atp-post-migration-other-tools.md#configure-microsoft-defender-for-endpoint-with-microsoft-malware-protection-command-line-utility-mpcmdrunexe). |

## <a name="see-also"></a>Vedere anche

- [Risolvere i falsi positivi/negativi in Microsoft Defender for Endpoint](defender-endpoint-false-positives-negatives.md)
