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
ms.openlocfilehash: edf51b344ed8f9c8e13587cc2ccf0ba1ed081da6
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37084211"
---
# <a name="step-3-secure-and-manage-your-user-sign-ins"></a><span data-ttu-id="428a5-103">Passaggio 3: proteggere e gestire gli accessi degli utenti</span><span class="sxs-lookup"><span data-stu-id="428a5-103">Step 3: Secure and manage your user sign-ins</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)


<a name="identity-windows-hello"></a>
## <a name="use-windows-hello-for-business"></a><span data-ttu-id="428a5-104">Usare Windows Hello for Business</span><span class="sxs-lookup"><span data-stu-id="428a5-104">Windows Hello for Business</span></span>

<span data-ttu-id="428a5-105">*Questo passaggio è facoltativo e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="428a5-105">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="428a5-106">Windows Hello for Business in Windows 10 Enterprise sostituisce le password con l'autenticazione complessa a due fattori durante l'accesso a un dispositivo Windows.</span><span class="sxs-lookup"><span data-stu-id="428a5-106">Windows Hello for Business in Windows 10 Enterprise replaces passwords with strong two-factor authentication when signing on a Windows device.</span></span> <span data-ttu-id="428a5-107">I due fattori sono un nuovo tipo di credenziale utente che è associato a un dispositivo e a una biometria o a un PIN.</span><span class="sxs-lookup"><span data-stu-id="428a5-107">The two factors are a new type of user credential that is tied to a device and a biometric or PIN.</span></span>

<span data-ttu-id="428a5-108">Per altre informazioni, vedere [Panoramica di Windows Hello for Business](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview).</span><span class="sxs-lookup"><span data-stu-id="428a5-108">For more information, see [Windows Hello for Business Overview](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview).</span></span>


<a name="identity-mfa"></a>
## <a name="set-up-azure-multi-factor-authentication"></a><span data-ttu-id="428a5-109">Impostare l’autenticazione a più fattori di Azure</span><span class="sxs-lookup"><span data-stu-id="428a5-109">Set up Azure Multi-Factor Authentication</span></span>

<span data-ttu-id="428a5-110">*Questo passaggio è facoltativo e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="428a5-110">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="428a5-111">Durante questo passaggio, verrà impostata l’autenticazione a più fattori di Azure per aggiungere un secondo livello di sicurezza agli accessi e alle transazioni degli utenti.</span><span class="sxs-lookup"><span data-stu-id="428a5-111">In this step, you'll set up Azure Multi-Factor Authentication (MFA) to add a second layer of security to user sign-ins and transactions.</span></span> <span data-ttu-id="428a5-112">L'autenticazione a più fattori richiede un altro metodo di verifica dopo che gli utenti hanno immesso correttamente la password.</span><span class="sxs-lookup"><span data-stu-id="428a5-112">MFA requires an additional verification method after users have correctly entered their password.</span></span> <span data-ttu-id="428a5-113">Senza l’autenticazione a più fattori, la password è l'unico metodo di verifica.</span><span class="sxs-lookup"><span data-stu-id="428a5-113">Without MFA, the password is the only verification method.</span></span> <span data-ttu-id="428a5-114">Il problema delle password è che molte di esse possono essere indovinate facilmente da un utente malintenzionato o condivise in modo inconsapevolmente con parti non affidabili.</span><span class="sxs-lookup"><span data-stu-id="428a5-114">The problem with passwords is that many of them are easily guessed by an attacker or unknowingly shared with untrusted parties.</span></span>

<span data-ttu-id="428a5-115">Con la MFA, il secondo livello di sicurezza può essere:</span><span class="sxs-lookup"><span data-stu-id="428a5-115">With MFA, the second layer of security can be:</span></span>

- <span data-ttu-id="428a5-116">Un dispositivo personale e attendibile che non può essere oggetto di spoofing o duplicazioni, come per esempio uno smartphone.</span><span class="sxs-lookup"><span data-stu-id="428a5-116">A personal and trusted device that isn’t easily spoofed or duplicated, such as a smart phone.</span></span>
- <span data-ttu-id="428a5-117">Un attributo biometrico, come per esempio un'impronta digitale.</span><span class="sxs-lookup"><span data-stu-id="428a5-117">A biometric attribute, such as a fingerprint.</span></span>

