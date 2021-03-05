---
title: Gestire l'accesso guest nei gruppi di Microsoft 365
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ms.assetid: 9de497a9-2f5c-43d6-ae18-767f2e6fe6e0
description: Informazioni su come aggiungere utenti guest a un gruppo di Microsoft 365, visualizzare gli utenti guest e usare PowerShell per controllare l'accesso guest.
ms.openlocfilehash: 9a713684bb9a2401316dbb3289115be19b220cff
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2021
ms.locfileid: "50453658"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a><span data-ttu-id="95679-103">Gestire l'accesso guest nei gruppi di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="95679-103">Manage guest access in Microsoft 365 groups</span></span>

<span data-ttu-id="95679-104">Per impostazione predefinita, l'accesso guest per i gruppi di Microsoft 365 è attivato per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="95679-104">By default, guest access for Microsoft 365 groups is turned on for your organization.</span></span> <span data-ttu-id="95679-105">Gli amministratori possono controllare se consentire l'accesso guest ai gruppi per l'intera organizzazione o per i singoli gruppi.</span><span class="sxs-lookup"><span data-stu-id="95679-105">Admins can control whether to allow guest access to groups for their whole organization or for individual groups.</span></span>

<span data-ttu-id="95679-106">Quando è attivata, i membri del gruppo possono invitare utenti guest a un gruppo di Microsoft 365 tramite Outlook sul Web.</span><span class="sxs-lookup"><span data-stu-id="95679-106">When it's turned on, group members can invite guest users to a Microsoft 365 group through Outlook on Web.</span></span> <span data-ttu-id="95679-107">Gli inviti vengono inviati al proprietario del gruppo per l'approvazione.</span><span class="sxs-lookup"><span data-stu-id="95679-107">Invitations are sent to the group owner for approval.</span></span>

<span data-ttu-id="95679-108">Dopo l'approvazione, l'utente guest viene aggiunto alla directory e al gruppo.</span><span class="sxs-lookup"><span data-stu-id="95679-108">Once approved, the guest user is added to the directory and the group.</span></span>

