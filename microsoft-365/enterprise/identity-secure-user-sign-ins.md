---
title: 'Passaggio 3: proteggere e gestire gli accessi degli utenti'
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
description: È possibile rendere più sicuri gli accessi degli utenti ai dispositivi Windows e a Microsoft 365.
ms.openlocfilehash: c1379cfdd65204a27c8147ade8c8c8704e441f1f
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2019
ms.locfileid: "40801731"
---
# <a name="step-3-secure-and-manage-your-user-sign-ins"></a>Passaggio 3: proteggere e gestire gli accessi degli utenti

![Fase 2 - Identità](./media/deploy-foundation-infrastructure/identity_icon-small.png)


<a name="identity-windows-hello"></a>
## <a name="use-windows-hello-for-business"></a>Usare Windows Hello for Business

*Questo passaggio è facoltativo e si applica alle versioni E3 ed E5 di Microsoft 365*

Windows Hello for Business in Windows 10 Enterprise sostituisce le password con l'autenticazione complessa a due fattori durante l'accesso a un dispositivo Windows. I due fattori sono un nuovo tipo di credenziale utente che è associato a un dispositivo e a una biometria o a un PIN.

Per altre informazioni, vedere [Panoramica di Windows Hello for Business](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview).


<a name="identity-mfa"></a>
## <a name="set-up-azure-multi-factor-authentication"></a>Impostare l’autenticazione a più fattori di Azure

*Questo passaggio è facoltativo e si applica alle versioni E3 ed E5 di Microsoft 365*

Durante questo passaggio, verrà impostata l’autenticazione a più fattori di Azure per aggiungere un secondo livello di sicurezza agli accessi e alle transazioni degli utenti. L'autenticazione a più fattori richiede un altro metodo di verifica dopo che gli utenti hanno immesso correttamente la password. Senza l’autenticazione a più fattori, la password è l'unico metodo di verifica. Il problema delle password è che molte di esse possono essere indovinate facilmente da un utente malintenzionato o condivise in modo inconsapevolmente con parti non affidabili.

Con la MFA, il secondo livello di sicurezza può essere:

- Un dispositivo personale e attendibile che non può essere oggetto di spoofing o duplicazioni, come per esempio uno smartphone.
- Un attributo biometrico, come per esempio un'impronta digitale.

È possibile abilitare la MFA e configurare il metodo di autenticazione secondario con i [criteri di accesso condizionale](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access), che consentono di usare i gruppi di Azure Active Directory (Azure AD) per distribuire la MFA a set di utenti specifici, ad esempio utenti pilota, aree geografiche o dipartimenti. È necessario comunicare agli utenti che la MFA è abilitata, in modo che ne comprendano i requisiti, come l'utilizzo obbligatorio di uno smartphone per effettuare l'accesso, e che possano effettuare l'accesso con esito positivo. 

Per ulteriori informazioni, consultare [Pianificazione di una distribuzione di Azure Multi-Factor Authentication basata su cloud](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted).

|||
|:-------|:-----|
|![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guida al lab di test: autenticazione a più fattori di Azure](multi-factor-authentication-microsoft-365-test-environment.md) |
|||

Come checkpoint provvisorio, è possibile vedere i [criteri uscita](identity-exit-criteria.md#crit-identity-mfa) per questa sezione.

<a name="identity-ident-prot"></a>
## <a name="protect-against-credential-compromise"></a>Proteggere dalla compromissione delle credenziali

*Questo passaggio è facoltativo e si applica solo alla versione E5 di Microsoft 365 Enterprise*

In questa sezione verrà illustrato come configurare i criteri di protezione dalla compromissione delle credenziali, per cui l'autore di un attacco scopre nome e password dell'account di un utente per ottenere l'accesso ai servizi e ai dati cloud di un'organizzazione. Azure AD Identity Protection include diversi modi per impedire a un utente malintenzionato di compromettere le credenziali di un account utente.

Con Azure AD Identity Protection, è possibile:

|||
|:---------|:---------|
|Determinare e affrontare possibili vulnerabilità relative alle identità dell'organizzazione|Azure AD usa l'apprendimento automatico per rilevare anomalie e attività sospette, come le attività di accesso e conseguenti all’accesso. Con questi dati, Azure AD Identity Protection genera report e avvisi che consentono di valutare i problemi e intervenire.|
|Rilevare azioni sospette correlate alle identità dell'organizzazione e intervenire automaticamente|È possibile configurare criteri basati sul rischio che rispondano automaticamente ai problemi rilevati quando viene raggiunto un livello di rischio specificato. Questi criteri, con altri controlli di accesso condizionale forniti da Azure AD e Microsoft Intune, possono bloccare automaticamente l’accesso o avviare azioni di correzione, incluse la reimpostazione della password e la richiesta dell'autenticazione a più fattori di Azure per gli accessi successivi.|
|Esaminare gli incidenti sospetti e risolverli con azioni amministrative|È possibile esaminare gli eventi di rischio usando le informazioni sugli incidenti di sicurezza. I flussi di lavoro di base sono disponibili per tenere traccia delle analisi e per attuare azioni correttive, come le reimpostazioni delle password.|

Vedere [altre informazioni su Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).

Vedere i [passaggi per abilitare Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).

Al termine della procedura Azure AD Identity Protection è stato abilitato e può essere usato per:

- Far fronte a potenziali vulnerabilità delle identità.
- Rilevare possibili tentativi di violazione delle credenziali.
- Ricercare le cause e risolvere attività sospette relative alle identità.

|||
|:-------|:-----|
|![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guida al lab di test: Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md) |
|||

Come checkpoint provvisorio, è possibile vedere i [criteri uscita](identity-exit-criteria.md#crit-identity-ident-prot) per questa sezione.

|||
|:-------|:-----|
|![Passaggio 4](./media/stepnumbers/Step4.png)| [Aggiungere gli account utente](identity-add-user-accounts.md) |
