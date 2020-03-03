---
title: Configurare l'autenticazione a più fattori per gli utenti di Office 365
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
description: Informazioni su come usare le impostazioni predefinite per la sicurezza per configurare l'autenticazione a più fattori per gli utenti di Office 365.
monikerRange: o365-worldwide
ms.openlocfilehash: 4dc52c25c3a9351be1a9f4d094d664bc4ed527f9
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/02/2020
ms.locfileid: "42361047"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="9f6d5-103">Configurare l'autenticazione a più fattori</span><span class="sxs-lookup"><span data-stu-id="9f6d5-103">Set up multi-factor authentication</span></span>
  
<span data-ttu-id="9f6d5-104">Nei nuovi abbonamenti a Office 365 per le aziende o Microsoft 365 Business le impostazioni predefinite per la sicurezza sono attivate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="9f6d5-104">Every new Office 365 for business or Microsoft 365 Business subscription will automatically have security defaults turned on.</span></span> <span data-ttu-id="9f6d5-105">Ciò significa che ogni utente dovrà configurare l'autenticazione a più fattori e installare l'app Authenticator nel proprio dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="9f6d5-105">This means that every user will have to set up multi-factor authentication (MFA) and install the Authenticator app on their mobile device.</span></span> <span data-ttu-id="9f6d5-106">Per altre informazioni, vedere [Configurare la verifica in due passaggi per Office 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).</span><span class="sxs-lookup"><span data-stu-id="9f6d5-106">For more information, see [Set up 2-step verification for Office 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).</span></span>  

<span data-ttu-id="9f6d5-107">I nove ruoli di amministratore seguenti dovranno eseguire delle autenticazioni aggiuntive ogni volta che eseguono l'accesso:</span><span class="sxs-lookup"><span data-stu-id="9f6d5-107">The following nine administrator roles will be required to perform additional authentication every time they sign in:</span></span>
- <span data-ttu-id="9f6d5-108">Amministratore globale</span><span class="sxs-lookup"><span data-stu-id="9f6d5-108">Global administrator</span></span>
- <span data-ttu-id="9f6d5-109">Amministratore di SharePoint</span><span class="sxs-lookup"><span data-stu-id="9f6d5-109">SharePoint administrator</span></span>
- <span data-ttu-id="9f6d5-110">Amministratore di Exchange</span><span class="sxs-lookup"><span data-stu-id="9f6d5-110">Exchange administrator</span></span>
- <span data-ttu-id="9f6d5-111">Amministratore di accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="9f6d5-111">Conditional Access administrator</span></span>
- <span data-ttu-id="9f6d5-112">Amministratore della sicurezza</span><span class="sxs-lookup"><span data-stu-id="9f6d5-112">Security administrator</span></span>
- <span data-ttu-id="9f6d5-113">Amministratore supporto tecnico o amministratore password:</span><span class="sxs-lookup"><span data-stu-id="9f6d5-113">Helpdesk administrator or password administrator</span></span>
- <span data-ttu-id="9f6d5-114">Amministratore fatturazione</span><span class="sxs-lookup"><span data-stu-id="9f6d5-114">Billing administrator</span></span>
- <span data-ttu-id="9f6d5-115">Amministratore utenti</span><span class="sxs-lookup"><span data-stu-id="9f6d5-115">User administrator</span></span>
- <span data-ttu-id="9f6d5-116">Amministratore dell'autenticazione</span><span class="sxs-lookup"><span data-stu-id="9f6d5-116">Authentication administrator</span></span>

<span data-ttu-id="9f6d5-117">Tutti gli altri utenti dovranno eseguire l'autenticazione aggiuntiva quando necessario.</span><span class="sxs-lookup"><span data-stu-id="9f6d5-117">All other users will be asked to perform additional authentication when needed.</span></span> <span data-ttu-id="9f6d5-118">Per altre informazioni, vedere [Che cosa sono le impostazioni predefinite per la sicurezza?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span><span class="sxs-lookup"><span data-stu-id="9f6d5-118">For more information, see [What are security defaults?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span></span>

