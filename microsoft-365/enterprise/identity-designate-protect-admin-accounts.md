---
title: 'Passaggio 2: Proteggere le identità con privilegi'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Comprendere e configurare gli account di amministratore per la massima protezione.
ms.openlocfilehash: 8a1d232ffc0242766d79b2e4884582f3b5524d22
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "34074056"
---
# <a name="step-2-secure-your-privileged-identities"></a><span data-ttu-id="4ad2a-103">Passaggio 2: Proteggere le identità con privilegi</span><span class="sxs-lookup"><span data-stu-id="4ad2a-103">Step 2: Secure your privileged identities</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-global-admin"></a>
## <a name="protect-global-administrator-accounts"></a><span data-ttu-id="4ad2a-104">Proteggere gli account amministratore globale</span><span class="sxs-lookup"><span data-stu-id="4ad2a-104">Protect global administrator accounts</span></span>

<span data-ttu-id="4ad2a-105">*Questo passaggio è obbligatorio e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="4ad2a-105">*This is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="4ad2a-106">In questa sezione è possibile impedire attacchi digitali nell'organizzazione garantendo la massima sicurezza degli account amministratore.</span><span class="sxs-lookup"><span data-stu-id="4ad2a-106">In this section, you'll help prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> <span data-ttu-id="4ad2a-107">A tale scopo, è necessario:</span><span class="sxs-lookup"><span data-stu-id="4ad2a-107">To do this, you must:</span></span>

- <span data-ttu-id="4ad2a-108">Creare account amministratore globale dedicati con [password molto complesse](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password) e usarli solo se necessario.</span><span class="sxs-lookup"><span data-stu-id="4ad2a-108">Create dedicated global administrator accounts with very [strong passwords](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password) and use them only when necessary.</span></span>
- <span data-ttu-id="4ad2a-109">Eseguire attività di amministrazione quotidiane assegnando ruoli di amministratore specifici, come amministratore di Exchange o delle password agli account utente del personale IT in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="4ad2a-109">Perform day-to-day administration by assigning specific administrator roles—such as Exchange administrator or Password administrator—to user accounts of IT staff as needed.</span></span>

<span data-ttu-id="4ad2a-110">Per gli account di amministratore globale dedicati, è necessario inoltre:</span><span class="sxs-lookup"><span data-stu-id="4ad2a-110">For your dedicated global admin accounts, you must also:</span></span>

