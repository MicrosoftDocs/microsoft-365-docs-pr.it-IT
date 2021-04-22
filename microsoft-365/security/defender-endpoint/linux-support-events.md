---
title: Risolvere i problemi relativi a eventi o avvisi mancanti per Microsoft Defender per Endpoint su Linux
description: Risolvere i problemi relativi a eventi o avvisi mancanti in Microsoft Defender per Endpoint su Linux.
keywords: microsoft, defender, Microsoft Defender for Endpoint, linux, eventi
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
ms.openlocfilehash: 7de216c1397a7cc4806af8221257eeedd2290830
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933314"
---
# <a name="troubleshoot-missing-events-or-alerts-issues-for-microsoft-defender-for-endpoint-on-linux"></a>Risolvere i problemi relativi a eventi o avvisi mancanti per Microsoft Defender per Endpoint su Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**

- [Microsoft Defender per Endpoint su Linux](microsoft-defender-endpoint-linux.md)

Questo articolo illustra alcuni passaggi generali per ridurre gli eventi o gli avvisi mancanti nel [portale del centro sicurezza.](https://securitycenter.windows.com/)

Dopo **che Microsoft Defender for Endpoint** è  stato installato correttamente in un dispositivo, verrà generata una pagina del dispositivo nel portale. Puoi esaminare tutti gli eventi registrati nella scheda sequenza temporale nella pagina del dispositivo o nella pagina di ricerca avanzata. In questa sezione viene descritto il caso in cui mancano alcuni o tutti gli eventi previsti.
Ad esempio, se mancano tutti gli eventi _CreatedFile._

## <a name="missing-network-and-login-events"></a>Eventi di rete e accesso mancanti

Microsoft Defender for Endpoint ha utilizzato `audit` il framework da linux per tenere traccia dell'attività di rete e di accesso.

1. Assicurati che il framework di controllo funzioni.

    ```bash
    service auditd status
    ```

    output previsto:

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

2. Se `auditd` è contrassegnato come arrestato, avviarlo.

    ```bash
    service auditd start
    ```

**Nei sistemi SLES,** il controllo SYSCALL in potrebbe essere disabilitato per impostazione predefinita e può essere utilizzato per `auditd` gli eventi mancanti.

1. Per verificare che il controllo SYSCALL non sia disabilitato, elencare le regole di controllo correnti:

    ```bash
    sudo auditctl -l
    ```

    se è presente la riga seguente, rimuoverla o modificarla per consentire a Microsoft Defender for Endpoint di tenere traccia di SYSCALL specifici.

    ```output
    -a task, never
    ```

    le regole di controllo si trovano in `/etc/audit/rules.d/audit.rules` .

## <a name="missing-file-events"></a>Eventi di file mancanti

Gli eventi dei file vengono raccolti con `fanotify` il framework. Nel caso in cui alcuni o tutti gli eventi di file non siano presenti, verificare che sia abilitato nel dispositivo e `fanotify` che il file system sia [supportato.](microsoft-defender-endpoint-linux.md#system-requirements)

Elencare i filesystem nel computer con:

```bash
df -Th
```
