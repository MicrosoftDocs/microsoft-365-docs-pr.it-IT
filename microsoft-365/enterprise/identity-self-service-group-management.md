---
title: 'Passaggio 6: Usare i gruppi per facilitare la gestione'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 02/25/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Capire e configurare la gestione dei gruppi self-service di Azure AD.
ms.openlocfilehash: 9400e99ced45370600d1d5dcee4388ddef4250fe
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283525"
---
# <a name="step-6-use-groups-for-easier-management"></a><span data-ttu-id="082d4-103">Passaggio 6: Usare i gruppi per facilitare la gestione</span><span class="sxs-lookup"><span data-stu-id="082d4-103">Step 6: Use groups for easier management</span></span>

<a name="identity-self-service-groups"></a>
## <a name="allow-users-to-create-and-manage-their-own-groups"></a><span data-ttu-id="082d4-104">Consentire agli utenti di creare e gestire i propri gruppi</span><span class="sxs-lookup"><span data-stu-id="082d4-104">Allow users to create and manage their own groups</span></span>

<span data-ttu-id="082d4-105">*Questo passaggio è facoltativo e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="082d4-105">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="082d4-106">In questa sezione verranno identificati i gruppi di Azure Active Directory (AD Azure) che possono essere gestiti dai proprietari del gruppo invece che dagli amministratori IT.</span><span class="sxs-lookup"><span data-stu-id="082d4-106">In this section, you'll identify Azure Active Directory (Azure AD) groups that can be managed by group owners instead of IT administrators.</span></span> <span data-ttu-id="082d4-107">Detta *gestione dei gruppi in modalità self-service*, questa caratteristica consente ai proprietari del gruppo a cui non sono stati assegnati ruoli di amministrazione per creare e gestire gruppi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="082d4-107">In this step, you'll identify Azure Active Directory (AD) groups that can be managed by group owners instead of IT administrators. Known as *self-service group management*, this feature allows group owners who are not assigned an administrative role to create and manage security groups.</span></span> 

<span data-ttu-id="082d4-p102">Gli utenti possono richiedere l'appartenenza a un gruppo di sicurezza e la richiesta passa al proprietario del gruppo invece che a un amministratore IT. Ciò permette che il controllo quotidiano dell'appartenenza al gruppo sia delegato ai proprietari del team, di progetto o aziendali che capiscano l'uso del gruppo e che possono gestirne l'appartenenza.</span><span class="sxs-lookup"><span data-stu-id="082d4-p102">Users can request membership in a security group and that request goes to the group owner, rather than an IT administrator. This allows the day-to-day control of group membership to be delegated to team, project, or business owners who understand the business use for the group and can manage its membership.</span></span>

>[!Note]
><span data-ttu-id="082d4-110">La gestione dei gruppi in modalità self-service è disponibile solo per specifici di sicurezza di Azure AD e Office 365.</span><span class="sxs-lookup"><span data-stu-id="082d4-110">Optional: Self-service group management is enabled for specific Azure AD security and Office 365 groups</span></span> <span data-ttu-id="082d4-111">Non è disponibile per i gruppi abilitati alla posta elettronica, liste di distribuzione o qualsiasi gruppo che è stato sincronizzato dall'ambiente Active Directory Domain Services (AD DS).</span><span class="sxs-lookup"><span data-stu-id="082d4-111">Self-service group management is available only for Azure AD security and Office 365 groups. It is not available for mail-enabled groups, distribution lists, or any group that has been synchronized from your on-premises Windows Server Active Directory (AD).</span></span>
>

<span data-ttu-id="082d4-112">Per ulteriori informazioni, vedere le [istruzioni per configurare un gruppo Azure AD per la gestione in modalità self-service](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management).</span><span class="sxs-lookup"><span data-stu-id="082d4-112">For more information, see the [instructions to configure an Azure AD group for self-service management](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management).</span></span>

