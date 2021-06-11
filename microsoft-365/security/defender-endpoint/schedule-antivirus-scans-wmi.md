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
# <a name="schedule-antivirus-scans-using-windows-management-instrumentation-wmi"></a><span data-ttu-id="c7fa8-104">Pianificare le analisi antivirus tramite Windows Management Instrumentation (WMI)</span><span class="sxs-lookup"><span data-stu-id="c7fa8-104">Schedule antivirus scans using Windows Management Instrumentation (WMI)</span></span>

<span data-ttu-id="c7fa8-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="c7fa8-105">**Applies to:**</span></span>

- [<span data-ttu-id="c7fa8-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="c7fa8-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="c7fa8-107">In questo articolo viene descritto come configurare le analisi pianificate tramite WMI.</span><span class="sxs-lookup"><span data-stu-id="c7fa8-107">This article describes how to configure scheduled scans using WMI.</span></span> <span data-ttu-id="c7fa8-108">Per ulteriori informazioni sulla pianificazione delle analisi e sui tipi di analisi, vedere [Configure scheduled quick or full Antivirus Microsoft Defender scans](schedule-antivirus-scans.md).</span><span class="sxs-lookup"><span data-stu-id="c7fa8-108">To learn more about scheduling scans and about scan types, see [Configure scheduled quick or full Microsoft Defender Antivirus scans](schedule-antivirus-scans.md).</span></span> 

## <a name="use-windows-management-instruction-wmi-to-schedule-scans"></a><span data-ttu-id="c7fa8-109">Utilizzare Windows Management Instruction (WMI) per pianificare le analisi</span><span class="sxs-lookup"><span data-stu-id="c7fa8-109">Use Windows Management Instruction (WMI) to schedule scans</span></span>

<span data-ttu-id="c7fa8-110">Utilizzare il [ **metodo Set** della **classe MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) per le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="c7fa8-110">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanParameters
ScanScheduleDay
ScanScheduleTime
RandomizeScheduleTaskTimes
```

<span data-ttu-id="c7fa8-111">Per altre informazioni e parametri consentiti, [Windows Defender API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="c7fa8-111">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>

## <a name="wmi-for-scheduling-scans-when-an-endpoint-is-not-in-use"></a><span data-ttu-id="c7fa8-112">WMI per la pianificazione delle analisi quando un endpoint non è in uso</span><span class="sxs-lookup"><span data-stu-id="c7fa8-112">WMI for scheduling scans when an endpoint is not in use</span></span>

<span data-ttu-id="c7fa8-113">Utilizzare il [metodo Set della classe MSFT_MpPreference per](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="c7fa8-113">Use the [Set method of the MSFT_MpPreference class](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) for the following properties:</span></span>

```WMI
ScanOnlyIfIdleEnabled
```

<span data-ttu-id="c7fa8-114">Per altre informazioni sulle API e sui parametri consentiti, vedi Windows Defender [API WMIv2.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="c7fa8-114">For more information about APIs and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

> [!NOTE]
> <span data-ttu-id="c7fa8-115">Quando si pianificano analisi per i periodi in cui gli endpoint non sono in uso, le analisi non rispettano la configurazione della limitazione della CPU e sfruttano al meglio le risorse disponibili per completare l'analisi il più velocemente possibile.</span><span class="sxs-lookup"><span data-stu-id="c7fa8-115">When you schedule scans for times when endpoints are not in use, scans do not honor the CPU throttling configuration and will take full advantage of the resources available to complete the scan as fast as possible.</span></span>


## <a name="wmi-for-scheduling-scans-to-complete-remediation"></a><span data-ttu-id="c7fa8-116">WMI per la pianificazione delle analisi per completare la correzione</span><span class="sxs-lookup"><span data-stu-id="c7fa8-116">WMI for scheduling scans to complete remediation</span></span>

<span data-ttu-id="c7fa8-117">Utilizzare il [ **metodo Set** della **classe MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) per le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="c7fa8-117">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
RemediationScheduleDay
RemediationScheduleTime
```

<span data-ttu-id="c7fa8-118">Per altre informazioni e parametri consentiti, [Windows Defender API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span><span class="sxs-lookup"><span data-stu-id="c7fa8-118">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

## <a name="wmi-for-scheduling-daily-scans"></a><span data-ttu-id="c7fa8-119">WMI per la pianificazione delle analisi giornaliere</span><span class="sxs-lookup"><span data-stu-id="c7fa8-119">WMI for scheduling daily scans</span></span>

<span data-ttu-id="c7fa8-120">Utilizzare il [ **metodo Set** della **classe MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) per le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="c7fa8-120">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanScheduleQuickScanTime
```

<span data-ttu-id="c7fa8-121">Per altre informazioni e parametri consentiti, [Windows Defender API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span><span class="sxs-lookup"><span data-stu-id="c7fa8-121">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

