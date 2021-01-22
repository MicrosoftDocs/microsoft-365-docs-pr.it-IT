---
title: Azioni correttive in Microsoft 365 Defender
description: Panoramica delle azioni correttive che seguono le indagini automatizzate in Microsoft 365 Defender
keywords: automatizzata, indagine, avviso, attivare, azione, correzione
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: c6b0275335f32419b470c789d83b069be7839c36
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932851"
---
# <a name="remediation-actions-in-microsoft-365-defender"></a>Azioni correttive in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

## <a name="remediation-actions"></a>Azioni correttive

Durante e dopo un'indagine automatizzata in Microsoft 365 Defender, le azioni di correzione vengono identificate per elementi dannosi o sospetti. Alcuni tipi di azioni correttive vengono intraprese nei dispositivi, denominati anche endpoint. Vengono eseguite altre azioni di correzione sul contenuto della posta elettronica. Le indagini automatizzate vengono completate dopo l'esecuzione, l'approvazione o il rifiuto delle azioni correttive.

> [!IMPORTANT]
> Se le azioni di correzione vengono eseguite automaticamente o solo dopo l'approvazione dipende da determinate impostazioni, ad esempio il modo in cui i livelli di automazione. Per ulteriori informazioni, vedere gli articoli seguenti:
> - [Configurare le funzionalità di analisi e risposta automatizzate in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md)
> - [Modalità di correzione delle minacce nei dispositivi](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
> - [Minacce e azioni di correzione sui contenuti di collaborazione & posta elettronica](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-remediation-actions#threats-and-remediation-actions)

Nella tabella seguente sono riepilogate le azioni di correzione attualmente supportate in Microsoft 365 Defender: 

|Azioni di correzione del dispositivo (endpoint)  |Azioni correttive della posta elettronica  |
|---------|---------|
|- Raccogliere il pacchetto di analisi <br/>- Isolare il dispositivo (questa azione può essere annullata)<br/>- Offboard machine <br/>- Esecuzione del codice di rilascio <br/>- Rilascio dalla quarantena <br/>- Esempio di richiesta <br/>- Limitare l'esecuzione del codice (questa azione può essere annullata) <br/>- Eseguire l'analisi antivirus <br/>- Arrestare e mettere in quarantena      |- BLOCCA URL (ora del clic)<br/>- Eliminare in modo reciso i messaggi di posta elettronica o i cluster<br/>- Posta elettronica in quarantena<br/>- Mettere in quarantena un allegato di posta elettronica<br/>- Disattivare l'inoltro della posta esterna          |

Le azioni correttive, in attesa di approvazione o già completate, possono essere visualizzate nel [centro notifiche.](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)

## <a name="remediation-actions-that-follow-automated-investigations"></a>Azioni correttive che seguono indagini automatizzate

Al termine di un'indagine automatizzata, viene raggiunto un verdetto per ogni prova coinvolta. A seconda del verdetto, vengono identificate le azioni correttive. In alcuni casi, le azioni correttive vengono eseguite automaticamente; in altri casi, invece, è necessario approvarle. Tutto dipende dalla configurazione [dell'analisi e della risposta automatizzate.](mtp-configure-auto-investigation-response.md)

Nella tabella seguente sono elencati i possibili verdetti e i risultati:

| Verdetto    | Area    | Risultati|
|------|------|------|
| Dannosa    | Dispositivi (endpoint)    | Le azioni di correzione vengono eseguite automaticamente [](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) (presupponendo che i gruppi di dispositivi dell'organizzazione siano impostati su Completo - correggere **automaticamente le minacce)**|
| Dannosa    | Contenuto della posta elettronica (URL o allegati) | Le azioni correttive consigliate sono in attesa di approvazione|
| Sospetta    | Dispositivi o contenuto della posta elettronica | Le azioni correttive consigliate sono in attesa di approvazione|
| Nessuna minaccia trovata    | Dispositivi o contenuto della posta elettronica    | Non sono necessarie azioni correttive|


## <a name="remediation-actions-that-are-taken-manually"></a>Azioni correttive eseguite manualmente

Oltre alle azioni di correzione che seguono le indagini automatizzate, il team delle operazioni di sicurezza può eseguire alcune azioni di correzione manualmente. Sono incluse le azioni seguenti:

- Azione manuale del dispositivo, ad esempio isolamento del dispositivo o quarantena dei file.
- Azione manuale della posta elettronica, ad esempio l'eliminazione recisa dei messaggi di posta elettronica. 
- [Azione di ricerca](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) avanzata su dispositivi o posta elettronica.
- [Azione](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer) di Explorer sul contenuto della posta elettronica, ad esempio lo spostamento della posta elettronica nella posta indesiderata, l'eliminazione recisa o l'eliminazione permanente della posta elettronica.
- Azione [di risposta in tempo](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) reale manuale, ad esempio l'eliminazione di un file, l'interruzione di un processo e la rimozione di un'attività pianificata.
- Azione di risposta in tempo reale con le API di [Microsoft Defender per endpoint,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/management-apis#microsoft-defender-for-endpoint-apis)ad esempio l'isolamento di un dispositivo, l'esecuzione di un'analisi antivirus e il recupero di informazioni su un file. 

## <a name="next-steps"></a>Passaggi successivi

- [Visita il Centro notifiche](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
- [Approvare o rifiutare azioni in sospeso](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)
- [Gestire falsi positivi/negativi nelle funzionalità di analisi e risposta automatizzate](mtp-autoir-report-false-positives-negatives.md)
