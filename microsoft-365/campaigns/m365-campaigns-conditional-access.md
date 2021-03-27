---
title: Attivare le impostazioni predefinite di sicurezza
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: Informazioni su come le impostazioni predefinite di sicurezza consentono di proteggere l'organizzazione da attacchi correlati all'identità fornendo impostazioni di sicurezza preconfigurate.
ms.openlocfilehash: ea36ba45af26a767b08ee1e75931dca54dacea64
ms.sourcegitcommit: c5d1528559953c6db7dca1d5cb453e0aa3215f02
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/27/2021
ms.locfileid: "51398292"
---
# <a name="turn-on-security-defaults"></a><span data-ttu-id="7404d-103">Attivare le impostazioni predefinite di sicurezza</span><span class="sxs-lookup"><span data-stu-id="7404d-103">Turn on security defaults</span></span>

<span data-ttu-id="7404d-104">Le impostazioni predefinite di sicurezza consentono di proteggere l'organizzazione da attacchi correlati all'identità fornendo impostazioni di sicurezza preconfigurate gestite da Microsoft per conto dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7404d-104">Security defaults help protect your organization from identity-related attacks by providing preconfigured security settings that Microsoft manages on behalf of your organization.</span></span> <span data-ttu-id="7404d-105">Queste impostazioni includono l'abilitazione dell'autenticazione a più fattori (MFA) per tutti gli amministratori e gli account utente.</span><span class="sxs-lookup"><span data-stu-id="7404d-105">These settings include enabling multi-factor authentication (MFA) for all admins and user accounts.</span></span> <span data-ttu-id="7404d-106">Per la maggior parte delle organizzazioni, le impostazioni predefinite di sicurezza offrono un buon livello di sicurezza aggiuntiva per l'accesso.</span><span class="sxs-lookup"><span data-stu-id="7404d-106">For most organizations, security defaults offer a good level of additional sign-in security.</span></span>

