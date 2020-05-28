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
description: "Informazioni su come impostare i criteri di scadenza delle password per l'organizzazione nell'interfaccia di amministrazione di Microsoft 365. "
ms.openlocfilehash: a4d5f5240a6d4cca686b4809d05970b5e18b897f
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399579"
---
# <a name="set-the-password-expiration-policy-for-your-organization"></a><span data-ttu-id="ecb43-103">Impostare i criteri di scadenza delle password per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="ecb43-103">Set the password expiration policy for your organization</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="ecb43-104">L'interfaccia di amministrazione sta cambiando.</span><span class="sxs-lookup"><span data-stu-id="ecb43-104">The admin center is changing.</span></span> <span data-ttu-id="ecb43-105">Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="ecb43-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="ecb43-106">Questo articolo è per le persone che impostano criteri di scadenza delle password in un'azienda, un istituto di istruzione o un'organizzazione no profit.</span><span class="sxs-lookup"><span data-stu-id="ecb43-106">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span>  

<span data-ttu-id="ecb43-107">Gli utenti non hanno le autorizzazioni per impostare una password in modo che non scada mai.</span><span class="sxs-lookup"><span data-stu-id="ecb43-107">If you're a user, you don't have the permissions to set your password to never expire.</span></span> <span data-ttu-id="ecb43-108">Chiedere al supporto tecnico dell'azienda o dell'istituto di istruzione di completare la procedura descritta in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="ecb43-108">Ask your work or school technical support to do the steps in this article for you.</span></span>

<span data-ttu-id="ecb43-109">Gli amministratori possono fare in modo che la password di un utente scada dopo un determinato numero di giorni o che non scada mai.</span><span class="sxs-lookup"><span data-stu-id="ecb43-109">As an admin, you can make user passwords expire after a certain number of days, or set passwords to never expire.</span></span> 

> [!Tip]
> <span data-ttu-id="ecb43-110">Per impostazione predefinita, le password scadono dopo 90 giorni.</span><span class="sxs-lookup"><span data-stu-id="ecb43-110">By default, passwords are set to expire in 90 days.</span></span> <span data-ttu-id="ecb43-111">Ricerche correnti indicano che le modifiche obbligatorie delle password sono più dannose che utili.</span><span class="sxs-lookup"><span data-stu-id="ecb43-111">Current research strongly indicates that mandated password changes do more harm than good.</span></span> <span data-ttu-id="ecb43-112">Le modifiche frequenti inducono gli utenti a scegliere password più deboli, a riutilizzare le password o ad aggiornare le vecchie password in modi facilmente individuabili dai pirati informatici.</span><span class="sxs-lookup"><span data-stu-id="ecb43-112">They drive users to choose weaker passwords, re-use passwords, or update old passwords in ways that are easily guessed by hackers.</span></span> <span data-ttu-id="ecb43-113">Se si imposta la password in modo che non scada mai, è consigliabile abilitare l'[autenticazione a più fattori](../security-and-compliance/set-up-multi-factor-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="ecb43-113">If setting password to never expire, we recommend enabling [multi-factor authentication](../security-and-compliance/set-up-multi-factor-authentication.md).</span></span>

<span data-ttu-id="ecb43-114">Seguire la procedura seguente se si vogliono impostare le password degli utenti in modo che scadano dopo un determinato periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="ecb43-114">Follow the steps below if you want to set user passwords to expire after a specific amount of time.</span></span>
> [!IMPORTANT]
> <span data-ttu-id="ecb43-115">Solo gli [amministratori globali](../add-users/about-admin-roles.md) possono eseguire questa procedura.</span><span class="sxs-lookup"><span data-stu-id="ecb43-115">Only [global admins](../add-users/about-admin-roles.md) can perform these steps.</span></span>
  
1. <span data-ttu-id="ecb43-116">Nell'interfaccia di amministrazione passare a **Impostazioni** \> **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="ecb43-116">In the admin center, go to the **Settings** \> **Settings**.</span></span>

