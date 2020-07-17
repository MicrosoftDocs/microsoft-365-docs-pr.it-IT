---
title: Configurare l'autenticazione a più fattori per gli utenti
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: mnirkhe
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
ms.openlocfilehash: 56ca51e77b2ba4fa370a2814a7be9df1393c29dc
ms.sourcegitcommit: 3951147f74510e2ead6c11ceab92854f0937426b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/08/2020
ms.locfileid: "45083539"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="51616-103">Configurare l'autenticazione a più fattori</span><span class="sxs-lookup"><span data-stu-id="51616-103">Set up multi-factor authentication</span></span>
  
<span data-ttu-id="51616-104">Basandosi sulla conoscenza dell'[autenticazione a più fattori (MFA) e del relativo supporto in Microsoft 365](multi-factor-authentication-microsoft-365.md), è ora di configurarla e implementarla nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="51616-104">Based on your understanding of [multi-factor authentication (MFA) and its support in Microsoft 365](multi-factor-authentication-microsoft-365.md), it’s time to set it up and roll it out to your organization.</span></span>

<span data-ttu-id="51616-105">Prima di iniziare, determinare se queste condizioni speciali sono valide per la propria situazione ed eseguire l'azione appropriata:</span><span class="sxs-lookup"><span data-stu-id="51616-105">Before you begin, determine if these special conditions apply to you and take the appropriate action:</span></span>

- <span data-ttu-id="51616-106">Se si hanno client di Office 2013 su dispositivi Windows, [abilitare Autenticazione moderna](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication).</span><span class="sxs-lookup"><span data-stu-id="51616-106">If you have Office 2013 clients on Windows devices, [enable Modern Authentication](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication).</span></span>

- <span data-ttu-id="51616-107">Se si hanno servizi directory di terze parti con Active Directory Federation Services (ADFS), configurare il server Azure MFA.</span><span class="sxs-lookup"><span data-stu-id="51616-107">If you have third-party directory services with Active Directory Federation Services (AD FS), set up the Azure MFA Server.</span></span> <span data-ttu-id="51616-108">Per altre informazioni, vedere [Scenari avanzati con server di autenticazione a più fattori di Azure e soluzioni VPN di terze parti](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn).</span><span class="sxs-lookup"><span data-stu-id="51616-108">See [advanced scenarios with Azure Multi-Factor Authentication and third-party VPN solutions](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) for more information.</span></span>

<span data-ttu-id="51616-109">Tutti gli altri utenti dovranno eseguire l'autenticazione aggiuntiva quando necessario.</span><span class="sxs-lookup"><span data-stu-id="51616-109">All other users will be asked to perform additional authentication when needed.</span></span> <span data-ttu-id="51616-110">Per altre informazioni, vedere [Metodo e impostazioni di verifica a due fattori](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-manage-settings#turn-on-two-factor-verification-prompts-on-a-trusted-device).</span><span class="sxs-lookup"><span data-stu-id="51616-110">For more information, please visit [Two-factor verification method and settings](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-manage-settings#turn-on-two-factor-verification-prompts-on-a-trusted-device).</span></span>

## <a name="step-1-decide-on-the-method-of-requiring-your-users-to-use-mfa"></a><span data-ttu-id="51616-111">Passaggio 1: scegliere il metodo per richiedere agli utenti di usare la MFA</span><span class="sxs-lookup"><span data-stu-id="51616-111">Step 1: Decide on the method of requiring your users to use MFA</span></span>

> [!NOTE]
> <span data-ttu-id="51616-112">Per eseguire questi passaggi, è necessario essere un amministratore globale o modificare MFA.</span><span class="sxs-lookup"><span data-stu-id="51616-112">You must be a global admin to set up or modify MFA.</span></span> <span data-ttu-id="51616-113">Sono disponibili tre modi per richiedere agli utenti di usare la MFA per gli accessi. Per informazioni dettagliate, vedere [Supporto all’autenticazione a più fattori in Microsoft 365](multi-factor-authentication-microsoft-365.md).</span><span class="sxs-lookup"><span data-stu-id="51616-113">There are three ways to require your users to use MFA for sign-ins. See [MFA support in Microsoft 365](multi-factor-authentication-microsoft-365.md) for the details.</span></span>

