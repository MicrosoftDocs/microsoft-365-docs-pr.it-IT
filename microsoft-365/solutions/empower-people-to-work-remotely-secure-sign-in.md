---
title: Passaggio 1. Aumentare la sicurezza di accesso per i lavoratori remoti con la MFA.
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 05/01/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
ms.custom:
- M365solutions
description: È necessario che l'utente remoto acceda con l'autenticazione a più fattori (MFA).
ms.openlocfilehash: dfb4262c05399e1c5add9b151c42c143ac723a7d
ms.sourcegitcommit: 7f307b4f583b602f11f69adae46d7f3bf6982c65
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2020
ms.locfileid: "44066128"
---
# <a name="step-1-increase-sign-in-security-for-remote-workers-with-mfa"></a>Passaggio 1. Aumentare la sicurezza di accesso per i lavoratori remoti con la MFA.

Per aumentare la sicurezza degli accessi dei lavoratori remoti, utilizzare l'autenticazione a più fattori (MFA). La MFA richiede che gli accessi utente siano soggetti a un'ulteriore verifica oltre alla password dell'account utente. Anche se un utente malintenzionato determina una password dell'account utente, deve anche essere in grado di rispondere a un'ulteriore verifica, ad esempio un SMS inviato a uno smartphone prima che venga concesso l'accesso.

![L'inserimento della password corretta e un'ulteriore verifica permettono di accedere](../media/empower-people-to-work-remotely/remote-workers-mfa.png)

Per tutti gli utenti, inclusi i lavoratori remoti e in particolare gli amministratori, Microsoft consiglia vivamente la MFA.

Sono disponibili tre modi per richiedere agli utenti di utilizzare la MFA in base al piano Microsoft 365.

