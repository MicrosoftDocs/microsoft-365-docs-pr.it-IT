---
title: Monitorare e creare report sulla Antivirus Microsoft Defender protezione
description: Usa Configuration Manager o gli strumenti siem (Security Information and Event Management) per usare i report e monitorare Microsoft Defender AV con PowerShell e WMI.
keywords: siem, monitor, report, Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 12/07/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 5780daaa65a4d83376dd7977e03e88e2d828befc
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2021
ms.locfileid: "52269589"
---
# <a name="report-on-microsoft-defender-antivirus"></a>Creare report in Microsoft Defender Antivirus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)

Antivirus Microsoft Defender è incorporato in Windows 10, Windows Server 2019 e Windows Server 2016. Antivirus Microsoft Defender è della protezione di nuova generazione in Microsoft Defender per Endpoint. La protezione di nuova generazione consente di proteggere i dispositivi da minacce software come virus, malware e spyware nella posta elettronica, nelle app, nel cloud e nel Web.

Con Antivirus Microsoft Defender, sono disponibili diverse opzioni per esaminare lo stato di protezione e gli avvisi. È possibile utilizzare la Microsoft Endpoint Manager [per monitorare Antivirus Microsoft Defender](/configmgr/protect/deploy-use/monitor-endpoint-protection) o creare avvisi di posta [elettronica.](/configmgr/protect/deploy-use/endpoint-configure-alerts) In caso contrario, è possibile monitorare la [protezione Microsoft Intune](/intune/introduction-intune).  

Microsoft Operations Management Suite include un componente aggiuntivo [Conformità](/windows/deployment/update/update-compliance-get-started) aggiornamenti che segnala i problemi Antivirus Microsoft Defender, inclusi gli aggiornamenti della protezione e le impostazioni di protezione in tempo reale.

Se si dispone di un server SIEM (Security Information and Event Management) di terze parti, è anche possibile utilizzare Windows Defender [eventi client.](/windows/win32/events/windows-events) 

Windows eventi includono diverse origini eventi di sicurezza, tra cui gli eventi di Gestione [](/windows/device-security/auditing/security-auditing-overview) account di sicurezza (SAM) ( ottimizzati per[Windows 10](/windows/whats-new/whats-new-windows-10-version-1507-and-1511), vedere anche l'argomento Controllo della sicurezza) e gli eventi [Windows Defender sicurezza](troubleshoot-microsoft-defender-antivirus.md). 

Questi eventi possono essere aggregati centralmente tramite [l'Windows di eventi.](/windows/win32/wec/windows-event-collector) Spesso, i server SIEM dispongono di connettori per Windows eventi, consentendo di correlare tutti gli eventi di sicurezza nel server SIEM. 

Puoi anche monitorare [gli eventi di malware usando la soluzione di valutazione malware in Log Analytics.](/azure/log-analytics/log-analytics-malware)

Per il monitoraggio o la determinazione dello stato con PowerShell, WMI o Microsoft Azure, vedere [la tabella delle opzioni di distribuzione,](deploy-manage-report-microsoft-defender-antivirus.md#ref2)gestione e creazione di report.

## <a name="related-articles"></a>Articoli correlati

- [Antivirus Microsoft Defender in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Antivirus Microsoft Defender in Windows Server 2016 e 2019](microsoft-defender-antivirus-on-windows-server.md)
- [Distribuire Antivirus Microsoft Defender](deploy-manage-report-microsoft-defender-antivirus.md)