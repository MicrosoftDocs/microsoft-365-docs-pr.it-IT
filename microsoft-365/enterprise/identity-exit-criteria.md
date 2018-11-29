---
title: "Fase 2: criteri uscita dell'infrastruttura di rete"
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Verificare che la configurazione soddisfi i criteri di Microsoft 365 Enterprise per l'infrastruttura e i servizi basati sull'identità.
ms.openlocfilehash: 49ba7801b740b2a1cfd77955517646ee80174712
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868883"
---
# <a name="phase-2-identity-infrastructure-exit-criteria"></a><span data-ttu-id="b90d9-103">Fase 2: criteri uscita dell'infrastruttura di rete</span><span class="sxs-lookup"><span data-stu-id="b90d9-103">Phase 2: Identity infrastructure exit criteria</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="b90d9-p101">Prima di passare alla Fase 3, assicurarsi che l'infrastruttura di gestione delle identità soddisfi queste condizioni. Vedere anche [Prerequisiti](https://docs.microsoft.com/microsoft-365-enterprise/identity-access-policies#prerequisites) per ulteriori elementi consigliati sull'infrastruttura di gestione delle identità.</span><span class="sxs-lookup"><span data-stu-id="b90d9-p101">Before you move on to Phase 3, make sure that your identity infrastructure meets these conditions. Also see [Prerequisites](https://docs.microsoft.com/microsoft-365-enterprise/identity-access-policies#prerequisites) for additional recommendations on identity infrastructure.</span></span>

<a name="crit-identity-user-groups"></a>
## <a name="required-all-users-groups-and-group-memberships-have-been-created"></a><span data-ttu-id="b90d9-106">Obbligatorio: sono stati creati tutti gli utenti, i gruppi e l'appartenenza ai gruppi</span><span class="sxs-lookup"><span data-stu-id="b90d9-106">Required: All users, groups, and group memberships have been created</span></span>

<span data-ttu-id="b90d9-107">Gli account e i gruppi utente sono stati creati in modo che:</span><span class="sxs-lookup"><span data-stu-id="b90d9-107">You've created user accounts and groups so that:</span></span>

- <span data-ttu-id="b90d9-108">I dipendenti dell'organizzazione e i fornitori, i terzisti e i partner della stessa abbiano un account utente corrispondente in Azure Active Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="b90d9-108">Employees in your organization and the vendors, contractors, and partners that work for or with your organization have a corresponding user account in Azure Active Directory (AD).</span></span>
- <span data-ttu-id="b90d9-109">I gruppi di Azure AD e i relativi membri contengano account utente e altri gruppi per scopi diversi, come il provisioning delle impostazioni di sicurezza per i servizi cloud Microsoft, la gestione delle licenze automatica e altri utilizzi.</span><span class="sxs-lookup"><span data-stu-id="b90d9-109">Azure AD groups and their members contain user accounts and other groups for various purposes, such as the provisioning of security settings for Microsoft cloud services, automatic licensing, and other uses.</span></span>

<span data-ttu-id="b90d9-110">Se necessario, il [Passaggio 1](identity-plan-users-groups.md) può aiutare a soddisfare questo requisito.</span><span class="sxs-lookup"><span data-stu-id="b90d9-110">If needed, [Step 1](identity-plan-users-groups.md) can help you meet this requirement.</span></span>

<a name="crit-identity-sync"></a>
## <a name="required-users-and-groups-are-synchronized-with-azure-ad"></a><span data-ttu-id="b90d9-111">Obbligatorio: gli utenti e i gruppi sono sincronizzati con Azure AD</span><span class="sxs-lookup"><span data-stu-id="b90d9-111">Required: Users and groups are synchronized with Azure AD</span></span>

<span data-ttu-id="b90d9-112">Se si dispone di un provider di identità locale esistente, come Windows Server Active Directory (AD), è stato utilizzato Azure AD Connect per sincronizzare i gruppi e gli account utente dal provider di identità locale al tenant di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="b90d9-112">If you have an existing on-premises identity provider, such as Windows Server Active Directory (AD), you have used Azure AD Connect to synchronize user accounts and groups from your on-premises identity provider to your Azure AD tenant.</span></span>

<span data-ttu-id="b90d9-113">Grazie alla sincronizzazione della directory, gli utenti possono accedere a Office 365 e agli altri servizi cloud Microsoft utilizzando le stesse credenziali che usano per l'accesso ai loro computer e alle risorse locali.</span><span class="sxs-lookup"><span data-stu-id="b90d9-113">With directory synchronization, your users can sign in to Office 365 and other Microsoft cloud services using the same credentials that they use to sign in to their computers and access on-premises resources.</span></span>

<span data-ttu-id="b90d9-114">Se necessario, il [Passaggio 7](identity-azure-ad-connect.md) può aiutare a soddisfare questo requisito.</span><span class="sxs-lookup"><span data-stu-id="b90d9-114">If needed, [Step 7](identity-azure-ad-connect.md) can help you meet this requirement.</span></span>

<span data-ttu-id="b90d9-115">Se si ignora questo requisito, saranno disponibili due set di account utente e gruppi:</span><span class="sxs-lookup"><span data-stu-id="b90d9-115">If you skip this requirement, you’ll have two sets of user accounts and groups:</span></span>

- <span data-ttu-id="b90d9-116">Gli account utente e i gruppi esistenti nel provider di identità locale</span><span class="sxs-lookup"><span data-stu-id="b90d9-116">User accounts and groups that exist in your on-premises identity provider</span></span>
- <span data-ttu-id="b90d9-117">Gli account utente e i gruppi esistenti nel tenant di Azure AD</span><span class="sxs-lookup"><span data-stu-id="b90d9-117">User accounts and groups that exist in your Azure AD tenant</span></span>

