---
title: "Passaggio 5: configurare l'autenticazione a più fattori"
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/05/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Comprendere e configurare l'autenticazione a più fattori per gli account utente.
ms.openlocfilehash: a54eb047c94430a2b3f61d06500c929e400e3d82
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868763"
---
# <a name="step-5-set-up-multi-factor-authentication"></a><span data-ttu-id="f98bc-103">Passaggio 5: configurare l'autenticazione a più fattori</span><span class="sxs-lookup"><span data-stu-id="f98bc-103">Step 5: Set up multi-factor authentication</span></span>

<span data-ttu-id="f98bc-104">*Questo passaggio è facoltativo e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="f98bc-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="f98bc-p101">Con questo passaggio è possibile configurare l'autenticazione a più fattori (MFA) per aggiungere un secondo livello di protezione per l'accesso e le transazioni utente. La MFA richiede una verifica aggiuntiva dopo l'immissione della password da parte dell'utente. Senza la MFA, la password rimane l'unico metodo di verifica. Molte password potrebbero essere indovinate facilmente da un utente malintenzionato o condivise inavvertitamente con parti non attendibili.</span><span class="sxs-lookup"><span data-stu-id="f98bc-p101">In Step 7, you'll set up multi-factor authentication (MFA) to add a second layer of security to user sign-ins and transactions. MFA requires an additional verification method after users have correctly entered their password. Without MFA, the password is the only verification method. The problem with passwords is that many of them are easily guessed by an attacker or unknowingly shared with untrusted parties.</span></span>

<span data-ttu-id="f98bc-109">Con la MFA, il secondo livello di sicurezza può essere:</span><span class="sxs-lookup"><span data-stu-id="f98bc-109">With MFA, the second layer of security can be:</span></span>

- <span data-ttu-id="f98bc-110">Un dispositivo personale e attendibile che non può essere oggetto di spoofing o duplicazioni, come per esempio uno smartphone.</span><span class="sxs-lookup"><span data-stu-id="f98bc-110">A personal and trusted device that isn’t easily spoofed or duplicated, such as a smart phone.</span></span>
- <span data-ttu-id="f98bc-111">Un attributo biometrico, come per esempio un'impronta digitale.</span><span class="sxs-lookup"><span data-stu-id="f98bc-111">A biometric attribute, such as a fingerprint.</span></span>

<span data-ttu-id="f98bc-p102">Abilitando la MFA si configura il metodo secondario di autenticazione per ogni account utente. È necessario comunicare agli utenti che la MFA è abilitata, in modo che comprendano i requisiti, come l'utilizzo obbligatorio di uno smartphone per effettuare l'accesso, e possano effettuare l'accesso con esito positivo.</span><span class="sxs-lookup"><span data-stu-id="f98bc-p102">You'll enable MFA and configure the secondary authentication method on a per-user account basis. Make sure to let users know that MFA is being enabled so they understand the requirements (such as mandatory use of a smart phone to sign in) and can sign in successfully.</span></span>

<span data-ttu-id="f98bc-114">Per maggiori informazioni, vedere [Pianificare l'autenticazione a più fattori per le distribuzioni di Office 365](https://support.office.com/article/Plan-for-multifactor-authentication-for-Office-365-Deployments-043807b2-21db-4d5c-b430-c8a6dee0e6ba)</span><span class="sxs-lookup"><span data-stu-id="f98bc-114">For more information, see [Plan for multi-factor authentication for Office 365 Deployments](https://support.office.com/article/Plan-for-multifactor-authentication-for-Office-365-Deployments-043807b2-21db-4d5c-b430-c8a6dee0e6ba).</span></span>

<span data-ttu-id="f98bc-115">Per configurare l'autenticazione a più fattori, [Configurare l'autenticazione a più fattori per gli utenti di Office 365](https://support.office.com/article/Set-up-multi-factor-authentication-for-Office-365-users-8f0454b2-f51a-4d9c-bcde-2c48e41621c6).</span><span class="sxs-lookup"><span data-stu-id="f98bc-115">To configure multifactor authentication, [Set up multi-factor authentication for Office 365 users](https://support.office.com/article/Set-up-multi-factor-authentication-for-Office-365-users-8f0454b2-f51a-4d9c-bcde-2c48e41621c6).</span></span>

<span data-ttu-id="f98bc-p103">È possibile richiedere la MFA con i criteri di accesso condizionale. Ad esempio, è possibile configurare un criterio di richiesta di MFA quando l'autenticazione è considerata di rischio medio o alto. Per ulteriori informazioni, vedere [Criteri comuni di identità e accesso dei dispositivi](identity-access-policies.md#require-mfa-based-on-sign-in-risk).</span><span class="sxs-lookup"><span data-stu-id="f98bc-p103">You can also require MFA with conditional access policies. For example, you can configure a policy that required MFA when the authentication is determined to be of medium or high risk. For more information, see [Step 2: Configure conditional access policy settings](identity-access-policies.md#require-mfa-based-on-sign-in-risk) in the Information Protection phase.</span></span>

>[!Note]
><span data-ttu-id="f98bc-p104">In alcune applicazioni, come per esempio Microsoft Office 2010 o le applicazioni più vecchie di Apple Mail, non è possibile utilizzare la MFA. Per utilizzare queste app, sarà necessario utilizzare le "password dell'app" al posto della password tradizionale. La password dell'app consente di bypassare la MFA e continuare a lavorare. Per ulteriori informazioni sulle password dell'app, vedere [Creare una password dell'app per Office 365](https://support.office.com/article/Create-an-app-password-for-Office-365-3e7c860f-bda4-4441-a618-b53953ee1183).</span><span class="sxs-lookup"><span data-stu-id="f98bc-p104">In some applications, such as Microsoft Office 2010 or older and Apple Mail, you can’t use MFA. To use these apps, you’ll need to use “app passwords” in place of your traditional password. The app password allows the app to bypass MFA and continue working. To learn more about app passwords, see [Create an app password for Office 365](https://support.office.com/article/Create-an-app-password-for-Office-365-3e7c860f-bda4-4441-a618-b53953ee1183).</span></span>
>

|||
|:-------|:-----|
|![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="f98bc-124">Guida al lab di test: autenticazione a più fattori</span><span class="sxs-lookup"><span data-stu-id="f98bc-124">Test Lab Guide: Multi-factor authentication</span></span>](multi-factor-authentication-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="f98bc-125">Come checkpoint provvisorio, è possibile vedere i [criteri uscita](identity-exit-criteria.md#crit-identity-mfa) per questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="f98bc-125">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-mfa) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="f98bc-126">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="f98bc-126">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step6.png)| [<span data-ttu-id="f98bc-127">Proteggere dalla compromissione delle credenziali</span><span class="sxs-lookup"><span data-stu-id="f98bc-127">Protect against credential compromise</span></span>](identity-azure-ad-identity-protection.md) |

