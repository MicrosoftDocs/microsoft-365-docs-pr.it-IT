---
title: Passaggio 1. Aumentare la sicurezza di accesso per i lavoratori ibridi con la MFA.
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- m365solution-remotework
- m365solution-scenario
ms.custom: ''
description: È necessario che l'utente ibrido acceda con l'autenticazione a più fattori (MFA).
ms.openlocfilehash: 105c2f7170b4bea648427b0fda57ad081cb99a86
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2021
ms.locfileid: "52788962"
---
# <a name="step-1-increase-sign-in-security-for-hybrid-workers-with-mfa"></a>Passaggio 1. Aumentare la sicurezza di accesso per i lavoratori ibridi con la MFA.

Per aumentare la sicurezza degli accessi dei lavoratori ibridi, utilizzare l'autenticazione a più fattori (MFA). La MFA richiede che gli accessi utente siano soggetti a un'ulteriore verifica oltre alla password dell'account utente. Anche se un utente malintenzionato determina una password dell'account utente, deve anche essere in grado di rispondere a un'ulteriore verifica, ad esempio un SMS inviato a uno smartphone prima che venga concesso l'accesso.

![L'inserimento della password corretta e un'ulteriore verifica permettono di accedere](../media/empower-people-to-work-remotely/remote-workers-mfa.png)

Per tutti gli utenti, inclusi i lavoratori ibridi e in particolare gli amministratori, Microsoft consiglia vivamente la MFA.

Sono disponibili tre modi per richiedere agli utenti di utilizzare la MFA in base al piano Microsoft 365.

