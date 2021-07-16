---
title: Introduzione a visibilità e dati analitici
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
description: Introduzione a visibilità e dati analitici.
ms.openlocfilehash: 12c1a01667b1bda545b619e931d99132e6611e35
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420132"
---
# <a name="get-started-with-visibility-and-insights"></a>Introduzione a visibilità e dati analitici

>*[Indicazioni sulle licenze Microsoft 365 per la sicurezza e la conformità](https://aka.ms/ComplianceSD).*

Il primo punto da cui iniziare è il dashboard di governance delle app in [https://compliance.microsoft.com/appgovernance](https://compliance.microsoft.com/appgovernance). Tenere presente che l'account di accesso deve disporre di uno di [questi ruoli di amministratore della governance delle app](app-governance-get-started.md#administrator-roles) per visualizzare i dati di governance.

![Pagina della governance delle app nel Centro conformità Microsoft 365](..\media\manage-app-protection-governance\mapg-cc-overview.png)

È anche possibile accedere al dashboard di governance delle app dall'**Interfaccia di amministrazione di Microsoft 365 > Centro conformità Microsoft 365 > Governance delle app > Pagina panoramica**.

## <a name="whats-available-on-the-dashboard"></a>Elementi disponibili nel dashboard

Il dashboard contiene un riepilogo dei componenti dell'ecosistema delle app Microsoft 365 nel tenant:

- **Riepilogo del tenant**: numero delle categorie principali di app e avvisi.
- **Avvisi di rilevamento e dei criteri**: gli avvisi attivi più recenti nel tenant
- **Accesso ai dati e alle risorse**: accesso aggregato all'API dell'applicazione e utilizzo complessivo delle risorse principali nel tenant. Passare il puntatore del mouse su ogni colonna mensile del grafico per visualizzare il valore corrispondente.
- **Migliorare la protezione e la governance delle app**: azioni consigliate, ad esempio la creazione di criteri di utilizzo o autorizzazione delle app.
- **App più popolari in base alla categoria**: le app principali ordinate in base alle categorie seguenti:
  
  - **Tutte le categorie**: ordina in base a tutte le categorie disponibili.
  - **Privilegi elevati**: i privilegi elevati sono una categoria determinata internamente in base all'apprendimento automatico e ai segnali della piattaforma.
  - **Livello di privilegi troppo elevato**: quando la governance dell'app riceve dati di telemetria che indicano che un'autorizzazione concessa a un'applicazione non è stata usata nei 90 giorni precedenti, tale applicazione ha un livello di privilegi troppo elevato. La governance dell'app deve essere eseguita per almeno 90 giorni per determinare se un'app ha un livello di privilegi troppo elevato.  
  - **Non verificate**: le applicazioni che non hanno ricevuto la [certificazione dell'editore](https://docs.microsoft.com/azure/active-directory/develop/publisher-verification-overview) vengono considerate non verificate.
  - **Solo app**: le [autorizzazioni dell'applicazione](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#permission-types) vengono usate dalle app che possono essere eseguite senza un utente connesso. Le app con autorizzazioni per accedere ai dati nel tenant rappresentano sono potenzialmente ad alto rischio.
  - **Nuove app**: le nuove app Microsoft 365 registrate negli ultimi sette giorni.  

## <a name="next-step"></a>Passaggio successivo

[Ottenere dati analitici su un'app specifica](app-governance-visibility-insights-view-apps.md).
