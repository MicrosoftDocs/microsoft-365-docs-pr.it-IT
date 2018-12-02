---
title: "Passaggio 12: configurare l'assegnazione automatica delle licenze"
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
description: Comprendere e configurare l'assegnazione delle licenze basate su gruppo per i gruppi di Azure AD.
ms.openlocfilehash: 82e4192f2ef9ba3d1d5ed7bd99a8cf603d7d4cc9
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868261"
---
# <a name="step-12-set-up-automatic-licensing"></a><span data-ttu-id="8a836-103">Passaggio 12: configurare l'assegnazione automatica delle licenze</span><span class="sxs-lookup"><span data-stu-id="8a836-103">Step 12: Set up automatic licensing</span></span>

<span data-ttu-id="8a836-104">*Questo passaggio è facoltativo e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="8a836-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="8a836-p101">In questo passaggio, i gruppi di sicurezza in Azure AD verranno configurati in modo da assegnare automaticamente le licenze da un set di sottoscrizioni a tutti i membri del gruppo. Questa funzionalità è conosciuta come *assegnazione delle licenze basate su gruppo*. Se un account utente viene aggiunto o rimosso da un gruppo, le licenze per le sottoscrizioni del gruppo verranno assegnate o rimosse automaticamente dall'account utente.</span><span class="sxs-lookup"><span data-stu-id="8a836-p101">In Step 11, you'll configure security groups in Azure AD to automatically assign licenses from a set of subscriptions to all the members of the group. This is known as *group-based licensing*. If a user account is added to or removed from the group, the licenses for the group’s subscriptions will be automatically assigned or removed from the user account.</span></span>

<span data-ttu-id="8a836-108">Per Microsoft 365 Enterprise è necessario configurare i gruppi di sicurezza di Azure AD per assegnare entrambe queste licenze:</span><span class="sxs-lookup"><span data-stu-id="8a836-108">For Microsoft 365 Enterprise, you'll configure Azure AD security groups to assign both of these licenses:</span></span>

- <span data-ttu-id="8a836-109">Office 365 Enterprise E3 o E5</span><span class="sxs-lookup"><span data-stu-id="8a836-109">Office 365 Enterprise E3 or E5</span></span>
- <span data-ttu-id="8a836-110">Enterprise Mobility + Security (EMS) E3 o E5</span><span class="sxs-lookup"><span data-stu-id="8a836-110">Enterprise Mobility + Security (EMS) E3 or E5</span></span>

<span data-ttu-id="8a836-p102">Utilizzando i gruppi identificati con il Passaggio 2, cercare quelli che contengono un elenco di account in cui tutti i membri del gruppo dispongono di entrambe le licenze di Office 365 ed EMS. Assicurarsi di avere a disposizione abbastanza licenze per tutti i membri del gruppo. Se le licenze a disposizione sono terminate, i nuovi utenti non potranno ottenerne una fino a quando non saranno di nuovo disponibili.</span><span class="sxs-lookup"><span data-stu-id="8a836-p102">Using the groups you identified in Step 2, look for groups that contain a list of accounts where all users in that group must have both Office 365 and EMS licenses. Make sure you have enough licenses for all the group members. If you run out of licenses, new users won’t be assigned licenses until licenses become available.</span></span>

>[!Note]
><span data-ttu-id="8a836-114">Non è necessario configurare l'*assegnazione delle licenze basate su gruppo* per i gruppi contenenti account Azure business to business (B2B).</span><span class="sxs-lookup"><span data-stu-id="8a836-114">You should not configure *group-based licensing* for groups that contain Azure business to business (B2B) accounts.</span></span>
>

<span data-ttu-id="8a836-115">Per ulteriori informazioni, vedere [Informazioni di base sull'assegnazione delle licenze basate su gruppo in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="8a836-115">See additional information on [Group-based licensing basics in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal).</span></span>

<span data-ttu-id="8a836-116">Vedere i [passaggi per configurare l'assegnazione delle licenze basate su gruppo per un gruppo di sicurezza Azure](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="8a836-116">See the [steps to configure group-based licensing for an Azure security group](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).</span></span>

<span data-ttu-id="8a836-117">I risultati di questo passaggio sono:</span><span class="sxs-lookup"><span data-stu-id="8a836-117">The results of this step are:</span></span>

- <span data-ttu-id="8a836-118">Sono stati identificati i gruppi di sicurezza idonei per l'assegnazione delle licenze basate su gruppo.</span><span class="sxs-lookup"><span data-stu-id="8a836-118">You've identified which security groups are appropriate for group-based licensing.</span></span>
- <span data-ttu-id="8a836-119">Sono stati configurati i gruppi per l'assegnazione delle licenze basate su gruppo.</span><span class="sxs-lookup"><span data-stu-id="8a836-119">You've configured these groups for group-based licensing.</span></span>

|||
|:-------|:-----|
|![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="8a836-121">Guida al lab di test: automatizzare le licenze e l'appartenenza ai gruppi</span><span class="sxs-lookup"><span data-stu-id="8a836-121">Test Lab Guide: Automate licenses and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="8a836-122">Come checkpoint provvisorio, è possibile vedere i [criteri uscita](identity-exit-criteria.md#crit-identity-group-license) per questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="8a836-122">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-group-license) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="8a836-123">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="8a836-123">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step13.png)| [<span data-ttu-id="8a836-124">Monitorare l'attività di tenant e di accesso</span><span class="sxs-lookup"><span data-stu-id="8a836-124">Monitor tenant and sign-in activity</span></span>](identity-azure-ad-access-usage-reporting.md) |