<span data-ttu-id="082d4-113">Come checkpoint provvisorio, è possibile vedere i [criteri di uscita](identity-exit-criteria.md#crit-identity-self-service-groups) per questa sezione.</span><span class="sxs-lookup"><span data-stu-id="082d4-113">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-self-service-groups) for this step.</span></span>

<a name="identity-dyn-groups"></a>
## <a name="set-up-dynamic-group-membership"></a><span data-ttu-id="082d4-114">Configurare l'appartenenza a gruppi dinamici</span><span class="sxs-lookup"><span data-stu-id="082d4-114">Set up dynamic group membership</span></span>

<span data-ttu-id="082d4-115">*Questo passaggio è facoltativo e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="082d4-115">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="082d4-116">In questa sezione si creerà una serie di regole che aggiungono o rimuovono automaticamente gli account utente dai membri di un gruppo di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="082d4-116">In this step, you'll create a series of rules that automatically add or remove user accounts as members of an Azure AD group. This is known as dynamic group membership. The rules are based on user account attributes, such as Department or Country.</span></span> <span data-ttu-id="082d4-117">Questa operazione è denominata *appartenenza dinamica al gruppo*.</span><span class="sxs-lookup"><span data-stu-id="082d4-117">This is known as *dynamic group membership*.</span></span> <span data-ttu-id="082d4-118">Le regole si basano sugli attributi dell’account utente, come il reparto o paese.</span><span class="sxs-lookup"><span data-stu-id="082d4-118">The rules are based on user account attributes, such as Department or Country.</span></span>

<span data-ttu-id="082d4-119">Le regole si applicano nel seguente modo:</span><span class="sxs-lookup"><span data-stu-id="082d4-119">Here’s how the rules are applied:</span></span>

- <span data-ttu-id="082d4-120">Se un nuovo account utente è conforme a tutte le regole relative al gruppo, può essere aggiunto come membro.</span><span class="sxs-lookup"><span data-stu-id="082d4-120">If a new user account matches all the rules for the group, it becomes a member.</span></span>
- <span data-ttu-id="082d4-121">Se un account utente non è un membro del gruppo, ma i suoi attributi vengono modificati per soddisfare le regole del gruppo, allora può essere aggiunto come membro.</span><span class="sxs-lookup"><span data-stu-id="082d4-121">If a user account isn’t a member of the group, but its attributes change so that it matches all the rules for the group, it becomes a member of that group.</span></span>
- <span data-ttu-id="082d4-122">Se un account utente non è conforme alle regole del gruppo, non può essere aggiunto come membro.</span><span class="sxs-lookup"><span data-stu-id="082d4-122">If a user account doesn’t match all the rules for the group, it isn’t added to the group.</span></span>
- <span data-ttu-id="082d4-123">Se un account utente è già membro del gruppo, ma i suoi attributi vengono modificati in modo da non essere più conformi alle regole, l'account verrà rimosso dal gruppo.</span><span class="sxs-lookup"><span data-stu-id="082d4-123">If a user account is a member of the group, but its attributes change so that it no longer matches all the rules for the group, it is removed as a member of the group.</span></span>

<span data-ttu-id="082d4-p105">Per utilizzare l'appartenenza dinamica, è necessario determinare i set di gruppi che possiedono un set comune di attributi di account utente. Per esempio, tutti i membri del Reparto vendite dovrebbero far parte del gruppo delle vendite di Azure AD, avendo impostato l'attributo Reparto dell'account utente su "Vendite".</span><span class="sxs-lookup"><span data-stu-id="082d4-p105">To use dynamic membership, you must first determine the sets of groups that have a common set of user account attributes. For example, all members of the Sales department should be in the Sales Azure AD group, based on the user account attribute Department set to “Sales”.</span></span>

<span data-ttu-id="082d4-126">Vedere le [istruzioni per creare e configurare le regole per un gruppo dinamico di Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="082d4-126">See the [instructions to create and configure the rules for a dynamic Azure AD group](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).</span></span>

<span data-ttu-id="082d4-127">I risultati di questa sezione sono:</span><span class="sxs-lookup"><span data-stu-id="082d4-127">The results of this step are:</span></span>

- <span data-ttu-id="082d4-128">Un set di gruppi di Azure AD che può essere configurato per l'appartenenza dinamica</span><span class="sxs-lookup"><span data-stu-id="082d4-128">A set of Azure AD groups that can be configured for dynamic membership</span></span>
- <span data-ttu-id="082d4-129">Un set di regole per ogni gruppo dinamico</span><span class="sxs-lookup"><span data-stu-id="082d4-129">A set of rules on each dynamic group</span></span>

|||
|:-------|:-----|
|![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="082d4-131">Guida al lab di test: automatizzare le licenze e l'appartenenza ai gruppi</span><span class="sxs-lookup"><span data-stu-id="082d4-131">Test Lab Guide: Automate licenses and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="082d4-132">Come checkpoint provvisorio, è possibile vedere i [criteri di uscita](identity-exit-criteria.md#crit-identity-dyn-groups) per questa sezione.</span><span class="sxs-lookup"><span data-stu-id="082d4-132">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-dyn-groups) for this step.</span></span>

<a name="identity-group-license"></a>
## <a name="set-up-automatic-licensing"></a><span data-ttu-id="082d4-133">Configurare l'assegnazione automatica delle licenze</span><span class="sxs-lookup"><span data-stu-id="082d4-133">Set up automatic licensing</span></span>

<span data-ttu-id="082d4-134">*Questo passaggio è facoltativo e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="082d4-134">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="082d4-135">In questa sezione è possibile configurare gruppi di sicurezza in Azure AD per assegnare automaticamente licenze da un set di abbonamenti a tutti i membri del gruppo.</span><span class="sxs-lookup"><span data-stu-id="082d4-135">In this section, you'll configure security groups in Azure AD to automatically assign licenses from a set of subscriptions to all the members of the group.</span></span> <span data-ttu-id="082d4-136">Questa operazione è denominata *licenze basate sui gruppi*.</span><span class="sxs-lookup"><span data-stu-id="082d4-136">This is known as *group-based licensing*.</span></span> <span data-ttu-id="082d4-137">Se un account utente viene aggiunto o rimosso dal gruppo, le licenze per gli abbonamenti del gruppo verranno automaticamente assegnate o rimosse dall'account utente.</span><span class="sxs-lookup"><span data-stu-id="082d4-137">In this step, you'll configure security groups in Azure AD to automatically assign licenses from a set of subscriptions to all the members of the group. This is known as group-based licensing. If a user account is added to or removed from the group, the licenses for the group’s subscriptions will be automatically assigned or removed from the user account.</span></span>

<span data-ttu-id="082d4-138">Per Microsoft 365 Enterprise è necessario configurare i gruppi di sicurezza di Azure AD per assegnare entrambe queste licenze:</span><span class="sxs-lookup"><span data-stu-id="082d4-138">For Microsoft 365 Enterprise, you'll configure Azure AD security groups to assign both of these licenses:</span></span>

- <span data-ttu-id="082d4-139">Office 365 Enterprise E3 o E5</span><span class="sxs-lookup"><span data-stu-id="082d4-139">Office 365 Enterprise E3 or E5</span></span>
- <span data-ttu-id="082d4-140">Enterprise Mobility + Security (EMS) E3 o E5</span><span class="sxs-lookup"><span data-stu-id="082d4-140">Enterprise Mobility + Security (EMS) E3 or E5</span></span>

<span data-ttu-id="082d4-p107">Utilizzando i gruppi identificati con il Passaggio 2, cercare quelli che contengono un elenco di account in cui tutti i membri del gruppo dispongono di entrambe le licenze di Office 365 ed EMS. Assicurarsi di avere a disposizione abbastanza licenze per tutti i membri del gruppo. Se le licenze a disposizione sono terminate, i nuovi utenti non potranno ottenerne una fino a quando non saranno di nuovo disponibili.</span><span class="sxs-lookup"><span data-stu-id="082d4-p107">Using the groups you identified in Step 2, look for groups that contain a list of accounts where all users in that group must have both Office 365 and EMS licenses. Make sure you have enough licenses for all the group members. If you run out of licenses, new users won’t be assigned licenses until licenses become available.</span></span>

>[!Note]
><span data-ttu-id="082d4-144">Non è necessario configurare l'*assegnazione delle licenze basate su gruppo* per i gruppi contenenti account Azure business to business (B2B).</span><span class="sxs-lookup"><span data-stu-id="082d4-144">You should not configure *group-based licensing* for groups that contain Azure business to business (B2B) accounts.</span></span>
>

<span data-ttu-id="082d4-145">Per ulteriori informazioni, vedere [Informazioni di base sull'assegnazione delle licenze basate su gruppo in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="082d4-145">See additional information on [Group-based licensing basics in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal).</span></span>

<span data-ttu-id="082d4-146">Vedere i [passaggi per configurare l'assegnazione delle licenze basate su gruppo per un gruppo di sicurezza Azure](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="082d4-146">See the [steps to configure group-based licensing for an Azure security group](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).</span></span>

<span data-ttu-id="082d4-147">I risultati di questa sezione sono:</span><span class="sxs-lookup"><span data-stu-id="082d4-147">The results of this step are:</span></span>

- <span data-ttu-id="082d4-148">Sono stati identificati i gruppi di sicurezza idonei per l'assegnazione delle licenze basate su gruppo.</span><span class="sxs-lookup"><span data-stu-id="082d4-148">You've identified which security groups are appropriate for group-based licensing.</span></span>
- <span data-ttu-id="082d4-149">Sono stati configurati i gruppi per l'assegnazione delle licenze basate su gruppo.</span><span class="sxs-lookup"><span data-stu-id="082d4-149">You've configured these groups for group-based licensing.</span></span>

|||
|:-------|:-----|
|![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="082d4-151">Guida al lab di test: automatizzare le licenze e l'appartenenza ai gruppi</span><span class="sxs-lookup"><span data-stu-id="082d4-151">Test Lab Guide: Automate licenses and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="082d4-152">Come checkpoint provvisorio, è possibile vedere i [criteri di uscita](identity-exit-criteria.md#crit-identity-group-license) per questa sezione.</span><span class="sxs-lookup"><span data-stu-id="082d4-152">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-group-license) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="082d4-153">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="082d4-153">Next step</span></span>

[<span data-ttu-id="082d4-154">Criteri uscita dell'infrastruttura di identità</span><span class="sxs-lookup"><span data-stu-id="082d4-154">Identity infrastructure exit criteria</span></span>](identity-exit-criteria.md)
