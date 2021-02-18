---
title: Come segnalare falsi positivi o falsi negativi dopo un'indagine automatizzata in Microsoft Defender per Office 365
description: Qualcosa non è stato rilevato o rilevato in modo errato da AIR in Microsoft Defender per Office 365? Informazioni su come inviare falsi positivi o falsi negativi a Microsoft per l'analisi.
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
ms.date: 01/29/2021
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.topic: how-to
ms.custom:
- autoir
ms.technology: mdo
ms.openlocfilehash: 48d7e1a7497f9bc2a07a84b36fb07939d25609bf
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289150"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>Come segnalare falsi positivi/negativi nelle funzionalità di analisi e risposta automatizzate

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Microsoft Defender per Office 365 Piano 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Se le funzionalità di analisi e risposta [automatizzate (AIR) in Office 365](automated-investigation-response-office.md) non sono state rilevate o rilevate in modo errato, il team delle operazioni di sicurezza può eseguire alcune operazioni per risolverlo. Tali azioni includono:

- [Segnalazione di un falso positivo/negativo a Microsoft;](#report-a-false-positivenegative-to-microsoft-for-analysis)
- [Modifica degli avvisi](#adjust-an-alert-to-prevent-false-positives-from-recurring) (se necessario); e
- [Annullamento delle azioni di correzione eseguite.](#undo-a-remediation-action)

Usa questo articolo come guida.

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>Segnalare un falso positivo/negativo a Microsoft per l'analisi

Se AIR in Microsoft Defender per Office 365 ha perso un messaggio di posta elettronica, un allegato di posta elettronica, un URL in un messaggio di posta elettronica o un URL in un file di Office, è possibile inviare posta indesiderata, phish, URL e file sospetti a Microsoft per l'analisi [di Office 365.](admin-submission.md)

È anche possibile [inviare un file a Microsoft per l'analisi del malware.](https://www.microsoft.com/wdsi/filesubmission)

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>Modificare un avviso per evitare che i falsi positivi si ricorrentino

Se un avviso viene attivato da un uso legittimo o non è accurato, puoi gestire gli avvisi nel portale [di Cloud App Security.](https://docs.microsoft.com/cloud-app-security/managing-alerts)

Se l'organizzazione usa [Microsoft Defender per Endpoint](https://docs.microsoft.com/windows/security/threat-protection) oltre a Office 365 e un file, un indirizzo IP, un URL o un dominio viene considerato come malware in un dispositivo, anche se è sicuro, è possibile creare un indicatore personalizzato con un'azione ["Consenti"](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators)per il dispositivo.

## <a name="undo-a-remediation-action"></a>Annullare un'azione correttiva

Nella maggior parte dei casi, se è stata eseguita un'azione di correzione su un messaggio di posta elettronica, un allegato di posta elettronica o un URL e l'elemento non è una minaccia, il team delle operazioni di sicurezza può annullare l'azione di correzione ed eseguire le operazioni necessarie per evitare che il falso positivo si ripeta. Puoi usare Esplora [minacce](#undo-an-action-using-threat-explorer) o la scheda Azioni per [un'indagine per](#undo-an-action-in-the-action-center) annullare un'azione.

> [!IMPORTANT]
> Assicurarsi di disporre delle autorizzazioni necessarie prima di tentare di eseguire le attività seguenti.

### <a name="undo-an-action-using-threat-explorer"></a>Annullare un'azione con Esplora minacce

Con Esplora minacce, il team delle operazioni di sicurezza può trovare un messaggio di posta elettronica interessato da un'azione e potenzialmente annullare l'azione.

|Scenario|Opzioni di annullamento|Ulteriori informazioni|
|---|---|---|
|Un messaggio di posta elettronica è stato instradato alla cartella Posta indesiderata di un utente|- Spostare il messaggio nella cartella Posta eliminata dell'utente<br/>- Spostare il messaggio nella cartella Posta in arrivo dell'utente<br/>- Eliminare il messaggio|[Trovare e analizzare i messaggi di posta elettronica dannosi recapitati in Office 365](investigate-malicious-email-that-was-delivered.md)|
|Un messaggio di posta elettronica o un file è stato messo in quarantena|- Rilasciare il messaggio di posta elettronica o il file<br/>- Eliminare il messaggio di posta elettronica o il file|[Gestire i messaggi in quarantena come amministratore](manage-quarantined-messages-and-files.md)|
|

### <a name="undo-an-action-in-the-action-center"></a>Annullare un'azione nel centro notifiche

Nel centro notifiche è possibile visualizzare le azioni di correzione eseguite e potenzialmente annullare l'azione.

1. Passare al Centro sicurezza Microsoft 365 ( [https://security.microsoft.com](https://security.microsoft.com) ).
2. Nel riquadro di spostamento selezionare **Centro notifiche.** 
3. Selezionare la **scheda Cronologia** per visualizzare l'elenco delle azioni completate.
4. Selezionare un elemento. Viene visualizzato il riquadro a comparsa. 
5. Nel riquadro a comparsa selezionare **Annulla.** Solo le azioni che possono essere annullate avranno un **pulsante** Annulla.

## <a name="see-also"></a>Vedere anche

- [Microsoft Defender per Office 365](office-365-atp.md)
- [Indagini automatizzate in Microsoft Defender per Office 365](office-365-air.md)
