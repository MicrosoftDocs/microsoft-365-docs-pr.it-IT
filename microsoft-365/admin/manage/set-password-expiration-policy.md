---
title: Impostare i criteri di scadenza delle password per l'organizzazione
f1.keywords:
- CSH
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
- GEA150
ms.assetid: 0f54736f-eb22-414c-8273-498a0918678f
description: Informazioni su come impostare i criteri di scadenza delle password per l'organizzazione nell'interfaccia di amministrazione di Microsoft 365.
ms.openlocfilehash: 59e9f4e36843d7c5d977a49d42ae0a11e9a2db25
ms.sourcegitcommit: a6625f76e8f19eebd9353ed70c00d32496ec06eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2020
ms.locfileid: "47362110"
---
# <a name="set-the-password-expiration-policy-for-your-organization"></a><span data-ttu-id="79366-103">Impostare i criteri di scadenza delle password per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="79366-103">Set the password expiration policy for your organization</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="79366-104">L'interfaccia di amministrazione sta cambiando.</span><span class="sxs-lookup"><span data-stu-id="79366-104">The admin center is changing.</span></span> <span data-ttu-id="79366-105">Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="79366-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

## <a name="before-you-begin"></a><span data-ttu-id="79366-106">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="79366-106">Before you begin</span></span>