> [!Note]
> <span data-ttu-id="95679-109">Le reti Yammer Enterprise che sono in modalità nativa o [l'area geografica dell'Unione Europea](https://go.microsoft.com/fwlink/?linkid=2107357) non supportano gli utenti guest di rete.</span><span class="sxs-lookup"><span data-stu-id="95679-109">Yammer Enterprise networks that are in Native Mode or the [EU Geo](https://go.microsoft.com/fwlink/?linkid=2107357) do not support network guests.</span></span>
> <span data-ttu-id="95679-110">I gruppi di Yammer connessi a Microsoft 365 attualmente non supportano l'accesso guest, ma è possibile creare gruppi esterni non connessi nella rete Yammer.</span><span class="sxs-lookup"><span data-stu-id="95679-110">Microsoft 365 Connected Yammer groups do not currently support guest access, but you can create non-connected, external groups in your Yammer network.</span></span> <span data-ttu-id="95679-111">Per [istruzioni, vedere Creare e gestire gruppi esterni in Yammer.](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-external-groups)</span><span class="sxs-lookup"><span data-stu-id="95679-111">See [Create and manage external groups in Yammer](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-external-groups) for instructions.</span></span>

<span data-ttu-id="95679-112">L'accesso guest nei gruppi viene spesso utilizzato come parte di uno scenario più ampio che include SharePoint o Teams.</span><span class="sxs-lookup"><span data-stu-id="95679-112">Guest access in groups is often used as part of a broader scenario that includes SharePoint or Teams.</span></span> <span data-ttu-id="95679-113">Questi servizi hanno le proprie impostazioni di condivisione guest.</span><span class="sxs-lookup"><span data-stu-id="95679-113">These services have their own guest sharing settings.</span></span> <span data-ttu-id="95679-114">Per istruzioni complete sulla configurazione della condivisione guest tra gruppi, SharePoint e Teams, vedere:</span><span class="sxs-lookup"><span data-stu-id="95679-114">For complete instructions for setting up guest sharing across groups, SharePoint, and Teams, see:</span></span>

- [<span data-ttu-id="95679-115">Collaborare con gli utenti guest a un sito</span><span class="sxs-lookup"><span data-stu-id="95679-115">Collaborate with guests in a site</span></span>](../../solutions/collaborate-in-site.md)
- [<span data-ttu-id="95679-116">Collaborare con gli utenti guest in un team</span><span class="sxs-lookup"><span data-stu-id="95679-116">Collaborate with guests in a team</span></span>](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a><span data-ttu-id="95679-117">Gestire l'accesso guest ai gruppi</span><span class="sxs-lookup"><span data-stu-id="95679-117">Manage groups guest access</span></span>

<span data-ttu-id="95679-118">Se si desidera abilitare o disabilitare l'accesso guest nei gruppi, è possibile farlo nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="95679-118">If you want to enable or disable guest access in groups, you can do so in the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="95679-119">Nell'interfaccia di amministrazione passare a **Mostra** tutte le impostazioni dell'organizzazione e nella scheda Servizi selezionare Gruppi di \>  \>  **Microsoft 365.** </span><span class="sxs-lookup"><span data-stu-id="95679-119">In the admin center, go to **Show all** \> **Settings** \> **Org settings** and on the **Services** tab, select **Microsoft 365 groups**.</span></span>
  
2. <span data-ttu-id="95679-120">Nella pagina **Gruppi di Microsoft 365** scegliere se consentire alle persone esterne all'organizzazione di accedere alle risorse del gruppo o consentire ai proprietari dei gruppi di aggiungere persone esterne all'organizzazione ai gruppi.</span><span class="sxs-lookup"><span data-stu-id="95679-120">On the **Microsoft 365 Groups** page, choose whether you want to let people outside your organization access group resources or let group owners add people outside your organization to groups.</span></span>

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a><span data-ttu-id="95679-121">Aggiungere utenti guest a un gruppo di Microsoft 365 dall'interfaccia di amministrazione</span><span class="sxs-lookup"><span data-stu-id="95679-121">Add guests to a Microsoft 365 group from the admin center</span></span>

<span data-ttu-id="95679-122">Se il guest esiste già nella directory, è possibile aggiungerlo ai gruppi dall'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="95679-122">If the guest already exists in your directory, you can add them to your groups from the Microsoft 365 admin center.</span></span> <span data-ttu-id="95679-123">I gruppi con appartenenza dinamica devono [essere gestiti in Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/enterprise-users/groups-create-rule)</span><span class="sxs-lookup"><span data-stu-id="95679-123">(Groups with dynamic membership must be [managed in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/enterprise-users/groups-create-rule).)</span></span>
  
1. <span data-ttu-id="95679-124">Nell'interfaccia di amministrazione passare alla pagina  >  **Gruppi di** gruppi.</span><span class="sxs-lookup"><span data-stu-id="95679-124">In the admin center, go to the **Groups** > **Groups** page.</span></span>
  
2. <span data-ttu-id="95679-125">Fare clic sul gruppo a cui si desidera aggiungere il guest e selezionare Visualizza tutti e **gestisci membri** nella **scheda** Membri.</span><span class="sxs-lookup"><span data-stu-id="95679-125">Click the group you want to add the guest to, and select **View all and manage members** on the **Members** tab.</span></span> 
  
4. <span data-ttu-id="95679-126">Selezionare **Aggiungi membri** e scegliere il nome del guest che si desidera aggiungere.</span><span class="sxs-lookup"><span data-stu-id="95679-126">Select **Add members**, and choose the name of the guest you want to add.</span></span>
    
5. <span data-ttu-id="95679-127">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="95679-127">Select **Save**.</span></span>

<span data-ttu-id="95679-128">Se si desidera aggiungere direttamente un guest alla directory, è possibile aggiungere utenti di collaborazione [B2B](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator)di Azure Active Directory nel portale di Azure.</span><span class="sxs-lookup"><span data-stu-id="95679-128">If you want to add a guest to the directory directly, you can [Add Azure Active Directory B2B collaboration users in the Azure portal](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).</span></span>

<span data-ttu-id="95679-129">Se si desidera modificare le informazioni di un guest, è possibile aggiungere o aggiornare le informazioni del profilo di un utente [tramite Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)</span><span class="sxs-lookup"><span data-stu-id="95679-129">If you want to edit any of a guest's information, you can [Add or update a user's profile information using Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>

## <a name="see-also"></a><span data-ttu-id="95679-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="95679-130">See also</span></span>

[<span data-ttu-id="95679-131">Bloccare gli utenti guest da un gruppo specifico</span><span class="sxs-lookup"><span data-stu-id="95679-131">Block guest users from a specific group</span></span>](https://docs.microsoft.com/microsoft-365/solutions/per-group-guest-access)

[<span data-ttu-id="95679-132">Gestire l'appartenenza ai gruppi nell'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="95679-132">Manage group membership in the Microsoft 365 admin center</span></span>](add-or-remove-members-from-groups.md)
  
[<span data-ttu-id="95679-133">Verifiche di accesso di Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="95679-133">Azure Active Directory access reviews</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[<span data-ttu-id="95679-134">Set-AzureADUser</span><span class="sxs-lookup"><span data-stu-id="95679-134">Set-AzureADUser</span></span>](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)
