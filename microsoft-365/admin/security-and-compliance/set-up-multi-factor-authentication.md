---
title: Configurare l'autenticazione a più fattori per gli utenti
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 8f0454b2-f51a-4d9c-bcde-2c48e41621c6
description: Scopri come configurare l'autenticazione a più fattori per l'organizzazione.
monikerRange: o365-worldwide
ms.openlocfilehash: 54c862d8f7c25472d84557e177a9107d2c14d846
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914463"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="06662-103">Configurare l'autenticazione a più fattori</span><span class="sxs-lookup"><span data-stu-id="06662-103">Set up multi-factor authentication</span></span>

<span data-ttu-id="06662-104">Basandosi sulla conoscenza dell'[autenticazione a più fattori (MFA) e del relativo supporto in Microsoft 365](multi-factor-authentication-microsoft-365.md), è ora di configurarla e implementarla nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="06662-104">Based on your understanding of [multi-factor authentication (MFA) and its support in Microsoft 365](multi-factor-authentication-microsoft-365.md), it's time to set it up and roll it out to your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="06662-105">Se è stato acquistato un abbonamento o una versione di valutazione dopo il 21 ottobre 2019 e viene richiesto di eseguire l'autenticazione a più fattori quando si accede, le [impostazioni di sicurezza predefinite](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) sono state abilitate automaticamente per l'abbonamento.</span><span class="sxs-lookup"><span data-stu-id="06662-105">If you purchased your subscription or trial after October 21, 2019, and you're prompted for MFA when you sign in, [security defaults](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) have been automatically enabled for your subscription.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="06662-106">Informazioni preliminari</span><span class="sxs-lookup"><span data-stu-id="06662-106">Before you begin</span></span>

