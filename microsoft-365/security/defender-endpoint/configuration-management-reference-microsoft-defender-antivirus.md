---
title: Gestire Windows Defender nell'azienda
description: Informazioni su come usare Criteri di gruppo, Configuration Manager, PowerShell, WMI, Intune e la riga di comando per gestire Microsoft Defender AV
keywords: Criteri di gruppo, gpo, config manager, sccm, scep, powershell, wmi, intune, defender, antivirus, antimalware, sicurezza, protezione
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 07/13/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: f9ecade23964db88076347b3a89085b25c1b1538
ms.sourcegitcommit: 4046c2c390851dffcdb430e1ba38c4df23fe2e69
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/13/2021
ms.locfileid: "53415564"
---
# <a name="manage-microsoft-defender-antivirus-in-your-business"></a>Gestire Antivirus Microsoft Defender nell'azienda

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)
- [Antivirus Microsoft Defender](/microsoft-365/security/defender-endpoint/microsoft-defender-antivirus-windows)

È possibile gestire e configurare Antivirus Microsoft Defender con gli strumenti seguenti:

- [Microsoft Intune](/mem/intune/protect/endpoint-security-antivirus-policy) (ora parte di Microsoft Endpoint Manager)
- [Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection-configure) (ora parte di Microsoft Endpoint Manager)
- [Criteri di gruppo](./use-group-policy-microsoft-defender-antivirus.md)
- [Cmdlet di PowerShell](./use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [Strumentazione gestione Windows (WMI)](./use-wmi-microsoft-defender-antivirus.md)
- Utilità da riga di comando di [Microsoft Malware Protection](./command-line-arguments-microsoft-defender-antivirus.md) (denominata utilità *mpcmdrun.exe* malware

Gli articoli seguenti forniscono ulteriori informazioni, collegamenti e risorse per l'utilizzo di questi strumenti per gestire e configurare Antivirus Microsoft Defender.

| Articolo | Descrizione |
|:---|:---|
|[Gestire Antivirus Microsoft Defender con Microsoft Intune e Microsoft Endpoint Configuration Manager](use-intune-config-manager-microsoft-defender-antivirus.md)|Informazioni sull'uso di Intune e Configuration Manager per distribuire, gestire, creare report e configurare Antivirus Microsoft Defender |
|[Gestire Antivirus Microsoft Defender con le impostazioni di Criteri di gruppo](use-group-policy-microsoft-defender-antivirus.md)|Elenco di tutte le impostazioni di Criteri di gruppo disponibili nei modelli ADMX |
|[Gestire Antivirus Microsoft Defender con i cmdlet di PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md)|Istruzioni per l'utilizzo dei cmdlet di PowerShell per gestire Antivirus Microsoft Defender, oltre a collegamenti alla documentazione per tutti i cmdlet e i parametri consentiti |
|[Gestire Antivirus Microsoft Defender con Windows Management Instrumentation (WMI)](use-wmi-microsoft-defender-antivirus.md)| Istruzioni per l'utilizzo di WMI per gestire Antivirus Microsoft Defender, oltre a collegamenti alla documentazione per le API WMIv2 (incluse tutte le classi, i metodi e le proprietà) |
|[Gestire Antivirus Microsoft Defender con lo MpCmdRun.exe da riga di comando](command-line-arguments-microsoft-defender-antivirus.md)| Istruzioni sull'utilizzo dello strumento da riga di comando dedicato per gestire e usare Antivirus Microsoft Defender |
