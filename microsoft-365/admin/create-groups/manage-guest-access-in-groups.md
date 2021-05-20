---
title: Gestire l'accesso guest in Microsoft 365 gruppi
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
description: Informazioni su come aggiungere ospiti a un gruppo Microsoft 365, visualizzare utenti guest e usare PowerShell per controllare l'accesso guest.
ms.openlocfilehash: c52f0094e724040b71d5d72cded049fed57e3969
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571938"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a><span data-ttu-id="46a4c-103">Gestire l'accesso guest in Microsoft 365 gruppi</span><span class="sxs-lookup"><span data-stu-id="46a4c-103">Manage guest access in Microsoft 365 groups</span></span>

<span data-ttu-id="46a4c-104">Per impostazione predefinita, l'accesso guest per Microsoft 365 gruppi è attivato per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="46a4c-104">By default, guest access for Microsoft 365 groups is turned on for your organization.</span></span> <span data-ttu-id="46a4c-105">Gli amministratori possono controllare se consentire l'accesso guest ai gruppi per l'intera organizzazione o per i singoli gruppi.</span><span class="sxs-lookup"><span data-stu-id="46a4c-105">Admins can control whether to allow guest access to groups for their whole organization or for individual groups.</span></span>

<span data-ttu-id="46a4c-106">Quando è attivato, i membri del gruppo possono invitare utenti guest a un gruppo Microsoft 365 gruppo tramite Outlook sul Web.</span><span class="sxs-lookup"><span data-stu-id="46a4c-106">When it's turned on, group members can invite guest users to a Microsoft 365 group through Outlook on Web.</span></span> <span data-ttu-id="46a4c-107">Gli inviti vengono inviati al proprietario del gruppo per l'approvazione.</span><span class="sxs-lookup"><span data-stu-id="46a4c-107">Invitations are sent to the group owner for approval.</span></span>

<span data-ttu-id="46a4c-108">Una volta approvato, l'utente guest viene aggiunto alla directory e al gruppo.</span><span class="sxs-lookup"><span data-stu-id="46a4c-108">Once approved, the guest user is added to the directory and the group.</span></span>

> [!Note]
> <span data-ttu-id="46a4c-109">Yammer Enterprise reti native o EU [Geo non supportano](/yammer/manage-security-and-compliance/manage-data-compliance) gli ospiti della rete.</span><span class="sxs-lookup"><span data-stu-id="46a4c-109">Yammer Enterprise networks that are in Native Mode or the [EU Geo](/yammer/manage-security-and-compliance/manage-data-compliance) do not support network guests.</span></span>
> <span data-ttu-id="46a4c-110">Microsoft 365 I Yammer di accesso non supportano attualmente l'accesso guest, ma è possibile creare gruppi esterni non connessi nella rete Yammer rete.</span><span class="sxs-lookup"><span data-stu-id="46a4c-110">Microsoft 365 Connected Yammer groups do not currently support guest access, but you can create non-connected, external groups in your Yammer network.</span></span> <span data-ttu-id="46a4c-111">Per [istruzioni, vedere Creare e gestire gruppi Yammer](/yammer/work-with-external-users/create-and-manage-external-groups) in un'80 esterne.</span><span class="sxs-lookup"><span data-stu-id="46a4c-111">See [Create and manage external groups in Yammer](/yammer/work-with-external-users/create-and-manage-external-groups) for instructions.</span></span>

<span data-ttu-id="46a4c-112">L'accesso guest nei gruppi viene spesso utilizzato come parte di uno scenario più ampio che include SharePoint o Teams.</span><span class="sxs-lookup"><span data-stu-id="46a4c-112">Guest access in groups is often used as part of a broader scenario that includes SharePoint or Teams.</span></span> <span data-ttu-id="46a4c-113">Questi servizi hanno le proprie impostazioni di condivisione degli ospiti.</span><span class="sxs-lookup"><span data-stu-id="46a4c-113">These services have their own guest sharing settings.</span></span> <span data-ttu-id="46a4c-114">Per istruzioni complete sulla configurazione della condivisione degli ospiti tra gruppi, SharePoint e Teams, vedere:</span><span class="sxs-lookup"><span data-stu-id="46a4c-114">For complete instructions for setting up guest sharing across groups, SharePoint, and Teams, see:</span></span>

