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
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 8f0454b2-f51a-4d9c-bcde-2c48e41621c6
description: Informazioni su come configurare l'autenticazione a più fattori per l'organizzazione.
monikerRange: o365-worldwide
ms.openlocfilehash: ca1a8bd47e2fa5bbd7b7aed396debefaad10ea5e
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/23/2020
ms.locfileid: "44351716"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="f96c2-103">Configurare l'autenticazione a più fattori</span><span class="sxs-lookup"><span data-stu-id="f96c2-103">Set up multi-factor authentication</span></span>
  
<span data-ttu-id="f96c2-104">In base alla comprensione dell' [autenticazione a più fattori e del relativo supporto in Microsoft 365](multi-factor-authentication-microsoft-365.md), è necessario configurarlo e distribuirlo all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f96c2-104">Based on your understanding of [multi-factor authentication (MFA) and its support in Microsoft 365](multi-factor-authentication-microsoft-365.md), it’s time to set it up and roll it out to your organization.</span></span>

<span data-ttu-id="f96c2-105">Prima di iniziare, determinare se queste condizioni speciali si applicano all'utente e intraprendere le azioni appropriate:</span><span class="sxs-lookup"><span data-stu-id="f96c2-105">Before you begin, determine if these special conditions apply to you and take the appropriate action:</span></span>