<span data-ttu-id="b90d9-p102">In questo stato, i due set di account e gruppi utente dovranno essere gestiti manualmente sia dagli utenti che dagli amministratori IT. Questo comporterà inevitabilmente la mancata sincronizzazione di account, password e gruppi.</span><span class="sxs-lookup"><span data-stu-id="b90d9-p102">In this state, the two sets of user accounts and groups must be manually maintained by both IT administrators and users. This will inevitably lead to unsynchronized accounts, their passwords, and groups.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="b90d9-120">Come eseguire il test</span><span class="sxs-lookup"><span data-stu-id="b90d9-120">How to test</span></span>
<span data-ttu-id="b90d9-121">Per verificare il corretto funzionamento dell'autenticazione con le credenziali locali, accedere al portale di Office 365 con le credenziali locali.</span><span class="sxs-lookup"><span data-stu-id="b90d9-121">To verify that authentication with on-premises credentials works correctly, sign in to the Office 365 portal with your on-premises credentials.</span></span>

<span data-ttu-id="b90d9-122">Per verificare il corretto funzionamento della sincronizzazione della directory, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b90d9-122">To verify that directory synchronization is working correctly, do the following:</span></span>

1.  <span data-ttu-id="b90d9-123">Creare un nuovo gruppo di test in Windows Server AD.</span><span class="sxs-lookup"><span data-stu-id="b90d9-123">Create a new test group in Windows Server AD.</span></span>
2.  <span data-ttu-id="b90d9-124">Attendere la sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="b90d9-124">Wait for the synchronization time.</span></span>
3.  <span data-ttu-id="b90d9-125">Controllare il tenant di Azure AD per verificare che venga visualizzato il nome del nuovo gruppo di test.</span><span class="sxs-lookup"><span data-stu-id="b90d9-125">Check your Azure AD tenant to verify that the new test group name appears.</span></span>

<a name="crit-identity-global-admin"></a>
## <a name="required-your-global-administrator-accounts-are-protected"></a><span data-ttu-id="b90d9-126">Obbligatorio: gli account di amministratore globale sono protetti</span><span class="sxs-lookup"><span data-stu-id="b90d9-126">Required: Your global administrator accounts are protected</span></span> 

