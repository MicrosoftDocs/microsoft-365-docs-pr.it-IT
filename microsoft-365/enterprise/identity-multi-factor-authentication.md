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
# <a name="step-4-configure-secure-user-authentication"></a><span data-ttu-id="bb40d-103">Passaggio 4: Configurare l'autenticazione utente sicura</span><span class="sxs-lookup"><span data-stu-id="bb40d-103">Step 4: Configure secure user authentication</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-mfa"></a>
## <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="bb40d-104">Configurare l'autenticazione a più fattori</span><span class="sxs-lookup"><span data-stu-id="bb40d-104">Set up multi-factor authentication.</span></span>

<span data-ttu-id="bb40d-105">*Questo passaggio è facoltativo e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="bb40d-105">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="bb40d-p101">Con questo passaggio è possibile configurare l'autenticazione a più fattori (MFA) per aggiungere un secondo livello di protezione per l'accesso e le transazioni utente. La MFA richiede una verifica aggiuntiva dopo l'immissione della password da parte dell'utente. Senza la MFA, la password rimane l'unico metodo di verifica. Molte password potrebbero essere indovinate facilmente da un utente malintenzionato o condivise inavvertitamente con parti non attendibili.</span><span class="sxs-lookup"><span data-stu-id="bb40d-p101">In this step, you'll set up multi-factor authentication (MFA) to add a second layer of security to user sign-ins and transactions. MFA requires an additional verification method after users have correctly entered their password. Without MFA, the password is the only verification method. The problem with passwords is that many of them are easily guessed by an attacker or unknowingly shared with untrusted parties.</span></span>

<span data-ttu-id="bb40d-110">Con la MFA, il secondo livello di sicurezza può essere:</span><span class="sxs-lookup"><span data-stu-id="bb40d-110">With MFA, the second layer of security can be:</span></span>

- <span data-ttu-id="bb40d-111">Un dispositivo personale e attendibile che non può essere oggetto di spoofing o duplicazioni, come per esempio uno smartphone.</span><span class="sxs-lookup"><span data-stu-id="bb40d-111">A personal and trusted device that isn’t easily spoofed or duplicated, such as a smart phone.</span></span>
- <span data-ttu-id="bb40d-112">Un attributo biometrico, come per esempio un'impronta digitale.</span><span class="sxs-lookup"><span data-stu-id="bb40d-112">A biometric attribute, such as a fingerprint.</span></span>

<span data-ttu-id="bb40d-p102">Abilitando la MFA si configura il metodo secondario di autenticazione per ogni account utente. È necessario comunicare agli utenti che la MFA è abilitata, in modo che comprendano i requisiti, come l'utilizzo obbligatorio di uno smartphone per effettuare l'accesso, e possano effettuare l'accesso con esito positivo.</span><span class="sxs-lookup"><span data-stu-id="bb40d-p102">You'll enable MFA and configure the secondary authentication method on a per-user account basis. Make sure to let users know that MFA is being enabled so they understand the requirements, such as mandatory use of a smart phone to sign in, and can sign in successfully.</span></span>

