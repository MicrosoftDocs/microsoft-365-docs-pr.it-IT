---
title: 'Passaggio 7: Configurare Identity Governance'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/06/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Informazioni su Identity Governance per il tenant di Azure AD e su come configurarlo.
ms.openlocfilehash: 1c0eab574e5436dd0c88a0b46d1916281bcf0577
ms.sourcegitcommit: 63e35b846d964dde5919a08c2fe432e749e8eff6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/19/2019
ms.locfileid: "37047359"
---
# <a name="step-7-configure-identity-governance"></a><span data-ttu-id="3769b-103">Passaggio 7: Configurare Identity Governance</span><span class="sxs-lookup"><span data-stu-id="3769b-103">Step 7: Configure identity governance</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="3769b-104">Identity Governance consente di proteggere, monitorare e controllare l'accesso alle risorse più importanti e garantire la produttività dei dipendenti.</span><span class="sxs-lookup"><span data-stu-id="3769b-104">Identity governance is all about protecting, monitoring, and auditing access to critical assets while ensuring employee productivity.</span></span> <span data-ttu-id="3769b-105">Ad esempio, con Identity Governance è possibile fare in modo che gli utenti giusti abbiano diritto di accesso alle risorse giuste e determinare se l'accesso cambia nel corso del tempo.</span><span class="sxs-lookup"><span data-stu-id="3769b-105">For example, with identity governance, you can ensure that the right users have the right access to the right resources and determine if that access changes over time.</span></span>

<span data-ttu-id="3769b-106">Vedere [questo articolo](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) per maggiori informazioni su Identity Governance per Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="3769b-106">See [this article](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) for more information about identity governance for Azure Active Directory (Azure AD).</span></span>

<a name="identity-access-reviews"></a>
## <a name="set-up-azure-ad-access-reviews"></a><span data-ttu-id="3769b-107">Impostare le verifiche di accesso di Azure AD</span><span class="sxs-lookup"><span data-stu-id="3769b-107">Set up Azure AD access reviews</span></span>

<span data-ttu-id="3769b-108">*Questo passaggio è facoltativo e si applica solo alla versione E5 di Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="3769b-108">*This is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="3769b-109">In questo passaggio verranno configurate le verifiche di accesso di Azure AD, che consentono di verificare l'accesso di un utente per garantire che solo le persone giuste dispongano di un accesso continuo.</span><span class="sxs-lookup"><span data-stu-id="3769b-109">In this step, you'll set up Azure AD access reviews, which allow you to review a user's access to ensure only the right people have continued access.</span></span> <span data-ttu-id="3769b-110">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="3769b-110">For example:</span></span>

- <span data-ttu-id="3769b-111">Quando un nuovo dipendente si unisce all'organizzazione, è necessario assicurarsi che disponga dell'accesso giusto per essere produttivo.</span><span class="sxs-lookup"><span data-stu-id="3769b-111">As a new employee joins your organization, you need to ensure they have the right access to be productive.</span></span>
- <span data-ttu-id="3769b-112">Quando questo dipendente si sposta in altri team, posizioni o dipartimenti, è necessario assicurarsi che l'accesso ai team, alle posizioni o ai dipartimenti precedenti venga rimosso se necessario.</span><span class="sxs-lookup"><span data-stu-id="3769b-112">As that employee moves to other teams, locations, or departments, you need to ensure that their access to previous teams, locations, or departments are removed as needed.</span></span>
- <span data-ttu-id="3769b-113">Se il dipendente o un ospite lascia l'organizzazione, è necessario assicurarsi che l'accesso venga rimosso.</span><span class="sxs-lookup"><span data-stu-id="3769b-113">When that employee or a guest leaves your organization, you need to ensure their access is removed.</span></span>

<span data-ttu-id="3769b-114">Questo è particolarmente importante se l'organizzazione è soggetta a controlli di sicurezza per determinare se gli account utente hanno un accesso troppo esteso, il che potrebbe comportare sanzioni pecuniarie in caso di violazione delle normative di settore o regionali.</span><span class="sxs-lookup"><span data-stu-id="3769b-114">This is especially important if your organization is subject to security audits to determine if user accounts have too much access, which could result in fines if in violation of industry or regional regulations.</span></span>

<span data-ttu-id="3769b-115">Vedere [questo articolo](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview) per maggiori informazioni sulle verifiche di accesso di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3769b-115">See [this article](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview) for more information about Azure AD access reviews.</span></span>

<span data-ttu-id="3769b-116">Vedere questi articoli per configurare tipi diversi di verifica di accesso:</span><span class="sxs-lookup"><span data-stu-id="3769b-116">See these articles to configure different types of access reviews:</span></span>

- [<span data-ttu-id="3769b-117">Gruppi e app</span><span class="sxs-lookup"><span data-stu-id="3769b-117">Groups and apps</span></span>](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [<span data-ttu-id="3769b-118">Ruoli di Azure AD</span><span class="sxs-lookup"><span data-stu-id="3769b-118">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [<span data-ttu-id="3769b-119">Ruoli delle risorse di Azure</span><span class="sxs-lookup"><span data-stu-id="3769b-119">Azure resource roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

<span data-ttu-id="3769b-120">Come checkpoint provvisorio, è possibile vedere i [criteri di uscita](identity-exit-criteria.md#crit-identity-access-reviews) per questa sezione.</span><span class="sxs-lookup"><span data-stu-id="3769b-120">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-access-reviews) for this section.</span></span>

## <a name="next-step"></a><span data-ttu-id="3769b-121">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="3769b-121">Next step</span></span>

[<span data-ttu-id="3769b-122">Criteri uscita dell'infrastruttura di identità</span><span class="sxs-lookup"><span data-stu-id="3769b-122">Identity infrastructure exit criteria</span></span>](identity-exit-criteria.md)