2. <span data-ttu-id="ecb43-117">Passare alla pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Sicurezza e privacy</a>.</span><span class="sxs-lookup"><span data-stu-id="ecb43-117">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Security & privacy</a> page.</span></span>
 <span data-ttu-id="ecb43-118">Gli utenti che non sono amministratori globali non visualizzeranno l'opzione Sicurezza e privacy.</span><span class="sxs-lookup"><span data-stu-id="ecb43-118">If you aren't a global admin, you won't see the Security and privacy option.</span></span>
  
3. <span data-ttu-id="ecb43-119">Selezionare **Criterio di scadenza delle password**.</span><span class="sxs-lookup"><span data-stu-id="ecb43-119">Select **Password expiration policy**.</span></span>
  
4. <span data-ttu-id="ecb43-120">Se non si vuole che gli utenti debbano cambiare le password, selezionare la casella di controllo accanto a **Impostare la scadenza delle password dopo un certo numero di giorni**.</span><span class="sxs-lookup"><span data-stu-id="ecb43-120">If you don't want users to have to change passwords, select the checkbox next to **Set user passwords to expire after a number of days**.</span></span>
  
5. <span data-ttu-id="ecb43-121">Digitare la frequenza con cui dovrebbero scadere le password.</span><span class="sxs-lookup"><span data-stu-id="ecb43-121">Type how often passwords should expire.</span></span> <span data-ttu-id="ecb43-122">Scegliere un numero di giorni compreso tra 14 e 730.</span><span class="sxs-lookup"><span data-stu-id="ecb43-122">Choose a number of days from 14 to 730.</span></span>
  
6. <span data-ttu-id="ecb43-123">Nella seconda casella digitare quando verranno avvisati gli utenti dell'imminente scadenza della password e poi selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ecb43-123">In the second box type when users are notified that their password will expire, and then select **Save**.</span></span> <span data-ttu-id="ecb43-124">Scegliere un numero di giorni compreso tra 1 e 30.</span><span class="sxs-lookup"><span data-stu-id="ecb43-124">Choose a number of days from 1 to 30.</span></span>
    
7. <span data-ttu-id="ecb43-125">Alla scadenza della password dell'utente, viene visualizzata una notifica nell'angolo in basso a destra dello schermo.</span><span class="sxs-lookup"><span data-stu-id="ecb43-125">When the user's password expires, they'll get a notification that appears in the lower right corner of their screen.</span></span>
  
## <a name="important-things-you-need-to-know-about-the-password-expiration-feature"></a><span data-ttu-id="ecb43-126">Informazioni importanti sulla funzionalità di scadenza delle password</span><span class="sxs-lookup"><span data-stu-id="ecb43-126">Important things you need to know about the password expiration feature</span></span>

<span data-ttu-id="ecb43-127">Ecco alcune informazioni utili sul funzionamento di questa funzionalità a partire da gennaio 2018:</span><span class="sxs-lookup"><span data-stu-id="ecb43-127">Here are some things to know about how this feature currently works as of January 2018:</span></span>
  
- <span data-ttu-id="ecb43-p107">Chi usa solo l'app Outlook non sarà obbligato a reimpostare la password di Microsoft 365 fino alla relativa scadenza nella cache. Questo può avvenire diversi giorni dopo la data di scadenza effettiva. Non ci sono soluzioni alternative a livello di amministratore.</span><span class="sxs-lookup"><span data-stu-id="ecb43-p107">People who only use the Outlook app won't be forced to reset their Microsoft 365 password until it expires in the cache. This can be several days after the actual expiration date. There's no workaround for this at the admin level.</span></span>
    