<span data-ttu-id="428a5-118">È possibile abilitare la MFA e configurare il metodo di autenticazione secondario con i [criteri di accesso condizionale](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access), che consentono di usare i gruppi di Azure Active Directory (Azure AD) per distribuire la MFA a set di utenti specifici, ad esempio utenti pilota, aree geografiche o dipartimenti.</span><span class="sxs-lookup"><span data-stu-id="428a5-118">You'll enable MFA and configure the secondary authentication method with [Conditional Access policies](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access), which allow you to use Azure Active Directory (Azure AD) groups to roll out MFA to specified sets of users, such as pilot users, geographical regions, or departments.</span></span> <span data-ttu-id="428a5-119">È necessario comunicare agli utenti che la MFA è abilitata, in modo che ne comprendano i requisiti, come l'utilizzo obbligatorio di uno smartphone per effettuare l'accesso, e che possano effettuare l'accesso con esito positivo.</span><span class="sxs-lookup"><span data-stu-id="428a5-119">You'll enable MFA and configure the secondary authentication method on a per-user account basis. Make sure to let users know that MFA is being enabled so they understand the requirements, such as mandatory use of a smart phone to sign in, and can sign in successfully.</span></span> 

<span data-ttu-id="428a5-120">Per ulteriori informazioni, consultare [Pianificazione di una distribuzione di Azure Multi-Factor Authentication basata su cloud](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted).</span><span class="sxs-lookup"><span data-stu-id="428a5-120">For more information, see [Planning a cloud-based Azure Multi-Factor Authentication deployment](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted).</span></span>

