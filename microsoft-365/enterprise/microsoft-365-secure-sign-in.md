---
title: Autenticazioni sicure degli utenti nel tenant di Microsoft 365
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/16/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Richiedere agli utenti di accedere in modo sicuro con l'autenticazione a più fattori (MFA) e altre funzionalità.
ms.openlocfilehash: 6c8f58e54ae21b4a5e1566dc72673e1d69152863
ms.sourcegitcommit: fdb5f9d865037c0ae23aae34a5c0f06b625b2f69
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/18/2020
ms.locfileid: "48132242"
---
# <a name="secure-user-sign-ins-to-your-microsoft-365-tenant"></a>Autenticazioni sicure degli utenti nel tenant di Microsoft 365

Per aumentare la sicurezza degli accessi degli utenti:

- Usare la protezione delle password di Azure Active Directory (Azure AD)
- Usare l'autenticazione a più fattori
- Distribuire criteri comuni di identità e accesso ai dispositivi.

## <a name="azure-ad-password-protection"></a>Azure AD Password Protection

La protezione delle password di Azure AD rileva e blocca le password deboli note e le loro varianti, e può anche bloccare altri elementi vulnerabili specifici delle organizzazioni. Gli elenchi predefiniti di password escluse globalmente sono applicate automaticamente a tutti gli utenti dei tenant di Azure AD. È possibile definire altre voci in un elenco di password escluse personalizzato. Quando gli utenti modificano o reimpostano le loro password, gli elenchi di password escluse sono controllati per applicare l'uso di password sicure.

Per altre informazioni, vedere [Configurare la protezione delle password di protezione di Azure AD](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad).

## <a name="mfa"></a>MFA

La MFA richiede che gli accessi utente siano soggetti a un'ulteriore verifica oltre alla password dell'account utente. Anche se un utente malintenzionato determina una password dell'account utente, deve anche essere in grado di rispondere a un'ulteriore verifica, ad esempio un SMS inviato a uno smartphone prima che venga concesso l'accesso.

![L'inserimento della password corretta e un'ulteriore verifica permettono di accedere](../media/empower-people-to-work-remotely/remote-workers-mfa.png)

Il primo passo per usare l'autenticazione MFA è di ***richiederla per tutti gli account amministratore***, noti anche come account privilegiati.

Oltre questo primo passaggio, Microsoft raccomanda vivamente l'autenticazione a più fattori per tutti gli utenti.

Sono disponibili tre modi per richiedere agli amministratori o agli utenti di utilizzare la MFA in base al piano Microsoft 365.

