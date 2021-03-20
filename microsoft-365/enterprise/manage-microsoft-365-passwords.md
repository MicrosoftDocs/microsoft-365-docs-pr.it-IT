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
ms.openlocfilehash: 2062da49310121ec18f7ce21f523531f10d6df9b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905093"
---
# <a name="manage-microsoft-365-user-account-passwords"></a><span data-ttu-id="f7d0f-103">Gestire le password degli account utente di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f7d0f-103">Manage Microsoft 365 user account passwords</span></span>

<span data-ttu-id="f7d0f-104">*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="f7d0f-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="f7d0f-105">È possibile gestire le password degli account utente di Microsoft 365 in diversi modi, a seconda della configurazione dell'identità.</span><span class="sxs-lookup"><span data-stu-id="f7d0f-105">You can manage Microsoft 365 user account passwords in several different ways, depending on your identity configuration.</span></span> <span data-ttu-id="f7d0f-106">È possibile gestire gli account utente nell'interfaccia di amministrazione di [Microsoft 365,](../admin/add-users/index.yml)in Servizi di dominio Active Directory o nell'interfaccia di amministrazione di Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="f7d0f-106">You can manage user accounts in the [Microsoft 365 admin center](../admin/add-users/index.yml), in Active Directory Domain Services (AD DS), or in the Azure Active Directory (Azure AD) admin center.</span></span>

## <a name="plan-for-where-and-how-you-will-manage-your-user-account-passwords"></a><span data-ttu-id="f7d0f-107">Pianificare dove e come gestire le password degli account utente</span><span class="sxs-lookup"><span data-stu-id="f7d0f-107">Plan for where and how you will manage your user account passwords</span></span>

<span data-ttu-id="f7d0f-108">La posizione e la modalità di gestione degli account utente dipendono dal modello di identità che si desidera utilizzare per Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f7d0f-108">Where and how you can manage your user accounts depends on the identity model you want to use for your Microsoft 365.</span></span> <span data-ttu-id="f7d0f-109">I due modelli sono solo cloud e ibridi.</span><span class="sxs-lookup"><span data-stu-id="f7d0f-109">The two models are cloud-only and hybrid.</span></span>
  
### <a name="cloud-only"></a><span data-ttu-id="f7d0f-110">Solo cloud</span><span class="sxs-lookup"><span data-stu-id="f7d0f-110">Cloud-only</span></span>

<span data-ttu-id="f7d0f-111">È possibile gestire le password degli account utente in:</span><span class="sxs-lookup"><span data-stu-id="f7d0f-111">You manage user account passwords in:</span></span>

