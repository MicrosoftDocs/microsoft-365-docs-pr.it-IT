---
title: Gestire le password degli account utente di Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: Informazioni su come gestire le password degli account utente di Microsoft 365.
ms.openlocfilehash: af64002ad54b517a6e8f0b687a00d6bed9ab0214
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328510"
---
# <a name="manage-microsoft-365-user-account-passwords"></a><span data-ttu-id="9f8ef-103">Gestire le password degli account utente di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9f8ef-103">Manage Microsoft 365 user account passwords</span></span>

<span data-ttu-id="9f8ef-104">*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.</span><span class="sxs-lookup"><span data-stu-id="9f8ef-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="9f8ef-105">È possibile gestire le password degli account utente di Microsoft 365 in diversi modi, a seconda della configurazione dell'identità.</span><span class="sxs-lookup"><span data-stu-id="9f8ef-105">You can manage Microsoft 365 user account passwords in several different ways, depending on your identity configuration.</span></span> <span data-ttu-id="9f8ef-106">È possibile gestire gli account utente nell'interfaccia di [amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users/), in servizi di dominio Active Directory (ad DS) o nell'interfaccia di amministrazione di Azure Active Directory (Azure ad).</span><span class="sxs-lookup"><span data-stu-id="9f8ef-106">You can manage user accounts in the [Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/add-users/), in Active Directory Domain Services (AD DS), or in the Azure Active Directory (Azure AD) admin center.</span></span>

## <a name="plan-for-where-and-how-you-will-manage-your-user-account-passwords"></a><span data-ttu-id="9f8ef-107">Pianificare la posizione e la modalità di gestione delle password degli account utente</span><span class="sxs-lookup"><span data-stu-id="9f8ef-107">Plan for where and how you will manage your user account passwords</span></span>

<span data-ttu-id="9f8ef-108">Il percorso e la modalità di gestione degli account utente dipendono dal modello di identità che si desidera utilizzare per Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9f8ef-108">Where and how you can manage your user accounts depends on the identity model you want to use for your Microsoft 365.</span></span> <span data-ttu-id="9f8ef-109">I due modelli sono solo basati sul cloud e ibridi.</span><span class="sxs-lookup"><span data-stu-id="9f8ef-109">The two models are cloud-only and hybrid.</span></span>
  
### <a name="cloud-only"></a><span data-ttu-id="9f8ef-110">Solo cloud</span><span class="sxs-lookup"><span data-stu-id="9f8ef-110">Cloud-only</span></span>

<span data-ttu-id="9f8ef-111">È possibile gestire le password degli account utente in:</span><span class="sxs-lookup"><span data-stu-id="9f8ef-111">You manage user account passwords in:</span></span>

