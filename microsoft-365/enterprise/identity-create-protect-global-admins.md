---
title: 'Passaggio 1: creare e proteggere gli account di amministratore globale'
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
description: Gli account di amministratore globale devono avere un trattamento speciale per proteggerli dal compromesso delle credenziali.
ms.openlocfilehash: 27b76671581ebd2dac32304752a85f8a6f60ac98
ms.sourcegitcommit: 6c8edbc54b193e964cf93aec48c51cb79231f1d9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2020
ms.locfileid: "42544035"
---
# <a name="step-1-create-and-protect-your-global-admin-accounts"></a><span data-ttu-id="6ad22-103">Passaggio 1: creare e proteggere gli account di amministratore globale</span><span class="sxs-lookup"><span data-stu-id="6ad22-103">Step 1: Create and protect your global admin accounts</span></span>

![Fase 2 - Identità](../media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-global-admin"></a>
## <a name="protect-global-administrator-accounts"></a><span data-ttu-id="6ad22-105">Proteggere gli account amministratore globale</span><span class="sxs-lookup"><span data-stu-id="6ad22-105">Protect global administrator accounts</span></span>

<span data-ttu-id="6ad22-106">*Questo passaggio è obbligatorio e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="6ad22-106">*This is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="6ad22-107">In questa sezione è possibile impedire attacchi digitali nell'organizzazione garantendo la massima sicurezza degli account amministratore.</span><span class="sxs-lookup"><span data-stu-id="6ad22-107">In this section, you'll help prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> <span data-ttu-id="6ad22-108">A tale scopo, è necessario:</span><span class="sxs-lookup"><span data-stu-id="6ad22-108">To do this, you must:</span></span>

- <span data-ttu-id="6ad22-109">Creare più account di amministratore globale dedicati con [password complesse](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password) e usarli solo se necessario.</span><span class="sxs-lookup"><span data-stu-id="6ad22-109">Create more than one dedicated global administrator accounts with [strong passwords](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password) and use them only when necessary.</span></span>
- <span data-ttu-id="6ad22-110">Eseguire attività di amministrazione quotidiane assegnando ruoli di amministratore specifici, come amministratore di Exchange o delle password ad altri account dedicati per questi ruoli o agli account utente del personale IT in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="6ad22-110">Perform day-to-day administration by assigning specific administrator roles—such as Exchange administrator or Password administrator—to other dedicated accounts for those roles or user accounts of IT staff as needed.</span></span>

<span data-ttu-id="6ad22-111">Per gli account di amministratore globale dedicati, è necessario inoltre:</span><span class="sxs-lookup"><span data-stu-id="6ad22-111">For your dedicated global admin accounts, you must also:</span></span>

1. <span data-ttu-id="6ad22-112">Testare l'account di ogni utente o le impostazioni dell'autenticazione a più fattori di Azure basata sull'accesso condizionale in un account utente di prova per assicurarsi che l'autenticazione a più fattori funzioni correttamente e come previsto.</span><span class="sxs-lookup"><span data-stu-id="6ad22-112">Test per-user account or Conditional Access-based Azure Multi-Factor Authentication (MFA) settings on a test user account to ensure that MFA works correctly and predictably.</span></span> <span data-ttu-id="6ad22-113">L'autenticazione a più fattori richiede una seconda forma di autenticazione, come il codice di verifica inviato a uno smartphone.</span><span class="sxs-lookup"><span data-stu-id="6ad22-113">MFA requires a secondary form of authentication, such as a verification code sent to a smart phone.</span></span>
2. <span data-ttu-id="6ad22-114">Creare e attivare un criterio di Accesso Condizionale per gli account di amministratore globale che richiedono l’autenticazione a due fattori e usare la forma più complessa di autenticazione secondaria disponibile nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="6ad22-114">Create and enable a Conditional Access policy for your global administrator accounts that requires MFA and uses the strongest form of secondary authentication available in your organization.</span></span> <span data-ttu-id="6ad22-115">Per altre informazioni, vedere [Autenticazione a più fattori di Azure](identity-access-prerequisites.md#protecting-administrator-accounts).</span><span class="sxs-lookup"><span data-stu-id="6ad22-115">See [Azure Multi-Factor Authentication](identity-access-prerequisites.md#protecting-administrator-accounts) for more information.</span></span>

<span data-ttu-id="6ad22-116">Per ulteriori protezioni, vedere [Proteggere gli account di amministratore globale di Office 365](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts#additional-protections-for-enterprise-organizations).</span><span class="sxs-lookup"><span data-stu-id="6ad22-116">See [Protect your Office 365 global administrator accounts](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts#additional-protections-for-enterprise-organizations) for additional protections.</span></span>

> [!Note]
> <span data-ttu-id="6ad22-117">Gli account di emergenza per scenari break-glass in situazioni di emergenza come cyberattacco devono essere solo account cloud.</span><span class="sxs-lookup"><span data-stu-id="6ad22-117">Emergency accounts for break-glass scenarios in emergencies such as a cyberattack should be cloud-only accounts.</span></span> <span data-ttu-id="6ad22-118">Potrebbero essere presenti anche degli account di amministratore globale (idonei o permanenti) che non sono solo cloud.</span><span class="sxs-lookup"><span data-stu-id="6ad22-118">You may also have global administrator accounts (eligible or permanent) that are not cloud-only.</span></span> <span data-ttu-id="6ad22-119">Per altre informazioni, vedere [Gestire gli account amministrativi di accesso di emergenza in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).</span><span class="sxs-lookup"><span data-stu-id="6ad22-119">For more information, see [Manage emergency-access administrative accounts in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).</span></span>

<span data-ttu-id="6ad22-120">I risultati di questa sezione sono:</span><span class="sxs-lookup"><span data-stu-id="6ad22-120">The results of this section are:</span></span>

- <span data-ttu-id="6ad22-121">Gli unici account utente dell'abbonamento a cui è assegnato il ruolo di amministratore globale sono gli account di amministratore globale dedicati.</span><span class="sxs-lookup"><span data-stu-id="6ad22-121">The only user accounts in your subscription that have the global admin role are the dedicated global administrator accounts.</span></span> <span data-ttu-id="6ad22-122">Per verificarlo, usare il comando seguente di Azure Active Directory PowerShell per Graph:</span><span class="sxs-lookup"><span data-stu-id="6ad22-122">Verify this with the following Azure Active Directory PowerShell for Graph command:</span></span> 
  ```powershell
  Get-AzureADDirectoryRole | Where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```
- <span data-ttu-id="6ad22-123">A tutti gli altri account utente che gestiscono i servizi dell'abbonamento sono assegnati ruoli di amministratore associati ai propri ruoli professionali.</span><span class="sxs-lookup"><span data-stu-id="6ad22-123">All other user accounts that manage your subscription services have admin roles assigned that are associated with their job responsibilities.</span></span>

> [!Note]
> <span data-ttu-id="6ad22-124">Vedere [Connettersi a PowerShell di Office 365](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) per le istruzioni sull'istallazione del modulo Azure Active Directory PowerShell for Graph e sull'accesso.</span><span class="sxs-lookup"><span data-stu-id="6ad22-124">See [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) for instructions on installing the Azure Active Directory PowerShell for Graph module and signing in.</span></span>

|||
|:-------|:-----|
|![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  <span data-ttu-id="6ad22-126">Per eseguire questa procedura in un ambiente di testing, vedere la Guida al lab di test [Proteggere gli account amministratore globale](protect-global-administrator-accounts-microsoft-365-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="6ad22-126">To practice this configuration in a test lab environment, see the [Protect global administrator accounts Test Lab Guide](protect-global-administrator-accounts-microsoft-365-test-environment.md).</span></span> |
|||

<span data-ttu-id="6ad22-127">Come checkpoint provvisorio, è possibile vedere i [criteri uscita](identity-exit-criteria.md#crit-identity-global-admin) per questa sezione.</span><span class="sxs-lookup"><span data-stu-id="6ad22-127">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-global-admin) for this section.</span></span>


<a name="identity-pim"></a>
## <a name="set-up-on-demand-administrators"></a><span data-ttu-id="6ad22-128">Configurare gli amministratori su richiesta</span><span class="sxs-lookup"><span data-stu-id="6ad22-128">Set up on-demand administrators</span></span>

<span data-ttu-id="6ad22-129">*Questo passaggio è facoltativo e si applica solo alla versione E5 di Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="6ad22-129">*This is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="6ad22-130">In questa sezione si procederà alla configurazione di Azure AD Privileged Identity Management (PIM) per ridurre la quantità di tempo per la quale gli account amministratore sono vulnerabili agli attacchi da parte di utenti malintenzionati.</span><span class="sxs-lookup"><span data-stu-id="6ad22-130">In this section, you'll set up Azure AD Privileged Identity Management (PIM) to reduce the amount of time that your administrator accounts are vulnerable to attack by malicious users.</span></span> <span data-ttu-id="6ad22-131">Su richiesta, PIM fornisce l'assegnazione JIT del ruolo di amministratore, se necessario.</span><span class="sxs-lookup"><span data-stu-id="6ad22-131">PIM provides on-demand, just-in-time assignment of the administrator roles when needed.</span></span>  

<span data-ttu-id="6ad22-132">Invece di essere amministratori permanenti degli account di amministratore, diventano amministratori idonei.</span><span class="sxs-lookup"><span data-stu-id="6ad22-132">Instead of your administrator accounts being permanent admins, they become eligible admins.</span></span> <span data-ttu-id="6ad22-133">Il ruolo di amministratore è inattivo finché qualcuno non lo richiede.</span><span class="sxs-lookup"><span data-stu-id="6ad22-133">The administrator role is inactive until someone needs it.</span></span> <span data-ttu-id="6ad22-134">Sarà quindi necessario completare un processo di attivazione per aggiungere il ruolo di amministratore all'account di amministratore per un determinato periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="6ad22-134">You'll then complete an activation process to add the administrator role to the administrator account for a specific amount of time.</span></span> <span data-ttu-id="6ad22-135">Al termine di tale periodo, PIM rimuove il ruolo di amministratore dall'account di amministratore.</span><span class="sxs-lookup"><span data-stu-id="6ad22-135">When the time expires, PIM removes the administrator role from the administrator account.</span></span>

<span data-ttu-id="6ad22-136">PIM è disponibile con Azure Active Directory Premium P2, incluso in Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="6ad22-136">PIM is available with Azure Active Directory Premium P2, which is included with Microsoft 365 E5.</span></span> <span data-ttu-id="6ad22-137">In alternativa, è possibile acquistare singole licenze di Azure Active Directory Premium P2 per gli account di amministratore.</span><span class="sxs-lookup"><span data-stu-id="6ad22-137">Alternately, you can purchase individual Azure Active Directory Premium P2 licenses for your administrator accounts.</span></span>

<span data-ttu-id="6ad22-138">Per attivare Azure PIM per gli account tenant e amministratore Azure Active Directory, vedere la [procedura per configurare PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).</span><span class="sxs-lookup"><span data-stu-id="6ad22-138">To enable Azure PIM for your Azure AD tenant and administrator accounts, see the [steps to configure PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).</span></span>

<span data-ttu-id="6ad22-139">Per sviluppare una roadmap che protegga l'accesso con privilegi dagli attacchi informatici, vedere [Protezione dell'accesso con privilegi per le distribuzioni ibride e cloud in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).</span><span class="sxs-lookup"><span data-stu-id="6ad22-139">To develop a comprehensive roadmap to secure privileged access against cyber attackers, see [Securing privileged access for hybrid and cloud deployments in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).</span></span>

<span data-ttu-id="6ad22-140">Come checkpoint provvisorio, è possibile vedere i [criteri uscita](identity-exit-criteria.md#crit-identity-pim) per questa sezione.</span><span class="sxs-lookup"><span data-stu-id="6ad22-140">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pim) for this section.</span></span>


<a name="identity-pam"></a>
## <a name="privileged-access-management"></a><span data-ttu-id="6ad22-141">Gestione accessi con privilegi</span><span class="sxs-lookup"><span data-stu-id="6ad22-141">Privileged access management</span></span>

<span data-ttu-id="6ad22-p109">La gestione degli accessi con privilegi è abilitata mediante la configurazione di criteri che specificano l'accesso just-in-time per le operazioni basate sulle attività nel tenant di Office 365. Può aumentare il livello di protezione dell'organizzazione da violazioni che possono usare account di amministratore privilegiato esistenti con accesso permanente a dati riservati o con accesso a impostazioni di configurazione cruciali. Ad esempio, è possibile configurare un criterio di gestione degli accessi con privilegi che richiede l'approvazione esplicita per accedere e modificare le impostazioni delle cassette postali dell'organizzazione nel tenant di Office 365.</span><span class="sxs-lookup"><span data-stu-id="6ad22-p109">Privileged access management is enabled by configuring policies that specify just-in-time access for task-based activities in your Office 365 tenant. It can help protect your organization from breaches that may use existing privileged administrator accounts with standing access to sensitive data or access to critical configuration settings. For example, you could configure a privileged access management policy that requires explicit approval to access and change organization mailbox settings in your Office 365 tenant.</span></span>

<span data-ttu-id="6ad22-p110">In questo passaggio verrà abilitata la gestione degli accessi con privilegi nel tenant di Office 365 e verranno configurati i criteri di accesso con privilegi che garantiscono una maggiore protezione per gli accessi basati sulle attività a impostazioni dati e configurazione di Office 365 dell’organizzazione. Esistono tre passaggi di base per iniziare a usare gli accessi con privilegi nell'organizzazione di Office 365:</span><span class="sxs-lookup"><span data-stu-id="6ad22-p110">In this step, you'll enable privileged access management in your Office 365 tenant and configure privileged access policies that provide additional security for task-based access to Office 365 data and configuration settings for your organization. There are three basic steps to get started with privileged access in your Office 365 organization:</span></span>

- <span data-ttu-id="6ad22-147">Creazione di un gruppo responsabile dell'approvazione</span><span class="sxs-lookup"><span data-stu-id="6ad22-147">Creating an approver's group</span></span>
- <span data-ttu-id="6ad22-148">Abilitazione dell’accesso con privilegi</span><span class="sxs-lookup"><span data-stu-id="6ad22-148">Enabling privileged access</span></span>
- <span data-ttu-id="6ad22-149">Creazione di criteri per l'approvazione</span><span class="sxs-lookup"><span data-stu-id="6ad22-149">Creating approval policies</span></span>

<span data-ttu-id="6ad22-p111">Una volta configurata, la gestione degli accessi con privilegi consentirà all'organizzazione di operare con privilegi permanenti uguali a zero e di fornire un livello di protezione contro vulnerabilità che si verificano a causa di questo tipo di accesso amministrativo permanente. L’accesso con privilegi richiede l'approvazione per l'esecuzione di tutte le attività associate a un criterio di approvazione definito. Gli utenti che necessitano di eseguire attività incluse nei criteri di approvazione devono richiedere e ottenere l'approvazione di accesso per disporre delle autorizzazioni necessarie a eseguire le attività definite nel criterio.</span><span class="sxs-lookup"><span data-stu-id="6ad22-p111">One configured, privileged access management will enable your organization to operate with zero standing privileges and provide a layer of defense against vulnerabilities arising because of such standing administrative access. Privileged access requires approvals for executing any task that has an associated approval policy defined. Users needing to execute tasks included in the an approval policy must request and be granted access approval in order to have permissions necessary to execute tasks defined in the policy.</span></span>

<span data-ttu-id="6ad22-153">Per abilitare la gestione degli accessi con privilegi di Office 365, vedere l’argomento [Configurare la gestione degli accessi con privilegi in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration).</span><span class="sxs-lookup"><span data-stu-id="6ad22-153">To enable Office 365 privileged access management, see the [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic.</span></span>

<span data-ttu-id="6ad22-154">Per ulteriori informazioni, vedere l’argomento [Gestione degli accessi con privilegi in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).</span><span class="sxs-lookup"><span data-stu-id="6ad22-154">For more information, see the [Privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview) topic.</span></span>


|||
|:-------|:-----|
|![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  <span data-ttu-id="6ad22-156">Per eseguire questa procedura in un ambiente di testing, vedere la [Guida al lab di test gestione degli accessi privilegiati](privileged-access-microsoft-365-enterprise-dev-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="6ad22-156">To practice this configuration in a test lab environment, see the [Privileged access management Test Lab Guide](privileged-access-microsoft-365-enterprise-dev-test-environment.md).</span></span> |
|||

<span data-ttu-id="6ad22-157">Come checkpoint provvisorio, vedere i [criteri uscita](identity-exit-criteria.md#crit-identity-pam) che corrispondono a questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="6ad22-157">As an interim checkpoint, see the [exit criteria](identity-exit-criteria.md#crit-identity-pam) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="6ad22-158">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="6ad22-158">Next step</span></span>

|||
|:-------|:-----|
|![Passaggio 2](../media/stepnumbers/Step2.png)| [<span data-ttu-id="6ad22-160">Proteggere le password</span><span class="sxs-lookup"><span data-stu-id="6ad22-160">Secure your passwords</span></span>](identity-secure-your-passwords.md) |

