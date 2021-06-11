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
# <a name="schedule-antivirus-scans-using-powershell"></a><span data-ttu-id="507e4-104">Pianificare analisi antivirus tramite PowerShell</span><span class="sxs-lookup"><span data-stu-id="507e4-104">Schedule antivirus scans using PowerShell</span></span>

<span data-ttu-id="507e4-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="507e4-105">**Applies to:**</span></span>

- [<span data-ttu-id="507e4-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="507e4-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="507e4-107">In questo articolo viene descritto come configurare le analisi pianificate utilizzando i cmdlet di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="507e4-107">This article describes how to configure scheduled scans using PowerShell cmdlets.</span></span> <span data-ttu-id="507e4-108">Per ulteriori informazioni sulla pianificazione delle analisi e sui tipi di analisi, vedere [Configure scheduled quick or full Antivirus Microsoft Defender scans](schedule-antivirus-scans.md).</span><span class="sxs-lookup"><span data-stu-id="507e4-108">To learn more about scheduling scans and about scan types, see [Configure scheduled quick or full Microsoft Defender Antivirus scans](schedule-antivirus-scans.md).</span></span> 

## <a name="use-powershell-cmdlets-to-schedule-scans"></a><span data-ttu-id="507e4-109">Utilizzare i cmdlet di PowerShell per pianificare le analisi</span><span class="sxs-lookup"><span data-stu-id="507e4-109">Use PowerShell cmdlets to schedule scans</span></span>

<span data-ttu-id="507e4-110">Utilizzare i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="507e4-110">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanParameters
Set-MpPreference -ScanScheduleDay
Set-MpPreference -ScanScheduleTime
Set-MpPreference -RandomizeScheduleTaskTimes

```

<span data-ttu-id="507e4-111">Per ulteriori informazioni, vedere [Use PowerShell cmdlets to configure and run Antivirus Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Defender [cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Antivirus Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="507e4-111">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

## <a name="powershell-cmdlets-for-scheduling-scans-when-an-endpoint-is-not-in-use"></a><span data-ttu-id="507e4-112">Cmdlet di PowerShell per la pianificazione delle analisi quando un endpoint non è in uso</span><span class="sxs-lookup"><span data-stu-id="507e4-112">PowerShell cmdlets for scheduling scans when an endpoint is not in use</span></span>

<span data-ttu-id="507e4-113">Utilizzare i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="507e4-113">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanOnlyIfIdleEnabled
```

<span data-ttu-id="507e4-114">Per altre informazioni, vedere [Usare i cmdlet di PowerShell per configurare ed eseguire Antivirus Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) e [Cmdlet di Defender](/powershell/module/defender/).</span><span class="sxs-lookup"><span data-stu-id="507e4-114">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

> [!NOTE]
> <span data-ttu-id="507e4-115">Quando si pianificano analisi per i periodi in cui gli endpoint non sono in uso, le analisi non rispettano la configurazione della limitazione della CPU e sfruttano al meglio le risorse disponibili per completare l'analisi il più velocemente possibile.</span><span class="sxs-lookup"><span data-stu-id="507e4-115">When you schedule scans for times when endpoints are not in use, scans do not honor the CPU throttling configuration and will take full advantage of the resources available to complete the scan as fast as possible.</span></span>

## <a name="powershell-cmdlets-for-scheduling-scans-to-complete-remediation"></a><span data-ttu-id="507e4-116">Cmdlet di PowerShell per la pianificazione delle analisi per completare la correzione</span><span class="sxs-lookup"><span data-stu-id="507e4-116">PowerShell cmdlets for scheduling scans to complete remediation</span></span>

<span data-ttu-id="507e4-117">Utilizzare i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="507e4-117">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -RemediationScheduleDay
Set-MpPreference -RemediationScheduleTime
```

<span data-ttu-id="507e4-118">Per ulteriori informazioni su come usare PowerShell con Antivirus Microsoft Defender, vedere Use [PowerShell cmdlets to configure](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Antivirus Microsoft Defender run Antivirus Microsoft Defender and [Defender cmdlets.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="507e4-118">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

## <a name="powershell-cmdlets-for-scheduling-daily-scans"></a><span data-ttu-id="507e4-119">Cmdlet di PowerShell per la pianificazione delle analisi giornaliere</span><span class="sxs-lookup"><span data-stu-id="507e4-119">PowerShell cmdlets for scheduling daily scans</span></span>

<span data-ttu-id="507e4-120">Utilizzare i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="507e4-120">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanScheduleQuickScanTime
```

<span data-ttu-id="507e4-121">Per ulteriori informazioni su come utilizzare PowerShell con Antivirus Microsoft Defender, vedere Utilizzare i cmdlet di [PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md) per configurare ed eseguire Antivirus Microsoft Defender [e i cmdlet defender.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="507e4-121">For more information about how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>


