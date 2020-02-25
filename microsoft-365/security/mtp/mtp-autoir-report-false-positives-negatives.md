---
title: Gestire falsi positivi o falsi negativi in aria in Microsoft Threat Protection
description: Si è verificato un errore o rilevato erroneamente da AIR in Microsoft Threat Protection? Informazioni su come inviare falsi positivi o falsi negativi a Microsoft per l'analisi.
keywords: automatizzato, indagine, avviso, trigger, azione, correzione, falso positivo, falso negativo
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.date: 01/29/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 2f3808f599caa4ed347fc182005397c14b9f51b2
ms.sourcegitcommit: 133bf7936e5ef1a4d06998429d0d01096bda929f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/24/2020
ms.locfileid: "42262003"
---
# <a name="handle-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>Gestire i falsi positivi/negativi nelle funzionalità di analisi e risposta automatizzate

**Si applica a:**
- Microsoft Threat Protection

[Le funzionalità di ricerca e risposta automatizzate](mtp-autoir.md) in Microsoft Threat Protection non hanno o rilevato erroneamente qualcosa? Per risolvere il problema, è possibile eseguire la procedura. È possibile:

- [Segnala un falso positivo/negativo a Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);

- [Modificare gli avvisi](#adjust-an-alert-to-prevent-false-positives-from-recurring) (se necessario); e 

- [Annullare le azioni di correzione eseguite nei dispositivi](#undo-a-remediation-action-that-was-taken-on-a-device). 

Utilizzare questo articolo come guida. 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>Segnalare un falso positivo/negativo a Microsoft per l'analisi

|Elemento mancante o rilevato erroneamente |Servizio  |Procedura  |
|---------|---------|---------|
|-Messaggio di posta elettronica <br/>-Allegato di posta elettronica <br/>-URL in un messaggio di posta elettronica<br/>-URL in un file di Office      |[Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)        |[Inviare messaggi di posta indesiderata sospetti, phishing, URL e file a Microsoft per l'analisi di Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)         |
|File o app in un dispositivo    |[Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection)         |[Inviare un file a Microsoft per l'analisi antimalware](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>Modificare un avviso per evitare che i falsi positivi vengano ricorrenti

|Scenario |Servizio |Procedura |
|--------|--------|--------|
|-Un avviso viene attivato da un utilizzo legittimo <br/>-Un avviso non è accurato    |[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)<br/> oppure <br/>[Rilevamento delle minacce avanzato di Azure](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)         |[Gestire gli avvisi nel cloud app Security Portal](https://docs.microsoft.com/cloud-app-security/managing-alerts)         |
|Un file, un indirizzo IP, un URL o un dominio viene considerato come malware su un dispositivo, anche se è sicuro|[Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection) |[Creare un indicatore personalizzato con un'azione "Consenti"](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |


## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a>Annullare un'azione di correzione eseguita su un dispositivo

Se è stata eseguita un'azione di correzione su un dispositivo, ad esempio un dispositivo Windows 10, e l'elemento è effettivamente pulito, il team delle operazioni di sicurezza può annullare l'azione di correzione nell' [Action Center](mtp-action-center.md).

> [!IMPORTANT]
> Verificare di disporre delle [autorizzazioni necessarie](mtp-action-center.md#required-permissions-for-action-center-tasks) prima di tentare di eseguire l'attività seguente.

1. Andare su [https://security.microsoft.com](https://security.microsoft.com) ed eseguire l'accesso. 

2. Nel riquadro di spostamento, scegliere **Centro notifiche**. 

3. Nella scheda **cronologia** selezionare un'azione che si desidera annullare. Verrà aperto un riquadro a comparsa.<br/>
    > [!TIP]
    > Utilizzare i filtri per limitare l'elenco dei risultati. 

4. Nel riquadro a comparsa per l'elemento selezionato, selezionare **Apri pagina di analisi**.

5. Nella visualizzazione dettagli analisi selezionare la scheda **azioni** .

6. Selezionare un elemento con stato **completato**e cercare un collegamento, ad esempio **approvato**, nella colonna **decisioni** . Verrà aperto un riquadro a comparsa con maggiori dettagli sull'azione.

7. Per annullare l'azione, selezionare **Elimina correzione**.

## <a name="related-articles"></a>Articoli correlati

- [Approvare o rifiutare le azioni relative all'indagine e reazione automatizzate](mtp-autoir-actions.md)

- [Altre informazioni sul centro notifiche](mtp-action-center.md)

- [Cercare in modo proattivo minacce con la ricerca avanzata di Microsoft Threat Protection](advanced-hunting-overview.md)
