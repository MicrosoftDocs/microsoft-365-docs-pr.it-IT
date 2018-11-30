---
title: "Passaggio 5: configurare l'autenticazione a più fattori"
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/05/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Comprendere e configurare l'autenticazione a più fattori per gli account utente.
ms.openlocfilehash: a54eb047c94430a2b3f61d06500c929e400e3d82
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868763"
---
# <a name="step-5-set-up-multi-factor-authentication"></a>Passaggio 5: configurare l'autenticazione a più fattori

*Questo passaggio è facoltativo e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

Con questo passaggio è possibile configurare l'autenticazione a più fattori (MFA) per aggiungere un secondo livello di protezione per l'accesso e le transazioni utente. La MFA richiede una verifica aggiuntiva dopo l'immissione della password da parte dell'utente. Senza la MFA, la password rimane l'unico metodo di verifica. Molte password potrebbero essere indovinate facilmente da un utente malintenzionato o condivise inavvertitamente con parti non attendibili.

Con la MFA, il secondo livello di sicurezza può essere:

- Un dispositivo personale e attendibile che non può essere oggetto di spoofing o duplicazioni, come per esempio uno smartphone.
- Un attributo biometrico, come per esempio un'impronta digitale.

Abilitando la MFA si configura il metodo secondario di autenticazione per ogni account utente. È necessario comunicare agli utenti che la MFA è abilitata, in modo che comprendano i requisiti, come l'utilizzo obbligatorio di uno smartphone per effettuare l'accesso, e possano effettuare l'accesso con esito positivo.

Per maggiori informazioni, vedere [Pianificare l'autenticazione a più fattori per le distribuzioni di Office 365](https://support.office.com/article/Plan-for-multifactor-authentication-for-Office-365-Deployments-043807b2-21db-4d5c-b430-c8a6dee0e6ba)

Per configurare l'autenticazione a più fattori, [Configurare l'autenticazione a più fattori per gli utenti di Office 365](https://support.office.com/article/Set-up-multi-factor-authentication-for-Office-365-users-8f0454b2-f51a-4d9c-bcde-2c48e41621c6).

È possibile richiedere la MFA con i criteri di accesso condizionale. Ad esempio, è possibile configurare un criterio di richiesta di MFA quando l'autenticazione è considerata di rischio medio o alto. Per ulteriori informazioni, vedere [Criteri comuni di identità e accesso dei dispositivi](identity-access-policies.md#require-mfa-based-on-sign-in-risk).

>[!Note]
>In alcune applicazioni, come per esempio Microsoft Office 2010 o le applicazioni più vecchie di Apple Mail, non è possibile utilizzare la MFA. Per utilizzare queste app, sarà necessario utilizzare le "password dell'app" al posto della password tradizionale. La password dell'app consente di bypassare la MFA e continuare a lavorare. Per ulteriori informazioni sulle password dell'app, vedere [Creare una password dell'app per Office 365](https://support.office.com/article/Create-an-app-password-for-Office-365-3e7c860f-bda4-4441-a618-b53953ee1183).
>

|||
|:-------|:-----|
|![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guida al lab di test: autenticazione a più fattori](multi-factor-authentication-microsoft-365-test-environment.md) |
|||

Come checkpoint provvisorio, è possibile vedere i [criteri uscita](identity-exit-criteria.md#crit-identity-mfa) per questo passaggio.

## <a name="next-step"></a>Passaggio successivo

|||
|:-------|:-----|
|![](./media/stepnumbers/Step6.png)| [Proteggere dalla compromissione delle credenziali](identity-azure-ad-identity-protection.md) |

