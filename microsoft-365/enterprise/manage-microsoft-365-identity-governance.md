---
title: Gestire la governance delle identità di Microsoft 365
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
description: Informazioni su come utilizzare le funzionalità di governance dell'identità di Microsoft 365.
ms.openlocfilehash: e4c537e7fa3ac099caf8b7dbc44327308751c8f5
ms.sourcegitcommit: 33afa334328cc4e3f2474abd611c1411adabd39f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2020
ms.locfileid: "48370347"
---
# <a name="manage-microsoft-365-identity-governance"></a><span data-ttu-id="e4fce-103">Gestire la governance delle identità di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e4fce-103">Manage Microsoft 365 identity governance</span></span>

<span data-ttu-id="e4fce-104">Identity Governance consente di proteggere, monitorare e controllare l'accesso alle risorse strategiche e garantire la produttività dei dipendenti.</span><span class="sxs-lookup"><span data-stu-id="e4fce-104">Identity governance is all about protecting, monitoring, and auditing access to critical assets while ensuring employee productivity.</span></span> <span data-ttu-id="e4fce-105">Ad esempio, con Identity Governance è possibile fare in modo che gli utenti giusti abbiano diritto di accesso alle risorse giuste e determinare se l'accesso cambia nel corso del tempo.</span><span class="sxs-lookup"><span data-stu-id="e4fce-105">For example, with identity governance, you can ensure that the right users have the right access to the right resources and determine if that access changes over time.</span></span>

<span data-ttu-id="e4fce-106">Per ulteriori informazioni, vedere questa [Panoramica della governance delle identità per Azure Active Directory (Azure ad)](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview).</span><span class="sxs-lookup"><span data-stu-id="e4fce-106">For more information, See this [overview of identity governance for Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview).</span></span>

## <a name="set-up-azure-ad-access-reviews"></a><span data-ttu-id="e4fce-107">Impostare le verifiche di accesso di Azure AD</span><span class="sxs-lookup"><span data-stu-id="e4fce-107">Set up Azure AD access reviews</span></span>

<span data-ttu-id="e4fce-108">Le recensioni di Azure AD Access consentono di controllare l'accesso di un utente per assicurarsi che solo le persone giuste abbiano accesso continuato.</span><span class="sxs-lookup"><span data-stu-id="e4fce-108">Azure AD access reviews allow you to review a user's access to ensure only the right people have continued access.</span></span> <span data-ttu-id="e4fce-109">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e4fce-109">For example:</span></span>

- <span data-ttu-id="e4fce-110">Quando un nuovo dipendente si unisce all'organizzazione, è necessario assicurarsi che disponga dell'accesso giusto per essere produttivo.</span><span class="sxs-lookup"><span data-stu-id="e4fce-110">As a new employee joins your organization, you need to ensure they have the right access to be productive.</span></span>
- <span data-ttu-id="e4fce-111">Quando questo dipendente si sposta in altri team, posizioni o dipartimenti, è necessario assicurarsi che l'accesso ai team, alle posizioni o ai dipartimenti precedenti venga rimosso se necessario.</span><span class="sxs-lookup"><span data-stu-id="e4fce-111">As that employee moves to other teams, locations, or departments, you need to ensure that their access to previous teams, locations, or departments are removed as needed.</span></span>
- <span data-ttu-id="e4fce-112">Se il dipendente o un ospite lascia l'organizzazione, è necessario assicurarsi che l'accesso venga rimosso.</span><span class="sxs-lookup"><span data-stu-id="e4fce-112">When that employee or a guest leaves your organization, you need to ensure their access is removed.</span></span>

<span data-ttu-id="e4fce-113">Questo è particolarmente importante se l'organizzazione è soggetta a controlli di sicurezza per determinare se gli account utente hanno un accesso troppo esteso, il che potrebbe comportare sanzioni pecuniarie in caso di violazione delle normative di settore o regionali.</span><span class="sxs-lookup"><span data-stu-id="e4fce-113">This is especially important if your organization is subject to security audits to determine if user accounts have too much access, which could result in fines if in violation of industry or regional regulations.</span></span>

