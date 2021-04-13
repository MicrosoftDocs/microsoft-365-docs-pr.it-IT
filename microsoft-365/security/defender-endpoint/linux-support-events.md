---
title: Risolvere i problemi relativi a eventi o avvisi mancanti per Microsoft Defender ATP per Linux
description: Risolvere i problemi di avvisi o eventi mancanti in Microsoft Defender ATP per Linux.
keywords: microsoft, defender, atp, linux, eventi
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
mms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 5981cb75b4c835390e27d902b5950e3c68305200
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687455"
---
# <a name="troubleshoot-missing-events-or-alerts-issues-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="a6480-104">Risolvere i problemi relativi a eventi o avvisi mancanti per Microsoft Defender per Endpoint su Linux</span><span class="sxs-lookup"><span data-stu-id="a6480-104">Troubleshoot missing events or alerts issues for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a6480-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="a6480-105">**Applies to:**</span></span>

- [<span data-ttu-id="a6480-106">Microsoft Defender per Endpoint su Linux</span><span class="sxs-lookup"><span data-stu-id="a6480-106">Microsoft Defender for Endpoint on Linux</span></span>](microsoft-defender-endpoint-linux.md)

<span data-ttu-id="a6480-107">Questo articolo illustra alcuni passaggi generali per ridurre gli eventi o gli avvisi mancanti nel [portale del centro sicurezza.](https://securitycenter.windows.com/)</span><span class="sxs-lookup"><span data-stu-id="a6480-107">This article provides some general steps to mitigate missing events or alerts in the [security center](https://securitycenter.windows.com/) portal.</span></span>

<span data-ttu-id="a6480-108">Dopo **che Microsoft Defender for Endpoint** è  stato installato correttamente in un dispositivo, verrà generata una pagina del dispositivo nel portale.</span><span class="sxs-lookup"><span data-stu-id="a6480-108">Once **Microsoft Defender for Endpoint** has been installed properly on a device, a _device page_ will be generated in the portal.</span></span> <span data-ttu-id="a6480-109">Puoi esaminare tutti gli eventi registrati nella scheda sequenza temporale nella pagina del dispositivo o nella pagina di ricerca avanzata.</span><span class="sxs-lookup"><span data-stu-id="a6480-109">You can review all recorded events in the timeline tab in the device page, or in advanced hunting page.</span></span> <span data-ttu-id="a6480-110">In questa sezione viene descritto il caso in cui mancano alcuni o tutti gli eventi previsti.</span><span class="sxs-lookup"><span data-stu-id="a6480-110">This section troubleshoots the case of some or all expected events are missing.</span></span>
<span data-ttu-id="a6480-111">Ad esempio, se mancano tutti gli eventi _CreatedFile._</span><span class="sxs-lookup"><span data-stu-id="a6480-111">For instance, if all _CreatedFile_ events are missing.</span></span>

## <a name="missing-network-and-login-events"></a><span data-ttu-id="a6480-112">Eventi di rete e accesso mancanti</span><span class="sxs-lookup"><span data-stu-id="a6480-112">Missing network and login events</span></span>

<span data-ttu-id="a6480-113">Microsoft Defender for Endpoint ha utilizzato `audit` il framework da linux per tenere traccia dell'attività di rete e di accesso.</span><span class="sxs-lookup"><span data-stu-id="a6480-113">Microsoft Defender for Endpoint utilized `audit` framework from linux to track network and login activity.</span></span>

1. <span data-ttu-id="a6480-114">Assicurati che il framework di controllo funzioni.</span><span class="sxs-lookup"><span data-stu-id="a6480-114">Make sure audit framework is working.</span></span>

    ```bash
    service auditd status
    ```

    <span data-ttu-id="a6480-115">output previsto:</span><span class="sxs-lookup"><span data-stu-id="a6480-115">expected output:</span></span>

    ```output
    ● auditd.service - Security Auditing Service
    Loaded: loaded (/usr/lib/systemd/system/auditd.service; enabled; vendor preset: enabled)
    Active: active (running) since Mon 2020-12-21 10:48:02 IST; 2 weeks 0 days ago
        Docs: man:auditd(8)
            https://github.com/linux-audit/audit-documentation
    Process: 16689 ExecStartPost=/sbin/augenrules --load (code=exited, status=1/FAILURE)
    Process: 16665 ExecStart=/sbin/auditd (code=exited, status=0/SUCCESS)
    Main PID: 16666 (auditd)
        Tasks: 25
    CGroup: /system.slice/auditd.service
            ├─16666 /sbin/auditd
            ├─16668 /sbin/audispd
            ├─16670 /usr/sbin/sedispatch
            └─16671 /opt/microsoft/mdatp/sbin/mdatp_audisp_plugin -d
    ```

2. <span data-ttu-id="a6480-116">Se `auditd` è contrassegnato come arrestato, avviarlo.</span><span class="sxs-lookup"><span data-stu-id="a6480-116">If `auditd` is marked as stopped, start it.</span></span>

    ```bash
    service auditd start
    ```

<span data-ttu-id="a6480-117">**Nei sistemi SLES,** il controllo SYSCALL in potrebbe essere disabilitato per impostazione predefinita e può essere utilizzato per `auditd` gli eventi mancanti.</span><span class="sxs-lookup"><span data-stu-id="a6480-117">**On SLES** systems, SYSCALL auditing in `auditd` might be disabled by default and can be accounted for missing events.</span></span>

1. <span data-ttu-id="a6480-118">Per verificare che il controllo SYSCALL non sia disabilitato, elencare le regole di controllo correnti:</span><span class="sxs-lookup"><span data-stu-id="a6480-118">To validate that SYSCALL auditing is not disabled, list the current audit rules:</span></span>

    ```bash
    sudo auditctl -l
    ```

    <span data-ttu-id="a6480-119">se è presente la riga seguente, rimuoverla o modificarla per consentire a Microsoft Defender for Endpoint di tenere traccia di SYSCALL specifici.</span><span class="sxs-lookup"><span data-stu-id="a6480-119">if the following line is present, remove it or edit it to enable Microsoft Defender for Endpoint to track specific SYSCALLs.</span></span>

    ```output
    -a task, never
    ```

    <span data-ttu-id="a6480-120">le regole di controllo si trovano in `/etc/audit/rules.d/audit.rules` .</span><span class="sxs-lookup"><span data-stu-id="a6480-120">audit rules are located at `/etc/audit/rules.d/audit.rules`.</span></span>

## <a name="missing-file-events"></a><span data-ttu-id="a6480-121">Eventi di file mancanti</span><span class="sxs-lookup"><span data-stu-id="a6480-121">Missing file events</span></span>

<span data-ttu-id="a6480-122">Gli eventi dei file vengono raccolti con `fanotify` il framework.</span><span class="sxs-lookup"><span data-stu-id="a6480-122">File events are collected with `fanotify` framework.</span></span> <span data-ttu-id="a6480-123">Nel caso in cui alcuni o tutti gli eventi di file non siano presenti, verificare che sia abilitato nel dispositivo e `fanotify` che il file system sia [supportato.](microsoft-defender-endpoint-linux.md#system-requirements)</span><span class="sxs-lookup"><span data-stu-id="a6480-123">In case some or all file events are missing, make sure `fanotify` is enabled on the device and that the file system is [supported](microsoft-defender-endpoint-linux.md#system-requirements).</span></span>

<span data-ttu-id="a6480-124">Elencare i filesystem nel computer con:</span><span class="sxs-lookup"><span data-stu-id="a6480-124">List the filesystems on the machine with:</span></span>

```bash
df -Th
```
