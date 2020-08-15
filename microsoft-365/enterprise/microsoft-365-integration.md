---
title: Integrazione di Microsoft 365 con ambienti locali
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 10/08/2019
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
ms.openlocfilehash: 46f0fab6396dd1db82524ea1aeedc6894ce7ab70
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691516"
---
# <a name="microsoft-365-integration-with-on-premises-environments"></a><span data-ttu-id="023ad-103">Integrazione di Microsoft 365 con ambienti locali</span><span class="sxs-lookup"><span data-stu-id="023ad-103">Microsoft 365 integration with on-premises environments</span></span>

<span data-ttu-id="023ad-104">*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="023ad-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="023ad-105">È possibile integrare Microsoft 365 con i servizi directory esistenti e con un'installazione locale di Exchange Server, Skype for Business Server 2015 o SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="023ad-105">You can integrate Microsoft 365 with your existing directory services and with an on-premises installation of Exchange Server, Skype for Business Server 2015, or SharePoint Server.</span></span>
  
 - <span data-ttu-id="023ad-106">Eseguendo l'integrazione con i servizi directory, è possibile sincronizzare e gestire gli account utente di entrambi gli ambienti.</span><span class="sxs-lookup"><span data-stu-id="023ad-106">When you integrate with directory services, you can synchronize and manage user accounts for both environments.</span></span> <span data-ttu-id="023ad-107">È anche possibile aggiungere la sincronizzazione dell'hash delle password o Single Sign-On (SSO) per consentire agli utenti di accedere a entrambi gli ambienti con le proprie credenziali locali.</span><span class="sxs-lookup"><span data-stu-id="023ad-107">You can also add password hash synchronization or single sign-on (SSO) so users can log on to both environments with their on-premises credentials.</span></span>
 - <span data-ttu-id="023ad-108">Mediante l'integrazione con i prodotti server locali viene creato un ambiente ibrido.</span><span class="sxs-lookup"><span data-stu-id="023ad-108">When you integrate with on-premises server products, you create a hybrid environment.</span></span> <span data-ttu-id="023ad-109">Un ambiente ibrido può essere di aiuto durante la migrazione di utenti o informazioni a Microsoft 365 oppure è possibile continuare ad avere alcuni utenti o alcune informazioni in locale e altre nel cloud.</span><span class="sxs-lookup"><span data-stu-id="023ad-109">A hybrid environment can help as you migrate users or information to Microsoft 365, or you can continue to have some users or some information on-premises and some in the cloud.</span></span> <span data-ttu-id="023ad-110">Per altre informazioni sugli ambienti ibridi, vedere [Panoramica sul cloud ibrido](https://docs.microsoft.com/Office365/Enterprise/hybrid-cloud-overview).</span><span class="sxs-lookup"><span data-stu-id="023ad-110">For more information about hybrid environments, see [Hybrid cloud overview](https://docs.microsoft.com/Office365/Enterprise/hybrid-cloud-overview).</span></span>

<span data-ttu-id="023ad-111">È inoltre possibile utilizzare i consulenti di Azure Active Directory (Azure AD) per le istruzioni di installazione personalizzate (è necessario essere connessi a Microsoft 365):</span><span class="sxs-lookup"><span data-stu-id="023ad-111">You can also use the Azure Active Directory (Azure AD) advisors for customized setup guidance (you must be signed in to Microsoft 365):</span></span>

