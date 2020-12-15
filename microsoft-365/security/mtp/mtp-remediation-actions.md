---
title: Azioni di correzione in Microsoft 365 Defender
description: Ottenere una panoramica delle azioni correttive che seguono le indagini automatizzate in Microsoft 365 Defender
keywords: automatizzata, indagine, avviso, attivare, azione, correzione
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.date: 12/09/2020
ms.reviewer: evaldm, isco
ms.openlocfilehash: 9e489e3b0100aa138b11d4bfb4ccc8048a2113f4
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/15/2020
ms.locfileid: "49683296"
---
# <a name="remediation-actions-in-microsoft-365-defender"></a>Azioni di correzione in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

## <a name="remediation-actions"></a>Azioni correttive

Durante e dopo un'indagine automatizzata in Microsoft 365 Defender, le azioni di correzione vengono identificate per gli elementi dannosi o sospetti. Alcuni tipi di azioni di correzione vengono eseguiti nei dispositivi, detti anche endpoint. Altre azioni di correzione vengono eseguite sul contenuto della posta elettronica. Indagini automatizzate complete dopo che sono state apportate, approvate o rifiutate le azioni di correzione.

> [!IMPORTANT]
> Se le azioni di correzione vengono eseguite automaticamente o solo dopo l'approvazione dipendono da determinate impostazioni, ad esempio i livelli di automazione. Per ulteriori informazioni, vedere gli articoli seguenti:
> - [Configurare le funzionalità di analisi e risposta automatizzate in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md)
> - [Come vengono risolte le minacce nei dispositivi](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
> - [Minacce e azioni correttive per la posta elettronica & contenuto di collaborazione](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-remediation-actions#threats-and-remediation-actions)

Nella tabella seguente sono riepilogate le azioni di correzione attualmente supportate in Microsoft 365 Defender: 

|Azioni di correzione del dispositivo (endpoint)  |Azioni correttive della posta elettronica  |
|---------|---------|
|-Raccogliere il pacchetto di indagine <br/>-Isolate Device (questa azione può essere annullata)<br/>-Trasferisce Machine <br/>-Esecuzione del codice di rilascio <br/>-Rilascio dalla quarantena <br/>-Esempio di richiesta <br/>-Limitare l'esecuzione del codice (questa azione può essere annullata) <br/>-Eseguire l'analisi antivirus <br/>-Arrestare e mettere in quarantena      |-Blocca URL (tempo di clic)<br/>-Eliminare i messaggi di posta elettronica o i cluster<br/>-Posta in quarantena<br/>-Mettere in quarantena un allegato di posta elettronica<br/>-Disattivare l'inoltro della posta esterna          |

Le azioni di correzione, sia che si tratti di approvazione in sospeso o che sono già state completate, possono essere visualizzate nel [Centro azioni](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).

## <a name="remediation-actions-that-follow-automated-investigations"></a>Azioni di correzione che seguono indagini automatizzate

Al termine di un'indagine automatizzata, viene raggiunto un verdetto per ogni elemento di prova coinvolto. A seconda del verdetto, vengono identificate le azioni di correzione. In alcuni casi, le azioni correttive vengono eseguite automaticamente; in altri casi, invece, è necessario approvarle. Tutto dipende da come [viene configurata l'analisi e la risposta automatizzata](mtp-configure-auto-investigation-response.md).

Nella tabella seguente sono elencati i possibili verdetti e i risultati:

| Verdetto    | Area    | Risultati|
|------|------|------|
| Dannosa    | Dispositivi (endpoint)    | Le azioni di correzione vengono eseguite automaticamente (presupponendo che i [gruppi di dispositivi](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) dell'organizzazione siano impostati automaticamente su **minacce complete**)|
| Dannosa    | Contenuto della posta elettronica (URL o allegati) | Le azioni correttive consigliate sono in attesa di approvazione|
| Sospetta    | Dispositivi o contenuto della posta elettronica | Le azioni correttive consigliate sono in attesa di approvazione|
| Non sono state trovate minacce    | Dispositivi o contenuto della posta elettronica    | Non sono necessarie azioni correttive|


## <a name="remediation-actions-that-are-taken-manually"></a>Azioni di correzione eseguite manualmente

Oltre alle azioni correttive che seguono le indagini automatizzate, il team delle operazioni di sicurezza può eseguire manualmente determinate operazioni di correzione. Di seguito sono riportate le azioni seguenti:

- Azione manuale del dispositivo, ad esempio isolamento del dispositivo o quarantena dei file.
- Azione manuale del messaggio di posta elettronica, ad esempio l'eliminazione di messaggi di posta elettronica. 
- Azione di [ricerca avanzata](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) su dispositivi o posta elettronica.
- Azione [Esplora](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer) sul contenuto della posta elettronica, ad esempio lo spostamento di posta elettronica in posta indesiderata, l'eliminazione di messaggi di posta elettronica o l'eliminazione definitiva.
- Azione manuale di [risposta in tempo reale](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) , ad esempio l'eliminazione di un file, l'interruzione di un processo e la rimozione di un'attività pianificata.
- Azione Live Response con [Microsoft Defender per le API endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/management-apis#microsoft-defender-for-endpoint-apis), ad esempio isolando un dispositivo, eseguendo un'analisi antivirus e ottenendo informazioni su un file. 

## <a name="next-steps"></a>Passaggi successivi

- [Visita il Centro notifiche](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
- [Approvare o rifiutare azioni in sospeso](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)
- [Gestire i falsi positivi/negativi nelle funzionalità di analisi e risposta automatizzate](mtp-autoir-report-false-positives-negatives.md)