- <span data-ttu-id="ecb43-p108">Gli utenti non ricevono una notifica tramite posta elettronica relativa alla scadenza della password dopo un determinato numero di giorni. Questa funzionalità è utile? **[Votare qui.](https://office365.uservoice.com/forums/273493-office-365-admin/suggestions/15028344-office-365-password-email-notification)**</span><span class="sxs-lookup"><span data-stu-id="ecb43-p108">Users do not get an email notification that their password is going to expire in X number of days. Do you want this feature? **[Vote here!](https://office365.uservoice.com/forums/273493-office-365-admin/suggestions/15028344-office-365-password-email-notification)**</span></span>
    
## <a name="prevent-last-password-from-being-used-again"></a><span data-ttu-id="ecb43-134">Impedire il riutilizzo dell'ultima password</span><span class="sxs-lookup"><span data-stu-id="ecb43-134">Prevent last password from being used again</span></span>

<span data-ttu-id="ecb43-135">In Azure Active Directory è possibile impedire agli utenti di riciclare le vecchie password.</span><span class="sxs-lookup"><span data-stu-id="ecb43-135">If you want to prevent your users from recycling old passwords, you can do so in Azure AD.</span></span> <span data-ttu-id="ecb43-136">Vedere [Applicare la cronologia delle password](https://docs.microsoft.com/windows/security/threat-protection/security-policy-settings/enforce-password-history).</span><span class="sxs-lookup"><span data-stu-id="ecb43-136">See [Enforce password history](https://docs.microsoft.com/windows/security/threat-protection/security-policy-settings/enforce-password-history).</span></span>

<span data-ttu-id="ecb43-137">Inoltre, se un dipendente ha usato un dispositivo mobile per accedere a Microsoft 365, è possibile cancellare i dati del dispositivo per assicurarsi che la password non venga più memorizzata e riutilizzata nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ecb43-137">In addition, if an employee used a mobile device to access Microsoft 365, you can wipe it to ensure the password is no longer stored and recycled from there.</span></span> <span data-ttu-id="ecb43-138">Informazioni vedere [Cancellare i dati e bloccare il dispositivo mobile di un ex dipendente](https://docs.microsoft.com/office365/admin/add-users/remove-former-employee?view=o365-worldwide#wipe-and-block-a-former-employees-mobile-device).</span><span class="sxs-lookup"><span data-stu-id="ecb43-138">To learn more, see [Wipe and block a former employee's mobile device](https://docs.microsoft.com/office365/admin/add-users/remove-former-employee?view=o365-worldwide#wipe-and-block-a-former-employees-mobile-device).</span></span>


## <a name="synchronize-user-passwords-hashes-from-an-on-premises-active-directory-to-azure-ad-microsoft-365"></a><span data-ttu-id="ecb43-139">Sincronizzare gli hash delle password degli utenti da un server di Active Directory locale ad Azure Active Directory (Microsoft 365)</span><span class="sxs-lookup"><span data-stu-id="ecb43-139">Synchronize user passwords hashes from an on-premises Active Directory to Azure AD (Microsoft 365)</span></span>

<span data-ttu-id="ecb43-140">Questo articolo spiega come configurare i criteri di scadenza per gli utenti basati solo su cloud (Azure Active Directory).</span><span class="sxs-lookup"><span data-stu-id="ecb43-140">This article is for setting the expiration policy for cloud-only users (Azure AD).</span></span> <span data-ttu-id="ecb43-141">Non si applica agli utenti di identità ibride che usano la sincronizzazione degli hash delle password, l'autenticazione pass-through o la federazione locale, ad esempio ADFS.</span><span class="sxs-lookup"><span data-stu-id="ecb43-141">It doesn't apply to hybrid identity users who use password hash sync, pass-through authentication or on-premises federation like ADFS.</span></span>
  
<span data-ttu-id="ecb43-142">Per informazioni sulla sincronizzazione degli hash delle password utente da Active Directory locale ad Azure Active Directory, vedere [Implementare la sincronizzazione degli hash delle password con il servizio di sincronizzazione di Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).</span><span class="sxs-lookup"><span data-stu-id="ecb43-142">To learn how to synchronize user password hashes from on premises AD to Azure AD, see [Implement password hash synchronization with Azure AD Connect sync](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).</span></span>
