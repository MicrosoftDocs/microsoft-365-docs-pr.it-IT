---
title: Come segnalare falsi positivi o falsi negativi dopo un'indagine automatizzata in Microsoft Defender per Office 365
description: È stato rilevato qualcosa di sbagliato o mancato da AIR in Microsoft Defender per Office 365? Informazioni su come inviare falsi positivi o falsi negativi a Microsoft per l'analisi.
keywords: automatizzato, indagine, avviso, trigger, azione, correzione, falso positivo, falso negativo
search.appverid: met150
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
ms.prod: m365-security
ms.date: 01/29/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.topic: how-to
ms.custom:
- autoir
ms.technology: mdo
ms.openlocfilehash: 287bd9cd4dda6ccb152e93908a409e036eab9cc7
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878881"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>Come segnalare falsi positivi/negativi nelle funzionalità di indagine e risposta automatizzate

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Microsoft Defender per Office 365 Piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Se le funzionalità di analisi e risposta [automatizzate (AIR) Office 365](automated-investigation-response-office.md) hanno perso o rilevato in modo errato qualcosa, il team delle operazioni di sicurezza può eseguire alcune operazioni per risolverlo. Tali azioni includono:

- [Segnalazione di un falso positivo/negativo a Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);
- [Regolazione degli avvisi](#adjust-an-alert-to-prevent-false-positives-from-recurring) (se necessario); e
- [Annullamento delle azioni di correzione eseguite](#undo-a-remediation-action).

Usa questo articolo come guida.

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>Segnalare un falso positivo/negativo a Microsoft per l'analisi

Se AIR in Microsoft Defender per Office 365 ha perso un messaggio di posta elettronica, un allegato di posta elettronica, un URL in un messaggio di posta elettronica o un URL in un file Office, è possibile inviare a Microsoft la posta indesiderata, il [phish,](admin-submission.md)gli URL e i file sospetti per l'analisi di Office 365 .

È inoltre possibile [inviare un file a Microsoft per l'analisi del malware.](https://www.microsoft.com/wdsi/filesubmission)

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>Modificare un avviso per evitare che i falsi positivi si ricorrenti

Se un avviso viene attivato da un uso legittimo o l'avviso non è accurato, è possibile gestire gli avvisi nel portale [di Cloud App Security.](/cloud-app-security/managing-alerts)

Se l'organizzazione usa [Microsoft Defender per Endpoint](/windows/security/threat-protection) oltre a Office 365 e un file, un indirizzo IP, un URL o un dominio viene considerato come malware in un dispositivo, anche se è sicuro, puoi creare un indicatore personalizzato con un'azione ["Consenti"](/windows/security/threat-protection/microsoft-defender-atp/manage-indicators)per il dispositivo.

## <a name="undo-a-remediation-action"></a>Annullare un'azione di correzione

Nella maggior parte dei casi, se è stata eseguita un'azione di correzione su un messaggio di posta elettronica, un allegato di posta elettronica o un URL e l'elemento non è in realtà una minaccia, il team delle operazioni di sicurezza può annullare l'azione di correzione e adottare misure per evitare che il falso positivo si ripeta. Puoi usare Esplora minacce [o](#undo-an-action-using-threat-explorer) la scheda [Azioni per un'indagine](#undo-an-action-in-the-action-center) per annullare un'azione.

> [!IMPORTANT]
> Assicurarsi di disporre delle autorizzazioni necessarie prima di tentare di eseguire le attività seguenti.

### <a name="undo-an-action-using-threat-explorer"></a>Annullare un'azione con Esplora minacce

Con Threat Explorer, il team delle operazioni di sicurezza può trovare un messaggio di posta elettronica interessato da un'azione e potenzialmente annullare l'azione.

<br>

****

|Scenario|Opzioni annulla|Altre informazioni|
|---|---|---|
|Un messaggio di posta elettronica è stato instradato alla cartella Posta indesiderata di un utente|<ul><li>Spostare il messaggio nella cartella Posta eliminata dell'utente</li><li>Spostare il messaggio nella cartella Posta in arrivo dell'utente</li><li>Eliminazione del messaggio</li></ul>|[Individuare e analizzare i messaggi di posta elettronica dannosi recapitati in Office 365](investigate-malicious-email-that-was-delivered.md)|
|Un messaggio di posta elettronica o un file è stato messo in quarantena|<ul><li>Rilasciare il messaggio di posta elettronica o il file</li><li> Eliminare il messaggio di posta elettronica o il file</li></ul>|[Gestire i messaggi in quarantena come amministratore](manage-quarantined-messages-and-files.md)|
|

### <a name="undo-an-action-in-the-action-center"></a>Annullare un'azione nel centro notifiche

Nel centro notifiche è possibile visualizzare le azioni di correzione eseguite e potenzialmente annullare l'azione.

1. Passare al portale Microsoft 365 Defender ( <https://security.microsoft.com> ).
2. Nel riquadro di spostamento selezionare **Centro notifiche.**
3. Selezionare la **scheda Cronologia** per visualizzare l'elenco delle azioni completate.
4. Selezionare un elemento. Verrà visualizzato il riquadro a comparsa.
5. Nel riquadro a comparsa selezionare **Annulla.** Solo le azioni che possono essere annullate avranno un **pulsante** Annulla.

## <a name="see-also"></a>Vedere anche

- [Microsoft Defender per Office 365](defender-for-office-365.md)
- [Indagini automatizzate in Microsoft Defender per Office 365](office-365-air.md)
