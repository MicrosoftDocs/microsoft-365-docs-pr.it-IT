---
title: "Fase 2: criteri uscita dell'infrastruttura di rete"
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/06/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Verificare che la configurazione soddisfi i criteri di Microsoft 365 Enterprise per l'infrastruttura e i servizi basati sull'identità.
ms.openlocfilehash: 4621c9e12519e39931fe8b883b3a8c446c39dae3
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2019
ms.locfileid: "36981857"
---
# <a name="phase-2-identity-infrastructure-exit-criteria"></a><span data-ttu-id="ddd15-103">Fase 2: criteri uscita dell'infrastruttura di rete</span><span class="sxs-lookup"><span data-stu-id="ddd15-103">Phase 2: Identity infrastructure exit criteria</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="ddd15-104">Verificare che l'infrastruttura di rete soddisfi i criteri obbligatori seguenti e assicurarsi di tenere in considerazione quelli facoltativi.</span><span class="sxs-lookup"><span data-stu-id="ddd15-104">Make sure your identity infrastructure meets the following required criteria and that you've considered those that are optional.</span></span>

<span data-ttu-id="ddd15-105">Vedere anche [Prerequisiti](https://docs.microsoft.com/microsoft-365-enterprise/identity-access-policies#prerequisites) per ulteriori consigli sull'infrastruttura di gestione delle identità.</span><span class="sxs-lookup"><span data-stu-id="ddd15-105">Also see [Prerequisites](https://docs.microsoft.com/microsoft-365-enterprise/identity-access-policies#prerequisites) for additional recommendations on identity infrastructure.</span></span>

<a name="crit-identity-user-groups"></a>
## <a name="required-your-users-groups-and-group-memberships-have-been-created"></a><span data-ttu-id="ddd15-106">Obbligatorio: sono stati creati gli utenti, i gruppi e l'appartenenza ai gruppi</span><span class="sxs-lookup"><span data-stu-id="ddd15-106">Required: All users, groups, and group memberships have been created</span></span>

<span data-ttu-id="ddd15-107">Gli account e i gruppi utente sono stati creati in modo che:</span><span class="sxs-lookup"><span data-stu-id="ddd15-107">You've created user accounts and groups so that:</span></span>

- <span data-ttu-id="ddd15-108">I dipendenti, i fornitori, i terzisti e i partner dell'organizzazione abbiano un account utente corrispondente in Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="ddd15-108">Employees in your organization and the vendors, contractors, and partners that work for or with your organization have a corresponding user account in Azure Active Directory (Azure AD).</span></span>
- <span data-ttu-id="ddd15-109">I gruppi di Azure AD e i relativi membri contengano account utente e altri gruppi per scopi diversi, come il provisioning delle impostazioni di sicurezza per i servizi cloud Microsoft, la gestione delle licenze automatica e altri utilizzi.</span><span class="sxs-lookup"><span data-stu-id="ddd15-109">Azure AD groups and their members contain user accounts and other groups for various purposes, such as the provisioning of security settings for Microsoft cloud services, automatic licensing, and other uses.</span></span>

<span data-ttu-id="ddd15-110">Se necessario, il [Passaggio 1](identity-plan-users-groups.md) può aiutare a soddisfare questo requisito.</span><span class="sxs-lookup"><span data-stu-id="ddd15-110">If needed, [Step 1](identity-plan-users-groups.md) can help you meet this requirement.</span></span>

<a name="crit-identity-global-admin"></a>
## <a name="required-your-global-administrator-accounts-are-protected"></a><span data-ttu-id="ddd15-111">Obbligatorio: gli account di amministratore globale sono protetti</span><span class="sxs-lookup"><span data-stu-id="ddd15-111">Required: Your global administrator accounts are protected</span></span> 

<span data-ttu-id="ddd15-112">Gli [account di amministratore globale di Office 365 sono stati protetti](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts) per contrastare la possibile compromissione delle credenziali da parte di malintenzionati, che potrebbe condurre a violazioni dell’abbonamento a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ddd15-112">You've [protected your Office 365 global administrator accounts](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts) to thwart  credential compromise by attackers that can lead to breaches of your Microsoft 365 subscription.</span></span>

<span data-ttu-id="ddd15-113">Se si ignora questo requisito, gli account di amministratore globale potrebbero essere soggetti ad attacchi e violazioni, consentendo a terzi l'acquisizione di dati e l'utilizzo di tali informazioni per scopi di raccolta, distruzione o ricatto.</span><span class="sxs-lookup"><span data-stu-id="ddd15-113">If you skip this requirement, your global administrator accounts can be susceptible to attack and compromise, allowing an attacker to gain system-wide access to your data for harvesting, destruction, or ransom.</span></span>

<span data-ttu-id="ddd15-114">Se necessario, il [Passaggio 2](identity-designate-protect-admin-accounts.md#identity-global-admin) può aiutare a soddisfare questo requisito.</span><span class="sxs-lookup"><span data-stu-id="ddd15-114">If needed, [Step 2](identity-designate-protect-admin-accounts.md#identity-global-admin) can help you meet this requirement.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="ddd15-115">Come eseguire il test</span><span class="sxs-lookup"><span data-stu-id="ddd15-115">How to test</span></span>

<span data-ttu-id="ddd15-116">Utilizzare questa procedura per verificare che gli account di amministratore globale siano protetti:</span><span class="sxs-lookup"><span data-stu-id="ddd15-116">Use these steps to verify that you've protected your global administrator accounts:</span></span>

1. <span data-ttu-id="ddd15-p101">Eseguire il seguente comando di Azure Active Directory PowerShell for Graph dal prompt dei comandi di PowerShell. Dovrebbe essere visualizzato solo l'elenco degli account di amministratore globale dedicati.</span><span class="sxs-lookup"><span data-stu-id="ddd15-p101">Run the following Azure AD V2 command at the PowerShell command prompt. You should see only the list of dedicated global administrator accounts.</span></span>
   ```
   Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
   ```
2. <span data-ttu-id="ddd15-p102">Accedere a Office 365 utilizzando ognuno degli account del Passaggio 1. Ogni accesso dovrà richiedere l'autenticazione a più fattori e la forma più avanzata di autenticazione secondaria disponibile nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ddd15-p102">Sign in to Office 365 using each of the accounts from step 1. Each sign in must require multi-factor authentication and the strongest form of secondary authentication available in your organization.</span></span>

> [!Note]
> <span data-ttu-id="ddd15-121">Vedere [Connettersi a PowerShell di Office 365](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) per le istruzioni sull'istallazione del modulo Azure Active Directory PowerShell for Graph e sull'accesso a Office 365.</span><span class="sxs-lookup"><span data-stu-id="ddd15-121">See [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) for instructions on installing the Azure Active Directory PowerShell for Graph module and signing in to Office 365.</span></span>

<a name="crit-identity-pim"></a>
## <a name="optional-you-have-set-up-privileged-identity-management-to-support-on-demand-assignment-of-the-global-administrator-role"></a><span data-ttu-id="ddd15-122">Facoltativo: è stato configurato Privileged Identity Management per supportare l'assegnazione su richiesta del ruolo di amministratore globale</span><span class="sxs-lookup"><span data-stu-id="ddd15-122">Optional: You have set up Privileged Identity Management to support on-demand assignment of the global administrator role</span></span>

<span data-ttu-id="ddd15-123">Sono state seguite le istruzioni presenti in [Configurare Azure AD Privileged Identity Management (PIM)](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure) per abilitare PIM nel tenant di Azure AD e sono stati configurati gli account di amministratore globale idonei per il ruolo di amministratori.</span><span class="sxs-lookup"><span data-stu-id="ddd15-123">You've used the instructions in [Configure Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure) to enable PIM in your Azure AD tenant and configured your global administrator accounts as eligible admins.</span></span>

<span data-ttu-id="ddd15-124">Inoltre, sono stati seguiti i consigli presenti in [Protezione dell'accesso con privilegi per le distribuzioni ibride e cloud in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices) per sviluppare una roadmap che protegga l'accesso con privilegi dagli attacchi informatici.</span><span class="sxs-lookup"><span data-stu-id="ddd15-124">You've also used the recommendations in [Securing privileged access for hybrid and cloud deployments in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices) to develop a roadmap that secures privileged access against cyber attackers.</span></span>

<span data-ttu-id="ddd15-125">Se si ignora questa opzione, gli account di amministratore globale potranno essere soggetti ad attacco online e, se violati, un utente malintenzionato potrà raccogliere, distruggere o conservare le informazioni riservate a scopo di ricatto.</span><span class="sxs-lookup"><span data-stu-id="ddd15-125">If you skip this option, your global administrator accounts are subject to ongoing online attack and, if compromised, can allow an attacker to harvest, destroy, or hold your sensitive information for ransom.</span></span>

<span data-ttu-id="ddd15-126">Se necessario, il [Passaggio 2](identity-designate-protect-admin-accounts.md#identity-pim) può aiutare con questa opzione.</span><span class="sxs-lookup"><span data-stu-id="ddd15-126">If needed, [Step 2](identity-designate-protect-admin-accounts.md#identity-pim) can help you with this option.</span></span>


<a name="crit-identity-sync"></a>
## <a name="required-users-and-groups-are-synchronized-with-azure-ad"></a><span data-ttu-id="ddd15-127">Obbligatorio: gli utenti e i gruppi sono sincronizzati con Azure AD</span><span class="sxs-lookup"><span data-stu-id="ddd15-127">Required: Users and groups are synchronized with Azure AD</span></span>

<span data-ttu-id="ddd15-128">Se si dispone di un'istanza locale di Active Directory Domain Services (AD DS), è stato usato Azure AD Connect per sincronizzare i gruppi e gli account utente dall'ambiente AD DS locale al tenant di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="ddd15-128">If you have an existing on-premises identity provider, such as Active Directory Domain Services (AD DS), you have used Azure AD Connect to synchronize user accounts and groups from your on-premises identity provider to your Azure AD tenant.</span></span>

<span data-ttu-id="ddd15-129">Grazie alla sincronizzazione della directory, gli utenti possono accedere a Office 365 e agli altri servizi cloud Microsoft utilizzando le stesse credenziali che usano per l'accesso ai loro computer e alle risorse locali.</span><span class="sxs-lookup"><span data-stu-id="ddd15-129">With directory synchronization, your users can sign in to Office 365 and other Microsoft cloud services using the same credentials that they use to sign in to their computers and access on-premises resources.</span></span>

<span data-ttu-id="ddd15-130">Se necessario, il [Passaggio 3](identity-azure-ad-connect.md#identity-sync) può aiutare a soddisfare questo requisito.</span><span class="sxs-lookup"><span data-stu-id="ddd15-130">If needed, [Step 3](identity-azure-ad-connect.md#identity-sync) can help you meet this requirement.</span></span>

<span data-ttu-id="ddd15-131">Se si ignora questo requisito, saranno disponibili due set di account utente e gruppi:</span><span class="sxs-lookup"><span data-stu-id="ddd15-131">If you skip this requirement, you’ll have two sets of user accounts and groups:</span></span>

- <span data-ttu-id="ddd15-132">Gli account utente e i gruppi esistenti nell'ambiente AD DS locale</span><span class="sxs-lookup"><span data-stu-id="ddd15-132">User accounts and groups that exist in your on-premises identity provider</span></span>
- <span data-ttu-id="ddd15-133">Gli account utente e i gruppi esistenti nel tenant di Azure AD</span><span class="sxs-lookup"><span data-stu-id="ddd15-133">User accounts and groups that exist in your Azure AD tenant</span></span>

<span data-ttu-id="ddd15-p103">In questo stato, i due set di account e gruppi utente dovranno essere gestiti manualmente sia dagli utenti che dagli amministratori IT. Questo comporterà inevitabilmente la mancata sincronizzazione di account, password e gruppi.</span><span class="sxs-lookup"><span data-stu-id="ddd15-p103">In this state, the two sets of user accounts and groups must be manually maintained by both IT administrators and users. This will inevitably lead to unsynchronized accounts, their passwords, and groups.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="ddd15-136">Come eseguire il test</span><span class="sxs-lookup"><span data-stu-id="ddd15-136">How to test</span></span>
<span data-ttu-id="ddd15-137">Per verificare il corretto funzionamento dell'autenticazione con le credenziali locali, accedere al portale di Office con le credenziali locali.</span><span class="sxs-lookup"><span data-stu-id="ddd15-137">To verify that authentication with on-premises credentials works correctly, sign in to the Office portal with your on-premises credentials.</span></span>

<span data-ttu-id="ddd15-138">Per verificare il corretto funzionamento della sincronizzazione della directory, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ddd15-138">To verify that directory synchronization is working correctly, do the following:</span></span>

1.  <span data-ttu-id="ddd15-139">Creare un nuovo gruppo di test in AD DS.</span><span class="sxs-lookup"><span data-stu-id="ddd15-139">Create a new test group in AD DS.</span></span>
2.  <span data-ttu-id="ddd15-140">Attendere la sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="ddd15-140">Wait for the synchronization time.</span></span>
3.  <span data-ttu-id="ddd15-141">Controllare il tenant di Azure AD per verificare che venga visualizzato il nome del nuovo gruppo di test.</span><span class="sxs-lookup"><span data-stu-id="ddd15-141">Check your Azure AD tenant to verify that the new test group name appears.</span></span>

<a name="crit-identity-sync-health"></a>
## <a name="optional-directory-synchronization-is-monitored"></a><span data-ttu-id="ddd15-142">Facoltativo: la sincronizzazione delle directory viene monitorata</span><span class="sxs-lookup"><span data-stu-id="ddd15-142">Optional: Directory synchronization is monitored</span></span>

<span data-ttu-id="ddd15-143">È stata consultata la documentazione disponibile in [Uso di Azure AD Connect Health per la sincronizzazione](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) (per la sincronizzazione delle password) o in [Uso di Azure AD Connect Health con AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) (per l'autenticazione federata) ed è stato implementato Azure AD Connect Health, che implica quanto segue:</span><span class="sxs-lookup"><span data-stu-id="ddd15-143">You've used [Azure AD Connect Health with sync](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) (for password synchronization) or [Using Azure AD Connect Health with AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) (for federated authentication) and have deployed Azure AD Connect Health, which involves:</span></span>

- <span data-ttu-id="ddd15-144">L'installazione dell'agente di Azure AD Connect Health su ciascuno dei server di identità locale.</span><span class="sxs-lookup"><span data-stu-id="ddd15-144">Installing the Azure AD Connect Health agent on each of your on-premises identity servers.</span></span>
- <span data-ttu-id="ddd15-145">L'utilizzo del portale di Azure AD Connect Health per monitorare lo stato della sincronizzazione in corso.</span><span class="sxs-lookup"><span data-stu-id="ddd15-145">Using the Azure AD Connect Health portal to monitor the state of the ongoing synchronization.</span></span>

<span data-ttu-id="ddd15-146">Se si ignora questa opzione, è possibile valutare in maniera più precisa lo stato dell'infrastruttura di gestione delle identità basata sul cloud.</span><span class="sxs-lookup"><span data-stu-id="ddd15-146">If you skip this option, you can more accurately assess the state of your cloud-based identity infrastructure.</span></span>

<span data-ttu-id="ddd15-147">Se necessario, il [Passaggio 3](identity-azure-ad-connect.md#identity-sync-health) può aiutare con questa opzione.</span><span class="sxs-lookup"><span data-stu-id="ddd15-147">If needed, [Step 3](identity-azure-ad-connect.md#identity-sync-health) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="ddd15-148">Come eseguire il test</span><span class="sxs-lookup"><span data-stu-id="ddd15-148">How to test</span></span>
<span data-ttu-id="ddd15-149">Il portale di Azure AD Connect Health mostra lo stato attuale e corretto dei controller di dominio locali e la sincronizzazione in corso.</span><span class="sxs-lookup"><span data-stu-id="ddd15-149">The Azure AD Connect Health portal shows the current and correct state of your on-premises identity servers and the ongoing synchronization.</span></span>

<a name="crit-identity-mfa"></a>
## <a name="optional-multi-factor-authentication-is-enabled-for-your-users"></a><span data-ttu-id="ddd15-150">Facoltativo: l'autenticazione a più fattori è abilitata per gli utenti</span><span class="sxs-lookup"><span data-stu-id="ddd15-150">Optional: Multi-factor authentication is enabled for your users</span></span>

<span data-ttu-id="ddd15-151">Sono stati usati la [Pianificazione per l'autenticazione a più fattori](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted) e i [criteri di accesso condizionale](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access) per abilitare l'autenticazione a più fattori (MFA) per gli account utente.</span><span class="sxs-lookup"><span data-stu-id="ddd15-151">You used [Plan for multi-factor authentication](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted) and [conditional access policies](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access) to enable multi-factor authentication (MFA) for your user accounts.</span></span>

<span data-ttu-id="ddd15-p104">Se si ignora questa opzione, gli account utente saranno vulnerabili alla violazione delle credenziali ad opera di possibili attacchi informatici. In caso di violazione della password di un account utente, tutte le risorse e le funzionalità dell'account (come i ruoli di amministratore) saranno a disposizione dell'utente malintenzionato, che potrà copiare, distruggere o conservare a scopo di ricatto documenti interni o altri dati.</span><span class="sxs-lookup"><span data-stu-id="ddd15-p104">If you skip this option, your user accounts are vulnerable to credential compromise by cyber attackers. If a user account’s password is compromised, all the resources and capabilities of the account, such as administrator roles, are available to the attacker. This allows the attacker to copy, destroy, or hold for ransom internal documents and other data.</span></span>

<span data-ttu-id="ddd15-155">Se necessario, il [Passaggio 4](identity-multi-factor-authentication.md#identity-mfa) può aiutare con questa opzione.</span><span class="sxs-lookup"><span data-stu-id="ddd15-155">If needed, [Step 4](identity-multi-factor-authentication.md#identity-mfa) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="ddd15-156">Come eseguire il test</span><span class="sxs-lookup"><span data-stu-id="ddd15-156">How to test</span></span>

1.  <span data-ttu-id="ddd15-157">Creare un account utente di test e assegnargli una licenza.</span><span class="sxs-lookup"><span data-stu-id="ddd15-157">Create a test user account in the Office 365 Admin portal and assign them a license.</span></span> 
2.  <span data-ttu-id="ddd15-158">Configurare l'autenticazione a più fattori per l'account utente di test con il metodo di verifica aggiuntivo in uso per gli account utente effettivi, come per esempio l'invio di un SMS al telefono.</span><span class="sxs-lookup"><span data-stu-id="ddd15-158">Configure multi-factor authentication for the test user account with the additional verification method that you are using for actual user accounts, such as sending a message to your phone.</span></span> 
3.  <span data-ttu-id="ddd15-159">Accedere al portale di Office 36 con l'account utente di test.</span><span class="sxs-lookup"><span data-stu-id="ddd15-159">Sign in to the Office 365 or Azure portal with the test user account.</span></span>
4.  <span data-ttu-id="ddd15-160">Verificare che l'autenticazione a più fattori richieda all'utente ulteriori informazioni di verifica e abbia esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ddd15-160">Verify that MFA prompts you for the additional verification information and results in a successful authentication.</span></span> 
5.  <span data-ttu-id="ddd15-161">Eliminare l'account utente di test.</span><span class="sxs-lookup"><span data-stu-id="ddd15-161">Delete the test user account.</span></span>

<a name="crit-password-prot"></a>
## <a name="optional-azure-ad-password-protection-is-banning-the-use-of-weak-passwords"></a><span data-ttu-id="ddd15-162">Facoltativo: la protezione con password di Azure Active Directory impedisce l'uso di password vulnerabili</span><span class="sxs-lookup"><span data-stu-id="ddd15-162">Optional: Azure AD password protection is banning the use of weak passwords</span></span>

<span data-ttu-id="ddd15-163">È stata abilitata l'esclusione delle password non appropriate [nel cloud](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) e nell'ambiente [Active Directory Domain Services (AD DS) locale](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises) per le password escluse a livello globale e, facoltativamente, per termini personalizzati.</span><span class="sxs-lookup"><span data-stu-id="ddd15-163">You have enabled the banning of bad passwords [in the cloud](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) and for your [on-premises Active Directory Domain Services (AD DS)](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises) for global banned passwords and, optionally, for custom terms.</span></span>

<span data-ttu-id="ddd15-164">Se necessario, il [Passaggio 4](identity-multi-factor-authentication.md#identity-password-prot) può aiutare con questa opzione.</span><span class="sxs-lookup"><span data-stu-id="ddd15-164">If needed, [Step 4](identity-multi-factor-authentication.md#identity-password-prot) can help you with this option.</span></span>

<a name="crit-identity-ident-prot"></a>
## <a name="optional-azure-ad-identity-protection-is-enabled-to-protect-against-credential-compromise-microsoft-365-enterprise-e5-only"></a><span data-ttu-id="ddd15-165">Facoltativo: Azure AD Identity Protection è abilitato per proteggere le credenziali da eventuali violazioni (solo Microsoft 365 Enterprise E5)</span><span class="sxs-lookup"><span data-stu-id="ddd15-165">Optional: Azure AD Identity Protection is enabled to protect against credential compromise</span></span>

<span data-ttu-id="ddd15-166">Azure AD Identity Protection è stato abilitato per:</span><span class="sxs-lookup"><span data-stu-id="ddd15-166">You've enabled Azure AD Identity Protection to:</span></span>

- <span data-ttu-id="ddd15-167">Far fronte a potenziali vulnerabilità delle identità.</span><span class="sxs-lookup"><span data-stu-id="ddd15-167">Address potential identity vulnerabilities.</span></span>
- <span data-ttu-id="ddd15-168">Rilevare possibili tentativi di violazione delle credenziali.</span><span class="sxs-lookup"><span data-stu-id="ddd15-168">Detect possible credential compromise attempts.</span></span>
- <span data-ttu-id="ddd15-169">Ricercare le cause e risolvere attività sospette relative alle identità.</span><span class="sxs-lookup"><span data-stu-id="ddd15-169">Investigate and address ongoing suspicious identity incidents.</span></span>

<span data-ttu-id="ddd15-p105">Se si ignora questa opzione, non sarà possibile rilevare o contrastare tentativi di violazione delle credenziali o ricercare le cause dei problemi di sicurezza relativi alle identità. Questo potrebbe rendere l'organizzazione vulnerabile alla violazione delle credenziali e alla conseguente minaccia ai dati sensibili.</span><span class="sxs-lookup"><span data-stu-id="ddd15-p105">If you skip this option, you won’t be able to detect or automatically thwart credential compromise attempts or investigate identity-related security incidents. This potentially leaves your organization vulnerable to a successful credential compromise and the resulting threat to your organization’s sensitive data.</span></span>

<span data-ttu-id="ddd15-172">Se necessario, il [Passaggio 4](identity-multi-factor-authentication.md#identity-ident-prot) può aiutare con questa opzione.</span><span class="sxs-lookup"><span data-stu-id="ddd15-172">If needed, [Step 4](identity-multi-factor-authentication.md#identity-ident-prot) can help you with this option.</span></span>

<a name="crit-identity-pw-reset"></a>
## <a name="optional-users-can-reset-their-own-passwords"></a><span data-ttu-id="ddd15-173">Facoltativo: gli utenti possono reimpostare la propria password</span><span class="sxs-lookup"><span data-stu-id="ddd15-173">Optional: Users can reset their own passwords</span></span>

<span data-ttu-id="ddd15-174">È stata utilizzata la procedura descritta in [Distribuzione rapida della reimpostazione della password self-service di Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) per configurare la reimpostazione della password per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="ddd15-174">You've used [Azure AD self-service password reset rapid deployment](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) to configure password reset for your users.</span></span>

<span data-ttu-id="ddd15-175">Se non si soddisfa questa condizione, gli utenti dovranno dipendere dagli amministratori degli account utente per reimpostare le proprie password, con un sovraccarico sull'amministrazione IT.</span><span class="sxs-lookup"><span data-stu-id="ddd15-175">If you don’t meet this condition, users will be dependent on user account administrators to reset their passwords, resulting in additional IT administration overhead.</span></span>

<span data-ttu-id="ddd15-176">Se necessario, il [Passaggio 5](identity-password-reset.md#identity-pw-reset) può aiutare con questa opzione.</span><span class="sxs-lookup"><span data-stu-id="ddd15-176">If needed, [Step 5](identity-password-reset.md#identity-pw-reset) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="ddd15-177">Come eseguire il test</span><span class="sxs-lookup"><span data-stu-id="ddd15-177">How to test</span></span>

1. <span data-ttu-id="ddd15-178">Creare un account utente di test con una password iniziale.</span><span class="sxs-lookup"><span data-stu-id="ddd15-178">Create a test user account with an initial password.</span></span>
2. <span data-ttu-id="ddd15-179">Utilizzare i passaggi illustrati in [Consentire agli utenti di reimpostare le loro password in Office 365](https://docs.microsoft.com/office365/admin/add-users/let-users-reset-passwords) per reimpostare la password dell'account utente di test.</span><span class="sxs-lookup"><span data-stu-id="ddd15-179">Use the steps in [Let users reset their own passwords in Office 365](https://docs.microsoft.com/office365/admin/add-users/let-users-reset-passwords) to reset the password on the test user account.</span></span>
3. <span data-ttu-id="ddd15-180">Disconnettersi ed effettuare di nuovo l'accesso con l'account utente di test con la nuova password.</span><span class="sxs-lookup"><span data-stu-id="ddd15-180">Sign out and then sign in to the test user account using the reset password.</span></span>
4. <span data-ttu-id="ddd15-181">Eliminare l'account utente di test.</span><span class="sxs-lookup"><span data-stu-id="ddd15-181">Delete the test user account.</span></span>

<a name="crit-identity-pw-writeback"></a>
## <a name="optional-password-writeback-is-enabled-for-your-users"></a><span data-ttu-id="ddd15-182">Facoltativo: il writeback delle password è abilitato per gli utenti</span><span class="sxs-lookup"><span data-stu-id="ddd15-182">Optional: Password writeback is enabled for your users</span></span>

<span data-ttu-id="ddd15-183">Sono state utilizzate le istruzioni riportate in [Reimpostazione delle password in modalità self-service di Azure AD con writeback delle password](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) per abilitare il writeback delle password per il tenant di Azure AD per la sottoscrizione di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="ddd15-183">You've used the instructions in [Azure AD SSPR with password writeback](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) to enable password writeback for the Azure AD tenant of your Microsoft 365 Enterprise subscription.</span></span>

<span data-ttu-id="ddd15-184">Se si ignora questa opzione, gli utenti che non sono connessi con il server locale devono reimpostare o sbloccare le password dei AD DS tramite un amministratore IT.</span><span class="sxs-lookup"><span data-stu-id="ddd15-184">If you skip this option, users who aren’t connected to your on-premises network must reset or unlock their AD DS passwords through an IT administrator.</span></span>

<span data-ttu-id="ddd15-185">Se necessario, il [Passaggio 5](identity-password-reset.md#identity-pw-writeback) può aiutare con questa opzione.</span><span class="sxs-lookup"><span data-stu-id="ddd15-185">If needed, [Step 5](identity-password-reset.md#identity-pw-writeback) can help you with this option.</span></span>

>[!Note]
><span data-ttu-id="ddd15-186">Il writeback delle password è necessario per utilizzare al meglio le funzioni di Azure AD Identity Protection, come la richiesta agli utenti di cambiare le password locali nel caso in cui Azure AD rilevi un alto rischio di violazione dell'account.</span><span class="sxs-lookup"><span data-stu-id="ddd15-186">Password writeback is required to fully utilize Azure AD Identity Protection features, such as requiring users to change their on-premises passwords when Azure AD has detected a high risk of account compromise.</span></span>
>

### <a name="how-to-test"></a><span data-ttu-id="ddd15-187">Come eseguire il test</span><span class="sxs-lookup"><span data-stu-id="ddd15-187">How to test</span></span>

<span data-ttu-id="ddd15-188">Per testare il writeback delle password, è necessario cambiare la password in Office 365.</span><span class="sxs-lookup"><span data-stu-id="ddd15-188">You test password writeback by changing your password in Office 365.</span></span> <span data-ttu-id="ddd15-189">Dovrebbe essere possibile usare l'account e la nuova password per accedere alle risorse di AD DS locale.</span><span class="sxs-lookup"><span data-stu-id="ddd15-189">You should be able to use your account and new password to access on-premises AD DS resources.</span></span>

1. <span data-ttu-id="ddd15-190">Creare un account utente di test in AD DS locale, consentire la sincronizzazione delle directory e concedere una licenza di Microsoft 365 Enterprise nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ddd15-190">Create a test user account in your on-premises AD DS, allow directory synchronization to occur, and then grant it an Office 365 license in the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="ddd15-191">Accedere al computer e al portale di Office con le credenziali dell'account utente di test da un computer remoto nel dominio AD DS locale.</span><span class="sxs-lookup"><span data-stu-id="ddd15-191">From a remote computer that is joined to your on-premises AD DS domain, sign in to the computer and the Office portal using the credentials of the test user account.</span></span>
3. <span data-ttu-id="ddd15-192">Selezionare **Impostazioni > Impostazioni di Office 365 > Password > Cambia password**.</span><span class="sxs-lookup"><span data-stu-id="ddd15-192">Select **Settings > Office 365 settings > Password > Change password**.</span></span>
4. <span data-ttu-id="ddd15-193">Digitare la password corrente, inserirne una nuova e quindi confermarla.</span><span class="sxs-lookup"><span data-stu-id="ddd15-193">Type the current password, type a new password, and then confirm it.</span></span>
5. <span data-ttu-id="ddd15-194">Disconnettersi dal portale di Office e dal computer remoto, quindi accedere al computer usando l'account utente di test e la relativa nuova password.</span><span class="sxs-lookup"><span data-stu-id="ddd15-194">Sign out of the Office portal and the remote computer and then sign in to the computer using the test user account and its new password.</span></span> <span data-ttu-id="ddd15-195">Questo passaggio dimostra che è stato possibile cambiare la password di un account utente di AD DS locale tramite il tenant di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="ddd15-195">This proves that you were able to change the password of an on-premises AD DS user account using the Azure AD tenant.</span></span>

<a name="crit-identity-sso"></a>
## <a name="optional-users-can-sign-in-using-azure-ad-seamless-single-sign-on"></a><span data-ttu-id="ddd15-196">Facoltativo: gli utenti possono accedere usando la funzionalità Accesso Single Sign-On facile di Azure AD</span><span class="sxs-lookup"><span data-stu-id="ddd15-196">Optional: Users can sign in using Azure AD Seamless Single Sign-on</span></span>

<span data-ttu-id="ddd15-197">È stato abilitato [Azure AD Connect: accesso Single Sign-On facile](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start) per l'organizzazione, con lo scopo di semplificare l'accesso degli utenti alle applicazioni basate sul cloud, come Office 365.</span><span class="sxs-lookup"><span data-stu-id="ddd15-197">You enabled [Azure AD Connect: Seamless Single Sign-On](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start) for your organization to simplify how users sign in to cloud-based applications, such as Office 365.</span></span>

<span data-ttu-id="ddd15-198">Se si ignora questa opzione, gli utenti potrebbero dover immettere le credenziali quando accedono alle applicazioni aggiuntive che usano il tenant di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="ddd15-198">If you skip this option, your users might be prompted to provide credentials when they access additional applications that use Azure AD.</span></span>

<span data-ttu-id="ddd15-199">Se necessario, il [Passaggio 5](identity-password-reset.md#identity-sso) può aiutare con questa opzione.</span><span class="sxs-lookup"><span data-stu-id="ddd15-199">If needed, [Step 5](identity-password-reset.md#identity-sso) can help you with this option.</span></span>

<a name="crit-identity-custom-sign-in"></a>
## <a name="optional-the-office-365-sign-in-screen-is-personalized-for-your-organization"></a><span data-ttu-id="ddd15-200">Facoltativo: la schermata di accesso a Office 365 è personalizzata per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="ddd15-200">Optional: The Office 365 sign-in screen is personalized for your organization</span></span>

<span data-ttu-id="ddd15-201">È stata utilizzata la procedura descritta in [Aggiungere il marchio dell'azienda alla pagina di accesso e alle pagine del riquadro di accesso](http://aka.ms/aadpaddbranding) per aggiungere le informazioni personalizzate distintive dell'azienda nella pagina di accesso di Office 365.</span><span class="sxs-lookup"><span data-stu-id="ddd15-201">You have used [Add company branding to your sign-in and Access Panel pages](http://aka.ms/aadpaddbranding) to add your organization’s branding to the Office 365 sign-in page.</span></span>

<span data-ttu-id="ddd15-202">Se si ignora questa opzione, gli utenti visualizzeranno una schermata generica di accesso a Office 365 e non avranno la certezza di effettuare l'accesso al sito dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ddd15-202">If you skip this option, your users will see a generic Office 365 sign-in screen and might not be confident that they’re signing into your organization’s site.</span></span>

<span data-ttu-id="ddd15-203">Se necessario, il [Passaggio 5](identity-password-reset.md#identity-custom-sign-in) può aiutare con questa opzione.</span><span class="sxs-lookup"><span data-stu-id="ddd15-203">If needed, [Step 5](identity-password-reset.md#identity-custom-sign-in) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="ddd15-204">Come eseguire il test</span><span class="sxs-lookup"><span data-stu-id="ddd15-204">How to test</span></span>

<span data-ttu-id="ddd15-p108">Accedere al portale di Office 365 con il nome dell'account utente e l'autenticazione a più fattori. Dovrebbero essere visualizzati gli elementi di personalizzazione nella pagina di accesso.</span><span class="sxs-lookup"><span data-stu-id="ddd15-p108">Sign in to the Office 365 portal with your user account name and multi-factor authentication. You should see your custom branding elements on the sign-in page.</span></span>

<a name="crit-identity-self-service-groups"></a>
## <a name="optional-self-service-group-management-is-enabled-for-specific-azure-ad-security-and-office-365-groups"></a><span data-ttu-id="ddd15-207">Facoltativo: la gestione dei gruppi in modalità self-service è abilitata per specifici gruppi di sicurezza di Azure AD e Office 365</span><span class="sxs-lookup"><span data-stu-id="ddd15-207">Optional: Self-service group management is enabled for specific Azure AD security and Office 365 groups</span></span>

<span data-ttu-id="ddd15-208">È stato stabilito quali gruppi soddisfano i requisiti per la gestione in modalità self-service, i relativi proprietari sono stati istruiti sulle responsabilità e sul flusso di lavoro della gestione dei gruppi ed [è stata configurata la gestione in modalità self-service in Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management) per tali gruppi.</span><span class="sxs-lookup"><span data-stu-id="ddd15-208">You've determined which groups are appropriate for self-service management, instructed their owners on group management workflow and responsibilities, and [set up self-service management in Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management) for those groups.</span></span>

<span data-ttu-id="ddd15-209">Se si ignora questa opzione, tutte le attività di gestione dei gruppi di Azure AD, dovranno essere eseguite dagli amministratori IT.</span><span class="sxs-lookup"><span data-stu-id="ddd15-209">If you skip this option, all Azure AD group management tasks must be done by IT administrators.</span></span>

<span data-ttu-id="ddd15-210">Se necessario, il [Passaggio 6](identity-self-service-group-management.md#identity-self-service-groups) può aiutare con questa opzione.</span><span class="sxs-lookup"><span data-stu-id="ddd15-210">If needed, [Step 6](identity-self-service-group-management.md#identity-self-service-groups) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="ddd15-211">Come eseguire il test</span><span class="sxs-lookup"><span data-stu-id="ddd15-211">How to test</span></span>
1.  <span data-ttu-id="ddd15-212">Creare un account utente di test in Azure AD con il portale di Azure.</span><span class="sxs-lookup"><span data-stu-id="ddd15-212">Create a test user account in Azure AD with the Azure portal.</span></span>
2.  <span data-ttu-id="ddd15-213">Accedere con l'account utente di test e creare un gruppo di sicurezza di test di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="ddd15-213">Sign-in as with the test user account and create a test Azure AD security group.</span></span>
3.  <span data-ttu-id="ddd15-214">Disconnettersi ed effettuare di nuovo l'accesso con l'account amministratore IT.</span><span class="sxs-lookup"><span data-stu-id="ddd15-214">Sign out and then sign-in with your IT administrator account.</span></span>
4.  <span data-ttu-id="ddd15-215">Configurare il gruppo di sicurezza di test per la gestione in modalità self-service dell'account utente di test.</span><span class="sxs-lookup"><span data-stu-id="ddd15-215">Configure the test security group for self-service management for the test user account.</span></span>
5.  <span data-ttu-id="ddd15-216">Disconnettersi ed effettuare di nuovo l'accesso con l'account utente di test.</span><span class="sxs-lookup"><span data-stu-id="ddd15-216">Sign out and then sign-in with your test user account.</span></span>
6.  <span data-ttu-id="ddd15-217">Utilizzare il portale di Azure per aggiungere membri al gruppo di sicurezza di test.</span><span class="sxs-lookup"><span data-stu-id="ddd15-217">Use the Azure portal to add members to the test security group.</span></span>
7.  <span data-ttu-id="ddd15-218">Eliminare il gruppo di sicurezza di test e l'account utente di test.</span><span class="sxs-lookup"><span data-stu-id="ddd15-218">Delete the test security group and the test user account.</span></span>

<a name="crit-identity-dyn-groups"></a>
## <a name="optional-dynamic-group-membership-settings-automatically-add-user-accounts-to-groups-based-on-user-account-attributes"></a><span data-ttu-id="ddd15-219">Facoltativo: le impostazioni di appartenenza a gruppi dinamici aggiungono automaticamente gli account utente ai gruppi in base agli attributi degli account utente</span><span class="sxs-lookup"><span data-stu-id="ddd15-219">Optional: Dynamic group membership settings automatically add user accounts to groups based on user account attributes</span></span>

<span data-ttu-id="ddd15-220">È stato configurato il set di gruppi dinamici di Azure AD e sono state utilizzate le istruzioni presenti in [Creare regole basate su attributi per l'appartenenza dinamica ai gruppi in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal) per creare i gruppi e le regole che determinano il set di attributi dell'account utente e i valori di appartenenza ai gruppi.</span><span class="sxs-lookup"><span data-stu-id="ddd15-220">You've determined the set of Azure AD dynamic groups and used the instructions in [Attribute-based dynamic group membership in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal) to create the groups and the rules that determine the set of user account attributes and values for group membership.</span></span>

<span data-ttu-id="ddd15-p109">Se si ignora questa opzione, l'appartenenza ai gruppi deve essere eseguita manualmente quando vengono aggiunti nuovi account o se gli attributi degli account utente cambiano con il tempo. Ad esempio, se un utente passa dal Reparto vendite al Reparto contabilità, è necessario:</span><span class="sxs-lookup"><span data-stu-id="ddd15-p109">If you skip this option, group membership must be done manually as new accounts are added or as user account attributes change over time. For example, if someone moves from the Sales department to the Accounting department, you must:</span></span>

- <span data-ttu-id="ddd15-223">Aggiornare il valore dell'attributo del reparto per quell'account utente.</span><span class="sxs-lookup"><span data-stu-id="ddd15-223">Update the value of the Department attribute for that user account.</span></span>
- <span data-ttu-id="ddd15-224">Rimuovere manualmente l'account dal gruppo delle vendite.</span><span class="sxs-lookup"><span data-stu-id="ddd15-224">Manually remove them from the Sales group.</span></span>
- <span data-ttu-id="ddd15-225">Aggiungere manualmente l'account al gruppo della contabilità.</span><span class="sxs-lookup"><span data-stu-id="ddd15-225">Manually add them to the Accounting group.</span></span>

<span data-ttu-id="ddd15-226">Se il gruppo delle vendite e il gruppo della contabilità erano gruppi dinamici, sarà necessario solo cambiare il valore del reparto dell'account utente.</span><span class="sxs-lookup"><span data-stu-id="ddd15-226">If the Sales and Accounting groups were dynamic, you would only have to change the user account’s Department value.</span></span>

<span data-ttu-id="ddd15-227">Se necessario, il [Passaggio 6](identity-self-service-group-management.md#identity-dyn-groups) può aiutare con questa opzione.</span><span class="sxs-lookup"><span data-stu-id="ddd15-227">If needed, [Step 6](identity-self-service-group-management.md#identity-dyn-groups) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="ddd15-228">Come eseguire il test</span><span class="sxs-lookup"><span data-stu-id="ddd15-228">How to test</span></span>

1. <span data-ttu-id="ddd15-229">Creare un gruppo di test dinamico in Azure AD con il portale di Azure e configurare una regola il reparto uguale a "test1".</span><span class="sxs-lookup"><span data-stu-id="ddd15-229">Create a test dynamic group in Azure AD with the Azure portal and configure a rule for the Department equals “test1”.</span></span>
2. <span data-ttu-id="ddd15-230">Creare un account utente di test in Azure AD e impostare la proprietà del reparto su "test1".</span><span class="sxs-lookup"><span data-stu-id="ddd15-230">Create a test user account in Azure AD and set the Department property to “test1”.</span></span>
3. <span data-ttu-id="ddd15-231">Esaminare le proprietà dell'account utente per verificare che sia un membro del gruppo dinamico di test.</span><span class="sxs-lookup"><span data-stu-id="ddd15-231">Examine the properties of the user account to ensure that it was made a member of the test dynamic group.</span></span>
4. <span data-ttu-id="ddd15-232">Cambiare il valore della proprietà del reparto per l'account utente di test impostandolo su "test2".</span><span class="sxs-lookup"><span data-stu-id="ddd15-232">Change the value of the Department property for the test user account to “test2”.</span></span>
5. <span data-ttu-id="ddd15-233">Esaminare le proprietà dell'account utente per verificare che non sia più membro del gruppo dinamico di test.</span><span class="sxs-lookup"><span data-stu-id="ddd15-233">Examine the properties of the user account to ensure that it is no longer a member of the test dynamic group.</span></span>
6. <span data-ttu-id="ddd15-234">Eliminare il gruppo dinamico di test e l'account utente di test.</span><span class="sxs-lookup"><span data-stu-id="ddd15-234">Delete the test dynamic group and the test user account.</span></span>

<a name="crit-identity-group-license"></a>
## <a name="optional-group-based-licensing-to-automatically-assign-and-remove-licenses-to-user-accounts-based-on-group-membership"></a><span data-ttu-id="ddd15-235">Facoltativo: gestione delle licenze basate su gruppo per assegnare e rimuovere automaticamente le licenze degli account utente in base all'appartenenza ai gruppi</span><span class="sxs-lookup"><span data-stu-id="ddd15-235">Optional: Group-based licensing to automatically assign and remove licenses to user accounts based on group membership</span></span>

<span data-ttu-id="ddd15-236">È stata [abilitata la gestione delle licenze basate su gruppo](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal) per i gruppi di sicurezza di Azure AD appropriati, in modo che le licenze di Microsoft 365 Enterprise vengano assegnate o rimosse automaticamente.</span><span class="sxs-lookup"><span data-stu-id="ddd15-236">You [enabled group-based licensing](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal) for the appropriate Azure AD security groups so that licenses for both Office 365 and EMS are automatically assigned or removed.</span></span>

<span data-ttu-id="ddd15-237">Se si ignora questa opzione, sarà necessario eseguire manualmente i seguenti passaggi:</span><span class="sxs-lookup"><span data-stu-id="ddd15-237">If you skip this option, you must manually:</span></span>

- <span data-ttu-id="ddd15-238">Assegnare le licenze ai nuovi utenti che dovranno avere accesso.</span><span class="sxs-lookup"><span data-stu-id="ddd15-238">Assign licenses to new users whom you intend to have access to Office 365 and EMS.</span></span>
- <span data-ttu-id="ddd15-239">Rimuovere le licenze dagli utenti che non fanno più parte dell'organizzazione o non hanno accesso.</span><span class="sxs-lookup"><span data-stu-id="ddd15-239">Remove licenses from users who are no longer with your organization or do not have access to Office 365 and EMS.</span></span>

<span data-ttu-id="ddd15-240">Se necessario, il [Passaggio 6](identity-self-service-group-management.md#identity-group-license) può aiutare con questa opzione.</span><span class="sxs-lookup"><span data-stu-id="ddd15-240">If needed, [Step 6](identity-self-service-group-management.md#identity-group-license) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="ddd15-241">Come eseguire il test</span><span class="sxs-lookup"><span data-stu-id="ddd15-241">How to test</span></span>

1. <span data-ttu-id="ddd15-242">Creare un gruppo di sicurezza di test in Azure AD con il portale di Azure e configurare la gestione delle licenze basate su gruppo per assegnare la licenza di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="ddd15-242">Create a test security group in Azure AD with the Azure portal and configure group-based licensing to assign Office 365 and EMS licenses.</span></span>
2. <span data-ttu-id="ddd15-243">Creare un account utente di test in Azure AD e aggiungerlo al gruppo di sicurezza di test.</span><span class="sxs-lookup"><span data-stu-id="ddd15-243">Create a test user account in Azure AD and add it to the test security group.</span></span>
3. <span data-ttu-id="ddd15-244">Esaminare le proprietà dell'account utente nell'interfaccia di amministrazione di Microsoft 365 per verificare che la licenza di Microsoft 365 Enterprise sia stata assegnata.</span><span class="sxs-lookup"><span data-stu-id="ddd15-244">Examine the properties of the user account in the Microsoft 365 admin center to ensure that it was assigned the Office 365 and EMS licenses.</span></span>
4. <span data-ttu-id="ddd15-245">Rimuovere l'account utente di test dal gruppo di sicurezza di test.</span><span class="sxs-lookup"><span data-stu-id="ddd15-245">Remove the test user account from the test security group.</span></span>
5. <span data-ttu-id="ddd15-246">Esaminare le proprietà dell'account utente per verificare che non disponga più della licenza di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="ddd15-246">Examine the properties of the user account to ensure that it no longer has the Office 365 and EMS licenses assigned.</span></span>
6. <span data-ttu-id="ddd15-247">Eliminare il gruppo di sicurezza di test e l'account utente di test.</span><span class="sxs-lookup"><span data-stu-id="ddd15-247">Delete the test security group and the test user account.</span></span>

<a name="crit-identity-access-reviews"></a>
## <a name="optional-access-reviews-configured-and-being-used-to-monitor-access"></a><span data-ttu-id="ddd15-248">Facoltativo: verifiche di accesso configurate e usate per monitorare l'accesso</span><span class="sxs-lookup"><span data-stu-id="ddd15-248">Optional: Access reviews configured and being used to monitor access</span></span>

<span data-ttu-id="ddd15-249">Sono stati usati questi articoli per configurare tipi diversi di verifiche di accesso per il monitoraggio dell'appartenenza a gruppi, dell'accesso alle applicazioni aziendali e delle assegnazioni di ruolo:</span><span class="sxs-lookup"><span data-stu-id="ddd15-249">You have used these articles to configure different types of access reviews to monitor group memberships, access to enterprise applications, and role assignments:</span></span>

- [<span data-ttu-id="ddd15-250">Gruppi e app</span><span class="sxs-lookup"><span data-stu-id="ddd15-250">Groups and apps</span></span>](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [<span data-ttu-id="ddd15-251">Ruoli di Azure AD</span><span class="sxs-lookup"><span data-stu-id="ddd15-251">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [<span data-ttu-id="ddd15-252">Ruoli delle risorse di Azure</span><span class="sxs-lookup"><span data-stu-id="ddd15-252">Azure resource roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

<span data-ttu-id="ddd15-253">Se necessario, il [Passaggio 7](identity-governance.md#identity-access-reviews) può aiutare con questa opzione.</span><span class="sxs-lookup"><span data-stu-id="ddd15-253">If needed, [Step 5](identity-governance.md#identity-access-reviews) can help you with this option.</span></span>

## <a name="results-and-next-steps"></a><span data-ttu-id="ddd15-254">Risultati e passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="ddd15-254">Results and next steps</span></span>

<span data-ttu-id="ddd15-255">L'infrastruttura di gestione delle identità nel cloud Microsoft 365 usa l'autenticazione avanzata, account amministratore protetti e funzionalità semplificate di accesso e gestione utenti.</span><span class="sxs-lookup"><span data-stu-id="ddd15-255">Your identity infrastructure in the Microsoft 365 cloud uses strong authentication, protected administrator accounts, and simplified user access and management.</span></span>

|||
|:-------|:-----|
|![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)| <span data-ttu-id="ddd15-256">Se si stanno seguendo le fasi per la distribuzione end-to-end di Microsoft 365 Enterprise, la fase successiva è [Windows 10 Enterprise](windows10-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="ddd15-256">If you're following the phases for the end-to-end deployment of Microsoft 365 Enterprise, your next phase is [Windows 10 Enterprise](windows10-infrastructure.md).</span></span> |

