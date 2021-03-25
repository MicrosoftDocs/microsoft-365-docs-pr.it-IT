---
title: Gestire Microsoft Defender per Endpoint tramite PowerShell, WMI e MPCmdRun.exe
description: Informazioni su come gestire Microsoft Defender per Endpoint con PowerShell, WMI e MPCmdRun.exe
keywords: post-migrazione, gestire, operazioni, manutenzione, utilizzo, PowerShell, WMI, MPCmdRun.exe, windows defender advanced threat protection, atp, edr
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
ms.openlocfilehash: 5f0e94360cfaa0c66aedec400e81adc85f4f5450
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185874"
---
# <a name="manage-microsoft-defender-for-endpoint-with-powershell-wmi-and-mpcmdrunexe"></a>Gestire Microsoft Defender per Endpoint con PowerShell, WMI e MPCmdRun.exe

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!NOTE]
> È consigliabile [usare Microsoft Endpoint Manager](https://docs.microsoft.com/mem) per gestire le funzionalità di protezione dalle minacce dell'organizzazione per i dispositivi (denominati anche endpoint). Endpoint Manager include [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) e Microsoft Endpoint [Configuration Manager.](https://docs.microsoft.com/mem/configmgr/core/understand/introduction) 
> - [Altre informazioni su Endpoint Manager](https://docs.microsoft.com/mem/endpoint-manager-overview)
> - [Co-gestire Microsoft Defender per Endpoint nei dispositivi Windows 10 con Configuration Manager e Intune](manage-atp-post-migration-intune.md)
> - [Gestire Microsoft Defender per Endpoint con Intune](manage-atp-post-migration-intune.md) 

È possibile gestire alcune impostazioni di Microsoft Defender Antivirus nei dispositivi con [PowerShell,](#configure-microsoft-defender-for-endpoint-with-powershell)  [Strumentazione](#configure-microsoft-defender-for-endpoint-with-windows-management-instrumentation-wmi) gestione Windows (WMI) e [Microsoft Malware Protection Command Line Utility](#configure-microsoft-defender-for-endpoint-with-microsoft-malware-protection-command-line-utility-mpcmdrunexe) (MPCmdRun.exe). Ad esempio, puoi gestire alcune impostazioni di Microsoft Defender Antivirus. E, in alcuni casi, è possibile personalizzare le regole di riduzione della superficie di attacco e le impostazioni di protezione degli exploit. 

> [!IMPORTANT]
> Le funzionalità di protezione dalle minacce configurate tramite PowerShell, WMI o MCPmdRun.exe possono essere sovrascritte dalle impostazioni di configurazione distribuite con Intune o Configuration Manager.

## <a name="configure-microsoft-defender-for-endpoint-with-powershell"></a>Configurare Microsoft Defender per Endpoint con PowerShell

Puoi usare PowerShell per gestire Microsoft Defender Antivirus, la protezione da exploit e le regole di riduzione della superficie di attacco.

|Attività  |Risorse per approfondire  |
|---------|---------|
|**Gestire Microsoft Defender Antivirus** <br/><br/>*Visualizzare lo stato della protezione antimalware, configurare le preferenze per le analisi antivirus & aggiornamenti e apportare altre modifiche alla protezione antivirus.*    |[Utilizzare i cmdlet di PowerShell per configurare e gestire Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/use-powershell-cmdlets-microsoft-defender-antivirus)  <br/><br/>[Usare i cmdlet di PowerShell per abilitare la protezione recapitata nel cloud](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus#use-powershell-cmdlets-to-enable-cloud-delivered-protection)       |
|**Configurare la protezione da** exploit per ridurre le minacce nei dispositivi dell'organizzazione<br/><br/> *È consigliabile usare la protezione degli exploit in [modalità](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/evaluate-exploit-protection#powershell) di controllo in un primo momento. In questo modo, puoi vedere in che modo la protezione degli exploit influisce sulle app che l'organizzazione usa.*     | [Personalizzare la protezione da exploit](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/customize-exploit-protection)<br/><br/>[Cmdlet di PowerShell per la protezione degli exploit](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/customize-exploit-protection#powershell-reference)        |
|**Configurare le regole di riduzione della superficie di** attacco con PowerShell <br/><br/>*È possibile utilizzare PowerShell per escludere file e cartelle dalle regole di riduzione della superficie di attacco.* |[Personalizzare le regole di riduzione della superficie di attacco: usare PowerShell per escludere i file & cartelle](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/customize-attack-surface-reduction#use-powershell-to-exclude-files-and-folders)<br/><br/>Vedi anche lo strumento dell'interfaccia utente grafica di [António Vasconcelo per l'impostazione](https://github.com/anvascon/MDATP_PoSh_Scripts/tree/master/ASR%20GUI)delle regole di riduzione della superficie di attacco con PowerShell. |
|**Abilitare Protezione di rete** con PowerShell <br/><br/>*È possibile usare PowerShell per abilitare Protezione di rete.* |[Attivare Protezione di rete con PowerShell](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/enable-network-protection#powershell) |
|**Configurare l'accesso controllato alle cartelle** per la protezione da ransomware <br/><br/>*[L'accesso controllato](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/controlled-folders) alle cartelle viene anche definito protezione antiransomware.* |[Abilitare l'accesso controllato alle cartelle con PowerShell](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/enable-controlled-folders#powershell) |
|**Configurare Microsoft Defender Firewall per** bloccare il traffico di rete non autorizzato che entra o esce dai dispositivi dell'organizzazione |[Microsoft Defender Firewall con Advanced Security Administration con Windows PowerShell](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-administration-with-windows-powershell) |
|**Configurare la crittografia e BitLocker** per proteggere le informazioni sui dispositivi dell'organizzazione che eseguono Windows |[Guida di riferimento di PowerShell per BitLocker](https://docs.microsoft.com/powershell/module/bitlocker/?view=win10-ps&preserve-view=true) |

## <a name="configure-microsoft-defender-for-endpoint-with-windows-management-instrumentation-wmi"></a>Configurare Microsoft Defender per Endpoint con Strumentazione gestione Windows (WMI)

WMI è un'interfaccia di script che consente di recuperare, modificare e aggiornare le impostazioni. Per ulteriori informazioni, vedere [Using WMI](https://docs.microsoft.com/windows/win32/wmisdk/using-wmi). 

|Attività  |Risorse per approfondire  |
|---------|---------|
|**Abilitare la protezione con distribuzione cloud** in un dispositivo    |[Usare Windows Management Instruction (WMI) per abilitare la protezione basata sul cloud](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus#use-windows-management-instruction-wmi-to-enable-cloud-delivered-protection)       |
|**Recuperare, modificare e aggiornare le impostazioni** per Microsoft Defender Antivirus     | [Utilizzare WMI per configurare e gestire Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/use-wmi-microsoft-defender-antivirus)<br/><br/>[Esaminare l'elenco delle classi WMI disponibili e degli script di esempio](https://docs.microsoft.com/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) <br/><br/>Vedi anche le informazioni di [riferimento Windows Defender provider WMIv2 archiviate](https://docs.microsoft.com/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal?redirectedfrom=MSDN)   |


## <a name="configure-microsoft-defender-for-endpoint-with-microsoft-malware-protection-command-line-utility-mpcmdrunexe"></a>Configurare Microsoft Defender per Endpoint con Microsoft Malware Protection Command-Line Utility (MPCmdRun.exe)

In un singolo dispositivo, è possibile eseguire un'analisi, avviare l'analisi diagnostica, verificare la disponibilità di aggiornamenti delle funzionalità di intelligence per la sicurezza e altro ancora usando lo mpcmdrun.exe da riga di comando. È possibile trovare l'utilità in `%ProgramFiles%\Windows Defender\MpCmdRun.exe` . Eseguirlo da un prompt dei comandi.

|Attività  |Risorse per approfondire  |
|---------|---------|
|**Gestire Microsoft Defender Antivirus**  |[Configurare e gestire Microsoft Defender Antivirus con mpcmdrun.exe](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/command-line-arguments-microsoft-defender-antivirus)        |

## <a name="configure-your-microsoft-defender-security-center"></a>Configurare Microsoft Defender Security Center

Se non l'hai già fatto, configura **Microsoft Defender Security Center** ( ) per visualizzare gli avvisi, configurare le funzionalità di protezione dalle minacce e visualizzare informazioni dettagliate sulla sicurezza complessiva [https://securitycenter.windows.com](https://securitycenter.windows.com) dell'organizzazione. 

Puoi anche configurare se e quali funzionalità possono essere visualizzati dagli utenti finali in Microsoft Defender Security Center.

- [Panoramica di Microsoft Defender Security Center](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/use)

- [Endpoint protection: Microsoft Defender Security Center](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)


## <a name="next-steps"></a>Passaggi successivi

- [Panoramica della gestione delle minacce e delle vulnerabilità](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [Visitare il dashboard delle operazioni di sicurezza di Microsoft Defender Security Center](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/security-operations-dashboard)

- [Gestire Microsoft Defender per Endpoint con Intune](manage-atp-post-migration-intune.md)
