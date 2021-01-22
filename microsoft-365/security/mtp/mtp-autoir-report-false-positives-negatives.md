---
title: Gestire falsi positivi o falsi negativi in AIR in Microsoft 365 Defender
description: Qualcosa non è stato rilevato o rilevato in modo errato da AIR in Microsoft 365 Defender? Informazioni su come inviare falsi positivi o falsi negativi a Microsoft per l'analisi.
keywords: automatizzato, indagine, avviso, trigger, azione, correzione, falso positivo, falso negativo
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.date: 09/16/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: dbef240e28258d1ac4000c05538d0ce073a9d910
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930355"
---
# <a name="handle-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>Gestire falsi positivi/negativi nelle funzionalità di analisi e risposta automatizzate

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

Le [funzionalità di analisi e risposta automatizzate](mtp-autoir.md) in Microsoft 365 Defender hanno mancato o rilevato in modo errato qualcosa? Per risolvere il problema, è possibile eseguire alcune operazioni. È possibile:

- [Segnalare un falso positivo/negativo a Microsoft;](#report-a-false-positivenegative-to-microsoft-for-analysis)

- [Modificare gli avvisi](#adjust-an-alert-to-prevent-false-positives-from-recurring) (se necessario); e 

- [Annullare le azioni di correzione eseguite nei dispositivi.](#undo-a-remediation-action-that-was-taken-on-a-device) 

Usa questo articolo come guida. 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>Segnalare un falso positivo/negativo a Microsoft per l'analisi

|Elemento perso o rilevato in modo errato |Servizio  |Soluzione  |
|---------|---------|---------|
|- Messaggio di posta elettronica <br/>- Allegato di posta elettronica <br/>- URL in un messaggio di posta elettronica<br/>- URL in un file di Office      |[Microsoft Defender per Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)        |[Inviare posta indesiderata, phish, URL e file sospetti a Microsoft per l'analisi](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)         |
|File o app in un dispositivo    |[Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection)         |[Inviare un file a Microsoft per l'analisi del malware](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>Modificare un avviso per impedire la ricorrente di falsi positivi

|Scenario |Servizio |Soluzione |
|--------|--------|--------|
|- Un avviso viene attivato da un uso legittimo <br/>- Un avviso non è accurato    |[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)<br/> o <br/>[Rilevamento avanzato delle minacce di Azure](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)         |[Gestire gli avvisi nel portale di Cloud App Security](https://docs.microsoft.com/cloud-app-security/managing-alerts)         |
|Un file, un indirizzo IP, un URL o un dominio viene considerato come malware in un dispositivo, anche se è sicuro|[Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection) |[Creare un indicatore personalizzato con un'azione "Consenti"](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |


## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a>Annullare un'azione di correzione eseguita in un dispositivo

Se è stata eseguita un'azione di correzione in un dispositivo (ad esempio un dispositivo Windows 10) e l'elemento non è una minaccia, il team delle operazioni di sicurezza può annullare l'azione di correzione nel centro [notifiche.](mtp-action-center.md)

> [!IMPORTANT]
> Assicurarsi di disporre delle [autorizzazioni necessarie prima](mtp-action-center.md#required-permissions-for-action-center-tasks) di tentare di eseguire l'attività seguente.

1. Andare su [https://security.microsoft.com](https://security.microsoft.com) ed eseguire l'accesso. 

2. Nel riquadro di spostamento, scegliere **Centro notifiche**. 

3. Nella scheda **Cronologia** selezionare un'azione che si desidera annullare. Verrà aperto un riquadro a comparsa.<br/>
    > [!TIP]
    > Utilizzare i filtri per restringere l'elenco dei risultati. 

4. Nel riquadro a comparsa per l'elemento selezionato selezionare Apri **pagina di analisi.**

5. Nella visualizzazione dei dettagli dell'indagine selezionare la **scheda** Azioni.

6. Selezionare un elemento con stato **Completato** e cercare un collegamento, ad esempio **Approvato,** nella **colonna Decisioni.** Verrà aperto un riquadro a comparsa con altri dettagli sull'azione.

7. Per annullare l'azione, selezionare **Elimina correzione.**

## <a name="see-also"></a>Vedere anche

- [Visualizzare i dettagli e i risultati di un'indagine automatizzata](mtp-autoir-results.md)
- [Ricerca proattiva delle minacce con ricerca avanzata in Microsoft 365 Defender](advanced-hunting-overview.md)