|Piano  |Consiglio  |
|---------|---------|
|Tutti i piani di Microsoft 365 (senza licenze di Azure AD Premium P1 o P2)     |[Abilitare le impostazioni predefinite di sicurezza in Azure AD](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults). Le impostazioni predefinite di sicurezza in Azure AD includono la MFA per utenti e amministratori.   |
|Microsoft 365 E3 (include le licenze di Azure AD Premium P1)     | Usare i [criteri comuni di accesso condizionale](/azure/active-directory/conditional-access/concept-conditional-access-policy-common) per configurare i criteri seguenti: <br>- [Richiedere la MFA per amministratori](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa) <br>- [Richiedere la MFA per tutti gli utenti](/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa) <br> - [Bloccare l'autenticazione legacy](/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)       |
|Microsoft 365 E5 (include le licenze di Azure AD Premium P2)     | Sfruttando Azure AD Identity Protection, iniziare a implementare il [set raccomandato di accesso condizionale e criteri correlati](../security/office-365-security/identity-access-policies.md) di Microsoft creando questi criteri:<br> - [Richiedere la MFA quando il rischio di accesso è considerato *medio* o *elevato*](../security/office-365-security/identity-access-policies.md#require-mfa-based-on-sign-in-risk) <br>- [Bloccare i client che non supportano l'autenticazione moderna](../security/office-365-security/identity-access-policies.md#block-clients-that-dont-support-multi-factor)<br>- [Gli utenti a rischio elevato devono modificare la password](../security/office-365-security/identity-access-policies.md#high-risk-users-must-change-password)       |
| | |

## <a name="security-defaults"></a>Impostazioni predefinite per la sicurezza

Le impostazioni predefinite di sicurezza sono una nuova funzionalità per gli abbonamenti a pagamento o di valutazione di Microsoft 365 e Office 365 creati dopo il 21 ottobre 2019. Questi abbonamenti hanno impostazioni predefinite di sicurezza attivate, che ***richiedono a tutti gli utenti di utilizzare la MFA con l'app Microsoft Authenticator***.
 
Gli utenti hanno 14 giorni per registrarsi per la MFA con l'app Microsoft Authenticator dai propri smartphone, periodo che inizia dalla prima volta che accedono dopo aver abilitato le impostazioni predefinite di sicurezza. Trascorsi 14 giorni, l'utente non sarà in grado di accedere fino al completamento della registrazione della MFA.

Le impostazioni di sicurezza predefinite garantiscono che tutte le organizzazioni dispongano di un livello base di sicurezza per l'accesso degli utenti abilitato per impostazione predefinita. È possibile disabilitare le impostazioni predefinite di sicurezza a favore della MFA con criteri di accesso condizionale o per singoli account.

Per altre informazioni, vedere questa [panoramica delle impostazioni predefinite di sicurezza](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).

## <a name="conditional-access-policies"></a>Criteri di accesso condizionale

I criteri di accesso condizionale sono un insieme di regole che specificano le condizioni in base alle quali gli accessi vengono valutati e consentiti. Ad esempio, è possibile creare un criterio di accesso condizionale che indichi:

- Se il nome dell'account utente corrisponde a un membro di un gruppo per utenti a cui sono assegnati i ruoli di amministratore di Exchange, utenti, password, sicurezza, SharePoint o globale, richiedere la MFA prima di consentire l'accesso.

Questo criterio consente di richiedere l'autenticazione a più fattori in base all'appartenenza al gruppo, anziché configurare i singoli account utente per l'autenticazione a più fattori quando vengono assegnati o non assegnati tramite questi ruoli di amministratore.

È inoltre anche utilizzare i criteri di accesso condizionale per funzionalità più avanzate, come la necessità di eseguire l'accesso da un dispositivo conforme, come il proprio portatile con Windows 10.

L'accesso condizionale richiede licenze di Azure AD Premium P1, che sono incluse con Microsoft 365 E3 ed E5.

Per altre informazioni, vedere questa [panoramica dell'accesso condizionale](/azure/active-directory/conditional-access/overview).

## <a name="azure-ad-identity-protection-support"></a>Supporto di Azure AD Identity Protection

Con Azure AD Identity Protection è possibile creare un criterio di accesso condizionale aggiuntivo che indichi:

- Se il rischio di accesso corrisponde a medio o alto, è richiesta la MFA.

Azure AD Identity Protection richiede licenze di Azure AD Premium P2, che sono incluse in Microsoft 365 E5.

Per altre informazioni, vedere [Accesso condizionale basato sul rischio](/azure/active-directory/conditional-access/howto-conditional-access-policy-risk#require-mfa-medium-or-high-sign-in-risk-users).

Tramite Azure AD Identity Protection è anche possibile creare un criterio per chiedere agli utenti di iscriversi per l'autenticazione a più fattori. Per altre informazioni, vedere [Configurare i criteri di registrazione dell'autenticazione a più fattori di Azure](/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy)


## <a name="using-these-methods-together"></a>Usare questi metodi insieme

Tenere presente quanto segue:

- Non è possibile abilitare le impostazioni predefinite di sicurezza se sono abilitati criteri di accesso condizionale.
- Non è possibile abilitare alcun criterio di accesso condizionale se sono abilitate le impostazioni predefinite di sicurezza.

Se le impostazioni predefinite di sicurezza sono abilitate, a tutti i nuovi utenti viene richiesta la registrazione della MFA e l'utilizzo dell'app Microsoft Authenticator. 

Questa tabella mostra i risultati dell'abilitazione della MFA con impostazioni predefinite di sicurezza e criteri di accesso condizionale.

| Metodo | Abilitato | Disattivato | Metodo di autenticazione aggiuntivo |
|:-------|:-----|:-------|:-------|
| **Impostazioni predefinite per la sicurezza**  | Non è possibile utilizzare i criteri di accesso condizionale | È possibile utilizzare i criteri di accesso condizionale | App Microsoft Authenticator |
| **Criteri di accesso condizionale** | Se alcuni sono abilitati, non è possibile abilitare le impostazioni predefinite per la sicurezza | Se sono tutti disabilitati, è possibile abilitare le impostazioni predefinite per la sicurezza  | Specificato dall'utente durante la registrazione della MFA  |
||||

## <a name="let-your-users-reset-their-own-passwords"></a>Consentire agli utenti di reimpostare le loro password

La reimpostazione della password self-service consente agli utenti di reimpostare le proprie password senza bisogno dell'intervento del personale IT. Gli utenti possono reimpostare rapidamente le password in qualsiasi momento e da qualsiasi luogo. Per altre informazioni, vedere [Pianificare una distribuzione della reimpostazione della password self-service di Azure AD](/azure/active-directory/authentication/howto-sspr-deployment).

## <a name="sign-in-to-saas-apps-with-azure-ad"></a>Accedere alle app SaaS con Azure AD

Oltre a fornire agli utenti l'autenticazione basata sul cloud, Azure AD può anche essere il modo più semplice per proteggere tutte le app, che si trovino in locale, nel cloud di Microsoft o in un altro cloud. [Integrando le app in Azure AD](/azure/active-directory/manage-apps/plan-an-application-integration), i lavoratori ibridi possono individuare facilmente le applicazioni di cui hanno bisogno e accedere in tutta sicurezza.

## <a name="admin-technical-resources-for-mfa-and-identity"></a>Risorse tecniche per amministratori per MFA e identità

- [5 modi principali per abilitare il lavoro remoto in Azure AD](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/top-5-ways-your-azure-ad-can-help-you-enable-remote-work/ba-p/1144691)
- [Roadmap delle identità per Microsoft 365](../enterprise/identity-roadmap-microsoft-365.md)
- [Video di formazione su Azure Academy Azure AD](https://www.youtube.com/watch?v=pN8o0owHfI0&list=PL-V4YVm6AmwUFpC3rXr2i2piRQ708q_ia)

## <a name="results-of-step-1"></a>Risultati del Passaggio 1

Dopo la distribuzione della MFA, gli utenti:

- Devono utilizzare la MFA per gli accessi.
- Hanno completato il processo di registrazione della MFA e la usano per tutti gli accessi.
- Possono usare la reimpostazione della password self-service per reimpostare le proprie password.

## <a name="next-step"></a>Passaggio successivo

[![Passaggio2: fornire l'accesso remoto alle app e ai servizi locali](../media/empower-people-to-work-remotely/remote-workers-step-grid-2.png)](empower-people-to-work-remotely-remote-access.md)

Proseguire con [Passaggio 2](empower-people-to-work-remotely-remote-access.md) per fornire l'accesso remoto alle app e ai servizi locali.