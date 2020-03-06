---
title: Abilitare i dispositivi Windows 10 associati a un dominio per essere gestiti da Microsoft 365 business
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- MARVEL_SEO_MAR
search.appverid:
- BCS160
- MET150
ms.assetid: 9b4de218-f1ad-41fa-a61b-e9e8ac0cf993
description: Informazioni su come consentire a Microsoft 365 di proteggere i dispositivi Windows 10 locali con l'aggiunta di Active Directory in pochi passaggi.
ms.openlocfilehash: 8d7caefa1ddcadf684fdb5b712601b1bdd4fb5bd
ms.sourcegitcommit: 26e4d5091583765257b7533b5156daa373cd19fe
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2020
ms.locfileid: "42550248"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business"></a><span data-ttu-id="d856b-103">Abilitare i dispositivi Windows 10 associati a un dominio per essere gestiti da Microsoft 365 business</span><span class="sxs-lookup"><span data-stu-id="d856b-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business</span></span>

<span data-ttu-id="d856b-104">Se l'organizzazione utilizza Windows Server Active Directory in locale, è possibile configurare Microsoft 365 business per proteggere i dispositivi Windows 10, mantenendo comunque l'accesso alle risorse locali che richiedono l'autenticazione locale.</span><span class="sxs-lookup"><span data-stu-id="d856b-104">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span>
<span data-ttu-id="d856b-105">Per impostare questa protezione, è possibile implementare i **dispositivi ibridi di Azure ad Uniti**.</span><span class="sxs-lookup"><span data-stu-id="d856b-105">To set up this protection, you can implement **Hybrid Azure AD joined devices**.</span></span> <span data-ttu-id="d856b-106">Questi dispositivi sono associati sia a Active Directory locale che a Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d856b-106">These devices are joined to both your on-premises Active Directory and your Azure Active Directory.</span></span>

<span data-ttu-id="d856b-107">In questo video vengono illustrati i passaggi da eseguire per la configurazione dello scenario più comune, che è anche dettagliato nei passaggi successivi.</span><span class="sxs-lookup"><span data-stu-id="d856b-107">This video describes the steps for how to set this up for the most common scenario, which is also detailed in the steps that follow.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="1-prepare-for-directory-synchronization"></a><span data-ttu-id="d856b-108">1. preparare la sincronizzazione della directory</span><span class="sxs-lookup"><span data-stu-id="d856b-108">1. Prepare for Directory Synchronization</span></span> 