<span data-ttu-id="b90d9-127">Gli [account di amministratore globale di Office 365 sono stati protetti](https://support.office.com/article/Protect-your-Office-365-global-administrator-accounts-6b4ded77-ac8d-42ed-8606-c014fd947560) per evitare che vengano compromesse le credenziali e che quindi possa esserci la violazione di una sottoscrizione a Office 365.</span><span class="sxs-lookup"><span data-stu-id="b90d9-127">You've [protected your Office 365 global administrator accounts](https://support.office.com/article/Protect-your-Office-365-global-administrator-accounts-6b4ded77-ac8d-42ed-8606-c014fd947560) to avoid compromising credentials that can lead to breaches of an Office 365 subscription.</span></span>

<span data-ttu-id="b90d9-128">Se si ignora questo requisito, gli account di amministratore globale potrebbero essere soggetti ad attacchi e violazioni, consentendo a terzi l'acquisizione di dati e l'utilizzo di tali informazioni per scopi di raccolta, distruzione o ricatto.</span><span class="sxs-lookup"><span data-stu-id="b90d9-128">If you skip this requirement, your global administrator accounts can be susceptible to attack and compromise, allowing an attacker to gain system-wide access to your data for harvesting, destruction, or ransom.</span></span>

<span data-ttu-id="b90d9-129">Se necessario, il [Passaggio 2](identity-designate-protect-admin-accounts.md) può aiutare a soddisfare questo requisito.</span><span class="sxs-lookup"><span data-stu-id="b90d9-129">If needed, [Step 2](identity-designate-protect-admin-accounts.md) can help you meet this requirement.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="b90d9-130">Come eseguire il test</span><span class="sxs-lookup"><span data-stu-id="b90d9-130">How to test</span></span>

<span data-ttu-id="b90d9-131">Utilizzare questa procedura per verificare che gli account di amministratore globale siano protetti:</span><span class="sxs-lookup"><span data-stu-id="b90d9-131">Use these steps to verify that you've protected your global administrator accounts:</span></span>

1. <span data-ttu-id="b90d9-p103">Eseguire il seguente comando di Azure AD v2 dal prompt dei comandi di PowerShell. Dovrebbe essere visualizzato solo l'elenco degli account di amministratore globale dedicati.</span><span class="sxs-lookup"><span data-stu-id="b90d9-p103">Run the following Azure AD V2 command at the PowerShell command prompt. You should see only the list of dedicated global administrator accounts.</span></span>
   ```
   Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
   ```
2. <span data-ttu-id="b90d9-p104">Accedere a Office 365 utilizzando ognuno degli account del Passaggio 1. Ogni accesso dovrà richiedere l'autenticazione a più fattori e la forma più avanzata di autenticazione secondaria disponibile nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b90d9-p104">Sign in to Office 365 using each of the accounts from step 1. Each sign in must require multi-factor authentication and the strongest form of secondary authentication available in your organization.</span></span>

> [!Note]
> <span data-ttu-id="b90d9-136">Vedere [Connettersi a PowerShell di Office 365](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) per le istruzioni sull'istallazione del modulo Azure AD PowerShell v2 e sull'accesso a Office 365.</span><span class="sxs-lookup"><span data-stu-id="b90d9-136">See [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) for instructions on installing the Azure AD V2 PowerShell module and signing in to Office 365.</span></span>

<a name="crit-identity-custom-sign-in"></a>
## <a name="optional-the-office-365-sign-in-screen-is-personalized-for-your-organization"></a><span data-ttu-id="b90d9-137">Facoltativo: la schermata di accesso a Office 365 è personalizzata per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="b90d9-137">Optional: The Office 365 sign-in screen is personalized for your organization</span></span>

<span data-ttu-id="b90d9-138">È stata utilizzata la procedura descritta in [Aggiungere il marchio dell'azienda alla pagina di accesso e alle pagine del riquadro di accesso](http://aka.ms/aadpaddbranding) per aggiungere le informazioni personalizzate distintive dell'azienda nella pagina di accesso di Office 365.</span><span class="sxs-lookup"><span data-stu-id="b90d9-138">You have used [Add company branding to your sign-in and Access Panel pages](http://aka.ms/aadpaddbranding) to add your organization’s branding to the Office 365 sign-in page.</span></span>

<span data-ttu-id="b90d9-139">Se si ignora questa opzione, gli utenti visualizzeranno una schermata generica di accesso a Office 365 e non avranno la certezza di effettuare l'accesso al sito dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b90d9-139">If you skip this option, your users will see a generic Office 365 sign-in screen and might not be confident that they’re signing into your organization’s site.</span></span>

<span data-ttu-id="b90d9-140">Se necessario, il [Passaggio 11](identity-customize-office-365-sign-in.md) può aiutare con questa opzione.</span><span class="sxs-lookup"><span data-stu-id="b90d9-140">If needed, [Step 11](identity-customize-office-365-sign-in.md) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="b90d9-141">Come eseguire il test</span><span class="sxs-lookup"><span data-stu-id="b90d9-141">How to test</span></span>

<span data-ttu-id="b90d9-p105">Accedere al portale di Office 365 con il nome dell'account utente e l'autenticazione a più fattori. Dovrebbero essere visualizzati gli elementi di personalizzazione nella pagina di accesso.</span><span class="sxs-lookup"><span data-stu-id="b90d9-p105">Sign in to the Office 365 portal with your user account name and multi-factor authentication. You should see your custom branding elements on the sign-in page.</span></span>

<a name="crit-identity-mfa"></a>
## <a name="optional-multi-factor-authentication-is-enabled-for-your-users"></a><span data-ttu-id="b90d9-144">Facoltativo: l'autenticazione a più fattori è abilitata per gli utenti</span><span class="sxs-lookup"><span data-stu-id="b90d9-144">Optional: Multi-factor authentication is enabled for your users</span></span>

<span data-ttu-id="b90d9-145">È stata utilizzata la procedura descritta in [Pianificare l'autenticazione a più fattori per le distribuzioni di Office 365](https://support.office.com/article/Plan-for-multifactor-authentication-for-Office-365-Deployments-043807b2-21db-4d5c-b430-c8a6dee0e6ba) e [Configurare l'autenticazione a più fattori per gli utenti di Office 365](https://support.office.com/article/Set-up-multi-factor-authentication-for-Office-365-users-8f0454b2-f51a-4d9c-bcde-2c48e41621c6) per abilitare l'autenticazione a più fattori (MFA) per gli account utente.</span><span class="sxs-lookup"><span data-stu-id="b90d9-145">You used [Plan for multi-factor authentication for Office 365 Deployments](https://support.office.com/article/Plan-for-multifactor-authentication-for-Office-365-Deployments-043807b2-21db-4d5c-b430-c8a6dee0e6ba) and [Set up multi-factor authentication for Office 365 users](https://support.office.com/article/Set-up-multi-factor-authentication-for-Office-365-users-8f0454b2-f51a-4d9c-bcde-2c48e41621c6) to enable multifactor authentication (MFA) for your user accounts.</span></span>

<span data-ttu-id="b90d9-p106">Se si ignora questa opzione, gli account utente saranno vulnerabili alla violazione delle credenziali ad opera di possibili attacchi informatici. In caso di violazione della password di un account utente, tutte le risorse e le funzionalità dell'account (come i ruoli di amministratore) saranno a disposizione dell'utente malintenzionato, che potrà copiare, distruggere o conservare a scopo di ricatto documenti interni o altri dati.</span><span class="sxs-lookup"><span data-stu-id="b90d9-p106">If you skip this option, your user accounts are vulnerable to credential compromise by cyber attackers. If a user account’s password is compromised, all the resources and capabilities of the account, such as administrator roles, are available to the attacker. This allows the attacker to copy, destroy, or hold for ransom internal documents and other data.</span></span>

<span data-ttu-id="b90d9-149">Se necessario, il [Passaggio 5](identity-multi-factor-authentication.md) può aiutare con questa opzione.</span><span class="sxs-lookup"><span data-stu-id="b90d9-149">If needed, [Step 5](identity-multi-factor-authentication.md) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="b90d9-150">Come eseguire il test</span><span class="sxs-lookup"><span data-stu-id="b90d9-150">How to test</span></span>

1.  <span data-ttu-id="b90d9-151">Creare un account utente di test nel portale di amministrazione di Office 365 e assegnargli una licenza.</span><span class="sxs-lookup"><span data-stu-id="b90d9-151">Create a test user account in the Office 365 Admin portal and assign them a license.</span></span> 
2.  <span data-ttu-id="b90d9-152">Configurare l'autenticazione a più fattori per l'account utente di test con il metodo di verifica aggiuntivo in uso per gli account utente effettivi, come per esempio l'invio di un messaggio al telefono.</span><span class="sxs-lookup"><span data-stu-id="b90d9-152">Configure multi-factor authentication for the test user account with the additional verification method that you are using for actual user accounts, such as sending a message to your phone.</span></span> 
3.  <span data-ttu-id="b90d9-153">Accedere al portale di Office 365 o di Azure con l'account utente di test.</span><span class="sxs-lookup"><span data-stu-id="b90d9-153">Sign in to the Office 365 or Azure portal with the test user account.</span></span>
4.  <span data-ttu-id="b90d9-154">Verificare che l'autenticazione a più fattori richieda all'utente ulteriori informazioni di verifica e abbia esito positivo.</span><span class="sxs-lookup"><span data-stu-id="b90d9-154">Verify that MFA prompts you for the additional verification information and results in a successful authentication.</span></span> 
5.  <span data-ttu-id="b90d9-155">Eliminare l'account utente di test.</span><span class="sxs-lookup"><span data-stu-id="b90d9-155">Delete the test user account.</span></span>

<a name="crit-identity-sync-health"></a>
## <a name="optional-directory-synchronization-is-monitored"></a><span data-ttu-id="b90d9-156">Facoltativo: la sincronizzazione delle directory viene monitorata</span><span class="sxs-lookup"><span data-stu-id="b90d9-156">Optional: Directory synchronization is monitored</span></span>

<span data-ttu-id="b90d9-157">È stata consultata la documentazione disponibile in [Uso di Azure AD Connect Health per la sincronizzazione](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) (per la sincronizzazione delle password) o in [Uso di Azure AD Connect Health con AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) (per l'autenticazione federata) ed è stato implementato Azure AD Connect Health, che implica quanto segue:</span><span class="sxs-lookup"><span data-stu-id="b90d9-157">You've used [Azure AD Connect Health with sync](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) (for password synchronization) or [Using Azure AD Connect Health with AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) (for federated authentication) and have deployed Azure AD Connect Health, which involves:</span></span>

- <span data-ttu-id="b90d9-158">L'installazione dell'agente di Azure AD Connect Health su ciascuno dei server di identità locale.</span><span class="sxs-lookup"><span data-stu-id="b90d9-158">Installing the Azure AD Connect Health agent on each of your on-premises identity servers.</span></span>
- <span data-ttu-id="b90d9-159">L'utilizzo del portale di Azure AD Connect Health per monitorare lo stato della sincronizzazione in corso.</span><span class="sxs-lookup"><span data-stu-id="b90d9-159">Using the Azure AD Connect Health portal to monitor the state of the ongoing synchronization.</span></span>

<span data-ttu-id="b90d9-160">Se si ignora questa opzione, è possibile valutare in maniera più precisa lo stato dell'infrastruttura di gestione delle identità basata sul cloud.</span><span class="sxs-lookup"><span data-stu-id="b90d9-160">If you skip this option, you can more accurately assess the state of your cloud-based identity infrastructure.</span></span>

<span data-ttu-id="b90d9-161">Se necessario, il [Passaggio 8](identity-azure-ad-connect-health.md) può aiutare con questa opzione.</span><span class="sxs-lookup"><span data-stu-id="b90d9-161">If needed, [Step 8](identity-azure-ad-connect-health.md) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="b90d9-162">Come eseguire il test</span><span class="sxs-lookup"><span data-stu-id="b90d9-162">How to test</span></span>
<span data-ttu-id="b90d9-163">Il portale di Azure AD Connect Health mostra lo stato attuale e corretto dei server di identità locale e la sincronizzazione in corso.</span><span class="sxs-lookup"><span data-stu-id="b90d9-163">The Azure AD Connect Health portal shows the current and correct state of your on-premises identity servers and the ongoing synchronization.</span></span>

<a name="crit-identity-pw-reset"></a>
## <a name="optional-users-can-reset-their-own-passwords"></a><span data-ttu-id="b90d9-164">Facoltativo: gli utenti possono reimpostare la propria password</span><span class="sxs-lookup"><span data-stu-id="b90d9-164">Optional: Users can reset their own passwords</span></span>

<span data-ttu-id="b90d9-165">È stata utilizzata la procedura descritta in [Distribuzione rapida della reimpostazione della password self-service di Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) per configurare la reimpostazione della password per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="b90d9-165">You've used [Azure AD self-service password reset rapid deployment](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) to configure password reset for your users.</span></span>

<span data-ttu-id="b90d9-166">Se non si soddisfa questa condizione, gli utenti dovranno dipendere dagli amministratori degli account utente per reimpostare le proprie password, con un sovraccarico sull'amministrazione IT.</span><span class="sxs-lookup"><span data-stu-id="b90d9-166">If you don’t meet this condition, users will be dependent on user account administrators to reset their passwords, resulting in additional IT administration overhead.</span></span>

<span data-ttu-id="b90d9-167">Se necessario, il [Passaggio 4](identity-password-reset.md) può aiutare con questa opzione.</span><span class="sxs-lookup"><span data-stu-id="b90d9-167">If needed, [Step 4](identity-password-reset.md) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="b90d9-168">Come eseguire il test</span><span class="sxs-lookup"><span data-stu-id="b90d9-168">How to test</span></span>

1. <span data-ttu-id="b90d9-169">Creare un account utente di test con una password iniziale.</span><span class="sxs-lookup"><span data-stu-id="b90d9-169">Create a test user account with an initial password.</span></span>
2. <span data-ttu-id="b90d9-170">Utilizzare i passaggi illustrati in [Consentire agli utenti di reimpostare le loro password in Office 365](https://support.office.com/article/Let-users-reset-their-own-passwords-in-Office-365-5bc3f460-13cc-48c0-abd6-b80bae72d04a) per reimpostare la password dell'account utente di test.</span><span class="sxs-lookup"><span data-stu-id="b90d9-170">Use the steps in [Let users reset their own passwords in Office 365](https://support.office.com/article/Let-users-reset-their-own-passwords-in-Office-365-5bc3f460-13cc-48c0-abd6-b80bae72d04a) to reset the password on the test user account.</span></span>
3. <span data-ttu-id="b90d9-171">Disconnettersi ed effettuare di nuovo l'accesso con l'account utente di test con la nuova password.</span><span class="sxs-lookup"><span data-stu-id="b90d9-171">Sign out and then sign in to the test user account using the reset password.</span></span>
4. <span data-ttu-id="b90d9-172">Eliminare l'account utente di test.</span><span class="sxs-lookup"><span data-stu-id="b90d9-172">Delete the test user account.</span></span>

<a name="crit-identity-pw-writeback"></a>
## <a name="optional-password-writeback-is-enabled-for-your-users"></a><span data-ttu-id="b90d9-173">Facoltativo: il writeback delle password è abilitato per gli utenti</span><span class="sxs-lookup"><span data-stu-id="b90d9-173">Optional: Password writeback is enabled for your users</span></span>

<span data-ttu-id="b90d9-174">Sono state utilizzate le istruzioni riportate in [Reimpostazione delle password in modalità self-service di Azure AD con writeback delle password](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) per abilitare il writeback delle password per il tenant di Azure AD per la sottoscrizione di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="b90d9-174">You've used the instructions in [Azure AD SSPR with password writeback](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) to enable password writeback for the Azure AD tenant of your Microsoft 365 Enterprise subscription.</span></span>

<span data-ttu-id="b90d9-175">Se si ignora questa opzione, gli utenti che non sono connessi con il server locale devono reimpostare o sbloccare le password di Windows Server AD tramite un amministratore IT.</span><span class="sxs-lookup"><span data-stu-id="b90d9-175">If you skip this option, users who aren’t connected to your on-premises network must reset or unlock their Windows Server AD passwords through an IT administrator.</span></span>

<span data-ttu-id="b90d9-176">Se necessario, il [Passaggio 9](identity-password-writeback.md) può aiutare con questa opzione.</span><span class="sxs-lookup"><span data-stu-id="b90d9-176">If needed, [Step 9](identity-password-writeback.md) can help you with this option.</span></span>

>[!Note]
><span data-ttu-id="b90d9-177">Il writeback delle password è necessario per utilizzare al meglio le funzioni di Azure AD Identity Protection, come la richiesta agli utenti di cambiare le password locali nel caso in cui Azure AD rilevi un alto rischio di violazione dell'account.</span><span class="sxs-lookup"><span data-stu-id="b90d9-177">Password writeback is required to fully utilize Azure AD Identity Protection features, such as requiring users to change their on-premises passwords when Azure AD has detected a high risk of account compromise.</span></span>
>

### <a name="how-to-test"></a><span data-ttu-id="b90d9-178">Come eseguire il test</span><span class="sxs-lookup"><span data-stu-id="b90d9-178">How to test</span></span>

<span data-ttu-id="b90d9-p107">Per testare il writeback delle password, è necessario cambiare la password in Office 365. Dovrebbe essere possibile usare l'account e la nuova password per accedere alle risorse di Windows Server AD locale.</span><span class="sxs-lookup"><span data-stu-id="b90d9-p107">You test password writeback by changing your password in Office 365. You should be able to use your account and new password to access on-premises Windows Server AD resources.</span></span>

1. <span data-ttu-id="b90d9-181">Creare un account utente di test per Windows Server AD locale, consentire la sincronizzazione della directory e concedere una licenza di Office 365 nel portale di amministrazione di Office 365.</span><span class="sxs-lookup"><span data-stu-id="b90d9-181">Create a test user account in your on-premises Windows Server AD, allow directory synchronization to occur, and then grant it an Office 365 license in the Office 365 admin portal.</span></span>
2. <span data-ttu-id="b90d9-182">Accedere al computer e al portale di Office 365 con le credenziali dell'account utente di test da un computer remoto nel dominio di Windows Server AD locale.</span><span class="sxs-lookup"><span data-stu-id="b90d9-182">From a remote computer that is joined to your on-premises Windows Server AD domain, sign in to the computer and the Office 365 portal using the credentials of the test user account.</span></span>
3. <span data-ttu-id="b90d9-183">Selezionare **Impostazioni > Impostazioni di Office 365 > Password > Cambia password**.</span><span class="sxs-lookup"><span data-stu-id="b90d9-183">Select **Settings > Office 365 settings > Password > Change password**.</span></span>
4. <span data-ttu-id="b90d9-184">Digitare la password corrente, inserirne una nuova e quindi confermarla.</span><span class="sxs-lookup"><span data-stu-id="b90d9-184">Type the current password, type a new password, and then confirm it.</span></span>
5. <span data-ttu-id="b90d9-p108">Disconnettersi dal portale di Office 365 e dal computer remoto e quindi accedere al computer utilizzando l'account utente di test e la relativa nuova password. Questo passaggio dimostra che è stato possibile cambiare la password di un account utente di Windows Server AD locale tramite il tenant di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="b90d9-p108">Sign out of the Office 365 portal and the remote computer and then sign in to the computer using the test user account and its new password. This proves that you were able to change the password of an on-premises Windows Server AD user account using the Azure AD tenant.</span></span>

<a name="crit-identity-sso"></a>
## <a name="optional-users-can-sign-in-using-single-sign-on"></a><span data-ttu-id="b90d9-187">Facoltativo: gli utenti possono accedere utilizzando Single Sign-On</span><span class="sxs-lookup"><span data-stu-id="b90d9-187">Optional: Users can sign in using single sign-on</span></span>

<span data-ttu-id="b90d9-188">È stato abilitato [Azure AD Connect: accesso Single Sign-On facile](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start) per l'organizzazione, con lo scopo di semplificare l'accesso degli utenti alle applicazioni basate sul cloud, come Office 365.</span><span class="sxs-lookup"><span data-stu-id="b90d9-188">You enabled [Azure AD Connect: Seamless Single Sign-On](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start) for your organization to simplify how users sign in to cloud-based applications, such as Office 365.</span></span>

<span data-ttu-id="b90d9-189">Se si ignora questa opzione, gli utenti potrebbero dover immettere le credenziali quando accedono alle applicazioni aggiuntive che utilizzano Azure AD.</span><span class="sxs-lookup"><span data-stu-id="b90d9-189">If you skip this option, your users might be prompted to provide credentials when they access additional applications that use Azure AD.</span></span>

<span data-ttu-id="b90d9-190">Se necessario, il [Passaggio 10](identity-single-sign-on.md) può aiutare con questa opzione.</span><span class="sxs-lookup"><span data-stu-id="b90d9-190">If needed, [Step 10](identity-single-sign-on.md) can help you with this option.</span></span>


<a name="crit-identity-group-license"></a>
## <a name="optional-group-based-licensing-to-automatically-assign-and-remove-licenses-to-user-accounts-based-on-group-membership"></a><span data-ttu-id="b90d9-191">Facoltativo: gestione delle licenze basate su gruppo per assegnare e rimuovere automaticamente le licenze degli account utente in base all'appartenenza ai gruppi</span><span class="sxs-lookup"><span data-stu-id="b90d9-191">Optional: Group-based licensing to automatically assign and remove licenses to user accounts based on group membership</span></span>

<span data-ttu-id="b90d9-192">È stata [abilitata la gestione delle licenze basate su gruppo](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal) per i gruppi di sicurezza di Azure AD appropriati in modo che le licenze di Office 365 ed EMS vengano assegnate o rimosse automaticamente.</span><span class="sxs-lookup"><span data-stu-id="b90d9-192">You [enabled group-based licensing](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal) for the appropriate Azure AD security groups so that licenses for both Office 365 and EMS are automatically assigned or removed.</span></span>

<span data-ttu-id="b90d9-193">Se si ignora questa opzione, sarà necessario eseguire manualmente i seguenti passaggi:</span><span class="sxs-lookup"><span data-stu-id="b90d9-193">If you skip this option, you must manually:</span></span>

- <span data-ttu-id="b90d9-194">Assegnare le licenze ai nuovi utenti che dovranno accedere a Office 365 ed EMS.</span><span class="sxs-lookup"><span data-stu-id="b90d9-194">Assign licenses to new users whom you intend to have access to Office 365 and EMS.</span></span>
- <span data-ttu-id="b90d9-195">Rimuovere le licenze dagli utenti che non fanno più parte dell'organizzazione o non hanno accesso a Office 365 ed EMS.</span><span class="sxs-lookup"><span data-stu-id="b90d9-195">Remove licenses from users who are no longer with your organization or do not have access to Office 365 and EMS.</span></span>

<span data-ttu-id="b90d9-196">Se necessario, il [Passaggio 12](identity-group-based-licensing.md) può aiutare con questa opzione.</span><span class="sxs-lookup"><span data-stu-id="b90d9-196">If needed, [Step 12](identity-group-based-licensing.md) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="b90d9-197">Come eseguire il test</span><span class="sxs-lookup"><span data-stu-id="b90d9-197">How to test</span></span>

1. <span data-ttu-id="b90d9-198">Creare un gruppo di sicurezza in Azure AD con il portale di Azure e configurare la gestione delle licenze basate su gruppo per assegnare le licenze di Office 365 ed EMS.</span><span class="sxs-lookup"><span data-stu-id="b90d9-198">Create a test security group in Azure AD with the Azure portal and configure group-based licensing to assign Office 365 and EMS licenses.</span></span>
2. <span data-ttu-id="b90d9-199">Creare un account utente di test in Azure AD e aggiungerlo al gruppo di sicurezza di test.</span><span class="sxs-lookup"><span data-stu-id="b90d9-199">Create a test user account in Azure AD and add it to the test security group.</span></span>
3. <span data-ttu-id="b90d9-200">Esaminare le proprietà dell'account utente nel portale di amministrazione di Office 365 per verificare che le licenze di Office 365 e EMS siano state assegnate.</span><span class="sxs-lookup"><span data-stu-id="b90d9-200">Examine the properties of the user account in the Office 365 admin portal to ensure that it was assigned the Office 365 and EMS licenses.</span></span>
4. <span data-ttu-id="b90d9-201">Rimuovere l'account utente di test dal gruppo di sicurezza di test.</span><span class="sxs-lookup"><span data-stu-id="b90d9-201">Remove the test user account from the test security group.</span></span>
5. <span data-ttu-id="b90d9-202">Esaminare le proprietà dell'account utente per verificare che non disponga più delle licenze di Office 365 ed EMS.</span><span class="sxs-lookup"><span data-stu-id="b90d9-202">Examine the properties of the user account to ensure that it no longer has the Office 365 and EMS licenses assigned.</span></span>
6. <span data-ttu-id="b90d9-203">Eliminare il gruppo di sicurezza di test e l'account utente di test.</span><span class="sxs-lookup"><span data-stu-id="b90d9-203">Delete the test security group and the test user account.</span></span>

<a name="crit-identity-dyn-groups"></a>
## <a name="optional-dynamic-group-membership-settings-automatically-add-user-accounts-to-groups-based-on-user-account-attributes"></a><span data-ttu-id="b90d9-204">Facoltativo: le impostazioni di appartenenza a gruppi dinamici aggiungono automaticamente gli account utente ai gruppi in base agli attributi degli account utente</span><span class="sxs-lookup"><span data-stu-id="b90d9-204">Optional: Dynamic group membership settings automatically add user accounts to groups based on user account attributes</span></span>

<span data-ttu-id="b90d9-205">È stato configurato il set di gruppi dinamici di Azure AD e sono state utilizzate le istruzioni presenti in [Creare regole basate su attributi per l'appartenenza dinamica ai gruppi in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal) per creare i gruppi e le regole che determinano il set di attributi dell'account utente e i valori di appartenenza ai gruppi.</span><span class="sxs-lookup"><span data-stu-id="b90d9-205">You've determined the set of Azure AD dynamic groups and used the instructions in [Attribute-based dynamic group membership in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal) to create the groups and the rules that determine the set of user account attributes and values for group membership.</span></span>

<span data-ttu-id="b90d9-p109">Se si ignora questa opzione, l'appartenenza ai gruppi deve essere eseguita manualmente quando vengono aggiunti nuovi account o se gli attributi degli account utente cambiano con il tempo. Ad esempio, se un utente passa dal Reparto vendite al Reparto contabilità, è necessario:</span><span class="sxs-lookup"><span data-stu-id="b90d9-p109">If you skip this option, group membership must be done manually as new accounts are added or as user account attributes change over time. For example, if someone moves from the Sales department to the Accounting department, you must:</span></span>

- <span data-ttu-id="b90d9-208">Aggiornare il valore dell'attributo del reparto per quell'account utente.</span><span class="sxs-lookup"><span data-stu-id="b90d9-208">Update the value of the Department attribute for that user account.</span></span>
- <span data-ttu-id="b90d9-209">Rimuovere manualmente l'account dal gruppo delle vendite.</span><span class="sxs-lookup"><span data-stu-id="b90d9-209">Manually remove them from the Sales group.</span></span>
- <span data-ttu-id="b90d9-210">Aggiungere manualmente l'account al gruppo della contabilità.</span><span class="sxs-lookup"><span data-stu-id="b90d9-210">Manually add them to the Accounting group.</span></span>

<span data-ttu-id="b90d9-211">Se il gruppo delle vendite e il gruppo della contabilità erano gruppi dinamici, sarà necessario solo cambiare il valore del reparto dell'account utente.</span><span class="sxs-lookup"><span data-stu-id="b90d9-211">If the Sales and Accounting groups were dynamic, you would only have to change the user account’s Department value.</span></span>

<span data-ttu-id="b90d9-212">Se necessario, il [Passaggio 15](identity-automatic-group-membership.md) può aiutare con questa opzione.</span><span class="sxs-lookup"><span data-stu-id="b90d9-212">If needed, [Step 15](identity-automatic-group-membership.md) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="b90d9-213">Come eseguire il test</span><span class="sxs-lookup"><span data-stu-id="b90d9-213">How to test</span></span>

1. <span data-ttu-id="b90d9-214">Creare un gruppo di test dinamico in Azure AD con il portale di Azure e configurare una regola il reparto uguale a "test1".</span><span class="sxs-lookup"><span data-stu-id="b90d9-214">Create a test dynamic group in Azure AD with the Azure portal and configure a rule for the Department equals “test1”.</span></span>
2. <span data-ttu-id="b90d9-215">Creare un account utente di test in Azure AD e impostare la proprietà del reparto su "test1".</span><span class="sxs-lookup"><span data-stu-id="b90d9-215">Create a test user account in Azure AD and set the Department property to “test1”.</span></span>
3. <span data-ttu-id="b90d9-216">Esaminare le proprietà dell'account utente per verificare che sia un membro del gruppo dinamico di test.</span><span class="sxs-lookup"><span data-stu-id="b90d9-216">Examine the properties of the user account to ensure that it was made a member of the test dynamic group.</span></span>
4. <span data-ttu-id="b90d9-217">Cambiare il valore della proprietà del reparto per l'account utente di test impostandolo su "test2".</span><span class="sxs-lookup"><span data-stu-id="b90d9-217">Change the value of the Department property for the test user account to “test2”.</span></span>
5. <span data-ttu-id="b90d9-218">Esaminare le proprietà dell'account utente per verificare che non sia più membro del gruppo dinamico di test.</span><span class="sxs-lookup"><span data-stu-id="b90d9-218">Examine the properties of the user account to ensure that it is no longer a member of the test dynamic group.</span></span>
6. <span data-ttu-id="b90d9-219">Eliminare il gruppo dinamico di test e l'account utente di test.</span><span class="sxs-lookup"><span data-stu-id="b90d9-219">Delete the test dynamic group and the test user account.</span></span>

<a name="crit-identity-self-service-groups"></a>
## <a name="optional-self-service-group-management-is-enabled-for-specific-azure-ad-security-and-office-365-groups"></a><span data-ttu-id="b90d9-220">Facoltativo: la gestione dei gruppi in modalità self-service è abilitata per specifici gruppi di sicurezza di Azure AD e Office 365</span><span class="sxs-lookup"><span data-stu-id="b90d9-220">Optional: Self-service group management is enabled for specific Azure AD security and Office 365 groups</span></span>

<span data-ttu-id="b90d9-221">È stato stabilito quali gruppi soddisfano i requisiti per la gestione in modalità self-service, i relativi proprietari sono stati istruiti sulle responsabilità e sul flusso di lavoro della gestione dei gruppi ed [è stata configurata la gestione in modalità self-service in Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management) per tali gruppi.</span><span class="sxs-lookup"><span data-stu-id="b90d9-221">You've determined which groups are appropriate for self-service management, instructed their owners on group management workflow and responsibilities, and [set up self-service management in Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management) for those groups.</span></span>

<span data-ttu-id="b90d9-222">Se si ignora questa opzione, tutte le attività di gestione dei gruppi di Azure AD, dovranno essere eseguite dagli amministratori IT.</span><span class="sxs-lookup"><span data-stu-id="b90d9-222">If you skip this option, all Azure AD group management tasks must be done by IT administrators.</span></span>

<span data-ttu-id="b90d9-223">Se necessario, il [Passaggio 14](identity-self-service-group-management.md) può aiutare con questa opzione.</span><span class="sxs-lookup"><span data-stu-id="b90d9-223">If needed, [Step 14](identity-self-service-group-management.md) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="b90d9-224">Come eseguire il test</span><span class="sxs-lookup"><span data-stu-id="b90d9-224">How to test</span></span>
1.  <span data-ttu-id="b90d9-225">Creare un account utente di test in Azure AD con il portale di Azure.</span><span class="sxs-lookup"><span data-stu-id="b90d9-225">Create a test user account in Azure AD with the Azure portal.</span></span>
2.  <span data-ttu-id="b90d9-226">Accedere con l'account utente di test e creare un gruppo di sicurezza di test di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="b90d9-226">Sign-in as with the test user account and create a test Azure AD security group.</span></span>
3.  <span data-ttu-id="b90d9-227">Disconnettersi ed effettuare di nuovo l'accesso con l'account amministratore IT.</span><span class="sxs-lookup"><span data-stu-id="b90d9-227">Sign out and then sign-in with your IT administrator account.</span></span>
4.  <span data-ttu-id="b90d9-228">Configurare il gruppo di sicurezza di test per la gestione in modalità self-service dell'account utente di test.</span><span class="sxs-lookup"><span data-stu-id="b90d9-228">Configure the test security group for self-service management for the test user account.</span></span>
5.  <span data-ttu-id="b90d9-229">Disconnettersi ed effettuare di nuovo l'accesso con l'account utente di test.</span><span class="sxs-lookup"><span data-stu-id="b90d9-229">Sign out and then sign-in with your test user account.</span></span>
6.  <span data-ttu-id="b90d9-230">Utilizzare il portale di Azure per aggiungere membri al gruppo di sicurezza di test.</span><span class="sxs-lookup"><span data-stu-id="b90d9-230">Use the Azure portal to add members to the test security group.</span></span>
7.  <span data-ttu-id="b90d9-231">Eliminare il gruppo di sicurezza di test e l'account utente di test.</span><span class="sxs-lookup"><span data-stu-id="b90d9-231">Delete the test security group and the test user account.</span></span>

<a name="crit-identity-ident-prot"></a>
## <a name="optional-azure-ad-identity-protection-is-enabled-to-protect-against-credential-compromise"></a><span data-ttu-id="b90d9-232">Facoltativo: Azure AD Identity Protection è abilitato per proteggere le credenziali da eventuali violazioni</span><span class="sxs-lookup"><span data-stu-id="b90d9-232">Optional: Azure AD Identity Protection is enabled to protect against credential compromise</span></span>

<span data-ttu-id="b90d9-233">Azure AD Identity Protection è stato abilitato per:</span><span class="sxs-lookup"><span data-stu-id="b90d9-233">You've enabled Azure AD Identity Protection to:</span></span>

- <span data-ttu-id="b90d9-234">Far fronte a potenziali vulnerabilità delle identità.</span><span class="sxs-lookup"><span data-stu-id="b90d9-234">Address potential identity vulnerabilities.</span></span>
- <span data-ttu-id="b90d9-235">Rilevare possibili tentativi di violazione delle credenziali.</span><span class="sxs-lookup"><span data-stu-id="b90d9-235">Detect possible credential compromise attempts.</span></span>
- <span data-ttu-id="b90d9-236">Ricercare le cause e risolvere attività sospette relative alle identità.</span><span class="sxs-lookup"><span data-stu-id="b90d9-236">Investigate and address ongoing suspicious identity incidents.</span></span>

<span data-ttu-id="b90d9-p110">Se si ignora questa opzione, non sarà possibile rilevare o contrastare tentativi di violazione delle credenziali o ricercare le cause dei problemi di sicurezza relativi alle identità. Questo potrebbe rendere l'organizzazione vulnerabile alla violazione delle credenziali e alla conseguente minaccia ai dati sensibili.</span><span class="sxs-lookup"><span data-stu-id="b90d9-p110">If you skip this option, you won’t be able to detect or automatically thwart credential compromise attempts or investigate identity-related security incidents. This potentially leaves your organization vulnerable to a successful credential compromise and the resulting threat to your organization’s sensitive data.</span></span>

<span data-ttu-id="b90d9-239">Se necessario, il [Passaggio 6](identity-azure-ad-identity-protection.md) può aiutare con questa opzione.</span><span class="sxs-lookup"><span data-stu-id="b90d9-239">If needed, [Step 6](identity-azure-ad-identity-protection.md) can help you with this option.</span></span>

<a name="crit-identity-pim"></a>
## <a name="optional-you-have-set-up-privileged-identity-management-to-support-on-demand-assignment-of-the-global-administrator-role"></a><span data-ttu-id="b90d9-240">Facoltativo: è stato configurato Privileged Identity Management per supportare l'assegnazione su richiesta del ruolo di amministratore globale</span><span class="sxs-lookup"><span data-stu-id="b90d9-240">Optional: You have set up Privileged Identity Management to support on-demand assignment of the global administrator role</span></span>

<span data-ttu-id="b90d9-241">Sono state utilizzate le istruzioni presenti in [Configurare Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure) per abilitare PIM nel tenant di Azure AD e sono stati configurati gli account di amministratore globale idonei per il ruolo di amministratori.</span><span class="sxs-lookup"><span data-stu-id="b90d9-241">You've used the instructions in [Configure Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure) to enable PIM in your Azure AD tenant and configured your global administrator accounts as eligible admins.</span></span>

<span data-ttu-id="b90d9-242">Inoltre, sono stati seguiti i consigli presenti in [Protezione dell'accesso con privilegi per le distribuzioni ibride e cloud in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices) per sviluppare una roadmap che protegga l'accesso con privilegi dagli attacchi informatici.</span><span class="sxs-lookup"><span data-stu-id="b90d9-242">You've also used the recommendations in [Securing privileged access for hybrid and cloud deployments in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices) to develop a roadmap that secures privileged access against cyber attackers.</span></span>

<span data-ttu-id="b90d9-243">Se si ignora questa opzione, gli account di amministratore globale potranno essere soggetti ad attacco online e, se violati, un utente malintenzionato potrà raccogliere, distruggere o conservare le informazioni riservate a scopo di ricatto.</span><span class="sxs-lookup"><span data-stu-id="b90d9-243">If you skip this option, your global administrator accounts are subject to ongoing online attack and, if compromised, can allow an attacker to harvest, destroy, or hold your sensitive information for ransom.</span></span>

<span data-ttu-id="b90d9-244">Se necessario, il [Passaggio 3](identity-azure-ad-identity-protection.md) può aiutare con questa opzione.</span><span class="sxs-lookup"><span data-stu-id="b90d9-244">If needed, [Step 3](identity-azure-ad-identity-protection.md) can help you with this option.</span></span>


## <a name="next-phase"></a><span data-ttu-id="b90d9-245">Fase successiva</span><span class="sxs-lookup"><span data-stu-id="b90d9-245">Next phase</span></span>

|||
|:-------|:-----|
|![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)| <span data-ttu-id="b90d9-246">La fase successiva del processo di distribuzione end-to-end per Microsoft 365 Enterprise è [Windows 10 Enterprise](windows10-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="b90d9-246">Your next phase in the end-to-end deployment process for Microsoft 365 Enterprise is [Windows 10 Enterprise](windows10-infrastructure.md).</span></span> |

