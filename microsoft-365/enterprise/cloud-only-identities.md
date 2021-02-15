---
title: Identità solo cloud di Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365p_AddUsersWithDirSync
- O365M_AddUsersWithDirSync
- O365E_HRCSetupAADConnectAboutLM617031
- O365E_AddUsersWithDirSync
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOP150
- MOE150
- MBS150
ms.assetid: 01920974-9e6f-4331-a370-13aea4e82b3e
description: Descrive come creare utenti e gruppi quando l'abbonamento a Microsoft 365 usa l'identità solo cloud.
ms.openlocfilehash: 111c42e644913a8f7f6e41d4e8bf65685263f757
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327928"
---
# <a name="microsoft-365-cloud-only-identity"></a><span data-ttu-id="51326-103">Identità solo cloud di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="51326-103">Microsoft 365 cloud-only identity</span></span>

<span data-ttu-id="51326-104">*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.</span><span class="sxs-lookup"><span data-stu-id="51326-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="51326-105">Con l'identità solo cloud, tutti gli utenti, i gruppi e i contatti vengono archiviati nel tenant di Azure Active Directory (Azure AD) dell'abbonamento a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="51326-105">With cloud-only identity, all your users, groups, and contacts are stored in the Azure Active Directory (Azure AD) tenant of your Microsoft 365 subscription.</span></span> <span data-ttu-id="51326-106">Ecco i componenti di base dell'identità solo cloud.</span><span class="sxs-lookup"><span data-stu-id="51326-106">Here are the basic components of cloud-only identity.</span></span>
 
![Componenti di base dell'identità solo cloud](../media/about-microsoft-365-identity/cloud-only-identity.png)

<span data-ttu-id="51326-108">Gli utenti e i relativi account utente nelle organizzazioni possono essere categorizzati in diversi modi.</span><span class="sxs-lookup"><span data-stu-id="51326-108">Users and their user accounts in organizations can be categorized in a number of ways.</span></span> <span data-ttu-id="51326-109">Ad esempio, alcuni sono dipendenti e hanno uno stato permanente.</span><span class="sxs-lookup"><span data-stu-id="51326-109">For example, some are employees and have a permanent status.</span></span> <span data-ttu-id="51326-110">Alcuni sono fornitori, terzisti o partner con uno stato temporaneo.</span><span class="sxs-lookup"><span data-stu-id="51326-110">Some are vendors, contractors, or partners that have a temporary status.</span></span> <span data-ttu-id="51326-111">Alcuni sono utenti esterni che non dispongono di account utente, ma devono comunque disporre dell'accesso a servizi e risorse specifici per supportare l'interazione e la collaborazione.</span><span class="sxs-lookup"><span data-stu-id="51326-111">Some are external users that have no user accounts but must still be granted access to specific services and resources to support interaction and collaboration.</span></span> <span data-ttu-id="51326-112">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="51326-112">For example:</span></span>

- <span data-ttu-id="51326-113">Gli account tenant rappresentano gli utenti all'interno dell'organizzazione con la licenza per i servizi cloud</span><span class="sxs-lookup"><span data-stu-id="51326-113">Tenant accounts represent users within your organization that you license for cloud services</span></span>

- <span data-ttu-id="51326-114">Gli account Business to Business (B2B) rappresentano gli utenti esterni all'organizzazione che vengono invitati a collaborare.</span><span class="sxs-lookup"><span data-stu-id="51326-114">Business to Business (B2B) accounts represent users outside your organization that you invite to participate in collaboration</span></span>

<span data-ttu-id="51326-115">Prendere in controllo i tipi di utenti nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="51326-115">Take stock of the types of users in your organization.</span></span> <span data-ttu-id="51326-116">Quali sono i raggruppamenti?</span><span class="sxs-lookup"><span data-stu-id="51326-116">What are the groupings?</span></span> <span data-ttu-id="51326-117">È ad esempio possibile raggruppare gli utenti in base alla funzione o allo scopo di alto livello dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="51326-117">For example, you can group users by high-level function or purpose to your organization.</span></span>

<span data-ttu-id="51326-p104">Inoltre, alcuni servizi cloud possono essere condivisi al di fuori dell'organizzazione senza alcun account utente. È necessario identificare anche questi gruppi di utenti.</span><span class="sxs-lookup"><span data-stu-id="51326-p104">Additionally, some cloud services can be shared with users outside your organization without any user accounts. You'll need to identify these groups of users as well.</span></span>

<span data-ttu-id="51326-120">È possibile usare i gruppi in Azure AD per diversi scopi che semplificano la gestione dell'ambiente cloud.</span><span class="sxs-lookup"><span data-stu-id="51326-120">You can use groups in Azure AD for several purposes that simplify management of your cloud environment.</span></span> <span data-ttu-id="51326-121">Ad esempio, con i gruppi di Azure AD, puoi:</span><span class="sxs-lookup"><span data-stu-id="51326-121">For example, with Azure AD groups, you can:</span></span>

- <span data-ttu-id="51326-122">Usare le licenze basate su gruppo per assegnare automaticamente le licenze per Microsoft 365 agli account utente non appena vengono aggiunti come membri.</span><span class="sxs-lookup"><span data-stu-id="51326-122">Use group-based licensing to assign licenses for Microsoft 365 to your user accounts automatically as soon as they are added as members.</span></span>
- <span data-ttu-id="51326-123">Aggiungere account utente a gruppi specifici in modo dinamico in base agli attributi degli account utente, ad esempio il nome del reparto.</span><span class="sxs-lookup"><span data-stu-id="51326-123">Add user accounts to specific groups dynamically based on user account attributes, such as department name.</span></span>
- <span data-ttu-id="51326-124">Effettuare automaticamente il provisioning degli utenti per le applicazioni Software as a Service (SaaS) e proteggere l'accesso a tali applicazioni con l'autenticazione a più fattori (MFA) e altri criteri di accesso condizionale.</span><span class="sxs-lookup"><span data-stu-id="51326-124">Automatically provision users for Software as a Service (SaaS) applications and to protect access to those applications with multi-factor authentication (MFA) and other Conditional Access policies.</span></span>
- <span data-ttu-id="51326-125">Eseguire il provisioning delle autorizzazioni e dei livelli di accesso per i siti del team di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="51326-125">Provision permissions and levels of access for SharePoint Online team sites.</span></span>

## <a name="next-steps-for-cloud-only-identity"></a><span data-ttu-id="51326-126">Passaggi successivi per l'identità solo cloud</span><span class="sxs-lookup"><span data-stu-id="51326-126">Next steps for cloud-only identity</span></span>

- [<span data-ttu-id="51326-127">Gestione degli account utente</span><span class="sxs-lookup"><span data-stu-id="51326-127">Manage user accounts</span></span>](manage-microsoft-365-accounts.md)
- <span data-ttu-id="51326-128">[Assegnare licenze agli account utente](assign-licenses-to-user-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="51326-128">[Assign licenses to user accounts](assign-licenses-to-user-accounts.md)</span></span>
- [<span data-ttu-id="51326-129">Gestire i gruppi e l'appartenenza ai gruppi</span><span class="sxs-lookup"><span data-stu-id="51326-129">Manage groups and group membership</span></span>](manage-microsoft-365-groups.md)
- [<span data-ttu-id="51326-130">Gestire le password degli account utente</span><span class="sxs-lookup"><span data-stu-id="51326-130">Manage user account passwords</span></span>](manage-microsoft-365-passwords.md)
