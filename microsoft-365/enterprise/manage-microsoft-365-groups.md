---
title: Gestire gruppi di Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: Informazioni su come gestire i gruppi di Microsoft 365.
ms.openlocfilehash: 529bdb874661329497b103a1207b90625ad33a4b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911008"
---
# <a name="manage-microsoft-365-groups"></a><span data-ttu-id="a7114-103">Gestire gruppi di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a7114-103">Manage Microsoft 365 groups</span></span>

<span data-ttu-id="a7114-104">*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="a7114-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="a7114-105">È possibile gestire i gruppi di Microsoft 365 in diversi modi, a seconda della configurazione.</span><span class="sxs-lookup"><span data-stu-id="a7114-105">You can manage Microsoft 365 groups in several different ways, depending on your configuration.</span></span> <span data-ttu-id="a7114-106">È possibile gestire gli account utente nell'interfaccia di amministrazione di [Microsoft 365,](../admin/add-users/index.yml)In PowerShell, in Servizi di dominio Active Directory o nell'interfaccia di amministrazione di [Azure Active Directory (Azure AD).](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)</span><span class="sxs-lookup"><span data-stu-id="a7114-106">You can manage user accounts in the [Microsoft 365 admin center](../admin/add-users/index.yml), PowerShell, in Active Directory Domain Services (AD DS), or in the [Azure Active Directory (Azure AD) admin center](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal).</span></span> 

## <a name="plan-for-where-and-how-you-will-manage-your-groups"></a><span data-ttu-id="a7114-107">Pianificare dove e come gestire i gruppi</span><span class="sxs-lookup"><span data-stu-id="a7114-107">Plan for where and how you will manage your groups</span></span>

<span data-ttu-id="a7114-108">La posizione e la modalità di gestione degli account utente dipendono dal modello di identità che si desidera utilizzare per Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a7114-108">Where and how you can manage your user accounts depends on the identity model you want to use for your Microsoft 365.</span></span> <span data-ttu-id="a7114-109">I due modelli globali sono solo cloud e ibridi.</span><span class="sxs-lookup"><span data-stu-id="a7114-109">The two overall models are cloud-only and hybrid.</span></span>
  
### <a name="cloud-only"></a><span data-ttu-id="a7114-110">Solo cloud</span><span class="sxs-lookup"><span data-stu-id="a7114-110">Cloud-only</span></span>

<span data-ttu-id="a7114-111">È possibile creare e gestire gruppi con:</span><span class="sxs-lookup"><span data-stu-id="a7114-111">You create and manage groups with:</span></span>