|Piano  |Consiglio  |
|---------|---------|
|Piani di Microsoft 365 (senza Azure AD Premium P1 o P2)     |[Abilitare le impostazioni predefinite di sicurezza in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults). Le impostazioni predefinite di sicurezza in Azure AD includono la MFA per utenti e amministratori.   |
|Microsoft 365 E3 (con Azure AD Premium P1)     | Usare i [criteri comuni di accesso condizionale](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) per configurare i criteri seguenti: <br>- [Richiedere la MFA per amministratori](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa) <br>- [Richiedere la MFA per tutti gli utenti](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa) <br> - [Bloccare l'autenticazione legacy](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)       |
|Microsoft 365 E5 (con Azure AD Premium P2)     | Sfruttando Azure AD Identity Protection, iniziare a implementare il [set raccomandato di accesso condizionale e criteri correlati](../enterprise/identity-access-policies.md) di Microsoft creando questi due criteri:<br> - [Richiedere la MFA quando il rischio di accesso è considerato *medio* o *elevato*](../enterprise/identity-access-policies.md#require-mfa-based-on-sign-in-risk) <br>- [Bloccare i client che non supportano l'autenticazione moderna](../enterprise/identity-access-policies.md#block-clients-that-dont-support-modern-authentication)<br>- [Gli utenti a rischio elevato devono modificare la password](../enterprise/identity-access-policies.md#high-risk-users-must-change-password)       |
| | |

## <a name="security-defaults"></a>Impostazioni predefinite per la sicurezza

Le impostazioni predefinite di sicurezza sono una nuova funzionalità per gli abbonamenti a pagamento o di valutazione di Microsoft 365 e Office 365 creati dopo il 21 ottobre 2019. Questi abbonamenti hanno impostazioni predefinite di sicurezza attivate, che ***richiedono a tutti gli utenti di utilizzare la MFA con l'app Microsoft Authenticator***.
 
Gli utenti hanno 14 giorni per registrarsi per la MFA con l'app Microsoft Authenticator dai propri smartphone, periodo che inizia dalla prima volta che accedono dopo aver abilitato le impostazioni predefinite di sicurezza. Trascorsi 14 giorni, l'utente non sarà in grado di accedere fino al completamento della registrazione della MFA.

Le impostazioni di sicurezza predefinite garantiscono che tutte le organizzazioni dispongano di un livello base di sicurezza per l'accesso degli utenti abilitato per impostazione predefinita. È possibile disabilitare le impostazioni predefinite di sicurezza a favore della MFA con criteri di accesso condizionale o per singoli account.

Per altre informazioni, vedere questa [panoramica delle impostazioni predefinite di sicurezza](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).

## <a name="conditional-access-policies"></a>Criteri di accesso condizionale

I criteri di accesso condizionale sono un insieme di regole che specificano le condizioni in base alle quali gli accessi vengono valutati e consentiti. Ad esempio, è possibile creare un criterio di accesso condizionale che indichi:

- Se il nome dell'account utente è per un utente che è un amministratore di Exchange, utente, password, sicurezza, SharePoint o globale, richiedere la MFA prima di consentire l'accesso.

Questo criterio risulta più semplice che cercare di ricordare di configurare i singoli account utente per la MFA quando vengono aggiunti o rimossi da questi ruoli di amministratore.

È inoltre anche utilizzare i criteri di accesso condizionale per funzionalità più avanzate, come la necessità di eseguire l'accesso da un dispositivo conforme, come il proprio portatile con Windows 10.

L'accesso condizionale richiede Azure AD Premium P1, incluso in Microsoft 365 E3 ed E5.

Per altre informazioni, vedere questa [panoramica dell'accesso condizionale](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).

## <a name="azure-ad-identity-protection-policies"></a>Criteri di Azure AD Identity Protection

I criteri di Azure AD Identity Protection sono un insieme di regole che specificano le condizioni in base alle quali gli accessi vengono valutati e consentiti. Ad esempio, è possibile creare un criterio di Azure AD Identity Protection che indichi:

- Se il rischio di accesso è determinato da un rischio medio o alto, l'utente deve utilizzare la MFA per accedere.

Azure AD Identity Protection richiede Azure AD Premium P2, incluso in Microsoft 365 E5.

Per ulteriori informazioni, vedere questa [panoramica di Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection).

## <a name="using-these-methods-together"></a>Usare questi metodi insieme

Tenere presente quanto segue:

- Non è possibile abilitare le impostazioni predefinite di sicurezza se sono abilitati criteri di accesso condizionale.
- Non è possibile abilitare alcun criterio di accesso condizionale se sono abilitate le impostazioni predefinite di sicurezza.

Se le impostazioni predefinite di sicurezza sono abilitate, a tutti i nuovi utenti viene richiesta la registrazione della MFA e l'utilizzo dell'app Microsoft Authenticator. 

Questa tabella mostra i risultati dell'abilitazione della MFA con impostazioni predefinite di sicurezza, criteri di accesso condizionale e impostazioni dell'account per utente.

|| Abilitato | Disattivato | Metodo di autenticazione secondario |
|:-------|:-----|:-------|:-------|
| **Impostazioni predefinite per la sicurezza**  | Non è possibile utilizzare i criteri di accesso condizionale | È possibile utilizzare i criteri di accesso condizionale | App Microsoft Authenticator |
| **Criteri di accesso condizionale** | Se alcuni sono abilitati, non è possibile abilitare le impostazioni predefinite per la sicurezza | Se non tutti sono abilitati, è possibile abilitare le impostazioni predefinite per la sicurezza  | Specificato dall'utente durante la registrazione della MFA  |
||||

## <a name="admin-training-and-technical-resources-for-mfa-and-identity"></a>Formazione e risorse tecniche per amministratori per MFA e identità

- [Pianificazione della MFA per Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/multi-factor-authentication-plan)
- [5 modi principali per abilitare il lavoro remoto in Azure AD](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/top-5-ways-your-azure-ad-can-help-you-enable-remote-work/ba-p/1144691)
- [Pianificare e distribuire l'infrastruttura di gestione delle identità di Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/identity-infrastructure?view=o365-worldwide#plan-and-deploy-your-microsoft-365-enterprise-identity-infrastructure)
- [Video di formazione su Azure Academy Azure AD](https://www.youtube.com/watch?v=pN8o0owHfI0&list=PL-V4YVm6AmwUFpC3rXr2i2piRQ708q_ia)
- [Configurare i criteri di registrazione dell'autenticazione a più fattori di Azure](https://docs.microsoft.com/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy)

## <a name="results-of-step-1"></a>Risultati del Passaggio 1

Dopo la distribuzione della MFA, gli utenti:

- Devono utilizzare la MFA per gli accessi.
- Devono aver completato il processo di registrazione della MFA e usarla per tutti gli accessi.

## <a name="next-step"></a>Passaggio successivo

Proseguire con [Passaggio 2](empower-people-to-work-remotely-remote-access.md) per fornire l'accesso remoto alle app e ai servizi locali.
