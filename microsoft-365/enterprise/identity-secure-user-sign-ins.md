---
title: 'Passaggio 3: proteggere e gestire gli accessi degli utenti'
f1.keywords:
- NOCSH
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
ms.openlocfilehash: c541f5b74fe3ea6e94b002212f21ec8645e8e87e
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42067293"
---
# <a name="step-3-secure-and-manage-your-user-sign-ins"></a><span data-ttu-id="d8c40-103">Passaggio 3: proteggere e gestire gli accessi degli utenti</span><span class="sxs-lookup"><span data-stu-id="d8c40-103">Step 3: Secure and manage your user sign-ins</span></span>

![Fase 2 - Identità](../media/deploy-foundation-infrastructure/identity_icon-small.png)


<a name="identity-windows-hello"></a>
## <a name="use-windows-hello-for-business"></a><span data-ttu-id="d8c40-105">Usare Windows Hello for Business</span><span class="sxs-lookup"><span data-stu-id="d8c40-105">Use Windows Hello for Business</span></span>

<span data-ttu-id="d8c40-106">*Questo passaggio è facoltativo e si applica alle versioni E3 ed E5 di Microsoft 365*</span><span class="sxs-lookup"><span data-stu-id="d8c40-106">*This is optional and applies to both the E3 and E5 versions of Microsoft 365*</span></span>

<span data-ttu-id="d8c40-107">Windows Hello for Business in Windows 10 Enterprise sostituisce le password con l'autenticazione complessa a due fattori durante l'accesso a un dispositivo Windows.</span><span class="sxs-lookup"><span data-stu-id="d8c40-107">Windows Hello for Business in Windows 10 Enterprise replaces passwords with strong two-factor authentication when signing on a Windows device.</span></span> <span data-ttu-id="d8c40-108">I due fattori sono un nuovo tipo di credenziale utente che è associato a un dispositivo e a una biometria o a un PIN.</span><span class="sxs-lookup"><span data-stu-id="d8c40-108">The two factors are a new type of user credential that is tied to a device and a biometric or PIN.</span></span>

<span data-ttu-id="d8c40-109">Per altre informazioni, vedere [Panoramica di Windows Hello for Business](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview).</span><span class="sxs-lookup"><span data-stu-id="d8c40-109">For more information, see [Windows Hello for Business Overview](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview).</span></span>


<a name="identity-mfa"></a>
## <a name="set-up-azure-multi-factor-authentication"></a><span data-ttu-id="d8c40-110">Impostare l’autenticazione a più fattori di Azure</span><span class="sxs-lookup"><span data-stu-id="d8c40-110">Set up Azure Multi-Factor Authentication</span></span>

<span data-ttu-id="d8c40-111">*Questo passaggio è facoltativo e si applica alle versioni E3 ed E5 di Microsoft 365*</span><span class="sxs-lookup"><span data-stu-id="d8c40-111">*This is optional and applies to both the E3 and E5 versions of Microsoft 365*</span></span>

<span data-ttu-id="d8c40-112">Durante questo passaggio, verrà impostata l’autenticazione a più fattori di Azure per aggiungere un secondo livello di sicurezza agli accessi e alle transazioni degli utenti.</span><span class="sxs-lookup"><span data-stu-id="d8c40-112">In this step, you'll set up Azure Multi-Factor Authentication (MFA) to add a second layer of security to user sign-ins and transactions.</span></span> <span data-ttu-id="d8c40-113">L'autenticazione a più fattori richiede un altro metodo di verifica dopo che gli utenti hanno immesso correttamente la password.</span><span class="sxs-lookup"><span data-stu-id="d8c40-113">MFA requires an additional verification method after users have correctly entered their password.</span></span> <span data-ttu-id="d8c40-114">Senza l’autenticazione a più fattori, la password è l'unico metodo di verifica.</span><span class="sxs-lookup"><span data-stu-id="d8c40-114">Without MFA, the password is the only verification method.</span></span> <span data-ttu-id="d8c40-115">Il problema delle password è che molte di esse possono essere indovinate facilmente da un utente malintenzionato o condivise in modo inconsapevolmente con parti non affidabili.</span><span class="sxs-lookup"><span data-stu-id="d8c40-115">The problem with passwords is that many of them are easily guessed by an attacker or unknowingly shared with untrusted parties.</span></span>

<span data-ttu-id="d8c40-116">Con la MFA, il secondo livello di sicurezza può essere:</span><span class="sxs-lookup"><span data-stu-id="d8c40-116">With MFA, the second layer of security can be:</span></span>