- <span data-ttu-id="51616-114">Impostazioni predefinite di sicurezza (consigliate per le piccole imprese)</span><span class="sxs-lookup"><span data-stu-id="51616-114">Security defaults (recommended for small businesses)</span></span>

  <span data-ttu-id="51616-115">Se è stato acquistato un abbonamento o una versione di valutazione dopo il 21 ottobre 2019 e in modo imprevisto viene richiesta la MFA, le [impostazioni predefinite di sicurezza](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) sono state abilitate automaticamente per l'abbonamento.</span><span class="sxs-lookup"><span data-stu-id="51616-115">If you purchased your subscription or trial after October 21, 2019, and you're unexpectedly prompted for MFA, [security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) have been automatically enabled for your subscription.</span></span>
  
  <span data-ttu-id="51616-116">Nei nuovi abbonamenti a Microsoft 365 le impostazioni predefinite per la sicurezza sono attivate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="51616-116">Every new Microsoft 365 subscription will automatically have security defaults turned on.</span></span> <span data-ttu-id="51616-117">Ciò significa che ogni utente dovrà configurare l'autenticazione a più fattori e installare l'app Microsoft Authenticator nel proprio dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="51616-117">This means that every user will have to set up MFA and install the Microsoft Authenticator app on their mobile device.</span></span>

  <span data-ttu-id="51616-118">Tutti gli utenti devono usare l'app Microsoft Authenticator come metodo di verifica aggiuntivo e l'autenticazione legacy è bloccata.</span><span class="sxs-lookup"><span data-stu-id="51616-118">All users must use the Microsoft Authenticator app as their additional verification method and legacy authentication is blocked.</span></span> 

- <span data-ttu-id="51616-119">Criteri di accesso condizionale (consigliati per le aziende)</span><span class="sxs-lookup"><span data-stu-id="51616-119">Conditional Access policies (recommended for enterprises)</span></span>

  <span data-ttu-id="51616-120">Gli utenti scelgono il metodo di verifica aggiuntivo durante la registrazione della MFA.</span><span class="sxs-lookup"><span data-stu-id="51616-120">Users choose the additional verification method during MFA registration.</span></span>

- <span data-ttu-id="51616-121">Account per utente (scelta non consigliata)</span><span class="sxs-lookup"><span data-stu-id="51616-121">Per-user account (not recommended)</span></span>

  <span data-ttu-id="51616-122">Gli utenti scelgono il metodo di verifica aggiuntivo durante la registrazione della MFA.</span><span class="sxs-lookup"><span data-stu-id="51616-122">Users choose the additional verification method during MFA registration.</span></span>

## <a name="step-2-test-mfa-on-your-pilot-users"></a><span data-ttu-id="51616-123">Passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="51616-123">Step 2.</span></span> <span data-ttu-id="51616-124">Testare la MFA con gli utenti del programma pilota</span><span class="sxs-lookup"><span data-stu-id="51616-124">Test MFA on your pilot users</span></span>

<span data-ttu-id="51616-125">Se si usano criteri di Accesso condizionale o MFA per utente (scelta non consigliata), selezionare gli utenti del programma pilota nell'azienda o nell'organizzazione per testare la registrazione e gli accessi della MFA. Per esempio:</span><span class="sxs-lookup"><span data-stu-id="51616-125">If you are using Conditional Access policies or per-user MFA (not recommended), select pilot users in your business or organization to test MFA registration and sign-ins. For example:</span></span>

- <span data-ttu-id="51616-126">Per i criteri di Accesso condizionale, creare un gruppo di utenti del programma pilota e un criterio che richieda la MFA per i membri del gruppo e per tutte le app.</span><span class="sxs-lookup"><span data-stu-id="51616-126">For Conditional Access policies, create a pilot users group and a policy that requires MFA for the members of the group and for all apps.</span></span> <span data-ttu-id="51616-127">Quindi, aggiungere gli account degli utenti del programma pilota al gruppo.</span><span class="sxs-lookup"><span data-stu-id="51616-127">Then, add your pilot user’s accounts to the group.</span></span>

