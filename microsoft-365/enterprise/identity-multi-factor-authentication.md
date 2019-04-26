---
title: "Passaggio 4: Configurare l'autenticazione utente sicura"
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/17/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Comprendere e configurare l'autenticazione a più fattori per gli account utente.
ms.openlocfilehash: 44d878a347e7b01263f9ba3a82f6443f5710dc43
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32285468"
---
# <a name="step-4-configure-secure-user-authentication"></a>Passaggio 4: Configurare l'autenticazione utente sicura

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-mfa"></a>
## <a name="set-up-multi-factor-authentication"></a>Configurare l'autenticazione a più fattori

*Questo passaggio è facoltativo e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*

Con questo passaggio è possibile configurare l'autenticazione a più fattori (MFA) per aggiungere un secondo livello di protezione per l'accesso e le transazioni utente. La MFA richiede una verifica aggiuntiva dopo l'immissione della password da parte dell'utente. Senza la MFA, la password rimane l'unico metodo di verifica. Molte password potrebbero essere indovinate facilmente da un utente malintenzionato o condivise inavvertitamente con parti non attendibili.

Con la MFA, il secondo livello di sicurezza può essere:

- Un dispositivo personale e attendibile che non può essere oggetto di spoofing o duplicazioni, come per esempio uno smartphone.
- Un attributo biometrico, come per esempio un'impronta digitale.

Abilitando la MFA si configura il metodo secondario di autenticazione per ogni account utente. È necessario comunicare agli utenti che la MFA è abilitata, in modo che comprendano i requisiti, come l'utilizzo obbligatorio di uno smartphone per effettuare l'accesso, e possano effettuare l'accesso con esito positivo.

Per altre informazioni, vedere [Pianificare l'autenticazione a più fattori](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted).

>[!Note]
>In alcune applicazioni, come per esempio Microsoft Office 2010 o le applicazioni più vecchie di Apple Mail, non è possibile utilizzare la MFA. Per utilizzare queste app, sarà necessario utilizzare le "password dell'app" al posto della password tradizionale. La password dell'app consente di bypassare la MFA e continuare a lavorare. Per ulteriori informazioni sulle password dell'app, vedere [Creare una password dell'app per Office 365](https://support.office.com/article/Create-an-app-password-for-Office-365-3e7c860f-bda4-4441-a618-b53953ee1183).
>

|||
|:-------|:-----|
|![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guida al lab di test: autenticazione a più fattori](multi-factor-authentication-microsoft-365-test-environment.md) |
|||

Come checkpoint provvisorio, è possibile vedere i [criteri uscita](identity-exit-criteria.md#crit-identity-mfa) per questa sezione.



<a name="identity-ident-prot"></a>
## <a name="protect-against-credential-compromise"></a>Proteggere dalla compromissione delle credenziali

*Questo passaggio è facoltativo e si applica solo alla versione E5 di Microsoft 365 Enterprise*

In questa sezione verrà illustrato come configurare i criteri di protezione dalla compromissione delle credenziali, per cui l'autore di un attacco scopre nome e password dell'account di un utente per ottenere l'accesso ai servizi e ai dati cloud di un'organizzazione. Azure AD Identity Protection offre una serie di modi per impedire all'autore di un attacco di entrare in account e gruppi e, di conseguenza, alla maggior parte dei dati importanti.

Con Azure AD Identity Protection, è possibile:

|||
|:---------|:---------|
|Determinare e affrontare possibili vulnerabilità relative alle identità dell'organizzazione|Azure AD usa l'apprendimento automatico per rilevare anomalie e attività sospette, come ad esempio attività di accesso e conseguenti all'accesso. Usando questi dati, Identity Protection genera report e avvisi che permettono di valutare i problemi e intervenire.|
|Rilevare azioni sospette correlate alle identità dell'organizzazione e intervenire automaticamente|È possibile configurare criteri basati sul rischio che rispondono automaticamente a problemi rilevati quando un livello di rischio specificato è stato raggiunto. Tali criteri, in aggiunta ad altri controlli sull'accesso condizionale forniti da Azure Active Directory ed Enterprise Mobility + Security (EMS), possono bloccare l'accesso o attuare azioni correttive, come le reimpostazioni della password e richiedere l'autenticazione a più fattori per gli accessi successivi.|
|Esaminare gli incidenti sospetti e risolverli con azioni amministrative|È possibile esaminare gli eventi di rischio usando le informazioni sugli incidenti di sicurezza. I flussi di lavoro di base sono disponibili per tenere traccia delle analisi e per attuare azioni correttive, come le reimpostazioni delle password.|

Vedere [altre informazioni su Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).

Vedere i [passaggi per abilitare Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).

Al termine della procedura Azure AD Identity Protection è stato abilitato e può essere usato per:

- Far fronte a potenziali vulnerabilità relative alle identità.
- Rilevare possibili tentativi di violazione delle credenziali.
- Ricercare le cause e risolvere attività sospette relative alle identità.

|||
|:-------|:-----|
|![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guida al lab di test: Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md) |
|||

Come checkpoint provvisorio, è possibile vedere i [criteri uscita](identity-exit-criteria.md#crit-identity-ident-prot) per questa sezione.

## <a name="monitor-tenant-and-sign-in-activity"></a>Monitorare l'attività di tenant e di accesso

*Questo passaggio è facoltativo e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*

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
|![](./media/stepnumbers/Step5.png)| [Semplificare l'accesso per gli utenti](identity-password-reset.md) |

