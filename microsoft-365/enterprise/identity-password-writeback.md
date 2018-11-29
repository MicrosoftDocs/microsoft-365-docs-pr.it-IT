---
title: 'Passaggio 9: semplificare gli aggiornamenti delle password'
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
description: Comprendere e configurare il writeback delle password per gli ambienti ibridi.
ms.openlocfilehash: 55da101ca729de804ae76dafbe35a46969af9d8d
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868461"
---
# <a name="step-9-simplify-password-updates"></a>Passaggio 9: semplificare gli aggiornamenti delle password

*Questo passaggio è facoltativo per gli ambienti ibridi e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

Questo passaggio consente agli utenti di reimpostare le password tramite Azure Active Directory (AD), la quale viene replicata in Windows Server Active Directory (AD). Questo processo è noto come writeback delle password. Grazie al writeback delle password, gli utenti non dovranno aggiornare le password tramite Windows Server Active Directory locale in cui sono archiviati gli attributi e gli account utente. Questa funzione risulta particolarmente utile per gli utenti in remoto o in roaming che non dispongono di una connessione di accesso remoto a una rete locale.

Il writeback delle password è necessario per utilizzare al meglio le funzioni di Identity Protection, come la richiesta agli utenti di cambiare le password locali nel caso in cui sia stato rilevato un alto rischio di violazione dell'account.

Per ulteriori informazioni e istruzioni di configurazione, vedere [Reimpostazione password self-service di Azure AD con writeback delle password](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback).

>[!Note]
>Eseguire l'aggiornamento all'ultima versione di Azure AD Connect per poter usufruire della migliore esperienza possibile e delle nuove caratteristiche appena rilasciate. Per ulteriori informazioni, vedere [Istallazione personalizzata di Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).
>

Come checkpoint provvisorio, è possibile vedere i [criteri uscita](identity-exit-criteria.md#crit-identity-pw-writeback) per questo passaggio.

## <a name="next-step"></a>Passaggio successivo

|||
|:-------|:-----|
|![](./media/stepnumbers/Step10.png)| [Semplificare l'accesso dell'account utente](identity-single-sign-on.md) |