- [<span data-ttu-id="46a4c-115">Collaborare con gli utenti guest a un sito</span><span class="sxs-lookup"><span data-stu-id="46a4c-115">Collaborate with guests in a site</span></span>](../../solutions/collaborate-in-site.md)
- [<span data-ttu-id="46a4c-116">Collaborare con gli utenti guest in un team</span><span class="sxs-lookup"><span data-stu-id="46a4c-116">Collaborate with guests in a team</span></span>](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a><span data-ttu-id="46a4c-117">Gestire l'accesso guest dei gruppi</span><span class="sxs-lookup"><span data-stu-id="46a4c-117">Manage groups guest access</span></span>

<span data-ttu-id="46a4c-118">Se si desidera abilitare o disabilitare l'accesso guest nei gruppi, è possibile farlo nell'interfaccia Microsoft 365 di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="46a4c-118">If you want to enable or disable guest access in groups, you can do so in the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="46a4c-119">Nell'interfaccia di amministrazione passare **a** \> **Mostra tutte le Impostazioni** \> **dell'organizzazione** e **nella scheda** Servizi selezionare **Microsoft 365 gruppi**.</span><span class="sxs-lookup"><span data-stu-id="46a4c-119">In the admin center, go to **Show all** \> **Settings** \> **Org settings** and on the **Services** tab, select **Microsoft 365 groups**.</span></span>
  
2. <span data-ttu-id="46a4c-120">Nella pagina **Microsoft 365 gruppi scegliere se** si desidera che persone esterne all'organizzazione accedono alle risorse del gruppo o che i proprietari dei gruppi aggigano persone esterne all'organizzazione ai gruppi.</span><span class="sxs-lookup"><span data-stu-id="46a4c-120">On the **Microsoft 365 Groups** page, choose whether you want to let people outside your organization access group resources or let group owners add people outside your organization to groups.</span></span>

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a><span data-ttu-id="46a4c-121">Aggiungere ospiti a un gruppo Microsoft 365 dall'interfaccia di amministrazione</span><span class="sxs-lookup"><span data-stu-id="46a4c-121">Add guests to a Microsoft 365 group from the admin center</span></span>

<span data-ttu-id="46a4c-122">Se l'ospite esiste già nella directory, è possibile aggiungerlo ai gruppi dall'interfaccia di Microsoft 365 di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="46a4c-122">If the guest already exists in your directory, you can add them to your groups from the Microsoft 365 admin center.</span></span> <span data-ttu-id="46a4c-123">I gruppi con appartenenza dinamica devono [essere gestiti in Azure Active Directory](/azure/active-directory/enterprise-users/groups-create-rule).</span><span class="sxs-lookup"><span data-stu-id="46a4c-123">(Groups with dynamic membership must be [managed in Azure Active Directory](/azure/active-directory/enterprise-users/groups-create-rule).)</span></span>
  
1. <span data-ttu-id="46a4c-124">Nell'interfaccia di amministrazione passare alla **pagina**  >  **Gruppi** gruppi.</span><span class="sxs-lookup"><span data-stu-id="46a4c-124">In the admin center, go to the **Groups** > **Groups** page.</span></span>
  
2. <span data-ttu-id="46a4c-125">Fare clic sul gruppo a cui si vuole aggiungere l'ospite e **selezionare Visualizza tutti e gestisci** membri nella **scheda** Membri.</span><span class="sxs-lookup"><span data-stu-id="46a4c-125">Click the group you want to add the guest to, and select **View all and manage members** on the **Members** tab.</span></span> 
  
4. <span data-ttu-id="46a4c-126">Selezionare **Aggiungi membri** e scegliere il nome dell'ospite da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="46a4c-126">Select **Add members**, and choose the name of the guest you want to add.</span></span>
    
5. <span data-ttu-id="46a4c-127">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="46a4c-127">Select **Save**.</span></span>

<span data-ttu-id="46a4c-128">Se si desidera aggiungere direttamente un guest alla directory, è possibile [aggiungere Azure Active Directory di collaborazione B2B nel portale di Azure](/azure/active-directory/b2b/add-users-administrator).</span><span class="sxs-lookup"><span data-stu-id="46a4c-128">If you want to add a guest to the directory directly, you can [Add Azure Active Directory B2B collaboration users in the Azure portal](/azure/active-directory/b2b/add-users-administrator).</span></span>

<span data-ttu-id="46a4c-129">Se si desidera modificare una delle informazioni di un ospite, è possibile [aggiungere o aggiornare le informazioni del profilo di un utente utilizzando Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="46a4c-129">If you want to edit any of a guest's information, you can [Add or update a user's profile information using Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>

## <a name="related-content"></a><span data-ttu-id="46a4c-130">Contenuti correlati</span><span class="sxs-lookup"><span data-stu-id="46a4c-130">Related content</span></span>

<span data-ttu-id="46a4c-131">[Bloccare gli utenti guest da un gruppo specifico](../../solutions/per-group-guest-access.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="46a4c-131">[Block guest users from a specific group](../../solutions/per-group-guest-access.md) (article)</span></span>

<span data-ttu-id="46a4c-132">[Gestire l'appartenenza a gruppi nell'Microsoft 365 di amministrazione](add-or-remove-members-from-groups.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="46a4c-132">[Manage group membership in the Microsoft 365 admin center](add-or-remove-members-from-groups.md) (article)</span></span>
  
<span data-ttu-id="46a4c-133">[Azure Active Directory di accesso (articolo)](/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)</span><span class="sxs-lookup"><span data-stu-id="46a4c-133">[Azure Active Directory access reviews](/azure/active-directory/active-directory-azure-ad-controls-perform-access-review) (article)</span></span>

<span data-ttu-id="46a4c-134">[Set-AzureADUser](/powershell/module/azuread/set-azureaduser) (articolo)</span><span class="sxs-lookup"><span data-stu-id="46a4c-134">[Set-AzureADUser](/powershell/module/azuread/set-azureaduser) (article)</span></span>