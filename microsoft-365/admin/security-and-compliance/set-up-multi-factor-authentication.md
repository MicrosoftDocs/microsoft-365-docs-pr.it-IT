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
ms.openlocfilehash: 5f468f040ca88ab4ab2bc198d0d7550bf2e7f4af
ms.sourcegitcommit: 8a88b7526e6a3a907f33a8567e0d25b74fe60d80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2020
ms.locfileid: "43204023"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="a5a61-103">Configurare l'autenticazione a più fattori</span><span class="sxs-lookup"><span data-stu-id="a5a61-103">Set up multi-factor authentication</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="a5a61-104">Se l'abbonamento o il processo è stato acquistato dopo il 21 ottobre 2019 e viene richiesto l'autenticazione a più fattori, le [impostazioni predefinite](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) per la sicurezza sono state abilitate automaticamente per l'abbonamento.</span><span class="sxs-lookup"><span data-stu-id="a5a61-104">If you purchased your subscription or trial after October 21, 2019, and you're unexpectedly prompted for multi-factor authentication (MFA), [security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) have been automatically enabled for your subscription.</span></span>

<span data-ttu-id="a5a61-105">Nei nuovi abbonamenti a Office 365 per le aziende o Microsoft 365 Business le impostazioni predefinite per la sicurezza sono attivate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="a5a61-105">Every new Office 365 for business or Microsoft 365 Business subscription will automatically have security defaults turned on.</span></span> <span data-ttu-id="a5a61-106">Questo significa che ogni utente dovrà configurare il master e installare l'app Microsoft Authenticator sul proprio dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="a5a61-106">This means that every user will have to set up MFA and install the Microsoft Authenticator app on their mobile device.</span></span> <span data-ttu-id="a5a61-107">Per altre informazioni, vedere [Configurare la verifica in due passaggi per Office 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).</span><span class="sxs-lookup"><span data-stu-id="a5a61-107">For more information, see [Set up 2-step verification for Office 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).</span></span>  

<span data-ttu-id="a5a61-108">I nove ruoli di amministratore seguenti dovranno eseguire delle autenticazioni aggiuntive ogni volta che eseguono l'accesso:</span><span class="sxs-lookup"><span data-stu-id="a5a61-108">The following nine administrator roles will be required to perform additional authentication every time they sign in:</span></span>
- <span data-ttu-id="a5a61-109">Amministratore globale</span><span class="sxs-lookup"><span data-stu-id="a5a61-109">Global administrator</span></span>
- <span data-ttu-id="a5a61-110">Amministratore di SharePoint</span><span class="sxs-lookup"><span data-stu-id="a5a61-110">SharePoint administrator</span></span>
- <span data-ttu-id="a5a61-111">Amministratore di Exchange</span><span class="sxs-lookup"><span data-stu-id="a5a61-111">Exchange administrator</span></span>
- <span data-ttu-id="a5a61-112">Amministratore di accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="a5a61-112">Conditional Access administrator</span></span>
- <span data-ttu-id="a5a61-113">Amministratore della sicurezza</span><span class="sxs-lookup"><span data-stu-id="a5a61-113">Security administrator</span></span>
- <span data-ttu-id="a5a61-114">Amministratore supporto tecnico o amministratore password:</span><span class="sxs-lookup"><span data-stu-id="a5a61-114">Helpdesk administrator or password administrator</span></span>
- <span data-ttu-id="a5a61-115">Amministratore fatturazione</span><span class="sxs-lookup"><span data-stu-id="a5a61-115">Billing administrator</span></span>
- <span data-ttu-id="a5a61-116">Amministratore utenti</span><span class="sxs-lookup"><span data-stu-id="a5a61-116">User administrator</span></span>
- <span data-ttu-id="a5a61-117">Amministratore dell'autenticazione</span><span class="sxs-lookup"><span data-stu-id="a5a61-117">Authentication administrator</span></span>

<span data-ttu-id="a5a61-118">Tutti gli altri utenti dovranno eseguire l'autenticazione aggiuntiva quando necessario.</span><span class="sxs-lookup"><span data-stu-id="a5a61-118">All other users will be asked to perform additional authentication when needed.</span></span> <span data-ttu-id="a5a61-119">Per altre informazioni, vedere [Che cosa sono le impostazioni predefinite per la sicurezza?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span><span class="sxs-lookup"><span data-stu-id="a5a61-119">For more information, see [What are security defaults?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span></span>

> [!NOTE]
> <span data-ttu-id="a5a61-120">È necessario essere un amministratore globale di Office 365 per impostare o modificare l'AMF.</span><span class="sxs-lookup"><span data-stu-id="a5a61-120">You must be an Office 365 global admin to set up or modify MFA.</span></span> <br><br>
> <span data-ttu-id="a5a61-121">Se non si usa la nuova interfaccia di amministrazione di Microsoft 365, è possibile attivarla selezionando l'opzione **Prova la nuova interfaccia di amministrazione** che si trova nella parte superiore della home page.</span><span class="sxs-lookup"><span data-stu-id="a5a61-121">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

