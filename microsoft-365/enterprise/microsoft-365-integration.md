---
title: Integrazione di Microsoft 365 con ambienti locali
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- Ent_O365
search.appverid:
- MET150
- LYN150
- SPS150
- MOE150
- MED150
ms.assetid: 263faf8d-aa21-428b-aed3-2021837a4b65
description: In questo articolo viene illustrato come integrare Microsoft 365 con i servizi directory esistenti e gli ambienti locali.
ms.openlocfilehash: c0453b7685254ccbbb301a17749fe48549fae78d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923967"
---
# <a name="microsoft-365-integration-with-on-premises-environments"></a><span data-ttu-id="c0361-103">Integrazione di Microsoft 365 con ambienti locali</span><span class="sxs-lookup"><span data-stu-id="c0361-103">Microsoft 365 integration with on-premises environments</span></span>

<span data-ttu-id="c0361-104">*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="c0361-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="c0361-105">È possibile integrare Microsoft 365 con Servizi di dominio Active Directory locale esistente e con le installazioni locali di Exchange Server, Skype for Business Server 2015 o SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="c0361-105">You can integrate Microsoft 365 with your existing on-premises Active Directory Domain Services (AD DS) and with on-premises installations of Exchange Server, Skype for Business Server 2015, or SharePoint Server.</span></span>
  
 - <span data-ttu-id="c0361-106">Quando si integra Servizi di dominio Active Directory, è possibile sincronizzare e gestire gli account utente per entrambi gli ambienti.</span><span class="sxs-lookup"><span data-stu-id="c0361-106">When you integrate AD DS, you can synchronize and manage user accounts for both environments.</span></span> <span data-ttu-id="c0361-107">È inoltre possibile aggiungere la sincronizzazione dell'hash delle password (PHS) o single sign-on (SSO) in modo che gli utenti possano accedere a entrambi gli ambienti con le proprie credenziali locali.</span><span class="sxs-lookup"><span data-stu-id="c0361-107">You can also add password hash synchronization (PHS) or single sign-on (SSO) so users can log on to both environments with their on-premises credentials.</span></span>
 - <span data-ttu-id="c0361-108">Mediante l'integrazione con i prodotti server locali viene creato un ambiente ibrido.</span><span class="sxs-lookup"><span data-stu-id="c0361-108">When you integrate with on-premises server products, you create a hybrid environment.</span></span> <span data-ttu-id="c0361-109">Un ambiente ibrido può essere utile quando si esegue la migrazione di utenti o informazioni a Microsoft 365 oppure è possibile continuare ad avere alcuni utenti o alcune informazioni in locale e altre nel cloud.</span><span class="sxs-lookup"><span data-stu-id="c0361-109">A hybrid environment can help as you migrate users or information to Microsoft 365, or you can continue to have some users or some information on-premises and some in the cloud.</span></span> <span data-ttu-id="c0361-110">Per ulteriori informazioni sugli ambienti ibridi, vedere [cloud ibrido.](../solutions/cloud-architecture-models.md#hybrid)</span><span class="sxs-lookup"><span data-stu-id="c0361-110">For more information about hybrid environments, see [hybrid cloud](../solutions/cloud-architecture-models.md#hybrid).</span></span>

<span data-ttu-id="c0361-111">È inoltre possibile usare gli advisor di Azure Active Directory (Azure AD) per istruzioni di configurazione personalizzate nell'interfaccia di amministrazione di Microsoft 365 (è necessario accedere a Microsoft 365):</span><span class="sxs-lookup"><span data-stu-id="c0361-111">You can also use the Azure Active Directory (Azure AD) advisors for customized setup guidance in the Microsoft 365 admin center (you must be signed in to Microsoft 365):</span></span>

