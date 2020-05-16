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
description: Informazioni su come utilizzare le impostazioni predefinite per la sicurezza per configurare l'autenticazione a più fattori per gli utenti.
monikerRange: o365-worldwide
ms.openlocfilehash: c4ea6037b34d29f2d1e05e248e03e49ee6b06f56
ms.sourcegitcommit: 22e9f54d0d3ead2be91a38d49325308c70f43f90
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "44262376"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="257e5-103">Configurare l'autenticazione a più fattori</span><span class="sxs-lookup"><span data-stu-id="257e5-103">Set up multi-factor authentication</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="257e5-104">Se l'abbonamento o il processo è stato acquistato dopo il 21 ottobre 2019 e viene richiesto l'autenticazione a più fattori, le [impostazioni predefinite](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) per la sicurezza sono state abilitate automaticamente per l'abbonamento.</span><span class="sxs-lookup"><span data-stu-id="257e5-104">If you purchased your subscription or trial after October 21, 2019, and you're unexpectedly prompted for multi-factor authentication (MFA), [security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) have been automatically enabled for your subscription.</span></span>

<span data-ttu-id="257e5-105">Ogni nuova sottoscrizione Microsoft 365 avrà automaticamente le [impostazioni predefinite](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) per la sicurezza attivate.</span><span class="sxs-lookup"><span data-stu-id="257e5-105">Every new Microsoft 365 subscription will automatically have [security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) turned on.</span></span> <span data-ttu-id="257e5-106">Questo significa che ogni utente dovrà configurare l'autenticazione a più fattori e installare l'app Microsoft Authenticator sul proprio dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="257e5-106">This means that every user will have to set up multi-factor authentication (MFA) and install the Microsoft Authenticator app on their mobile device.</span></span> <span data-ttu-id="257e5-107">Per ulteriori informazioni, vedere [set up Mae for a Microsoft 365 account](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).</span><span class="sxs-lookup"><span data-stu-id="257e5-107">For more information, see [Set up MFA for a Microsoft 365 account](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).</span></span>

<span data-ttu-id="257e5-108">I nove ruoli di amministratore seguenti dovranno eseguire delle autenticazioni aggiuntive ogni volta che eseguono l'accesso:</span><span class="sxs-lookup"><span data-stu-id="257e5-108">The following nine administrator roles will be required to perform additional authentication every time they sign in:</span></span>

- <span data-ttu-id="257e5-109">Amministratore globale</span><span class="sxs-lookup"><span data-stu-id="257e5-109">Global administrator</span></span>
- <span data-ttu-id="257e5-110">Amministratore di SharePoint</span><span class="sxs-lookup"><span data-stu-id="257e5-110">SharePoint administrator</span></span>
- <span data-ttu-id="257e5-111">Amministratore di Exchange</span><span class="sxs-lookup"><span data-stu-id="257e5-111">Exchange administrator</span></span>
- <span data-ttu-id="257e5-112">Amministratore di accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="257e5-112">Conditional Access administrator</span></span>
- <span data-ttu-id="257e5-113">Amministratore della sicurezza</span><span class="sxs-lookup"><span data-stu-id="257e5-113">Security administrator</span></span>
- <span data-ttu-id="257e5-114">Amministratore supporto tecnico o amministratore password:</span><span class="sxs-lookup"><span data-stu-id="257e5-114">Helpdesk administrator or password administrator</span></span>
- <span data-ttu-id="257e5-115">Amministratore fatturazione</span><span class="sxs-lookup"><span data-stu-id="257e5-115">Billing administrator</span></span>
- <span data-ttu-id="257e5-116">Amministratore utenti</span><span class="sxs-lookup"><span data-stu-id="257e5-116">User administrator</span></span>
- <span data-ttu-id="257e5-117">Amministratore dell'autenticazione</span><span class="sxs-lookup"><span data-stu-id="257e5-117">Authentication administrator</span></span>

<span data-ttu-id="257e5-118">Tutti gli altri utenti dovranno eseguire l'autenticazione aggiuntiva quando necessario.</span><span class="sxs-lookup"><span data-stu-id="257e5-118">All other users will be asked to perform additional authentication when needed.</span></span>

> [!NOTE]
> <span data-ttu-id="257e5-119">È necessario essere un amministratore globale per impostare o modificare il Master</span><span class="sxs-lookup"><span data-stu-id="257e5-119">You must be a global admin to set up or modify MFA</span></span> <br><br>
> <span data-ttu-id="257e5-120">Se non si usa la nuova interfaccia di amministrazione di Microsoft 365, è possibile attivarla selezionando l'opzione **Prova la nuova interfaccia di amministrazione** che si trova nella parte superiore della home page.</span><span class="sxs-lookup"><span data-stu-id="257e5-120">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

