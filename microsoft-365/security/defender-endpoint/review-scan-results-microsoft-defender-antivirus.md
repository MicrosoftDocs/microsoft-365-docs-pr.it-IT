---
title: Esaminare i risultati delle analisi di Microsoft Defender AV
description: Esaminare i risultati delle analisi usando Microsoft Endpoint Configuration Manager, Microsoft Intune o l Sicurezza di Windows app
keywords: risultati dell'analisi, correzione, analisi completa, analisi rapida
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/28/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: ec3dd2edc09d504af0ed76b17577130b1cdce1b7
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275373"
---
# <a name="review-microsoft-defender-antivirus-scan-results"></a>Esaminare Antivirus Microsoft Defender risultati dell'analisi

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)

Al termine Antivirus Microsoft Defender'analisi, se si [](run-scan-microsoft-defender-antivirus.md) tratta di un'analisi su richiesta o pianificata, [](scheduled-catch-up-scans-microsoft-defender-antivirus.md)i risultati vengono registrati ed è possibile visualizzarli. 


## <a name="use-configuration-manager-to-review-scan-results"></a>Usare Configuration Manager per esaminare i risultati dell'analisi

Vedi [Come monitorare lo stato Endpoint Protection stato](/configmgr/protect/deploy-use/monitor-endpoint-protection).

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

Per ulteriori informazioni su come usare PowerShell con Antivirus Microsoft Defender, vedere Use [PowerShell cmdlets to configure](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Antivirus Microsoft Defender run Antivirus Microsoft Defender and [Defender cmdlets.](/powershell/module/defender/)

## <a name="use-windows-management-instruction-wmi-to-review-scan-results"></a>Utilizzare Windows Management Instruction (WMI) per esaminare i risultati dell'analisi

Usa il [ **metodo Get** delle **classi MSFT_MpThreat** **e MSFT_MpThreatDetection.**](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="related-articles"></a>Articoli correlati

- [Personalizzare, avviare ed esaminare i risultati di Antivirus Microsoft Defender analisi e correzione](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Antivirus Microsoft Defender in Windows 10](microsoft-defender-antivirus-in-windows-10.md)