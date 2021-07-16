---
title: Informazioni sui criteri delle applicazioni
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
description: Informazioni sui criteri delle applicazioni.
ms.openlocfilehash: 6d4ff23ca0e09f5e410d32d6ced144afc0c4bb15
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420361"
---
# <a name="learn-about-app-policies"></a>Informazioni sui criteri delle applicazioni

>*[Indicazioni sulle licenze di Microsoft 365 per la sicurezza e la conformità](https://aka.ms/ComplianceSD).*

La governance delle app Microsoft rileva il comportamento anomalo delle app nel tenant di Microsoft 365 e genera avvisi che è possibile visualizzare, analizzare e risolvere. Oltre a questa funzionalità di rilevamento predefinita, è possibile usare un insieme di modelli predefiniti per creare criteri di app personalizzati che generano altri avvisi.

Questi criteri per i modelli e i comportamenti delle app e utenti possono proteggere gli utenti dall'uso di app non conformi o dannose e limitare l'accesso delle app rischiose ai dati del tenant.

Ecco una rapida revisione dei ruoli di amministratore necessari per la gestione dei criteri delle app.

| Ruolo | Lettura dei criteri | Creare, aggiornare o eliminare criteri |
|:-------|:-----|:-------|
| Amministratore di conformità | ![Segno di spunta](..\media\checkmark.png) | ![Segno di spunta](..\media\checkmark.png) |
| Lettore di conformità | ![Segno di spunta](..\media\checkmark.png) |  |
| Amministratore globale | ![Segno di spunta](..\media\checkmark.png) | ![Segno di spunta](..\media\checkmark.png) |
| Ruolo con autorizzazioni di lettura globali  | ![Segno di spunta](..\media\checkmark.png) |  |
| Amministratore della sicurezza | ![Segno di spunta](..\media\checkmark.png) | ![Segno di spunta](..\media\checkmark.png) |
| Ruolo con autorizzazioni di lettura per la sicurezza  | ![Segno di spunta](..\media\checkmark.png) |  |
| Operatore della sicurezza | ![Segno di spunta](..\media\checkmark.png) | ![Segno di spunta](..\media\checkmark.png) |
||||

<!--
How app policies are the method by which MAPG detects app anomolies resulting in detection (alerts) and remediation (manual or automatic) 


CFA #2 Scenario 1: As an admin, I can quickly set up policies to govern M365 apps in my tenant using MAPG out-of-the-box templates
CFA #2 Scenario 2: As an admin, I can create customized policies to govern M365 apps in my tenant to meet my organizations requirements.
CFA #2 Scenario 3: As an admin or policy reviewer, I can view all policies created in my environment and quickly see which policies have associated alerts. 
CFA #2 Scenario 4: As an admin, I can adjust policies efficiently to meet changing needs.

App policy templates

- Basic info
- Policy settings and conditions
- Actions
- Status

--> 

## <a name="next-step"></a>Passaggio successivo

[Introduzione ai criteri delle applicazioni.](app-governance-app-policies-get-started.md)
