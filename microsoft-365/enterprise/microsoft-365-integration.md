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
description: In questo articolo vengono fornite informazioni su come integrare Microsoft 365 con i servizi directory esistenti e gli ambienti locali.
ms.openlocfilehash: 9c5e287ed4a440d1f62081a4c94e39f0f162b4dc
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384881"
---
# <a name="microsoft-365-integration-with-on-premises-environments"></a><span data-ttu-id="6a370-103">Integrazione di Microsoft 365 con ambienti locali</span><span class="sxs-lookup"><span data-stu-id="6a370-103">Microsoft 365 integration with on-premises environments</span></span>

<span data-ttu-id="6a370-104">*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.</span><span class="sxs-lookup"><span data-stu-id="6a370-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="6a370-105">È possibile integrare Microsoft 365 con i servizi di dominio Active Directory (AD DS) e con le installazioni locali di Exchange Server, Skype for Business Server 2015 o SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="6a370-105">You can integrate Microsoft 365 with your existing on-premises Active Directory Domain Services (AD DS) and with on-premises installations of Exchange Server, Skype for Business Server 2015, or SharePoint Server.</span></span>
  
 - <span data-ttu-id="6a370-106">Quando si integra servizi di dominio Active Directory, è possibile sincronizzare e gestire gli account utente per entrambi gli ambienti.</span><span class="sxs-lookup"><span data-stu-id="6a370-106">When you integrate AD DS, you can synchronize and manage user accounts for both environments.</span></span> <span data-ttu-id="6a370-107">È inoltre possibile aggiungere la sincronizzazione degli hash delle password (pH) o Single Sign-on (SSO), in modo che gli utenti possano accedere a entrambi gli ambienti con le credenziali locali.</span><span class="sxs-lookup"><span data-stu-id="6a370-107">You can also add password hash synchronization (PHS) or single sign-on (SSO) so users can log on to both environments with their on-premises credentials.</span></span>
 - <span data-ttu-id="6a370-108">Mediante l'integrazione con i prodotti server locali viene creato un ambiente ibrido.</span><span class="sxs-lookup"><span data-stu-id="6a370-108">When you integrate with on-premises server products, you create a hybrid environment.</span></span> <span data-ttu-id="6a370-109">Un ambiente ibrido può essere di aiuto durante la migrazione di utenti o informazioni a Microsoft 365 oppure è possibile continuare ad avere alcuni utenti o alcune informazioni in locale e altre nel cloud.</span><span class="sxs-lookup"><span data-stu-id="6a370-109">A hybrid environment can help as you migrate users or information to Microsoft 365, or you can continue to have some users or some information on-premises and some in the cloud.</span></span> <span data-ttu-id="6a370-110">Per ulteriori informazioni sugli ambienti ibridi, vedere [cloud ibrido](../solutions/cloud-architecture-models.md#hybrid).</span><span class="sxs-lookup"><span data-stu-id="6a370-110">For more information about hybrid environments, see [hybrid cloud](../solutions/cloud-architecture-models.md#hybrid).</span></span>

<span data-ttu-id="6a370-111">È inoltre possibile utilizzare i consulenti di Azure Active Directory (Azure AD) per le istruzioni di installazione personalizzate nell'interfaccia di amministrazione di Microsoft 365 (è necessario essere connessi a Microsoft 365):</span><span class="sxs-lookup"><span data-stu-id="6a370-111">You can also use the Azure Active Directory (Azure AD) advisors for customized setup guidance in the Microsoft 365 admin center (you must be signed in to Microsoft 365):</span></span>

