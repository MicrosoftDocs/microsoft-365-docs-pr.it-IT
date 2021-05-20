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
description: Informazioni su come aggiungere guest a un Microsoft 365, visualizzare gli utenti guest e usare PowerShell per controllare l'accesso guest.
ms.openlocfilehash: c52f0094e724040b71d5d72cded049fed57e3969
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571938"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a><span data-ttu-id="de43d-103">Gestire l'accesso guest in Microsoft 365 gruppi</span><span class="sxs-lookup"><span data-stu-id="de43d-103">Manage guest access in Microsoft 365 groups</span></span>

<span data-ttu-id="de43d-104">Per impostazione predefinita, l'accesso guest per Microsoft 365 è attivato per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="de43d-104">By default, guest access for Microsoft 365 groups is turned on for your organization.</span></span> <span data-ttu-id="de43d-105">Gli amministratori possono controllare se consentire l'accesso guest ai gruppi per l'intera organizzazione o per singoli gruppi.</span><span class="sxs-lookup"><span data-stu-id="de43d-105">Admins can control whether to allow guest access to groups for their whole organization or for individual groups.</span></span>

<span data-ttu-id="de43d-106">Quando è attivata, i membri del gruppo possono invitare utenti guest a un gruppo Microsoft 365 tramite Outlook sul Web.</span><span class="sxs-lookup"><span data-stu-id="de43d-106">When it's turned on, group members can invite guest users to a Microsoft 365 group through Outlook on Web.</span></span> <span data-ttu-id="de43d-107">Gli inviti vengono inviati al proprietario del gruppo per l'approvazione.</span><span class="sxs-lookup"><span data-stu-id="de43d-107">Invitations are sent to the group owner for approval.</span></span>

<span data-ttu-id="de43d-108">Dopo l'approvazione, l'utente guest viene aggiunto alla directory e al gruppo.</span><span class="sxs-lookup"><span data-stu-id="de43d-108">Once approved, the guest user is added to the directory and the group.</span></span>

> [!Note]
> <span data-ttu-id="de43d-109">Yammer Enterprise le reti che sono in modalità nativa o [l'area geografica dell'UE](/yammer/manage-security-and-compliance/manage-data-compliance) non supportano i guest di rete.</span><span class="sxs-lookup"><span data-stu-id="de43d-109">Yammer Enterprise networks that are in Native Mode or the [EU Geo](/yammer/manage-security-and-compliance/manage-data-compliance) do not support network guests.</span></span>
> <span data-ttu-id="de43d-110">Microsoft 365 I Yammer connessi non supportano attualmente l'accesso guest, ma è possibile creare gruppi esterni non connessi nella Yammer rete.</span><span class="sxs-lookup"><span data-stu-id="de43d-110">Microsoft 365 Connected Yammer groups do not currently support guest access, but you can create non-connected, external groups in your Yammer network.</span></span> <span data-ttu-id="de43d-111">Per istruzioni, vedere Create [and manage external groups in Yammer.](/yammer/work-with-external-users/create-and-manage-external-groups)</span><span class="sxs-lookup"><span data-stu-id="de43d-111">See [Create and manage external groups in Yammer](/yammer/work-with-external-users/create-and-manage-external-groups) for instructions.</span></span>

<span data-ttu-id="de43d-112">L'accesso guest nei gruppi viene spesso utilizzato come parte di uno scenario più ampio che include SharePoint o Teams.</span><span class="sxs-lookup"><span data-stu-id="de43d-112">Guest access in groups is often used as part of a broader scenario that includes SharePoint or Teams.</span></span> <span data-ttu-id="de43d-113">Questi servizi hanno le proprie impostazioni di condivisione guest.</span><span class="sxs-lookup"><span data-stu-id="de43d-113">These services have their own guest sharing settings.</span></span> <span data-ttu-id="de43d-114">Per istruzioni complete sulla configurazione della condivisione guest tra gruppi, SharePoint e Teams, vedere:</span><span class="sxs-lookup"><span data-stu-id="de43d-114">For complete instructions for setting up guest sharing across groups, SharePoint, and Teams, see:</span></span>

