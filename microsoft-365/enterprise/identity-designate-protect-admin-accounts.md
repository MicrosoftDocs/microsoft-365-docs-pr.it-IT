---
title: 'Passaggio 2: proteggere gli account amministratore globale'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Comprendere e configurare gli account di amministratore per la massima protezione.
ms.openlocfilehash: ccab7c8526817ee5140a5315c56f6f8a42f085d2
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868916"
---
# <a name="step-2-protect-global-administrator-accounts"></a><span data-ttu-id="004c4-103">Passaggio 2: proteggere gli account amministratore globale</span><span class="sxs-lookup"><span data-stu-id="004c4-103">Step 2: Protect global administrator accounts</span></span>

<span data-ttu-id="004c4-104">*Questo passaggio è obbligatorio e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="004c4-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="004c4-p101">In questo passaggio, è possibile impedire attacchi digitali nell'organizzazione garantendo la massima sicurezza degli account amministratore. Per farlo, è necessario:</span><span class="sxs-lookup"><span data-stu-id="004c4-p101">In Step 5, you'll help prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible. To do this, you must:</span></span>

- <span data-ttu-id="004c4-107">Creare account amministratore globale dedicati con [password molto complesse](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password) e usarli solo se necessario.</span><span class="sxs-lookup"><span data-stu-id="004c4-107">Create dedicated global administrator accounts with very [strong passwords](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password) and use them only when necessary.</span></span>
- <span data-ttu-id="004c4-108">Eseguire attività di amministrazione quotidiane assegnando ruoli di amministratore specifici, come amministratore di Exchange o delle password agli account utente del personale IT in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="004c4-108">Perform day-to-day administration by assigning specific administrator roles—such as Exchange administrator or Password administrator—to user accounts of IT staff as needed.</span></span>

<span data-ttu-id="004c4-109">Per gli account di amministratore globale dedicati, è necessario inoltre:</span><span class="sxs-lookup"><span data-stu-id="004c4-109">For your dedicated global admin accounts, you must also:</span></span>

1. <span data-ttu-id="004c4-p102">Testare l'account di ogni utente o le impostazioni dell'autenticazione a più fattori basata sull'accesso condizionale in un account utente di prova per assicurarsi che l'autenticazione a più fattori funzioni correttamente e come previsto. L'autenticazione a più fattori richiede una seconda forma di autenticazione, come il codice di verifica inviato a uno smartphone.</span><span class="sxs-lookup"><span data-stu-id="004c4-p102">Test per-user account or conditional access-based multi-factor authentication (MFA) settings on a test user account to ensure that MFA works correctly and predictably. MFA requires a secondary form of authentication, such as a verification code sent to a smart phone.</span></span>
2. <span data-ttu-id="004c4-p103">Configurare l'autenticazione a più fattori per ogni account amministratore globale di Office 365 dedicato e usare la forma più forte di autenticazione secondaria disponibile nell'organizzazione. Vedere [Autenticazione a più fattori](identity-multi-factor-authentication.md) per maggiori informazioni.</span><span class="sxs-lookup"><span data-stu-id="004c4-p103">Configure MFA for each of the dedicated Office 365 global administrator accounts, and use the strongest form of secondary authentication available in your organization. See [Multi-factor authentication](identity-multi-factor-authentication.md) for more information.</span></span>
2. <span data-ttu-id="004c4-p104">Usare un criterio di accesso condizionale per richiedere l'autenticazione a più fattori per gli account di amministratore globale. Per ulteriori informazioni, vedere [Protezione degli account di amministratore](identity-access-prerequisites.md#protecting-administrator-accounts).</span><span class="sxs-lookup"><span data-stu-id="004c4-p104">Use a conditional access policy to require MFA for global administrator accounts. See [Protecting administrator accounts](identity-access-prerequisites.md#protecting-administrator-accounts) for more information.</span></span>
4. <span data-ttu-id="004c4-p105">Utilizzare un criterio Office 365 Cloud App Security per monitorare l'attività dell'account amministratore globale. Per maggiori informazioni, vedere [Configurare un livello di sicurezza maggiore per Office 365](infoprotect-configure-increased-security-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="004c4-p105">Use an Office 365 Cloud App Security policy to monitor global administrator account activity. See [Information protection for Microsoft 365 Enterprise](infoprotect-configure-increased-security-office-365.md) for more information.</span></span>

<span data-ttu-id="004c4-118">Vedere [Proteggere gli account di amministratore globale di Office 365](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts) per ulteriori informazioni sulla configurazione.</span><span class="sxs-lookup"><span data-stu-id="004c4-118">See [Protect your Office 365 global administrator accounts](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts) for more information about configuration.</span></span>

> [!Note]
> <span data-ttu-id="004c4-p106">Le organizzazioni dovrebbero utilizzare identità solo cloud per creare account con privilegi, come gli amministratori globali, per scenari di intrusione durante le emergenze, come un cyberattacco. Per ulteriori informazioni, vedere [Gestire gli account amministrativi per accessi di emergenza in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).</span><span class="sxs-lookup"><span data-stu-id="004c4-p106">Organizations should use cloud-only identities to create privileged accounts, such as global administrators, for break-glass scenarios in emergencies, such as a cyberattack. For more information, see [Manage emergency-access administrative accounts in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).</span></span>

<span data-ttu-id="004c4-121">I risultati di questo passaggio sono:</span><span class="sxs-lookup"><span data-stu-id="004c4-121">The results of this step are:</span></span>

- <span data-ttu-id="004c4-p107">Gli unici account utente nell'abbonamento a cui è assegnato il ruolo di amministratore globale sono il nuovo set di account di amministratore globale dedicati. Per verificarlo, usare il comando PowerShell V2 di Windows Azure Active Directory:</span><span class="sxs-lookup"><span data-stu-id="004c4-p107">The only user accounts in your subscription that have the global admin role are the new set of dedicated global administrator accounts. Verify this with the following Windows Azure AD V2 PowerShell command:</span></span> 
  ```
  Get-AzureADDirectoryRole | Where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```
- <span data-ttu-id="004c4-124">A tutti gli altri account utente quotidiani che gestiscono l'abbonamento sono assegnati ruoli di amministratore associati ai propri ruoli professionali.</span><span class="sxs-lookup"><span data-stu-id="004c4-124">All other everyday user accounts that manage your subscription have admin roles assigned that are associated with their job responsibilities.</span></span>

> [!Note]
> <span data-ttu-id="004c4-125">Vedere [Connettersi a PowerShell di Office 365](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) per le istruzioni sull'installazione del modulo Azure AD V2 PowerShell e su come accedere.</span><span class="sxs-lookup"><span data-stu-id="004c4-125">See [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) for instructions on installing the Azure AD V2 PowerShell module and signing in.</span></span>

|||
|:-------|:-----|
|![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="004c4-127">Guida al lab di test: proteggere gli account amministratore globale</span><span class="sxs-lookup"><span data-stu-id="004c4-127">Test Lab Guide: Protect global administrator accounts</span></span>](protect-global-administrator-accounts-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="004c4-128">Come checkpoint provvisorio, è possibile vedere i [criteri uscita](identity-exit-criteria.md#crit-identity-global-admin) per questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="004c4-128">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-global-admin) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="004c4-129">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="004c4-129">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)| [<span data-ttu-id="004c4-130">Configurare gli amministratori globali su richiesta</span><span class="sxs-lookup"><span data-stu-id="004c4-130">Set up on-demand global administrators</span></span>](identity-privileged-identity-management.md) |

