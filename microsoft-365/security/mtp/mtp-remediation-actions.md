---
title: Azioni di correzione che seguono indagini automatizzate in Microsoft Threat Protection
description: Ottenere una panoramica delle azioni correttive che seguono le indagini automatizzate in Microsoft Threat Protection
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
ms.topic: conceptual
ms.custom: autoir
ms.date: 09/16/2020
ms.reviewer: evaldm, isco
ms.openlocfilehash: 205809bac14cc82e850ea1cbc0349256432bfe68
ms.sourcegitcommit: 7c0873d2a804f17697844fb13f1a100fabce86c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962586"
---
# <a name="remediation-actions-following-automated-investigations-in-microsoft-threat-protection"></a>Azioni di correzione che seguono indagini automatizzate in Microsoft Threat Protection

**Si applica a:**
- Microsoft Threat Protection


## <a name="remediation-actions"></a>Azioni correttive

Durante e dopo un'analisi automatizzata in Microsoft Threat Protection, le azioni di correzione vengono identificate per gli elementi dannosi o sospetti. Alcuni tipi di azioni di correzione vengono eseguiti nei dispositivi, detti anche endpoint. Altre azioni di correzione vengono eseguite sul contenuto della posta elettronica. Indagini automatizzate complete dopo che sono state apportate, approvate o rifiutate le azioni di correzione.

Nella tabella seguente sono riepilogate le azioni di correzione attualmente supportate in Microsoft Threat Protection: 

|Azioni di correzione del dispositivo (endpoint)  |Azioni correttive della posta elettronica  |
|---------|---------|
|-Raccogliere il pacchetto di indagine <br/>-Isolate Device (questa azione può essere annullata)<br/>-Trasferisce Machine <br/>-Esecuzione del codice di rilascio <br/>-Rilascio dalla quarantena <br/>-Esempio di richiesta <br/>-Limitare l'esecuzione del codice (questa azione può essere annullata) <br/>-Eseguire l'analisi antivirus <br/>-Arrestare e mettere in quarantena      |-Blocca URL (tempo di clic)<br/>-Eliminare i messaggi di posta elettronica o i cluster<br/>-Posta in quarantena<br/>-Mettere in quarantena un allegato di posta elettronica<br/>-Disattivare l'inoltro della posta esterna          |

Le azioni di correzione, sia che si tratti di approvazione in sospeso o che sono già state completate, possono essere visualizzate nel [Centro azioni](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).

## <a name="remediation-actions-follow-automated-investigations"></a>Le azioni correttive seguono indagini automatizzate

Al termine di un'indagine automatizzata, viene raggiunto un verdetto per ogni elemento di prova coinvolto. A seconda del verdetto, vengono identificate le azioni di correzione. In alcuni casi, le azioni correttive vengono eseguite automaticamente; in altri casi, invece, è necessario approvarle. Tutto dipende da come [viene configurata l'analisi e la risposta automatizzata](mtp-configure-auto-investigation-response.md).

Nella tabella seguente sono elencati i possibili verdetti e i risultati:

|Verdetto    |Area    |Risultati|
|------|------|------|
|Dannosa    |Dispositivi (endpoint)    |Le azioni di correzione vengono eseguite automaticamente (presupponendo che i [gruppi di dispositivi](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) dell'organizzazione siano impostati automaticamente su **minacce complete**)|
|Dannosa    |Contenuto della posta elettronica (URL o allegati) | Le azioni correttive consigliate sono in attesa di approvazione|
|Sospetta    |Dispositivi o contenuto della posta elettronica |Le azioni correttive consigliate sono in attesa di approvazione|
|Non sono state trovate minacce    |Dispositivi o contenuto della posta elettronica    |Non sono necessarie azioni correttive|

> [!IMPORTANT]
> Se le azioni di correzione vengono eseguite automaticamente o solo dopo l'approvazione dipendono da determinate impostazioni, ad esempio i criteri di gruppo per i dispositivi dell'organizzazione. Per ulteriori informazioni, vedere gli articoli seguenti:
> - [Configurare le funzionalità di analisi e risposta automatizzate in Microsoft Threat Protection](mtp-configure-auto-investigation-response.md)
> - [Come vengono risolte le minacce nei dispositivi](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

## <a name="next-steps"></a>Passaggi successivi

- [Visitare il centro azioni](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
- [Approvare o rifiutare azioni in sospeso](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)
- [Gestire i falsi positivi/negativi nelle funzionalità di analisi e risposta automatizzate](mtp-autoir-report-false-positives-negatives.md)