- [<span data-ttu-id="de43d-115">Collaborare con gli utenti guest a un sito</span><span class="sxs-lookup"><span data-stu-id="de43d-115">Collaborate with guests in a site</span></span>](../../solutions/collaborate-in-site.md)
- [<span data-ttu-id="de43d-116">Collaborare con gli utenti guest in un team</span><span class="sxs-lookup"><span data-stu-id="de43d-116">Collaborate with guests in a team</span></span>](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a><span data-ttu-id="de43d-117">Gestire l'accesso guest ai gruppi</span><span class="sxs-lookup"><span data-stu-id="de43d-117">Manage groups guest access</span></span>

<span data-ttu-id="de43d-118">Se si desidera abilitare o disabilitare l'accesso guest nei gruppi, è possibile farlo nell'Microsoft 365 di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="de43d-118">If you want to enable or disable guest access in groups, you can do so in the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="de43d-119">Nell'interfaccia di amministrazione, andare a Mostra tutte **Impostazioni** impostazioni dell'organizzazione e nella scheda Servizi selezionare Microsoft 365 \>  \>  **gruppi**. </span><span class="sxs-lookup"><span data-stu-id="de43d-119">In the admin center, go to **Show all** \> **Settings** \> **Org settings** and on the **Services** tab, select **Microsoft 365 groups**.</span></span>
  
2. <span data-ttu-id="de43d-120">Nella pagina **Microsoft 365** gruppi scegliere se consentire alle persone esterne all'organizzazione di accedere alle risorse del gruppo o consentire ai proprietari di gruppi di aggiungere persone esterne all'organizzazione ai gruppi.</span><span class="sxs-lookup"><span data-stu-id="de43d-120">On the **Microsoft 365 Groups** page, choose whether you want to let people outside your organization access group resources or let group owners add people outside your organization to groups.</span></span>

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a><span data-ttu-id="de43d-121">Aggiungere utenti guest a un Microsoft 365 dall'interfaccia di amministrazione</span><span class="sxs-lookup"><span data-stu-id="de43d-121">Add guests to a Microsoft 365 group from the admin center</span></span>

<span data-ttu-id="de43d-122">Se il guest esiste già nella directory, è possibile aggiungerlo ai gruppi dall'Microsoft 365 di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="de43d-122">If the guest already exists in your directory, you can add them to your groups from the Microsoft 365 admin center.</span></span> <span data-ttu-id="de43d-123">I gruppi con appartenenza dinamica devono [essere gestiti in Azure Active Directory](/azure/active-directory/enterprise-users/groups-create-rule).</span><span class="sxs-lookup"><span data-stu-id="de43d-123">(Groups with dynamic membership must be [managed in Azure Active Directory](/azure/active-directory/enterprise-users/groups-create-rule).)</span></span>
  
1. <span data-ttu-id="de43d-124">Nell'interfaccia di amministrazione passare alla **pagina**  >  **Gruppi di** gruppi.</span><span class="sxs-lookup"><span data-stu-id="de43d-124">In the admin center, go to the **Groups** > **Groups** page.</span></span>
  
2. <span data-ttu-id="de43d-125">Fare clic sul gruppo a cui si desidera aggiungere il guest e selezionare **Visualizza tutti** e gestisci membri nella **scheda** Membri.</span><span class="sxs-lookup"><span data-stu-id="de43d-125">Click the group you want to add the guest to, and select **View all and manage members** on the **Members** tab.</span></span> 
  
4. <span data-ttu-id="de43d-126">Selezionare **Aggiungi membri** e scegliere il nome del guest che si desidera aggiungere.</span><span class="sxs-lookup"><span data-stu-id="de43d-126">Select **Add members**, and choose the name of the guest you want to add.</span></span>
    
5. <span data-ttu-id="de43d-127">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="de43d-127">Select **Save**.</span></span>

<span data-ttu-id="de43d-128">Se si desidera aggiungere direttamente un guest alla directory, è possibile aggiungere Azure Active Directory utenti di collaborazione [B2B nel portale di Azure.](/azure/active-directory/b2b/add-users-administrator)</span><span class="sxs-lookup"><span data-stu-id="de43d-128">If you want to add a guest to the directory directly, you can [Add Azure Active Directory B2B collaboration users in the Azure portal](/azure/active-directory/b2b/add-users-administrator).</span></span>

<span data-ttu-id="de43d-129">Se si desidera modificare le informazioni di un guest, è possibile aggiungere o aggiornare le informazioni del profilo di un utente [utilizzando Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="de43d-129">If you want to edit any of a guest's information, you can [Add or update a user's profile information using Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>

## <a name="related-content"></a><span data-ttu-id="de43d-130">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="de43d-130">Related content</span></span>

<span data-ttu-id="de43d-131">[Bloccare gli utenti guest da un gruppo specifico](../../solutions/per-group-guest-access.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="de43d-131">[Block guest users from a specific group](../../solutions/per-group-guest-access.md) (article)</span></span>

<span data-ttu-id="de43d-132">[Gestire l'appartenenza ai gruppi nell'Microsoft 365 di amministrazione](add-or-remove-members-from-groups.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="de43d-132">[Manage group membership in the Microsoft 365 admin center](add-or-remove-members-from-groups.md) (article)</span></span>
  
<span data-ttu-id="de43d-133">[Azure Active Directory access review](/azure/active-directory/active-directory-azure-ad-controls-perform-access-review) (articolo)</span><span class="sxs-lookup"><span data-stu-id="de43d-133">[Azure Active Directory access reviews](/azure/active-directory/active-directory-azure-ad-controls-perform-access-review) (article)</span></span>

<span data-ttu-id="de43d-134">[Set-AzureADUser](/powershell/module/azuread/set-azureaduser) (articolo)</span><span class="sxs-lookup"><span data-stu-id="de43d-134">[Set-AzureADUser](/powershell/module/azuread/set-azureaduser) (article)</span></span>