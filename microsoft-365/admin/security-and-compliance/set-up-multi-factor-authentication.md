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
localization_priority: Normal
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
description: Informazioni su come configurare l'autenticazione a più fattori per l'organizzazione.
monikerRange: o365-worldwide
ms.openlocfilehash: a8e84746a577b95307d325047f0822e8eb3786f0
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2020
ms.locfileid: "44779942"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="2ae6e-103">Configurare l'autenticazione a più fattori</span><span class="sxs-lookup"><span data-stu-id="2ae6e-103">Set up multi-factor authentication</span></span>
  
<span data-ttu-id="2ae6e-104">In base alla comprensione dell' [autenticazione a più fattori e del relativo supporto in Microsoft 365](multi-factor-authentication-microsoft-365.md), è necessario configurarlo e distribuirlo all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="2ae6e-104">Based on your understanding of [multi-factor authentication (MFA) and its support in Microsoft 365](multi-factor-authentication-microsoft-365.md), it’s time to set it up and roll it out to your organization.</span></span>

<span data-ttu-id="2ae6e-105">Prima di iniziare, determinare se queste condizioni speciali si applicano all'utente e intraprendere le azioni appropriate:</span><span class="sxs-lookup"><span data-stu-id="2ae6e-105">Before you begin, determine if these special conditions apply to you and take the appropriate action:</span></span>