- <span data-ttu-id="d8c40-117">Un dispositivo personale e attendibile che non può essere oggetto di spoofing o duplicazioni, come per esempio uno smartphone.</span><span class="sxs-lookup"><span data-stu-id="d8c40-117">A personal and trusted device that isn’t easily spoofed or duplicated, such as a smart phone.</span></span>
- <span data-ttu-id="d8c40-118">Un attributo biometrico, come per esempio un'impronta digitale.</span><span class="sxs-lookup"><span data-stu-id="d8c40-118">A biometric attribute, such as a fingerprint.</span></span>

<span data-ttu-id="d8c40-119">È possibile abilitare la MFA e configurare il metodo di autenticazione secondario con i [criteri di accesso condizionale](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access), che consentono di usare i gruppi di Azure Active Directory (Azure AD) per distribuire la MFA a set di utenti specifici, ad esempio utenti pilota, aree geografiche o dipartimenti.</span><span class="sxs-lookup"><span data-stu-id="d8c40-119">You'll enable MFA and configure the secondary authentication method with [Conditional Access policies](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access), which allow you to use Azure Active Directory (Azure AD) groups to roll out MFA to specified sets of users, such as pilot users, geographical regions, or departments.</span></span> <span data-ttu-id="d8c40-120">È necessario comunicare agli utenti che la MFA è abilitata, in modo che ne comprendano i requisiti, come l'utilizzo obbligatorio di uno smartphone per effettuare l'accesso, e che possano effettuare l'accesso con esito positivo.</span><span class="sxs-lookup"><span data-stu-id="d8c40-120">Make sure to let your users know that MFA is being enabled so they understand the requirements, such as mandatory use of a smart phone to sign in, and can sign in successfully.</span></span> 

<span data-ttu-id="d8c40-121">Per ulteriori informazioni, consultare [Pianificazione di una distribuzione di Azure Multi-Factor Authentication basata su cloud](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted).</span><span class="sxs-lookup"><span data-stu-id="d8c40-121">For more information, see [Planning a cloud-based Azure Multi-Factor Authentication deployment](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted).</span></span>