- [<span data-ttu-id="a7114-112">L'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a7114-112">The Microsoft 365 admin center</span></span>](../admin/add-users/index.yml)
- [<span data-ttu-id="a7114-113">PowerShell</span><span class="sxs-lookup"><span data-stu-id="a7114-113">PowerShell</span></span>](maintain-group-membership-with-microsoft-365-powershell.md)
- [<span data-ttu-id="a7114-114">Interfaccia di amministrazione di Azure AD</span><span class="sxs-lookup"><span data-stu-id="a7114-114">Azure AD admin center</span></span>](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    
### <a name="hybrid"></a><span data-ttu-id="a7114-115">Ibrido</span><span class="sxs-lookup"><span data-stu-id="a7114-115">Hybrid</span></span>

<span data-ttu-id="a7114-116">I gruppi di Servizi di dominio Active Directory vengono sincronizzati con Microsoft 365 da Servizi di dominio Active Directory, quindi è necessario usare gli strumenti di Servizi di dominio Active Directory locali per gestire questi gruppi.</span><span class="sxs-lookup"><span data-stu-id="a7114-116">AD DS groups are synchronized with Microsoft 365 from AD DS, so you must use on-premises AD DS tools to manage these groups.</span></span>

<span data-ttu-id="a7114-117">È inoltre possibile creare e gestire gruppi di Azure AD separati dai gruppi di Servizi di dominio Active Directory, ma che possono contenere utenti e gruppi di Servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a7114-117">You can also create and manage Azure AD groups that are separate from AD DS groups but can contain users and groups from AD DS.</span></span> <span data-ttu-id="a7114-118">In questo caso, è possibile utilizzare:</span><span class="sxs-lookup"><span data-stu-id="a7114-118">In this case, you can use:</span></span>

- [<span data-ttu-id="a7114-119">L'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a7114-119">The Microsoft 365 admin center</span></span>](../admin/add-users/index.yml)
- [<span data-ttu-id="a7114-120">PowerShell</span><span class="sxs-lookup"><span data-stu-id="a7114-120">PowerShell</span></span>](maintain-group-membership-with-microsoft-365-powershell.md)
- [<span data-ttu-id="a7114-121">Interfaccia di amministrazione di Azure AD</span><span class="sxs-lookup"><span data-stu-id="a7114-121">Azure AD admin center</span></span>](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)

## <a name="allow-users-to-create-and-manage-their-own-groups"></a><span data-ttu-id="a7114-122">Consentire agli utenti di creare e gestire i propri gruppi</span><span class="sxs-lookup"><span data-stu-id="a7114-122">Allow users to create and manage their own groups</span></span>

<span data-ttu-id="a7114-123">Azure AD consente i gruppi che possono essere gestiti dai proprietari dei gruppi anziché dagli amministratori IT.</span><span class="sxs-lookup"><span data-stu-id="a7114-123">Azure AD allows groups that can be managed by group owners instead of IT administrators.</span></span> <span data-ttu-id="a7114-124">Detta *gestione dei gruppi in modalità self-service*, questa caratteristica consente ai proprietari del gruppo a cui non sono stati assegnati ruoli di amministrazione per creare e gestire gruppi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="a7114-124">Known as *self-service group management*, this feature allows group owners who are not assigned an administrative role to create and manage security groups.</span></span> 

<span data-ttu-id="a7114-p105">Gli utenti possono richiedere l'appartenenza a un gruppo di sicurezza e la richiesta passa al proprietario del gruppo invece che a un amministratore IT. Ciò permette che il controllo quotidiano dell'appartenenza al gruppo sia delegato ai proprietari del team, di progetto o aziendali che capiscano l'uso del gruppo e che possono gestirne l'appartenenza.</span><span class="sxs-lookup"><span data-stu-id="a7114-p105">Users can request membership in a security group and that request goes to the group owner, rather than an IT administrator. This allows the day-to-day control of group membership to be delegated to team, project, or business owners who understand the business use for the group and can manage its membership.</span></span>

>[!Note]
><span data-ttu-id="a7114-127">La gestione dei gruppi in modalità self-service è disponibile solo per specifici gruppi di sicurezza di Azure AD e Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a7114-127">Self-service group management is available only for Azure AD security and Microsoft 365 groups.</span></span> <span data-ttu-id="a7114-128">Non è disponibile per gruppi abilitati alla posta, liste di distribuzione o gruppi sincronizzati da Servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a7114-128">It is not available for mail-enabled groups, distribution lists, or any group that has been synchronized from AD DS.</span></span>
>

<span data-ttu-id="a7114-129">Per ulteriori informazioni, vedere le [istruzioni per configurare un gruppo Azure AD per la gestione in modalità self-service](/azure/active-directory/active-directory-accessmanagement-self-service-group-management).</span><span class="sxs-lookup"><span data-stu-id="a7114-129">For more information, see the [instructions to configure an Azure AD group for self-service management](/azure/active-directory/active-directory-accessmanagement-self-service-group-management).</span></span>

## <a name="set-up-dynamic-group-membership"></a><span data-ttu-id="a7114-130">Configurare l'appartenenza a gruppi dinamici</span><span class="sxs-lookup"><span data-stu-id="a7114-130">Set up dynamic group membership</span></span>

<span data-ttu-id="a7114-131">Azure AD supporta la configurazione di una serie di regole che aggiungono o rimuovono automaticamente gli account utente come membri di un gruppo di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="a7114-131">Azure AD supports configuring a series of rules that automatically add or remove user accounts as members of an Azure AD group.</span></span> <span data-ttu-id="a7114-132">Questa operazione è denominata *appartenenza dinamica al gruppo*.</span><span class="sxs-lookup"><span data-stu-id="a7114-132">This is known as *dynamic group membership*.</span></span> <span data-ttu-id="a7114-133">Le regole si basano sugli attributi dell’account utente, come il reparto o paese.</span><span class="sxs-lookup"><span data-stu-id="a7114-133">The rules are based on user account attributes, such as Department or Country.</span></span>

<span data-ttu-id="a7114-134">Ecco come vengono applicate le regole:</span><span class="sxs-lookup"><span data-stu-id="a7114-134">Here's how the rules are applied:</span></span>

- <span data-ttu-id="a7114-135">Se un nuovo account utente è conforme a tutte le regole relative al gruppo, può essere aggiunto come membro.</span><span class="sxs-lookup"><span data-stu-id="a7114-135">If a new user account matches all the rules for the group, it becomes a member.</span></span>
- <span data-ttu-id="a7114-136">Se un account utente non è un membro del gruppo, ma i suoi attributi vengono modificati per soddisfare le regole del gruppo, allora può essere aggiunto come membro.</span><span class="sxs-lookup"><span data-stu-id="a7114-136">If a user account isn't a member of the group, but its attributes change so that it matches all the rules for the group, it becomes a member of that group.</span></span>
- <span data-ttu-id="a7114-137">Se un account utente non è conforme alle regole del gruppo, non può essere aggiunto come membro.</span><span class="sxs-lookup"><span data-stu-id="a7114-137">If a user account doesn't match all the rules for the group, it isn't added to the group.</span></span>
- <span data-ttu-id="a7114-138">Se un account utente è già membro del gruppo, ma i suoi attributi vengono modificati in modo da non essere più conformi alle regole, l'account verrà rimosso dal gruppo.</span><span class="sxs-lookup"><span data-stu-id="a7114-138">If a user account is a member of the group, but its attributes change so that it no longer matches all the rules for the group, it is removed as a member of the group.</span></span>

<span data-ttu-id="a7114-p108">Per utilizzare l'appartenenza dinamica, è necessario determinare i set di gruppi che possiedono un set comune di attributi di account utente. Per esempio, tutti i membri del reparto Vendite dovrebbero far parte del gruppo Vendite di Azure AD, avendo impostato l'attributo Reparto dell'account utente su "Vendite".</span><span class="sxs-lookup"><span data-stu-id="a7114-p108">To use dynamic membership, you must first determine the sets of groups that have a common set of user account attributes. For example, all members of the Sales department should be in the Sales Azure AD group, based on the user account attribute Department set to "Sales".</span></span>

<span data-ttu-id="a7114-141">Vedere le [istruzioni per creare e configurare le regole per un gruppo dinamico di Azure AD](/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="a7114-141">See the [instructions to create and configure the rules for a dynamic Azure AD group](/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).</span></span>

## <a name="set-up-automatic-licensing"></a><span data-ttu-id="a7114-142">Configurare l'assegnazione automatica delle licenze</span><span class="sxs-lookup"><span data-stu-id="a7114-142">Set up automatic licensing</span></span>

<span data-ttu-id="a7114-143">È possibile configurare i gruppi di sicurezza in Azure AD per assegnare automaticamente le licenze da un set di sottoscrizioni a tutti i membri del gruppo.</span><span class="sxs-lookup"><span data-stu-id="a7114-143">You can configure security groups in Azure AD to automatically assign licenses from a set of subscriptions to all the members of the group.</span></span> <span data-ttu-id="a7114-144">Questa operazione è denominata *licenze basate sui gruppi*.</span><span class="sxs-lookup"><span data-stu-id="a7114-144">This is known as *group-based licensing*.</span></span> <span data-ttu-id="a7114-145">Se un account utente viene aggiunto o rimosso dal gruppo, le licenze per gli abbonamenti del gruppo verranno automaticamente assegnate o rimosse dall'account utente.</span><span class="sxs-lookup"><span data-stu-id="a7114-145">If a user account is added to or removed from the group, the licenses for the group's subscriptions will be automatically assigned or unassigned from the user account.</span></span>

<span data-ttu-id="a7114-146">Per Microsoft 365 Enterprise è necessario configurare i gruppi di sicurezza di Azure AD per assegnare la licenza di Microsoft 365 Enterprise appropriata.</span><span class="sxs-lookup"><span data-stu-id="a7114-146">For Microsoft 365 Enterprise, you'll configure Azure AD security groups to assign the appropriate Microsoft 365 Enterprise license.</span></span>

<span data-ttu-id="a7114-147">Assicurarsi di avere a disposizione abbastanza licenze per tutti i membri del gruppo.</span><span class="sxs-lookup"><span data-stu-id="a7114-147">Make sure you have enough licenses for all the group members.</span></span> <span data-ttu-id="a7114-148">Se le licenze a disposizione terminano, i nuovi utenti non potranno ottenerne una finché non ne saranno di nuovo disponibili.</span><span class="sxs-lookup"><span data-stu-id="a7114-148">If you run out of licenses, new users won't be assigned licenses until licenses become available.</span></span>

>[!Note]
><span data-ttu-id="a7114-149">Non è necessario configurare l'assegnazione delle licenze basate su gruppo per i gruppi contenenti account Azure business to business (B2B).</span><span class="sxs-lookup"><span data-stu-id="a7114-149">You should not configure group-based licensing for groups that contain Azure business to business (B2B) accounts.</span></span>
>

<span data-ttu-id="a7114-150">Per altre informazioni, vedi Nozioni di base sulle licenze basate su [gruppo in Azure AD.](/azure/active-directory/active-directory-licensing-whatis-azure-portal)</span><span class="sxs-lookup"><span data-stu-id="a7114-150">For more information, see [Group-based licensing basics in Azure AD](/azure/active-directory/active-directory-licensing-whatis-azure-portal).</span></span>

<span data-ttu-id="a7114-151">Vedere le [istruzioni per configurare le licenze basate su gruppo per un gruppo di sicurezza di Azure.](/azure/active-directory/active-directory-licensing-group-assignment-azure-portal)</span><span class="sxs-lookup"><span data-stu-id="a7114-151">See the [instructions to configure group-based licensing for an Azure security group](/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).</span></span>