| Piano | Consiglio |
|---------|---------|
|Tutti i piani di Microsoft 365 (senza licenze di Azure AD Premium P1 o P2)     |[Abilitare le impostazioni predefinite di sicurezza in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults). Le impostazioni predefinite di sicurezza in Azure AD includono la MFA per utenti e amministratori.   |
|Microsoft 365 E3 (include le licenze di Azure AD Premium P1)     | Usare i [criteri comuni di accesso condizionale](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) per configurare i criteri seguenti: <br>- [Richiedere la MFA per amministratori](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa) <br>- [Richiedere la MFA per tutti gli utenti](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa) <br> - [Bloccare l'autenticazione legacy](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)       |
|Microsoft 365 E5 (include le licenze di Azure AD Premium P2)     | Sfruttando Azure AD Identity Protection, iniziare a implementare il [set raccomandato di accesso condizionale e criteri correlati](../enterprise/identity-access-policies.md) di Microsoft creando questi due criteri:<br> - [Richiedere la MFA quando il rischio di accesso è considerato *medio* o *elevato*](../enterprise/identity-access-policies.md#require-mfa-based-on-sign-in-risk) <br>- [Gli utenti a rischio elevato devono modificare la password](../enterprise/identity-access-policies.md#high-risk-users-must-change-password)       |
| | |

### <a name="security-defaults"></a>Impostazioni predefinite per la sicurezza

Le impostazioni predefinite di sicurezza sono una nuova funzionalità per gli abbonamenti a pagamento o di valutazione di Microsoft 365 e Office 365 creati dopo il 21 ottobre 2019. Questi abbonamenti hanno impostazioni predefinite di sicurezza attivate, che ***richiedono a tutti gli utenti di utilizzare la MFA con l'app Microsoft Authenticator***.
 
Gli utenti hanno 14 giorni per registrarsi per la MFA con l'app Microsoft Authenticator dai propri smartphone, periodo che inizia dalla prima volta che accedono dopo aver abilitato le impostazioni predefinite di sicurezza. Trascorsi 14 giorni, l'utente non sarà in grado di accedere fino al completamento della registrazione della MFA.

Le impostazioni di sicurezza predefinite garantiscono che tutte le organizzazioni dispongano di un livello base di sicurezza per l'accesso degli utenti abilitato per impostazione predefinita. È possibile disabilitare le impostazioni predefinite di sicurezza a favore della MFA con criteri di accesso condizionale o per singoli account.

Per altre informazioni, vedere questa [panoramica delle impostazioni predefinite di sicurezza](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).

### <a name="conditional-access-policies"></a>Criteri di accesso condizionale

I criteri di accesso condizionale sono un insieme di regole che specificano le condizioni in base alle quali gli accessi vengono valutati e l'accesso viene consentito. Ad esempio, è possibile creare un criterio di accesso condizionale che indichi:

- Se il nome dell'account utente corrisponde a un membro di un gruppo per utenti a cui sono assegnati i ruoli di amministratore di Exchange, utenti, password, sicurezza, SharePoint o globale, richiedere la MFA prima di consentire l'accesso.

Questo criterio consente di richiedere l'autenticazione a più fattori in base all'appartenenza al gruppo, anziché configurare i singoli account utente per l'autenticazione a più fattori quando vengono assegnati o non assegnati tramite questi ruoli di amministratore.

È inoltre anche utilizzare i criteri di accesso condizionale per funzionalità più avanzate, come la necessità di eseguire l'accesso da un dispositivo conforme, come il proprio portatile con Windows 10.

L'accesso condizionale richiede licenze di Azure AD Premium P1, che sono incluse con Microsoft 365 E3 ed E5.

Per altre informazioni, vedere questa [sintesi dell'accesso condizionale](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).

### <a name="using-these-methods-together"></a>Usare questi metodi insieme

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

## <a name="identity-and-device-access-policies"></a>Criteri di identità e accesso ai dispositivi

Le impostazioni e i criteri di accesso dei dispositivi e delle identità sono funzionalità raccomandate e la loro configurazione, combinata con i criteri di accesso condizionale, Intune, e Azure AD Identity Protection, determina se una specifica richiesta di accesso debba essere accolta e a quali condizioni.  Questa determinazione è basata sull'account utente autenticato, il dispositivo usato, l'app usata dall'utente per accedere, la posizione da cui viene inviata la richiesta di accesso, e una valutazione del rischio della richiesta. Questa funzionalità garantisce che solo gli utenti e i dispositivi autorizzati possano accedere alle risorse cruciali dell'utente.

>[!Note]
>Azure AD Identity Protection richiede licenze di Azure AD Premium P2, che sono incluse in Microsoft 365 E5.
>

I criteri di identità e accesso ai dispositivi sono definiti per essere usati in tre livelli: 

- La protezione di base è il livello minimo di sicurezza per le identità e i dispositivi che accedono ad app e dati.
- La protezione sensibile garantisce una maggiore sicurezza per dati specifici. Le identità e i dispositivi sono soggetti a requisiti di sicurezza e integrità dei dispositivi più rigorosi.
- La protezione per ambienti con dati altamente regolamentati o classificati è di solito centrata su piccole quantità di dati altamente classificati, che contengono segreti commerciali o sono sottoposti a normative sui dati. Le identità e i dispositivi sono soggetti a requisiti di sicurezza e integrità dei dispositivi molto più rigorosi. 

Questi livelli, e le loro configurazioni corrispondenti, offrono livelli costanti di protezione per tutti i dati, le identità e i dispositivi.

Microsoft raccomanda vivamente di configurare e distribuire i criteri di identità e accesso ai dispositivi nell'organizzazione, incluse le impostazioni specifiche di Microsoft Teams, Exchange Online e SharePoint. Per altre informazioni, vedere [Configurazioni di identità e accesso dei dispositivi](microsoft-365-policies-configurations.md).

<!--

## Let your users reset their own passwords

Self-Service Password Reset (SSPR) enables users to reset their own passwords without impacting IT staff. Users can quickly reset their passwords at any time and from any place. Watch [this video](https://go.microsoft.com/fwlink/?linkid=2128524) to set up SSPR.

## Sign in to SaaS apps with Azure AD

In addition to providing cloud authentication for users, Azure AD can also be your central way to secure all your apps, whether they’re on-premises, in Microsoft’s cloud, or in another cloud. By [integrating your apps into Azure AD](https://docs.microsoft.com/azure/active-directory/manage-apps/plan-an-application-integration), you can make it easy for your users to discover the applications they need and sign into them securely.

## Results of deployment of secure sign-ins

After deployment of MFA, your users:

- Are required to use MFA for sign-ins.
- Have completed the MFA registration process and are using MFA for all sign-ins.
- Can use SSPR to reset their own passwords.

- [Plan an Azure AD self-service password reset deployment](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment)

--> 

## <a name="admin-technical-resources-for-mfa-and-secure-sign-ins"></a>Risorse tecniche per amministratori per MFA e autenticazioni sicure

- [MFA per Microsoft 365](../admin/security-and-compliance/multi-factor-authentication-microsoft-365.md)
- [Roadmap delle identità per Microsoft 365](identity-roadmap-microsoft-365.md)
- [Video di formazione su Azure Academy Azure AD](https://www.youtube.com/watch?v=pN8o0owHfI0&list=PL-V4YVm6AmwUFpC3rXr2i2piRQ708q_ia)
- [Configurare i criteri di registrazione dell'autenticazione a più fattori di Azure](https://docs.microsoft.com/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy)
- [Configurazioni di identità e accesso dei dispositivi](microsoft-365-policies-configurations.md)

