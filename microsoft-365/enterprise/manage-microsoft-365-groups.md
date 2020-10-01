---
title: Gestire i gruppi di Microsoft 365
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
ms.openlocfilehash: a01bf5dcc0b87cbdce8d7044b666cfb3a16a5aa9
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328521"
---
# <a name="manage-microsoft-365-groups"></a><span data-ttu-id="b4bdb-103">Gestire i gruppi di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b4bdb-103">Manage Microsoft 365 groups</span></span>

<span data-ttu-id="b4bdb-104">*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.</span><span class="sxs-lookup"><span data-stu-id="b4bdb-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="b4bdb-105">È possibile gestire i gruppi Microsoft 365 in vari modi, a seconda della configurazione.</span><span class="sxs-lookup"><span data-stu-id="b4bdb-105">You can manage Microsoft 365 groups in several different ways, depending on your configuration.</span></span> <span data-ttu-id="b4bdb-106">È possibile gestire gli account utente nell'interfaccia di [amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users/), PowerShell, in servizi di dominio Active Directory (ad DS) o nell'interfaccia di amministrazione di Azure [Active Directory (Azure ad)](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="b4bdb-106">You can manage user accounts in the [Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/add-users/), PowerShell, in Active Directory Domain Services (AD DS), or in the [Azure Active Directory (Azure AD) admin center](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal).</span></span> 

## <a name="plan-for-where-and-how-you-will-manage-your-groups"></a><span data-ttu-id="b4bdb-107">Pianificare la posizione e la modalità di gestione dei gruppi</span><span class="sxs-lookup"><span data-stu-id="b4bdb-107">Plan for where and how you will manage your groups</span></span>

<span data-ttu-id="b4bdb-108">Il percorso e la modalità di gestione degli account utente dipendono dal modello di identità che si desidera utilizzare per Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b4bdb-108">Where and how you can manage your user accounts depends on the identity model you want to use for your Microsoft 365.</span></span> <span data-ttu-id="b4bdb-109">I due modelli complessivi sono solo basati sul cloud e sull'ambiente ibrido.</span><span class="sxs-lookup"><span data-stu-id="b4bdb-109">The two overall models are cloud-only and hybrid.</span></span>
  
### <a name="cloud-only"></a><span data-ttu-id="b4bdb-110">Solo cloud</span><span class="sxs-lookup"><span data-stu-id="b4bdb-110">Cloud-only</span></span>

<span data-ttu-id="b4bdb-111">È possibile creare e gestire gruppi con:</span><span class="sxs-lookup"><span data-stu-id="b4bdb-111">You create and manage groups with:</span></span>

