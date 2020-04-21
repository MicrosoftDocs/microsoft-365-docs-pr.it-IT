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
ms.openlocfilehash: 4a829aa597596564b9c2f468e72f3a766b198372
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43627681"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="93ddc-103">Configurare l'autenticazione a più fattori</span><span class="sxs-lookup"><span data-stu-id="93ddc-103">Set up multi-factor authentication</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="93ddc-104">Se si è acquistato l'abbonamento o la versione di valutazione dopo il 21 ottobre 2019 e si è inaspettatamente richiesto l'AMF, le [impostazioni predefinite](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) per la sicurezza sono state abilitate automaticamente per l'abbonamento.</span><span class="sxs-lookup"><span data-stu-id="93ddc-104">If you purchased your subscription or trial after October 21, 2019, and you're unexpectedly prompted for MFA, [security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) have been automatically enabled for your subscription.</span></span>

<span data-ttu-id="93ddc-105">Ogni nuova sottoscrizione Microsoft 365 avrà automaticamente le impostazioni predefinite per la sicurezza attivate.</span><span class="sxs-lookup"><span data-stu-id="93ddc-105">Every new Microsoft 365 subscription will automatically have security defaults turned on.</span></span> <span data-ttu-id="93ddc-106">Ciò significa che ogni utente dovrà configurare l'autenticazione a più fattori e installare l'app Authenticator nel proprio dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="93ddc-106">This means that every user will have to set up multi-factor authentication (MFA) and install the Authenticator app on their mobile device.</span></span> <span data-ttu-id="93ddc-107">Per ulteriori informazioni, vedere [configurare la verifica in due passaggi per Microsoft 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).</span><span class="sxs-lookup"><span data-stu-id="93ddc-107">For more information, see [Set up 2-step verification for Microsoft 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).</span></span>  

<span data-ttu-id="93ddc-108">I nove ruoli di amministratore seguenti dovranno eseguire delle autenticazioni aggiuntive ogni volta che eseguono l'accesso:</span><span class="sxs-lookup"><span data-stu-id="93ddc-108">The following nine administrator roles will be required to perform additional authentication every time they sign in:</span></span>

- <span data-ttu-id="93ddc-109">Amministratore globale</span><span class="sxs-lookup"><span data-stu-id="93ddc-109">Global administrator</span></span>
- <span data-ttu-id="93ddc-110">Amministratore di SharePoint</span><span class="sxs-lookup"><span data-stu-id="93ddc-110">SharePoint administrator</span></span>
- <span data-ttu-id="93ddc-111">Amministratore di Exchange</span><span class="sxs-lookup"><span data-stu-id="93ddc-111">Exchange administrator</span></span>
- <span data-ttu-id="93ddc-112">Amministratore di accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="93ddc-112">Conditional Access administrator</span></span>
- <span data-ttu-id="93ddc-113">Amministratore della sicurezza</span><span class="sxs-lookup"><span data-stu-id="93ddc-113">Security administrator</span></span>
- <span data-ttu-id="93ddc-114">Amministratore supporto tecnico o amministratore password:</span><span class="sxs-lookup"><span data-stu-id="93ddc-114">Helpdesk administrator or password administrator</span></span>
- <span data-ttu-id="93ddc-115">Amministratore fatturazione</span><span class="sxs-lookup"><span data-stu-id="93ddc-115">Billing administrator</span></span>
- <span data-ttu-id="93ddc-116">Amministratore utenti</span><span class="sxs-lookup"><span data-stu-id="93ddc-116">User administrator</span></span>
- <span data-ttu-id="93ddc-117">Amministratore dell'autenticazione</span><span class="sxs-lookup"><span data-stu-id="93ddc-117">Authentication administrator</span></span>

<span data-ttu-id="93ddc-118">Tutti gli altri utenti dovranno eseguire l'autenticazione aggiuntiva quando necessario.</span><span class="sxs-lookup"><span data-stu-id="93ddc-118">All other users will be asked to perform additional authentication when needed.</span></span> <span data-ttu-id="93ddc-119">Per altre informazioni, vedere [Che cosa sono le impostazioni predefinite per la sicurezza?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span><span class="sxs-lookup"><span data-stu-id="93ddc-119">For more information, see [What are security defaults?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span></span>

> [!NOTE]
> <span data-ttu-id="93ddc-120">Per impostare o modificare l'autenticazione a più fattori, è necessario essere un amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="93ddc-120">You must be a global admin to set up or modify multi-factor authentication.</span></span> <br><br>
> <span data-ttu-id="93ddc-121">Se non si usa la nuova interfaccia di amministrazione di Microsoft 365, è possibile attivarla selezionando l'opzione **Prova la nuova interfaccia di amministrazione** che si trova nella parte superiore della home page.</span><span class="sxs-lookup"><span data-stu-id="93ddc-121">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