<span data-ttu-id="d856b-109">Prima di sincronizzare gli utenti e i computer dal dominio Active Directory locale, esaminare [prepararsi per la sincronizzazione della directory in Office 365](https://docs.microsoft.com/office365/enterprise/prepare-for-directory-synchronization).</span><span class="sxs-lookup"><span data-stu-id="d856b-109">Before you synchronize your users and computers from the local Active Directory Domain, review [Prepare for directory synchronization to Office 365](https://docs.microsoft.com/office365/enterprise/prepare-for-directory-synchronization).</span></span> <span data-ttu-id="d856b-110">In particolare:</span><span class="sxs-lookup"><span data-stu-id="d856b-110">In particular:</span></span>

   - <span data-ttu-id="d856b-111">Verificare che nella directory non siano presenti duplicati per gli attributi seguenti: **mail**, **proxyAddresses**e **userPrincipalName**.</span><span class="sxs-lookup"><span data-stu-id="d856b-111">Make sure that no duplicates exist in your directory for the following attributes: **mail**, **proxyAddresses**, and **userPrincipalName**.</span></span> <span data-ttu-id="d856b-112">Questi valori devono essere univoci e tutti i duplicati devono essere rimossi.</span><span class="sxs-lookup"><span data-stu-id="d856b-112">These values must be unique and any duplicates must be removed.</span></span>
   
   - <span data-ttu-id="d856b-113">Si consiglia di configurare l'attributo **userPrincipalName** (UPN) per ogni account utente locale in modo che corrisponda all'indirizzo di posta elettronica principale corrispondente all'utente con licenza Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d856b-113">We recommend that you configure the **userPrincipalName** (UPN) attribute for each local user account to match the primary email address that corresponds to the licensed Microsoft 365 user.</span></span> <span data-ttu-id="d856b-114">Ad esempio: *Mary.Shelley@contoso.com* anziché *Mary@contoso. local*</span><span class="sxs-lookup"><span data-stu-id="d856b-114">For example: *mary.shelley@contoso.com* rather than *mary@contoso.local*</span></span>
   
   - <span data-ttu-id="d856b-115">Se il dominio Active Directory termina con un suffisso non instradabile come *. local* o *. LAN*, invece di un suffisso instradabile su Internet, ad esempio *. com* o *. org*, modificare il suffisso UPN degli account utente locali come descritto in [preparare un dominio non instradabile per la sincronizzazione della directory](https://docs.microsoft.com/office365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization).</span><span class="sxs-lookup"><span data-stu-id="d856b-115">If the Active Directory domain ends in a non-routable suffix like *.local* or *.lan*, instead of an internet routable suffix such as *.com* or *.org*, adjust the UPN suffix of the local user accounts first as described in [Prepare a non-routable domain for directory synchronization](https://docs.microsoft.com/office365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization).</span></span> 

## <a name="2-install-and-configure-azure-ad-connect"></a><span data-ttu-id="d856b-116">2. installare e configurare Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="d856b-116">2. Install and configure Azure AD Connect</span></span>

<span data-ttu-id="d856b-117">Per sincronizzare gli utenti, i gruppi e i contatti da Active Directory locale ad Azure Active Directory, installare Azure Active Directory Connect e configurare la sincronizzazione della directory.</span><span class="sxs-lookup"><span data-stu-id="d856b-117">To synchronize your users, groups, and contacts from the local Active Directory into Azure Active Directory, install Azure Active Directory Connect and set up directory synchronization.</span></span> <span data-ttu-id="d856b-118">Per ulteriori informazioni, vedere [configurare la sincronizzazione della directory per Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846) .</span><span class="sxs-lookup"><span data-stu-id="d856b-118">See [Set up directory synchronization for Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846) to learn more.</span></span>

> [!NOTE]
> <span data-ttu-id="d856b-119">I passaggi sono esattamente gli stessi per Microsoft 365 business.</span><span class="sxs-lookup"><span data-stu-id="d856b-119">The steps are exactly the same for Microsoft 365 Business.</span></span> 

<span data-ttu-id="d856b-120">Quando si configurano le opzioni per Azure AD Connect, è consigliabile abilitare la **sincronizzazione delle password**, l' **accesso Single Sign-on senza**problemi e la funzionalità writeback delle **password** , supportata anche in Microsoft 365 business.</span><span class="sxs-lookup"><span data-stu-id="d856b-120">As you configure your options for Azure AD Connect, we recommend that you enable **Password Synchronization**, **Seamless Single Sign-On**, and the **password writeback** feature, which is also supported in Microsoft 365 Business.</span></span>

> [!NOTE]
> <span data-ttu-id="d856b-121">Sono disponibili ulteriori passaggi per il writeback delle password oltre la casella di controllo in Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="d856b-121">There are some additional steps for password writeback beyond the check box in Azure AD Connect.</span></span> <span data-ttu-id="d856b-122">Per ulteriori informazioni, vedere [How-to: Configure password writeback](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback).</span><span class="sxs-lookup"><span data-stu-id="d856b-122">For more information, see [How-to: configure password writeback](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback).</span></span> 

## <a name="3-configure-hybrid-azure-ad-join"></a><span data-ttu-id="d856b-123">3. configurare la join ibrido di Azure AD</span><span class="sxs-lookup"><span data-stu-id="d856b-123">3. Configure Hybrid Azure AD Join</span></span>

<span data-ttu-id="d856b-124">Prima di abilitare i dispositivi Windows 10 a essere Uniti ad Azure ibrido, verificare che siano soddisfatti i prerequisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="d856b-124">Before you enable Windows 10 devices to be Hybrid Azure AD joined, make sure that you meet the following prerequisites:</span></span>

   - <span data-ttu-id="d856b-125">Si sta eseguendo la versione più recente di Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="d856b-125">You're running the latest version of Azure AD Connect.</span></span>

   - <span data-ttu-id="d856b-126">Azure AD Connect ha sincronizzato tutti gli oggetti computer dei dispositivi in cui si desidera essere Uniti AD Azure ibrido.</span><span class="sxs-lookup"><span data-stu-id="d856b-126">Azure AD connect has synchronized all the computer objects of the devices you want to be hybrid Azure AD joined.</span></span> <span data-ttu-id="d856b-127">Se gli oggetti computer appartengono a specifiche unità organizzative (OU), assicurarsi che le unità organizzative siano impostate per la sincronizzazione anche in Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="d856b-127">If the computer objects belong to specific organizational units (OU), then make sure these OUs are set for synchronization in Azure AD connect as well.</span></span>

<span data-ttu-id="d856b-128">Per registrare i dispositivi Windows 10 aggiunti a un dominio come ibridi di Azure AD Uniti, seguire la procedura illustrata nell' [esercitazione: Configure Hybrid Azure Active Directory join for Managed](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join)Domains.</span><span class="sxs-lookup"><span data-stu-id="d856b-128">To register existing domain-joined Windows 10 devices as Hybrid Azure AD joined, follow the steps in the [Tutorial: Configure hybrid Azure Active Directory join for managed domains](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join).</span></span> <span data-ttu-id="d856b-129">Questo ibrido consente di abilitare Active Directory locale esistente in computer Windows 10 e renderli pronti per il cloud.</span><span class="sxs-lookup"><span data-stu-id="d856b-129">This hybrid-enables your existing on-premises Active Directory joined Windows 10 computers and make them cloud ready.</span></span>
    
## <a name="4-enable-automatic-enrollment-for-windows-10"></a><span data-ttu-id="d856b-130">4. abilitare la registrazione automatica per Windows 10</span><span class="sxs-lookup"><span data-stu-id="d856b-130">4. Enable automatic enrollment for Windows 10</span></span>

 <span data-ttu-id="d856b-131">Per registrare automaticamente i dispositivi Windows 10 per la gestione dei dispositivi mobili in Intune, vedere [registrazione di un dispositivo Windows 10 automaticamente tramite criteri di gruppo](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy).</span><span class="sxs-lookup"><span data-stu-id="d856b-131">To automatically enroll Windows 10 devices for mobile device management in Intune, see [Enroll a Windows 10 device automatically using Group Policy](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy).</span></span> <span data-ttu-id="d856b-132">È possibile impostare criteri di gruppo a livello di computer locale o per operazioni in blocco, è possibile utilizzare la console Gestione criteri di gruppo e i modelli ADMX per creare questa impostazione di criteri di gruppo nel controller di dominio.</span><span class="sxs-lookup"><span data-stu-id="d856b-132">You can set the Group Policy at a local computer level, or for bulk operations, you can use the Group Policy Management Console and ADMX templates to create this Group Policy setting on your Domain Controller.</span></span>

## <a name="5-configure-seamless-single-sign-on"></a><span data-ttu-id="d856b-133">5. configurare l'accesso Single Sign-on senza problemi</span><span class="sxs-lookup"><span data-stu-id="d856b-133">5. Configure Seamless Single Sign-On</span></span>

  <span data-ttu-id="d856b-134">SSO senza soluzione di continuità firma automaticamente gli utenti nelle risorse cloud di Microsoft 365 quando utilizzano i computer aziendali.</span><span class="sxs-lookup"><span data-stu-id="d856b-134">Seamless SSO automatically signs users into their Microsoft 365 cloud resources when they use corporate computers.</span></span> <span data-ttu-id="d856b-135">È sufficiente distribuire una delle due opzioni di criteri di gruppo descritte in [Azure Active Directory Single Sign-on senza problemi: avvio veloce](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sso-quick-start#step-2-enable-the-feature).</span><span class="sxs-lookup"><span data-stu-id="d856b-135">Simply deploy one of the two Group Policy options described in [Azure Active Directory Seamless Single Sign-On: Quick start](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sso-quick-start#step-2-enable-the-feature).</span></span> <span data-ttu-id="d856b-136">L'opzione **criteri di gruppo** non consente agli utenti di modificare le relative impostazioni, mentre l'opzione **preferenza criteri di gruppo** consente di impostare i valori, ma anche di lasciarli configurabili dall'utente.</span><span class="sxs-lookup"><span data-stu-id="d856b-136">The **Group Policy** option doesn't allow users to change their settings, while the **Group Policy Preference** option sets the values but also leaves them user-configurable.</span></span>

## <a name="6-set-up-windows-hello-for-business"></a><span data-ttu-id="d856b-137">6. configurare Windows Hello for business</span><span class="sxs-lookup"><span data-stu-id="d856b-137">6. Set up Windows Hello for Business</span></span>

 <span data-ttu-id="d856b-138">Windows Hello for business sostituisce le password con una forte autenticazione a due fattori (2FA) per l'accesso a un computer locale.</span><span class="sxs-lookup"><span data-stu-id="d856b-138">Windows Hello for Business replaces passwords with strong two-factor authentication (2FA) for signing into a local computer.</span></span> <span data-ttu-id="d856b-139">Un fattore è una coppia di chiavi asimmetriche e l'altro è un PIN o un altro gesto locale, ad esempio l'impronta digitale o il riconoscimento facciale, se il dispositivo lo supporta.</span><span class="sxs-lookup"><span data-stu-id="d856b-139">One factor is an asymmetric key pair, and the other is a PIN or other local gesture such as fingerprint or facial recognition if your device supports it.</span></span> <span data-ttu-id="d856b-140">Se possibile, è consigliabile sostituire le password con 2FA e Windows Hello for business.</span><span class="sxs-lookup"><span data-stu-id="d856b-140">We recommend that you replace passwords with 2FA and Windows Hello for Business where possible.</span></span>

<span data-ttu-id="d856b-141">Per configurare le finestre ibride Hello for business, vedere i [prerequisiti di Windows Hello for business per le chiavi ibride](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-trust-prereqs).</span><span class="sxs-lookup"><span data-stu-id="d856b-141">To configure Hybrid Windows Hello for Business, review the [Hybrid Key trust Windows Hello for Business Prerequisites](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-trust-prereqs).</span></span> <span data-ttu-id="d856b-142">Seguire le istruzioni riportate in [Configure Hybrid Windows Hello for business Key Trust Settings](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-whfb-settings).</span><span class="sxs-lookup"><span data-stu-id="d856b-142">Then follow the instructions in [Configure Hybrid Windows Hello for Business key trust settings](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-whfb-settings).</span></span> 
