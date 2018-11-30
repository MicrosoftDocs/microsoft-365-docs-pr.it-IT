---
title: "Passaggio 10: semplificare l'accesso utente"
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
description: Comprendere e configurare l'accesso Single Sign-On facile ad Azure AD (SSO facile).
ms.openlocfilehash: 9d18cb559d3a4a9ee401e0f94fb53bc6360d88c8
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868822"
---
# <a name="step-10-simplify-user-sign-in"></a>Passaggio 10: semplificare l'accesso utente

*Questo passaggio è facoltativo per gli ambienti ibridi e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

In questo passaggio, viene configurato l'accesso Single Sign-On facile (SSO facile di Azure Active Directory) per consentire agli utenti di accedere ai servizi che usano gli account utente di Azure Active Directory senza dover digitare la password e in molti casi, i propri nomi utente. In questo modo, gli utenti possono accedere sempre facilmente alle applicazioni basate sul cloud, come Office 365, senza componenti aggiuntivi in locale, quali ad esempio i server di federazione delle identità.

L'accesso SSO facile di Azure AD viene configurato con lo strumento Azure AD Connect.

Vedere le [istruzioni per configurare l'accesso SSO facile ad Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).

|||
|:-------|:-----|
|![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guida del laboratorio di testing: accesso SSO facile di Azure AD](single-sign-on-m365-ent-test-environment.md) |
|||

Come checkpoint provvisorio, è possibile vedere i [criteri uscita](identity-exit-criteria.md#crit-identity-sso) per questo passaggio.

## <a name="next-step"></a>Passaggio successivo

|||
|:-------|:-----|
|![](./media/stepnumbers/Step11.png)| [Personalizzare la pagina di accesso a Office 365](identity-customize-office-365-sign-in.md) |