<span data-ttu-id="7404d-107">Per ulteriori informazioni sulle impostazioni predefinite di sicurezza e sui criteri applicati, vedere [What are security defaults?](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span><span class="sxs-lookup"><span data-stu-id="7404d-107">For more information about security defaults and the policies they enforce, see [What are security defaults?](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span></span>

<span data-ttu-id="7404d-108">Se l'abbonamento è stato creato il 22 ottobre 2019 o dopo il 22 ottobre 2019, è possibile che siano state abilitate automaticamente le impostazioni per verificare &mdash; le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="7404d-108">If your subscription was created on or after October 22, 2019, security defaults might have been automatically enabled for you&mdash;you should check your settings to confirm.</span></span>

<span data-ttu-id="7404d-109">Per abilitare le impostazioni predefinite di sicurezza in Azure Active Directory (Azure AD) o per verificare se sono già abilitate:</span><span class="sxs-lookup"><span data-stu-id="7404d-109">To enable security defaults in your Azure Active Directory (Azure AD) or to check to see if they're already enabled:</span></span>

1. <span data-ttu-id="7404d-110">Accedere all'interfaccia di amministrazione di <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365</a> con le credenziali di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="7404d-110">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a> with Global admin credentials.</span></span>

2. <span data-ttu-id="7404d-111">Nel riquadro sinistro selezionare **Mostra tutto e quindi** in Interfaccia di **amministrazione** selezionare Azure **Active Directory.**</span><span class="sxs-lookup"><span data-stu-id="7404d-111">In the left pane, select **Show All,** and then under **Admin centers**, select **Azure Active Directory**.</span></span>

3. <span data-ttu-id="7404d-112">Nel riquadro sinistro dell'interfaccia **di amministrazione di Azure Active Directory selezionare** Azure Active **Directory.**</span><span class="sxs-lookup"><span data-stu-id="7404d-112">In the left pane of the **Azure Active Directory admin center,** select **Azure Active Directory**.</span></span>

4. <span data-ttu-id="7404d-113">Nel menu a sinistra del  dashboard seleziona Proprietà nella sezione **Gestisci.**</span><span class="sxs-lookup"><span data-stu-id="7404d-113">From the left menu of the Dashboard, in the **Manage** section, select **Properties**.</span></span>

    :::image type="content" source="../media/m365-campaigns-conditional-access/azure-ad-properties.png" alt-text="Screenshot dell'interfaccia di amministrazione di Azure Active Directory che mostra il percorso della voce di menu Proprietà.":::

5. <span data-ttu-id="7404d-115">Nella parte inferiore della **pagina Proprietà** selezionare Gestisci impostazioni **predefinite sicurezza.**</span><span class="sxs-lookup"><span data-stu-id="7404d-115">At the bottom of the **Properties** page, select **Manage Security defaults**.</span></span>

6. <span data-ttu-id="7404d-116">Nel riquadro destro verrà visualizzata l'impostazione Abilita impostazioni **predefinite di** sicurezza.</span><span class="sxs-lookup"><span data-stu-id="7404d-116">In the right pane, you'll see the **Enable Security defaults** setting.</span></span> <span data-ttu-id="7404d-117">Se **si seleziona** Sì, le impostazioni predefinite di sicurezza sono già abilitate e non sono necessarie ulteriori azioni.</span><span class="sxs-lookup"><span data-stu-id="7404d-117">If **Yes** is selected, then security defaults are already enabled and no further action is required.</span></span> <span data-ttu-id="7404d-118">Se le impostazioni predefinite di sicurezza non sono attualmente abilitate, selezionare **Sì** per abilitarle e quindi selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="7404d-118">If security defaults are not currently enabled, then select **Yes** to enable them, and then select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="7404d-119">Se si usano criteri di accesso condizionale, è necessario disattivarli prima di utilizzare le impostazioni predefinite di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="7404d-119">If you've been using Conditional Access policies, you'll need to turn them off before using security defaults.</span></span>
>
> <span data-ttu-id="7404d-120">È possibile utilizzare impostazioni predefinite di sicurezza o criteri di accesso condizionale, ma non è possibile utilizzare entrambe le impostazioni contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="7404d-120">You can use either security defaults or Conditional Access policies, but you can't use both at the same time.</span></span>

## <a name="consider-using-conditional-access"></a><span data-ttu-id="7404d-121">Prendere in considerazione l'uso dell'accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="7404d-121">Consider using Conditional Access</span></span>

<span data-ttu-id="7404d-122">Se l'organizzazione ha requisiti di sicurezza complessi o se è necessario un controllo più granulare sui criteri di sicurezza, è consigliabile utilizzare l'accesso condizionale anziché le impostazioni predefinite di sicurezza per ottenere una posizione di sicurezza simile o superiore.</span><span class="sxs-lookup"><span data-stu-id="7404d-122">If your organization has complex security requirements or you need more granular control over your security policies, then you should consider using Conditional Access instead of security defaults to achieve a similar or higher security posture.</span></span> 

<span data-ttu-id="7404d-123">L'accesso condizionale consente di creare e definire criteri che reagiscono agli eventi di accesso e richiedono azioni aggiuntive prima che a un utente venga concesso l'accesso a un'applicazione o a un servizio.</span><span class="sxs-lookup"><span data-stu-id="7404d-123">Conditional Access lets you create and define policies that react to sign-in events and request additional actions before a user is granted access to an application or service.</span></span> <span data-ttu-id="7404d-124">I criteri di accesso condizionale possono essere granulari e specifici, per consentire agli utenti di essere produttivi ovunque e in qualsiasi momento, ma anche di proteggere l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7404d-124">Conditional Access policies can be granular and specific, empowering users to be productive wherever and whenever, but also protecting your organization.</span></span>

<span data-ttu-id="7404d-125">Le impostazioni predefinite di sicurezza sono disponibili per tutti i clienti, mentre l'accesso condizionale richiede una licenza per uno dei piani seguenti:</span><span class="sxs-lookup"><span data-stu-id="7404d-125">Security defaults are available to all customers, while Conditional Access requires a license for one of the following plans:</span></span>

- <span data-ttu-id="7404d-126">Azure Active Directory Premium P1 o P2</span><span class="sxs-lookup"><span data-stu-id="7404d-126">Azure Active Directory Premium P1 or P2</span></span>
- <span data-ttu-id="7404d-127">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="7404d-127">Microsoft 365 Business Premium</span></span>
- <span data-ttu-id="7404d-128">Microsoft 365 E3 o E5</span><span class="sxs-lookup"><span data-stu-id="7404d-128">Microsoft 365 E3 or E5</span></span>
- <span data-ttu-id="7404d-129">Enterprise Mobility & Security E3 o E5</span><span class="sxs-lookup"><span data-stu-id="7404d-129">Enterprise Mobility & Security E3 or E5</span></span>

<span data-ttu-id="7404d-130">Se si desidera utilizzare l'accesso condizionale per configurare criteri equivalenti a quelli abilitati per le impostazioni predefinite di sicurezza, vedere le guide dettagliate seguenti:</span><span class="sxs-lookup"><span data-stu-id="7404d-130">If you want to use Conditional Access to configure policies equivalent to those enabled by security defaults, check out the following step-by-step guides:</span></span>

- [<span data-ttu-id="7404d-131">Richiedere la MFA per amministratori</span><span class="sxs-lookup"><span data-stu-id="7404d-131">Require MFA for administrators</span></span>](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)
- [<span data-ttu-id="7404d-132">Richiedi MFA per la gestione di Azure</span><span class="sxs-lookup"><span data-stu-id="7404d-132">Require MFA for Azure management</span></span>](/azure/active-directory/conditional-access/howto-conditional-access-policy-azure-management)
- [<span data-ttu-id="7404d-133">Bloccare l'autenticazione legacy</span><span class="sxs-lookup"><span data-stu-id="7404d-133">Block legacy authentication</span></span>](/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)
- [<span data-ttu-id="7404d-134">Richiedere la MFA per tutti gli utenti</span><span class="sxs-lookup"><span data-stu-id="7404d-134">Require MFA for all users</span></span>](/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)
- <span data-ttu-id="7404d-135">[Richiedi registrazione MFA di Azure AD](/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy) - Richiede Azure AD Identity Protection, che fa parte di Azure Active Directory Premium P2</span><span class="sxs-lookup"><span data-stu-id="7404d-135">[Require Azure AD MFA registration](/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy) - Requires Azure AD Identity Protection, which is part of Azure Active Directory Premium P2</span></span>

<span data-ttu-id="7404d-136">Per ulteriori informazioni sull'accesso condizionale, vedere [Che cos'è l'accesso condizionale?](/azure/active-directory/conditional-access/overview)</span><span class="sxs-lookup"><span data-stu-id="7404d-136">To learn more about Conditional Access, see [What is Conditional Access?](/azure/active-directory/conditional-access/overview)</span></span> <span data-ttu-id="7404d-137">Per ulteriori informazioni sulla creazione di criteri di accesso condizionale, vedere [Create a Conditional Access policy](/azure/active-directory/authentication/tutorial-enable-azure-mfa#create-a-conditional-access-policy).</span><span class="sxs-lookup"><span data-stu-id="7404d-137">For more information about creating Conditional Access policies, see [Create a Conditional Access policy](/azure/active-directory/authentication/tutorial-enable-azure-mfa#create-a-conditional-access-policy).</span></span>

> [!NOTE]
> <span data-ttu-id="7404d-138">Se si dispone di un piano o di una licenza che fornisce l'accesso condizionale ma non sono stati ancora creati criteri di accesso condizionale, è possibile utilizzare le impostazioni predefinite di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="7404d-138">If you have a plan or license that provides Conditional Access but haven't yet created any Conditional Access policies, you're welcome to use security defaults.</span></span> <span data-ttu-id="7404d-139">Tuttavia, è necessario disattivare le impostazioni predefinite di sicurezza prima di poter utilizzare i criteri di accesso condizionale.</span><span class="sxs-lookup"><span data-stu-id="7404d-139">However, you'll need to turn off security defaults before you can use Conditional Access policies.</span></span>