<span data-ttu-id="79366-107">Questo articolo è per le persone che impostano criteri di scadenza delle password in un'azienda, un istituto di istruzione o un'organizzazione no profit.</span><span class="sxs-lookup"><span data-stu-id="79366-107">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="79366-108">Per completare questa procedura, è necessario accedere con l'account amministratore di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="79366-108">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> <span data-ttu-id="79366-109">[Che cos'è un account amministratore?](../admin-overview/admin-overview.md).</span><span class="sxs-lookup"><span data-stu-id="79366-109">[What's an admin account?](../admin-overview/admin-overview.md).</span></span>

<span data-ttu-id="79366-110">Per eseguire questa procedura, è necessario essere un [amministratore globale o delle password](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="79366-110">You must be a [global admin or password admin](../add-users/about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="79366-111">Gli utenti non hanno le autorizzazioni per impostare una password in modo che non scada mai.</span><span class="sxs-lookup"><span data-stu-id="79366-111">If you're a user, you don't have the permissions to set your password to never expire.</span></span> <span data-ttu-id="79366-112">Chiedere al supporto tecnico dell'azienda o dell'istituto di istruzione di completare la procedura descritta in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="79366-112">Ask your work or school technical support to do the steps in this article for you.</span></span>

<span data-ttu-id="79366-113">Gli amministratori possono fare in modo che la password di un utente scada dopo un determinato numero di giorni o che non scada mai.</span><span class="sxs-lookup"><span data-stu-id="79366-113">As an admin, you can make user passwords expire after a certain number of days, or set passwords to never expire.</span></span>

## <a name="set-password-expiration-policy"></a><span data-ttu-id="79366-114">Impostare il criterio di scadenza delle password</span><span class="sxs-lookup"><span data-stu-id="79366-114">Set password expiration policy</span></span>

> [!Tip]
> <span data-ttu-id="79366-115">Per impostazione predefinita, le password scadono dopo 90 giorni.</span><span class="sxs-lookup"><span data-stu-id="79366-115">By default, passwords are set to expire in 90 days.</span></span> <span data-ttu-id="79366-116">Ricerche correnti indicano che le modifiche obbligatorie delle password sono più dannose che utili.</span><span class="sxs-lookup"><span data-stu-id="79366-116">Current research strongly indicates that mandated password changes do more harm than good.</span></span> <span data-ttu-id="79366-117">Le modifiche frequenti inducono gli utenti a scegliere password più deboli, a riutilizzare le password o ad aggiornare le vecchie password in modi facilmente individuabili dai pirati informatici.</span><span class="sxs-lookup"><span data-stu-id="79366-117">They drive users to choose weaker passwords, re-use passwords, or update old passwords in ways that are easily guessed by hackers.</span></span> <span data-ttu-id="79366-118">Se si imposta la password in modo che non scada mai, è consigliabile abilitare l'[autenticazione a più fattori](../security-and-compliance/set-up-multi-factor-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="79366-118">If setting password to never expire, we recommend enabling [multi-factor authentication](../security-and-compliance/set-up-multi-factor-authentication.md).</span></span>

<span data-ttu-id="79366-119">Seguire la procedura seguente se si vogliono impostare le password degli utenti in modo che scadano dopo un determinato periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="79366-119">Follow the steps below if you want to set user passwords to expire after a specific amount of time.</span></span>
> [!IMPORTANT]
> <span data-ttu-id="79366-120">Solo gli [amministratori globali](../add-users/about-admin-roles.md) possono eseguire questa procedura.</span><span class="sxs-lookup"><span data-stu-id="79366-120">Only [global admins](../add-users/about-admin-roles.md) can perform these steps.</span></span>
  
1. <span data-ttu-id="79366-121">Nell'interfaccia di amministrazione passare a **Impostazioni** \> **Impostazioni organizzazione**.</span><span class="sxs-lookup"><span data-stu-id="79366-121">In the admin center, go to the **Settings** \> **Org Settings**.</span></span>

2. <span data-ttu-id="79366-122">Passare alla pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Sicurezza e privacy</a>.</span><span class="sxs-lookup"><span data-stu-id="79366-122">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Security & privacy</a> page.</span></span>
 <span data-ttu-id="79366-123">Gli utenti che non sono amministratori globali non visualizzeranno l'opzione Sicurezza e privacy.</span><span class="sxs-lookup"><span data-stu-id="79366-123">If you aren't a global admin, you won't see the Security and privacy option.</span></span>
  
3. <span data-ttu-id="79366-124">Selezionare **Criterio di scadenza delle password**.</span><span class="sxs-lookup"><span data-stu-id="79366-124">Select **Password expiration policy**.</span></span>
  
4. <span data-ttu-id="79366-125">Se non si vuole che gli utenti debbano cambiare le password, selezionare la casella di controllo accanto a **Impostare la scadenza delle password dopo un certo numero di giorni**.</span><span class="sxs-lookup"><span data-stu-id="79366-125">If you don't want users to have to change passwords, select the checkbox next to **Set user passwords to expire after a number of days**.</span></span>
  
5. <span data-ttu-id="79366-126">Digitare la frequenza con cui dovrebbero scadere le password.</span><span class="sxs-lookup"><span data-stu-id="79366-126">Type how often passwords should expire.</span></span> <span data-ttu-id="79366-127">Scegliere un numero di giorni compreso tra 14 e 730.</span><span class="sxs-lookup"><span data-stu-id="79366-127">Choose a number of days from 14 to 730.</span></span>
  
6. <span data-ttu-id="79366-128">Nella seconda casella digitare quando verranno avvisati gli utenti dell'imminente scadenza della password e poi selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="79366-128">In the second box type when users are notified that their password will expire, and then select **Save**.</span></span> <span data-ttu-id="79366-129">Scegliere un numero di giorni compreso tra 1 e 30.</span><span class="sxs-lookup"><span data-stu-id="79366-129">Choose a number of days from 1 to 30.</span></span>

7. <span data-ttu-id="79366-130">Alla scadenza della password dell'utente, viene visualizzata una notifica nell'angolo in basso a destra dello schermo.</span><span class="sxs-lookup"><span data-stu-id="79366-130">When the user's password expires, they'll get a notification that appears in the lower right corner of their screen.</span></span>
  
## <a name="important-things-you-need-to-know-about-the-password-expiration-feature"></a><span data-ttu-id="79366-131">Informazioni importanti sulla funzionalità di scadenza delle password</span><span class="sxs-lookup"><span data-stu-id="79366-131">Important things you need to know about the password expiration feature</span></span>

<span data-ttu-id="79366-132">Ecco alcune informazioni utili sul funzionamento di questa funzionalità a partire da gennaio 2018:</span><span class="sxs-lookup"><span data-stu-id="79366-132">Here are some things to know about how this feature currently works as of January 2018:</span></span>
  
- <span data-ttu-id="79366-p108">Chi usa solo l'app Outlook non sarà obbligato a reimpostare la password di Microsoft 365 fino alla relativa scadenza nella cache. Questo può avvenire diversi giorni dopo la data di scadenza effettiva. Non ci sono soluzioni alternative a livello di amministratore.</span><span class="sxs-lookup"><span data-stu-id="79366-p108">People who only use the Outlook app won't be forced to reset their Microsoft 365 password until it expires in the cache. This can be several days after the actual expiration date. There's no workaround for this at the admin level.</span></span>

- <span data-ttu-id="79366-p109">Gli utenti non ricevono una notifica tramite posta elettronica relativa alla scadenza della password dopo un determinato numero di giorni. Questa funzionalità è utile? **[Votare qui.](https://office365.uservoice.com/forums/273493-office-365-admin/suggestions/15028344-office-365-password-email-notification)**</span><span class="sxs-lookup"><span data-stu-id="79366-p109">Users do not get an email notification that their password is going to expire in X number of days. Do you want this feature? **[Vote here!](https://office365.uservoice.com/forums/273493-office-365-admin/suggestions/15028344-office-365-password-email-notification)**</span></span>

## <a name="prevent-last-password-from-being-used-again"></a><span data-ttu-id="79366-139">Impedire il riutilizzo dell'ultima password</span><span class="sxs-lookup"><span data-stu-id="79366-139">Prevent last password from being used again</span></span>

<span data-ttu-id="79366-140">In Active Directory (AD) locale è possibile impedire agli utenti di riciclare le vecchie password applicando la cronologia delle password.</span><span class="sxs-lookup"><span data-stu-id="79366-140">If you want to prevent your users from recycling old passwords, you can do so by enforcing password history in on-premises Active Directory (AD).</span></span> <span data-ttu-id="79366-141">Vedere [Creare criteri password personalizzati](https://docs.microsoft.com/azure/active-directory-domain-services/password-policy#create-a-custom-password-policy).</span><span class="sxs-lookup"><span data-stu-id="79366-141">See [Create a custom password policy](https://docs.microsoft.com/azure/active-directory-domain-services/password-policy#create-a-custom-password-policy).</span></span>

<span data-ttu-id="79366-142">In Azure AD, quando l'utente modifica una password, non è possibile usare di nuovo l'ultima password.</span><span class="sxs-lookup"><span data-stu-id="79366-142">In Azure AD, The last password can't be used again when the user changes a password.</span></span> <span data-ttu-id="79366-143">Il criterio password viene applicato a tutti gli account utente creati e gestiti direttamente in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="79366-143">The password policy is applied to all user accounts that are created and managed directly in Azure AD.</span></span> <span data-ttu-id="79366-144">Questo criterio password non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="79366-144">This password policy can't be modified.</span></span> <span data-ttu-id="79366-145">Vedere i [criteri per le password di Azure AD](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts).</span><span class="sxs-lookup"><span data-stu-id="79366-145">See [Azure AD password policies](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts).</span></span>

## <a name="synchronize-user-passwords-hashes-from-an-on-premises-active-directory-to-azure-ad-microsoft-365"></a><span data-ttu-id="79366-146">Sincronizzare gli hash delle password degli utenti da un server di Active Directory locale ad Azure Active Directory (Microsoft 365)</span><span class="sxs-lookup"><span data-stu-id="79366-146">Synchronize user passwords hashes from an on-premises Active Directory to Azure AD (Microsoft 365)</span></span>

<span data-ttu-id="79366-147">Questo articolo spiega come configurare i criteri di scadenza per gli utenti basati solo su cloud (Azure Active Directory).</span><span class="sxs-lookup"><span data-stu-id="79366-147">This article is for setting the expiration policy for cloud-only users (Azure AD).</span></span> <span data-ttu-id="79366-148">Non si applica agli utenti con identità ibride che usano la sincronizzazione dell'hash delle password, l'autenticazione pass-through o la federazione locale, ad esempio ADFS.</span><span class="sxs-lookup"><span data-stu-id="79366-148">It doesn't apply to hybrid identity users who use password hash sync, pass-through authentication, or on-premises federation like ADFS.</span></span>
  
<span data-ttu-id="79366-149">Per informazioni sulla sincronizzazione degli hash delle password utente da Active Directory locale ad Azure Active Directory, vedere [Implementare la sincronizzazione degli hash delle password con il servizio di sincronizzazione di Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).</span><span class="sxs-lookup"><span data-stu-id="79366-149">To learn how to synchronize user password hashes from on premises AD to Azure AD, see [Implement password hash synchronization with Azure AD Connect sync](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).</span></span>

## <a name="password-policies-and-account-restrictions-in-azure-active-directory"></a><span data-ttu-id="79366-150">Criteri per le password e restrizioni di Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="79366-150">Password policies and account restrictions in Azure Active Directory</span></span>

<span data-ttu-id="79366-151">È possibile configurare più criteri per le password e restrizioni in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="79366-151">You can set more password policies and restrictions in Azure active directory.</span></span> <span data-ttu-id="79366-152">Vedere [Criteri per le password e restrizioni di Azure Active Directory](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy) per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="79366-152">Check out [Password policies and account restrictions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy) for more info.</span></span>

## <a name="update-password-policy"></a><span data-ttu-id="79366-153">Aggiornare i criteri password</span><span class="sxs-lookup"><span data-stu-id="79366-153">Update password Policy</span></span>

<span data-ttu-id="79366-154">Il cmdlet Set-MsolPasswordPolicy aggiorna i criteri delle password di un dominio o di un tenant specifico.</span><span class="sxs-lookup"><span data-stu-id="79366-154">The Set-MsolPasswordPolicy cmdlet updates the password policy of a specified domain or tenant.</span></span> <span data-ttu-id="79366-155">Sono necessarie due impostazioni. La prima indica il periodo di validità di una password prima che debba essere cambiata e la seconda indica il numero di giorni prima della data di scadenza della password in cui si attiverà l'invio agli utenti della prima notifica della scadenza.</span><span class="sxs-lookup"><span data-stu-id="79366-155">Two settings are required; the first is to indicate the length of time that a password remains valid before it must be changed and the second is to indicate the number of days before the password expiration date that will trigger when users will receive their first notification that their password will soon expire.</span></span>

<span data-ttu-id="79366-156">Per informazioni su come aggiornare i criteri delle password per un dominio o un tenant specifico, vedere [Set-MsolPasswordPolicy](https://docs.microsoft.com/powershell/module/msonline/set-msolpasswordpolicy?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="79366-156">To learn how to update password policy for a specific domain or tenant, see [Set-MsolPasswordPolicy](https://docs.microsoft.com/powershell/module/msonline/set-msolpasswordpolicy?view=azureadps-1.0).</span></span>

## <a name="related-content"></a><span data-ttu-id="79366-157">Contenuti correlati</span><span class="sxs-lookup"><span data-stu-id="79366-157">Related content</span></span>

[<span data-ttu-id="79366-158">Consentire agli utenti di reimpostare le loro password</span><span class="sxs-lookup"><span data-stu-id="79366-158">Let users reset their own passwords</span></span>](../add-users/let-users-reset-passwords.md)

[<span data-ttu-id="79366-159">Reimpostare password</span><span class="sxs-lookup"><span data-stu-id="79366-159">Reset passwords</span></span>](../add-users/reset-passwords.md)