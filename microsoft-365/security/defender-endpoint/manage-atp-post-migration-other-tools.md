---
title: Gestire Microsoft Defender per Endpoint tramite PowerShell, WMI e MPCmdRun.exe
description: Informazioni su come gestire Microsoft Defender per Endpoint con PowerShell, WMI e MPCmdRun.exe
keywords: post-migrazione, gestire, operazioni, manutenzione, utilizzo, PowerShell, WMI, MPCmdRun.exe, Microsoft Defender for Endpoint, edr
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
ms.openlocfilehash: 063870c58377d7327f621ec49855b684065f436b
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286766"
---
# <a name="manage-microsoft-defender-for-endpoint-with-powershell-wmi-and-mpcmdrunexe"></a>Gestire Microsoft Defender per Endpoint con PowerShell, WMI e MPCmdRun.exe

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!NOTE]
> È consigliabile [usare Microsoft Endpoint Manager](/mem) per gestire le funzionalità di protezione dalle minacce dell'organizzazione per i dispositivi (denominati anche endpoint). Endpoint Manager include [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) e [Microsoft Endpoint Configuration Manager](/mem/configmgr/core/understand/introduction).
>
> - [Ulteriori informazioni su Endpoint Manager](/mem/endpoint-manager-overview)
> - [Co-gestire Microsoft Defender for Endpoint nei dispositivi Windows 10 con Configuration Manager e Intune](manage-atp-post-migration-intune.md)
> - [Gestire Microsoft Defender per Endpoint con Intune](manage-atp-post-migration-intune.md)