<span data-ttu-id="e4fce-114">Per ulteriori informazioni, vedere la [Panoramica delle recensioni di Access](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview).</span><span class="sxs-lookup"><span data-stu-id="e4fce-114">For more information, see the [overview of access reviews](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview).</span></span>

<span data-ttu-id="e4fce-115">Vedere questi articoli per configurare tipi diversi di verifica di accesso:</span><span class="sxs-lookup"><span data-stu-id="e4fce-115">See these articles to configure different types of access reviews:</span></span>

- [<span data-ttu-id="e4fce-116">Gruppi e app</span><span class="sxs-lookup"><span data-stu-id="e4fce-116">Groups and apps</span></span>](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [<span data-ttu-id="e4fce-117">Ruoli di Azure AD</span><span class="sxs-lookup"><span data-stu-id="e4fce-117">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [<span data-ttu-id="e4fce-118">Ruoli delle risorse di Azure</span><span class="sxs-lookup"><span data-stu-id="e4fce-118">Azure resource roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

## <a name="set-up-azure-ad-entitlement-management"></a><span data-ttu-id="e4fce-119">Configurare la gestione dei diritti di Azure AD</span><span class="sxs-lookup"><span data-stu-id="e4fce-119">Set up Azure AD entitlement management</span></span>

<span data-ttu-id="e4fce-120">Gestione dei diritti di wiht Azure AD, è possibile gestire il ciclo di vita delle identità e dell'accesso in scala automatizzando i flussi di lavoro delle richieste di accesso, le assegnazioni di accesso, le recensioni e la scadenza.</span><span class="sxs-lookup"><span data-stu-id="e4fce-120">Wiht Azure AD entitlement management, you can manage the identity and access lifecycle at scale by automating access request workflows, access assignments, reviews, and expiration.</span></span>

<span data-ttu-id="e4fce-121">I dipendenti devono accedere a vari gruppi, applicazioni e siti per svolgere il proprio lavoro.</span><span class="sxs-lookup"><span data-stu-id="e4fce-121">Your employees need access to various groups, applications, and sites to perform their job.</span></span> <span data-ttu-id="e4fce-122">La gestione di questo accesso può essere difficile perché i requisiti cambiano, vengono aggiunte nuove applicazioni o gli utenti hanno bisogno di ulteriori diritti di accesso.</span><span class="sxs-lookup"><span data-stu-id="e4fce-122">Managing this access can be challenging because requirements change, new applications are added, or users need additional access rights.</span></span> <span data-ttu-id="e4fce-123">Quando si collabora con altre organizzazioni, potrebbe non essere possibile sapere chi nell'altra organizzazione ha bisogno di accedere alle risorse dell'organizzazione e gli utenti esterni non sapranno quali applicazioni, gruppi o siti utilizza l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e4fce-123">When you collaborate with other organizations, you may not know who in the other organization needs access to your organization's resources, and outside users won't know what applications, groups, or sites your organization is using.</span></span>

<span data-ttu-id="e4fce-124">La gestione dei diritti di Azure AD può aiutare a gestire in modo più efficiente l'accesso ai gruppi, alle applicazioni e ai siti di SharePoint per gli utenti interni ed esterni.</span><span class="sxs-lookup"><span data-stu-id="e4fce-124">Azure AD entitlement management can help you more efficiently manage access to groups, applications, and SharePoint sites for internal and outside users.</span></span>
 
<span data-ttu-id="e4fce-125">Per ulteriori informazioni, vedere la [Panoramica della gestione dei diritti di Azure ad](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview).</span><span class="sxs-lookup"><span data-stu-id="e4fce-125">For more information, see the [overview of Azure AD entitlement management](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview).</span></span>
