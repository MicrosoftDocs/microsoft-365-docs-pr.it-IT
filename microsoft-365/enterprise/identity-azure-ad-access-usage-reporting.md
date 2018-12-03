---
title: "Passaggio 13: monitorare l'attività di tenant e di accesso"
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Comprendere e configurare l'accesso e il report di utilizzo di Azure AD.
ms.openlocfilehash: 997d52bc11036e1dbb7dcc6e1f9f48a59b2ddbf5
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868265"
---
# <a name="step-13-monitor-tenant-and-sign-in-activity"></a>Passaggio 13: monitorare l'attività di tenant e di accesso

*Questo passaggio è facoltativo e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

In questo passaggio, è possibile rivedere le attività dei log di controllo e le attività di accesso utilizzando la creazione di report di Azure AD. Sono disponibili due tipi di report.

Il **Report delle attività di log di controllo** registra la storia di ogni attività eseguita nel tenant di Azure AD. Questo report può fornire risposte a domande come:

- Chi ha aggiunto un membro al gruppo amministratore?
- Quali utenti hanno effettuato l'accesso in una determinata app?
- Quante reimpostazioni della password sono state eseguite?

Il **Report delle attività di accesso** registra gli utenti che hanno eseguito le attività riportate nei report dei log di controllo. Questo report può fornire risposte a domande come:

- Qual è il criterio di accesso per un utente specifico sotto esame?
- Qual'è il numero degli accessi durante un giorno, una settimana o un mese?
- Quanti tentativi di accesso non hanno avuto esito positivo e per quali account si è verificata questa occorrenza?

Per ulteriori informazioni sui report e su come accedere ad essi, vedere [Creazione di report di Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-azure-portal).

Il risultato di questo passaggio è acquisire consapevolezza riguardo tali report e comprendere come utilizzarli per comprendere gli eventi e le attività di Azure AD a scopo di pianificazione e sicurezza.

## <a name="next-step"></a>Passaggio successivo

|||
|:-------|:-----|
|![](./media/stepnumbers/Step14.png)| [Consentire agli utenti di creare e gestire i propri gruppi](identity-self-service-group-management.md) |
