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
description: Informazioni su come aggiungere gli ospiti a un gruppo di Microsoft 365, visualizzare gli utenti guest e utilizzare PowerShell per controllare l'accesso guest.
ms.openlocfilehash: 3fba6b4498f275b07148c2d879d141474ddf4a13
ms.sourcegitcommit: 3cdb670f10519f7af4015731e7910954ba9f70dc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753278"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a><span data-ttu-id="58c37-103">Gestire l'accesso guest nei gruppi di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="58c37-103">Manage guest access in Microsoft 365 groups</span></span>

<span data-ttu-id="58c37-104">Per impostazione predefinita, l'accesso guest per i gruppi di Microsoft 365 è attivato per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="58c37-104">By default, guest access for Microsoft 365 groups is turned on for your organization.</span></span> <span data-ttu-id="58c37-105">Gli amministratori possono controllare se consentire l'accesso Guest ai gruppi per l'intera organizzazione o per i singoli gruppi.</span><span class="sxs-lookup"><span data-stu-id="58c37-105">Admins can control whether to allow guest access to groups for their whole organization or for individual groups.</span></span>

<span data-ttu-id="58c37-106">Quando è attivata, i membri del gruppo possono invitare gli utenti Guest a un gruppo di Microsoft 365 tramite Outlook sul Web.</span><span class="sxs-lookup"><span data-stu-id="58c37-106">When it's turned on, group members can invite guest users to a Microsoft 365 group through Outlook on Web.</span></span> <span data-ttu-id="58c37-107">Gli inviti vengono inviati al proprietario del gruppo per l'approvazione.</span><span class="sxs-lookup"><span data-stu-id="58c37-107">Invitations are sent to the group owner for approval.</span></span>

<span data-ttu-id="58c37-108">Una volta approvato, l'utente ospite viene aggiunto alla directory e al gruppo.</span><span class="sxs-lookup"><span data-stu-id="58c37-108">Once approved, the guest user is added to the directory and the group.</span></span>

> [!Note]
> <span data-ttu-id="58c37-109">Le reti aziendali di Yammer che si trovano in modalità nativa o l' [eu Geo](https://go.microsoft.com/fwlink/?linkid=2107357) non supportano gli utenti della rete.</span><span class="sxs-lookup"><span data-stu-id="58c37-109">Yammer Enterprise networks that are in Native Mode or the [EU Geo](https://go.microsoft.com/fwlink/?linkid=2107357) do not support network guests.</span></span>
> <span data-ttu-id="58c37-110">I gruppi di Yammer connessi a Microsoft 365 non supportano attualmente l'accesso guest, ma è possibile creare gruppi esterni non connessi nella rete Yammer.</span><span class="sxs-lookup"><span data-stu-id="58c37-110">Microsoft 365 Connected Yammer groups do not currently support guest access, but you can create non-connected, external groups in your Yammer network.</span></span> <span data-ttu-id="58c37-111">Per istruzioni, vedere [creare e gestire gruppi esterni in Yammer](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-external-groups) .</span><span class="sxs-lookup"><span data-stu-id="58c37-111">See [Create and manage external groups in Yammer](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-external-groups) for instructions.</span></span>

<span data-ttu-id="58c37-112">L'accesso guest nei gruppi è spesso utilizzato come parte di uno scenario più ampio che include SharePoint o teams.</span><span class="sxs-lookup"><span data-stu-id="58c37-112">Guest access in groups is often used as part of a broader scenario that includes SharePoint or Teams.</span></span> <span data-ttu-id="58c37-113">Tali servizi dispongono di impostazioni di condivisione Guest.</span><span class="sxs-lookup"><span data-stu-id="58c37-113">These services have their own guest sharing settings.</span></span> <span data-ttu-id="58c37-114">Per istruzioni complete su come configurare la condivisione Guest tra gruppi, SharePoint e team, vedere:</span><span class="sxs-lookup"><span data-stu-id="58c37-114">For complete instructions for setting up guest sharing across groups, SharePoint, and Teams, see:</span></span>

