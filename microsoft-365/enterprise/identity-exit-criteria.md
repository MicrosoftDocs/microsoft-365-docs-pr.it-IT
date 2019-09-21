---
title: "Fase 2: criteri uscita dell'infrastruttura di rete"
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
description: Verificare che la configurazione soddisfi i criteri di Microsoft 365 Enterprise per l'infrastruttura e i servizi basati sull'identità.
ms.openlocfilehash: 880bfa2b71158a2fa5c64fb09af2e8a34428a7a8
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37071685"
---
# <a name="phase-2-identity-infrastructure-exit-criteria"></a><span data-ttu-id="841c7-103">Fase 2: criteri uscita dell'infrastruttura di rete</span><span class="sxs-lookup"><span data-stu-id="841c7-103">Phase 2: Identity infrastructure exit criteria</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="841c7-104">Verificare che l'infrastruttura di rete soddisfi i criteri obbligatori seguenti e assicurarsi di tenere in considerazione quelli facoltativi.</span><span class="sxs-lookup"><span data-stu-id="841c7-104">Make sure your identity infrastructure meets the following required criteria and that you've considered those that are optional.</span></span>

<span data-ttu-id="841c7-105">Vedere anche [Prerequisiti](https://docs.microsoft.com/microsoft-365-enterprise/identity-access-policies#prerequisites) per ulteriori consigli sull'infrastruttura di gestione delle identità.</span><span class="sxs-lookup"><span data-stu-id="841c7-105">Also see [Prerequisites](https://docs.microsoft.com/microsoft-365-enterprise/identity-access-policies#prerequisites) for additional recommendations on identity infrastructure.</span></span>

<a name="crit-identity-global-admin"></a>
## <a name="required-your-global-administrator-accounts-are-protected"></a><span data-ttu-id="841c7-106">Obbligatorio: gli account di amministratore globale sono protetti</span><span class="sxs-lookup"><span data-stu-id="841c7-106">Required: Your global administrator accounts are protected</span></span> 

<span data-ttu-id="841c7-107">Gli [account di amministratore globale di Office 365 sono stati protetti](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts) per contrastare la possibile compromissione delle credenziali da parte di malintenzionati, che potrebbe condurre a violazioni dell’abbonamento a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="841c7-107">You've [protected your Office 365 global administrator accounts](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts) to thwart  credential compromise by attackers that can lead to breaches of your Microsoft 365 subscription.</span></span>

<span data-ttu-id="841c7-108">Se si ignora questo requisito, gli account di amministratore globale potrebbero essere soggetti ad attacchi e violazioni, consentendo a terzi l'acquisizione di dati e l'utilizzo di tali informazioni per scopi di raccolta, distruzione o ricatto.</span><span class="sxs-lookup"><span data-stu-id="841c7-108">If you skip this requirement, your global administrator accounts can be susceptible to attack and compromise, allowing an attacker to gain system-wide access to your data for harvesting, destruction, or ransom.</span></span>

<span data-ttu-id="841c7-109">Se necessario, il [Passaggio 1](identity-create-protect-global-admins.md#identity-global-admin) può aiutare a soddisfare questo requisito.</span><span class="sxs-lookup"><span data-stu-id="841c7-109">If needed, [Step 1](identity-create-protect-global-admins.md#identity-global-admin) can help you meet this requirement.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="841c7-110">Come eseguire il test</span><span class="sxs-lookup"><span data-stu-id="841c7-110">How to test</span></span>

<span data-ttu-id="841c7-111">Utilizzare questa procedura per verificare che gli account di amministratore globale siano protetti:</span><span class="sxs-lookup"><span data-stu-id="841c7-111">Use these steps to verify that you've protected your global administrator accounts:</span></span>

1. <span data-ttu-id="841c7-112">Al prompt dei comandi di PowerShell, eseguire il comando seguente di Azure Active Directory PowerShell per Graph.</span><span class="sxs-lookup"><span data-stu-id="841c7-112">Run the following Azure Active Directory PowerShell for Graph command at the PowerShell command prompt.</span></span> <span data-ttu-id="841c7-113">Dovrebbe essere visualizzato solo l'elenco degli account di amministratore globale dedicati.</span><span class="sxs-lookup"><span data-stu-id="841c7-113">Run the following Azure AD V2 command at the PowerShell command prompt. You should see only the list of dedicated global administrator accounts.</span></span>
   ```
   Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
   ```
2. <span data-ttu-id="841c7-114">Accedere a Office 365 usando ognuno degli account del passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="841c7-114">Sign in to Office 365 using each of the accounts from step 1. Each sign in must require multi-factor authentication and the strongest form of secondary authentication available in your organization.</span></span> <span data-ttu-id="841c7-115">Ogni accesso dovrà richiedere Azure Multi-Factor Authentication e la forma più avanzata di autenticazione secondaria disponibile nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="841c7-115">Each sign in must require Azure Multi-Factor Authentication and the strongest form of secondary authentication available in your organization.</span></span>

> [!Note]
> <span data-ttu-id="841c7-116">Vedere [Connettersi a PowerShell di Office 365](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) per le istruzioni sull'istallazione del modulo Azure Active Directory PowerShell for Graph e sull'accesso a Office 365.</span><span class="sxs-lookup"><span data-stu-id="841c7-116">See [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) for instructions on installing the Azure Active Directory PowerShell for Graph module and signing in to Office 365.</span></span>

<a name="crit-identity-pim"></a>
## <a name="optional-you-have-set-up-privileged-identity-management-to-support-on-demand-assignment-of-the-global-administrator-role"></a><span data-ttu-id="841c7-117">Facoltativo: è stato configurato Privileged Identity Management per supportare l'assegnazione su richiesta del ruolo di amministratore globale</span><span class="sxs-lookup"><span data-stu-id="841c7-117">Optional: You have set up Privileged Identity Management to support on-demand assignment of the global administrator role</span></span>

<span data-ttu-id="841c7-118">Sono state seguite le istruzioni presenti in [Configurare Azure AD Privileged Identity Management (PIM)](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure) per abilitare PIM nel tenant di Azure AD e sono stati configurati gli account di amministratore globale idonei per il ruolo di amministratori.</span><span class="sxs-lookup"><span data-stu-id="841c7-118">You've used the instructions in [Configure Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure) to enable PIM in your Azure AD tenant and configured your global administrator accounts as eligible admins.</span></span>

<span data-ttu-id="841c7-119">Inoltre, sono stati seguiti i consigli presenti in [Protezione dell'accesso con privilegi per le distribuzioni ibride e cloud in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices) per sviluppare una roadmap che protegga l'accesso con privilegi dagli attacchi informatici.</span><span class="sxs-lookup"><span data-stu-id="841c7-119">You've also used the recommendations in [Securing privileged access for hybrid and cloud deployments in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices) to develop a roadmap that secures privileged access against cyber attackers.</span></span>

<span data-ttu-id="841c7-120">Se si ignora questa opzione, gli account di amministratore globale potranno essere soggetti ad attacco online e, se violati, un utente malintenzionato potrà raccogliere, distruggere o conservare le informazioni riservate a scopo di ricatto.</span><span class="sxs-lookup"><span data-stu-id="841c7-120">If you skip this option, your global administrator accounts are subject to ongoing online attack and, if compromised, can allow an attacker to harvest, destroy, or hold your sensitive information for ransom.</span></span>

<span data-ttu-id="841c7-121">Se necessario, il [Passaggio 1](identity-create-protect-global-admins.md#identity-pim) può aiutare con questa opzione.</span><span class="sxs-lookup"><span data-stu-id="841c7-121">If needed, [Step 1](identity-create-protect-global-admins.md#identity-pim) can help you with this option.</span></span>

<a name="crit-identity-pam"></a>
## <a name="optional-you-have-configure-privileged-access-management-in-office-365"></a><span data-ttu-id="841c7-122">Facoltativo: è stata configurata la gestione degli accessi con privilegi in Office 365</span><span class="sxs-lookup"><span data-stu-id="841c7-122">Optional: You have configure privileged access management in Office 365</span></span>

<span data-ttu-id="841c7-123">Sono state usate le informazioni contenute nell'argomento [Configurare la gestione degli accessi con privilegi in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) per abilitare l'accesso con privilegi e creare uno o più criteri di accesso con privilegi all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="841c7-123">You've used the information in the [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic to enable privileged access and create one or more privileged access policies in your organization.</span></span> <span data-ttu-id="841c7-124">I criteri sono stati configurati ed è abilitato l'accesso just-in-time ai dati sensibili o alle impostazioni di configurazione critiche.</span><span class="sxs-lookup"><span data-stu-id="841c7-124">You've configured these policies and just-in-time access is enabled for access to sensitive data or access to critical configuration settings.</span></span>

<span data-ttu-id="841c7-125">Se necessario, il [Passaggio 1](identity-create-protect-global-admins.md#identity-pam) può aiutare a soddisfare questo requisito.</span><span class="sxs-lookup"><span data-stu-id="841c7-125">If needed, [Step 1](identity-create-protect-global-admins.md#identity-pam) can help you meet this requirement.</span></span> 

<a name="crit-password-prot"></a>
## <a name="optional-azure-ad-password-protection-is-banning-the-use-of-weak-passwords"></a><span data-ttu-id="841c7-126">Facoltativo: la protezione con password di Azure Active Directory impedisce l'uso di password vulnerabili</span><span class="sxs-lookup"><span data-stu-id="841c7-126">Optional: Azure AD password protection is banning the use of weak passwords</span></span>

<span data-ttu-id="841c7-127">È stata abilitata l'esclusione delle password non appropriate [nel cloud](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) e nell'ambiente [Active Directory Domain Services (AD DS) locale](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises) per le password escluse a livello globale e, facoltativamente, per termini personalizzati.</span><span class="sxs-lookup"><span data-stu-id="841c7-127">You have enabled the banning of bad passwords [in the cloud](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) and for your [on-premises Active Directory Domain Services (AD DS)](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises) for global banned passwords and, optionally, for custom terms.</span></span>

<span data-ttu-id="841c7-128">Se necessario, il [Passaggio 2](identity-secure-your-passwords.md#identity-password-prot) può aiutare con questa opzione.</span><span class="sxs-lookup"><span data-stu-id="841c7-128">If needed, [Step 2](identity-secure-your-passwords.md#identity-password-prot) can help you with this option.</span></span>

<a name="crit-identity-pw-reset"></a>
## <a name="optional-users-can-reset-their-own-passwords"></a><span data-ttu-id="841c7-129">Facoltativo: gli utenti possono reimpostare la propria password</span><span class="sxs-lookup"><span data-stu-id="841c7-129">Optional: Users can reset their own passwords</span></span>

<span data-ttu-id="841c7-130">È stata utilizzata la procedura descritta in [Distribuzione rapida della reimpostazione della password self-service di Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) per configurare la reimpostazione della password per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="841c7-130">You've used [Azure AD self-service password reset rapid deployment](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) to configure password reset for your users.</span></span>

<span data-ttu-id="841c7-131">Se non si soddisfa questa condizione, gli utenti dovranno dipendere dagli amministratori degli account utente per reimpostare le proprie password, con un sovraccarico sull'amministrazione IT.</span><span class="sxs-lookup"><span data-stu-id="841c7-131">If you don’t meet this condition, users will be dependent on user account administrators to reset their passwords, resulting in additional IT administration overhead.</span></span>

<span data-ttu-id="841c7-132">Se necessario, il [Passaggio 2](identity-secure-your-passwords.md#identity-pw-reset) può aiutare con questa opzione.</span><span class="sxs-lookup"><span data-stu-id="841c7-132">If needed, [Step 2](identity-secure-your-passwords.md#identity-pw-reset) can help you with this option.</span></span>

<a name="crit-identity-sso"></a>
## <a name="optional-users-can-sign-in-using-azure-ad-seamless-single-sign-on"></a><span data-ttu-id="841c7-133">Facoltativo: gli utenti possono accedere usando la funzionalità Accesso Single Sign-On facile di Azure AD</span><span class="sxs-lookup"><span data-stu-id="841c7-133">Optional: Users can sign in using Azure AD Seamless Single Sign-on</span></span>

<span data-ttu-id="841c7-134">È stato abilitato [Azure AD Connect: accesso Single Sign-On facile](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start) per l'organizzazione, con lo scopo di semplificare l'accesso degli utenti alle applicazioni basate sul cloud, come Office 365.</span><span class="sxs-lookup"><span data-stu-id="841c7-134">You enabled [Azure AD Connect: Seamless Single Sign-On](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start) for your organization to simplify how users sign in to cloud-based applications, such as Office 365.</span></span>

<span data-ttu-id="841c7-135">Se si ignora questa opzione, gli utenti potrebbero dover immettere le credenziali quando accedono alle applicazioni aggiuntive che usano il tenant di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="841c7-135">If you skip this option, your users might be prompted to provide credentials when they access additional applications that use Azure AD.</span></span>

<span data-ttu-id="841c7-136">Se necessario, il [Passaggio 2](identity-secure-your-passwords.md#identity-sso) può aiutare con questa opzione.</span><span class="sxs-lookup"><span data-stu-id="841c7-136">If needed, [Step 2](identity-secure-your-passwords.md#identity-sso) can help you with this option.</span></span>

<a name="crit-identity-custom-sign-in"></a>
## <a name="optional-the-office-365-sign-in-screen-is-personalized-for-your-organization"></a><span data-ttu-id="841c7-137">Facoltativo: la schermata di accesso a Office 365 è personalizzata per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="841c7-137">Optional: The Office 365 sign-in screen is personalized for your organization</span></span>

<span data-ttu-id="841c7-138">È stata utilizzata la procedura descritta in [Aggiungere il marchio dell'azienda alla pagina di accesso e alle pagine del riquadro di accesso](http://aka.ms/aadpaddbranding) per aggiungere le informazioni personalizzate distintive dell'azienda nella pagina di accesso di Office 365.</span><span class="sxs-lookup"><span data-stu-id="841c7-138">You have used [Add company branding to your sign-in and Access Panel pages](http://aka.ms/aadpaddbranding) to add your organization’s branding to the Office 365 sign-in page.</span></span>

<span data-ttu-id="841c7-139">Se si ignora questa opzione, gli utenti visualizzeranno una schermata generica di accesso a Office 365 e non avranno la certezza di effettuare l'accesso al sito dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="841c7-139">If you skip this option, your users will see a generic Office 365 sign-in screen and might not be confident that they’re signing into your organization’s site.</span></span>

<span data-ttu-id="841c7-140">Se necessario, il [Passaggio 2](identity-secure-your-passwords.md#identity-custom-sign-in) può aiutare con questa opzione.</span><span class="sxs-lookup"><span data-stu-id="841c7-140">If needed, [Step 2](identity-secure-your-passwords.md#identity-custom-sign-in) can help you with this option.</span></span>


<a name="crit-identity-mfa"></a>
## <a name="optional-azure-multi-factor-authentication-is-enabled-for-your-users"></a><span data-ttu-id="841c7-141">Facoltativo: il servizio Azure Multi-Factor Authentication è abilitato per gli utenti</span><span class="sxs-lookup"><span data-stu-id="841c7-141">Optional: Azure Multi-Factor Authentication is enabled for your users</span></span>

<span data-ttu-id="841c7-142">Sono stati usati la [Pianificazione per la distribuzione di Azure Multi-Factor Authentication](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted) e i [criteri di accesso condizionale](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access) per abilitare Azure Multi-Factor Authentication (MFA) per gli account utente.</span><span class="sxs-lookup"><span data-stu-id="841c7-142">You used [Plan for Azure Multi-Factor Authentication](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted) and [Conditional Access policies](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access) to enable Azure Multi-Factor Authentication (MFA) for your user accounts.</span></span>

<span data-ttu-id="841c7-p104">Se si ignora questa opzione, gli account utente saranno vulnerabili alla violazione delle credenziali ad opera di possibili attacchi informatici. In caso di violazione della password di un account utente, tutte le risorse e le funzionalità dell'account (come i ruoli di amministratore) saranno a disposizione dell'utente malintenzionato, che potrà copiare, distruggere o conservare a scopo di ricatto documenti interni o altri dati.</span><span class="sxs-lookup"><span data-stu-id="841c7-p104">If you skip this option, your user accounts are vulnerable to credential compromise by cyber attackers. If a user account’s password is compromised, all the resources and capabilities of the account, such as administrator roles, are available to the attacker. This allows the attacker to copy, destroy, or hold for ransom internal documents and other data.</span></span>

<span data-ttu-id="841c7-146">Se necessario, il [Passaggio 3](identity-secure-user-sign-ins.md#identity-mfa) può aiutare con questa opzione.</span><span class="sxs-lookup"><span data-stu-id="841c7-146">If needed, [Step 3](identity-secure-user-sign-ins.md#identity-mfa) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="841c7-147">Come eseguire il test</span><span class="sxs-lookup"><span data-stu-id="841c7-147">How to test</span></span>

1.  <span data-ttu-id="841c7-148">Creare un account utente di test e assegnargli una licenza.</span><span class="sxs-lookup"><span data-stu-id="841c7-148">Create a test user account in the Office 365 Admin portal and assign them a license.</span></span> 
2.  <span data-ttu-id="841c7-149">Configurare Azure Multi-Factor Authentication per l'account utente di test con il metodo di verifica aggiuntivo in uso per gli account utente effettivi, come per esempio l'invio di un SMS al telefono.</span><span class="sxs-lookup"><span data-stu-id="841c7-149">Configure multi-factor authentication for the test user account with the additional verification method that you are using for actual user accounts, such as sending a message to your phone.</span></span> 
3.  <span data-ttu-id="841c7-150">Accedere al portale di Office 36 con l'account utente di test.</span><span class="sxs-lookup"><span data-stu-id="841c7-150">Sign in to the Office 365 or Azure portal with the test user account.</span></span>
4.  <span data-ttu-id="841c7-151">Verificare che l'autenticazione a più fattori richieda all'utente ulteriori informazioni di verifica e abbia esito positivo.</span><span class="sxs-lookup"><span data-stu-id="841c7-151">Verify that MFA prompts you for the additional verification information and results in a successful authentication.</span></span> 
5.  <span data-ttu-id="841c7-152">Eliminare l'account utente di test.</span><span class="sxs-lookup"><span data-stu-id="841c7-152">Delete the test user account.</span></span>

<a name="crit-identity-ident-prot"></a>
## <a name="optional-azure-ad-identity-protection-is-enabled-to-protect-against-credential-compromise-microsoft-365-enterprise-e5-only"></a><span data-ttu-id="841c7-153">Facoltativo: Azure AD Identity Protection è abilitato per proteggere le credenziali da eventuali violazioni (solo Microsoft 365 Enterprise E5)</span><span class="sxs-lookup"><span data-stu-id="841c7-153">Optional: Azure AD Identity Protection is enabled to protect against credential compromise</span></span>

<span data-ttu-id="841c7-154">Azure AD Identity Protection è stato abilitato per:</span><span class="sxs-lookup"><span data-stu-id="841c7-154">You've enabled Azure AD Identity Protection to:</span></span>

- <span data-ttu-id="841c7-155">Far fronte a potenziali vulnerabilità delle identità.</span><span class="sxs-lookup"><span data-stu-id="841c7-155">Address potential identity vulnerabilities.</span></span>
- <span data-ttu-id="841c7-156">Rilevare possibili tentativi di violazione delle credenziali.</span><span class="sxs-lookup"><span data-stu-id="841c7-156">Detect possible credential compromise attempts.</span></span>
- <span data-ttu-id="841c7-157">Ricercare le cause e risolvere attività sospette relative alle identità.</span><span class="sxs-lookup"><span data-stu-id="841c7-157">Investigate and address ongoing suspicious identity incidents.</span></span>

<span data-ttu-id="841c7-p105">Se si ignora questa opzione, non sarà possibile rilevare o contrastare tentativi di violazione delle credenziali o ricercare le cause dei problemi di sicurezza relativi alle identità. Questo potrebbe rendere l'organizzazione vulnerabile alla violazione delle credenziali e alla conseguente minaccia ai dati sensibili.</span><span class="sxs-lookup"><span data-stu-id="841c7-p105">If you skip this option, you won’t be able to detect or automatically thwart credential compromise attempts or investigate identity-related security incidents. This potentially leaves your organization vulnerable to a successful credential compromise and the resulting threat to your organization’s sensitive data.</span></span>

<span data-ttu-id="841c7-160">Se necessario, il [Passaggio 3](identity-secure-user-sign-ins.md#identity-ident-prot) può aiutare con questa opzione.</span><span class="sxs-lookup"><span data-stu-id="841c7-160">If needed, [Step 3](identity-secure-user-sign-ins.md#identity-ident-prot) can help you with this option.</span></span>


### <a name="how-to-test"></a><span data-ttu-id="841c7-161">Come eseguire il test</span><span class="sxs-lookup"><span data-stu-id="841c7-161">How to test</span></span>

1. <span data-ttu-id="841c7-162">Creare un account utente di test con una password iniziale.</span><span class="sxs-lookup"><span data-stu-id="841c7-162">Create a test user account with an initial password.</span></span>
2. <span data-ttu-id="841c7-163">Utilizzare i passaggi illustrati in [Consentire agli utenti di reimpostare le loro password in Office 365](https://docs.microsoft.com/office365/admin/add-users/let-users-reset-passwords) per reimpostare la password dell'account utente di test.</span><span class="sxs-lookup"><span data-stu-id="841c7-163">Use the steps in [Let users reset their own passwords in Office 365](https://docs.microsoft.com/office365/admin/add-users/let-users-reset-passwords) to reset the password on the test user account.</span></span>
3. <span data-ttu-id="841c7-164">Disconnettersi ed effettuare di nuovo l'accesso con l'account utente di test con la nuova password.</span><span class="sxs-lookup"><span data-stu-id="841c7-164">Sign out and then sign in to the test user account using the reset password.</span></span>
4. <span data-ttu-id="841c7-165">Eliminare l'account utente di test.</span><span class="sxs-lookup"><span data-stu-id="841c7-165">Delete the test user account.</span></span>

<a name="crit-identity-sync"></a>
## <a name="required-for-hybrid-identity-users-and-groups-are-synchronized-with-azure-ad"></a><span data-ttu-id="841c7-166">Obbligatorio per l'identità ibrida: gli utenti e i gruppi sono sincronizzati con Azure AD</span><span class="sxs-lookup"><span data-stu-id="841c7-166">Required: Users and groups are synchronized with Azure AD</span></span>

<span data-ttu-id="841c7-167">Se si dispone di un'istanza locale di Active Directory Domain Services (AD DS), è stato usato Azure AD Connect per sincronizzare i gruppi e gli account utente dall'ambiente AD DS locale al tenant di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="841c7-167">If you have an existing on-premises identity provider, such as Active Directory Domain Services (AD DS), you have used Azure AD Connect to synchronize user accounts and groups from your on-premises identity provider to your Azure AD tenant.</span></span>

<span data-ttu-id="841c7-168">Grazie alla sincronizzazione della directory, gli utenti possono accedere a Office 365 e agli altri servizi cloud Microsoft utilizzando le stesse credenziali che usano per l'accesso ai loro computer e alle risorse locali.</span><span class="sxs-lookup"><span data-stu-id="841c7-168">With directory synchronization, your users can sign in to Office 365 and other Microsoft cloud services using the same credentials that they use to sign in to their computers and access on-premises resources.</span></span>

<span data-ttu-id="841c7-169">Se necessario, il [Passaggio 4](identity-add-user-accounts.md#identity-sync) può aiutare a soddisfare questo requisito.</span><span class="sxs-lookup"><span data-stu-id="841c7-169">If needed, [Step 4](identity-add-user-accounts.md#identity-sync) can help you meet this requirement.</span></span>

<span data-ttu-id="841c7-170">Se si ignora questo requisito, saranno disponibili due set di account utente e gruppi:</span><span class="sxs-lookup"><span data-stu-id="841c7-170">If you skip this requirement, you’ll have two sets of user accounts and groups:</span></span>

- <span data-ttu-id="841c7-171">Gli account utente e i gruppi esistenti nell'ambiente AD DS locale</span><span class="sxs-lookup"><span data-stu-id="841c7-171">User accounts and groups that exist in your on-premises identity provider</span></span>
- <span data-ttu-id="841c7-172">Gli account utente e i gruppi esistenti nel tenant di Azure AD</span><span class="sxs-lookup"><span data-stu-id="841c7-172">User accounts and groups that exist in your Azure AD tenant</span></span>

<span data-ttu-id="841c7-p106">In questo stato, i due set di account e gruppi utente dovranno essere gestiti manualmente sia dagli utenti che dagli amministratori IT. Questo comporterà inevitabilmente la mancata sincronizzazione di account, password e gruppi.</span><span class="sxs-lookup"><span data-stu-id="841c7-p106">In this state, the two sets of user accounts and groups must be manually maintained by both IT administrators and users. This will inevitably lead to unsynchronized accounts, their passwords, and groups.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="841c7-175">Come eseguire il test</span><span class="sxs-lookup"><span data-stu-id="841c7-175">How to test</span></span>
<span data-ttu-id="841c7-176">Per verificare il corretto funzionamento dell'autenticazione con le credenziali locali, accedere al portale di Office con le credenziali locali.</span><span class="sxs-lookup"><span data-stu-id="841c7-176">To verify that authentication with on-premises credentials works correctly, sign in to the Office portal with your on-premises credentials.</span></span>

<span data-ttu-id="841c7-177">Per verificare il corretto funzionamento della sincronizzazione della directory, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="841c7-177">To verify that directory synchronization is working correctly, do the following:</span></span>

1.  <span data-ttu-id="841c7-178">Creare un nuovo gruppo di test in AD DS.</span><span class="sxs-lookup"><span data-stu-id="841c7-178">Create a new test group in AD DS.</span></span>
2.  <span data-ttu-id="841c7-179">Attendere la sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="841c7-179">Wait for the synchronization time.</span></span>
3.  <span data-ttu-id="841c7-180">Controllare il tenant di Azure AD per verificare che venga visualizzato il nome del nuovo gruppo di test.</span><span class="sxs-lookup"><span data-stu-id="841c7-180">Check your Azure AD tenant to verify that the new test group name appears.</span></span>

<a name="crit-identity-sync-health"></a>
## <a name="optional-directory-synchronization-is-monitored"></a><span data-ttu-id="841c7-181">Facoltativo: la sincronizzazione delle directory viene monitorata</span><span class="sxs-lookup"><span data-stu-id="841c7-181">Optional: Directory synchronization is monitored</span></span>

<span data-ttu-id="841c7-182">È stata consultata la documentazione disponibile in [Uso di Azure AD Connect Health per la sincronizzazione](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) (per la sincronizzazione delle password) o in [Uso di Azure AD Connect Health con AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) (per l'autenticazione federata) ed è stato implementato Azure AD Connect Health, che implica quanto segue:</span><span class="sxs-lookup"><span data-stu-id="841c7-182">You've used [Azure AD Connect Health with sync](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) (for password synchronization) or [Using Azure AD Connect Health with AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) (for federated authentication) and have deployed Azure AD Connect Health, which involves:</span></span>

- <span data-ttu-id="841c7-183">L'installazione dell'agente di Azure AD Connect Health su ciascuno dei server di identità locale.</span><span class="sxs-lookup"><span data-stu-id="841c7-183">Installing the Azure AD Connect Health agent on each of your on-premises identity servers.</span></span>
- <span data-ttu-id="841c7-184">L'utilizzo del portale di Azure AD Connect Health per monitorare lo stato della sincronizzazione in corso.</span><span class="sxs-lookup"><span data-stu-id="841c7-184">Using the Azure AD Connect Health portal to monitor the state of the ongoing synchronization.</span></span>

<span data-ttu-id="841c7-185">Se si ignora questa opzione, è possibile valutare in maniera più precisa lo stato dell'infrastruttura di gestione delle identità basata sul cloud.</span><span class="sxs-lookup"><span data-stu-id="841c7-185">If you skip this option, you can more accurately assess the state of your cloud-based identity infrastructure.</span></span>

<span data-ttu-id="841c7-186">Se necessario, il [Passaggio 4](identity-add-user-accounts.md#identity-sync-health) può aiutare con questa opzione.</span><span class="sxs-lookup"><span data-stu-id="841c7-186">If needed, [Step 4](identity-add-user-accounts.md#identity-sync-health) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="841c7-187">Come eseguire il test</span><span class="sxs-lookup"><span data-stu-id="841c7-187">How to test</span></span>
<span data-ttu-id="841c7-188">Il portale di Azure AD Connect Health mostra lo stato attuale e corretto dei controller di dominio locali e la sincronizzazione in corso.</span><span class="sxs-lookup"><span data-stu-id="841c7-188">The Azure AD Connect Health portal shows the current and correct state of your on-premises identity servers and the ongoing synchronization.</span></span>


<a name="crit-identity-pw-writeback"></a>
## <a name="optional-password-writeback-is-enabled-for-your-users"></a><span data-ttu-id="841c7-189">Facoltativo: il writeback delle password è abilitato per gli utenti</span><span class="sxs-lookup"><span data-stu-id="841c7-189">Optional: Password writeback is enabled for your users</span></span>

<span data-ttu-id="841c7-190">Sono state utilizzate le istruzioni riportate in [Reimpostazione delle password in modalità self-service di Azure AD con writeback delle password](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) per abilitare il writeback delle password per il tenant di Azure AD per la sottoscrizione di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="841c7-190">You've used the instructions in [Azure AD SSPR with password writeback](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) to enable password writeback for the Azure AD tenant of your Microsoft 365 Enterprise subscription.</span></span>

<span data-ttu-id="841c7-191">Se si ignora questa opzione, gli utenti che non sono connessi con il server locale devono reimpostare o sbloccare le password dei AD DS tramite un amministratore IT.</span><span class="sxs-lookup"><span data-stu-id="841c7-191">If you skip this option, users who aren’t connected to your on-premises network must reset or unlock their AD DS passwords through an IT administrator.</span></span>

<span data-ttu-id="841c7-192">Se necessario, il [Passaggio 4](identity-add-user-accounts.md#identity-pw-writeback) può aiutare con questa opzione.</span><span class="sxs-lookup"><span data-stu-id="841c7-192">If needed, [Step 4](identity-add-user-accounts.md#identity-pw-writeback) can help you with this option.</span></span>

>[!Note]
><span data-ttu-id="841c7-193">Il writeback delle password è necessario per utilizzare al meglio le funzioni di Azure AD Identity Protection, come la richiesta agli utenti di cambiare le password locali nel caso in cui Azure AD rilevi un alto rischio di violazione dell'account.</span><span class="sxs-lookup"><span data-stu-id="841c7-193">Password writeback is required to fully utilize Azure AD Identity Protection features, such as requiring users to change their on-premises passwords when Azure AD has detected a high risk of account compromise.</span></span>
>

### <a name="how-to-test"></a><span data-ttu-id="841c7-194">Come eseguire il test</span><span class="sxs-lookup"><span data-stu-id="841c7-194">How to test</span></span>

<span data-ttu-id="841c7-195">Per testare il writeback delle password, è necessario cambiare la password in Office 365.</span><span class="sxs-lookup"><span data-stu-id="841c7-195">You test password writeback by changing your password in Office 365.</span></span> <span data-ttu-id="841c7-196">Dovrebbe essere possibile usare l'account e la nuova password per accedere alle risorse di AD DS locale.</span><span class="sxs-lookup"><span data-stu-id="841c7-196">You should be able to use your account and new password to access on-premises AD DS resources.</span></span>

1. <span data-ttu-id="841c7-197">Creare un account utente di test in AD DS locale, consentire la sincronizzazione delle directory e concedere una licenza di Microsoft 365 Enterprise nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="841c7-197">Create a test user account in your on-premises AD DS, allow directory synchronization to occur, and then grant it an Office 365 license in the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="841c7-198">Accedere al computer e al portale di Office con le credenziali dell'account utente di test da un computer remoto nel dominio AD DS locale.</span><span class="sxs-lookup"><span data-stu-id="841c7-198">From a remote computer that is joined to your on-premises AD DS domain, sign in to the computer and the Office portal using the credentials of the test user account.</span></span>
3. <span data-ttu-id="841c7-199">Selezionare **Impostazioni > Impostazioni di Office 365 > Password > Cambia password**.</span><span class="sxs-lookup"><span data-stu-id="841c7-199">Select **Settings > Office 365 settings > Password > Change password**.</span></span>
4. <span data-ttu-id="841c7-200">Digitare la password corrente, inserirne una nuova e quindi confermarla.</span><span class="sxs-lookup"><span data-stu-id="841c7-200">Type the current password, type a new password, and then confirm it.</span></span>
5. <span data-ttu-id="841c7-201">Disconnettersi dal portale di Office e dal computer remoto, quindi accedere al computer usando l'account utente di test e la relativa nuova password.</span><span class="sxs-lookup"><span data-stu-id="841c7-201">Sign out of the Office portal and the remote computer and then sign in to the computer using the test user account and its new password.</span></span> <span data-ttu-id="841c7-202">Questo passaggio dimostra che è stato possibile cambiare la password di un account utente di AD DS locale tramite il tenant di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="841c7-202">This proves that you were able to change the password of an on-premises AD DS user account using the Azure AD tenant.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="841c7-203">Come eseguire il test</span><span class="sxs-lookup"><span data-stu-id="841c7-203">How to test</span></span>

<span data-ttu-id="841c7-204">Accedere al portale di Office 365 con il nome dell'account utente e Azure Multi-Factor Authentication.</span><span class="sxs-lookup"><span data-stu-id="841c7-204">Sign in to the Office 365 portal with your user account name and Azure Multi-Factor Authentication.</span></span> <span data-ttu-id="841c7-205">Nella pagina di accesso dovrebbero essere visualizzati gli elementi di personalizzazione.</span><span class="sxs-lookup"><span data-stu-id="841c7-205">Sign in to the Office 365 portal with your user account name and multi-factor authentication. You should see your custom branding elements on the sign-in page.</span></span>


<a name="crit-identity-self-service-groups"></a>
## <a name="optional-self-service-group-management-is-enabled-for-specific-azure-ad-security-and-office-365-groups"></a><span data-ttu-id="841c7-206">Facoltativo: la gestione dei gruppi in modalità self-service è abilitata per specifici gruppi di sicurezza di Azure AD e Office 365</span><span class="sxs-lookup"><span data-stu-id="841c7-206">Optional: Self-service group management is enabled for specific Azure AD security and Office 365 groups</span></span>

<span data-ttu-id="841c7-207">È stato stabilito quali gruppi soddisfano i requisiti per la gestione in modalità self-service, i relativi proprietari sono stati istruiti sulle responsabilità e sul flusso di lavoro della gestione dei gruppi ed [è stata configurata la gestione in modalità self-service in Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management) per tali gruppi.</span><span class="sxs-lookup"><span data-stu-id="841c7-207">You've determined which groups are appropriate for self-service management, instructed their owners on group management workflow and responsibilities, and [set up self-service management in Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management) for those groups.</span></span>

<span data-ttu-id="841c7-208">Se si ignora questa opzione, tutte le attività di gestione dei gruppi di Azure AD, dovranno essere eseguite dagli amministratori IT.</span><span class="sxs-lookup"><span data-stu-id="841c7-208">If you skip this option, all Azure AD group management tasks must be done by IT administrators.</span></span>

<span data-ttu-id="841c7-209">Se necessario, il [Passaggio 5](identity-use-group-management.md#identity-self-service-groups) può aiutare con questa opzione.</span><span class="sxs-lookup"><span data-stu-id="841c7-209">If needed, [Step 5](identity-use-group-management.md#identity-self-service-groups) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="841c7-210">Come eseguire il test</span><span class="sxs-lookup"><span data-stu-id="841c7-210">How to test</span></span>
1.  <span data-ttu-id="841c7-211">Creare un account utente di test in Azure AD con il portale di Azure.</span><span class="sxs-lookup"><span data-stu-id="841c7-211">Create a test user account in Azure AD with the Azure portal.</span></span>
2.  <span data-ttu-id="841c7-212">Accedere con l'account utente di test e creare un gruppo di sicurezza di test di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="841c7-212">Sign-in as with the test user account and create a test Azure AD security group.</span></span>
3.  <span data-ttu-id="841c7-213">Disconnettersi ed effettuare di nuovo l'accesso con l'account amministratore IT.</span><span class="sxs-lookup"><span data-stu-id="841c7-213">Sign out and then sign-in with your IT administrator account.</span></span>
4.  <span data-ttu-id="841c7-214">Configurare il gruppo di sicurezza di test per la gestione in modalità self-service dell'account utente di test.</span><span class="sxs-lookup"><span data-stu-id="841c7-214">Configure the test security group for self-service management for the test user account.</span></span>
5.  <span data-ttu-id="841c7-215">Disconnettersi ed effettuare di nuovo l'accesso con l'account utente di test.</span><span class="sxs-lookup"><span data-stu-id="841c7-215">Sign out and then sign-in with your test user account.</span></span>
6.  <span data-ttu-id="841c7-216">Utilizzare il portale di Azure per aggiungere membri al gruppo di sicurezza di test.</span><span class="sxs-lookup"><span data-stu-id="841c7-216">Use the Azure portal to add members to the test security group.</span></span>
7.  <span data-ttu-id="841c7-217">Eliminare il gruppo di sicurezza di test e l'account utente di test.</span><span class="sxs-lookup"><span data-stu-id="841c7-217">Delete the test security group and the test user account.</span></span>

<a name="crit-identity-dyn-groups"></a>
## <a name="optional-dynamic-group-membership-settings-automatically-add-user-accounts-to-groups-based-on-user-account-attributes"></a><span data-ttu-id="841c7-218">Facoltativo: le impostazioni di appartenenza a gruppi dinamici aggiungono automaticamente gli account utente ai gruppi in base agli attributi degli account utente</span><span class="sxs-lookup"><span data-stu-id="841c7-218">Optional: Dynamic group membership settings automatically add user accounts to groups based on user account attributes</span></span>

<span data-ttu-id="841c7-219">È stato configurato il set di gruppi dinamici di Azure AD e sono state utilizzate le istruzioni presenti in [Creare regole basate su attributi per l'appartenenza dinamica ai gruppi in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal) per creare i gruppi e le regole che determinano il set di attributi dell'account utente e i valori di appartenenza ai gruppi.</span><span class="sxs-lookup"><span data-stu-id="841c7-219">You've determined the set of Azure AD dynamic groups and used the instructions in [Attribute-based dynamic group membership in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal) to create the groups and the rules that determine the set of user account attributes and values for group membership.</span></span>

<span data-ttu-id="841c7-p110">Se si ignora questa opzione, l'appartenenza ai gruppi deve essere eseguita manualmente quando vengono aggiunti nuovi account o se gli attributi degli account utente cambiano con il tempo. Ad esempio, se un utente passa dal Reparto vendite al Reparto contabilità, è necessario:</span><span class="sxs-lookup"><span data-stu-id="841c7-p110">If you skip this option, group membership must be done manually as new accounts are added or as user account attributes change over time. For example, if someone moves from the Sales department to the Accounting department, you must:</span></span>

- <span data-ttu-id="841c7-222">Aggiornare il valore dell'attributo del reparto per quell'account utente.</span><span class="sxs-lookup"><span data-stu-id="841c7-222">Update the value of the Department attribute for that user account.</span></span>
- <span data-ttu-id="841c7-223">Rimuovere manualmente l'account dal gruppo delle vendite.</span><span class="sxs-lookup"><span data-stu-id="841c7-223">Manually remove them from the Sales group.</span></span>
- <span data-ttu-id="841c7-224">Aggiungere manualmente l'account al gruppo della contabilità.</span><span class="sxs-lookup"><span data-stu-id="841c7-224">Manually add them to the Accounting group.</span></span>

<span data-ttu-id="841c7-225">Se il gruppo delle vendite e il gruppo della contabilità erano gruppi dinamici, sarà necessario solo cambiare il valore del reparto dell'account utente.</span><span class="sxs-lookup"><span data-stu-id="841c7-225">If the Sales and Accounting groups were dynamic, you would only have to change the user account’s Department value.</span></span>

<span data-ttu-id="841c7-226">Se necessario, il [Passaggio 5](identity-use-group-management.md#identity-dyn-groups) può aiutare con questa opzione.</span><span class="sxs-lookup"><span data-stu-id="841c7-226">If needed, [Step 5](identity-use-group-management.md#identity-dyn-groups) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="841c7-227">Come eseguire il test</span><span class="sxs-lookup"><span data-stu-id="841c7-227">How to test</span></span>

1. <span data-ttu-id="841c7-228">Creare un gruppo di test dinamico in Azure AD con il portale di Azure e configurare una regola il reparto uguale a "test1".</span><span class="sxs-lookup"><span data-stu-id="841c7-228">Create a test dynamic group in Azure AD with the Azure portal and configure a rule for the Department equals “test1”.</span></span>
2. <span data-ttu-id="841c7-229">Creare un account utente di test in Azure AD e impostare la proprietà del reparto su "test1".</span><span class="sxs-lookup"><span data-stu-id="841c7-229">Create a test user account in Azure AD and set the Department property to “test1”.</span></span>
3. <span data-ttu-id="841c7-230">Esaminare le proprietà dell'account utente per verificare che sia un membro del gruppo dinamico di test.</span><span class="sxs-lookup"><span data-stu-id="841c7-230">Examine the properties of the user account to ensure that it was made a member of the test dynamic group.</span></span>
4. <span data-ttu-id="841c7-231">Cambiare il valore della proprietà del reparto per l'account utente di test impostandolo su "test2".</span><span class="sxs-lookup"><span data-stu-id="841c7-231">Change the value of the Department property for the test user account to “test2”.</span></span>
5. <span data-ttu-id="841c7-232">Esaminare le proprietà dell'account utente per verificare che non sia più membro del gruppo dinamico di test.</span><span class="sxs-lookup"><span data-stu-id="841c7-232">Examine the properties of the user account to ensure that it is no longer a member of the test dynamic group.</span></span>
6. <span data-ttu-id="841c7-233">Eliminare il gruppo dinamico di test e l'account utente di test.</span><span class="sxs-lookup"><span data-stu-id="841c7-233">Delete the test dynamic group and the test user account.</span></span>

<a name="crit-identity-group-license"></a>
## <a name="optional-group-based-licensing-to-automatically-assign-and-remove-licenses-to-user-accounts-based-on-group-membership"></a><span data-ttu-id="841c7-234">Facoltativo: gestione delle licenze basate su gruppo per assegnare e rimuovere automaticamente le licenze degli account utente in base all'appartenenza ai gruppi</span><span class="sxs-lookup"><span data-stu-id="841c7-234">Optional: Group-based licensing to automatically assign and remove licenses to user accounts based on group membership</span></span>

<span data-ttu-id="841c7-235">È stata [abilitata la gestione delle licenze basate su gruppo](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal) per i gruppi di sicurezza di Azure AD appropriati, in modo che le licenze di Microsoft 365 Enterprise vengano assegnate o rimosse automaticamente.</span><span class="sxs-lookup"><span data-stu-id="841c7-235">You [enabled group-based licensing](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal) for the appropriate Azure AD security groups so that licenses for both Office 365 and EMS are automatically assigned or removed.</span></span>

<span data-ttu-id="841c7-236">Se si ignora questa opzione, sarà necessario eseguire manualmente i seguenti passaggi:</span><span class="sxs-lookup"><span data-stu-id="841c7-236">If you skip this option, you must manually:</span></span>

- <span data-ttu-id="841c7-237">Assegnare le licenze ai nuovi utenti che dovranno avere accesso.</span><span class="sxs-lookup"><span data-stu-id="841c7-237">Assign licenses to new users whom you intend to have access to Office 365 and EMS.</span></span>
- <span data-ttu-id="841c7-238">Rimuovere le licenze dagli utenti che non fanno più parte dell'organizzazione o non hanno accesso.</span><span class="sxs-lookup"><span data-stu-id="841c7-238">Remove licenses from users who are no longer with your organization or do not have access to Office 365 and EMS.</span></span>

<span data-ttu-id="841c7-239">Se necessario, il [Passaggio 5](identity-use-group-management.md#identity-group-license) può aiutare con questa opzione.</span><span class="sxs-lookup"><span data-stu-id="841c7-239">If needed, [Step 5](identity-use-group-management.md#identity-group-license) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="841c7-240">Come eseguire il test</span><span class="sxs-lookup"><span data-stu-id="841c7-240">How to test</span></span>

1. <span data-ttu-id="841c7-241">Creare un gruppo di sicurezza di test in Azure AD con il portale di Azure e configurare la gestione delle licenze basate su gruppo per assegnare la licenza di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="841c7-241">Create a test security group in Azure AD with the Azure portal and configure group-based licensing to assign Office 365 and EMS licenses.</span></span>
2. <span data-ttu-id="841c7-242">Creare un account utente di test in Azure AD e aggiungerlo al gruppo di sicurezza di test.</span><span class="sxs-lookup"><span data-stu-id="841c7-242">Create a test user account in Azure AD and add it to the test security group.</span></span>
3. <span data-ttu-id="841c7-243">Esaminare le proprietà dell'account utente nell'interfaccia di amministrazione di Microsoft 365 per verificare che la licenza di Microsoft 365 Enterprise sia stata assegnata.</span><span class="sxs-lookup"><span data-stu-id="841c7-243">Examine the properties of the user account in the Microsoft 365 admin center to ensure that it was assigned the Office 365 and EMS licenses.</span></span>
4. <span data-ttu-id="841c7-244">Rimuovere l'account utente di test dal gruppo di sicurezza di test.</span><span class="sxs-lookup"><span data-stu-id="841c7-244">Remove the test user account from the test security group.</span></span>
5. <span data-ttu-id="841c7-245">Esaminare le proprietà dell'account utente per verificare che non disponga più della licenza di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="841c7-245">Examine the properties of the user account to ensure that it no longer has the Office 365 and EMS licenses assigned.</span></span>
6. <span data-ttu-id="841c7-246">Eliminare il gruppo di sicurezza di test e l'account utente di test.</span><span class="sxs-lookup"><span data-stu-id="841c7-246">Delete the test security group and the test user account.</span></span>


<a name="crit-identity-access-reviews"></a>
## <a name="optional-access-reviews-configured-and-being-used-to-monitor-access"></a><span data-ttu-id="841c7-247">Facoltativo: verifiche di accesso configurate e usate per monitorare l'accesso</span><span class="sxs-lookup"><span data-stu-id="841c7-247">Optional: Access reviews configured and being used to monitor access</span></span>

<span data-ttu-id="841c7-248">Sono stati usati questi articoli per configurare tipi diversi di verifiche di accesso per il monitoraggio dell'appartenenza a gruppi, dell'accesso alle applicazioni aziendali e delle assegnazioni di ruolo:</span><span class="sxs-lookup"><span data-stu-id="841c7-248">You have used these articles to configure different types of access reviews to monitor group memberships, access to enterprise applications, and role assignments:</span></span>

- [<span data-ttu-id="841c7-249">Gruppi e app</span><span class="sxs-lookup"><span data-stu-id="841c7-249">Groups and apps</span></span>](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [<span data-ttu-id="841c7-250">Ruoli di Azure AD</span><span class="sxs-lookup"><span data-stu-id="841c7-250">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [<span data-ttu-id="841c7-251">Ruoli delle risorse di Azure</span><span class="sxs-lookup"><span data-stu-id="841c7-251">Azure resource roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

<span data-ttu-id="841c7-252">Se necessario, il [Passaggio 6](identity-configure-identity-governance.md#identity-access-reviews) può aiutare con questa opzione.</span><span class="sxs-lookup"><span data-stu-id="841c7-252">If needed, [Step 6](identity-configure-identity-governance.md#identity-access-reviews) can help you with this option.</span></span>


## <a name="results-and-next-steps"></a><span data-ttu-id="841c7-253">Risultati e passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="841c7-253">Results and next steps</span></span>

<span data-ttu-id="841c7-254">L'infrastruttura di gestione delle identità nel cloud Microsoft 365 usa l'autenticazione avanzata, account amministratore protetti e funzionalità semplificate di accesso e gestione utenti.</span><span class="sxs-lookup"><span data-stu-id="841c7-254">Your identity infrastructure in the Microsoft 365 cloud uses strong authentication, protected administrator accounts, and simplified user access and management.</span></span>

|||
|:-------|:-----|
|![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)| <span data-ttu-id="841c7-255">Se si stanno seguendo le fasi per la distribuzione end-to-end di Microsoft 365 Enterprise, la fase successiva è [Windows 10 Enterprise](windows10-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="841c7-255">If you're following the phases for the end-to-end deployment of Microsoft 365 Enterprise, your next phase is [Windows 10 Enterprise](windows10-infrastructure.md).</span></span> |