1. <span data-ttu-id="4ad2a-p102">Testare l'account di ogni utente o le impostazioni dell'autenticazione a più fattori basata sull'accesso condizionale in un account utente di prova per assicurarsi che l'autenticazione a più fattori funzioni correttamente e come previsto. L'autenticazione a più fattori richiede una seconda forma di autenticazione, come il codice di verifica inviato a uno smartphone.</span><span class="sxs-lookup"><span data-stu-id="4ad2a-p102">Test per-user account or conditional access-based multi-factor authentication (MFA) settings on a test user account to ensure that MFA works correctly and predictably. MFA requires a secondary form of authentication, such as a verification code sent to a smart phone.</span></span>
2. <span data-ttu-id="4ad2a-p103">Configurare l'autenticazione a più fattori per ogni account amministratore globale di Office 365 dedicato e usare la forma più forte di autenticazione secondaria disponibile nell'organizzazione. Vedere [Autenticazione a più fattori](identity-multi-factor-authentication.md#identity-mfa) per maggiori informazioni.</span><span class="sxs-lookup"><span data-stu-id="4ad2a-p103">Configure MFA for each of the dedicated Office 365 global administrator accounts, and use the strongest form of secondary authentication available in your organization. See [Multi-factor authentication](identity-multi-factor-authentication.md#identity-mfa) for more information.</span></span>
2. <span data-ttu-id="4ad2a-p104">Usare un criterio di accesso condizionale per richiedere l'autenticazione a più fattori per gli account di amministratore globale. Per ulteriori informazioni, vedere [Protezione degli account di amministratore](identity-access-prerequisites.md#protecting-administrator-accounts).</span><span class="sxs-lookup"><span data-stu-id="4ad2a-p104">Use a conditional access policy to require MFA for global administrator accounts. See [Protecting administrator accounts](identity-access-prerequisites.md#protecting-administrator-accounts) for more information.</span></span>

<span data-ttu-id="4ad2a-117">Vedere [Proteggere gli account di amministratore globale di Office 365](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts) per ulteriori informazioni sulla configurazione.</span><span class="sxs-lookup"><span data-stu-id="4ad2a-117">See [Protect your Office 365 global administrator accounts](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts) for more information about configuration.</span></span>

> [!Note]
> <span data-ttu-id="4ad2a-p105">Le organizzazioni dovrebbero utilizzare identità solo cloud per creare account con privilegi, come gli amministratori globali, per scenari di intrusione durante le emergenze, come un cyberattacco. Per ulteriori informazioni, vedere [Gestire gli account amministrativi per accessi di emergenza in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).</span><span class="sxs-lookup"><span data-stu-id="4ad2a-p105">Organizations should use cloud-only identities to create privileged accounts, such as global administrators, for break-glass scenarios in emergencies, such as a cyberattack. For more information, see [Manage emergency-access administrative accounts in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).</span></span>

<span data-ttu-id="4ad2a-120">I risultati di questa sezione sono:</span><span class="sxs-lookup"><span data-stu-id="4ad2a-120">The results of this section are:</span></span>

- <span data-ttu-id="4ad2a-121">Gli unici account utente dell'abbonamento a cui è assegnato il ruolo di amministratore globale sono i nuovi account di amministratore globale dedicati.</span><span class="sxs-lookup"><span data-stu-id="4ad2a-121">The only user accounts in your subscription that have the global admin role are the new set of dedicated global administrator accounts.</span></span> <span data-ttu-id="4ad2a-122">Per verificarlo, usare il comando seguente di Azure Active Directory PowerShell for Graph:</span><span class="sxs-lookup"><span data-stu-id="4ad2a-122">Verify this with the following Azure Active Directory PowerShell for Graph command:</span></span> 
  ```
  Get-AzureADDirectoryRole | Where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```
- <span data-ttu-id="4ad2a-123">A tutti gli altri account utente quotidiani che gestiscono l'abbonamento sono assegnati ruoli di amministratore associati ai propri ruoli professionali.</span><span class="sxs-lookup"><span data-stu-id="4ad2a-123">All other everyday user accounts that manage your subscription have admin roles assigned that are associated with their job responsibilities.</span></span>

> [!Note]
> <span data-ttu-id="4ad2a-124">Vedere [Connettersi a PowerShell di Office 365](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) per le istruzioni sull'istallazione del modulo Azure Active Directory PowerShell for Graph e sull'accesso.</span><span class="sxs-lookup"><span data-stu-id="4ad2a-124">See [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) for instructions on installing the Azure Active Directory PowerShell for Graph module and signing in.</span></span>

|||
|:-------|:-----|
|![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="4ad2a-126">Guida al lab di test: proteggere gli account amministratore globale</span><span class="sxs-lookup"><span data-stu-id="4ad2a-126">Test Lab Guide: Protect global administrator accounts</span></span>](protect-global-administrator-accounts-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="4ad2a-127">Come checkpoint provvisorio, è possibile vedere i [criteri uscita](identity-exit-criteria.md#crit-identity-global-admin) per questa sezione.</span><span class="sxs-lookup"><span data-stu-id="4ad2a-127">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-global-admin) for this section.</span></span>


<a name="identity-pim"></a>
## <a name="set-up-on-demand-global-administrators"></a><span data-ttu-id="4ad2a-128">Configurare gli amministratori globali su richiesta</span><span class="sxs-lookup"><span data-stu-id="4ad2a-128">Set up on-demand global administrators</span></span>

<span data-ttu-id="4ad2a-129">*Questo passaggio è facoltativo e si applica solo alla versione E5 di Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="4ad2a-129">*This is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="4ad2a-130">In questa sezione si procederà alla configurazione di Azure AD Privileged Identity Management (PIM) per ridurre la quantità di tempo per la quale gli account amministratore globale sono vulnerabili agli attacchi da parte di utenti malintenzionati.</span><span class="sxs-lookup"><span data-stu-id="4ad2a-130">In this section, you'll set up Azure AD Privileged Identity Management (PIM) to reduce the amount of time that your global administrator accounts are vulnerable to attack by malicious users.</span></span> <span data-ttu-id="4ad2a-131">Su richiesta, PIM fornisce l'assegnazione JIT del ruolo di amministratore globale, se necessario.</span><span class="sxs-lookup"><span data-stu-id="4ad2a-131">PIM provides on-demand, just-in-time assignment of the global administrator role when needed.</span></span>  

<span data-ttu-id="4ad2a-p108">Gli account amministratore globale non sono amministratori permanenti, ma diventano amministratori idonei. Il ruolo di amministratore globale è inattivo fino a quando un utente ne ha bisogno. A questo punto verrà completato un processo di attivazione per aggiungere il ruolo di amministratore globale all'account dell'amministratore globale per un periodo di tempo specifico. Quando il tempo scade, PIM rimuove il ruolo di amministratore globale dall'account amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="4ad2a-p108">Instead of your global administrator accounts being a permanent admin, they become eligible admins. The global administrator role is inactive until someone needs it. You'll then complete an activation process to add the global administrator role to the global administrator account for a specific amount of time. When the time expires, PIM removes the global administrator role from the global administrator account.</span></span>

<span data-ttu-id="4ad2a-p109">PIM è disponibile con Azure Active Directory Premium P2, incluso con Microsoft 365 Enterprise E5. In alternativa, è possibile acquistare delle licenze singole per Azure Active Directory Premium P2 per gli account amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="4ad2a-p109">PIM is available with Azure Active Directory Premium P2, which is included with Microsoft 365 Enterprise E5. Alternately, you can purchase individual Azure Active Directory Premium P2 licenses for your global administrator accounts.</span></span>

<span data-ttu-id="4ad2a-138">Per attivare Azure PIM per gli account tenant e amministratore globale Azure Active Directory, vedere la [procedura per configurare PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).</span><span class="sxs-lookup"><span data-stu-id="4ad2a-138">To enable Azure PIM for your Azure AD tenant and global administrator accounts, see the [steps to configure PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).</span></span>

<span data-ttu-id="4ad2a-139">Per sviluppare una roadmap che protegga l'accesso con privilegi dagli attacchi informatici, vedere [Protezione dell'accesso con privilegi per le distribuzioni ibride e cloud in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).</span><span class="sxs-lookup"><span data-stu-id="4ad2a-139">To develop a comprehensive roadmap to secure privileged access against cyber attackers, see [Securing privileged access for hybrid and cloud deployments in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).</span></span>

<span data-ttu-id="4ad2a-140">Come checkpoint provvisorio, è possibile vedere i [criteri uscita](identity-exit-criteria.md#crit-identity-pim) per questa sezione.</span><span class="sxs-lookup"><span data-stu-id="4ad2a-140">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pim) for this section.</span></span>


## <a name="next-step"></a><span data-ttu-id="4ad2a-141">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="4ad2a-141">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)| [<span data-ttu-id="4ad2a-142">Configurare l'identità ibrida</span><span class="sxs-lookup"><span data-stu-id="4ad2a-142">Configure hybrid identity</span></span>](identity-azure-ad-connect.md) |

