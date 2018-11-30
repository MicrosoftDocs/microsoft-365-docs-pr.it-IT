---
title: "Passaggio 15: configurare l'appartenenza a gruppi dinamica"
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Comprendere e configurare l'appartenenza automatica a un gruppo dinamico in base agli attributi di un account.
ms.openlocfilehash: 8619179bc4e3ce17d9201cafb88e1b1c48fc7f4f
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868795"
---
# <a name="step-15-set-up-dynamic-group-membership"></a><span data-ttu-id="e73d8-103">Passaggio 15: configurare l'appartenenza a gruppi dinamica</span><span class="sxs-lookup"><span data-stu-id="e73d8-103">Step 15: Set up dynamic group membership</span></span>

<span data-ttu-id="e73d8-104">*Questo passaggio è facoltativo e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="e73d8-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="e73d8-p101">Con questo passaggio, è possibile creare una serie di regole per aggiungere o rimuovere automaticamente gli account utente in un gruppo di Azure AD. Questa operazione è denominata *appartenenza a gruppi dinamica*. Le regole si basano sugli attributi dell'account utente, come il reparto o il Paese.</span><span class="sxs-lookup"><span data-stu-id="e73d8-p101">In Step 12, you'll create a series of rules that automatically add or remove user accounts as members of an Azure AD group. This is known as *dynamic group membership*. The rules are based on user account attributes, such as Department or Country.</span></span>

<span data-ttu-id="e73d8-108">Le regole si applicano nel seguente modo:</span><span class="sxs-lookup"><span data-stu-id="e73d8-108">Here’s how the rules are applied:</span></span>

- <span data-ttu-id="e73d8-109">Se un nuovo account utente è conforme a tutte le regole relative al gruppo, può essere aggiunto come membro.</span><span class="sxs-lookup"><span data-stu-id="e73d8-109">If a new user account matches all the rules for the group, it becomes a member.</span></span>
- <span data-ttu-id="e73d8-110">Se un account utente non è un membro del gruppo, ma i suoi attributi vengono modificati per soddisfare le regole del gruppo, allora può essere aggiunto come membro.</span><span class="sxs-lookup"><span data-stu-id="e73d8-110">If a user account isn’t a member of the group, but its attributes change so that it matches all the rules for the group, it becomes a member of that group.</span></span>
- <span data-ttu-id="e73d8-111">Se un account utente non è conforme alle regole del gruppo, non può essere aggiunto come membro.</span><span class="sxs-lookup"><span data-stu-id="e73d8-111">If a user account doesn’t match all the rules for the group, it isn’t added to the group.</span></span>
- <span data-ttu-id="e73d8-112">Se un account utente è già membro del gruppo, ma i suoi attributi vengono modificati in modo da non essere più conformi alle regole, l'account verrà rimosso dal gruppo.</span><span class="sxs-lookup"><span data-stu-id="e73d8-112">If a user account is a member of the group, but its attributes change so that it no longer matches all the rules for the group, it is removed as a member of the group.</span></span>

<span data-ttu-id="e73d8-p102">Per utilizzare l'appartenenza dinamica, è necessario determinare i set di gruppi che possiedono un set comune di attributi di account utente. Per esempio, tutti i membri del Reparto vendite dovrebbero far parte del gruppo delle vendite di Azure AD, avendo impostato l'attributo Reparto dell'account utente su "Vendite".</span><span class="sxs-lookup"><span data-stu-id="e73d8-p102">To use dynamic membership, you must first determine the sets of groups that have a common set of user account attributes. For example, all members of the Sales department should be in the Sales Azure AD group, based on the user account attribute Department set to “Sales”.</span></span>

<span data-ttu-id="e73d8-115">Vedere le [istruzioni per creare e configurare le regole per un gruppo dinamico di Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="e73d8-115">See the [instructions to create and configure the rules for a dynamic Azure AD group](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).</span></span>

<span data-ttu-id="e73d8-116">I risultati di questo passaggio sono:</span><span class="sxs-lookup"><span data-stu-id="e73d8-116">The results of this step are:</span></span>

- <span data-ttu-id="e73d8-117">Un set di gruppi di Azure AD che può essere configurato per l'appartenenza dinamica</span><span class="sxs-lookup"><span data-stu-id="e73d8-117">A set of Azure AD groups that can be configured for dynamic membership</span></span>
- <span data-ttu-id="e73d8-118">Un set di regole per ogni gruppo dinamico</span><span class="sxs-lookup"><span data-stu-id="e73d8-118">A set of rules on each dynamic group</span></span>

|||
|:-------|:-----|
|![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="e73d8-120">Guida al lab di test: automatizzare le licenze e l'appartenenza ai gruppi</span><span class="sxs-lookup"><span data-stu-id="e73d8-120">Test Lab Guide: Automate licenses and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="e73d8-121">Come checkpoint provvisorio, è possibile vedere i [criteri uscita](identity-exit-criteria.md#crit-identity-dyn-groups) per questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="e73d8-121">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-dyn-groups) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="e73d8-122">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="e73d8-122">Next step</span></span>

[<span data-ttu-id="e73d8-123">Criteri uscita dell'infrastruttura di identità</span><span class="sxs-lookup"><span data-stu-id="e73d8-123">Identity exit criteria</span></span>](identity-exit-criteria.md)