- <span data-ttu-id="51616-128">Per la MFA per utente, abilitare la MFA per gli account degli utenti del programma pilota, uno alla volta.</span><span class="sxs-lookup"><span data-stu-id="51616-128">For per-user MFA, enable MFA for the user accounts of your pilot users one a time.</span></span>

<span data-ttu-id="51616-129">Collaborare con gli utenti del programma pilota per risolvere le domande e i problemi e predisporre una distribuzione fluida nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="51616-129">Work with your pilot users to address questions and issues to prepare for a smooth roll out to your organization.</span></span>

## <a name="step-3-inform-your-organization-that-mfa-is-coming"></a><span data-ttu-id="51616-130">Passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="51616-130">Step 3.</span></span> <span data-ttu-id="51616-131">Informare l'organizzazione della futura implementazione della MFA</span><span class="sxs-lookup"><span data-stu-id="51616-131">Inform your organization that MFA is coming</span></span>

<span data-ttu-id="51616-132">Usare le notifiche tramite posta elettronica, manifesti nei corridoi, riunioni del team o corsi di formazione per garantire che i dipendenti comprendano:</span><span class="sxs-lookup"><span data-stu-id="51616-132">Use email notifications, hallway posters, team meetings, or formal training to ensure that your employees understand:</span></span>