- [<span data-ttu-id="b4bdb-112">L'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b4bdb-112">The Microsoft 365 admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/)
- [<span data-ttu-id="b4bdb-113">PowerShell</span><span class="sxs-lookup"><span data-stu-id="b4bdb-113">PowerShell</span></span>](maintain-group-membership-with-microsoft-365-powershell.md)
- [<span data-ttu-id="b4bdb-114">Interfaccia di amministrazione di Azure AD</span><span class="sxs-lookup"><span data-stu-id="b4bdb-114">Azure AD admin center</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    
### <a name="hybrid"></a><span data-ttu-id="b4bdb-115">Ibrido</span><span class="sxs-lookup"><span data-stu-id="b4bdb-115">Hybrid</span></span>

<span data-ttu-id="b4bdb-116">I gruppi di servizi di dominio Active Directory vengono sincronizzati con Microsoft 365 da servizi di dominio Active Directory, pertanto è necessario utilizzare gli strumenti di AD DS locali per gestire questi gruppi.</span><span class="sxs-lookup"><span data-stu-id="b4bdb-116">AD DS groups are synchronized with Microsoft 365 from AD DS, so you must use on-premises AD DS tools to manage these groups.</span></span>

<span data-ttu-id="b4bdb-117">È inoltre possibile creare e gestire i gruppi di Azure AD che sono separati dai gruppi di servizi di dominio Active Directory, ma possono contenere utenti e gruppi di servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b4bdb-117">You can also create and manage Azure AD groups that are separate from AD DS groups but can contain users and groups from AD DS.</span></span> <span data-ttu-id="b4bdb-118">In questo caso, è possibile utilizzare:</span><span class="sxs-lookup"><span data-stu-id="b4bdb-118">In this case, you can use:</span></span>

- [<span data-ttu-id="b4bdb-119">L'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b4bdb-119">The Microsoft 365 admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/)
- [<span data-ttu-id="b4bdb-120">PowerShell</span><span class="sxs-lookup"><span data-stu-id="b4bdb-120">PowerShell</span></span>](maintain-group-membership-with-microsoft-365-powershell.md)
- [<span data-ttu-id="b4bdb-121">Interfaccia di amministrazione di Azure AD</span><span class="sxs-lookup"><span data-stu-id="b4bdb-121">Azure AD admin center</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)

## <a name="allow-users-to-create-and-manage-their-own-groups"></a><span data-ttu-id="b4bdb-122">Consentire agli utenti di creare e gestire i propri gruppi</span><span class="sxs-lookup"><span data-stu-id="b4bdb-122">Allow users to create and manage their own groups</span></span>

<span data-ttu-id="b4bdb-123">Azure AD consente ai gruppi che possono essere gestiti dai proprietari del gruppo invece degli amministratori IT.</span><span class="sxs-lookup"><span data-stu-id="b4bdb-123">Azure AD allows groups that can be managed by group owners instead of IT administrators.</span></span> <span data-ttu-id="b4bdb-124">Detta *gestione dei gruppi in modalità self-service*, questa caratteristica consente ai proprietari del gruppo a cui non sono stati assegnati ruoli di amministrazione per creare e gestire gruppi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="b4bdb-124">Known as *self-service group management*, this feature allows group owners who are not assigned an administrative role to create and manage security groups.</span></span> 

<span data-ttu-id="b4bdb-p105">Gli utenti possono richiedere l'appartenenza a un gruppo di sicurezza e la richiesta passa al proprietario del gruppo invece che a un amministratore IT. Ciò permette che il controllo quotidiano dell'appartenenza al gruppo sia delegato ai proprietari del team, di progetto o aziendali che capiscano l'uso del gruppo e che possono gestirne l'appartenenza.</span><span class="sxs-lookup"><span data-stu-id="b4bdb-p105">Users can request membership in a security group and that request goes to the group owner, rather than an IT administrator. This allows the day-to-day control of group membership to be delegated to team, project, or business owners who understand the business use for the group and can manage its membership.</span></span>

>[!Note]
><span data-ttu-id="b4bdb-127">La gestione dei gruppi in modalità self-service è disponibile solo per specifici gruppi di sicurezza di Azure AD e Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b4bdb-127">Self-service group management is available only for Azure AD security and Microsoft 365 groups.</span></span> <span data-ttu-id="b4bdb-128">Non è disponibile per i gruppi abilitati alla posta, le liste di distribuzione o qualsiasi gruppo sincronizzato da servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b4bdb-128">It is not available for mail-enabled groups, distribution lists, or any group that has been synchronized from AD DS.</span></span>
>

<span data-ttu-id="b4bdb-129">Per ulteriori informazioni, vedere le [istruzioni per configurare un gruppo Azure AD per la gestione in modalità self-service](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management).</span><span class="sxs-lookup"><span data-stu-id="b4bdb-129">For more information, see the [instructions to configure an Azure AD group for self-service management](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management).</span></span>

## <a name="set-up-dynamic-group-membership"></a><span data-ttu-id="b4bdb-130">Configurare l'appartenenza a gruppi dinamici</span><span class="sxs-lookup"><span data-stu-id="b4bdb-130">Set up dynamic group membership</span></span>

<span data-ttu-id="b4bdb-131">Azure AD supporta la configurazione di una serie di regole che aggiungono o rimuovono automaticamente gli account utente come membri di un gruppo di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="b4bdb-131">Azure AD supports configuring a series of rules that automatically add or remove user accounts as members of an Azure AD group.</span></span> <span data-ttu-id="b4bdb-132">Questa operazione è denominata *appartenenza dinamica al gruppo*.</span><span class="sxs-lookup"><span data-stu-id="b4bdb-132">This is known as *dynamic group membership*.</span></span> <span data-ttu-id="b4bdb-133">Le regole si basano sugli attributi dell’account utente, come il reparto o paese.</span><span class="sxs-lookup"><span data-stu-id="b4bdb-133">The rules are based on user account attributes, such as Department or Country.</span></span>

<span data-ttu-id="b4bdb-134">Ecco come vengono applicate le regole:</span><span class="sxs-lookup"><span data-stu-id="b4bdb-134">Here's how the rules are applied:</span></span>

- <span data-ttu-id="b4bdb-135">Se un nuovo account utente è conforme a tutte le regole relative al gruppo, può essere aggiunto come membro.</span><span class="sxs-lookup"><span data-stu-id="b4bdb-135">If a new user account matches all the rules for the group, it becomes a member.</span></span>
- <span data-ttu-id="b4bdb-136">Se un account utente non è un membro del gruppo, ma i suoi attributi vengono modificati per soddisfare le regole del gruppo, allora può essere aggiunto come membro.</span><span class="sxs-lookup"><span data-stu-id="b4bdb-136">If a user account isn't a member of the group, but its attributes change so that it matches all the rules for the group, it becomes a member of that group.</span></span>
- <span data-ttu-id="b4bdb-137">Se un account utente non è conforme alle regole del gruppo, non può essere aggiunto come membro.</span><span class="sxs-lookup"><span data-stu-id="b4bdb-137">If a user account doesn't match all the rules for the group, it isn't added to the group.</span></span>
- <span data-ttu-id="b4bdb-138">Se un account utente è già membro del gruppo, ma i suoi attributi vengono modificati in modo da non essere più conformi alle regole, l'account verrà rimosso dal gruppo.</span><span class="sxs-lookup"><span data-stu-id="b4bdb-138">If a user account is a member of the group, but its attributes change so that it no longer matches all the rules for the group, it is removed as a member of the group.</span></span>

<span data-ttu-id="b4bdb-p108">Per utilizzare l'appartenenza dinamica, è necessario determinare i set di gruppi che possiedono un set comune di attributi di account utente. Per esempio, tutti i membri del reparto Vendite dovrebbero far parte del gruppo Vendite di Azure AD, avendo impostato l'attributo Reparto dell'account utente su "Vendite".</span><span class="sxs-lookup"><span data-stu-id="b4bdb-p108">To use dynamic membership, you must first determine the sets of groups that have a common set of user account attributes. For example, all members of the Sales department should be in the Sales Azure AD group, based on the user account attribute Department set to "Sales".</span></span>

<span data-ttu-id="b4bdb-141">Vedere le [istruzioni per creare e configurare le regole per un gruppo dinamico di Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="b4bdb-141">See the [instructions to create and configure the rules for a dynamic Azure AD group](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).</span></span>

## <a name="set-up-automatic-licensing"></a><span data-ttu-id="b4bdb-142">Configurare l'assegnazione automatica delle licenze</span><span class="sxs-lookup"><span data-stu-id="b4bdb-142">Set up automatic licensing</span></span>

<span data-ttu-id="b4bdb-143">È possibile configurare i gruppi di sicurezza di Azure ad per assegnare automaticamente le licenze da un set di sottoscrizioni a tutti i membri del gruppo.</span><span class="sxs-lookup"><span data-stu-id="b4bdb-143">You can configure security groups in Azure AD to automatically assign licenses from a set of subscriptions to all the members of the group.</span></span> <span data-ttu-id="b4bdb-144">Questa operazione è denominata *licenze basate sui gruppi*.</span><span class="sxs-lookup"><span data-stu-id="b4bdb-144">This is known as *group-based licensing*.</span></span> <span data-ttu-id="b4bdb-145">Se un account utente viene aggiunto o rimosso dal gruppo, le licenze per gli abbonamenti del gruppo verranno automaticamente assegnate o rimosse dall'account utente.</span><span class="sxs-lookup"><span data-stu-id="b4bdb-145">If a user account is added to or removed from the group, the licenses for the group's subscriptions will be automatically assigned or unassigned from the user account.</span></span>

<span data-ttu-id="b4bdb-146">Per Microsoft 365 Enterprise è necessario configurare i gruppi di sicurezza di Azure AD per assegnare la licenza di Microsoft 365 Enterprise appropriata.</span><span class="sxs-lookup"><span data-stu-id="b4bdb-146">For Microsoft 365 Enterprise, you'll configure Azure AD security groups to assign the appropriate Microsoft 365 Enterprise license.</span></span>

<span data-ttu-id="b4bdb-147">Assicurarsi di avere a disposizione abbastanza licenze per tutti i membri del gruppo.</span><span class="sxs-lookup"><span data-stu-id="b4bdb-147">Make sure you have enough licenses for all the group members.</span></span> <span data-ttu-id="b4bdb-148">Se le licenze a disposizione terminano, i nuovi utenti non potranno ottenerne una finché non ne saranno di nuovo disponibili.</span><span class="sxs-lookup"><span data-stu-id="b4bdb-148">If you run out of licenses, new users won't be assigned licenses until licenses become available.</span></span>

>[!Note]
><span data-ttu-id="b4bdb-149">Non è necessario configurare l'assegnazione delle licenze basate su gruppo per i gruppi contenenti account Azure business to business (B2B).</span><span class="sxs-lookup"><span data-stu-id="b4bdb-149">You should not configure group-based licensing for groups that contain Azure business to business (B2B) accounts.</span></span>
>

<span data-ttu-id="b4bdb-150">Per ulteriori informazioni, vedere [nozioni di base sulla gestione delle licenze basate su gruppo in Azure ad](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="b4bdb-150">For more information, see [Group-based licensing basics in Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal).</span></span>

<span data-ttu-id="b4bdb-151">Vedere le [istruzioni per configurare la gestione delle licenze basate su gruppo per un gruppo di sicurezza di Azure](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="b4bdb-151">See the [instructions to configure group-based licensing for an Azure security group](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).</span></span>
