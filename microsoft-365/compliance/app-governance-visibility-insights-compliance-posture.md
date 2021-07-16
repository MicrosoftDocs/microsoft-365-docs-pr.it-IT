---
title: Determinare il profilo di conformità dell'app
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Determinare il profilo di conformità dell'app.
ms.openlocfilehash: 152f68e8fe0e7d7340d2e048bc73684bc079386f
ms.sourcegitcommit: 2fd60871975d61e60d4827b36cd689021fd2a4c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2021
ms.locfileid: "53438025"
---
# <a name="determine-your-app-compliance-posture"></a>Determinare il profilo di conformità dell'app

>*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](https://aka.ms/ComplianceSD).*

La governance delle app di Microsoft consente di valutare rapidamente il profilo di conformità delle app di terze parti e il relativo accesso ai dati nel tenant di Microsoft 365 dalla pagina Panoramica della governance delle app nel [Centro conformità Microsoft 365](https://aka.ms/appgovernance).

![La pagina Panoramica della governance delle app nel Centro conformità Microsoft 365](..\media\manage-app-protection-governance\mapg-cc-overview.png)

>[!Note]
> L'account di accesso deve disporre di uno di [questi ruoli](app-governance-get-started.md#administrator-roles) per visualizzare i dati di governance delle app.
>

In questa pagina puoi visualizzare:

- Per le app abilitate per OAuth che usano l'API Microsoft Graph:

  - Numero di app nel tenant
  - Numero di app con troppi privilegi
  - Numero di privilegi elevati

  Da queste informazioni è possibile determinare il livello di rischio per l'organizzazione da app con troppi privilegi e con privilegi elevati.

- Per gli avvisi:

  - Numero di avvisi attivi del tenant
  - Numero di avvisi basati sui rilevamenti della governance delle app (**avvisi delle minacce**)
  - Numero di avvisi basati sui criteri delle app in uso (**avvisi dei criteri**)
  - I 10 avvisi più recenti

  Da queste informazioni è possibile determinare la velocità con cui sono generati gli avvisi e il relativo numero di avvisi rilevati e basati su criteri.

- Per l’accesso ai dati e alle risorse:

  - Totale dei dati a cui accedono le app nel tenant tramite API Graph nei tre mesi di calendario correnti e precedenti. (Attualmente include solo l'utilizzo del caricamento e del download di Posta di Outlook e file)
  - Consumo dati nei tre mesi di calendario correnti e precedenti, suddivisi per tipo di risorsa. (Attualmente include solo l'utilizzo del caricamento e del download di Posta di Outlook e file)

  Da queste informazioni è possibile determinare il verificarsi di picchi anomali relativi all'accesso ai dati nel tenant di Microsoft 365.