È possibile gestire alcune impostazioni Antivirus Microsoft Defender nei dispositivi con [PowerShell,](#configure-microsoft-defender-for-endpoint-with-powershell) [Strumentazione](#configure-microsoft-defender-for-endpoint-with-windows-management-instrumentation-wmi) gestione Windows (WMI) e [Microsoft Malware Protection Command Line Utility](#configure-microsoft-defender-for-endpoint-with-microsoft-malware-protection-command-line-utility-mpcmdrunexe) (MPCmdRun.exe). Ad esempio, è possibile gestire alcune impostazioni Antivirus Microsoft Defender predefinite. E, in alcuni casi, è possibile personalizzare le regole di riduzione della superficie di attacco e le impostazioni di protezione degli exploit.

> [!IMPORTANT]
> Le funzionalità di protezione dalle minacce configurate tramite PowerShell, WMI o MCPmdRun.exe possono essere sovrascritte dalle impostazioni di configurazione distribuite con Intune o Configuration Manager.

## <a name="configure-microsoft-defender-for-endpoint-with-powershell"></a>Configurare Microsoft Defender per Endpoint con PowerShell

È possibile usare PowerShell per gestire le Antivirus Microsoft Defender, la protezione da exploit e le regole di riduzione della superficie di attacco.

|Attività|Risorse per approfondire|
|---|---|
|**Gestire Antivirus Microsoft Defender** <p> Visualizzare lo stato della protezione antimalware, configurare le preferenze per le analisi antivirus & aggiornamenti e apportare altre modifiche alla protezione antivirus.*|[Utilizzare i cmdlet di PowerShell per configurare e gestire Antivirus Microsoft Defender](/windows/security/threat-protection/microsoft-defender-antivirus/use-powershell-cmdlets-microsoft-defender-antivirus) <p> [Usare i cmdlet di PowerShell per abilitare la protezione recapitata nel cloud](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus#use-powershell-cmdlets-to-enable-cloud-delivered-protection)|
|**Configurare la protezione da** exploit per ridurre le minacce nei dispositivi dell'organizzazione <p> *È consigliabile usare la protezione degli exploit in [modalità](/microsoft-365/security/defender-endpoint/evaluate-exploit-protection#powershell) di controllo in un primo momento. In questo modo, puoi vedere in che modo la protezione degli exploit influisce sulle app che l'organizzazione usa.*|[Personalizzare la protezione dagli exploit](/microsoft-365/security/defender-endpoint/customize-exploit-protection) <p> [Cmdlet di PowerShell per la protezione degli exploit](/microsoft-365/security/defender-endpoint/customize-exploit-protection#powershell-reference)|
|**Configurare le regole di riduzione della superficie di** attacco con PowerShell <p> *È possibile utilizzare PowerShell per escludere file e cartelle dalle regole di riduzione della superficie di attacco.*|[Personalizzare le regole di riduzione della superficie di attacco: usare PowerShell per escludere i file & cartelle](/microsoft-365/security/defender-endpoint/customize-attack-surface-reduction#use-powershell-to-exclude-files-and-folders) <p> Vedi anche lo strumento dell'interfaccia utente grafica di [António Vasconcelo per l'impostazione](https://github.com/anvascon/MDATP_PoSh_Scripts/tree/master/ASR%20GUI)delle regole di riduzione della superficie di attacco con PowerShell.|
|**Abilitare Protezione di rete** con PowerShell <p> *È possibile usare PowerShell per abilitare Protezione di rete.*|[Attivare Protezione di rete con PowerShell](/microsoft-365/security/defender-endpoint/enable-network-protection#powershell)|
|**Configurare l'accesso controllato alle cartelle** per la protezione da ransomware <p> *[L'accesso controllato](/microsoft-365/security/defender-endpoint/controlled-folders) alle cartelle viene anche definito protezione antiransomware.*|[Abilitare l'accesso controllato alle cartelle con PowerShell](/microsoft-365/security/defender-endpoint/enable-controlled-folders#powershell)|
|**Configurare Microsoft Defender Firewall per** bloccare il traffico di rete non autorizzato che entra o esce dai dispositivi dell'organizzazione|[Microsoft Defender Firewall con Advanced Security Administration con Windows PowerShell](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-administration-with-windows-powershell)|
|**Configurare la crittografia e BitLocker** per proteggere le informazioni sui dispositivi dell'organizzazione che eseguono Windows|[Guida di riferimento di PowerShell per BitLocker](/powershell/module/bitlocker/)|

## <a name="configure-microsoft-defender-for-endpoint-with-windows-management-instrumentation-wmi"></a>Configurare Microsoft Defender per Endpoint con Windows Management Instrumentation (WMI)

WMI è un'interfaccia di script che consente di recuperare, modificare e aggiornare le impostazioni. Per ulteriori informazioni, vedere [Using WMI](/windows/win32/wmisdk/using-wmi).

|Attività|Risorse per approfondire|
|---|---|
|**Abilitare la protezione con distribuzione cloud** in un dispositivo|[Utilizzare Windows Management Instruction (WMI) per abilitare la protezione basata sul cloud](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus#use-windows-management-instruction-wmi-to-enable-cloud-delivered-protection)|
|**Recuperare, modificare e aggiornare le impostazioni** per Antivirus Microsoft Defender|[Utilizzare WMI per configurare e gestire Antivirus Microsoft Defender] (/windows/security/threat-protection/microsoft-defender-antivirus/use-wmi-microsoft-defender-antivirus <p> [Esaminare l'elenco delle classi WMI disponibili e degli script di esempio](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) <p> Vedi anche le informazioni di [riferimento Windows Defender provider WMIv2 archiviate](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal?redirectedfrom=MSDN)|

## <a name="configure-microsoft-defender-for-endpoint-with-microsoft-malware-protection-command-line-utility-mpcmdrunexe"></a>Configurare Microsoft Defender per Endpoint con Microsoft Malware Protection Command-Line Utility (MPCmdRun.exe)

In un singolo dispositivo, è possibile eseguire un'analisi, avviare l'analisi diagnostica, verificare la disponibilità di aggiornamenti delle funzionalità di intelligence per la sicurezza e altro ancora usando lo mpcmdrun.exe da riga di comando. È possibile trovare l'utilità in `%ProgramFiles%\Windows Defender\MpCmdRun.exe` . Eseguirlo da un prompt dei comandi.

|Attività|Risorse per approfondire|
|---|---|
|**Gestire Antivirus Microsoft Defender**|[Configurare e gestire Antivirus Microsoft Defender con mpcmdrun.exe](/windows/security/threat-protection/microsoft-defender-antivirus/command-line-arguments-microsoft-defender-antivirus)|

## <a name="configure-your-microsoft-defender-security-center"></a>Configurare il Microsoft Defender Security Center

Se non è già stato fatto, configurare il **Microsoft Defender Security Center** ( ) per visualizzare gli avvisi, configurare le funzionalità di protezione dalle minacce e visualizzare informazioni dettagliate sulla sicurezza complessiva [https://securitycenter.windows.com](https://securitycenter.windows.com) dell'organizzazione.

È inoltre possibile configurare se e quali funzionalità gli utenti finali possono visualizzare nella Microsoft Defender Security Center.

- [Panoramica della Microsoft Defender Security Center](/microsoft-365/security/defender-endpoint/use)

- [Endpoint protection: Microsoft Defender Security Center](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a>Passaggi successivi

- [Panoramica della gestione di minacce e vulnerabilità](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [Visitare il dashboard Microsoft Defender Security Center delle operazioni di sicurezza](/microsoft-365/security/defender-endpoint/security-operations-dashboard)

- [Gestire Microsoft Defender per Endpoint con Intune](manage-atp-post-migration-intune.md)