- <span data-ttu-id="2ae6e-106">Se si dispone di client di Office 2013 nei dispositivi Windows, [abilitare l'autenticazione moderna](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication).</span><span class="sxs-lookup"><span data-stu-id="2ae6e-106">If you have Office 2013 clients on Windows devices, [enable Modern Authentication](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication).</span></span>

- <span data-ttu-id="2ae6e-107">Se si dispone di servizi directory di terze parti con Active Directory Federation Services (AD FS), configurare il server Azure Mae.</span><span class="sxs-lookup"><span data-stu-id="2ae6e-107">If you have third-party directory services with Active Directory Federation Services (AD FS), set up the Azure MFA Server.</span></span> <span data-ttu-id="2ae6e-108">Per ulteriori informazioni, vedere [scenari avanzati con autenticazione a più fattori di Azure e soluzioni VPN di terze parti](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) .</span><span class="sxs-lookup"><span data-stu-id="2ae6e-108">See [advanced scenarios with Azure Multi-Factor Authentication and third-party VPN solutions](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) for more information.</span></span>


<span data-ttu-id="2ae6e-109">Tutti gli altri utenti dovranno eseguire l'autenticazione aggiuntiva quando necessario.</span><span class="sxs-lookup"><span data-stu-id="2ae6e-109">All other users will be asked to perform additional authentication when needed.</span></span> <span data-ttu-id="2ae6e-110">Per ulteriori informazioni, visitare il [metodo e le impostazioni per la verifica a due fattori](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-manage-settings#turn-on-two-factor-verification-prompts-on-a-trusted-device).</span><span class="sxs-lookup"><span data-stu-id="2ae6e-110">For more information, please visit [Two-factor verification method and settings](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-manage-settings#turn-on-two-factor-verification-prompts-on-a-trusted-device).</span></span>

=======
## <a name="step-1-decide-on-the-method-of-requiring-your-users-to-use-mfa"></a><span data-ttu-id="2ae6e-111">Passaggio 1: decidere il metodo per richiedere agli utenti di utilizzare il Master</span><span class="sxs-lookup"><span data-stu-id="2ae6e-111">Step 1: Decide on the method of requiring your users to use MFA</span></span>

> [!NOTE]
> <span data-ttu-id="2ae6e-112">È necessario essere un amministratore globale per impostare o modificare l'AMF.</span><span class="sxs-lookup"><span data-stu-id="2ae6e-112">You must be a global admin to set up or modify MFA.</span></span> <span data-ttu-id="2ae6e-113">Esistono tre modi per richiedere agli utenti di utilizzare il servizio di autenticazione utente per gli accessi. Per i dettagli, vedere [supporto di AMF in Microsoft 365](multi-factor-authentication-microsoft-365.md) .</span><span class="sxs-lookup"><span data-stu-id="2ae6e-113">There are three ways to require your users to use MFA for sign-ins. See [MFA support in Microsoft 365](multi-factor-authentication-microsoft-365.md) for the details.</span></span>

- <span data-ttu-id="2ae6e-114">Impostazioni predefinite per la sicurezza (consigliata per le aziende di piccole dimensioni)</span><span class="sxs-lookup"><span data-stu-id="2ae6e-114">Security defaults (recommended for small businesses)</span></span>

  <span data-ttu-id="2ae6e-115">Se si è acquistato l'abbonamento o la versione di valutazione dopo il 21 ottobre 2019 e si è inaspettatamente richiesto l'AMF, le [impostazioni predefinite](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) per la sicurezza sono state abilitate automaticamente per l'abbonamento.</span><span class="sxs-lookup"><span data-stu-id="2ae6e-115">If you purchased your subscription or trial after October 21, 2019, and you're unexpectedly prompted for MFA, [security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) have been automatically enabled for your subscription.</span></span>
  
  <span data-ttu-id="2ae6e-116">Ogni nuova sottoscrizione Microsoft 365 avrà automaticamente le impostazioni predefinite per la sicurezza attivate.</span><span class="sxs-lookup"><span data-stu-id="2ae6e-116">Every new Microsoft 365 subscription will automatically have security defaults turned on.</span></span> <span data-ttu-id="2ae6e-117">Questo significa che ogni utente dovrà configurare il master e installare l'app Microsoft Authenticator sul proprio dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="2ae6e-117">This means that every user will have to set up MFA and install the Microsoft Authenticator app on their mobile device.</span></span>

  <span data-ttu-id="2ae6e-118">Tutti gli utenti devono utilizzare l'app Microsoft Authenticator come metodo di verifica aggiuntivo e l'autenticazione legacy è bloccata.</span><span class="sxs-lookup"><span data-stu-id="2ae6e-118">All users must use the Microsoft Authenticator app as their additional verification method and legacy authentication is blocked.</span></span> 

- <span data-ttu-id="2ae6e-119">Criteri di accesso condizionale (consigliato per le aziende)</span><span class="sxs-lookup"><span data-stu-id="2ae6e-119">Conditional Access policies (recommended for enterprises)</span></span>

  <span data-ttu-id="2ae6e-120">Gli utenti scelgono il metodo di verifica aggiuntivo durante la registrazione dell'AMF.</span><span class="sxs-lookup"><span data-stu-id="2ae6e-120">Users choose the additional verification method during MFA registration.</span></span>

- <span data-ttu-id="2ae6e-121">Account per utente (non consigliato)</span><span class="sxs-lookup"><span data-stu-id="2ae6e-121">Per-user account (not recommended)</span></span>

  <span data-ttu-id="2ae6e-122">Gli utenti scelgono il metodo di verifica aggiuntivo durante la registrazione dell'AMF.</span><span class="sxs-lookup"><span data-stu-id="2ae6e-122">Users choose the additional verification method during MFA registration.</span></span>

## <a name="step-2-test-mfa-on-your-pilot-users"></a><span data-ttu-id="2ae6e-123">Passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="2ae6e-123">Step 2.</span></span> <span data-ttu-id="2ae6e-124">Test dell'AMF per gli utenti pilota</span><span class="sxs-lookup"><span data-stu-id="2ae6e-124">Test MFA on your pilot users</span></span>

<span data-ttu-id="2ae6e-125">Se si utilizzano criteri di accesso condizionale o AMF per utente (scelta non consigliata), selezionare gli utenti pilota nell'azienda o nell'organizzazione per testare la registrazione e gli accessi dell'AMF. Per esempio:</span><span class="sxs-lookup"><span data-stu-id="2ae6e-125">If you are using Conditional Access policies or per-user MFA (not recommended), select pilot users in your business or organization to test MFA registration and sign-ins. For example:</span></span>

- <span data-ttu-id="2ae6e-126">Per i criteri di accesso condizionale, creare un gruppo di utenti pilota e un criterio che richiede l'AMF per i membri del gruppo e per tutte le app.</span><span class="sxs-lookup"><span data-stu-id="2ae6e-126">For Conditional Access policies, create a pilot users group and a policy that requires MFA for the members of the group and for all apps.</span></span> <span data-ttu-id="2ae6e-127">Aggiungere quindi gli account dell'utente pilota al gruppo.</span><span class="sxs-lookup"><span data-stu-id="2ae6e-127">Then, add your pilot user’s accounts to the group.</span></span>

- <span data-ttu-id="2ae6e-128">Per l'autenticazione a livello di utente, abilitare l'AMF per gli account utente degli utenti pilota una volta.</span><span class="sxs-lookup"><span data-stu-id="2ae6e-128">For per-user MFA, enable MFA for the user accounts of your pilot users one a time.</span></span>

<span data-ttu-id="2ae6e-129">Collaborare con gli utenti pilota per risolvere i problemi e le domande da preparare per una distribuzione uniforme all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="2ae6e-129">Work with your pilot users to address questions and issues to prepare for a smooth roll out to your organization.</span></span>

## <a name="step-3-inform-your-organization-that-mfa-is-coming"></a><span data-ttu-id="2ae6e-130">Passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="2ae6e-130">Step 3.</span></span> <span data-ttu-id="2ae6e-131">Informare l'organizzazione dell'arrivo dell'AMF</span><span class="sxs-lookup"><span data-stu-id="2ae6e-131">Inform your organization that MFA is coming</span></span>

<span data-ttu-id="2ae6e-132">Utilizzare le notifiche di posta elettronica, i poster dei corridoi, le riunioni del team o la formazione formale per garantire che i dipendenti comprendano:</span><span class="sxs-lookup"><span data-stu-id="2ae6e-132">Use email notifications, hallway posters, team meetings, or formal training to ensure that your employees understand:</span></span>

- <span data-ttu-id="2ae6e-133">Perché è necessario disporre dell'AMF per gli accessi</span><span class="sxs-lookup"><span data-stu-id="2ae6e-133">Why MFA is being required for sign-ins</span></span>
- [<span data-ttu-id="2ae6e-134">Come effettuare la registrazione per il metodo di verifica aggiuntivo</span><span class="sxs-lookup"><span data-stu-id="2ae6e-134">How to register for their additional verification method</span></span>](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)
- [<span data-ttu-id="2ae6e-135">Come effettuare l'accesso dopo la registrazione</span><span class="sxs-lookup"><span data-stu-id="2ae6e-135">How to sign-in after registration</span></span>](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)
- [<span data-ttu-id="2ae6e-136">Come modificare il metodo di verifica aggiuntivo</span><span class="sxs-lookup"><span data-stu-id="2ae6e-136">How to change their additional verification method</span></span>](https://support.microsoft.com/office/956ec8d0-7081-4518-a701-f8414cc20831)
- [<span data-ttu-id="2ae6e-137">Come gestire situazioni come un nuovo smartphone</span><span class="sxs-lookup"><span data-stu-id="2ae6e-137">How to deal with situations like a new smart phone</span></span>](https://support.microsoft.com/office/6951be76-af50-49a4-847f-21391eaa59f2)

<span data-ttu-id="2ae6e-138">Soprattutto, assicurarsi che i dipendenti comprendano ***quando il requisito dell'AMF verrà imposto in*** modo che non li sorprenda.</span><span class="sxs-lookup"><span data-stu-id="2ae6e-138">Most importantly, make sure your employees understand ***when the MFA requirement is going to be imposed*** so that it does not surprise them.</span></span>

## <a name="step-4-roll-out-the-mfa-requirement-to-your-organization-or-users"></a><span data-ttu-id="2ae6e-139">Passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="2ae6e-139">Step 4.</span></span> <span data-ttu-id="2ae6e-140">Implementazione del requisito AMF per l'organizzazione o gli utenti</span><span class="sxs-lookup"><span data-stu-id="2ae6e-140">Roll out the MFA requirement to your organization or users</span></span>

<span data-ttu-id="2ae6e-141">In base al metodo di requisiti di AMF prescelto, distribuire l'autenticazione dell'AMF ai dipendenti oltre i tester pilota.</span><span class="sxs-lookup"><span data-stu-id="2ae6e-141">Based on your chosen MFA requirement method, roll out MFA authentication to the employees beyond your pilot testers.</span></span>

### <a name="security-defaults"></a><span data-ttu-id="2ae6e-142">Impostazioni predefinite per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="2ae6e-142">Security defaults</span></span>

<span data-ttu-id="2ae6e-143">È possibile abilitare o disabilitare le impostazioni predefinite di sicurezza dal riquadro delle **Proprietà** di Azure Active Directory (Azure ad) nel portale di Azure.</span><span class="sxs-lookup"><span data-stu-id="2ae6e-143">You enable or disable security defaults from the **Properties** pane for Azure Active Directory (Azure AD) in the Azure portal.</span></span>

1.  <span data-ttu-id="2ae6e-144">Accedere all'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com) con le credenziali di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="2ae6e-144">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with global admin credentials.</span></span>
2.  <span data-ttu-id="2ae6e-145">Passare alla [pagina Azure Active Directory-Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="2ae6e-145">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
3.  <span data-ttu-id="2ae6e-146">Nella parte inferiore della pagina scegliere **Gestire le impostazioni predefinite per la sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="2ae6e-146">At the bottom of the page, choose **Manage Security defaults**.</span></span>
4.  <span data-ttu-id="2ae6e-147">Scegliere **Sì** per abilitare le impostazioni predefinite per la sicurezza e **No** per disabilitare le impostazioni predefinite per la sicurezza e quindi scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="2ae6e-147">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

<span data-ttu-id="2ae6e-148">Se sono stati utilizzati i [criteri di accesso condizionale di base](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection), ecco come passare a utilizzo delle impostazioni predefinite di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="2ae6e-148">If you have been using [baseline Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection), here is how you move to using security defaults.</span></span>

1.  <span data-ttu-id="2ae6e-149">Passare alla [pagina Criteri di accesso condizionale](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span><span class="sxs-lookup"><span data-stu-id="2ae6e-149">Go to the [Conditional Access - Policies page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span></span>
2.  <span data-ttu-id="2ae6e-150">Scegliere tutti i criteri di base che **sono attivi** e impostare **Attiva criterio** su **disattivato**.</span><span class="sxs-lookup"><span data-stu-id="2ae6e-150">Choose each baseline policy that is **On** and set **Enable policy** to **Off**.</span></span>
2.  <span data-ttu-id="2ae6e-151">Passare alla [pagina Azure Active Directory-Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="2ae6e-151">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
4.  <span data-ttu-id="2ae6e-152">Nella parte inferiore della pagina scegliere **Gestire le impostazioni predefinite per la sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="2ae6e-152">At the bottom of the page, choose **Manage Security defaults**.</span></span>
5.  <span data-ttu-id="2ae6e-153">Scegliere **Sì** per abilitare le impostazioni predefinite per la sicurezza e **No** per disabilitare le impostazioni predefinite per la sicurezza e quindi scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="2ae6e-153">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

### <a name="conditional-access-policies"></a><span data-ttu-id="2ae6e-154">Criteri di accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="2ae6e-154">Conditional Access policies</span></span>

<span data-ttu-id="2ae6e-155">Creare, configurare e abilitare i criteri corretti che includono il gruppo di utenti che richiedono l'autenticazione a più fattori per l'accesso.</span><span class="sxs-lookup"><span data-stu-id="2ae6e-155">Create, configure, and enable the appropriate policies that include the group of users that require MFA for sign-in.</span></span>

### <a name="per-user-mfa-not-recommended"></a><span data-ttu-id="2ae6e-156">AMF per utente (non consigliata)</span><span class="sxs-lookup"><span data-stu-id="2ae6e-156">Per-user MFA (not recommended)</span></span>

<span data-ttu-id="2ae6e-157">Abilitare gli account utente per l'AMF corrispondente all'implementazione.</span><span class="sxs-lookup"><span data-stu-id="2ae6e-157">Enable user accounts for MFA corresponding to your rollout.</span></span>

### <a name="supporting-your-employees"></a><span data-ttu-id="2ae6e-158">Supporto dei dipendenti</span><span class="sxs-lookup"><span data-stu-id="2ae6e-158">Supporting your employees</span></span>

<span data-ttu-id="2ae6e-159">Quando i dipendenti si iscrivono e iniziano a eseguire l'accesso con l'AMF, assicurarsi che gli specialisti IT, il reparto IT o il supporto tecnico possano rispondere rapidamente a domande e risolvere i problemi.</span><span class="sxs-lookup"><span data-stu-id="2ae6e-159">As your employees register and begin signing in with MFA, ensure that your IT specialists, IT department, or helpdesk can answer questions and address issues quickly.</span></span>

<span data-ttu-id="2ae6e-160">Vedere questo articolo per [informazioni sulla risoluzione dei problemi relativi agli accessi dell'AMF](https://support.microsoft.com/office/6951be76-af50-49a4-847f-21391eaa59f2).</span><span class="sxs-lookup"><span data-stu-id="2ae6e-160">See this article for [information about troubleshooting MFA sign-ins](https://support.microsoft.com/office/6951be76-af50-49a4-847f-21391eaa59f2).</span></span> 


