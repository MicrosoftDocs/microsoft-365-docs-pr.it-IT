---
title: Sincronizzare gli utenti di dominio con Microsoft 365
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: M365-subscription-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Sincronizzare gli utenti controllati dal dominio con Microsoft 365 for business.
ms.openlocfilehash: b40a995a1723808d2fd171c534e9131a891840ba
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841360"
---
# <a name="synchronize-domain-users-to-microsoft-365"></a><span data-ttu-id="729f0-103">Sincronizzare gli utenti di dominio con Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="729f0-103">Synchronize domain users to Microsoft 365</span></span>

## <a name="1-prepare-for-directory-synchronization"></a><span data-ttu-id="729f0-104">1. preparare la sincronizzazione della directory</span><span class="sxs-lookup"><span data-stu-id="729f0-104">1. Prepare for Directory Synchronization</span></span> 

<span data-ttu-id="729f0-105">Prima di sincronizzare gli utenti e i computer dal dominio Active Directory locale, esaminare [preparare la sincronizzazione della directory a Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/prepare-for-directory-synchronization).</span><span class="sxs-lookup"><span data-stu-id="729f0-105">Before you synchronize your users and computers from the local Active Directory Domain, review [Prepare for directory synchronization to Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/prepare-for-directory-synchronization).</span></span> <span data-ttu-id="729f0-106">In particolare:</span><span class="sxs-lookup"><span data-stu-id="729f0-106">In particular:</span></span>

   - <span data-ttu-id="729f0-107">Verificare che nella directory non siano presenti duplicati per gli attributi seguenti: **mail** , **proxyAddresses** e **userPrincipalName** .</span><span class="sxs-lookup"><span data-stu-id="729f0-107">Make sure that no duplicates exist in your directory for the following attributes: **mail** , **proxyAddresses** , and **userPrincipalName** .</span></span> <span data-ttu-id="729f0-108">Questi valori devono essere univoci e tutti i duplicati devono essere rimossi.</span><span class="sxs-lookup"><span data-stu-id="729f0-108">These values must be unique and any duplicates must be removed.</span></span>
   
   - <span data-ttu-id="729f0-109">Si consiglia di configurare l'attributo **userPrincipalName** (UPN) per ogni account utente locale in modo che corrisponda all'indirizzo di posta elettronica principale corrispondente all'utente con licenza Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="729f0-109">We recommend that you configure the **userPrincipalName** (UPN) attribute for each local user account to match the primary email address that corresponds to the licensed Microsoft 365 user.</span></span> <span data-ttu-id="729f0-110">Ad esempio: *Mary.Shelley@contoso.com* anziché *Mary@contoso. local*</span><span class="sxs-lookup"><span data-stu-id="729f0-110">For example: *mary.shelley@contoso.com* rather than *mary@contoso.local*</span></span>
   
   - <span data-ttu-id="729f0-111">Se il dominio Active Directory termina con un suffisso non instradabile come *. local* o *. LAN* , invece di un suffisso instradabile su Internet, ad esempio *. com* o *. org* , modificare il suffisso UPN degli account utente locali come descritto in [preparare un dominio non instradabile per la sincronizzazione della directory](https://docs.microsoft.com/microsoft-365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization).</span><span class="sxs-lookup"><span data-stu-id="729f0-111">If the Active Directory domain ends in a non-routable suffix like *.local* or *.lan* , instead of an internet routable suffix such as *.com* or *.org* , adjust the UPN suffix of the local user accounts first as described in [Prepare a non-routable domain for directory synchronization](https://docs.microsoft.com/microsoft-365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization).</span></span> 

<span data-ttu-id="729f0-112">L' **esecuzione di IdFix** nel passaggio quattro (4) seguente assicurerà inoltre che Active Directory locale sia pronto per la sincronizzazione della directory.</span><span class="sxs-lookup"><span data-stu-id="729f0-112">The **Run IdFix** in step four (4) below, will also make sure your on-premises Active Directory is ready for directory synchronization.</span></span>

## <a name="2-install-and-configure-azure-ad-connect"></a><span data-ttu-id="729f0-113">2. installare e configurare Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="729f0-113">2. Install and configure Azure AD Connect</span></span>

<span data-ttu-id="729f0-114">Per sincronizzare gli utenti, i gruppi e i contatti da Active Directory locale ad Azure Active Directory, installare Azure Active Directory Connect e configurare la sincronizzazione della directory.</span><span class="sxs-lookup"><span data-stu-id="729f0-114">To synchronize your users, groups, and contacts from the local Active Directory into Azure Active Directory, install Azure Active Directory Connect and set up directory synchronization.</span></span> 

 1. <span data-ttu-id="729f0-115">Nell'interfaccia di [Amministrazione](https://go.microsoft.com/fwlink/p/?linkid=2024339), selezionare **configurazione** nel NAV sinistro.</span><span class="sxs-lookup"><span data-stu-id="729f0-115">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339), select **Setup** in the left nav.</span></span>

 2. <span data-ttu-id="729f0-116">In **accesso e sicurezza** , scegliere **Visualizza**  in **Sincronizza utenti dalla directory dell'organizzazione** .</span><span class="sxs-lookup"><span data-stu-id="729f0-116">Under **Sign-in and security** , choose **View**  under **Sync users from your org's directory** .</span></span>

 3. <span data-ttu-id="729f0-117">Nella pagina **Sync Users from your org ' s directory** scegliere **Get Started** .</span><span class="sxs-lookup"><span data-stu-id="729f0-117">On the **Sync users from your org's directory** page, choose **Get started** .</span></span>

 4. <span data-ttu-id="729f0-118">Nel primo passaggio eseguire lo strumento IdFix per preparare la sincronizzazione della directory.</span><span class="sxs-lookup"><span data-stu-id="729f0-118">In the first step  run IdFix tool to prepare for Directory sync.</span></span>

 5. <span data-ttu-id="729f0-119">Seguire la procedura guidata per scaricare Azure AD Connect e utilizzarlo per sincronizzare gli utenti controllati dal dominio a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="729f0-119">Follow the wizard steps to download Azure AD Connect and use it to synchronize your domain-controlled users to Microsoft 365.</span></span>


<span data-ttu-id="729f0-120">Per ulteriori informazioni, vedere [configurare la sincronizzazione della directory per Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization) .</span><span class="sxs-lookup"><span data-stu-id="729f0-120">See [Set up directory synchronization for Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization) to learn more.</span></span>

<span data-ttu-id="729f0-121">Quando si configurano le opzioni per Azure AD Connect, è consigliabile abilitare la **sincronizzazione delle password** , l' **accesso Single Sign-on senza** problemi e la funzionalità writeback delle **password** , supportata anche in Microsoft 365 for business.</span><span class="sxs-lookup"><span data-stu-id="729f0-121">As you configure your options for Azure AD Connect, we recommend that you enable **Password Synchronization** , **Seamless Single Sign-On** , and the **password writeback** feature, which is also supported in Microsoft 365 for business.</span></span>

> [!NOTE]
> <span data-ttu-id="729f0-122">Sono disponibili ulteriori passaggi per il writeback delle password oltre la casella di controllo in Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="729f0-122">There are some additional steps for password writeback beyond the check box in Azure AD Connect.</span></span> <span data-ttu-id="729f0-123">Per ulteriori informazioni, vedere [How-to: Configure password writeback](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback).</span><span class="sxs-lookup"><span data-stu-id="729f0-123">For more information, see [How-to: configure password writeback](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback).</span></span> 

<span data-ttu-id="729f0-124">Se si desidera anche gestire i dispositivi Windows 10 aggiunti a un dominio, vedere [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium](manage-windows-devices.md) per configurare un join di Azure ad ibrido.</span><span class="sxs-lookup"><span data-stu-id="729f0-124">If you also want to manage domain-joined Windows 10 devices, see [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium](manage-windows-devices.md) to set up a hybrid Azure AD Join.</span></span> 