- <span data-ttu-id="f96c2-106">Se si dispone di client di Office 2013 nei dispositivi Windows, [abilitare l'autenticazione moderna](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication).</span><span class="sxs-lookup"><span data-stu-id="f96c2-106">If you have Office 2013 clients on Windows devices, [enable Modern Authentication](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication).</span></span>

- <span data-ttu-id="f96c2-107">Se si dispone di servizi directory di terze parti con Active Directory Federation Services (AD FS), configurare il server Azure Mae.</span><span class="sxs-lookup"><span data-stu-id="f96c2-107">If you have third-party directory services with Active Directory Federation Services (AD FS), set up the Azure MFA Server.</span></span> <span data-ttu-id="f96c2-108">Per ulteriori informazioni, vedere [scenari avanzati con autenticazione a più fattori di Azure e soluzioni VPN di terze parti](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) .</span><span class="sxs-lookup"><span data-stu-id="f96c2-108">See [advanced scenarios with Azure Multi-Factor Authentication and third-party VPN solutions](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) for more information.</span></span>

## <a name="step-1-decide-on-the-method-of-requiring-your-users-to-use-mfa"></a><span data-ttu-id="f96c2-109">Passaggio 1: decidere il metodo per richiedere agli utenti di utilizzare il Master</span><span class="sxs-lookup"><span data-stu-id="f96c2-109">Step 1: Decide on the method of requiring your users to use MFA</span></span>

<span data-ttu-id="f96c2-110">Esistono tre modi per richiedere agli utenti di utilizzare il servizio di autenticazione utente per gli accessi. Per i dettagli, vedere [supporto di AMF in Microsoft 365](multi-factor-authentication-microsoft-365.md) .</span><span class="sxs-lookup"><span data-stu-id="f96c2-110">There are three ways to require your users to use MFA for sign-ins. See [MFA support in Microsoft 365](multi-factor-authentication-microsoft-365.md) for the details.</span></span>

- <span data-ttu-id="f96c2-111">Impostazioni predefinite per la sicurezza (consigliata per le aziende di piccole dimensioni)</span><span class="sxs-lookup"><span data-stu-id="f96c2-111">Security defaults (recommended for small businesses)</span></span>

  <span data-ttu-id="f96c2-112">Se si è acquistato l'abbonamento o la versione di valutazione dopo il 21 ottobre 2019 e si è inaspettatamente richiesto l'AMF, le [impostazioni predefinite](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) per la sicurezza sono state abilitate automaticamente per l'abbonamento.</span><span class="sxs-lookup"><span data-stu-id="f96c2-112">If you purchased your subscription or trial after October 21, 2019, and you're unexpectedly prompted for MFA, [security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) have been automatically enabled for your subscription.</span></span>
  
  <span data-ttu-id="f96c2-113">Ogni nuova sottoscrizione Microsoft 365 avrà automaticamente le impostazioni predefinite per la sicurezza attivate.</span><span class="sxs-lookup"><span data-stu-id="f96c2-113">Every new Microsoft 365 subscription will automatically have security defaults turned on.</span></span> <span data-ttu-id="f96c2-114">Questo significa che ogni utente dovrà configurare il master e installare l'app Microsoft Authenticator sul proprio dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="f96c2-114">This means that every user will have to set up MFA and install the Microsoft Authenticator app on their mobile device.</span></span>

  <span data-ttu-id="f96c2-115">Tutti gli utenti devono utilizzare l'app Microsoft Authenticator come metodo di verifica aggiuntivo e l'autenticazione legacy è bloccata.</span><span class="sxs-lookup"><span data-stu-id="f96c2-115">All users must use the Microsoft Authenticator app as their additional verification method and legacy authentication is blocked.</span></span> 

- <span data-ttu-id="f96c2-116">Criteri di accesso condizionale (consigliato per le aziende)</span><span class="sxs-lookup"><span data-stu-id="f96c2-116">Conditional Access policies (recommended for enterprises)</span></span>

  <span data-ttu-id="f96c2-117">Gli utenti scelgono il metodo di verifica aggiuntivo durante la registrazione dell'AMF.</span><span class="sxs-lookup"><span data-stu-id="f96c2-117">Users choose the additional verification method during MFA registration.</span></span>

- <span data-ttu-id="f96c2-118">Account per utente (non consigliato)</span><span class="sxs-lookup"><span data-stu-id="f96c2-118">Per-user account (not recommended)</span></span>

  <span data-ttu-id="f96c2-119">Gli utenti scelgono il metodo di verifica aggiuntivo durante la registrazione dell'AMF.</span><span class="sxs-lookup"><span data-stu-id="f96c2-119">Users choose the additional verification method during MFA registration.</span></span>

## <a name="step-2-test-mfa-on-your-pilot-users"></a><span data-ttu-id="f96c2-120">Passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="f96c2-120">Step 2.</span></span> <span data-ttu-id="f96c2-121">Test dell'AMF per gli utenti pilota</span><span class="sxs-lookup"><span data-stu-id="f96c2-121">Test MFA on your pilot users</span></span>

<span data-ttu-id="f96c2-122">Se si utilizzano criteri di accesso condizionale o AMF per utente (scelta non consigliata), selezionare gli utenti pilota nell'azienda o nell'organizzazione per testare la registrazione e gli accessi dell'AMF. Per esempio:</span><span class="sxs-lookup"><span data-stu-id="f96c2-122">If you are using Conditional Access policies or per-user MFA (not recommended), select pilot users in your business or organization to test MFA registration and sign-ins. For example:</span></span>

- <span data-ttu-id="f96c2-123">Per i criteri di accesso condizionale, creare un gruppo di utenti pilota e un criterio che richiede l'AMF per i membri del gruppo e per tutte le app.</span><span class="sxs-lookup"><span data-stu-id="f96c2-123">For Conditional Access policies, create a pilot users group and a policy that requires MFA for the members of the group and for all apps.</span></span> <span data-ttu-id="f96c2-124">Aggiungere quindi gli account dell'utente pilota al gruppo.</span><span class="sxs-lookup"><span data-stu-id="f96c2-124">Then, add your pilot user’s accounts to the group.</span></span>

- <span data-ttu-id="f96c2-125">Per l'autenticazione a livello di utente, abilitare l'AMF per gli account utente degli utenti pilota una volta.</span><span class="sxs-lookup"><span data-stu-id="f96c2-125">For per-user MFA, enable MFA for the user accounts of your pilot users one a time.</span></span>

<span data-ttu-id="f96c2-126">Collaborare con gli utenti pilota per risolvere i problemi e le domande da preparare per una distribuzione uniforme all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f96c2-126">Work with your pilot users to address questions and issues to prepare for a smooth roll out to your organization.</span></span>

## <a name="step-3-inform-your-organization-that-mfa-is-coming"></a><span data-ttu-id="f96c2-127">Passaggio 3:</span><span class="sxs-lookup"><span data-stu-id="f96c2-127">Step 3.</span></span> <span data-ttu-id="f96c2-128">Informare l'organizzazione dell'arrivo dell'AMF</span><span class="sxs-lookup"><span data-stu-id="f96c2-128">Inform your organization that MFA is coming</span></span>

<span data-ttu-id="f96c2-129">Utilizzare le notifiche di posta elettronica, i poster dei corridoi, le riunioni del team o la formazione formale per garantire che i dipendenti comprendano:</span><span class="sxs-lookup"><span data-stu-id="f96c2-129">Use email notifications, hallway posters, team meetings, or formal training to ensure that your employees understand:</span></span>

- <span data-ttu-id="f96c2-130">Perché è necessario disporre dell'AMF per gli accessi</span><span class="sxs-lookup"><span data-stu-id="f96c2-130">Why MFA is being required for sign-ins</span></span>
- [<span data-ttu-id="f96c2-131">Come effettuare la registrazione per il metodo di verifica aggiuntivo</span><span class="sxs-lookup"><span data-stu-id="f96c2-131">How to register for their additional verification method</span></span>](https://support.office.com/article/set-up-your-microsoft-365-sign-in-for-multi-factor-authentication-ace1d096-61e5-449b-a875-58eb3d74de14?ui=en-US&rs=en-001&ad=US)
- [<span data-ttu-id="f96c2-132">Come effettuare l'accesso dopo la registrazione</span><span class="sxs-lookup"><span data-stu-id="f96c2-132">How to sign-in after registration</span></span>](https://support.office.com/article/sign-in-to-microsoft-365-with-multi-factor-authentication-2b856342-170a-438e-9a4f-3c092394d3cb)
- [<span data-ttu-id="f96c2-133">Come modificare il metodo di verifica aggiuntivo</span><span class="sxs-lookup"><span data-stu-id="f96c2-133">How to change their additional verification method</span></span>](https://support.office.com/article/change-how-you-do-additional-verification-956ec8d0-7081-4518-a701-f8414cc20831)
- [<span data-ttu-id="f96c2-134">Come gestire situazioni come un nuovo smartphone</span><span class="sxs-lookup"><span data-stu-id="f96c2-134">How to deal with situations like a new smart phone</span></span>](https://support.office.com/article/fix-common-problems-with-multi-factor-authentication-6951be76-af50-49a4-847f-21391eaa59f2)

<span data-ttu-id="f96c2-135">Soprattutto, assicurarsi che i dipendenti comprendano ***quando il requisito dell'AMF verrà imposto in*** modo che non li sorprenda.</span><span class="sxs-lookup"><span data-stu-id="f96c2-135">Most importantly, make sure your employees understand ***when the MFA requirement is going to be imposed*** so that it does not surprise them.</span></span>

## <a name="step-4-roll-out-the-mfa-requirement-to-your-organization-or-users"></a><span data-ttu-id="f96c2-136">Passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="f96c2-136">Step 4.</span></span> <span data-ttu-id="f96c2-137">Implementazione del requisito AMF per l'organizzazione o gli utenti</span><span class="sxs-lookup"><span data-stu-id="f96c2-137">Roll out the MFA requirement to your organization or users</span></span>

<span data-ttu-id="f96c2-138">In base al metodo di requisiti di AMF prescelto, distribuire l'autenticazione dell'AMF ai dipendenti oltre i tester pilota.</span><span class="sxs-lookup"><span data-stu-id="f96c2-138">Based on your chosen MFA requirement method, roll out MFA authentication to the employees beyond your pilot testers.</span></span>

### <a name="security-defaults"></a><span data-ttu-id="f96c2-139">Impostazioni predefinite per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="f96c2-139">Security defaults</span></span>

<span data-ttu-id="f96c2-140">È possibile abilitare o disabilitare le impostazioni predefinite di sicurezza dal riquadro delle **Proprietà** di Azure Active Directory (Azure ad) nel portale di Azure.</span><span class="sxs-lookup"><span data-stu-id="f96c2-140">You enable or disable security defaults from the **Properties** pane for Azure Active Directory (Azure AD) in the Azure portal.</span></span>

1.  <span data-ttu-id="f96c2-141">Accedere all'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com) con le credenziali di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="f96c2-141">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with global admin credentials.</span></span>
2.  <span data-ttu-id="f96c2-142">Passare alla [pagina Azure Active Directory-Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="f96c2-142">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
3.  <span data-ttu-id="f96c2-143">Nella parte inferiore della pagina scegliere **Gestire le impostazioni predefinite per la sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="f96c2-143">At the bottom of the page, choose **Manage Security defaults**.</span></span>
4.  <span data-ttu-id="f96c2-144">Scegliere **Sì** per abilitare le impostazioni predefinite per la sicurezza e **No** per disabilitare le impostazioni predefinite per la sicurezza e quindi scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f96c2-144">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

<span data-ttu-id="f96c2-145">Se sono stati utilizzati i [criteri di accesso condizionale di base](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection), ecco come passare a utilizzo delle impostazioni predefinite di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="f96c2-145">If you have been using [baseline Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection), here is how you move to using security defaults.</span></span>

1.  <span data-ttu-id="f96c2-146">Passare alla [pagina Criteri di accesso condizionale](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span><span class="sxs-lookup"><span data-stu-id="f96c2-146">Go to the [Conditional Access - Policies page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span></span>
2.  <span data-ttu-id="f96c2-147">Scegliere tutti i criteri di base che **sono attivi** e impostare **Attiva criterio** su **disattivato**.</span><span class="sxs-lookup"><span data-stu-id="f96c2-147">Choose each baseline policy that is **On** and set **Enable policy** to **Off**.</span></span>
2.  <span data-ttu-id="f96c2-148">Passare alla [pagina Azure Active Directory-Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="f96c2-148">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
4.  <span data-ttu-id="f96c2-149">Nella parte inferiore della pagina scegliere **Gestire le impostazioni predefinite per la sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="f96c2-149">At the bottom of the page, choose **Manage Security defaults**.</span></span>
5.  <span data-ttu-id="f96c2-150">Scegliere **Sì** per abilitare le impostazioni predefinite per la sicurezza e **No** per disabilitare le impostazioni predefinite per la sicurezza e quindi scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f96c2-150">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

### <a name="conditional-access-policies"></a><span data-ttu-id="f96c2-151">Criteri di accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="f96c2-151">Conditional Access policies</span></span>

<span data-ttu-id="f96c2-152">Creare, configurare e abilitare i criteri corretti che includono il gruppo di utenti che richiedono l'autenticazione a più fattori per l'accesso.</span><span class="sxs-lookup"><span data-stu-id="f96c2-152">Create, configure, and enable the appropriate policies that include the group of users that require MFA for sign-in.</span></span>

### <a name="per-user-mfa-not-recommended"></a><span data-ttu-id="f96c2-153">AMF per utente (non consigliata)</span><span class="sxs-lookup"><span data-stu-id="f96c2-153">Per-user MFA (not recommended)</span></span>

<span data-ttu-id="f96c2-154">Abilitare gli account utente per l'AMF corrispondente all'implementazione.</span><span class="sxs-lookup"><span data-stu-id="f96c2-154">Enable user accounts for MFA corresponding to your rollout.</span></span>

### <a name="supporting-your-employees"></a><span data-ttu-id="f96c2-155">Supporto dei dipendenti</span><span class="sxs-lookup"><span data-stu-id="f96c2-155">Supporting your employees</span></span>

<span data-ttu-id="f96c2-156">Quando i dipendenti si iscrivono e iniziano a eseguire l'accesso con l'AMF, assicurarsi che gli specialisti IT, il reparto IT o il supporto tecnico possano rispondere rapidamente a domande e risolvere i problemi.</span><span class="sxs-lookup"><span data-stu-id="f96c2-156">As your employees register and begin signing in with MFA, ensure that your IT specialists, IT department, or helpdesk can answer questions and address issues quickly.</span></span>

<span data-ttu-id="f96c2-157">Vedere questo articolo per [informazioni sulla risoluzione dei problemi relativi agli accessi dell'AMF](https://support.office.com/article/fix-common-problems-with-multi-factor-authentication-6951be76-af50-49a4-847f-21391eaa59f2).</span><span class="sxs-lookup"><span data-stu-id="f96c2-157">See this article for [information about troubleshooting MFA sign-ins](https://support.office.com/article/fix-common-problems-with-multi-factor-authentication-6951be76-af50-49a4-847f-21391eaa59f2).</span></span> 