- <span data-ttu-id="51616-133">Perché è necessaria la MFA per gli accessi</span><span class="sxs-lookup"><span data-stu-id="51616-133">Why MFA is being required for sign-ins</span></span>
- [<span data-ttu-id="51616-134">Come registrarsi per il metodo di verifica aggiuntivo</span><span class="sxs-lookup"><span data-stu-id="51616-134">How to register for their additional verification method</span></span>](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)
- [<span data-ttu-id="51616-135">Come eseguire l'accesso dopo la registrazione</span><span class="sxs-lookup"><span data-stu-id="51616-135">How to sign-in after registration</span></span>](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)
- [<span data-ttu-id="51616-136">Come cambiare il metodo di verifica aggiuntivo</span><span class="sxs-lookup"><span data-stu-id="51616-136">How to change their additional verification method</span></span>](https://support.microsoft.com/office/956ec8d0-7081-4518-a701-f8414cc20831)
- [<span data-ttu-id="51616-137">Come gestire situazioni come un nuovo smartphone</span><span class="sxs-lookup"><span data-stu-id="51616-137">How to deal with situations like a new smart phone</span></span>](https://support.microsoft.com/office/6951be76-af50-49a4-847f-21391eaa59f2)

<span data-ttu-id="51616-138">Soprattutto, accertarsi che i dipendenti comprendano ***quando verrà imposto il requisito della MFA*** in modo da non coglierli di sorpresa.</span><span class="sxs-lookup"><span data-stu-id="51616-138">Most importantly, make sure your employees understand ***when the MFA requirement is going to be imposed*** so that it does not surprise them.</span></span>

## <a name="step-4-roll-out-the-mfa-requirement-to-your-organization-or-users"></a><span data-ttu-id="51616-139">Passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="51616-139">Step 4.</span></span> <span data-ttu-id="51616-140">Implementare il requisito della MFA nell'organizzazione o agli utenti</span><span class="sxs-lookup"><span data-stu-id="51616-140">Roll out the MFA requirement to your organization or users</span></span>

<span data-ttu-id="51616-141">In base al metodo del requisito della MFA scelto, distribuire l'autenticazione MFA ai dipendenti oltre che agli utenti del programma pilota.</span><span class="sxs-lookup"><span data-stu-id="51616-141">Based on your chosen MFA requirement method, roll out MFA authentication to the employees beyond your pilot testers.</span></span>

### <a name="security-defaults"></a><span data-ttu-id="51616-142">Impostazioni predefinite per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="51616-142">Security defaults</span></span>

<span data-ttu-id="51616-143">È possibile abilitare o disabilitare le impostazioni predefinite di sicurezza dal riquadro **Proprietà** di Azure Active Directory (Azure AD) nel portale di Azure.</span><span class="sxs-lookup"><span data-stu-id="51616-143">You enable or disable security defaults from the **Properties** pane for Azure Active Directory (Azure AD) in the Azure portal.</span></span>

1.  <span data-ttu-id="51616-144">Accedere al [portale di amministrazione di Microsoft 365](https://admin.microsoft.com) con le credenziali di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="51616-144">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with global admin credentials.</span></span>
2.  <span data-ttu-id="51616-145">Passare alla [pagina Proprietà di Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="51616-145">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
3.  <span data-ttu-id="51616-146">Nella parte inferiore della pagina scegliere **Gestire le impostazioni predefinite per la sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="51616-146">At the bottom of the page, choose **Manage Security defaults**.</span></span>
4.  <span data-ttu-id="51616-147">Scegliere **Sì** per abilitare le impostazioni predefinite di sicurezza e **No** per disabilitare le impostazioni predefinite per la sicurezza, quindi scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="51616-147">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

<span data-ttu-id="51616-148">Se sono stati usati [criteri di accesso condizionale di base](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection), ecco come passare all'uso delle impostazioni predefinite di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="51616-148">If you have been using [baseline Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection), here is how you move to using security defaults.</span></span>

1.  <span data-ttu-id="51616-149">Passare alla pagina [Accesso condizionale - Criteri](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span><span class="sxs-lookup"><span data-stu-id="51616-149">Go to the [Conditional Access - Policies page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span></span>
2.  <span data-ttu-id="51616-150">Scegliere ciascun criterio di base che è **Attivato** e impostare **Abilitare il criterio** su **Disattivato**.</span><span class="sxs-lookup"><span data-stu-id="51616-150">Choose each baseline policy that is **On** and set **Enable policy** to **Off**.</span></span>
2.  <span data-ttu-id="51616-151">Passare alla [pagina Proprietà di Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="51616-151">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
4.  <span data-ttu-id="51616-152">Nella parte inferiore della pagina scegliere **Gestire le impostazioni predefinite per la sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="51616-152">At the bottom of the page, choose **Manage Security defaults**.</span></span>
5.  <span data-ttu-id="51616-153">Scegliere **Sì** per abilitare le impostazioni predefinite di sicurezza e **No** per disabilitare le impostazioni predefinite per la sicurezza, quindi scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="51616-153">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

### <a name="conditional-access-policies"></a><span data-ttu-id="51616-154">Criteri di accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="51616-154">Conditional Access policies</span></span>

<span data-ttu-id="51616-155">Creare, configurare e abilitare i criteri appropriati che includono il gruppo di utenti che richiedono la MFA per l'accesso.</span><span class="sxs-lookup"><span data-stu-id="51616-155">Create, configure, and enable the appropriate policies that include the group of users that require MFA for sign-in.</span></span>

### <a name="per-user-mfa-not-recommended"></a><span data-ttu-id="51616-156">MFA per utente (scelta non consigliata)</span><span class="sxs-lookup"><span data-stu-id="51616-156">Per-user MFA (not recommended)</span></span>

<span data-ttu-id="51616-157">Abilitare gli account utente per la MFA in base all'implementazione.</span><span class="sxs-lookup"><span data-stu-id="51616-157">Enable user accounts for MFA corresponding to your rollout.</span></span>

### <a name="supporting-your-employees"></a><span data-ttu-id="51616-158">Supporto dei dipendenti</span><span class="sxs-lookup"><span data-stu-id="51616-158">Supporting your employees</span></span>

<span data-ttu-id="51616-159">Quando i dipendenti si registrano e iniziano a eseguire l'accesso con la MFA, assicurarsi che gli specialisti IT, il reparto IT o il supporto tecnico possano rispondere rapidamente alle domande e risolvere i problemi.</span><span class="sxs-lookup"><span data-stu-id="51616-159">As your employees register and begin signing in with MFA, ensure that your IT specialists, IT department, or helpdesk can answer questions and address issues quickly.</span></span>

<span data-ttu-id="51616-160">Vedere questo articolo per [informazioni sulla risoluzione dei problemi di accesso con la MFA](https://support.microsoft.com/office/6951be76-af50-49a4-847f-21391eaa59f2).</span><span class="sxs-lookup"><span data-stu-id="51616-160">See this article for [information about troubleshooting MFA sign-ins](https://support.microsoft.com/office/6951be76-af50-49a4-847f-21391eaa59f2).</span></span> 


