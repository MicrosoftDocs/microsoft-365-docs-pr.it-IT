---
title: 'Passaggio 2: proteggere le password'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: È necessario rendere le password complesse e gestibili all'interno dell'organizzazione.
ms.openlocfilehash: a3661eedc11e0c826422f540cf1e2e9abf911f9d
ms.sourcegitcommit: 83b919f8a7fcc4f75044ffc09fecd66fb4ed35b5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/24/2019
ms.locfileid: "37662552"
---
# <a name="step-2-secure-your-passwords"></a>Passaggio 2: proteggere le password

![Fase 2: identità](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-password-prot"></a>
## <a name="prevent-bad-passwords"></a>Impedire l'uso di password non consentite

*Questo passaggio è facoltativo e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*

Per creare le password degli account utente, tutti gli utenti devono attenersi alla [Guida alle password di Microsoft](https://www.microsoft.com/research/publication/password-guidance/).

Per impedire agli utenti di creare password facilmente determinabili, usare la protezione password di Azure Active Directory, che usa sia un elenco di password non consentite globale che un elenco facoltativo di password non consentite personalizzato, specificato dall'utente. Ad esempio, è possibile specificare condizioni specifiche per l'organizzazione, come:

- Nomi di marchio
- Nomi di prodotto
- Posizioni, ad esempio la sede centrale aziendale
- Termini interni specifici della società
- Abbreviazioni con significato aziendale specifico

È possibile bloccare le password non consentite [nel cloud](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) e per [Active Directory Domain Services (AD DS) locale](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises).

Come checkpoint provvisorio, è possibile vedere i [criteri uscita](identity-exit-criteria.md#crit-password-prot) per questa sezione.

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

In questa sezione verrà impostato l’Accesso Single Sign-On (SSO) facile di Azure Active Directory, che funziona con la Sincronizzazione dell'hash delle password (PHS) e l’Autenticazione pass-through (PTA), per consentire agli utenti di accedere ai servizi che usano gli account utenti di Azure AD senza dover digitare la password e, in molti casi, il nome utente. In questo modo gli utenti possono facilmente accedere alle applicazioni basate su cloud come Office 365, senza aver bisogno di componenti aggiuntivi in loco quali ad esempio server federativi di identità.

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

Per ulteriori informazioni, vedere [Aggiungere il marchio dell'organizzazione alla pagina di accesso di Office 365](https://docs.microsoft.com/office365/admin/setup/customize-sign-in-page).

Per istruzioni sulla configurazione, vedere [Aggiungere il marchio dell'organizzazione alle pagine di accesso e Riquadro di accesso](http://aka.ms/aadpaddbranding).

Come checkpoint provvisorio, è possibile vedere i [criteri di uscita](identity-exit-criteria.md#crit-identity-custom-sign-in) per questa sezione.

## <a name="next-step"></a>Passaggio successivo

|||
|:-------|:-----|
|![Passaggio 3](./media/stepnumbers/Step3.png)| [Proteggere e gestire gli accessi degli utenti](identity-secure-user-sign-ins.md) |