|||
|:-------|:-----|
|![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="d8c40-123">Guida al lab di test: autenticazione a più fattori di Azure</span><span class="sxs-lookup"><span data-stu-id="d8c40-123">Test Lab Guide: Azure Multi-Factor Authentication</span></span>](multi-factor-authentication-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="d8c40-124">Come checkpoint provvisorio, è possibile vedere i [criteri uscita](identity-exit-criteria.md#crit-identity-mfa) per questa sezione.</span><span class="sxs-lookup"><span data-stu-id="d8c40-124">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-mfa) for this section.</span></span>

<a name="identity-ident-prot"></a>
## <a name="protect-against-credential-compromise"></a><span data-ttu-id="d8c40-125">Proteggere dalla compromissione delle credenziali</span><span class="sxs-lookup"><span data-stu-id="d8c40-125">Protect against credential compromise</span></span>

<span data-ttu-id="d8c40-126">*Questo passaggio è facoltativo e si applica solo alla versione E5 di Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="d8c40-126">*This is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="d8c40-127">In questa sezione verrà illustrato come configurare i criteri di protezione dalla compromissione delle credenziali, per cui l'autore di un attacco scopre nome e password dell'account di un utente per ottenere l'accesso ai servizi e ai dati cloud di un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d8c40-127">In this section, you'll learn how to configure policies that protect against credential compromise, where an attacker determines a user’s account name and password to gain access to an organization’s cloud services and data.</span></span> <span data-ttu-id="d8c40-128">Azure AD Identity Protection include diversi modi per impedire a un utente malintenzionato di compromettere le credenziali di un account utente.</span><span class="sxs-lookup"><span data-stu-id="d8c40-128">Azure AD Identity Protection provides a number of ways to help prevent an attacker from compromising a user account's credentials.</span></span>

<span data-ttu-id="d8c40-129">Con Azure AD Identity Protection, è possibile:</span><span class="sxs-lookup"><span data-stu-id="d8c40-129">With Azure AD Identity Protection, you can:</span></span>

|||
|:---------|:---------|
|<span data-ttu-id="d8c40-130">Determinare e affrontare possibili vulnerabilità relative alle identità dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="d8c40-130">Determine and address potential vulnerabilities in your organization’s identities</span></span>|<span data-ttu-id="d8c40-131">Azure AD usa l'apprendimento automatico per rilevare anomalie e attività sospette, come le attività di accesso e conseguenti all’accesso.</span><span class="sxs-lookup"><span data-stu-id="d8c40-131">Azure AD uses machine learning to detect anomalies and suspicious activity, such as sign-ins and post-sign-in activities.</span></span> <span data-ttu-id="d8c40-132">Con questi dati, Azure AD Identity Protection genera report e avvisi che consentono di valutare i problemi e intervenire.</span><span class="sxs-lookup"><span data-stu-id="d8c40-132">Using this data, Azure AD Identity Protection generates reports and alerts that help you evaluate the issues and take action.</span></span>|
|<span data-ttu-id="d8c40-133">Rilevare azioni sospette correlate alle identità dell'organizzazione e intervenire automaticamente</span><span class="sxs-lookup"><span data-stu-id="d8c40-133">Detect suspicious actions that are related to your organization’s identities and respond to them automatically</span></span>|<span data-ttu-id="d8c40-134">È possibile configurare criteri basati sul rischio che rispondano automaticamente ai problemi rilevati quando viene raggiunto un livello di rischio specificato.</span><span class="sxs-lookup"><span data-stu-id="d8c40-134">You can configure risk-based policies that automatically respond to detected issues when a specified risk level has been reached.</span></span> <span data-ttu-id="d8c40-135">Questi criteri, con altri controlli di accesso condizionale forniti da Azure AD e Microsoft Intune, possono bloccare automaticamente l’accesso o avviare azioni di correzione, incluse la reimpostazione della password e la richiesta dell'autenticazione a più fattori di Azure per gli accessi successivi.</span><span class="sxs-lookup"><span data-stu-id="d8c40-135">These policies, in addition to other Conditional Access controls provided by Azure AD and Microsoft Intune, can either automatically block access or take corrective actions, including password resets and requiring Azure Multi-Factor Authentication for subsequent sign-ins.</span></span>|
|<span data-ttu-id="d8c40-136">Esaminare gli incidenti sospetti e risolverli con azioni amministrative</span><span class="sxs-lookup"><span data-stu-id="d8c40-136">Investigate suspicious incidents and resolve them with administrative actions</span></span>|<span data-ttu-id="d8c40-p107">È possibile esaminare gli eventi di rischio usando le informazioni sugli incidenti di sicurezza. I flussi di lavoro di base sono disponibili per tenere traccia delle analisi e per attuare azioni correttive, come le reimpostazioni delle password.</span><span class="sxs-lookup"><span data-stu-id="d8c40-p107">You can investigate risk events using information about the security incident. Basic workflows are available to track investigations and initiate remediation actions, such as password resets.</span></span>|

<span data-ttu-id="d8c40-139">Vedere [altre informazioni su Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).</span><span class="sxs-lookup"><span data-stu-id="d8c40-139">See [more information about Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).</span></span>

<span data-ttu-id="d8c40-140">Vedere i [passaggi per abilitare Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).</span><span class="sxs-lookup"><span data-stu-id="d8c40-140">See the [steps to enable Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).</span></span>

<span data-ttu-id="d8c40-141">Al termine della procedura Azure AD Identity Protection è stato abilitato e può essere usato per:</span><span class="sxs-lookup"><span data-stu-id="d8c40-141">The results of this step are that you've enabled Azure AD Identity Protection and you are using it to:</span></span>

- <span data-ttu-id="d8c40-142">Far fronte a potenziali vulnerabilità delle identità.</span><span class="sxs-lookup"><span data-stu-id="d8c40-142">Address potential identity vulnerabilities.</span></span>
- <span data-ttu-id="d8c40-143">Rilevare possibili tentativi di violazione delle credenziali.</span><span class="sxs-lookup"><span data-stu-id="d8c40-143">Detect possible credential compromise attempts.</span></span>
- <span data-ttu-id="d8c40-144">Ricercare le cause e risolvere attività sospette relative alle identità.</span><span class="sxs-lookup"><span data-stu-id="d8c40-144">Investigate and address ongoing suspicious identity incidents.</span></span>

|||
|:-------|:-----|
|![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="d8c40-146">Guida al lab di test: Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="d8c40-146">Test Lab Guide: Azure AD Identity Protection</span></span>](azure-ad-identity-protection-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="d8c40-147">Come checkpoint provvisorio, è possibile vedere i [criteri uscita](identity-exit-criteria.md#crit-identity-ident-prot) per questa sezione.</span><span class="sxs-lookup"><span data-stu-id="d8c40-147">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-ident-prot) for this section.</span></span>

|||
|:-------|:-----|
|![Passaggio 4](../media/stepnumbers/Step4.png)| [<span data-ttu-id="d8c40-149">Aggiungere gli account utente</span><span class="sxs-lookup"><span data-stu-id="d8c40-149">Add your user accounts</span></span>](identity-add-user-accounts.md) |