> [!NOTE]
> <span data-ttu-id="9f6d5-p103">Per configurare o modificare l'autenticazione a più fattori è necessario essere un amministratore globale di Office 365. </span><span class="sxs-lookup"><span data-stu-id="9f6d5-p103">You must be an Office 365 global admin to set up or modify multi-factor authentication. </span></span><br><br>
> <span data-ttu-id="9f6d5-120">Se non si usa la nuova interfaccia di amministrazione di Microsoft 365, è possibile attivarla selezionando l'opzione **Prova la nuova interfaccia di amministrazione** che si trova nella parte superiore della home page.</span><span class="sxs-lookup"><span data-stu-id="9f6d5-120">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

<span data-ttu-id="9f6d5-121">Se in precedenza è stata configurata l'autenticazione a più fattori con criteri di base [è necessario disattivare quest'ultimi e attivare le impostazioni predefinite per la sicurezza](#move-from-baseline-policies-to-security-defaults).</span><span class="sxs-lookup"><span data-stu-id="9f6d5-121">If you have previously set up MFA with baseline policies, [you must turn them off and turn on security defaults](#move-from-baseline-policies-to-security-defaults).</span></span> <span data-ttu-id="9f6d5-122">Tuttavia, se si dispone di Microsoft 365 Business o il proprio abbonamento include [Azure Active Directory Premium 1 o Azure Active Directory Premium 2](https://azure.microsoft.com/pricing/details/active-directory/) è possibile inoltre configurare i criteri di [accesso condizionale](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span><span class="sxs-lookup"><span data-stu-id="9f6d5-122">However, if you have Microsoft 365 Business or your subscription includes [Azure Active Directory Premium 1, or Azure Active Directory Premium 2](https://azure.microsoft.com/pricing/details/active-directory/), you can also set up [conditional access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies.</span></span> <span data-ttu-id="9f6d5-123">Per usare i criteri di accesso condizionale, è necessario assicurarsi che sia [abilitata l'autenticazione moderna](#enable-multi-factor-authentication-for-your-organization).</span><span class="sxs-lookup"><span data-stu-id="9f6d5-123">To use conditional access policies, you need to make sure [modern authentication is enabled](#enable-multi-factor-authentication-for-your-organization).</span></span>

## <a name="manage-security-defaults"></a><span data-ttu-id="9f6d5-124">Gestire le impostazioni predefinite per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="9f6d5-124">Manage security defaults</span></span>

1. <span data-ttu-id="9f6d5-125">Accedere all'[interfaccia di amministrazione](https://go.microsoft.com/fwlink/p/?linkid=834822) con le credenziali di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="9f6d5-125">Sign in to [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822) with your Global admin credentials.</span></span>
2. <span data-ttu-id="9f6d5-126">Passare alle [Proprietà di Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="9f6d5-126">Go to [Azure Active Directory Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>

3. <span data-ttu-id="9f6d5-127">Nella parte inferiore della pagina scegliere **Gestire le impostazioni predefinite per la sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="9f6d5-127">At the bottom of the page, choose **Manage Security defaults**.</span></span>
4. <span data-ttu-id="9f6d5-128">Scegliere **Sì** per abilitare le impostazioni predefinite di sicurezza e **No** per disabilitare le impostazioni predefinite per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="9f6d5-128">Choose **Yes** to enable security defaults and **No** to disable security defaults.</span></span>

## <a name="move-from-baseline-policies-to-security-defaults"></a><span data-ttu-id="9f6d5-129">Passare dai criteri di base alle impostazioni predefinite per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="9f6d5-129">Move from baseline policies to security defaults</span></span>

1. <span data-ttu-id="9f6d5-130">Nell'[interfaccia di amministrazione](https://go.microsoft.com/fwlink/p/?linkid=834822) selezionare **Configurazione**.</span><span class="sxs-lookup"><span data-stu-id="9f6d5-130">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), select **Setup**.</span></span>

2. <span data-ttu-id="9f6d5-131">Accanto a **Accesso e sicurezza**, in **Rendi l’accesso più sicuro**, selezionare **Visualizzazione**.</span><span class="sxs-lookup"><span data-stu-id="9f6d5-131">Next to **Sign-in and security**, under **Make sign-in more secure**, select **View**.</span></span>

3. <span data-ttu-id="9f6d5-132">In **Rendi l’accesso più sicuro**, selezionare **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="9f6d5-132">Under **Make sign-in more secure**, select **Manage**.</span></span> 

4. <span data-ttu-id="9f6d5-133">Nella pagina **Criteri di accesso condizionale al portale di Azure** selezionare ogni criterio di base **Attivato** e impostarlo su **Disattivato**.</span><span class="sxs-lookup"><span data-stu-id="9f6d5-133">On the **Azure portal Conditional Access - Policies** page,  choose each Baseline policy that is **On**, and set them to **Off**.</span></span>
5. <span data-ttu-id="9f6d5-134">Passare alla pagina [Proprietà di Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="9f6d5-134">Go to [Azure Active Directory Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) page.</span></span>
6. <span data-ttu-id="9f6d5-135">Nella parte inferiore della pagina scegliere **Gestire le impostazioni predefinite per la sicurezza**e nel riquadro **Abilitare le impostazioni predefinite per la sicurezza** impostare **Abilita le impostazioni predefinite per la sicurezza** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="9f6d5-135">On the bottom of the page, choose **Manage Security defaults**, and in the **Enable Security defaults** pane, set **Enable Security defaults** toggle to **Yes**.</span></span> 

## <a name="enable-modern-authentication-for-your-organization"></a><span data-ttu-id="9f6d5-136">Abilitare l'autenticazione moderna per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="9f6d5-136">Enable Modern authentication for your organization</span></span>

<span data-ttu-id="9f6d5-137">Tutte le applicazioni client di Office 2016 supportano MFA con ADAL (Active Directory Authentication Library).</span><span class="sxs-lookup"><span data-stu-id="9f6d5-137">All Office 2016 client applications support MFA through the use of the Active Directory Authentication Library (ADAL).</span></span> <span data-ttu-id="9f6d5-138">Questo significa che le password dell'app non sono necessarie per i client di Office 2016.</span><span class="sxs-lookup"><span data-stu-id="9f6d5-138">This means that app passwords aren't required for Office 2016 clients.</span></span> <span data-ttu-id="9f6d5-139">Tuttavia, è necessario assicurarsi che l'abbonamento a Office 365 sia abilitato per ADAL o per l'autenticazione moderna.</span><span class="sxs-lookup"><span data-stu-id="9f6d5-139">However, you need to make sure your Office 365 subscription is enabled for ADAL, or modern authentication.</span></span>

1. <span data-ttu-id="9f6d5-140">Per abilitare l'autenticazione moderna, nell'[interfaccia di amministrazione](https://go.microsoft.com/fwlink/p/?linkid=834822) selezionare **Impostazioni** \> **Impostazioni** e quindi nella scheda **Servizi** scegliere **Autenticazione moderna** dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="9f6d5-140">To enable modern authentication, from the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), select **Settings** \> **Settings** and then in the **Services** tab, choose **Modern authentication** from the list.</span></span>

2. <span data-ttu-id="9f6d5-141">Selezionare la casella **Abilita l'autenticazione moderna** nel pannello **Autenticazione moderna**.</span><span class="sxs-lookup"><span data-stu-id="9f6d5-141">Check the **Enable modern authentication** box in the **Modern authentication** panel.</span></span> 

    ![Pannello Autenticazione moderna con casella di controllo Abilita selezionata.](../../media/enablemodernauth.png)
    
## <a name="enable-multi-factor-authentication-for-your-organization"></a><span data-ttu-id="9f6d5-143">Abilitare l'autenticazione a più fattori per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="9f6d5-143">Enable multi-factor authentication for your organization</span></span>
    
1. <span data-ttu-id="9f6d5-144">Nell'interfaccia di [Amministrazione](https://go.microsoft.com/fwlink/p/?linkid=834822)selezionare **utenti** e **utenti attivi**.</span><span class="sxs-lookup"><span data-stu-id="9f6d5-144">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), select **Users** and **Active Users**.</span></span>

2. <span data-ttu-id="9f6d5-145">Nella sezione **utenti attivi** fare clic su autenticazione a più **fattori**.</span><span class="sxs-lookup"><span data-stu-id="9f6d5-145">In the **Active Users** section, Click on  **multi-factor authentication**.</span></span>

3. <span data-ttu-id="9f6d5-146">Nella pagina **autenticazione** a più fattori selezionare **utente** se si sta abilitando questa operazione per un utente o selezionare l' **aggiornamento in blocco** per abilitare più utenti.</span><span class="sxs-lookup"><span data-stu-id="9f6d5-146">On the **Multi-factor authentication** page, select **user** if you are enabling this for one user or select **Bulk Update** to enable multiple users.</span></span>

4. <span data-ttu-id="9f6d5-147">Fare clic su **Abilita** in **passaggi rapidi**.</span><span class="sxs-lookup"><span data-stu-id="9f6d5-147">CLick on **Enable** under **Quick Steps**.</span></span>

5. <span data-ttu-id="9f6d5-148">Nella finestra popup, fare clic su **Abilita autenticazione**a più fattori.</span><span class="sxs-lookup"><span data-stu-id="9f6d5-148">In the Pop-up window, Click on **Enable Multi-Factor Authentication**.</span></span>

<span data-ttu-id="9f6d5-149">Dopo aver configurato l'autenticazione a più fattori per l’organizzazione, agli utenti verrà richiesto di impostare la verifica in due passaggi sui loro dispositivi.</span><span class="sxs-lookup"><span data-stu-id="9f6d5-149">After you set up multi-factor authentication for your organization, your users will be required to set up two-step verification on their devices.</span></span> <span data-ttu-id="9f6d5-150">Per altre informazioni, vedere [Configurare la verifica in due passaggi per Office 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).</span><span class="sxs-lookup"><span data-stu-id="9f6d5-150">For more information, see [Set up 2-step verification for Office 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).</span></span>
    
> [!TIP]
> <span data-ttu-id="9f6d5-151">Per spiegare agli utenti come configurare l'app Authenticator, visitare [Usare Microsoft Authenticator con Office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411?ui=en-US&rs=en-US&ad=US#ID0EAADAAA=_Step_1).</span><span class="sxs-lookup"><span data-stu-id="9f6d5-151">To explain to your users how to set up the Authenticator app, please visit [Use Microsoft Authenticator with office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411?ui=en-US&rs=en-US&ad=US#ID0EAADAAA=_Step_1).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="9f6d5-152">Dal mese di agosto 2017 tutti i nuovi tenant di Office 365 che includono Skype for Business Online ed Exchange Online hanno l'autenticazione moderna abilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="9f6d5-152">As of August of 2017, all new Office 365 tenants that include Skype for Business online and Exchange online have modern authentication enabled by default.</span></span> <span data-ttu-id="9f6d5-153">Per controllare lo stato di autenticazione moderna di Skype for Business Online, è possibile usare PowerShell per Skype for Business Online con credenziali di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="9f6d5-153">To check your modern authentication status for Skype for Business online, you can use Skype for Business online PowerShell with Global Admin credentials.</span></span> <span data-ttu-id="9f6d5-154">Eseguire Get-CsOAuthConfiguration per controllare l'output di -ClientADALAuthOverride.</span><span class="sxs-lookup"><span data-stu-id="9f6d5-154">Run Get-CsOAuthConfiguration to check the output of -ClientADALAuthOverride.</span></span> <span data-ttu-id="9f6d5-155">Se -ClientADALAuthOverride è "Allowed" (Consentito), l'autenticazione moderna è attiva.</span><span class="sxs-lookup"><span data-stu-id="9f6d5-155">If -ClientADALAuthOverride is 'Allowed', modern authentication is on.</span></span>
<span data-ttu-id="9f6d5-156">Per controllare lo stato di autenticazione moderna per Exchange Online, vedere [Abilitare l'autenticazione moderna in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).</span><span class="sxs-lookup"><span data-stu-id="9f6d5-156">To check your MA status for Exchange Online, please visit [Enable modern authentication in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).</span></span>

## <a name="related-articles"></a><span data-ttu-id="9f6d5-157">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="9f6d5-157">Related articles</span></span>

[<span data-ttu-id="9f6d5-158">I 10 principali modi per proteggere i piani di Office 365 e Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="9f6d5-158">Top 10 ways to secure Office 365 and Microsoft 365 Business plans</span></span>](secure-your-business-data.md)

[<span data-ttu-id="9f6d5-159">Abilitare l'autenticazione moderna per Office 2013 nei dispositivi Windows</span><span class="sxs-lookup"><span data-stu-id="9f6d5-159">Enable Modern Authentication for Office 2013 on Windows devices</span></span>](enable-modern-authentication.md)