<span data-ttu-id="a5a61-122">Se in precedenza è stata configurata l'autenticazione a più fattori con criteri di base [è necessario disattivare quest'ultimi e attivare le impostazioni predefinite per la sicurezza](#move-from-baseline-policies-to-security-defaults).</span><span class="sxs-lookup"><span data-stu-id="a5a61-122">If you have previously set up MFA with baseline policies, [you must turn them off and turn on security defaults](#move-from-baseline-policies-to-security-defaults).</span></span> <span data-ttu-id="a5a61-123">Tuttavia, se si dispone di Microsoft 365 business o l'abbonamento include [Azure Active Directory Premium P1 o Azure Active Directory Premium P2](https://azure.microsoft.com/pricing/details/active-directory/), è anche possibile configurare i criteri di [accesso condizionale](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) .</span><span class="sxs-lookup"><span data-stu-id="a5a61-123">However, if you have Microsoft 365 Business or your subscription includes [Azure Active Directory Premium P1 or Azure Active Directory Premium P2](https://azure.microsoft.com/pricing/details/active-directory/), you can also set up [Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies.</span></span> <span data-ttu-id="a5a61-124">Per utilizzare i criteri di accesso condizionale, è necessario verificare che [l'autenticazione moderna](#enable-modern-authentication-for-your-organization) sia abilitata.</span><span class="sxs-lookup"><span data-stu-id="a5a61-124">To use conditional access policies, you need to make sure [modern authentication](#enable-modern-authentication-for-your-organization) is enabled.</span></span>

> [!TIP]
> <span data-ttu-id="a5a61-125">Per spiegare agli utenti come configurare l'app Authenticator, visitare [Usare Microsoft Authenticator con Office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411?ui=en-US&rs=en-US&ad=US#ID0EAADAAA=_Step_1).</span><span class="sxs-lookup"><span data-stu-id="a5a61-125">To explain to your users how to set up the Authenticator app, please visit [Use Microsoft Authenticator with office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411?ui=en-US&rs=en-US&ad=US#ID0EAADAAA=_Step_1).</span></span>

## <a name="manage-security-defaults"></a><span data-ttu-id="a5a61-126">Gestire le impostazioni predefinite per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="a5a61-126">Manage security defaults</span></span>

1. <span data-ttu-id="a5a61-127">Accedere all'[interfaccia di amministrazione](https://go.microsoft.com/fwlink/p/?linkid=834822) con le credenziali di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="a5a61-127">Sign in to [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822) with your Global admin credentials.</span></span>
2. <span data-ttu-id="a5a61-128">Passare alle [Proprietà di Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="a5a61-128">Go to [Azure Active Directory Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>

3. <span data-ttu-id="a5a61-129">Nella parte inferiore della pagina scegliere **Gestire le impostazioni predefinite per la sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="a5a61-129">At the bottom of the page, choose **Manage Security defaults**.</span></span>
4. <span data-ttu-id="a5a61-130">Scegliere **Sì** per abilitare le impostazioni predefinite per la sicurezza o **No** per disabilitare le impostazioni predefinite per la sicurezza e quindi scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="a5a61-130">Choose **Yes** to enable security defaults or **No** to disable security defaults, and then choose **Save**.</span></span>

## <a name="move-from-baseline-policies-to-security-defaults"></a><span data-ttu-id="a5a61-131">Passare dai criteri di base alle impostazioni predefinite per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="a5a61-131">Move from baseline policies to security defaults</span></span>

1. <span data-ttu-id="a5a61-132">Nell'interfaccia di [Amministrazione](https://go.microsoft.com/fwlink/p/?linkid=834822), selezionare **Mostra tutto**, quindi **Azure Active Directory** in interfaccia di **Amministrazione**.</span><span class="sxs-lookup"><span data-stu-id="a5a61-132">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), select **Show all**, and then **Azure Active Directory** under **Admin centers**.</span></span>

2. <span data-ttu-id="a5a61-133">Nell'interfaccia di **amministrazione di Azure Active Directory** scegliere**protezione**di **Azure Active Directory** > .</span><span class="sxs-lookup"><span data-stu-id="a5a61-133">In the  **Azure Active Directory admin center** choose **Azure Active Directory** > **Security**.</span></span>

3. <span data-ttu-id="a5a61-134">Sulla **sicurezza | Pagina introduttiva** , scegliere **accesso condizionale**.</span><span class="sxs-lookup"><span data-stu-id="a5a61-134">On the **Security | Getting started** page, choose **Conditional Access**.</span></span> 

4. <span data-ttu-id="a5a61-135">Nella pagina **Criteri di accesso condizionale al portale di Azure** selezionare ogni criterio di base **Attivato** e impostarlo su **Disattivato**.</span><span class="sxs-lookup"><span data-stu-id="a5a61-135">On the **Azure portal Conditional Access - Policies** page,  choose each Baseline policy that is **On**, and set them to **Off**.</span></span>
5. <span data-ttu-id="a5a61-136">Passare alla pagina [Proprietà di Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="a5a61-136">Go to [Azure Active Directory Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) page.</span></span>
6. <span data-ttu-id="a5a61-137">Nella parte inferiore della pagina scegliere **Gestire le impostazioni predefinite per la sicurezza**e nel riquadro **Abilitare le impostazioni predefinite per la sicurezza** impostare **Abilita le impostazioni predefinite per la sicurezza** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="a5a61-137">On the bottom of the page, choose **Manage Security defaults**, and in the **Enable Security defaults** pane, set **Enable Security defaults** toggle to **Yes**.</span></span> 

## <a name="enable-modern-authentication-for-your-organization"></a><span data-ttu-id="a5a61-138">Abilitare l'autenticazione moderna per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="a5a61-138">Enable Modern authentication for your organization</span></span>

<span data-ttu-id="a5a61-139">Tutte le applicazioni client di Office 2016 supportano MFA con ADAL (Active Directory Authentication Library).</span><span class="sxs-lookup"><span data-stu-id="a5a61-139">All Office 2016 client applications support MFA through the use of the Active Directory Authentication Library (ADAL).</span></span> <span data-ttu-id="a5a61-140">Questo significa che le password dell'app non sono necessarie per i client di Office 2016.</span><span class="sxs-lookup"><span data-stu-id="a5a61-140">This means that app passwords aren't required for Office 2016 clients.</span></span> <span data-ttu-id="a5a61-141">Tuttavia, è necessario assicurarsi che l'abbonamento a Office 365 sia abilitato per ADAL o per l'autenticazione moderna.</span><span class="sxs-lookup"><span data-stu-id="a5a61-141">However, you need to make sure your Office 365 subscription is enabled for ADAL, or modern authentication.</span></span>

1. <span data-ttu-id="a5a61-142">Per abilitare l'autenticazione moderna, nell'[interfaccia di amministrazione](https://go.microsoft.com/fwlink/p/?linkid=834822) selezionare **Impostazioni** \> **Impostazioni** e quindi nella scheda **Servizi** scegliere **Autenticazione moderna** dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="a5a61-142">To enable modern authentication, from the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), select **Settings** \> **Settings** and then in the **Services** tab, choose **Modern authentication** from the list.</span></span>

2. <span data-ttu-id="a5a61-143">Selezionare la casella **Abilita l'autenticazione moderna** nel pannello **Autenticazione moderna**.</span><span class="sxs-lookup"><span data-stu-id="a5a61-143">Check the **Enable modern authentication** box in the **Modern authentication** panel.</span></span> 

    ![Pannello Autenticazione moderna con casella di controllo Abilita selezionata.](../../media/enablemodernauth.png)
    
> [!IMPORTANT]
> <span data-ttu-id="a5a61-145">Dal mese di agosto 2017 tutti i nuovi tenant di Office 365 che includono Skype for Business Online ed Exchange Online hanno l'autenticazione moderna abilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="a5a61-145">As of August of 2017, all new Office 365 tenants that include Skype for Business online and Exchange online have modern authentication enabled by default.</span></span> <span data-ttu-id="a5a61-146">Per controllare lo stato di autenticazione moderna di Skype for Business Online, è possibile usare PowerShell per Skype for Business Online con credenziali di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="a5a61-146">To check your modern authentication status for Skype for Business online, you can use Skype for Business online PowerShell with Global Admin credentials.</span></span> <span data-ttu-id="a5a61-147">Eseguire Get-CsOAuthConfiguration per controllare l'output di -ClientADALAuthOverride.</span><span class="sxs-lookup"><span data-stu-id="a5a61-147">Run Get-CsOAuthConfiguration to check the output of -ClientADALAuthOverride.</span></span> <span data-ttu-id="a5a61-148">Se -ClientADALAuthOverride è "Allowed" (Consentito), l'autenticazione moderna è attiva.</span><span class="sxs-lookup"><span data-stu-id="a5a61-148">If -ClientADALAuthOverride is 'Allowed', modern authentication is on.</span></span>
<span data-ttu-id="a5a61-149">Per controllare lo stato di autenticazione moderna per Exchange Online, vedere [Abilitare l'autenticazione moderna in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).</span><span class="sxs-lookup"><span data-stu-id="a5a61-149">To check your MA status for Exchange Online, please visit [Enable modern authentication in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).</span></span>

## <a name="related-articles"></a><span data-ttu-id="a5a61-150">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="a5a61-150">Related articles</span></span>

[<span data-ttu-id="a5a61-151">I 10 principali modi per proteggere i piani di Office 365 e Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="a5a61-151">Top 10 ways to secure Office 365 and Microsoft 365 Business plans</span></span>](secure-your-business-data.md)

[<span data-ttu-id="a5a61-152">Abilitare l'autenticazione moderna per Office 2013 nei dispositivi Windows</span><span class="sxs-lookup"><span data-stu-id="a5a61-152">Enable Modern Authentication for Office 2013 on Windows devices</span></span>](enable-modern-authentication.md)