- [<span data-ttu-id="023ad-112">Sincronizzare gli utenti dalla directory dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="023ad-112">Sync users from your org's directory</span></span>](https://aka.ms/aadconnectpwsync)
- [<span data-ttu-id="023ad-113">Assistente distribuzione di AD FS</span><span class="sxs-lookup"><span data-stu-id="023ad-113">AD FS deployment advisor</span></span>](https://aka.ms/adfsguidance)
- [<span data-ttu-id="023ad-114">Guida alla configurazione di Azure AD</span><span class="sxs-lookup"><span data-stu-id="023ad-114">Azure AD setup guide</span></span>](https://aka.ms/aadpguidance)
   
## <a name="before-you-begin"></a><span data-ttu-id="023ad-115">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="023ad-115">Before you begin</span></span>

<span data-ttu-id="023ad-116">Prima di integrare Microsoft 365 e un ambiente locale, è inoltre necessario partecipare alla [pianificazione della rete e all'ottimizzazione delle prestazioni](network-planning-and-performance.md).</span><span class="sxs-lookup"><span data-stu-id="023ad-116">Before you integrate Microsoft 365 and an on-premises environment, you also need to attend to [network planning and performance tuning](network-planning-and-performance.md).</span></span> <span data-ttu-id="023ad-117">È anche opportuno conoscere i [modelli di identità](about-microsoft-365-identity.md).</span><span class="sxs-lookup"><span data-stu-id="023ad-117">You will also want to understand the available [identity models](about-microsoft-365-identity.md).</span></span> 

<span data-ttu-id="023ad-118">Vedere [dove gestire gli account di microsoft 365](manage-microsoft-365-accounts.md) per un elenco di strumenti che è possibile utilizzare per gestire gli utenti e gli account di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="023ad-118">See [where to manage Microsoft 365 accounts](manage-microsoft-365-accounts.md) for a list of tools you can use to manage Microsoft 365 users and accounts.</span></span> 
  
## <a name="integrate-microsoft-365-with-directory-services"></a><span data-ttu-id="023ad-119">Integrazione di Microsoft 365 con i servizi directory</span><span class="sxs-lookup"><span data-stu-id="023ad-119">Integrate Microsoft 365 with directory services</span></span>
<span data-ttu-id="023ad-120">Se si dispone di account utente esistenti in una directory locale, non si vuole ricreare tutti gli account in Microsoft 365 e rischiare di introdurre differenze o errori tra gli ambienti.</span><span class="sxs-lookup"><span data-stu-id="023ad-120">If you have existing user accounts in an on-premises directory, you don't want to re-create all of those accounts in Microsoft 365 and risk introducing differences or errors between the environments.</span></span> <span data-ttu-id="023ad-121">La sincronizzazione della directory consente di eseguire il mirroring degli account tra l'ambiente online e quello locale.</span><span class="sxs-lookup"><span data-stu-id="023ad-121">Directory synchronization helps you mirror those accounts between your online and on-premises environments.</span></span> <span data-ttu-id="023ad-122">La sincronizzazione della directory evita agli utenti la necessità di ricordare nuove informazioni per ogni ambiente e all'amministratore di creare o aggiornare gli account due volte.</span><span class="sxs-lookup"><span data-stu-id="023ad-122">With directory synchronization, your users don't have to remember new information for each environment, and you don't have to create or update accounts twice.</span></span> <span data-ttu-id="023ad-123">Sarà necessario [preparare la directory locale per la](prepare-for-directory-synchronization.md) sincronizzazione della directory.</span><span class="sxs-lookup"><span data-stu-id="023ad-123">You will need to [prepare your on-premises directory](prepare-for-directory-synchronization.md) for directory synchronization.</span></span>
  
![Usare la sincronizzazione della directory per mantenere sincronizzate le informazioni degli account locali e di quelli online](../media/a64af0d0-9be6-46b1-8727-277e683abf5e.png)
  
<span data-ttu-id="023ad-125">Se si desidera che gli utenti siano in grado di accedere a Microsoft 365 con le credenziali locali, è anche possibile configurare SSO.</span><span class="sxs-lookup"><span data-stu-id="023ad-125">If you want users to be able to log on to Microsoft 365 with their on-premises credentials, you can also configure SSO.</span></span> <span data-ttu-id="023ad-126">Con SSO, Microsoft 365 è configurato per considerare attendibile l'ambiente locale per l'autenticazione degli utenti.</span><span class="sxs-lookup"><span data-stu-id="023ad-126">With SSO, Microsoft 365 is configured to trust the on-premises environment for user authentication.</span></span>
  
![Con Single Sign-On, lo stesso account è disponibile sia nell'ambiente locale che nell'ambiente online](../media/d76235f2-8a53-405e-b8ef-dfa4cfc208b8.png)
  
<span data-ttu-id="023ad-128">Tecniche di gestione degli account utente diverse offrono agli utenti esperienze diverse, come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="023ad-128">Different user account management techniques provide different experiences for your users, as shown in the following table.</span></span>
 
### <a name="directory-synchronization-with-or-without-password-hash-synchronization-or-pass-through-authentication"></a><span data-ttu-id="023ad-129">Sincronizzazione della directory con o senza sincronizzazione dell'hash delle password o autenticazione pass-through</span><span class="sxs-lookup"><span data-stu-id="023ad-129">Directory synchronization with or without password hash synchronization or pass-through authentication</span></span>

<span data-ttu-id="023ad-130">Un utente accede all'ambiente locale con il proprio account utente (dominio\nomeutente).</span><span class="sxs-lookup"><span data-stu-id="023ad-130">A user logs on to their on-premises environment with their user account (domain\username).</span></span> <span data-ttu-id="023ad-131">Quando si accede a Microsoft 365, è necessario eseguire di nuovo l'accesso con l'account aziendale o dell'Istituto di istruzione (user@domain.com).</span><span class="sxs-lookup"><span data-stu-id="023ad-131">When they go to Microsoft 365, they must log on again with their work or school account (user@domain.com).</span></span> <span data-ttu-id="023ad-132">Il nome utente è lo stesso in entrambi gli ambienti.</span><span class="sxs-lookup"><span data-stu-id="023ad-132">The user name is the same in both environments.</span></span> <span data-ttu-id="023ad-133">Quando si aggiunge l'autenticazione hash della password o pass-through, l'utente ha la stessa password per entrambi gli ambienti, ma sarà necessario fornire tali credenziali quando si accede a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="023ad-133">When you add password hash sync or pass-through authentication, the user has the same password for both environments, but will have to provide those credentials again when logging on to Microsoft 365.</span></span> <span data-ttu-id="023ad-134">La sincronizzazione della directory con la sincronizzazione dell'hash delle password è lo scenario più di frequente.</span><span class="sxs-lookup"><span data-stu-id="023ad-134">Directory synchronization with password hash sync is the most commonly used directory sync scenario.</span></span>

<span data-ttu-id="023ad-135">Per configurare la sincronizzazione della directory, usare Azure Active Directory Connect.</span><span class="sxs-lookup"><span data-stu-id="023ad-135">To set up directory synchronization, use Azure Active Directory Connect.</span></span> <span data-ttu-id="023ad-136">Per istruzioni, leggere [configurare la sincronizzazione della directory per Microsoft 365](set-up-directory-synchronization.md)e [Azure ad Connect con le impostazioni Express](https://go.microsoft.com/fwlink/p/?LinkId=698537).</span><span class="sxs-lookup"><span data-stu-id="023ad-136">For instructions, read [Set up directory synchronization for Microsoft 365](set-up-directory-synchronization.md), and [Azure AD Connect with express settings](https://go.microsoft.com/fwlink/p/?LinkId=698537).</span></span>

<span data-ttu-id="023ad-137">Per ulteriori informazioni, vedere [preparazione della sincronizzazione della directory a Microsoft 365](prepare-for-directory-synchronization.md) e [integrazione delle identificazioni locali con Azure Active Directory](https://go.microsoft.com/fwlink/?LinkId=518101).</span><span class="sxs-lookup"><span data-stu-id="023ad-137">Learn more about [preparing for directory synchronization to Microsoft 365](prepare-for-directory-synchronization.md) and [integrating your on-premises identifies with Azure Active Directory](https://go.microsoft.com/fwlink/?LinkId=518101).</span></span>

### <a name="directory-synchronization-with-sso"></a><span data-ttu-id="023ad-138">Sincronizzazione della directory con SSO</span><span class="sxs-lookup"><span data-stu-id="023ad-138">Directory synchronization with SSO</span></span>

<span data-ttu-id="023ad-139">Un utente accede all'ambiente locale con il proprio account utente.</span><span class="sxs-lookup"><span data-stu-id="023ad-139">A user logs on to their on-premises environment with their user account.</span></span> <span data-ttu-id="023ad-140">Quando si accede a Microsoft 365, sono connessi automaticamente oppure eseguono l'accesso utilizzando le stesse credenziali utilizzate per l'ambiente locale (dominio\nomeutente).</span><span class="sxs-lookup"><span data-stu-id="023ad-140">When they go to Microsoft 365, they are either logged on automatically, or they log on using the same credentials they use for their on-premises environment (domain\username).</span></span>

<span data-ttu-id="023ad-141">Per configurare SSO si usa anche Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="023ad-141">To set up SSO you also use Azure AD Connect.</span></span> <span data-ttu-id="023ad-142">Per le istruzioni, vedere [Installazione personalizzata di Azure AD Connect](https://go.microsoft.com/fwlink/p/?LinkID=698430).</span><span class="sxs-lookup"><span data-stu-id="023ad-142">For instructions, read [Custom installation of Azure AD Connect](https://go.microsoft.com/fwlink/p/?LinkID=698430).</span></span>

<span data-ttu-id="023ad-143">Vedere [Accesso Single Sign-On alle applicazioni in Azure Active Directory](https://go.microsoft.com/fwlink/p/?LinkId=698604).</span><span class="sxs-lookup"><span data-stu-id="023ad-143">Learn more about [single sign-on to applications in Azure Active Directory](https://go.microsoft.com/fwlink/p/?LinkId=698604).</span></span>

## <a name="azure-ad-connect"></a><span data-ttu-id="023ad-144">Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="023ad-144">Azure AD Connect</span></span>

<span data-ttu-id="023ad-145">Azure AD Connect sostituisce le precedenti versioni di strumenti di integrazione delle identità come DirSync e Azure AD Sync. Per altre informazioni, vedere [Che cos'è l'identità ibrida con Azure Active Directory?](https://go.microsoft.com/fwlink/p/?LinkId=527969).</span><span class="sxs-lookup"><span data-stu-id="023ad-145">Azure AD Connect replaces older versions of identity integration tools such as DirSync and Azure AD Sync. For more information, see [What is hybrid identity with Azure Active Directory?](https://go.microsoft.com/fwlink/p/?LinkId=527969).</span></span> <span data-ttu-id="023ad-146">Per eseguire l'aggiornamento da Azure Active Directory Sync ad Azure AD Connect, vedere le [istruzioni di aggiornamento](https://go.microsoft.com/fwlink/p/?LinkId=733240).</span><span class="sxs-lookup"><span data-stu-id="023ad-146">If you want to update from Azure Active Directory Sync to Azure AD Connect, see [the upgrade instructions](https://go.microsoft.com/fwlink/p/?LinkId=733240).</span></span> 

<span data-ttu-id="023ad-147">Vedere anche [deploy microsoft 365 Directory Synchronization in Microsoft Azure](https://go.microsoft.com/fwlink/?LinkId=517887).</span><span class="sxs-lookup"><span data-stu-id="023ad-147">Also see [Deploy Microsoft 365 Directory Synchronization in Microsoft Azure](https://go.microsoft.com/fwlink/?LinkId=517887).</span></span>

## <a name="see-also"></a><span data-ttu-id="023ad-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="023ad-148">See also</span></span>

[<span data-ttu-id="023ad-149">Panoramica di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="023ad-149">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)