<span data-ttu-id="bb40d-115">Per altre informazioni, vedere [Pianificare l'autenticazione a più fattori](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted).</span><span class="sxs-lookup"><span data-stu-id="bb40d-115">For more information, see [Plan for multi-factor authentication for Office 365 Deployments](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted).</span></span>

>[!Note]
><span data-ttu-id="bb40d-p103">In alcune applicazioni, come per esempio Microsoft Office 2010 o le applicazioni più vecchie di Apple Mail, non è possibile utilizzare la MFA. Per utilizzare queste app, sarà necessario utilizzare le "password dell'app" al posto della password tradizionale. La password dell'app consente di bypassare la MFA e continuare a lavorare. Per ulteriori informazioni sulle password dell'app, vedere [Creare una password dell'app per Office 365](https://support.office.com/article/Create-an-app-password-for-Office-365-3e7c860f-bda4-4441-a618-b53953ee1183).</span><span class="sxs-lookup"><span data-stu-id="bb40d-p103">In some applications, such as Microsoft Office 2010 or older and Apple Mail, you can’t use MFA. To use these apps, you’ll need to use “app passwords” in place of your traditional password. The app password allows the app to bypass MFA and continue working. To learn more about app passwords, see [Create an app password for Office 365](https://support.office.com/article/Create-an-app-password-for-Office-365-3e7c860f-bda4-4441-a618-b53953ee1183).</span></span>
>

|||
|:-------|:-----|
|![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="bb40d-121">Guida al lab di test: autenticazione a più fattori</span><span class="sxs-lookup"><span data-stu-id="bb40d-121">Test Lab Guide: Multi-factor authentication</span></span>](multi-factor-authentication-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="bb40d-122">Come checkpoint provvisorio, è possibile vedere i [criteri uscita](identity-exit-criteria.md#crit-identity-mfa) per questa sezione.</span><span class="sxs-lookup"><span data-stu-id="bb40d-122">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-mfa) for this step.</span></span>



<a name="identity-ident-prot"></a>
## <a name="protect-against-credential-compromise"></a><span data-ttu-id="bb40d-123">Proteggere dalla compromissione delle credenziali</span><span class="sxs-lookup"><span data-stu-id="bb40d-123">Protect against credential compromise</span></span>

<span data-ttu-id="bb40d-124">*Questo passaggio è facoltativo e si applica solo alla versione E5 di Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="bb40d-124">*This step is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="bb40d-125">In questa sezione verrà illustrato come configurare i criteri di protezione dalla compromissione delle credenziali, per cui l'autore di un attacco scopre nome e password dell'account di un utente per ottenere l'accesso ai servizi e ai dati cloud di un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="bb40d-125">In this step, you'll learn how to configure policies that protect against credential compromise, where an attacker determines a user’s account name and password to gain access to an organization’s cloud services and data. Azure AD Identity Protection provides a number of ways to help prevent an attacker from moving laterally through your accounts and groups, and subsequently, to your most valuable data.</span></span> <span data-ttu-id="bb40d-126">Azure AD Identity Protection offre una serie di modi per impedire all'autore di un attacco di entrare in account e gruppi e, di conseguenza, alla maggior parte dei dati importanti.</span><span class="sxs-lookup"><span data-stu-id="bb40d-126">In this step, you'll learn how to configure policies that protect against credential compromise, where an attacker determines a user’s account name and password to gain access to an organization’s cloud services and data. Azure AD Identity Protection provides a number of ways to help prevent an attacker from moving laterally through your accounts and groups, and subsequently, to your most valuable data.</span></span>

<span data-ttu-id="bb40d-127">Con Azure AD Identity Protection, è possibile:</span><span class="sxs-lookup"><span data-stu-id="bb40d-127">With Azure AD Identity Protection, you can:</span></span>

|||
|:---------|:---------|
|<span data-ttu-id="bb40d-128">Determinare e affrontare possibili vulnerabilità relative alle identità dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="bb40d-128">Determine and address potential vulnerabilities in your organization’s identities</span></span>|<span data-ttu-id="bb40d-p105">Azure AD usa l'apprendimento automatico per rilevare anomalie e attività sospette, come ad esempio attività di accesso e conseguenti all'accesso. Usando questi dati, Identity Protection genera report e avvisi che permettono di valutare i problemi e intervenire.</span><span class="sxs-lookup"><span data-stu-id="bb40d-p105">Azure AD uses machine learning to detect anomalies and suspicious activity, such as sign-ins and post-sign-in activities. Using this data, Identity Protection generates reports and alerts that help you evaluate the issues and take action.</span></span>|
|<span data-ttu-id="bb40d-131">Rilevare azioni sospette correlate alle identità dell'organizzazione e intervenire automaticamente</span><span class="sxs-lookup"><span data-stu-id="bb40d-131">Detect suspicious actions that are related to your organization’s identities and respond to them automatically</span></span>|<span data-ttu-id="bb40d-p106">È possibile configurare criteri basati sul rischio che rispondono automaticamente a problemi rilevati quando un livello di rischio specificato è stato raggiunto. Tali criteri, in aggiunta ad altri controlli sull'accesso condizionale forniti da Azure Active Directory ed Enterprise Mobility + Security (EMS), possono bloccare l'accesso o attuare azioni correttive, come le reimpostazioni della password e richiedere l'autenticazione a più fattori per gli accessi successivi.</span><span class="sxs-lookup"><span data-stu-id="bb40d-p106">You can configure risk-based policies that automatically respond to detected issues when a specified risk level has been reached. These policies, in addition to other conditional access controls provided by Azure Active Directory and Enterprise Mobility + Security (EMS), can either automatically block access or take corrective actions, including password resets and requiring multi-factor authentication for subsequent sign-ins.</span></span>|
|<span data-ttu-id="bb40d-134">Esaminare gli incidenti sospetti e risolverli con azioni amministrative</span><span class="sxs-lookup"><span data-stu-id="bb40d-134">Investigate suspicious incidents and resolve them with administrative actions</span></span>|<span data-ttu-id="bb40d-p107">È possibile esaminare gli eventi di rischio usando le informazioni sugli incidenti di sicurezza. I flussi di lavoro di base sono disponibili per tenere traccia delle analisi e per attuare azioni correttive, come le reimpostazioni delle password.</span><span class="sxs-lookup"><span data-stu-id="bb40d-p107">You can investigate risk events using information about the security incident. Basic workflows are available to track investigations and initiate remediation actions, such as password resets.</span></span>|

<span data-ttu-id="bb40d-137">Vedere [altre informazioni su Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).</span><span class="sxs-lookup"><span data-stu-id="bb40d-137">See [more information about Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).</span></span>

<span data-ttu-id="bb40d-138">Vedere i [passaggi per abilitare Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).</span><span class="sxs-lookup"><span data-stu-id="bb40d-138">See the [steps to enable Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).</span></span>

<span data-ttu-id="bb40d-139">Al termine della procedura Azure AD Identity Protection è stato abilitato e può essere usato per:</span><span class="sxs-lookup"><span data-stu-id="bb40d-139">The results of this step are that you've enabled Azure AD Identity protection and you are using it to:</span></span>

- <span data-ttu-id="bb40d-140">Far fronte a potenziali vulnerabilità relative alle identità.</span><span class="sxs-lookup"><span data-stu-id="bb40d-140">Address potential identity vulnerabilities.</span></span>
- <span data-ttu-id="bb40d-141">Rilevare possibili tentativi di violazione delle credenziali.</span><span class="sxs-lookup"><span data-stu-id="bb40d-141">Detect possible credential compromise attempts.</span></span>
- <span data-ttu-id="bb40d-142">Ricercare le cause e risolvere attività sospette relative alle identità.</span><span class="sxs-lookup"><span data-stu-id="bb40d-142">Investigate and address ongoing suspicious identity incidents.</span></span>

|||
|:-------|:-----|
|![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="bb40d-144">Guida al lab di test: Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="bb40d-144">Test Lab Guide: Azure AD Identity Protection</span></span>](azure-ad-identity-protection-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="bb40d-145">Come checkpoint provvisorio, è possibile vedere i [criteri uscita](identity-exit-criteria.md#crit-identity-ident-prot) per questa sezione.</span><span class="sxs-lookup"><span data-stu-id="bb40d-145">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-ident-prot) for this step.</span></span>

## <a name="monitor-tenant-and-sign-in-activity"></a><span data-ttu-id="bb40d-146">Monitorare l'attività di tenant e di accesso</span><span class="sxs-lookup"><span data-stu-id="bb40d-146">Monitor tenant and sign-in activity</span></span>

<span data-ttu-id="bb40d-147">*Questo passaggio è facoltativo e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="bb40d-147">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="bb40d-p108">In questo passaggio, è possibile rivedere le attività dei log di controllo e le attività di accesso utilizzando la creazione di report di Azure AD. Sono disponibili due tipi di report.</span><span class="sxs-lookup"><span data-stu-id="bb40d-p108">In this step, you'll review audit logs and sign-in activity using Azure AD reporting. Two types of reports are available.</span></span>

<span data-ttu-id="bb40d-p109">Il **Report delle attività di log di controllo** registra la storia di ogni attività eseguita nel tenant di Azure AD. Questo report può fornire risposte a domande come:</span><span class="sxs-lookup"><span data-stu-id="bb40d-p109">The **Audit logs activity report** records the history of every task performed in your Azure AD tenant. This report answers questions like:</span></span>

- <span data-ttu-id="bb40d-152">Chi ha aggiunto un membro al gruppo amministratore?</span><span class="sxs-lookup"><span data-stu-id="bb40d-152">Who added someone to an admin group?</span></span>
- <span data-ttu-id="bb40d-153">Quali utenti hanno effettuato l'accesso in una determinata app?</span><span class="sxs-lookup"><span data-stu-id="bb40d-153">Which users are signing into a specific app?</span></span>
- <span data-ttu-id="bb40d-154">Quante reimpostazioni della password sono state eseguite?</span><span class="sxs-lookup"><span data-stu-id="bb40d-154">How many password resets are happening?</span></span>

<span data-ttu-id="bb40d-p110">Il **Report delle attività di accesso** registra gli utenti che hanno eseguito le attività riportate nei report dei log di controllo. Questo report può fornire risposte a domande come:</span><span class="sxs-lookup"><span data-stu-id="bb40d-p110">The **Sign-ins activity report** records who performed the tasks reported by the audit logs report. This report answers questions like:</span></span>

- <span data-ttu-id="bb40d-157">Qual è il criterio di accesso per un utente specifico sotto esame?</span><span class="sxs-lookup"><span data-stu-id="bb40d-157">For a specific user under investigation, what is their sign-in pattern?</span></span>
- <span data-ttu-id="bb40d-158">Qual'è il numero degli accessi durante un giorno, una settimana o un mese?</span><span class="sxs-lookup"><span data-stu-id="bb40d-158">What is my volume of sign-ins over a day, week, or month?</span></span>
- <span data-ttu-id="bb40d-159">Quanti tentativi di accesso non hanno avuto esito positivo e per quali account si è verificata questa occorrenza?</span><span class="sxs-lookup"><span data-stu-id="bb40d-159">How many of these sign-in attempts were not successful, and for which accounts?</span></span>

<span data-ttu-id="bb40d-160">Per ulteriori informazioni sui report e su come accedere ad essi, vedere [Creazione di report di Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="bb40d-160">For more information about the reports and how to access them, see [Azure Active Directory reporting](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-azure-portal).</span></span>

<span data-ttu-id="bb40d-161">Il risultato di questo passaggio è acquisire consapevolezza riguardo tali report e comprendere come utilizzarli per comprendere gli eventi e le attività di Azure AD a scopo di pianificazione e sicurezza.</span><span class="sxs-lookup"><span data-stu-id="bb40d-161">As a result of this step, you'll gain awareness of these reports and an understanding of how you can use them to gain insights on Azure AD events and activities for planning and security purposes.</span></span>



## <a name="next-step"></a><span data-ttu-id="bb40d-162">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="bb40d-162">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step5.png)| [<span data-ttu-id="bb40d-163">Semplificare l'accesso per gli utenti</span><span class="sxs-lookup"><span data-stu-id="bb40d-163">Simplify access for users</span></span>](identity-password-reset.md) |

