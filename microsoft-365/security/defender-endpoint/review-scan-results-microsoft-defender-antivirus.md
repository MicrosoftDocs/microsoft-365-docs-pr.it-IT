---
title: Esaminare i risultati delle analisi di Microsoft Defender AV
description: Esaminare i risultati delle analisi tramite Microsoft Endpoint Configuration Manager, Microsoft Intune o l'app Sicurezza di Windows
keywords: risultati dell'analisi, correzione, analisi completa, analisi rapida
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/28/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 8fe2810ce18589d3131aa17f25ccfb01ec26b892
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690567"
---
# <a name="review-microsoft-defender-antivirus-scan-results"></a>Esaminare i risultati dell'analisi di Microsoft Defender Antivirus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)

Al termine di un'analisi di Microsoft [](run-scan-microsoft-defender-antivirus.md) Defender Antivirus, se si tratta di un'analisi su richiesta o pianificata, [](scheduled-catch-up-scans-microsoft-defender-antivirus.md)i risultati vengono registrati ed è possibile visualizzarli. 


## <a name="use-configuration-manager-to-review-scan-results"></a>Usare Configuration Manager per esaminare i risultati dell'analisi

Vedi [Come monitorare lo stato di Endpoint Protection.](/configmgr/protect/deploy-use/monitor-endpoint-protection)

## <a name="use-powershell-cmdlets-to-review-scan-results"></a>Utilizzare i cmdlet di PowerShell per esaminare i risultati dell'analisi

Il cmdlet seguente restituirà ogni rilevamento nell'endpoint. Se sono presenti più rilevamenti della stessa minaccia, ogni rilevamento verrà elencato separatamente, in base al momento di ogni rilevamento:

```PowerShell
Get-MpThreatDetection
```

![Screenshot of PowerShell cmdlets and outputs](images/defender/wdav-get-mpthreatdetection.png)

È possibile specificare `-ThreatID` di limitare l'output in modo da visualizzare solo i rilevamenti per una minaccia specifica.

Se si desidera elencare i rilevamenti delle minacce, ma combinare i rilevamenti della stessa minaccia in un singolo elemento, è possibile utilizzare il cmdlet seguente:

```PowerShell
Get-MpThreat
```

![screenshot di PowerShell](images/defender/wdav-get-mpthreat.png)

Per ulteriori informazioni su come usare PowerShell con Microsoft [Defender Antivirus,](use-powershell-cmdlets-microsoft-defender-antivirus.md) vedere Utilizzare i cmdlet di PowerShell per configurare ed eseguire i cmdlet di Microsoft Defender Antivirus e [Defender.](/powershell/module/defender/)

## <a name="use-windows-management-instruction-wmi-to-review-scan-results"></a>Usare Windows Management Instruction (WMI) per esaminare i risultati dell'analisi

Usa il [ **metodo Get** delle **classi MSFT_MpThreat** **e MSFT_MpThreatDetection.**](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="related-articles"></a>Articoli correlati

- [Personalizzare, avviare ed esaminare i risultati delle analisi e delle correzioni di Microsoft Defender Antivirus](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)