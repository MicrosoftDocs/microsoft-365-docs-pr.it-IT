---
title: Pianificare analisi antivirus tramite PowerShell
description: Pianificare analisi antivirus tramite PowerShell
keywords: analisi rapida, analisi completa, antivirus, pianificazione, PowerShell
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/09/2021
ms.reviewer: pauhijbr, ksarens
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 73ba654dd312c63651f0cf43244796e94e8ad55b
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879714"
---
# <a name="schedule-antivirus-scans-using-powershell"></a>Pianificare analisi antivirus tramite PowerShell

**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)

In questo articolo viene descritto come configurare le analisi pianificate utilizzando i cmdlet di PowerShell. Per ulteriori informazioni sulla pianificazione delle analisi e sui tipi di analisi, vedere [Configure scheduled quick or full Antivirus Microsoft Defender scans](schedule-antivirus-scans.md). 

## <a name="use-powershell-cmdlets-to-schedule-scans"></a>Utilizzare i cmdlet di PowerShell per pianificare le analisi

Utilizzare i cmdlet seguenti:

```PowerShell
Set-MpPreference -ScanParameters
Set-MpPreference -ScanScheduleDay
Set-MpPreference -ScanScheduleTime
Set-MpPreference -RandomizeScheduleTaskTimes

```

Per ulteriori informazioni, vedere [Use PowerShell cmdlets to configure and run Antivirus Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Defender [cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Antivirus Microsoft Defender.

## <a name="powershell-cmdlets-for-scheduling-scans-when-an-endpoint-is-not-in-use"></a>Cmdlet di PowerShell per la pianificazione delle analisi quando un endpoint non è in uso

Utilizzare i cmdlet seguenti:

```PowerShell
Set-MpPreference -ScanOnlyIfIdleEnabled
```

Per altre informazioni, vedere [Usare i cmdlet di PowerShell per configurare ed eseguire Antivirus Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) e [Cmdlet di Defender](/powershell/module/defender/).

> [!NOTE]
> Quando si pianificano analisi per i periodi in cui gli endpoint non sono in uso, le analisi non rispettano la configurazione della limitazione della CPU e sfruttano al meglio le risorse disponibili per completare l'analisi il più velocemente possibile.

## <a name="powershell-cmdlets-for-scheduling-scans-to-complete-remediation"></a>Cmdlet di PowerShell per la pianificazione delle analisi per completare la correzione

Utilizzare i cmdlet seguenti:

```PowerShell
Set-MpPreference -RemediationScheduleDay
Set-MpPreference -RemediationScheduleTime
```

Per ulteriori informazioni su come usare PowerShell con Antivirus Microsoft Defender, vedere Use [PowerShell cmdlets to configure](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Antivirus Microsoft Defender run Antivirus Microsoft Defender and [Defender cmdlets.](/powershell/module/defender/)

## <a name="powershell-cmdlets-for-scheduling-daily-scans"></a>Cmdlet di PowerShell per la pianificazione delle analisi giornaliere

Utilizzare i cmdlet seguenti:

```PowerShell
Set-MpPreference -ScanScheduleQuickScanTime
```

Per ulteriori informazioni su come utilizzare PowerShell con Antivirus Microsoft Defender, vedere Utilizzare i cmdlet di [PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md) per configurare ed eseguire Antivirus Microsoft Defender [e i cmdlet defender.](/powershell/module/defender/)


