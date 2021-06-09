---
title: Risolvere i falsi positivi o i falsi negativi in Microsoft 365 Defender
description: Qualcosa non è stato rilevato o rilevato in modo errato da AIR in Microsoft 365 Defender? Informazioni su come inviare falsi positivi o falsi negativi a Microsoft per l'analisi.
keywords: automatizzato, indagine, avviso, correzione, falso positivo, falso negativo
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: how-to
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: 3cffa97d26b2b28de8d9e45d7030e0931a7ba072
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2021
ms.locfileid: "52269579"
---
# <a name="address-false-positives-or-false-negatives-in-microsoft-365-defender"></a>Risolvere i falsi positivi o i falsi negativi in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Si applica a:**
- Microsoft 365 Defender

Talvolta possono verificarsi falsi positivi o negativi con qualsiasi soluzione di protezione dalle minacce. Se [le funzionalità di analisi e risposta](m365d-autoir.md) automatizzate in Microsoft 365 Defender hanno perso o rilevato qualcosa in modo errato, il team delle operazioni di sicurezza può eseguire le operazioni seguenti:

- [Segnalare un falso positivo/negativo a Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis)
- [Modificare gli avvisi](#adjust-an-alert-to-prevent-false-positives-from-recurring) (se necessario)
- [Annullare le azioni di correzione eseguite nei dispositivi](#undo-a-remediation-action-that-was-taken-on-a-device)

Nelle sezioni seguenti viene descritto come eseguire queste attività.

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>Segnalare un falso positivo/negativo a Microsoft per l'analisi

|Elemento perso o rilevato in modo errato |Servizio  |Soluzione  |
|---------|---------|---------|
|- Messaggio di posta elettronica <br/>- Allegato di posta elettronica <br/>- URL in un messaggio di posta elettronica<br/>- URL in un Office file      |[Microsoft Defender per Office 365](/microsoft-365/security/office-365-security/defender-for-office-365)        |[Inviare posta indesiderata sospetta, phish, URL e file a Microsoft per l'analisi](../office-365-security/admin-submission.md)         |
|File o app in un dispositivo    |[Microsoft Defender per endpoint](/windows/security/threat-protection)         |[Inviare un file a Microsoft per l'analisi del malware](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>Modificare un avviso per evitare che i falsi positivi si ricorrenti

|Scenario |Servizio |Soluzione |
|--------|--------|--------|
|- Un avviso viene attivato da un uso legittimo <br/>- Un avviso non è accurato    |[Microsoft Cloud App Security](/cloud-app-security)<br/> oppure <br/>[Azure Threat Protection](/azure/security/fundamentals/threat-detection)         |[Gestire gli avvisi nel Cloud App Security portale](/cloud-app-security/managing-alerts)         |
|Un file, un indirizzo IP, un URL o un dominio viene considerato come malware in un dispositivo, anche se è sicuro|[Microsoft Defender per endpoint](/windows/security/threat-protection) |[Creare un indicatore personalizzato con un'azione "Consenti"](/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |

## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a>Annullare un'azione di correzione eseguita in un dispositivo

Se è stata eseguita un'azione di correzione su un'entità (ad esempio un dispositivo o un messaggio di posta elettronica) e l'entità interessata non è effettivamente una minaccia, il team delle operazioni di sicurezza può annullare l'azione di correzione nel centro [notifiche.](m365d-action-center.md)

1. Andare su [https://security.microsoft.com](https://security.microsoft.com) ed eseguire l'accesso. 
2. Nel riquadro di spostamento, scegliere **Centro notifiche**. 
3. Nella scheda **Cronologia** selezionare un'azione che si desidera annullare. Verrà visualizzato il riquadro a comparsa.
4. Nel riquadro a comparsa selezionare **Annulla.**

> [!TIP]
> Vedi [Annullare le azioni completate.](m365d-autoir-actions.md#undo-completed-actions)

## <a name="see-also"></a>Vedere anche

- [Visualizzare i dettagli e i risultati di un'indagine automatizzata](m365d-autoir-results.md)
- [Ricerca proattiva di minacce con ricerca avanzata in Microsoft 365 Defender](advanced-hunting-overview.md)
- [Indirizzare i falsi positivi/negativi in Microsoft Defender per Endpoint](/windows/security/threat-protection/microsoft-defender-atp/defender-endpoint-false-positives-negatives)