- [<span data-ttu-id="9f8ef-112">L'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9f8ef-112">The Microsoft 365 admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/)
- <span data-ttu-id="9f8ef-113">Interfaccia di amministrazione di Azure AD</span><span class="sxs-lookup"><span data-stu-id="9f8ef-113">The Azure AD admin center</span></span>
    
### <a name="hybrid"></a><span data-ttu-id="9f8ef-114">Ibrido</span><span class="sxs-lookup"><span data-stu-id="9f8ef-114">Hybrid</span></span>

<span data-ttu-id="9f8ef-115">Con l'identità ibrida, le password vengono archiviate in servizi di dominio Active Directory, pertanto è necessario utilizzare gli strumenti di AD DS locali per gestire le password degli account utente.</span><span class="sxs-lookup"><span data-stu-id="9f8ef-115">With hybrid identity, passwords are stored in AD DS so you must use on-premises AD DS tools to manage user account passwords.</span></span> <span data-ttu-id="9f8ef-116">Anche quando si utilizza la sincronizzazione degli hash delle password (pH), in cui Azure AD archivia una versione con hash della versione già sottoposto a hash in servizi di dominio Active Directory, è necessario che gli utenti gestiscano le proprie password in servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9f8ef-116">Even when using Password Hash Synchronization (PHS), in which Azure AD stores a hashed version of the already hashed version in AD DS, you and users must manage their passwords in AD DS.</span></span>

<span data-ttu-id="9f8ef-117">Con il [writeback delle password](#pw_writeback), gli utenti possono modificare le password di servizi di dominio Active Directory tramite Azure ad.</span><span class="sxs-lookup"><span data-stu-id="9f8ef-117">With [password writeback](#pw_writeback), your users can change their AD DS passwords through Azure AD.</span></span>

## <a name="prevent-bad-passwords"></a><span data-ttu-id="9f8ef-118">Impedire l'uso di password non consentite</span><span class="sxs-lookup"><span data-stu-id="9f8ef-118">Prevent bad passwords</span></span>

<span data-ttu-id="9f8ef-119">Per creare le password degli account utente, tutti gli utenti devono attenersi alla [Guida alle password di Microsoft](https://www.microsoft.com/research/publication/password-guidance).</span><span class="sxs-lookup"><span data-stu-id="9f8ef-119">All your users should be using [Microsoft's password guidance](https://www.microsoft.com/research/publication/password-guidance) to create their user account passwords.</span></span>

<span data-ttu-id="9f8ef-120">Per impedire agli utenti di creare password facilmente determinabili, usare la protezione password di Azure Active Directory, che usa sia un elenco di password non consentite globale che un elenco facoltativo di password non consentite personalizzato, specificato dall'utente.</span><span class="sxs-lookup"><span data-stu-id="9f8ef-120">To prevent users from creating an easily-determined password, use Azure AD password protection, which uses both a global banned password list and an optional custom banned password list that you specify.</span></span> <span data-ttu-id="9f8ef-121">Ad esempio, è possibile specificare condizioni specifiche per l'organizzazione, come:</span><span class="sxs-lookup"><span data-stu-id="9f8ef-121">For example, you can specify terms that are specific to your organization, such as:</span></span>

- <span data-ttu-id="9f8ef-122">Nomi di marchio</span><span class="sxs-lookup"><span data-stu-id="9f8ef-122">Brand names</span></span>
- <span data-ttu-id="9f8ef-123">Nomi di prodotto</span><span class="sxs-lookup"><span data-stu-id="9f8ef-123">Product names</span></span>
- <span data-ttu-id="9f8ef-124">Posizioni, ad esempio la sede centrale aziendale</span><span class="sxs-lookup"><span data-stu-id="9f8ef-124">Locations (for example, such as company headquarters)</span></span>
- <span data-ttu-id="9f8ef-125">Termini interni specifici della società</span><span class="sxs-lookup"><span data-stu-id="9f8ef-125">Company-specific internal terms</span></span>
- <span data-ttu-id="9f8ef-126">Abbreviazioni con significato aziendale specifico</span><span class="sxs-lookup"><span data-stu-id="9f8ef-126">Abbreviations that have specific company meaning</span></span>

<span data-ttu-id="9f8ef-127">È possibile vietare le password non valide [nel cloud](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) e per il servizio di [dominio Active Directory locale](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises).</span><span class="sxs-lookup"><span data-stu-id="9f8ef-127">You can ban bad passwords [in the cloud](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) and for your [on-premises AD DS](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises).</span></span>

## <a name="simplify-user-sign-in"></a><span data-ttu-id="9f8ef-128">Semplificare l'accesso utente</span><span class="sxs-lookup"><span data-stu-id="9f8ef-128">Simplify user sign-in</span></span>

<span data-ttu-id="9f8ef-129">Azure AD seamless Single Sign-on (Azure AD seamless SSO) è compatibile con il pH e l'autenticazione pass-through (PTA), per consentire agli utenti di accedere ai servizi che utilizzano gli account utente di Azure AD senza dover digitare le password e, in molti casi, i nomi utente.</span><span class="sxs-lookup"><span data-stu-id="9f8ef-129">Azure AD Seamless Single Sign-On (Azure AD Seamless SSO) works with PHS and Pass-Through Authentication (PTA), to allow your users to sign in to services that use Azure AD user accounts without having to type in their passwords, and in many cases, their usernames.</span></span> <span data-ttu-id="9f8ef-130">In questo modo gli utenti possono facilmente accedere alle applicazioni basate su cloud come Office 365, senza aver bisogno di componenti aggiuntivi in loco quali ad esempio server federativi di identità.</span><span class="sxs-lookup"><span data-stu-id="9f8ef-130">This gives your users easier access to cloud-based applications, such as Office 365, without needing any additional on-premises components such as identity federation servers.</span></span>

<span data-ttu-id="9f8ef-131">L'accesso SSO facile di Azure AD viene configurato con lo strumento Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="9f8ef-131">You configure Azure AD Seamless SSO with the Azure AD Connect tool.</span></span> <span data-ttu-id="9f8ef-132">Vedere le [istruzioni per configurare l'accesso SSO facile ad Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span><span class="sxs-lookup"><span data-stu-id="9f8ef-132">See the [instructions to configure Azure AD Seamless SSO](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span></span>

<a name="pw_writeback"></a>
## <a name="simplify-password-updates-to-ad-ds"></a><span data-ttu-id="9f8ef-133">Semplificare gli aggiornamenti delle password in servizi di dominio Active Directory</span><span class="sxs-lookup"><span data-stu-id="9f8ef-133">Simplify password updates to AD DS</span></span>

<span data-ttu-id="9f8ef-134">Con il writeback delle password, è possibile consentire agli utenti di reimpostare le proprie password tramite Azure AD, che viene quindi replicato in servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9f8ef-134">With password writeback, you can allow users to reset their passwords through Azure AD, which is then replicated to AD DS.</span></span> <span data-ttu-id="9f8ef-135">Gli utenti non devono accedere al servizio di dominio Active Directory locale per aggiornare le password.</span><span class="sxs-lookup"><span data-stu-id="9f8ef-135">Users don’t need to access their on-premises AD DS to update their passwords.</span></span> <span data-ttu-id="9f8ef-136">Questo risulta particolarmente utile per gli utenti remoti o mobili che non dispongono di una connessione remota alla rete locale.</span><span class="sxs-lookup"><span data-stu-id="9f8ef-136">This is valuable to roaming or remote users who do not have a remote access connection to the on-premises network.</span></span>

<span data-ttu-id="9f8ef-137">Il writeback delle password è necessario per utilizzare al meglio le capacità di Azure AD Identity Protection, come la richiesta agli utenti di cambiare le password locali nel caso in cui sia stato rilevato un alto rischio di violazione dell'account.</span><span class="sxs-lookup"><span data-stu-id="9f8ef-137">Password writeback is required to fully utilize Azure AD Identity Protection capabilities, such as requiring users to change their on-premises passwords when there has been a high risk of account compromise detected.</span></span>

<span data-ttu-id="9f8ef-138">Per ulteriori informazioni e istruzioni di configurazione, vedere [Reimpostazione password self-service di Azure AD con writeback delle password](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback).</span><span class="sxs-lookup"><span data-stu-id="9f8ef-138">For additional information and configuration instructions, see [Azure AD SSPR with password writeback](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback).</span></span>

>[!Note]
><span data-ttu-id="9f8ef-p108">Eseguire l'aggiornamento all'ultima versione di Azure AD Connect per poter usufruire della migliore esperienza possibile e delle nuove caratteristiche appena rilasciate. Per ulteriori informazioni, vedere [Istallazione personalizzata di Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).</span><span class="sxs-lookup"><span data-stu-id="9f8ef-p108">Upgrade to the latest version of Azure AD Connect to ensure the best possible experience and new features as they are released. For more information, see [Custom installation of Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).</span></span>
>

## <a name="simplify-password-resets"></a><span data-ttu-id="9f8ef-141">Semplificare le reimpostazioni delle password</span><span class="sxs-lookup"><span data-stu-id="9f8ef-141">Simplify password resets</span></span>

<span data-ttu-id="9f8ef-142">La reimpostazione della password in modalità self-service (SSPR) consente agli utenti di reimpostare o sbloccare le password o gli account.</span><span class="sxs-lookup"><span data-stu-id="9f8ef-142">Self-service password reset (SSPR) allows users to reset or unlock their passwords or accounts.</span></span> <span data-ttu-id="9f8ef-143">Per segnalare abusi o usi impropri è possibile utilizzare la reportistica dettagliata, che tiene traccia degli accessi degli utenti al sistema, insieme alle notifiche.</span><span class="sxs-lookup"><span data-stu-id="9f8ef-143">To alert you to misuse or abuse, you can use the detailed reporting that tracks when users access the system, along with notifications.</span></span> <span data-ttu-id="9f8ef-144">È necessario abilitare il [writeback delle password](#pw_writeback) prima di poter distribuire le reimpostazioni delle password.</span><span class="sxs-lookup"><span data-stu-id="9f8ef-144">You must enable [password writeback](#pw_writeback) before you can deploy password resets.</span></span>

<span data-ttu-id="9f8ef-145">Vedere le [istruzioni per implementare la reimpostazione della password](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment).</span><span class="sxs-lookup"><span data-stu-id="9f8ef-145">See the [instructions to roll out password reset](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment).</span></span>

