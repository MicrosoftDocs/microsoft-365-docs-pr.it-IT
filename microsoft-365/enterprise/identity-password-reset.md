---
title: "Passaggio 5: Semplificare l'accesso per gli utenti"
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/19/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Comprendere e configurare la reimpostazione della password self-service (SSPR) per Azure AD.
ms.openlocfilehash: 98118a5891ea8224843faa638b52a421d96e8a0b
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32287062"
---
# <a name="step-5-simplify-access-for-users"></a>Passaggio 5: Semplificare l'accesso per gli utenti

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)


<a name="identity-pw-writeback"></a>
## <a name="simplify-password-updates"></a>Semplificare gli aggiornamenti delle password

*Questo passaggio è facoltativo per gli ambienti ibridi e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*

In questa sezione verrà consentito agli utenti di reimpostare la password con Azure Active Directory (Azure AD), che è poi replicata nei servizi di Dominio di Active Directory (AD DS) locali. Questo processo è noto come writeback delle password. Con il writeback delle password gli utenti non hanno bisogno di aggiornare le password tramite Active Directory Domain Services (AD DS) in cui vengono archiviati gli account utente e i relativi attributi. Questo risulta particolarmente utile per gli utenti remoti o mobili che non dispongono di una connessione remota alla rete locale.

Il writeback delle password è necessario per utilizzare al meglio le funzioni di Identity Protection, come la richiesta agli utenti di cambiare le password locali nel caso in cui sia stato rilevato un alto rischio di violazione dell'account.

Per ulteriori informazioni e istruzioni di configurazione, vedere [Reimpostazione password self-service di Azure AD con writeback delle password](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback).

>[!Note]
>Eseguire l'aggiornamento all'ultima versione di Azure AD Connect per poter usufruire della migliore esperienza possibile e delle nuove caratteristiche appena rilasciate. Per ulteriori informazioni, vedere [Istallazione personalizzata di Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).
>

|||
|:-------|:-----|
|![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guida al lab di test: writeback della password](password-writeback-m365-ent-test-environment.md) |
|||

Come checkpoint provvisorio, è possibile vedere i [criteri di uscita](identity-exit-criteria.md#crit-identity-pw-writeback) per questa sezione.

<a name="identity-pw-reset"></a>
## <a name="simplify-password-resets"></a>Semplificare le reimpostazioni delle password

*Questo passaggio è facoltativo e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*

In questa sezione viene abilitata la reimpostazione della password self-service per consentire agli utenti di reimpostare o sbloccare le password o gli account. Per segnalare abusi o usi impropri è possibile utilizzare la reportistica dettagliata, che tiene traccia degli accessi degli utenti al sistema, insieme alle notifiche. È necessario attivare il writeback della password prima di implementare le reimpostazioni delle password.

Vedere le [istruzioni per implementare la reimpostazione della password](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment).

|||
|:-------|:-----|
|![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guida al lab di test: reimpostazione della password](password-reset-m365-ent-test-environment.md) |
|||

Come checkpoint provvisorio, è possibile vedere i [criteri di uscita](identity-exit-criteria.md#crit-identity-pw-reset) per questa sezione.


<a name="identity-sso"></a>
## <a name="simplify-user-sign-in"></a>Semplificare l'accesso utente

*Questo passaggio è facoltativo per gli ambienti ibridi e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*

In questa sezione si imposterà Accesso Single Sign-On (SSO) facile di Azure Active Directory per consentire agli utenti di accedere ai servizi che usano gli account utenti di Azure AD senza dover digitare la password e, in molti casi, il nome utente. In questo modo gli utenti possono facilmente accedere alle applicazioni basate su cloud come Office 365, senza aver bisogno di componenti aggiuntivi in loco quali ad esempio server federativi di identità.

L'accesso SSO facile di Azure AD viene configurato con lo strumento Azure AD Connect.

Vedere le [istruzioni per configurare l'accesso SSO facile ad Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).

|||
|:-------|:-----|
|![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guida del laboratorio di testing: accesso SSO facile di Azure AD](single-sign-on-m365-ent-test-environment.md) |
|||

Come checkpoint provvisorio, è possibile vedere i [criteri di uscita](identity-exit-criteria.md#crit-identity-sso) per questa sezione.


<a name="identity-custom-sign-in"></a>
## <a name="customize-the-office-365-sign-in-page"></a>Personalizzare la pagina di accesso a Office 365

*Questo passaggio è facoltativo e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*

In questo passaggio si aggiunge il nome dell'azienda, il logo e altri elementi familiari alla pagina di accesso dell'organizzazione per renderla più riconoscibile per gli utenti. 

Con Microsoft 365 Enterprise, è possibile personalizzare l'aspetto delle pagine di accesso e del Riquadro di accesso affinché includano il logo e colori dell'azienda e informazioni sull'utente personalizzate. 

Quando un utente prova ad accedere da un dispositivo, vede qualcosa simile a quanto mostrato nell'esempio seguente nella pagina di accesso di Office 365 *prima della personalizzazione*.

![Esempio di pagina di accesso di Office 365 prima della personalizzazione](./media/identity-customize-office-365-sign-in/id-step01-sign-in-before.png)

Ed ecco cosa vedrà lo stesso utente di Contoso Corporation *dopo la personalizzazione*.

![Esempio di pagina di accesso di Office 365 dopo la personalizzazione](./media/identity-customize-office-365-sign-in/id-step01-sign-in-after.png)

Per ulteriori informazioni, vedere [Aggiungere il marchio dell'organizzazione alla pagina di accesso di Office 365](https://docs.microsoft.com/office365/admin/setup/customize-sign-in-page).

Per istruzioni sulla configurazione, vedere [Aggiungere il marchio dell'organizzazione alle pagine di accesso e Riquadro di accesso](http://aka.ms/aadpaddbranding).

Come checkpoint provvisorio, è possibile vedere i [criteri di uscita](identity-exit-criteria.md#crit-identity-custom-sign-in) per questa sezione.


## <a name="next-step"></a>Passaggio successivo

|||
|:-------|:-----|
|![](./media/stepnumbers/Step6.png)| [Usare i gruppi per facilitare la gestione](identity-self-service-group-management.md) |