- [<span data-ttu-id="58c37-115">Collaborare con gli utenti guest a un sito</span><span class="sxs-lookup"><span data-stu-id="58c37-115">Collaborate with guests in a site</span></span>](../../solutions/collaborate-in-site.md)
- [<span data-ttu-id="58c37-116">Collaborare con gli utenti guest in un team</span><span class="sxs-lookup"><span data-stu-id="58c37-116">Collaborate with guests in a team</span></span>](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a><span data-ttu-id="58c37-117">Gestione degli accessi ai gruppi</span><span class="sxs-lookup"><span data-stu-id="58c37-117">Manage groups guest access</span></span>

<span data-ttu-id="58c37-118">Se si desidera abilitare o disabilitare l'accesso guest nei gruppi, è possibile farlo nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="58c37-118">If you want to enable or disable guest access in groups, you can do so in the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="58c37-119">Nell'interfaccia di amministrazione, andare a **Mostra tutte** le impostazioni \> **Settings** \> **org** impostazioni e nella scheda **Servizi** , selezionare **Microsoft 365 gruppi**.</span><span class="sxs-lookup"><span data-stu-id="58c37-119">In the admin center, go to **Show all** \> **Settings** \> **Org settings** and on the **Services** tab, select **Microsoft 365 groups**.</span></span>
  
2. <span data-ttu-id="58c37-120">Nella pagina **Microsoft 365 groups** , scegliere se si desidera consentire agli utenti esterni all'organizzazione di accedere alle risorse del gruppo o consentire ai proprietari di gruppi di aggiungere persone esterne all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="58c37-120">On the **Microsoft 365 Groups** page, choose whether you want to let people outside your organization access group resources or let group owners add people outside your organization to groups.</span></span>

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a><span data-ttu-id="58c37-121">Aggiungere gli utenti a un gruppo di Microsoft 365 dall'interfaccia di amministrazione</span><span class="sxs-lookup"><span data-stu-id="58c37-121">Add guests to a Microsoft 365 group from the admin center</span></span>

<span data-ttu-id="58c37-122">Se l'ospite è già presente nella directory, è possibile aggiungerli ai gruppi dall'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="58c37-122">If the guest already exists in your directory, you can add them to your groups from the Microsoft 365 admin center.</span></span>
  
1. <span data-ttu-id="58c37-123">Nell'interfaccia di amministrazione, andare alla pagina **gruppi**  >  **Groups** .</span><span class="sxs-lookup"><span data-stu-id="58c37-123">In the admin center, go to the **Groups** > **Groups** page.</span></span>
  
2. <span data-ttu-id="58c37-124">Fare clic sul gruppo a cui si desidera aggiungere l'ospite e selezionare **Visualizza tutti e Gestisci membri** nella scheda **membri** .</span><span class="sxs-lookup"><span data-stu-id="58c37-124">Click the group you want to add the guest to, and select **View all and manage members** on the **Members** tab.</span></span> 
  
4. <span data-ttu-id="58c37-125">Selezionare **Aggiungi membri**e scegliere il nome del Guest che si desidera aggiungere.</span><span class="sxs-lookup"><span data-stu-id="58c37-125">Select **Add members**, and choose the name of the guest you want to add.</span></span>
    
5. <span data-ttu-id="58c37-126">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="58c37-126">Select **Save**.</span></span>

<span data-ttu-id="58c37-127">Se si desidera aggiungere direttamente un guest alla directory, è possibile [aggiungere gli utenti di collaborazione B2B di Azure Active Directory nel portale di Azure](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).</span><span class="sxs-lookup"><span data-stu-id="58c37-127">If you want to add a guest to the directory directly, you can [Add Azure Active Directory B2B collaboration users in the Azure portal](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).</span></span>

<span data-ttu-id="58c37-128">Se si desidera modificare le informazioni di un ospite, è possibile [aggiungere o aggiornare le informazioni del profilo di un utente utilizzando Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="58c37-128">If you want to edit any of a guest's information, you can [Add or update a user's profile information using Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>

## <a name="see-also"></a><span data-ttu-id="58c37-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="58c37-129">See also</span></span>

[<span data-ttu-id="58c37-130">Bloccare gli utenti Guest da un gruppo specifico</span><span class="sxs-lookup"><span data-stu-id="58c37-130">Block guest users from a specific group</span></span>](https://docs.microsoft.com/microsoft-365/solutions/per-group-guest-access)

[<span data-ttu-id="58c37-131">Gestire l'appartenenza ai gruppi nell'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="58c37-131">Manage group membership in the Microsoft 365 admin center</span></span>](add-or-remove-members-from-groups.md)
  
[<span data-ttu-id="58c37-132">Recensioni di Azure Active Directory Access</span><span class="sxs-lookup"><span data-stu-id="58c37-132">Azure Active Directory access reviews</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[<span data-ttu-id="58c37-133">Set-AzureADUser</span><span class="sxs-lookup"><span data-stu-id="58c37-133">Set-AzureADUser</span></span>](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)
