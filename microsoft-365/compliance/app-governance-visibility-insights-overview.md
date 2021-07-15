---
title: Informazioni su visibilità e dati analitici
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
description: Informazioni su visibilità e dati analitici.
ms.openlocfilehash: ee485c972193c515bafec55f58a7a89aa1f567f1
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420126"
---
# <a name="learn-about-visibility-and-insights"></a>Informazioni su visibilità e dati analitici

>*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](https://aka.ms/ComplianceSD).*

Con la governance delle app Microsoft, è possibile ottenere rapidamente visibilità e dati analitici significativi sull'ecosistema di applicazioni Microsoft 365. È necessario iniziare dalla dashboard di governance delle app che fornisce un riepilogo dettagliato degli avvisi e delle app nel tenant che richiedono l'attenzione dell'amministratore.

La visibilità e i dati analitici della governance delle app consente di visualizzare:

- Un elenco delle app abilitate per OAuth che accedono ai dati di Microsoft 365 tramite le API di Microsoft Graph.
- Una visualizzazione dettagliata delle attività dell'app in modo da consentire all’utente di reagire o rispondere di conseguenza.

>[!Note]
>Le app esclusive di Azure, a cui non sono concesse le autorizzazioni necessarie per accedere alle risorse Microsoft 365, non vengono visualizzate nella governance delle app.
>

Per una panoramica dei ruoli di amministratore necessari alla visibilità e ai dati analitici, vedere [Ruoli di amministratore](app-governance-get-started.md#administrator-roles).

<!--
From messaging doc, page 21:

View M365 App List & Metadata
View M365 App List of Consented Users
View M365 App Permissions
View M365 App Permission Usage
View Over permissioned Apps
Aggregate M365 API Usage Data by Workload (count, download/upload)
Per-App M365 API Usage Data by Workload (count, download/upload)
Per-User M365 API Usage Data by Workload (count, download/upload)
M365 API Usage Data For High-Value/Classified Assets (count, download/upload)
M365 API Error Analysis per App
-->

Con la governance delle app, è possibile visualizzare:

- Una dashboard di tutti i dati analitici.
- I dati a cui hanno avuto accesso una o tutte le app con dati analitici a livello di carico di lavoro e utente.
- Informazioni e metadati dell'app, ad esempio autorizzazioni, data di registrazione e certificazione.
- Informazioni e metadati dell'autore, ad esempio nome e stato di verifica.
- Utilizzo delle principali risorse (e-mail e file) nel tenant.
- Dati analitici su:

  - App con privilegi elevati.
  - App con troppi privilegi.
  - App a utilizzo elevato.
  - Principali utenti autorizzati e relativi dati a cui può accedere un'app specifica.
  - Account prioritari con dati a cui un'app specifica può accedere.

- Una visualizzazione cumulativa degli utenti che accedono alle app.
- Dati analitici degli avvisi.
- Dati analitici sull'elenco dei criteri.
<!-->
- Criteri creati in MCAS nel portale di governance delle app.
-->
- Avvisi per le app abilitate per OAuth generati in MCAS, nel portale di governance delle app.

È inoltre possibile:

- Eseguire il drill-down di una singola app (pagina dell'app) con tutti i dati analitici associati.
- Eseguire il drill-down degli utenti principali in base ai dati e agli account prioritari all'interno di una singola app.

## <a name="next-step"></a>Passaggio successivo

[Introduzione ai dati analitici dell’applicazione](app-governance-visibility-insights-get-started.md)