<span data-ttu-id="93ddc-122">Se in precedenza è stata configurata l'autenticazione a più fattori con criteri di base [è necessario disattivare quest'ultimi e attivare le impostazioni predefinite per la sicurezza](#move-from-baseline-policies-to-security-defaults).</span><span class="sxs-lookup"><span data-stu-id="93ddc-122">If you have previously set up MFA with baseline policies, [you must turn them off and turn on security defaults](#move-from-baseline-policies-to-security-defaults).</span></span> <span data-ttu-id="93ddc-123">Tuttavia, se si dispone di Microsoft 365 Business o il proprio abbonamento include [Azure Active Directory Premium 1 o Azure Active Directory Premium 2](https://azure.microsoft.com/pricing/details/active-directory/) è possibile inoltre configurare i criteri di [accesso condizionale](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span><span class="sxs-lookup"><span data-stu-id="93ddc-123">However, if you have Microsoft 365 Business or your subscription includes [Azure Active Directory Premium 1, or Azure Active Directory Premium 2](https://azure.microsoft.com/pricing/details/active-directory/), you can also set up [conditional access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies.</span></span> <span data-ttu-id="93ddc-124">Per utilizzare i criteri di accesso condizionale, è necessario verificare che [l'autenticazione moderna](#enable-modern-authentication-for-your-organization) sia abilitata.</span><span class="sxs-lookup"><span data-stu-id="93ddc-124">To use conditional access policies, you need to make sure [modern authentication](#enable-modern-authentication-for-your-organization) is enabled.</span></span>

> [!TIP]
> <span data-ttu-id="93ddc-125">Per spiegare agli utenti come configurare l'app Authenticator, visitare [Usare Microsoft Authenticator con Office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411?ui=en-US&rs=en-US&ad=US#ID0EAADAAA=_Step_1).</span><span class="sxs-lookup"><span data-stu-id="93ddc-125">To explain to your users how to set up the Authenticator app, please visit [Use Microsoft Authenticator with office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411?ui=en-US&rs=en-US&ad=US#ID0EAADAAA=_Step_1).</span></span>

## <a name="manage-security-defaults"></a><span data-ttu-id="93ddc-126">Gestire le impostazioni predefinite per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="93ddc-126">Manage security defaults</span></span>

1. <span data-ttu-id="93ddc-127">Accedere all'[interfaccia di amministrazione](https://go.microsoft.com/fwlink/p/?linkid=834822) con le credenziali di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="93ddc-127">Sign in to the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822) with your Global admin credentials.</span></span>
2. <span data-ttu-id="93ddc-128">Passare alle [Proprietà di Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="93ddc-128">Go to [Azure Active Directory Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
3. <span data-ttu-id="93ddc-129">Nella parte inferiore della pagina scegliere **Gestire le impostazioni predefinite per la sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="93ddc-129">At the bottom of the page, choose **Manage Security defaults**.</span></span>
4. <span data-ttu-id="93ddc-130">Scegliere **Sì** per abilitare le impostazioni predefinite di sicurezza e **No** per disabilitare le impostazioni predefinite per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="93ddc-130">Choose **Yes** to enable security defaults and **No** to disable security defaults.</span></span>

## <a name="move-from-baseline-policies-to-security-defaults"></a><span data-ttu-id="93ddc-131">Passare dai criteri di base alle impostazioni predefinite per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="93ddc-131">Move from baseline policies to security defaults</span></span>

1. <span data-ttu-id="93ddc-132">Nell'[interfaccia di amministrazione](https://go.microsoft.com/fwlink/p/?linkid=834822) selezionare **Configurazione**.</span><span class="sxs-lookup"><span data-stu-id="93ddc-132">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), select **Setup**.</span></span>

2. <span data-ttu-id="93ddc-133">Accanto a **Accesso e sicurezza**, in **Rendi l’accesso più sicuro**, selezionare **Visualizzazione**.</span><span class="sxs-lookup"><span data-stu-id="93ddc-133">Next to **Sign-in and security**, under **Make sign-in more secure**, select **View**.</span></span>

3. <span data-ttu-id="93ddc-134">In **Rendi l’accesso più sicuro**, selezionare **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="93ddc-134">Under **Make sign-in more secure**, select **Manage**.</span></span> 

4. <span data-ttu-id="93ddc-135">Nella pagina **criteri di accesso condizionale** scegliere tutti i criteri di base **che sono**attivi e impostarli su **disattivato**.</span><span class="sxs-lookup"><span data-stu-id="93ddc-135">On the **Conditional Access - Policies** page, choose each Baseline policy that is **On**, and set them to **Off**.</span></span>
5. <span data-ttu-id="93ddc-136">Passare alla pagina [Proprietà di Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="93ddc-136">Go to [Azure Active Directory Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) page.</span></span>
6. <span data-ttu-id="93ddc-137">Nella parte inferiore della pagina fare clic su **Gestisci impostazioni predefinite di sicurezza**e, nel riquadro **Attiva impostazioni di sicurezza** , impostare **Consenti impostazioni predefinite di sicurezza** su **Sì**e quindi scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="93ddc-137">On the bottom of the page, choose **Manage Security defaults**, and in the **Enable Security defaults** pane, set **Enable Security defaults** toggle to **Yes**, and then choose **Save**.</span></span> 

## <a name="enable-modern-authentication-for-your-organization"></a><span data-ttu-id="93ddc-138">Abilitare l'autenticazione moderna per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="93ddc-138">Enable modern authentication for your organization</span></span>

<span data-ttu-id="93ddc-139">Tutte le applicazioni client di Office 2016 supportano MFA con ADAL (Active Directory Authentication Library).</span><span class="sxs-lookup"><span data-stu-id="93ddc-139">All Office 2016 client applications support MFA through the use of the Active Directory Authentication Library (ADAL).</span></span> <span data-ttu-id="93ddc-140">Questo significa che le password dell'app non sono necessarie per i client di Office 2016.</span><span class="sxs-lookup"><span data-stu-id="93ddc-140">This means that app passwords aren't required for Office 2016 clients.</span></span> <span data-ttu-id="93ddc-141">Tuttavia, è necessario assicurarsi che la sottoscrizione Microsoft 365 sia abilitata per l'autenticazione di ADAL o moderna.</span><span class="sxs-lookup"><span data-stu-id="93ddc-141">However, you need to make sure your Microsoft 365 subscription is enabled for ADAL, or modern authentication.</span></span>

1. <span data-ttu-id="93ddc-142">Per abilitare l'autenticazione moderna, nell'[interfaccia di amministrazione](https://go.microsoft.com/fwlink/p/?linkid=834822) selezionare **Impostazioni** \> **Impostazioni** e quindi nella scheda **Servizi** scegliere **Autenticazione moderna** dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="93ddc-142">To enable modern authentication, from the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), select **Settings** \> **Settings** and then in the **Services** tab, choose **Modern authentication** from the list.</span></span>

2. <span data-ttu-id="93ddc-143">Selezionare la casella **Attiva autenticazione moderna (scelta consigliata)** nel pannello **autenticazione moderna** e quindi fare clic su **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="93ddc-143">Check the **Enable modern authentication (recommended)** box in the **Modern authentication** panel, and then choose **Save changes**.</span></span> 

    ![Pannello Autenticazione moderna con casella di controllo Abilita selezionata.](../../media/enablemodernauth.png)
    
> [!IMPORTANT]
> <span data-ttu-id="93ddc-145">A agosto del 2017, tutte le nuove sottoscrizioni di Microsoft 365 che includono Skype for business online ed Exchange Online hanno l'autenticazione moderna abilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="93ddc-145">As of August of 2017, all new Microsoft 365 subscriptions that include Skype for Business online and Exchange online have modern authentication enabled by default.</span></span> <span data-ttu-id="93ddc-146">Per controllare lo stato di autenticazione moderna di Skype for Business Online, è possibile usare PowerShell per Skype for Business Online con credenziali di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="93ddc-146">To check your modern authentication status for Skype for Business online, you can use Skype for Business online PowerShell with Global Admin credentials.</span></span> <span data-ttu-id="93ddc-147">Eseguire Get-CsOAuthConfiguration per controllare l'output di -ClientADALAuthOverride.</span><span class="sxs-lookup"><span data-stu-id="93ddc-147">Run Get-CsOAuthConfiguration to check the output of -ClientADALAuthOverride.</span></span> <span data-ttu-id="93ddc-148">Se -ClientADALAuthOverride è "Allowed" (Consentito), l'autenticazione moderna è attiva.</span><span class="sxs-lookup"><span data-stu-id="93ddc-148">If -ClientADALAuthOverride is 'Allowed', modern authentication is on.</span></span>
<span data-ttu-id="93ddc-149">Per controllare lo stato di autenticazione moderna per Exchange Online, vedere [Abilitare l'autenticazione moderna in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).</span><span class="sxs-lookup"><span data-stu-id="93ddc-149">To check your MA status for Exchange Online, please visit [Enable modern authentication in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).</span></span>

## <a name="related-articles"></a><span data-ttu-id="93ddc-150">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="93ddc-150">Related articles</span></span>

[<span data-ttu-id="93ddc-151">Top 10 modi per proteggere i piani Microsoft 365 for business</span><span class="sxs-lookup"><span data-stu-id="93ddc-151">Top 10 ways to secure Microsoft 365 for business plans</span></span>](secure-your-business-data.md)

[<span data-ttu-id="93ddc-152">Abilitare l'autenticazione moderna per Office 2013 nei dispositivi Windows</span><span class="sxs-lookup"><span data-stu-id="93ddc-152">Enable Modern Authentication for Office 2013 on Windows devices</span></span>](enable-modern-authentication.md)