- [<span data-ttu-id="f7d0f-112">L'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f7d0f-112">The Microsoft 365 admin center</span></span>](../admin/add-users/index.yml)
- <span data-ttu-id="f7d0f-113">Interfaccia di amministrazione di Azure AD</span><span class="sxs-lookup"><span data-stu-id="f7d0f-113">The Azure AD admin center</span></span>
    
### <a name="hybrid"></a><span data-ttu-id="f7d0f-114">Ibrido</span><span class="sxs-lookup"><span data-stu-id="f7d0f-114">Hybrid</span></span>

<span data-ttu-id="f7d0f-115">Con l'identità ibrida, le password vengono archiviate in Servizi di dominio Active Directory, quindi è necessario utilizzare gli strumenti di Servizi di dominio Active Directory locali per gestire le password degli account utente.</span><span class="sxs-lookup"><span data-stu-id="f7d0f-115">With hybrid identity, passwords are stored in AD DS so you must use on-premises AD DS tools to manage user account passwords.</span></span> <span data-ttu-id="f7d0f-116">Anche quando si usa la sincronizzazione dell'hash delle password (PHS), in cui Azure AD archivia una versione con hash della versione già con hash in Servizi di dominio Active Directory, è necessario gestire le password in Servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f7d0f-116">Even when using Password Hash Synchronization (PHS), in which Azure AD stores a hashed version of the already hashed version in AD DS, you and users must manage their passwords in AD DS.</span></span>

<span data-ttu-id="f7d0f-117">Con [il writeback delle password,](#pw_writeback)gli utenti possono modificare le password di Servizi di dominio Active Directory tramite Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f7d0f-117">With [password writeback](#pw_writeback), your users can change their AD DS passwords through Azure AD.</span></span>

## <a name="prevent-bad-passwords"></a><span data-ttu-id="f7d0f-118">Impedire l'uso di password non consentite</span><span class="sxs-lookup"><span data-stu-id="f7d0f-118">Prevent bad passwords</span></span>

<span data-ttu-id="f7d0f-119">Per creare le password degli account utente, tutti gli utenti devono attenersi alla [Guida alle password di Microsoft](https://www.microsoft.com/research/publication/password-guidance).</span><span class="sxs-lookup"><span data-stu-id="f7d0f-119">All your users should be using [Microsoft's password guidance](https://www.microsoft.com/research/publication/password-guidance) to create their user account passwords.</span></span>

<span data-ttu-id="f7d0f-120">Per impedire agli utenti di creare password facilmente determinabili, usare la protezione password di Azure Active Directory, che usa sia un elenco di password non consentite globale che un elenco facoltativo di password non consentite personalizzato, specificato dall'utente.</span><span class="sxs-lookup"><span data-stu-id="f7d0f-120">To prevent users from creating an easily-determined password, use Azure AD password protection, which uses both a global banned password list and an optional custom banned password list that you specify.</span></span> <span data-ttu-id="f7d0f-121">Ad esempio, è possibile specificare condizioni specifiche per l'organizzazione, come:</span><span class="sxs-lookup"><span data-stu-id="f7d0f-121">For example, you can specify terms that are specific to your organization, such as:</span></span>

- <span data-ttu-id="f7d0f-122">Nomi di marchio</span><span class="sxs-lookup"><span data-stu-id="f7d0f-122">Brand names</span></span>
- <span data-ttu-id="f7d0f-123">Nomi di prodotto</span><span class="sxs-lookup"><span data-stu-id="f7d0f-123">Product names</span></span>
- <span data-ttu-id="f7d0f-124">Posizioni, ad esempio la sede centrale aziendale</span><span class="sxs-lookup"><span data-stu-id="f7d0f-124">Locations (for example, such as company headquarters)</span></span>
- <span data-ttu-id="f7d0f-125">Termini interni specifici della società</span><span class="sxs-lookup"><span data-stu-id="f7d0f-125">Company-specific internal terms</span></span>
- <span data-ttu-id="f7d0f-126">Abbreviazioni con significato aziendale specifico</span><span class="sxs-lookup"><span data-stu-id="f7d0f-126">Abbreviations that have specific company meaning</span></span>

<span data-ttu-id="f7d0f-127">È possibile vietare le password non valide [nel cloud](/azure/active-directory/authentication/concept-password-ban-bad) e per Servizi di dominio Active [Directory locale.](/azure/active-directory/authentication/concept-password-ban-bad-on-premises)</span><span class="sxs-lookup"><span data-stu-id="f7d0f-127">You can ban bad passwords [in the cloud](/azure/active-directory/authentication/concept-password-ban-bad) and for your [on-premises AD DS](/azure/active-directory/authentication/concept-password-ban-bad-on-premises).</span></span>

## <a name="simplify-user-sign-in"></a><span data-ttu-id="f7d0f-128">Semplificare l'accesso utente</span><span class="sxs-lookup"><span data-stu-id="f7d0f-128">Simplify user sign-in</span></span>

<span data-ttu-id="f7d0f-129">Azure AD Seamless Single Sign-On (Azure AD Seamless SSO) funziona con PHS e autenticazione Pass-Through (PTA), per consentire agli utenti di accedere ai servizi che usano account utente di Azure AD senza dover digitare le password e, in molti casi, i nomi utente.</span><span class="sxs-lookup"><span data-stu-id="f7d0f-129">Azure AD Seamless Single Sign-On (Azure AD Seamless SSO) works with PHS and Pass-Through Authentication (PTA), to allow your users to sign in to services that use Azure AD user accounts without having to type in their passwords, and in many cases, their usernames.</span></span> <span data-ttu-id="f7d0f-130">In questo modo gli utenti possono facilmente accedere alle applicazioni basate su cloud come Office 365, senza aver bisogno di componenti aggiuntivi in loco quali ad esempio server federativi di identità.</span><span class="sxs-lookup"><span data-stu-id="f7d0f-130">This gives your users easier access to cloud-based applications, such as Office 365, without needing any additional on-premises components such as identity federation servers.</span></span>

<span data-ttu-id="f7d0f-131">L'accesso SSO facile di Azure AD viene configurato con lo strumento Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="f7d0f-131">You configure Azure AD Seamless SSO with the Azure AD Connect tool.</span></span> <span data-ttu-id="f7d0f-132">Vedere le [istruzioni per configurare l'accesso SSO facile ad Azure AD](/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span><span class="sxs-lookup"><span data-stu-id="f7d0f-132">See the [instructions to configure Azure AD Seamless SSO](/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span></span>

<a name="pw_writeback"></a>
## <a name="simplify-password-updates-to-ad-ds"></a><span data-ttu-id="f7d0f-133">Semplificare gli aggiornamenti delle password in Servizi di dominio Active Directory</span><span class="sxs-lookup"><span data-stu-id="f7d0f-133">Simplify password updates to AD DS</span></span>

<span data-ttu-id="f7d0f-134">Con il writeback delle password, è possibile consentire agli utenti di reimpostare le password tramite Azure AD, che viene quindi replicato in Servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f7d0f-134">With password writeback, you can allow users to reset their passwords through Azure AD, which is then replicated to AD DS.</span></span> <span data-ttu-id="f7d0f-135">Gli utenti non devono accedere ai servizi di dominio Active Directory locali per aggiornare le password.</span><span class="sxs-lookup"><span data-stu-id="f7d0f-135">Users don’t need to access their on-premises AD DS to update their passwords.</span></span> <span data-ttu-id="f7d0f-136">Questo risulta particolarmente utile per gli utenti remoti o mobili che non dispongono di una connessione remota alla rete locale.</span><span class="sxs-lookup"><span data-stu-id="f7d0f-136">This is valuable to roaming or remote users who do not have a remote access connection to the on-premises network.</span></span>

<span data-ttu-id="f7d0f-137">Il writeback delle password è necessario per utilizzare al meglio le capacità di Azure AD Identity Protection, come la richiesta agli utenti di cambiare le password locali nel caso in cui sia stato rilevato un alto rischio di violazione dell'account.</span><span class="sxs-lookup"><span data-stu-id="f7d0f-137">Password writeback is required to fully utilize Azure AD Identity Protection capabilities, such as requiring users to change their on-premises passwords when there has been a high risk of account compromise detected.</span></span>

<span data-ttu-id="f7d0f-138">Per ulteriori informazioni e istruzioni di configurazione, vedere [Reimpostazione password self-service di Azure AD con writeback delle password](/azure/active-directory/active-directory-passwords-writeback).</span><span class="sxs-lookup"><span data-stu-id="f7d0f-138">For additional information and configuration instructions, see [Azure AD SSPR with password writeback](/azure/active-directory/active-directory-passwords-writeback).</span></span>

>[!Note]
><span data-ttu-id="f7d0f-p108">Eseguire l'aggiornamento all'ultima versione di Azure AD Connect per poter usufruire della migliore esperienza possibile e delle nuove caratteristiche appena rilasciate. Per ulteriori informazioni, vedere [Istallazione personalizzata di Azure AD Connect](/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).</span><span class="sxs-lookup"><span data-stu-id="f7d0f-p108">Upgrade to the latest version of Azure AD Connect to ensure the best possible experience and new features as they are released. For more information, see [Custom installation of Azure AD Connect](/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).</span></span>
>

## <a name="simplify-password-resets"></a><span data-ttu-id="f7d0f-141">Semplificare le reimpostazioni delle password</span><span class="sxs-lookup"><span data-stu-id="f7d0f-141">Simplify password resets</span></span>

<span data-ttu-id="f7d0f-142">La reimpostazione della password self-service consente agli utenti di reimpostare o sbloccare le password o gli account.</span><span class="sxs-lookup"><span data-stu-id="f7d0f-142">Self-service password reset (SSPR) allows users to reset or unlock their passwords or accounts.</span></span> <span data-ttu-id="f7d0f-143">Per segnalare abusi o usi impropri è possibile utilizzare la reportistica dettagliata, che tiene traccia degli accessi degli utenti al sistema, insieme alle notifiche.</span><span class="sxs-lookup"><span data-stu-id="f7d0f-143">To alert you to misuse or abuse, you can use the detailed reporting that tracks when users access the system, along with notifications.</span></span> <span data-ttu-id="f7d0f-144">È necessario abilitare il [writeback delle password](#pw_writeback) prima di poter distribuire le reimpostazioni delle password.</span><span class="sxs-lookup"><span data-stu-id="f7d0f-144">You must enable [password writeback](#pw_writeback) before you can deploy password resets.</span></span>

<span data-ttu-id="f7d0f-145">Vedere le [istruzioni per implementare la reimpostazione della password](/azure/active-directory/authentication/howto-sspr-deployment).</span><span class="sxs-lookup"><span data-stu-id="f7d0f-145">See the [instructions to roll out password reset](/azure/active-directory/authentication/howto-sspr-deployment).</span></span>