- [<span data-ttu-id="c0361-112">Guida alla configurazione di Azure AD</span><span class="sxs-lookup"><span data-stu-id="c0361-112">Azure AD setup guide</span></span>](https://aka.ms/aadpguidance)
- [<span data-ttu-id="c0361-113">Sincronizzare gli utenti dalla directory dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="c0361-113">Sync users from your org's directory</span></span>](https://aka.ms/aadconnectpwsync)
- [<span data-ttu-id="c0361-114">Advisor per la distribuzione di Active Directory Federation Services (AD FS)</span><span class="sxs-lookup"><span data-stu-id="c0361-114">Active Directory Federation Services (AD FS) deployment advisor</span></span>](https://aka.ms/adfsguidance)
   
## <a name="before-you-begin"></a><span data-ttu-id="c0361-115">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="c0361-115">Before you begin</span></span>

<span data-ttu-id="c0361-116">Prima di integrare Microsoft 365 e un ambiente locale, è inoltre necessario eseguire la pianificazione della rete e l'ottimizzazione [delle prestazioni.](network-planning-and-performance.md)</span><span class="sxs-lookup"><span data-stu-id="c0361-116">Before you integrate Microsoft 365 and an on-premises environment, you also need to do [network planning and performance tuning](network-planning-and-performance.md).</span></span> <span data-ttu-id="c0361-117">È anche opportuno conoscere i [modelli di identità](about-microsoft-365-identity.md).</span><span class="sxs-lookup"><span data-stu-id="c0361-117">You will also want to understand the available [identity models](about-microsoft-365-identity.md).</span></span> 

<span data-ttu-id="c0361-118">Per un elenco degli strumenti che è possibile utilizzare per gestire gli account utente di [Microsoft 365,](manage-microsoft-365-accounts.md) vedere manage Microsoft 365 accounts.</span><span class="sxs-lookup"><span data-stu-id="c0361-118">See [manage Microsoft 365 accounts](manage-microsoft-365-accounts.md) for a list of tools you can use to manage Microsoft 365 user accounts.</span></span> 
  
## <a name="integrate-microsoft-365-with-ad-ds"></a><span data-ttu-id="c0361-119">Integrare Microsoft 365 con Servizi di dominio Active Directory</span><span class="sxs-lookup"><span data-stu-id="c0361-119">Integrate Microsoft 365 with AD DS</span></span>

<span data-ttu-id="c0361-120">Se si dispone di account utente esistenti in Servizi di dominio Active Directory, non si desidera creare di nuovo tutti questi account in Microsoft 365 e rischiare di introdurre differenze o errori tra gli ambienti.</span><span class="sxs-lookup"><span data-stu-id="c0361-120">If you have existing user accounts in AD DS, you don't want to re-create all of those accounts in Microsoft 365 and risk introducing differences or errors between the environments.</span></span> <span data-ttu-id="c0361-121">La sincronizzazione della directory consente di eseguire il mirroring di tali account tra gli ambienti locali e online.</span><span class="sxs-lookup"><span data-stu-id="c0361-121">Directory synchronization helps you mirror those accounts between your on-premises and online environments.</span></span> <span data-ttu-id="c0361-122">La sincronizzazione della directory evita agli utenti la necessità di ricordare nuove informazioni per ogni ambiente e all'amministratore di creare o aggiornare gli account due volte.</span><span class="sxs-lookup"><span data-stu-id="c0361-122">With directory synchronization, your users don't have to remember new information for each environment, and you don't have to create or update accounts twice.</span></span> <span data-ttu-id="c0361-123">Sarà necessario preparare la [directory locale](prepare-for-directory-synchronization.md) per la sincronizzazione della directory.</span><span class="sxs-lookup"><span data-stu-id="c0361-123">You will need to [prepare your on-premises directory](prepare-for-directory-synchronization.md) for directory synchronization.</span></span>
  
![Usare la sincronizzazione della directory per mantenere sincronizzate le informazioni degli account locali e di quelli online](../media/microsoft-365-integration/directory-synchronization.png)
  
<span data-ttu-id="c0361-125">Se si desidera che gli utenti possano accedere a Microsoft 365 con le proprie credenziali locali, è anche possibile configurare SSO.</span><span class="sxs-lookup"><span data-stu-id="c0361-125">If you want users to be able to log on to Microsoft 365 with their on-premises credentials, you can also configure SSO.</span></span> <span data-ttu-id="c0361-126">Con SSO, Microsoft 365 è configurato per considerare attendibile l'ambiente locale per l'autenticazione utente.</span><span class="sxs-lookup"><span data-stu-id="c0361-126">With SSO, Microsoft 365 is configured to trust the on-premises environment for user authentication.</span></span>
  
![Con Single Sign-On, lo stesso account è disponibile sia nell'ambiente locale che nell'ambiente online](../media/microsoft-365-integration/single-sign-on.png)

### <a name="directory-synchronization-with-or-without-password-hash-synchronization-or-pass-through-authentication-pta"></a><span data-ttu-id="c0361-128">Sincronizzazione della directory con o senza sincronizzazione dell'hash delle password o autenticazione pass-through (PTA)</span><span class="sxs-lookup"><span data-stu-id="c0361-128">Directory synchronization with or without password hash synchronization or pass-through authentication (PTA)</span></span>

<span data-ttu-id="c0361-129">Un utente accede all'ambiente locale con il proprio account utente (dominio\nomeutente).</span><span class="sxs-lookup"><span data-stu-id="c0361-129">A user logs on to their on-premises environment with their user account (domain\username).</span></span> <span data-ttu-id="c0361-130">Quando passano a Microsoft 365, devono accedere di nuovo con il proprio account aziendale o dell'istituto di istruzione (user@domain.com).</span><span class="sxs-lookup"><span data-stu-id="c0361-130">When they go to Microsoft 365, they must log on again with their work or school account (user@domain.com).</span></span> <span data-ttu-id="c0361-131">Il nome utente è lo stesso in entrambi gli ambienti.</span><span class="sxs-lookup"><span data-stu-id="c0361-131">The user name is the same in both environments.</span></span> <span data-ttu-id="c0361-132">Quando si aggiunge PHS o PTA, l'utente ha la stessa password per entrambi gli ambienti, ma dovrà fornire di nuovo tali credenziali quando accede a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c0361-132">When you add PHS or PTA, the user has the same password for both environments, but will have to provide those credentials again when logging on to Microsoft 365.</span></span> <span data-ttu-id="c0361-133">La sincronizzazione della directory con PHS è la sincronizzazione della directory più comune.</span><span class="sxs-lookup"><span data-stu-id="c0361-133">Directory synchronization with PHS is the most commonly used directory synchronization .</span></span>

<span data-ttu-id="c0361-134">Per configurare la sincronizzazione della directory, usare Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="c0361-134">To set up directory synchronization, use Azure AD Connect.</span></span> <span data-ttu-id="c0361-135">Per istruzioni, vedere [Configurare la sincronizzazione della directory per Microsoft 365](set-up-directory-synchronization.md) e [Azure AD Connect con impostazioni rapide.](/azure/active-directory/hybrid/how-to-connect-install-express)</span><span class="sxs-lookup"><span data-stu-id="c0361-135">For instructions, see [Set up directory synchronization for Microsoft 365](set-up-directory-synchronization.md) and [Azure AD Connect with express settings](/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

<span data-ttu-id="c0361-136">Ulteriori informazioni sulla [preparazione per la sincronizzazione della directory con Microsoft 365](prepare-for-directory-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="c0361-136">Learn more about [preparing for directory synchronization to Microsoft 365](prepare-for-directory-synchronization.md).</span></span>

### <a name="directory-synchronization-with-sso"></a><span data-ttu-id="c0361-137">Sincronizzazione della directory con SSO</span><span class="sxs-lookup"><span data-stu-id="c0361-137">Directory synchronization with SSO</span></span>

<span data-ttu-id="c0361-138">Un utente accede all'ambiente locale con il proprio account utente.</span><span class="sxs-lookup"><span data-stu-id="c0361-138">A user logs on to their on-premises environment with their user account.</span></span> <span data-ttu-id="c0361-139">Quando si accede a Microsoft 365, l'accesso viene eseguito automaticamente oppure l'accesso viene eseguito con le stesse credenziali utilizzate per l'ambiente locale (dominio\nomeutente).</span><span class="sxs-lookup"><span data-stu-id="c0361-139">When they go to Microsoft 365, they are either logged on automatically, or they log on using the same credentials they use for their on-premises environment (domain\username).</span></span>

<span data-ttu-id="c0361-140">Per configurare SSO si usa anche Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="c0361-140">To set up SSO you also use Azure AD Connect.</span></span> <span data-ttu-id="c0361-141">Per istruzioni, vedere [Installazione personalizzata di Azure AD Connect.](/azure/active-directory/hybrid/how-to-connect-install-custom)</span><span class="sxs-lookup"><span data-stu-id="c0361-141">For instructions, see [Custom installation of Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-custom).</span></span>

<span data-ttu-id="c0361-142">Per ulteriori informazioni, vedere [Single #A0](/azure/active-directory/manage-apps/what-is-single-sign-on).</span><span class="sxs-lookup"><span data-stu-id="c0361-142">For more information, see [single sign-on](/azure/active-directory/manage-apps/what-is-single-sign-on).</span></span>

## <a name="azure-ad-connect"></a><span data-ttu-id="c0361-143">Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="c0361-143">Azure AD Connect</span></span>

<span data-ttu-id="c0361-144">Azure AD Connect sostituisce le versioni precedenti degli strumenti di integrazione delle identità come DirSync e Azure AD Sync. Se si desidera eseguire l'aggiornamento da Azure Active Directory Sync ad Azure AD Connect, vedere [le istruzioni per l'aggiornamento.](/azure/active-directory/hybrid/how-to-dirsync-upgrade-get-started)</span><span class="sxs-lookup"><span data-stu-id="c0361-144">Azure AD Connect replaces older versions of identity integration tools such as DirSync and Azure AD Sync. If you want to update from Azure Active Directory Sync to Azure AD Connect, see [the upgrade instructions](/azure/active-directory/hybrid/how-to-dirsync-upgrade-get-started).</span></span> 

## <a name="see-also"></a><span data-ttu-id="c0361-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c0361-145">See also</span></span>

[<span data-ttu-id="c0361-146">Panoramica di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="c0361-146">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)