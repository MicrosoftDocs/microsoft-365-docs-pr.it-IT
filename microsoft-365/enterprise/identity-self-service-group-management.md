---
title: 'Passaggio 14: consentire agli utenti di creare e gestire i propri gruppi'
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
description: Capire e configurare la gestione dei gruppi self-service di Azure AD
ms.openlocfilehash: d46e82fd72b8eef896a223229a2cc3d25ae56c76
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868608"
---
# <a name="step-14-allow-users-to-create-and-manage-their-own-groups"></a><span data-ttu-id="54dd3-103">Passaggio 14: consentire agli utenti di creare e gestire i propri gruppi</span><span class="sxs-lookup"><span data-stu-id="54dd3-103">Step 14: Allow users to create and manage their own groups</span></span>

<span data-ttu-id="54dd3-104">*Questo passaggio è facoltativo e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="54dd3-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="54dd3-p101">In questo passaggio, vengono identificati i gruppi di Azure Active Directory (AD) che possono essere gestiti da proprietari di gruppi invece che da amministratori IT. Nota come *gestione gruppi self-service*, questa funzione consente ai proprietari dei gruppi senza ruolo amministrativo di creare e gestire gruppi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="54dd3-p101">In Step 14, you'll identify Azure Active Directory (AD) groups that can be managed by group owners instead of IT administrators. Known as *self-service group management*, this feature allows group owners who are not assigned an administrative role to create and manage security groups.</span></span> 

<span data-ttu-id="54dd3-p102">Gli utenti possono richiedere l'appartenenza a un gruppo di sicurezza e la richiesta passa al proprietario del gruppo invece che a un amministratore IT. Ciò permette che il controllo quotidiano dell'appartenenza al gruppo sia delegato ai proprietari del team, di progetto o aziendali che capiscano l'uso del gruppo e che possono gestirne l'appartenenza.</span><span class="sxs-lookup"><span data-stu-id="54dd3-p102">Users can request membership in a security group and that request goes to the group owner, rather than an IT administrator. This allows the day-to-day control of group membership to be delegated to team, project, or business owners who understand the business use for the group and can manage its membership.</span></span>

>[!Note]
><span data-ttu-id="54dd3-p103">La gestione gruppi self-service è disponibile solo per la sicurezza Azure AD e i gruppi Office 365. Non è disponibile per i gruppi abilitati alla posta elettronica, liste di distribuzione o per gruppi sincronizzati da Windows Server Active Directory (AD) locale.</span><span class="sxs-lookup"><span data-stu-id="54dd3-p103">Self-service group management is available only for Azure AD security and Office 365 groups. It is not available for mail-enabled groups, distribution lists, or any group that has been synchronized from your on-premises Windows Server Active Directory (AD).</span></span>
>

<span data-ttu-id="54dd3-111">Per ulteriori informazioni, vedere le [istruzioni per configurare un gruppo Azure Active Directory per la gestione in modalità self-service](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management).</span><span class="sxs-lookup"><span data-stu-id="54dd3-111">For more information, see the [instructions to configure an Azure AD group for self-service management](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management).</span></span>

<span data-ttu-id="54dd3-112">Come checkpoint provvisorio, è possibile vedere i [criteri uscita](identity-exit-criteria.md#crit-identity-self-service-groups) per questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="54dd3-112">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-self-service-groups) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="54dd3-113">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="54dd3-113">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step15.png)| [<span data-ttu-id="54dd3-114">Configurare l'appartenenza a gruppi dinamica</span><span class="sxs-lookup"><span data-stu-id="54dd3-114">Set up dynamic group membership</span></span>](identity-automatic-group-membership.md) |
