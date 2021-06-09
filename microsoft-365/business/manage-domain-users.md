---
title: Sincronizzare gli utenti di dominio con Microsoft 365
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
description: Sincronizzare gli utenti controllati dal dominio con Microsoft 365 per le aziende.
ms.openlocfilehash: b477b8a1f35a790d6c49937c973c141ad9f90ad4
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578408"
---
# <a name="synchronize-domain-users-to-microsoft-365"></a><span data-ttu-id="ac762-103">Sincronizzare gli utenti di dominio con Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ac762-103">Synchronize domain users to Microsoft 365</span></span>

## <a name="1-prepare-for-directory-synchronization"></a><span data-ttu-id="ac762-104">1. Preparare la sincronizzazione della directory</span><span class="sxs-lookup"><span data-stu-id="ac762-104">1. Prepare for Directory Synchronization</span></span> 

<span data-ttu-id="ac762-105">Prima di sincronizzare utenti e computer dal dominio Active Directory locale, vedere [Prepare for directory synchronization to Microsoft 365](../enterprise/prepare-for-directory-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="ac762-105">Before you synchronize your users and computers from the local Active Directory Domain, review [Prepare for directory synchronization to Microsoft 365](../enterprise/prepare-for-directory-synchronization.md).</span></span> <span data-ttu-id="ac762-106">In particolare:</span><span class="sxs-lookup"><span data-stu-id="ac762-106">In particular:</span></span>

   - <span data-ttu-id="ac762-107">Verificare che nella directory non siano presenti duplicati per gli attributi **seguenti: mail,** **proxyAddresses** e **userPrincipalName**.</span><span class="sxs-lookup"><span data-stu-id="ac762-107">Make sure that no duplicates exist in your directory for the following attributes: **mail**, **proxyAddresses**, and **userPrincipalName**.</span></span> <span data-ttu-id="ac762-108">Questi valori devono essere univoci ed eventuali duplicati devono essere rimossi.</span><span class="sxs-lookup"><span data-stu-id="ac762-108">These values must be unique and any duplicates must be removed.</span></span>
   
   - <span data-ttu-id="ac762-109">È consigliabile configurare l'attributo **userPrincipalName** (UPN) per ogni account utente locale in modo che corrisponda all'indirizzo di posta elettronica principale corrispondente all'utente Microsoft 365 con licenza.</span><span class="sxs-lookup"><span data-stu-id="ac762-109">We recommend that you configure the **userPrincipalName** (UPN) attribute for each local user account to match the primary email address that corresponds to the licensed Microsoft 365 user.</span></span> <span data-ttu-id="ac762-110">Ad esempio: *mary.shelley@contoso.com* anziché *mary@contoso.local*</span><span class="sxs-lookup"><span data-stu-id="ac762-110">For example: *mary.shelley@contoso.com* rather than *mary@contoso.local*</span></span>
   
   - <span data-ttu-id="ac762-111">Se il dominio di Active Directory termina con un suffisso non instradabile come *.local* o *.lan*, invece di un suffisso instradabile internet come *.com* o *.org,* regola il suffisso UPN degli account utente locali come descritto in [Prepare a non-routable domain for directory synchronization](../enterprise/prepare-a-non-routable-domain-for-directory-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="ac762-111">If the Active Directory domain ends in a non-routable suffix like *.local* or *.lan*, instead of an internet routable suffix such as *.com* or *.org*, adjust the UPN suffix of the local user accounts first as described in [Prepare a non-routable domain for directory synchronization](../enterprise/prepare-a-non-routable-domain-for-directory-synchronization.md).</span></span> 

<span data-ttu-id="ac762-112">**L'esecuzione di IdFix** nel passaggio 4 (4) seguente assicura inoltre che Active Directory locale sia pronto per la sincronizzazione della directory.</span><span class="sxs-lookup"><span data-stu-id="ac762-112">The **Run IdFix** in step four (4) below, will also make sure your on-premises Active Directory is ready for directory synchronization.</span></span>

## <a name="2-install-and-configure-azure-ad-connect"></a><span data-ttu-id="ac762-113">2. Installare e configurare Azure AD Connessione</span><span class="sxs-lookup"><span data-stu-id="ac762-113">2. Install and configure Azure AD Connect</span></span>

<span data-ttu-id="ac762-114">Per sincronizzare utenti, gruppi e contatti da Active Directory locale a Azure Active Directory, installare Azure Active Directory Connessione e configurare la sincronizzazione della directory.</span><span class="sxs-lookup"><span data-stu-id="ac762-114">To synchronize your users, groups, and contacts from the local Active Directory into Azure Active Directory, install Azure Active Directory Connect and set up directory synchronization.</span></span> 

 1. <span data-ttu-id="ac762-115">[Nell'interfaccia di amministrazione](https://go.microsoft.com/fwlink/p/?linkid=2024339)seleziona **Installazione** nel riquadro di spostamento a sinistra.</span><span class="sxs-lookup"><span data-stu-id="ac762-115">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339), select **Setup** in the left nav.</span></span>

 2. <span data-ttu-id="ac762-116">In **Accesso e sicurezza** scegliere Visualizza in Sincronizza utenti dalla directory **dell'organizzazione.** </span><span class="sxs-lookup"><span data-stu-id="ac762-116">Under **Sign-in and security**, choose **View**  under **Sync users from your org's directory**.</span></span>

 3. <span data-ttu-id="ac762-117">Nella pagina **Sincronizza utenti dalla directory dell'organizzazione** scegliere **Introduzione.**</span><span class="sxs-lookup"><span data-stu-id="ac762-117">On the **Sync users from your org's directory** page, choose **Get started**.</span></span>

 4. <span data-ttu-id="ac762-118">Nel primo passaggio eseguire lo strumento IdFix per preparare la sincronizzazione della directory.</span><span class="sxs-lookup"><span data-stu-id="ac762-118">In the first step  run IdFix tool to prepare for Directory sync.</span></span>

 5. <span data-ttu-id="ac762-119">Segui i passaggi della procedura guidata per scaricare Azure AD Connessione e usarlo per sincronizzare gli utenti controllati dal dominio con Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ac762-119">Follow the wizard steps to download Azure AD Connect and use it to synchronize your domain-controlled users to Microsoft 365.</span></span>


<span data-ttu-id="ac762-120">Per ulteriori informazioni, vedere [Set up directory synchronization for Microsoft 365.](../enterprise/set-up-directory-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="ac762-120">See [Set up directory synchronization for Microsoft 365](../enterprise/set-up-directory-synchronization.md) to learn more.</span></span>

<span data-ttu-id="ac762-121">Quando si configurano le opzioni per Azure AD Connessione, è consigliabile abilitare la sincronizzazione delle **password,** **l'accesso Single #A0** e la funzionalità di writeback delle **password,** supportata anche in Microsoft 365 per le aziende.</span><span class="sxs-lookup"><span data-stu-id="ac762-121">As you configure your options for Azure AD Connect, we recommend that you enable **Password Synchronization**, **Seamless Single Sign-On**, and the **password writeback** feature, which is also supported in Microsoft 365 for business.</span></span>

> [!NOTE]
> <span data-ttu-id="ac762-122">Esistono alcuni passaggi aggiuntivi per il writeback delle password oltre la casella di controllo in Azure AD Connessione.</span><span class="sxs-lookup"><span data-stu-id="ac762-122">There are some additional steps for password writeback beyond the check box in Azure AD Connect.</span></span> <span data-ttu-id="ac762-123">Per ulteriori informazioni, vedere [Procedura: configurare il writeback delle password.](/azure/active-directory/authentication/howto-sspr-writeback)</span><span class="sxs-lookup"><span data-stu-id="ac762-123">For more information, see [How-to: configure password writeback](/azure/active-directory/authentication/howto-sspr-writeback).</span></span> 

<span data-ttu-id="ac762-124">Se vuoi anche gestire i dispositivi Windows 10 aggiunti al dominio, vedi Abilitare i dispositivi Windows 10 aggiunti [al](manage-windows-devices.md) dominio da Microsoft 365 Business Premium per configurare un'aggiunta ibrida ad Azure AD.</span><span class="sxs-lookup"><span data-stu-id="ac762-124">If you also want to manage domain-joined Windows 10 devices, see [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium](manage-windows-devices.md) to set up a hybrid Azure AD Join.</span></span>