---
title: Identità solo cloud di Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 06/09/2020
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
description: In questo articolo viene descritto come creare utenti e gruppi quando la sottoscrizione Microsoft 365 utilizza l'identità solo cloud.
ms.openlocfilehash: 4c8e7d4a29f548fca2fef9696f488dc333743ef9
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691095"
---
# <a name="microsoft-365-cloud-only-identity"></a><span data-ttu-id="f1dfe-103">Identità solo cloud di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f1dfe-103">Microsoft 365 cloud-only identity</span></span>

<span data-ttu-id="f1dfe-104">*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="f1dfe-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="f1dfe-105">Con l'identità solo cloud, tutti gli utenti, i gruppi e i contatti vengono archiviati nel tenant di Azure Active Directory (Azure AD) dell'abbonamento a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f1dfe-105">With cloud-only identity, all your users, groups, and contacts are stored in the Azure Active Directory (Azure AD) tenant of your Microsoft 365 subscription.</span></span> <span data-ttu-id="f1dfe-106">Ecco i componenti di base dell'identità solo cloud.</span><span class="sxs-lookup"><span data-stu-id="f1dfe-106">Here are the basic components of cloud-only identity.</span></span>
 
![I componenti di base dell'identità solo cloud](../media/about-microsoft-365-identity/cloud-only-identity.png)

<span data-ttu-id="f1dfe-108">Gli utenti e i loro account utente nelle organizzazioni possono essere categorizzati in vari modi.</span><span class="sxs-lookup"><span data-stu-id="f1dfe-108">Users and their user accounts in organizations can be categorized in a number of ways.</span></span> <span data-ttu-id="f1dfe-109">Ad esempio, alcuni sono dipendenti e hanno uno stato permanente.</span><span class="sxs-lookup"><span data-stu-id="f1dfe-109">For example, some are employees and have a permanent status.</span></span> <span data-ttu-id="f1dfe-110">Alcuni sono fornitori, appaltatori o partner che hanno uno stato temporaneo.</span><span class="sxs-lookup"><span data-stu-id="f1dfe-110">Some are vendors, contractors, or partners that have a temporary status.</span></span> <span data-ttu-id="f1dfe-111">Alcuni sono utenti esterni che non dispongono di account utente, ma è comunque necessario concedere l'accesso a servizi e risorse specifici per supportare l'interazione e la collaborazione.</span><span class="sxs-lookup"><span data-stu-id="f1dfe-111">Some are external users that have no user accounts but must still be granted access to specific services and resources to support interaction and collaboration.</span></span> <span data-ttu-id="f1dfe-112">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="f1dfe-112">For example:</span></span>

- <span data-ttu-id="f1dfe-113">Gli account tenant rappresentano gli utenti all'interno dell'organizzazione con la licenza per i servizi cloud</span><span class="sxs-lookup"><span data-stu-id="f1dfe-113">Tenant accounts represent users within your organization that you license for cloud services</span></span>

- <span data-ttu-id="f1dfe-114">Gli account Business to Business (B2B) rappresentano gli utenti esterni all'organizzazione che vengono invitati a collaborare.</span><span class="sxs-lookup"><span data-stu-id="f1dfe-114">Business to Business (B2B) accounts represent users outside your organization that you invite to participate in collaboration</span></span>

<span data-ttu-id="f1dfe-115">Fare un bilancio dei tipi di utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f1dfe-115">Take stock of the types of users in your organization.</span></span> <span data-ttu-id="f1dfe-116">Quali sono i raggruppamenti?</span><span class="sxs-lookup"><span data-stu-id="f1dfe-116">What are the groupings?</span></span> <span data-ttu-id="f1dfe-117">Ad esempio, è possibile raggruppare gli utenti in base alla funzione o allo scopo di alto livello dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f1dfe-117">For example, you can group users by high-level function or purpose to your organization.</span></span>

<span data-ttu-id="f1dfe-p104">Inoltre, alcuni servizi cloud possono essere condivisi al di fuori dell'organizzazione senza alcun account utente. È necessario identificare anche questi gruppi di utenti.</span><span class="sxs-lookup"><span data-stu-id="f1dfe-p104">Additionally, some cloud services can be shared with users outside your organization without any user accounts. You'll need to identify these groups of users as well.</span></span>

<span data-ttu-id="f1dfe-120">È possibile utilizzare i gruppi in Azure AD per diversi scopi che semplificano la gestione dell'ambiente cloud.</span><span class="sxs-lookup"><span data-stu-id="f1dfe-120">You can use groups in Azure AD for several purposes that simplify management of your cloud environment.</span></span> <span data-ttu-id="f1dfe-121">Ad esempio, con i gruppi di Azure AD, è possibile:</span><span class="sxs-lookup"><span data-stu-id="f1dfe-121">For example, with Azure AD groups, you can:</span></span>

- <span data-ttu-id="f1dfe-122">Utilizzare la gestione delle licenze basate su gruppo per assegnare le licenze per Microsoft 365 agli account utente automaticamente non appena vengono aggiunti come membri.</span><span class="sxs-lookup"><span data-stu-id="f1dfe-122">Use group-based licensing to assign licenses for Microsoft 365 to your user accounts automatically as soon as they are added as members.</span></span>
- <span data-ttu-id="f1dfe-123">Aggiungere account utente a gruppi specifici in modo dinamico in base agli attributi degli account utente, ad esempio il nome del reparto.</span><span class="sxs-lookup"><span data-stu-id="f1dfe-123">Add user accounts to specific groups dynamically based on user account attributes, such as department name.</span></span>
- <span data-ttu-id="f1dfe-124">Provisioning automatico degli utenti per le applicazioni del software come servizio (SaaS) e per proteggere l'accesso a tali applicazioni con l'autenticazione a più fattori e altre regole di accesso condizionale.</span><span class="sxs-lookup"><span data-stu-id="f1dfe-124">Automatically provision users for Software as a Service (SaaS) applications and to protect access to those applications with multi-factor authentication (MFA) and other Conditional Access rules.</span></span>
- <span data-ttu-id="f1dfe-125">Provisioning delle autorizzazioni e dei livelli di accesso per i siti del team di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="f1dfe-125">Provision permissions and levels of access for SharePoint Online team sites.</span></span>

<span data-ttu-id="f1dfe-126">È possibile creare nuovi ***utenti*** con:</span><span class="sxs-lookup"><span data-stu-id="f1dfe-126">You create new ***users*** with:</span></span>

- [<span data-ttu-id="f1dfe-127">L'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f1dfe-127">The Microsoft 365 admin center</span></span>](https://docs.microsoft.com/office365/admin/add-users/add-users)
- [<span data-ttu-id="f1dfe-128">PowerShell per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f1dfe-128">PowerShell for Microsoft 365</span></span>](create-user-accounts-with-microsoft-365-powershell.md)

<span data-ttu-id="f1dfe-129">È possibile creare nuovi ***gruppi*** con:</span><span class="sxs-lookup"><span data-stu-id="f1dfe-129">You create new ***groups*** with:</span></span>

- [<span data-ttu-id="f1dfe-130">L'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f1dfe-130">The Microsoft 365 admin center</span></span>](https://docs.microsoft.com/office365/admin/create-groups/create-groups)
- [<span data-ttu-id="f1dfe-131">PowerShell per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f1dfe-131">PowerShell for Microsoft 365</span></span>](manage-microsoft-365-groups-with-powershell.md)


## <a name="next-step-for-cloud-only-identity"></a><span data-ttu-id="f1dfe-132">Passaggio successivo per l'identità solo cloud</span><span class="sxs-lookup"><span data-stu-id="f1dfe-132">Next step for cloud-only identity</span></span>

<span data-ttu-id="f1dfe-133">[Assegnare licenze agli account utente](assign-licenses-to-user-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="f1dfe-133">[Assign licenses to user accounts](assign-licenses-to-user-accounts.md)</span></span>
