---
title: Pianificare le analisi antivirus tramite strumentazione Windows management
description: Pianificare analisi antivirus tramite WMI
keywords: analisi rapida, analisi completa, WMI, pianificazione, antivirus
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
ms.openlocfilehash: 1aa174f4601fb57eebbc4fb7c78e1809b9f072c8
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879709"
---
# <a name="schedule-antivirus-scans-using-windows-management-instrumentation-wmi"></a>Pianificare le analisi antivirus tramite Windows Management Instrumentation (WMI)

**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)

In questo articolo viene descritto come configurare le analisi pianificate tramite WMI. Per ulteriori informazioni sulla pianificazione delle analisi e sui tipi di analisi, vedere [Configure scheduled quick or full Antivirus Microsoft Defender scans](schedule-antivirus-scans.md). 

## <a name="use-windows-management-instruction-wmi-to-schedule-scans"></a>Utilizzare Windows Management Instruction (WMI) per pianificare le analisi

Utilizzare il [ **metodo Set** della **classe MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) per le proprietà seguenti:

```WMI
ScanParameters
ScanScheduleDay
ScanScheduleTime
RandomizeScheduleTaskTimes
```

Per altre informazioni e parametri consentiti, [Windows Defender API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="wmi-for-scheduling-scans-when-an-endpoint-is-not-in-use"></a>WMI per la pianificazione delle analisi quando un endpoint non è in uso

Utilizzare il [metodo Set della classe MSFT_MpPreference per](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) le proprietà seguenti:

```WMI
ScanOnlyIfIdleEnabled
```

Per altre informazioni sulle API e sui parametri consentiti, vedi Windows Defender [API WMIv2.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

> [!NOTE]
> Quando si pianificano analisi per i periodi in cui gli endpoint non sono in uso, le analisi non rispettano la configurazione della limitazione della CPU e sfruttano al meglio le risorse disponibili per completare l'analisi il più velocemente possibile.


## <a name="wmi-for-scheduling-scans-to-complete-remediation"></a>WMI per la pianificazione delle analisi per completare la correzione

Utilizzare il [ **metodo Set** della **classe MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) per le proprietà seguenti:

```WMI
RemediationScheduleDay
RemediationScheduleTime
```

Per altre informazioni e parametri consentiti, [Windows Defender API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).

## <a name="wmi-for-scheduling-daily-scans"></a>WMI per la pianificazione delle analisi giornaliere

Utilizzare il [ **metodo Set** della **classe MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) per le proprietà seguenti:

```WMI
ScanScheduleQuickScanTime
```

Per altre informazioni e parametri consentiti, [Windows Defender API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).

