---
title: Gestire Windows Defender nell'azienda
description: Informazioni su come usare Criteri di gruppo, Configuration Manager, PowerShell, WMI, Intune e la riga di comando per gestire Microsoft Defender AV
keywords: Criteri di gruppo, gpo, config manager, sccm, scep, powershell, wmi, intune, defender, antivirus, antimalware, sicurezza, protezione
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 12/16/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 6b9845812763f9e3f1fdecf5566824eb76971dad
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764868"
---
# <a name="manage-microsoft-defender-antivirus-in-your-business"></a>Gestire Microsoft Defender Antivirus nell'azienda

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)

Puoi gestire e configurare Microsoft Defender Antivirus con gli strumenti seguenti:

- [Microsoft Intune](/mem/intune/protect/endpoint-security-antivirus-policy) (ora parte di Microsoft Endpoint Manager)
- [Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection-configure) (ora parte di Microsoft Endpoint Manager)
- [Criteri di gruppo](./use-group-policy-microsoft-defender-antivirus.md)
- [Cmdlet di PowerShell](./use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [Strumentazione gestione Windows (WMI)](./use-wmi-microsoft-defender-antivirus.md)
- Utilità da riga di comando di [Microsoft Malware Protection](./command-line-arguments-microsoft-defender-antivirus.md) (denominata utilità *mpcmdrun.exe* malware

Gli articoli seguenti forniscono ulteriori informazioni, collegamenti e risorse per l'uso di questi strumenti per gestire e configurare Microsoft Defender Antivirus.

| Articolo | Descrizione |
|:---|:---|
|[Gestire Microsoft Defender Antivirus con Microsoft Intune e Microsoft Endpoint Configuration Manager](use-intune-config-manager-microsoft-defender-antivirus.md)|Informazioni sull'uso di Intune e Configuration Manager per distribuire, gestire, segnalare e configurare Microsoft Defender Antivirus |
|[Gestire Microsoft Defender Antivirus con le impostazioni di Criteri di gruppo](use-group-policy-microsoft-defender-antivirus.md)|Elenco di tutte le impostazioni di Criteri di gruppo disponibili nei modelli ADMX |
|[Gestire Microsoft Defender Antivirus con i cmdlet di PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md)|Istruzioni per l'utilizzo dei cmdlet di PowerShell per gestire Microsoft Defender Antivirus, oltre a collegamenti alla documentazione per tutti i cmdlet e i parametri consentiti |
|[Gestire Microsoft Defender Antivirus con Strumentazione gestione Windows (WMI)](use-wmi-microsoft-defender-antivirus.md)| Istruzioni per l'utilizzo di WMI per gestire Microsoft Defender Antivirus, oltre a collegamenti alla documentazione per le API WMIv2 (incluse tutte le classi, i metodi e le proprietà) |
|[Gestire Microsoft Defender Antivirus con lo mpcmdrun.exe da riga di comando](command-line-arguments-microsoft-defender-antivirus.md)|Istruzioni sull'uso dello strumento da riga di comando dedicato per gestire e usare Microsoft Defender Antivirus |