- [<span data-ttu-id="6a370-112">Guida alla configurazione di Azure AD</span><span class="sxs-lookup"><span data-stu-id="6a370-112">Azure AD setup guide</span></span>](https://aka.ms/aadpguidance)
- [<span data-ttu-id="6a370-113">Sincronizzare gli utenti dalla directory dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="6a370-113">Sync users from your org's directory</span></span>](https://aka.ms/aadconnectpwsync)
- [<span data-ttu-id="6a370-114">Consulente per la distribuzione di Active Directory Federation Services (AD FS)</span><span class="sxs-lookup"><span data-stu-id="6a370-114">Active Directory Federation Services (AD FS) deployment advisor</span></span>](https://aka.ms/adfsguidance)
   
## <a name="before-you-begin"></a><span data-ttu-id="6a370-115">Informazioni preliminari</span><span class="sxs-lookup"><span data-stu-id="6a370-115">Before you begin</span></span>

<span data-ttu-id="6a370-116">Prima di integrare Microsoft 365 e un ambiente locale, è inoltre necessario eseguire la pianificazione della [rete e l'ottimizzazione delle prestazioni](network-planning-and-performance.md).</span><span class="sxs-lookup"><span data-stu-id="6a370-116">Before you integrate Microsoft 365 and an on-premises environment, you also need to do [network planning and performance tuning](network-planning-and-performance.md).</span></span> <span data-ttu-id="6a370-117">È anche opportuno conoscere i [modelli di identità](about-microsoft-365-identity.md).</span><span class="sxs-lookup"><span data-stu-id="6a370-117">You will also want to understand the available [identity models](about-microsoft-365-identity.md).</span></span> 

<span data-ttu-id="6a370-118">Vedere [gestire gli account microsoft 365](manage-microsoft-365-accounts.md) per un elenco degli strumenti che è possibile utilizzare per gestire gli account utente di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6a370-118">See [manage Microsoft 365 accounts](manage-microsoft-365-accounts.md) for a list of tools you can use to manage Microsoft 365 user accounts.</span></span> 
  
## <a name="integrate-microsoft-365-with-ad-ds"></a><span data-ttu-id="6a370-119">Integrazione di Microsoft 365 con servizi di dominio Active Directory</span><span class="sxs-lookup"><span data-stu-id="6a370-119">Integrate Microsoft 365 with AD DS</span></span>

<span data-ttu-id="6a370-120">Se si dispone di account utente esistenti in servizi di dominio Active Directory, non si desidera ricreare tutti gli account in Microsoft 365 e rischiare di introdurre differenze o errori tra gli ambienti.</span><span class="sxs-lookup"><span data-stu-id="6a370-120">If you have existing user accounts in AD DS, you don't want to re-create all of those accounts in Microsoft 365 and risk introducing differences or errors between the environments.</span></span> <span data-ttu-id="6a370-121">La sincronizzazione della directory consente di rispecchiare gli account tra gli ambienti locali e online.</span><span class="sxs-lookup"><span data-stu-id="6a370-121">Directory synchronization helps you mirror those accounts between your on-premises and online environments.</span></span> <span data-ttu-id="6a370-122">La sincronizzazione della directory evita agli utenti la necessità di ricordare nuove informazioni per ogni ambiente e all'amministratore di creare o aggiornare gli account due volte.</span><span class="sxs-lookup"><span data-stu-id="6a370-122">With directory synchronization, your users don't have to remember new information for each environment, and you don't have to create or update accounts twice.</span></span> <span data-ttu-id="6a370-123">Sarà necessario [preparare la directory locale per la](prepare-for-directory-synchronization.md) sincronizzazione della directory.</span><span class="sxs-lookup"><span data-stu-id="6a370-123">You will need to [prepare your on-premises directory](prepare-for-directory-synchronization.md) for directory synchronization.</span></span>
  
![Usare la sincronizzazione della directory per mantenere sincronizzate le informazioni degli account locali e di quelli online](../media/microsoft-365-integration/directory-synchronization.png)
  
<span data-ttu-id="6a370-125">Se si desidera che gli utenti siano in grado di accedere a Microsoft 365 con le credenziali locali, è anche possibile configurare SSO.</span><span class="sxs-lookup"><span data-stu-id="6a370-125">If you want users to be able to log on to Microsoft 365 with their on-premises credentials, you can also configure SSO.</span></span> <span data-ttu-id="6a370-126">Con SSO, Microsoft 365 è configurato per considerare attendibile l'ambiente locale per l'autenticazione degli utenti.</span><span class="sxs-lookup"><span data-stu-id="6a370-126">With SSO, Microsoft 365 is configured to trust the on-premises environment for user authentication.</span></span>
  
![Con Single Sign-On, lo stesso account è disponibile sia nell'ambiente locale che nell'ambiente online](../media/microsoft-365-integration/single-sign-on.png)

### <a name="directory-synchronization-with-or-without-password-hash-synchronization-or-pass-through-authentication-pta"></a><span data-ttu-id="6a370-128">Sincronizzazione della directory con o senza sincronizzazione dell'hash delle password o autenticazione pass-through (PTA)</span><span class="sxs-lookup"><span data-stu-id="6a370-128">Directory synchronization with or without password hash synchronization or pass-through authentication (PTA)</span></span>

<span data-ttu-id="6a370-129">Un utente accede all'ambiente locale con il proprio account utente (dominio\nomeutente).</span><span class="sxs-lookup"><span data-stu-id="6a370-129">A user logs on to their on-premises environment with their user account (domain\username).</span></span> <span data-ttu-id="6a370-130">Quando si accede a Microsoft 365, è necessario eseguire di nuovo l'accesso con l'account aziendale o dell'Istituto di istruzione (user@domain.com).</span><span class="sxs-lookup"><span data-stu-id="6a370-130">When they go to Microsoft 365, they must log on again with their work or school account (user@domain.com).</span></span> <span data-ttu-id="6a370-131">Il nome utente è lo stesso in entrambi gli ambienti.</span><span class="sxs-lookup"><span data-stu-id="6a370-131">The user name is the same in both environments.</span></span> <span data-ttu-id="6a370-132">Quando si aggiungono pH o PTA, l'utente ha la stessa password per entrambi gli ambienti, ma sarà necessario fornire tali credenziali quando si accede a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6a370-132">When you add PHS or PTA, the user has the same password for both environments, but will have to provide those credentials again when logging on to Microsoft 365.</span></span> <span data-ttu-id="6a370-133">La sincronizzazione della directory con pH è la sincronizzazione delle directory più comunemente utilizzata.</span><span class="sxs-lookup"><span data-stu-id="6a370-133">Directory synchronization with PHS is the most commonly used directory synchronization .</span></span>

<span data-ttu-id="6a370-134">Per configurare la sincronizzazione della directory, utilizzare Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="6a370-134">To set up directory synchronization, use Azure AD Connect.</span></span> <span data-ttu-id="6a370-135">Per istruzioni, vedere [configurare la sincronizzazione della directory per Microsoft 365](set-up-directory-synchronization.md) e [Azure ad Connect with Express Settings](https://go.microsoft.com/fwlink/p/?LinkId=698537).</span><span class="sxs-lookup"><span data-stu-id="6a370-135">For instructions, see [Set up directory synchronization for Microsoft 365](set-up-directory-synchronization.md) and [Azure AD Connect with express settings](https://go.microsoft.com/fwlink/p/?LinkId=698537).</span></span>

<span data-ttu-id="6a370-136">Per ulteriori informazioni, vedere [preparazione della sincronizzazione della directory a Microsoft 365](prepare-for-directory-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="6a370-136">Learn more about [preparing for directory synchronization to Microsoft 365](prepare-for-directory-synchronization.md).</span></span>

### <a name="directory-synchronization-with-sso"></a><span data-ttu-id="6a370-137">Sincronizzazione della directory con SSO</span><span class="sxs-lookup"><span data-stu-id="6a370-137">Directory synchronization with SSO</span></span>

<span data-ttu-id="6a370-138">Un utente accede all'ambiente locale con il proprio account utente.</span><span class="sxs-lookup"><span data-stu-id="6a370-138">A user logs on to their on-premises environment with their user account.</span></span> <span data-ttu-id="6a370-139">Quando si accede a Microsoft 365, sono connessi automaticamente oppure eseguono l'accesso utilizzando le stesse credenziali utilizzate per l'ambiente locale (dominio\nomeutente).</span><span class="sxs-lookup"><span data-stu-id="6a370-139">When they go to Microsoft 365, they are either logged on automatically, or they log on using the same credentials they use for their on-premises environment (domain\username).</span></span>

<span data-ttu-id="6a370-140">Per configurare SSO si usa anche Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="6a370-140">To set up SSO you also use Azure AD Connect.</span></span> <span data-ttu-id="6a370-141">Per istruzioni, vedere [Custom Installation of Azure ad Connect](https://go.microsoft.com/fwlink/p/?LinkID=698430).</span><span class="sxs-lookup"><span data-stu-id="6a370-141">For instructions, see [Custom installation of Azure AD Connect](https://go.microsoft.com/fwlink/p/?LinkID=698430).</span></span>

<span data-ttu-id="6a370-142">Per ulteriori informazioni, vedere [Single Sign-on](https://go.microsoft.com/fwlink/p/?LinkId=698604).</span><span class="sxs-lookup"><span data-stu-id="6a370-142">For more information, see [single sign-on](https://go.microsoft.com/fwlink/p/?LinkId=698604).</span></span>

## <a name="azure-ad-connect"></a><span data-ttu-id="6a370-143">Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="6a370-143">Azure AD Connect</span></span>

<span data-ttu-id="6a370-144">Azure AD Connect sostituisce le versioni precedenti degli strumenti di integrazione delle identità, come DirSync e Azure AD Sync. Se si desidera eseguire l'aggiornamento dalla sincronizzazione di Azure Active Directory ad Azure AD Connect, vedere [le istruzioni per l'aggiornamento](https://go.microsoft.com/fwlink/p/?LinkId=733240).</span><span class="sxs-lookup"><span data-stu-id="6a370-144">Azure AD Connect replaces older versions of identity integration tools such as DirSync and Azure AD Sync. If you want to update from Azure Active Directory Sync to Azure AD Connect, see [the upgrade instructions](https://go.microsoft.com/fwlink/p/?LinkId=733240).</span></span> 

## <a name="see-also"></a><span data-ttu-id="6a370-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6a370-145">See also</span></span>

[<span data-ttu-id="6a370-146">Panoramica di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="6a370-146">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)