|||
|:-------|:-----|
|![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="428a5-122">Guida al lab di test: autenticazione a più fattori di Azure</span><span class="sxs-lookup"><span data-stu-id="428a5-122">Test Lab Guide: Azure Multi-Factor Authentication</span></span>](multi-factor-authentication-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="428a5-123">Come checkpoint provvisorio, è possibile vedere i [criteri uscita](identity-exit-criteria.md#crit-identity-mfa) per questa sezione.</span><span class="sxs-lookup"><span data-stu-id="428a5-123">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-mfa) for this section.</span></span>

<a name="identity-ident-prot"></a>
## <a name="protect-against-credential-compromise"></a><span data-ttu-id="428a5-124">Proteggere dalla compromissione delle credenziali</span><span class="sxs-lookup"><span data-stu-id="428a5-124">Protect against credential compromise</span></span>

<span data-ttu-id="428a5-125">*Questo passaggio è facoltativo e si applica solo alla versione E5 di Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="428a5-125">*This is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="428a5-126">In questa sezione verrà illustrato come configurare i criteri di protezione dalla compromissione delle credenziali, per cui l'autore di un attacco scopre nome e password dell'account di un utente per ottenere l'accesso ai servizi e ai dati cloud di un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="428a5-126">In this section, you'll learn how to configure policies that protect against credential compromise, where an attacker determines a user’s account name and password to gain access to an organization’s cloud services and data.</span></span> <span data-ttu-id="428a5-127">Azure AD Identity Protection include diversi modi per impedire a un utente malintenzionato di compromettere le credenziali di un account utente.</span><span class="sxs-lookup"><span data-stu-id="428a5-127">Azure AD Identity Protection provides a number of ways to help prevent an attacker from compromising a user account's credentials.</span></span>

<span data-ttu-id="428a5-128">Con Azure AD Identity Protection, è possibile:</span><span class="sxs-lookup"><span data-stu-id="428a5-128">With Azure AD Identity Protection, you can:</span></span>

|||
|:---------|:---------|
|<span data-ttu-id="428a5-129">Determinare e affrontare possibili vulnerabilità relative alle identità dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="428a5-129">Determine and address potential vulnerabilities in your organization’s identities</span></span>|<span data-ttu-id="428a5-130">Azure AD usa l'apprendimento automatico per rilevare anomalie e attività sospette, come le attività di accesso e conseguenti all’accesso.</span><span class="sxs-lookup"><span data-stu-id="428a5-130">Azure AD uses machine learning to detect anomalies and suspicious activity, such as sign-ins and post-sign-in activities. Using this data, Identity Protection generates reports and alerts that help you evaluate the issues and take action.</span></span> <span data-ttu-id="428a5-131">Con questi dati, Azure AD Identity Protection genera report e avvisi che consentono di valutare i problemi e intervenire.</span><span class="sxs-lookup"><span data-stu-id="428a5-131">Azure AD uses machine learning to detect anomalies and suspicious activity, such as sign-ins and post-sign-in activities. Using this data, Identity Protection generates reports and alerts that help you evaluate the issues and take action.</span></span>|
|<span data-ttu-id="428a5-132">Rilevare azioni sospette correlate alle identità dell'organizzazione e intervenire automaticamente</span><span class="sxs-lookup"><span data-stu-id="428a5-132">Detect suspicious actions that are related to your organization’s identities and respond to them automatically</span></span>|<span data-ttu-id="428a5-133">È possibile configurare criteri basati sul rischio che rispondano automaticamente ai problemi rilevati quando viene raggiunto un livello di rischio specificato.</span><span class="sxs-lookup"><span data-stu-id="428a5-133">You can configure risk-based policies that automatically respond to detected issues when a specified risk level has been reached.</span></span> <span data-ttu-id="428a5-134">Questi criteri, con altri controlli di accesso condizionale forniti da Azure AD e Microsoft Intune, possono bloccare automaticamente l’accesso o avviare azioni di correzione, incluse la reimpostazione della password e la richiesta dell'autenticazione a più fattori di Azure per gli accessi successivi.</span><span class="sxs-lookup"><span data-stu-id="428a5-134">These policies, in addition to other Conditional Access controls provided by Azure AD and Microsoft Intune, can either automatically block access or take corrective actions, including password resets and requiring Azure Multi-Factor Authentication for subsequent sign-ins.</span></span>|
|<span data-ttu-id="428a5-135">Esaminare gli incidenti sospetti e risolverli con azioni amministrative</span><span class="sxs-lookup"><span data-stu-id="428a5-135">Investigate suspicious incidents and resolve them with administrative actions</span></span>|<span data-ttu-id="428a5-p107">È possibile esaminare gli eventi di rischio usando le informazioni sugli incidenti di sicurezza. I flussi di lavoro di base sono disponibili per tenere traccia delle analisi e per attuare azioni correttive, come le reimpostazioni delle password.</span><span class="sxs-lookup"><span data-stu-id="428a5-p107">You can investigate risk events using information about the security incident. Basic workflows are available to track investigations and initiate remediation actions, such as password resets.</span></span>|

<span data-ttu-id="428a5-138">Vedere [altre informazioni su Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).</span><span class="sxs-lookup"><span data-stu-id="428a5-138">See [more information about Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).</span></span>

<span data-ttu-id="428a5-139">Vedere i [passaggi per abilitare Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).</span><span class="sxs-lookup"><span data-stu-id="428a5-139">See the [steps to enable Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).</span></span>

<span data-ttu-id="428a5-140">Al termine della procedura Azure AD Identity Protection è stato abilitato e può essere usato per:</span><span class="sxs-lookup"><span data-stu-id="428a5-140">The results of this step are that you've enabled Azure AD Identity protection and you are using it to:</span></span>

- <span data-ttu-id="428a5-141">Far fronte a potenziali vulnerabilità delle identità.</span><span class="sxs-lookup"><span data-stu-id="428a5-141">Address potential identity vulnerabilities.</span></span>
- <span data-ttu-id="428a5-142">Rilevare possibili tentativi di violazione delle credenziali.</span><span class="sxs-lookup"><span data-stu-id="428a5-142">Detect possible credential compromise attempts.</span></span>
- <span data-ttu-id="428a5-143">Ricercare le cause e risolvere attività sospette relative alle identità.</span><span class="sxs-lookup"><span data-stu-id="428a5-143">Investigate and address ongoing suspicious identity incidents.</span></span>

|||
|:-------|:-----|
|![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="428a5-145">Guida al lab di test: Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="428a5-145">Test Lab Guide: Azure AD Identity Protection</span></span>](azure-ad-identity-protection-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="428a5-146">Come checkpoint provvisorio, è possibile vedere i [criteri uscita](identity-exit-criteria.md#crit-identity-ident-prot) per questa sezione.</span><span class="sxs-lookup"><span data-stu-id="428a5-146">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-ident-prot) for this section.</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step4.png)| [<span data-ttu-id="428a5-147">Aggiungere gli account utente</span><span class="sxs-lookup"><span data-stu-id="428a5-147">Add your user accounts</span></span>](identity-add-user-accounts.md) |
