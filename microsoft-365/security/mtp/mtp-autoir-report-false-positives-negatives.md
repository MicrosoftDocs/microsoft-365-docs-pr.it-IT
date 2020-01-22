---
title: Come segnalare falsi positivi o falsi negativi in aria in Microsoft Threat Protection
description: Si è verificato un errore o rilevato erroneamente da AIR in Microsoft Threat Protection? Informazioni su come inviare falsi positivi o falsi negativi a Microsoft per l'analisi.
keywords: automatizzato, indagine, avviso, trigger, azione, correzione, falso positivo, falso negativo
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: d62f10cdf9805cdcfae7ba5bd5381ca589d1297c
ms.sourcegitcommit: 3dca80f268006658a0b721aa4f6df1224c7964dc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2020
ms.locfileid: "41260194"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>Come segnalare falsi positivi/negativi nelle funzionalità di analisi e risposta automatizzate

**Si applica a:**
- Microsoft Threat Protection

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

[Le funzionalità di ricerca e risposta automatizzate](mtp-autoir.md) in Microsoft Threat Protection non hanno o rilevato erroneamente qualcosa? È possibile segnalarlo a Microsoft o regolare gli avvisi (se necessario). Utilizzare la tabella seguente come guida: 


|Elemento  |Rilevato da  |Come segnalarlo  |
|---------|---------|---------|
|Messaggio di posta elettronica <br/>Allegato di posta elettronica <br/>URL in un messaggio di posta elettronica o in un file di Office      |[Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)        |[Inviare messaggi di posta indesiderata sospetti, phishing, URL e file a Microsoft per l'analisi di Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)         |
|File o app in un dispositivo    |[Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection)         |[Inviare un file a Microsoft per l'analisi antimalware](https://www.microsoft.com/wdsi/filesubmission)         |
|Avviso attivato da un utilizzo legittimo <br/>Avviso inesatto    |[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)<br/> oppure <br/>[Rilevamento delle minacce avanzato di Azure](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)         |[Gestire gli avvisi nel cloud app Security Portal](https://docs.microsoft.com/cloud-app-security/managing-alerts)         |


## <a name="next-steps"></a>Passaggi successivi

- [Approvare o rifiutare le azioni relative all'indagine e reazione automatizzate](mtp-autoir-actions.md)
- [Altre informazioni sul centro notifiche](mtp-action-center.md)
- [Cercare in modo proattivo minacce con la ricerca avanzata di Microsoft Threat Protection](advanced-hunting-overview.md)