<span data-ttu-id="257e5-121">Se in precedenza è stata configurata l'autenticazione con criteri di base, è necessario disattivarla [per abilitare le impostazioni predefinite per la sicurezza](#move-from-baseline-policies-to-security-defaults).</span><span class="sxs-lookup"><span data-stu-id="257e5-121">If you have previously set up MFA with baseline policies, [you must turn them off to turn on security defaults](#move-from-baseline-policies-to-security-defaults).</span></span> <span data-ttu-id="257e5-122">Tuttavia, se si dispone di Microsoft 365 business o l'abbonamento include [Azure Active Directory Premium P1 o Azure Active Directory Premium P2](https://azure.microsoft.com/pricing/details/active-directory/), è anche possibile configurare i criteri di [accesso condizionale](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) .</span><span class="sxs-lookup"><span data-stu-id="257e5-122">However, if you have Microsoft 365 Business or your subscription includes [Azure Active Directory Premium P1 or Azure Active Directory Premium P2](https://azure.microsoft.com/pricing/details/active-directory/), you can also set up [Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies.</span></span> <span data-ttu-id="257e5-123">Per utilizzare i criteri di accesso condizionale, è necessario verificare che le impostazioni predefinite per la sicurezza siano disabilitate e che [l'autenticazione moderna](#enable-modern-authentication-for-your-organization) sia abilitata.</span><span class="sxs-lookup"><span data-stu-id="257e5-123">To use Conditional Access policies, you need to make sure security defaults are disabled and [modern authentication](#enable-modern-authentication-for-your-organization) is enabled.</span></span>

> [!TIP]
> <span data-ttu-id="257e5-124">Per spiegare agli utenti come configurare l'app Microsoft Authenticator, vedere [utilizzare Microsoft Authenticator con Office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411).</span><span class="sxs-lookup"><span data-stu-id="257e5-124">To explain to your users how to set up the Microsoft Authenticator app, see [Use Microsoft Authenticator with Office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411).</span></span>

## <a name="manage-security-defaults"></a><span data-ttu-id="257e5-125">Gestire le impostazioni predefinite per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="257e5-125">Manage security defaults</span></span>

1. <span data-ttu-id="257e5-126">Accedere al [portale di amministrazione](https://go.microsoft.com/fwlink/p/?linkid=834822) con le credenziali di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="257e5-126">Sign in to the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822) with global admin credentials.</span></span>
2. <span data-ttu-id="257e5-127">Passare alla [pagina Azure Active Directory-Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="257e5-127">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
3. <span data-ttu-id="257e5-128">Nella parte inferiore della pagina scegliere **Gestire le impostazioni predefinite per la sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="257e5-128">At the bottom of the page, choose **Manage Security defaults**.</span></span>
4. <span data-ttu-id="257e5-129">Scegliere **Sì** per abilitare le impostazioni predefinite per la sicurezza e **No** per disabilitare le impostazioni predefinite per la sicurezza e quindi scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="257e5-129">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

## <a name="move-from-baseline-policies-to-security-defaults"></a><span data-ttu-id="257e5-130">Passare dai criteri di base alle impostazioni predefinite per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="257e5-130">Move from baseline policies to security defaults</span></span>

1. <span data-ttu-id="257e5-131">Passare alla [pagina Criteri di accesso condizionale](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span><span class="sxs-lookup"><span data-stu-id="257e5-131">Go to the [Conditional Access - Policies page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span></span>
2. <span data-ttu-id="257e5-132">Scegliere tutti i criteri di base che **sono attivi** e impostare **Attiva criterio** su **disattivato**.</span><span class="sxs-lookup"><span data-stu-id="257e5-132">Choose each baseline policy that is **On** and set **Enable policy** to **Off**.</span></span>
3. <span data-ttu-id="257e5-133">Passare alla [pagina Azure Active Directory-Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="257e5-133">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
4. <span data-ttu-id="257e5-134">Nella parte inferiore della pagina fare clic su **Gestisci impostazioni predefinite di sicurezza**e, nel riquadro **Attiva impostazioni di sicurezza** , impostare **Consenti impostazioni predefinite di sicurezza** su **Sì**e quindi scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="257e5-134">On the bottom of the page, choose **Manage Security defaults**, and in the **Enable Security defaults** pane, set **Enable Security defaults** toggle to **Yes**, and then choose **Save**.</span></span> 

## <a name="enable-modern-authentication-for-your-organization"></a><span data-ttu-id="257e5-135">Abilitare l'autenticazione moderna per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="257e5-135">Enable modern authentication for your organization</span></span>

<span data-ttu-id="257e5-136">Tutte le applicazioni client di Office 2016 supportano MFA con ADAL (Active Directory Authentication Library).</span><span class="sxs-lookup"><span data-stu-id="257e5-136">All Office 2016 client applications support MFA through the use of the Active Directory Authentication Library (ADAL).</span></span> <span data-ttu-id="257e5-137">Questo significa che le password dell'app non sono necessarie per i client di Office 2016.</span><span class="sxs-lookup"><span data-stu-id="257e5-137">This means that app passwords aren't required for Office 2016 clients.</span></span> <span data-ttu-id="257e5-138">Per ulteriori informazioni, vedere [questo articolo](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-mfasettings#app-passwords) .</span><span class="sxs-lookup"><span data-stu-id="257e5-138">See [this article](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-mfasettings#app-passwords) for more information.</span></span>

<span data-ttu-id="257e5-139">Tuttavia, è necessario assicurarsi che la sottoscrizione Microsoft 365 sia abilitata per l'autenticazione di ADAL o moderna.</span><span class="sxs-lookup"><span data-stu-id="257e5-139">However, you need to make sure your Microsoft 365 subscription is enabled for ADAL, or modern authentication.</span></span>

1. <span data-ttu-id="257e5-140">Per abilitare l'autenticazione moderna, nell'interfaccia di [Amministrazione](https://go.microsoft.com/fwlink/p/?linkid=834822)selezionare **Impostazioni** \> **organizzazione organizzativa** e quindi nella scheda **Servizi** scegliere **autenticazione moderna** dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="257e5-140">To enable modern authentication, from the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), select **Settings** \> **Org Settings** and then in the **Services** tab, choose **Modern authentication** from the list.</span></span>

2. <span data-ttu-id="257e5-141">Selezionare la casella **Attiva autenticazione moderna (scelta consigliata)** nel pannello **autenticazione moderna** e quindi fare clic su **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="257e5-141">Check the **Enable modern authentication (recommended)** box in the **Modern authentication** panel, and then choose **Save changes**.</span></span> 

    ![Pannello Autenticazione moderna con casella di controllo Abilita selezionata.](../../media/enablemodernauth.png)
    
> [!IMPORTANT]
> <span data-ttu-id="257e5-143">A agosto del 2017, tutte le nuove sottoscrizioni di Microsoft 365 che includono Skype for business online ed Exchange Online hanno l'autenticazione moderna abilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="257e5-143">As of August of 2017, all new Microsoft 365 subscriptions that include Skype for Business online and Exchange online have modern authentication enabled by default.</span></span> <span data-ttu-id="257e5-144">Per controllare lo stato di autenticazione moderna di Skype for Business Online, è possibile usare PowerShell per Skype for Business Online con credenziali di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="257e5-144">To check your modern authentication status for Skype for Business online, you can use Skype for Business online PowerShell with Global Admin credentials.</span></span> <span data-ttu-id="257e5-145">Eseguire Get-CsOAuthConfiguration per controllare l'output di -ClientADALAuthOverride.</span><span class="sxs-lookup"><span data-stu-id="257e5-145">Run Get-CsOAuthConfiguration to check the output of -ClientADALAuthOverride.</span></span> <span data-ttu-id="257e5-146">Se -ClientADALAuthOverride è "Allowed" (Consentito), l'autenticazione moderna è attiva.</span><span class="sxs-lookup"><span data-stu-id="257e5-146">If -ClientADALAuthOverride is 'Allowed', modern authentication is on.</span></span>
<span data-ttu-id="257e5-147">Per controllare lo stato di autenticazione moderna per Exchange Online, vedere [Abilitare l'autenticazione moderna in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).</span><span class="sxs-lookup"><span data-stu-id="257e5-147">To check your MA status for Exchange Online, please visit [Enable modern authentication in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).</span></span>

## <a name="related-articles"></a><span data-ttu-id="257e5-148">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="257e5-148">Related articles</span></span>

[<span data-ttu-id="257e5-149">Top 10 modi per proteggere i piani Microsoft 365 for business</span><span class="sxs-lookup"><span data-stu-id="257e5-149">Top 10 ways to secure Microsoft 365 for business plans</span></span>](secure-your-business-data.md)

[<span data-ttu-id="257e5-150">Abilitare l'autenticazione moderna per Office 2013 nei dispositivi Windows</span><span class="sxs-lookup"><span data-stu-id="257e5-150">Enable Modern Authentication for Office 2013 on Windows devices</span></span>](enable-modern-authentication.md)