- <span data-ttu-id="06662-107">È necessario essere un ammistratore globale per gestire l-autenticazione MFA.</span><span class="sxs-lookup"><span data-stu-id="06662-107">You must be a Global admin to manage MFA.</span></span> <span data-ttu-id="06662-108">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="06662-108">For more information, see [About admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="06662-109">Se l'autenticazione a più fattori per utente è abilitata, è necessario [Disabilitare l'autenticazione a più fattori per utente ereditata](#turn-off-legacy-per-user-mfa).</span><span class="sxs-lookup"><span data-stu-id="06662-109">If you have legacy per-user MFA turned on, [Turn off legacy per-user MFA](#turn-off-legacy-per-user-mfa).</span></span>
- <span data-ttu-id="06662-110">Se si hanno client di Office 2013 su dispositivi Windows, [attivare Autenticazione moderna per i client Office 2013](./enable-modern-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="06662-110">If you have Office 2013 clients on Windows devices, [turn on Modern Authentication for Office 2013 clients](./enable-modern-authentication.md).</span></span>
- <span data-ttu-id="06662-111">Avanzato: se si hanno servizi directory di terze parti con Active Directory Federation Services (ADFS), configurare il server Azure MFA.</span><span class="sxs-lookup"><span data-stu-id="06662-111">Advanced: If you have third-party directory services with Active Directory Federation Services (AD FS), set up the Azure MFA Server.</span></span> <span data-ttu-id="06662-112">Per altre informazioni, vedere [Scenari avanzati con l’autenticazione a più fattori di Azure AD e soluzioni VPN di terze parti](/azure/active-directory/authentication/howto-mfaserver-nps-vpn).</span><span class="sxs-lookup"><span data-stu-id="06662-112">See [advanced scenarios with Azure AD Multi-Factor Authentication and third-party VPN solutions](/azure/active-directory/authentication/howto-mfaserver-nps-vpn) for more information.</span></span>

## <a name="turn-security-defaults-on-or-off"></a><span data-ttu-id="06662-113">Attivare o disattivare le impostazioni di sicurezza predefinite</span><span class="sxs-lookup"><span data-stu-id="06662-113">Turn Security defaults on or off</span></span>

<span data-ttu-id="06662-114">Per gran parte delle organizzazioni, le impostazioni di sicurezza predefinite offrono un buon livello di sicurezza aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="06662-114">For most organizations, Security defaults offer a good level of additional sign-in security.</span></span> <span data-ttu-id="06662-115">Per altre informazioni, vedere [Che cosa sono le impostazioni predefinite per la sicurezza?](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span><span class="sxs-lookup"><span data-stu-id="06662-115">For more information, see [What are security defaults?](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span></span>

<span data-ttu-id="06662-116">Se l'abbonamento è nuovo, l'impostazione predefinita della sicurezza potrebbe essere già attivata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="06662-116">If your subscription is new, Security defaults might already be turned on for you automatically.</span></span>

<span data-ttu-id="06662-117">È possibile abilitare o disabilitare le impostazioni predefinite di sicurezza dal riquadro **Proprietà** di Azure Active Directory (Azure AD) nel portale di Azure.</span><span class="sxs-lookup"><span data-stu-id="06662-117">You enable or disable security defaults from the **Properties** pane for Azure Active Directory (Azure AD) in the Azure portal.</span></span>

1. <span data-ttu-id="06662-118">Accedere al [portale di amministrazione di Microsoft 365](https://admin.microsoft.com) con le credenziali di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="06662-118">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with global admin credentials.</span></span>
2. <span data-ttu-id="06662-119">Nel riquadro di spostamento sinistro scegliere **Mostra tutto**, e in **Interfacce di amministrazione** scegliere **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="06662-119">In the left nav choose **Show All** and under **Admin centers**, choose **Azure Active Directory**.</span></span>
3. <span data-ttu-id="06662-120">Nell’**Interfaccia di amministrazione di Azure Active Directory** scegliere **Azure Active Directory** \> **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="06662-120">In the **Azure Active Directory admin center** choose **Azure Active Directory** \> **Properties**.</span></span>
4. <span data-ttu-id="06662-121">Nella parte inferiore della pagina scegliere **Gestire le impostazioni di sicurezza predefinite**.</span><span class="sxs-lookup"><span data-stu-id="06662-121">At the bottom of the page, choose **Manage Security defaults**.</span></span>
5. <span data-ttu-id="06662-122">Scegliere **Sì** per abilitare le impostazioni di sicurezza predefinite o **No** per disabilitare le impostazioni predefinite per la sicurezza, quindi scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="06662-122">Choose **Yes** to enable security defaults or **No** to disable security defaults, and then choose **Save**.</span></span>

<span data-ttu-id="06662-123">Se i [criteri di accesso condizionale di base](/azure/active-directory/conditional-access/concept-baseline-protection) sono stati usati, sarà richiesto di disattivarli prima di iniziare a usare le impostazioni di sicurezza predefinite.</span><span class="sxs-lookup"><span data-stu-id="06662-123">If you have been using [baseline Conditional Access policies](/azure/active-directory/conditional-access/concept-baseline-protection), you will be prompted to turn them off before you move to using security defaults.</span></span>

1. <span data-ttu-id="06662-124">Passare alla pagina [Accesso condizionale - Criteri](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span><span class="sxs-lookup"><span data-stu-id="06662-124">Go to the [Conditional Access - Policies page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span></span>
2. <span data-ttu-id="06662-125">Scegliere ciascun criterio di base che è **Attivato** e impostare **Abilitare il criterio** su **Disattivato**.</span><span class="sxs-lookup"><span data-stu-id="06662-125">Choose each baseline policy that is **On** and set **Enable policy** to **Off**.</span></span>
3. <span data-ttu-id="06662-126">Passare alla [pagina Proprietà di Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="06662-126">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
4. <span data-ttu-id="06662-127">Nella parte inferiore della pagina scegliere **Gestire le impostazioni predefinite per la sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="06662-127">At the bottom of the page, choose **Manage Security defaults**.</span></span>
5. <span data-ttu-id="06662-128">Scegliere **Sì** per abilitare le impostazioni predefinite di sicurezza e **No** per disabilitare le impostazioni predefinite per la sicurezza, quindi scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="06662-128">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

## <a name="use-conditional-access-policies"></a><span data-ttu-id="06662-129">È possibile utilizzare i criteri di accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="06662-129">Use Conditional Access policies</span></span>

<span data-ttu-id="06662-130">Se l'organizzazione ha esigenze di sicurezza di accesso più granulare, i criteri di accesso condizionale possono offrire un maggiore controllo.</span><span class="sxs-lookup"><span data-stu-id="06662-130">If your organization has more granular sign-in security needs, Conditional Access policies can offer you more control.</span></span> <span data-ttu-id="06662-131">L'accesso condizionale consente di creare e definire criteri che reagiscono agli eventi di autenticazione e richiedono altre azioni prima che un utente sia autorizzato ad accedere a un'applicazione o un servizio.</span><span class="sxs-lookup"><span data-stu-id="06662-131">Conditional Access lets you create and define policies that react to sign in events and request additional actions before a user is granted access to an application or service.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="06662-132">Disabilitare sia l’autenticazione a più fattori per utente che le impostazioni di sicurezza prima di abilitare i criteri di accesso condizionale.</span><span class="sxs-lookup"><span data-stu-id="06662-132">Turn off both per-user MFA and Security defaults before you enable Conditional Access policies.</span></span>

<span data-ttu-id="06662-133">L'accesso condizionale è disponibile per i clienti che hanno acquistato Azure AD Premium P1 o licenze che lo includono, come Microsoft 365 Business Premium e Microsoft 365 E3.</span><span class="sxs-lookup"><span data-stu-id="06662-133">Conditional Access is available for customers who have purchased Azure AD Premium P1, or licenses that include this, such as Microsoft 365 Business Premium, and Microsoft 365 E3.</span></span> <span data-ttu-id="06662-134">Per altre informazioni, vedere [Creare un criterio di accesso condizionale](/azure/active-directory/authentication/tutorial-enable-azure-mfa).</span><span class="sxs-lookup"><span data-stu-id="06662-134">For more information, see [create a Conditional Access policy](/azure/active-directory/authentication/tutorial-enable-azure-mfa).</span></span>

<span data-ttu-id="06662-135">L'accesso condizionale basato sul rischio è disponibile con la licenza P2 di Azure AD Premium P2 o con licenze che lo includono, come Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="06662-135">Risk-based conditional access is available through Azure AD Premium P2 license, or licenses that include this, such as Microsoft 365 E5.</span></span> <span data-ttu-id="06662-136">Per altre informazioni, vedere [Accesso condizionale basato sul rischio](/azure/active-directory/conditional-access/howto-conditional-access-policy-risk).</span><span class="sxs-lookup"><span data-stu-id="06662-136">For more information, see [risk-based Conditional Access](/azure/active-directory/conditional-access/howto-conditional-access-policy-risk).</span></span>

<span data-ttu-id="06662-137">Per altre informazioni su Azure AD P1 e P2, vedere [Prezzi di Azure Active Directory](https://azure.microsoft.com/pricing/details/active-directory/).</span><span class="sxs-lookup"><span data-stu-id="06662-137">For more information about the Azure AD P1 and P2, see [Azure Active Directory pricing](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>

### <a name="turn-on-modern-authentication-for-your-organization"></a><span data-ttu-id="06662-138">Attivare l'autenticazione moderna per la propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="06662-138">Turn on Modern authentication for your organization</span></span>

<span data-ttu-id="06662-139">Per la maggior parte degli abbonamenti l'autenticazione moderna è automaticamente attivata, ma se l'abbonamento è stato acquistato prima di agosto 2017, è probabile che sia necessario attivare l'autenticazione moderna per usare caratteristiche come l'autenticazione a più fattori in client Windows come Outlook.</span><span class="sxs-lookup"><span data-stu-id="06662-139">For most subscriptions modern authentication is automatically turned on, but if you purchased your subscription before August 2017, it is likely that you will need to turn on Modern Authentication in order to get features like Multi-Factor Authentication to work in Windows clients like Outlook.</span></span>


1. <span data-ttu-id="06662-140">Nell'interfaccia di amministrazione di Microsoft 365, nel riquadro di spostamento sinistro, scegliere **Impostazioni** \> **Impostazioni organizzazione**.</span><span class="sxs-lookup"><span data-stu-id="06662-140">In the Microsoft 365 admin center, in the left nav choose **Settings** \> **Org settings**.</span></span>
2. <span data-ttu-id="06662-141">Nella scheda **Servizi**, scegliere **Autenticazione moderna**, e nel riquadro **Autenticazione moderna**, verificare che **Abilita autenticazione moderna** sia selezionato.</span><span class="sxs-lookup"><span data-stu-id="06662-141">Under the **Services** tab, choose **Modern authentication**, and in the **Modern authentication** pane, make sure **Enable Modern authentication** is selected.</span></span> <span data-ttu-id="06662-142">Selezionare **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="06662-142">Choose **Save changes**.</span></span>

### <a name="turn-off-legacy-per-user-mfa"></a><span data-ttu-id="06662-143">Disabilitare l'autenticazione a più fattori per utente ereditata</span><span class="sxs-lookup"><span data-stu-id="06662-143">Turn off legacy per-user MFA</span></span>

<span data-ttu-id="06662-144">Se l'autenticazione a più fattori per utente è stata attivata in precedenza, è necessario disattivarla prima di abilitare le impostazioni di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="06662-144">If you have previously turned on per-user MFA, you must turn it off before enabling Security defaults.</span></span>

1. <span data-ttu-id="06662-145">Nell'interfaccia di amministrazione di Microsoft 365, nel riquadro di spostamento sinistro, scegliere **Utenti** \> **Utenti attivi**.</span><span class="sxs-lookup"><span data-stu-id="06662-145">In the Microsoft 365 admin center, in the left nav choose **Users** \> **Active users**.</span></span>
1. <span data-ttu-id="06662-146">Nella pagina **Utenti attivi**, scegliere **Autenticazione a più fattori**.</span><span class="sxs-lookup"><span data-stu-id="06662-146">On the **Active users** page, choose **Multi-factor authentication**.</span></span>
1. <span data-ttu-id="06662-147">Nella pagina Autenticazione a più fattori, selezionare ogni utente e impostare il loro stato Autenticazione a più fattori su **Disabilitato**.</span><span class="sxs-lookup"><span data-stu-id="06662-147">On the multi-factor authentication page, select each user and set their Multi-Factor auth status to **Disabled**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="06662-148">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="06662-148">Next steps</span></span>

- [<span data-ttu-id="06662-149">Come registrarsi per il metodo di verifica aggiuntivo</span><span class="sxs-lookup"><span data-stu-id="06662-149">How to register for their additional verification method</span></span>](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)
- [<span data-ttu-id="06662-150">Cos’è l'autenticazione a più fattori</span><span class="sxs-lookup"><span data-stu-id="06662-150">What is: Multifactor Authentication</span></span>](https://support.microsoft.com/help/4577374/what-is-multifactor-authentication)
- [<span data-ttu-id="06662-151">Come eseguire l'accesso dopo la registrazione</span><span class="sxs-lookup"><span data-stu-id="06662-151">How to sign-in after registration</span></span>](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)
- [<span data-ttu-id="06662-152">Come cambiare il metodo di verifica aggiuntivo</span><span class="sxs-lookup"><span data-stu-id="06662-152">How to change their additional verification method</span></span>](https://support.microsoft.com/office/956ec8d0-7081-4518-a701-f8414cc20831)

## <a name="related-topics"></a><span data-ttu-id="06662-153">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="06662-153">Related topics</span></span>

[<span data-ttu-id="06662-154">Video: Attivare l'autenticazione a più fattori</span><span class="sxs-lookup"><span data-stu-id="06662-154">Video: Turn on multi-factor authentication</span></span>](../../business-video/turn-on-mfa.md)

[<span data-ttu-id="06662-155">Video: Attivare l'autenticazione a più fattori per il telefono</span><span class="sxs-lookup"><span data-stu-id="06662-155">Video: Turn on multi-factor authentication for your phone</span></span>](../../business-video/set-up-mfa.md)