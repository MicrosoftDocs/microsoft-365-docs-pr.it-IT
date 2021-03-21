---
title: Azioni di correzione in Microsoft 365 Defender
description: Panoramica delle azioni di correzione che seguono indagini automatizzate in Microsoft 365 Defender
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
ms.date: 01/29/2021
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: 7dd95e8d7fe6424e294fbc9500fb908819463678
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928629"
---
# <a name="remediation-actions-in-microsoft-365-defender"></a>Azioni di correzione in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

## <a name="remediation-actions"></a>Azioni correttive

Durante e dopo un'indagine automatizzata in Microsoft 365 Defender, vengono identificate azioni di correzione per elementi dannosi o sospetti. Alcuni tipi di azioni di correzione vengono eseguite nei dispositivi, definiti anche endpoint. Altre azioni di correzione vengono eseguite sul contenuto della posta elettronica. Le indagini automatizzate vengono completate dopo l'esecuzione, l'approvazione o il rifiuto di azioni correttive.

> [!IMPORTANT]
> Il fatto che le azioni di correzione siano eseguite automaticamente o solo dopo l'approvazione dipende da determinate impostazioni, ad esempio il modo in cui i livelli di automazione. Per ulteriori informazioni, vedere gli articoli seguenti:
> - [Configurare le funzionalità di analisi e risposta automatizzate in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md)
> - [Modalità di correzione delle minacce nei dispositivi](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
> - [Minacce e azioni di correzione sui contenuti di collaborazione & posta elettronica](../office-365-security/air-remediation-actions.md#threats-and-remediation-actions)

Nella tabella seguente sono riepilogate le azioni di correzione attualmente supportate in Microsoft 365 Defender: 

|Azioni di correzione del dispositivo (endpoint)  |Azioni correttive della posta elettronica  |
|:---------|:---------|
|- Raccogliere il pacchetto di indagine <br/>- Isolare il dispositivo (questa azione può essere annullata)<br/>- Computer offboard <br/>- Esecuzione del codice di rilascio <br/>- Rilascio dalla quarantena <br/>- Esempio di richiesta <br/>- Limitare l'esecuzione del codice (questa azione può essere annullata) <br/>- Eseguire l'analisi antivirus <br/>- Arrestare e mettere in quarantena      |- URL di blocco (ora del clic)<br/>- Eliminazione recidiva dei messaggi di posta elettronica o dei cluster<br/>- Posta elettronica in quarantena<br/>- Mettere in quarantena un allegato di posta elettronica<br/>- Disattivare l'inoltro della posta esterna          |

Le azioni di correzione, in attesa di approvazione o già completate, possono essere visualizzate nel [Centro notifiche.](./mtp-action-center.md)

## <a name="remediation-actions-that-follow-automated-investigations"></a>Azioni correttive che seguono indagini automatizzate

Al termine di un'indagine automatizzata, viene raggiunto un verdetto per ogni prova coinvolta. A seconda del verdetto, vengono identificate le azioni correttive. In alcuni casi, le azioni correttive vengono eseguite automaticamente; in altri casi, invece, è necessario approvarle. Tutto dipende dal modo in cui [vengono configurate l'indagine e la risposta automatizzate.](mtp-configure-auto-investigation-response.md)

Nella tabella seguente sono elencati i possibili verdetti e i risultati:

| Verdetto    | Area    | Risultati|
|------|------|------|
| Dannosa    | Dispositivi (endpoint)    | Le azioni di correzione vengono eseguite automaticamente [](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) (presupponendo che i gruppi di dispositivi dell'organizzazione siano impostati su **Completo - correggere automaticamente le minacce)**|
| Dannosa    | Contenuto della posta elettronica (URL o allegati) | Le azioni correttive consigliate sono in attesa di approvazione|
| Sospetta    | Dispositivi o contenuto della posta elettronica | Le azioni correttive consigliate sono in attesa di approvazione|
| Nessuna minaccia trovata    | Dispositivi o contenuto della posta elettronica    | Non sono necessarie azioni correttive|


## <a name="remediation-actions-that-are-taken-manually"></a>Azioni correttive eseguite manualmente

Oltre alle azioni di correzione che seguono indagini automatizzate, il team delle operazioni di sicurezza può eseguire alcune azioni di correzione manualmente. Sono incluse le azioni seguenti:

- Azione manuale del dispositivo, ad esempio isolamento del dispositivo o quarantena dei file.
- Azione manuale della posta elettronica, ad esempio l'eliminazione recidiva dei messaggi di posta elettronica. 
- [Azione di ricerca](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) avanzata su dispositivi o posta elettronica.
- [Azione di Explorer](../office-365-security/threat-explorer.md) sul contenuto della posta elettronica, ad esempio lo spostamento della posta elettronica nella posta indesiderata, l'eliminazione recisa della posta elettronica o l'eliminazione permanente della posta elettronica.
- Azione [di risposta in tempo](/windows/security/threat-protection/microsoft-defender-atp/live-response) reale manuale, ad esempio l'eliminazione di un file, l'arresto di un processo e la rimozione di un'attività pianificata.
- Azione di risposta in tempo reale con le API di [Microsoft Defender per endpoint,](/windows/security/threat-protection/microsoft-defender-atp/management-apis#microsoft-defender-for-endpoint-apis)ad esempio l'isolamento di un dispositivo, l'esecuzione di un'analisi antivirus e il recupero di informazioni su un file. 

## <a name="next-steps"></a>Passaggi successivi

- [Visita il Centro notifiche](./mtp-action-center.md)
- [Visualizzare e gestire le azioni correttive](./mtp-autoir-actions.md)
- [Gestire falsi positivi/negativi nelle funzionalità di analisi e risposta automatizzate](mtp-autoir-report-false-positives-negatives.md)